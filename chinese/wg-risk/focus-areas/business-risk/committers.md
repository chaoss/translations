# Committers

问题：社区贡献者的健壮性如何？

## 描述
Committers指标是已向项目提交代码的个人数量。 这与更广泛构造的[“贡献者”CHAOSS 指标](https://github.com/chaoss/wg-common/blob/master/focus-areas/who/contributors.md)不同，直接针对管理者在决定使用哪个开源项目时，风险评估中出现的一个特定问题。  虽然不一定在所有情况下都是如此，但人们普遍认为，一个项目的贡献者越多，该项目就越有可能继续得到更新、支持和必要的资源。 因此，该指标使各组织能够在知情的情况下决定，给定项目的提交者人数是否可能在当前或未来构成项目被放弃或支持不足的风险。

## 目标

从管理者决定将开源项目纳入其组织的角度来看，提交者的数量有时很重要。  特别是代码贡献与更大规模的贡献者指标（包括文档作者、创建问题的个人和其他类型的贡献）可能会有很大不同，具体取决于开源项目所采用的管理风格。 McDonald 等人 (2014) 让人们注意到不同开源项目如何遵循开放分布式模型，而其他项目则遵循高度集中式模型。 较少的代码贡献者可能表明项目对外部贡献的开放程度较低，或者是项目中只有少数人了解并对代码库做出贡献。

## 实现

在开源项目中，每个有提交合并到项目的电子邮件地址都是一个“提交者”（见下一节的“已知问题”）。 建议确定特定时间段内唯一的提交者数量，这样做的公式也很简单：

`Number_of_committers = distinct_contributor_ids (在具有开始日期和结束日期的一段时间内)`。 例如，我可能想知道在过去的 18 个月里，有多少不同的人向一个项目提交了代码。 `Committers` 揭晓答案。

### 数据质量的已知问题
* 许多贡献者使用不止一个邮箱，如果不协调这些共享身份，可能会人为地提高提交者总数。
* 几个提交者“顺便”做出一些微小的贡献，也可能人为地提高这一数字。

### 可视化效果

Grimoire Lab 显示提交者

![Grimoire Lab Committers](images/committers_grimoire-lab.png)

### 筛选条件
* 时间：较新的不同Committer的数量可能比项目（代码仓）整个生命周期内的人数更能清楚地表明参与项目的人数。
* 提交大小：按代码行数衡量的少量代码提交可以被排除，避免已知问题
* 提交次数：某一时间段内提交次数少于某个最低限度的贡献者可从这一数字中排除。

## 提供指标的工具
Augur 为代码仓中的每条提交记录维护了一个表格。

![Augur Committers](images/committers_augur.png)

要评估一个代码仓的不同提交者，可以使用以下 SQL 或文档化的 API 端点：
```sql
SELECT
    cmt_author_name,
    COUNT ( * ) AS counter
FROM
    commits
WHERE
    repo_id = 22159
GROUP BY
    cmt_author_name
ORDER BY
    counter DESC
```

该表达式使最终用户能够按提交计数阈值轻松筛选，返回的行数就是代码仓的“Total_Committers”。

[Grimoire Lab](https://chaoss.biterg.io/app/kibana#/dashboard/Git) 还额外提供了针对Committer的洞察能力。

## 参考资料
1. Nora McDonald, Kelly Blincoe, Eva Petakovic, and Sean Goggins. 2014. Modeling Distributed Collaboration on GitHub. Advances in Complex Systems 17(7 & 8).
