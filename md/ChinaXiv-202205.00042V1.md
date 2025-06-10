# 随机环境下上临界分支过程的非一致性 Berry-Esseen 估计

范协钰①，吴浩①，叶印娜②\*

$\textcircled{1}$ 天津大学应用数学中心，天津 300072;  
$\textcircled{2}$ 西交利物浦大学理学院应用数学系，苏州215123  
E-mail: fanxiequan@hotmail.com,wuhao_math@tju.edu.cn,yinna.ye@xjtlu.edu.cn

国家自然科学基金(批准号：11971063）资助项目

摘要设 $( Z _ { n } ) _ { n \geqslant 0 }$ 是一个独立同分布环境下的上临界分支过程．本文得到了两个关于 $( Z _ { n } ) _ { n \geqslant 0 }$ 的非一致性 Berry-Esseen 估计.该结果把 Grama et al.[Stochastic Process.Appl.,127(4),1255-1281,2017]的 Berry-Esseen估计推广到了非一致性的情形．最后，我们讨论了这些结果在区间估计方面的应用.

关键词分支过程随机环境非一致性 Berry-Esseen 估计MSC（2020）主题分类60J80，60K37，60F05，62E20

# 1引言

随机环境下的分支过程最早由 Smith 和Wilkinson [1]引入，它是Galton-Watson 过程的一个推广.记 $\xi = ( \xi _ { 0 } , \xi _ { 1 } , \ldots )$ 是一列独立同分布的随机变量,其中 $\xi _ { n }$ 代表第 $\mathbf { \Omega } _ { n }$ 代的随机环境.随机环境下的分支过程 $( Z _ { n } ) _ { n \geqslant 0 }$ 有如下表达式：

$$
Z _ { 0 } = 1 , \ Z _ { n + 1 } = \sum _ { i = 1 } ^ { Z _ { n } } X _ { n , i } , \ n \geqslant 0 ,
$$

其中 $X _ { n , i }$ 代表第 $n$ 代第 $\mathbf { \chi } _ { i }$ 个个体的后代数目．随机变量 $X _ { n , i }$ 的分布依赖于环境 $\xi _ { n }$ ，其分布律为$p \left( \xi _ { n } \right) = \{ p _ { k } \left( \xi _ { n } \right) = \mathbb { P } ( X _ { n , i } = k | \xi _ { n } ) : k \in \mathbb { N } \}$ ．对给定的 $\xi _ { n }$ ， $( X _ { n , i } ) _ { i \geqslant 1 }$ 是一列独立同分布的随机变量；而且 $( X _ { n , i } ) _ { i \geqslant 1 }$ 与 $( Z _ { 1 } , \ldots , Z _ { n } )$ 独立.记 $( \Gamma , \mathbb { P } _ { \xi } )$ 为随机环境 $\xi$ 给定后的条件概率空间,其中 $\mathbb { P } _ { \xi }$ 通常称为淬火分布 (quenced law).记 $\Theta$ 为随机环境 $\xi$ 的状态空间,则总的概率空间可以由乘积空间 $\left( \Theta ^ { \mathbb { N } } \times \Gamma , \mathbb { P } \right)$ 来表示,其中 $\mathbb { P } ( d x , d \xi ) = \mathbb { P } _ { \xi } ( d x ) \tau ( d \xi )$ ，根据定义，对于任意的定义在完全概率空间 $\Theta ^ { \mathbb { N } } \times \Gamma$ 上的非负可测函数 $g$ ，我们有

$$
\int g ( x , \xi ) \mathbb { P } ( d x , d \xi ) = \int \int g ( x , \xi ) \mathbb { P } _ { \xi } ( d x ) \tau ( d \xi ) ,
$$

其中 $\tau$ 代表环境 $\xi$ 的分布律.通常称 $\mathbb { P }$ 为退火分布 (annealed law)．而 $\mathbb { P } _ { \xi }$ 可以看成 $\mathbb { P }$ 在给定环境 $\xi$ 下的条件概率.我们用 $\mathbb { E } _ { \xi }$ 和 $\mathbb { E }$ 分别表示概率 $\mathbb { P } _ { \xi }$ 和 $\mathbb { P }$ 下的数学期望．对给定的 $\xi$ ，非负整数 $n \geqslant 0$ 和正实数 $p > 0$ ，定义

$$
m _ { n } ^ { ( p ) } = m _ { n } ^ { ( p ) } ( \xi ) = \sum _ { i = 0 } ^ { \infty } i ^ { p } p _ { i } ( \xi _ { n } ) , \quad m _ { n } = m _ { n } ( \xi ) = m _ { n } ^ { ( 1 ) } ( \xi ) .
$$

则

$$
m _ { 0 } ^ { ( p ) } = \mathbb { E } _ { \xi } Z _ { 1 } ^ { p } \quad \mathrm { ~ \textmu ~ { ~ H ~ } ~ } \ m _ { n } = \mathbb { E } _ { \xi } X _ { n , i } , \quad i \geqslant 1 .
$$

考虑下面的随机变量

$$
\Pi _ { 0 } = 1 , \quad \Pi _ { n } = \Pi _ { n } ( \xi ) = \prod _ { i = 0 } ^ { n - 1 } m _ { i } , \quad n \geqslant 1 .
$$

容易验证

$$
\mathbb { E } _ { \xi } Z _ { n + 1 } = \mathbb { E } _ { \xi } \Big ( \sum _ { i = 1 } ^ { Z _ { n } } X _ { n , i } \Big ) = \mathbb { E } _ { \xi } \Big [ \mathbb { E } _ { \xi } \Big ( \sum _ { i = 1 } ^ { Z _ { n } } X _ { n , i } \Big | Z _ { n } \Big ) \Big ] = \mathbb { E } _ { \xi } \Big ( \sum _ { i = 1 } ^ { Z _ { n } } m _ { n } \Big ) = m _ { n } \mathbb { E } _ { \xi } Z _ { n } .
$$

通过迭代,我们有 $\Pi _ { n } = \mathbb { E } _ { \xi } Z _ { n }$ .记

$$
X = \log m _ { 0 } , \quad \mu = \mathbb { E } X , \quad \sigma ^ { 2 } = \mathbb { E } ( X - \mu ) ^ { 2 } .
$$

根据参数 $\mu < 0 , \mu = 0$ 或 $\mu > 0$ 的不同,随机环境下的分支过程 $( Z _ { n } ) _ { n \geqslant 0 }$ 分别被称为下临界的，临界的或上临界的.因此， $\mu$ 也被称为关键参数

随机环境下的上临界分支过程的极限理论在过去的十多年间吸引了很多学者的研究，见Boinghoff[2],Li etal.[3],Wang 和 Liu [4],Fan etal.[5],Böinghoff和 Kersting [6],Huang 和 Liu [7]以及 $\mathrm { { X u } }$ [8].特别地,Grama et al.[9] 得到了以下 Berry-Esseen 估计（见 [9] 中的定理1.1）．假设 $p _ { 0 } \left( \xi _ { 0 } \right) = 0$ 几乎处处成立，且存在两个常数 $p > 1$ 和 $\delta \in ( 0 , 1 ]$ 使得 $\mathbb { E } X ^ { 2 + \delta } < \infty$ 和 $\begin{array} { r } { \mathbb { E } \left( \frac { Z _ { 1 } } { m _ { 0 } } \right) ^ { p } < \infty } \end{array}$ 成立．则有下列关于 $\log Z _ { n }$ 的 Berry-Esseen 估计成立

$$
\operatorname* { s u p } _ { x \in \mathbb { R } } \left. \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right. \leqslant \frac { C } { n ^ { \delta / 2 } } ,
$$

其中 $C$ 是个正的常数.当 $\delta = 1$ 时,常数 $C$ 的渐近精确值由Gao[10]给出

本文的主要目的是建立关于 $\log Z _ { n }$ 的非一致性 Berry-Esseen 估计.虽然人们对独立随机变量之和的非一致性 Berry-Esseen 估计已经有了非常深入的研究,参考 Bikelis [11] 及 Chen 和 Shao [12] 的工作，但是到目前为止还未有随机环境下分支过程的非一致性 Berry-Esseen 估计.这篇文章的目标既是补充这方面的空白.我们得到了以下结果：对所有的 $\boldsymbol { x } \in \mathbb { R }$ 以及 $\delta ^ { ' } \in ( 0 , \delta )$ ，下式成立

$$
\left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } .
$$

根据 (2.1)，随机变量 $\log Z _ { n }$ 只有有限的 $1 + \delta ^ { ' }$ 阶矩,所以当 $| x |  \infty$ 时上述的非一致性 Berry-Esseen估计是以 $| x | ^ { - 1 - \delta ^ { ' } }$ 的速度衰减的，而不是 $| x | ^ { - 2 - \delta }$ 的速度衰减．显然，因为增加了代数衰减的因子，上面的非一致性 Berry-Esseen 估计比（1.1）的结果更加精确．此外，当 $X$ 具有矩母函数且 $\begin{array} { r } { \mathbb { E } \frac { Z _ { 1 } ^ { p } } { m _ { 0 } } < \infty } \end{array}$ 时，我们还得到了带有指数衰减速率的非一致性 Berry-Esseen 估计；见本文的定理2.

本文章的结构安排如下.在第二节,我们给出本文的主要结果.在第三节和第四节,我们分别给出主要结果的一些应用和证明．在本文中， $C$ 或 $\mid c \mid$ 都是代表正的常数，而 $C _ { K }$ 代表依赖于 $K$ 的正数，且它们的确切值可随所在位置的不同而变化，

# 2 主要结果

在本文中,记 $X _ { i } = \log m _ { i }$ ， $i \geqslant 0$ 显然， $( X _ { i } ) _ { i \geqslant 0 }$ 是一列独立同分布的随机变量且仅依赖于环境 $\xi$ 设 $( S _ { n } ) _ { n \geqslant 0 }$ 为随机环境下分支过程所对应的随机游动,其定义如下：

$$
S _ { 0 } = 0 , S _ { n } = \log \Pi _ { n } = \sum _ { i = 0 } ^ { n - 1 } X _ { i } , n \geqslant 1 .
$$

则可对 $\log Z _ { n }$ 进行如下分解

$$
\log Z _ { n } = S _ { n } + \log W _ { n } ,
$$

其中 $\begin{array} { r } { W _ { n } = \frac { Z _ { n } } { \Pi _ { n } } } \end{array}$ ．注意到无论是在测度 $\mathbb { P }$ 还是测度 $\mathbb { P } _ { \xi }$ 下, $W _ { n }$ 都是关于如下定义的 $\sigma -$ 代数流 $( \mathcal { F } _ { n } ) _ { n \geqslant 0 }$ 的非负鞅,

$$
\begin{array} { r } { \mathcal { F } _ { 0 } = \sigma \{ \xi \} , ~ \mathcal { F } _ { n } = \sigma \left\{ \xi , X _ { k , i } , 0 \leqslant k \leqslant n - 1 , i \geqslant 1 \right\} , ~ n \geqslant 1 . } \end{array}
$$

根据Doob鞅收敛定理和Fatou引理, $W _ { n }$ 的极限存在，记作 $W$ ，且 $W$ 满足 $\mathbb { E } W \leqslant 1$ ．本文通篇假设以下条件： $Z _ { 1 } \geqslant 1$ 几乎处处成立，

$$
\sigma \in ( 0 , \infty ) \quad \mathbb { E } \quad \mathbb { E } \frac { Z _ { 1 } } { m _ { 0 } } \log ^ { + } Z _ { 1 } < \infty .
$$

上述条件足以保证 $\mu > 0$ 5

$$
\mathbb { P } ( W > 0 ) = \mathbb { P } \left( Z _ { n } \stackrel { n \to \infty } { \longrightarrow } \infty \right) = 1
$$

且 $W _ { n }$ 依 $\mathbb { L } ^ { 1 } ( \mathbb { P } )$ 收敛到 $W$ ，详见Tanny [13]

记 $\log ^ { + } x = \operatorname* { m a x } \{ \log x , \ 0 \}$ 考虑以下两个条件：

