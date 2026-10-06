# Catalog — platform, config, automation

## Claude Code configuration

- `claude-code-setup` (**Anthropic, official**) — scans a codebase and recommends
  hooks, skills, subagents, and MCP servers for it. The orchestrator's project
  onboarding step. Run once per repo; its output is *evidence*, not instructions.
- `update-config` — anything in `settings.json`: permissions, env vars, and
  **hooks**. Automated behaviours ("from now on when X", "whenever X", "after X")
  **require hooks** — the harness executes those, not you, so memory and
  preferences cannot deliver them. Route every "always do X" request here.
- `fewer-permission-prompts` — scan transcripts, build an allowlist of common
  read-only calls to cut prompt fatigue.
- `keybindings-help` — `~/.claude/keybindings.json`.
- `init` — create a CLAUDE.md for a codebase.
- Terminal-dialog commands (`/permissions`, `/config`, `/doctor`, `/hooks`) open
  an interactive panel and are **not available in this session** — point Joseph at
  the app UI or an interactive `claude` terminal instead.

## Hooks

- `hookify:hookify` — create hooks from conversation analysis or explicit
  instruction. `hookify:list` / `configure` / `help` / `writing-rules`.
- **Hooks in force (updated 2026-09-24):** a SessionStart hook
  (`~/.claude/hooks/session-start-setup.sh`, local only, also surfaces the absence
  watchdog's stale jobs), a GLOBAL PostToolUse vault frontmatter guard
  (`~/.claude/hooks/vault-frontmatter-guard.sh`, advisory, covers Write/Edit and the
  Obsidian MCP writes), impeccable's PostToolUse + Stop in `settings.local.json`,
  hookify's own plugin hooks, and two project-scoped hookify rules in the vault.
  All advisory: nothing blocks, because headless jobs cannot answer a deny. Adding
  another global hook is still a standing-configuration change: **ask first.**

## Skills and plugins

- `anthropic-skills:skill-creator` — build a new skill. The terminus of
  `learn-from-video`. Improve an existing skill before creating a duplicate.
- `find-skills` — search the open ecosystem before building.
- `cowork-plugin-management:create-cowork-plugin` / `cowork-plugin-customizer` —
  author or tailor a plugin.
- `anthropic-skills:setup-cowork`, `anthropic-skills:mcp-builder`.
- Install pattern used here: canonical git clone in `~/.agents/skills/<name>`,
  symlinked into **both** `~/.claude/skills` and `~/.codex/skills`, so one
  `git pull` updates every host. Prefer this over `npx skills add` snapshots,
  which do not update and produce duplicate entries.

## Cross-agent

- `codex:rescue` — hand investigation or a substantial coding task to Codex.
  `codex:setup` — check the local Codex CLI and the stop-time review gate.
- `codex:codex-cli-runtime`, `codex:codex-result-handling`,
  `codex:gpt-5-4-prompting` — internal contracts; read before driving Codex.
- `gstack-codex` — the gstack wrapper, three modes.
- Antigravity has no host of its own and delegates. Capability matrix lives in
  `90 Meta/Agent Capabilities.md`; paths in `90 Meta/External Files Index.md`.

## MCP servers currently wired (updated 2026-09-24)

`obsidian` (vault, native HTTP) · `google_workspace` (pinned 2.0.9, offline start) ·
`microsoft365` (fails until Joseph's Okta + Duo login) · `context7` (live docs,
vendored 4.1.1) · `playwright` (real-browser QA, vendored 0.0.82; only
`browser_run_code_unsafe` and `browser_file_upload` are denied). All start locally, with no
npx at session start. Several connector plugins need OAuth and are **unavailable in a
non-interactive session** — say so rather than retrying.

**Language servers (Claude Code plugins):** `pyright-lsp` and `typescript-lsp-noata@joseph-local`
are live. `swift-lsp` is off until `xcode-build-server` exists, because it reports false errors.
**On trial, not registered:** Peekaboo, behind the read-only `peekaboo-safe` wrapper, and a
pinned research-data library set. **Rejected:** iMCP (LAN-exposed) and icalBuddy (unmaintained).
There is no safe off-the-shelf calendar or contacts server. Details:
`90 Meta/Setup/Local-MCP-Servers.md`, `90 Meta/Setup/Language-Servers.md`.

## Dormant by design

- **OmniRoute** — cloned inert at `~/AgentRuntime/OmniRoute`. Not npm-installed,
  no server, no `ANTHROPIC_BASE_URL`. Routes prompts and source through ~291
  third-party providers. **Only** for exhausted Claude usage, per Joseph; never a
  default, never silently in-path. **Ask before activating.**
- `gstack-setup-gbrain` — second brain, skipped.
- Team-mode SessionStart hook and plan-tune hooks — skipped so no network call
  fires on every session start, including scheduled runs.

## Credentials — the hard boundary

Claude **cannot** create accounts, enter passwords, or type API keys — this does
not lift with permission. Prepare the slot, then stop.
Keys live at `~/.config/agent-keys/.env` (mode 0600, never committed, never copied
into the vault). Currently: `GEMINI_API_KEY` live; `MANUS_API_KEY` blank (paid
tier). **Use header auth, never a key in a URL.**
