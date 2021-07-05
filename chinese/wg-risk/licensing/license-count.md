# 许可证计数

问题：有多少种不同的许可证？

## 描述
The total count of identified licenses in a software package where the same license can be counted more than once if it is found in multiple source files. This can include both software and document related licenses. This metric also provides a binary indicator of whether or not the repository contains files without license declarations. This metric is a "complexity of licensing case" flag for open source managers. For example, the ideal case would look like the table below:

软件包中已识别许可证的总数，如果在多个源文件中找到相同的许可证，则可以多次计数。这可以包括与软件和文档相关的许可证。该指标还提供了一个二进制标记，指示代码仓库是否包含没有许可证声明的文件。该指标对开源管理人员来说体现了“许可证的复杂性”。例如，理想情况如下表所示：

| 许可证数量 | 是否存在无许可证的文件 |
| ------------- |-------------|
| 1      | FALSE |

A more common case would require references to [Licenses Declared](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Declared.md) and [License Coverage](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Coverage.md) metrics, in the situation reflected in this table:

更常见的情况是需要引用 [声明的许可证](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Declared.md) 和 [许可证覆盖度](https://github.com /chaoss/wg-risk/blob/master/metrics/License_Coverage.md) 指标，在此表中反映的情况：

| 许可证数量 | 是否存在无许可证的文件 |
| ------------- |-------------|
| 11      | TRUE |

## Objectives
对于负责监督开源软件获取和管理的 IT 经理或向市场交付开源软件的开源计划办公室或社区经理而言，最简单的情况是在所有文件中声明单一许可类型。如果软件中包含一个或多个许可证，该指标将快速而明显地说明；数字越大，决策者的考虑的情况就越复杂。

该指标的第二个方面是代码仓库（软件包）是否包含没有许可证声明的文件的二进制标记。

## 实现

### 提供指标的工具

 1. [Augur](https://github.com/chaoss/augur)

许可证数量可以在任何 [Augur 风险页面](http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk) 的“声明的许可证”部分下找到。表中的行数为许可证数。

## 参考资料
1. https://spdx.org/
2. https://www.fossology.org
