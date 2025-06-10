# 新型热继电器过载保护研究

宗鸣宫赫

（沈阳工业大学电气工程学院沈阳 110870)

![](images/aeea2fc2953affffdcfa922c325e5cf3618bc3aba9fa235265ccffbae0f1cb08.jpg)

宗鸣男1957年生，教授，博士生导师，研究方向为特种电机及其控制、智能化电器。

摘要：热继电器过载保护的传统机理是依据双金属片的受热弯曲特性，但由于双金属片材料及特性分散性较大、反时限特性单一、调整误差大、重复性差、易受环境温度影响误动或拒动等原因，很难满足当今的过载保护要求。为了确保交流电动机安全可靠的工作，需要对热继电器进行电子化和智能化的研究。本文提出了一种新型热继电器的控制原理，通过实验验证了该原理的可行性，为电动机的热保护开辟了一条新的途径。

关键词：新型热继电器 电动机过载保护 控制原理 智能化研究中图分类号：TM582

# Research on Overload Protection of New Type Thermal Relay

Zong MingGong He (Shenyang University of TechnologyShenyang 110870 China ）

![](images/cc49f8dbe4b9e2614059a46a3e5f4724ab7fef66cb9161b25b1451cf14dcb13f.jpg)

宫赫女1991年生，硕士，研究方向为电器设计及其关键技术。

Abstract: The overload protection mechanism of traditional thermal relay is based on the heated bending properties of double metal sheets. However, because of the double sheet metal materials and characteristics of scattered large,the inverse time characteristic of single,the large error of adjust, poor reproducibility, and it is easily influenced by the environment temperature misoperation or maloperation. So,it is difficult to meet the requirements of the current overload protection.In order to ensure the safety and reliability of the AC motor, it is necessary to study the electronic and intelligent thermal relay. In this paper, a new type of thermal relay control principle is presented,and the feasibility of the principle is verified by experiments.A new way for the motor thermal protection is opened up.

Keywords: New thermal relay, motor overload protection, control theory, intelligent research

# 1 引言

热继电器的主要用途是用于电动机的过载保护、断相保护以及不对称保护。电动机是将电能转化成机械能的装置，用作拖动各种生产机械的动力，是工业、农业和国防建设及人民生活正常进行的重要保证[1]。据不完全统计，电动机的耗电量占电网总发电量的 $70 \%$ 以上，是工农业及商业系统中应用最为广泛的动力设备。然而，每年因故障造成电动机烧毁甚至引发重大安全事故的事件时有发生。因此，为了确保电动机的正常运行，热继电器的过载保护就显得十分重要[2-4]。利用双金属片实现过载保护的热脱扣方式方法简单、体积小、成本低，可在一定程度上获得反时限保护特性[5]。但是，由于双金属片材料及特性分散性较大、反时限特性单一、调整误差大、重复性差、易受坏境温度影响误动或拒动等原因，很难满足当今的过载保护要求[6-9]。此外，采用双金属片的热继电器还有一大缺点一—复位等待，即如果线路出现过载，双金属片弯曲使得继电器已经动作，那么由于温度的变化需要时间，所以即使在排除故障后也必须要等到双金属片的温度降下来以后，线路才能继续供电[10]。

电子式热继电器[11-12]的出现解决了传统热继电器的缺点，但同时又引入了新的问题，即需要一个测量线路电流的工具一一电流互感器，而电流互感器由于有铁心、体积大、易饱和等缺陷限制了热继电器智能化的发展[13-14]。

本文提出了一种热电混合式过载保护新原理，是一种简单有效的新方法。配合单片机的控制，能够实现保护特性多样且调节方便、不受环境温度影响、重复性和稳定性比较好、便于智能化控制的目的。同时还能减小电器设备的体积，避免大电流时铁心饱和，增大电流的监控范围。此外，还能解决传统热继电器动作后，要想复位需要等待的问题。

# 2 新型热继电器的控制系统

# 2.1控制系统

热继电器的过载保护分为热保护和电子式过电流保护两种，热保护是通过热元件将过载电流转变为温度，借助双金属片实现过载脱扣。电子式过电流保护采用电流传感器检测过载电流，配合单片机系统实现过载保护。本项目结合传统双金属片的热保护和电子式过电流保护（称之为热电混合式过载

保护)，如图1所示，用温度传感器代替了热保护中的双金属片，用热元件和温度传感器组合代替了电子式过电流保护中的电流互感器。首先通过热元件1来反映电流，绝缘材料2是导热性能好的绝缘材料，通过绝缘材料2将温度传递到温度传感器3，然后通过温度传感器3将温度变换成电信号，考虑到环境温度的影响，采用补偿温度传感器4进行修正。最后，将电信号传送到单片机系统5，进行计算，然后发出相应指令，通过电磁机构6控制主回路的通断。

