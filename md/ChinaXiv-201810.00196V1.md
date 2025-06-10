# 基于FDM与FBG技术的路基小变形监测研究

杨语尧」洪成雨²汪磊

(1．上海工程技术大学城市轨道交通学院，上海 201600 2.上海大学土木工程系，上海 200444)

[摘要]本研究从铁路路基健康监测出发，基于FDM(Fused Deposition Modeling)与FBG(Fiber BraggGrating)技术开发了路基小变形监测系统。利用FDM技术和FBG传感技术设计带封装和锚固板的FBG传感器监测模型，标定试验可得荷载与土体位移的关系，结果表明：位移与荷载呈良好的线性关系，相关系数达到0.99，标试验测得最大位移为 $0 . 2 5 \mathrm { m m }$ ，最小位移为 $0 . 0 5 \mathrm { m m }$ ，传感器灵敏度达到$4 \mathrm { n m / m m }$ ，最小分辨率达到 $0 . 6 2 ~ { \mu \mathrm { m } }$ 。通过两种试验工况检验传感器可行性，包括监测路基在静、动载作用下的位移变化，静荷载作用下监测数据表明：波长及位移随时间呈阶梯性增长，试验成功采集路基的最小位移达到 $0 . 0 0 4 \mathrm { m m }$ 。动荷载监测试验结果表明传感器可以快速反映车辆模型荷载产生的竖向压力。

[关键词]FBG传感器；FDM技术；路基；位移；健康监测

# 1引言

随着国家综合国力的提升，土木工程得到很好的发展，对其的健康监测也受到重视。在桥梁、隧道等土木工程或模拟试验中，常需要监测关键部位的位移变化情况，更准确地评价桥梁、隧道的安全性能及损伤程度[1-3]。路基微观位移不及时得到控制，不仅影响结构美观，更危及结构安全，因此，对路基位移的健康监测是当今应重点研究的问题。吕聪儒[4]等使用埋入式激光沉降仪测量法对路基沉降测量研究，沉降仪操作方便，精度高；闫宏业[5]等提出了一种新型实用的装配式分层沉降观测装置，观测装置精度较高且稳定。在众多方法中，传感器因其施工简便、体积小、测量范围可调等特点逐渐被广泛使用。

光纤传感技术始于1977年，距今已有三十多年的发展经历。光纤技术不仅在很多行业得到良好的发展，也成为衡量一个国家信息化的重要指标之一。目前常用的传感器有电子传感器，电阻传感器和光学传感器等。李光伟等利用电容式加速传感器监测路基位移[6]，电容式传感器具有温度稳定性好，结构简单等特点；张斌等[7]利用霍尔电磁传感器对路基横向剖面沉降测量分析，霍尔传感器具有灵敏度高，体积小等特点。但由于路基暴露在自然环境下，电子传感器易受天气影响和电磁干扰，霍尔传感器互换性差，信号随温度变化，非线性输出，因此作为光敏传感器的布拉格光纤光栅传感器因其体积小，抗磁干扰能力强，传输损耗小等优点，在能源，环保，工业等领域有着广泛应用[8-11]。

本研究结合熔融沉积式技术对布拉格光纤光栅传感器封装保护固定，结合当前我国路基情况，模拟列车实际运行，铺设路基模型，埋设传感器于轨道路基内部，对土体小变形进行监测研究。

# 2新型的FBG位移传感器

# 2.1 FiberBraggGrating (FBG)传感技术工作原理

FiberBraggGrating(FBG)传感器是应用较为广泛的传感器之一。FBG传感器即布拉格光纤光栅传感器，光纤光栅是一种新型智能传感元件[12]。属于波长调制型非线性作用的光纤传感器[13]。FBG 传感器由光纤和光栅组成，光纤是由玻璃或塑料构成的一种纤维。图1为光纤结构内部图，从内部到外部由三部分组成：纤芯，包层和涂覆层。

![](images/2685cd36c1ef97c6b0aa5da006b9825c2097121fd924fa4ee45e7466be8340be.jpg)  
图1光纤结构内部图

