# 代码变更

问题：在指定时间内源代码变更了多少？


## 描述

这些是指定时间内源代码的变更。 对于“变更”，我们会考虑开发者认为的代码的原子变更。 换句话说，变更是对源代码的一些更改，通常作为一个整体被接受和合并，根据需要也会作为一个整体被还原。 例如，对于 git，每个“变更”对应一个“提交”，或者更准确地说，“代码变更”对应于触及被视为源代码的文件的提交部分。


## 目标

* 编码活动量。 代码变更是项目活动的代理。 统计一个项目对应的仓库集合中的代码变更，可以让您了解该项目中的整体编码活动。 当然，该指标不是唯一用于跟踪编码活动量的指标。


## 实现

**聚合器：**
* 计数。 一段时间内变更的总数。

**参数：**
* 时间段。 开始日期和完成日期。 默认：永久。 考虑变更的时期。
* 源代码标准。 算法。 默认：所有文件均为源代码。 如果专注于源代码，需要一个标准来确定一个文件是否为源代码的一部分。


### 筛选条件

* 按参与者（作者、提交者）。 需要参与者合并（合并同一作者的对应 ID）。

* 按参与者群组（雇主、性别…）。 需要参与者分组，并且可能需要参与者合并。

* 按[标记](https://www.odoo.com/documentation/13.0/reference/guidelines.html#tag-and-module-name)（用于提交的消息）。 需要提交消息的结构。 在开源项目中，此标记可用于和每个贡献者交流，例如，提交是错误修复或功能改进的情况。

### 可视化效果

* 一段时间内每个月的计数
* 一段时间内每个群组的计数

可以用条形图表示，X 轴为时间。 每个条形代表一定时间（如一个月）内的代码变更。


### 提供指标的工具

* [GrimoireLab](https://chaoss.github.io/grimoirelab) 支持此指标，开箱即用。
  - 查看 [Bitergia Analytics 的 CHAOSS 实例](https://chaoss.biterg.io/app/kibana#/dashboard/Git)示例。
  - 从 [GrimoireLab Sigils 面板集合](https://chaoss.github.io/grimoirelab-sigils/panels/git/)下载并导入包含此指标可视化效果示例的现成仪表板。
  - 按照说明向任意 GrimoreLab Kibiter 仪表板添加一个示例可视化效果：
    * 新建一个 `Vertical Bar` 图
    * 选择 `git` 索引
    * Y 轴：`Unique Count` 聚合，`hash` 字段，`# Commits` 自定义标签
    * X 轴：`Date Histogram` 聚合，`grimoire_creation_date` 字段，`Auto` 间隔，`Time` 自定义标签
  - 屏幕截图示例： ![GrimoireLab 指标截图 Code_Changes](https://github.com/chaoss/wg-evolution/blob/master/metrics/images/code_changes-GrimoireLab.png)

* [Augur](http://augur.osshealth.io/) 将此指标作为[代码变更](http://augur.osshealth.io/api_docs/#api-Evolution-code_changes_repo/)和[代码变更行](http://augur.osshealth.io/api_docs/#api-Evolution-code_changes_lines_repo)提供。 两个指标均以 `repo` 和 `repo_group` 形式提供，更多信息见 [Augur 文档](https://oss-augur.readthedocs.io/en/master/getting-started/create-a-metric/overview.html#metric-forms)。

* [Gitdm](https://repo.or.cz/w/git-dm.git)


### 数据收集策略

**具体描述：Git**

请参阅 [git 的参考实现](https://github.com/chaoss/wg-evolution/blob/master/implementations/notebooks_df/code_changes_git.ipynb)

强制性参数（对于 Git）：

* 日期类型。 作者日期或提交者日期。 默认：作者日期。  
  对于每个 git 提交，都会保留两个日期：撰写提交的日期和提交到仓库的日期。 为了确定时间段，必须选择其中一项。

* 包括合并提交。 布尔值。 默认：True。  
  合并提交是指合并一个分支的提交，在某些情况下不认为反映编码活动。

* 包括空提交。 布尔值。 默认：True。  
  空提交是未触及文件的提交，在某些情况下不认为反映编码活动。

## 参考资料

* https://www.odoo.com/documentation/13.0/reference/guidelines.html#tag-and-module-name
