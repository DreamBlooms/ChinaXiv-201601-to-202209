# 数值模拟方法在河流冰塞水位模拟中的应用以黄河三湖河口弯道段为例

徐凯莉¹²，吕海深²，刘名文}²，朱永华1²，何超禄¹²，谢冰绮³（1.河海大学水文水资源与水利工程科学国家重点实验室,江苏 南京210098；2.河海大学水文水资源学院，江苏 南京210098；3.珠江水利委员会珠江水利科学研究院,广东 广州510630)

摘要：运用开源的河冰数值模型RIVICE模拟黄河三湖河口弯道段2008—2010年开河期的冰塞水位,并进行模型参数的敏感性分析。研究所使用的流量、水位、冰厚等数据均来自水文年鉴。结果表明,用RIVICE模型模拟开河期冰塞水位具有很高的可行性。冰塞回水水位对上游边界流量十分敏感，说明了水利工程调控的重要性,研究通过数值模型对冰塞水位进行模拟及演变预测，为水利工程调控和凌汛防治提供一定的参考。

关键词：黄河三湖河口弯道段；冰塞水位；RIVICE模型

黄河宁蒙河段由于特殊的地理位置、水力条件、河道形态以及人为因素的影响，是凌汛灾害频发的典型河段[1]。凌汛的发生是由于冰塞,国际上将冰塞划分为窄河冰塞和宽河冰塞，分别是水力增厚和机械增厚所致[2],国内则将其称为冰塞和冰坝[3]。冬季冻结期易发生冰塞,春季开河期易发生冰坝，开河期的冰坝会使上游水位大幅壅高，造成更严重的淹没和溃堤风险。据统计1991一2010年黄河宁蒙河段产生的局部冰坝凌灾多达36场，单次损失最多达7亿元[4]。2010年后，受到上游水利工程调控的影响，冰坝凌灾减少，多以文开河为主[5]三湖河口弯道段因其独特的河道形态，属于极易卡冰位置，虽然在上游水利工程的调控和人工破冰的作用下，凌汛灾害得到一定缓解，但对于开河期冰坝洪水的研究需要进一步的探究。

国外对冰塞的机理研究始于20世纪60年代，最初基于稳态进行冰的理论研究[2]。随着计算机技术的发展，国际上有很多学者建立了模拟河冰的数值模型,如一维模型ICEJAM[6]、RIVJAM[7]、River1D[8]、RIVICE[9]、RICEN[10]等，二维模型DynaICE[1]和CRISSP2D[12]。国内在对河冰原型观测和实验研究等方面取得了很多成果[13-15],但对河冰的数值模拟起步较晚，研究较少。茅泽育等[16结合热力学和动力学计算，模拟河道结冰封冻过程中冰塞体的演变以及对水位的影响；冀鸿兰等1通过耦合水温和冰盖生消模型对静水状态下的水体结冰融化过程进行了数值模拟;黄河水利委员会[18]以RICEN模型为基础并做出改进，将使冰盖破碎的临界流量由1个常数改为1个经验公式，开发了综合一维非稳态河冰动力模型YRIDM;李超[9用二维模型DynaICE模拟了三湖河口弯道段的封河过程

不同于已有研究，本研究的目标是模拟开河期，完整冰盖破裂之后向下游流去，在河道的易卡冰位置堵塞，降低河道过流能力，引起上游水位壅高的过程。这种堵塞可能是由单层浮冰构成的表面冰塞[20],流量大时，也有可能受力增厚形成冰坝（宽河冰塞），所以，本文将这一过程统称为冰塞。本研究选取RIVICE模型模拟这一过程，一是因为RIVICE模型不仅可以模拟冬季河道结冰封冻，也可模拟开河期冰盖破碎后在力的作用下增厚，形成阻水冰塞9]；二是因为RIVICE模型采用冰动力与水动力双向松散耦合的方式来模拟冰塞，不需要求解复杂的微分方程,计算更加简单高效[21]

本研究选取黄河内蒙古三湖河口弯道段为研究河段，模拟开河时期因河道卡冰而造成的水位壅高。旨在验证RIVICE模型模拟的可行性，以及为上游水利工程在开河期的防凌汛调度提供科学依据，在尽可能不造成严重冰塞洪水的情况下，向下游释放更多的流量。

# 1材料与方法

# 1.1 研究区概况

选取地处半干旱区的黄河三湖河口弯道段(图1),范围是亿利黄河大桥以上的 $9 . 8 9 \mathrm { k m }$ 。此处河床坡降小,河道中有心滩地形复杂,加之泥沙淤积，过流能力弱。此处有2个弯道、弯道曲率大，第2个弯道处河道收缩近乎一半，加之受下游亿利黄河大桥桥墩的阻水影响，是极易卡冰的河段。黄河三湖河口上游段河流呈自南向北流向，因此在春季开河期，上游先开河，破裂的冰盖向下流至此处，加剧了形成冰塞洪水的风险，所以在此段进行冰塞洪水水位的预报预警研究意义突出。参考已有研究[]，该河段河底坡度为0.0001，据此概化出了宽浅矩形河道断面。

# 1.2数据来源

本研究采取2008年、2009年、2010年畅流期和开河期的洪水数据来率定和验证模型，洪水数据均来自水文年鉴。模拟的上边界设置为流量过程，下边界设置为水位过程。因选取河道短，边界处没有水位和流量的实测数据，所以上边界的流量和下边界的水位都用三湖河口站的数据。与此同时，用三湖河口站的数据来验证模拟结果。

# 1.3冰塞计算理论方法

RIVICE模型是由加拿大环境与气候变化委员会（Environment and Climate Change Canada,ECCC)开发的开源模型。该模型是一维的水动力与冰动力过程的双向松散耦合模型，用隐式有限差分格式对圣维南方程组进行求解，并加入了河冰动力过程。模型可模拟冰花的形成、岸冰的演进、冰盖的形成、来冰在冰盖前缘的并置、锚冰、冰的输移、冰盖的融化与破碎、冰塞和悬坝这些河冰过程[22]。

