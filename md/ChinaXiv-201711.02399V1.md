# 对焦分类方法

# The Focusing Classification Method

何沧平微博人工智能实验室cangping@staff.weibo.com

2017年11月16日

# 摘要

本文提出一个名为对焦分类的线性分类方法，尝试替代经典的逻辑回归。对焦分类能够从数学论证上保证法向量有界，有直观的几何解释，方便选取更接近最优值的参数初值，在手写数字图像数据集上的分类正确率、收敛速度均显著优于逻辑回归，参数初值即使分类正确率达到了 $9 7 . 3 1 \%$ 。

This paper proposes a new linear classification method named Focusing Classification, with the goal of taking the place of Logistic Regression. Focusing Classification has some advantages: length of its normal vector is limited,intuitional geometrical explanation,parameters' initial values are close to the best values.numerical experiments on the MNIST dataset demonstrate that Focusing Classification has better performance than Logistic Regression on length of its normal vector,accuracy and rate of convergence.With initial parameter values,Focusing Classification gains an accuracy of $9 7 . 3 1 \%$ ：

关键字：对焦分类，逻辑回归，线性分类

# 1引言

逻辑回归(Logistic Regression）是机器学习的一个基础分类方法[1]。它形式简单，有LIBLINEAR[2]这样的现成工具库，工程实现方便，在互联网推荐系统（例如广告点击预测，微博消息推送）中有广泛的应用。但是，逻辑回归仍有一些难以完美解决的的问题。

过拟合现象，即训练一段时间以后，随着训练样本集上的正确率逐渐提高，测试样本上的正确率却不再提高甚至反而下降。过拟合的根本原因尚无共识，目前的应对办法是在损失函数中添加正则化项[3]，阻止参数变得过大，至于多大算是"过大"，没有具体定义。

虽然正则化缓解了过拟合现象，但它带来了新的麻烦：正则化系数的选择缺少理论指导，只能针对具体训练样本多次试探；正则化还增加了模型复杂度，求解最优化问题需要大量的技巧[4-11]。

参数初值难选准。逻辑回归的参数只有大致的含义，例如w代表各个特性的权重，b代表截距。这些含义难以指导选到最优值附近的初值，通常的做法是随机选取初值、预训练。对某个具体训练样本集，按照均匀分布、正态分布等常见分布取值，尝试几次，选用表现最好的分布；先在小样本集上训练，然后将得到的最优参数值用作大样本集上的初值。这种两种方法都费时费力。

本文设计一种名为对焦分类（FocusingClassification）的线性二分类方法，克服逻辑回归面临的困难，同时不显著降低分类正确率，尝试代替逻辑回归。在"不让参数过大能够缓解过拟合现象"的假设前提下，对焦分类从数学理论上保证分隔平面法向量的模长有界，从而不必再使用正则化手段来缓解过拟合现象；对焦分类有明确直观的几何意义，方便为参数选取较准确的初值。

本文后续内容这样组织。第2节明确二分类问题并提出线性可分这个概念，第3节给出逻辑回归的几何解释，第4节给出对焦分类的具体公式，第5节是对焦分类的几何解释，第6节从数学上证明法向量有界，第7节给出具体算法实现，第8节是数值实验，第9节总结全文，第10节的附录证明逻辑回归法向量的无限和有界。

# 2 二分类问题

给定数据集 $D \ = \ \{ ( \mathbf { x } _ { 1 } , y _ { 1 } ) , ( \mathbf { x } _ { 2 } , y _ { 2 } ) , . . . , ( \mathbf { x } _ { m } , y _ { m } ) \}$ ，其中 $d$ 为正整数，列向量 $\mathbf { x } _ { i } ~ =$ $( x _ { i 1 } ; x _ { i 2 } ; \ldots ; x _ { i d } )$ ， $y _ { i } \in \{ 0 , 1 \}$ 。当 $y _ { i } = 1$ 时称 $\mathbf { x } _ { i }$ 是正样本，当 $y _ { i } = 0$ 时称 $\mathbf { x } _ { i }$ 是负样本。二分类问题是要从数据集 $D$ 中学习到一个模型，然后用这个模型预测任意的样本 ${ \bf x } _ { j }$ 是正样本还是负样本。

对给定数据集 $D$ ，记列向量 $\mathbf { w } = ( w _ { 1 } ; w _ { 2 } ; \ldots ; w _ { d } )$ ， $\mathbf { c } = ( c _ { 1 } ; c _ { 2 } ; \ldots ; c _ { d } )$ 。如果存在一个$d$ 维平面

$$
\mathbf { w } ^ { T } ( \mathbf { x } - \mathbf { c } ) = 0 , \quad | \mathbf { w } | \neq 0 ,
$$

使得对任意样本 ${ \bf x } _ { i } \in D$ 有

$$
\left\{ { \begin{array} { l l } { y _ { i } = 0 , } & { { \nmid \nmid \nmid \nmid \mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) < 0 , } } \\ { y _ { i } = 1 , } & { { \nmid \nmid \nmid \nmid \mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) \geq 0 , } } \end{array} } \right.
$$

或者

$$
\left\{ \begin{array} { l l } { y _ { i } = 1 , } & { \nleq { \mathbb { 1 } } \mathbb { 1 } \not \exists \not \in { \mathbf { w } } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) < 0 , } \\ { y _ { i } = 0 , } & { \ngeq { \mathbb { 1 } } \mathbb { 1 } \not \subset \mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) \geq 0 , } \end{array} \right.
$$

那么称数据集 $D$ 是线性可分的。下文仅讨论式(2)的情形，式(3)情形对应的算法和结论都相同。

如果用平面(1）来推测任意样本 $| \mathbf { x } _ { j } |$ 归属的类别

$$
y _ { j } = \left\{ { 0 , \quad \nrightarrow \nrightarrow \infty ^ { T } ( \mathbf { x } _ { j } - \mathbf { c } ) < 0 , } \right.
$$

那么(1)称为分隔平面。如果 $y _ { j } = 0$ ，那么推测 $\mathbf { x }$ 是负样本；如果 $y _ { j } = 1$ ，那么推测 $\mathbf { x } _ { j }$ 是正样本。

根据线性可分的定义，任意平面都可以用做分隔平面，区别只是推测效果可能不同。式(1）是分隔平面的点法式方程，由解析几何知道，它还有一个等价的斜截式方程。

# 3 逻辑回归的几何解释与初值

教科书中常以概率的角度讲解逻辑回归。为方便引入对焦分类方法，这里给出逻辑回归的直观几何解释和存在的初值问题。

逻辑回归的目标是从样本集中学习到分隔平面的斜截式方程

$$
\begin{array} { r } { \mathbf { w } ^ { T } \mathbf { x } + b = 0 , } \end{array}
$$

确定其中的法向量 $\mathbf { w }$ 和截距 $b$ 值。为此用到Sigmoid函数

$$
\sigma ( z ) = \frac { 1 } { 1 + e ^ { - z } } ,
$$

$\sigma ( z )$ 的图像如图1中的红色曲线所示。为了让正样本和负样本分别逼近函数 $\sigma ( z )$ 的正负无穷两端，对 $\forall \mathbf { x } _ { i } \in D$ ，令 $z _ { i } = \mathbf { w } ^ { T } \mathbf { x } _ { i } + b$ ，定义单个样本 $\mathbf { x } _ { i }$ 上的损失函数

$$
l ( z _ { i } ) = \left\{ \begin{array} { l l } { - \ln ( 1 - \sigma ( z _ { i } ) ) , } & { \mathcal { H } \mathbb { H } \mathbb { H } } \\ { - \ln ( \sigma ( z _ { i } ) ) , } & { \mathcal { H } \mathbb { H } \mathbb { H } } \end{array} { } y _ { i } = 0 , \right.
$$

因此，样本集 $D$ 上的损失函数为

$$
L ( \mathbf { w } , b ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } l ( z _ { i } ) ,
$$

求解它的最小值

$$
\{ \hat { \mathbf { w } } , \hat { b } \} = \arg \operatorname* { m i n } _ { \mathbf { w } , b } \frac { 1 } { m } \sum _ { i = 1 } ^ { m } l ( z _ { i } ) .
$$

就得到了最优参数w和 $\hat { b }$ 。

损失函数 $l ( z _ { i } )$ 能够衡量近似值 $\sigma ( z _ { i } )$ 与真实标签 $y _ { i }$ 之间的差距。如图1所示，红色曲线是Sigmoid函数 $\sigma ( z _ { i } )$ ；在 $\mathbf { x } _ { i }$ 为正样本即 $y _ { i } = 1$ 时，用右侧双向箭头标记的距离反映$\sigma ( z _ { i } )$ 与 $y _ { i } = 1$ 之间距离， $z _ { i }$ 越大， $\sigma ( z _ { i } )$ 越接近于 $y _ { i }$ ， $l ( z _ { i } )$ 越接近于0（见图2中红色曲线)；在 $\mathbf { x } _ { i }$ 为负样本即 $y _ { i } = 0$ 时，用左侧双向箭头标记的距离反映 $\sigma ( z _ { i } )$ 与 $y _ { i } = 0$ 之间距离， $z _ { i }$ 越小， $1 - \sigma ( \boldsymbol { z } _ { i } )$ 越接近于 $1 - y _ { i } = 1$ ， $l ( z _ { i } )$ 越接近于0 (见图 2中蓝色曲线)。

![](images/e6cfd578dda8e900480a676e986049c2f6d60e14bcf12ba4a2b88d3c42818ec0.jpg)  
图1：逻辑回归：近似值 $\sigma ( z _ { i } )$ (红色曲线)与样本标签的距离 (带双向箭头的直线)。

![](images/2ab739f995361bc67bd975285f20685a3c7b5e99fc3dba9e8abc69de800771ef.jpg)  
图2：逻辑回归：单个样本上的损失函数 $l ( z _ { i } )$ 。

图2画出了单个正样本 (红色)和单个负样本（蓝色）的损失曲线。直观地理解，如果样本集是线性可分的，那么正样本对应的 $z _ { i }$ 越大，该样本上的损失函数值越小；负样本对应的 $z _ { i }$ 越小，该样本上的损失函数值越小。从而，式(4)的计算结果是负样本向 $z _ { i }$ 负无穷方向移动，正样本向 $z _ { i }$ 正无穷方向移动，达到了分类的目的。

虽然能分离正负样本，但逻辑回归还有个问题待解决：初值难选准。

由附录中的定理4知道，样本集 $D$ 线性可分时，逻辑回归最优分隔平面的法向量 $\hat { \mathbf { w } }$ 的模长是 $+ \infty$ 。这意味着，求解式(4)的过程中法向量模长趋向 $+ \infty$ ，但永远无法达到 $+ \infty$ ，必须在适当的时候结束迭代计算。那么问题就来了，不知道结束迭代时法向量的模长是多少，无法为法向量 $\mathbf { w }$ 选择接近最优法向量的初值，导致计算量较多。截距 $b$ 的最优值依赖于法向量 $\mathbf { w }$ ，因此也难给它一个较好的初值。

由附录中的定理5知道，样本集 $D$ 线性不可分时，逻辑回归最优分隔平面的法向量W有界。虽然不再趋向于 $+ \infty$ ，但仍然无法预先估算W的位置。在实际应用中，还会在式（4)的目标函数中添加正则化项，导致W的取值更加复杂，初值更难选准。

# 4对焦分类方法

既然法向量无限是逻辑回归初值难选的一个原因，那么就让对焦分类自动保证法向量有界。逻辑回归采用的斜截式平面方程(3)，参数含义不直观。对焦分类方法采用斜截式与点法式混合形式的平面方程，使各个参数都有直观的几何意义，指导选取较好的初值。

对焦变换的形式为

$$
z _ { i } = \mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) + b ,
$$

这里的 $\mathbf { c }$ 是需要指定的任意向量，称为锚点；w称为法向量，实数 $b$ 称为离心距， $z _ { i }$ 称为法向距离。定义两个实数 $F _ { 0 }$ 和 $F _ { 1 }$ ，称为焦点，满足 $F _ { 0 } = - F _ { 1 }$ 且 $F _ { 1 } > \ln ( 3 ) = 1 . 0 9 8 6$ 。记$G _ { 0 } = \sigma ( F _ { 0 } )$ ， $G _ { 1 } = \sigma ( F _ { 1 } )$ 。

定义4个下标集 $\begin{array} { r } { \underset { \{ \mathfrak { A } = \{ i \} y _ { i } = 1 , z _ { i } \leq F _ { 1 } , i = 1 , 2 , \ldots , m \} , \ J _ { 0 } } { \widehat { \sharp } } = \{ i | y _ { i } = 0 , z _ { i } \leq F _ { 0 } , i = 1 , 2 , \ldots , m \} , \ I _ { 1 } = \{ i | y _ { i } = 0 , z _ { i } \geq 2 , \ldots , m \} , \ J _ { 2 } = \{ i | z _ { i } = 1 , \ldots , z _ { i } \geq F _ { 1 } , i = 1 , 2 , \ldots , m \} , \ J _ { 0 } = \{ i | y _ { i } = 1 , 2 , \ldots , K _ { 1 } \} , \ } \end{array}$ $F _ { 0 } , i = 1 , 2 , \dots , m \}$ $1 , 2 , \ldots , m \}$ 。

