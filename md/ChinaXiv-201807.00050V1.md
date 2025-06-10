# 基于蜂群算法和新阈值函数的信号去噪算法

邓高峰，叶金才，王国富，张法全(桂林电子科技大学 信息与通信学院，广西 桂林 541004)

摘要：针对阈值和阈值函数的调节参数取值问题，提出一种基于人工蜂群优化算法的带参新阈值函数的信号去噪算法。首先，验证带参新阈值函数的连续性、高阶可微性、参数可调性；其次，根据最小均方误差（MSE）策略，利用人工蜂群优化算法优化各分解层的阈值和调整参数，得到最优去噪信号。最后，利用信噪比（SNR）、MSE指标验证信号的去噪效果。实验结果表明：人工蜂群优化算法选取的阈值参数和新小波阈值函数可以有效地对带噪信号去噪。

关键词：小波分析；人工蜂群优化算法；调整参数；阈值函数；信号去噪中图分类号：TN911.72 doi:10.3969/j.issn.1001-3695.2018.04.0254

Signal denoising method based on bee colony algorithm and new threshold function

Deng Gaofeng, Ye Jincai, Wang Guofu, Zhang Faquan (SchoolofInformation&Communication,Guilin UniversityofElectronicTechnology,Guilin Guangxi 541o04,China)

Abstract:Aimingatthe problemsof selectingthe adjustment parameters in thresholdandthreshold function，a signal denoising methodbasedonartificialbeoptimizationalgorithmand new thresholdfunctionisproposed.Firstly,thetheoretical analysisofthenewthresholdfunctioniscarriedouttoverifyitscontinuityhigh-orderdiferentiabilityandparameter adjustability.Secondlyaccording tothe minimummeansquareerror (MSE）strategy,theartificialbeecolonyoptimization algorithm isused tooptimize the thresholdsand adjustment parametersof each decomposition layer,and then theoptimal denoised signal isobtained.Finallythesimulationexperimentiscarriedout toverifythedenoising effectacordingtothe signal-to-noiseratio (SNR)and MSE.Theexperimental result showsthatthe threshold parameters selected byartificial bee optimization algorithm and the new wavelet threshold function can effectively denoise a noisy signal.

Key words: wavelet analysis; artificial bee colony algorithm; adjustment parameters;threshold function;signal denoising

# 0 引言

信号去噪是信号处理技术的关键，是最大程度上恢复原始信号的过程，它是信号处理中极其重要的一部分。传统的去噪方法通常是基于傅立叶变换。在过去的十年时间里，小波变换在时频信号分析中的地位随着信号的多分辨分析和局部信号特征分析的重要性的提高而不断提高。在信号处理中使用小波变换是空间域和频域部分变换的过程。从带噪的信号中精准地提取有效信号，该过程称为信号的去噪。阈值函数和阈值的选择决定小波阈值去噪效果。

阈值函数的选择是决定小波去噪效果的一大关键要素。1995年，美国学者Donoho提出的软阈值和硬阈值两种小波阈值去噪方法1]。这两种常规阈值去噪方法具有计算简单、有效抑制噪声、保留奇异信息等优点，是一种简单有效的方法。作为最基本的阈值函数，硬阈值和软阈值函数都有自己的缺陷。硬阈值函数的断点问题使其不具有连续性，而软阈值函数自身存在恒定偏差的问题。

