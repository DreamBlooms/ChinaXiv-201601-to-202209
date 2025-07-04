# 基于分层介质模型的HF雷达高度计火星回波仿真研究

徐曦煜 刘和光 杨双宝(中国科学院国家空间科学中心微波遥感技术重点实验室北京 100190)

摘要火星次表层中的水探测是当前深空探测领域中的热门问题之一．高频(HF)雷达高度计具有较强的穿透能力，且能同时实现距离和功率测量，是火星次表层探测的重要手段.介绍了高频雷达高度计系统的原理和设计，通过分析高度计电磁脉冲与多层光滑介质之间的相互作用，得出其回波功率随时间变化的模型，并考虑了表面粗糙度对表面回波功率的影响．选用典型的火星分层介质模型，对其介电常数特性和高度计回波波形进行了仿真．仿真结果表明，采用高频雷达高度计系统可实现对火星次表层介电特性垂直廓线的反演，对火星中水的识别具有重要作用.

关键词高频雷达高度计,火星,分层介质模型,介电常数，回波功率 中图分类号P353,V447

# Echo of HF-band Radar Altimeter from Mars Based on a Multi-layer Media Model

XU Xiyu LIU Heguang YANG Shuangbao (KeyLaboratory of Microwave Remote Sensing,National Space Science Center, Chinese AcademyofSciences,Beijing 1o0190)

Abstract The detection of water in Mars is currently one of the most striking issues in deep space detection. High Frequency (HF) radar altimeter has good penetrating ability and can measure the range and power simultaneously. In this paper,the principles and design of the altimeter system were presented,the interaction between the altimeter electromagnetic pulses and multi-layer smooth media was deduced,and the modelof the echo power with respect to the time delay was extracted.Besides, the effects of Mars surface roughness were also considered.Finally,two typical Mars multi-layer models were adopted,and the dielectric constants and the altimeter echo waveforms were simulated. Results of the simulation show that the vertical dielectric constant profile of Mars subsurface could be retrieved by HF radar altimetry,and the water in Mars could be identified in certain cases.

Key wordsHigh frequency radar altimeter,Mars,Multi-layer media model, Dielectric constant, Echo power

# 0 引言

火星中水的探测是当前深空探测领域中的热门问题之一．大量研究表明，火星表层由风沉积层、硬沉积层等构成的尘壤(regolith)覆盖，水分子以固态或液态的形式存在于次表层区域[1-2].高频(HF)频段 $\mathrm { 3 { \sim } 3 0 M H z ) }$ 电磁波具有较强的穿透能力，特别适用于对火星次表层的探测[1,3]．本文提出HF雷达高度计可实现对火星表层和次表层介电特性的探测

# 1HF雷达高度计原理和设计

用于火星表层/次表层探测的HF雷达高度计是一台天底点指向雷达，通过发射脉冲及测量回波传输时间进行距离测量，并通过调整接收机的自动增益控制（AutomaticGain Control，AGC)进行回波功率测量[4-5]，可实现对火星表层尘壤厚度和次表层的分层介电常数廓线等参数的反演，进而识别火星地下水，并绘制次表层沿轨向散射回波的剖面分布图，

