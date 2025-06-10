# AIMS望远镜8\~10微米成像终端系统装调检测方法

王雅琦1²，冯志伟1,，白先勇1,2,3，张志勇1,2,3，孙英姿1,3，荀辉，沈宇樑1²，邓元勇1,2.3(1．中国科学院国家天文台，北京100101;2．中国科学院大学，北京100049;3．中国科学院国家天文台太阳活动重点实验室，北京 100101;4．中国科学院国家天文台天文光学重点实验室，北京100101;5．中国科学院上海技术物理研究所，上海 200083)

摘要：针对AIMS望远镜 ${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ 真空制冷成像终端系统的高精度装调需求，提出了一种基于中红外可调谐激光光源的宽谱段干涉检测和装调方法。首先，采用泰曼一格林型干涉仪，利用其参考臂可调的优势，弥补光源相干性不足的缺陷，从而可以实现 $8 { \sim } 1 0 \mu \mathrm { m }$ 宽谱段的干涉测量。其次，完成了干涉仪光学系统设计，可同时兼顾 $8 { \sim } 1 0 { \mu } \mathrm { m }$ 和可见光双波段的波前质量，从而解决了肉眼不可见为干涉仪自身装调带来的困难。设计结果表明，利用可见光激光器进行干涉仪自身装调，可达到RMS $0 . 0 5 \lambda @ 0 . 6 3 3 \mu \mathrm { m }$ 的波前精度；在 $8 \mathrm { { \sim } 1 0 \mu m }$ 检测波段，干涉仪波前RMS值均能优于 $0 . 0 0 1 \lambda$ ，可满足待测系统的检测需求。最后，基于逆向优化法仿真了 ${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ 光学系统的装调流程。

关键词：中红外；装调检测；泰曼一格林干涉仪；逆向优化中图分类号：TN21 文献标识码：A 文章编号:XXXXXXXXXXXXXXX

# 0引言

正在建设中的“用于太阳磁场精确测量的中红外观测系统”项目（简称AIMS）是我国自主研制的第一台专门用于中远红外波段太阳观测的大型设备。其中 $8 { \sim } 1 0 \mu \mathrm { m }$ 波段成像观测系统是该望远镜的重要终端设备之一，用于系统研究太阳活动的中红外响应[1-2]，以新的视角开拓新的领域，创造新的科学机遇。

然而，创造新的机遇也意味着面临更多的技术挑战。科学观测要求 $8 { \sim } 1 0 \mu \mathrm { m }$ 终端系统的成像质量须达到衍射极限。而常温的黑体辐射峰值在 $8 { \sim } 1 0 \mu \mathrm { m }$ ，为抑制环境背景，提高信噪比，系统需要工作在100K的真空制冷环境中。在低温环境中光学元件曲率和折射率的变化，以及结构的形变都会严重影响系统像质。低温环境导致的变化比较复杂，目前还没有成熟的经验可循，所以必须要对该终端系统进行精密的检测，并根据检测结果指导系统装调。

在可见光波段已有成熟的装调检测方法和仪器，如ZYGO干涉仪[3、4D干涉仪以及夏克哈特曼波前传感器等，均可以实现 $ { \mathrm { P V } } \lambda / 2 0$ 以上的高精度检测。但由于本终端系统为了尽量减小真空舱的体积，采用了透射式光学设计，可见光不能透过，因而可见光波段的检测仪器和方法无法直接应用。

利用红外干涉仪进行装调检测是很好的选择。为应对红外波段的检测需求，国际上很早就开展了红外波段干涉仪的研究[4]，已经开发出了成熟的商业化产品[5]；国内近些年来也开展了红外干涉仪的研究工作[6-8]，积累了很多成功的经验。

然而，目前国内外所开展的红外干涉测量主要集中在 $3 . 3 9 \mu \mathrm { m }$ 和 $1 0 . 6 \mu \mathrm { m }$ 等相干性较好的激光波段。对于AIMS望远镜 $8 { \sim } 1 0 \mu \mathrm { m }$ 终端而言，其波段跨越了 $2 \mu \mathrm { m }$ 的带宽，现有红外干涉仪显然无法满足该系统的装调检测需求，因此我们需要发展一种适用于该系统的测试方法。

在可见光和近红外波段利用宽波段短相干光源进行干涉测量已有先例，LawrenceJ.Steimle等人采用连续谱光源配合单色仪构造宽波段的光源，可以覆盖 $2 0 0 { \sim } 1 1 0 0 \mathrm { n m }$ 的带宽，利用泰曼一格林型式干涉仪，实现了哈勃望远镜干涉滤光片的透过波前测量[9。但在中红外波段，宽波段的连续谱光源通常为碳化硅和氮化硅等热光源，其辐射强度与温度相关，满足黑体辐射定律。在中红外波段这些光源辐射强度已经很弱，经单色仪分光，再经过干涉仪系统后能量所剩无几，用现有的探测器几乎无法探测到。

近年来发展起来的红外可调谐激光器技术能够在 $8 { \sim } 1 0 \mu \mathrm { m }$ 的波段实现连续可调，且有较高的辐射强度，可以考虑用来作干涉检测的光源[10-11]。但宽谱段可调谐激光器相干性较差，因此我们采用了非共路泰曼一格林型干涉仪，利用参考臂长度可调的优势实现等光程干涉，以弥补相干性不足的缺陷，从而实现干涉测量。

本文主要根据AIMS望远镜成像光路的装调检测需求，设计了基于中红外可调谐激光器光源的泰曼一格林型干涉仪检测方案，完成了干涉仪系统的参数设计，并进行了仿真分析。本研究对AIMS望远镜 $8 { \sim } 1 0 \mu \mathrm { m }$ 终端系统的装调和检测有一定的指导意义，同时也为红外的其它波段以及其它光学系统的装调检测提供了参考。

# 1红外干涉检测方案的总体设计及分析

# 1.1 $8 { \sim } 1 0 \mu \mathrm { m }$ 终端系统参数及装调检测需求

$8 { \sim } 1 0 \mu \mathrm { m }$ 成像系统是AIMS望远镜主要终端之一，位置如图1所示，图2为 $8 { \sim } 1 0 \mu \mathrm { m }$ 成像终端系统光路。

![](images/2f2aab06d815f74e2fa39c1f8933f41d891936f040acd45e016e5b47790e9406.jpg)  
图1AIMS望远镜 $8 { \sim } 1 0 { \mu } \mathrm { m }$ 成像终端系统位置

![](images/606cf21d1bcdb0d2aa08eb61a7e70481f8097f589beda828ee4f2a9d73988158.jpg)  
Fig.1Position of $8 { \sim } 1 0 \mu \mathrm { m }$ imaging terminal systemofAIMS   
图2 $8 { \sim } 1 0 \mu \mathrm { m }$ 成像终端系统光路 Fig.2Optical path of ${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ imaging terminal system

图2中可见，由AIMS望远镜中继光学系统出射的准直光束入射到 $8 { \sim } 1 0 \mu \mathrm { m }$ 成像系统中。准直光束的直径为 $2 8 \mathrm { m m }$ 。经过一次成像镜组会聚后，再经由场镜将中间瞳面成像于二次成像镜组之前。在中间瞳面处设置制冷光阑，以抑制孔径边缘带来的杂散光。干涉滤光片置于靠近制冷光阑的位置，以限制系统透过波段。再经二次成像镜组将太阳像成像于探测器感光面上。整体光路系统长度为 $3 2 8 \mathrm { m m }$ ，系统等效焦比为3.5，视场角为 $6 . 4 ^ { \prime }$ 。为抑制环境背景辐射，场镜、干涉滤光片、制冷光阑、二次成像镜组和探测器等均置于真空制冷环境中，由真空封窗与外部环境隔开，工作温度为 $1 0 0 \mathrm { K }$ 。

在如此低温条件下，光学材料的折射率和元件的曲率均将发生较大的变化，而这种变化并没有可靠的实测数据可供参考。光学结构也将发生较大形变，材料不均匀性和加工应力等因素导致的形变非常复杂，仅采用模拟仿真很难与实际结果相吻合。因此为确保成像质量，我们需发展一种可行的装调检测方法。

# 1.2 红外干涉检测方案设计

${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ 光路系统为直径 $2 8 \mathrm { m m }$ 准直光入射的成像系统，等效焦比为 $\mathrm { F } / 3 . 5$ ，为此，设计了采用泰曼一格林型红外干涉仪进行装调和检测的方案，检测方案示意图如图3所示。

![](images/68e9b4203253ef345a39a0780195a8da1cceb0aaaeedff576bb6b70e2143eab7.jpg)  
Fig.3Schematic diagram of infrared interference detection scheme

红外光源采用 $8 { \sim } 1 0 \mu \mathrm { m }$ 可调谐红外激光器[12]，具体参数如图4和表1所示。可见该激光器在 $8 { \sim } 1 0 \mu \mathrm { m }$ 波段连续可调，且激光功率均可达到 $5 0 \mathrm { m W }$ ，能够满足检测需求。

![](images/8a4d6008930c6437ad102acda0f8f7eee7f45a1d6670db64c4445b6ef027bb65.jpg)  
图3红外干涉检测方案示意图  
图4 中红外可调谐激光器峰值功率随波长变化曲线[12]

Fig.4Curves of peak power varying with wavelength of tunable Mid-IR laser system

# 表1中红外可调谐激光器具体参数

Tab.1Detailed parameters of Tunable mid infrared laser system

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Center Wavelength(μm)</td><td>9-10.5</td></tr><tr><td>Min.Tuning Range (μm)</td><td>8-11.5</td></tr><tr><td>Min.Tuning Range (cm-1)</td><td>>300</td></tr><tr><td>Linewidth</td><td>0.1cm/0.081nm@9um (FWHM)</td></tr></table></body></html>

激光光束经会聚透镜聚焦于针孔光阑，光阑采用水冷方式制冷，冷却至室温。光束由准直镜组准直后经分束片分成两路。分束片采用硒化锌（ $\mathrm { Z n S e } ^ { \cdot }$ ）材料，根据待测系统透过率设计分光比，从而保证参考光与测试光强度尽量相等。反射光束作为参考光，经标准平面反射镜 $\Phi$ 返回；透射光束作为测试光，由窗口入射真空舱，经会聚镜组转化为与待测系统焦比相适应的球面波，并使其球心与待测系统的焦点重合，反向入射待测系统，经过 $8 { \sim } 1 0 \mu \mathrm { m }$ 成像系统形成准直光束，再经标准平面反射镜 $\textcircled{2}$ 返回。参考光和测试光再经分束片后汇合成一束平行光，通过会聚镜组在探测器上接收干涉条纹。探测器拟采用国产 $6 4 0 { \times } 5 1 2 \mathrm { H g C d T e }$ 焦平面阵列探测器，像元大小为 $1 5 \mu \mathrm { m }$ 。探测器放置在光阑12 后适当的距离，使干涉条纹完全投射在感光面之内。

设计中，采用了球面波从焦点入射的检测方式，以减小准直光束直径。准直光束的直径仅为 $1 0 \mathrm { m m }$ ，从而减小了准直镜、分束镜和会聚镜的口径，大大降低了加工难度和成本。

# 1.3系统相干性分析

在干涉测量中，用条纹对比度 $K$ 来表示干涉场中某点附近的条纹清晰程度[13]，

$$
K = \frac { I _ { M } - I _ { m } } { I _ { M } + I _ { m } }
$$

（1）式中， $I _ { M }$ 和 $I _ { m }$ 分别为条纹的强度极大值和极小值。当 $K = 1$ 时，条纹最清晰，即完全相干。当 $K = 0$ 时，条纹完全看不见，即非相干。

影响条纹对比度的因素，主要包括光源尺寸、两相干光波振幅比和谱线线宽等。本系统中光源采用了较小尺寸的针孔光阑，对对比度的影响可以忽略；根据系统透过率设计分束片膜系，检测光与参考光可以实现等振幅，从而不影响对比度。因此本系统中对条纹对比度影响较大的因素是光源的单色性。

能够发生干涉的最大光程差 $\Delta L$ 为：

$$
\Delta L = \frac { \lambda ^ { 2 } } { \Delta \lambda }
$$

其中 $\lambda$ 为激光光源输出谱线的中心波长， $\Delta \lambda$ 为谱线线宽。

单一波长光强随 $\Delta L$ 的变化为：

$$
2 i ( k ) [ 1 + \cos ( k \Delta L ) ]
$$

$i ( k )$ 为以波数表示的光谱分布函数，不同波长光强分布叠加

$$
I ( \Delta L ) = 2 \int _ { 0 } ^ { \infty } i ( k ) [ 1 + \cos ( k \Delta L ) ] d k
$$

可以求出条纹对比度 $K$ 与 $\Delta \lambda$ 和 $\Delta L$ 的关系。

在不影响计算精度的情况下，不妨取 $i ( k )$ 为方波分布，则由（1）式和（4）式可得：

$$
K = \frac { I _ { M } - I _ { m } } { I _ { M } + I _ { m } } = s i n c \left( \frac { \Delta k \Delta L } { 2 } \right)
$$

可调谐激光器输出的谱线线宽约为 $\mathtt { 1 } \lambda \lambda = 0 . 0 8 1 \mathrm { { n m } }$ ，在中心波长 $\scriptstyle \lambda = 9 \mu \mathrm { m }$ 处，当 $K { = } 0 . 5$ 时，可计算出 $\Delta L$ 约为 $1 9 2 \mathrm { m m }$ ，即参考臂与测试臂之间的光程差为 $1 9 2 \mathrm { m m }$ 时，条纹的可见度仍可达到0.5，该光程差在实际操作中很容易实现。因此基于中红外可调谐激光光源的干涉检测方案是可行的。

# 2红外干涉仪的基本参数设计及仿真

基于上述红外干涉检测方案，设计了一组准直镜，将针孔光阑出射的球面波转换为直径约为 $1 0 \mathrm { m m }$ 的高质量平面波。准直镜组是由硫化锌（ $z \mathrm { n s }$ ）材料透镜构成的双分离镜组，焦比为3.5。设计参数如表2所示。

<html><body><table><tr><td>Surf</td><td>Radius</td><td>Thickness</td><td>Glass</td><td>Semi-diameter</td></tr><tr><td>OBJ</td><td>Infinity</td><td>32.192</td><td></td><td>0</td></tr><tr><td>STO</td><td>44.288</td><td>2</td><td>ZnS</td><td>5.045</td></tr><tr><td>2</td><td>40.042</td><td>1.6</td><td></td><td>5.057</td></tr><tr><td>3</td><td>-159.594</td><td>2</td><td>ZnS</td><td>5.262</td></tr><tr><td>4</td><td>-31.548</td><td>0</td><td></td><td>5.416</td></tr><tr><td>5(Paraxial)</td><td></td><td>99.893</td><td></td><td>5.416</td></tr><tr><td>IMA</td><td></td><td></td><td></td><td>2.802E-3</td></tr></table></body></html>

利用 Zemax 软件进行了波前分析，如图5所示。结果表明，准直镜组的波像差PV 值为 $0 . 0 0 8 7 \lambda @ 9 \mu \mathrm { m }$ ，RMS 值为 $0 . 0 0 2 8 \lambda @ 9 \mu \mathrm { m }$ ，设计结果能够满足干涉系统精度要求。

![](images/ffb41db85f49c9cfb8d0518f7ce0b4d1b6a2a184a8c64169b8bf97d8ef4837b0.jpg)  
图5准直镜组波前  
Fig.5Wavefront of collimating lens

由于可调谐激光器输出谱线线宽约为 $0 . 0 8 1 \mathrm { n m }$ ，因而透镜组设计不需要考虑色差；而整个 $8 { \sim } 1 0 \mu \mathrm { m }$ 检测波段跨度较宽，消色差设计难度较大，因此准直镜组未采用消色差设计。不同波长对应的像质变化主要是离焦所致，可通过移动针孔光阑以及激光会聚透镜的位置进行补偿。表3为Zemax软件计算得到的不同工作波长在其焦点位置所对应的波前。可见，不同工作波长的波前仍可满足测试的精度要求。

表2准直镜组设计参数Tab.2Designed parameters of collimating lens  
表3准直镜组在不同波段对应的波前Tab.3Wavefront of collimating lens in different waveband  

<html><body><table><tr><td>Wavelength</td><td>Focus</td><td>PV value of wavefront</td><td>RMSvalueofwavefront</td></tr><tr><td>8um</td><td>31.892mm</td><td>0.011λ</td><td>0.0035λ</td></tr><tr><td>9um</td><td>32.192mm</td><td>0.0087λ</td><td>0.0028λ</td></tr><tr><td>10um</td><td>32.546mm</td><td>0.0067λ</td><td>0.0022λ</td></tr></table></body></html>

针对 $8 { \sim } 1 0 \mu \mathrm { m }$ 成像系统，我们将会聚镜组以及成像镜组设计为与准直镜组相同的镜组，系统对称结构的补偿将使得像质进一步提高。由于镜组焦距相同，系统放大率为1。会聚镜组将准直光束转化为 $\mathrm { F } / 3 . 5$ 的球面波，与待测系统的焦比相匹配。在不加入待检系统的情况下,使用一个等焦比的理想透镜（不会引入任何像差）替换待测系统放入干涉仪中，以模拟干涉仪自身的波像差。仿真结果显示，干涉系统的波像差RMS值为 $0 . 0 0 1 4 \lambda \textcircled { \omega } 9 \mu \mathrm { m }$ ，如图6（b）所示。可见能够满足待测系统衍射极限的装调检测需求。

![](images/5057700feb524cc0f57e7603716c41dd32ad3986af7b40532731d18219fb1152.jpg)  
图6不加入待检系统情况下干涉系统及波像差 Fig.6Interference system without the system under test and its wavefront

在 Zemax 中非序列模式下对干涉系统进行建模，在探测器上观察到仿真干涉条纹，如图7所示。

![](images/626f84aa04e4c51bca12d89d165b2941009a5802f559af689524ff6b6f7360bc.jpg)  
图7非序列模式下干涉条纹图  
Fig.7Interference fringe diagram in non-sequential mode

# 3红外干涉仪自校准装调方法

在进行检测之前干涉仪自身需要进行精确装调，以获得高质量波前。但由于红外波段肉眼不可见，干涉仪系统的装调难度较大。为此在光学设计时，考虑利用可见光He-Ne 激光器实现干涉仪装调。所以在设计准直镜以及会聚透镜时均采用了可见光波段具有较好透过率的 $z _ { \mathrm { n S } }$ 材料，并在膜系设计时考虑了可见光的透过带。在透镜参数的优化设计时也兼顾了可见光的波前。

装调时采用自准直的方法排列元件，如图8所示。

![](images/720483d11d2f8cc83a08cda517eb8c4037198f61c091f80d4ef98f0c207b466b.jpg)  
图8干涉仪装调示意图

将 $0 . 6 3 3 \mu \mathrm { m H e } \mathrm { - N e }$ 激光器切入光路，光束会聚后经针孔及准直镜，由标准平面反射镜返回，使光点与针孔重合；然后在准直光路中插入分束板，再利用标准平面镜将光束返回；调整反射镜的角度，在会聚透镜处放置一接收屏，在屏上可以观察到两平行光束的干涉条纹。然后撤去观察屏，插入会聚透镜，调整会聚透镜及标准平面镜的角度，在会聚透镜焦面上将两光点调整至重合，此时利用可见光探测器接收干涉条纹，经过精密调整将波前调整到最佳。

由光学设计软件模拟结果图9（a）可见，系统波前RMS值可达到 $0 . 0 5 \lambda @ 0 . 6 3 3 \mu \mathrm { m }$ ，其干涉条纹如图9（b）所示。

![](images/42e57775472cd25d316c0921e2e24d1d2da0811341c31bd587a9ded8b2ad3a86.jpg)  
Fig.8Installation and adjustment diagram of interferometel   
图9可见光入射时的波前和干涉条纹  
Fig.9 Wavefront and interference fringes caused by visible light incidenting

中红外波段与可见光的区别仅在于焦距不同，根据追迹软件计算，波长分别为 ${ 9 } { \mu \mathrm { m } }$ 与$0 . 6 3 3 \mu \mathrm { m }$ 时，准直镜焦距差值为 $3 . 5 7 0 \mathrm { m m }$ ，因此可以平移针孔光阑相应的距离，而后切入中红外激光束。为保证和可见光共光路，利用红外靶标进行红外和可见光的共光路调整8。此时系统仅有离焦误差，只需微调针孔光阑的位置即可校准干涉仪系统。同样，在切换不同波长时，系统仍然是仅有离焦，所以只需要沿光轴调整针孔即可。在 Zemax 中模拟了不同工作波长下干涉仪的调整情况，如表4所示：

表4干涉仪在不同工作波段对应的波前Tab.4 Wavefrontof interferometer in different wavebands  

<html><body><table><tr><td>Wavelength</td><td>Displacement</td><td>RMSvalueofwavefront</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td>8um</td><td>0.3mm</td><td>0.0019λ</td></tr><tr><td>9um</td><td>0</td><td>0.0014λ</td></tr><tr><td>10um</td><td>-0.354mm</td><td>0.0010λ</td></tr></table></body></html>

# 4 $8 { \sim } 1 0 \mu \mathrm { m }$ 光学系统装调检测方法的初步模拟

干涉仪装调完成后，将待检 $8 { \sim } 1 0 \mu \mathrm { m }$ 光学系统插入干涉仪的检测臂中，并调整参考光路中标准平面镜的距离实现等臂长，此时即可开展波前的检测。

由于真空制冷结构的空间限制，会聚透镜需放置于真空制冷系统中。干涉仪出射的准直光束经过封窗入射。装调的具体步骤如下：

1、将安装好前后封窗的真空罐体放置于测试臂，此时真空罐密封顶盖敞开，处于常温常压状态;

2、依次插入会聚透镜、二次成像镜组、干涉滤光片、场镜，并逐次在各镜组焦面后用标准球面镜将光束返回形成干涉，每一步均通过观察干涉条纹将波前调整到最佳;

3、安装一次成像镜组，利用标准平面镜将光束返回，并再次将波前调整到最佳。

此时，系统在常温常压环境下完成安装。而后抽真空并加注液氮。当温度稳定到100K后，进行工作温度下检测和装调。需要说明的是，由于在检测光路中会聚透镜占据了观测系统探测器的位置，因此在 $8 { \sim } 1 0 \mu \mathrm { m }$ 光学结构设计中，探测器和会聚透镜可以在真空制冷条件下进行切换，且均可进行多维度调整。

将采用逆向优化法进行装调，即利用Zemax通过设置失调量模拟出干涉条纹，以此判断光学元件失调量的大小与方向，从而指导系统装调。以二次成像镜组为例，当二次成像镜组分别沿X轴和Y轴倾斜时，条纹随镜组倾斜角度变化的模拟结果，如图10所示。

![](images/af159a11efc0136034b4abfa58418bc63a87e96c9e6ed69f2ff68bbfb0b3cbbb.jpg)  
图10不同倾斜角度时的条纹变化 Fig.1OThe change of fringe with different tilt angle

当二次成像镜组分别沿X轴、Y轴偏心时，条纹随镜组偏心而产生的变化如图11所示：

![](images/9fb401517dc8b11cfd81c3b4639ca02023b4f30737560aaf10dc3a1a2f9f0fe7.jpg)

在实际检测中，通过提取探测器获得的条纹信息，并对其进行处理即可得出此时镜组的失调量信息。因此，在模拟仿真的指导下根据条纹的变化可实现系统的装调。

# 5总结

针对 $8 { \sim } 1 0 \mu \mathrm { m }$ 成像系统的高精度装调检测需求，设计了基于可调谐激光光源的泰曼一格林型中红外宽谱段干涉仪。针对红外波段肉眼不可见给干涉仪自身装调带来的装调困难，介绍了可见光波段干涉仪自校准装调的解决办法，并对待测系统装调流程进行了仿真分析。本研究可为宽波段红外光学系统检测装调，以及红外材料的光学性能参数的测量提供一种新方法。

# An alignment and testing method of $\mathbf { 8 } { \sim } \mathbf { 1 0 } \mathbf { \mu m }$ imaging terminal system of AIMS

Wang Yaqi1²，Feng Zhiwei14，Bai Xianyong13，Zhang Zhiyong13，Sun Yingzi13， Xun Hui5，Shen Yuliang1.2, Deng Yuanyong' (1.National Astronomical Observatories,Chinese Academy of Sciences,Beijing 1Oo101,China;   
2.University of Chinese Academy of Sciences，Beijing 1Ooo49,China;   
3.KeyLaboratoryofSolarActivity,NationalAstronomicalObservatories,Chinese AcademyofSciences,BeijingoCina;   
4.KeyLaboratorfOpticalstrooyatioaltronomicalObseatorsCneecadefences,jgia;   
5.Shanghai Institute of Technical Physics of the Chinese Academy of Sciences,Shanghai 2Ooo83,China)

Abstract:In order to meet the requirements of high-precision alignment of the ${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ vacuum cooling imaging terminal system of AIMS,a method of broadband interference for alignment and test based on mid-infrared tunable laser source is proposed.Firstof all,the Twyman-Green interferometer is used to make up for the lack of coherence of the light source by taking advantage of its adjustable reference arm,so that the ${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ broadband interferometrycan berealized.Secondly,theoptical designof the interferometer is completed,which can take into account the wavefront quality of ${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ band and visible light band at the same time,so as to solve the diffculty of the interferometer's self adjustment caused by invisible.The design results show that the use of visible laser for self-installationand adjustment of the interferometercanachieve a wavefront accuracyof RMS $0 . 0 5 \lambda @ 6 3 3 \mathrm { n m }$ .In the detection band of $8 { \sim } 1 0 { \mu } \mathrm { m }$ ，the RMS value of the interferometer wavefront can be better than $0 . 0 0 1 \lambda$ ，which can meet the detection requirements of the system under test.Finally,the assembly and adjustment process of the ${ 8 \mathord { \sim } } 1 0 { \mu \mathrm { m } }$ optical system is simulated based on the reverse optimization method.

Key words:Mid-infrared; alignment and test; Twyman-Green interferometer；Reverse optimization

# 参考文献

[1]Li Xin, Song Yongliang,Uitenbroek,H. Infrared diagnostics of the solar magnetic field with Mg I $1 2 \mu \mathrm { m }$ lines: forward-model results[J].Astronomy&Astrophysics,2021, 646:A79(12pp).   
[2]Hong Jie,Bai Xianyong,Li Ying.Non-LTE Calculations of the $\mathbf { M g } \texttt { I } 1 2 . 3 2 \ \mu \mathrm { m }$ Line in a Flaring Atmosphere[J]. The Astrophysical Journal,2020,898:134(12pp).   
[3］刘强，徐晨，李新南．基于双平晶互检法的平面绝对检验仿真[J]．天文研究与技术,2017,14(1):78-86.   
[4]Munnerlyn C R, Latta Milton. Rough surface interferometry using a $\mathrm { C O } _ { 2 }$ Laser Source[J]. Applied Optics, 7:1858-1859.   
[5]Kwon Osuk, Wyant JC, Hayslett C R. Rough surface interferometry at $1 0 . 6 \mu \mathrm { m } [ \mathrm { J } ]$ . Applied Optics,1980,19 (11) : 1862-1869.   
[6] 陈进榜,陈磊,王青,等.大孔径移相式 $\mathrm { C O } _ { 2 }$ 激光干涉仪[J].中国激光,1998,25(1):31-36.   
[7] 何勇,陈磊,王青,等.移相式泰曼-格林红外干涉仪及应用[J].红外与激光工程,2003,32(4):335-338.   
[8] 贺俊,王青,陈磊.移相式泰曼-格林红外干涉仪调试技术[J].红外与激光工程,2008.37(3):516-520.   
[9] Lawrence J. Steimle，Yaujen Wang.Development ofa broadband achromatic Twyman-Green interferometer[J].SPIE,1993,Vol.2019:366-373.   
[10] Alexander Ebner,Robert Zimmerleiter, Christoph Cobet. Sub-second quantum cascade laser based infrared spectroscopic ellipsometry[J].Optics Letters,2019,44(14):3426-3429.   
[11]Alicja Dabrowska,Andreas Schwaighofer,Stefan Lindner. Mid-IR refractive index sensor for detecting proteins employing an external cavity quantum cascade laser-based Mach-Zehnder interferometer[J]. Optics Express,2020,28(24):36632-36642.   
[12]DRS Daylight Solutions. MIRcat-QTM Mid-IR Laser. htps://daylightsolutions.com/product/mircat/. 2021. 4. 13.   
[13]梁钰廷．物理光学.第4版.北京:电子工业出版社,2012:81-87.