# AI 落地实用开源仓库索引与分析库

> **目标**：每天从 GitHub Trending + X 热议中精选 **固定20个** 高质量、可落地的 AI / Agent / RAG / Agentic 项目，并提供结构化分析与商业洞察。  
> 采用 **ai-content-kb** 架构：原文可信 · Wiki 可读 · 图谱可查 · AI 输出可审核。

## 快速导航

- [按分类浏览](wiki/index.md)
- [最新每日更新](wiki/daily/)
- [深度研究](research/)
- [AI 代理使用指南](#ai-代理使用指南)
- [合作协议](#合作协议)

## 按分类浏览

| 分类 | 入口 |
|------|------|
| Agent Frameworks & Orchestration | [wiki/categories/agent-frameworks.md](wiki/categories/agent-frameworks.md) |
| RAG & Knowledge Systems | [wiki/categories/rag-systems.md](wiki/categories/rag-systems.md) |
| LLM Deployment & Serving | [wiki/categories/llm-deployment.md](wiki/categories/llm-deployment.md) |
| Multi-Agent & Workflow | [wiki/categories/multi-agent.md](wiki/categories/multi-agent.md) |
| Content & Creative AI | [wiki/categories/content-creative.md](wiki/categories/content-creative.md) |
| Local & Self-Hosted AI | [wiki/categories/local-ai.md](wiki/categories/local-ai.md) |
| Agent Safety & Governance | [wiki/categories/agent-safety.md](wiki/categories/agent-safety.md) |

完整列表见 **[wiki/index.md](wiki/index.md)**

## 最新每日更新

- **[2026-07-12 完整日报](wiki/daily/2026-07-12.md)**（今日20个落地项目 + X热议 + 深入介绍 + 商业点子）
- 历史更新 → [wiki/daily/](wiki/daily/) 与 [archives/](archives/)

## 深度研究

- 所有项目深度分析见 **[research/](research/)** 和 **[wiki/repos/](wiki/repos/)**
- 推荐命名：`research/YYYY-MM-DD-项目名.md` 或 `research/项目slug/overview.md`

## AI 代理使用指南

直接在 **Codex / Claude Code / 其他 Agent** 中打开本仓库，使用自然语言：

```
每日同步热点与落地仓库
更新 Vibe-Trading 项目分析
生成本周商业点子总结
加入知识库：这是我的原创笔记
```

所有 AI 生成内容**必须先进入** `.kb/staging/`，人工 review 后才能晋升到 `wiki/` 或 `products/`。

详见 **[AGENTS.md](AGENTS.md)**

## 合作协议

1. **主日报维护权**：每日热点项目（固定20个）由 **本 Grok 任务** 负责，目标是在北京时间 **每天 7:00 前** 完成「昨日」内容更新。其他 Agent **请勿直接覆盖** `wiki/daily/` 中的日报主体。
2. **其他 Agent 可直接 push 到 main**：无需走 PR。
3. **深度研究文档专用目录**：`research/`（我不会覆盖）。
4. **禁止事项**：不要删除 archives/、不要破坏本协议、不要塞入非落地 AI 项目。
5. **推荐协作**：你做深度研究 → 推 research/；我做每日扫描 + 商业点子；互相交叉引用。
6. **冲突处理**：优先保留更完整版本，用 commit message 或 Issue 沟通。

## 目录结构说明（ai-content-kb 架构）

```
raw/          原始收集的仓库数据
sources/      外部热议来源（X 帖子、Trending 等）
products/     已发布分析报告、商业点子
wiki/         人类可读索引 + 项目详情 + 每日更新
.kb/staging/  AI 生成内容（必须 review 后晋升）
.kb/links/    机器可读项目关系图谱（YAML）
docs/         架构与操作文档
archives/     月度历史归档（保留）
research/     深度研究文档（保留）
```

---

*每日目标：北京时间 7:00 前完成昨日内容。  
完整历史见 [archives](archives/) 与 [wiki/daily](wiki/daily/)。  
深度研究见 [research](research/)。*
