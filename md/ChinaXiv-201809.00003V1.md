# 开都-孔雀河流域水资源优化配置

王文辉²，黄粵¹，刘铁¹，孟凡浩²，刘蛟³(1．中国科学院新疆生态与地理研究所,荒漠与绿洲生态国家重点实验室,新疆 乌鲁木齐830011;2．中国科学院大学,北京100049；3．西华大学能源与动力工程学院,四川成都610039)

摘要：水资源是维持内陆河流域社会经济与生态环境协调发展的关键因素。针对水资源短缺现状，建立兼顾生态、生产和生活用水的优化配置方案是提高水资源利用效率、缓解供需矛盾的有效手段。本文以开都－孔雀河流域为研究区,采用二阶段区间优化算法,基于历史气象、水文、土地利用、社会经济等数据,构建水资源优化模型，,对市政用水、生态用水、工农服务业用水等进行年、月、旬多尺度优化配置。该方法结合区间、概率优化的特点,可准确分析多水源来水和多用户用水的不确定性，实现不同政策情景下的水资源最优配置。研究表明：流域市政、畜牧业和二三产业需水基本能够满足,缺水主要发生在农业、生态用水和塔里木河下游输水。在区域分配上,库尔勒与和静县农业缺水最为显著;生态缺水主要发生在博湖县和库尔勒市,塔里木河下游生态输水单元最为缺水,在高来水水平下仍缺水 $0 . 2 7 \times 1 0 ^ { 8 } \sim ~ 0 . 9 2 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ 。年内配水量最大发生在7月，最小为1月;9月缺水程度最高，农业和生态缺水量分别为 $0 . 3 6 \times 1 0 ^ { 8 } \sim 1 . 4 3 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 和 $0 . 9 0 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 。不同的水资源管理政策将导致流域系统收益发生明显变化，与其他政策情景相比,经济效益优先的情景下,系统能获得更高的用水收益，是相对最优的水资源配置方案。

关键词：二阶段区间优化算法；水资源；优化配置；政策分析；内陆河流域

干旱区经济发展和生态系统稳定高度依赖于可靠的水资源保障，水资源的盈缺状况和利用水平已成为评价人类社会与自然环境持续健康发展的重要指标[1-2]。干旱区水资源不合理开发利用将导致生态环境恶化,也制约了区域经济社会和谐发展(3]；水资源供需的协调性是影响流域稳定发展的关键问题,其分布不均是阻碍各行业健康发展的主要制约因素。近年来，对水资源高效利用的需求极大地推动了人们寻求水资源合理调配的深入探索，而“三生用水"（生产用水、生活用水和生态用水)是水资源配置的关键环节，对维持人类社会和自然环境和谐发展具有重要作用[4]

在水资源短缺且来水不确定性加剧的背景下，开展干旱区水资源合理规划、供需水分析预测、行业用水效益统计等工作具有重大意义。特别是在水资源优化配置方面，国内外学者针对不同流域区域特点,提出了很多有效方法。王浩等[5]基于水资源二元演化方法，提出了西北干旱区水资源优化配置的模式与计算方法;黄显峰等[将多目标混沌优化算法应用到水资源优化配置中，用来解决复杂水资源系统优化配置的问题;王峰等[以经济、环境、社会的综合效益最大化为目标，利用多目标规划方法建立了区域水资源优化配置方法。Huang 等[在两阶段随机规划（two-stage stochastic programming,TSP）的基础上引入了区间参数，提出了两阶段区间优化算 法（inexact two-stagestochasticprogramming,ITSP）,该算法能够处理气候、用水单元、水文过程等多重不确定性条件下的水资源配置问题。然而，目前研究多基于年或更长时间间隔对流域水资源进行优化配置，而对不确定性来水条件下的水资源配置中的季节变化关注较少[9],缺少精细尺度上（如月、旬)的优化配置方案[10]

开都-孔雀河(以下简称开孔河)是塔里木河流域主要的源流之一，流域人口约 $1 . 2 4 \times { { 1 0 } ^ { 6 } }$ 人，耕地面积 $4 . 1 6 \times 1 0 ^ { 4 } ~ \mathrm { h m } ^ { 2 }$ ,其下游灌区也是新疆重要的经济、粮食生产、生态保护区域之一;同时还肩负着向塔里木河干流下游生态恢复区输水的责任，水资源合理配置的重要性不言而喻。本研究选取开孔河流域作为研究区，采用二阶段区间优化算法(ITSP)，以开孔河流域历史水文、生态和社会经济等数据为基础，依据不同季节各个用水单元的需水要求，研究在多时间尺度（年、月、旬）下的水资源优化方案;考虑不同县（市)各种农作物灌溉定额和多种植被类型需水规律，实现水量配置的精细化，并分析经济发展优先、农业优先和生态保护等不同政策情景下的水资源时空配置与系统盈亏。所获得优化方案可以协调各行业用水关系，提高综合用水效益，为区域水资源管理提供有力的分析工具和决策依据。

# 研究区概况

开孔河流域位于新疆巴音郭楞蒙古自治州（简称巴州)境内，地处塔克拉玛干沙漠东北缘、塔里木盆地东北部，流域总面积为 $5 . 7 0 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ 。由于天山支脉阿克塔格的阻隔，形成了流域内焉耆盆地平原区和孔雀河冲积平原区两大地形地貌单元，地势由西北向东南倾斜（图1）。

![](images/ee3a0c5518e4682ff40454904487f6578431c27fceb269b6ab9a45bdc0b40720.jpg)  
图1研究区示意图  
Fig.1Sketch map of the study area

