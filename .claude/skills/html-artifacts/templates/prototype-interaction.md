# Prototype Interaction

**Source:** `.claude/examples/html-effectiveness/08-prototype-interaction.html`

## When

User wants to feel a UI interaction — drag-to-reorder, multi-step flow, modal sequence. Throwaway clickable mock that conveys the experience.

## Anatomy

- Header: eyebrow (project / context), h1 (interaction name), subtitle
- Frame strip — 3-5 screens linked left-to-right with arrows showing transition
- Inline interactive widget — the actual interaction at small scale
- `<section class="notes">` — "What you're feeling" — design intent / rationale per step
- `<section class="questions">` — Open questions for review

## Sections to Replace

1. `<title>` + h1: interaction name
2. Frame strip: replace `<rect>` placeholders with real UI screenshots-as-SVG or hand-drawn boxes
3. Interactive widget: implement the actual interaction. Keep it small — one component, not a whole app.
4. Notes: per-frame commentary on what the user should feel / why this beats alternative
5. Open questions: real decisions still up for debate

## Customization Knobs

- Swap the widget: drag-reorder, modal flow, accordion, command palette. Each will need its own JS.
- Add timing notes (`200ms ease-out`) next to transition arrows.
- Add before/after comparison row.

## Pitfalls

- If the interaction needs real data or backend, this template is the wrong tool — sketch it instead, or build a real prototype.
- Don't ship broken interactivity. Test every click, drag, key press.
- Resist scope creep — one interaction per file. Multiple interactions → multiple files.
- JS inline at bottom of body, no external libs.
