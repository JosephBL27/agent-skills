# agent-skills

Three skills I wrote that sit between my prompt and everything else installed on
my machine. They are plain Markdown in the open SKILL.md format, so any agent
host that reads that format can load them.

| Skill | What it does |
|---|---|
| [orchestrate](orchestrate/SKILL.md) | Splits a request into work units, gives each unit one deliverable and one test it can fail, and routes each unit to the one skill built for it. A unit is done when its test passes, not when a tool ran. |
| [pathfind](pathfind/SKILL.md) | Runs before anything is built by hand. Probes installed and installable skills, MCP servers, SDKs and libraries, official docs and video material, then returns one pathway: a named primary, named complements, and an explicit list of what it searched and found nothing for. |
| [axe-edge](axe-edge/SKILL.md) | A compact research-first pass for ordinary non-trivial work: look for what already exists, compare at least three credible pathways, pick one primary and at most two complements, smoke-check it. The full instruction is in [axe-edge/references/AXE_EDGE.md](axe-edge/references/AXE_EDGE.md). |

## How they fit together

```
prompt
  └─ orchestrate ── decompose ── one unit, one test
        │
        ├─ route: core list of 15 skills → 7 catalogs → pathfind
        │                                         └─ probes every surface, reports misses too
        ├─ delegate: each subagent gets only its own unit
        ├─ verify: the unit's test passes, or it is not done
        └─ report: every skill used, then 3 to 5 ranked next steps
```

Everything runs through my Obsidian vault. The routing catalog in
[orchestrate/references/catalog-brain.md](orchestrate/references/catalog-brain.md)
tells the agent to read the vault's boot notes before acting and to write what it
learns back to the right note, so a finding from one session is there for the
next one. orchestrate's routing table lists 148 skills and commands; most of them
are third-party, and these three are mine.

The detail I care most about is in pathfind: every probe has to report what it
searched and found nothing for, because a search that lists only hits looks the
same as a search that never looked.

## Install

Copy a skill folder into your agent's skills directory, for example:

```bash
cp -R orchestrate pathfind axe-edge ~/.claude/skills/
```

The catalogs name the skills on my machine. Edit
`orchestrate/references/routing-table.md` and the `catalog-*.md` files to match
yours.

Joseph Blumberg · josephblumberg325@gmail.com
