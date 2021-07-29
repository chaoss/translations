# OSI 批准的许可证

问题：在项目的许可证中，OSI 批准的开源许可证所占比例是多少？

## 描述

这个指标提供了项目内所用开源许可证的透明度。 需要透明的原因是一些许可证的传播实际上对开源并不友好。 开源项目可能不希望包含未经 OSI 批准的许可证。

如 OSI 所述：“开源许可证是符合开源定义的许可证 - 简而言之，其允许软件被自由使用、修改和共享。 要获得开源倡议（也称 OSI）批准，许可证必须经过开源倡议的许可证审查流程。”

## 目标

确定项目是否含有不符合开源定义的许可证。 这种透明度有助于项目有意识地决定是否包含未经 OSI 批准的许可证。

## 实现

可在 SPDX 提供的 [Licenses.json](https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json) 中找到 OSI 批准的许可证。

### 可视化效果

![OSI](images/osi-approved-licenses_visualization.png)

### 提供指标的工具

Augur 在项目的“风险”页面下提供该指标。

示例：http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk

### 数据收集策略

从代码仓提取许可证列表，与许可证覆盖率指标相同。 将许可证列表与 [Licenses.json](https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json) 比较，记录 OSI 批准的许可证数量。 计算 OSI 许可证列表上文件的百分比。

## 资源

* [OSI 许可证页面](https://opensource.org/licenses)
* [SPDX 许可证列表](https://spdx.org/licenses/)


