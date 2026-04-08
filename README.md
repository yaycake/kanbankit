# KanBanKit

A personal project tracker that lives in a folder and runs with Claude. Includes a kanban board, a task list, and a memory system so Claude learns your projects, your people, and your shorthand over time.

---

## What's included

| File / Folder | What it does |
|---------------|--------------|
| `dashboard.html` | Kanban board UI — open in any browser |
| `TASKS.md` | Where your tasks live; Claude reads and writes here |
| `CLAUDE.md` | Claude's working memory — loads every session |
| `memory/` | Deep memory: projects, people, glossary |
| `.claude/skills/` | Five skills that power the system |

---

## Getting started

**Requirements:** [Claude desktop app](https://claude.ai/download) with Cowork mode.

1. Download or clone this repo
2. Open the Claude desktop app and start a new Cowork session
3. Select the `KanBanKit` folder as your project folder
4. Type `/start`

Claude will orient you and tell you exactly what to do next.

---

## Commands

| Command | What it does |
|---------|--------------|
| `/start` | Orientation for new users — start here |
| `setup` | Add a new project to the system |
| `add tasks` | Capture tasks from free-form input or dictation |
| `remember that...` | Teach Claude a person, term, or project detail |
| `personal update` | Weekly check-in — share your focus, Claude reviews all tasks and suggests changes |

---

## How it works

**Tasks** live in `TASKS.md` as plain markdown checkboxes. Claude adds to and reads from this file directly. The kanban board in `dashboard.html` reads the same file — open it in your browser to visualize your work.

**Memory** builds up over time. When you introduce someone ("BTW, Priya is our new PM"), Claude writes it to `memory/people.md`. When you explain a term ("we call it the north star"), it goes to `memory/glossary.md`. Project context lives in `memory/projects/`. All of this loads automatically at the start of each session so Claude always has context.

**Skills** are the five commands above. They're bundled in `.claude/skills/` so they work as soon as you open the folder — no installation or configuration needed.

---

## Opening the dashboard

`dashboard.html` runs entirely in your browser — no server needed. Just open the file directly:

- **Mac:** double-click `dashboard.html`, or `open dashboard.html` in terminal
- **Windows:** double-click `dashboard.html`

The board reads your `TASKS.md` on load and reflects whatever's in the file. Changes you make in Claude (via `add tasks`) show up the next time you refresh the board.

---

## Tips

- **Start with `setup`** — Claude needs at least one project before task assignment makes sense
- **Be casual** — `add tasks` is designed for brain dumps; just say what's on your mind
- **Teach as you go** — you don't need to fill out the memory files manually; just mention things naturally and use `remember that...` when you want Claude to retain something
- **The memory files are yours** — `CLAUDE.md`, `memory/people.md`, and `memory/glossary.md` are plain markdown; edit them directly any time

---

## File structure

```
KanBanKit/
├── README.md
├── dashboard.html
├── TASKS.md
├── CLAUDE.md
├── memory/
│   ├── people.md
│   ├── glossary.md
│   └── projects/
└── .claude/
    └── skills/
        ├── start/
        ├── setup/
        ├── add-tasks/
        ├── manage-memory/
        └── personal-update/
```
