# 应力锥体增强绝缘非线性属性对HVDC电缆 终端电场分布的影响

李忠华张霞（哈尔滨理工大学工程电介质及其应用技术教育部重点实验室哈尔滨150080）

![](images/a105e6cafe683e46f9634f718d643cfd02e2eaba840e22f21288a8a5b81005d6.jpg)

李忠华男 1962年生，博士，教授，博士生导师，主要从事非线性聚合物绝缘理论与相关测试技术、电缆绝缘与诊断技术等方面的研究工作。

摘要：高压直流电缆及附件稳态电场分布主要取决于绝缘材料的电导率，而电导率又与场强、温度紧密相关，这使得直流电缆附件电场分布相比高压交流电缆附件更复杂。为此，在固定电缆终端XLPE 绝缘、硅油电导率和温度梯度的条件下，本文采用多物理场耦合软件仿真研究了应力锥体增强绝缘非线性属性对高压直流电缆户外复合型终端稳态电场分布的影响规律。仿真研究结果表明：复合型户外高压直流电缆终端，工厂绝缘和增强绝缘界面切向电场在应力锥体根部和顶部可能出现极大值；而在半导电应力锥内表面电场也可能在根部和顶部出现极大值；通过调控增强绝缘材料的非线性属性可实现复合型电缆终端电场分布的综合调控。

关键词：HVDC 电缆终端 应力锥体增强绝缘材料非线性属性电场分布中图分类号：TM247

# Effect of Nonlinear Properties of Stress Cone Reinforced Insulation on Electric Field Distribution of HVDC Cable Terminal

![](images/b4b4e57c37c532a48ddaa77910d51949e518f1674425ef86249d6730996b593c.jpg)

张霞女1990年生，硕士研究生，主要研究方向为非线性复合绝缘材料在高压直流电缆附件中的应用。

