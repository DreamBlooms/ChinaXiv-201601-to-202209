# 适应SCR脱硝的回转式空气预热器传热计算模型研究

黄风良¹,孙志坚'，李鹏程¹,程攻'，顾金芳²,胡亚才(1.浙江大学热工与动力系统研究所，浙江省 杭州市 310027；2．浙江开尔新材料科技股份有限公司，浙江省 金华市 321031)

摘要：电厂烟气经SCR脱硝后，产生粘度大、腐蚀性强的硫酸氢铵，造成空预器堵塞和腐蚀，影响机组运行。针对SCR 脱硝后回转式空预器运行环境的改变，在已有传热模型研究的基础上，结合回转式空预器的结构特点，提出了一种可用于SCR 脱硝后的空预器传热计算模型。考虑 SCR 脱硝后烟气成分变化以及温度对物性的影响，可准确计算得到 SCR 脱硝后回转式空预器内部温度场，为电厂配置 SCR 脱硝装置后回转式空预器的设计和改造提供理论依据。对两分仓和SCR脱硝前后三分仓回转式空预器实例计算以及和现场实验结果比较，表明本文提出的传热计算模型适用面广、计算精度高。

关键字：回转式空气预热器；传热模型；SCR脱硝；温度场；沉积中图分类号：TK124 文献标识码：A

# The Investigation of Heat Transfer Model of Rotary Air Preheaters Adapt To SCR

# Denitrification

HUANG Fengliang', SUN Zhijian1, CHEN Ran1,LI Pengcheng', GU Jinfang², HU Yacai1 (1.InstituteofThermal Science and Power Systems,Zhejiang University, Hangzhou 310o27,Zhejiang Province,China; 2. Zhejiang Kaier New Materials Corporation,Jinhua 321031, Zhejiang Province, China)

Abstract: After SCR denitrification in thermal power plants,high viscosity and highly corrosive $\mathrm { N H _ { 3 } H S O _ { 4 } }$ would be generated which would bring blockageandcorosiontotherotaryairpreheaters.Thus wouldaffects theoperationof tepalnts.Forthechanging operationenvironmentofrotaryairpreheatersafterSCRdenitrification,thispaperraisedaheattransferodelforrotaryairpreaters adaptto SCR denitrificationat thebaseofother investigationscombined withthe structural features ofrotaryair preheaters. Consideringthechanging offlue gas compositionandtemperature impact tothephysicalpropertiesoflue gasandcalculating the concentration of $\mathrm { N H } _ { 3 }$ and $\mathrm { S O } _ { 3 }$ to determine the deposition temperature of $\mathrm { N H _ { 4 } S O _ { 4 } }$ ,the model raised in this paper could accurately caleulatethetemperaturefelds inrotaryairpreheatersafterSCRdenitrificationwhichcouldprovideateoreticalbasisforthedesign andtransformationoftherotaryairpreheatersinthermalpowerplantsafterSCRdenitrification.Accordingtotheheatransfer calculationexamplesoftri-sectorialrotaryairpreheaters tatbeforeandafterSCRdenitrificationandthecompaisonwithfeldtest results,the heat transfer model raised in this paper has high preciseness and applicability

KeyWords:rotary air preheater; heattransfer characteristics;SCRdenitrification;temperature fields;deposition

# 0.引言

2011年9月，国家环保部发布了《火电厂大气污染物排放标准》[1]，对火电厂的的烟气脱硝提出了高于欧盟现行排放限值的标准。脱硝改造成为电厂改造工作的重要环节，采用国际上火电厂烟气脱硝的主流技术选择性催化还原法(selectivecatalyticreduction，SCR)对烟气脱硝，产生的副产品 $\mathrm { S O } _ { 3 }$ 和氨化学反应生成粘性极大的硫酸氢铵。在 $1 8 0 { - } 2 3 0 ^ { \circ } \mathrm { C }$ 时硫酸氢铵会凝固在空预器的传热元件上，同时还会导致烟气中的粉尘的沉积，形成严重的堵灰和腐蚀。若不采取有效措施，短时间内，由于空预器的阻力增加过大以及换热效果骤减会导致锅炉停机[2]。因而需要对现有回转式空预器进行改造，改造的关键为更换耐腐蚀换热元件及采用合适吹灰手段[3]。

