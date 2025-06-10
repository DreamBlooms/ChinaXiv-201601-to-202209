# 基于小波变换的卫星阻力系数分析

刘卫，王荣兰，刘四清，师立勤，龚建村(中国科学院空间科学与应用研究中心，北京100190)

摘要：以不同弧长解算天宫一号空间实验室连续55天(d)GPS轨道数据得到卫星阻力系数 $C _ { d }$ 序列并对同期的太阳辐射通量 $f _ { 1 0 . 7 }$ 和地磁活动指数 $a _ { p } \ A _ { p }$ 序列高、低频多层小波分解。空间环境参量和 $C _ { d }$ 序列各层信号滑动相关性的统计分析结果表明小波分解的阻力系数序列与对应的 $f _ { 1 0 . 7 } \ A _ { p }$ 序列整体具有很好的滞后相关性验证了通过 $f _ { 1 0 . 7 } ^ { } \ A _ { p } ^ { }$ 预报 $C _ { d }$ 的可行性。对不同回归模型和回归分析样本序列长度 $n$ 分析 $C _ { d }$ 预报值残差表明：采用 $f _ { 1 0 . 7 }$ （204一元回归模型并取 $n = 2 0 \mathrm { ~ d ~ }$ 时， $C _ { d }$ 预报结果最优。另外,NRLMSIS-OO 模型在 $3 5 0 ~ \mathrm { k m }$ 高度的中低纬度区域地磁活动上升相响应过度,而下降相则响应不足;太阳辐射通量上升相响应适度，下降相响应过度。最后对应用前景进行总结，该方法对提高航天器轨道预报精度具有重要参考价值。

关键词：小波变换；阻力系数；滞后相关；天宫一号；空间环境   
中图分类号：V474.3 文献标识码：A 文章编号:1000-328(2015)02-0142-09   
DOI:10.3873/j.issn.1000-1328.2015.02.003

# Analysis of Satellite Drag Coefficient Based on Wavelet Transformation

LIU Wei,WANG Rong-an ,LIU Si-qing,SHI Li-qin ,GONG Jian-cun (Centerfor Space Science and Applied Research,Chinese Academy of Sciences,Beijing 1Oo190,China)

Abstract:Drag coefficient sequence $C _ { d }$ is obtained by solving Tiangong 1 continuous 55 days（d) GPS orbit data with different arc length. The same period solar radiation flux $f _ { 1 0 . 7 }$ and geomagnetic index $a _ { p } \mathbf { \Omega } , A _ { p }$ sequences are high and low frequencymulti-waveletdecomposed.Statistical analysisresultsof themultilayerslidingcorelation betweenspace environmental parameters and decomposition of $C _ { d }$ show that lag correlation between the satellite drag coefficient sequence after wavelet decomposition and the corresponding level of $f _ { 1 0 . 7 } \ , A _ { p }$ sequence is good.It is also verified that the $C _ { d }$ （20 prediction is feasible.Prediction residuals of $C _ { d }$ with different regression models and different sample lengths are analyzed. The results show that the case setting sample length of 2O days and selecting $f _ { 1 0 . 7 }$ regression model is best.It is also show that NRLMSIS-OO model's response in the region of $3 5 0 ~ \mathrm { k m }$ （Tiangong's altitude）and low-middle latitude（Tiangong's inclination） is excessive during the ascent phase of geomagnetic activity $A _ { p }$ and is inadequate during decline phase. Additionally,forthelow-frequencydecomposition sequence NRLMSIS-OO modelsresponse isappropriate during theascent rising phase of $f _ { 1 0 . 7 }$ .For the high frequency decomposition sequence，NRLMSIS-0O model's response is small-scale inadequate during the ascent phase of $f _ { 1 0 . 7 }$ and is excessive during the decline phase of $f _ { 1 0 . 7 }$ .Finally,the summary of potentialuseandoutlook are listed；thismethod hasanimportant referencevaluefor improving thespacecraft orbit prediction accuracy.

Key words:Wavelet transformation; Drag coeficient;Lag correlation; Tiangong 1；Space environment

# 0引言

的主要误差源。目前典型大气模式中误差均在$1 5 \% \sim 3 0 \% ^ { \mathrm { ~ [ 1 ~ . ~ } }$ -2],太阳活动峰年或磁暴期会更大。该误差是经验模式所固有，由空间环境指数建模不大气阻力摄动是近地空间目标轨道确定、预报完善引起，可通过解算同期卫星轨道数据补偿修正[1]。大气模式短期修正方面 国内外学者做了大量研究工作。Doornbos等利用TLE轨道数据中丰富的阻力信息对CIRA-72模式进行短期修正，并使用5颗近地点 $2 8 0 \sim 5 3 0 ~ \mathrm { k m }$ 目标验证修正效果，表明仅一天的参数修正可减小密度中误差 $1 5 \%$ \~$30 \%$ ，考虑其它参数的影响中误差至少能降低$12 \%$ [2]。Lechtenberg等基于精密星历对短期大气模型密度进行修正[3]。Pardini等通过第23太阳活动周峰年4颗卫星半长轴变化，分析了6种(JR-71，MSISE-90/00GOST-2004和JB06/08)大气模式偏差指出现有经典模式均高估 $5 0 0 ~ \mathrm { k m }$ 以下大气密度约 $7 \% \sim 2 0 \%$ [4],此偏差是建模过程中考虑卫星阻力系数高度无关引起[4-5]。同时文献[5－8]指出卫星阻力系数随轨道高度、卫星构形和材质等因素变化。Pardini等分析轨道高度 $1 5 0 \sim 1 5 0 0 ~ \mathrm { k m }$ 之间11颗球形卫星整个太阳活动周轨道衰减数据，评估JR-71和MSISE-90模式，认为两模式误差与空间环境变化及轨道高度是相关的，且任何空间环境下两模式均高估 $4 0 0 ~ \mathrm { k m }$ 以下大气密度[9]。