![](images/bd1d870d0d681090442f5e99e487cf6cb72666146413dad53265fbb9652831a8.jpg)  
图1热电混合式过载保护系统  
Fig.1Thermo-electric mixed type overload protection system 1—热元件2—绝缘材料3—温度传感器4—补偿温度传感器 5—硬件电路6—单片机系统7—电磁机构

# 2.2理论分析

电子式热继电器是根据测量线路中的电流来判断电流的过载情况，本文正好相反，是利用热继电器金属片上温度的变化情况来反应线路中电流的变化。根据热平衡原理（也称为能量守恒定律）[15]，有

$$
p \mathrm { d } t = c G \mathrm { d } \tau + k F \tau \mathrm { d } t
$$

式中， $p$ 为恒值的热功率； $\mathbf { \Psi } _ { c }$ 为发热体的比热容；$G$ 为发热体的质量； $F$ 为发热体的散热表面面积；$k$ 为散热系数； $\tau$ 为某个时刻下，发热体对冷却体的温差。在本文中，发热体与冷却体的温差代表的是热继电器双金属片与热继电器内部的环境温度的差值。

式（1）等号右边第1项表示发热体温升提高$\mathrm { d } \tau$ 时所吸取的热能；第2项表示发热体在储存热能的同时，还出现了散至冷却体的热能。恒值的热功率是由电阻发热引起，则

$$
i ^ { 2 } R \mathrm { d } t = c G \mathrm { d } \tau + k F \tau \mathrm { d } t
$$

两边同除以 $\mathrm { d } t$ ，得

$$
i ^ { 2 } R = c G \frac { \mathrm { d } \tau } { \mathrm { d } t } + k F \tau
$$

假定热继电器的双金属片的电阻恒定不变，则

$$
i ^ { 2 } = \frac { c G } { R } \frac { \mathrm { d } \tau } { \mathrm { d } t } + \frac { k F } { R } \tau
$$

假定热继电器的工作环境稳定，则令

$$
{ \frac { c G } { R } } = a
$$

$$
{ \frac { k F } { R } } = b
$$

则有

$$
i ^ { 2 } = a \frac { \mathrm { d } \tau } { \mathrm { d } t } + b \tau
$$

式（7）是在两个假定条件下得到的电流与温升的关系。如果能够得到系数 $\boldsymbol { a }$ 和 $b$ 就能够通过式 (7)描述线路电流和发热体温升的关系，进而在热电混合式过载保护控制系统中，就可以通过测量双金属片的温度变化和环境温度变化，得到线路的电流。

# 3新型热继电器的结构设计

本文以JR36-20型热继电器为参考，对其结构进行改造设计新型热电混合式热继电器。JR36-20型为三相双金属片式，其脱扣级别为10A，具有整定电流连续可调装置。由于JR36-20型热继电器的双金属片为新型热电混合式热继电器的热元件，如图2所示，利用耐热绝缘的物体固定住双金属片，使得双金属片受热不能弯曲。温度传感器需要快速反应出线路电流的变化，因此绝缘材料选择导热不导电并且能够粘住温度传感器的材料，本项目选择3J型导热双面胶，温度传感器和温度补偿传感器则是采用热电阻PT100，用来检测A、B、C三相电流的温度传感器通过导热双面胶贴在热继电器的三个双金属片上，用来检测环境温度的温度补偿传感器则通过导热双面胶贴在热继电器的塑料外壳上。在固定好双金属片、贴好温度传感器之后，将热继电器封装好，并固定在硬件电路板上。传感器的引出线与硬件电路连接在一起，硬件电路用来反应热电阻PT100的电阻值以及电阻值稳定后的时间。原热继电器的铁心和触点在新型热继电器中由信号继电器来代替。

![](images/4894d27007b773d02e3ef2643cd3c42f0801de0cdfccd7a5580918d7b5c09517.jpg)  
图2新型热继电器  
Fig.2New type of thermal relay   
图3硬件电路整体设计方案  
Fig.3The overall design of hardware circuit

