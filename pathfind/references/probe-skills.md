# Probe: skills

**Question:** does an agent skill already do this, installed or installable?

This is the surface people forget, because package search cannot see it. When the
task is "extend what an agent can do", the capability may exist as a skill and no
amount of npm searching will surface it. AXE-09 ranks agent skill registries with
the MCP registries for exactly this reason.

## Installed first

```bash
ls ~/.claude/skills/ ~/.codex/skills/ 2>/dev/null
```

The flat index of everything already present, with one-line descriptions:

```
~/.claude/skills/orchestrate/references/routing-table.md
```

Grep that before anything else. The domain catalogs beside it carry the *why*;
the routing table carries the *what exists*. A hit here costs nothing to adopt —
no install, no gate, no new trust decision — which makes it strictly better than
an equally good external candidate.

Also check the host's own plugin marketplace and any bundled plugin skills. On
this machine gstack alone contributes ~55, and they are easy to forget because
they are namespaced `/gstack-*`.

## Then installable

```bash
npx skills find "<query>"
```

Leaderboard: <https://skills.sh/>. The `find-skills` skill automates this surface
and is the right thing to invoke rather than reimplementing the search.

## What makes a candidate credible

Install count, source reputation (official orgs over unknown authors), and
upstream repository health. A search result is recall, not trust — it never
authorizes installation on its own. Anything you would actually install goes
through AXE-14.

## Reporting

Name the specific skill and the one line that makes it a fit. If several skills
are close, say which is closest and why the others lose — "close" is how a
general skill gets picked over the specific one built for the job.

State plainly when nothing covers the task. Concluding "no skill exists" *after
searching this surface* is a real finding; concluding it without searching is the
failure the probe exists to prevent.
