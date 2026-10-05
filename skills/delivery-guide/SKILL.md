---
name: delivery-guide
description: Say which Strategy to Service skill to use next, by reading the delivery folder and finding what is waiting at which stage. Use for "what's next", "which skill should I use", "where are we", or "how does this plugin work".
---

# Delivery guide

Explains the skills in this plugin and, given the current state of `delivery/`, recommends the next one to run.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)). If the organisation's profile changes the stages, follow it.

## The skills, in order

| Step | Skill | Use when | Takes | Gives |
|---|---|---|---|---|
| 0 | map-current-process | First, and whenever the way of working changes | Interviews, documents, tracker exports | current-process.md, delivery-profile.md |
| 1 | strategy-map | Strategy or annual plan changes | Strategy material | strategy-map.md |
| 2 | business-case | An idea needs funding | Strategy map + idea | BC-nnn (Fund gate) |
| 3 | quarter-plan | Quarterly planning | Approved cases + capacity | Plan + F-nnn (Commit gate) |
| 4.1 | refine | A committed feature is next | F-nnn | Stories, ready to build |
| 4.2 | design | Only if a story needs design | Stories | D-nnn, glossary, interfaces |
| 4.3 | build-test-first | A story is ready | Story | Tested code |
| 4.4 | review | Code is ready to merge | Branch | Verdict |
| 4.5 | verify | Review passed | Running system | Evidence |
| 4.6 | release-candidate | Stories verified | Verified stories | R-nnn (candidate) |
| 5 | release-ready | Candidate exists | R-nnn | Release pack (Release gate) |
| 6 | benefits-review | 2, 6, 12 weeks after switch-on | Release + readings | BR-nnn, ledger (Benefits gate) |
| any | diagnose | Something is broken or slow | Symptom | Root cause + fix |
| any | team-retro | End of sprint | Sprint data | Experiments |
| any | status-report | Steering meeting due | delivery/ | Status pack |

## Steps

1. If `delivery/` does not exist or has no profile, recommend `map-current-process`.
2. Otherwise, list items by status and gate: cases in draft or awaiting Fund, approved cases not yet planned, features not refined, stories in progress, releases awaiting the Release gate, releases due a benefits checkpoint (count weeks from switch-on).
3. Recommend the single next skill, with the artefact it should start from and why. Mention anything overdue, such as a benefits checkpoint that has passed or a gate waiting longer than the profile allows.

## Output

A short answer in the conversation: where things stand, the recommended next skill and its input. Nothing is written to disk.
