---
title: "Taichi 三月社区月报"
date: "2023-04-01" 
description:
  📌 四月高光时刻\
---

# Taichi 2023 年 4 月社区月报

## ⚙️ 技术动态

- AOT Playground 已发布，无需配置环境，即可在 Playground 编写 Taichi 程序。赶紧来尝试吧：https://aot-play.taichi-lang.cn/

## 🗓️ 社区精选

- **基于 Taichi 实现 VOF 两相流求解器**

作者：houkensjtu，项目地址：https://github.com/houkensjtu/taichi-2d-vof

taichi-2d-vof 基于 Taichi 实现了一个模拟两相流体的 VOF 法求解器。 VOF 方法在两相流计算中是非常流行的一种算法，常被用于跟踪两种不混溶的流体（例如空气和水）之间的界面。 本项目中 VOF 对流函数采用了基于 Murray Rudman 的修改版本的通量校正传输 (FCT) 算法。 代码的主循环部分主要可以分为以下步骤：速度对流、施加外力、施加不可压缩性条件、更新速度场、对流体积分数场，并可视化结果。 本项目通过非常精简的代码展示了 Taichi 语言在 GPU 上进行高效流体模拟的强大功能。

![](https://user-images.githubusercontent.com/124654014/235360756-e260391f-78f6-4f5b-9ee6-aede23a94f8b.gif)

VOF 求解器结果展示

- **【Ti example 投稿】基于 ti.cuda 的差分进化算法**

作者：Nanase-Nishino，项目地址：https://forum.taichi-lang.cn/t/topic/4136

差分进化算法是优化算法中的常见算法，应用领域广泛。差分进化算法的迭代依赖于一个大循环，该循环甚至可以达到 1,000,000，但是由于 Python/MatLab 对于循环的优化较差，c++ 等语言编码难度较高，因此通过 Taichi 加速原生 Python 代码很有意义，以便兼顾编码难度和运算速度。本项目实现面向数据的基于 Taichi 的差分进化算法，并实现了 2D/3D 可视化。


![31f11ae6-385c-43dc-ba18-350c843d1568](https://user-images.githubusercontent.com/124654014/235360867-06a81064-3022-45b6-b5ae-0847be48140a.gif)

2D res

![ab3a91b1-f35b-4c70-8fbf-4df1854e7171](https://user-images.githubusercontent.com/124654014/235360868-cbd2aeef-b848-4612-8c7e-508a7e2bf5e3.gif)

3D res

- **TaichiVisTools: 用于太极调试的可视化小工具**

作者：beidou，项目地址：https://forum.taichi-lang.cn/t/topic/4244

在写仿真代码的时候，常常会希望有可视化的调试工具。比如用鼠标框选粒子，可视化稀疏网格，矩阵检查器等…这对我们调试代码很有帮助。作者正在开发一套完全基于 GGUI 之上的小工具。
希望实现的功能包括：

- 粒子拾取器： 用鼠标框选得到粒子的 id 并且高亮。
- 稀疏网格可视化：用线框小方块表示稀疏网格的是否被占用。
- 矩阵检查器：检查矩阵的大致分布情况和异常值。

![](https://user-images.githubusercontent.com/124654014/235361022-20920c1d-db23-4d5d-b6d3-4904662bffca.png)

粒子拾取器

## 💡 社区活动

- Taichi 项目入选开源之夏，学生招募即将开始，欢迎点击 [报名](https://summer-ospp.ac.cn/org/orgdetail/1f1103c9-5204-4cbc-8723-03d43acbaaf1?lang=zh) 参加活动~ 

- 社区技术博客征文活动开启，欢迎加入 [内容共创计划](https://mp.weixin.qq.com/s/IzJwRobRwJW4dqP4ND3fPg)，传播技术知识。

- 技术分享：Taichi NeRF：无需写 CUDA 代码，用 Taichi 实现 Instant NGP。本次分享的主讲人林尤添是哈尔滨工业大学电子信息工程学院在读博士生，也是 Taichi NeRF 方向的实习生。本期分享中尤添介绍了 taichi-nerfs 的基本结构，讲解主要代码，带大家了解如何使用 Taichi 实现 NeRF 的加速，此外还介绍了如何结合 Taichi 和 PyTorch 实现算子的自动微分。

- 技术分享：当前超火的 NeRF 技术，经历了哪些发展演变？本次分享的主讲人为香港科技大学的徐新沅同学。[本期分享与大家聊一聊 NeRF 领域经典项目，不同数据结构的特点介绍与对比，以及稀疏显式辐射场与 Taichi 结合方向的思索。徐新沅同学目前在研究 NeRF 与点云、SLAM 的融合，希望未来能通过 NeRF 相关技术构建高质量的 3D 模型](https://www.bilibili.com/video/BV11g4y1M75L/)。

- 技术分享：[GPU 研发工程师教你 Taichi AOT 的正确使用方式](https://www.bilibili.com/video/BV1mh4y1H7K4/) ，本次分享的主讲人为 Taichi GPU 研发工程师梁任冬，本次分享面向使用过 Taichi 并对移动端部署感兴趣的小伙伴，通过此次 Meetup 参会者学习了 Taichi AOT 基本工作原理和代码编写。并在线体验了 Taichi AOT playground。

## 📃 精选博客

**精选 Paper**

香港科技大学电子及计算机工程系博士徐浩在论文 D2SLAM: Decentralized and Distributed Collaborative Visual-inertial SLAM System for Aerial Swarm 中使用 TaichiSLAM 开发稠密重建部分以及稠密建图。

论文代码已经开源至：https://github.com/HKUST-Aerial-Robotics/D2SLAM ，文档数据集逐渐更新中。

论文预印本地址：https://arxiv.org/abs/2211.01538

## 🙋‍♂️贡献者力量

感谢社区同学们在 Taichi 项目中的贡献 ❤️

**taichi:**

@lgyStoic, [lang] Add popcnt to llvm intrinsic support #7772

@listerily, [lang] [ir] Added atomic multiplication support for all backends #7854

@chunleili, [sparse] Add sparse_grid #7832

@52wdWPF, [Doc] Update field.md #7819

@zxlbig, [perf] Fix Taichi CPU backend compile parameter to pair performance with Numba. #7731

@TachikakaMin, [bug] Returning nan for ti.sym_eig on identity matrix #7443

@liblaf, [bug] Fix camera controls #7681

@Lee-abcde, [example] Add 2D euler fluid simulation example #7568

**taichi-nerfs:**

@Asxcvbn, updated train.py to address torch update #32

## 🙌 Taichi 小课堂

Q：Taichi 支持哪些返回值类型？

A：Taichi 函数的返回值可以是标量、ti.Matrix、ti.Vector、ti.Struct。与 kernel 不同，Taichi 函数可以有多个返回值，但至多只能有一条返回语句。

扫描以下二维码关注我们～

![](https://user-images.githubusercontent.com/124654014/232975155-6b306bbb-e54f-4904-aab0-b8e09fd9b650.jpeg)

