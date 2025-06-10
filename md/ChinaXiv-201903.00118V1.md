# 基于灵敏度法的停电系统网架重构过程中负荷调整策略

![](images/4f77ca381e87adfeaaf678a8096c543c65fb583356dadeae8e9cf81a8f318352.jpg)

石屹岭男 1992年生，硕士研究生，研究方向为电力系统安全稳定控制。

石屹岭\~ 马福龙周前 汪成根 陈晞（1.南京理工大学自动化学院 南京 2100942.江苏省电力公司电力科学院 南京 210008）

摘要：电力系统停电恢复过程中需要恢复负荷以平衡发电机出力的增加，但负荷的投入可能造成已恢复节点电压越限，影响恢复过程的安全。本文基于灵敏度法调整负荷分配方案，使各节点电压满足要求。首先对已恢复电网进行灵敏度分析，在潮流计算的基础上，计算电压越限节点与所有负荷节点视在功率变化的灵敏度，对灵敏度最大的负荷节点，根据最大的灵敏度计算要投入的负荷量，将功率平均分配到各负荷节点，循环调用上述方法直至所有节点电压均满足要求。IEEE39节点系统仿真验证了本文方法的有效性。

关键词：停电灵敏度负荷调整 网架重构中图分类号：TM714；V44

# Load Adjustment Strategy Based on Sensitivity Analysis During Network Reconfiguration of Blackout System

![](images/1193c6f397a58d008a0fc2d931a968f90c63b785fc117d4b69dce73980841ae5.jpg)

Shi Yiling'Ma Fulongl Zhou Qian²Wang Chenggen² Chen $X i ^ { 1 }$ (1. Nanjing University of Science of TechnologyNanjing 210094 China 2. Jiangsu Electric Power Company Research InstituteNanjing 210008 China）

马福龙男 1994年生，研究方向为电力系统安全稳定控制。

Abstract: During power system restoration, it is necessary to restore the load for balancing the increasing output of the generator, but the restoration of load may cause over-voltage of restored nodes, which would affect the safety of power system recovery. In this paper, based on the sensitivity approach, the load distribution scheme is presentedto satisfy the voltage requirements of each node.Firstly,based on the power flow calculation, the sensitivities between the most severityover-voltage node and other load nodes are calculated. The load adjust capacity of the most sensitive load node is calculated according to its sensitivity, which is equal allocated to other load nodes.Above steps will berecalled untilthe voltages of all nodes are security. The validity of the proposed method is verified in IEEE 39-bus testing system.

Keywords: Blackout, sensitive, load adjustment, power grid reconfiguration

# 1 引言

随着互联电网的规模不断扩大，电力系统的可靠性不断提高，但是影响电网不稳定的因素也在不断增多，各种不确定因素仍可能引发大面积停电事故，对社会造成灾难性的影响[1-2]。停电系统的恢复过程可以分为黑启动阶段、网架重构阶段和负荷恢复阶段[3-4]，在网架重构阶段需要恢复负荷以平衡发电机出力的增加，对加快系统恢复具有重要意义。

现有研究中对负荷恢复的优化进行了大量研究。文献[5]基于最短路径算法和遗传算法对配电网的负荷进行优化。文献[6]利用直角坐标的最优乘子牛顿潮流法与灵敏度技术对负荷恢复阶段的负荷恢复量进行优化。文献[7]用遗传模拟退火算法计算得到最大允许恢复负荷量。文献[8]采用基于电网分区的负荷恢复智能优化策略。文献[9]对网架重构过程中的负荷恢复进行优化，采用层次分析法和贪婪算法恢复尽可能多的负荷。文献[10]提出采用广域测量系统提供的实时精确数据使负荷恢复量最大化。文献[11]考虑了负荷恢复过程中的冷负荷恢复特性，用粒子群算法求解最大负荷恢复量。文献[12]考虑了负荷恢复过程中的暂态电压、频率变化，用自适应遗传算法求解负荷恢复量。

在网架重构阶段，现有研究主要通过智能算法得到满足约束条件的负荷分配方案，但由于智能算法求解速度较慢，且负荷分配主要是配合发电机出力，所以需要加快负荷分配方案的计算速度，从而加快网架重构的优化速度。

