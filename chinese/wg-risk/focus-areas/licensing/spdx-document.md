# SPDX 文档

问题：软件包是否具有关联的 SPDX 文档作为依赖项、许可证和安全相关问题的标准表达式？

## 描述
软件包具有关联的 SPDX 文档作为依赖项、许可证和安全相关问题的标准表达式。 有关 SPDX 规范的更多信息，请访问：https://spdx.org/

## 目标
对于获取开源软件用作 IT 或开源计划办公室组合的一部分的管理者，SPDX 文档提供的核心管理信息越发重要。  这是因为软件包存在于复杂的软件供应链中，必须以标准化的方式明确表达该软件包的相关依赖项、许可证和安全相关问题。 SPDX 文档为软件包的内部使用和下游分发提供了单一信息来源。 SPDX 文档可帮助组织将开源工作常规化，以便更好地与其开源风险管理例程相结合。

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

### 筛选条件

[augur-SPDX](https://github.com/chaoss/augur-spdx) 用于扫描 GitHub 代码仓 [Zephyr](https://github.com/zephyrproject-rtos/zephyr)。 以下是从扫描中以 JSON 格式识别的许可证：
```
{
  "0": "Apache-2.0",
  "1": "BSD-2-Clause",
  "2": "BSD-3-Clause",
  "3": "GPL-2.0",
  "4": "GPL-2.0+",
  "5": "GPL-3.0+",
  "6": "ISC",
  "7": "MIT"
  "8": "BSD-4-Clause-UC",
  "9": "CC0-1.0"
}
```
本文档由 Augur 生成。

## 提供指标的工具

* [DoSOCSv2](https://github.com/DoSOCSv2/DoSOCSv2)，嵌入为 [Augur](https://github.com/chaoss/augur) 服务。 使用 DoSOCSv2 插件配置的 Augur，可提供逐个文件的 SPDX 文档。  数据库模式的相关部分如下所示。
* [Augur-SPDX](https://github.com/chaoss/augur-spdx) 嵌入为 [Augur](https://github.com/chaoss/augur) 服务。 使用 augur-spdx 插件（该插件衍生自 DOSOCS）配置的 Augur，可提供逐个文件的 SPDX 文档。  数据库模式的相关部分如下所示。 此实现是 DoSOCSv2 的分支。

* 包
* Package_Files
* 文件（有可能也包含在其他包中，但可能性不大）。 许可证信息被添加为 SBOM 的一部分，但许可证鉴别的复杂性详述于 [License_Count](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Count.md)、[License_Coverage](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Coverage.md) 和 [License_Declared](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Declared.md) 指标。 

  ![SBOM](images/spdx-document_sbom.png)


## 参考资料
* https://spdx.org
* https://www.ntia.doc.gov/SoftwareTransparency  