开孔河流域深居欧亚大陆腹地，距海洋较远，且位于天山南坡，北、西、南三面高山环绕，处于西来水汽的背风面，远离海洋，所以，此流域降水量明显少于天山北坡，属于干旱大陆性气候，具有四季分明，冬夏季较长，春秋季较短，且春季升温快，秋季降温快,以及昼夜温差大等特点[1]。与此同时,研究区内干旱少雨(焉耆盆地和孔雀河冲积平原多年平均降水量分别为 $5 4 \sim 7 7 ~ \mathrm { m m } . 4 7 \sim 7 5 ~ \mathrm { m m }$ ），日照时间长，蒸发量大（焉耆盆地和孔雀河冲积平原多年平均蒸发量分别为 $1 ~ 8 1 3 \sim 2 ~ 3 1 5 ~ \mathrm { m m } , 1 ~ 8 8 7 \sim 2 ~ 7 7 7$ mm）[12 -13]

据统计资料显示，流域主要地表水源来自开都河,占流域水资源总量的 $8 5 \%$ [14],其丰水期主要集中在6一8月（占全年的 $5 2 . 2 \%$ ），表1为开孔河大山口来水量概率水平分布。图2为大山口水文站各旬多年平均水资源量

表1不同来水水平划分  
Tab.1 Classification of inflow level   

<html><body><table><tr><td>水平划分</td><td>年径流量/(10m·a-1)</td><td>概率/%</td></tr><tr><td>L(低）</td><td>24.61~32.82</td><td>40</td></tr><tr><td>LM(中低）</td><td>33.55~34.39</td><td>10</td></tr><tr><td>M(中)</td><td>34.92~38.83</td><td>25</td></tr><tr><td>MH(中高)</td><td>39.74~43.43</td><td>15</td></tr><tr><td>H(高)</td><td>44.52~57.10</td><td>10</td></tr></table></body></html>

![](images/d1be8d82949ef8117f851cfba078dc3270cf312d831b4efe7a8b8239ef4442ca.jpg)  
图2大山口水文站各旬多年平均水量(1957—2011年)Fig.2Multi-year average inflow at Dashankou HydrometricStation（1957 -2011)

# 2 数据与方法

# 2.1 数据源与预处理

本研究采用的数据包括：1957—2011年开都河大山口水文站的历史流量数据（巴音郭楞蒙古自治州水利局），巴音布鲁克、巴伦台、焉耆等气象站1958—2013年日值气象数据（气象共享网http：//data.cma.cn/）;2010年土地利用/覆被数据（采用LandsatTM数据目视解译制成）;2010年MOD13Q1流域归一化植被指数(NDVI)数据，可获取流域内不同土地利用/覆被类型下的面积、分布和绿色植物生长状况信息；各县市主要农作物种植面积相应的灌溉定额，以及流域内各县（市）人口数据、三产产值和人均产值数据、牲畜头数和相应的市场价格等社会经济数据来源于《巴音郭楞蒙古自治州统计年鉴》。

# 2.2 二阶段区间优化算法(ITSP)

本文基于区间机会约束的二阶段优化模型，结合区间、机会优化的优点研究水资源配置，该模型既能处理确定性需水区间上下限，又能够处理不确定性随机来水量(15],通过将优化模型转化为符合确定期望上下限的最优机会配置，求解流域水量配置模型，得到期望目标最优的方案。有效处理不同情景下，承诺配水目标没有达到时的经济损失，解决模型参数为已知分布随机变量的优化问题[16]。在两阶段优化规划中，对优化配置模型中随机事件发生前后各做一次决策，减少因原决策不确定性带来的损失，以获得不同来水水平下的最优决策方案。

各旬区间约束的水资源优化配置函数如下[17]：

$$
\begin{array} { r } { f _ { \mathrm { m a x } } ^ { \pm } = \sum _ { i = 1 } ^ { m } B _ { i } ^ { ^ { \pm } } W _ { i } ^ { ^ { \pm } } - \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } P _ { j } C _ { i } ^ { ^ { \pm } } S _ { i j } ^ { ^ { \pm } } } \end{array}
$$

$$
\begin{array} { r } { \sum _ { i = 1 } ^ { m } \big ( \mathbf { \nabla } W _ { i } ^ { \pm } - S _ { i j } ^ { \pm } \big ) \leqslant q _ { j } ^ { \pm } , \mathbf { \nabla } \mathrm { V } i } \end{array}
$$

$$
S _ { i j } ^ { \pm } \leqslant W _ { i } ^ { \pm } \leqslant W _ { i \operatorname* { m a x } } ^ { \pm } , \ \forall i
$$

$$
S _ { i j } ^ { \ \pm } \geqslant 0 , \ \forall i , j
$$

式中 $: f _ { \mathrm { m a x } } ^ { \pm }$ 是系统净收益 ( ${ 1 0 } ^ { 4 }$ 元）； ${ B } _ { i } ^ { \pm }$ 用水项 $i$ 满足单位水量的净收益( $1 0 ^ { 4 }$ 元）； $\boldsymbol { W } _ { i } ^ { \pm }$ 是用水项 $\mathbf { \chi } _ { i }$ 的总需水量 $( \mathbf { m } ^ { 3 } ) { \mathop : } C _ { i } ^ { \pm }$ 是用水项 $i$ 没有得到单位水量时的惩罚( $1 0 ^ { 4 }$ 元）； $S _ { i j } ^ { \pm }$ 是在来水水平 ${ q _ { j } } ^ { \pm }$ 时用项 $\mathbf { \chi } _ { i }$ 没有得到满足的水量 $\left( { \bf \ m } ^ { 3 } \right)$ ； $\boldsymbol { W } _ { i \mathrm { m a x } } ^ { \pm }$ 为对用水单元 $i$ 所承诺的最大水量 $( \mathbf { m } ^ { 3 } ) : q _ { j } ^ { \pm }$ 是在 $j$ 来水水平时的水量 $\left( \mathbf { m } ^ { 3 } \right)$ ;$P _ { j }$ 表示来水水平是 $j$ 时的概率; $n$ 表示不同来水水平数； $m$ 是总的用水项数量。

由于公式中水资源规划目标 $\boldsymbol { W } _ { i } ^ { \pm }$ 必须在第一阶段设定，而缺水量则在第二阶段计算，因此称为两阶段线性优化模型。当 $\boldsymbol { W } _ { i } ^ { \pm }$ 被定义为区间形式的输入时，现有的线性模型解法不能直接求解。因此，水资源规划量可通过在模型中引入 $Z _ { i }$ 来求解。令${ \cal W } _ { i } ^ { \pm } = { \cal W } _ { i } ^ { - } + \Delta { \cal W } _ { i } Z _ { i }$ 取确定值,其中 $\Delta W _ { i } = W _ { i } ^ { + } - W _ { i } ^ { - }$ 且 $Z _ { i } \in \left[ 0 , 1 \right]$ 。当 $\boldsymbol { W } _ { i } ^ { \pm }$ 取值为其上限( $\mathbf { \mathcal { Z } } _ { i } = 1$ )，表明用水项 $i$ 的配水量为最大，系统收益将会最高，但却带来最大的系统风险。相反，当 $\boldsymbol { W } _ { i } ^ { \pm }$ 取值为其下界（ $\left| Z _ { i } = 0 \right|$ )时，表明用水项 $i$ 的配水量为最低，系统收益较低，相应的系统风险也比较小。经上下界分别计算求解，得到最优引水目标 $\boldsymbol { W } _ { i j \mathrm { o p t } } ^ { \pm }$ 和最优缺水量$S _ { i \mathrm { j o p t } } ^ { \pm }$ ,则优化配水量为 $A _ { i j \mathrm { o p t } } ^ { \pm } = W _ { i j \mathrm { o p t } } ^ { \pm } - S _ { i j \mathrm { o p t } } ^ { \pm }$ 。

本文定义的需水单元包括市政、畜牧业、二三产业、农业、生态(流域内)的5种用水行业以及向塔里木河下游生态输水；计算范围包括开孔河流域内5县(和静、和硕、焉耆、博湖、尉犁)1市(库尔勒），和塔里木河下游生态输水区。首先，考虑季节和物候的影响因素，确定所有需水单元的水量配置目标和上下限，分析各用水单元获得单位水量时的经济效益和水量未满足时的经济损失，即第一阶段规划目标的设定。然后，通过统计历史55a不同水平的来水量和水体蒸发等数据，确定各来水水平的概率及相应的各旬水资源量，通过二阶段区间优化方法，使各用水单元获得的综合净经济效益最大，计算随机来水情况下各县不同需水单元在不同用水时期的最优配水量目标和缺水量。

# 2.3参数配置

人畜用水在整个水量配置系统中具有最高的优先级，无论在何种情境下都是首要保证的，因此，水量满足时其经济效益大，水量未满足时损失也相对更高。此项用水量有相关的标准，生活用水定额按照《城市居民生活用水量标准》（GB/T50331-

2002)来确定，牲畜用水定额采用牲畜家禽用水量标准[18]。居民生活用水收益和损失系数在研究中采用人均生产总值，牲畜用水效益和损失系数则根据牲畜市场价值来计算。

工业、建筑业被称作第二产业，服务业又被称作第三产业。通过查阅统计年鉴，根据工业、建筑业和服务业生产总值和万元耗水量(19],计算二三产业需水量。一般来说万元耗水量和全年工业、建筑业和服务业生产总值随月份变化不大，因此，对全年各旬的水量按平均计算，代入优化算法。

研究区各县的作物面积和分布不同，灌溉方式也有差别。本文根据春小麦、冬小麦、高梁、棉花、向日葵、夏玉米、油菜、大豆、甜菜等新疆巴音郭楞蒙古自治州主要的农作物供水情况，基于这些农作物的全年灌溉定额[20]，结合生长期不同的需水量要求，计算各县各旬的农业灌溉需水量。根据灌溉定额、灌溉效率、渠道水损失率等参数确定灌溉毛引水量的上下限。农作物各旬产值系数则根据农业总产值与各旬水量比例的乘积计算得到。

NDVI指数因其较好地反映了植被空间分布和植物生长状况(2I],在本研究中,用来分析植被各月变化，进而采用面积定额法计算生态植被年需水总量。面积定额法主要是以某一地区类型植被的面积乘以其生态需水量定额，计算得到该类型植被的生态需水量，某地区各类型植被生态需水量之和即为该地区植被生态需水总量[4,22]。计算公式为：

$$
\begin{array} { r } { \mathbb { W } = \sum \mathbb { W } _ { i } = \sum A _ { i } \boldsymbol { r } _ { i } } \end{array}
$$

式中： $W$ 为植被生态需水总量 $( \mathbf { m } ^ { 3 } ) : W _ { i }$ 为植被类型$i$ 的生态需水量 $( \mathbf { m } ^ { 3 } ) { \ ; } A _ { i }$ 为植被类型的面积 $\left( \mathrm { { h m } } ^ { 2 } \right)$ ;$r _ { i }$ 为植被类型 $\mathbf { \chi } _ { i }$ 的需水定额 $( \mathrm { ~ m ~ } ^ { 3 } \cdot \mathrm { h m } ^ { - 2 }$ )。根据生态系统服务价值的研究(23-24],生态需水量满足时的经济效益和不满足时的损失根据单位面积不同覆被类型的产值系数(即生态系统服务价值)进行计算。

# 3 结果分析

# 3.1水资源年际优化配置结果

图3为流域各县（市）、各行业年需水量优化配置结果。

从全年统计分析来看，对于市政用水和畜牧业用水单元，在任意流量水平下，其用水需求都基本能够完全得到满足，缺水量为0；只有在低来水水平时市政配水量为 $0 . 9 8 \times 1 0 ^ { 8 } \sim 1 . 0 7 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ ,其他来水水平时均为 $1 . 0 7 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ ;牲畜饮水在各来水水平下优化配水量均为 $0 . 6 6 \times 1 0 ^ { 8 } { \mathrm { ~ m } } ^ { 3 } \cdot { \mathrm { ~ a ~ } } ^ { - 1 }$ 。对于二三产业用水，在低来水水平下，配水量为$4 . 4 0 \times 1 0 ^ { 8 } \sim 4 . 5 2 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ ,在其他来水水平下优化配水量均为 $4 . 5 2 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ 。对于农业用

L M □H 优化目标10 （a）上限 肉  
（-：g01g）/ 86420 的 H 中 d政牧 业 溉 态 政 牧 业 溉 态 政 牧 业 既 态 政 牧 业 溉 态 政 牧 业 溉 态 政 态市 畜 产 灌 生 市 畜 H 生 市 畜 云 生 市 畜产 灌 生 市 畜产 灌 生 市 畜 灌 生中 三三 三三 三 EE 输和静 和硕 焉耆 博湖 库尔勒 尉犁 水10  
·） 8 （b）下限6420 国 2 国 72 Z2态 政 牧 不 理市 畜饰 三5 三三 三三 输和静 和硕 焉耆 博湖 库尔勒 尉犁 水

水单元,水资源规划量在低、中、高流量水平下分别为 $3 . 4 3 \times 1 0 ^ { 8 } \sim 1 4 . 8 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 } \cdot 1 4 . 9 1 \times 1 0 ^ { 8 } \cdot$ ）$2 3 . 3 6 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \ \cdot \ \mathrm { a } ^ { - 1 }$ 和 $2 4 . 7 1 \times 1 0 ^ { 8 } \sim 2 5 . 3 5 \times 1 0 ^ { 8 }$ $\mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ ;对于流域内生态用水单元与塔里木河下游生态输水单元,在低、中、高流量水平下的配水量分别为 $1 . 1 0 ~ \times ~ 1 0 ^ { 8 } ~ \sim ~ 1 . ~ 2 7 ~ \times ~ 1 0 ^ { 8 } ~ \mathrm { { m } ^ { 3 } ~ \cdot ~ { \Large ~ a } ^ { - 1 } ~ }$ $1 . 3 3 \times 1 0 ^ { 8 } \sim 2 . 2 4 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } ~ \cdot ~ \mathrm { a } ^ { - 1 } ~ , ~ 5 . ~ 6 5 ~ \times ~ 1 0 ^ { 8 } ~ \sim$ （204号$6 . 8 2 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 和 $0 . 2 3 \times 1 0 ^ { 8 } \sim 0 . 6 1 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ：$\mathrm { ~ a ~ } ^ { - 1 } \ 、 0 . 6 2 \times 1 0 ^ { 8 } \sim 0 . 7 2 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 } \ 、 1 . 4 4 \times 1 0 ^ { 8 } \sim$ （204号$2 . 0 9 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 。表明缺水主要发生在农业和生态用水单元。这是由于农业和生态输水所需水量占到流域总用水量的 $7 5 \%$ 以上，而市政、畜牧业和二三产业每单元用水量则能够带来更高的系统收益。因此，当水量不足以满足所有用水单元的需求时，由于市政、畜牧业和二三产业能够带来更高的单位用水收益，因而要先满足这几个用水单元的需求，然后依次满足农业、生态和塔里木河下游输水的需求。因为其水资源的需求量较低，同时具有较高的用水优先权，所以，市政用水、畜牧业和二三产业用水单元的用水需求很容易满足而不发生缺水，缺水情况主要发生在农业、生态和塔里木河下游输水部分。

