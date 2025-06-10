DOI:10.16592/ j.cnki.1004-7859.2016.02.001

# 毫米波FMCWSAR系统设计与成像研究

蔡永俊1² 张祥坤 姜景山

(1．中国科学院微波遥感技术重点实验室国家空间科学中心，北京100190)

(2．中国科学院大学电子电气与通信工程学院，北京100049)

摘要:首先,详细分析了调频连续波合成孔径雷达(FMCW SAR)机载试验系统 深入阐述了系统各部分的设计方法和主要原理基于此系统进行首次校飞试验以验证系统性能;其次 深入分析了FMCW SAR回波信号特点和图像重建方法揭示了其脉冲发射期间雷达的连续运动对回波信号的影响，定量地指出了其对图像重建的影响，并采用改进的距离多普勒算法对其补偿从而对场景进行聚焦;最后通过实际航空校飞试验数据验证了系统分析设计和图像重建算法的有效性。关键词:线性调频连续波;合成孔径雷达;系统设计;成像研究

中图分类号：TN958 文献标志码：A 文章编号:1004-7859(2016)02-0001-05

# A Study on System Design and Imaging of Millimeter Wave FMCW SAR

CAI Yongjun1 ² ZHANG Xiangkun1 JIANG Jingshan1 (1.Key Laboratory of Microwave Remote Sensing ,Chinese Academy of Sciences， National Space Science Center，Beijing 1O019O ,China) (2.School of Electronic ,Electrical and Communication Engineering , University of Chinese Academy of Sciences，Beijing 1OoO49,China)

Abstract:Firstly,anaiboreFMCWSARtestsystemisdesignedandanalyzedandthedesigmethodsandmainprinciplesofll partsof thesystemareexplained in-depth.Basedonthesystem,aflighttestovalidate theperformancewasconducted.Thenthe characteristicsofechosignalandimagingmethodofFMCWSARareanalyzed,andtheinfluenceonechosignalowingtoheconstantmovementduringthepulsesweeptimewasrevealed,andtheinfluenceonimagingwasquantitativelypointedoutndhere visedrangeDopplerimagingalgorithmisusedtocompensatedthisefect.Atlast,theperformanceandvalidityof thesystemnd theimage reconstruction algorithm designed in this paper are verified by the real flight experiment data.

Key words: frequency modulated continuous wave; synthetic aperture radar; system design; imaging research

# 0 引言

传统脉冲体制合成孔径雷达(SAR)由于设备复杂、成本昂贵、体积大、质量大和抗干扰能力不足等缺点使得其无法装载于轻小型飞机、无人机或精确制导武器等平台上完成一些紧急任务，也不适用于低成本要求的民用项目,这大大限制了SAR技术的大规模应用。然而随着近年来无人机技术的快速发展及在军民领域不断深入的应用其对SAR的小型化提出了越来越迫切的需求。

调频连续波合成孔径雷达(FMCWSAR)将合成孔径技术与调频连续波雷达相结合，这种新体制的合成孔径雷达不仅具有调频连续波雷达体积小、质量轻、造价低和抗干扰能力强等特点，同时又具有传统SAR的高分辨率的特点，非常适合精确制导武器或无人机等小型平台，成为SAR小型化发展的重要方向，在环境监测、自标识别、军事侦察、农作物评估、地形测绘等众多领域具有广泛的应用前景[1-4]。

由于FMCWSAR发射大时宽大带宽线性调频信号信号持续时长一般为 $1 \ \mathrm { m s } \sim 1 0 \ \mathrm { m s }$ ,而在脉冲SAR中该时长一般在微秒量级所以FMCWSAR在系统结构和信号处理方法等方面与脉冲SAR具有本质区别。比如由于大时宽带宽信号导致接收的数据量非常大，就不能采用传统脉冲SAR的接收方法，从而也会引起数据处理方法的不同；由于信号时宽较长必须考虑在脉冲发射期间雷达的连续运动引起的自标与雷达瞬时斜距的改变而在脉冲体制SAR中，该斜距的变化可以忽略，所以对于FMCWSAR，必须分析雷达的脉内运动对接收信号及图像创建算法的影响，即必须判别“停走停”假设是否成立。

