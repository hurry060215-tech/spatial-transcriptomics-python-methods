# Spatial Transcriptomics Python Methods
# 空间转录组 Python 方法目录

This repository is a curated Python-only map for spatial transcriptomics analysis. It is arranged by the practical order of a spatial analysis project: data model, QC, normalization, segmentation, spatial statistics, cell mapping, domains, communication, alignment, histology integration, and reporting.

本仓库是一个只收录 Python 方法的空间转录组方法目录。编排顺序按真实项目的一般路线展开：数据对象、质控、标准化、分割、空间统计、细胞映射、空间域、通讯、配准、病理图像整合和结果汇报。

## Table of Contents / 目录

- [Scope / 收录范围](#scope)
- [Recommended Workflow / 推荐分析路线](#recommended-workflow)
- [Practical Routes / 实用组合](#practical-routes)
- [Python Method Catalog / Python 方法目录](methods.md)
  - [Data containers and general toolkits](methods.md#data-containers)
  - [QC, normalization, and bias correction](methods.md#qc-normalization)
  - [Cell segmentation and reconstruction](methods.md#segmentation)
  - [Spatially variable genes and patterns](methods.md#spatial-signal)
  - [Cell mapping and deconvolution](methods.md#cell-mapping)
  - [Domains, niches, and clustering](methods.md#domains-niches)
  - [Communication and spatial networks](methods.md#communication-networks)
  - [Alignment and integration](methods.md#alignment-integration)
  - [Histology and super-resolution](methods.md#histology-super-resolution)
- [Papers / 论文](papers.md)
- [Papers with public code / 带公开代码的学习文章](papers_with_public_code.md)

<a id="scope"></a>

## Scope / 收录范围

- Include: Python packages, Python-first workflows, PyPI/conda-installable tools, or command-line tools with Python APIs.
- Exclude: R-only, Julia-only, JavaScript-only, GUI-only tools unless there is a Python implementation.
- Prefer: methods that operate on `AnnData`, `SpatialData`, `squidpy`, or well-documented `.h5ad` workflows.

- 收录：Python 包、Python 优先流程、可通过 PyPI/conda 安装的工具，或有 Python API 的命令行工具。
- 不收录：纯 R、Julia、JavaScript、纯 GUI 工具，除非有 Python 实现。
- 优先：兼容 `AnnData`、`SpatialData`、`squidpy` 或 `.h5ad` 流程的方法。

<a id="recommended-workflow"></a>

## Recommended Workflow / 推荐分析路线

| Stage | English goal | 中文目标 | Representative Python choices |
|---|---|---|---|
| 1. Data model | Store expression, coordinates, images, shapes, and labels consistently. | 统一保存表达、坐标、图像、轮廓和标签。 | `AnnData`, `Scanpy`, `Squidpy`, `SpatialData`, `Sopa` |
| 2. QC | Evaluate spots, cells, transcripts, segmentation, and tissue regions. | 检查 spot、细胞、转录本、分割和组织区域质量。 | `Scanpy`, `Squidpy`, `MerQuaCo`, `Sopa` |
| 3. Normalization | Normalize counts and handle platform-specific biases. | 标准化表达并处理平台偏差。 | `Scanpy`, `scvi-tools`, `ResolVI`, `Sopa` |
| 4. Segmentation | Convert images or transcript clouds into cells when needed. | 在需要时把图像或转录本点云转为细胞。 | `Cellpose`, `DeepCell`, `ComSeg`, `Bin2Cell`, `BIDCell`, `Segger` |
| 5. Spatial signal | Detect spatially variable genes and local gene programs. | 检测空间变异基因和局部基因程序。 | `SpatialDE`, `Squidpy`, `PROST`, `SOMDE`, `Hotspot`, `SLOPER` |
| 6. Cell mapping | Map scRNA-seq references to spatial data or infer cell-type abundance. | 把单细胞参考映射到空间数据或推断细胞组成。 | `cell2location`, `Tangram`, `DestVI`, `Stereoscope`, `CytoSPACE`, `SpaGE` |
| 7. Domains and niches | Identify spatial domains, cell niches, and microenvironments. | 识别空间域、细胞 niche 和微环境。 | `SpaGCN`, `stLearn`, `STAGATE`, `GraphST`, `CellCharter`, `NicheCompass`, `GASTON` |
| 8. Communication | Infer spatially constrained signaling and transport. | 推断带空间约束的信号通讯和转运。 | `COMMOT`, `SpaOTsc`, `Squidpy`, `CellPhoneDB`, `LIANA+` |
| 9. Alignment | Align slices, samples, or modalities. | 配准切片、样本或多模态数据。 | `PASTE`, `PASTE2`, `STalign`, `moscot`, `TOAST` |
| 10. Histology integration | Combine H&E or multiplex images with expression. | 整合 H&E 或多重图像与表达。 | `HEST`, `TESLA`, `ST-Net`, `DeepSpot`, `SpaHDmap` |
| 11. Reporting | Produce reproducible notebooks and spatial figures. | 输出可复现 notebook 和空间图。 | `Scanpy`, `Squidpy`, `Sopa`, `napari`, `matplotlib` |

<a id="practical-routes"></a>

## Practical Routes / 实用组合

**10x Visium / spot-based data**

Use `Scanpy` for baseline QC, `Squidpy` for spatial graphs and plotting, `SpatialDE` or `SOMDE` for spatially variable genes, `cell2location` or `Tangram` for mapping, and `SpaGCN`, `STAGATE`, or `GraphST` for spatial domains.

**10x Visium / spot 数据**

可用 `Scanpy` 做基础质控，`Squidpy` 建空间图和绘图，`SpatialDE` 或 `SOMDE` 找空间变异基因，`cell2location` 或 `Tangram` 做细胞映射，`SpaGCN`、`STAGATE` 或 `GraphST` 做空间域。

**Visium HD / high-resolution binned data**

Start from `AnnData` or `SpatialData`. Use `Bin2Cell`, `Cellpose`, or `Sopa` for cell-level reconstruction where appropriate, then analyze with `Squidpy`, `cell2location`, `CellCharter`, or `NicheCompass`.

**Visium HD / 高分辨率 bin 数据**

建议从 `AnnData` 或 `SpatialData` 开始。需要细胞级重建时可考虑 `Bin2Cell`、`Cellpose` 或 `Sopa`，后续用 `Squidpy`、`cell2location`、`CellCharter` 或 `NicheCompass` 分析。

**Xenium / CosMx / MERFISH / MERSCOPE**

Use `Sopa` and `SpatialData` for large images and shapes, `MerQuaCo` for QC, `Cellpose`, `DeepCell`, `ComSeg`, or `Segger` for segmentation-related work, then analyze neighborhoods with `Squidpy`, `COMMOT`, `CellCharter`, or `NicheCompass`.

**Xenium / CosMx / MERFISH / MERSCOPE**

大图像和空间轮廓建议用 `Sopa` 与 `SpatialData` 管理，质控可用 `MerQuaCo`，分割相关工作可用 `Cellpose`、`DeepCell`、`ComSeg` 或 `Segger`，邻域和通讯分析可用 `Squidpy`、`COMMOT`、`CellCharter` 或 `NicheCompass`。

## Files / 文件

- [methods.md](methods.md): Python methods arranged by analysis step.
- [papers.md](papers.md): reviews, benchmarks, and representative method papers.
- [papers_with_public_code.md](papers_with_public_code.md): learning-oriented papers, protocols, benchmarks, and tutorials with public code.
- [CONTRIBUTING.md](CONTRIBUTING.md): lightweight rules for adding new methods.

- [methods.md](methods.md)：按分析步骤整理的 Python 方法清单。
- [papers.md](papers.md)：综述、benchmark 和代表性方法论文。
- [papers_with_public_code.md](papers_with_public_code.md)：带公开代码、适合跟着学习的文章、协议、benchmark 和教程。
- [CONTRIBUTING.md](CONTRIBUTING.md)：新增方法的简单规范。

## Source Inspiration / 参考来源

This repository is inspired by public spatial omics lists, especially:

- [crazyhottommy/awesome_spatial_omics](https://github.com/crazyhottommy/awesome_spatial_omics)
- [p-gueguen/Spatial_transcriptomics_tools](https://github.com/p-gueguen/Spatial_transcriptomics_tools)

The entries here are reorganized by Python-only usability and by a practical analysis path.
