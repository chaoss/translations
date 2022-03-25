# 代码变更提交

问题: 在一次变更请求中，包含了多少次 [提交](https://chaoss.community/metric-change-requests/)? 

同义词: PR提交, Merge提交
## 描述
这个指标枚举了通过git平台的每一个变更请求相关的代码提交，并列出了每个提交的[贡献者](https://chaoss.community/metric-contributors/)，以及相关的父提交。

在审核代码托管平台的更改请求提交时，需要注意许多细微差别。与直接从软件代码仓中挖掘的代码提交数据相比，是否压缩提交、何时压缩以及如何压缩提交对报告的变更请求提交数据有很大的影响。例如，在变更请求合入时，提交通常会压缩。这通常会导致API提供的更改请求提交数据的细节较少。而且每个变更请求也会成为被合并分支的一次提交。值得注意的是，只有提交到默认分支时，才会反映在此代码仓的代码提交指标中。也可以从其他分支挖掘提交和拉取提交请求，但这种做法并不常见。

注意: 通常有一些更改请求不在默认分支中。

2021特别提示: 针对主分支的变更提交请求分析应考虑主分支名称的变化。从2021年开始，许多项目的默认分支从“master”变成了“main”。少数项目使用main或master以外的名称作为其默认分支，工具应该考虑到这一点，在分析提交日志之前注意检查默认分支的名称。当默认分支的名称更改时更应注意。

## 目标
1. 该指标提供的信息可以帮助告知通常如何管理代码仓的变更请求流程。在开发的过程中，合并请求中的提交数量和参与提交代码的人数往往是一致的。但纵观所有的开源项目中，他们却有所不同。
2. 维护人员能够知道贡献者在某一提交请求中与其他贡献者协作的历史。 
3. 变更请求提交的总数越大，合并的复杂性就越大。意识到这一点有助于为之后的维护人员明确潜在的贡献者，例如需要具备更高的技能水平。
4. 了解变更请求提交的数量可以了解潜在变更请求的复杂性，并可能影响代码仓的策略和指导方针。
5. 识别与更典型的提交模式不同的变更请求(如提交大小、提交顺序)或变更请求模式(如提交数量)。
6. 这个度量可以通过探索通过变更请求过程获得提交的贡献者的[人口统计数据](https://github.com/drnikki/open-demographics)来告知项目的多样性和包容性。


## 实现
__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[ CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/blob/main/resources)以获得更多指导。__
### 过滤器
* 每次提交添加的代码行数
* 每次提交删除的代码行数
* 在一段时间内代码的更改
* 提交中的迭代(在合并请求中包含的提交中，同一个文件被涉及的次数)
* 每次提交变更的文件数
* 每次提交的贡献者数量

### Visualizations 

![augur_api](images/change-request-commits_augur-api.png)


[图片来源](http://augur.chaoss.io/api/unstable/pull_request_reports/average_commits_per_PR?repo_id=25440&start_date=06-01-2021)

### 提供度量的工具 

* Augur
    * API Endpoint: [http://augur.chaoss.io/api/unstable/pull_request_reports/average_commits_per_PR?repo_id=25440](http://augur.chaoss.io/api/unstable/pull_request_reports/average_commits_per_PR?repo_id=25440) 
* GrimoireLab
    * [https://chaoss.github.io/grimoirelab-sigils/chaoss-gmd-cde/lines_of_code_changed/](https://chaoss.github.io/grimoirelab-sigils/chaoss-gmd-cde/lines_of_code_changed/) 

### 数据收集策略
* 挖掘 git 日志
* 平台API调用

## 参考文献
* [Goggins, S., Lumbard, K., & Germonprez, M. (2021). Augur: Architecture for Capturing, Reshaping, and Socially Contextualizing Open Source Software Communities. ACM SoHeal Conference. International Conference on Software Engineering, Virtual. https://doi.org/DOI: 10.5281/zenodo.4627236  ](https://www.seangoggins.net/wp-content/plugins/zotpress/lib/request/request.dl.php?api_user_id=655145&dlkey=HNG22ZSU&content_type=application/pdf)


## 贡献者
* Vinod Ahuja
* Kevin Lumbard
* Elizabeth Barron
* Sean Goggins
* Armstrong Foundjem 