本文首先给出了机载FMCWSAR系统分析设计思路和主要组成单元的设计方法并分析其工作原理;

然后分析FMCWSAR回波接收方式及其对系统构成和图像重构的影响;其次，对FMCWSAR信号特征和图像重建方法进行研究，重点剖析由于脉内雷达的连续运动对接收信号的影响及其解决方法；最后通过实际飞行试验和数据来验证本文系统分析设计和成像方法的有效性。

# 1 FMCW SAR系统设计

由于毫米波段SAR系统体积小、质量轻和抗干扰能力强等优势突出非常适用于无人机等小型平台应用而且对于短程应用毫米波在大气中的衰减就显得不特别重要[5]因此本文系统采用Ka 波段。

为了减小天线的体积和质量实现小型化，天线采用E面矩形透镜喇叭天线；同时，由于采用FMCW体制必须使用收发分置的双天线方法来避免连续波体制带来的收发信号泄露问题，隔离度一般能达到60 dB。

# 1.1 射频单元设计

图1为系统射频单元组成部分，包含发射链路和接收链路。发射链路中信号输入为直接数字频率合成(DDS)产生的 $7 5 0 \ \mathrm { \ M H z } \pm 1 5 0$ MHz的线性调频扫描连续波信号幅度约为 $0 ~ \mathrm { d B m } ;$ 来自频率综合器的本振信号为 $9 . 2 ~ \mathrm { G H z }$ 的单频信号。在图1中,混频器1首先进行四倍谐波混频产生 $3 6 . 8 ~ \mathrm { G H z }$ 的单频信号；然后与DDS产生的信号进行混频得到 $3 6 . 0 5 ~ \mathrm { G H z } \pm 1 5 0 \$ MHz的线性调频信号，带宽为 $3 0 0 ~ \mathrm { M H z }$ 。此信号经过功放产生功率为 $2 5 ~ \mathrm { d B m }$ 的线性调频信号，然后通过定向耦合器分为两路：一部分输出至天线到达天线的平均功率约为 $2 3 \ \mathrm { d B m } ;$ 另一部分输出至接收机，到达接收机的平均功率约为 $1 0 ~ \mathrm { d B m }$ 。在接收链路中信号输入为天线接收的 $3 6 . 0 5 ~ \mathrm { G H z } \pm 1 5 0 ~ \mathrm { M H z }$ 的线性调频连续波信号，功率约为 $- 9 0 ~ \mathrm { d B m } \sim - 3 0 ~ \mathrm { d B m }$ ,以及来自发射链路的本振信号功率为 $1 0 ~ \mathrm { d B m }$ 。输出至数据采集部分的功率小于10dBm，频率为 $4 ~ \mathrm { k H z } \sim 1 0$ MHz，以及来自系统控制的5位自动增益控制(AGC)的控制信号。接收链路采用对数放大的形式：输入信号功率在 $\mathrm { - 9 0 ~ d B m \sim - 6 0 ~ d B m }$ 区间段，信号增益为60 dB;输入功率在 $- 6 0 ~ \mathrm { d B m } \sim - 3 0 ~ \mathrm { d B m }$ 区间段信号增益随着信号幅度的增加而减小最大功率 $- 3 0 ~ \mathrm { d B m }$ 时的增益为 $4 0 ~ \mathrm { d B }$ 。

36.05 GHz 上变频器36.05GHz±150 MHz 25 dBm 混频器1发射天线 23 dBm 务 750MEz±150MHS耦合器 功放 AMP1BPF2B.300MHz B300MHz B.300MHz发射链路频率综合器输出信号9.2 GHz36.05 GHz±150 MHz接收天线 R R 数据采集-90 dBm\~30 dBm L5 dB 13605 G混频器2 FPF5 对数放大器 BPF6 射随放大器 4 kHz-10MHzNF:3.5 dB B:150 MHz f 10 MHz f: 10 MHz 接收链路5位AGC控制32dB衰减