SCR脱硝后，硫酸氢铵沉积区主要在原有空预器的中、低温段，为减缓传热元件的堵灰和腐蚀，常规空预器改造多将中低温段换热元件更换为耐腐蚀和易清洗的搪瓷元件。而搪瓷元件的高度和波形选择，则主要依赖于SCR脱硝后空预器内部温度场的准确计算。同时，火电厂SCR脱硝方式都是向烟气中喷入氨水、液氨、尿素等产生氨气的物质，依靠 $\mathrm { N H } _ { 3 }$ 和烟气中的 $\mathsf { N O } _ { \mathrm { x } }$ 反应，将其还原为氮气[4。含氮物质的加入造成烟气成分的改变，因此对空预器温度场进行计算时需要考虑到烟气成分变化对物性的影响。

而目前我国对SCR脱硝后的回转式空预器的温度计算模型还没有文献可参考，已有文献[5]-[12]都是针对传统回转式空预器的温度计算。本文针对电厂SCR脱硝后回转式空预器运行环境的改变，提出了一种适用于SCR 脱硝的空预器传热计算模型。考虑了SCR脱硝后烟气成分变化以及温度对物性的影响，可准确计算得到SCR脱硝后回转式空预器内部温度场。给出了硫酸氢铵沉积温度的经验关系式，为电厂配置SCR脱硝装置后回转式空预器冷热段高度选择提供了依据。

# 1．传热计算模型

# 1.1传热数学模型

回转式空气预热器稳态运行状态下流体（烟气、二次风和一次风）和传热元件之间的能量平衡关系式8]如下。

流体：

$$
c _ { f } w _ { f } \rho _ { f } \alpha \frac { \partial t _ { f } } { \partial l } = a _ { f } h ( t _ { m } - t _ { f } )
$$

传热元件：

$$
c _ { m } m _ { m } n \frac { \hat { \sigma } t _ { m } } { \hat { \sigma } \beta } = a _ { f } h ( t _ { m } - t _ { f } )
$$

式(1)(2)中， $c _ { f }$ 和 $c _ { m }$ 分为流体和传热元件比热；$w _ { f }$ 和 $\rho _ { f }$ 分为流体的流速和密度； $\alpha$ 是单位角度β的流体的流通面积，, $\alpha _ { f }$ 是流体与传热元件间的换热系数;$h$ 和 $m _ { m }$ 分别为单位角度 $\beta ,$ 单位高度 $l$ 的换热面积和受热面质量； $n$ 为转子的角度转动速率； $t _ { f }$ 和 $t _ { m }$ 分为流体和传热元件的温度。

式(1) (2)中 $t _ { f } , \ t _ { m }$ 分别可以认为是传热元件与流体的平均温度,则对能量平衡方程(1) (2)进行离散化有：

$$
\begin{array} { l } { { c _ { f } ^ { j } w _ { f } ^ { j } \rho _ { f } ^ { j } \alpha ( t _ { f o } ^ { j } - t _ { f i } ^ { j } ) = \alpha _ { f } ^ { j } h \Delta l ( \displaystyle \frac { t _ { m i } ^ { i } + t _ { m o } ^ { i } } { 2 } - \displaystyle \frac { t _ { f i } ^ { j } + t _ { f o } ^ { j } } { 2 } ) } } \\ { { c _ { m } ^ { i } m _ { m } ^ { i } n ( t _ { m o } ^ { i } - t _ { m i } ^ { i } ) = \alpha _ { f } ^ { j } h \Delta \beta ( \displaystyle \frac { t _ { m i } ^ { i } + t _ { m o } ^ { i } } { 2 } - \displaystyle \frac { t _ { f i } ^ { j } + t _ { f o } ^ { j } } { 2 } ) } } \end{array}
$$

令：