(A1）存在常数 $\delta \in ( 0 , 1 ]$ 使得

$$
\mathbb { E } X ^ { 2 + \delta } = \mathbb { E } \left( \log m _ { 0 } \right) ^ { 2 + \delta } < \infty .
$$

(A2）存在常数 $p > 1$ 使得

$$
\mathbb { E } \left( \frac { m _ { 0 } ^ { ( p ) } } { m _ { 0 } ^ { p } } \right) < \infty .
$$

在上述条件下,我们得到了以下带有代数衰减速率的非一致性Berry-Esseen 估计.

定理1 假设条件（A1）和（A2）成立．则对任意的 $\boldsymbol { x } \in \mathbb { R }$ 以及 $\delta ^ { ' } \in ( 0 , \delta )$

$$
\left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } .
$$

显然，我们的结果不仅蕴含着Grama et al.[9]的 Berry-Esseen 估计(见 [9]中的定理1.1)．而且,通过增加一个代数衰减的因子 1+|z|1+，改进了Grama et al.[9]的结果.

记

$$
d _ { w } \left( X \right) = \int _ { - \infty } ^ { + \infty } \left| \mathbb { P } \left( X \leqslant x \right) - \Phi ( x ) \right| d x
$$

为随机变量 $X$ 和标准正态随机变量的 Wasserstein-1距离．则定理1蕴含以下推论.该推论给出了Wasserstein-1 距离下, $\left( \log Z _ { n } - n \mu \right) / \sigma { \sqrt { n } }$ 收敛到标准正态随机变量的速率.

推论1 在定理1的条件下，下式成立

$$
d _ { w } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \right) \leqslant \frac { C } { n ^ { \delta / 2 } } .
$$

接下来,我们考虑以下比（A1)和（A2)更强的条件：

(A3）存在常数 ${ \lambda _ { 0 } } > 0$ 使得

$$
\mathbb { E } e ^ { \lambda _ { 0 } X } = \mathbb { E } m _ { 0 } ^ { \lambda _ { 0 } } < \infty .
$$

(A4)存在常数 $p > 1$ 使得

$$
\mathbb { E } \left( \frac { Z _ { 1 } ^ { p } } { m _ { 0 } } \right) = \mathbb { E } \left( \frac { m _ { 0 } ^ { ( p ) } } { m _ { 0 } } \right) < \infty .
$$

在条件（A3)和（A4)下,我们有以下带有指数衰减速率的非一致性 Berry-Esseen 估计.此结果类似于Fan et al.[14]关于鞅的非一致性Berry-Esseen 估计.

定理2 假设条件（A3)和（A4)成立．则对任意的 $\boldsymbol { x } \in \mathbb { R }$

$$
\left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| \leqslant C \frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) \exp \left\{ - \frac { { \hat { x } } ^ { 2 } } { 2 } \right\} ,
$$

其中

$$
{ \hat { x } } = { \frac { | x | } { \sqrt { 1 + c | x | / { \sqrt { n } } } } } .
$$

在文章[9]中,Grama 等人在条件（A3)和（A4)下得到了Cramér 型中偏差.与Grama 等人的结果相比，(2.4)式的优势在于它对任意的 $\boldsymbol { x } \in \mathbb { R }$ 成立而不局限于 $\mathbf { \Psi } _ { x }$ 需满足 $0 \leqslant | x | = o ( { \sqrt { n } } )$ 的情况

# 3 区间估计上的应用

# 3.1 $\mu$ 的置信区间

若 $\sigma$ 已知，则定理1可以用于构造 $\mu$ 的置信区间.

定理3 假设定理1的条件成立．设 $\kappa _ { n } \in ( 0 , 1 )$ ，且满足

$$
\left| \log \kappa _ { n } \right| = o \left( \log n \right) , \quad n \to \infty .
$$

则对充分大的 $n$ $\left[ A _ { n } , B _ { n } \right]$ 是 $\mu$ 的置信水平为 $1 - \kappa _ { n }$ 的置信区间,其中

$$
A _ { n } = { \frac { \log Z _ { n } } { n } } - { \frac { \sigma \Phi ^ { - 1 } \left( 1 - { \frac { \kappa _ { n } } { 2 } } \right) } { \sqrt { n } } } , \qquad B _ { n } = { \frac { \log Z _ { n } } { n } } + { \frac { \sigma \Phi ^ { - 1 } \left( 1 - { \frac { \kappa _ { n } } { 2 } } \right) } { \sqrt { n } } } .
$$

证明 根据定理1，下面的式子

$$
\frac { \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x \right) } { 1 - \Phi ( x ) } = 1 + o ( 1 ) \quad \Xi \quad \frac { \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant - x \right) } { \Phi ( - x ) } = 1 + o ( 1 )
$$

在 $0 \leqslant x = o \left( { \sqrt { \log n } } \right)$ 上一致成立．当 $p \searrow 0$ ，标准正态分布的分位数具有以下展式

$$
\Phi ^ { - 1 } ( p ) = - \sqrt { \log \frac { 1 } { p ^ { 2 } } - \log \log \frac { 1 } { p ^ { 2 } } - \log ( 2 \pi ) } + o ( 1 ) .
$$

特别地,当 $\kappa _ { n }$ 满足条件(3.1)时,标准正态分布的 $\left( 1 - \kappa _ { n } / 2 \right)$ -分位数满足 $\Phi ^ { - 1 } \left( 1 - \kappa _ { n } / 2 \right) = - \Phi ^ { - 1 } \left( \kappa _ { n } / 2 \right) =$ $O ( { \sqrt { | \log \kappa _ { n } | } } )$ ，且它是 $\sqrt { \log n }$ 的无穷小量.根据 (3.2)式，当 $n  \infty$ 时，以下两个式子成立

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } > \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \right) \sim \frac { \kappa _ { n } } { 2 } ,
$$

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } < - \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \right) \sim \frac { \kappa _ { n } } { 2 } .
$$

因此,当 $n  \infty$ 时,

$$
\mathbb { P } \left( - \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \leqslant \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \right) \sim 1 - \kappa _ { n } .
$$

上式表明当 $\mathbf { \Omega } _ { n }$ 足够大时, $[ A _ { n } , B _ { n } ]$ 是 $\mu$ 的置信水平为 $1 - \kappa _ { n }$ 的置信区间.

# 3.2 $Z _ { n }$ 的置信区间

若参数 $\mu$ 与 $\sigma$ 都已知,我们可以运用定理1和2来构造 $Z _ { n }$ 的置信区间.这类置信区间可以用于预测人口数 $Z _ { n }$ ：

定理4设 $\kappa _ { n } \in ( 0 , 1 )$ .考虑下面(B1)与（B2)两组条件:

(B1）定理1的条件成立且

$$
\left| \log \kappa _ { n } \right| = o \left( \log n \right) , \quad n \to \infty .
$$

(B2）定理2的条件成立且

$$
\left| \log \kappa _ { n } \right| = o \big ( n ^ { 1 / 3 } \big ) , \quad n \to \infty .
$$

如果条件(B1)或(B2)满足，则对足够大的 $\mathbf { \Omega } _ { n }$ ， $[ A _ { n } , B _ { n } ]$ 是 $Z _ { n }$ 的置信水平为 $\mathbf { 1 } - \kappa _ { n }$ 的置信区间,其中

$$
A _ { n } = \exp \Big \{ n \mu - \sigma \sqrt { n } \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \Big \} , \qquad B _ { n } = \exp \Big \{ n \mu + \sigma \sqrt { n } \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \Big \} .
$$

证明 假设条件 (B1)满足.根据定理1和 (3.3),我们有：当 $n  \infty$ 时，

$$
\begin{array} { l } { \displaystyle \mathbb { P } \left( - \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \leqslant \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \right) } \\ { \displaystyle = \mathbb { P } \Bigg ( \exp \left\{ n \mu - \sigma \sqrt { n } \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \right\} \leqslant Z _ { n } \leqslant \exp \left\{ n \mu + \sigma \sqrt { n } \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } { 2 } \right) \right\} \Bigg ) \sim 1 - \kappa _ { n } . } \end{array}
$$

由上式可见，当 $\mathbf { \Omega } _ { n }$ 足够大时, $[ A _ { n } , B _ { n } ]$ 是 $Z _ { n }$ 的置信水平为 $\mathbf { 1 } - \kappa _ { n }$ 的置信区间.

现在,假设条件(B2)满足．根据定理2,我们有

$$
\frac { \mathbb { P } \left( { \frac { \log Z _ { n } - n \mu } { \sigma { \sqrt { n } } } } \geqslant x \right) } { 1 - \Phi ( x ) } = 1 + o ( 1 )
$$

$$
\frac { \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant - x \right) } { \Phi ( - x ) } = 1 + o ( 1 )
$$

在 $0 \leqslant x = o ( n ^ { 1 / 6 } )$ ， $n  \infty$ ，上一致成立．当 $\kappa _ { n }$ 满足条件（3.5）时，标准正态分布的 $( 1 - \kappa _ { n } / 2 )$ -分位数满足 $\Phi ^ { - 1 } \left( 1 - \kappa _ { n } / 2 \right) = - \Phi ^ { - 1 } \left( \kappa _ { n } / 2 \right) = O ( \sqrt { | \log \kappa _ { n } | } )$ ，且它是 $n ^ { 1 / 6 }$ 的无穷小量．然后，根据 (3.6)，我们有

$$
\begin{array} { r } { \mathbb P \bigg ( - \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } 2 \right) \leqslant \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant \Phi ^ { - 1 } \left( 1 - \frac { \kappa _ { n } } 2 \right) \bigg ) \sim 1 - \kappa _ { n } . } \end{array}
$$

由上式可见，结论仍然成立.

# 4主要结果的证明

# 4.1 定理1的准备引理

关于独立随机变量之和,Bikelis [11] 给出了以下非一致性 Berry-Esseen 估计.引理1设 $Y _ { 1 } , \dots , Y _ { n }$ 是相互独立的随机变量，且满足

$$
\mathbb { E } Y _ { i } = 0 \quad \stackrel { \in } { \to } \quad \mathbb { E } | Y _ { i } | ^ { 2 + \delta } < \infty , i = 1 , \ldots , n ,
$$

其中常数 $\delta \in ( 0 , 1 ]$ 假设 $\sum _ { i = 1 } ^ { n } \mathbb { E } Y _ { i } ^ { 2 } = 1$ ．则对任意的 $\boldsymbol { x } \in \mathbb { R }$ ，下式成立

$$
\left| \mathbb { P } \bigg ( \sum _ { i = 1 } ^ { n } Y _ { i } \leqslant x \bigg ) - \Phi ( x ) \right| \leqslant \frac { C } { 1 + | x | ^ { 2 + \delta } } \sum _ { i = 1 } ^ { n } \mathbb { E } \left| Y _ { i } \right| ^ { 2 + \delta } .
$$

考虑 $W$ 分别在 $\mathbb { P } _ { \xi }$ 和 $\mathbb { P }$ 下的拉普拉斯变换,即对任意的 $t > 0$

$$
\phi _ { \xi } ( t ) = \mathbb { E } _ { \xi } e ^ { - t W } \quad \not { \mathbb { H } } \quad \phi ( t ) = \mathbb { E } \phi _ { \xi } ( t ) = \mathbb { E } e ^ { - t W } .
$$

我们有下面的估计.

引理2 假设条件（A1)和（A2）成立．则对任意的 $t > 0$ 5

$$
\phi ( t ) \leqslant \frac { C } { 1 + ( \log ^ { + } t ) ^ { 1 + \delta } } .
$$

证明 引入位移运算符 $T ^ { n }$ ，即 $T ^ { n } \left( \xi _ { 0 } , \xi _ { 1 } , \ldots \right) = ( \xi _ { n } , \xi _ { n + 1 } , \ldots ) , n \geqslant 1 .$ 对给定的 $k \geqslant 0$ ，记

$$
\Pi _ { n } \left( T ^ { k } \xi \right) = m _ { k } \cdot \cdot \cdot m _ { k + n - 1 } .
$$

特别地,我们有 $\Pi _ { n } = \Pi _ { n } \left( T ^ { 0 } \xi \right)$ ．接下来,我们借鉴Grama et al.[15]的方法.由[15]中的(3.15)，可证明对任意的 $t > 0$ 和 $n \geqslant 1$ ，有

$$
\phi ( t ) \leqslant \mathbb { E } \phi \Bigl ( \frac { t } { \Pi _ { n } } \Bigr ) \prod _ { j = 0 } ^ { n - 1 } \bigl ( p _ { 1 } ( \xi _ { j } ) + ( 1 - p _ { 1 } ( \xi _ { j } ) ) \beta _ { K } \bigr ) + \frac { 1 } { K } \mathbb { E } \left[ \phi _ { T ^ { n } \xi } \Bigl ( \frac { t } { \Pi _ { n } } \Bigr ) \mathbb { E } _ { T ^ { n } \xi } W ^ { p } \right] + \mathbb { P } \Bigl ( \frac { t } { \Pi _ { n } } < t _ { K } \Bigr ) ,
$$

