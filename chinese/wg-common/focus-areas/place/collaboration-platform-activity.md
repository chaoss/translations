# 协作平台活动

问题: 项目使用的跨数字协作平台(例如 GitHub, GitLab Slack, email)的活动总数是多少？
问题: 项目使用的跨数字协作平台的活动总数是多少？

## 描述
开源项目使用许多不同的数字通信和协作平台。这些平台可能包括电子邮件、社交媒体、聊天应用程序和代码管理技术(例如 GitHub, GitLab)。这个度量标准衡量跨协作平台发生的消息活动的位置和数量。

## 目标
了解社区在哪里协作。当我们去拓展洞察每个项目所遵循的相关流程，如果对交流日志的审查尽可能完整，这些洞察会更准确。展示一个项目是多么的开放和透明。帮助人们找到合适的地方做出贡献，并与项目联系起来。帮助项目维护者确定最佳的渠道数量，可以切实有效的分享信息，同时允许贡献者以最适合他们的方式连接。找到最低障碍的渠道参与。其他相关指标，如: [突发性波动](https://chaoss.community/metric-burstiness/), [项目发展速度](https://chaoss.community/metric-project-velocity/), [社会聆听](https://chaoss.community/metric-social-listening), [活动的日期和时间](https://chaoss.community/metric-activity-dates-and-times/), [聊天平台包容性](https://github.com/chaoss/wg-diversity-inclusion/issues/318)

## 实现
数据收集的单位是平台上的单个活动。与该指标有关的元数据可以包括:
* 时间戳
* 发件人
* 多线程/非线程平台
* 数据收集日期
* 平台消息标识符

### 过滤条件
* 人数
* 消息数
* 议题和变更请求的评论数
* 平台种类 (邮件列表，irc等))
* 一周每天的活动量


### 可视化效果

![GrimoireLab 实现](images/collaboration-platforms.png)

https://chaoss.biterg.io/app/kibana#/dashboard/ab68fe20-17f2-11e9-872f-e17019e68d6d

### 提供度量的工具
* Orbit.love 是一个社区管理平台，可以从几个平台获取这些信息: https://docs.orbit.love/docs/adding-activities
* GrimoireLab
* Augur


## 参考资料
* 相关指标: https://chaoss.community/metric-chat-platform-inclusivity/
* 相关指标: https://chaoss.community/metric-issues-new/

## 贡献者

* Elizabeth Barron
* Sean Goggins
* Matt Germonprez
* Danial Izquierdo
* Dawn Foster
* Beth Hancock
* Kevin Lumbard