$$
\mathrm { A } = \frac { \alpha _ { f } ^ { j } h \Delta l } { c _ { f } ^ { j } w _ { f } ^ { j } \rho _ { f } ^ { j } \alpha }
$$

$$
\mathbf { B } = { \frac { \alpha _ { f } ^ { j } h \Delta \beta } { c _ { m } ^ { i } m _ { m } ^ { i } n } }
$$

由(3)-(6)两式可得：

$$
t _ { m o } ^ { i } = \frac { 2 \mathbf { B } t _ { f i } ^ { j } + ( \mathbf { A } + 2 - \mathbf { B } ) t _ { m i } ^ { i } } { \mathbf { A } + \mathbf { B } + 2 }
$$

$$
t _ { f o } ^ { j } = \frac { ( \mathrm { B } + 2 - \mathrm { A } ) t _ { f i } ^ { j } + 2 \mathrm { A } t _ { m i } ^ { i } } { \mathrm { A } + \mathrm { B } + 2 }
$$

式(5)(6)中， $w _ { f } ^ { j } \rho _ { f } ^ { j } \alpha$ 为单位角度 $\beta |$ 内参与换热的流体质量流量，用 $\boldsymbol { q } _ { \ : f } ^ { \ : j }$ 表示，单位 $\mathrm { k g / s }$ ；将随转子不断转动而参与换热的传热元件看\`成流体， $m _ { m } ^ { i } n$ 为单位角度 $\beta ,$ 单位高度 $l$ 内参与换热的传热元件的质量流量，用 $\boldsymbol { q } _ { \ m } ^ { \ i }$ 表示单位 $\mathrm { k g / s }$ 。

# 1.2模型求解

流体与传热元件受热面间的换热系数 $\boldsymbol { \alpha } _ { f } ^ { j }$ 、流体比热 $c _ { f } ^ { j }$ 以及传热元件比热 $c _ { m } ^ { i }$ 都是温度的函数(流体流速 $\boldsymbol { w } _ { f } ^ { j }$ 和流体密度 $\rho _ { f } ^ { j }$ 和温度有关，但是两者的乘积与温度无关)。但对于回转式空预器内的微元体，因流体温度以及传热元件温度变化很小，故上述离散化模型可以适用。沿空预器轴向和周向进行网格划分，每一个网格即可作为一个微元体单元进行求解，进而求得稳态下回转式空预器内部的温度场。如图1所示，计算网格划分把烟气、空气连接在一起。

本文根据文献[13][15]依次确定烟气和空气的物性参数（比热、黏度等）、传热元件物性参数、流体与传热元件的换热系数随温度和流体流速等因素变化的关联式。而网格内流体与传热元件的物性由进出□温度算术平均温度确定。

根据回转式空气预热器微元体的稳态传热模型，当给定入口流体和传热元件的温度、流量以及网格尺寸以后，网格出口的温度便确定下来。

求解过程为，先假设烟气侧最左端传热元件温度，按照模型计算得到各流体出口温度以及一次风侧最右端传热元件温度，根据空预器的结构工作原理，此时传热元件应该从一次风侧转入烟气侧，即烟气侧最左端传热元件温度应该等于一次风侧最右端传热元件温度。

所以迭代关系式就是，将计算得到的一次风侧最右端的传热元件温度重复赋值给烟气侧最左端的传热元件，直到烟气侧最左端传热元件温度与一次风侧最右端传热元件温度差值的绝对值小于终止判据。

本模型与文献[8中提出的解析模型相比，省掉了直接解析求解过程中的拉普拉斯与反拉普拉斯变换，结合空预器结构工作原理，巧妙地简化了计算过程。与文献[11相比，本模型采用网格划分省掉了其中的复化差分方法，在不影响计算精度的前提下，简化了计算模型，

![](images/d9310eaa6ed214837af927ebc8e246a0cd90c66adce7745d927ef1724196111b.jpg)  
Fig.1The division of computing grid cell

针对SCR脱硝后空预器多层结构改造计算，只需将各层波纹板的换热系数随温度和流体流速等因素变化的关联式带入计算模型即可。

# 2．SCR脱硝后烟气成分变化

在催化剂作用下， $\mathrm { N H } _ { 3 }$ 选择性催化还原烟气中的$\mathsf { N O } _ { \mathrm { x } }$ 的反应如下：

$$
4 \mathrm { N H } _ { 3 } + 4 \mathrm { N O } + \mathrm { O } _ { 2 }  4 \mathrm { N } _ { 2 } + 6 \mathrm { H } _ { 2 } \mathrm { O }
$$

$$
4 \mathrm { N H } _ { 3 } + 2 \mathrm { N O } _ { 2 } + \mathrm { O } _ { 2 }  3 \mathrm { N } _ { 2 } + 6 \mathrm { H } _ { 2 } \mathrm { O }
$$

$$
4 \mathrm { N H } _ { 3 } + 6 \mathrm { N O }  5 \mathrm { N } _ { 2 } + 6 \mathrm { H } _ { 2 } \mathrm { O }
$$

$$
8 \mathrm { N H } _ { 3 } + 6 \mathrm { N O } _ { 2 } \to 7 \mathrm { N } _ { 2 } + 1 2 \mathrm { H } _ { 2 } \mathrm { O }
$$

以上反应仅是总的反应式，而真正的化学反应是通过中间产物来进行的[16]，在典型的SCR反应条件（ $\mathrm { \Delta N H _ { 3 } / N O }$ 物质的量之比 $\geqslant 1$ ， $\mathrm { O } _ { 2 }$ 体积分数 $52 \%$ ，反应温度 ${ < } 4 0 0 ^ { \circ } \mathrm { C }$ ）下，反应（9）是最主要的，这是因为烟气中 $90 \% - 9 5 \%$ 的 $\mathrm { N O } _ { \mathrm { x } }$ 是以NO形式存在的。

由此可知，经过SCR 脱硝装置后，烟气中的 $\mathsf { N O } _ { \mathrm { x } }$ 转化成 $\Nu _ { 2 }$ ，对空预器进行传热计算时，需注意此处烟气成分的变化。

此外，由于 $\mathrm { S O } _ { 2 }$ 的氧化，烟气中 $\mathrm { S O } _ { 3 }$ 的浓度大大增加，特别是对于燃烧高硫煤的电厂来说，这一问题更为突出。通常，烟气经过SCR后， $\mathrm { S O } _ { 3 }$ 的浓度会增加近一倍[17]。

本文对SCR脱硝后回转式空预器换热计算时，根据实际煤种以及空气过量系数计算得到烟气成份，同时根据烟气流经脱硝系统后成份变化作为计算数据带入到计算程序中计算，即可得到回转式换热器内部温度场。

# 3.硫酸氢铵沉积温度的确定

根据回转式空预器结构尺寸以及烟气成分可精确计算其内部温度场，现有电厂改造项目中通常冷热段交界处温度要比硫酸氢铵沉积温度高 $1 0 ^ { \circ } \mathrm { C }$ 以上。为校核冷热段传热元件的高度选择是否合适，确定硫酸氢铵的沉积温度至关重要。

$\mathrm { N H _ { 4 } H S O _ { 4 } }$ 形成受烟气中 $\mathrm { S O } _ { 3 }$ 和 $\mathrm { N H } _ { 3 }$ 的浓度、机组运行负荷等多种因素的影响。但其沉积温度主要受空预器内部 $\mathrm { S O } _ { 3 }$ 和 $\mathrm { N H } _ { 3 }$ 的浓度沉积影响[18]。

![](images/c8b7d1d27a85a711a75e6d0897fdfdbee3a07ce444479f61412ae55228e8c1d3.jpg)  
图1计算网格单元划分  
图 $2 \mathrm { N H } _ { 3 }$ 和 $\mathrm { S O } _ { 3 }$ 浓度乘积对硫酸氢铵沉积的影响 Fig.2 The concentration of $\mathbf { N H } _ { 3 }$ and $\mathbf { S O } _ { 3 }$ influence on the

# deposition temperature of $\mathbf { N H _ { 4 } H S O _ { 4 } }$

硫酸氢铵的沉积温度是 $\mathrm { N H } _ { 3 }$ 和 $\mathrm { S O } _ { 3 }$ 浓度乘积的函数，它们之间的关系如图2所示。经验计算关系式为：

$$
1 1 . 4 5 \log ( { n _ { _ { N H _ { 3 } } } } ^ { * } { n _ { _ { S O _ { 3 } } } } ) + 1 9 2 . 2 9
$$

由图2可见，随着 $\mathrm { N H } _ { 3 }$ 和 $\mathrm { S O } _ { 3 }$ 浓度乘积的降低，硫酸氢铵的沉积温度降低。空预器内 $\mathrm { N H } _ { 3 }$ 浓度主要由SCR脱硝装置内氨气逃逸率决定，通常电厂SCR脱硝装置都能保证氨气逃逸率小于 $3 \mathrm { m g / L }$ ，因此为确定硫酸氢铵沉积温度需确定 $\mathrm { S O } _ { 3 }$ 浓度。烟气中 $\mathrm { S O } _ { 3 }$ 的浓度主要由燃煤含硫量决定，同时烟气中的 $\mathrm { S O } _ { 2 }$ 在SCR装置内由于催化剂的作用会有一部分转化为$\mathrm { S O } _ { 3 }$ ，但其受具体SCR装置内催化剂种类以及反应温度影响较大，故实际计算时只能将 $\mathrm { S O } _ { 3 }$ 浓度定为一个范围，以确定硫酸氢铵沉积温度。

# 4．计算实例及分析

# 4.1三分仓预热器计算及分析

由于《标准》[1]的实施，浙江某600MW燃煤电厂进行了SCR 脱硝改造，与之配备的三分仓回转式空气预热器（2-32VI(T)-2080SMRC型）也进行了相应的结构改造。空预器去掉了原有的中温段传热元件，增大冷段高度并且采用耐腐蚀的搪瓷传热元件。

# 表1空预器改造前后结构参数比较

Tab.1 Comparison of the structural parameters   

<html><body><table><tr><td>空预器 结构</td><td>项目</td><td>传热元</td><td>传热元件</td></tr><tr><td rowspan="2">改造前</td><td>高温段</td><td>DU3</td><td>1.000</td></tr><tr><td>中温段</td><td>DU3</td><td>0.775</td></tr><tr><td></td><td>低温段</td><td>DU3</td><td>0.305</td></tr><tr><td rowspan="2">改造后</td><td>高温段</td><td>DU3</td><td>1.150</td></tr><tr><td>低温段</td><td>Ke-1</td><td>1.000</td></tr></table></body></html>

本文分别以脱硝改造前后该三分仓回转式空预器结构参数以及设计工况锅炉最大连续蒸发量(Boilermaximumcontinuerate，BMCR)、汽机额定负载工况(turbine rated load,BRL)和 $7 5 \% \mathrm { B R L }$ 下烟气和空气的进口参数和漏风系数作为计算原始数据，利用本文提出的计算模型进行校核。计算结果如表2、表3所示，表中设计值为综合锅炉热力计算给出的结果，计算值为用本文模型计算得到的结果。

由表2可以看出对改造前回转式空预器，本文计算值与设计值最大偏差为BMCR工况下一次风出□温度，但偏差值小于 $1 \%$ 。

由表3可以看出，对改造后空预器，本文计算值与设计值最大偏差小于 $1 \%$ 。说明本文计算方法对脱硝后三分仓回转式空预器传热计算的精确性。同时本文计算方法一次计算即可以得到空预器内部流体（烟气、一二次风）以及传热元件的温度分布。

图3为SCR脱硝后空预器设计工况BMCR下，沿圆周方向传热元件的温度分布。其中hout为热段出口处传热元件温度，即空预器上端面；mid为改造后空预器冷热段交界处传热元件温度；cout为冷段出口处传热元件温度，也即空预器下端面。

![](images/906db8aaa40d5fb34c51c60a7e0b9eafbb7ab165e8e7353200574aad8e29c3be.jpg)

Before and after the transformation of the rotary air preheater   
图3设计工况BMCR下圆周方向传热元件温度分布 Fig.3Temperature variationof the heat transfercomponents in the circumferential direction under design conditions BMCR 表2改造前三分仓空气预热器计算结果比较 Tab.2 Comparison of the calculated results of the tri-sectorial rotaryairpreheaterbefore transformation   
表3改造后三分仓空气预热器计算结果比较  
Tab.3 Comparison of the calculated results of the tri-sectorial   

<html><body><table><tr><td>设计工 况</td><td>温度/℃</td><td>设计 值 值</td><td>计算</td><td>偏差/%</td></tr><tr><td>BMCR</td><td>出口烟气 出口二次风 出口一次风</td><td>133 341 324</td><td>132.59 342.06 326.88</td><td>0.310 0.310 0.881</td></tr><tr><td>BRL</td><td>出口烟气 出口二次风 出口一次风</td><td>132 337 322</td><td>131.55 338.37 324.14</td><td>0.342 0.405 0.660</td></tr><tr><td>75%BRL</td><td>出口烟气 出口二次风 出口一次风</td><td>118 307 297</td><td>117.57 306.13 296.20</td><td>0.366 0.284 0.270</td></tr></table></body></html>

rotaryairpreheater after transformation   

<html><body><table><tr><td>设计工况</td><td>温度/℃</td><td>设计值</td><td>计算值</td><td>偏差/%</td></tr><tr><td rowspan="3">BMCR</td><td>出口烟气</td><td>135</td><td>135.86</td><td>0.634</td></tr><tr><td>出口二次风</td><td>339</td><td>339.99</td><td>0.291</td></tr><tr><td>出口一次风</td><td>323</td><td>324.96</td><td>0.603</td></tr><tr><td rowspan="3">BRL</td><td>出口烟气</td><td>136</td><td>135.14</td><td>0.636</td></tr><tr><td>出口二次风</td><td>337</td><td>336.44</td><td>0.166</td></tr><tr><td>出口一次风</td><td>322</td><td>322.46</td><td>0.142</td></tr><tr><td rowspan="3">75%BRL</td><td>出口烟气</td><td>121</td><td>121.15</td><td>0.123</td></tr><tr><td>出口二次风</td><td>307</td><td>304.17</td><td>0.930</td></tr><tr><td>出口一次风</td><td>297</td><td>294.41</td><td>0.880</td></tr></table></body></html>

由图3可以看到沿着圆周方向，在 $0 { \sim } 1 6 0 ^ { \circ }$ 传热元件温度逐渐升高；在 $1 8 0 { \sim } 2 9 0 ^ { \circ }$ ，传热元件温度逐渐降低；在 $3 1 0 { \sim } 3 4 0 ^ { \circ }$ ，传热元件温度继续降低但下降趋势变缓。这是与三分仓回转式空预器的结构一致的。此煤种产生烟气经SCR脱硝装置后 $\mathrm { S O } _ { 3 }$ 浓度为 $1 . 5 8 { - } 2 . 3 7 \mu \mathrm { L / L }$ ， $\mathrm { N H } _ { 3 }$ 浓度为3uL/L，由图2知此范围内 $\mathrm { N H _ { 4 } H S O _ { 4 } }$ 沉积温度为 $1 9 0 { \sim } 2 0 0 ^ { \circ }$ 由图3知热段传热元件最低温度在 $2 1 0 ^ { \circ } \mathrm { C }$ ，即热段波纹板温度高于 $\mathrm { N H _ { 4 } H S O _ { 4 } }$ 沉积温度。结构改造后,冷段采用搪瓷波纹板，缓解了冷段的低温腐蚀，该电厂SCR脱硝后回转式空预器的正常运行验证了传热设计计算的合理性。

对SCR脱硝后空预器的设计和改造，重点为确定传热元件的高度和波形。由上例改造后空预器温度场计算可知，本文传热模型可精确得到空预器内部硫酸氢铵沉积区最低温度，为传热元件的高度和波形选择提供理论依据。

# 4.2现场实验与计算值比较

为对SCR脱硝后此电厂空预器运行效果进行检验，本文作者对该电厂进行了现场测试。

本文作者在该电厂设计工况BMCR下，采用同步测试方法，测试了回转式空预器进出口烟气温度和一、二次风温度。并根据电厂提供的实时烟气流量、二次风流量、一次风流量以及漏风系数，应用本文模型进行了计算。计算结果如表4所示。

# 表4现场实验与计算值比较

Tab.4 Comparison of the calculated results withthefieldtest   

<html><body><table><tr><td>温度/℃</td><td>实验值</td><td>计算值</td><td>偏差/%</td></tr><tr><td>出口烟气</td><td>115.1</td><td>118.67</td><td>3.008</td></tr><tr><td>出口二次风</td><td>309.9</td><td>311.64</td><td>0.558</td></tr><tr><td>出口一次风</td><td>287.2</td><td>293.37</td><td>2.103</td></tr></table></body></html>

电厂锅炉运行过程中，工况很难长期稳定运行，相应的空预器也会不断做出调节。但由表4数据可

知，本文计算方法得出的结果与实验值非常接近，说明了本文计算方法对SCR脱硝后空气预热器温度计算的准确性。

# 5．结论

电厂经SCR脱硝后，产生粘度大、腐蚀性强的硫酸氢铵，造成空预器堵塞和腐蚀，影响机组运行。

1)针对SCR脱硝后回转式空预器运行环境的改变，在已有传热研究的基础上，结合回转式空预器的结构特点，提出了一种适用于SCR脱硝后的空预器传热计算模型。

2)考虑SCR脱硝后烟气成分变化以及温度对物性的影响，除了可以准确得到出口处各流体的温度外，还能够准确得到回转式空预器内部流体（烟气、二次风以及一次风）和传热元件的温度场。此为电厂配置SCR脱硝装置后回转式空预器的改造提供理论指导，可准确而快速的为改造后传热元件高度、传热元件波形、转子转速等选择提供理论依据。

3）给出了 $\mathrm { N H _ { 4 } H S O _ { 4 } }$ 沉积温度与空预器内烟气中 $\mathrm { S O } _ { 3 }$ 和 $\mathrm { N H } _ { 3 }$ 的浓度沉积的经验计算关系式，为空预器改造后传热元件的高确定提供参考。

4)对SCR脱硝前后三分仓回转式空预器实例计算以及和现场实验比较，表明本文提出的传热计算模型适用面广、计算精度高。

# 参考文献

[1]．GB13223-2011．火电厂大气污染物排放标准[S]. GB 13223-2011.Emission standard of air pollutants for thermal power plants [S].   
[2]．蔡明坤，装有脱硝系统锅炉用回转式预热器设计存在问 题和对策[J]．锅炉技术,2005,36(4)：8-12. Cai Mingkun,The problem and solution in air preheater design for boilers with De-NOx equipments[J]. Boiler technology, 2005,36(4):8-12.   
[3]．钟礼金,宋玉宝．锅炉 SCR 烟气脱硝空气预热器堵塞原 因及其解决措施[J]．热力发电,2012,41(8):45-50. Zhong lijing, Song Yubao.Air preheater blocking in boiler with SCR denitrfication device: Reason analysisand solutions[J]. Thermal Power Generation,2012,41(8):45-50.   
[4]．沈伯雄,刘亭,韩永富．选择性非催化还原脱除氮氧化物 的影响因素分析[J]中国电机工程学 报,2008,28(23):53-59. Shen Boxiong,Liu Ting,Han Yongfu. Analysis on impact factors for removal of NOx with selective non-catalytic reduction[J].Proceedings of the CSEE,2008,28(23):53-59.   
[5]．锅炉机组热力计算标准方法[M]．北京锅炉厂译,机械工 业出版社,1976.   
[6]．胡华进,徐治皋．三分仓空气预热器传热特性的算法研 究[J]．动力工程,1998,18(1):54-57. Hu Huajin, Xu Zhigao. Research on the calculation of the heat transfer of tri-sectorial regenerative air preheater[J]. Power Engineering,1998,18(1): 54-57.   
[7]．周俊虎,杨伟娟，靳彦涛，周志军,曹欣玉,岑可法．三分 仓空气预热器热力计算的研究[J]．动力工 程,2003,23(6):2810-2813. Zhou Junhu, Yang Weijuan, Jin Yantao et al. Research on the heat balance calculation of the tri-sectionalregenerativeairpreheater[J].Power Engineering,2003,23(6):2810-2813.   
[8]．冷伟,陈道伦,张志伦．基于解析方法的回转式空气预热 器换热计算[J]．中国电机工程学报,2005,25(3):141-146. Leng Wei, Chen Daolun, Zhang Zhilun. Heat exchange calculation of a regenerative air heater with analytical method[J],2005,25(3):141-146   
[9]．冷伟,王渡．一种改进的回转式空气预热器热力计算方 法[J].动力工程,2005,25(3):392-395. Leng Wei， Wang Du. An improved way for thermal calculationofrotaryairpreheaters[J].Power Engineering,2005,25(3):392-395   
[10].冷伟,陈曦,于翔,王渡．回转式空气预热器非稳定换热的 分析[J]．动力工程,2006,26(3):412-416. Leng Wei, Cheng Xi, Yu Xiang, Wang Du. Analysis of unsteady heat exchange of rotary air preheaters[J]. Power Engineering,2006,26(3):412-416.   
[11].王洪跃,毕小龙,司风琪,徐治皋．求解回转式空气预热器 传热模型的解析一数值法[J]．中国电机工程学 报,2006,26(11):51-55. Wang Hongyue,Bi xiaolong， Si Fengqi， Xu Zhigao. Analytical-numerical method based on the model of heat transfer in rotary regenerator[J]. Proceedings of te CSEE, 2006,26(11):51-55.   
[12].王洪跃,毕小龙,王雷,司风琪,徐治皋．回转式空气预热器 传热模型动态仿真[J]．锅炉技术,2006,37(2):31-34. Wang Hongyue，Bi xiaolong， Si Fengqi,Xu Zhigao. Dynamic simulation for the heat transfer model of thermal rotary air-preheater [] Boiler technology, 2006,37(2):31-34.   
[13].洪荣华,吴杰,屠传经．烟气物性的直接计算方法．第五 届全国热管会议论文集,1996(9). Hong Ronghua, Wu Jie, Tu Chuanjing. The direct calculation method of gasproperties.Fifth National Conference Proceedings of heat pipe,1996(9).   
[14].张启．回转式空预器温度场数值计算及漏风研究[D]. 上海：上海交通大学,2009. Zhang Qi. The numerical calculation of rotary air preheater temperature field and research of leakage[D]. shang hai: Shang hai Jiao tong university,2009.   
[15].林宗虎,徐同模．实用锅炉手册[M]．化工工业出版 社,1999. Lin Zenghu,Xu Tongmo.Handbook of utility boiler [M]. Chemical Industry Press,1999.   
[16].Prins W L,Nuninga Z L. Design and experience with catalytic forSCR-DENOx[J].Catalysis Today, 1993,16(7):187-205.   
[17].鲁佳易，卢啸风,刘汉周，陈继辉．SCR 法烟气脱硝催化 剂及其应用特性的探讨[J].电站系统工程，2008，24(1): $5 { \sim } 8$ Lu Jiayi,Lu Xiaofeng,Liu Hanzhou,Chen Jihui. The recent application of De-NOx SCR catalysts[J].Power System Engineering,2008,24(1): $5 { \sim } 8$ ：   
[18].Fossil Energy Research Corporation.In Situ Device for Real-Time Catalyst Deactivation Meas urements[R]. Final Technical Report: DOE Project 422FC2G05NT4229898, Laguna Hills, Calif ornia,May 2007.