基于此，本文基于灵敏度法调整负荷分配方案，使各节点电压满足要求。首先对已恢复电网进行灵敏度分析，在潮流计算的基础上，计算过电压节点与所有负荷节点视在功率变化的灵敏度，对灵敏度最大的负荷节点，根据最大的灵敏度计算要投入的负荷量，将功率平均分配到各负荷节点，循环调用上述方法直至所有节点电压均满足要求。最后，以IEEE39节点系统为例对本文方法进行验证。

# 2 灵敏度分析

灵敏度分析是基于潮流方程的电力网络稳定性分析方法之一，它根据系统中某些变量之间的微分关系，来表示变量之间的敏感程度，物理概念明确，计算简单[13-14]。灵敏度分析方法基于网络方程的线性化，分析状态变量和控制变量之间的关系，当控制变量发生微小变化时，状态变量也会发生变化，根据它们之间的这种关系，可以用灵敏度指标来衡量系统的稳定程度，并且可作为系统稳定性调节的依据。本文用灵敏度分析方法分析节点电压与负荷节点注入功率之间的关系，通过灵敏度指标来调整负荷的投入，以保持电压在稳定范围内。

# 2.1灵敏度分析的数学模型

灵敏度分析基于潮流方程，潮流计算的基本方程是节点功率平衡方程

$$
P _ { i } = U _ { i } \sum _ { j = 1 } ^ { n } U _ { j } ( G _ { i j } \cos \delta _ { j } + B _ { i j } \sin \delta _ { i j } )
$$

$$
Q _ { i } = U _ { i } \sum _ { j = 1 } ^ { n } U _ { j } ( G _ { i j } \sin \delta _ { j } - B _ { i j } \cos \delta _ { i j } )
$$

式中， $P _ { i }$ ， $\boldsymbol { Q } _ { i }$ 分别为节点的有功功率和无功功率；$U _ { i }$ ， $U _ { j }$ 分别为i、 $j$ 节点的节点电压； $G _ { i j }$ ， $B _ { i j }$ 为节点导纳矩阵的元素的实部和虚部； $\delta _ { \scriptscriptstyle i j }$ 为两节点之间电压相位的差值。

在灵敏度分析中所有的变量可以分为三类，分别为控制变量 $U$ 、状态变量 $X$ 及独立参数变量 $\alpha$ ，控制变量包括负荷节点有功无功、发电机节点有功无功；状态变量包括负荷节点电压及相角；独立参数变量包括线路导纳阻抗。按照这种变量分类潮流方程可表示为以下形式[15-18]

$$
f ( X , U , \alpha ) = 0
$$

$$
\Delta X = - \Bigg ( \frac { \partial f } { \partial X } \Bigg ) ^ { - 1 } \frac { \partial f } { \partial U } \Delta U = S \Delta U
$$

将潮流方程在运行点线性化可得式 (4)，即状态变量和控制变量之间的灵敏度矩阵表达式。

# 2.2灵敏度指标

本文需要分析节点电压随负荷变化的灵敏度指标，根据这两个灵敏度指标可以求出将电压稳定到约束范围内需要的有功负荷和无功负荷调整量，上述两个指标的意义为：

