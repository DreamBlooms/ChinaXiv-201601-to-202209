# 基于参数自适应的孤岛检测算法研究

![](images/7dadc6e07405aee723820ff2b72188ba0c1801f57b186f7a38693d44830a894e.jpg)

吕广强男1974年生，博士，副教授，主要研究方向为电能质量检测与治理，分布式电源并网控制等。

沙尧女 1990年生，硕士研究生，主要研究方向为微网协调控制。

吕广强沙尧（南京理工大学自动化学院南京 210094）

摘要：本文从孤岛检测盲区和电流谐波畸变率两种孤岛检测算法有效性评价指标出发，根据算法参数与检测盲区和电流谐波畸变率之间的关系，对主动频率偏移法（AFD）和Sandia频率偏移法（SFS）进行了算法改进，提出一种基于参数自适应的孤岛检测算法。使得在负载发生变化时，能够进行自动参数择优，提高孤岛检测成功率，并减小电流谐波畸变率，最后通过仿真验证了该改进算法的优越性。

关键词：孤岛检测盲区 电流谐波畸变率参数自适应中图分类号：TM615

# Research on the Islanding Detection Algorithm Based on Parameter Adaptive

Li GuangqiangSha Yao (Nanjing University of Science and Technology Nanjing 210094 China ）

Abstract: From the non-detection zone and the current harmonic distortion,which are two effectiveness indexes of islanding detection,according to the relationship between the parameters of islanding detection algorithm and the non-detection zone and harmonic distortion, a new algorithm based on parameter adaptive is proposed to improve the active frequency drift (AFD) and the Sandia frequency shift (SFS) algorithm. It can select more appropriate parameter, when the load changes.And it proved that in the improved algorithm,the success rate of islanding detection became higher, and the harmonic distortion became smaller by simulation.

Keywords: Non-detection zone of islanding detection, current harmonic distortion, parameter adaptive

# 1 引言

随着分布式发电的迅速发展，越来越多的分布式电源接入电网并投入使用[1，此外分布式电源还存在孤岛运行模式。孤岛效应可分为计划孤岛和非计划孤岛两类[2]。计划孤岛不仅减少了停电事故的影响，提高了供电可靠性，也充分发挥了分布式能源的效益。而非计划孤岛可能会对电力设备和电网工作人员造成严重的损害[3-4]，因此，无论从安全性还是可靠性的角度考虑，所有并网分布式发电系统都要求设有孤岛检测装置，以避免非计划孤岛的发生。目前孤岛检测方法一般分为两大类：被动式孤岛检测法和主动式孤岛检测法[5]。

过欠电压、过欠频率检测法和电压谐波检测法[是具有代表性的两种被动式检测法。前者是通过检测公共耦合点（PCC点）的电压幅值、频率是否超过阈值来判断孤岛的发生，简单实用，但是当逆变器与本地负载功率匹配时存在检测盲区，且阈值难以确定。后者是通过检测PCC点电压的总谐波畸变率来判断是否发生孤岛现象，优点是逆变器与本地负载功率匹配时不存在检测盲区，但是在电网正常运行时，实际系统中的非线性因素会导致误判断[8]。

主动式孤岛检测法应用较多的是功率偏移法和频率偏移法。功率偏移法通过周期性向输出电流中加入有功或者无功扰动信号并检测PCC点电压是否发生变化来判断孤岛的发生[9]，该方法稳定、准确，但是多逆变器并联时注入的谐波会发生相互干扰。频率偏移法通过控制逆变器输出电流的相位、频率的变化，使PCC点电压相位和频率跟随发生变化形成正反馈过程，最终PCC点电压的频率超出正常范围从而检测出孤岛的发生[0]。但是传统的频率偏移法引入了非线性畸变，使得逆变器输出电流的谐波畸变率很大，降低供电电能质量。

目前的孤岛检测采取的方案主要是主动式孤岛检测法，集中在实现盲区减小的同时提高电能质量。文献[12]提出的改进主动移频算法，虽然能够减小谐波含量但是注入的谐波成分比较复杂；文献[13]提出的负序电压正反馈检测法不适用于单相分布式电源；文献[14]提出的基于偶次谐波扰动的检测方法在时域判断孤岛时响应较慢。

本文针对上述问题，从孤岛检测盲区和电流谐波畸变率两种孤岛检测算法有效性评价指标出发，根据算法参数与检测盲区和电流谐波畸变率之间的关系，对主动频率偏移法和Sandia频率偏移法进行了算法的改进，提出一种基于参数自适应的孤岛检测算法，使得当负载发生变化时，能够自动进行参数择优，提高孤岛检测成功率，并减小电流谐波畸变率。

# 2 主动移频类检测法

# 2.1AFD算法基本原理

AFD法的基本原理是：基于并网标准前提下，在逆变器输出电流的过零点周期性地引入频率偏移量f，使并网电流的给定频率发生偏移最终超过设定的频率阈值范围，检测出发生孤岛效应[15]。

以频率向上偏移为例，检测原理如图1所示，此时逆变器输出电流的给定信号是一个周期为 $T _ { \mathrm { T p v } }$ 的畸变斩波波形，电网电压的周期为 $T _ { \mathrm { V u t i l } }$ 。由图1可见，电流波形存在一个大小为 $t _ { \mathrm { z } }$ 的死区于正、负半周之间。定义电流波形的截断系数为

$$
c f = \frac { t _ { \mathrm { z } } } { T _ { \mathrm { V u t i l } } / 2 }
$$

![](images/e5ce2ad38c39558aeb4cd3ee3bf29786d0cf858acb772b1df1155c7deee8034a.jpg)  
图1AFD 法的基本原理  
Fig.1The basic principle ofAFD method

并网运行时，由于主网对公共耦合点的电压产生钳制作用使电压的频率不会发生变化，孤岛效应发生后，耦合点电压摆脱主网的钳制，电压的频率随着被加入扰动信号的电流波形的变化而变化，每个周期都会比前一个周期略微增大。由于每个周期输出电压的波形都跟随畸变的斩波波形，因此电压的频率持续向上偏移，直到超出设定的保护阈值检测出孤岛状态。

AFD法的原理简单，操作方便，检测性能远高于被动检测法，因此在实际工程中被广泛采纳。其缺点是注入的扰动信号使电流波形发生畸变，这对逆变器输出的电能质量有一定的影响，这也是主动检测法固有的缺陷，且在特殊负载条件下存在检测盲区[16]

# 2.2 SFS算法基本原理

美国的Sandia实验室为了克服上述AFD法的缺陷提出了一种改进的频率偏移孤岛检测法Sandia频率偏移法，又称带有正反馈的主动频率偏移法（Active Frequency DriftwithPositive Feedback,AFDPF）。

并网运行时，逆变器的输出电流和输出端电压分别为

$$
\begin{array} { r l } & { i _ { \mathrm { i n v } } = I _ { \mathrm { i n v } } \sin \left( \omega t + \varphi _ { \mathrm { i n v } } \right) } \\ & { u _ { \mathrm { a } } = U _ { \mathrm { a m } } \sin \left( \omega t + \varphi _ { \mathrm { a } } \right) } \end{array}
$$

式中， $I _ { \mathrm { i n v } }$ 和 $U _ { \mathrm { a m } }$ 分别为电流和电压的幅值； $\varphi _ { \mathrm { i n v } }$ 和$\varphi _ { \mathrm { a } }$ 分别为电流和电压的初始相位。

定义 SFS 算法中的截断系数 $c f$ 为

$$
c f _ { k } = c f _ { k - 1 } + K \Delta f
$$

式中， $c f _ { k }$ 和 $c f _ { k - 1 }$ 分别为第 $k$ 个周期和第 $k { - } 1$ 个周期的截断系数； $K$ 为反馈系数； $\Delta f { = } f { - } f _ { \mathrm { g } }$ 是逆变器端输出电压的频率 $f$ 和电网电压的额定频率 $f _ { \mathrm { g } }$ 之间的频率偏差。

由上述截断系数的定义可以看出， $\Delta f$ 越大， $c f$ 越大，也就是说逆变器输出端电压的频率偏离电网 电压额定频率越多，频率偏移的速度越快，Sandia 频率偏移法利用这种正反馈效应使逆变器输出端电 压的频率持续偏移超出设定的阈值，从而检测出孤 岛状态。

# 3 算法参数的分析

# 3.1参数与检测盲区的关系

理论分析及相关实验表明，几乎任何一种孤岛检测法都有检测失败的可能性，即一定存在检测盲区。本文采用 $Q _ { \mathrm { f 0 } } \times C _ { \mathrm { n o r m } }$ 坐标系来对算法的检测盲区进行描述，该坐标系能够在一个二维平面上体现出基于频率的孤岛检测法的盲区特性，且坐标之间相互独立不会发生耦合现象[17]。

经过理论推导得出AFD法和SFS法的盲区边界的公式分别为

$$
\frac { \tan \left( \displaystyle { \frac { \pi } { 2 } } c f \right) } { Q _ { \mathrm { f 0 } } } - \frac { 0 . 5 } { f _ { 0 } } < \Delta C _ { \mathrm { n o r m } } < \frac { \tan \left( \displaystyle { \frac { \pi } { 2 } } c f \right) } { Q _ { \mathrm { f 0 } } } + \frac { 0 . 7 } { f _ { 0 } }
$$

$$
\frac { \tan \left( \displaystyle \frac { \pi } { 2 } c f _ { 0 } + \displaystyle \frac { \pi } { 2 } k \times 0 . 5 \right) } { Q _ { \mathrm { f 0 } } } - \frac { 0 . 5 } { f _ { 0 } } + 1 < \Delta C _ { \mathrm { n o m } } <
$$

$$
\frac { \tan \left( \displaystyle \frac { \pi } { 2 } c f _ { 0 } - \displaystyle \frac { \pi } { 2 } k \times 0 . 7 \right) } { Q _ { \mathrm { f 0 } } } + \frac { 0 . 7 } { f _ { 0 } } + 1
$$

根据式(5)，通过Matlab编程得到AFD检测法对应的孤岛检测盲区边界如图2所示。

![](images/fe8b415dcd7b221f9454760e89177d26daa574c20926c38e848cfd41638d1961.jpg)  
图2AFD法的盲区边界

由图2可以看出，对品质因数不同的负载而言，AFD检测法的检测盲区一定存在，且截断系数cf的变化会导致检测盲区的位置发生变化，而对盲区的大小影响不大。

根据式 (6)，通过Matlab编程得到SFS检测法对应的孤岛检测盲区边界如图3所示。

![](images/5baff0a3d19d6a20b2854e7b5bde050f10335cf57fc1c1d33b1f0308e5b459d4.jpg)  
Fig.2Boundary of non-detection zone of AFD method   
图3 SFS法的盲区边界  
Fig.3Boundary of non-detection zone of SFS method

对比图3a和图3b可以看出，初始截断系数 $c f _ { 0 }$ 的取值越大，盲区的位置越往上偏移。分别观察两图中的3条曲线可知， $K$ 的值越大，检测盲区越小，因此SFS算法可以通过增大比例因子 $K$ 来减小检测盲区，从而达到给定品质因数值条件下的检测无盲区。

# 3.2参数与电流谐波畸变率的关系

# 3.2.1AFD算法参数与电流谐波畸变率的关系

文献[18]分析了电流谐波畸变率和截断系数cf之间的关系，截断系数越大，电流谐波畸变率越大。当系统引入AFD检测算法，不同截断系数条件下的电流谐波畸变率见下表。

# 表截断系数对电流谐波畸变率的影响

Tab.Effect of truncation coefficient on current harmonic distortion   

<html><body><table><tr><td>截断系数cf</td><td>0.02</td><td>0.03</td><td>0.04</td><td>0.05</td></tr><tr><td>总谐波畸变率(%)</td><td>3.56</td><td>5.30</td><td>5.92</td><td>7.08</td></tr></table></body></html>

分析可知，主动频率偏移法由于扰动信号的引入对电能质量造成影响，总谐波畸变率明显增大，证明了AFD检测法会对系统电能的质量产生不利影响，并且依据截断系数的不同，对电能质量的影响程度也有所差别。从上表中数据可知，当截断系数cf增大时，电流谐波畸变率也随之增大。因此能够得出在保证孤岛检测成功的前提下，截断系数cf的取值尽可能小可以减小主动频率偏移检测法对供电电能质量的影响。

# 3.2.2SFS算法参数与电流谐波畸变率的关系

相较于AFD检测法而言，SFS检测法的截断系数从固定值变成了带反馈系数的变化值。

(1）选取相同的初始截断系数。若初始截断系数均设为0，反馈系数从 $K = 0 . 0 6$ 变成 $K = 0 . 0 2$ 时，电流谐波畸变率从 $2 . 5 4 \%$ 变成 $2 . 1 7 \%$ ，谐波畸变率变化幅度很小，由此证明反馈系数 $K$ 会对电流的谐波畸变率产生影响，但是影响程度非常小，几乎可以忽略不计。而反馈系数 $K$ 的增大却能够使孤岛算法的检测盲区有明显的减小，从而也有力地证明了SFS 检测法的优越性。

(2）选取相同的反馈系数。当截断系数分别为$c f = 0 . 0 2 + 0 . 0 3 \Delta f$ ， $c f = 0 . 0 3 + 0 . 0 3 \Delta f$ $c f = 0 . 0 5 + 0 . 0 3 \Delta f$ 时，逆变器输出电流的谐波畸变率分别为 $1 . 1 0 \%$ F$4 . 0 6 \%$ 和 $1 0 . 2 1 \%$ ，该结果验证了截断系数越大，电流谐波畸变率越大的理论，并且当反馈系数 $K$ 一定时，初始截断系数 $c f _ { 0 }$ 越小，电流谐波畸变率就越小，所以通常情况下将初始截断系数 $c f _ { 0 }$ 设作零。

综上所述，反馈系数 $K$ 对谐波畸变率的影响较小，但是增大 $K$ 的值能够减小孤岛检测盲区，而截断系数中的 $c f _ { 0 }$ 对谐波畸变率的影响较大。因此，在设置算法参数时为了达到减小检测盲区并降低逆变器输出电流的谐波畸变率的目的，应该将初始截断系数 $c f _ { 0 }$ 的值设置得尽量小，而反馈系数 $K$ 的值则根据具体情况确定。

# 4算法改进与仿真验证

# 4.1基于参数自适应的算法改进

从上文对孤岛检测盲区的分析可知，虽然负载品质因数 $\boldsymbol { \mathcal { Q } } _ { \mathrm { f } }$ 的增大会增加孤岛检测难度，但选取不同的截断系数cf会使得检测盲区的位置不同，因此，可以通过负载的电阻、电容和电感值计算出 $Q _ { \mathrm { f 0 } }$ 和 $C _ { \mathrm { n o r m } }$ 的值，并将截断系数设置成检测盲区之外的参数，这种参数自适应的方法大大减小了主动频率偏移法孤岛检测失败的可能性。另外，Sandia频率偏移法中截断系数的选取原则类似，从上文的盲区分析中可知，反馈系数 $K$ 的大小对孤岛检测盲区的大小有一定的影响，反馈系数 $K$ 的取值越大，孤岛检测盲区越小。但是从电流谐波畸变率的角度而言，反馈系数 $K$ 的增大会导致电流谐波畸变率略有增大。参数自适应算法可以将这种矛盾进行折中，它的核心思想就是在负载改变的情况下，进行参数寻优，使孤岛检测方法更加灵活、有效。

# 4.2仿真验证

# 4.2.1改进的AFD法仿真验证

设置负载参数为 $Q _ { \mathrm { f 0 } } = 2 . 5$ ， $C _ { \mathrm { n o r m } } { = } 1 . 0 0$ 。

(1）当 $c f = 0 . 0 3$ 时，电流的频率没有超过设定的阈值 $5 0 . 5 \mathrm { H z }$ ，孤岛检测失败。结果如图4所示。

(2）采用自适应算法后，算法在经验区域内选择最适合的截断系数，使得孤岛检测成功。结果如图5所示。

![](images/5a0882d4e0ca24e08fb325ffc612bceedfe75ee7023353bd40900ef142de66b2.jpg)  
(a）电网电压频率

![](images/eb9c45b8068d0eed5cba47979b11a1ca1402097c1c3d0390053d7bebfb6d78de.jpg)  
图4未采用参数自适应算法的仿真结果 Fig.4The simulation results of algorithm without parameteradaptive

![](images/e582d026f68a87e397cf94729232063bdf9c7d30f6bc1fdc352d25fb44735b6f.jpg)  
图5采用参数自适应算法的仿真结果

利用参数自适应算法改变截断系数cf的值来改变检测盲区边界的位置，使得相应的负载远离检测盲区，这样使原本处于检测盲区之内的负载条件也能够成功地检测出孤岛，使孤岛检测的成功率得到提高。

# 4.2.2改进的SFS法仿真验证

在SFS检测法中，当截断系数cf为变量时，若  
$c f _ { 0 }$ 的取值较大，则引入的谐波也比较大，因此在两  
个 $c f _ { 0 }$ 都能检测成功时，应自动选取较小的 $c f _ { 0 }$ 减小  
引入的谐波电流，提高供电电能质量。本文采用在  
SFS 检测算法下，通过负载参数计算出 $Q _ { \mathrm { f 0 } }$ 和 $C _ { \mathrm { n o r m } }$   
的值，并利用查表法给出最佳的反馈系数 $K$ 的值，使得负载发生变化时，能够自适应调节反馈系数 $K$

成功检测出孤岛，并使电流的谐波畸变率最小。该算法相较于传统的Sandia频率偏移法的优势是检测盲区小，电流的谐波畸变率大大减小并且运行灵活性强。

负载参数为 $Q _ { \mathrm { f 0 } } = 2 . 5$ ， $C _ { \mathrm { n o r m } } = 1 . 0 0$ ，当 $c f = 0 . 0 6 +$ $0 . 0 6 \Delta f$ 和 $c f = 0 . 0 6 \Delta f$ 时，都能够检测出孤岛，但是$c f _ { 0 }$ 的取值会对电流谐波畸变率产生较大的影响，因此在保证孤岛检测成功的前提下，算法应该能够选择谐波畸变率较小的参数。

（1）未采用参数自适应算法的情况下，当参数为 $Q _ { \mathrm { f 0 } } = 2 . 5$ ， $C _ { \mathrm { n o r m } } { = } 1 . 0 0$ ， $c f { = } 0 . 0 6 + 0 . 0 6 \Delta f$ 时，孤岛检测成功，其电流谐波畸变率为 $12 . 4 3 \%$ 。仿真结果如图6所示。

![](images/a4a03555e76a2ef308c52886110f2dc55a27e838935ed7d80bde3086ce9717bd.jpg)  
Fig.5The simulation results of parameter adaptive algorithm

![](images/8eaf1595019b086091821442392304dd4395eb0f593aa2dfa28f9faaa95e1897.jpg)  
图6未采用参数自适应算法的仿真结果 Fig.6The simulation results of algorithm without parameter adaptive

(2）使用参数自适应算法，在相同的负载条件下，选择最优的参数。仿真波形如图7所示。

![](images/a429e82c82283fd1f4262d46ea89fa71568c19f90ddbfd3256658b6e941656c7.jpg)  
图7采用参数自适应算法的仿真结果   
Fig.7The simulation results of parameter adaptive algorithm

由以上分析可知，截断系数 $c f { = } 0 . 0 6 + 0 . 0 6 \Delta f$ 和$c f { = } 0 . 0 6 \Delta f$ 均可以成功检测出孤岛，从图中可以看出，当 $c f = 0 . 0 6 \Delta f$ 时，电流的谐波畸变率为 $2 . 5 4 \%$ 。对比可知，通过参数自适应的算法可以自动选择最优参数，在孤岛检测成功的前提下使得电流的总谐波畸变率更小。

# 5 结论

本文提出了一种基于参数自适应算法的孤岛改进算法，该算法能够根据参数与检测盲区和电流谐波畸变率之间的关系，在负载发生变化时，能够在经验区域内自适应选择最优的参数，提高孤岛检测成功率，降低电流谐波畸变率。但是该算法中还存在一些不足之处，在今后的研究中，可以进一步优化，使孤岛检测达到最佳效果。

# 参考文献

[1] 赵清林，郭小强，邬伟扬．单相逆变器并网控制 技术研究[J]．中国电机工程学报，2007，27(16)： 60-64. Zhao Qinglin,Guo Xiaoqing,Wu Weiyang.Research on control strategy for single-phase grid-connected inverter[J]. Proceedings of the CSEE,2007,27(16): 60-64.   
[2] 张有兵，穆淼婕，翁国庆．分布式发电系统的孤 岛检测方法研究[J]．电力系统保护与控制，2011, 39(1): 139-146. Zhang Youbing,Mu Miaojie,Weng Guoqing. Research on islanding detection of distributed power generation systems[J].Power System Protection and Control,2011,39(1): 139-146.   
[3] Zeineldin H H,Ei-saadany EF,Salama M M A. Islanding detection of inverter-based distributed generation[J]. IEE Proceeding of Generation, Transmission and Distribution, 2006,153(6): 644- 652.   
[4] 林明耀，顾娟，单竹杰，等．一种使用的组合式 光伏并网系统孤岛效应检测方法[J]．电力系统自 动化，2009，33(23)：85-89. Lin Mingyao, Gu Juan, Shan Zhujie, et al. A practical hybrid islanding detection method for grid-connected photovoltaic system[J]. Automation of Electric Power Systems, 2009,33(23): 85-89.   
[5] 刘方锐，康勇，张宇，等．带正反馈的主动移频孤 岛检测法的参数优化[J]．电工电能新技术，2008, 27(3): 22-25. Liu Fangrui, Kang Yong, Zhang Yu, et al. Parameter optimization for active frequency drift with positive feedback islanding detection strategy[J]. Advanced Technology of Electrical Engineering and Energy, 2008,27(3): 22-25.   
[6] 郭小强，赵清林，邬伟扬．光伏并网发电系统孤岛 检测[J]．电工技术学报，2007，22(4)：157-161. Guo Xiaoqiang, Zhao Qinglin, Wu Weiyang. Islanding detection method for photovoltaic grid -connected power system[J]. Transactions of China Electrotechnical Society, 2007, 22(4): 157-161.   
[7] De Mango F, Liserre M, Aquila A D, et al. Overview of anti-islanding algorithms for PV systems: Part I passive methods[C]. International Conference on Power Electronics and Motion Control, Portoroz, Slovenia: 1878-1883.   
[8] 张学广，王瑞，刘鑫龙，等．改进的主动频率 偏移孤岛检测算法[J]．电力系统自动化，2012, 36(14): 200-204. Zhang Xueguang, Wang Rui, Liu Xinlong, et al. Improved active frequency drift anti-islanding algorithm[J]. Automation of Electric Power Systems, 2012,36(14): 200-204.   
[9] 任碧莹，孙向东，钟彦儒，等．用于单相分布式 发电系统孤岛检测的新型电流扰动方法[J]．电工 技术学报，2009，24(7)：157-163. Ren Biying, Sun Xiangdong, ZhongYanru, et al. A novel current-disturbing method for islanding detection in single-phase distributed power generation systems[J]. Transaction of China Electrotechnical Society, 2009,24(7): 157-163.   
[10] 刘方锐，余蜜，张宇，等．主动移频法在光伏并 网逆变器并联运行下的孤岛检测机理研究[J]．中 国电机工程学报，2009，29(12)：47-51. Liu Fangrui, Yu Mi, Zhang Yu, et al. Islanding detection evaluation for active frequency drifting methods in multiple photovoltaic grid-connected converter[J].Proceedings of the CSEE,2009,29(12): 47-51.   
[11] 栗赛男，黄梅，张维戈．基于置信区间法的分 布式发电日出力曲线研究[J]．电气应用，2016, 35(7): 29-36.   
[12] AhmadY,Bin Wu,SamirK.Improved active frequency drift anti-islanding detection method for grid connected photovoltaic system[J]. IEEE Transactions on Power Electronics,2012,27(5): 2367-2375.   
[13] 郭小强，邬伟扬．微电网非破坏性无盲区孤岛检测 技术[J]．中国电机工程学报，2009，29(25)：7-12. Guo Xiaoqiang,Wu Weiyang. Non-devastating islanding detection for micro-grids without non detection zone[J].Proceedings of the CSEE,2009, 29(25): 7-12.   
[14] 张琦，孙向东，钟彦儒，等．用于分布式发电系 统孤岛检测的偶次谐波电流扰动法[J]．电工技术 学报，2011，26(7)：112-119. Zhang Qi, Sun Xiangdong, Zhong Yanru, et al. Even harmonic current disturbing method for islanding detection in the distributed power generation systems[J].Transactions of China Electrotechnical Society,2011,26(7):112-119.   
[15] 谢东．分布式发电多逆变器并网孤岛检测技术研 究[D]．合肥：合肥工业大学，2014.   
[16] Velasco D,Trujillo C,Figueres E,S.An active anti-islanding method based on Phase-PLL perturbation[J].IEEE Transactions on Power Electronics,2011,26(4):1056-1066.   
[17] 刘芙蓉，康勇，段善旭，等．一种有效的孤岛检测 盲区描述方法[J]．电工技术学报，2007，22(10)： 167-172. Liu Furong,Kang Yong,Duan Shanxu,et al.A novel method for mapping non-detection zone[J]. Transactions of China Electrotechnical Society, 2007,22(10): 167-172.   
[18] Wang F,Xu Z G. Evaluation of inverter resident passive islanding detection method for grid connected PV system under constant power mode[C]. IEEE Control & Decision Conference,2009:3086- 3089.