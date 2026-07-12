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
6. **站点保持可导航**：MkDocs 站点（docs/ + mkdocs.yml）必须与内容同步，导航清晰、侧边栏可用

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
8. **晋升后必须同步到站点**：见下方「站点管理契约」

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
- **同步 docs/ 与更新 mkdocs.yml nav**（强制）

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
| `docs/` | **MkDocs 站点源**（与 wiki 镜像） | review 后 + 站点维护 | 站点权威 |
| `.kb/staging/` | **所有 AI 生成内容的唯一入口** | Agent | 否 |
| `.kb/links/` | 已审核项目关系图谱（YAML） | review 后 | 可重建 |
| `research/` | 其他 Agent 的深度研究文档 | 其他 Agent 直接 push | 保留 |
| `archives/` | 月度历史归档 | Grok 任务 | 保留 |
| `mkdocs.yml` | 站点导航、主题、插件配置 | 仅站点维护任务 | 是 |

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
- **站点文件（docs/、mkdocs.yml）变更必须符合站点管理契约**

## Review 规则

决定是否晋升的优先级：
1. review status
2. 是否符合「AI落地可用」标准
3. 落地价值与热度
4. 来源可信度

**原则：宁可漏合，也不误合。**

---

# 站点管理详细契约（MkDocs Site Management Contract）

> 本契约是所有 Agent / Grok 任务维护本仓库 GitHub Pages 站点的**强制规范**。  
> 站点基于 **MkDocs Material**，源目录 = `docs/`，配置 = 根目录 `mkdocs.yml`。  
> 部署由 `.github/workflows/pages.yml` 在 push main 时自动完成（mkdocs build --strict → deploy）。

## 1. 双写同步原则（wiki ↔ docs）

| 内容类型 | 权威源 | 必须同步到 | 说明 |
|----------|--------|------------|------|
| 日报 | wiki/daily/ | docs/daily/ | 文件名完全一致 YYYY-MM-DD.md |
| 分类页 | wiki/categories/ | docs/categories/ | 文件名一致，内容镜像 |
| 总索引 | wiki/index.md | docs/index.md | 快速导航与分类列表保持同步 |
| 深度研究入口 | research/ | docs/research/ | README 镜像 |
| 代理规则 | AGENTS.md (root) | docs/AGENTS.md | 保持一致（docs 版可精简） |
| 其他站点文档 | docs/ 内 | - | ARCHITECTURE / CONTRIBUTING / GITHUB_PAGES / GRAPH_SCHEMA 仅存在于 docs/ |

**硬规则**：
- 晋升日报时，必须 **同时** 写入 `wiki/daily/` 和 `docs/daily/`
- 更新分类时，必须 **同时** 更新两边
- 任何一方缺失都会导致站点导航失效或内容不全

## 2. 导航（nav）维护规则（最关键）

`mkdocs.yml` 的 `nav` 是站点侧边栏 + 顶部 tabs 的唯一真相源。

### 当前推荐结构（2026-07-12 优化版）

```yaml
nav:
  - 首页: index.md
  - 日报:
    - 2026-07-12: daily/2026-07-12.md
    # 新日报必须插入到最顶部（最新在前）
  - 分类:
    - Agent Frameworks: categories/agent-frameworks.md
    - RAG Systems: categories/rag-systems.md
    - Multi-Agent: categories/multi-agent.md
    - Content & Creative: categories/content-creative.md
    - Local AI: categories/local-ai.md
    - Agent Safety: categories/agent-safety.md
    - LLM Deployment: categories/llm-deployment.md
  - 深度研究: research/README.md
  - 站点管理:
    - 代理规则 (AGENTS): AGENTS.md
    - 架构说明: ARCHITECTURE.md
    - 贡献指南: CONTRIBUTING.md
    - 部署说明: GITHUB_PAGES.md
    - 图谱 Schema: GRAPH_SCHEMA.md
```

### 必须遵守的 nav 变更规则

