# 全日面太阳磁场望远镜精密温控系统研制

张鑫伟1,²，林佳本²,邓元勇1.2

(1.中国科学院大学，北京 100049;2.中国科学院国家天文台太阳活动重点实验室，北京 100101)

摘要：双折射滤光器是太阳观测中的重要设备，其中的双折射晶体的折射率对温度变化非常敏感，光学设计要求滤光器温度控制系统的稳定精度达到 $0 . 0 1 ^ { \circ } \mathrm { C }$ 以内，才能保证滤光器精确稳定地工作。太阳望远镜中双折射滤光器构型复杂，使用环境恶劣，其高精度温控一直是国际公认的核心技术。针对全日面太阳望远镜滤光器的温控问题，设计了基于积分分离PI加前馈的复合温控系统，实现了对滤光器的高精度恒温控制。系统使用24位AD实现高精度温度采集，采用数字滤波算法提高测温精确度；积分分离PI结合环境温度作为参数的前馈控制的复合控制方法，输出PWM控制策略，实现对滤光器高精度温控。相比原有的滤光器温控系统，本系统在保持原有温控精度的前提下，大大简化了系统设计。结果表明：当设定温度为 $4 2 . 2 1 6 ^ { \circ } \mathrm { C }$ 时，在实验室中，温控精度达到 $\pm 0 . 0 0 1 ^ { \circ } \mathrm { C }$ ；该温控系统已经在怀柔观测基地投入使用，最大温度波动 $0 . 0 0 7 5 ^ { \circ } \mathsf { C }$ ，控制效果准确稳定，获得大量高质量科学数据。

关键词：温度控制；太阳望远镜；双折射滤光器；PID控制；前馈控制分类号： $\mathrm { T H 7 5 3 + }$ 1 文献标识码：A 文章编号：1672-7673（2020）03

太阳磁场是太阳物理中最关键的物理量[1]，太阳耀斑、日冕、太阳黑子等日面活动都与太阳磁场有密切的联系。怀柔太阳观测基地(Huairou Solar Observing Station，HSOS)的全日面太阳磁场望远镜（SolarMagnetism and the Activity Telescope,SMAT）建成于2006 年[2]，开展全日面矢量磁场和全日面 $\mathrm { H } \alpha$ 观测，是具有国际一流水平的太阳磁场和太阳活动监测设备。滤光器是全日面太阳磁场望远镜核心光学组成部件，其中的双折射晶体的折射率对温度变化十分敏感，温度波动能直接导致观测的太阳谱线中心偏移出$6 5 6 2 . 8 1 { \scriptstyle \pm 2 } \mathring \mathrm { A }$ 的设定要求[3]。因此，要使滤光器稳定工作在要求的窄带范围内，达到预期观测目标，就要求光学原件的温度稳定精度必须控制在 $0 . 0 1 ^ { \circ } \mathrm { C }$ 以内[4]。

全日面太阳磁场望远镜从建成至今已运行十多年，原有温控系统精度大大下降，故障频发，因此需要更换新的温控系统。本设计既为设备改造升级，同时也为中国科学院先导专项A类项目先进天基太阳天文台（Advanced Space-borne Solar Observatory，ASO-S）载荷之一全日面矢量磁像仪（Full disk vectorMagnetoGraph，FMG）宇航级温控系统设计积累技术经验。

