---
layout: default
title: Agent Operating Rules
---

# Agent Operating Rules
# AI 落地实用仓库索引（hot-opensource-projects）

本仓库是 **AI 落地实用开源仓库的索引与分析库**。  
每天从 GitHub Trending + X 热议中精选 **固定 20 个** 高质量、可落地的 AI / Agent / RAG / Agentic 项目，并进行结构化分析 + 商业洞察。

## 核心原则（必须严格遵守）

1. **原文保持可信**：`raw/` 与 `sources/` 是权威来源
2. **Wiki 保持可读**：`wiki/` 是人类界面，必须引用原文
3. **图谱保持可查**：`.kb/links/` 存储 typed relationships
4. **AI 输出保持可审核**：所有 AI 生成内容 **必须先进入** `.kb/staging/`，人工 review 后才能晋升
5. **只收落地项目**：必须是生产就绪、可部署、有真实案例或完整 pipeline 的项目

---

## 每日核心工作流（最重要）

### `每日同步热点与落地仓库`

**触发条件**：每天北京时间 7:00 前完成「昨日」内容。

**执行步骤**（严格按顺序）：
1. 从 **GitHub Trending**（尤其是 AI / Agent / LLM 相关）和 **X 热议** 中各自选取约 20 个候选项目
2. 去重后，按「AI落地可用」标准精选 **固定 20 个** 高质量项目
3. 生成完整日报内容（四部分结构），写入 `.kb/staging/daily/YYYY-MM-DD.md`
4. 更新 `wiki/index.md` 和对应 `wiki/categories/` 中的链接
5. 为新增或重要项目生成/更新 `wiki/repos/项目名.md` 深度分析（放入 staging）
6. 生成商业点子总结，放入 `.kb/staging/products/`
7. 输出 review 报告，等待人工确认后晋升到正式目录

**AI落地可用筛选标准**（必须全部满足）：
- 有完整 README 和可运行示例
- 支持实际部署（Docker / 本地 / 云端）
- 社区活跃或有真实落地案例
- 解决真实生产问题（而非纯 demo / 论文代码）
- 与 Agent / RAG / Coding / 内容 / 交易 / 安全等相关

### `更新指定项目分析`
为 `wiki/repos/项目名.md` 生成或更新深度分析（背景、核心功能、落地价值、优缺点、最新更新、使用建议）。

### `生成商业点子总结`
基于今日/本周 20 个项目，提炼 5-7 个可直接落地的商业方向，输出到 `products/`。

### `review and publish`
审核 `.kb/staging/` 中的内容：
- 验证引用、路径、落地标准
- 通过后晋升到 `wiki/daily/`、`wiki/repos/`、`products/`
- 更新 `wiki/index.md`

### `查询知识库`
从 `wiki/` + `.kb/links/` 导航，返回带仓库相对路径引用的答案。

---

## 目录语义与职责

| 目录 | 角色 | 谁可以写 | 权威？ |
|------|------|----------|--------|
| `raw/` | 原始收集的仓库数据 | Agent + 人类 | 是 |
| `sources/` | 外部热议来源（X、Trending） | Agent + 人类 | 是 |
| `products/` | 已发布分析报告、商业点子 | 仅 review 后 | 是 |
| `wiki/daily/` | 每日完整日报（20个项目 + 观点 + 介绍 + 商业点子） | 仅 Grok 任务 review 后 | 否（引用） |
| `wiki/repos/` | 单项目深度分析页 | Agent + 人类 review 后 | 否 |
| `wiki/categories/` | 分类索引 | Agent review 后 | 否 |
| `wiki/index.md` | 总索引 | Agent review 后 | 否 |
| `.kb/staging/` | **所有 AI 生成内容的唯一入口** | Agent | 否 |
| `.kb/links/` | 已审核项目关系图谱（YAML） | review 后 | 可重建 |
| `research/` | 其他 Agent 的深度研究文档 | 其他 Agent 直接 push | 保留 |
| `archives/` | 月度历史归档 | Grok 任务 | 保留 |

---

## 写入边界（硬规则）

- **所有 AI 输出必须先进入 `.kb/staging/`**
- 不要直接修改已审核的 `wiki/` 或 `products/` 内容
- 不要删除 `archives/` 或 `research/`
- 不要把非落地 AI 项目塞进每日 20 个列表
- 保持 **全中文**
- 每日日报必须严格四部分结构：
  1. 20个高质量落地项目表格
  2. X 上热议观点（详细）
  3. 重点项目深入介绍（十分详细）
  4. 基于今日20个项目的商业点子推荐

## Review 规则

决定是否晋升的优先级：
1. review status
2. 是否符合「AI落地可用」标准
3. 落地价值与热度
4. 来源可信度

**原则：宁可漏合，也不误合。**