大气密度除包含11年、27天、半周年、周年、半周日、周日和潮汐等错综复杂的周期变化外还存在磁暴等因素引起的非周期变化，有些因素难以模制，使得大气密度精确建模工作相当困难。文献[10-11]指出现有大气模式误差与空间环境参量相关，并建立基于远紫外能量 $E _ { 1 0 . 7 }$ 指数、地磁指数 $a _ { p }$ 的短期动态密度修正系数。大气阻尼摄动力计算式中含大气密度、相对速度和弹道系数等因素。研究表明，一定弧段内的大气密度误差可通过阻力系数 $C _ { d }$ 平滑补偿，以削弱大气阻力误差。陈建荣等在磁暴期间用折线型 $C _ { d }$ 吸收大气模式误差提高了轨道确定精度[12-13]。刘舒前等分析磁静期阻力系数与地磁指数和沿迹残差的关系，建立中长期轨道预报中阻力系数的补偿算法[14]。

小波变换源于20世纪80年代地球物理研究中地震信号分析[15],其克服傅立叶变换的缺点具有时域和频域局部化特征，变换后可获取目标信号各频率子段信息。小波变换是强有力的时频分析工具,有人将其称为“数学显微镜”。小波分析已广泛用于信号、图像处理、模式识别及大气湍流等诸多领域。文献[16]利用小波变换时域特性对降水时间序列进行多时间尺度小波分析，为旱涝预报提供了重要信息。

天宫一号（Tiangong1TG1)是我国首个空间实验室。自2011年发射以来积累了大量探测数据，为空间科学研究奠定了基础。基于大气模式误差与空间环境参量相关，且可通过阻力系数进行补偿的理论。本文以不同弧长解算 $2 0 1 3 - 2 - 5 \mathrm { ~ T 0 0 : 0 0 }$ 至2013-3-31 T00:00(BJT)间 TG1 连续 55天(d)GPS轨道数据,得到卫星阻力系数 $C _ { d }$ 序列利用 $3 \sigma$ 法则剔除异常数据。对同期太阳辐射通量 $f _ { 1 0 . 7 }$ 和地磁指数 $a _ { p }$ （20 $A _ { p }$ 序列进行高、低频5层小波分解分解后的各层信号进行了滑动相关性分析。结果表明，小波分解后的 $C _ { d }$ 与 $f _ { 1 0 . 7 } \ A _ { p }$ 各层次信号具有很好的滞后相关性验证了 $C _ { d }$ 通过 $f _ { 1 0 . 7 } \ A _ { p }$ 预报的可行性。通过回归分析建立 $C _ { d }$ 与 $f _ { 1 0 . 7 } \ A _ { p }$ 关系并使用GPS轨道数据解算 $C _ { d }$ 值验证预报的有效性。最后对方法适用范围与局限性等进行讨论，该方法对提高航天器轨道预报精度具有重要意义。

# 1阻力系数解算

卫星在轨运行中，大气阻力加速度 $\pmb { a } _ { \mathrm { d r a g } }$ 可表达为：

$$
{ \pmb a } _ { \mathrm { d r a g } } \ = - \ \frac { 1 } { 2 } B \rho { \pmb v } _ { s } ^ { 2 }
$$

式中:弹道系数 $B ~ = ~ C _ { d } A / M ~ , C$ 为卫星阻力系数，$A / M$ 是面积质量比 ${ } , { \boldsymbol \rho }$ 是卫星所处位置大气密度， $\mathbf { \delta } _ { \mathbf { \boldsymbol { \nu } } _ { s } }$ 是卫星相对大气的速度矢量。

大气阻力加速度由 $C _ { d }$ $. A / M , \pmb { \nu } _ { s }$ 和 $\rho$ 四因素共同构成。大气阻力摄动误差为各因素误差与因素间耦合误差之和。故大气密度误差通过阻力系数补偿的原理可表达为[17]：

$$
B \int _ { 0 } ^ { \Delta t } \rho \pmb { \nu } _ { s } ^ { 2 } \mathrm { d } t \approx B ^ { \prime } \int _ { 0 } ^ { \Delta t } \rho \pmb { \nu } _ { s } ^ { 2 } \mathrm { d } t
$$

式中： $B ^ { \prime }$ 为轨道确定中估算弹道系数 $\cdot \rho ^ { \prime }$ 为大气密度模式计算值， $\Delta t$ 为轨道拟合弧长。

在 $A / M$ 已知的情况下，估算阻力系数 $C _ { d }$ 与估算弹道系数 $B$ 是等效的。地磁指数 $a _ { _ p } \mathrm { \Delta } \mathcal { A } _ { p }$ 分为$^ { 3 \mathrm { ~ h ~ } }$ 值和日值太阳辐射通量 $f _ { 1 0 . 7 }$ 为日值故本文分别以 $^ 3 \mathrm { ~ h ~ }$ 弧长和1d弧长解算阻力系数 $C _ { d }$ 序列。

# 1.1 解算方法与模型

阻力系数解算本质是将其包含到状态矢量 $\scriptstyle { \mathbf { \boldsymbol { X } } }$

中进行微分修正。通过GPS轨道数据中位置矢量r建立测量方程[18]：

$$
r = G ( \mathbf { \chi } _ { t } \mathbf { \chi } , \mathbf { \chi } ) \mathbf { \chi } + V
$$

将测量方程线性化在参考状态量 $\boldsymbol { X } _ { 0 } ^ { * }$ 处泰勒展开略去高阶项得到条件方程:

$$
\textbf { \boldsymbol { y } } = \widetilde { \pmb { G } } \pmb { x } + \boldsymbol { v }
$$

式中: $\pmb { y } = \pmb { r } _ { o } - \pmb { r } _ { c }$ 是残差 $, r _ { o } \ r _ { c }$ 分别为位置矢量测量值和计算值;状态量 $X$ 包含位置、速度矢量和阻力系数即 $X = X ( r , \nu , \mathcal { C } _ { d } ) ; x = X _ { 0 } - X ^ { * } = X _ { 0 } ^ { k } - X _ { 0 } ^ { k - 1 }$ （204号为待估状态量的修正量； $\widetilde { G }$ 是相应 $m \times n$ 维高矩阵，$m$ 是 $N$ 个测量数据对应的维数， $n$ 则是待估状态量的维数通常 $m$ 远大于 $n$ ,充分利用测量数据统计信息。

