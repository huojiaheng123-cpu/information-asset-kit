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

## Context Adaptation

This skill must stay useful without relying on one person's private background.

- Do not assume hidden personal goals, business context, or previous conversations.
- If no context is available, analyze from a general reader/operator/team perspective.
- If context is available, adapt the usefulness, value migration, action, and asset decision to that context.
- Generic does not mean weak: still identify who the text matters for, what changes, what can be tested, and what should or should not be saved.

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

Do not wait for perfect extraction forever. If the source text is incomplete after reasonable extraction attempts, analyze only what is actually available and mark the result as partial.

If outside verification is needed, limit it to the few claims that change the user's decision. For inspiration or trend reading, adjacent-search is welcome, but label it as outside research and summarize progress before going deeper.

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
What it changes for the reader, operator, team, or target audience:
What the requester should do:
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
How would the requester's current work or workflow change?
What could the requester, team, or target audience amplify with it?
What should they reduce dependence on?
What can people still contribute?
```

This is the main worldview layer. Do not reduce it to a tool recommendation.

## Intent Layer

Do not analyze every text with the same structure. After evidence is available, identify the user's intent:

```text
Summary: what the text says.
Judgment: whether it is true, useful, or worth attention.
Worldview / trend: what changes in capability, work, roles, industry, or leverage.
Action: what the user should try next.
Asset: whether this should become a note, SOP, prompt, skill, script, or project.
```

Use the worldview/trend structure only when the user asks for inspiration, trend sense, "open my eyes", AI industry meaning, role shifts, or capability migration. Otherwise use the lighter relevant shape.

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
Domain knowledge-base update: belongs in an existing project, business, or research memory system.
```

If writing to a knowledge base or vault, update the closest existing note before creating a new one.

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
对使用者/团队的启发：
价值迁移：
下一步行动：
沉淀建议：
```

**Worldview / trend text**

```text
文章本身：
外部核验：
趋势判断：
对使用者/团队意味着什么：
下一步小实验：
是否沉淀：
```

Use this for AI trends, new roles, industry shifts, creator/developer experiences, and articles meant to broaden judgment. Do not reduce the answer to "learn this job/tool"; translate it into what capability becomes cheaper, what becomes valuable, and what the user can test next.

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
