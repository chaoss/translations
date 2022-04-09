# 变更请求评审

问题：[变更请求](https://chaoss.community/metric-change-requests/) 评审用平台功能进行正式审核流程到什么程度？

＃＃ 描述
变更请求是指由评估变更质量的其他开发人员进行审查，以确保变更符合项目宗旨。变更请求的审查内容可能会建议改进或合并前再进行改变。软件工程研究认识到代码审查的通用工具可以提高软件质量（Baker 等人，1997；Kemerer 等人，2009）。对于许多项目，成功合并更改需要审阅者在其上签字。该指标评估正式审核流程，并确定在接受或拒绝变更请求之前如何审核，以及在何种程度上对其进行审核。


变更请求审查包括关于整个变更请求的优先级评论、要求特定变更的文件级别评论，以及变更请求是否被“接受”、“已请求变更”，或者变更请求被关闭而不合并的原因。

注意：
* 对项目仓库默认分支的变更请求可能与移动到开发分支的变更请求具有不同的审查特征。
* 变更请求审查在实践中以多种不同方式实施。例如，一些项目使用变更请求评论作为一种审查形式，而其他项目使用主要开源软件开发平台上提供的更正式的变更请求审查功能。有时会记录项目的具体审查实践。

## 目标
了解项目仓库内以及跨项目仓库集合的变更请求审查实践的性质。

变更请求审查可以帮助告知代码的质量和代码开发的效率。

随着时间的推移检查变更请求审查过程和及时性有助于展示开源软件项目的演变。

## 实现
__健康指标的使用和传播可能导致侵犯隐私。组织可能会面临风险。这些风险可能源于遵守欧盟的 GDPR、美国的州法律或其他法律。 GitHub 和 GitLab 等数据提供商的服务条款也可能存在合同风险。必须检查指标的使用是否存在风险和潜在的数据伦理问题。请参阅 [CHAOSS 数据伦理文档](https://github.com/chaoss/metrics/blob/main/resources) 获取更多指导__

### 聚合

* 使用平台功能正式审查的变更请求百分比是多少？
* 审查的变更请求附带审查的平均数和中位数是多少？
* 相互竞争的开源项目和通常部署在一起的开源项目在变更请求审查过程中存在哪些差异？

### 过滤条件
* 进行评论的唯一 [贡献者](https://chaoss.community/metric-contributors/) 的数量
*机器人与人类评论
* [接受变更请求](https://chaoss.community/metric-change-requests-accepted/)
* [拒绝变更请求](https://chaoss.community/metric-change-requests-declined/)
* [变更请求持续时间](https://chaoss.community/metric-change-requests-duration/)
* [变更请求接受率]([https://chaoss.community/metric-change-request-acceptance-ratio/](https://chaoss.community/metric-change-request-acceptance-ratio/))

* 变更请求审查流程是否记录在 CONTRIBUTING.md 文件中？
    * 项目是否有 CONTRIBUTING.md 文件？
    * 如果是这样，CONTRIBUTING.md 文件是否包含“review”一词？
    * 项目是否遵循这些准则？ （这需要与可观察到的做法相比，对文件进行定性审查）。
* 时间段：确定变更请求审查实践分析的开始和结束日期。



### 提供指标的工具
Augur 提供了这些表格，其中存储了评论信息。以后将开发一个API来提供这些评论信息。
    * Pull_request_reviews（对变更请求的所有评审）
    * Pull_request_reviewers（所有变更请求审阅者）
    * Pull_request_review_msg_ref（来自变更请求审阅者的消息的桥接表）
    * 消息（变更请求、问题、电子邮件、松弛和变更请求审查消息和评论）


### 数据收集策略
* [GitHub API] (https://docs.github.com/en/rest/reference/issues#comments)
* [Gitlab API] (https://docs.gitlab.com/ee/api/notes.html)


＃＃ 参考
* [https://opensource.com/article/19/3/managing-changes-open-source-projects](https://opensource.com/article/19/3/managing-changes-open-source-projects )
* [https://about.gitlab.com/handbook/engineering/infrastructure/change-management/](https://about.gitlab.com/handbook/engineering/infrastructure/change-management/)
* Baker Jr, Richard A. “代码审查提高了软件质量。” _第十九届软件工程国际会议论文集_。 1997 年。
* Kemerer、Chris F. 和 Mark C. Paulk。 “设计和代码审查对软件质量的影响：基于 psp 数据的实证研究。” _IEEE 软件工程交易_ 35.4 (2009): 534-550

## 贡献者
* Kevin Lumbard
* Elizabeth Barron
* Vinod Ahuja
* Sean Goggins
* Enoch Kaxada

