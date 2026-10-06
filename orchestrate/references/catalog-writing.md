# Catalog — writing, voice, documents

## Joseph's voice — the order matters

1. `_archive:anecdote` — **read the Anecdote Index before drafting anything in his
   voice.** Priority Spine, by-theme navigation, explicit Voice Rules ("lead with
   a concrete scene, not an abstract value"; "preserve the humour"; "do not
   flatten into 'leadership' or 'overcoming adversity' language").
2. `writecheck` — diagnose and revise a draft against his target register (Cronon,
   Homer, Ovid). Reports the specific sentences dragging each metric.
3. `avoid-ai-writing` / `clean-ai-writing` — strip AI tells. Modes: `detect`
   (flag only), `rewrite` (default), `edit` (in-place on a named file).

**The score comes from code, never from your impression:**
```bash
node -e 'const D=require(process.env.HOME+"/.agents/skills/avoid-ai-writing/detector/patterns.js");const r=D.analyzeText(require("fs").readFileSync(process.argv[1],"utf8"));console.log(r.score,r.label,r.issues.length)' FILE
node ~/.agents/skills/avoid-ai-writing/detector/validate.js before.md after.md
```
`validate.js` exits non-zero if a rewrite touched a code block, frontmatter,
blockquote, table cell, inline code, URL, path, or heading structure. **Run it
after every edit-mode pass.**

**Hard rule:** documented detector false-positive rates exceed 60% on non-native
English writers. Never present a flag or score as evidence of *who wrote*
something, and never let it feed a consequential judgement. Say this out loud when
reporting.

**Never inject** while removing AI-isms: fake first person, manufactured stakes,
forced contrarianism, performed candour, extra em dashes, staccato fragmentation.
Replacing one fingerprint with a louder one is a failure even at a clean score.

`avoid-ai-writing` removes tells; it is **not** a house style guide (Vale's job),
not `impeccable` (pixels), not gstack `design-*` (sprint gates).

## Documents

- `anthropic-skills:docx` / `xlsx` / `pptx` / `pdf` — real Office and PDF files.
- `anthropic-skills:doc-coauthoring` — drafting a document with the user.
- `gstack-make-pdf` — markdown → publication-quality PDF.
- `gstack-document-generate` — documentation from scratch for a module or project.
- `gstack-document-release` — post-ship doc update.
- `engineering:documentation` — generic engineering docs.

## PDFs (interactive)

- `pdf-viewer:open` / `view-pdf` — open for visual collaboration. **Not** for
  summarising or extracting text — use native `Read` for that.
- `pdf-viewer:annotate` · `fill-form` · `sign` — markup, form fill, signature
  placement.

## Presentation and publishing

- `anthropic-skills:web-artifacts-builder` — build a web Artifact.
- `artifact-design` — **required** before designing an Artifact page.
- Gamma MCP — AI presentations and docs. Note: it **cannot edit** an existing
  gamma; do not promise revisions.

## Business writing

- `small-business:contract-review` — NDA/MSA/vendor review, plain-English risk
  flags, DOCX redline out.
- `design:ux-copy` — interface copy, error states, empty states.