# 4 硬件设计

# 4.1硬件电路整体设计方案

新型热电混合式过载保护继电器的硬件电路如图3所示，其中包括了桥式测量电路、模拟开关、差动放大器、单片机、LED显示、键盘输入以及继电器输出。通过PT100将双金属片的温度信号转换成电阻信号，通过桥式测量电路将电阻信号转换为电压信号，进而由模拟开关选择，经过差动放大器输送到单片机里，在单片机里对其进行A-D转换，并进行判断处理后，将输出信号送到液晶显示器上显示电流值、温度值以及热继电器的工作状态和故障类型，同时控制继电器的通断。键盘输入用来使继电器复位。

A传温度 PT100 桥式测量 液晶显示器B相温度 PT100 桥式测量 8选 差动放大器传感器 电路 1模拟 PI单1片机77 继电器C温 PT100 桥式测量 开关 输出环境温度PT100 桥式测量 键盘

# 4.2硬件电路

图4为依据上述硬件电路整体设计方案以及本项目的设计思想所设计的硬件电路。

图4硬件电路中74HC4051是一个8选1模拟开关，其通道0、1、2分别对应双金属片上PT100的电压信号，通道3对应用来测量环境温度的PT100的电压信号，通道4、5用来调整放大器的放大倍数，通道6用来对放大器进行调零。实际的硬件电路如图5所示。

![](images/70631cede5c989880f4f3b31a2266b0be1a73a8447cacd268b919ceaa14cd570.jpg)  
图4硬件电路

![](images/96b2ed9ce11874f07ecc3cf39cce73424e88465724893c3cc78ef89db912a7b5.jpg)  
图5实际的硬件电路 Fig.5Actual hardware circuit

# 5 软件设计

根据热继电器的过载特性标准，结合热继电器的过载电流与温升之间的数学模型以及过载延时的特性要求，通过单片机进行软件设计。程序流程图如图6所示。

本项目根据电流的过载情况，可以实现电流热过载保护、断相保护以及电流的不对称保护。首先，因为电动机的起动瞬间电流会迅速增大，所以需要避开电动机的起动过程。在程序流程图中，采用延

![](images/73715041bcbfae413da26b167929c82d74f64a711422f709fdcd901edfb1deba.jpg)  
Fig.4Hardware circuit   
图6程序流程图  
Fig.6Program flow chart

时等待来处理。其次，无论是基于电流的何种故障，都需要知道电流值。项目采用PT100热电阻通过桥式电路测量出各支路PT100稳定后的电阻值，进而通过查其分度表，得到此时的温升，再通过主回路电流与温升之间的关系得到三个支路的电流情况，根据电流与热继电器额定电流的大小就可以判定线路中是否有电流故障，为何种电流故障。若没有故障，程序回到初始化位置，继续检测线路的主回路电流；若出现故障，需要对不同的故障进行不同的处理，具体如下：

