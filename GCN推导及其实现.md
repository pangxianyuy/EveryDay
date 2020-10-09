# GCN推导及其实现
## 为什么要研究Graph
* CNN开法处理非欧数据
* 而非欧数据又非常非常有用和常见
* 相比CNN,图有更强解释性这很重要
* 图有一个非常重要的特征：它是一种事物型结构


## 如何研究Graph
主要有两个流派：Vertex domain和spatial domain｡

前者基于空域卷积的方法，直接将卷积操作定义在每个结点的连接关系上，它跟传统的卷积神经网络中的卷积更相似一些。在这个类别中比较有代表性的方法有 Message Passing Neural Networks(MPNN)，GraphSage，Diffusion Convolution Neural Networks(DCNN)，PATCHY-SAN等。

后者则从图信只处理起家，借助图谱理论实现图上卷积。包括 Spectral CNN[5], Cheybyshev Spectral CNN(ChebNet)[6], 和 First order of ChebNet(1stChebNet)等
论文Semi-Supervised Classification with Graph Convolutional Networks就是一阶邻居的ChebNet（GCN）。


## 如何求解Graph
在信号处理中老师告诉我们有些问题时域很不好解决，转到频域就能轻松求解，时域和频域只是方法而不是本质。

基础：求导和拉谱拉斯算子。
概念：拉谱拉斯算子是二阶导数在高维空向的推导

推导：将梯底引入图数据（非欧数据）![](GCN%E6%8E%A8%E5%AF%BC%E5%8F%8A%E5%85%B6%E5%AE%9E%E7%8E%B0/bear_sketch@2x.png)

进一步的，做矩阵抽像有：
![](GCN%E6%8E%A8%E5%AF%BC%E5%8F%8A%E5%85%B6%E5%AE%9E%E7%8E%B0/bear_sketch@2x.png)


至此，作者用热力图完成G CN的近似推导，从物理学角度看，GCN本质也是一种热力传导／消息传递。
![](GCN%E6%8E%A8%E5%AF%BC%E5%8F%8A%E5%85%B6%E5%AE%9E%E7%8E%B0/bear_sketch@2x.png)


## 解题技巧：推广到频域
常规傅里叶变换本质：将任意函数表为若干个正交函数的线性组合。
![](GCN%E6%8E%A8%E5%AF%BC%E5%8F%8A%E5%85%B6%E5%AE%9E%E7%8E%B0/bear_sketch@2x.png)


因此，构造图券积的核心思路


