Li Zhonghua Zhang Xia (Key Laboratory of Engineering Dielectrics and its Application Technology, Ministry of Education Harbin University of TechnologyHarbin15oo80China ）

Abstract: The steady-state electric field distribution in HVDC cables and accessories mainly depends on the conductivity of insulating materials,and the conductivity is closely related with the electric field and temperature.So the electric field distribution of HVDC cable accessories is more complex than the electric field distribution of HVAC cable accessories. In this paper, the influence of nonlinear properties of stress cone reinforced insulation on the steady-state electric field distribution of outdoor compound terminal of HVDC cable is studied using COMSOL Multiphysics software,and under the conditions in which the XLPE insulation conductivity, silicone oil conductivity and the temperature gradient in the cable terminal are fixed. The simulation results show that: the tangential electric field at the interface between the factory insulation and the reinforced insulation in the compound outdoor HVDC cable terminal will show the maximum field at the root and top of the stress cone,and the electric field of the inner surface of the semicon stress cone may also appear the maximum field at the root and the top.The comprehensive regulation of electric field distribution of compound HVDC cable terminal can be realized by adjusting the nonlinear properties of the stress cone reinforced insulation.

收稿日期：2018-08-03

Keywords: HVDC cable terminal, stress-cone reinforced insulation, nonlinear properties of materials, electric field distribution

# 1 引言

高压直流（HVDC）输电因其输电距离远、输送容量大以及控制灵活等特点，将成为我国高压输电电网的重要组成部分。直流输电在跨越海峡、穿越隧道和城市时，HVDC 电缆成为必然选择[1-3]。高压及超高压直流输电技术的发展为HVDC电缆提供了广阔的发展空间。HVDC电缆附件技术是HVDC电缆的关键技术之一。电缆运行经验表明，除了安装不当或外力机械破坏外，大多数的击穿事故与电缆系统的绝缘材料和绝缘结构关系密切[4-5]。

在直流电压作用下，电缆附件绝缘结构中稳态电场分布由电导率决定，而电导率又是场强和温度的非线性函数，使得具有多层绝缘结构电缆附件的电场分布颇为复杂。电缆附件结构中，绝缘屏蔽层断开处电场应力集中致使电缆附件内部发生局部放电，甚至击穿[6-8]。

电缆附件中电应力控制有两种途径：其一是优化半导电应力锥结构，通过电极结构调控电场分布；其二是利用非线性绝缘材料作为增强绝缘，通过增强绝缘材料的非线性电导或极化特性调控电场分布[7-8]。第一种技术途径是比较传统的方法，得到广泛应用；第二种技术途径在低压电缆附件中得到了实际应用，但并未在高压电缆附件中得到实际应用。将两种技术途径进行有机结合可能是研发更高电压等级电缆附件的有效途径。考虑到非线性绝缘材料在复杂绝缘结构中的潜在应用，国内外学者对非线性绝缘材料进行了材料配方、介电特性及其机理方面的基础研究[9-14]

通过电场数值仿真技术，探明应力锥体增强绝缘非线性属性对HVDC电缆附件中稳态电场分布的影响规律，对后续电缆附件材料研发和结构设计具有重要的指导意义。

# 2 模型建立及求解方法

采用商品化COMSOLMultiphysics软件进行温度场和电场的求解，求解前需进行模型结构、计算场域、材料属性和边界条件的确定等准备工作。

# 2.1电缆终端结构与计算场域的确定

电缆附件包括电缆终端和连接盒，相对而言电缆终端电场分布比连接盒更复杂。为此，本文选择电缆终端为研究对象。考虑到整体预制式电缆终端并没有在HVDC电缆线路中得到应用，本文以硅油填充的 $3 2 0 \mathrm { k V }$ HVDC电缆户外复合终端作为实例，选择图1所示的简化电缆终端结构模型。

![](images/9b00e06703fc336498b7eaf783ddb4449d4d6c4a118cd392ea7e5c4542ac35f8.jpg)  
图1电缆终端模型的结构图

电缆终端是轴对称结构，故采用二维场进行温度场及电场的求解。为了使仿真效果更接近实际，在确定电缆终端有限元计算场域时考虑了空气边界问题。经反复尝试，确定径向长度 $1 2 . 0 0 \mathrm { m }$ 、轴向长度 $8 . 0 0 \mathrm { m }$ 的计算场域，进一步扩大场域只是增加计算量，对电缆终端内温度、电场分布计算影响不大。整体计算场域如图2所示。

![](images/c083c379681b3b7b92190f110b991b3a3ae9d0c937f1873fa6e721cffaff643e.jpg)  
Fig.1Structure diagram of cable termination   
图2电缆终端数值仿真计算场域  
Fig.2 Simulation model diagram of cable termination

# 2.2电缆附件绝缘材料属性的定义

在工程应用温度、电场范围内，绝缘材料的电

导符合跳跃电导机制，其电导率γ与场强、温度的关系为[15-16]

$$
\gamma = A \exp \left( \frac { - \varphi q } { k _ { \mathrm { b } } T } \right) \frac { \sin h ( 1 0 ^ { 6 } B | E | ) } { 1 0 ^ { 6 } | E | }
$$

式中， $A$ 为与材料有关的常数（ $\mathrm { \Delta V / ( \Omega \cdot \ m ^ { 2 } ) }$ ）； $\varphi$ 为活化能（eV）； $q$ 为电子电荷量（C）； $k _ { \mathrm { b } }$ 为玻尔兹曼常数（ $\mathrm { { ( \mathrm { J / K } ) } }$ ； $T$ 为材料温度（K）； $B$ 为电导率对电场的依赖系数！ $\langle \mathrm { m } / \mathrm { V } \rangle$ ； $E$ 为场强（ $\mathrm { { \langle k V / m m } }$ 。

通过实际测量，得到XLPE和硅油绝缘性能参数见表1。

# 表1材料属性参数值

Tab.1 Parameter values of material properties  

<html><body><table><tr><td>材料</td><td>A/[V/(Ω · m²)]</td><td>B/(m/V)</td><td>φ/(eV)</td><td></td></tr><tr><td>XLPE</td><td>28.80</td><td>7.10 × 10-8</td><td>0.52</td><td>2.3</td></tr><tr><td>硅油</td><td>2.22</td><td>2.32 ×10-7</td><td>0.40</td><td>1.7</td></tr></table></body></html>

通过大量的实验配方研究，确定增强绝缘材料相关参数范围：系数 $A$ 的在 $5 . 3 9 \times 1 0 ^ { - 4 } \sim$ $5 3 . 9 0 ( \mathrm { V } / \Omega \cdot \mathrm { m } ^ { 2 } )$ 之间；电场依赖系数 $B$ 的范围为（204号 $9 . 0 0 \times 1 0 ^ { - 8 } \sim 6 . 0 0 \times 1 0 ^ { - 7 } \mathrm { { m / V } }$ ；活化能 $\varphi$ 的范围为$0 . 2 3 \sim 0 . 6 0 \mathrm { e V }$ ；相对介电常数为2.7。

考虑玻璃钢套管和硅橡胶复合绝缘子处的温度、场强变化范围很小，将两者的电导率定义为常数，即 $5 \times 1 0 ^ { - 1 4 } \mathrm { S / m }$ ，相对介电常数分别为3.7和2.6。

# 2.3电缆终端稳态温度场的求解

根据参考文献[17]，确定电缆终端各类材料热学参数见表2。

表2材料的热学参数值  
Tab.2Thermal parameter values of material   

<html><body><table><tr><td>材料</td><td>热导率/[W·(m·K)-1]热熔/[J·(kg·K)]密度/(kg·m-3)</td></tr><tr><td>增强绝缘</td><td>0.25 1700 1180</td></tr><tr><td>XLPE 0.29</td><td>2250 922</td></tr><tr><td>硅油 0.14</td><td>1630 960</td></tr><tr><td>玻璃钢 0.33</td><td>700 2200</td></tr><tr><td>绝缘子 0.20</td><td>1300 1250</td></tr></table></body></html>

目前，HVDCXLPE电缆线芯长期工作温度为$7 0 \mathrm { { ^ \circ C } }$ ，未来研究的目标是使XLPE直流电缆线芯工作温度达到 $9 0 \mathrm { ^ \circ C }$ [18]。因此，仿真模型中将电缆导体线芯温度设定为 $9 0 \mathrm { { ^ circ C } }$ 。根据传热学三类边界条件的定义[19-20]，在计算电缆终端稳态温度场分布时，假设周围传热介质分布均匀，并且温度保持稳定。电缆终端的稳态温度场求解中，取图1中的a边界、b边界为第一类边界条件，即环境温度 $2 0 \mathrm { { ^ circ C } }$ ；c边界为自由边界。采用稳态求解器得到电缆终端的稳态温度场分布，如图3所示。

![](images/6b8d63e5c7d096d4458e78597462f43221e737403c355a80a99e991e3b698fca.jpg)

图3电缆终端稳态温度场分布图  
Fig.3Static temperature field cloud chart of cable termination

由图3可知，电缆终端的XLPE部分的温度范围是 $8 8 . 4 8 \sim 8 9 . 8 3 \mathrm { ^ \circ C }$ ，增强绝缘部分的温度范围是$8 4 . 8 8 \sim 8 8 . 4 8 \top$ 。本研究以此稳态温度场分布为条件对电缆终端进行电场求解。

# 2.4电场计算的加压方式及求解

电缆终端的直流稳态电场仿真时，定义电缆线芯电位为 $2 3 0 \mathrm { k V }$ ，图2中的边界b、c设定为零电势位；边界a为自由边界，采用瞬态求解器。根据仿真结果，施加5000s时电场分布基本达到稳态。稳态电场分布除决定于边界条件外，还取决于由于材料介电属性空间梯度变化形成空间电荷极化[21-22]。

# 3电缆终端稳态电场仿真及分析

研究表明，非线性绝缘材料具有均化电场分布的功能[1-14,23-24]。增强绝缘电导率按式（1)，且参数设定 $\varLambda = 5 . 3 9 \times 1 0 ^ { - 3 } \mathrm { V } / ( \Omega \cdot \mathrm { m } ^ { 2 } )$ 、 $B = ( 3 . 4 8 \times 1 0 ^ { - 7 } ) \mathrm { m / V } ,$ （2$\varphi = 0 . 2 3 \mathrm { e V }$ 为典型值，仿真得到稳态电场分布结果如图4所示。

