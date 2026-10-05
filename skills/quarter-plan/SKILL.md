---
name: quarter-plan
description: Turn approved business cases into a committed quarterly plan and a set of feature tickets, including measurement features, dependencies and capacity. Use for "quarterly planning", "plan the quarter", "break this case into features", or "what can we commit to".
---

# Quarter plan

**Stage 3 of the example lifecycle, ending at the Commit gate.** Turns funded business cases into features that teams can build, checks they fit the capacity of both IT *and* the business, and makes measurement part of the plan rather than an afterthought.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- Approved business cases: `delivery/cases/BC-*.md` with an approved Gate record.
- Team capacity for the quarter: teams, people, planned leave, and run work already committed. Ask if not provided.
- Business availability: product owners, subject experts and testers for each case.
- The previous quarter's plan, if any, for work carried over.

## Steps

1. **List candidate cases** in priority order (the investment board's order if given; otherwise by value per unit of cost, mandatory work first).
2. **Break each case into features.** A feature is something a user or the business can see working, small enough for one team to finish within the quarter. Write each with: what it does, who it is for, the business case it serves, and how we'll know it's done.
3. **Add the measurement features.** For every case, at least one feature that makes its measures visible: the product events from the value case, the data feed, and a dashboard or report showing baseline, target and current reading. If the case needs a comparison group, include the release switch that creates it.
4. **Map dependencies** across teams and outside suppliers. Each dependency has an owner, a date needed and a date promised.
5. **Check capacity.** Size features roughly (small, medium, large, or in team-weeks). Keep at least the profile's free share for run work and surprises (20% in the example). If the plan does not fit, cut whole features, starting from the lowest value; never thin the measurement features.
6. **Book the business time.** For each case, name the product owner, experts and business testers and the weeks they are needed. Unbooked business time is the commonest reason AI-speed teams sit idle.
7. **List risks** with owners.
8. **Gate check.** Run the Commit checklist from the profile and mark each item.

## Output

- `delivery/plans/YYYY-Qn.md`: the committed features by team and month, dependencies, capacity table (IT and business), risks, the Commit checklist, and an empty Gate record.
- `delivery/features/F-nnn.md`, one per feature, with front-matter (`parent: BC-nnn`, `owner:` the product owner), a description, acceptance outline, size, team, and `measurement: true` on measurement features. If a tracker connector is available, create the features there as well and record the `link:`.

**Done when:** every committed feature has a parent case, every case has a measurement feature, every dependency has an owner, and the capacity table shows the plan fits.

## Hand-off

When the Commit gate is approved, each feature goes to the development team, starting with `refine`. Tell the delivery lead which features have external dependencies due first.
