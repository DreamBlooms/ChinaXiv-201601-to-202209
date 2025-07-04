编号：163716

# 基于多尺度量纲统一原则的油藏孔隙分形输运特性研究

王志国1,2 张聪慧1 贾永英1,²尹柴玲」　刘晓燕 1,2

163318)

摘要：油藏孔隙分布具有分形特征，如何将分形描述方法应用到油藏多孔介质内流体的输运特性研究过程中，目前的研究方法存在一定局限，主要是没有考虑量纲统一原则和尺度效应等。本文基于量纲统一原则，利用分形描述方法，对油藏多孔介质内输运过程渗透率和渗流流量进行了推导，得到了输运特性参数的单位尺度转换系数，据此可以实现基于微观分形特征描述来分析宏观输运过程。本文建立的分形输运描述方程能够实现不同尺度层级间的转换，得到的宏观特性参数结果更接近实测值。基于本文所建模型，利用某油藏数据进行了分析验证，得到了输运流量及渗透率变化规律与实际油藏的分布规律吻合。

关键词：输运特性；分形；量纲统一；尺度转换；油藏孔隙 中图分类号：TE31 文献标识码：A

# Study on the fractal transport characteristics of reservoir pore based on the principle of multi dimension unity

WANG Zhi-Guo1,2 ZHANG Cong-hui1JIA Yong-Ying1,2 YIN chai-ling1 LIU Xiao-yan1,2

(1. Civil Engineering College,Northeast Petroleum University,Daqing,163318, China; 2. Heilongjiang Key LaboratoryofDisaster Prevention, Mitigation and Protection Enginering,Northeast Petroleum University,Daqing,163318,China)

Abstract:The reservoir pore distribution has fractal characteristics.How to apply the fractal description method to the transport properties of the fluid in the porous medium of the reservoir,the current research methods have some limitations,which is mainly without considering the principle of dimensional unification and scale effect etc.In this paper,based on the principle ofdimensional unification, the permeability and seepage flow in the porous media are deduced byusing the fractal description method.The unit scale conversion coefficients of transport characteristics are obtained, which can be used to analyze the macroscopic transport process basis of microscopic fractal characteristics.In this paper,the fractal transport equation can be used to achieve the conversion between diferent scale levels,and the results of the macroscopic characteristic parameters are closer to the measured values.Based on the model established in this paper,the data of a reservoir are analyzed and verified.The variation law of the transportation flow and the permeability is consistent with the distribution rule of the actual reservoir.

Key words:Transport characteristics; Fractal; Dimensional unification; Scale conversion; Reservoir pore

# 0引言

气体、电、热、声、波等在多孔介质里的传递[I]。有关多孔介质中流体输运特性的研究通常与油藏开采相关联，主要在于油藏储层介质的特性可以直接所谓多孔介质的输运是指在孔隙中的液体、或间接地反映出地下油藏的情况，据此可以理解和预测地下油藏动态，进而达到提高油气采收率目的[2]。

对孔隙结构的研究可追溯至20世纪20年代，由Nutting[3]首次通过毛细管曲线理论结合铸体薄片的方法研究储层的孔隙特征。此后，人们逐渐意识到实际油藏的孔隙结构相当复杂，用传统的数学基础方法并不能很好地描述出真实的油藏孔隙概况。20世纪80年代B.B.Mandelbrot[4]在总结了自然界中非规则图形后，首次提出分形这个概念，可以用来处理极不规则的复杂形体。此后，一些研究表明储层岩石的宏观和微观空间都具有良好的分形特征。Avnir等[5]利用分子吸附法证明了储层岩石的孔隙结构具有分形性质；Katz 和Thompson 等[6-8]利用扫描电镜观察岩石断面，发现各种砂岩、页岩及碳酸盐岩在3到4个数量级的范围内是自相似的，可用分形维数来描述孔隙的结构特征，其值在 $2 . 5 5 { \sim } 2 . 8 7$ 之间，统计自相似的尺度范围在0.2μm到50μm之间，之后他们通过统计分形的方法预测了岩石的孔隙度的值，证明与实测值基本吻合；Hansen[9]通过盒维数得出砂岩的体积分形维数和表面分形维数以及分维与岩石渗透率的关系，证明岩石的渗透率依赖于分形维数的大小。Kim Tae H[10]等基于分形理论开发出分形离散裂缝网络代码，建立FDFN（分形离散网络）模型，获得油藏孔隙度值；XieSY等[11]利用电子显微镜呈现二维图像，及盒维数和多重分形参数计算分形维数，建立它们与油藏孔隙度和渗透率的关系，评估不同地层的油藏储量。

