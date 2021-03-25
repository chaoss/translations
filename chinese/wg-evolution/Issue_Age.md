# 问题时长

问题：未解决问题有多长时间处于未解决状态？

## 描述
这一指标表明在考虑的时间段内，问题有多长时间处于未解决状态。 如果一个问题已解决，但在这段时间内又重新变为未解决，则将其视为自最初发布为未解决的日期以来一直为未解决状态。

## 目标
当问题时长不断增加时，找出项目中时间最长的未解决问题，深入了解为什么这些问题长时间都未能解决。 此外，要了解维护者解决问题的水平和速度。

## 实现
对于所有未解决问题，获取问题发布为未解决的日期，计算距当前日期的天数。

**聚合器：**
* 平均数。 所有未解决问题的平均时长。
* 中位数。 所有未解决问题的中位时长。

**参数：**
* 时间段。 考虑未解决问题的开始日期和结束日期。 默认：永久（即项目问题活动的整个可观察时段）。

### 筛选条件
* 模块或工作组
* 问题标记/标签

### 可视化效果

1. 未解决问题的汇总数据<br /> ![未解决问题的汇总数据](images/open_issue_data.png)

2. 每天未解决问题的计数<br /> ![每天未解决问题的计数](images/open_issue_count_timeseries.png)

### 提供指标的工具

* [GrimoireLab](https://chaoss.github.io/grimoirelab/)
* [Augur](http://augur.osshealth.io/api_docs/#api-Evolution-Open_Issue_Age_Repo_)

### 数据收集策略

关于收集已解决问题的数据的具体说明，请参阅[“新问题”的对应部分](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_New.md#data-collection-strategies)。

## 参考资料
