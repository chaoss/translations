# 文档的无障碍性

问题: 文档如何适应不同的用户?

## 描述

由于文档在开源项目中所起的作用，文档的无障碍性至关重要。文档用户具有不同的能力，要求以不同的格式提供文档，以便为这些不同的用户提供同等的授权。其目标是为了促进项目最广泛的贡献者的理解能力。

## 目标

这些目标有助于衡量您的文档是否为广大受众所接受，同时又不会对其预期受众的部分群体造成不成比例的人为债务。

* **无障碍屏幕阅读器** — 文档可根据屏幕阅读软件的标准访问.
* **学习灵活性** — 有不同认知方式、感觉差异和神经多样性的人都可以使用文件。 [(1)](https://static.sched.com/hosted_files/kcsna2019/05/Breaking%20Down%20Barriers%20to%20Kubernetes%20Contribution%20for%20Neurodivergent%20Individuals%20%282%29.pdf).
* **盲人或视障人士** — 文档对主要阅读文字的人来说是无障碍的。图表和图像是非无障碍类型的文件的例子。


## 实现

**注意:**  注意文档的目标读者。由于项目和可能做出贡献的人的范围很广，文件应满足所有受众的不同要求。


### 数据收集策略

*使用**工具**来评估屏幕阅读器的友好性 [(5)](https://www.w3.org/WAI/ER/tools/) [(6)](https://a11yproject.com/#Quick-tests) 来确定文档是否对屏幕阅读器友好?
* **采访**  新人可以找出文档是如何帮助，(a)理解贡献过程，和/或，(b)帮助完成项目中的任务\
采访问题举例:
  * 您通过使用文档理解贡献过程的体验是什么？
  * 当您有关于在项目中工作的问题时，您查阅文档的体验是什么？
  * 您对文档出现的技术术语感到满意吗?
* **调查** 项目成员
  * 矩阵项: 当您需要查找有关此项目的过程、政策或指南的相关信息时，以下哪项描述了您的经验？ [(2)](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=158869274)
    * 矩阵行可以是:
      * 邮件列表交流
      * 聊天交流
      * 执行代码审查
      * 代码被采纳的流程
      * 行为守则
      * 新入职人员
      * 许可证
      * 商标
      * 添加新的提交者或者贡献者
      * 项目发布
      * 投票流程
      * 安装过程
      * 功能开发
      * API 集成
      * 测试套件
      * 架构总览
      * 用户指南

    * 矩阵列可以使:
      * 总是很容易找到
      * 很容易找到
      * 很难找到
      * 很难找到
  * 多项选择: 当您开始参与项目时，是否遇到过与文档无障碍性相关的任何挑战(例如，语言障碍、文档的可发现性、文档结构) ？? [(2)](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=158869274)
    * 回答选项:
      * 没有挑战
      * 一些挑战
      * 几个挑战
      * 许多挑战
    * 开放式的后续问题，如果答案不是“没有挑战”: 描述一个例子，当你经历挑战，该挑战如何影响你，以及如何，如果有，你克服了挑战。
  * 开放式问题: 对于改进项目的政策、流程或提供给新贡献者的指南，你有什么建议？？ [(2)](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=158869274)
* 寻找关于可读性和可扫描性的组织结构，例如：
  * 标题
  * 文本和代码块
  * 标号或者段落
  * 锚点
* 通过考虑以下因素来评估搜索能力:
  * 用户能多容易地找到这个文档?
  * 用户在文档中找到他们需要的东西有多容易?
  * 使用键盘操作文档容易吗?
* 提供一个快速的微观调查，只有一个问题给文档的读者(例如，当离开文档页面时，底部页或弹出):
  * 是/否的问题: 这个文档页面对你来是否无障碍性?
  * 李克特量表[1-x ] : 这个文档对你来说有多容易理解?
  * 简短回答: 您对文档的无障碍性有什么看法？
* 与文件的预期用户进行**预览**文档。观察他们如何交互和使用文档，以及他们在哪里卡住了。这可以是一个视频会议会话，文档的用户在其中共享他们的屏幕。
* 要求文档的用户写一个**摩擦日志**，描述他们在文档中遇到的问题。这为文档编辑提供了具体的使用案例，以了解如何为特定用户改进文档。
* 考虑是否为不同的受众提供**不同版本的文档**？例如，一个简要的版本和一个非常详细的版本。


## 参考资料

1. [为在Kubernetes做贡献的神经分化症患者打破障碍](https://static.sched.com/hosted_files/kcsna2019/05/Breaking%20Down%20Barriers%20to%20Kubernetes%20Contribution%20for%20Neurodivergent%20Individuals%20%282%29.pdf)
2. [Apache 基金会社区调查问卷2020](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=158869274)
3. [GNOME 无障碍报障团队](https://wiki.gnome.org/Accessibility)
4. [W3C Web 内容无障碍访问指南](https://www.w3.org/WAI/standards-guidelines/wcag/)
5. [W3C Web 无障碍性评估工具](https://www.w3.org/WAI/ER/tools/)
6. [一些用于检测web无障碍性的快速测试方法](https://a11yproject.com/#Quick-tests)
7. [Knowability - 一个专门从事无障碍性建设的团体](https://knowbility.org/services/document-accessibility/)
8. [关于无障碍性度量指标的思考](https://www.boia.org/blog/3-times-accessibility-and-disability-stats-matter-and-3-times-they-dont)
9. [Paypal无障碍指南清单](http://paypal.github.io/a11y/)
10. [通用设计](http://shop.oreilly.com/product/9780596518745.do)
