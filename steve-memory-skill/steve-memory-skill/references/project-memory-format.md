# Project Memory Format

Use a short persistent memory for stable project facts and a labeled Odysseus note for the evolving project record.

## Durable project fact

Store with `manage_memory`, category `fact`:

`[Project: <Project Name>] <Type>: <concise durable fact>.`

Types may include `Canon`, `Direction`, `Mechanic`, `Correction`, `Constraint`, or `Preference`.

Example:

`[Project: Grey Harbor] Direction: grounded survival horror with a biotech and chemical conspiracy.`

## Structured project note

Create or update a freeform note:

- Title: `<Project Name> — Project Memory`
- Type: `note`
- Label: `project-<project-slug>`
- Content:

```markdown
Project: <Project Name>
Category:
Summary:
Current Direction:
Important Details:
Bugs:
To-Do:
Saved Prompts:
Corrections:
Next Step:
```

Keep empty sections when they will be useful later, but remove categories that repeatedly stay irrelevant.

## Project checklist

Keep actionable work in a separate checklist:

- Title: `<Project Name> — To-do`
- Type: `checklist`
- Label: `project-<project-slug>`
- Items: structured `{text, done}` checklist items

Do not place checklist items into the freeform `content` field.

## Update workflow

1. Normalize the project label, for example `project-grey-harbor`.
2. List notes using that label.
3. View the candidate note by ID before changing it.
4. Ask when multiple notes could be the intended target.
5. Update the existing note rather than creating duplicates.
6. Preserve canon and current direction unless the user explicitly changes them.
7. Record corrections clearly and use the corrected version in later answers.
8. Summarize or archive stale detail when the note becomes difficult to use.

## Grey Harbor example

```markdown
Project: Grey Harbor
Category: Survival horror
Summary: A grounded coastal mystery.
Current Direction: Resident Evil-style investigation involving a biotech and chemical conspiracy.
Important Details: No supernatural enemies.
Bugs:
To-Do:
Saved Prompts:
Corrections:
Next Step:
```
