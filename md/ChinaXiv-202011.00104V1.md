# 修订后水分盈亏指数在甘肃省冬小麦干旱监测中的应用

贾建英}²，刘蓉³，韩兰英²，万信¹，王大为1（1中国气象局兰州干旱气象研究所／甘肃省干旱气候变化与减灾重点实验室／中国气象局干旱气候变化与减灾重点开放实验室,甘肃 兰州 730020；2 兰州区域气候中心,甘肃兰州 730020;3兰州市气象局，甘肃兰州730020）

摘要：提高西北旱作农业干旱监测准确性和时效性,对农业生产防灾减灾有重要意义。利用甘肃省3个农业气象观测站长期土壤水分和冬小麦生育状况观测资料、1971—2016年43个冬小麦种植县气象观测资料及产量资料，基于冬小麦播前底和生育期水分盈亏量修订了作物水分盈亏指数，并确定了干旱等级指标，改进后作物水分盈亏指数与土壤贮水和冬小麦减产率高度相关，能更准确的反映甘肃省冬小麦干旱实况，并利用ArcGIS分析了近46a甘肃省冬小麦不同生育期、不同等级干旱发生频率的时空分布特征。结果表明：甘肃省冬小麦从播种至开花期随着发育期推移，呈现干旱频率增加、范围扩大的趋势，多以中旱居多，其中拔节一开花期发生面积最大，陇中、庆阳市北部、平凉市西部、天水市西部、陇南市南部干旱出现频率较高;开花一成熟期随着降水量增加干旱发生频率减少、程度减轻。

关 键 词：干旱监测；作物水分盈亏指数；冬小麦；土壤贮水；甘肃省文章编号： $1 0 0 0 - 6 0 6 0 \bigl ( 2 0 2 0 \bigr ) 0 4 - 0 8 7 1 - 0 9 \bigl ( 0 8 7 1 \sim 0 8 7 9 \bigr )$

干旱是全球影响范围最广泛、造成全球经济损失最严重的自然灾害1，随着全球气候的变化，呈现出干旱影响范围不断增大、干旱损失日趋加剧的态势[2-3]。研究表明,21世纪全球干旱风险将进一步增加[4-5]。而干旱影响最为明显也最为直接的就是农业系统。中国是农业大国，干旱是造成农业经济损失最严重的气象灾害，我国常年农作物受旱面积约$( 0 . 2 0 \sim 0 . 2 7 ) { \times } 1 0 ^ { 8 } \ \mathrm { h m } ^ { 2 }$ ，每年损失粮食！ $( 2 5 0 \sim 3 0 0 ) \times$ $1 0 ^ { \mathrm { { s } } } \mathrm { k g }$ ，占各种自然灾害损失总量的 $6 0 \% ^ { [ 6 ] }$

国际上通常将干旱划分为4种类型[5-7]：气象干旱、农业干旱、水文干旱和社会经济干旱，而农业干旱是四类干旱中最复杂的一种，因为它涉及到土壤、作物、大气和人类对资源利用等多方面因素。农业干旱监测作为减轻农业干旱灾害损失与影响的重要途径,是干旱研究的重要内容之一[8-10]。20世纪初，美国首先兴起干旱监测方面的研究，前期的干旱监测指数多数只考虑降水量单一因子[11-2]后期逐渐发展到多因子结合的复杂干旱指数。大体可分为两类,一类是基于遥感监测技术[13-14],应用广泛的如温度植被干旱指数(TVDI)、作物水分胁迫指数(CWSI)等;另一类是基于地面气象观测数据的干旱指数[15-17],如针对气象干旱的降水距平百分率$( P a )$ 、帕默尔干旱指数(PDSI)、标准降水指数(SPI)等，而农业干旱监测指数应用广泛的是土壤相对湿度[17]、水分亏缺指数[18]、作物水分盈亏指数[19-22]等。

冬小麦是甘肃省主要粮食作物之一，主要分布于半干旱区的陇西黄土高原、半湿润区的陇东黄土高原和湿润区的陇南徽成盆地。黄土高原上覆盖深厚的黄土层，厚度在 $5 0 \sim 8 0 \mathrm { m }$ 之间,颗粒细，土质松,是天然的“土壤水库”[23-24], $1 0 0 \mathrm { c m }$ 土层贮存水分$2 5 0 \sim 3 4 0 ~ \mathrm { m m } , 2 0 0 ~ \mathrm { c m }$ 土层贮存水分 $5 8 0 \sim 6 4 0 ~ \mathrm { m m }$ ，土壤贮水量对冬小麦生长发育及最终产量影响较

