# 基于Hilbert-Huang变换与支持向量机的故障电弧检测研究

![](images/4aee250d461fcb5118338b9c5b214ad0b7937fb27d97106e1bf93aa6d9750f5f.jpg)

张湛男1966年生，本科，工程师，研究方向为电力系统设计和电力系统智能技术。

![](images/2707d621efb5fe0cd91f2a841d3b0081114f9a5223c86301a732cbbe315e8b64.jpg)

杨光男1989年生，博士研究生，研究方向为电工理论与新技术、故障诊断与检测技术和现代轨道交通技术等。

张湛杨光²张峰²（1.中国电力工程顾问集团中南电力设计院武汉 4300712.上海交通大学电子信息与电气工程学院上海200240）

摘要：随着国内用电设备增多，电气火灾的发生率也有所升高，故障电弧检测的研究成为当今热点。本文提出一种Hilbert-Huang 变换与支持向量机相结合的方法，其中采用Hilbert-Huang变换对不同负载电流波形进行时域分解，从而提取各模态分量的特征值。然后采用支持向量机的自适应分类方法，通过学习不同负载下Hilbert-Huang变换得到的特征值，自适应地区分正常运行状态与故障电弧运行状态。本文以调光灯、电吹风高档、电吹风低档、电风扇和电水壶等5种类型的常用负载作为研究对象，验证算法的正确性。

关键词：故障电弧检测 故障电弧断路器 Hilbert-Huang 变换支持向量机中图分类号：TM711

# Research of Arc Fault Detecting Based on Hilbert-Huang Transformation and Support Vector Machine

Zhang Zhan' Yang Guang² Zhang Feng² (1.Central Southern China Electric Power Design Institute of China Power Engineering Consulting GroupWuhan 430071 China 2.Shanghai Jiao Tong UniversityShanghai200240China）

