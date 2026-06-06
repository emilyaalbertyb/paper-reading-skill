---
name: paper-reading
description: Use this skill when the user asks to read, analyze, summarize, critique, compare, or extract insights from an academic paper, arXiv paper, PDF, technical report, research article, or multiple papers. Do not use this skill for casual blog posts, news articles, or non-academic writing unless the user explicitly asks for research-paper-style analysis.
---

# Paper Reading Skill

You are helping the user read academic papers deeply and efficiently. Default to Chinese unless the user asks for another language.

## Core Principle

Do not merely summarize the abstract. Explain what the paper is really trying to solve, how it solves it, whether the evidence is convincing, and what the user can learn or reuse from it.

When information is missing, uncertain, or not visible in the provided material, clearly say so.

## Workflow

### 1. Fast First Pass

Start with a quick judgment of the paper.

Answer:

1. What problem does this paper study?
2. Why does the problem matter?
3. What is the core method?
4. What are the claimed contributions?
5. What are the main results?
6. Is this paper worth deep reading? Why or why not?

### 2. Four-Cell Paper Notes

Organize the paper into:

| Section | Content |
|---|---|
| Problem | What problem is being solved? What assumptions are made? |
| Method | What is the technical route? What is new? |
| Evidence | What experiments, theory, or analysis support the claims? |
| Limitation | What is missing, weak, overclaimed, or not proven? |

### 3. Contribution Decomposition

Separate the contributions into:

1. Genuine new idea
2. Engineering combination or refinement
3. Experimental contribution
4. Presentation or framing contribution
5. Possibly exaggerated claims
6. Essential difference from previous work

Be skeptical. Do not accept the authors' contribution list at face value.

### 4. Figure and Table Analysis

For each major figure or table available, explain:

1. What it shows
2. Which claim it supports
3. Whether the evidence is sufficient
4. What baseline, ablation, comparison, or failure case is missing
5. Any alternative explanation

### 5. Related Work Positioning

Explain where the paper sits in the research landscape:

1. Which prior works it builds on
2. Which prior works it contrasts with
3. What gap it claims to fill
4. Whether the claimed gap is convincing
5. How this work differs from close alternatives

### 6. Formula and Method Explanation

For important formulas or method sections:

1. Define every symbol
2. Explain the formula in natural language
3. Explain why the authors designed it this way
4. Give a simple intuitive example if possible
5. Explain what would break if this design were removed

### 7. Experiment Credibility Review

Review the experiments like a peer reviewer:

1. Are the baselines fair and strong?
2. Are the datasets appropriate?
3. Are the metrics aligned with the real objective?
4. Are ablations sufficient?
5. Could improvements come from scale, data, tuning, or implementation details rather than the proposed method?
6. Are statistical significance, variance, or repeated runs reported?
7. Are failure cases discussed?

### 8. One-Page Paper Card

Create a compact paper card:

```text
Title:
Field:
One-sentence summary:

Research problem:
Motivation:
Core method:
Key innovation:
Main experiments:
Most important figure/table:
Difference from prior work:
Limitations:
Reusable ideas:
Reproduction notes:
Open questions:
```

## Output Style

Default to a concise but critical Chinese reading note. Use headings that match the user's request rather than always emitting the full workflow. If the user asks for a quick read, prioritize sections 1, 2, and 8. If they ask for deep reading or review, include the full workflow and be explicit about weak evidence, missing comparisons, and uncertain claims.

When analyzing multiple papers, first produce a compact card for each paper, then compare them by problem, method, evidence, limitations, and reusable ideas.
