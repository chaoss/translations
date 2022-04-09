# 许可证覆盖

问题：代码仓有多少已声明许可证？

## 描述
代码仓有多少扫描工具可以识别的已声明许可证，许可证可能不仅是 OSI 批准的。 这包括软件和文档源文件，以总覆盖率的百分比表示。

## 目标
通过许可证覆盖率，可以深入了解软件包中具有已声明许可证的文件的百分比，从而得出两个用例：
1. 软件包供内部组织使用，已声明许可证覆盖可以突出使用该软件包时的利益点或关注点。
2. 此外，一个软件包提供到外部、下游项目，已声明许可证覆盖可以使下游集成、部署和使用所需的许可证信息透明化。

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

### 筛选条件
时间：代码仓依赖项随时间变化后，可能导致代码仓中声明的许可证也发生变化。 除了基本了解之外，跟踪许可证存在的主要动机之一是注意意外的新许可证引入。

### 可视化效果

#### Augur 输出的 Web 演示：

![Augur JSON Output](images/license-coverage_augur-json-output.png)

#### Augur 输出的 JSON 演示：

![Augur Web Output](images/license-coverage_augur-web-output.png)

### 提供指标的工具

 1. [Augur](https://github.com/chaoss/augur)

可以提取和筛选数据以获得所需信息。 可在任意 [Augur 风险页面](http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk)找到许可证覆盖数据。

## 参考资料
* https://spdx.org/
* https://www.fossology.org
