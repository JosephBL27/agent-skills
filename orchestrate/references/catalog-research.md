# Catalog — research, learning, currency

**The premise:** your training data has a cutoff, the ecosystem does not. Any unit
that depends on current tooling routes through here *before* the build unit runs.

## Discovery and gating

- `axe-edge` — the default for non-trivial work. Inspect host capabilities →
  vendor/official sources → MCP registry → GitHub/package registries → compare ≥3
  pathways → complementary-tool pass. Keeps context compact, smoke-checks.
- `axe` — flagship. **Required** for R3/R4, foundational changes, irreversible or
  production operations, auth/secrets, regulated data, broad privilege changes.
  Loads broader evidence, verifies independently. Its gates govern.
- `find-skills` — `npx skills find <query>` across the open skill ecosystem. **Run
  before concluding a capability must be built.** Recall ≠ trust: gate on install
  count, source reputation, repo health.
- `anthropic-skills:learn` — structured learning of a new topic.
- `_archive:past-projects` — search Joseph's own prior art first. Cheapest source
  of a correct answer.

## Video and social

- `watch` — one specific video → frames + timestamped transcript. Local
  mlx-whisper, no API key. YouTube, Instagram, TikTok, X, Vimeo, ~1800 sites.
  **Always read the frames** — listicle videos render names on screen that the
  audio never says.
- `learn-from-video` — the full loop: watch → optional independent Gemini read →
  reconcile into a spec labelled `confirmed`/`single-source`/`conflict` → gate →
  hand to `skill-creator`. Use when the goal is durable capability, not one answer.
- `social-slideshow-research` — TikTok-style swipe/slideshow posts → verified
  itineraries and lists.

**Routing rule learned the hard way:** video is for *technique and taste*; vendor
docs and Context7 MCP are for *API surface*. A 72-minute "beginner to advanced"
Motion tutorial never once mentioned `AnimatePresence`, `layoutId`, or variants.

## Live documentation

- **Context7 MCP** — current library docs in context. Prefer over memory for any
  API question. (MCP, not a skill — added at user scope.)
- **Playwright MCP** — real browser: the agent opens the page and QA-tests it.
- `WebSearch` / `WebFetch` — vendor docs, changelogs, provenance checks.
- Provenance check before installing anything:
  ```bash
  curl -s https://api.github.com/repos/<owner>/<repo> | \
    python3 -c "import json,sys;d=json.load(sys.stdin);print(d['stargazers_count'], d['pushed_at'][:10], (d.get('license') or {}).get('spdx_id'))"
  ```
  Two same-named repos is not automatically a fork-squat — **measure** before
  calling provenance ambiguous.

## Research output

- `notebooklm` — full NotebookLM API: notebooks, sources, podcasts, artifacts.
- `design:research-synthesis`, `design:user-research` — synthesising findings.
- `anthropic-skills:explain-usage` — explain how something is used.
- `gstack-scrape` / `gstack-browse` — headless extraction at speed.
- **Browser routing:** headless QA/scrape/screenshot → `gstack-browse`; logged-in
  real-session work → the Chrome extension surface. **Never switch silently — say
  which one you used.**

## Acquisition gate (applies to everything found here)

Presumptively fine: first-party host integrations, official vendor
connectors/SDKs, mature official repos. Reject or escalate on: unexplained
privilege, prompts/code routed to third parties, unnecessary secret access,
unverifiable provenance, abandoned critical dependency, destructive defaults, or
install-time scripts on anything security-relevant. Sponsored content (`#ad`,
`#partner`) is a recommendation with a conflict of interest — weight it down and
say so.
