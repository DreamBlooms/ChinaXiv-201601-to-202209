# 数据驱动的通勤团体配对共享停车方法研究

何梦园，刘正熙，熊运余，李征(四川大学 计算机学院，成都 610000)

摘要：随着机动车保有量日益增加，停车难愈发成为城市的通病，但当上班地点停车场大排长龙时，周边居住区车位却大量处于空闲状态，车位资源却得不到合理利用。而现有的共享停车方法由于其随机性实施难度较大，为减少其随机性，降低共享停车的实施难度以及减少车位资源的浪费，基于毗邻办公楼与居住区的通勤团体之间出行时间具有的天然互补性，提出数据驱动的一对一的配对共享的解决方案。通过分析车场车辆进出记录数据对问题进行求解，分析进出口数据，得到关于居住区车位的空闲时长特征与办公楼车辆的使用时长特征，进而根据时长最大化的匹配方法得到配对车位与车辆。针对选取的停车场进行实验，完全匹配的车位占比 $3 7 . 6 6 \%$ ,所有匹配车位利用率平均提高 $1 5 . 2 4 \%$ ，其中最大提高 $5 7 . 8 4 \%$ 。结果表明配对共享具有较大可行性。

关键词：城市交通；共享停车；数据分析；车位配对；居住区共享中图分类号：U491 doi:10.19734/j.issn.1001-3695.2018.05.0503

# Research on paired shared parking for commuter groups dirven by data

He Mengyuan, Liu Zhengxi†, Xiong Yunyu, Li Zheng (School ofComputer,SiChuan University,Chengdu 61oooo,China)

Abstract: With the increase in the numberof motor vehicles,parking has become acommon problem in cities.When many peopletakealong time to lineup fora parking space athe workplaces,there are many parking spaces are available n the residentialarea that aroundthe workplaces,which cause theuseofparking space ineffectively.However,the existing shared parking methodsaredificulttoimplement becauseofitsrandomness.Inorder toreduce itsrandomness,educe thedificulty of implementing shared parking,fianltoreduce the wasteofparking spaceresources,and becauseofthecomplementarityof travel times betweencommuter groups inresidentialareasandoficebuildings wherearound theresidentialareas,we presenta data-driven one-to-one pairing shared solution.To solvethis problem,weanalyze theentry and exit record dataof vehicles， thenobtainthecharacteristicsoftheidledurationoftheparkingspaceintheresidentialareaandthedurationofuseoftheoffice building,finall get theresultsof matching parking spaces and vehicles acording tothe matching methodofmaximizing the duration. In the experiment for selected area,the proportion of fully matched parking spaces was $3 7 . 6 6 \%$ ，and the average utilization rate of all matching parking spaces increased by $1 5 . 2 4 \%$ , and the maximum increase was $5 7 . 8 4 \%$ . The result shows that paired shared parking is extremely feasible.

Key Words: city traffic; shared parking; data analysis; paired sharing; residential area sharing

# 0 引言

随着机动车的保有量日益增加，城市停车位越发紧张，停车难成为不少城市的通病。以成都市为例，根据交管局数据统计，截止2017年底，成都市机动车保有量达到452万辆[1]。而停车位却远远不够。特别是在上班地点停车位异常紧张，而附近居住区却空有大量车位。在此状况下，由美国城市土地研究所率先提出的共享停车不失为一种在现有车位资源基础上解决问题的途径。共享停车理念由美国城市土地研究所在《共享停车》中提出，是指在一定区域范围内根据全天各个时段的高峰停车特性在不同性质土地的停车吸引点间共同利用车位[2]。也就是对同一个车位有不同的利用性质，例如小区私家车位与外来车辆共享不同时段的车位。在此基础上，众多学者对共享停车进行了相关研究，对通勤团体共享停车问题的进行研究，提出了不同条件下的分配方法，构建经济学模型对其求解，并通过数值实验证明了它们的有效性[3]，对泊位共享的停车需求预测模型研究，实验结果表面基于泊位共享时，高峰停车需求减少 $2 0 \% ^ { [ 4 ] }$ 。对泊位共享能力评估模型的研究，结果表明居住区可为毗邻建筑物提供约 $5 5 \%$ 的车位资源[5]；对居住区共享泊位资源优化配置的研究，使用蚁群算法对共享停车的车位分配进行优化，结果表明对比先到先服务的方法可以将共享泊位利用时长提高 $1 1 . 8 2 \% ^ { [ 6 ] }$ ；对运营商效益和影响用户停车行为的因素综合分析，提出以系统效率最大化为目标的0-1规划模型，该模型较先到先服务模型提高营业收入 $13 . 3 \%$ ，停车使用率提高$8 . 3 3 \% [ 7 ]$ 。以上对共享停车理论研究以及实施可行性与应用有较多描述，对共享停车中的经济学模型进行了讨论，得到关于共享停车中盈利模型，对于共享停车中居住区的共享能力进行了讨论并得出关于共享能力的计算模型，也对车位如何分配进行了讨论，提出一蚁群种算法。但都较少涉及具体共享情况中车位与车辆如何分配的问题，只有文献[6]提及，但其为随机共享的模型，在实际情况中，随机性带来的管理难题导致实施难度较大，所以共享停车并不普及。基于此，为减少其随机性，本文结合办公楼与居住区的通勤团体的出行时间具有的互补性，将一对多的随机共享变为一对一的固定共享，提出基于数据驱动的毗邻办公楼一居住区长期固定配对共享方法，使得于办公楼停车的某一上班族与在居民小区拥有某个车位的上班族达成匹配，前者固定长期地使用后者的居民小区泊位。由于外部车辆长期使用居住区内同一车位，大可同一车位登记两辆车（现有技术与方法），在提高车位时长利用率的同时，对降低工作人员的工作难度，缓解实施共享停车的实际情况中物业阻拦的难题以及减少超时停车矛盾的发生也有一定帮助，增大于居住区实施共享停车的可能。

