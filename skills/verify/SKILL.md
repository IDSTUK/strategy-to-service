---
name: verify
description: Run the actual application and check each acceptance criterion and measurement event works end to end, with evidence. Use for "verify", "QA", "test it for real", "does it actually work", or after review and before a release candidate.
---

# Verify

**Development step 5 of 6. Always.** Passing tests prove the code does what the tests say. This step proves the running system does what the story says: in a browser, through the API, or in the app, the way a user or the business would see it. It also proves the measurement events arrive, which the Release gate needs.

Read [the conventions](../../shared/conventions.md).

## Input

- The reviewed branch, deployed to a test or preview environment, or run locally.
- The story's acceptance criteria and the measurement stories.

## Steps

1. **Start the system** the way it really runs (not just the test suite).
2. **Walk each acceptance example** with its real values. Record pass or fail, with evidence: a screenshot, a response, a log line.
3. **Try the edges** the examples imply but don't spell out: empty values, a slow network, permissions for a user who shouldn't have access, the same action twice.
4. **Check measurement:** do the product events arrive in the analytics or data store with the right fields? Record where you saw them.
5. **Accessibility and basic performance** for user-facing changes: keyboard use, labels, contrast, and page or response time against the profile's limits if any.
6. **Every failure** becomes a bug linked to the story, with steps to reproduce, and goes back to `build-test-first` (or `diagnose` if the cause is unclear).

## Output

A verification record on the story (tracker comment or `delivery/stories/S-nnn-verify.md`): each acceptance example with result and evidence, edge cases tried, measurement events confirmed, bugs raised.

**Done when:** every acceptance example and every measurement event has a recorded result with evidence.

## Next

When every story in the planned release is verified, go to `release-candidate`.
