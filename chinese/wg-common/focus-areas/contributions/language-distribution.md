# 编程语言分布

问题: 开源项目中有哪些不同的编程语言，每种编程语言所占的百分比是多少？

## 描述

项目中所使用编程语言的数量和每种语言所占的百分比可以使人们对代码贡献者所需要的技能以及项目本身的性质有所了解。

## Objectives
这个度量标准将帮助特定开源项目的新手，同时也为开源项目经理结合他们自己的经验和组织，提供了一个关于项目概况的视角。

在关注价值度量的领域中: 作为求职的一部分，开发人员可以使用这个指标来识别那些深度依赖于他们所使用的编程语言的项目。

在关注演进度量的领域中: 这个指标可以用于标识随着时间的推移每种语言中文件或代码行数量的变化。例如，一个项目在某个时间点可能是 x% Python 和 y% Javascript。也许一年后，由于项目的重点转向了用户体验，用文件数或代码行数来衡量的 Javascript 使用量可能会更多。

在关注风险度量的领域中: 这个度量可以与上游依赖度量相结合，以确定是否在项目中使用了某个重要的语言，但尚未被依赖扫描工具确认。

在关注多样，平等与包容度量的领域中: 当包容性的、多样化的和公平的社区被确定后，它们将有一定程度的编程语言分布。

当一个人寻找新的项目时，知道哪些项目依赖于他们已经知道的或者想要学习的编程语言，可以是一系列“个人过滤器”中的一个。

一般来说，这个度量对开源办项目公室是有用的，社区管理人员的目标是了解哪种语言最突出，哪种语言很少被使用，但是很重要。

## 实现
Language distribution takes into account different properties of each file in a repository with an a priori identifiable computer programming language. As new languages emerge, there may be initial periods where counting tools do not recognize their extensions, in which case they may be counted as “other”. Such periods are typically brief.  
编程语言分布使用一种先验的可识别计算机编程语言来考虑代码仓中每个文件的不同属性。当新语言的出现，可能会出现计数工具无法识别其文件后缀的初始阶段，在这种情况下，它们可能被视为“其他”语言。这样的时期通常是短暂的。

### 过滤条件
 - 时间
 - 文件数 - 每种语言的文件数。

	| **编程语言** | **文件数** |
	| ------------ | ----------- |
	| Python | 246 |
	| JSON | 28 |
	| BASH | 26 |
	| Plain Text | 14 |
	| Shell | 12 |
	| gitignore | 8 |
	| YAML | 6 |
	| Makefile | 4 |
	| R | 2 |
	| Docker ignore | 2 |
	| Dockerfile | 2 |
	| Markdown | 2 |

 - 代码行数 - 每种语言代码行数的百分比.

	| **编程语言** | **每种语言代码行数的百分比** |
	| ------------ | ----------- |
	| Python | 94.60% |
	| BASH | 2.48% |
	| Shell | 1.08% |
	| JSON | 0.52% |
	| R | 0.42% |
	| Plain Text | 0.38% |
	| Makefile | 0.16% |
	| YAML | 0.15% |
	| gitignore | 0.12% |
	| Dockerfile | 0.05% |
	| Docker ignore | 0.03% |
	| Markdown | 0.00% |

代码行数或文件数都可以表示为绝对数或百分比，具体取决于度量所使用的应用程序。在许多情况下，简单的文件计数是有用的，而代码的绝对行数可能很难区分，因为量级要大得多。


### 提供度量的工具

[Augur-Community-Reports](https://github.com/chaoss/augur-community-reports) 代码仓目前提供这个指标。
[GrimoireLab](https://github.com/chaoss/grimoirelab) 通过识别文件后缀名来提供这个指标。 
[Augur](https://github.com/chaoss/augur) 在前端提供，同时也通过API endpoint提供.

### 数据收集策略
代码仓的内容可以通过迭代每个文件来计算，这种方案有几个库支持实现: https://github.com/boyter/scc

一些编程语言的文件扩展名，比如 Jupyter Notebooks，可能会被排除在外，因为它们掩盖了实际使用的编程语言。

## 参考资料
 - https://github.com/boyter/scc  

## 贡献者

 - Dawn Foster
 - Beth Hancock
 - Matt Germonprez
 - Elizabeth Barron
 - Daniel Izquierdo
 - Kevin Lumbard
 - Sean Goggins
