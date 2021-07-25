# 议题解决时长

问题：解决议题花费了多长时间？

## 描述
这一指标表明议题在解决之前平均有多长时间处于未解决状态。 议题如[已解决议题](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_Closed.md)中定义。

对于重新打开后再次关闭的议题，只有最后的解决日期与该指标有关。

## 目标
此指标可用于评估完成和解决讨论所需的工作量和时间。 此指标还可以提供项目响应程度的相关信息。

## 实现

对于每个已关闭的议题：
* 议题解决时长 = 已关闭的议题时间戳 - 新建议题的时间戳

**聚合器：**
* 平均数。 仓库中议题得到解决的平均时间（默认以天为单位）。

**参数：**
* 时间段。 开始日期和完成日期。 默认：永久。  
  考虑议题的时间周期。


### 筛选条件

* 按时间。 由提供的开始日期到提供的结束日期，表明平均议题解决时长。
  - 按议题建立时间。 由提供的开始日期到提供的结束日期，在此时间段内新创建的议题是花多长时间解决的（该议题的解决时间可能晚于规定的时间段）。
  - 按议题关闭时间。 由提供的开始日期到提供的结束日期，在此时间段内解决的议题是花多长时间解决的（该议题创建时间可能早于规定的时间段）。

* 按参与者（提交者、评论者、解决者）。 需要参与者合并（合并同一作者的对应 ID）。

* 按参与者群组（雇主、性别…涉及每个参与者）。 需要参与者分组，并且可能需要参与者合并。



### 可视化效果

* 一段时间的平均数（如一月平均数、二月平均数、三月平均数等）
* 给定时间段的平均数（例如，2019 年的全年平均数，或一月至三月的平均数）


### 提供指标的工具

* [Augur](http://augur.osshealth.io/) 将此指标作为[已解决议题解决时长](http://augur.osshealth.io/api_docs/#api-Evolution-Closed_Issue_Resolution_Duration_Repo_)提供。 该指标均以 `repo` 和 `repo_group` 指标形式提供，更多信息见 [Augur 文档](https://oss-augur.readthedocs.io/en/master/getting-started/create-a-metric/overview.html#metric-forms)。


### 数据收集策略

关于收集已解决议题的数据的具体说明，请参阅[“已解决议题”的对应部分](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_Closed.md#data-collection-strategies)。


## 参考资料

