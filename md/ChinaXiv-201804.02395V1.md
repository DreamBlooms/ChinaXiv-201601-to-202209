# 含积分环节过程对象模型的频域辨识方法

张迁1，王亚刚'，王凯1,2

(1.上海理工大学光电信息与计算机工程学院，上海 200093;2.上海出版印刷高等专科学校 印刷设备工程系，上海200093)

摘要：由于考虑系统的安全性和经济性无法进行开环实验，而目前最常用的闭环继电反馈辨识方法需要进行数次的继电反馈实验，并且该方法只能辨识固定结构的低阶模型，无法满足实际工业的需要。针对这一情况，提出了一种新的含积分环节过程对象的频域模型辨识方法，其能快速找到对象模型的主要频率段，分析频率段内的频率特性，从而准确的辨识出含积分环节对象的模型。仿真实验的结果表明该辨识方法能够高效且准确的辨识出含积分加环节的对象。

关键词：模型辨识；含积分环节；频率响应 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.02.0089

# Modeling identification for process with integral unit in frequency domain

Zhang Qianl, Wang Yagangl, Wang Kai1, 2 (1.SchoolofOptical-Electrical&ComputerEnginering,UniversityofShanghaiforScience&TechnologyShanghai0093, China;2.Dept.ofPrintingEquipmentEngineering,ShanghaiPublishing&Printing Colege,Shanghai20o093,China)

Abstract:The model with integralunit isone processobject inactual industry especially inchemicalengineering andthermal power plant.The open loop experiment could not be done because of systems’security and economy.Also the close-loop identification method which is mostlycommonlyusedto identify theobjectisbyusingrelayfedback,duetothis method needs severalrelayfedbacktestsandonlyforfixed structureloworder models,soitcouldn'tmeet theactualindustrialrequirements. According to this circumstance,anewtechniqueofmodeling identificationforprocess with integralunit modelhasbnraised. Itcanfind amain frequencybandof theobject quicklyand analyze frequencyresponse.Then the model with integralunitcan be identified accurately.The results of simulation show that this method could acquire a great identification effect.

Key words: Modeling identification; Integral unit; Frequency response

# 0 引言

