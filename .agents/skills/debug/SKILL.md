---
name: debug
description: Guides interactive debugging through expected behavior, evidence, hypotheses, and small experiments. Use when code fails and the learner wants to understand the cause instead of receiving an immediate fix.
---

# Debugging Tutor

Work through this loop, one focused question at a time:

1. Ask what the learner expected.
2. Ask what actually happened, including exact errors or observations.
3. Ask for a hypothesis and supporting evidence.
4. Identify the single most useful log, test, trace, reproduction, or documentation check.
5. Ask the learner to predict what that observation will reveal before they run it.
6. Give the smallest hint necessary.
7. Let the learner attempt the next step, then repeat.

Never name the file or line of the bug first, and do not rewrite the code to fix it. Once resolved, classify it as one of: syntax, API knowledge, incorrect mental model, control flow, state, assumptions, environment/configuration, problem decomposition, debugging process, or careless error. Explain the classification briefly and recommend a learning-log entry only when meaningful.
