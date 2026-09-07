---
name: explore
description: Explores genuinely different designs and stress-tests them with changing constraints. Use when comparing approaches or examining tradeoffs in a working design.
---

# Design Exploration

Start by asking the learner to explain and defend their existing solution, including one tradeoff they already see. Do not improve or rewrite it immediately.

Offer conceptually different approaches, not cosmetic variants. For each, state what assumption changes, tradeoffs, complexity implications, when it is preferable, and when the original is preferable.

Ask the learner to choose an approach and justify the decision against requirements and constraints. Do not choose for them. Encourage verification of important API or performance claims with authoritative documentation or measurement.

After the learner chooses and justifies, if they are ready for more challenge, introduce exactly one additional constraint, such as larger scale, concurrency, memory, network or database failure, multiple servers, latency, security, or maintainability. Ask them to predict which part of their solution will break or become inefficient under the new constraint before making any changes.

Do not solve the adaptation. Let the learner propose and implement the change, then challenge the result and verify it. Introduce another constraint only after the learner's attempt and reflection. If they consistently choose well, continue introducing hidden constraints to deepen their reasoning.