在实际工业生产应用中，尤其是在化工工业以及火力发电机组等领域，比如水塔水位控制、气体存储中[有时会出现含积分环节的过程对象。经典的例子就是锅炉汽包[2]，锅炉的膨胀会导致鼓级与锅炉给水量之间的传递函数发生改变，产生一个含积分环节的对象模型。这种对象不同于一般单调、稳定的通用工业模型，现今学界有很多针对这种过程对象的开环频域辨识方法，如作图法[3]，通过给出系统开环阶跃响应曲线的拐点和峰值点，即作出 $y = 0 . 2 8 ^ { * } y ( \infty )$ 处曲线的切线进行近似计算;或者累加法[3]，通过将系统离散化后，累加输出值进行计算。但是在实际工业过程对象的

模型辨识中，考虑到系统的安全性和经济性，无法进行开环实验。而已有的对含有积分环节过程对象的模型闭环辨识一般采用继电反馈法[4,5]，该方法通过在闭环系统回路中反复切换PID 控制器进行继电反馈实验以采集多个频率响应点进行计算。但是考虑到工业生产中的经济性、安全性、复杂性等[，往往无法在闭环系统中随意切换PID控制器进行数次继电反馈实验，并且该方法只能辨识固定结构的对象模型[7,8]，所以往往无法使用继电反馈法进行含积分环节对象的辨识。而文献[10,11]所提出的根据实际运行的系统采集到的数据的频域辨识方法，也只是针对一般的过程对象，对于这类含积分环节的特殊对象则不太适用。

因此为了获得含积分环节对象的准确模型，本文提出了一种新的频域辨识方法，只需要采集闭环系统的实际运行数据进行分析，即可找出被辨识对象的主要频率段，然后在该频率段内对该过程对象进行频率特性分析，就可以迅速找出对象的多个主要频率点，从而进行含积分环节对象过程的模型辨识。

# 1 过程对象的模型辨识

# 1.1 频率响应特性

通常在实际工业生产中，信号从一个稳定状态变化到另一个稳定状态的情况经常遇到，两个稳定状态之间的信号包含了极为重要的频域特性。因为一般的系统响应信号 $f ( t )$ 可以分解成瞬态部分 $\Delta f ( t )$ 和稳态部分 $f _ { s } ( t )$ ，即

$$
\Delta f ( t ) = f ( t ) - f _ { s } ( t )
$$

由于两个稳定状态之间的变化的信号通常不满足绝对可积的条件，所以考虑对等式两边进行Laplace变换，得

$$
\begin{array} { l } { { \displaystyle { \cal F } ( s ) = \Delta F ( s ) + { \cal F } _ { s } ( s ) } } \\ { { \displaystyle ~ = \int _ { 0 } ^ { \infty } \Delta f ( t ) e ^ { - s t } d t + \frac { f ( \infty ) } { s } } } \end{array}
$$

假设在 $t = T _ { f }$ 时刻， $f ( t )$ 达到稳态值，也就是说在 $T _ { f }$ 之后时刻的 $\Delta f ( t )$ 基本都等于零，则对象的输入输出信号的拉式变换表达式为

$$
U ( s ) \approx \int _ { 0 } ^ { T _ { u } } \Delta u ( t ) e ^ { - s t } d t + \frac { u ( \infty ) } { s }
$$

$$
C ( s ) \approx \int _ { 0 } ^ { T _ { s } } C _ { t } \left( t \right) e ^ { - s t } d t + \frac { C ( \infty ) } { s }
$$

![](images/adc449f67b85b0c19cba3e30d983aca36aff0f2a88c552022ad81b1971e9888a.jpg)  
图1含积分环节对象模型的输入输出信号

如图1所示，在闭环阶跃响应中，对象输入为阶跃信号，$\Delta u ( t )$ 等于零，而输出结果包含动态环节和稳态环节这两部分，如果使得 $s = j \omega$ ，则对象的传递函数可表示为：

$$
G ( j \omega ) = \frac { Y ( j \omega ) } { U ( j \omega ) } \approx \frac { y ( \infty ) + j \omega \int _ { 0 } ^ { T _ { y } } \Delta y ( t ) e ^ { - j \omega t } d t } { u ( \infty ) }
$$

可以将式(5)的积分部分分成 $N$ 个长度为 $\Delta t _ { k }$ 的子区间，展开成积分累加的形式，即

$$
\int _ { 0 } ^ { T _ { y } } \Delta y ( t ) e ^ { - j \omega t } d t = \sum _ { k = 1 } ^ { N _ { y } } \Bigl ( \int _ { t _ { k - 1 } } ^ { t _ { k } } \Delta y ( t ) e ^ { - j \omega t } d t \Bigr )
$$

其中 $N _ { y }$ 为数据的采样个数。

在式(6)的基础上，将 $s = j \omega$ 代入式(5)，进一步推导整理,得到对象各个重要频率点的频率响应特性：

$$
G ( j \omega _ { i } ) \approx
$$

这样对于任意给定频率 $\omega$ ，都可根据式(7)求出该频率点时对象的幅值和相位。

# 1.2过程对象的主要频率点

含积分环节模型的Nyquist图如图2所示，假设过程对象的模型趋于收敛，由于一般系统通常工作在中、低频段[9]，因此我们只需要选取曲线的中、低频段作为主要频率段，即主要频率段位于第ⅡI、IⅢ象限，也就是位于虚轴左半平面的频率点[5,]假设频率为零作为频率段的起始频率，临界频率作为终点频率，用迭代公式计算

$$
\omega _ { n + 1 } = \omega _ { n } - ( \pi + \varphi _ { n } ) \frac { \omega _ { n } - \omega _ { n - 1 } } { \varphi _ { n } - \varphi _ { n - 1 } }
$$

$$
\varphi = \arg \big [ G ( j \omega ) \big ]
$$

其中： $\omega _ { \scriptscriptstyle 0 }$ 和 $\varphi _ { \mathrm { 0 } }$ 均为零， $\omega _ { \mathrm { { l } } }$ 取一个非常小的数，例如 $1 0 ^ { - 3 }$ 等， $\varphi _ { 1 }$ 通过式(9)进行计算得到，其中的 $G ( j \omega _ { n } )$ 由式(7)可得。经过数次的反复迭代以后，求出对象的临界频率 $\omega _ { c }$ (对应相角为 $- \pi$ )。此时， $( 0 , \omega _ { c } )$ 就是想要求得的主要频率段。

![](images/53e4b100ce1b4ae0b0dfbfacd3bcdac09536cf6cba5fb482589aeb641ff22d3f.jpg)  
图2积分加纯滞后模型的Nyquist 图

# 1.3传递函数模型

在根据2.2节方法所求的频率段 $( \omega _ { n 1 } , \omega _ { n 2 } )$ 内取 $\mathbf { M }$ 个频率点来求解最终的过程对象的传递函数模型。在实际工业生产中，工业对象的系统模型都是高阶和复杂的，以至于即使我们获得其精确地模型也很难设计出合适的控制器，因此我们采用下式(10)二阶带积分模型对实际系统过程进行逼近。

$$
G ^ { ' } ( s ) = \frac { b } { s ( s + a ) } e ^ { - L s }
$$

式(10)的参数ab以及L可以通过将 $\omega _ { n }$ $\upsilon _ { n } \left( \mathrm { n } { = } 1 , 2 , 3 { \ldots } , \mathrm { { M } } \right)$ 代入$G ^ { ' } ( j \omega )$ 与实际频率响应点 $G ( j \omega )$ 进行拟合来解得，即

$$
G ( j \omega _ { n } ) = \frac { b } { j \omega _ { n } ( ( j \omega _ { n } ) + a ) } e ^ { - L j \omega _ { n } }
$$

$$
\mathbf { , } n = 1 , 2 , . . . , M
$$

其中，在拟合时需要用到 $G ( j \omega )$ 的幅值条件和相位条件，即

$$
\begin{array} { l } { { \omega _ { n } ^ { ~ 4 } \big | G ( j \omega ) \big | ^ { 2 } + } } \\ { { \omega _ { n } ^ { ~ 2 } \big | G ( j \omega ) \big | ^ { 2 } a ^ { 2 } - b ^ { 2 } = 0 } } \end{array}
$$

$$
\begin{array} { l } { \displaystyle - \arg [ G \big ( j \omega _ { n } \big ) ] - \frac { \pi } { 2 } - } \\ { \displaystyle } \\ { \tan ^ { - 1 } ( \frac { \omega _ { n } } { a } ) = \omega _ { n } L } \end{array}
$$

其中 $n = 1 , 2 , 3 , . . . , M$ ，式(12)可以用式(14)的矩阵表示。

$$
\Phi \theta = \Gamma
$$

$$
\Phi = \left[ \begin{array} { c c c } { { \omega _ { 1 } ^ { ~ 4 } \big | G ( j \omega _ { 1 } ) \big | ^ { 2 } } } & { { \omega _ { 1 } ^ { ~ 2 } \big | G ( j \omega _ { 1 } ) \big | ^ { 2 } } } \\ { { } } & { { } } & { { } } \\ { { \omega _ { 2 } ^ { ~ 4 } \big | G ( j \omega _ { 2 } ) \big | ^ { 2 } } } & { { \omega _ { 2 } ^ { ~ 2 } \big | G ( j \omega _ { 2 } ) \big | ^ { 2 } } } \\ { { } } & { { } } & { { \vdots } } \\ { { } } & { { } } & { { } } \\ { { \omega _ { n } ^ { ~ 4 } \big | G ( j \omega _ { n } ) \big | ^ { 2 } } } & { { \omega _ { n } ^ { ~ 2 } \big | G ( j \omega _ { n } ) \big | ^ { 2 } } } \end{array} \right]
$$

$$
\begin{array}{c} \Gamma = \left[ \begin{array} { l } { 1 } \\ { 1 } \\ { \vdots } \\ { 1 } \end{array} \right] , \theta = \left[ \theta _ { 1 } ^ { \phantom { \dagger } }  \\ { \theta _ { 2 } ^ { \phantom { \dagger } } } \end{array} \right] = \left[ \begin{array} { l } { 1 } \\ { \mathbf { \bar { b } } ^ { 2 } } \\ { \mathbf { \bar { b } } ^ { 2 } } \\ { \mathbf { \bar { b } } ^ { 2 } } \end{array} \right]
$$

式(14)中的 $\theta$ 可以通过最小二乘算法求出

$$
\theta = ( \Phi ^ { T } \Phi ) ^ { - 1 } \Phi ^ { T } \Gamma
$$

由式(16)可以计算出传递函数模型的各个参数

$$
\left[ \begin{array} { l } { b } \\ { a } \end{array} \right] = \left[ \begin{array} { l } { 1 } \\ { \pm \sqrt { \theta _ { 1 } } } \\ { \pm \sqrt { \frac { \theta _ { 2 } } { \theta _ { 1 } } } } \end{array} \right]
$$

如果系统的输出随着输入信号的增加而增加，则为正对象，$^ { a , b }$ 取正；反之，则取负。

在模型参数 $^ { } | a , b _ { }$ 确定以后,纯滞后 $L$ 则可以通过 $G ( j \omega )$ 的相位条件和最小二乘法求出。

$$
\left[ \begin{array} { c } { \omega _ { 1 } } \\ { \omega _ { 2 } } \\ { \vdots } \\ { \omega _ { n } } \end{array} \right] L = \left[ \begin{array} { c } { - \arg \left[ G ( j \omega _ { 1 } ) \right] - \frac { \pi } { 2 } - \tan ^ { - 1 } \left( \frac { \omega _ { 1 } } { a } \right) } \\ { \hphantom { - } } \\ { - \arg \left[ G ( j \omega _ { 2 } ) \right] - \frac { \pi } { 2 } - \tan ^ { - 1 } \left( \frac { \omega _ { 2 } } { a } \right) } \\ { \vdots } \\ { - \arg \left[ G ( j \omega _ { n } ) \right] - \frac { \pi } { 2 } - \tan ^ { - 1 } \left( \frac { \omega _ { n } } { a } \right) } \end{array} \right]
$$

# 2 仿真实验

为了检验本方法的准确性和可靠性，本文在仿真实验中引入信噪比率(SNR)[12,13,14,15]

$$
S N R = \frac { m e a n ( a b s ( n o i s e ) ) } { m e a n ( a b s ( s i g n a l ) ) }
$$

由于传统的继电反馈法无法辨识高阶对象模型，而实际工业中需要进行高阶模型的辨识，所以采用高阶模型作为对象模型。

设定仿真对象一的模型[16]为

$$
G ( s ) = { \frac { 1 } { s ( s + 1 ) ^ { 8 } } }
$$

其开环阶跃响应曲线如图1所示。

![](images/54041c94ea5a50c0863f7b06793c250a3221cbc5ff4c67d4ad02a0befd3edb97.jpg)  
图3对象1在 $S N R { = } 2 0 \%$ 环境下辨识模型的Nyquist 图

图3为在 $S N R { = } 2 0 \%$ 环境下的实际过程对象一和采用本文提出的方法所得到模型的Nyquist曲线。图中红色实线为实际对象的Nyquist图，蓝色实线为本文方法辨识出的模型的Nyquist图，黑色电话线为一般二阶辨识方法辨识出的模型的Nyquist图， $\times$ 为对象的频率响应点。

最终辨识出的主要频率范围为(0,0.1852)，在此区间选取十个频率点，最终辨识出的对象模型为

$$
G ( s ) = { \frac { 0 . 3 3 4 1 } { s ( s + 0 . 3 3 3 6 ) } } e ^ { - 5 . 1 1 2 6 s }
$$

设定对象二的模型为积分加纯滞后模型

$$
G ( s ) = { \frac { 1 } { s ( s ^ { 2 } + 2 s + 1 ) ( s + 3 ) } } e ^ { - s }
$$

![](images/bc3540eee799a7d0ff117df0e0390d0f973788c2e03e6c72e816f26a9df0a223.jpg)  
图4对象2在 $S N R = 2 0 \%$ 环境下辨识模型的Nyquist图

图4为在 $S N R = 2 0 \%$ 环境下的实际过程对象1和采用本文提出的方法所得到模型的Nyquist 曲线。图中红色实线为实际对象的Nyquist图，蓝色实线为本文方法辨识出的模型的Nyquist图，黑色电话线为一般二阶辨识方法辨识出的模型的Nyquist 图， $\times$ 为对象的频率响应点。

最终辨识出的主要频率范围为(0,0.5243)，在此区间选取十个频率点，最终辨识出的对象模型为

$$
G ( s ) = { \frac { 0 . 6 4 0 1 } { s ( s + 0 . 2 1 4 3 ) } } e ^ { - 1 . 8 3 4 4 s }
$$

由上述两种过程对象的辨识结果可以看出，本文提出的频域方法辨识出的模型精度很高，与实际对象模型的拟合程度也很好。采用本文方法能够根据采集到的系统运行数据，提炼出所需的重要频率段，可以很好的将噪声的干扰消除。由此可见，即使在噪声环境下，本文的辨识方法也具有很好的本方法很好的鲁棒性和实用性，能够精确的辨识出含积分环节的过程对象的模型，且本文方法适用于广泛的含积分环节的过程对象。因此本文的辨识方法可用于实际的工业生产中。

# 3 结束语

本文提出了一种含积分过程对象的频域辨识方法，不需要任何的先验条件，只需要根据系统正常运行产生的数据获得对象的主要频率段，求取重要频域点，最终通过幅频特性来确定最终的模型，仿真实验表明即使在噪声干扰下，该辨识方法对含积分环节的模型仍具有良好的辨识效果，弥补了传统继电反馈法只能辨识固定的低阶模型，且需要大量实验的不足。并且由于本文方法具有很好的鲁棒性和准确性，适用于广泛的含积分环节过程对象，所以本文方法可以用于实际的工业对象辨识中。

# 参考文献：

[1]王维贺，王平．二阶加纯滞后对象模型辨识方法及其应用[J].化工自 动化及仪表,2010,37(9):21-24.(WangWeihe,Wang Ping.Identification method and application of second-order plus time delay model[J].Control and Instruments in Chemical Industry,2010,37(9): 21-24.)   
[2]Luyben W L.Identification and tuning of integrating processes with deadtime and inverse response [J]. Industrial & Engineering Chemistry Research,2003,42(13):3030-3035.   
[3]房方．单元机组协调控制系统的先进控制策略研究[D].保定：华北电 力大学,2Oo5.(Fang Fang.Research on the advanced control strategy of unit coordinated control system [D]. Baoding:North China Electric Power University,2005.)   
[4]Austom K J,Hagglund T.Automatic tuning of simple regulators with specifications on phase and amplitude margins [J].Automatic,1984,20: 645.   
[5]Hagglund T.Process control in practice [M].[S.L] $\because$ Studentlitteratur and Chartwell-Bratt,1991.   
[6] 李少远，蔡文剑．工业过程辨识与控制[M].北京：化学工业出版社, 2005.(Li Shaoyuan,Cai Wenjian.Identification and Control of Industrial Process [M]. Beijing: Chemical Industry Pres,2005.)   
[7] 刘海，王储栋，严怀诚，等．基于饱和继电反馈的模型参数辨识及 PID 控制器参数自整定[J].计算机与应用化学，2012,29(9):1007-1010. (Liu Hai,Wang Chudong，Yan Huaicheng，et al. Model parameter identification and parameter self-tunning of PID controller based on saturation relay feedback [J]. Computers and Applied Chemistry,2012,29 (9): 1007-1010.)   
[8] 马明达，朱新坚．基于偏置继电反馈的一种新的频域辨识方法[J].计 算机仿真,2006,23(3): 84-87.(Ma Mingda,Zhu Xinjian.ANew Frequency Domain Identification A Lgorithm Based On Biased Relay Feedback [J]. Computer Simulation,2006,23 (3): 84-87.)   
[9]胡寿松．自动控制原理[M].北京：科学出版社,2013.(Hu Shousong. Automatic Control Theory [M].Beijing: Science Press,2013.）   
[10]王亚刚，戴自祥，邵惠鹤．基于频域辨识的自整定 PID 控制器[J]．自 动化仪表,2000,21(8): 9-13.(Wang Yagang,Dai Zixiang,Shao Huihe.The Self-Tunning PID Controller Based on Frequency Domain Recognition [J]. Process Automation Instrumentation,2000,21(8): 9-13. )   
[11] Wang Yagang,Xu Xiaoming, Cai Wenjian. Online identification of process systems in the frequency domain [J].Intermational Journal of Computer Applications in Technology,2011,41(1): 11-16.   
[12]丁东杰，王亚刚．工业过程频域建模与控制器参数鉴定[J].控制工程, 2016,23(11）.(Ding Dongjie,Wang Yagang.Modeling in Frequency Domain and Controller Parameter Tuning for Industrial Processes [J]. Control Engineering ofChina,2016,23(1).)   
[13] Wu Yan,Yang Qinghai, Kwak S K. Energy eficiency maximization for energy harvesting milimeter wave systems at high SNR [J]. IEEE Wireless Communications Letters,2017,5(6): 689-701.   
[14] Yang Feiran,Enzner G,Yang Jun. Frequency-domain adaptive kalman filter with fast recovery of abrupt echo-path changes [J]. IEEE Signal Processing Letters,2017,12 (24): 1778-1782.   
[15] Sun Jinhua, Yu Zhongyang. Joint time-frequency domain and code-aided carrier synchronization algorithm at low SNR [C]// Proc of Information Technology and Artificial Intelligence Conference.2014.   
[16] Wang Yagang, Cai Wenjian. Identification for integrating processes in the frequency domain [C]//Proc of the 4th World Congress on Inteligent Control and Automation. 2002: 3344-3348.