---
title: "{{title}}"
created: "{{date:YYYY-MM-DD}}"
updated: "{{date:YYYY-MM-DD}}"
type: "source-summary"
status: "draft"
source_urls: []
source_notes: []
tags:
  - wiki
  - llm-kb
confidence: "medium"
---

# {{title}}

> [!abstract] TL;DR
> 2-4 sentence synthesis of the page purpose and takeaway.

## Core Idea

- What is the key idea?
- Why does it matter now?
- How does it differ from naive RAG usage?

## Architecture Mapping

- Raw sources (`raw/`):
- Compiled wiki (`wiki/`):
- Schema/workflow rules (`AGENTS.md`):

## Evidence & Claims

- Claim: 
  - Evidence: [[raw/...]] or URL
  - Confidence: `low | medium | high`

- Claim: 
  - Evidence: [[raw/...]] or URL
  - Confidence: `low | medium | high`

Key claim anchor for deep links. ^key-claim

## Ingest Actions

- [ ] Create/refresh summary page
- [ ] Update related concept/entity pages
- [ ] Add/update backlinks
- [ ] Add/update `INDEX.md`
- [ ] Add entry draft to `LOG.md`

## Query Outputs

- Candidate derived outputs to file back into wiki:
  - Comparison page
  - Q&A synthesis page
  - Slide/visual artifact note

> [!todo]
> If this note came from a query, list what should be persisted vs kept ephemeral.

## Lint Checklist

- [ ] Contradictions with existing notes checked
- [ ] Stale claims flagged
- [ ] Missing cross-links added
- [ ] Orphan risk reviewed
- [ ] Follow-up questions recorded

> [!warning]
> Do not edit `raw/` source captures unless correcting obvious extraction errors.

## Related Notes

- [[INDEX]]
- [[LOG]]
- [[AGENTS]]
- [[raw/Thread by @karpathy]]
- [[raw/llm-wiki]]

## Log Entry Draft

```markdown
## [{{date:YYYY-MM-DD}}] ingest | {{title}}
- Sources: [[raw/...]]
- Updated pages: [[...]], [[...]]
- Notes: key changes, contradictions, next actions
```
