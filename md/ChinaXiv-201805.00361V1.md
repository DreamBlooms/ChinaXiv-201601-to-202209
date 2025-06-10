# 基于可变粒度机会调度的网络大数据知识扩充算法\*

黄金国1，刘涛1，周先春²，严锡君

(1.江苏开放大学 信息与机电工程学院，南京 210017;2.南京信息工程大学 电子与信息工程学院，南京 210017;3.河海大学 计算机与信息学院，南京 210098)

摘要：为了满足网络大数据背景下，大数据传播的数据知识高精度要求和清除劣质数据干扰，基于粒度可变调整方案提出了机会调度的网络大数据知识扩充算法。在分析网络大数据特征基础上，通过自适应向量编码，捕捉网络大数据的异构特性，采用多阶反向传播将异构网络大数据归一化处理，再通过机会调度实现网络大数据实时传输。同时，基于网络大数据组成的知识工程系统分割细粒度大数据，将多维特征进行降维处理，使得知识粒度转变为已知，接着调整粒度动态特性，使得知识工程的大数据集具有线性特征和明确的几何特性，通过知识扩充提高知识获取精度。实验结果通过与基于细粒度的知识获取算法进行对比，证明了所提算法的网络数据传输的高可靠性、实时性和知识获取的高效率。

关键词：网络大数据；知识工程；知识扩充；可变粒度；机会调度中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2017.09.0947

# Network big data knowledge extension algorithm based on variable granularity and opportunistic scheduling

Huang Jinguo1,Liu Tao1, Zhou Xianchun²,Yan Xijun³ (1.Schoolofinformation &mechanicalandelectrical engineering Jiangsu Open University Nanjing210ol7 China;2.School ofelectronic&informationengineeing,Nanjing UniversityofInformationScience&Technology,Nanjing210ol7China;3. College ofcomputer&information Hohai University,Nanjing21oo98,China)

Abstract:Inorder to metthe needsofthe networkunderthebackgroundofbigdata,andeliminate inferiordata interference dataknowledge highprecisionrequirementsoflargedata transmission,variablesizeadjustmentschemebasedonthealgorithm to expand the networkoflarge dataknowledgeopportunisticschedulingis proposed.Basedontheanalysisoflarge datanetwork characteristics,theadaptivevectorencoding,capture theheterogeneouscharacteristicsoflargedatanetwork,using multirder back-propagationnetworkofheterogeneousdataisnormalized,andthenthroughthereal-time ransmissonoflargedatanetwork to achieve opportunistic scheduling.At the same time,the knowledge engineering system composed of network data segmentationoffine-grainedbig data basedonthe multidimensional featuredimension，thegranularityof knowledge transformation is known,thenadjustthe sizeofthedynamiccharacteristics,makingbigdata setofknowledgeenginerng with linear caracteristicsand clear geometriccharacteristics,improve the acuracyof knowledge acquisition through knowledge expansion.Theexperimentalresultsarecompared withthe algorithmbasedonfine grained knowledgeacquisition,which proves the high reliability,real time and high efficiency of network data transmission.

Key Words:Networkbigdata; knowledge engineering; knowledgeextension;variable granularity;opportunisticcheduling

# 0 引言

据知识结果成为知识工程5的关键问题之一。如何从网络大数据传播6的知识中重建数据知识库，得到了广泛关注。

网络大数据固有的类型异构、数据多元和分布式传播等特点[1,2]，使得如何在网络大数据背景下，确保大数据传播的数据知识精度[3]和消除劣质数据[4]干扰，获取有效解决问题的大数

