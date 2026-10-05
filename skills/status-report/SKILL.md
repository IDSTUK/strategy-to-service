---
name: status-report
description: Produce a steering-committee status pack from the delivery folder, with progress, spend against budget, the benefits ledger and where work is waiting (business or IT). Use for "status report", "steering pack", "RAG report", "portfolio update", or "where is work stuck".
---

# Status report

**Works across every stage.** Reads everything in `delivery/` and writes the report that steering committees, portfolio offices and executives ask for. It also shows where work is waiting and whose turn it is, so that business bottlenecks can be seen as clearly as IT ones.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- Everything in `delivery/`: cases, plans, features, releases, reviews, the benefits ledger.
- Tracker data if a connector is available (statuses and the dates they changed).
- Spend figures: actuals per case from finance, if provided. Ask; never invent them.
- The audience and period (for example "investment board, September").

## Steps

1. **Portfolio table.** One row per business case in flight: stage, gate it is waiting on, status (red, amber, green with a one-line reason), next milestone and date, owner.
2. **Spend against budget** per case: budgeted, actual to date, forecast to complete. Mark figures *from finance* or *estimated*.
3. **Value.** Summarise the benefits ledger: promised and delivered to date, cash and capacity separate, plus any case whose stop criteria have been met.
4. **Where work is waiting.** For every open item, work out how long it has been waiting and for whom: waiting on a business decision, business testing, business readiness, an approval board, or IT. Total by owner. Use tracker dates where available; otherwise use the `updated:` dates and say so.
5. **Decisions needed.** List what this audience must decide now, each with the artefact and the deadline.
6. **Traceability check.** Flag orphans (features with no case, cases with no objective) and cases with no measurement feature.

## Output

`delivery/reports/YYYY-MM-<audience>.md`: a one-page summary (the five things the audience must know), then the sections above. Plain English; no unexplained abbreviations. If a reporting connector exists, also publish there.

**Done when:** every case in flight appears once, every red or amber has a reason and an owner, and the waiting-time table is totalled by owner.

## Hand-off

Decisions recorded by the audience go back into the Gate record of the artefact concerned.
