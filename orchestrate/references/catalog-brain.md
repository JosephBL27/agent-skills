# Catalog — brain, memory, sessions

The Obsidian vault at `<your vault>` is the single
brain. **Do not stand up a second memory system** — that is why gstack's `gbrain`
was deliberately skipped and why `claude-mem` is still unapproved.

## Session lifecycle

- `resume [N] [search]` — load CLAUDE.md + last N session logs, optionally
  grepping. **Start of a continuing thread.**
- `compress [slug]` — save the session to `20 Areas/Session-Logs/` before ending.
- `preserve [insight]` — append a durable learning to the vault's `90 Meta/CLAUDE.md`
  (auto-archives at 280 lines).
- `gstack-context-save` / `gstack-context-restore` — lighter, project-scoped
  working context. Complementary to `compress`, not a replacement.

## Vault maintenance

- `brain-steward` (agent) — closes the detect→repair loop. Use when Brain Health
  shows unresolved drift, a metric has not moved in over a week, `_MAP` is past
  its freshness contract, or on scheduled maintenance. **Not** for answering
  questions about Joseph — that is ordinary vault reading.
- `_archive:scan-brain` — re-scan local + Drive sources, refresh the index.
- `_archive:past-projects` — search prior work before designing something new.
- `_archive:anecdote` — the voice bank. See `catalog-writing.md`.
- `anthropic-skills:consolidate-memory` — merge duplicate memories, fix stale
  facts, prune the index.
- `productivity:memory-management` / `task-management` / `update` / `start` —
  the productivity plugin's own two-tier memory. **Overlaps the vault — do not
  adopt without asking.**

## Boot order (read-order == precedence-order)

1. `90 Meta/Identity.md` — Tier 0, who Joseph is
2. `AGENTS.md` — the multi-agent contract
3. `90 Meta/Memory-Protocol.md` — required before touching Gmail/Drive/Messages
4. `90 Meta/CLAUDE.md` — Claude-specific elaboration
5. `90 Meta/Operating Principles.md` — lowest precedence
6. Tier files as relevant: Accounts · Education · Work · Skills · Career ·
   Medical · `60 People/<Name>.md` · `30 Resources/Anecdotes/`
7. The relevant PARA folder

## Never without confirmation

`vault_delete` on any note · bulk renames or moves · edits to `90 Meta/CLAUDE.md`,
`Identity.md`, or `Operating Principles.md` — **propose first, write after "go"**
(Identity *content* may be updated once Joseph confirms a fact).

## Proactively

- Surface follow-ups as `- [ ]` checkboxes after writing a meeting or daily note.
- Flag a `10 Projects/` file untouched for 14+ days as possibly ready to archive.
- On learning something durable, update the **right tier file** — personal facts →
  Identity, logins → Accounts, school → Education, health → Medical, career →
  Career, automation → Codex Automations, a recurring person → `60 People/`.

## Scheduling and recurrence

- `schedule` — cron-scheduled cloud agents, or a one-time future run.
- `loop` — run a prompt/command on an interval, or self-paced.
- `anthropic-skills:schedule` / `anthropic-skills:morning` — scheduled routines
  and the morning brief.
- Check `90 Meta/Codex Automations.md` **before** assuming a background job runs
  or changing automation state.

## Known failure modes

- Obsidian MCP "not connected" is usually **Obsidian being closed**, not a server
  fault. Diagnose from client MCP logs, not guesses.
- Bare wikilinks in YAML frontmatter (`related: `A`, `B``) **silently discard
  the whole property block**. Use a block list of quoted strings, and verify
  through the parser, never by reading.
- A metric that never moves is a detector bug until proven otherwise. When an
  authoritative parser exists, query it; report NOT CHECKED rather than 0.
