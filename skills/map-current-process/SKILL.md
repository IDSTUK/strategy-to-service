---
name: map-current-process
description: Map how an organisation delivers change today, find where work waits, and write a delivery profile the other skills follow. Use for "map our process", "where are we slow", "how do we work today", or before using any other skill in this plugin for the first time.
---

# Map the current process

**Stage 0: start with what you do now.** Before changing anything, describe how change really moves through this organisation today: from an idea or a strategy, through funding, planning, build, testing and release, to someone checking whether it worked. The output is a picture people recognise, the places where work waits, and a profile that makes the other skills fit the organisation rather than the other way round.

Read [the conventions](../../shared/conventions.md) first.

## Input

Any of these. More sources give a truer map; one interview is enough to start.

- Interviews or notes from people at each step: sponsors, finance, product owners, engineers, testers, release and operations staff.
- Process documents: governance handbooks, templates, terms of reference for boards.
- Exports from tracking tools (Jira, Azure DevOps, ServiceNow): item created, status changes and dates. These give real waiting times.
- An existing `delivery/delivery-profile.md`, if this is a refresh.

## Steps

1. **Collect the steps as people describe them**, in their own words and names. Ask each person: what arrives on your desk, what you do with it, who you hand it to, what you wait for, and how long it usually takes. Use their vocabulary for stage names; do not translate into a framework.
2. **For each step, record:** name, owner (role), what comes in, what goes out, tool used, approvals needed, typical working time, typical waiting time, and whether it is business or IT.
3. **Measure waiting from data where you can.** If tracker exports exist, compute time spent in each status, split into *working* (someone is actively on it) and *waiting* (queued for a person, a meeting or an approval). Mark every figure as *measured* or *estimated*.
4. **Find the bottlenecks.** Rank steps by waiting time. Note where the business is waiting on IT and where IT is waiting on the business. Expect the second to grow as development speeds up.
5. **Propose small changes**, at most five, each one step from today, ranked by the waiting time it removes. For each: what changes, who has to agree, how you will know it worked, and which skill in this plugin (if any) helps. Prefer changes a team can try next month without a reorganisation.
6. **Compare with the example profile** (`../../shared/delivery-profile.example.md`). List what this organisation already does that the example also does, and what it does differently. Differences are not faults; record them.
7. **Write the delivery profile** for this organisation, using the structure of the example profile: their cadences, their stages (mapped to the skills where a skill fits), their gates with their real checklists and decision-makers, their roles and their tools. Where they have no equivalent of a gate, leave it out rather than inventing one.

## Output

- `delivery/current-process.md`: the step table, a simple flow (a Mermaid flowchart is fine), the waiting-time ranking, and the proposed changes.
- `delivery/delivery-profile.md`: the profile every other skill reads first.

Both have front-matter as set out in the conventions. Owner of the profile is the person accountable for how delivery runs (often the head of delivery or the CTO).

**Done when:** every step has an owner, an input and an output; every waiting time is marked measured or estimated; and the profile names a decision-maker for each gate it contains.

## Hand-off

Show the person the top three waiting points and the proposed changes, and ask which one they want to try first. The next stage in the example is `strategy-map`; an organisation may start wherever its biggest bottleneck is.
