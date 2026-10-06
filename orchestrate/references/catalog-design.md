# Catalog — design, motion, UI

**The standing rule:** before writing any user-facing interface, pick a design
skill. Hand-rolled CSS is the fallback, never the default.

## Pick the direction first

- `taste-skill` — anti-slop default for a new interface. Infers direction from the
  brief; audit-first on redesigns. **Start here** unless a more specific one fits.
- `minimalist-skill` — clean editorial: warm monochrome, typographic contrast, no
  gradients or heavy shadows. **The right call for long-form reading surfaces**
  (Liaozhai / Metamorphoses reading aid).
- `soft-skill` — high-end agency look: premium fonts, considered shadows, card
  structure, spring animation. For "make it feel expensive".
- `industrial-brutalist-ui` — Swiss typography × military terminal. Rigid grids,
  extreme type contrast. For data-heavy dashboards and editorial sites that should
  read as declassified blueprints.
- `gpt-taste` — GSAP-heavy editorial motion: AIDA structure, ScrollTrigger pinning
  and scrubbing, bento grids, wide typography.
- `apple-design` — Apple's interface and motion philosophy for the web: gesture
  physics, springs, interruptible transitions, materials, optical typography.
- `design-taste-frontend-v1` — legacy v1 behaviour. Only for backward compatibility.
- `frontend-design:frontend-design` — **superseded by `impeccable`.** Flagged to
  Joseph, not disabled. Do not route here by default.

## Fix what already exists

- `redesign-skill` — upgrade an existing site to premium without breaking
  function. Audits for generic AI patterns first. Works with any CSS framework.
- `impeccable` — 23 design commands (`/polish`, `/critique`, `/audit`, `/distill`,
  `/harden`, …) **plus a 60-rule deterministic detector** with no LLM:
  `npx impeccable detect <path|url>`. Run `/impeccable init` once per project.
  **This is the measurable one — use it to verify, not just to advise.**
- `gstack-design-review` — designer's-eye QA that finds and *fixes* spacing,
  hierarchy, AI-slop patterns, slow interactions.
- `design:design-critique`, `design:accessibility-review`, `design:design-system`,
  `design:design-handoff`, `design:ux-copy` — generic design-practice bundle.

## Motion

**Taste vs mechanics — route to both, they are different roles.**

- `animate` — build an animation from scratch, deciding in the order that matters:
  should it animate at all → purpose → tool → properties → curve → interruption →
  exit. **Writes the implementation.**
- `emil-design-eng` — Emil Kowalski's philosophy on polish, component design, and
  the invisible details. The *why* behind a motion choice.
- `motion-react` — the *how* for React: `AnimatePresence`, `layoutId`, variants,
  gestures, and the layout-distortion gotchas. Includes the Motion-vs-GSAP split.
- `find-animation-opportunities` — read-only: where should this animate, and
  where should it explicitly not.
- `review-animations` — critique existing motion in a diff.
- `improve-animations` — read-only whole-codebase motion audit → plans.
- `animation-vocabulary` — reverse lookup: "the bouncy thing when a popover opens"
  → the actual term. Use to name an effect, not to build one.

## Components and kits

- `shadcn-ui-kits` — Kokonut UI + Bklit UI registries. **Carries the adoption
  decision**: both need Tailwind v4 + shadcn, so for a bespoke-CSS project the
  answer is usually "read the local clone and reimplement". Start here before
  suggesting either kit.
- `bklit-ui` — official Bklit skill: charts, theming, animation, `useChart`.
- `pick-ui-library` — choosing a component library at all.
- `prototype` — quick interactive prototype.

## Images and brand

- `imagegen-frontend-web` — premium website design references. **One horizontal
  image per section** — an 8-section page produces 8 images, never a compressed board.
- `imagegen-frontend-mobile` — app-native mobile screens in phone mockups.
- `image-to-code-skill` — generate the design image first, analyse it, then build
  to match. For visually important pages.
- `brandkit` — brand-guideline boards, logo systems, identity decks.
- `stitch-design-taste` — DESIGN.md generation for Google Stitch.
- `anthropic-skills:canvas-design`, `anthropic-skills:algorithmic-art` — canvas
  and generative visual work.
- `artifact-design` / `artifact-diagramming` / `artifact-capabilities` — required
  reading before publishing an Artifact; `artifact-capabilities` before any
  `window.claude.*` runtime code.
- `dataviz` — **read before writing the first line of chart code**, in any medium.
  Owns palette, mark specs, legends, light/dark consistency.

## Design workflow (gstack)

- `gstack-design-consultation` — research the landscape, propose a full system
  (aesthetic, type, colour, layout, spacing, motion) with font/colour previews.
- `gstack-design-shotgun` — generate multiple variants, compare on a board,
  collect structured feedback.
- `gstack-design-html` — production-quality HTML/CSS finalisation.

## Routing shorthand

*impeccable judges the pixels · taste/minimalist/soft choose the direction ·
animate + motion-react produce the motion · gstack runs the sprint · dataviz owns
anything with an axis.*
