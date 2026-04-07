---
name: setup
description: >
  Quickly onboard a new project by asking for a title, description, and immediate
  tasks — then writing the project memory file and adding tasks to TASKS.md.
  Use when the user wants to add a project to their system, says "start a new project",
  "initiate project", "set up [project name]", "add a project", or is getting the
  system running for the first time and wants to capture what they're working on.
  Fast and focused — runs in under a minute per project.
---

# Setup

Capture a new project in three questions, then write it to memory and tasks.

## The Interview

Ask all three questions in a single message — keep it light:

> Let's get this project into the system. Three quick things:
>
> 1. **Project title** — what do you call it?
> 2. **Description** — what is it and what's the goal? A sentence or two is fine.
> 3. **Immediate tasks** — what needs to happen next? List whatever's top of mind.

## After They Answer

### Write the project file

Create `memory/projects/{slug}.md` (slug = lowercase, hyphenated title):

```markdown
# [Project Title]

## What It Is
[Description from user]

## Immediate Tasks
- [task 1]
- [task 2]
- ...
```

Create `memory/projects/` if it doesn't exist.

### Update CLAUDE.md

Add or update the project in the `## Projects` table in `CLAUDE.md`:

```markdown
| **[Project Title]** | [one-line description] |
```

- If `CLAUDE.md` doesn't exist yet, create it with a minimal structure: `## Me` (blank), `## Projects` table with this entry, and `→ Details: memory/projects/` pointer.
- If `CLAUDE.md` exists but has no `## Projects` section, add one.
- If the project is already listed, update the row rather than duplicating it.

### Add tasks to TASKS.md

Append the immediate tasks under a project section header in `TASKS.md`.
If `TASKS.md` doesn't exist yet, create it with just this project's tasks.

Format:
```markdown
## [Project Title]

- [ ] Task one
- [ ] Task two
```

### Confirm what was created

One short message:

> Done. Added **[Project Title]** to CLAUDE.md, created its project file, and dropped [X] tasks into your list.
>
> Run **setup** again whenever you want to add another project.

## Keep it short

No preamble, no explanation of the system, no asking follow-up questions unless something is genuinely unclear. The user can enrich the project file with mid-range goals, people, decisions, and open questions later — this is just the starting point.
