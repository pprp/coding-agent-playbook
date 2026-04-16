# AGENTS.md Reference Template (English)

> For Codex, Codex CLI, and other coding agents that consume `AGENTS.md`.

## Purpose

This file is not meant to make the agent more creative. It is meant to make the agent more reliable at delivering code changes that are verifiable, reviewable, and reversible.

## Priority Order

1. Verification first  
   Define what proves success before writing code. Prefer executable checks such as tests, lint, typecheck, build steps, screenshots, or reproducible steps.

2. Explore, then plan, then code  
   For anything beyond a trivial edit, read the relevant code, find the boundaries, and understand dependencies before changing behavior.

3. Clear, structured, non-conflicting instructions  
   Tasks should read like a strong issue: background, goal, constraints, scope, acceptance criteria, and references.

4. Small scope, incremental progress  
   Split large tasks into steps that can each be independently verified.

5. Minimal changes, respect existing patterns  
   Reuse local conventions for structure, naming, testing, and error handling whenever possible.

6. Protect behavior before cleanup  
   For cleanup, refactor, or deslop work, lock behavior first with regression tests or other evidence, then simplify structure.

7. Keep context clean  
   Carry only the context that materially helps the current task. Avoid dragging in long, stale, or unrelated history.

8. Default to one agent, parallelize only when useful  
   Start with a single agent. Add parallel agents only when work is naturally separable and the coordination overhead is worth it.

9. Separate implementation from review  
   When practical, let one agent write code and another agent review or verify it independently.

10. Add guardrails around high-risk actions  
   Destructive, irreversible, sensitive, or expensive actions should run with tighter permissions and explicit risk awareness.

## Default Execution Protocol

1. Explore  
   Read the relevant code, tests, configuration, and docs before choosing an approach.

2. Plan  
   State the intended steps, how success will be verified, and any notable risks.

3. Implement  
   Prefer the smallest viable change. Do not refactor unrelated code unless the task explicitly calls for it.

4. Verify  
   Run checks that match the size and risk of the change. Lightweight checks for small edits, broader checks for cross-cutting changes.

5. Report  
   Summarize what changed, how it was verified, and what risks or gaps remain.

## Constraints

- Do not add speculative abstractions, extension points, or dependencies for hypothetical future needs.
- Do not modify unrelated files, formatting, naming, or comments as drive-by cleanup.
- Do not delete logic you do not understand. Explain its role first, then decide whether it should change.
- Do not optimize for elegance over correctness, stability, and reviewability.
- If behavior is not already protected, add regression coverage before cleanup work.
- Reuse existing utilities, fixtures, error handling patterns, and configuration conventions whenever possible.

## Recommended Task Input Format

Provide the following when possible:

- Goal: what problem should be solved
- Scope: which files, modules, or surfaces may change
- Constraints: what must not change
- Acceptance: what counts as done
- References: similar code, docs, issues, or examples

## Recommended Delivery Format

- Result: what was completed
- Verification: what checks were run and what happened
- Risks: remaining gaps, follow-ups, or manual checks

## One-line Principle

Keep the agent inside clear boundaries and have it complete work through small, minimal, verifiable changes instead of having it generate lots of code under vague goals.
