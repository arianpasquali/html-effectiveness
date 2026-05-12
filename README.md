# The unreasonable effectiveness of HTML

Twenty self-contained `.html` files an agent produced instead of a wall of markdown. Each demo trades a document you'd skim for one you'd actually read. Companion to the blog post.

## What this is

A gallery of agent-generated HTML artifacts grouped by the kind of work they replace — exploration, code review, design, prototyping, diagrams, decks, research, reports, and custom editing UIs.

Every file is a single static `.html` with no build step, no dependencies, no server. Open in browser. Done.

## Usage

```bash
# Open the index
open index.html

# Or any individual demo
open templates/07-prototype-animation.html
```

Optional: serve over HTTP if you want a clean URL bar.

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Layout

```
index.html        Gallery + intro
README.md
templates/        Twenty self-contained demos
```

Demo categories (see `index.html`): Exploration, Code Review, Design, Prototyping, Diagrams, Decks, Research, Reports, Custom Editors.

## Requirements

Modern browser. Nothing else.
