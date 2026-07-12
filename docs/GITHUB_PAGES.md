# GitHub Pages 部署说明

本仓库使用 **MkDocs Material** 构建站点，由 GitHub Actions 自动部署。

## 自动部署（推荐，已配置）

- Workflow：`.github/workflows/pages.yml`
- 触发：push 到 `main` 或手动 workflow_dispatch
- 步骤：checkout → setup Python → install deps → `mkdocs build --strict` → upload artifact → deploy
- 站点地址：https://liaoqiaochunfengchuijiuxing.github.io/hot-opensource-projects/

## 手动启用（首次需要）

1. 打开仓库 Settings → Pages
2. Source 选择 **GitHub Actions**（推荐，与 workflow 匹配）
3. 或 Branch: `main` / Folder: `/ (root)`（如果使用旧 Jekyll 方式）

## 本地验证

```bash
pip install -r requirements.txt
mkdocs serve          # 预览 http://127.0.0.1:8000
mkdocs build --strict # 与 CI 一致，检查导航断链
```

## 导航与侧边栏

- 配置文件：根目录 `mkdocs.yml`
- 源内容：`docs/`
- **任何导航变更必须遵循 AGENTS.md 中的「站点管理详细契约」**
- 当前已优化：分组 nav、sections、expand、toc.integrate、git-revision-date 等

详见 [AGENTS.md](AGENTS.md) 的站点管理章节。
