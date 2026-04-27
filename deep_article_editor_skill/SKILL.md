---
name: deep-article-editor
version: 0.1.0
description: Use this skill when the user asks to polish, rewrite, restructure, or upgrade a Chinese article into a more engaging deep-analysis essay, especially for business, technology, industry, macro, AI, policy, or trend commentary. Do not use it for pure translation, news briefs, literary fiction, legal drafting, or strictly academic peer-review unless the user explicitly asks for this style.
---

# Deep Article Editor Skill

## Purpose
Turn an ordinary Chinese article from “information delivery” into “cognitive progression”: the reader should be pulled in by a tension, guided through progressively deeper explanations, and leave with a memorable framework or higher-level conclusion.

This skill is based on a repeatable editorial pattern:

1. Start with a familiar misconception, tension, or counterintuitive question.
2. Reframe the topic from a small concept/event into a larger structural change.
3. Use concrete analogies to make abstract ideas easy to grasp.
4. Build a clear progression: phenomenon → misconception → correction → essence → mechanism → trend → impact → elevated conclusion.
5. Add memorable models, such as “short term / medium term / long term,” “cost floor / value ceiling,” “two critical thresholds,” or “from tool use to system reconstruction.”
6. End by elevating the topic into a broader shift, but do not overstate unproven claims.

## Trigger phrases
Use this skill when the user says things like:

- “帮我润色这篇文章”
- “把这篇文章改得更有深度/更引人入胜”
- “按照之前Token那篇文章的写法优化”
- “重构文章结构”
- “改成深度商业评论/产业分析/公众号长文”
- “帮我做标题、导语、小标题和金句”
- “让文章更有认知冲突和趋势感”

## Inputs to request only when missing and truly necessary
If the article is already provided, proceed without asking. Infer sensible defaults when possible.

Useful optional inputs:

- Target reader: executives, investors, general readers, technical readers, policy readers, students.
- Use case: WeChat article, op-ed, internal memo, speech draft, report preface, video script.
- Tone: rational and restrained, sharper commentary, more accessible, more academic, more commercial.
- Revision strength: light polish, medium restructure, full rewrite.
- Fact policy: no new facts; allow suggested cases only with labels; allow researched additions if browsing/tools are available.
- Length target: preserve length, compress, expand.

Default assumptions when absent:

- Target reader: educated general/business reader.
- Use case: Chinese long-form article.
- Tone: clear, restrained, analytical, engaging.
- Revision strength: medium restructure.
- Fact policy: do not invent facts; mark missing evidence.

## Non-negotiable guardrails

1. Preserve the user’s core position unless they explicitly ask for a different argument.
2. Do not fabricate data, cases, quotes, dates, institutions, or expert opinions.
3. If a claim is unsupported, mark it as `【需补充证据】`, `【建议补案例】`, or `【预测性判断，需谨慎表述】`.
4. Distinguish facts from interpretation and forecasts.
5. Do not use empty hype, vague adjectives, or exaggerated “epoch-making” language unless the article has evidence to support it.
6. Do not turn every article into a sensational “爆款.” The goal is deep engagement, not clickbait.
7. Keep Chinese expression natural, precise, and rhythmical.
8. If the article contains citations, preserve them unless the user asks to change citation style.

## Core editing workflow

### Step 1: Diagnose the article
Identify:

- The real core question.
- The strongest existing insight.
- The weakest part of the argument.
- The best tension or misconception to amplify.
- The likely reader resistance: “Why should I care?” “Is this true?” “What does this change?”

### Step 2: Rebuild the cognitive arc
Do not merely polish sentences. Rebuild the reader’s path:

1. Phenomenon: What is happening?
2. Misconception: How do people usually misunderstand it?
3. Correction: Why is that view incomplete?
4. Essence: What is it really?
5. Mechanism: How does it work? What are the cost, supply, demand, incentives, constraints, or feedback loops?
6. Trend: How may it evolve over time?
7. Impact: Who benefits, who loses, who controls standards, interfaces, pricing, or distribution?
8. Elevation: What larger shift does this reveal?