其中 $t _ { K } = ( C K ) ^ { - 1 / ( p - 1 ) }$ ， $C$ 和 $K$ 都是正数且满足下式

$$
\beta _ { K } : = 1 - ( 1 - 1 / p ) t _ { K } \in ( 0 , 1 ) .
$$

再由[15]中的 (3.18),有

$$
\mathbb { E } \left[ \phi _ { T ^ { n } \xi } \left( \frac { t } { \Pi _ { n } } \right) \mathbb { E } _ { T ^ { n } \xi } W ^ { p } \right] \leqslant \mathbb { E } \phi \left( \frac { t } { \Pi _ { n } } \right) + \sum _ { k = 0 } ^ { \infty } \mathbb { E } \frac { \phi \left( t / \Pi _ { k + 1 } ( T ^ { n } \xi ) \Pi _ { n } ( \xi ) \right) } { \Pi _ { k } ^ { p - 1 } ( T ^ { n } \xi ) } \frac { m _ { k } ^ { ( p ) } \left( T ^ { n } \xi \right) } { m _ { k } ^ { p } \left( T ^ { n } \xi \right) } .
$$

设 $p \in ( 1 , 2 ]$ ．对给定的 $( n , K )$ ， $\tilde { Y } _ { n , K }$ 是一个取值为正的随机变量,其分布定义如下：对于任意有界可测函数 $g$ ，

$$
\begin{array} { r c l } { \mathbb { E } g ( \tilde { Y } _ { n , K } ) } & { = } & { \displaystyle \frac { 1 } { q _ { n , K } } \left[ \mathbb { E } g \left( \frac { 1 } { \Pi _ { n } } \right) \prod _ { j = 0 } ^ { n - 1 } ( p _ { 1 } ( \xi _ { j } ) + ( 1 - p _ { 1 } ( \xi _ { j } ) ) \beta _ { K } ) \right. } \\ & & { \displaystyle + \left. \frac { 1 } { K } \mathbb { E } g \left( \frac { 1 } { \Pi _ { n } } \right) + \frac { 1 } { K } \sum _ { k = 0 } ^ { \infty } \mathbb { E } \frac { g \left( \frac { 1 } { \Pi _ { k + 1 } ( T ^ { n } \xi ) \Pi _ { n } ( \xi ) } \right) } { \Pi _ { k } ^ { p - 1 } ( T ^ { n } \xi ) } \frac { m _ { k } ^ { ( p ) } ( T ^ { n } \xi ) } { m _ { k } ^ { p } ( T ^ { n } \xi ) } \right] , } \end{array}
$$

其中 $q _ { n , K }$ 是归一化常数(使得当 $g = 1$ 时， $\mathbb { E } g ( \tilde { Y } _ { n , K } ) = 1 \quad$ ),其表达式如下：

$$
\begin{array} { r c l } { \displaystyle q _ { n , K } } & { = } & { \displaystyle \mathbb { E } \prod _ { j = 0 } ^ { n - 1 } \big ( p _ { 1 } ( \xi _ { j } ) + ( 1 - p _ { 1 } ( \xi _ { j } ) ) \beta _ { K } \big ) + \frac { 1 } { K } \left[ 1 + \sum _ { k = 0 } ^ { \infty } \mathbb { E } \frac { 1 } { \prod _ { k } ^ { p - 1 } \big ( T ^ { n } \xi \big ) } \frac { m _ { k } ^ { ( p ) } \big ( T ^ { n } \xi \big ) } { m _ { k } ^ { p } \big ( T ^ { n } \xi \big ) } \right] } \\ & { = } & { \Big [ \mathbb { E } \big ( p _ { 1 } ( \xi _ { 0 } ) + ( 1 - p _ { 1 } ( \xi _ { 0 } ) ) \beta _ { K } \big ) \Big ] ^ { n } + \frac { 1 } { K } \left[ 1 + \frac { 1 } { 1 - \mathbb { E } m _ { 0 } ^ { - ( p - 1 ) } } \mathbb { E } \Big ( \frac { m _ { 0 } ^ { ( p ) } } { m _ { 0 } ^ { p } } \Big ) \right] . } \end{array}
$$

上式来自 [15] 中的 (3.21).综合 (4.1)-(4.3)，可得

$$
\phi ( t ) \leqslant q _ { n , K } \mathbb { E } \phi ( \tilde { Y } _ { n , K } t ) + \mathbb { P } \Big ( \frac { t } { \Pi _ { n } } < t _ { K } \Big ) .
$$

选择常数 $A$ 满足 $\log A > \mu$ ，故有 $A > 1$ 当 $A ^ { n + 1 } \leqslant t < A ^ { n + 2 }$ 时取 $K = K _ { n } = ( ( n + 1 ) \log A ) ^ { 1 + \delta }$ ，则有 $\begin{array} { r } { \operatorname* { l i m } _ { n  \infty } \sqrt [ n ] { t _ { K _ { n } } } = 1 } \end{array}$ ，且，由 Nageav 不等式（见[16]中的推论 2.5)，当 $\mathbf { \Omega } _ { n }$ 足够大时有

$$
\mathbb { P } \Big ( \frac { t } { \prod _ { n } } < t _ { K _ { n } } \Big ) = \mathbb { P } \Big ( \Pi _ { n } > \frac { t } { t _ { K _ { n } } } \Big ) \leqslant \mathbb { P } \Big ( S _ { n } - n \mu > n \big ( \log \frac { A } { \sqrt [ \eta ] { t _ { K _ { n } } } } - \mu \big ) \Big ) \leqslant \frac { C } { n ^ { 1 + \delta } } .
$$

当 $t \geqslant A ^ { 2 }$ 时,设正整数 $\boldsymbol { n }$ 满足 $A ^ { n + 1 } \leqslant t < A ^ { n + 2 }$ ，则

$$
n > \frac { \log t } { \log A } - 2 .
$$

那么由 (4.6),对任意的 $A ^ { n + 1 } \leqslant t < A ^ { n + 2 }$ ，有

$$
\mathbb { P } \Big ( \frac { t } { \Pi _ { n } } < t _ { K _ { n } } \Big ) \leqslant \frac { C } { n ^ { 1 + \delta } } < C \left( \frac { \log t } { \log A } - 2 \right) ^ { - 1 - \delta } \leqslant \frac { C } { ( \log t ) ^ { 1 + \delta } } .
$$

注意到 $0 \leqslant \phi ( t ) \leqslant 1 \ ( t > 0 )$ ．所以由（4.5)和(4.7)，有

$$
\phi ( t ) \quad \leqslant \quad \sum _ { n = 1 } ^ { \infty } q _ { n , K _ { n } } \mathbf { 1 } _ { \left\{ A ^ { n + 1 } \leqslant t < A ^ { n + 2 } \right\} } + \frac { C } { 1 + ( \log ^ { + } t ) ^ { 1 + \delta } } .
$$

由 $q _ { n , K }$ 的定义（4.4）知当 $A ^ { n + 1 } \leqslant t < A ^ { n + 2 }$ 时，

$$
q _ { n , K _ { n } } \leqslant \frac { C } { 1 + ( \log ^ { + } t ) ^ { 1 + \delta } } .
$$

最后，由(4.8)和（4.9）可得：对任意的 $t > 0$

$$
\phi ( t ) \leqslant \frac { C } { 1 + ( \log ^ { + } t ) ^ { 1 + \delta } } .
$$

引理2证毕.

引理3假设条件（A1)和（A2)成立.则对任意的 $q \in ( 1 , 1 + \delta )$ ，下面两个不等式成立

$$
\mathbb { E } | \log W | ^ { q } < \infty
$$

和

$$
\operatorname* { s u p } _ { n \in \mathbb { N } } \mathbb { E } | \log W _ { n } | ^ { q } < \infty .
$$

证明 考虑关于 $\mathbb { E } | \log W | ^ { q }$ 的截断分解式

$$
\begin{array} { r } { \mathbb { E } | \log W | ^ { q } = \mathbb { E } | \log W | ^ { q } \mathbf { 1 } _ { \{ W > 1 \} } + \mathbb { E } | \log W | ^ { q } \mathbf { 1 } _ { \{ W \leqslant 1 \} } . } \end{array}
$$

对于上述等式右边的第一项,有

$$
\mathbb { E } | \log W | ^ { q } \mathbf { 1 } _ { \{ W > 1 \} } \leqslant C \mathbb { E } W < \infty .
$$

对于第二项,有

$$
\begin{array} { r c l } { { \displaystyle \mathbb { E } | \log W | ^ { q } { \bf 1 } _ { \{ W \leqslant 1 \} } } } & { { = } } & { { \displaystyle q \int _ { 1 } ^ { \infty } \frac { 1 } { t } ( \log t ) ^ { q - 1 } \mathbb { P } ( W \leqslant t ^ { - 1 } ) d t } } \\ { { } } & { { \leqslant } } & { { \displaystyle q e \int _ { 1 } ^ { \infty } \frac { \phi ( t ) } { t } ( \log t ) ^ { q - 1 } d t } } \\ { { } } & { { = } } & { { \displaystyle q e \left( \int _ { 1 } ^ { e } \frac { \phi ( t ) } { t } ( \log t ) ^ { q - 1 } d t + \int _ { e } ^ { \infty } \frac { \phi ( t ) } { t } ( \log t ) ^ { q - 1 } d t \right) . } } \end{array}
$$

上式中的不等式利用了Markov不等式，即有

$$
\mathbb { P } ( W \leqslant t ^ { - 1 } ) \leqslant e \mathbb { E } e ^ { - t W } = e \phi ( t ) .
$$

显然:

$$
\int _ { 1 } ^ { e } \frac { \phi ( t ) } { t } ( \log t ) ^ { q - 1 } d t < \infty .
$$

由引理2以及 $q < 1 + \delta$ ，我们有

$$
\int _ { e } ^ { \infty } \frac { \phi ( t ) } { t } ( \log t ) ^ { q - 1 } d t \leqslant C \int _ { e } ^ { \infty } \frac { 1 } { t ( \log t ) ^ { 2 + \delta - q } } d t < \infty .
$$

将(4.15)和(4.16)代入(4.14),可得

$$
\mathbb { E } | \log W | ^ { q } \mathbf { 1 } _ { \{ W \leqslant 1 \} } < \infty .
$$

因此，由(4.12),(4.13)以及(4.17),(4.10)得证.

下面证明 (4.11)．由于函数 $x \mapsto \left| \log ^ { q } ( x ) \mathbf { 1 } _ { \{ x \leqslant 1 \} } \right|$ ， $q > 1$ ，是非负凸的以及根据[7]中的引理 2.1,我们有

$$
\operatorname* { s u p } _ { n \in \mathbb { N } } \mathbb { E } \left| \log W _ { n } \right| ^ { q } \mathbf { 1 } _ { \left\{ W _ { n } \leqslant 1 \right\} } = \mathbb { E } \left| \log W \right| ^ { q } \mathbf { 1 } _ { \left\{ W \leqslant 1 \right\} } .
$$

通过类似于 $\mathbb { E } | \mathrm { l o g } W | ^ { q }$ 的截断方式并由（4.17）可得

$$
\begin{array} { l } { \displaystyle \operatorname* { s u p } _ { n \in \mathbb { N } } \mathbb { E } | \log W _ { n } | ^ { q } = \displaystyle \operatorname* { s u p } _ { n \in \mathbb { N } } \big ( \mathbb { E } | \log W _ { n } | ^ { q } \mathbf { 1 } _ { \{ W _ { n } > 1 \} } + \mathbb { E } | \log W _ { n } | ^ { q } \mathbf { 1 } _ { \{ W _ { n } \leqslant 1 \} } \big ) } \\ { \displaystyle \qquad \leqslant \operatorname* { s u p } _ { n \in \mathbb { N } } \mathbb { E } | \log W _ { n } | ^ { q } \mathbf { 1 } _ { \{ W _ { n } > 1 \} } + \displaystyle \operatorname* { s u p } _ { n \in \mathbb { N } } \mathbb { E } | \log W _ { n } | ^ { q } \mathbf { 1 } _ { \{ W _ { n } \leqslant 1 \} } } \\ { \displaystyle \qquad \leqslant C \mathbb { E } W + \mathbb { E } | \log W | ^ { q } \mathbf { 1 } _ { \{ W \leqslant 1 \} } < \infty . } \end{array}
$$

