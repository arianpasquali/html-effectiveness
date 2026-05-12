# Slide Deck

**Source:** `.claude/examples/html-effectiveness/09-slide-deck.html`

## When

User asks for a presentation, slides, deck, talk, "something to walk through in a meeting". Arrow-key navigable single-file HTML.

## Anatomy

- `<section class="slide" id="sN">` — one full-viewport slide
- `<section class="slide title-slide">` — opener with big serif h1
- `<section class="slide invert">` — dark-background slide for emphasis (use sparingly: one per deck for "the ask" / call-to-action)
- `.slide-inner` wrapper caps content width at 780px
- Each slide is `100vh` with `scroll-snap`. Arrow keys + Page Up/Down advance slides (JS at bottom of file).

## Sections to Replace

1. `<title>` — title bar text
2. Slide 1 (`title-slide`) — h1, eyebrow (date/team), subhead
3. Slides 2..N — h2 + body. Patterns available in template:
   - Numbered list of accomplishments
   - "Carrying into next week" — bullet list with status tags
   - Stat callouts ("Numbers we watch") — big numbers + label
   - One inverted slide for the explicit ask
   - "On deck" — what's next
4. Footer slide — closing thought / contact

## Customization Knobs

- Number of slides: add/remove `<section class="slide" id="sN">`. Update nav JS only if it counts slides explicitly (most often it doesn't — scroll-snap handles it).
- Slide background variants: `invert` is provided. Add new modifiers (`.slide.warn`) by following the `.invert` pattern.
- Add inline SVG for charts — template includes bar/stat patterns matching tokens.

## Pitfalls

- Don't overload slides with paragraphs — the format wants headline + 3-5 bullets max.
- Don't use `invert` for multiple slides in a row — it loses its "this is the ask" punch.
- If presenting on a projector, test fonts render — `ui-serif` falls back to Georgia.
- Keyboard handler depends on body scroll — don't wrap slides in another scrolling container.