FBG传感器的工作原理是：当一定带宽的光源进入到FBG传感器中时，一部分光发生反射，一部分发生透射，反射光波返回耦合器并通过耦合器进入光纤光栅解调仪装置，光纤光栅解调仪接收信号，测得波长 $\lambda _ { \beta }$ 的变化。图2为传感器原理图。 $\lambda _ { \beta }$ 与纤芯折射率 $\mathfrak { n }$ 和光栅周期∧有关。即：

$$
\lambda _ { \beta } = 2 \mathrm { n } \lambda
$$

式中： $\mathfrak { n }$ 为纤芯折射率， $\Lambda$ 为光栅周期。

![](images/4ed4fc85f97947479ca1118245ed5776dbdc65e7263db2bbc46b950627ddb168.jpg)  
图2传感器原理图

当压力变化时，FBG传感器光栅周期 $\Lambda$ 发生变化$\triangle \Lambda$ ，反射波长 $\lambda _ { \mathrm { { \beta } } }$ 增大，忽略温度变化，光纤光栅轴向应变引起波长变化为：

$$
\Delta \lambda _ { \beta } = \lambda _ { \beta } \left( 1 - P _ { e } \right) \varepsilon = K _ { e } \varepsilon
$$

式中： $\mathrm { \Delta P _ { e } }$ 为纤芯有效光弹系数，取0.22， $\mathrm { K _ { e } }$ 为测量应变的灵敏度，多数FBG传感器的中心波长从约 $1 5 2 0 ~ \mathrm { n m }$ 变化至约 $1 5 7 0 \mathrm { n m }$ 。

# 2.2新型位移传感器的设计与制作

FusedDeposition Modeling(FDM)即 熔融沉积式技术，是3D打印技术中的一种，以数字模型文件为基础快速打印成形。FDM技术工作原理为：在高温下，丝状热熔材料在喷头处加热熔化，根据型号的配置信息，打印机喷嘴将材料通过设计的模型尺寸施加到工作台上，通过喷头沿零件截面运动，将融化的材料挤出，材料迅速凝固，形成一层后，机台下降一个高度（即分层厚度），然后施加下一层，直到打印机的喷嘴成形为实心。材料通常采用热塑性材料，如蜡、尼龙、AcrylonitrileButadiene Styrene(ABS)、Polylactice Acid(PLA)等，本试验使用FINDER3D打印机，打印精度为100 微米，打印量为410立方英寸，本试验采用的是PLA材料。图3为3D打印机打印锚固板。

![](images/b673df62d4b87f312fc9c2de2cbbd8b31cc0c64cfcb4d1f98ed8786e438ba821.jpg)  
图3FDM技术打印锚固板

新型的FBG位移传感器由两个锚固板和一个长标距传感器组成，锚固板的直径为 $6 0 \mathrm { m m }$ ，厚度为 $4 \mathrm { m m }$ 。长标距传感器由透明的PVC（Polyvinylchloride）外包层（直径 $2 \mathrm { m m }$ ）和内部隔离的FBG传感器组成，长度为 $1 0 0 \mathrm { m m }$ ，传感器末端与铠装跳线相连作为保护。图4为基于FDM与FBG技术设计的新型位移传感器，利用CATIA软件设计锚固板，在圆心预留孔道，由于FBG传感器受压易破坏和路基环境的复杂性，FBG传感器全长度需加PVC保护，利用FDM技术将封装好的FBG传感器打印于锚固板圆心处。监测试验直接将FBG传感器埋置于土体内部，当荷载作用于土体时，锚固板受到土体挤压，引起FBG压缩或者拉伸，中心波长发生

变化。

![](images/b7e77c18d85d033055497b9fb9f22ec94cb56fb80e4025ab379cb554bcd683d1.jpg)  
图4新型FBG位移传感器

# 2.3标定试验

标定试验在恒温的试验室进行，将FBG位移传感器一端固定，另一端采用步进式加载，每次加载 $2 0 \mathrm { g }$ 时间间隔为 $2 0 ~ \mathrm { s }$ ，共加载3次，然后依次卸载，记录每次加卸载的传感器波长与位移变化。

