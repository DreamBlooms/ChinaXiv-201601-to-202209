# 基于概率假设密度的近邻目标快速跟踪算法

王颖

(商丘职业技术学院 机电系，河南 商丘 476000)

摘要：针对杂波场景中多个目标相互近邻时，标准概率假设密度滤波器难以正确估计目标状态且计算复杂度高等问题，提出一种基于概率假设密度的近邻目标快速跟踪算法。所提算法首先采用自适应门技术从传感器观测集中划分出源于真实目标的观测集，随后利用真实目标观测集来更新预测强度，最后应用检测导向的近邻目标权重校正方法有选择地重分配各离散时刻后验强度中不精确的分量权重。实验结果表明，所提算法不仅具有高效率的目标跟踪，而且具有良好的鲁棒性。

关键词：近邻目标跟踪；概率假设密度；权重再分配；状态估计；计算效率 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2020.03.0049

Fast close-spaced target tracking algorithm based on probability hypothesis density

Wang Ying (Dept.ofMechanical&Electronic Engineering,Shangqiu Polytechnic,Shangqiu 476ooo,China)

Abstract:Takingaccountof the problems thatthestandard probabilityhypothesis density filteris dificult toestimate the target statecorrctlyandhashighcomputationalcomplexitywhenthereare multiple targets moveclose toeachothernclutter environments,this paperputs forwardafastclose-spacedtargetrackingalgorithmbasedontheprobabilityhypothesis density. The proposed algorithm firstuses anadaptive gate technologytodividethe measurementset originated fromtherealtargets fromthe sensor measurement set,and thenuses thereal target measurement set to update the predicted intensity.Finally,a detection-guided close-spaced targetreweight approach selectively redistributes the inaccurate component weights withinthe posteriorintensityateachdiscrete time.Experimentalresultsillustratethat theproposedalgorithmnotonlyhas target racking with high efficiency,but also has good stability.

Keywords:close-spaced targettracking; probabilityhypothesisdensity; weightredistribution;stateestimate;computingtime

# 0 引言

近年来，Mahler[1]采用点过程理论提出一种基于有限集统计学的多目标跟踪算法。基于有限集统计学框架的多目标Bayes滤波器具有较好的跟踪性能，然而该类滤波器的计算复杂度较高。针对该问题，文献[2]采用随机有限集和点过程理论提出了概率假设密度(PHD)滤波器。线性高斯噪声动态系统下，高斯混合PHD(GMPHD)给出了PHD 滤波器的一种闭合解[3]。

相较于大多数传统的数据关联滤波器[4-6]，PHD 滤波器无须显示的数据关联(即，观测与目标的关联)[7\~II]。针对杂波环境下目标检测和跟踪问题，Baisa等人[12]提出一种基于GMPHD的多类型多目标滤波(MTMTF)算法。通过采用目标分类更新策略，MTMTF算法克服了GMPHD滤波器更新步中不同类型目标观测的相互干扰。然而，当场景中同类型目标相互近邻时，MTMTF算法的目标状态及数目精度较低。标准Bayes框架下，Aoki等人[13]从理论上分析了杂波环境下的近邻目标身份识别和观测-目标间关联等问题，并且详细解释了近邻目标的标记互换现象。但是文献[13]仅仅从理论上给出了近邻目标身份不确定性的分析与证明，没有给出具体的实现。基于最大似然概率多假设方法，Schoenecker等人[14]提出一种非Bayes框架的多目标滤波器。该滤波器分析并验证了目标间距对近邻目标区分度的影响。多假设方法的引入使得该滤波器在强杂波场景中的计算量非常大，因此其迭代效率难以满足真实跟踪应用的需求。考虑目标估计精度和计算代价权衡下的多近邻目标跟踪，Zhang等人[15]提出一种权重再分配的GMPHD(WA-GMPHD)滤波器。通过迭代地对各滤波时刻目标权重进行惩罚式的多次更新，WA-GMPHD滤波器改善了标准GMPHD滤波器在跟踪近邻目标时的不足。尽管WA-GMPHD 滤波器的状态估计精度相对较高，但是该滤波器的计算效率仍相对较低。基于一种新的近邻目标分量融合方法,Nie 等人[16]提出一种改进的GMPHD(IPA-GMPHD)滤波器。通过利用目标的权重、均值及协方差，IPA-GMPHD滤波器一定程度上避免了近邻目标的分量错误融合，从而提高了近邻目标的跟踪精度。然而，密集杂波的近邻目标场景下IPA-GMPHD滤波器的状态估计精度相对较低，且其计算代价高。

