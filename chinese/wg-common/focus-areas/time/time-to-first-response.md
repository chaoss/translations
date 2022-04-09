# 第一响应时长

问题：对于需要关注的活动，从创建到第一次响应需要多长时间？


## 描述

对活动的首次响应有时可能是最重要的响应。 首次响应表明社区活跃并且积极参与沟通。 如果对活动的响应时间较长，可能表示社区不够积极。 短时间内对活动做出响应，有助于吸引更多成员参与社区内的进一步讨论。


## 目标

确定各种活动的首次响应节奏，涉及 PR、问题、电子邮件、IRC 帖子等。对于项目的新贡献者、长期贡献者以及整体项目健康情况，首次响应时长都是一项重要考虑因素。


## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

活动的首次响应时长 = 首次响应发布到活动的时间 - 活动创建时间。


### 筛选条件

* 回复者的角色，例如，只计算维护者的响应
* 自动响应，例如，通过筛选排除机器人和其他自动回复，只统计真人回复
* 活动类型，如问题（见指标[问题响应时间](https://chaoss.community/metric-issue-response-time/)）、电子邮件、聊天信息、变更请求


### 可视化效果

![GrimoireLab 面板：效率时序总览](images/time-to-first-response_efficiency-timing-overview.png)

---------

![Augur 可视化效果：首次响应时长热图 ](images/time-to-first-response_augur-ttc-1.png)

---------

![Augur 可视化效果：平均响应时间](images/time-to-first-response_augur-ttc-2.png)

### 提供指标的工具

* GrimoireLab 面板：[效率时序总览](https://chaoss.github.io/grimoirelab-sigils/panels/efficiency-timing-overview/)
* [Kata Containers 仪表板效率面板](https://katacontainers.biterg.io/app/kibana#/dashboard/cbbdd920-288c-11e9-b662-975152e57997)

## 参考资料


