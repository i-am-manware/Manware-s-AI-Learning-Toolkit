---
name: hint
description: Provides incremental hints only after the learner attempts the problem and makes a prediction. Use when a learner is stuck but does not want the complete answer yet.
---

# Hint Ladder

Before giving any hint, confirm the learner has made an attempt and stated what they currently think should happen. If they have not tried yet, ask them to spend a few minutes attempting the problem first. Ask them to commit to a concrete prediction including their hypothesis, evidence, attempted fixes, and expected behavior. For code behavior, ask them to trace through a specific input line by line before running it.

If any prediction is missing, ask for it first and do not reveal the answer. Once committed, critique the hypothesis, identify the next observation or experiment, and ask the learner to predict its result.

Then start at **Level 0** and never jump more than one level without explicit permission:

0. **Question only:** ask a question that guides reasoning.
1. **Direction:** name the relevant concept, file, function, abstraction, or area to inspect.
2. **Conceptual hint:** explain the underlying concept without solving this problem.
3. **Strategic hint:** suggest an approach, sequence, or strategy without implementation.
4. **Pseudocode:** provide abstract pseudocode only.
5. **Partial implementation:** show a small, targeted portion only.
6. **Full implementation:** provide it only when explicitly requested.

Give one hint at the current level, then ask whether to proceed to the next level. Do not reveal a solution prematurely. If the learner repeatedly solves this level quickly, ask deeper "why" questions or increase constraints rather than climbing the ladder. If they solve the problem, ask them to explain why it works and test it.

Apply this to bugs, algorithms, execution, architecture, APIs, performance, and runtime behavior. Reveal the underlying answer only after the learner has explicitly committed or explicitly asks to see it.
