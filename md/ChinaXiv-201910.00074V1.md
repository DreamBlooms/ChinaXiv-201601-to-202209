# 基于线性模型平均估计的置信区间

王苗苗123

(1.北京中医药大学中药学院，北京100102;2.中国科学院大学数学科学学院，北京 100049;3.中国科学院数学与系统科学研究院，北京100190)

摘要已有的关于模型平均估计渐近分布理论的研究多是基于局部误设定的假设,[1]是其中开创性的且最著名的文章之一.虽然利用局部误设定的假设可以证明模型平均估计渐近分布理论,但是[2]等对此假设提出了不合理性质疑和解释.本文我们研究[1]中的置信区间估计方法.证明了在一般参数设定下,虽然[1]中的渐近分布理论不一定成立,但是关于不确定参数的线性函数的置信区间在正态分布误差、线性回归模型下是有效的，即置信区间的覆盖率趋于预设定的名义水平.我们通过模拟研究进一步验证了理论结果

关键词模型平均,渐近分布,线性回归.

MR(2000)主题分类号62E20,62F12

# Confidence Interval based on Model Average Estimator for Linear Regression

WANG Miaomiaol $^ { 1 2 3 }$

(1.School of Chinese Materia Medica, Beijing University of Chinese Medicine， Beijing 100102; 2.School of Mathematical Sciences， University of Chinese Academy of Sciences，，Beijing 100049; 3.Academy of Mathematics and Systems Science，Chinese Academy of Sciences，Beijing 100190)

AbstractMost authors have examined the inference of model averaging estimators under local misspecification assumption. [1] is one of the most groundbreaking and famous articles. However, although the local misspecification assumption provides a suitable framework for studying the asymptotic theories of Frequentist Model Averaging estimators,it also draws comments from [2] because of its realism. In this paper, we prove that the confidence interval construction method for the linear function of parameters in [1] is still valid in linear regression with normally distributed error under general fixed parameter setup. It means that the coverage probability of the confidence interval can reach the nominal level. The simulation results support our theory conclusion.

KeywordsModel averaging,Asymptotic distribution,Linear regression.

# 1引言

