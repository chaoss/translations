# Issue时长

问题：未关闭的issue开了多长时间？

## 描述
这一指标是指在度量的时间段内，issue有多长时间处于未关闭状态。 如果一个issue已经关闭，但在这段时间内又重新打开，则将该issue按照初始发布的时间来考虑。

## 目标
当issue的时长不断增加时，找出项目中时间最长的未关闭issue，深入了解为什么这些issue长时间都未能关闭。 此外，要了解维护者解决issue的好坏程度和速度。

## 实现
对于所有未关闭的issue，计算issue发布的日期到当前的天数。

**聚合器：**
* 平均数。 所有未关闭的issue的平均时长。
* 中位数。 所有未关闭的issue的中位时长。

**参数：**
* 时间段。 考虑未关闭的issue的开始日期和结束日期。 默认：永久（即项目issue活跃的全部可观察时段）。

### 筛选条件
* 模块或工作组
* issue的Tags/labels

### 可视化效果

1. 未关闭的issue汇总数据<br /> ![未解决issue的汇总数据](images/open_issue_data.png)

2. 每天未关闭issue的数量<br /> ![每天未解决issue的计数](images/open_issue_count_timeseries.png)

### 提供指标的工具

* [GrimoireLab](https://chaoss.github.io/grimoirelab/)
* [Augur](http://augur.osshealth.io/api_docs/#api-Evolution-Open_Issue_Age_Repo_)

### 数据收集策略

关于收集已关闭issue数据的具体说明，请参阅[“新issue”的对应部分](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_New.md#data-collection-strategies)。

## 参考资料
