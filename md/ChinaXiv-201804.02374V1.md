# 多路GNSS 欺骗干扰互相关噪声模型

陈建华，陈树新，吴昊，何仁珂(空军工程大学 信息与导航学院，西安 710077)

摘要：为开展GNSS 欺骗干扰源定位研究，构建了多路GNSS欺骗干扰互相关噪声模型。首先分析了欺骗干扰原理并给出了信号模型；通过对噪声构成和规律的分析，研究建立了PRN码间互相关噪声模型；最后利用信噪比和欺骗信号方位角分布进行描述。仿真结果显示，多路GNSS欺骗干扰中码间互相关噪声，在接收通道噪声中的比重随欺骗信号功率增加趋于 $100 \%$ 。这表明测向精度与多路GNSS 欺骗信号功率是一组矛盾，实际测向结果可通过欺骗信号信噪比寻优。

关键词：卫星导航欺骗干扰；互相关噪声；信噪比；方位角分布 中图分类号：TN967.1 doi: 10.3969/j.issn.1001-3695.2018.02.0110

# Cross correlation noise model of multiple GNSS spoofing signals

Chen Jianhua, Chen Shuxin,Wu Hao, Chen Libo (College of Information &Navigation College,Air Force Engineering University,Xi'an 710o7,China)

Abstract: Inorder to carryout research oflocatingthe source of GNSS spoofing interference,this paper built amodel of multiple GNSS spoofing interference noise.Firstly,thispaperanalyzed thetheoryofspoofing and gave the mathematic models ofsignals.Then,itbuiltamodelofcrosscorelationinterferenceofPRNsbasedontheanalysis tocomposingandregularofthe noise.Fnally,this paper applied SNRanddistributionofazimuth todepictthe noise model.The simulationresults indicated that the weight of the crosscorrelation noise of multiple GNSS spoofing in the noise of receiver tended to $100 \%$ . It reveals that thedirectionprecision contradicts multiple GNSS spoofing power,andtheresult ofdirection finding can beoptimized bySNR of the spoofing.

Key words:GNSS spoofing interference; cross correlation noise; SNR;distribution of azimutl

# 0 引言

自美国的GPS成功开发以来，在全球范围的多个领域广泛应用。2017年11月5日我国的BDS-III“一箭双星”也刚刚发射升空，实现了由区域导航向全球组网的跨越，因此无论民用还是军事对GNSS的依赖程度都与日俱增，卫星导航对抗逐渐成为必须直面的重要课题。目前在军事领域，GNSS欺骗式干扰与抗干扰一直是卫星导航对抗领域的研究热点，分析欺骗干扰噪声成分并构建噪声模型，对研究欺骗干扰的本质属性和特点规律，增强GNSS欺骗干扰源定位能力具有重要意义。

在GNSS抗欺骗干扰研究领域，文献错误！未找到引用源。提出解扩之前在不分离欺骗信号和真实信号不同PRN 码的前提下，进行预解扩信号功率方差测试，以此来检测欺骗信号的存在与否；欧洲联合研究中心的 Borio 等人错误！未找到引用源。改进了（angle-of-arrival,AOA）检测，基于广义似然比检验，提出了对载波相位差的积分部分做平方和（sum-of-squares,SoS)处理，来检测欺骗信号的来波方位；文献错误！未找到引用源。提出了向欺骗信号的正交零空间发送接收信号，在独立于数个天线的子空间更为鲁棒地消除欺骗信号。

在 GNSS 欺骗干扰研究领域，文献[3]基于 JiST/SWANS(Java in simulation time/scalable wireless Ad-hoc networksimulator)仿真构建了GPS欺骗干扰模型并分析了其特点规律；文献错误！未找到引用源。通过研究欺骗信号和真实信号的信噪比和捕获跟踪误差，得出了一般化的欺骗信号功率控制方法;文献错误！未找到引用源。通过分析噪声基底，研究欺骗信号和真实信号的捕获概率，得出了多路欺骗信号的功率分配策略。

