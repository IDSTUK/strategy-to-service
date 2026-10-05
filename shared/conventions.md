# Delivery conventions

Every skill in this plugin reads and writes the same kind of file, in the same place, so the output of one skill is the input of the next. This file is the single source of those rules.

## Where things live

All artefacts live in a `delivery/` folder at the root of the working repository (or a dedicated "delivery" repository for business teams who have no code repo). Git is the audit trail: who changed what, when, and why.

```
delivery/
  delivery-profile.md        # this organisation's stages, gates, checklists and tools (see below)
  current-process.md         # from map-current-process
  strategy-map.md            # from strategy-map
  cases/BC-001.md            # from business-case
  plans/2026-Q4.md           # from quarter-plan
  features/F-001.md          # from quarter-plan, refined by refine
  stories/S-001.md           # from refine (only when no tracker is connected)
  decisions/D-001.md         # from design
  releases/R-001.md          # from release-candidate, completed by release-ready
  reviews/BR-001-6w.md       # from benefits-review
  benefits-ledger.md         # from benefits-review
  reports/2026-10-status.md  # from status-report
  retros/2026-10-14.md       # from team-retro
```

If the folder does not exist, create it. If the organisation keeps an artefact somewhere else (Confluence, Jira, SharePoint), the profile says so and the file in `delivery/` holds a link plus the front-matter.

## Front-matter

Every artefact starts with YAML front-matter. These fields are required:

```yaml
---
id: BC-001                 # prefix from the table below, then a number
title: Self-service address change
parent: OBJ-02             # the id this artefact serves; empty only for strategy objectives
owner: Priya Shah          # a named person, never a team or "TBC"
status: draft              # draft | ready | approved | rejected | done | stopped
gate: fund                 # the gate this artefact is waiting on, or none
updated: 2026-10-05
---
```

| Prefix | Artefact | Written by |
|---|---|---|
| OBJ | Strategic objective (inside strategy-map.md) | strategy-map |
| BC | Business case | business-case |
| F | Feature | quarter-plan |
| S | Story | refine |
| D | Decision record | design |
| R | Release | release-candidate, release-ready |
| BR | Benefits review | benefits-review |

**Traceability:** every artefact names its parent, so any line of code can be followed up to the objective it serves, and any objective down to what was built for it. A story with no feature, or a feature with no business case, is an orphan: flag it rather than proceed.

## Gates

A gate is a decision point with a checklist and a named decision-maker.

- The skill **checks** every checklist item and lists any that are missing.
- The skill sets `status: ready` only when every item passes. Otherwise it stays `draft` and the skill says exactly what is missing and who could supply it.
- The skill **never** sets `status: approved`. Approval is recorded by the named decision-maker (or by the skill on their explicit instruction in this session, quoting who approved and when), in a `## Gate record` section at the bottom of the artefact:

```markdown
## Gate record
- Gate: fund
- Decision: approved | rejected | approved with conditions
- Decided by: Sam Okafor, Investment Board
- Date: 2026-10-12
- Conditions: Re-baseline call volumes after the November price change.
```

The gate names, checklists and decision-makers come from the delivery profile. The example profile's gates are Fund, Commit, Release and Benefits.

## Tools and connectors

The skills are tool-agnostic. Before writing an artefact, check the profile's `tools` section and whether a matching connector is available in this session:

- **Connector available** (for example Jira, Azure DevOps, ServiceNow, Confluence, an analytics tool): write the `delivery/` file and also create or update the item in that tool, then record its key or URL in the front-matter as `link:`.
- **No connector:** write the `delivery/` file only and say which tool the item should be copied into.

Never block on a missing connector. A file in git is always enough to carry on.

## The delivery profile

`delivery/delivery-profile.md` describes how *this* organisation works: its stage names, gates, checklists, decision-makers, cadences and tools. It is written by `map-current-process` and edited by people.

Every skill reads it first. Where it is silent, fall back to the example profile shipped with the plugin (`shared/delivery-profile.example.md`). Where it differs from the example, the organisation's profile wins: these skills support the way a team works today and help it improve one step at a time.

## Writing style for artefacts

Plain English for a business reader. Short sentences. Name people, numbers and dates. Write "we don't know yet" rather than guessing, and add it to an `## Open questions` section with an owner.
