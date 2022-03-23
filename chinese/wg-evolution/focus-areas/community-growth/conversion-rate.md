# 转化率

问题：新贡献者转化为更持久贡献者的转化比率是多少？
 

＃＃ 描述

转化率指标主要旨在确定新社区成员如何随着时间的推移成为更持久的贡献者。但是，转换率指标也可以帮助了解贡献者角色的变化、社区如何发展或衰退，以及在开源社区中进行维护的途径。

转化率指标可以通过表明新成员如何在项目中扮演越来越重要的角色来对多样性、公平性和包容性产生影响。通过转化率指标可以更好地理解多样性、公平性和包容性，以了解社区倡议和外展可能如何帮助或伤害成员更多地参与其中。
 

## 目标

- 观察新成员是否越来越多地参与开源项目
- 观察新成员是否在开源项目中担任领导角色
- 观察外展工作是否正在为开源项目产生新的贡献者
- 观察外展工作是否影响现有社区成员的角色
- 观察社区冲突是否会导致开源社区中角色的变化
- 确定临时、常规和核心贡献者

## 实现

### 过滤条件

- 提交
- 问题创建
- 发表评论
- 更改请求创建
- 更改请求评论
- 合并变更请求
- 代码审查
- 代码审查评论
- 反应（表情符号）
- 聊天平台消息
- 邮件列表消息
- 聚会出席

### 可视化
![社区整体结构](https://github.com/chaoss/wg-evolution/blob/main/focus-areas/community-growth/images/structure.png)

来源：https://chaoss.github.io/grimoirelab-sigils/assets/images/screenshots/sigils/overall-community-structure.png


![开发者级别](https://github.com/chaoss/wg-evolution/blob/main/focus-areas/community-growth/images/level.png)

来源：https://opensource.com/sites/default/files/uploads/2021-09-15-developer-level-02.png

### 提供指标的工具

- [GrimoireLab](https://github.com/chaoss/grimoirelab)
- [Augur](https://github.com/chaoss/augur)

### 数据收集策略

以下是来自 [openEuler](https://www.openeuler.org/en/) 社区的示例：

参加社区举办的线下活动A的一组人可以被识别为活动参与者。A组的人口统计信息可以在人们注册活动时从在线调查中获取。要确定这些参与者的转化率：

1) A组的一些人开始关注和Fork代码仓库，表明他们对这个社区表现出一定的兴趣。我们将它们标记为子组 D0（开发人员级别 0），作为 A 组的子集。
    - A组总人数与D0分组人数的转化率为：D0/活动参与者

2) 来自 D0 子组的一些人做出了更多的贡献，而不仅仅是Watch或Fork，包括创建Issue、对问题发表评论或执行代码审查。我们将它们标记为子组 D1（开发人员级别 1）作为 D0 的子集。
    - 子组 D0 的总人数与子组 D1 的人数的转换率为：D1/D0。

3) 来自 D1 子组的一些人继续为项目做出更多贡献，例如代码贡献。这可能包括创建合并请求和合并新的项目代码。我们将它们标记为子组 D2（开发人员级别 2）作为 D1 的子集。
    - 子组 D1 的总人数与子组 D2 的人数的转换率为：D2/D1。
	
![贡献者漏斗](https://github.com/chaoss/wg-evolution/blob/main/focus-areas/community-growth/images/funnel.png)


定义：
- 开发者 （D0）:  触达贡献者，合入 PR（Pull Request)、提交 Issue 或者评论 issue 或者PR ，以及针对代码仓库进行过 Star、Watch、或 Fork 的开发者
- 贡献者 （D1）:  广义贡献者，合入 PR（Pull Request)、提交 Issue 或者评论 issue 或者PR 的开发者
- 代码贡献者（D2）：狭义贡献者，合入了 PR（Pull Request) 的开发者
- 转化率（活动参与者-> D0）：CR（活动参与者-> D2）= D0/活动参与者
- 转化率 (D0 -> D1)：CR(Conversion Rate) (D0 -> D1) = D1/D0
- 转化率 (D1 -> D2)：CR(Conversion Rate) (D1 -> D2) = D2/D1


## 引用 
- https://opensource.com/article/21/11/data-open-source-contributors
- https://gitee.com/openeuler/website-v2/blob/master/web-ui/docs/en/blog/zhongjun/2021-09-15-developer-level.md  
- https://chaoss.github.io/grimoirelab-sigils/common/onion_analysis/ 
- https://mikemcquaid.com/2018/08/14/the-open-source-contributor-funnel-why-people-dont-contribute-to-your-open-source-project/  


## 贡献者 
- Yehui Wang 
- Clement Li 
- zhongjun 
- Xiaoya Xia 
- Matt Germonprez  
- Sean Goggins  
- King Gao  

