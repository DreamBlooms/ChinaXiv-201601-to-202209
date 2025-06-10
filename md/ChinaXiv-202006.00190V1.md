# 宁夏沿黄城市带植被覆盖时空演变及其驱动力分析

吴加敏}，蔡创创²，孙灏²，姚建华'，陈伟²，顾继升'，蒋金豹²（1．宁夏回族自治区遥感测绘勘查院(宁夏回族自治区遥感中心）,宁夏 银川750021；2．中国矿业大学(北京)地球科学与测绘工程学院,北京100083)

摘要：宁夏沿黄城市带是宁夏经济社会发展的精华地带,探索该区域的生态环境问题对宁夏沿黄城市带建设意义重大。本文基于2002—2018 年的 MODIS 遥感数据,利用 Mann-Kendall非参数检验、Sen's 斜率估计、景观格局分析、偏相关分析以及残差趋势分析方法，研究了该区域植被覆盖状况的时空演变过程及趋势。结果表明：2002—2018 年宁夏沿黄城市带约 $4 4 . 9 1 \%$ 区域的植被覆盖度显著增加,约 $1 . 3 1 \%$ 区域的植被覆盖度显著减少，约 $5 3 . 7 8 \%$ 区域的植被覆盖度变化不显著;宁夏沿黄城市带植被覆盖度变化与气温具有较强的负相关性,与降水具有较强的正相关性；宁夏沿黄城市带 $8 1 . 4 0 \%$ 的区域人为因素对植被覆盖度多年变化趋势的贡献率大于 $5 0 \%$ ，有约 $2 4 \%$ 的区域气候因素对植被覆盖度多年变化趋势的贡献率大于 $5 0 \%$ 。

关键词：植被覆盖度；时空演变；驱动力；Mann-Kendall非参数检验；Sen's 斜率估计；沿黄城市带；宁夏

宁夏沿黄城市带是以地缘相近、交通便利、经济关联度较高的银川市为中心，石嘴山、吴忠、中卫3个地级市为主干形成的城镇集合体，是宁夏城镇分布最密集、生产力要素最活跃的区域，也是宁夏经济社会发展的精华地带。宁夏沿黄城市带以宁夏全区$43 \%$ 的土地面积创造了该区 $90 \%$ 以上的GDP和财政收入，承载着引领宁夏工业化和城市化建设的重任。然而，工业化和城镇化的迅速发展，给社会带来巨大效益的同时，也可能会引发诸多生态环境问题，例如大气污染、水体污染、绿地覆盖度减少、湖泊面积缩小等。定量评价与深入分析沿黄城市带工业化和城镇化已经或引发的生态环境问题，对于宁夏沿黄城市带建设具有重大意义。植被作为陆地生态系统的主体，是连接土壤、大气和水分等要素的自然纽带，因此成为陆地生态环境的重要“指示器”之_[1-3]。植被覆盖度（fractional vegetation cover,FVC)定义为植被垂直投影面积与地表面积的比值，通常用百分比 $( \% )$ 来表示，是进行区域生态系统评估的重要定量指标[4-6]。本文针对宁夏沿黄城市带植被覆盖度的时空演变过程和趋势开展研究，期望从植被覆盖度的角度，透视宁夏沿黄城市带工业化和城镇化已经或引发的生态环境问题。遥感技术在监测植被覆盖度方面具有多光谱、多分辨率、多时相、多角度、快速成像等优势[7-8],已经成为监测全球及区域植被覆盖变化的最主要手段。目前，已形成多种植被覆盖度遥感计算方法，这些方法大致可分为： $\textcircled{1}$ 物理模型法：如一种利用中等分辨率与高分辨率卫星图像相结合建立植被覆盖度提取模型，以获取大范围植被覆盖度的方法[9];动态贝叶斯网络方法，将辐射传输模型与作物生长统计模型相结合，从中分辨率成像光谱仪（MODIS）反射率数据中提取植被覆盖度，综合利用遥感数据和作物生长特性的信息[1o];叶面积指数(leaf area index,LAI)模型反演法,可准确估算出乔、灌、草覆盖度[1-12]。 $\textcircled{2}$ 回归模型法：如利用归一化植被指数（normalizeddifferencevegetation index,NDVI）和实测的FVC 构建回归分析模型[13];利用实测的地面覆盖度数据与SAVI（soil adjusted vegetation index）建立了锡林浩特地区植被覆盖度的线性回归模型[14];选取了包括DVI（simple difference vegetation indices）、NDVI、SA-VI等20种植被指数,利用回归模型估算植被覆盖度[15]。 $\textcircled{3}$ 混合像元分解法：如利用像元二分模型估算植被覆盖度[16-17];使用亚像元分解模型进行植被覆盖度的动态变化分析[18]；采用干枯燃料指数

（deadfuleindex，DFI）构建NDVI-DFI像元三分模型，估算了锡林郭勒草原的光合植被覆盖度和非光合植被覆盖度[19];采用面向对象多端元混解模型，有效地减少了计算量和混合像元的端元变化，提高了植被覆盖度反演精度[20]。 $\textcircled{4}$ 机器学习法：如利用神经网络和PROSAIL辐射传输模型来反演植被覆盖度,并生成了CYCLOPES覆盖度产品[21]；利用支持向量机（supportvectormachine,SVM)方法来识别半干旱区的植被类型，在SVM结果上进一步估算研究区域的 FVC[22];基于IKONOS 遥感影像,利用决策树分类方法估算乔木植被覆盖度，分类精度达97.3%[23]  
O

本文的主要目的在于揭示宁夏沿黄城市带FVC的时空演变过程和趋势，考虑到长时间序列分析对遥感数据的一致性要求、研究区的地表覆盖类型特点（主要是草地和耕地），以及技术方法的鲁棒性、可行性等，基于LAI反演FVC的物理模型。