# 1 实施配对共享停车的先行条件

由于配对共享停车的本质在于共享停车双方是一对一的关系而不是居住区泊位对外界车辆一对多的关系，所以根据可实施停车共享的基本条件[5结合配对共享停车性质对其实施条件进行总结研究如下：

a)选取的居民小区车场需支持一车位多车的登记方式，即同一车位可停多辆车，系统也可登记放行。只有在此条件下，匹配成功的外来车辆才可在登记车牌后自由出入车场，此为实施配对共享停车的必要条件（居住区可不必为开放小区）。如果无法支持一车位多车的登记，外来车辆无法以月租车的身份进出场，那么固定长期的共享是无法实现的。现有的车位智能锁与室内地图也为配对共享奠定基础。

b)车场需支持车牌识别的进出场方式，在车牌识别的基础上才可实现车辆的高效进出场与管理，共享停车才有较大可行性。

c)居民小区与商业办公楼之间的车辆出行特性应形成宏观上的互补，是形成配对共享的基础条件，也提高长时间共享的可能。即居住区的早高峰出行和办公楼早高峰进场、居住区的晚高峰回程和办公楼晚高峰出场的时间范围相近，形成早晚高峰的互补进出场，才有可能实现大规模的配对共享。

d)毗邻的居民小区与商业办公楼距离适当，步行或骑车（共享单车）时间适宜，在时间适宜的情况下，共享停车才有可能实施，时间长于可忍受时间时，共享停车的可行性较低。

# 2 匹配算法

# 2.1应用场景

在商业办公楼A附近步行距离可接受的范围内某居住区B可提供共享车位，且该共享车位具有稳定的朝出夕归特性，即符合上班族的特征。与此同时，商业办公楼A附近存在上班时间内停车的长期需求，即对居住区B的某个共享车位有使用需求。具体使用场景如图1所示。位于居住区B的A车位可供且只供商业楼A的车辆A使用，其中A车位的共享时段为连续时间段，车辆A于共享时段内可自由使用该车位。图中斜纹阴影部分表示车位拥有者使用时段；空白部分为空闲时段；网状阴影为外来车位使用者使用时段。

![](images/e6e3728ad86baa07e5fffdb1ef77aa2bdbe3277b15c10ac9c0a97ae1627fe267.jpg)  
图1配对共享泊位使用场景示意图

# 2.2 匹配算法

本文匹配算法根据进出口记录计算得到的特征进行居住区车位与办公楼车辆的匹配，具体流程如图2所示。首先需对获取的数据进行停车时长的计算，再根据计算得时长数据提取关于车位使用的特征，对其进行时长最大化的匹配处理得到最终匹配结果。以下对其算法进行详细说明。

![](images/726bad22bb732936455b56ade531a6b4a76bf1aef2a4e03ac4d9aab1f528a757.jpg)  
Fig.1Sketch map of paired parking space using   
图2匹配算法流程示意图  
Fig.2Flow diagram of matching algorithm

# 1）车位提供者空闲特征提取