### Step 3: Strengthen the opening
Prefer openings that create a cognitive hook:

- “很多人以为……但真正的问题不是……而是……”
- “表面上看，这是……更深层看，它意味着……”
- “过去我们讨论……今天真正发生变化的是……”
- “如果只把它理解为……就会错过它真正重塑的东西。”

Opening requirements:

- Avoid slow background exposition.
- Reveal the tension within the first 1–3 paragraphs.
- Tell the reader why this matters now.
- Do not overpromise beyond the article’s evidence.

### Step 4: Convert loose ideas into models
Where possible, turn complex material into compact frameworks:

- Time model: “短期看A，中期看B，长期看C。”
- Layer model: “底部由成本托住，顶部由价值拉开。”
- Transition model: “从A到B，再到C。”
- Threshold model: “真正的爆发取决于两个临界点。”
- Flywheel model: “价格下降 → 使用扩散 → 认知普及 → 需求放大 → 成本继续下降。”

Models must clarify the logic. Do not add models that are decorative or forced.

### Step 5: Add analogies carefully
Use analogies to lower cognitive friction. Good analogies should map one difficult idea to one familiar structure.

Useful analogy types:

- Infrastructure: electricity, water, roads, cloud computing.
- Market pricing: subscription, prepaid card, consultant billing, utility meter.
- Organizational change: from tool use to workflow automation to system reconstruction.

Avoid analogies when they distort the concept or imply a false equivalence.

### Step 6: Add power and incentive questions
For business, technology, industry, policy, or macro articles, add the deeper questions:

- Who defines the standard?
- Who controls the interface or distribution entrance?
- Who owns the pricing anchor?
- Who bears the cost?
- Who captures the surplus?
- Who is commoditized?
- Who gains infrastructure-level power?

This turns an explanatory article into a structural analysis.

### Step 7: Rewrite headings
Headings should carry judgments, not just labels.

Weak:

- “行业背景”
- “市场分析”
- “未来趋势”

Stronger:

- “真正变化的不是技术，而是使用方式”
- “成本只是底线，能力才决定溢价”
- “价格下降未必压缩市场，反而可能点燃需求”
- “谁控制入口，谁就掌握新秩序的话语权”

### Step 8: Strengthen the ending
The ending should not merely summarize. It should elevate.

Good ending pattern:

- “这件事不是……而是……”
- “它真正改变的，不是……而是……”
- “我们正在从……走向……”
- “它不是答案，而是一个信号。”

The final paragraph should leave the reader with one durable thesis.

## Default output format
Unless the user asks for a full rewrite only, output in this sequence:

1. `【总体诊断】`
   - 3–6 sentences: main issue, main potential, best editorial direction.

2. `【建议标题】`
   - 3–5 titles.
   - Briefly label each: rational, sharp, commercial, public-facing, internal memo, etc.

3. `【重写后的导语】`
   - 1 strong version by default.
   - If useful, provide two styles: “强冲突型” and “理性分析型.”

4. `【结构优化建议】`
   - Proposed section order.
   - Explain what each section should accomplish.

5. `【逐段/完整润色正文】`
   - Respect the requested revision strength.
   - Preserve facts and core stance.
   - Mark unsupported claims.

6. `【可增强的核心判断】`
   - 5–10 memorable sentences that fit the article.

7. `【风险提示】`
   - Evidence gaps, overstatements, concept ambiguity, unsupported forecasts, or possible reader objections.

## Quality checklist before final answer

Before finalizing, verify:

- The opening contains tension, not just background.
- The article has a clear cognitive arc rather than a pile of points.
- Each major section advances the argument.
- Headings contain judgments.
- At least one useful model or framework appears if the subject supports it.
- Analogies clarify rather than decorate.
- Facts are not invented.
- Forecasts are framed as forecasts.
- The ending elevates the topic without becoming empty or exaggerated.
- The final output matches the user’s requested length and format.