随着科学技术的进步和油气勘探不断发展深入，国内的学者也在努力探索中。同登科等[12]使用分形维数与分形指数来描述分形油藏的渗流特征，并分析了分形参数对分形油藏压力的影响，得出的预测结果与实际油藏的原始资料很接近；郁伯铭等[1采用分形理论和方法建立油藏多孔介质的分形渗流模型，推导各参数的分形计算公式，得出解析解；刘俊亮等[13]人根据分形基本概念，利用Sierpinski就分形多孔介质的孔隙率、渗透率等特征参数进行推导，讨论了不同分形模型下渗透率一分形维数的关系与它们的差异；孔祥言等人[14]对双重分维的多孔介质导出了油藏渗流速度、渗透率及孔隙率的公式，绘制了油藏地层的样板曲线用以分析油井；王自明等[15]把碳酸盐岩储层裂缝的分形特征与渗透率数据结合，建立了该储层渗透率的变异函数，并证明与实际情况吻合；刘波[16等利用压汞毛管压力数据得出低渗透油田储层岩石的分形维数，并与其他描述岩石非均质性的参数进行对比，得出平均分形维数越大，多孔介质的非均质性越强，油田产量越低、含水率越高；于本福等人[17]建立了油藏压力分布的分形渗流模型，推导出动态储层压力的预测公式，得出分形维数对储层压力的影响。

综上所述，基于分形理论来研究油藏多孔介质内流体的输运特性问题，研究者们主要是通过建立分形油气藏渗流模型，近似描述油藏地质孔隙结构，并且取得了一定的科研成果。但是实际孔隙结构的内部属性和空间分布都存在不均匀的变化，决定了多孔介质的结构特性在空间不同的方向上会存在变异性，如一些大的孔隙尺度为毫米或厘米层级，而微小孔隙只有纳米或微米层级那么大，因此孔隙的尺寸会跨越几个尺度层级，从分子尺度到微观尺度，或者是从微观尺度到宏观尺度上的差异。虽然储层孔隙在不同尺度范围内都具有分形特征，但对油藏输运特性的影响区别很大，即大尺度下表现的是油藏孔隙整体的性质和规律，而小尺度则是局部的体现。这使得简单的将两者结合来分析油藏会存在分形尺度效应问题，即在一个尺度层级下总结的规律在另一个尺度层级并不一定适用，从而使计算结果与实际的值会有较大的偏离。鉴此，本文基于量纲统一原则，利用分形描述方法，推导油藏多孔介质内输运过程模型方程，并进行实际分析。

# 1分形渗流一般描述方法

多孔介质的输运特性是由一系列特征参数来描述的，其中最重要的两个物性参数是孔隙度和渗透率，因此对这两个量的分析是研究者们关注的重要问题之一。渗透率、孔隙度及其关系式决定于多孔介质的微观孔隙结构，经过人们研究发现，天然形成的多孔介质和部分人工制造的多孔材料的微结构具有分形特征。借助分形几何理论，提出了多种理论模型来描述多孔介质的微结构，建立多孔介质输运问题与分形维数的关系。

渗透率与孔隙率 $\phi$ 、分形维度 $D _ { f }$ 等参数存在一定的函数关系，关系式表示如下

$$
K = K { \big ( } \phi , D _ { f } \ldots \ldots { \big ) }
$$

根据流体的流动状态，利用毛细管束模型推导得出渗透率的表达式为[5]

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

$$
K = \frac { N D _ { f } } { 8 \tau } \Bigg ( \frac { 1 - \delta ^ { 5 - D _ { f } } } { \delta ^ { - D _ { f } } - 1 } \Bigg ) \frac { \lambda _ { \mathrm { m a x } } ^ { 5 } } { 5 - D _ { f } }
$$

式（2）中， $N$ 为单元体多孔介质的弯曲毛细管或孔隙的总数。定义 $\tau = L _ { e } / L$ 为多孔介质的平均迁曲度，即毛细管或孔道的实际长度与宏观长度的比值。 $\delta = \lambda _ { \operatorname* { m i n } } / \lambda _ { \operatorname* { m a x } }$ 为孔介质中最小和最大孔隙半径之比。在该方程中，对总数 $N$ 求取中的一些系数，没有明确概念，也无从知晓怎样得到；对平均迁曲度 $\tau$ 定义不明确，此推导不够精确。

第二种模型是多孔介质渗流力学模型，从渗流力学的角度出发，利用Fanning摩擦系数 $f$ 与雷诺数 $R _ { e }$ 在一定条件下呈现的对数线性关系，得到渗透率表达式[6]

$$
K = { \frac { N D _ { f } } { 2 c } } \left( { \frac { D _ { f } } { 2 - D _ { f } } } \right) \left( { \frac { 1 - \lambda ^ { 2 - D _ { f } } } { \lambda ^ { - D _ { f } } - 1 } } \right) \left( { \frac { 1 - \lambda ^ { 3 - D _ { f } } } { \lambda ^ { - D _ { f } } - 1 } } \right) { \frac { \lambda _ { \operatorname* { m a x } } ^ { 5 } } { 3 - D _ { f } } }
$$

式（3）中， $\mathbf { \Psi } _ { c }$ 为常数，可以由摩擦系数 $f$ 和雷诺数 $R _ { e }$ 求出。但公式需要限制条件，即 $R _ { e } < 5$ 的情况下，一方面对多孔介质中渗流速度等有限定，另一方面提出的相关公式并未与实验结果进行比较，无法得到验证。

对渗透率的研究郁伯铭等[I通过建立分形分析解模型，结合哈根一泊萧叶方程，导出多孔介质总流量的关系表达式

$$
\begin{array} { l } { \displaystyle { \mathcal { Q } = - \int _ { \lambda _ { \mathrm { m i n } } } ^ { \lambda _ { \mathrm { m a x } } } q ( \lambda ) d N ( \lambda ) } } \\ { \displaystyle { = \frac { \pi } { 1 2 8 } \frac { \Delta P } { \mu } \frac { D _ { f } } { L ^ { D _ { T } } \left( 3 + D _ { T } - D _ { f } \right) } \lambda _ { \mathrm { m a x } } ^ { 3 + D _ { T } } \times \left[ 1 - \left( \frac { \lambda _ { \mathrm { m i n } } } { \lambda _ { \mathrm { m a x } } } \right) ^ { 3 + D _ { T } - D _ { f } } \right] } } \end{array}
$$

式中， $\Delta P$ 为进出口两端压力差， $\mu$ 为流体的黏度系数， $L$ 为弯曲毛细管或孔隙的直观长度，$D _ { f }$ 指多孔介质的分形维数， $D _ { T }$ 是迁曲度分形维数。

由流量公式结合达西定律得到渗透率的函数关系表达式

$$
K = \frac { \mu L Q } { \Delta P A } = \frac { \pi } { 1 2 8 } \frac { L ^ { D _ { T } - 1 } } { A } \frac { D _ { f } } { 3 + D _ { T } - D _ { f } } \lambda _ { \mathrm { m a x } } ^ { 3 + D _ { T } }
$$

式中， $A$ 是某个单元体的横截面积。

公式（5）中没有经验常数，且每一个参数都有确定的物理意义，但美中不足的是推导的公式中都没有考虑单位尺度需要统一的问题。即不了解孔隙变化规律和对尺度的依赖性，只是单纯的自行代入各个相关参数，随意取值，缺少理论依据，而且会产生数据量纲的不统一问题，这势必与实际产生的结果造成偏离。因为渗透率、流量等特性参数是描述宏观多孔介质的，而分形维数是表征微观孔隙结构，在已知某一尺度下的性质，来求另一尺度下的性质时，需要一个媒介来使微观尺度的描述和宏观尺度计算的量纲达到统一。也就是本文研究的要点，在考虑单位尺度层级统一转换的基础上，对以上提到的某一公式加以修正，得出单位尺度转换系数，减小误差，以更加接近真实值。

# 2基于量纲统一原则的分形渗流描述方法

前述描述方法存在一定缺陷。首先，在单根毛细管流量的表达式中涉及到两个不同尺度层级的参数，即毛管长度L属于宏观尺度，毛细管管径λmax是微观尺度，而宏观与微观对孔隙特性的影响区别很大。其次，在公式推导过程中，并没有对公式中每一个特征参数的量纲尺度下定义。因此在反映孔隙中流量的分布规律时，该公式的右边没有保持量纲的一致性和单位的一致性。根据这一原理，此渗流基本公式是不完整不完善的。那么，二者结合在整个公式中的计算时，必须将各项达到量纲的统一，需要存在一个某尺度下的量纲转换系数。

从最初含有长度 $L$ 和管径 $\lambda _ { \operatorname* { m a x } }$ 的方程式入手，统一为宏观尺度，得到如下关系式

$$
\dot { L _ { e } } = \left( \frac { L } { k \lambda } \right) ^ { D _ { T } } k \lambda = k ^ { 1 - D _ { T } } L ^ { D _ { T } } \lambda ^ { 1 - D _ { T } } = k ^ { 1 - D _ { T } } L _ { e }
$$

$k$ 代表任意不同尺度层级间需要达到一致的数量级，它由人为制定的尺度与国际化统一量纲的关系确定。

将转换后的毛管长度方程代入流量方程可得到

$$
\begin{array} { r l } { \dot { q ^ { * } } ( \lambda ) = \frac { \pi } { 1 2 8 } \frac { \Delta P } { L _ { e } ^ { * } ( \lambda ) } \frac { ( k \lambda ) ^ { 4 } } { \mu } } & { { } = \frac { \pi } { 1 2 8 } \frac { \Delta P } { \mu } \frac { \left( k \lambda \right) ^ { 4 } } { k ^ { 1 - D _ { T } } L _ { e } } } \end{array}
$$

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

$$
\begin{array} { l l } { { \displaystyle { \vphantom { \displaystyle { \frac { \pi } { 1 2 8 } \frac { \Delta P } { \mu } } \frac { ( k \lambda ) ^ { 4 } } { k ^ { 1 - D _ { r } } L ^ { D _ { r } } \lambda ^ { 1 - D _ { r } } } } } } } & { { } } \\ { { \mathrm { } } } \\ { { \displaystyle { \vphantom { \frac { \pi } { 1 2 8 } \frac { \Delta P } { 1 2 8 } \frac { \Delta P } { \mu } \frac { \lambda ^ { 4 } } { L ^ { D _ { r } } \lambda ^ { 1 - D _ { r } } } } } } } & { { \mathrm { } = k ^ { 3 + D _ { r } } q \big ( \lambda \big ) } } \end{array}
$$

单元体截面的流量为

$$
\begin{array} { l } { { \displaystyle { \mathcal { Q } ^ { ' } = - \int _ { \bar { \lambda } _ { m a x } } ^ { \bar { \lambda } _ { m a x } } ( \lambda ) d N ( \lambda ) } } } \\ { { \displaystyle { } } } \\ { { = - k ^ { 3 + D _ { T } } \int _ { \bar { \lambda } _ { m a x } } ^ { \bar { \lambda } _ { m a x } } \frac { \pi } { 1 2 8 } \frac { \Delta P } { \mu } \frac { \lambda ^ { 4 } } { L ^ { { D _ { T } } } \lambda ^ { 1 - D _ { T } } } { \times } { D _ { f } \lambda _ { m a x } ^ { D _ { f } } } \lambda ^ { - \left( D _ { f ^ { * } } + 1 \right) } d \lambda } } \\ { { \displaystyle { } } } \\ { { \displaystyle { } = k ^ { 3 + D _ { T } } \frac { \pi } { 1 2 8 } \frac { \Delta P } { \mu } \frac { \Delta P } { L ^ { D _ { f } } \left( 3 + D _ { T } - D _ { f } \right) } \lambda _ { m a x } ^ { 3 + D _ { T } } = k ^ { 3 + D _ { T } } Q } } \end{array}
$$

定义 $\boldsymbol { K } _ { \boldsymbol { q } } = \boldsymbol { k } ^ { 3 + D _ { T } }$ ，称为流量尺度转换系数。利用Dancy定律，渗透率的公式为

$$
K = { \frac { \mu L Q } { \Delta P A } }
$$

由达西定律可以知道，公式中的相关物理量都是宏观物理量，因此不存在尺度层级，直接代入流量 $\boldsymbol { \mathcal { Q } } ^ { ' }$ ，得到如下新的渗透率公式

$$
K ^ { ' } = \frac { \mu L Q ^ { ' } } { \Delta P A } = k ^ { 3 + D _ { T } } \frac { \mu L Q } { \Delta P A } = k ^ { 3 + D _ { T } } K
$$

由此得到，分形渗透率公式的转换系数$\boldsymbol { K } _ { K } = \boldsymbol { K } _ { q } = \boldsymbol { k } ^ { 3 + D _ { T } }$ 。

该修正公式的意义在于，在描述宏观物理特性时，优先考虑某量纲尺度下数值的计算，然后与尺度转换系数结合，达到方程两边量纲统一的目的。

# 3修正后分形渗流基本公式的验证及应用

基于本文建立的油藏多孔介质的流量和渗透率模型方程，对4种岩心的宏观输运特性参数流量和渗透率进行数值计算，据此分析微观孔隙特征对宏观输运参数的影响规律。

# 3.1实验数据及基本参数

本文采用4个不同油田岩心资料进行数值计算，并将修正方程的计算值与原公式以及实测值进行比较。这些样品包括3种砂岩和一种碳酸盐岩，其原始三维数据是通过微CT扫描成像系统采集得到的，能直观描述岩心特性。图1为砂岩B1数字岩心的三维图像，图像中无色透明的部分代表孔隙，有颜色的代表固体骨架， $X , Y , Z$ 分别代表不同的方向；图2为B1在 $Z$ 方向上二维截图所得到的图像，其中白色为孔隙，黑色则是固体。

通过计算岩心的基本物理参数，从而更加精确的描述分析油藏。实验数据及基本参数如表1所示。

# 3.2分形维数

以B1岩心为例，对修正公式进行验证。首先由扫描设备得到所需数据如下：最小、最大孔隙直径 $\lambda _ { \operatorname* { m i n } } = 5 . 3 4 5 \mu m$ 、 $\lambda _ { \operatorname* { m a x } } = 1 2 5 . 6 0 8 \mu m$ ，孔隙度$\phi = 0 . 1 9 6$ ，渗透率 $K = 1 2 8 6 m D$ ，岩样宏观长度$L _ { 0 } = 2 . 1 3 8 m m$ ，取动力粘度 $\mu { = } 1 m P a \cdot s$ ，压差$\Delta P = 1 P a$ 0

根据微观参数，计算出孔隙分布的分形维数$D _ { f }$ 为2.484；迁曲度分形维数 $D _ { T }$ 为1.198。另外，其余3组岩心与此相似，不再累述。

![](images/dd793de23e622b66a9a9b72390f85a8f77ad57a699994a33e887620ac9062862.jpg)  
图1砂岩B1的三维扫描图像（像素分辨率5.34μm，样品尺寸 $2 . 1 3 8 m m$ ）  
Fig.1The three dimensional scanning image of sandstone B1 (Pixel resolution 5.34 μm , Sample size 2.138 mm )

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/18e35f8ff6952ad8b41d4c1c879c3a52e43bf93d9ea5de58b36453475ab59be7.jpg)  
图2砂岩B1的二维截面  
（像素分辨率5.34um，样品尺寸2.138mm） Fig.2The two dimensional section of sandstone B1 (Pixel resolution 5.34 μm , Sample size 2.138 mm )

Table 1 Experimental data and basic parameters of   

<html><body><table><tr><td colspan="5">4 core samples</td></tr><tr><td>岩样号</td><td>尺寸 mm</td><td>最小孔 径μm</td><td>最大孔 孔隙度 径μm</td><td>渗透率 mD</td></tr><tr><td>SandstoneB1</td><td>2.138</td><td>5.345</td><td>125.608</td><td>0.196 1286.0</td></tr><tr><td>CarbonateC1</td><td>1. 140</td><td>2.850</td><td>96.900 0.233</td><td>1102.0</td></tr><tr><td>SandstoneS1</td><td>1. 486</td><td>4. 956</td><td>133.812 0.246</td><td>3898.0</td></tr><tr><td>SandstoneS4</td><td>1.44</td><td>4.803</td><td>148.893 0.250</td><td>6966.0</td></tr></table></body></html>

# 3.3修正前后对比计算分析

根据前述已有的公式和修正后的模型，进行了计算渗流流量和渗透率的对比计算，详见表2及表3。由以上数值计算，可以得到以下结论：

（1）通过比较微米尺度与毫米尺度下流量和渗透率的值，得出当参数取值在不同尺度层级时，计算结果会产生不同程度的误差，即存在尺度效应问题。这是因为油藏多孔介质非均质性的存在，使得空间不同位置上有不同尺度大小的孔隙结构；

表14种岩心样品实验数据及基本参数  

<html><body><table><tr><td>序号</td><td>岩样</td><td>流量原值 106μm3/s</td><td>微米尺度 Qum</td><td>偏差 ,%</td><td>毫米尺度 Qmm</td><td>偏差 ,%</td><td>修正流量 Q</td><td>偏差 ,%</td></tr><tr><td>1</td><td>B1</td><td>2.484</td><td>2.36</td><td>14. 18</td><td>2.33</td><td>15.27</td><td>2. 765</td><td>-0.55</td></tr><tr><td>2</td><td>C1</td><td>1.256</td><td>2.04</td><td>-62.4</td><td>2.037</td><td>-62. 14</td><td>1. 752</td><td>-39.5</td></tr><tr><td>3</td><td>S1</td><td>5.792</td><td>5. 677</td><td>1. 98</td><td>5.667</td><td>2. 17</td><td>5.788</td><td>0.07</td></tr><tr><td>4</td><td>S4</td><td>10.03</td><td>8.952</td><td>10.7</td><td>8.944</td><td>10.84</td><td>9.524</td><td>5.04</td></tr></table></body></html>

表24种岩心渗流流量对比 Table 2Comparison of seepage flow in 4 cores   
表34种岩心渗透率对比  
Table 3Comparison of 4 kinds of core permeability   

<html><body><table><tr><td rowspan="2">序号</td><td rowspan="2">岩样</td><td rowspan="2">渗透率 原值mD</td><td rowspan="2">微米尺度 Qum</td><td rowspan="2">偏差 n,%</td><td rowspan="2">毫米尺度</td><td rowspan="2">偏差 n2,%</td><td rowspan="2">修正渗透率 K</td><td rowspan="2">偏差 13,%</td></tr><tr><td>Kmm</td></tr><tr><td>1</td><td>B1</td><td>1286</td><td>1105.1</td><td>14. 07</td><td>1104</td><td>14. 15</td><td>1293</td><td>-0.54</td></tr><tr><td>2</td><td>C1</td><td>1102</td><td>1789.54</td><td>-62.4</td><td>1782</td><td>-61. 7</td><td>1536.84</td><td>-39.46</td></tr><tr><td>3</td><td>S1</td><td>3898</td><td>3816.42</td><td>2.1</td><td>3826</td><td>2.00</td><td>3895.02</td><td>0.076</td></tr><tr><td>4</td><td>S4</td><td>6966</td><td>6216.75</td><td>10.75</td><td>6216.0</td><td>10.76</td><td>6613.90</td><td>5.05</td></tr></table></body></html>

（2）由表中 $\textcircled{2}$ 号岩样可以看出，在毫米尺度下的值比微米尺度更接近实测值，但是得出的结果都与实测值偏离很远。分析原因，一方面可能是提取的岩心样品在这一区域内孔隙尺寸都偏大，所以更适合尺度层级比较大的运算；另一方面可能是该尺度范围内的此种分形特征并不是很突出，因此误差很大。由此得出，虽然分析的是微观孔隙结构，但是，尺度范围并不是越小越好，而且在研究油藏多孔介质时，单一尺度并不能反映出油藏整体的特征；

（3）对比分析修正前后的渗透率及流量值，修正后的结果误差更小，与实际值更接近，所以修正公式成立。该公式的修正是利用方程两边要达到量纲统一的原则，把某量纲微观尺度下的值与该尺度下的量纲转换系数相结合，通过系数这个桥梁，得出最终宏观结果。

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

# 3.4参数变化特性影响分析

选取 $\textcircled{1}$ 号岩样进行参数变化特性分析。计算过程中通过改变岩样尺寸、最小和最大孔隙直径以及孔隙度等，据此得到不同的渗透率和流量的变化值，以分析微观孔隙结构的参数对宏观输运特性参数渗

![](images/74e13ff5e1f30b68d2759bca6bedaa03f2187938a384fe90acceeb7018a65e49.jpg)  
图3孔隙度对油藏流量及渗透率的影响 Fig.3Effects of porosity on reservoir flow and permeability

透率和流量的变化规律及影响，结果如图3-图6所示。

由图3可知，在压力一定时，孔隙内部的流量和渗透率，随着孔隙度增大而增大。这是因为当岩心孔隙度 $\phi$ 增大，微观孔隙分形维数 $D _ { f }$ 增大，由此得到孔隙结构非均质性增强，孔隙分布不均匀，会对孔隙内的渗流性能在不同方向上产生一定的影响。孔隙度 $\phi$ 增大，孔隙平均迁曲度 $\tau _ { a \nu }$ 减小，迁曲度分形维数 $D _ { T }$ 减小，孔隙通道逐渐趋于一条直线，便于孔隙内流体流动，因而渗透率和流量逐渐增大。

![](images/22879a7fd5ee4ababfef9fff6634b6b577422c8615038b7f529ddb2200ab8a6a.jpg)  
图4最小孔隙直径对流量及渗透率的影响 Fig.4The influence of the minimum pore diameter on flow rate and permeability

由图4可知，在孔隙度一定的情况下，渗透率和流量随着最小孔隙直径的增大而减小。同理，当最小孔隙直径 $\lambda _ { \operatorname* { m i n } }$ 逐渐增大时，微观孔隙分形维数$D _ { f }$ 逐渐减小，岩心内不同大小尺度的孔隙分布趋于均匀。但此时孔隙的迁曲度分形维数 $D _ { T }$ 逐渐增大，表征孔隙结构内流体流通通道的迁回曲折程度增大，流体很难顺畅的穿过孔隙，因而此时流量和渗透率是减小的。

![](images/e8dd36a26f92ab6612e72a66e7a0eb53541b36d14ed882c988efa24f34e41b02.jpg)

由图5可知，增大最大孔隙直径，岩心渗透率和流量也逐渐增大。因为在孔隙率 $\phi$ 一定的情况下，最小孔隙直径 $\lambda _ { \operatorname* { m i n } }$ 不变，最大孔隙直径 $\lambda _ { \operatorname* { m a x } }$ 不断增大，由此计算得到孔隙分形维数 $D _ { f }$ 增大，即岩心非均质性增强，不同方向上最大与最小孔隙之间相差数量级逐渐增大，此时微小孔隙直径可以忽略，对整体流量和渗透率没有影响。并且随着max的逐渐增大， $D _ { T }$ 逐渐减小，孔隙通道趋于一条直线，便于宏观输运，因此渗透率和流量是逐渐增大的。

![](images/db76b6b04ea4d83937b4d59fbb314cfb362003554aaea032b0fb809eee4bda25.jpg)  
图5最大孔隙直径对流量及渗透率的影响 Fig.5The influence of the maximum pore diameter on flow rate and permeability   
图6岩心尺寸对流量及渗透率的影响  
Fig.6Effect of core size on flow rate and permeability 由图6可知，随着储层岩心取样尺寸的增加，

WORD批量转PDF工具-未注册注册码购买联系QQ:3049816538油藏的流量和渗透率逐渐降低。岩心直观长度尺寸$L _ { 0 }$ 的增长，分形维数 $D _ { f }$ 并没有发生变化，因为岩心长度并没有对岩心的内部结构产生影响，因此此时 $D _ { f }$ 不能用来判断其对宏观输运特性参数的影响。$L _ { 0 }$ 增大孔隙的迁曲度分形维数 $D _ { T }$ 减小，但因岩心两端压差不变，当距离增大，流量和渗透率依然减小。

# 4结论

多孔介质结构组成极其复杂，精确描述困难，为此一些研究者们尝试引入分形理论，对其进行描述和分析。但由于实际多孔介质，孔隙在空间不同方向上存在尺度差异，对宏观孔隙输运特性影响很大，尺度效应等影响不应忽略。本文考虑量纲统一原则和尺度效应，对多孔介质相关分形输运模型进行了修正和完善，并进行了计算分析，得到以下结论：

（1）针对已有多孔介质分形渗流模型存在单位、尺度不明确问题，本文进行重新推导，得到了相关的分形输运分析模型，并将其应用到油藏多孔介质中进行了验证；（2）将微观孔隙尺度与宏观计算分析相结合，得到相关输运特性参数，据此可以分析不同层级间的尺度效应；实际分析表明，对于油藏并不是尺度越小计算结果越精确；（3）基于本文提出的分形输运模型，利用某油田油藏数据进行了分析计算，并分析了微观孔隙特征参数对油藏宏观输运参数的影响。实际分析表明，随着孔隙度和最大孔隙直径的增大，流量和渗透率也增大；随着最小孔隙直径与取样尺寸的增大，流量和渗透率减小。本文模拟计算分析结果与油藏实际输运特性规律相吻合。

# 参考文献：

[1] 郁伯铭，徐鹏，邹明清等．分形多孔介质输运物理[M]. 北京：科学出版社,2014:1-5   
YU Boming,XU Peng, ZHOU Mingqing,et al. Transport   
PhysicsofFractal Porous Media[M].Beijing:Science   
Press,2014:1-5   
[2]尹彩玲.基于分形理论油藏多孔介质输运特性研究[D].大 庆：东北石油大学,2015:3-6   
YIN Chailing.The Study ofReserviorPorousMedia Transport Properties Based on Fractal Theory[D].Daqing:Northeast Petroleum University,2015:3-6   
[3] Nutting P G. Some Physical Problems in Oil Recovery[J]. Oil and Gas Journal, 1929,28(27): 44-45 [4] Mandelbrot B B. How Long Is the Coast of Bristain   
Statistical Self-Similarity and Fractional Dimension[J]. Science, 1967, 156(3775):636-638   
[5] Adler P M, et al. Real Porous Media: Local Geometry and Macroscopic Properties[R]. Applied Mechanics Reviews,1998, 51(9): 537-585   
[6] Thovert JF, Wary F, et al. Thermal Conductivity of Random Media and Regular Fractals[J]. Journal of Applied Physics, 1990,68(8): 3872-3883   
[7] Pfeifer P,Avnir D. Chemistry Non-Integral Dimension Between Two and Three[J]. The Journal of Chemical Physics, 1983, 7(7) :3369-3558   
[8] Katz, A.J and Thompson, A.H. Fractal Sandstone Pores: Implication for Conductivity and Pore Formation[J]. Physical Review Letters,1985, 54:1325-1328   
[9] Hansen, J.P.and Skjeltorp,A.T.. Fractal Pore Space and Rock Permeability Implications[J]. Physical Review B,1988, 38(4):2635-2638   
[10] Kim, Tae H, Schechter,David S.EstimationofFracture Porosity of Maturally Fractured Reservoirs with No Matrix Porosity Using Fractal Discrete Fracture Networks[J]. Reservoir Evalustion and Engineering, 2009,12(2):232-242   
[11] XIE Shuyun, CHENG Qiuming, et al. Fractal and   
multifractal analysis of carbonate pore-scale digital images of petroleum reservoirs[J]. Marine and Petroleum Geology,2010, 27(2):476-485   
[12] 同登科，葛家理．分形油藏不稳定渗流问题的精确解[J]. 力学学报,1998,30(5):621-627   
TONG Dengke, GE Jiali. An Eeact Solution For Unsteady Seepage Flow Through Fractal Reservoir[J]. Acta Mechanica Sinica,1998,30(5):621-627   
[13] 刘俊亮，田长安等．分形多孔介质孔隙微结构参数与渗 透率的分维关系[J]．水科学进展,2006,17(6):812-817   
LIU Junliang, TIAN Changan, et al. Fractal Dimensionality Dependence of Microstructural Parameters and Permeability in Fractal Porous Media[J]. Advances in Water Science,2006, 17(6):812-817   
[14] 孔祥言，李道伦等．分形渗流基本公式及分形油藏样板 曲线[J]．西安石油大学学报（自然科学版）,2007,22(2):1-5 SUN Xiangyan,LI Daolun, et al. Basic Formulas ofFractal Seepage and Type-Curves of Fractal Reservoirs[J]. Advances in Water Science (Natural Science）,2007,22(2): 1-5   
[15]王自明，宋文杰等．利用分形模拟建立裂缝型碳酸盐岩 储层渗透率变异函数[J]．天然气工业,2007,27(11):73-75 WANG Ziming, SONG Wenjie, et al. Application ofFractal Simulation Technique to Modeling of Fractured Carbonate

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

Reservoir[J]. Natural Gas Industry,2007,27(11):73-75   
[16]刘波，樊晓东等．低渗透油田岩石微观性描述及对开发   
效果影响[J].辽宁工程技术大学学报（自然科学版),2009,   
28(1):150-152   
LIUBo,FANXiaodong,etal.Fractal Characterization of   
Heterogeneity inLowPermeabilityRock and Its Effect on   
Production Performance[J]. Journal ofLiaoning Technical   
University（Natural Science）,2009,28(1):150-152   
[17]于本福，闫相祯等.考虑储层孔隙介质分形特点的衰竭   
气藏储气库储层压力分布预测[J].石油学报,2013,34(5):   
1017-1022   
YUBenfu,YANXiangzhen etal.Dynamic ReservoirPressure   
Prediction ofDepleted Reservoir Gas Storage Considering the   
FractalFeatureofPorousMedium[J].Petroleum Science,2013,   
34(5):1017-1022

# WORD批量转PDF工具-未注册 注册码购买联系QQ:3049816538