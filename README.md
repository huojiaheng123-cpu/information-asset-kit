# Information Asset Kit

Information Asset Kit is a Codex plugin that turns messy inputs into evidence-bounded judgment, next actions, and reusable assets.

It is designed for people who do not only want summaries. It helps decide:

- What evidence is actually available?
- Is the input useful, questionable, or just inspiring?
- What changes if this capability or trend matures?
- What should someone try next?
- Should this become a note, SOP, prompt, skill, script, or project experiment?

## Included Skills

| Skill | Use For |
| --- | --- |
| `information-to-asset` | Upper router. Classifies the input, chooses the evidence path, identifies user intent, and synthesizes meaning, action, and asset routing. |
| `text-to-asset` | Articles, WeChat posts, newsletters, essays, transcripts, copied text, extracted PDF text, and long-form notes. |
| `watch-video-skill` | Local videos, web videos, short videos, course clips, screen recordings, and video links. |
| `audio-transcribe` | Audio/video transcription before analysis. |
| `ai-frontier-radar` | AI trends, GitHub projects, frontier signals, tools, and fast-moving ecosystem changes. |

## Core Workflow

```text
input -> evidence -> meaning -> usefulness -> value migration -> action -> asset decision
```

The plugin first asks what kind of input it is, then what the requester wants from it:

```text
Summary: what does it say?
Judgment: is it true, useful, or worth attention?
Worldview / trend: what capability, role, workflow, or market shift does it reveal?
Action: what should be tried next?
Asset: should it become a reusable note, SOP, prompt, skill, script, or project?
Project: can it become a concrete experiment?
```

## Why This Is Different From a Summary Tool

Most analysis stops at "what it says." This plugin pushes one layer further:

- It separates facts, opinions, predictions, and marketing.
- It states what was actually seen, read, extracted, or inferred.
- It can verify the few external claims that matter most.
- It turns trends into value-migration questions: what gets cheaper, what becomes more valuable, and what humans or teams should still contribute.
- It avoids saving everything as a permanent note.

## Context Adaptation

The public version does not assume one person's private goals, business, or memory system.

If no context is available, it analyzes from a general reader, operator, creator, learner, or team perspective. If context is available, it adapts the judgment to that context while keeping evidence and inference separate.

Generic does not mean weak: the output should still identify who the input matters for, what changes, what can be tested, and whether it deserves to become an asset.

## Example Prompts

```text
Analyze this article and tell me whether it is actually useful.
```

```text
Turn this video into judgment, action, and reusable assets.
```

```text
Check this GitHub AI project. What trend does it represent, and should I learn from it?
```

```text
Analyze this WeChat article. Do not just summarize it; tell me what it means and what I should test next.
```

```text
I want inspiration and trend sense from this input. Open my eyes, but keep evidence boundaries clear.
```

## Output Modes

### Quick Take

```text
Conclusion:
Why:
Next step:
Should it become an asset:
```

### Deep Analysis

```text
What it is:
Evidence boundary:
Core content:
Usefulness:
Value migration:
Implications for the requester/team:
Next action:
Asset recommendation:
```

### Worldview / Trend Analysis

```text
The source itself:
External verification:
Trend judgment:
What it means for the requester/team:
Small experiment:
Should it be saved:
```

## Evidence Rules

- Do not claim to have watched a video from a title, cover image, or webpage snippet.
- Do not claim to have read a full article if only an excerpt or preview was available.
- For blocked or incomplete WeChat articles, report the extraction state instead of guessing.
- For current AI tools, GitHub projects, prices, product claims, or recent events, verify live when the claim may have changed.
- External verification should usually focus on the 2-3 claims that most affect the judgment.

## Installation

Install this repository as a Codex plugin from GitHub:

```text
https://github.com/huojiaheng123-cpu/information-asset-kit
```

After installing or updating, restart or reload Codex if the new skills do not appear immediately.

## Optional Dependencies

Some skills can work in a degraded mode without local tools, but richer video/audio analysis may need:

- FFmpeg
- Chrome or Edge
- Playwright / browser automation support
- Python packages used by the bundled video/audio scripts

The video skill includes capability checks and should report missing dependencies instead of pretending full analysis is available.

## Limitations

- This plugin improves analysis discipline; it does not make inaccessible content accessible.
- It cannot verify private, paywalled, login-only, or deleted content unless the requester provides access or text.
- It should not be used as a substitute for professional legal, medical, or financial advice.
- It should not write into a knowledge base by default; it should propose where something belongs unless asked to edit files.

## License

MIT
