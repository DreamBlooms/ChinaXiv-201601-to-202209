# 基于高频隔离交交直接变换器的新型STATCOM研究

师贺李磊 马爱华管月（南京理工大学自动化学院 南京210018）

![](images/7aab512314dcb6100151389f51324acf5645eeebb9587e0af6e8f8effa92187e.jpg)

师贺男1991年生，硕士研究生，研究方向为电力电子在电力系统中的应用。

摘要：本文首先介绍了一种基于交交直接变换器的新型无功补偿器，没有直流储能环节，补偿器可靠性更好，成本更低。以推挽正激式交流变换器为研究对象，分析了新型 STATCOM的工作原理、补偿特性以及控制策略。首次将高频隔离变换器引入新型 STATCOM的研究，实现了网侧和补偿电容的电气隔离，增大了补偿器补偿容量。提出了一种基于单相无功电流检测方法的直接电流控制方案，相较于目前基于正交分解模块和dq坐标变换的控制方式，该方案计算量小，结构简单，容易实现。最后，进行了仿真实验，验证以上理论分析以及本文提出的直接电流控制方案。仿真结果表明，基于推挽正激式交流变换器的新型 STATCOM可以实现对网侧无功电流的实时动态补偿，系统稳定性好，闭环控制调节快速，无静态误差。

关键词：交交直接变换器 推挽正激 STATCOM直接电流控制中图分类号：TM464

![](images/b8e7578785bc6cd3daca7e1f9669274c90f2d8fe1d58aaf9db6d13649022f1e9.jpg)

# Research of Novel STATCOM Based on Insolated High Frequency AC-AC Converter

Shi He LiLeiMa Aihua Guan Yue (Nanjing University of Science &TechnologyNanjing210094 China）

李磊男 1975年生，博士，副教授，博士生导师，研究方向为多电平技术和电力电子在电力系统中的应用。

Abstract: Firstly, a novel STATCOM based on AC-AC converter is introduced in this paper, which lack of DC link energy storage and is more reliable and cost-effective. Pushpull forward AC converter is used for the study,and the working principle, compensation characteristics,control strategy is studied. Insolated high frequency ac-ac converter is introduced intonovel STATCOM, as a result, electrical isolationbetween grid-side and the compensation capacitor is implemented and compensation capacity is increased. Direct current control scheme which based on single-phase reactive current detection methods have been proposed in this paper. Compared with present control mode which based on orthogonal decomposition module and dqcoordinate transformation,the scheme proposed has less calculation amount and simple structure,and it is easy to achieve. Finally, the simulation was carry out to verify above theoretical analysis and the proposed direct current control scheme.The simulation results show thatnovel STATCOM based on insolated high frequency AC-AC convertercan compensate reactive current real time and dynamically. The system is stablewell, closed-loop can adjust the compensator quickly without static error.

Keywords: AC-AC converter, push-pull forward, STATCOM, direct current control icheme

# 1 引言

无功功率是电力系统中一个重要的物理量，大多数网络元件以及负载都需要消耗无功功率，这些无功通过发电机提供并且实现长距离的传送显然是不合理的，甚至是不可能的，合理的方法是在需要消耗无功功率的地方设置无功补偿装置，向电网吸收（或发出）无功[]。早期的无功补偿装置有同步调相机、并联电容器等，它们存在体积大、成本高及动态补偿受限等多种缺点。因而后来出现了静止无功补偿装置，典型代表是静止无功补偿器(SVC)和静止无功发生器（STATCOM)。SVC在动态调节基波无功时，还需考虑自身产生的高次谐波的消除问题，并且在系统电压低时，其无功补偿的能力会降低。STATCOM指由自换相的电力半导体桥式变流器来吸收或发出无功功率的动态补偿装置，能够动态地补偿快速变化的瞬时无功功率，控制灵活，调节速度快[2]。但由于目前的主流STATCOM主功率电路采用DC/AC的电压源逆变结构。电压源逆变器的直流侧采用大容量电解电容器组作为储能元件，电解电容的使用带来如下问题：首先，电解电容寿命较短，容易损坏，从而使得STATCOM装置可靠性较差；其次，储能电容体积大，价格昂贵，大大限制了STATCOM的市场前景。所以传统STATCOM在工业生产上的应用并不广泛。