![](images/ccf1b962c7a44f2331863907d7a3704664ce9d932b077021f741fccb5cbef406.jpg)  
图4电缆终端稳态电场分布图  
Fig.4Static electric field distribution diagram of cable termination

由图4可知，电缆终端是一种多层绝缘结构，界面是绝缘的薄弱环节。为此，后续研究选取应力锥内表面、XLPE工厂绝缘与增强绝缘界面处的场强为电缆终端电场分布的主要研究对象。

# 3.1材料相关系数 $A$ 对稳态电场分布的影响

取电场依赖系数 $B = ( 3 . 4 8 \times 1 0 ^ { - 7 } ) \mathrm { m } / \mathrm { V }$ 、活化能$\varphi = 0 . 2 3 \mathrm { e V }$ ，取不同系数 $A$ 值仿真得到界面切向场强和应力锥表面场强分布与电场依赖系数 $A$ 的关系如图5所示。

由图5a可知，应力锥内表面最大电场随参数 $A$ 的增大而大幅度减小，当 $A > 5 . 3 9 \times 1 0 ^ { - 3 } \mathrm { V } / ( \Omega \cdot \mathrm { m } ^ { 2 } )$ 时，应力锥内表面电场可控制 $1 \mathrm { k V / m m }$ 附件。

由图5b可知， $A$ 值过大或过小，在应力锥体、电缆绝缘和硅油三结合点（图1中的h点）处均出现最高电场，且电场方向不同。当 $\varLambda = 5 . 3 9 \times 1 0 ^ { - 3 } \mathrm { V } / ( \Omega \cdot \mathrm { m } ^ { 2 } )$ 时，其对应的最大界面切向场强值为 $0 . 8 \mathrm { k V / m m }$ ，满足复合绝缘交界面的切向场强值要控制目标要求，小于1kV/mm[21]

