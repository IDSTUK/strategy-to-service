---
name: release-candidate
description: Bundle verified stories into a release candidate with merge, version, change log, ticket links, evidence and rollback steps, then stop before production and hand over to release-ready. Use for "release candidate", "prepare the release", "cut a release", or "ship" in an organisation with change control.
---

# Release candidate

**Development step 6 of 6. Always.** Packages finished work so the business can release it. It **stops before production**: deploying behind a switch may be automatic in some organisations, but switching it on for users is a business decision made at the Release gate. Keeping those apart is what lets controls such as separation of duties hold while development moves fast.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- Stories with a "ready to merge" review and a complete verification record.
- The repository and its release conventions (branching, versioning, change log).

## Steps

1. **Check the evidence.** Every story in scope has review and verify records. List any that don't and leave them out.
2. **Merge** following the repository's rules (pull request, required approvals). Never bypass a required approval.
3. **Version and change log.** Bump the version per the project's scheme and write the change log entry in plain language, grouped by feature, each line naming its story.
4. **Rollback steps.** How to undo this release: switch off, redeploy previous version, data changes to reverse. Note anything that cannot be undone (for example a data migration) in bold.
5. **Write the release file.**

## Output

`delivery/releases/R-nnn.md` with front-matter (`parent:` the feature or features, `gate: release`, `status: draft`), listing: version, stories with links to their review and verify records, change log, rollback steps, irreversible changes, and the environment where it can be tried. The merged code, tagged with the version.

**Done when:** every story in the release has linked evidence and the rollback section is complete.

## Next

Hand over to the product owner and release manager: `release-ready` completes the release pack.