模型平均方法自提出以来,备受统计学家关注,广泛应用于金融学、经济学、社会学、生物医学等各领域.模型平均方法有两大研究方向:贝叶斯模型平均(Bayes

Model Averaging,BMA）和频率模型平均(Frequentist Model Averaging,FMA).与贝叶斯模型平均[3]不同,FMA中的权重仅由数据确定,并且不需要先验假设.本文主要关注FMA的研究.模型平均估计的渐近分布理论是FMA方法研究中最核心的问题之一,关于此的研究非常多.例如[1]和[4]研究了基于极大似然估计的模型平均方法的渐近理论.[5]推导出了线性回归模型中最小二乘模型平均估计的渐近分布.其他工作还有[6]、[7]、[8]、[9]以及[10]等.这些工作都是基于对参数的局部误设定的假设.此假设要求一些真实参数的阶数和样本量有关,即为 $1 / { \sqrt { n } }$ .虽然这个假设为研究FMA估计量的渐近理论提供了一个合适的框架,但实际上此假设有待商榷，具体评论参阅 [2].最近,在一般固定参数设定下,也有关于模型平均估计渐近分布理论的研究.例如,基于Mallows 准则和交叉验证准则,在嵌套候选模型设置下,[11]推导了最小二乘模型平均估计的渐近分布；去除局部误设定的假设,[12]研究了模型平均估计的极限分布理论,但是极限分布中含有候选模型的偏差.

[1]是众多研究模型平均渐近分布理论的重要文献之一,给出了基于极大似然估计的模型平均方法的渐近理论.设独立随机样本 $y _ { 1 } , \ldots , y _ { n }$ ,其中 $\mathbf { \Psi } _ { n }$ 是样本量,且 $y _ { i }$ 的密度函数为 $f$ ，我们对参数 $\mu = \mu ( f )$ 进行统计推断,这里 $\mu$ 是任意光滑函数.[1]关注如下模型

$$
f ( y , \theta ) ,
$$

其中 $\pmb { \theta } = ( \theta _ { 1 } , \dots , \theta _ { q } ) ^ { T } = \left( \beta ^ { T } , \gamma ^ { T } \right) ^ { T } \subset \mathbf { \Theta } \subset \mathbb { R } ^ { q }$ 这里 $\beta$ 和 $\gamma$ 分别是 $q _ { 1 }$ 维和 $q _ { 2 }$ 维参数向量,且 $\beta$ 是确定在模型中的参数,而 $\gamma$ 则不然.若 $\gamma = \gamma _ { 0 }$ 固定且已知,对应的模型我们称作零模型，即 $f ( y , \pmb { \theta } ) = f \left( y , \left( \beta ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right)$ ．他们基于一种局部误设定的假定研究模型平均估计的渐近分布.局部误设定假设真实模型为

$$
f _ { t r u e } ( y ) = f _ { n } ( y ) = f \left( y , \left( \beta _ { 0 } ^ { T } , \left( \gamma _ { 0 } + \delta / \sqrt { n } \right) ^ { T } \right) ^ { T } \right) ,
$$

其中 $\pmb { \delta } = ( \delta _ { 1 } , \ldots , \delta _ { q _ { 2 } } ) ^ { T }$ 表示模型偏离零模型的程度,此时,

$$
\mu _ { t r u e } = \mu \left( \left( \beta _ { 0 } ^ { T } , \left( \gamma _ { 0 } + \delta / \sqrt { n } \right) ^ { T } \right) ^ { T } \right) .
$$

局部误设定假设意味着模型中一些参数的阶数和样本量有关,为 $1 / { \sqrt { n } }$ .尽管在此假设下,我们可以推导出FMA估计的渐近分布理论,但很多学者对此提出质疑,例如[2]怀疑此假设的真实性.我们研究估计的有效性通常是基于大样本理论，然而随着样本增多,若参数阶数为 $1 / { \sqrt { n } }$ 。则参数空间变得越来越小，导致参数越来越接近真实值.换句话说,此时所有的候选模型越来越接近真实模型.所以,在大样本下,局部误设定的假设是不真实的.总之,这一假设并不是一个常规的条件,而是关乎理论推导过程及结果的关键假设.

本文在一般固定参数设置下,研究[1]的置信区间构造方法.我们发现虽然[1]中的渐近分布理论不一定成立,但是关于参数 $\gamma$ 线性函数的置信区间在正态分布误差和线性回归模型下是有效的,即置信区间的覆盖率可达到预设定的名义水平,为模型平均估计的区间预测提供了方法和理论支持.

本文具体安排如下：第2节主要介绍候选模型的构造方法和模型平均估计.在第3节中,我们说明在固定参数设置下,[1]的渐近分布理论不一定成立,并给出此设置下[1]中的置信区间构造方法.第4节在正态分布误差、线性回归模型下,推导出模型平均估计的一些理论性质,并基于这些理论给出不确定参数的线性函数的置信区间.第5节通过模拟研究,进一步验证第4节的置信区间的有效性.最后,第6节做出总结.本文中所有引理和定理的证明见附录.

# 2模型框架和模型平均估计

考虑基于有限项协变量的线性回归模型

$$
y _ { i } = { \pmb x } _ { i } ^ { T } \beta + z _ { i } ^ { T } \gamma + e _ { i } , \quad i = 1 , \ldots , n ,
$$

其中 $y _ { i }$ 是响应变量, $\pmb { x } _ { i } = ( x _ { i , 1 } , \cdots , x _ { i , q _ { 1 } } ) ^ { T }$ 和 $\boldsymbol { z } _ { i } = ( z _ { i , 1 } , \cdot \cdot \cdot , z _ { i , q _ { 2 } } ) ^ { T }$ ， $i = 1 , \ldots , n$ 是协变量向量,误差项 $e _ { i }$ $, i = 1 , \ldots , n$ 独立同正态分布.令 $\pmb { h } _ { i } = \left( \pmb { x } _ { i } ^ { T } , \pmb { z } _ { i } ^ { T } \right) ^ { T }$ 以及 $H = \left( \boldsymbol { h } _ { 1 } , \cdot \cdot \cdot , \boldsymbol { h } _ { n } \right) ^ { T }$ ：设 $\mathrm { E } ( e _ { i } | { \bf h } _ { i } ) = 0$ 且 $\mathrm { V a r } ( e _ { i } | h _ { i } ) = \sigma ^ { 2 }$ 记 $\pmb { \theta } = \left( \beta ^ { T } , \gamma ^ { T } \right) ^ { T }$ ，则 $y _ { i }$ 的条件密度函数 $f ( y _ { i } , \pmb { \theta } | h _ { i } )$ （204号同 $\mathcal { N } \left( \pmb { x } _ { i } ^ { T } \pmb { \beta } + \pmb { z } _ { i } ^ { T } \gamma , \sigma ^ { 2 } \right)$ 的密度函数.

令 $\pmb { \theta } _ { 0 }$ 表示真实参数值.设一般固定参数设置为

$$
\boldsymbol { \theta } _ { 0 } = \left( \beta _ { 0 } ^ { T } , \gamma ^ { T } \right) ^ { T } = \left( \beta _ { 0 } ^ { T } , \left( \gamma _ { 0 } + \delta ^ { \prime } \right) ^ { T } \right) ^ { T } = \left( \beta _ { 0 } ^ { T } , \left( \gamma _ { 0 } + \delta / \sqrt { n } \right) ^ { T } \right) ^ { T } ,
$$

其中 $\gamma _ { 0 } = ( \gamma _ { 0 , 1 } , \cdot \cdot \cdot , \gamma _ { 0 , q _ { 2 } } ) ^ { T }$ 从而 $\pmb { \delta } ^ { \prime } = \left( \delta _ { 1 } ^ { \prime } , \ldots , \delta _ { q _ { 2 } } ^ { \prime } \right) ^ { T } = \gamma - \gamma _ { 0 }$ 是固定的且 $\delta = \sqrt { n } \delta ^ { \prime }$ ：

首先,在一般固定参数的假设 (2.2)下,我们给出候选模型的构造方法．设有$M$ 个子模型,其中第 $m$ 个候选模型包含参数 $\beta$ 以及参数 $\gamma$ 的某些分量 $\gamma _ { j }$ 等于$\gamma _ { j , 0 }$ 记 $k _ { m }$ 为第 $m$ 个候选模型中参数的个数．通常,如果考虑参数的所有可能的组合,则 $M = 2 ^ { q _ { 2 } }$ ；如果仅考虑嵌套组合，则 $M = q _ { 2 } + 1$ ，由参数下标组成的集合 $\boldsymbol { S }$ 是 $\{ 1 , \ldots , q _ { 2 } \}$ 的子集.对第 $m$ 个子模型,参数下标集 $S _ { m } = \{ i _ { 1 } , \cdot \cdot \cdot , i _ { k _ { m } - q _ { 1 } } \} \subset \{ 1 , \cdot \cdot \cdot , q _ { 2 } \}$ （204号且 $S _ { m } ^ { c } = \{ i _ { k _ { m } - q _ { 1 } + 1 } , \cdot \cdot \cdot , i _ { q _ { 2 } } \}$ 是 $S _ { m }$ 在集合 $\{ 1 , \ldots , q _ { 2 } \}$ 中的补集.为便于说明,记 $\gamma _ { S _ { m } } =$ （20 $\left( \gamma _ { i _ { 1 } } , \cdots , \gamma _ { i _ { k _ { m } - q _ { 1 } } } \right) ^ { T }$ 和樂 $\gamma _ { S _ { m } ^ { c } } = \left( \gamma _ { i _ { k _ { m } - q _ { 1 } + 1 } } , \cdot \cdot \cdot , \gamma _ { i _ { q _ { 2 } } } \right) ^ { T }$ 从而，第 $\mid m \mid$ 个模型中的参数为 ${ \pmb \theta } _ { m } = $ $\left( \beta ^ { T } , \gamma _ { m } ^ { T } \right) ^ { T }$ ，其中 $\gamma _ { m } = \left( \gamma _ { 1 } , \gamma _ { 2 } , \cdot \cdot \cdot , \gamma _ { q _ { 2 } } \right) ^ { T }$ .此时， $\gamma _ { S _ { m } ^ { c } } = \gamma _ { 0 , S _ { m } ^ { c } }$ .此外,通过对 $\pmb { \theta } _ { m }$ 的各分量进行一系列的置换,重写成如下形式

$$
\begin{array} { r } { \quad \Pi _ { m } \pmb { \theta } _ { m } = \left( \beta ^ { T } , \gamma _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T } = \left( \pmb { \theta } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T } , } \end{array}
$$

其中 $\pmb { \theta } _ { S _ { m } } = \left( \beta ^ { T } , \gamma _ { S _ { m } } ^ { T } \right) ^ { T }$ 且 $\Pi _ { m }$ 为置换矩阵. $\Pi _ { m }$ 可以通过对单位矩阵进行一系列行置换得到.设单位矩阵 $\pmb { I } _ { q } = \left( e _ { 1 } , \pmb { e } _ { 2 } , \cdot \cdot \cdot , \pmb { e } _ { q } \right) ^ { T }$ ，其中 $e _ { j }$ 是第 $j$ 个分量为1的单位向量,则

$$
\Pi _ { m } = \left( e _ { 1 } , \cdots , e _ { q _ { 1 } } , e _ { q _ { 1 } + i _ { 1 } } , \cdots , e _ { q _ { 1 } + i _ { k _ { m } - q _ { 1 } } } , e _ { q _ { 1 } + i _ { k _ { m } - q _ { 1 } + 1 } } , \cdots , e _ { q _ { 1 } + i _ { q _ { 2 } } } \right) ^ { T } .
$$

在第 $\mid m \mid$ 个模型下,记 $\widehat { \pmb { \theta } } _ { S _ { m } }$ 为参数 $\pmb { \theta } _ { S _ { m } }$ 在参数空间 $\Theta _ { m } \subset \mathbb { R } ^ { k _ { m } }$ 上的极大似然估计,这可由对数似然方程 $\begin{array} { r } { \sum _ { i = 1 } ^ { n } \partial \mathrm { l o g } f ( y _ { i } , \pmb { \theta } _ { m } | \pmb { h } _ { i } ) / \partial \pmb { \theta } _ { S _ { m } } = 0 } \end{array}$ 解得.此时, $\widehat { \pmb { \theta } } _ { S _ { m } }$ 也是 $\pmb { \theta } _ { S _ { m } }$ 的最小二乘估计.定义 $\widehat { \pmb { \theta } } _ { m } = \Pi _ { m } ^ { T } \left( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \pmb { \gamma } _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T }$ 记 $D _ { n } = \widehat { \delta } _ { f u l l } = \sqrt { n } \left( \widehat { \gamma } _ { f u l l } - \gamma _ { 0 } \right)$ 且 $\widehat { \gamma } _ { f u l l }$ 是基于全模型 $\gamma$ 的估计.定义 ${ \widehat { \mu } } _ { m } = \mu \left( { \widehat { \pmb { \theta } } } _ { m } \right)$ 为第 $m$ 个子模型的估计.下面我们考虑与[1]中形式相同的模型平均估计. $\mu ( \pmb { \theta } _ { 0 } )$ 的估计具有如下形式：

$$
\widehat { \mu } \left( \pmb { w } \left( D _ { n } \right) \right) = \sum _ { m = 1 } ^ { M } w _ { m } \left( D _ { n } \right) \widehat { \mu } _ { m } ,
$$

其中 $w _ { m } \left( D _ { n } \right)$ 是对第 $\mid m \mid$ 个候选模型所加的随机权重.于是权重向量

$$
{ \pmb w } \left( D _ { n } \right) = ( w _ { 1 } ( D _ { n } ) , \dots , w _ { M } ( D _ { n } ) ) ^ { T }
$$

属于权重集合W={ω(Dn)∈[0,1]M:∑m=1wm(Dn)=1}.

# 3区间估计

为便于描述[1]中的统计推断问题,我们首先给出一些记号.设 $f ( y , \theta )$ 关于参数$\pmb \theta$ 的一阶偏导存在且 $\Psi ( y , \pmb { \theta } ) = \partial \log f ( y , \pmb { \theta } ) / \partial \pmb { \theta }$ ，则Fisher信息阵定义为

$$
\mathcal { F } ( \pmb \theta ) = E _ { 0 } \left\{ \Psi ( y , \pmb \theta ) \Psi ( y , \pmb \theta ) ^ { T } \right\} .
$$

从而,基于全模型在 $\left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T }$ 处的Fisher信息阵为

$$
\begin{array} { r } { \boldsymbol { q _ { 1 } } \times \boldsymbol { q _ { 1 } } \quad \boldsymbol { q _ { 1 } } \times \boldsymbol { q _ { 2 } } } \\ { \boldsymbol { J _ { f u l l } } = \mathcal { F } \left( \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right) = \left( \begin{array} { c c } { \boldsymbol { J _ { 0 0 } } } & { \boldsymbol { J _ { 0 1 } } } \\ { \boldsymbol { J _ { 0 1 } } } & { \boldsymbol { J _ { 1 1 } } } \end{array} \right) , } \\ { \boldsymbol { J _ { 1 0 } } \qquad \boldsymbol { J _ { 1 1 } } } \end{array}
$$

$$
q _ { 2 } \times q _ { 1 } q _ { 2 } \times q _ { 2 }
$$

且其逆矩阵为

$$
\begin{array} { r } { \boldsymbol { q } _ { 1 } \times \boldsymbol { q } _ { 1 } \quad \boldsymbol { q } _ { 1 } \times \boldsymbol { q } _ { 2 } } \\ { \boldsymbol { J } _ { f u l l } ^ { - 1 } = \left( \begin{array} { c c } { \boldsymbol { J } ^ { 0 0 } } & { \boldsymbol { J } ^ { 0 1 } } \\ { \boldsymbol { J } } & { \boldsymbol { \mathbf { \mu } } } \\ { \boldsymbol { J } ^ { 1 0 } } & { \boldsymbol { J } ^ { 1 1 } } \end{array} \right) . } \end{array}
$$

$$
q _ { 2 } \times q _ { 1 } q _ { 2 } \times q _ { 2 }
$$

类似于[1],我们感兴趣的参数 $\mu ( \pmb \theta _ { 0 } )$ 的 $1 - \alpha$ 置信区间为

$$
\begin{array} { r l r } & { } & { \left[ \widehat { \mu } \left( \pmb { w } \left( D _ { n } \right) \right) - { \widehat { \omega } } ^ { T } \left\{ D _ { n } - { \widehat { \delta } } \left( D _ { n } \right) \right\} / \sqrt { n } - z _ { 1 - \alpha / 2 } { \widehat { \varphi } } / \sqrt { n } , \right. } \\ & { } & { \left. \widehat { \mu } \left( \pmb { w } \left( D _ { n } \right) \right) - { \widehat { \omega } } ^ { T } \left\{ D _ { n } - { \widehat { \delta } } \left( D _ { n } \right) \right\} / \sqrt { n } + z _ { 1 - \alpha / 2 } { \widehat { \varphi } } / \sqrt { n } \right] , } \end{array}
$$

其中 $z _ { 1 - \alpha / 2 }$ 是标准正态分布的 $1 - \alpha / 2$ 分位数； $\widehat { J } _ { 0 0 } ^ { - 1 } , \widehat { J } _ { 1 0 } , \widehat { J } _ { 0 1 }$ 以及 $\widehat { J } _ { 1 1 }$ 分别是 $J _ { 0 0 } ^ { - 1 }$ ， $J _ { 1 0 } , J _ { 0 1 }$ 以及 $J _ { 1 1 }$ 的相合估计,从而利用 $\widehat { K } = \left( \widehat { J } _ { 1 1 } - \widehat { J } _ { 1 0 } \widehat { J } _ { 0 0 } ^ { - 1 } \widehat { J } _ { 0 1 } \right) ^ { - 1 }$ 估计 $K = \left( J _ { 1 1 } - J _ { 1 0 } J _ { 0 0 } ^ { - 1 } J _ { 0 1 } \right) ^ { - 1 }$ （204号 $\begin{array} { r } { \widehat { \omega } = \widehat { J } _ { 1 0 } \widehat { J } _ { 0 0 } ^ { - 1 } \frac { \partial \mu } { \partial \beta } - \frac { \partial \mu } { \partial \gamma } } \end{array}$ 和 $\widehat { \varphi } = \left\{ \left( \frac { \partial \mu } { \partial \pmb { \theta } } \right) ^ { T } \widehat { J } _ { 0 0 } ^ { - 1 } \frac { \partial \mu } { \partial \pmb { \theta } } + \widehat { \omega } ^ { T } \widehat { K } \widehat { \omega } \right\} ^ { 1 / }$ 2 分别是 $\begin{array} { r } { \omega = J _ { 1 0 } J _ { 0 0 } ^ { - 1 } \frac { \partial \mu } { \partial \beta } - \frac { \partial \mu } { \partial \gamma } } \end{array}$ 和$\varphi = \left\{ \left( { \frac { \partial \mu } { \partial \theta } } \right) ^ { T } J _ { 0 0 } ^ { - 1 } { \frac { \partial \mu } { \partial \theta } } + \omega ^ { T } K \omega \right\} ^ { 1 }$ 2 的相合估计,注意其中的偏导数均是在 $\left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T }$ 点取得; $\Gamma _ { m }$ 是 $\left( k _ { m } - q _ { 1 } \right) \times q _ { 2 }$ 维选择矩阵,将向量 $\gamma _ { m }$ 映射成它的子向量 $\gamma _ { S _ { m } } = \Gamma _ { m } \gamma _ { m }$ ；记$K _ { m } = \left( \Gamma _ { m } K ^ { - 1 } \Gamma _ { m } ^ { T } \right) ^ { - 1 }$ ，令

$$
\widehat { \delta } ( D _ { n } ) = K ^ { 1 / 2 } \left\{ \sum _ { m = 1 } ^ { M } w _ { m } \left( D _ { n } \right) V _ { m } \right\} K ^ { - 1 / 2 } D _ { n } ,
$$

这里 $D _ { n } = \widehat { \delta } _ { f u l l } = \sqrt { n } \left( \widehat { \gamma } _ { f u l l } - \gamma _ { 0 } \right)$ 且 $V _ { m } = K ^ { - 1 / 2 } \Gamma _ { m } ^ { T } K _ { m } \Gamma _ { m } K ^ { - 1 / 2 }$

