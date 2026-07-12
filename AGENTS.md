# Agent Operating Rules - AI 落地实用仓库索引

本仓库是 **AI 落地实用开源仓库的索引与分析库**。  
目标：每天从 GitHub Trending + X 热议中精选固定 **20 个** 高质量、可落地的 AI / Agent / RAG / Agentic 项目，并进行结构化分析。

## 核心原则（严格遵守）

- **原文保持可信**：raw/ 与 sources/ 是权威来源
- **Wiki 保持可读**：wiki/ 是人类界面，必须引用原文
- **图谱保持可查**：.kb/links/ 存储 typed relationships
- **AI 输出保持可审核**：所有 AI 生成内容必须先进入 `.kb/staging/`，人工 review 后才能晋升

## 每日核心工作流

### `每日同步热点与落地仓库`
1. 从 GitHub Trending（AI/Agent 分类）和 X 搜索收集今日热门仓库
2. 按「AI落地可用」标准筛选（生产就绪、可部署、有真实案例、社区活跃、有文档）
3. 为新项目生成结构化分析页（背景、核心功能、落地价值、优缺点、最新更新）
4. 更新 `wiki/index.md` 和对应 `wiki/categories/`
5. 把生成内容全部放入 `.kb/staging/`
6. 报告需要人工 review 的关键变更

### `更新指定项目分析`
为 `wiki/repos/项目名.md` 生成或更新深度分析。

### `生成商业点子总结`
基于当前 20 个项目，提炼可落地的商业方向，输出到 `products/`。

### `加入知识库`
把用户提供的材料按 provenance 放入 raw/ 或 sources/，并生成 staging 候选。

### `查询知识库`
从 wiki/ 和 .kb/links/ 导航，返回带引用的答案。

### `review and publish index`
审核 `.kb/staging/` 中的内容，验证后晋升到 wiki/ 或 products/。

## 目录语义

| 目录 | 角色 | 权威？ |
|------|------|--------|
| `raw/` | 原始收集的仓库数据 | 是（owner intent） |
| `sources/` | 外部热议来源（X、Trending） | 是（external claims） |
| `products/` | 已发布分析报告、商业点子 | 是（published expression） |
| `wiki/` | 人类可读索引 + 项目详情 + 每日更新 | 否（必须引用原文） |
| `.kb/staging/` | AI 生成内容（待审核） | 否 |
| `.kb/links/` | 已审核项目关系图谱（YAML） | 可重建 |
| `research/` | 深度研究文档（其他 Agent 专用） | 保留 |
| `archives/` | 月度历史归档 | 保留 |

## 写入边界

- 所有 AI 输出必须先进入 `.kb/staging/`
- 不要直接修改已审核的 wiki/ 或 products/ 内容
- 不要删除 archives/ 或 research/
- 不要把非落地 AI 项目塞进每日 20 个列表
- 保持全中文

## Review 规则

决定因素：
1. review status
2. 落地价值
3. 热度与来源可信度
4. 人类所有权

宁可漏合，也不误合。