选取两个传感器分析波长与位移之间的关系，如图5所示，为传感器位移与波长关系图，拟合可得中心波长与位移的对应关系分别为 $\mathrm { y } = 3 . 9 8 2 \mathrm { x } + 1 5 3 1 . 5$ ，$\mathrm { y } { = } 4 . 0 2 7 4 \mathrm { x } { + } 1 5 4 9$ ，因此传感器的灵敏度分别为3.982$\mathrm { { n m / m m } }$ ， $4 . 0 2 7 4 \mathrm { n m / m m }$ ，由于光栅解调仪精度为0.0025$\mathrm { n m }$ ，求得传感器1，4分辨率均为 $0 . 6 2 \mu \mathrm { m }$ 。

![](images/9b96b90fab12adb23de277d36423b41c4baca10469831a011c4edbbcdc12b7ae.jpg)  
图5传感器位移与波长关系图

图6所示为标定试验中FBG传感器位移和荷载变化关系图，标定试验得到位移与荷载关系，试验结果表明：随着荷载的增加，传感器位移线性增大，相关系数最高达到0.99，线性度理想，标定试验测得最小位移为$0 . 0 5 \mathrm { m m }$ ，最大测量范围达到 $0 . 2 5 \mathrm { m m }$ 。标定试验中，由于新型FBG传感器锚固端尚未固定，因此FBG传感器受到较大拉力，位移也较大。

![](images/18853da3b4cc18e9e3b86b51e3bddae0c15b747dfb882c7e31487869ac0a8e28.jpg)  
图6传感器荷载与位移关系

# 3路基监测模型

# 3.1路基模型的建立

试验所需模型箱采用亚克力模型箱，尺寸为70$\mathtt { c m } { \times } 5 0 \mathtt { c m } { \times } 5 0 \mathtt { c m }$ 。路基模型如图7所示，包括：传感器、路基、缆线。路基采用标准砂铺设，路基模型长 $7 0 \mathrm { c m }$ 路面宽度为 $1 2 \mathrm { c m }$ 。路基采用1:1的坡度，坡长，坡高均为 $9 \mathrm { c m }$ 。标准砂的参数如表1所示。

![](images/5e26cf5c225f4ab146519e116273e1a5a060dc58434a84580a2530fda2ec1c2c.jpg)  
图7路基模型与监测传感器的布设

表1标准砂参数  
  

<html><body><table><tr><td colspan="7">TableTStandardsandparameters</td></tr><tr><td>参数</td><td>重度 /kN.m²</td><td>弹性模量 /kPa</td><td>泊松比</td><td>摩擦角 /0</td><td>粘聚力 /kPa</td><td>压实度 /%</td></tr><tr><td>标准</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>砂</td><td>18.5</td><td>20000</td><td>0.35</td><td>31.8</td><td>0</td><td>80</td></tr></table></body></html>

# 3.2传感器布设

4个FBG位移传感器布设于路基模型中部，具体位置如图8所示。相邻传感器间距为 $1 7 \mathrm { c m }$ ，两端位移传感器距模型箱壁的距离为 $9 . 5 \mathrm { c m }$ 。四个位移传感器从左至右编号分别为1#， $2 \#$ ，3#，4#，相应的初始波长分别为 $1 5 3 6 \mathrm { n m }$ 、 $1 5 3 2 \mathrm { n m }$ 、 $1 5 4 4 \mathrm { n m }$ 和 $1 5 5 2 \mathrm { n m }$ 。待传感器埋设完成，在FBG传感器上覆盖 $4 0 \mathrm { m m }$ 标准砂，并铺设轨道板。路基横断面尺寸及FBG位置见图9。

![](images/e3b1f07cc638da59cd91473dd9ca6a32993e8f8054387d48a1870c55d03f2dac.jpg)  
图8FBG传感器位置示意图

![](images/a1353e5485481d70b10f7fd81478f84c5c8991633699c03a7de804e3f07b5e61.jpg)  
图9路基横断面尺寸及FBG位置示意图（单位：cm）

