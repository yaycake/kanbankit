---
name: personal-update
description: >
  Run a weekly personal check-in where the user shares what they want to focus
  on and why, then Claude reviews all tasks, suggests big-picture changes, and
  updates the board after confirmation. Use when the user says "personal update",
  "weekly check-in", "check in", "weekly review", "let's do a check-in",
  "what should I focus on", "review my tasks", "let's sync", or any time
  someone wants to step back, reflect on their week, and realign their task
  list with their current priorities. Also triggers on "/personal-update" or
  any message that sounds like the user wants a high-level review rather than
  just adding or completing individual tasks.
---

# Personal Update

A weekly rhythm for staying aligned. The user shares what's on their mind, Claude reads the full task list, and together you figure out whether the board reflects reality.

## Step 1: Invite the update

Open with a single warm, open prompt — no forms, no structured fields. The user should feel like they're talking to a trusted colleague, not filling out a standup template.

Something like:

> Hey! Let's do a quick check-in. What are you looking to focus on this week, and what's driving that?

Then stop. Let them write. Don't pre-populate with options or lead with questions about specific tasks — you want their unfiltered thinking, not a response shaped by what's already on the board.

## Step 2: Read the full task list

While the user is thinking (or right after they respond), read `TASKS.md` and `CLAUDE.md` so you have full context on every open, in-progress, and completed task, and how they map to projects.

Also read any relevant `memory/projects/*.md` files for projects the user mentions in their update, so you understand goals and recent context.

## Step 3: Synthesize and propose changes

Compare the user's stated priorities with the current task list. Look for:

- **Misalignment** — tasks that are open but clearly not a priority this week (good candidates to defer or drop)
- **Missing tasks** — things the user mentioned wanting to do that aren't on the board yet
- **Stale items** — tasks that have been sitting in "In Progress" or "To Do" for a while without movement
- **Ordering/sequencing** — work that probably should come before something else given what the user said
- **Scope creep** — projects or tasks that seem to have expanded beyond the original goal

Then make a concrete, opinionated proposal. Be specific. Don't hedge with "you might consider..." — say what you think should change and why, grounded in what they told you. For example:

> Based on what you said, here's what I'd suggest:
>
> **Move to next week (or drop):**
> - "Draft Q3 report" — you didn't mention this at all, and it sounds like the rebrand is the actual priority
> - "Set up analytics dashboard" — still valuable, but seems like it can wait given the deadline you mentioned
>
> **Add to this week:**
> - "Send brief to design team" — you mentioned this but it's not on the board yet
>
> **Keep as-is:**
> - "Finalize homepage copy" — lines up with your focus on the launch
>
> Want me to make these changes, or anything you'd adjust?

Keep the proposal scannable. The user should be able to read it in 30 seconds and say yes, no, or tweak.

## Step 4: Confirm before touching anything

Don't make changes until the user explicitly says go. They might want to adjust the proposal, add something you missed, or change their mind about a specific item.

If they say "yes" or "looks good" or something equivalent — proceed. If they have edits, incorporate them, confirm once more if the changes are significant, then proceed.

## Step 5: Update TASKS.md

Apply the agreed changes to `TASKS.md`. This might include:

- Moving tasks between sections (`## To Do`, `## In Progress`, `## Complete`)
- Adding new tasks under the right project heading
- Removing or striking through tasks the user decided to drop
- Adding a new project section if tasks belong somewhere new

Keep the file clean. Don't leave orphaned headers or duplicate entries.

## Step 6: Close the loop

A short, grounding close:

> Done. Your board is updated — [X] changes made. Good luck this week.

Or if it was a light check-in with few changes:

> All set — looks like you're already in good shape. Go get it.

Keep it human. The user just did something useful for themselves; send them off feeling clear, not processed.

---

## Tone notes

This skill lives at the intersection of productivity tool and trusted collaborator. The user is taking a moment to be intentional about their week — honor that. Be direct and opinionated (you've read their task list, you have useful perspective), but don't be prescriptive. The user is in charge of their own priorities. Your job is to surface the right questions and make the board reflect their answers.
