# 近似稀疏的低秩张量填充

喻高航；郑伟东；胡文玉\$

摘要：针对目前大多数的低秩张量填充(LRTC)模型存在过度稀疏而导致数据的细微特征被忽略的现象，本文借助框架变换和低秩矩阵分解，提出了一个基于近似稀疏的低秩张量填充(AS-LRTC)模型，进一步设计了块逐次上界极小化(BSUM)算法求解该模型．在一定条件下可以证明该算法的收敛性，大量的实验结果表明本文提出的算法比现有一些经典算法有明显的优势，

关键词：近似稀疏，低秩，张量填充，矩阵分解，框架变换

# 1引言

大数据时代每时每刻都在产生大量的高维数据，例如，电商交易数据、多传感器阵列数据、疾病基因表达数据、网络社交数据、视频监控、临床医学影像等．这些数据不仅规模大，维度高，还有着较为复杂的内在结构．若采用矩阵对数据进行表示，将会损坏数据的各维度的信息结构而造成较大的误差．张量(tensor)作为向量和矩阵的高维推广，是高维数据的一种自然表达形式．采用张量形式表示和处理高维数据已经在许多领域得到了广泛的应用，如图像/视频修复[1,2]、前景后景分离[3]、核磁共振图像恢复[4]、高光谱图像恢复[5,6]、视频去雨[7,8]以及信号重建[9]等,并且获得了很好的效果

张量填充是指从部分的观测数据中恢复完整的数据，可以被描述为一个张量数据缺失值估计问题(即填充问题)，是矩阵填充的高阶扩展.问题的关键是建立观测数据和缺失数据之间的联系[10]．低秩张量填充(Low-Rank Tensor Completion，简称LRTC)是利用真实张量的低秩先验来估计缺失数据，从数学上讲，低秩张量填充模型写成

其中 $\mathcal { V } \in \mathbb { R } ^ { d _ { 1 } \times \cdots \times d _ { N } }$ 是待恢复张量, $\mathcal { F }$ 是观测张量, $\Omega$ 是记录观测数据对应位置组成的集合， $\mathcal { P } ( \cdot )$ 是投影算子．张量的秩有多种不同的定义且不唯一，在张量秩的所有定义中，Tucker 秩被广泛用于低秩张量填充问题研究中[10-12]．然而,模型(1)中直接使用Tucker 秩进行求解是一个NP 难问题[13].

矩阵核范数(也称为迹范数或Ky Fan范数)是秩函数在矩阵谱范数单位球上凸包络，因此，通常利用核范数来逼近矩阵秩函数．受此启发，Liu 等人[10]首次提出了张量核范数的定义，即张量每个模矩阵的核

范数加权和：

$$
\parallel \mathcal { V } \parallel _ { * } = \sum _ { n = 1 } ^ { N } \alpha _ { n } \| Y _ { ( n ) } \| _ { * } .
$$

其中 $\alpha _ { n } > 0$ 且 $\begin{array} { r } { \sum _ { n = 1 } ^ { N } \alpha _ { n } = 1 } \end{array}$ ， $Y _ { ( n ) }$ 表示张量 $y$ 第 $\overset { \cdot } { n }$ 模式展开的矩阵， $\| \cdot \| _ { * }$ 表示矩阵核范数．基于张量核范数的定义，他们提出了如下张量填充模型:

$$
\operatorname* { m i n } _ { y } \sum _ { n = 1 } ^ { N } \alpha _ { n } \| Y _ { ( n ) } \| _ { * }
$$

之后，很多有效的算法被提出来求解上述凸优化问题.例如，文献[10]设计了三种求解算法(SiLRTC、FaLRTC 和HaLRTC),而Gandy等人[14]提出了基于Douglas-Rachford 分裂算法和交替方向乘子法(ADMM)的求解算法

然而，Romera-Paredes 等人[15]证明了张量每个模矩阵的核范数加权和并不是张量展开矩阵秩的和 的最紧凑凸包．于是,有学者考虑非凸优化模型，如Li等人[16]提出了基于矩阵 $p { \cdot }$ -范数的非凸松弛模型:

$$
\operatorname* { m i n } _ { \mathcal { V } } \sum _ { n = 1 } ^ { N } \alpha _ { n } \| Y _ { ( n ) } \| _ { p , \varepsilon } ^ { p }
$$

其中 $\varepsilon > 0 , p \in ( 0 , 1 )$ ．而Ji等人[17]提出了基于每个模式展开的非凸对数函数模型:

$$
\operatorname* { m i n } _ { y } \sum _ { n = 1 } ^ { N } \alpha _ { n } \mathrm { l o g d e t } ( ( Y _ { ( n ) } Y _ { ( n ) } ^ { T } ) ^ { 1 / 2 } + \varepsilon _ { n } I _ { n } )
$$

其中 $\varepsilon _ { n } > 0$ ．文献[17]将对数函数进行线性化处理，应用了ADMM方法求解模型，但未分析算法的收敛性

Mu等人[18]证明了张量每个模核范数的和实质上是次优的，并提出了新的凸松弛方法，即方处理(Square Deal)．相对于张量核范数，方处理要求更少的观察样本可以得到可靠的恢复结果.进一步，Nie[19]证明了在一定条件下，张量方处理所得矩阵的秩可以与张量的CP 秩相等．基于方处理，Bai 等人[20]提出了一个修正的约束张量填充模型，并建立了其误差边界.

$$
\operatorname* { m i n } _ { \boldsymbol { y } } \sum _ { n = 1 } ^ { N } \| \mathcal { Y } _ { \lfloor j \rfloor } \| _ { * } - \langle F ( \tilde { \mathcal { Y } } _ { \lfloor j \rfloor } ) , \mathcal { Y } _ { \lfloor j \rfloor } - \tilde { \mathcal { Y } } _ { \lfloor j \rfloor } \rangle
$$

其中 $\tilde { \mathcal { V } } \in R ^ { n _ { i _ { 1 } } \times \cdots \times n _ { i _ { N } } }$ 一个张量,通过将 $y$ 的模 $\cdot i _ { k }$ 重标记为模 $k ( k = 1 , 2 , \cdots , N )$ ， $j \in \{ 1 , 2 , \cdots , N \}$ 和置换 $( i _ { 1 } , \cdots , i _ { n } )$ ，使 $\begin{array} { r } { { \bf \nabla } _ { n ( 1 ) } : = \prod _ { k = 1 } ^ { j } n _ { i _ { k } } } \end{array}$ 尽可能接近 $\begin{array} { r } { n _ { ( 2 ) } : = \prod _ { k = j + 1 } ^ { N } n _ { i _ { k } } } \end{array}$ ， $\mathcal { V } _ { \lfloor j \rfloor } = r e s h a p e ( \tilde { \mathcal { V } } _ { ( 1 ) } , n _ { ( 1 ) } , n _ { ( 2 ) } ) .$ （20号

上述介绍的方法在求解过程中需要进行矩阵的奇异值分解(SVD)，随着维数的增加，这在时间和存储上都是高消耗. $\mathrm { { X u } }$ 等人[21]将低秩矩阵分解的矩阵填充模型[22]推广到低秩张量填充模型,通过并行地对张量 $y$ 沿所有模式展开的矩阵应用低秩矩阵分解：

$$
\operatorname* { m i n } _ { y , A , X } \sum _ { n = 1 } ^ { N } \frac { \alpha _ { n } } { 2 } \| Y _ { ( n ) } - A _ { n } X _ { n } \| _ { F } ^ { 2 }
$$

其中 $Y _ { ( n ) } \approx A _ { n } X _ { n }$ ， $A = ( A _ { 1 } , \cdot \cdot \cdot , A _ { N } )$ ， $\boldsymbol { X } = ( X _ { 1 } , \cdots , X _ { N } )$ ．该方法称为TMac[21],获得比FaLRTC 更快的时间效率和更好的性能.

