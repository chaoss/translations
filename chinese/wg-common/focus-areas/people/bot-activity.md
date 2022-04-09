# 机器人（bot）活动 

问题: 自动化机器人活动的数量是多少？

## 描述
机器人是一种支持项目活动的软件。机器人在开源项目中扮演着越来越重要的角色，帮助协调开源项目的工作。机器人支持各种工作流程，包括议题和合并请求管理和贡献者协议。机器人为开源软件项目提供了许多选择，以决定如何有效地管理项目工作。

## 目标
机器人活动指标有助于区分人和自动化应用程序（例如，机器人）的项目活动。这样一来，社区管理者可以更好地区分新贡献者的增加、CLA机器人活动和机器人相关的访问控制等。这个指标可以为以下方面提供额外的背景。
* [首次响应时间](https://chaoss.community/metric-time-to-first-response/)
* 构建处理时间 
* 社交考虑 -- 不是所有机器人 
* 成熟度
* 社区大小 
* 项目透明度

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

* 随着时间推移，机器人与人类活动的比率
* 随着时间的推移，机器人的平均数量 

### 过滤条件 
* 具有用户档案的机器人
* 需要人工交互的机器人 
* 自行运行的机器人 
* 协助软件开发的机器人 
* 协助沟通的机器人
* 协助访问控制的机器人
* 协助包容性的机器人 
* 使用机器人的平台 (例如, GitHub, Slack)

### 可视化效果 

![k8s.devstats.cncf.io](https://user-images.githubusercontent.com/656208/130105428-f9a0cc9e-dc7a-43e3-a654-25261cb4cae8.png)

From: https://k8s.devstats.cncf.io/d/5/bot-commands-repository-groups?orgId=1&var-period=w&var-repogroup_name=Kubernetes&var-repo_name=kubernetes%2Fkubernetes&var-commands=All


## 参考资料
- [6个可以帮助你开源项目的机器人](https://www.twilio.com/blog/6-bots-better-open-source-project)
- [GiHub的Hubot](https://hubot.github.com/)

## 贡献者
- Sean Goggins
- Matt Germonprez
- Kevin Lumbard
- Dawn Foster
- Elizabeth Barron
- Vinod Ahuja
- Matt Cantu

