[TOC]

# 第三章 智能供应链(二)

### Thinking1  常见的规划问题都包括哪些？      能简要说明常见的规划问题

* LP：Linear Programming 线性规划

  ​	研究线性约束条件下线性目标函数的极值问题

* ILP：Integer Linear Programming 整数线性规划

  ​	全部决策变量必须为整数

* MIP：Mixed Integer Programming 混合整数规划

  ​	混合整数规划是LP的一种，其中部分的决策变量是整数（不要求全部都是整数）

VRP：Vehicle Routing Problem 车辆路径问题

### Thinking2  常用的规划工具包都有哪些？      能简要说明常用的规划工具

* pulp

  ​	只用于线性模型，包括如整数规划、01规划，还是混合整数线性规划 MILP

* ortools

  ​	Google开发，用于优化的开源软件，可以解决车辆路径、流程、整数和线性规划等问题，提供了C++,Python,Java,.NET接口

###  Thinking3  RFM模型的原理是怎样的      能简要说明RFM模型的原理  

RFM是由三个英文单词的首字母组成的，即Recency（最近一次消费时间间隔）、Frequency（一段时间内的消费频率）和Monetary（一段时间内的消费金额）（RFM分析模型介绍）

（1） **重要价值用户**，RFM三个值都很高，需要**提供VIP服务**
（2） **重要发展用户**，消费频率低，但是其他两个值比较高，那么需要想办法**提高他的消费频率**
（3） **重要保持用户**，最近消费距离现在时间比较远（F值低），但是消费频次和消费金额高。这种用户一般是一段时间没来的忠实用户，我们需要主动与他保持联系，**提高复购率**。
（4） **重要挽留用户**，最近消费时间距离现在比较远，消费的频率也比较低，但是消费的金额比较多。这种用户，即将流失，需要主动联系，调查清楚哪里出现了问题，想办法挽留。

![](https://github.com/zhouyusheng-coder/photocloud/blob/main/image/20200627153356791.jpg)







| 分类           | 内容                                                         | 数据集 | 是否了解掌握 | 评阅点                                                       | GitHub代码 |
| -------------- | ------------------------------------------------------------ | ------ | ------------ | ------------------------------------------------------------ | ---------- |
| 工具           | 智能供应链                                                   |        |              |                                                              |            |
| 工具           | 对欺诈行为（fraud）进行预测                                  |        |              |                                                              |            |
| 工具           | 对销售业绩（Sales）进行预测                                  |        |              |                                                              |            |
| 工具           | 掌握多种分类器的使用：LR，GaussianNB，LinearSVC，KNeighborsClassifier，LinearDiscriminantAnalysis，DecisionTreeClassifier，RandomForestClassifier，XGBClassifier |        |              |                                                              |            |
| 工具           | 掌握多种回归器的使用：LinearRegression,  Lasso, Ridge, DecisionTreeRegressor, XGBRegressor, LGBMRegressor,  RandomForestRegressor |        |              |                                                              |            |
| 原理           | 线性规划                                                     |        |              |                                                              |            |
| 原理           | 整数规划                                                     |        |              |                                                              |            |
| 原理           | 混合整数规划                                                 |        |              |                                                              |            |
| 工具           | pulp工具                                                     |        |              |                                                              |            |
| 工具           | Google ortools                                               |        |              |                                                              |            |
| 课下思考与练习 |                                                              |        |              |                                                              |            |
| Thinking1      | 常见的规划问题都包括哪些？                                   |        |              | 能简要说明常见的规划问题（10points）                         |            |
| Thinking2      | 常用的规划工具包都有哪些？                                   |        |              | 能简要说明常用的规划工具（10points）                         |            |
| Thinking3      | RFM模型的原理是怎样的                                        |        |              | 能简要说明RFM模型的原理（10points）                          |            |
| Action1        | 智能供应链分析     数据集：SupplyChainDataset.csv，供应链采购数据     To Do：     对于欺诈订单进行预测，即Order Status='SUSPECTED_FRAUD'     对于迟交货订单进行预测，即Delivery Status= 'Late delivery'     对于销售额进行预测，即Sales字段     对于订货数量进行预测，即Order Item Quantity |        |              | 1、对欺诈订单进行预测（10points）     2、对迟交货订单进行预测（10points）     3、对销售额进行预测（10points）     4、对订货数量进行预测（10points）     5、对模型进行可解释性分析（10points） |            |
| Action2        | 一个农民承包了6块耕地共300亩，准备播种小麦，玉米，水果和蔬菜四种农产品，已知各种农产品的计划播种面积、每块土地种植不同农产品的单产收益     如何进行合理安排，使得总收益最大     可以使用pulp/ortools工具 |        |              | 1、能使用pulp或ortools工具（10points）     2、结果正确（10points） |            |