阻力系数解算中主要模型和参量:

1） $7 0 \times 7 0$ 阶地球引力场模型GGM02C;2） $3 0 \times 3 0$ 阶TOPEX4.0海潮模型;3）NRLMSIS-OO 大气模型;4）坐标、时间及天文常数系统采用IERS（2003）标准；5）日、月引力摄动；6）太阳光压 固体潮摄动。

通过多次迭代求解条件方程，获取阻力系数最优估计解算连续弧段得到阻力系数 $C _ { d }$ 序列。

# 1.2 异常数据剔除

天宫任务需要轨道机动或轨道衰减等需轨道机动以保障任务或轨道维持。如解算弧段内含轨道机动解算出的阻力系数就不能准确表征大气密度偏差，此情况为阻力系数异常，表现为定轨残差RMS( $R _ { \mathrm { r e s i d u a l } }$ ）较大。通过残差RMS统计,使用 $3 \sigma$ 法则对异常数据进行剔除。

即：如果 $\mid R _ { \mathrm { r e s i d u a l } } \ - \mu _ { \mathrm { r e s i d u a l } } \mid  > \ 3 \sigma _ { \mathrm { r e s i d u a l } }$ ,则剔除该弧段解算的阻力系数，以保证获取的 $C _ { d }$ 序列正确反映大气密度误差。其中 $R _ { \mathrm { r e s i d u a l } }$ 为定轨残差RMS，$\mu _ { \mathrm { r e s i d u a l } }$ 为 $R _ { \mathrm { r e s i d u a l } }$ 序列均值， $\sigma _ { \mathrm { r e s i d u a l } }$ 为 $R _ { \mathrm { r e s i d u a l } }$ 序列标准差。

# 2数据处理

解算阻力系数分别得到弧长 $^ 3 \mathrm { ~ h ~ }$ 和1d的 $C _ { d }$ 序 列并剔除异常值。对 $C _ { d }$ 序列作归一化处理，定义 归一化值 $\overline { { C } } _ { d } = C _ { d } / 2 . 2$ 。对 $C _ { d }$ 及同期 $f _ { 1 0 . 7 } \ A _ { p } \ \mu _ { p }$ 序

列进行高、低频5层小波分解不同尺度上分析分解信号相关性。

# 2.1 离散小波变换

假设输入信号 $\boldsymbol { \mathscr { f } } ( \mathbf { \Theta } _ { t } )$ ，记 $\varphi _ { j k } ( \mathbf { \alpha } _ { t } ) \ \equiv \ 2 ^ { - j / 2 } \varphi ( 2 ^ { - j } t \ -$ k） $, \psi _ { j k } ( \textit { t } ) = 2 ^ { - j / 2 } \psi ( \textit { 2 } ^ { - j } t - k ) , \varphi$ $\varphi ( \mathbf { \Omega } _ { t } )$ 与 $\psi ( \mathbf { \xi } _ { t } )$ 为多分辨率分析中的尺度函数和小波函数； $\{ \varphi _ { j k } ( \mathbf { \Omega } _ { t } ) \}$ 与$\{ \psi _ { j k } ( \mathbf { \Omega } _ { t } ) \}$ 为正交基函数集。记 $P _ { 0 } f = f$ 在第 $j$ 级上的一维离散小波变换为(DWT)。通过正交投影 $P _ { j } f$ 与Qjf将Pj-1f分解为[19-21]：

$$
P _ { j - 1 } f = P _ { j } f + Q _ { j } f = \ \sum _ { k } c _ { k } ^ { j } \varphi _ { j k } \ + \ \sum _ { k } d _ { k } ^ { j } \psi _ { j k }
$$

式中: $c _ { k } ^ { j } = \sum _ { n = 0 } ^ { p - 1 } h ( n ) c _ { 2 k + n } ^ { j - 1 } , d _ { k } ^ { j } = \sum _ { n = 0 } ^ { p - 1 } g ( n ) c _ { 2 k + n } ^ { j - 1 } ( j = 1 )    $ $2 \ \cdot \ . \ , \ L \ \ne 0 \ , 1 \ \ . \ . \ \cdot \ \ \frac { N } { 2 ^ { j } } - 1 ) \ ; \ \{ h ( \ n ) \ \}$ 与 $\{ \varrho ( n ) \}$ 为低通和高通滤波系数，由基函数 $\{ \varphi _ { j k } ( \mathbf { \Omega } _ { t } ) \}$ 、$\{ \psi _ { j k } ( \mathbf { \Omega } _ { t } ) \}$ 确定； $p$ 为滤波系数的长度； $N$ 为输入信号的长度， $L$ 为所需的级数。最终得到各级小波系数序列 $c _ { k } ^ { j } \ d _ { k } ^ { j }$ 。

小波基函数选用Daubechies图1为弧长1d归一化阻力系数 $\overline { { C } } _ { d }$ 及对应 $A _ { p }$ 序列多级分解结果。图1(a)顶部两曲线为 $A _ { p }$ 和 $\overline { { C } } _ { d }$ 原始序列原序列间不存在显著相关性。图 $\mathbf { l } \left( \mathrm { ~ a ~ } , \mathrm { b } \right)$ 其余曲线为两序列低频分解 $L 5 \ \sim \ L 1$ ，低频部分表现出一定负相关性。同样图 $1 ( \mathrm { ~ c ~ } , \mathrm { d } )$ 除顶部曲线为 $A _ { p }$ 和 $\overline { { C } } _ { d }$ 原始序列外 其余为两序列高频分解 $H 5 \sim H 1$ ，高频部分呈现出更强负相关，表明NRLMSIS-OO模式在 $3 5 0 ~ \mathrm { k m }$ 高度中低纬度区域（Tiangong1， $\mathrm { h } \approx 3 5 0 \ \mathrm { k m } \ , \mathrm { i } \approx$ $4 2 ^ { \circ } .$ )地磁活动上升相存在过响应，而下降相则响应不足。

