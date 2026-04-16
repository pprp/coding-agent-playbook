# CLAUDE.md Reference Template (English)

> Repository-level guidance for Claude Code.

## Core Goal

Use Claude Code to produce small, verifiable changes that fit the existing codebase, rather than letting it jump straight into implementation with unclear context.

## Priority Order

1. Give Claude a verification loop  
   Every task should include tests, commands, expected output, screenshots, or reproducible steps whenever possible.

2. Explore first, then plan, then code  
   For medium or large tasks, separate understanding the problem from editing the code.

3. Prompts should be specific and issue-like  
   Provide the goal, relevant files, hard constraints, acceptance criteria, and reference implementations when available.

4. Prefer one well-scoped task at a time  
   Claude performs best on bounded tasks with clear ownership and clear proof of completion.

5. Follow existing repository patterns  
   Reuse local conventions for code structure, testing, naming, and error handling instead of rewriting nearby code for stylistic consistency.

6. Separate cleanup from behavior change  
   If you need both, protect behavior first and keep cleanup as a distinct, reviewable step.

7. Control context density  
   Include only the files, logs, and notes that materially help the task. Excess context lowers reliability.

8. Start with one session, parallelize only when useful  
   Use a single Claude session for the main thread of work. Add parallel sessions only for naturally separable review, testing, or migration lanes.

9. Keep clear role separation in parallel work  
   Implementation, testing, and review are more reliable when they do not all happen inside the same context.

10. Tighten permissions for high-risk actions  
   Destructive, sensitive, remote, or expensive actions should run with explicit guardrails and tighter permission boundaries.

## Default Claude Code Workflow

1. Explore  
   Read the relevant code, tests, config, docs, and errors before deciding what to change.

2. Plan  
   Write short steps describing the intended change, verification method, and major risks.

3. Implement  
   Start with the smallest change that can work. Do not refactor unrelated code unless the task explicitly requires it.

4. Verify  
   Run checks that match the change: tests, lint, typecheck, build, screenshot comparisons, or manual repro steps.

5. Report  
   Summarize the result, the evidence, the remaining risks, and any points that still require human judgment.

## Concrete Instructions for Claude

- Use a planning-oriented workflow for medium and large tasks instead of jumping directly to code.
- If the request is ambiguous, surface the ambiguity before going deeper, but proceed automatically on low-risk and reversible next steps.
- Do not add speculative abstractions, config knobs, or dependencies for hypothetical future needs.
- Do not make drive-by edits to unrelated files, formatting, comments, or naming.
- For cleanup or refactor work, add coverage or other behavioral evidence before simplifying structure.
- Keep explanations short and make verification concrete.

## Information That Helps In Prompts

- Background: why the change is needed
- Goal: the intended outcome
- Scope: what Claude may edit
- Boundaries: what must not change
- Acceptance: how completion will be judged
- References: similar code, issues, docs, screenshots

## Recommended Final Response Shape

- Result: what was completed
- Verification: what was run and what happened
- Risks: what remains uncertain or needs manual confirmation

## One-line Principle

Do not let Claude write a lot of code under vague instructions; put it inside clear constraints and have it progress through exploration, planning, minimal edits, and verification.