# 1 数据资料

# 1.1 研究区概况

图1为宁夏沿黄城市带的空间分布，图中的土地覆盖类型为2017年的MODIS（ormoderateresolu-tion imaging spectroradiometer）土地覆盖类型产品MCD12Q1，分类模式为IGBP全球植被分类，该土地覆盖类型的空间分辨率是 $5 0 0 \mathrm { ~ m ~ }$ 。宁夏沿黄城市带国土面积约为 $4 . 1 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,地理坐标 $1 0 4 ^ { \circ } 2 2 ^ { \prime } \sim$ $1 0 7 ^ { \circ } 5 0 ^ { \prime } \mathrm { E } \ : . 3 6 ^ { \circ } 4 3 ^ { \prime } \sim 3 9 ^ { \circ } 2 2 ^ { \prime } \mathrm { N }$ ,属温带大陆性半湿润半干旱气候,年均气温 $5 \sim 9 ~ \mathrm { { ^ { c } C } }$ ,年降水 $1 8 0 \sim 6 8 0 ~ \mathrm { m m }$ 。该区域的地表覆盖类型主要是草地和耕地，占整个研究区的 $9 3 \%$ 以上，另外还有少量的灌丛，城市和建成区以及稀疏植被。

# 1.2 遥感数据

本研究主要采用MODIS叶面积指数（LAI)产品、地表覆盖类型产品、太阳天顶角数据产品以及地表反射率产品。其中LAI产品具体为MCD15A2，时间分辨率为8d,空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ ,时间范围为2002—2018年，影像合计759景，空间轨道范围为$\mathtt { h } 2 6 \mathrm { v } 0 5$ 。地表覆盖类型产品具体为MCD12Q1，时间分辨率为1a,空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ ，时间为2017年，影像合计1景。太阳天顶角数据产品具体为MOD09A1,时间分辨率为8d,空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ ，时间范围为2002—2018年，影像合计759景。地表反射率产品为MOD09A1，时间分别为MOD09A1.A2018177、MOD09A1．A2018193、MOD09A1.A2018209、MOD09A1.A2018225共4景。首先利用MODISReprojection Tools（MRT）工具对LAI数据、太阳天顶角数据、地表覆盖类型产品；以及地表反射率数据进行坐标转换、格式转换、投影转换等一系列预处理。通过ENVI/IDL,利用研究区的矢量数据进行裁剪得到研究区LAI数据、地表覆盖类型产品、太阳天顶角以及地表反射率数据

![](images/c60985d43d1269a371651c8d38c7ee7085d3218e3e52ae5aa88fff9d92237623.jpg)  
图1宁夏沿黄城市带空间分布以及主要地表覆盖类型 Fig.1Ningxia along the yellow city belt distribution

# 2 研究方法

# 2.1 植被覆盖度计算

基于辐射传输模型理论，植被覆盖度与植被叶面积指数密切相关，存在一个经典物理意义上的转换公式[24]：

$$
\mathrm { F V C } = 1 - \mathrm { e } ^ { \left[ \mathbf { \xi } - G \left( \theta \right) \times \mathrm { L A L } / \mathrm { c o s } \theta \right] }
$$

式中： $G ( \theta )$ 为叶片投影因子,取值为 $0 . 5 ^ { [ 2 5 ] }$ ; $\theta$ 为太阳天顶角。

$$
\mathrm { F V C } = 1 - \mathrm { e } ^ { - \mathrm { L A V } ( 2 \mathrm { c o s } \theta ) }
$$

式中：FVC的取值范围为0～1,通常情况下 $\mathrm { F V C } <$ $20 \%$ 为低植被覆盖区； $2 0 \% < \mathrm { F V C } < 4 0 \%$ 为中低植被覆盖区; $4 0 \% < \mathrm { F V C } < 6 0 \%$ 为中植被覆盖区;

$6 0 \% < \mathrm { F V C } < 8 0 \%$ 为中高植被覆盖区； $\mathrm { F V C } > 8 0 \%$   
为高植被覆盖区。

此外，为减少大气的云、颗粒、阴影、视角以及太阳高度角等对LAI数据的影响[26],本文根据具体的研究尺度，采用最大值合成法（maximumvaluecom-posit,MVC）,对8d尺度的LAI进一步处理,其表达式如下：

$$
\mathrm { L A I } ^ { i } = \underset { i = 1 } { M a x } \mathrm { L A I } _ { i }
$$

式中： $\mathrm { L A I } ^ { i }$ 是第 $i$ 年（月)LAI最大合成值，即LAI的最高值; $\mathrm { L A I } _ { i }$ 为各像元8d合成最大LAI值; $d$ 为第$i$ 年（月） $\cdot 8 \mathrm { ~ d ~ }$ 合成LAI影像总数。

# 2.2 时间序列分析方法

2.2.1Mann-Kendall非参数检验Mann-Kendall非参数检验方法[27]是目前被广泛应用的趋势分析方法，能很好地揭示时间序列的趋势变化，其优点在于不需要遵从一定的正态分布，也不受少数异常值的干扰。设某时间序列为 $\{ X _ { i } \}$ （ $i = 1 , 2 , \cdots , n )$ ，时间序列 $\{ X _ { i } \}$ 的对偶数：

$$
S = \sum _ { i = 1 } ^ { n - 1 } \sum _ { j = i + 1 } ^ { n } { \mathrm { s g n } ( X _ { j } - X _ { i } ) }
$$