# 1.2 频率综合器单元设计

频率综合器负责整个系统各种频率源的产生，并为发射模块提供发射激励信号，为接收模块提供参考本振信号发射模块将发射激励信号进行放大接收模块进行去调频接收。其主要完成以下功能：

1)输出给发射链路的 $9 . 2 ~ \mathrm { G H z }$ 连续波信号，功率约为 $1 3 \ \mathrm { d B m }$ ，发射链路对该信号进行4倍倍频再由DDS输出信号混频;2)输出给DDS的本振信号,频率为1GHz幅度为3dBmDDS接收该信号再生成系统所需扫频信号;3)输出给数据采集系统的是功率为 $1 3 \ \mathrm { d B m }$ 的$1 0 0 ~ \mathrm { M H z }$ 中频信号用于对接收信号进行采样；

4)输出给仪器参考用的功率为 $1 0 ~ \mathrm { d B m }$ 的 $1 0 ~ \mathrm { M H z }$ 的参考信号。

其结构框图如图2所示。

![](images/17de773a6b42e50035ef52e007d2d8b7b49d7e330bd003c02f9f8739e11e0f2a.jpg)  
图1射频部分组成框图  
图2频率综合器构成框图

# 1.3 频率合成单元

该单元采用基于DDS的方案生成系统所需扫频信号具有体积小、控制灵活和功耗小等优势，完成在系统外触发或内触发控制下产生扫频信号的功能。在本系统中DDS采用1GHz时钟的芯片，产生带宽为$3 0 0 ~ \mathrm { M H z }$ 的扫频信号扫描起始点频率 $6 0 0 ~ \mathrm { { M H z } }$ 终止点频率 $9 0 0 ~ \mathrm { M H z }$ 。其结构框图如图3所示。

![](images/0973dd84fd923b59c425a2b36b3dc7f2442383a39f5ec3173a398f5aa416b706.jpg)  
图3频率合成单元结构框图

# 1.4数据采集存储单元设计

数据采集存储单元实现对系统中雷达连续回波信号数据采集及存储、全球定位导航(GPS)与惯导数据的接收、DDS的触发控制、以及接收机的AGC调整。由于采用去调频接收方式，接收信号与发射信号进行混频之后再进入采样单元，使得采样单元的输入信号是带宽很小的中频信号，这大大降低了系统对采样单元的要求使得采样单元能够具有体积小、质量轻、成本低和便于集成等优点，非常适合于小型SAR的需求。其结构框图如图4所示。

连接计算机ADC F数据 接UB256GBAGC控制字 高速缓存FPGAGPS 秒脉冲  
同步脉冲GPS及  
触发脉冲 惯导数据  
外部时钟 时钟 电源管理 电源数据采集及存储单元

![](images/4a788448f6c543fbc974ffa0d845a9900094fe74500f375b6dc419122bc8369f.jpg)  
图4数据采集存储单元结构框图  
图5FMCWSAR射频组件与天线

# 2 FMCWSAR成像处理

# 2.1 去调频

FMCWSAR一般采用去调频（Dechirp）方式接收回波信号Dechirp原理是将接收信号与发射信号或发射信号的延迟信号进行共轭相乘[6]。同时，FMCWSAR系统回波延迟一般很短且远小于发射信号时宽，所以常采用发射信号作为参考信号。经过Dechirp后接收信号的相位变为

$$
\varphi = 2 \pi { \left( { k { \tau } t + { f _ { 0 } } { \tau } - \frac { k } { 2 } { \tau } ^ { 2 } } \right) }
$$

将接收信号相位对距离时间 $\mathbf { \chi } _ { t }$ 求导，可得到距离频率为

$$
f _ { \mathrm { r } } = { \frac { 1 } { 2 \pi } } { \frac { \mathrm { d } \varphi } { \mathrm { d } t } } = k \tau
$$

