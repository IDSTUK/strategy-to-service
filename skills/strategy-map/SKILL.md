---
name: strategy-map
description: Turn a three-year or annual plan into measurable strategic objectives that business cases can link to. Use for "strategy map", "turn our strategy into objectives", or when a business case has no objective to serve.
---

# Strategy map

**Stage 1 of the example lifecycle.** Strategy documents are usually written for a board, not for the people deciding what to build. This skill turns them into a short list of objectives, each with a measure, a baseline and a target, so every later business case can say which objective it serves and by how much.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md) if none exists).

## Input

The raw material, in any form: a strategy deck, an annual plan, board papers, a CEO's letter, a budget summary, or notes from a conversation with the executive team. This is the only skill in the chain that starts from unstructured material.

## Steps

1. **Pull out the intended outcomes.** Separate outcomes ("cut cost to serve by 15%") from activities ("move to the cloud"). Activities become capability gaps in step 4, not objectives.
2. **Write each objective** as one sentence a business reader would agree with. Aim for three to seven. More than seven means the strategy has not chosen yet; say so.
3. **Give each objective a measure:** what number shows progress, where that number comes from today, its **baseline** (with date and source, or "not measured yet" as an open question with an owner), and the **target** with a date.
4. **List capability gaps:** what the organisation cannot do today that it would need to reach each objective (skills, systems, data, processes). Link each gap to its objectives.
5. **Note constraints** the strategy sets: budget envelope, regulatory deadlines, platforms that must be used or retired.
6. **Check:** every objective has a measure and a named executive owner; every baseline is measured or carries an open question.

## Output

`delivery/strategy-map.md`, with front-matter (`id: STRATEGY`, owner is the executive who owns the strategy), containing:

- A table of objectives: `OBJ-nn`, objective, measure, baseline (value, date, source), target (value, date), executive owner.
- Capability gaps, each linked to objectives.
- Constraints.
- Open questions, each with an owner.

**Done when:** every objective has an id, a measure, a baseline or an owned open question, a target and an owner.

## Hand-off

Business cases (`business-case`) now link to an `OBJ-nn` as their parent. Tell the person: "Ideas can now be written up as business cases against these objectives."