在水资源的区域分配上，当水量不足时，库尔勒与和静县农业缺水量在低、中、高来水水平下分别为（204 $5 . 6 6 \times 1 0 ^ { 8 } \sim 9 . 8 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } \mathrm { ~ } _ { \mathrm { ~ v } } 0 . 6 3 \times 1 0 ^ { 8 } \$ ）（20 $\mathrm { ~ 5 . ~ 2 3 \times 1 0 ^ { 8 } ~ m ^ { 3 } ~ \bullet ~ a ^ { - 1 } ~ . ~ 0 ~ } \sim 0 . \ 2 2 6 \ \times 1 0 ^ { 8 } \ \mathrm { m ^ { 3 } } \ \bullet \mathrm { ~ a ^ { - 1 } ~ }$ 和（204 $3 . 6 5 \times 1 0 ^ { 8 } \sim 4 . 4 2 \times 1 0 ^ { 8 } \mathrm { ~ m ~ } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 } \cdot 1 . \mathrm { ~ 0 8 ~ } \times 1 0$ $3 . 6 6 \times 1 0 ^ { 8 } ~ \mathrm { { m } ^ { 3 } ~ \cdot ~ a ~ ^ { - 1 } ~ , 0 ~ \sim 0 . ~ 3 1 ~ \times 1 0 ^ { 8 } ~ \mathrm { { m } ^ { 3 } ~ \cdot ~ a ~ ^ { - 1 } ~ } }$ ;其次是生态用水，主要发生在博湖县、库尔勒市，在低、中、高来水水平下分别为 $2 . 2 0 \times 1 0 ^ { 8 } \sim 2 . 3 0 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ·a−¹、2.03 ×10\~2.15×10m³·a-1、0.25×10\~