上述工作主要基于功率检测与控制、来波方向测量和干扰信号抵消等理论探索了GNSS干扰与抗干扰技术，对继续深入研究抗欺骗干扰的工程实践具有指导作用。然而在电磁环境日益复杂的今天，看似毫无关联的信号相互作用也可以产生严重的影响，例如今年4月份发生在成都双流机场的多起“无人机扰航”事件。为此本文立足GNSS欺骗干扰与抗干扰技术，从接收机噪声角度切入，构建多路GNSS欺骗信号互相关噪声模型，采用欺骗信号信噪比和欺骗干扰源方位角分布较为直观地描述了GNSS互相关噪声的分布特点与变化规律。

# 1 欺骗式干扰原理

GNSS欺骗式干扰不同于普通的干扰模式，按照这种方式工作的干扰源所发射的干扰信号形式与真实的GNSS信号是完全一样的，但其中用于解算PVT信息的数据却是虚假的。按照其虚假导航信息的来源不同，可分为生成式欺骗干扰和转发式欺骗干扰，两种欺骗方式都是通过改变伪距定位方程中的钟差时延量 $\Delta t$ 来达到欺骗接收机的目的，如式错误！未找到引用源。所示。

$$
\left\{ \begin{array} { l l } { \rho _ { 1 } { = } \sqrt { \left( x - x _ { 1 } \right) ^ { 2 } + \left( y - y _ { 1 } \right) ^ { 2 } + \left( z - z _ { 1 } \right) ^ { 2 } } + c \left( t + \Delta t \right) } \\ { \rho _ { 2 } { = } \sqrt { \left( x - x _ { 2 } \right) ^ { 2 } + \left( y - y _ { 2 } \right) ^ { 2 } + \left( z - z _ { 2 } \right) ^ { 2 } } + c \left( t + \Delta t \right) } \\ { \quad \quad \cdots \quad } \\ { \rho _ { n } { = } \sqrt { \left( x - x _ { n } \right) ^ { 2 } + \left( y - y _ { n } \right) ^ { 2 } + \left( z - z _ { n } \right) ^ { 2 } } + c \left( t + \Delta t \right) } \end{array} \right.
$$

假设GNSS接收机采用四星定位方式，则工作原理如图1欺骗干扰示意图所示。

![](images/3243816643c37d3ee75fe3b3fa5137266e2149f72fbc57e714b0b3956654eb9b.jpg)  
图1欺骗干扰示意图

以GPS信号为例，GNSS接收机利用卫星信号进行定位与授时作业是一个典型的CDMA通信过程。若干颗卫星采用不同PRN码对携带导航信息的数据码进行扩频处理，不仅可以增加通信系统容量，还可以使卫星信号具有较好的隐蔽性，之后再将扩频处理后的数据码调制到射频载波上发送出去，卫星发送的真实导航信号可以表示为

$$
s ^ { A } \left( n T _ { s } \right) = \sum _ { i = 1 } ^ { N } \sqrt { 2 P _ { i } ^ { A } } D _ { i } ^ { A } \left( n T _ { s } + \tau _ { i } ^ { A } \right) C _ { i } ^ { A } \left( n T _ { s } + \psi _ { i } ^ { A } \right) e ^ { j \left( 2 \pi f _ { i } ^ { A } n T _ { s } + \varphi _ { i } ^ { A } \right) }
$$

其中：上标 $A$ 标记真实卫星信号，下标 $i$ 表示真实信号的第 $i$ 路， $T _ { s }$ 为采样间隔， $P$ 是真实卫星信号功率， $D$ 和 $C$ 表示数据码和PRN码， $\tau$ 、 $\psi$ 和 $\varphi$ 分别表示数据码、PRN码和载波的初相位。

从信号模型层面来看，欺骗信号可以看做如式错误！未找到引用源。那样通过改变真实GNSS信号中的相位延迟信息来达到欺骗目的。

$$
\left\{ \begin{array} { l } { \tau ^ { s } = \tau ^ { A } + \Delta \tau } \\ { \psi ^ { s } = \psi ^ { A } + \Delta \psi } \\ { \varphi ^ { s } = \varphi ^ { A } + \Delta \varphi } \end{array} \right.
$$

仿照式错误！未找到引用源。，GNSS欺骗信号模型可以表示为

$$
s ^ { s } \left( n T _ { s } \right) = \sum _ { k = 1 } ^ { M } \sqrt { 2 P _ { k } ^ { s } } D _ { k } ^ { s } \left( n T _ { s } + \tau _ { k } ^ { s } \right) C _ { k } ^ { s } \left( n T _ { s } + \psi _ { k } ^ { s } \right) e ^ { j \left( 2 \pi f _ { k } ^ { s } n T _ { s } + \varphi _ { k } ^ { s } \right) }
$$

其中：上标 $S$ 标记欺骗信号，其余字母含义参考式错误!未找到引用源。。

# 2多路欺骗信号互相关噪声

# 1.1噪声来源

GNSS信号经过两万多公里的空间传播，到达地球表面附近时已经非常微弱，一般将其功率估计为-158dBW，而地面附近的环境热噪声却要远远高于这个水平，如果默认环境温度为$2 9 0 \mathrm { K }$ ，则在PRN码功率谱主瓣 $2 \mathrm { M H z }$ 带宽内的噪声功率一般可估计为-141dBW 错误!未找到引用源。，因此 GNSS 信号是隐藏于热噪声之下的，欺骗信号亦然，故在射频前端对欺骗信号进行分析显然是不现实的。GNSS接收机射频端接收的信号模型可以表示为

$$
s \left( n T _ { s } \right) = s ^ { A } \left( n T _ { s } \right) + s ^ { S } \left( n T _ { s } \right) + \xi \left( n T _ { s } \right)
$$

其中 $\xi \left( n T _ { s } \right)$ 表示环境高斯白噪声。

信号经过一级混频处理，中频信号送捕获跟踪，省略掉采样间隔，其第 $l$ 路做相关运算后的结果可以表示为

$$
\begin{array} { l } { { r _ { l } \left( K \right) = \sqrt { 2 { P _ { l } } ^ { A } } e ^ { j \varphi _ { l } } + \displaystyle \sum _ { i \neq l } ^ { N } \sqrt { 2 { P _ { i } } ^ { A } } F _ { i l } \left( K \right) + } } \\ { { \displaystyle \sum _ { k = 1 } ^ { M } \sqrt { 2 { P _ { k } ^ { S } } } F _ { k l } \left( K \right) + \eta \left( K \right) } } \end{array}
$$

$$
F _ { i l } \left( K \right) = \frac { 1 } { N } \sum _ { n = \left( K - 1 \right) N + 1 } ^ { K N } C _ { i } \left( n + \tau _ { i l K } \right) C _ { l } \left( n \right) e ^ { j \left( 2 \pi \Delta f _ { i l K } n + \Delta \varphi _ { i l K } \right) }
$$

式错误！未找到引用源。错误！未找到引用源。中： $K$ 表示做相关运算的两个信号的时间间隔， $\tau _ { i l K } \setminus \Delta f _ { i l K }$ 和 $\Delta { { \varphi } _ { i l K } }$ 分别表示第 $i$ 路本地同步信号与第 $l$ 路卫星信号之间的时延、多普勒频差和载波相位差， $\eta ( K )$ 表示高斯白噪声的相关值， $F _ { \mathit { k l } } \left( K \right)$ 的形式类似式错误!未找到引用源。，不再赘述。

从上述分析可以看出，存在GNSS干扰信号的接收机在处理信号时，除了受到环境热噪声的影响，还存在本地PRN码与接收信号做相关运算时产生的互相关干扰。

# 1.2互相关噪声模型

考虑到GNSS接收机接收到的欺骗干扰信号要强于真实信号，因此由欺骗信号混入而产生的互相关干扰对噪声水平的影响是不能忽略的。现假设有第 $m$ 路信号，该信号的PRN码与真实信号和欺骗信号的都不同，用它与接收机接收到的信号做相关运算来估计噪声水平。

以式错误！未找到引用源。为例，等号右边第一项是接收机的目标信号的相关结果，其他三项属于影响接收机工作的干扰信号相关结果。基于这样的分析，那么接收机噪声功率估计问题就可以转化成对码相关结果中的干扰项求方差的问题，如式错误！未找到引用源。所示。$\sigma _ { r _ { m } \left( K \right) } ^ { 2 } = \mathrm { v a r } \left[ \sum _ { i = 1 } ^ { N } \sqrt { 2 P _ { i } ^ { A } } F _ { i m } \left( K \right) + \sum _ { k = 1 } ^ { M } \sqrt { 2 P _ { k } ^ { S } } F _ { k m } \left( K \right) + \eta \left( K \right) \right]$ (8)假设真实信号和欺骗信号的多普勒频偏与延时都随机分布且相互独立，则上式可重写为

$$
\begin{array} { l } { { \displaystyle \sigma _ { r _ { m } ( K ) } ^ { 2 } = 2 \sum _ { i = 1 } ^ { N } P _ { i } ^ { A } \mathrm { v a r } \Big [ F _ { i m } \big ( K \big ) \Big ] + } } \\ { { \displaystyle 2 \sum _ { k = 1 } ^ { M } P _ { k } ^ { S } \mathrm { v a r } \Big [ F _ { k m } \big ( K \big ) \Big ] + \mathrm { v a r } \Big [ \eta \big ( K \big ) \Big ] } } \end{array}
$$

式错误！未找到引用源。中的var $\left[ F _ { i m } \left( K \right) \right]$ 和var $\left[ F _ { \mathrm { } k m } \big ( K \big ) \right]$ 是由两路不同 PRN 码信号互相关的结果，这两路信号中的PRN码都被随机多普勒频偏和相位差所调制。值得一提的是，该项中已经包含了接收机I/Q两支路信号，且满足均值为零的二维高斯分布，由于I/Q两支路信号的协方差微乎其微，则它们所服从的分布可以表示为$F _ { i m } \left( K \right) \sim N \left( \left[ \begin{array} { c c c } { { 0 } } \\ { { 0 } } \end{array} \right] , \left[ \begin{array} { c c c } { { \sigma _ { I , F _ { i m } } ^ { 2 } } } & { { 0 } } \\ { { 0 } } & { { \sigma _ { Q , F _ { i m } } ^ { 2 } } } \end{array} \right] \right)$ (10)

式错误!未找到引用源。中的由环境热噪声 $\eta ( K )$ 所产生的vai $: \left[ \eta ( K ) \right]$ 也服从如下分布：

$$
\eta ( K ) \sim N { \left( \left[ \begin{array} { l } { 0 } \\ { 0 } \end{array} \right] , \frac { \sigma _ { n } ^ { 2 } } { N } \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} \right] \right) }
$$