由式(2)可知，Dechirp将所有目标的回波信号变为一个单频的信号频率瞬时值与信号回波延时有关。其过程如图6所示。由此可见Dechirp使信号带宽大大降低从而降低了对系统A/D采样模块的要求，从而能减轻系统质量和节约系统成本。

![](images/74c66414d55c5196a2bca1f40bdf1f4600dbb6de8663d2689549bc20d7e49a0f.jpg)  
图6发射/接收信号时频关系与去调频原理

# 2.2FMCWSAR回波信号模型及图像重建

图7为FMCWSAR成像几何关系图雷达工作在正侧视情形高度为 $h$ ,速度为 $\mathbf { \sigma } _ { v }$ ,天线波束角为 $\beta$ 雷达距目标的最短斜距为 $R _ { 0 } = \sqrt { h ^ { 2 } + y ^ { 2 } }$ 。

![](images/2f0f768730170290a53c0eb0a5a4bc8ee9610f3cd5333ca467bc494d55793a75.jpg)  
图5给出了本文FMCWSAR射频组件与天线实物图。  
图7 FMCWSAR成像几何关系图

由于FMCWSAR发射信号时长较大，对于一个脉冲周期内的信号回波延迟是变化的，与某脉冲发射期

间内雷达至某点目标的瞬时斜距有关[7-10],该瞬时斜距可以表示成如下

$$
R ( \mathit { \omega } _ { t _ { \mathrm { a } } } \mathit { \omega } _ { t } ) = \sqrt { R _ { 0 } ^ { 2 } + v ^ { 2 } ( \mathit { \omega } _ { t _ { \mathrm { a } } } + t ) { \mathit { \omega } } ^ { 2 } }
$$

对式(3)在距离时间 $\scriptstyle t = 0$ 处进行泰勒级数展开，由于是在极短的脉冲持续时间 $T _ { \mathrm { { p } } }$ 内所以可忽略其二次及更高次项的影响，展开后瞬时斜距可表示为

$$
\begin{array} { r c l } { { R ( \ { \scriptstyle t _ { \mathrm {  a } } } \ { \scriptstyle \mu } ) } } & { { = } } & { { \sqrt { R _ { 0 } ^ { 2 } \ + \ v ^ { 2 } { t _ { \mathrm { a } } ^ { 2 } } } + { \frac { \displaystyle v ^ { 2 } { t _ { \mathrm { a } } } } { \displaystyle { \sqrt { R _ { 0 } ^ { 2 } \ + \ v ^ { 2 } { t _ { \mathrm { a } } ^ { 2 } } } } } } = } } \\ { { } } & { { } } & { { R ( \ { \scriptstyle t _ { \mathrm { a } } } ) \ + { \frac { \displaystyle v ^ { 2 } { t _ { \mathrm { a } } } } { \displaystyle { \sqrt { R _ { 0 } ^ { 2 } \ + \ v ^ { 2 } { t _ { \mathrm { a } } ^ { 2 } } } } } } { } } } \end{array}
$$

式中： $R \big ( \ t _ { \mathrm { a } } \big )$ 为方位时间 $t _ { \mathrm { a } }$ 时刻雷达与目标的斜距。所以在脉冲发射期间雷达与自标的瞬时斜距不仅与方位时间 $t _ { \mathrm { a } }$ 有关还与距离时间 $\mathbf { \chi } _ { t }$ 有关，且可近似地认为与距离时间只成线性关系，即瞬时斜距的变化量近似不变。将式(4)对距离时间 $\mathbf { \chi } _ { t }$ 求导，可得到由雷达连续运动引起的附加距离频率偏移

$$
\Delta f = - \frac { 2 } { \lambda } \frac { \mathrm { d } R ( \mathrm {  ~ \ell ~ } t _ { \mathrm { a } } \mathrm {  ~ \ell ~ } t ) } { \mathrm { d } t } = - \frac { 2 } { \lambda } \frac { v ^ { 2 } t _ { \mathrm { m } } } { \sqrt { R _ { 0 } ^ { 2 } + v ^ { 2 } t _ { \mathrm { a } } ^ { 2 } } } = f _ { \mathrm { d } }
$$