$0 . 6 9 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ 和 $1 . 4 0 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 } \cdot 1 . 0 7 \times$ $1 0 ^ { 8 } \sim 1 . ~ 4 0 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } \cdot \mathrm { ~ a } ^ { - 1 } \setminus 0 . ~ 0 5 \times 1 0 ^ { 8 } \sim 0 . ~ 2 9 \times$ $1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ ;塔里木河下游生态输水缺水最为严重,在高来水水平下仍缺水 $0 . 2 7 \times 1 0 ^ { 8 } \sim 0 . 9 2 \times 1 0 ^ { 8 }$ $\mathbf { m } ^ { 3 } \cdot \mathbf { a } ^ { - 1 }$ 。

# 3.2水资源各月优化配置结果

图4为各县市水资源优化配置的季节分布情况。从水量分配结果来看，在中等来水水平下，配水量最大发生在7月，其中和静、和硕、焉耆、博湖、库尔勒、尉犁县（市）配水量分别为 $0 . \ 0 6 \times 1 0 ^ { 8 } \ \sim$ 1$0 . 9 4 \times 1 0 ^ { 8 } ~ \mathrm { ~ m ~ } ^ { 3 }$ 、0.53 × 10°\~ 0. $5 7 \ \times \ 1 0 ^ { 8 } \ \mathrm { ~ m } ^ { 3 }$ 、$0 . 5 9 \times 1 0 ^ { 8 } \sim 0 . 6 2 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \mathrm { , 0 . 1 5 \times 1 0 ^ { 8 } \sim 0 . 5 6 \times 1 0 ^ { 8 } }$ （204号$\mathrm { m ^ { 3 } } \mathrm { \Omega } _ { \mathrm { { \perp } } } \mathrm { 1 } . 8 2 \times 1 0 ^ { 8 } \mathrm { \Omega } \sim 2 . 3 8 \times 1 0 ^ { 8 } \mathrm { \Omega m ^ { 3 } } \mathrm { \Omega } _ { \mathrm { { \perp } } } 0 . 6 2 \times 1 0 ^ { 8 } \mathrm { \Omega } \sim 0 . 6 7 \mathrm { \Omega } \times$ $1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ;塔里木河下游生态输水需求依然无法得到完全满足,缺水量为 $0 \sim 0 . 0 2 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 。最小配水量发生在2月,6县(市)配水量分别为 $0 . 0 8 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ 、$0 . 0 5 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \setminus 0 . 0 5 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \setminus 0 . 0 6 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \setminus 0 . 4 3 \times$ $1 0 ^ { 8 } \sim 0 . 4 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \setminus 0 . 0 6 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ;由于冬季无灌溉且生态用水减少，水资源量相对丰富，塔里木河下游输水竞争压力小，配水量为 $0 . \ 1 4 \times 1 0 ^ { 8 } \sim 0 . 1 6 \times$ （204号 $1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 。

图5为中等来水水平下，开孔河流域各行业配水量的季节分布情况。其中，配水量最大的7月，市政、畜牧、二三产业、农业与生态单元的配水量分别为 $\mathrm { ~ / ~ 0 . ~ 0 9 ~ \times ~ 1 0 ^ { 8 } ~ } \mathrm { ~ m ^ { 3 } ~ } \mathrm { ~ } \mathrm { , ~ } 0 . \mathrm { ~ 3 8 ~ } \times 1 0 ^ { 8 } \mathrm { ~ m ^ { 3 } ~ } \mathrm { , ~ } 0 . \mathrm { ~ 0 6 ~ } \times 1 0 ^ { 8 } \mathrm { ~ m ^ { 3 } ~ }$ 、$3 . 2 4 \times 1 0 ^ { 8 } \sim 4 . 8 3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } , 0 \sim 0 . 3 8 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ;配水量最小的1月，各行业优化配水量分别为 $0 . 0 9 \times 1 0 ^ { 8 }$ $\mathrm { m ^ { 3 } } \setminus 0 . 3 8 \times 1 0 ^ { 8 } \mathrm { m ^ { 3 } } \setminus 0 . 0 6 \times 1 0 ^ { 8 } \mathrm { m ^ { 3 } } \setminus 0 . 0 4 \times 1 0 ^ { 8 } \mathrm { m ^ { 3 } }$ 。9月综合缺水最为显著，其中又以农业和生态缺水量最大，分别为 $0 . \ 3 6 \times 1 0 ^ { 8 } \sim 1 . \ 4 3 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 和$0 . 9 0 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 。

