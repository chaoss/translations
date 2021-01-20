# 就业机会

问题：有多少招聘信息要求项目技术与技能？


## 描述

开源贡献者赚取生活费的一种常见方式是受雇于公司或成为自雇或自由开发者。 特定项目中的技能可能会改善求职者获得工作的前景。 与特定开源项目中所学技能相关的最明显需求指标是该项目或其技术纳入招聘信息中的时间。


## 目标

该指标可以让贡献者了解在特定开源项目中所学技能被公司重视的程度。


## 实现

要在求职平台（如 LinkedIn、Indeed 或 Dice）上获得这一指标，前往职位搜索并输入开源项目的名称。 返回的招聘信息数量即为指标。 通过求职平台的 API 定期收集指标并存储结果，即可查看趋势。


### 筛选条件

* 招聘信息时长；信息会过时，填写后可能不会被移除


### 可视化效果

可以查看以下内容扩展指标：

* 返回的职位的薪资范围
* 返回的职位的资历水平
* 现场或非现场职位的可用性
* 工作地点
* 地理位置


## 参考资料

* LinkedIn 职位搜索 API：https://developer.linkedin.com/docs/v1/jobs/job-search-api#
* Indeed 职位搜索 API：https://opensource.indeedeng.io/api-documentation/docs/job-search/
* Dice.com 职位搜索 API：http://www.dice.com/external/content/documentation/api.html
* Monster 职位搜索 API：https://partner.monster.com/job-search
* Ziprecruiter API（需要合作）：https://www.ziprecruiter.com/zipsearch

_注意：_此指标仅限于单个项目，但参与开源也可由其他原因获益。 这一指标可以超越单一项目，改为使用编程语言、进程、开源经验或框架等相关技能作为职位的搜索参数。