2008年，美国学者DeepakDivan 和JyotiSastry在一篇文章中提出了Inverter-less STATCOMs的概念[3]，将传统的补偿电容器通过交流斩波器并联接入电网中，通过对交流斩波器的控制，补偿电容呈现出“动态电容器”的特性，因而可以实现对无功功率的连续动态补偿，有很高的调节速度。但是文献只是介绍了这一补偿方式的基本原理，没有对这一新技术的特性以及控制策略做深入研究。基于这一思想，国内外学者对无逆变结构STATCOM的系统结构、特性以及控制策略做了相应的研究，并试图把这种方法从单相系统扩展到三相系统中。但以上的研究内容都是基于Buck型和Boost型基本交流斩波器展开，补偿容量较小，系统闭环控制策略复杂而又单一，因而这项新技术尚且处在一个发展阶段，新型交流变换器的引入、补偿容量的增加以及新的闭环控制方案的设计及简化等方面都有待深入研究[4-7]

本文首次将高频隔离的推挽正激式交交直接变换器代替基本交流斩波器引入到新型STATCOM的研究中。新拓扑的应用，增大了装置无功补偿容量，并且实现了电网侧和补偿电容侧的电气隔离，提高了补偿装置的可靠性。文章详细分析了交流变换器的工作原理以及新型STATCOM的补偿特性，基于单相无功实时检测方法提出了一种简单可靠的直接电流控制方案，相较于目前基于正交分解模块和dq坐标变换的控制方式，该方案计算量小，结构简单，容易实现。设计了新型 STATCOM，实现了其对基波无功的实时精确补偿功能。

# 2基于交流变换器的无功补偿原理

基于交流变换器的无功补偿系统结构如图1a所示。交交变换器直接和电网并联，变换器负载为传统的无功补偿电容器，因而交流变换器可以从电网侧“吸收”一个超前电网电压 $9 0 ^ { \circ }$ 的容性电流 $i _ { \mathrm { c } }$ 。图1b中， $U _ { \mathrm { s } }$ 表示电压矢量， $I _ { \mathrm { L } }$ 表示负载电流矢量，一般电力系统负载为感性，所以电流滞后电网。当STATCOM投入到系统中，容性电流 $I _ { \mathrm { c } }$ 对感性无功进行补偿，网侧电流 $ { I _ { \mathrm { s } } } =  { I _ { \mathrm { L } } } +  { I _ { \mathrm { c } } }$ ，显然，通过控制交流变换器“吸收”的容性电流 $I _ { \mathrm { c } }$ 的大小，就可使得$I _ { \mathrm { s } }$ 的相位和网侧电压相同，实现动态无功补偿。

![](images/d8b03aee742d8b3ac6d107e90f9be2893c955fba43396f2edb61a787c0fe3112.jpg)  
图1基于交流变换器的无功补偿原理图 Fig.1Reactive power compensation schematics based on AC converter

新型STATCOM装置主要包括两部分：交交变换器和无功补偿电容器。本文交交变换器应用高频隔离推挽正激式交交直接变换器，其拓扑结构如图2所示。

![](images/d3de6766228e61476abc30b0d55a23d778bf7e1e468fd8f5922d72adafe811bd.jpg)  
图2高频隔离推挽正激式交交直接变换器 Fig.2Insolated high frequency push-pull forward AC-AC converter

推挽正激类拓扑通过在推挽拓扑结构中附加一个钳位吸收电容 $C _ { s }$ ，实现了对高频变压器漏感能量的回收，同时也抑制一次侧开关管电压尖峰。推挽正激拓扑整体上可以分为5个部分：高频变压器、变压器一次侧的推挽正激结构斩波器1、变压器二次侧全波整流斩波器2、输入滤波器和输出滤波器。高频变压器有4个绕组：一次绕组 $T _ { \mathrm { p 1 } }$ ， $T _ { \mathfrak { p } 2 }$ ，二次绕组 $T _ { \mathrm { s l } }$ 和 $T _ { \mathrm { p 2 } }$ 。一、二次侧匝数： $N _ { \mathfrak { p } 1 } = N _ { \mathfrak { p } 2 } \ . \ N _ { \mathfrak { s } 1 } = N _ { \mathfrak { p } 2 }$ 定义电压比为： $N { = } N _ { \mathrm { s l } } / N _ { \mathrm { p l } }$ 。输入滤波器 $L _ { \mathrm { i } }$ 和输入电容 $C _ { \mathrm { i } }$ 用于滤除变换器输入电流中的谐波成分，主要是开关频率成分。输出滤波器滤除输出电压的开关频率成分。

