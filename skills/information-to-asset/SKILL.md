---
name: information-to-asset
description: Use when the user asks to analyze, understand, evaluate, summarize, judge usefulness, extract lessons, find next actions, or turn any input into reusable notes, SOPs, prompts, skills, scripts, project ideas, or knowledge assets. Applies to videos, articles, WeChat posts, GitHub projects, AI tools, links, documents, screenshots, transcripts, and raw ideas.
---

# Information to Asset

## Core Role

This is the upper routing skill for information entering a reusable knowledge and action system.

Do not become a giant all-purpose analyst. Decide what the input is, what evidence is needed, which lower skill should handle extraction, then synthesize the result into judgment, action, and asset routing.

```text
input -> evidence -> meaning -> usefulness -> value migration -> action -> asset decision
```

## Context Adaptation

This skill must be reusable across different people, teams, domains, and projects.

- Do not assume private background, personal goals, business context, or prior conversations that are not present.
- If no personal or organizational context is available, answer from a general operator/creator/team perspective.
- If context is available, adapt the judgment to that context, but keep evidence and inference separate.
- Strong generic output should still identify who the input matters for, what capability changes, what gets cheaper, what becomes valuable, and what can be tested next.

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

## Stop Conditions

Do not keep extracting evidence indefinitely. For hard-to-access links such as WeChat articles:

- After 2 browser/HTTP attempts and 1 decoding retry, stop and report the evidence state.
- If title, account, date, and usable `js_content` text are available, move to analysis.
- If only partial text is available, analyze the available part with a clear completeness warning.
- If no real article text is available, ask for pasted text or permission to continue trying a specific method.
- For long extraction steps, give a brief progress update instead of silently working.

Completeness matters, but a visible evidence boundary is better than an invisible loop.

## Verification Budget

When article text is incomplete, do not let fact-checking become an endless web investigation:

- For worldview, inspiration, trend, or "open my eyes" requests, outside verification and adjacent-search are useful; keep them, but make the phase visible.
- Separate "article analysis" from "external verification."
- Verify only the 2-3 claims that affect the user's judgment most.
- Prefer primary sources for current factual claims.
- Stop after enough evidence to label each key claim as supported, contradicted, or unverified.
- Do not chase every name, keyword, or related news item unless the user asks for a research brief.

If verification expands beyond the article, say that the task has shifted from content analysis to outside research.

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
What does it change for the requester, team, or target audience?
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
How would the requester's current work or workflow change?
What could the requester, team, or audience amplify with it?
What should they reduce dependence on?
What can people still contribute?
```

This is the world-model layer. The goal is not to chase tools; it is to see where human value moves when AI lowers the cost of a capability.

## Intent Layer

Do not choose the output shape only from the source type. After evidence is available, identify the user's intent:

```text
Summary: user wants to know what the input says.
Judgment: user wants to know whether it is true, useful, or worth attention.
Worldview / trend: user wants inspiration, horizon expansion, capability migration, or industry meaning.
Action: user wants to know what to do next.
Asset: user wants to decide whether and where to sediment it.
Project: user wants a concrete experiment or implementation path.
```

The same source can need different outputs. A WeChat article can be a quick summary, a fact-check, a worldview signal, or an action plan. Do not force every input into the worldview/trend structure.

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
Domain knowledge-base update: belongs in an existing project, business, or research memory system.
```

Do not write files by default. If the user asks to sediment the result, first look for the closest existing note, index, protocol, or skill. Update existing assets before creating new ones.

## Output Modes

Choose the lightest useful shape based on intent:

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
对使用者/团队的启发：
下一步动作：
沉淀建议：
```

**Worldview / trend analysis**

Use this when the user wants inspiration, trend sense, AI industry meaning, role/career shifts, or to "open my eyes":

```text
文章本身：
外部核验：
趋势判断：
对使用者/团队意味着什么：
下一步小实验：
是否沉淀：
```

The key move is to turn the input into a capability-path judgment, not a job-title chase or tool recommendation.

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