针对上述近邻目标算法的状态估计精度低及计算代价高等问题，本文在GMPHD框架下提出一种近邻目标快速跟踪算法。该算法首先利用自适应门方法从观测集中筛选目标的真实观测，然后利用检测导向的近邻目标分量权重校正方法有选择地重分配后验强度中分量不精确的权重，最后经仿真实验验证了本文算法的有效性。

# 1 基于随机有限集的GMPHD滤波器

PHD滤波器将目标状态和传感器观测分别建模为有限集，即， $k$ 时刻目标状态集和观测集分别为 $X _ { k } = \{ x _ { k } ^ { 1 } , . . . , x _ { k } ^ { M _ { k } } \}$ 和$Z _ { k } = \{ z _ { k } ^ { 1 } , . . . , z _ { k } ^ { N _ { k } } \}$ ，其中 $\boldsymbol { M } _ { k }$ 和 ${ N } _ { k }$ 分别为目标数目和观测数目。PHD 滤波器是随机有限集多目标Bayes滤波器的一种近似方法。该滤波器在各时刻通过迭代地传递目标强度，从而实现目标的状态及数目估计。然而，PHD滤波器迭代过程中需要进行集合积分运算，因而无法直接求得闭合解。高斯白噪声的线性动态系统中，GMPHD滤波器为PHD滤波器提供了一种解析解。通过PHD滤波迭代，GMPHD滤波器采用高斯分量的加权和近似目标强度。GMPHD滤波器主要包括预测步和更新步。

预测步：假设 $k - 1$ 时刻后验强度的高斯混合为

$$
\upsilon _ { k - 1 | k - 1 } ( x ) = \sum _ { i = 1 } ^ { J _ { k - 1 | k - 1 } } w _ { k - 1 | k - 1 } ^ { i } \mathcal { N } ( x ; m _ { k - 1 | k - 1 } ^ { i } , P _ { k - 1 | k - 1 } ^ { i } )
$$

其中 $\mathcal { N } ( \because m , P )$ 为均值 $m$ 、协方差 $P$ 的高斯密度函数， $w _ { k - 1 | k - 1 } ^ { i }$ 为第 $i$ 个高斯分量的权重， $\boldsymbol { J } _ { k - 1 | k - 1 }$ 为高斯分量的数目。则 $k$ 时刻预测强度为

$$
\upsilon _ { k | k - 1 } ( x ) = p _ { s , k } \sum _ { i = 1 } ^ { J _ { k | k - 1 } } w _ { k - 1 | k - 1 } ^ { i } \mathcal { N } ( x ; m _ { k | k - 1 } ^ { i } , P _ { k | k - 1 } ^ { i } )
$$

$$
m _ { k | k - 1 } ^ { i } = F _ { k - 1 } m _ { k - 1 | k - 1 } ^ { i }
$$

$$
P _ { k | k - 1 } ^ { i } = F _ { k - 1 } P _ { k - 1 | k - 1 } ^ { i } F _ { k - 1 } ^ { T } + \mathcal { Q } _ { k - 1 }
$$

其中 $\boldsymbol { p } _ { s , k }$ 为存活概率， $F _ { k - 1 }$ 为状态转移矩阵， $\scriptstyle Q _ { k - 1 }$ 为状态噪声协方差矩阵。

更新步：基于预测强度 $v _ { k | k - 1 } ( x )$ 和观测集 $Z _ { k }$ ， $k$ 时刻后验强度为

$$
\upsilon _ { k | k } ( x ) = ( 1 - p _ { d , k } ) \upsilon _ { k | k - 1 } ( x ) + \sum _ { l = 1 } ^ { N _ { k } } \sum _ { i = 1 } ^ { J _ { k | k - 1 } } \upsilon _ { k | k } ^ { i , l } \mathcal { N } ( x ; m _ { k | k } ^ { i , l } , P _ { k | k } ^ { i } )
$$

其中等式右侧第一项为目标漏检项，第二项为观测更新项，$p _ { d , k }$ 为检测概率，权重 $w _ { k | k } ^ { i , l }$ 、均值 $m _ { k | k } ^ { i , l }$ 和协方差矩阵 $P _ { k | k } ^ { i , l }$ 分别为

