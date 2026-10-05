# Strategy to Service

**A worked example of AI-assisted delivery, from strategy to measured benefits.** It is one example, not a prescription. Start with what you do now.

AI makes development faster. Soon the slow part of change is everything around development: deciding what to build, funding it, testing it with the business, releasing it, and finding out whether it worked. These skills show how AI can help with those business stages as well as with the code, and how value can be defined before work starts and measured after release.

Read the full write-up, with the diagram: <https://idst.uk/strategy-to-service/>

## Install

In Claude Code:

```
/plugin marketplace add IDSTUK/strategy-to-service
/plugin install strategy-to-service@idst
```

Skills are then available as `/strategy-to-service:<skill>`, and Claude will also pick them up when your request matches.

## Start with what you do now

Run `map-current-process` first. It maps how change moves through your organisation today, shows where work waits, and writes `delivery/delivery-profile.md`. Every other skill reads that profile first, so they follow your stage names, gates and tools. Without a profile, they fall back to [the example profile](shared/delivery-profile.example.md).

## The skills

**Business stages: one skill each. Each takes the previous stage's output and hands its own output on.**

| Stage | Skill | Takes | Gives | Gate |
|---|---|---|---|---|
| 0 Understand today | `map-current-process` | Interviews, documents, tracker exports | Current process, delivery profile | |
| 1 Strategy | `strategy-map` | Strategy and annual plan material | Objectives with measures, baselines, targets | |
| 2 Invest | `business-case` | Strategy map + an idea | Business case with a measurable value case | Fund |
| 3 Plan the quarter | `quarter-plan` | Approved cases + capacity | Quarter plan + feature tickets | Commit |
| 4 Build | development skills below | Features | Release candidate | |
| 5 Release | `release-ready` | Release candidate | Release pack | Release |
| 6 Measure | `benefits-review` | Release + live readings | Benefits review, benefits ledger | Benefits |
| Any time | `status-report` | Everything in `delivery/` | Steering pack | |

**Development, in this order:**

1. `refine`: feature to stories with examples and measurement stories. *Always.*
2. `design`: terms, decisions, interfaces. *Only when a story needs it.*
3. `build-test-first`: one failing test, then the code. *Always.*
4. `review`: standards, match to the story and business case, security. *Always.*
5. `verify`: run the real system against the examples. *Always.*
6. `release-candidate`: merge, version, evidence, rollback; stops before production. *Always.*

Also `diagnose` whenever something breaks, and `team-retro` at the end of each sprint. Not sure what's next? `delivery-guide` reads your `delivery/` folder and tells you.

## How it fits together

- **Files first, tools optional.** Every skill writes Markdown with front-matter to a `delivery/` folder, so git gives you the audit trail. Where a connector is available (Jira, Azure DevOps, ServiceNow, Confluence, analytics), the skill also writes there. See [the conventions](shared/conventions.md).
- **Traceable.** Every artefact names its parent: objective, business case, feature, story, release, benefits review.
- **Gates are checklists the skills enforce and people decide.** A skill will not mark a business case ready without a measured baseline, a named benefit owner and stop criteria. It never records an approval on its own.
- **Value is measured, not assumed.** Measurement features are planned with the work, confirmed before release, and read at 2, 6 and 12 weeks. The benefits ledger puts each sponsor's promised and delivered value side by side.

[`examples/delivery/`](examples/delivery/) follows one fictional business case through every stage.

## Credits

The development skills borrow ideas from [Matt Pocock's skills](https://github.com/mattpocock/skills) (test-first at agreed seams, two-axis review, deep modules, grilling) and [gstack](https://github.com/garrytan/gstack) (structured plan reviews, real-browser QA, security review), rewritten to stand alone and to fit organisations with separate roles and change control.

MIT licence. Made by [IDST](https://idst.uk), who also run training on AI-assisted delivery for teams.
