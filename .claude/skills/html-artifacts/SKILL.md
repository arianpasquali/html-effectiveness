---
name: html-artifact
description: Use when user asks for a slide deck, status report, weekly update, implementation plan, feature/concept explainer, clickable prototype, or annotated PR review — produces a single self-contained .html file from a curated template instead of markdown.
---

# HTML Artifact

## Overview

Single-file `.html` deliverables beat wall-of-markdown when the output benefits from spatial layout, color, navigation, or interaction. Repo ships seven design-aligned templates under `templates/` at repo root (see https://github.com/arianpasquali/html-effectiveness). This skill routes a request to the right template, then copy-and-customize.

Core principle: **copy template, replace content, preserve design tokens**. Do not regenerate CSS from scratch — these templates share an ivory/slate/clay palette and serif/sans/mono stack that is the look. Tweaks OK, rewrites no.

## When to Use

Use when user asks for any of:

| Intent / phrase | Template | Reference |
|---|---|---|
| "slide deck", "presentation", "slides for meeting" | `09-slide-deck.html` | `templates/slide-deck.md` |
| "status report", "weekly update", "what shipped" | `11-status-report.html` | `templates/status-report.md` |
| "implementation plan", "how we'll build X", "hand-off plan" | `16-implementation-plan.html` | `templates/implementation-plan.md` |
| "explain how X works in this repo", "feature explainer" | `14-research-feature-explainer.html` | `templates/feature-explainer.md` |
| "explain concept X", "teach me X with diagrams" | `15-research-concept-explainer.html` | `templates/concept-explainer.md` |
| "clickable prototype", "mock the interaction", "show the flow" | `08-prototype-interaction.html` | `templates/prototype-interaction.md` |
| "PR review writeup", "annotated review of branch/PR" | `03-code-review-pr.html` | `templates/code-review-pr.md` |

**Do NOT use when:**
- User wants real markdown (e.g. PR body for GitHub, Linear ticket, commit message)
- Output must be machine-parsed
- Project has its own templating system (check first)
- Request is for a website / app — those are not artifacts

## Workflow

1. **Identify intent** — match to row in table above. Ambiguous? Ask user which template.
2. **Read the matching template reference** in `templates/<name>.md` — it lists sections, customization knobs, and pitfalls.
3. **Copy source `.html`** verbatim to an output path. Default: `outputs/html/<slug>.html` at repo root. Ask user if they want different path.
4. **Replace content blocks** in copied file:
   - `<title>` and `<h1>` first
   - Eyebrow / dateline / subtitle
   - Each `<section>` body in order
   - Keep class names, structure, CSS untouched unless tweaking design intentionally
5. **Preserve design tokens** (`:root` block). Adding new tokens OK. Removing/replacing palette is NOT this skill.
6. **Verify**: open file in browser, check no broken interactivity (slide-deck keys, prototype clicks).
7. **Report** absolute output path so user can open it.

## Customization Boundaries

| OK to change | Avoid |
|---|---|
| Text content, headings, lists, table rows | Color palette in `:root` |
| Section count (add/remove `<section>`) | Serif/sans/mono font stack |
| Add new CSS classes for new content | Renaming existing class names that scripts target |
| Tweak spacing, font sizes per content density | Replacing layout primitives wholesale |
| Add new inline SVG diagrams matching token colors | Importing external CSS/JS frameworks |

## Common Mistakes

- **Rebuilding the CSS** — wastes tokens, breaks visual consistency across artifacts. Copy the file.
- **Inlining markdown content unchanged** — defeats the point. If output is "paragraphs in a column", use markdown not HTML.
- **Breaking the JS in slide-deck or prototype** — these have arrow-key / click handlers. Test after edits.
- **Forgetting `<title>`** — first thing reviewers see in browser tab.
- **External assets** — templates are self-contained. Inline SVG, no `<img src=>` to external URLs, no CDN links.

## File Paths

- Source templates: `templates/<NN>-<name>.html` (in html-effectiveness repo)
- Per-template references: `.claude/skills/html-artifacts/templates/<name>.md`
- Default output: `outputs/html/<slug>.html` (create dir if missing)

## Reference Index

- [Slide deck](templates/slide-deck.md)
- [Status report](templates/status-report.md)
- [Implementation plan](templates/implementation-plan.md)
- [Feature explainer](templates/feature-explainer.md)
- [Concept explainer](templates/concept-explainer.md)
- [Prototype interaction](templates/prototype-interaction.md)
- [Code review PR](templates/code-review-pr.md)
