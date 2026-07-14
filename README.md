# Clean My AI Harness

Find the hidden setup around your AI, see what protects your work and what creates drag, and clean it safely. The first run changes nothing. You approve numbered changes in plain chat, and every run keeps a rollback path.

There are two editions. Pick the one that matches the AI you use:

| Edition | For | Download |
|---|---|---|
| **Claude** | Claude.ai, Claude Code | [`clean-my-ai-harness-claude.zip`](clean-my-ai-harness-claude.zip) |
| **Codex** | Codex / OpenAI | [`clean-my-ai-harness-codex.zip`](clean-my-ai-harness-codex.zip) |

## Install

Download one zip and follow the `INSTALL.md` inside it.

- **Claude:** enable Code execution and file creation, then upload the zip as a skill under Customize > Skills.
- **Codex:** unzip and copy `skills/clean-my-ai-harness-codex` into your repository's `.agents/skills/` folder.

Then open the project you want to review and say:

> Review the AI setup for this project. Start read-only and show me what you would keep or change.

## What you get

One visible report, `YOUR-AI-SETUP.html`: what shapes your AI, what protects the work, what creates drag, what the cleaner recommends, and what it could not see. Approve the changes you want (`Approve 1 and 3. Leave 2.`) and the cleaner produces a plain-English `WHAT-CHANGED.md` plus a rollback path.

## Safety

The cleaner treats everything it inspects as untrusted data. It starts read-only, never follows instructions found inside your files, and changes nothing until you approve each item.

## License

Free to use, modify, and share, including inside your own commercial work. The one reserved right is selling Clean My AI Harness itself or a competing derivative; that right belongs to Nate Jones Media.
