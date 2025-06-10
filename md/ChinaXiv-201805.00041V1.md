# 基于属性散射信息的随机梯度最小方差追踪SAR超分辨重建算法

丛迅超1，万群²

(1．中国电子科技集团公司第十研究所，成都 610036;2.电子科技大学 电子工程学院，成都 6117312)

摘要：无论军事还是民用合成孔径雷达（SAR）应用领域，对实现目标更高分辨、更精细描述的期望和需求都十分迫切。在稀疏表示框架下，构建了基于属性散射中心模型（ASC）部件级局部散射模型的SAR重建观测模型；提出一种基于信号域的散射中心属性参数空间分类策略，并联合频域外推，提出一种基于随机梯度最小方差追踪的部件级超分辨 SAR重建算法。该算法最终的超分辨 SAR图像由FFT获得，提高了算法效率；并且该算法实现了在重建超分辨SAR 图像的同时获取高精度的目标散射中心属性级特征。仿真合成数据和电磁计算数据验证了算法的超分辨能力，并利用ASC属性的克拉美罗界对算法属性估计性能进行了评估。

关键词：合成孔径雷达；属性散射中心模型；稀疏表示；频域外推中图分类号：TN911.73

# Superresolution SAR reconstruction algorithmusing stochastic gradient minimum variance pursuit with attributed scattering priors

Cong Xunchao1, Wan Qun² (1.The10th Research InstitutionofChinaElectronicsTechnologyGroupCorporation,Chengdu610036,China;2.Shoolof Electronic Engineering,UniversityofElectronic Science&TechnologyofChina,Chengdu 611731,China)

Abstract:Theapplications inboth themilitaryandcivilfeldhave presing needsand great expectationsofachievingthetarget higheresolutionand moredetaileddescriptio.This paperfirstlymodeledtheobject-levelSARobservationsbasedonatributed scattering center (ASC)model insparserepresentation framework.Secondly,it proposedaclassifying strategyof thetarget attributespacefortheobject-levelreconstruction in signal domain.Combined with data extrapolating,then it proposeda stochastic gradient minimum variance pursuit (SGMVP)basedobject-level super-resolutionreconstructionalgorithm.It finally achievedsuper-resolutionimagebyFFTtoefectively promotetheeficiencyoftheproposedalgorithm.Theproposedalgorithm notonlycanachieve improved superrsolution image but alsoprovide accurate physically-relevant attibuted features of the scaterers simultaneously. Experimental results confirm the effectiveness of the proposed algorithm.

Key Words:syntheticaperture radar(SAR);atributed scatering center(ASC) model; sparserepresentation；spectrum extrapolation

# 0 引言

