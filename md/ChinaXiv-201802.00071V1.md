# 一种叶片前缘前带微小圆柱的垂直轴风力机

陈珺」，孙晓晶」，黄典贵²(1.上海大学上海市应用数学和力学研究所，上海2000722.上海理工大学 能源与动力工程学院，上海 200093)

摘要：本文提出了一种通过在叶片前缘前设置微小圆柱来抑制叶片上流动分离的控制方法，并对采用此流动控制方法后的升力型垂直轴风力机的气动性能进行了数值研究。结果表明，在大攻角情况下，翼型前缘前设置微小圆柱可以有效的抑制风力机叶片上的流动分离，得到增升减阻的效果；同时，与传统的升力型垂直轴风力机相比，前缘前设置微小圆柱后的垂直轴风力机在低尖速比下的风能利用率可得到大幅度的提高。

关键词：垂直轴风力机；流动分离；气动性能；风能利用率中图分类号：TK89 文献标识码：A

# A New Type of Vertical-axis Wind Turbine Equipped with the Blades having Micro-cylinders Installed in front of Their Leading-edges

CHEN Jun', SUN Xiao-Jing', Huang Dian-Gui² (1.Shanghai Institute of Applied Mathematicsand Mechanics,Shanghai University,Shanghai 20o072,China;

2.SchoolofEnergyandPowerEngineering,UniversityofShanghai forScienceandTechnology,Shanghai2Oo093,China)

Abstract: This paper presents a flow control method using micro-cylinder installed in front of the blade leading edge and invests the aerodynamic performance of the VAWT equipped with micro-cylinders.Numerical results suggest thatthe flow separation is effectively controled by seting a micro-cylinder in front of the blade leading edge when the blade works at large atack angle.Meanwhile,the VAWT equipped with micro-cylinders has higher efficiency than regular VAWT under small tip speed ratio.

Key words: vertical axis wind turbine； flow separation; aerodynamic performance；wind energy utilizatior efficiency

# 0前言

风能是一种无污染的可再生能源，它是可再生能源中发展最快的清洁能源，同时风力发电也是最具有大规模开发和商业化发展前景的发电方式。如果风能的 $1 \%$ 被利用，则可以减少世界 $3 \%$ 的能源消耗；风能用于发电，可产生世界总电量的 $8 \% { \sim } 9 \% ^ { [ 1 ] }$ 。质量轻、结构简单、平衡性好、安装维护方便的Darrieus直叶片垂直轴风力机（SB-VAWT）具有广阔的应用前景[2]。但传统的升力型垂直轴风力机在低尖速比下常处于大攻角工况下运行，随之产生大尺度的流动分离，导致翼型的升力系数降低，阻力系数增大，最终使风力机叶片的气动性能恶化。

为了能使升力型垂直轴风力机在低尖速比下的气动性能有所提高，本文提出了一种在叶片前缘前设置微小圆柱的流动控制方法，并通过课题组自主研发的计算软件UCFD[3]对采用这种方法来抑制垂直轴风力机叶片上流动分离的效果进行了数值模拟。同时，对在叶片前缘前设置微小圆柱后的垂直轴风力机的气动性能进行了数值模拟计算，并将得到的风能利用率与传统的垂直轴风力机的风能利用率进行了对比。

# 1计算模型

计算中升力型垂直轴风力机叶片翼型选用NACA0015,翼型弦长 $c { = } 4 0 0 \ \mathrm { m m }$ ，旋转直径 $D / = 2 5 0 0$ $\mathrm { m m }$ ，自由来流速度 $V { = } 1 0 \mathrm { m } / \mathrm { s } ^ { [ 4 ] }$ 。图1为该风力机的轴向截面示意图，其中 $o$ 为旋转中心， $R$ 为旋转半径。图2为叶片前缘前设置微小圆柱后的放大图，

$L$ 为前缘前微小圆柱距离叶片前缘的距离， $d$ 为前缘前微小圆柱的直径。

![](images/9f147a948123597204dcb984a544561e43adcf30f9f48821af9ca335cdc53de3.jpg)  
图1垂直轴风力机的轴向截面示意图

