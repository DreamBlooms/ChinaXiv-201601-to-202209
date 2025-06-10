# 三相级联型高频链矩阵整流器及其换流策略研究

邓文浪　杨永菁（湘潭大学信息工程学院湘潭411105）

![](images/41139bfdfc89397dde13286aed1aee234d03d72fa1a5445d12cb6829d8c4b491.jpg)

邓文浪女 1970年生，教授，博士生导师，主要研究方向为电力电子变换及其控制技术、矩阵变换器及其应用等。

摘要：提出了一种应用于高压场合的三相线电压级联型高频链矩阵整流器（LVC-HLFMR）拓扑，该拓扑由基于HLFMR 单元模块的三相线电压级联型变换器、高频变压器、单相整流器构成，可直接与三相系统相连，具有开关数量少、省略直流储能环节及结构紧凑等优点。分析了HLFMR的调制策略，在此基础上提出了针对三相桥直接级联结构特点的HFLMR改进换流策略，解决了采用常规换流时出现的负载开路问题，以及变换器工作状态切换至零矢量时的瞬时相间短路问题，仿真结果表明所提拓扑的正确性及改进换流策略的有效性。

关键词：线电压级联 高频链矩阵整流器 空间矢量调制一步换流 中图分类号：TM45

# Research on Three-Phase Line-Voltage-Cascaded HighFrequency Link Matrix Rectifier and Its Commutation Strategy

![](images/ddf32663bdea6f5853a9b3352fa5b9133691f6cde0c8beebb6baca501c593500.jpg)

Deng WenlangYang Yongjing （College of Information Engineering Xiangtan UniversityXiangtan411105 China ）

杨永菁男 1992年生，硕士研究生，主要研究方向为矩阵变换器及其应用。

Abstract: An three-phase line-voltage-cascaded high-frequency link matrix rectifier (LVC-HLFMR) topology applied in high-voltage situations is proposed in the paper. The topology consists of three-phase line voltage cascaded converter which based on HLFMR unit module,high frequency link transformer, single-phase rectifier，and it can be directly connected to a three-phase system.It has the advantages of few switch quantity, omit the dc energy storage link,compact structure, etc. The HLFMR modulation strategy is analyzed, on this basis an improved commutation strategy is proposed according to the three-phase bridge direct cascade structure characteristics. The problem of open load when using the conventional commutation strategy and the instantaneous short circuit problem when converter work status switch to zero vector are solved. The simulation and experimental results verify the validity of the proposed topology and the effectiveness of the improvement commutation strategy.

Keywords: Line-voltage-cascaded, high-frequency link matrix rectifier, space vector modulation, one-step commutation

# 1 引言

三相级联型功率变换器是一种以传统两电平六开关功率变换器为单元，通过线电压级联方式构成的多重化变换器，具有提高电压等级、谐波含量低、易于模块化、扩展性强的优点。与基于单相H桥的三相级联型变换器相比，开关数量更少，减少了所需直流电容，直流侧电压纹波小，因而更适合应用于高压场合。

1999年，E．Cengelci等学者提出了三重线电压级联变换器（LineVoltageCascade，LVC）拓扑结构，应用于中压可调速系统中，通过仿真验证其具有电压变化率低、谐波含量低等优点。JunWen和KeyueSmedley等提出通过限流电感把6个三相两电平电压源逆变器输出依次串联叠加得到六相输出，并将其应用于可调速六相电机。文献[1]提出一种三相线电压级联结构，由3个三相全桥逆变器的三相桥臂直接级联，输出线电压由子模块线电压叠加而成。文献[2]通过改变三相桥臂的连接方式，提出了一种新型线电压级联结构，使其更易于向更高级联数扩展。上述大部分研究均以基于传统两电平六开关功率变换器的三相级联变换器为研究对象，传统功率变换器中间环节包含的直流电容不仅降低了系统的可靠性，同时还会增加系统的体积与成本。此外，在实际应用中，基于电压等级的变换、安全、隔离等原因，往往需要将变换器采用隔离结构。

高频链矩阵整流器（HighFrequencyLinkMatrixRectifier，HFLMR）由精简矩阵变换器（ReducedMatrixConverter，RMC）、高频变压器与单相整流电路组成，该结构将传统隔离型整流器的三级结构简化为两级，省去中间直流环节的同时具备良好的输入输出特性。本文在此基础上提出了线电压级联高频链矩阵整流器（LineVoltage Cascade High-Frequency Link Matrix Rectifier，LVC-HFLMR）结构，以HFLMR为单元，通过线电压级联形成应用于高压大功率场合的多模块级联型变换器，其具备如下特点： $\textcircled{1}$ 结构紧凑，无直流储能环节； $\textcircled{2}$ 输入特性好，可四象限运行； $\textcircled{3}$ 高频变压器代替工频变压器，降低了变压器的体积与质量； $\textcircled{4}$ 三相线电压直接级联，节省开关数量。