# 干旱区地理

大[23-24]。研究表明，甘肃省冬麦区底熵对冬小麦产量的贡献率为 $3 8 . 6 \% , 8 \sim 9$ 月降水与翌年陇东黄土高原冬小麦产量相关较高[25-27]。而目前应用广泛的农业干旱监测指数对作物播前底熵的作用考虑较少[18],因而不能客观准确监测甘肃省黄土高原冬小麦干旱实况。

本文利用甘肃省长期定位土壤水分观测资料、气象资料及冬小麦生育状况和产量要素观测资料，拟将考虑冬小麦休闲期土壤贮水和生育期间降水盈亏量修订作物水分盈亏指数，分析甘肃省冬小麦干旱时空分布特征，评价修订后作物水分盈亏指数在研究区的适用性，以期为西北旱作农业提高水资源利用效率和防灾减灾提供科学依据。

# 1资料与方法

# 1. 1 资料来源

甘肃省不同气候区冬小麦土壤水分观测数据及生育状况观测数据来源于3个农业气象试验（观测)站：通渭农业气象观测站( $[ 1 0 5 ^ { \circ } 1 4 ^ { \prime } \mathrm { E } , 3 5 ^ { \circ } 1 3 ^ { \prime } \mathrm { N } ]$ 海拔高度 $1 7 6 8 . 2 \ : \mathrm { m }$ )年降水量 $3 9 0 . 6 ~ \mathrm { m m }$ ,定为半干旱区[23],土壤质地为壤土，碱性;西峰农业气象试验站0 $( 1 0 7 ^ { \circ } 3 8 ^ { \prime } \mathrm { E } , 3 5 ^ { \circ } 4 4 ^ { \prime } \mathrm { N }$ ,海拔高度 $1 \ 4 2 1 \ \mathrm { m } .$ )年降水量$5 2 7 . 2 \mathrm { m m }$ ,定为半湿润区[23],土壤质地为壤土,碱性;成县农业气象观测站 $\langle 1 0 5 ^ { \circ } 4 3 ^ { \prime } \mathrm { E } , 3 3 ^ { \circ } 4 5 ^ { \prime } \mathrm { N }$ ，海拔高度$9 7 0 \mathrm { m }$ )年降水量 $6 2 1 . 4 \ \mathrm {  m m }$ ，定为湿润区[23]，土壤质地为粘壤土，中性。测定时间：通渭农业气象试验站观测时间为1984、1985、1990、1991、1993—1996、1998、2004、2010一2012年，西峰农业气象试验站观测时间为1981一2014年，成县农业气象试验站观测时间为1991—2014年。43个冬小麦种植县1971—2016年气象资料来源于甘肃省气象局信息中心（图1),1981—2016年产量资料和干旱灾情资料来源于《甘肃农村年鉴》。按照气候特征甘肃省冬麦区划分为三大麦区：陇中麦区包括兰州市、定西市和临夏州，陇东麦区包括庆阳市和平凉市，陇南麦区包括天水市和陇南市，区域平均发育期为各区域冬小麦观测站点生育期多年平均值(表1)[28-29]

![](images/2e4a58070439b250ea2a4cb2be5181ab9c6a64a069c01b5ae624b8754087ee26.jpg)  
图1研究区域及站点  
Fig.1Study area and weather stations

表1甘肃省3大麦区平均发育期  
Tab.1Average developmental stages of three winter wheat areas in Gansu Province   

<html><body><table><tr><td>地区</td><td>休闲期</td><td>播种</td><td>越冬</td><td>返青</td><td>拔节</td><td>开花</td><td>成熟</td></tr><tr><td>陇中</td><td>7月/下旬~9月/中旬</td><td>9月/下旬</td><td>11月/上旬</td><td>3月/中旬</td><td>5月/中旬</td><td>6月/中旬</td><td>7月/中旬</td></tr><tr><td>陇东</td><td>7月/中旬~9月/中旬</td><td>9月/下旬</td><td>11月/中旬</td><td>3月/上旬</td><td>4月/中旬</td><td>5月/中旬</td><td>7月/上旬</td></tr><tr><td>陇南</td><td>7月/上旬~10月/上旬</td><td>10月/中旬</td><td>12月/中旬</td><td>2月/下旬</td><td>3月/下旬</td><td>4月/下旬</td><td>6月/下旬</td></tr></table></body></html>

# 1.2基于休闲期土壤贮水对冬小麦水分盈亏指数 修订