# 3.3路基监测试验

路基监测试验平台，包括路基位移监测端，无线信号采集端，光栅解调仪和信号接收端。图10所示为本试验搭建好的路基监测平台，当路基受到荷载，FBG传感器波长发生变化，通过无线信号采集端将信号无线传入信号接收端，光栅解调仪监测波长。

![](images/a2151c93b2e6fd6105ceca5bf408666c3b11b1f180e98abab1ce18eb90ef98a8.jpg)  
图10路基监测试验平台的简历

试验数据采集所用的光纤光栅解调仪具有扫描范围广，分辨率高的特点，可长期高精度监测温度、应变、压力、位移和加速度等物理量。所用解调仪可允许在一根光纤上同时连接大于40个FBG传感器，也可随时扩展到32个光学通道。本次路基位移监测试验采用两种工况，用不同重量砝码模拟车辆荷载作用。不同工况如下：

工况1：模拟静荷载作用。加载范围为 $1 { - } 5 \mathrm { k g }$ ，采用步进式加载，逐次加载，每次 $1 \mathrm { k g }$ ，采集频率为每20s加载一次。

工况2：模拟动荷载作用。列车以 $0 . 0 0 1 \mathrm { m / s }$ 的速度匀速运行，方向为从传感器1#至传感器4#，加载范围为 $1 { - } 5 \mathrm { k g }$ 。

土体内部FBG传感器受力图如图11，荷载作用下，土体变形，锚固板受到土体挤压，并对光纤产生轴力作用，应力应变关系如下，

$$
\mathcal { E } y = \sigma { _ y } / E _ { y }
$$

根据泊松比可知：

$$
\mathbf { v } = - \varepsilon _ { \mathrm { x } } / \varepsilon _ { y }
$$

由胡克定律可得：

$$
\mathcal { E } \mathrm { x } = - \nu \mathcal { E } y
$$

由（2）得波长与竖向应力关系为：

$$
\frac { \Delta \lambda _ { \beta } } { \lambda _ { \beta } } { = } _ { - \upsilon \mathcal { E } y } ( 1 - P _ { e } )
$$

![](images/6fed5373d13c4a39bee098f5cd173dd8c2565b0c3f4d1e67715137b7adb7d426.jpg)  
图11 土体内部FBG传感器受力图  
图11不同传感器时间与波长及位移关系图

# 4监测结果与讨论

图11为4个FBG传感器波长及位移随时间变化的关系图。试验结果表明，传感器波长随时间的变化呈现阶梯型增长，传感器初始增长量分别为： $0 . 0 5 \mathrm { n m }$ ，0.04$\mathrm { n m }$ ， $0 . 0 6 \mathrm { n m }$ ， $0 . 0 4 \mathrm { n m }$ ，最大增长量分别为： $0 . 2 5 \mathrm { n m }$ ，$0 . 1 4 \mathrm { n m }$ ， $0 . 2 1 ~ \mathrm { n m }$ ， $0 . 2 4 ~ \mathrm { n m }$ ，增长量呈线性增加，四个传感器位移最小值可达 $0 . 0 0 4 \mathrm { m m }$ ，最大值可达 $0 . 0 1 9 \mathrm { m m }$ 监测数据结果表明FBG具有很高的灵敏性。同时，随着时间的增大，位移呈现阶梯式增大，且增长越来越快。加载过程中，位移发生突变，无加载时，位移值稳定。

1537800 0.080 1537000 0波长位移 pgm 0.070 0.060 1537500   
3 0.050 mmmo   
1537200 e 0.030 1537100 0.020 1537000 1536900 @ mmb 0.010 1536800 0.000 20 40 60 80 100 120 时间(s) (a) 1532050 0.040 1552000 0一波长位移 80.035 1531900 0.030 1531850 0.025 1531800 0.020   
153150 mm 0.015 建码 1531650 1531600 ymmmtm 0.010 1531550 0.005 1531500 0.000 20 40 60 80 100 120 时间（s) (b) 1545600 0.070 1545500 一波长位移 0.060 1545400 0.050   
1 eu 1545000 0.020 1544900 1544800 I 0.010 1544700 0.000 20 40 60 8 100 120 时间(s) (c) 1553900 0.070 1553800 波长位移 mm 0.060 1553700 0.050 1553600 155300 1553400 1553300 0.020 1553200 1553100 0.010 1553000 0.000 20 40 60 80 100 120 时间（s) (d)