图2给出弧长1d解算 $\overline { { C } } _ { d }$ 和 $f _ { 1 0 . 7 }$ 序列小波分解结果图2(a)顶部两曲线为 $f _ { 1 0 . 7 }$ 和 $\overline { { C } } _ { d }$ 原始序列原始序列间存在较强的相关性。图 $2 ( \mathrm { ~ a ~ } , \mathrm { b } )$ 其它曲线为两序列低频分解 $L 5 \ \sim \ L 1$ 。低频部分 $L 5$ 太阳辐射流量 $f _ { 1 0 . 7 }$ 上升相 $\overline { { C } } _ { d }$ 序列基本保持稳定，下降相 $\overline { { C } } _ { d }$ 序列相应下降,表明NRLMSIS-OO 模式在 $3 5 0 ~ \mathrm { k m }$ 高度中低纬度区域 $, f _ { 1 0 . 7 }$ 上升相响应适度，下降相存在过响应。同样，图 $2 ( \mathrm { ~ c ~ } , \mathrm { d } )$ 中 $\mathrm { ~ ( ~ c ~ ) ~ }$ 顶部两曲线为$f _ { 1 0 . 7 }$ 和 $\overline { { C } } _ { d }$ 原始序列其它为两序列高频分解 $H 5 ~ \sim$ $H 1 \circ f _ { 1 0 . 7 } \setminus \overline { { C } } _ { d }$ 高频部分呈现出很强的正相关，表明NRLMSIS-OO模式在 $f _ { 1 0 . 7 }$ 上升相在小尺度上的响应不足而下降相存在过响应。

![](images/ba8c363f6b375487e699d4185a72d30f94994400d32b73652e5281c9f1de5bc1.jpg)  
图1地磁指数和阻力系数的小波分解  
Fig.1The multi-wavelet decomposition of $A _ { p }$ （20 $\overline { { \mathcal { L } } } _ { d }$ sequences   
图2太阳辐射指数和阻力系数的小波分解  
Fig.2The multi-wavelet decomposition of $\dot { f } _ { 1 0 . 7 }$ （20 $\overline { { \mathcal { L } } } _ { d }$ sequences

5 10 15 2025303540455055 T/d (a)   
CTT 51 150 5 10 15 20 25 30 3540455055 T/d （b)   
e   
HfSHvHH 0 -0.1 5 1015 2025303540455055 T/d (c) 5 0 o > S 红 -0.1 10 15 20 25 30 35 40 45 505 T/d (d)

另外分析表明弧长 $^ 3 \mathrm { ~ h ~ }$ 解算阻力系数序列与对应 $a _ { { } _ { p } }$ 序列呈极弱相关性。可能是解算弧长不够等因素引入了其它误差导致的，限于篇幅具体分析结果不再列出。

# 2.2 滑动相关分析

滑动相关性分析是固定空间环境序列前后滑动$\overline { { C } } _ { d }$ 序列并计算相关系数统计相关系数变化规律，为$C _ { d }$ 预报分析提供依据。首先对 $A _ { p }$ 及对应的 $\overline { { C } } _ { d }$ 序列作滑动相关性分析。选取同一分解层两相同长度的序列 固定 $A _ { p }$ 序列前后滑动 $\overline { { C } } _ { d }$ 序列取滑动值-3～3d,计算两序列相关系数。解算长度55d序列中取滑动序列长度 $3 0 \mathrm { ~ d ~ }$ 。滑动值在-3\~3d范围时各滑动值均可计算19个相关系数。

表1列出 $A _ { p }$ ， $\overline { { C } } _ { d }$ 序列各层信号不同滑动值时，相关系数均值。 $R _ { - A _ { p } \overline { { { C } } } _ { d } } ~ R _ { - A _ { p } \overline { { { C } } } _ { d } } H 5 ~ \sim H 1 ~ R _ { - A _ { p } \overline { { { C } } } _ { d } } L 5 ~ \sim L 1$ 各表示 $A _ { p }$ ， $\overline { { C } } _ { d }$ 原始序列 高频 $H 5 \sim H 1$ ，低频 $L 5 ~ \sim$ $L 1$ 序列相关系数均值。图3是 $A _ { p }$ ， $\overline { { C } } _ { d }$ 序列各层分解信号滑动相关系数统计。图 $^ 3 ( \mathrm { ~ a ~ } , \underline { { \mathbf { g } } } )$ 是 $A _ { p }$ （20 $\overline { { \mathcal { L } } } _ { d }$ 原始序列滑动相关性统计，滑动值2d时原始序列间表现出较强的负相关性，如表1所示相关系数均值-0.3102.图 $3 ( \mathrm { ~ b ~ } \sim \mathrm { f } )$ 给出 $A _ { p }$ ， $\overline { { C } } _ { d }$ 序列高频 $H 5 ~ \sim$ $H 1$ 滑动相关系数统计，可见原始序列及高频 $H 5 ~ \sim$ $H 2$ 部分滑动值取2d时呈现出较强的负相关性，相关系数均值分别为： $- \ 0 . \ 3 1 0 2 \ , - \ 0 . \ 2 3 2 2$ $- 0 . 5 5 7 6 , - 0 . 3 7 , - 0 . 4 3 9 6$ 而高频 $H 1$ 的相关性则没有规律。图 $3 ( \mathrm { ~ h ~ } \mathord { \sim } \mathrm { ~ l } )$ 给出 $A _ { p }$ ， $\overline { { C } } _ { d }$ 序列低频 $L 5 ~ \sim$ L1滑动相关系数统计情况，低频部分情况类似整体表现出负相关，当滑动值取2d时整体负相关性较强。

表1 $A _ { _ p } \ \overline { { C } } _ { d }$ 序列各滑动值对应相关系数均值Table 1The mean of $A _ { p }$ （20 $\overline { { \mathcal { L } } } _ { d }$ sliding correlation  