![](images/62af2b71ef5db723d3765d511398871f601911f7425249ec2ecd86c7a92e265d.jpg)  
图4各县(市)各月优化配水量  
Fig.4Optimized monthly water volumes for all the counties（cities)

# 3.3水资源旬优化配置结果

春汛期(以4月下旬为例)和夏汛期(7月下旬为例)是水资源量明显变化的时期，同时也是各地区各行业(尤其是农业和生态)用水的重要时期，图6为中等来水水平下4月下旬与7月下旬各县市水量优化配置结果。

中等来水水平下，4月下旬流域来水量为$1 . 6 4 \times 1 0 ^ { 8 } \sim 2 . 5 1 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ,和静、和硕、焉耆、博湖、库尔勒、尉犁配水量分别为 $0 . 0 2 \times 1 0 ^ { 8 } \sim 0 . 2 1 \times 1 0 ^ { 8 }$ $\mathrm { m ^ { 3 } } \setminus 0 . \ 1 1 \ \times \ 1 0 ^ { 8 } \ \mathrm { m ^ { 3 } } \ \setminus 0 . \ 1 2 \ \times \ 1 0 ^ { 8 } \ \mathrm { m ^ { 3 } } \ \setminus 0 . \ 0 4 \ \times \ 1 0 ^ { 8 } \ \sim \$ （$0 . \mathrm { 0 9 \times 1 0 ^ { 8 } ~ m ^ { 3 } ~ } \mathrm { { , } } 0 . 3 9 \times 1 0 ^ { 8 } \sim 0 . 5 0 \times 1 0 ^ { 8 } ~ \mathrm { { m ^ { 3 } } } ~ \mathrm { { , } } 0 . 1 2 \times 1 0 ^ { 8 }$ $\mathbf { m } ^ { 3 }$ ;塔里木河下游生态输水需求依然无法得到完全满足,缺水量为 $0 . 0 5 2 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 。其中,博湖县缺水最为显著,缺水量为 $0 . 0 4 \times 1 0 ^ { 8 } \sim 0 . 1 2 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } ,$ 7月下旬,流域来水量为 $3 . 7 7 \times 1 0 ^ { 8 } \sim 5 . 7 5 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ，和静、和硕、焉耆、博湖、库尔勒、尉犁配水量分别为$0 . 0 2 \times 1 0 ^ { 8 } \sim 0 . 3 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \setminus 0 . 1 9 \times 1 0 ^ { 8 } \sim 0 . 2 3 \times 1 0 ^ { 8 }$ $\mathrm { m ^ { 3 } } \setminus 0 . 2 1 \times 1 0 ^ { 8 } \sim 0 . 2 4 \times 1 0 ^ { 8 } \mathrm { m ^ { 3 } } \setminus 0 . 0 1 \times 1 0 ^ { 8 } \sim 0 . 2 7 \times$ （204号$1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \ \mathrm { _ { \circ } } 0 . 7 1 \times 1 0 ^ { 8 } \ \sim 0 . \ 9 1 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \ \mathrm { _ { \circ } } 0 . \ 2 4 \times 1 0 ^ { 8 } \ \sim$ （204号$0 . 2 7 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 。其中博湖县缺水量最大,为 $0 \sim$ $0 . 2 7 \times 1 0 ^ { 8 } \ \mathrm { ~ m ~ } ^ { 3 }$ ;塔里木河生态输水的缺水量为$0 . 0 6 \times 1 0 ^ { 8 } \sim 0 . 0 8 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } ,$ 。

![](images/94e5867a9bcff61012cc29732e7728a5f77e4aed4b3f9e9e55a6a34471479971.jpg)  
Fig.5Optimized monthly water volumes for different industries

![](images/654859ec3948b2ed000a81d2a2d12c184c9224ee252ef37b863fce3ee46c65e0.jpg)  
图5各月各行业优化配水量  
图6各县4月、7月下旬不同来水水平优化配水量  
Fig.6Optimized water volumes for all the counties in April and July