（1）当PQ节点的有功功率增加时，该节点的电压下降；反之当PQ节点的有功功率减少时，该节点的电压上升。(2）当PQ节点的无功功率增加时，该节点的电压下降；反之当PQ节点的无功功率减少时，该节点的电压上升。

# 3基于灵敏度分析的电压越限调整策略

在负荷恢复过程中，发电机出力在缓慢增加，负荷的投入也受到功率增量的约束，本文采用灵敏度分析的方法调整负荷的投入，将电压限制到约束范围内。

基本策略是找出电压越限最严重的节点，采用式（5）求出该点电压与系统所有负荷节点的视在功率变化灵敏度，找出其中灵敏度最大的负荷节点，根据式（6）求出需要投入的负荷量，如果调整的这个负荷量大于灵敏度最大负荷节点的总负荷量，将要调整的有功负荷量取该节点总负荷量。

$$
S _ { \mathrm { g r } } = \left( S _ { \mathrm { p } } + S _ { \mathrm { Q } } \tan \varphi r \right)
$$

$$
\Delta P _ { \mathrm { L } } = ( \bar { U } - U _ { \mathrm { g } } ) \big / S _ { \mathrm { g r m a x } }
$$

计算出电压调整需要的负荷量后，将这部分功率分配到各负荷节点，将电压调整的这部分功率平均分配给各负荷节点的负荷，无功负荷和有功负荷按相同的比例投入。采用平均分配的方式，各个越限点的电压就会有明显的下降，而且调整的次数也比较少，方法也是最简单。依据上述方法进行电压调整，如果调整后依旧有电压越限点，将重复此过程，直到电压满足要求。网架重构过程中负荷恢复程序流程图如下图所示。

![](images/863387b66d0ca8b809c86b52429df6d6ccfaefebdb3df98d2d60b16e0c9b984f.jpg)  
图网架重构过程中负荷调整策略 Fig.Load adjustment strategy during network reconfiguration

# 4 算例分析

为了检验本文算法的有效性，以IEEE39节点系统为例对本文方法的有效性进行仿真分析。假设节点31为黑启动电源和平衡机，装机容量为${ 5 8 0 } \mathrm { M W }$ 。系统总恢复过程分为了9个时步，每个时步都起动一台发电机组，并恢复已建立网架中的部分重要负荷，具体恢复顺序见表1。

# 表1每个时步的恢复路径

Tab.1 Restoration path with each time step   

<html><body><table><tr><td>时 步</td><td>起动 机组</td><td>总恢复时间 恢复路径 /min</td></tr><tr><td>1</td><td>32</td><td>31→6→11→10→32</td></tr><tr><td>2</td><td>33</td><td>6→5→4→14→15→16→19→33</td></tr><tr><td>3</td><td>36</td><td>70</td></tr><tr><td>4</td><td>35</td><td>85</td></tr><tr><td>5</td><td>30</td><td>100</td></tr><tr><td>6</td><td>37</td><td>110</td></tr><tr><td>7</td><td>34</td><td>120</td></tr><tr><td>8</td><td>38 3 →18→17→27→26→29→38</td><td>150</td></tr><tr><td>9</td><td>39</td><td>165</td></tr></table></body></html>

以第二时步为例，说明负荷调整策略。在第一时步时，31节点上负荷全部投入，在第二时步时，发电机增加出力为 $4 1 . 6 \mathrm { M W }$ ，将负荷分配到节点4、15、16，分配完成后系统潮流见表2。

表2负荷分配后的潮流计算  
Tab.2Results of power flow calculation after load distribution   

<html><body><table><tr><td>节点</td><td>电压</td><td>发电有功</td><td>发电无功</td><td>负荷有功</td><td>负荷无功</td><td>无功补偿</td></tr><tr><td>编号 4</td><td>(pu) 1.0910</td><td>/MW 0</td><td>/Mvar</td><td>/MW</td><td>/Mvar 18.4</td><td>/Mvar</td></tr><tr><td>5</td><td>1.0810</td><td>0</td><td>0 0</td><td>50</td><td></td><td>0</td></tr><tr><td>6</td><td>1.0790</td><td>0</td><td>0</td><td>0 0</td><td>0</td><td>0</td></tr><tr><td>10</td><td>1.0710</td><td>0</td><td>0</td><td>0</td><td>0 0</td><td>0 0</td></tr><tr><td>11</td><td>1.0740</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>14</td><td>1.1020</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>15</td><td>1.1130</td><td>0</td><td>0</td><td>37.5</td><td>17.9</td><td>0</td></tr><tr><td>16</td><td>1.1170</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>19</td><td>1.1200</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>31</td><td>1.0000</td><td>22.2</td><td>0</td><td>9.2</td><td>4.6</td><td>-29.1</td></tr><tr><td>32</td><td>0.9830</td><td>97.5</td><td>-86.5</td><td>12.5</td><td>0</td><td>0</td></tr><tr><td>33</td><td>1.0470</td><td>0</td><td>0</td><td>10</td><td>0</td><td>0</td></tr></table></body></html>

从表2中可看出，节点15、16、19电压越限，最高电压越限点为19节点。用基于灵敏度分析的方法调整电压越限，首先计算19节点与各负荷节点的视在功率灵敏度，选出灵敏度最大的节点，通过计算得到最大灵敏度为-0.036，该节点需要增加的负荷为 $2 2 5 \mathrm { M W }$ 。将这部分功率平均分配到其他负荷点中，无功负荷按有功负荷的比例同时投入，负荷调整后潮流结果见表3。

表3电压越限调整后的潮流计算结果  
Tab.3Results of power flow calculation after regulating the over-limit voltage   

<html><body><table><tr><td>节点</td><td>电压</td><td>发电有功</td><td>发电无功</td><td>负荷有功</td><td>负荷无功</td><td>无功补偿</td></tr><tr><td>编号</td><td>(pu)</td><td>/MW</td><td>/Mvar</td><td>/MW</td><td>/Mvar</td><td>/Mvar</td></tr><tr><td>4</td><td>1.0500</td><td>0</td><td>0</td><td>147.9</td><td>54.4</td><td>0</td></tr><tr><td>5</td><td>1.0570</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>6</td><td>1.0580</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>10</td><td>1.0570</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>11</td><td>1.0580</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>14</td><td>1.0510</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>15</td><td>1.0470</td><td>0</td><td>0</td><td>126.6</td><td>60.60</td><td>0</td></tr><tr><td>16</td><td>1.0490</td><td>0</td><td>0</td><td>79.5</td><td>7.8</td><td>0</td></tr><tr><td>19</td><td>1.0520</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>31</td><td>1.0000</td><td>290.7</td><td>0</td><td>9.2</td><td>4.6</td><td>58.3</td></tr><tr><td>32</td><td>0.9830</td><td>97.5</td><td>-24.9</td><td>12.5</td><td>0</td><td>0</td></tr><tr><td>33</td><td>0.9830</td><td>0</td><td>0</td><td>10</td><td>0</td><td>0</td></tr></table></body></html>

可以看出，各节点的电压都降到约束范围内，负荷有功无功都有所增加，整个系统功率保持在平衡状态，本文负荷调整策略有效。在每个时步中重复调用本文调整策略，可以快速实现恢复过程中负荷的调整，为网架重构的优化提供支持。

# 5 结论

针对停电系统恢复网架重构过程中负荷恢复引起的电压越限问题，本文提出了基于灵敏度法的负荷调整策略。对已恢复的电网进行潮流计算，选择电压越限节点，采用灵敏度法计算该节点对所有负荷点的灵敏度，取灵敏度最大的负荷点，基于灵敏度技术负荷调整量，将负荷调整量分配到其他负荷点，循环上述步骤直至所有节点电压均满足要求。IEEE39节点系统仿真结果表明，本文方法能够有效地解决节点电压越限的问题，提高恢复过程中电网的安全性。

# 参考文献

[1] 唐斯庆，张弥，李建设，等．海南电网 $^ { 6 } 9 \cdot 2 6 ^ { 3 }$ 大面积停电事故的分析与总结[J]．电力系统自动化，2006，30(1)：1-7.Tang Siqing, Zhang Mi,Li Jianshe,et al.Review ofblackout in hainan on september 26th--causes andrecommendations[J].Automation of Electric PowerSystems,2006,30(1): 1-7.

[2] 葛睿，董昱，吕跃春．欧洲"11．4"大停电事故分 析及对我国电网运行工作的启示[J]．电网技术, 2007，31(3): 1-6. Ge Rui, Dong Yu, Lv Yuechun. Analysis of largescale blackout in UCTE power grid and lessons to be drawn to power grid operation in China[J]. Power System Technology,2007, 31(3): 1-6.   
[3] Fink L H, Liou K L, Liu C C. From generic restoration actions to specific restoration strategies[J]. IEEE Transactions on Power Systems,1995,10(2): 745-752.   
[4] Ancona J J. A framework for power system restoration following a major power failure[J]. IEEE Transactions on Power Systems,1995,10(3):1480- 1485.   
[5] 余贻鑫，段刚．基于最短路算法和遗传算法的配电 网络重构[J]．中国电机工程学报，2000，20(9)： 44-49. Yu Yixin,Duan Gang. Shortest path algorithm and genetic algorithm based distribution system reconfiguration[J]. Proceedings of the CSEE, 2000, 20(9): 44-49.   
[6] 刘映尚，吴文传，冯永青，等．黑启动过程中的 负荷恢复[J]．电网技术，2007，31(13)：17-22. Liu Yingshang, Wu Wenchuan, Feng Yongqing, et al.Load recovery during power system blackstart[J]. Power System Technology,2007,31(13): 17-22.   
[7] 陈小平，顾雪平．基于遗传模拟退火算法的负荷 恢复计划制定[J]．电工技术学报，2009，24(1)： 171-175. Chen Xiaoping, Gu Xueping. Determination of the load restoration plans based on genetic simulated annealing algorithms[J]. Transactions of China Electrotechnical Society, 2009,24(1): 171-175.   
[8] 石立宝，赤东阳，姚良忠，等．基于电网分区的 负荷恢复智能优化策略[J]．电力系统保护与控制, 2011，39(2): 1-7. Shi Libao, Chi Dongyang, Yao Liangzhong, et al. Intelligent optimizaiton strategy for load restoration considering power grid partitioning[J]. Power System Protection and Control, 2011,39(2): 1-7.   
[9] 钟慧荣，顾雪平，朱玲欣．黑启动恢复中网架重 构阶段的负荷恢复优化[J]．电力系统保护与控制, 2011，39(17): 26-32. Zhong Huirong,Gu Xueping,Zhu Lingxin. Optimizaiton of load restoration during network reconfiguring process of black-start restoration[J]. Power System Protection and Control, 2011,39(17): 26-32.   
[10] Liu W, Lin Z, Wen F, et al. A wide area monitoring system based load restoration method[J]. IEEE Transactions on Power Systems,2013,28(2):2025- 2034.   
[11] 程改红，徐政．基于粒子群优化的最优负荷恢复 算法[J]．电力系统自动化，2007，31(16)：62-65. Cheng Gaihong,Xu Zheng. Optimal load restoration algorithm based on PSO[J].Automation of Electric Power Systems,2007,31(16): 62-65.   
[12] 杨可，刘俊勇，贺星棋，等．黑启动中考虑动态 过程的负荷最优恢复[J]．电力自动化设备，2009, 29(10): 88-92. Yang Ke,Liu Junyong,He Xingqi,et al. Optimal load restoration consdering dynamic process during blackstart[J]. Electric Power Automation Equipment, 2009,29(10): 88-92.   
[13] 孟波，孟现岭，靳玉凯，等．灵敏度分析法在静 态电压稳定中的应用[J]．技术与市场，2014(4)： 50-51. Meng Bo,Meng Xianling,Jin Yukai,et al. The application of sensitivity analysis in static voltage stability[J]. Technology and Market, 2014(4): 50-51.   
[14] 段献忠，袁骏，何仰赞，等．电力系统电压稳定 灵敏度分析方法[D]．武汉华中科技大学，1997.   
[15] 曾水根，丁俊健，刘万斌．基于逆波算法实现的电 力故障数据分析公式编辑器[J]．电气应用，2016, 35(14): 56-58.   
[16] 孙宏斌，张伯明，相年德．准稳态灵敏度的分析 方法[J]．中国电机工程学报，1999，19(4)：9-13. Sun Hongbin, Zhang Boming,Xiang Niande. New sensitivity analysis method under quasi-steady-state for power systems[J]. Proceedings of the CSEE,1999, 19(4): 9-13.   
[17] 王景亮，张焰，王承民，等．基于灵敏度分析与最 优潮流的电网无功/电压考核方法[J]．电网技术， 2005，29(10):65-69. Wang Jingliang,Zhang Yan,Wang Chengmin,et al. Power system reactive power/voltage assessment based on sensitivity analysis and optimal power flow[J].Power System Technology,2005,29(10): 65-69.   
[18] 程改红，徐政．电力系统故障恢复过程中的过电 压控制[J]．电网技术，2004，28(11)：29-33. Cheng Gaihong,Xu Zheng.A method to control sustained overvoltage during power system restoration[J]. Power System Technology, 2004, 28(11): 29-33.