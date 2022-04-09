# 依赖库年龄

问题:与当前的稳定版本相比，项目的依赖库的年龄是多少？

## 描述
Libyears 解释了与项目[依赖库](https://github.com/chaoss/wg-risk/blob/master/focus-areas/dependency-risk-assessment/upstream-code-dependencies.md)的当前稳定版本相比，项目(代码仓，或者可构建软件的代码仓)依赖库的年龄是多少。依赖库的“当前稳定”版本是一个用于一般用途的版本，不包括候选/草稿版本。年龄是一个项目的所有依赖关系的累积，可以通过多种方式确定，比如报告总年龄、平均年龄，可能还有中位年龄(注意，如果有长长的年龄尾巴，中位年龄可以隐藏这个问题)。一般来说，较低的依赖库年龄更好。工具还应该提供按年龄排序的依赖库列表，以提供更深入的了解。度量这一概念是在“测量软件系统中的依赖新鲜度”中由 Cox 等人[ Cox 2015]提出的。

注意: 在某些情况下，使用旧版本代替当前版本可能是更明智的选择; 也就是说，这个度量提供了洞察以帮助其他人确定哪些旧版本在使用。

## 目标
依赖库年龄度量的目标是帮助识别对项目稳定性、安全性和脆弱性构成风险的依赖库。一个早已过时的组件更有可能具有公开知道的漏洞，而且也不太可能得到良好的支持。它是一个有用的初始过滤器，用于对依赖关系进行分类，以帮助识别最值得仔细检查的项目的依赖关系。

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__

### 参数
默认情况下，这些信息将存在于一个软件生态系统中(例如 JavaScript 或 Maven) ，因为它们更容易计算。这个度量可以跨多个生态系统中计算，但是往往需要更多的信息，例如，跨生态系统的软件物料清单(SBOM)。

此信息可以只考虑直接依赖关系，或者还可以包括所有可传递的依赖关系。如果包含传递性依赖关系，则更有可能发现潜在的问题，但并非所有这类工具都支持这一点。

如果一个项目有多个稳定/受支持的分支，那么在任何分支中考虑“当前”是否可以接受？默认情况下，只考虑最新的稳定分支，因为随着时间的推移，通常较旧的分支得到的维护较少。另一种选择(虽然不是默认选择)是，如果旧版本获得积极支持，那么也可以接受旧版本为“当前”版本; 报告必须在使用该选择时明确注明。
是否应该有一个宽限期，新的依赖关系仍然被视为”当前”？默认情况下，答案是否定的; 任何特定的宽限期都是任意的，关键是要尽量保持与时俱进。

### 过滤条件
依赖级别(仅直接，包括传递依赖，等。定义在[上游代码依赖](https://github.com/chaoss/wg-risk/blob/master/focus-areas/Dependency-risk-assessment/Upstream-Code-Dependencies.md)度量指标里。
* 累积年龄
* 依赖的平均年龄
* 依赖年龄的中位数
* 依赖关系的排序列表(按依赖库年龄降序排列) ，因此首先识别“由于年龄而造成的风险最大的”依赖关系

### 可视化效果
这是依赖库年龄的一个示例，以直接依赖项的累积度量例，在本例中，累积值为103.78依赖库年龄。

![](./images/libyear.png)

这张图片来源于 https://github.com/nasirhjafri/libyear   


### 提供度量的工具
请注意，一些工具还可以计算版本号之间的差异(例如，1.1.1 vs. 1.2.3) ; 这样信息量更大，但并非所有依赖关系都使用相同的版本编号方法，因此为了简单起见，我们将重点放在度量时间上。

下面是一些实现依赖库年龄工具的例子: 
* https://github.com/nasirhjafri/libyear  - 利用requirements.txt度量Python。 
* https://github.com/sesh/piprot 
* https://github.com/chaoss/augur - deps_libyear_worker - 现在可以度量Python和Javascript。
* https://github.com/jaredbeck/libyear-bundler - 利用Gemfile度量Ruby。

## 参考资料

* [Cox 2015] “测量软件系统中的依赖新鲜度” by Joel Cox, Eric Bouwers, Marko van Eekelen, and Joost Visser, https://ericbouwers.github.io/papers/icse15.pdf  
* https://libyear.com/  


## 贡献者
* Sophia Vargas (Google)
* David A. Wheeler (Linux Foundation)
* Vinod Ahuja (University of Nebraska Omaha)
* Kate Stewart (Linux Foundation)
* Duane O’Brien
* Sean Goggins (University of Missouri / CHAOSS Project)
