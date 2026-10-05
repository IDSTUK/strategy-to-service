---
name: refine
description: Break a committed feature into small stories with testable acceptance criteria, measurement stories and a test approach, checked against a definition of ready. Use for "refine", "write the stories", "acceptance criteria", "is this ready to build", or the first step of building any feature.
---

# Refine

**Development step 1 of 6. Always runs first.** A feature from the quarter plan becomes stories that one engineer, with AI help, can build and verify in a day or two. Stories that are ready to build matter more than they used to: when building is fast, a vague story wastes a whole cycle of build, review and test.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- A committed feature: `delivery/features/F-nnn.md` (or its tracker item), and its parent business case.
- The codebase it touches, if one exists.
- The product owner, for questions.

## Steps

1. **Read up the chain.** Read the feature, its business case (especially the value case and product events) and the parts of the codebase it touches.
2. **Ask before you assume.** List what is unclear, then ask the product owner one question at a time, offering your recommended answer each time. Stop when you could explain every story to a tester.
3. **Slice vertically.** Each story delivers a thin, working path end to end (screen to data), not a layer. Prefer three small stories to one large one.
4. **Write each story:** who, what, why (one line each); acceptance criteria as *Given / When / Then* examples with real values; and the **test seam**, meaning the public interface where a test will check the behaviour.
5. **Add the measurement stories.** For each product event in the value case that this feature touches, a story that emits it, with an acceptance criterion that it arrives in the analytics or data store.
6. **Flag design needs.** If a story introduces a new concept, a new integration, a data model change or anything hard to reverse, mark it `needs design: true`.
7. **Definition of ready**, per story: clear acceptance criteria with examples; test seam named; dependencies resolved or owned; size small; business tester named for acceptance.

## Output

Stories, each with front-matter `parent: F-nnn`: in the tracker if a connector is available (record links in the feature file), otherwise `delivery/stories/S-nnn.md`. Update the feature file with its story list and a ready / not ready summary.

**Done when:** every story meets the definition of ready or lists exactly what is missing and who owns it.

## Next

- Any story marked `needs design` → `design`, then `build-test-first`.
- Otherwise → `build-test-first`.