根据车辆进出记录数据分析居住区车辆的出行特征即车位的空闲特征，在计算其空闲特征前需指定特定的时间区间，即设定对于共享停车的时间约束，因上班族具有明显的时间规律，所以在时间约束内具有明显空闲特征的才能实施共享。设开始时间点为 $T _ { s t a r t }$ ，结束时间点为 $T _ { e n d }$ ，其应满足基本条件即应符合商业楼与居住区的出行规律，令出行高峰区间为[T1,T2],回程高峰期为 $[ T 3 , T 4 ] .$ 则 $T _ { s t a r t } \in [ T _ { 1 } , T _ { 2 } ]$ ， $T _ { e n d } \in \left[ T _ { 3 } , T _ { 4 } \right]$ 。根据居住区的出行时间统计来选取具体时间节点，设 $T _ { \mathrm { j c } }$ 为居住区出行占比最大的时间节点， $T _ { \mathrm { j h } }$ 为回程占比最大的时间节点。此时 $T _ { s t a r t } { = } T _ { \mathrm { j c } }$ $\scriptstyle { T _ { e n d } = T _ { \mathrm { j h } } }$ 。

对于选取的[Tstart， $\mathrm { . T _ { e n d } } ]$ 利用其为居住区所有月租车位（临停车位不具有分享条件）的空闲特性进行分析，首先计算月租车的空闲时长。用 $\mathrm { t } _ { \mathrm { a r r } }$ 表示车辆到达车场时间，tea表示车辆离开时间，用I表示居住区月租车位集合，对于 $i \in I$ ，令 $\mathbf { \sigma } _ { \mathbf { X } _ { i } }$ 为月租车位i的空闲时段个数，获得居住区中所有绑定有月租车辆的车位进出记录的关于空闲时段的矩阵 $\mathbf { N }$ 。

$$
N = [ \begin{array} { l l l l } { t _ { { \mathrm { l e a } } } ^ { 1 1 } t _ { \mathrm { a r r } } ^ { 1 1 } } \\ { t _ { { \mathrm { l e a } } } ^ { 1 2 } t _ { \mathrm { a r r } } ^ { 1 2 } } \\ { \dots } \\ { t _ { { \mathrm { l e a } } } ^ { 1 \dots } } \\ { t _ { { \mathrm { l e a } } } ^ { 1 \boldsymbol { x } _ { l } } t _ { \mathrm { a r r } } ^ { 1 \boldsymbol { x } _ { l } } } \end{array} ] \quad \dots \quad \{ \begin{array} { l l } { t _ { { \mathrm { l e a } } } ^ { i _ { 1 } } t _ { \mathrm { a r r } } ^ { i _ { 1 } } } \\ { t _ { { \mathrm { l e a } } } ^ { i _ { 2 } } t _ { \mathrm { a r r } } ^ { i _ { 2 } } } \\ { \dots } \\ { t _ { { \mathrm { l e a } } } ^ { i _ { \dots } } t _ { \mathrm { a r r } } ^ { i _ { \dots } } } \\ { t _ { { \mathrm { l e a } } } ^ { i _ { x _ { i } } } t _ { \mathrm { a r r } } ^ { i _ { x _ { i } } } } \end{array} \} \quad \dots \quad \{ \begin{array} { l l } { t _ { { \mathrm { l e a } } } ^ { n 1 } t _ { \mathrm { a r r } } ^ { n 1 } } \\ { t _ { { \mathrm { l e a } } } ^ { n 2 } t _ { \mathrm { a r r } } ^ { n 2 } } \\ { \dots } \\ { t _ { { \mathrm { l e a } } } ^ { n \boldsymbol { x } _ { n } } t _ { \mathrm { a r r } } ^ { n \boldsymbol { x } _ { n } } } \\ { t _ { { \mathrm { l e a } } } ^ { n \boldsymbol { x } _ { n } } t _ { \mathrm { a r r } } ^ { n \boldsymbol { x } _ { n } } } \end{array} \} ]
$$

为计算指定时间区间内的空闲特征，若(tlea，tarr)∩(Tstart,$T _ { e n d } ) { = } ( T _ { s t a r t } , \ T _ { e n d } )$ ，即空闲时段包含指定时段区间时，定义此时的空闲时段为有效共享时段即在该时间区间内可分享；反之，记为不可分享。使 $\mathbf { H }$ 表示工作日集合（节假日不具备共享条件)，对于 $i \in I , j \in H$ ， $\Delta T _ { f } ^ { i j }$ 为月租车位 $i$ 在第 $j$ 个工作日的的时间区间 $( T _ { s t a r t } ^ { j } , ~ T _ { e n d } ^ { j } )$ 内空闲特征，其可表示为

