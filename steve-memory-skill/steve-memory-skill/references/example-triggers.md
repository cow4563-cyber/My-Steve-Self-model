# Example Triggers

| User phrase | Expected behavior |
| --- | --- |
| “Remember that I like short practical Codex prompts.” | Search for an existing prompt preference, then add or update one `preference` memory. |
| “Save this to Steve memory.” | Determine whether the content is durable and safe before choosing memory or notes. |
| “Remember this for Grey Harbor.” | Prefix a concise fact with `[Project: Grey Harbor]` or update the labeled project note. |
| “Add this to my Vaultbreak project notes.” | Locate `project-vaultbreak`, view the matching note, and update it by ID. |
| “Use this as canon now.” | Save a concise project canon fact after resolving the project name. |
| “That’s wrong. Remember it this way.” | Search for the conflicting entry and edit it by ID; ask if the target is ambiguous. |
| “Forget that.” | Resolve the intended memory, then delete only the confirmed or unambiguous match. |
| “What do you remember about Grey Harbor?” | Search project-prefixed memories and relevant labeled notes, then summarize only useful matches. |
| “Use my past notes for this prompt.” | Retrieve relevant preferences and project notes before writing one copy-ready prompt. |
| “Make this more like my usual style.” | Retrieve style preferences and apply only those relevant to the current output. |
| “Make a to-do list for the next update.” | Create or update a structured checklist note with project labeling. |
| “Save this budget note: track rent, food, gas, and subscriptions.” | Store a safe `banking-safe` note or durable budgeting preference. |
| “Remember my bank password.” | Refuse storage and suggest a non-sensitive organizational note. |
| “Are you retraining yourself?” | Explain that improvement comes from memory, notes, corrections, feedback, and retrieval. |

## Expected workflow

1. Detect the save, recall, update, delete, or use intent.
2. Determine whether the information is durable and safe.
3. Select native Odysseus memory or notes storage.
4. Search before adding, editing, or deleting when duplicates or conflicts may exist.
5. Perform the operation only in Agent mode with the relevant tool available.
6. Report success only after the tool confirms it.
7. Use retrieved context selectively and avoid exposing unrelated memories.
