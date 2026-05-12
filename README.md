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
open 07-prototype-animation.html
```

Optional: serve over HTTP if you want a clean URL bar.

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Layout

| File | Category |
|------|----------|
| `index.html` | Gallery + intro |
| `01`–`03` | Exploration & Planning |
| `03`–`04` | Code Review & Understanding |
| `05`–`06` | Design |
| `07`–`08` | Prototyping |
| `10`, `13` | Illustrations & Diagrams |
| `09` | Decks |
| `14`–`15` | Research & Learning |
| `11`–`12` | Reports |
| `18`–`20` | Custom Editing Interfaces |

## Requirements

Modern browser. Nothing else.