网络大数据传播方向，文献[7]所提出的一种空间结构方案通过将符号型据被转换为值型，使得不仅有效保持原符号型特征而且重造了样本的相似度。文献[8的优化原型系统，一方面可以加速多批量数据传输服务器集群，另一方面能够最好地利用带宽和分散随机线性网络编码的最大有用的信息传播。文献[9]研究了资源受限的移动机会网络的最优数据分发问题，解决了移动机会网络中时延受限的最小代价组播问题。

网络调度方向，基于随机线性网络编码，文献[10]提出了一种优先级调度方案，不仅可以利用信息包接收状态等线性关系反馈信息，还可以求解中继节点的有效信息规模。文献[11]研究了多通道无线链路之间的节点及其调度方案。文献[12]提出了一个完全分散的新分布式调度策略，使得每个节点根据其流量需求确定要调度的单元数量。

知识工程方向，文献[13]通过研究虚拟地理环境的地理知识特点，研究了虚拟地理环境的地理知识的分类及其工程架构。文献[14]提出了跨学科和多文化的方法来应对知识社会中的问题和挑战。文献[15]研究了一个知识工程框架处理零散的知识建模和多信息源的在线学习，对零散知识的非线性融合，和自动化需求驱动的知识导航。

在上述网络大数据传播和知识挖掘等领域的研究基础上，结合机会调度的网络大数据模型，研究了一种可以提高网络大数据传播效率和数据质量的知识扩充算法。

# 1 机会调度的网络大数据模型

与传统的网络数据相比，网络大数据具有一些明显特征例如数据类型复杂且异构、数据结构差异性、数据挖掘复杂度高和网络调度难度大等。针对上述网络大数据的特征，通过自适应向量编码，捕捉网络大数据的异构特性和类型特征，采用多阶反向传播统一异构网络大数据，通过机会调度网络大数据。

首先，将网络大数据挖掘对象从一维向量组转变为多维向量编码空间，得到网络大数据异构特征驱动的自适应多维向量编码模型。其次，基于大数据规模和维度，激励网络大数据在多维向量编码空间的异构特性和类型特征的捕捉。接着，提出了基于网络大数据挖掘对象和机会调度的多阶反向传播算法，将多维向量编码空间与多阶反向传播空间有机融合。最后，在多维向量编码空间中进行特征捕捉与多阶反向传播，从而组建了机会调度的网络大数据模型。

设一个 $\mathbf { m }$ 维有限域欧式空间 $G ^ { m }$ ，任意一维的向量空间为$A _ { i }$ $4 , ~ a _ { i } ^ { 1 } \in A _ { i } ^ { m } , a _ { i } ^ { 2 } \in A _ { i } ^ { m } , \cdots , a _ { i } ^ { m } \in A _ { i } ^ { m }$ 。定义 $A _ { i } ^ { 1 } , A _ { i } ^ { 2 } , \cdots , A _ { i } ^ { m }$ 的多维向量编码空间的定义如下：

$$
\left[ \begin{array} { c c c } { a _ { 1 } ^ { 1 } } & { \cdots } & { a _ { i } ^ { 1 } } \\ { \vdots } & { \ddots } & { \vdots } \\ { a _ { 1 } ^ { m } } & { \cdots } & { a _ { i } ^ { m } } \end{array} \right] \left[ \begin{array} { c } { A _ { i } ^ { 1 } } \\ { \vdots } \\ { A _ { i } ^ { m } } \end{array} \right] = \left[ \begin{array} { c } { A _ { i } ^ { 1 } \displaystyle \sum _ { j = 1 } ^ { i } a _ { j } ^ { 1 } } \\ { \vdots } \\ { A _ { i } ^ { m } \displaystyle \sum _ { j = 1 } ^ { i } a _ { j } ^ { m } } \end{array} \right]
$$

在 $G ^ { m }$ 空间上，针对 $A _ { i } ^ { m }$ 的多维向量编码空间，网络大数据异构特征向量 $B$ 与多维向量的映射关系如下：

$$
\left\{ \begin{array} { l } { \displaystyle b _ { i } ^ { j } = \sum _ { i = 1 , j = 1 } ^ { m } \left\| A _ { i } ^ { m } \right\| ^ { 2 } \left( a _ { j } ^ { i } - m \right) } \\ { \displaystyle a _ { i } ^ { j } = \left\| B \right\| ^ { 2 } + \sum _ { i = 1 } ^ { m } A _ { i } \left\| b _ { i } \right\| } \\ { c = A \cdot B = \sum _ { i = 1 , j = 1 } ^ { m } b _ { i } ^ { j } \cdot a _ { i } ^ { j } \cdot \left( \left\| A _ { i } ^ { m } \right\| ^ { 2 } + \left\| B \right\| ^ { 2 } \right) } \end{array} \right.
$$

其中:b 表示向量 $B$ 的元素， $\mathrm { j }$ 表示空间上的向量维度，c表示基于向量 $B$ 驱动，对向量 $A$ 进行向量编码后的向量。

自适应多维向量编码形式描述如式（3）：

$$
\left\{ \begin{array} { l l } { \displaystyle C _ { a _ { 1 } \cdots a _ { n } } = \big \| A _ { \quad 1 , \cdots , m } ^ { m } \big \| + \prod _ { i = 1 , \cdots , m } B _ { i } } \\ { \displaystyle c _ { i } ^ { j } = \frac { \delta } { 2 \pi } \exp \left\{ - \big \| a _ { i } ^ { j } - b _ { i } ^ { j } \big \| ^ { 2 } \right\} } \\ { \displaystyle d _ { i } ^ { j } = \frac { \sqrt { \big ( a _ { i } ^ { j } - b _ { i } ^ { j } \big ) } } { \big \| C \big \| ^ { 2 } } } \end{array} \right.
$$

其中:向量 $C _ { a _ { 1 } \cdots a _ { m } }$ 为多维向量空间上网络大数据的编码。变量 $\delta$ 表示向量维度偏移量。参量 $d _ { i } ^ { j }$ 表示向量A与向量B多维空间编码后之间的差异。

自适应多维向量编码后的网络大数据在网络传播过程中，进行如式（4）所示的迭代计算。

$$
\left\{ \begin{array} { l } { \displaystyle \overline { { C _ { a _ { 1 } \cdots a _ { m } } } } = C _ { a _ { 1 } \cdots a _ { m } } - \frac { \displaystyle \int c _ { i } \cdot \left\| A ^ { m } _ { i } \right\| _ { i = 1 , \ldots , m } d c } { \displaystyle \prod _ { i = 1 , \ldots , m } B _ { i } } } \\ { \displaystyle \overline { { C _ { i } ^ { j } } } = c _ { i } ^ { j } - \frac { \displaystyle \sum _ { i = 1 , j = i } ^ { m } \left\| a _ { i } ^ { j } - b _ { i } ^ { j } \right\| ^ { 2 } } { \displaystyle 2 \pi } } \end{array} \right.
$$

其中: $C _ { a _ { 1 } \cdots a _ { m } }$ 和 $c _ { i } ^ { j }$ 表示多维空间编码向量及其参量的网络传播的迭代变形处理。

为了提高网络大数据的传播效率，采用机会调度，机会参量可由式（5）计算得到。

$$
O _ { i = 1 \ldots m } = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } \frac { \displaystyle \int t \cdot \sqrt { \left| a _ { i } ^ { j } - b _ { i } ^ { j } \right| } d t } { \displaystyle \left\| C _ { a _ { 1 } , \ldots a _ { m } } \right\| ^ { 2 } }
$$

其中: $O _ { i = 1 \dots m }$ 表示 $\mathrm { ~ m ~ }$ 个维度上每个维度的机会调度权重。参数t表示网络大数据传播时间。随着网络大数据编码传播的过程，基于多维空间编码差异进行网络大数据传播的机会调度。

综上所述，网络大数据的多阶反向传播的主要步骤如下：

a)获取网络大数据的多维空间编码及其参量，得到 $C _ { a _ { 1 } \cdots a _ { m } }$ 和 $c _ { i } ^ { j }$

b)对多维空间编码向量及其参量的进行网络传播的迭代变形处理，得到 $C _ { a _ { 1 } \cdots a _ { m } }$ 和 $\overline { { c _ { i } ^ { j } } }$ 。

c)对于每一维空间的编码参量c，求解机会调度权重 $\boldsymbol { o } _ { i = 1 \dots m }$ 。

