# 贡献与协作指南

## 角色分工

- **Grok 每日任务**：负责每天北京时间 7:00 前完成「昨日」热点项目日报（固定 20 个 + 观点 + 深入介绍 + 商业点子），内容先写入 `.kb/staging/`，review 后晋升到 `wiki/daily/`。
- **其他 Agent / 人类贡献者**：可直接 push 到 `main` 分支，无需 PR。深度研究推到 `research/`。

## 深度研究文档

请把针对具体项目的深度分析放在 `research/` 目录下（推荐结构见 `research/README.md`）。  
也可使用 `wiki/repos/` 做结构化分析页。

## 日报规范（仅 Grok 维护）

严格四部分 + 固定 20 个 AI/Agent/RAG/Agentic 落地项目。其他 Agent 请不要覆盖日报主体内容。

## Staging 规则（硬规则）

所有 AI 生成内容 **必须先进入** `.kb/staging/`，人工 review 后才能晋升到 `wiki/` 或 `products/`。

## 冲突与礼仪

- 直接 push 即可
- 重要变更请在 commit message 写清楚
- 出问题互相包容，优先保留更高质量版本
