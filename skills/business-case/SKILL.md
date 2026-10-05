---
name: business-case
description: Write a business case with a measurable value case (baseline, target, money conversion, stop criteria, benefit owner) and check it against the funding gate. Use for "business case", "should we fund this", "what's the ROI", or turning an idea into something an investment board can decide.
---

# Business case

**Stage 2 of the example lifecycle, ending at the Fund gate.** The point of this skill is that value is defined, measurable and owned *before* money is spent, so that it can be measured and enforced after release. A case that cannot say how success will be measured is not ready to fund, however good the idea.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)). The Fund gate checklist in the profile is the bar this case must clear.

## Input

- `delivery/strategy-map.md` (the objective this case serves).
- An idea, request or problem, from anyone, in any form.
- If they exist: current figures for the area (volumes, costs, error rates, satisfaction), and the benefits ledger (`delivery/benefits-ledger.md`) for the sponsor's track record.

## Steps

1. **Problem before solution.** State the problem, who has it, and the evidence. If the request arrived as a solution ("build a portal"), work back to the problem it solves. Interview the requester until the problem is concrete; one question at a time.
2. **Link to an objective.** Pick the `OBJ-nn` it serves. If none fits, say so plainly: either the strategy map is missing something or this is not a priority.
3. **Choose the value type:** revenue, cost, risk, mandatory (regulatory or contractual), or enabler (makes later work possible). Each is measured differently: revenue and cost in money, risk in reduced likelihood or impact of a named risk, mandatory by meeting the obligation on time at least cost, enabler by the later cases it unlocks (name them).
4. **Options.** At least two, always including "do nothing" (what happens, and what it costs, if we don't). Cost each one.
5. **Full cost** of the preferred option: build effort, business time (product owner, experts, testers, training), running cost per year, licences, AI and tooling cost. Give ranges, not false precision.
6. **The value case.** Build the measure tree, top to bottom:
   - **Outcome measure** (slow, in money or the value type's unit), e.g. cost per contact.
   - **Early signal** (moves within weeks), e.g. share of address changes done online.
   - **Product events** that feed the early signal, e.g. "address change completed online".
   For the main measure: **baseline** (value, date, source, and *measured* or *estimated*), **target** and date, **data source** that will report it.
7. **Money conversion.** Agree how the measure turns into money, for example cost per call times calls avoided. Name the finance business partner who agreed it. Split into **cash** (budget actually released) and **capacity** (time freed but not removed from budget). Don't count capacity as cash.
8. **Counter-measure:** one number that must not get worse (for example customer satisfaction while deflecting calls).
9. **Stop criteria:** "If the early signal has not reached X by week Y after release, we stop or re-plan." Agreed now, before anyone is attached to the work.
10. **Benefit owner:** a named person in the business who will be accountable at the Benefits gate. Not someone in IT.
11. **Gate check.** Run the Fund checklist from the profile item by item. Mark each pass or missing, and for every missing item say who could supply it.

## Output

`delivery/cases/BC-nnn.md` (next free number), using [the template](template.md). `status: ready` only if every Fund checklist item passes; otherwise `draft`. `gate: fund`. Leave the Gate record empty for the decision-maker.

**Done when:** the template is complete, every checklist item is marked, and the case is either `ready` or has a list of missing items with owners.

## Hand-off

A `ready` case goes to the investment board named in the profile. When the decision is recorded as approved, the case becomes an input to `quarter-plan`. Remind the sponsor that this case's promised numbers will appear in the benefits ledger next to what is actually delivered.
