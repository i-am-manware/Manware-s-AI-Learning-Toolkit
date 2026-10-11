---
name: roadmap
description: Create, update, and traverse a milestone-driven learning roadmap.
---

# Roadmap Tracker & Guide

Maintain and advance a multi-stage roadmap in `learning/roadmap.md`.

## Mode 0: Ingestion / Import
When the learner provides raw curriculum text, an external syllabus, or an exported ChatGPT prompt:
1. Parse the text into sequential phases and milestone tasks.
2. Ensure each item includes:
   - Checkbox status (`[-]` for the first topic, `[ ]` for the rest).
   - Milestone title and prerequisite concepts.
   - A concrete deliverable or verification check.
3. Automatically write or overwrite this structure to `learning/roadmap.md`.
4. Ask the learner to confirm the generated milestones before beginning Topic 1.

## Mode 1: Initialization / Creation
When the learner provides a high-level goal or topics:
1. Break it down into sequential, milestone-sized topics with concrete deliverables.
2. Structure `learning/roadmap.md` using the exact schema below.
3. Keep the initial topic marked as `in_progress` and all subsequent topics marked as `pending`.

## Mode 2: Resuming / Advancing
When the learner says "start", "resume", "where did we stop?", or asks to continue:
1. Read `learning/roadmap.md`.
2. Find the last topic marked `[x]` (completed) or `[-]` (in progress).
3. If the current topic is verified complete, change its status to `[x]` with a completion timestamp.
4. Set the immediately following topic to `[-]` (in progress).
5. State the active topic, its prerequisite goals, and recommend the right starter skill (e.g. `explain` for theory, `arch` for system design, or `test` for implementations).

## Mode 3: Milestone Verification
Before marking any topic as `[x]`:
1. Ask the learner to demonstrate or summarize completion (e.g. explain the invariant, show passing tests, or present the design).
2. Do not silently mark items complete without learner confirmation or evidence.
3. Suggest logging significant insights or misconceptions into `learning/concepts.md` or `learning/mistakes.md`.