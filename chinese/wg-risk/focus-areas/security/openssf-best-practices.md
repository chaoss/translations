# Open Source Security Foundation (OpenSSF) 最佳实践徽章

问题：项目目前OpenSSF最佳实践徽章的状态如何？

## 描述

如 [OpenSSF 最佳实践徽章页面](https://bestpractices.coreinfrastructure.org/en)所述：Linux 基金会 OpenSSF 最佳实践徽章是开源项目展示其遵循最佳实践的一种方式。项目可以使用此 Web 应用程序解释其如何遵循每种最佳实践，从而免费自愿地进行自我认证。如果项目满足所有必须的标准，即可获得合格徽章。

## 目标

如 [OpenSSF 最佳实践徽章页面](https://bestpractices.coreinfrastructure.org/en)所述：OpenSSF 徽章表示项目对 Linux 基金会核心基础架构倡议定义的“开源项目最佳实践”的遵循程度，该倡议重点关注开源软件的网络安全。该计划的目标是鼓励项目生产更好、更安全的软件，并允许其他人确定项目是否遵循最佳实践。

徽章的消费者可以快速评估哪些开源项目遵循了最佳实践，从而更有可能生产出更高质量的安全软件。

## 实现

相关信息见 [OpenSSF 的 API 文档](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/api.md)。

### 可视化效果

![](images/cii-best-practices_visualization.png)

### 提供指标的工具

Augur 为 OpenSSF 最佳实践指标提供了示例实现。使用的 OpenSSF 示例见 http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk

### 数据收集策略

相关信息见 [OpenSSF 的 API 文档](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/api.md)。

如 [OpenSSF 最佳实践徽章页面](https://bestpractices.coreinfrastructure.org/en)所述：如果项目满足所有必要标准，即可获得合格徽章。对于给定项目，每个标准的状态可以是“满足”、“未满足”、“不适用”或“未知”。每项标准都有四个类别：“必须”、“应该”、“建议”或“未来”。要获得徽章，所有“必须”和“绝不”标准必须满足，所有“应该”标准必须满足或者记录有不执行该标准的理由，所有“建议”标准必须被评价为满足或未满足。如果项目满足附加标准，可获得银级和金级的高级徽章。

## 参考资料

- OpenSSF 徽章网站：https://bestpractices.coreinfrastructure.org/en
- Augur：https://github.com/chaoss/augur



