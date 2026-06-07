# Contributing
# 贡献规范

Add a method only when it has a working Python package, Python-first workflow, or documented Python API.

新增方法时，请确认它有可运行的 Python 包、以 Python 为主的流程，或明确的 Python API。

## Entry Format / 条目格式

Use the existing table structure:

- Method name
- Main use
- Chinese explanation
- Link to package, documentation, or paper

请沿用现有表格结构：

- 方法名
- 主要用途
- 中文说明
- 包、文档或论文链接

## Quality Rules / 质量规则

- Keep descriptions short and factual.
- Prefer peer-reviewed papers; preprints are acceptable when no paper exists.
- Avoid adding R-only methods to this repository.
- Mention whether the method expects `AnnData`, `SpatialData`, raw transcript coordinates, image masks, or other input formats when that matters.

- 描述要短、准确、可判断。
- 优先收录正式发表论文；没有正式论文时可收录预印本。
- 不要把纯 R 方法加入本仓库。
- 如果输入格式很关键，请说明该方法需要 `AnnData`、`SpatialData`、原始转录本坐标、图像 mask 或其他格式。

