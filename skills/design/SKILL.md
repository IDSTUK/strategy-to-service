---
name: design
description: Agree domain terms, record significant decisions and design module interfaces before building. Use only when a story is marked "needs design", adds a new concept or integration, changes the data model, or is hard to reverse. Also for "decision record", "architecture decision", or "where should this live".
---

# Design

**Development step 2 of 6. Only when needed.** Most stories go straight from `refine` to `build-test-first`. Use this step when a story introduces something new or hard to undo. It produces the two things architecture boards ask for and AI-assisted teams need most: a shared vocabulary, and decisions written down with their reasons.

Read [the conventions](../../shared/conventions.md) and the delivery profile (`delivery/delivery-profile.md`, or [the example](../../shared/delivery-profile.example.md)).

## Input

- Stories marked `needs design: true`, with their feature and business case.
- The codebase, and any existing glossary (`CONTEXT.md` or similar) and decision records (`delivery/decisions/`).
- The organisation's architecture standards, if the profile names them.

## Steps

1. **Terms.** List the business concepts the story touches. For each, one agreed name and a one-line definition, using the business's words. Add new or changed terms to the project glossary (`CONTEXT.md`, created if missing). Code should use these names.
2. **Options.** For the significant choice, set out two or three options with their trade-offs: cost to build, cost to change later, risk, fit with standards.
3. **Interface first.** Where new code is needed, design the module's public interface before its insides: a small interface hiding a lot of behaviour is easier to test, change and explain. Name the seams where tests will sit. Sketch it as signatures or a short example of use.
4. **Ask the people who decide.** Present the options and your recommendation to the engineer or architect who owns the area. Record their decision.
5. **Write the decision record.**

## Output

- `delivery/decisions/D-nnn.md` with front-matter (`parent:` the story or feature), sections: context, options considered, decision, consequences, who decided and when.
- Updated `CONTEXT.md` glossary.
- The story updated with the agreed interface and seams.

**Done when:** every new term has a definition, the decision has a named decider, and every story it covers names its test seams.

## Next

`build-test-first`.
