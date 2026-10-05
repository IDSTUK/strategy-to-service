---
name: review
description: Review a branch before merge on three checks, covering coding standards, match to the story and business case, and security, then report findings by severity. Use for "review", "code review", "check this before merge", or "does this do what the story asked".
---

# Review

**Development step 4 of 6. Always, before merge.** Three separate checks, because each catches what the others miss. The second check, "does the code do what was asked, traced back to the business case", is the link auditors and architecture boards look for and generic code review skips.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- The branch and its diff against the main branch.
- The story (and feature and business case) it implements.
- The project's documented standards, and the organisation's security standards if the profile names them.

## Steps

Run the three checks independently. If sub-agents are available, run them in parallel so one doesn't colour another.

1. **Standards.** Does the code follow this repository's documented standards and glossary? Readability, naming, structure, error handling, tests at the agreed seams. Cite the standard for each finding.
2. **Spec.** Does the code do what the story's acceptance criteria say, all of them, and nothing outside them? Are the measurement events emitted as the business case needs? Is there anything built that no story asked for?
3. **Security.** Input handling, authentication and authorisation, secrets, data exposure (especially personal data), dependency risks, logging of sensitive data. Use the organisation's standards where given.

For each finding: file and line, what is wrong, a concrete case where it goes wrong, severity (must fix / should fix / consider), and a suggested fix. Check every must-fix finding against the actual code before reporting it.

## Output

A review report in the pull request (or `delivery/stories/S-nnn-review.md` with no code host connected), grouped by check and sorted by severity, ending in one verdict: **ready to merge**, **fix then merge**, or **rework**.

**Done when:** all three checks have run, each finding has a severity, and there is a verdict.

## Next

Must-fix findings go back to `build-test-first`. Once the verdict is "ready to merge", go to `verify`.