<html><body><table><tr><td>滑动值</td><td>-3d</td><td>-2d</td><td>-1d</td><td>0d</td><td>1d</td><td>2d</td><td>3d</td></tr><tr><td>R_Apd</td><td>0.0545</td><td>0.1072</td><td>-0.083</td><td>-0.0766</td><td>-0.23</td><td>-0.3102</td><td>-0.1512</td></tr><tr><td>R_Apcd H5</td><td>0.0144</td><td>-0.0923</td><td>-0.1993</td><td>-0.3089</td><td>-0.3343</td><td>-0.2322</td><td>-0.204</td></tr><tr><td>R_ApCdH4</td><td>-0. 1995</td><td>-0.3086</td><td>-0.4098</td><td>-0.4919</td><td>-0.5458</td><td>-0.5576</td><td>-0.5089</td></tr><tr><td>R-ApH3</td><td>0.3364</td><td>0.2816</td><td>0.0616</td><td>-0.1722</td><td>-0.3116</td><td>-0.37</td><td>-0.2647</td></tr><tr><td>R_ApH2</td><td>0.1408</td><td>0.3873</td><td>0.2405</td><td>-0.1049</td><td>-0.4355</td><td>- 0.4396</td><td>0.1071</td></tr><tr><td>R-ApcH</td><td>-0.0515</td><td>0.217</td><td>-0.3342</td><td>0.2619</td><td>0.0247</td><td>-0.2232</td><td>0.0562</td></tr><tr><td>R-AL5</td><td>0.1597</td><td>0.0528</td><td>-0.0538</td><td>-0.155</td><td>-0.2602</td><td>-0.3653</td><td>-0.4706</td></tr><tr><td>R_ApCdL4</td><td>0.1691</td><td>0.0639</td><td>-0.0234</td><td>-0.089</td><td>-0.1443</td><td>- 0.1953</td><td>-0.2493</td></tr><tr><td>R_ApCdL3</td><td>-0.0898</td><td>-0.1674</td><td>-0.2455</td><td>-0.3317</td><td>- 0.4149</td><td>-0.4839</td><td>-0.5142</td></tr><tr><td>R_ApdL2</td><td>-0.0695</td><td>-0.1464</td><td>-0.224</td><td>-0.3079</td><td>-0.3891</td><td>-0.4583</td><td>- 0.4952</td></tr><tr><td>R_ApCdL1</td><td>0.0821</td><td>0.0984</td><td>-0.0138</td><td>-0.17</td><td>-0.3121</td><td>-0.3532</td><td>-0.2284</td></tr></table></body></html>

表2是 $f _ { 1 0 . 7 }$ 1 $\overline { { C } } _ { d }$ 序列各层信号取不同滑动值时的相关系数均值。 $R _ { - f _ { 1 0 . 7 } \overline { { C } } _ { d } } ~ R _ { - f _ { 1 0 . 7 } \overline { { C } } _ { d } } H 5 \sim H 1$ ，$R _ { - f _ { 1 0 . 7 } \overline { { { c } } } _ { d } } L 5 \sim L 1$ 各为 $f _ { 1 0 . 7 }$ ， $\overline { { C } } _ { d }$ 原始序列 高频 $H 5 \ \sim$ $H 1$ ，低频 $L 5 \ \sim \ L 1$ 相关系数均值。图4是 $f _ { 1 0 . 7 }$ ' $\overline { { C } } _ { d }$ 序列各层信号滑动相关系数统计，图 $\mathbf { \nabla } \cdot \mathbf { 4 } \left( \mathbf { \nabla } \mathrm { a _ { \ t } } \mathbf { \vec { \mathrm { g } } } \right)$ 是$f _ { 1 0 . 7 } \ \overline { { C } } _ { d }$ 原始序列滑动相关性统计原始序列间表现出较强的相关性且随滑动值增大相关性有减弱趋势。从 $C _ { d }$ 预报的角度，我们希望在滑动值大于0（滞后相关)时具有更强的相关性。好在减弱趋势是缓慢的滑动值取1d时相关系数均值为0.65。

图 $4 ( \mathrm { ~ b ~ } \sim \mathrm { f } )$ 给出 $f _ { 1 0 . 7 }$ ， $\overline { { C } } _ { d }$ 序列高频 $H 5 \sim H 1$ 滑动相关系数统计高频 $H 5$ - $H 4$ 部分较原始序列具有更强的相关性变化趋势与原始序列相似。高频 $H 3$ $\sim H 1$ 部分则相关性较弱且变化不规律。图4（h～1)给出 $A _ { p }$ ， $\overline { { C } } _ { d }$ 序列低频 $L 5 \ \sim \ L 1$ 滑动相关系数统计，低频部分相关系数随滑动值增大而减弱，但整体表现出较强正相关。虽然滑动值小于0(超前相关)时各分解序列相关性更强些，但从变化趋势上来看滑动值取1d时，也具有较强的相关性。 $C _ { d }$ 预报中可取滑动值1d避免引入空间环境预报误差。

![](images/104c2e9ffeaaa892a2351ff63380743c7085f662761749ed3eddb653b2ad8f64.jpg)  
图3地磁指数和阻力系数分解序列滑动相关性统计  
Fig.3The boxplot of $A _ { p }$ （204号 $\overline { { \mathcal { L } } } _ { d }$ sliding correlation

表2 $f _ { 1 0 . 7 } \ \overline { { C } } _ { d }$ 序列各滑动值对应相关系数均值

Table2The mean of $\dot { f } _ { 1 0 . 7 }$ （20 $\overline { { \mathcal { L } } } _ { d }$ sliding correlation   

