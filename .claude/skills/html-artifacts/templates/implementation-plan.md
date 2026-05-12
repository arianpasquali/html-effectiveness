# Implementation Plan

**Source:** `.claude/examples/html-effectiveness/16-implementation-plan.html`

## When

User wants a hand-off plan for a feature: milestones, data flow, mockups, the risky code, risks. Output an engineer can read and start building.

## Anatomy

- Header: eyebrow, h1 (feature name), prompt-box (the original ask)
- Section: Milestones / timeline — bullets with target dates
- Section: Data flow — inline SVG diagram (boxes + arrows)
- Section: UI mockups — inline mini wireframes (rounded rects + labels)
- Section: Risky code — annotated code block with `<pre>` showing the tricky function
- Section: Risk table — risk | likelihood | impact | mitigation columns
- Section: Open questions / decisions deferred

## Sections to Replace

1. `<title>` + h1: feature name
2. `.prompt-box`: paste / paraphrase the user's original ask
3. Timeline: dates → bullets. Keep dates absolute, not relative.
4. Data-flow SVG: redraw boxes for the actual services / modules. Use `--oat` for stores, `--clay` for entry point, `--olive` for external systems.
5. Code block: actual function the engineer will write or modify. Annotate inline with margin notes.
6. Risk table rows: real risks ranked.

## Customization Knobs

- Add API contract section if the plan crosses a service boundary.
- Add migration / rollout phasing section if behind a flag.
- Drop UI mockups if backend-only feature.

## Pitfalls

- Don't fabricate dates — ask user or mark `TBD`.
- Risks need mitigations, not just descriptions. If you can't write a mitigation, surface it as an open question.
- Data flow should be the ACTUAL flow including failure paths, not the happy path only.
- Code block: should be small and pointed — the one function that will be ugly, not the whole feature pasted.