基于第 $\mathbf { \Omega } _ { m }$ 个模型的Fisher信息阵为

$$
\begin{array} { r } { J _ { S _ { m } } = \left( \begin{array} { c c } { q _ { 1 } \times q _ { 1 } } & { q _ { 1 } \times ( k _ { m } - q _ { 1 } ) } \\ { J _ { 0 0 } } & { J _ { 0 1 } \Gamma _ { m } ^ { T } } \\ { } & { } \\ { \Gamma _ { m } J _ { 1 0 } } & { \Gamma _ { m } J _ { 1 1 } \Gamma _ { m } ^ { T } } \end{array} \right) , } \\ { \big ( k _ { m } - q _ { 1 } \big ) \times q _ { 1 } } & { \big ( k _ { m } - q _ { 1 } \big ) \times \big ( k _ { m } - q _ { 1 } \big ) } \end{array}
$$

且其逆矩阵为

$$
\begin{array} { r } { J _ { \cal S _ { m } } ^ { - 1 } = \left( \begin{array} { c c } { q _ { 1 } \times q _ { 1 } } & { q _ { 1 } \times ( k _ { m } - q _ { 1 } ) } \\ { J ^ { 0 0 , m } } & { J ^ { 0 1 , m } } \\ { } & { } \\ { J ^ { 1 0 , m } } & { J ^ { 1 1 , m } } \end{array} \right) . } \\ { \left( k _ { m } - q _ { 1 } \right) \times q _ { 1 } \ } & { \left( k _ { m } - q _ { 1 } \right) \times \left( k _ { m } - q _ { 1 } \right) } \end{array}
$$

下面,我们解释[1]中的结果在固定参数设置下不一定成立.记 $\widehat { \pmb { \theta } } _ { S _ { m } } = \left( \widehat { \beta } _ { S _ { m } } ^ { T } , \widehat { \gamma } _ { S _ { m } } ^ { T } \right) ^ { T }$ 由 $\begin{array} { r } { \sum _ { i = 1 } ^ { n } \partial \mathrm { l o g } f \left( y _ { i } , \left( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T } \right) \bigg / \partial { \pmb { \theta } } _ { S _ { m } } = 0 , } \end{array}$ 将

$$
\sum _ { i = 1 } ^ { n } \frac { \partial \mathrm { l o g } f \left( y _ { i } , \left( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T } \right) } { \partial { \pmb { \theta } } _ { S _ { m } } }
$$

在 $\left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T }$ 处 Taylor展开,得

$$
\begin{array} { r l } { \mathfrak { w } = } & { \frac { 1 } { \sqrt { \pi } } \displaystyle \sum _ { s = 1 } ^ { n } \frac { \gamma \log ( ( \mathfrak { F } _ { s } ( \cdot , \mathfrak { F } _ { s } ^ { \mathcal { N } } , \mathfrak { F } _ { s , s } ^ { \mathcal { N } } ) ) ^ { T } ) } { \partial \mathfrak { F } _ { s , s } } } \\ { = } & { \frac { 1 } { \sqrt { \pi } } \displaystyle \sum _ { s = 1 } ^ { n } [ \frac { \partial \mathfrak { u } _ { s } ( \cdot , \mathfrak { F } _ { s } ^ { \mathcal { N } } , \mathfrak { F } _ { s , s } ^ { \mathcal { N } } ) } { \partial \mathfrak { F } _ { s , s } } ] _ { 1 } ( \frac { \partial ^ { 2 } \mathfrak { u } _ { s , s } ( \frac { \partial } { \partial \mathfrak { x } } _ { s } ( \cdot , \mathfrak { F } _ { s } ^ { \mathcal { N } } ) ^ { T } ) } { \partial \mathfrak { F } _ { s , s } \partial \mathfrak { F } _ { s , s } ^ { \mathcal { N } } } ) \frac { \partial ^ { 2 } \mathfrak { u } _ { s , s } ( \frac { \partial } { \partial \mathfrak { x } } _ { s } ( \cdot , \mathfrak { F } _ { s } ^ { \mathcal { N } } ) ^ { T } ) } { \partial \mathfrak { F } _ { s , s } \partial \mathfrak { F } _ { s , s } ^ { \mathcal { N } } } } \\ & { \quad + ( \widehat { \beta } _ { s = - 3 } ) ^ { T } \widehat { \gamma } ( \mathfrak { F } _ { s } ( \cdot , \mathfrak { F } _ { s } , \cdot ) ^ { T } , \mathfrak { u } ) ^ { \mathcal { N } } ] ^ { T } } \\ { = } &  \frac { 1 } { \sqrt { \pi } } \displaystyle \sum _ { s = 1 } ^ { n } \frac { \gamma \log ( ( \mathfrak { L } _ { s } ( \cdot , \mathfrak { X } _ { s } ^ { \mathcal { N } } , \mathfrak { F } _ { s } ^ { \mathcal { N } } ) ^ { T } ) } { \partial \mathfrak { F } _ { s , s } } + \frac { \partial ^ { 2 } \mathfrak { u } _ { s , s } ( \frac { \partial } { \partial \mathfrak { x } } _ { s } ( \cdot , \widehat { \beta } _ { s } ^ { \mathcal { N } } , \mathfrak { F } _ { s } ^ { \mathcal { N } } ) ) } { \partial \mathfrak { F } _ { s , s } \partial \mathfrak { F } _ { s , s } ^ { \mathcal { N } } } \\ & { \quad \cdot ( ( \widehat { \beta } _ { s , - 3 } ) ^ { T } , ( \mathfrak { F } _ { s , - 3 } \cap \mathfrak { L } _ { s } ) ^ { T } ) ^ { T } ] . } \end{array}
$$

其中 $\left( \widetilde { \beta } _ { 0 } ^ { T } , \widetilde { \gamma } _ { 0 } ^ { T } \right) ^ { T } = \left( \widetilde { \beta } _ { 0 } ^ { T } , \widetilde { \gamma } _ { 0 , S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T }$ 位于 $\left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T }$ 和 $\left( \widehat { \theta } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T }$ 之间.因此

$$
\left( \sqrt { n } \left( \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } \right) \right) = \left( - \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( y _ { i } , \left( \widehat { \beta } _ { 0 } ^ { T } , \widetilde { \gamma } _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } \right) ^ { - 1 } \cdot \sqrt { n } \left[ \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial \log f \left( y _ { i } , \theta _ { 0 } \right) } { \partial \theta _ { S _ { m } } } \right] .
$$

根据[13]中定理18的证明,注意到 $\mathrm { E } _ { 0 } \left\{ \Psi _ { m } ( y , \pmb { \theta } _ { S _ { m } } ) \right\}$ 关于 $\theta _ { { S _ { m } } }$ 连续,可知任给 $\varepsilon > 0$ 存在 $\rho > 0$ 使得当 $| \pmb { \theta } _ { S _ { m } } - \pmb { \theta } _ { 0 , S _ { m } } | < \rho$ 时,

$$
\left| \mathrm { E } _ { 0 } \dot { \Psi } _ { m } ( y , \pmb { \theta } _ { S _ { m } } ) + { \cal J } _ { S _ { m } } \right| < \varepsilon .
$$

再由一致强大数律知,依概率1地存在正整数 $N$ ，使得当 $n > N$ 时有

$$
\operatorname* { s u p } _ { \theta _ { S _ { m } } \in \{ \theta _ { S _ { m } } : | \theta _ { S _ { m } } - \theta _ { 0 } , s _ { m } | < \rho \} } \left| \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \dot { \Psi } _ { m } ( y _ { i } , \theta _ { S _ { m } } ) - \mathrm { E } _ { 0 } \dot { \Psi } _ { m } ( y , \theta _ { S _ { m } } ) \right| < \varepsilon .
$$

结合(3.5)以及 (3.6)，当 $n > N$ 时,有

$$
\begin{array} { r l } & { \left| \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } + J _ { S _ { m } } \right| } \\ { \le } & { \displaystyle \operatorname* { s u p } _ { \theta _ { S _ { m } } \in \{ \theta _ { S _ { m } } : \left. \theta _ { S _ { m } } - \theta _ { 0 , S _ { m } } \right. < \rho \} } \left\{ \left| \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \dot { \Psi } _ { m } ( y , \theta _ { S _ { m } } ) - \mathrm { E } _ { 0 } \dot { \Psi } _ { m } ( y , \theta _ { S _ { m } } ) \right| \right. } \\ & { \qquad \left. + \left| \mathrm { E } _ { 0 } \dot { \Psi } _ { m } ( y , \theta _ { S _ { m } } ) + J _ { S _ { m } } \right| \right\} \le 2 \varepsilon . } \end{array}
$$

但是在固定参数设置下,不能保证 $( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } ) ^ { T } \overset { a . s . } {  } ( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } ) ^ { T }$ ，从而,我们不能保证下式成立

$$
\frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \mathrm { l o g } f \left( y _ { i } , \left( \widetilde { \beta } _ { 0 } ^ { T } , \widetilde { \gamma } _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } \xrightarrow { a . s . } \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \mathrm { l o g } f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } .
$$

注意到

$$
\begin{array} { r l } & { \left| \frac { 1 } { n } \displaystyle \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( \mathcal { Y } _ { i } , \left( \widetilde { \beta } _ { 0 } ^ { T } , \widetilde { \gamma } _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } + \mathcal { I } _ { S _ { m } } \right| } \\ { = } & { \left| \frac { 1 } { n } \displaystyle \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( \mathcal { Y } _ { i } , \left( \widetilde { \beta } _ { 0 } ^ { T } , \widetilde { \gamma } _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } - \frac { 1 } { n } \displaystyle \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( \mathcal { Y } _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } \right. } \\ & { \left. + \frac { 1 } { n } \displaystyle \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( \mathcal { Y } _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } + \mathcal { I } _ { S _ { m } } \right| , } \end{array}
$$

所以不能保证

$$
- \sum _ { i = 1 } ^ { n } \partial ^ { 2 } \mathrm { l o g } f \left( y _ { i } , \left( \widetilde { \beta } _ { 0 } ^ { T } , \widetilde { \gamma } _ { 0 } ^ { T } \right) ^ { T } \right) \Big / \left( n \partial \pmb { \theta } _ { S _ { m } } \partial \pmb { \theta } _ { S _ { m } } ^ { T } \right) \xrightarrow { a . s . } J _ { S _ { m } } .
$$

对 $f \left( y _ { i } , \pmb { \theta } _ { 0 } \right)$ 在 $\left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T }$ 处 Taylor 展开知,

$$
f \left( y _ { i } , \theta _ { 0 } \right) = f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right) \left\{ 1 + \frac { \partial \log f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \right) } { \partial \gamma } \delta ^ { \prime } + R _ { 1 } ( y _ { i } , \delta ^ { \prime } ) \right\} ,
$$

其中 $R _ { 1 } ( y _ { i } , \delta ^ { \prime } )$ 是余项.然而,在一般固定参数设置下, $f ( y _ { i } , \pmb \theta _ { 0 } )$ 的余项不一定随着 $n$ 趋于无穷而趋于0.故而,[1]的渐近分布理论不一定成立.

# 4主要结论

