# Routing table — flat index of everything installed

Grep this file. Domain catalogs carry the *why*; this carries the *what exists*.

Counts: 127 SKILL.md on disk · 113 bundled plugin skills · 15 built-ins.

## Personal / installed (non-gstack)

- `access` — Manage Discord channel access — approve pairings, edit allowlists, set DM/group policy. Use when the user asks
- `agent-development` — This skill should be used when the user asks to "create an agent", "add an agent", "write a subagent", "agent 
- `animate` — Build an animation from scratch, making the decisions in the order that determines whether it feels right — sh
- `animation-vocabulary` — Reverse-lookup glossary that turns a vague description of a web animation or motion effect into its exact term
- `apple-design` — Apple's approach to interface design and fluid, physical motion, translated for the web. Use when building or 
- `avoid-ai-writing` — Audit, rewrite, or compose content against AI writing patterns ("AI-isms"). Use this skill when asked to "remo
- `bklit-ui` — > Bklit UI charts and data visualization for any project using the @bklit shadcn registry. Install, compose, t
- `brandkit` — Premium brand-kit image generation skill for creating high-end brand-guidelines boards, logo systems, identity
- `build-mcp-app` — This skill should be used when the user wants to build an "MCP app", add "interactive UI" or "widgets" to an M
- `build-mcp-server` — This skill should be used when the user asks to "build an MCP server", "create an MCP", "make an MCP integrati
- `build-mcpb` — This skill should be used when the user wants to "package an MCP server", "bundle an MCP", "make an MCPB", "sh
- `cardputer-buddy` — Iterate on the Cardputer-Adv MicroPython app bundle (Claude Buddy, Snake, Hello) after the device is already p
- `claude-automation-recommender` — Analyze a codebase and recommend Claude Code automations (hooks, subagents, skills, plugins, MCP servers). Use
- `claude-md-improver` — Audit and improve CLAUDE.md files in repositories. Use when user asks to check, audit, update, improve, or fix
- `claude-security` — "The Claude Security menu — pick a job: scan the codebase (the whole repository or a scoped part of it), scan 
- `codex-cli-runtime` — Internal helper contract for calling the codex-companion runtime from Claude Code
- `codex-result-handling` — Internal guidance for presenting Codex helper output back to the user
- `command-development` — This skill should be used when the user asks to "create a slash command", "add a command", "write a custom com
- `configure` — Set up the Discord channel — save the bot token and review access policy. Use when the user pastes a Discord b
- `design-taste-frontend` — Anti-slop frontend skill for landing pages, portfolios, and redesigns. The agent reads the brief, infers the r
- `design-taste-frontend-v1` — The original v1 taste-skill, preserved for projects depending on its exact behavior. The current default is `d
- `emil-design-eng` — This skill encodes Emil Kowalski's philosophy on UI polish, component design, animation decisions, and the inv
- `example-command` — An example user-invoked skill that demonstrates frontmatter options and the skills/<name>/SKILL.md layout
- `example-skill` — This skill should be used when the user asks to "demonstrate skills", "show skill format", "create a skill tem
- `find-animation-opportunities` — Search a codebase or UI for places that don't animate but should, and reject everything that shouldn't. Read-o
- `find-skills` — Helps users discover and install agent skills when they ask questions like "how do I do X", "find a skill for 
- `frontend-design` — Guidance for distinctive, intentional visual design when building new UI or reshaping an existing one. Helps w
- `full-output-enforcement` — Overrides default LLM truncation behavior. Enforces complete code generation, bans placeholder patterns, and h
- `gpt-5-4-prompting` — Internal guidance for composing Codex and GPT-5.4 prompts for coding, review, diagnosis, and research tasks in
- `gpt-taste` — Elite UX/UI & Advanced GSAP Motion Engineer. Enforces Python-driven true randomization for layout variance, st
- `hackernews-frontpage` — Scrape the Hacker News front page (titles, points, comment counts).
- `high-end-visual-design` — Teaches the AI to design like a high-end agency. Defines the exact fonts, spacing, shadows, card structures, a
- `hook-development` — This skill should be used when the user asks to "create a hook", "add a PreToolUse/PostToolUse/Stop hook", "va
- `image-to-code` — Elite website image-to-code skill for Codex. For visually important web tasks, it must first generate the desi
- `imagegen-frontend-mobile` — Elite mobile app image-generation skill for creating premium, app-native screen concepts and flows. Designed f
- `imagegen-frontend-web` — Elite frontend image-direction skill for generating premium, conversion-aware website design references. CRITI
- `impeccable` — Use when the user wants to design, redesign, shape, critique, audit, polish, clarify, distill, harden, optimiz
- `improve-animations` — Survey a codebase's animation and motion code as a senior motion advisor, then produce a prioritized audit and
- `improve-react` — Survey a whole React codebase as a senior React engineer, using React Doctor's scan as evidence, then produce 
- `industrial-brutalist-ui` — Raw mechanical interfaces fusing Swiss typographic print with military terminal aesthetics. Rigid grids, extre
- `learn-from-video` — Learn a new technique from a video (YouTube, Instagram, TikTok, conference talk, screencast) and turn it into 
- `m5-onboard` — End-to-end onboarding for a freshly-plugged-in M5Stack ESP32 device (Cardputer, Cardputer-Adv, Core, CoreS3, S
- `math-olympiad` — "Solve competition math problems (IMO, Putnam, USAMO, AIME) with adversarial verification that catches the err
- `mcp-integration` — This skill should be used when the user asks to "add MCP server", "integrate MCP", "configure MCP in plugin", 
- `minimalist-ui` — Clean editorial-style interfaces. Warm monochrome palette, typographic contrast, flat bento grids, muted paste
- `motion-react` — Animate React interfaces with Motion (motion.dev, formerly Framer Motion) — enter/exit transitions, shared-ele
- `notebooklm` — Complete API for Google NotebookLM - full programmatic access including features not in the web UI. Create not
- `pick-ui-library` — Pick the right library for a given frontend task from a curated, opinionated list — numbers, OTP inputs, chart
- `playground` — Creates interactive HTML playgrounds — self-contained single-file explorers that let users configure something
- `plugin-settings` — This skill should be used when the user asks about "plugin settings", "store plugin configuration", "user-conf
- `plugin-structure` — This skill should be used when the user asks to "create a plugin", "scaffold a plugin", "understand plugin str
- `project-artifact` — Generate and publish a project status artifact — an opinionated, tabbed status page for a project too big for 
- `prototype` — Build multiple genuinely different versions of a UI piece you describe, rendered behind a visual picker so you
- `react-doctor` — Use when finishing a feature, fixing a bug, before committing React code, or when the user types `/doctor`, as
- `receipts` — Generate a personal Claude Code usage & impact report ("receipts") from this machine's local session transcrip
- `redesign-existing-projects` — Upgrades existing websites and apps to premium quality. Audits current design, identifies generic AI patterns,
- `review-animations` — Reviews animation and motion code against a high craft bar derived from Emil Kowalski's design engineering phi
- `session-report` — Generate an explorable HTML report of Claude Code session usage (tokens, cache, subagents, skills, expensive p
- `shadcn-ui-kits` — Add premium pre-built React components and charts to a project using the Kokonut UI and Bklit UI shadcn regist
- `skill-creator` — Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to c
- `skill-development` — This skill should be used when the user wants to "create a skill", "add a skill to plugin", "write a new skill
- `social-slideshow-research` — Extract itinerary/list content from TikTok-style slideshow posts via browser/computer control, and turn creato
- `stitch-design-taste` — Semantic Design System Skill for Google Stitch. Generates agent-friendly DESIGN.md files that enforce premium,
- `supabase` — "Use when doing ANY task involving Supabase. Triggers: Supabase products (Database, Auth, Edge Functions, Real
- `supabase-postgres-best-practices` — Postgres performance optimization and best practices from Supabase. Use this skill when writing, reviewing, or
- `vision-framework` — "Implement computer vision features including text recognition (OCR), face detection, barcode scanning, image 
- `watch` — Watch a video from YouTube, Instagram, X/Twitter, Vimeo, TikTok or any of ~1800 yt-dlp sites (or a local path)
- `writecheck` — Diagnose and revise Joseph's draft prose against his target register (Cronon, Homer, Ovid). Use when asked to 
- `writing-hookify-rules` — This skill should be used when the user asks to "create a hookify rule", "write a hook rule", "configure hooki

## gstack suite (58)

- `gstack`
- `gstack-autoplan`
- `gstack-benchmark`
- `gstack-benchmark-models`
- `gstack-browse`
- `gstack-canary`
- `gstack-careful`
- `gstack-codex`
- `gstack-context-restore`
- `gstack-context-save`
- `gstack-cso`
- `gstack-design-consultation`
- `gstack-design-html`
- `gstack-design-review`
- `gstack-design-shotgun`
- `gstack-devex-review`
- `gstack-diagram`
- `gstack-document-generate`
- `gstack-document-release`
- `gstack-freeze`
- `gstack-guard`
- `gstack-health`
- `gstack-investigate`
- `gstack-ios-clean`
- `gstack-ios-design-review`
- `gstack-ios-fix`
- `gstack-ios-qa`
- `gstack-ios-sync`
- `gstack-land-and-deploy`
- `gstack-landing-report`
- `gstack-learn`
- `gstack-make-pdf`
- `gstack-office-hours`
- `gstack-open-gstack-browser`
- `gstack-openclaw-ceo-review`
- `gstack-openclaw-investigate`
- `gstack-openclaw-office-hours`
- `gstack-openclaw-retro`
- `gstack-pair-agent`
- `gstack-plan-ceo-review`
- `gstack-plan-design-review`
- `gstack-plan-devex-review`
- `gstack-plan-eng-review`
- `gstack-plan-tune`
- `gstack-qa`
- `gstack-qa-only`
- `gstack-retro`
- `gstack-review`
- `gstack-scrape`
- `gstack-setup-browser-cookies`
- `gstack-setup-deploy`
- `gstack-setup-gbrain`
- `gstack-ship`
- `gstack-skillify`
- `gstack-spec`
- `gstack-sync-gbrain`
- `gstack-unfreeze`
- `gstack-upgrade`

## Personal commands

- `/axe`
- `/axe-edge`
- `/clean-ai-writing`
- `/compress`
- `/preserve`
- `/resume`

## Bundled plugin skills

**anthropic-skills** — `anthropic-skills:algorithmic-art` · `anthropic-skills:avoid-ai-writing` · `anthropic-skills:axe-edge` · `anthropic-skills:canvas-design` · `anthropic-skills:consolidate-memory` · `anthropic-skills:doc-coauthoring` · `anthropic-skills:docx` · `anthropic-skills:explain-usage` · `anthropic-skills:learn` · `anthropic-skills:mcp-builder` · `anthropic-skills:morning` · `anthropic-skills:pdf` · `anthropic-skills:pptx` · `anthropic-skills:schedule` · `anthropic-skills:setup-cowork` · `anthropic-skills:skill-creator` · `anthropic-skills:web-artifacts-builder` · `anthropic-skills:xlsx`

**engineering** — `engineering:architecture` · `engineering:code-review` · `engineering:debug` · `engineering:deploy-checklist` · `engineering:documentation` · `engineering:incident-response` · `engineering:standup` · `engineering:system-design` · `engineering:tech-debt` · `engineering:testing-strategy`

**finance** — `finance:audit-support` · `finance:close-management` · `finance:financial-statements` · `finance:journal-entry` · `finance:journal-entry-prep` · `finance:reconciliation` · `finance:sox-testing` · `finance:variance-analysis`

**data** — `data:analyze` · `data:build-dashboard` · `data:create-viz` · `data:data-context-extractor` · `data:data-visualization` · `data:explore-data` · `data:sql-queries` · `data:statistical-analysis` · `data:validate-data` · `data:write-query`

**design** — `design:accessibility-review` · `design:design-critique` · `design:design-handoff` · `design:design-system` · `design:research-synthesis` · `design:user-research` · `design:ux-copy`

**apollo** — `apollo:enrich-lead` · `apollo:prospect` · `apollo:sequence-load`

**small-business** — `small-business:business-pulse` · `small-business:call-list` · `small-business:canva-creator` · `small-business:cash-flow-snapshot` · `small-business:close-month` · `small-business:content-strategy` · `small-business:contract-review` · `small-business:crm-cleanup` · `small-business:crm-maintenance` · `small-business:customer-pulse` · `small-business:customer-pulse-check` · `small-business:friday-brief` · `small-business:handle-complaint` · `small-business:invoice-chase` · `small-business:job-post-builder` · `small-business:lead-triage` · `small-business:margin-analyzer` · `small-business:monday-brief` · `small-business:month-end-prep` · `small-business:month-heads-up` · `small-business:plan-payroll` · `small-business:price-check` · `small-business:quarterly-review` · `small-business:review-contract` · `small-business:run-campaign` · `small-business:sales-brief` · `small-business:smb-onboard` · `small-business:smb-router` · `small-business:tax-prep` · `small-business:tax-season-organizer` · `small-business:ticket-deflector`

**productivity** — `productivity:memory-management` · `productivity:start` · `productivity:task-management` · `productivity:update`

**pdf-viewer** — `pdf-viewer:annotate` · `pdf-viewer:fill-form` · `pdf-viewer:open` · `pdf-viewer:sign` · `pdf-viewer:view-pdf`

**hookify** — `hookify:configure` · `hookify:help` · `hookify:hookify` · `hookify:list` · `hookify:writing-rules`

**codex** — `codex:rescue` · `codex:setup` · `codex:codex-cli-runtime` · `codex:codex-result-handling` · `codex:gpt-5-4-prompting`

**supabase** — `supabase:supabase` · `supabase:supabase-postgres-best-practices`

**cowork-plugin-management** — `cowork-plugin-management:cowork-plugin-customizer` · `cowork-plugin-management:create-cowork-plugin`

**_archive** — `_archive:anecdote` · `_archive:past-projects` · `_archive:scan-brain`

## Built-in / harness

- `dataviz`
- `artifact-design`
- `artifact-diagramming`
- `artifact-capabilities`
- `update-config`
- `keybindings-help`
- `simplify`
- `fewer-permission-prompts`
- `loop`
- `schedule`
- `claude-api`
- `run`
- `init`
- `review`
- `security-review`
