---
name: build-test-first
description: Build a ready story test-first, one acceptance example at a time, with a failing test at the agreed seam, then the least code to pass it. Use for "build this story", "implement", "TDD", "red-green", or any coding work on a refined story.
---

# Build test-first

**Development step 3 of 6. Always.** Each acceptance example in the story becomes a test that fails first and then passes. When AI writes much of the code, tests written first are how people stay sure the code does what the business asked for and nothing else.

Read [the conventions](../../shared/conventions.md). Follow the project's own coding standards (`CLAUDE.md`, `CONTRIBUTING.md` or similar) and glossary (`CONTEXT.md`).

## Input

- A story that meets the definition of ready: acceptance examples, test seam, and design decisions if any.
- The codebase and its test setup.

## Steps

1. **Confirm the seams** named in the story with the engineer before writing tests. Tests go at those public interfaces, never against internals.
2. **Loop, one example at a time:**
   - **Red:** write one test for the next acceptance example, using the example's real values as the expected result. Run it. It must fail, and fail for the right reason.
   - **Green:** write the least code that makes it pass. Run the whole relevant suite.
   - Repeat with the next example. Each slice teaches something; let the next test respond to it.
3. **Measurement stories** are built the same way: the test checks that the event is emitted with the right fields.
4. **Keep it tidy between slices** only where the tests stay green; larger restructuring belongs in `review`.
5. **Commit** after each green slice with a message naming the story id.

Good tests read like the acceptance criteria, survive refactoring, and get their expected values from the story rather than recomputing them the way the code does.

## Output

Code and tests on a branch named for the story, every acceptance example covered by a passing test, commits referencing the story id. Note on the story anything that turned out different from the plan.

**Done when:** every acceptance example has a test that was seen failing and now passes, and the full suite is green.

## Next

`review`. If a test fails for reasons nobody understands, use `diagnose` first.
