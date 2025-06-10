# 内燃机排气余热回收梯级分段温差电单偶模拟分析

贾琦，舒歌群，田华，卫海桥，梁兴雨，孙秀秀（天津大学内燃机燃烧学国家重点实验室，天津，300072）摘要：本文选取了 ${ \bf B i } _ { 2 } \mathrm { T e } _ { 3 }$ 和 $\mathrm { C o S b } _ { 3 }$ 两种温差电材料设计了一种梯级分段温差电单偶，并对其建立了数学模型，导出温差电单偶的功率和效率计算公式，分析冷热端陶瓷片表面温度、温差电单偶长度以及表面对流传热系数对分段温差电单偶性能的影响。分析结果表明提高热面温度、降低冷面温度和提高热表面对流传热系数均可以提高分段温差电单偶的最大输出功率和最大转换效率。缩短温差电单偶的长度可以增大最大输出功率，但会导致最大转换效率的明显下降。

关键词：内燃机；排气；余热利用；温差发电中图分类号：TK402 文献标志码：A

# Simulation and Analysis of Segmented Thermoelectric Unicouple Used for Waste Heat Recovery of Internal Combustion Engine

JIA Qi SHU Ge-Qun Tian Hua Wei Hai-Qiao Liang Xing-Yu Sun Xiu-> (State Key Laboratory of Engines, Tianjin University, Tianjin 3oo072, China)

Abstract: In this paper, a segmented thermoelectric unicouple is designed using two kinds of thermoelectric materials-- ${ \bf \cdot B i } _ { 2 } \mathrm { T e } _ { 3 }$ and $\mathrm { C o S b } _ { 3 }$ . The mathematical model of the unicouple is established.Based on the mathematical model,calculation formula of the output power and conversion eficiencyare derived. And the thesis analyzes the influence of surface temperature ofhot and cold side ceramics,thickness of unicouple and convection heat transfer coefficient of hot surface on the performance of segmented thermoelectric unicouple.The results show that increase hot surface temperature,reduce cold surface temperature and increase the convection heat transfer coefficient can improve the maximum output power and conversion eficiency of the thermoelectric unicouple. Cutting down the thickness of unicouple can increase the maximum output power, but it will result in the reducing of maximum conversion efficiency.

Key Word: internal combustion engine; exhaust; waste heat recovery; thermoelectric generator

# 0前言

内燃机输出的有效功率一般只占燃油燃烧总热量的 $3 0 \% - 4 5 \%$ （柴油机）或 $20 \% - 3 0 \%$ （汽油机），而其余大部分的能量都通过冷却水和排气散失掉了，造成能量的严重浪费[1]。温差发电是一种绿色环保技术，具有性能稳定、无噪音、体积小、使用寿命长等优点。内燃机余热源的分析结果显示，由于排气温度较高，与环境温度间存在很大的温差，在排气系统使用温差发电技术回收热量的潜力很大[2]。

目前限制温差发电广泛应用的主要原因是相对较低的热电转换效率。温差发电器的效率主要取决于温差电材料的优值系数，冷热端的温度以及温差电单偶的长度和截面积。温差电材料的优值系数$Z T { = } a ^ { 2 } { \sigma } T / K$ ，其中 $\smash { a , \sigma , k }$ 分别为材料的塞贝克系数、电导率、热导率[3]。材料的优值系数越大，在相同的温差下，热电转换效率也就相对越高。一般来说，任意一种温差电材料只会在一定的温度范围内取得较高的优值系数，严重影响了温差发电在内燃机排气余热这种大温差余热回收条件下的转换效率。

采用分段结构，将适用于不同温度的热电材料沿温度梯度串联，使单偶中每段材料均在最佳的温度内工作，可以提高温差发电器在大温差条件下的转换效率[4]。因此，为满足对内燃机排气余热的回收，本文设计了一种分段温差电单偶，高温侧选用 $\mathrm { C o S b } _ { 3 }$ 基温差电材料，低温侧选用 ${ \bf B i } _ { 2 } \mathrm { T e } _ { 3 }$ 基温差电材料，并对其进行模拟分析，计算不同热面温度、冷面温度、温差电单偶长度以及热表面对流传热系数对其性能的影响。

