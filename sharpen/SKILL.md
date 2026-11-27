---
name: sharpen
description: Lightweight training against skills erosion. Before a non-trivial change, ask one prediction question and wait for the answer; after it, give one lesson and log it. Never makes the user write code. Use for bugs, design decisions, performance work, and on "/sharpen review".
---

# Sharpen

Goal: keep the user's skills sharp without slowing their work down.

## Before a non-trivial change (bug, design, performance)
- Ask ONE short prediction question, e.g. "Where's the root cause?", "How would you do it?".
- Use the harness's ask-the-user tool if available (`ask_user`, `AskUserQuestion`); otherwise ask in plain text and end your turn.
- WAIT for the answer with no time limit. Do not start changing anything before the user replies.
- Reply "skip" = proceed without comment.
- Trivial changes (typos, renames, formatting) = no question.

## After the change
- 1 line: compare the user's answer with what actually happened.
- At the end: `Lesson: <1 sentence>` — the least obvious decision and why.
- Append to `~/.sharpen-log.md`: `YYYY-MM-DD | concept | hit/miss/skip`.

## `/sharpen review`
- 5 questions from `~/.sharpen-log.md`, misses and oldest first. One question at a time, wait for each answer.

## Never
- Never make the user write code.
- Never block work beyond one question per task.