![](images/7a22782a0de01a54b28b6d56f920d8a5bbf98f9c63f3bd7b3461e62d251d1c6b.jpg)  
图5不同 $A$ 值下稳态电场分布图  
Fig.5Diagram of steady electric field distribution under different $A$ values

结合图5a和5b， $A$ 值过大或过小均导致电缆终端电场畸变严重，控制在 $5 . 3 9 \times 1 0 ^ { - 3 } \mathrm { V } / ( \Omega \cdot \mathrm { m } ^ { 2 } )$ 附近较为合适。

# 3.2电场依赖系数 $B$ 对稳态电场分布的影响

取 $\varLambda = 5 . 3 9 \times 1 0 ^ { - 3 } \mathrm { V } / ( \Omega \cdot \mathrm { m } ^ { 2 } )$ ，活化能 $\varphi = \ 0 . 2 3 \mathrm { e V }$ 改变电场依赖系数 $B$ 值，仿真得到应力锥表面场强和XLPE绝缘界面切向场强分布与电场依赖系数 $B$ 的关系如图6所示。

由图6a可知，在所给的 $B$ 值范围内，其对应力锥表面场强影响相对较小。随着电场依赖系数 $B$ 值的增大，应力锥表面场强值总体减小，当$B \geqslant 1 . 5 0 \times 1 0 ^ { - 7 } \mathrm { m / V }$ 时，应力锥表面最大场强值位置由应力锥根部e点转移到了应力锥顶端f点。

![](images/be2b7538abd9f5632f5b674ee0fb95971786233ef34cd54546c1dd96417bd15b.jpg)  
图6不同 $B$ 值下稳态电场分布图  
Fig.6Diagram of steady electric field distribution under different $B$ values

由图6b可知，电场依赖系数 $B$ 对界面切向场强的分布总体影响不大。随着 $B$ 值的增大，电缆终端应力锥根部e点附近的界面切向场强值逐渐减小，增强绝缘端部h点附近的界面切向场强值先正向减小后反向增大。

综合图6a和图6b，当 $B$ 值介于 $( 1 . 5 0 \sim 6 . 0 0 ) \times$ $1 0 ^ { - 7 } \mathrm { m / V }$ 范围内时，最大界面切向场强值均小于$1 \mathrm { k V / m m }$ ，满足复合绝缘交界面的切向场强值控制要求。

# 3.3活化能 $\varphi$ 对稳态电场分布的影响

