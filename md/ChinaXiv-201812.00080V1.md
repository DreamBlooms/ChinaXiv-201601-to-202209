# 基于改进块稀疏贝叶斯学习算法的波达方向估计

王书豪，阮怀林

(国防科技大学 电子对抗学院，合肥 230037)

摘要：针对传统的基于稀疏表示的DOA估计算法单纯利用信号的空域稀疏性，导致在低信噪比时稀疏性能变差，影响信号稀疏重构效果的问题。使用分块稀疏理论对信号进行稀疏分解。随着目标增多及作战任务改变，DOA估计往往呈现目标群测向的特点，为了能够更好地利用信号的结构特征和统计特征，提出了基于空时联合的块稀疏 DOA估计算法，使用块稀疏理论挖掘信号的内部结构，充分利用了信号的块内稀疏性和块间相关性，提高稀疏重构性能，进而对 DOA估计效果有很大的提升。仿真实验表明，相比于经典的DOA方法，本方法有着更好的估计效果。

关键词：空时联合；块稀疏；稀疏贝叶斯学习；DOA估计 中图分类号：TN911.23 doi: 10.19734/j.issn.1001-3695.2018.08.0553

DOA estimation based on improved block sparse Bayesian learning algorithm

Wang Shuhao, Ruan Huailin (SchoolofElectronicCountermeasures,National UniversityofDefenseTechnology University,Hefei23037,China)

Abstract: The traditional DOA estimation algorithm basedon sparse representation only uses sparse signal in spatial domain,which leads to poor sparse performance atlow SNR and affcts the effctof sparse signal reconstruction.This paper used block sparse theory to decompose the signal sparsely.With the increase of target and the change of combat mission,DOA estimationoften presents the characteristicsof target group direction finding.Inorder to make beter use of the structural and statistical characteristics of signals,this paper proposed a block sparse DOA estimation algorithmbased on space-time combination (STC-BSBL).This method improves the performance of sparse reconstruction,and thus greatly improves the DOA estimation efect.Simulation results show that the proposed method has beter estimation performance compared with the traditional DOA method.

Key words: spatial-temporal combined; block sparse; sparse Bayesian learning; DOA estimation

