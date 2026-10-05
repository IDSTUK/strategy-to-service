---
id: PROFILE
title: Example delivery profile (Strategy to Service)
owner: Replace with the person who owns your delivery process
status: example
updated: 2026-10-05
---

# Example delivery profile: Strategy to Service

This is **one example** of how a mid-to-large IT department might run change, from the three-year plan to measured benefits. It is the fallback the skills use when an organisation has not written its own profile. Run `map-current-process` to write a profile that describes how *your* organisation works today; change this one only as far as your teams are ready to.

## Cadences

| Rhythm | Length | What happens |
|---|---|---|
| Strategy | 3 years, refreshed yearly | Objectives and the measures that show progress |
| Budget | Yearly, re-forecast quarterly | Business cases funded, spend tracked |
| Quarter plan | 13 weeks | Features committed across teams, dependencies agreed |
| Sprint | 2 weeks | Stories built, reviewed and verified |
| Release | Every 2 weeks, or on demand behind a release switch | Release pack approved, switch turned on |
| Benefits checkpoints | 2, 6 and 12 weeks after release | Continue, expand or stop |

## Stages

| # | Stage | Skill | Input | Output |
|---|---|---|---|---|
| 0 | Understand today | map-current-process | Interviews, documents, tracker exports | current-process.md, delivery-profile.md |
| 1 | Strategy | strategy-map | Strategy and annual plan material | strategy-map.md |
| 2 | Invest | business-case | strategy-map.md + an idea | cases/BC-nnn.md |
| 3 | Plan the quarter | quarter-plan | Approved business cases + team capacity | plans/YYYY-Qn.md + features/F-nnn.md |
| 4 | Build | development skills (see below) | Committed features | releases/R-nnn.md (release candidate) |
| 5 | Release | release-ready | Release candidate | releases/R-nnn.md (release pack) |
| 6 | Measure | benefits-review | Release pack + live readings | reviews/BR-nnn.md + benefits-ledger.md |
| any | Report | status-report | Everything in delivery/ | reports/YYYY-MM-status.md |

Development, in order: refine → design (only when needed) → build-test-first → review → verify → release-candidate. Use diagnose whenever a bug or incident appears and team-retro at the end of each sprint.

## Gates

### Gate 1: Fund
- **Decided by:** Investment board (chair: the CFO's delegate)
- **Artefact:** business case
- **Checklist:**
  - [ ] Linked to a strategic objective (parent: OBJ-nn)
  - [ ] Problem stated with evidence, not just a solution
  - [ ] At least two options, including "do nothing", each costed
  - [ ] Full cost: build, business time, running cost, AI and tooling cost
  - [ ] Value type chosen: revenue, cost, risk, mandatory or enabler
  - [ ] Main measure named, with a **baseline that has been measured** and its data source
  - [ ] Target and date for the main measure
  - [ ] Early signal (leading indicator) that should move within weeks
  - [ ] Conversion to money agreed with the finance business partner (named), split into cash and capacity
  - [ ] Counter-measure that must not get worse
  - [ ] Stop criteria agreed in advance
  - [ ] Named benefit owner in the business (not in IT)

### Gate 2: Commit
- **Decided by:** Business owners and the delivery lead, at quarterly planning
- **Artefact:** quarter plan
- **Checklist:**
  - [ ] Every feature traces to an approved business case
  - [ ] Every business case in the plan has at least one measurement feature
  - [ ] Cross-team dependencies listed, each with an owner and a date
  - [ ] Planned work fits capacity, with at least 20% kept free for run work and surprises
  - [ ] Business time booked: product owner, subject experts, testers, named and in calendars
  - [ ] Risks listed with owners

### Gate 3: Release
- **Decided by:** Release manager (or change board for high-risk changes)
- **Artefact:** release pack
- **Checklist:**
  - [ ] Every story in the release has passed review and verify
  - [ ] Business acceptance testing done, signed off by the named business tester
  - [ ] Measurement confirmed working: events or data are arriving for the main measure and early signal
  - [ ] Release switch and comparison group configured (or a stated reason why not)
  - [ ] Rollback plan written and tested
  - [ ] Training, communications and support notes ready
  - [ ] Change request raised with risk rating

### Gate 4: Benefits
- **Decided by:** Benefit owner, reported to the investment board
- **Artefact:** benefits review
- **Checklist:**
  - [ ] Reading taken at the checkpoint from the agreed data source
  - [ ] Compared against baseline, target and comparison group
  - [ ] Counter-measure checked
  - [ ] Recommendation made: continue, expand, change or stop
  - [ ] Benefits ledger updated

## Roles

| Role | Typical job title | Uses |
|---|---|---|
| Sponsor | Business director | business-case, benefits-review |
| Benefit owner | Business manager | business-case, release-ready, benefits-review |
| Finance business partner | Finance | business-case (money conversion), status-report |
| Portfolio office | PMO | quarter-plan, status-report |
| Product owner | Product manager or business analyst | quarter-plan, refine, release-ready |
| Architect | Solution or enterprise architect | strategy-map, design |
| Delivery lead | Delivery or engineering manager | quarter-plan, team-retro, status-report |
| Engineer | Developer | refine, design, build-test-first, review, diagnose |
| Tester | QA or business tester | verify, release-ready |
| Release manager | Release or change manager | release-candidate, release-ready |
| Service owner | Operations | diagnose, benefits-review |

## Tools

Replace each entry with what you use. Skills write to `delivery/` files and, where a connector is available, to the named tool.

| Purpose | Tool |
|---|---|
| Strategy and documents | none (files only) |
| Business cases and portfolio | none (files only) |
| Features and stories | none (files only) |
| Code and reviews | git |
| Change requests | none (files only) |
| Release switches | none |
| Analytics and measures | none |
| Reporting | none (markdown reports) |