研究中只考虑2#号传感器的监测结果作为分析对象，图12为 $2 \#$ 号传感器在 $\mathbf { \sigma } _ { 1 - 5 } \exp \mathbf { \varepsilon } _ { \mathrm { \mathbf { k g } } }$ 动荷载作用下传感器位移随时间的变化关系图。图12(a)为在 $1 \mathrm { k g }$ 荷载作用下，传感器2#位移随时间的变化。可以看出，传感器波长在25s时突变，在30s时位移增大至 $0 . 0 0 3 \mathrm { m m }$ ，列车在经过传感器2#后，土体恢复原来状态，即发生弹性变形。图(b)、(c)、(d)和(e)分别为传感器 2#在 $2 \mathrm { k g }$ ， $3 \mathrm { k g }$ $4 \mathrm { k g }$ 和 $5 \mathrm { k g }$ 荷载作用下位移的变化图，传感器波长均在

30s时达到最大，分别为： $0 . 0 0 7 2 \mathrm { m m }$ ， $0 . 0 1 6 \mathrm { m m }$ ，0.017$\mathbf { m } \mathbf { m }$ 和 $0 . 0 2 1 \mathrm { m m } , \cdot$ ，且列车在经过传感器2后，土体没有恢复原来的状态，即发生塑性变形，残余变形与峰值变形的比值分别为： $34 \%$ ， $3 5 \%$ ， $3 8 \%$ 和 $3 7 \%$ 。动荷载试验中，监测到最小位移 $0 . 0 0 3 \mathrm { m m }$ ，最大位移达0.021mm，且相同的时间发生相同的峰值、残余变形比近似相同。监测结果表明FBG传感器具有高的灵敏度，能够监测动荷载作用下路基小变形，且从监测结果能够判断土体是否发生塑性变形和变形程度。在实际应用中，不仅可以实时监测土体变形情况，还可根据峰值统计某段路面通过不同种类列车的数量。

![](images/4ca2ccd0e0bf84b6dc6149e9bdbef5be9e8a368c4f4b4dd1b9ed102d8c975a76.jpg)  
图12路基在动荷载作用下时间与位移关系图

# 5结论与建议

针对用FBG传感器对路基健康监测的客观需求，设计了带锚固板的新型FBG位移传感器，围绕FBG传感器在不同工况下展开研究，得出以下结论：

（1）该试验基于FDM技术和FBG技术成功设计路基位移监测系统。该监测系统具有以下优点：PVC保护管有效保护FBG传感器；利用FDM技术和PLA材料快速打印锚固板，用于固定FBG传感器；保护裸光纤不被破损，更好的发挥FBG传感器的性能。

（2）标定试验结果表明，新型FBG位移传感器监测最大位移 $0 . 2 5 \mathrm { m m }$ ，最小位移为 $0 . 0 4 ~ \mathrm { m m }$ 。荷载与位移符合线性关系，相关系数达到0.99，线性良好，传感器灵敏度 $4 \mathrm { n m / m m }$ ，分辨率 $0 . 6 2 ~ { \mu \mathrm { m } }$ 。

（3）静荷载监测结果表明：FBG传感器成功监测最小位移 $0 . 0 0 5 \mathrm { m m }$ ，测量精度高，利用新型FBG位移传感器可测量小变形；动荷载监测结果表明：传感器可以快速地反映车辆模型荷载产生的竖向压力，FBG传感器成功监测最小位移 $0 . 0 0 3 \mathrm { m m }$ ，最大位移达 $0 . 0 2 1 \mathrm { m m }$ 且列车经过传感器时，传感器波长突变，FBG传感器具有高的灵敏性。小荷载作用下，土体发生弹性变形，位移可恢复初始状态，大荷载作用下，土体应变有残留，变形比达到 $3 8 \%$ ，土体产生塑性变形。

