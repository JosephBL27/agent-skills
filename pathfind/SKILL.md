---
name: pathfind
description: Decide what to build WITH before deciding what to build. Probes every capability surface — installed and installable skills, MCP servers and connectors, SDKs/libraries/CLIs, official docs, video and course material via /watch, and platform features like hooks and runtime choice — then returns one ordered pathway with a named primary, named complements, and an explicit list of what was searched and found nothing. Use this whenever a task involves an unfamiliar domain, a "what's the best way to do X" question, a build you're about to hand-roll, a stack or library or model choice, a request to research an implementation before writing it, or any phrasing like "figure out the right approach", "what should we use for", "research this properly", or "build this the right way". Also use before any foundational or hard-to-reverse build. Do NOT use for a task whose tools are already known and settled — pathfind is discovery, and running it on a known task is pure overhead.
argument-hint: "[what you're about to build or decide]"
allowed-tools: Bash, Read, Write, Edit, Grep, Glob, Skill, WebSearch, WebFetch, ToolSearch
user-invocable: true
---

# pathfind — what to build with

`orchestrate` splits work across skills you already have. **pathfind runs earlier
and asks a different question: what capability surfaces exist at all?**

The failure it prevents is the expensive one. Not "we picked the wrong library" —
that gets caught in review. It is **hand-rolling something that already exists**,
committing to a pathway before knowing the alternatives, and discovering the
right tool three days in. A wrong architecture chosen in haste costs more than
any research pass.

pathfind produces a **pathway**, not code. Execution is somebody else's job.

## Do not run this on everything

Discovery has a cost, and a discovery layer that always fires is a tax on every
task. If the tools are already known and settled — editing a file in a repo whose
stack you know, fixing a bug you've already root-caused, a one-line change — skip
it. Say so and move on.

The signal to run pathfind is **uncertainty about the surface**, not difficulty.
A hard task with obvious tools does not need it. An easy task in an unfamiliar
domain does.

## Step 1 — classify depth, then choose probes

Depth is already defined. Use **AXE-07's R0–R4** rather than inventing a scale:
`90 Meta/AXE_OS/brain/policies/AXE-07-Research-Depth-Classifier.md`. Classify
*before* probing, so the amount of research cannot be justified retroactively in
either direction.

| Depth | Probes to run |
|---|---|
| R0–R1 | none, or a single targeted probe. Name the tool and proceed. |
| R2 | skills + the one surface the domain lives on |
| R3 | all five probes; compare candidates properly |
| R4 | all five, plus threat model and a reversible prototype before committing |

State the R-level and the probe set out loud. That one line is what makes an
over- or under-scoped pass visible later.

## Step 2 — run the probes

Five surfaces, each with its own reference file. Read only the ones your depth
calls for.

| Probe | Surface | Reference |
|---|---|---|
| skills | installed skills, skills.sh, host marketplace | `references/probe-skills.md` |
| mcp | connected servers, registries, host connectors | `references/probe-mcp.md` |
| package | SDKs, libraries, CLIs, and their current docs | `references/probe-package.md` |
| education | official docs, changelogs, video via `/watch` | `references/probe-education.md` |
| platform | hooks, settings, runtime and language choice | `references/probe-platform.md` |

**AXE-09 owns the order of sources inside every probe** — local and installed
first, then official docs, repos, registries, releases, issues, security
intelligence; curated lists for recall only; social discussion as supporting
evidence. Do not restate that ordering here or in the probes; follow it.

Run independent probes in the same turn rather than in sequence. They do not
depend on each other, and serializing them is the main reason a discovery pass
feels slow enough to skip next time.

### Every probe reports in the same shape

Uniform output is what makes synthesis mechanical instead of a vibe:

```
PROBE <name>
  candidates   <name — one line on what it covers — evidence you actually saw>
  nothing for  <the part of the task this surface does NOT cover>
  cost         <install / auth / permission / context weight>
  gate         <clear | needs AXE-14 | needs Joseph>
```

**`nothing for` is not optional.** A probe that returns only hits is
indistinguishable from a probe that did not look hard, and silent gaps are how a
pathway ends up with a hole in the middle. If a surface genuinely offers nothing,
say "nothing for: all of it" — that is a real and useful result.

## Step 3 — synthesize one pathway

Pick **one primary** per job, plus at most two complements that cover a
*different* role — implement plus verify, not two implementers. Redundant
complements look thorough and mostly burn context.

Report as an ordered pathway:

```
PATHWAY
  1. <step>            via <tool>        because <reason>
  2. <step>            via <tool>        because <reason>
  verifier             <the mechanical check that proves it worked>
  rejected             <candidate — why it lost, in one line>
  not covered          <what no surface answered; how you'll handle it>
  gated                <anything needing AXE-14 or Joseph's decision>
```

The `because` column is the part worth writing carefully. It is what lets a wrong
choice be spotted later without re-running the whole pass, and it is the thing
that gets preserved to the brain.

`rejected` matters as much as the winner. "Evaluated X, chose native instead" is
a durable asset — it stops the next session re-running the same evaluation.

## Step 4 — hand off

pathfind does not execute. When the pathway is agreed:

- multi-unit work → `orchestrate` with the pathway as its routing input
- foundational, irreversible, auth/secrets/production → `/axe`
- a single obvious build → just build it, naming the pathway you followed

## The gates you must not walk through

**Discovery is autonomous. Acquisition is not.** AXE-14 governs anything you
would install or execute: canonical source and ownership, license, releases,
issues, install scripts, dependencies, permissions, vulnerabilities, a pinned
version, a rollback. Search results never authorize execution by themselves.
pathfind may *recommend* an install; it may not perform one on its own.

**Recall is not trust.** A high-ranking search result, a popular registry entry,
and a confident README are all recall. Gate on install count, source reputation,
and repository health before recommending anything.

**Two identical failures forbid a third.** If a probe comes back empty twice by
the same method, change the method — a different surface, a different query
shape, or an explicit "no surface covers this". That is AXE-38, and it applies to
searching exactly as it applies to retrying a build.

**Say "nothing found" out loud.** Falling back to general knowledge silently is
the specific failure this skill exists to prevent. If no surface covers a unit,
write `not covered` in the pathway and state that you are proceeding on general
knowledge. That sentence is a feature.

## Preserve what you learned

A discovery pass that is not recorded gets re-run. Per AXE-36, write the outcome
where the next session will find it:

- the decision and its `because` → the project note and auto-memory
- a package or skill that was adopted → `30 Resources/Agent Skills/<slug>/`
- a rejection worth keeping → the same place, marked as evaluated-and-declined

When a new finding supersedes an old one, update the old entry in place or mark
it stale with a pointer. Two conflicting strategies standing side by side is
worse than either alone.

## Precedence

pathfind routes and recommends; it does not authorize. It sits below the boot
files (Identity → AGENTS → Memory-Protocol → Codex → Operating Principles) and
below AXE_OS. If a pathway would breach a never-rule, an acquisition gate, or the
retry limit, stop and surface it rather than routing around it.