一般7、8、9月是麦田休闲期,而这3个月降水通常占全年降水的 $5 0 \% \sim 6 0 \%$ ,而深厚的黄土覆盖为降水资源转化为土壤水分提供了条件，因此休闲期土壤贮水对甘肃省冬小麦整个生育期都有重要作用[28-29]。参考前人[23,30]方法计算了贮水量和贮水效率：休闲期 $1 \mathrm { m }$ 土层多年平均贮水量半湿润区为 $8 5 . 6 ~ \mathrm { m m }$ ,贮水效率为 $3 2 . 0 \%$ ；湿润区为71.8$\mathbf { m } \mathbf { m }$ ，贮水效率为 $1 8 . 1 \%$ ;而半干旱区为 $2 4 . 4 ~ \mathrm { m m }$ ，贮水效率为 $1 4 . 2 \% ^ { [ 2 3 , 2 9 ] }$ 。作物水分盈亏指数 $( L )$ 表征了作物需水量（W）与降水量 $( R )$ 之间的盈亏程度，是一个基于农田水分收支原理的旱涝评价指标[19-22,29] ○

$$
\ L = { \frac { R - W } { W } }
$$

研究表明，一个时段干旱的严重程度，不仅与该时段水分盈亏量有关，还受前期水分盈亏量影响 [19-23，29]。因此，作物水分盈亏指数在甘肃黄土高原等地应用，需将休闲期贮水考虑进去，同时，还将前期水分盈亏量影响考虑进去，式(1)可修订为：

$$
L = \frac { R _ { 0 } \times W S E + R - W } { W }
$$

式中：WSE为休闲期贮水效率[23.29]； $R _ { 0 }$ 为休闲期降水 $( \mathbf { m } \mathbf { m } )$ ； $R$ 为播种以来的降水量( $\mathrm { { ( m m ) } }$ ； $W$ 为作物需水量（ $\bf \Pi _ { \mathrm { m m } } )$ ，由式(3)计算得出。

$$
W { = } K _ { c } \times E T _ { 0 }
$$

式中： $K _ { c }$ 为基于实际耗水量确定的作物系数[29-30] $E T _ { 0 }$ 为参考作物蒸散量，采用FAO推荐用Pen man-Monteith计算[29]

# 1.3干旱等级指标的确定

参考《甘肃农村年鉴》中灾情资料，结合3个农气观测站历年干旱灾害的记载，依据GB/T32136-2015[18]中农田与作物形态农业干旱指标等级，确立了不同等级干旱的作物水分盈亏指数等级[28-29](表2）。

# 表2甘肃省冬小麦水分盈亏指数干旱等级

Tab.2Drought grades of winter wheat water budget index in Gansu Province   

<html><body><table><tr><td>等级</td><td>类型</td><td>水分盈亏指数/L</td></tr><tr><td>0</td><td>无旱</td><td>L>0.0</td></tr><tr><td>1</td><td>轻旱</td><td>-0.1<L≤0.0</td></tr><tr><td>2</td><td>中旱</td><td>-0.3<L≤-0.1</td></tr><tr><td>3</td><td>重旱</td><td>-0.5<L≤-0.3</td></tr><tr><td>4</td><td>特旱</td><td>L≤-0.5</td></tr></table></body></html>

# 2结果与分析

# 2.1修订后水分盈亏指数与土壤贮水量和减产率的关系

修订后作物水分盈亏指数与 $1 \mathrm { m }$ 土层总贮水量呈明显正相关（ $R ^ { 2 } = 0 . 6 5 2 ~ 2$ （图2)，表征了水分对冬小麦生育需水的满足程度，基本能准确反映甘肃省冬麦区土壤水分实际状况，在实际应用中大体能客观监测冬小麦干旱实况，评估冬小麦干旱等级。修订后作物水分盈亏指数与减产率相关性较高（表3)，且都通过0.01水平信度检验;其中，不同气候区冬小麦在拔节一开花期作物水分盈亏指数与产量的相关系数最高，此阶段正是冬小麦需水关键期，对水分较为敏感，开花期以后随着降水量增加，作物水分盈亏指数程度减轻，但干旱对冬小麦造成的损失已不可逆，所以成熟期作物水分盈亏指数与减产率的相关性有所下降，特别是降水量充沛湿润区从开花期以后相关性下降更显著。