# 1 计算模型

如图1为温差电单偶发电示意图，每个温差电单偶主要由 $\mathrm { ~ \bf ~ P ~ }$ 型和 $\mathrm { ~  ~ N ~ }$ 型电偶臂，以及冷热两端用于导热绝缘的陶瓷片组成。本文设计的温差电单偶所选取的P型高温材料为 $\mathrm { B a _ { 0 . 3 } I n _ { 0 . 3 } F e C o _ { 3 } S b _ { 1 2 } } .$ 、低温侧为 $\mathrm { B i } _ { 0 . 4 8 } \mathrm { S b } _ { 1 . 5 2 } \mathrm { T e } _ { 3 }$ ; $\mathrm { ~  ~ N ~ }$ 型高温材料为 $\mathrm { B a _ { 0 . 4 } I n _ { 0 . 4 } C o _ { 4 } S b _ { 1 2 } } .$ 低温侧为 $\mathrm { B i } _ { 2 } \mathrm { T e } _ { 2 . 7 } \mathrm { S e } _ { 0 . 3 }$ ，材料物性参数参考文献。P、N型电偶臂高温和低温材料的长度比例 $\delta _ { 1 } { : } \delta _ { 2 }$ 为1:1。假定热量只沿着电偶臂方向传递，忽略电偶臂和环境的传热损失，忽略接触热阻和接触电阻。温差电单偶的上下两面分别是热源和冷源，在冷热源的共同作用下，热端陶瓷片上端面温度（以下简称热面温度）为 $T _ { h s }$ ，冷端陶瓷片下端面温度（以下简称冷面温度）为 $T _ { c s }$ ，电偶臂两端的温度分别为 $T _ { h }$ 和 $T _ { c }$ 。

![](images/d5abf2e12737e04daad0f17318ce465a01a86c6c26073ec9ce323c8967433301.jpg)  
图1分段温差电单偶发电示意图

图2为 $\mathrm { ~ \bf ~ P ~ }$ 型电偶臂两材料分界面温度的计算流程，首先初设分界面温度 $\mathrm { T _ { J P } }$ ，计算得到 $\int _ { T _ { J P } } ^ { T _ { h } } \lambda _ { P 1 } \big ( T \big ) \mathrm { d } T$ 和 $\int _ { T _ { c } } ^ { T _ { / P } } \lambda _ { P 2 } ( T ) \mathrm { d } T$ ，其中 $\lambda _ { \scriptscriptstyle P 1 } \left( T \right)$ 和 $\lambda _ { \mathit { P } 2 } \left( T \right)$ 分别为高温和低温材料的导热系数随温度变化的函数。在稳态过程中，高温和低温材料垂直于电偶臂方向的截面上导热量相等，故截面上的导热量 $\scriptstyle Q _ { P }$ 为

$$
\theta _ { P } \ = \ \frac { \displaystyle \int _ { T _ { _ { J P } } } ^ { T _ { h } } \lambda _ { P 1 } \big ( T \big ) \mathrm { d } T } { \delta _ { 1 } } = \frac { \displaystyle \int _ { T _ { c } } ^ { T _ { _ { J P } } } \lambda _ { P 2 } \big ( T \big ) \mathrm { d } T } { \delta _ { 2 } }
$$

![](images/a6bb51e880c79e29871fdb699ddcbe986f4d5014d2ee815fc318be48c25ba634.jpg)  
Fig.1Schematic diagram of segmented thermoelectric unicouple   
图2两材料分界面温度计算流程图  
Fig.2Calculation flowchart of interface temperature between two materials

