# 单隐层神经网络输入权值的一种新算法

刘金澎，田大钢(上海理工大学 管理学院，上海 200093)

摘要：针对传统极端学习机输入权值与隐层阈值随机设定的问题，提出了输出值反向分配算法。算法在传统极端学习机的基础上，通过优化方法得到最优输出值分配系数，并利用最小二乘法确定网络输入参数。将本文算法应用到常用数据集进行实验，并与其他极端学习机改进算法进行比较，显示本文算法有良好的学习以及泛化能力，能够得到简单的网络结构，证明了算法的有效性。

关键词：极端学习机；单隐层神经网络；优化方法；输出值反向分配中图分类号：TP183 doi:10.3969/j.issn.1001-3695.2018.07.0418

# New algorithm for input weight of single hidden layer neural network

Liu Jinpeng, Tian Dagang (Business School, Universityof Shanghai for Science& Technology,Shanghai 20oo93,China）

Abstract:This paper proposedabackdistribution algorithm foroutput values,which was to solvetherandomseting problem aboutinput weightsand hiddenlayer thresholdson traditional extreme learning machine.Onthebasisof traditional extreme learning machine,thealgorithmobtains theoptimaloutput value distributioncoefcientthrough theoptimization method,and usesthe least squares method to determine the network input parameters.Experiments on common data sets show that,the proposed algorithm notonly achieves good learning and generalizationabilitycompared with other improved extreme learning machine algorithms,but also can obtain a simple network structure and it is effective.

Key words: extreme learning machine; single-hidden layer neural networks; optimization; output back distribution

# 0 引言

极端学习机（extreme learningmachine，ELM）由Huang等人2006年首次提出，是一种新型的单隐层前馈神经网络模型，其运算速度是传统前馈神经网络的数千倍，并且具有良好的泛化能力[1。ELM的核心思想是随机生成网络的输入权值和隐层阈值，并根据最小二乘法确定输出权值。但由于其隐层参数（输入权值和隐层阈值）的随机性，难以保证得到好的结果[2.3]。为找到最优网络参数，Zhu 等人提出了进化极端学习（evolutionaryELM，E-ELM)，其中输入权重和隐层阈值通过差分方法进行优化，输出权重使用Moore-Penrose（M-P）广义逆计算，该算法学习速度快，但推广能力较差[4]。Huang 等人提出一种增量极端学习机（incrementalELM，I-ELM)，有效的提高了网络学习速度，但测试精度稍差[5.6]。Rong 等人提出剪枝极端学习机（pruningELM，P-ELM)，该方法能够得到较好的测试精度以及简单的网络结构，但学习的时间相对较长[7]。Emilio 等人提出的贝叶斯极端学习机（BayesianELM,BELM)，提高了网络推广能力，但随机参数问题仍有待改进[8]。Han 等人采用混合学习算法来克服极端学习机的缺陷，利用改进后的粒子群极端学习机（Particle SwarmOptimization，PSO-ELM)来选择输入权值和隐层阈值，有较好的网络泛化能力，但模型结构复杂[9]。综合来看，针对ELM的讨论主要集中在两点：如何确定输入层与隐层之间的连接权以及如何确定隐层节点数。

本文主要针对ELM 随机选取输入层和隐含层之间的连接权（输入权值）及隐层阈值的问题，提出一种新的单隐层神经网络权值确定算法——输出值反向分配算法，利用优化方法确定输入权值。经过数值实验，得出输出值反向分配算法可以解决输入参数随机设定的问题，能够得到较好的推广能力。

# 1 基本理论

# 1.1单隐层前馈神经网络

单隐层前馈神经网络由输入层，单隐含层和输出层构成[10]。相邻层的节点由连接权重进行全连接，单隐层前馈神经网络能够表示成如下函数：

$$
\begin{array} { r } { f ( X ) = \sum _ { i = 1 } ^ { L } v _ { i } \varphi \big ( \sum _ { j = 1 } ^ { n } w _ { i j } x _ { j } + b _ { i } \big ) + v _ { 0 } = } \end{array}
$$

$$
\begin{array} { r } { \sum _ { i = 1 } ^ { L } v _ { i } \varphi \big ( { W } _ { i } ^ { T } \cdot X + b _ { i } \big ) + v _ { 0 } } \end{array}
$$