![](images/a601ad96ecc2750dced559fd6bcd51c799dca1f34927842cca047343ddbbc716.jpg)  
图2水分盈亏指数 $( L )$ 与 $1 \mathrm { m }$ 土层总贮水量散点图 Fig.2Scatter plot of water budget index $( L )$ and $1 \mathrm { m }$ soil water storage

# 表3不同生育期水分盈亏指数与减产率相关性

Tab.3Relevance of water budget index and yield reduction rate in different growth periods   

<html><body><table><tr><td>区域</td><td>越冬</td><td>返青</td><td>拔节</td><td>开花</td><td>成熟</td></tr><tr><td>半干旱区</td><td>0.428**</td><td>0.505**</td><td>0.524**</td><td>0.625**</td><td>0.538**</td></tr><tr><td>半湿润区</td><td>0.570**</td><td>0.532**</td><td>0.678**</td><td>0.656**</td><td>0.569**</td></tr><tr><td>湿润区</td><td>0.471**</td><td>0.502**</td><td>0.611**</td><td>0.244</td><td>0.198</td></tr></table></body></html>

注：\*\*表示通过0.01水平信度检验

# 2.2不同生育期干旱发生频率空间分布

甘肃省冬麦区干旱从播种至开花期随着发育期推移出现频率增加、范围扩大的趋势，开花一成熟期干旱发生频率略有减少(图3)：播种一越冬期在兰州市榆中、定西市安定和漳县、庆阳市环县、陇南市文县出现频率为 $2 0 \% \sim 3 0 \%$ ,冬麦区其余地方出现频率较低;越冬一返青期，陇南市北部、天水市东部发生干旱机率较低，其余冬麦区干旱出现频率较前一生育期都有所增加，特别是榆中、安定、武山、文县增加明显;返青一拔节期，冬麦区大部(除陇南市)干旱出现频率较前一生育期增加幅度在$2 0 \% \sim 4 0 \%$ ;拔节一开花期干旱出现范围最大、频率最高，降水量最充沛的陇南市徽成盆地出现频率达到 $5 5 \% \sim 6 5 \%$ ，陇中大部、庆阳市北部、平凉市西部、天水市西部、陇南市南部出现在 $7 5 \% \sim 8 6 \%$ ,其余冬麦区干旱出现频率也在 $6 5 \% \sim 7 5 \%$ ;开花一成熟期随着降水增多，干旱频率不同程度出现下降。

# 2.3不同生育期不同等级干旱发生频率空间分布

(1)播种一越冬期

播种一越冬期干旱出现频率较低：轻旱出现频率为 $2 \% \sim 5 \%$ ,中、重旱出现频率在 $5 \% \sim 1 0 \%$ ,特旱出现频率在 $3 \%$ 以下，主要发生在陇中和庆阳市西北、平凉市西部、陇南市南部等地(图4)。由于甘肃属于温带(大陆性)季风气候，降水主要集中在夏秋季（7\~9月）[23],土壤蓄足底，且播种一越冬阶段冬小麦需水量少，该阶段甘肃省冬小麦受干旱威胁风险最小。

![](images/c09a24d03faf9bb748450c088b6c1309709e0621d08f712f8f8f1ce3e878ea89.jpg)  
Fig.3Drought frequency of winter wheat in different growth periods in Gansu Province $1 \%$

(2)越冬一返青期越冬一返青期干旱出现频率：轻、中旱出现频率为 $5 \% \sim 1 5 \%$ ，主要在陇中、庆阳市、平凉市、陇南市南部;重旱出现频率在 $8 \% \sim 2 4 \%$ ,出现在文县、环县、榆中等地；特旱出现频率在 $6 \%$ 以下，主要发生在榆中、文县(图5)。该阶段甘肃省处于冬季少雨，由于冬小麦处于休眠期，干旱对冬小麦影响不大。

![](images/3f83b4677b57c1efdb9f71ffaf9b17eaa72420965c455181e04588abbe7e4402.jpg)  
图3甘肃省冬小麦不同发育期干旱出现频率 $1 \%$   
图4播种一越冬期出现不同等级干旱频率 $1 \%$   
Fig.4Drought frequency at different levels of sowing-overwintering periods

(3)返青一拔节期