传统的SAR目标重建技术往往建立在理想点目标假设下，而目标的散射中心实际来自现实世界中目标的散射部件。最近几年，越来越多的文献开始研究SAR回波中目标的非理想散射特征，并指出在SAR重建过程中引入目标各向异性散射信息和色散散射信息可有效提高重建性能。Fasoula等人[1,2]将方位观测孔径等大小的划分成多个子孔径，并联合子孔径进行各向异性散射检测，各子孔径重建的SAR图像非相干叠加构成最终SAR合成图像。但这种基于子孔径独立处理后再非相干叠加的技术，会遭遇方位分辨率损失的问题。为了缓解这个问题，Cetin等人[3-5]利用正则化 $l _ { p } ( 0 < p < 1 )$ 稀疏优化技术对目标非理想散射进行建模，提出了具有超分辨和特征增强能力的SAR重建算法。然而正则化参数的选择对最终的重建性能影响较大。Jackson等人[6\~8]将散射机理驱使的参数化模型（如几何绕射模型[9]和典型形状特征模型[10])引入到SAR重建问题中，将SAR重建问题转换为一个参数估计问题。然而，该技术是一个高计算代价的非线性非凸问题，特别是在考虑了定阶问题时。为了克服和缓解以上问题，本文将压缩感知理论与属性散射先验[1I]相结合，提出了一种新的SAR重建算法。压缩感知理论（CS)[12,13]指出通过求解一个欠定的稀疏约束优化问题，高维的稀疏信号能被高概率的重建。在理想点目标假设下，Liu、Zhang 等人[14,15]和向高等人[16提出了三个基于CS的SAR重建算法，能高效获得SAR重建图像。

本文的主要贡献是在构建SAR重建算法过程中同时考虑散射中心的空域稀疏性和散射体的属性散射信息。通过散射中心属性参数空间分类，原始的多属性参数联合估计问题被适当分解，以降低计算负担。本文所提出的SGMVP属性参数估计算法包含基于字典的追踪、最优自适应滤波以及残差更新三个过程。该算法不仅能获得超分辨的SAR重建图像，同时还能提供高精度的散射体物理相关的属性散射特征。

# 1 属性散射信息驱动的观测模型

# 1.1属性散射中心描述

人造目标通常能直观地近似分解为一些简单的几何体，如图1所示。由电磁理论可知，这些几何体被称为典型散射部件，他们随频率和入射角变化的散射响应是可预测的[17]。属性散射中心模型就是其中一种有效的电磁散射参数化模型，能够有效的捕获和描述散射体的各向异性散射特性和色散散射特性，为目标的散射响应提供物理相关的简洁描述。由GTD模型出发，将空间中位于 $( x _ { p } , y _ { p } )$ 处的典型散射部件的属性散射幅度响应可统一近似写为

$$
S ( k , \phi ; \Upsilon _ { p } ) = \sigma _ { p } \big ( j k / k _ { c } \big ) ^ { \alpha _ { p } }
$$

$$
\mathrm { e x p } \Bigl ( - c k \beta _ { _ { p } } \sin \phi \Bigr ) \mathrm { s i n c } \Biggl ( \frac { k l _ { _ { p } } } { \pi } \mathrm { s i n } \Bigl ( \phi - \overline { { \phi } } _ { _ { p } } \Bigr ) \Biggr )
$$

其中： $\sigma _ { { } _ { p } }$ 是散射中心的复散射系数， $\alpha _ { { _ p } }$ 为频率依赖属性参数，$\beta _ { { } _ { p } }$ 为方位依赖属性参数， $l _ { p }$ 表示散射中心的长度属性参数， $\overline { { \phi } } _ { p }$ 为散射中心姿态角属性参数。第 $p$ 个散射中心的七种属性集合为 $\Upsilon _ { p } \cup \{ x _ { p } , y _ { p } \}$ ， $\Upsilon _ { p } = \{ \sigma _ { p } , \alpha _ { p } , \beta _ { p } , l _ { p } , \overline { { \phi } } _ { p } \}$ ，波数 $k = 2 \pi / \lambda$ ， $\phi$ 表示方位角。属性散射中心模型将典型散射部件粗略的划分为局部式散射中心和展布式散射中心。矩形板、躺圆柱和二面角属于展布式散射中心。对于展布式散射中心，描述局部式散射中心的方位依赖属性 $\beta _ { { } _ { p } } = 0$ 。而局部式散射中心主要包括球、三面角以及圆顶帽三类典型散射部件。对于局部式散射中心，散射部件在雷达视线平面上的投影有效长度以及姿态角都恒等于零，即 $l _ { p } = \overline { { \phi } } _ { p } = 0$ 。另外，频率依赖属性参数 $\alpha _ { { _ p } }$ 是一个与散射体表面局部曲率有关的整数值。

![](images/e35dc07ab3c307ff4d66b191e3fcfa8eeff730873ee694a292d6722a707e2cdc.jpg)  
图1复杂目标部件级近似分解示意图

# 1.2基于ASC的SAR观测模型

SAR数据获取的原理是随着天线平台的运动，雷达从多个方位角度对兴趣观测区域实现脉冲数据采集。由于散射体的空间位置信息和几何形状信息分别对SAR相位史的相位和幅度进行调制，因此能够开发算法同时获取散射体的空间位置属性和几何结构属性。理想点目标模型的散射响应是恒幅且独立于频率和方位角的，因此与基于理想点模型的SAR重建模型不同，本文将给出一种基于ASC 模型的部件级散射特征化SAR重建模型。基于典型散射体的相位史可表示为

$$
r ( k , \phi ) = \sum _ { p = 1 } ^ { P } h ( x _ { p } , y _ { p } , k , \phi ) \exp \left\{ - j 2 k \rho _ { p } ( x _ { p } , y _ { p } , \phi ) \right\}
$$

其中:位置偏移量 $\rho _ { p } ( x _ { p } , y _ { p } , \phi ) = x _ { p } \cos \phi + y _ { p } \sin \phi$ ， $P$ 表示场景中的散射中心数量。散射函数明确的写为 $h ( x _ { p } , y _ { p } , k , \phi )$ ，用于表征散射体的非理想散射行为。对于某个空间位置，基于ACS 模型的散射函数可表示为 $h ( k , \phi ) = \sigma _ { p } S ( k , \phi ; \overline { { \Upsilon } } _ { p } )$ ，其中属性参数集$\overline { { \Upsilon } } _ { p } = \{ \beta _ { p } , l _ { p } , \overline { { \phi } } _ { p } \}$ 。考虑到当信号带宽小于 $4 ~ \mathrm { G H z }$ 时形状属性参数不具有可辨识性，本文暂时忽略该属性[17]。因此，基于ASC的SAR观测模型可写为

$$
r ( k , \phi ) = \sum _ { p = 1 } ^ { P } \sum _ { \nu = 1 } ^ { V } \sum _ { u = 1 } ^ { U _ { \nu } } \sigma _ { p } ^ { \nu , u } S ( k , \phi ; \overline { { { \Upsilon } } } _ { p } ^ { \nu , u } ) \exp \left\{ - j 2 k \rho _ { _ p } ( x _ { _ p } , y _ { _ p } , \phi ) \right\}
$$

其中: $\nu$ 为散射中心类型索引， $V = 2$ 表示过完备字典中含有局部式和展布式两类典型散射体， $U _ { \nu }$ 表示散射中心类型为 $\nu$ 的属性参数空间 $\mathbf { \overline { { Y } } } _ { p } ^ { \nu , u }$ 离散化以后的基向量数。本文假设相位史测量的频点数为 $L$ ，方位点数为 $N$ ，则容易获得 $r = r ( k , \phi ) \in \mathbb { C } ^ { N L }$ 以及 $\pmb { S } _ { \nu , u , p } = S ( k , \phi ; \overline { { \Upsilon } } _ { p } ^ { \nu , u } ) \in \mathbb { C } ^ { N L }$ 。对于每一个空间位置，向量 $\pmb { S } _ { \nu , u , p }$ 能被串联形成矩阵 $\overline { { \overline { { S } } } } _ { p } = [ \overline { { \overline { { S } } } } _ { 1 , p } , \cdots , \overline { { \overline { { S } } } } _ { \nu , p } ]$ ，其中 $\overline { { \pmb { S } } } _ { \nu , p } = [ \pmb { S } _ { \nu , 1 , p } , \cdots , \pmb { S } _ { \nu , U _ { \nu } , p } ]$ 为类型 $\nu$ 所对应的子字典。如果本文令 $U = { \sum _ { \nu = 1 } ^ { V } } U _ { \nu }$ ，并同时定义子字典 $T _ { _ { p } } = \overline { { S } } _ { _ { p } } \odot ( q _ { _ { p } } \eta _ { _ { U } } ^ { _ { T } } )$ ，其中 $\odot$ 表示矩阵元素相乘，（204号 $q _ { p } = \exp \{ - j 2 k \rho _ { { p } } ( x _ { { p } } , y _ { { p } } , \phi ) \} \in \mathbb { C } ^ { N L }$ ， $\pmb { \mathscr { 1 } } _ { \mathnormal { v } }$ 是全一向量，则可以获得一个简洁的线性表示：

$$
\boldsymbol { r } = \boldsymbol { T } \boldsymbol { \sigma } + \boldsymbol { \varepsilon }
$$

其中: $\ b { T } = [ \ b { T } _ { 1 } , \cdots , \ b { T } _ { P } ] \in \mathbb { C } ^ { \ b { N L } \times \ b { U P } }$ 是对应所有空间位置的过完备字典，（204号 $\varepsilon$ 是复的白高斯噪声以及复散射系数向量 $\boldsymbol { \sigma } = [ \sigma _ { 1 , 1 , 1 } \cdots \sigma _ { P , V , U _ { V } } ] ^ { T }$ 。式(4)即为基于属性散射信息的观测模型。

# 2 基于SGMVP的SAR超分辨重建算法原理及 流程

虽然SAR重建模型(4)具有捕获散射体非理想散射行为的能力，但是由于散射中心属性的多样性以及成百上千的空间位置数，将使得过完备字典T的列数急剧增加。直接求解问题(4)将遭遇高内存需求以及高计算量等问题。另外，如果利用理想点散射模型对典型散射部件的散射响应进行拟合，则典型散射部件响应将被近似表征为多个不同空间位置的点散射响应的叠加。该误差严重影响散射中心其他属性的估计精度，甚至导致属性特征的估计完全失败。为了解决以上问题，本文将属性散射信息与改进的随机梯度最小方差追踪(SGMVP)技术相结合，提出一种新的物理散射特性相关的超分辨SAR重建算法。ASC模型的六种属性在SGMVP中被层级的估计。整个SGMVP包含三大处理过程：a）追踪过程：判别散射中心类型的同时估计第一类属性参数（散射中心的空间位置和有效长度)；b）最优自适应滤波过程：获取第二类属性参数（局部散射中心的方位依赖和展布式散射中心的姿态角）以及第三类属性参数（复散射系数)；c）残差更新过程。

