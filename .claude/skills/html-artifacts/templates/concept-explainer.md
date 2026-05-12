# Concept Explainer (general)

**Source:** `.claude/examples/html-effectiveness/15-research-concept-explainer.html`

## When

Teaching a general CS / ML / systems concept with an interactive diagram. NOT repo-specific — for that use `feature-explainer.md`.

## Anatomy

- Header: h1 + one-line punchline
- Section: "The trick" — the core idea explained with an interactive SVG (e.g. ring, graph, plot)
- Interactive controls — buttons/sliders that mutate the diagram via JS
- Section: Comparison — table comparing this concept to alternatives (mod N, naive approach, etc.)
- Section: Where you'll meet it — real-world examples / systems that use it
- Margin glossary — hover-linked terms

## Sections to Replace

1. `<title>` + h1: concept name + tagline
2. Interactive diagram: this is the heart — needs to actually work. Adapt the SVG and JS to your concept. Keep `--clay` for the actor / current state, `--olive` for secondary, `--oat` for environment.
3. Comparison table: this vs. the naive way (rows = property, columns = approaches)
4. Real-world: 3-5 named systems / papers
5. Glossary: 5-10 terms

## Customization Knobs

- Replace SVG ring (default) with whatever geometry fits — bar chart, network graph, 2D plane.
- Add a "play it out" stepper that animates a sequence (e.g. add a node → rebalance).
- Math notation: use plain text (`O(log n)`) or inline SVG, not MathJax.

## Pitfalls

- The interactive diagram MUST teach something the static version can't. If it doesn't, drop it.
- Don't reproduce a textbook section — the artifact's value is interaction.
- Test in browser: click every control, make sure JS doesn't throw.
- Keep JS small and inline — no frameworks.
