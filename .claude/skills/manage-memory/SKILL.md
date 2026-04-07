---
name: manage-memory
description: >
  Teach Claude new things to remember — people, terms, projects, and context.
  Use when the user says "remember that...", "FYI...", "by the way...",
  "add to memory", "X means Y", "so-and-so is our...", introduces a person by
  name and role, explains an acronym or internal term, or corrects something
  Claude got wrong about their world. Also triggers when the user wants to
  update, remove, or review what Claude knows. If someone is teaching Claude
  something about themselves or their work, use this skill.
---

# Manage Memory

Store what the user tells you in the right place so it's available in every future session.

## The Three Memory Files

Route each piece of information to where it belongs:

| What | Where |
|------|-------|
| A person — name, role, relationship | `memory/people.md` |
| A term, acronym, codename, shorthand | `memory/glossary.md` |
| A project — context, goals, status updates | `memory/projects/{slug}.md` |

If the update also changes something in the `## Projects` table in `CLAUDE.md` (e.g., a new project or updated description), update that too. For people and glossary, CLAUDE.md doesn't need to change — the detail files are enough.

## How to Write Each Entry

**People** — add or update a row in `memory/people.md`:
```
| Name (nickname) | Role / how they relate to the user |
```
Include the nickname or shorthand if the user uses one.

**Glossary** — add or update a row in `memory/glossary.md`:
```
| Term | What it means in this person's world |
```

**Projects** — if the project file exists (`memory/projects/{slug}.md`), add the new information in the most sensible place — update the description, append a note, or add context. If the file doesn't exist yet, create it with a minimal structure (title, what it is, any notes the user gave).

## Handling Updates and Corrections

If the user is correcting something ("actually, Tom moved to a different team"), find the existing entry and update it in place rather than duplicating it. If they're removing something ("you don't need to remember X anymore"), delete the entry and confirm.

## Confirm

One short reply saying what was stored:

> Got it — added **Tom Chen** as Head of Engineering to your people file.

or

> Noted — "Atlas" = your internal design system. Saved to glossary.

Keep it brief. The user is teaching you something; just confirm you got it.

## When It's Ambiguous

If you're not sure which file something belongs in, make your best call — don't ask. The only time to ask is if the information itself is too vague to write down meaningfully (e.g., "remember this" with no content).