在追踪过程中，通过将第二、第三类属性参数初始化为零以及观测的随机压缩采样 $Q < N L$ ，可获得有效降维后的过完备字典 $\overline { { \boldsymbol { T } } } \in \mathbb { C } ^ { Q \times P L ^ { \prime } }$ ，其中有效长度属性参数离散化为 $l ^ { \prime } = 1 , \cdots , L ^ { \prime }$ 。计算相关向量 $c = \rvert \bar { T } ^ { H } r ^ { \prime } ( \tau ) \lvert \in \mathbb { R } ^ { P L ^ { \prime } }$ 其中 $r ^ { \prime } ( \tau )$ 是第 $\tau$ 次迭代的残差向量。然后，通过确定相关向量最大元素，即argmax{c(e)},可获得第 $\tau$ 个散射中心的第一类属性估计，其中 $\boldsymbol { e }$ 表示相关向量 $c$ 中元素的索引。如果有效长度属性是非零的，则判别第 $\tau$ 个散射中心为展布式典型散射体，同时描述局部式散射体的方位依赖 $\beta _ { \tau }$ 赋值为零。相反的，如果有效长度属性估计为零，则判别第 $\tau$ 个散射中心为局部式典型散射体，并将第 $\tau$ 个散射中心的姿态角属性取值为零。在已知散射中心类型的情况下，结合同一散射中心的姿态角属性 $\overline { { \phi } } _ { \tau }$ 和方位依赖属性 $\beta _ { \tau }$ 不可能同时非零的特点。本文设计开发适当的最优自适应滤波过程估计第二类和第三类属性参数。联合ASC模型及估计出的第一类属性估计构建辅助参数 $\xi _ { \tau }$ 的搜索子空间 $\tilde { S } ( \xi _ { \tau } ; \tilde { \Upsilon } _ { \tau } ) \in \mathbb { C } ^ { Q \times Z }$ ，其中当散射中心判别为局部式散射中心时，辅助参数 $\xi _ { \tau }$ 代表该散射中心的姿态角属性 $\overline { { \phi } } _ { \tau }$ 。当散射中心判别为展布式散射中心时，辅助参数 $\xi _ { \tau }$ 代表该散射中心的方位依赖属性 $\beta _ { \tau }$ ， $Z$ 为 $\xi _ { \tau }$ 的离散采样数,参数集 $\tilde { \Upsilon } _ { \tau }$ 表示从集合 $\{ \beta _ { \tau } , \overline { { \phi } } _ { \tau } , l _ { \tau } , x _ { \tau } , y _ { \tau } \}$ 中除去 $\xi _ { \tau }$ 所代表的属性参数后的参数集。本文通过最小方差方法估计第 $\tau$ 个散射中心的辅助参数 $\xi _ { \tau }$ 的值，即有

