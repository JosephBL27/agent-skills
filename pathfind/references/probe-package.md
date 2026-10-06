# Probe: SDKs, libraries, CLIs

**Question:** has someone already solved this, and is their solution current?

Two distinct failures live here. The obvious one is hand-rolling a solved
problem. The subtler and more common one is **answering from memory** — writing
against an API as you remember it rather than as it currently is. Library APIs
move; training data does not.

## Check current docs, not recall

```
mcp__context7__resolve-library-id      then     mcp__context7__query-docs
```

Use it even for libraries you know well — React, Next.js, Tailwind, SwiftUI,
Vision. Especially for those, because familiarity is exactly what stops you
checking. Prefer this over general web search for anything API-shaped: syntax,
configuration, migration between versions, CLI usage, setup.

Skip it when the question is not library-shaped — refactoring, business logic,
debugging your own code, general design.

## Then evaluate the candidates

License, maintenance, open issues, release cadence, target platform and minimum
version, dependency weight, and whether the API surface you need is actually
stable. For a consequential dependency, compare at least the top alternatives
before committing rather than adopting the first plausible hit.

Prior art in Joseph's own repos and vault counts as a source and comes first.
"We already evaluated this" is the cheapest possible answer.

## The local-vendoring rule

On this machine, dependencies are **vendored locally** — never remote-resolved
during an unattended build, because a scheduled job that reaches the network at
build time fails in ways nobody is awake to see. Any recommendation to add a
dependency must say where it will be vendored and at what pinned version or
commit.

## Choosing native instead is a real outcome

"Evaluated X, chose the platform API instead" is a legitimate and frequently
correct result — and it is a durable asset, because it stops the next session
re-running the same comparison. Record it with the reasoning, not just the
verdict.

## Reporting

Name the package, the version you would pin, the license, and the one line that
makes it a fit. Name what you compared it against and why that lost. Flag
anything requiring an install for the AXE-14 gate — discovery is autonomous,
adding a dependency is not.
