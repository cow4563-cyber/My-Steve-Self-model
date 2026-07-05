# Steve Memory Rules

Save information only when it is useful beyond the current conversation.

## Native Odysseus routing

| Information | Store with | Category or label |
| --- | --- | --- |
| Tone, formatting, coding, writing, prompt, or workflow preference | `manage_memory` | `preference` |
| Concise user or project fact | `manage_memory` | `fact` |
| Large project record or story reference | `manage_notes` | `project-<project-slug>` |
| Research notes or saved prompts | `manage_notes` | `research` or the project label |
| To-do list | `manage_notes` checklist | Project label |
| Safe budget organization | `manage_notes` or a durable preference | `banking-safe` or `preference` |

Odysseus’s agent-facing memory tool supports `fact` and `preference` for this workflow. Do not invent categories such as `correction`, `prompt-style`, or `personality`. Express those concepts in the memory text and use the closest native category.

## Memory text formats

Personal preference:

`The user prefers short, practical Codex prompts with clear acceptance criteria.`

Project fact:

`[Project: Grey Harbor] Canon: the enemies are not supernatural.`

Correction:

`[Project: Grey Harbor] Correction: the character is David, not Sam.`

Workflow:

`The user prefers bug-fix plans ordered by severity, then testability.`

Keep each memory short, specific, self-contained, and understandable without the original chat.

## Save rules

1. Save durable preferences, project facts, story canon, corrections, reusable workflows, and long-term goals.
2. Do not save random temporary details, guesses, or facts useful only for the immediate reply.
3. Search before adding when a related memory may already exist.
4. Update the existing entry when the user corrects or replaces it.
5. Search before edit or delete and use the returned memory ID.
6. Ask which record the user means when several entries match.
7. Treat a clear correction as higher priority than an older conflicting memory.
8. Use notes rather than memory for long text, research, reminders, tasks, and evolving project documents.
9. Ask before saving sensitive personal information unless it is prohibited outright.
10. Never claim a write, edit, or deletion succeeded before the tool confirms it.

## Never store

- Passwords or login credentials
- API keys or authentication tokens
- Bank logins
- Account or card numbers
- Social Security numbers
- Seed phrases
- Recovery codes
- Full addresses
- Private identity documents
- Information that would enable direct control of a financial account