根据不同的输入输出，交流变换器有两种工作模式， $u _ { \mathrm { i } } > 0$ 为模式1, $u _ { \mathrm { i } } < 0$ 为模式2；根据 $u _ { \mathrm { N p } }$ 的极性和 $u _ { \mathrm { s } }$ 极性的关系，每个开关周期分为4个工作阶段：一个正向阶段（ $u _ { \mathrm { N p } }$ 和 $u _ { \mathrm { s } }$ 极性相同)、一个反向阶段（ $u _ { \mathrm { N p } }$ 和 $u _ { \mathrm { s } }$ 极性相反）、两个零阶段（ $\dot { \left. u _ { \mathrm { N p } } \right. }$ 为零)。工作过程的主要波形图如图3所示。图3中每个开关周期有两个三角波，因此产生两个开通脉冲。占空比重新定义如下：占空比 $D$ 大小等于二次侧整流电路输出电压 $u _ { \mathrm { A B } }$ 在一个开关周期 $T$ 内的占空比。

由图3可以看出，输出滤波器前端的电压 $u _ { \mathrm { A B } }$ 是一个单极性幅值为正弦变化的脉冲波，其脉冲周期是开关周期的两倍。当负载为电容时，高频隔离推挽正激式交交直接变换器的输入输出特性为

