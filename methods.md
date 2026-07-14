# Python Method Catalog
# Python 方法目录

Use this file as a decision map. Each section gives common Python choices, when to use them, and a paper or documentation link when available.

本文件按分析决策组织。每一节列出常用 Python 方法、适用场景，以及可用论文或文档链接。

## Table of Contents / 目录

- [Data containers and general toolkits / 数据对象与通用工具](#data-containers)
- [QC, normalization, and bias correction / 质控、标准化与偏差校正](#qc-normalization)
- [Cell segmentation and reconstruction / 细胞分割与细胞重建](#segmentation)
- [Spatially variable genes and spatial patterns / 空间变异基因与空间模式](#spatial-signal)
- [Cell mapping, annotation, and deconvolution / 细胞映射、注释与反卷积](#cell-mapping)
- [Domains, niches, and spatial clustering / 空间域、生态位与空间聚类](#domains-niches)
- [Cell-cell communication and spatial networks / 细胞通讯与空间网络](#communication-networks)
- [Multi-sample alignment and integration / 多样本配准与整合](#alignment-integration)
- [Histology, image features, and super-resolution / 病理图像、图像特征与超分辨率](#histology-super-resolution)
- [Subcellular, CNV, isoforms, and advanced analyses / 亚细胞、CNV、异构体与高级分析](#advanced-analyses)
- [Notes / 注意](#notes)

<a id="data-containers"></a>

## 1. Data Containers and General Toolkits / 数据对象与通用工具

| Method | Use | 中文说明 |
|---|---|---|
| [`AnnData`](https://anndata.readthedocs.io/) | Standard matrix container for Scanpy/scverse workflows. | Scanpy/scverse 生态的基础矩阵对象。 |
| [`Scanpy`](https://scanpy.readthedocs.io/) | Single-cell style preprocessing, clustering, and visualization. | 单细胞式质控、标准化、聚类和可视化。 |
| [`Squidpy`](https://squidpy.readthedocs.io/) | Spatial graph, neighborhood, image, and ligand-receptor analysis. | 空间图、邻域、图像和配体-受体分析。 |
| [`SpatialData`](https://spatialdata.scverse.org/) | Coordinate systems, images, labels, points, and shapes. | 管理坐标系统、图像、标签、点和轮廓。 |
| [`Sopa`](https://github.com/gustaveroussy/sopa) | Scalable processing of image-based spatial omics. | 成像型空间组学的大规模处理流程。 |
| [`stLearn`](https://github.com/BiomedicalMachineLearning/stLearn) | Spatial transcriptomics analysis with morphology support. | 整合空间位置和组织形态的分析工具。 |
| [`Spateo`](https://spateo-release.readthedocs.io/) | Spatiotemporal modeling and 3D spatial transcriptomics analysis. | 时空建模、3D 空转和定量分析框架。 |
| [`LazySlide`](https://github.com/rendeirolab/LazySlide) | Whole-slide image analysis framework. | 全切片图像分析框架。 |

<a id="qc-normalization"></a>

## 2. QC, Normalization, and Bias Correction / 质控、标准化与偏差校正

| Method | Use | 中文说明 |
|---|---|---|
| [`Scanpy` QC](https://scanpy.readthedocs.io/) | Count depth, detected genes, mitochondrial genes, and filtering. | 基础表达质控和过滤。 |
| [`Squidpy` image QC](https://squidpy.readthedocs.io/) | Image features and spatial graph checks. | 图像特征和空间图检查。 |
| [`MerQuaCo`](https://github.com/AllenInstitute/merquaco) | QC for image-based spatial transcriptomics. | 成像型空转质控。 |
| [`GrandQC`](https://github.com/cpath-ukk/grandqc) | Digital pathology QC. | 病理图像质控。 |
| [`Sopa`](https://github.com/gustaveroussy/sopa) | Scalable preprocessing, patching, and platform-specific import. | 大图像切块、平台读入和预处理。 |
| [`scvi-tools`](https://scvi-tools.org/) | Probabilistic modeling, integration, and downstream latent spaces. | 概率建模、整合和低维表示。 |
| [`ResolVI`](https://github.com/scverse/scvi-tools) | Bias correction in the scvi-tools ecosystem. | scvi-tools 生态中的偏差校正方法。 |
| [`MisTIC`](https://github.com/yunguan-wang/MisTic-Wanglab) | Correct mis-assigned transcripts from segmentation errors. | 校正因分割错误导致的转录本错配。 |
| [`ovrl.py`](https://github.com/HiDiHlabs/ovrl.py) | Investigate vertical signal properties in imaging data. | 检查成像型空转的纵向信号问题。 |

<a id="segmentation"></a>

## 3. Cell Segmentation and Cell Reconstruction / 细胞分割与细胞重建

| Method | Use | 中文说明 |
|---|---|---|
| [`Cellpose`](https://github.com/MouseLand/cellpose) | Generalist cell and nucleus segmentation. | 通用细胞/细胞核分割。 |
| [`DeepCell` / `Mesmer`](https://github.com/vanvalenlab/deepcell-tf) | Deep-learning cell segmentation. | 深度学习细胞分割。 |
| [`CellSAM`](https://github.com/vanvalenlab/cellSAM) | Foundation-model style cell segmentation. | 泛化能力较强的细胞分割模型。 |
| [`ComSeg`](https://github.com/fish-quant/ComSeg) | Transcript point-cloud segmentation. | 基于转录本点云的分割。 |
| [`FICTURE`](https://github.com/seqscope/ficture) | Feature-based segmentation and region analysis. | 基于表达 feature 的分割和区域分析。 |
| [`Bin2Cell`](https://github.com/Teichlab/bin2cell) | Cell reconstruction for Visium HD bins. | Visium HD bin 到细胞级重建。 |
| [`BIDCell`](https://github.com/SydneyBioX/BIDCell) | Biologically informed deep learning segmentation. | 生物学约束的深度学习分割。 |
| [`Segger`](https://github.com/dpeerlab/segger) | Fast cell segmentation for imaging-based ST. | 成像型空转快速细胞分割。 |
| [`Bering`](https://github.com/jian-shu-lab/Bering) | Graph deep learning for segmentation and molecular annotation. | 图深度学习分割与分子注释。 |
| [`Points2Regions`](https://github.com/wahlby-lab/Points2Regions) | Segmentation-free transcript region discovery. | 无需分割的转录本区域识别。 |
| [`SSAM`](https://github.com/HiDiHlabs/ssam) | Segmentation-free analysis with mRNA density. | 基于 mRNA 密度的无分割分析。 |

<a id="spatial-signal"></a>

## 4. Spatially Variable Genes and Spatial Patterns / 空间变异基因与空间模式

| Method | Use | 中文说明 |
|---|---|---|
| [`SpatialDE`](https://github.com/Teichlab/SpatialDE) | Gaussian-process spatial differential expression. | 高斯过程空间差异表达。 |
| [`Squidpy` spatial autocorrelation](https://squidpy.readthedocs.io/) | Moran's I, neighborhood enrichment, and spatial statistics. | Moran's I、邻域富集和空间统计。 |
| [`PROST`](https://github.com/Tang-Lab-super/PROST) | SVG detection and spatial pattern exploration. | 空间变异基因检测和模式识别。 |
| [`SOMDE`](https://github.com/XuegongLab/somde) | Self-organizing map plus Gaussian process SVG detection. | 自组织映射结合高斯过程的 SVG 检测。 |
| [`Hotspot`](https://github.com/YosefLab/Hotspot) | Informative local gene modules. | 局部基因模块检测。 |
| [`SLOPER`](https://github.com/chitra-lab/SLOPER) | Score-based learning of spatial expression rates. | 基于 score 的空间表达率建模。 |
| [`FlashS`](https://pypi.org/project/flashs/) | Frequency-domain SVG testing. | 频域高斯核 SVG 检测。 |
| [`SpatialCorr`](https://github.com/mbernste/SpatialCorr) | Spatially varying gene-set correlation. | 空间变相关基因集分析。 |

<a id="cell-mapping"></a>

## 5. Cell Mapping, Annotation, and Deconvolution / 细胞映射、注释与反卷积

| Method | Use | 中文说明 |
|---|---|---|
| [`cell2location`](https://github.com/BayraktarLab/cell2location) | Probabilistic cell-type deconvolution with scRNA-seq references. | 基于单细胞参考的概率反卷积。 |
| [`Tangram`](https://github.com/broadinstitute/Tangram) | Map single-cell profiles or genes onto spatial locations. | 把单细胞或基因表达映射到空间位置。 |
| [`DestVI`](https://docs.scvi-tools.org/en/stable/user_guide/models/destvi.html) | Continuous cell-state deconvolution in scvi-tools. | 推断连续细胞状态的反卷积。 |
| [`Stereoscope`](https://github.com/almaan/stereoscope) | Probabilistic deconvolution. | 概率反卷积方法。 |
| [`CytoSPACE`](https://github.com/digitalcytometry/cytospace) | High-resolution alignment of single-cell and spatial transcriptomes. | 单细胞和空间数据高分辨率配准。 |
| [`SpaGE`](https://github.com/tabdelaal/SpaGE) | Spatial gene expression prediction and mapping. | 空间基因表达预测和映射。 |
| [`rctd-py`](https://github.com/p-gueguen/rctd-py) | Python implementation of RCTD-style deconvolution. | RCTD 思路的 Python 实现。 |
| [`TACCO`](https://github.com/simonwm/tacco) | Transfer annotations between single-cell and spatial datasets. | 单细胞和空间数据间标签转移。 |
| [`STELLAR`](https://github.com/snap-stanford/stellar) | Annotation of spatially resolved single-cell data. | 空间单细胞注释。 |
| [`moscot`](https://github.com/theislab/moscot) | Optimal-transport cell mapping and alignment. | 最优传输细胞映射与配准。 |

<a id="domains-niches"></a>

## 6. Domains, Niches, and Spatial Clustering / 空间域、生态位与空间聚类

| Method | Use | 中文说明 |
|---|---|---|
| [`SpaGCN`](https://github.com/jianhuupenn/SpaGCN) | Spatial domain detection with gene expression, location, and histology. | 结合表达、位置和病理图像的空间域识别。 |
| [`stLearn` SME](https://github.com/BiomedicalMachineLearning/stLearn) | Morphology-aware spatial smoothing and clustering. | 结合组织形态的空间平滑和聚类。 |
| [`STAGATE`](https://github.com/zhanglabtools/STAGATE) | Graph attention network for spatial clustering. | 图注意力网络空间聚类。 |
| [`GraphST`](https://github.com/JinmiaoChenLab/GraphST) | Graph contrastive learning for clustering and integration. | 图对比学习用于空间聚类和整合。 |
| [`DeepST`](https://github.com/JiangBioLab/DeepST) | Graph contrastive framework for clustering, integration, and deconvolution. | 图对比学习框架，覆盖聚类、整合和反卷积。 |
| [`CellCharter`](https://github.com/CSOgroup/cellcharter) | Hierarchical niche detection. | 层级 niche 检测。 |
| [`NicheCompass`](https://github.com/Lotfollahi-lab/nichecompass) | End-to-end spatial multi-omics niche analysis. | 端到端空间多组学 niche 分析。 |
| [`GASTON`](https://github.com/raphael-group/GASTON) | Graph-based spatial domain and tissue-layer modeling. | 基于图的空间域和组织层建模。 |
| [`SpatialGLUE`](https://github.com/JinmiaoChenLab/SpatialGlue) | Multi-omics cell niche identification. | 多组学空间 niche 识别。 |
| [`STAMP`](https://github.com/JinmiaoChenLab/scTM) | Topic-modeling style spatial transcriptomics analysis. | topic modeling 风格的空间分析。 |
| [`Novae`](https://github.com/MICS-Lab/novae) | Foundation model for spatial domains and tissue organization. | 空间域和组织结构 foundation model。 |

<a id="communication-networks"></a>

## 7. Cell-Cell Communication and Spatial Networks / 细胞通讯与空间网络

| Method | Use | 中文说明 |
|---|---|---|
| [`COMMOT`](https://github.com/zcang/COMMOT) | Spatial communication through collective optimal transport. | 基于 collective optimal transport 的空间通讯推断。 |
| [`SpaOTsc`](https://github.com/zcang/SpaOTsc) | Spatial and signaling relationship inference with optimal transport. | 基于最优传输推断空间和信号关系。 |
| [`Squidpy ligand-receptor`](https://squidpy.readthedocs.io/) | Ligand-receptor enrichment in spatial neighborhoods. | 空间邻域中的配体-受体富集。 |
| [`CellPhoneDB`](https://github.com/ventolab/CellphoneDB) | Ligand-receptor interaction analysis. | 配体-受体互作分析。 |
| [`LIANA+`](https://github.com/saezlab/liana-py) | Consensus ligand-receptor analysis with Python support. | 支持 Python 的综合通讯推断框架。 |
| [`DeepLinc`](https://github.com/xryanglab/DeepLinc) | Cell interaction landscape reconstruction. | 细胞互作景观重建。 |
| [`FlowSig`](https://github.com/axelalmet/flowsig) | Intercellular flow inference. | 细胞间信息流推断。 |
| [`CellNEST`](https://github.com/schwartzlab-methods/CellNEST) | Cell relay networks with graph attention. | 基于图注意力的细胞 relay 网络。 |

<a id="alignment-integration"></a>

## 8. Multi-Sample Alignment and Integration / 多样本配准与整合

| Method | Use | 中文说明 |
|---|---|---|
| [`PASTE`](https://github.com/raphael-group/paste) | Pairwise and center alignment of spatial slices. | 切片两两配准和中心配准。 |
| [`PASTE2`](https://github.com/raphael-group/paste2) | Extension of PASTE for partial overlap and larger settings. | 支持部分重叠和更复杂场景的 PASTE 扩展。 |
| [`STalign`](https://github.com/JEFworks-Lab/STalign) | Diffeomorphic alignment for spatial genomics. | 空间组学可微形变配准。 |
| [`moscot`](https://github.com/theislab/moscot) | Optimal transport for temporal, spatial, and multimodal mapping. | 用最优传输做时间、空间和多模态映射。 |
| [`TOAST`](https://github.com/cecca46/TOAST) | Topography-aware optimal transport alignment. | 拓扑感知最优传输配准。 |
| [`STAligner`](https://github.com/zhanglabtools/STAligner) | Graph neural-network integration across slices. | 多切片图神经网络整合。 |
| [`SPACEL`](https://github.com/QuKunLab/SPACEL) | Alignment and 3D reconstruction. | 空间配准和 3D 重建。 |
| [`SLAT`](https://github.com/gao-lab/SLAT) | Spatial alignment with graph matching. | 基于图匹配的空间配准。 |

<a id="histology-super-resolution"></a>

## 9. Histology, Image Features, and Super-Resolution / 病理图像、图像特征与超分辨率

| Method | Use | 中文说明 |
|---|---|---|
| [`TESLA`](https://github.com/jianhuupenn/TESLA) | Super-resolution and histology-guided spatial analysis. | 基于组织图像的超分辨率和空间分析。 |
| [`ST-Net`](https://github.com/bryanhe/ST-Net) | Predict expression from histology. | 从病理图像预测表达。 |
| [`HEST`](https://github.com/mahmoodlab/HEST) | Dataset and tooling for ST plus histology. | 空转加病理图像数据和工具。 |
| [`DeepSpot`](https://github.com/ratschlab/DeepSpot) | Spatial expression prediction from H&E images using spatial context. | 利用空间上下文从 H&E 图像预测空间表达。 |
| [`DeepSpot2Cell`](https://github.com/ratschlab/DeepSpot2Cell) | Virtual single-cell spatial transcriptomics from H&E with spot-level supervision. | 用 spot 级监督从 H&E 预测虚拟单细胞空转。 |
| [`DeepSpot-M`](https://github.com/ratschlab/DeepSpotM) | Multimodal foundation model for transcriptome-wide virtual ST from histology. | 从组织学做全转录组虚拟空转的多模态基础模型。 |
| [`istar`](https://github.com/daviddaiweizhang/istar) | Super-resolution for Visium. | Visium 超分辨率。 |
| [`SpaHDmap`](https://github.com/sldyns/SpaHDmap) | High-definition embedding with histology encoders. | 表达和图像编码器结合的高分辨率空间嵌入。 |
| [`AESTETIK`](https://github.com/ratschlab/aestetik) | Multimodal representation learning for spatially resolved transcriptomics (image + expression). | 多模态空间转录组表示学习（图像+表达）。 |

<a id="advanced-analyses"></a>

## 10. Subcellular, CNV, Isoforms, and Advanced Analyses / 亚细胞、CNV、异构体与高级分析

| Method | Use | 中文说明 |
|---|---|---|
| [`Bento`](https://github.com/YeoLab/bento-tools) | Subcellular transcript localization analysis. | 亚细胞转录本定位分析。 |
| [`Sprawl`](https://github.com/salzman-lab/SPRAWL) | Subcellular transcript pattern analysis. | 亚细胞转录本空间模式分析。 |
| [`FISHFactor`](https://github.com/bioFAM/FISHFactor) | Subcellular transcript patterns. | 亚细胞转录本模式分解。 |
| [`CalicoST`](https://github.com/raphael-group/CalicoST) | Copy-number variation in spatial data. | 空间数据 CNV 分析。 |
| [`inSituCNV`](https://github.com/Moldia/InSituCNV) | CNV inference for image-based ST. | 成像型空转 CNV 推断。 |
| [`SPLISOSM`](https://github.com/JiayuSuPKU/SPLISOSM) | Spatial isoform modeling. | 空间异构体建模。 |
| [`SOCS`](https://github.com/algo-bio-lab/SOCS) | Time-series spatial trajectory inference. | 时间序列空间轨迹推断。 |
| [`STORIES`](https://github.com/cantinilab/stories) | Spatiotemporal reconstruction with optimal transport. | 用最优传输做时空轨迹重建。 |

<a id="notes"></a>

## Notes / 注意

- Before any spatial operation, verify that coordinate arrays exist and are numeric, commonly `adata.obsm["spatial"]`.
- For image-based data, explicitly record segmentation source, boundary expansion, transcript assignment rules, and coordinate system.
- For deconvolution, keep the single-cell reference preprocessing auditable; reference quality often matters more than the downstream model.
- For multi-slice work, run per-sample QC before alignment so that bad tissue regions do not drive registration.

- 做任何空间操作前，先确认坐标数组存在且为数值型，常见位置是 `adata.obsm["spatial"]`。
- 成像型数据要明确记录分割来源、边界扩张、转录本归属规则和坐标系统。
- 反卷积中，单细胞参考的预处理要可追溯；参考质量常常比模型选择更关键。
- 多切片分析要先做单样本质控，再配准，避免低质量区域主导配准。

