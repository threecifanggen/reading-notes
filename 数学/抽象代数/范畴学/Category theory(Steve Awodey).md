# Category Theory(Steve Awodey)

# META

**创建日期**: 2021-03-09

**参考等级**: ⭐⭐⭐⭐⭐

**关联**: 

**标签**: #范畴学; #函数式编程; #抽象代数

**引用**: Awodey, Steve. *Category Theory*. Oxford Logic Guides. Edited by A.J. Macintyre, D.S. Scott. Vol. 52, New York: Oxford university press, 2010.

## 概述


# 结构

## 总体结构

```mermaid
graph TD

```

# 正文分析

## 1 Categories

### 1.1 Introduction

范畴学是什么：

* 研究函数的（抽象）代数

### 1.2 集合的函数

定义$f$为从$A$集合到另一个$B$集合的函数，写作：
$$
f: A \rightarrow B
$$


其中，
$$
range(f) \subseteq B
$$
我们再定义
$$
g: B \rightarrow C
$$
则
$$
g \circ f : A \rightarrow C
$$
切满足
$$
\begin{align}
(g\circ f)(a) = g(f(a)) && a \in A
\end{align}
$$

$$
\begin{array}{cccc}
A & \xrightarrow{f} & B\\
&{g \circ f}\searrow & \downarrow{g} \\
& & C
\end{array}
$$

定义indentity函数为
$$
1_A : A \rightarrow A
$$
其中
$$
1_A(a) = a
$$

### 1.3 范畴的定义

标签: #范畴

> 定义1.1：
>
> 一个**范畴**（*Category*）包括下面的元素：
>
> * 对象(*Objects*)：$A, B, C, ....$
>
> * 箭头(*Arrows*): $f, g, h, ...$
>
> * 对于每个箭头$f$，对可以给出以下的对象
>   $$
>   \begin{align}
>   dom(f), && cod(f)
>   \end{align}
>   $$
>   叫做**范围**(*domain*)和**共范围**(*codomain*)。写作
>   $$
>   f: A -> B
>   $$
>   其中$A = dom(f)$，$B = cod(f)$
>
> * 给定$f: A \rightarrow B$和$g: B \rightarrow C$，可以得到
>   $$
>   cod(f) = dom(g)
>   $$
>   并且可以得到存在一个箭头满足
>   $$
>   g \circ f : A \rightarrow C
>   $$
>   也叫做函数$f$和$g$的**复合**(*composite*)
>
> * 对于任何一个对象$A$，存在一个箭头
>   $$
>   1_A = A \rightarrow A
>   $$
>
> * 结合律(Associativity)：
>   $$
>   h \circ (g \circ f) = (h \circ g) \circ f
>   $$
>
> * 单位元(Unit)：
>   $$
>   f \circ 1_A = f = 1_b \circ f
>   $$
>   对于所有$f: A \rightarrow B$

### 1.4 一些范畴的例子

#### 1. 集合和函数的集合

#### 2. 结构集合的范畴

* 群和群同构
* 向量空间和线性变换
* 图和图同构
* 实数和连续函数
* ...

#### 3. 偏序集(partially ordered set)

二元关系$a\le_A b$满足下面的条件($a, b, c \in A$)

* 反身性(reflexivity)：$a\le_A a$
* 传递性(transitivity)：$a\le_A b, b \le_B c \Rightarrow a \le_A c$
* 反对称(antisymmetry): $a\le_A b, b \le_A a \Rightarrow a = b$

#### 4. REL

#### 5. 有限范畴

##### 范畴1

仅含有$*$和指向自己的identity箭头

##### 范畴2

仅含有$*$、$@$和$* \rightarrow @$以及各自的identity箭头

#### 6. Functor

标签: #Functor; #函子

> 定义1.2
>
> Functor$F$满足
> $$
> F: C \rightarrow D
> $$
> 是在$C$和$D$之间的映射，是关于对象到对象、箭头到箭头的映射，即满足
>
> (a) $F(f: A \rightarrow B) = F(f): F(A) \rightarrow F(B)$
>
> (b) $F(1_A) = 1_{F(A)}$
>
> (c) $F(g \circ f) = F(g) \circ F(f)$

#### 6. Preorder(前序)

#### 10. 逻辑上的例子

存在**证明的范畴**（*category of proofs*），其中对象就是公式：
$$
\psi, \phi, ...
$$
arrow是从$\psi$到$\phi$的推理：
$$
\frac{\psi}{...}\\\frac{...}{\phi}
$$

#### 11. 计算机科学的例子

对于函数式编程语言$L$，存在一个联系范畴，$L$的数据类型就是对象，$L$中的可计算函数(过程/程序)就是arrows。对于$\begin{array}{cc} X & \xrightarrow{f} & Y \xrightarrow {g} Z\end{array}$则可以写作
$$
g\circ f = f;g
$$

#### 13. 幺半群

是具有二元运算$· : M \times M \rightarrow M$以及单位元$u \in M$的群，且符合对于所有$x, y, x \in M$，
$$
x ·	(y· z) = (x · y) · z
$$
以及
$$
u · x = x · u
$$

### 1.5 同构

> 定义1.3 同构
>
> 对于任何范畴 $C$， 一个箭头$f: A \rightarrow B$被称为**同构**(*isomorphism*)，如果在$C$中存在一个箭头$g: B \rightarrow A$使得
> $$
> \begin{align}
> g \circ f = 1_A && and && f \circ g = 1_B
> \end{align}
> $$

同构意味着，反过程是唯一的。

>定义1.4 群
>
>一个群$G$是一个幺半群，并对于任何一个元素$g$都有一个相反的$g^{-1}$。因此，$G$是一个仅有一个对象的范畴，其中每一个箭头都事一个同构。

## 1.6 范畴的建构

* 范畴的积:
  $$
  C \times D
  $$
  为
  $$
  (f, g) : (C, D) \rightarrow(C', D')
  $$

* 范畴的反面(*opposite*) $C^{op}$

  即箭头反调形成的范畴

* 箭头范畴(*arrow category*) $C^{\rightarrow}$：一个$C$将$C$中的箭头最为对象，然后有个箭头

# 文摘

# 评论

