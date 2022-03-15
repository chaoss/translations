# 偶尔贡献者

问题: 我们该如何理解偶尔贡献者的数量和他们所做的贡献?

同义词: 顺路贡献者; 临时贡献者，片段贡献者

## 描述
偶尔贡献者是那些不定期地对项目作出贡献的人。在社区中，偶尔贡献者非常重要，因为他们的贡献可以以有意义的方式推进项目。对于偶尔贡献者，一个精确的定义是“至少3个月没有提交变更请求（pull request），并且在项目中总共没有贡献超过12个变更请求（pull request）的人”[1]

偶尔贡献者的动机:
- 自助服务: 一个人有一个需要修复的bug，所以他们提交了一个议题（issue）或修复。
- 工作相关的: 一个人为一家公司工作，公司需要修复一个 bug 或新功能。
- 特殊项目或用例: 一个人需要让他们自己的项目在 Commodore 64 或 Atari 800XL 上运行。
- 文档添加/修复: 一个人正在修复一个错别字。
- 编程马拉松、研讨会或其他活动: 一个人为了一个特定的目的或目标参加了一个有时间限制的活动。
- 次优尝试: 一个人本打算留在社区做贡献，但是最终认为社区或项目不适合他们。
- 生活事件: 一个人本打算留在社区做贡献，但可能经历了一个生活事件，限制了他们参与开源。

## 目标
监控偶尔贡献者可以帮助你理解以下情况:
- 越来越多的人正在关注这个项目
- 越来越多的人在使用这个项目
- 贡献流程运转良好
- 更多的人能够为这个项目做出贡献 
- 存在更多的贡献者，以转化为可靠的社区成员

所有这些都可以帮助您提高对项目健康状况的理解。

## 实现

健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅 CHAOSS 数据伦理文档以获得更多指导。

### 筛选条件
- 在某人不再是偶然贡献者之前的最小贡献数量。 
- 在某人不再被视为偶然贡献者之前，两个贡献间隔的最长时间 
- 被归类为偶尔贡献者的数量占贡献者总数的百分比
- 重复出现的偶尔贡献者 

### 可视化效果

![Occasional Contributors Augur](images/occasional-augur.png)

来自 Augur https://tinyurl.com/augur-flyby 

Augur API 文档: https://tinyurl.com/augur-flyby-docs 

![Occasional Contributors Cauldron](images/occasional-caudron.png)

来自: https://cauldron.io/

### 提供指标的工具
- [Cauldron.io](https://cauldron.io/)
- [Devstats](https://devstats.cncf.io/)
- [Augur](https://github.com/chaoss/augur)

## 参考资料
[1] https://k8s.devstats.cncf.io/d/18/new-and-episodic-pr-contributors?orgId=1 

[2] [Have It Your Way: Maximizing Drive-Thru Contributions by VM Brasseur](https://www.youtube.com/watch?v=q3ie1duhpCg)

## 贡献者
- Matt Germonprez
- Regina Nkemchor Adejo
- Dawn Foster
- Kevin Lumbard
- Vinod Ahuja
