# 软件物料清单

问题：软件包是否对依赖软件、许可证和安全相关问题有标准表达？

## 描述
软件包具有对依赖软件、许可和安全相关问题的标准表达。这是对“物料清单”的一种枚举，因此不表示为度量指标。将此 CHAOSS 指标视为“组件清单”更为准确，这在许多面向风险的开源软件获取的话题中尤为重要。

## 目标
对于获取开源软件作为工作的IT 或开源项目办公室的管理人员来说，“软件物料清单”（“SBOM”）是越来越重要的“核心管理信息”。出现这种情况是因为，由于软件包存在于复杂的软件供应链中，因此必须以标准化的方式清楚地表达该软件包的相关依赖软件、许可证和安全相关问题。软件物料清单提供了一个单一的源文档，该文档为软件包的内部使用和下游分发提供了信息。软件物料清单有助于组织如何常规化开展开源工作，以更好地与他们自己的开源风险管理程序集成。

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

### 可视化
DoSOCSv2 用于扫描 GitHub代码仓。以下是扫描中的一些核心许可证，可用作格式示例：
```
LicenseID: LicenseRef-See-URL
LicenseName: See-URL
ExtractedText: com/license
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-Dual-license
LicenseName: Dual-license
ExtractedText:  MIT or new BSD license.
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-BSD
LicenseName: BSD
ExtractedText: Available via the MIT or new BSD license.
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-Python
LicenseName: Python
ExtractedText: license. Your class definition should look\nsomething like this:\n\n.. code:: python\n\n #SPDX-License
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-Non-profit
LicenseName: Non-profit
ExtractedText: nonprofit
LicenseCrossReference:
LicenseComment: found by nomos
```

### 提供指标的工具
[DoSOCSv2](https://github.com/DoSOCSv2/DoSOCSv2) 被集成到[Augur](https://github.com/chaoss/augur) 中，作为一项服务提供。

使用 DoSOCSv2 插件配置的 Augur 可以逐一对文件生成 SBOM。数据库模型的相关部分如下所示。从 SBOM 的角度来看，最重要的一点是它比其他描述的软件许可证的指标更简单。对于SBOM，我们只需要简单地看一些枚举值：
* 软件包
* 包文件
* 文件（可能有，不太可能包含在其他包中）。
许可证信息作为 SBOM 的一部分包含在内，但许可证识别的复杂性体现在 [许可证计数](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Count.md)、[ 许可证覆盖度](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Coverage.md) 和 [声明的许可证](https://github.com/chaoss/wg-risk/blob/master /metrics/License_Declared.md) 等指标中。![SBOM](images/software-bill-of-materials_license.png)

## 资源
https://spdx.org  
https://www.ntia.doc.gov/SoftwareTransparency  