引理3得证.

以下引理引用自[9]中的引理2.4，其证明可参考[9].

引理4假设条件（A1)和（A2)成立.则存在常数 $\gamma \in ( 0 , 1 )$ 使得对任意的 $n \geqslant 0$ ，下式成立

$$
\mathbb { E } | \log W _ { n } - \log W | \leqslant C \gamma ^ { n } .
$$

在定理1的证明中，下面的引理起着关键作用，

引理5假设条件(A1)和(A2)成立.则对任意的 $\boldsymbol { x } \in \mathbb { R }$ 以及 $\delta ^ { ' } \in ( 0 , \delta )$ ，下面两个不等式成立

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x , \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x \right) \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } }
$$

和

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x , \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } .
$$

证明 由于(4.19)的证明方法与(4.18）的类似,我们仅证明(4.18).当 $\begin{array} { r } { x > \frac { \sqrt { n } \mu } { \sigma } } \end{array}$ ，我们有

$$
\mathbb P \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x , \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x \right) \leqslant \mathbb P \left( \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x \right) .
$$

根据引理1,当 $\begin{array} { r } { x > \frac { \sqrt { n } \mu } { \sigma } } \end{array}$ ，不等式(4.18)显然成立.当 $\begin{array} { r } { x < - \frac { \sqrt { n } \mu } { \sigma } } \end{array}$ ，根据 $Z _ { n } \geqslant 1$ 几乎处处成立,我们有

$$
{ \frac { \log Z _ { n } - n \mu } { \sigma { \sqrt { n } } } } \geqslant - { \frac { { \sqrt { n } } \mu } { \sigma } } .
$$

所以对任意的x<-μ

$$
\mathbb { P } \left( { \frac { \log Z _ { n } - n \mu } { \sigma { \sqrt { n } } } } \leqslant x , { \frac { S _ { n } - n \mu } { \sigma { \sqrt { n } } } } \geqslant x \right) = 0 .
$$

即不等式（4.18）对任意的 $\begin{array} { r } { | x | > \frac { \sqrt { n } \mu } { \sigma } } \end{array}$ 成立.

接下来，我们证明对任意的 $\begin{array} { r } { | x | \leqslant \frac { \sqrt { n } \mu } { \sigma } } \end{array}$ ，不等式（4.18）成立．定义

$$
Y _ { m , n } = \sum _ { i = m + 1 } ^ { n } { \frac { X _ { i } - \mu } { \sigma { \sqrt { n } } } } , \quad Y _ { n } = Y _ { 0 , n } , \quad V _ { m } = { \frac { \log { W _ { m } } } { \sigma { \sqrt { n } } } } , \quad D _ { m , n } = V _ { n } - V _ { m } .
$$

令 $\textstyle \alpha _ { n } = { \frac { 1 } { \sqrt { n } } }$ 和 $m = [ { \sqrt { n } } ]$ ,其中 []表示不超过 $\mathbf { \Psi } _ { t }$ 的最大整数．由(2.1）可得

$$
\begin{array} { r l } { \mathbb P \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x , \displaystyle \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x \right) \leqslant } & { \mathbb P \left( Y _ { n } + V _ { m } \leqslant x + \alpha _ { n } , Y _ { n } \geqslant x \right) } \\ & { \qquad + \mathbb P \left( | D _ { m , n } | > \alpha _ { n } \right) . } \end{array}
$$

对于不等式(4.20)右边的第二项,利用 Markov 不等式和引理4,可得存在一个常数 $\gamma \in ( 0 , 1 )$ ，使得对任意的 $\begin{array} { r } { | x | \leqslant \frac { \sqrt { n } \mu } { \sigma } } \end{array}$

$$
\mathbb { P } \left( \left| D _ { m , n } \right| > \alpha _ { n } \right) \leqslant \frac { \mathbb { E } \left| D _ { m , n } \right| } { \alpha _ { n } } = \frac { \sqrt { n } \mathbb { E } \left| \log W _ { n } - \log W _ { m } \right| } { \sigma \sqrt { n } } \leqslant C \gamma ^ { m } \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 2 + \delta } } .
$$

上述最后一个不等式成立的原因是 $n ^ { \delta / 2 } ( 1 + n ^ { ( 2 + \delta ) / 2 } ) \gamma ^ { m } = o ( 1 )$ ， $n  \infty$ ．对于不等式（4.20)右边的第一项,我们将运用分解的方法来控制它．令

$$
G _ { m , n } ( \boldsymbol { x } ) = \mathbb { P } \left( Y _ { m , n } \leqslant \boldsymbol { x } \right) , G _ { n } ( \boldsymbol { x } ) = \mathbb { P } \left( Y _ { n } \leqslant \boldsymbol { x } \right)
$$

由于 $Y _ { m , n }$ 和 $( Y _ { m } , V _ { m } )$ 是相互独立的,我们有

$$
\begin{array} { r l } & { \mathbb { P } \left( Y _ { n } + V _ { m } \leqslant x + \alpha _ { n } , Y _ { n } \geqslant x \right) } \\ & { = \mathbb { P } \left( Y _ { m , n } + Y _ { m } + V _ { m } \leqslant x + \alpha _ { n } , Y _ { m , n } + Y _ { m } \geqslant x \right) } \\ & { = \displaystyle \int \int \mathbb { P } \left( Y _ { m , n } + s + t \leqslant x + \alpha _ { n } , Y _ { m , n } + s \geqslant x \right) v _ { m } ( d s , d t ) } \\ & { = \displaystyle \int \int \mathbf { 1 } _ { \left\{ t \leqslant \alpha _ { n } \right\} } \left( G _ { m , n } \left( x - s - t + \alpha _ { n } \right) - G _ { m , n } ( x - s ) \right) v _ { m } ( d s , d t ) . } \end{array}
$$

注意到 $( X _ { i } ) _ { i \geqslant 1 }$ 是独立同分布的随机变量序列，因此 （20 $\sum _ { i = m + 1 } ^ { n } X _ { i }$ 和 $\sum _ { i = 1 } ^ { n - m } X _ { i }$ 同分布.于是,我们可以得到公

$$
\begin{array} { r c l } { G _ { m , n } ( x ) = \mathbb { P } \left( \displaystyle \sum _ { i = m + 1 } ^ { n } \frac { X _ { i } - \mu } { \sigma \sqrt { n } } \leqslant x \right) } & { = } & { \mathbb { P } \left( \displaystyle \sum _ { i = 1 } ^ { n - m } \frac { X _ { i } - \mu } { \sigma \sqrt { n - m } } \leqslant \displaystyle \frac { x \sqrt { n } } { \sqrt { n - m } } \right) } \\ & { = } & { G _ { n - m } \left( \displaystyle \frac { x \sqrt { n } } { \sqrt { n - m } } \right) = G _ { n - m } \left( x \left( 1 + R _ { n } \right) \right) , } \end{array}
$$

其中

$$
R _ { n } = { \sqrt { \frac { n } { n - m } } } - 1
$$

且 $\begin{array} { r } { 0 \leqslant R _ { n } \leqslant \frac { C } { \sqrt { n } } } \end{array}$ .利用微分中值定理，对任意的 $\boldsymbol { x } \in \mathbb { R }$ ，有

$$
\begin{array} { l c l } { \displaystyle \left| \Phi \left( x \left( 1 + R _ { n } \right) \right) - \Phi ( x ) \right| } & { \leqslant } & { \displaystyle R _ { n } \left| x \frac { 1 } { \sqrt { 2 \pi } } \exp \left\{ - \frac { x ^ { 2 } } { 2 } \right\} \right| \leqslant C \frac { 1 } { \sqrt { n } } \left| x \exp \left\{ - \frac { x ^ { 2 } } { 2 } \right\} \right| } \\ { \leqslant } & { C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 2 + \delta } } . } \end{array}
$$

由引理1可以推出

$$
\begin{array} { r c l } { | G _ { n - m } \left( x \left( 1 + R _ { n } \right) \right) - \Phi \left( x \left( 1 + R _ { n } \right) \right) | } & { = } & { \displaystyle \left| \mathbb { P } \left( \displaystyle \sum _ { i = 1 } ^ { n - m } \frac { X _ { i } - \mu } { \sigma \sqrt { n - m } } \leqslant \frac { x \sqrt { n } } { \sqrt { n - m } } \right) - \Phi \left( \frac { x \sqrt { n } } { \sqrt { n - m } } \right) \right| } \\ & { \leqslant } & { \displaystyle C \frac { 1 } { ( n - m ) ^ { \delta / 2 } } \frac { 1 } { 1 + | x \left( 1 + R _ { n } \right) | ^ { 2 + \delta } } } \\ & { \leqslant } & { \displaystyle C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 2 + \delta } } . } \end{array}
$$

综合 (4.23)-(4.25),我们有

$$
| G _ { m , n } ( x ) - \Phi ( x ) | \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 2 + \delta } } .
$$

因此，由 (4.22),我们可以得到

$$
\begin{array} { r } { \mathbb { P } \left( Y _ { n } + V _ { m } \leqslant x + \alpha _ { n } , Y _ { n } \geqslant x \right) \leqslant J _ { 1 } + J _ { 2 } + J _ { 3 } , } \end{array}
$$

其中

$$
\begin{array} { l } { \displaystyle { J _ { 1 } = \int \int \mathbf { 1 } _ { \{ t \leqslant \alpha _ { n } \} } \left| \Phi \left( x - s - t + \alpha _ { n } \right) - \Phi ( x - s ) \right| v _ { m } ( d s , d t ) , } } \\ { \displaystyle { J _ { 2 } = C \frac { 1 } { n ^ { \delta / 2 } } \int \int \mathbf { 1 } _ { \{ t \leqslant \alpha _ { n } \} } \frac { 1 } { 1 + | x - s | ^ { 2 + \delta } } v _ { m } ( d s , d t ) } } \end{array}
$$

和

$$
\begin{array} { r c l } { { \cal J } _ { 3 } } & { { = } } & { { \displaystyle C \frac { 1 } { n ^ { \delta / 2 } } \int \int { \bf 1 } _ { \{ t \leqslant \alpha _ { n } \} } \frac { 1 } { 1 + | x - s - t + \alpha _ { n } | ^ { 2 + \delta } } v _ { m } ( d s , d t ) . } } \end{array}
$$

对于 $J _ { 1 }$ ，利用微分中值定理，可得

$$
\begin{array} { r l r } {  { \mathbf { 1 } _ { \{ t \leqslant \alpha _ { n } \} } | \Phi ( x - s - t + \alpha _ { n } ) - \Phi ( x - s ) | } } \\ & { \leqslant } & { C | - t + \alpha _ { n } | \exp \{ - \frac { x ^ { 2 } } { 8 } \} + | - t + \alpha _ { n } | \mathbf { 1 } _ { \{ | s | \geqslant 1 + \frac { 1 } { 4 } | x | \} } + | - t + \alpha _ { n } | \mathbf { 1 } _ { \{ | t | \geqslant 1 + \frac { 1 } { 4 } | x | \} } . } \end{array}
$$

于是,我们有

$$
J _ { 1 } \leqslant J _ { 1 1 } + J _ { 1 2 } + J _ { 1 3 } ,
$$

其中

$$
\begin{array} { l } { \displaystyle { J _ { 1 1 } = C \int \int \big | - t + \alpha _ { n } \big | \exp \left\{ - \frac { x ^ { 2 } } { 8 } \right\} v _ { m } ( d s , d t ) , } } \\ { \displaystyle { J _ { 1 2 } = \int \int \big | - t + \alpha _ { n } \big | { \bf 1 } _ { \{ | s | \geqslant 1 + \frac { 1 } { 4 } | x | \} } v _ { m } ( d s , d t ) } } \end{array}
$$

和

$$
J _ { 1 3 } = \int \int | - t + \alpha _ { n } | \mathbf { 1 } _ { \{ | t | \geqslant 1 + { \frac { 1 } { 4 } } | x | \} } v _ { m } ( d s , d t ) .
$$

首先来看 $J _ { 1 1 }$ ，由引理3可得,对任意的 $\boldsymbol { x } \in \mathbb { R }$