因此，若 $\frac { \int _ { T _ { \jmath P } } ^ { T _ { b } } \lambda _ { P 1 } \big ( T \big ) \mathrm { d } T } { \int _ { T _ { c } } ^ { T _ { \jmath P } } \lambda _ { P 2 } \big ( T \big ) \mathrm { d } T } = \frac { \delta _ { 1 } } { \delta _ { 2 } }$ ，则Tjp的取值正确，否则调整 $T _ { J P }$ 的取值重新计算，直到得到正确的分界面温度。同理可求得 $\mathrm { \Delta N }$ 型电偶臂分界面温度 $T _ { J N \circ }$ P、 $\mathrm { \Delta N }$ 电偶臂的平均塞贝克系数 $\scriptstyle a _ { P }$ 和 $a _ { N }$ 分别为

$$
\alpha _ { P } \ = \frac { \displaystyle \int _ { T _ { s p } } ^ { T _ { h } } \alpha _ { P 1 } ( T ) \mathrm { d } T + \displaystyle \int _ { T _ { c } } ^ { T _ { s p } } \alpha _ { P 2 } ( T ) \mathrm { d } T } { T _ { h } \ - \ T _ { c } }
$$

$$
\alpha _ { _ N } \ = \ \frac { \displaystyle \int _ { T _ { _ M } } ^ { T _ { _ b } } \alpha _ { _ { \scriptscriptstyle N 1 } } ( T ) \mathrm { d } T + \displaystyle \int _ { T _ { c } } ^ { T _ { _ { J P } } } \alpha _ { _ { \scriptscriptstyle N 2 } } ( T ) \mathrm { d } T } { T _ { _ h } \ - \ T _ { c } }
$$

其中 ${ \alpha _ { P I } ( T ) } \cdot \ \alpha _ { P 2 } ( T ) \cdot \ \alpha _ { N I } ( T ) \cdot \ \alpha _ { N 2 } ( T ) \nonumber$ 分别为P、N型高低温材料的塞贝克系数随温度变化的函数。

$\mathrm { ~ \bf ~ P ~ }$ 型和 $\mathrm { ~  ~ N ~ }$ 型电偶臂的总内阻 $R _ { P } , \ R _ { N }$ 分别为

$$
R _ { P } \ = \frac { \displaystyle \int _ { 0 } ^ { \delta _ { 1 } } \rho _ { P 1 } ( L ) \mathrm { d } L + \displaystyle \int _ { 0 } ^ { \delta _ { 2 } } \rho _ { P 2 } ( L ) \mathrm { d } L } { A }
$$

$$
R _ { \scriptscriptstyle { N } } = { \frac { \displaystyle \int _ { 0 } ^ { \delta _ { 1 } } \rho _ { { \scriptscriptstyle { N 1 } } } ( L ) \mathrm { d } L + \displaystyle \int _ { 0 } ^ { \delta _ { 2 } } \rho _ { { \scriptscriptstyle { N 2 } } } ( L ) \mathrm { d } L } { \cal A } }
$$

其中 $\rho _ { P I } ( L ) \cdot \rho _ { P 2 } ( L ) \cdot \rho _ { N I } ( L ) \cdot \rho _ { N 2 } ( L ) ^ { \prime }$ 分别为 $\mathrm { ~ \bf ~ P ~ }$ 、N型高低温材料的电阻率沿电偶臂方向变化的函数， $A$ 为电偶臂的横截面积。

则温差电单偶的内阻 $R _ { i n }$ 为

# $_ \mathrm { R i n = R P + R N }$

温差电单偶产生的开路电压 $U$ 为

$$
U = \alpha { \left( T _ { _ { h } } - T _ { _ { c } } \right) }
$$

其中 $\alpha$ 为总塞贝克系数，由 $\scriptstyle { a = a _ { P } - a _ { N } }$ 计算得到。

单偶两端连接一负载 $R _ { L }$ ，则电路中电流 $I _ { 0 }$ 为

$$
{ { I } _ { 0 } } \ = \ { \frac { U } { { { R } _ { i n } } \ + \ { { R } _ { L } } } } \ = \ { \frac { \alpha { { \left( { { T } _ { h } } \ - \ { { T } _ { c } } \right) } } } { { { R } _ { i n } } \ + \ { { R } _ { L } } } }
$$

