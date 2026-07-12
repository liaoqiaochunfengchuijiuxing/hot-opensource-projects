# Agent Operating Rules

本仓库是 **AI 落地实用开源仓库的索引与分析库**。  
每天从 GitHub Trending + X 热议中精选 **固定 20 个** 高质量、可落地的 AI / Agent / RAG / Agentic 项目，并进行结构化分析 + 商业洞察。

## 核心原则（必须严格遵守）

1. **原文保持可信**：`raw/` 与 `sources/` 是权威来源
2. **Wiki 保持可读**：`wiki/` / `docs/` 是人类界面，必须引用原文
3. **图谱保持可查**：`.kb/links/` 存储 typed relationships
4. **AI 输出保持可审核**：所有 AI 生成内容 **必须先进入** `.kb/staging/`，人工 review 后才能晋升
5. **只收落地项目**：必须是生产就绪、可部署、有真实案例或完整 pipeline 的项目
6. **站点保持可导航**：MkDocs 站点必须与内容同步（详见下方「站点管理契约」）

## 每日核心工作流

### `每日同步热点与落地仓库`

**触发条件**：每天北京时间 7:00 前完成「昨日」内容。

**执行步骤**：
1. 从 GitHub Trending + X 热议中各自选取约 20 个候选项目
2. 去重后，按「AI落地可用」标准精选 **固定 20 个** 高质量项目
3. 生成完整日报内容，写入 `.kb/staging/daily/YYYY-MM-DD.md`
4. 更新导航和分类
5. 生成商业点子总结
6. **晋升后同步 docs/ 并更新 mkdocs.yml nav**（见站点管理契约）

**AI落地可用筛选标准**：
- 有完整 README 和可运行示例
- 支持实际部署（Docker / 本地 / 云端）
- 社区活跃或有真实落地案例
- 解决真实生产问题
- 与 Agent / RAG / Coding / 内容 / 交易 / 安全等相关

### 其他命令
- `更新指定项目分析`
- `生成商业点子总结`
- `review and publish`

---

# 站点管理详细契约（MkDocs）

> 完整版见仓库根目录 [AGENTS.md](https://github.com/liaoqiaochunfengchuijiuxing/hot-opensource-projects/blob/main/AGENTS.md#站点管理详细契约mkdocs-site-management-contract)。  
> 本页为站点内精简版，强制规则不变。

## 1. 双写同步（wiki ↔ docs）

- 日报：`wiki/daily/` ↔ `docs/daily/`（文件名完全一致）
- 分类：`wiki/categories/` ↔ `docs/categories/`
- 总索引：`wiki/index.md` ↔ `docs/index.md`
- 晋升时必须两边同时写入

## 2. 导航（nav）维护硬规则

`mkdocs.yml` 是侧边栏 + tabs 的唯一真相源。

**新增日报必须做的事**：
1. 把新日期插入 `日报:` section **最顶部**
2. 同步更新 `docs/index.md` 最新链接
3. 保证路径相对 docs/ 正确

**当前结构**（已优化）：
- 首页
- 日报（最新在上）
- 分类（7 个类别，含 LLM Deployment）
- 深度研究
- 站点管理（AGENTS / 架构 / 贡献 / 部署 / Schema）

## 3. 侧边栏与主题

启用 features（不可删）：
- navigation.tabs / sections / expand / top / indexes / footer
- toc.follow + toc.integrate
- search.suggest / highlight
- content.code.copy / action.edit

插件：search + tags + git-revision-date-localized

## 4. 晋升 Checklist

- [ ] docs/ 文件已同步
- [ ] mkdocs.yml nav 已更新
- [ ] docs/index.md 已更新
- [ ] `mkdocs build --strict` 通过
- [ ] commit 信息含 site sync 说明

## 5. 禁止

- 直接改 site/（CI 生成）
- 重复 nav 链接
- 删除已发布日报
- 关闭 strict 模式

本地验证：
```bash
pip install -r requirements.txt
mkdocs serve
mkdocs build --strict
```

**本契约与根目录 AGENTS.md 保持一致，最后更新 2026-07-12。**
