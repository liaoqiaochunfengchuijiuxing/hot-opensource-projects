# Graph Schema

关系以 YAML sidecar 形式存储在 `.kb/links/`。

## 必填字段

- `schema_version`
- `source`（仓库相对路径）
- `source_type`
- `title`
- `review_status`（draft / reviewed）
- `edges` 列表

## Edge 类型

- `mentions`
- `explains`
- `uses`
- `derived_from`
- `part_of`
- `related_to`
- `alias_of`

每个 edge 包含：`target`, `target_type`, `confidence`, `evidence`。