因此综合上述分析，GNSS 接收机的噪声水平估计 $\sigma _ { r _ { m } \left( K \right) } ^ { 2 }$ m(K)服从如下所示的高斯分布：

$$
\sigma _ { r _ { m } ( K ) } ^ { 2 } \sim N ( \begin{array} { c c c } { { \displaystyle { [ 0 ] } , \frac { N _ { 0 } } { 2 N T _ { s } } { [ 0  } } } & { { 0 } } \\ { { } } & { { } } \\ { { \displaystyle { 2 ( \sum _ { i = 1 } ^ { N } P _ { i } ^ { A } + \sum _ { k = 1 } ^ { M } P _ { k } ^ { S } ) } { [ \begin{array} { c c } { { \sigma _ { I , F _ { i m } } ^ { 2 } } } & { { 0 } } \\ { { 0 } } & { { \sigma _ { Q , F _ { i m } } ^ { 2 } } } \end{array} ] } ) } } \end{array} )
$$

上文中提到，GNSS 接收机射频前端的环境热噪声功率远远高于GNSS信号功率，因而在射频前端无论分析研究噪声还是欺骗干扰信号，都会遇到很大的困难。而式错误！未找到引用源。的得到，恰恰为解决上述问题提供了新的思路，在接收机载波环和码环输出端研究噪声水平以及欺骗干扰的特点，大大提高了工作效率。

