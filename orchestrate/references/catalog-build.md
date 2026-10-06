# Catalog — build, debug, ship, data

Format: `skill — use when. **not for** what it is mistaken for.`

## The sprint (gstack) — think → plan → build → review → test → ship → reflect

- `gstack-spec` — vague intent → executable spec, five phases. Use before building
  anything with unclear requirements. **not for** work already specified.
- `gstack-office-hours` — YC-style pressure test on an idea or direction.
- `gstack-autoplan` — runs CEO + design + eng + DX plan reviews sequentially with
  auto-decisions. Use for a plan worth four lenses. **not for** a one-file change.
- `gstack-plan-ceo-review` / `-eng-review` / `-design-review` / `-devex-review` —
  the individual lenses when you want one, interactively.
- `gstack-investigate` — **root-cause first, no fixes before investigation.** Use
  the moment a bug's cause is not obvious. This is the default debugging entry.
- `gstack-review` — staff-eng review of a diff before landing.
- `gstack-cso` — security review, OWASP + STRIDE. Use for auth, secrets, input
  handling, anything internet-facing.
- `gstack-codex` — cross-model second opinion via Codex CLI. Use when stuck or
  when a second architecture read is worth it.
- `gstack-qa` — QA a web app **and fix** what it finds. `gstack-qa-only` reports
  without fixing.
- `gstack-health` — code-quality dashboard. `gstack-benchmark` — perf regressions.
- `gstack-ship` — merge base, tests, diff review, version bump, changelog, PR.
- `gstack-land-and-deploy` / `gstack-canary` / `gstack-landing-report` — deploy
  and watch. `gstack-setup-deploy` configures it once.
- `gstack-retro` / `gstack-learn` / `gstack-document-release` — reflect and record.
- `gstack-careful` / `gstack-guard` / `gstack-freeze` / `gstack-unfreeze` — safety
  rails: destructive-command warnings and directory-scoped edits.
- `gstack-context-save` / `gstack-context-restore` — working context across sessions.
- `gstack-document-generate` — docs from scratch for a module or project.
- `gstack-make-pdf` — markdown → publication-quality PDF.
- `gstack-diagram` — English or mermaid → editable `.excalidraw` triplet.
- `gstack-scrape` / `gstack-browse` — headless browser work. `gstack-skillify`
  freezes a successful scrape into a permanent skill.
- `gstack-upgrade`, `gstack-plan-tune`, `gstack-benchmark-models`,
  `gstack-pair-agent`, `gstack-connect-chrome`, `gstack-setup-browser-cookies` —
  maintenance and browser plumbing.
- **Skipped deliberately:** `gstack-setup-gbrain` / `gstack-sync-gbrain` — the
  vault is the brain. Do not stand up a second one without asking.

## React / frontend correctness

- `react-doctor` — 400+ rules: lint, a11y, bundle size, architecture. Run when
  finishing a feature or before committing React. Regression-check mode included.
- `improve-react` — whole-codebase audit → prioritised plans for other agents.
  **Read-only.** Use for a roadmap, not a fix-now pass.
- `motion-react` — Motion (motion.dev) API: presence, layout, gesture, springs.
  See `catalog-design.md` for the taste side.

## iOS / Swift

- `gstack-ios-qa` — live-device QA for SwiftUI over USB.
- `gstack-ios-fix` — autonomous iOS bug fixer.
- `gstack-ios-design-review` — visual audit on real hardware.
- `gstack-ios-sync` / `gstack-ios-clean` — debug-bridge lifecycle.
- `vision-framework` — OCR, barcode, face detection, segmentation, Core ML
  inference on iOS. Use for any camera/Vision feature.

## Engineering practice (plugin bundle)

- `engineering:architecture` — write or evaluate an ADR; choosing between
  technologies with trade-offs recorded.
- `engineering:system-design`, `engineering:code-review`, `engineering:debug`,
  `engineering:testing-strategy`, `engineering:tech-debt`,
  `engineering:deploy-checklist`, `engineering:incident-response`,
  `engineering:documentation`, `engineering:standup`.
- Prefer the gstack equivalent when both apply — gstack is wired to Joseph's
  workflow; the plugin bundle is generic.

## Data

- `data:explore-data`, `data:analyze`, `data:statistical-analysis`,
  `data:validate-data`, `data:data-context-extractor` — understand and check a
  dataset before charting it.
- `data:write-query` / `data:sql-queries` — SQL authoring.
- `data:create-viz` / `data:data-visualization` / `data:build-dashboard` — but
  **read `dataviz` first**; it owns the visual system (palette, marks, legends).
- `bklit-ui` — actual chart components for a shadcn project. See `shadcn-ui-kits`.

## Database / backend

- `supabase:supabase` — anything Supabase: auth, RLS, edge functions, realtime.
- `supabase:supabase-postgres-best-practices` — **load before** writing or
  changing schema, migrations, RLS, indexes, triggers, or diagnosing slow queries.
  Applies to Postgres anywhere, not just Supabase.

## Platform / infra

- `claude-api` — Claude/Anthropic model ids, pricing, tool use, caching. **Never
  answer LLM questions from memory.** Skip only if another provider is named.
- `anthropic-skills:mcp-builder` — build an MCP server.
- `run` — launch and drive the project's app to see a change actually working.
- `init` — create a CLAUDE.md for a codebase.
- `security-review`, `review`, `simplify` — built-ins; `simplify` is quality-only
  and does **not** hunt bugs.