$$
w _ { k | k } ^ { i , l } = \frac { p _ { d , k } w _ { k | k - 1 } ^ { i } q _ { k } ^ { i } ( z _ { k } ^ { l } ) } { \displaystyle { K _ { k } ( z _ { k } ^ { l } ) + p _ { d , k } \sum _ { j = 1 } ^ { J _ { k | k - 1 } } w _ { k | k - 1 } ^ { j } q _ { k } ^ { j } ( z _ { k } ^ { l } ) } }
$$

$$
q _ { k } ^ { i } ( z _ { k } ^ { l } ) = \mathcal { N } ( z _ { k } ^ { l } ; H _ { k } m _ { k | k - 1 } ^ { i } , H _ { k } P _ { k | k - 1 } ^ { i } H _ { k } ^ { T } + R _ { k } )
$$

$$
m _ { k | k } ^ { i , l } = m _ { k | k - 1 } ^ { i } + K _ { k } ^ { i } ( z _ { k } ^ { l } - H _ { k } m _ { k | k - 1 } ^ { i } )
$$

$$
P _ { k | k } ^ { i } = [ I - K _ { k } ^ { i } H _ { k } ] P _ { k | k - 1 } ^ { i }
$$

$$
K _ { k } ^ { i } = P _ { k | k - 1 } ^ { i } H _ { k } ^ { \tau } ( H _ { k } P _ { k | k - 1 } ^ { i } H _ { k } ^ { \tau } + R _ { k } ) ^ { - 1 }
$$

其中 $I$ 为单位矩阵， $\mathcal { K } _ { k } \left( \cdot \right)$ 为杂波强度， $H _ { k }$ 为观测矩阵， $R _ { k }$ 为观测噪声协方差矩阵。

# 2 近邻目标快速GMPHD跟踪算法

# 2.1基于自适应门方法的观测集划分

杂波干扰的目标跟踪场景下，每一时刻由传感器获取的观测集中包括目标观测和杂波。杂波不仅降低了GMPHD滤波器后验强度的精度，而且加重了滤波器的迭代负担。本文采用一种基于自适应门的目标观测划分方法，从观测集 $Z _ { k }$ 中分离出源于真实目标的观测，以降低杂波在迭代过程中的数目。

$k$ 时刻，预测强度 $\upsilon _ { k | k - 1 } ( x )$ 由式(2)表示。基于自适应门的目标观测划分方法将传感器观测集 $Z _ { k } = \{ z _ { k } ^ { 1 } , . . . , z _ { k } ^ { N _ { k } } \}$ 划分为目标观测集 $Z _ { r e a l , k }$ 和杂波集，其中目标观测集 $Z _ { r e a l , k }$ 为

$$
{ \cal Z } _ { r e a l , k } = \{ z _ { k } ^ { j } \mid f _ { d i s } ( x _ { k | k - 1 } ^ { i } , z _ { k } ^ { j } ) \leq ( \alpha + w _ { k | k - 1 } ^ { i } ) \eta _ { t h } , z _ { k } ^ { j } \in { \cal Z } _ { k } \}
$$

$$
f _ { d i s } ( x _ { k | k - 1 } ^ { i } , { z _ { k } ^ { j } } ) = ( z _ { k } ^ { j } - H _ { k } m _ { k | k - 1 } ^ { i } ) ^ { T } { \zeta ^ { - 1 } } ( z _ { k } ^ { j } - H _ { k } m _ { k | k - 1 } ^ { i } )
$$

$$
\zeta = H _ { k } P _ { k | k - 1 } ^ { i } H _ { k } ^ { T } + R _ { k }
$$

其中 $\eta _ { { \scriptscriptstyle t h } }$ 为经验门阈值， $\alpha$ 为调节因子， $\boldsymbol { w _ { k | k - 1 } ^ { i } } = \boldsymbol { p _ { s , k } } \boldsymbol { w _ { k - 1 | k - 1 } ^ { i } }$ 。

从式(11)可见，不等式右侧的上限值 $( \alpha + w _ { k | k - 1 } ^ { i } ) \eta _ { t h }$ 随着权重$w _ { k | k - 1 } ^ { i }$ 和 $\alpha$ 的变化而自动缩放。即不同分量在关联其对应观测时所对应的阈值是不同的。基于自适应门的目标观测划分方法可以较大程度地改善由经验门阈值方法导致的观测丢失现象

