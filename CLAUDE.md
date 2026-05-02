# Project summary

This project is a web app for visualizing the recruitment timeline for Polish high schools.

# Agent behavioral guidelines

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

---

**These guidelines are working if:** fewer unnecessary changes in diffs, fewer rewrites due to overcomplication, and clarifying questions come before implementation rather than after mistakes.

# Discussions Before Coding

Don't start coding until explicitly told to. For any non-trivial task, discuss first — surface assumptions, alternatives, and tradeoffs before touching code.

- Be concise. No elaborate explanations.
- Don't agree reflexively. Push back, question the approach, show pros and cons.
- Default to the simpler solution. Complexity needs justification.

# Implementation Discipline

Implement in small, verifiable steps. Each step should be small enough that you can run the tests, see them pass, and move on with confidence. Don't stack multiple unverified steps on top of each other.

- **One step at a time.** Make the smallest coherent change, run the tests, then continue. If tests fail, fix them before moving on — never advance with a red suite.
- **Stop on surprise.** If you hit territory the plan didn't cover — a missing abstraction, an unclear interface, a question the plan doesn't answer — stop and tell the user. Don't invent your way through.
- **Stop on creep.** If the change is becoming larger or more tangled than the plan implied, stop and tell the user. The plan probably has a gap.
- **Stop on doubt.** If you find yourself guessing what the user wants, stop and ask.

These stops are not failures — they're signals that the design conversation needs another round before more code is written. Surfacing them early is cheaper than unwinding a half-built implementation later.
