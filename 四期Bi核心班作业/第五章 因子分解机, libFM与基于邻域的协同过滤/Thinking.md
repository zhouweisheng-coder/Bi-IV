### Thinking1 在实际工作中，FM和MF哪个应用的更多，为什么1、能简要说明FM和MF的区别（5point）     2、能简要说明FM在推荐系统，以及应用场景中的作用（5point）  

##### 实际工作中FM应用更多些，因为MF方法只是适用于评分预估的类似场景中，在ctr预估等场景中较难逼近实际目标，并且MF适用隐向量表示用户和物品的特征，最终只能推荐训练样本中存在的用户和样本，冷启动问题较为严重。

1. FM是MF引入二阶特征的特例，MF可以被认为是只有User ID 和Item ID这两个特征信息时的FM模型。
   * FM矩阵将User和Item都进行了one-hot编码作为特征，使得特征维度非常巨大且稀疏
   * 矩阵分解MF是FM的特例，即特征只有User ID 和Item ID的FM模型
   * 矩阵分解MF只适用于评分预测，进行简单的特征计算，无法利用其他特征
   * FM引入了更多辅助信息（Side information）作为特征
   * FM在计算二阶特征组合系数的时候，使用了MF
2. FM的核心思想，使得稀疏数据下学习不充分的问题也能得到充分解决，可提供的非零样本大大增加

### Thinking2 FFM与FM有哪些区别？1、能简要说明区别（10point）

* FM每个特征只有一个隐向量，FM是FFM的特例

* FFM每个特征有多个隐向量，使用哪个，取决于和哪个向量进行点乘
* FM旨在解决大规模稀疏数据的特征组合问题而FFM是把相同性质的特征归为一个field.

### Thinking3 DeepFM相比于FM解决了哪些问题，原理是怎样的1、能说明DeepFM相比于FM有哪些改进的地方（5points）     2、能说明DeepFM的原理，FM+DNN模型（5points）

1. FM一般情况下只是提取一阶和二阶特征，本身算法是可以提取高阶特征的，但是计算复杂度太高。引入DNN可以更加高效的提取二阶以上的特征。
2. FM提取低阶(low order)特征，既可以做1阶特征建模，也可以做2阶特征建模；神经网络DNN提取高阶(high order)特征

### Thinking4 Surprise工具中的baseline算法原理是怎样的？BaselineOnly和KNNBaseline有什么区别？1、能简要说明baseline的原理（5points)     2、能简要说明BaselineOnly和KNNBaseline的区别（5points)

1. baseline算法通过加入用户和商品对整体的偏差来优化预测评分，可以使用ALS，SGD等优化方法优化baseline参数。
2. BaselineOnly是基于统计的基准预测线打分，KNNBaseline是协同过滤算法的变种，考虑每个用户评分的基线。

### Thinking5基于邻域的协同过滤都有哪些算法，请简述原理1、能说出两种不同的基于邻域的协同过滤的算法（5points）     2、这些算法之间的区别和作用（5pionts）

1. 基于邻域的协同过滤有KNNBasic、KNNWithMeans、KNNWithZScore、KNNBaseline等
2. KNNBasic是引用KNN计算用户兴趣相似度的基本的协同过滤算法，KNNWithMeans引入用户的平均兴趣，KNNWithZScore引入用户平均兴趣及标准差，考虑到用户打分的偏差考虑到用户打分的偏差



---

---

---











### Action1使用libfm工具对movielens进行评分预测，采用SGD优化算法1、运行出结果，结果正确（10points）

### Action2使用DeepFM对movielens进行评分预测1、使用DeepFM工具进行评分预测，代码正确，可以跑通简单的movielens_sample数据集（10points）     2、可以跑通完整的movielens数据集（10points）

###  Action3使用基于邻域的协同过滤（KNNBasic,  KNNWithMeans, KNNWithZScore,  KNNBaseline中的任意一种）对MovieLens数据集进行协同过滤，采用k折交叉验证(k=3)，输出每次计算的RMSE, MAE1、完成代码（10points）     2、得出K折，每次的RMSE，MAE结果（10points）

| 分类           | 内容                                                         | 数据集                  | 是否了解掌握                                                 | 评阅点                                                       | GitHub代码 |
| -------------- | ------------------------------------------------------------ | ----------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------- |
| 课上理解部分   |                                                              |                         |                                                              |                                                              |            |
| 原理           | FM算法的原理                                                 |                         |                                                              |                                                              |            |
| 原理           | FM算法的计算复杂度                                           |                         |                                                              |                                                              |            |
| 原理           | FFM算法的原理                                                |                         |                                                              |                                                              |            |
| 原理           | DeepFM算法的原理                                             |                         |                                                              |                                                              |            |
| 工具           | libfm                                                        | movielens               |                                                              |                                                              |            |
| 工具           | libffm                                                       |                         |                                                              |                                                              |            |
| 工具           | xlearn                                                       | criteo_ctr数据集(small) |                                                              |                                                              |            |
| 工具           | deepctr                                                      | MovieLens_Sample        |                                                              |                                                              |            |
| 原理           | 基于邻域的协同过滤 UserCF，ItemCF                            |                         |                                                              |                                                              |            |
| 原理           | 相似邻居的定义                                               |                         |                                                              |                                                              |            |
| 原理           | 相似度计算的方式                                             |                         |                                                              |                                                              |            |
| 工具           | Surprise工具中的基于邻域的协同过滤算法使用                   |                         |                                                              |                                                              |            |
| 课下思考与练习 |                                                              |                         |                                                              |                                                              |            |
| Thinking1      | 在实际工作中，FM和MF哪个应用的更多，为什么                   |                         |                                                              | 1、能简要说明FM和MF的区别（5point）     2、能简要说明FM在推荐系统，以及应用场景中的作用（5point） |            |
| Thinking2      | FFM与FM有哪些区别？                                          |                         |                                                              | 1、能简要说明区别（10point）                                 |            |
| Thinking3      | DeepFM相比于FM解决了哪些问题，原理是怎样的                   |                         |                                                              | 1、能说明DeepFM相比于FM有哪些改进的地方（5points）     2、能说明DeepFM的原理，FM+DNN模型（5points） |            |
| Thinking4      | Surprise工具中的baseline算法原理是怎样的？BaselineOnly和KNNBaseline有什么区别？ |                         | 1、能简要说明baseline的原理（5points)     2、能简要说明BaselineOnly和KNNBaseline的区别（5points) |                                                              |            |
| Thinking5      | 基于邻域的协同过滤都有哪些算法，请简述原理                   |                         |                                                              | 1、能说出两种不同的基于邻域的协同过滤的算法（5points）     2、这些算法之间的区别和作用（5pionts） |            |
| Action1        | 使用libfm工具对movielens进行评分预测，采用SGD优化算法        |                         |                                                              | 1、运行出结果，结果正确（10points）                          |            |
| Action2        | 使用DeepFM对movielens进行评分预测                            |                         |                                                              | 1、使用DeepFM工具进行评分预测，代码正确，可以跑通简单的movielens_sample数据集（10points）     2、可以跑通完整的movielens数据集（10points） |            |
| Action3        | 使用基于邻域的协同过滤（KNNBasic,  KNNWithMeans, KNNWithZScore,  KNNBaseline中的任意一种）对MovieLens数据集进行协同过滤，采用k折交叉验证(k=3)，输出每次计算的RMSE, MAE |                         |                                                              | 1、完成代码（10points）     2、得出K折，每次的RMSE，MAE结果（10points） |            |