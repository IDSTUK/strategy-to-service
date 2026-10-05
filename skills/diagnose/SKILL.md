---
name: diagnose
description: Find the root cause of a bug, failing test, incident or slowdown by reproducing it first, then fix it with a test that proves it. Use for "diagnose", "debug", "it's broken", "incident", "why is this slow", or any failure whose cause is unclear.
---

# Diagnose

**Use at any time:** during build, after a failed verification, or for a live incident. A fix without a reproduction is a guess. This skill gets a reliable reproduction first, then narrows to the cause, then fixes it test-first.

Read [the conventions](../../shared/conventions.md).

## Input

The symptom: an error, a failing test, an incident ticket, a user report or a performance complaint, plus access to logs, the codebase and an environment where it can be run.

## Steps

1. **Reproduce.** Build the fastest reliable way to see the failure: ideally a single failing test, otherwise a script or exact steps. If you can't reproduce it, gather more evidence (logs, timings, which users, since when) before guessing.
2. **Narrow.** Form one hypothesis at a time and test it with an observation that could prove it wrong: a log line, a bisect between a good and bad version, a smaller input. Write down each hypothesis and its result.
3. **Root cause.** State the cause in one sentence and the evidence that confirms it. Ask "why was this possible?" once more and note any wider weakness.
4. **Fix test-first.** Turn the reproduction into a test that fails, then fix until it passes, as in `build-test-first`.
5. **Check for siblings:** the same mistake elsewhere in the code.

## Output

A diagnosis note on the bug or incident (tracker or `delivery/stories/<id>-diagnosis.md`): symptom, reproduction, hypotheses tried, root cause with evidence, fix, test added, siblings found, and any wider weakness worth a story.

**Done when:** the reproduction fails before the fix and passes after it, and the root cause is stated with evidence.

## Next

Back to `review` for the fix. Incidents with business impact are also noted at the next `benefits-review` or `status-report`.
