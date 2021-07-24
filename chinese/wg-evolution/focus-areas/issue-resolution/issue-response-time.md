# 问题响应时间

问题：从问题创建到另一贡献者在问题线程中做出响应经过了多长时间？

## 描述
这一指标表明从问题创建到其他贡献者响应之间的时间间隔。

这一指标是[共同工作组](https://github.com/chaoss/wg-common)中[第一响应时长](https://github.com/chaoss/wg-common/blob/master/focus-areas/when/time-to-first-response.md)的特定情况。


## 目标
了解开源社区的响应能力。

## 实现

**聚合器：**
* 平均数。 平均响应时间（天）。
* 中位数。 中位响应时间（天）。

**参数：**
* 时间段。 开始日期和完成日期。 默认：永久。
*  计算响应的时期。

### 筛选条件
* 项目角色的响应（例如，第一维护者响应）
* 机器人与人类（例如，滤除自动化的“欢迎第一贡献者消息”）
* 由项目中的角色创建（例如，对新贡献者的响应与长期贡献者的响应）
* 打开问题的日期
* 问题的状态（例如，仅查看当前未解决问题）

### 可视化效果

![GrimoireLab 的示例可视化效果](images/issue-response-time_grimoirelab.png)

### 提供指标的工具
* GrimoireLab：[任意票证系统的一般情况](https://chaoss.github.io/grimoirelab-sigils/panels/efficiency-timing-overview/)、[GitHub 问题](https://chaoss.github.io/grimoirelab-sigils/panels/github-issues-efficiency/)、[GitLab 问题](https://chaoss.github.io/grimoirelab-sigils/panels/gitlab-issues-efficiency/)
* [Augur](http://augur.osshealth.io/api_docs/#api-Evolution-Issue_Response_Time_Repo_)

### 数据收集策略

查看[新问题](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_New.md)指标的“问题”定义。 从第一响应时间戳中减去创建问题的时间戳。 如果问题的作者创建了响应，则不计算响应。

## 参考资料