# 2 互相关噪声模型描述

# 2.1 载噪比和信噪比

接收机接收到的信号功率大小还不足以反映信号质量的好坏，必须知道该信号是在什么样的噪声环境里得到的，简言之，信号与噪声的相对强弱才能准确描述信号质量的好坏。在一般的热噪声环境里，载噪比 $C / N _ { 0 }$ 已经能充分描述信号的质量，其定义为

$$
C / N _ { 0 } = \frac { P _ { r } } { N _ { 0 } }
$$

其中： $P _ { r }$ 表示接收信号的功率， $N _ { 0 }$ 是单位带宽上的热噪声功率，一般取-204dBW/Hz（温度 $2 9 0 \mathrm { K }$ )。

然而在上文的分析中，混入欺骗信号的接收机中不仅有热噪声，还有欺骗信号引起的互相关干扰，因此单纯的载噪比已无法适应对欺骗信号的研究，为此引入信噪比SNR来替代载噪比，在只有热噪声的系统中，SNR 与 $C / N _ { 0 }$ 仅差一个相干积分时间 $T _ { c }$ ：

$$
S N R = \big ( C / N _ { 0 } \big ) T _ { c } { = } \frac { P _ { r } } { N _ { 0 } B _ { n } }
$$

考虑应用到本文中，应该用上文的噪声水平估计来作为分母，那么欺骗信号的信噪比应该表示为