式中： $\lambda$ 为雷达中心频率对应的波长; $f _ { \mathrm { d } }$ 为多普勒频率。由式(5)可知附加频率偏移等于方位多普勒频率因此称之为多普勒偏移。所以式(4)可以表示为

$$
R ( \ t _ { \mathrm { a } } \ \mu ) = R ( \ t _ { \mathrm { a } } ) - \frac { \lambda f _ { \mathrm { d } } } { 2 } t
$$

将式(6)代入式(1)可得到Dechirp之后的回波信号相位表达式因此接收信号的完整表达式(以复数形式表示)可以表示如下

$$
s ( \mathrm { \Delta } t _ { \mathrm { a } } \mathrm { \Delta } \mu ) \ = A \mathrm { e } ^ { \mathrm { j } 2 \pi ( \mathrm { \Delta } k \tau _ { \mathrm { a } } - f _ { \mathrm { d } } ) \mathrm { \Delta } t } \mathrm { e } ^ { \mathrm { j } 2 \pi f _ { 0 } \tau _ { \mathrm { a } } } \mathrm { e } ^ { - \mathrm { j } \pi k \tau _ { \mathrm { a } } ^ { 2 } }
$$

式中: $A$ 为回波信号的幅度;第一个相位项为Dechirp之后距离向的一次相位；第二个相位项是方位聚焦所需的相位，包含了在合成孔径时间内方位向信号的相干性;第三个相位项为剩余视频相位（RVP），是经Dechirp后产生的，该项不用单独去除，可以合并入方位匹配滤波器中在方位压缩中一并去除，从而可以简化成像步骤。

为了进行距离徙动校正（RCMC)以及方位压缩，需要将该信号变换到距离多普勒域。与脉冲SAR不同的是对于FMCWSAR，直接对去斜接收信号进行方位向傅里叶变换就可以很方便地得到距离多普勒域信号形式。对于小斜视角情形，去斜接收信号在距离多普勒域具有以下形式

$$
\begin{array} { r l } { s ( f _ { \mathrm { d } } \ k ) } & { = \ A \ e ^ { \mathrm { j } \pi _ { K _ { \mathrm { a } } } ^ { f _ { \mathrm { d } } ^ { 2 } } } \mathrm { e } ^ { \mathrm { j } \frac { 4 \pi k } { c } R ( f _ { \mathrm { d } } ) \ t } \mathrm { e } ^ { - \mathrm { j } 2 \pi f _ { \mathrm { d } } t } \mathrm { e } ^ { - \mathrm { j } \frac { 4 \pi k } { c ^ { 2 } } R ^ { 2 } ( f _ { \mathrm { d } } ) } } \\ { - \ 4 \ - } & { } \end{array}
$$

式中: $A ^ { \prime } { = } A _ { 0 } \mathrm { e } ^ { \mathrm { i } \overline { { \frac { 4 \pi R _ { 0 } } { \lambda } } } }$ 为信号幅度和常数相位;第一个相位项包含了方位向调频信号；第二个相位项为距离调制信号，该相位为距离向信号仅存的一次相位;第三个相位项为多普勒偏移项这是相比较于脉冲SAR多出的相位是由雷达相对于自标的连续运动产生所以对于FMCWSAR，“停走停”假设不再成立，在成像时需要校正其影响;最后一项为RVP; $K _ { \mathrm { a } }$ 为方位调频率; $R$ $( f _ { \mathrm { d } } )$ 为距离多普勒域的距离形式。其中