# 2.2检测导向的近邻目标分量权重校正

$k$ 时刻，基于预测强度 $\upsilon _ { k | k - 1 } ( x )$ 和目标观测集 $Z _ { r e a l , k }$ ，后验强度 $\upsilon _ { k | k } \left( x \right)$ 由式(5)计算得出。由于 $Z _ { r e a l , k }$ 几乎仅含有源于目标的观测，因此后验强度 $\upsilon _ { k \left| k \right. } ( x )$ 的精度相对较高。近邻目标场景下，源于多个近邻目标的观测同样也彼此相邻，因此源于不同目标的多个观测可能会趋近于多个近邻目标的某一个。基于真实跟踪场景中观测来源不确定假设和GMPHD滤波器的预测强度更新规则，式(5)表示的后验强度 $\upsilon _ { k | k } \left( x \right)$ 中部分高斯分量权重 $\boldsymbol { w _ { k | k } ^ { i } }$ 不正确，即后验强度 $\upsilon _ { k \left| k \right. } ( x )$ 的精度较低，最终目标状态难以从后验强度 $\upsilon _ { k | k } ( x )$ 中正确地估计。

通过对后验强度 $\upsilon _ { k | k } \left( x \right)$ 中高斯分量的权重进行再分配，WA-GMPHD滤波器提高了近邻目标的状态估计精度。密集杂波的近邻目标场景下，WA-GMPHD滤波器在各时刻几乎均需要对高斯分量的权重进行校正，因而该滤波器的计算代价较高。此外，WA-GMPHD滤波器在重分配高斯分量的权重时利用当前时刻分量权重为依据选择待校正高斯分量，一定程度上不能正确反映高斯分量与其真实对应观测间的关系因此该滤波器的目标状态估计精度相对不高。

针对WA-GMPHD滤波器在跟踪近邻目标时存在的上述两点不足，本文提出一种基于检测导向的近邻目标分量权重校正方法。各滤波时刻高斯分量的权重是否需要重分配通过一种检测策略来确定。如果经检测需要重新分配，则采用近邻目标分量权重校正策略对高斯分量的权重进行重分配，否则，后验强度中高斯分量的权重不做调整。

$k$ 时刻，基于预测强度 $\upsilon _ { k | k - 1 } ( x )$ 和目标观测集 $Z _ { r e a l , k } = \{ z _ { k } ^ { l }$ }=1， 后验强度 $\upsilon _ { k | k } ( x )$ 中状态 $x _ { k | k } ^ { i , l }$ 的高斯分量的权重 $w _ { k | k } ^ { i , l }$ 可由式(6)计 算，且其非归一化权重 $\tilde { w } _ { k | k } ^ { i , l }$ 为

$$
\tilde { w } _ { k | k } ^ { i , l } = p _ { d , k } w _ { k | k - 1 } ^ { i } \mathcal { N } ( z _ { k } ^ { l } ; H _ { k } m _ { k | k - 1 } ^ { i } , H _ { k } P _ { k | k - 1 } ^ { i } H _ { k } ^ { T } + R _ { k } )
$$

基于 $J _ { \boldsymbol { k } | \boldsymbol { k } - 1 } \times \boldsymbol { n } _ { \boldsymbol { r } , \boldsymbol { k } }$ 个权重 $w _ { k | k } ^ { i , l }$ 和非归一化权重 $\tilde { w } _ { k | k } ^ { i , l }$ ，与后验强度$\upsilon _ { k \left| k \right. } ( x )$ 中所有高斯分量相对应的权重矩阵 $\chi$ 和非归一化权重矩阵 $\tilde { \chi }$ 分别表示为

$$
\mathcal { X } = \left[ \begin{array} { c c c } { w _ { k | k } ^ { 1 , 1 } } & { \cdots } & { w _ { k | k } ^ { 1 , l } } \\ { \vdots } & { \ddots } & { \vdots } \\ { w _ { k | k } ^ { i , 1 } } & { \cdots } & { w _ { k | k } ^ { i , l } } \end{array} \right] _ { J _ { k | k - 1 } \times n _ { r , k } } , \tilde { \chi } = \left[ \begin{array} { c c c } { \tilde { w } _ { k | k } ^ { 1 , 1 } } & { \cdots } & { \tilde { w } _ { k | k } ^ { 1 , l } } \\ { \vdots } & { \ddots } & { \vdots } \\ { \tilde { w } _ { k | k } ^ { i , 1 } } & { \cdots } & { \tilde { w } _ { k | k } ^ { i , l } } \end{array} \right] _ { J _ { k | k - 1 } \times n _ { r , k } }
$$