国内外对高精度恒温控制系统有很深入的研究。随着电子技术与人工智能的发展，温控系统中的测控电路集成度越来越高，温控算法更多的结合神经网络等智能化方法，以适用于复杂非线性的温控场合。在滤光器恒温控制方面，南京天文仪器厂[5将铜丝缠绕在滤光器内核外围，铜丝同时承担测温和加热作用，达到了良好的温控效果。在实验室环境下，使用水银温度计目视测得恒温精度达到了 $\pm 0 . 0 0 5 ^ { \circ } \mathrm { C }$ ，但绕制铜丝复杂耗时，且该工作主要完成在20世纪80年代，采用模拟电路控制方式，设计中的部分电子元器件已经无替代产品可用，硬件电路设计方案也不能满足当前的高集成度、高性能、低功耗等新要求。怀柔太阳观测基地在2012年完成的磁场望远镜滤光器控制系统,采用两级温控方式，基本解决了滤光器温控问题，应用于怀柔基地 35cm 磁场望远镜，本文针对全日面太阳磁场望远镜滤光器，采用一级恒温结构设计，提出基于前馈加反馈的控制方式，进一步简化了滤光器精密温控系统设计。滤光器温控系统的主要难点在于，在室外环境的情况下依旧对恒温精度提出很高的要求，并且需要时间稳定性。综上，结合滤光器温控要求精度高，在室外环境下，目前的温控方案均不能直接适用于滤光器温控问题，同时为了适应当前控制系统的发展潮流，需要对滤光器温控问题进行针对性的研究。

本文对怀柔观测基地全日面太阳磁场望远设计如下温控方案：首先采用24位高分辨率AD设计实现高精度温度读取电路，用PWM温控电路实现加热回路；提出用前馈加反馈的复合温控算法，并设计低散热的保温结构。该系统在实验室环境达到了 $4 2 . 2 1 6 ^ { \circ } \mathrm { C } \pm 0 . 0 0 1 ^ { \circ } \mathrm { C }$ 的稳定精度，在望远镜实际运行中，系统最大波动为 $0 . 0 0 7 5 ^ { \circ } \mathrm { C }$ ，均优于 $0 . 0 1 ^ { \circ } \mathrm { C }$ 温度稳定度的指标要求。

# 1系统介绍

全日面太阳磁场望远镜包含两个望远镜，一个用于测量全日面矢量磁场，另一个用于观测全日面 $\mathrm { H } \alpha$ 。两个望远镜滤光器机械结构设计基本一致，因此，温控系统可采用基本相似的硬件结构和相同的软件系统完成两个望远镜的恒温设计。本文主要以 $\mathrm { H } \alpha$ 望远镜为例介绍滤光器恒温系统设计。

# 1.1硬件构成

Hα望远镜滤光器恒温控制结构设计简图如图1。滤光器最内层是包含光学器件的滤光器内核，由内向外依次是：聚酰亚胺恒温加热膜、羊毛毡恒温保温层，最外层是滤光器的金属外壳。严密的保温结构设计是实现滤光器精密温控的重要保障。 $\mathrm { H } \alpha$ 望远镜滤光器和数字温度传感器放置在全日面太阳磁场望远镜其中一个镜舱内，传感器和加热膜通过屏蔽线缆接入观测室的温控箱。

![](images/44edb07e641fac4520e8b06ef875c67f37987442d6928967df1bab6aaf60e67e.jpg)  
图1Ha望远镜滤光器结构及图温控系统框  
Fig.1Hα telescope filter structure block and Temperature control system diagram

控制箱内的硬件电路核心部件可分为3大模块：精密测温模块、主控芯片模块及PWM驱动加热模块。主控电路模块除了主控芯片外，还包含外围电压管理电路单元和串口通信电路单元；电压管理单元为主控芯片提供稳定的能源供应；串口通信单元负责完成同上位机的数据交互。PWM驱动加热模块由高速MOSFET驱动器、MOS 管和肖特基二极管组成，该模块负责将主控芯片输出的TTL电平升压增流，以满足加热功率需求。

精密测温模块的实现是滤光器高精度温控的首要前提。本文通过选用24位高精度的AD芯片ADS1232，硬件上优化电路设计，软件上采用数字滤波算法，使测温达到万分之一摄氏度的分辨率。在电路设计时，使 AD 芯片的参考电压 Vref 和测温电路电压 $U$ 使用同一电压源，这样避免了 $\frac { U } { V _ { r e f } }$ 波动带来的测温不准的影响。温度读取电路使用电桥式电路接入热敏电阻传感器R，电桥电路计算热敏电阻阻值如(1)式：

$$
\begin{array} { r } { R = \frac { r ( U \mp 2 * u _ { 0 } | ) } { U \pm | 2 * u _ { 0 } | } } \end{array}
$$

其中，正负号的选取需根据电桥输出电压的正负变化确定； $U$ 为 $2 ^ { 2 4 }$ ; $u _ { 0 }$ 为 AD 转换后的值。

将求得的热敏电阻阻值R代入Steinhart-Hart方程解(2)式求出对应阻值的温度：

$$
T = 1 / ( c _ { 1 } + c _ { 2 } * l n R + c _ { 3 } * l n ^ { 3 } R )
$$

其中， $T$ 为热力学温标；c1、c2、c3为常数，由热敏电阻传感器厂家提供。

# 1.2工作流程

系统工作流程如图2。系统工作时，MCU首先对温控参数以及外设初始化，接着采集AD端的数字信号，经过解析求得滤光器的当前温度量，再经过温控算法得到加热膜的控制量，转化为PWM控制信号输出控制，完成的一次测控流程。

![](images/3883c75b72058b49e44c808d5ca431bbc09f2c22c705b8c025bf8b0589d76128.jpg)  
图2温控系统流程图  
Fig.2Temperature control systemflowchart

# 2温控算法设计与实现

温控算法是整个控制系统的核心，通过分析滤光器温控问题的特点，采用了前馈加积分分离PI反馈的复合控制方式。该算法将前馈控制的时效性和反馈控制的稳定性的优点结合在一起，有效地解决了滤光器温控问题。

针对全日面太阳磁场望远镜滤光器温控问题对稳态特性要求高、动态特性要求较低的特性，主控方式选择采用积分分离PI的控制方式。积分分离PI传递函数：

$$
\begin{array} { r } { G ( S ) = K _ { p } + K _ { i } \frac { 1 } { s } } \end{array}
$$

前馈控制系统是根据扰动或给定值的变化进行补偿来工作的控制系统8]，其特点是当扰动产生后，被控变量还未变化前，根据扰动作用的大小进行控制，用来补偿扰动作用对被控变量的影响。

