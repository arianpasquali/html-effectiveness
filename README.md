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

## Install as Claude Code skill

Repo ships `html-artifacts` skill under `.claude/skills/`. Skill routes requests like "slide deck", "status report", "PR writeup" to right template, then copy-and-customize.

**Project-scoped** (works in this repo only):

```bash
git clone https://github.com/arianpasquali/html-effectiveness
cd html-effectiveness
# Skill auto-discovered from .claude/skills/ when Claude Code runs here
```

**User-scoped** (works everywhere):

```bash
mkdir -p ~/.claude/skills
cp -r .claude/skills/html-artifacts ~/.claude/skills/
```

Restart Claude Code session. Trigger by asking for any artifact type:

> "make me a slide deck for the Q2 review"
> "write a status report for the migration"
> "explain this PR as an annotated writeup"

## Requirements

Modern browser. Nothing else. Skill install requires Claude Code.