取材料系数 $\varLambda = 5 . 3 9 \times 1 0 ^ { - 3 } \mathrm { V } / ( \Omega \cdot \mathrm { m } ^ { 2 } )$ 、电场依赖系数 $B = 3 . 4 8 \times 1 0 ^ { - 7 } \mathrm { m / V }$ ，改变活化能 $\varphi$ 值，仿真得到应力锥表面场强和XLPE界面切向场强与活化能 $\varphi$ 的关系如图7所示。

由图7可知，活化能 $\varphi$ 值对电缆终端的应力锥和XLPE表面场界面切向场强影响很大。随着 $\varphi$ 值的减小，应力锥和XLPE表面场界面切向场强最大电场强度均减小。当 $\varphi = 0 . 2 3 \mathrm { e V }$ 时，h点附近的界面切向场强值接近于0；应力锥内表面最大电场控制在 $1 \mathrm { k V / m m }$ 以下。由此可见，增强绝缘材料电导活化能越低，应力锥表面场强和XLPE界面切向场强以及应力锥内表面电场越低。

![](images/60dde7f09b674ba20b2660739cebfd4cf63a5177051c8eaf94935b2f6af83e76.jpg)  
图7不同 $\varphi$ 值下稳态电场分布图

Fig.7 Diagram of steady electric field distribution under different $\varphi$ values

# 4结论

通过HVDC电缆终端稳态电场数值分析得出如下结论：

（1）HVDC电缆复合型终端结构中，工厂XLPE绝缘与应力锥增强绝缘界面切向场强有两个部位可能出现电场最大值，分别是应力锥根部和应力锥增强绝缘顶端部。