$$
\boldsymbol { \xi } _ { \tau } = \underset { \boldsymbol { \xi } _ { \tau } } { \arg \operatorname* { m i n } } \mathcal { D } \left\{ \left| \tilde { S } ( \boldsymbol { \xi } _ { \tau } ; \tilde { \boldsymbol { \Upsilon } } _ { \tau } ) ^ { H } \boldsymbol { C } ^ { - 1 } \tilde { S } ( \boldsymbol { \xi } _ { \tau } ; \tilde { \boldsymbol { \Upsilon } } _ { \tau } ) \right| ^ { 2 } \right\}
$$

其中: $\mathcal { D } \{ \cdot \}$ 表示矩阵的主对角线， $C = \ E [ r r ^ { H } ] + \lambda _ { 1 } I$ 是相位史协方差矩阵， $\lambda _ { 1 }$ 是噪声相关的对角加载参数。对于辅助参数 $\xi _ { \tau }$ 的一个真实值，式(5)是一个理论上理想的滤波过程，该滤波过程在参数取真实值处使能量最大化，同时使得其他取值处的能量最小。因此，通过估计出的第一类属性参数和表征第二类属性的辅助参数，容易确定第 $\tau$ 个散射中心对应的属性相关的基向量在过完备字典 $\tau$ 中的原子索引 $\epsilon ( \tau )$ 。因此，可更新最优支撑集 $\Omega ( \tau ) = \Omega ( \tau - 1 ) \cup \epsilon ( \tau )$ ，同时扩展选择矩阵

