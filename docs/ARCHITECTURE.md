# Architecture - AI 落地实用仓库索引

## 分层模型

| Layer | Purpose | Authoritative? |
|-------|---------|----------------|
| `raw/` | 原始收集的仓库数据 | 是 |
| `sources/` | 外部热议来源 | 是 |
| `products/` | 已发布分析与商业点子 | 是 |
| `wiki/` | 人类可读索引 + 项目详情 + 每日更新 | 否（引用原文） |
| `.kb/staging/` | AI 生成候选 | 否 |
| `.kb/links/` | 已审核关系图谱 | 可重建 |
| `research/` | 深度研究（其他 Agent） | 保留 |
| `archives/` | 月度历史归档 | 保留 |

## 为什么采用 review-first

AI 输出廉价但信任昂贵。  
所有生成内容必须经过 staging → human review → promote 流程，防止污染永久知识库。

## 每日生命周期

1. 收集（raw/ + sources/）
2. AI 生成候选 → `.kb/staging/`
3. 人工 review
4. 晋升到 wiki/ 或 products/
5. 更新索引与关系图谱

## Scaling Path

1. 验证角色与流程（当前阶段）
2. 添加 schema linting
3. 添加文件 manifest + hash
4. 按需引入向量检索
