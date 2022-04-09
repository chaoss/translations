# 测试覆盖率

问题：代码的测试情况如何？

## 描述
测试覆盖率描述了至少一个测试套覆盖了多少给定的代码仓。测试覆盖率有两个主要的衡量标准。一个是针对代码仓运行的测试套中涵盖的**子例程**的百分比。测试覆盖率的另一个主要含义是测试套执行期间覆盖的**语句**的百分比。 “测试覆盖率”在CHAOSS中的度量定义包括这两个单独的度量指标。

编程语言将**子例程** 特指为“函数”、“方法”、“例程”，或在某些情况下称为“子程序”。在此定义中，特定代码仓的覆盖率仅限于特定代码仓中定义的方法，并且不包括代码仓所依赖的库或其他软件的覆盖率。

## 目标

了解测试覆盖水平是代表软件质量的一个信号。测试覆盖率低的代码表明软件工程实践可能不太严格，并且相应地增加了在部署和使用时检测到缺陷的可能性。

## 实现

__健康指标的使用和传播可能导致隐私侵犯。组织可能会面临风险。这些风险可能来自于遵守欧盟的 GDPR、美国的州法律或其它法律。此外，GitHub 和 GitLab 等数据提供商的服务条款也可能带来合同风险。请务必检查度量指标的使用是否存在风险和潜在的数据伦理问题。请参阅[CHAOSS 数据伦理文件](https://github.com/chaoss/metrics/tree/main/resources)以获得更多指导。__


语句包括变量赋值、循环声明、对系统函数的调用、“go to”语句以及函数或方法完成时常见的 `return` 语句，其中可能包括也可能不包括返回 `value` 或 `value数组`。

#### 子例程覆盖率

![Subroutine Coverage](images/test-coverage_subroutine-coverage.png)

#### 语句覆盖率

![Statement Coverage](images/test-coverage_statement-coverage.png)

### 筛选条件
* 时间：按时间变化过滤测试覆盖率，可以帮助项目关注最大化整体测试覆盖率。具体参数包括时间段的“开始日期”和“结束日期”。
* 代码文件: 每个代码仓都包含许多代码文件。按特定文件过滤覆盖率提供了更精细的测试覆盖率视图。某些函数或语句可能会导致比其他函数或语句更严重的软件故障。例如，安全关键系统的“故障安全”功能中未经测试的代码比“字体颜色”功能测试更重要。
* 编程语言：大多数当代开源软件代码仓都包含几种不同的编程语言。每个`Code_File`的覆盖率都可以按照编程语言进行过滤。

### 提供指标的工具
- 提供测试覆盖率信息 
  * [Python 的主要测试框架PyTest](https://docs.pytest.org/en/latest/)
  * [用于 Python 的 Flask Web 框架支持覆盖测试](http://flask.pocoo.org/docs/1.0/tutorial/tests/)
  * [可以从我的网站获取用于 Java、C 和 C++ 等常用语言的开源代码覆盖工具，包括这个。](https://stackify.com/code-coverage-tools/#OpenSource)

- 存储测试覆盖率信息 
  * [Augur](https://github.com/chaoss/augur) 将测试覆盖率展现为一个表格，该表是其代码仓中主代码仓表格的子项。每次计算测试覆盖率时，都会对每个测试的文件、测试使用的测试工具和文件中的语句/子程序的数量以及测试的语句和子程序的数量进行记录。通过在此粒度记录测试数据，Augur 启用了“代码文件”和“编程语言”汇总级别的统计信息和过滤器。


## 参考资料
1. J.H. Andrews, L.C. Briand, Y. Labiche, and A.S. Namin. 2006. Using Mutation Analysis for Assessing and Comparing Testing Coverage Criteria. IEEE Transactions on Software Engineering 32, 8: 608–624. https://doi.org/10.1109/TSE.2006.83
2. Phyllis G Frankl and Oleg Iakounenko. 1998. Further Empirical Studies of Test Effectiveness. In Proceedings of the 6thACM SIGSOFT International Symposium on Foundations of Software Engineering, 153–162.
3. Phyllis G Frankl and Stewart N Weiss. 1993. An Experimental Comparison of the Effectiveness of Branch Testing and Data Flow Testing. EEE Transactions on SoftwareEngineering 19, 8: 774–787.
4. Laura Inozemtseva and Reid Holmes. 2014. Coverage is not strongly correlated with test suite effectiveness. In Proceedings of the 36th International Conference on Software Engineering - ICSE 2014, 435–445. https://doi.org/10.1145/2568225.2568271
5. Akbar Siami Namin and James H. Andrews. 2009. The influence of size and coverage on test suite effectiveness. In Proceedings of the eighteenth international symposium on Software testing and analysis - ISSTA ’09, 57. https://doi.org/10.1145/1572272.1572280