返青一拔节期干旱出现频率：除陇南市南部，冬麦区大部轻旱出现频率为 $8 \% \sim 1 6 \%$ ;中、重旱出现频率在 $12 \% \sim 3 6 \%$ ，主要在陇中、陇东大部及天水市西北部(甘谷、秦安、武山）、陇南市南部(武都、文县);特旱出现频率在 $6 \% \sim 1 2 \%$ ,主要发生在榆中、环县、文县(图6)。该阶段冬小麦需水量递增，而甘肃省处于初春少雨时段，冬小麦遭受干旱威胁风险增大。

![](images/3d92bf59dc9c3b6c1a170d61f5dc4936e13bd24ccee850ad85f33a92a977a0c3.jpg)  
图5越冬一返青期出现不同等级干旱频率 $1 \%$   
Fig.5Drought frequency at different levels of overwinter-recovering periods $1 \%$

# (4)拔节一开花期

拔节一开花期干旱出现频率：轻旱主要在临夏州东部(东乡、康乐）定西市南部(渭源、漳县）、庆阳市宁县、平凉市灵台、天水市东部(秦州、麦积）、陇南市北部(岩昌、西和、成县、徽县、两当)，发生频率为 $1 5 \% \sim 3 0 \%$ ;而冬麦区大部(除陇南市武都和文县)中旱出现频率在 $2 0 \% \sim 3 6 \%$ ;重旱出现频率在$1 6 \sim 5 0 \%$ ，主要在陇中和陇东大部、天水市西部、陇南市南部;特旱出现频率在 $2 0 \% \sim 4 0 \%$ ,主要发生在环县、文县、武都(图7)。该阶段是冬小麦需水高峰期和关键期，而甘肃省仍处于春末夏初少雨时段，造成该阶段冬小麦遭受干旱威胁风险最大。

(5)开花一成熟期

开花一成熟期干旱出现频率：轻旱主要在陇中、陇南大部，出现频率为 $1 3 \% \sim 1 8 \%$ ;冬麦区中旱大部(除陇南市南部、庆阳市西北部等地)出现频率在 $2 4 \% \sim 4 4 \%$ ;重旱出现频率在 $2 0 \% \sim 6 0 \%$ ,主要在陇中、陇东大部及天水市西部、陇南市南部等地，特旱出现频率在 $12 \% \sim 2 4 \%$ ,主要发生在环县、文县(图8)。该阶段也处于冬小麦需水关键期，甘肃降水逐渐增加但未进入多雨时段[31-32],冬小麦遭受干旱威胁的风险仍较高。

# 3结论

（1）休闲期土壤贮水是影响黄土高原冬小麦生产力的重要因素[24-27],而休闲期土壤贮水主要消耗在了冬小麦返青至开花期[23]。本文考虑休闲期土壤贮水和生育期水分盈亏修订了作物水分盈亏指数，修订后的作物水分盈亏指数与实测土壤湿度和冬小麦减产率高度相关，能真实反映甘肃省冬小麦干旱实际情况;拔节期和开花期水分盈亏指数与冬小麦减产率相关性最高，该阶段是冬小麦需水关键期，在一定程度能定量评估十旱对冬小麦产量造成的损失，而成熟期相关性有所下降，特别是湿润区开花期以后相关性下降较为显著，是因为随着降水量增加旱情缓解，而干旱对产量的影响已不可逆，说明该指数对干旱的不可逆性反映不够客观，还需在今后的业务应用中改进完善。

![](images/94e203e9b98d1d57aa56a57b5cb65e27474843f39e76e3a98e1907d829b09de4.jpg)  
图6返青一拔节期出现不同等级干旱频率 $1 \%$

![](images/4b1ff265460dd671ceb956df93e3a6f78a7bb4ccc534ad7e7aa361d82aed0b8f.jpg)  
Fig.6Drought frequency at different levels of recovering-jointing periods $1 \%$   
图7拔节一开花期出现不同等级干旱频率 $1 \%$   
Fig.7Drought frequency at different levels of jointing-flowering periods /%

![](images/3f017ce57183efab84ea1ee0c6d5b639ce6be11172b58893f8f022affe7c40f4.jpg)  
图8开花一成熟期出现不同等级干旱频率 $1 \%$   
Fig.8Drought frequency at different levels of flowering-mature periods $1 \%$

(2）甘肃省冬麦区从播种至开花期随着发育期推移，呈现干旱频率增加、范围扩大的趋势，其中拔节一开花期干旱范围最大、程度最重，开花一成熟期随着降水量增加干旱发生频率略有减少。播种至返青期，兰州市榆中、定西市安定、庆阳市环县、天水市武山、陇南市文县等地干旱出现频率较大，且多以中旱居多；返青至成熟期，各冬麦区干旱出现频率均显著增加，陇中、庆阳市北部、平凉市西部、天水市西部、陇南市南部干旱出现频率较高，以中旱居多。水分盈亏指数中的降水 $( R )$ 应为某时段农业有效降水量，特别是在黄土高原，有效降水的区分较为关键，而本文统计的是某时段的所有降水，这对修订后水分盈亏指数的监测效果有一定影响。因此，在今后业务应用中，需区分有效降水进一步改进水分盈亏指数，并对比分析不同干旱监测指数的监测效果，逐步完善作物水分盈亏指数。

# 参考文献(References)

[1]IPCC.Climate change 2O14:Impacts,adaptation and vulnerability,working group II report[M].New York:Cambridge University Press,2014.   
[2]张强,韩兰英,张立阳,等.论气候变暖背景下干旱灾害风险特 征与管理[J].地球科学进展，2014，29(1)：80-91.[ZHANG Qiang,HANLanying，ZHANGLiyang,et al.Analysis on the character and management strategy of drought disaster and risk under climate warming[J].Advance in Earth Science,2014,29 (1):80-91.]   
[3] HAN Lanying,ZHANG Qiang,MA Pengli,et al. The spatial distribution characteristics of a comprehensive drought risk index in southwestern China and underlying causes ［J].Theoretical and Applied Climatology,2015,120(1):1756-1769.   
[4] DAI Ai.Drought under global warming:A review[J].Wiley InterdisciplinaryReviews:Climate Change,2011,2(1):45-65.   
[5]刘宪锋,朱秀芳,潘耀忠,等.农业干旱监测研究进展与展望 [J].地理学报,2015,70（11）)：1835－1843.[LIU Xianfeng, ZHU Xiufang,PAN Yaozhong,et al. Agricultural drought monitor: Progress,challenges and prospect[J]. Acta Geographica Sinica,2015,70(11):1835-1843.]   
[6]李茂松,李森,李育慧.中国近 50a来旱灾灾情分析[J].中国 农业气象,2003,24（1）:7-10.[LI Maosong,LI Seng,LI Yuhui. Studies on drought in the past 5O years in China[J].Chinese Journal of Agrometeorology,2003,24(1):7-10.]   
[7］陈怀亮,张红卫,刘荣花.中国农业干旱的监测、预警和灾损评 估[J].科技导报,2009,，（11）:82－92.[CHEN Huailiang， ZHANG Hongwei,LIU Ronghua.Agricultural drought monitoring,forecasting and loss assessment in China[J]. Science Technology Review,2009,（11):82-92.]   
[8］张强,张良,崔显成,等.干旱监测与评价技术的发展及其科学 挑战[J].地球科学进展,2011,（7):763－778.[ZHANG Qiang, ZHANG Liang,CUI Xiancheng,et al. Progress and challenges in drought assessment and monitoring[J]. Advance in Earth Science,2011,(7):763-778.]   
[9]王春乙,王石立,霍治国,等.近10a来中国主要农业气象灾害 监测预警与评估技术研究进展[J].气象学报,2005,（5)： 659 - 671.[WANG Chunyi,WANG Shili,HUO Zhiguo,et al. Progress in research of agro-meteorological disasters in China in recent decade[J]. Acta Meteorologica Sinica,2005,（5）: 659 - 671.]   
[10］李柏贞,周广胜.干旱指标研究进展[J].生态学报,2014,34 （5）:1043- 1052.[LI Bozhen,ZHOU Guangsheng.Advance in the study on drought index[J]. Acta Ecologica Sinica,2014,34 (5):1043-1052.]   
[11] MUNGER T T. Graphic method of representing and comparing drought intensities[J].Monthly Weather Review,1916,44（11)： 642- 643.   
[12]KINCER JB.The seasonal distribution of precipitation and its frequency and intensity in the United States[J].Monthly Weather Review,1919,47(9):624- 631.   
[13］陈怀亮,冯定原.用遥感资料估算深层土壤水分的方法和模型 [J].应用气象学报,1999,10(2):232－237.[CHEN Huailiang, FENG Dingyuan.The monitoring method and model of deep soil layer moistures by remotely sensed data[J]. Journal of Applied Meteorological Science,1999,10(2):232-237.]   
[14］陈书林,刘元波,温作民.卫星遥感反演土壤水分研究综述[J]. 地球科学进展,2012,（11):1192－1203.[CHEN Shulin,LIU Yuanbo,WEN Zuomin.Satellite retrieval of soil moisture:An overview[J].Advance in Earth Science,2012,(11):1192-1203.]   
[15]PALMER W C. Meteorological drought [M]. Washington DC: US Weather Bureau,1965.   
[16]MCKEE T B,DOESKEN N J,KLEIST J. The relationship of drought frequency and duration to time scales[J]. Proceedings of the 8th Conference on Applied Climatology:American Meteorological Society Boston,MA,1993:179-183.   
[17］曹永强,郑爽,范帅邦,等.基于修正Z指数的辽西北春旱演变 分析[J].干旱区地理,2017,40(1):10-16.[CAO Yongqiang, ZHENG Shuang,FAN Shuaibang,et al.Evolution analysis of spring drought events in northwest Liaoning based on grade adjustment of Z-Index[J].Arid Land Geography,2017,40（1）: 10-16]   
[18]GB/T32136_2015.农业干旱等级［S].2015.[GB/T 32136 2015. Grade of agricultural drought [S].2015.]   
[19］苏永秀,李政,吕厚荃.水分盈亏指数及其在农业干旱监测中 的应用[J].气象科技,2008,36(5):592-595.[SUYongxiu,LI Zheng,LU Houquan. Application of water budget index in agricultural drought monitoring[J]. Meteorological Science and Technology,2008,36(5):592-595.]   
[20］张玉芳,王锐婷,陈东东,等.利用水分盈亏指数评估四川盆地 玉米生育期干旱状况[J].中国农业气象,2011,32(4):615- 620.[ ZHANG Yufang,WANG Ruiting,CHEN Dongdong,et al. Evaluation on drought at maize growth stage in Sichuan Basin using water budget index[J]. Chinese Journal of Agrometeorology,2011,32(4):615-620.]   
[21］高晓容,王春乙,张继权,等.近50a东北玉米生育阶段需水量 及旱涝时空变化[J].农业工程学报,2012,28(12)：101－109. [GAO Xiaorong,WANG Chunyi, ZHANG Jiquan,et al. Crop water requirement and temporal-spatial variation of drought and flood disaster during growth stages for maize in northeast during past 50 years[J]. Transactions of the Chinese Society of Agricultural Engineering,2012,28(12):101-109.]   
[22]贾建英,贺楠,韩兰英,等.基于自然灾害风险理论和 ArcGIS 的西南地区玉米干旱风险分析[J].农业工程学报,2015,31 (4）: 152 - 159.[JIA Jianying,HE Nan,HAN Lanying,et al. Analysis on drought risk of maize in Southwest China based on natural disaster risk theory and ArcGIS［J]. Transactions of the Chinese Society of Agricultural Engineering,2015,31(4):152 - 159.]   
[23］贾建英,赵俊芳,万信,等.黄土高原不同降水区休闲期土壤贮 水效率及其对冬小麦水分利用的影响[J].生态学报,2017,37 (17):1-9 .[JIAJianying,ZHAO Junfang,WAN Xin,et al.Effects of soil water storage efciency on winter wheat water use efficiency in different precipitation areas during the fallow period in the Loess Plateau,western China[J].Acta Ecologica Sinica,2017,37(17):1- 9.]   
[24］邓振镛,张强,王强,等.黄土高原旱作区土壤贮水力和农田耗 水量对冬小麦水分利用率的影响[J].生态学报，2010,30 (14） :3672 - 3678.[DENG Zhenyong,ZHANG Qiang,WANG Qiang,et al. Effects of soil water storage capacity and consumption on winter-wheat water use efficiency in dryland areas of the Loess Plateau in western China[J].Acta Ecologica Sinica,2010, 30(14):3672-3678.]   
[25］邓振镛,张强,王强,等.黄土高原旱塬区土壤贮水量对冬小麦 产量的影响[J].生态学报,2011,31(18):5281-5290.[DENG Zhenyong,ZHANG Qiang,WANG Qiang,et al. Influence of water storage capacity on yield of winter wheat in dry farming area in the Loess Plateau[J].Acta Ecologica Sinica,2011,31（18）: 5281-5290.]   
[26］罗俊杰,黄高宝.底熵对旱地冬小麦产量和水分利用效率的影 响研究[J].灌溉排水学报,2009,28(3):102－104,111.[LUO Junjie,HUANG Gaobao.Effects of different soil water before sowing on winter wheat yield and WUE in semi-arid areas[J]. Journal of Irrigation and Drainage,2009,28(3):102-104,111.]   
[27］罗俊杰,王勇,樊廷录.旱地不同生态型冬小麦水分利用效率 对播前底的响应[J].干旱地区农业研究,2010,28(1)：61- 65,71.[LUO Junjie, WANG Yong,FAN Tinglu. Effect of win

ter wheat yield and WUE with different soil water before sowing in semi-arid areas[J].Agricultural Research in the Arid Areas, 2010,28(1):61-65,71.]

[28］贾建英,韩兰英，万信，等.甘肃省冬小麦干旱灾害风险评估及 其区划[J].干旱区研究,2019,36(6)：1478-1486.[JIAJianying,HANLanying,WANXin,et al.Risk and regionalization of drought for winter wheat in Gansu Province[J].Arid Zone Research,2019,36(6):1478-1486]

[29］贾建英，韩兰英，万信.甘肃省冬小麦水分盈亏指数的改进及其应用[J].中国生态农业学报，2018，26(4)：559-566.[JIAJianying,HANLanying,WANXin.Improvement and applicabil-ity of winter wheat water budget index in Gansu Province[J].Chinese Journal of Eco-Agriculture,2018,26(4):559-566.]

[30］侯贤清，李荣，韩清芳，等.夏闲期不同耕作模式对土壤蓄水保效果及作物水分利用效率的影响[J].农业工程学报，2012，

28（3）:94-100.[HOU Xianqing,LI Rong,HAN Qingfang,et al.Effects of different tillage patterns during summer fallow on soil water conservation and crop water use efficiency[J].Transactions of the CSAE,2012,28(3):94-100.]

[31］杨金虎,靳荣，刘晓云，等.西北地区东部汛期降水季节内分布 特征分析[J].干旱区地理，2017,40(5)：942-950.[YANG Jinhu,JIN Rong,LIU Xiaoyun,et al.Inter-seasonal distribution pattern of rainy season precipitation in the east region of northwest China[J]. Arid Land Geography,2017,40(5):942-950.]   
[32]韩盟伟，赵广举，穆兴民，等.黄土高原1959—2015年潜在蒸发 量的时空变化[J].干旱区地理，2017，40(5)：997－1004. [HAN Mengwei,ZHAO Guangju,MU Xingmin,et al. Spatial and temporal variations of potential evapotranspirationon the Loess Plateau during 1959- 2015[J].Arid Land Geography, 2017,40(5):997-1004.]

# Applicability of modified water budget index in winter wheat drought monitoring of Gansu Province

JIA Jian-ying'²，LIU Rong²，HAN Lan-ying1,²，WAN Xin'，WANG Da-wei' （1Key（Open）LaboratoryofAridClimaticChangeandReducingDisasterofGansuProvinceKeyOpenLaboratoryofAridClimaticChange andReducingasterofineterogicalmstrationsituterideogineterogicaldminstrati 730020,Gansu,China;2 Lanzhou Regional Climate Center,Lanzhou 73o020,Gansu,China; 3Lanzhou Meteorology Bureau,Lanzhou 73oo20,Gansu,China)

Abstract:Winter wheat is a major grain crop in Gansu Province, where precipitation is the most limiting factor for winter-wheat production. The uneven space-time distribution of precipitation results in perennial winter-wheat drought in the province.Therefore,it is of great significance to improve the accuracyand timeliness of drought monitoring in dryland agriculture in northwestern China.This could provide the needed scientific basis for decision-making departments to formulate agricultural-disaster prevention and mitigation measures in support ofregional food security.Inthe present study,we collcted multiyear data on soil-water content and winter-wheat fertility from three agronomic observatory stations as wellas daily observational data on meteorological elements for 43 winter-wheat-growing counties during 1971-2016. On the basis of soil-water content before sowing and on water budget for winter-wheat development stages,the crop water-budget index was revised,and the drought index for different grades was then determined.The correlation coeficient between the water-budget index and soil-water storage was 0.6522.The high correlation between the water-budget index for diferent growth periods and winter-wheat yield reduction rate passed a 0.01 test of significance.This showed that the modified water-budget index can accurately reflect winter-wheat drought for Gansu Province.Results of using ArcGIS to map the spatial distribution (including intensityand frequency）of drought at diferent wheat-growth stages in the years 1971-2016 show that the winter-wheat drought occurrence and range in Gansu Province increased with each growth stage from sowing to flowering.The drought distributions during the jointing and flowering periods were the the most widespread,occurring in central Gansu Province,north of Qingyang,west of Pingliang, west of Tianshui,and south ofLongnan.The frequency and level of drought in the mature （flowering） period decreased with increasing precipitation. Thus,the modified crop water-budget index objectively reflected winter-wheat drought in Gansu Province, thereby providing a reliable reference application.

Key words:drought monitoring；water budget index；winter wheat； soil water storage; Gansu Province