后验强度 $\upsilon _ { k | k } \left( x \right)$ 中高斯分量的权重是否需要重新分配可由式(16)来检测。

$$
f _ { r e d } = \left\{ { \begin{array} { l } { t r u e \ , \ \left( f _ { c o u } ( \aleph ( x _ { k | k } ^ { i } ) ) > 1 \right) o r \left( f _ { c o u } ( \aleph ( x _ { k | k } ^ { i } ) ) = 0 \right) } \\ { f a l s e , \ } \end{array} } \right. \ \qquad \nexists \nrightarrow { \xrightarrow { \infty } } \ \qquad 
$$

其中 $f _ { r e d } = t r u e$ 表示高斯分量的权重需要重分配， $f _ { r e d } = f a l s e$ 表示高斯分量的权重无须重分配， $f _ { c o u }$ 为统计集合元素数目函数， $\aleph ( x _ { k \left| k \right. } ^ { i } )$ 表示状态 $x _ { k | k } ^ { i , l } ( \forall l = 1 ; n _ { r , k } )$ 的高斯分量的权重超过状态抽取阈值 $\omega _ { { t h } }$ [3]的分量索引集。

当 $f _ { r e d }$ 为true时，后验强度 $\upsilon _ { k | k } \left( x \right)$ 中高斯分量的权重需要进行重分配。初始化集合 $\beta = \{ 1 , . . . , J _ { k | k - 1 } \}$ ，高斯分量权重的重分配详细步骤如下：

a）从后验强度 $\upsilon _ { k | k } \left( x \right)$ 中检索权重最大的高斯分量，其权重在权重矩阵 $\chi$ 中的索引为

$$
\langle i _ { m p i } , l _ { m p i } \rangle = \underset { i \in \beta a n d \forall l = 1 : n _ { r , k } } { \arg \operatorname* { m a x } } ( w _ { k | k } ^ { i , l } )
$$

b)如果权重和 $\sum _ { l = 1 } ^ { n _ { r , k } } w _ { k | k } ^ { i _ { n p } , l }$ 不超过1,状态 $x _ { k | k } ^ { i _ { m p i } , l } ( \forall l = 1 : n _ { r , k } )$ 的高斯分量的权重无须校正，转到步骤(6)；否则状态 $x _ { k | k } ^ { i _ { w n i } , l } ( \forall l = 1 ; n _ { r , k } )$ 的高斯分量的权重需要重新分配。

c）计算状态 $x _ { k | k } ^ { i _ { m n } , l } ( \forall l = 1 : n _ { r , k } )$ 的高斯分量与该分量在 $k - 1$ 时刻所属目标 $T _ { k - 1 } ( x _ { k | k } ^ { i _ { w p i } } )$ 的距离，检索具有最小距离值的高斯分量，其索引为

$$
\begin{array} { r } { \big \langle i _ { m p i } , l _ { m p i } ^ { * } \big \rangle = \underset { \forall l = 1 : n _ { r , k } } { \arg \operatorname* { m i n } } ( d _ { k } ( x _ { k | k } ^ { i _ { m p i } , l } , X _ { k - 1 } ( x _ { k | k } ^ { i _ { m p i } } ) ) ) } \end{array}
$$

其中 $X _ { k - 1 } ( x _ { k | k } ^ { i _ { m p i } } )$ 表示 $k - 1$ 时刻目标 $T _ { k - 1 } ( \boldsymbol { x } _ { k | k } ^ { i _ { w p i } } )$ 的状态， $d _ { k } ( x _ { k | k } ^ { i _ { w p i } , l } , X _ { k - 1 } ( x _ { k | k } ^ { i _ { w p i } } ) )$ 表示状态 $x _ { k | k } ^ { i _ { \mathrm { w p i } } , l }$ 和 $X _ { k - 1 } ( x _ { k | k } ^ { i _ { m y s } } )$ 间的欧氏距离。

更新索引为

