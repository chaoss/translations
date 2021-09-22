# 代码克隆（clone）

问题: 在本地机器上保存了多少份开源项目代码仓的副本？

## 描述
代码克隆（clone）是保存到本地计算机的代码仓的副本。

**注意:**  许多时候代码克隆（clone）和 [技术分支（technical fork）](https://github.com/chaoss/translations/blob/main/chinese/wg-common/focus-areas/contributions/technical-fork.md) 可以互换使用，但是两者之间是有区别的。 一个 [技术分支（technical fork）](https://github.com/chaoss/translations/blob/main/chinese/wg-common/focus-areas/contributions/technical-fork.md) 是同一代码托管平台上代码仓的副本, 而 代码克隆（clone）是本地计算机上的副本。

![Technical Fork & Clones](images/technical-fork-clones_fork-clones.png)

[图片来源于 Stakeoverflow](https://stackoverflow.com/questions/9257533/what-is-the-difference-between-origin-and-upstream-on-github/9257901#9257901)

## 目标

代码克隆（clone）指标的目标是确定一个项目的下载数量。对代码克隆（clone）的分析可以帮助我们深入了解这个项目的受欢迎程度和使用情况。

## 实现

### 过滤条件 
* 时间周期 (例如, 按星期、月份、年份分的代码克隆（clone）量)
* 部分代码克隆（clone）(由 gitlab 提供 https://docs.gitlab.com/ee/topics/git/partial_clone.html#partial-clone)

### 可视化效果 
 
![GitHub Clones](images/clones_github_clones.png)

[图片来源于 Github 博客](https://github.blog/2014-08-12-clone-graphs/)


## 参考资料
* [分叉和克隆代码仓之间的区别是什么？](https://github.community/t/the-difference-between-forking-and-cloning-a-repository/10189)
* [分叉和克隆的区别是什么？](https://opensource.com/article/17/12/fork-clone-difference)
* [Github API]([https://docs.github.com/en/rest/reference/repos#get-repository-clones](https://docs.github.com/en/rest/reference/repos#get-repository-clones))

## 贡献者
* Vinod Ahuja
* Sean Goggins 
* Matt Germonprez
* Kevin Lumbard
* Dawn Foster 
* Elizabeth Barron
