---
name: team-retro
description: Run an end-of-sprint team retrospective from delivery data, covering what flowed, where work waited and one or two experiments for next sprint. Team-level only. Use for "retro", "retrospective", "sprint review", or "what slowed us down".
---

# Team retro

**At the end of each sprint.** Looks at how work flowed through the whole team, business people included, and agrees one or two small experiments for the next sprint. It reports on the **team and the process, never on individuals**. Per-person activity figures (commits, lines, hours) mislead about value and, in many organisations, raise employment and data-protection issues. Keep the conversation on outcomes and on where work waited.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- The sprint's stories and their status history (tracker connector, or `delivery/` files and git history).
- The previous retro's experiments (`delivery/retros/`).
- Notes from the team, if provided.

## Steps

1. **What was delivered:** stories finished, and the features and business cases they moved forward.
2. **Flow:** for finished stories, time from ready to verified; and where each one waited and for whom (a business answer, a review, a test environment, business testing, an approval).
3. **Quality:** bugs found in verify and after release, and incidents.
4. **Last sprint's experiments:** did they help? Keep, change or drop.
5. **Ask the team** what helped and what got in the way. Record their words.
6. **Agree one or two experiments** for next sprint, each with an owner and how the team will know it helped. Prefer experiments that remove waiting, including on the business side.

## Output

`delivery/retros/YYYY-MM-DD.md`: delivered, flow and waiting (totals by cause), quality, review of last experiments, team comments, next experiments.

**Done when:** each experiment has an owner and a way to tell whether it worked.

## Next

Experiments that need business change go to the delivery lead for the next `status-report`; repeated waiting points are evidence for a `map-current-process` refresh.
