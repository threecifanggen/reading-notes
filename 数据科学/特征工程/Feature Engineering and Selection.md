# Feature Engineering and Selection

## META

**创建日期**: 2021-02-14

**参考等级**: ⭐⭐⭐⭐⭐🌕

**关联**: 

**标签**: #特征工程; #数据科学; #数据分析; #机器学习

**引用**: Kuhn, Max, and Kjell Johnson. *Feature Engineering and Selection: A Practical Approach for Predictive Models*. CRC Press, 2019.

### 概述


## 结构

### 总体结构

```mermaid
graph TD

```

## 正文分析

### Introduction

一个常见的建模过程：

![image-20210214184649286](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214184649286.png)

### 一个预测缺血性中风的例子

#### 第一步：Splitting

将数据分成训练组和测试组。

| 数据组 | 发成卒中(n) | 味发生卒中(n) |
| :----: | :---------: | :-----------: |
| 训练组 |   51%(45)   |    49%(44)    |
| 测试组 |   51%(19)   |    49%(18)    |

#### 第二步：预处理

![image-20210214190716777](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214190716777.png)

![image-20210214190731135](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214190731135.png)

#### 第三步：搜寻

过程,比较两个模型，用下面的方法：

> 每次重抽样做如下事：
>
> * 使用90%的重抽样去拟合模型$M_1$和$M_2$
> * 用余下的10%数据预测模型
> * 计算$M_1$和$M_2$的ROC曲线
> * 计算两个AUC值得差距
>
> 使用单边t-test来比较是否$M_2$模型好于$M_1$模型

![image-20210214191531648](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214191531648.png)

![image-20210214191549891](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214191549891.png)

#### 第四步：组间预测模型

### 预测性模型过程的概观

#### 衡量表现

##### 回归的指标

* RMSE: root mean squared error。对极端值铭感
* R^2^: 这个标准往往具有迷惑性。对极端值铭感
* MAD: Median absolute deviation

##### 分类的指标

* 混淆矩阵(confusion matrix)
* 准确率
* Cohen’s Kappa
* 敏感性(sensitivity, true positive)
* 特异性(specificity, false positive)
* 精确率(precision)
* 召回率(recall)
* ROC和precision-recall curve

#### 数据分割

#### 重抽样

##### V-折CV和它的变体

##### 蒙特卡洛CV

标签: #蒙特卡洛CV

##### Bootstrap

##### 滑动原始预测

用在时间序列预测中

##### 验证集

##### 重抽样中的方差和偏差

![image-20210214193817465](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214193817465.png)

#### 优化参数和过拟合

### 预览可视化

标签: #数据可视化; #可视化

#### 可视化数值型数据

##### Box图、小提琴图和Histograms

![image-20210214194131492](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194131492.png)

![image-20210214194143131](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194143131.png)

![image-20210214194158411](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194158411.png)

##### 使用小平面(facet)、颜色和形状

![image-20210214194255369](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194255369.png)

##### 散点图

![image-20210214194311955](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194311955.png)

##### 热图

![image-20210214194331060](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194331060.png)

##### 相关性矩阵图

![image-20210214194404875](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194404875.png)

##### 折线图

![image-20210214194423909](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194423909.png)

##### 关键组件分析

![image-20210214194514458](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194514458.png)

![image-20210214194526777](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194526777.png)

#### 分类数据可视化

##### 可视化结果和预测因子之间的关系

![image-20210214194651390](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194651390.png)

##### 展示不同分类因子之间的关系

![image-20210214194747993](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214194747993.png)

#### 建模后的可视化

### 编码分类预测变量

#### 对无序的分类做伪变量(Dummy Variables)

![image-20210214195230960](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214195230960.png)

#### 编码多个分类的预测因子

#### 新分类的策略

#### 监督性的编码方法

![image-20210214195422660](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210214195422660.png)

#### 编码有顺序的数据