Abstract: With the increasing consumption of electric equipment, the occurring rates of electrical fires also rise in a high speed. This paper proposes a method combine HilbertHuang Transformation (HHT) and Support Vector Machine (SVM).We adopt the HHT to decompose the current waveform in different kinds of loads,and analyze the Intrinsic Mode Function from time domain and frequency domain.The SVM learns characteristic value in different loads,thus identification of normal condition and arc fault condition can be done in an adaptive way. This paper takes five kinds of common loads (dimmer, drier with high power, drier with low power,fan,heater, etc.） for the research object to verify the validity of the proposed method.

Keywords: Arc detecting,arc fault circuit interrupter, Hilbert-Huang transformation, support vector machine

# 1 引言

随着工业用电的不断发展和家庭用电设备的不断普及，火灾事故发生的频率也逐年上升。其中，电气原因引起的火灾也占很大比例。住宅内的电气线路、电源线或用电设备内部线路等，长时间运行在过载条件下可能会造成电线绝缘层的老化和破损，从而导致电弧故障的产生。插头与插座之间接触不良也可能导致故障电弧的产生。虽然低压电弧的负荷电流很小，但是其温度可达到上千度，使线路中的绝缘层烧毁，同时引燃周围的可燃物，最终酿成火灾。传统的保护装置虽然可以对线路的中短路、欠电压、过电压和过载等情况提供必要的保护，但是当线路中发生低压电弧故障时，线路中的电流幅值与正常运行时的电流幅值相差无几，因此，无法检测出是否产生了电弧故障，为室内火灾埋下隐患，对人们的生命财产的安全构成了严重威胁。于是，有必要开发一套专门针对电弧故障的线路保护装置取代传统的电流断路器、过电流断路器和熔断器等线路保护装置，电弧故障断路器（ArcFaultCircuitInterrupter，AFCI）应运而生[1]。

国外很早就开始着手研究故障电弧，19世纪20年代，Cassie和Mayr等人相继提出电弧动态模型理论。Schavemaker结合Cassie 模型和Mayr模型的优点，提出了Schavemaker数学物理模型[2]。1998 年，George D.Gregory 和 Gary W. Scott 等人提出电弧断路器的概念，从此，故障电弧进入了民用化时代[3]。1999年2月，美国保险商试验室制定了UL1699《电弧故障断路装置安全标准》（standardfor safety for arc fault circuit interrupters）[]，规定了不同类型AFCI的性能参数、安全试验测试项目及试验方法等，使AFCI的测试环境及性能指标更加规范化，有利于低压故障电弧课题的进一步深入。2002年，美国国家防火协会（NationalFireProtectionAssociation，NFPA）制订了美国国家电气法规（NationalElectricalCode，NEC），规定所有在室内安装的支路必须安装故障电弧断路器以保护整条支路，同时还要求单相、电源线加插头连接的室内空调也要配备AFCI保护装置[4]。2009 年,E.Carvou与N.BenJemaa 等人对不同功率阻性负载下的电压幅值、燃弧时间、电流幅值和击穿电压等进行了研究比较，归纳出 $1 2 0 \mathrm { V }$ 、 $6 0 \mathrm { { H z } }$ 系统和120V、 $5 0 \mathrm { { H z } }$ 系统故障电弧特性的异同[5]。

# 2 Hilbert-Huang变换

Hilbert-Huang 变换 （Hilbert-Huang Transform,HHT）是由美籍华人黄谔（NordenEHuang）教授于1998年提出的。该方法是一种基于经验的后验的方法，其自适应性和处理非平稳信号上的优势使该方法被广泛运用于地震、水波、心音、机械振动和电网负荷等数据的处理中。HHT由经验模态分解(Empirical Mode Decomposition，EMD） 和Hilbert变换（Hilbert Transform，HT）两部分组成。EMD将原始数据分解成多层分量。Hilbert变换将时域信号变换到时间－频率域，从而可以对信号进行频谱分析和能量分析。

# 2.1经验模态分解

EMD是将任何信号（包括线性信号、非线性信号、平稳信号和非平稳信号等）通过一定的筛分条件进行经验模态分解，分解成多个固有模态分量(IntrinsicModeFunction，IMF）和一个残余量的和的形式[。EMD分解的目的是将一个复杂时域信号按照频率的高低分解为若干个满足Hilbert变换条件的固有模态分量，从而能够通过Hilbert变换求解各分量的瞬时频率。瞬时频率能反映信号的本质特征。

EMD方法与以前的其他方法不同，该方法是将信号本身作为尺度函数对信号进行筛分，因此该方法具有一定的自适应能力。不仅如此，该方法更关注局部极值点，因此有利于细节信号的分析。

EMD分解可以将任何信号分解为多个固有模态函数和一个残余量的和的形式，即

$$
x ( t ) = \sum _ { j = 1 } ^ { n } c _ { j } ( t ) + r _ { n } ( t )
$$

其中

$$
c _ { j } ( t ) = a _ { j } ( t ) \cos \left[ \int \omega _ { j } ( t ) \mathrm { d } t \right]
$$

式中， $c _ { j } ( t )$ 为原始信号分解后得到的固有模态分量，该分量可表示成幅值和相角的形式； $r _ { n } ( t )$ 为原始信号经过多次EMD提取后最后得到的残余量，表征信号在时间轴上的趋势。具体筛分步骤如下所示[7：

（1）筛选出原始信号的所有局部极大值点和局部极小值点。

(2）用3次样条插值方法分别构建局部极大值 与局部极小值的拟合曲线，构建局部极大值包络和 局部极小值包络。

(3）计算算数平均。

(4）提取细节信号。

(5）判断细节信号是否满足筛分停止条件。如果不满足，则将作为原始信号继续回到步骤（1）迭代筛分；如果满足，则将作为一个固有模态分量。

(6）将原信号中的该固有模态分量去除，继续回到步骤（1）提取下一个固有模态分量。

该筛分步骤可以通过程序流程图清晰表示。如图1所示。

![](images/397b26b60431e99fb084726bf6cd6d2328a009b779ecc60bf0620f4908850468.jpg)  
图1EMD 筛分过程流程图

其中，EMD分解出的IMF分量需要符合以下两个要求：

（1）IMF的极大极小值个数之和与过零点数目至多相差一个。(2）IMF在任意时间点的上下包络算数平均值为0。原信号去除IMF后得到的细节信号是残余量 $\boldsymbol { r } _ { n }$ 的判断标准为：(1) $\boldsymbol { r } _ { n }$ 小于某一阈值。(2） $\boldsymbol { r } _ { n }$ 为时间的单调函数。EMD方法具有几个最突出的特性，包括：自适应特性、正交性、完备性以及分量调制特性[]。

# 2.2 Hilbert谱分析

EMD分解得到多个固有模态分量和一个残余量后，各分量作Hilbert变换。Hilbert变换定义如下

$$
H ( t ) = \frac { 1 } { \pi } \int _ { - \infty } ^ { + \infty } \frac { c ( \tau ) } { t - \tau } \mathrm { d } \tau
$$

傅里叶变换是Hilbert变换的特殊形式。可以得出结论：傅里叶变换仅适用于平稳信号的频谱分析，而Hilbert变换既适合平稳信号频谱分析，也适合稳信号的频谱分析。

原始信号经过EMD分解和Hilbert变换，进而得到“Hilbert谱”。Hilbert 谱结合了EMD分解的滤波特性，将分解得到的窄带信号通过Hilbert变换，克服了傅里叶变换单一幅值和固定频率的局限性。

Hilbert边际谱被定义为

$$
h ( \omega ) = \int _ { 0 } ^ { T } H ( \omega , t ) \mathrm { d } t
$$

式中， $h ( \omega )$ 为Hilbert边际谱； $H ( \omega , t )$ 为Hilbert谱;  
$T$ 为采样时间长度。

Hilbert边际谱与傅里叶频谱类似，反映了信号的幅值随频率变化的趋势，二者最大的不同在于Hilbert边际谱中的极值点表示该频率在信号中曾经出现过，而傅里叶频谱中的极值点表示平稳信号可以在整个时间域中分解出该频率的正弦信号。Hilbert边际谱的最高瞬时频率可以与信号的采样率相等，而傅里叶频谱的最高分辨率仅为信号采样率的一半。因此，Hilbert边际谱相对于傅里叶频谱的优势在于它具有更高的分辨率[10]。

# 3支持向量机

支持向量机是CorinnaCortes 和Vapnik等于1995年首先提出并发展起来的基于统计理论的机器学习方法。该方法根据有限样本信息在模型的复杂性和学习能力之间寻求最佳折中，从而达到在样本量较少的情况下也能获得良好统计规律的目的。考虑两类样本线性可分，线性判别函数的一般形式为

$$
f ( x ) = w ^ { \mathrm { T } } x + b
$$

式中， $x$ 为 $n$ 维向量数据点； ${ \bf \nabla } _ { \pmb { \mu } } \psi$ 为权重向量； $b$ 为偏置。SVM的基本原理如图2所示。

![](images/94504c0862290cd704e61d39c798668bb472fb1d9ffdaf1ed89e8a3eccb93636.jpg)  
Fig.1Flowchart of sifting process   
图2SVM基本原理Fig.2 SVM principle

对于一个线性可分训练样本： $S = ( ( x _ { 1 } , y _ { 1 } )$ 。…，$( x _ { \mathrm { n } } , y _ { \mathrm { n } } ) )$ ，以符号“ $\bigcirc$ ”和“ $\cdot$ ”分别表示两类不同样本点，其中，方程 $( W \cdot X ) + b = 0$ 就为最优划分超平面。 $\mathbf { \mathcal { W } }$ 为超平面的法向量。方程 $\left( W \cdot X \right) + b = - 1$ 与 $( W \cdot X ) + b = 1$ 分别被称为左边界与右边界。引入松弛变量 $\xi _ { i }$ ，作为容忍噪声和离群点的度量，目标函数变为

$$
f ( x ) = \mathrm { s g n } \left( \sum _ { i = 1 } ^ { n } y _ { i } \alpha _ { i } K ( x _ { i } , x ) + b \right)
$$

式中， $x _ { i }$ 为训练数据； $x$ 为测试数，从而形成支持向量机网络。

# 4 电弧故障辨识

$$
{ \mathrm { m i n i m i s e } } \quad { \frac { 1 } { 2 } } \left\| w \right\| ^ { 2 } + C \sum _ { i = 1 } ^ { n } \xi _ { i }
$$

$$
y _ { i } ( w ^ { \mathrm { T } } x _ { i } + b ) \geqslant 1 - \xi _ { i } \quad i = 1 , \cdots , n
$$

$$
\xi _ { i } \geqslant 0 \quad i = 1 , \cdots , n
$$

式中， $C$ 为惩罚因子。引入核函数

$$
\mathrm { a x i m u m } \quad \sum _ { i = 1 } ^ { n } \alpha _ { i } - \frac { 1 } { 2 } \sum _ { i , j = 1 } ^ { n } y _ { i } y _ { j } \alpha _ { i } \alpha _ { j } K ( x _ { i } , x _ { j } )
$$

$$
\sum _ { i = 1 } ^ { n } \alpha _ { i } y _ { i } = 0
$$

表1中列出了5种常见的家用电器负载，这些负载包含了阻性负载、开关特性负载和容性负载3种类型。

# 表1家庭常用负载

Tab.1 The common loads in household   

<html><body><table><tr><td>序号</td><td>负载</td><td>功率/W</td><td>类型</td></tr><tr><td>1</td><td>电水壶</td><td>1000</td><td>阻性</td></tr><tr><td>2</td><td>电吹风高档</td><td>1000</td><td>近似阻性</td></tr><tr><td>3</td><td>电吹风低档</td><td>600</td><td>开关电源</td></tr><tr><td>4</td><td>电风扇(电容起动型）</td><td>50</td><td>容性</td></tr><tr><td>5</td><td>调光灯</td><td>1000</td><td>开关电源</td></tr></table></body></html>

决策函数写作如下形式

图3对这5种负载正常运行与故障电弧下的电

2.0 2.01.5 1.51.0 1.0 M0.5 0.5  
A 0 IA 0-0.5 -0.5-1.0 -1.0-1.5 -1.5A-2.0 -2.00 0.010.020.030.040.050.060.070.080.090.10 0 0.010.020.030.040.050.060.070.080.090.10t/s t/s正常运行 电弧故障(a）电水壶负载1.5 1.51.0 GWW0.5  
小 0 A-0.5-1.0-1.5 -1.50 0.010.020.030.040.050.060.070.080.090.10 0 0.010.020.030.040.050.060.070.080.090.10t/s t/s正常运行 电弧故障

(b）电吹风高档

![](images/55a63f4ad484e48af3ad118be5e412d6ff95ee4481e2f3aa5b79b871ced362c4.jpg)  
图3正常运行与故障电弧运行电流波形对比  
Fig.3 Currents comparison between normal and arc fault

流波形进行比较，并展示了二者的异同。

将5种类型的样本数据经过归一化和平滑预处理后，EMD分解，得到每个IMF分量的边际谱。图4给出阻性负载电水壶负载的EMD分解形式。

根据图4可以看出，电水壶负载正常情况下分解为2个IMF分量和1个残余量，电水壶故障负载可分解3个IMF分量和1个残余量。电水壶负载故障电弧状态在电流过零点处有明显的平肩。因为EMD分解是自适应地根据信号自身来决定分解频段的带宽，因此该平肩导致故障运行的EMD分量个

0.8 0.6 8 0 0.01 0.02 0.03 0.04 0.05 0.060.07 0.08   
新 8 -0.2 0.4 0 0.01 0.02 0.03 0.04 0.05 0.06 0.07 0.08 1i 8 -0.2 -0.4 T 0 0.01 0.02 0.03 0.04 0.05 0.060.07 0.08 1A 0.4985F 差 0.4984 残 0.4984 0 0.01 0.02 0.03 0.04 0.05 0.060.07 0.08 t/s (a）正常运行EMD分解 6 0.4 0.2 0 0.01 0.02 0.03 0.04 0.05 0.06 0.07 0.08   
新 0.5 0 -0.5 0 0.01 0.02 0.03 0.04 0.05 0.06 0.07 0.08   
美 0.5 0 -0.5 0 0.01 0.02 0.03 0.04 0.05 0.06 0.07 0.08 /美 0.5 0.45 0 0.01 0.02 0.03 0.04 0.05 0.06 0.07 0.08 t/s (b）故障电弧状态运行EMD分解

数以及每个频率段的信号复杂程度要高于正常运行状态。

根据IMF分量的边际谱的峰值情况，可以将多个频率段的IMF分量进行重新归类，从而避免了EMD分解的过分类状况。根据多种负载的多组数据进行采样分析以及HHT变换后，根据经验可以将频率成分分为4类，并规定阈值如下：

（1）IMF峰值频率 $> 2 5 0 \mathrm { H z }$ ，阈值为0.05。  
(2）IMF峰值频率在 $2 0 0 \sim 2 5 0 \mathrm { H z }$ ，阈值为0.05。  
(3）IMF峰值频率在 $1 0 0 \sim 2 0 0 \mathrm { H z }$ ，阈值为 $0 . 0 5$ 。  
（4）IMF峰值频率为 $5 0 \sim 1 0 0 \mathrm { H z }$ ，阈值为0.1。

需要通过以上步骤得出用于区分正常运行和有电弧故障发生情况下的特征值点。第一个特征值为超过阈值的采样点个数，用于判别正常运行于故障电弧运行状态存在的差异，也可以体现出各负载的特征值存在的差异。

第二类特征值为各类分量的极大值和极小值个数。该特征值是为了提取各分量的形状特征而设定的。由于一般情况下故障电弧运行状态下纹波数要多于正常运行状态，因此极大值与极小值个数是较为有效的判别标准。

对于调光灯负载、电扇负载以及电吹风低档负载来说，发生故障电弧时，不同周期的峰值会随机变化，每个周期幅值围成的面积也有所不同。因此确定第三组分类特征值，即：将各周期的离散幅值累加，然后对相邻周期的累加和求差值的绝对值，最后求取差值的最大值。该最大值则为所需的特征量。

将采集信号经过Hilbert-Huang变换得到211特征值样本，将其分为两类，其中107个样本作为训练样本，用于确定SVM模型。剩余的104个样本用于测试SVM模型的分类精度。这211个样本见表2。选取C-SVC（C-SupportVector Classification）分类方法，选取最大进化代数为300，参数 $\mathbf { \Psi } _ { c }$ 和 $g$ 的初值分别设为1.5与1.7，可以得出测试样本的最高分类精度可达 $9 9 . 0 3 8 ~ 5 \%$ 。

表2分类样本组成  
Tab.2 Component of classifying instances   

<html><body><table><tr><td></td><td>训练样本数</td><td>测试样本数</td></tr><tr><td>调光灯正常</td><td>11</td><td>10</td></tr><tr><td>调光灯故障</td><td>10</td><td>10</td></tr><tr><td>电吹风高档正常</td><td>10</td><td>10</td></tr><tr><td>电吹风高档故障</td><td>13</td><td>12</td></tr><tr><td>电吹风低档正常</td><td>13</td><td>12</td></tr><tr><td>电吹风低档故障</td><td>10</td><td>10</td></tr><tr><td>电风扇正常</td><td>10</td><td>10</td></tr><tr><td>电风扇故障</td><td>10</td><td>10</td></tr><tr><td>电水壶正常</td><td>10</td><td>10</td></tr><tr><td>电水壶故障</td><td>10</td><td>10</td></tr></table></body></html>

# 5 结论

本文提出一种基于Hilbert-Huang变换与支持向量机相结合的故障电弧辨识方法，通过EMD分解提取故障电弧的特征量，然后结合SVM来区分正常运行状态下的电流波形和故障电弧运行状态下的电流波形。该方法可以适应不同负载对电弧辨识产生的影响，将辨识分类问题简化为两值分类问题。经过试验验证，该方法能够有效识别故障电弧状态。

# 参考文献

[1] UL1699,UL Standard for Safety for Arc Fault

Circuit Interrupters[S].2nd Edition,2006.   
[2] Schavemaker P H,Van der Slui L.An improved mayr-type arc model based on current-zero measurements[circuit breakers][J].IEEE Transactions on Power Delivery,20o0,15(2):580- 584.   
[3] Gregory G D,Scott G W. The arc-fault circuit interrupter,an emerging product[C]. IEEE Industrial and Commercial Power Systems Technical Conference, 1998:48-55.   
[4] Tom Potter，颜培荣．AFCI技术在家用空调电源 插头中的应用[J]．电器，2004(9)：36-37. Potter T,Yan Peirong.Application of AFCI in Power plug for household air conditioner[J]. China Appli ance,2004,(09):36-37.   
[5] CarvouE,BenJemaaN.Electrical arc characterization for ac-arc fault applications[C]. Proceedings of the 55th IEEE Holm Conference on Electrical Contacts, Vancouver,2009:21-26.   
[6] 钱昌松，刘代志，刘志刚，等．基于递归高通滤波 的经验模态分解及其在地震信号分析中的应用[J]. 地球物理学报，2010，53(5)：1215-1225. Qian Changsong,Liu Daizhi, Liu Zhigang,et al. EMD based on recursive high-pass filter and its application on seismic signal analysis[J]. Chinese Journal of Geophysics,2010, 53(5): 1215-1225.   
[7] Rilling G,Flandrin P,Goncalvés P. On empirical mode decomposition and its algorithms[C]. IEEEEURASIP Workshop on Nonlinear Signal and Image Processing NSIP, 2003,3: 8-11.   
[8] 张冠英，曹旺林，李长伟，等．低压故障电弧检测 与周期辨识[J]．电气应用，2016，35(23)：81-85.   
[9] 万畅，齿轮箱轴承故障诊断的时频分析方法初步 探讨[D]．兰州：兰州理工大学，2007.   
[10] 董红生，心电波形检测与心率变异性分析方法研 究[D]．兰州：兰州理工大学，2012.

# （上接第25页）

[11] 中国电器工业协会，全国高压开关设备标准化技术委员会．GB11022—1999高压开关设备和控制设备标准的公用技术要求[S]．北京：中国标准出版社，1999.  
[12] 包博，谢天喜． $7 5 0 ~ \mathrm { k V }$ 高压电抗器笼式出线结构均压特性研究[J]．电网技术，2011，35(5)：232-236.Bao Bo,Xie Tianxi.Voltage sharing characteristicsof cage outgoing line structure for HV reactors in

750kV power grid[J]. Power System Technology, 2011,35(5):232-236. [13] 潘浩，殷庆铎，高文胜．固体绝缘中气隙尺寸 对局部放电过程的影响[J]．高电压技术，2008, 34(3): 458-461. Pan Hao,Yin Qingduo,Gao Wensheng.Influence of void dimensions on partial discharge in solid insulation[J].High Voltage Engineering,20o8,34(3): 458-461.