$$
\hat { T } _ { \Omega ( \tau ) } = \left\{ t _ { i } | i \in \Omega ( \tau ) \right\}
$$

其中: $t _ { i }$ 是过完备字典的第 $i$ 列。然后，将选择矩阵带入LMS过程递归的估计第三类属性，即复散射系数。LMS的梯度下降递归更新可表示为

$$
\begin{array} { r } { \tilde { \sigma } _ { \omega + 1 } = \tilde { \sigma } _ { \omega } + \lambda _ { 2 } \Big ( r _ { \omega } - \hat { t } ^ { \omega } \tilde { \sigma } _ { \omega } \Big ) \Big ( \hat { t } ^ { \omega } \Big ) ^ { H } } \end{array}
$$

其中: $\hat { t } ^ { \omega }$ 表示选择矩阵的第 $\omega$ 行， $r _ { \omega }$ 是 $r$ 的第 $\omega$ 个元素， $\lambda _ { 2 }$ 是步长参数。 $\tilde { \sigma } _ { \omega + 1 }$ 表示一个复系数向量，其维数等于当前支撑集的元素个数。由于以上递归过程，复系数向量取值不断更新，$\omega$ 取值从1到 $\boldsymbol { \mathcal { Q } }$ .第三类属性在当前迭代的估计可表示为$\hat { \sigma } _ { \Omega ( \tau ) } = \tilde { \sigma } _ { \varrho }$ 。在残差更新过程，利用 $\scriptstyle \zeta ( \tau ) = \parallel r ^ { \prime } ( \tau ) \parallel _ { 2 } / \parallel r \parallel _ { 2 }$ 计算当前残差，其中 $r ^ { \prime } ( \tau ) = r - \hat { T } _ { \textsc { a ( t ) } } \tilde { \sigma } _ { _ { Q } }$ 表示残差向量。随着迭代次数的增加，残差逐渐趋近于零。当其达到或低于一个预设的门限时，输出复散射系数的最终估计。最后，利用估计的散射中心属性信息和ASC模型，对SAR目标的频域观测谱进行外推。为了进一步降低模型误差的影响，保留原始回波中的弱细节特征，利用原始回波替换由ASC模型生成的相位史的中心部分。最终无加权的超分辨SAR图像可通过基于FFT的算法(例如：PFA)获得。详细的重建算法处理流程可见SGMVP算法。

SGMVP算法

初始化：一个初始系数向量 $\hat { \sigma } ( 0 ) = 0$ ；几何相关的字典$\overline { { \boldsymbol { T } } } \in \mathbb { C } ^ { Q \times P L ^ { \prime } }$ ；参数 $\lambda _ { 1 }$ 和 $\lambda _ { 2 }$ ；终止门限 $\kappa _ { 1 }$ 和 $\kappa _ { 2 }$ 口