$$
S N R { = } \frac { P _ { r } ^ { S } } { \sigma _ { r _ { m } ( K ) } ^ { 2 } }
$$

式错误!未找到引用源。中，欺骗信号功率 $P _ { r } ^ { s }$ 的增加，会引起接收机噪声水平 r(k)的抬高，但是二者变化规律相对$C / N _ { 0 }$ 较为直观的变化规律不同，下文的仿真也会进一步说明

# 2.2欺骗干扰源的测向模型

考虑在卫星导航对抗中对欺骗干扰源测向定位的需求，本文采用互相关噪声环境对方位角测量带来的影响进行评价。无线电测向的方法很多，例如振幅法、相位法和空间谱估计等，本文选取相位干涉测向中较为简单的二单元干涉仪作为测向方法。

![](images/bf23cf1707801efefb08d6cbab10bdabd68a69c80cf2b3551328b6062fcb1615.jpg)  
图2二单元干涉仪测向

如

图2所示，两个天线单元之间的连线称为测向基线，其间距 $D$ 被称为天线孔径，一般用 $D$ 与待测电波的波长 $\lambda$ 的比值来衡量测向误差的精度，该比值一般取1\~2，越大测向结果越精确。

当待测信号较强时，若测向设备不受任何干扰，忽略测向系统误差，且该体制下相位模糊问题已经得到很好地解决，则对GNSS欺骗信号的结果可用式错误！未找到引用源。表示，$\Delta \varphi$ 表示两个天线单元所接收信号的相位差。

$$
\theta { = } \arcsin \left( \frac { \lambda \Delta \varphi } { 2 \pi D } \right) , \quad 0 { \leq } \theta { \leq } 9 0 ^ { \circ }
$$

# 2.3欺骗干扰源方位角分布

