# Rubin Causal Model (RCM) 和随机化试验

# META

**创建日期**: 2021-03-23

**参考等级**: ⭐⭐

**关联**: 

**标签**: #2021-03-01; #RCM; #因果推理

**引用**: 丁鹏, "Rubin Causal Model (Rcm) 和随机化试验," 因果推断简介, 2012, https://cosx.org/2012/03/causality2-rcm/.

## 概述

# 正文分析

## 术语介绍

标签; #ACE

* $Z_i$：是否处理
* $Y_i$: 结果变量。$\{Y_i(1),Y_i(0)\}$表示个体$i$接收处理或对照的潜在结果(potential outcome)
* $Y_i(1) - Y_i(0)$。表示个体$i$的因果作用。但是因为只能选择其一，所以观测的结果是$Y_i = Z_iY_i(1) - (1-Z_i)Y_i(0)$

以此，ACE(平均因果作用, Average Causal Effect)为，
$$
ACE(Z \rightarrow Y) = E\{Y_i(1) - Y_i(0)\}
$$
所以可得:
$$
\begin{align}
ACE(Z \rightarrow Y) & = E\{Y_i(1)\} -  E\{Y_i(0)\}\\
					 & = E\{Y_i(1)|Z_i = 1\} -  E\{Y_i(0)| Z_i=0\}\\
					 & = E\{Y_i | Z_i = 1\} - E \{Y_i| Z_i = 0\}
\end{align}
$$
这里需要满足两个条件

* 期望算子是线性的，才能满足等式的条件，即$E(X - Y) = E(X) - E(Y)$
* 需要随机化，即满足$Z \bot \{Y(1), Y(0)\}$

## 一些衡量参数

### 风险差

标签: #风险差

风险差(risk difference; RD)的定义：
$$
\begin{align}
CRD(Z \rightarrow Y) & = P(Y(1) = 1) - P(Y(0) = 0) \\
					 & = P(Y = 1 | Z = 1) - P(Y = 1 | Z = 0)
\end{align}
$$

### 风险比

标签: #风险比

风险比(risk ratio; RR):
$$
\begin{align}
CRR(Z \rightarrow Y) & = \frac{P(Y(1) = 1)}{P(Y(0) = 1)} \\
					 & = \frac{P(Y = 1 | Z = 1)}{P(Y = 1 | Z = 0)}
\end{align}
$$

### 优势比

标签: #优势比

优势比(odds ratio; OR):
$$
\begin{align}
COR(Z \rightarrow Y) & = \frac{P(Y(1) = 1)P(Y(0)= 0)}{P(Y(0) = 1)P(Y(1) = 0)} \\
					 & = \frac{P(Y = 1 | Z = 1)P(Y = 0 | Z = 0)}{P(Y = 1 | Z = 0) P(Y = 0 | Z = 1)}
\end{align}
$$

## 区别

* CRR和COR与ACE的出发点不同，ACE是个体期望，而C**是总体定义

# 文摘

# 评论
