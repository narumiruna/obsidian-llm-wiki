---
title: "LLM Wiki Workflow"
created: "2026-04-06"
updated: "2026-04-06"
type: "source-summary"
status: "active"
source_urls:
  - "https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f"
  - "https://x.com/karpathy/status/2039805659525644595?s=46"
source_notes:
  - "[[raw/llm-wiki]]"
  - "[[raw/Thread by @karpathy]]"
tags:
  - wiki
  - llm-kb
  - workflow
confidence: "high"
---

# LLM Wiki Workflow

> [!abstract] TL;DR
> Build a persistent markdown wiki that compounds over time. Store sources in `raw/`, let the LLM maintain `wiki/`, and continuously run ingest/query/lint loops so new knowledge updates existing pages instead of being rediscovered from scratch.

## Core Idea

The main shift is from query-time retrieval only (classic RAG behavior) to a maintained knowledge layer. The wiki is treated as a compiled artifact: each new source updates summaries, entities, concept pages, and cross-links.

## Architecture (3 Layers)

- **Raw sources**: immutable captures in `raw/`.
- **Wiki layer**: synthesized notes and relationships in `wiki/`.
- **Schema/rules**: operating conventions in `AGENTS.md`.

## Operating Loop

### 1. Ingest

- Add one source to `raw/`.
- Extract key claims and evidence.
- Update related wiki pages, not just create one summary page.
- Record the change in `LOG.md` and keep `INDEX.md` navigable.

### 2. Query

- Ask questions against the wiki first.
- Create durable outputs (comparison notes, synthesis pages, deck-ready notes).
- File useful outputs back into `wiki/` so exploration compounds.

### 3. Lint

- Detect contradictions and stale claims.
- Find orphan or weakly linked pages.
- Identify missing concepts/entities for new pages.

## Why This Scales Better Than Chat-Only Work

- Cross-references and synthesis are pre-built.
- Contradictions can be tracked explicitly.
- New work improves prior work instead of resetting context each session.

## Practical Notes from Karpathy

- Obsidian is the frontend/IDE; the LLM is the maintainer.
- Markdown and local assets make outputs reusable.
- At moderate scale, index + summaries can work without complex RAG stacks.

> [!todo]
> Next step for this vault: start creating concept/entity pages in `wiki/`, then keep `INDEX.md` and `LOG.md` updated on every ingest.

## Related Notes

- [[raw/llm-wiki]]
- [[raw/Thread by @karpathy]]
- [[AGENTS]]
- [[INDEX]]
- [[LOG]]