d)对于每一阶网络大数据传播，求解前向集合 $F _ { i } ^ { m }$ 和反向数据集合 $R _ { i } ^ { m }$ 。

e)计算向量A与向量B的多维空间编码后之间的差异 $d _ { i } ^ { j }$ （20   
f)计算 ${ \boldsymbol { F } } _ { i } ^ { m }$ 和 $R _ { i } ^ { m }$ 的残差，修正反向网络大数据集合 $R _ { i } ^ { m }$   
机会调度的网络大数据的多阶反向传播算法描述如下：   
输入： $\mathrm { ~ m ~ }$ ， $A _ { i }$ （20   
输出： $\overline { { { R } _ { i } ^ { m } } }$ （204号   
for $\mathrm { i } { = } 1$ $\mathrm { i } { + } { + }$ $\mathrm { i } { < } = \mathrm { m }$ $\left\| \boldsymbol A _ { 1 , \cdots , m } ^ { m } \right\| ;$   
for j=1 $\therefore \mathrm { j + + } , \mathrm { j < = m }$ （204号   
$\mathrm { B _ { j } { = } B _ { j } { ^ { * } B _ { j - l } } }$ ，   
obtain （20 $C _ { a _ { 1 } \cdots a _ { m } }$ and $c _ { i } ^ { j }$   
for i=1, $\mathrm { i } { + } { + }$ $\mathrm { i } { < } = \mathrm { m }$ ${ \cal \overline { { { \cal C } _ { a _ { 1 } \cdots a _ { m } } } } } = C _ { a _ { 1 } \cdots a _ { m } } - \frac { \displaystyle { \int } c _ { i } \cdot \left\| A ^ { m } { } _ { i } \right\| _ { i = 1 , \ldots , m } d c } { \displaystyle { \prod _ { i = 1 , \cdots , m } B _ { i } } } ;$ ${ \displaystyle \overline { { c _ { i } ^ { j } } } = c _ { i } ^ { j } - \frac { \displaystyle \sum _ { i = 1 , j = i } ^ { m } \left\| a _ { i } ^ { j } - b _ { i } ^ { j } \right\| ^ { 2 } } { \displaystyle 2 \pi } } ~ ;$   
for $\mathrm { i } { = } 1$ ， $\mathrm { i } { + } { + }$ $\mathrm { i } { < } = \mathrm { m }$   
← $\mathrm { e m p } { = } \sum _ { i = 1 } ^ { m } { \frac { \displaystyle { \int t \cdot \sqrt { \left| a _ { i } ^ { j } - b _ { i } ^ { j } \right| } d t } } { \displaystyle { \left\| C _ { a _ { 1 } , . . a _ { m } } \right\| ^ { 2 } } } } ;$ $O _ { i = 1 \dots m } { \mathrm { = t e m p / m } } ;$ （204   
computing the $\boldsymbol { F _ { i } ^ { m } }$ and $R _ { i } ^ { m }$ ：，   
amending the $R _ { i } ^ { m }$ with $F _ { i } ^ { m }$ ·，   
return $\overline { { { R } _ { i } ^ { m } } }$

