# Steve Memory Skill for Odysseus

Steve Memory Skill is an importable Odysseus skill bundle that helps Odysseus behave like a consistent personal assistant through memory, notes, corrections, retrieval, preferences, and project context.

“Self-learning” here does **not** mean automatic model retraining, hidden fine-tuning, or autonomous self-modification.

## What it does

- Saves useful long-term preferences and concise facts
- Maintains project context and story canon
- Tracks corrections without preserving known-wrong claims
- Uses labeled notes for project records, research, prompts, and checklists
- Retrieves relevant local context before answering
- Preserves Steve’s friendly, practical, calm, lightly silly style
- Enforces strict banking and credential-storage boundaries

## Folder structure

```text
steve-memory-skill/
├── SKILL.md
├── README.md
└── references/
    ├── banking-safety.md
    ├── example-triggers.md
    ├── memory-rules.md
    └── project-memory-format.md
```

## Requirements

- Odysseus with the Skills system enabled
- Memory and Notes enabled for the current user
- Agent mode for full tool-backed save, update, delete, and retrieval workflows
- Any Odysseus-compatible model, including local Ollama models such as `steve:latest`

The skill itself does not require OpenAI, Anthropic, Gemini, or another paid cloud API.

## Import into the installed Odysseus version

The inspected Odysseus build is `1.0.1-dev.5acd0ce`. Its UI imports skills from a public GitHub or skills.sh URL; it does not directly import a local folder or ZIP.

For the cleanest GitHub import, make the **contents** of `steve-memory-skill/` the root of a public GitHub repository so the repository root contains `SKILL.md`, `README.md`, and `references/`.

1. Create a public GitHub repository.
2. Upload the contents of `steve-memory-skill/` to the repository root.
3. Open Odysseus.
4. Open **Brain**.
5. Select **Add**.
6. Paste the GitHub repository URL into **Skill import URL**.
7. Select **Import**.
8. Open **Brain → Skills** and verify that `steve-memory-skill` is published and enabled.

Current-version behavior:

- URL import stamps the current Odysseus owner onto the installed skill.
- URL import changes `source` to `imported`.
- This build currently stores URL-imported skills under the `imported` category even when the source frontmatter says `category: memory`.
- Only public GitHub content is supported by the importer; private repositories requiring authentication are not supported by this UI flow.

## ZIP and local-folder limitation

`steve-memory-skill.zip` is a portable archive with the parent folder included. The inspected Odysseus UI cannot import that ZIP directly.

Odysseus stores local skills under:

```text
data/skills/<category>/<skill-name>/SKILL.md
```

In the current Docker container, that root is `/app/data/skills/`. Manual copying is not recommended for this installation because:

- Strict owner filtering hides manually copied skills without the correct `owner` frontmatter.
- The portable bundle intentionally omits the machine-specific owner.
- The running container has no host bind mount for `/app/data`, so a replaced container may lose manually copied data.

Use the supported GitHub URL importer unless the Odysseus installation is first configured with persistent data storage and the correct owner stamping.

## Use

Enable **Brain → Skills** and switch the conversation to **Agent** mode for complete memory and notes behavior.

Odysseus also exposes published skills as slash commands:

```text
/steve-memory-skill <request>
```

The slash command can pin the skill instructions to a request, but persistent tool operations still require the relevant tools and permissions. Plain Chat mode supports only limited inline memory handling and does not expose the full Skills/Notes tool workflow.

## Test prompts

- `Remember that I like short practical Codex prompts.`
- `Save this as a Grey Harbor project fact: no supernatural enemies.`
- `What do you remember about Grey Harbor?`
- `That is wrong. Remember that the character is David, not Sam.`
- `Forget my last prompt-style preference.`
- `Make a project checklist for the next Vaultbreak update.`
- `Save this safe budget note: track rent, food, gas, and subscriptions.`
- `Are you retraining yourself when you learn my preferences?`

## Safety

Never store passwords, API keys, authentication tokens, bank logins, account or card numbers, Social Security numbers, seed phrases, recovery codes, full addresses, or private identity documents. Never use this skill to move money, make purchases, or directly control a financial account.