由于陶瓷片两端存在温差，冷热端两块陶瓷片在工作中传递的热量 $Q _ { h }$ 和 $\textstyle { \mathcal { Q } } _ { c }$ 分别为

$$
Q _ { _ h } \ = \ \big ( T _ { _ { h s } } \ - \ T _ { _ h } \big ) K _ { _ h }
$$

$$
Q _ { c } \ = \Big ( T _ { c } \ - \ T _ { c s } \Big ) K _ { c }
$$

其中

$$
K _ { _ h } \ = \ { \frac { \lambda _ { h } A _ { h } } { I _ { h } } }
$$

$$
K _ { c } \ = \frac { { \lambda } _ { c } A _ { c } } { I _ { c } }
$$

$K _ { h }$ 和 $K _ { c }$ 分别为热端和冷端陶瓷片的热导， $\lambda _ { h }$ ，$A _ { h }$ 、 $l _ { h }$ 和 $\lambda _ { c }$ 、 $\textstyle A _ { c }$ 、 $l _ { c }$ 分别为热端和冷端陶瓷片的导热系数、横截面积和长度。

根据珀尔贴定律，当电路中电流为 $I _ { 0 }$ 时，单偶 热端吸收和冷端释放的珀尔贴热 $Q _ { I }$ 、 $Q _ { 2 }$ 分别为

$$
Q _ { 1 } \ = \alpha I _ { 0 } T _ { h }
$$

$$
Q _ { \mathrm { 2 } } \ = \alpha I _ { \mathrm { 0 } } T _ { c }
$$

根据焦耳效应，当电路中电流为 $I _ { 0 }$ 时，温差电单偶产生的焦耳热 $\varrho _ { J }$ 为

$$
Q _ { J } \ = \ { J _ { 0 } } ^ { 2 } R _ { i n }
$$

根据傅里叶定律，由于温差电单偶冷热端温差产生的传导热 $Q _ { K }$ 为

$$
Q _ { K } \ = \ K _ { 0 } \big ( T _ { h } \ - \ T _ { c } \big )
$$

其中

$$
K _ { \scriptscriptstyle 0 } = \frac { 1 } { \displaystyle \frac { \delta _ { \scriptscriptstyle 1 } } { \lambda _ { \scriptscriptstyle P 1 } { \cal A } } + \frac { \delta _ { \scriptscriptstyle 2 } } { \lambda _ { \scriptscriptstyle P 2 } { \cal A } } } + \frac { 1 } { \displaystyle \frac { \delta _ { \scriptscriptstyle 1 } } { \lambda _ { \scriptscriptstyle N 1 } { \cal A } } + \frac { \delta _ { \scriptscriptstyle 2 } } { \lambda _ { \scriptscriptstyle N 2 } { \cal A } } }
$$

$K _ { \theta }$ 为温差电单偶的热导， $\lambda _ { P I } \circ \lambda _ { P 2 } \circ \lambda _ { N I } \circ \lambda _ { P 2 }$ 分别为P、N型高温和低温型材料的平均导热系数，其数值根据各段材料两端温度和材料导热系数随温度的变化求得。

由于珀尔贴效应、傅里叶效应和焦耳效应的影响根据能量守恒原理， $\varrho _ { h }$ 、 $\textstyle { \mathcal { Q } } _ { c }$ 可表示为[]

$$
\begin{array} { r l } { \boldsymbol { \theta } _ { h } \ : = \ : \boldsymbol { \theta } _ { 1 } + \boldsymbol { \theta } _ { K } - 0 . 5 \boldsymbol { \theta } _ { J } \quad } & { } \\ { = \ : \alpha I _ { 0 } \boldsymbol { T } _ { h } + \ : K _ { 0 } \big ( \boldsymbol { T } _ { h } - \boldsymbol { T } _ { c } \big ) - 0 . 5 { \boldsymbol { I } _ { 0 } } ^ { 2 } \boldsymbol { R } _ { i n } } & { } \\ { = \ : \big ( \boldsymbol { T } _ { h s } - \boldsymbol { T } _ { h } \big ) \boldsymbol { K } _ { h } } \end{array}
$$