$$
\begin{array} { r c l } { { { \cal J } _ { 1 1 } } } & { { \leqslant } } & { { C \exp \left\{ - \displaystyle \frac { x ^ { 2 } } { 8 } \right\} \left( \mathbb { E } | V _ { m } | + \alpha _ { n } \right) } } \\ { { } } & { { \leqslant } } & { { C \displaystyle \frac { 1 } { n ^ { \delta / 2 } } \displaystyle \frac { 1 } { 1 + | x | ^ { 2 + \delta } } . } } \end{array}
$$

对于 $J _ { 1 2 }$ ，令 $\tau , \iota > 1$ ，且满足 $\begin{array} { r } { \frac { 1 } { \tau } + \frac { 1 } { \iota } = 1 } \end{array}$ ．利用 Holder 不等式,我们有以下估计：对任意的 $\ b { x } \in \mathbb { R }$ ，

$$
\begin{array} { r c l } { { J _ { 1 2 } } } & { { \leqslant } } & { { \displaystyle \iint | t | \mathbf { 1 } _ { \left\{ | s | \geqslant 1 + \frac { 1 } { 4 } | x | \right\} } v _ { m } ( d s , d t ) + \alpha _ { n } \int \mathbf { 1 } _ { \left\{ | s | \geqslant 1 + \frac { 1 } { 4 } | x | \right\} } v _ { m } ( d s ) } }  \\ { { } } & { { \leqslant } } & { { \displaystyle \left( \int | t | ^ { \tau } v _ { m } ( d t ) \right) ^ { \frac { 1 } { \tau } } \left( \int \mathbf { 1 } _ { \left\{ | s | \geqslant 1 + \frac { 1 } { 4 } | x | \right\} } v _ { m } ( d s ) \right) ^ { \frac { 1 } { \tau } } + \frac { 1 } { \sqrt { n } } \mathbb { P } \left( | Y _ { m } | \geqslant 1 + \frac { 1 } { 4 } | x | \right) } } \\ { { } } & { { \leqslant } } & { { \displaystyle C \frac { 1 } { \sqrt { n } } \left[ \mathbb { P } \left( | Y _ { m } | \geqslant 1 + \frac { 1 } { 4 } | x | \right) \right] ^ { \frac { 1 } { \tau } } + \frac { 1 } { \sqrt { n } } \mathbb { P } \left( | Y _ { m } | \geqslant 1 + \frac { 1 } { 4 } | x | \right) . } } \end{array}
$$

由引理1知

$$
\begin{array} { r c l } { \mathbb { P } \bigg ( | Y _ { m } | \geqslant 1 + \displaystyle \frac 1 4 | x | \bigg ) } & { = } & { \mathbb { P } \bigg ( Y _ { m } \geqslant 1 + \displaystyle \frac 1 4 | x | \bigg ) + \mathbb { P } \bigg ( Y _ { m } \leqslant - 1 - \displaystyle \frac 1 4 | x | \bigg ) } \\ & { \leqslant } & { 1 - \Phi \left( ( 1 + \displaystyle \frac 1 4 | x | ) \displaystyle \frac { \sqrt n } { \sqrt m } \right) + \Phi \left( - ( 1 + \displaystyle \frac 1 4 | x | ) \displaystyle \frac { \sqrt n } { \sqrt m } \right) } \\ & & { + C \displaystyle \frac { 1 } { 1 + \big ( ( 1 + | x | / 4 ) \sqrt n / \sqrt m \big ) ^ { 2 + \delta } } \sum _ { i = 1 } ^ { m } \mathbb { E } \left| \displaystyle \frac { X _ { i } - \mu } { \sigma \sqrt m } \right| ^ { 2 + \delta } } \\ & { \leqslant } & { C \displaystyle \frac { 1 } { n ^ { ( 1 + \delta ) / 2 } } \displaystyle \frac { 1 } { 1 + | x | ^ { 2 + \delta } } . } \end{array}
$$

现在设 $\begin{array} { r } { \delta ^ { ' } = \frac { 3 + 2 \delta } { \iota } - \delta } \end{array}$ ，则有

$$
\delta ^ { ' } = 3 + \delta - { \frac { 3 + 2 \delta } { \tau } }
$$

将(4.30)代入(4.29),即有：对任意的 $| x | \leqslant \mu { \sqrt { n } } / \sigma$ .

$$
J _ { 1 2 } \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } .
$$

下面我们再看 $J _ { 1 3 }$ 取 $\begin{array} { r } { p = \frac { \delta ^ { ' } + \delta } { 2 } } \end{array}$ ，利用 Markov 不等式和引理3,我们可以得到,对任意的 $\begin{array} { r } { | x | \leqslant \frac { \sqrt { n } \mu } { \sigma } } \end{array}$

$$
\begin{array} { r c l } { { J _ { 1 3 } } } & { { \leqslant } } & { { \displaystyle \int | \iota | \mathbf 1 _ { \{ | \varepsilon | \geqslant 1 + \frac 1 4 | \varepsilon | \} } v _ { m } ( d t ) + \int \alpha _ { n } \mathbf 1 _ { \{ | \varepsilon | \geqslant 1 + \frac 1 4 | \varepsilon | \} } v _ { m } ( d t ) } } \\ { { } } & { { \leqslant } } & { { \displaystyle \int \frac { | \varepsilon | ^ { p } } { ( 1 + | x | / 4 ) ^ { p } } | \varepsilon | \ v _ { m } ( d t ) + \frac 1 { \sqrt n } \mathbb P \left( | V _ { m } | \geqslant 1 + \frac 1 4 | x | \right) } } \\ { { } } & { { \leqslant } } & { { \displaystyle \frac 1 { ( 1 + | x | / 4 ) ^ { p } } \mathbb E | V _ { m } | ^ { 1 + p } + \frac 1 { \sqrt n } \frac 1 { ( 1 + | x | / 4 ) ^ { 1 + p } } \mathbb E | V _ { m } | ^ { 1 + p } } } \\ { { } } & { { \leqslant } } & { { \displaystyle C \frac 1 { n ^ { \delta / 2 } } \frac 1 { 1 + | x | ^ { 1 + \delta ^ { \prime } } } . } } \end{array}
$$

综合 (4.27)-(4.33)，有

$$
J _ { 1 } \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } .
$$

值得注意的是,对任意 $\delta ^ { \prime \prime } \in ( 0 , \delta ^ { \prime } ]$ ，我们有

$$
J _ { 1 } \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime \prime } } } .
$$

然而，由 $\delta ^ { \prime }$ 的定义可得 $\delta ^ { ' } \in ( 0 , \delta )$ 的充要条件为 $\begin{array} { r } { \tau \in \left( \frac { 3 + 2 \delta } { 3 + \delta } , \frac { 3 + 2 \delta } { 3 } \right) } \end{array}$ 由（4.31)式， $\delta ^ { ' }$ 与 $\tau$ 呈单调递增关系，且当 $\begin{array} { r } { \tau = \frac { 3 + 2 \delta } { 3 } } \end{array}$ 时， $\delta ^ { ' }$ 达到最大值 $\delta$ ．由此可见，使(4.35）成立的最大的 $\delta ^ { ^ { \prime \prime } }$ 为 $\delta ^ { ' }$ ，否则 $\delta ^ { ^ { \prime \prime } }$ 将超过 $\delta$

现在来讨论 $J _ { 2 }$ 和 $J _ { 3 }$ 的上界估计.利用与(4.30)类似的推导过程，可得,对任意的 $\boldsymbol { x } \in \mathbb { R }$ ，

$$
\begin{array} { r c l } { { J _ { 2 } } } & { { = } } & { { C \displaystyle \frac { 1 } { n ^ { \delta / 2 } } \displaystyle \int \int \mathbf { 1 } _ { \{ t \leqslant \alpha _ { n } \} } \displaystyle \frac { 1 } { 1 + | x - s | ^ { 2 + \delta } } v _ { m } ( d s , d t ) } } \\ { { } } & { { \leqslant } } & { { C \displaystyle \frac { 1 } { n ^ { \delta / 2 } } \left( \displaystyle \int _ { | s | < 1 + | x | / 2 } \displaystyle \frac { 1 } { 1 + | x - s | ^ { 2 + \delta } } v _ { m } ( d s ) + \displaystyle \int _ { | s | \geqslant 1 + | x | / 2 } \displaystyle \frac { 1 } { 1 + | x - s | ^ { 2 + \delta } } v _ { m } ( d s ) \right) } } \end{array}
$$

$$
\begin{array} { r l } { \leqslant } & { { } C \displaystyle \frac { 1 } { n ^ { \delta / 2 } } \left[ \displaystyle \frac { 1 } { 1 + | x / 2 | ^ { 2 + \delta } } + \mathbb { P } \bigg ( | Y _ { m } | \geqslant 1 + \displaystyle \frac { 1 } { 2 } | x | \bigg ) \right] } \\ { \leqslant } & { { } C \displaystyle \frac { 1 } { n ^ { \delta / 2 } } \displaystyle \frac { 1 } { 1 + | x | ^ { 2 + \delta } } . } \end{array}
$$

对于 $J _ { 3 }$ ，利用与(4.30）和(4.33)类似的推导过程,可得，对任意的 $\begin{array} { r } { | x | \leqslant \frac { \sqrt { n } \mu } { \sigma } } \end{array}$

$$
\begin{array} { r c l } { { J _ { 3 } } } & { { = } } & { { C { \displaystyle \frac { 1 } { n ^ { \delta / 2 } } } \displaystyle \int \int \mathbf { 1 } _ { \{ t \leq \alpha _ { n } \} } \displaystyle \frac { 1 } { 1 + | x - s - t | ^ { 2 + \delta } } v _ { m } ( d s , d t ) } } \\ { { } } & { { \leqslant } } & { { C { \displaystyle \frac { 1 } { n ^ { \delta / 2 } } } \left( \displaystyle \int \int _ { | s + t | < 2 + | x | / 2 } { \displaystyle \frac { 1 } { 1 + | x / 2 | ^ { 2 + \delta } } } v _ { m } ( d s , d t ) + \displaystyle \int _ { | s | \geqslant 1 + | x | / 4 } v _ { m } ( d s ) + \displaystyle \int _ { | t | \geqslant 1 + | x | / 4 } v _ { m } ( d t ) \right) } } \\ { { } } & { { \leqslant } } & { { C { \displaystyle \frac { 1 } { n ^ { \delta / 2 } } } \left[ { \displaystyle \frac { 1 } { 1 + | x / 2 | ^ { 2 + \delta } } } + \mathbb { P } \left( | Y _ { m } | \geqslant 1 + { \displaystyle \frac { 1 } { 4 } } | x | \right) + \mathbb { P } \left( | V _ { m } | \geqslant 1 + { \displaystyle \frac { 1 } { 4 } } | x | \right) \right] } } \\ { { } } & { { \leqslant } } & { { C { \displaystyle \frac { 1 } { n ^ { \delta / 2 } } } { \displaystyle \frac { 1 } { 1 + | x | ^ { 2 + \delta } } } . } } \end{array}
$$

于是，将(4.34)，(4.36）和(4.37)代入(4.26)，可得

$$
\mathbb { P } \left( Y _ { n } + V _ { m } \leqslant x + \alpha _ { n } , Y _ { n } \geqslant x \right) \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } .
$$

最后，由(4.20),(4.21）和(4.38)，可得(4.18)对任意的 $\begin{array} { r } { | x | \leqslant \frac { \sqrt { n } \mu } { \sigma } } \end{array}$ 成立.

# 4.2 定理1的证明

由 (2.1),我们知道

$$
{ \frac { \log Z _ { n } - n \mu } { \sigma { \sqrt { n } } } } = { \frac { S _ { n } - n \mu } { \sigma { \sqrt { n } } } } + { \frac { \log W _ { n } } { \sigma { \sqrt { n } } } } .
$$

由引理1和条件 (A1),我们有

$$
\left| \mathbb { P } \left( \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| \leqslant C \sum _ { i = 1 } ^ { n } \mathbb { E } \left| \frac { X _ { i } - \mu } { \sigma \sqrt { n } } \right| ^ { 2 + \delta } \frac { 1 } { ( 1 + | x | ) ^ { 2 + \delta } } \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 2 + \delta } } .
$$

注意到

$$
\begin{array} { r l } & { \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) } \\ { = } & { \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x , \displaystyle \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) + \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x , \displaystyle \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } > x \right) } \\ { = } & { \mathbb { P } \left( \displaystyle \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) + \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x , \displaystyle \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } > x \right) - \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } > x , \displaystyle \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) . } \end{array}
$$