在滤光器温控系统中，环境温度波动是系统外界干扰的主要因素之一，环境温度和被控对象的温差会影响温控对象的散热速率，进而需要调整温控策略以使系统温度稳定。北京日气温变化平均可达 $1 0 ^ { \circ } \mathrm { C }$ ，年

气温变化达 $4 0 ^ { \circ } \mathrm { C } ^ { [ 9 ] }$ 。所以考虑环境温度变化带来的影响是十分必要的，因此，算法将全日面太阳磁场望远镜镜舱内的温度作为参数引入温控算法，提高系统的抗干扰能力。图3是引入前馈控制后的控制框图。

![](images/7d58cbb5465200aad571b6fb448a41e6503cc920be29a1df36d8307e13e2ae3d.jpg)  
图3积分分离PI与前馈控制结合的复合控制系统  
Fig.3 Integral separation PI and feedforward control combined control system

前馈控制需要将环境温度对系统的扰动进行定量描述，才能引入温控算法。因此，需要对全日面太阳磁场望远镜滤光器的温度扰动模式进行研究。环境温度变化直接导致滤光器的散热速率发生变化，全日面太阳磁场望远镜滤光器的散热方式主要属于对流散热，根据对流散热公式：

$$
Q = h A \delta = Q _ { 0 }
$$

其中， $h$ 为换热系数； $A$ 为有效换热面积。对流散热量 $\boldsymbol { Q }$ 与温控对象表面与流体的温差 $\theta$ 成正比，当温差一定时，可以用恒定的加热功率使得输入热量 $Q _ { 0 }$ 等于耗散热量 $\boldsymbol { \mathcal { Q } }$ ，以达到温控对象的恒温要求。所以在设定温度附近，为保持滤光器恒温，系统输出的控制量 $U ( t )$ 总是要大于0。

