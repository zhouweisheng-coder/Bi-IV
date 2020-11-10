[TOC]

# 第十一章 Graph Embedding

### Thinking1  什么是Graph Embedding，都有哪些算法模型      简要说明Graph  Embedding，以及相关算法模型  

* Graph  Embedding是图网络中的点用低维的向量表示，并且这些向量要能反应原有网络的特性，比如原网络中两个点的结构类似，那么这两个点表示的向量也应该类似
* Graph EMbedding常用算法模型有Deep Walk, Node2Vec等

### Thinking2  如何使用Graph  Embedding在推荐系统，比如NetFlix 电影推荐，请说明简要的思路  简要说明Graph  Embedding在NetFlix电影推荐中的作用，有自己的见解      

* 根据用户行为，构建以电影item为node的图，然后通过random walk或者node2vec等算法生成生成电影item的表示向量。
* 如图1所示。图1(a)表示3个用户看过的电影，并按照时间顺序做了排列，比如用户U1先后购买了D A B三个电影。这里有一个业务上的技巧，就是把用户在某个时间窗内的连续行为作为一个session，例如一个小时，如果超过时间窗，就划分为不同的session。通常在短周期内访问的电影更具有相似性。根据购买顺序构建有向图，如图1(b)所示， ![[公式]](https://www.zhihu.com/equation?tex=edge_%7Bij%7D) 记录了从电影i到电影j的出现次数。计算电影的转移概率，并根据转移概率做游走，生成商品序列，如图1(c)所示。其中转移概率如公式(1)所示， ![[公式]](https://www.zhihu.com/equation?tex=M_%7Bij%7D) 表示从商品i到商品j的出现次数， ![[公式]](https://www.zhihu.com/equation?tex=N_%7B%2B%7D%28v_i%29) 表示的 ![[公式]](https://www.zhihu.com/equation?tex=v_i) 直接邻域。最后根据skip-gram训练商品的向量表示，如图1(d)所示。![](https://cdn.jsdelivr.net/gh/zhouyusheng-coder/photocloud//image/%E5%9B%BE%E7%89%871.jpg)

### Thinking3  数据探索EDA都有哪些常用的方法和工具      简要说明常用的EDA方法和工具

##### EDA方法流程：

1、形成假设，确定主题去探索

2、清理数据

3、评价数据质量

4、数据报表

5、探索分析每个变量

6、探索每个自变量与因变量之间的关系

7、探索每个自变量之间的相关性

8、从不同的维度来分析数据

##### 工具：

* missingno：可视化的展示数据缺失的分布情况，能够查看缺失值的分布情况，缺失数据有哪些原因，哪些地方有丢失
* pivottablejs：能够形成一个透视表，将每个变量形成统计
* Pandas_profiling：生成分析报表
* matplotlib、seaborn绘图工具

##### 常用EDA方法：

* dataframe中value_counts()统计字段不同值的个数

* 判断列的缺失值

  * df.isnull().any() #判断哪些列存在缺失值

  * df.isnull().sum() #判断列的缺失值总数

后续优化：

•使用时间字段

•特征工程

超参数优化



| 分类           | 内容                                                         | 数据集                                                       | 是否了解掌握 | 评阅点                                                       | GitHub代码 |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------ | ------------------------------------------------------------ | ---------- |
| 课上理解部分   |                                                              |                                                              |              |                                                              |            |
| 原理           | Graph Embedding的使用场景                                    |                                                              |              |                                                              |            |
| 工具           | word2vec工具使用                                             |                                                              |              |                                                              |            |
| 原理           | Graph Embedding的主要方法                                    |                                                              |              |                                                              |            |
| 原理           | DeepWalk = Random Walk + Skip-gram                           |                                                              |              |                                                              |            |
| 工具           | 使用DeepWalk对Project A：美国大学生足球队进行Embedding       |                                                              |              |                                                              |            |
| 工具           | NetWorks工具使用                                             |                                                              |              |                                                              |            |
| 原理           | Node2Vec算法原理                                             |                                                              |              |                                                              |            |
| 原理           | BFS（宽度优先）与DFS（深度优先）                             |                                                              |              |                                                              |            |
| 原理           | 返回概率p 与 出入参数q                                       |                                                              |              |                                                              |            |
| 工具           | Node2Vec工具使用                                             |                                                              |              |                                                              |            |
| 工具           | 使用Node2Vec对Project A：美国大学生足球队进行Embedding       |                                                              |              |                                                              |            |
| 工具           | Graph Embedding工具                                          |                                                              |              |                                                              |            |
| 工具           | 使用Graph  Embedding工具对Project A：美国大学生足球队进行Embedding |                                                              |              |                                                              |            |
| 工具           | 缺失值可视化工具missingno                                    |                                                              |              |                                                              |            |
| 工具           | pandas_profiling 一行代码生成报告                            |                                                              |              |                                                              |            |
| 课下思考与练习 |                                                              |                                                              |              |                                                              |            |
| Thinking1      | 什么是Graph Embedding，都有哪些算法模型                      |                                                              |              | 简要说名Graph  Embedding，以及相关算法模型（10points）       |            |
| Thinking2      | 如何使用Graph  Embedding在推荐系统，比如NetFlix 电影推荐，请说明简要的思路 | 简要说明Graph  Embedding在NetFlix电影推荐中的作用，有自己的见解（10points） |              |                                                              |            |
| Thinking3      | 数据探索EDA都有哪些常用的方法和工具                          |                                                              |              | 简要说明常用的EDA方法和工具（10points）                      |            |
| Action1        | seealsology是个针对Wikipidea页面的语义分析工具，可以找到与指定页面相关的Wikipidea     seealsology-data.tsv 文件存储了Wikipidea页面的关系（Source, Target, Depth）     使用Graph Embedding对节点（Wikipidea）进行Embedding（DeepWalk或Node2Vec模型）     对Embedding进行可视化（使用PCA呈现在二维平面上）     找到和critical illness insurance相关的页面 |                                                              |              | 1、完成代码（20points）     2、结果正确（20points）          |            |
| Action2        | 二手车价格预测     数据集：     used_car_train_20200313.csv     used_car_testA_20200313.csv     数据来自某交易平台的二手车交易记录     ToDo：给你一辆车的各个属性（除了price字段），预测它的价格 |                                                              |              | 1、数据探索EDA（20points）     2、使用缺失值可视化工具或pandas_profiling工具（10points） |            |