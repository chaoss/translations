# 首次关闭议题的贡献者

问题：在给定项目中，有多少贡献者是第一次关闭议题？

## 描述
该指标表示在给定项目中首次关闭议题的贡献者数量。 当贡献者第一次关闭议题时，这表明该项目中的个人“粘性”，特别是贡献者不为代码提交者的情况。

## 目标
将“关闭议题”确定为贡献者旅程中的一个里程碑，了解贡献者如何在[贡献者漏斗](https://mikemcquaid.com/2018/08/14/the-open-source-contributor-funnel-why-people-dont-contribute-to-your-open-source-project/)中移动。

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

**聚合器：**
* 计数。 在给定时间段内，首次关闭此项目议题的贡献者总数。
* 百分比。 在给定时间段内，*首次*关闭此项目议题的贡献者占该时间段内关闭过议题的贡献者*总数*的比例。

**参数：**
* 时间段。 计算首次问题关闭者的开始日期和结束日期。 默认：永久（即整个可观察项目生命周期）

### 筛选条件
* 排除重新打开的议题（如果在不到 1 小时的时间内重新打开，则可以选择筛选条件）

### 可视化效果
* 表中列出首次关闭议题的贡献者的姓名和对应时间。
* 时间轴在 x 轴显示时间，y 轴为固定连续时间段（如每月）的汇总指标值。 这种可视化效果可以显示所考虑项目的指标随时间的变化情况。

### 数据收集策略
基于[已解决议题](https://chaoss.community/metric-issues-closed/)和[贡献者](https://chaoss.community/metric-contributors/)定义，通过首次解决议题的日期完善贡献者信息。

## 参考资料

* [贡献者漏斗 Mike McQuaid](https://mikemcquaid.com/2018/08/14/the-open-source-contributor-funnel-why-people-dont-contribute-to-your-open-source-project/)