1. **新增日报**：
   - 把新日期插入 `日报:` 列表 **最顶部**
   - 保留至少最近 7 天（或全部，按体积决定）
   - 同步更新 `docs/index.md` 的「最新每日更新」列表

2. **新增分类**：
   - 在 `分类:` 下添加新条目（中文标题 + 正确相对路径）
   - 同时创建 `docs/categories/xxx.md` 和 `wiki/categories/xxx.md`
   - 更新 `docs/index.md` 的「按分类浏览」

3. **禁止事项**：
   - 不要出现重复链接（如「首页」和「项目索引」都指向 index.md）
   - 不要把站点管理文档放在顶级（必须在「站点管理」section 下）
   - 不要删除「站点管理」section
   - 路径必须相对于 docs/（不要带 docs/ 前缀）

4. **变更后验证**：
   - 本地 `mkdocs build --strict` 必须通过
   - 推送后检查 GitHub Pages 是否成功部署

## 3. 侧边栏与主题优化规则

当前启用的 Material features（不可随意删除）：

```yaml
features:
  - navigation.tabs          # 顶部标签页
  - navigation.sections      # 侧边栏分组
  - navigation.expand        # 默认展开
  - navigation.top           # 回到顶部
  - navigation.indexes       # section index 支持
  - navigation.footer        # 页脚导航
  - search.suggest
  - search.highlight
  - content.code.copy
  - content.action.edit
  - toc.follow
  - toc.integrate            # TOC 集成到侧边栏
```

**优化原则**：
- 保持 `navigation.sections` + `navigation.expand` 使侧边栏清晰分组
- 日报 section 只放日期，不放其他
- 分类 section 按字母或逻辑顺序（当前：Frameworks → RAG → Multi → Content → Local → Safety → Deployment）
- 站点管理 section 固定放最后
- 不要添加过多顶级项（最多 5 个顶级）

插件必须包含：
- search
- tags
- git-revision-date-localized（显示页面更新时间）

## 4. 内容晋升到站点的完整流程

```
.kb/staging/xxx.md
       ↓ review 通过
wiki/daily/ 或 wiki/categories/ 或 products/
       ↓ 强制同步
docs/daily/ 或 docs/categories/ 等
       ↓ 更新
mkdocs.yml 的 nav（如有新文件）
       ↓ 更新
docs/index.md 快速导航
       ↓ push main
GitHub Actions 自动 mkdocs build --strict + deploy
```

**Checklist（每次 review and publish 必须执行）**：
- [ ] docs/ 对应文件已创建/更新
- [ ] wiki/ 与 docs/ 内容一致（日报/分类）
- [ ] mkdocs.yml nav 已正确插入新日报/新分类
- [ ] docs/index.md 已更新最新链接
- [ ] 无断链（本地或 CI 检查）
- [ ] commit message 明确写「sync site: ...」

## 5. 禁止操作（会导致站点损坏）

- 直接编辑已部署的 site/（只读，由 CI 生成）
- 在 mkdocs.yml 中使用绝对路径或错误相对路径
- 删除 docs/ 下的任何已发布日报
- 修改 theme.palette / language 而不通知维护者
- 关闭 --strict 模式（workflow 必须保持）
- 在 docs/ 中放入非 Markdown 或未声明的大文件

## 6. 本地开发与验证命令

```bash
# 安装
pip install -r requirements.txt

# 预览（推荐）
mkdocs serve

# 严格构建（与 CI 一致）
mkdocs build --strict

# 检查 nav 是否有断链
mkdocs build --strict 2>&1 | cat
```

## 7. 变更审批与通知

- 任何对 `mkdocs.yml` 的结构变更（增加/删除 section、改 features）必须在 commit message 写「nav: ...」
- 重大导航重构先更新本契约，再改配置
- 其他 Agent 可直接 push 内容，但 **nav 与主题变更优先由 Grok 维护**

---

**本契约生效时间**：2026-07-12  
**维护者**：Grok + 料峭春风吹酒醒  
**最后同步**：与 mkdocs.yml 优化版本保持一致