<html><body><table><tr><td>滑动值</td><td>-3d</td><td>-2d</td><td>-1d</td><td>0d</td><td>1d</td><td>2d</td><td>3d</td></tr><tr><td>R-f10.7d</td><td>0.639</td><td>0.7085</td><td>0.7426</td><td>0.7224</td><td>0.65</td><td>0.5661</td><td>0.4805</td></tr><tr><td>R-10.7dH5</td><td>0.835</td><td>0.9464</td><td>0.9217</td><td>0.8364</td><td>0.7526</td><td>0. 6557</td><td>0.4746</td></tr><tr><td>R-f10.7dH4</td><td>0.705</td><td>0.7735</td><td>0.8126</td><td>0.7866</td><td>0.7106</td><td>0.6148</td><td>0.5151</td></tr><tr><td>R-f10.7CdH3</td><td>0.0116</td><td>-0.0046</td><td>-0.023</td><td>-0.0407</td><td>- 0. 0546</td><td>-0.0606</td><td>-0.058</td></tr><tr><td>R10.7H2</td><td>0.0018</td><td>-0.0004</td><td>-0.0037</td><td>-0.0076</td><td>-0.0112</td><td>-0.0134</td><td>-0.0121</td></tr><tr><td>R-f10.7CdH1</td><td>0.0026</td><td>0.0005</td><td>-0.0016</td><td>-0.0031</td><td>-0.0057</td><td>-0.009</td><td>-0.0106</td></tr><tr><td>R-10.7L5</td><td>0.8899</td><td>0.9958</td><td>0.8911</td><td>0.7877</td><td>0. 6868</td><td>0.5822</td><td>0.4774</td></tr><tr><td>R-f10.7L4</td><td>0.6288</td><td>0.7299</td><td>0.8191</td><td>0.8936</td><td>0.909</td><td>0.8634</td><td>0.774</td></tr><tr><td>R-10.7CdL3</td><td>0.7508</td><td>0.8367</td><td>0.8896</td><td>0.9089</td><td>0.8828</td><td>0.8213</td><td>0.7313</td></tr><tr><td>R-f10.7dL2</td><td>0.728</td><td>0.8145</td><td>0.8491</td><td>0.8334</td><td>0.7751</td><td>0.6896</td><td>0.5899</td></tr><tr><td>R-10.7L1</td><td>0.6809</td><td>0.7665</td><td>0.7977</td><td>0.7741</td><td>0.7</td><td>0.6054</td><td>0.5216</td></tr></table></body></html>

上述分析表明阻力系数 $C _ { d }$ 对地磁指数 $A _ { p }$ 和太阳辐射流量 $f _ { 1 0 . 7 }$ 都具有滞后相关性，与 $A _ { p }$ 相比 $f _ { 1 0 . 7 }$ 序列的相关性更强些。工程应用中，可通过实测的空间环境指数对 $C _ { d }$ 序列进行 $1 \sim 2 \mathrm { ~ d ~ }$ 预报

# 3 回归分析与验证

通过滑动相关性的分析阻力系数 $C _ { d }$ 对地磁指数 $A _ { p }$ 和太阳辐射 $f _ { 1 0 . 7 }$ 分别取滑动值2d和

1d。对各层分解信号进行多元非线性回归分析,模型为:

$$
C _ { d } \ = \ \sum _ { i = 1 } ^ { 5 } \alpha _ { i 0 } \ + \alpha _ { i 1 } x _ { i 1 } \ + \alpha _ { i 2 } x _ { i 1 } ^ { 2 } \ + \alpha _ { i 3 } x _ { i 2 } \ + \alpha _ { i 4 } x _ { i 2 } ^ { 2 }
$$

采用二次多项式进行回归分析,式中： $x _ { i 1 } \ x _ { i 2 }$ 为 $A _ { p }$ 和 $\mathcal { f } _ { 1 0 . 7 }$ 分解的各层信号; $\alpha _ { i 0 } \alpha _ { i 1 } \alpha _ { i 2 } \alpha _ { i 3 } \alpha _ { i 4 }$ 为回归系数;最后将高低频信号叠加得到 $C _ { d }$ 值。

C 0. 0.8 --+ 上 白+ + 百面 B0 1宝\* + +++ T ++ -++ B -0.1 0.10.2 -1 丰 + 1 -0.2-3-2-10123 -3-2-10123 -3-2-10123 -3-2-10123T/d T/d T/d T/d(a) (b) (c) (d)  
m0 860 1 --- 卓 30T 白！ 品 1内 心□ 日 H-0.05 - 十 +  
-0.1 土 0.2 -1 +++≠↓-3-2-10123 -3-2-10123 -3-2-10123 -3-2-10123T/d T/d T/d T/d(e) (f) （g） (h)150 17 1 8004 一 □++ 白 80604 星点7 - 白  
4 B0.5 i +++ 1 Ⅱ  
-0.5++ ++ 0.2 + 0.2 + +-3-2-10123 -3-2-10123 -3-2-10123 -3-2-10123T/d T/d T/d T/d(i) i (k) (1)

![](images/993097fb6c031cbcf89f1385114a89ace555926fa6e34b7c33edea372b6fdd06.jpg)  
图4太阳辐射指数和阻力系数分解序列滑动相关性统计  
Fig.4The boxplot of $f _ { 1 0 . 7 }$ （2 $\overline { { \mathcal { L } } } _ { d }$ sliding correlation   
图5回归分析结果统计与验证  
Fig.5The statistic of regression analysis and verification

仍以解算的 $5 5 \mathrm { ~ d ~ }$ 序列为样本选取长度为 $n$ 的连续序列进行回归分析。剩余序列来验证回归分析结果并统计 $C _ { d }$ 序列预报残差。图5(a)给出滑动值分别取 $2 \mathrm { ~ d ~ } , 1 \mathrm { ~ d ~ }$ 时 $A _ { p }$ 和 $f _ { 1 0 . 7 }$ 实测值 图5(b)给出不同回归模型预报 $C _ { d }$ 值与实际解算值曲线标注见图5（a）其中 $C _ { d }$ 预报值1\~3分别是 $f _ { 1 0 . 7 } ^ { } \ A _ { p } ^ { }$ 一元和

