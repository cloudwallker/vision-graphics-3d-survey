# 代表与前沿研究：视觉、图形与三维场景

核验截止2026-10-02。下列8项按基础与近期问题组织；不是完整书目，也不宣称截至该日全部最新最优结果。日期区别首版预印本与会议年份，录用信息以一手页面或选读论文核对。摘要采用改写。

| 工作 | 日期与可核状态 | 入门价值及阅读问题 | 一手来源 |
|---|---|---|---|
| NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis | 2020-03-19首版；ECCV 2020正式论文 | 建立连续空间表示与可微体渲染的概念。先问颜色如何沿光线合成，再理解位置编码与分层采样 | [arXiv](https://arxiv.org/abs/2003.08934)、[作者项目](https://www.matthewtancik.com/nerf) |
| CLIP / Learning Transferable Visual Models From Natural Language Supervision | ICML 2021正式论文，PMLR 139 | 图像和文字如何在共享空间匹配？零样本能力与训练数据覆盖是什么关系？它提供表征而非天然三维理解 | [PMLR正式页](https://proceedings.mlr.press/v139/radford21a.html) |
| 3D Gaussian Splatting for Real-Time Radiance Field Rendering | SIGGRAPH 2023 / ACM TOG正式论文 | 理解显式高斯、协方差、透明度合成与密度控制；比较训练、渲染和内存成本 | [Inria作者项目及论文](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/) |
| Segment Anything | ICCV 2023正式论文；预印本2023年4月 | 了解可提示的类别无关掩码生成。掩码好不等于对象属性理解好，可作为三维语义流水线基础 | [CVF原PDF](https://openaccess.thecvf.com/content/ICCV2023/papers/Kirillov_Segment_Anything_ICCV_2023_paper.pdf)、[arXiv](https://arxiv.org/abs/2304.02643) |
| LuSh-NeRF | NeurIPS 2024正式论文；所读版本见[论文卡片](../papers/P133.md) | 低光、噪声与手持模糊怎样耦合？比较先增强照片与在三维训练中联合建模的区别 | [NeurIPS原PDF](https://proceedings.neurips.cc/paper_files/paper/2024/file/c69465280855cfe25d566e359da140c1-Paper-Conference.pdf)、[arXiv](https://arxiv.org/abs/2411.06757) |
| MAGE | CVPR 2025正式论文；所读版本见[论文卡片](../papers/P122.md) | 从单图恢复可重光照材质，思考反照率与光照混淆；检查合成训练材质和真实物体的差别 | [CVF原PDF](https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_MAGE__Single_Image_to_Material-Aware_3D_via_the_Multi-View_CVPR_2025_paper.pdf) |
| OpenScan | 首版2024-08-20、v4 2025-11-24；arXiv注明AAAI 2026录用，所读会议版本见[论文卡片](../papers/P109.md) | 从类别查询走向功能与材质属性，读八类标注的来源和评价协议，不把“开放类别”当作全面场景理解 | [arXiv版本记录](https://arxiv.org/abs/2408.11030)、[作者项目](https://youjunzhao.github.io/OpenScan/) |
| TurboGS | 首版2026-06-14；arXiv注明ICML 2026录用，所读版本见[论文卡片](../papers/P104.md) | 把算力分配到难像素。讨论稀疏监督与低纹理波纹，以及加速是否在相同GPU与质量预算下比较 | [arXiv](https://arxiv.org/abs/2606.15924) |

## 按研究问题扩展选读

核心阅读线可从真实采集退化、可重光照表示、语言场景理解和高效优化展开。玻璃与镜面研究补充特殊成像条件；注意力与指代研究补充对象和关系线索；物理运动与全景编辑则关注生成内容的可控性。不同分支需分别检查监督来源及实验条件。

图像地理定位与视觉语言推理连接视觉理解和外部知识；复杂图像检索主要评价召回与排序效果。使用语言模型并不足以决定论文所属任务。摘要层面的概括也不能代替方法精读或实验复现。

## 前沿问题地图

| 问题 | 已见研究切入 | 尚需核查的证据 |
|---|---|---|
| 真实照片不符合干净成像假设 | LuSh-NeRF联合退化建模 | 不同相机噪声、动态对象、位姿不准是否仍有效 |
| 生成三维只能在原光照下好看 | MAGE分解材质与几何 | 未见真实材质及背面是否可辨识，重光照误差如何量化 |
| 三维模型能认类别但不懂用途 | OpenScan属性基准 | 实例属性、常识先验与掩码错误的独立影响 |
| 更快训练牺牲局部结构 | TurboGS稀疏优化 | 低纹理、动态场景、等预算质量及硬件一致性 |

这些问题可用来形成假设，不是已经得到证实的研究结论。若2026年10月后继续整理，需重新核对新版本、勘误、数据和正式出版状态。

## 延伸研究与版本核验（2026-10-02）

本表列出直接论文来源、版本状态与阅读依据。

| 论文 | 已核验来源 | 发表与版本状态 | 阅读依据 |
|---|---|---|---|
| [VSSD: Vision Mamba with Non-Causal State Space Duality](<../papers/P078.md>) | [直接来源](<https://arxiv.org/abs/2407.18559v2>) | CVF 官方 proceedings：ICCV 2025，10819–10829，2025-10；另保存 arXiv v2（2024-08-04）。 | fulltext |
| [Region-Level Policy Optimization for Fine-grained MLLM Perception](<../papers/P051.md>) | [直接来源](<https://arxiv.org/abs/2609.19745v1>) | 已核 arXiv 预印本；官方摘要页未见会议/期刊发表声明，本次未确认正式发表。 | fulltext |
| [DEFUSE: Generalizable Backdoor Defense for Self-Supervised Encoders with Generative Priors](<../papers/P052.md>) | [直接来源](<https://arxiv.org/abs/2608.25851v1>) | arXiv 作者备注：Accepted at ACM Multimedia 2026；录用声明已核，未独立核会议正式出版日期。 | fulltext |
| [Multi-level traffic-responsive tilt camera surveillance through predictive correlated online learning](<../papers/P153.md>) | [直接来源](<https://arxiv.org/abs/2408.02208>) | Transportation Research Part C正式2024-10卷167文章104804；arxiv首发2024-08-05。 | fulltext |
