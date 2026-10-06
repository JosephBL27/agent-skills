# Probe: MCP servers and connectors

**Question:** is there already a live tool for this, or one worth connecting?

An MCP server that is already connected is the cheapest capability available —
authenticated, in-session, zero acquisition cost. Reaching for a browser or a
hand-rolled script while a connected server does the job is the single most
common waste this probe catches.

## Connected first

Deferred tools appear by name in system reminders but carry no schema until
fetched. Search them before assuming a capability is missing:

```
ToolSearch  query: "<keyword>"        max_results: 10
```

Keyword search matches the server-name substring, so one query returns a whole
toolkit. Batch everything you expect to need into a single call — one
comma-separated `select:` beats one round-trip per tool.

Note which servers are **connected but unauthenticated**. Those are not
capabilities yet; they are a request for Joseph to authorize, and that belongs in
the pathway's `gated` line rather than being quietly assumed.

## Then discoverable

```
mcp__mcp-registry__search_mcp_registry
mcp__mcp-registry__suggest_connectors
mcp__mcp-registry__list_connectors
```

Prefer vendor-official servers over community re-implementations. Vendor-official
paths are the first discovery surface for a reason: they track the upstream API,
and a community wrapper is one more thing that goes stale.

## Cost, honestly

MCP tool schemas are deferred by default — only the tool *name* sits in context,
so a connected server usually costs nothing until used. Do not report a token
cost for deferred tools, and do not recommend adding a server "for free" on that
basis either: every server is something to authenticate, maintain, and keep
current.

A server that requires OAuth in a non-interactive session is unavailable now, no
matter how good the fit. Say so rather than planning around a tool that cannot run.

## Reporting

Name the server and the specific tools that cover the job. Distinguish three
states clearly, because they have very different costs: **connected and ready**,
**connected but needs auth**, **not installed**.
