---
title: "Attention Residuals"
created: "2026-04-06"
updated: "2026-04-06"
type: "paper-note"
status: "active"
authors:
  - "Kimi Team (MoonshotAI)"
year: 2026
venue: "arXiv"
doi: ""
arxiv: "2603.15031"
url: "https://arxiv.org/abs/2603.15031"
tags:
  - paper
  - llm
  - transformer
  - residual
rating:
confidence: "medium"
source_urls:
  - "https://www.alphaxiv.org/overview/2603.15031.md"
  - "https://arxiv.org/abs/2603.15031"
---

# Attention Residuals

> [!abstract] Paper TL;DR
> This paper replaces fixed additive residual accumulation with depth-wise softmax attention over previous layers. The proposed Attention Residuals (AttnRes), especially Block AttnRes, improves training dynamics and downstream performance while staying practical at scale. Reported gains are notable on reasoning and coding benchmarks, with reduced hidden-state growth and more uniform gradients across depth.

## Citation

- Authors: Kimi Team (MoonshotAI)
- Venue / Year: arXiv, 2026
- ArXiv: [2603.15031](https://arxiv.org/abs/2603.15031)
- Overview: [AlphaXiv report](https://www.alphaxiv.org/overview/2603.15031.md)

## Research Question

- Can residual connections in deep LLMs be made content-aware and selective across depth, instead of fixed additive accumulation?
- Can this be done without introducing prohibitive system overhead?

## Method

- Key idea: treat depth-wise residual aggregation as an attention problem.
- Full AttnRes: each layer attends over all prior layer outputs with softmax weights.
- Block AttnRes: compress layers into blocks, apply attention over block representations for scalability.
- Practical engineering:
  - Cross-stage caching for pipeline parallel training.
  - Two-phase inference computation to reduce memory access overhead.

## Main Results

| Metric / Benchmark | AttnRes | Baseline | Delta |
|---|---:|---:|---:|
| GPQA-Diamond | +7.5 | 0 | +7.5 |
| Minerva Math | +3.6 | 0 | +3.6 |
| HumanEval | +3.1 | 0 | +3.1 |
| MMLU | +1.1 | 0 | +1.1 |
| TriviaQA | +1.9 | 0 | +1.9 |

> [!note]
> The report also indicates better scaling behavior and improved depth utilization versus PreNorm residual baselines.

## Evidence & Claims

- Claim: PreNorm residual accumulation causes hidden-state growth and contribution dilution with depth.
  - Evidence: AlphaXiv report sections on training dynamics and output magnitude.
  - Confidence: `medium`

- Claim: Block AttnRes mitigates hidden-state growth and yields more uniform gradient distribution.
  - Evidence: AlphaXiv report training dynamics analysis.
  - Confidence: `medium`

- Claim: Block AttnRes improves multi-step reasoning and code generation benchmarks.
  - Evidence: AlphaXiv report downstream benchmark section.
  - Confidence: `medium`

Anchor claim for deep link references. ^key-claim

## Limitations

- Current note is based on AlphaXiv structured report, not full paper line-by-line reading.
- Numeric deltas are report-level summaries; exact experimental setup details should be verified against the original paper.
- No independent reproduction in this vault yet.

## Reproducibility Checklist

- [ ] Code repository located
- [ ] Dataset access confirmed
- [ ] Hyperparameters captured
- [ ] Environment dependencies captured
- [ ] Reproduction risks documented

## Connections

- Related papers: [[raw/llm-wiki]]
- Related concepts: [[wiki/LLM Wiki Workflow]]
- Contradictory findings: [[...]]

## Practical Notes

- Where useful: deeper LLM training where residual dilution limits depth efficiency.
- Likely challenge: system complexity increases despite block optimizations.
- Next experiment: compare a baseline residual stack vs block-attention residual stack under same compute budget.

> [!todo]
> Pull the full `abs` markdown or arXiv PDF and fill exact equations, block size settings, and ablation table details.

## Follow-up Actions

- [ ] Update/create related concept note in `wiki/`
- [x] Add paper note entry to `INDEX.md`
- [x] Append operation entry to `LOG.md`