![](images/a4a493bdcfa91a608a7bfa36330f9723efe121042ae8111e1933ff610d7422d5.jpg)  
Fig.1 Schematic of the cross section ofVAWT

Fig.2 Schematic of the micro-cylinder in front of blade leading

edge

程序基于三维结构化网格，整个计算域采用结构网格，外边界距翼型弦长中心为 $8 0 ~ c$ ，尽量减小边界对风力机流场的影响。同时，对叶片和微小圆柱近壁面进行了加密处理。图3为整个计算域网格；图4为翼型附近网格。

![](images/586a7ce418f0008f338de87a29ac8d19eda9ad557c2c97301c289e5e325e8175.jpg)  
图3整个计算域网格

![](images/5ff6a885169e58a69e7764747da31b972b1f8f49b6a90f152f37115f7456fa12.jpg)  
图2叶片前缘前设置微小圆柱示意图  
Fig.3Whole meshofVAWT   
图4翼型附近网格  
Fig.4Mesh around the airfoil

# 2 数值方法

本文通过求解二维不可压非定常N-S方程来数值模拟风力机流场，选用 Spalart-Allmaras (S-A)湍流模型，空间采用Roe's三阶迎风格式，计算域外边界为圆形，边界条件设置为速度进出口，翼型和微小圆柱的边界条件设为无滑移壁面，流场来流 $x$ 方向马赫数 ${ \cal M } _ { a }$ 为0.0294。

# 3计算结果及分析

# 3.1前缘前设置与未设置微小圆柱时翼型的气动性 能的比较

# 3.1.1模型验证

为了验证数值模拟的可靠性，本文首先模拟了单个NACA0012翼型在雷诺数 $R _ { e }$ 为6000000的情况下，该翼型升阻力系数随来流攻角改变而变化的情况，并将计算结果与修正后的实验值进行了比较。图5为不同攻角下，翼型升阻力系数的计算值与实验值的对比图。

![](images/61fcf49169415a6ce733a9d3031814539b07354d8431cf80eb4995e5a2275660.jpg)  
图5不同攻角下升阻力系数对比图

Fig.5 Comparison of the lift and drag coefficient between experiment and numerical simulation at various attack angle

从图5中可以看出，攻角在 $1 7 ~ ^ { \circ }$ 之前升阻力系数与实验值都拟合得较好，但在大攻角下出现了一定的偏差。这与数值模拟时采用二维非定常模拟，忽略了实际的三维效应有关，且在大攻角情况下，叶片上出现了流动分离，流动变得复杂。但从总体上来看，本文所采用的网格与计算程序用于该类翼型的模拟还是可靠的。

# 3.1.2前缘前设置与未设置微小圆柱时翼型的气动 性能的比较

影响采用微小圆柱抑制翼型上流动分离效果的主要因素有：微小圆柱的直径 $d$ 和微小圆柱距离翼型前缘距离 $L$ 。因此，本文首先对微小圆柱的直径$d$ 和微小圆柱距离翼型前缘距离 $L$ 进行了初步优化。当来流速度为 $1 0 ~ \mathrm { m / s }$ ，攻角 $1 8 ~ ^ { \circ }$ 时得到的数值模拟结果如图6所示。

![](images/149dd83b88881353a938635d228b6c72ba50d303ae5dbf8e455dbaa5ac4815a9.jpg)  
图6不同 $d$ 和 $L$ 的升阻比数值模拟结果Fig.6Lift-drag ratio at various $L$ and $d$ （204号

从图6可以看出，在攻角为 $1 8 ^ { \circ }$ 的工况下，微 小圆柱距离叶片前缘距离 $L$ 为 $0 . 0 3 \mathrm { ~ m ~ }$ 和 $0 . 0 4 \mathrm { ~ m ~ }$ 时， 微小圆柱直径的增大，可使翼型的升阻比降低，同 时微小圆柱直径 $d$ 为 $0 . 0 2 \mathrm { ~ m ~ }$ 和 $0 . 0 3 \mathrm { ~ m ~ }$ 时，距离翼 型前缘太近或太远都可导致翼型的升阻比降低。适 当的微小圆柱的 $d$ 和 $L$ 能使翼型的升阻比提高，不 适当的微小圆柱的 $d$ 和 $L$ 使翼型的升阻比下降。表 1给出了在来流风速为 $1 0 \mathrm { m / s }$ ，攻角为 $1 8 ^ { \circ }$ 情况下， 前缘前未加微小圆柱时的NACA0012翼型的升阻 力系数与升阻比，并与在该翼型前加直径为 $0 . 0 1 \mathrm { m }$ 距翼型前缘 $0 . 0 3 \mathrm { ~ m ~ }$ 的微小圆柱后翼型的升阻力系 数和升阻比进行对比。

