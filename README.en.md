# Paper Reading Skill

[中文 README](README.md)

`paper-reading` is a Codex skill for deep and efficient academic paper reading. It is designed for arXiv papers, PDFs, technical reports, research articles, and multi-paper comparison tasks.

The skill defaults to Chinese output. Its goal is not to restate the abstract, but to help you understand what problem the paper is really solving, whether the method is genuinely new, whether the evidence is convincing, whether the contributions are overstated, and which ideas can be reused.

## Features

- Quickly judge whether a paper is worth deep reading
- Produce four-cell paper notes: problem, method, evidence, and limitation
- Decompose claimed contributions into real novelty, engineering combinations, experimental contributions, and framing
- Analyze which claims are supported by major figures and tables
- Position the paper against related work
- Explain key formulas and method sections in plain language
- Review experimental credibility like a peer reviewer
- Generate a compact one-page paper card
- Compare multiple papers side by side

## Repository Structure

```text
paper-reading/
├── SKILL.md
└── agents/
    └── openai.yaml
```

`paper-reading/SKILL.md` contains the actual skill instructions. `agents/openai.yaml` provides UI-facing metadata for Codex.

## Installation

Clone this repository and copy the `paper-reading` folder into your local Codex skills directory:

```bash
git clone https://github.com/emilyaalbertyb/paper-reading-skill.git
mkdir -p ~/.codex/skills
cp -R paper-reading-skill/paper-reading ~/.codex/skills/
```

After installation, restart Codex or reload skills.

## Example Prompts

```text
Use $paper-reading to analyze this arXiv paper in Chinese.
```

```text
Use $paper-reading to compare these three papers and explain which ideas are reusable.
```

```text
Use $paper-reading to review the experiments and tell me whether the evidence supports the claims.
```

## Scope

Use this skill for academic papers, arXiv papers, PDFs, technical reports, research articles, and explicitly requested research-paper-style analysis.

It is not intended for casual blog posts, news articles, or non-academic writing unless the user explicitly asks for research-paper-style analysis.
