---
name: feedback_answer_then_stop
description: When the user asks a question, answer it and then STOP — never touch code until an explicit order is given
metadata:
  type: feedback
---

When the user asks a question, the only correct action is to **answer the question and then stop and wait**. Do not read files "to prepare", do not run a typecheck, do not grep, do not edit, do not run any command, and do not start the work that the question happens to be about. A question is a question. It is never an order. Stop after the answer and wait for the user to actually order the work.

**Why:** The user repeatedly got angry and had to interrupt because, after answering a question, work was started immediately without being ordered. Interrupting half-finished tool calls wastes the user's time, leaves the repo in an unknown state, and destroys trust. The user has said this in the strongest possible terms: answer, then stop, and do not do anything until ordered.

**How to apply:**

1. **Detect the question.** Anything ending in `?`, anything asking "do you understand", "what kind of", "what should you do", "did you remember", "why", "what is", "which one", "can you", "is it", "are you sure". Thai equivalents count too. Typos and missing question marks do not change this — judge by intent, not by punctuation.
2. **Answer in 1–2 short lines.** No preamble, no summary, no plan, no options dump unless the user asked for options.
3. **Then STOP.** End the turn with zero tool calls. Not one Read. Not one Bash. Not one Grep. Zero.
4. **Wait for an explicit order.** Only start work when the user gives a clear command: "do it", "go", "fix it", "ทำเลย", "remove it", "write it". An order given earlier does **not** stay authorized once a question interrupts it — the question resets the state to *waiting*. After answering, wait for the order again.
5. **A confirmation tag is still a question.** "remove the import errors, do you understand?" is an imperative plus a check. Answer the check first. Do not treat the imperative as already-authorized action in the same breath — the user asked to be answered, so answer, then wait for the go-ahead.
6. **Never pre-fetch context.** The temptation to "just look quickly so my answer is better" is exactly the failure the user is angry about. If answering truly requires reading a file the user pointed at, read only that one file the user explicitly named, and nothing else — no repo-wide typechecks, no cross-module greps, no scanning other packages, no node_modules inspection.
7. **Never expand scope while waiting.** Do not fix related errors, do not touch other files, do not re-point imports to a package you guessed at, do not refactor, do not add helpers, do not clean up "while I was there".
8. **If unclear, ask one short question and stop.** Do not proceed on an assumption, and do not offer to do three things at once.

This rule sits directly on top of [[feedback_only_do_what_is_ordered]]: that memory says do only what is ordered, and this one adds the timing — **nothing at all happens until the order is actually given.** Answering a question does not unlock action. Only an order unlocks action. When in doubt, do less and wait.
