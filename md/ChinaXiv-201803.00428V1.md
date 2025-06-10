# 逻辑回归上的反拉加速方法

The Counter Pull Acceleration Method for Logistic Regression

何沧平微博cangping@staff.weibo.com

2018年3月12日

# 摘要

本文通过严格数学分析找出了逻辑回归过拟合的成因：边界样本的损失贡献比重大且随法向量增长而加速增大、边界样本分布散乱，顺便理清了正则项的作用机理。利用过拟合机制，本文提出一种反拉方法，既能缓解过拟合，又能减少训练步数，在 MNIST数据集上实现加速38.25倍，在CIFAR10数据集上实现加速5.61倍。

In this paper,I found the two reasons of overfitting of logistic regression: boundary samples occupy a larger and larger share as the length of normal vector becomes longer and longer, boundary samples do not fit their probability density function well.With the help of insight in overfittng,I propose a acceleration method for logistic regression and got a training speedup of 38.25 on MNIST dataset,a training speedup of 5.61 on CIFAR10 dataset.

关键字：逻辑回归，过拟合解释，反拉加速

# 1引言

逻辑回归（Logistic Regression）是机器学习的一个基础分类方法[1]。它形式简单，有 LIBLIN-EAR [2]这样的工具库，工程实现方便，在互联网推荐系统中有广泛的应用。各大公司有成千上万台服务器在一刻不停地训练逻辑回归模型，如果能保证正确率的前提下大幅提高训练速度，那么将能节省大量运营成本。

目前提高训练速度的主要手段是样本预处理和设计更好的最优化算法。一个有效的样本预处理方法是按分量白化[3]；可用的最优化算法有很多，常用的是梯度下降法的多种变体[4]，例如随机梯度法、Momentum 算法、Nesterov accelerated gradient 算法、Adagrad 算法、Adadelta 算法，等等；还有 DFP、BFGS、L-BFGS 等拟牛顿算法[6]，以及速度更快的信赖域算法[7]；并行化的最优化算法[5]也能提高训练速度。

过拟合是计算学习的关键障碍，通常的解释是模型过于复杂[1,8]，要用相对简单的模型来缓解过拟合现象；至于过拟合的成因，可用“偏差-方差分解”[1,9]来解释，[10]还讨论了过拟合与噪声、多重假设检验的关系。缓解过拟合的常用手段是添加正则化项，[8]对比了 $L _ { 1 }$ 正则化和 $L _ { 2 }$ 正则化的特点。

本文的初衷是探究逻辑回归过拟合的形成机制，因为模型已经确定，所以无法再用“模型过于复杂”这样的理由来解释。因此跳出常规的概率视角，用Taylor展开分析交叉熵后发现，逻辑回归过拟合的原因有两个：边界样本的损失贡献比重大且随法向量增长而加速增大、边界样本分布散乱。虽然法向量过大只是过拟合的表象，但是控制法向量模长却能够切实缓解过拟合，因此各种正则化手段有效。

利用对过拟合机制的洞察，本文提出一种反拉方法：修改各个样本在交叉熵损失函数中的贡献比重，提高被分错样本的损失贡献，能够减少提高逻辑回归的训练次数；降低被分错样本的损失贡献，能够减缓过拟合。为了保证交叉熵的数值稳定性，顺便提出一种近似计算方法。在手写数字数据集 MNIST[12]上，反拉方法将训练速度提高 38.25倍；在CIFRA10 数据集上，反拉方法将训练速度提高 5.61 倍。

本文后续内容这样组织。第2节给出逻辑回归公式，为后文公式推导做准备；第3节给合实例和公式推导给出过拟合的2个原因；第4节给出反拉方法；第5节是数值实验，验证反拉方法的加速性能和缓解过拟合的效果。

# 2 逻辑回归

给定数据集 $D = \{ ( \mathbf { x } _ { 1 } , y _ { 1 } ) , ( \mathbf { x } _ { 2 } , y _ { 2 } ) , \dots , ( \mathbf { x } _ { m } , y _ { m } ) \}$ ，其中 $d$ 为正整数，列向量 $\mathbf { x } _ { i } = ( x _ { i 1 } ; x _ { i 2 } ; \ldots ; x _ { i d } )$ 标量 $y _ { i } \in \{ 0 , 1 \}$ 。当 $y _ { i } = 0$ 时称 $\mathbf { x } _ { i }$ 是负样本，当 $y _ { i } = 1$ 时称 $\mathbf { x } _ { i }$ 是正样本。二分类问题是要从数据集 $D$ 中学习到一个模型，然后用这个模型预测任意的样本 $\mathbf { x } _ { j }$ 是正样本还是负样本。

逻辑回归的任务是从给定数据集 $D$ 中学习到分隔面的斜截式方程

$$
\mathbf { w } ^ { T } \mathbf { x } + b = 0 , \quad | \mathbf { w } | \neq 0
$$

确定其中的法向量 $\mathbf { w }$ 和截距 $b$ 值。这里的 $\mathbf { w }$ 是列向量，记为 $\mathbf { w } = ( w _ { 1 } ; w _ { 2 } ; \ldots ; w _ { d } )$ ， $b$ 是标量。任意平面都可以用做分隔面，区别只是推测效果可能不同。

