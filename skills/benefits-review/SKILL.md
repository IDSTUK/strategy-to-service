---
name: benefits-review
description: Measure whether a released change delivered what its business case promised, recommend whether to continue, expand, change or stop it, and update the benefits ledger. Use for "benefits review", "did it work", "ROI check", "2/6/12 week review", or "update the benefits ledger".
---

# Benefits review

**Stage 6 of the example lifecycle, the Benefits gate.** This closes the loop. It reads the numbers the business case promised, takes the real readings, and makes a recommendation. Each result goes into a benefits ledger, which shows every sponsor's promised and delivered value side by side. The investment board sees that ledger when it decides the next case, and that is what makes the measurement stick.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- The release pack `delivery/releases/R-nnn.md` (switch-on date, switch plan, comparison group).
- The business cases it serves (`delivery/cases/BC-*.md`): baseline, target, early signal, money conversion, counter-measure, stop criteria.
- Readings from the agreed data sources. Use an analytics or reporting connector if available; otherwise ask the benefit owner for the figures and their source.
- `delivery/benefits-ledger.md` if it exists.

## Steps

1. **Which checkpoint is this?** Count weeks from the switch-on date. Use the profile's checkpoints (2, 6 and 12 weeks in the example), or "ad hoc" if requested.
2. **Take the readings** for the early signal, the outcome measure and the counter-measure, each with value, date and source. Note the reading as *from the agreed source* or *from elsewhere* (and why).
3. **Compare** against baseline and target, and against the comparison group if there is one. With a comparison group, the difference between the groups is the effect. Without one, list other things that changed in the period (seasonality, price changes, other releases) and say how confident the comparison is.
4. **Check the stop criteria** agreed in the business case. If they are met, the recommendation is stop or re-plan unless there is a stated, evidenced reason otherwise.
5. **Convert to money** using the agreed conversion, kept as cash and capacity separately. Report realised to date and forecast for the year.
6. **Recommend:** continue, expand (switch on for more users), change (named adjustment, back to `refine`), or stop (switch off, and what to remove). One paragraph of reasons.
7. **Update the ledger.** One row per case: sponsor, benefit owner, promised (from the case), delivered to date, forecast, confidence, last checkpoint, recommendation.
8. **Gate check.** Run the Benefits checklist from the profile and mark each item.

## Output

- `delivery/reviews/BR-nnn-<checkpoint>.md` with front-matter (`parent: R-nnn`, `owner:` benefit owner, `gate: benefits`), containing readings, comparison, money, recommendation, checklist and an empty Gate record.
- `delivery/benefits-ledger.md`, updated. Create it if missing with columns: case, sponsor, benefit owner, value type, promised (cash / capacity), delivered to date, forecast, confidence, last checkpoint, recommendation.

**Done when:** every measure in the case has a reading with a source, the stop criteria have been checked, and the ledger row is updated.

## Hand-off

The benefit owner presents the recommendation to the board named in the profile. A *change* recommendation returns to `refine` as new stories. Lessons about estimates feed the next `business-case`, and anything that changes an objective's measure feeds the next `strategy-map` refresh.
