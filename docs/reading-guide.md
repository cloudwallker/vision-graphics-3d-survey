# 阅读路线：视觉、图形与三维场景

本路线帮助初学者逐步解释一条研究线的任务、表示、公式和证据。先完成共同基础，再选一个分支深入；按掌握程度推进，练习以阅读、画图和手算为主。

## 先做共同基础

1. **阶段一：图像输出与监督。** 读本目录综述前两节，分别画检测框、分割掩码、深度图和三维点云。用10个像素手算IoU，列出训练需要什么标签。成果：一页术语表，能区分“看懂图像”与“重建真实三维”。
2. **阶段二：NeRF。** 从[原论文](https://arxiv.org/abs/2003.08934)读任务、表示、体渲染。手算两点透明度合成；逐项标出位置、方向、颜色、密度与采样距离。成果：一张光线示意图和一个数值例子，不要求先理解全部训练细节。
3. **阶段三：3DGS。** 读[作者项目及原论文](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)，比较隐式函数与显式高斯。画三个不同方向的椭圆；说明增密、剪枝为何影响速度与质量。成果：一张NeRF/3DGS对照表，分别写建模成本、渲染成本与内存。

## 按兴趣选一个入口

| 分支 | 推荐顺序 | 每篇必须答出的两个问题 |
|---|---|---|
| 真实成像与复原 | [LuSh-NeRF](../papers/P133.md) → [RGB-D玻璃](../papers/P129.md) → [GhostingNet](../papers/P130.md) | 作者观察到的成像线索是什么？线索在哪些条件下会失效？ |
| 三维生成与材质 | [MAGE](../papers/P122.md) → [Phidias](../papers/P126.md) → [DreamPhysics](../papers/P127.md) | 哪些部分来自观测，哪些来自先验猜测？评价证明了几何、材质还是外观？ |
| 三维语言理解 | CLIP → SAM → [OpenScan](../papers/P109.md) → [HCMA](../papers/P128.md) | 错误来自语言匹配还是候选区域？训练类别和属性查询怎样分开？ |
| 高效三维建模 | 3DGS → [TurboGS](../papers/P104.md) | 省掉了哪些计算？是否把代价转移到额外预处理、显存或视觉质量？ |
| 注意力与指代 | [PoseSOR](../papers/P135.md) → [PCNet](../papers/P134.md) → [LG-SOR](../papers/P124.md) | 人物姿态或文字关系怎样改变目标判断？是否使用额外标签或模型生成信息？ |

## 核心论文的精读页码

- [LuSh-NeRF原PDF](https://proceedings.neurips.cc/paper_files/paper/2024/file/c69465280855cfe25d566e359da140c1-Paper-Conference.pdf)：第4页体渲染，第5–7页分解与训练，第7–9页数据、设置与对比。先问为何不能直接拼接低光增强和去模糊。
- [MAGE原PDF](https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_MAGE__Single_Image_to_Material-Aware_3D_via_the_Multi-View_CVPR_2025_paper.pdf)：第3–5页表示与损失，第6–7页数据与消融。画出五种G-buffer，把一处阴影与低反照率区别开。
- [OpenScan原PDF](http://www.cs.cityu.edu.hk/~rynson/papers/aaai26a.pdf)：第3–4页标注和查询，第5–6页七个基线与结果。分别构造类别、材质、用途三个查询；解释为何它们难度不同。
- [TurboGS原PDF](https://arxiv.org/pdf/2606.15924)：第3–6页方法，第6–9页主实验与局限，第13页硬件。检查至少一行训练时间和一行SSIM/LPIPS，不只抄最快数字。

页码为PDF页序号，可能与正文印刷页码不同；如果原文更新，应重新定位。

## 将阅读整理为可检验的问题

选一篇主论文写约800字解释：输入输出、关键观察、两个模块、一个公式例子和实验边界。再补一个经典基线与一篇相关论文，完成“原问题—已有方法—仍未解释的现象”的一页对照。最后选取两篇任务相近的论文，比较数据、预算和评价条件。

可以讨论的**待验证假设**包括稀疏优化是否需要按纹理自适应密集监督、属性查询错误是否主要由掩码质量造成、单图材质预测是否应输出不确定性。先设计可否证的对照及评价，再决定是否值得实现。阅读理解、拟议实验和已经验证的结果应分别记录，不能把阅读笔记称为复现。

## 延伸研究与版本核验（2026-10-02）

以下论文可扩展前面的阅读安排。先完成一篇方法卡，再按问题选择下一篇。

- 董旻京：[VSSD: Vision Mamba with Non-Causal State Space Duality](<../papers/P078.md>)。先解释视觉状态空间架构的问题和输入输出，再对照卡片核验具体版本及方法。
- 董旻京：[Region-Level Policy Optimization for Fine-grained MLLM Perception](<../papers/P051.md>)。先解释细粒度多模态感知的问题和输入输出，再对照卡片核验具体版本及方法。
- 董旻京：[DEFUSE: Generalizable Backdoor Defense for Self-Supervised Encoders with Generative Priors](<../papers/P052.md>)。先解释自监督编码器后门防御的问题和输入输出，再对照卡片核验具体版本及方法。
- 李韬：[Multi-level traffic-responsive tilt camera surveillance through predictive correlated online learning](<../papers/P153.md>)。先解释在线学习：交通摄像控制的问题和输入输出，再对照卡片核验具体版本及方法。