将引理5应用于最后一个等式，我们得到

$$
\left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \mathbb { P } \left( \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) \right| \leqslant C \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } .
$$

综合（4.39)和（4.40),有

$$
\left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| \leqslant \left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \mathbb { P } \left( \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) \right|
$$

$$
\begin{array} { r l } & { + \left| \mathbb { P } \left( \displaystyle \frac { S _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| } \\ { \leqslant } & { C \displaystyle \frac { 1 } { n ^ { \delta / 2 } } \frac { 1 } { 1 + | x | ^ { 1 + \delta ^ { \prime } } } . } \end{array}
$$

定理1得证.

# 4.3 定理2的准备引理

利用与引理3类似的证明，我们有下面的引理，

引理6假设条件(A3)和(A4)成立．则存在正数 $a _ { 0 }$ 使得下面两个不等式成立

$$
\mathbb { E } W ^ { - a _ { 0 } } < \infty
$$

和

$$
\operatorname* { s u p } _ { n \in \mathbb { N } } \mathbb { E } W _ { n } ^ { - a _ { 0 } } < \infty .
$$

证明 由于

$$
W ^ { - a _ { 0 } } = \frac { 1 } { \Gamma \left( a _ { 0 } \right) } \int _ { 0 } ^ { \infty } e ^ { - t W } t ^ { a _ { 0 } - 1 } d t ,
$$

则

$$
\begin{array} { l c l } { { \mathbb { E } W ^ { - a _ { 0 } } } } & { { = } } & { { \displaystyle \frac { 1 } { \Gamma \left( a _ { 0 } \right) } \int _ { 0 } ^ { \infty } \phi ( t ) t ^ { a _ { 0 } - 1 } d t } } \\ { { } } & { { = } } & { { \displaystyle \frac { 1 } { \Gamma \left( a _ { 0 } \right) } \left( \int _ { 0 } ^ { 1 } \phi ( t ) t ^ { a _ { 0 } - 1 } d t + \int _ { 1 } ^ { \infty } \phi ( t ) t ^ { a _ { 0 } - 1 } d t \right) , } } \end{array}
$$

其中 $\Gamma$ 是伽马函数．对于上式括号中的第一项,由于 $0 \leqslant \phi ( t ) \leqslant 1 \ ( t > 0 )$ ，则对任意的 $a _ { 0 } > 0$ ，有

$$
\int _ { 0 } ^ { 1 } \phi ( t ) t ^ { a _ { 0 } - 1 } d t \leqslant C \int _ { 0 } ^ { 1 } t ^ { a _ { 0 } - 1 } d t < \infty .
$$

对于第二项,我们首先需要证明存在正数 $a _ { 1 }$ ，使得对任意的 $t > 0$ 有

$$
\phi ( t ) \leqslant { \frac { C } { 1 + t ^ { a _ { 1 } } } } .
$$

接下来,我们借鉴Grama et al.[15]的方法．引入引理2 证明中的取值为正的随机变量 $\tilde { Y } _ { n , K }$ ．根据(4.5),我们有：对所有的 $t > 0$

$$
\phi ( t ) \leqslant q _ { n , K } \mathbb { E } \phi ( \tilde { Y } _ { n , K } t ) + \mathbb { P } \Big ( \frac { t } { \Pi _ { n } } < t _ { K } \Big ) .
$$

设 $p \in ( 1 , 2 ]$ ，由(4.3),有

$$
\begin{array} { r c l } { \displaystyle q _ { n , K } \mathbb { E } \tilde { Y } _ { n , K } ^ { - a } } & { = } & { \displaystyle \mathbb { E } \left[ \Pi _ { n } ^ { a } \prod _ { j = 0 } ^ { n - 1 } \left( p _ { 1 } ( \xi _ { j } ) + ( 1 - p _ { 1 } ( \xi _ { j } ) ) \beta _ { K } \right) \right] + \frac { 1 } { K } \mathbb { E } \Pi _ { n } ^ { a } } \\ & & { \displaystyle + \frac { 1 } { K } \mathbb { E } \left[ \Pi _ { n } ^ { a } ( \xi ) \sum _ { k = 0 } ^ { \infty } \frac { \Pi _ { k + 1 } ^ { a } ( T ^ { n } \xi ) } { \Pi _ { k } ^ { p - 1 } ( T ^ { n } \xi ) } \left( \frac { m _ { k } ^ { ( p ) } ( T ^ { n } \xi ) } { m _ { k } ^ { p } ( T ^ { n } \xi ) } \right) \right] . } \end{array}
$$

由于在 $\mathbb { P }$ 下,对任意的 $k \geqslant 0$ $\Pi _ { n } ( \xi )$ 独立于 $\Pi _ { k + 1 } ( T ^ { n } \xi )$ 和 $\Pi _ { k } ( T ^ { n } \xi )$ ，那么

$$
\begin{array} { r l } { q _ { \mathrm { e } , \kappa } W _ { \kappa , \kappa } ^ { ( - 2 ) } } & { = \ : | \kappa | \displaystyle [ 1 \Theta _ { \kappa } ^ { \kappa , 1 } \displaystyle \frac { \kappa } { \int _ { - \infty } ^ { \infty } } ( 1 + \gamma _ { \kappa } ( \xi _ { \kappa } ) \xi _ { \kappa } ) ^ { 2 } \kappa _ { \kappa } ] } \\ & { \quad + \displaystyle \frac { 1 } { \kappa } \displaystyle \frac { 2 \kappa \eta _ { \kappa } ^ { \kappa } } { 2 \kappa } [ 1 + \displaystyle \sum _ { k = 1 } ^ { \infty } \frac { 1 \tilde { \kappa } _ { k \kappa } ^ { \kappa } ( \frac { 2 \kappa \eta _ { \kappa } ^ { \kappa } } { \sqrt { \kappa ( \xi _ { \kappa } - \zeta ) } } \xi ) ( \frac { \kappa \eta _ { \kappa } ^ { \kappa } ( \xi ) } { \sqrt { \kappa ( \xi _ { \kappa } - \zeta ) } \zeta } ) ] } { \kappa ^ { 2 } } } \\ & { = \ : \ : \frac { \kappa } { \kappa ^ { - 1 } } \displaystyle \frac { \kappa } { ( \kappa \eta _ { \kappa } ^ { \kappa } ( \xi _ { \kappa } ) ( \xi _ { \kappa } ) + ( 1 - \kappa \eta _ { \kappa } \xi _ { \kappa } ) ( \xi _ { \kappa } ) ) \beta \kappa _ { k } ^ { \kappa } } } \\ &  \quad + \ : \frac { 1 } { \kappa } \displaystyle \frac { \kappa \ln ( \kappa ) } { \kappa } [ 1 + \displaystyle \sum _ { k = 1 } ^ { \infty } \frac { 1 \kappa ^ { \kappa } + ( \frac { 2 \kappa \eta _ { \kappa } \xi _ { \kappa } } { \sqrt { \kappa ( \xi _ { \kappa } - \zeta ) } \zeta } ) ( \frac { \kappa \eta _ { \kappa } ^ { \kappa } ( \xi _ { \kappa } ^ { \kappa } \zeta ) } { \sqrt { \kappa _ { \kappa } ^ { \kappa } ( \frac { 2 \kappa \eta _ { \kappa } \zeta } { \sqrt { \kappa ( \xi _ { \kappa } - \zeta ) } \zeta } ) } ) } { \kappa ^ { 2 } } ] } \\ & { = \ :  \kappa [ \phi _ { \kappa } ^ { \kappa } ( \eta _ { \kappa } ^ { \kappa } ( 1 + ) - ( 1 - \rho _ { \kappa } ) ) \kappa _ { k } ]  } \\ &  \quad + \ : \frac { ( \lambda \zeta \kappa ) ^ { \kappa } } { \kappa } [ 1 - \displaystyle \frac { 1 }  \kappa - \kappa n _ { \kappa } ^ { \kappa } ( \frac { 2 \kappa \eta _ { \kappa } ^ { \kappa } } { \sqrt { \kappa ( \xi _ { \kappa } - \zeta ) } \zeta } ) ^ { \kappa } ( \frac  \kappa \eta _ { \kappa } ^ { \kappa } \eta _ { \kappa } ^  \kappa  \end{array}
$$

因此，利用控制收敛定理和 (4.47)，可得

$$
q _ { n , K } \mathbb { E } \tilde { Y } _ { n , K } ^ { - a } \xrightarrow { a \downarrow 0 } q _ { n , K } \overset { n \to \infty } { \longrightarrow } \frac { 1 } { K } \left( 1 + C \right) \overset { K \to \infty } { \longrightarrow } 0 .
$$

那么，我们可以取 $n _ { 0 } , K _ { 0 }$ 以及充分小的 $a _ { 1 } \in ( 0 , \lambda _ { 0 } )$ 使得 $q _ { n _ { 0 } , K _ { 0 } } \mathbb { E } \tilde { Y } _ { n _ { 0 } , K _ { 0 } } ^ { - a _ { 1 } } < 1$ ，再由(4.46）与 Markov不等式可得

$$
\begin{array} { r c l } { \phi ( t ) } & { \leqslant } & { q _ { n _ { 0 } , K _ { 0 } } \mathbb { E } \phi ( \tilde { Y } _ { n _ { 0 } , K _ { 0 } } t ) + \mathbb { P } \Big ( \displaystyle \frac { t } { \Pi _ { n _ { 0 } } } < t _ { K _ { 0 } } \Big ) } \\ & { \leqslant } & { q _ { n _ { 0 } , K _ { 0 } } \mathbb { E } \phi ( \tilde { Y } _ { n _ { 0 } , K _ { 0 } } t ) + \displaystyle \frac { C _ { n _ { 0 } , K _ { 0 } } } { t ^ { a _ { 1 } } } . } \end{array}
$$

注意到 $0 \leqslant \phi ( t ) \leqslant 1 \ ( t > 0 )$ ．最后，由（4.48)以及[17]中的引理4.1可得：对任意的 $t > 0$

$$
\phi ( t ) \leqslant { \frac { C } { 1 + t ^ { a _ { 1 } } } } .
$$

则(4.45)得证．下面我们取 $0 < a _ { 0 } < a _ { 1 }$ ，有

$$
\int _ { 1 } ^ { \infty } \phi ( t ) t ^ { a _ { 0 } - 1 } d t \leqslant C \int _ { 1 } ^ { \infty } t ^ { a _ { 0 } - a _ { 1 } - 1 } d t < \infty .
$$

由（4.43),(4.44)和(4.49）可得(4.41)成立.

下面证明 (4.42)．由于函数 $x \mapsto x ^ { - a _ { 0 } } \ ( a _ { 0 } > 0 , \ x > 0 )$ 是非负凸函数．则根据[7]中的引理2.1,我们有

$$
\operatorname* { s u p } _ { n \in \mathbb { N } } \mathbb { E } W _ { n } ^ { - a _ { 0 } } = \mathbb { E } W ^ { - a _ { 0 } } < \infty .
$$

引理6得证.

下一个引理表明Cramér条件（A3)和Bernstein条件 $( \mathbf { A 3 ^ { \prime } } )$ 是等价的

引理7条件(A3)与下面的条件 $( \mathbf { A 3 ^ { \prime } } )$ 等价.

(A3'）存在一个常数 $H > 0$ ，使得对于任意的 $k \geqslant 2$ ，

$$
\mathbb { E } ( X - \mu ) ^ { k } \leqslant { \frac { 1 } { 2 } } k ! H ^ { k - 2 } \mathbb { E } ( X - \mu ) ^ { 2 } .
$$

证明 首先证明充分性.假设 $( \mathbf { A 3 ^ { \prime } } )$ 成立,利用泰勒展开式，有

$$
\mathbb { E } e ^ { \lambda _ { 0 } ( X - \mu ) } = \mathbb { E } \left( 1 + \sum _ { k = 1 } ^ { \infty } \frac { ( \lambda _ { 0 } ( X - \mu ) ) ^ { k } } { k ! } \right) = 1 + \sum _ { k = 2 } ^ { \infty } \mathbb { E } \frac { ( \lambda _ { 0 } ( X - \mu ) ) ^ { k } } { k ! } \leqslant 1 + \sum _ { k = 2 } ^ { \infty } \frac { 1 } { 2 } \sigma ^ { 2 } \lambda _ { 0 } ^ { k } H ^ { k - 2 } .
$$

令 $\begin{array} { r } { \lambda _ { 0 } = \frac { 1 } { 2 H } } \end{array}$ ，由 (4.51)，我们得到

$$
\mathbb { E } e ^ { \lambda _ { 0 } X } \leqslant e ^ { \lambda _ { 0 } \mu } \left( 1 + \frac { \sigma ^ { 2 } } { 4 H ^ { 2 } } \right) .
$$

这就证得了(A3)成立.

下面证明必要性．假设（A3）成立，即 $\mathbb { E } e ^ { \lambda _ { 0 } ( X - \mu ) } = : c _ { 0 } < \infty$ 由不等式 $x ^ { k } \leqslant k ! e ^ { x }$ ，可得对任意的$k \geqslant 3$ ，

$$
\begin{array} { r c l } { \mathbb { E } ( X - \mu ) ^ { k } } & { = } & { \lambda _ { 0 } ^ { - k } \mathbb { E } [ \lambda _ { 0 } ( X - \mu ) ] ^ { k } \leqslant k ! \lambda _ { 0 } ^ { - k } \mathbb { E } e ^ { \lambda _ { 0 } ( X - \mu ) } } \\ & { = } & { \displaystyle \frac { 1 } { 2 } k ! \lambda _ { 0 } ^ { - k + 3 } \frac { 2 \lambda _ { 0 } ^ { - 3 } c _ { 0 } } { \sigma ^ { 2 } } \mathbb { E } ( X - \mu ) ^ { 2 } } \\ & { \leqslant } & { \displaystyle \frac { 1 } { 2 } k ! H ^ { k - 2 } \mathbb { E } ( X - \mu ) ^ { 2 } , } \end{array}
$$

其中 $H = \operatorname* { m a x } \{ \lambda _ { 0 } ^ { - 1 } , \frac { 2 \lambda _ { 0 } ^ { - 3 } c _ { 0 } } { \sigma ^ { 2 } } \}$ 当 $k = 2$ 时,(4.50）显然成立．必要性得证.

下述引理给出了两个关于 $\log Z _ { n }$ 的Bernstein型不等式.

引理8 假设条件(A3)和(A4)成立.则对任意的 $x \geqslant 0$ ，以下不等式成立

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x \right) \leqslant 2 \exp \left\{ - \frac { x ^ { 2 } } { 2 \left( 1 + c x / \sqrt { n } \right) } \right\}
$$

和

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant - x \right) \leqslant C \exp \left\{ - \frac { x ^ { 2 } } { 2 \left( 1 + c x / \sqrt { n } \right) } \right\} ,
$$

其中 $C$ 是大于1的常数.

证明由于Cramér 条件（A3)和Bernstein条件 $( \mathbf { A 3 ^ { \prime } } )$ 是等价的,我们只需要在条件 $( \mathbf { A 3 ^ { \prime } } )$ 和(A4）下证明引理8即可.当 $x = 0$ 时，这两个不等式显然成立．因此，我们只需考虑 $x > 0$ 的情况.首先给出（4.52）的证明．记

$$
\eta _ { n , i } = { \frac { X _ { i } - \mu } { \sigma { \sqrt { n } } } } , i = 1 , \ldots , n .
$$

显然有

$$
{ \frac { \log Z _ { n } - n \mu } { \sigma { \sqrt { n } } } } = \sum _ { i = 1 } ^ { n } \eta _ { n , i } + { \frac { \log W _ { n } } { \sigma { \sqrt { n } } } } ,
$$

其中 $\sum _ { i = 1 } ^ { n } \eta _ { n , i }$ 是一列独立同分布的随机变量之和.那么对于任意的 $x > 0$ ，我们有

$$
\begin{array} { l c l } { \displaystyle \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \geqslant x \right) } & { = } & { \displaystyle \mathbb { P } \left( \sum _ { i = 1 } ^ { n } \eta _ { n , i } + \frac { \log W _ { n } } { \sigma \sqrt { n } } \geqslant x \right) } \\ & { \leqslant } & { I _ { 1 } + I _ { 2 } , } \end{array}
$$

其中

$$
I _ { 1 } = \mathbb { P } \left( \sum _ { i = 1 } ^ { n } \eta _ { n , i } \geqslant x - { \frac { x ^ { 2 } } { \sigma { \sqrt { n } } } } \right)
$$

$$
I _ { 2 } = \mathbb { P } \left( { \frac { \log W _ { n } } { \sigma { \sqrt { n } } } } \geqslant { \frac { x ^ { 2 } } { \sigma { \sqrt { n } } } } \right) .
$$

将Bernstein不等式应用于 $I _ { 1 }$ ，对任意的 $\textstyle x \in { \biggl ( } 0 , { \frac { \sigma { \sqrt { n } } } { 2 } } { \biggr ) }$ 我们有

$$
I _ { 1 } \leqslant \exp \left\{ - \frac { x ^ { 2 } \left( 1 - \frac { x } { \sigma \sqrt { n } } \right) ^ { 2 } } { 2 \left( 1 + \frac { H } { \sigma \sqrt { n } } x \left( 1 - \frac { x } { \sigma \sqrt { n } } \right) \right) } \right\} \leqslant \exp \left\{ - \frac { x ^ { 2 } } { 2 \left( 1 + c x / \sqrt { n } \right) } \right\} .
$$

利用 Markov 不等式以及 $\mathbb { E } W _ { n } = 1$ ，对任意的 $\textstyle x \in \left( 0 , { \frac { \sigma { \sqrt { n } } } { 2 } } \right)$ ，可得

$$
I _ { 2 } = \mathbb { P } \left( W _ { n } \geqslant \exp \left\{ x ^ { 2 } \right\} \right) \leqslant \exp \left\{ - x ^ { 2 } \right\} \mathbb { E } W _ { n } = \exp \left\{ - x ^ { 2 } \right\} .
$$

结合 (4.54)-(4.56)，对任意的 $\textstyle x \in { \bigg ( } 0 , { \frac { \sigma { \sqrt { n } } } { 2 } } { \bigg ) }$ ,可得 (4.52).当 $\begin{array} { r } { x \geqslant \frac { \sigma \sqrt { n } } { 2 } } \end{array}$ 时,有

$$
\mathbb { P } \left( { \frac { \log Z _ { n } - n \mu } { \sigma { \sqrt { n } } } } \geqslant x \right) \leqslant I _ { 3 } + I _ { 4 } ,
$$

其中

$$
I _ { 3 } = \mathbb { P } \left( \sum _ { i = 1 } ^ { n } \eta _ { n , i } \geqslant \frac { x } { 2 } \right) \quad \sharp \mathbb { I } _ { \mathbf { \omega } } I _ { 4 } = \mathbb { P } \left( \frac { \log W _ { n } } { \sigma \sqrt { n } } \geqslant \frac { x } { 2 } \right) .
$$

运用与I和I类似的证明方法,对任意的x≥ 以及足够大的 $\mid c \mid$ ，我们有

$$
I _ { 3 } \leqslant \exp \left\{ - { \frac { ( x / 2 ) ^ { 2 } } { 2 \left( 1 + { \frac { H } { \sigma { \sqrt { n } } } } { \frac { x } { 2 } } \right) } } \right\} \leqslant \exp \left\{ - { \frac { x ^ { 2 } } { 2 \left( 1 + c x / { \sqrt { n } } \right) } } \right\}
$$

和

$$
I _ { 4 } \leqslant \exp \left\{ - \frac { x \sigma \sqrt { n } } { 2 } \right\} \mathbb { E } W _ { n } \leqslant \exp \left\{ - \frac { x ^ { 2 } } { 2 \left( 1 + c x / \sqrt { n } \right) } \right\} .
$$

综合(4.57)-(4.60)，可得对任意的 $\begin{array} { r } { x \geqslant \frac { \sigma \sqrt { n } } { 2 } } \end{array}$ ，(4.52）成立.

下面证明(4.53)．设 $a _ { 0 }$ 是一个由引理6给出的正数．那么，对任意的 $ { \boldsymbol { { x } } } > 0$ ，有

$$
\begin{array} { l c l } { \displaystyle \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant - x \right) } & { = } & { \displaystyle \mathbb { P } \left( - \sum _ { i = 1 } ^ { n } \eta _ { n , i } - \frac { \log W _ { n } } { \sigma \sqrt { n } } \geqslant x \right) } \\ & { \leqslant } & { I _ { 5 } + I _ { 6 } , } \end{array}
$$

其中

$$
I _ { 5 } = \mathbb { P } \left( - \sum _ { i = 1 } ^ { n } \eta _ { n , i } \geqslant x - \frac { x ^ { 2 } } { a _ { 0 } \sigma \sqrt { n } } \right) \sharp [ ] I _ { 6 } = \mathbb { P } \left( - \frac { \log W _ { n } } { \sigma \sqrt { n } } \geqslant \frac { x ^ { 2 } } { a _ { 0 } \sigma \sqrt { n } } \right) .
$$

然后,我们给出 $I _ { 5 }$ 和 $I _ { 6 }$ 的上界.利用 Bernstein 不等式，对任意的 $\textstyle x \in \left( 0 , { \frac { a _ { 0 } \sigma { \sqrt { n } } } { 2 } } \right)$ ，有

$$
I _ { 5 } \leqslant \exp \left\{ - \frac { x ^ { 2 } \left( 1 - \frac { x } { a _ { 0 } \sigma \sqrt { n } } \right) ^ { 2 } } { 2 \left( 1 + \frac { H } { \sigma \sqrt { n } } x \left( 1 - \frac { x } { a _ { 0 } \sigma \sqrt { n } } \right) \right) } \right\} \leqslant \exp \left\{ - \frac { x ^ { 2 } } { 2 \left( 1 + c x / \sqrt { n } \right) } \right\} .
$$

并且由 Markov 不等式和引理6,对任意的 $\textstyle x \in \left( 0 , { \frac { a _ { 0 } \sigma { \sqrt { n } } } { 2 } } \right)$ 我们有

$$
I _ { 6 } = \mathbb { P } \left( \log W _ { n } \leqslant - \frac { x ^ { 2 } } { a _ { 0 } } \right) = \mathbb { P } \left( W _ { n } ^ { - a _ { 0 } } \geqslant \exp \left\{ x ^ { 2 } \right\} \right) \leqslant \exp \{ - x ^ { 2 } \} \mathbb { E } W _ { n } ^ { - a _ { 0 } } < \infty .
$$

综合 (4.61)-(4.63)，对任意的 $\begin{array} { r } { x \in { \bigg ( } 0 , \frac { a _ { 0 } \sigma \sqrt { n } } { 2 } { \bigg ) } } \end{array}$ ，有（4.53）成立.当 $\textstyle \left| x \geqslant { \frac { a _ { 0 } \sigma { \sqrt { n } } } { 2 } } \right|$ 时,有

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant - x \right) \leqslant I _ { 7 } + I _ { 8 } ,
$$

其中

$$
I _ { 7 } = \mathbb { P } \left( - \sum _ { i = 1 } ^ { n } \eta _ { n , i } \geqslant \frac { x } { 2 } \right) \sharp \mathbb { I } _ { \mathbf { \delta } } I _ { 8 } = \mathbb { P } \left( - \frac { \log W _ { n } } { \sigma \sqrt { n } } \geqslant \frac { x } { 2 } \right) .
$$

再次利用 Bernstein 不等式,对任意的 $\textstyle \left| x \geqslant { \frac { a _ { 0 } \sigma { \sqrt { n } } } { 2 } } \right|$ ，可得

$$
I _ { 7 } \leqslant \exp \left\{ - \frac { ( x / 2 ) ^ { 2 } } { 2 \left( 1 + \frac { H } { \sigma \sqrt { n } } \frac { x } { 2 } \right) } \right\} \leqslant \exp \left\{ - \frac { x ^ { 2 } } { 2 \left( 1 + c x / \sqrt { n } \right) } \right\} .
$$

利用与 $I _ { 6 }$ 类似的证明方法,对任意的 $\textstyle \left| x \geqslant { \frac { a _ { 0 } \sigma { \sqrt { n } } } { 2 } } \right|$ ，我们有

$$
I _ { 8 } = \mathbb { P } \left( \log W _ { n } \leqslant - { \frac { \sigma { \sqrt { n } } x } { 2 } } \right) \leqslant \exp \left\{ - { \frac { a _ { 0 } \sigma { \sqrt { n } } x } { 2 } } \right\} \mathbb { E } W _ { n } ^ { - a _ { 0 } } \leqslant C \exp \left\{ - { \frac { x ^ { 2 } } { 2 \left( 1 + c x / { \sqrt { n } } \right) } } \right\} .
$$

引理得证.

下述引理是Grama etal.[9]中定理1.3推导出的直接结果

引理9假设（A3)和（A4)成立．则对任意的 $x \in \left[ 0 , n ^ { 1 / 4 } \right]$ ，以下不等式成立