$$
\langle i _ { m p i } , l _ { m p i } \rangle = \left\{ \begin{array} { c c } { \langle i _ { m p i } , l _ { m p i } \rangle , } & { w _ { k | k } ^ { i _ { m p i } , l _ { m p i } } > \omega _ { t h } } \\ { \langle i _ { m p i } , l _ { m p i } ^ { * } \rangle , } & { \sharp \sharp ^ { \prime } \sharp } \end{array} \right.
$$

d）状态 ${ x _ { k \parallel k } ^ { i _ { m p i } , l } } ( \forall l = 1 ; n _ { r , k } , l \neq l _ { m p i } )$ 的高斯分量在非归一化权重矩 阵 $\tilde { \chi }$ 的权重更新为

$$
\tilde { w } _ { n e w , k | k } ^ { i _ { n p i } , l } = \tilde { w } _ { k | k } ^ { i _ { n p i } , l } \times \rho ^ { i _ { n p i } }
$$

其中惩罚系数 $\rho ^ { i _ { n p i } } = 1 - w _ { k | k } ^ { i _ { n p i } , l _ { n p i } }$ 。

状态 $x _ { k | k } ^ { i , l } ( \forall l = 1 ; n _ { r , k } , l \neq l _ { m p i } )$ 的高斯分量在权重矩阵 $\chi$ 的权重更新为

$$
w _ { n e w , k | k } ^ { i , l } = \left\{ \begin{array} { c c } { \displaystyle \frac { 1 } { \mathcal { H } } \times \tilde { w } _ { k | k } ^ { i _ { m n } , l } \times \rho ^ { i _ { m p i } } , } & { i = i _ { m p i } } \\ { \displaystyle \frac { 1 } { \mathcal { H } } \times \tilde { w } _ { k | k } ^ { i , l } } & { , \ : \ : \forall i = 1 : J _ { k | k - 1 } , i \neq i _ { m p i } } \end{array} \right.
$$

其中归一化因子 $\mathcal { H }$ 为

$$
\mathcal { H } = { \cal { K } } _ { k } ( z _ { k } ^ { l } ) + \tilde { w } _ { k | k } ^ { i _ { m p i } , l } \times \rho ^ { i _ { m p i } } + \sum _ { j = 1 , j \neq i _ { m p i } } ^ { J _ { k | k - 1 } } \tilde { w } _ { k | k } ^ { j , l }
$$

e）如果权重和 $\sum _ { l = 1 } ^ { n _ { r , k } } w _ { k | k } ^ { i _ { n p l } , l }$ 不超过1，转到步骤f）；否者，转到步骤d）。

f)更新集合 $\beta$ ，即从集合 $\beta$ 中删除 $i _ { m p i }$ 。

g）如果 $\beta$ 为空，近邻目标分量权重校正过程结束，否则，转到步骤a）。

备注：高斯分量合并方法。基于GMPHD滤波器的分量融合方法[3]，将 $k$ 时刻后验强度 $\upsilon _ { k \left| k \right. } ( x )$ 中属于第 $i$ 个高斯分量(其状态为 $x _ { k | k } ^ { i } ( \forall i = 1 \colon J _ { k | k - 1 } )$ )的 $n _ { r , k } + 1$ 子分量(状态 $x _ { k | k } ^ { i , l } \left( \forall l = 0 : n _ { r , k } \right)$ 的高斯分量)按照各子分量的权重加权融合为一个状态为$\tilde { x } _ { k | k } ^ { i } \big ( \forall i = 1 : J _ { k | k - 1 } \big )$ 的高斯分量，其中状态 $x _ { k | k } ^ { i , l } ( l = 0 )$ 的高斯分量为式(5)中目标漏检项中与状态 $\boldsymbol { x } _ { \boldsymbol { k } | \boldsymbol { k } - 1 } ^ { i }$ 的高斯分量相对应的漏检分量。

# 3 仿真实验

实验场景为一个 $[ 0 m , 7 0 0 m ] \times [ 0 m , 7 0 0 m ]$ 二维监视区域。该区域中含有3个真实目标，其中3个目标在第 35时刻相互接近。图1给出了实验场景的60秒仿真示意，其中杂波数目服从均值为5的均匀分布。检测概率 $p _ { d , k } = 0 . 9 9$ ，存活概率$p _ { s , k } = 0 . 9 9$ ，采样间隔为1秒，状态抽取阈值 $\omega _ { t h } = 0 . 5$ ，调节因子 $\alpha = 1$ 。状态噪声服从零均值、标准差为0.5的高斯分布，观测噪声服从零均值、标准差为25的高斯分布。

基于OSPA距离[17]、运算时间和权重再分配概率三个指标，本文算法分别与WA-GMPHD[15]和IPA-GMPHD[16]滤波器进行对比，其中OSPA距离的两个参数分别为 $p = 2$ 和$c = 1 0 0$ 。较小的OSPA距离表示目标状态估计精度相对较高，反之亦然[17]。所有实验结果均为1000次Monte-Carlo仿真的平均值。

图2为1000次Monte-Carlo实验的OSPA距离、运算时间和权重再分配概率结果。仅采用分量合并策略的IPA-GMPHD滤波器难以完全解决近邻目标的高斯分量合并问题，因此该滤波器的OSPA距离较大，且所需运算时间较多。由于无须高斯分量权重再分配，该滤波器的权重再分配概率为零。当目标间的距离较大时，WA-GMPHD滤波器和本文算法的OSPA距离几乎相同。然而，当目标相互接近时，WA-GMPHD滤波器的OSPA距离要远大于本文算法的OSPA距离。与WA-GMPHD滤波器相比，本文算法的运算时间和权重再分配概率均较低。较小的权重再分配概率使得本文算法的运算时间较小。本文算法良好滤波性能的原因是：通过应用检测导向的近邻目标分量权重校正策略和观测划分方法，本文算法能够有选择地校正各时刻高斯分量的权重以获得高精度的后验强度。

700 业 专 中 长 \* 养茶 专 ↓ 专 号 中 \* \* \* \* 600 = 专 常 1 中 A 市 养 中 专 秘 500 专 专 \* \* 茶 张 水 1 m400 \* 心 \* 星 美 等 心 M 长 200 专 市 茶 水茶 3 中 2 多 米 长 中 100 款 专 5 中 等 专 中 疗 学茶 专 \* \* \* 张张 \* 专 \* \* 05 ， C 专 0 100 200 300 400 500 600 70C 方向 (m)

图3为三种滤波器在不同杂波均值场景下的结果对比。IPA-GMPHD滤波器的OSPA距离和运算时间受杂波数目的影响明显。尽管WA-GMPHD滤波器的OSPA距离随杂波数目的增多有一定的提高，但是杂波数目的逐渐增多使得WA-GMPHD滤波器的权重再分配概率不断增大，因而该滤波器的运算时间不断增多。由于本文算法的权重再分配概率不受杂波数目的干扰，因此本文算法的运算时间在各杂波数目处相似。与WA-GMPHD滤波器相比，本文算法的OSPA距离总体上较小，表明本文算法的目标状态估计精度受杂波数目变化的影响相对较小。

图4为检测概率对各滤波器性能影响的结果对比，其中杂波均值为10。相较于WA-GMPHD和IPA-GMPHD滤波器，本文算法在各个检测概率处均具有较小的OSPA距离和较少的运算时间。同时，随着检测概率的提高，本文算法的权重再分配概率不断得以改善。较低检测概率使得近邻目标场景中的目标观测来源更加难以分辨，因此WA-GMPHD滤波器的权重再分配概率很大。即WA-GMPHD滤波器需要更频繁地重分配后验强度中高斯分量的权重。这也使得该滤波器的运算时间相对较多。

![](images/6295c9de255359f3bacfc6892732ffa0b3f14259e6c07586d829e9fea7c3bf19.jpg)  
图1目标轨迹和观测  
Fig.1Target tracks and measurements   
图2各滤波器Monte-Carlo 结果对比  
Fig.2Comparison ofMonte-Carlo result of each filter

![](images/c11b6a251f7ed1d39597dbdf70f6ebb945215633650d01d183202ffa9f0d4ae1.jpg)  
Fig.3Comparison of the influence of clutter mean on the performance of each filter

![](images/2a870f466f950d8ad906d5a21f72644815bcab26a724a4b92dcb93f67240a971.jpg)  
图3杂波均值对各滤波器性能影响对比  
图4检测概率对各滤波器性能影响对比  
Fig.4Comparison of the influence of detection probability on the performance of each filter

# 4 结束语

本文提出一种近邻目标快速PHD 跟踪算法以解决标准PHD滤波器难以有效地跟踪近邻目标问题。通过自适应门观测划分方法和检测导向的近邻目标分量权重校正方法，本文算法有选择地重分配各滤波时刻后验强度中高斯分量的权重，一定程度上缓解了近邻目标跟踪环境下高斯分量权重误更新问题，改善了高精度后验强度和低计算代价间的矛盾。实验表明，本文算法具有较好的跟踪性能(目标状态估计精度高和运算时间少)，是一种良好的和鲁棒的基于状态估计精度和计算负担相均衡的近邻多目标PHD跟踪算法。

# 参考文献：

[1]Mahler R. Statistical multisource-multitarget information fusion [M]. Norwood,MA:ArtechHouse,2007:483-531.   
[2]Mahler R.Multi-target Bayes filtering via first-order multi-target moments [J].IEEE Trans on Aerospace and Electronic Systems,2003, 39 (4): 1152-1178.   
[3]Vo B N,Ma WK.The Gaussian mixture probability hypothesis density filter [J].IEEE Trans on Signal Processing,2006,54(11): 4096-4104.   
[4]刘昀晓，王东峰，曹林，等．基于车辆数据的k近邻联合概率数据关 联算法[J]．电讯技术，2020,60(4):448-454.(Liu Yunxiao,Wang Dongfeng,Cao Lin,et al.Ak nearest neighbor-joint probability data association algorithm based on vehicle data [J].Telecommunication Engineering,2020,60 (4):448-454.)   
[5]Sheng Hao,Chen Jiahui, Zhang Yang,et al. Iterative multiple hypothesis tracking with tracklet-level association [J].IEEE Trans on Circuits and Systems for Video Technology,2019,29 (12):3660-3672.   
[6]Xie Yifan,Huang Yuan, Song TL.Iterative joint integrated probabilistic data association filter for multiple-detection multiple-target tracking [J].

Digital Signal Processing,2018 (72):232-243.

[7] 洪磊，陈树新，吴昊，等．一种学生t混合粒子实现的概率假设密度 滤波器[J/OL]．计算机应用研究．(2019-09-25）[2020-02-26]. https://doi.0rg/10.19734/j.issn.1001-3 695.2018.11.0905.(Hong Lei, Chen Shuxin,Wu Hao,et al. Student's t particle implementations of probability hypothesis density filters [J/OL].Application Research of Computers.(2019-09-25)[2020-02-26].https://doi.org/10.19734/j.issn. 1001-3 695.2018.11.0905.)   
[8]Hu Qi,Ji Hongbing,Zhang Yongquan.A standard PHD filter for joint tracking and classification of maneuvering extended targets using random matrix[J]. Signal Processing,2018 (144): 352-363.   
[9]Garcia F,Prioleti A,CerriP,et al.PHD filter for vehicle tracking based on a monocular camera[J].Expert Systems with Applications,2018 (91): 472-479.   
[10] JorqueraF,Hernandez S,Vergara D.Probability hypothesis density filter using determinantal point processes for multi object tracking [J]. Computer Vision and Image Understanding,2019 (183): 33-41.   
[11]程轩，宋骊平，姬红兵，邹志彬．标签箱粒子概率假设密度群目标 跟踪算法[J]．系统工程与电子技术,2019,41(8):1677-1685.(Cheng Xuan,Song Liping,Ji Hongbing,et al.Group target tracking algorithm based on labeled box particle probability hypothesis density [J].Systems Engineering and Electronics,2019,41(8):1677-1685.)   
[12] Baisa NL,Wallace A.Multiple target, multiple type filtering in the RFS framework [J].Digital Signal Processing,2019 (89): 49-59.   
[13]Aoki EH,Mandal PK,Svensson L,et al.Labeling uncertainty in multitarget tracking [J].IEEE Trans on Aerospace and Electronic Systems,2016,52(3):1006-1020.   
[14] Schoenecker S,Willett P,Bar-Shalom Y.Resolution limits for tracking closely spaced targets [J].IEEE Trans on Aerospace and Electronic Systems,2018,54(6):2900-2910.   
[15] Zhang Huanqing,Ge Hongwei,Yang Jinlong，et al.A GM-PHD algorithm for multiple target tracking based on false alarm detection with irregular window [J].Signal Processing,2016 (120): 537-552.   
[16] Nie Yongfang,Zhang Tao.Improved pruning algorithm for Gaussian mixture probability hypothesis density filter [J].Journal of Systems

Engineering and Electronics,2018,29 (2): 229-235. [17] Schuhmacher D,Vo B T,Vo B N.A consistent metric for performance evaluation of multi-object filters [J].IEEE Trans on Signal Processing, 2008,56(8):3447-3457.