由于该试验工况和试验次数的有限性，仍有不足之处需要改进。后续会根据情况，添加工况和研究范围，如研究路基沉降，表面变形等。

# [参考文献]

[1] Wonseok CHUNG,Donghoon KANG.Full-scale test of aconcrete box girder using FBG sensing[J]. EngineeningStructures,2008,30: 643-652.  
[2] 肖裕民，黄仁富.隧道围岩体内位移监测分析[J].西部交通科技，2009,28(10):93-96.  
[3] 陈伟民.大跨径拱桥多维位移的光电组合监测技术研究[D].重庆：重庆大学，2008.  
[4] 吕聪儒，楼云，张鹏.埋入式激光沉降仪测量法及工程应用[J]．水利水电科技进展,2014,34(S2):42-44.34(S2): 42-44.  
[5] 闫宏业，蔡德钩，姚建平，等．装配式分层沉降观测装置在路基沉降观测中的应用[J]．铁道建筑,2008(6):83-85.  
[6] 李光伟，董林玺.基于MEMS加速度传感器的位移检测系统[J].传感器与微系统，2014,(7):79-81.  
[7] 张斌，冯其波，杨靖，等．路基沉降远程自动监测系统的研发[J]．中国铁道科学,2012,33(1):139-144.  
[8] 梁敏富，方新秋，薛广哲，等．光纤光栅测力锚杆的标定试验[J].煤矿安全,2015,46(1):44—46.  
[9] 李伟，李川．双悬臂梁式光纤Bragg 光栅位移传感器[J].微计算机信息，2011,27(9):52-53.  
[10] 丁腾蛟.基于悬臂结构的大量程光纤Bragg光栅位移传感器[D].武汉:武汉理工大学,2012.  
[11] 尹兴彬，马伟宏，曹 慧，等．一种高精度光纤光栅位移传感器设计研究[J]．科技信息,2012(6):170--171.

[12]LI Hongnan,LI Dongsheng and WANG Suyan. Study and application of health monitoring by fiber optic sensors in civil engineering[A],ASME,Pressure Vessels and Piping Division, 2003,468:217-224.

# Study on Measurement Method of Small Deformation of Embankment Based on FDM and FBG Technology

YANG Yuyao1, HONG Chengyu², WANGLei1

(1.ColegeofUrbanRailTansit,ShangaiUniversityOfEngieringSciene,Shangai6oo,ChinaDepartmentofCivilEiing Shanghai University， Shanghai 200444, China)

[Abstract]Basedontherailwayembankmenthealthmonitoring,thisstudydevelopedaembankmentsmalldeformationmonitoringsystem basedonFDM(FusedDepositionModeling)andFBG(FiberBraggGrating)technology.UsingFDMtechnologyandFBGsensingtechology todesigtheFGsensormonitoringmodelwithpackageandanchorplate,therelationshipetweeladandsoildisplacementcanbebtaind bycalibrationtestultssohattisplacetasgodearelatiosipiteladndthelaiocctac 0.99.The test measured a maximum displacement of $0 . 2 5 ~ \mathrm { m m }$ ,a minimum displacement of $0 . 0 5 ~ \mathrm { { m m } }$ ，a sensor sensitivity of $4 \ \mathrm { n m / m m }$ and a minimum resolution of $0 . 6 2 ~ { \mu \mathrm { m } }$ .The feasibilityof the sensor is tested by two test conditions,including monitoring the displacement of the embankmentunderstaticanddynamicloads.Themonitoringdataunderstaticloadshowsthatthewavelengthanddisplacementincrease stepwise with time,and the minimum displacement of the embankment is successfully colected.It reaches $0 . 0 0 4 \ \mathrm { m m }$ .The dynamic load monitoring test results show that thesensor can quickly reflectthe vertical pressure generated bythe vehicle model load.

[Key words] FBG sensor; FDM; embankment; displacement; health monitoring