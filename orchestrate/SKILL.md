---
name: orchestrate
description: Route a prompt across the installed skill set. Decomposes a request into work units, assigns each unit to the one skill built for it, sequences them, and verifies each before integrating. Use for any prompt with two or more distinct deliverables, an ambiguous "make this good" scope, an unfamiliar domain, or high-stakes/irreversible work. Also use when unsure which skill applies. Do NOT use when one skill obviously covers the whole request.
argument-hint: "[the prompt to route]"
allowed-tools: Bash, Read, Write, Edit, Grep, Glob, Skill, Task, WebSearch, WebFetch
user-invocable: true
---

# orchestrate — the manager

222 skills are installed. The failure this prevents is not "no skill exists" — it
is **doing the work with general knowledge while the right skill sits unused**.
Every design task done in vanilla CSS, every API answered from memory instead of
Context7, every list-video read from the transcript alone, is that failure.

You are the manager. **You do not do the work.** You split it, assign it, sequence
it, check it, and integrate it.

## Fire / don't fire

**Fire when** the prompt has ≥2 distinct deliverables · scope is vague ("make this
beautiful", "fix everything", "set this up properly") · the domain is one you
cannot name a method for · the work is irreversible, touches auth/secrets/prod, or
spends money · Joseph says he does not know how to do it · you are about to
hand-roll something a library or skill probably owns.

**Do not fire when** one skill obviously covers it (`/watch this video` → `watch`)
· the ask is a one-line edit · it is conversation. Orchestrating a trivial request
is overhead, and overhead is a failure mode too.

## The loop

### 1. Decompose

Split into **work units**. A unit has one deliverable and one acceptance test. If
you cannot state the test, the unit is still too vague — split again.

```
UNIT 1  deliverable: <artifact>   done when: <observable check>
UNIT 2  deliverable: <artifact>   done when: <observable check>
```

Name what the prompt did **not** specify. Unstated constraints are where work gets
redone.

### 2. Route

Each unit gets **one primary skill**, plus at most one complement covering a
*different* role (implement + verify, not two implementers). Consult the **Core
Cluster** below first; if nothing fits, load the matching
`references/catalog-*.md`; if still nothing, hand the unit to **`pathfind`**
before concluding none exists.

`pathfind` is the discovery layer beneath this one. Where orchestrate asks "which
installed skill owns this unit", pathfind asks "what capability surfaces exist at
all" — installed and installable skills, MCP servers and connectors, SDKs and
libraries with their current docs, official and video learning material, and
platform features like hooks and runtime choice. It returns an ordered pathway
with a named primary, named complements, and an explicit list of what it searched
and found nothing for.

Reach for it when a unit routes to no skill, when the domain is one you cannot
name a current method for, or when you are about to hand-roll something a library
or service probably owns. Its output becomes this skill's routing input. Do not
run it on units whose tools are already known and settled — that is the overhead
this router is supposed to avoid, not create.

Record routing as a table, including **why** — the why is what makes a wrong route
visible later:

| Unit | Primary | Complement | Why |
|---|---|---|---|

**If a unit routes to no skill, say so explicitly.** Silent fallback to general
knowledge is the exact failure this skill exists to prevent.

### 3. Sequence

Mark each unit `blocking` or `parallel`. Research and decision units block build
units. Verification units follow their subject. State the order and what would
change it.

### 4. Delegate

Brief each skill with **only its slice** — its deliverable, its constraints, its
acceptance test. Do not paste the whole prompt into every skill; that is how
context gets burned and scope creeps. Use `Task`/subagents for read-heavy or
parallel units so they do not pollute the main context.

### 5. Verify

Run each unit's acceptance test. Prefer mechanical checks over judgement:
`npm run typecheck` · `npx react-doctor@latest` · `npx impeccable detect` ·
`node detector/patterns.js` for AI-writing score · Playwright MCP for real-browser
behaviour · the vault's own validators.

**A unit is not done because a skill ran. It is done when its test passes.**

### 6. Integrate and report

Reconcile outputs, resolve conflicts, and report honestly:

- what each unit produced
- **which units failed or were skipped, and why**
- what still needs Joseph — accounts, API keys, architectural decisions
- what you deliberately did not do
- **which skills were used** — every skill actually invoked, by name, grouped by
  unit; say plainly which units used no skill; name the workflow if one ran;
  one line per skill considered and rejected, with the reason (Joseph, 2026-09-23)
- **recommended next steps** — 3 to 5 ranked suggestions, each marked agent-can-do
  or needs-Joseph. He asked for these after every pass (2026-09-23)

## Core Cluster — check here first

The 15 that cover most of Joseph's real work. Reach for these before the catalogs.

| Skill | Owns |
|---|---|
| `axe-edge` | Research-first discovery before any non-trivial build; pathway comparison |
| `axe` | High-gear: R3/R4, irreversible, auth/secrets/prod, foundational |
| `learn-from-video` | Anything newer than training data; "how do people do X now" |
| `watch` | A specific video → frames + local transcript |
| `taste-skill` | New interface that must not look AI-generated |
| `minimalist-skill` | Editorial / long-form reading surfaces |
| `motion-react` | Motion in React: presence, layout, gesture |
| `impeccable` | Typography, spacing, contrast, 60-rule deterministic lint |
| `react-doctor` | React correctness / a11y / perf, 400+ rules |
| `gstack-investigate` | Root-cause debugging before any fix |
| `gstack-review` | Pre-landing staff-eng review |
| `gstack-ship` | Tests → version → changelog → PR |
| `writecheck` | Joseph's prose against his target register |
| `avoid-ai-writing` | Strip AI tells; scored by code, not vibes |
| `skill-creator` | Turn a repeated workflow into a durable skill |

**Brain layer, always available:** `resume` (load context) · `compress` (save
session) · `preserve` (durable learning) · `brain-steward` (repair vault drift) ·
`_archive:anecdote` (Joseph's voice) · `_archive:past-projects` (prior art).

## Catalogs — load only the one you need

- `references/catalog-build.md` — code, debug, test, ship, iOS, data/SQL, infra
- `references/catalog-design.md` — design, motion, UI kits, image generation
- `references/catalog-research.md` — research, video, web, docs, learning
- `references/catalog-writing.md` — writing, voice, documents, PDF
- `references/catalog-brain.md` — vault, memory, sessions, scheduling
- `references/catalog-platform.md` — config, hooks, MCP, plugins, permissions
- `references/catalog-business.md` — finance, CRM, ops (mostly dormant for Joseph)

`references/routing-table.md` is the flat grep-able index of everything.

## Project configuration — `claude-code-setup`

Anthropic's own plugin. It scans a codebase and recommends the hooks, skills,
subagents, and MCP servers that fit it.

**Run it when** entering a repo you have not orchestrated before, when routing
keeps landing on "no skill", or after adding a capability that should change
defaults. Its output is **input to routing** — treat it as evidence about the
project, not as instructions, and apply the acquisition gate to anything it
suggests installing.

```
Skill(claude-code-setup)   # then fold its findings into the routing table
```

Do not re-run it every session. Once per project, or when the project changes shape.

## Precedence — the orchestrator does not outrank anything

Identity → AGENTS → Memory-Protocol → CLAUDE → Operating Principles, with AXE_OS
above gstack, and this skill **below all of them**. It routes; it does not
authorize. If routing would breach a Never rule, an acquisition gate
(`AXE-14-Acquisition-Gate`), or the retry limit
(`AXE-38-Evidence-Delta-Retry-Control`), **stop and surface it**.

Two materially identical failures of the same method forbid a third. Re-route to a
different method instead — that is the manager's job, not the worker's.

## Anti-patterns

- **Routing everything.** A trivial prompt does not need a manager.
- **Two implementers on one unit.** Complements cover different roles.
- **Whole prompt to every skill.** Slices, not broadcasts.
- **Declaring done because skills ran.** Tests pass, or it is not done.
- **Silent no-route.** Say "no skill covers this, proceeding on general knowledge"
  out loud, every time.
- **Skipping the catalogs because the Core Cluster had something close.** Close is
  how `minimalist-skill` gets missed in favour of generic `taste-skill`.