$$
\begin{array} { l } { \displaystyle { \{ u _ { \mathrm { o } } = N D u _ { \mathrm { s } }  } } \\ { \displaystyle { \vphantom { ( \frac { \partial _ { \mathrm { d } } } { \partial _ { \mathrm { o } } } = C \frac { \mathrm { d } u _ { \mathrm { o } } } { \mathrm { d } t } }  } } \\ { \displaystyle {  \vphantom { ( \frac { \partial _ { \mathrm { d } } } { \partial _ { \mathrm { c } } } = N D i _ { \mathrm { o } } }  } } \end{array}
$$

式中，网侧电压 $u _ { \mathrm { s } } = U _ { \mathrm { m } } \mathrm { s i n } \omega t$ ； $C$ 为补偿电容的容值； $N$ 为变压器电压比； $D$ 为占空比； $i _ { \mathrm { o } }$ 为负载电

![](images/19455ea6c48e4fe7aa664ffcbda05d019fed69f508620adafaffe9f1ca47f17f.jpg)  
图3主要波形图Fig.3Main waveforms

流，则网侧注入电流 $i _ { \mathrm { c } }$ 为

$$
 i _ { \mathrm { c } } = \omega C N ^ { 2 } D ^ { 2 } U _ { \mathrm { m } } \cos { \omega t }
$$

式（2）表明，正常情况电网的电压幅值 $U _ { \mathrm { m } }$ ，变压器电压比 $N$ 以及补偿电容 $C$ 都是定值，因此补偿电流 $i _ { \mathrm { c } }$ 的大小只和占空比 $D$ 有关，通过对 $D$ 的动态控制实现无功的实时补偿。基于高频隔离推挽正激式新型STATCOM可以被看成是一个容值可调节的可变电器，电流 $i _ { \mathrm { c } }$ 超前网侧电压 $9 0 ^ { \circ }$ 。

和基于交流斩波器的 STATCOM相比，本文 $i _ { \mathrm { c } }$ 的大小和变压器电压比 $N$ 有直接的关系，因此在其他外界条件一致的情况下，新型STATCOM的注入电流大小，即补偿容量相较于基于交流斩波器的 STATCOM可以更大，如图4所示。图4a为 $N =$

![](images/f8fd97bc58b3e54bd9a1e422aa30d09d62a277bb389eae3f7f071ef3d3fce166.jpg)  
(a）新型STATCOM补偿容量

![](images/d880f13a0ae2d5c3a376d6033bf1b7e049198e5793705671b01ba67e1d959af2.jpg)  
图4补偿容量对比

2时，新型STATCOM的补偿电流和网侧电压等级$U _ { \mathrm { m } }$ 和占空比 $D$ 的关系，图4b为基于交流斩波器的STATCOM的补偿电流和 $U _ { \mathrm { m } }$ ， $D$ 的关系[8]，可见相同电压等级和占空比以及其他参数一样的条件下，前者的补偿容量是后者的4倍。

# 3新型STATCOM的直接电流控制

# 3.1单项无功电流检测

单相无功电流的检测目前采用较多的是从三相无功电流检测方法推导出来的dq坐标变换法，这种方法需要将采样电流 $i _ { \mathrm { s } }$ 进行正交分解，对两个正交量进行dq变换，得到代表无功电流的 $i _ { \mathrm { q } }$ 分量。这种检测方法比较复杂，对正交分量产生模块的设计精度要求高。另外一种单相无功电流检测方法是将单相电流首先构造成三相电流，然后再用三相检测方法检测单相无功电流，这种方法的缺点是计算复杂，并且有额外的延时影响检测效率。本文采用的是一种直接单相无功电流检测方法[9]，检测原理如下。

首先，网侧电流 $i _ { \mathrm { s } }$ 可以分解成两个部分，即

$$
{ i } _ { \mathrm { s } } = { i } _ { \mathrm { p } } ( t ) + { i } _ { \mathrm { q } } ( t )
$$

式中， $i _ { \mathrm { p } } ( t )$ 表示电网电流有功分量； $i _ { \mathrm { q } } ( t )$ 表示电网电流无功分量。设网侧电压为 $u _ { \mathrm { s } } = U _ { \mathrm { m } } \mathrm { s i n } \ \omega t$ ，则式(3）可以写成

$$
i _ { \mathrm { s } } = I _ { \mathrm { p } } \sin \omega t + I _ { \mathrm { q } } \cos \omega t
$$

式（4）和与电网电压同步的余弦信号相乘即得到

$$
\begin{array} { r } { i _ { \mathrm { s } } \cos \omega t = I _ { \mathrm { p } } \sin \omega t \cos \omega t + I _ { \mathrm { q } } \cos ^ { 2 } \omega t } \\ { = \cfrac { I _ { \mathrm { q } } } { 2 } + \cfrac { I _ { \mathrm { q } } } { 2 } \cos 2 \omega t + \cfrac { I _ { \mathrm { p } } } { 2 } \sin 2 \omega t } \end{array}
$$

式（5）表明，网侧电流的无功成分Icosωt可以由 $I _ { \mathrm { q } } / 2$ 表示，也就是说，交流无功被变换了直流分量，采用一定的措施得到这个直流分量，即可检测到网侧电流中无功的含量。例如将网侧电流和与电网电压同步的余弦信号相乘的信号通过一个LPF，即可获得表示无功大小的直流量。可见这种检测方法计算量少，容易实现，检测效率较高。

# 3.2直接电流控制

基于3.1节的单相无功电流检测方法，本文提出一种适用于新型STATCOM的直接电流控制方案，原理如图5所示。直接电流控制，就是采用跟踪型PWM控制技术对网侧无功电流的瞬时值进行反馈控制。其中跟踪型PWM技术又分为三角波比较方式和滞环比较方式，本文采用三角波比较方式来获得PWM控制信号。

![](images/83ef4daf061f61b7409725fb72dd8c9aa042f57e20d2d4dd2ec4762e147c7ea9.jpg)  
Fig.4Comparison of compensation capacity   
图5直接电流控制原理图  
Fig.5Direct current control schematics

图5的控制原理为：首先，对网侧电压电流进行采样，采样电压 $u _ { \mathrm { s } }$ 经过一个锁相环PLL 得到和电压同相的单位余弦信号cos $\omega t$ ，采样电流 $i _ { \mathrm { s } }$ 和余弦信号cos@t经过一个乘法器相乘，将交流无功成分转变成直流分量，低通滤波器LPF将无功电流直流分量 $i _ { \mathrm { q } } ^ { * }$ 分离出来，和参考值0进行比较，误差信号${ \Delta } i _ { \mathrm { q } } ^ { \ast }$ 经过PI调节得到占空比 $D$ ，与载波比较得到交流变换器开关管的PWM触发信号，最终实现网侧无功电流的动态补偿。在该控制方法中PI调节器可以实现无稳态误差的电流跟探控制。

# 3.3基于PLL的余弦波发生器

图5中提出的直接电流控制方式用到和网侧电压同频同相位的余弦信号，该余弦信号直接影响到控制系统的精度和速度。下面给出基于锁相环(PLL）的与电网电压同步余弦信号发生器的设计原理，如图6所示。

![](images/f1250ff68ff0cbdbbe100f93b01f0e97d54ff7a3ace24898badcfc6dd92d9b9d.jpg)  
Fig.6Principle of synchronization cosine signal generatorbased onthe PLL

图6基于PLL与电网电压同步余弦信号发生器原理

图6的基本原理是采样后的网侧电压 $u _ { \mathrm { s } }$ 经过零比较器后得到的方波作为锁相环的一个输入，鉴相环、低通滤波器和函数信号发生器构成一个锁相环电路 (PLL)，函数信号发生器发生两个同步的正弦和方波信号，其频率由控制电压控制，方波信号作为反馈信号接入鉴相环的另外一个输入，和 $u _ { \mathrm { s } }$ 的方波进行比较，产生的误差信号经LPF得到控制信号，迅速调整信号发生器发生的正弦信号的频率和相位，使其最终和 $u _ { \mathrm { s } }$ 同步。得到的正弦信号再经移相电路移相 $9 0 ^ { \circ }$ ，即得到所需的余弦信号。

# 4 仿真分析

为了验证以上理论分析，验证新型STATCOM工作原理、直接电流控制策略的正确性以及系统动态特性，本文采用仿真软件对系统进行了仿真实验。

系统仿真参数：电网侧电压幅值为 $2 2 0 \sqrt { 2 } \mathrm { ~ V ~ }$ 频率为 $5 0 \mathrm { { H z } }$ ，开关频率为 $2 0 \mathrm { { k H z } }$ ，网侧滤波电感$L _ { \mathrm { i } } = 6 \mathrm { m H }$ ，滤波电容 $C _ { \mathrm { i } } = 4 \mu \mathrm { F }$ ，无功补偿电容器 $C =$ $1 1 0 \mu \mathrm { F }$ ，理想情况下最大补偿容量约为1.1kvar。

图7为不同占空比时的系统补偿电流大小，为了方便观察，图中电流波形为检测值乘以20之后的波形。如图7所示，注入电流 $i _ { \mathrm { c } }$ 超前电网电压 $u _ { \mathrm { s } }$ 大约 $9 0 ^ { \circ }$ ，其幅值大小跟随占空比 $D$ 变化。

负载为感性负载 $R = 3 0 \Omega$ 、 $L = 8 0 \mathrm { m H }$ 时的闭环仿真波形如图8所示。图8a显示STATCOM投入系统之前，网侧电压 $u _ { \mathrm { s } }$ 和网侧电流 $i _ { \mathrm { s } }$ 存在相位差，即存在无功功率；图8b显示补偿电流 $i _ { \mathrm { c } }$ 超前网侧电压（/V0OI）I（/AOOI） WAAAt( $1 0 \mathrm { m s } /$ 格)

（/VOOI）I（/A00I） WMMA t( $1 0 \mathrm { m s / }$ 格) (b) $D = 0 . 4$ 电网电压 $u _ { \mathrm { s } }$ 和注入电流 $i _ { \mathrm { c } }$ （/V0OI）I（/A00I） 20ic t (10ms/格) (c) $D = 0 . 5$ 电网电压 $u _ { \mathrm { s } }$ 和注入电流 $i _ { \mathrm { c } }$

![](images/d605c29e13bedf3d59fdab4da14b3b1e833a859bb5658b24901059cee73a190b.jpg)  
图7不同占空比无功补偿器的补偿电流  
Fig.7Compensation currentat different duty cycles

(a) $D = 0 . 2$ 电网电压 $u _ { \mathrm { s } }$ 和注入电流 $i _ { \mathrm { c } }$ (b）网侧电压 $u _ { \mathrm { s } }$ 和补偿电流 $i _ { \mathrm { c } }$

![](images/2496b05b71e38e57d9a3d44f363be07fb25992c9a6c5d3294ecbc622bdfb572e.jpg)  
Fig.8 Simulation waveforms

图8仿真波形

$9 0 ^ { \circ }$ ，是一个容性电流；图8c表明补偿后网侧电压$u _ { \mathrm { s } }$ 和网侧电流 $i _ { \mathrm { s } }$ 相位相同，无功功率被STATCOM补偿；图8d为PI调节器的调节过程，反映了系统的动态调节过程以及稳态性能。其输入信号为网侧无功误差信号，经过一段时间的调节，最终稳定值为0，表示无功功率最终被补偿完全；PI调节器输出信号作为控制信号发生器的控制信号，表示了占空比的大小，最终稳定在一个定值。表明系统动态调节效果好，调节速度较快，没有稳态误差。

# 5 结论

(1）本文理论分析了基于推挽正激高频隔离交流变换器的新型STATCOM补偿特性。该方案的优点，是实现了电网侧和补偿电容侧的电气隔离，提高了补偿装置的可靠性；将其与基于交流斩波器的STATCOM的做比较，相同条件下新型STATCOM可以提供更大的补偿容量。

(2）提出了一种基于单相无功电流检测方法的直接电流控制方案，相较于基于正交分解模块和dq坐标变换的控制方式，该方案计算简单，容易实现,检测效率较高。

(3）通过仿真实验，验证了以上理论分析，证实了新型STATCOM方案和提出的直接电流控制的可行性，该方案可以对网侧实现实时动态无功补偿。（4）该方案不需要直流储能单元，降低了无功补偿装置成本，同时系统结构简单，控制容易实现，具有较高的可靠性，工业应用前景很好。

# 参考文献

[1] 王兆安．谐波抑制和无功功率补偿[M]．机械工业出版社，1998.  
[2] 刘娇娇．基于多电平交流变换器的静止无功补偿器的研究[D]．南京：南京理工大学，2013.  
[3] Divan D,Sastry J. Inverter-less STATCOMs[C].IEEE Power Electronics Specialists Conference,2008:1372-1377.  
[4] 马立新，马天顺．基于改进 Buck-Boost 斩波电路的无功补偿器设计[J]．机电工程，2014，31(9)：1191-1195.Ma Lixin, Ma Tianshun. Design for reactive powercompensator based on improved Buck-Boost AC/AC chopper[J]. Journal of Mechanical & ElectricalEngineering,2014,31(9): 1191-1195.  
[5] Liu J, Li L. Application of AC converter inSTATCOM[C]. Power Electronics and MotionControl Conference.2012: 2819-2822.  
[6] Divan D, Sastry J. Inverter-less active flters-a newconcept in harmonic and VAR compensation[C].Power Electronics Specialists Conference, 2007:2926-2932.  
[7] 吴必瑞，裴素萍．基于DSP的能量双向流动交直流电源变换器[J]．电气应用，2016，35(12)：54-57.  
[8] 武伟，谢少军，汤雨，等．基于Buck交－交斩波器的无功补偿器拓扑与控制方法设计[J]．电力系统自动化，2013，37(5)：124-129.Wu Wei, Xie Shaojun, Tang Yu. Topology andcontrol strategy design for buck AC-AC chopperbased var compensators[J].Automation of ElectricPower Systems,2013,37(5): 124-129.  
[9] 蒋斌，颜钢锋，赵光宙．一种单相谐波电流检测法的研究[J]．电工技术学报，2000，15(6)：65-69.Jinag Bin, Yan Gangfeng, Zhao Guangzhou. Studyon a deteeting method for harmonic currents insinlge-phase circuit [J]. Transactions of ChinaElectrotechnical Society,2000,15(6): 65-69.