# Paper Reading Skill

`paper-reading` 是一个用于深度阅读学术论文的 Codex skill，适用于 arXiv 论文、PDF、技术报告、研究文章，以及多篇论文对比分析。

它默认使用中文输出，重点不是复述摘要，而是帮助你判断论文真正要解决什么问题、方法是否有新意、证据是否充分、贡献是否被夸大，以及有哪些可以复用的想法。

## 功能

- 快速判断论文是否值得深读
- 输出四格论文笔记：问题、方法、证据、局限
- 拆解论文贡献，区分真正新意、工程组合、实验贡献和包装表述
- 分析主要图表支持了哪些 claim
- 梳理论文与相关工作的关系
- 用自然语言解释关键公式和方法设计
- 像审稿人一样检查实验可信度
- 生成一页纸论文卡片
- 支持多篇论文的横向比较

## 仓库结构

```text
paper-reading/
├── SKILL.md
└── agents/
    └── openai.yaml
```

`paper-reading/SKILL.md` 是 skill 的主体说明文件。`agents/openai.yaml` 是 Codex 技能列表中使用的展示元数据。

## 安装

克隆仓库后，把 `paper-reading` 文件夹复制到本地 Codex skills 目录：

```bash
git clone https://github.com/emilyaalbertyb/paper-reading-skill.git
mkdir -p ~/.codex/skills
cp -R paper-reading-skill/paper-reading ~/.codex/skills/
```

安装后重启 Codex，或重新加载 skills。

## 示例提示词

```text
Use $paper-reading to analyze this arXiv paper in Chinese.
```

```text
Use $paper-reading to compare these three papers and explain which ideas are reusable.
```

```text
Use $paper-reading to review the experiments and tell me whether the evidence supports the claims.
```

## 适用范围

适用于学术论文、arXiv 论文、PDF、技术报告、研究文章，以及用户明确要求的 research-paper-style 分析。

不建议用于普通博客、新闻文章或非学术写作，除非用户明确希望按论文阅读方式分析。
