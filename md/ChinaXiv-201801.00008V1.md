# 玉米籽粒的传质干燥模拟及实验分析

黄凯 陈兴付 陈鹏枭 王凤贺 涂广 赵宇 刘相东 杨德勇

(中国农业大学工学院,北京 100083)

摘要：为了解干燥过程中玉米籽粒内部水分的扩散过程，优化干燥工艺参数，本文采用模拟研究和实验研究方法分析干燥过程中玉米籽粒内部水分分布随时间的变化规律。玉米籽粒由种皮、角质胚乳、粉质胚乳和胚四组分组成，四种组分水分扩散系数各不相同，本文分别假设玉米籽粒由单组分均质体和多组分非均质体组成，分别建立了玉米籽粒的干燥数学模型，利用COMSOLMultiphysics模块模拟研究了玉米籽粒内部的水分变化情况，并通过玉米籽粒的薄层干燥实验进行了实验验证。研究结果表明，建立的两个模型均可有效模拟玉米籽粒薄层干燥过程； $8 0 ^ { \circ } \mathrm { C }$ 的模拟值与实验值的差异较 $7 0 ^ { \circ } \mathrm { C }$ 的小；玉米籽粒多组分模型精度优于单组分模型精度。

关键词：玉米籽粒；多组分；单组分；薄层干燥；质量传递中图分类号：TH432 文献标识码：A

# Simulation and Experimental Analysis of Mass Transfer in Drying a Single Corn Kernel

HUANG KaiCHEN Xing-Fu CHEN Peng-XiaoWANG Feng-He TU GuangZHAO Yu LIU Xiang-DongYANG De-Yong (College of Engineering, China Agricultural University,Beijing 1ooo83, China)

Abstract: To study the moisture diffusion of a single corn kernel during drying,and to optimize the drying parameters,the moisture content distribution in the corn kernel over time was researched by the methods of simulation and experimental analysis. Corn kernel consists of four components of seed coat, horny endosperm, farinaceous endosperm and embryo,all of whose diffusion coeffcient differ. Then two hypotheses are proposed: one is that the corn kernel consists of isotropic monocomponent; the other is that the corn kernel consists of multicomponent described above. Based on the hypotheses,different drying mathematical models of a single corn kernel were built,and solved by the software of COMSOL Multiphysics for mass transfer. Thin layer drying experiment of the corn kernel was conducted to validate the models.The simulation and experimental results indicated that both of the models could explain the drying process of corn kernel well. The difference between simulation and experimental results under $8 0 ^ { \circ } \mathrm { C }$ is smaller than that of $7 0 ^ { \circ } \mathrm { C }$ . And the simulation precision of multicomponent model is better than that of monocomponent model.

Key words: corn kernel; multicomponent； monocomponent; thin layer drying； mass transfer

# 0引言

合理的干燥工艺对于干燥行业至关重要，就玉米而言，干燥工艺会影响玉米开裂率，储藏时间以及总体产品质量[1]，同时还会造成能源浪费。目前，越来越多的干燥工艺，可以通过模型模拟[2,3]，再进行一定的实验以检验模型，最后调整模型以改善干燥工艺，达到提升产品质量和节能减排的目的。

玉米籽粒形状不规则，组织结构较为复杂，在不同干燥阶段不同截面处的水分分布各不相同。通过核磁共振、CT扫描等技术手段只能确定某个时刻某个截面处的水分分布[4,5]。水分在不同籽粒结构中的扩散速度不同，决定了将玉米分层分析的必要性。Takhar考虑了玉米籽粒的不均匀性，研究了玉米不同成分的扩散系数[]。干燥过程中，玉米不同组分的质地不一样，则不同组分的水分扩散速度也不一样。同时，籽粒内部的水分梯度与籽粒内部结构息息相关，其内部结构可以看作种皮、角质胚乳、粉质胚乳和胚四部分组成的组合体[8,9]，其扩散系数各不相同，而这都与籽粒的温度和水分含量有关。Chen根据玉米复杂结构，将每个组分分离开来，分别测得了它们的干燥曲线，通过运用COMSOLMultiphysics对菲克第二定律进行求解，得出了不同成分的扩散系数与干燥温度和含水率的关系，为本文玉米扩散系数的选择提供了理论依据。张世伟[10,11]根据热风条件下的玉米籽粒内部传热传质过程，对三维模型进行了理论分析与模拟研究。通过医用CT扫描了玉米籽粒，将扫描得到的高精度图片通过MIMICS和ANSYS软件优化后，建立了玉米籽粒的三维几何模型，再导入COMSOLMultiphysics模拟软件中完成求解计算。这种方法可以用于更好地描述玉米籽粒内部的质量传递过程和水分随干燥过程的变化情况。所以，本文拟通过构造多组分与单组分玉米籽粒结构的物理模型，通过COMSOLMultiphysics模拟与薄层干燥实验进行对比分析，以检验玉米籽粒不同组分模型的模拟精度。