(2）HVDC电缆复合型终端结构中，半导电应力锥喇叭口内表面最大电场同样可能出现在两个部位，分别是喇叭口根部和顶部。

(3）通过调整应力锥体增强绝缘的非线性属性，可实现HVDC电缆终端电场分布的综合调控。

# 参考文献

[1]高本锋，张学伟，刘辛晔，等．高压直流输电保 护定值整定流程的研究[J]．电工技术学报，2015, 30(12): 400-407. Gao Benfeng,Zhang Xuewei,Liu Xinye,et al. Research of HVDC Protection Value Setting Process[J]. Transactions of China Electrotechnical Society,2015,30(12): 400-407.   
[2] 汤广福，罗湘，魏晓光．多端直流输电与直流电网 技术[J]．中国电机工程学报，2013，33(10)：8-17. Tang Guangfu, Luo Xiang, Wei Xiaoguang. Multiterminal HVDC and DC-grid Technology[J]. Proceedings of the CSEE, 2013,33(10): 8-17.   
[3] 温家良，吴锐，彭畅，等．直流电网在中国的应用 前景分析[J]．中国电机工程学报，2012，32(13): 7-12. Wen Jialiang, Wu Rui, Peng Chang, et al. Analysis of DC grid prospects in China[J]. Proceedings of the CSEE,2012,32(13): 7-12.   
[4] 周远翔，赵健康，刘睿，等．高压／超高压电力电 缆关键技术分析及展望[J]．高电压技术，2014, 40(9): 2593-2612. Zhou Yuanxiang, Zhao Jiankang, Liu Rui, et al. Key technical analysis and prospect of high voltage and extra-high voltage power cable[J]. High Voltage Engineering,2014, 40(9): 2593-2621.   
[5] 杨帆，杨旗，程鹏，等．电缆接头内部气隙放电 缺陷下的绝缘劣化程度表征方法[J]．电工技术学 报，2017，32(2)：24-32. Yang Fan, Yang Qi, Cheng Peng, et al. Study of cracking extent for gap discharge in insulating material of power cable joint[J]. Transactions of China Electrotechnical Society,2017,32(2): 24-32.   
[6] Xu Z, Choo W, Chen G.DC electric field distribution in planar dielectric in the presence of space charge[C]. IEEE International Conference on Solid Dielectrics, 2007: 514-517.   
[7] Ghorbani H, Jeroense M, Olsson C O,et al.HVDC cable systems—highlighting extruded technology[J]. IEEE Transactions on Power Delivery, 2014, 29(1): 414-421.   
[8]Eigner A, Semino S. 50 years of electrical-stress control in cable accessories[J]. IEEE Electrical Insuiation Magazine,∠Ul3,zy()): 4/-5).   
[9] Gramespacher H,Svahn J,Greuter F,et al. Microvaristor based field grading elements for HV terminations[C]. Proceedings of the XIIIth International Symposium on High Voltage Engineering, 2003: 147.   
[10]Jeroense M. HVDC,the next generation of transmission highlights with focus on extruded cable systems[C]. IEEE International Symposium on Electrical Insulating Materials,2008:10-15.   
[11]Donzel L,Greuter F,Christen T. Nonlinear resistive electric field grading part 2: materials and applications[J]. IEEE Electrical Insulation Magazine, 2011, 27(2): 18-29.   
[12]Fabiani D, Montanari G C, Laurent C,et al. Polymeric HVDC cable design and space charge accumulation. part 1: insulation/semicon interface[J]. IEEE Electrical Insulation Magazine,2007,23(6):11-19.   
[13]谢竟成，胡军，何金良，等．非线性复合材料对 不均匀电场的改善效果仿真分析[J]．高电压技术, 2014，40(3): 741-750. Xie Jingcheng,Hu Jun, He Jinliang,et al. Simulation analyse of modification effect of nonlinear composites on nonuniform electrical fields[J].High Voltage Engineering,2014, 40(3): 741-750.   
[14]胡军，赵孝磊，杨霄，等．非线性电导材料应力 锥改善电缆终端电场强度分布[J]．高电压技术， 2017，43(2):398-404. Hu Jun, Zhao Xiaolei, Yang Xiao,et al. Improving the electric field strength distribution of cable terminals by stress cone of nonlinear conductivity material[J]. High Voltage Engineering, 2017, 43(2): 398-404.   
[15]Boggs S, Damon D H, Hjerild J, et al. Effect of insulation properties on the field grading of solid dielectric DC cable[J].IEEE Transactions on Power Delivery,2001, 16(4): 456-461.   
[16]Blythe A R. Electrical properties of polymers [M]. Cambridge University Press,1986.   
[17]杨世铭，陶文钰．传热学[M]．4版．北京：高等 教育出版社，2006：44-45.   
[18]应启良．柔性直流输电系统用直流交联聚乙烯绝 缘电缆导体最高温度提高到 $9 0 \mathrm { { ^ circ C } }$ 的可行性[J]．电 线电缆，2014(3)：1-4. Ying Qiliang.Feasibility of raising the maximum conductor temperature to $9 0 \mathrm { ~ \textdegree ~ }$ ofDC XLPE cables with rated voltages up to $3 2 0 \mathrm { k V }$ for VSC system[J]. Electric Wire and Cable,2014(3):1-4.   
[19] 李昭红，阳林，田野，等．高压直流电缆接头稳 态温度场分布及其影响因素[J]．中国电力，2016, 48(2): 48-53. Li Zhaohong,Yang Lin,Tian Ye,et al. Steadystate temperature field ofHVDC cable joint and its influencing factors[J]. Electric Power, 2016,48(2): 48-53.   
[20] 尚康良，曹均正，赵志斌，等．320kVXLPE 高压 直流电缆接头附件仿真分析和结构优化设计[J]. 中国电机工程学报，2016，36(7)：2018-2024. Shang kangliang,Cao Junzheng,Zhao Zhibin,et al.Simulation analysis and design optimization of $3 2 0 \mathrm { k V }$ HVDC cable joint[J].Proceedings of the CSEE,2016,36(7): 2018-2024.   
[21] 顾金．柔性高压直流交联聚乙烯(XLPE)电缆及其 附件的设计研究[D]．上海：上海交通大学，2010.   
[22] Christen T,DonzelL,GreuterF.Nonlinearresistive electric field grading part 1: theory and simulation[J]. IEEE Electrical Insulation Magazine,2010,26(6): 47-59.   
[23] Ross R.Dealing with interface problems in polymer cable terminations[J].IEEE Electrical Insulation Magazine, 1999,15(4): 5-9.   
[24] 李忠华，刘乐乐，郑欢，等．HVDC电缆电场分 布影响因素的仿真研究[J]．中国电机工程学报， 2016,36(9): 2563-2571. Li Zhonghua，Liu Lele，Zheng Huan,et al.Simulation on the influence factors of electric fielddistribution in HVDC cable[J].Proceedings of the CSEE,2016,36(9):2563-2571.