换流策略是LVC-HFLMR实用化的关键技术之一，目前对于HFLMR的换流策略研究较为成熟，常用的方法有两步换流、四步换流和半自然一步换流。相较于两步或四步换流，半自然一步换流由于每个开关周期中开关上电压的极性和电流的方向都可以确定，方法简便且无需检测器件，具有更好的应用前景。LVC-HFLMR3个模块采用相同的开关信号，若简单使用HFLMR的换流策略则会出现换流时单个模块负载开路的情况。为此，本文基于LVC-HFLMR的结构特点，提出了一种适用于LVC-HFLMR的一步换流策略，避免了换流时可能出现的负载开路及瞬时相间短路问题，建立了LVC-HFLMR系统的仿真模型，仿真结果验证了所提拓扑及其换流策略的正确性和可行性。

# 2 LVC-HFLMR拓扑结构

图1为LVC-HFLMR的拓扑结构，主要由3个高频链矩阵整流器模块构成，交流侧由3个精简矩阵变换器线电压级联而成，RMC将输入工频交流转化为正、负交替的高频脉冲电，经高频变压器实现电压等级变换与电气隔离后，通过二极管全桥整流变换为直流，3个整流电路的输出并联后为负载提供直流输出。

LVC-HFLMR的3个三相桥桥臂中点分别记为${ \bf a } _ { 1 }$ ， $\mathbf { b } _ { 1 }$ ， $\mathbf { c } _ { 1 }$ ， ${ \bf a } _ { 2 }$ ， $\mathbf { b } _ { 2 }$ 、 $\mathbf { c } _ { 2 }$ 和 ${ \bf a } _ { 3 }$ ， $\mathbf { b } _ { 3 }$ 、 $\mathbf { c } _ { 3 }$ ，为简化分析，不妨假设三相电源平衡且内阻为0， $L _ { \mathrm { a } } = L _ { \mathrm { b } } = L _ { \mathrm { c } } = L$ 每个模块的器件参数相同，变压器匝数比为 $n$ 。

![](images/c6bc23361c8723a3e3cef115b7f81d392879ceedb6ddb9d07d46e360f700faf7.jpg)  
图1LVC-HFLMR 拓扑结构  
Fig.1The topology of LVC-HFLMR

由图1可知，LVC-HFLMR交流侧线电压为

$$
\left\{ \begin{array} { l l } { u _ { \mathrm { a b } } = u _ { \mathrm { a l b 1 } } + u _ { \mathrm { a 2 b 2 } } } \\ { u _ { \mathrm { b c } } = u _ { \mathrm { b 2 c 2 } } + u _ { \mathrm { b 3 c 3 } } } \\ { u _ { \mathrm { c a } } = u _ { \mathrm { c 3 a 3 } } + u _ { \mathrm { c 1 a l } } } \end{array} \right.
$$

设流进每个桥臂的电流分别为 $i _ { k i }$ ，（ $k = \mathrm { a }$ ，b，C； $i = 1$ ，2，3)，设输入三相电流对称，且有效值为 $I$ ，则有

