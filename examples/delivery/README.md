# Worked example: Brightwater Utilities

A fictional water company, used to show one business case travelling the whole chain. Every number here is invented for illustration.

| File | Written by | Stage |
|---|---|---|
| strategy-map.md | strategy-map | 1 Strategy |
| cases/BC-001.md | business-case | 2 Invest (Fund gate) |
| plans/2026-Q4.md | quarter-plan | 3 Plan (Commit gate) |
| features/F-001.md, F-002.md | quarter-plan | 3 Plan |
| releases/R-001.md | release-candidate, then release-ready | 4 Build, 5 Release (Release gate) |
| reviews/BR-001-6w.md | benefits-review | 6 Measure (Benefits gate) |
| benefits-ledger.md | benefits-review | 6 Measure |

Try it: copy this folder into a scratch repository as `delivery/`, delete the baseline row from `cases/BC-001.md`, and ask the `business-case` skill to check the case. It should refuse to mark it ready.
