# 根系水分胁迫响应函数对土壤水及作物生长动态和产量模拟影响的研究

王铁英¹，王仰仁¹，柴俊芳²，郭文俊²

（1.天津农学院水利工程学院，天津300392;2.山西省洪洞县霍泉水利事务中心灌溉试验站，山西 临汾031600)

摘要：为探究根系水分胁迫响应函数对农田水分动态及产量模拟的影响，基于Richards方程和PS123作物生长模型分别进行了土壤水分动态和小麦产量的模拟，对比分析了VG(S型曲线）、MP(凹凸型曲线)及LS(S型曲线)3种水分胁迫响应函数。采用山西省霍泉站(3a)及潇河站(2a)的试验资料对模型中的土壤水力特征参数、水分胁迫响应函数参数进行反演，确定最优的参数值，得到了土壤含水率、蒸散量及籽粒产量的模拟结果。结果表明：(1)VG、MP及LS函数条件下的土壤水分及产量模拟结果均较好，回归估计标准误差(RMSE)值在0.021\~0.036之间，模拟值与实测值间的$R$ 检验达到了极显著水平;对于霍泉站，VG、MP、LS函数条件下，土壤含水率模拟值与实测值的平均相对误差分别为 $6 . 3 7 \% . 8 . 2 6 \%$ 及 $7 . 1 8 \%$ ，相关性系数值最小为0.7814,模拟产量的平均相对误差值分别为 $8 . 7 3 \% . 8 . 4 0 \%$ 及 $8 . 4 2 \%$ ;对于潇河站，土壤含水率模拟值与实测值的平均相对误差结果普遍大于霍泉站，最大为 $1 2 . 4 7 \%$ 。(2）土壤水分动态模拟，S型曲线的水分胁迫响应函数较凹凸型曲线的水分胁迫响应函数表现出了更好的效果，其中使用VG函数模拟的平均相对误差较小，模拟的蒸散量更接近于实测值。(3）产量模拟,3种水分胁迫响应函数差异不明显。综上，VG函数是一种精度较高的根系水分胁迫响应函数，且模型简洁、方便;改进的LS函数能够提高模拟精度，但模型的稳定性有待近一步研究。

关键词：水分胁迫；根系吸水模式；农田水分模拟；产量模拟；参数反演

# 文章编号：

根系水分胁迫响应函数被定义为实际根系吸水速率与最大根系吸水速率之比，是研究干旱胁迫对根系吸水影响的重要参数。根系吸水是植物获取水分、养分、进行光合作用的基础，也是联系水循环和碳循环的纽带[]。在土壤水分动态及产量的模拟中,根系吸水模型是极为重要的组成部分[2],模拟效果直接影响土壤水分动态模拟及产量模拟精度[3]。宏观条件[4-5]下的经验模型[6常用于模拟根系吸水过程，模型主要考虑根系吸水同根系密度分布、土壤剖面含水率、蒸腾速率的关系[7-8]。作物的根系吸水速率往往难于直接测试,因此康绍忠等[2]直接分析了土壤剖面充分湿润时的根系吸水速率随深度的变化规律，并依据土壤-植物的水平衡关系得出了土壤剖面均匀湿润时的根系吸水速率模型，用于计算最大根系吸水速率，在实际应用中较为简单。

土壤剖面含水率对根系吸水有直接影响，当土壤含水率降低时，根系吸水受到抑制，吸水速率小于充分湿润时的吸水速率。根系水分胁迫响应函数用于反映土壤水分胁迫对根系吸水的抑制作用，使根系吸水模型可以适用于干旱、半干旱条件，朱永华等[8引入土壤湿度有关的参数改进了根系吸水模型，得出了干旱荒漠区域的根系吸水模型。根系水分胁迫响应函数主要表征为土壤含水率或土壤基质势的分段函数，有线性[9-10]和非线性["两类。

线性函数表明根系吸水速率随土壤基质势或土壤含水率的下降呈线性减小趋势，其中Feddes 等[12]所提出的分段线性函数最为典型。非线性函数分为S型函数[13]和凹凸型函数 $^ { [ 1 4 - 1 5 ] } 2$ 种，二者均表明根系吸水速率随着土壤基质势或土壤含水率变化是一个渐变的过程,其中分别以Van Genuchten模型[16]和康绍忠等建立的适用于小麦根系吸水模式的指数模型较为简便、典型。与线性函数相比，非线性的土壤水分胁迫响应函数在大多数情况下能更加准确地表征土壤水分对根系吸水的影响[17]。凹凸型响应函数在分段连接处会出现变化速率突变，为避免该现象本研究提出了以土壤含水率为变量的S型水分胁迫响应函数模型，与另外2种典型的根系水分胁迫响应函数进行对比分析，该对比在作物水模拟过程中完成。

作物水模型主要用于对作物生长发育动态、产量进行模拟，是定量化评价灌水施肥等田间管理措施的重要手段[18],其模拟对象主要为土壤水、土壤氮素和作物生长。土壤水的模拟主要是土壤水分运动与蒸散过程，不同的模型采用方法不同，如在水分模拟中,WOFOST[19]、DSSAT[20] $\mathrm { P S } 1 2 3 ^ { [ 2 1 - 2 2 ] }$ 等模型采用计算较为简单的水平衡法,而HYDRUS- $\cdot 1 \mathrm { D } ^ { [ 2 3 - 2 4 ] }$ ）DAISY[25]等模型则采用了以Richards[7方程为基础的土壤水动力学模型，更适用于边界条件复杂的环境且计算精度较高[26]。作物蒸散模拟中大部分模型采用了Penman-Monteith方程计算参考作物蒸散量，通过作物系数计算潜在蒸散量，最后使用叶面积指数将潜在蒸散量分为潜在蒸腾量和潜在蒸发量，实际蒸发量可作为Richards方程的上边界条件，潜在蒸腾量输入作物根系吸水模型作为实际根系吸水的驱动。作物生长模拟过程是从光合有效辐射出发，考虑光、温、水和养分等胁迫，描述光合作用及干物质积累、分配和转化过程。目前，既有较通用的WOFOST、DSSAT、DAISY等模型，也有针对不同作物的特定模型，如用于模拟谷类作物的CE-RES模型。以荷兰DeWit教授为首的研究小组，先后建立和完善了在不同生产力水平下的作物生长模拟模型，以PS123模型为代表，更多地强调作物的共性，与作物的生理生态机理结合较紧，在我国的适应性方面已有良好的工作基础[28],如毛振强等[29]以河北曲周县30a的气象数据为依据，应用PS123模型分析了该地区夏玉米的需水量和优化灌溉方案，对指导当地玉米生产具有重要意义。

PS123模型是联系水分与作物生长关系的主要环节，其对于水分动态模拟采用简化的水平衡法，对根系吸水只是依据机理进行了较为简单的线性化处理,需要进一步完善[30]。鉴于此,本研究选用PS123作物生长模型与Richards方程建立了作物产量与水分关系，并采用机理性较强的根系吸水模型。采用规划求解方法对模型参数进行率定，对不同形式水分胁迫响应函数的表征效果进行了评价。

# 1研究区概况

# 1.1试验站概况

以冬小麦作为研究对象，以山西霍泉、潇河两处试验站的试验资料为依据。霍泉站位于霍泉灌区中上游的洪洞县广胜寺镇东安村( $\mathrm { 1 1 1 ^ { \circ } 4 6 ^ { \prime } 2 1 ^ { \prime \prime } E }$ ，$3 6 ^ { \circ } 1 7 ^ { \prime } 3 5 ^ { \prime \prime } \mathrm { N } .$ ，海拔高程 $5 2 9 \mathrm { m }$ ，该地所属气候为暖温带大陆性气候，土壤质地为轻壤土， $0 { \sim } 1 0 0 ~ \mathrm { c m }$ 土壤容重 $1 . 4 6 \ \mathrm { g \cdot c m } ^ { - 3 }$ ,田间持水率为 $0 . 3 5 9 2 { \mathrm { ~ c m } } ^ { 3 } \cdot { \mathrm { c m } } ^ { - 3 }$ 。潇河试验站位于晋中市榆次区杨村( $\langle 1 1 2 ^ { \circ } 4 1 ^ { \prime } 3 1 ^ { \prime \prime } \mathrm { E }$ ，$3 7 ^ { \circ } 3 9 ^ { \prime } 0 6 ^ { \prime \prime } \mathrm { N } .$ ，海拔高程 $7 8 2 . 6 4 \mathrm { ~ m ~ }$ ,土质为重壤土， $0 \sim$ $1 0 0 \ \mathrm { c m }$ 土壤容重为 $1 . 4 2 \ \mathrm { g } \cdot \mathrm { c m } ^ { - 3 }$ ，田间持水率为$0 . 4 0 4 4 ~ \mathrm { c m } ^ { 3 } { \cdot } \mathrm { c m } ^ { - 3 }$ 。

模拟中取用了霍泉站2017—2019年与潇河站2004—2005年共5个站年的冬小麦试验资料（小麦生育期跨越冬季,本文中年为收获年），主要包括各年的气象数据、冬小麦生长发育期的干物质测试数据及土壤含水率实测数据。其中，土壤含水率测试方法，霍泉站为烘干法，潇河站为中子仪法。霍泉站为大田试验，小区面积为 $6 6 . 7 \mathrm { ~ m } ^ { 2 }$ ，潇河站采用了无底测坑,测坑面积为 $3 . 3 3 \mathrm { m } { \times } 2 \mathrm { m }$ 。

# 1.2试验处理选定

霍泉站与潇河站均为冬小麦水肥耦合试验。其中，霍泉站每年设置6个处理，潇河站每年设置10个处理。本研究仅在每年的试验处理中选取了高水、中水和零水处理用于模型参数的率定，详细处理信息见表1。由表可见，不同年份、处理间施肥数量有所不同，因此研究中土壤含水率、蒸散量和产量的变化为水肥双重影响下的结果，

# 干旱区地理

表1冬小麦水肥耦合试验处理基本信息  
Tab.1 Basic information of winter wheat water and fertilizer coupling test treatment   

<html><body><table><tr><td rowspan="3">站名</td><td rowspan="3">年份</td><td rowspan="3">处理</td><td rowspan="3">灌水定额 /mm</td><td colspan="4">灌水时间(月-日)</td><td rowspan="3">底肥 /kg·hm-2</td><td rowspan="3">追肥 /kg·hm-²</td></tr><tr><td>1次</td><td>2次</td><td>3次</td><td>4次</td></tr><tr><td>霍泉站</td><td>2017</td><td>高水</td><td>75</td><td>11-22</td><td>03-22</td><td>05-08</td><td>05-22</td><td>600</td><td>450</td></tr><tr><td></td><td></td><td>中水</td><td>75</td><td>11-22</td><td>03-22</td><td>05-22</td><td>1</td><td>600</td><td>300</td></tr><tr><td></td><td></td><td>零水</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>600</td><td>1</td></tr><tr><td></td><td>2018</td><td>高水</td><td>75</td><td>03-15</td><td>04-18</td><td>05-12</td><td>05-31</td><td>900</td><td>563</td></tr><tr><td></td><td></td><td>中水</td><td>75</td><td>03-15</td><td>04-18</td><td>05-12</td><td>一</td><td>600</td><td>375</td></tr><tr><td></td><td></td><td>零水</td><td>1</td><td>1</td><td>1</td><td>1</td><td>一</td><td>1</td><td>1</td></tr><tr><td></td><td>2019</td><td>高水</td><td>75</td><td>03-26</td><td>04-22</td><td>05-22</td><td>1</td><td>1050</td><td>510</td></tr><tr><td></td><td></td><td>中水</td><td>75</td><td>03-26</td><td>05-08</td><td>一</td><td>1</td><td>750</td><td>345</td></tr><tr><td></td><td></td><td>零水</td><td>1</td><td>一</td><td>一</td><td>1</td><td>一</td><td>1</td><td>1</td></tr><tr><td>潇河站</td><td>2004</td><td>高水</td><td>75</td><td>12-11</td><td>04-19</td><td>05-07</td><td>05-29</td><td>750</td><td>225</td></tr><tr><td></td><td></td><td>中水</td><td>45</td><td>04-19</td><td>1</td><td>一</td><td>1</td><td>750</td><td>225</td></tr><tr><td></td><td></td><td>零水</td><td>1</td><td>一</td><td>一</td><td>一</td><td>一</td><td>750</td><td>1</td></tr><tr><td></td><td>2005</td><td>高水</td><td>75</td><td>12-01</td><td>04-02</td><td>05-11</td><td>05-31</td><td>1125</td><td>338</td></tr><tr><td></td><td></td><td>中水</td><td>45</td><td>04-20</td><td>1</td><td>一</td><td>1</td><td>750</td><td>225</td></tr><tr><td></td><td></td><td>零水</td><td>二</td><td>二</td><td>二</td><td>二</td><td>二</td><td>750</td><td>二</td></tr></table></body></html>

# 2 研究方法

# 2.1土壤水热耦合变化动态模拟

2.1.1土壤水热耦合动态模拟模型本研究在冬小麦生育期水分模拟的过程中考虑了温度变化，采用包含根系吸水项的Richards方程进行土壤水分动态模拟，以1d作为模拟时段，对距地表 $2 \mathrm { m }$ 内的土壤含水率及热流进行分层模拟( $2 0 ~ \mathrm { c m }$ 一层），依据STVF理论模式31分析土壤温度变化对土壤水分运动特性参数的影响。采用尚松浩等[16]给出的水热耦合方程模拟热流变化，该方程综合考虑了土壤水分迁移、热传导、水分相变等因素，相对于传统水热耦合方程，水、热方程间的耦合性大为减少，可以不考虑相变作用，只在计算时段末根据冻结曲线进行冰和未冻水含量的修正，有利于提高方程求解的迭代计算。

$$
\frac { \partial \theta } { \partial t } = \frac { \partial \theta } { \partial z } \bigg [ D ( \theta ) \frac { \partial \theta } { \partial z } \bigg ] - \frac { \partial K ( \theta ) } { \partial z } - S ( z , t )
$$

$$
C _ { \mathrm { e } } \frac { \partial T } { \partial t } = \frac { \partial } { \partial z } \bigg [ \lambda _ { \mathrm { e } } \frac { \partial T } { \partial z } \bigg ] - U _ { \mathrm { e } } \frac { \partial T } { \partial z }
$$

$$
C _ { 1 } { = } L _ { \mathrm { f } } \rho _ { \mathrm { w } } { \frac { \mathrm { d } \theta _ { \mathrm { m } } } { \mathrm { d } T } }
$$

$$
C _ { \mathrm { e } } { = } C _ { \mathrm { v } } { + } C _ { 1 }
$$

$$
\lambda _ { \mathrm { { e } } } = \lambda + D ( \theta _ { \mathrm { { u } } } ) C _ { 1 }
$$

$$
U _ { \mathrm { e } } = C _ { \mathrm { 1 } } \frac { \mathrm { d } K \big ( \theta _ { \mathrm { u } } \big ) } { \mathrm { d } \theta _ { \mathrm { u } } }
$$

$$
D ( \theta ) = K { \bigl ( } \theta { \bigr ) } { \biggl ( } { \frac { \mathrm { d } \theta } { \mathrm { d } h } } { \biggr ) } ^ { - 1 }
$$

$$
\theta \left( h \right) = \left\{ \begin{array} { l l } { \theta _ { \mathrm { r } } + \frac { \theta _ { \mathrm { n } } - \theta _ { \mathrm { r } } } { \left[ 1 + \left( - \alpha h \right) ^ { n } \right] ^ { \frac { n - 1 } { n } } } } & { \ h < h _ { \mathrm { s } } } \\ { \theta _ { \mathrm { s } } } & { \ h \geqslant h _ { \mathrm { s } } } \end{array} \right.
$$

$$
K ( \theta ) = \{ K _ { \mathrm { s } } \Bigg ( \frac { \theta - \theta _ { \mathrm { r } } } { \theta _ { \mathrm { s } } - \theta _ { \mathrm { r } } } \Bigg ) ^ { 0 . 5 } \Bigg \{ 1 - \Bigg [ 1 - \Bigg ( \frac { \theta - \theta _ { \mathrm { r } } } { \theta _ { \mathrm { n } } - \theta _ { \mathrm { r } } } \Bigg ) ^ { \frac { 1 } { m } } \Bigg ] ^ { m } \Bigg \} \qquad \theta < \theta _ { \mathrm { s } }
$$

式中： $\theta$ 为土壤体积含水率 $\left( \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 } \right) ,$ ； $\mathbf { \Psi } _ { t } \mathbf { \Psi } _ { t }$ 为时间（204号 $( \mathrm { m i n } \big |$ ） $D ( \theta )$ 为土壤非饱和扩散率 $( \mathrm { c m } ^ { 2 } \cdot \mathrm { m i n } ^ { - 1 } ,$ ，根据式(7)计算,其中 $\frac { \mathrm { d } \theta } { \mathrm { d } h }$ 为比水容量, $\theta$ 与 $h$ 的关系由土壤水分特征曲线确定(式8) $\left[ 1 6 , 2 4 , 2 6 \right]$ $K ( \theta )$ 为土壤非饱和导水率( $( \mathrm { c m } \cdot \mathrm { m i n } ^ { - 1 }$ ),采用目前普遍使用的式(9)计算[16.23,26], $z$ 为深度 $( \mathrm { c m } ) ; S ( z , t )$ 为根系吸水速率 $( \operatorname* { m i n } ^ { - 1 } )$ ）;$T$ 为土壤温度 $( \mathrm { { ^ { c ) } } { ; } } L _ { \mathrm { { f } } }$ 为融化潜热,研究中取 $3 3 5 \mathrm { J \cdot g ^ { - 1 } }$ $\theta _ { \mathrm { { m } } }$ 为相应土壤负温度条件下可能的最大未冻水含量$\left( \mathrm { { c m } } \cdot \mathrm { { c m } } ^ { - 3 } \right.$ ）； $C _ { \mathrm { v } }$ 为土壤容积比热 $\left( \mathbf { J } \cdot \mathbf { g } ^ { - 1 } \cdot ^ { \circ } \mathbf { C } ^ { - 1 } \right)$ ， $\textstyle C _ { \mathrm { v } } = 1 . 9 2$ $( 1 - \theta _ { \mathrm { s } } ) \substack { + 4 . 1 8 \theta ^ { [ 3 2 ] } }$ $\lambda$ 为土壤体积热导率 $\left( \mathbb { W } \cdot \mathrm { c m } ^ { - 3 } \bullet ^ { \circ } \mathrm { C } ^ { - 1 } \right)$ ，$\lambda { = } C , D _ { \mathrm { h } } , D _ { \mathrm { h } }$ 为土壤热扩散率[16], $D _ { \mathrm { h } } { = } 0 . 0 0 2 { + } 0 . 0 1 1 5 \theta { + }$ $0 . 0 1 0 3 \theta ^ { 0 . 5 }$ · $\theta _ { \mathrm { u } }$ 为土壤未冻水体积含水率( $( \mathrm { c m } \cdot \mathrm { c m } ^ { - 3 } )$ ，未冻水含量可以利用脉冲核磁共振法、量热法、时域反射法等方法测定[16],其测定过程较为复杂，本文直接引用了尚松浩给出的冻结特征曲线[16]; $\theta _ { \mathrm { s } }$ 为饱和土壤含水率 $\left( \mathrm { c m } { \cdot } \mathrm { c m } ^ { - 3 } \right) ; C _ { 1 } \vphantom { \sqrt { 1 0 } } , C _ { \mathrm { e } } \vphantom { \sqrt { 1 0 } } , U _ { \mathrm { e } }$ 分别为冻土的相变热容量、等效体积热容量、等效热导率及等效对流速度，由 $\theta _ { \mathrm { m } } \setminus \theta _ { \mathrm { u } } \setminus \lambda \setminus D ( \theta ) \setminus K ( \theta )$ 通过公式计算得到。 $\theta _ { \mathrm { r } }$ 为残余土壤含水率( $( \mathrm { c m } \cdot \mathrm { c m } ^ { - 3 } )$ ； $h$ 为土壤基质势 ${ \bigl ( } \operatorname { c m } { \bigr ) } ; \alpha , n$ 为土壤水分特征曲线形状参数,其值通过参数反演确定； $m { = } 1 { - } 1 / n ; h _ { \mathrm { s } }$ 为经验参数（ $( \mathrm { c m } )$ ，本研究取值为 $0 { ; } K _ { \mathrm { s } }$ 为土壤饱和导水率 $( \mathbf { c } \mathbf { m } \cdot \mathbf { m } \mathbf { \dot { n } } ^ { - 1 } ,$ ，其值通过参数反演确定； $\theta _ { \mathrm { n } }$ 为模型曲线外插参数，数值比0稍大。

上述水热耦合方程与初始条件、边界条件一起组成完整的水热耦合动态模拟模型。初始条件、边界条件采用王仰仁33论文中给出的计算方法，初始条件中土壤含水率为播种日土壤剖面含水率，气温根据自动气象站测得，地温采用地温温度计测得；上边界条件中地表通量等于棵间土壤蒸发量[33],地表温度根据空气温度与地表温度的经验关系计算；下边界条件中的温度及土壤含水率因在小麦生育期内变化较小,因而采用第一类边界条件[34]。利用差分方法求解，可得分层土壤含水率及温度随时间的变化过程。

2.1.2根系吸水模型采用潜在的根系吸水速率与水分胁迫响应的乘积计算根系的实际吸水速率[2]。

$$
S ( z , t ) = S _ { 0 } ( z , t ) \beta
$$

式中： $S ( z , t )$ 为根系吸水速率（ $\cdot \mathrm { m i n } ^ { - 1 }$ ； $S _ { 0 } ( z , t )$ 为土壤充分湿润条件下的根系吸水速率 $( \operatorname* { m i n } ^ { - 1 } )$ ，采用Novak[35]给出公式计算，见式(11)； $\beta$ 为水分胁迫响应函数，是以土壤基质势或土壤含水率为自变量的函数。

$$
S _ { 0 } ( z , t ) = \mathrm { T p } ( t ) \frac { \delta \mathrm { e } ^ { \left[ - \delta ( z / z _ { \mathrm { r } } ) \right] } } { z _ { \mathrm { r } } \left[ 1 - \mathrm { e } ^ { - \delta } \right] }
$$

式中： $\mathrm { T p } ( t )$ 为作物潜在蒸腾速率 $\bf { \chi } _ { c m } . \min ^ { - 1 } ,$ ，是作物潜在蒸散量的一部分，可根据经验公式计算得到[3]；$z$ 为深度 $( \mathrm { c m } ) { \scriptstyle { ; z _ { \mathrm { r } } } }$ 为根系层深度( $( \mathrm { c m } )$ ；8为经验系数，与作物种类有关，本文参照由懋正1的研究取 ${ \delta } \mathrm { = } 3 . 8$ O

本研究对3种形式的水分胁迫响应函数进行了对比分析。

（1）以土壤基质势为因变量的VanGenuchten函数[4（以下称为VG)。

$$
\beta ( h ) = \frac { 1 } { 1 + \displaystyle \left[ \frac { h ( z ) + \pi ( z ) } { h _ { 5 0 } } \right] ^ { P } }
$$

式中： $\beta ( h )$ 为以土壤基质势为自变量的水分胁迫响应函数，呈S形状变化； $h ( z )$ 为地面以下深度 $z$ 处的土壤基质势( $\bf ( \mathrm { c m ) }$ $\pi ( z )$ 为土壤溶质势，本研究未考虑溶质影响，因此取 $\pi ( z ) { = } 0 ; P$ 为经验系数，通过参数反演确定； $h _ { 5 0 }$ 为作物蒸腾量减小到最大可能蒸腾量 $5 0 \%$ 时所对应的土壤水势( $\mathrm { ( c m ) }$ ，其值通过参数反演确定。

(2）以土壤含水率为因变量的幂函数4（以下称为MP)。

$$
\begin{array} { r } { \beta ( \theta ) = \left\{ \begin{array} { l l } { 1 \qquad } & { \theta > \theta _ { \mathrm { j } } } \\ { \left( \mathrm { A W } \right) ^ { A } } & { \theta _ { \mathrm { w p } } \leqslant \theta \leqslant \theta _ { \mathrm { j } } } \\ { 0 } & { \theta < \theta _ { \mathrm { w p } } } \end{array} \right. } \end{array}
$$

$$
\mathrm { A W } = { \frac { \theta _ { z } - \theta _ { \mathrm { w p } } } { \theta _ { \mathrm { j } } - \theta _ { \mathrm { w p } } } }
$$

式中： $\beta ( \theta )$ 为以土壤含水率为自变量的水分胁迫响应函数，呈凹(凸)形状变化;AW为有效土壤含水率的相对值； $\theta _ { z }$ 为 $z$ 深度的土壤含水率 $( \mathrm { c m } \cdot \mathrm { c m } ^ { - 3 } ) ; \theta _ { \mathrm { j } }$ 为临界土壤含水率 $( \mathrm { c m } \cdot \mathrm { c m } ^ { - 3 } . $ ）； $\theta _ { \mathrm { w p } }$ 为凋萎土壤含水率$( \mathrm { c m } \cdot \mathrm { c m } ^ { - 3 } , $ ; $A$ 为经验系数； $\theta _ { \mathrm { j } } \setminus \theta _ { \mathrm { w p } }$ 和 $A$ 通过参数反演确定。

(3）以土壤含水率为因变量的改进型分段函数，式(13)在分段连接点处会出现速率突变，不符合作物生长的连续渐变过程，鉴于此引入参数 $B , C$ 消除速率突变，形成S型曲线，由此给出了LS,计算公式如下：

$$
\beta ^ { \prime } ( \theta ) = \{ \begin{array} { l l } { 1 } & { \theta > \theta _ { \mathrm { j } } } \\ { 1 + ( \frac { 1 } { \mathrm { A W } ^ { B } } - 1 ) ^ { C } ] ^ { - 1 } } & { \theta _ { \mathrm { w p } } \leqslant \theta \leqslant \theta _ { \mathrm { j } } } \\ { 0 } & { \theta < \theta _ { \mathrm { w p } } } \end{array} 
$$

式中： $\beta ^ { \prime } ( \theta )$ 为改进线型的水分胁迫响应函数； $B , C$ 为经验系数，通过参数反演确定。

# 2.2冬小麦产量模拟

采用PS123作物生长模型进行冬小麦产量模拟，模拟过程中除了考虑有效太阳辐射和温度外，同时考虑有效水分和有效养分胁迫的影响。模拟产量利用大田作物总的同化潜力表示[36],计算过程如下：

$$
\mathrm { F g a s s } _ { i } = \mathrm { F g c } _ { i } \times 3 0 / 4 4 \times \mathrm { F W } _ { i } \times \mathrm { F N } _ { i } \times \mathrm { C V F }
$$

式中：Fgass:为大田作物总同化率 $\left( \mathbf { k g } \cdot \mathbf { h m } ^ { - 2 } \cdot \mathbf { d } ^ { - 1 } \right)$ $\mathrm { F g c } _ { i }$ 为密闭参照作物总 $\mathrm { C O } _ { 2 }$ 吸收率 $\left( \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 } \right)$ ,根据日长、温度、叶面积指数、消光系数、光能利用效率、冠层顶部截获的光合有效辐射计算[30]； $3 0 / 4 4$ 为 $\mathrm { C H } _ { 2 } \mathrm { O }$ 与 $\mathrm { C O } _ { 2 }$ 的分子量之比； $\mathrm { F W } _ { i }$ 为水分胁迫系数；FN为养

# 干旱区地理

分胁迫系数，分别采用式(17)和式(18)计算；CVF为光合产物转化效率，通过参数反演得到； $i$ 为生长天数。

$$
\mathrm { F W } _ { i } = \left\{ \begin{array} { l l } { 0 } & { \frac { \mathrm { E T a } _ { i } } { \mathrm { E T p } _ { i } } < k _ { 2 } } \\ { \left( \frac { \mathrm { E T a } _ { i } } { \mathrm { E T p } _ { i } } \right) ^ { \lambda _ { 1 } } } & { k _ { 2 } \leqslant \frac { \mathrm { E T a } _ { i } } { \mathrm { E T p } _ { i } } \leqslant k _ { 1 } } \\ { 1 } & { \frac { \mathrm { E T a } _ { i } } { \mathrm { E T p } _ { i } } > k _ { 1 } } \end{array} \right.
$$

$$
\mathrm { F N } _ { i } = \left\{ \begin{array} { l l } { \left( \frac { \mathrm { S r } _ { i } } { \mathrm { S m } _ { i } } \right) ^ { \lambda _ { 2 } } } & { \ \frac { \mathrm { S r } _ { i } } { \mathrm { S m } _ { i } } < k _ { 3 } } \\ { 1 } & { \ \frac { \mathrm { S r } _ { i } } { \mathrm { S m } _ { i } } \geqslant k _ { 3 } } \end{array} \right.
$$

式中： $\mathrm { E T a } _ { i }$ 为水分胁迫下的作物实际蒸散量 $\left( \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 } \right)$ ;$\mathrm { E T p } _ { i }$ 为作物潜在蒸散量( $\mathrm { [ } \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \mathrm { ] }$ ）； $\mathrm { S r } _ { i }$ 为根系吸氮量$\left( \mathbf { k g } \cdot \mathbf { h m } ^ { - 2 } \cdot \mathbf { d } ^ { - 1 } \right)$ ，根据实际根系吸水量与土壤水溶液氮素浓度的乘积计算[33]; $\mathrm { S m } _ { i }$ 为植株最低限度含氮量$\left( \mathrm { k g } \bullet \mathrm { h m } ^ { - 2 } \bullet \mathrm { d } ^ { - 1 } \right) ; \lambda _ { 1 } \ 、 \lambda _ { 2 }$ 分别为水分亏缺敏感指数和养分亏缺敏感指数； $\smash { k _ { 1 } \leqslant k _ { 2 } \leqslant k _ { 3 } }$ 为经验系数，均通过参数反演得到。

# 2.3参数反演

本研究利用Excel规划求解工具中的演化算法反演确定待求参数。对霍泉站，将3a共9个处理数据放在一起进行参数反演；对潇河站，将2a共6个处理数据放在一起进行参数反演。反演参数主要包括土壤水分动态模拟中的参数和小麦产量模拟中的参数。

（1）土壤水分动态模拟参数反演，以实测土壤含水率及模拟土壤含水率误差平方和最小为目标函数，见式（19)：

$$
\operatorname* { m i n } _ { j = 1 } ^ { m } \mathrm { S W } _ { j } , \ : \ : \sharp \sharp \ : \mathrm { S W } _ { j } = \left( \sum _ { i = 1 } ^ { p _ { j } } ( \theta _ { i j } - \theta ^ { \prime } { } _ { i j } ) \right) _ { j }
$$

式中：SW为第 $j$ 个处理所有模拟土壤含水率与实测土壤含水率的误差平方和； $\theta _ { i j }$ 为实测土壤含水率（2号 $( \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 } )$ ； $\theta ^ { \prime } { } _ { i j }$ 为模拟土壤含水率( $( \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 }$ ） $p _ { j }$ 为 $j$ 处理中实测土壤含水率的个数, $i { = } 1 , 2 , \cdots , p _ { j } ; j { = } 1$ $2 , \cdots , m$ ,其中 $m$ 为规划求解所用到处理个数,霍泉站 $\scriptstyle { m = 9 }$ ，潇河站 $m { = } 6$ 售

待定参数包括土壤水分特性参数 $\smash { \theta _ { \mathrm { s } } \vphantom { \theta _ { \mathrm { r } } \Omega _ { 0 } } \theta _ { \mathrm { r } } \vphantom { \theta _ { \mathrm { r } } \Omega _ { 0 } } \Omega _ { 0 } \vphantom { A _ { \mathrm { r } } \Omega _ { 0 } } \Omega _ { \mathrm { s } } }$ 以及水分胁迫参数 $h _ { 5 0 } \ 、 P \ 、 \theta _ { \mathrm { w p } } \ 、 \theta _ { \mathrm { j } } \ 、 A \ 、 B \ 、 C \ 。$ 。演化时，根据已有的经验参数[31],参照试验站的土壤质地确定3组参数初始值，依次进行演化计算，可获得3组待定参数，选定其中土壤含水率拟合误差最小的一组参数值作为初始值，再进行演化计算，当参数不再变化时停止演化计算。

(2）冬小麦生长动态及产量模拟参数反演，以茎、叶、籽粒模拟值与实测值误差平方和最小为目标函数，见式(20)：

$$
\begin{array} { r l r } {  { \operatorname* { m i n } _ { j = 1 } ^ { m } \mathrm { S Y } _ { j } } } \\ & { } & { \mathrm { S Y } _ { j } = [ \sum _ { o = 1 } ^ { e _ { j } } ( \mathrm { Y E } _ { o j } - \mathrm { Y E ^ { \prime } } _ { o j } ) ^ { 2 } + \sum _ { q = 1 } ^ { g _ { j } } ( \mathrm { Y J } _ { q j } - \mathrm { Y J ^ { \prime } } _ { q j } ) ^ { 2 } + \sum _ { v = 1 } ^ { l _ { j } } ( \mathrm { Y L } _ { v j } - \mathrm { Y L ^ { \prime } } _ { v j } ) ^ { 2 } ] _ { j } } \end{array}
$$

式中：SY为第 $j$ 个处理中实测干物质重与模拟干物 质重的误差平方和;YE、YJ、YL分别为实测叶、茎、 籽粒干重 $( \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } ) ; \mathrm { Y E } ^ { \prime } \cdot \mathrm { Y J ^ { \prime } } \cdot \mathrm { Y L } ^ { \prime }$ 分别为模拟叶、 茎、籽粒干重 $\left( \mathbf { k g } \cdot \mathbf { h m } ^ { - 2 } \right) ; e _ { j } \mathbf { \lambda } , g _ { j } \mathbf { \lambda } , l _ { j }$ 分别为 $j$ 处理中叶、 茎、籽粒实测干重样本的个数, $o { = } 1 , 2 , \cdots , e _ { j } , q { = } 1 .$ $2 , \cdots , g _ { j } , v \mathrm { = } 1 , 2 , \cdots , l _ { j \circ }$

可变参数包括水分胁迫系数参数 $( k _ { 1 } , k _ { 2 } , \lambda _ { 1 } )$ 养分胁迫系数参数 $( k _ { 3 } , \lambda _ { 2 } )$ 及光合产物转化效率(CVF)。为了获得更为准确的产量模拟结果，在式(20)的基础以产量模拟值与实测值误差平方和最小为目标(式21)，进一步进行参数反演分析。

$$
\mathrm { Y L } _ { j } = \operatorname* { m i n } \sum _ { j = 1 } ^ { m } \Bigl ( \mathrm { Y L } _ { j } ^ { * } - \mathrm { Y L } _ { \ j } ^ { \prime } \Bigr ) ^ { 2 }
$$

式中： $\mathrm { Y L } _ { j } ^ { * }$ 为处理 $j$ 收获时实测产量 $\left( \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } \right.$ ）； $\mathrm { Y L } _ { \textit { j } } ^ { \prime }$ 为j处理模拟产量 $\left( \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } \right)$ ）

# 2.4拟合精度评价

采用回归估计标准误差(RMSE）、相对误差（RE）、相关性系数 $\left( r \right) ^ { \left[ 3 8 \right] }$ 对土壤含水率的模拟结果进行评价， $\boldsymbol { r }$ 值越大，表明模型拟合效果越好，RMSE、RE值越小，表明模拟值的精度越高。采用相关性系数对地上干物质的拟合情况进行评价，因收获时产量数据较少，采用相对误差对模拟产量结果进行评价，并利用 $F$ 检验对不同水分胁迫响应函数模拟的产量进行差异性检验

# 3结果与分析

# 3.1水分胁迫响应函数对 $\mathbf { 0 { \sim } 6 0 ~ c m }$ 土壤水分动态模 拟的影响

通过式(19)进行参数反演优化，取最优演化结果，见表2、表3。由表可见，不同的水分胁迫响应函数条件下，利用试验资料反演得到的土壤水力特征参数、水分胁迫响应函数参数，没有明显的差异，且均在合理范围内[39],如θ均大于田间持水率，且不超过0.5，表明了反演参数的合理性。

利用反演的参数，可以得到不同土壤含水率模拟结果，对模拟值和实测值进行RMSE、RE和 $r$ 的对比分析，结果见表4及图1。由图表可见，不同水分胁迫响应函数条件下模拟结果的显著性检验均达到极显著水平，相关性系数r最小为0.7196，RMSE在 $0 . 0 2 1 7 { \sim } 0 . 0 3 6 3$ 之间,表明土壤含水率模拟结果与实测值具有非常好的一致性。从霍泉站土壤含水

# 表2土壤水力特征参数反演结果

Tab.2 Inversion results of soil hydraulic characteristic parameters   

<html><body><table><tr><td>站名</td><td>模型</td><td>0/cm³·cm-3</td><td>0/cm³·cm-3</td><td>α/cm-1</td><td>n</td><td>K/cm·d-1</td></tr><tr><td rowspan="3">霍泉站</td><td>VG</td><td>0.4468</td><td>0.0066</td><td>0.0076</td><td>1.3769</td><td>9.3486</td></tr><tr><td>MP</td><td>0.4460</td><td>0.0033</td><td>0.0245</td><td>1.6078</td><td>5.5227</td></tr><tr><td>LS</td><td>0.4833</td><td>0.0095</td><td>0.0073</td><td>1.8180</td><td>2.7249</td></tr><tr><td rowspan="3">潇河站</td><td>VG</td><td>0.4900</td><td>0.0036</td><td>0.0128</td><td>1.4325</td><td>7.5811</td></tr><tr><td>MP</td><td>0.4502</td><td>0.0054</td><td>0.0279</td><td>1.4296</td><td>5.9857</td></tr><tr><td>LS</td><td>0.4618</td><td>0.0040</td><td>0.0303</td><td>1.5368</td><td>5.1511</td></tr></table></body></html>

注：VG、MP、LS分别为以土壤基质势为因变量的VanGenuchten函数、以土壤含水率为因变量的幂函数、以土壤含水率为因变量的改进型分段函数； $\theta _ { \mathrm { s } }$ 为饱和土壤含水率；0为残余土壤含水率； $a , n$ 为土壤水分特征曲线形状参数； $K _ { s }$ 为土壤饱和导水率。下同。

表33种水分胁迫响应函数参数反演结果  
Tab.3 Three kinds of moisture stress response function parameter inversion results   

<html><body><table><tr><td rowspan="2">站名</td><td colspan="2">VG</td><td colspan="3">MP</td><td colspan="4">LS</td></tr><tr><td>P</td><td>h50/cm</td><td>0/cm·cm-3</td><td>0wp/cm·cm-³</td><td>A</td><td>0/cm³·cm-3</td><td>0wp/cm³·cm-³</td><td>B</td><td>C</td></tr><tr><td>霍泉站</td><td>1.98</td><td>1438.21</td><td>0.3586</td><td>0.1495</td><td>0.5931</td><td>0.3709</td><td>0.1680</td><td>0.5457</td><td>2.9801</td></tr><tr><td>潇河站</td><td>1.71</td><td>1059.34</td><td>0.2574</td><td>0.1781</td><td>0.5954</td><td>0.3781</td><td>0.1513</td><td>0.5427</td><td>2.6097</td></tr></table></body></html>

注： $h _ { 5 0 }$ 为作物蒸腾量减小到最大可能蒸腾量 $5 0 \%$ 时所对应的土壤水势； $\theta _ { \mathrm { j } }$ 为临界土壤含水率; $\theta _ { \mathrm { w p } }$ 为凋萎土壤含水率; $\textit { P } _ { \cdot } A , B , C$ 为经验系数。

# 表4不同水分胁迫响应函数模拟效果的评价

Tab.4Evaluationof simulation effectsofdifferent moisture stress response functions   

<html><body><table><tr><td>站名</td><td>模型</td><td>RMSE</td><td>RE范围/%</td><td>平均RE/%</td><td></td><td>样本数</td></tr><tr><td rowspan="3">霍泉站</td><td>VG</td><td>0.0217</td><td>0.05~23.82</td><td>6.37</td><td>0.8557</td><td>191</td></tr><tr><td>MP</td><td>0.0273</td><td>0.01~22.02</td><td>8.26</td><td>0.8150</td><td>191</td></tr><tr><td>LS</td><td>0.0223</td><td>0.04~27.27</td><td>7.18</td><td>0.7814</td><td>191</td></tr><tr><td rowspan="3">潇河站</td><td>VG</td><td>0.0363</td><td>0.13~38.46</td><td>12.47</td><td>0.8280</td><td>122</td></tr><tr><td>MP</td><td>0.0279</td><td>0.08~30.98</td><td>8.59</td><td>0.7820</td><td>122</td></tr><tr><td>LS</td><td>0.0314</td><td>0.09~40.62</td><td>10.33</td><td>0.7196</td><td>122</td></tr></table></body></html>

注：RMSE为回归估计标准误差;RE为相对误差;r为相关性系数，检验结果均达到极显著水平。下同。

率模拟结果看，VG最好，其次为LS,MP相对较差，表明S型胁迫响应函数的模拟结果优于凹凸型函数；对于S型曲线，基于土壤基质势的VG要好于LS。从潇河站模拟结果看，土壤含水率相对误差大于霍泉站，平均RE最大为 $1 2 . 4 7 \%$ ;对比3种胁迫响应函数，MP计算的RE数值最小，另外2种函数对应的相对误差均值较大；潇河站土壤含水率相对误差变化范围较大，主要原因可能是中子仪测定土壤含水率过程中存在率定误差，盛钰4的研究中也出现

了类似情况。

# 3.2水分胁迫响应函数对蒸腾量和蒸散量模拟的影响

水分胁迫响应函数对蒸腾量(Ta)及蒸散量(ETa)的模拟有明显的影响(表5)。由表5可见，使用VG模拟的根系吸水量及ETa明显高于另外2种水分胁迫响应函数条件下的模拟值，且更接近实测值，2个试验站非常一致，不同处理也表现出了相同结果。这里ETa的实测值是利用水量平衡法计算求得，计算过程中没有考虑水分的深层渗漏及深层土壤水的补给。对于高水、中水的处理，灌水后根系层含水率较高，水分向下运移的数量相对较多，因而灌水处理实测的ETa普遍大于模拟值;不灌水情况下，根系层含水率较低，对水分的吸持力较大，更容易发生深层土壤水的补给，因而霍泉站零水处理模拟蒸散量普遍大于实测值。

对于MP、LS2种水分胁迫响应函数，霍泉站采用MP模拟的Ta及ETa较低；而潇河站采用MP模拟结果明显大于LS模拟值。说明MP、LS受试验环境变化影响较大，存在不稳定性，相对而言VG使用效

0.35 (a)霍泉 0.35 (b)霍 MP 0.35 (c)霍泉  
/ 0.30 / 0.30 o/m 0.300.25 0.25 0.250.20 y=0.9806x 0.20 y=0.9435x 0.20 y=0.9945xR²=0.7323 R²=0.6642 R²=0.61060.15 0.15 1 0.150.15 0.20 0.25 0.30 0.35 0.15 0.20 0.25 0.30 0.35 0.15 0.20 0.25 0.30 0.35实测值/cmcm-3 实测值/cm·cm-3 实测值/cmcm-30.45 (d)潇河站(VG) 0.45 (e)潇河站(MP) 0.45 (f)潇河站(LS)  
/ 0030 R=-00.570x / 0.40 2=-00.61x .t 0.40 =-0.0.63280.25 0.30 0.300.20 0.25 卖 0.250.15 0.20 3 0.200.10 J 0.15 L 0.15 J0.10 0.20 0.30 0.40 0.10 0.20 0.30 0.40 0.10 0.20 0.30 0.40实测值/cmcm-3 实测值/cmcm-3 实测值/cmcm-3注：VG、MP、LS分别为以土壤基质势为因变量的Van Genuchten 函数、以土壤含水率为因变量的幂函数、以土壤含水率为因变量的改进型分段函数。下同。

Fig.1 Comparison of simulated and measured water content values of three moisture stress response functions

表5不同水分胁迫响应函数下模拟的蒸腾量及蒸散量  
Tab.5Simulated transpiration and evapotranspiration under different moisture stressresponse functions /mm   

<html><body><table><tr><td rowspan="2">站名</td><td rowspan="2">年份</td><td rowspan="2">模型</td><td colspan="2">高水</td><td colspan="2">中水</td><td colspan="2">零水</td></tr><tr><td>Ta</td><td>ETa</td><td>Ta</td><td>ETa</td><td>Ta</td><td>ETa</td></tr><tr><td>霍泉站</td><td>2017</td><td>VG</td><td>264.4</td><td>401.8</td><td>224.2</td><td>350.3</td><td>160.6</td><td>263.5</td></tr><tr><td></td><td></td><td>MP</td><td>201.6</td><td>312.9</td><td>170.2</td><td>275.5</td><td>111.6</td><td>186.7</td></tr><tr><td></td><td></td><td>LS</td><td>244.4</td><td>356.7</td><td>194.3</td><td>297.7</td><td>112.2</td><td>193.4</td></tr><tr><td></td><td></td><td>实测</td><td>1</td><td>502.0</td><td>1</td><td>400.2</td><td>1</td><td>261.3</td></tr><tr><td></td><td>2018</td><td>VG</td><td>248.2</td><td>383.3</td><td>241.7</td><td>359.7</td><td>150.1</td><td>246.7</td></tr><tr><td></td><td></td><td>MP</td><td>186.2</td><td>283.3</td><td>184.0</td><td>266.8</td><td>101.0</td><td>163.0</td></tr><tr><td></td><td></td><td>LS</td><td>226.1</td><td>331.9</td><td>221.5</td><td>310.6</td><td>104.8</td><td>176.6</td></tr><tr><td></td><td></td><td>实测</td><td>1</td><td>446.4</td><td>1</td><td>378.7</td><td>1</td><td>232.7</td></tr><tr><td></td><td>2019</td><td>VG</td><td>245.9</td><td>371.7</td><td>216.7</td><td>323.5</td><td>129.9</td><td>224.1</td></tr><tr><td></td><td></td><td>MP</td><td>182.6</td><td>271.5</td><td>157.4</td><td>233.5</td><td>85.7</td><td>150.7</td></tr><tr><td></td><td></td><td>LS</td><td>220.5</td><td>315.1</td><td>182.0</td><td>262.9</td><td>82.8</td><td>156.0</td></tr><tr><td></td><td></td><td>实测</td><td>1</td><td>404.9</td><td>1</td><td>374.8</td><td>1</td><td>235.1</td></tr><tr><td>潇河站</td><td>2004</td><td>VG</td><td>303.1</td><td>451.5</td><td>187.5</td><td>283.0</td><td>130.9</td><td>204.0</td></tr><tr><td></td><td></td><td>MP</td><td>270.2</td><td>391.8</td><td>146.4</td><td>224.2</td><td>92.0</td><td>157.2</td></tr><tr><td></td><td></td><td>LS</td><td>247.8</td><td>372.6</td><td>128.2</td><td>208.9</td><td>78.8</td><td>149.0</td></tr><tr><td></td><td></td><td>实测</td><td>1</td><td>529.6</td><td>1</td><td>297.3</td><td>1</td><td>235.6</td></tr><tr><td></td><td>2005</td><td>VG</td><td>337.1</td><td>461.1</td><td>187.3</td><td>234.7</td><td>162.1</td><td>206.0</td></tr><tr><td></td><td></td><td>MP</td><td>299.3</td><td>397.1</td><td>141.3</td><td>187.8</td><td>114.6</td><td>157.9</td></tr><tr><td></td><td></td><td>LS</td><td>276.0</td><td>380.1</td><td>126.1</td><td>180.6</td><td>96.0</td><td>145.9</td></tr><tr><td></td><td></td><td>实测</td><td>二</td><td>515.0</td><td>二</td><td>237.9</td><td>二</td><td>213.3</td></tr></table></body></html>

注：Ta为蒸腾量；ETa为蒸散量。

果好。

# 3.3水分胁迫响应函数对产量模拟的影响

采用PS123作物生长模型模拟作物产量，以霍泉站实测的地上干物质重数据反演了作物生长动态模拟参数，并给出了地上干物质模拟值与实测值的拟合程度检验结果，给出了最终产量模拟结果的相对误差(表6)。由表6可见，地上干物质重模拟值与实测值的相关性系数均在0.91以上， $\mid r \mid \mid$ 检验达到了极显著水平，表明模拟值与实测值具有很好的一致性，3种水分胁迫响应函数都可以获得高精度的模拟结果。

由表6,VG、MP及LS的平均RE分别为 $8 . 7 3 \%$ 、$8 . 4 0 \%$ 及 $8 . 4 2 \%$ ,产量模拟结果较为接近，图2给出了模拟产量与实测产量对比情况。由图可见，3种水分胁迫响应函数模拟值与实测值吻合程度较好，确定性系数在0.73以上，模拟点贴近1:1直线，表明产量模拟结果较好。对27个模拟产量样本按不同的水分胁迫响应函数进行单因素的 $F$ 检验，计算 $F$ 值为0.0032，小于 $F _ { 0 . 0 1 } ( 5 . 6 1 )$ ,表明根系水分胁迫响应函数确定性对最终产量模拟没有明显的影响。

# 4讨论

水分是制约干旱区作物生长的主要因素，根系水分胁迫响应函数是根系吸水模型中的重要组成部分。通过评估不同形式水分胁迫响应函数的表征效果，有助于完善对根系吸水过程的处理。在作物产量水分关系中，根系水分胁迫响应函数通过以下过程影响土壤水动态、作物生长动态和产量的模拟。

利用参考作物蒸散量、作物系数、叶面积指数可计算潜在蒸腾量、潜在蒸发量。其中，潜在蒸发量通过上边界条件影响土壤水分运动，潜在蒸腾量通过根系吸水影响实际蒸腾量，同时根系吸水量也用于计算根系吸氮量。水分胁迫响应函数形式不同时，模拟的根系吸水效果不同，如吴训等的研究表明，非线性胁迫响应函数相对于线性胁迫响应函数有更好的表征效果，本文进一步对比了非线性水分胁迫响应函数间表征效果，更好地反映了作物生长连续渐变过程。土壤基质势不受土壤分层影响，随深度变化是连续的，本文研究结果表明VG模拟水分变化优于另外2种函数。

作物吸收的水分、养分对生长发育及生物量积累具有显著影响，对此PS123模型将不同影响因子分为了不同的生产潜力水平[36]，可采用实际蒸腾量与潜在蒸腾量的比值作为作物生长水分胁迫因子，采用根系吸氮量与植株最低限度含氮量的比值作为作物生长养分胁迫因子。蒸腾量与蒸发量较难进行准确区分4I，实际蒸腾计算不准确将引起光合

表6作物生长及产量模拟结果及评价  
Tab.6 Crop growth and yield simulation results and evaluation   

<html><body><table><tr><td>模型</td><td></td><td>h</td><td>入</td><td>CVF</td><td>k</td><td>入</td><td>r</td><td>平均RE/%</td><td>样本数</td></tr><tr><td>VG</td><td>0.6860</td><td>0.1143</td><td>0.6456</td><td>0.5140</td><td>0.5185</td><td>0.9803</td><td>0.9186</td><td>8.73</td><td>75</td></tr><tr><td>MP</td><td>0.8190</td><td>0.0725</td><td>0.9028</td><td>0.6625</td><td>0.2374</td><td>0.1551</td><td>0.9223</td><td>8.40</td><td>75</td></tr><tr><td>LS</td><td>0.8880</td><td>0.0409</td><td>0.7874</td><td>0.6005</td><td>0.1140</td><td>0.6999</td><td>0.9268</td><td>8.42</td><td>75</td></tr></table></body></html>

注：CVF为光合产物转化效率； $k _ { 1 } \ 、 k _ { 2 } \ 、 \lambda _ { 1 } 、 k _ { 3 } 、 \lambda _ { 2 }$ 均为经验系数； $\boldsymbol { r }$ 检验均达到极显著水平。

![](images/9c58c0e7d2b82dd8bd311aba5c89f4412fbbfa8a9ed9325b2da926f29e0d88d3.jpg)  
图2产量模拟值与实测值对比  
Fig.2 Comparison of output simulation value and actual measurement value

# 干吴区地理

产物模拟误差增大,进而降低生物量模拟精度[42],因而多数研究直接采用实际蒸散量与潜在蒸散量相比作为影响因子，如在FAO第33号灌排文件中给出的产量与水分响应转换关系中采用了实际蒸散量与潜在蒸散量的比值，这种经验关系使用较为广泛[43]

植物光合产物分配系数模式[33]的建立可实现生物产量在根、茎、叶、籽粒间的分配，从而完成作物生长动态及产量的模拟。生物产量在根、茎、叶、籽粒间分配时也会受到水分、养分等环境因素的影响，即影响植株各器官的生长发育，这种影响又会反馈到潜在蒸散量与潜在生物量模拟中，对此张淑杰等44建立了动态作物系数计算方法取代了原本的固定作物系数。本研究着重对比水分胁迫响应函数形式，没有考虑作物系数动态变化对作物生长和产量模拟的影响，该处理对产量模拟没有造成过大误差，如康国芳[45]模拟的冬小麦产量平均相对误差为 $7 . 1 0 \%$ ;王伟等[46采用CERES-Wheat模型预测冬小麦产量， $\textrm { 4 a }$ 平均相对误差为 $9 . 4 2 \%$ ，同本研究给出的相对误差 $( 8 . 4 0 \% \sim 8 . 7 3 \%$ 接近。

不同的水分胁迫响应函数形式没有对产量模拟产生明显的影响，主要是因为水分胁迫系数、养分胁迫系数的参数反演，在一定程度上修正了蒸散量、吸氮量对作物生长动态及产量的影响。利用反演模型推求土壤水分特征参数已成为近些年的研究热点[47-48],相对室内试验的方法，参数反演获得的参数在一定程度上概化了不同空间点的差异。另一方面，参数反演对作物生长模型中非保守参数的率定也有很大作用，通过率定可以使模型本地化，显著提高模拟精度[42]

# 5结论

（1）采用VG、MP及LS都可以获得较好的土壤水分模拟结果及产量模拟结果，相关性系数值均在0.71以上，土壤含水率模拟值与实测值的平均RE小于 $1 2 . 5 \%$ ,模拟产量的平均RE小于 $8 . 8 \%$ ○

(2）就土壤水分动态模拟效果而言，S型水分胁迫响应函数好于凹凸型水分胁迫响应函数，VG水分胁迫响应函数又好于LS水分胁迫响应函数。采用VG水分胁迫响应函数得到的蒸散量更能反映实际情况。

（3）本研究中提出的LS水分胁迫响应函数很好的避免了分段函数中速率突变问题具有较好的模拟效果，但是其随环境变化的稳定性还有待进一步研究。

# 参考文献(References)

[1]李会杰.黄土高原林地深层土壤根系吸水过程及其对水分胁迫 和土壤碳输入的影响[D].杨凌:西北农林科技大学,2019.[Li Huijie.Root water uptake process in deep soil for forest growing on the Loess Plateau and its effect on water stress and soil carbon input[D].Yangling: Northwest A&F University,2019.]   
[2]康绍忠,刘晓明,熊运章.冬小麦根系吸水模式的研究[J].西北 农林科技大学学报(自然科学版),1992,20(2):5-12.[Kang Shaozhong,Liu Xiaoming, Xiong Yunzhang.Research on the model of mater uptake by winter wheat root system[J]. Journal of Northwest A &FUniversity (Natural Science Edition),1992,20(2): 5-12.]   
[3]姜鹏.东北玉米物质生产及根系吸水对水分胁迫的响应研究 [D].沈阳:沈阳农业大学,2O19.[Jiang Peng.Northeast corn material production and root water absorption study on the response of water stres[D]. Shenyang: Shenyang Agricultural University, 2019.]   
[4]王玉阳,陈亚鹏.植物根系吸水模型研究进展[J].草业学报, 2017,26(3): 214-225.[Wang Yuyang, Chen Yapeng. Research progress in water uptake models by plant roots[J]. Acta Prataculturae Sinica,2017,26(3): 214-225.]   
[5]王春霞,孙西欢,马娟娟,等.植物根系吸水研究[J].山西水利, 2007(1): 85-86,88.[Wang Chunxia, Sun Xihuan, Ma Juanjuan, et al. Research on plant root water absorption[J]. Shanxi Water Resources,2007(1): 85-86,88.]   
[6]赵成义,黄俊梅,王玉潮,等.植物根系吸水特性研究[J].干旱区 地理,1999,22(2): 88-96.[Zhao Chengyi, Huang Junmei, Wang Yuchao,et al.Research on water absorption characteristics of plant roots[J]. Arid Land Geography,1999,22(2): 88-96.]   
[7]李聪.农业水文模型中的关键参数对作物蒸腾量影响的数值研 究[D].杭州:浙江大学,2020.[Li Cong.Numerical study on the effects of key parameters of agro-hydrological model on crop transpiration[D]. Hangzhou: Zhejiang University,2020.]   
[8]朱永华,件彦卿,吕海深.荒漠植物根系吸水的数学模型[J].干 旱区资源与环境,2001,15(2):76-80.[Zhu Yonghua,Wu Yanqing,Lu Haishen.Mathematical model of water absorption of eremophyte root system[J]. Journal of Arid Land Resources and Environment, 2001,15(2): 76-80.]   
[9]Feddes RA,Kowalik PJ, Malinka K K,et al. Simulation of field water uptake by plants using a soil water dependent root extraction function[J].Journal ofHydrology,1976,31(1-2):1-26.   
[10]金欣欣,石建初,李森,等.根系吸水模型模拟覆膜旱作水稻气 孔导度[J].农业工程学报,2017,33(9):107-115.[Jin Xinxin, Shi Jianchu,Li Sen,et al. Modeling stomatal conductance using root-water-uptake in ground cover rice production system[J]. Transactions of the Chinese Society of Agricultural Engineering,2017, 33(9): 107-115.]   
[11]Bouten W,Heimovaara TJ,Tiktak A.Spatial patterns of throughfall and soil water dynamics in a Douglas fir stand[J].Water Resources Research,1992,28(12): 3227-3233.   
[12]Feddes R A, Kowalik P, Zarandy H. Simulation of field water use and crop yield[M].Wageningen: Centre for Agricultural Publishing and Documentation,1978: 189.   
[13] 吉喜斌,康尔泗,陈仁升,等.植物根系吸水模型研究进展[J].西 北植物学报,2006,26(5):1079-1086.[Ji Xibin, Kang Ersi, Chen Rensheng,et al. Research advances about water-uptake models by plant roots[J].Acta Botanica Boreali-Occidentalia Sinica,2006,26 (5): 1079-1086.]   
[14] 吴训.土壤水分亏缺对作物蒸腾耗水的胁迫影响及其定量表征 [D].北京:中国农业大学,2019.[Wu Xun.Effects of soil water deficit on crop water consumption by transpiration and their quantitative delineations[D].Beijing:China Agricultural University, 2019.]   
[15]Wu X, Zuo Q,Shi J,et al. Introducing water stress hysteresis to the Feddes empirical macroscopic root water uptake model[J]. Agricultural Water Management,2020,240:106293,doi: 10.1016/j.agwat.2020.106293.   
[16] 尚松浩,毛晓敏,雷志栋,等.土壤水分动态模拟模型及其应用 [M].北京:科学出版社,2009:65-121.[Shang Songhao,Mao Xiaomin,Lei Zhidong,et al. Dynamic simulation model of soil moisture and its application[M]. Beijing: Science Press,2009: 65- 121.]   
[17] 吴训,石建初,左强.基于作物水分关系改进土壤水分胁迫修正 系数的反求方法[J].水利学报,2020,51(2):212-222.[Wu Xun, Shi Jianchu,Zuo Qiang.Improvingthe inverse method to estimate the soil water stress reduction function based on crop-water relations[J]. Journal of Hydraulic Engineering,2020,51(2): 212-222.]   
[18] 孙扬越,申双和.作物生长模型的应用研究进展[J].中国农业气 象,2019,40(7): 444-459.[Sun Yangyue, Shen Shuanghe.Research progress in application of crop growth models[J]. Chinese Journal of Agrometeorology,2019,40(7): 444-459.]   
[19] 王锐,李亚飞,张丽娟,等.土壤湿度驱动WOFOST模型及其适 应性[J].中国农业气象,2015,36(3):263-271.[Wang Rui,Li Yafei,Zhang Lijuan,et al. WOFOST model based on soil moisture driven and its adaptability[J]. Chinese Journal of Agrometeorology, 2015,36(3): 263-271.]   
[20] 郎婷婷,郝蒙蒙,吴风华,等.基于DSSAT模型的京津冀地区主 要农作物用水分析[J].干旱地区农业研究,2019,37(5):235- 242,248.[Lang Tingting, Hao Mengmeng, Wu Fenghua, et al. Study on water requirements of major crops in Beijing-Tianjin-Hebei region using DSSAT model[J]. Agricultural Research in the Arid Areas,2019,37(5): 235-242,248.]   
[21] 刘洪,郭文利,宇振荣.土地生产力模型(PS123)的校正和验证 [J].中国农业气象,2005,26(3):150-154.[Liu Hong,Guo Wenli, Yu Zhenrong.Validation and calibration of land production simulation model (PS123)[J].Chinese Journalof Agrometeorolog005, 26(3): 150-154.]   
[22]杨丽霞,王仰仁.PS123模型用于山西省冬小麦水管理的适用 性评价[J].灌溉排水学报,2014,33(4/5):409-413.[Yang Lixia, Wang Yangren.Evaluation on the applicabilityof PS123 model in Shanxi Province[J]. Journalof Irrigation and Drainage,2014,33(4/ 5): 409-413.]   
[23] 王国帅,史海滨,李仙岳,等.基于HYDRUS-1D模型的荒漠绿 洲水盐运移模拟与评估[J].农业工程学报,2021,37(8):87-98. [Wang Guoshuai, Shi Haibin,Li Xianyue,et al. Simulation and evaluation of soil water and salt transport in desert oases of Hetao Irrigation District using HYDRUS-1D model[J]. Transactions of the Chinese Societyof Agricultural Engineering,2021,37(8): 87-98.]   
[24] 王世明,范敬龙,赵英,等.咸水灌溉条件下塔里木河下游沙漠 土壤水盐运移数值模拟[J].干旱区地理,2021,44(4):1104- 1113.[Wang Shiming,Fan Jinglong,Zhao Ying,etal. Numerical simulation of water and salt migration in desert soil in the lower reaches of Tarim River under salt-water irrigation[J]. Arid Land Geography,2021,44(4): 1104-113.]   
[25]Hansen S,Abrahamsen P,Petersen C T,et al. Daisy: Model use, calibration,and validation[J]. Transactions of the ASABE,2012, 55(4): 1315-1333.   
[26]胡克林,梁浩.农田土壤-作物系统过程模型及应用[M].北京: 科学出版社,2019:1-49.[Hu Kelin,Liang Hao.Farmland soil: Crop system process model and application[M]. Beijing: Science Press,2019: 1-49.]   
[27] 姜志伟,陈仲新,周清波,等.CERES-Wheat作物模型参数全局 敏感性分析[J].农业工程学报,2011,27(1):236-242.[Jiang Zhiwei, Chen Zhongxin, Zhou Qingbo,et al. Global sensitivity analysis f CERES-Wheatmodelparameters[J].Transactionsof heChinese Society of Agricultural Engineering,2011,27(1): 236-242.]   
[28] 陈小民,崔红,刘志铭,等.作物模型在我国玉米生产中的研究 与应用[J].玉米科学,2018,26(3):115-120.[Chen Xiaomin,Cui Hong,Liu Zhiming,et al.Researchandapplicationonmaize pro duction by crop models in China[J]. Journal of Maize Sciences, 2018,26(3): 115-120.]   
[29] 毛振强,张银锁,宇振荣.基于作物生长模型的夏玉米灌溉需求 分析[J].作物学报,2003,29(3):419-426.[Mao Zhenqiang, Zhang Yinsuo,Yu Zhenrong.Water requirement and irrigation scenarios of summer maize production aided by crop growth simulation model[J]. Acta Agronomica Sinica,2003,29(3): 419-426.]   
[30] 胡克林,李保国,陈研,等.作物生长与土壤水氮运移联合模拟 的研究I—模型[J].水利学报,2007,38():779-785.[Hu Kelin,Li Baoguo,Chen Yan,et al.Coupled simulation of crop growth with soil water-heat-nitrogen transport I: Model[J]. Journal of Hydraulic Engineering,2007,38(7): 779-785.]   
[31]王康.非饱和土壤水流运动及溶质运移[M].北京:科学出版社,

# 干旱区地理

2010: 1-109.[Wang Kang. Unsaturated soil water flow movement and solute transport[M]. Beijing: Science Press,201O: 1-109.]   
[32] 康绍忠.土壤-植物-大气连续体水分传播理论及其应用[M].北 京：中国水利水电出版社,1994:1-121.[Kang Shaozhong.Soilplant-atmosphere continum water propagation theory and its application[M]. Beijing: China Water Conservancy and Hydropower Press,1994: 1-121.]   
[33]王仰仁.考虑水分和养分胁迫的 SPAC水热动态与作物生长模 拟研究[D].杨凌:西北农林科技大学,2004.[Wang Yangren. Water,heat transfer and crop growth simulation in SPAC with water and nutrient stress[D]. Yangling: Northwest A& F University, 2004.]   
[34] 雷志栋,杨诗秀,谢森传.土壤水动力学[M].北京:清华大学出 版社,1988:77-130.[Lei Zhidong,Yang Shixiu,Xie Senchuan. Soil water hydrodynamics[M]. Beijing: Tsinghua University Press, 1988: 77-130.]   
[35]Novak V.Estimation of soil-water extraction pattrnsby roots[J]. Agricultural Water Management,1987,12(4): 271-278.   
[36] 宇振荣,王建武,邱建军.土地利用系统分析[M].北京:中国农 业科技出版社,1997:101-162.[Yu Zhenrong,Wang Jianwu, Qiu Jianjun. Land use system analysis[M]. Beijing: China Agricultural Science and Technology Press,1997: 101-162.]   
[37]姚丽.限量供水条件下精准灌溉技术集成效益分析[D].天津: 天津农学院,2O20.[Yao Li.Analysis of integrated benefit of precision irrigation technology under limited water supply[D].Tianjin: Tianjin Agricultural University,2020.]   
[38] 明道绪.田间试验与统计分析[M].第三版.北京:科学出版社, 2013:39-275.[Ming Daoxu.Field experiments and statistical analysis[M]. $3 ^ { \mathrm { r d } }$ ed. Beijing: Science Press,2013: 39-275.]   
[39]丁运韬,程煜,张体彬,等.利用HYDRUS-2D模拟膜下滴灌玉 米农田深层土壤水分动态与根系吸水[J].干旱地区农业研究, 2021,39(3): 23-32.[Ding Yuntao, Cheng Yu, Zhang Tibin, et al. Modeling of dynamics of deep soil water and root uptake of maize with mulched drip irrigations using HYDRUS-2D[J].Agricultural Research in the Arid Areas,2021,39(3): 23-32.]   
[40] 盛钰.绿洲农田土壤水分运移规律及其对作物生长的影响[D]. 乌鲁木齐:新疆农业大学,2004.[Sheng Yu.The law of soil water movement and its influence on growth of crop in oasis farmland [D]. Urumqi: Xinjiang Agricultural University,2004.]   
[41] 杨诗秀 刘亶仁 陆秀文 等 应用十壤物理-十壤水和温度应

用[M].北京:水利水电出版社,1984:123-151.[Yang Shixiu, Liu Danren,Lu Xiuwen, et al.Applied soil physics: Soil water and temperature application[M]. Beijing: China Water Conservancy and Hydropower Press,1984: 123-151.]   
[42] 蔡福,米娜,明惠青,等.WOFOST模型蒸散过程改进对玉米干 旱模拟影响[J].应用气象学报,2021,32(1):52-64.[Cai Fu,Mi Na,Ming Huiqing,et al. Effcts of improving evapotranspiration parameterization scheme on WOFOST model performance in simulating maize drought stress processJ]. Journal of Applied Meteorological Science,2021,32(1): 52-64.]   
[43]孙仕军,张琳琳,陈志君,等.AquaCrop作物模型应用研究进展 [J].中国农业科学,2017,50(17): 3286-3299.[Sun Shijun, Zhang Linlin, Chen Zhijun, et al.Advances in AquaCrop model research andapplication[J]. Scientia Agricultura Sinica,2O17,50(17): 3286-3299.]   
[44] 张淑杰,周广胜,李荣平.基于涡度相关的春玉米逐日作物系数 及蒸散模拟[J].应用气象学报,2015,26(6):695-704.[Zhang Shujie, Zhou Guangsheng,Li Rongping. Daliy crop coefficient of spring maize using eddy covariance observation and its actual evapotranspiration simulation[J]. Journal of Applied Meteorological Science,2015,26(6): 695-704.]   
[45] 康国芳.河北省冬小麦生长模拟与叶绿素荧光参数分析[D].保 定：河北农业大学,2008.[Kang Guofang.Study on winter growth simulation and chlorophyll fluorescence parameter analysis in Hebei Province[D]. Baoding: Hebei Agricultural University,2008.]   
[46] 王伟,黄义德,黄文江,等.作物生长模型的适用性评价及冬小 麦产量预测[J].农业工程学报,2010,26(3):233-237.[Wang Wei,Huang Yide,Huang Wenjiang,et al.Applicability evaluation of CERES-wheat model and yield prediction of winter wheat[J]. Transactions of the CSAE,2010,26(3): 233-237.]   
[47] 俞明涛,张科锋.基于HYDRUS-2D软件的土壤水力特征参数 反演及间接地下滴灌的土壤水分运动模拟[J].浙江农业学报, 2019,31(3): 458-468.[Yu Mingtao,Zhang Kefeng.Identification of soil hydraulic parameters based on HYDRUS-2D software and simulation of soil water movement under indirect subsurface drip irrigation[J]. Acta Agriculturae Zhejiangensis,2019,31(3): 458-468.]   
[48] 刘彬彬.基于微遗传算法的土壤水力特征参数反演及水分运动 模拟[D].杭州:浙江大学,2018.[Liu Binbin.Identification of soil hydraulic property parameters based on the micro- genetic algorithm and simulation[D]. Hangzhou: Zhejiang University,2018.]

# Effect of root water stress response function on soil water, crop growth dynamics and yield simulation

WANG Tieying'， WANG Yangren'， CHAI Junfang²， GUO Wenjun² (1.School of Hydraulic Engineering,Tianjing Agricultural University,Tianjing 3Oo392, China; 2.IrigationExperimentStationofHuoquanWaterConservancyAfirsCnter,HongdongCounty,Linfen36o,haniCina)

Abstract: To investigate the effect of the root moisture stress response function (RMSRF) on soil moisture dynamic and yield simulation,the soil moisture dynamic,and wheat yield were simulated based on the Richards equation and PS123 crop growth model.The three RMSRFof VG (S-curve),MP(convex curve),and LS (S-curve) were compared. The soil characteristic and RMSRF parameters in the model were inverted to determine the optimal parameter values using the measured data from Huoquan Station (three years） and Xiaohe Station (two years)in Shanxi Province, China to obtain the simulation results of soil moisture content, evapotranspiration,and grain yield.The analysis isas follws.(1） The soil moisture and yield simulations under VG,MP,and LS functions are good. The RMSE value is between O.021 and 0.036; the $r$ test between the simulated and measured values has reached an extremely significant level.For the Huoquan Station,under the three RMSRFof VG,MP, and LS conditions,the average relative errors of the simulated and measured values for soil moisture content are $6 . 3 7 \%$ ， $8 . 2 6 \%$ ,and $7 . 1 8 \%$ , respectively. The minimum certainty coefficient value is O.7814.The average relative error values of the simulated wheat yield are $8 . 7 3 \%$ ， $8 . 4 0 \%$ ,and $8 . 4 2 \%$ , respectively. For the Xiaohe Station, the average relative error of the simulated and measured values for soil moisture content is greater than that of the Huoquan Station, with a maximum of $12 . 4 7 \%$ . (2)The simulation of soil moisture dynamic shows that RMSRF by the S-shaped curve shows beter results than RMSRF by the concave-convex curve.The average relative error using the VG function is smaler,and the simulated evapotranspiration is closer to the actual measurement. (3) In terms of yield simulation results,there is no significant difference among the three RMSRF. In summary,the VG function is a high-precision RMSRF,and the model is simple and convenient. The suggested LS function can improve the simulation accuracy,but the stability of the model needs further research.

Key words: moisture stress； root moisture uptake model; farmland moisture simulation; yield simulation； pa-rameter inversion