单个样本 ${ \bf x } _ { i } \in D$ 上的损失函数定义为

$$
h ( z _ { i } ) = \left\{ \begin{array} { l l } { 1 - \cos ( r ( G _ { 0 } - \sigma ( z _ { i } ) ) , } \\ { 1 - \cos ( \sigma ( z _ { i } ) - G _ { 0 } ) , } \\ { 1 - \cos ( G _ { 1 } - \sigma ( z _ { i } ) ) , } \\ { 1 - \cos ( r ( \sigma ( z _ { i } ) - G _ { 1 } ) ) , } \end{array} \right.
$$

这里 $\boldsymbol { r }$ 的取值范围为 $[ 0 , \pi / ( 2 G _ { 1 } - 1 ) ]$ ，一个典型值是 $r = ( 1 - G _ { 0 } ) / G _ { 0 }$ 。将样本集 $D$ 的上损失函数定义为

$$
H ( \mathbf { w } , b ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } h ( z _ { i } ) .
$$

给定锚点 $| \mathbf { c } \rrangle$ ，在样本集 $D$ 上求损失函数式（7）的最小值

$$
\{ \hat { \mathbf { w } } , \hat { b } \} = \underset { \mathbf { w } , b } { \arg \operatorname* { m i n } } H ( \mathbf { w } , b )
$$

即可得到最优参数 $\hat { \mathbf { w } }$ 和 $\hat { b }$ 。然后，对任意的样本 ${ \bf x } _ { j }$ ，对它做对焦变换

$$
z _ { j } = \hat { \mathbf { w } } ^ { T } ( \mathbf { x } _ { j } - \mathbf { c } ) + \hat { b } ,
$$

用式(10)来推测它是正样本或是负样本：

$$
y _ { j } = \left\{ { \begin{array} { l l } { 0 , } & { { \mathtt { M } } { \rVert } \bigoplus _ { j } z _ { j } < 0 , } \\ { 1 , } & { { \mathtt { M } } { \rVert } \bigoplus _ { \mathbf { k } } z _ { j } \geq 0 , } \end{array} } \right.
$$

如果 $y _ { j } = 0$ ，那么推测 $\mathbf { x } _ { j }$ 是负样本；如果 $y _ { j } = 1$ ，那么推测 $\mathbf { x } _ { j }$ 是正样本。

使用最速下降法等迭代方法求解式(8)时,需要计算导数。对 $\forall 1 \leq i \leq m$ 和 $\forall 1 \leq j \leq d$ ，由式 (5)(6)知，损失函数的偏导数为

$$
h ^ { \prime } ( z _ { i } ) = \left\{ \begin{array} { l l } { - \sin [ r ( G _ { 0 } - \sigma ( z _ { i } ) ) ] r \sigma ^ { \prime } ( z _ { i } ) , } \\ { \sin ( \sigma ( z _ { i } ) - G _ { 0 } ) \sigma ^ { \prime } ( z _ { i } ) , } \\ { - \sin ( G _ { 1 } - \sigma ( z _ { i } ) ) \sigma ^ { \prime } ( z _ { i } ) , } \\ { \sin [ r ( \sigma ( z _ { i } ) - G _ { 1 } ) ] r \sigma ^ { \prime } ( z _ { i } ) , } \end{array} \right.
$$

$$
\begin{array} { r c l } { \displaystyle \frac { \partial h ( \boldsymbol { z } _ { i } ) } { \partial \boldsymbol { w } _ { j } } } & { = } & { \displaystyle \frac { \partial h ( \boldsymbol { z } _ { i } ) } { \partial \boldsymbol { z } _ { i } } \frac { \partial \boldsymbol { z } _ { i } } { \partial \boldsymbol { w } _ { j } } = \frac { \partial h ( \boldsymbol { z } _ { i } ) } { \partial \boldsymbol { z } _ { i } } ( \boldsymbol { x } _ { i j } - \boldsymbol { c } _ { j } ) , } \\ { \displaystyle \frac { \partial h ( \boldsymbol { z } _ { i } ) } { \partial b } } & { = } & { \displaystyle \frac { \partial h ( \boldsymbol { z } _ { i } ) } { \partial \boldsymbol { z } _ { i } } \frac { \partial \boldsymbol { z } _ { i } } { \partial b } = \frac { \partial h ( \boldsymbol { z } _ { i } ) } { \partial \boldsymbol { z } _ { i } } . } \end{array}
$$

从而有

$$
\begin{array} { r } { \displaystyle \frac { \partial H ( { \bf w } , b ) } { \partial { \bf w } } = - \sum _ { i \in I _ { 0 } } \sin [ r ( G _ { 0 } - \sigma ( z _ { i } ) ) ] r \sigma ^ { \prime } ( z _ { i } ) ( { \bf x } _ { i } - { \bf c } ) + \sum _ { i \in I _ { 1 } } \sin ( \sigma ( z _ { i } ) - G _ { 0 } ) \sigma ^ { \prime } ( z _ { i } ) ( { \bf x } _ { i } - { \bf c } ) } \\ { - \sum _ { i \in J _ { 0 } } \sin ( G _ { 1 } - \sigma ( z _ { i } ) ) \sigma ^ { \prime } ( z _ { i } ) ( { \bf x } _ { i } - { \bf c } ) + \sum _ { i \in J _ { 1 } } \sin [ r ( \sigma ( z _ { i } ) - G _ { 1 } ) ] r \sigma ^ { \prime } ( z _ { i } ) ( { \bf x } _ { i } - { \bf c } ) , } \end{array}
$$

$$
\begin{array} { r } { \displaystyle \frac { \partial { \cal H } ( { \bf w } , b ) } { \partial b } = - \sum _ { i \in I _ { 0 } } \sin [ r ( G _ { 0 } - \sigma ( z _ { i } ) ) ] r \sigma ^ { \prime } ( z _ { i } ) + \sum _ { i \in I _ { 1 } } \sin ( \sigma ( z _ { i } ) - G _ { 0 } ) \sigma ^ { \prime } ( z _ { i } ) } \\ { \displaystyle - \sum _ { i \in J _ { 0 } } \sin ( G _ { 1 } - \sigma ( z _ { i } ) ) \sigma ^ { \prime } ( z _ { i } ) + \sum _ { i \in J _ { 1 } } \sin [ r ( \sigma ( z _ { i } ) - G _ { 1 } ) ] r \sigma ^ { \prime } ( z _ { i } ) . } \end{array}
$$

# 5 对焦分类的几何解释

本节给出对焦换式（5）中的参数w、c、 $b$ 和 $z _ { i }$ 的直观含义，为此引入一个解析几何中的概念。

定义1.对 $d$ 维平面 $\mathbf { n } ^ { T } ( \mathbf { x } - \mathbf { c } ) = 0$ 和 $d$ 维空间的任意点 $\mathbf { x } _ { i }$ ，称 $\frac { \mathbf n ^ { T } ( \mathbf x _ { i } - \mathbf c ) } { | \mathbf n | }$ 为点到平面的有向距离，称 $\mathbf { n } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } )$ 为点到平面的法向距离。

由定义 1知道，法向距离等于有向距离乘以平面法向量的模长。令 $\begin{array} { r } { p _ { i } = \frac { \mathbf { n } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) } { | \mathbf { n } | } } \end{array}$ ，由解析几何知道，如果 $p _ { i } > 0$ ，那么点 $\mathbf { x } _ { i }$ 在法向 $\mathbf { n }$ 方向的一侧 (正面)；如果 $p _ { i } < 0$ ，那么点$\mathbf { x } _ { i }$ 在法向 $\mathbf { n }$ 方向相反的一侧 (背面)；如果 $p _ { i } = 0$ ，那么点 $\mathbf { x } _ { i }$ 在平面上。

使用式(8)得到的最优参数w 和 $\hat { b }$ 以后，就得了最优分隔平面的斜截式方程

$$
\begin{array} { r } { \hat { \mathbf { w } } ^ { T } ( \mathbf { x } - \mathbf { c } ) + \hat { b } = 0 , } \end{array}
$$

其中锚点 $| \textbf { c } \rrangle$ 是任意指定的常向量。假设这个平面的点法式方程为

$$
\hat { \mathbf { w } } ^ { T } ( \mathbf { x } - \hat { \mathbf { c } } ) = 0 ,
$$

那么易知

$$
\hat { b } = \hat { \mathbf { w } } ^ { T } ( \mathbf { c } - \hat { \mathbf { c } } ) .
$$

从而 $\hat { b }$ 的几何意义就是锚点 $| \textbf { c } \rrangle$ 到分隔平面的法向距离，这正是它的名字离心距的由来。

由定义1知道， $z _ { i } = \hat { \mathbf { w } } ^ { T } ( \mathbf { x } _ { i } - \hat { \mathbf { c } } )$ 是点 $\mathbf { x } _ { i }$ 到分隔平面(14)的法向距离。对分隔平面来说，只要法向量W保持方向不变，模长做任意变化仍然表示同一个平面。注意，零向量没有方向，法向量的模长不能为0。

实际计算时，能从计算结果中得到分隔平面的斜截式方程 (13)。现在来确定分隔平面的点法式方程(14）中的c。注意，在分隔平面固定的情况下，该平面的上任意点均可用作式(14)中的c。为了保证唯一性和推导方便，不妨假设c-c与法向量W共线，即存在非零实数 $s$ 使得

$$
\mathbf { c } - \hat { \mathbf { c } } = s \hat { \mathbf { w } } ,
$$

那么由式(15)知

$$
\hat { b } = \hat { \mathbf { w } } ^ { T } s \hat { \mathbf { w } } = s | \hat { \mathbf { w } } | ^ { 2 } ,
$$

从而有

$$
| \mathbf { c } - { \hat { \mathbf { c } } } | = s | { \hat { \mathbf { w } } } | = { \frac { \hat { b } } { | { \hat { \mathbf { w } } } | } } ,
$$

$$
\hat { \mathbf { c } } = \mathbf { c } - s \hat { \mathbf { w } } = \mathbf { c } - \frac { \hat { b } } { | \hat { \mathbf { w } } | ^ { 2 } } \hat { \mathbf { w } } .
$$

以2 维样本为例说明各个参数的含义。对2维样本，分隔平面退化为直线。图3中，黑色直线 $\mathbf { w } ^ { T } ( \mathbf { x } - \mathbf { c } ) = 0$ 是迭代计算的起点，法向量W 和锚点 $\mathbf { c }$ 随意取值，离心距 $b$ 的初值取0。带箭头的黑色直线是法向量 $\mathbf { w }$ ，两条直线的交叉点是 $\mathbf { \sigma } _ { \mathbf { c } }$ 。绿色直线是迭代若干次之后得到的最优分隔线 $\hat { \mathbf { w } } ^ { T } ( \mathbf { x } - \mathbf { c } ) + \hat { b } = 0$ ，带箭头的绿色直线是它的法向W，两条直线的交叉点就是c。点 $\mathbf { c }$ 和点之间距离为 $\hat { b } / | \hat { \mathbf { w } } |$ ，对应式 (16)，这意味着 $\hat { b }$ 能够衡量人为指定的锚点 $\mathbf { c }$ 与最优锚点之间的距离。

![](images/2268340cbd33e8fc592a5740411a90ebe89ad146a7dbf19d37eed6ab137250a2.jpg)  
图3：对焦分类中参数的几何意义

现在考察对焦对类方法的分类机理。

观察损失函数 $h ( z _ { i } )$ 的走势，见图4， $y _ { i } = 1$ 标识的曲线对应正样本， $y _ { i } = 0$ 标识的曲线对应负样本。由图 4和式(6)可以看出，在 $r = ( 1 - G _ { 0 } ) / G _ { 0 }$ 时，正负样本的损失曲线关于纵轴轴对称，两条曲线在焦点 $F _ { 1 }$ 和 $F _ { 0 }$ 处的值分别为0，且有

$$
\operatorname* { l i m } _ { z _ { i } \to - \infty } \ h ( z _ { i } ) = \operatorname* { l i m } _ { z _ { i } \to + \infty } \ h ( z _ { i } ) = \operatorname* { l i m } _ { z _ { i } \to - \infty } \ h ( z _ { i } ) = \operatorname* { l i m } _ { z _ { i } \to + \infty } \ h ( z _ { i } ) = 1 - \cos ( G _ { 1 } ) .
$$

从图 4可以看出，也可以用式(6)严格证明：在 $y _ { i } = 0$ 时， $h ( z _ { i } )$ 在 $( - \infty , F _ { 0 } ]$ 严格单调递减，在 $[ F _ { 0 } , + \infty )$ 严格单调递增；在 $y _ { i } = 1$ 时， $h ( z _ { i } )$ 在 $\left( - \infty , F _ { 1 } \right]$ 严格单调递减，在$[ F _ { 1 } , + \infty )$ 严格单调递增。

对一个正样本 $\mathbf { x } _ { i }$ 来说，它的法向距离 $z _ { i }$ 落在焦点 $F _ { 1 }$ 上时对整体损失 ${ \cal H } ( { \bf w } , b )$ 的贡献最小。但是，所有正样本的法向距离 $z _ { i }$ 通常会散落在一个区间中，不会全部落在焦点 $F _ { 1 }$ 上。因此，调整对焦变换中的参数使所在正样本的法向距离聚集在焦点 $F _ { 1 }$ 附近，就能促使整体损失 ${ \cal H } ( { \bf w } , b )$ 达到最小值。同理，负样本的法向距离集中在焦点 $F _ { 0 }$ 附近时，也能促进整体损失 ${ \cal H } ( { \bf w } , b )$ 达到最小值。

观察损失函数导数 $h ^ { \prime } ( z )$ 的图像，见图5，两条曲均连续，焦点 $F _ { 0 }$ 、 $F _ { 1 }$ 之外均光滑。这意味着迭代过程会平稳地收敛到最优点，不会出现前进方向的跳变。越靠近焦点，导数的绝对值越大，这意味着迭代计算时将加速逼近最优值，不会在最优值附近震荡。沿着正无穷和负无穷方向，导数快速逼近0，这意味着如果对焦变换参数的初值偏离最优值太远，那么收敛会很慢。不过，使用时不必担心这个问题，7.1节给出的方法能选到接近最优值的初值。

![](images/88df09b552584fecbdacc8908c639c606bb43b97554df13bf48dae3fb3c06801.jpg)  
图4:单个样本上的损失函数 $h ( z _ { i } )$ ，焦点 $F _ { 0 } = - 1 . 5$ ， $F _ { 1 } = 1 . 5$ ， $r = ( 1 - G _ { 0 } ) / G _ { 0 } ,$ #

# 6法向量边界

本节证明对焦变换中的最优法向量 $\hat { \mathbf { w } }$ 和 $\hat { b }$ 是有界的，从而不必担心逻辑回归中出现的法向无限问题。先证明1维样本的情形，再证明 $d$ 维样本的情形。

# 6.11维样本

对1维样本，样本向量在形式上就成为 $\mathbf { x } _ { i } = \left( x _ { i 1 } \right)$ ，简记为 $x _ { i }$ ，将 $\mathbf { w } = ( w _ { 1 } )$ 简记为 $w$ ，将 $\mathbf { c } = \left( c _ { 1 } \right)$ 简记为 $\boldsymbol { \mathscr { c } }$ 。假设样本集 $D _ { 1 } = \{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , \dots , ( x _ { m } , y _ { m } ) \}$ 是线性可分的，即存在一个点 $\hat { c }$ 使得

$$
\left\{ \begin{array} { l l } { y _ { i } = 0 , \quad \niiint \ncong x _ { i } < \hat { c } , } \\ { y _ { i } = 1 , \quad \niiint \ncong x _ { i } > \hat { c } , } \end{array} \right.
$$

或者

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { y _ { i } = 1 , \quad \mathtt { j } \sharp \sharp \ x _ { i } < \hat { c } , } \\ { y _ { i } = 0 , \quad \mathtt { j } \sharp \sharp \ x _ { i } > \hat { c } . } \end{array} \right. } \end{array}
$$

![](images/8836b12f82227292b1cbbe164c4b347dfa6d16c6bcf2ff295258c1811993829c.jpg)  
图5：单个样本上的损失函数的导数 $h ^ { \prime } ( z _ { i } )$ ，焦点 $F _ { 0 } = - 1 . 5$ ， $F _ { 1 } = 1 . 5$ ， $r = ( 1 - G _ { 0 } ) / G _ { 0 }$ 。

这时最优分隔平面退化一个点： $z = { \hat { c } }$ 。不失一般性，再假设 $\hat { c } = 0$ 。如果 $\hat { c } \neq 0$ ，只需对所有样本 $x _ { i } , i = 1 , 2 , \ldots , m$ 都作一个平移操作，不影响分类结果。 $\hat { c } = 0$ 时，取 $\boldsymbol c = \boldsymbol { \hat { c } }$ ，由式(5)知 $\hat { b } = 0$ ，对焦变换就成为

$$
z _ { i } = w ( x _ { i } - \hat { c } ) + \hat { b } = w x _ { i } .
$$

既然 $\hat { b }$ 已经确定，现在寻找最优参数的工作只剩下确定式(19)中的最优标量 $\hat { w }$ 。

接下来仅讨论(17）成立的情形，(18）成立的情形证明方法相同。

定理1．1维样本集 $D$ 线性可分时，对焦分类最优分隔平面的法向量有界。

证：为方便叙述，假设

$$
x _ { m _ { 1 } + m _ { 0 } } \leq x _ { m _ { 1 } + m _ { 0 } - 1 } \leq \cdots \leq x _ { m _ { 1 } + 1 } < 0 < x _ { 1 } \leq x _ { 2 } \leq \cdots \leq x _ { m _ { 1 } } ,
$$

其中 $m _ { 0 }$ 和 $m _ { 1 }$ 为正整数，且满足 $m _ { 0 } + m _ { 1 } = m$ 。记

$$
h _ { 0 0 } ( z _ { i } ) = \left\{ \begin{array} { l l } { 1 - \cos ( r ( G _ { 0 } - \sigma ( z _ { i } ) ) , } \\ { 0 , } \end{array} \right.
$$

$$
h _ { 0 1 } ( z _ { i } ) = \left\{ \begin{array} { l l } { 1 - \cos ( \sigma ( z _ { i } ) - G _ { 0 } ) , } \\ { 0 , } \end{array} \right.
$$

6法向量边界

$$
h _ { 1 1 } ( z _ { i } ) = \left\{ \begin{array} { l l } { 1 - \cos ( r ( \sigma ( z _ { i } ) - G _ { 1 } ) ) , } \\ { 0 , } \end{array} \right.
$$

$$
H _ { 0 } ( w ) = \sum _ { y _ { i } = 0 } h ( z _ { i } ) , \ H _ { 1 } ( w ) = \sum _ { y _ { i } = 1 } ^ { m } h ( z _ { i } ) ,
$$

从而式(7)变为

$$
H ( w , b ) = \frac { 1 } { m } \left[ H _ { 0 } ( w ) + H _ { 1 } ( w ) \right] .
$$

在 $w x _ { m _ { 1 } } < F _ { 1 }$ 即 $w < F _ { 1 } / x _ { m _ { 1 } }$ 时，由式(19)(20)(22)得到

$$
H _ { 1 } ( w ) = \sum _ { i = 1 } ^ { m _ { 1 } } h _ { 1 0 } ( w x _ { i } ) , \quad H _ { 1 } ^ { \prime } ( w ) = x _ { i } \sum _ { i = 1 } ^ { m _ { 1 } } h _ { 1 0 } ^ { \prime } ( w x _ { i } ) ,
$$

对 $1 \leq i \leq m _ { 1 }$ ， $x _ { i } > 0$ ， $h _ { 1 0 } ^ { \prime } ( w x _ { i } ) < 0$ ，因此 $H _ { 1 } ^ { \prime } ( w ) < 0$ ， $H _ { 1 } ( w )$ 在 $\left( - \infty , F _ { 1 } / x _ { m _ { 1 } } \right]$ 严格单调递减。

在 $w x _ { 1 } > F _ { 1 }$ 即 $w > F _ { 1 } / x _ { 1 }$ 时，由式(19)(21)(22)得到

$$
H _ { 1 } ( w ) = \sum _ { i = 1 } ^ { m _ { 1 } } h _ { 1 1 } ( w x _ { i } ) , \quad H _ { 1 } ^ { \prime } ( w ) = x _ { i } \sum _ { i = 1 } ^ { m _ { 1 } } h _ { 1 1 } ^ { \prime } ( w x _ { i } ) ,
$$

对 $1 \leq i \leq m _ { 1 } , \ x _ { i } > 0 , \ h _ { 1 1 } ^ { \prime } ( w x _ { i } ) > 0$ ，因此 $H _ { 1 } ^ { \prime } ( w ) > 0$ ， $H _ { 1 } ( w )$ 在 $[ F _ { 1 } / x _ { 1 } , \infty )$ 严格单调递增。

综合 $H _ { 1 } ( w )$ 在 $w < F _ { 1 } / x _ { m _ { 1 } }$ 和 $w > F _ { 1 } / x _ { 1 }$ 两种情形下的单调性，再考虑到 $H _ { 1 } ( w )$ 一阶连续可导，可知 $H _ { 1 } ( w )$ 的全局最小点 $\hat { w } _ { 1 }$ 落在区间 $[ F _ { 1 } / x _ { m _ { 1 } } , F _ { 1 } / x _ { 1 } ]$ 0

用同样的方法可以证明， $H _ { 0 } ( w )$ 的全局最小点 $\hat { w } _ { 0 }$ 落在区间 $[ F _ { 0 } / x _ { m _ { 1 } + m _ { 0 } } , F _ { 0 } / x _ { m _ { 1 } + 1 } ] \subset$ 由式(23)知, $\boldsymbol { H } ( \boldsymbol { w } , \boldsymbol { b } )$ 的全局最小点 $\hat { w }$ 落在区间 $[ \operatorname* { m i n } \{ F _ { 0 } / x _ { m _ { 1 } + m _ { 0 } } , F _ { 1 } / x _ { m _ { 1 } } \}$ $\operatorname* { m a x } \{ F _ { 1 } / x _ { 1 } , F _ { 0 } / x _ { m _ { 1 } + 1 } \} ]$ 即 $\hat { w }$ 有界。

[证毕]

# 6.2 $d$ 维样本

借助法向距离可以将 $d \geq 2$ 维样本集 $D = \{ ( \mathbf { x } _ { 1 } , y _ { 1 } ) , ( \mathbf { x } _ { 2 } , y _ { 2 } ) , \dots , ( \mathbf { x } _ { m } , y _ { m } ) \}$ 上的二分类问题转化为1维样本集上的二分类问题，从而完成证明。

定理2. $d$ 维样本集线性可分时，对焦分类最优分隔平面的法向量有界。

证：假设 $d$ 维样本集 $D$ 是线性可分的，再假设将 $D$ 完全正确分类的最优分隔平面为

$$
\begin{array} { r } { \hat { \mathbf { w } } ^ { T } ( \mathbf { x } - \mathbf { c } ) + \hat { b } = 0 . } \end{array}
$$

令单位向量 $\mathbf { n } = \hat { \mathbf { w } } / | \hat { \mathbf { w } } |$ ， $p _ { i } = { \bf n } ^ { T } ( { \bf x } _ { i } - { \bf c } ) + \hat { b }$ ，显然 $p _ { i }$ 是样本 $\mathbf { x } _ { i }$ 到平面(24)的有向距离,样本集 $D$ 上二分类问题等价于1维样本集 ${ { D } _ { 1 } } = \left\{  { \left( { { p } _ { 1 } } , { { y } _ { 1 } } \right) } , { { \left( { { p } _ { 2 } } , { { y } _ { 2 } } \right) } , . . . , { { \left( { { p } _ { m } } , { { y } _ { m } } \right) } } } \right\}$ 上的二分类问题，假设 $D _ { 1 }$ 上的对焦变换为

$$
z _ { i } = \lambda p _ { i } .
$$

由定理1知，式（25）的最优参数 $\hat { \lambda }$ 有界，从而样本集 $D$ 上的最优法向量 $\hat { \mathbf { w } } = \hat { \lambda } \mathbf { n }$ 有界。

[证毕]

# 6.3 样本集线性不可分

通常情况下，样本集是线性不可分的，即对任意给定的分隔平面，其正面（或背面）都有一些负样本 (或正样本)。这种情形下，最优分隔平面法向量有界的前提条件变得复杂。

观察图4中的损失函数曲线，猜测会有一个暂无证明的模糊结论：

定理3. $d$ 维样本集 $D$ 线性不可分时，如果所有正样本的中心点与所有负样本的中心点显著分离，那么对焦分类的最优法向量有界。

# 7对焦分类的算法实现

本节起，考虑一般性的 $d \geq 1$ 维样本集，为叙述便利，统一采用向量符号，不再单独考虑 $d = 1$ 的情形。

# 7.1 参数初值

用最速下降法等方法迭代求解式(8)时，需要给出式(5)中的3个参数 $\mathbf { c } , b$ 和 $\mathbf { w }$ 的初值。

由图6直观地看，正负样本都是聚集在某个区域。由统计规律知道，很多随机事件服从正态分布。对正态分布而言，数学期望是它的中心，正样本中心和负样本中心之间的中点应该位于分隔平面的附近。定义2个集合 $K _ { 0 } = \{ i | y _ { i } = 0 , 1 \leq i \leq m \}$ 和 $K _ { 1 } = \{ i | y _ { i } = 1 , 1 \leq$ $i \leq m \}$ ，将 $K _ { 0 }$ 和 $K _ { 1 }$ 中元素的数量分别记为 $m _ { 0 }$ 和 $m _ { 1 }$ 。将正样中心和负样本中心分别记为

$$
\pmb { \mu } _ { 1 } = \frac { 1 } { m _ { 1 } } \sum _ { i \in K _ { 1 } } \mathbf { x } _ { i } , \ \pmb { \mu } _ { 0 } = \frac { 1 } { m _ { 0 } } \sum _ { i \in K _ { 0 } } \mathbf { x } _ { i } ,
$$

从而锚点 $\mathbf { c }$ 可以指定为

$$
\mathbf { c } = \frac { \pmb { \mu } _ { 0 } + \pmb { \mu } _ { 1 } } { 2 } .
$$

理想情况下，c恰好落在最优分隔平面上，此时有 $\mathbf { c } = \hat { \mathbf { c } }$ ，由式(16)知道 $\hat { b } = 0$ 。因此,$b$ 的初值应选为

$$
b = 0 .
$$

![](images/1f4ecb94d2848bef20d604bdaca6ccddefb38454c43a512a07763113a022ed7e.jpg)  
图6：参数的初值。2个五角星分别为正负样本的中心。

由图4知，正负样本会分别聚集在焦点 $F _ { 1 }$ 、 $F _ { 0 }$ 附近，因此选取w的初值使得正样本的中心 $\pmb { \mu } _ { 1 }$ 落在焦点 $F _ { 1 }$ 上，使得负样本的中心 $\pmb { \mu } _ { 0 }$ 落在焦点 $F _ { 0 }$ 上。几乎不存w 使得正负样本中心同时落在焦点上，因此实际操作中选取一个中间值。这个初值几乎肯定不是最优值，但离最优值不会太远。

为了确定法向量 $\mathbf { w }$ 的初值，先确定其方向 $\mathbf { n }$ ，再确定其模长 $\lambda$ ，即 $\mathbf { w } = \lambda \mathbf { n }$ 。用正负样本中心的连线方向作为 $\mathbf { n }$ 的方向，即

$$
\begin{array} { r } { { \bf n } = ( { \pmb \mu } _ { 1 } - { \pmb \mu } _ { 0 } ) / | { \pmb \mu } _ { 1 } - { \pmb \mu } _ { 0 } | . } \end{array}
$$

令 $\theta _ { 0 } = { \bf n } ^ { T } ( \pmb { \mu } _ { 0 } - \mathbf { c } ) , \theta _ { 1 } = { \bf n } ^ { T } ( \pmb { \mu } _ { 1 } - \mathbf { c } ) .$

$$
\lambda = \frac { 1 } { 2 } \left( \frac { F _ { 0 } } { \theta _ { 0 } } + \frac { F _ { 1 } } { \theta _ { 1 } } \right) ,
$$

从而法向量的初值就为

$$
\begin{array} { r c l } { \mathbf { w } } & { = } & { \lambda \mathbf { n } } \\ & { = } & { \displaystyle \frac { 1 } { 2 } \left( \frac { F _ { 0 } } { \theta _ { 0 } } + \frac { F _ { 1 } } { \theta _ { 1 } } \right) \frac { \mu _ { 1 } - \mu _ { 0 } } { | \pmb { \mu } _ { 1 } - \pmb { \mu } _ { 0 } | } . } \end{array}
$$

# 7.2 调整标准差

在实际应用案例中，通常正样本和负样本的方差不相等，甚至相差很大，这种差别导致对焦分类的分类精度稍低于逻辑回归，原因也相当直观。

实际案例中的样本集通常是几乎线性可分的：只有少量的样本（例如小于 $5 \%$ ）被错误分类，因而逻辑回归法向量的模长相当大，正负样本对应的 $z _ { i }$ 均远离原点。从图1可以看出，在远离原点的地方，例如正无穷方向，不同样本的损失函数值的差别很小，远小于在原点附近的差别，从而逻辑回归对方差差异不敏感。

对焦回归就不一样了，大量样本聚集在焦点附近，样本之间的损失函数值差别大得多，因此必须调整均衡。

利用 (28)中的单位向量 $\mathbf { n }$ ，令 $p _ { i } = \mathbf { n } ^ { T } \mathbf { x } _ { i }$ 。定义集合 $P _ { 0 } = \{ p _ { i } | i \in K _ { 0 } \}$ ， $P _ { 1 } = \{ p _ { i } | i \in K _ { 0 } \}$ 将 $P _ { 0 }$ 中所有元素的标准差记为 $\scriptstyle v _ { 0 }$ ，将 $P _ { 1 }$ 中所有元素的标准差记为 $\boldsymbol { v } _ { 1 }$ 。定义常量标准差比例为

$$
\eta = \left\{ \begin{array} { l l } { v _ { 0 } / v _ { 1 } , } & { \mathcal { U } \mathbb { H } \mathbb { E } v _ { 0 } \leq v _ { 1 } , } \\ { v _ { 1 } / v _ { 0 } , } & { \mathcal { U } \mathbb { H } \mathbb { E } v _ { 0 } > v _ { 1 } . } \end{array} \right.
$$

记

$$
\xi _ { 0 } = { \mathbf w } ^ { T } ( { \pmb \mu } _ { 0 } - { \mathbf c } ) + b , \quad \xi _ { 1 } = { \mathbf w } ^ { T } ( { \pmb \mu } _ { 1 } - { \mathbf c } ) + b .
$$

现在可以对 $z _ { i }$ 做标准差修正了。当 $v _ { 0 } \leq v _ { 1 }$ 时，令

$$
\begin{array} { r } { \bar { z } _ { i } = \left\{ \begin{array} { l l } { z _ { i } , } & { \mathcal { U } \mathbb { H } \mathbb { H } \bar { \times } i \in K _ { 0 } , } \\ { \eta ( z _ { i } - \xi _ { 1 } ) + \xi _ { 1 } , } & { \mathcal { U } \mathbb { H } \mathbb { H } i \in K _ { 1 } , } \end{array} \right. } \end{array}
$$

当 $v _ { 0 } > v _ { 1 }$ 时，令

$$
\begin{array} { r } { \bar { z } _ { i } = \left\{ \begin{array} { l l } { \eta ( { z } _ { i } - { \xi } _ { 0 } ) + \xi _ { 0 } , } & { \mathcal { U } \mathbb { H } \bar { \lesssim } i \in K _ { 0 } , } \\ { z _ { i } , } & { \mathcal { U } \mathbb { H } \bar { \lesssim } i \in K _ { 1 } . } \end{array} \right. } \end{array}
$$

在后续迭代计算中，用 $\bar { z } _ { i }$ 代替损失函数和损失函数导数公式里的 $z _ { i }$ 。

# 7.3 迭代算法

这里用最速下降法寻找对焦分类的最优参数，即求解最小化问题式(8)。使用其它最优法算法时，请参照实施。

步1，获取数据：样本集 $D = \{ ( \mathbf { x } _ { 1 } , y _ { 1 } ) , ( \mathbf { x } _ { 2 } , y _ { 2 } ) , \dots , ( \mathbf { x } _ { m } , y _ { m } ) \} _ { \textsc { c } }$ （20

步2，离心距赋初值： $b = 0$ 。

步3，锚点赋初值：使用式(26)计算正负样本的中心点 $\pmb { \mu } _ { 1 }$ 和 $\pmb { \mu } _ { 0 }$ ，使用式(27)得到锚点初值 ${ \bf c } = ( \pmb { \mu } _ { 0 } + \pmb { \mu } _ { 1 } ) / 2$ 。

步4，指定焦点 $F _ { 0 }$ 、 $F _ { 1 }$ 。按照第 4节的规定， $F _ { 1 }$ 的取值范围是 $( \ln ( 3 ) , + \infty )$ ，一个典型值是 $F _ { 1 } = 1 . 5$ ；指定系数 $\mathbf { \Psi } _ { r } $ 的值，按照第4节的规定， $r$ 的取值范围是 $[ 0 , \pi / ( 2 G _ { 1 } - 1 ) ]$ ，一个典型值是 $r = ( 1 - G _ { 0 } ) / G _ { 0 }$ 。指定最速下降法的下降步长 $s$ ，这个值可以随意指定，例如$s = 0 . 1$ ，但不可太大，否则可能导致迭代不收敛。指定收敛阈值 $\tau$ ，这个值也可以随意指定为一个正数，例如 $\tau = 1 0 ^ { - 5 }$ 。令迭代计数器 $k = 0$ ，损失值 $\mathrm { L o s s 0 { = } 1 }$ 。

步5，法向量赋初值：用式(28)得到单位向量 $\mathbf { n }$ ，用式(29)给法向量 $\mathbf { w }$ 指定初值。

步6，用式(30)计算标准差比例 $\eta$ 。

现在开始最速度下降法迭代。

步7，对样本集 $D$ 中的所有样本作对焦变换，即用（5）计算 $z _ { i } = \mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) + b , i =$ $1 , 2 , \ldots , m$ 。

步8，用式(32)或(33)修正 $\{ z _ { i } | i = 1 , 2 , \dots , m \}$ 得到 $\{ \bar { z } _ { i } | i = 1 , 2 , \dots , m \}$ 0

步9，计算损失函数值：用 $\bar { z } _ { i }$ 代替式（7）中的 $z _ { i }$ ，记 $\mathrm { L o s s 1 } = H ( \mathbf { w } , b )$ 。如果 $\mathrm { L o s s 0 - }$ Loss1 $< \tau$ ，那么跳转至步11；否则，令 $\mathrm { L o s s 0 = L o s s 1 }$ 。

步10，参数更新，使用式(11)(12)计算

$$
\mathbf { w } = \mathbf { w } + s \frac { \partial H ( \mathbf { w } , b ) } { \partial \mathbf { w } } , \quad b = b + s \frac { \partial H ( \mathbf { w } , b ) } { \partial b } ,
$$

跳转至步7。

步11，计算样本集 $D$ 上的分类正确率：对任意样本 ${ \bf x } _ { j }$ ，用(9)计算 $z _ { j }$ ，然后用式(32)或(33)做标准差计整得到 $\bar { z } _ { j }$ ，用式(10)推测样本 $\mathbf { x } _ { j }$ 是正样本或负样本；统计所有样本的推测结果，得到正确率。结束。

# 8 数值实验

对焦回归的设计目标是解决逻辑回归所面临的问题，因此本节对比二者的分类正确率、初值优劣、收敛速度、法向量模长。

MNIST[12]数据库是典型的分类数据集，它包含数字 $0 ^ { \sim } 9$ 的手写图像，6万个图像用于训练，1万个图像用于测试。将数字 $0 ^ { \sim } 9$ 的图像分别抽取出来，形成10个训练子集和10个测试子集。

由MNIST官网知道，目前还没有方法能将MNIST完全正确地分类，从而可以认为MNIST不是线性可分的。由定理5知道，这种情形下逻辑回归的法向量有界，因此不使用正则化措施。最速下降法的下降步长指定为0.1，迭代次数设为2000，法向量 $\mathbf { w }$ 的每个元素都按照服从均匀分布 $U ( - 1 / 7 8 4 , 1 / 7 8 4 )$ 来选取初值，截距 $\textit { b }$ 按照服从均匀分布 $U ( - 1 , 1 )$ 来选取初值。

用对焦分类计算时，指定焦点为 $F _ { 1 } = 1 . 5$ ， $F _ { 0 } = - 1 . 5$ ， $r = ( 1 - G _ { 0 } ) / G _ { 0 }$ ，指定最速下降法的下降步长为 $s = 0 . 1$ 。

# 8.1 分类正确率

用分类正确的样本数量除以样本总量就得到分类正确率。逻辑回归在训练集上的正确率见表1，正确率均值为 $9 8 . 7 1 9 1 \%$ ；逻辑回归在测试集上的正确率见表2，正确率均值为$9 8 . 6 7 3 0 \%$ 。

表1：逻辑回归在MNIST训练集上的正确率%  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>99.87</td><td>1</td><td></td><td></td><td>-</td><td></td><td></td><td>-</td><td></td></tr><tr><td>2</td><td>99.00</td><td>99.08</td><td>-</td><td>-</td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>3</td><td>99.43</td><td>99.09</td><td>97.38</td><td>1</td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>4</td><td>99.65</td><td>99.62</td><td>98.58</td><td>99.46</td><td>1</td><td></td><td>-</td><td>-</td><td></td></tr><tr><td>5</td><td>98.66</td><td>99.48</td><td>98.10</td><td>96.03</td><td>98.99</td><td>1</td><td>-</td><td>-</td><td></td></tr><tr><td>6</td><td>99.21</td><td>99.76</td><td>98.36</td><td>99.48</td><td>99.12</td><td>98.08</td><td>一</td><td>-</td><td>-</td></tr><tr><td>7</td><td>99.69</td><td>99.48</td><td>98.69</td><td>98.69</td><td>98.88</td><td>99.33</td><td>99.86</td><td>1</td><td>-</td></tr><tr><td>8</td><td>99.29</td><td>98.21</td><td>97.46</td><td>97.02</td><td>99.26</td><td>96.27</td><td>98.99</td><td>99.06</td><td>1</td></tr><tr><td>9</td><td>99.52</td><td>99.52</td><td>98.80</td><td>98.37</td><td>96.89</td><td>98.70</td><td>99.81</td><td>95.91</td><td>98.24</td></tr></table></body></html>

表2：逻辑回归在MNIST测试集上的正确率%  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>99.95</td><td>-</td><td></td><td></td><td>-</td><td></td><td></td><td>-</td><td></td></tr><tr><td>2</td><td>99.11</td><td>99.31</td><td></td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>3</td><td>99.75</td><td>99.63</td><td>97.65</td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>4</td><td>99.85</td><td>99.91</td><td>98.46</td><td>99.60</td><td>1</td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>5</td><td>98.99</td><td>99.61</td><td>97.97</td><td>96.27</td><td>99.20</td><td>1</td><td>-</td><td>-</td><td>-</td></tr><tr><td>6</td><td>98.97</td><td>99.57</td><td>98.34</td><td>99.39</td><td>98.81</td><td>98.05</td><td>-</td><td>-</td><td>-</td></tr><tr><td>7</td><td>99.60</td><td>99.21</td><td>97.96</td><td>98.04</td><td>98.91</td><td>99.22</td><td>99.60</td><td>1</td><td>-</td></tr><tr><td>8</td><td>99.39</td><td>98.91</td><td>97.31</td><td>96.93</td><td>99.34</td><td>95.82</td><td>98.81</td><td>98.10</td><td>1</td></tr><tr><td>9</td><td>99.30</td><td>99.53</td><td>98.68</td><td>98.27</td><td>97.04</td><td>98.42</td><td>99.69</td><td>96.07</td><td>97.78</td></tr></table></body></html>

这些表格里，第1行中的数字 $\phantom { - } 0 ^ { - } 8$ 表示正样本对应的数字，第1列中的数字 $1 ^ { \sim } 9$ 表示负样本对应的数字。 $+ 1$ 对角线上的位置表示正负样本用同一个数字的图像，无意义，不需要计算；右上角部分与左下角部分对称，故不再列出数值，用"-"代替。

对焦分类在训练集上的正确率见表3，正确率均值为为 $9 9 . 0 2 0 4 \%$ ；对焦分类在测试集上的正确率见表4，正确率均值为 $9 9 . 0 8 2 5 \%$ 。

用对焦分类正确率减去逻辑回归的正确率，得到表5和表6。在训练集样本上和测试样本集上，对焦分类的平均正确率比逻辑回归的平均正确率分别高 $0 . 3 0 0 7 \%$ 和 $0 . 4 0 9 5 \%$ 。

# 8.2 初值优劣

逻辑回归的初始值随机选取，导致初始正确率不高，见表7，正确率均值为 $4 9 . 2 7 \%$ ，等效于随机推测样本是正样本或是负样本。

表3：对焦分类在MNIST训练集上的正确率 $\%$   

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>99.98</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td>-</td><td></td></tr><tr><td>2</td><td>99.34</td><td>99.61</td><td>-</td><td>-</td><td>-</td><td></td><td>-</td><td>-</td><td></td></tr><tr><td>3</td><td>99.76</td><td>99.68</td><td>97.12</td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>4</td><td>99.96</td><td>99.88</td><td>99.65</td><td>99.72</td><td>-</td><td></td><td></td><td>-</td><td></td></tr><tr><td>5</td><td>99.77</td><td>99.62</td><td>98.42</td><td>95.80</td><td>99.24</td><td>1</td><td>-</td><td>-</td><td></td></tr><tr><td>6</td><td>99.70</td><td>99.96</td><td>98.51</td><td>99.15</td><td>99.29</td><td>97.99</td><td>一</td><td>-</td><td>-</td></tr><tr><td>7</td><td>99.98</td><td>99.91</td><td>99.21</td><td>99.31</td><td>99.12</td><td>99.49</td><td>99.89</td><td>1</td><td>-</td></tr><tr><td>8</td><td>99.67</td><td>99.63</td><td>98.25</td><td>96.44</td><td>99.48</td><td>98.86</td><td>98.34</td><td>98.65</td><td>1</td></tr><tr><td>9</td><td>99.72</td><td>99.79</td><td>99.48</td><td>98.95</td><td>96.89</td><td>98.29</td><td>99.79</td><td>96.09</td><td>98.53</td></tr></table></body></html>

表4：对焦分类在MNIST测试集上的正确率%  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>100.00</td><td>-</td><td></td><td></td><td>一</td><td></td><td>-</td><td>一</td><td>-</td></tr><tr><td>2</td><td>99.25</td><td>99.77</td><td>1</td><td></td><td>-</td><td></td><td>-</td><td></td><td>-</td></tr><tr><td>3</td><td>99.90</td><td>99.86</td><td>97.99</td><td>-</td><td></td><td></td><td>-</td><td>-</td><td>-</td></tr><tr><td>4</td><td>99.95</td><td>100.00</td><td>99.70</td><td>99.80</td><td>1</td><td></td><td></td><td>-</td><td>-</td></tr><tr><td>5</td><td>99.79</td><td>99.85</td><td>98.80</td><td>96.90</td><td>99.41</td><td></td><td>-</td><td>-</td><td>-</td></tr><tr><td>6</td><td>99.90</td><td>99.90</td><td>98.34</td><td>99.49</td><td>99.28</td><td>97.73</td><td>1</td><td></td><td>-</td></tr><tr><td>7</td><td>99.85</td><td>100.00</td><td>98.64</td><td>98.77</td><td>99.30</td><td>99.43</td><td>99.85</td><td>1</td><td>-</td></tr><tr><td>8</td><td>99.69</td><td>99.86</td><td>98.65</td><td>96.62</td><td>99.39</td><td>98.66</td><td>98.40</td><td>98.15</td><td>1</td></tr><tr><td>9</td><td>99.65</td><td>99.95</td><td>99.41</td><td>98.96</td><td>97.09</td><td>98.32</td><td>99.75</td><td>96.37</td><td>98.34</td></tr></table></body></html>

表5：对焦分类正确率减去逻辑回归正确率% (训练)  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>0.1184</td><td>1</td><td></td><td></td><td></td><td>-</td><td></td><td></td><td></td></tr><tr><td>2</td><td>0.3367</td><td>0.5354</td><td>-</td><td></td><td>-</td><td></td><td>-</td><td>-</td><td></td></tr><tr><td>3</td><td>0.3318</td><td>0.5904</td><td>-0.2564</td><td></td><td>-</td><td></td><td>1</td><td></td><td></td></tr><tr><td>4</td><td>0.3060</td><td>0.2622</td><td>1.0678</td><td>0.2673</td><td>1</td><td></td><td>-</td><td>-</td><td>1</td></tr><tr><td>5</td><td>1.1107</td><td>0.1398</td><td>0.3164</td><td>-0.2251</td><td>0.2486</td><td>1</td><td></td><td>-</td><td></td></tr><tr><td>6</td><td>0.4898</td><td>0.1975</td><td>0.1516</td><td>-0.3237</td><td>0.1616</td><td>-0.0882</td><td>1</td><td>-</td><td></td></tr><tr><td>7</td><td>0.2954</td><td>0.4305</td><td>0.5236</td><td>0.6131</td><td>0.2478</td><td>0.1540</td><td>0.0246</td><td>1</td><td>-</td></tr><tr><td>8</td><td>0.3822</td><td>1.4214</td><td>0.7875</td><td>-0.5759</td><td>0.2138</td><td>2.5905</td><td>-0.6458</td><td>-0.4127</td><td>1</td></tr><tr><td>9</td><td>0.2022</td><td>0.2679</td><td>0.6803</td><td>0.5795</td><td>0</td><td>-0.4046</td><td>-0.0253</td><td>0.1801</td><td>0.2881</td></tr></table></body></html>

表6：对焦分类正确率减去逻辑回归正确率% (测试)  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>0.0473</td><td>1</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>2</td><td>0.1491</td><td>0.4615</td><td>-</td><td></td><td></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>3</td><td>0.1508</td><td>0.2331</td><td>0.3428</td><td>1</td><td>-</td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>4</td><td>0.1019</td><td>0.0945</td><td>1.2413</td><td>0.2008</td><td>1</td><td>-</td><td>-</td><td>1</td><td></td></tr><tr><td>5</td><td>0.8013</td><td>0.2467</td><td>0.8316</td><td>0.6309</td><td>0.2134</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>6</td><td>0.9288</td><td>0.3344</td><td>0</td><td>0.1016</td><td>0.4639</td><td>-0.3243</td><td>1</td><td>-</td><td>-</td></tr><tr><td>7</td><td>0.2490</td><td>0.7859</td><td>0.6796</td><td>0.7360</td><td>0.3980</td><td>0.2083</td><td>0.2518</td><td>1</td><td>-</td></tr><tr><td>8</td><td>0.3071</td><td>0.9483</td><td>1.3460</td><td>-0.3024</td><td>0.0511</td><td>2.8403</td><td>-0.4141</td><td>0.0499</td><td>-</td></tr><tr><td>9</td><td>0.3519</td><td>0.4198</td><td>0.7349</td><td>0.6934</td><td>0.0502</td><td>-0.1052</td><td>0.0508</td><td>0.2946</td><td>0.5547</td></tr></table></body></html>

表7：逻辑回归在训练集上的初始正确率%  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>46.77</td><td>1</td><td></td><td></td><td>-</td><td></td><td></td><td>-</td><td></td></tr><tr><td>2</td><td>49.85</td><td>46.91</td><td>-</td><td>-</td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>3</td><td>50.86</td><td>47.63</td><td>49.28</td><td>-</td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>4</td><td>49.66</td><td>46.42</td><td>50.49</td><td>48.79</td><td>1</td><td>-</td><td></td><td>-</td><td>1</td></tr><tr><td>5</td><td>52.21</td><td>44.57</td><td>47.64</td><td>46.93</td><td>51.87</td><td>1</td><td>-</td><td>-</td><td></td></tr><tr><td>6</td><td>45.95</td><td>46.75</td><td>50.17</td><td>49.12</td><td>49.68</td><td>47.81</td><td>1</td><td>-</td><td>-</td></tr><tr><td>7</td><td>51.16</td><td>51.83</td><td>48.74</td><td>49.46</td><td>48.25</td><td>53.61</td><td>51.42</td><td>1</td><td></td></tr><tr><td>8</td><td>49.69</td><td>46.46</td><td>50.45</td><td>51.17</td><td>49.96</td><td>51.91</td><td>49.72</td><td>48.29</td><td>1</td></tr><tr><td>9</td><td>50.11</td><td>46.88</td><td>49.96</td><td>49.25</td><td>50.07</td><td>47.68</td><td>49.87</td><td>51.29</td><td>50.42</td></tr></table></body></html>

表8：对焦分类在训练集上的初始正确率 $\%$   

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>99.94</td><td>1</td><td></td><td></td><td>-</td><td></td><td>一</td><td>-</td><td></td></tr><tr><td>2</td><td>98.23</td><td>99.02</td><td>-</td><td>-</td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>3</td><td>98.68</td><td>99.48</td><td>93.56</td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>4</td><td>99.80</td><td>99.66</td><td>99.00</td><td>99.11</td><td>1</td><td></td><td>-</td><td>-</td><td></td></tr><tr><td>5</td><td>97.97</td><td>99.05</td><td>96.91</td><td>87.27</td><td>97.13</td><td>1</td><td>-</td><td>-</td><td></td></tr><tr><td>6</td><td>98.28</td><td>99.64</td><td>95.36</td><td>98.23</td><td>97.91</td><td>95.96</td><td>一</td><td>-</td><td></td></tr><tr><td>7</td><td>99.58</td><td>99.71</td><td>97.59</td><td>98.47</td><td>97.60</td><td>98.05</td><td>99.32</td><td>1</td><td>-</td></tr><tr><td>8</td><td>98.71</td><td>98.62</td><td>96.44</td><td>88.94</td><td>97.55</td><td>96.86</td><td>97.33</td><td>96.87</td><td>1</td></tr><tr><td>9</td><td>99.00</td><td>99.53</td><td>98.29</td><td>97.64</td><td>89.40</td><td>95.88</td><td>99.28</td><td>92.42</td><td>95.86</td></tr></table></body></html>

表9：对焦分类的锚点与最优锚点的相对距离%  

<html><body><table><tr><td>负-正</td><td>0</td><td>1 2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>-8.42</td><td>1</td><td>-</td><td></td><td>-</td><td>-</td><td>- -</td><td></td></tr><tr><td>2</td><td>-3.89</td><td>12.47</td><td>-</td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>3</td><td>-5.10</td><td>9.52</td><td>-1.38</td><td>- -</td><td>一</td><td></td><td></td><td></td></tr><tr><td>4</td><td>-6.94</td><td>5.49</td><td>-6.85</td><td>-3.13</td><td>-</td><td>-</td><td></td><td></td></tr><tr><td>5</td><td>-8.83</td><td>7.10</td><td>-2.26</td><td>2.13</td><td>2.56 -</td><td>-</td><td>-</td><td>-</td></tr><tr><td>6</td><td>-5.05</td><td>8.30</td><td>-2.66</td><td>-1.09</td><td>2.16 0.53</td><td></td><td>-</td><td></td></tr><tr><td>7</td><td>-6.50</td><td>6.90</td><td>-3.95</td><td>-4.31</td><td>1.35 -3.18</td><td>-1.59</td><td>1</td><td></td></tr><tr><td>8</td><td>-4.55</td><td>12.35</td><td>-4.03</td><td>1.50</td><td>2.89 9.99</td><td>0.49</td><td>2.36</td><td>1</td></tr><tr><td>9</td><td>-5.15</td><td>5.00</td><td>-4.23</td><td>-5.05</td><td>-4.13</td><td>-1.24</td><td>-1.41 -0.07</td><td>-4.99</td></tr></table></body></html>

对焦回归的初始值选择有明确的理论指导，导致初始正确率较高，见表8，平均为$9 7 . 3 1 \%$ 。

由式(16)知，锚点 $\mathbf { c }$ 与最优锚点的之间绝对距离为 $\hat { b } / | \hat { \mathbf { w } } |$ ，相对距离可以用绝对距离与 $| \pmb { \mu } _ { 1 } - \pmb { \mu } _ { 0 } | / 2$ 之间的比值表示，即

$$
\frac { 2 \hat { b } } { | \hat { \mathbf { w } } | | \pmb { \mu } _ { 1 } - \pmb { \mu } _ { 0 } | } .
$$

训练集上的相对距离列在表9，平均值为- $. 0 . 3 7 5 1 \%$ ，可见锚点的选取十分精确。

# 8.3 收敛速度

用2个指标来衡量收敛速度：达到最高正确率的 $9 9 \%$ 和最高正确率的 $9 9 . 9 \%$ 所需要的迭代次数。之所以不用达到最高正确率所需的迭代次数，是因为在最高点附近几乎都会发生

表10:逻辑回归 $9 9 \%$ 分位迭代次数  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>2</td><td>-</td><td></td><td></td><td>一</td><td></td><td></td><td>一</td><td></td></tr><tr><td>2</td><td>96</td><td>74</td><td>一</td><td></td><td></td><td>-</td><td></td><td>一</td><td></td></tr><tr><td>3</td><td>76</td><td>66</td><td>122</td><td>-</td><td></td><td>-</td><td></td><td>一</td><td></td></tr><tr><td>4</td><td>2</td><td>19</td><td>51</td><td>34</td><td></td><td></td><td></td><td>一</td><td></td></tr><tr><td>5</td><td>141</td><td>81</td><td>93</td><td>380</td><td>102</td><td></td><td></td><td>一</td><td></td></tr><tr><td>6</td><td>68</td><td>35</td><td>269</td><td>53</td><td>21</td><td>120</td><td></td><td></td><td>-</td></tr><tr><td>7</td><td>24</td><td>85</td><td>177</td><td>143</td><td>133</td><td>32</td><td>2</td><td>-</td><td></td></tr><tr><td>8</td><td>76</td><td>166</td><td>216</td><td>256</td><td>79</td><td>469</td><td>50</td><td>121</td><td>一</td></tr><tr><td>9</td><td>55</td><td>25</td><td>101</td><td>258</td><td>369</td><td>122</td><td>9</td><td>381</td><td>271</td></tr></table></body></html>

表11:逻辑回归 $9 9 . 9 \%$ 分位迭代次数  

<html><body><table><tr><td>负-正</td><td>0</td><td>1 2</td><td></td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>268</td><td>1</td><td></td><td></td><td></td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>2</td><td>1275</td><td>1222</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td><td></td><td>-</td></tr><tr><td>3</td><td>1110</td><td>1200</td><td>1253</td><td>-</td><td></td><td></td><td>-</td><td></td><td></td></tr><tr><td>4</td><td>474</td><td>847</td><td>1202</td><td>970</td><td></td><td></td><td></td><td></td><td>-</td></tr><tr><td>5</td><td>1515</td><td>1379</td><td>1238</td><td>1481</td><td>1121</td><td>1</td><td>-</td><td></td><td></td></tr><tr><td>6</td><td>1120</td><td>1073</td><td>1502</td><td>1011</td><td>745</td><td>1487</td><td>1</td><td>-</td><td>-</td></tr><tr><td>7</td><td>691</td><td>1119</td><td>1406</td><td>1019</td><td>1021</td><td>1118</td><td>335</td><td>1</td><td></td></tr><tr><td>8</td><td>1113</td><td>1482</td><td>1514</td><td>1523</td><td>1336</td><td>1568</td><td>1289</td><td>1265</td><td></td></tr><tr><td>9</td><td>800</td><td>699</td><td>1133</td><td>1554</td><td>1792</td><td>1337</td><td>541</td><td>1733</td><td>1680</td></tr></table></body></html>

微小振荡，随机性强，难以正确反映算法的特性。

逻辑回归的 $9 9 \%$ 分位迭代次数列在表10，平均值为122.78；逻辑回归的 $9 9 . 9 \%$ 分位迭代次数列在表11，平均值为1168.02。

对焦分类的 $9 9 \%$ 分位迭代次数列在表12，平均值为23.69；对焦分类的 $9 9 . 9 \%$ 分位迭代次数列在表13，平均值为361.16.

由表 $1 0 ^ { \sim } 1 3$ 易知，对焦分类的收敛速度比逻辑回归快很多。

逻辑回归的截距b的初值列在表14，平均值为0.0513；迭代2000 次之后截距b的终值列在表15，平均值为0.0941；可以将截距b的初值与终值差的绝对值称为接近度，接近度越小越好，逻辑回归的接近度均值为0.3710。

对焦回归的离心距b 初值为0，迭代 2000 次之后离心距b 的值列在表 16，平均值为-0.0069，接近度平均值为0.0737。与逻辑回归相比，对焦回归的初值更接近终值，更好。

表12:对焦分类 $9 9 \%$ 分位迭代次数  

<html><body><table><tr><td>负-正</td><td>0 1</td><td>2</td><td></td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>0</td><td>-</td><td></td><td>-</td><td></td><td></td><td>一</td><td></td><td></td></tr><tr><td>2</td><td>2</td><td>0</td><td>-</td><td>-</td><td>一</td><td></td><td>一</td><td></td><td>一</td></tr><tr><td>3</td><td>2</td><td>0</td><td>41</td><td></td><td>-</td><td></td><td>一</td><td></td><td>一</td></tr><tr><td>4</td><td>0</td><td>0</td><td>0</td><td>0</td><td>-</td><td></td><td>一</td><td>一</td><td>一</td></tr><tr><td>5</td><td>8</td><td>0</td><td>8</td><td>263</td><td>17</td><td>一</td><td></td><td>-</td><td>一</td></tr><tr><td>6</td><td>3</td><td>0</td><td>108</td><td>0</td><td>6</td><td>16</td><td>一</td><td>-</td><td></td></tr><tr><td>7</td><td>0</td><td>0</td><td>12</td><td>0</td><td>13</td><td>13</td><td>0</td><td></td><td></td></tr><tr><td>8</td><td>0</td><td>1</td><td>16</td><td>123</td><td>18</td><td>25</td><td>1</td><td>29</td><td>1</td></tr><tr><td>9</td><td>0</td><td>0</td><td>3</td><td>6</td><td>61</td><td>27</td><td>0</td><td>198</td><td>46</td></tr></table></body></html>

表13：对焦分类 $9 9 \%$ 分位迭代次数  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>0</td><td>-</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>2</td><td>102</td><td>41</td><td></td><td></td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>3</td><td>95</td><td>108</td><td>325</td><td>-</td><td></td><td>-</td><td></td><td></td><td></td></tr><tr><td>4</td><td>19</td><td>30</td><td>100</td><td>69</td><td>-</td><td>-</td><td></td><td></td><td></td></tr><tr><td>5</td><td>124</td><td>154</td><td>51</td><td>1709</td><td>164</td><td>1</td><td></td><td>-</td><td></td></tr><tr><td>6</td><td>236</td><td>134</td><td>1303</td><td>150</td><td>189</td><td>414</td><td>-</td><td>-</td><td></td></tr><tr><td>7</td><td>112</td><td>55</td><td>340</td><td>184</td><td>1025</td><td>731</td><td>161</td><td>-</td><td></td></tr><tr><td>8</td><td>109</td><td>99</td><td>185</td><td>1243</td><td>418</td><td>296</td><td>97</td><td>628</td><td></td></tr><tr><td>9</td><td>285</td><td>68</td><td>90</td><td>691</td><td>418</td><td>1268</td><td>230</td><td>1228</td><td>774</td></tr></table></body></html>

表14：逻辑回归截距b初值  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>.8560</td><td>-</td><td>-</td><td>-</td><td>-</td><td>1</td><td>-</td><td>-</td><td></td></tr><tr><td>2</td><td>.2500</td><td>-.1306</td><td>1</td><td>-</td><td>-</td><td></td><td>-</td><td>-</td><td></td></tr><tr><td>3</td><td>-.2662</td><td>-.3966</td><td>-.3327</td><td>1</td><td>-</td><td></td><td>-</td><td>-</td><td>1</td></tr><tr><td>4</td><td>.4788</td><td>.2850</td><td>.0470</td><td>.8713</td><td>1</td><td></td><td>-</td><td>-</td><td></td></tr><tr><td>5</td><td>.3807</td><td>.6325</td><td>-.2973</td><td>-.3549</td><td>-.9653</td><td>1</td><td>-</td><td></td><td></td></tr><tr><td>6</td><td>.9041</td><td>-.1027</td><td>-.5404</td><td>.9929</td><td>-.2355</td><td>.3973</td><td>1</td><td>-</td><td>-</td></tr><tr><td>7</td><td>-.7932</td><td>-.5697</td><td>-.8572</td><td>.5080</td><td>.0098</td><td>-.3679</td><td>.2959</td><td>1</td><td></td></tr><tr><td>8</td><td>-.8116</td><td>.4658</td><td>.9810</td><td>-.0130</td><td>.1991</td><td>.9828</td><td>.7160</td><td>.8654</td><td>1</td></tr><tr><td>9</td><td>-.1333</td><td>-.4223</td><td>-.6506</td><td>-.9309</td><td>.1562</td><td>.8105</td><td>.1012</td><td>-.1354</td><td>-.5732</td></tr></table></body></html>

表15：逻辑回归2000次迭代后的截距b  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>.4280</td><td>1</td><td>-</td><td>-</td><td>-</td><td></td><td></td><td>-</td><td></td></tr><tr><td>2</td><td>-.1410</td><td>.2158</td><td>1</td><td>-</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td></tr><tr><td>3</td><td>-.4141</td><td>-.0962</td><td>.1157</td><td>1</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td></tr><tr><td>4</td><td>.1230</td><td>.3888</td><td>.0514</td><td>.5935</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td></tr><tr><td>5</td><td>-.8248</td><td>.4153</td><td>-.7692</td><td>-1.0776</td><td>-1.2000</td><td>1</td><td>-</td><td>-</td><td></td></tr><tr><td>6</td><td>.4611</td><td>.1806</td><td>-.0488</td><td>.7307</td><td>.0464</td><td>1.0269</td><td>1</td><td>-</td><td></td></tr><tr><td>7</td><td>-1.1317</td><td>-.3160</td><td>-.8410</td><td>-.1229</td><td>-.2266</td><td>-.2077</td><td>.0680</td><td>1</td><td>-</td></tr><tr><td>8</td><td>-.6578</td><td>1.0086</td><td>1.3943</td><td>.6378</td><td>.6047</td><td>2.5445</td><td>.8359</td><td>1.3909</td><td></td></tr><tr><td>9</td><td>-.3167</td><td>-.2194</td><td>-.5657</td><td>-.8159</td><td>.3086</td><td>1.1756</td><td>.0268</td><td>.5616</td><td>-1.1064</td></tr></table></body></html>

表16：对焦分类2000次迭代后的离心距b  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>-.1480</td><td></td><td></td><td></td><td>-</td><td></td><td>-</td><td></td><td></td></tr><tr><td>2</td><td>-.0639</td><td>.2044</td><td>1</td><td>-</td><td>-</td><td></td><td>-</td><td></td><td>1</td></tr><tr><td>3</td><td>-.0833</td><td>.1574</td><td>-.0212</td><td>-</td><td>-</td><td>-</td><td>-</td><td></td><td></td></tr><tr><td>4</td><td>-.1123</td><td>.1007</td><td>-.1024</td><td>-.0523</td><td>1</td><td>-</td><td>-</td><td></td><td>-</td></tr><tr><td>5</td><td>-.1348</td><td>.1247</td><td>-.0352</td><td>.0285</td><td>.0403</td><td>1</td><td></td><td></td><td>1</td></tr><tr><td>6</td><td>-.0893</td><td>.1416</td><td>-.0423</td><td>-.0197</td><td>.0346</td><td>.0089</td><td>1</td><td></td><td></td></tr><tr><td>7</td><td>-.1194</td><td>.1226</td><td>-.0755</td><td>-.0772</td><td>.0189</td><td>-.0531</td><td>-.0294</td><td>1</td><td>-</td></tr><tr><td>8</td><td>-.0749</td><td>.1900</td><td>-.0563</td><td>.0212</td><td>.0447</td><td>.1246</td><td>.0086</td><td>.0421</td><td>1</td></tr><tr><td>9</td><td>-.0926</td><td>.0889</td><td>-.0756</td><td>-.0841</td><td>-.0518</td><td>-.0187</td><td>-.0226</td><td>-.0009</td><td>-.0772</td></tr></table></body></html>

表17：逻辑回归初始法向量模长  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>.0210</td><td>-</td><td></td><td></td><td>-</td><td></td><td></td><td>-</td><td>-</td></tr><tr><td>2</td><td>.0205</td><td>.0204</td><td></td><td>-</td><td>-</td><td></td><td></td><td>-</td><td>1</td></tr><tr><td>3</td><td>.0204</td><td>.0207</td><td>.0210</td><td>1</td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>4</td><td>.0205</td><td>.0209</td><td>.0207</td><td>.0201</td><td>1</td><td></td><td></td><td></td><td>1</td></tr><tr><td>5</td><td>.0207</td><td>.0204</td><td>.0206</td><td>.0208</td><td>.0209</td><td>1</td><td></td><td>-</td><td>-</td></tr><tr><td>6</td><td>.0212</td><td>.0200</td><td>.0209</td><td>.0212</td><td>.0208</td><td>.0204</td><td>1</td><td>-</td><td></td></tr><tr><td>7</td><td>.0212</td><td>.0205</td><td>.0211</td><td>.0204</td><td>.0209</td><td>.0204</td><td>.0209</td><td>1</td><td></td></tr><tr><td>8</td><td>.0202</td><td>.0203</td><td>.0209</td><td>.0209</td><td>.0201</td><td>.0209</td><td>.0203</td><td>.0204</td><td>1</td></tr><tr><td>9</td><td>.0208</td><td>.0209</td><td>.0209</td><td>.0196</td><td>.0204</td><td>.0205</td><td>.0200</td><td>.0202</td><td>.0214</td></tr></table></body></html>

表18：逻辑回归2000次迭代后的法向量模长  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>2.7713</td><td>-</td><td>-</td><td></td><td>-</td><td></td><td></td><td></td><td>-</td></tr><tr><td>2</td><td>3.5602</td><td>3.8066</td><td>1</td><td>-</td><td></td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>3</td><td>3.5543</td><td>3.5001</td><td>3.6743</td><td></td><td>-</td><td>-</td><td>-</td><td>-</td><td></td></tr><tr><td>4</td><td>3.1414</td><td>3.2576</td><td>3.5991</td><td>3.6558</td><td>1</td><td></td><td>-</td><td>-</td><td></td></tr><tr><td>5</td><td>4.0163</td><td>3.8027</td><td>3.7661</td><td>4.5227</td><td>4.1154</td><td></td><td></td><td>-</td><td>-</td></tr><tr><td>6</td><td>3.6352</td><td>3.4458</td><td>4.2158</td><td>3.7039</td><td>3.7896</td><td>3.8219</td><td>1</td><td>-</td><td>-</td></tr><tr><td>7</td><td>3.2619</td><td>3.6135</td><td>3.5932</td><td>3.5840</td><td>4.1163</td><td>4.0012</td><td>3.3663</td><td>1</td><td>-</td></tr><tr><td>8</td><td>3.3878</td><td>3.8553</td><td>3.9169</td><td>4.1160</td><td>4.0820</td><td>4.1455</td><td>3.7295</td><td>3.8305</td><td>1</td></tr><tr><td>9</td><td>3.2914</td><td>3.4038</td><td>3.7502</td><td>3.8728</td><td>5.0291</td><td>4.2215</td><td>3.5780</td><td>4.2077</td><td>4.2341</td></tr></table></body></html>

# 8.4 法向量模长

逻辑回归初始法向量模长列在表17，平均值为0.0206；逻辑回归在 2000 次迭代后的法向量模长列在表18，平均值为3.7677。对焦分类初始法向量模长列在表19，平均值为0.6546；对焦分类在 2000 次迭代后的法向量模长列在表20，平均值为0.6964，相对于初始值，仅增长了 $6 . 3 9 \%$

观察这些模长数据可知，逻辑回归的法向量模长较大；对焦分类的法向量模长较小，增长缓慢，极有可能是有界的，支持了定理3。

表19:对焦分类初始法向量模长  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>.3967</td><td>-</td><td></td><td>-</td><td>-</td><td></td><td></td><td></td><td>-</td></tr><tr><td>2</td><td>.5333</td><td>.5923</td><td></td><td></td><td>一</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>3</td><td>.5368</td><td>.5845</td><td>.6829</td><td>-</td><td></td><td></td><td>一</td><td></td><td>-</td></tr><tr><td>4</td><td>.4805</td><td>.5300</td><td>.6338</td><td>.5710</td><td>-</td><td>-</td><td></td><td></td><td></td></tr><tr><td>5</td><td>.6617</td><td>.6209</td><td>.6628</td><td>.9628</td><td>.7283</td><td>-</td><td></td><td>-</td><td>-</td></tr><tr><td>6</td><td>.5277</td><td>.5280</td><td>.7594</td><td>.5586</td><td>.6998</td><td>.6869</td><td>-</td><td>-</td><td>-</td></tr><tr><td>7</td><td>.4724</td><td>.5587</td><td>.5589</td><td>.5735</td><td>.7453</td><td>.6713</td><td>.5296</td><td>1</td><td>-</td></tr><tr><td>8</td><td>.5345</td><td>.6299</td><td>.7802</td><td>.8272</td><td>.6909</td><td>.9666</td><td>.6410</td><td>.6261</td><td>1</td></tr><tr><td>9</td><td>.4856</td><td>.5647</td><td>.6077</td><td>.6274</td><td>1.2074</td><td>.7963</td><td>.6358</td><td>1.0045</td><td>.7839</td></tr></table></body></html>

表20：对焦分类2000次迭代后的法向量模长  

<html><body><table><tr><td>负-正</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td></tr><tr><td>1</td><td>.4648</td><td>1</td><td></td><td></td><td>-</td><td>-</td><td></td><td></td><td>-</td></tr><tr><td>2</td><td>.5842</td><td>.6473</td><td>1</td><td>-</td><td>-</td><td>-</td><td></td><td>-</td><td></td></tr><tr><td>3</td><td>.5841</td><td>.6444</td><td>.7002</td><td>1</td><td>-</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>4</td><td>.5188</td><td>.6487</td><td>.6314</td><td>.6370</td><td>1</td><td>-</td><td>1</td><td></td><td>-</td></tr><tr><td>5</td><td>.6730</td><td>.7267</td><td>.6897</td><td>.8589</td><td>.7653</td><td>1</td><td>1</td><td></td><td>-</td></tr><tr><td>6</td><td>.6214</td><td>.6004</td><td>.8046</td><td>.6716</td><td>.7462</td><td>.7694</td><td>1</td><td>-</td><td>-</td></tr><tr><td>7</td><td>.5788</td><td>.6618</td><td>.7128</td><td>.6858</td><td>.6974</td><td>.7457</td><td>.6515</td><td>1</td><td>-</td></tr><tr><td>8</td><td>.5867</td><td>.6459</td><td>.7270</td><td>.7805</td><td>.7135</td><td>.8035</td><td>.7423</td><td>.7464</td><td>1</td></tr><tr><td>9</td><td>.5815</td><td>.6699</td><td>.7236</td><td>.6969</td><td>1.0099</td><td>.8020</td><td>.6823</td><td>.8944</td><td>.8078</td></tr></table></body></html>

![](images/43c1ef2c2bc7b66008c529e20a643744c5a049d0e00e6b9295347b40bb3b8275.jpg)  
图7：逻辑回归：单样本损失函数的导数 $l ( z _ { i } )$ 。

# 9总结

本文设计的对焦分类方法解决了逻辑回归面临的2个困难：法向量模长过大、初值不准，并提供了理论证明和直观的几何解释性。虽然无法保证控制法向量模长一定能够缓解过拟合现象，但仍然可以在有过拟合现象的数据集测试对焦分类的表现。

后续工作可以去证明定理3，将对焦分类并行化。

# 10 附录

为证明逻辑回归的法向无限定理和法向有界定理，先考查损失函数的导数。

由式 (3)得

$$
l ^ { \prime } ( z _ { i } ) = \left\{ { \begin{array} { l l } { \sigma ( z _ { i } ) , } & { { \nmid \mathrm { { \# I } } \mathrm { { \# } } \ y _ { i } = 0 , } } \\ { \sigma ( z _ { i } ) - 1 , } & { { \nmid \mathrm { { \# I } } \mathrm { { \# } } \ y _ { i } = 1 . } } \end{array} } \right.
$$

$l ^ { \prime } ( z _ { i } )$ 的图像如图2所示。对正样本 $\mathbf { x } _ { i }$ ，当 $z _ { i } > 0$ 时 $- 0 . 5 < l ^ { \prime } ( z _ { i } ) < 0$ ，当 $z _ { i } ~ < ~ 0$ 时$- 1 < l ^ { \prime } ( z _ { i } ) < - 0 . 5$ ，当 $z _ { i } = 0$ 时 $l ^ { \prime } ( z _ { i } ) = - 0 . 5$ ；对负样本 $\mathbf { x } _ { i }$ ，当 $z _ { i } > 0$ 时 $0 . 5 < l ^ { \prime } ( z _ { i } ) < 1$ ，当 $z _ { i } < 0$ 时 $0 < l ^ { \prime } ( z _ { i } ) < 0 . 5$ ，当 $z _ { i } = 0$ 时 $l ^ { \prime } ( z _ { i } ) = 0 . 5$ 。

定理4 (法向无限)．样本集 $D$ 线性可分时，逻辑回归最优分隔平面的法向量W 的模长是$+ \infty$ 。

证：根据线性可分的定义，存在向量 $\mathbf { w } _ { 1 }$ 和标量 $c _ { 1 }$ ， $\forall \mathbf { x } _ { i } \in D$ 满足

$$
z _ { i 1 } = \left\{ \begin{array} { l l } { \mathbf { w } _ { 1 } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } _ { 1 } ) < 0 , } \\ { \mathbf { w } _ { 1 } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } _ { 1 } ) \geq 0 , } \end{array} \right.
$$

令 $\mathbf { w } _ { 2 } = 2 \mathbf { w } _ { 1 }$ ，那么有

$$
z _ { i 2 } = \mathbf { w } _ { 2 } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } _ { 1 } ) = 2 \mathbf { w } _ { 1 } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } _ { 1 } ) = z _ { i 1 } , i = 1 , 2 , \ldots , m ,
$$

因此，对任意的正整数 $1 \leq i \leq m$ ，有

$$
l ( z _ { i 2 } ) = \left\{ \begin{array} { l l } { - \ln ( 1 - \sigma ( 2 z _ { i 1 } ) ) < - \ln ( 1 - \sigma ( z _ { i 1 } ) ) , } \\ { - \ln ( \sigma ( 2 z _ { i 1 } ) ) \le - \ln ( \sigma ( z _ { i 1 } ) ) , } \end{array} \right.
$$

即 $L ( \mathbf { w } _ { 2 } , b ) < L ( \mathbf { w } _ { 1 } , b )$ 。按照这个每次模长加倍的方法推下去，就得到 $| \hat { \mathbf { w } } | = + \infty$ 。

[证毕]

定理5 (法向有界).样本集 $D$ 线性不可分时，逻辑回归最优分隔平面的法向量有界。

证：假设满足式(4)的最优分隔平面的点法式方程为

$$
\hat { \mathbf { w } } ^ { T } ( \mathbf x - \hat { \mathbf c _ { 1 } } ) = 0 .
$$

令 $\mathbf { n } = \hat { \mathbf { w } } / | \hat { \mathbf { w } } |$ ，显然 $| { \bf n } | = 1$ 。假设样本集 $D$ 线性不可分，从而存在指标 $\mathbf { \chi } _ { i }$ 使得

$$
z _ { i } = { \mathbf { n } } ^ { T } ( { \bf x } _ { i } - { \bf c } _ { 1 } ) \geq 0 , \boxplus y _ { i } = 0
$$

或者

$$
z _ { i } = \mathbf { n } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } _ { 1 } ) < 0 , \mathrm { E } \ g _ { i } \ =
$$

将指标集合记为

$$
\begin{array} { r l } & { I _ { 0 } = \{ i | z _ { i } < 0 \operatorname { E } y _ { i } = 0 , \quad 1 \leq i \leq m \} , } \\ & { I _ { 1 } = \{ i | z _ { i } > 0 \operatorname { E } y _ { i } = 1 , \quad 1 \leq i \leq m \} , } \\ & { J _ { 0 } = \{ j | z _ { j } > 0 \operatorname { E } y _ { j } = 0 , \quad 1 \leq j \leq m \} , } \\ & { J _ { 1 } = \{ j | z _ { j } < 0 \operatorname { E } y _ { j } = 1 , \quad 1 \leq j \leq m \} , } \\ & { K _ { 0 } = \{ k | z _ { k } = 0 , \quad 1 \leq k \leq m \} , } \end{array}
$$

指标集合上的损失函数分别记为

$$
\begin{array} { r c l } { { { \cal L } _ { I _ { 0 } } ( { \bf n } ) } } & { { = } } & { { \displaystyle { \displaystyle { \frac { 1 } { m } } \sum _ { i \in I _ { 0 } } l ( z _ { i } ) , } \quad { \cal L } _ { I _ { 1 } } ( { \bf n } ) = \displaystyle { \frac { 1 } { m } \sum _ { i \in I _ { 1 } } l ( z _ { i } ) } , } } \\ { { { \cal L } _ { J _ { 0 } } ( { \bf n } ) } } & { { = } } & { { \displaystyle { \frac { 1 } { m } \sum _ { j \in J _ { 0 } } l ( z _ { j } ) , } \quad { \cal L } _ { J _ { 1 } } ( { \bf n } ) = \displaystyle { \frac { 1 } { m } \sum _ { j \in J _ { 1 } } l ( z _ { j } ) } , } } \\ { { { \cal L } _ { K _ { 0 } } ( { \bf n } ) } } & { { = } } & { { \displaystyle { \frac { 1 } { m } \sum _ { k \in K _ { 0 } } l ( z _ { k } ) } } } \end{array}
$$

由式 (3)知,

$$
L ( \mathbf { n } , b ) = L _ { I _ { 0 } } ( \mathbf { n } ) + L _ { I _ { 1 } } ( \mathbf { n } ) + L _ { J _ { 0 } } ( \mathbf { n } ) + L _ { J _ { 1 } } ( \mathbf { n } ) + L _ { K _ { 0 } } ( \mathbf { n } ) .
$$

由式(36)(37）知 $I _ { 0 } \cup I _ { 1 } \cup K _ { 0 }$ 和 $J _ { 0 } \cup J _ { 1 } \ne \phi$ 是非空集合，为论证方便，这里仅考虑 $I _ { 0 }$ 、$I _ { 1 }$ 、 $J _ { 0 }$ 、 $J _ { 1 }$ 、 $K _ { 0 }$ 均为非空集合的一般情形，其它特殊情形可做类似证明。

令 $\lambda > 1$ 为正实数， $\delta$ 为正无究小量。接下来寻找 $\lambda$ 的取值范围，使得

$$
\begin{array} { r l } { { \cal L } ( ( \lambda + \delta ) { \bf n } , b ) - { \cal L } ( \lambda { \bf n } , b ) } & { } \\ { = } & { { \cal L } _ { I _ { 0 } } ( ( \lambda + \delta ) { \bf n } ) - { \cal L } _ { I _ { 0 } } ( \lambda { \bf n } ) + { \cal L } _ { I _ { 1 } } ( ( \lambda + \delta ) { \bf n } ) - { \cal L } _ { I _ { 1 } } ( \lambda { \bf n } ) + { \cal L } _ { J _ { 0 } } ( ( \lambda + \delta ) { \bf n } ) } \\ & { - { \cal L } _ { J _ { 0 } } ( \lambda { \bf n } ) + { \cal L } _ { J _ { 1 } } ( ( \lambda + \delta ) { \bf n } ) - { \cal L } _ { J _ { 1 } } ( \lambda { \bf n } ) + { \cal L } _ { K _ { 0 } } ( ( \lambda + \delta ) { \bf n } ) - { \cal L } _ { K _ { 0 } } ( \lambda { \bf n } ) } \\ { > } & { 0 } \end{array}
$$

成立。

由式(38)(3)知，对 $\forall k \in K _ { 0 }$ ，有 $z _ { k } = 0 , \ l ( ( \lambda + \delta ) z _ { k } ) = l ( \lambda z _ { k } ) = \ln ( 2 )$ 。由式(39)知,

$$
L _ { K _ { 0 } } ( ( \lambda + \delta ) \mathbf { n } ) - L _ { K _ { 0 } } ( \lambda \mathbf { n } ) = 0 .
$$

对 $\forall j \in J _ { 0 }$ ，由式(35)知， $l ^ { \prime } ( z _ { j } )$ 的值从 $1 / 2$ 严格单调递增至1，从而有

$$
l ( ( \lambda + \delta ) z _ { j } ) - l ( \lambda z _ { j } ) > l ^ { \prime } ( \lambda z _ { j } ) \delta z _ { j } > \frac { 1 } { 2 } \delta z _ { j } ,
$$

$$
L _ { J _ { 0 } } ( ( \lambda + \delta ) { \bf n } ) - L _ { J _ { 0 } } ( \lambda { \bf n } ) > \frac { 1 } { 2 } \delta \sum _ { j \in J _ { 0 } } z _ { j } .
$$

对 $\forall j \in J _ { 1 }$ ，由式(35)知， $l ^ { \prime } ( z _ { j } )$ 的值从 $- 1$ 严格单调递增至 $- 1 / 2$ ，从而有

$$
l ( ( \lambda + \delta ) z _ { j } ) - l ( \lambda z _ { j } ) > l ^ { \prime } ( \lambda z _ { j } ) \delta z _ { j } > - \frac { 1 } { 2 } \delta z _ { j } ,
$$

$$
L _ { J _ { 1 } } ( ( \lambda + \delta ) { \bf n } ) - L _ { J _ { 1 } } ( \lambda { \bf n } ) > - \frac { 1 } { 2 } \delta \sum _ { j \in J _ { 1 } } z _ { j } .
$$

令

$$
E _ { 0 } = \frac { 1 } { 2 } ( \sum _ { j \in J _ { 0 } } z _ { j } - \sum _ { j \in J _ { 1 } } z _ { j } ) / ( - \sum _ { i \in I _ { 0 } } z _ { i } + \sum _ { i \in I _ { 1 } } z _ { i } ) ,
$$

由 $I _ { 0 } \setminus I _ { 1 } \setminus J _ { 0 } \setminus J _ { 1 }$ 的定义知 $E _ { 0 } ~ > ~ 0 ~$ 。这里需要假设 $E _ { 0 } ~ < ~ 1$ ，它可以模糊地理解为"样本集中被分错的样本数量小于被分对的样本数量的2倍”，显然是一个合理的假设。由式(35)知，在 $y _ { i } = 0$ 时， $l ^ { \prime } ( z _ { i } )$ 在定义域 $( - \infty , 0 )$ 上的值从0严格单调递增至 $1 / 2$ ，因此对$\forall \lambda > \lambda _ { 0 } = - \sigma ^ { - 1 } ( E _ { 0 } ) > 0$ 和 $\forall i \in I _ { 0 }$ 均有 $l ^ { \prime } ( \lambda z _ { i } ) < E _ { 0 }$ 。

对 $\forall i \in I _ { 0 }$ ，由式(3)(35）知

$$
0 > l ( ( \lambda + \delta ) z _ { i } ) - l ( \lambda z _ { i } ) > l ^ { \prime } ( \lambda z _ { i } ) \delta z _ { i } ,
$$

参考文献

进而，对 $\forall \lambda > \lambda _ { 0 }$ 有

$$
L _ { I _ { 0 } } ( ( \lambda + \delta ) { \bf n } ) - L _ { I _ { 0 } } ( \lambda { \bf n } ) > \delta \sum _ { i \in I _ { 0 } } l ^ { \prime } ( \lambda z _ { i } ) z _ { i } > \delta E _ { 0 } \sum _ { i \in I _ { 0 } } z _ { i } .
$$

由式(35)知，在 $y _ { i } = 1$ 时， $l ^ { \prime } ( z _ { i } )$ 在定义域 $( 0 , + \infty )$ 上的值从 $- 1 / 2$ 严格单调递增至0，因此对 $\forall \lambda > \lambda _ { 1 } = \sigma ^ { - 1 } ( 1 - E _ { 0 } ) > 0$ 和 $\forall i \in I _ { 1 }$ 有

$$
- E _ { 0 } < l ^ { \prime } ( \lambda z _ { i } ) < 0 .
$$

对 $\forall i \in I _ { 1 }$ ，由式(3)(35)知

$$
0 > l ( ( \lambda + \delta ) z _ { i } ) - l ( \lambda z _ { i } ) > l ^ { \prime } ( \lambda z _ { i } ) \delta z _ { j } ,
$$

进而，对 $\forall \lambda > \lambda _ { 1 }$ 有

$$
L _ { I _ { 1 } } ( ( \lambda + \delta ) { \bf n } ) - L _ { I _ { 1 } } ( \lambda { \bf n } ) > \delta \sum _ { i \in I _ { 1 } } l ^ { \prime } ( \lambda z _ { i } ) z _ { i } > - \delta E _ { 0 } \sum _ { i \in I _ { 1 } } z _ { i } .
$$

综合式 (40)-(45)得知，当 $\lambda > \operatorname* { m a x } \{ \lambda _ { 0 } , \lambda _ { 1 } \}$ 时，有

$$
\begin{array} { r l } {  { L ( ( \lambda + \delta ) { \bf n } , b ) - L ( \lambda { \bf n } , b ) } } \\ { > } & { \delta E _ { 0 } \sum _ { i \in I _ { 0 } } z _ { i } - \delta E _ { 0 } \sum _ { i \in I _ { 1 } } z _ { i } + \frac { \delta } { 2 } \sum _ { j \in J _ { 0 } } z _ { j } - \frac { \delta } { 2 } \sum _ { j \in J _ { 1 } } z _ { j } + 0 } \\ { > } & { \delta E _ { 0 } ( \sum _ { i \in I _ { 0 } } z _ { i } - \sum _ { i \in I _ { 1 } } z _ { i } ) + \frac { \delta } { 2 } ( \sum _ { j \in J _ { 0 } } z _ { j } - \sum _ { j \in J _ { 1 } } z _ { j } ) } \\ { \ge } & { \frac { \delta } { 2 } \frac { \displaystyle \sum _ { j \in J _ { 0 } } z _ { j } - \sum _ { j \in J _ { 1 } } z _ { j } } { \displaystyle \sum _ { i \in I _ { 0 } } z _ { i } + \sum _ { i \in I _ { 1 } } z _ { i } } ( \sum _ { i \in I _ { 0 } } z _ { i } - \sum _ { i \in I _ { 1 } } z _ { i } ) + \frac { \delta } { 2 } ( \sum _ { j \in J _ { 0 } } z _ { j } - \sum _ { j \in J _ { 1 } } z _ { j } ) } \\ { = } & { 0 . } \end{array}
$$

式（46)意味着 $\boldsymbol { L } ( \lambda \mathbf { n } , b )$ 在 $\lambda \in \left( \operatorname* { m a x } \{ \lambda _ { 0 } , \lambda _ { 1 } \} , + \infty \right)$ 严格单调递增，从而最分优分隔平面的法向量模长 $| \hat { \mathbf { w } } | = \hat { \lambda } | \mathbf { n } | = \hat { \lambda } \leq \operatorname* { m a x } \{ \lambda _ { 0 } , \lambda _ { 1 } \}$ ，即𝑤有界。

[证毕]

# 参考文献

[1]周志华，机器学习，p57-60，清华大学出版社，2016.4   
[2] https://www.csie.ntu.edu.tw/ cjlin/liblinear/   
[3] T.Hastie,R. Tibshirani, and J. Friedman.The Elements of Statisti- cal Learning, Second Edition: Data Mining, Inference,and Prediction. Springer Series in Statistics. Springer,0002-2009.corr.3rd edition,Feb.2009.   
[4] G.Andrew and J. Gao. Scalable training of ll-regularized log-linear models. In Proceedings of the 24th international conference on Machine learning, ICML '07, pages 33-40,New York, NY, USA,2007. ACM.   
[5] C.-J. Lin and J. J. Mor e. Newton's method for large bound-constrained optimization problems. SIAM J.on Optimization, 9(4):1100-1127,Apr. 1999.   
[6] C.-J. Lin, R. C. Weng,and S. S. Keerthi. Trust region newton method for logistic regression. Journal of Machine Learning Research, 9:627-650, 2008.   
[7] G.-X. Yuan, K.-W. Chang, C.-J. Hsieh,and C.-J. Lin. A comparison of optimization methods and software for large-scale l1-regularized linear clas- sifcation. J. Mach. Learn.Res., 11:3183-3234, Dec.2010   
[8] S.Perkins and J.Theiler. Online feature selection using grafting.In In In- ternational Conference on Machine Learning, pages 592-599. ACM Press, 2003.   
[9] M.J. Streeter and H. B. McMahan. Less regret via online conditioning. CoRR, abs/1002.4862, 2010.   
[10] G.-X. Yuan, C.-H. Ho,and C.-J. Lin. An improved glmnet for ll-regularized logistic regression. Journal of Machine Learning Research,13:1999-2030, 2012.   
[11] J.Friedman, T.Hastie,and R. Tibshirani. Regularization paths for gener- alized linear models via coordinate descent. Journal of Statistical Software,33(1):1-22, 2010.   
[12] http://yann.lecun.com/exdb/mnist/