(1）出现过载故障时，需要先进行延时处理，延时时间到，显示过载故障并且继电器执行脱扣。(2）出现断相故障时，显示断相故障并且继电器执行脱扣。(3）出现不对称故障时，显示不对称故障，并且报警。故障处理完毕时，热继电器需要手动按键复位，复位后，将回到初始化位置。

# 6 实验

通过上述理论分析和设计，最关键的是要通过实验来建立线路的主回路电流与温升之间的数学模型。本文通过虚拟服务器采集PT100两端的电压。在某一环境温度下，给热继电器通以一定的电流 $I _ { 1 }$ 观测硬件电路电压的变化，进而可得在这一电流下，双金属片上PT100 两端的电压与通电时间的关系，以及代表环境温度的PT100 两端的电压。由于电压与电阻是线性关系，PT100的电阻与温度也是线性关系，则式（7）也可以表示为

$$
i ^ { 2 } = { \cal A } \frac { \mathrm { d } u } { \mathrm { d } t } + B u
$$

式中， $u$ 为虚拟服务器直接采集到的PT100两端的电压； $A$ 为与发热体的比热容、质量、电阻以及桥式测量电路的电阻和PT100的温度电阻之间的线性关系有关的一个参数； $B$ 是与发热体的散热面积、散热系数、电阻以及桥式测量电路的电阻和PT100的温度电阻之间的线性关系有关的一个参数。

综上所述，通过测得的实验数据，由式（8）即可得到主回路的电流，实验现场如图7所示，考虑到实验能承受的范围，选取线路额定电流为3A，每一组实验通过虚拟服务器采集600个数据，得到的电压如图8所示，分别是电流为2倍过载（6A）、3倍过载（9A）、4倍过载（12A）和5倍过载（15A)

![](images/729429c0bf73cdf114783c2dae15ae40e6b1db72835f06bd50088bf49e010613.jpg)  
图7实验现场 Fig.7Experiment site

所对应PT100的电压信号的变化，以及对应的压差。

对图8的数据进行分析，利用Matlab软件，得到的模型为

$$
i ^ { 2 } = 4 2 . 2 3 + 3 7 1 0 { \frac { \mathrm { d } u } { \mathrm { d } t } } + 1 2 7 6 u
$$

![](images/59133a7180fd6ccc300edaeb0a5b6b3234437b312555b827e0abe5d2c7613c5f.jpg)  
(a）2倍过载电压信号

![](images/04293c15e04cfaf90918f5b23f09a85c99541a62ad57dd5808cfb762337b12df.jpg)  
(b）2倍过载压差信号

![](images/3153c003d345f6cbf025deb80c87f50d3179af0311e76b94ae1f99d4b351fdcc.jpg)  
(c）3倍过载电压信号

![](images/5ef16e9db4662f73d67156504d441842677b8f0a4af21f3cf12062c284809992.jpg)  
(d）3倍过载压差信号

![](images/7f3d0f383172ced77671c47fea95b0ae6862da412df94532af5921bd251d5264.jpg)  
(e）4倍过载电压信号

![](images/aceb08821e2371bb54f00a5a2bed153913bc4c8bf9f02e3ca99b1348994d926e.jpg)  
(f）4倍过载压差信号

![](images/f14154776d01935be7e5c0ef183942b151c3ec87f896c4bfb99ed79a69cb1744.jpg)  
(g）5倍过载电压信号

![](images/d48060f4ff4850f2a7bbe310bbfd7b084f981c7cf7b05b9983c68283bafab9a7.jpg)  
图8实验数据曲线  
Fig.8The curves of experimental data

由式 (9)，利用上述硬件电路以及软件程序设计，即可完成本文提出的通过温度的变化来确定线路中的电流的新型热继电器的设计。实验数据见下表。

# 表实际电流与显示的电流

Tab.Comparison of actual current and display current   

<html><body><table><tr><td>实际电流/A</td><td>显示电流/A</td></tr><tr><td>3</td><td>3.0</td></tr><tr><td>6</td><td>5.6</td></tr><tr><td>9</td><td>9.3</td></tr><tr><td>12</td><td>11.9</td></tr><tr><td>15</td><td>14.9</td></tr></table></body></html>

由上表可知通过硬件电路显示的电流与线路中实际流过的电流有差别，从图7也可以看出，电压有波动，分析产生这种现象的原因有如下几点：

（1）双金属片的电阻并不是恒定的，是随温度的升高而变化的。(2）散热系数可能会随某些因素变化。(3）新原理的验证是在传统热继电器的结构上进行改造，其散热条件不好，很难达到热平衡。(4）实验过程中，由于电流的变化通过调压器调节，是一个连续变化量，因此也可能对一些数据参数造成影响。

尽管存在一些误差，本实验也验证了新原理的可行性。因此，若想要将这种新的思想应用于实际当中，就需要对热继电器的结构进行重新设计。首先，依据本文的系统结构图（见图1）需要用热元件来取代双金属片，要求热元件的电阻随温度变化要小；其次热继电器的散热条件也需要做相应的改变，方案一是通过增加通风口来提高散热能力；方案二是将与热元件接近位置的外壳处改用导热良好的金属来代替。对比两种方案，方案一会引入新的问题，即如果增加通风口，其内部环境不再封闭，易受外界环境的影响，而方案二仍然是一个封闭的环境，其散热主要依靠热传导实现，散热系数相对恒定。

# 7 结束语

本文提出了作为电动机过载保护的热继电器的一种新的设计原理，既能实现多种保护特性，又能确保热继电器的体积，同时还具有智能化的显示、报警等功能，结合了传统热继电器和电子式热继电器的优点，适用于所有电动机的过载保护。不仅对新型热继电器进行了理论分析、硬件电路设计和软件设计，还对传统热继电器进行了改造，通过实验验证了新型热继电器的可行性。新型热继电器的结构参数还有待进一步研究。总而言之，热电混合式过载保护作为一种新思想，不仅可以应用在热继电器上，也可以应用于断路器的过载保护，甚至是短延时保护，这对智能化电器的发展具有推动作用。

# 参考文献

[1] Orr M P. Thermal overload protection for electric motors on motor-operated valves[J]. Federal Register, 2012.   
[2] 隋宏进．关于电机保护问题的探讨[J]．电气工程 应用[J]．2012(1)：34-36. Sui Hongjin. Discussion on the protection of electric motors[J]. Electrical Engineering Application, 2012(1): 34-36.   
[3] 吴国沛，周良才．鼠笼异步电动机常见故障的分 析与诊断[J]．华南理工大学学报：自然科学版, 1999，27(10): 52-57. Wu Guopei, Zhou Liangcai. Analysis and diagnosis of common fault of the asynchronous motor in squirrel cage[J]. Journal of South China University of Technology: JCR Science Edition, 1999,27(10): 52-57.   
[4] 李璇华，黄益庄，唐晓泉，等．电动机故障分析 和综合保护配置[J]．电力系统保护与控制，2001， 29(12): 30-33. Li Xuanhua, Huang Yizhuang, Tang Xiaoquan, et al. Motor failure analysis and integrated protection configuration[J].Power System Protection and Control,2001,29(12):30-33.   
[5] 柳春生．双金属片式热继电器的应用条件分析[J]. 煤矿机电，2002，23(7)：99-101. Liu Chunsheng. Applied condition analysis of bimetallic type heat relay[J]. Colliery Mechanical & Electrical Technology,2002，23(7): 99-101.   
[6] 马振东.热继电器故障分析及处理[J].农村电气化, 2007(7): 35. Ma Zhendong.Thermal relay failure analysis and processing[J]. Rural Electrification,2007(7): 35.   
[7] 鲍棋铭，高乃奎，马小芹，等．大型发电机主绝缘 老化的热分析研究[J]．中国电机工程学报，2003, 23(7): 99-101. Bao Ming, Gao Naikui, Ma Xiaoqin, et al. The thermal analysis of primary insulation of large power generators[J]. Proceedings of the CSEE, 2003, 23(7): 99-101.   
[8] Wang S,Sun L,Huang W C.Thermal overload protection for AC asynchronous motor based on complex morlet wavelet[J].Applied Mechanics & Materials,2015,740: 364-367.   
[9] 汪东芳．用电机保护器取代热继电器以实现节能 [J]．电工技术，2008(8)：56，66. Wang Dongfang. Replacing thermal relay with motor protector to realize energy saving[J]. Electrical Engineering, 2008(8): 56, 66.   
[10]薛建和．热继电器自动复位时间的影响因素[J]. 电气开关，1992(1)：18-20. Xue Jianhe. The influence factors of the automatic reset time[J]. Electrical Switch,1992(1): 18-20.   
[11]周月英．一种新型电子式热过载继电器[J]．电工 电气，2010(8)：36-38. Zhou Yueying.A new type of electronic thermal overload relay[J]. Electrical & Electronics,2010(8): 36-38.   
[12]池国英．对电子式电机保护器的新探索[J]．河北 工业科技，2004，21(3)：14-16. Chi Guoying. New exploration of electronic machine protector[J]. Hebei Industrial Technology, 2004,21 (3): 14-16.   
[13]何瑞华．智能电网系统中低压电器发展探讨[J]. 低压电器，2011(1)：1-5. He Ruihua. The development of low voltage electrical equipment in smart grid system[J]. Low Voltage, 2011(1): 1-5.   
[14]陈德桂．智能电网促进了低压电器新品种的发展 与新技术的应用[J]．低压电器，2010(23)：1-7. Chen Degui. Smart grid promotes the development of new and new technologies for low-voltage electrical appliances[J]. Low Voltage,2010(23): 1-7.   
[15]Frei PU,Weichert H O.Advanced thermal simulation of a circuit breaker[C]. Proceedings of the 50th IEEE Holm Conference on Electrical Contacts and the 22nd International Conference on Electrical Contacts,2004: 104-110.   
[16]张宜倜．变压器温升计算原理分析[J]．变压器, 2009，46(9):6-10. Zhang Yijun.Analysis of the theory of temperature rise in transformer[J]. Transformer, 2009,46(9): 6-10.