本节在模型框架(2.1)和固定参数设置 (2.2)下,我们证明当 $\mu$ 是参数 $\gamma$ 的线性函数时,(3.4)的覆盖率可达到预设定的名义水平.为便于清晰解释[1]中置信区间构造方法在特殊设置下的有效性，下面,我们仍采用类似于上节的记号.在给定 $H$ 下,我们给出信息阵的具体形式.基于全模型在 $\left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T }$ 处的Fisher信息矩阵为

$$
J _ { f u l l } | _ { H } = \left( { \begin{array} { c c } { J _ { 0 0 } | _ { H } } & { J _ { 0 1 } | _ { H } } \\ { J _ { 1 0 } | _ { H } } & { J _ { 1 1 } | _ { H } } \end{array} } \right) = { \frac { 1 } { n \sigma ^ { 2 } } } \sum _ { i = 1 } ^ { n } \left( { \begin{array} { c c } { x _ { i } x _ { i } ^ { T } } & { x _ { i } z _ { i } ^ { T } } \\ { z _ { i } x _ { i } ^ { T } } & { z _ { i } z _ { i } ^ { T } } \end{array} } \right) ,
$$

其中 $\sigma ^ { 2 }$ 基于全模型来估计;同理,基于第 $m$ 个模型的Fisher信息阵为

$$
J _ { S _ { m } | H } = \left( \begin{array} { c c } { J _ { 0 0 | H } } & { J _ { 0 1 | H } \Gamma _ { m } ^ { T } } \\ { \Gamma _ { m } J _ { 1 0 | H } } & { \Gamma _ { m } J _ { 1 1 | H } \Gamma _ { m } ^ { T } } \end{array} \right) ;
$$

相应的逆矩阵分别记为

$$
J _ { f u l l | H } ^ { - 1 } = \binom { J ^ { 0 0 | H } } { J ^ { 1 0 | H } } \quad J ^ { 0 1 | H } \quad | \downarrow \downarrow \downarrow \quad J _ { S _ { m } | H } ^ { - 1 } = \binom { J ^ { 0 0 , m | H } } { J ^ { 1 0 , m | H } } \quad J ^ { 0 1 , m | H } \quad \cdot
$$

令

$$
\varphi _ { H } = \left\{ \left( \frac { \partial \mu } { \partial \pmb { \theta } } \right) ^ { T } J _ { 0 0 | H } ^ { - 1 } \frac { \partial \mu } { \partial \pmb { \theta } } + \omega _ { H } ^ { T } K _ { H } \omega _ { H } \right\} ^ { 1 / 2 }
$$

以及

$$
\widehat { \delta } ( D _ { n } ) = K _ { H } ^ { 1 / 2 } \left\{ \sum _ { m = 1 } ^ { M } w _ { m } \left( D _ { n } \right) V _ { m | H } \right\} K _ { H } ^ { - 1 / 2 } D _ { n } ,
$$

其中 $\begin{array} { r } { \omega _ { H } = J _ { 1 0 | H } J _ { 0 0 | H } ^ { - 1 } \frac { \partial \mu } { \partial \beta } - \frac { \partial \mu } { \partial \gamma } } \end{array}$ $\begin{array} { r } { - \frac { \partial \mu } { \partial \gamma } , K _ { H } = { \left( J _ { 1 1 | H } - J _ { 1 0 | H } J _ { 0 0 | H } ^ { - 1 } J _ { 0 1 | H } \right) } ^ { - 1 } , D _ { n } = \widehat \delta _ { f u l l } = \sqrt { n } ( \widehat \gamma _ { f u l l } - \widehat \gamma _ { f l u } ) , } \end{array}$ （204号$\gamma _ { 0 , }$ ）， $K _ { m | H } = \left( \Gamma _ { m } K _ { H } ^ { - 1 } \Gamma _ { m } ^ { T } \right) ^ { - 1 }$ 以及 $V _ { m | H } = K _ { H } ^ { - 1 / 2 } \Gamma _ { m } ^ { T } K _ { m | H } \Gamma _ { m } K _ { H } ^ { - 1 / 2 }$ .

下面,我们给出一些引理和定理.

引理1.在固定参数设置(2.2)下，有

$$
\sqrt { n } \left( \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } \right) = J _ { S _ { m } | H } ^ { - 1 } \left( { J } _ { 0 1 | H } \right) \sqrt { n } \delta ^ { \prime } \sim \mathcal { N } \left( 0 , J _ { S _ { m } | H } ^ { - 1 } \right) .
$$

进一步,我们可以得出如下结论，

引理2.设 $\partial ^ { 2 } \mu ( \pmb { \theta } ) / \left( \partial \beta \partial \beta ^ { T } \right)$ ， $\partial ^ { 2 } \mu ( \pmb { \theta } ) / \left( \partial \beta \partial \gamma ^ { T } \right)$ 以及 $\partial ^ { 2 } \mu ( \pmb { \theta } ) / \left( \partial \gamma \partial \beta ^ { T } \right)$ 的每个元素均有界，当 $\mu$ 是参数 $\gamma$ 的线性函数时，在第 $m$ 个模型下，我们有

$$
\sqrt { n } \left[ \left\{ \widehat { \mu } _ { m } - \mu \left( \pmb { \theta } _ { 0 } \right) \right\} - \omega _ { H } ^ { T } \left( \pmb { I } _ { q _ { 2 } } - K _ { H } ^ { 1 / 2 } V _ { m | H } K _ { H } ^ { - 1 / 2 } \right) \delta ^ { \prime } \right]
$$

$$
\begin{array} { r l } { = } & { { } \Bigg \{ \frac { \partial \mu ( \pmb { \theta } _ { 0 } ) } { \partial \beta } \Bigg \} ^ { T } J _ { 0 0 | H } ^ { - 1 } M _ { n } - \omega _ { H } ^ { T } K _ { H } ^ { 1 / 2 } V _ { m | H } K _ { H } ^ { - 1 / 2 } W _ { n } + o _ { p } ( 1 ) , } \end{array}
$$

其中 $M _ { n } \sim \mathcal { N } \left( \mathbf { 0 } , J _ { 0 0 \mid H } \right)$ 且 $W _ { n } \sim \mathcal { N } \left( \mathbf { 0 } , K _ { H } \right)$

定理1.在引理2的假设下，模型平均估计 (2.3)的分布有如下形式

$$
\begin{array} { r l } & { \sqrt { n } \left[ \left\{ \widehat { \mu } \left( \pmb { w } \left( D _ { n } \right) \right) - \mu \left( \pmb { \theta } _ { 0 } \right) \right\} - \omega _ { H } ^ { T } \left\{ \delta ^ { \prime } - \widehat { \delta } \left( \pmb { \delta } ^ { \prime } \right) \right\} \right] } \\ { = } & { \left\{ \displaystyle \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \beta } \right\} ^ { T } J _ { 0 0 } ^ { - 1 } M _ { n } - \omega _ { H } ^ { T } \widehat { \delta } ( W _ { n } ) + o _ { p } ( 1 ) \doteq \Lambda + o _ { p } ( 1 ) , } \end{array}
$$

其中 $\Lambda$ 服从均值0的正态分布，且方差为

$$
\Sigma = \left( \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \pmb { \theta } } \right) ^ { T } J _ { 0 0 | H } ^ { - 1 } \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \pmb { \theta } } + \omega _ { H } ^ { T } \mathrm { V a r } \widehat { \pmb { \delta } } ( W _ { n } ) \pmb { \omega } _ { H } .
$$