□市政□畜牧二三产业日灌溉生态1.5 (a)4月下旬上限 1.5 [ (b)4月下旬下限  
10 二 一 7 自 国 一L LM M MH H L LM M MH H1.5 (c)7月下旬上限 （2 1.5 (d)7月下旬下限  
0 050 2 自 国 目 8 0 目L LM M MH H L LM M MH H

![](images/994472f31ee2ab96b944a3fe7e774f09ecd65e03504f63d8965b0c5a6319fddb.jpg)  
图7各行业4月、7月下旬不同来水水平优化配水量  
Fig.7Optimized water volumes for different industries in April and July   
图83种情景各县(市)各行业配水量比较  
Fig.8Compared results of redistributed water volumes for diffrent industries under different conditions

中等来水水平下，4月下旬，市政、二三产业、畜牧、农业与生态单元的配水量分别为 $0 . 0 3 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 、1.24×10m²、0.02 ×10m²、0.02×10\~0.97×108$\mathrm { m } ^ { 3 } \ 、 0 \sim 0 . 0 1 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ （图7）。其中，生态缺水最为明显,缺水量为 $0 . 1 2 \times 1 0 ^ { 8 } \sim 0 . 1 3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ 。7月下旬，市政、二三产业、畜牧、农业与生态单元的配水量分别为 $0 . 0 3 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot 1 . 3 6 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot 0 . 0 2 \times 1 0 \ \mathrm { m } ^ { 3 }$ 、

$1 . 1 8 \times 1 0 ^ { 8 } \sim 1 . 7 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \mathrm { , 0 . 1 2 } \times 1 0 ^ { 8 } \sim 0 . 3 5 \times 1 0 ^ { 8 }$ $\mathbf { m } ^ { 3 }$ 。其中,农业缺水最为显著,缺水量为 $0 \sim 0 . 5 7 \times$ $1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 。

# 4讨论

本研究中定义了3种不同水资源政策情景，其中 $\textcircled{1}$ 情景1：经济效益最大的水资源规划政策，即着力发展对区域GDP贡献最大的二三产业，并全力满足其用水需求； $\textcircled{2}$ 情景2：农业发展优先的水资源规划政策，即提高农业生产用水的优先等级； $\textcircled{3}$ 情景3：保护生态环境的水资源规划政策，即提高流域生态用水的优先等级。结果表明，不同的水资源管理政策会导致规划目标、缺水量、系统收益和损失的变化。

表23种情景下综合效益比较  
Tab.2Comparison of comprehensive benefits under different conditions   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">上限</td><td colspan="3">下限</td></tr><tr><td>经济优先</td><td>农业发展优先</td><td>生态保护</td><td>经济优先</td><td>农业发展优先</td><td>生态保护</td></tr><tr><td>和静</td><td>485.22</td><td>305.16</td><td>375.09</td><td>160.49</td><td>80.64</td><td>121.22</td></tr><tr><td>和硕</td><td>83.28</td><td>70.75</td><td>76.66</td><td>31.64</td><td>24.67</td><td>27.4</td></tr><tr><td>焉耆</td><td>184.81</td><td>100.18</td><td>130.88</td><td>74.95</td><td>32.6</td><td>53.47</td></tr><tr><td>博湖</td><td>79.56</td><td>46.63</td><td>61.78</td><td>32.95</td><td>17.75</td><td>25.74</td></tr><tr><td>库尔勒</td><td>2 327.33</td><td>527.57</td><td>1 222.23</td><td>1 162.61</td><td>270.14</td><td>715.92</td></tr><tr><td>尉型</td><td>202.85</td><td>161.7</td><td>175.81</td><td>54.11</td><td>32.85</td><td>42.72</td></tr><tr><td>塔里木河下游输水</td><td>0.06</td><td>0.01</td><td>0.31</td><td>0.01</td><td>0.03</td><td>0.06</td></tr><tr><td>市政</td><td>9.44</td><td>9.44</td><td>9.44</td><td>7.67</td><td>7.67</td><td>7.67</td></tr><tr><td>畜牧</td><td>716.01</td><td>716.01</td><td>716.01</td><td>177. 32</td><td>177.32</td><td>177. 32</td></tr><tr><td>二三产业</td><td>2 632.53</td><td>486.45</td><td>1 306.33</td><td>1 329.32</td><td>274.38</td><td>798.23</td></tr><tr><td>灌溉</td><td>3.79</td><td>6.44</td><td>2.45</td><td>2.46</td><td>2.89</td><td>1.36</td></tr><tr><td>生态</td><td>1.29</td><td>0.16</td><td>8.21</td><td>1.17</td><td>-0.03</td><td>1.89</td></tr></table></body></html>

从图8可以看出，在情景1、情景2和情景3下，农业用水单元在低径流水平时优化水资源量分别为$3 . 4 3 \times 1 0 ^ { 8 } \sim 1 4 . 8 4 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } . 5 . 3 7 \times 1 0 ^ { 8 } \sim 1 6 . 8 6 \times$ $1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 和 $3 . 6 6 \times 1 0 ^ { 8 } \sim 1 4 . 6 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ;在中径流水平时优化水资源量分别为 $1 4 . 9 1 \times 1 0 ^ { 8 } \sim 2 3 . 3 6 \times 1 0 ^ { 8 }$ $\mathrm { m ^ { 3 } } \ 、 1 6 . 9 3 \times 1 0 ^ { 8 } \sim 2 6 . 2 9 \times 1 0 ^ { 8 } \mathrm { m ^ { 3 } }$ 和 $1 2 . 8 0 \times 1 0 ^ { 8 }$ \~$2 2 . 1 6 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ;在高径流水平时优化水资源量分别为 $2 4 . 7 1 \times 1 0 ^ { 8 } \sim 2 5 . 3 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } . 3 2 . 1 3 \times 1 0 ^ { 8 } \sim$ （20（20 $3 4 . 5 5 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 和 $2 3 . 2 4 \times 1 0 ^ { 8 } \sim 2 5 . 6 0 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,情景2下农业配水量在各来水水平下均为最高。对于生态用水，配水量均在情景3下最大，分别为 $1 . 9 9 \times$ $1 0 ^ { 8 } \sim 2 . 7 1 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \ 、 4 . 6 7 \times 1 0 ^ { 8 } \sim 4 . 7 0 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ 和$9 . 8 5 \times 1 0 ^ { 8 } \sim 1 0 . 5 4 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 。在情景1和情景3下,当来水量不足时，塔里木河下游输水量首先显著减少（由于生态输水单位水量产生的系统收益最小），来水量进一步减少时，生态用水单元缺水量也明显增加;情景2下,当来水量不足时,塔里木河下游输水和生态用水减少显著程度相当，当水量进一步减少时，塔里木河下游缺水下降到最低，生态和灌溉缺水才逐渐增多。

同时，不同的水资源管理政策将导致不同的系统收益（当水资源规划完成时)和惩罚（缺水发生时)。例如,情景1、情景2和情景3下，系统净收益为 $1 \ 5 1 6 . \ 7 6 \times 1 0 ^ { 8 } \sim 3 \ 3 6 3 . \ 1 1 \times 1 0 ^ { 8 }$ 元、 $4 5 8 . 6 8 \times$ $1 0 ^ { 8 } \sim 1 ~ 2 1 2 . 0 0 \times 1 0 ^ { 8 }$ 元和 $9 8 6 . 5 2 \times 1 0 ^ { 8 }$ 新 $2 ~ 0 4 2 . 7 6 \times$ $1 0 ^ { 8 }$ 元。结果表明,农业发展或经济优先情景下的系统净收益有较大的提升;在经济优先情景下，系统净收益高于农业优先情景和生态保护情景,是相对最优的配水方案（表2）。

# 5结语

本文以开都孔雀河流域为研究区，采用二阶段区间优化算法，基于历史气象、水文、土地利用、社会经济等数据，构建水资源优化模型，对市政用水、生态用水、畜牧业和工农服务业用水等耗水单元进行年、月、旬多尺度优化配置。

（1）市政、畜牧业和二三产业均能满足用水需求，而缺口主要发生在农业灌溉和生态用水，并以塔里木河下游输水缺水量最为显著，在中等来水下农业、生态、塔里木河下游输水的缺水量分别为 $1 . 9 9 \times$ $1 0 ^ { 8 } \sim 1 0 . 4 4 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 } \cdot 5 . 0 8 \times 1 0 ^ { 8 } \sim 5 . 9 8 \times 1 0 ^ { 8 }$ $\mathrm { ~ \bf ~ m ^ { 3 } ~ } \bullet \mathrm { ~ \bf ~ a ~ } ^ { - 1 } \mathrm { ~ \bf ~ \ l ~ } . 6 4 \times 1 0 ^ { 8 } \mathrm { ~ \bf ~ \sim ~ } 1 . 7 3 \times 1 0 ^ { 8 } \mathrm { ~ \bf ~ m ^ { 3 } ~ } \bullet \mathrm { ~ \bf ~ a ~ } ^ { - 1 } \mathrm { ~ \bf ~ \Omega ~ }$ ：。

