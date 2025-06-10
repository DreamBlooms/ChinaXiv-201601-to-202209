# 电网监控系统中变压器自适应负载率新算法

米超杨华郑燃²周晖1（1.国网河北省电力公司石家庄供电分公司石家庄 0500512.国网金华供电公司金华321000）

![](images/a6f17d8eac92e8c06e515b72633919f0373c406b199c6484abd54e63f786fa18.jpg)

米超男1986年生，工程师，主要从事电网监控、电力调度、继电保护方面的工作。

摘要：在电网集中监控模式中，变压器负载率监视所采用的传统负载率计算方法受变压器中、低压侧开关遥测采样正确性的影响。本文利用调度技术支持系统的网络拓扑分析，引入开关状态参数和主变压器状态参数，提出一种主变压器自适应负载率算法，并通过仿真模型进行仿真验证，结果表明该方法能正确反映变压器负载率，并且不受变压器中、低压侧开关遥测采样正确性的影响，对科学调度、精细监控具有重要意义。

关键词：电网监控 负载率 自适应中图分类号：TM734

# A New Adaptive Load Rate Approach of Transformer in Power Grid Monitoring System

![](images/50b4e8cb6e2fac11920b34cb257c10a3a169016f3495f108c49e589b1181db02.jpg)

Mi Chao1 Yang Hua1Zheng Ran²Zhou Huil (1. State Grid Hebei Eletric Power Company Shijiazhuang Power Supply Branch Shijiazhuang050051 China 2.State Grid Jinhua Eletric Power CompanyJinhua3210oo China ）

杨华女1986年生，工程师，主要从事电力调度、电网监控、继电保护方面的工作。

Abstract: Under centralized monitoring model for power grid, the traditional calculation method for monitoring transformer loading rate is influenced by measurement value sampling of medium voltage side and low voltage side circuit breakers. Based on network topology analysis in regulation technical support system, switch state parameter and transformer state parameter is introduced.A new adaptive loading rate approach is proposed and simulation model verifies the effect of this model. Through this simulation model, the adaptive loading rate algorithm can correctly get the load rate of transformer, which is not influenced by measurement value sampling of medium voltage side and low voltage side circuit breakers. The method is important to scientific regulation and careful monitoring.

Keywords: Power grid monitoring,loading rate, adaptive

# 1 引言

随着电网运营规模的不断扩大，调控一体化发展[1-3]进入了新的阶段。电网监控业务是“大运行”体系建设的一个重要环节，不仅承担了电网运行监视的基本业务，还包括了信号分析处理[4-8]、开关远方操作、事故处理、新设备投运验收、输变电设备状态在线监测、工业视频辅助监视等业务[9-12]，给监控值班员带来了新的挑战，同时也给电网监控中信息筛选与处理的智能化提出了更高的要求。

在电网日常监视过程中，变压器负载率是重点监视内容之一，但传统的负载率计算可靠性受到现场设备，包括采样装置、测控装置、远动装置、调度数据网的可靠性的制约。在大强度工作量的监控业务中，不易发现由于相关装置异常产生的不匹配数据及错误数据。尤其在“迎峰度夏”期间，主变压器负载率的正确性对电网供电可靠性监测有重要作用。由于遥测数据不正确（模值变小）导致高负载率的主变压器实际显示低负载率，未引起监控员注意，从而导致处理时机延误，发生主变压器跳闸甚至损坏重要设备的情况。

本文采用的自适应变压器负载率新算法在主变压器中、低压侧开关遥测值不正确的情况下，仍能得到正确的主变压器负载率，并与传统负载率计算值作对比，反应出遥测存在的隐患缺陷，为消缺处理提供了重要依据。

# 2传统主变压器负载率计算方法

目前，国家电网公司各级调度机构均采用D5000智能调度技术支持系统，此系统能根据现场采集的实时运行数据，结合电网模型、拓扑连接关系，将传统的面向开关、量测的监视提升为面向一次设备运行状态的综合监视，为调度员提供基于设备基本量测的信息，如机组停复役、线路停运、线路充电、线路过载、高压电抗器的投退、静止补偿器投退、变压器投退或充电、变压器过载、母线投退等，使得调度员、监控员能够直观地了解设备运行状态。D5000系统的功能结构如图1所示。

在D5000系统中，对于图2内桥接线变电站的三绕组变压器，传统的变压器负载率计算是通过采集中、低压侧有功、无功遥测值，得到相应主变压器的视在功率。此算法未包含主变压器损耗，因主变压器损耗所占主变压器视在功率的比例不大，对负载率计算结果影响较小，在电网实时监控业务中对负载率信息准确度的获取是可以接受的。

![](images/6ae2cdbba709e1180338416a2e1e563ce5b997cdff7400ad17d25d6e3fb0e724.jpg)  
图1D5000系统功能结构图

![](images/04fafe0ffec030a379c923319b0db774079ba7ceeff717279638bba5359f2b28.jpg)  
Fig.1D5ooO system function structure diagram   
图2110kV变电站接线示意图  
Fig.2Wiring diagram of $1 1 0 \mathrm { k V }$ substation

1# 主变压器负载率为

$$
\delta _ { 1 } ( ^ { \boldsymbol { \circ } } / _ { 0 } ) = \frac { \sqrt { \left( P _ { 1 } + P _ { 2 } \right) ^ { 2 } + \left( Q _ { 1 } + Q _ { 2 } \right) ^ { 2 } } } { S _ { \mathrm { n 1 } } }
$$

2#主变压器负载率为

$$
\delta _ { 2 } ( ^ { 0 } / _ { 0 } ) = \frac { \sqrt { \left( P _ { 3 } + P _ { 4 } \right) ^ { 2 } + \left( Q _ { 3 } + Q _ { 4 } \right) ^ { 2 } } } { S _ { \mathrm { n } 2 } }
$$

从图2及式（1）可以看出，1#变压器负载率的可靠性与 $P _ { 1 }$ ， $P _ { 2 }$ ， $\boldsymbol { { Q } } _ { 1 }$ ， $\boldsymbol { Q } _ { 2 }$ 遥测采样的正确性直接相关。一旦变压器中、低压侧开关的遥测采样异常或遥测不刷新，1#主变压器负载率将变为不可靠数据。而且在电网集中监控模式下，对于地区级电网，县域 $1 1 0 \mathrm { k V }$ 变电站二次设备质量参差不齐，一些设备老旧严重，遥测装置异常状况时有发生。遥测采样异常未有相应的光字牌及告警信息，监控范围内厂站数量较多，监控员无法及时发现相关遥测缺陷，为事故埋下了隐患。

# 3 变压器自适应负载率计算方法

如图3所示，石家庄地区电网 $1 1 0 \mathrm { k V }$ 隆兴变电站采用内桥接线方式，分为 $1 1 0 \mathrm { k V }$ 、 $3 5 \mathrm { k V }$ 、 $1 0 \mathrm { k V }$ 三个电压等级。进线1视在功率为 $S _ { 1 1 }$ ，进线2视在功率为 $S _ { 1 2 }$ ， $1 1 0 \mathrm { k V } ~ 1 \#$ 段母线电压为 $U _ { 1 1 }$ ， $1 1 0 \mathrm { k V } 2 \#$ 段母线电压为 $U _ { 1 2 }$ ，分段al开关视在功率为 $S _ { \mathrm { a l } }$ 。

![](images/c647a065b30f5037041e1fa7fb44df62ddc00c813115085f8da53a46d5f813ac.jpg)  
图3 $1 1 0 \mathrm { k V }$ 隆兴变电站接线图  
Fig.3Wiring diagram of $1 1 0 \mathrm { k V }$ Longxing substation

引入潮流矩阵

$$
S = [ S _ { 1 1 } \quad S _ { \mathrm { a 1 } } \quad S _ { 1 2 } ]
$$

开关状态矩阵为

$$
A { = } [ A _ { 1 1 } \quad A _ { \mathrm { a } 1 } \quad A _ { 1 2 } ]
$$

主变压器状态矩阵为

$$
\pmb { { \cal B } } = [ B _ { 1 \# } \quad B _ { 2 \# } ]
$$

其中，开关状态参数为

主变压器状态参数为

分段a1开关视在功率为

$$
S _ { \mathrm { a l } } = \left| U _ { 1 1 } I _ { \mathrm { a l } } \right|
$$

对于内桥接线变电站， $1 1 0 \mathrm { k V }$ 侧运行方式见表

1。运行方式依次为：（a）正常运行方式；(b）单主变压器1；（c）单主变压器2；（d）单线路1；（e）单线路2；（f）单线路单主变压器11；（g）单线路单主变压器12；(h）单线路单主变压器21；（i）单线路单主变压器22。

# 表1内桥接线状态参数

Tab.1 State parameter in internal bridge connection   

<html><body><table><tr><td>参数</td><td rowspan="2">A11</td><td rowspan="2">Aa1</td><td rowspan="2">A12</td><td rowspan="2">B1#</td><td rowspan="2">B2#</td></tr><tr><td>方式</td></tr><tr><td>(a)</td><td>1</td><td>0</td><td>1</td><td>1</td><td>1</td></tr><tr><td>(b)</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td></tr><tr><td>(c）</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td></tr><tr><td>(d)</td><td>1</td><td>1</td><td>0</td><td>1</td><td>1</td></tr><tr><td>(e)</td><td>0</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>(f)</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>(g)</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td></tr><tr><td>(h)</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td></tr><tr><td>(i)</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td></tr></table></body></html>

不同运行方式下，根据 $1 1 0 \mathrm { k V }$ 侧的相关参数可得两台主变压器的视在功率 $S _ { 1 \# }$ ， $S _ { 2 \# }$ 为

(a）正常运行方式

$$
S _ { 1 \# } = S _ { 1 1 } \quad S _ { 2 \# } = S _ { 1 2 }
$$

(b）单主变压器1

$$
S _ { 1 \# } = S _ { 1 1 } + S _ { 1 2 } \quad S _ { 2 \# } = 0
$$

(c）单主变压器2

$$
S _ { 1 \# } = 0 \quad S _ { 2 \# } = S _ { 1 1 } + S _ { 1 2 }
$$

(d）单线路1

$$
S _ { 1 \# } = S _ { 1 1 } - S _ { 1 2 } \quad S _ { 2 \# } = S _ { \mathrm { a 1 } }
$$

(e）单线路2

$$
S _ { 1 \# } = S _ { \mathrm { a l } } S _ { 2 \# } = S _ { 1 2 } - S _ { \mathrm { a 1 } }
$$

(f）单线路单主变压器11

$$
S _ { 1 \# } = S _ { 1 1 } \quad S _ { 2 \# } = 0
$$

（g）单线路单主变压器12

$$
S _ { 1 \# } = 0 S _ { 2 \# } = S _ { 1 1 }
$$

(h）单线路单主变压器21

$$
S _ { 1 \# } = S _ { 1 2 } \quad S _ { 2 \# } = 0
$$

(i）单线路单主变压器22

$$
S _ { 1 \# } = 0 S _ { 2 \# } = S _ { 1 2 }
$$

令 $S _ { 1 + 2 } = \left| S _ { 1 1 } + S _ { 1 2 } \right|$ ，则上述不同运行方式下主变压器视在功率计算式为正常运行方式、单主变压器、单线路单主变压器

$$
S = \binom { S _ { 1 \# } } { S _ { 2 \# } } = \binom { B _ { 1 \# } S _ { 1 1 } + ( 1 - B _ { 2 \# } ) S _ { 1 2 } } { B _ { 2 \# } S _ { 1 2 } + ( 1 - B _ { 1 \# } ) S _ { 1 1 } }
$$

单线路

$$
S = { \binom { S _ { 1 \# } } { S _ { 2 \# } } } = { \binom { S _ { 1 + 2 } A _ { 1 1 } + S _ { \mathrm { a 1 } } ( A _ { 1 2 } - A _ { 1 1 } ) } { S _ { 1 + 2 } A _ { 1 2 } + S _ { \mathrm { a 1 } } ( A _ { 1 1 } - A _ { 1 2 } ) } }
$$

由上述分析可知，对变电站运行方式的识别是自适应负载率算法的重要组成部分。通过D5000调度技术支持系统进行网络拓扑，获得断路器的状态信息，从而确定变电站当前运行方式。根据不同的运行方式，自主选择负载率计算公式。图4为自适应负载率算法的流程图。

![](images/ed26b097eafa1f3d899ad6d16e5055ee37f39cc5cd12904269a65d7f3b0a10e6.jpg)  
图4自适应负载率算法流程图  
Fig.4Flow chart of adaptive load rate approach

# 4案例分析

本文采用石家庄电网 $1 1 0 \mathrm { k V }$ 富村变电站作为仿真模型。运行方式如下：该变电站为内桥接线，两台主变压器容量均为 $5 0 \mathrm { M V \cdot A }$ ， $1 1 0 \mathrm { k V }$ 进线为中富线166、中高1线T接线167开关，分别带 $1 1 0 \mathrm { k V }$ 两段、三段母线运行，正常运行方式下分段102、302、502开关均为热备用。图5为D5000系统中富村变电站的一次接线图简化示例。

当 $1 1 0 \mathrm { k V }$ 中富线检修状态时，中高1线T接线167开关带2#、3#主变压器运行，102开关在运行状态。3#主变压器的313开关采样异常， $3 5 \mathrm { k V }$ 三段母线各分路遥测总加值与313开关遥测值不匹配。

![](images/ba6a561f1d865146bcd6203e96549f8e1eb0c2118c3a280a310e7c3be7426928.jpg)  
图5110kV富村变电站潮流图  
Fig.5Electric power flow of $1 1 0 \mathrm { k V }$ Fucun station

此时，按照传统负载率计算方式，3#主变压器负载率为

$$
\left\{ \begin{array} { l l } { P _ { 3 } = P _ { 3 1 3 } + P _ { 5 1 3 } } \\ { Q _ { 3 } = Q _ { 3 1 3 } + Q _ { 5 1 3 } } \\ { \delta _ { 3 } ( \vphantom { ^ 0 } \% ) = \sqrt { P _ { 3 } ^ { 2 } + Q _ { 3 } ^ { 2 } } / S _ { \mathrm { N } } } \end{array} \right.
$$

按照自适应负载率算法，通过图4中变电站运行方式的自动识别，得到3#主变压器负载率为

$$
\left\{ \begin{array} { l } { P _ { 3 } ^ { \prime } = P _ { 1 6 6 + 1 6 7 } A _ { 1 6 7 } + P _ { 1 0 2 } ( A _ { 1 6 6 } - A _ { 1 6 7 } ) } \\ { Q _ { 3 } ^ { \prime } = \mathcal { Q } _ { 1 6 6 + 1 6 7 } A _ { 1 6 7 } + \mathcal { Q } _ { 1 0 2 } ( A _ { 1 6 6 } - A _ { 1 6 7 } ) } \\ { \delta _ { 3 } ^ { \prime } ( \% ) = \sqrt { { P _ { 3 } ^ { \prime } } ^ { 2 } + { Q _ { 3 } ^ { \prime } } ^ { 2 } } / S _ { \mathrm { N } } } \end{array} \right.
$$

两种负载率算法对比见表2。

表2两种负载率算法对照表  
Tab.2 Comparison table of two load rate approaches   

<html><body><table><tr><td></td><td>传统算法</td><td>自适应算法</td></tr><tr><td>3#主变压器负载率(%)</td><td>65.04</td><td>98.86</td></tr></table></body></html>

由表2可知，在主变压器中、低压侧开关采样异常时，传统负载率算法不能正确反映主变压器负荷情况。尤其在主变压器重载时，不能满足过负荷报警要求。3#主变压器已经接近满载，需要采取转移负荷的措施，此时传统计算方法因计算结果严重偏小未能在监控信息中推出主变压器过负荷等相关告警报文，影响调度负荷转移的时机。自适应负载率算法通过 $1 1 0 \mathrm { k V }$ 侧开关遥测值的对比计算，真实反映出主变压器视在功率的情况，为负荷监视和潮流控制提供重要依据，具有可靠性和自适应性。

当变电站采样装置均无异常时，富村站遥测数据如图6所示。经过两种负载率计算方法得到的3#主变压器负载率结果见表3。

![](images/7a42162d354cde6087de23413966f388f6019b743e50614a991c483746f18bfa.jpg)  
图6 $1 1 0 \mathrm { k V }$ 富村变电站潮流图  
Fig.6Electric power flow of $1 1 0 \mathrm { k V }$ Fucun station

表3两种负载率算法对比  
Tab.3 Comparison of two load rate approaches   

<html><body><table><tr><td></td><td>传统算法</td><td>自适应算法</td></tr><tr><td>3# 主变压器负载率(%)</td><td>97.02</td><td>98.86</td></tr></table></body></html>

在采样装置无异常的情况下，传统负载率计算方法和自适应负载率计算方法在主变压器视在功率的计算结果上，只相差主变压器损耗值，对计算结果影响不大，两者的计算结果相近，均能正确反映主变压器负载率。

因此，在实际电网监控系统中，主变压器负载率的传统计算方法应与自适应算法相结合，保留传统计算方法的告警报文显示、负载率越限相关窗口展示区等信息。在此基础上增加自适应主变压器负载率计算展示平台。通过两种方法结果的自主对比，形成可视化的对比展示平台。不仅能提高主变压器过负荷监视的效率，还能发现主变压器中、低压侧开关遥测采样异常缺陷情况，为今后遥测装置消缺提供了参考依据。

# 5 结束语

本文分析了电网监控系统中变压器负载率传统计算方法的不足，在总结内桥变电站运行方式的基础上，引入开关、主变压器状态参数，并归纳出自适应负载率计算方法，形成系统的自适应负载率计算方法流程。最后通过仿真模拟验证了新方法的可靠性和自适应性。在电网监控业务中，自适应计算方法和传统计算方法相结合，通过两种方法计算结果的对比分析，既弥补了传统计算方法的不足，为主变压器负载率监视提供了重要保障，又能更便捷地发现遥测采样异常缺陷，为今后的设备消缺提供数据支持。

# 参考文献

[1] 张颖，熊德智． $5 0 0 \mathrm { k V }$ 电网运行集控中心设计与 实现[J]．中国电力，2010(7)：81-85. Zhang Ying, Xiong Dezhi. Design and implementation of $5 0 0 \mathrm { k V }$ power grid operating centralized control center[J].Electric Power,2010(7):81-85.   
[2] 叶康，王伟，林锋，等．特大城市电网集中监控 模式下设备告警信息参数模型的研究[J]．华东电 力，2014，42(1):82-87. Ye Kang,Wang Wei, Lin Feng,et al. Alarm information parameter model under centralized monitoring mode for mega-urban grid [J]. East China Electric Power,2014,42(1): 82-87.   
[3] 赵林，赵家庆，钱科军．调度自动化系统新型人机 界面关键技术研究[J]．电网技术，2014，38(11)： 3193-3198. Zhao Lin, Zhao Jiaqing,Qian Kejun. Research on key technology of new man-computer interface for dispatching automation system[J]. Power System Technol0gy,2014,38(11): 3193-3198.   
[4] 祁爱华，康洪波，赵翊君．基于云计算技术的 智能电网监控系统的研究[J]．电源技术，2014, 38(9): 1743-1744. Qi Aihua,Kang Hongbo,Zhao Yujun.Research of smart grid monitoring system based on cloud computation[J]. Chinese Journal of Power Sources, 2014,38(9): 1743-1744.   
[5] 司亚超，于江利，吕国．基于Zigbee 技术的智能 电网监控系统的研究和分析[J]．电源技术，2014, 38(4): 783-784. Si Yachao,Yu Jiangli, Lv Guo.Research and analysis of smart grid monitoring system based on Zigbee technology[J]. Chinese Journal of Power Sources, 2014,38(4): 783-784.   
[6] 王金丽，盛万兴，王金宇，等．中低压配电网统 一数据采集与监控系统设计和实现[J]．电力系统 自动化，2012，36(18)：72-76. Wang Jinli,Sheng Wanxing,Wang Jinyu,et al. Design and implementation of a centralized data acquisition and supervisory system for mediumlow voltage distribution network[J].Automation of Electric Power Systems,2012,36(18): 72-76.   
[7] 金芬兰，王昊，范广民，等．智能电网调度控制 系统的变电站集中监控功能设计[J]．电力系统自 动化，2015，39(1)：241-247. Jin Fenlan,Wang Hao,Fan Guangmin, et al. Design of centralized substation monitoring functions for smart grid dispatching and control systems[J]. Automation of Electric Power Systems,2015,39(1): 241-247.   
[8] 许家焰，陈浩敏．基于OS2的变电站一体化监控 模拟仿真系统的设计与实现[J]．电力系统保护与 控制，2015，43(15)：111-117. Xu Jiayan,Chen Haomin.Design and realization of integrated supervision and control simulation system based on OS2 in substation[J].Power System Protection and Control, 2015,43(15):111-117.   
[9] 杜红卫，何勇，张瑞鹏，等．地区电网调度智能辅 助决策软件设计[J]．电力系统自动化，2010(2)： 108-112. Du Hongwei, He Yong, Zhang Ruipeng, et al. Design of regional power grid dispatching intelligent aided decision-making software[J].Automation of Electric Power Systems,2010(2):108-112.   
[10] 葛朝强，黄志龙，毕晓亮．华东电网世界一流 调度指标监控可视化设计[J]．华东电力，2014, 42(3): 439-441. Ge Chaoqiang,Huang Zhilong,Bi Xiaoliang,et al. Index monitoring visualization design for east China power grid world-class scheduling[J]. East China Electric Power,2014,42(3): 439-441.   
[11] 王虎，谢江，王鹏，等．一种电网调控一体化 仿真培训系统的实现方法[J]．华东电力，2014, 42(3): 567-572. Wang Hu,Xie Jiang,Wang Peng,et al.DTS implementation method for power grid integrated dispatching and control[J]. East China Electric Power, 2014,42(3): 567-572.   
[12] 赵林，王丽丽，刘艳，等．电网实时监控可视化技 术研究与分析[J]．电网技术，2014，38(2)：538- 543. Zhao Lin,Wang Lili,Liu Yan,et al. Research and analysis on visualization technology for power grid real-time monitoring[J]. Power System Technology, 2014,38(2): 538-543.