表1设置微小圆柱前后的升阻力系数和升阻比对比 Table 1 Comparison of $C _ { l } ,$ （204号 $\mathrm { C _ { d } }$ and $\mathrm { C _ { l } / C _ { d } }$ between NACA0012 and NACA0012 with micro-cylinder   

<html><body><table><tr><td></td><td>C</td><td>Cd</td><td>CICd</td></tr><tr><td>NACA0012</td><td>0.8928</td><td>0.1500</td><td>5.95</td></tr><tr><td>设置微小圆柱</td><td>1.4481</td><td>0.09338</td><td>15.51</td></tr></table></body></html>

从表1可以看出：前缘前加了微小圆柱后的翼型，其升力系数可提高 $60 \%$ 以上，且阻力系数有所降低，使得翼型的升阻比得到提高。图7和图8为在 $1 8 ^ { \circ }$ 攻角下，在NACA0012翼型前缘前适当位置处未设置和设置了微小圆柱后翼型周围流线变化的比较。

![](images/ea40dd3ec3d41ef3c78d3408ed958501b365bf02a382e9f7ec1793640232e576.jpg)  
图7翼型前缘前未设置微小圆柱时的流线图

![](images/2958f37c6467a6280aab4dd90d635d186251596386468fb9369c837537fa391b.jpg)  
Fig.7StreamlinesofNACAo012 at $1 8 ^ { \circ }$ attackangle   
图8翼型前缘前设置微小圆柱时的流线图  
Fig.8 Streamlines ofNACAo012 with micro-cylinder at $1 8 ^ { \circ }$ attack angle

可以看出，在翼型前缘前设置微小圆柱后，翼型上原有的较大的流动分离泡（如图7所示）变成了靠近翼型尾缘处的很小的分离泡（如图8所示），翼型上的流动分离得到了显著抑制。

在以上数值模拟结果的基础上，试图将这种流动控制的方法进一步应用到升力型垂直轴风力机的叶片上，当风力机叶片处于大攻角工况运行时，采用这种方法可以有效推迟或抑制叶片上的流动分离，提高风力机叶片的气动性能。

# 3.2风力机叶片前缘前设置微小圆柱后的气动性能分析及与传统风力机结果的比较

在模拟叶片前缘前设置微小圆柱的升力型垂直轴风力机之前，本文先对文献4中的升力型垂直轴风力机进行数值模拟。模拟结果与实验值相比，最佳风能利用率所对应的叶尖速比基本一致，但最佳风能利用率偏高。风能利用率偏高与数值模拟时采用二维非定常模拟，忽略了实际三维效应有关。综上，本文所采用的网格与计算程序是有效的。接着，本文对叶片前缘设置微小圆柱的风力机的气动性能进行数值模拟。

影响采用微小圆柱抑制风力机叶片上流动分离效果的主要因素有：微小圆柱的直径 $d$ 和微小圆柱距离叶片前缘距离 $L$ 。因此，本文对微小圆柱的直径 $d$ 和微小圆柱距离风力机叶片前缘距离 $L$ 进行了初步优化。当来流速度为 $1 0 \ \mathrm { m / s }$ ，叶尖速比为1.1时，采用不同 $d$ 和 $L$ 时的风力机风能利用率的模拟结果如图9所示。

![](images/ab9b5e49a159b4aa30c7ba60f6cb9a56d1ab1157f711f67426adcbc5c9719a2c.jpg)  
图9 叶尖速比1.1时不同设置微小圆柱工况的 $C _ { p }$ 对比图 Fig.9 Wind energyutilization efficiency of various $L$ and $d$ at 1.1 tip speed ratio

