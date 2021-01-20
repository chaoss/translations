# 活跃问题

问题：在一定时期内有多少活跃问题？


## 描述

问题如[新问题](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_New.md)中定义。 显示某些活动的问题是指在一定时期内具有一些注释，或状态发生一些变化（包括关闭问题）的问题。

例如，在 GitHub 问题中，注释、新标记或关闭问题的操作，都被认为是活动的标志。


## 目标

* 项目中的活跃问题量。 活跃问题是项目活动的代理。 统计一个项目对应的仓库集合中与代码相关的活跃问题，可以了解该项目中处理问题的整体活动。 当然，该指标不是唯一用于跟踪编码活动量的指标。


## 实现

**聚合器：**
* 计数。 一段时间内活跃问题的总数。
* 比率。 一段时间内活跃问题占问题总数的比率。

**参数：**
* 时间段。 考虑问题的开始日期和结束日期。 默认：永久。

* 源代码标准。 算法。 默认：所有问题均与源代码相关。  
  如果我们专注于源代码，则需要一个标准来确定一个问题是否与源代码相关。

### 筛选条件

* 按参与者（提交者、评论者、解决者）。 需要合并同一作者对应的身份。
* 按参与者群组（雇主、性别…涉及每个参与者）。 需要参与者分组，并且可能需要参与者合并。


### 可视化效果

* 一段时间内每个周期的计数
* 一段时间内每个周期的比率

这些可以通过应用先前定义的筛选条件进行分组。 可以用条形图表示，X 轴为时间。 每个条形代表一定时间（如一个月）内更改代码的提案。


### 提供指标的工具

* [GrimoireLab](https://chaoss.github.io/grimoirelab) 为 GitHub 问题、GitLab 问题、Jira、Bugzilla 和 Redmine 提供了计算此页面相似指标的数据。 就指标而言，**GrimoireLab 数据只有每个项的最后更新日期，这将计算指标的时间范围限制到当前日期为止**。
  - 根据源 API 的不同，对问题更新的定义可能有所不同。 GrimoireLab 使用 `metadata__updated_on` 存储最新问题更新，请查看 [Perceval 文档](https://perceval.readthedocs.io/en/latest/search.html?q=metadata_updated_on&check_keywords=yes&area=default)查找每种情况下正在使用的特定 API 字段，并了解其限制（如果有）。
  - 当前，没有显示此操作的仪表板。 不过，构建可视化效果仍很容易，可以显示上一次活动在给定日期和当前日期之间某个时刻的使用次数（我们将针对 GitHub 问题进行操作）。
  - 按照说明向任意 GrimoreLab Kibiter 仪表板添加一个示例可视化效果：
    * 新建一个 `Metric` 可视化效果。
    * 选择 `github_issues` 索引。
    * 筛选条件：`pull_request` 为 `false`。
    * 指标：`Count` 聚合，`# Issues Active` 自定义标签。
    * 桶：`Date Range` 聚合，`metadata__updated_on` 字段，`now-1M` 自从（或任何适合您需求的间隔），`now` 直到，将“自定义标签”留空以查看图例中的具体日期。
    * 查看右上角的时间选择器，确保将其设置为包括数据的整个故事，这样我们就不会根据其创建日期排除任何项目。
  - 屏幕截图示例：![GrimoireLab screenshot of metric issues_active](https://github.com/chaoss/wg-evolution/blob/master/metrics/images/issues_active_GrimoireLab.png)。

### 数据收集策略

**具体描述：GitHub**

对于 GitHub，活跃问题定义为“获得注释、标记变更、分配人员变更或被关闭的问题”。

**具体描述：GitLab**

对于 GitLab，活跃问题定义为“获得注释、标记变更、分配人员变更或被关闭的问题”。

**具体描述：Jira**

对于 Jira，活跃问题定义为“获得注释、状态变更、分配人员变更或被关闭的问题”。

**具体描述：Bugzilla**

对于 Bugzilla，活跃问题定义为“获得注释、状态变更、分配人员变更或被关闭的错误报告”。

## 参考资料