$$
\begin{array} { r l } { \ Q _ { c } \ = \ Q _ { 2 } \ + \ Q _ { _ K } \ + \ 0 . 5 Q _ { _ J } \ } & { } \\ { \ } & { = \ \alpha I _ { 0 } T _ { c } \ + \ K _ { 0 } \big ( T _ { h } \ - \ T _ { c } \big ) + \ 0 . 5 { T _ { 0 } } ^ { 2 } R _ { i n } } \\ { \ } & { = \ \big ( T _ { c } \ - \ T _ { c s } \big ) K _ { c } } \end{array}
$$

# 2 功率和效率方程

温差电单偶连接负载 $R _ { L }$ 后，电路中的电流为 $I _ { 0 }$ 此时温差电单偶的输出功率 $P$ 为

$$
\begin{array} { l } { { P = I _ { 0 } { } ^ { 2 } R _ { L } = \left[ \alpha \big ( T _ { h } - T _ { c } \big ) / \big ( R _ { i n } + R _ { L } \big ) \right] ^ { 2 } R _ { L } } } \\ { { \mathrm { ~ } = \alpha ^ { 2 } \big ( T _ { h } - T _ { c } \big ) ^ { 2 } R _ { L } / \big ( R _ { i n } + R _ { L } \big ) ^ { 2 } } } \end{array}
$$

温差电单偶的热电转换效率 $\eta$ 定义为[7]

$$
\eta = P \mathrm { ~ / ~ } Q _ { \mathit { h } }
$$

将式(15)、(13)代入式(16)，可得到温差电单偶的工作效率为

$$
\eta ~ = ~ I ^ { 2 } R _ { L } ~ / [ \alpha I _ { 0 } T _ { h } ~ + ~ K _ { 0 } \big ( T _ { h } ~ - ~ T _ { c } \big ) - 0 . 5 { T _ { 0 } } ^ { 2 } R _ { i n } ]
$$

# 3结果与分析

# 3.1热面温度的影响

在该分析中，选取冷面温度为 $3 0 0 \mathrm { K }$ ，单偶长度设为 $3 \mathrm { m m }$ ，选取热面温度由500K逐渐增大的到800K，计算分段温差电单偶性能随负载的变化。

图3为不同热面温度下温差电单偶性能随负载的变化。随着负载逐渐增大，单偶的输出功率和转换效率均先增大后减小。当负载电阻与温差电单偶的内阻相等时，温差电单偶的输出功率最大，此时电路中的负载电阻定义为最大功率电阻。温差电单偶达到最大转换效率时的负载定义为最大效率电阻。对比图3a和图3b，可以发现在相同条件下最大效率电阻略大于最大功率电阻。

![](images/0c61cbe38b286dfd06dc931734c0d2203e4e9df75efbb63694f75f0465b3314d.jpg)  
图3不同热面温度下温差电单偶性能随负载的变化 Fig.3Variation of performance of the thermoelectric unicouple with load resistance for different hot surface temperatures

随着热面温度逐渐增大，单偶的最大输出功率逐渐升高，如图3a所示。这是由于随着热面温度的升高，温差电单偶热端温度快速升高，冷热端温差逐渐增大，单偶产生电压明显上升，而内阻虽增大但变化幅度较小，因此最大输出功率逐渐升高。

随着热面温度的升高，分段温差电单偶的最大转换效率逐渐增大，增大速度逐渐降低，如图3b所示。随着热面温度的升高，两种材料的分界面温度逐渐升高，低温型 ${ \bf B i } _ { 2 } \mathrm { T e } _ { 3 }$ 材料两端的平均温度逐渐高于 ${ \bf B i } _ { 2 } \mathrm { T e } _ { 3 }$ 的最佳效率温度， ${ \bf B i } _ { 2 } \mathrm { T e } _ { 3 }$ 材料的效率出现负增长，虽然高温型材料的效率仍在逐渐增大，但分段温差电单偶的效率增速逐渐降低。

