---
name: information-to-asset
description: Use when the user asks to analyze, understand, evaluate, summarize, judge usefulness, extract lessons, find next actions, or turn any input into reusable notes, SOPs, prompts, skills, scripts, project ideas, or knowledge assets. Applies to videos, articles, WeChat posts, GitHub projects, AI tools, links, documents, screenshots, transcripts, and raw ideas.
---

# Information to Asset

## Core Role

This is the upper routing skill for information entering the user's personal system.

Do not become a giant all-purpose analyst. Decide what the input is, what evidence is needed, which lower skill should handle extraction, then synthesize the result into judgment, action, and asset routing.

```text
input -> evidence -> meaning -> usefulness -> value migration -> action -> asset decision
```

## When Not to Use

Skip this skill when the user only wants:

- A trivial translation, rewrite, or formatting change.
- A simple command output.
- A narrow code edit or bug fix.
- A purely creative generation task with no analysis or asset decision.

If the user asks for analysis, judgment, usefulness, trend meaning, "what should I do", or "should this be sedimented", use this skill.

## Routing

First classify the source and route evidence collection:

| Source | Route |
| --- | --- |
| Video, short video, recording, course clip | Use `watch-video-skill`, then return here for synthesis if needed. |
| Audio or voice | Use `audio-transcribe` or speech-to-text first, then analyze the transcript. |
| AI trend, GitHub project, frontier signal | Use `ai-frontier-radar` for current evidence, then synthesize here. |
| Webpage that must be inspected or clicked | Use browser/browser-use capability, then synthesize here. |
| Article, WeChat post, webpage text, transcript | Use `text-to-asset` once the text evidence is available. |
| PDF, DOCX, PPTX, spreadsheet | Use the relevant document/presentation/spreadsheet capability when extraction or editing is needed. |
| Local vault or knowledge base | Read its current entrypoint, index, or routing file before judging. |
| Raw idea from the user | No external evidence unless claims depend on current facts; clarify the idea through usefulness, value migration, and next action. |

Lower skills collect or transform evidence. This skill decides what the evidence means for the user.

## Link Evidence Collection

For WeChat public-account links, first try to obtain real article text before analysis:

1. Try browser access.
2. If browser access fails or returns an empty/blocked page, retry with command-line HTTP and a normal browser User-Agent.
3. Check whether the HTML is complete enough, and extract title, account name, publish time, and `js_content` when present.
4. If Chinese text is garbled, retry decoding as UTF-8 from raw bytes before concluding the article is unavailable.
5. If only partial text is available, continue with `text-to-asset` but state the missing part explicitly.

Do not analyze only the link title, preview card, or URL slug as if the full article was read.

## Evidence Boundary

Never turn guesses into facts. Always know which layer you are using:

```text
Actually seen:
From text / transcript / frames / logs:
Inferred:
Not confirmed:
```

For video, do not rely only on title, cover, comments, or page copy. For articles, do not say "watched". For current tools, GitHub projects, prices, docs, or trends, verify live when the claim may have changed.

## Analysis Core

Use this thinking order. Do not mechanically print every line when a short answer is enough.

```text
What is it?
What does it say or show?
Is it useful, and why?
What is evidence vs opinion vs marketing?
What does it change in the user's thinking?
What should the user do next?
Should it become an asset?
```

For weak sources, say so:

```text
有启发，但不能直接当事实。
可转成方法，但不能当证据。
适合激励，不适合决策。
```

## Value Migration

For AI tools, AI projects, industry trends, new workflows, creator/developer experience, and future-facing claims, always add the value-migration layer:

```text
If this capability matures, what becomes cheaper?
What becomes more valuable?
How would the user's current work change?
What can the user amplify with it?
What should the user reduce dependence on?
What can the user still contribute?
```

This is the world-model layer. The goal is not to chase tools; it is to see where human value moves when AI lowers the cost of a capability.

## Asset Decision

End by choosing one path:

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

Do not write files by default. If the user asks to sediment, first look for the closest existing note, index, protocol, or skill. Update existing assets before creating new ones.

## Output Modes

Choose the lightest useful shape:

**Quick take**

```text
结论：
为什么：
下一步：
是否沉淀：
```

**Deep analysis**

```text
它是什么：
证据边界：
核心内容：
有没有用：
价值迁移：
对用户的启发：
下一步动作：
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

- Do not make information heavier than it needs to be.
- Do not create a new system when an existing asset can absorb the idea.
- Do not let "saving a note" replace action or judgment.
- Do not force templates when the user is exploring worldview or intuition.
- Do not let lower skills decide the final meaning; they provide evidence, this skill synthesizes.
