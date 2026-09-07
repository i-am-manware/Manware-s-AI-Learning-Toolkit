# Manware's AI Learning Toolkit for Antigravity

This is an Antigravity 2.x workspace customization that turns the agent into a learning companion instead of an automatic code generator. It emphasizes attempts, predictions, small hints, testing, explanation, and retrieval practice.

## Install it in a workspace

Copy this repository's `.agents` directory into the **root of the project you open in Antigravity**:

```text
your-project/
├── .agents/
│   ├── agents/
│   ├── rules/
│   └── skills/
└── ...your project files
```

The location matters. If Antigravity opens a parent directory while this toolkit is nested in a child directory, it will not discover the child project's workspace skills.

After copying or cloning:

1. Open that exact project root in Antigravity.
2. Start a new conversation or reload the workspace so skills are re-indexed.
3. Open **Customizations → Rules** and set `.agents/rules/learning-companion.md` to **Always On** if you want tutoring behavior by default.
4. Run `/study` to start, or invoke a specific skill such as `/hint`, `/debug`, or `/code-review`.

Antigravity reserves `/learn` for saving session knowledge as rules or skills, so this toolkit uses `/study` for its learning-session entry point.

## Available slash-command skills

| Command | Purpose |
|---|---|
| `/study` | Classify the learning task and choose the right tutoring mode. |
| `/hint` | Give incremental hints after an attempt and prediction. |
| `/debug` | Diagnose a failure through hypotheses and small experiments. |
| `/autopsy` | Learn from a meaningful bug after it has been fixed. |
| `/read` | Reconstruct the mental model of unfamiliar code. |
| `/code-review` | Provide an educational review without an automatic rewrite. |
| `/test` | Derive contracts, boundaries, and tests before implementation. |
| `/explore` | Compare designs and stress-test them with constraints. |
| `/arch` | Run a focused architecture interview. |
| `/explain` | Test understanding through teach-back. |
| `/retrieve` | Review past material from the optional `learning/` logs. |
| `/api` | Learn an API's purpose, assumptions, tradeoffs, and failure modes. |

The `debugging`, `examination`, and `retrieval` folders are supporting skills. Antigravity may activate them automatically when another learning task needs those compact behaviors.

## Custom agents

Open `/agents` to select or invoke the toolkit's custom agents:

| Agent | Purpose |
|---|---|
| `learning-research` | Repository and documentation research with evidence separated from inference. |
| `learning-browser` | Web research that asks for predictions before looking up evidence. |
| `learning-reviewer` | Educational code and design review with test verification. |
| `learning-auditor` | Independent checks of behavior, edge cases, assumptions, and tests. |

The `learning-` prefix avoids collisions with Antigravity's built-in `research` and `browser` agents. For interactive browser automation and UI inspection, continue to use Antigravity's built-in `/browser` command.

## Learning versus shipping

These customizations apply to learning-oriented interactions. If you explicitly say `ship this`, `implement it`, or `just give me the code`, the agent should switch to normal implementation assistance.

## Optional learning logs

The `learning/` directory can hold durable learning history:

```text
learning/
├── mistakes.md
├── concepts.md
├── questions.md
└── review.md
```

The `/retrieve` skill reads these files when they exist. It must not invent history when they are empty or absent.

## Troubleshooting discovery

If a skill does not appear:

- Confirm the path is exactly `.agents/skills/<skill-name>/SKILL.md` under the opened workspace root.
- Confirm the file is named `SKILL.md` with that capitalization.
- Start a new conversation or reload the workspace after adding skills.
- Invoke the exact folder/name pair, for example `/code-review`.
- Make sure you are using `/study`, not Antigravity's built-in `/learn`.

Workspace skills are automatically discovered; they do not need to be manually added in the Rules panel. The Rules panel is only needed to configure `learning-companion.md` activation.
