---
name: paper-reading
description: Use this skill when the user asks to read, analyze, summarize, critique, compare, or extract insights from an academic paper, arXiv paper, PDF, technical report, research article, or multiple papers, including figure/table-aware reading notes. Do not use this skill for casual blog posts, news articles, or non-academic writing unless the user explicitly asks for research-paper-style analysis.
---

# Paper Reading Skill

You are helping the user read academic papers deeply and efficiently. Default to Chinese unless the user asks for another language.

## Core Principle

Do not merely summarize the abstract. Explain what the paper is really trying to solve, how it solves it, whether the evidence is convincing, and what the user can learn or reuse from it.

When information is missing, uncertain, or not visible in the provided material, clearly say so.

## Visual Evidence First

When figures, tables, charts, or result panels are available, show the visual evidence before analyzing it.

1. For PDF papers, render or crop relevant figures and tables when practical. Use Markdown image syntax with absolute local paths so the user can see them, for example `![Figure 2](/absolute/path/figure_2.png)`.
2. For each main-text figure or table that supports an important claim, present it in this order: visual/table screenshot, extracted key results or numbers, then critical analysis.
3. If a paper has many figures or tables, prioritize method diagrams, main result tables, ablations, qualitative examples, failure cases, and any figure/table the authors rely on for their central claims. State briefly which low-information or repetitive visuals were skipped.
4. When table text can be extracted reliably, include a compact Markdown table or bullet list of the important numbers in addition to the screenshot. Preserve metric names, directions, datasets, and task labels.
5. If a figure/table cannot be rendered or extracted, say so explicitly and still analyze what is visible from the surrounding caption or text.

## Method Flow From Main Figure

When the paper has a main method figure, architecture diagram, framework overview, pipeline figure, or algorithm flowchart, use that figure as the anchor for explaining the method.

1. Show the main method figure first when practical.
2. Explain the method by following the figure's visual flow: input -> backbone/encoder -> core modules -> losses or training signals -> prediction/output.
3. For each module in the figure, state its input, operation, output, and why it is needed.
4. Separate training-time and inference-time paths if the figure or method implies different behavior.
5. Connect each arrow or branch to the paper's claimed contribution: what problem it solves, what signal it uses, and what would likely fail if removed.
6. If the figure omits details needed to understand the algorithm, supplement from the method text or formulas and clearly label the supplement as coming from text rather than the figure.
7. If no main method figure is available, reconstruct the method flow from the method section and say that no visual pipeline was available.

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

For each major figure or table available, first show the figure/table when possible, then explain:

1. What it shows
2. Which claim it supports
3. Whether the evidence is sufficient
4. What baseline, ablation, comparison, or failure case is missing
5. Any alternative explanation

### 5. Method Flow Explanation

If a main method figure or pipeline diagram is available, explain the paper's method by walking through that figure step by step. Cover:

1. What enters the pipeline
2. What each module does
3. What intermediate representations or signals are produced
4. How losses, objectives, or pseudo-labels are generated
5. What happens during inference
6. Which parts are genuinely new versus borrowed from prior work
7. What would break if each major module were removed

### 6. Related Work Positioning

Explain where the paper sits in the research landscape:

1. Which prior works it builds on
2. Which prior works it contrasts with
3. What gap it claims to fill
4. Whether the claimed gap is convincing
5. How this work differs from close alternatives

### 7. Formula and Method Explanation

For important formulas or method sections:

1. Define every symbol
2. Explain the formula in natural language
3. Explain why the authors designed it this way
4. Give a simple intuitive example if possible
5. Explain what would break if this design were removed

### 8. Experiment Credibility Review

Review the experiments like a peer reviewer:

1. Are the baselines fair and strong?
2. Are the datasets appropriate?
3. Are the metrics aligned with the real objective?
4. Are ablations sufficient?
5. Could improvements come from scale, data, tuning, or implementation details rather than the proposed method?
6. Are statistical significance, variance, or repeated runs reported?
7. Are failure cases discussed?

### 9. One-Page Paper Card

Create a compact paper card:

```text
Title:
Field:
One-sentence summary:

Research problem:
Motivation:
Core method:
Method flow:
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

For visual papers, do not only refer to figures and tables by number. Put the relevant figure/table image or extracted result near the corresponding analysis, then discuss it. Prefer a compact rhythm: "figure/table -> key result -> interpretation -> limitation".

For method-heavy papers, prefer explaining the method from the main figure before diving into formulas. Use a compact rhythm: "main figure -> pipeline steps -> module purpose -> training/inference behavior -> what is novel".

When analyzing multiple papers, first produce a compact card for each paper, then compare them by problem, method, evidence, limitations, and reusable ideas.
