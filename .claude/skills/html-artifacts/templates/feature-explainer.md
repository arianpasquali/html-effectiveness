# Feature Explainer (in-repo)

**Source:** `.claude/examples/html-effectiveness/14-research-feature-explainer.html`

## When

"How does X work in this repo?" — feature already exists, user wants a navigable explainer. Request-path walkthrough, config snippets, FAQ.

## Anatomy

- Header card (clay-tinted) — TL;DR box: feature name + 2-3 sentence summary
- Section: The request path, step by step — collapsible `<details>` blocks per step, each with file:line refs
- Section: Configuring — tabbed config snippets (YAML / env / code) using `<details>` or radio-tabs
- Section: Gotchas worth knowing — bulleted list with concrete failure modes
- Section: FAQ — `<details>` Q/A pairs

## Sections to Replace

1. `<title>` + h1: `How <feature> works in <repo>`
2. TL;DR: the one-paragraph answer
3. Request path steps: real file paths, real function names, real line numbers (verify with grep before writing)
4. Config snippets: copy from actual config files in repo, not invented examples
5. Gotchas: real ones learned from incidents or code comments
6. FAQ: questions actually asked in Slack / docs / PR comments

## Customization Knobs

- Add a "where to make changes" section pointing to the right files.
- Add architecture diagram (inline SVG) for the call graph if it spans modules.
- Glossary in side margin for project-specific terms.

## Pitfalls

- Hallucinated file paths and line numbers are the #1 failure mode here — every reference must be verified.
- Don't paraphrase the README — the value is concrete `path:line` pointers and the FAQ.
- Collapsible sections default closed: put the most-asked thing first.
