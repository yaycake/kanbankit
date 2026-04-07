---
name: add-tasks
description: >
  Parse free-form input — typed or dictated — into individual tasks and add them
  to TASKS.md under the right project. Use when the user says "add tasks",
  "I need to...", "can you add...", "remind me to...", "things I need to do:",
  or pastes/dictates a stream of things they want captured. Also triggers when
  the user gives a brain dump, a list of to-dos, or mentions multiple things
  they need to get done. Great for capturing tasks quickly without worrying
  about format.
---

# Add Tasks

Turn whatever the user gives you — a sentence, a brain dump, a dictated list — into clean, individual tasks in TASKS.md.

## Step 1: Parse

Break the input into discrete, actionable tasks. Each task should be a single thing someone can actually do. Don't over-split ("write and send the email" is one task) or under-split ("handle the whole launch" should become specific subtasks if the user gave enough detail).

If the user just said something vague like "add tasks" without giving any, ask: "What do you want to add?"

## Step 2: Assign Projects

Read `CLAUDE.md` to see what projects exist. For each task, figure out which project it belongs to. Use context clues — keywords, names, topics — to match. If a task clearly belongs to a project, assign it silently. If it's ambiguous or doesn't fit any project, put it under `## Inbox`.

Create an `## Inbox` section in TASKS.md if it doesn't exist.

## Step 3: Write to TASKS.md

Append each task under its project section. Format:

```markdown
## [Project Name]

- [ ] Task one
- [ ] Task two
```

If the section already exists, append to it. If it doesn't, create it at the bottom of the file.

## Step 4: Confirm

One short reply listing what was added and where:

> Added 3 tasks:
> - "Call Sarah about budget" → **Acme Rebrand**
> - "Finish Q2 report" → **Inbox**
> - "Set up staging environment" → **DevOps**

Keep it scannable. No extra commentary unless something genuinely needs clarification.

## Tone

Fast and frictionless. The user is trying to capture something quickly — don't slow them down with questions unless a task is completely uninterpretable.