在固定参数设置(2.2）下, $\mu ( \pmb \theta _ { 0 } )$ 的 $1 - \alpha$ 置信区间变成

$$
\begin{array} { r l r } { C I _ { \mu , n } } & { = } & { \left[ \widehat { \mu } \left( \pmb { w } \left( D _ { n } \right) \right) - \omega _ { H } ^ { T } \left\{ D _ { n } ^ { \prime } - \widehat { \delta } \left( D _ { n } ^ { \prime } \right) \right\} - z _ { 1 - \alpha / 2 } \varphi _ { H } / \sqrt { n } , \right. } \\ & { } & { \left. \widehat { \mu } \left( \pmb { w } \left( D _ { n } \right) \right) - \omega _ { H } ^ { T } \left\{ D _ { n } ^ { \prime } - \widehat { \delta } \left( D _ { n } ^ { \prime } \right) \right\} + z _ { 1 - \alpha / 2 } \varphi _ { H } / \sqrt { n } \right] } \end{array}
$$

且 $D _ { n } ^ { \prime } = \widehat { \delta } _ { f u l l } ^ { \prime } = \widehat { \gamma } _ { f u l l } - \gamma _ { 0 }$ 定义

$$
T _ { n } = \frac { \sqrt { n } \left[ \widehat { \mu } \left( \pmb { w } \left( D _ { n } \right) \right) - \mu \left( \pmb { \theta } _ { 0 } \right) - \omega _ { H } ^ { T } \left\{ D _ { n } ^ { \prime } - \widehat { \delta } \left( D _ { n } ^ { \prime } \right) \right\} \right] } { \varphi _ { H } } .
$$

我们有下列结论.

推论1.在引理2的假设下, $T _ { n }$ 依概率收敛于服从标准正态分布的随机变量,即 (4.7) 的区间覆盖率趋于预设定的名义水平.

根据这一推论, $\mu ( \pmb \theta _ { 0 } )$ 的 $1 - \alpha$ 置信区间依赖于 $\delta$ ，在固定参数设置下,当我们把[1]所提出的置信区间中的 $\delta$ 替换成 $\sqrt { n } \delta ^ { \prime }$ 时,关于参数 $\gamma$ 的线性函数的区间覆盖率可达到 $1 - \alpha$

下一节,我们应用MonteCarlo模拟来进一步验证这些理论结果.

# 5模拟研究

考虑线性回归模型

$$
y _ { i } = x _ { i } ^ { T } \beta + z _ { i } ^ { T } \gamma + e _ { i } , \quad i = 1 , \ldots , n ,
$$

其中 $\beta = ( 1 , 1 ) ^ { T }$ ， $\gamma = ( 0 , 1 . 5 , 0 ) ^ { T }$ ， $\pmb { x } _ { i } = ( 1 , x _ { i , 1 } ) ^ { T }$ ， $z _ { i } = ( z _ { i , 1 } , z _ { i , 2 } , z _ { i , 3 } ) ^ { T }$ ， $( x _ { i , 1 } , z _ { i , 1 } , z _ { i , 2 } , z _ { i , 3 } ) ^ { T } \sim$ $\mathcal { N } ( \mathbf { 0 } , Q )$ ；误差项 $e _ { i }$ ， $i = 1 , \ldots , n$ 相互独立同正态分布 $\mathcal { N } ( 0 , \sigma ^ { 2 } )$ 且 $\sigma$ 为0.5,1和1.5.设$Q$ 的对角元均为1且非对角元为 $\rho ^ { | i - j | }$ ，其中 $\rho = 0 . 5$ 和0.8．取样本量 $n = 1 0$ ，50和100.基于上述设置,模拟循环1000次,我们研究参数 $\beta _ { 1 } , \gamma _ { 2 }$ 以及均值 $\mu$ 的置信区间.

下面，我们考虑一些常用的权重选择准则，包括S-AIC、S-BIC以及MMA.基于这些准则的结果在表格中分别用SAIC、SBIC以及MMA来标记.

S-AIC和 S-BIC权重:第 $\mid m \mid$ 个候选模型的AIC 和BIC分别为

$$
\mathrm { A I C } _ { m } = - 2 \sum _ { i = 1 } ^ { n } \log f ( y _ { i } , \widehat { \theta } _ { m } | h _ { i } ) + 2 k _ { m } , \quad \mathrm { B I C } _ { m } = - 2 \sum _ { i = 1 } ^ { n } \log f ( y _ { i } , \widehat { \theta } _ { m } | h _ { i } ) + k _ { m } \log n .
$$

从而，定义S-AIC和S-BIC权重为

$$
\widehat { w } _ { \mathrm { x I C } , m } = \exp ( - \mathrm { x I C } _ { m } / 2 ) / \sum _ { m = 1 } ^ { M } \exp ( - \mathrm { x I C } _ { m } / 2 ) , \quad m = 1 , \ldots , M ,
$$

其中 $\mathrm { x I C } _ { m }$ 是第 $m$ 个子模型的AIC或BIC权值

MMA权重：由[14]提出的MMA权重可通过极小化下式

$$
C _ { n } ( \pmb { w } ) = \sum _ { i = 1 } ^ { n } \bigg \{ y _ { i } - \sum _ { m = 1 } ^ { M } w _ { m } \widehat { \mu } _ { m } \bigg \} ^ { 2 } + 2 \sigma ^ { 2 } \sum _ { m = 1 } ^ { M } w _ { m } k _ { m }
$$

得到,其中权重向量 ${ \pmb w } \equiv ( w _ { 1 } , \dots , w _ { M } ) ^ { T }$ 且限制在如下单纯形集合 $\mathcal { W } \equiv \{ \pmb { w } \in [ 0 , 1 ] ^ { M }$ $0 \leq w _ { k } \leq 1 \}$ 中; $\sigma ^ { 2 }$ 未知但可基于全模型来估计.

当 $( x _ { i , 1 } , z _ { i , 1 } , z _ { i , 2 } , z _ { i , 3 } ) ^ { T }$ 来自不同分布时,比如均匀分布、指数分布以及一些混合分布，我们发现变换协变量的分布对模拟结果的影响甚微.所以,这里我们只展示正态分布情形的模拟结果.

基于上述权重,在表1-2中,我们给出了置信区间的覆盖率和平均长度.可以看到所有方法的区间覆盖率都达到了预设定的名义水平.值得注意的是在不同权重准则下,区间的覆盖率和平均长度是一样的,这说明[1]的置信区间构造方法不受权重影响,只需权重之和为1.这些模拟结果支持了我们的结论.

# 6总结

现有关于模型平均渐近分布理论的研究成果基本上是基于局部误设定的假设,参数与样本量有关且随样本量增大而变得非常小.鉴于此假设的非真实性,我们希望去除这种假设,研究在一般固定参数设定下,模型平均估计的统计推断.本文在一般固定参数设置下,对于线性回归模型且误差项服从正态分布,我们证明了[1]中的置信区间构造方法对不确定参数的线性函数仍然有效.换句话说,尽管[1]的渐近分布理论在一般参数设定下无法证实,但是在上述特殊情况下,不确定参数的线性函数的置信区间覆盖率可达到预设定的名义水平.

在一般固定参数设置下,研究模型平均估计量的统计推断问题意义非凡.未来我们可以研究,在线性回归模型下,当误差项来自于其他分布时,[1]中的置信区间构造方法.也可以推导基于其他权重选择准则的模型平均估计的渐近分布理论.

# 参考文献

[1] Hjort NL, Claeskens G.Frequentist model average estimators.Journal of the American Statistical Association, 2003, 98(464): 879-899.   
[2] Raftery A E, Zheng Y.Discusson: Performance of Bayesian Model Averaging. Journal of the American Statistical Association, 2003, 98(1): 931-938.   
[3] Hoeting JA,Madigan D,Raftery A E,Volinsky C T.Bayesian model averaging:a tutorial. Statistical Science,1999,14(4):382-401.   
[4] Claeskens G, Hjort N L. Model Selection and Model Averaging. Cambridge: Cambridge University Press,2008.   
[5] Liu C A. Distribution theory of the least squares averaging estimator. Journal of Econometrics, 2015,186(1): 142-159.   
[6] Leung G, Barron A R. Information theory and mixing least-squares regressions. IEEE Transactions on Information Theory,2006,52(8):3396-3410.   
[7] Potscher,Benedikt M.The Distribution of Model Averaging Estimators and an Impossibility Result regarding Its Estimation.Lecture Notes-Monograph Series,2006,52:113-129.   
[8] Hansen B E. Averaging Estimators for Regressions with a Possible Structural Break. Econometric Theory,2009,25(6): 1498-1514..   
[9] Hansen B E.Averaging estimators for autoregressons with a near unit root. Journal of Econometrics,2010,158(1): 142-155.   
[10] 朱容,邹国华.半参数模型平均估计的渐近理论.中国科学:数学,2018,v.48(8):31019-1052. (Zhu R, Zou G H. The asymptotic theory for model averaging in general semiparametric models (in Chinese). Sci Sin Math, 2018, 48(8): 1019-1052)   
[11] Zhang X Y,Liu C A. Inference after Model Averaging in Linear Regression Models. Social Science Electronic Publishing,2017.   
[12] Mitra P,Lian H,Mitra R,Liang H, Xie MG.A general framework for frequentist model averaging. Science China Mathematics,2019,62(2):205-226.   
[13] Ferguson T S.A Course in Large Sample Theory. London: Chapman and Hall,1996.   
[14] Hansen B E. Least squares model averaging. Econometrica, 2007,75(4): 1175-1189.

# 附录

# 引理1的证明

在线性回归模型下，当误差项服从正态分布时，我们有

$$
\begin{array} { r l } { \left( \frac { \partial \log f ( y _ { i } , \theta _ { 0 } | h _ { i } ) } { \partial \beta } \right) } & { = \ \left( - \frac { 1 } { \sigma ^ { 2 } } \left( - y _ { i } x _ { i } + x _ { i } ^ { T } \beta _ { 0 } \alpha _ { i } + z _ { i } ^ { T } \left( \gamma _ { 0 } + \delta ^ { \prime } \right) x _ { i } \right) \right) } \\ { \left( \frac { \partial \log f ( y _ { i } , \theta _ { 0 } | h _ { i } ) } { \partial \gamma } \right) } & { = \ \left( - \frac { 1 } { \sigma ^ { 2 } } \left( - y _ { i } z _ { i } + z _ { i } ^ { T } \left( \gamma _ { 0 } + \delta ^ { \prime } \right) z _ { i } + x _ { i } ^ { T } \beta _ { 0 } z _ { i } \right) \right) } \\ & { = \ \left( - \frac { 1 } { \sigma ^ { 2 } } \left( - y _ { i } x _ { i } + x _ { i } ^ { T } \beta _ { 0 } \alpha _ { i } + z _ { i } ^ { T } \gamma _ { 0 } \alpha _ { i } \right) \right) + \left( - \frac { 1 } { \sigma ^ { 2 } } z _ { i } ^ { T } \delta ^ { \prime } x _ { i } \right) } \\ & { = \ \left( \frac { \partial \log f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \left| h _ { i } \right. \right) } { \partial \beta } \right) + \left( - \frac { 1 } { \sigma ^ { 2 } } x _ { i } z _ { i } ^ { T } \right) \delta ^ { \prime } } \\ & { = \ \frac { \left( \partial \log f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \left| h _ { i } \right. \right) \right)} { \partial \gamma }  + \left( - \frac { 1 } { \sigma ^ { 2 } } z _ { i } z _ { i } ^ { T } \right) \delta ^ { \prime } } \end{array}
$$

以及

$$
\frac { \partial ^ { 2 } \log f \left( y _ { i } , \theta _ { 0 } | h _ { i } \right) } { \partial \theta \partial \theta ^ { T } } = - \frac { 1 } { \sigma ^ { 2 } } \left( x _ { i } x _ { i } ^ { T } \quad x _ { i } z _ { i } ^ { T } \right) = \frac { \partial ^ { 2 } \log f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \left| h _ { i } \right. \right) } { \partial \theta \partial \theta ^ { T } } .
$$

由 $\begin{array} { r } { \sum _ { i = 1 } ^ { n } \partial \log f \left( y _ { i } , \left( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T } \big | \pmb { h } _ { i } \right) \bigg / \partial \pmb { \theta } _ { S _ { m } } = 0 , } \end{array}$ 将

$$
\sum _ { i = 1 } ^ { n } \frac { \partial \log f \left( y _ { i } , \left( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \pmb { \gamma } _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T } \big | \pmb { h } _ { i } \right) } { \partial \pmb { \theta } _ { S _ { m } } }
$$

在 $\pmb { \theta } _ { 0 }$ 处 Taylor 展开,得

$$
\begin{array} { r c l } { ( 0 ) } & { = } & { \displaystyle \frac { 1 } { \sqrt { n } } \sum _ { i = 1 } ^ { n } \bigg [ \frac { \partial \log ( \frac { \partial \log ( \hat { \rho } _ { i } ( \hat { \rho } _ { i } , \hat { \rho } _ { i } ) ) } { \partial \theta _ { s } } ) } { \partial \theta _ { s } } \bigg ] } \\ & & { + ( \frac { \partial ^ { 2 } \log ( \frac { \partial \log ( \hat { \rho } _ { i } ( \hat { \rho } _ { i } , \hat { \rho } _ { i } ^ { \top } , \hat { \rho } _ { i } ^ { \top } ) ^ { T } ) } { \partial \theta _ { s } } ) } { \partial \theta _ { s } \partial \theta _ { s } ^ { 2 } } \frac { \partial ^ { 2 } \log ( \frac { \partial \log ( \hat { \rho } _ { i } ( \hat { \beta } _ { s } ^ { T } , \hat { \rho } _ { i } ^ { \top } ) ^ { T } ) } { \partial \theta _ { s } \partial \theta _ { s } } ) } { \partial \theta _ { s } \partial \theta _ { s } \partial \hat { \gamma } _ { s } ^ { T } } \bigg ] } \\ & & { \cdot ( ( \hat { \beta } _ { s n } - \beta ) ) ^ { \tau } , \ \langle \widetilde { \mathbf { r } } _ { s n } - \gamma _ { 0 n } , } \\ & { = } & { \displaystyle \frac { 1 } { \sqrt { n } } \sum _ { i = 1 } ^ { n } \bigg [ \frac { \partial \log ( f _ { 0 0 } , \hat { \theta } _ { 0 } , h _ { k + } ) } { \partial \theta _ { s } \partial _ { s } } + \frac { \partial ^ { 2 } \log ( \frac { \partial \log ( \hat { \rho } _ { k } ( \hat { \beta } _ { s } ^ { \top } , \hat { \rho } _ { k } ^ { \top } ) ^ { T } ) } { \partial \theta _ { s } \partial \theta _ { s } ^ { 2 } } | h _ { k }  } { \partial \theta _ { s } \partial \theta _ { s } ^ { 2 } } \bigg ] } \\ & & { \cdot ( ( \hat { \beta } _ { s n } - \beta ) ^ { \tau } , \ \langle \widetilde { \mathbf { r } } _ { s n } - \gamma _ { 0 n } , } \end{array}
$$

其中 $\left( \check { \beta } _ { 0 } ^ { T } , \check { \gamma } _ { 0 } ^ { T } \right) ^ { T }$ 位于 $\pmb { \theta } _ { 0 }$ 和 $\left( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T }$ 之间.因此

$$
\begin{array} { r l } & { \left( \sqrt { n } \left( \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } \right) \right. } \\ { \left. \sqrt { n } \left( \widehat { \gamma } _ { S _ { m } } - \gamma _ { 0 , S _ { m } } \right) \right) } \\ { = } & { \left( - \frac { 1 } { n } \displaystyle \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( y _ { i } , \left( \check { \beta } _ { 0 } ^ { T } , \check { \gamma } _ { 0 } ^ { T } \right) ^ { T } \big | h _ { i } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } \right) ^ { - 1 } } \end{array}
$$

$$
\begin{array} { c l } { \displaystyle } & { \displaystyle \cdot \sqrt { n } [ \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial \log f ( y _ { i } , \theta _ { 0 } | h _ { i } ) } { \partial \theta _ { S _ { m } } } + \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f ( y _ { i } , ( \tilde { \beta } _ { 0 } ^ { T } , \tilde { \gamma } _ { 0 } ^ { T } ) ^ { T } | h _ { i }  ) } { \partial \theta _ { S _ { m } } \partial \gamma ^ { T } } \delta ^ { \prime } ] } \\ { = } & { \displaystyle ( - \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f ( y _ { i } , ( \tilde { \beta } _ { 0 } ^ { T } , \tilde { \gamma } _ { 0 } ^ { T } ) ^ { T } | h _ { i }  ) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } ) ^ { - 1 } } \\ & { \displaystyle  \cdot \sqrt { n } [ \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \Gamma _ { m } \frac { \partial \log f ( y _ { i } , \theta _ { 0 } | h _ { i } ) } { \partial \theta } + \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f ( y _ { i } , ( \tilde { \beta } _ { 0 } ^ { T } , \tilde { \gamma } _ { 0 } ^ { T } ) ^ { T } | h _ { i }  ) } { \partial \theta _ { S _ { m } } \partial \gamma ^ { T } } \delta ^ { \prime } ] . } \end{array}
$$