$$
\begin{array} { r l } & { [ i _ { \mathrm { a } } = i _ { \mathrm { a l } } = \sqrt { 2 } I \sin \omega t  } \\ & {  \{ i _ { \mathrm { b } } = i _ { \mathrm { b 2 } } = \sqrt { 2 } I \sin ( \omega t - 1 2 0 ^ { \circ } )   } \\ & {   i _ { \mathrm { c } } = i _ { \mathrm { c 3 } } = \sqrt { 2 } I \sin ( \omega t + 1 2 0 ^ { \circ } )  } \end{array}
$$

根据图1所示的接线方式及基尔霍夫电流定律，可得

$$
\begin{array} { r l } & { \left\{ \begin{array} { l l } { i _ { \mathrm { a } { 1 } } + i _ { \mathrm { b } { 1 } } + i _ { \mathrm { c } { 1 } } = 0 } \\ { i _ { \mathrm { a } { 2 } } + i _ { \mathrm { b } { 2 } } + i _ { \mathrm { c } { 2 } } = 0 } \\ { i _ { \mathrm { a } { 3 } } + i _ { \mathrm { b } { 3 } } + i _ { \mathrm { c } { 3 } } = 0 } \end{array} \right. } \\ & { \left\{ \begin{array} { l l } { i _ { \mathrm { a } { 2 } } = - i _ { \mathrm { b } { 1 } } } \\ { i _ { \mathrm { b } { 3 } } = - i _ { \mathrm { c } { 2 } } } \\ { i _ { \mathrm { c } { 1 } } = - i _ { \mathrm { a } { 3 } } } \end{array} \right. } \end{array}
$$

考虑到系统每个子模块采用同步控制，且根据接线特点，空间矢量调制时，以第1扇区为例，仅$u _ { \mathrm { a b } }$ 、 $u _ { \mathrm { a c } }$ 两个线电压作用，电流关系有

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { i _ { \mathrm { b 1 } } = i _ { \mathrm { b } } } \\ { i _ { \mathrm { a 3 } } = - i _ { \mathrm { c } } } \\ { i _ { \mathrm { c 2 } } = 0 } \end{array} \right. } \end{array}
$$

第1扇区线电压平均值 $\overline { { u } } _ { \mathrm { a b } } = \overline { { u } } _ { \mathrm { a c } }$ ，两个线电压作用时间对称相等，可得 $\overline { { \dot { l } _ { _ { \mathrm { a 3 } } } } } = \overline { { \dot { l } _ { _ { \mathrm { b 1 } } } } }$ ，结合式（4）可得，在第1扇区中，基波分量为

$$
{ i _ { { \mathrm { _ { a 3 } } } } + i _ { { \mathrm { _ { b 1 } } } } + i _ { { \mathrm { _ { c 2 } } } } = 0 }
$$

同理，在每个扇区式（5）均成立。结合式(2）～式 (5)，可得每个模块的三个桥臂电流分别为

$$
\left\{ \begin{array} { l } { { \displaystyle i _ { \mathrm { a l } } = \sqrt { 2 } I \sin \omega t } } \\ { { } } \\ { { \displaystyle i _ { \mathrm { b l } } = \frac { 1 } { \sqrt { 3 } } \sqrt { 2 } I \sin \left( \omega t - 1 5 0 ^ { \circ } \right) } } \\ { { } } \\ { { \displaystyle i _ { \mathrm { c l } } = \frac { 1 } { \sqrt { 3 } } \sqrt { 2 } I \sin \left( \omega t + 1 5 0 ^ { \circ } \right) } } \end{array} \right.
$$

$$
\left\{ \begin{array} { l } { { i _ { \mathrm { a } 2 } = \displaystyle \frac { 1 } { \sqrt { 3 } } \sqrt { 2 } I \sin \left( \omega t + 3 0 ^ { \circ } \right) } } \\ { { } } \\ { { i _ { \mathrm { b } 2 } = \displaystyle \frac { 1 } { \sqrt { 3 } } \sqrt { 2 } I \sin \left( \omega t - 1 2 0 ^ { \circ } \right) } } \\ { { } } \\ { { i _ { \mathrm { c } 2 } = \displaystyle \frac { 1 } { \sqrt { 3 } } \sqrt { 2 } I \sin \left( \omega t + 9 0 ^ { \circ } \right) } } \end{array} \right.
$$

$$
\left\{ \begin{array} { l } { { i _ { \mathrm { a 3 } } = \displaystyle \frac { 1 } { \sqrt { 3 } } \sqrt { 2 } I \sin \left( \omega t - 3 0 ^ { \circ } \right) } } \\ { { } } \\ { { i _ { \mathrm { b 3 } } = \displaystyle \frac { 1 } { \sqrt { 3 } } \sqrt { 2 } I \sin \left( \omega t - 9 0 ^ { \circ } \right) } } \\ { { } } \\ { { i _ { \mathrm { c 3 } } = \sqrt { 2 } I \sin \left( \omega t + 1 2 0 ^ { \circ } \right) } } \end{array} \right.
$$

由式（6）可知，虽然每个子模块的3个桥臂电流不对称，但每个模块引出的输入相电流均为模块中电流最大项，选取开关时，仅需考虑三相输入相电流的幅值，且考虑开关采取同步动作，3个模块的RMC可等效为一个来进行简化分析。

忽略开关管的损耗后，高频变压器的简化等效电路如图2所示[5]，其中 $L _ { \mathrm { s } }$ 为等效漏电感； $C _ { \mathfrak { p } }$ 为一次侧回路分布电容； $\boldsymbol { C } _ { \mathrm { s } } ^ { \prime }$ 为折算到一次侧的二次侧回路电容； $R _ { 1 }$ 为电源内阻； ${ \boldsymbol { R } } _ { 2 } ^ { \prime }$ 为折算后的负载绕组电阻。

![](images/00a2646cac2049439e1e638f3cd4b507bcc8de8ffd3cc4b27e5b9a71aae1e007.jpg)  
图2高频变压器等效电路   
Fig.2The equivalent circuit of high frequency link transformer   
图3简化隔离部分等效开关电路  
Fig.3Simplified equivalent switch circuit ofIsolated part

在图2等效电路中，高频变压器输入侧为RMC的高频输出，无直流电容，而输出侧为直流电容，考虑直流电容的值要远大于变压器分布电容的值，二次电阻相较负载电阻可忽略。得到工作状态下隔离环节的等效电路如图3所示。

R干3 ++理想变压器

在每个工作状态下，电流只流经3个模块中的其中2个模块，变压器二次侧高频脉冲电整流后并联输出，等效理想变压器电压比为 $n / 2$ ，综合可得

LVC-HFLMR的等效电路如图4所示。

![](images/470f92c69241dd98a3a9b2d60dcea46e94c9ec19bbb24a2eae63053b0f010fc4.jpg)  
图4LVC-HFLMR 等效开关电路  
图5 扇区划分

从等效电路可以看出，LVC-HFLMR结构功能与高频矩阵整流器相同，虽然级联更多的元件不可避免地带来更多的器件损耗，但级联器件分担电压应力的作用对于满足系统高电压等级的需求意义十分重大。

# 3 LVC-HFLMR调制策略

考虑到3个模块采取相同的开关信号，这里主要对单个模块HFLMR的调制策略进行分析。双极性电流空间矢量（Bipolar-Current-SpaleVectorModulation，B-C-SVM）能够实现输入电流正弦，功率因数可调，输出电压/电流纹波小且开关损耗低，是目前较为适用HFLMR的调制策略。不同于传统电流空间矢量，为了得到正负交变的高频脉冲电，输入电流由两组极性相反的基本矢量及零矢量进行合成，得到的输出极性有正有负，因而称之为双极性电流空间矢量调制。

采用图5扇区划分，不同于传统B-C-SVM的6扇区划分，将HFLMR输入电流空间矢量复平面划分为12个扇区，每个扇区里三相输入电压之间的相对大小是确定的。例如，扇区1中 $u _ { \mathrm { a } } > u _ { \mathrm { c } } > u _ { \mathrm { b } }$ 扇区2中 $u _ { \mathrm { a } } > u _ { \mathrm { b } } > u _ { \mathrm { c } }$ 。在合成矢量时，选择对应线电压较低的矢量先作用，如图5a所示，当需要合成的矢量 $I _ { \mathrm { r } }$ 位于扇区1时，选择矢量 $\pmb { I } _ { \mathrm { a b } }$ 、 $\boldsymbol { I } _ { \mathrm { a c } }$ 进行合

![](images/9765b3e2595d7b2d3241bd5ed9b6d61f8d5339f1224a348aa91d01d695b4c3a0.jpg)  
(a）输入电流空间矢量  
Fig.5 Sector division

u  
XIXOXIX  
XXX区123456789101112(b）三相输入电压波形及扇区划分

成，矢量 $\pmb { I } _ { \mathrm { a b } }$ ， $\boldsymbol { I } _ { \mathrm { a c } }$ 对应的线电压分别为 $u _ { \mathrm { a b } }$ ， $u _ { \mathrm { a c } }$ ，在扇区1中 $u _ { \mathrm { a b } } > u _ { \mathrm { a c } }$ ，此时，选择 $\pmb { I } _ { \mathrm { a c } }$ 先作用，以保证矢量切换时，工作电压总是从 $u _ { \mathrm { a c } }$ 切换至 $u _ { \mathrm { a b } }$ ，使得换流过程实现自然换流。由于矩阵整流器输出为高频电，所需合成的输入电流矢量由参考输入相电流所在扇区相邻的两个有效矢量（用来得到输出正电流 $I _ { \mathrm { m } }$ )、与之极性相反的两个有效矢量（得到输出负电流 $- I _ { \mathrm { m } }$ ）和零矢量这5个矢量合成。以扇区1为例，输入相电流由 $\pmb { I } _ { \mathrm { a b } }$ ， $I _ { \mathrm { a c } }$ ， $I _ { \mathrm { b a } }$ ， $\boldsymbol { I _ { \mathrm { c a } } }$ 和 $I _ { \mathrm { a a } } 5$ 个矢量合成。

![](images/16d02e27c94f58e36428d4cf50919fb92ded91b0427a61103ae248d35546c5e2.jpg)  
Fig.4Equivalent switch circuit ofLVC-HFLMR   
图6B-C-SVM的输出电压、矢量合成顺序图Fig.6B-C-SVM output voltage、vector synthesis sequence

设三相输入电压为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { u _ { \mathrm { a } } = \sqrt { 2 } U \sin \omega t } \\ { u _ { \mathrm { b } } = \sqrt { 2 } U \sin \left( \omega t - 1 2 0 ^ { \circ } \right) } \\ { u _ { \mathrm { c } } = \sqrt { 2 } U \sin \left( \omega t + 1 2 0 ^ { \circ } \right) } \end{array} \right. } \end{array}
$$

以图6所示扇区1矢量合成顺序图为例，当参考电流 $I _ { \mathrm { r } }$ 位于扇区1时，一个开关周期的前半周期，由扇区相邻的2个有效矢量 $\pmb { I } _ { \mathrm { a b } }$ 、 $\boldsymbol { I } _ { \mathrm { a c } }$ 及零矢量合成 $I _ { \mathrm { r } }$ ，此时RMC输出正向电流 $I _ { \mathrm { { m } } }$ ，变压器一次电压为 $U _ { \mathrm { a b } }$ ， $U _ { \mathrm { a c } }$ 。对应的各矢量作用时间计算式为

$$
\left[ \begin{array} { c } { T _ { \mathrm { { a } } } = T _ { \mathrm { { a b } } } = T _ { \mathrm { { b a } } } = \frac { m \sin \left( \frac { \pi } { 6 } - \theta _ { i } \right) T _ { s } } { 2 } } \\ { T _ { \mathrm { { a } } } = T _ { \mathrm { { a c } } } = T _ { \mathrm { { c a } } } = \frac { m \sin \left( \frac { \pi } { 6 } + \theta _ { i } \right) T _ { s } } { 2 } } \end{array} \right]
$$

$$
\boxed { T _ { \scriptscriptstyle 0 } = \frac { T _ { \mathrm { s } } } { 2 } - T _ { \mathrm { a b } } - T _ { \mathrm { a c } } }
$$

式中， $T _ { \mathrm { s } }$ 为开关周期； $\mathbf { \nabla } _ { m }$ 为调制比； $\theta _ { i }$ 为参考电流矢量与 $I _ { 1 }$ 矢量的夹角， $\theta _ { i } = \omega t - \varphi + 3 0 ^ { \circ }$ 。其前半周期矢量合成方式如图7所示。

![](images/dc6454e8dce4603de3bd8fb5c670a6add5999f6414f4af140d6d5a515cd98a72.jpg)  
图7扇区1矢量合成方式

后半周期与前半周期类似，为了得到与前半周期极性相反的电流，使用扇区7相邻的两个矢量$I _ { \mathrm { b a } }$ ， $\boldsymbol { I _ { \mathrm { c a } } }$ 。变压器一次电压为 $U _ { \mathrm { b a } }$ 、 $U _ { \mathrm { c a } }$ 。开关信号与前半周期相反，此时RMC输出反向电流 $- I _ { \mathrm { m } }$ ，基本矢量的占空比只与 $\theta _ { i }$ 及 $m$ 有关，在一个周期中，这两个参数均保持不变，后半周期的基本矢量占空比与前半周期相同，从而得到一个周期内正负交替高频电。

仅考虑三相输入相电流，分析其前半周期的电流平均值为

$$
\begin{array} { l } { { \displaystyle { \{ \overline { { i } } _ { \mathrm { a l } } = \frac { ( T _ { 1 } + T _ { 2 } ) I _ { \mathrm { m } } } { T _ { s } } = \sqrt { 2 } I \cos ( \theta _ { i } - 3 0 ^ { \circ } )  } } } \\ { { \displaystyle {  \begin{array} { l } { { \{ \overline { { i } } _ { \mathrm { b 2 } } = \frac { - T _ { 1 } I _ { \mathrm { m } } } { T _ { s } } = - \sqrt { 2 } I \sin ( 6 0 ^ { \circ } - \theta _ { i } )  } } \\ { {  \overline { { i } } _ { \mathrm { c 3 } } = \frac { - T _ { 2 } I _ { \mathrm { m } } } { T _ { s } } = - \sqrt { 2 } I \sin \theta _ { i } } \end{array}  } } } \end{array} }
$$

后半周期的矢量作用时间与前半周期对应的矢量相同，得到的电流平均值也完全相同，代入 $\theta _ { i } =$ $\omega t - \varphi + 3 0 ^ { \circ }$ ，得

$$
\begin{array} { r l } & { \left\{ \overline { { i } } _ { \mathrm { a } } = \overline { { i } } _ { \mathrm { a l } } = \sqrt { 2 } I _ { \mathrm { m } } \cos \left( \omega t - \varphi \right) \right. } \\ & { \left\{ \overline { { i } } _ { \mathrm { b } } = \overline { { i } } _ { \mathrm { b } 2 } = \sqrt { 2 } I _ { \mathrm { m } } \cos \left( \omega t - \varphi - 1 2 0 ^ { \circ } \right) \right. } \\ & { \left. \overline { { i } } _ { \mathrm { c } } = \overline { { i } } _ { \mathrm { c } 3 } = \sqrt { 2 } I _ { \mathrm { m } } \cos \left( \omega t - \varphi + 1 2 0 ^ { \circ } \right) \right. } \end{array}
$$

上式表明三相输入电流正弦对称，调节参考矢量与输入电压矢量的夹角 $\varphi$ 可调节输入功率因数。

# 4 LVC-HFLMR的一步换流策略

在划分的12个扇区中，每个扇区里三相的相电压大小关系都是相对稳定的，在上述调制策略中，为了增大电压利用率，并尽量减少开关损耗，相电压绝对值最大的一相始终保持导通，换流发生在另外极性相同的两相之中。例如，扇区1中， $u _ { \mathrm { a } } > 0$ $u _ { \mathrm { c } } < 0$ ， $u _ { \mathrm { b } } < 0$ ，换流发生在 $\boldsymbol { \mathrm { \textbf { b } } }$ 、c相中。通过选择合适的矢量作用顺序，可以实现所提拓扑结构的一步换流。

下面以扇区1的一个PWM周期前半周期为例，说明其换流过程，其中， $^ { * } 1 ^ { * }$ 表示上桥臂导通； $^ { 6 6 } 0 ^ { 9 }$ 表示下桥臂导通；“X”表示上、下桥臂均关断；“S”表示上、下桥臂均导通，该桥臂呈直通状态。

(1）在开关状态由1X0变为10X过程中，变压器一次电压由 $u _ { \mathrm { a c } }$ 变成 $u _ { \mathrm { a b } }$ ，驱动开通 $\mathrm { S } _ { \mathrm { b l } }$ （双向开关的两个IGBT同时给予导通信号）的同时关断 $\mathrm { \Delta S _ { c l } }$ 由于IGBT的导通时间远小于其关断时间，此时，并不会出现变压器一次侧开路的情况，且由于 $u _ { \mathrm { c } } >$ $u _ { \mathrm { b } }$ ，B、C相之间不会发生相间短路。工作电流由 $i _ { \mathrm { a c } }$ 切换至 $i _ { \mathrm { a b } }$ ，该过程为自然换流，开关管实现软关断。

此时电流由原本流经1、3模块，转为流经1、2模块，换流前后的电流路径如图8、图9所示，此时各模块C相桥臂均未导通，导致第三模块变压器一次侧开路，如图10所示。此时，选择导通第三模块 $\mathrm { \Delta S _ { a l } }$ 使A相桥臂直通，给变压器漏感提供泄能

![](images/f82c367ca5bf1adfd237bed3a3199d5e8210238598dee5c168d93f05a90f2c58.jpg)  
Fig.7Sector 1 vector synthesis method   
图8换流前 $u _ { \mathrm { a c } }$ 工作时的电流路径  
Fig.8The current path before switching when $u _ { \mathrm { a c } }$ works

![](images/6e6869238bb0f23943bff391eddbe537e9f91368ffbaf660cc76af3428a0c927.jpg)  
图9换流后 $u _ { \mathrm { a b } }$ 工作时的电流路径

![](images/0e6a9e92d7d1bd282055e7302fc403b74306e40aac42d1e86a81705ee02d166a.jpg)  
图10第三模块变压器一次侧开路

回路。

上述换流过程开关动作状态如图11所示。其中， $\mathrm { \Delta S _ { 3 a l } }$ 表示第三个模块的A相桥臂下开关。 $\mathrm { \Delta S } _ { \mathrm { 3 a l } }$ 在第三个模块漏感电流降为零后，将开关信号变为低电平进行关断。

同理，在划分的12个扇区中，每个扇区三相输入的相对大小确定。通过安排合理的有效矢量作用顺序，便可以实现有效矢量切换时的一步自然换流。

![](images/b6f907fc76ae2212055ffc5d71edd9fafc402d5ac473529242ff02b982490a42.jpg)  
Fig.9The current path after switching when $u _ { \mathrm { a b } }$ works   
Fig.10Third module transformer open circuit   
图11 $1 \mathrm { X } 0 \to 1 0 \mathrm { X }$ 时开关动作Fig.11Switch action when $1 \mathrm { X } 0 \to 1 0 \mathrm { X }$ （204号

(2）在开关状态由10X变为SXX过程中，变压器一次电压由 $u _ { \mathrm { a b } }$ 变为零，变换器将由 $\mathrm { S _ { a h } }$ ， $\mathrm { \Delta S _ { b l } }$ 导通转为 $\mathrm { \Delta S _ { a h } }$ 、 $\mathrm { \Delta S _ { a l } }$ 直通给变压器漏感放电提供路径。此时，若直接一步换流，关断 $\mathrm { S } _ { \mathrm { b l } }$ 的同时导通 $\mathrm { \Delta S _ { a l } }$ 由于A相电压最大， $\mathrm { \Delta S _ { a l + } }$ 流过如图12所示电流，此时 $\mathrm { S } _ { \mathrm { b l } }$ 开关管由于关断的延时，流经 $\mathrm { \Delta S _ { b l } }$ 的电流不会马上下降，反而由于流过 $\mathrm { \Delta S _ { a l + } }$ 的电流与变压器逐渐增大的一次电流均流过 $\mathrm { S } _ { \mathrm { b l - } }$ 而出现瞬时过冲，然后再开始下降，直至关断。可以看到，在上述换流过程中，A、B相存在一个短暂的相间短路过程，开关管 $\mathrm { S } _ { \mathrm { b l - } }$ 上的电流会出现瞬时过冲，这对开关管的安全工作不利。

为了避免上述换流时出现的相间短路，在变压器一次电压由 $u _ { \mathrm { a b } }$ 变为零的过程中，采用两步换流的思想，仅导通 $\mathrm { \Delta S _ { a l - } }$ ，此时，与之前的分析类似，电流依然流过 $\mathrm { S } _ { \mathrm { b l } }$ ，然后关断 $\mathrm { S } _ { \mathrm { b l } }$ ，电流被强迫换流至Sal-o

此换流过程开关动作状态如图13所示。其他扇区的换流过程与扇区1类似，工作矢量间切换时为自然换流，开关管均为软关断，切换至零矢量时，为强迫换流，此过程中由于开关的关断时间远大于开关的导通时间，仍可同时给予两组开关动作信号，

![](images/4ec8c481aa08aced7c2b62719e80ef0d17a34b20fc6984a05f37fb7dfbace766.jpg)  
图12 暂态过程 $u _ { \mathrm { a b } } \to 0$

![](images/7f526810d40236c986e7eb647380963336cec3c36293afc7b83ba57052ebb5ea.jpg)  
Fig.12The transient process of $u _ { \mathrm { a b } } \to 0$   
图13切换至零矢量时开关动作  
Fig.13Switch action when switching to zero vector

实现一步换流。

# 5 仿真研究

在上述理论分析的基础上，在Matlab/Simulink中搭建了LVC-HFLMR及其控制系统的仿真模型。仿真参数如下：网侧输入额定相电压 $2 2 0 \mathrm { V }$ ，额定频率 $5 0 \mathrm { { H z } }$ ，直流电感 $L _ { 0 } = 1 0 \mathrm { m H }$ ，直流电容 $C _ { 0 } = 1 \mu \mathrm { F }$ 负载电阻 $R = 2 \Omega$ ，开关频率为 $1 0 \mathrm { k H z }$ 。系统仿真波形如图14所示。

由图 $1 4 \mathrm { a \sim }$ 图14c可知，LVC-HFLMR可以实现近单位功率因数运行，输出稳定的直流电压。图

![](images/21f2367c1a8e7975ddbff4cdec0222bc32673c62a7a6ca03762cd5c97a7c56a2.jpg)  
  
Fig.14Simulation waveforms of LVC-HFLMR

14d为变压器一次电压波形，在每个开关周期内，矢量合成时均由较小的线电压对应的矢量先作用，以保证换流时实现自然换流。对比图14e与图14f可知，每个工作状态只有两个模块工作，改进换流策略给非工作状态模块的变压器漏感提供了泄能路径，避免了非工作状态变压器的一次侧开路，且每个变压器在一个周期中，仅有1/3的时间会出现非工作状态，减小了高峰电压，使得一次电压更低,提高了系统的安全性。

# 6 结束语

（1）提出了输入侧三相直接级联、输出侧并联的LVC-HFLMR 拓扑，相对于基于单相H桥的三相级联结构，节省了开关管的数量，省略了直流侧电容，有效地提高了开关的电压等级，且利用高频变压器代替传统变压器，使得系统体积更小，结构更加紧凑，成本更低，在三相高压系统中具有较好的应用前景。

(2）基于HFLMR的一步换流策略，将输入相电流划分为12个扇区，根据每个扇区内三相输入电压的相对大小关系，确定每个扇区矢量切换的顺序，选择合适的开关顺序，实现了LVC-HFLMR的安全换流，简化了换流逻辑，提高了换流可靠性。

（3）针对LVC-HFLMR换流时可能出现负载短路的模块，直通一组桥臂，给变压器漏感提供放能路径。采用两步换流的思想，避免了工作状态切换至零矢量时的瞬时短路问题，提高了换流策略的安全性与可靠性。

# 参考文献

[1] 何金平，毛承雄，陆继明，等．三相线电压级联 多电平变换器原理及仿真研究[J]．高电压技术, 2007，33(4):170-174. He Jinping,Mao Chengxiong,Lu Jiming.Research on three phase line voltage cascaded multilevel converter[J].High Voltage Engi-neering,2007,33 (4): 170-174.   
[2] 陆治国，赵丽丽，吴春军．一种新型的三相桥级联 型PWM变换器[J]．电力系统保护与控制，2012, 40(24): 131-137. Lu Zhiguo,Zhao Lili,Wu Chunjun.A novel threephase-bridge cascaded PWM converter[J].Power System Protection and Control, 2012,40(24):131- 137.   
[3] 王志强，夏长亮，史婷娜．基于等效开关电路模 型的三重化线电压级联型变换器[J]．中国电机工 程学报，2013，33(6)：15-24. Wang Zhiqiang,Xia Changliang,Shi Tingna. The triple line-voltage cascaded converter control based on the equivalent switch circuit model[J]. Proceedings of the CSEE, 2013, 33(6): 15-24.   
[4] Xia Changliang, Zhou Faqiang, Wang Zhiqiang. Equivalent switch circuit model and proportional resonant control for triple line-voltage cascaded voltage-source converter[J]. IEEE Transactions on Power Electronics,2013,28(5): 2389-2401.   
[5] 习超．电子电力变压器等效模型及其应用[D]．武 汉：华中科技大学，2007.   
[6] Toliyat HA,Waikar S,Lipo T A.Analysis and simulation of five phase synchronous eluctance machines including third harmonic of airgap MMF[J]. IEEE Transactions on Industry Applications,1998,4(2): 332-339.   
[7] 邓文浪，杨欣荣，朱建林，等．18开关双级矩阵 变换器的空间矢量调制策略及其仿真研究[J]．中 国电机工程学报，2005，25(15)：84-90. Deng Wenlang, Yang Xinrong, Zhu Jianlin, et al. Space vector modulation strategy of two-stage matrix converter with 18 switch and it's simulation study[J]. Proceedings of the CSEE,2005,25(15): 84-90.   
[8] Jun Wen, Keyue Smedley. A new multilevel inverterhexagram inverter for medium-voltage adjustable speed drive systems part I: six-phase motor drive[J]. Powering,2007, 4(4): 611-617.   
[9] Empringham L, Kolar JW, Rodriguez J, et al. Technological issues and industrial application of matrix converters: a review[J]. IEEE Transactions on Industrial Electronics,2013,60(10): 4260-4271.   
[10] Nguyen T D,Lee H H.Carrier-based PWM technique for three-to-five phase indirect matrix converters[C]. IECON 2011 Conference on IEEE Industrial Electronics Society,2011: 3662-3667.   
[11]Bozorgi A M, Monfared M, Mashhadi HR. Two simple over modulation algorithms for space vector modulated three-phase to three-phase matrix converter[J].IET Power Electronics,2014,7(7): 1915-1924.