# 1干燥传质模型

# 1.1玉米籽粒物理模型

# 1.1.1多组分几何模型

假设玉米籽粒在宽度方向上结构对称，因此只需计算玉米籽粒的二分之一即可，其物理模型如图1所示。其中玉米籽粒的四部分体积如表1所示。

型如图2所示。取玉米籽粒重心为坐标原点， $x$ 轴、$y$ 轴分别代表玉米籽粒的宽度和厚度方向。

![](images/7c12b022a71a31ee187782a273a71321df4851a8701a0cf58eafa5ca161c0474.jpg)  
图2四分之一玉米籽粒物理模型  
Fig.2Aquarterofcornkernel physical model   
图1PRO/E构建的玉米种皮、角质胚乳、粉质胚乳、胚 Fig.1 Seed coat,horny endosperm, farinaceous endosperm, embryo of corn kernel constructed by PRO/E

其中，玉米籽粒的多组分几何模型与玉米籽粒的单组分几何模型总体尺寸一样。

# 1.2热风干燥数学模型

# 1.2.1多组分玉米籽粒的热风干燥数学模型

干燥模型假设：1)干燥初期，玉米籽粒内部温度和水分分布均匀；2)不考虑干燥过程中玉米籽粒的收缩变形；3)玉米籽粒各组成部分分别为各向同性的均匀体；4)水分以液态形式扩散到外部边界，在玉米籽粒表面汽化。

干燥过程中，籽粒内部的传质方程描述为：

DD1

$$
\frac { \partial X } { \partial t } = \frac { \partial } { \partial x } \Bigg ( D _ { i } \frac { \partial X } { \partial x } \Bigg ) + \frac { \partial } { \partial y } \Bigg ( D _ { i } \frac { \partial X } { \partial y } \Bigg ) + \frac { \partial } { \partial z } ( D _ { i } \frac { \partial X } { \partial z } )
$$

$$
t = 0 \ , X = X _ { 0 }
$$

$$
- D \frac { \hat { \sigma } X } { \hat { \sigma } n } = h _ { m } ( X - X _ { e } )
$$

表1玉米粒四组分体积  
Table 1 Four components volume of corn kernel   

<html><body><table><tr><td></td><td>种皮</td><td>角质胚乳</td><td>粉质胚乳</td><td>胚</td></tr><tr><td>体积/mm</td><td>5.8</td><td>137.3</td><td>63.7</td><td>26.5</td></tr><tr><td>体积含量比</td><td>2.5%</td><td>68.3%</td><td>31.7%</td><td>11.4%</td></tr></table></body></html>

干燥初始条件为：

边界条件为：

$$
h _ { _ { m } } = { \frac { S h D _ { _ a } } { d } }
$$

# 1.1.2单组分几何模型

假设玉米籽粒在宽度、厚度方向上结构对称，因此只需计算玉米籽粒的四分之一即可，其物理模

式中： $t$ 为干燥时间，s； $X$ 为玉米干基水分含量， $\mathrm { k g / k g } ; h _ { m }$ 为对流传质系数， $\mathrm { m } / { \mathrm { s } } ; S h$ 为 Sherwood数； $d$ 为等效粒径， $\mathrm { m m }$ $X _ { e }$ 为平衡水分含量， $\mathrm { { k g / k g } }$ $D _ { i }$ 为玉米不同组分的水分有效扩散系数， $i { = } 1 , 2 , 3$ ，4， $\mathrm { m } ^ { 2 } / \mathrm { s }$ 。