$$
\Delta T _ { f } ^ { i j } = \left\{ \begin{array} { l l } { 1 , T _ { s t a r t } ^ { j } \leq t _ { l e a } ^ { i x _ { i } } < t _ { a r r } ^ { i x _ { i } } \leq T _ { e n d } ^ { j } } \\ { 0 , o t h e r s } \end{array} \right.
$$

其中： $\Delta T _ { f } ^ { i j } = 1$ 时表示其可分享； $\Delta T _ { f } ^ { i j } = 0$ 时表示不符合分享条件。根据以上结果得到关于车位的空闲特征矩阵 $F$ 。因上班族的停车时间具有周期性（以自然周为周期），为方便计算，将工作日 $j$ 按照周一至周五分类，将各类称为不同的周期，用0表示周期的集合，对于 $i \in I , n \in O$ ,将所有 $\Delta T _ { f } ^ { i j }$ 根据工作日的日期转换为用 $\Delta T _ { f } ^ { i n }$ 表示的车位i在周期 $n$ 的空闲特征，如果$\forall \Delta T _ { f } ^ { i n } \neq 0$ ,那么称车位 $i$ 在周期 $n$ 可分享，表示矩阵 $\nu$ 中符合条件的车辆可于周期 $n$ 在车位 $i$ 停车，用 $P _ { i n }$ 表示；相反，如果$\exists \Delta T _ { f } ^ { i n } = 0$ ，表示车位 $i$ 在周期 $n$ 存在空闲时长不符要求的情况，无法长期固定分享，用 $P _ { \mathrm { i n } } { = } 0$ 表示，其数学表达式如下：

$$
p _ { i n } = { \left\{ \begin{array} { l l } { 1 , \forall \Delta T _ { f } ^ { i n } \neq 0 } \\ { 0 , \exists \Delta T _ { f } ^ { i n } = 0 } \end{array} \right. }
$$

根据分类计算结果得到车位关于周期的空闲特征矩阵 $F ^ { \prime }$ ：

$$
F ^ { \prime } = \left[ \begin{array} { l l l } { p _ { 1 1 } } & { \ldots } & { p _ { 1 5 } } \\ { p _ { 2 1 } } & { \ldots } & { p _ { 2 5 } } \\ { \ldots } & { \ldots } & { \ldots } \\ { p _ { i 1 } } & { \ldots } & { p _ { i 5 } } \end{array} \right] , i \in I 
$$

# 2）潜在车位使用者使用特征提取

与1)中方法相似，稍有不同的为本文定义有效的停车时长需限定在指定时间区间(Tstart-α， $T _ { e n d } \mathbf { \Psi } + \mathbf { a } )$ 内，其中 $\mathfrak { a }$ 为时间节点浮动值，对于 $T _ { s t a r t }$ 允许向前浮动一定值，而 $T _ { e n d }$ 允许向后浮动一定值，因为对于进行长期共享停车的车位提供者与车位需求者之间，车位共享者的进场或离场时间存在一定的协商空间，可适当调整。笔者认为当且仅当 $( t _ { a r r } , t _ { l e a } ) ~ \cap$ (Tstart-α,$T _ { e n d } + { \bf a } ) = \left( t _ { a r r } , t _ { l e a } \right)$ 时，停车时长为有效时长。那么对于 $k \in L , j \in H$ $\mathbf { L }$ 为商业楼月租停车的车辆合集，月租车辆 $k$ 在第 $j$ 个工作日的 $( T _ { s t a r t } ^ { j } - \alpha , \ T _ { e n d } ^ { j } + \alpha )$ 区间之内的有效停车时长为

$$
\Delta T _ { \mathrm { v } } ^ { k j } = \sum _ { x _ { i } } u _ { x _ { i } } ^ { k j }
$$

其中： $u _ { x _ { i } } ^ { k j }$ 为 $( T _ { s t a r t } ^ { j } , ~ T _ { e n d } ^ { j } )$ 区间内的第 $x _ { i }$ 个停车时长。

$$
u _ { x _ { i } } ^ { k j } = \left\{ \begin{array} { l l } { t _ { l e a } ^ { k x _ { i } } - t _ { a r r } ^ { k x _ { i } } , T _ { s t a r t } ^ { j } \leq t _ { a r r } ^ { k x _ { i } } < t _ { l e a } ^ { k x _ { i } } \leq T _ { e n d } ^ { j } } \\ { 0 , o t h e r s } \end{array} \right.
$$

根据计算的停车时长整理为关于月租车辆的停车时长矩阵$\boldsymbol { V }$ 。与1）中方法类似，将其以自然周为周期分类，对于$\mathbf { k } \in L , n \in O$ ，将所有 $\Delta T _ { \mathrm { v } } ^ { \mathrm { k } j }$ 根据工作日的日期转换为用 $\Delta T _ { \nu } ^ { k n }$ 表示的车位 $i$ 在周期 $n$ 的有效停车时长，将属同一周期的停车时长均值作为车辆的平均时长，用 $m _ { \mathrm { { k n } } }$ 表示车辆在周期 $n$ 的平均时长，将其整理为矩阵V"。

$$
V ^ { \prime } = { \left[ \begin{array} { l l l } { m _ { 1 1 } } & { \ldots } & { m _ { 1 5 } } \\ { m _ { 2 1 } } & { \ldots } & { m _ { 2 5 } } \\ { \ldots } & { \ldots } & { \ldots } \\ { m _ { k 1 } } & { \ldots } & { m _ { k 5 } } \end{array} \right] } , k \in L
$$

3）车位提供者-潜在车位使用者配对

对于共享停车中的车位分配问题，最常用的方法为先到先服务的方法，即根据车位使用者的到达时间分配空闲可用的车位，对于先到先服务的方法，车位很大可能得不到最大的利用，因其没有对时长进行约束，即当停靠很短时间内的车辆比停靠长时间的车辆先到达时，那么停靠短时间的车辆分配到的车位很大可能为空闲时长长的车位，导致后面的时长被浪费掉，且其针对的是随机短时的共享，对于本文的长期固定共享并不适用，所以提出时长最大化的匹配方法。

将以上矩阵 $F$ 与 $V ^ { \prime }$ 进行车位与车辆的匹配,令匹配度 $s$ 为每个车位空闲特征向量与车辆停车时长向量的乘积，乘积越大表示其越匹配，双方可共享时长越长，那么对于（20 $\mathrm { i } \in I , \mathrm { k } \in L , n \in O , S \mathrm { i } \mathrm { _ { l } }$ 为车位 $i$ 与车辆 $k$ 的可共享时长，其表达式如下：

$$
S _ { \mathrm { i k } } = \sum _ { n = 1 } ^ { 5 } ( p _ { i n } * m _ { k n } )
$$

而要获得车位i与车辆 $\mathbf { k }$ 最优化的匹配结果，则需使得 $\mathrm { S } _ { i k }$ 最大，假设

$$
\operatorname* { m a x } ( S _ { \mathrm { i k } } ) = \sum _ { n = 1 } ^ { 5 } ( p _ { i n } * m _ { k n } )
$$

那么本文提出的时长最大化的匹配方法求的就是其中的与

$i$ 对应的 $k$ □

为提高算法的效率，将时长最大化匹配方法分为全特征匹配与不完全特征匹配两个部分。其中全特征表示车位的空闲特征在所有周期中全为1；反之为不完全特征。其示意图如图3所示。图中左边方块集代表车位的共享状态，空白格代表当前车位在当前周期可共享，斜纹方格代表不可共享；右边方块集代表车辆停车情况，有四角星图形代表当前车辆在当前周期会停车，空白代表不会停车。

![](images/f72996f5086a10e8359e11b56acf0c2a10aa9b9609d80d338ac2318a041cb582.jpg)  
图3匹配算法示意图  
Fig.3Sketch map of matching algorithm cases

a）全特征匹配。

假设 $F$ 中筛选出的全特征车位为a个，那么将这a个车位与 $V ^ { \prime }$ 中按照停车时长之和倒序排序的前a个车辆匹配，其中全特征车位按照平均离场和进场时间间隔时长排序。如果间隔越长排越前，以提高共享成功的可能性，那么对于这a个车位而言，此时得到的匹配度S为最大值，如图3（a）中分割线以上的部分，车位1-4为按照排序的全特征车位，它们与对应排序的车辆1-4匹配成功。

b）不完全特征匹配。

(a)将全特征匹配成功的车位与车辆元素分别从矩阵 $F ^ { \prime }$ 与$V ^ { \prime }$ 中剔除，令e表示车位的可分享度即空闲特征1的个数，将不完全特征车位按e的大小排序，若e相同，用与全特征匹配中相同的排序方法排序，而剩余的车辆元素按照停车时长排序，用如图3（a）中分割线以下的部分表示。

(b)对于 $\mathbf { i } \in \mathbf { I , k } \in L , n \in O$ ,将车位i的空闲特征为1的周期n整理为集合W,对于矩阵 $V ^ { \prime }$ ，筛选其中与集合W 的周期对应的$\mathrm { \ m k n { > } 0 }$ 的行，即在集合W中的周期有停车的可与车位i发生共享行为的车辆。

(c)在筛选的车辆中，根据公式计算S值，其中使得Sik值最大的车辆k,为车辆i的最佳匹配，如图3（b）所示，车位4的集合 $\scriptstyle \mathbf { W = } ( 1 , 2 , 3 , 4 )$ ，而在右边方块集中实心四角星的方块表示与车位4周期对应的停车时长不为零的元素，那么车辆矩阵中筛选出符合的车辆为4、5、6，其中虚线框包含的车辆7完全不符合条件，在计算中剔除。根据式(8)得到与车位4最佳匹配的车辆4。

(d)将匹配成功的车位与车辆从相应矩阵中剔除，重复步骤(b)和(c)，直至任意矩阵中的元素都匹配完成。

至此，所有的车位或车辆都已匹配完成，得到关于每个车位的匹配对象车辆。

# 3 实例分析

为验证配对停车共享方法的可行性，根据获取的数据进行实例分析，使用的工具为R3.3.2。

# 3.1，1数据获取与处理

本文数据来源为车场进出口道闸记录数据，本文获取了位于成都市的七个停车场的进出场记录数据，选取的车场均采用车牌识别的方式检测车牌，真实有效。进出记录数据段如表1所示。其中类型为停车类型，分为月租与临停（月租为可长期停车而临

停为短期停车）。

表1车辆进出记录  
Table1Records of enter and exit parking lot by vehicles   

<html><body><table><tr><td>车牌号</td><td>进场时间</td><td>出场时间</td><td>类型</td><td>车位</td></tr><tr><td>川A12345</td><td>2017-01-0118:00</td><td>2017-01-01 8:00</td><td>月租</td><td>B208</td></tr><tr><td>川A12345</td><td>2017-04-0118:00</td><td>2017-04-02 8:00</td><td>临停</td><td>B200</td></tr></table></body></html>

在原始数据中，需对冗余数据、错误数据以及滞留库数据进行清理。在此数据中即包括重复识别记录、车牌未能识别的记录以及长期滞留车库的车辆记录，对此类数据予以剔除。除此之外，对于同一车位登记多个车牌的，需将其进出记录进行合并处理。

# 3.2 筛选可行车场

在七个停车场中的处于同一片区中的四个车场中，其中办公楼停车场为相邻的商鼎国际地下停车场以及华尔兹停车场，将其合并称为商业停车场，居民小区停车场为同一小区的锦官新城东区停车场以及锦官新城西区停车场，将其合并称为居住区停车场。以上停车场均支持一车位多车的登记方式且都为车牌识别的进出场方式。而且在对以上停车场的实地考察中，发现办公楼停车场与居住区停车场间的骑行时间最长不超过10min。对各车场的车辆进出特性进行研究，选取各车场在2017-1-01至2017-4-30的4个月内共15万条月租车的进出记录数据，分析其车辆的进出时间特性。因临停车辆未绑定车位亦不具有停车持久性规律，不具备配对共享条件，所以不纳入分析范围。由于节假日对于上班族来说无分享意义，所以只针对工作日进行数据分析。将0:00至24:00分为24个时间段，以1h为间隔，统计出每个时间段内进出车辆数，绘制各车场车辆出行特性如图4和5所示。图中实线与虚线分别表示车辆驶离车场与驶入车场。居住区有明显朝出夕归特性，在工作时间具有空闲特质。而办公楼车场具有朝进夕出的特性，与居民小区互补的车辆出行特性为进行配对共享停车提供绝佳条件。以上均符合实施配对共享的先行条件，所以将以上车场作为实验车场获取数据。

办公楼504540 ： 18 U 进场35  
辆30  
2  
车15150 ： C80 4 &1-00:71时间段居住区5045 进场40 出场35  
满30  
数25105 产0 .时间段

# 3.3数据分析

选取2017.01一2017.03共3个月的数据作为实验数据，数据中各停车场的月租车数量如表2所示，办公楼有月租车566辆，而居住区有919辆。

表2停车场月租车数量  
Table 2Number of monthly rental vehicles   

<html><body><table><tr><td></td><td>办公楼</td><td>居住区</td></tr><tr><td>月租车数量(辆)</td><td>566</td><td>919</td></tr><tr><td>可匹配数量（辆)</td><td>248</td><td>253</td></tr></table></body></html>

而根据图4和5所示，办公楼停车场的进场时间与居住区出场时间均集中在7:00\~10:00的时间区间内，而17:00\~19:00这一时间区间为办公楼停车场的离场时间与居住区进场时间的高峰。在区间内以半小时为单位计算其出行与回程数量占比如表3所示。可以看出居住区的出行时间为8：00\~8:30时，出行车辆数量占比最多为 $2 6 . 4 8 \%$ ，且7:00\~8:30出行数量占比 $50 \%$ 以上，所以设置Tstart=8:30，同理设置Tend $_ { - 1 7 : 3 0 }$ 。

Table 3Time distribution statistic of get in and out   

<html><body><table><tr><td>出行时间</td><td>数量占比/%</td><td>回程时间</td><td>数量占比/%</td></tr><tr><td>7:00-7:30</td><td>11.76</td><td>17:00-17:30</td><td>20.00</td></tr><tr><td>7:30-8:00</td><td>17.65</td><td>17:30-18:00</td><td>36.67</td></tr><tr><td>8:00-8:30</td><td>26.48</td><td>18:00-18:30</td><td>23.33</td></tr><tr><td>8:30-9:00</td><td>15.68</td><td>18:30-19:00</td><td>20.00</td></tr><tr><td>9:00-9:30</td><td>14.70</td><td></td><td></td></tr><tr><td>9:30-10:00</td><td>13.73</td><td></td><td></td></tr></table></body></html>

根据[8:30,17:30]时间区间计算可分享与潜在停车的数量即可匹配数量如表2所示，可分享的车位数量为车位总数的$2 7 . 5 3 \%$ 。

本文设定浮动时间 $\mathrm { ~ a ~ } { = } 0 . 2 5 \mathrm { h }$ 。那么对于全部的月租车辆得到相关矩阵与，将其按照时长最大化方法进行匹配得到关于居住区与办公楼之间配对成功的为231对，其中17个车位未成功匹配，通过分析其进出记录发现其可与剩余未匹配车辆进行匹配，只是在设置的时间区间内无法匹配，所以在修改时间区间后，再次进行以上匹配算法的流程，最后得到匹配结果如表4所示。匹配成功的共有248对。有如表4(车牌号脱敏表示)，即对于[川 $\mathbf { A } ^ { * * * * * } 2 ]$ 所绑定的居住区的车位，匹配到办公楼的车牌为[藏 $\mathrm { H } ^ { * * * * * } \mathrm { J }$ 的车辆。

表3进出时间统计表  
表4配对结果  
Table 4Result of matching algorithm   

<html><body><table><tr><td>办公楼</td><td>居住区</td></tr><tr><td>藏H****5</td><td>川 A****2</td></tr><tr><td>川A****E</td><td>川A****9</td></tr><tr><td>…</td><td></td></tr><tr><td>赣A****7</td><td>川 A****M</td></tr><tr><td>粤B****9</td><td>川 A****C</td></tr><tr><td>总计（对）</td><td>248</td></tr></table></body></html>

为验证其效果，选取2017年4月的数据作为测试数据，以居住区与办公楼的某两辆配对月租车为例，将停车时段根据时间节点合并，其车位使用如图6(a)所示。图中灰色表示车位非空闲，白色表示车位空闲。[川 $\mathbf { A } ^ { * * * * * } 6 ]$ 为居住区车辆，[川$\mathbf { A } ^ { * * * * * } { } ^ { * } 8 ]$ 为办公楼车辆，合并为合并后车位的利用情况。若两者时间存在冲突则办公楼车辆的停车时段不计入合并停车时段，图中所示冲突不可合并方框内的时间段存在冲突，无法计入合并。其中能较好合并的如图6(b)所示。图中灰色部分为居住区车辆停车，斜纹阴影为办公楼车辆停车。

根据停车时段计算其匹配合并后的时长利用率（总时长利用率 $\ c =$ 总停车时长/总时长）以及损失率（损失率 $\ l =$ 办公楼车辆停车时长利用率 $. +$ 居住区车位停车时长利用率-匹配车位时长利用率），损失率作为评判其是否完全匹配的指标，值越小表示其匹配程度越高，当值为0时，两者完全不损失任何时间，达到最好的共享停车效果。[川 $\mathrm { A } ^ { * * * * * } 6 ]$ 与[川 $\mathbf { A } ^ { * * * * * } { } 8 ]$ 合并后的计算结果如表6所示。未匹配时时长利用率为 $4 0 . 9 2 \%$ ，匹配后其时长利用率提高 $12 . 4 9 \%$ ，损失率为 $5 . 0 9 \%$ ，表示两者能较好地配对停车。

![](images/ee153995740b2ca20655571e9966e6b16292b7586e7cf07a2c41e1143cb51426.jpg)  
图6配对车辆停车时段合并示意图  
Fig.6Sketch map of paired vehicles merging parking period

对所有的配对车辆的进出记录按照以上方法进行合并，分别计算统计每个自然周（第四周包含月末两天）的匹配效果如表7所示。平均时长利用率提升 $1 5 . 2 4 \%$ ，在所有配对中最大提升率为 $5 7 . 8 4 \%$ ，损失率均值为 $10 . 0 1 \%$ ，其中达成完全匹配有87对，以及能较好匹配的为102对。

对于其中完全匹配的居住区车位与办公楼车辆，双方可完全无缝连接的停车，即不存在时间冲突的问题，此类配对完全达到配对共享的效果。

表6时长利用率统计  
Table 6Statistic of parking time utilization ratio   
表7整体匹配效果统计  

<html><body><table><tr><td>未匹配时长利用率/%</td><td>匹配时长利用率/%</td><td>损失时长利用率/%</td></tr><tr><td>40.92</td><td>53.41</td><td>5.09</td></tr></table></body></html>

# 4 结束语

本文基于毗邻的居住区、办公楼两者的上班族之间的出行时间具有互补性的特点，即当居住区上班族于上班时间空出车位而办公楼上班族却需要停车，提出一种基于时长最大化的一对一的共享停车模式与解决方案，为解决城市停车难题提供一种新思路。利用车辆的出行记录数据分析其出行特性，得到关于居住区车位的空闲特性与办公楼车位的使用特性；使用时长最大化的匹配方法对其进行匹配，得到关于居住区车位与办公楼车辆的配对结果。用测试数据对其进行验证，其中完全匹配的居住区车位占配对总数的 $3 7 . 6 6 \%$ ，车位时长利用率平均提高$1 5 . 2 4 \%$ ，最大提升 $5 7 . 8 4 \%$ ，结果表明配对共享具有较大可行性，为实施共享停车提供了一种新思路。

Table 7Statistic of matching results   

<html><body><table><tr><td rowspan="2">日期</td><td rowspan="2">时长利用 率提升均 值/%</td><td rowspan="2">损失时长 利用率均 值/%</td><td rowspan="2">最大时长利 用率提升/% =0)</td><td rowspan="2">完全匹配数/较好匹配个数 个（损失率/个（损失率</td></tr><tr><td><=5%)</td></tr><tr><td>4.1-4.7</td><td>14.58</td><td>10.67</td><td></td><td></td></tr><tr><td>4.8-4.14</td><td>15.26</td><td>10.23</td><td></td><td></td></tr><tr><td>4.15- 4.21</td><td>15.80</td><td>9.19</td><td></td><td></td></tr><tr><td>4.22-</td><td></td><td></td><td></td><td></td></tr><tr><td>4.30</td><td>15.35</td><td>9.94</td><td></td><td></td></tr><tr><td>平均</td><td>15.24</td><td>10.01</td><td>57.84</td><td>87 102</td></tr></table></body></html>