根据(5)式，散热速率和温差成正比，但直接使用正比例函数描述该扰动会增加外界温度快速波动对温控系统的影响，所以将正比例函数阶梯化，如(5)式。

$$
\begin{array} { r } { U ( t ) \geq f = B \ast I N T \left( \frac { \Theta } { c } \right) + D > 0 } \end{array}
$$

其中，INTO表示取整函数； $B$ 、C、 $D$ 均是根据需求可调整的参数。阶梯函数可以有效缓解外界温度快速波动对系统温控策略的影响。在实测时，根据调试数据累积，确定出3个常数的值。该前馈控制的加入可以迅速确定加热功率的下边界，避免干扰源导致控制系统出现扰动，甚至震荡。

# 3测试结果

# 3.1实验室测试结果

完成系统关键问题研究及硬件电路搭建和软件系统编写后，制作控制箱并搭建模拟实验环境。实验中，首先通过调节PI参数，消除温控稳态静差，待稳定后记录两通道的温度数据并绘制曲线。光学仪器中,晶体部件对温度变化敏感，升温过快、不均匀会加大晶体损坏的风险。试验中，滤光器从室温 $1 9 \mathrm { { ^ \circ C } }$ 升至 $4 2 ^ { \circ } \mathrm { C }$ 耗时 $2 . 5 \mathrm { h }$ 。图4是滤光器温度平稳后的温度曲线。从图4可以看出,温度稳定后滤光器在近 $2 0 \mathrm { { m i n } }$ 时间内，温度持续保持在 $4 2 . 2 1 6 ^ { \circ } \mathrm { C } \pm 0 . 0 0 1 ^ { \circ } \mathrm { C }$ 内，优于稳定度在 $0 . 0 1 ^ { \circ } \mathrm { C }$ 内的指标要求。

![](images/35b340bd5192befb7e7754ce2da648a6dbe1b94b79255bc030323bfeb6b19a4f.jpg)  
图4滤光器温控系统测试结果

# 3.2现场实测结果

在实验室环境中，本方案设计的温控系统表现良好稳定，因此，于2018年8月用于全日面太阳磁场望远镜观测现场。截止到目前，该系统已稳定运行1年之久。图5是温控系统在 $3 0 \mathrm { { m i n } }$ 内温度曲线图，从中可以看出，温度数值均在 $4 2 . 2 1 2 3 { \sim } 4 2 . 2 1 9 8 ^ { \circ } \mathrm { C }$ 之间，最大波动 $0 . 0 0 7 5 ^ { \circ } \mathrm { C }$ ，满足 $0 . 0 1 ^ { \circ } \mathrm { C }$ 的精度要求。计算RMS，如公式(6)，得42.2157004。

$$
\mathrm { R M S } = \sqrt { \frac { \sum _ { i = 0 } ^ { n } { t _ { i } } ^ { 2 } } { n - 1 } }
$$

![](images/91a1b24a37f1ac3671ab3f770fc29fa164899e68a7a2031e1381097a3bc3ce03.jpg)  
Fig.4 Test results of filter temperature control system   
图5实测中滤光器温度变化曲线  
Fig.5Filter temperature curve in actual measure

# 4结论

滤光器温控是全日面太阳磁场望远镜中的一项关键技术，高精度恒温系统是望远镜准确稳定工作的重要保障。本文针对室外环境工作的滤光器温控问题设计的温控系统，采用加热膜及新型电子元件设计温控方案，提出前馈加积分分离PI的复合一级温控方式，简化了系统设计。在实验室环境中，系统在72小时阶段内保持稳定工作，温控精度优于温控目标要求；在实际运行1年中，滤光器温控稳定精度波动在 $0 . 0 1 ^ { \circ } \mathrm { C }$ 范围内，产出大量高质量的科学数据。