再由 (6.8),可得

$$
\begin{array} { r l } & { \sqrt { n } \left\{ \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial \log f \left( y _ { i } , \pmb \theta _ { 0 } | { \boldsymbol h } _ { i } \right) } { \partial \pmb \theta } \right\} = \sqrt { n } \left( \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \partial \log f \left( y _ { i } , \pmb \theta _ { 0 } | { \boldsymbol h } _ { i } \right) / \partial \beta \right) } \\ { \doteq } & { \left( \displaystyle M _ { n } \right) = \frac { 1 } { \sigma ^ { 2 } } \sqrt { n } \frac { 1 } { n } \sum _ { i = 1 } ^ { n } e _ { i } \left( { \boldsymbol x } _ { i } ^ { _ { n } } \right) \sim \mathcal { N } ( 0 , { \boldsymbol J } _ { f u l l } | { \boldsymbol H } ) , } \end{array}
$$

$$
- \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \mathrm { l o g } f \left( y _ { i } , \left( \tilde { \beta } _ { 0 } ^ { T } , \tilde { \gamma } _ { 0 } ^ { T } \right) ^ { T } \big | h _ { i } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } = - \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \mathrm { l o g } f \left( y _ { i } , \left( \beta _ { 0 } ^ { T } , \gamma _ { 0 } ^ { T } \right) ^ { T } \big | h _ { i } \right) } { \partial \theta _ { S _ { m } } \partial \theta _ { S _ { m } } ^ { T } } = J _ { S _ { m } \mid H } ,
$$

$$
\frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial ^ { 2 } \log f \left( y _ { i } , \left( \breve { \beta } _ { 0 } ^ { T } , \breve { \gamma } _ { 0 } ^ { T } \right) ^ { T } \big | h _ { i } \right) } { \partial \theta _ { S _ { m } } \partial \gamma ^ { T } } \delta ^ { \prime } = \left( \begin{array} { c } { { - \frac { 1 } { \sigma ^ { 2 } } { \bf x } _ { i } z _ { i } ^ { T } } } \\ { { - \frac { 1 } { \sigma ^ { 2 } } \Gamma _ { m } z _ { i } z _ { i } ^ { T } } } \end{array} \right) \delta ^ { \prime } = \left( \begin{array} { c } { { J _ { 0 1 | H } } } \\ { { \Gamma _ { m } J _ { 1 1 | H } } } \end{array} \right) \delta ^ { \prime } = \left( \begin{array} { c } { { J _ { 1 1 | H } } } \\ { { J _ { 1 1 | H } } } \end{array} \right) .
$$

以及

$$
\begin{array} { r l } & { \sqrt { n } \left\{ \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \partial \log f \left( y _ { i } , \theta _ { 0 } | h _ { i } \right) } { \partial \theta _ { S _ { m } } } \right\} = \sqrt { n } \left( \frac { \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \partial \log f \left( y _ { i } , \theta _ { 0 } | h _ { i } \right) / \partial \beta } { \displaystyle \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \partial \log f \left( y _ { i } , \theta _ { 0 } | h _ { i } \right) / \partial \gamma _ { S _ { m } } } \right) } \\ { \doteq \ : } & { \left( \displaystyle \frac { M _ { n } } { N _ { n } ^ { m } } \right) \sim \mathcal { N } \left( 0 , { J } _ { S _ { m } | H } \right) . } \end{array}
$$

因此,将 (6.10)-(6.12)代入 (6.9)，可得

$$
\sqrt { n } \left( \begin{array} { c } { { \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } } } \\ { { \widehat { \gamma } _ { S _ { m } } - \gamma _ { 0 , S _ { m } } } } \end{array} \right) = J _ { S _ { m } | H } ^ { - 1 } \left\{ \left( \begin{array} { c } { { J _ { 0 1 | H } } } \\ { { \Gamma _ { m } J _ { 1 1 | H } } } \end{array} \right) \sqrt { n } \delta ^ { \prime } + \left( { \cal N } _ { n } ^ { m } \right) \right\}
$$

以及

$$
\sqrt { n } \left( \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } \right) = J _ { S _ { m } } ^ { - 1 } | H \left( \begin{array} { c } { J _ { 0 1 | H } } \\ { \Gamma _ { m } J _ { 1 1 | H } } \end{array} \right) \sqrt { n } \delta ^ { \prime } \sim \mathcal { N } \left( 0 , J _ { S _ { m } | H } ^ { - 1 } \right) .
$$

引理2的证明

记 $\pmb { \delta } _ { S _ { m } } ^ { \prime } = \left( \delta _ { i _ { 1 } } ^ { \prime } , \cdot \cdot \cdot , \delta _ { i _ { k _ { m } - q _ { 1 } } } ^ { \prime } \right) ^ { T }$ 和 $\pmb { \delta } _ { S _ { m } ^ { c } } ^ { \prime } = \left( \delta _ { i _ { k _ { m } - q _ { 1 } + 1 } } ^ { \prime } , \cdot \cdot \cdot , \delta _ { i _ { q _ { 2 } } } ^ { \prime } \right) ^ { T }$ 将 $\widehat { \mu } _ { m }$ 在 $\pmb { \theta } _ { 0 }$ 处 Taylor 展开得

$$
\widehat { \mu } _ { m } - \mu \left( \pmb { \theta } _ { 0 } \right) = \left\{ \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \beta } \right\} ^ { T } \left( \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } \right) + \left\{ \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \gamma _ { S _ { m } } } \right\} ^ { T } \left( \widehat { \gamma } _ { S _ { m } } - \gamma _ { 0 , S _ { m } } \right) - \left\{ \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \gamma } \right\} ^ { T } \delta ^ { \prime }
$$

$$
\begin{array} { r l } & { + \left( \widehat { \gamma } _ { S _ { m } } - \widehat { \beta } _ { 0 } - \beta _ { 0 } \right) ^ { T } \Pi _ { m } \left( \frac { \partial ^ { 2 } \mu ( \overline { { \theta } } _ { 0 } ) } { \partial \beta \partial \beta \overline { { \beta } } ^ { T } } \frac { \partial ^ { 2 } \mu ( \overline { { \theta } } _ { 0 } ) } { \partial \beta \partial \gamma ^ { T } } \right) \Pi _ { m } ^ { T } \left( \widehat { \gamma } _ { S _ { m } } - \gamma _ { 0 , S _ { m } } - \delta _ { S _ { m } } ^ { \prime } \right) , } \\ & { \quad \quad \quad - \delta _ { S _ { m } ^ { c } } ^ { \prime } } \end{array}
$$

其中 $\overline { { \pmb { \theta } } } _ { 0 }$ 位于 $\pmb { \theta } _ { 0 }$ 和 $\left( \widehat { \pmb { \theta } } _ { S _ { m } } ^ { T } , \widehat { \gamma } _ { S _ { m } } ^ { T } , \gamma _ { 0 , S _ { m } ^ { c } } ^ { T } \right) ^ { T }$ 之间.类似于(6.14)的证明，可得

$$
\sqrt { n } \left( \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } \right. \sqrt { n } \left( 0 , J _ { S _ { m } | H } ^ { - 1 } \right) \sim \mathcal { N } \left( 0 , J _ { S _ { m } | H } ^ { - 1 } \right) .
$$

当 $\mu$ 是参数 $\gamma$ 的线性函数时， $\begin{array} { r } { \frac { \partial ^ { 2 } \mu ( \overline { { \pmb { \theta } } } _ { 0 } ) } { \partial \gamma \partial \gamma ^ { T } } = 0 } \end{array}$ 又 $\begin{array} { r } { \frac { \partial ^ { 2 } \mu ( \overline { { \pmb { \theta } } } _ { 0 } ) } { \partial \beta \partial \beta ^ { T } } , \frac { \partial ^ { 2 } \mu ( \overline { { \pmb { \theta } } } _ { 0 } ) } { \partial \beta \partial \gamma ^ { T } } } \end{array}$ 以及 有界，结合（6.16)，得