致谢在此致谢为本文实验提供必要帮助与支持的成都市千帆科技有限责任公司与成都市微泊科技有限公司，感谢两家公司提供车辆进出口数据。

# 参考文献：

[1]公安部交通管理局.2017年全国机动车和驾驶人保持高位增长 [EB/OL].(2018-01-15）[2018-05-20].http://www. mps. gov. cn/n2255040/n4908728/c5977158/content. htm.   
[2]Smith M S.Shared Parking [M].2nd.Washington DC: Urban Land Institute, 2005:1-5.   
[3]Xu Suxiu,Cheng Meng,Yang Hai,et al.Private parking slot sharing [J]. Transportation Research PartB:Methodological.2016,93 (partA):596-617.   
[4]肖飞，张利学，晏克非．基于泊位共享的停车需求预测[J].城市交通, 2009,7 (3):73-79.(Xiao Fei, Zhang Lixue,Yan Kefei. Parking demand forecasting based on parking space sharing [J]. Urban Transport of China, 2009,7 (3): 73-79.)   
[5]段满珍，杨兆升，张林，等．居住区泊位对外共享能力评估模型[J]. 交通运输系统工程与信息,2015,15(4):106-112,117,(Duan Manzhen, Yang Zhaosheng,Zhang Lin,et al. Residential parking spaces shared capability assessment model [J].Journal of Transportation Systems Engineering and Information Technology,2015,15 (4): 106-112,117. )   
[6]姚恩建，张正超，张嘉霖，等．居住区共享泊位资源优化配置模型及算 法[J].交通运输系统工程与信息,2017,17(2):160-167.(Yao Enjian, Zhang Zhengchao,Zhang Jialin，et al.A model and algorithm for optimization of the utilization of residential shared parking slots [J].Journal of Transportation Systems Engineering and Information Technology,2017, 17 (2): 160-167.)   
[7]Yang Bo,Yuan Zhenzhou, Yang Yang,et al. The study on allocation model of shared parking slots in multi-parking lots [C]// Proc of the 5th International Conference on Mechatronics,Materials,Chemistryand Computer Engineering France: Atlantis Press,2017: 457-465.