（2）库尔勒与和静县农业缺水最显著，中等来水下分别缺水 $0 . ~ 6 3 ~ \times 1 0 ^ { 8 } ~ { \sim } ~ 5 . ~ 2 3 ~ \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } ~ { \cdot } ~ \mathrm { a } ^ { - 1 }$ 、$1 . 0 8 \times 1 0 ^ { 8 } \sim 3 . 6 6 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } \cdot \mathrm { \ a } ^ { - 1 }$ ;博湖县和库尔勒市生态缺水最显著，中等来水下分别为分别缺水 $0 . 6 3 \times$ $1 0 ^ { 8 } \sim 5 . 2 3 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 } \ 、 1 . 0 8 \times 1 0 ^ { 8 } \sim 3 . 6 6 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ：a-。

（3）7月全区总配水量最大，中等来水水平下为 $3 . 7 7 \times 1 0 ^ { 8 } \sim 5 . 7 5 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ,最小发生在2月，为$0 . 8 9 \times 1 0 ^ { 8 } \sim 0 . 9 1 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } , 9$ 月缺水量最大，为$1 . 5 0 \times 1 0 ^ { 8 } \sim 2 . 5 8 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } .$ 。

（4）在经济效益优先、农业发展优先和生态保护3种情景下，中等来水水平下总配置水量分别为$2 3 . 1 1 \times 1 0 ^ { 8 } \sim 3 2 . 5 6 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 } \cdot 2 0 . 7 8 \times 1 0 ^ { 8 } \sim$ $3 0 . \ 1 3 \ \times \ 1 0 ^ { 8 } \ \mathrm { ~ m } ^ { 3 } \cdot \ \mathrm { a } ^ { - 1 } \ , \ 2 3 . \ 2 1 \ \times \ 1 0 ^ { 8 } \ \sim \ 3 2 . \ 7 0 \ \times$ $1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ ;所获得的经济和生态综合效益分别为$1 ~ 5 1 6 . 7 6 \times 1 0 ^ { 8 } \sim 3 ~ 3 6 3 . 1 1 \times 1 0 ^ { 8 }$ 元、 $. 4 5 8 . 6 8 \times 1 0 ^ { 8 }$ \~$1 2 1 2 . 0 0 \times 1 0 ^ { 8 }$ 元和 $9 8 6 . 5 2 \times 1 0 ^ { 8 } \sim 2 \ 0 4 2 . 7 6 \times 1 0 ^ { 8 }$ 元。

研究中考虑了各季节来水与各县（市）用水的不确定性，量化各用水单元的收益与损失，并计算了不同政策情景下的优化配置方案，为缺水地区水资源分配提供了依据。但是，该模型输入水资源量和各耗水单元需水量基于历史统计获得，后续研究将结合流域水文模型，增加对未来气候变化和土地利用变化背景下的水资源配置和预测

# 参考文献（References）：

