# Coding Agent Playbook

Sharper bilingual templates for `AGENTS.md` and `CLAUDE.md`.

一个面向 coding agent 时代的文档模板仓库，帮助你把“随手写的提示词”升级成“真正能约束执行行为的仓库操作文档”。

## Why This Repo Exists

Most repository guidance for agents is too vague to change behavior. It sounds reasonable, but it does not reliably improve execution when tasks get messy.

This repo focuses on the opposite:

- tighter instructions
- clearer workflow
- stronger verification pressure
- smaller, more reviewable changes
- more explicit boundaries around risk

核心目标很简单：让 agent 在真实项目里更稳定、更克制、更容易 review，而不是在模糊上下文下“聪明地写很多代码”。

## What's Inside

- `AGENTS_en.md`
  English reference template for writing a repository-level `AGENTS.md`.
- `AGENTS_zh.md`
  `AGENTS.md` 中文参考模板。
- `CLAUDE_en.md`
  English reference template tailored for `CLAUDE.md` and Claude Code workflows.
- `CLAUDE_zh.md`
  `CLAUDE.md` 中文参考模板。

## Design Direction

These documents are written in a style inspired by skill files such as Anthropic's `frontend-design/SKILL.md`.

That means the templates favor:

- short, high-signal sections
- direct operational language
- explicit priority and workflow guidance
- strong boundaries like `CRITICAL`, `IMPORTANT`, `NEVER`, and `ALWAYS`
- instructions that shape behavior under pressure, not just philosophy in calm conditions

This repo is not trying to copy the content of any skill file. It is borrowing the clarity, pacing, and decisiveness of that style.

## When To Use These Templates

Use this repo if you want to:

- create a serious `AGENTS.md` for Codex, Claude Code, or similar agents
- standardize how agents should explore, plan, implement, verify, and report
- reduce drive-by edits, speculative abstractions, and vague final responses
- give your team a cleaner starting point for repo-specific agent instructions

## AGENTS.md vs CLAUDE.md

- Use `AGENTS.md` when you want a tool-agnostic operating contract for coding agents in general.
- Use `CLAUDE.md` when you want Claude Code specific guidance, especially around prompt shape, context control, and execution workflow.
- Use both when your repository is touched by multiple agent tools and you want a shared baseline plus tool-specific tuning.

## Quick Start

1. Copy the template that matches your tool and language.
2. Replace generic advice with repository-specific commands and constraints.
3. Add real verification steps such as `test`, `lint`, `typecheck`, `build`, or screenshot review.
4. Mark risky actions clearly, especially deletes, migrations, deployments, remote writes, and sensitive file changes.
5. Remove any rule that sounds nice but would not actually change a decision during execution.

## Customization Checklist

Before using a template in a real project, add:

- editable and non-editable paths
- standard verification commands
- testing expectations for bugfixes, cleanup, and refactor work
- final response requirements
- permission and escalation rules for risky actions
- repository-specific conventions for naming, structure, and reuse

## Writing Principles Behind These Templates

The templates in this repo assume:

- agents should explore before editing
- plans should be visible for non-trivial work
- cleanup should not happen without protecting behavior first
- existing repository patterns should be reused before new abstractions are introduced
- verification is part of the task, not an optional extra

## Language Notes

The English and Chinese files are aligned in intent, but they are written to read naturally in each language rather than as literal line-by-line translations.

## Suggested Repo Structure

```text
.
├── AGENTS_en.md
├── AGENTS_zh.md
├── CLAUDE_en.md
├── CLAUDE_zh.md
└── README.md
```

## How To Adapt This Repo For Your Team

Start small. Do not turn your guidance files into long policy documents.

Keep only the rules that meaningfully improve:

- execution quality
- verification discipline
- reviewability
- safety around risky actions

If a sentence would not change what the agent actually does, it probably does not belong in your final version.