实际数据不仅限于其低秩特性，往往还具有分段光滑的性质．在模型(3）中, $X _ { 3 }$ 在实际应用中具有清晰的物理意义，例如：视频数据表现为数据的空间信息结构，常常表现出分段光滑的性质．特别地，全变分(Total Variation,TV)能够很好地刻画分段光滑性质,并且在很多应用中取得了显著的效果[4,23-25].针对实际应用中 $X _ { 3 }$ 表现出的分段光滑的特性,Ji等人[26]将TV 正则项与低秩张量填充相结合,提出如下模型:

$$
\operatorname* { m i n } _ { y , X , A } \sum _ { n = 1 } ^ { 3 } \frac { \alpha _ { n } } { 2 } \| Y _ { ( n ) } - A _ { n } X _ { n } \| _ { F } ^ { 2 } + \mu \mathrm { T V } ( X _ { 3 } )
$$

其中 $\mu > 0$ 是正则参数， $\textstyle \sum _ { n = 1 } ^ { 3 } \alpha _ { n } = 1$ ， $A = ( A _ { 1 } , A _ { 2 } , A _ { 3 } )$ ， $\boldsymbol { X } = ( X _ { 1 } , X _ { 2 } , X _ { 3 } )$ ， $\mathrm { { T V } } ( X _ { 3 } )$ 表示 $X _ { 3 }$ 的全变分.  
由于TV正则项通常会导致阶梯伪影，因子图像的细节和几何特征在模型(4)中不能很好的保留.

在实际应用中,细节和几何结构具有重要的地位.特别地，框架变换是一组正交基的生成,放宽了正交性和线性无关性的要求，它的冗余具有保留几何特征和细节的能力.基于此,Jiang 等人[27]将框架变换正则项引入到张量填充问题中，得到优于模型(4)模的效果，其模型如下:

$$
\operatorname* { m i n } _ { y , X , A } \sum _ { n = 1 } ^ { 3 } \frac { \alpha _ { n } } { 2 } \| Y _ { ( n ) } - A _ { n } X _ { n } \| _ { F } ^ { 2 } + \lambda \| W X _ { 3 } ^ { T } \| _ { 1 , 1 }
$$

其中 $\lambda > 0$ 是正则参数，W是框架变换矩阵，满足 $W ^ { T } W = I$ ．模型(4)和模型(5)的目标函数不是关于变量 $( X , A , { \mathcal { Y } } )$ 的联合凸函数，但是关于变量 $X , A , \mathcal { Y }$ 的子函数是凸的．因此，采用块逐次上界极小化算法进行求解，且具有收敛性保证.

然而，图像经过框架变换后的系数向量通常是近似稀疏而非完全稀疏，在模型(5)中采用 $l _ { 1 }$ 范数会导致恢复的因子图像 $X _ { 3 }$ 的微妙特征被忽略掉.因此，在图像修复问题中，Shen等人[28]采用框架变换的软阈值算子，以及对 $l _ { 0 }$ 范数采用加权 $l _ { 1 }$ 范数进行近似，最后建立了近似稀疏的修复模型，得到了优于 $\cdot l _ { 1 }$ 范数正则化的修复模型．受此启发，本文对模型(5)进行改进，提出一个近似稀疏的低秩张量填充模型．在此基础上，基于块逐次上界极小化算法(Block Successive Upper-bound Minimization，简称BSUM)设计了快速有效的优化算法，并给出了算法的收敛性证明．同时，通过数值实验来说明本文算法的优越性

本文内容结构安排如下：第二章回顾了有关预备知识，如张量的基础知识、框架变换、不动点算法和BSUM算法的一些初步知识等．第三章给出了一个近似稀疏张量填充模型，并基于BSUM算法与临近不动点算法，并分析了算法的收敛性;第四章给出了数值实验;最后一章总结全文.

# 2 张量基础与预备知识

本章首先将介绍相关记号及涉及到的有关张量基础知识[29]，同时还将简要介绍本文用到的相关算法和框架变换理论.

# 2.1 相关记号

本文采用希腊字母表示标量，例如： $\alpha , \beta , \mu$ ；粗体小写字母表示向量，例如：a,b；大写字母表示矩阵,

例如：X,Y；花体字母表示张量,例如: $x , y$ ；空心字母表示集合，例如: $\mathbb { R }$ 表示实数空间．特别地, $\Omega$ 表示观测数据中已知元素的位置，即若 $\Omega _ { i _ { 1 } , \cdots , i _ { N } } = 1$ ，则表示数据中第 $( i _ { 1 } , \cdots , i _ { N } )$ 个元素已知；若 $\Omega _ { i _ { 1 } , \cdots , i _ { N } } = 0$ 则表示相应位置元素缺失,张量X的第(𝑖i,,iN）个元素记为xi,…,iN

集合 $\mathbb { S }$ 的指示函数 $\iota _ { \mathbb { S } }$ ，定义为：

$$
\iota _ { \mathbb { S } } ( x ) = { \left\{ \begin{array} { l l } { 0 , } & { x \in \mathbb { S } ; } \\ { \infty , } & { { \stackrel { \mathrm { H } } { \div } } { \stackrel { \cdot } { \mathbb { E } } } . } \end{array} \right. }
$$

指标张量 $\Omega$ 上的投影算子记为 $\mathcal { P } _ { \Omega }$ ，定义为：

$$
\begin{array} { r } { ( P _ { \Omega } ( \boldsymbol { \mathcal { X } } ) ) _ { i _ { 1 } , \cdots , i _ { N } } = \left\{ \begin{array} { l l } { x _ { i _ { 1 } , \cdots , i _ { N } } , } & { \Omega _ { i _ { 1 } , \cdots , i _ { N } } = 1 ; } \\ { 0 , } & { \mathrm { ~ \# \it { \dot { \mathcal { C } } } . } } \end{array} \right. } \end{array}
$$

# 2.2 张量的定义与运算

张量(tensor）定义为一个多维数组，是向量和矩阵在多维空间中的推广，数据的维度称为张量的阶.下面我们介绍张量中涉及的一些概念以及张量与矩阵的相互转化关系.

![](images/e1a80697acf49f37f1837ff725aa2d9a9b280fbf228685b872cd3a5a1f21513e.jpg)  
图1：一阶、二阶、三阶张量

定义2.1(张量纤维(fiber)）纤维是指从张量中抽取向量的操作.张量纤维是由矩阵行、列概念的高维推广．在矩阵中固定其中一个维度，可以得到行或者列．类似于矩阵操作，张量第 $n$ 维度纤维(mode $\boldsymbol { \cdot } \boldsymbol { n }$ fiber）定义为固定张量其它维度指标不变，只保留张量第 $n$ 维度指标变化生成的向量.

特别地，矩阵的模-1纤维是矩阵的列，模-2纤维是矩阵的行，三维张量的模-1、-2、-3纤维分别称为列(column)、行(row）和管(tube).

![](images/b9c1b48065f6d3e3652a9abd2b32753b888e3cc4d745ac81d683a2ec9316daf4.jpg)  
图2：三阶张量的模-n纤维

定义2.2(张量切片(slice)）切片操作是指在张量中抽取矩阵的操作．在张量中如果保留两个维度变化，其它的维度不变可以得到一个矩阵，这个矩阵即为张量切片.

![](images/f6317d5f33a30c9e710ecc354c16ad6b3224db339f5223ce7ac66e3e81a13804.jpg)  
图3：三阶张量的切片

特别地,三阶张量 $\mathcal { X } \in R ^ { I _ { 1 } \times I _ { 2 } \times I _ { 3 } }$ 三个维度的切片分别为 $X _ { i : : } , X _ { : j : } , X _ { : : k }$ ,分别记为水平切片(horizontalslice)、侧向切片(lateral slice)、正向切片(frontal slice).

定义2.3（张量矩阵展开(Unfolding-Matricization)）张量 $\mathcal { X } \in \mathbb { R } ^ { d _ { 1 } \times d _ { 2 } \dots \times d _ { N } }$ 的矩阵展开是将一个张量的元素重新排列(即对张量的模 $- n$ 纤维按字典顺序重新排列)，得到一个矩阵的过程．张量在第 $n$ 维度上的展开矩阵表示为 $X _ { ( n ) } = u n f o l d _ { n } ( { \mathcal { X } } ) \in R ^ { d _ { n } \times \prod _ { i \neq n } d _ { i } }$ ．其中张量的第 $( i _ { 1 } , \cdots , i _ { N } )$ 个元素映射到展开矩阵的第 $( i _ { n } , j )$ 个元素，满足

$$
j = 1 + \sum _ { k = 1 , k \ne n } ^ { N } ( i _ { k } - 1 ) J _ { k } , J _ { k } = \prod _ { m = 1 , m \ne n } ^ { k - 1 } d _ { m } .
$$

定义2.4（张量内积(Inner product)）两个相同大小张量的内积 $\langle \cdot , \cdot \rangle$ 定义为它们对应元素的乘积之和，即

$$
\langle \mathcal { X } , \mathcal { Y } \rangle = \sum _ { i _ { 1 } , i _ { 2 } \cdots , i _ { N } } x _ { i _ { 1 } , i _ { 2 } \cdots , i _ { N } } y _ { i _ { 1 } , i _ { 2 } \cdots , i _ { N } } .
$$

特别地，张量的Frobenius 范数与矩阵的Frobenius 范数相同，即所有元素的平方和开方： $\| \mathcal { X } \| _ { F } =$ $\begin{array} { r } { \sqrt { \langle \mathcal { X } , \mathcal { X } \rangle } = \sqrt { \sum _ { i _ { 1 } , i _ { 2 } \cdots , i _ { N } } | x _ { i _ { 1 } , i _ { 2 } \cdots , i _ { N } } | ^ { 2 } } . } \end{array}$ （204号

定义2.5（张量Tucker 秩）张量 $\mathcal { X } \in \mathbb { R } ^ { d _ { 1 } \times d _ { 2 } \dots \times d _ { N } }$ 的第 $n$ 维展开矩阵的秩定义为：

$$
r a n k _ { n } ( { \mathcal { X } } ) = r a n k ( X _ { ( n ) } ) .
$$

令 $\mathit { r a n k } _ { n } ( \mathcal { X } ) = r _ { n } , n = 1 , 2 , \cdot \cdot \cdot , N$ ，则张量 $\chi$ 的Tucker 秩定义为：

$$
r a n k _ { t } ( { \mathcal { X } } ) = ( r _ { 1 } , r _ { 2 } , \cdot \cdot \cdot , r _ { N } ) .
$$

# 2.3 BSUM算法

假设 $X = X _ { 1 } \times X _ { 2 } \times \cdot \cdot \cdot \times X _ { n }$ 且 $X _ { i } \subset \mathbb { R } ^ { m _ { i } }$ ，变量 $\mathbf { x } \in X$ 可视为 $\mathbf { x } = \left( \mathbf { x } _ { 1 } , \mathbf { x } _ { 2 } , \cdots , \mathbf { x } _ { n } \right)$ ，其中第i分块变量 $\mathbf { x } _ { i } \in X _ { i }$ ．考虑如下的优化问题:

$$
\begin{array} { c } { { m i n \quad f ( { \bf x } ) } } \\ { { s . t \quad { \bf x } \in X . } } \end{array}
$$

令 $\begin{array} { r } { u _ { i } ( \mathbf { x } _ { i } , \mathbf { x } ^ { k } ) = f ( \mathbf { x } _ { 1 } ^ { k } , \cdot \cdot \cdot , \mathbf { x } _ { i } , \cdot \cdot \cdot , \mathbf { x } _ { n } ^ { k } ) + \frac { \rho } { 2 } \| \mathbf { x } _ { i } - \mathbf { x } _ { i } ^ { k } \| _ { 2 } ^ { 2 } } \end{array}$ ，其中 $\rho > 0 , i = 1 , \cdot \cdot , n$ .BSUM算法每一次更新

单个变量块，不断循环进行如下 $\overset { \cdot } { n }$ 步迭代，直到满足一定的收敛条件.

$$
\left\{ \begin{array} { l l } { s t e p \ 1 : \mathbf { x } _ { 1 } ^ { k + 1 } = a r g m i n \ u _ { 1 } ( \mathbf { x } _ { 1 } , \mathbf { x } _ { ( 1 ) } ^ { k } ) , } \\ { \begin{array} { l l } { \mathbf { x } _ { 1 } \in \mathbf { X } _ { 1 } } \\ { s t e p \ 2 : \mathbf { x } _ { 2 } ^ { k + 1 } = a r g m i n \ u _ { 2 } ( \mathbf { x } _ { 2 } , \mathbf { x } _ { ( 2 ) } ^ { k } ) , } \\ { \quad } \\ { \quad } \\ { \vdots } \\ { s t e p \ n : \mathbf { x } _ { n } ^ { k + 1 } = a r g m i n \ u _ { n } ( \mathbf { x } _ { n } , \mathbf { x } _ { ( n ) } ^ { k } ) , } \end{array} } \end{array} \right.
$$

在满足适当条件下，可以证明BSUM算法按坐标收敛：

引理2.1（[30]）设 $u ( { \mathbf { x } } , { \mathbf { x } } ^ { k - 1 } )$ 是 $f ( x )$ 在 $x ^ { k - 1 }$ 处的近似函数，若满足以下条件：

$$
\left\{ \begin{array} { l } { u _ { i } ( \mathbf { y } _ { i } , \mathbf { y } ) = f ( \mathbf { y } ) , \forall \mathbf { y } \in \mathcal { X } , \forall i ; } \\ { u _ { i } ( \mathbf { y } _ { i } , \mathbf { y } ) \geq f ( \mathbf { y } _ { 1 } , \mathbf { y } _ { 2 } , \cdots , \mathbf { y } _ { i - 1 } , \mathbf { x } _ { i } , \mathbf { y } _ { i + 1 } , \cdots , \mathbf { y } _ { n } ) , \forall \mathbf { x } _ { i } \in \mathcal { X } _ { i } , \forall \mathbf { y } \in X , \forall i ; } \\ { u _ { i } ^ { \prime } ( \mathbf { x } _ { i } , \mathbf { y } ; \mathbf { d } _ { i } ) | _ { \mathbf { x } _ { i } = \mathbf { y } _ { i } } = f ^ { \prime } ( \mathbf { y } ; \mathbf { d } ) , \forall \mathbf { d } = ( 0 , \cdots , \mathbf { d } _ { i } , \cdots , 0 ) ~ s . t . ~ \mathbf { y } _ { i } + \mathbf { d } _ { i } \in X _ { i } , \forall i ; } \\ { u _ { i } ( \mathbf { x } _ { i } , \mathbf { y } ) \nVdash ( \mathbf { x } _ { i } , \mathbf { y } ) ~ \mathcal { H } \land \ncong \mathit { x } _ { i } \ncong \mathit { x } _ { i } \ncong \mathit { y } , \forall i = 1 , \cdots , n , } \end{array} \right.
$$

其中 $u _ { i } ( \mathbf { x } _ { i } , \mathbf { y } )$ 是关于第 $i$ 个块的子问题， $f ^ { ' } ( \mathbf { y } ; \mathbf { d } )$ 是函数 $f$ 在y 处d方向的方向导数．假设 $u _ { i } ( \mathbf { x } _ { i } , \mathbf { y } )$ 是关  
于 $\mathbf { \ddot { x } } _ { i } ( i = 1 , \cdots , n )$ 的拟凸函数，且每个子问题argmin $u _ { i } ( { \bf x } _ { i } , { \bf x } ^ { k - 1 } ) , s . t . { \ x } \in X _ { i }$ 在任意点 $\mathbf { x } ^ { k - 1 } \in X$ 处均$\mathbf { x } _ { i }$   
有唯一解，则由BSUM算法产生的点列按坐标收敛到问题(7)的极小值点.

# 2.4 框架变换(framelet变换)

如果系统 $X \in L _ { 2 } ( \mathbb { R } )$ 满足

$$
f = \sum _ { g \in X } \langle f , g \rangle g , \forall f \in L _ { 2 } ( \mathbb { R } ) ,
$$

则称之为 $L _ { 2 } ( \mathbb { R } )$ 的紧框架，其中 $\langle \cdot , \cdot \rangle$ 是 $L _ { 2 } ( \mathbb { R } )$ 的内积.而小波系统 $X ( \Psi )$ 定义为由以下有限集合的扩张和仿射集合： $\Psi = \{ \psi _ { 1 } , \psi _ { 2 } , \cdot \cdot \cdot , \psi _ { r } \} \in L ^ { 2 } ( R )$ 定义.

$$
X ( \Psi ) = \{ 2 ^ { k / 2 } \psi _ { l } ( 2 ^ { k } \cdot - j ) : \psi _ { l } \in \Psi ; 1 \leq l \leq r ; k , j , l \in Z \} .
$$

特别地，如果 $X ( \Psi )$ 同时是 $L _ { 2 } ( R )$ 的紧框架，则 $\psi _ { l } ( l = 1 , 2 , \cdots , r )$ 被称为框架, $X ( \Psi )$ 被称为紧小波框架.

在离散化情形，图像 $f$ 可等价视作 $\{ f _ { i } = \langle f , \psi ( \cdot - i ) \rangle \}$ ，其中 $\psi$ 是与小框架系统相关的可细化函娄$f$ 的 $L$ 级离散小框架分解则是在预定最粗糙 $L$ 层的系数 $\{ f = \langle f , 2 ^ { - L / 2 } \psi _ { i } ( 2 ^ { - L } \cdot - j ) \rangle \}$ ，同时框架系数为

$$
\left\{ f = \langle f , 2 ^ { - L / 2 } \psi _ { i } ( 2 ^ { - L } \cdot - j ) \rangle , 1 \leq i \leq r ^ { 2 } - 1 , 0 \leq l \leq L . \right\}
$$

上述分解可写成关于图像 $f \in \mathcal { R } ^ { m n }$ 的线性形式 $W f$ ，其中 $W \in \mathbb { R } ^ { k \times m n }$ ．由酉扩张原理(unitaryextension principle,UEP)可知, $W ^ { T } W = I$ .其中 $W ^ { T }$ 表示框架逆变换, $W$ 的行向量构成了 $\mathbb { R } ^ { m n }$ 的一个紧框架系统.文中采用文献[31-33]构造的分段线性B样条小框架.

# 2.5 临近不动点算法

记 $\Gamma _ { 0 } (  { \mathbb { R } } ^ { d } )$ 为所有下半连续凸函数 $h : \mathbb R ^ { d } \to ( - \infty , + \infty ]$ 构成的集合，其中 $d o m ( h ) : = \{ \mathbf { u } \in \mathbb { R } ^ { d } : h ( \mathbf { u } ) <$ $+ \infty \} \neq \emptyset$ .设 $f , g \in \Gamma _ { 0 } ( \mathbb { R } ^ { d } )$ ,考虑凸极小化问题:

$$
\begin{array} { r } { m i n \varphi ( \mathbf { x } ) + \psi ( \mathbf { W } \mathbf { x } ) . } \end{array}
$$

定义2.6(临近算子(proximity operator)）若 $f$ 是在 $\mathbb { R } ^ { m }$ 上的实凸函数，则函数 $f$ 在 $\mathbf { x } \in \mathbb { R } ^ { n }$ 上的临近算子定义为：

$$
p r o x _ { f } ( \mathbf { x } ) = a r g m i n \{ f ( \mathbf { u } ) + \frac { 1 } { 2 } \parallel \mathbf { u } - \mathbf { x } \parallel _ { 2 } ^ { 2 } \colon \mathbf { u } \in \mathbb { R } ^ { n } \} .
$$

记 $\mathbb { S } _ { + }$ 为所有对称正定矩阵集合．设 $\mathbf { H } \in \mathbb { S } _ { + }$ ， $\| \mathbf { x } \| _ { \mathbf { H } } : = \mathbf { x } ^ { T } \mathbf { H } \mathbf { x }$ 表示加权 $l _ { 2 }$ 范数．可以定义更一般的临近算子：

$$
p r o x _ { f , H } ( \mathbf { x } ) = a r g m i n \{ f ( \mathbf { u } ) + \frac { 1 } { 2 } \parallel \mathbf { u } - \mathbf { x } \parallel _ { H } ^ { 2 } \colon \mathbf { u } \in \mathbb { R } ^ { n } \} .
$$

定义2.7（次微分(subdifferential)）若 $f$ 是在 $\mathbb { R } ^ { m }$ 上的实凸函数，则 $f$ 在 $\mathbf { x } \in \mathbb { R } ^ { n }$ 上的次微分定义为：

$$
\partial _ { f } ( \mathbf { x } ) = \{ \mathbf { y } \in \mathbb { R } ^ { n } : f ( \mathbf { z } ) \geq f ( \mathbf { x } ) + < \mathbf { y } , \mathbf { z } - \mathbf { x } > , \mathbf { z } \in \mathbb { R } ^ { n } \} .
$$

次微分是函数在不可微情形下的扩展，若函数可微，则次微分就是函数的梯度.容易证明： $\lambda \partial f ( x ) =$ $\partial _ { \lambda f } ( x )$ ，其中 $\lambda > 0$

对任意的 $\mathbf { x } \in \mathbb { R } ^ { d }$ ： $h \in \Gamma _ { 0 } (  { \mathbb { R } } ^ { d } )$ 的共轭函数 $h ^ { * }$ 定义为 $h ^ { \ast } ( y ) : = s u p \{ \langle \mathbf { x } - \mathbf { y } \rangle - h ( \mathbf { x } ) : \mathbf { x } \in \mathbb { R } \}$ ．如下定理刻画了优化问题(9)的解.

定理2.1（[34,35]）设 $\varphi \in \Gamma _ { 0 } ( \mathbb { R } ^ { n } ) , \psi \in \Gamma _ { 0 } ( \mathbb { R } ^ { m } ) , W$ $W$ 为 $m \times n$ 矩阵．如果 $\mathbf { x } \in \mathbb { R } ^ { n }$ 是问题(9）的解,那么对于任何入, $\beta > 0$ ，都存在一个向量 $\mathbf { y } \in \mathbb { R } ^ { m }$ ，使得

$$
\begin{array} { r } { \mathbf { x } = p r o x _ { \lambda \varphi } ( \mathbf { x } - \lambda W ^ { T } \mathbf { y } ) ; } \end{array}
$$

$$
\mathbf { y } = p r o x _ { \beta \psi ^ { * } } ( \mathbf { y } + \beta W \mathbf { x } ) .
$$

反之，如果存在 $\lambda , \beta > 0$ ，则 $\mathbf { x } \in \mathbb { R } ^ { n }$ 和 $\mathbf { y } \in \mathbb { R } ^ { m }$ 满足方程(10）和(11)，则 $\mathbf { x }$ 是问题(9）的一个解.

基于定理2.1,接下来设计求解问题(9)的算法．对于 $\mathbf { z } : = ( \mathbf { x } , \mathbf { y } ) \in \mathbb { R } ^ { n } \times \mathbb { R } ^ { m }$ ，定义

$$
\Psi ( \mathbf { z } ) : = \lambda \varphi ( \mathbf { x } ) + \beta \psi ^ { * } ( \mathbf { y } )
$$

和

$$
\mathbf { E } : = \left[ \begin{array} { c c } { \mathbf { I } _ { n } } & { - \lambda W ^ { T } } \\ { \beta W } & { \mathbf { I } _ { m } } \end{array} \right] .
$$

由文献[35]知,

$$
p r o x _ { \Psi } ( \mathbf { x } ) : = ( p r o x _ { \lambda \varphi } ( \mathbf { x } ) , p r o x _ { \beta \psi ^ { * } } ( \mathbf { y } ) ) \in \mathbb { R } ^ { n } \times \mathbb { R } ^ { m } ,
$$

则方程(10）和(11）可转化为:

$$
\mathbf { z } = p r o x _ { \Psi } ( \mathbf { E } \mathbf { z } ) .
$$

注意到对任意非零矩阵 $W , { \bf E }$ 的谱范数 $\Vert \mathbf { E } \Vert _ { 2 }$ 严格大于1,简单迭代 $\mathbf { z } ^ { k + 1 } = p r o x _ { \Psi } ( \mathbf { E } \mathbf { z } ^ { k } ) .$ 对于给定初值 $ { \mathbf { z } } ^ { 0 }$ 可能不收敛．为克服矩阵E 的扩展性带来的困难，将 $E$ 分裂为两个子矩阵 $\mathbf { \nabla } \cdot \boldsymbol { M }$ 与 $E - M$ 之和.矩阵 $E$ 的分裂可能得到收敛的迭代格式，迭代格式如下：

$$
\mathbf { x } ^ { k + 1 } = p r o x _ { \Psi } ( M x ^ { k + 1 } + ( E - M ) \mathbf { x } ^ { k } ) .
$$

矩阵 $M$ 的选择方法有很多，例如若选择

$$
M = \left[ \begin{array} { c c } { { 0 } } & { { 0 } } \\ { { 2 \beta W } } & { { 0 } } \end{array} \right] ,
$$

则迭代格式(13)变成

$$
\left\{ \begin{array} { l } { \mathbf { x } ^ { k + 1 } = p r o x _ { \lambda \varphi } ( \mathbf { x } ^ { k } - \lambda W ^ { T } \mathbf { y } ^ { k } ) ; } \\ { \mathbf { y } ^ { k + 1 } = p r o x _ { \beta \psi ^ { * } } ( \mathbf { y } ^ { k } + \beta W ( 2 \mathbf { x } ^ { k + 1 } - \mathbf { x } ^ { k } ) ) . } \end{array} \right.
$$

而若选择

$$
\begin{array} { r } { M = \left[ \begin{array} { c c } { 0 } & { - 2 \lambda W ^ { T } } \\ { 0 } & { 0 } \end{array} \right] , } \end{array}
$$

则变成

$$
\left\{ \begin{array} { l } { \mathbf { y } ^ { k + 1 } = p r o x _ { \lambda \varphi } ( \mathbf { x } ^ { k } + \beta W \mathbf { y } ^ { k } ) ; } \\ { \mathbf { x } ^ { k + 1 } = p r o x _ { \beta \psi ^ { * } } ( \mathbf { x } ^ { k } - \lambda W ( 2 \mathbf { y } ^ { k + 1 } - \mathbf { y } ^ { k } ) ) . } \end{array} \right.
$$

可以证明：如果 $\begin{array} { r } { \lambda \beta < \frac { 1 } { \| W \| _ { 2 } ^ { 2 } } } \end{array}$ ，则从(14)或(15)生成的序列 $\{ \mathbf { x } ^ { ( k ) } \}$ 收敛到问题(9）的解[34,36].

# 3 模型及算法分析

# 3.1 提出的模型

本文引入软阈值框架正则化,考虑一个三元张量 $\mathcal { V } \in \mathbb { R } ^ { d _ { 1 } \times d _ { 2 } \times d _ { 3 } }$ ，建立如下的张量填充模型:

$$
\underset { \mathcal { V } , A , X } { m i n } \sum _ { n = 1 } ^ { 3 } \frac { \alpha _ { n } } { 2 } \parallel Y _ { ( n ) } - A _ { n } X _ { n } \parallel _ { F } ^ { 2 } + \lambda \parallel S _ { \gamma } ( W X _ { 3 } ^ { T } ) \parallel _ { 0 }
$$

其中 $\begin{array} { r } { \sum _ { n = 1 } ^ { 3 } \alpha _ { n } = 1 , \lambda > 0 } \end{array}$ 是正则化参数， $A : = ( A _ { 1 } , A _ { 2 } , A _ { 3 } ) , X : = ( X _ { 1 } , X _ { 2 } , X _ { 3 } )$ ， $W$ 是框架变换矩阵， $\| \cdot \| _ { 0 }$ （204号是 $l _ { 0 }$ 范数，软阈值算子 $( S _ { \gamma } ( u ) ) _ { i } : = s i g n ( u _ { i } ) m a x \{ \mid u _ { i } \mid - \gamma _ { i } , 0 \}$ ，可知目标函数(16）是非凸非光滑的．若采用 $l _ { 1 }$ 范数代替 $l _ { 0 }$ 范数，将非凸问题松弛为凸优化问题并不能得到很好的效果，因为 $\mathbf { \chi } _ { l _ { 1 } }$ 范数不能像 $\boldsymbol { l } _ { 0 }$ 范数那样能有效捕捉数据稀疏性．因此，为了尽可能的遵循 $l _ { 0 }$ 范数，本文将 $l _ { 0 }$ 范数重写为具有非线性间断权函数的加权 $l _ { 1 }$ 范数，然后使用连续权函数逼近不连续权函数.

对 $\ b { x } \in \mathbb { R }$ ，定义 $F : \mathbb { R }  \mathbb { R }$

$$
F ( x ) : = { \{ \begin{array} { l l } { { \frac { 1 } { | x | } } , } & { x \neq 0 ; } \\ { 0 , } & { { \underset { \mathrm { \tiny \ddot { \times } } } { \mathbb { E } } } { \stackrel { . } {  } } { \vec { \in } } . } \end{array}  }
$$

那么，对于 $\mathbf { u } \in \mathbb { R } ^ { d }$ ，有

$$
\| \mathbf { u } \| _ { 0 } = \sum _ { i = 0 } ^ { d } F ( u _ { i } ) \mid u _ { i } \mid ,
$$

即向量 $\mathit { \Pi } _ { \mathcal { U } }$ 的 $l _ { 0 }$ 范数可以用其第 $\mathbf { \chi } _ { i } ^ { \phantom { } }$ 分量的权重 $F ( u _ { i } )$ 表示为它的“加权” $l _ { 1 }$ 范数．由于函数 $F$ 在 $x = 0$ 时不连续，给计算带来困难，因此采用一系列正的连续偶函数 $F _ { \epsilon }$ 逼近不连续权函数 $F$ .定义

$$
F _ { \epsilon } ( x ) : = \left\{ \begin{array} { l l } { \frac { 1 } { | x | } , } & { | x | > \epsilon , } \\ { \frac { 1 } { \epsilon } , } & { 0 \leq | x | \leq \epsilon . } \end{array} \right.
$$

则 $\underset { \epsilon  0 ^ { + } } { l i m } F _ { \epsilon } ( x ) = F ( x ) , x \in \mathbb { R } \backslash \{ 0 \}$ ．此时,模型(16）可近似写成:（204号

$$
\underset { y , A , X } { m i n } \sum _ { n = 1 } ^ { 3 } \frac { \alpha _ { n } } { 2 } \parallel Y _ { ( n ) } - A _ { n } X _ { n } \parallel _ { F } ^ { 2 } + \lambda \sum _ { i = 1 } ^ { m } F _ { \epsilon } ( ( S _ { \gamma } ( W X _ { 3 } ^ { T } ) ) _ { i } ) \mid ( S _ { \gamma } ( W X _ { 3 } ^ { T } ) ) _ { i } \mid
$$

也即：

$$
\underset { y , A , X } { m i n } \sum _ { n = 1 } ^ { 3 } \frac { \alpha _ { n } } { 2 } \parallel Y _ { ( n ) } - A _ { n } X _ { n } \parallel _ { F } ^ { 2 } + \lambda \parallel \Xi S _ { \gamma } ( W X _ { 3 } ^ { T } ) \parallel _ { 1 }
$$

$$
\ d _ { 3 } . t . \ P _ { \Omega } ( \mathcal { V } ) = \mathcal { F }
$$

其中三是具有正对角元素的对角矩阵， $\Xi$ 的第 $\dot { \mathbf { \rho } } _ { i }$ 个对角线元素是 $\xi _ { i } : = F _ { \epsilon } ( ( S _ { \gamma } ( W X _ { 3 } ^ { T } ) ) ) _ { i }$ ．因此,优化问题(16）可以转化为如下问题求解:

$$
m i n ~ f ( \mathcal { V } , A , X ) = \sum _ { n = 1 } ^ { 3 } \frac { \alpha _ { n } } { 2 } \| Y _ { ( n ) } - A _ { n } X _ { n } \| _ { F } ^ { 2 } + \lambda \parallel \Xi \mathcal { S } _ { \gamma } ( W X _ { 3 } ^ { T } ) \parallel _ { 1 } + l ( \mathcal { V } ) ,
$$

其中

$$
l ( \mathcal { Y } ) : = \left\{ \begin{array} { l l } { 0 , } & { \mathcal { P } _ { \Omega } ( \mathcal { Y } ) = \mathcal { F } , } \\ { \infty , } & { \sharp \sharp \vec { \mathsf { E } } . } \end{array} \right.
$$

我们称式(17)为基于近似稀疏的低秩张量填充(Approximate Sparsity based Low-Rank Tensor Completion，简称AS-LRTC)模型.

# 3.2 求解算法

在本节中,我们将设计基于BSUM 算法框架的算法求解问题(17)．该问题显然不是关于变量 $( X , A , { \mathcal { Y } } )$ 的联合凸函数，但它对于每个变量 $X , A , \mathcal { Y }$ 都是凸函数．设 $\mathcal { Z } = ( X , A , \mathcal { Y } )$ ， $Z ^ { k } = ( X ^ { k } , A ^ { k } , \mathcal { V } ^ { k } )$ ，问题(17）可以通过如下问题求解：

$$
\mathcal { Z } ^ { k + 1 } = a r g \operatorname* { m i n } _ { \mathcal { Z } } h ( \mathcal { Z } , \mathcal { Z } ^ { k } ) = a r g \operatorname* { m i n } _ { \mathcal { Z } } f ( \mathcal { Z } ) + \frac { \rho } { 2 } \parallel \mathcal { Z } - \mathcal { Z } ^ { k } \parallel _ { F } ^ { 2 } ,
$$

其中 $\rho > 0$ 令 $\mathcal { Z } _ { 1 } ^ { k } = ( X ^ { k } , A ^ { k } , \mathcal { V } ^ { k } )$ ， $\mathcal { Z } _ { 2 } ^ { k } = ( X ^ { k + 1 } , A ^ { k } , \mathcal { V } ^ { k } )$ ， $\mathcal { Z } _ { 3 } ^ { k } = ( X ^ { k + 1 } , A ^ { k + 1 } , y ^ { k } )$ ，原问题可以通过以下迭代格式求解:

$$
\left\{ \begin{array} { l l } { { X } ^ { k + 1 } = a r g \ m i n \{ \ h _ { 1 } ( X , \mathcal { Z } _ { 1 } ^ { k } ) \} = a r g \ m i n \ \{ f ( X , A ^ { k } , \mathcal { Y } ^ { k } ) + \frac { \rho } { 2 } \ \| \ X - X ^ { k } \ \| _ { F } ^ { 2 } \} , } \\ { { A } ^ { k + 1 } = a r g \ m i n \{ \ h _ { 2 } ( A , \mathcal { Z } _ { 2 } ^ { k } ) \} = a r g \ m i n \ \{ f ( X ^ { k + 1 } , A ^ { k } , \mathcal { Y } ^ { k } ) + \frac { \rho } { 2 } \ \| \ A - A ^ { k } \ \| _ { F } ^ { 2 } \} , } \\ { { \mathcal { Y } } ^ { k + 1 } = a r g \ m i n \{ \ h _ { 3 } ( \mathcal { Y } , \mathcal { Z } _ { 3 } ^ { k } ) \} = a r g \ m i n \ \{ f ( X ^ { k + 1 } , A ^ { k + 1 } , \mathcal { Y } ^ { k } ) + \frac { \rho } { 2 } \ \| \ \mathcal { Y } - \mathcal { Y } ^ { k } \ \| _ { F } ^ { 2 } \} . } \end{array} \right.
$$

注意到 $X$ 和 $A$ 的子问题可以再分解为三个独立的子问题，而且 $y$ 有显示解．具体如下：

$X$ 子问题:

$$
X _ { n } ^ { k + 1 } = \left\{ \begin{array} { l l } { ( \alpha _ { n } ( A _ { n } ^ { k } ) ^ { T } A _ { n } ^ { k } + \rho I _ { 1 } ) ^ { \dagger } ( \alpha _ { n } ( A _ { n } ^ { k } ) ^ { T } Y _ { ( n ) } ^ { k } + \rho X _ { n } ^ { k } ) , ~ n = 1 , 2 , } \\ { a r g ~ m i n \{ \frac { \alpha _ { 3 } } { 2 } ~ \| ~ Y _ { ( 3 ) } ^ { k } - A _ { 3 } ^ { k } X _ { 3 } ~ \| _ { F } ^ { 2 } + \lambda ~ \| ~ \Xi S _ { \gamma } ( W X _ { 3 } ^ { T } ) ~ \| _ { 1 } + \frac { \rho } { 2 } ~ \| ~ X _ { 3 } - X _ { 3 } ^ { k } ~ \| _ { F } ^ { 2 } \} , ~ n = 3 . } \end{array} \right.
$$

$A$ 子问题:

$$
A _ { n } ^ { k + 1 } = ( \alpha _ { n } Y _ { ( n ) } ^ { k } ( X _ { n } ^ { k + 1 } ) ^ { T } + \rho A _ { n } ^ { k } ) ( \alpha _ { n } ( X _ { n } ^ { k } ) ^ { T } X _ { n } ^ { k } + \rho I _ { 2 } ) ^ { \dagger } , n = 1 , 2 , 3 .
$$

$y$ 子问题:

$$
\mathcal { V } ^ { k + 1 } = \mathcal { P } _ { \Omega ^ { c } } \bigl ( \sum _ { n = 1 } ^ { 3 } \alpha _ { n } f o l d _ { n } \bigl ( \frac { \alpha _ { n } A _ { n } ^ { k + 1 } X _ { n } ^ { k + 1 } + \rho Y _ { ( n ) } ^ { k } } { \alpha _ { n } + \rho } \bigr ) \bigr ) + \mathcal { F } .
$$

接下来，我们来分析求解 $X _ { 3 }$ 的细节.特别地, $X _ { 3 } ^ { k + 1 }$ 等价于求解如下问题的解:

$$
m i n \frac { \mu } { X } \parallel Y _ { ( 3 ) } ^ { k } - A _ { 3 } ^ { k } X _ { 3 } \parallel _ { F } ^ { 2 } + \parallel \Xi S _ { \gamma } ( W X _ { 3 } ^ { T } ) \parallel _ { 1 } + \frac { \rho _ { 1 } } { 2 } \parallel X _ { 3 } - X _ { 3 } ^ { k } \parallel _ { F } ^ { 2 } .
$$

显然，若 $\begin{array} { r } { f ( X _ { 3 } ) : = \frac { \mu } { 2 } \| Y _ { ( 3 ) } ^ { k } - A _ { 3 } ^ { k } X _ { 3 } \| _ { F } ^ { 2 } + \frac { \rho } { 2 } \| X _ { 3 } - X _ { 3 } ^ { k } \| _ { F } ^ { 2 } } \end{array}$ 和 $g ( W X _ { 3 } ^ { T } ) : = \| \Xi S _ { \gamma } ( W X _ { 3 } ^ { T } ) \| _ { 1 }$ ，优化问题(23）是问题(9）的一个特例．因此，可用临近不动点算法式(14)或式(15)进行求解．不失一般性,我们采用式(14)，则可得如下迭代格式：

$$
\left\{ \begin{array} { l } { { X _ { 3 } ^ { k + 1 } = p r o x _ { \lambda f } \bigl ( X _ { 3 } ^ { k } - \gamma W ^ { T } U ^ { k } \bigr ) , } } \\ { { U ^ { k + 1 } = p r o x _ { \beta g ^ { * } } \bigl ( U ^ { k } + \beta W ( 2 X _ { 3 } ^ { k + 1 } - X _ { 3 } ^ { k } ) \bigr ) . } } \end{array} \right.
$$

进一步可得,

$$
\left\{ \begin{array} { l l } { X _ { 3 } ^ { k + 1 } = \left( ( 1 + \lambda \rho _ { 1 } ) I + \lambda \mu ( A _ { 3 } ^ { k } ) ^ { T } A _ { 3 } ^ { k } \right) ^ { \dagger } \left( X _ { 3 } ^ { k } - \lambda W ^ { T } U ^ { k } - \lambda \mu ( A _ { 3 } ^ { k } ) ^ { T } Y _ { ( 3 ) } ^ { k } + \lambda \rho _ { 1 } X _ { 3 } ^ { k } \right) , } \\ { U ^ { k + 1 } = p r o x _ { \beta g ^ { * } } ( U ^ { k } + \beta W ( 2 X _ { 3 } ^ { k + 1 } - X _ { 3 } ^ { k } ) ) . } \end{array} \right.
$$

对于给定的非负数 $\xi$ 和 $\epsilon$ ，对任意 $x \in \mathbb { R }$ ，定义函数

$$
l _ { \xi , \epsilon } ( x ) : = \xi \cdot m a x \{ | \ x | - \epsilon , 0 \} .
$$

则根据函数 $g$ 的定义，对任意矩阵 $U = ( u _ { i j } )$ ，可知 $\begin{array} { r } { g ( U ) = \sum _ { i } \sum _ { j } l _ { \xi _ { i j } , \epsilon _ { i j } } ( u _ { i j } ) } \end{array}$ 是可分离的．因此,其共轭函数满足

$$
g ^ { * } ( Y ) = \sum _ { i } \sum _ { j } l _ { \xi _ { i j } , \epsilon _ { i j } } ^ { * } ( y _ { i j } ) ,
$$

且由临近算子性质(式(12)),有

$$
p r o x _ { \beta g ^ { * } } ( Y ) = \left( p r o x _ { \beta l _ { \xi _ { i j } , \gamma _ { i j } } ^ { * } } ( y _ { i j } ) \right) .
$$

最后， $\beta g ^ { * }$ 的函数表达式与邻近算子可由如下引理求得：

引理3.1对于两个非负数 $\xi$ 和∈，在 $x \in \mathbb { R }$ ，有

$$
l _ { \xi , \epsilon } ^ { * } ( x ) : = \left\{ \begin{array} { l l } { \epsilon \mid x \mid , } & { | x | \leq \xi ; } \\ { + \infty , } & { \frac { \sharp } { \wedge } \ddot { \gtrsim } . } \end{array} \right.
$$

此外，对 $\beta > 0$ ，都有

$$
p r o x _ { \beta l _ { \xi , \epsilon } ^ { * } } : = \left\{ \begin{array} { l l } { s i g n ( x ) \xi , } & { | x | > \beta \epsilon + \xi ; } \\ { x - s i g n ( x ) \beta \epsilon , } & { \beta \epsilon \leq \beta \epsilon + \xi ; } \\ { 0 , } & { \sharp \sharp \vec { \Sigma } . } \end{array} \right.
$$

引理3.1的详细证明见文献[28].

综合上述分析，则得到了本文提出的求解模型(17)的算法:

算法1基于BSUM算法的AS-LRTC模型求解  
输入：观测张量： $\mathcal { F }$ ；观测元素已知位置的集合 $: \Omega$ ；给定的Tucker 秩 ${ \bf \chi } : r = ( r _ { 1 } , r _ { 2 } , r _ { 3 } )$   
输出：重构张量： $y$   
1: function AS-LRTC  
2: 初始化： $\begin{array} { r } { A _ { n } ^ { 0 } = r a n d ( I _ { n } \times r _ { n } ) , X _ { n } ^ { 0 } = r a n d ( r _ { n } \times \prod _ { m = 1 , m \neq n } ^ { k - 1 } I _ { m } ) , n = ( 1 , 2 , 3 ) ; \mathcal { V } = \mathcal { P } _ { \Omega } ( \mathcal { F } ) ; } \end{array}$ （3: while not converged do  
4: 通过式(20)更新 $X _ { 1 } , X _ { 2 }$   
5: 通过求解(23)更新 $X _ { 3 }$   
6: 通过式(21)更新 $A _ { n } ( n = 1 , 2 , 3 )$   
7: 通过式(22)更新y;  
8: end While  
9:return $y$ （204号

# 3.3 收敛性分析

接下来，说明本文基于BSUM提出的算法满足引理2.1的条件，从而必是收敛的，

定理3.1由(18)生成的迭代格式收敛到坐标极小点：

证明：首先， $h ( \mathcal { Z } , \mathcal { Z } ^ { k } )$ 是函数 $f ( { \mathcal { Z } } )$ 的近似，是其在第 $k$ 次迭代的全局上界，并满足下列条件：

$$
\begin{array} { r l } & { h _ { i } ( \mathcal { Z } _ { i } , \mathcal { Z } ) = f ( \mathcal { Z } ) , \forall \mathcal { Z } , i = 1 , 2 , 3 ; } \\ & { h _ { i } ( \bar { \mathcal { Z } } _ { i } , \mathcal { Z } ) \geq f ( \mathcal { Z } _ { 1 } , \cdots , \bar { \mathcal { Z } } _ { i } , \cdots , \mathcal { Z } _ { 3 } ) , \forall \bar { \mathcal { Z } } _ { i } , \forall \mathcal { Z } , i = 1 , 2 } \\ & { h _ { 1 } ^ { ' } ( \bar { \mathcal { Z } } _ { 1 } , \mathcal { Z } ; \mathcal { D } _ { 1 } ) | _ { \bar { \mathcal { Z } } _ { 1 } = \mathcal { Z } _ { 1 } } = f ^ { ' } ( \mathcal { Z } ; \mathcal { D } ^ { 1 } ) , \forall \mathcal { D } ^ { 1 } = ( \mathcal { D } _ { 1 } , 0 , 0 ) ; } \\ & { h _ { 2 } ^ { ' } ( \bar { \mathcal { Z } } _ { 2 } , \mathcal { Z } ; \mathcal { D } _ { 2 } ) | _ { \bar { \mathcal { Z } } _ { 2 } = \mathcal { Z } _ { 2 } } = f ^ { ' } ( \mathcal { Z } ; \mathcal { D } ^ { 2 } ) , \forall \mathcal { D } ^ { 2 } = ( 0 , \mathcal { D } _ { 2 } , 0 ) ; } \\ & { h _ { 3 } ^ { ' } ( \bar { \mathcal { Z } } _ { 3 } , \mathcal { Z } ; \mathcal { D } _ { 3 } ) | _ { \bar { \mathcal { Z } } _ { 3 } = \mathcal { Z } _ { 3 } } = f ^ { ' } ( \mathcal { Z } ; \mathcal { D } ^ { 3 } ) , \forall \mathcal { D } ^ { 3 } = ( 0 , 0 , \mathcal { D } _ { 3 } ) ; } \end{array}
$$

其中， $\mathcal { Z } = ( X , A , \mathcal { Y } )$ ，当 $i = { 1 , 2 , 3 }$ 时 $\mathcal { Z } _ { i }$ 分别等于 $X , A , \mathcal { Y }$

另外，子问题 $h _ { i } ( i = 1 , 2 , 3 )$ 分别关于 $X , A , \mathcal { V }$ 强凸，因此每个子问题均有唯一解.故按坐标收敛到问题的极小值点. □

# 4数值实验

在本节中，我们将在3阶张量数据上测试AS-LRTC方法的性能，数据类型包括：视频数据、高光谱图像、核磁共振图像以及彩色图像.进行对比的方法为Ji等人[26]提出的MF-TV和Jiang等人[27]提出的MF-Framelet 的张量填充方法．为了定量评价各方法恢复的图像质量，我们采用峰值信噪比(PeakSignal-to-Noise Ratio,PSNR)和结构相似性指数(Structural Similarity,SSIM)作为数值指标.假设真实张量是 $\bar { \mathcal { D } }$ 。则恢复出的张量 $y$ 的PSNR的定义如下：

$$
\mathrm { P S N R } ( \mathcal { V } , \bar { \mathcal { V } } ) = 1 0 l o g _ { 1 0 } \frac { n \bar { \mathcal { V } } _ { m a x } ^ { 2 } } { \Vert \bar { \mathcal { V } } - \mathcal { V } \Vert _ { F } ^ { 2 } }
$$

其中 $n$ 表示张量中的元素个数， $\bar { \mathcal { D } } _ { m a x }$ 表示真实张量中的像素最大值.假设真实二维图像是 $\bar { Y }$ ，则恢复出的图像 $Y$ 的SSIM定义如下：

$$
\mathrm { S S I M } ( Y , \bar { Y } ) = \frac { ( 2 m e a n ( Y ) m e a n ( \bar { Y } ) + c _ { 1 } ) ( 2 c o v ( Y , \bar { Y } ) + c _ { 2 } ) } { ( m e a n ( Y ) ^ { 2 } + m e a n ( \bar { Y } ) ^ { 2 } + c _ { 1 } ) ( s t d ( Y ) ^ { 2 } + s t d ( \bar { Y } ) ^ { 2 } + c _ { 2 } ) }
$$

其中 $m e a n ( Y , \bar { Y } ) , s t d ( Y )$ 和 $c o v ( Y , \bar { Y } )$ 分别表示 $Y$ 的像素平均值, $Y$ 的标准差, $Y$ 和 $\bar { Y }$ 的协方差, $c _ { 1 }$ 和 $c _ { 2 }$ 为两个常数．对于真实张量数据，我们计算其按各维度展开矩阵的SSIM值的平均值，以此代替张量的SSIM值.停止准则是两个连续重构张量的相对变化(RelCha)，定义如下：

$$
R e l C h a = \frac { \parallel Y ^ { k + 1 } - Y ^ { k } \parallel _ { F } } { \parallel Y ^ { k } \parallel _ { F } } < \varepsilon
$$

其中 $\varepsilon > 0$ 是给定容许误差

在所有实验过程中，对于MF-TV,MF-Framelet方法，其参数设置采用文献给出的参数．本文提出的AS-LRTC模型参数设置如下： $\alpha _ { i } = 1 / 3 ( i = 1 , 2 , 3 )$ ， $\rho = 0 . 1$ ， $\mu = 1 / 3 , \lambda = 1 0 , \beta = 0 . 9 / \lambda , \rho _ { 1 } = 0 . 0 1$ 所有实验均在Windows 10和MATLAB(R2016b）平台上实现，平台配置为2.70GHz的 $\mathrm { I n t e l ( R ) X e o n ( R ) }$ CPU和32G的内存.

# 4.1 视频图像修复

在本节中,我们测试了7个是视频:salesman,coastguard, news,suzie,hall,carphone,foreman．所有视频均为YUV格式．在实验中，首先将视频的Y通道转化为150帧的灰度视频，然后进行测试.所有测试视频的尺寸均为 $1 4 4 \times 1 7 6 \times 1 5 0$ 。采样率SR分别设置为 $5 \%$ 5 $1 0 \%$ ， $2 0 \%$ ， $3 0 \%$ 和 $4 0 \%$

表1总结了通过三种低秩张量填充方法针对不同的SR重建的所有测试视频的PSNR和SSIM.结果表明，该方法在PSNR和SSIM值方面始终优于比较方法，特别是在采样率 $S R$ 低于 $2 0 \%$ 时．图4显示了在 $S R = 1 0 \%$ 的情况下，通过三种低秩张量填充方法重建的所有视频的其中一帧．我们观察到所提出的AS-LRTC方法所重建视频的视觉效果优于其他方法．具体而言，所提出的AS-LRTC方法能够更好地填充缺失数据，同时更多地保留视频的基本结构和有效信息，而MF-TV和MF-Framelet 获得的结果仍然具有大量缺失数据．图5中可以看出AS-LRTC方法恢复的视频的像素值能更好的接近原素值，图6表明AS-LRTC方法恢复的每一帧图像的效果优于其它两种方法，

表1:MF-TV,MF-Framelet和本文提出的AS-LRTC方法的数值对比结果(PSNR,SSIM)  

<html><body><table><tr><td rowspan="2">video</td><td>SR</td><td colspan="2">5%</td><td colspan="2">10%</td><td colspan="2">20%</td><td colspan="2">30%</td><td colspan="2">40%</td></tr><tr><td>method</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td></tr><tr><td rowspan="3">salesman</td><td>MF-TV</td><td>9.849</td><td>0.0634</td><td>13.882</td><td>0.2779</td><td>24.095</td><td>0.7981</td><td>32.108</td><td>0.9290</td><td>35.286</td><td>0.9640</td></tr><tr><td>MF-Framelet</td><td>11.053</td><td>0.1652</td><td>14.634</td><td>0.4381</td><td>25.643</td><td>0.8334</td><td>32.623</td><td>0.9388</td><td>35.543</td><td>0.9669</td></tr><tr><td>AS-LRTC</td><td>18.2773</td><td>0.5465</td><td>27.592</td><td>0.8676</td><td>31.741</td><td>0.9298</td><td>34.202</td><td>0.9563</td><td>35.957</td><td>0.9701</td></tr><tr><td rowspan="3">coastguard</td><td>MF-TV</td><td>7.532</td><td>0.0369</td><td>8.607</td><td>0.0615</td><td>11.463</td><td>0.1290</td><td>17.603</td><td>0.3529</td><td>26.503</td><td>0.7671</td></tr><tr><td>MF-Framelet</td><td>8.945</td><td>0.0654</td><td>10.685</td><td>0.1154</td><td>14.589</td><td>0.2006</td><td>21.346</td><td>0.5072</td><td>28.180</td><td>0.8198</td></tr><tr><td>AS-LRTC</td><td>18.638</td><td>0.3150</td><td>19.405</td><td>0.4001</td><td>20.249</td><td>0.4922</td><td>23.727</td><td>0.7137</td><td>24.676</td><td>0.7703</td></tr><tr><td rowspan="3">news</td><td>MF-TV</td><td>10.604</td><td>0.1179</td><td>12.638</td><td>0.2187</td><td>19.153</td><td>0.5277</td><td>30.356</td><td>0.8380</td><td>34.845</td><td>0.9302</td></tr><tr><td>MF-Framelet</td><td>12.591</td><td>0.2575</td><td>15.062</td><td>0.3748</td><td>22.280</td><td>0.6472</td><td>32.730</td><td>0.904</td><td>35.820</td><td>0.9508</td></tr><tr><td>AS-LRTC</td><td>21.943</td><td>0.7306</td><td>26.155</td><td>0.8489</td><td>30.615</td><td>0.8986</td><td>33.921</td><td>0.9399</td><td>36.470</td><td>0.9626</td></tr><tr><td rowspan="3">suzie</td><td>MF-TV</td><td>13.559</td><td>0.0915</td><td>22.126</td><td>0.6018</td><td>31.830</td><td>0.8713</td><td>34.808</td><td>0.9247</td><td>36.484</td><td>0.9481</td></tr><tr><td>MF-Framelet</td><td>15.486</td><td>0.2014</td><td>24.040</td><td>0.6729</td><td>32.328</td><td>0.8810</td><td>35.009</td><td>0.9281</td><td>36.591</td><td>0.9489</td></tr><tr><td>AS-LRTC</td><td>20.503</td><td>0.5378</td><td>29.051</td><td>0.8042</td><td>33.178</td><td>0.8993</td><td>35.192</td><td>0.9315</td><td>36.606</td><td>0.9498</td></tr><tr><td rowspan="3">hall</td><td>MF-TV</td><td>13.414</td><td>0.4184</td><td>24.779</td><td>0.8265</td><td>33.170</td><td>0.9412</td><td>35.025</td><td>0.9600</td><td>36.274</td><td>0.9690</td></tr><tr><td>MF-Framelet</td><td>13.015</td><td>0.4671</td><td>24.118</td><td>0.8325</td><td>33.307</td><td>0.9450</td><td>35.186</td><td>0.9619</td><td>36.423</td><td>0.9713</td></tr><tr><td>AS-LRTC</td><td>26.655</td><td>0.8475</td><td>30.514</td><td>0.9110</td><td>33.654</td><td>0.9469</td><td>35.173</td><td>0.9608</td><td>36.348</td><td>0.9695</td></tr><tr><td rowspan="3">carphone</td><td>MF-TV</td><td>10.058</td><td>0.1137</td><td>14.743</td><td>0.4782</td><td>30.762</td><td>0.8748</td><td>34.470</td><td>0.9390</td><td>36.208</td><td>0.9601</td></tr><tr><td>MF-Framelet</td><td>10.640</td><td>0.2151</td><td>14.849</td><td>0.5344</td><td>31.651</td><td>0.8886</td><td>34.719</td><td>0.9447</td><td>36.363</td><td>0.9632</td></tr><tr><td>AS-LRTC</td><td>19.924</td><td>0.4798</td><td>29.611</td><td>0.8463</td><td>33.203</td><td>0.9235</td><td>35.073</td><td>0.9494</td><td>36.445</td><td>0.9636</td></tr><tr><td rowspan="3">foreman</td><td>MF-TV</td><td>7.056</td><td>0.0253</td><td>13.749</td><td>0.2617</td><td>29.726</td><td>0.8471</td><td>32.780</td><td>0.9149</td><td>34.451</td><td>0.9421</td></tr><tr><td>MF-Framelet</td><td>7.252</td><td>0.0277</td><td>13.505</td><td>0.3017</td><td>30.179</td><td>0.8561</td><td>32.891</td><td>0.9183</td><td>34.539</td><td>0.9441</td></tr><tr><td>AS-LRTC</td><td>15.503</td><td>0.1431</td><td>26.131</td><td>0.6978</td><td>31.126</td><td>0.8835</td><td>33.083</td><td>0.9231</td><td>34.583</td><td>0.9446</td></tr></table></body></html>

![](images/5d973914648e6fd0e3fbc055954b02e03ccccf29c49bb7ea872a3af1f9c4c035.jpg)  
图4：不同方法对视频图像其中一帧的恢复结果(采样率为 $1 0 \%$ ).第一列：真实数据；第二列：观测数据；第三列：MF-TV恢复结果;第四列:MF-Framelet恢复结果;第五列：AS-LRTC 恢复结果

![](images/c20f091ead8fdcc161ec606f9dcd42707eaaec73334bee493c77bdae8a1adc48.jpg)  
图5：对视频news和hall利用三种LRTC方法进行重建得到其中一个模-3纤维对应的像素值

![](images/51a2072a624bf108ef50a78858c05241eccd2a927b7ffc3fd32ea51885207ba8.jpg)  
图6：对视频news和hall利用三种LRTC方法进行重建得到各帧的PSNR值

# 4.2 高光谱图像修复

在本节中，我们测试的高光谱图像的大小为 $3 5 0 \times 3 5 0 \times 1 8 8$ ．SR设置为 $1 0 \%$ ．图7显示了通过提出的方法和三种比较方法重建的测试高光谱图像的波段．可以看出，与MF-TV和MF-framelet相比，所提出的AS-LRTC方法能够很好的重构高光谱图像.

![](images/9b0fc2b25940b42faec7a61f906d49a24e3b9b360d2922586e9b932378ee38d0.jpg)  
图7：不同方法对高光谱视频图像第56波段和第155波段的恢复结果(采样率为 $1 0 \%$ ).第一列：真实数据;第二列：观测数据；第三列:MF-TV恢复结果；第四列：MF-Framelet恢复结果；第五列：AS-LRTC恢复结果

# 4.3 核磁共振图像修复

该测试使用尺寸为 $1 8 1 \times 2 1 7 \times 1 8 1$ 的MRI数据作为测试数据.SR设置为 $10 \%$ ．由于可以将所有方向的切片视为图像，因此在图8中,我们显示了从三个不同方向分别观察到的三个重建MRI数据的代表性切片．在不同方向的重构上，我们看到，本文所提出的AS-LRTC方法重构的MRI的视觉质量均优于其他的比较方法.

![](images/aa124292533979ce364e6e88e9432ca18fce582f04328679ed18685104fd7384.jpg)  
图8：不同方法对视频图像其中一帧的恢复结果(采样率为 $1 0 \%$ ).第一列：真实数据；第二列：观测数据；第三列：MF-TV恢复结果;第四列:MF-Framelet恢复结果;第五列：AS-LRTC 恢复结果

# 4.4 彩色图像修复

本节我们用 $2 5 6 \times 2 5 6 \times 3$ 大小的彩色图片来测试我们的方法的有效性和优点，根据彩色图片在空间域的分段光滑性,我们将模型适当的改为(25)，从模型看，求解算法与前文相似.

$$
\underset { \mathcal { V } , A , X } { m i n } \sum _ { n = 1 } ^ { 3 } \frac { \alpha _ { n } } { 2 } \parallel Y _ { ( n ) } - A _ { n } X _ { n } \parallel _ { F } ^ { 2 } + \lambda \parallel \Xi S _ { \gamma } ( W X _ { 2 } ^ { T } ) \parallel _ { 1 }
$$

从表2中可以看出，我们的方法恢复出的彩色图片的PSNR 值和SSIM值比MF-TV 和MF-Framelet 方法高，尤其是当采样率为 $1 0 \%$ 和 $2 0 \%$ 时，我们的方法的效果更明显．从图9中可以更直观的看出我们的方法恢复出的图像效果明显好于其它两种方法，从背景的色彩上看，我们的方法更接近原图像.

表 2:MF-TV,MF-Framelet和本文提出的AS-LRTC方法的数值对比结果(PSNR,SSIM)  

<html><body><table><tr><td rowspan="2">name</td><td>SR</td><td colspan="2">10%</td><td colspan="2">20%</td><td colspan="2">30%</td><td colspan="2">40%</td><td colspan="2">50%</td></tr><tr><td>method</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td></tr><tr><td rowspan="3">airplane</td><td>MF-TV</td><td>8.213</td><td>0.0390</td><td>15.110</td><td>0.1467</td><td>22.541</td><td>0.5633</td><td>27.702</td><td>0.7839</td><td>30.930</td><td>0.5407</td></tr><tr><td>MF-Framelet</td><td>8.950</td><td>0.0441</td><td>15.725</td><td>0.1769</td><td>23.375</td><td>0.5966</td><td>28.082</td><td>0.7991</td><td>31.408</td><td>0.8831</td></tr><tr><td>AS-LRTC</td><td>18.038</td><td>0.4094</td><td>23.254</td><td>0.6018</td><td>26.707</td><td>0.7627</td><td>29.546</td><td>0.8528</td><td>31.760</td><td>0.8949</td></tr><tr><td rowspan="3">facade</td><td>MF-TV</td><td>12.805</td><td>0.1776</td><td>20.365</td><td>0.5481</td><td>27.361</td><td>0.8407</td><td>31.072</td><td>0.9215</td><td>33.661</td><td>0.9541</td></tr><tr><td>MF-Framelet</td><td>15.563</td><td>0.3127</td><td>22.459</td><td>0.6487</td><td>28.337</td><td>0.8685</td><td>31.619</td><td>0.9297</td><td>33.942</td><td>0.9573</td></tr><tr><td>AS-LRTC</td><td>19.195</td><td>0.4951</td><td>27.809</td><td>0.8561</td><td>30.558</td><td>0.9155</td><td>32.763</td><td>0.9462</td><td>34.411</td><td>0.9618</td></tr><tr><td rowspan="3">house</td><td>MF-TV</td><td>10.375</td><td>0.0573</td><td>17.407</td><td>0.2468</td><td>25.2175</td><td>0.6329</td><td>30.249</td><td>0.8041</td><td>33.298</td><td>0.8806</td></tr><tr><td>MF-Framelet</td><td>11.573</td><td>0.0750</td><td>19.095</td><td>0.3064</td><td>26.432</td><td>0.6704</td><td>30.672</td><td>0.8171</td><td>33.348</td><td>0.8844</td></tr><tr><td>AS-LRTC</td><td>19.904</td><td>0.4356</td><td>25.559</td><td>0.6493</td><td>29.210</td><td>0.7880</td><td>32.132</td><td>0.8649</td><td>34.092</td><td>0.9044</td></tr><tr><td rowspan="3">lena</td><td>MF-TV</td><td>10.960</td><td>0.0779</td><td>14.664</td><td>0.1565</td><td>19.848</td><td>0.3452</td><td>25.607</td><td>0.6444</td><td>30.413</td><td>0.8356</td></tr><tr><td>MF-Framelet</td><td>12.685</td><td>0.1122</td><td>16.367</td><td>0.1898</td><td>21.142</td><td>0.3999</td><td>26.396</td><td>0.6773</td><td>30.540</td><td>0.8406</td></tr><tr><td>AS-LRTC</td><td>16.426</td><td>0.3044</td><td>17.494</td><td>0.3648</td><td>26.189</td><td>0.7090</td><td>29.285</td><td>0.8281</td><td>31.940</td><td>0.8932</td></tr><tr><td rowspan="3">peppers</td><td>MF-TV</td><td>10.771</td><td>0.0759</td><td>14.071</td><td>0.1553</td><td>17.675</td><td>0.2843</td><td>23.326</td><td>0.5633</td><td>28.557</td><td>0.7822</td></tr><tr><td>MF-Framelet</td><td>12.172</td><td>0.1441</td><td>15.986</td><td>0.2101</td><td>18.907</td><td>0.3338</td><td>24.295</td><td>0.6049</td><td>29.202</td><td>0.7984</td></tr><tr><td>AS-LRTC</td><td>14.482</td><td>0.2270</td><td>17.235</td><td>0.3662</td><td>24.819</td><td>0.6606</td><td>28.021</td><td>0.7914</td><td>30.720</td><td>0.8668</td></tr><tr><td rowspan="3">sailboat</td><td>MF-TV</td><td>9.306</td><td>0.0962</td><td>12.681</td><td>0.1894</td><td>15.839</td><td>0.2961</td><td>19.606</td><td>0.4563</td><td>24.886</td><td>0.6740</td></tr><tr><td>MF-Framelet</td><td>11.237</td><td>0.1438</td><td>15.414</td><td>0.2566</td><td>18.132</td><td>0.3652</td><td>21.448</td><td>0.5235</td><td>25.736</td><td>0.7055</td></tr><tr><td>AS-LRTC</td><td>15.279</td><td>0.2791</td><td>16.304</td><td>0.3527</td><td>23.3674</td><td>0.6454</td><td>25.814</td><td>0.7533</td><td>28.415</td><td>0.8395</td></tr></table></body></html>

![](images/74ea0990ef1617358d725db1401ee20fcae448c179e6d0256a1533161c32793f.jpg)  
图9：不同方法对彩色图像的恢复结果(采样率为 $4 0 \%$ )．第一列：真实数据；第二列：观测数据；第三列：MF-TV恢复结果;第四列:MF-Framelet 恢复结果;第五列:AS-LRTC恢复结果

# 5结论

本文结合近似稀疏和低秩矩阵分解提出了一个近似稀疏的张量填充模型，利用问题的结构设计了有效的AS-LRTC算法．一定条件下证明了算法的收敛性，大量数值结果表明该方法在恢复视觉效果和增强

分段平滑度方面均取得了很好的效果，

# 参考文献

[1] Yokota T,Lee N, Cichocki A. Robust multilinear tensor rank estimation using higher order singular value decomposition and information criteria. IEEE Transactions on Signal Processing, 2016, 65(5): 1196-1206   
[2] Mei J J, Dong Y, Huang T Z, et al. Cauchy noise removal by nonconvex ADMM with convergence guarantees. Journal of Scientific Computing, 2018,74(2): 743-766   
[3] Sobral A, Zahzah E. Matrix and tensor completion algorithms for background model initialization: A comparative evaluation. Pattern Recognition Letters, 2017, 96: 22-33   
[4] Varghees V N, Manikandan M S, Gini R. Adaptive MRI image denoising using total-variation and local noise estimation//IEEE-International Conference On Advances In Engineering, Science And Management (ICAESM-2012). IEEE,2012: 506-511   
[5] Zhao X L, Wang F, Huang T Z, et al. Debluring and sparse unmixing for hyperspectral images. IEEE Transactions on Geoscience and Remote Sensing, 2013, 51(7): 4045-4058   
[6] Chen Y, Huang T Z, Zhao X L, et al. Hyperspectral image restoration using framelet-regularized low-rank nonnegative matrix factorization. Applied Mathematical Modeling, 2018,63: 128-147   
[7] Zhang H, Patel V M. Convolutional sparse and low-rank coding-based rain streak removal//2017 IEEE Winter Conference on Applications of Computer Vision (WACV). IEEE, 2017: 1259-1267   
[8] Jiang T X, Huang T Z, Zhao X L, et al. Fastderain: A novel video rain streak removal method using directional gradient priors. IEEE Transactions on Image Processng, 2018, 28(4): 2089-2102   
[9] Sidiropoulos N D,De Lathauwer L,Fu X, et al. Tensor decomposition for signal processing and machine learning. IEEE Transactions on Signal Processing, 2017, 65(13): 3551-3582   
10] Liu J, Musialski P, Wonka P,et al. Tensor completion for estimating missng values in visual data. IEEE transactions on pattern analysis and machine intelligence, 2012,35(1): 208-220   
11] Tan H, Cheng B,Wang W,et al. Tensor completion via a multi-linear low-n-rank factorization model. Neurocomputing, 2014,133:161-169   
12] Filipovic M, Jukic A.Tucker factorization with missing data with application to low-nrank tensor completion.Multidim. Syst. Sign.P,2013   
13] Hillr C J,Lim L H. Most tensor problems are NP-hard. Journal of the ACM (JACM), 2013, 60(6): 1-39   
14] Gandy S, Recht B, Yamada I. Tensor completion and low-n-rank tensor recovery via convex optimization. Inverse Problems, 2011, 27(2): 025010 [15]Romera-Paredes B,Pontil M. A new convex relaxation for tensor completion//Advances in Neural Information Processing Systems. 2013: 2967-2975 [16] Li YF,Shang K, Huang Z H.Low Tucker rank tensor recovery via ADMM based on exact and inexact iteratively reweighted algorithms.Journal of Computational and Applied Mathematics, 2018, 331:   
64-81 [17] Ji T Y, Huang T Z, Zhao X L,et al. A non-convex tensor rank approximation for tensor completion. Applied Mathematical Modelling, 2017, 48: 410-422 [18]Mu C, Huang B,Wright J, et al. Square deal: Lower bounds and improved relaxations for tensor recovery//International conference on machine learning. 2014: 73-81 [19]Nie J. Nearly Low Rank Tensors and Their Approximations. arXiv preprint arXiv:1412.7270, 2014 [20] Bai M, Zhang X, Ni G, et al. An adaptive correction approach for tensor completion. SIAM Journal on Imaging Sciences, 2016, 9(3): 1298-1323 [21] Xu Y,Hao R,Yin W,et al.Paralel matrix factorization for low-rank tensor completion. Inverse Problems & Imaging, 2015, 9 (2) : 601-624. [22] Wen Z, Yin W, Zhang Y. Solving a low-rank factorization model for matrix completion by a nonlinear successive over-relaxation algorithm. Mathematical Programming Computation, 2012, 4(4): 333-361 [23] Zhao X L, Wang W, Zeng T Y, et al. Total variation structured total least squares method for image restoration. SIAM Journal on Scientific Computing, 2013, 35(6): B1304-B1320 [24] Chan T F, Vese L A. Active contours without edges. IEEE Transactions on image processing, 2001,   
10(2): 266-277 [25] Chan S H, Khoshabeh R, Gibson K B, et al. An augmented Lagrangian method for total variation video restoration. IEEE Transactions on Image Processing, 2011, 20(11): 3097-3111 [26] Ji T Y,Huang T Z, Zhao X L,et al. Tensor completion using total variation and low-rank matrix factorization. Information Sciences, 2016, 326: 243-257 [27] Jiang T X, Huang T Z, Zhao X L, et al. Matrix factorization for low-rank tensor completion using framelet prior. Information Sciences, 2018,436: 403-417 [28] Shen L, Xu Y, Zhang N. An approximate sparsity model for inpainting. Applied and Computational Harmonic Analysis, 2014, 37(1): 171-184 [29]Kolda T G, Bader B W. Tensor decompositions and applications. SIAM review, 2009, 51(3): 455-500 [30]Razaviyayn M, Hong M, Luo Z Q. A unified convergence analysis of block successive minimization methods for nonsmooth optimization. SIAM Journal on Optimization, 2013, 23(2): 1126-1153 [31]Ron A,Shen Z. Affne systems inL2 (Rd): the analysis of the analysis operator. Journal of Functional Analysis, 1997, 148(2): 408-447   
[32] Cai JF, Chan R H, Shen Z.A framelet-based image inpainting algorithm. Applied and Computational Harmonic Analysis,2008,24(2):131-149   
[33] Chai A, Shen Z. Deconvolution: A wavelet frame approach. Numerische Mathematik, 2007,106(4): 529-587   
[34] Li Q,Miccheli C A, Shen L,et al.A proximity algorithm accelerated by Gauss- Seidel iterations for L1/TV denoising models.Inverse Problems,2012,28(9): 095003   
[35] Li Q,Shen L,Xu Y,et al. Multi-step fixed-point proximity algorithms for solving a class of optimization problems arising from image processing. Advances in Computational Mathematics, 2015, 41(2): 387-422   
[36] Zhang X,Burger M, Osher S.A unifed primal-dual algorithm framework based on Bregman iteration. Journal of Scientific Computing, 2011, 46(1): 20-46