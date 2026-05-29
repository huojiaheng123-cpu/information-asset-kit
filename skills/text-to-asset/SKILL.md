---
name: text-to-asset
description: Use when the user asks to analyze, evaluate, summarize, judge usefulness, extract lessons, or turn text-based inputs into reusable judgment, action, notes, SOPs, prompts, skills, scripts, project ideas, or knowledge assets. Applies to WeChat posts, web articles, newsletters, essays, forum posts, transcripts, copied text, meeting notes, PDFs already extracted to text, and raw long-form text.
---

# Text to Asset

## Role

Use this for text evidence. It does not watch videos, play audio, browse hidden pages, or inspect files by itself. It analyzes text that has been opened, pasted, extracted, or otherwise made available.

Core path:

```text
text -> claim map -> evidence boundary -> usefulness -> value migration -> action -> asset decision
```

## Evidence Boundary

Start by identifying what the text actually is:

```text
Source type:
Author / publisher if known:
Date if known:
Text actually available:
Missing context:
```

For WeChat public-account articles, mark which extraction layer succeeded:

```text
Browser page:
Command-line HTML:
js_content正文:
Title / account / publish time:
Encoding status:
Completeness:
```

If only HTML, a preview, or partial `js_content` is available, say so before analysis.

Do not treat the text as verified fact. Separate:

```text
Facts or directly stated claims:
Author opinions:
Predictions:
Marketing or emotional framing:
Things that need outside verification:
```

If the user asks for current facts, product details, legal/financial/medical claims, pricing, or recent events, verify live before relying on the text.

## Analysis Frame

Use the lightest useful answer. Do not mechanically expand every section when the text is minor.

```text
It says what:
What is useful:
What is questionable:
What it changes in the user's thinking:
What the user should do:
Whether it should become an asset:
```

For weak but inspiring content, label it clearly:

```text
有启发，但不能直接当事实。
可转成方法，但不能当证据。
适合激励，不适合决策。
```

## Value Migration

For AI, tools, workflows, industry trends, project experience, creator experience, business changes, and future-facing claims, add:

```text
If this capability or trend matures, what becomes cheaper?
What becomes more valuable?
How would the user's current work change?
What can the user amplify with it?
What should the user reduce dependence on?
What can the user still contribute?
```

This is the main worldview layer. Do not reduce it to a tool recommendation.

## Asset Decision

Choose one:

```text
Ignore: no new evidence, no action, no reusable judgment.
Temporary: interesting but not reliable or actionable yet.
Formal note: improves judgment and can be called later.
SOP / prompt: repeatable process worth reusing.
Skill: recurring workflow that should guide future agents.
Script / tool: deterministic repeated task worth automating.
Project experiment: worth testing in 30 minutes to 7 days.
Business/vault update: belongs in an existing domain memory system.
```

If writing to a vault, update the closest existing note before creating a new one.

## Output Shapes

**Quick text analysis**

```text
结论：
有用处：
风险/边界：
下一步：
是否沉淀：
```

**Deep text analysis**

```text
来源和证据边界：
核心主张：
事实 / 观点 / 预测 / 营销：
对用户的启发：
价值迁移：
下一步行动：
沉淀建议：
```

**Asset update proposal**

```text
应该更新哪里：
为什么不是新建：
建议补充什么：
验证方式：
```

## Guardrails

- Do not say you read a full article if only an excerpt is available.
- Do not say you watched or heard anything when only text is available.
- Do not turn every article into a permanent note.
- Do not over-summarize into vague inspiration; preserve the concrete useful judgment.
- Do not create a new framework when an existing note can absorb the idea.