随着热面温度的升高，最大功率电阻和最大效率电阻略微增大。随热面温度的升高， ${ \bf B i } _ { 2 } \mathrm { T e } _ { 3 }$ 的电阻率逐渐增大， $\mathrm { C o S b } _ { 3 }$ 电阻率随温度变化较小，且 $\mathrm { C o S b } _ { 3 }$ 的电阻率明显高于 ${ \bf B i } _ { 2 } \mathrm { T e } _ { 3 }$ ，从而使分段温差电单偶内阻的变化介于两种材料之间，更接近于 $\mathrm { C o S b } _ { 3 }$ 电阻率的变化，而最大功率电阻与温差电单偶的内阻相等，因此最大功率电阻随热面温度升高略微增大。

# 3.2冷面温度的影响

在本分析中，设定热面温度为650K，冷面温度设定为由300K逐渐增大到500K，单偶的长度设为$3 \mathrm { m m }$ ，计算不同冷面温度下单偶的性能随负载的变化。

![](images/15c30eef6859267a24fec9404f81388685882499f52051a1a4d67bec91f70e85.jpg)  
图4不同冷面温度下温差电单偶性能随电阻的变化 Fig.4Variation of performance of the thermoelectric unicouple with load resistance for different cold surface temperatures

图4为不同热面温度下温差电单偶性能随负载电阻变化的曲线。随着冷面温度逐渐增大，温差电单偶的输出功率和热电转换效率均降低，这是由于随着冷面温度的升高，温差电单偶冷端温度快速上升，冷热端温差逐渐降低，因此最大输出功率逐渐降低。由于冷热端温差逐渐降低，热端吸热量也逐渐降低，但降低的速度低于输出功率的降低速度，因此最大转换效率也逐渐下降。

# 3.3温差电单偶长度的影响

在该分析中，热面温度设定为650K，冷面温度设定为300K，分别计算分段温差电单偶在长度为

$3 \mathrm { m m }$ 、 $2 \mathrm { m m }$ 、 $1 \mathrm { m m }$ 、 $0 . 5 \mathrm { m m }$ 、 $0 . 2 5 \mathrm { m m }$ 时的性能随负载的变化。

图为5a温差电单偶长度对输出功率的影响，随着温差电单偶长度由 $3 \mathrm { m m }$ 逐渐缩短，分段温差电单偶的输出功率均逐渐增大，最大功率电阻逐渐减小。这是由于随着温差电单偶长度减小，其热阻减小,冷热端温差减小，产生的开路电压也随之减小，同时温差电单偶的内阻也减小，且减小速度大于开路电压的减小速度，故最大输出功率逐渐增大。

![](images/e8c02343c8b3d43110b277f3475c104cb8d732df6069ccc40fad9865af9030ad.jpg)  
图5不同温差电单偶长度下温差电单偶性能随负载的变化 Fig.5Variation of performance of thermoelectric unicouple with load resistance for different unicouple thicknesses

图5b为温差电单偶长度对转换效率的影响，随着温差电单偶长度由 $3 \mathrm { m m }$ 逐渐缩短，温差电单偶的最大转换效率逐渐降低。这是由于随着温差电单偶长度的缩短，输出功率虽逐渐增大，但由于长度缩短，冷热端传热热阻大幅降低，温差电单偶热端吸热量大幅升高，故最大转换效率逐渐降低。

# 3.4热表面对流传热系数的影响