# 2 可变粒度的知识扩充算法

基于网络大数据组成的知识工程系统定义为三元组 $K { = } { < } \mathrm { R } .$ E, $\mathrm { A R } >$ ，其中R表示网络大数据集；E表知识描述对象；AR表示大数据集所有元素的知识属性集。对于， $\forall a r \in A R$ ， $\forall e \in E$ ，定义线性关系属性映射 $a r : e \to T _ { r }$ ，其中 $\mathrm { T _ { r } }$ 表示网络大数据集R的任一元素 $\mathbf { r }$ 的知识属性映射关系，形如 $R { \left( e \right) } \subset A R { \left( r \right) }$ 。因此，一个粗糙的知识工程系统可定义为${ K R } = \left. { R , E \bigcap A R ( r ) , A R \bigcup \lambda } \right.$ ，其中 $\lambda$ 表示粒度粗糙权重。

假设K是一个多粒度粗糙知识工程系统，R，E和AR之间存在模糊粗糙映射关系，且R与E之间的元素映射存在多对多现象，即 $h \in R \cap E$ 且 $h \in \forall a r \subset A R$ 。于是，K中的细粒度精确知识集合 $\overline { { K } }$ 与粗糙知识工程系统KR的细粒度知识集合$\overline { { K R } } \left( \lambda < \overline { { \lambda } } \right)$ ，存在如式（6）所示的关系。

