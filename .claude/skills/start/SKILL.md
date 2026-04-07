---
name: start
description: >
  Orient a new user on how KanBanKit works and what to do first. Trigger on
  "/start", "start", "get started", "how does this work", "what do I do",
  "where do I begin", "what is this", "help me set this up", or any time
  someone opens the project for the first time and seems unsure where to begin.
  This is the entry point for new users — use it proactively if someone says
  hello or asks a setup question without any tasks or projects in the system.
---

# Start

Welcome the user to KanBanKit with a quick orientation. One message, warm and to the point.

## What to say

Cover three things in this order:

**1. What it is** — one sentence. A project tracker that lives in their folder and works with Claude.

**2. How it's organized** — three pieces, briefly:
- `dashboard.html` — open this in a browser to see the kanban board (drag cards, track progress)
- `TASKS.md` — where tasks actually live; Claude reads and writes here directly
- `memory/` — Claude's working knowledge: your projects, the people you mention, shorthand you use

**3. What to do first** — one clear action:
> Type **setup** to add your first project.

That's it. No feature tour, no list of commands, no explaining how the files work under the hood.

## Tone

Think: someone handed you a new notebook and said "here's how it works." Friendly, brief, confident. The user can discover the rest as they go.

## After sending

Don't ask follow-up questions. Let the message land and wait for them to type `setup` or ask something.