在该分析中，冷面温度设为300K，温差电单偶长度定为 $3 \mathrm { m m }$ 。热表面有温度为800K的流体流过，计算在理想条件（热表面对流换热系数无穷大）和热表面对流换热系数为 $1 5 0 0 \mathrm { W / m } ^ { 2 } \mathrm { K }$ 、 $1 0 0 0 \mathrm { W / m } ^ { 2 } \mathrm { K }$ ，$5 0 0 \mathrm { W / m } ^ { 2 } \mathrm { K }$ 、 $1 0 0 \mathrm { W / m } ^ { 2 } \mathrm { K }$ 时性能随负载的变化。

图6为热表面对流传热系数对输出功率的影响，随着热表面对流传热系数由 $1 0 0 \mathrm { W / m } ^ { 2 } \mathrm { K }$ 逐渐增大,分段温差电单偶的最大输出功率和最大转换效率均逐渐增大，最大功率电阻略微增大。这是由于随着热表面对流传热系数的的增大，热面温度快速升高，冷热端温差上升，根据3.1的分析可知，此时最大输出功率和最大转换效率均逐渐增大，最大功率电阻也随之增大。同时随着热表面对流传热系数的增大，最大输出功率和最大转换效率的增速均逐渐降低，最大输出功率和转换效率逐渐接近理想条件。

![](images/3c9a6ecd06c9f18e2325469b9302d58569fa874506d909ef54b9b3556939a41f.jpg)  
图6不同热表面对流传热系数下温差电单偶性能随负载的变化  
Fig.6Variation of performance with load resistance for different convection heat transfer coefficients of hot surface

# 4结论

本文对分段温差电单偶的性能进行了模拟分析，计算了不同条件下温差电单偶的输出功率和转换效率随负载的变化趋势，主要结论总结如下：1）提高热面温度、降低冷面温度、缩短温差电单偶的长度和提高热表面对流传热系数均可以提高分段温差电单偶的最大输出功率。

2）提高热面温度、降低冷面温度、延长温差电单偶长度、提高热表面对流传热系数均可以提高分段温差电单偶的最大转化效率3）热表面的换热效率对温差电单偶的输出功率和转换效率有很大影响，在设计温差发电器时应尽可能提高热表面的对流传热系数，同时设法增大热端的换热面积。

# 参考文献

[1] Chammas R El, Clodic D.Combined Cycle for Hybrid Vehicles[C]/SAE 2005 World Congress & Exhibition, Session Advanced Hybrid Vehicle Powertrains (part 4 & 5). 2005.   
[2]Yang J. Potential Applications of Thermoelectric Waste Heat Recovery in the Automotive Industry[C]//Thermoelectrics，2005．ICT 2005．24th International Conference on.IEEE,2005:170-174.   
[3]Poudel B,Hao Q，Ma Y，et al. High-Thermoelectric Performance ofNanostructured Bismuth Antimony Telluride Bulk Alloys[J]. Science，2008，320(5876): 634-638.   
[4]赵媛媛，曾葆青，李影．分段温差电元件性能的仿真研 究[J]．电源技术,2010 (005):493-495. ZHAO Yuanyuan, ZENG Baoqing, LI Ying. Study on Simulation of Segmented Thermoelectric Unicouples Performance[J]. Chinese Journal of Power Sources,2010 (005): 493-495   
[5]周洪宇. $\mathbf { B i } _ { 2 } \mathrm { T e } _ { 3 } / \mathrm { C o S b } _ { 3 }$ 宽温域热电器件的设计与性能 [D]．武汉：武汉理工大学,2012. ZHOU Hongyu. TheDesignandPropertiesof $\mathrm { B i _ { 2 } T e _ { 3 } / C o S b _ { 3 } }$ ThermoelectricGeneratorwith Wide Temperature Range[D]. Wuhan: Wuhan University of Technology,2012.   
[6]Chen L,Gong J, Sun F,et al. Effect of Heat Transfer on thePerformanceofThermoelectricGenerators[J]. International Journal of Thermal Sciences,2002,41(1): 95-99.   
[7]Gou X, Xiao H, Yang S.Modeling, Experimental Study and Optimization on Low-Temperature Waste Heat Thermoelectric Generator System[J].Applied Energy, 2010,87(10): 3131-3136.