$$
\left\{ \begin{array} { l l } { \displaystyle K _ { \mathrm { a } } = \frac { \lambda R _ { \mathrm { 0 } } } { 2 v ^ { 2 } } } \\ { \displaystyle R ( f _ { \mathrm { a } } ) = R _ { \mathrm { 0 } } + \frac { \lambda ^ { 2 } R _ { \mathrm { 0 } } } { 8 v ^ { 2 } } f _ { \mathrm { d } } ^ { 2 } } \end{array} \right.
$$

式中： $\mathbf { \sigma } _ { v }$ 为雷达运行速度。由于经过去斜接收后，距离向信号变成一个单频信号。由于在时域存在一次相位变换到频域就为sinc型的函数，直接对接收信号进行距离傅里叶变换即可完成距离压缩，距离频域的信号位置由距离调制系数决定，将式(8)变换到距离频域即可完成距离压缩。距离频域的信号表达式为

$$
s \{ f _ { \mathrm { d } } ~ f \} ~ = ~ A _ { 1 } \mathrm { s i n c } \Big \{ T _ { \mathrm { p } } \Big [ f - \frac { 2 k } { c } R ( f _ { \mathrm { a } } ) ~ + f _ { \mathrm { d } } \Big ] \Big \} .
$$

$$
\mathrm { e } ^ { \mathrm { j } \pi _ { K _ { \mathrm { a } } } ^ { f _ { \mathrm { d } } ^ { 2 } } } \mathrm { e } ^ { - \mathrm { j } \frac { 4 \pi k } { c ^ { 2 } } R ^ { 2 } ( f _ { \mathrm { d } } ) }
$$

式（10)为FMCWSAR目标回波距离压缩完后的信号表达式。其中 $, T _ { \mathrm { { p } } }$ 为脉冲持续长度，由式(10)可知FMCWSAR在距离多普勒域的距离徙动表达式为

$$
R C M = { \frac { 2 k } { c } } R ( f _ { \mathrm { a } } ) - f _ { \mathrm { d } }
$$

FMCWSAR信号时宽较大，使不同方位时刻接收的点目标回波在距离向产生了一个附加距离迁移，通过式(11)可以将其校正。

最后，用于方位压缩的匹配滤波器可以由式(10)得到，滤波器的频域形式为

$$
\begin{array} { r l } { H ( f _ { \mathrm { d } } ) } & { = \mathrm { e } ^ { \mathrm { j } \pi _ { K _ { \mathrm { a } } } ^ { f _ { \mathrm { d } } ^ { 2 } } } \mathrm { e } ^ { - \mathrm { j } \frac { 4 \pi k } { c ^ { 2 } } R ^ { 2 } ( f _ { \mathrm { d } } ) } } \end{array}
$$

所以经过上述步骤FMCWSAR图像重建完成，最终的信号形式为

$$
\begin{array} { r l } { s ( \mathrm { \Delta } t _ { \mathrm { { d } } } \ f ) } & { = A _ { 2 } { \operatorname { s i n c } } ( \mathrm { \Delta } \pi B _ { \mathrm { { a } } } t _ { \mathrm { { a } } } ) \operatorname { s i n c } \Big [ T _ { \mathrm { { p } } } \Big ( f - \frac { 2 k } { c } R _ { 0 } \Big ) \Big ] } \end{array}
$$

式中： $A _ { 2 }$ 为幅度及常数相位; $B _ { \mathrm { a } }$ 为方位多普勒带宽。

# 3 航空校飞试验

为了验证本文FMCWSAR系统设计与成像方法的有效性在某轻小型飞行平台上进行了校飞试验。试验中载机平台飞行高度约为 $3 0 0 \mathrm { ~ m ~ }$ 速度约为 $5 5 ~ \mathrm { m / s }$ 进行了条带式成像试验。采用本文改进的距离多普勒成像方法进行成像图8显示了某区域的成像结果。图中矩形区域标注的为两条道路的岔路口主要散射为面散射表现在成像结果中为散射较弱的目标，椭圆形区域标注的为房屋建筑物主要散射来自地面及墙壁构成的二次散射所以表现在成像结果中为散射较强的目标。

![](images/badadc7208cd4676062735bbd5be21eb7ed0021de82897b1b559aae7ee41c586.jpg)  
图8某区域成像结果与光学图像对比

# 4结束语

