# 审查

问题：在一段时间内发生了哪些新的变更源代码的审查请求？

## 描述
当项目采用代码审查进程时，变更并不直接提交至代码库，而是先以“源代码变更提案”的形式进行讨论。 每一个提案都应由其他开发者审查，这些开发者可能会提出改进建议，让原始提议者发送新版本的提案，直到取得肯定的审查结果，接受代码，或者直到提案被拒绝。

例如，“审查”在 GitHub 中对应“拉取请求”，在 GitLab 中对应“合并请求”，在 Gerrit 中对应“代码审查”，在 Gerrit 中对应“变更集”。


## 目标
* 提议的项目变更量。 审查是项目活动的代理。 统计一个项目对应的仓库集合中的代码变更审查，可以让您了解该项目中审查变更的整体活动。 当然，该指标不是唯一用于跟踪编码活动量的指标。


## 实现

**聚合器：**
* 计数。 一段时间内审查的总数。

**参数：**

* 时间段。 开始日期和完成日期。 默认：永久。  
  考虑审查的时间段。

* 源代码标准。 算法。 默认：所有文件均为源代码。  
  如果我们专注于源代码，则需要一个标准来确定一个文件是否为源代码的一部分。


### 筛选条件

* 按参与者（提交者、审查者、合并者）。 需要参与者合并（合并同一作者的对应 ID）。
* 按参与者群组（雇主、性别…涉及每个参与者）。 需要参与者分组，并且可能需要参与者合并。
* 状态（打开，关闭）


### 可视化效果

* 一段时间内每个月的计数
* 一段时间内每个群组的计数

可以用条形图表示，X 轴为时间。 每个条形代表一定时间（如一个月）内更改代码的审查。



### 提供指标的工具

* [Grimoirelab](https://chaoss.github.io/grimoirelab) 为 GitHub 拉取请求、GitLab 合并请求和 Gerrit 变更集开箱即用地提供该指标。
  - 查看 [Bitergia Analytics 的 CHAOSS 实例](https://chaoss.biterg.io/app/kibana#/dashboard/GitHub-Pull-Requests)示例。
  - 基于 GitHub 拉取请求数据，从 [GrimoireLab Sigils 面板集合](https://chaoss.github.io/grimoirelab-sigils/panels/github-pullrequests/)下载并导入包含此指标可视化效果示例的现成仪表板。
  - 按照说明向任意 GrimoreLab Kibiter 仪表板添加一个 GitHub 拉取请求的示例可视化效果：
    * 新建一个 `Vertical Bar` 图。
    * 选择 `github_issues` 索引。
    * 筛选条件：`pull_request` 为 `true`。
    * 指标 Y 轴：`Count` 聚合，`# Pull Requests` 自定义标签。
    * X 轴：`Date Histogram` 聚合，`grimoire_creation_date` 字段，`Auto` 间隔，`Time` 自定义标签。
    * 桶拆分系列：`Terms` 子聚合，`state` 字段，`metric: # Pull Requests` 排序依据，`Descending` 排列，`1000` 大小，`State` 自定义标签。 注意，这一可视化效果基于拉取请求的创建日期，所以项的创建日期被计算在内，而这里设置的状态，呈现数据时的当前状态，例如，在给定时间范围内创建的 `n` 个拉取请求当前 `open` 或 `closed`。
  - 屏幕截图示例： ![GrimoireLab 审查指标截图](https://github.com/chaoss/wg-evolution/blob/master/metrics/images/reviews-GrimoireLab.png)


### 数据收集策略

**具体描述：GitHub**

对于 GitHub，审查定义为“拉取请求”，前提是其提出对源代码文件的变更。

审查的日期可以定义为（为了在或不在一段时间内考虑）拉取请求的提交日期。

**具体描述：GitLab**

对于 GitLab，审查定义为“合并请求”，前提是其提出对源代码文件的变更。

审查的日期可以定义为（为了在或不在一段时间内考虑）合并请求的提交日期。

**具体描述：Gerrit**

对于 GitLab，审查定义为“代码审查”，某些上下文中为“变更集”，前提是其提出对源代码文件的变更。

审查的日期可以定义为（为了在或不在一段时间内考虑）通过提交补丁集进行审查而开始代码审查的日期。

## 参考资料