* 使用线性编码
* 使用二次多项式编码

#### 从文本中创建特征

### 处理数值预测变量

#### 一对一转换

##### BOX-COX转换

标签: #BoxCox; #幂转换
$$
x ^ {*} = \begin{cases} 
\frac {x^{\lambda} - 1} {\lambda \tilde{x}^{\lambda}}, && \lambda \ne 0 \\
\tilde{x}log\, x, && \lambda = 0
\end{cases}
$$
其中，$\tilde{x}$为预测数据的几何平均数。

几何平均数为：
$$
\tilde{x} = \sqrt[n]{x_1x_2...x_n}
$$
转换方法：

* $\lambda = 1$，无转换
* $\lambda = 0$，log转换
* $\lambda = 0.5$ ，平方根转换
* $\lambda = -1$，倒数转换

效果：

![image-20210224110243602](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210224110243602.png)

##### logit转换

标签: #logit转换; #arcsine转换
$$
logit(\pi) = log(\frac{\pi}{1 - \pi})
$$
与之相同的还可以使用**arcsine转换**

##### 集中化

* scaling

#### 一对多转换

##### 非线性特征/基本扩展和样条 

标签: #基本扩展; #Basis_Expansion; 

基本扩展是将预测变量转为一系列函数，譬如，使用三元函数来扩展

此外，多项式样条也是一个方法，基于几个节点来产生扩展。

##### 离散化预测变量

#### 多对多转换

##### 线性投射方法

* PCA
* Kernel PCA
* ICA(independent component analysis)
* NNMF(non-negative matrix factorization)
* PLS(partial least squares)

##### 自动编码

使用神经网络

##### 空间标志

标签: #空间标志; #Spatial_Sign
$$
x_{ij}^* = \frac {x_{ij}} {\sum^p_{j=1}x_{ij}^2}
$$

##### 距离和深度特征

标签: #数据深度; #待读

### 检测交互影响

#### 简介

交互的例子：

![image-20210225102455097](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210225102455097.png)

可以直接将交互项描述为两个的乘积：
$$
y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_1 x_2 + error
$$
情况：

* 如果$\beta_3$与0没有显著差异性，此时交互并没有表达好。这种情况下叫可加的(*additive*)。
* 如果$\beta_3$显著性小于0，则交互称为对抗的(*antagonistic*)
* 如果$\beta_3$显著性大于0，则交互成为增益的(*synergistic*)
* 有存在情况就是$\beta_1$和$\beta_2$都不显著与0有差异，但是$\beta_3$有，这个称为非典型的(*atypical*)

![image-20210225103551251](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210225103551251.png)

![image-20210225103606698](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210225103606698.png)

#### 搜寻交互的准则

![image-20210225104031332](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210225104031332.png)

三大准则：

* **阶层准则**(Hierarchy Principle): 越高层级的交互，越没有可能解释相应值
* **影响稀疏**(Effect Sparsity): 只有一小部分的交互会产生显著影响
* **遗传准则**(Heredity Principle): 

#### 实践上的考量

![image-20210225105948461](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210225105948461.png)

#### 识别预测性交互的强力策略(Brute-Force Approach)

##### 简单的策略

使用嵌套模型，譬如简单模型为：
$$
y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + error
$$
则嵌套模型为：
$$
y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_1 x_2 + error
$$
然后验证各个参数是否显著。

### 处理缺失值

#### 简介

缺失值的来源：

* 合并源数据集
* 随机事件
* 测量失败

#### 理解自然和严格的缺失信息

##### 可视化缺失信息



![image-20210225111620600](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210225111620600.png)

##### 总结缺失信息

![image-20210225111937193](https://typora-picgo-bed.oss-cn-beijing.aliyuncs.com/image-20210225111937193.png)

#### 使用的模型可以对抗缺失值

比如**CART模型**

#### 删除数据

#### 编码缺失



## 文摘

## 评论