a)利用追踪过程 $\underset { e \in [ P L ^ { \prime } ] } { \arg \operatorname* { m a x } } \{ c ( e ) \}$ 估计第 $\tau$ 个散射中心的第一类属性，根据有效长度是否为零判别散射中心类型。

b)分配一个恰当的第二类属性给辅助参数 $\xi _ { \tau }$ ，并通过改进的最小方差技术估计辅助参数

$$
\boldsymbol { \xi } _ { \tau } = \underset { \boldsymbol { \xi } _ { \tau } } { \arg \operatorname* { m i n } } \mathcal { D } \left\{ \left| \tilde { S } ( \boldsymbol { \xi } _ { \tau } ; \tilde { \Upsilon } _ { \tau } ) ^ { H } C ^ { - 1 } \tilde { S } ( \boldsymbol { \xi } _ { \tau } ; \tilde { \Upsilon } _ { \tau } ) \right| ^ { 2 } \right\}
$$

c）估计出的前两类属性确定基向量在过完备字典 $\tau$ 中的索引 $\epsilon ( \tau )$ ，并更新支撑集 $\Omega ( \tau ) = \Omega ( \tau - 1 ) \cup \epsilon ( \tau )$ 和选择矩阵

$$
\hat { T } _ { \Omega ( \tau ) } = \left\{ t _ { i } | i \in \Omega ( \tau ) \right\}
$$

d)MMSE准则下结合估计出的选择矩阵，采用LMS递归策略估计第三类属性 $\begin{array} { r } { \tilde { \sigma } _ { \omega + 1 } = \tilde { \sigma } _ { \omega } + \lambda _ { 2 } \Big ( r _ { \omega } - { \hat { t } } ^ { \omega } \tilde { \sigma } _ { \omega } \Big ) \Big ( { \hat { t } } ^ { \omega } \Big ) ^ { H } } \end{array}$ ，其中$\omega \leq Q$ 。

e)迭代增加 $\tau$ ，直到 $\zeta ( \tau ) \leq \kappa _ { 1 }$ 或者 $\begin{array} { r } { | r { ' } ( \tau ) - r { ' } ( \tau - 1 ) \| _ { 2 } \le \kappa _ { 2 } } \end{array}$ 。

f联合典型散射部件的属性估计和ASC模型外推相位史数 据。

g)用原始回波替换由ASC重新生成的观测谱的中心部分，利用基于FFT的方法获得最终的超分辨SAR图像。

# 3 仿真实验验证

为了验证本文提出的SAR重建算法的性能优势，主要从散射中心属性的估计精度以及超分辨重建能力两个方面对算法进行实验考察。首先，本文利用SAR系统模型生成理论分辨率为$0 . 3 ~ \mathrm { m } \times 0 . 3 ~ \mathrm { m }$ 的 SAR相位史数据，系统参数见表1。

<html><body><table><tr><td>衣1</td><td>系统参数</td></tr><tr><td>参数类型</td><td>取值</td></tr><tr><td>信号载频</td><td>9.0 GHz</td></tr><tr><td>频率采样间隔</td><td>0.01 GHz</td></tr><tr><td>方位采样间隔</td><td>0.05°</td></tr><tr><td>频率数</td><td>50</td></tr><tr><td>方位数</td><td>66</td></tr></table></body></html>

合成场景包含十二个典型散射部件：三个躺圆柱、两个圆顶帽、两个三面角、三个矩形板、一个二面角和一个球体，如图2(a)所示。然后给相位史数据加上已知噪声方差的复的高斯白噪声。利用多次重复该噪声加载过程获得独立重复实验的观测数据。利用克拉美罗界对本文提出的 SGMVP算法估计性能进行评估。图2(c)展示了随着信噪比增加散射中心属性估计方差的变化规律。本文将SNR定义为峰值相位史信号能量与噪声方差之比。正如本文所期望的，六种属性的估计精度都随着SNR的增加而增加。然而，需要指出的是由于参数空间的离散化，以及数值优化过程的初始值设置，估计方差均不能达到克拉美罗界。

![](images/0d4a5993009f2ff11313b85949d10bdb82dbf167e1c53758959110cc2efc1037.jpg)  
图2合成场景重建结果与重建性能

