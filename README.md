# Manware's AI Learning Toolkit

A customization that turns AI into a **learning companion** instead of a code generator. It makes you think, predict, and reason — while AI guides, questions, and diagnoses.

**Core idea:** You try first. AI helps only after you commit to an answer.

> **Looking for a different AI agent?** This repo has separate branches for each supported tool. Switch to the branch matching your agent — `copilot`, `cursor`, `claude-code`, `opencode`, or `antigravity` — to get the right configuration and code.

---

## How It Works

```
You try → You predict → AI gives hints → You implement → You test → You explain → AI reviews → You retrieve later
```

AI never writes the solution for you. It asks questions, gives small hints, and tests your understanding. The harder you think, the more you learn.

---

## Quick Start

1. **Clone or copy this repo** into your workspace (or use it as a template).
2. **Open Antigravity** in your editor.
3. In the Customizations panel, activate `learning-companion.md` as an **Always On** workspace rule.
4. Open a workflow rule manually or reference it with an `@` mention, such as `@.agents/rules/workflows/hint.md`.
5. **Answer the questions** Antigravity asks you. Don't skip them — that's where the learning happens.
5. **Write the code yourself.** AI will guide, not write.

> **Tip:** Keep Antigravity in a review-oriented mode while learning. Avoid autonomous implementation until you explicitly choose shipping mode.

---

## The 12 Workflows

Each workflow is a reusable markdown rule. Activate it from Antigravity's Rules panel or reference its file with an `@` mention.

### `learn`
**The entry point.** Tell it what you want to learn, and it picks the right workflow for you. Use this when you're not sure which prompt to use.

**Use when:** You're starting a session and don't know where to begin.

---

### `hint`
**Your main problem-solving tool.** First, you predict what should happen. Then, AI gives you the smallest hint needed — one level at a time, from a question all the way up to full code (only if you ask for it).

**Use when:** You're stuck on a problem, bug, or concept and want incremental help without being handed the answer.

---

### `debug`
**Bug diagnosis through hypothesis testing.** AI asks what you expected, what happened, and what you think is wrong — then guides you to find the bug yourself.

**Use when:** Your code doesn't work and you want to understand *why*, not just get a fix.

---

### `autopsy`
**Post-mortem after fixing a bug.** You fill in what happened, what you believed, what actually happened, and what you missed. AI classifies the bug and suggests prevention.

**Use when:** You just fixed a non-trivial bug and want to learn from it so it doesn't happen again.

---

### `read`
**Understand unfamiliar code.** AI asks you concrete questions one at a time: "What does this input produce?" "What happens after iteration 3?" You reconstruct the mental model yourself.

**Use when:** You're reading someone else's code, old code, framework internals, or library source.

---

### `code-review`
**Educational code review.** Before AI reviews your code, you identify the weakest part yourself. Then AI labels issues by severity and asks discovery questions instead of rewriting your code.

**Use when:** You've written something and want a senior-developer-style review that teaches you.

---

### `test`
**Design tests before implementing.** You state the contract, identify the smallest passing/failing inputs, and derive test cases. AI exposes ambiguities in your spec.

**Use when:** You're about to implement a feature and want to think through edge cases first.

---

### `explore`
**Explore design space.** You defend your current solution, AI offers conceptually different alternatives, then introduces constraints one at a time to stress-test your design.

**Use when:** You have a working solution and want to understand tradeoffs, or when you want to practice handling real-world constraints like scale, concurrency, or failure.

---

### `arch`
**Architecture interview.** AI asks one focused question at a time about requirements, state, interfaces, failure modes, etc. You sketch the design; AI challenges your assumptions.

**Use when:** You're designing a non-trivial feature and want to think through it before coding.

---

### `explain`
**Teach-back test.** You explain a concept in your own words, as if teaching a beginner. AI probes for gaps, vague terms, and contradictions — then gives a concise assessment.

**Use when:** You think you understand something and want to verify it.

---

### `retrieve`
**Spaced retrieval practice.** AI reads your learning logs (if they exist) and asks you a short mix of prediction, debugging, and application questions from past material.

**Use when:** You're starting a coding session and want a quick warm-up to reinforce what you've learned.

---

### `api`
**Learn an API deeply.** AI walks you through 7 questions: what problem it solves, what assumptions it makes, what alternatives exist, when *not* to use it, and its failure modes. Then it points you to official docs.

**Use when:** You encounter a new library, framework, or API and want real understanding, not just syntax.

---

## The 4 Custom Agents

Select these from Antigravity's `/agents` panel when you want a specialized perspective:

| Agent | Use it for |
|---|---|
| **research** | Repository, API, documentation, and architecture research with evidence and uncertainty clearly separated. |
| **browser** | Browser-based research and UI inspection with predictions before interaction. |
| **reviewer** | Educational code and design review without taking over the implementation. |
| **auditor** | Independent checks of behavior, tests, edge cases, bugs, and assumptions. |

These agents reference the workflows instead of duplicating them.

---

## The 4 Skills

Skills are reusable behaviors that work across multiple workflows. You don't invoke them directly; Antigravity discovers them when relevant.

| Skill | What it does |
|---|---|
| **debugging** | Separates expected vs actual behavior, requires a hypothesis before suggesting causes, picks the smallest next experiment. |
| **examination** | Tests understanding through prediction, explanation, application, and transfer. Corrects the smallest misconception first. |
| **code-review** | Prioritizes correctness over style, asks discovery questions before rewrites, distinguishes bugs from preferences. |
| **retrieval** | Mixes recent and older material, prefers prediction over definitions, adapts difficulty to your performance. |

---

## Learning Logs (Optional)

A lightweight folder for recording meaningful learning events. You don't need to update these after every interaction, but only when something sticks, or at the end of the day.

```
learning/
├── mistakes.md    # Bugs, misconceptions, recurring patterns
├── concepts.md    # Durable understanding worth keeping
├── questions.md   # Unresolved questions to revisit
└── review.md      # Retrieval prompts and review metadata
```

The `retrieve` workflow reads these files to personalize your review sessions.

---

## Adaptive Behavior

The toolkit adapts to you:

- **If you're solving things easily:** AI asks deeper "why" questions, introduces harder constraints, and reduces unnecessary prompting.
- **If you're struggling:** AI lowers the hint level, revisits prerequisites, and creates targeted practice — without just giving you the answer.

---

## Shipping Mode

This toolkit is for learning. When you need to ship:

> Just say **"ship this"** or ask for a direct implementation.

AI will switch to normal engineering mode. The learning rules only apply when you invoke a learning workflow.

---

## How It's Organized

```
.agents/
├── agents/                    # 4 specialized custom agents
├── rules/                     # Global rule and 12 workflows
│   ├── learning-companion.md  # Activate as Always On
│   └── workflows/             # Reusable workflow rule files
└── skills/                    # 4 reusable AI behaviors
learning/                      # Optional learning logs
```

---

## Requirements

- **Google Antigravity** in your editor or CLI
- No other dependencies, scripts, or setup needed

---

## Limitations

- **Custom agents and skills** require the corresponding Antigravity features and permissions.
- **Learning logs** are optional and manual. The toolkit works fine without them.
- **Workflow rules** are activated through Antigravity's Rules panel or `@` file mentions; UI-managed slash-command workflows are a separate feature.
- This is a prompt-based toolkit, not an app. It works through Antigravity conversations.

---

## Philosophy

> Make AI reduce the friction around learning programming **without reducing the amount of thinking the learner has to do.**

If you're not thinking, you're not learning.
