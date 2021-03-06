# 变更请求中审查周期的持续时间

问题: 单个变更请求中审查周期的持续时间是多少?

## 描述

一个变更请求会基于一个或者多个审查周期。 在一个审查周期内，一个或多个审查者可以对提议的贡献提供反馈。 审查周期的持续时间，或贡​​献的每次新迭代之间的时间，是该指标的基础。

## 目标
该项目为项目维护者提供的相关洞察:
* 代码审查过程迟滞缓慢, 因为有更多的的迭代以及审查周期增加。
* 流程瓶颈导致代码审查迭代时间长。
* 审查周期中维护者或提交者响应缓慢，导致审查周期处于放弃或者半放弃状态。
* 具有不同审查循环周期长度的评论的特征。

## 实现
审查周期持续时间用于衡量单个变更请求中一个审核周期的时间长度。
持续时间可以计算的间隔包括:
* 每个审查周期开始的时刻，定义为提交或更新变更请求的时间点。
* 每个审查周期结束的时刻，可能是因为变更请求已更新并需要重新审查，或者是因为变更请求被接受或拒绝。

### 筛选条件

平均或中位值持续时间, 可以选择性的使用过滤或者分组条件包括:
* 参与审核的人数
* 审核中的评论数
* 变更请求中涉及的修改文件或者代码
* 提出变更请求的项目或组织
* 提交变更请求的时间
* 为变更请求做出贡献的开发人员
* 变更请求
* 变更请求的审核周期数 （例如，按第一、第二、……轮过滤）

### 可视化效果
### 提供度量的工具

## 参考资料

可用于实现度量的数据示例: https://gerrit.wikimedia.org/r/c/mediawiki/core/+/194071