为了进一步展示本文提出的SAR重建算法超分辨优势，将所提算法与两个基准SAR重建算法进行比较。它们分别为传统的极坐标算法和稀疏驱使的拟牛顿超分辨算法（QNA算法）。图3(a)(c)(e)分别展示了在 $3 0 ~ \mathrm { d B }$ 信噪比下三种算法的 $2 \times 2$ 倍超分辨重建结果，本文采用等高线图对重建结果进行展示，意在更加清晰的显示QNA算法和本文所提算法的超分辨优势，其中这两个算法的压缩采样率均设为 $\mathcal { Q } \mathrm { ~ / ~ } ( N L ) = 0 . 8 5$ 。图3(b)(d)(f)分别展示的是与其左图对应且在方位向距离 $\scriptstyle \mathbf { y } = 0 . 0 7 5$ m处的一维切片图像。黑色圆圈和黑色点线分别表示散射中心准确的幅度值和距离门。从图3可知，QNA算法和本文所提算法在局部式散射中心的超分辨重建性能上都要优于PFA算法。而且，本文所提算法由于联合了物理相关的属性散射先验信息，要比QNA算法具有更强的展布式散射中心超分辨重建能力。为了量化的评估重建性能，本文定义重建均方误差$\mathrm { R M S E } = 2 0 \log _ { 1 0 } ( \left\| r - \hat { r } \right\| _ { 2 } / \left\| r \right\| _ { 2 } )$ 。在图2(d)展示了每个信噪比下进行50次的蒙特卡洛实验的三种重建算法RMSE性能曲线。由于联合了部件级的散射信息，本文所提算法在高信噪比下能够获得比基于理想点目标模型的QNA重建算法更低的重建残差。图2(b)展示了所提算法在SNR为27dB时的SAR 超分辨重建图像。然而，实验经验总结当SNR低于15dB时，误差传递现象将明显影响所提算法的重建性能。进一步提高算法在低

SNR下的高精度部件级重建性能是未来研究工作之一。在重建效率方面，因为FPA算法的耗时远小于另外两种算法，因此本文主要比较QNA算法和本文所提算法的重建效率。对于图2(b)的场景，50次的蒙特卡洛实验下，QNA算法的平均成功重建耗时为 $1 6 . 7 1 \mathrm { ~ s ~ }$ ，本文所提算法的平均成功重建耗时为 $2 9 . 4 3 \mathrm { ~ s ~ } _ { \circ }$ （20由于本文算法在重建过程中引入了部件级模型的属性参数集估计过程，因此计算复杂度和资源消耗比另外两种基于理想点目标模型的重建算法更高。如何降低计算量，提高算法重建效率也是下一步需要研究的问题。