$A _ { p }$ （2 $, f _ { 1 0 . 7 }$ 二元非线性回归模型预报的 $C _ { d }$ 值。为便于预报误差比较图5(c)依据 $C _ { d }$ 预报残差对预报值的“毛刺"进行“削顶"平滑处理。对比图5(a)可见“毛刺”多出现在空间环境上升或下降相。各回归模型对空间环境变化响应不同，如 $f _ { 1 0 . 7 }$ 一元回归模型对空间环境变化处理较好，只含一个“毛刺”其余两模型则差一些。图 $5 ( \mathrm { ~ b ~ } \sim \mathrm { { c } ) }$ 均取 $n _ { \mathrm { ~ \scriptsize ~ = ~ } 2 0 \mathrm { ~ d ~ } }$ 平滑后三种回归模型 $C _ { d }$ 序列预报残差标准差分别为：$0 . 1 4 1 2 \ \mathrm { ~ 0 } . 6 4 5 4 \ \mathrm { ~ 0 } . 2 8 0 2$ ，可见 $f _ { 1 0 . 7 }$ 一元非线性回归模型预报结果是最优。图 $5 ( \mathrm { ~ d ~ } \mathord { \sim } \mathrm { ~ f ~ } )$ 给出 $f _ { 1 0 . 7 }$ 一元回归模型时分别取 $n \ = 3 0 \mathrm { ~ d ~ } \ 2 0 \mathrm { ~ d ~ } \ , 1 0 \mathrm { ~ d ~ }$ 时 $C _ { d }$ 的预报值与解算值，平滑后对应残差标准差分别为：$0 . 1 6 6 3 \ \mathrm { 0 . 1 4 1 2 \ 0 . 1 5 8 0 }$ 。可见 $C _ { d }$ 预报优劣与回归分析序列长度相关取 $n _ { \mathrm { ~ \scriptsize ~ = ~ } 2 0 \mathrm { ~ d ~ } }$ 预报结果最优。另外统计发现回归系数 $\alpha _ { i 0 } \alpha _ { i 1 } \alpha _ { i 2 } \alpha _ { i 3 } \alpha _ { i 4 }$ 波动较大，回归系数是时变的，只适用于短期 $C _ { d }$ 预报。

利用建立的回归模型选取实例，检验轨道预报精度提高情况。取空间环境剧烈波动期样本，使用三种方法进行预报： $\textcircled{1} C _ { d }$ 取常数2.2 $\textcircled{2}$ 前一弧段估算 $C _ { d }$ 用于后续预报 $\textcircled{3}$ 本文方法预报 $C _ { d }$ 值。表3列出三种方法预报结果及误差，可见方法 $\textcircled{3}$ 轨道预报精度最优位置预报误差较方法 $\textcircled{1}$ 、 $\textcircled{2}$ 的千米级，精确至百米级。当然空间环境平稳变化期的改进效果则没有这么明显限于剧烈扰动期的数据样本数量这里就不给出统计结论了。

表3不同 $C _ { d }$ 模式下的轨道预报误差  
Table 3The prediction errors of position with different $C _ { d }$ mode   

<html><body><table><tr><td>预报方法</td><td>Cd取值</td><td>预报时长/d</td><td>预报X/m</td><td>预报Y/m</td><td>预报Z/m</td><td>位置误差/m</td></tr><tr><td>①</td><td>2.2</td><td>1</td><td>5941829</td><td>3075328</td><td>-790634</td><td>2659.573</td></tr><tr><td>②</td><td>2.9304</td><td>1</td><td>5939655</td><td>3078517</td><td>- 794101</td><td>2528.256</td></tr><tr><td>③</td><td>2. 5544</td><td>1</td><td>5940775</td><td>3076875</td><td>- 792316</td><td>144. 9546</td></tr><tr><td></td><td>实测GPS轨道数据</td><td></td><td>5940737</td><td>3076969</td><td>- 792420</td><td>NULL</td></tr></table></body></html>

# 4结束语

本文以不同弧长解算连续 $5 5 \mathrm { ~ d ~ }$ 天宫一号GPS轨道数据得到阻力系数 $C _ { d }$ 序列对同期的太阳辐射通量 $f _ { 1 0 . 7 }$ 和地磁活动指数 $a _ { p }$ “ $A _ { p }$ 序列一并进行高、低频小波分解统计分析空间环境参量 $A _ { p }$ $\mathcal { f } _ { 1 0 . 7 }$ 和 $C _ { d }$ 序列各分解信号滑动相关性。结果表明，滑动值分别取2d和1d时，卫星阻力系数序列小波分解后与对应层次 $A _ { p } \ f _ { 1 0 . 7 }$ 序列具有很好的滞后相关性验证了 $C _ { d }$ 可预报性。地磁指数 $A _ { p }$ 和阻力系数 $C _ { d }$ 序列整体呈现负相关，表明NRLMSIS-OO模式在高度$3 5 0 ~ \mathrm { k m }$ 的中低纬度区域地磁活动上升相存在过响应，下降相则响应不足。太阳辐射流量 $f _ { 1 0 . 7 }$ 和阻力系数 $C _ { d }$ 序列整体表现出较强正相关,低频部分 $f _ { 1 0 . 7 }$ 上升相 $C _ { d }$ 序列基本保持稳定，下降相 $C _ { d }$ 序列相应下降表明NRLMSIS-OO 模式在太阳辐射流量上升相响应适度，下降相存在过响应高频部分呈现很强的正相关表明NRLMSIS-OO模式在 $f _ { 1 0 . 7 }$ 上升相存在小尺度上的响应不足而下降相存在过响应。

分析不同回归模型和不同回归分析样本序列长度 $n$ 的情况下的 $C _ { d }$ 预报值残差结果表明 $f _ { 1 0 . 7 }$ 一元回归模型取 $n _ { \mathrm { ~ } } = 2 0$ d时， $C _ { d }$ 预报结果最优。另外统计发现回归系数 $\alpha _ { i 0 } \alpha _ { i 1 } \alpha _ { i 2 } \alpha _ { i 3 } \alpha _ { i 4 }$ 波动较大故方法只适用于 $C _ { d }$ 短期预报。此外磁扰期 $C _ { d }$ 预报会出现毛刺需平滑处理。因不同大气模式在各空间环境变化段中表现出的误差是不同的故回归系数对不同大气模式不具有普遍适用性。