当前系统虽然已经达到了预期的设计目标，但在系统的设计、调试过程中发现有两方面的问题可以进一步研究，提升系统的稳定度和可靠性：（1）确定温控算法参数比较耗时，更换被控系统后还需重新进行参数整定；（2）算法考虑了环境温度对滤光器温控的干扰，但缺乏对太阳光照射到滤光器内部的能量的定量计算分析。因此，下一步将研究采用自适应温控算法，方便系统调试使用，并分析太阳光对滤光器温控的影响，进一步提高系统的抗干扰能力。

# 参考文献

1 刘煜，张洪起，包曙东．太阳磁场观测研究[J]．天文学进展,2001,19(1):34-44.  
2 郭晶晶，杨云飞，冯松,等．太阳望远镜高精度导行方法[J]．科学通报,2016,61(10):91-99.  
3 ZHANGHQ，WANG DG,DENG Y Y,et al.Solar magnetism and the activity telescope at HSOS[J].Chinese Journalof  
Astronomy & Astrophysics,2007,7(2):281-288.  
4LINJB，DENGYY,GUOJ,etal.Designofthehighprecisionthermostatforbirefringentflter[C//Procedingsof the  
Ground-based and Airborne Telescopes VI. 2016.  
5 侯惠芳，明长荣．滤光器恒温控制电路[J].北京天文台台刊，1986(2):239-244.  
6 于佳．滤光器恒温控制系统设计[D]．北京：中国科学院大学，2012.  
7 李毅，余少辉，周步洲．基于DS18B20的测温系统设计【J】．电子技术，2009（1）：11-13.  
8 胡庆波，吕征宇．全数字伺服系统中位置前馈控制器的设计[J]．电气传动，2005，35(5):24-27.  
9 杨萍，肖子牛，刘伟东．北京气温日变化特征的城郊差异及其季节变化分析[J]．大气科学,2013,37(1):101-112.

# Development of Precise Temperature Control System for Solar Magnetism and the Activity Telescope

Zhang Xinwei1.2,Lin Jiaben², Deng Yuanyong (1.UniversityofChinese AcademyofScience，Beijing1Ooo49，China;

NationalstronomicalObservatory，ChineseAcademyofSciences，Beijingol，China，Email:zhangxinwei5@mailsucasducn)

Abstract: Birefringent filters are the key optical components of solar telescopes.The birefringence of the refracted crystal in the filter is very sensitive to temperature changes.The stabilization accuracy must be beter than $0 . 0 1 ^ { \circ } \mathrm { C }$ to ensure that the filter operates stably and accurately. The high precision temperature control system of solar telescope has always been recognized as the core technology in the world,because of the complex structure of birefringent filter which is used outdoors.Temperature control system based on integral separation PI and feedforward is designed for the temperature control of the filter of Solar Magnetism and the Activity Telescope to achieve thermostaticcontrol of the filter with High-Precision. High-Precision temperature acquisition is realized by using 24-bit AD and temperature measurement accuracy is improved by digital filtering algorithm.

A compound control algorithm is designed by combining integral separated PI temperature control algorithm with a feedforward control that takes the ambient temperature as a parameter. Compared with the original filter temperature control system, this design greatly simplifies the system without loss of temperature control accuracy. As aresult, PWM control strategy is output to achieve the secondary temperature control of the filter core and the insulation layer. The system had been tested for 72 hours in laboratory. When the temperature is set at $4 2 . 2 1 6 ^ { \circ } \mathrm { C }$ the accuracy of temperature control is better than $4 2 . 2 1 6 \mathrm { + / \mathrm { - 0 . 0 0 1 ^ { \circ } C } } .$ Since 2O18,the system has been put into use at Huairou Solar Observing Station,and the maximum temperature fluctuation is $0 . 0 0 7 5 ^ { \circ } \mathrm { C }$ . The control system is accurate and stable, and a large number of high-quality scientific data are obtained.

Key words:Temperature control,Solar telescope, Birefringent filters,PID control,Feed-forward control