$$
\left| \log { \frac { \mathbb { P } \left( { \frac { \log Z _ { n } - n \mu } { \sigma { \sqrt { n } } } } > x \right) } { 1 - \Phi ( x ) } } \right| \leqslant C { \frac { 1 + x ^ { 3 } } { \sqrt { n } } }
$$

和

$$
\left| \log \frac { \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant - x \right) } { \Phi ( - x ) } \right| \leqslant C \frac { 1 + x ^ { 3 } } { \sqrt { n } } .
$$

# 4.4 定理2的证明

当 $x \in \left[ 0 , n ^ { 1 / 4 } \right]$ 时，由引理9 的第一个不等式,我们有

$$
\begin{array} { r c l } { \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) } & { = } & { \displaystyle - \left[ \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } > x \right) - ( 1 - \Phi ( x ) ) \right] } \\ & { \geqslant } & { \displaystyle - \left[ ( 1 - \Phi ( x ) ) \exp \left\{ C \displaystyle \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} - ( 1 - \Phi ( x ) ) \right] } \\ & { = } & { \displaystyle - ( 1 - \Phi ( x ) ) \left( \exp \left\{ C \displaystyle \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} - 1 \right) . } \end{array}
$$

利用不等式 $e ^ { x } - 1 \leqslant x e ^ { x } , x \geqslant 0$ ，我们有