# 1.2.2单组分玉米籽粒的热风干燥数学模型

干燥模型假设：1)干燥初期，玉米籽粒内部温度和水分分布均匀；2)不考虑干燥过程中玉米籽粒的收缩变形；3)玉米籽粒为各向同性的均匀体；4)水分以液态形式扩散到外部边界，在玉米籽粒表面汽化。干燥初始条件、边界条件与1.2.1一致。

干燥过程中，籽粒内部的传质方程描述为：

$$
\frac { \partial X } { \partial t } { = } \nabla \cdot \left( D \nabla X \right)
$$

式中： $D$ 为水分有效扩散系数， $\mathrm { m } ^ { 2 } / \mathrm { s }$ 。

# 1.2.3玉米籽粒的热风干燥传热数学模型

干燥过程中，籽粒内部的传热方程描述为：

$$
\frac { \partial T } { \partial t } = \frac { \hat { \sigma } } { \hat { \sigma } x } \Bigg ( k \frac { \hat { \sigma } T } { \hat { \sigma } x } \Bigg ) + \frac { \hat { \sigma } } { \hat { \sigma } y } \Bigg ( k \frac { \hat { \sigma } T } { \hat { \sigma } y } \Bigg ) + \frac { \hat { \sigma } } { \hat { \sigma } z } \Bigg ( k \frac { \hat { \sigma } T } { \hat { \sigma } z } \Bigg )
$$

干燥初始条件为：

$$
t = 0 , T = T _ { 0 }
$$

边界条件为：

$$
- k \left( \frac { \hat { \sigma } T } { \hat { \sigma } n } \right) = h _ { t } \left( T _ { e } - T _ { 0 } \right) + \rho [ h _ { f g } + C _ { p } ( T - T _ { e } ) ] \frac { V } { A } \frac { \hat { \sigma } X } { \hat { \sigma } t }
$$

式中： $T$ 为玉米籽粒温度，K； $T _ { 0 }$ 为玉米籽粒初始温度， $\mathrm { \Delta K }$ ； $T _ { e }$ 为热风温度， $\mathrm { \Delta K }$ ; $k$ 为玉米籽粒的导热系数， ${ \bf W } / ( { \bf m } { \cdot } { \bf K } )$ ； $\frac { \partial T } { \partial n }$ 为籽粒内部温度 $T$ 沿外法线 $n$ 的导数； $h _ { t }$ 为对流传热系数， $\mathrm { W } / ( \mathrm { m } ^ { 2 } { \cdot } \mathrm { K } )$ ；玉米籽粒的比热容 $C _ { p } { = } 2 0 1 0 \mathrm { J / ( k g { . } K ) }$ [12]；玉米籽粒密度 $\scriptstyle \rho = 1 1 5 0$ $\mathrm { k g / m } ^ { 3 [ 1 3 ] }$ 广， $h _ { f g }$ 为玉米籽粒的汽化潜热， $\mathrm { J / k g }$ ）： $V$ 为玉米籽粒的体积， $\mathrm { m } ^ { 3 }$ ： $A$ 为玉米籽粒的表面积， $\mathrm { m } ^ { 2 }$ 。

# 2实验材料与方法

# 2.1实验材料

玉米(德美亚1号)，无破损、霉变粒，色泽气味正常。收获时初始含水率 $0 . 3 8 { \pm } 0 . 0 2$ (d.b.) $\mathrm { { k g / k g } }$ 收获后装入密封袋，储藏在冰箱中 $( 5 \pm 1 ) ^ { \circ } \mathrm { C }$ ，待实验前取出凉至室温。

# 2.2主要实验装置

数字型洞道干燥实验装置(浙江中控科教仪器设备有限公司)：鼓风机(BYF7122)额定功率 $3 7 0 \mathrm { W }$ ；电加热器额定功率 $4 . 5 \mathrm { k W }$ ；干燥室尺寸为$1 8 0 \mathrm { m m } { \times } 1 8 0 \mathrm { m m } { \times } 1 2 5 0 \mathrm { m m }$ ；称重传感器为CZ500型，$0 { \sim } 3 0 0 \mathrm { g }$ 。