本文详细地分析设计了FMCWSAR试验系统及其成像方法通过对线性调频连续波和去调频体制信号处理的过程和特性分析，采用收发分置的双天线方式以提高收发隔离度，采用毫米波段频段和透镜喇叭天线以进一步减小系统的体积和重量，采用Dechirp方式接收信号以降低对系统A/D采样单元的要求，分析FMCW体制对接收信号和成像的影响，揭示其与“停走停”假设下的成像方法的区别，对理解FMCWSAR系统工作原理和模式具有重要意义，并通过实际飞行试验结果验证了本文分析设计的有效性。校飞结果表明本文设计的FMCWSAR试验系统性能良好，达到此次设计和试验要求，为之后进一步的完善和提高系统性能奠定了良好的基础。

# 参考文献

[1]DUERSCH MI.BYU micro-SAR:A very small low-power LFM-CWsyntheticapertureradar[D].Provo，Utah: Brigham Young University,2004.   
[2]刘闯,洪香茹 张涛．小型 SAR系统设计[J]．火控 雷达技术，2012，41(1)：1-5. LIU Chuang,HONG Xiangru,ZHANG Tao.Design of miniSAR system[J].Fire Control Radar Technology,2012,41 $( 1 ) \colon 1 - 5$   
[3]高许岗,雍延梅．无人机载微型 SAR系统设计与实现 [J]．雷达科学与技术， $2 0 1 4 , 1 2 ( 1 ) : 3 5 - 3 8 .$ GAO Xugang，YONG Yanmei．Design and realization of UAV high resolution miniature SAR[J].Radar Science and Technology,2014,12(1):35-38.   
[4]张军,毛二可.线性调频连续波 SAR 成像处理研究 [J].现代雷达,2005,27(4)：42-45. ZHANG Jun,MAO Erke.A study on LFMCW signal processing[J]． Modern Radar,2005,27(4):42-45.   
[5] 马兵强 张大炜,王岩飞．斜视FMCWSAR的四阶多项 式插值波数域算法[J]．现代雷达 ,2014，36(2)：47- 51. MA Bingqiang,ZHANG Dawei ,Wang Yanfei. A wavenumber domain algorithm using four-order polynomial interpolation for squint FMCW-SAR[J]．Modern Radar,2O14,36 $( 2 ) : 4 7 - 5 1$ ：   
[6] GRIFFITHS H D. Synthetic aperture processing for full-derampradar altimeters[J]．Electronics Letters，1988，24 (7): 371 -373.   
[7] WITJJM DE,HOOGEBOOMP.Performance analysis of a high resolution airborne FM-CW synthetic aperture radar [C]//2O03 International Radar Symposium.Dresden,Germany:German Institute of Navigation,20O3:269 -273.   
[8] META A.Signal processing of FMCW synthetic aperture radar data[D].Delft,Holland:Holland Delft University of Technology,2006.   
[9] LIUY,DENGYK,WANGR,etal.Bistatic FMCW SAR signal model and imaging approach[J].IEEE Transactions on Aerospace and Electronic Systems,2014,49(3):2017 -2028.   
[10]NAVNEET S,ROY A,BHATTACHARYA C. High-resolution SAR image generation by subaperture processing of FMCW radar signal [J]. IEEE Geoscience and Remote Sensing Letters ,2014,11(11) :1866 -1870.

蔡永俊男1989 年生，博士研究生。研究方向为合成孔径雷达信号处理与系统研究、全极化合成孔径雷达信息处理。

张祥坤男1972年生，研究员。研究方向为合成孔径雷达信号处理与系统研究、微波遥感理论与技术。

姜景山男1936年生 院士博士生导师。研究方向为微波遥感理论与技术。

# 声明

为适应我国信息化建设，扩大本刊以及作者的知识信息交流渠道，本刊已被目次页上的数据库全文收录，其作者文章著作权使用费与本刊稿酬一次性付给。如作者不同意文章被收录，请在来稿时向本刊申明 本刊将作适当处理。

《现代雷达》编辑部