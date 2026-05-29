---
name: ai-frontier-radar
description: Track fast-moving AI frontier signals and turn them into information-gap briefings. Use when the user asks for AI frontier intelligence, GitHub/Hugging Face/arXiv AI trends, fast-rising AI projects, coding agents, AI agents, MCP ecosystem updates, model releases, product opportunities, or wants to know what is becoming important before mainstream coverage catches up.
---

# AI Frontier Radar

## Purpose

Produce high-signal AI frontier briefings that help the user detect emerging capability shifts early. Prioritize actionable information gaps over generic news summaries.

## Default Workflow

1. Define the scan window and scope. If the user does not specify a window, use the latest 7 days for volatile sources and the latest 30 days for slower sources. Prefer exact dates in the response.
2. Search current sources. Browse the internet for recent data unless the user explicitly provides sources or asks not to browse.
3. Gather signals across multiple layers:
   - GitHub: fast-rising repos, release notes, issues, commits, forks, contributors, demos, and whether respected developers are starring or discussing it.
   - Hugging Face: new/trending models, datasets, Spaces, model cards, downloads, likes, and demos.
   - Papers and research: arXiv, Papers with Code, lab blogs, benchmark jumps, new evaluation methods.
   - Product and platform updates: OpenAI, Anthropic, Google DeepMind, Meta, Microsoft/GitHub, xAI, Perplexity, Mistral, Alibaba/Qwen, DeepSeek, ByteDance, Tencent, Baidu, Moonshot, Zhipu, and other relevant labs.
   - Ecosystem chatter: Hacker News, Reddit, X posts when accessible, Discord/forum summaries, issue threads, and developer complaints.
4. Score each candidate with the information-gap rubric below.
5. Filter aggressively. Prefer 5-10 items with clear reasons over a long list.
6. Explain why each item matters, what might be overhyped, and what the user could do next.

## Information-Gap Rubric

Use this formula:

```text
attention-worthy = new capability x fast diffusion x real pain x low adoption friction x defensible ecosystem position
```

Assess each item on these dimensions:

- Capability shift: What can people do now that was hard, expensive, or impossible before?
- Diffusion speed: Is it gaining stars, downloads, forks, integrations, demos, PRs, or founder/developer attention quickly?
- Pain intensity: Which workflow pain does it solve, and who urgently feels it?
- Adoption friction: Can a motivated user try it today with a CLI, API, hosted demo, extension, MCP server, or template?
- Ecosystem position: Is it a one-off demo, a reusable primitive, a protocol layer, infrastructure, or an application wedge?
- Durability: Does it have maintainers, releases, docs, tests, issue activity, and a plausible path beyond initial hype?
- Monetization or leverage: Could it become a tool, plugin, workflow service, vertical app, data layer, or consulting opportunity?

## Priority Themes

When the user asks broadly about AI frontier developments, prioritize:

- Coding agents and software engineering automation.
- Computer-use agents that operate browsers, desktops, IDEs, spreadsheets, design tools, or 3D tools.
- Agent memory, context engineering, evals, observability, orchestration, and sandboxing.
- MCP and tool/protocol ecosystems.
- Multimodal generation: voice, video, image, 3D, real-time avatars, and synthetic media workflows.
- Local AI, small models, quantization, on-device inference, and privacy-preserving automation.
- Data pipelines for LLM applications: document conversion, RAG, extraction, labeling, and synthetic data.
- Vertical AI workflows where AI saves 80% of time for a specific role.

## Output Formats

For a quick briefing, use:

```markdown
**Frontier Radar: YYYY-MM-DD**

1. [Name](link) - one-line what it is.
   Signal: growth/release/demo/source.
   Why it matters: concrete capability shift.
   Skepticism: what may be hype or fragile.
   Move: what the user can try, watch, or build.
```

For a strategic memo, use:

```markdown
**Thesis**
Short thesis in 2-3 bullets.

**Signals**
Table with item, source, signal strength, why now, opportunity.

**Watchlist**
3-5 things to monitor next week.

**Action**
1-3 concrete moves for the user.
```

Keep tone direct, opinionated, and practical. Avoid generic "AI is changing everything" phrasing.

## Verification Rules

- Browse for current facts, dates, star counts, releases, and model availability.
- Cite links for claims that depend on current data.
- Treat GitHub stars as a noisy signal. Cross-check with forks, contributors, commit recency, issues, releases, downloads, demos, and external discussion.
- Distinguish official releases from community summaries.
- Name uncertainty. If growth data comes from a third-party leaderboard, say so and link it.
- Do not present investment advice. For finance-related AI projects, label them as research or tooling unless the user explicitly asks for financial analysis.

## Reference

Load `references/signal-sources.md` when the user asks for a deeper scan, recurring radar, source expansion, or wants to build a durable information workflow.
