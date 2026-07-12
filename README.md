---
layout: default
title: AI 落地实用开源仓库索引
---

# AI 落地实用开源仓库索引与分析库

> **目标**：每天从 GitHub Trending + X 热议中精选 **固定 20 个** 高质量、可落地的 AI / Agent / RAG / Agentic 项目，并提供结构化分析与商业洞察。  
> 架构：原文可信 · Wiki 可读 · 图谱可查 · AI 输出可审核（基于 ai-content-kb） · **站点可导航**

## 快速导航

| 入口 | 说明 |
|------|------|
| [最新日报](wiki/daily/) | 每日 20 个落地项目 + X 热议 + 深入介绍 + 商业点子 |
| [项目总索引](wiki/index.md) | 所有已收录项目 |
| [分类浏览](wiki/categories/) | 按类型快速查找 |
| [深度研究](research/) | 其他 Agent 推送的详细研究文档 |
| [商业点子](products/) | 已发布的商业方向总结 |
| [AGENTS.md](AGENTS.md) | AI 代理操作规则、工作流与**站点管理详细契约** |
| [MkDocs 站点](https://liaoqiaochunfengchuijiuxing.github.io/hot-opensource-projects/) | 优化后的导航 + 侧边栏（Material 主题） |

## 按分类浏览

- [Agent Frameworks & Orchestration](wiki/categories/agent-frameworks.md)
- [RAG & Knowledge Systems](wiki/categories/rag-systems.md)
- [LLM Deployment & Serving](wiki/categories/llm-deployment.md)
- [Multi-Agent & Workflow](wiki/categories/multi-agent.md)
- [Content & Creative AI](wiki/categories/content-creative.md)
- [Local & Self-Hosted AI](wiki/categories/local-ai.md)
- [Agent Safety & Governance](wiki/categories/agent-safety.md)

## 最新每日更新

- **[2026-07-12](wiki/daily/2026-07-12.md)**（今日完整内容）
- 历史更新 → [wiki/daily/](wiki/daily/) 与 [archives/](archives/)

## AI 代理使用指南

在 **Codex / Claude Code / Grok** 中打开本仓库，直接说：

```
每日同步热点与落地仓库
更新 Vibe-Trading 项目分析
生成本周商业点子总结
review and publish
```

所有 AI 生成内容会自动进入 `.kb/staging/`，等待 review 后晋升。  
**站点（MkDocs 导航 / 侧边栏 / docs 同步）变更必须严格遵循 AGENTS.md 中的「站点管理详细契约」。**

详见 **[AGENTS.md](AGENTS.md)**

## 合作协议（所有 Agent 必须遵守）

1. **主日报维护权**：每日 20 个项目日报由 **Grok 任务** 负责，目标北京时间 **7:00 前** 完成昨日内容。其他 Agent **请勿覆盖** `wiki/daily/` 主体。
2. **其他 Agent 可直接 push 到 main**：无需 PR。
3. **深度研究**：推到 `research/`（我不会覆盖）。
4. **AI 输出规则**：必须先进入 `.kb/staging/`，review 后才能晋升。
5. **禁止事项**：不要删除 archives/ 或 research/，不要塞入非落地项目。
6. **冲突处理**：优先保留更完整版本，用 commit message 沟通。
7. **站点变更**：nav / 主题 / 侧边栏优化优先由 Grok 维护，遵循站点管理契约。

## 目录结构

```
raw/            原始收集数据
sources/        外部热议来源（X / Trending）
products/       已发布分析与商业点子
wiki/daily/     每日完整日报
wiki/repos/     单项目深度分析
wiki/categories/ 分类索引
wiki/index.md   总索引
.kb/staging/    AI 生成内容入口（必须 review）
.kb/links/      项目关系图谱
research/       其他 Agent 深度研究（保留）
archives/       月度历史归档（保留）
docs/           MkDocs 站点源（与 wiki 镜像 + 站点文档）
mkdocs.yml      站点导航、侧边栏、主题配置（权威）
```

---

*每日目标：北京时间 7:00 前完成昨日内容。*  
*完整历史见 [archives](archives/) 与 [wiki/daily](wiki/daily/)。*  
*深度研究见 [research](research/)。*  
*站点管理契约见 [AGENTS.md](AGENTS.md)。*