为了克服硬阈值和软阈值函数的缺陷，2012年，sigmoid阈值函数被提出[2]。该阈值函数对小波系数具有较好的量化效果。但是，对小波系数量化的空间还有更进一步的提升。因此，本论文提出一种基于余弦函数的可导阈值函数，通过增加调整因子来提高阈值函数功能的灵活性。阈值的选取是决定小波去噪效果的另一大关键要素。在小波分解系数中，原始信号对应的小波系数远远大于噪声系数[3]。因此，选择合适的阈值可将小波系数中的噪声系数有效滤除。在过去的方法中，阈值的获取主要包括：基于邻域窗的自适应阈值法和经验选取阈值法，前者利用各分解层邻域小波系数的相关性估计合理的阈值[4]，后者通过反复的实验，最后根据经验来选取合适的阈值，该方法的工作量较大。为了克服人为循环试验选取最优参数值的缺点，并且能够获得较好的阈值，本文通过群智能优化技术获取合理的阈值和调节参数。例如粒子群优化算法、蚁群算法、人工鱼群算法等。结合人工蜂群算法具有良好的收敛性[5、适用于多变量优化问题[]、较好的全局搜索能力[7][8]，本论文采用人工蜂群算法优化阈值和调节参数，并将该算法与带参数阈值函数相结合，实现对带噪信号进行有效的滤波。

# 1 小波阈值函数设计

小波阈值包括硬阈值和软阈值两种，这两种方法的去噪原理都是以特定阈值为分界点。不同点是：在不同尺度空间，硬阈值函数将绝对值小于该阈值的分解系数置零，同时保留绝对值大于该阈值的分解系数[9]。硬阈值函数为

$$
\begin{array} { r } { \overline { { \mathbf { d } _ { j , k } } } = \left\{ \begin{array} { l l } { \mathbf { d } _ { j , k } } & { \left| \mathbf { d } _ { j , k } \right| \geq \lambda } \\ { 0 } & { \left| \mathbf { d } _ { j , k } \right| < \lambda } \end{array} \right. } \end{array}
$$

而软阈值函数将绝对值小于该阈值的分解系数置零，大于阈值的分解系数通过相应算法滤除携带在该系数的噪声数值。软阈值函数为

$$
\overline { { \mathbf { d } _ { j , k } } } = \left\{ \begin{array} { l l } { \operatorname { s g n } \big ( \mathbf { d } _ { j , k } \big ) \big ( | \mathbf { d } _ { j , k } | - \lambda \big ) } & { \left| \mathbf { d } _ { j , k } \right| \geq \lambda } \\ { 0 } & { \left| \mathbf { d } _ { j , k } \right| < \lambda } \end{array} \right.
$$

为了克服硬阈值和软阈值功能的缺陷，本文提出一种基于余弦函数的新小波阈值函数为

$$
 \overline { { \mathrm { d } _ { j , k } } } = \left\{ \begin{array} { l l } { \displaystyle { \mathrm { s } i g n \big ( } d _ { j , k } { \bigg ) } \left( | d _ { j , k } | - \frac { \big ( \lambda + 1 \big ) } { \lambda + \exp \big ( \alpha / 1 0 \ast \big ( | d _ { j , k } | - \lambda \big ) \big ) } \ast \lambda \right) } & { , } & { \left| d _ { j , k } \right| \geq \lambda } \\ { 0 \ , } & { \left| d _ { j , k } \right| < \lambda } \end{array} \right.
$$

其中： $\boldsymbol { d } _ { j , \boldsymbol { k } }$ 为小波系数， $\lambda$ 为阈值， $\alpha$ 为调整因子。通过自由调整 $\alpha$ 的取值，使该阈值函数更好地适应不同特性含噪信号的去噪。

很明显，新阈值函数由一个指数函数构成。根据基本函数的特性可知，新阈值函数同样具有连续性和高阶可微性。因此，新阈值函数可以克服不连续性导致的伪吉布斯效应，也可以有效地抑制振荡现象，使重构的去噪信号更加光滑。为了直接观测新阈值函数特性和调节因子 $\alpha$ 的作用，简单地取$- 1 0 \leq d _ { j , k } \leq 1 0$ ， $\lambda = 4$ 。对比不同阈值函数图形，和不同 $\alpha$ 值的新阈值函数图形。如图1所示。图1中，H-T表示硬阈值函数，S-T表示软阈值，N-T表示新阈值函数，2、10、20分别表示 $\alpha$ 的取值。

从图1可以清晰地看出，当 $\alpha$ 越来越小时，新阈函数具有软阈值函数值特征，随着 $\alpha$ 越来越大时，新阈值函数趋向于硬阈值函数，可知该新阈值函数是通过参数 $\alpha$ 自由调节的软-硬阈值函数。

![](images/4dc280901b2e76f822f7a74be81bb44ac816eeaaba853eebab5072dba72d75f8.jpg)  
图1比较不同的阈值函数和不同参数的新阈值函数

# 2 人工蜂群算法（ABC)

ABC 算法是一种启发式优化算法，基于迭代的思想，其灵感来自蜂群聚觅食行为[10]。标准人造蜜蜂分为三种，即雇佣蜂、观察蜂、侦查蜂。雇佣蜂通过搜索所有的食物源，并对含有丰富蜜量的区域进行搜索，根据蜜蜂之间的行为交流，食物源被观察蜂和侦查蜂开发并选出最优蜜源。ABC算法主要为以下四步：初始化蜂群、雇佣蜂阶段、观察蜂阶段、侦查蜂阶段[1]。

# 2.1初始化蜂群

利用随机函数生成 $S N$ 个 $n$ 维度的食物源（雇佣蜂），食物源产生公式如下：

$$
x _ { i , j } = x _ { \mathrm { m i n } , j } + r a n d ( 0 , 1 ) ^ { * } \left( x _ { \mathrm { m a x } , j } - x _ { \mathrm { m i n } , j } \right)
$$

其中 $i = 1 , 2 , 3 , \cdots , S N$ 代表食物源的个数。$j = 1 , 2 , 3 , \cdots , n$ 表示每个食物源的维度。 $x _ { \mathrm { m i n } , j }$ 和$x _ { m a x , j }$ 分别表示 $j$ 维度空间的最小值和最大值。

# 2.2雇佣蜂阶段

雇佣蜂在各蜜源邻域进行搜索，并且算出每个食物源的适应值与观察蜂共享。搜索公式如下：

$$
\nu _ { i , j } = x _ { i , j } + \varphi _ { i , j } \big ( x _ { i , j } - x _ { r , j } \big )
$$

其中： $\varphi _ { i , j }$ 为 $[ - 1 , 1 ]$ 范围的一个随机数。 $r \in \left\{ 1 , 2 \cdots , S N \right\}$ 表示在 $j$ 维度中 $i$ 的邻域产生新的食物源，为保持新食物源的有效性， $r \neq i$ ，通过贪婪选择，在 $x _ { i }$ 与 $\nu _ { i }$ 之间选择好的蜜源，蜜源的适应值计算式如下：

$$
f i t n e s s ( i ) = \left\{ \begin{array} { l l } { \displaystyle { 1 } } & { \displaystyle { F ( i ) \geq 0 } } \\ { \displaystyle { 1 + | F ( i ) } , } & { F ( i ) < 0 } \end{array} \right.
$$

其中 $F \big ( i \big )$ 为解的目标函数值。

# 2.3 观察蜂阶段

观察蜂根据与蜜量丰富度相关的概率评估值选取最优食物源。这种概率评估公式如下：

$$
P _ { i } = \frac { f i t ( x _ { i } ) } { \displaystyle \sum _ { n = 1 } ^ { S N } f i t ( x _ { n } ) }
$$

其中： $\mathrm { \it { f i t } } ( x _ { i } )$ 为第 $i$ 个食物源的适应值。蜜量丰富程度与它被选取的概率成正比。通过用轮盘选择方案选择概率估值大的蜜源。

# 2.4侦查蜂阶段

若在预定周期内，食物源 $x _ { i , j }$ 没有得到改善，则放弃该食物源。侦查蜂变为雇佣蜂，并且利用公式（3-2）在当前最大区域随机产生一个新的食物源。

# 3 去噪算法设计

# 3.1 目标函数

评估去噪后信号质量指标主要是重构信号与原始信号之间信噪比（ $\mathrm { S N R } _ { \mathrm { o u t p u t } }$ ）和均方误差（MSE）[12]，公式如下：

$$
M S E = \frac { 1 } { N } \sum _ { n = 1 } ^ { N } \biggl ( X \bigl [ \boldsymbol { n } \bigr ] - \hat { X } \bigl [ \boldsymbol { n } \bigr ] \biggr ) ^ { 2 }
$$

$$
\operatorname { S N R } _ { \mathrm { \ o u t p u t } } = 1 0 \log _ { 1 0 } { \frac { \displaystyle \sum _ { n = 1 } ^ { N } X \left[ n \right] ^ { 2 } } { \displaystyle \sum _ { n = 1 } ^ { N } \left( \stackrel { \wedge } { X } \left[ n \right] - X \left[ n \right] \right) ^ { 2 } } }
$$

其中： $X [ n ]$ 为原始信号， $\hat { X } \big [ n \big ]$ 为去噪后的信号。将重构信号与原始信号之间的MSE公式（4-1）作为公式（3-3）的目标函数，构造出本论文算法的适应度函数。

# 3.2去噪参数设置和算法流程

去噪算法分三步：

a)采用固定小波变换（SWT）技术[13]对带噪信号进行小波分解，得到特征系数和细节系数；

b)将各分解层阈值和调节参数作为解的坐标分量，使用ABC算法优化阈值和参数，输出最优阈值和调节参数；

c)利用各分解层的最优阈值和调节参数进行信号去噪，输出去噪后的信号。

去噪算法流程如图2所示。

![](images/6df19cdfd76d90ca5f82bf72cdfa224e6e9f8d49c4c1723d48e6e35e5203eda2.jpg)  
图2去噪算法流程图

# 4 仿真实验

# 4.1去噪参数设置

小波参数设置：通过多次比较不同滤波器和不同分解层数的实验效果，本实验设置的分解层为4，选用Haar滤波器。

ABC参数设置：确定解的维度等于分解层数与调节参数个数的和，即为 ${ \mathrm { D } } { = } 5$ ，迭代次数为50，各分解层的阈值区间为[0,100]，根据图1设置调节参数的区间为[0,50]，食物源的个数SN为10，最优解未更新的次数"limit"等于 $0 . 5 ^ { * } S N ^ { * } \mathrm { D }$ ，即为25。

# 4.2 实验结果分析

为验证提出算法的有效性和普遍性，本文选用Bumps 和Blocks基准信号作为测试信号，分别给这两种基准信号添加不同强度的高斯白噪声,产生SNR为10dB、15dB的带噪信号。将MSE、SNR作为去噪效果指标。分别比较硬(Hard）、软(Soft）、Sigmoid阈值函数与新阈值函数（New）的去噪效果。去噪数据如表1所示。图3为ABC算法收敛曲线图。图4为SNR分别为10dB、15dB 时对应的Bumps 信号去噪图。图5为SNR分别为10dB、15dB时对应的Blocks信号去噪图。

表1数据显示，Sigmiod和新阈值函数的去噪指标均优于软、硬阈值函数，但是，新阈值函数可得到更大的信噪比和更小的均方误差，因此，对于本论文的信号去噪效果而言，新阈值函数的更好。图3的纵坐标为MSE，横坐标为迭代次数。从四个子图可以明显地看出，随着迭代次数增加，算法不断优化阈值和调节参数，从而得到更小的MSE，特别在算法的中前期，收敛速率更快。图4和图5清晰地显示了不同阈值函数去噪后的信号，以图4为例，软阈值去噪后的信号肉眼效果最差。硬阈值函数去噪后的信号依然存在大量的噪声，相比于Sigmoid阈值函数而言，新阈值函数的整体去噪效果更加的优秀。

表1基于人工蜂群算法的不同阈值函数的去噪指标  

<html><body><table><tr><td rowspan="2">带噪信号信噪比(dB)</td><td rowspan="2">原始信号</td><td colspan="4">最小均方误差 (MSE)</td><td colspan="4">信噪比 SNR(dB)</td></tr><tr><td>Soft</td><td>Hard</td><td>Sigmoid</td><td>New</td><td>Soft</td><td>Hard</td><td>Sigmoid</td><td>New</td></tr><tr><td>10</td><td>Bumps</td><td>0.2744</td><td>0.2413</td><td>0.1573</td><td>0.1306</td><td>16.7401</td><td>17.3299</td><td>19.1906</td><td>20.0016</td></tr><tr><td></td><td>Blocks</td><td>0.6248</td><td>0.5320</td><td>0.4305</td><td>0.3388</td><td>17.5862</td><td>18.2167</td><td>19.1364</td><td>20.1766</td></tr><tr><td>15</td><td>Bumps</td><td>0.0894</td><td>0.0856</td><td>0.0565</td><td>0.0516</td><td>20.7679</td><td>21.7990</td><td>23.4495</td><td>24.0065</td></tr><tr><td></td><td>Blocks</td><td>0.3382</td><td>0.2499</td><td>0.1164</td><td>0.1070</td><td>20.1838</td><td>21.5371</td><td>24.4987</td><td>25.1829</td></tr></table></body></html>

![](images/6c51cd4aa47cdc00fe8fb01f10f51574d0e79a5e6259b31a62cda517b177329a.jpg)  
图3人工蜂群算法优化收敛曲线

![](images/2dfe2d6af8ece76e440b87b9df3d1c190ba5331984d260de00589bc58a4f8d3a.jpg)  
图4Bumps信号（ $\mathrm { a ) S N R { = } 1 0 d B }$ (b)SNR $= 1$ 15dB

![](images/14e6c6d066c63fc26acb4ad4fbe5993809bf3332730eed7c578007c4ef53d1c2.jpg)  
图5Blucks信号（ $\mathrm { a ) S N R { = } 1 0 d B }$ （204号 $( \mathbf { b } ) \mathbf { S } \mathbf { N } \mathbf { R } { = } 1 5 \mathbf { d } \mathbf { B }$

# 5 结束语

本论文提出了基于ABC 算法的带参新阈值函数信号去噪算法。通过理论证明和仿真实验分析，可得出如下结论：

a)本文提出一种新的带参阈值函数用于带噪信号的小波阈值去噪。该阈值函数在全域具有连续性、高阶可微性、参数可调性。通过数据分析，可知该阈值函数可以有效量化小波系数，从而达到较好的去噪效果。

b）本文将小波阈值函数与ABC算法结合，提出一种新颖的去噪方法。以阈值和调节参数作为ABC算法中解的坐标，利用最小化原始信号与重构信号之间的MSE，可以快速、有效地得到最优阈值和调节参数。这种方法具有自适应特性，可以克服传统阈值去噪方法的不灵活缺陷。

# 参考文献：

[1]Donoho D L.De-noising by soft-thresholding [M].[S.1.] $\because$ IEEE Press, 1995.   
[2]Yi Tinghua,Li Hongnan,Zhao Xiaoyan.Noise smoothing for structural vibration test signals using an improved wavelet thresholding technique. [J].Sens0rs,2012,12(8):11205.   
[3]吴光文，王昌明，包建东，等．基于自适应阈值函数的小波阈值去噪方 法[J]．电子与信息学报,2014,36(6):1340-1347.(Wu Guangwen,Wang Changming,Bao Jiandong,et al.A wavelet threshold de-noising algorithm based on adaptive threshold function [J].Journal of Electronics& Information Technology,2014,36 (6): 1340-1347.)

[4]高国荣，刘艳萍，潘琼．基于小波域可导阈值函数与自适应阈值的脉冲 星信号消噪 [J].物理学报，2012,61(13):549-553.(Gao Guorong,Liu Yanping,Pan Qiong.Adifferentiable thresholding function and an adaptive threshold selection technique for pulsar signal denoising [J].Acta Physica Sinica,2012,61 (13): 165-172.)

[5]宁爱平，张雪英．人工蜂群算法的收敛性分析[J].控制与决策，2013 (10):1554-1558.(Ning Aiping,Zhang Xueying. Convergence analysis of artificial bee colony algorithm [J].Control & Decision,2013,28(10): 1554-1558.)   
[6]Karaboga D,Gorkemli B,Ozturk C,et al.A comprehensive survey: artificial bee colony (ABC）algorithm and applications [J].Artificial Intelligence Review,2014,42(1): 21-57.   
[7]何尧，刘建华，杨荣华．人工蜂群算法研究综述[J].计算机应用研究, 2018,35 (5):1281-1286.(He Yao,Liu Jianhua,Yang Ronghua. Research onArtificial Bee Colony Algorithm [J].Application Research of Computers,2018,35 (05):1281-1286.)   
[8]赵辉，李牧东，翁兴伟，等．具有自适应全局最优引导快速搜索策略的 人工蜂群算法 [J].控制与决策，2014(11):2041-2047.(Zhao Hui,Li Mudong,Weng Xingwei.Improved artificial bee colony algorithm with self-adaptive global best-guided quick searching strategy [J].Control & Decision,2014 (11): 2041-2047.)   
[9]Lu Jingyi,Lin Hong,Ye Dong,et al.A New Wavelet Threshold Function and Denoising Application [J].Mathematical Problems in Engineering, 2016,(2016-5-9),2016,2016 (3): 1-8.

[10]Karaboga D,Basturk B.A powerful and efficient algorithm for numerical function optimization:artificial bee colony(ABC) algorithm [M].Kluwer Academic Publishers,2007.

[11]沈夏炯，王龙，韩道军．人工蜂群优化的BP神经网络在入侵检测中的 应用[J].计算机工程，2016,42(2):190-194.(Sheng Xiajiong，Wang Long，Han Daojun，Application of BP neural network optimized by artificial bee colony in intrusion detection [J]. Computer Engineering,2016, 42 (2): 190-194.)

[12]杨岳飞，刘辉，谭检平．带噪语音信号小波去噪算法研究[J].计算机 工程与应用，2015，51(14):211-213.(Yang Yuefeng,Liu Hui，Tan Jianping,.Research on wavelet-based speech signal with noise denoising algorithms.[J].Computer Engineering and Applications,2O15,51(14): 211-213.)

[13] Zhong Shuncong，Oyadiji，S.Olutunde.Crack detection in simply supported beams using stationary wavelet transform of modal data [J]. Structural Control & Health Monitoring,2015,18(2):169-190.