---
name: release-ready
description: Get a release candidate ready for the business to switch on, covering acceptance testing, training and comms, the change request, the release switch plan and confirmation that measurement works. Checked against the release gate. Use for "release pack", "is this ready to go live", "UAT", "change request", or "go/no-go".
---

# Release ready

**Stage 5 of the example lifecycle, ending at the Release gate.** Development hands over a release candidate. This skill does the business half of releasing: acceptance testing by real business users, readiness of the people affected, the change request, and proof that the measures promised in the business case will actually report. It separates *deploying* (IT puts the code live, switched off) from *releasing* (the business switches it on), so business readiness, not IT, sets the pace.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- `delivery/releases/R-nnn.md` written by `release-candidate`: what is in the release, stories, review and verify evidence, rollback steps.
- The features and business cases it serves (follow the parents).
- Access to a test or preview environment, if the business testers will use one.

## Steps

1. **Acceptance test scripts.** From each story's acceptance criteria, write step-by-step scripts a business tester can follow in plain language, with expected results. Group them by tester. Record the named tester and result (pass, fail, comment) for each. Failures go back to development as bugs, linked to the story.
2. **Business readiness.** For each group of people affected (customers, staff, support), list what changes for them and what they need: training notes, a short "what's new", support FAQs and known issues. Draft them.
3. **Measurement check.** For every measure in the parent business cases, confirm data is arriving now: name the event or report, where you saw it, and the reading. If it is not arriving, the release is not ready. This is the step that makes the Benefits gate possible.
4. **Release switch plan.** Who switches it on, for whom first (for example 10% of users or one region), and whether a comparison group stays on the old way so the benefit can be measured fairly. If no switch is possible, say why and how the before-and-after comparison will be made instead.
5. **Change request.** Draft it in the profile's format: what is changing, why (link the case), risk rating with reasons, test evidence, rollback plan, release window, and who to call.
6. **Gate check.** Run the Release checklist from the profile and mark each item.

## Output

`delivery/releases/R-nnn.md`, completed with sections for acceptance testing, business readiness, measurement check, switch plan, change request, the Release checklist, and an empty Gate record. Supporting drafts (training notes, FAQs) can sit beside it as `R-nnn-training.md` and similar. If a change-management connector (such as ServiceNow) is available, raise the change there and record its `link:`.

`status: ready` only when every checklist item passes.

**Done when:** every acceptance script has a named tester and a result, every measure has a confirmed reading, and the checklist is fully marked.

## Hand-off

The release manager (or change board) decides. After the switch is turned on, record the date in the release file; the Benefits checkpoints (2, 6 and 12 weeks in the example) count from that date, and `benefits-review` takes over.