为了寻找分隔面 (1)，对 $\forall \mathbf { x } _ { i } \in D$ ，令 $z _ { i } = \mathbf { w } ^ { T } \mathbf { x } _ { i } + b$ ，按照[11]中定义， $z _ { i }$ 为点 $\mathbf { x } _ { i }$ 到分隔面(1）的加权距离。定义单个样本 $\mathbf { x } _ { i }$ 上的损失函数

$$
l ( z _ { i } ) = \left\{ \begin{array} { l l } { - \ln ( 1 - \sigma ( z _ { i } ) ) , } & { \mathrm { } \mathcal { H } \mathbb { H } \mathbb { } \ y _ { i } = 0 , } \\ { - \ln ( \sigma ( z _ { i } ) ) , } & { \mathrm { } \mathcal { H } \mathbb { H } \mathbb { } \ y _ { i } = 1 , } \end{array} \right.
$$

这里的 $\sigma ( z )$ 为 Sigmoid 函数 $\begin{array} { r } { \sigma ( z ) = \frac { 1 } { 1 + e ^ { - z } } } \end{array}$ 。将样本集 $D$ 上的损失函数定义为

$$
L ( \mathbf { w } , b ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } l ( z _ { i } ) ,
$$

overfitting of LR on linear separable dataset3 。 train-negtive。 train-positivetest-negtive2 test-positive：1 。 中 0+ obobo 1 + 0.0.0.0.. ·O·O-·O:O··O:：： T+2 0 : ： 1）· ：-2-3-3 -2 -1 0 1 2 3+

![](images/be267e27855acfba7641e84a257584e40ee8a777f8a05c98bce54e0c4cbc8837.jpg)  
图1：线性可分样本集上的过拟合  
图2：线性可分样本集上的正确率

求解它的最小值

$$
\begin{array} { r } { \{ \hat { \mathbf { w } } , \hat { b } \} = \underset { \mathbf { w } , b } { \arg \operatorname* { m i n } } L ( \mathbf { w } , b ) , } \end{array}
$$

就得到了最优参数w和 $\hat { b }$ ，代入（1）即得最优分隔面 $\hat { \mathbf { w } } ^ { T } \mathbf { x } + \hat { b } = 0$ 号

对任意样本 ${ \bf x } _ { j }$ ，用最优分隔面来推测它归属的类别。令

$$
\begin{array} { r } { y _ { j } = \left\{ \begin{array} { l l } { 0 , } & { \niiint \ncong \hat { \mathbf { w } } ^ { T } \mathbf { x } _ { j } + \hat { b } < 0 , } \\ { 1 , } & { \niiint \ncong \hat { \mathbf { w } } ^ { T } \mathbf { x } _ { j } + \hat { b } \geq 0 , } \end{array} \right. } \end{array}
$$

如果 $y _ { j } = 0$ ，那么推测 $\mathbf { x }$ 是负样本；如果 $y _ { j } = 1$ ，那么推测 ${ \bf x } _ { j }$ 是正样本。

# 3 过拟合实例与成因

在逻辑回归问题中，正确率通常会随着训练步数的增加而升高。有时在训练若干步以后，随着训练集样本上的正确率逐渐提高，测试集上的正确率不再提高甚至下降，这种现象称为过拟合。

为直观说明过拟合的成因，先给出2个没有实际意义的例子，它们分别对应线性可分的样本集和线性不可分的样本集。

# 3.1 线性可分样本集上的过拟合

图1中，蓝色圆圈是训练集中的负样本，红色圆圈是训练集中的正样本。训练集中的36 个负样本均匀分布在区域 $[ - 3 , - 1 ] \times [ - 1 , 1 ]$ 中，一个偏离主体的训练集负样本是点 (0.5,-1)。训练集中的 36 个正样本均匀分布在区域 $[ 1 , 3 ] \times [ - 1 , 1 ]$ 中，一个偏离主体的训练集正样本是点 (-0.5,1)。根据[11]中的定义，可以验证这个训练集线性可分。 $2 0 \times 2 0$ 个蓝色小圆点是测试集中的负样本，它

2.5 。 train-negtive 。 train-positive 2 test-negtive test-positive 1.5 · 1 19:0:0.9:0 广 。 0。 O·············· a% 0: p18 q:0: oop 。 0: +2 0 d : 0::0: :0: :: ： o:: ： :d :8 :8: 8:8 · · ： ： · ： · ： D : ： 0010 ： ： ： . 1 : o: :6: d ：： ：： -1.5 -2 -2.5 -3 -2 -1 0 1 2 3 X1

![](images/c27b900716542b650fafe0845e3876efeba6f4fb3e8977204705919e9d46afe6.jpg)  
图3：线性不可分样本集上的过拟合  
图4：线性不可分样本集上的正确率

们均匀分布在区间 $[ - 3 , - 0 . 2 ] \times [ - 1 . 5 , 1 . 5 ]$ 中； $2 0 \times 2 0$ 个红点小圆点是测试集中的正样本，它们均匀分布在区间 $[ 0 . 2 , 3 ] \times [ - 1 . 5 , 1 . 5 ]$ 中。

使用逻辑回归对这个样本集分类，用最速下降法迭代求解式 (3)，迭代步长指定为0.1。图1中的黑色直线是初始分隔线 (分隔面在二维空间退化为分隔线)，洋红色虚线是迭代1000 步后的分隔线，洋红色实直线是迭代 2000 步后的分隔线。黑色直线是按照[11]中的方法选取的：

$$
\frac { ( \pmb { \mu } _ { 0 } + \pmb { \mu } _ { 1 } ) ^ { T } } { | \pmb { \mu } _ { 0 } + \pmb { \mu } _ { 1 } | } ( \mathbf { x } - \frac { \pmb { \mu } _ { 0 } + \pmb { \mu } _ { 1 } } { 2 } ) = 0 ,
$$

这里的 $\pmb { \mu } _ { 0 }$ 是训练集中所有负样本的均值， $\pmb { \mu } _ { 1 }$ 是训练集中所有正样本的均值。

图2是迭代过程中的正确率走势，在第1635步迭代之后，训练集上的正确率达到了1，但测试集上的正确率从第180步开始持续下降，发生过拟合。

# 3.2 线性不可分样本集上的过拟合

图3中，蓝色圆圈是训练集中的负样本，红色圆圈是训练集中的正样本。训练集中的36个负样本均匀分布在区域 $[ - 3 , - 1 ] \times [ - 1 , 1 ]$ 中，一个偏离主体的训练集负样本是点 (0.4,-0.4)。训练集中的 36 个正样本均匀分布在区域 $[ 1 , 3 ] \times [ - 1 , 1 ]$ 中，一个偏离主体的训练集正样本是点(-0.8,0.4)。根据[11]中的定义，这个训练集线性不可分。 $2 0 \times 2 0$ 个蓝色小圆点是测试集中的负样本，它们均匀分布在区间 $[ - 3 , - 0 . 2 ] \times [ - 1 . 5 , 1 . 5 ]$ 中； $2 0 \times 2 0$ 个红点小圆点是测试集中的正样本，它们均匀分布在区间 $[ 0 . 2 , 3 ] \times [ - 1 . 5 , 1 . 5 ]$ 中。

使用逻辑回归对这个样本集分类，用最速下降法迭代求解式(3)，迭代步长指定为0.1。图3中的黑色直线是初始分隔线，洋红色虚线是迭代 5000 步后的分隔线，洋红色实直线是迭代10000 步后的分隔线。黑色直线的方程是(5)。图4是迭代过程中的正确率走势，训练集上的正确率保持平稳，但测试集上的正确率从463步开始持续下降，发生过拟合。

![](images/6a15c5b7d4afc00af1f0d2974ef991d3a9996de0786f091c7d430130f9134afc.jpg)  
图5：单个样本上的损失函数 $l ( z _ { i } )$ 。红线对应正样本，蓝线对应负样本。

仔细孝查图1和图3发现，很少的边界样本的大致决定了分隔面的走向，边界样本的影响力比远离边界的样本的影响力大很多，这也许就是探寻过拟合线索。

# 3.3 过拟合成因

人眼直观判断，图1和图3中各有2个训练样本远离主体，应该按噪音处理，舍去；即使不舍去，它们对确定分隔线的影响也不应太大。实际上，如果舍去噪音样本，那么训练集得到的理想分隔线应该为 $x _ { 1 } = 0$ 。黑色直线方程为 $0 . 9 9 9 9 x _ { 1 } + 0 . 0 1 4 0 x _ { 2 } = 0$ ，与理想分割线很接近。

逻辑回归得到的分隔线是怎么偏离样本主体的呢？为此，仔细观察损失函数 $l ( z _ { i } )$ 的走势。样本 $\mathbf { x } _ { i }$ 与 $z _ { i }$ 一一对应，从图5中知道，对正样本 $\mathbf { x } _ { i }$ ，如果 $z _ { i } \geq 0$ ，那么 $\mathbf { x } _ { i }$ 被正确分类，此时它的损失函数值 $l ( \sigma ( z _ { i } ) ) \leq - \ln ( \sigma ( 0 ) )$ ；如果 $z _ { i } < 0$ ，那么 $\mathbf { x } _ { i }$ 被错误地分为负类，此时它的损失函数值$l ( \sigma ( z _ { i } ) ) > - \ln ( \sigma ( 0 ) )$ 。当 $\mathbf { x } _ { i }$ 为负样本时，情况类似。

从图5中可以直观地看到，相对于被正确分类的样本，被错误分类的样本对损失函数的贡献更大。

为了定量分析样本对损失函数的贡献，需要用 Taylor 公式寻找 $l ( z _ { i } )$ 的简单近似函数。为此定义两个函数

$$
f _ { 0 } ( z ) = \left\{ \begin{array} { l l } { - e ^ { z } , } & { \hbar \mathbb { I } \mathbb { H } \mathbb { K } z < - C _ { 0 } < 0 , } \\ { \ln ( 1 - \sigma ( z ) ) , } & { \hbar \mathbb { I } \mathbb { H } \mathbb { K } - C _ { 0 } \leq z \leq C _ { 0 } , } \\ { - z - e ^ { - z } , } & { \hbar \mathbb { I } \mathbb { H } \mathbb { K } z > C _ { 0 } > 0 , } \end{array} \right.
$$

$$
f _ { 1 } ( z ) = \left\{ \begin{array} { l l } { z - e ^ { z } , } & { \nleq \scriptscriptstyle { \mathscr { W } } \displaystyle \mathbb { H } \displaystyle \mathbb { E } z < - C _ { 0 } < 0 , } \\ { \ln ( \sigma ( z ) ) , } & { \nleq \scriptscriptstyle { \mathscr { W } } \displaystyle \mathbb { E } - C _ { 0 } \leq z \leq C _ { 0 } , } \\ { - e ^ { - z } , } & { \nleq \scriptscriptstyle { \mathscr { W } } \displaystyle \mathbb { E } z > C _ { 0 } > 0 , } \end{array} \right.
$$

这里的 $C _ { 0 }$ 是任意指定的正实数。

定理1.函数 $f _ { 0 } ( z )$ 是 $\ln ( 1 - \sigma ( z ) )$ 的近似，函数 $f _ { 1 } ( z )$ 是 $\ln ( \sigma ( z ) )$ 的近似。

证．先证明 $f _ { 0 } ( z )$ 是 $\ln ( 1 - \sigma ( z ) )$ 的近似。当 $z < - C _ { 0 }$ 时， $e ^ { z } < \exp ( - C _ { 0 } ) < 1$ ，从而有

$$
{ \begin{array} { l l l } { \displaystyle \ln ( 1 - \sigma ( z ) ) } & { = } & { \displaystyle \ln ( 1 - { \frac { 1 } { 1 + e ^ { - z } } } ) = \ln ( 1 - { \frac { e ^ { z } } { 1 + e ^ { z } } } ) = \ln ( { \frac { 1 } { 1 + e ^ { z } } } ) = \ln ( 1 ) - \ln ( 1 + e ^ { z } ) } \\ { \displaystyle } & { = } & { \displaystyle - e ^ { z } + { \cal O } ( e ^ { 2 z } ) . } \end{array} }
$$

当 $z > C _ { 0 }$ 时， $e ^ { - z } < \exp ( - C _ { 0 } ) < 1$ ，从而有

$$
\begin{array} { r c l } { \displaystyle \ln ( 1 - \sigma ( z ) ) } & { = } & { \displaystyle \ln ( 1 - \frac { 1 } { 1 + e ^ { - z } } ) = \ln ( \frac { e ^ { - z } } { 1 + e ^ { - z } } ) = \ln ( e ^ { - z } ) - \ln ( 1 + e ^ { - z } ) } \\ & { = } & { \displaystyle - z - e ^ { - z } + { \cal O } ( e ^ { - 2 z } ) . } \end{array}
$$

因此，对任意给定的实数 $z$ ， $\operatorname* { m a x } ( | f _ { 0 } ( z ) - \ln ( 1 - \sigma ( z ) ) | ) = O ( \exp ( - 2 C _ { 0 } ) )$ ，函数 $f _ { 0 } ( z )$ 是 $\ln ( 1 - \sigma ( z ) )$ 的近似。

再证明 $f _ { 1 } ( z )$ 是 $\ln ( \sigma ( z ) )$ 的近似。当 $z < - C _ { 0 }$ 时， $e ^ { z } < \exp ( - C _ { 0 } ) < 1$ ，从而有

$$
\begin{array} { r c l } { \displaystyle \ln ( \sigma ( z ) ) } & { = } & { \displaystyle \ln ( \frac { 1 } { 1 + e ^ { - z } } ) = \ln ( \frac { e ^ { z } } { 1 + e ^ { z } } ) = \ln ( e ^ { z } ) - \ln ( 1 + e ^ { z } ) } \\ & { = } & { z - e ^ { z } + { \cal O } ( e ^ { 2 z } ) . } \end{array}
$$

当 $z > C _ { 0 }$ 时， $e ^ { - z } < \exp ( - C _ { 0 } ) < 1$ ，从而有

$$
\ln ( \sigma ( z ) ) = \ln ( { \frac { 1 } { 1 + e ^ { - z } } } ) = \ln ( 1 ) - \ln ( 1 + e ^ { - z } ) = - e ^ { - z } + O ( e ^ { - 2 z } ) .
$$

因此，对任意给定的实数 $z$ ， $\operatorname* { m a x } ( | f _ { 1 } ( z ) - \ln ( \sigma ( z ) ) | ) = O ( \exp ( - 2 C _ { 0 } ) )$ ，函数 $f _ { 1 } ( z )$ 是 $\ln ( \sigma ( z ) )$ 的近似。

[证毕]

当 $C _ { 0 } = 4 . 3$ 时， $\exp ( - C _ { 0 } ) = 0 . 0 1 3 6$ ， $\exp ( - 2 C _ { 0 } ) = 0 . 0 0 0 1 8 4 1 1$ 。实际上，容易验证，此时有$0 < f _ { 0 } ( z ) - \ln ( 1 - \sigma ( z ) ) < 0 . 0 0 0 1 , 0 < f _ { 1 } ( z ) - \ln ( \sigma ( z ) ) < 0 . 0 0 0 1 ,$ 逼近良好。

根据定理1，单个样本上的损失函数(2）可以近似地表示为

$$
l ( z _ { i } ) \approx \left\{ { \begin{array} { l l } { - f _ { 0 } ( z _ { i } ) , } & { { \mathcal { H } } \mathbb { H } \mathbb { H } } \\ { - f _ { 1 } ( z _ { i } ) , } & { { \mathcal { H } } \mathbb { H } \mathbb { H } } \end{array} } y _ { i } = 0 , \right.
$$

为简化说明，本节后续叙述只考虑正样本的损失函数曲线，负样本的情形类似。式（1）是分隔面的斜截式方程，由解析几何知道，它有一个等价的点法式方程 $\mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) = 0$ ，这里的 $\mathrm { ~ \bf ~ c ~ }$ 是 $d$ 维列向量。假设样本 $\mathbf { x } _ { 1 }$ 和 ${ \bf x } _ { 2 }$ 均为正样本，给定法向量w 和点 $\mathrm { ~ \bf ~ c ~ }$ ，有 $z _ { 1 } = \mathbf { w } ^ { T } ( \mathbf { x } _ { 1 } - \mathbf { c } )$ 和$z _ { 2 } = \mathbf { w } ^ { T } ( \mathbf { x } _ { 2 } - \mathbf { c } )$ 。观察图5中红线知道，如果 $z _ { 1 } < z _ { 2 }$ ，那么 $l ( z _ { i } ) > l ( z _ { 2 } )$ ，即

推论1，样本的加权距离越小，损失贡献越大。

给定 $C _ { 0 } > 0$ 。当 $z _ { 1 } < z _ { 2 } < - C _ { 0 }$ 时， ${ \bf x } _ { 1 }$ 和 ${ \bf x } _ { 2 }$ 均位于分隔面 $\mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) = 0$ 的背面，即都被分错了。假设 $\mathbf { w } _ { 2 } = s \mathbf { w }$ ，其中实数 $s > 1$ ，记 $\bar { z } _ { 1 } = \mathbf { w } _ { 2 } ^ { T } ( \mathbf { x } _ { 1 } - \mathbf { c } )$ 和 $\bar { z } _ { 2 } = \mathbf { w } _ { 2 } ^ { T } ( \mathbf { x } _ { 2 } - \mathbf { c } )$ ，那么有

$$
\frac { l ( \bar { z } _ { 1 } ) } { l ( \bar { z } _ { 2 } ) } = \frac { l ( s z _ { 1 } ) } { l ( s z _ { 2 } ) } \approx \frac { - f _ { 1 } ( s z _ { 1 } ) } { - f _ { 1 } ( s z _ { 2 } ) } \approx \frac { s z _ { 1 } - e ^ { s z _ { 1 } } } { s z _ { 2 } - e ^ { s z _ { 2 } } } \approx \frac { z _ { 1 } } { z _ { 2 } } \approx \frac { l ( z _ { 1 } ) } { l ( z _ { 2 } ) } ,
$$

由式 (8)得

推论2.被分错样本之间的损失贡献比例不随法向量的变化而变化。

给定 $C _ { 0 } > 0$ 。当 $C _ { 0 } < z _ { 1 } < z _ { 2 }$ 时， ${ \bf x } _ { 1 }$ 和 ${ \bf x } _ { 2 }$ 均位于分隔面 $\mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) = 0$ 的正面，即都被分对了。假设 $\mathbf { w } _ { 2 } = s \mathbf { w }$ ，其中实数 $s > 1$ ，记 $\bar { z } _ { 1 } = \mathbf { w } _ { 2 } ^ { T } \big ( \mathbf { x } _ { 1 } - \mathbf { c } \big )$ 和 $\bar { z } _ { 2 } = \mathbf { w } _ { 2 } ^ { T } \big ( \mathbf { x } _ { 2 } - \mathbf { c } \big )$ ，那么有

$$
\frac { l ( \bar { z } _ { 1 } ) } { l ( \bar { z } _ { 2 } ) } = \frac { l ( s z _ { 1 } ) } { l ( s z _ { 2 } ) } \approx \frac { - f _ { 1 } ( s z _ { 1 } ) } { - f _ { 1 } ( s z _ { 2 } ) } \approx \frac { e ^ { - s z _ { 1 } } } { e ^ { - s z _ { 2 } } } = \exp ( s ( z _ { 2 } - z _ { 1 } ) ) = ( \exp ( z _ { 2 } - z _ { 1 } ) ) ^ { s } ,
$$

由式 (9)得

推论3.被分对样本之间的损失贡献比例会随着法向量的增长而指数级增长。

给定 $C _ { 0 } > 0$ 。当 $z _ { 2 } > C _ { 0 }$ 且 $z _ { 1 } = - z _ { 2 }$ 时， ${ \bf x } _ { 1 }$ 和 ${ \bf x } _ { 2 }$ 分别位于分隔面 $\mathbf { w } ^ { T } ( \mathbf { x } _ { i } - \mathbf { c } ) = 0$ 的背面和正面，即一个被分错了另一个被分对了。假设 $\mathbf { w } _ { 2 } = s \mathbf { w }$ ，其中实数 $s > 1$ ，记 $\bar { z } _ { 1 } = \mathbf { w } _ { 2 } ^ { T } \big ( \mathbf { x } _ { 1 } - \mathbf { c } \big )$ 和$\bar { z } _ { 2 } = \mathbf { w } _ { 2 } ^ { T } ( \mathbf { x } _ { 2 } - \mathbf { c } )$ ，那么有

$$
\frac { l ( \bar { z } _ { 1 } ) } { l ( \bar { z } _ { 2 } ) } = \frac { l ( - s z _ { 2 } ) } { l ( s z _ { 2 } ) } \approx \frac { - f _ { 1 } ( - s z _ { 2 } ) } { - f _ { 1 } ( s z _ { 2 } ) } \approx \frac { s z _ { 2 } + \exp ( - s z _ { 2 } ) } { \exp ( - s z _ { 2 } ) } = 1 + s z _ { 2 } \exp ( s z _ { 2 } ) ,
$$

由式 (10)得

推论4.被分错样本与被分对样本之间的损失贡献比例会随着法向量的增长而指数级增长。

将分隔面附近样本称为边界样本。从推论 $1 ^ { \sim }$ 推论4可知，对损失函数的贡献比例，由大到小分顺序是：被分错的样本、被分对的边界样本、被分对的其它样本，它们之间的比例关系随着法向量的增长而迅速增大。适用逻辑回归的数据集，被最优分隔面分错的样本占比不大，这样被分错的样本通常会在分隔面附近。考虑到，在线性可分数据集上，法向量模长 $\lvert \mathbf { w } \rvert$ 趋向无穷大[11]，分隔平面几乎完全由边界样本决定。在线性不可分数据集上，法向量模长 $\lvert \mathbf { w } \rvert$ 有界[11]，但最优分隔面的法向量模长可能仍然很大，过拟合仍然严重。因此得出过拟合原因之一：边界样本的损失贡献比重大且随权重增长而加速增大。

自然界很多事件服从正态分布，例如图6，中心处样本密度大，能够很好在逼近其概率密度函数；在远离中心的边缘处，概率密度函数的值较小，样本稀疏，不能很好地反映其概率密度函数。考虑到训练集边界样本基本决定分隔平面，而测试集样本的实际分布与训练集会有一些差异，所以得到的分隔平面不能很好地分隔训练集。因此得到过拟合的原因之二：边界样本分布散乱。

第3节的2个过拟合例子都是根据这2个原因设计出来的。

![](images/1c726dd31ff9318cbd3ce6b13a82ae5cab43bb04e0fe934ef84f075d0a7ff48b.jpg)  
图6：一个服从正态分布的样本集

# 3.4 正则化的作用机理

缓解过拟合的常用手段是添加正则化项，各种各样的正则化方法的目标都是一致的：控制法向量的模长，不让 $\mathbf { \left| w \right| }$ 过大。由过拟合的成因可知，虽然法向量过大只是过拟合的表象，不是根本原因，但限制它的模长确实有效缓解了过拟合，这是因为它限制了边缘样本的损失贡献比重。正则化缓解过拟的同时，必然会降低训练集上的正确率。

从过拟合成因还可以知道缓解过拟合的另一个思路：修整边界样本使之准确反映概率密度函数。教科书[1]中已经写明增加样本数量能缓解过拟合，其实也可以用边界样本散乱的观点来解释：增加样本总量，边界样本数量也同比例增加，从而边界样本更好地反映其概率密度函数，从而缓解过拟合。

# 4反拉加速

图5画出了单个正样本(红色）和单个负样本（蓝色）的损失曲线。直观地理解，如果样本集是线性可分的，那么正样本对应的 $z _ { i }$ 越大，该样本上的损失函数值越小；负样本对应的 $z _ { i }$ 越小，该样本上的损失函数值越小。从而，在式(3)的计算过程中，负样本向 $z _ { i }$ 负无穷方向移动，正样本向 $z _ { i }$ 正无穷方向移动，达到了分类的目的。从过拟合成因的分析过程可知，对给定的 $\mathbf { w }$ 和 $\mid b \mid$ ，被错误分类的样本的损失贡献比重大，从而能优先减少分错样本的数量。

为了更快速地找到最优分隔面，索性进一步提高被分错样本的损失贡献，让错误更猛烈一些。

# 4.1 反拉方法

定义半正定(POsitive Semidefinite）函数

$$
\begin{array} { r } { \mathrm { p o s } ( z ) = \left\{ \begin{array} { l l } { 0 , } \\ { z , } \end{array} \right. } \end{array}
$$

和半负定(NEgtive Semidefinite）函数

$$
\begin{array} { r } { \mathrm { n e s } ( z ) = \left\{ \begin{array} { l l } { z , } & { \mathrm { \# I \# \# } z \leq 0 , } \\ { 0 , } & { \mathrm { \# I \# \# } z > 0 . } \end{array} \right. } \end{array}
$$

加权距离的计算方法保持不变，即

$$
z _ { i } = \mathbf { w } ^ { T } \mathbf { x } _ { i } + b .
$$

对加权距离进行反拉变换，得到

$$
Z _ { i } = \left\{ { \begin{array} { l l } { z _ { i } + \lambda { \mathrm { p o s } } ( z _ { i } ) , } & { { \mathfrak { H A } } \not \parallel \not \parallel y _ { i } = 0 , } \\ { z _ { i } + \lambda { \mathrm { n e s } } ( z _ { i } ) , } & { { \mathfrak { H A } } \not \parallel \not \parallel y _ { i } = 1 , } \end{array} } \right.
$$

这里的 $\lambda$ 称为反拉系数，取值范围是 $( - 1 , + \infty )$ 。将损失函数(2)替换为

$$
h ( z _ { i } ) = \left\{ \begin{array} { l l } { - \ln ( 1 - \sigma ( Z _ { i } ) ) , } & { \mathcal { H } \mathbb { H } \mathbb { H } } \\ { - \ln ( \sigma ( Z _ { i } ) ) , } & { \mathcal { H } \mathbb { H } \mathbb { H } } \end{array} { } y _ { i } = 0 , \right.
$$

从而样本集 $D$ 上的损失函数为

$$
H ( \mathbf { w } , b ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } h ( z _ { i } ) .
$$

求解它的最小值

$$
\begin{array} { r } { \{ \hat { \mathbf { w } } , \hat { b } \} = \underset { \mathbf { w } , b } { \arg \operatorname* { m i n } } H ( \mathbf { w } , b ) , } \end{array}
$$

就得到了最优参数和 $\hat { b }$ 。

由式(4.1)(4.1)知，在 $\lambda = 0$ 时， $h ( z _ { i } ) = l ( z _ { i } )$ 。图7中对比了逻辑回归损失函数 $l ( z )$ 和反拉后的损失函数 $h ( z )$ ，可以看到，当 $\lambda > 0$ 时，对被分错的样本，反拉后的损失更大了；当 $- 1 < \lambda < 0$ 时，对被分错的样本，反拉后的损失变小了一些，可以缓解过拟合。实际应用时，反拉系数 $\lambda$ 的选取需要多次试探，以便找到最优值。

损失函数 $h ( z )$ 的导数也容易求得

$$
\frac { \partial h ( z _ { i } ) } { \partial \mathbf { w } } = \left\{ \begin{array} { l l } { \sigma ( Z _ { i } ) [ 1 + \lambda \mathrm { p o s } ^ { \prime } ( z _ { i } ) ] \mathbf { x } _ { i } , } & { \mathrm { \# I I \# } \ y _ { i } = 0 , } \\ { [ \sigma ( Z _ { i } ) - 1 ] [ 1 + \lambda \mathrm { n e s } ^ { \prime } ( z _ { i } ) ] \mathbf { x } _ { i } , } & { \mathrm { \# I I \# } \ y _ { i } = 1 , } \end{array} \right.
$$

![](images/38647d78b7d00b00b0fc74f8e2fadc0bff3cfe03f7d7f37ece0b5dd4f99aa429.jpg)  
图7：反拉后的损失函数，蓝线对应负样本，红线对应正样本。 $\lambda = 0$ 时 $h ( z _ { i } )$ 就退化为 $l ( z _ { i } )$ 。

$$
\frac { \partial h ( z _ { i } ) } { \partial b } = \left\{ \begin{array} { l l } { \sigma ( Z _ { i } ) [ 1 + \lambda \mathrm { p o s } ^ { \prime } ( z _ { i } ) ] , } \\ { [ \sigma ( Z _ { i } ) - 1 ] [ 1 + \lambda \mathrm { n e s } ^ { \prime } ( z _ { i } ) ] , } \end{array} \right.
$$

这里的半正定函数的导数为

$$
\begin{array} { r } { \mathrm { p o s } ^ { \prime } ( z ) = \left\{ \begin{array} { l l } { 0 , } & { \mathcal { Y } \mathbb { H } \mathscr { R } \ z < 0 , } \\ { 1 , } & { \mathcal { Y } \mathbb { H } \mathscr { R } \ z \ge 0 . } \end{array} \right. } \end{array}
$$

半负定函数的导数为

$$
\begin{array} { r } { \mathrm { n e s } ^ { \prime } ( z ) = \left\{ \begin{array} { l l } { 1 , } & { \mathcal { Y } \mathbb { I } \mathbb { K } \ z \leq 0 , } \\ { 0 , } & { \mathcal { Y } \mathbb { I } \mathbb { K } \ z > 0 . } \end{array} \right. } \end{array}
$$

反拉加速只用于训练，不用于推测。一旦得到最优分隔面参数 $\hat { \mathbf { w } }$ 和 $\hat { b }$ ，仍然使用式(4)来推测样本的类别。

# 4.2 损失函数的数值稳定性

使用反拉方法后，对给定的正样本 $\mathbf { x } _ { i }$ 、法向量w 和截距 $\textit { b }$ ，如果 $z _ { i } < 0$ ，那么 $\lambda$ 越大 $\sigma ( Z _ { i } )$ 越接近于0，损失函数 $\ln ( \sigma ( Z _ { i } ) )$ 的数值计算越不稳定，很容易超出计算机的表示范围，得到结果NaN(Not A Number)。负样本的情形类似。

为了保持数值稳定，同时减少一点计算量，用式（6)近似计算式（4.1）中的 $\ln ( 1 - \sigma ( Z _ { i } ) )$ ，用式（7）近似计算式（4.1）中的 $\ln ( \sigma ( Z _ { i } ) )$ 。式(6)(4.1）中的常数 $C _ { 0 }$ 可以根据精度要求取值，例如$C _ { 0 } = 4 . 3$ 时，近似值与精确值之间的误差小于0.0001.

# 5 数值实验

反拉方法的设计目标是减少迭代次数，降低训练成本，额外收获是能够缓解过拟合。

反拉方法的本质是调整了各个样本的损失比重，不涉及正则项和最优化算法，因此只需要在最优化算法、正则项相同的情况下对比逻辑回归在使用反拉方法前后的性能。

MNIST数据集和CIFAR10数据集分别包含了10类样本，恰好可以任取2类样本组合起来测试反拉方法的性能。

# 5.1 加速MNIST训练

手写数字数据集 MNIST[12]包含0-9这个10 个数字的图片，图片大小为 $2 8 \times 2 8$ ，将2维单色图像拉平制作为1维向量。取任意两个数字的图片分别作为负样本、正样本进行训练，组合顺序依次为0-1、0-2、..、0-9、1-2、1-3、..、1-9、..、7-8、8-9，一共 45 种组合。每种组合训练 10次，然后训练下一种组合，共计训练 450次。训练使用负梯度下降法，步长指定为0.01，无正则化项，w 的初值从均匀分布 $U ( - 1 / { \sqrt { 7 8 4 } } , 1 / { \sqrt { 7 8 4 } } )$ 中随机选取， $b$ 的初值为0。最大迭代步数设为20000，LR最大正确率对应的迭代步数（称为 $L R$ 最优迭代步数），FLR迭代时到达LR最大正确率花费的迭代步数称为 $F \mathrm { L R }$ 最优迭代步数，如图8如示，用LR的最优迭代步数除以FLR的最优迭代步数就得到加速倍数，如图9所示。加速倍数为1意味着没有加速，加速倍数大于1意味有加速。从图9看出，加速倍数在 $1 3 . 1 0 \tilde { \mathrm { ~ } } 8 7 . 2 2$ 之间，平均值为38.25。反拉方法在训练集和测试集上正确分别为 $9 9 . 2 3 \%$ 和 $9 8 . 8 2 \%$ ，相对于未反拉时正确率的提升见图10，训练集上平均提高 $0 . 5 1 \%$ 测试集上平均提高 $0 . 1 4 \%$ 。

# 5.2 加速CIFAR10训练

手写数字数据集CIFAR10[13]包含10类彩色图片，图片大小为 $3 2 \times 3 2$ ，将2维彩色图像拉平制作为1维向量。取任意两类图片分别作为负样本、正样本进行训练，组合顺序依次为1-2、1-3、.、1-10、2-3、2-4、..、2-10、、8-9、9-10，一共 45 种组合。每种组合训练 10 次，然后训练下一种组合，共计训练450次。训练使用负梯度下降法，步长指定为0.0001，无正则化项，w的初值从均匀分布 $U ( - 1 / \sqrt { 3 0 7 2 } , 1 / \sqrt { 3 0 7 2 } )$ 中随机选取， $b$ 的初值为0。最大迭代步数设为20000,最优迭代步数如图11如示，加速倍数如图12所示。加速倍数在 $1 . 8 0 \tilde { \ } 9 . 0 6 \$ 之间，平均值为5.61。反拉方法在训练集和测试集上正确率均值分别为 $8 1 . 6 9 \%$ 和 $8 1 . 0 0 \%$ ，相对于未反拉时正确率的提升见图10，训练集上平均提高 $2 . 5 2 \%$ ，测试集上平均提高 $2 . 0 6 \%$ 。图 $1 1 ^ { \sim }$ 图13中未显示正确率出现大幅震荡的组合。

# 5.3 控制过拟合

在 3.1节的例子上应用反拉方法，取 $\lambda = - 0 . 9$ ，法向量初始值为 $\mathbf { w } = ( 1 / \sqrt { 2 } ; - 1 / \sqrt { 2 } )$ ，截距 $b = 0$ ，初始分隔线如图14中黑线所示。用负梯度下降法迭代求解式 (11)，迭代步长指定

![](images/e10c1dacbb0aa96f85f827ee49eaeeffa75648b2825c19aeb25ce1f978db03fd.jpg)  
图8：在MNIST上，LR最大正确率对应的训练次数，横轴是各个组合的编号。LR 表示未用反拉加速，FLR代表使用了反拉加速。

![](images/a56a14d83932e98cd106d891f6477fc5c4fdb35372b2723271efa354da04bd2a.jpg)  
图9：在MNIST上，反拉方法获得的加速倍数。

![](images/5a1d99c6dca3e2751330a1d84e0bfe47b44931250134643d08b01474d2d5048c.jpg)  
Difference of accuracy, $\lambda = 2 0$ （204   
图10：在MNIST上，反拉方法对正确率的影响。

![](images/52780569c883ae1c04030f10fe9bae193884f4e9e3cc5a4f6a363f7b5cd6b81a.jpg)

![](images/27df07389cb1c8045a5b363445a28b1e5174f96d1e4a127d4dae89ddc816c974.jpg)  
图12：在CIFAR10上，反拉方法获得的加速倍数。

![](images/ea81fa35031382d7ff10ed8b791dd11211d468566909aab42822553dad69af63.jpg)  
图11：在CIFAR10上，LR最大正确率对应的训练次数，横轴是各个组合的编号。  
图13：在CIFAR10上，反拉方法对正确率的影响。

FLR on linear separable datasets 。 train-negtive 3 。 train-positive test-negtive 2 test-positive E … · ： ........ 8 0···0-.·0·O·· # :0 8 / q :p: = +2 ： ：: 。 ： ： ：: -2 -3 -3 -2 -1 0 1 2 3 +

![](images/b37e32d2f565e920340a1695d00ba413a8518091c0ddedd9f219cd63f7c4744c.jpg)  
图14：线性可分训练集上， $\lambda = - 0 . 9$ 时反拉方法的训练效果。  
图15：在线性可能分训练集上，最优法向量W随 $\lambda$ 的变化情况，右上角的 $^ +$ 号代表13个相互接近的点。

为0.1，前后两步迭代的损失函数值小于 $\epsilon = 1 0 ^ { - 6 }$ 时停止迭代。洋红色虚线是迭代1281步后的分隔线，洋红色实直线是迭代2561步后停止时的最优分隔线。最优分隔线的斜截式方程为$4 . 1 0 6 6 x _ { 1 } + 0 . 0 7 1 8 x _ { 2 } + 1 . 5 2 3 7 \times 1 0 ^ { - 1 7 } = 0$ ，调整系数后的等价方程为 $x _ { 1 } + 0 . 0 1 7 5 x _ { 2 } + 3 . 7 1 0 5 \times 1 0 ^ { - 1 8 } =$ 0，与人眼观察的理想分隔线 $x _ { 1 } = 0$ 很接近。此时，反拉方法有效缓解了过拟合。

在3.1节的例子上应用反拉方法， $\lambda$ 在区间 $[ - 1 , 1 ]$ 上均匀取21个值，迭步长指定为0.1，前后两步迭代的损失函数值小于 $\epsilon = 1 0 ^ { - 6 }$ 时停止迭代。将所得的21个最优法向量W 绘制出来，得到图15。黑色带箭头直线是 $\lambda = - 1$ 时得到 $\hat { \mathbf { w } }$ ，洋红色带箭头直线是 $\lambda = 1$ 时得到w，折线上的 $^ +$ 号对应 $\lambda \in ( - 1 , 1 )$ 时得到的W。注意，这个线性不可分样本集的理想分隔线是 $x _ { 1 } = 0$ ，它的法向量 $\mathbf { w } = ( 1 ; 0 )$ 。从图15知， $\lambda = - 0 . 9$ 时的法向量方向与理想法向量最接近，随着 $\lambda$ 的增大，最优法向量与理想法向量的夹角越来越大，过拟合起来越严重。这个实验证明，反拉系数 $\lambda$ 能够控制线性可分数据集上的过拟合。

在3.2节的例子上应用反拉方法，取 $\lambda = - 0 . 8$ ，法向量初始值为 $\mathbf { w } = ( 1 / \sqrt { 2 } ; - 1 / \sqrt { 2 } )$ ，截距 $b = 0$ ，初始分隔线如图 16黑线所示。用负梯度下降法迭代求解式 (11)，迭代步长指定为0.1，前后两步迭代的损失函数值小于 $\epsilon = 1 0 ^ { - 6 }$ 时停止迭代。洋红色虚线是迭代1057步后的分隔线，洋红色实直线是迭代 2116步后停止时的最优分隔线。最优分隔线的斜截式方程为$3 . 8 3 5 6 x _ { 1 } - 0 . 0 1 4 0 x _ { 2 } + 0 . 0 2 0 8 = 0$ ，调整系数后的等价方程为 $x _ { 1 } - 0 . 0 0 3 7 x _ { 2 } + 0 . 0 0 5 4 = 0$ ，与人眼观察的理想分隔线 $x _ { 1 } = 0$ 很接近。此时，反拉方法有效缓解了过拟合。

在3.2节的例子上应用反拉方法， $\lambda$ 在区间 $[ - 1 , 1 ]$ 上均匀取21个值，代步长指定为0.1，前后两步迭代的损失函数值小于 $\epsilon = 1 0 ^ { - 6 }$ 时停止迭代。将所得的21个最优法向量W绘制出来，得到图17。黑色带箭头直线是 $\lambda = - 1$ 时得到w，洋红色带箭头直线是 $\lambda = 1$ 时得到w，折线上的 $^ +$ 号对应 $\lambda \in ( - 1 , 1 )$ 时得到的W。注意，这个线性不可分样本集的理想分隔线是 $x _ { 1 } = 0$ ，它的法向

FLR on linear unseparable datasets 3 。 train-negtive 。 train-positive test-negtive 2 test-positive 0 心 :: ： 8 88 0.0.0.0. O·0-0·0· +2 o.o ? 00。 X ::::o: 888 ： · 8： T · ： L · 0.060 : \* ： -2 -3 -3 -2 -1 0 1 2 3 +

![](images/d616402f68264fb834657f9e9978d7a0469e94f8d66c42f7b731a1b0df86c920.jpg)  
图16：线性不可分训练集上， $\lambda = - 0 . 8$ 时反拉方法的训练效果。  
图17：在线性不可能分训练集上，最优法向量w随 $\lambda$ 的变化情况。

量 $\mathbf { w } = ( 1 ; 0 )$ 。从图17， $\lambda = - 0 . 8$ 时的法向量方向与理想法向量最接近，随着 $\lambda$ 的增大，最优法向量与理想法向量的夹角越来越大，过拟合起来越严重。这个实验证明，反拉系数 $\lambda$ 能够控制线性不可分数据集上的过拟合。

# 6 总结与展望

本文用严格数学分析来解释逻辑回归过拟合现象，进而得到了加速训练过程的反拉方法和保证交叉熵数值稳定的近似方法。由过拟合原因的推导过程知道，反拉加速会导致更加严重的过拟合，必须采取应对措施。可以添加常规的正则项，也可以将反拉系数逐渐减至0以下。根据数值实验经验，反拉系数 $\lambda$ 过大时，正确率会降低，正确率曲线震荡。在实际应用中，应首先保证正确率曲线平滑，再追求加速性能。

反拉方法的加速效果看起来与样本集有一定的关联，其间的作用机理需要进一步研究。

# 参考文献

[1]周志华.机器学习.清华大学出版社，2016.4

[2] R.-E. Fan, K.-W. Chang, C.-J. Hsieh, X.-R. Wang,and C.-J. Lin. LIBLINEAR: A library for large linear classification Journal of Machine Learning Research 9(20o8), 1871-1874.   
[3] Simon Wiesler, Hermann Ney. A Convergence Analysis of Log-Linear Training. Advances in Neural Information Processing Systems，2011 :657-665   
[4] Sebastian Ruder. An overview of gradient descent optimization algorithms. arXiv:1609.04747 [cs.LG]   
[5] Brendan H., Holt G., Sculley D., Young M., Ebner D., Grady J., Nie L., Philips. T, Davydov E., Golovin D., Chikkerur S., Liu D., Wattenberg M., Hrafnkelsson A., Boulos T., Kubica J. (2013)Ad Click Prediction: a View from the Trenches. Proceedings of the 19-th KDD.   
[6] G.Andrew and J. Gao. Scalable training of ll-regularized log-linear models. In Proceedings of the 24th international conference on Machine learning, ICML’ O7, pages 33-40, New York, NY, USA, 2007. ACM.   
[7] C.-J.Lin and J. J. Mor e. Newton’ s method for large bound-constrained optimization problems. SIAM J. on Optimization, 9(4):1100-1127, Apr. 1999.   
[8] T.Hastie,R. Tibshirani,and J. Friedman.The Elements of Statistical Learning,Second Edition: Data Mining,Inference,and Prediction. Springer Series in Statistics.Springer,O002-2009. corr.3rd edition,Feb.2009.   
[9] P.Domingos.A unified bias-variance decomposition and its applications. In Proceedings of the Seventeenth International Conference on Machine Learning, pages 231-238, Stanford, CA, 2000.Morgan Kaufmann.   
[10] Pedro Domingos. A Few Useful Things to Know about Machine Learning. Communications of the ACM, Vol. 55 No. 10, Pages 78-87, 2012.   
[11]何沧平，对焦分类方法，[ChinaXiv:201711.02399]   
[12] Yann LeCun, Corinna Cortes, Christopher J.C.Burges.The MNIST database of handwritten digits. http://yann.lecun.com/exdb/mnist/   
[13] Alex Krizhevsky. The CIFAR-10 dataset. http://www.cs.toronto.edu/ kriz/cifar.html