$$
\left\{ \begin{array} { l l } { \displaystyle \overline { { K } } = \left\{ r \in R : \frac { ( e , a r ) \bigcup \bigl ( r \to A R ( r ) \bigr ) } { e } \subset K \right\} } \\ { \displaystyle \overline { { K R } } = \left\{ r \in R : \frac { 1 } { r } \bigl ( e , a r \bigr ) \cap ( r , \lambda ) \cap K \right\} } \\ { \displaystyle \overline { { \lambda } } = \frac { \displaystyle \overline { { \sum } } \sqrt { \left| a _ { i } - b _ { i } \right| } } { \displaystyle \overline { { \left\| A \right\| ^ { 2 } } } } } \end{array} \right.
$$

其中: $\overline { { \lambda } }$ 表示粗糙集的细粒度阈值。

在网络大数据知识工程系统中，知识粒度在大数据网络传输的多维向量空间中具有多维特征，该特征使得知识粒度具有未知性和动态特性。为了寻求细粒度大数据，以便将多维特征进行降维处理，使得知识粒度转变为已知，且调整动态特性，使得知识工程的大数据集具有线性特征和明确的几何特性，提高知识挖掘精度和知识处理目标的唯一定义。对于，粗粒度多维大数据，通过调整粒度特征和降维处理，降未知性进行线性描述，隐藏未知大数据的多维空间几何特性。多维向量空间与细粒度知识几何特征空间之间的对应关系详见图1，知识工程的三元组降维至二元组，将未知因素进行了确定性转换和几何特征。

![](images/fc82d4e56bea65c2123a3dae7305a5b99e04f6cfd87fcd00c6057c8788085134.jpg)  
图1多维空间与几何特征空间的对应

因此，对于知识工程系统K，基于可变粒度给出网络大数据知识的参数和属性描述：

$$
\left\{ \begin{array} { l l } { - = f \big ( r , E , A R \big ) , r \in \overline { { R _ { i } ^ { m } } } , f : R ^ { m } \to V ^ { m } } \\ { \qquad \quad } \\ { f \big ( r , E , A R \big ) = \displaystyle \frac { \big ( E , A R \big ) \bigcap \big ( r , \lambda \big ) } { r \big \| K \big \| ^ { 2 } } } \end{array} \right.
$$

其中， $f : R ^ { m } \to V ^ { m }$ 表示从原始多维向量空间 ${ \sf R } ^ { \mathrm { m } }$ 到可变力度特征空间 $\mathrm { V ^ { m } }$ 的降维映射。

可变粒度转换可以通过方程 $\boldsymbol { \rho } { = } ( \mathrm { r } ^ { * } \mathrm { s i n } \mathrm { a } { + } \mathrm { e } ^ { * } \mathrm { c o s } \beta ) \mathrm { f } ( \mathrm { r } , \mathrm { e } , \mathrm { a r } ) \mathrm { ~ }$ 进行解析完成，其中 $\rho$ 表示可变粒度， $\mathfrak { a }$ 表示任一大数据大数据元素r的多维向量空间水平交叉弧度， $\beta$ 表示任一知识描述对象e在空间降维过程中产生的垂直交叉弧度。因此，可变粒度与网络大数据知识工程的迭代关系如式（8）所示。

$$
\{ \begin{array} { l l } { ( r , e ) \displaystyle | \rho = f ( r , e ; \alpha ) } & { \{ ( r , e ) \in R ^ { m } \} } \\ { ( \overline { { r } } , e ) \displaystyle | \rho = f ( \overline { { r } } , e ; \beta ) } & { \overline { { \lambda } } \leq \cos \beta } \end{array} 
$$

降维后知识平面上的数据点经过粒度可变转换后，多维空间的知识集全部转入细粒度几何特征空间。该空间内的数据知识具备了确定关系和线性特征。此时，网络大数据知识工程系统KR有效解决了粗粒度的不规则几何空间对知识挖掘的干扰和粒度的动态变化对知识空间的影响。图2给出了网络大数据知识获取中的粒度调度方案，以 $\overline { { \lambda } }$ 为阈值分割粗粒度集和细粒度集。细粒度直接进入获取结果，粗粒度通过可变粒度调度，消除未知性和不规则性，转换为细粒度。

![](images/76adcbc47d202e920351abf9cc9849445886c6499d9c81ae3986a6135fa3211f.jpg)  
图2基于可变粒度的知识获取模型

经过图2的可变粒度调度后，网络大数据知识工程在 $\overline { { \lambda } }$ 的细粒度分割后，通过式（9）进行知识扩充。

$$
\left\{ \begin{array} { l l } { \displaystyle { f \left( \overline { { R ^ { n } } } , \overline { { \lambda } } , \rho , \alpha , \beta \right) = \frac { \sum _ { i = 1 } ^ { m } r _ { i } + \overline { { \lambda } } \left( \sin \alpha + \cos \beta \right) ^ { \rho } } { \left\| R \right\| ^ { 2 } } } } \\ { \displaystyle { \alpha = \arctan \frac { \lambda } { \overline { { \lambda } } } } } \\ { \displaystyle { \beta = \arctan \sqrt { \rho ^ { 2 } - \overline { { \lambda } } } \Big \vert } } \end{array} \right.
$$

# 3 实验结果分析

对基于可变粒度机会调度的网络大数据知识扩充算法记为NKE-VOS进行性能分析与验证。实验中，主要分析了网络调度后数据误差、数据传输延迟、知识获取的收敛次数等性能。在相同实验环境下，所提算法的上述性能与基于细粒度的知识获取算法记为FGKA进行了对比。所采用的实验平台如表1所述。

表1实验平台  

<html><body><table><tr><td>参数</td><td>取值</td></tr><tr><td>网络终端数</td><td>50个</td></tr><tr><td>网络服务器数</td><td>5个</td></tr><tr><td>服务器CPU</td><td>Intel Xeon E3 v2</td></tr><tr><td>服务器硬盘空间</td><td>2TB</td></tr><tr><td>无线通信协议</td><td>IEEE 802.11g</td></tr><tr><td>服务器操作系统</td><td>Ubuntu Server16.04.2LTS</td></tr><tr><td>算法开发语言</td><td>Java</td></tr><tr><td>实验时间</td><td>50 min</td></tr><tr><td>网络终端存储空间</td><td>4 GB</td></tr></table></body></html>

图3给出了逐步激活网络终端后，随着网络大数据量的增加，两种算法所采用的网络调度算法在数据精度方面的表现。两种算法在 $5 0 ~ \mathrm { m i n }$ 内调度传输的大数据分别与原数据进行比对，得到数据误差。对比发现，FGKA算法的所采用的静态调度，对与大数据的规模变化反映迟缓，导致数据丢失或出错，严重制约了数据质量。反之，所设计的NKE-VOS算法所采用的机会调度，将网络大数据挖掘对象从一维向量组转变为多维向量编码空间，基于大数据规模和维度，激励网络大数据在多维向量编码空间的异构特性和类型特征的捕捉，实现高效率网络调度，有助于提高数据精度。

![](images/0efdd6d4d034c823615fed98ada4015d4e7a6363088a8024aad5a0a9c64715e5.jpg)  
图3数据误差

图4给出了随着网络大数据量的增加，两种算法在网络传输实时性方面的表现。分别统计了50分钟内两种算法传输的大数据的端到端延迟，并求平均值。对比发现，所提出的NKE-VOS 算法通过获取网络大数据的多维空间编码及其参量，接着对每一维空间的编码参量进行机会调度，对于每一阶网络大数据传播，求解前向集合和反向数据集合，采用机会调度的网络大数据的多阶反向传播算法，从而缩短网络数据传输延迟，保障实时性。

图5给出了随着网络服务器的增加，两种算法完成知识获取所需要的迭代次数。所提NKE-VOS算法将粗粒度多维大数据进行粒度可变调度，同时降维，明确未知性的线性描述，消除未知大数据，重构多维空间几何特性，所以可以在较少的迭代过程中获取知识，从而扩充网络大数据知识。

![](images/4442804afe7960a10299de377d8263c869d7c1eeed8543287f7e741ee1a69520.jpg)  
图4数据传输延迟

![](images/9aa239bbda74b9b8ff31455818af6517e87fc0fc513e298c1206d23092ba1530.jpg)  
图5收敛次数

# 4 结束语

网络大数据应用对数据传播的实时性、数据精度和知识获取效率提出了更高要求，为了满足上述要求，提出了一种适用于网络大数据的基于可变粒度和机会调度的网络大数据知识扩充算法。首先，该算法从网络大数据异构特征出发，建立多维向量空间，实时捕捉异构特性，通过自适应多维向量编码，经过多阶反向传播和机会调度，保障网络大数据传输的实时性和可靠性。其次，将网络大数据的知识工程系统按照粒度可变阈值进行细粒度分割，通过多维特征的降维，实现知识粒度的已知性和动态几何特征的明确，采用了基于可变粒度的知识扩充算法。所提算法与基于细粒度的知识获取算法在数据误差、数据传输延迟、知识获取的收敛次数等性能的对比实验，结果表明所提算法在网络大数据传输可靠性、实时性和知识获取效率等方面具有明显优势。

参考文献：   
[1]Gao J,Lu WF,Dai Z J,et al.A computational approach to characterizing the impact of social influence on individuals'vacination decision making. [J]. Plos One,2013,8 (4): 601-611.   
[2]Przulj N,Malod-Dognin N.Network analytics in theage of big data [J]. Science,2016,353 (6295): 123-124.   
[3]Gao S,Pang H,Gallinari P,et al.Anovel embedding method for information diffusion prediction in social network big data[J]. IEEE Trans on Industrial Informatics,2017,3 (99): 1-11.   
[4]Kim R,Lim H, Krishnamachari B.Prefetching-based data dissemination in vehicular cloud systems [J].IEEE Trans on Vehicular Technology,2016,65 (1): 292-306.   
[5]康文文，李浩敏，汤超，等．面向复杂工程系统设计的云知识平台[J]. 系统工程与电子技术,2017,39(5):1078-1084.   
[6]Zheng X,Wang J,Dong W,et al.Bulk Data dissemination in wireless sensor networks:analysis,implications and improvement [J]. IEEE Transon Computers,2016,65(5):1428-1439.   
[7]王齐，钱宇华，李飞江．基于空间结构的符号数据仿射传播算法 [J]. 模式识别与人工智能,2016,29(12):1132-1139.   
[8]LiuY,Niu D,Khabbazian M.Cooper: Expedite Batch Data Dissemination in Computer Clusters with Coded Gossips [J]. IEEE Transon Parallel & Distributed Systems,2017,28 (8): 2204-217.   
[9]Liu Y,Wu H, Xia Y,et al. Optimal Online Data Dissemination for Resource Constrained Mobile Opportunistic Networks [J].IEEE Trans on Vehicular Technology,2017,66 (6): 5301-5315.   
[10]王练，梁申虎，彭代渊．多源多中继无线网络中基于随机线性网络编码 的调度方案[J]．电子与信息学报,2017,39(3):532-538.   
[11] Moharir S,Krishnasamy S,Shakkottai S.Scheduling in densified networks algorithms and performance [J]. IEEE//ACM Trans on Networking. 2017, 25 (1): 164-178.   
[12]Domingo-Prieto M,Chang T,Vilajosana X,et al.Distributed PID-based scheduling for 6tisch networks [J]. IEEE Communications Letters,2016,20 (5): 1006-1009.   
[13]林珲，游兰．虚拟地理环境知识工程初探[J].地球信息科学学报,2015, 17 (12): 1423-1430.   
[14] Garcia-Penalvo FJ. Engineering contributions to a multicultural perspective of the knowledge society [J].IEEE Revista Iberoamericana De Tecnologias Del Aprendizaje,2015,10 (1): 17-18.   
[15] Wu X, Chen H, Zhang Q,et al. Knowledge Engineering with Big Data [J]. IEEE Intelligent Systems,2015,30 (5): 46-55.