其他仪器设备：DHG-9140A电热恒温鼓风干燥箱(上海精宏实验设备有限公司),FB224电子天平(上海舜宇恒平科学仪器有限公司)，HM70 温湿度仪(芬兰Vaisala 公司)。

# 2.3实验方法

# 2.3.1玉米籽粒热风薄层干燥实验

设置干燥实验条件：干燥初期籽粒内部水分、温度分布均匀，以玉米初始含水率 $3 9 . 3 3 \% \mathrm { ( d . b . ) }$ ，初始表面温度 $2 5 \mathrm { { ^ \circ C } }$ ，干燥风温 $7 0 ^ { \circ } \mathrm { C }$ 以及 $8 0 ^ { \circ } \mathrm { C }$ (薄层干燥实验发现，热风温度越高，玉米籽粒的干燥速率越快，但并非温度越高干燥效果越好[14]，因而本文选取 $7 0 ^ { \circ } \mathrm { C }$ 和 $8 0 ^ { \circ } \mathrm { C }$ 作为热风温度)，风速 $1 . 2 \ \mathrm { m / s }$ ，空气相对湿度 $12 \pm 2 \%$ 为初始条件，玉米籽粒干燥至安全含水率 $14 \%$ 。分别测定玉米籽粒的干燥曲线。

![](images/2bfa5b3af48892f60e7c855fbbee388ffcfc544d3891781f1b66410fa5b2ebf3.jpg)  
图3干燥装置示意图

1一鼓风机；2一管道；3一进风口；4一加热器； 5一干燥室；6一气流均布器；7一称重传感器； 8一物料；9－玻璃视镜门；10，11，12一蝶阀 Fig.3 Schematic diagram of drying equipment 1-Fan; 2-Pipe; 3-Air inlet; 4-Heater; 5-Drying chamber; 6-Air distributor; 7-Load cells; 8-Material; 9-Glassmirror doors;10,11,12-Flygate

# 2.3.2计算机模拟实验

表2传质传热过程参数  
Table 2 Parameters in the heat and mass transfer process   

<html><body><table><tr><td colspan="2">proctss</td></tr><tr><td colspan="2">模型参数 参数设置</td></tr><tr><td>玉米表面扩散系数D/m/s</td><td>7.817×105x 4850T</td></tr><tr><td>种皮扩散系数D/m/s</td><td>3.76×10e-37522T X15</td></tr><tr><td>硬质胚乳扩散系数D/m²/s</td><td>4.08×10e2506.6/T X1.5</td></tr><tr><td>软质胚乳扩散系数D3/m/s</td><td>9.65x107e-15881T X21.5</td></tr><tr><td>胚扩散系数D4/m²/s</td><td>8.79×106e3202/T Xx15</td></tr><tr><td>舍伍德数Sh</td><td>2.0+ 0.522Rel² Sc1/3</td></tr><tr><td>玉米等效粒径d/mm</td><td>4.83</td></tr><tr><td>常数Da</td><td>2.5×10-5</td></tr><tr><td></td><td>exp(-1.74-3.56X +</td></tr><tr><td>玉米籽粒导热系数 k/ W/(m·K)</td><td>4.72×10T +6.48X² -</td></tr><tr><td></td><td>1.5×10 4T² + 6.72×10² XT)</td></tr><tr><td>水的汽化潜热hw/J/kg</td><td>383.65 × (647.1- T) 0.316</td></tr><tr><td>玉米籽粒的汽化潜热 hfg/ J/kg</td><td>h ×(1 + 0.8953e-1232χ )</td></tr></table></body></html>