其中： $X = \ ( x _ { 1 }$ ， $x _ { 2 }$ ， $x _ { 3 }$ ，…， $x _ { n }$ ）T表示网络的n维输入向量，$\pmb { W _ { i } } \mathrm { = \ ( } \ b { w _ { i 1 } } \mathrm { , \ } \ b { w _ { i 2 } } \mathrm { , \ } \ \pmb { w _ { i 3 } } \mathrm { , \ } \cdots \mathrm { , \ } \ \pmb { w _ { i n } } \mathrm { ) }$ T表示输入层与隐层第 $i$ 个节点的连接权（即输入权值)，它的大小代表着各节点之间连接的强弱，$b _ { i }$ 是隐层第 $i$ 个节点的阈值(即隐层阈值)， $\mathbf { \Delta } _  \mathbf { \nu } _ { \mathbf { \lambda } } \mathbf { \nu } _ { \mathbf { \lambda } } \mathbf { \nu } _ { \mathbf { \lambda } } \mathbf { \nu } _ { \mathbf { \lambda } } \mathbf { \nu } _ { \mathbf { \lambda } \mathbf { \lambda } } \mathbf { \Lambda } _  \mathbf { \lambda } \mathbf { \Lambda } \mathbf { \Lambda } _  \mathbf { \lambda } \mathbf { \Lambda } \mathbf { \Lambda } \mathbf { \Lambda } _  \mathbf { \lambda } \mathbf { \Lambda } \mathbf { \Lambda } \mathbf { \Lambda } _  \mathbf { \lambda } \mathbf { \Lambda } \mathbf { \Lambda } \mathbf { \Lambda } _ { \mathbf { \lambda } \mathbf { \Lambda } \mathbf { \Lambda } \mathbf { \Lambda } _ { \mathbf { \lambda } \mathbf { \Lambda } \mathbf { \Lambda } \mathbf _ { \lambda } \mathbf { \Lambda \Lambda } \mathbf _ { \lambda \lambda } \mathbf { \Lambda \Lambda } \mathbf _ { \lambda \lambda } \mathbf _ { \lambda \lambda } \mathbf _ { \lambda \lambda } \mathbf { \Lambda \Lambda } _ \mathbf { \Lambda \Lambda } \left. \mathbf { \Lambda \Lambda } _ { \mathbf { \lambda } \mathbf { \Lambda \Lambda } \mathbf { \Lambda \Lambda }  } } }\right.$ 表示隐层第i个节点到输出层的连接权(即输出权值)， $\varphi ( \cdot )$ 表示隐层活化函数，本文使用Sigmoid 函数， ${ \pmb W } _ { i } \cdot { \pmb X }$ 表示 $\pmb { W } _ { i }$ 和 $\pmb { X }$ 的内积， $f ( X )$ 为网络输出。输出神经元的活化函数为线性函数，所以网络的输出权向量 $V { = } \ ( \nu _ { 1 } , \ \nu _ { 2 } , \ \cdots , \ \nu _ { L } ) ^ { ' }$ T可以根据最小二乘法求解，极端学习机就是这样求解的。但 $\mathbf { \Delta } _ { W }$ 和 $b$ 却不易求得，文献[6][7][8]都涉及到这个问题，本文将给出一种新的算法来确定隐层参数（ $( W$ $b$ 。

# 1.2极端学习机算法

设有任意的 $N$ 个样本 $( X _ { i } , \ Y ) , \ i = 1 , \ 2 , \ \cdots , \ N , \ X _ { i } = ( x _ { i 1 } ,$ （2$x _ { i 2 }$ ，…， $x _ { i n }$ ）T为网络的 $\mathfrak { n }$ 维输入向量， $\pmb { Y } \mathrm { = } \ ( \} _ { 1 } , \ y _ { 2 } , \ \cdots , \ y _ { N } )$ （204号T为 $N$ 个样本输出。则样本学习问题可以表达为：

$$
\begin{array} { r } { f ( \boldsymbol { X } _ { k } ) = \sum _ { i = 1 } ^ { L } \boldsymbol { v } _ { i } \varphi \big ( \boldsymbol { W } _ { i } ^ { \mathrm { T } } \cdot \boldsymbol { X } _ { k } + \boldsymbol { b } _ { i } \big ) + \boldsymbol { v } _ { 0 } \approx \boldsymbol { y } _ { k } , k = 1 , 2 , \cdots , N } \end{array}
$$

其中：选取合适的输出权重 $\mathbf { \Delta } _ { \nu _ { i } }$ 、输入权重 ${ \pmb W } _ { i }$ 以及隐层阈值 $b _ { i }$ 使得样本输出 $y _ { k }$ 与网络输出之间的误差尽量小。

因为网络输出函数为线性函数，所以式（2）就是关于 $\scriptstyle V =$ （v1，V2，…， $\nu _ { L }$ ）T的线性方程组。给定输入权值和隐层阈值后，输出权重可以通过求解线性方程组求得。

上述方程组可以简写为

$$
\mathrm { { H V = Y } }
$$

$\pmb { H }$ 记为

$$
\pmb { H } =
$$

$$
\left[ \begin{array} { c c c c c } { \boldsymbol { \varphi } \mathbf { \Sigma } ( \pmb { W } _ { 1 } ^ { \mathrm { T } } \cdot \pmb { X } _ { 1 } + b _ { 1 } ) } & & & { \dots } & { \boldsymbol { \varphi } \mathbf { \Sigma } ( \pmb { W } _ { L } ^ { \mathrm { T } } \cdot \pmb { X } _ { 1 } + b _ { L } ) } & & { 1 } \\ { \boldsymbol { \varphi } \mathbf { \Sigma } ( \pmb { W } _ { 1 } ^ { \mathrm { T } } \cdot \pmb { X } _ { 2 } + b _ { 1 } ) } & & & { \boldsymbol { \varphi } \mathbf { \Sigma } ( \pmb { W } _ { L } ^ { \mathrm { T } } \cdot \pmb { X } _ { 2 } + b _ { L } ) } & & { 1 } \\ { \vdots } & & { \ddots } & & { \vdots } & \\ { \boldsymbol { \varphi } \mathbf { \Sigma } ( \pmb { W } _ { 1 } ^ { \mathrm { T } } \cdot \pmb { X } _ { N } + b _ { 1 } ) } & { \dots } & { \boldsymbol { \varphi } \mathbf { \Sigma } ( \pmb { W } _ { L } ^ { \mathrm { T } } \cdot \pmb { X } _ { N } + b _ { L } ) } & & { 1 } \end{array} \right] _ { N \times \ ( L + 1 ) }
$$

$\pmb { H }$ 是式（2）的系数矩阵， $V = ( \nu _ { 1 } , \nu _ { 2 } , \cdots , \nu _ { L } ) ^ { \mathrm { ~ T ~ } }$ 是输出权值向量， ${ \pmb Y } = ~ ( y _ { 1 } , ~ y _ { 2 }$ ，，yv）T是样本的一维输出。容易知道，对几乎所有的W， $b$ ， $\pmb { H }$ 为列满秩矩阵。

特别地，当 $\scriptstyle { L = N - 1 }$ ，即隐层节点数等于样本个数时，只要隐层输出矩阵 $\pmb { H }$ 为非奇异矩阵，存在唯一的 $\boldsymbol { V }$ ，满足方程组(3)，因此，含有 $L$ （ $\scriptstyle \cdot { \cal L } = N - 1$ ）个隐层节点的单隐层前馈神经网络能够以零误差学会 $N$ 个样本[2,11],也就是网络输出与样本输出完全一致。但事实上样本数一般很大，若隐层节点数等于样本数，除了导致计算量很大之外，更主要地是会出现过拟合现象，网络的泛化能力降低[1]。

当 $L { < } N { - } 1$ ，即隐层节点小于样本数时，线性方程组（3）未知量个数少于方程个数，可以利用最小二乘法求解输出向量 $\smash { \vert \boldsymbol { V } _ { \perp } \vert }$ （204上述式（3）的最小二乘解为

$$
\mathrm { \Delta V { = } H ^ { + } Y { = } \ ( H ^ { T } H ) \ ^ { \ - 1 } H ^ { T } Y }
$$

其中 $\pmb { H } ^ { + } = \ ( \pmb { H } ^ { \mathrm { T } } \pmb { H } ) \ ^ { - 1 } \pmb { H } ^ { \mathrm { T } }$ 为 $\pmb { H }$ 的 $M / P$ 广义逆矩阵[12]。

极端学习机的基本步骤如下：

a）随机选择隐层参数（网络输入权值 ${ \pmb W } _ { i }$ 和隐层阈值 $b _ { i }$ ；b）根据隐层参数计算隐层输出矩阵 $H$ c）根据求解得到输出权值 $V .$ 0由上可见，极端学习机的一个主要难点就是解决W， $b$ 的选择问题。

# 2 基于ELM的输出值反向分配算法

取 $v _ { 0 } = 0$ 。设有任意的 $N$ 个样本 $( X _ { j } , Y _ { j } ) , j { = } 1 , 2 , \cdots ,$ （20$N , \ X _ { j } { = \ ( x _ { j 1 } , \ x _ { j 2 } , \ \cdots , \ x _ { j n } ) }$ T为网络的 $n$ 维输入向量， $\pmb { Y } \pmb { = } \ ( y _ { 1 }$ y2，…，yN）T为 $N$ 个样本输出。设隐层节点数为 $L$ ，隐层活化函数为Sigmoid函数， $V { = } \ ( \ \nu _ { 1 } , \ \nu _ { 2 } , \ \cdots , \ \nu _ { L } ) ^ { ' }$ I为输出权值， ${ \pmb W } _ { i }$ 表示输入向量与隐层第 $i$ 个节点的连接权（即输入权值)， $b _ { i }$ 是隐层第 $i$ 个节点的阈值 (即隐层阈值)。

取分配系数向量 ${ \bf \ddot { \boldsymbol { \alpha } } } = \left( \alpha _ { 1 } , \alpha _ { 2 } , \cdots , \alpha _ { L } \right) ^ { \mathrm { \scriptscriptstyle T } } , 0 \equiv { \alpha } _ { i } \equiv 1 , \mathrm { i } = 1 ,$ 2，…，L，令隐层节点i的输出为 $y \pmb { \alpha } _ { i }$ ，即

$$
\varphi \big ( \pmb { W } _ { i } ^ { \mathrm { T } } \cdot \pmb { X } + \pmb { b } _ { i } \big ) = y \pmb { \alpha } _ { i }
$$

则

$$
\pmb { W } _ { i } ^ { \operatorname { T } } \cdot \pmb { X } + b _ { i } = \varphi ^ { - 1 } ( y \pmb { \alpha } _ { i } )
$$

本文选取的活化函数为Sigmoid函数，该函数值域在（0，1)，为使 $\varphi ^ { - 1 } ( y \pmb { \alpha } _ { i } )$ 有定义，需要对样输出y进行转换，使其值在（0，1）之间。

将样本代入式（4)，可以得到如下方程组：

$$
\left\{ \begin{array} { l l } { \displaystyle \varphi \big ( { \pmb W } _ { i } ^ { \mathrm { T } } \cdot { \pmb X } _ { 1 } + b _ { i } \big ) = y _ { 1 } \alpha _ { i } } \\ { \displaystyle \varphi \big ( { \pmb W } _ { i } ^ { \mathrm { T } } \cdot { \pmb X } _ { 2 } + b _ { i } \big ) = \mathtt { y } _ { 2 } \alpha _ { i } } \\ { \vdots } \\ { \displaystyle \varphi \big ( { \pmb W } _ { i } ^ { \mathrm { T } } \cdot { \pmb X } _ { \mathrm { N } } + b _ { i } \big ) = \mathtt { y } _ { \mathrm { N } } \alpha _ { i } } \end{array} \right.
$$

再根据式（5）得到如下方程组：

$$
\left\{ \begin{array} { l l } { W _ { i } ^ { \mathrm { T } } \cdot X _ { 1 } + b _ { i } = \varphi ^ { - 1 } ( y _ { 1 } \pmb { \alpha } _ { i } ) } \\ { W _ { i } ^ { \mathrm { T } } \cdot X _ { 2 } + b _ { i } = \varphi ^ { - 1 } ( y _ { 2 } \pmb { \alpha } _ { i } ) } \\ { \qquad \vdots } \\ { W _ { i } ^ { \mathrm { T } } \cdot X _ { \mathrm { N } } + b _ { i } = \varphi ^ { - 1 } ( y _ { \mathrm { N } } \pmb { \alpha } _ { i } ) } \end{array} \right.
$$

当α给定时，式（6）是关于 $W$ ， $b$ 的线性方程组，所以可以通过最小二乘法确定输入权值 ${ \pmb W } _ { i }$ 和隐层阈值 $b _ { i }$ 。

为表述简洁，记上述方程组为

$$
\widetilde { \pmb { W } } _ { i } = \left( { \pmb { W } } _ { i } \right) , \widetilde { \pmb { X } } _ { j } = \left( { \pmb { \operatorname { \chi } } } _ { 1 } ^ { X _ { j } } \right)
$$

这里 $\pmb { W } _ { i }$ 是 $n { + } 1$ 维向量， $i { = } 1 , \ 2 , \ \cdots , \ L , \ \mathrm { X } _ { j }$ 是 $n { + } 1$ 维向量，$j { = } 1 , \ 2 , \ \cdots , \ N _ { \circ }$ 则

$$
\widetilde { \pmb { W } } = \left( \begin{array} { c c c c } { { \pmb { W } _ { 1 } } } & { { \pmb { W } _ { 2 } } } & { { \cdots } } & { { \pmb { W } _ { L } } } \\ { { { b } _ { 1 } } } & { { { b } _ { 2 } } } & { { \cdots } } & { { { b } _ { L } } } \end{array} \right) = ( \widetilde { \pmb { W } } _ { 1 } \widetilde { \pmb { W } } _ { 2 } \quad \cdots \quad \widetilde { \pmb { W } } _ { \mathrm { L } } )
$$

$$
{ \widetilde { X } } = { \binom { X _ { 1 } \quad X _ { 2 } \quad \cdots \quad X _ { N } } { 1 } } = ( { \widetilde { X } } _ { 1 } \quad { \widetilde { X } } _ { 2 } \quad \cdots \quad { \widetilde { X } } _ { N } )
$$

其中： $\widetilde { \pmb { W } }$ 是 $n { + } 1$ 行 $L$ 列矩阵， $\widetilde { \pmb { X } }$ 是 $n { + } 1$ 行 $N$ 列矩阵。网络隐层神经元输出矩阵 ${ \pmb H }$ 可记为

$$
\begin{array}{c} \begin{array} { r } { \pmb { H } = [ \begin{array} { c c c } { \pmb { ( \widetilde { W } _ { 1 } ^ { \mathrm { T } } \cdot \widetilde { X } _ { 1 } ) } } & & \\ { \pmb { ( \widetilde { W } _ { 1 } ^ { \mathrm { T } } \cdot \widetilde { X } _ { 2 } ) } } & & { \cdots } & \\ & { \vdots } & & { \ddots } \\ { \pmb { ( \widetilde { W } _ { 1 } ^ { T } \cdot \widetilde { X } _ { N } ) } } & & { \cdots } & \end{array} ] _ { N \times L } \cdot \widetilde { \pmb { X } } _ { 1 } ) } \\ { \pmb { \operatorname { \varphi } } \mathbf { ( } \widetilde { W } _ { 1 } ^ { T } \cdot \widetilde { X } _ { N } ) } & & { \cdots \quad \varphi \mathbf { ( } \widetilde { W } _ { L } ^ { T } \cdot \widetilde { X } _ { N } ) } \end{array} ] _ { N \times L } = \boldsymbol { \varphi } ( \widetilde { X } ^ { \mathrm { T } } \widetilde { \pmb { W } } )  \end{array}
$$

系数矩阵中，当 $\boldsymbol { A } = ~ ( a _ { i j } ) _ { \phantom { } _ { m \times n } }$ 时，用 $\varphi ( A )$ 表示矩阵$( \boldsymbol { \varphi } ( a _ { i j } ) ) _ { m \times n } \circ$

由此，方程式（6）可以简写为

$$
\widetilde { X } ^ { \mathrm { T } } \widetilde { \pmb { W } } _ { i } = \boldsymbol { \rho } ^ { - 1 } ( \pmb { Y } \pmb { \alpha } _ { i } )
$$

其中： $\varphi ^ { - 1 } ( { \cal Y } { \pmb \alpha } _ { i } ) = ~ ( \varphi ^ { - 1 } ( \mathrm { y } _ { 1 } { \pmb \alpha } _ { i } ) , ~ \varphi ^ { - 1 } ( \mathrm { y } _ { 2 } { \pmb \alpha } _ { i } ) , ~ \cdots$ ，φ-1(ynαi)）T。因此（7）式中的最小二乘解为

$$
\widetilde { \pmb { W } } _ { i } = \left( \widetilde { \pmb { X } } ^ { \mathrm { T } } \right) ^ { + } \varphi ^ { - 1 } ( \pmb { Y } \pmb { \alpha } _ { i } ) = \left( \widetilde { \pmb { X } } \widetilde { \pmb { X } } ^ { \mathrm { T } } \right) ^ { - 1 } \widetilde { \pmb { X } } \varphi ^ { - 1 } ( \pmb { Y } \pmb { \alpha } _ { i } )
$$

$$
i = 1 , \ 2 , \ \cdots , \ L
$$

式（8）是含有输出值分配系数向量 $\pmb { \alpha }$ 的表达式。确定 $\pmb { \alpha }$ ，使其在满足约束条件情况下，最小化下列目标函数：

$$
\begin{array} { r } { m i n \frac { 1 } { N } \left\| \sum _ { i = 1 } ^ { L } \pmb { v } _ { i } \varphi ( \widetilde { \pmb { X } } ^ { \mathrm { T } } \big ( \widetilde { \pmb { X } } ^ { \mathrm { T } } \big ) ^ { + } \varphi ^ { - 1 } ( \pmb { Y } \pmb { \alpha } _ { i } ) ) - \pmb { Y } \right\| ^ { 2 } } \end{array}
$$

这里取 $L _ { 2 }$ 范数。

这样，求解输入权值和隐层阈值的问题，就转换为求解含有输出值分配系数向量 $\pmb { \alpha }$ 的优化问题：

$$
\begin{array} { r } { \left\{ m i n \frac { 1 } { N } \left\| \sum _ { i = 1 } ^ { L } \pmb { v } _ { i } \varphi ( \widetilde { X } ^ { \mathrm { T } } \big ( \widetilde { X } ^ { \mathrm { T } } \big ) ^ { + } \varphi ^ { - 1 } ( { \pmb { Y } } { \pmb { \alpha } } _ { i } ) ) - { \pmb { Y } } \right\| ^ { 2 } \right. } \\ { 0 \le \pmb { \alpha } _ { i } \le 1 } \end{array}
$$

由式（9）可以求出最优的 $\pmb { \alpha }$ 。确定 $\pmb { \alpha }$ 以后，根据式（8）计算 $\widetilde { \pmb { W } } _ { i }$ ，再根据极端学习机算法求出 $V$

$$
\mathrm { V = H + Y = ( H T H ) { \cdot } l H T Y }
$$

$\begin{array} { r } { \mathop { \mathfrak { T } } e ( V , \alpha ) { = } \frac { 1 } { N } \left\| \sum _ { i = 1 } ^ { L } { \pmb v } _ { i } \varphi ( \widetilde { X } ^ { \mathrm { T } } \big ( \widetilde { X } ^ { \mathrm { T } } \big ) ^ { + } \varphi ^ { - 1 } ( Y { \pmb \alpha } _ { i } ) ) - Y \right\| ^ { 2 } } \end{array}$ 输出值反向分配算法的基本步骤如下：

输入： $X , \ Y , \ L , \ \varepsilon ;$ 输出：W、 $V$

a）随机选择输出权值 $V { = } ( \nu _ { 1 } { } ^ { 0 } , \nu _ { 2 } { } ^ { 0 } , \cdots , \nu _ { \mathrm { L } } { } ^ { 0 } ) ^ { \mathrm { T } } ;$ b）根据式（9）求出最优输出值分配系数向量 ${ \pmb { \alpha } } = \left( \alpha _ { 1 } ^ { 0 } \right.$ $\alpha _ { 2 } ^ { 0 } , \mathrm { ~ } \cdots , \alpha _ { L } ^ { 0 } \mathrm { } ) ^ { \mathrm { ~ T ~ } }$

c）根据式（8）计算输入权值和隐层阈值 $\widetilde { \pmb { W } } _ { i }$ d）由式（10）确定新的输出权值 $\smash {  { V _ { \circ } } }$ e）若 $e ( V , \ \pmb { \alpha } ) < \varepsilon$ ，则算法终止，否则返回步骤 $\boldsymbol { \mathbf { b } }$ ）

容易知道，以上算法显然是收敛的。事实上， $e ( V ^ { 0 } , \ \pmb { \alpha } ^ { 0 } ) \geq$ $e ( V ^ { 1 } , \alpha ^ { 0 } ) \geq e ( V ^ { 1 } , \alpha ^ { 1 } ) \geq e ( V ^ { 2 } , \alpha ^ { 1 } ) \geq \cdots \geq 0 \circ$

本文提出的输出值反向分配算法由于 $\boldsymbol { V }$ 是由最小二乘求得，保留了极端学习机的优点，同时 $w$ 是通过 $\pmb { \alpha }$ 用 $\widetilde { \pmb { W } } _ { i } =$ $\left( \widetilde { X } ^ { \mathrm { T } } \right) ^ { + } \boldsymbol { \phi } ^ { - 1 } ( \pmb { Y } \pmb { \alpha } _ { i } ) = \left( \widetilde { X } \widetilde { X } ^ { \mathrm { T } } \right) ^ { - 1 } \widetilde { X } \boldsymbol { \phi } ^ { - 1 } ( \pmb { Y } \pmb { \alpha } _ { i } )$ 算得， $\pmb { \alpha }$ 由优化算法求得，本文算法可望能够获得比随机选择好的结果。同时，在算法的计算结果中，如果某一个 $\pmb { \alpha } _ { i } = 0$ ，则相应的隐层节点可以删除，这使得该算法有选择隐层节点数的作用。

式（9）并不能保证是凸优化问题，但计算效果比较好，尤其对分类问题，其中的原因有待进一步研究。

# 3 数值实验

# 3.1实验数据

本文选取的实验数据均来源于UCI机器学习数据库[13]，该数据库中的数据均为实际问题的真实数据，并多被用于机器学习研究。本文选取了常用的Iris、Wine、PimaIndiansDiabetes和Wisconsin Breast Cancer 数据集、Heart、Balance Scale、Haberman'sSurvival 和UserKnowledge Modeling 数据集，其中测试样本均是随机选取所得，如表1所示。

表1数据集基本属性  

<html><body><table><tr><td>数据集名称</td><td>训练样本</td><td>测试样本</td><td>属性</td><td>分类</td></tr><tr><td>Iris</td><td>100</td><td>50</td><td>4</td><td>3</td></tr><tr><td>Wine</td><td>118</td><td>60</td><td>13</td><td>3</td></tr><tr><td>Pima I.D</td><td>538</td><td>230</td><td>8</td><td>2</td></tr><tr><td>Wisconsin B.C</td><td>379</td><td>190</td><td>30</td><td>2</td></tr><tr><td>Heart</td><td>180</td><td>90</td><td>13</td><td>2</td></tr><tr><td>Balance Scale</td><td>425</td><td>200</td><td>4</td><td>3</td></tr><tr><td>Haberman's S</td><td>204</td><td>102</td><td>3</td><td>2</td></tr><tr><td>User K.M</td><td>258</td><td>145</td><td>5</td><td>4</td></tr></table></body></html>

# 3.2 实验过程及结果

a）Iris数据集。该算例将样本分为三类，分别对应1、2、3。输出值反向分配算法中活化函数为Sigmoid函数，因此需要将样本数据的期望输出调整至（0，1)，根据下式进行转换：

$$
y _ { 0 = } \frac { y - m i n ( y ) } { m a x ( y ) - m i n ( y ) }
$$

$y _ { 0 }$ 为变换后的期望输出， $y$ 为原本样本期望输出。

应用本文输出值反向分配算法进行实验，构造含有三个隐层节点的单隐层网络，即式（2）中 $L { = } 3$ ，随机给定输出权值，将训练样本以及测试样本代入算法，根据上面所述的学习算法过程，求得最终网络输入权值

$$
W = \left( \begin{array} { c c c } { { - 0 . 0 7 8 0 } } & { { 0 . 0 8 2 4 } } & { { 0 . 0 8 2 4 } } \\ { { - 0 . 0 5 1 5 } } & { { 2 . 0 9 8 0 } } & { { 2 . 0 9 8 2 } } \\ { { 0 . 1 3 2 0 } } & { { - 0 . 1 7 8 4 } } & { { - 0 . 1 7 8 4 } } \\ { { 0 . 3 1 1 7 } } & { { 1 0 . 2 1 9 8 } } & { { 1 0 . 2 2 0 3 } } \end{array} \right) ^ { \mathrm { T } }
$$

隐层阈值 $b \mathrm { = } ( \mathrm { - } 2 7 . 4 8 3 5 \mathrm { - } 1 2 . 9 2 3 8 \mathrm { - } 1 2 . 9 2 4 5 ) ^ { \mathrm { T } }$ ，网络最终输出权值 $V = \ ( 1 . 1 6 2 5 { \times } 1 0 ^ { 1 2 } \ 2 . 2 3 3 4 { \times } 1 0 ^ { 3 } \ { - 2 . 2 3 3 3 \times } 1 0 ^ { 3 } ) ^ { \mathrm { ~ T ~ } }$ 0

b）Wine 数据集。该算例将样本分为3类，实验前，将类别进行如式（11）的转换，首先构造一个含有20个隐层节点的单隐层网络，根据本文的输出值反向分配算法进行学习，最后α1，α4，αg，α10，α13，α14，α15，α16，α17，α18均为零，删除对应的隐层节点，得到含有10个隐层节点的单隐层网络。网络输入权值为

<html><body><table><tr><td></td><td>−0.0094 8.4085 ×10-5 -0.0269</td><td>-0.0029 5.6784 × 10-4 -0.0078</td><td>-0.0028 4.3521× 10-4</td><td>-0.0028 4.9985× 10-4</td><td>-0.0016 0.0045</td><td>−0.0033 0.0014 -0.0085</td><td>-0.0033 0.0014</td><td>-0.0028 4.3188 × 10-4</td><td>-0.0028 4.6795× 10-4</td><td>-0.0033 0.0013</td></tr><tr><td colspan="16"></td></tr><tr><td rowspan="9">W=</td><td>0.0011</td><td></td><td>−0.0076 0.0010</td><td>-0.0076 0.0011</td><td>−0.0014 0.0022</td><td>0.0016</td><td>-0.0084 0.0016</td><td>−0.0076 0.0010</td><td>-0.0075 0.0011</td><td>-0.0085 0.0015</td></tr><tr><td>0.0031 1.4270 × 10-5</td><td></td><td></td><td></td><td>−8.3720 × 10-5</td><td>-2.0872 × 10-5</td><td>-2.2064 × 10-5</td><td></td><td></td><td></td></tr><tr><td></td><td>-5.9930 × 10-6</td><td>-3.6486 × 10-6</td><td>-4.8417 × 10-6</td><td></td><td>0.0102</td><td></td><td>-3.5667×10-6</td><td>-4.2894× 10-6</td><td>-1.8322 ×10-5</td></tr><tr><td>0.0156 -0.0243</td><td>0.0067</td><td>0.0060</td><td>0.0063 -0.0109</td><td>0.0185 -0.0399</td><td>-0.0193</td><td>0.0105 -0.0197</td><td>0.0060 -0.0104</td><td>0.0061</td><td>0.0097</td></tr><tr><td></td><td>−0.0117</td><td>−0.0104</td><td>−0.0092</td><td>−0.0408</td><td>-0.0176</td><td>−0.0181</td><td>-0.0086</td><td>-0.0106</td><td>-0.0182</td></tr><tr><td>−0.0178</td><td>−0.0100</td><td>−0.0087</td><td>0.0037</td><td>0.0101</td><td>0.0059</td><td>0.0060</td><td></td><td>-0.0089</td><td>−0.0164</td></tr><tr><td>0.0096</td><td>0.0039 0.0015</td><td>0.0036</td><td>0.0013</td><td>0.0070</td><td>0.0027</td><td>0.0028</td><td>0.0036 0.0012</td><td>0.0036</td><td>0.0056 0.0025</td></tr><tr><td>0.0022</td><td>-0.0024</td><td>0.0012 -0.0019</td><td>-0.0021</td><td>-0.0195</td><td>−0.0059</td><td>-0.0062</td><td>-0.0018</td><td>0.0013 -0.0020</td><td>−0.0054</td></tr><tr><td>−0.0145 -2.7572 ×10-4</td><td>-0.0068</td><td>-0.0061</td><td>-0.0064</td><td>−0.0223 -3.8219× 10-5</td><td>-0.0110 -2.6942×.10-5</td><td>−0.0113 -2.7344×10-5</td><td>-0.0061</td><td>-0.0062</td><td>−0.0104 2.6016×.10-5/</td></tr></table></body></html>

隐层阈值 $b =$ (-0.0390 0.0102-0.0471-0.0094 0.1210 0.08120.0835-0.0508-0.02340.0754）T，网络的输出权值 $\scriptstyle V =$ $( 7 . 0 6 9 3 \times 1 0 ^ { 5 } - 1 . 9 0 3 3 \times 1 0 ^ { 1 0 } 8 . 0 8 5 1 \times 1 0 ^ { 1 0 } 6 . 6 5 6 9 \times 1 0 ^ { 1 0 } - 8 . 4 7 1 3 \times 1 0 ^ { 5 }$ $- 2 . 1 4 9 7 { \times } 1 0 ^ { 1 0 } 1 . 2 7 9 8 { \times } 1 0 ^ { 1 0 } - 5 . 6 4 1 0 { \times } 1 0 ^ { 1 0 } )  { \mathrm { ~ \textrm ~ { ~ ~ } ~ } } _ { \circ }$ （204号

c）PimaIndiansDiabetes数据集。该算例的样本期望输出为0、1两类，首先构造一个含有10个隐层节点的单隐层网络，利用本文中的网络算法进行学习，得到 $\alpha _ { 3 }$ ， $\alpha _ { 4 }$ ， $\alpha _ { 5 }$ 都为零，所以删除对应的隐层节点，得到含有7个隐层节点的单隐层网络。网络输入权值为

<html><body><table><tr><td rowspan="7">W=</td><td>0.1450</td><td>0.1455</td><td>0.1467</td><td>0.4055</td><td>0.1369 0.0332</td><td>0.1389 0.0337</td><td>0.1341 0.0325</td></tr><tr><td>0.0352 -0.0133</td><td>0.0353 -0.0134</td><td>0.0356 -0.0135</td><td>0.0984 -0.0373</td><td>-0.0126</td><td>-0.0128</td><td>-0.0123</td></tr><tr><td>2.9216×10-4 -0.0011</td><td>2.9328 ×10-4 -0.0011</td><td>2.9559 ×10-4 -0.0012</td><td>8.1720 × 10-4 -0.0032</td><td>2.7582 ×10-4 -0.0011</td><td>2.7995 ×10-4 -0.0011</td><td>2.7030 ×10-4 -0.0011</td></tr><tr><td>0.0914</td><td>0.0918</td><td>0.0925</td><td>0.2558</td><td>0.0863</td><td>0.0876</td><td>0.0846</td></tr><tr><td>0.9595</td><td>0.9632</td><td>0.9708</td><td>2.6839</td><td>0.9095</td><td>0.9194</td><td>0.8877</td></tr><tr><td>0.0059</td><td>0.0060</td><td>0.0060</td><td>0.0166</td><td>0.0056</td><td>0.0057</td><td>0.0055</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

隐层阈值 b=(-16.5627 -16.5821 -16.6218 -25.6151 -$1 6 . 2 8 1 1 - 1 6 . 3 5 2 2 - 1 6 . 1 8 5 8 ) ^ { \mathrm { T } }$ ，网络的输出权值 $V { = } ( - 4 . 9 0 5 6 { \times } 1 0 ^ { 8 }$ （20 $5 . 8 2 4 9 \times 1 0 ^ { 8 }$ 行 $\cdot 1 . 2 4 7 6 { \times } 1 0 ^ { 8 }$ -0.1772 $- 7 . 7 6 0 7 \times 1 0 ^ { 7 }$ $9 . 5 4 1 1 \times 1 0 ^ { 7 }$ $1 . 5 0 3 2 \times 1 0 ^ { 7 } \$ T。

d）WisconsinBreastCancer数据集。该数据集样本分为良性和恶性两类，分别对应1和0，构造含有1个隐层节点的单隐层网络，得到的网络输入权值为 $W / = \ ( - 1 . 4 6 8 7 \times 1 0 ^ { - 1 0 } 6 . 5 6 6 6$ 0.1334-0.5236-0.0174-3.881563.0322-7.8507-31.6170-26.339318.1990-1.07470.4935 0.8863-0.0440-399.079426.5462 59.0644-122.0129 -204.8474 107.1777 -5.5983 -0.2940 0.0673 0.029719.86801.6532-9.6924-36.943221.4134-107.7062 )，隐层阈值$b { = } 4 0 . 6 5 4 8$ ，网络输出权值 $V { = } 1 . 0 2 6 9$ 。

e）Heart数据集。该数据集含有13个属性值，即为样本输入，样本输出为样本所属类别，该样本数据分为1、2两类。经过上述式（11）的转换以后，构造含有2个隐层节点的单隐层网络，得到的网络输入权值为

隐层阈值 $b \mathrm { = } ( \mathrm { - } 2 4 . 6 2 5 4 \mathrm { - } 3 . 4 9 2 1 ) ^ { \mathrm { T } }$ ，输出权值 $V { = } ( 2 . 5 7 6 3 { \times } 1 0 ^ { 1 0 }$ 0.4878)T。

f）Balance Scale、Haberman's Survival 和 User KnowledgeModeling数据集。BalanceScale数据集为多元分类，样本期望输出分别为-1、0和1;Haberman'sSurvival数据集为二元分类，样本期望输出分别对应1和2；UserKnowledgeModeling数据集为多元分类，样本期望输出分别对应1、2、3和4，在均进行如上式（11）的转换之后，分别构造含有4、2和7个隐层节点的单隐层网络进行学习。实验结果见表2。限于篇幅，略去了网络输入权值、隐层阈值和输出权值。

将网络输出值y进行四舍五入后得到 $y ^ { * }$ ，并与网络期望输出值进行比较，得到如下实验结果，如表2所示。

表2数据集实验结果  

<html><body><table><tr><td>数据集</td><td>RMSE</td><td>TestRMSE</td><td>训练精度</td><td>测试精度</td><td>节点数</td></tr><tr><td>Iris</td><td>0.2360</td><td>0.1975</td><td>95%</td><td>98%</td><td>3</td></tr><tr><td>Wine</td><td>0.1285</td><td>0.2035</td><td>100%</td><td>98.33%</td><td>10</td></tr><tr><td>Pima I.D</td><td>0.3974</td><td>0.3735</td><td>77.32%</td><td>79.57%</td><td>7</td></tr><tr><td>WisconsinB.C</td><td>0.1284</td><td>0.1850</td><td>97.89%</td><td>95.79%</td><td>1</td></tr><tr><td>Heart</td><td>0.3524</td><td>0.3787</td><td>85%</td><td>86.67%</td><td>2</td></tr><tr><td>Balance Scale</td><td>0.3585</td><td>0.3357</td><td>90.59%</td><td>94%</td><td>4</td></tr><tr><td>Haberman's S</td><td>0.4257</td><td>0.4408</td><td>73.04%</td><td>78.43%</td><td>2</td></tr><tr><td>User K.M</td><td>0.2349</td><td>0.2137</td><td>94.19%</td><td>98.62%</td><td>7</td></tr></table></body></html>

根据本文提出的算法对于以上8个算例的学习情况，在保证较低的训练误差以及测试误差情况下，能够得到较高的分类正确率。此外，在这些例子中，网络最多含有10个隐层节点，最少含有1个隐层节点，在计算过程中，网络取多个隐层节点进行实验，会出现某些 ${ \pmb { \alpha } } _ { k } = 0$ 的情况，这就意味着其对应的隐层节点可以删除。

以上实验数据皆为分类数据集，主要因为本文的算法为输出值反向分配算法。按照本文的思路，当样本是分类问题时，输出值只有少数几个数字，比较容易用几个 ${ \pmb { \alpha } } _ { k }$ 实现分配。所以算法对分类问题的效果比较好。而对于样本输出为连续值的回归数据集，拟合的效果比较差。

针对文中Iris、Wine、PimaIndiansDiabetes和WisconsinBreastCancer算例，将本文所提出的算法与其他文献中提出的多种改进的极端学习机算法：文献[14]中优化剪枝极端学习机(OP-ELM)，文献[15]中分层极端学习机（H-ELM）和传统极端学习机(ELM）、文献[16]中稀疏贝叶斯极端学习机（SBELM)

以及文献[17]中基于粒子群优化算法极端学习机（PSO-ELM)进行实验对比，如表3所示。

表3分类实验结果比较  

<html><body><table><tr><td>数据集</td><td>算法</td><td>测试精度</td><td>节点数</td></tr><tr><td rowspan="6">Iris</td><td>本文</td><td>98%</td><td>3</td></tr><tr><td>OPELM</td><td>95%</td><td>4~17</td></tr><tr><td>HELM</td><td>100%</td><td>N1=N2=20;</td></tr><tr><td></td><td></td><td>N3=200</td></tr><tr><td>ELM</td><td>92%</td><td>200</td></tr><tr><td>SBELM</td><td>98%</td><td>2.4×3</td></tr><tr><td rowspan="5">Wine</td><td>本文</td><td>98.33%</td><td>10</td></tr><tr><td>OPELM</td><td>90.7%</td><td>不详</td></tr><tr><td>HELM</td><td>100%</td><td>N1=N2=20;</td></tr><tr><td>ELM</td><td>95%</td><td>N3=500 500</td></tr><tr><td>SBELM</td><td>99.41%</td><td>3.3×3</td></tr><tr><td rowspan="8">Pima I.D</td><td>本文</td><td></td><td></td></tr><tr><td>OPELM</td><td>79.57%</td><td>7</td></tr><tr><td></td><td>74.9%</td><td>不详</td></tr><tr><td>HELM</td><td>80.47%</td><td>N1=N2=10; N3=200</td></tr><tr><td>ELM</td><td>76.95%</td><td>200</td></tr><tr><td>SBELM</td><td>78.66%</td><td>8</td></tr><tr><td>PSO-ELM</td><td>76.38%</td><td>10</td></tr><tr><td></td><td></td><td></td></tr><tr><td rowspan="3">Wisconsin B. C</td><td>本文</td><td>95.79%</td><td>1</td></tr><tr><td>OPELM</td><td>95.6%</td><td>不详</td></tr><tr><td>SBELM</td><td>97.22%</td><td>5.6</td></tr></table></body></html>

对比各个实验结果可以看出，本文算法与其他上述算法的精度大致相同。除了Wine数据集中，本文算法与SBELM算法的隐层节点数略有差异以外，对于其它数据集，本文算法所需的隐层节点数最少。根据统计学习理论，节点数少的网络推广能力更好的概率更大。

# 4 结束语

本文提出了一种输出值反向分配算法来求得单隐层神经网络的输入权值与隐层阈值。输入权值通过分配系数向量 $\pmb { \alpha }$ 确定，$\pmb { \alpha }$ 通过优化方法求得。实验结果表明，本文算法在保证有较好的学习质量情况下，可以获得结构比较简单的单隐层网络。

# 参考文献：

[1]Huang GuangBin,Zhu QinYu, Siew C K. Extreme learning machine: theory and applications [J].Neurocomputing,2006,70 (1-3): 489-501.   
[2]牛培峰，马云鹏，刘魏岩，等．极端学习机算法的改进及应用研究[J]. 燕山大学学报,2015(2):127-132.(Niu Peifeng,Ma Yunpeng,Liu Weiyan, et al. Improvement and application of extreme learning machine algorithm [J]. JourmalofYanshanUniversity,2015(2):127-132.)   
[3]卢海峰，卫伟，杨梦月．局部感知的类限制极限学习机[J/OL].计算机 应用研究,2018,35 (10).htp://www.arocmag.com/article/02-2018-10- 009.html.(Lu Haifeng,Wei Wei, Yang Mengyue.Receptive field classconstrained extreme learning machine.[J/OL]. Application Research of Computers,2018,35(10).http://www.arocmag.com/article/02-2018-10- 009. html.)   
[4]Zhu Qinyu, Qin A K, Suganthan PN,et al. Evolutionary extreme learning machine[J].Patern Recognition,2005,38(10):1759-1763.   
[5] Huang Guangbin,Chen Lei, SiewC.K. Universal approximation using incremental constructive feedforward networks with random hidden nodes [J].IEEE Transon Neural Networks,2006,17 (4): 879-892.   
[6]Huang Guangbin, Chen Lei. Convex incremental extreme learning machine [J].Neurocomputing,2007,70 (16-18): 3056-3062.   
[7]Rong HJ, Ong Y S,Tan AH,et al.A fast pruned-extreme learning machine for classfication problem [J].Neurocomputing,20o8,72: 359-366.   
[8]Soria Olivas E,Gomez Sanchis J,Martin JD,et al. BELM: Bayesian extreme learning machine[J].IEEE Trans on Neural Networks,2011,22 (3): 505-509.   
[9]Han F, Yao HF, Ling Q H.An improved evolutionary extreme learning machine based on particle swarm optimization [J]. Neurocomputing, 2013, 116: 87-93.   
[10] Hagan MT,Demuth HB.神经网络设计 [M].北京：机械工业出版社, 2002: 8-15.   
[11] Huang Gao,Huang Guangbin, Song Shiji,et al. Tends in extreme learning machines [J]. Neural Networks,2015,61(C): 32-48.   
[12] SerreD,Matries: Theory and Applications [M]. Spring,New York,2002:18- 32.   
[13] UCI Machine Learning Repository [DB/OL]. http://rchive.ics.uci. edu/ml/datasets. html.   
[14] Miche Y, Sorjamaa A,BasP,etal.OP-ELM: Optimally Pruned Extreme Learning Machine [J]. IEEE Trans on Neural Networks,2010,21(1):158- 162.   
[15] Tang Jiexiong，Deng Chenwei,Huang Guangbin. Extreme Learning Machine for Multilayer Perceptron [J]. IEEE Trans on Neural Networks and Learning Systems,2016,27 (4): 809-821.   
[16]Luo Jiahua, Vong C M, Wong P K. Sparse Bayesian Extreme Learning Machine for Multi-classification [J].IEEE Trans on Neural Networks and Learning Systems,2014,25 (4): 836-843   
[17]顾秀君．基于粒子群优化的极端学习机的研究及其应用[D].镇江：江 苏大学,2013.(Gu Xiujun. A Study of Extreme Learning Machine Based on Particle Swarm Optimization And Its Application [D]. Zhenjiang: Jiangsu University, 2013)