$$
\begin{array} { r } { ( \widehat { \gamma } _ { S _ { m } } - \beta _ { 0 }  } \\ {  ( \widehat { \gamma } _ { S _ { m } } - \gamma _ { 0 } , S _ { m } - \delta _ { S _ { m } } ^ { \prime } ) ^ { T } \Pi _ { m } ( \frac { \partial ^ { 2 } \mu ( \overline { { \theta } } _ { 0 } ) } { \partial \beta \partial \beta ^ { T } } \frac { \partial ^ { 2 } \mu ( \overline { { \theta } } _ { 0 } ) } { \partial \beta \partial \overline { { \gamma } } ^ { T } } ) \Pi _ { m } ^ { T } ( \widehat { \gamma } _ { S _ { m } } - \gamma _ { 0 } , S _ { m } - \delta _ { S _ { m } } ^ { \prime } ) = O _ { p } ( \frac { 1 } { n } ) . } \\ { - \delta _ { S _ { m } ^ { c } } ^ { \prime } } \end{array}
$$

将(6.13)代入(6.15)，可得

$$
\begin{array} { r l } & { \sqrt { n } \left[ \left\{ \widehat { \mu } _ { m } - \mu \left( \pmb { \theta } _ { 0 } \right) \right\} + \left\{ \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \gamma } \right\} ^ { T } \delta ^ { \prime } - \left( \frac { \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \widehat { \beta } } } { \partial \gamma _ { S _ { m } } } \right) ^ { T } J _ { S _ { m } | H } ^ { - 1 } \left( \underbrace { J _ { 0 1 | H } } _ { \Gamma _ { m } J _ { 1 1 | H } } \right) \delta ^ { \prime } \right] } \\ { = } & { \left( \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \gamma _ { S _ { m } } } \right) ^ { T } \left[ \left( \sqrt { n } \left( \widehat { \beta } _ { S _ { m } } - \beta _ { 0 } \right) \right) - J _ { S _ { m } | H } ^ { - 1 } \left( \underbrace { J _ { 0 1 } } _ { \Gamma _ { m } J _ { 1 1 | H } } \right) \sqrt { n } \delta ^ { \prime } \right] } \\ { = } & { \left( \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \gamma _ { S _ { m } } } \right) ^ { T } \mathbf { J } _ { S _ { m } | H } ^ { - 1 } \left( \underbrace { M _ { n } } _ { N _ { n } ^ { m } } \right) + o _ { p } ( 1 ) \doteq \Lambda _ { m } + o _ { p } ( 1 ) . } \end{array}
$$

令 $W _ { n } = J ^ { 1 0 | H } M _ { n } + J ^ { 1 1 | H } N _ { n }$ ．由[1]中引理3.3的证明,同理可得

