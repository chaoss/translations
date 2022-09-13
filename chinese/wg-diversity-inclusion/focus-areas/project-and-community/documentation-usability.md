# 文档可用性

问题：从内容和结构的角度来看，文档的可用性是什么？


## 描述

文档可用性确保不同用户都能理解开源项目文档的关键作用。 文档可用性包含结构、内容、术语和可读性等问题，目的是最大限度推动贡献者对项目的理解。


## 目标
* **技术术语** - 文档使用适当程度的技术术语，并提供必要的术语解释，确保特定项目的入门贡献者能够理解文档。
* **结构清晰度** - 文档易于阅读和理解。
* **可读性** - 文档语言应简洁明了，使用常用词和短句，以确保非母语者或可能不了解类似缩写惯例或推论模式的人能够理解。
* **语言包容性** - 文档应避免使用非包容性语言（例如“brogrammer”语言或排斥性/贬义语言）。
* **语言多元化** - 针对目标受众和不同语言提供通用语言的文档。
* **时间/注意力多元化** - 文档应该有包容性，能够让人们在不同时间读取或设置/运行命令。 还应考虑到需要照顾孩子或具有其他照护职责的人员，这些人员随时可能将注意力转移到屏幕之外。
因此保持文档更小、<u>更易消耗</u>是更加可取的。

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

### 数据收集策略

* 采访新人，确定文档如何帮助贡献者 (a) 理解贡献过程，和/或 (b) 完成任务。 样本采访问题：
  * 描述一下您使用文档了解贡献过程的经验。
  * 描述一下您在社区工作中遇到问题时使用文档的经验。
  * 描述您使用文件了解和帮助外联工作的经验。
  * 您对这里出现的大量技术术语感到满意吗？ （适用于李克特量表 [1-5] 的调查）
  * 有您不理解的术语或语言吗？
  * 您对改进项目的政策、流程或新贡献者可用的准则有什么建议？
  * 采访后，社区可追踪回复，记为 `Positive experience`、`Negative experience` 或 `Neutral experience`，并逐月报告这些情况，了解随时间推移的改进情况。
* 提出有关可读性和可扫描性的问题，如：文档是否使用组织结构，如：
  * 标题
  * 文本和代码块
  * 项目符号与段落
  * 锚点
* 与文档的预期用户进行预审。 观察他们如何使用文档以及在哪里遇到问题。 可以采用视频会议会话，让文档用户共享屏幕。
* 要求文档用户编写[摩擦日志](https://devrel.net/developer-experience/an-introduction-to-friction-logging)
            并描述其在文档上遇到的问题。 这为文档编辑提供了具体用例，以了解如何针对具体用户改进文档。
* 考虑为不同受众提供不同版本的文档。 例如，轻量版本和非常详细的版本。



## 资源

* [W3C Web 内容无障碍指南](https://www.w3.org/WAI/standards-guidelines/wcag/)
* [W3C Web 无障碍评估工具列表](https://www.w3.org/WAI/ER/tools/)
* [一些评估 Web 辅助功能的快速测试](https://a11yproject.com/#Quick-tests)
* [专门研究辅助功能的小组](https://knowbility.org/services/document-accessibility/)
* [关于辅助功能指标的思考](https://www.boia.org/blog/3-times-accessibility-and-disability-stats-matter-and-3-times-they-dont)
* [GNOME 与辅助功能 ](https://wiki.gnome.org/Accessibility)
* [Paypal 无障碍指南列表](http://paypal.github.io/a11y/)
* [核心基础架构倡议：最佳实践徽章](https://bestpractices.coreinfrastructure.org/en)
* [打破神经多样性个体的 Kubernetes 贡献障碍](https://static.sched.com/hosted_files/kcsna2019/05/Breaking%20Down%20Barriers%20to%20Kubernetes%20Contribution%20for%20Neurodivergent%20Individuals%20%282%29.pdf)
* [`文档基础`](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md#documentation_basics)
* [`文档接口`](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md#documentation_interface)
* [摩擦日志](https://devrel.net/developer-experience/an-introduction-to-friction-logging)
* [斯坦福：屏幕阅读器测试](https://soap.stanford.edu/tips/screen-reader-testing)
