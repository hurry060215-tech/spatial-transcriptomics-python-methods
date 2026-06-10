# Python Papers with Public Code
# 带公开代码的 Python 空间转录组学习文章

This page is a learning-oriented reading list. It focuses on papers, protocols, benchmarks, and tutorial-style resources that are useful for learning the Python methods listed in this repository and that provide public code, package source, analysis scripts, or executable notebooks.

本页是面向学习的阅读清单。收录重点不是“所有论文”，而是能帮助学习本仓库 Python 方法、并且带公开代码、包源码、分析脚本或可运行 notebook 的文章、协议、benchmark 和教程型资源。

## Table of Contents / 目录

- [How to Use This List / 如何使用](#how-to-use)
- [Core Python Workflow Papers / Python 核心流程文章](#core-workflow)
- [Task-Oriented Papers with Code / 按任务整理的文章与代码](#task-oriented)
- [Suggested Learning Order / 建议学习顺序](#learning-order)
- [Selection Rules / 收录规则](#selection-rules)

<a id="how-to-use"></a>

## How to Use This List / 如何使用

- Read the **paper** for the modeling idea.
- Open the **code** link and run a notebook or minimal example.
- Keep track of input objects: `AnnData`, `SpatialData`, raw transcript coordinates, masks, images, or `h5ad`.
- For deep-learning methods, check GPU requirements before trying the full paper workflow.

- 先读 **Paper** 理解建模思想。
- 再打开 **Code** 链接，优先跑 notebook 或最小示例。
- 记录输入对象：`AnnData`、`SpatialData`、原始转录本坐标、mask、图像或 `h5ad`。
- 深度学习方法先看 GPU 要求，不要一开始就跑完整论文流程。

<a id="core-workflow"></a>

## Core Python Workflow Papers / Python 核心流程文章

| Stage | Paper / Resource | Methods | Public code / tutorial | Why learn it / 学习价值 |
|---|---|---|---|---|
| Single-cell foundation | [Scanpy: a scalable toolkit for analyzing single-cell gene expression data](https://doi.org/10.1186/s13059-017-1382-0) | Scanpy, AnnData | [scverse/scanpy](https://github.com/scverse/scanpy), [Scanpy docs](https://scanpy.readthedocs.io/) | Most Python spatial workflows inherit Scanpy/AnnData preprocessing habits. / Python 空转多数继承 Scanpy/AnnData 习惯。 |
| Spatial workflow | [Squidpy: a scalable framework for spatial omics analysis](https://doi.org/10.1038/s41592-021-01358-2) | Squidpy | [scverse/squidpy](https://github.com/scverse/squidpy), [Squidpy docs](https://squidpy.readthedocs.io/) | Core Python entry for spatial graphs, neighborhoods, image features, and plotting. / Python 空转空间图和邻域分析入口。 |
| Probabilistic modeling | [A Python library for probabilistic analysis of single-cell omics data](https://doi.org/10.1038/s41587-021-01206-w) | scvi-tools, DestVI, cell2location ecosystem | [scverse/scvi-tools](https://github.com/scverse/scvi-tools), [scvi-tools docs](https://scvi-tools.org/) | Learn the probabilistic modeling style behind many modern spatial methods. / 学现代概率模型风格。 |
| Spatial data model | [SpatialData documentation and examples](https://spatialdata.scverse.org/) | SpatialData | [scverse/spatialdata](https://github.com/scverse/spatialdata) | Important for large images, coordinates, labels, and shapes. / 学大图像、坐标、轮廓和标签的数据组织。 |
| Image-based processing | [Sopa: a technology-invariant pipeline for analyses of image-based spatial omics](https://doi.org/10.1038/s41467-024-48981-z) | Sopa, SpatialData | [gustaveroussy/sopa](https://github.com/gustaveroussy/sopa), [Sopa docs](https://gustaveroussy.github.io/sopa/) | Practical framework for Xenium, MERSCOPE, CosMx, and other image-based platforms. / 成像型空转实用流程。 |

<a id="task-oriented"></a>

## Task-Oriented Papers with Code / 按任务整理的文章与代码

| Task | Paper | Methods | Public code / tutorial | What to learn / 学什么 |
|---|---|---|---|---|
| Spatially variable genes | [SpatialDE: identification of spatially variable genes](https://doi.org/10.1038/nmeth.4636) | SpatialDE | [Teichlab/SpatialDE](https://github.com/Teichlab/SpatialDE) | Gaussian-process view of spatial expression variation. / 学高斯过程空间变异基因。 |
| Cell mapping | [Deep learning and alignment of spatially resolved single-cell transcriptomes with Tangram](https://doi.org/10.1038/s41592-021-01264-7) | Tangram | [broadinstitute/Tangram](https://github.com/broadinstitute/Tangram), [Tangram tutorial](https://tangram-sc.readthedocs.io/en/latest/tutorial_sq_link.html) | Map sc/snRNA-seq cells or genes into spatial coordinates. / 学单细胞到空间映射。 |
| Cell mapping / deconvolution | [Cell2location maps fine-grained cell types in spatial transcriptomics](https://doi.org/10.1038/s41587-021-01139-4) | cell2location | [BayraktarLab/cell2location](https://github.com/BayraktarLab/cell2location), [cell2location paper repo](https://github.com/vitkl/cell2location_paper), [lymph node tutorial](https://cell2location.readthedocs.io/en/latest/notebooks/cell2location_tutorial.html) | Bayesian cell-type abundance mapping with scRNA-seq references. / 学概率反卷积和细胞丰度映射。 |
| Continuous cell states | [A data-driven approach to predict and infer cell-type-specific gene expression in spatial transcriptomics](https://doi.org/10.1038/s41587-022-01272-8) | DestVI | [scvi-tools DestVI docs](https://docs.scvi-tools.org/en/stable/user_guide/models/destvi.html) | Infer continuous cell states in spatial data. / 学连续细胞状态反卷积。 |
| Deconvolution | [Probabilistic cell-type assignment of spatially resolved transcriptomics data](https://doi.org/10.1038/s41467-020-15968-5) | Stereoscope | [almaan/stereoscope](https://github.com/almaan/stereoscope) | Early probabilistic spatial deconvolution baseline. / 学早期概率反卷积基线。 |
| Domains and SVGs | [SpaGCN: integrating gene expression, spatial location and histology to identify spatial domains](https://doi.org/10.1038/s41592-021-01255-8) | SpaGCN | [jianhuupenn/SpaGCN](https://github.com/jianhuupenn/SpaGCN), [SpaGCN tutorial](https://github.com/jianhuupenn/SpaGCN/blob/master/tutorial/tutorial.md) | Combine gene expression, coordinates, and histology in a graph. / 学表达、坐标和图像联合建图。 |
| Spatial domains | [Deciphering spatial domains from spatially resolved transcriptomics with adaptive graph attention auto-encoder](https://doi.org/10.1038/s41467-022-29439-6) | STAGATE | [zhanglabtools/STAGATE](https://github.com/zhanglabtools/STAGATE) | Graph attention for spatial clustering and denoising. / 学图注意力空间聚类。 |
| Clustering, integration, deconvolution | [Spatially informed clustering, integration, and deconvolution of spatial transcriptomics with GraphST](https://doi.org/10.1038/s41467-023-36796-3) | GraphST | [JinmiaoChenLab/GraphST](https://github.com/JinmiaoChenLab/GraphST) | Self-supervised graph contrastive learning for multiple ST tasks. / 学图对比学习。 |
| Communication | [Screening cell-cell communication in spatial transcriptomics via collective optimal transport](https://doi.org/10.1038/s41592-022-01728-4) | COMMOT | [zcang/COMMOT](https://github.com/zcang/COMMOT) | Spatially constrained ligand-receptor communication and signaling direction. / 学带距离约束的空间通讯。 |
| Communication | [Modeling intercellular communication in tissues using spatial graphs of cells](https://doi.org/10.1038/s41587-022-01467-z) | NCEM | [theislab/ncem](https://github.com/theislab/ncem) | Spatial graph modeling of cellular communication. / 学空间图上的细胞通讯建模。 |
| Alignment | [Alignment and integration of spatial transcriptomics data](https://doi.org/10.1038/s41592-022-01459-6) | PASTE | [raphael-group/paste](https://github.com/raphael-group/paste), [paste3](https://github.com/raphael-group/paste3) | Optimal-transport alignment of adjacent spatial slices. / 学最优传输切片配准。 |
| Alignment | [Alignment of spatial genomics data using deep Gaussian processes](https://doi.org/10.1038/s41592-023-01972-2) | GPSA / STalign-related alignment concepts | [andrewcharlesjones/spatial-alignment](https://github.com/andrewcharlesjones/spatial-alignment) | Probabilistic alignment to a common coordinate system. / 学公共坐标系概率配准。 |
| Alignment | [STalign: alignment of spatial transcriptomics data using diffeomorphic metric mapping](https://github.com/JEFworks-Lab/STalign) | STalign | [JEFworks-Lab/STalign](https://github.com/JEFworks-Lab/STalign) | Diffeomorphic alignment for ST sections and atlases. / 学可微形变配准。 |
| Segmentation | [Cellpose: a generalist algorithm for cellular segmentation](https://doi.org/10.1038/s41592-020-01018-x) | Cellpose | [MouseLand/cellpose](https://github.com/MouseLand/cellpose) | Practical cell/nucleus segmentation baseline. / 学细胞和细胞核分割基线。 |
| Segmentation | [Whole-cell segmentation of tissue images with human-level performance using large-scale data annotation and deep learning](https://doi.org/10.1038/s41587-021-01094-0) | DeepCell / Mesmer | [vanvalenlab/deepcell-tf](https://github.com/vanvalenlab/deepcell-tf), [DeepCell docs](https://deepcell.readthedocs.io/) | Segmentation for tissue images and multiplex imaging. / 学组织图像分割。 |
| Segmentation | [CellSAM: a foundation model for cell segmentation](https://doi.org/10.1038/s41592-025-02879-w) | CellSAM | [vanvalenlab/cellSAM](https://github.com/vanvalenlab/cellSAM) | Modern foundation-model style segmentation. / 学 foundation model 分割。 |
| Visium HD reconstruction | [Bin2Cell: reconstructing cells from Visium HD spatial transcriptomics data](https://github.com/Teichlab/bin2cell) | Bin2Cell | [Teichlab/bin2cell](https://github.com/Teichlab/bin2cell) | Convert high-resolution Visium HD bins into cell-level objects. / 学 Visium HD bin 到细胞重建。 |
| Super-resolution / histology | [Deciphering tumor ecosystems at super-resolution from spatial transcriptomics with TESLA](https://doi.org/10.1016/j.cels.2023.03.008) | TESLA | [jianhuupenn/TESLA](https://github.com/jianhuupenn/TESLA) | Histology-guided super-resolution and tumor ecosystem analysis. / 学病理图像辅助超分辨率。 |
| Benchmark | [Benchmarking spatial and single-cell transcriptomics integration methods](https://doi.org/10.1038/s41592-022-01480-9) | Tangram, gimVI, SpaGE, cell2location, SpatialDWLS, RCTD | [paper](https://doi.org/10.1038/s41592-022-01480-9) | Compare mapping and deconvolution methods before choosing one. / 选映射和反卷积方法前先读。 |
| Benchmark | [Benchmarking clustering, alignment, and integration methods for spatial transcriptomics](https://doi.org/10.1186/s13059-024-03361-0) | SpaGCN, STAGATE, GraphST, PASTE and others | [maiziezhoulab/BenchmarkST](https://github.com/maiziezhoulab/BenchmarkST), [BenchmarkST docs](https://benchmarkst-reproducibility.readthedocs.io/) | Method-selection guide for spatial domains and integration. / 空间域和整合选型指南。 |
| Benchmark / application | [Xenium benchmarking: independent analysis workflows across public Xenium datasets](https://doi.org/10.1038/s41592-025-02617-2) | Scanpy, Squidpy, segmentation/QC/domain workflows | [Moldia/Xenium_benchmarking](https://github.com/Moldia/Xenium_benchmarking) | Learn real image-based ST QC and downstream analysis patterns. / 学真实 Xenium 质控和下游分析。 |

<a id="learning-order"></a>

## Suggested Learning Order / 建议学习顺序

1. Learn `AnnData` and `Scanpy` basics.
2. Run a `Squidpy` spatial graph and neighborhood tutorial.
3. Learn spatial gene detection with `SpatialDE` or Squidpy autocorrelation.
4. Learn mapping/deconvolution with `Tangram`, then `cell2location`.
5. Learn spatial domains with `SpaGCN`, `STAGATE`, or `GraphST`.
6. Learn communication with `COMMOT` after cell labels or domains are credible.
7. Learn alignment with `PASTE` or `STalign` when working with serial sections.
8. Learn segmentation with `Cellpose`, `DeepCell`, or `Bin2Cell` for image-based / Visium HD data.

1. 先学 `AnnData` 和 `Scanpy` 基础。
2. 跑一个 `Squidpy` 空间图和邻域教程。
3. 用 `SpatialDE` 或 Squidpy 自相关学空间基因检测。
4. 先学 `Tangram`，再学 `cell2location` 做映射和反卷积。
5. 用 `SpaGCN`、`STAGATE` 或 `GraphST` 学空间域。
6. 有可信细胞标签或空间域后，再学 `COMMOT` 通讯。
7. 做连续切片时再学 `PASTE` 或 `STalign`。
8. 成像型或 Visium HD 数据再学 `Cellpose`、`DeepCell` 或 `Bin2Cell`。

<a id="selection-rules"></a>

## Selection Rules / 收录规则

- The paper/resource must connect to at least one Python method in this repository.
- Public code can be a package source repository, paper reproduction repository, notebook, protocol, or executable tutorial.
- Benchmark papers are included when they help decide which method to learn or use.
- This list is curated for learning value, not citation count.

- 文章或资源必须对应本仓库至少一个 Python 方法。
- 公开代码可以是包源码、论文复现仓库、notebook、protocol 或可运行教程。
- benchmark 如果能帮助方法选型，也收录。
- 本清单按学习价值整理，不按引用量排序。