根据科学目标，参考欧洲MARSIS（Mars Ad-vanced Radar for Subsurface and Ionospheric Soun-ding)系统[6-7] 和美国 SHARAD (SHAllow subsur-face soundingRADar）系统[8-9的载荷设计经验,本文设计了HF 雷达高度计，其系统参数列于表1.

为了在穿透深度与垂直方向分辨率之间实现性能折中，HF高度计采用了 $2 0 \mathrm { { M H z } }$ 的中心工作频率．为提高其距离分辨能力，高度计采用线性调频脉冲（Chirp信号）作为发射脉冲，时宽 $1 0 0 \mu \mathrm { s }$ ，带宽 $1 0 \mathrm { M H z }$ ，压缩比1000.接收机采用全去斜技术实现脉冲压缩[4.

根据最新的高度计体制，高度计采用了传统和合成孔径两种工作模式，该体制已成功用于Croysat-2等地球遥感测高卫星[10]．合成孔径工作模式可显著提高高度计的沿轨向分辨率及有效信噪比.两种工作模式之间根据需要可自由切换．根据系统多普勒带宽的需要，高度计设计了 $6 0 0 \mathrm { { H z } }$ 的脉冲重复频率.

由于高度计工作波长较长，采用半波偶极子天线形式[11．与普通偶极子天线相比，半波偶极子天线的阻抗特性很容易实现谐振，在方向图上无副瓣半波偶极子的天线长度为波长的1/2，考虑到雷达采用的线性调频信号工作频率最低为 $1 5 \mathrm { M H z }$ （对应于 $2 0 \mathrm { m }$ 波长),天线孔径不能低于 $1 0 \mathrm { m }$ ：天线孔径较大，因此设计为可伸展结构.

# 2HF雷达高度计回波模型

根据研究，火星表面上层更多的是由于火山、冲积、风、冰川等过程形成的地层，在大尺度上，该层可被解释为具有指数衰减特性的多孔风化土壤， $z$ 值深处的孔性为[12]

$$
\begin{array} { r } { \pmb { \varPhi } ( z ) = \pmb { \varPhi } ( 0 ) \exp ( - z / K ) . } \end{array}
$$

其中， ${ \bar { \pmb { \phi } } } ( 0 )$ 为表面的孔性(通常在 $\mathbf { 0 . 2 { \sim } 0 . 5 }$ 内)，即混合物中空气、水、冰等的比例 (按体积算)， $K$ 为衰减速度 (采用距离量纲).

火星近表层土壤的孔中可能含有大量冰态水，在较深层则可能表现为液态．图1给出了火星地层模型示意，包括全球水和冰的分布.这只是一个典型分

# 表1HF频段雷达高度计系统参数表

Table 1 System parameters of HF-band radaraltimeter   

<html><body><table><tr><td>工作频率/MHz</td><td>20</td></tr><tr><td>飞行高度/km</td><td>400</td></tr><tr><td>信号形式</td><td>线性调频信号</td></tr><tr><td>时宽/μs</td><td>100</td></tr><tr><td>带宽/MHz</td><td>10</td></tr><tr><td>发射功率/W</td><td>100 (传统);20 (SAR)</td></tr><tr><td>脉冲重复频率/Hz</td><td>600</td></tr><tr><td>天线体制</td><td>半波偶极子</td></tr><tr><td>天线口径/m</td><td>10</td></tr><tr><td>天线波束宽度/()</td><td>77</td></tr><tr><td>天线增益/dB</td><td>2.14</td></tr></table></body></html>

![](images/d43b306222b08aee1cc28a0fc2f980ae8d09fbf5030d2f5af62c865598364c02.jpg)  
图1火星次表层模型 Fig.1 Mars subsurface model

![](images/e30fadc128aca67da8a6fa58caa84e4bc210da3b7753fac225bd4b8ef1763470.jpg)  
图2火星次表层分层   
Fig.2Mars subsurface multi-layer sketch

布示例，以下将通过具体示例对火星次表层结构进行仿真.

# 2.1平坦界面次表层模型

如前所述，火星表面以下基本都是分层分布的因此首先分析平坦界面的分层模型

考查如图2所示的简化分层模型.这里将其分 为了三层. (1)大气层,高度为 $H _ { 0 }$ ；(2)沉积层，高度 为 $H _ { 1 }$ ；(3)玄武岩层.设三层的电气特性如下.

(1)大气层介电常数为 $\scriptstyle \varepsilon _ { 0 }$ ，损耗正切为 $\tan \delta _ { 0 }$ （约 为0),磁导率为 $\mu _ { 0 }$

(2)沉积层介电常数为 $\varepsilon _ { 1 }$ ，损耗正切为 $\tan \delta _ { 1 }$ ，磁导率为 $\mu _ { 1 }$

(3)玄武岩层介电常数为 $\varepsilon _ { 2 }$ ，损耗正切为 $\tan \delta _ { 2 }$ 磁导率为 $\mu _ { 2 }$

除少数铁磁性介质外，一般介质的磁导率均接近于 $\mu _ { 0 }$ ；通常假设 $\mu _ { 1 } \approx \mu _ { 0 } ; \mu _ { 2 } \approx \mu _ { 0 } .$ （2

高度计发射的信号穿透大气层达到火星表面，共产生两个回波（二次以上反射的回波不考虑，因为其能量足够低).一是火星表面的直接反射回波；二是透射入火星表面沉积层的电磁波经过衰减和玄武岩界面的反射，在沉积层和大气层传输后，由高度计接收的回波.

这两部分回波可利用延时区分.两个回波之间的延时差为

$$
t = { \frac { 2 H _ { 1 } } { c _ { 1 } } } = 2 H _ { 1 } { \sqrt { \varepsilon _ { 1 } \mu _ { 0 } } } .
$$

可得

$$
H _ { 1 } = \frac { t } { 2 \sqrt { \varepsilon _ { 1 } \mu _ { 0 } } } .
$$

这样即可根据延迟计算高度.由式(3)计算高度的前提是需要知道沉积层的介电常数 $\varepsilon _ { 1 }$ ．该值可由表面回波功率得到.

镜面的后向散射系数完全相干，其雷达方程表现为Friss传输方程，即

$$
P _ { \mathrm { r } } = { \frac { P _ { \mathrm { t } } \lambda ^ { 2 } G ^ { 2 } | T | ^ { 2 } } { 1 6 \pi H ^ { 2 } } } .
$$

式中， $\boldsymbol { { \cal T } }$ 为两个介质之间界面的反射系数，有

$$
\Gamma = \frac { \sqrt { \varepsilon _ { 1 } } - \sqrt { \varepsilon _ { 2 } } } { \sqrt { \varepsilon _ { 1 } } + \sqrt { \varepsilon _ { 2 } } } .
$$

式中， $\varepsilon _ { 1 }$ 和 $\varepsilon _ { 2 }$ 分别为两层介质的介电常数

由式(4）直接可得大气层和沉积层界面的反射回波功率为

$$
P _ { \mathrm { r 0 } } = \frac { P _ { \mathrm { t } } \lambda ^ { 2 } G ^ { 2 } | T _ { 0 } | ^ { 2 } } { 1 6 \pi H _ { 0 } ^ { 2 } } .
$$

式中， ${ { I } _ { 0 } }$ 为大气层和沉积层界面的反射系数．沉积层和玄武岩层界面的反射回波功率为

$$
P _ { \mathrm { r 1 } } = \frac { P _ { \mathrm { t } } \lambda ^ { 2 } G ^ { 2 } ( 1 - | { \cal { \Gamma } } _ { 0 } | ^ { 2 } ) ^ { 2 } | { \cal { \Gamma } } _ { 1 } | ^ { 2 } } { 1 6 \pi ( H _ { 0 } + H _ { 1 } ) ^ { 2 } L ^ { 2 } } .
$$

回波包括一次反射、两次透射和两次衰减， $( 1 -$ $| { \cal T } _ { 0 } | ^ { 2 } )$ 为电磁波在大气层和沉积层界面处的透射率，${ { T } _ { 1 } }$ 为沉积层与玄武岩界面处的反射系数， $\scriptstyle { \bar { L } }$ 为电磁波在沉积层中的衰减，有

$$
\begin{array} { r l } & { L \approx \frac { \displaystyle \pi f \varepsilon ^ { \prime \prime } H _ { 1 } \sqrt { \frac { \mu } { \varepsilon _ { 1 } ^ { \prime } } } } { \displaystyle c } = \frac { \pi f \mathrm { t a n } \delta H _ { 1 } \sqrt { \mu \varepsilon _ { 1 } ^ { \prime } } } { c } = } \\ & { \qquad \frac { \displaystyle \pi f \mathrm { t a n } \delta H _ { 1 } \sqrt { \varepsilon _ { 1 } ^ { \prime } } } { c } ( \mathrm { N p } ) = } \\ & { \qquad \frac { \displaystyle 8 . 6 9 \pi f \mathrm { t a n } \delta H _ { 1 } \sqrt { \mu \varepsilon _ { 1 } ^ { \prime } } ( \mathrm { d B } ) \approx } { c } } \\ & { \qquad ( \displaystyle 9 . 1 1 \times 1 0 ^ { - 8 } ) f \mathrm { t a n } \delta H _ { 1 } \sqrt { \varepsilon _ { 1 } ^ { \prime } } \ ( \mathrm { d B } ) . } \end{array}
$$

其中, $\boldsymbol { \mathscr { c } }$ 为真空中的光速, $\varepsilon _ { 1 } ^ { \prime }$ 和 $\mu$ 分别为相对介电常数和磁导率， $\mu$ 设为1.式(8）中,

$$
1 \mathrm { N p } = 2 0 \log \mathrm { e d B } = 8 . 6 9 \mathrm { d B } .
$$

因此，根据两个界面回波的功率和相对时延可以确定两层介质的介电特性.对于多层平坦介质，可以按照同样的方法建立各层反射回波模型

# 2.2粗糙表面的几何光学模型

2.1节中假定火星表面是平坦的，但这通常不符合实际情况.以下将建立火星粗糙表面模型.火星的表层呈现大尺度和小尺度粗糙度.由于本文研究的是火星轨道器的遥感测量，大尺度模型已能满足需求对于着陆器或巡视器的次表层雷达，则需要考虑小尺度模型.

火星粗糙表面散射元的高度概率密度满足零均 值高斯分布[13],即

$$
f ( h ) = \frac { 1 } { 2 \pi \sigma _ { h } } \exp \Big ( - \frac { h ^ { 2 } } { 2 \sigma _ { h } ^ { 2 } } \Big ) .
$$

式中， $\sigma _ { h }$ 为本地高程分布的均方根值．本地均方根斜率可由本地均方根波高和相关长度 $\mathbf { \xi } _ { l }$ 导出，即

$$
\sigma _ { \mathrm { s } } ^ { 2 } = \sigma _ { \mathrm { h } } ^ { 2 } | C _ { \mathrm { s } } ^ { \prime \prime } ( 0 ) | = \frac { 2 \sigma _ { \mathrm { h } } ^ { 2 } } { l ^ { 2 } } .
$$

大尺度粗糙表面的散射场主要成分是镜面 (准镜面）反射，在 $0 . 2 { \sim } 1 0 \mathrm { k m }$ 的尺度上, $\sigma _ { \mathbf { s } }$ 一般不超过0.02 rad $\left( 1 ^ { \circ } \right)$

根据经典基尔霍夫近似下的准镜面几何光学模型，回波的散射系数为

$$
\sigma ^ { 0 } ( \theta ) = \frac { | { \varGamma _ { 0 } } | ^ { 2 } } { 2 \sigma _ { \mathrm { s } } ^ { 2 } \cos ^ { 4 } \theta } \exp \Big ( - \frac { \mathrm { t a n } ^ { 2 } \theta } { 2 \sigma _ { \mathrm { s } } ^ { 2 } } \Big ) .
$$

其中， $\theta$ 为电磁波入射角．设偏离天底方向的斜距为 $R$ ，则由几何关系，有

$$
\cos \theta = { \frac { H _ { 0 } } { R } } , \quad \mathrm { t a n } \theta = { \frac { \sqrt { R ^ { 2 } - H _ { 0 } ^ { 2 } } } { R } } .
$$

将式（12）代入式（11）可得

$$
\sigma ^ { 0 } ( R ) = \frac { | { \Gamma _ { 0 } } | ^ { 2 } R ^ { 4 } } { 2 \sigma _ { \mathrm { s } } ^ { 2 } H _ { 0 } ^ { 4 } } \exp \bigg ( - \frac { R ^ { 2 } - H _ { 0 } ^ { 2 } } { 2 H _ { 0 } ^ { 2 } \sigma _ { \mathrm { s } } ^ { 2 } } \bigg ) .
$$

显然，传输距离 $R$ 是时间 $\mathbf { \Psi } _ { t }$ 的函数，即

$$
\begin{array} { l } { { \displaystyle R = \frac { c t } { 2 } , } } \\ { { \displaystyle H _ { 0 } = \frac { c t _ { 0 } } { 2 } . } } \end{array}
$$

以 $t _ { 0 }$ 作为时间轴的零点，设 $t _ { \mathrm { p } } = t - t _ { 0 } \left( t _ { \mathrm { p } } \ll t _ { 0 } \right)$ 则有

$$
R ^ { 2 } - H _ { 0 } ^ { 2 } = \Big ( { \frac { c } { 2 } } \Big ) ^ { 2 } ( t ^ { 2 } - t _ { 0 } ^ { 2 } ) \approx { \frac { c t _ { p } H _ { 0 } } { 2 } } ,
$$

代入式 (11)并化简可得

$$
\sigma ^ { 0 } = \frac { | I _ { 0 } | ^ { 2 } } { 2 \sigma _ { \mathrm { s } } ^ { 2 } } \exp \bigg ( - \frac { c t _ { \mathrm { p } } } { 2 H _ { 0 } \sigma _ { \mathrm { s } } ^ { 2 } } \bigg ) .
$$

根据雷达方程，此时对应的回波峰值功率为

$$
P _ { \mathrm { r } } = { \frac { P _ { \mathrm { t } } G ^ { 2 } \lambda ^ { 2 } \sigma ^ { 0 } A } { ( 4 \pi ) ^ { 3 } H _ { 0 } ^ { 4 } } } ,
$$

式中, $A$ 为电磁波的照射面积.根据Walsh公式[14],脉冲有限足迹直径和照射面积分别为

$$
\begin{array} { l } { \displaystyle { D = 2 \sqrt { H _ { 0 } c \tau \Big ( 1 + \frac { H _ { 0 } } { R _ { \mathrm { M } } } \Big ) } , } } \\ { \displaystyle { A = \pi \Big ( \frac { D } { 2 } \Big ) ^ { 2 } = \pi H _ { 0 } c \tau \Big ( 1 + \frac { H _ { 0 } } { R _ { \mathrm { M } } } \Big ) . } } \end{array}
$$

上式中考虑了火星的曲率， $R _ { \mathrm { m } }$ 为火星半径．将式(16)和(19)代入式(17）可得

$$
P _ { \mathrm { r } } = { \frac { P _ { \mathrm { t } } G ^ { 2 } \lambda ^ { 2 } c \tau | T _ { 0 } | ^ { 2 } } { 8 ( 4 \pi ) ^ { 2 } \sigma _ { \mathrm { s } } ^ { 2 } H _ { 0 } ^ { 3 } } } \Big ( 1 + { \frac { H _ { 0 } } { R _ { \mathrm { m } } } } \Big ) \exp \Big ( - { \frac { c t _ { \mathrm { p } } } { 2 H _ { 0 } \sigma _ { \mathrm { s } } ^ { 2 } } } \Big ) .
$$

这就是粗糙表面的高度计雷达方程．该方程可用于HF高度计地表回波功率的提取.

# 3火星次表层介质分层介电特性仿真

一般地，火星表面和次表层介质都可以用空气、水 (冰)、土壤等的混合物建模.在高于 $\boldsymbol { 1 0 0 \mathrm { k H z } }$ 的频段,该混合介质的介电常数可用下式表示[15]：

$$
\varepsilon _ { \mathbf { m } } = \varepsilon _ { \mathbf { a } } ^ { \phi ( 1 - s ) } \varepsilon _ { \mathbf { w } } ^ { \phi s } \varepsilon _ { \mathbf { s } } ^ { 1 - \phi } .
$$

式中， $\varepsilon _ { \mathbf { m } }$ 为混合物的介电常数； $\varepsilon _ { \mathrm { a } }$ 为空气介电常数，非常近似 $1 ; \varepsilon _ { \mathrm { w } }$ 为水的介电常数; $\varepsilon _ { \mathbf { s } }$ 是固体土壤的介电常数.式中 $\phi$ 为孔性；而水的各种形态(冰、液态纯净水和盐水等)在孔性中所占比例称为饱和度，记为 $s$ (见图3).根据Debye方程[16，有

$$
\begin{array} { r l r } { \displaystyle \varepsilon _ { \mathrm { w } } = \varepsilon _ { \infty } + \frac { \varepsilon _ { \mathrm { s t } } - \varepsilon _ { \infty } } { 1 - \mathrm { j } \omega \tau _ { \mathrm { r } } } = } & { } & \\ { \displaystyle \left[ \varepsilon _ { \infty } + \frac { ( \varepsilon _ { \mathrm { s t } } - \varepsilon _ { \infty } ) } { 1 + ( \omega \tau _ { \mathrm { r } } ) ^ { 2 } } \right] + \mathrm { j } \frac { \omega \tau _ { \mathrm { r } } ( \varepsilon _ { \mathrm { s t } } - \varepsilon _ { \infty } ) } { 1 + ( \omega \tau _ { \mathrm { r } } ) ^ { 2 } } . } \end{array}
$$

火星的表层和次表层介质中富含碎石、瓦砾等这些碎片都是散射体，使得介质内部有更复杂的介电结构.如果对这些碎片边界的散射行为逐一考查，整个散射行为将过于复杂，以至于无法计算．只要碎片 (散射体)在介质中均匀分布，即可以把这些散射体和背景介质等效成单一介质.

Kong推导了球形散射体的等效介电常数[15]：

$$
\varepsilon _ { \mathrm { e } } = \varepsilon _ { \mathrm { b } } \Big [ \frac { 1 + 2 f _ { \mathrm { v } } k _ { \varepsilon } } { 1 - f _ { \mathrm { v } } k _ { \varepsilon } } + \mathrm { j } f _ { \mathrm { v } } ( 2 \pi ) ^ { 4 } .
$$

$$
\Bigl ( \frac { a } { \lambda } \Bigr ) ^ { 3 } \Bigl | \frac { k _ { \varepsilon } } { 1 - f _ { \mathrm { v } } k _ { \varepsilon } } \Bigr | ^ { 2 } \frac { ( 1 - f _ { \mathrm { v } } ) ^ { 4 } } { ( 1 + 2 f _ { \mathrm { v } } ) ^ { 2 } } \Bigr ] ,
$$

其中,

$$
k _ { \varepsilon } = \frac { \varepsilon _ { \mathrm { d } } - \varepsilon _ { \mathrm { b } } } { \varepsilon _ { \mathrm { d } } + 2 \varepsilon _ { \mathrm { b } } } ,
$$

$\varepsilon _ { \mathbf { b } }$ 为背景介电常数， $\varepsilon _ { \mathrm { d } }$ 为散射体 (碎片)的介电常数，$f _ { \mathrm { v } }$ 为碎片的体占比， $\alpha$ 为散射体半径， $\lambda$ 为电磁波波长．式(23)虽然是针对球形散射体推导的，但对于大体光滑的一般形状碎片也是适用的.火星表面的碎片基本是随机分布的，因此可用式(23）对含碎片的介质介电常数进行建模

根据火星特点，仿真模拟了两种情形下的介质分层模型，并计算了每层的介电常数实部和损耗正切

情形1浅层渗流．其 $1 6 0 \mathrm { m }$ 以下的水相是盐水，可以看到，盐水成分的损耗正切很大，在此情况下电磁波的穿透深度受到很大局限，

情形2典型冻土区．该地貌最大的特点是50米以下有一层很深的冰透镜体，表现为纯冰．其损耗正切比分凝冰更小 (0.0012)，电磁波在其中的穿透深度最深．冰透镜体和分凝冰都是火星探测中很重要的固态水探测要素.

仿真结果列于表2和表3.表中给出了各层的孔性、饱和度、水相(水相为0代表空气,1代表冰,2代表液态水，3代表盐水)、介质材料等的参数作为输入参数.输出参数为介电常数实部和损耗正切.在仿真中,假定大部分介质的铁氧体含量为 $1 0 \%$ ，直径 $0 . 1 \mathbf { m }$ 的碎片体占比为 $5 \%$

# 4回波仿真结果

为了验证火星次表层分层介质模型和反演方法，对以上两种情形的回波进行了仿真.HF高度计对各层的分辨率如图4所示.由图4中可见，各层的分辨

![](images/fb7f744e8c4cae533b52f97c7d04475af6022be9a8faf154c7d5657cb817d27b.jpg)  
图3火星表层内含空气、水 (冰)、土壤的介质模型Fig.3Mars media model containing air,water (ice) and soil

![](images/434d30c24feabf66b0228fd8972bc2f9b2e97531e5ab64f2a42e29aa2c6eaf51.jpg)  
图4各层垂直分辨率  
Fig.4Vertical resolutions of each layer

# 表2情形1介电常数仿真结果 (20层)

Table 2 Dielectric constant simulation results of Case 1 (20 layers)   

<html><body><table><tr><td>层数</td><td>距表面高度/m</td><td>孔性/(%)</td><td>饱和度/(%)</td><td>水相</td><td>介质材料</td><td>介电常数实部</td><td>损耗正切</td></tr><tr><td>1</td><td>1</td><td>50</td><td>0</td><td>0</td><td>风沉积层</td><td>2.9922</td><td>-0.0053</td></tr><tr><td>2</td><td>3</td><td>15</td><td>0</td><td>0</td><td>硬沉积层</td><td>5.9524</td><td>-0.0086</td></tr><tr><td>3</td><td>5</td><td>50</td><td>0</td><td>0</td><td>沉积玄武岩</td><td>2.9922</td><td>-0.0053</td></tr><tr><td>4</td><td>10</td><td>5</td><td>0</td><td>0</td><td>致密玄武岩</td><td>7.2482</td><td>--0.0095</td></tr><tr><td>5</td><td>100</td><td>10</td><td>0</td><td>0</td><td>分层玄武岩</td><td>6.5680</td><td>-0.0091</td></tr><tr><td>6</td><td>110</td><td>50</td><td>100</td><td>1</td><td>风沉积层</td><td>5.1839</td><td>-0.0058</td></tr><tr><td>7</td><td>150</td><td>10</td><td>50</td><td>1</td><td>分层玄武岩</td><td>6.9401</td><td>-0.0091</td></tr><tr><td>8</td><td>152</td><td>20</td><td>0</td><td>0</td><td>冲积沉积层</td><td>5.3951</td><td>-0.0081</td></tr><tr><td>9</td><td>160</td><td>50</td><td>0</td><td>0</td><td>火山灰</td><td>2.9922</td><td>-0.0053</td></tr><tr><td>10</td><td>200</td><td>10</td><td>100</td><td>3</td><td>分层玄武岩</td><td>12.9450</td><td>-0.1544</td></tr><tr><td>11</td><td>220</td><td>20</td><td>100</td><td>3</td><td>火山口溅射物</td><td>20.5938</td><td>-0.3089</td></tr><tr><td>12</td><td>250</td><td>10</td><td>20</td><td>3</td><td>分层玄武岩</td><td>7.5303</td><td>-0.0376</td></tr><tr><td>13</td><td>255</td><td>50</td><td>20</td><td>3</td><td>风沉积层</td><td>5.8696</td><td>-0.1484</td></tr><tr><td>14</td><td>350</td><td>10</td><td>20</td><td>3</td><td>分层玄武岩</td><td>7.5303</td><td>-0.0376</td></tr><tr><td>15</td><td>355</td><td>20</td><td>20</td><td>3</td><td>冲积沉积层</td><td>7.0831</td><td>-0.0651</td></tr><tr><td>16</td><td>500</td><td>10</td><td>20</td><td>3</td><td>分层玄武岩</td><td>7.5303</td><td>-0.0376</td></tr><tr><td>17</td><td>750</td><td>10</td><td>20</td><td>3</td><td>分层玄武岩</td><td>7.5303</td><td>-0.0376</td></tr><tr><td>18</td><td>760</td><td>50</td><td>20</td><td>3</td><td>火山灰</td><td>5.8696</td><td>-0.1484</td></tr><tr><td>19</td><td>900</td><td>10</td><td>20</td><td>3</td><td>分层玄武岩</td><td>7.5303</td><td>-0.0376</td></tr><tr><td>20</td><td>1000</td><td>10</td><td>20</td><td>3</td><td>分层玄武岩</td><td>7.5303</td><td>-0.0376</td></tr></table></body></html>

率位于 $\mathsf { 5 } \mathord { \sim } 1 0 \mathrm { m }$ ，各层的衰减如图5所示，可以看到，情形2中第6层 (冰透镜体)的衰减远比其他层低(约为 $0 . 0 1 \mathrm { d B } { \cdot } \mathrm { m } ^ { - 1 }$ )，因此高度计电磁波在冰层中可穿透更深的深度.

根据式(2）可求出每两层之间反射回波对应的延迟，对式(6)和式(7）进行推广，可得各层之间界面反射回波对应的回波功率.将这些延迟与功率对应起来可得到回波波形，如图6所示.纵坐标的功率值

# 表3情形2介电常数仿真结果（8层）

Table3 Dielectric constant simulation results of Case 2 (8 layers)   

<html><body><table><tr><td>层数</td><td>距表面高度/m</td><td>孔性/(%)</td><td>饱和度/(%)</td><td>水相</td><td>介质材料</td><td>介电常数实部</td><td>损耗正切</td></tr><tr><td>1</td><td>1</td><td>50</td><td>0</td><td>0</td><td>风沉积层</td><td>2.9922</td><td>-0.0053</td></tr><tr><td>2</td><td>3</td><td>15</td><td>0</td><td>0</td><td>硬沉积层</td><td>5.9524</td><td>-0.0086</td></tr><tr><td>3</td><td>5</td><td>50</td><td>100</td><td>1</td><td>沉积玄武岩</td><td>5.1839</td><td>-0.0058</td></tr><tr><td>4</td><td>50</td><td>10</td><td>100</td><td>1</td><td>致密玄武岩</td><td>7.3336</td><td>-0.0092</td></tr><tr><td>5</td><td>55</td><td>50</td><td>100</td><td>1</td><td>沉积玄武岩</td><td>5.1839</td><td>-0.0058</td></tr><tr><td>6</td><td>205</td><td>100</td><td>100</td><td>1</td><td>冰透镜体</td><td>3.2000</td><td>-0.0012</td></tr><tr><td>7</td><td>225</td><td>20</td><td>100</td><td>1</td><td>冲积沉积层</td><td>6.7234</td><td>-0.0083</td></tr><tr><td>8</td><td>1000</td><td>10</td><td>100</td><td>1</td><td>分层玄武岩</td><td>7.3336</td><td>-0.0092</td></tr></table></body></html>

![](images/64bfd3f587b37efff15941b3868c574fe9625c4383b467d61806c7fe8c4e0e57.jpg)  
Fig.5 Attenuations of each layer

![](images/acf74b15855dd55ce03c5ee7201f156fb6989bce52a44d1fdd8b3a33a065298e.jpg)  
图5各层的衰减  
图6各层回波波形 (冲击脉冲) Fig.6Echo waveform of each layer (impulse)

已转换为dBm，横坐标利用系统的压缩脉冲宽度 $( 1 / 1 0 \mathrm { M H z } = 1 0 0 \mathrm { n s } )$ 进行了归一化，对应于回波的时间分辨单元.

图6的仿真中将高度计脉冲看为冲击脉冲，没有考虑雷达系统点目标响应的影响，无限光滑平面的反射行为可看做点目标，而在高度计系统中使用了

![](images/a7ad58bb2f1ec025547b68b359ecfd8e9b8a53a8f8ba5082d2ee70b84e0def43.jpg)  
图7各层回波波形(实际点目标响应） Fig.7 Echowaveform of each layer (actual PTR)

全去斜脉冲压缩技术，其点目标响应对应于sinc函数[17]；通常为了数学表达和推导的简便，可将其表示为高斯函数形式，即

$$
S _ { \mathrm { r } } ( t ) = A \exp \Big ( - \frac { t ^ { 2 } } { 2 \sigma _ { \mathrm { p } } ^ { 2 } } \Big ) ,
$$

式中， $A$ 为归一化幅度； $\sigma _ { \mathrm { p } } = k \tau , \tau$ 为系统的压缩脉冲宽度（带宽的倒数， $1 0 0 \mathrm { n s } \dot { }$ ： $k$ 为点目标响应等效高斯函数的比例因子，根据Jason高度计团队的研究结果，取k=0.513[18].

因此，高度计接收到的总的回波功率

$$
P _ { \mathrm { r } } ( t ) = \sum _ { i = 0 } ^ { n } { P _ { \mathrm { r } , i } \exp \Big [ - \frac { ( t - t _ { i } ) ^ { 2 } } { 2 \sigma _ { \mathrm { p } } ^ { 2 } } \Big ] } ,
$$

式中， $n$ 为介质的层数， $P _ { \mathrm { r } , i }$ 为第 $i$ 层介质底部的反射功率， $t _ { i }$ 为第 $i$ 层介质底部回波对应的延迟

根据式（26）得到的高度计回波波形如图7所示从图6和图7可以看到，在情形1中，由于次表层 $2 0 0 \mathrm { m }$ 左右的介质介电常数过大（实部大于10，虚部接近2)，电磁波急剧衰减，更深的次表层难以探测．而在情形2中，由于系统分辨率的限制，1\~3层和4\~5层实际上表现为1个峰.冰层位于第 $1 0 { \sim } 2 5$ 个回波单元之间.冰层以下的反射功率明显降低很多.这是因为冰层以下的反射系数明显降低，且衰减增高．因此通过回波下降的幅度和持续的延迟可识别冰层的分布.

以上讨论的是理想光滑分层界面的回波，当表面或各层介质之间的界面为粗糙时，就要考虑如式（10）所示的粗糙度等参数，实际的回波功率会降低.但这里仿真的是单脉冲回波功率，对于多脉冲回波功率还可以进行累积.对于传统模式，回波功率的累积是非相关的，回波功率要乘以累积脉冲数的平方根；对于合成孔径模式，累积是相关的，回波功率要乘以累积脉冲数.

# 5结论

介绍了HF雷达高度计系统的原理和参数设计，推导了高度计电磁脉冲和多层光滑介质之间的相互作用，并提取其回波功率随时间变化的模型，同时考虑了表明粗糙度对表面回波功率的影响.选用两种典型的火星分层介质模型，并对其各层的介电常数特性和高度计回波时间延迟、功率衰减和波形形状等进行了仿真.仿真结果表明，采用HF雷达高度计系统可以实现对火星次表层介电特性垂直廓线的反演从而实现对火星中的水（包括固态水和液态水）的识别和探测.HF高度计对于火星次表层的探测具有有重要意义，在今后中国自主火星探测中可考虑选用该有效载荷.

# 参考文献

[1]JinYaqiu,FaWenzhe,XuFeng.Overviewoftheadvance forMars exploration using microwave remote sensing[J]. ChinaJ.Space Sci.,2008,28(3):264-272.In Chinese(金 亚秋，法文哲，徐丰，火星探测的微波遥感技术[J].空间科学学 报，2008,28(3):264-272)   
[2]Jiao Weixin,ZouHong.PlanetarySciences[M].Beijing: PekingUniversityPress,20o9.InChinese(焦维新,邹鸿 行星科学[M].北京：北京大学出版社，2009) [3] Panel on Frequency Allocations and Spectrum Protection for Scientific Uses,Committee on Radio Frequencies,National Research Council. Handbook of Frequency Allocations and Spectrum Protection for Scientific Uses [M]. Washington DC:National Academies Press,2007 [4] Chelton D B,Walsh E J,MacArthur J L.Pulse compression and sea level tracking in satellite altimetry [J].J. Atmos.Ocean.Tech.,1989(6):407-438 [5] Xu Xiyu,Liu Heguang,Liu Peng.Engineering design of the rain mode on an ocean-dedicating radar altimeter [Cl//20i0 International Conference on Microwave and Millimeter Wave Technology (ICMMT).Chengdu:IEEE,   
2010:1719-1722 [6] Picardi G,Biccari D,Cartacci M,et al.MARSIS,aradar for the study of the Martian subsurface in the Mars Express mission[J].Mem.S.A.It.Suppl.,2007,11:15-25 [7] Picardi G,Plaut J J,Biccari D,et al. Radar soundings of the subsurface of Mars [J]. Science,2005,310:1925-1928 [8]Seu R,Biccaria D,Orosei R,et al.SHARAD:The MRO   
2005 shallow radar[J]. Planet.Space Sci.,2004,52(1-   
3):157-166 [9] Seu R,Phillips RJ,Biccari D,et al. SHARAD sounding radar on the Mars reconnaissance orbiter [J].J.Geophys. Res.,2007,112(E5):1-18   
[10] ESRIN ESA,Mullard Space Science Laboratory,University College London.Cryosat product handbook [R]. 2012   
[11] Harry M J.Ground Penetrating Radar: Theory and Application [M].Singapore:Eisevier,2009   
[12] Squyres S W,Clifford S M,Kuzmin R O,et al.Ice in the Martian regolith [M]//Mars.Tucson:University of Arizona Press,1992:557-593   
[13] Woodhouse I H.Microwave remote sensing [M]. London: Taylor&Francis,2006   
[14] Brown G S.The average impulse response of a rough surface and its applications [J].IEEE Trans.Antenn. Prop, 1977，AP-25:67-74   
[15]KongJA.Electromagnetic Wave Theory [M].New York: John Wiley& Sons,1986   
[16] Yin Zhiwen.Physics [M].Beijing: Science Press,2003.In Chinese (殷之文.电介质物理学[M].北京：科学出版社,2003)   
[17] Xu Xiyu,Xu Ke,Wang Zhenzhan. Generation of the HY2 satellite altimeter look-up table to account for the PTR and LPF features [C]//IGARSS Proceedings.Melbourne: IEEE GRSS,2013:2017-2020   
[18] Thibaut P,Amarouche L,Zanife O Z,et al. Jason-1 altimeter ground processing look-up correction tables [J]. Marine Geod.,2004,27(3/4):409-431