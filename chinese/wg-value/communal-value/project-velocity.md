# 项目速度

问题：什么是组织的发展速度？

## 描述

项目速度是指问题数、拉取请求数、提交量和贡献者数，用作“创新”的指标。

## 目标

让开源计划办公室 (OSPO) 管理员能够比较项目组合的项目速度。

OSPO 管理员可以使用项目速度指标来：

- 报告开源项目与内部项目的项目速度对比
- 比较项目组合中的项目速度
- 找出哪些项目的发展超出了内部贡献者的范围（在筛选内部贡献者与外部贡献者时）
- 找出值得参与的有前途领域
- 突出未来几年可能成为成功平台的领域

[参见示例](https://www.cncf.io/blog/2017/06/05/30-highest-velocity-open-source-projects)

## 实现

基本指标包括：

- [关闭的问题](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_Closed.md)
- [评论数](https://github.com/chaoss/wg-evolution/blob/master/metrics/Reviews.md)
- [代码变更数](https://github.com/chaoss/wg-evolution/blob/master/metrics/Code_Changes.md)
- [提交者数](https://github.com/chaoss/wg-risk/blob/master/metrics/Committers.md)

### 筛选条件

* 内部与外部贡献者
* 项目来源（例如，内部仓库、开源仓库和竞争对手的开源仓库）
* 时间

### 可视化效果

* X 轴：代码更改的对数刻度
* Y 轴：问题数和评论数之和的对数刻度。
* 点大小：提交者
* 点为项目

![cncf](images/project-velocity_visualization.png)

[来自 CNCF](https://www.cncf.io/blog/2017/06/05/30-highest-velocity-open-source-projects/)

### 提供指标的工具

* CNCF - https://github.com/cncf/velocity

## 参考资料

- [Can Open Source Innovation work in the Enterprise?](https://www.threefivetwo.com/blog/can-open-source-innovation-work-in-the-enterprise)
- [Open Innovation for a High Performance Culture](https://www.nearform.com/blog/want-a-high-performing-culture-make-way-for-open-innovation)
- [Open Source for the Digital Enterprise](https://www.cio.com/article/3213146/open-source-is-powering-the-digital-enterprise.html)
- [Highest Velocity Open Source Projects](https://www.cncf.io/blog/2017/06/05/30-highest-velocity-open-source-projects)