$$
\begin{array} { r l } & { \quad ( \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } ) ^ { T } \mathcal { F } _ { \phi _ { \phi } ^ { - 1 } , \phi _ { \phi } } ^ { \frac { 1 } { 2 } } ( \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } ) \delta ^ { - } - \{ \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } \} ^ { T } \delta ^ { \phi } } \\ { = } & { \quad ( \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } ) ^ { T } ( \int _ { 0 } ^ { \mathcal { R } _ { \phi ^ { - 1 } } \Delta \phi _ { \phi } } \int _ { 0 } ^ { 1 \sin \phi } ( \frac { \zeta _ { 2 , \phi _ { \phi } } } { \Gamma _ { 2 , \phi _ { \phi } } } ) \delta ^ { \phi } - \{ \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } \} ^ { T } \delta ^ { \phi }  } \\ { = } & { \quad  \{ \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } \} ^ { T } ( \int _ { 0 } ^ { \mathcal { R } _ { \phi ^ { - 1 } } \Delta \phi _ { \phi } } \int _ { 0 } ^ { 1 \sin \phi } ( \frac { \zeta _ { 2 , \phi _ { \phi } } } { \Gamma _ { 2 , \phi _ { \phi } } } ) ( \frac { \zeta _ { 2 , \phi _ { \phi } } } { \Gamma _ { 2 , \phi _ { \phi } } } ) \delta ^ { \phi }  } \\ & { \quad  + \{ \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } \} ^ { T } ( \int _ { 0 } ^ { \mathcal { R } _ { \phi ^ { - 1 } } \Delta \phi _ { \phi } } ( \mathcal { F } _ { \phi ^ { - 1 } } \delta ^ { 2 } ) \delta \frac { 1 } { \Gamma _ { \phi } } m _ { \phi } ( \phi _ { \phi } ) ) \delta ^ { \phi } - \{ \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } \} ^ { T } \delta ^ { \phi }  } \\ { = } &  \quad  \{ \frac { \partial \beta _ { \phi } ( \phi _ { \phi } ) } { \partial \phi _ { \phi } } \} ^ { T } ( \Gamma _ { \phi } ^ { \mu } \frac  \zeta _ { 2 , \phi } ^ { \mu } ( \phi _   \end{array}
$$

以及

$$
\begin{array} { r l r } { \Lambda _ { m } } & { { } = } & { \left( \begin{array} { c } { \frac { \partial \mu ( \pmb { \theta } _ { 0 } ) } { \partial \beta } } \\ { \frac { \partial \mu ( \pmb { \theta } _ { 0 } ) } { \partial \gamma _ { S _ { m } | H } } } \end{array} \right) ^ { T } J _ { S _ { m } | H } ^ { - 1 } \left( \begin{array} { c } { M _ { n } } \\ { N _ { n } ^ { m } } \end{array} \right) } \end{array}
$$

$$
\begin{array} { r l } { = } & { { } \left( \begin{array} { l } { \frac { \partial \mu \left( \theta _ { 0 } \right) } { \partial \beta } } \end{array} \right) ^ { T } \left( J ^ { 0 0 , m | H } \quad J ^ { 0 1 , m | H } \right) \left( \begin{array} { l } { M _ { n } } \\ { N _ { n } ^ { m } } \end{array} \right) } \\ { = } &  { } \left\{ \begin{array} { l l } { \frac { \partial \mu \left( \theta _ { 0 } \right) } { \partial \beta } \right\} ^ { T } \left( J ^ { 0 0 , m | H } M _ { n } + J ^ { 0 1 , m | H } N _ { n } ^ { m } \right) + \left\{ \frac { \partial \mu \left( \theta _ { 0 } \right) } { \partial \gamma _ { S _ { m } } } \right\} ^ { T } \left( J ^ { 1 0 , m | H } M _ { n } + J ^ { 1 1 , m | H } N _ { n } ^ { m } \right) } \end{array} \end{array}
$$

因此，我们可得到类似于1中引理3.3的结论：

$$
\begin{array} { l } { \displaystyle \sqrt { n } \left[ \left\{ \widehat { \mu } _ { m } - \mu \left( \pmb { \theta } _ { 0 } \right) \right\} - \omega _ { H } ^ { T } \left( \pmb { I } _ { q _ { 2 } } - K _ { H } ^ { 1 / 2 } V _ { m } K _ { H } ^ { - 1 / 2 } \right) \pmb { \delta } ^ { \prime } \right] } \\ { \displaystyle = \left\{ \frac { \partial \mu \left( \pmb { \theta } _ { 0 } \right) } { \partial \pmb { \beta } } \right\} ^ { T } J _ { 0 0 | H } ^ { - 1 } M _ { n } - \omega _ { H } ^ { T } K _ { H } ^ { 1 / 2 } V _ { m } K _ { H } ^ { - 1 / 2 } W _ { n } + o _ { p } ( 1 ) . } \end{array}
$$

# 定理1的证明

令 $I _ { \boldsymbol { q } _ { 2 } }$ 为 $q _ { 2 }$ 维单位矩阵.仿照(6.9)的证明可得

$$
\begin{array} { r c l } { { D _ { n } } } & { { = } } & { { \sqrt { n } ( \widehat { \gamma } _ { f u l l } - \gamma _ { 0 } ) } } \\ { { } } & { { } } & { { } } \\ { { } } & { { = } } & { { \left( { \bf 0 } _ { q _ { 2 } \times q _ { 1 } } { \quad \cal I } _ { q _ { 2 } } \right) J _ { f u l l | H } ^ { - 1 } \sqrt { n } \left\{ \left( { \small J _ { 0 1 | H } } \right) \delta ^ { \prime } + \left( { \small N _ { n } } \right) \right\} } } \end{array}
$$

以及

$$
D _ { n } - \sqrt { n } \delta ^ { \prime } = J ^ { 1 0 | H } M _ { n } + J ^ { 1 1 | H } N _ { n } = W _ { n } \sim { \mathcal { N } } ( 0 , K _ { H } ) .
$$

注意随机向量 $W _ { n }$ 和 $M _ { n }$ 是独立的．由于对所有候选模型 $\mid m \mid$ ，随机变量 $w _ { m } \left( D _ { n } \right)$ 和 $\widehat { \mu } _ { m }$ 可表示成同一随机向量 $\left( M _ { n } ^ { T } , N _ { n } ^ { T } \right) ^ { T }$ 的函数,并且 $w _ { m } \left( D _ { n } \right)$ 是 $D _ { n }$ 的连续函数，从而

$$
\begin{array} { r l } & { \sqrt { n } \left( \left\{ \displaystyle \sum _ { m = 1 } ^ { M } w _ { m } \left( D _ { n } \right) \widehat { \mu } _ { m } - \mu \left( \theta _ { 0 } \right) \right\} - \omega _ { H } ^ { T } \left[ I _ { q _ { 2 } } - K ^ { 1 / 2 } \left\{ \displaystyle \sum _ { m = 1 } ^ { M } w _ { m } \left( D _ { n } \right) H _ { m } \right\} K ^ { - 1 / 2 } \right] \delta ^ { \prime } \right) } \\ { = } & { \sqrt { n } \left[ \left\{ \displaystyle \sum _ { m = 1 } ^ { M } w _ { m } \left( D _ { n } \right) \widehat { \mu } _ { m } - \mu \left( \theta _ { 0 } \right) \right\} - \omega _ { H } ^ { T } \left\{ \delta ^ { \prime } - \widehat { \delta } \left( \delta ^ { \prime } \right) \right\} \right] } \\ { = } & { \left\{ \displaystyle \frac { \partial \mu \left( \theta _ { 0 } \right) } { \partial \beta } \right\} ^ { T } J _ { 0 0 \mid H } ^ { - 1 } M _ { n } - \omega _ { H } ^ { T } \widehat { \delta } ( W _ { n } ) + o _ { p } ( 1 ) \doteq \Lambda + o _ { p } ( 1 ) , } \end{array}
$$

$\begin{array} { r } { \widehat { \delta } ( W _ { n } ) = K ^ { 1 / 2 } \left\{ \sum _ { m = 1 } ^ { M } w _ { m } \left( W _ { n } \right) H _ { m } \right\} K ^ { - 1 / 2 } W _ { n } } \end{array}$ ，此外,无论是在固定参数设置还是在局部误设定假设下， $\Lambda$ 服从均值为0且方差为 $\Sigma$ 的正态分布,其中

$$
\Sigma = \left( \frac { \partial \mu } { \partial \pmb { \theta } } \right) ^ { T } J _ { 0 0 | H } ^ { - 1 } \frac { \partial \mu } { \partial \pmb { \theta } } + \omega _ { H } ^ { T } \mathrm { V a r } \widehat { \delta } ( W _ { n } ) \omega _ { H } .
$$

# 推论1的证明

由定理1的证明，可得

$$
\begin{array} { r l r } { T _ { n } } & { = } & { \frac { \sqrt { n } \left[ \widehat { \mu } \left( { \pmb w } \left( D _ { n } \right) \right) - \mu \left( \theta _ { 0 } \right) - \omega _ { H } ^ { T } \left\{ D _ { n } ^ { \prime } - \widehat { \delta } \left( D _ { n } ^ { \prime } \right) \right\} \right] } { \varphi _ { H } } } \\ & { = } & { \frac { \sqrt { n } \left[ \widehat { \mu } \left( { \pmb w } \left( D _ { n } \right) \right) - \mu \left( \theta _ { 0 } \right) \right] - \omega _ { H } ^ { T } \left\{ D _ { n } - \widehat { \delta } \left( D _ { n } \right) \right\} } { \varphi _ { H } } } \end{array}
$$

$$
\begin{array} { r l } { = } & { { } \frac { \sqrt { n } [ \widehat { \beta } ( w ( D _ { n } ) ) - \mu ( \theta _ { 0 } ) - \omega _ { H } ^ { T } \{ \delta ^ { \prime } - \widehat { \delta } ( \delta ^ { \prime } ) \} ] - \omega _ { H } ^ { T } ( D _ { n } - \sqrt { n } \delta ^ { \prime } ) + \omega _ { H } ^ { T } \{ \widehat { \delta } ( D _ { n } ) - \sqrt { n } \widehat { \delta } ( \delta ^ { \prime } ) \} } { \varphi _ { H } } } \\ { = } & { { } \frac { \{ \frac { \partial \mu ( \theta _ { 0 } ) } { \partial \beta } \} ^ { T } J _ { 0 0  H } ^ { - 1 } M _ { n } - \omega _ { H } ^ { T } W _ { n } } { \varphi _ { H } } + o _ { p } ( 1 ) = Z _ { H } + o _ { p } ( 1 ) , } \end{array}
$$

其中 $Z _ { H } \sim \mathcal { N } ( 0 , 1 )$

表1 在线性回归模型下,当 $\rho = 0 . 5$ 时， $9 5 \%$ 置信区间的覆盖率（CP(95)）和长度 $\left( \mathbf { L e n ( 9 5 ) } \right) ,$ (Table 1 Coverage Probability and Length of $9 5 \%$ confidence intervals (CP(95) and Len(95)): $\rho = 0 . 5$ ）  

<html><body><table><tr><td colspan="3"></td><td colspan="3">σ= 0.5</td><td colspan="3">σ=1</td><td colspan="3">σ = 1.5</td></tr><tr><td>n</td><td></td><td>方法</td><td>β</td><td>2</td><td>μ</td><td>β1</td><td>22</td><td>μ</td><td>β1</td><td>2</td><td>μ</td></tr><tr><td rowspan="6">50</td><td rowspan="5">CP(95)</td><td>SAIC</td><td>0.950</td><td>0.947</td><td>0.949</td><td>0.939</td><td>0.953</td><td>0.950</td><td>0.957</td><td>0.945</td><td>0.945</td></tr><tr><td>SBIC</td><td>0.950</td><td>0.947</td><td>0.949</td><td>0.939</td><td>0.953</td><td>0.950</td><td>0.957</td><td>0.945</td><td>0.945</td></tr><tr><td>MMA</td><td>0.950</td><td>0.947</td><td>0.949</td><td>0.939</td><td>0.953</td><td>0.950</td><td>0.957</td><td>0.945</td><td>0.945</td></tr><tr><td>SAIC</td><td>0.3413</td><td>0.3809</td><td>0.6319</td><td>0.6828</td><td>0.7676</td><td>1.2721</td><td>1.0259</td><td>1.1409</td><td>1.9238</td></tr><tr><td>Len(95) SBIC</td><td>0.3413</td><td>0.3809</td><td>0.6319</td><td>0.6828</td><td>0.7676</td><td>1.2721</td><td>1.0259</td><td>1.1409</td><td>1.9238</td></tr><tr><td></td><td>MMA</td><td>0.3413</td><td>0.3809</td><td>0.6319</td><td>0.6828</td><td>0.7676</td><td>1.2721</td><td>1.0259</td><td>1.1409</td><td>1.9238</td></tr><tr><td rowspan="6">100</td><td rowspan="5">CP(95)</td><td>SAIC</td><td>0.945</td><td>0.958</td><td>0.954</td><td>0.956</td><td>0.951</td><td>0.958</td><td>0.959</td><td>0.941</td><td>0.936</td></tr><tr><td>SBIC</td><td>0.945</td><td>0.958</td><td>0.954</td><td>0.956</td><td>0.951</td><td>0.958</td><td>0.959</td><td>0.941</td><td>0.936</td></tr><tr><td>MMA</td><td>0.945</td><td>0.958</td><td>0.954</td><td>0.956</td><td>0.951</td><td>0.958</td><td>0.959</td><td>0.941</td><td>0.936</td></tr><tr><td>SAIC</td><td>0.2322</td><td>0.2604</td><td>0.4350</td><td>0.4673</td><td>0.5233</td><td>0.8649</td><td>0.7008</td><td>0.7819</td><td>1.3102</td></tr><tr><td>Len(95) SBIC</td><td>0.2322</td><td>0.2604</td><td>0.4350</td><td>0.4673</td><td>0.5233</td><td>0.8649</td><td>0.7008</td><td>0.7819</td><td>1.3102</td></tr><tr><td></td><td>MMA</td><td>0.2322 0.2604</td><td>0.4350</td><td>0.4673</td><td>0.5233</td><td>0.8649</td><td>0.7008</td><td>0.7819</td><td>1.3102</td></tr><tr><td rowspan="6">200</td><td rowspan="4">CP(95)</td><td>SAIC</td><td>0.956</td><td>0.956</td><td>0.952</td><td>0.951</td><td>0.962</td><td>0.957</td><td>0.952</td><td>0.953</td><td>0.954</td></tr><tr><td>SBIC</td><td>0.956</td><td>0.956</td><td>0.952</td><td>0.951</td><td>0.962</td><td>0.957</td><td>0.952</td><td>0.953</td><td>0.954</td></tr><tr><td>MMA</td><td>0.956</td><td>0.956</td><td>0.952</td><td>0.951</td><td>0.962</td><td>0.957</td><td>0.952</td><td>0.953</td><td>0.954</td></tr><tr><td>SAIC</td><td>0.1622</td><td>0.1810</td><td>0.3031</td><td>0.3258</td><td>0.3629</td><td>0.6061</td><td>0.4867</td><td>0.5439</td><td>0.8947</td></tr><tr><td>Len(95)</td><td>SBIC</td><td>0.1622</td><td>0.1810 0.3031</td><td>0.3258</td><td>0.3629</td><td>0.6061</td><td>0.4867</td><td>0.5439</td><td></td><td>0.8947</td></tr><tr><td></td><td>MMA</td><td>0.1622</td><td>0.1810</td><td>0.3031</td><td>0.3258</td><td>0.3629</td><td>0.6061</td><td>0.4867</td><td>0.5439</td><td>0.8947</td></tr></table></body></html>

表2 在线性回归模型下,当 $\rho = 0 . 8$ 时， $9 5 \%$ 置信区间的覆盖率(CP(95）和长度Len(95)Table 2 Coverage Probability and Length of $9 5 \%$ confidence intervals (CP(95) and Len(95)): $\rho = 0 . 8 \dot { }$ ）  

<html><body><table><tr><td colspan="3"></td><td colspan="3">σ=0.5</td><td colspan="3">σ=1</td><td colspan="3">σ =1.5</td></tr><tr><td>n</td><td></td><td>方法</td><td>β</td><td>22</td><td>μ</td><td>β1</td><td>22</td><td>μ</td><td>β1</td><td>2</td><td>μ</td></tr><tr><td rowspan="6">50</td><td rowspan="5">CP(95)</td><td>SAIC</td><td>0.954</td><td>0.960</td><td>0.939</td><td>0.937</td><td>0.960</td><td>0.952</td><td>0.945</td><td>0.937</td><td>0.944</td></tr><tr><td>SBIC</td><td>0.954</td><td>0.960</td><td>0.939</td><td>0.937</td><td>0.960</td><td>0.952</td><td>0.945</td><td>0.937</td><td>0.944</td></tr><tr><td>MMA</td><td>0.954</td><td>0.960</td><td>0.939</td><td>0.937</td><td>0.960</td><td>0.952</td><td>0.945</td><td>0.937</td><td>0.944</td></tr><tr><td>SAIC</td><td>0.4933</td><td>0.6330</td><td>0.6312</td><td>0.9886</td><td>1.2614</td><td>1.2691</td><td>1.4685</td><td>1.8644</td><td>1.8739</td></tr><tr><td>SBIC</td><td>0.4933</td><td>0.6330</td><td>0.6312</td><td>0.9886</td><td>1.2614</td><td>1.2691</td><td>1.4685</td><td>1.8644</td><td>1.8739</td></tr><tr><td></td><td>MMA</td><td>0.4933</td><td>0.6330</td><td>0.6312</td><td>0.9886</td><td>1.2614</td><td>1.2691</td><td>1.4685</td><td>1.8644</td><td>1.8739</td></tr><tr><td rowspan="6">100</td><td rowspan="5">CP(95)</td><td>SAIC</td><td>0.945</td><td>0.942</td><td>0.946</td><td>0.951</td><td>0.952</td><td>0.958</td><td>0.946</td><td>0.942</td><td>0.933</td></tr><tr><td>SBIC</td><td>0.945</td><td>0.942</td><td>0.946</td><td>0.951</td><td>0.952</td><td>0.958</td><td>0.946</td><td>0.942</td><td>0.933</td></tr><tr><td>MMA</td><td>0.945</td><td>0.942</td><td>0.946</td><td>0.951</td><td>0.952</td><td>0.958</td><td>0.946</td><td>0.942</td><td>0.933</td></tr><tr><td>SAIC</td><td>0.3366</td><td>0.4289</td><td>0.4342</td><td>0.6746</td><td>0.8630</td><td>0.8672</td><td>1.0138</td><td>1.2902</td><td>1.3169</td></tr><tr><td>Len(95) SBIC</td><td>0.3366</td><td>0.4289</td><td>0.4342</td><td>0.6746</td><td>0.8630</td><td>0.8672</td><td>1.0138</td><td>1.2902</td><td>1.3169</td></tr><tr><td></td><td>MMA</td><td>0.3366</td><td>0.4289 0.4342</td><td>0.6746</td><td></td><td>0.8630</td><td>0.8672</td><td>1.0138</td><td>1.2902</td><td>1.3169</td></tr><tr><td rowspan="6">200</td><td rowspan="5">CP(95)</td><td>SAIC</td><td>0.954</td><td>0.946</td><td>0.943</td><td>0.944</td><td>0.948</td><td>0.943</td><td>0.956</td><td>0.952</td><td>0.950</td></tr><tr><td>SBIC</td><td>0.954</td><td>0.946</td><td>0.943</td><td>0.944</td><td>0.948</td><td>0.943</td><td>0.956</td><td>0.952</td><td>0.950</td></tr><tr><td>MMA</td><td>0.954</td><td>0.946</td><td>0.943</td><td>0.944</td><td>0.948</td><td>0.943</td><td>0.956</td><td>0.952</td><td>0.950</td></tr><tr><td>SAIC</td><td>0.2353</td><td>0.3006</td><td>0.3012</td><td>0.4674</td><td>0.5982</td><td>0.6045</td><td>0.7047</td><td>0.8973</td><td>0.8968</td></tr><tr><td>SBIC</td><td>0.2353</td><td>0.3006</td><td>0.3012</td><td>0.4674</td><td>0.5982</td><td>0.6045</td><td>0.7047</td><td>0.8973</td><td>0.8968</td></tr><tr><td></td><td>MMA</td><td>0.2353</td><td>0.3006</td><td>0.3012</td><td>0.4674</td><td>0.5982</td><td>0.6045</td><td>0.7047</td><td>0.8973</td><td>0.8968</td></tr></table></body></html>