在实际对欺骗干扰源的测向定位中，电磁环境不会是上文所假设的理想状态，接收到的信号中不仅存在自然噪声，很有可能混入人为干扰，这些都会使干扰源的方位角测量结果存在较大的方差。据研究，在二单元干涉测向体制下，方位角方差$\boldsymbol { \sigma } _ { \theta } ^ { 2 }$ 的大小与所测得的 $\Delta \varphi$ 的方差 $\sigma _ { \varphi } ^ { 2 }$ 有关，其关系可用式错误！未找到引用源。表示。

$$
\sigma _ { { \boldsymbol { \theta } } } = 2 \arcsin ( \frac { \lambda \sigma _ { \varphi } } { 4 \pi D } )
$$

在大信噪比条件下，两个天线单元所测得相位差的方差$\sigma _ { \varphi } ^ { 2 }$ 可以用下式来描述：

$$
\sigma _ { \varphi } = \sqrt { \frac { 1 } { 2 S N R } }
$$

基于上述理论分析，采用MonteCarlo仿真思路对干扰源的方位角进行多次测量，则GNSS欺骗干扰源的方位角应当服从如下分布：

$$
\theta ^ { s } \sim N \left( \overline { { \theta ^ { s } } } , 2 \arcsin \left( \frac { \lambda \sqrt { \sigma _ { r _ { m } ( K ) } ^ { 2 } \big / \big ( 2 P _ { r } ^ { s } \big ) } } { 4 \pi D } \right) \right)
$$

式错误！未找到引用源。从理论上看是符合工程实践规律的，

在反三角函数线性性质较好的区域内，方位角方差与系统噪声成正比，与GNSS欺骗干扰信号成反比。

# 3 仿真实验

# 3.1噪声估计

根据式错误！未找到引用源。的结论，假设进入接收机码环的欺骗信号和真实信号各有10路错误!未找到引用源。，且单路真实导航信号功率为-158dBW。文献错误！未找到引用源。指出标准化功率的金码互相关方差一般为 $\sigma _ { { I , i m } } ^ { 2 } = \sigma _ { { 0 , i m } } ^ { 2 } = 0 . 0 0 0 3 3$ ，相关积分时间 $T _ { c } = N T _ { s }$ 分别取1ms、2ms、4ms 和 $8 \mathrm { m s }$ ，仿真结果如

![](images/ac85c4d4eae3fb4e241c81874114b64da117a92c4afad31f32b788542a7ee5ef.jpg)  
图3所示。

![](images/385fb1a76e45f3e7932c0736011481c61b7a9fbe20693de10da730480cd550eb.jpg)  
图3接收机噪声水平估计

考虑到接收机码环处理过程中的噪声来源至少有两部分，对PRN码的互相关噪声所占比重也做了仿真分析，结果如图4所示。

![](images/e0c616e78fb381c1ab06abe65751e73a19f556f9d5ce4e58d2c2e72d77c64de1.jpg)  
图4互相关干扰在噪声估计中的权重

根

![](images/906a46469cc4b74994404b4ec6b2ae570f5f70a034f88fadd84858ae418554ce.jpg)

图3的仿真结果，当欺骗信号总功率小于-140dBW时，噪声水平至少低于真实信号功率 $1 2 ~ \mathrm { d B }$ ，且此时相干积分的时间长短对噪声水平估计的影响比较显著，具体表现为相干积分时间越长，噪声水平越低，这与理论分析中积分器的低通滤波属性密切相关；当欺骗信号总功率大于 $. 1 4 0 \mathrm { d B W }$ 时，相干积分时间对噪声水平估计的影响基本可以忽略不计，并且欺骗信号总功率大约-126dB左右时，噪声水平会迅速超越真实信号功率。

图4的仿真结果，一方面展示了接收机中PRN码互相关噪声随欺骗干扰信号功率增加而不断增大，并且占整个接收机噪声的权重不断增加，趋近 $100 \%$ ；另一方面说明了相干积分时间对互相关噪声在噪声整体中比重的影响，相干积分时间越长互相关噪声比重越大，间接反映了互相关噪声的低频属性和环境热噪声的高频属性。

