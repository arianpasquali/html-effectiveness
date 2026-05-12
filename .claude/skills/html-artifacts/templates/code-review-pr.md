# Code Review PR

**Source:** `.claude/examples/html-effectiveness/03-code-review-pr.html`

## When

Annotated review writeup of a PR / branch — diff with margin notes, severity tags, risk map, suggested next steps. NOT the PR body itself (use markdown for that); this is the reviewer's deliverable.

## Anatomy

- Header: PR number + title, branch, author
- `<section class="prose">` — What this PR does (2-3 paragraphs of context)
- Section: Risk map — table or visual grid of risks (auth, perf, data integrity) × likelihood
- Section: Files — file-by-file annotated diff. Each file has:
  - File path heading
  - `<pre>` code block with added (clay) / removed (oat) line highlights
  - Margin notes calling out specific lines with severity tags (`blocker`, `nit`, `question`, `praise`)
- Section: Suggested next steps — ordered list, blockers first

## Sections to Replace

1. `<title>`: `PR #N — Review Summary`
2. h1: actual PR title
3. Prose section: what the PR does, in your words (not the author's description)
4. Risk map: real risks for THIS change
5. File diffs: pull real before/after, annotate with real concerns. Use line numbers.
6. Next steps: blocker items first, then nits

## Customization Knobs

- Add "test coverage" section if relevant.
- Add "approved-with-changes" / "needs another pass" banner at top.
- Severity tags can be extended (`security`, `perf`, `style`) — match existing color tokens.

## Pitfalls

- Don't ship without actually reading every changed file. The format implies thoroughness.
- "Praise" tags matter — find the good parts, not just problems.
- Don't paste massive diff blocks — excerpt the meaningful hunks.
- Required by repo CLAUDE.md: end with a rating out of 5 + brief motivation (e.g. `**Rating: 4/5**`).
- Line numbers from diff are slippery — verify against the branch HEAD.
