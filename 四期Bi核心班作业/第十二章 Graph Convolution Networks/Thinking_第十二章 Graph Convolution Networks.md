[TOC]



# 第十二章 Graph Convolution Networks

### Thinking1  GCN/Graph Embedding 都有哪些应用场景      

简要说出Graph  Embedding的使用场景型（10points）  

* 网络分析、推荐系统、 生物化学、 交通预测、 计算机视觉、 自然语言处理等

### Thinking2  在交通流量预测中，如何使用Graph  Embedding，请说明简要的思路    

简要说明Graph  Embedding在交通流量预测的作用，有自己的见解（20points）      

* 每一个地点或者路口为顶点，上一时刻的流量为边构建有权图
* 可采用node2vec算法，通过边权重计算转移概率从而游走生成多个序列
* 再设置合适的窗口大小，skip-gram训练每个序列为矩阵向量

### Thinking3  在文本分类中，如何使用Graph  Embedding，请说明简要的思路      

简要说明Graph  Embedding在文本分类中的作用，有自己的见解（20points）

* 分词处理，然后通过词频构建图
* 通过随机游走算法产生大量序列

- 将产生的序列放入skip-gram算法中，设定合适的窗口生成词的表示矩阵。

- 节点序列=句子，序列中的节点=句子中的单词

  

| 分类           | 内容                                                         | 数据集 | 是否了解掌握                                                 | 评阅点                                                       | GitHub代码 |
| -------------- | ------------------------------------------------------------ | ------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------- |
| 课上理解部分   |                                                              |        |                                                              |                                                              |            |
| 原理           | Graph Embedding的使用场景                                    |        |                                                              |                                                              |            |
| 工具           | Graph Embedding工具                                          |        |                                                              |                                                              |            |
| 原理           | GCN原理                                                      |        |                                                              |                                                              |            |
| 原理           | 常用的3种拉普拉斯矩阵                                        |        |                                                              |                                                              |            |
| 工具           | 使用GCN对Project A：美国大学生足球队进行Embedding            |        |                                                              |                                                              |            |
| 工具           | Project：二手车价格预测                                      |        |                                                              |                                                              |            |
| 工具           | Project：网络影响力分析                                      |        |                                                              |                                                              |            |
| 课下思考与练习 |                                                              |        |                                                              |                                                              |            |
| Thinking1      | GCN/Graph Embedding 都有哪些应用场景                         |        |                                                              | 简要说出Graph  Embedding的使用场景型（10points）             |            |
| Thinking2      | 在交通流量预测中，如何使用Graph  Embedding，请说明简要的思路 |        | 简要说明Graph  Embedding在交通流量预测的作用，有自己的见解（20points） |                                                              |            |
| Thinking3      | 在文本分类中，如何使用Graph  Embedding，请说明简要的思路     |        |                                                              | 简要说明Graph  Embedding在文本分类中的作用，有自己的见解（20points） |            |
| Action1        | Dolphin数据集是 D.Lusseau 等人使用长达 7  年的时间观察新西兰 Doubtful Sound海峡 62 只海豚群体的交流情况而得到的海豚社会关系网络。这个网络具有 62 个节点，159  条边。节点表示海豚，边表示海豚间的频繁接触     数据文件：dolphins.gml     1）对Dolphin 关系进行Graph Embedding，使用GCN     2）对Embedding进行可视化（使用PCA呈现在二维平面上） |        |                                                              | 1、完成代码（20points）     2、结果正确（10points）          |            |
| Action2        | 二手车价格预测     数据集：     used_car_train_20200313.csv     used_car_testA_20200313.csv     数据来自某交易平台的二手车交易记录     ToDo：给你一辆车的各个属性（除了price字段），预测它的价格 |        |                                                              | 1、完成代码（20points）     2、结果正确（20points）          |            |