# 3.2 载噪比及信噪比

根据载噪比的定义，首先对单路欺骗信号和真实信号的载噪比进行仿真， 结果如

![](images/37ee7a5710b3deb98b4ca104ae7bdbec89a2d2f470431a62057fb231ce1ab7f1.jpg)

图5，图中欺骗信号载噪比随欺骗信号总功率的增加线性增大，而真实信号载噪比保持恒定，这个结果显然只考虑了环境热噪声对信号质量的影响，忽略了PRN码间互相关噪声的影响，因此无法准确反映接收机中的信号清晰程度。

![](images/1b338fdbeb4231f031649a6ef22e26e53711367090ccdd2b4830681f62c5e736.jpg)  
图5载噪比分析

开

![](images/113c70438d111119bd2e8545b77f80acd49c81f02d9dd6e8ea1a5c8d5171c2bd.jpg)  
抛

图5的仿真结果，根据上文的理论分析再做信噪比仿真研究，单路欺骗信号功率取10路总功率的平均值，噪声水平估计中的相干积分时间取1ms，仿真结果如

![](images/7eed91571dd8a94710bbd744848aa2e17971fa34c501ab2a8e14c232094216de.jpg)  
图6所示。

![](images/6ee34b203ce938613e3a688b810541dbf31f23818d10c7df7d693fbb3704bbe4.jpg)  
图6信噪比分析

对比

图5、6的仿真结果，毫无疑问后者的参考价值更高一些，随着噪声水平的不断抬高，欺骗信号的信噪比上升速度逐渐趋缓，直至基本保持恒定，而真实信号的信噪比以较快的速度不断降低，没有任何趋缓的征兆。

可 以 根 据

![](images/1a9da42d54da5d3ccb00cfba9a77260f74bceb949d0ca8563e34e27d72aa3719.jpg)

图6的仿真结果换位思考一下，假设敌方以本文设定的模式对我方实施欺骗干扰，可以推测欺骗总功率选择肯定不会超过-130dBW，因为再增加功率不仅会增加暴露干扰源位置风险、提高干扰的实施成本，而且干扰的效果不会得到明显的改善，工程上对欺骗干扰的检测也可以此作为参考。

![](images/228eae7ae288ed29d8e57295a4f4e2003aa605e588ae6a599d25144c3b340c24.jpg)  
图7GNSS干扰源方位角方差

# 3.3干扰源方位

假设 GNSS 欺骗干扰源工作在 $1 ~ 5 7 5 ~ \mathrm { M H z }$ ( $\lambda { = } 1 9 c m$ ，GPS系统L1载波)，测向机原理采用上文提到的方法，天线孔径 $D$ 取1，相干积分时间取1ms、 $2 \mathrm { m s }$ 、 $4 \mathrm { m s }$ 和 $8 \mathrm { m s }$ ，仿真结果

![](images/b4d657202f46cf572e674c943b0878b8265c42d7555b07a8575c1cff25494f3b.jpg)  
图7所示。

16 14 046 p 1210 8 464 -3.305 -3.3 单路欺骗信号SNR[dB] 6 4 T c=1ms -T c=2ms 2 -Tc=4ms 品 Tc=8m6 0 5 10 15 20 单路欺骗信号SNR[dB]

仿真结果表明，该测向体制下对GNSS欺骗干扰源测量结果的方差是类指数形式递减的。假设对

![](images/5b9e6d4813299fc1dc737e4db56b5218d7c8260968fc0c05714d2b2322bc3420.jpg)

图6的分析推测合理，欺骗信号总功率不超过-130dBW，则单路欺骗干扰信号的信噪比不会高于 $1 8 . 6 \mathrm { d B }$ ，那么对其干扰源的测量误差就不会低于0.76[degree]。

值得格外注意的是 ，