最后，本文利用几何光学与物理光学相结合的高频电磁计算软件生成简易坦克目标频域回波数据，并用其验证本文所提算法。该数据采集实验系统的频带为 $8 . 7 5 { \sim } 9 . 2 5 \operatorname { G H z }$ ，方位角范围是 $8 8 . 3 5 ^ { \circ } \ \sim 9 1 . 6 5 ^ { \circ }$ ，天顶角为 $6 0 ^ { \circ }$ 。图4(a)是简易坦克目标的照片，目标几何尺寸为 $9 . 5 1 \mathrm { ~ m ~ }$ （长度） $\times 3 . 5 6 ~ \mathrm { m } ( \$ 宽度） $\times 2 . 5 7$ m(高度)。入射波为水平极化的平面波。图4(c)\~(e)分别展示的是PFA算法、QNA算法和所提算法的 $2 \times 2$ 超分辨重建SAR图像。图中标记的小区域A和B展示了所提算法的超分辨重建优势。另外，本文将散射中心类型的判别结果覆盖在超分辨重建图像上，如图4(b)所示，其中黄色矩形标记和绿色三角标记分别表示展布式散射中心和局部式散射中心。所提算法在重建超分辨图像的同时获取的散射中心属性和类型特征信息能够有效的为SAR高级处理模块（如自动目标识别模块）提供支持。

![](images/67e4de29f0dbea133da40d7d0c66b682e22a9ac8c81dba56ee3a9db134665117.jpg)  
图3信噪比为30dB时的超分辨重建结果比较

# 4 结束语

本文提出一种基于信号域的散射中心属性参数空间分类策略，并联合频域外推，提出一种基于随机梯度最小方差追踪的部件级超分辨重建算法。该算法能获得至少两倍的超分辨重建SAR图像。散射中心属性参数的估计方差接近CRLB。实现了在获得超分辨 SAR 图像的同时获取高精度的目标散射中心属性级特征。

![](images/8ebca082f69eaf72190c87b08552eed01ebf852c9d3c749c7a6d070b21bc2bf1.jpg)  
图4坦克目标的重建结果

# 参考文献：

[1]FasoulaA,Driessen H,Genderen Van P.De-ghosting of tomographic images in a radar network with sparse angular sampling[J]. International Journal of Microwave and Wireless Technologies.2010,2(3-4):359-367.

[2]Flake LR,Ahalt S C, KrishnamurthyAK. Detecting anisotropic scattering with hidden Markov models [J].IEE Proceedings-Radar,Sonar and Navigation,1997,144(2): 81-86.   
[3]Cetin M,Karl W C.Feature-enhanced synthetic aperture radar image formation based on nonquadratic regularization [J].IEEE Trans on Image Processing,2001,10(4): 623-631.   
[4]Cong Xunchao,Gui Guan,Li Xiao,et al. Object-level SAR imaging method withcanonicalscatteringcharacterisationandinter-subdictionary interferences mitigation [J].IET Radar,Sonar& Navigation,2O16,10(4): 784-790.   
[5]Varshney KR,Cetin M,Fisher JW, etal. Sparse representation in structured dictionaries with application to synthetic aperture radar[J].IEEE Trans on Signal Processing,2008,56(8): 3548-3561.   
[6]Jackson JA,Moses RL.Synthetic aperture radar 3D feature extraction for arbitrary flight paths [J].IEEE Trans on Aerospace and Electronic Systems, 2012,48 (3):2065-2084.   
[7]Liao Kefei,Zhang Xiaoling，Shi Jun.Plane-wave synthesis and RCS extraction via 3-D linear array SAR,[J].IEEE Antennas and Wireless Propagation Letters,2015,14(1): 994-997.   
[8]Guo Kunyi,Qu Quanyou, Sheng Xinqing. Geometry reconstruction based on attributes of scattering centers by using time-frequency representations [J].IEEE Trans on Antennas and Propagation,2016,64(2): 708-720.   
[9]Keller JB.Geometrical theory of diffraction [J].Journal of the Optical Society of America,1962,52(2):116-130.   
[10] Hammond G B,Jackson JA.SAR canonical feature extraction using molecule dictionaries [C]//Proc of Radar Conference.Washington DC: IEEE Press,2013:1-6.   
[11] PotterLC,MosesRL.Attributed scattering centers for SAR ATR[J].IEEE Trans on Image Processing,1997,6(1): 79-91.   
[12] Candes EJ, Tao T.Decoding by linear programming [J].IEEE Trans on Information Theory,2005,51(12):4203-4215.   
[13]Lin Yumin,Chen Yi,Huang Naishan,et al.Low-complexity stochastic gradient pursuit algorithm and architecture for robust compressive sensing reconstruction [J].IEEE Trans on Signal Processing,2016,65(3):638-650.   
[14] Liu Hongchao,Jiu Bo,Liu Hongwei, et al. Superresolution ISAR imaging based on sparse Bayesian learning [J].IEEE Trans on Geoscience and Remote Sensing,2014,52 (8): 5005-5013.   
[15] Zhang Lei,Qiao Zhijun,Xing Mengdao,et al.High-resolution ISAR imaging with sparse stepped-frequency waveforms [J].IEEE Trans on Geoscience and Remote Sensing,2011,49(11): 4630-4651.   
[16]向高，张晓玲，师君，等，基于随机阵列的降维压缩感知三维成像方法 [J]．计算机应用研究,2015,33(1):286-290.   
[17] Akyildiz, Yeliz.Feature extraction from synthetic aperture radar imagery [D]. Columbus: The Ohio State University,2000,17-55.