统计显示弧长 $^ 3 \mathrm { ~ h ~ }$ 解算阻力系数序列与对应$A _ { p }$ 序列呈极弱相关性，可能是解算弧长不够等因素引入其它误差导致 具体原因有待深入研究。本文从小波分解的角度列出卫星阻力系数与空间环境参量变化关系为 $C _ { d }$ 预报提供了方法，解决了现有工程中普遍采用前段定轨解算阻力系数值用于后续轨道预报时在空间环境剧烈波动期引入较大误差的问题。分析方法对提高航天器轨道预报精度具有重要参考价值。

# 参考文献

[1]Doornbos E，Klinkrad H，VisserP.Atmosphericdensity calibration using satellite drag observations [J].Advances in Space Research,2005 ,36(3):515-521.   
[2] Doornbos E Klinkrad H,Visser P.Use of two-line element data for thermosphere neutral density model calibration [J]．Advances in Space Research,2008,41(7):1115-1122.   
[3] LechtenbergTF，McLaughlinCA，LockeT，etal. Thermospheric density variations: observability using precision satellite orbits and effects on orbit propogation [J].Space Weather,2013,11(1):34-45.   
[4] Pardini C，Moe K，Anselmo L.Thermospheric density model biases at the 23rd sunspot maximum [J].Planetary and Space Science,2012,67(1):130-146.   
[5]Moe K,Moe M M.Gas- surface interactions and satelite drag coefficients [J]．Planetary and Space Science,2Oo5,53(8): 793 -801.   
[6]Gaposchkin EM,Coster AJ.Analysis of satellite drag[M]. Lexington(USA) :Lincoln Lab,1988.   
[7]Cook G E.Satellite drag coefficients [J]．Planetary and Space Science,1965,13(10):929-946. [8］马淑英，李晶，周云良．大气拖曳引起卫星轨道衰减的数值 模拟[J]．宇航动力学学报,2012,3(1)：9-14.[Ma Shuying Li Jing,Zhou Yun-liang.Simulation of orbit decay for LEO satellite causedbyatmosphericdrag[J].Journalof Astrodynamics ,2012,3(1):9 -14.] [9]Pardini C,Tobiska WK，Anselmo L.Analysis of the orbital decay of spherical satellites using different solar flux proxies and atmospheric density models [J]．Advances in Space Research，   
2006,37(2):392-400. [10]Storz MF,Bowman BR,Branson MJI,et al.High accuracy satellite drag model（HASDM)[J]．Advances in Space Research,2005,36(12):2497 -2505. [11]Bowman B R,Storz M F.High accuracy satelite drag model （HASDM) review [J].Advances in the Astronautical Sciences,   
2003,116:1943-1952. [12]陈建荣，王家松．磁暴下的LEO卫星精密轨道确定[J]．飞 行器测控学报,2005,24(6)：34-38.[Chen Jian-rong， Wang Jia-song.Precision orbit determination of low-earth orbiters under magnetic storms[J].Journal of Spacecraft TT&C Technology ,2005,24(6):34-38.] [13]黄卫东，张育林．分布式卫星轨道构形的大气摄动分析及修 正方法[J]．宇航学报,2005,26(05)：649-652.[Huang Wei-dong,Zhang Yu-lin.Analysis of atmospheric perturbation to distributed satellites orbit configuration and its modified method [J]．Journal of Astronautics,2005 ,26(05):649-652.] [14]刘舒前，龚建村，刘四清，等．中长期轨道预报中大气阻力 系数补偿算法的研究[J]．宇航学报,2013,34(2)：157-   
162.[Liu Shu-shi,Gong Jian-cun，Liu Si-qing，et al. Atmospheric drag coefficient calibration in medium-term orbit prediction [J]． Journal of Astronautics,2013,34(2)：157 -   
162.]   
[15] KumarP，Foufoula G E.Wavelet analysis for geophysical applications [J].Reviews of Geophysics,1997,35(4):385- 412.   
[16] 匡正，季仲贞，林一驿．华北降水时间序列资料的小波分析 [J]．气候与环境研究,2000,5（3)：312-317.[Kuang Zheng,Ji Zhong-zhen,Lin Yi-hua.Wavelet analysis of rainfall data in north china [J].Climatic and Enviromental Research， 2000,5(3):312 -317.]   
[17] Bowman BR.True satellite ballistic coefficient determination for HASDM[C]．AIAA/ASS Astrodynamics Specialist Conference and Exhibit,California,USA,August5-8,2002.   
[18] 李济生．人造卫星精密轨道确定[M].北京：解放军出版 社,1995:1 -16.   
[19] Mallat S G.A theory for multiresolution signal decomposition: the wavelet representation [J].Pattern Analysis and Machine Intelligence,IEEE Transactions on,1989,11(7):674-936.   
[20]王明祥，宁宇蓉，王晋国．基于Mallat 算法的一维离散小波 变换的实现[J]．西北大学学报（自然科学版），2006，36 (3):364-368.[Wang Ming-xiang,Ning Yu-rong,Wang Jinguo．Realization of one dimension discrete wavelet transform based on Mallat algorithm [J].Journal of Northwest University (Natural Science Edition）,2006 ,36(3):364-368.]   
[21]熊智新，胡慕伊，陈朝霞，等．离散小波变换算法剖析及其 通用程序实现[J]．计算机工程与设计，2007，28（20)： 4856-4859.[ Xiong Zhi-xin,Hu Mu-yi ,Chen Zhao-xia,et al. Analysis of discrete wavelet transform algorithm and its general implementation for programming [J].Computer Engineering and Design,2007,28(20):4856-4859.]

# 作者简介：

刘卫(1984-）男硕士助理研究员主要从事人造卫星精密定轨及空间碎片碰撞预警研究。  
通信地址：北京市8701信箱(100190)  
电话：（010)62586415  
E-mail:liuwei $@$ nssc.ac.cn

(编辑:牛苗苗)