161412epl 9.454 9.452-3.305 -3.3单路欺骗信号SNR[dB]4 Tc=1ms-Tc=2ms2 - -T c=4msT c=8ms0-10 -5 0 5 10 15 20单路欺骗信号SNR[dB]

图7的仿真结果告诉我们，单纯延长相干积分时间对降低角度测量方差意义不大，这对角度测量实践时的数据采集时间长短具有指导意义，该分析也与上文互相关干扰在噪声估计中的比重分析结论相吻合。

# 4 结束语

本文针对目前GNSS欺骗干扰源定位的需求，研究了存在多路欺骗干扰信号时的噪声来源、概率分布特点和变化规律，构建了接收机中PRN码间互相关噪声模型，并采用信噪比和欺骗干扰源方位角分布较为直观地阐释了GNSS接收机噪声的特点与规律，得出如下结论：

a)多路GNSS欺骗干扰信号所引起的PRN码间互相关干扰不可忽视，且在接收机噪声中的权重随欺骗信号功率增加而增大，最终趋于 $100 \%$

b)SNR较CNR更能准确反映存在欺骗干扰时接收机中信号的清晰程度，且基于功率检测的抗欺骗干扰技术在必须-130dBW以下仍然保持较高的效率；

c)单路欺骗信号的SNR不会高于18.6dB，二单元相位干涉测得的方位角方差不低于0.76[degree]，且单纯延长相干积分时间对提高方位角测量精度意义不大。

# 参考文献：

[1]Broumandan A, Siddakatte R, Lachapelle G.Feature article: an approach to detect GNSS spoofing [J]. IEEE Aerospace & Electronic Systems Magazine, 2017,32 (8): 64-75.   
[2]Borio D, Gioia C.A sum-of-squares approach to GNSS spoofing detection [J].IEEE Trans on Aerospace & Electronic Systems,2016,52 (4):1756- 1768.   
[3]Han Shuai, Chen Lei,Meng Weixiao,et al.Improve the security of gnss receivers through spoofing mitigation [J]. IEEE Access,2017,PP(99): 1.   
[4]Schmidt D,Radke K, Camtepe S,et al.A survey and analysis of the gnss spoofing threat and countermeasures [J].ACM Computing Surveys,2016, 48 (4): 64.   
[5]胡彦逢，边少锋，曹可劲，等.GNSS 接收机欺骗干扰功率控制策略[J]. 中国惯性技术学报,2015,23(2):207-210.(Hu Yanfeng,Bian Shaofeng, Cao Kejin,et al. Spoofing power control strategy for GNSS receiver [J]. Journal of Chinese Inertial Technology,2015,23 (2):207-210.)   
[6] 黄森，陈树新，杨宾峰，等．多路 GNSS 欺骗干扰信号功率控制策略 [J].空军工程大学学报·自然科学版,2017,18(1):76-80.(Huang Sen, Chen Shuxin,Yang Binfeng,et al.A power control strategy of multiple GNSS spoofing signals [J]. Journal of Air Force Engineering University (Natural Science Edition),2017,18(1): 76-80.)   
[7]谢钢.GPS 原理与接收机设计 [M]．北京：电子工业出版社,2009.(Xie Gang.Principles of GPS and receiver design [M].Beijing:Publication House of Electronics Industry,2009.)   
[8] 黄龙，龚航，朱祥维，等.针对GNSS 授时接收机的转发式欺骗干扰技 术研究[J].国防科技大学学报,2013,35(4):93-96.(HuangLong,Gong Hang,Zhu Xiangwei,et al. Research of re-radiating spoofing technique to GNSS timing receiver [J].Journal of National University of Defense Technology,2013,35 (4): 93-96.)   
[9]Nielsen J, Dehghanian V,Lachapelle G.Eectiveness of GNSS spoofing countermeasure based on receiver CNR measurements [J]. International Journal of Navigation and Observation,2012,2012（7).