目前，基于稀疏表示的雷达信号波达方向(direction ofarrival,DOA)估计估计算法广受关注，李子高等人[I利用目前广泛应用的信号稀疏表示，使用凸优化类的正交匹配跟踪(orthogonal matchingpursuit,OMP)算法实现信号的DOA估计，但这种方法只考虑了信号整体的稀疏性，往往会造成低信噪比条件下难以精确重构信号的问题。实际上，除了一般稀疏性，块稀疏结构在DOA估计中广泛存在，如今的测向问题，空域中感兴趣的目标信号往往以集群的形式出现，群目标数量众多，群内分布密集，呈现分块稀疏性。文献[2]提出块稀疏分解的信号重构方法，利用信号块的结构特性提高重构性能。张智林等人[3将这一理论进一步发展，提出了块稀疏贝叶斯学习算法(block sparse Bayesian learning，BSBL)，创新性地利用了信号的分块稀疏性和块间相关性实现了精确的稀疏信号重构。

本文以BSBL为基础，将其拓展到多测量矢量(MMV)模型DOA估计的应用中去，在考虑信号分块稀疏性和信号相关性的基础上，兼顾多观测矢量间的时域相关信息，以窄带信号为例，提出使用空时联合块稀疏贝叶斯学习(space-timecombinationBSBL,STC-BSBL)方法对其进行DOA估计。

# 1 阵列结构及数据模型

# 1.1MMV模型

考虑 $L$ 个远场窄带信号入射到由M个阵元组成的均匀线

阵上，一元线阵沿轴线均匀放置，每个阵元间距相同，均为d，阵列接收模型如图1所示。

![](images/a32ce05d536840d92a9f7d6d78b1cb71cf87e96654272ed88ccbb3bcd09ee126.jpg)  
图1阵列结构示意图Fig.1Array structure

假设信号的中心频率为 $f$ ，带宽为B，波长为 $\lambda$ ，阵元间距取为 $d = \%$ ，入射角度为 $\boldsymbol { \theta } = \{ \boldsymbol { \theta } _ { 1 } , \boldsymbol { \theta } _ { 2 } \cdots \boldsymbol { \theta } _ { L } \}$ ，则t时刻第 $\mathrm { ~ m ~ }$ 个阵元的接收数据表示为

$$
y _ { m } \left( t \right) = \sum _ { i = 1 } ^ { L } x _ { i } ( t - \tau _ { m , i } ) + n _ { m } ( t )
$$

$$
\ d _ { m } = 1 , 2 , \ d . . . . M
$$

其中： $\tau _ { m , i } = \frac { 1 } { c } ( m - 1 ) d \sin ( \theta _ { i } ) , m = 1 , 2 , . . . . M , i = 1 , \cdots , L$ 。

如果考虑整个天线阵列中 $M$ 个阵元接收到的信号，将接

收数据用矩阵的形式表示为

$$
{ \left[ \begin{array} { l } { y _ { 1 } ( t ) } \\ { y _ { 2 } ( t ) } \\ { \vdots } \\ { y _ { M } ( t ) } \end{array} \right] } = { \left[ \begin{array} { l l l l } { e ^ { - j \beta x _ { 1 } \sin ( \theta _ { 1 } ) } } & { e ^ { - j \beta x _ { 1 } \sin ( \theta _ { 2 } ) } \cdots e ^ { - j \beta x _ { 1 } \sin ( \theta _ { L } ) } } \\ { e ^ { - j \beta x _ { 2 } \sin ( \theta _ { 1 } ) } } & { e ^ { - j \beta x _ { 2 } \sin ( \theta _ { 2 } ) } \cdots e ^ { - j \beta x _ { 2 } \sin ( \theta _ { L } ) } } \\ { \vdots } & { \vdots } \\ { e ^ { - j \beta x _ { M } \sin ( \theta _ { 1 } ) } } & { e ^ { - j \beta x _ { M } \sin ( \theta _ { 2 } ) } \cdots e ^ { - j \beta x _ { M } \sin ( \theta _ { L } ) } } \end{array} \right] } { \left[ \begin{array} { l } { x _ { 1 } ( t ) } \\ { x _ { 2 } ( t ) } \\ { \vdots } \\ { x _ { L } ( t ) } \end{array} \right] } + { \left[ \begin{array} { l } { n _ { 1 } ( t ) } \\ { n _ { 2 } ( t ) } \\ { \vdots } \\ { n _ { M } ( t ) } \end{array} \right] }
$$

将上述过程拓展到多观测矢量(multi measurement vector,MMV模型，设定快拍数为P，即对空域内所有感兴趣的信号进行 $\mathrm { ~ \bf ~ P ~ }$ 次观测，得到 $\mathrm { ~ \bf ~ P ~ }$ 个如式(2)所示的观测矢量，用矩阵的形式表示为

$$
Y { = } \Phi X { + } N _ { _ { X } }
$$

$\boldsymbol { Y } \in \boldsymbol { R } ^ { M \times P }$ 是 $\mathrm { ~ \bf ~ P ~ }$ 个测量矢量组成的观测矩阵， $\Phi$ 是由空域密集网格划分构成的过完备基矩阵，在MMV模型中，称为感知矩阵。待重构信号 $\boldsymbol { X } \in \boldsymbol { R } ^ { N \times P }$ ， $ { N _ { s } }$ 为加性高斯噪声。本文进行DOA估计的关键就是求解信号源矩阵 $\boldsymbol { \cal X }$ 中不同列向量之间非零信号的位置，即对应信号的方位角。

# 1.2块稀疏MMV模型

在上述MMV模型中，本文作以下假设：信号 $\boldsymbol { \cal X }$ 中不同列向量间非零位置相同。通过这一假设， $\boldsymbol { \cal X }$ 就具备了行稀疏(row sparse)性[4]，非零行矢量具备了分块稀疏的基础，块稀疏的优势在于它能充分利用信号内部的结构特性，以及非零块之间的时域相关性，提高信号的稀疏重构性能，应用到DOA估计中，可以得到更好的估计效果，更快的收敛速度。

下面建立与之对应的块稀疏MMV模型。将信号矩阵X分为 $\mathbf { g }$ 块，非零信号块个数W满足 $\mathbf { w } \ll g$ ，第P个信号块用$x _ { { P } }$ 表示，每个块大小为 $d _ { i }$ ， $d _ { i }$ 大小可以不相等，这一点区别于传统块稀疏重构算法。其分块结构式如下

$$
X = [ \underbrace { x _ { i } , \cdots , x _ { d _ { 1 } } } _ { x _ { 1 } ^ { T } } , \underbrace { x _ { d _ { 1 } + 1 } , \cdots x _ { d _ { 2 } + d _ { 1 } } } _ { x _ { 2 } ^ { T } } , \cdots \underbrace { x _ { N - d _ { g } } , \cdots , x _ { N } } _ { x _ { g } ^ { T } } ] ^ { T }
$$

同时，感知矩阵 $\Phi$ 相应地分成 $\mathbf { g }$ 块， $\Phi { = } \{ \Phi _ { \mathrm { 1 } } , \Phi _ { \mathrm { 2 } } { \cdots } \Phi _ { \mathrm { g } } \}$ ，$\Phi _ { i }$ 为对应第 $i$ 个信号块 $x _ { i }$ 的 $M \times d _ { i }$ 维基矢量。

# 2 空时联合的块稀疏贝叶斯学习算法

本章主要思路是构建空时联合块稀疏贝叶斯学习框架下的信号DOA估计模型，然后给出相应的算法步骤。首先建立贝叶斯框架下块稀疏模型，然后针对多测量条件下群目标信号所具有的空时相关性[5]，提出空时联合稀疏的思想，推导了模型中时域特性参数和结构特性参数的迭代求解方法，实现了信号的重构，进而实现对目标信号源的DOA估计。

# 2.1贝叶斯框架下块稀疏模型的构建

对块稀疏模型的处理常使用稀疏贝叶斯学习的方法，这是因为稀疏贝叶斯学习不但可以方便地对各类物理信息进行建模描述，而且其重构性能优异且对相关性较强的感知矩阵有较好的鲁棒性[6]。稀疏贝叶斯学习(sparseBayesianlearning，SBL)由Tipping[7首次提出，并经过Wipf等人不断改进，在稀疏信号重构领域收到了越来越多研究学者的青睐。该方法通过对观测y和信号 $\textbf { \em x }$ 建立分层贝叶斯模型，采用参数化的概率模型对系统求解，为求解稀疏的结构信息提供了一种非常灵活的数学方法

$$
\begin{array} { l } { p \left( { \boldsymbol y } | \beta \right) \sim N \left( { \boldsymbol y } ; \phi \boldsymbol { x } , \beta ^ { - 1 } \boldsymbol { I } \right) } \\ { p \left( x _ { i } | \gamma _ { i } \right) \sim N \left( x _ { i } ; 0 , \gamma _ { i } \right) \quad i = 1 , \cdots N } \end{array}
$$

由于这一方法是在单观测矢量(SMV的前提下提出的，因此，本文把上文所建立的块稀疏MMV模型转换为单观测矢量下的块稀疏贝叶斯模型，从而套用上式进行分析。

利用Kronecker积[8]将多测量矢量映射为单测量矢量，具体步骤为

$$
\begin{array} { l } { y \triangleq \mathit { \nu e c } \left( Y ^ { T } \right) } \\ { A = \Phi \otimes I } \\ { x \triangleq \mathit { \nu e c } \left( X ^ { T } \right) \left( \mathit { \nu e c } \left( X ^ { T } \right) \right) } \\ { n \triangleq \mathit { \nu e c } \left( N ^ { T } \right) } \end{array}
$$

其中： $\pmb { X } \in \pmb { R } ^ { N P \times 1 }$ ， $A \in { R } ^ { P M \times P N }$ ， $y \in R ^ { M P \times 1 }$ 。得到单观测矢量下的块稀疏贝叶斯学习的DOA估计模型

$$
y = A x + n
$$

在这一模型下，信号 $\textbf { \em x }$ 是分块稀疏的，每一个信号块 $x _ { i }$ 大小为 $\ d _ { i } \times P$ ，其信号模型示意图如图2所示。

![](images/4a88e3a9e3d67df227023c3ccb2e5150c6eecdd897d8c15145926ac8b64157d3.jpg)  
图2空时块稀疏信号示意图  
Fig.2Space-time block sparse signal diagram

正如图1中阵列接收，远场信号往往呈现多目标、集群化的特点，这就造成了目标信号不仅在空域（MMV模型的行向量）是分块稀疏的，而且时域回波（MMV模型的列向量）也存在很强的相关性[9]。如何利用这两类信息，研究快速、高性能重构算法，是本文最关心的问题。基于以上考虑，本文提出了空时联合块稀疏贝叶斯学习算法，在BSBL算法的基础上，将信号的分块稀疏特性（block sparse）、块内相关性结构（intra-blockcorrelation）以及多观测矢量时域相关性结构联合起来，提升重构性能。

# 2.2 基于 STC-BSBL算法的 DOA 估计

引入超参量 $\gamma _ { i }$ ， $B _ { i }$ ，其中， $\gamma _ { i }$ 代表第 $i$ 行向量 $X _ { i }$ 与观测矩阵Y的相关性，信号的 $\gamma _ { i }$ 较大，噪声的 $\gamma _ { i }$ 较小，在参数 $\gamma _ { i }$ 的学习中，其值越大， $x _ { i }$ 就越有可能是信号分量，其值越小，越有可能是噪声分量，一旦确定了 $\gamma _ { i }$ 中的非零位置，信号的方位角随之确定。因此对超参量 $\gamma _ { i }$ 的学习是核心。而对于块稀疏信号而言，还需要考虑块内结构，引入参量 $B _ { i }$ ，定义$A _ { i } = \gamma _ { i } B _ { i }$ 为 $x _ { i }$ 的协方差矩阵，A也是一个正定对称矩阵，用来描述信号X的空域相关性。

对于时域相关性的建模，本文从实际情况出发，假设信号矩阵X的列向量都满足同一个时域相关结构 $B$ ，则

$$
p ( x _ { i } ; A _ { i } , B ) = N ( x _ { i } ; 0 , A _ { i } \otimes B )
$$

进一步假设信号矩阵X中各行向量不相关，则式(9)可以写为

$$
p ( x | \boldsymbol { r } , \boldsymbol { B } ) = N ( x ; 0 , \boldsymbol { r } \otimes \boldsymbol { B } )
$$

$$
\boldsymbol { \Gamma } = d i a g ^ { - 1 } ( \{ A _ { \iota } , A _ { \scriptscriptstyle 2 } , \cdots A _ { \scriptscriptstyle N } \} )
$$

假设噪声服从零均值高斯分布，即

$$
N _ { p q } \sim N ( 0 , \lambda ) \ \forall p , q
$$

则

$$
p ( y | x ; \lambda ) \sim N _ { y | x } ( \psi _ { X , \lambda I ) }
$$

新的感知矩阵 $\scriptstyle { \psi = \phi \otimes I }$ 过于巨大（其大小为 $P M \times P N$ ），在稀疏重构算法中，存储和计算每一个感知矩阵块都要耗费很大的存储空间，因此，考虑引入矩形正态分布，将SMV模型转换为矩阵形式下的贝叶斯学习模型[10]。

由此更新式(10)(11)，得到MMV模型下 $\mathrm { \Delta } \mathrm { X }$ 的先验分布和观测信号模型

$$
p ( \boldsymbol { X } | \boldsymbol { r } , \boldsymbol { B } ) = M N ( \boldsymbol { X } ; 0 , \boldsymbol { r } , \boldsymbol { B } )
$$

$$
p ( Y | \lambda , B ) = M N ( Y ; \phi X , \lambda I , B )
$$

结合先验概率模型式(12)(13)，得到似然函数和后验概率公式为

$$
\begin{array} { c } { { p ( Y | \lambda , \bar { C } , B ) = p ( \displaystyle Y | X , \lambda ) p ( X | \bar { I } , B ) } } \\ { { { } } } \\ { { = M N ( Y ; 0 , C , B ) } } \\ { { { } } } \\ { { p ( X | Y ; \lambda , \bar { I } , B ) = N ( \mu , \bar { { } } ) } } \end{array}
$$

其中：

$$
\boldsymbol { C } = \lambda \boldsymbol { I } + \phi \boldsymbol { \Gamma } \phi ^ { \intercal }
$$

均值为

$$
\mu = \big / _ { \lambda } \Sigma \phi ^ { _ T } Y
$$

方差为

$$
\Sigma = \left( { \varGamma ^ { - 1 } + \gamma _ { \lambda } \phi ^ { \tau } \phi } \right) ^ { - 1 }
$$

首先，对超参量 $\lambda$ 的估计，常把它当做一个罚参数，根据信噪比的不同，对 $\lambda$ 赋予不同的值[11]

$$
\lambda = \left\{ \begin{array} { l l } { 0 . 1 \| y \| _ { 2 } ^ { 2 } , } & { S N R < 2 0 d B } \\ { 0 . 0 1 \| y \| _ { 2 } ^ { 2 } , } & { S N R < 2 0 d B } \\ { 1 0 ^ { - 6 } , } & { \widehat { \mathcal { D } } \widehat { \mathbb { H } } _ { \mathbb { K } } ^ { \frac { \Xi } { \mu _ { \mathbb { K } } ^ { 4 } } \widehat { \mathbb { F } ^ { \pm 1 } } } } \end{array} \right.
$$

对均值和协方差的求解等价于对超参量A、 $B$ 的估计问题，正确估计出超参量即可获得最大后验概率的解，从而重构 X，得到所需的DOA估计，为此，构造如下的对数似然函数：

$$
L = M \log | B | + P \log | C | + T r \big [ B ^ { \scriptscriptstyle - 1 } Y ^ { \scriptscriptstyle T } C ^ { \scriptscriptstyle - 1 } Y \big ]
$$

通过对似然函数中各个超参量求偏导，可得到各参量的更新公式，为了简化计算，将上式写成两个代价函数的形式。

$$
L ( B ) \triangleq M \log \left| B \right| + T r \left[ B ^ { \scriptscriptstyle - 1 } Y ^ { \scriptscriptstyle T } C ^ { \scriptscriptstyle - 1 } Y \right]
$$

$$
L ( A _ { ; } ) \triangleq P \log \left| C \right| + T r \left[ B ^ { \scriptscriptstyle - 1 } Y ^ { \scriptscriptstyle T } C ^ { \scriptscriptstyle - 1 } Y \right]
$$

在 $L ( B )$ 中，将 $A _ { i }$ 看做已知变量， $L ( A _ { i } )$ 中，将 $B$ 看做已知变量，通过给 $B$ 一个初始化的值，采用式(17)与式(18)对超参量进行交替更新[12]，步骤为，首先初始化 $B = 1$ ，更新 $L ( A _ { i } )$ 得到A，随后计算得到 $c$ ，继续对 $L ( B )$ 更新得到新的 $B$ 。经过 $\mathbf { k }$ 次迭代后， $A _ { i }$ ， $B$ 收敛于一稳定值。

对于参量 $B$ 的更新，可以直接对 $L ( B )$ 求偏导

$$
\frac { \hat { \sigma } L ( B ) } { \hat { \sigma } B } { = } M B ^ { - 1 } - B ^ { - 1 } Y ^ { T } C ^ { - 1 } Y B ^ { - 1 }
$$

令 $\frac { \partial L ( B ) } { \partial B } = 0$ ，得

$$
B = \frac { Y ^ { T } C ^ { - 1 } Y } { M }
$$

对块相关矩阵 $A _ { i }$ 的更新，代价函数 $L ( A _ { i } )$ 中的 $c$ 可写为

$$
\pmb { C } = \pmb { D } _ { - i } + \pmb { \phi } _ { i } \pmb { A } _ { i } \pmb { \phi } _ { i } ^ { T }
$$

其中定义D=λ+∑ΦCmΦ

应用矩阵求逆定理[13并对代价函数进行最小化处理可得

$$
{ \pmb { S } } _ { i } \triangleq { \pmb { \phi } } _ { i } ^ { T } { \pmb { D } } _ { - i } ^ { - 1 } { \pmb { Y } }
$$

$$
q _ { i } \triangleq \phi _ { { \scriptscriptstyle i } } ^ { { \scriptscriptstyle T } } D _ { { \scriptscriptstyle i } } ^ { { \scriptscriptstyle - 1 } } \phi _ { { \scriptscriptstyle i } }
$$

$$
A _ { i } = { \pmb S } _ { i } ^ { - 1 } \left( \frac { { \pmb q } _ { i } { \pmb B } ^ { - 1 } { \pmb q } _ { i } ^ { T } } { P } - { \pmb S } _ { i } \right) { \pmb S } _ { i } ^ { - 1 }
$$

通过计算得到的A，通过 $\gamma _ { i } { = } \frac { 1 } { d _ { i } } T r [ A _ { i } ]$ 计算得到 $\gamma _ { i } ^ { \phantom { i } } \left[ 1 4 \right]$ 。估计出所有的超参量后，后验概率密度得出，即

$$
X ^ { * } = \mu = \big ( \lambda \Sigma ^ { - 1 } + \Phi ^ { T } \Phi \big ) \Phi ^ { T } Y
$$

$$
\mathbf { \Sigma } = \Sigma \mathbf { \varPhi } ^ { T } \left( \lambda I + \mathbf { \varPhi } ^ { T } \Sigma \mathbf { \varPhi } \right) ^ { - 1 } \mathbf { \varPsi } ^ { \prime }
$$

从而恢复出原信号，并根据 $\gamma _ { i }$ 的非零位置，完成信号的DOA估计。使用流程图来描述整个信号重构及DOA估计过程，如图3所示。

![](images/57bdfd356c3027a0c3bf2c0b409d84257ebeb0f541115d873f88cfadb0c9b710.jpg)  
图3基于STC-BSBL 算法的DOA估计流程图

# 3 仿真实验

# 3.1DOA估计效果比较

设定均匀线阵阵元数为30，阵元间距为信号频率对应的半波长，空域范围 $[ - 9 0 ^ { \circ } , 9 0 ^ { \circ } ]$ ，真实信号数目3，真实信号来波方位角 $\theta = [ 0 ^ { \circ } , 3 5 ^ { \circ } , 4 0 ^ { \circ } ] , i = 1 , 2 , 3$ ，输入信噪比 $\mathrm { S N R = } 8 \mathrm { d B }$ ，快拍数$\scriptstyle \mathrm { P = 1 0 0 }$ 。进行1000次蒙特卡洛实验，DOA估计结果如图 4所示。

将凸优化类正交匹配追踪（OMP）算法和基于子空间类的MUSIC算法对信号进行DOA估计，与本文所使用的STC-BSBL算法的DOA估计效果进行比较。信号数目为4,来波方向分别为 $\theta = \left[ 3 0 ^ { \circ } , 4 5 ^ { \circ } , 6 0 ^ { \circ } , 7 5 ^ { \circ } \right]$ ，其他条件同上文不变。从仿真结果如图5所示。

![](images/978189d28d3b82a96ee65689964d4ebc9e12ac299b3ea84e1ce338b8cc1f6efe.jpg)  
Fig.3DOA estimation flow chart based on STC-BSBL algorithm   
图4STC-BSBL算法的DOA估计效果Fig.4DOA estimation effect of STC-BSBL algorithm

![](images/d9fd71394c260c41a4b4d0d8ef166c3b908b977dd72b4a9c436e50c89659d5f0.jpg)  
图5不同算法的DOA估计效果对比

从仿真结果可以看出，在给定的条件下，三种方法均能实现对信号的DOA估计，但从估计精度的角度上看，STC-BSBL算法和OMP算法拥有比MUSIC算法更窄的角度估计范围，和更低的幅值适应度。

# 3.2DOA 估计正确率对比

目前，基于稀疏分解的DOA估计算法除了凸优化类算法，还包括稀疏贝叶斯学习框架下常用的块稀疏贝叶斯学习算法（BSBL)，基于时序结构的稀疏贝叶斯学习（TM-SBL）[15],本实验以稀疏度K为自变量，仿真了这三种方法的 DOA估计正确率并与本文方法进行对比。四种方法在不同稀疏度下的识别正确率曲线如图6所示。

![](images/299079ab4e95105d768a01c0c17b0f936f0a0b55b71a036164061eb0eaf1f7e4.jpg)  
图6识别正确率  
Fig.6The correct recognition rate

从仿真结果可以看出，本文使用的STC-BSBL算法在同等的测量条件下有着更好的重构性能，在同等稀疏度下，有着更高的DOA估计正确率，且能适应更多数目的信号DOA估计。

# 3.3仿真实验3DOA估计均方根误差分析

为了能更好地凸显本文算法在DOA估计的优越性，分别以信噪比和快拍数为自变量，比较五种方法在进行DOA估计是的均方误差曲线。定义DOA估计的均方根误差为

$$
\mathit { R M S E } { = } \sqrt { \frac { 1 } { \mathit { K J } } \sum _ { j = 1 } ^ { J } \sum _ { k = 1 } ^ { K } \left( \hat { \theta } _ { k j } - \theta _ { k } \right) ^ { 2 } }
$$

结果如图7、8所示，从图中可以看出，随着信噪比和快拍数的提高，每种算法的RMSE均在减小，但在低信噪比和小快拍数时，OMP算法和ISSM算法的估计误差明显增大。BSBL和TM-SBL算法利用了信号的块内结构或时域相关结构，重构误差有一定降低，但STC-BSBL算法由于联合了信号的空域相关性和时域相关性，估计误差始终是最小的。

![](images/0b864f6867738bc1d482bd38e9ba096e2b310e70a1aba36685c4ff110aa89701.jpg)  
图7均方根误差随信噪比的变化曲线

![](images/cd9023343d29c7ed413632d7f681ba2aad7c6ebcc2912427f2dc92b6b65b3015.jpg)  
Fig.5Effect Comparison of different algorithms ofDOA estimation   
Fig.7Variation ofRMSE with the SNR   
图8均方根误差随快拍数的变化曲线  
Fig.8Variation of RMSE with the number of snapshot

# 4 结束语

本文在稀疏贝叶斯学习框架下，分析了块稀疏理论在稀疏信号重构方面的优越性，推导了块稀疏贝叶斯学习模型，并针对多观测矢量模型下的窄带信号DOA估计问题，构建了块稀疏MMV模型，在现有的BSBL算法的基础上进行改进，在考虑信号块内相关性的基础上，联合了多次观测下信号的时域相关性，提出空时联合块稀疏贝叶斯学习算法。通过比较实验，证明了该算法对雷达信号DOA估计在测向精度上有着更好的效果。

# 参考文献：

[1]李子高，李淑秋，闻疏琳．一种改进的正交匹配追踪的DOA估计方 法[J]．测控技术，2017,36(1):27-31.(Li Zigao,Li Shuqiu，Wen Shulin.An improved DOA estimation method based on orthogonal matching pursuit [J].TT&C Technology,2017,36(1): 27-31.)   
[2]Eldar Y C,Patrick K,Bolcskei H. Block-sparse signals:uncertainty relations and efficient recovery [J].IEEE Trans on Signal Processing, 2010,58(6):3042-3054.   
[3]Zhang Zhilin，Rao B D.Sparse signal recovery with temporally correlated source vectors using sparse Bayesian learning [J]. IEEE Journal of Selected Topics in Signal Processing.2011,5(5): 912-926.   
[4]Wipf D P,Rao B D.An empirical Bayesian strategy for solving the simultaneous sparse approximation problem[J]. IEEE Trans on Signal Processing,2007,55(7):3704-3716.   
[5]Zhang Zhilin,Jung T P,Makeig S,et al.Spatiotemporal sparse Bayesian learning with applications to compressed sensingof multichannel physiological signals [J]. IEEE Trans on Neural Systems x ΛUHauIHtauun LHgcIHg,∠U1+,∠(U).1Iou-117. [6]Tipping M E.Sparse Bayesian learning and the relevance vector machine [J].Journal of Machine Learning Research，2Oo1,1(3):   
211-244. [7]Tipping M E.Sparse Bayesian learning and the relevance vector machine.[J].Journal of Machine Learning Research，2Oo1,1(3):   
211-244. [8]方青，张弓，贲德．基于块稀疏贝叶斯学习的多任务压缩感知重构 算法[J].物理学报，2015,64(7):70201-070201.(Fang Qing，Zhang Gong,Yi De.Multitask compressed sensing reconstruction algorithm based on block sparse Bayesian learning [J].Acta Physics,2O15,64(7):   
70201-070201.) [9]Ziniel J,Schniter P.Efficient high-dimensional inference in the multiple measurement vector problem [J]. IEEE Trans on Signal Processing,   
2013,61(2):340-354. [10]刘本源．快速块稀疏贝叶斯学习算法的理论与应用[D].长沙：国防 科学技术 大学，2O15.(Liu Benyuan.Theory and application of fast block sparse Bayesian learning algorithm [D].Changsha:National University of Defense Science and Technology,2015.)   
[11] YuL,Sun H,BarbotJP,et al.Bayesian compressive sensing for cluster structured sparse signals [J]. Signal Processing,2012,92(1): 259-269.   
[12]张新月．基于稀疏重构算法的宽带信号DOA 估计研究[D].成都： 电子科技大学,2015.(Zhang Xinyue.Research on DOA estimation of broadband signals based on sparse reconstruction algorithm [D]. Chengdu:Xidian University,2015.)   
[13]Roweis S. Matrix identities[EB/OL]. (1999-06). https://cs.nyu.edu/\~roweis/notes/matrixid.pdf.   
[14]王彪，朱志慧，戴跃伟．一种快速稀疏贝叶斯学习的水声目标方位 估计方法研究[J]．声学学报，2016.41(1):81-86.(Wang Biao,Zhu Zhihui and Dai Yuewei.A fast sparse Bayesian learning method for underwater acoustic target azimuth estimation [J].Acta Acoustica Sinica,2016,41(1):81-86.)   
[15] Zhang Zhilin,Bhaskar D.Rao.Recovery of block sparse signals using the framework of block sparse Bayesian learning [C]//Proc of IEEE International Conference on Acoustics,Speech and Signal Processing. 2012:3345.