Lindenschmidt等[23]已将此模型用于加拿大的阿萨巴斯卡河、和平河[24]等河流的冰塞洪水预报，已有的研究结果表明该模型具有较好的模拟效果，能较准确的估计发生冰塞时的回水剖面。本研究选用了RIVICE中的水动力、水力糙率和冰盖受力增厚这3个模块对黄河三湖河口弯道处的冰塞洪水过程进行模拟。

1.3.1水动力模拟虽然河道上覆盖有冰，但依旧将其视为明渠水流，忽略冰盖的压力。和一般水力学模型相同，RIVICE模型采用圣维南方程组来计算一维明渠非恒定流,因将河道概化成矩形且无侧向入流，圣维南方程组被简化如下：

连续方程： $B \frac { \partial z } { \partial t } + \frac { \partial Q } { \partial x } = 0$ 运动方程： $\begin{array} { l } { { \displaystyle { \left( \frac { \partial Q } { \partial t } + 2 v \frac { \partial Q } { \partial x } \right) \frac { 1 } { A g } = } } } \\ { { \displaystyle { - ( 1 - F ^ { 2 } ) \frac { \partial z } { \partial x } + \left( \frac { 1 } { B } \frac { \partial A ^ { \prime } } { \partial x } \right) F ^ { 2 } - \frac { Q | Q | } { K ^ { 2 } } } } } \end{array}$ 式中： $B$ 为河道宽度 $( \mathrm { m } ) { \ : } ; z$ 为水位 $\mathrm { ( m ) }$ $Q$ 为流量( $\mathbf { m } ^ { 3 }$ ：$\mathrm { ~ s ~ } ^ { - 1 }$ ）； $\mathbf { \Phi } _ { t }$ 为时间(s); $x$ 为距离 ${ \bf \Pi } ( { \bf \Pi } _ { \mathrm { m } } ) { \bf \Pi } _ { ; v }$ 为流速 $\left( \mathbf { m } ^ { 2 } \cdot \mathbf { s } ^ { - 1 } \right) ; A$ 为河道过流面积 $( \mathbf { m } ^ { 2 } ) { \ : } ; g$ 为重力加速度 $( 9 . 8 \mathrm { m } \cdot \mathrm { s } ^ { - 2 } ) ; F$ 为弗劳德数； $K$ 为输送系数。 $A ^ { z }$ 为过流面积随水位的变化率。

![](images/6aff415c266d0387cba5a6b58a4257d9f93b9994995bb801681c7ff7cc62365c.jpg)  
图1 黄河三湖河口弯道段  
Fig.1Sanhuhekou bend reach of the Yellow River

采用隐式有限差分格式对方程进行求解，得到 各个计算断面上各个时刻的水流状态。

1.3.2水力糙率在有冰盖的河段，水流除受到河床的阻力外还受到冰盖下表面的阻力。冰层覆盖下河道的输送系数 $K _ { i }$ 采用调整后的曼宁公式计算：

$$
K _ { i } = \frac { 1 } { n _ { c } } A { R _ { c } } ^ { 2 / 3 } 
$$

式中： $n _ { c }$ 为河床和冰盖的复合曼宁糙率系数； $R _ { c }$ 为冰盖下的水力半径 $\left[ R _ { c } { = } A / ( P _ { b } { + } P _ { i } ) \right] ;$ $P _ { b }$ 为河道湿周; $P _ { i }$ 为冰盖湿周。复合曼宁糙率系数 $n _ { c }$ 用Sabaneev公式计算：

$$
n _ { c } = \left( \frac { n _ { b } ^ { ~ 3 / 2 } + n _ { i } ^ { ~ 3 / 2 } } { 2 } \right) ^ { 2 / 3 }
$$

式中：河床的曼宁糙率系数 $n _ { b }$ 作为一个参数，用畅流期的洪水进行率定，在模拟冰塞的过程中保持不变；对于冰盖的曼宁糙率系数 $n _ { i }$ ,模型采取KGS方法[9]。

KGS方法基于Nezhikhovskiy25提出的公式，将冰盖的糙率系数视为冰厚的函数：

$$
n _ { i } = \frac { n _ { 8 \mathrm { ~ m ~ } } } { 0 . 1 0 5 } \bigl [ 0 . 0 3 0 2 \ln ( h ) + 0 . 0 4 4 5 \bigr ]
$$

式中： $h$ 为冰盖的厚度 $( \mathrm { m } ) { \mathrm { ; } n _ { 8 \mathrm { ~ m ~ } } }$ 为 $h { = } 8 \mathrm { ~ m ~ }$ 时冰盖的糙率系数，将其作为1个系数，用冰塞时的洪水数据率定。

1.3.3冰盖厚度作用在冰盖上的力包括6种，如图2所示： $F _ { T }$ 为水流对冰盖前缘产生的推力； $F _ { D }$ 为冰盖下流动的水对冰盖的拖力； $F _ { \scriptscriptstyle  { W } }$ 为冰盖重量沿坡向的分量； $\boldsymbol { F } _ { F }$ 为冰盖和河岸之间的摩擦力； $F _ { C }$ 为当冰盖冻结到河岸上产生的内聚力; $F _ { I }$ 为冰盖的内阻力。因此次模拟春季开河期的冰塞，此时 $F _ { C }$ 很小，所以忽略。

水流对冰盖前缘产生的推力 $F _ { T }$ 的计算公式为：

$$
F _ { _ T } = \left( 1 - \frac { d _ { d } } { d _ { _ u } } \right) ^ { 2 } { v _ { d } } ^ { 2 } B d _ { _ u } \frac { \gamma } { 2 g }
$$

式中： $d _ { u }$ 为冰盖前缘上游处水深 $\mathrm { ( m ) }$ $d _ { d }$ 为冰盖前缘下水深 $( \mathbf { \Phi } _ { \mathrm { m } } ) { \bf { ; } } v _ { d }$ 为冰盖前缘下的宽度平均速度 $\left( \mathbf { m } \cdot \mathbf { s } ^ { - 1 } \right) ; B$ 为冰盖宽度 $( \mathrm { m } ) { : \gamma }$ 为水的比重 $( 9 8 0 0 \mathrm { N } \cdot \mathrm { m } ^ { - 3 }$ )。

冰盖下流动的水对冰盖的拖力 $F _ { D }$ 的计算公式为：

$$
F _ { _ D } = \left( \frac { \gamma d S n _ { i } ^ { ^ { 1 . 5 } } } { 2 n _ { c } ^ { ^ { 1 . 5 } } } \right) A _ { i }
$$

式中： $s$ 为水力坡度； $d$ 为冰盖下水深 ${ \bf \Pi } ( { \bf m } ) { \bf ; } A _ { i }$ 为冰盖 的下表面面积 $\left( \mathbf { m } ^ { 2 } \right)$ U

冰盖重量沿坡向的分量 $F _ { \scriptscriptstyle  { W } }$ 的计算公式为：

$$
F _ { _ { W } } = \gamma _ { _ { i } } V _ { _ { o } } S
$$

式中： $\gamma _ { i }$ 为冰的比重 $( 9 0 2 0 \mathrm { N } \cdot \mathrm { m } ^ { - 3 }$ ）； $V _ { o }$ 为两岸间冰盖 的体积 $\left( \mathbf { m } ^ { 3 } \right)$ 0

冰盖和河岸之间摩擦力 $\boldsymbol { F } _ { F }$ 的计算公式为：

$$
F _ { _ { F } } = 2 f h l K _ { _ { 1 } } \tan \varphi
$$

式中 $: f$ 为沿岸冰盖的压应力 $( \mathrm { P a } ) { \mathrel { \operatorname { \cdot } } } K _ { 1 }$ 为1个系数，表示冰盖横向应力与纵向应力之比; $\varphi$ 为冰盖和河岸间的摩擦角; $l$ 为断面之间的距离 $\mathrm { { ( m ) } }$ 。将 $K _ { 1 }$ 和 $\mathrm { t a n } \varphi$ 组合成1个参数 $K _ { 1 } \mathrm { t a n }$ ，用冰塞时的洪水数据率定。

冰盖内阻力 $F _ { I }$ 的计算公式：

$$
F _ { _ { I } } = \gamma _ { i } \bigg ( 1 - \frac { \gamma _ { i } } { \gamma } \bigg ) \frac { h ^ { 2 } B } { 2 } K _ { \gamma } e
$$

式中： $e$ 为冰盖的孔隙度； $K _ { 2 }$ 为强度系数，二者均作为参数，用冰塞时的洪水数据率定。

![](images/5d7f83553ba3672307ae97bdecb0576f532558cf79980df06a82be160a942814.jpg)  
图2冰盖受力示意图  
Fig.2 Schematic diagram of ice covert force

如果 $F _ { T } + F _ { D } + F _ { \mathrm { { w } } } - F _ { F } { < } F _ { I }$ ，即内阻力可以抵抗外力，来冰会在冰盖前缘发生并置之后向上游延伸，形成表面冰塞。如果 $F _ { T } + F _ { D } + F _ { \mathrm { { w } } } - F _ { F } { > } F _ { I }$ ，即内阻力不能抵抗外力，来冰发生推挤使冰盖增厚直到内阻力能够抵抗外力，形成冰坝。

# 1.4模型参数及敏感性分析

参数的敏感性分析是了解参数对模型影响大小的重要途经。对于本次模拟来说，研究冰塞水位对参数的敏感性，可以揭示冰塞洪水形成的主要控制因素，为凌汛防治提供科学依据。

本研究选取传统的局部敏感性分析方法对参数和边界条件进行敏感性分析，基于2008年、2009年、2010年的数据，在保持其他参数值不变的情况下，单次让1个参数或边界条件提高 $1 0 \%$ ,计算上边界处回水水位的变化。参数敏感性用以下公式计算：

$$
S _ { _ Y } = \left| \frac { Y - Y _ { _ \mathrm { b a s e } } } { Y _ { _ \mathrm { b a s e } } } \times \frac { X _ { _ \mathrm { b a s e } } } { X - X _ { _ \mathrm { b a s e } } } \right| \times 1 0 0 \%
$$

式中：base表示参数基础值; $Y$ 表示状态变量，即上边界处的水位； $X$ 表示参数； $S _ { Y }$ 表示变量 $Y$ 对参数 $X$ 的敏感性指数。

# 2 结果与讨论

# 2.1畅流期模型率定

首先，要验证模型水动力部分的有效性以及率定参数 $n _ { b }$ ,研究选取2008-08-09—08-15、2009-08-22—08-27这2场洪水来率定，再用2010-06-10—06-15的洪水数据进行验证。率定和验证的结果中，当 $n _ { b } { = } 0 . 0 1 2$ 时，模拟结果较好。图3表明了2008年、2009年和2010年年3场洪水率定和验证的结果，可以看出，模拟出的水位与实测值吻合良好。经过统计计算，模拟的3场洪水中，水位的确定性系数分别为0.91、0.90和 $0 . 8 7$ 。流量的确定性系数均

为 $0 . 9 9$ 。

这个结果证明了RIVICE模型水动力部分可以很好的模拟无冰状态下的洪水，为模拟冰塞洪水提供了良好的基础。

# 2.2开河期模型率定

开河期冰盖破裂、流冰、卡冰以及冰塞被冲向下游等过程具有很大的随机性，模拟如此复杂的过程造成的回水对于本研究来说也是巨大的挑战。因为模型并不能完全精准地捕捉这一复杂的变化过程，所以本研究选取2008年、2009年、2010年开河期的洪水过程来验证RIVICE模拟冰塞回水水位的可行性。

开河期流量的突然增大会造成冰盖破裂和机械增厚，为更好地预报特定来冰条件下一定的流量会造成的冰塞相应壅水高度，上边界条件设为不变的入流流量，下边界设置为不变的水位。因为本次模拟不考虑气温的变化，所以单次只模拟3日的水位过程。

研究选择2008-03-16—03-19、2009-03-16—03-19、2010-03-22—03-25这3场冰塞洪水事件对RIVICE模型进行率定和验证，并分别在各年中选取同流量下畅流期模拟的水位作为比较。表1中列出了3次模拟的参数值和边界值设置。本次模拟设置2个边界条件和9个参数，边界条件为上边界的流量$Q$ 和下边界的水位 $W$ 。9个参数中河床的曼宁糙率系数 $n _ { b }$ 、计算冰塞下表面曼宁糙率系数的参数 $n _ { 8 \mathrm { ~ m ~ } }$ 、计算冰塞与河岸之间摩擦力的参数 $K _ { 1 } \mathrm { t a n }$ 、计算冰塞内阻力的参数 $K _ { 2 }$ 和冰塞的孔隙度 $e$ 在每次模拟中保持不变。冰塞前缘的厚度 $F _ { T }$ 、冰塞下游完整冰盖的厚度 $h$ 和每个时刻冰的增量 $V _ { \mathrm { i c e } }$ 每年不同，参考水文年鉴。此外，模拟河段总长为 $9 . 8 9 \ \mathrm { k m } , 5 0 \ \mathrm { m }$ 设置1个计算断面，卡冰位置 $x$ 均设为第2个弯道收缩处，既第167个计算断面处。

![](images/a0cf4161c155fcc8a21f1ab7835dc547480a2eb6af1034a1b5cbb42227e38801.jpg)  
图3畅流期洪水水位模拟结果  
Fig.3Simulation results of flood stage at open water

表1模型边界条件和参数值   
Tab.1 Boundary conditions and parameter of model   

<html><body><table><tr><td>参数/边界条件</td><td>单位</td><td>表征含义</td><td>2008年</td><td>2009年</td><td>2010年</td></tr><tr><td>nb</td><td>1</td><td>河床糙率</td><td>0.012</td><td>0.012</td><td>0.012</td></tr><tr><td>n8m</td><td>1</td><td>冰盖糙率</td><td>0.12</td><td>0.12</td><td>0.12</td></tr><tr><td>Kitan</td><td>1</td><td>冰塞与河岸的摩擦力</td><td>0.218</td><td>0.218</td><td>0.218</td></tr><tr><td>K</td><td>1</td><td>冰塞的内阻力</td><td>8.5</td><td>8.5</td><td>8.5</td></tr><tr><td>e</td><td>1</td><td>冰塞的孔隙度</td><td>0.3</td><td>0.3</td><td>0.3</td></tr><tr><td>Fr</td><td>m</td><td>冰塞前缘厚度</td><td>0.35</td><td>0.25</td><td>0.20</td></tr><tr><td>h</td><td>m</td><td>冰塞下游完整冰盖厚度</td><td>0</td><td>0</td><td>0</td></tr><tr><td>x</td><td>1</td><td>卡冰位置</td><td>167</td><td>167</td><td>167</td></tr><tr><td>Vice</td><td>m·△t-1</td><td>上游来冰量</td><td>50</td><td>60</td><td>40</td></tr><tr><td>Q</td><td>m·s-1</td><td>上游边界流量</td><td>800</td><td>661</td><td>670</td></tr><tr><td>W</td><td>m</td><td>下游边界水位</td><td>1020.7</td><td>1020.18</td><td>1020.36</td></tr></table></body></html>

图4表明了2008年、2009年、2010年开河期模拟的水位过程与实测的水位过程的比较以及与同流量下畅流期模拟的水位的比较。从图中可以看出，在开河期，虽然模拟的水位变化较为平缓，实测的水位变化较为复杂，但是模拟的水位和实测值的变化趋势一致。2009年第2日之后流量陡增到897，水位过程增幅较大，模拟的水位不能很好地模拟出这一陡增的水位。经过统计计算，2008年、2009年、2010年的最大误差分别为 $0 . 0 3 5 \mathrm { ~ m ~ } , 0 . 2 4 9$ $\mathrm { m } . 0 . 1 8 2 \mathrm { m }$ ，确定性系数为 $0 . 9 2 , 0 . 7 9 , 0 . 7 6 _ { \circ }$

模拟结果说明了模型可以很好地模拟春季开河期由于河道冰塞而造成的水位升高。与相同流量下畅流期模拟的水位的比较可知，有冰塞影响时的水位比畅流期的水位高出平均 $1 . 4 \mathrm { m }$ ，说明了冰塞洪水的严重性以及准确模拟并预报冰塞洪水的重要性。

# 2.3敏感性分析结果

从敏感性分析结果(图5)中可以看出，上边界处的水位对流量Q最为敏感，说明了开河期控制上游来水的重要性。其次是计算冰盖曼宁糙率系数的参数 $n _ { 8 \mathrm { ~ m ~ } }$ 、下游边界水位 $W$ 。流量的增大除了会直接导致水位升高外还会使并置的冰盘发生机械增厚，冰盖的糙率增大会增加水流的阻力，下游的水位升高会提高壅水的基础，这些均是形成冰塞洪水的重要成因，所以这些值的增大会造成冰塞回水水位的大幅增大。上游来冰量的增加会造成更加严重的冰塞，使上游水位壅高更多。

计算冰塞内阻力的参数 $K _ { 2 }$ 、计算冰塞与河岸之间摩擦力的参数 $K _ { 1 } \mathrm { t a n }$ 和冰塞的孔隙度 $e$ 的增大会使上边界处的水位减小，是因为冰塞的内阻力和河岸对冰塞的摩擦力都是与流向相反的力，这2个值的升高会增加冰塞的稳定性，使冰塞的增厚减少，冰塞对水流产生的摩擦阻力减小，使回水水位降低。在堵塞过程中冰被压实，孔隙度越大，冰塞体积减小的越多，造成的冰塞回水水位就越小。

河床的糙率、冰盖前缘厚度和冰塞下游完整冰盖的厚度是低敏感或非敏感参数。

模拟2008年、2009年和2010年开河期的冰塞水位时，依据实测数据设置的流量和水位边界条件、冰盖厚度和上游来冰量存在较大差异，在此影响下，参数和边界条件的敏感性也显示出较大差异，如2008年和2010年冰塞开始的位置向下游移动，会造成上游的回水水位升高，而2009年则相反。这充分说明了冰塞事件及其造成的洪水水位具有混沌性和随机性。

![](images/d68bdb1863d7f3a88f51800ddff75cdcc9913772082ed6c9facc8a42ca391297.jpg)  
图4开河期和畅流期冰塞水位模拟结果  
Fig.4 Simulation results of ice jam stage at break-up period and open water period

![](images/f700a7028c4ba660de24f88b71f4bd5a0f6e5ce0fb3646b60fbc409f0a10b522.jpg)  
图5敏感性分析结果  
Fig.5Results of sensitivity analysis

# 3结论

本研究用开源的河冰模型RIVICE模拟了春季开河期黄河三湖河口弯道段的冰塞水位，选取畅流期和开河期的冰塞洪水对RIVICE模型进行了验证,并分析了模型参数和边界条件的敏感性，得出以下结论：

（1）相同流量下，相较于无冰状态，有冰塞发生会造成更高的水位，RIVICE模型通过数值模拟的方法考虑了来冰在河道中的卡堵、因受力而导致的机械增厚和冰对水流的阻力作用，进而能有效的模拟出由于冰塞导致的水位抬升。

（2）确定上边界流量情况下，用RIVICE模型模拟河道的冰塞回水水位具有可行性。可以为上游水利工程的调蓄提供科学依据,确保在不会造成严重的下游冰塞洪水的情况下合理下泄流量。在没水利工程或者水利工程无法调节的情况下，为上游来水量造成冰塞洪水的严重性提供有效的预警

(3）冰塞造成的回水水位对流量最为敏感，证明了上游水利工程对开河期流量调控的重要性，因此水利工程调节方案的有效性是冰塞洪水防控的重要保障。

参考文献(References）:   
[1]姚惠明,秦福兴,沈国昌,等.黄河宁蒙河段凌情特性研究[J].水 科学进展,2007,18(6):893-899.[Yao Huiming,QinFuxing,Shen Guochang,et al.Ice regime characteristics in the Ningxia-Inner Mongolia reach of Yellow River[J].Advance in Water Science, 2007,18(6): 893-899.]   
[2]Pariset E, Hausser R,Aagnon A. Formation of ice covers and ice jams in rivers[J]. Journal of the Hydraulics Division,1966,92 (HY6): 1-24.   
[3]河流冰情观测规范:SL 59—2015[S].北京:中国水利水电出版 社,2015.[Specification for Observation of Ice Regime in Rivers: SL 59—2015[S]. Beijing: China Water & Power Press,2015.]   
[4]史新娟.黄河内蒙古段河冰过程及热力增长模型研究[D].呼和 浩特：内蒙古农业大学,2013.[Shi Xinjuan.Ice Process and a Model of the Thermal Growth and Decay of Ice Cover in the Inner Mongolia Reach of the Yellow River[D].Hohhot: Inner MongoliaAgricultural University,2013.]   
[5]韩作强,梁聪聪,朱春子.2018—2019年度黄河宁蒙河段凌情 特点分析[J].中国防汛抗旱,2020,30(5):21-24,29.[Han Zuoqiang, Liang Congcong, Zhu Chunzi. Analysis of iceregime characteristics in Ningxia-Inner Mongolia section of the Yellow River in2018——2019[J]. China Flood & Drought Management,2020,30 (5): 21-24,29.]   
[6] Flato G M, Gerard R. Calculation of ice jam profiles proceedings[J]. 4th Workshop on River Ice,Montreal,1986: C-3(CGU-HS Committee on River Ice Processes and the Environment, Edmonton, Canada).   
[7]Beltaos S. Numerical computation of river ice jams[J]. Canadian Journal of Civil Engineering,1993,20(1): 88-99.   
[8]Andrishak R,Hicks F.Simulating the effects of climate change on the ice regime of the Peace River[J]. Canadian Journal of Civil Engineering,2008,35(5): 461-472.   
[9]EC (Environment Canada) RIVICE model-User’s manual[M]. Saskatoon, SK, Canada, Environment Canada Steering Commitee,2003.   
[10]Shen H T,Wang D S,Lal A M W.Numerical simulation of river ice processes[J]. Journal ofCold Regions Engineering,1995,9(3): 107-118.   
[11]Shen H T,Su J,Liu L. SPH simulation of river ice dynamics[J]. Journal of Computational Physics,200o,165(2): 752-770.   
[12] Liu L,Li H, Shen H T.A two-dimensional comprehensive river ice model[C]/Proceedings of the 18th IAHR Symposium on River Ice, Sapporo, Japan, 2006.   
[13]可素娟,吕光圻,任志远.黄河巴彦高勒河段冰塞机理研究[J]. 水利学报,200,31(7):66-70.[Ke Sujuan,Lyu Guangqi,Ren Zhiyuan. Study on mechanism of ice jam formation in Bayangaole sectionof Yellw River[J].Journal of Hydraulic Engineering, 2000,31(7): 66-70.]   
[14] 王军,章宝平,陈胖胖,等.封冻期冰塞堆积演变的试验研究[J]. 水利学报,2016,47(5): 693-699.[Wang Jun, Zhang Baoping, Chen Pangpang,et al. Experimental study of jam accumulation during freezing period[J].Journal of Hydraulic Engineering,2O16,47(5): 693-699.]   
[15]翟佳伦,史小红,刘禹,等.乌梁素海冰封期水温与溶解氧浓度 变化研究[J].干旱区研究,2021,38(3):629-639.[Zhai Jialun, Shi Xiaohong,Liu Yu,et al.Change law of water temperature and dissolved oxygen concentration of Wuliangsu Sea in icebound period[J].Arid Zone Research,2021,38(3): 629-639.]   
[16]茅泽育,吴剑疆,张磊,等.天然河道冰塞演变发展的数值模拟 [J].水科学进展,2003,14(6):700-705.[Mao Zeyu,Wu Jianjiang, Zhang Lei,et al. Numerical simulation of river ice jam[J].Advance in Water Science,2003,14(6): 700-705.]   
[17]冀鸿兰,石慧强,牟献友,等 水塘静水冰生消原型研究与数值 模拟[J].水利学报,2016,47(11): 1352-1362.[Ji Honglan,Shi Huiqiang,Mou Xianyou,et al. Study on the pool ice growth-decay and numerical modeling[J]. Journal of Hydraulic Engineering,2O16,47 (11): 1352-1362.]   
[18]Fu C,Popescu I,Wang C,et al. Challenges in modelling river flow and ice regime on the Ningxia-Inner Mongolia reach of the Yellow River,China[J].Hydrology & Earth System ences,2014,18(3): 1225-1237.   
[19] 李超.黄河(内蒙古段)河冰生消演变特性及数值模拟研究[D]. 呼和浩特:内蒙古农业大学,2015.[Li Chao.Study on Characteristics River Ice Evolution and Numerical Simulation of The Yellow River (Inner Mongolia Reach)[D].Hohhot: Inner MongoliaAgricultural University,2015.]   
[20]Beltaos S,GerardR,Prowse T,et al. River Ice Jams[M]. Burlington, Canada,Water Resources Publication,1995.   
[21]Lindenschmidt K-E,Sydor M,CarsonR W.Modelling ice cover formation of a lake-river system with exceptionally high flows (Lake St.Martin and Dauphin River,Manitoba)[J]. Cold Regions Science and Technology,2012,82:36-48.   
[22]Lindenschmidt K-E.Numerical Modelling of River-Ice Processes (Model Description),River Ice Processesand Ice Flood Forecasting[M]. Saskatoon, SK,Canada, Springer,202O:121-143.   
[23]Lindenschmidt K-E. Using stage frequency distributions as objective functions for model calibration and global sensitivity analyses [J].Environmental Modelling and Software,2O17,92:169-175.   
[24]Lindenschmidt K-E,Das A,Rokaya P,et al.Ice-jam flood risk assessment and mapping[J]. Hydrological Processes,2O16,30(21): 3754-3769.   
[25]Nezhikhovskiy R A.Coefficients of roughness of bottom surface on slush-ice cover[J].In Soviet Hydrology,1964:127-150.

# Numerical simulation of the ice jam stage in the Sanhuhekou bendreachoftheYellowRiver

XU Kaili1²，LYU Haishen’²，LIU Minwen²， ZHU Yonghua',2, HE Chaolul²，XIE Bingqi³ (1.State KeyLaboratoryof Hydrology-Water Resources and Hydraulic Engineering,Hohai University,Nanjing   
210098,Jiangsu,China; 2.CollgeofHydrology and WaterResources,Hohai University,Nanjing 21098,Jiangsu,   
China;3.Pearl River Water Resources Research Institute,Pearl River Water Resources Commission,Guangzhou 510630, Guangdong, China)

Abstract: In this study,the open-source numerical river ice model RIVICE was used to simulate the ice jam water level in the Sanhuhekou bend reach of the Yelow River during the break-up period. Its parameters were then subjected tosensitivityanalysis.Flow,water level,and ice th ickness wereobtained from the Hydrological Yearbook.Results show that the RIVICE model can be utilized to simulate the ice jam water level in the break-up period.The backwater level of an ice jam is highly sensitive to the upstream boundary discharge, indicating the importance of water conservancy projects in flow regulation. Therefore,the established model can provide a scientific theoretical basis for managing water conservancy projects and ice flood control.

Keywords: Sanhuhekou bend reach of the Yellow River; ice jam water level; RIVICE model