[1]赵翔,陈吉江,毛洪翔.水资源与社会经济生态环境协调发展 评价研究[J].中国农村水利水电,2009（9）：58-62.〔Zhao Xiang,Chen Jijiang,Mao Hongxiang.An evaluation of the coordinated development of water resources,social economy and eco-environment[J].China Rural Water and Hydropower,2Oo9（9）:58 -62.]   
[2]邓清海,潘国营,贾军辉,等.基于GIS 的水资源优化管理信息 系统——以濮阳市水资源管理为例[J].干旱区研究,2004,21 (1）:17-2O.[Deng Qinghai,Pan Guoying,Jia Junhui,et al.GISbased optimized management information system of water resources:A case study on the management of water resources in Puyang[J].Arid Zone Research,2004,21(1）:17-20]   
[3]鲍超,方创琳.干旱区水资源开发利用对生态环境影响的研究 进展与展望[J].地理科学进析展,2008,27（3）;38-46.［Bao Chao,Fang Chuanglin.Impact of water resources exploitation and utilization on eco-environment in arid area:Progress and prospect [J].Progress in Geography,2008,27(3）:38-46.]   
[4] 杨爱民，唐克旺，王浩，等.生态用水的基本理论与计算方法 [J].水利学报,2004,35（12）:39-45.[Yang Aimin,Tang Kewang,Wang Hao,et al.Theory and calculation method of ecological water use[J].Journal of Hydraulic Engineering,20O4,35(12）:39 -45.]   
[5]王浩,秦大庸,郭孟卓,等.旱区水资源合理配置模式与计算方 法[J].水科学进展,2004,15（6）:689-694.[Wang Hao,Qin Dayong,Guo Mengzhuo,et al.Mode and calculation method for rational water resources allocation in arid zone[J].Advances in Water Science,2004,15(6) :689-694.]   
[6] 黄显峰，邵东国，顾文权，等.基于多目标混沌优化算法的水资 源配置研究[J].水利学报,2008,39（2）：183－188.[Huang Xianfeng,Shao Dongguo,Gu Wenquan,et al. Optimal water resources deployment based on multi-objective chaotic optimization algorithm[J].Journal of Hydraulic Engineerin,2008,39(2）:183 -188.] 〔7］王峰,李树荣,杨亭亭.区域水资源区间多目标规划模型及求 解[J].水电能源科学,2011,29（4）:35-37.[Wang Feng,Li Shurong,Yang Tingting.Regional water resource interval multi-objective programming model and its solution[J]. Intermational Journal Hydroelectric Energy,2011,29(4）:35-37.] [8]Huang G H,Loucks D P.An inexact two-stage stochastic programming model for water resources management under uncertainty[J]. Civil Engineering Systems,2000,17(2）:95-118. [9]黄世华,张世挺,秦燕燕,等.张掖地区1951—2010 年逐月 SPI 分析及年内水资源配置〔J].兰州大学学报（自然科学版），   
2013（4）:511-514.[Huang Shihua,Zhang Shiting,Qin Yanyan, et al.Monthly SPI and water resource allocation in Zhangye Area within the years of 1951-2010[J].Journal of Lanzhou University （Natural Sciences Edition）,2013（4）:511-514.] [10］赵喜富.基于“三条红线”的滨海地区水资源优化配置研究 [D].济南：山东大学,2015.[Zhao Xifu.Study on Optimization Allocation of Water Resources Based on“Three Line”Constraint in Coastal Area[D]. Jinan:Shandong University,2015.] [11］王维霞,王秀君,姜逢清,等.近30a来开都河上游径流量变化 的气候响应[J].干旱区研究,2013,30(4）:743－748.[Wang Weixia,Wang Xiujun,Jiang Fengqing,etal.Response of runoff volume to climate change in the Kaidu River Basin in recent 30 years[J].Arid Zone Research,2013,30(4）:743-748.] [12］陈大春.新疆焉耆盆地地表水、地下水联合调度应用研究 〔D].乌鲁木齐:新疆农业大学,2000.[Chen Dachun.A Application Study of Surface Water & Groundwater United Optimization and Deposition on Xinjiang Yanqi Basin[D]. Urumqi: Xinjiang Agricultural University,2000.] [13］李卫红,陈忠升,李宝富,等.新疆开都-孔雀河流域绿洲需水 量与稳定性分析[J].冰川冻土,2012,34(6)：1470-1 477. [Li Weihong,Chen Zhongsheng,Li Baofu,et al.Analysis of water demand and stability for oasis in Kaidu-Kong-que river basin, Southern Xinjiang〔J].Journal of Glaciologyand Geocryology,   
2012,34(6) :1 470-1 477.] ［14］王水献.开孔河流域绿洲水土资源开发及其生态环境效应研 究[D].乌鲁木齐：新疆农业大学,2008.[Wang Shuixian.Study on Effect of Oasis Water and Land Resources Development and Environment in Kaidu-Kongque Basin[J]. Urumqi: Xinjiang Agricultural University,2008.] [15］刘三省,尹建光,李薇,等.基于区间机会约束规划的滨州新区 水资源优化配置[J].水电能源科学,2014（7）：28－32.［Liu Sanxing,Yin Jianguang,Li Wei,et al. Water resources optimization allocation of Binzhou new district based on interval chance constrained programming[J]. Water Resources and Power,2014（7） :   
28-32.] [16］李琳琳.基于区间二阶段随机规划的多水源优化配置[J].黑 龙江水利科技,2015,43（11）：10-13.［LiLinlin.Multi-water source optimization based on inexact two-stage stochastic programming[J]. Heilongjiang Science and Technologyof Water Conservancy,2015,43（11) :10-13.] [17]Huang Y,Chen X,Li Y,et al.A simulation-based two-stage interval-stochastic programming model for water resources management in Kaidu-Konqi watershed,China[J].Journal of Arid Land,2012,   
4(4):390 -398.   
[18]张家凤,陈亚宁，李卫红，等.开都河-孔雀河流域水资源需求 分析[J].新疆农业科学,2011,48（10）:1929-1935.[Zhang Jiafeng,Chen Yaning,LiWeihong,etal.Thedemend Analysisof waterresources in Kaidu river-Kongque river drainage basin[J]. Xinjiang Agricultural Sciences,2011,48（10） :1 929-1 935.]   
[19］任建民，孙文，顾明林.中国西部地区水资源开发利用与管理 [M].郑州：黄河水利出版社.2012.［RenJianmin,SunWen,Gu Minglin.Water Resources Development Utilization and Management in Western China[M].Zhengzhou:The Yellow River Water Conservancy Press,2012.]   
[20]王忠，周和平，张江辉.新疆农业用水定额技术研究应用[M]. 北京：中国农业科学技术出版社,2012.［Wang Zhong,Zhou Heping,Zhang Jianghui.Research and Application of Agricultural WaterQuota Technology in Xinjiang[M].Beijing:China Agriculturalscience and Technology Press,2012.]   
[21]王柳,段英.利用遥感影像进行植被分布分析[J].测绘与空间 地理信息,2012,35（3）：140-142.［WangLiu,DuanYing.Analysis of the vegetation distribution based on the remote sensing

image[J].Geomatics& Spatial Information Technology,2O12,35

(3):140-142.]  
[22]胡广录,赵文智.干旱半干旱区植被生态需水量计算方法评述[J].生态学报,2008,28（12）:6282-6291.[HuGuanglu ZhaoWenzhi.Reviews on calculating methods of vegetation ecologicalwaterrequirement in arid and semiarid regions[J].Acta EcologicaSinica,2008,28(12):6 282-6 291.]  
[23]谢高地，张彩霞,张雷明，等.基于单位面积价值当量因子的生态系统服务价值化方法改进[J].自然资源学报，2015，30（8）：1 243-1 254.[Xie Gaodi,Zhang Caixia,Zhang Leiming,et al.Improvement of the evaluation method for ecosystem service valuebased on per unit area[J].Journal of Natural Resources,2O15,30(8):1 243 -1 254.)  
[24]谢高地，甄霖,鲁春霞，等.一个基于专家知识的生态系统服务价值化方法[J].自然资源学报，2008，23（5）：911-919.［XieGaodi,Zhen Lin,Lu Chunxia,etal.Expert knowledge based valua-tion method of ecosystem services in China[J].Journal of NaturalResources,2008,23(5):911-919.]

# Optimized Redistribution of Water Resources in the Kaidu-Kongque River Basin

WANG Wen-hui $^ { 1 , 2 }$ ，HUAGN Yue’，LIU Tiel， MENG Fan-hao $^ { 1 , 2 }$ ，LIU Jiao³ (1.State KeyLaboratoryof Desert and Oasis Ecology,Xinjiang Instituteof Ecologyand Geography,ChineseAcademyof Sciences,Urumqi 830011,Xinjaing,China; 2. University of Chinese Academy of Sciences,Beijing 100049,China ; 3．School of Energy and Power Engineering,Xihua University,Chengdu 61o039,Sichuan,China)

Abstract：Waterresources is the keyfactor to maintaina harmonious social,economicand ecological development in inlandriver basin.To establishanoptimal plan ofredistributing water resources isan efective method for impro vingthe effciency of water resources utilization and alleviating the contradiction between water resources supply and demand basedon thecurent situation of water shortage in the study area.In this paper,the Kaidu-Kongque Watershed was considered as the research area,and the two-stage interval optimization algorithm was used to develop a model of optimizing waterresources basedonthe historical,meteorological,hydrological,landuse,social and economic data,and the optimized modes ofredistributing water resources forthe various industries were caried out.On which theuncertainties of inflow sources and water users could be exactly analyzed,andan optimized redistribution of water resources could be achieved.The results showed that the water consumptions for the urban residents,animal husbandry and secondaryand tertiary industries could bebasicallsatisfied,and the water shortage occurred mainly in agriculture,ecologyand ecologic water conveyance to the lower reaches of the Tarim River.Regionaly,the water shortage in agriculture occurred mainly in Korla Cityand Hejing County,theecological water shortage occurred mostly in Bohu County and Korla City,and the water shortage is the most serious and as high as $0 . 2 7 \times 1 0 ^ { 8 } - 0 . 9 2$ （20 $\times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 } \cdot \mathrm { ~ a ~ } ^ { - 1 }$ in high-inflow year in the lower reaches of the Tarim River.The highest and lowest water shortages occurred in Julyand January respectively;the most serious water shortage occurred in September,and the water shortage volumes for agriculture and ecology were $0 . 3 6 \times 1 0 ^ { 8 } - 1 . 4 3 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ and $0 . 9 0 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ respectively. Different water management policies could lead to the significant changes of benefits in stream system.Compared with other policy scenarios,the system under the priority of economic benefits could obtain a high water use effciency.

Key words：two-stage interval optimization algorithm;water resources;optimized water redistribution;policy analysis;inland drainage basin