从图9可以看出，随着微小圆柱直径 $d$ 的增加，风力机的风能利用率有所下降，但随着距离 $L$ 的增加，风能利用率则在不断增加。图10给出了距离 $L$ 为 $0 . 0 2 \mathrm { ~ m ~ }$ ，直径 $d$ 为 $0 . 0 0 1 \mathrm { ~ m ~ }$ 的微小圆柱设置与未设置微小圆柱的风力机 $C _ { p }$ 在低叶尖速比下的变化曲线。

![](images/d5728ef7a7ffb43ae5ac3aa9594c2f6f927aa0c1c2155dc1900aceb8ee2e2d7e.jpg)  
图10设置小圆柱前后 $C _ { p }$ 随叶尖速比变化图 Fig.10 Comparison of wind energy utilization efficiency between regular VAWT and VAWT with micro-cylinder at various tip speed ratio

从图10中可以看出，在低尖速比1.1的情况下，叶片前缘前设置微小圆柱后的风力机 $C _ { p }$ 比传统风力机提高了 $9 \%$ 。在低尖速比情况下，前缘前设置微小圆柱对风力机气动性能的提高是非常显著的。图11和图12分别给出了在叶尖速比1.1时风力机叶片前缘前适当位置处未设置和设置了微小圆柱的流线图。

![](images/ffcab22c57e7cdec0ee7900d90497c35a3f2fad8b7efd15ad582d23bf3498933.jpg)  
图11某时刻风力机叶片前缘前未设置微小圆柱流线图Fig.11 Streamlines of regular VAWT

![](images/8e9fa707af647cf9f803648fc64dbfa484f1bc072d966e3103e540dc2ef411fd.jpg)  
图12某时刻风力机叶片前缘前设置微小圆柱流线图 Fig.12 Streamlines ofVAWT with micro-cylinder

从图11、12中可以看出，在左下角位置，通过在叶片前缘前设置微小圆柱，叶片上原有的大流动分离泡被抑制，从而改善了风力机叶片的气动性能，提高了升力型垂直轴风力机在低尖速比下的风能利用率。

# 4结论

本文针对风力机叶片在大攻角下运行易产生流动分离的特征，提出了一种在风力机叶片前缘前设置微小圆柱来提高风力机叶片气动性能的流动控制方法，并采用课题组自主研发的计算软件UCFD对该流动控制方法的有效性进行了数值模拟研究，得到以下结论：(1）在大攻角情况下，在翼型前缘前设置微小圆柱可以有效的抑制翼型上的流动分离，起到增升减阻的作用；

(2）与传统垂直轴升力型风力机相比，在低尖速比下，叶片前缘前设置微小圆柱后的升力型垂直轴风力机的风能利用率有明显提高，如在叶尖速比为1.1的工况下，在风力机叶片前加设优化后的微小圆柱，风力机的风能利用率可提高 $9 \%$ 。

# 参考文献

[1]张志英．风能与风力发电技术[M]．北京：化学工业出版 社,2010 ZHANG Zhiying. Wind Energy andWindPower Technology[M].Beijing: Chemistry Industry Press,2010   
[2] SandarE,HansB,Mats L.Evaluation ofDifferent Turbine Concepts for Wind Power[J].Renewable and Sustainable Energy Reviews,2008(12):1419--1434   
[3] 黄典贵．一个通用的流体力学计算软件及其考核[J]．工 程热物理学报,2012,33(10):1703--1706 HUANG Diangui. A Common Unified Computational Fluid Dynamic Software and its Validation[J]. Journal of Engineering Thermophysics,2012,33(10):1703--1706   
[4]Bravo R,Tullis S,Ziada S.Performance Testing of a Small Vertical-Axis Wind Turbine. $2 1 ^ { \mathrm { s t } }$ Canadian Congress of Applied Mechanics,Toronto，Ontario, Canada 2007   
[5] Ladson,C L.Effects of Independent Variation of Mach and Reynolds Numbers on the Low-Speed Aerodynamic Characteristics of the NACA 0012 Airfoil Section.NASA TM 4074,1988