$$
\exp \left\{ C \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} - 1 \leqslant C \frac { 1 + x ^ { 3 } } { \sqrt { n } } \exp \left\{ C \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} .
$$

由不等式

$$
{ \frac { e ^ { - x ^ { 2 } / 2 } } { \sqrt { 2 \pi } ( 1 + x ) } } \leqslant 1 - \Phi ( x ) \leqslant { \frac { e ^ { - x ^ { 2 } / 2 } } { \sqrt { \pi } ( 1 + x ) } } , \quad \forall x \geqslant 0
$$

以及(4.65)和(4.66)，可得

$$
\begin{array} { r c l } { \displaystyle \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) } & { \geqslant } & { \displaystyle - \frac { C ( x ^ { 2 } + 1 - x ) } { \sqrt { 2 \pi n } } \exp \left\{ - \frac { x ^ { 2 } } { 2 } + C \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} } \\ & { \geqslant } & { \displaystyle - C \frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) \exp \left\{ - \frac { x ^ { 2 } } { 2 } + C \frac { x ^ { 3 } } { \sqrt { n } } \right\} . } \end{array}
$$

由于 $x \in \left[ 0 , n ^ { 1 / 4 } \right]$ ，我们有

$$
1 - C { \frac { x } { \sqrt { n } } } = { \frac { 1 } { 1 + \displaystyle \sum _ { k = 1 } ^ { \infty } ( C x / { \sqrt { n } } ) ^ { k } } } = { \frac { 1 } { 1 + C x / { \sqrt { n } } ( { \frac { 1 } { 1 - C x / { \sqrt { n } } } } ) } } \geqslant { \frac { 1 } { 1 + C x / { \sqrt { n } } } } .
$$

所以

$$
\exp \left\{ - { \frac { x ^ { 2 } } { 2 } } + C { \frac { x ^ { 3 } } { \sqrt { n } } } \right\} = \exp \left\{ - { \frac { x ^ { 2 } } { 2 } } \left( 1 - C { \frac { x } { \sqrt { n } } } \right) \right\} \leqslant \exp \left\{ - { \frac { x ^ { 2 } } { 2 ( 1 + C x / { \sqrt { n } } ) } } \right\} .
$$

将（4.69）应用于（4.68)，对任意 $x \in \left[ 0 , n ^ { 1 / 4 } \right]$ ，有

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \geqslant - C \frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) \exp \left\{ - \frac { x ^ { 2 } } { 2 ( 1 + c x / \sqrt { n } ) } \right\} .
$$

下面我们给出 $\begin{array} { r } { \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) } \end{array}$ 的上界．再次使用引理9的第一个不等式，有

$$
\begin{array} { r c l } { \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) } & { = } & { \displaystyle - \left[ \mathbb { P } \left( \displaystyle \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } > x \right) - ( 1 - \Phi ( x ) ) \right] } \\ & { \leqslant } & { \displaystyle - \left[ ( 1 - \Phi ( x ) ) \exp \left\{ - C \displaystyle \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} - ( 1 - \Phi ( x ) ) \right] } \\ & { = } & { \displaystyle - ( 1 - \Phi ( x ) ) \left( \exp \left\{ - C \displaystyle \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} - 1 \right) . } \end{array}
$$

由不等式 $e ^ { x } - 1 \geqslant x , x \leqslant 0 .$ ，可得

$$
\exp \left\{ - C \frac { 1 + x ^ { 3 } } { \sqrt { n } } \right\} - 1 \geqslant - C \frac { 1 + x ^ { 3 } } { \sqrt { n } } .
$$

将（4.67)和(4.72）应用于(4.71),有

$$
\begin{array} { r c l } { \displaystyle \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) } & { \leqslant } & { \displaystyle \frac { C ( 1 + x ^ { 2 } - x ) } { \sqrt { \pi n } } \exp \left\{ - \frac { x ^ { 2 } } { 2 } \right\} } \\ & { \leqslant } & { \displaystyle C \frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) \exp \left\{ - \frac { x ^ { 2 } } { 2 ( 1 + c x / \sqrt { n } ) } \right\} . } \end{array}
$$

综合(4.70）和（4.73),对任意的 $x \in [ 0 , n ^ { 1 / 4 } ]$ ,我们得到

$$
\left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| \leqslant C \frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) \exp \left\{ - \frac { x ^ { 2 } } { 2 ( 1 + c x / \sqrt { n } ) } \right\} .
$$

当 $x > n ^ { 1 / 4 }$ 时,我们有

$$
\begin{array} { r l } { \left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| } & { = \left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } > x \right) - \left( 1 - \Phi ( x ) \right) \right| } \\ & { \quad \leqslant \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } > x \right) + 1 - \Phi ( x ) . } \end{array}
$$

由引理8的第一个不等式以及引理7,对任意的 $x > n ^ { 1 / 4 }$ ，有

$$
\mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } > x \right) \leqslant C \exp \left\{ - \frac { x ^ { 2 } } { 2 ( 1 + c x / \sqrt { n } ) } \right\} .
$$

注意到

$$
1 - \Phi ( x ) \leqslant { \frac { e ^ { - x ^ { 2 } / 2 } } { \sqrt { \pi } ( 1 + x ) } } \leqslant { \frac { 1 } { 1 + x } } \exp \left\{ - { \frac { x ^ { 2 } } { 2 ( 1 + c x / { \sqrt { n } } ) } } \right\} .
$$

并且对任意的 $x > n ^ { 1 / 4 }$ ，有

$$
\frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) \geqslant 1 \quad \notin \mathbb { H } \quad \frac { 1 } { 1 + x } \leqslant \frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) .
$$

综合（4.67)）以及(4.74)-(4.77),我们有

$$
\left| \mathbb { P } \left( \frac { \log Z _ { n } - n \mu } { \sigma \sqrt { n } } \leqslant x \right) - \Phi ( x ) \right| \leqslant C \frac { 1 } { \sqrt { n } } ( 1 + x ^ { 2 } ) \exp \left\{ - \frac { x ^ { 2 } } { 2 ( 1 + c x / \sqrt { n } ) } \right\} .
$$

对于 $x < 0$ 的情况，可以用类似的方法证明，只是将（4.67）替换为

$$
\frac { e ^ { - x ^ { 2 } / 2 } } { \sqrt { 2 \pi } ( 1 + | x | ) } \leqslant \Phi ( x ) \leqslant \frac { e ^ { - x ^ { 2 } / 2 } } { \sqrt { \pi } ( 1 + | x | ) } , ~ x \leqslant 0 ,
$$

而且将引理8以及引理9中的第二个不等式分别运用于 $x \in \left[ - n ^ { 1 / 4 } , 0 \right]$ 和 $x \in \left( - \infty , - n ^ { 1 / 4 } \right)$ 两个情况下的证明. □

# 参考文献

1Smith,W.L.and Wilkinson,W.E.(1969).On branching processes in random environments.Ann.Math. Stat. 40(3),814-827.   
2Boinghof,C.(2014).Limit theorems forstronglyand intermediately supercriticalbranching processs inrandom environment with linear fractional ofspring distributions.Stochastic Process.Appl.124(11),3553-3577.   
3Li,Y.,Liu,Q.,Gao,Z.Q.and Wang,H. (2014).Asymptotic propertiesofsupercritical branching procesesinrandom environments.Front.Math.China 9,737-751   
4Wang,Y.and Liu,Q.(2O17).Limit theorems forasupercritical branching processwith immigration inarandom environment．Sci. China Math.60(12),2481-2502.   
5Fan,X.,Hu,H.andLiu,Q.(2020).Uniform Cramer moderatedeviationsand Berry-Esseebounds forasupercritical branching process in a random environment.Front. Math.China 15(5),891-914.   
6Boinghof, Cand Kersting,C.(2010).Upper large deviations of branching process in a random environment for offspring distributions with geometrically bounded tails. Stochastic Process.Appl.120(10),2064-2077.   
7Huang,C.and Liu,Q.(20l2).Moments,moderateand large deviations fora branching processin arandom environment. Stochastic Process．Appl.(122)(2),522-545.   
8Xu,H. (2021).Deviation inequalitiesforasupercritical branching processinarandomenvironment.J.Math.Research Appl.,to appear.arXiv:2109.03489. 9Grama,I.,Liu,Q.and Miqueu,E.(20l7).Bery-Essenboundand Cramérlarge deviationexpansionforasupercritical branching process in a random environment. Stochastic Process. Appl. 127(4),1255-1281.   
10Gao,Z.Q.(2021).Exact convergencerate inthecentrallimit theoremforabranching processinarandomenvironment. Stat.Probab.Letters 178:109194.   
11Bikelis,A.(1966).Onestimatesof theremainder term in thecentrallimit theorem.Lith.Math.J.6(3),323-346.   
12Chen,L.H.Y.and Shao,Q.M.(20o1).Anon-uniform Berry-Essenbound via Stein's method.Probab.Theory Relat. Fields 120(2): 236-254.   
13Tanny,D. (1988).Anecessaryandsuffcient condition fora branching processinarandom environment togrow like the product of its means.Stochastic Process.Appl.28(1),123-139.   
14Fan,X.,Grama,I.andLiu.Q.(2017).Nonuniform Berr-Eseenboundsformartingales withapplications tostatistical estimation. Statistics 51(1),105-122.   
15Grama,I,Liu,Q.and Miqueu,E.(2021).Asymptoticof thedistribution and harmonic momentsforasupercritical branching process in a random environment. (hal-03416307).   
16Fan,X.,Grama,I.and Liu,Q.(2O17).Deviation inequalities for martingales with applications $J$ .Math.Anal.Appl. 448(1), 538-566.   
17Liu,Q.(199).Asymptotic properties ofsupercriticalage-dependent branching processes and homogeneous branching random walks. Stochastic Process.Appl.82(1),61-87.   
18Liu,Q.(20ol).Local dimensions of the branching measure on a Galton-Watson tree.Ann.Inst.Henri Poincaré Probab.Stat.37(2),195-222.

# Nonuniform Berry-Esseen bounds for a supercritical branching process in a random environment

Xiequan Fan & Hao Wu & Yinna Ye

Abstract Let ( $\left( Z _ { n } \right)$ ）be a supercritical branching process in an independent and identically distributed rando environment.We establish nonuniform Berry-Esseen bounds for the process ( $Z _ { n }$ ),which refine the Berry-Esse( bound of Grama et al. [Stochastic Process.Appl.,127(4),1255-1281,2017].We also discuss an application our result to constructing confidence interval for the criticality parameter.

KeywordsBranching processes,Random environment,Nonuniform Berry-Esseen bounds   
MSC(2010) 60J80,60K37,60F05,62E20   
doi: 10.1360/012011-XXX