模型的数值求解采用 COMSOL Multiphysics(4.3a）中的对流扩散模块和传热模块[15]，根据传热传质数学模型自定义的控制方程，对玉米籽粒进行模拟实验，模拟实验条件与实验条件相同。在COMSOLMultiphysics设置过程中，导入物理模型后，在单元尺寸中，校准选择普通物理网格标准，通过网格无关性验证表明，取普通物理网格作为计算网格满足精度要求。

传质传热过程各参数如表2所示。

# 2.4实验参数的获取

干基含水率计算公式为：${ \ M } _ { t } = \frac { W _ { t } - W _ { G } } { W _ { G } }$

式中： $\boldsymbol { W } _ { t }$ 为在任意干燥 $t$ 时刻的总质量，g; $W _ { G }$ 为干物质质量， $\mathbf { g } _ { \mathsf { c } }$ （20

# 3结果分析与讨论

模拟干燥5min后，籽粒内部不同位置处温度差异很小，温度梯度近似为零；此后仅考虑水分梯度对水分扩散的影响。由图4可知，热风温度为$7 0 ^ { \circ } \mathrm { C }$ ，干燥 $1 2 \mathrm { m i n }$ 时，单组分玉米籽粒平均含水率模拟值和实验值相差最大，最大差值为0.0389，相对误差为 $1 1 . 3 9 \%$ ，误差来源可能是由于实际物料与模拟假设参数间的差异。模型中采用一维球体湿分扩散模型得到的经验水分有效扩散系数，且将玉米籽粒简化成均质体，而实际玉米籽粒由种皮、胚、角质胚乳、粉质胚乳等组分组成，且各部分扩散系数不同，对其简化必然引起偏差。相比而言，多组分玉米籽粒平均含水率模拟值和实验值具有较高的重合度，最大差值为0.0138，相对误差为 $4 . 5 6 \%$ 。

![](images/9a4ff2038b08334a9375b60dedf2c3f4d1204ab5394b4ed31c8d18088db02e78.jpg)  
图 $\boldsymbol { 4 7 0 ^ { \circ } C }$ 下单组分与多组分模拟值与实验值干燥对比曲线 Fig.4 Comparison of drying curves from one-component model,multi-component model and experiment in $7 0 ^ { \circ } \mathsf { C }$

进入干燥末期，随着玉米籽粒含水率减小，模拟值与实验值的差值逐渐变大，此时模拟含水率变化慢，而实测含水率变化快，原因可能在于：干燥实验末期，在高温下持续干燥较长时间的玉米籽粒开裂，玉米籽粒失去了籽粒皮层阻力，使籽粒内部直接接触热风，加快了水分传递速率；同时玉米籽粒收缩变形，水分在玉米籽粒内部的传递距离变短，相应的单位时间水分传递速率就变快；而在模拟实验时，模型并未考虑玉米在干燥过程中的开裂以及收缩变形，因此造成了干燥末期含水率模拟值与实验值的差值较大的现象。

![](images/61c0719e86b79495377292e4528d4806e2cd43571de8463337768e43c3d822cd.jpg)  
图 $\textsf { 5 8 0 } ^ { \circ } \mathsf { C }$ 下单组分与多组分模拟值与实验值干燥对比曲线 Fig.5 Comparison of drying curves from one-component model, multi-component model and experiment in $8 0 ^ { \circ } \mathsf { C }$

对比图4和图5可以发现，热风温度越高，玉米籽粒达到安全含水率所需的时间越短，干燥耗时越短。同时，可以观察到热风温度 $8 0 ^ { \circ } \mathrm { C }$ 时，单组分模型与多组分模型的模拟值与实验值的差异都较热风温度 $7 0 ^ { \circ } \mathrm { C }$ 时为小，这可能是因为：温度越高，扩散系数越大，同时各组分的扩散系数差异减小，接近实际值，进而模拟值与实验值的差异变小，但考虑到减少的差值与提升热风干燥温度所需要的能量，以及高温易降低玉米品质，并不值得用过高的温度进行干燥，以达到节能的目的。同时，即使在热风温度为 $7 0 ^ { \circ } \mathrm { C }$ 的时候，多组分的模拟值与实验值的差异也很小，说明多组分玉米干燥模型较单组分玉米干燥模型具有更高的精度，证明了模型的可靠性。不同干燥温度条件下，玉米籽粒含水率 $X$ 随干燥时间 $t ( \mathrm { m i n } )$ 的变化规律如表3所示。

表3玉米干燥曲线回归模型  
Table 3 Formulas of corn drying curves under different temperatures   

<html><body><table><tr><td>温度/℃</td><td>模型</td><td>关系式</td><td>R²</td></tr><tr><td rowspan="3">70</td><td>实验值</td><td>X= 0.00002t² - 0.0044t + 0.3905</td><td>0.9990</td></tr><tr><td>多组分</td><td>X= 0.00002t² - 0.0044t + 0.3807</td><td>0.9976</td></tr><tr><td>单组分</td><td>X= 0.00003t² - 0.0044t + 0.3608</td><td>0.9805</td></tr><tr><td rowspan="3">80</td><td>实验值</td><td>X=0.00003t² - 0.0052t + 0.3724</td><td>0.9963</td></tr><tr><td>多组分</td><td>X= 0.00003t² - 0.0051t + 0.3657</td><td>0.9947</td></tr><tr><td>单组分</td><td>X= 0.00003t² - 0.0050t + 0.3475</td><td>0.9764</td></tr></table></body></html>

此外，从多组分玉米干燥模型的水分分布云图中也可以看出玉米籽粒内部的水分变化情况。图6

分别为不同温度条件下(左图为 $7 0 ^ { \circ } \mathrm { C }$ ,右图为 $8 0 ^ { \circ } \mathrm { C } \mathrm { \cdot }$ ）玉米籽粒模拟干燥600s、1800s、3600s时的水分分布云图。由图可知，随着干燥时间的进行，玉米籽粒的平均含水率逐渐降低；玉米籽粒外部含水率低于内部含水率；在不同干燥阶段，干燥温度为 $8 0 ^ { \circ } \mathrm { C }$ 时的玉米籽粒的含水率较干燥温度为 $7 0 ^ { \circ } \mathrm { C }$ 时的低，即温度越高干燥越快。

![](images/e49812e104c1723bef3c41b2b2dfdaad591dc3aae0c0d107becf7d02ebc5bd7b.jpg)  
图6不同干燥时刻不同干燥温度的水分分布云图（左 $7 0 \ ^ { \circ } \mathsf { C }$ ，右 $8 0 \ ^ { \circ } \mathsf { C }$ ）  
Fig.6Moisture distribution nephogram in different drying time of corn kernel (left: $7 0 ^ { \circ } \mathsf { C }$ ,right: $8 0 ^ { \circ } \mathsf { C }$ ）

# 4结论

(1)本文建立了玉米籽粒的多组分与单组分几何模型和干燥数学模型，模拟研究与薄层干燥实验研究结果表明，基于玉米籽粒的成分、物理结构特点构建的多组分干燥模型与单组分干燥模型均可有效反映薄层干燥试验曲线的变化趋势，但多组分干燥模型的模拟精度优于单组分模型。

(2)干燥温度升高，模型模拟结果与实验结果间的差异降低，但降低幅度有限。热风温度为 $7 0 ^ { \circ } \mathrm { C }$ 时，多组分干燥模型依然具有较高精度，具有实际应用价值。

# 参考文献

[1]Prachayawarakorn S,Poomsa-ad N,Soponronnarit S.

Quality maintenance and economy with high- temperature paddy-drying processes[J]. Journal of Stored Products Research, 2005,41(3): 333-351.   
[2] Perre P. A Review of Modern Computational and Experimental Tools Relevant to the Field of Drying[J]. Drying Technology, 2011,29(13SI): 1529-1541.   
[3] 袁越锦，谭礼斌，徐英英，等．颗粒堆积多孔介质干燥多 尺度多层结构传热传质模型及模拟[J].工程热物理学报, 2015,36(12): 2726-2730. YUAN Yuejin， TAN Libin， XU Yingying， et al. Multi-Scale and Mutli-Layer Structural Modeling and Simulation of Heat and Mass Transfer Process for Drying of Grain Packing Porous Media[J]. Journal of Engineering Thermophysics,2015,36(12): 2726-2730.(in Chinese with English abstract)   
[4] 祝树森，张绪坤，黄俭花，等．基于核磁共振的物料内部 水分检测及应用进展[J]．食品科技,2012,37(6):294-298. ZHU Shusen， ZHANG Xukun,HUANG Jianhua,et al. Testing and application progress of material internal moisture based on nuclear magnetic resonance[J]. Food Science and Technology,2012,37(6): 294-298. (in Chinese with English abstract)   
[5] 要世瑾，杜光源，牟红梅，等．基于核磁共振技术检测小 麦植株水分分布和变化规律[J]．农业工程学报，2014, 30(24): 177-186. YAO Shijin，DU Guangyuan， MOU Hongmei， et al. Detection of water distribution and dynamics in body of winter wheat based on nuclear magnetic resonance[J]. Transactions of the Chinese Society of Agricultural Engineering (Transactions of the CSAE)，2014,30(24): 177-186. (in Chinese with English abstract)   
[6] Takhar P S,Maier D E, Campanella O H, et al. Hybrid mixture theory based moisture transport and stress development in corn kernels during drying: Validation and simulation results[J]. Journal of Food Engineering,2011, 106(4): 275-282.   
[7] Chen G B, Maier D E, Campanella O H, et al. Modeling of moisture diffusivities for components of yellow-dent corn kernels[J]. Journal of Cereal Science,2009, 50(1): 82-90.   
[8] 贾灿纯,李业波，刘登瀛，等．缓苏过程中玉米颗粒内部 水分分布的数学模拟[J]．农业工程学报，1996，12(1): 147-151. JIA Canchun,LI Yebo,LIU Dengying, et al. Mathematics simulation of the moisture content distribution in a corn

kernel during tempering[J]. Transactions of the Chinese Society of Agricultural Engineering(Transactions of the CSAE),1996,12(1):147-151.(in Chinese with English abstract)

[9] 葛玉姣．玉米种子干燥过程中皮层阻力影响的研究[D]. 沈阳：东北大学，2012. GE Yujiao.The study on cortex resistance in drying process of corn seeds[D]. Shenyang: Northeastern University, 2012. (in Chinese with English abstract)   
[10]张世伟，陈帅，黎勋，等．基于三维实体模型的玉米颗粒 真空干燥数值模拟[J]．真空科学与技术学报,2016,36(1): 51-56. ZHANG Shiwei, CHEN Shuai,LI Xun,et al. Modelling and Numerical Simulation of Single Corn-Grain in Vacuum Drying[J]. Chinese Journal of Vacuum Science and Technology,2016,36(1):51-56.(in Chinese with English abstract)   
[11]张世伟，孔宁华，张志军，等．基于三维实体模型的玉米 热风干燥模拟计算[J]．东北大学学报(自然科学版),2013, 34(6): 871-874. ZHANG Shiwei, KONG Ninghua, ZHANG Zhijun, et al. Simulation of Hot Air Drying on Corn Grains Based on the Three Dimension Entity Model[J].Journal of Northeastern Univeristy (Natural Science)，2013,34(6): 871-874. (in Chinese with English abstract)   
[12] 贾灿纯，曹崇文．玉米颗粒内部的二维传热传质过程[J]. 北京农业工程大学学报,1995,15(1):45-51. JIA Canchun,CAO Chongwen.Process of two-dimensional heat and mass transfer in corn kernel[J]. Journal of Beijing agricultural engineering university,1995,15(1):45-51.(in Chinese with English abstract)   
[13]朱文学，曹崇文．农产品干燥工艺过程的计算机模拟 [M]．北京：中国农业出版社,2001. ZHU Wenxue,CAO Chongwen.Computer Simulation of Agricultural Product Drying Process[M].Beijing: China Agricultural Press,2o01.(in Chinese with English abstract)   
[14] Abasi S,Minaei S.Effect of Drying Temperature on MechanicalPropertiesofDriedCorn[J].Drying Technology,2014,32(7): 774-780.   
[15]任广跃，张伟，陈曦，等．缓苏在粮食干燥中的研究进展 [J].食品科学,2016,37(1):279-285. REN Guangyue, ZHANG Wei, CHEN Xi, et al.Advances in the application of tempering in grain drying[J].Food Science,2016,37(1):279-285.(in Chinese with English abstract)