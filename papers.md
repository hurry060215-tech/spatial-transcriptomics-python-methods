# Papers for Python Spatial Transcriptomics Workflows
# Python 空间转录组流程参考论文

This file collects papers that are useful when choosing Python methods. It is not a complete bibliography.

本文件收集选择 Python 方法时最常用的一组论文，并不是完整书目。

## Reviews and Best-Practice Papers / 综述与最佳实践

| Topic | Paper | Why read it / 阅读价值 |
|---|---|---|
| Field overview | [Exploring tissue architecture using spatial transcriptomics](https://doi.org/10.1038/s41586-021-03634-9) | High-level map of spatial technologies and analysis tasks. / 了解空间技术和分析任务全景。 |
| Computational challenges | [Computational challenges and opportunities in spatially resolved transcriptomic data analysis](https://doi.org/10.1038/s41467-021-25557-9) | Useful for pitfalls and method categories. / 适合理解方法分类和常见陷阱。 |
| Statistical methods review | [Statistical and machine learning methods for spatially resolved transcriptomics data analysis](https://doi.org/10.1186/s13059-022-02653-7) | Good bridge from statistics to workflows. / 从统计建模到实际流程的衔接较好。 |
| Spatial omics review | [The expanding vistas of spatial transcriptomics](https://doi.org/10.1038/s41587-022-01448-2) | Useful for matching technology scale to analysis method. / 适合按平台分辨率选择方法。 |
| Deconvolution benchmark | [Benchmarking spatial and single-cell transcriptomics integration methods](https://doi.org/10.1038/s41592-022-01480-9) | Compares mapping and deconvolution methods including Tangram, gimVI, and cell2location. / 比较映射和反卷积方法。 |
| Deconvolution practical benchmark | [A comprehensive benchmarking with practical guidelines for cellular deconvolution of spatial transcriptomics](https://doi.org/10.1038/s41467-023-37168-7) | Practical guidance for cell-type deconvolution. / 反卷积方法选择指南。 |
| Spatial clustering benchmark | [Benchmarking spatial clustering methods for spatially resolved transcriptomics](https://doi.org/10.1038/s41592-024-02215-8) | Helps choose domain and niche tools. / 辅助选择空间聚类和空间域工具。 |

## Foundational Technology Papers / 技术基础论文

| Technology | Paper |
|---|---|
| Spatial Transcriptomics / Visium predecessor | [Visualization and analysis of gene expression in tissue sections by spatial transcriptomics](https://doi.org/10.1126/science.aaf2403) |
| Slide-seq | [Slide-seq: A scalable technology for measuring genome-wide expression at high spatial resolution](https://doi.org/10.1126/science.aaw1219) |
| Slide-seqV2 | [Highly sensitive spatial transcriptomics at near-cellular resolution with Slide-seqV2](https://doi.org/10.1038/s41587-020-0739-1) |
| Stereo-seq | [Spatiotemporal transcriptomic atlas of mouse organogenesis using DNA nanoball-patterned arrays](https://doi.org/10.1016/j.cell.2022.04.003) |
| MERFISH | [Spatially resolved, highly multiplexed RNA profiling in single cells](https://doi.org/10.1126/science.aaa6090) |
| STARmap | [Three-dimensional intact-tissue sequencing of single-cell transcriptional states](https://doi.org/10.1126/science.aat5691) |

## Python Method Papers / Python 方法论文

| Method | Paper |
|---|---|
| Scanpy | [Scanpy: a scalable toolkit for analyzing single-cell gene expression data](https://doi.org/10.1186/s13059-017-1382-0) |
| Squidpy | [Squidpy: a scalable framework for spatial omics analysis](https://doi.org/10.1038/s41592-021-01358-2) |
| scvi-tools | [A Python library for probabilistic analysis of single-cell omics data](https://doi.org/10.1038/s41587-021-01206-w) |
| SpatialDE | [SpatialDE: identification of spatially variable genes](https://doi.org/10.1038/nmeth.4636) |
| SpaGCN | [SpaGCN: integrating gene expression, spatial location and histology to identify spatial domains](https://doi.org/10.1038/s41592-021-01255-8) |
| Tangram | [Multimodal intersection analysis of single-cell transcriptomes and spatial transcriptomics](https://doi.org/10.1038/s41592-021-01264-7) |
| cell2location | [Cell2location maps fine-grained cell types in spatial transcriptomics](https://doi.org/10.1038/s41587-021-01139-4) |
| DestVI | [A data-driven approach to predict and infer cell-type-specific gene expression in spatial transcriptomics](https://doi.org/10.1038/s41587-022-01272-8) |
| Stereoscope | [Probabilistic cell-type assignment of spatially resolved transcriptomics data](https://doi.org/10.1038/s41467-020-15968-5) |
| PASTE | [Alignment and integration of spatial transcriptomics data](https://doi.org/10.1038/s41592-022-01459-6) |
| STalign | [Alignment of spatial genomics data using deep Gaussian processes](https://doi.org/10.1038/s41592-023-01972-2) |
| COMMOT | [Screening cell-cell communication in spatial transcriptomics via collective optimal transport](https://doi.org/10.1038/s41592-022-01728-4) |
| NCEM | [Modeling intercellular communication in tissues using spatial graphs of cells](https://doi.org/10.1038/s41587-022-01467-z) |
| DeepLinc | [De novo reconstruction of cell interaction landscapes from single-cell spatial transcriptome data with DeepLinc](https://doi.org/10.1186/s13059-022-02692-0) |
| Cellpose | [Cellpose: a generalist algorithm for cellular segmentation](https://doi.org/10.1038/s41592-020-01018-x) |
| Mesmer / DeepCell | [Whole-cell segmentation of tissue images with human-level performance using large-scale data annotation and deep learning](https://doi.org/10.1038/s41587-021-01094-0) |
| CellSAM | [CellSAM: a foundation model for cell segmentation](https://doi.org/10.1038/s41592-025-02879-w) |
| Bin2Cell | [Bin2Cell: reconstructing cells from Visium HD spatial transcriptomics data](https://github.com/Teichlab/bin2cell) |
| Spateo | [Spateo documentation and method resources](https://spateo-release.readthedocs.io/) |

## Reading Order / 建议阅读顺序

1. Start with Scanpy and Squidpy if you are building a Python workflow.
2. Read the benchmark papers before choosing deconvolution or clustering methods.
3. For image-based data, read segmentation papers before downstream spatial biology papers.
4. For multi-slice work, read PASTE or STalign before building a cohort-level workflow.

1. 如果要搭 Python 流程，先读 Scanpy 和 Squidpy。
2. 选择反卷积或空间聚类方法前，先读 benchmark。
3. 成像型空转要先理解分割论文，再看下游空间生物学方法。
4. 多切片项目建议先读 PASTE 或 STalign，再设计队列级流程。