$$
\operatorname { s g n } ( X _ { j } - X _ { i } ) = { \left\{ \begin{array} { l l } { + 1 , ( X _ { j } - X _ { i } ) > 0 } \\ { 0 , ( X _ { j } - X _ { i } ) = 0 } \\ { - 1 , ( X _ { j } - X _ { i } ) < 0 } \end{array} \right. }
$$

式中： $s$ 为正态分布，均值为0,方差 $\operatorname { V a r } ( S ) = n ( n -$ 1） $( 2 n + 5 ) / 1 8$ 。当 $n > 1 0$ 时，Mann-Kendall统计量 $U$ ：

$$
\begin{array} { r l r } {  { \frac { S - 1 } { \sqrt { \operatorname { V a r } ( S ) } } , } } & { { } S > 0 } \\ { U = } & { { } 0 , \qquad S = 0 } \\ { \frac { S + 1 } { \sqrt { \operatorname { V a r } ( S ) } } , } & { { } S < 0 } \end{array}
$$

M-K统计量 $U$ 的取值范围为 $( - \infty , + \infty )$ 。如果 $\mid U \mid > U _ { 1 - \alpha / 2 }$ 即 $\alpha$ 置信水平上，时间序列数据存在明显的上升或下降趋势。 $U > 0$ 时，表示时间序列$\{ X _ { i } \}$ 为上升趋势； $U < 0$ 时，表示时间序列 $\{ X _ { i } \}$ 为下降趋势。

根据显著性水平以及统计量 $U$ 将变化趋势分为5个等级，分级结果见表1。

2.2.2 Sen's 斜率估计 Mann-Kendall 算法可以实现时间序列的趋势显著性检验，但无法得到时间序列的变化率。Sen's斜率估计对Mann-Kendall算法进行了补充，能够准确计算时间序列的变化率 $\beta _ { \circ }$ 当 $\beta > 0$ 时，序列呈上升趋势；当 $\beta = 0$ 时，表示序列变化趋势不明显；当 $\beta < 0$ 时,序列呈下降趋势。

表1显著性检验结果分级  
Tab.1 Classification of significance test results   

<html><body><table><tr><td>变化趋势</td><td>统计量U</td><td>显著性水平</td></tr><tr><td>极显著减少</td><td>U<0</td><td>α<0.01</td></tr><tr><td>一般显著减少</td><td></td><td>0.01<α<0.05</td></tr><tr><td>基本不变</td><td></td><td>α>0.05</td></tr><tr><td>一般显著增加</td><td>U>0</td><td>0.01<α<0.05</td></tr><tr><td>极显著增加</td><td></td><td>α<0.01</td></tr></table></body></html>

对于时间序列 $x _ { i } = \left( \ b { x } _ { 1 } , \ b { x } _ { 2 } , \cdots , \ b { x } _ { n } \right)$ ,Sen's斜率 $\beta$ 的计算公式为：

$$
\beta = \mathrm { M e d i a n } \left( \frac { x _ { j } - x _ { i } } { j - i } \right) , \forall j > i
$$

式中：Median为中值函数，即先将得到的序列按照从小到大的顺序排列，如果序列对是奇数，则取最中间的一个数作为Sen's斜率，如果序列对是偶数，则取最中间的两个数的平均数作为Sen's斜率; $\forall$ 表示任意。

# 2.3偏相关分析以及残差趋势分析

2.3.1偏相关分析偏相关分析是指两个变量同时与第3个变量相关时，将第3个变量的影响剔除，只分析另外两个变量间相关程度的过程[28],该方法在一定程度上能够减弱因某一因素的变化导致其他因素与因变量的关系的影响。本文基于像元计算FVC 与气候指标的偏相关系数，首先计算FVC与年平均气温和年降水的简单相关系数，进而得到偏相关系数。计算公式如下：

$$
R _ { x _ { - } y . z } = \frac { R _ { x y } - R _ { x z } \cdot R _ { y z } } { \sqrt { ( 1 - R _ { x z } ^ { 2 } ) ( 1 - R _ { y z } ^ { 2 } ) } }
$$

式中： $R _ { x _ { - } y . z }$ 为固定变量后变量 $x$ 与 $y$ 的偏相关系数;$R _ { { _ x y } } , R _ { { _ x z } } , R _ { { _ y z } }$ 分别为 $x$ 与 $y , x$ 与 $_ { z , y }$ 与 $z$ 之间的相关系数。

2.3.2残差趋势分析气候因素以及人为因素是影响FVC变化的两大因素。其中气温、降水是气候因素中的两大主要因素。鉴于其他气候因素对FVC变化的影响相对较小，笔者在气象因素中仅考虑气温、降水两大因素。利用残差趋势分析法将每个像元的FVC与气候因子(年平均气温、年降水)做回归分析，进而得到每个像元的FVC预测值，该预测值为单个气候因子对FVC的影响，以偏相关系数的大小作为权值进行加权平均，获得最终FVC的预测值，即气候因素对FVC的贡献值。将每个像元的FVC真值减去FVC预测值可到人类活动对FVC的影响值，即人为因素对FVC的贡献值。具体为：

$$
\mathrm { F V C } _ { \mathrm { c l i m a t e } } = W _ { \mathrm { p r e d } \_ \mathrm { t e m p } } \times \mathrm { F V C } _ { \mathrm { p r e d } \_ \mathrm { t e m p } } + W _ { \mathrm { p r e d } \_ \mathrm { p r e c } } \times
$$

$$
\mathrm { F V C } _ { \mathrm { p r e d \_ p r e c } }
$$

式中： $W _ { \mathrm { p r e d \mathrm { - } t e m p } } ~ = ~ \frac { R _ { \mathrm { F V C \mathrm { - } t e m p . \ p r e c } } } { R _ { \mathrm { F V C \mathrm { - } t e m p . \ p r e c } } + R _ { \mathrm { F V C \mathrm { - } p r e c . \ t e m p } } }$ $W _ { \mathrm { p r e d \_ p r e c } }$ $= \frac { R _ { \mathrm { F V C \mathrm { _ { \mathrm { - } \ p r e c \cdot \mathrm { _ { \ell } e m p } } } } } } { R _ { \mathrm { F V C \mathrm { _ { \mathrm { - } \ell } t e m p . \mathrm { p r e c \it } } } } + R _ { \mathrm { F V C \mathrm { _ { \mathrm { - } \ p r e c \mathrm { _ { \mathrm { - } \ell } t e m p } } } } } } ; \mathrm { F V C _ { \mathrm { _ { \mathrm { _ { \mathrm { } r e d \mathrm { _ { - } \ell } t e m p } } } } } , F V C _ { \mathrm { _ { \mathrm { _ { \mathrm { p r e d \mathrm { _ { - } \ell } } p r e c \mathrm { _ { \ell } } } } } } } }$ 别为FVC与年平均气温、年降水线性回归预测值。

$$
\mathrm { F V C } _ { \mathrm { h u m a n } _ { - } t } = \mathrm { F V C } _ { \mathrm { t r u e } _ { - } t } - \mathrm { F V C } _ { \mathrm { c l i m a t e } _ { - } t }
$$

式中： $\mathrm { F V C } _ { \mathrm { h u m a n } \_ t }$ 为像元在第 $\mathbf { \chi } _ { t }$ 年人为因素对FVC 的贡献值; $\mathrm { F V C } _ { \mathrm { t r u e } \_ t }$ 为像元在第 $\mathbf { \chi } _ { t } ^ { }$ 年的真实值;$\mathrm { F V C } _ { \mathrm { c l i m a t e } \_ t }$ 为像元在第 $\mathbf { \chi } _ { t }$ 年气候因素对FVC 的贡献值。

$$
\frac { \mathrm { d } \mathrm { F V C } _ { \mathrm { t r u e } } } { \mathrm { d } t } = \frac { \mathrm { d } \mathrm { F V C } _ { \mathrm { c l i m a t e } } } { \mathrm { d } t } + \frac { \mathrm { d } \mathrm { F V C } _ { \mathrm { h u m a n } } } { \mathrm { d } t }
$$

$$
= C ( { \mathrm { ~ c l i m a t e } } ) + C ( { \mathrm { ~ h u m a n } } )
$$

式中： $\mathrm { d F V C _ { \mathrm { t r u e } } / d \boldsymbol { t } \mathrm { \Omega } , \mathrm { d F V C _ { \mathrm { c l i m a t e } } / d \boldsymbol { t } \mathrm { \Omega } , \mathrm { d F V C _ { \mathrm { h u m a n } } / d \boldsymbol { t } \mathrm { \Omega } } } }$ 分别

表示FVC多年变化趋势、气候因素、人为因素对FVC多年变化趋势的贡献。

进一步可以求得气候以及人为因素对FVC多年变化趋势的贡献率 $\rho ( \chi )$ 为：

$$
\rho ( \chi ) = \frac { C ( \chi ) } { d \mathrm { F V C } _ { \mathrm { t r u e } } / d t } \times 1 0 0 \%
$$

# 3结果与讨论

# 3.1植被覆盖度计算结果交叉验证

利用像元二分模型计算FVC，根据沿黄城市带植被覆盖的实际情况以及植被指数NDVI灰度分布频率累计表，选择 $9 9 . 5 \%$ 和 $0 . 5 \%$ 的置信区间内上下限累计频率值作为纯植被覆盖时的NDVI和纯土壤地表的NDVI。从像元二分模型和LAI模型中等间隔提取200个像元对，相关性分析如图2所示。结果表明两者的相关系数分别为：0.848（177），0.847（193），0.766（209），0.775（225），均在显著性水平 $\cdot P < 0 . 0 1$ 的情况下显著相关;其次斜率分别为：1.046(177),0.974(193）,0.923(209）,0.971(225），均接近于 $y = x$ 。因此,本文基于LAI计算的FVC 具有较大的可靠性。

![](images/f27449b2beca50eb0fc9fb9099b9c74c5673522de79bcaa7f22ec3776dde7c3f.jpg)  
图2LAI反演FVC-NDVI反演FVC交叉验证  
Fig.2LAI retrieve FVC-NDVI retrieve FVC cross validation

![](images/634b1a7777d3dacc972094a6a1432386a17ef88d2359b4e22c814c0791d624a5.jpg)  
Fig.3Vegetation coverage distribution along the yellow city belt in Ningxia from 2OO2 to 2018

# 3.2植被覆盖度的空间分布格局

图3为2002—2018年(间隔4a显示)宁夏沿黄城市带植被覆盖度空间分布。可以看出，石嘴山市南部植被覆盖度较高，北部偏低；银川市植被覆盖度最高，且主要集中在北部；吴忠市植被覆盖度整体偏低，较高区域主要集中在西北部;中卫市植被覆盖度整体偏低，较高区域主要集中在西北部。其次，2002—2006年植被覆盖度最低。

图4为宁夏沿黄城市带 2002—2018 年（间隔4a)各等级植被覆盖面积占比。从图中可以看出，5个年份植被覆盖度低的区域面积占比较高。其中低植被覆盖区面积占比在2006年出现了极显著增加，达到了 $4 4 . 6 1 \%$ ；中低植被覆盖区面积占比出现极显著减少，减少至 $3 4 . 6 6 \%$ ;其余4个年份面积占比相对稳定;中、中高、高植被覆盖区面积占比在这5a间呈增加的趋势，分别由2002年的 $1 4 . 9 4 \% . 8 . 0 4 \%$ 、$2 . 7 9 \%$ 增加至2018年的 $3 1 . 1 8 \% . 1 4 . 9 2 \% . 7 . 8 4 \%$ 。

# 3.3植被覆盖度的时间变化过程

MODISLAI产品起始时间为2002年7月4日，故2002年6月无相应的数据。由图5可见，植被覆盖度在5一9月呈现出先上升后下降的变化趋势，5—8月植被覆盖度有所上升，且8月植被覆盖度达到最大,9月植被覆盖度显著下降。其次，5个年份中，2018 年各月份植被覆盖度均最大;而2006 年各月份植被覆盖度均最小。

![](images/70978f59852d6a7fa52b985337bb6b25845f96753596b3c993912449ca0f2f12.jpg)  
图32002—2018年宁夏沿黄城市带植被覆盖度分布  
图42002—2018 年各等级植被覆盖度面积占比Fig.4Proportion of vegetation coverage of eachgrade from 2002 to 2018

由图6可知，2002—2018年年均植被覆盖度总体呈线性增长态势 $( 0 . 7 8 \% \cdot { \mathrm { ~ a ~ } } ^ { - 1 }$ ， $P < 0 . 0 1 { \ : } )$ ，最低值 $2 7 . 6 8 \%$ 发生在2005 年，最大值 $4 6 . 1 2 \%$ 发生在2018年。其中，2002—2005年呈下降趋势，由

![](images/5b56fdb2951aa7608f2273fe6fea4817f419f9bd9a9165a067b05ded37033c8c.jpg)  
图52002—2018 年生长季(间隔4a)FVC 年内变化 Fig.5Annual changes of FVC during the growth season from 2002 to 2018(4 years interval)

![](images/2133116bed969b165a164eb96d16b6fe068923fa7f91579700bd73f1a4c87413.jpg)  
图62002—2018年年均值FVC 变化 Fig.6Annual mean FVC change from 20O2 to 2018

$3 3 . 8 1 \%$ 下降至 $2 7 . 6 8 \%$ ;2005—2007—2008 年呈现 先增 $8 . 5 2 \%$ 后降 $4 . 5 2 \%$ ;2008—2012—2015 年呈先 增 $1 0 . 8 3 \%$ 后降 $7 . 2 4 \%$ ;2015—2018年呈上升趋 势,由 $3 5 . 2 7 \%$ 上升至 $4 6 . 1 2 \%$ 。

# 3.4植被覆盖度的演变趋势

图7为2002—2018年各等级植被覆盖度时间序列变化。总体看来，2002—2018年低植被覆盖像元数呈减少趋势 $( \mathbf { \nabla } - 2 7 4 8 \cdot \mathbf { a } ^ { - 1 }$ ， $\textstyle P < 0 . 0 5 { \mathrm { ~ , ~ } }$ ；中低植被覆盖像元数增幅极小且极不显著;中植被覆盖区、中高植被覆盖区、高植被覆盖区FVC像元数均呈增加趋势。其中，中高植被覆盖区、高植被覆盖区像元数增加趋势极显著 $\left( P < 0 . 0 1 \right)$ 。

图8是利用Mann-Kendall非参数检验和Sen's斜率分析得到的宁夏沿黄城市带植被覆盖度变化趋势及变化率，表2统计了相应的面积变化及其比例。研究表明，2002—2018年宁夏沿黄城市带植被覆盖度显著增加的区域占总面积的 $4 4 . 9 1 \%$ ,主要分布在清水河和黄河沿岸，以及石嘴山和中卫市的东南部区域；植被覆盖度显著减少的区域占总面积的$1 . 3 1 \%$ ，主要分布在银川、吴忠和中卫市建成区及其附近，主要是由于城市建筑用地扩张引起的；植被覆盖度变化不显著的区域占总面积的 $5 3 . 7 8 \%$ 。其中，植被覆盖度一般显著增加和极显著增加的面积分别占研究区总面积的 $1 9 . 3 7 \%$ 和 $2 5 . 5 4 \%$ 。相比之下，植被覆盖度减少的地区面积占比相对较小。其中，植被覆盖度一般显著减少和极显著减少的面积分别占研究区总面积的 $0 . 6 5 \%$ 和 $0 . 6 6 \%$ 。FVC变化率小于-0.0004的区域占总面积的 $6 . 7 8 \%$ ;

![](images/7c1a2cedfb02c202dd2354047d6ef07fea226d1e836cb867b4db2ceb56f6c2d4.jpg)  
图72002—2018年不同植被覆盖像元数变化  
Fig.7Variation of pixel number of different vegetation cover from 2OO2 to 2018

![](images/813a30670428a7a589dc22f35056203e32aa0dde81eb923883d882149a683152.jpg)  
图82002—2018宁夏沿黄城市带FVC 变化趋势及变化率 Fig.8Change trend and change rate of FVC along yelow city belt in Ningxia from 2OO2 to 2018

表2 2002—2018 年宁夏沿黄城市带 Sen's $\mathbf { + M - K }$ 面积占比变化  
Tab.2Area change of Sen's $\mathbf { + M - K }$ in the yellow belt of ningxia from 2012 to 2018   

<html><body><table><tr><td></td><td>(-0.048，-0.01]</td><td>(-0.01,-0.0004]</td><td>(-0.0004,0.0004]</td><td>(0.0004,0.01]</td><td>(0.01,0.062]</td><td>合计</td></tr><tr><td>极显著减少</td><td>0.56</td><td>0.10</td><td>0</td><td>0</td><td>0</td><td>0.66</td></tr><tr><td>-般显著减少</td><td>0.31</td><td>0.34</td><td>0</td><td>0</td><td>0</td><td>0.65</td></tr><tr><td>基本不变</td><td>0.20</td><td>5.27</td><td>2.79</td><td>43.39</td><td>2.13</td><td>53.78</td></tr><tr><td>-般显著增加</td><td>0</td><td>0</td><td>0</td><td>12.12</td><td>7.25</td><td>19.37</td></tr><tr><td>极显著增加</td><td>0</td><td>0</td><td>0</td><td>5.11</td><td>20.43</td><td>25.54</td></tr><tr><td>合计</td><td>1.07</td><td>5.71</td><td>2.79</td><td>60.62</td><td>29.81</td><td>100.00</td></tr></table></body></html>

变化率介于 $- 0 . 0 0 0 \ 4 \sim 0 . 0 0 0 \ 4$ 之间的区域占研究区总面积的 $2 . 7 9 \%$ ;变化率介于 $0 . 0 0 0 \ 4 \sim 0 . 0 1$ 的区域面积占研究区总面积的 $6 0 . 6 2 \%$ ;变化率介于$0 . 0 1 \sim 0 . 0 6 2$ 的区域占研究区总面积的 $2 9 . 8 1 \%$ 0总之，从变化趋势以及变化率的角度均可看出，宁夏沿黄城市带整体FVC增加趋势较为明显。

# 4讨论

# 4.1植被覆盖度变化与气候因素的相关性

图9为宁夏沿黄城市带年最大FVC与年平均气温和年降水的偏相关系数空间分布。由年最大FVC与年平均气温的空间相关性分析可知，正相关的区域主要分布在黄河以及清水河沿岸周边，土地利用类型以耕地为主;呈现负相关和较弱相关的区域主要集中在城市和建成区周边，以及中卫市中部和东南部区域，土地利用类型以草原为主。由年最大FVC与年降水空间相关性分析可知，与气温的空间相关性相反，正相关区域主要集中在中卫市、吴忠市以及银川市的西北部和东南部，主要土地利用类型为草地，少部分为耕地。呈现负相关以及相关性较弱的区域主要集中在城市和建成区附近。整体而言，与年均气温相比，年最大FVC与年降水的相关性更强。

# 4.2气候及人为因素对植被覆盖度趋势的贡献

植被覆盖度变化是气候因素和人为因素共同作用的结果，分析气候因素和人为因素对宁夏沿黄城市带植被覆盖度的变化趋势贡献尤为重要。图10为气候及人为因素对多年FVC变化趋势贡献率的空间分布。从图10a可知，贡献率小于 $1 1 \%$ 的区域主要集中在城市建成区及其周围，面积占比约$6 . 8 \%$ ,其中石嘴山市较为集中;贡献率介于 $1 1 \%$ \~$31 \%$ 之间的区域主要集中在黄河沿岸以及清水河沿岸,面积占比约 $3 7 . 7 \%$ 。贡献率大于 $5 0 \%$ 的区域呈零散分布，面积占比约 $2 4 \%$ ,在中卫市、吴忠市较为集中。从图10b可知， $6 . 2 \%$ 的区域贡献率小于$31 \%$ ; $1 2 . 4 \%$ 的区域贡献率介于 $3 1 \% \sim 5 0 \%$ 之间;

![](images/74ded6b593d2f090abd4135089223bb1fd7e9bbb3f7c49f49afbd50dfa154701.jpg)  
  
图9丁夏沿黄城币带年最大值rV与年平均气温和年降水的偏相大系数空间分布 Fig.9Spatialdistributionof partial corelation coeffcient between annual maximum FVCand annual mean temperature and annual precipitationin the yellow citybelt of Ningxia

![](images/53f2c909b68bb3e087a565b631e03a24b2eab636566dc669adfa311b953b5fbc.jpg)  
图102002—2018年宁夏沿黄城市带气候因素和人为因素对FVC变化趋势的贡献率  
Fig.1OContributionrateof climatefactorsand human factors toFVCvariation trend intheyellowcitybeltof Ningxi from 2002 to 2018

$8 1 . 4 \%$ 的区域贡献率大于 $5 0 \%$ 。相比于气候因素，人为因素对FVC的贡献率整体较高。

# 5结论

（1）Mann-Kendall非参数检验表明，2002—2018年宁夏沿黄城市带约 $4 4 . 9 1 \%$ 区域的植被覆盖度显著增加，约 $1 . 3 1 \%$ 区域的植被覆盖度显著减少，约 $5 3 . 7 8 \%$ 区域的植被覆盖度变化不显著

(2）Sen's斜率分析表明,2002—2018 年宁夏沿黄城市带约 $6 0 . 6 1 \%$ 区域的FVC变化率介于$0 . 0 0 0 4 \sim 0 . 0 1$ 之间，约 $2 9 . 8 1 \%$ 区域的FVC变化率介于 $0 . 0 1 \sim 0 . 0 6 2$ 之间，约 $2 . 8 0 \%$ 区域的FVC变化率介于 $- 0 . 0 0 0 \ 4 \sim 0 . 0 0 0 \ 4$ 之间,约 $6 . 7 8 \%$ 区域的FVC 变化率小于 $- 0 . 0 0 0 \ 4$ 。

（3）宁夏沿黄城市带FVC与年平均气温呈显著负相关，与年降水呈显著正相关，说明气候因子是影响宁夏沿黄城市带FVC 的重要因素之一。

（4）植被覆盖度变化是气候因素和人为因素共同作用的结果， $8 1 . 4 \%$ 的区域人为因素对植被覆盖度多年变化趋势的贡献率大于 $5 0 \%$ ，有约 $2 4 \%$ 的区域气候因素对植被覆盖度多年变化趋势的贡献率大于 $5 0 \%$ ，人为因素已成为宁夏沿黄城市带植被覆盖度变化的主导因素。

总之，2002—2018年宁夏沿黄城市带植被覆盖度总体呈增大趋势，其中植被覆盖度显著增加的区域主要分布在清水河和黄河沿岸以及石嘴山和中卫市的东南部;显著减少区域主要分布在银川、吴忠和中卫市建成区及其附近，主要是由于城市建筑用地扩张引起的。

# 参考文献（References）:

[1］孙红雨,王长耀,牛铮,等.中国地表植被覆盖变化及其与气候 因子关系—一基于 NOAA 时间序列数据分析[J].遥感学报， 1998,2(3）:204-210.[Sun Hongyu,Wang Changyao,Niu Zheng, et al.Analysis of the vegetation cover change and the relationship between NDVI and environmental factors by using NOAA time series data[J].Journal of Remote Sensing,1998,2(3）:204-210.]   
[2］闫萧萧,李晶,杨震.2000—2016 年陈巴尔虎旗植被覆盖度时 空变化遥感动态监测[J].中国农业大学学报,2018,23（6)： 121-129.［Yan Xiaoxiao,Li Jing,Yang Zhen.Dynamicremote sensing monitoring on the temporal-spatial changes of vegetation coverage in Chen Barag Banner from 2OOO to 2O16[J]. Journal of China Agricultural University,2018,23(6）:121-129.]   
[3]Roerink GJ,Menenti M,Soepboer W,et al. Assessment of climate impact on vegetation dynamics by using remote sensing[J].Physics and Chemistry of the Earth,2003,28(1-3):103-109.   
[4]郭辉,黄粤,李向义,等.基于多尺度遥感数据的塔里木河干流 地区植被覆盖动态[J].中国沙漠,2016,36(5）：1472-1480. [Guo Hui,Huang Yue,Li Xiangyi,et al.Dynamic changes of fractional vegetation cover along the mainstream of the Tarim River [J].China Desert,2016,36(5）:1472-1480.]   
[5］亚库普·约麦尔,阿里木江·卡斯木.喀什市城市植被及其覆 盖度研究［J].测绘科学,2016,41（3）：109-113.［Yakupu Yuemaier,Alimujiang Kasimu. Study on urban vegetation and its coverage in Kashgar city[J]. Science of Surveying and Mapping, 2016,41(3):109 -113.]   
[6]周志强,曾源,张磊,等.南水北调中线水源区植被覆盖度遥感 监测分析［J]．国土资源遥感,2012（1）：70－76.［Zhou Zhiqiang,Zeng Yuan,Zhang Lei,et al.Remote sensing monit oring and analysis of vegetation coverage in the water source area of the middle route of projects to divert water from the south to the north [J].Remote Sensing of Land and Resources,2012(1）:70 -76.]   
[7］刘永进,乔德军,郑卫华.基于植被覆盖度序列的变化矢量分 析[J].测绘通报,2008（11）:41－43,60.[Liu Yongjin,Qiao Dejun,Zheng Weihua. Change vector analysis based on vegetation coverage sequence[J]. Bulletin of Surveying and Mapping,2008 (11) :41 -43,60.]   
[8］朱学山,江涛,魏显虎,等.基于遥感卫星的肯尼亚2000—2013 年植被覆盖度研究[J].山东科技大学学报（自然科学版), 2016,35(6）:24-29.[Zhu Xueshan,Jiang Tao,Wei Xianhu,et al. Study of vegetation coverage during 200o -2013 in Kenya based on remote sensing statellite[J]. Journal of Shandong University of Science and Technology（Natural Science Edition）,2016,35 (6) :24 -29.]   
[9］牛宝茹,刘俊蓉,王政伟.干旱半干旱地区植被覆盖度遥感信 息提取研究[J].武汉大学学报（信息科学版）,2005,30（1)： 27 -30.[Niu Baoru,Liu Junrong,Wang Zhengwei. Remote sensing information extracton based on vegetation fraction in drought and half-drought area[J]. Journal of Wuhan University（Information Science Edition）,2005,30(1）:27 -30.]   
[10]Wang X X,Jia K,Liang S L,etal.Fractional vegetation cover estimation method through dynamic bayesian network combining radiative transfer model and crop growth model[J]. IEEE Transactions on Geoscience and Remote Sensing,2016,54(12）:7442-7450.   
[11]Kuusk A,Lang M,Nilson T.Simulation of the reflectance of ground vegetation in sub-boreal forests[J].Agricultural and Forest Meteorology,2004,126(1-2) :33-46.   
[12]黄健熙,吴炳方,曾源,等.水平和垂直尺度乔、灌、草覆盖度遥 感提取研究进展[J].地球科学进展,2005,20（8）:871-881. [Huang Jianxi,Wu Bingfang,Zeng Yuan,et al. Review of tree、 shrubgrass cover of horizontal and vertical scale retrieval from remotely sensed data[J].Progress in Earth Science,2005,20（8）: 871 -881.]   
[13] Zoungrana B JB,Conrad C,Thiel M,et al. MODIS NDVI trends and fractional land cover change for improved assessments of vegetation degradation in Burkina Faso,West Africa[J].Journal of Arid Environments,2018,153:66-75.   
[14］张宏斌,杨桂霞,辛晓平,等.锡林浩特草原植被盖度变化研究 [J].中国农业资源与区划,2007,28（2）:42-46.[Zhang Hongbin,Yang Guixia,Xin Xiaoping,et al.Study on the changes in vegetation coverage of Xilinhaote grassland[J]. China Agricultural Resources and Regionalization,2007,28(2）:42 -46.]   
[15]Barati S,Rayegani B,Saati M,et al. Comparison the accuracies of different spectral indices for estimation of vegetation cover fraction in sparse vegetated areas[J].The Egyptian Journal of Remote Sensing and Space Science,2011,14(1):49 -56.   
[16] Wei X D,Wang S N,Wang Y K,et al.Spatial and temporal change of fractional vegetation cover in North-Western China from 200O to 2010[J]. Geological Journal,2018,53;427-434.   
[17］裴志林,杨勤科,王春梅,等.黄河上游植被覆盖度空间分布特 征及其影响因素[J].干旱区研究,2019,36（3）:546- 555. [Pei Zhilin,Yang Qinke,Wang Chunmei,etal.Spatial distribution of vegetation coverage and its affecting factors in the upper reaches of the Yellow River[J].Arid Zone Research,2019,36(3）:546- 555.]   
[18］陈云浩,李晓兵,陈晋,等.1983—1992 年中国陆地植被 NDVI 演变特征的变化矢量分析[J].遥感学报,2002,6（1)：12 18,81.[Chen Yunhao,Li Xiaobing,Chen Jin,et al.The change of NDVI time series based on change vector analysis in China,1983 −1992[J]. Journal of Remote Sensing,2002,6(1）:12-18,

# 81.]

[19］王光镇，王静璞,邹学勇，等.基于像元三分模型的锡林郭勒草 原光合植被和非光合植被覆盖度估算[J].生态学报，2017，37 (17）：5722-5731.［Wang Guangzhen,Wang Jingpu,Zou Xueyong,et al.Estimation of fractional cover of photosynthetic and non-photosynthetic vegetation in the Xilingol steppe region using the NDVI-DFI model[J].Acta Ecologica Sinica,2017,37（17）： 5722 -5731.]

[20］李哲，宫兆宁，刘先林,等.基于面向对象多端元混解模型的植 被覆盖度反演及其时空分布研究[J].遥感技术与应用,2018， 33(6）:1149-1158.[Li Zhe,Gong Zhaoning,Liu Xianlin,et al. Vegetation coverage retrieval and spatio-temporal distribution based on object-oriented multi-terminal mixed model[J].Remote Sensing Technology and Application,2018,33(6）:1149-1158.]   
[21]BaretF,Hagolle O,GeigerB,etal.LAI,FAPAR and fcover CYCLOPES global products derived from VEGETATION-part1:principles of the algorithm[J].Remote Sensing of Environment,2007, 110(3):275-286.   
[22]Su L H. Optimizing support vector machine learning for semi-arid vegetation mapping by using clustering analysis[J].Isprs Journal of Photogrammetry and Remote Sensing,2009,64(4） :407-413.   
[23]Goetz SJ,WrightRK,Smith AJ,et al.IKONOS imagery for resource management:Tree cover,impervious surfaces,and riparian buffer analyses in the Mid-Atlantic region[J].Remote Sensing of Environment,2003,88（1-2）:195-208.   
[24]Roujean JL.A bidirectional reflectance model of the earth's surface for the correction of remote sensing data[J].Journal of Geophysical Research,1992,97(20):455-420,468. [25］丁艳玲.植被覆盖度遥感估算及其真实性检验研究［D].长 春：中国科学院研究生院东北地理与农业生态研究所，2015. [Ding Yanling.Research on the Estimation of Fractional Vegetation Cover and the Validation of Fractional Vegetation cover Product[D].Changchun:Graduate School of Chinese Academy of Sciences Northeast Institute of Geography and Agricultural Ecology,   
2015.] [26］刘闯，葛成辉.美国对地观测系统(EOS)中分辨率成像光谱仪 （MODIS)遥感数据的特点与应用[J].遥感信息,2000(3）：45-   
48.［Liu Chuang,Ge Chenghui.Characteristics and application of modis remote sensing data in the united states earth observation system（EOS)[J].Remote Sensing Information,2000(3）:45-48.] [27］牟乐，芦奕晓，杨惠敏，等.1981—2015年中国西北牧区植被覆 盖的时空变化[J].干旱区研究,2018,35（3）：615-623.[Mou Le,Lu Yixiao,Yang Huimin,et al.Spatiotemporal variation of vegetation cover in the pastoral area in Northwestern China during the period of 1981-2015[J].Arid Zone Research,2018,35(3）:615 -623.] [28］王涛,杨梅焕.榆林地区植被指数动态变化及其对气候和人类 活动的响应[J].干旱区研究，2017，34（5）：1133－1140. [Wang Tao,Yang Meihuan.Dynamic change of NDVI and its response to climate change and human activities in Yulin,Shaanxi Province,China[J].Arid Zone Research,2017,34（5）:1133-   
1140. ]

# Spatiotemporal evolution and driving force analysis of fractional vegetation coverage over the urban belt along the Yellow River in Ningxia

WU Jia-min'， CAI Chuang-chuang²， SUN Hao²， YAO Jian-hua', CHEN Wei²， GU Ji-sheng'， JIANG Jin-bao²   
(1.The Remote Sensing SurveyingandMappingInstituteofthe Ningxia Hui Autonomous Region/Remote Sensing Centerof Ningxia, Yinchuan 750021,Ningxia,China;   
2.CollegeofGeoscienceadurveyingEngineeing,ChinaUniersityofiningadTecnology(Beijing）,Beijingoa)

Abstract:The urban belt alongthe Yellow River in Ningxia is the essence of Ningxia’s economic and social development.Itissignificantto study theenvironmental issues in theseareas.Inthis study,we investigated the spatiotemporal evolution and trend offractional vegetation coverage（FVC）based on MODIS remote sensing data from 2002 to 2O18 using the Mann-Kendallnon-parametric test,Sen's slope estimation,and landscape pattrn analysis methods.The results showed that from 2002 to 2018,FVC in $4 4 . 9 1 \%$ of the study area increased significantly,FVC in $1 . 3 1 \%$ of the area decreased,and FVC did not change in $5 3 . 7 8 \%$ of the area. There was a strong negative correlation between vegetation coverage change and temperature and a strong positive correlation between vegetation coverage change and precipitation. The contribution of $8 1 . 4 0 \%$ of regional man-made factors along the Yellow City Belt in Ningxia to the multi-year trend of FVC was greater than $50 \%$ ,and about $24 \%$ of the regional climate factors contributed more than $5 0 \%$ to the multi-year trend of FVC.

Key words:fractional vegetation cover；spatiotemporal evolution；driving force；Mann-Kendall non-parametric test；Sen's slope estimator；urban belt along the Yellow River；Ningxia