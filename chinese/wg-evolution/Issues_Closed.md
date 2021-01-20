# 关闭的问题

问题：在一定时期内有多少关闭的问题？


## 描述

问题如[新问题](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_New.md)中定义。 关闭的问题是指在一定时期内变更为关闭状态的问题。

在某些情况下或某些项目中，还有其他状态或标记可以被视为“关闭”。 例如，在某些项目中，使用状态或标记“fixed”说明问题已关闭，即使它还需要一些操作才能正式关闭。

在大多数问题跟踪器中，问题被关闭后还可重新打开。 重新打开问题可以被视为打开一个新的问题，或者使先前的关闭无效（见下文参数）。

例如，在 GitHub 问题或 GitLab 问题中，关闭的问题是指在某一时期关闭的问题。


## 目标

项目中处理的问题量。 关闭的问题是项目活动的代理。 统计一个项目对应的仓库集合中与代码相关的关闭的问题，可以了解该项目中完成问题处理的整体活动。 当然，该指标不是唯一用于跟踪编码活动量的指标。


## 实现

**聚合器：**
* 计数。 一段时间内活跃问题的总数。
* 比率。 一段时间内活跃问题占问题总数的比率。

**参数：**
* 时间段。 考虑问题的开始日期和结束日期。 默认：永久。

* 源代码标准。 算法。 默认：所有问题均与源代码相关。  
  如果我们专注于源代码，则需要一个标准来确定一个问题是否与源代码相关。 通过更改默认值，可以将所有问题都包含在指标中。

* 重新打开为新问题。 布尔值，定义是否将重新打开的问题视为新问题。 如果为 false，则意味着重新打开之前的关闭操作应视为无效。 注意：如果该参数为 false，则任何时期的关闭的问题数量都可能会在未来发生变化，如果其中一些问题被重新打开。

* 关闭标准。 算法。 默认：在相关时间内有关闭事件。


### 筛选条件

* 按参与者（提交者、评论者、解决者）。 需要合并同一作者对应的身份。

* 按参与者群组（雇主、性别…涉及每个参与者）。 需要参与者分组，并且可能需要参与者合并。


### 可视化效果

* 一段时间内每个周期的计数
* 一段时间内每个周期的比率

这些可以通过应用上述定义的筛选条件进行分组。 可以用条形图表示，X 轴为时间。


### 提供指标的工具

* [GrimoireLab](https://chaoss.github.io/grimoirelab) 为 GitHub 问题、GitLab 问题、Jira、Bugzilla 和 Redmine 提供了计算指标的数据。 当前仪表板根据创建日期显示信息，这意味着其显示了在某个时间段内创建的问题的当前状态（例如 [GitHub 问题仪表板](https://chaoss.github.io/grimoirelab-sigils/panels/github-issues/)，您可以查看[其运作中的状态](https://chaoss.biterg.io/app/kibana#/dashboard/GitHub-Issues)）。 不过，通过执行以下步骤，仍然可以轻松建立可视化效果基于关闭日期显示问题：
  - 按照说明向任意 GrimoreLab Kibiter 仪表板添加一个示例可视化效果：
    * 新建一个 `Vertical Bar` 图。
    * 选择 `github_issues` 索引。
    * 筛选条件：`pull_request` 为 `false`。
    * 筛选条件：`state` 为 `closed`。
    * 指标 Y 轴：`Count` 聚合，`# Closed Issues` 自定义标签。
    * 桶 X 轴：`Date Histogram` 聚合，`closed_at` 字段，`Weekly` 间隔（或任何适合您需求的间隔，取决于您希望在图表中可视化的整个时间范围），`Time` 自定义标签。
  - 屏幕截图示例：![GrimoireLab screenshot of metric issues_closed](https://github.com/chaoss/wg-evolution/blob/master/metrics/images/issues_closed_GrimoireLab.png)。


### 数据收集策略

**具体描述：GitHub**

对于 GitHub，关闭的问题定义为“关闭的问题”。

**具体描述：GitLab**

对于 GitLab，活跃的问题定义为“关闭的问题”。

**具体描述：Jira**

对于 Jira，活跃的问题定义为“变更为关闭状态的问题”。

**具体描述：Bugzilla**

对于 Bugzilla，活跃的问题定义为“变更为关闭状态的错误报告”。

## 参考资料

