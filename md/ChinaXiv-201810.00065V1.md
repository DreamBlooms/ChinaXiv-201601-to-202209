# 基于多维关联规则的区域能源安全外生警源隐含特征分析

胡健，蒲东，孙金花(重庆理工大学 管理学院，重庆 400054)

摘要：针对现阶段我国区域能源安全突发事件频现的问题，对区域能源安全外生警源隐含特性展开了研究。通过对区域能源安全事件案例抽取，构建了能源安全外生警源属性集和数据集。依据数据集的特点，设计了能源安全外生警源多维关联规则挖掘模型。该模型首先基于多维属性融合的思路，通过把属性划分为事务项，将外生警源多维属性映射为一维，然后利用Apriori算法的基本原理进行规则挖掘。在此基础上，将该模型应用于能源安全外生警源隐含特征分析中，研究警源属性间的关联关系，实现强关联规则输出。研究结果表明，多维关联规则方法可以发现隐藏在外生警源数据中的规律，通过对挖掘出规则集的归纳分析，得出区域能源安全外生警源爆发时具有衍生性、季节性、危害性和持续性等共性特征。

关键词：区域能源安全；外生警源；多维关联规则；Apriori算法；隐含特性 中图分类号：X915.1 doi:10.3969/j.issn.1001-3695.2018.05.0379

# Analysis on implicit characteristics of regional energy security exogenous source based on multi-dimensional association rule

Hu Jian, Pu Dong, Sun Jinhua (School of Management, Chongqing University of Technology, Chongqing 40oo54, China)

Abstract: According to the problemoffrequent occurrence ofregional energyevents inour country,this paper makes adeep studyonthe implicit characteristicsofregional energy security exogenous source.This research constructs the atribute setand datasetofregionalenergysecurityexogenoussourcethrough extracting differentcases,andinthelightofthedatasetfeatures, designs amulti-dimensional associationrule mining modelonregionalenergysecurity exogenous source.Basedonthe ideaof multi-dimensionalatribute fusion,the model firstlymaps the multi-dimensionalatributes toonedimensionbydividing the atributes into items,and then mines therules withthe basic principleofApriori algorithm.On thebasis,this paperuses this modeltoanalyze the implicit characteristicsof theregional energysecurity exogenous source,which makes aresearchonthe relationship between these atributes inorder tooutput the strong associationrules.Theresearch results show that multidimensional associationrule modelcan findtheimplicit characteristics oftheregional energy security exogenous source,which are derivative, seasonality, harmfulness and durability.

Key words:regional energy security；exogenous source；multi-dimensional asociationrule； Apriori algorithm;implicit characteristic

# 0 引言

近年来不断频发的区域能源安全突发事件，已对我国各地区的经济发展和社会稳定造成了严重影响。例如，2008年初，由于暴雪引发的自然灾害严重影响了电网运行，全国19 个省出现了大范围拉闸停电；2011年以来，重庆地区因贵州和四川等煤炭能源产地突然对煤炭外销和运输实行严格控制，致使电煤出现供应紧张。2013年11月，我国华北和西南地区10余省突然出现了大规模“气荒”。诱发这些事件的源头更多是由于能源系统外部因素的突然变化所致。然而，目前我国能源安全体系尚无法对引发区域能源安全事件的外生警源进行有分析，从而造成了区域能源供需缺口现象频现。因此，深入挖掘区域能源安全外生警源的隐含特性，对于区域能源安全有效预警研究具有重要的意义。

目前在区域能源安全研究成果中，多集中于从宏观整体层面来研究能源安全问题。Vlado[1]建立了基于一种新的和扩大概念化的能源安全评估工具，充分考虑了每个国家或地区的能源安全和政策的定量和定性属性，从11类维度对能源安全进行测评。Andreas等人[2]则对能源安全指标体系的构成进行了深入探讨，认为衡量能源安全指标包括预测性指标和结果指标两大类。刘立涛等人[3]系统地构建了我国区域能源安全评价指标体系，并选取广东与陕西作为能源输入与输出区代表，对两省能源安全展开实证分析。赵春富等人[4建议从供应链的角度出发，考虑能源系统内部各因素及与外部因素的相互作用，构建链式的预警体系。范秋芳[则通过对特定能源安全预警问题分析，基于BP神经网络的基本原理，构建了石油安全监测预警方法与模型，并开展了实证应用分析[5]。郭金栋等从煤炭安全压力、状态和响应3个子系统出发构建了煤炭安全测度指标体系，评价了煤炭安全的程度。苏飞等人[7在构建区域能源安全脆弱性评估模型及其评价指标体系的基础上，对我国30个地区的常规能源安全供给脆弱性进行了定量评估。吴初国等人[8对能源安全的标准进行了界定，采用综合评分法和熵权系数法两种方法计算了评价指标的权重，对不同的情景下我国能源安全进行了评价。胡剑波等人[9从压力、状态、响应等三个方面构建9 个指标来评价中国的能源安全状况。张强[10]利用综合集成复杂系统问题研究方法，构建了能源安全预警系统，并详细给出了系统的设计和实现方法。而周德群等人[1学者则采用 Hilbert-huang 变换的方法构造石油价格波动预警分量，以此来对历次石油价格波动过程展开预警分级研究。郭玲玲等人[12]运用系统动力学理论构建中国能源安全的系统动力学模型，模拟得到三种我国能源安全系统的发展模式。郝平等人[13]利用数据仓库和关联规则挖掘方法建立了区域能源消耗预警系统，对区域能源消耗进行监察管理和预警。然而与区域能源安全外生警源相关的研究成果较少，仅有学者迟春洁[14提出了能源安全外生警源的概念，而魏一鸣等人[15,16]在阐述区域能源安全事件的基础上，分析了诱发区域能源安全事件的外部关键因素。

通过对上述文献资料梳理可知，现有的区域能源安全体系尚未对诱发能源安全事件的根源要素进行研究。因此，本文从外部性角度，将影响区域能源安全事件的主要外部因素界定为外生警源，并对其内涵进行界定。通过外生警源案例来抽取外生警源的属性，并构建外生警源数据集。结合外生警源数据集的特点，利用多维关联规则方法对外生警源隐含特征进行深入挖掘，以期为区域能源安全预警提供决策参考。

# 1 能源安全外生警源内涵及特征属性

# 1.1区域能源安全外生警源内涵

区域能源安全预警是指对于某一地区能源系统未来的演化趋势进行预期性评价，以事先发现其未来运行中可能出现的问题并分析其成因，进而为警情分析决策、制定相应防范措施和缓解能源供需矛盾提供决策依据。确切地说，预警是度量某种状态偏离预警线的强弱程度、发出预警信号的过程，其实质是对区域能源安全运行的稳定性程度的评判，其目的与作用在于

识警防患，超前预控。

区域能源安全外生警源是指由于区域能源系统的外部影响因素发生变化，如能源价格的波动、能源政策的调整、突发自然灾害等，导致区域能源系统随之产生扰动，并由此引发威胁区域能安全的连锁反映事件。本文将这些影响区域能源系统安全的外部性要素界定为外生警源。外生警源是分析突发区域能源安全警情的重要外部根源，是区域能源安全警情的策源地。因此，研究区域能源安全外生警源是区域能源安全预警的新的逻辑起点，其关键就在于如何有效识别出区域能源安全外生警源及其形成机理。

# 1.2区域能源安全外生警源的类型

引发区域能源安全的外部影响因素很多，包括宏观经济、能源政策、环境因素、突发因素等。本文收集了区域能源安全典型事件，发现引发区域能源安全事件的根源大多是能源系统的外部因素，在总结区域能源安全事件成因及演化过程的基础上，并依据以上外部影响因素，从外生警源的形成机理角度将外生警源划分为以下几类：

a）能源价格波动。由于我国的能源价格由政府管制，能源价格的定价机制不是由市场供需决定，所以能源价格的扰动会打破局部地区的能源供需平衡，从而形成干扰区域能源安全的外生警源，最终诱发区域能源安全事件。

以成品油为例，国内能源定价机制决定了成品油价格在政府规制的范围内，批发企业可通过相对灵活的措施适时调整价格。在这种情况下，当成品油批发企业突然上涨价格时，由于零售企业受制于政府严格的定价机制，导致其价格调整相对迟滞于市场供需变化，出现进价高于销售价格情况，严重影响其利润获取。这一能源价格扰动要素就成为区域能源安全的外生警源，在其集聚达到一定程度时，势必会引发局部地区出现油品能源停供、限供等区域能源安全事件。

b)区域能源政策干预不当。部分地区为了自身区域经济发展或受到国家层面政策的约束，在特定时期，会强制性地对能源政策进行某种干预，从而引发局部地区的能源供需和调配失衡，诱发区域能源安全事件。例如2010年11月，浙江、江苏、湖南等地爆发电力安全事件，其原因是这些地区政府为完成减排指标，突击进行拉闸限电；2011年，重庆地区因贵州煤炭能源产地突然对煤炭外销和运输实行严格控制，致使电煤出现供应紧张。

c）外部环境变化。外部环境变化这一区域能源安全的外生警源更多可能会诱发局部地区的能源需求量、能源供应量发生突变，导致区域能源安全事件。通过对近年来我国各地区突发的区域能源安全事件的诱因分析，将影响区域能源安全的外部环境划分为季节变化、运力紧张、自然灾害、

能源生产和运输等突发事件。例如2008年和2009年，我国多个地区连续两年冬季出现突如其来的降雪，阻碍了能源运输，出现了“煤荒”“电荒”。

# 1.3外生警源特征属性

通过对“煤荒”“油荒”“电荒”和“气荒”等区域能源安全事件的收集，对比分析了各类能源安全外生警源的形成机理，并依据相关文献的研究，抽取了各类能源安全外生警源共性特征，并将外生警源特征属性分为描述性属性和状态属性，见图1。

# 1.4外生警源特征属性划分

由于区域能源安全外生警源属性具有多维度特点，用经典的单维规则方法无法进行隐含特性的挖掘。因此，首先通过咨询能源安全领域的专家、参考等级划分的相关文献资料，并对区域能源安全外生警源形成机理、影响程度的深入分析，对状态属性进行量化划分，将多维外生警源特征属性转换为事务项。

具体见表1所示。

区域能源安全外生警源特征属性描述性属性 状态属性发生时间 发生地点 事件类型 诱发原因 波及范围 持续时间 能源缺口程度 经济损失程度 社会反响

表1外生警源属性划分  

<html><body><table><tr><td colspan="2">属性</td><td colspan="6">区间划分及符号命名</td></tr><tr><td rowspan="2">发生时间</td><td>Ta</td><td>Tb</td><td>T</td><td>Td</td><td></td><td></td><td></td></tr><tr><td>春季</td><td>夏季</td><td>秋季</td><td>冬季</td><td>1</td><td>1</td><td>一</td></tr><tr><td rowspan="2">发生地点</td><td>Pa</td><td>Pb</td><td>Pc</td><td>Pd</td><td>Pe</td><td>Pf</td><td>Pg</td></tr><tr><td>华北地区</td><td>华东地区</td><td>华中地区</td><td>华南地区</td><td>东北地区</td><td>西南地区</td><td>西北地区</td></tr><tr><td rowspan="2">事件类型</td><td>I</td><td>Ib</td><td>I</td><td>Id</td><td></td><td></td><td></td></tr><tr><td>石油安全事件</td><td>煤炭安全事件</td><td>天然气安全事件</td><td>电力安全事件</td><td></td><td>1</td><td>1</td></tr><tr><td rowspan="2">诱发原因</td><td>Ca</td><td>Cb</td><td>Cc</td><td>Cd</td><td>Ce</td><td>Cf</td><td>Cg</td></tr><tr><td>能源价格变化</td><td>能源供应量突变</td><td>能源政策调整</td><td>能源产量变化</td><td>自然灾害</td><td>突发事件</td><td>季节交替变化</td></tr><tr><td rowspan="2">波及范围(省)</td><td>Ra</td><td>Rb</td><td>Rc</td><td>Rd</td><td>Re</td><td>Rf</td><td></td></tr><tr><td>(0,5]</td><td>(5,10]</td><td>(10,15]</td><td>(15,20]</td><td>(20,25]</td><td>(25,31]</td><td>1</td></tr><tr><td rowspan="2">持续时间(月)</td><td>Da</td><td>Db</td><td>Dc</td><td>Dd</td><td>De</td><td>Df</td><td></td></tr><tr><td>(0,1]</td><td>(1,3]</td><td>(3,5]</td><td>(5,7]</td><td>(7,9]</td><td>(9,12]</td><td>1</td></tr><tr><td rowspan="2">能源缺口程度</td><td>Ga</td><td>Gb</td><td>Gc</td><td>Gd</td><td>Ge</td><td>Gf</td><td>Gg</td></tr><tr><td>非常小</td><td>很小</td><td>小</td><td>中等</td><td>大</td><td>很大</td><td>非常大</td></tr><tr><td rowspan="2">经济损失程度</td><td>La</td><td>Lb</td><td>Lc</td><td>Ld</td><td>Le</td><td>L</td><td>Lg</td></tr><tr><td>非常小</td><td>很小</td><td>小</td><td>中等</td><td>大</td><td>很大</td><td>非常大</td></tr><tr><td rowspan="2">社会反响</td><td>Fa</td><td>Fb</td><td>Fe</td><td>Fd</td><td>Fe</td><td>Ff</td><td>Fg</td></tr><tr><td>非常小</td><td>很小</td><td>小</td><td>中等</td><td>大</td><td>很大</td><td>非常大</td></tr></table></body></html>

# 2 多维关联规则挖掘模型构建

通过外生警源特征属性划分，将外生警源案例转换为了事务项的集合 $I { = } \{ i _ { 1 } , i _ { 2 } , \cdots , i _ { \mathrm { m } } \}$ 。本文采用Apriori算法的基本原理来挖掘隐含在外生警源数据中的规则。该方法主要包括两个主要过程，一是从事务项的集合中找出所有的频繁项集；二是由频繁项集产生强关联规则。

# 2.1Apriori算法的基本原理

Apriori 算法是一种最有影响的挖掘布尔关联规则频繁项集的算法。算法的名字基于这样的事实：算法使用频繁项集性质的先验知识，正如人们将看到的。Apriori使用一种称做逐层搜索的迭代方法， $k \mathrm { . }$ 项集用于探索 $( k { + } 1 )$ -项集。首先，找到频繁1-项集的集合。该集合记做 $L _ { 1 \circ } L _ { 1 }$ 用于找频繁2-项集的集合 $L _ { 2 }$ 而 $L _ { 2 }$ 用于找 $\mathbf { { \mathcal { L } } } _ { 3 }$ ，如此下去，直到不能找到频繁 $k \mathrm { . }$ 项集。找每个$L _ { k }$ 需要一次数据库扫描。

1)生成频繁项集首先找到频繁1-项集的集合，该集合记作 $L _ { 1 \circ } ~ L _ { 1 }$ 用于找频繁2-项集的集合 $L _ { 2 }$ ，而 $L _ { 2 }$ 用于找 $L _ { 3 }$ ，依此下去，直到不能找到频繁 $\mathbf { k }$ -项集。找每个 $L _ { \mathrm { k } }$ 需要扫描一次数据库。步骤如下：

a)找到频繁1-项集。扫描事务数据库，Sup_count(A)表示事务项集 $A$ 出现的次数，Count（T）表示事务的个数。式（1）定义频繁项集的支持度，把满足最小支持度的单个事务项称作频繁1-项集。

$$
\mathrm { m i n } _ { - } s u p \big ( { \cal A } \big ) = \frac { S u p _ { - } c o u n t \big ( { \cal A } \big ) } { C o u n t ( T ) }
$$

b)连接步。通过 $L _ { k - 1 }$ 与自己连接产生候选 $\mathbf { k }$ -项集的集合。

该候选项集的集合记做 $C _ { k \circ }$ 设 $l _ { 1 }$ 和 $l _ { 2 }$ 是 $L _ { k - 1 }$ 中的项集。记号[]表示 $l _ { i }$ 的第 $j$ 项。为方便计算，假定事物项按出现的先后次序排序。执行连接 $L _ { k - 1 } { \scriptstyle \bowtie } L _ { k - 1 }$ ，其中 $L _ { k - 1 }$ 的元素是可连接的，如果它们前(k-2)个项相同。即，当满足式（2）中的条件时， $L _ { k - 1 }$ 的元素 $l _ { 1 }$ 和 $l _ { 2 }$ 是可连接的，连接 $l _ { 1 }$ 和 $l _ { 2 }$ 产生的结果项集是 $l _ { 1 } [ 1 ] l _ { 1 } [ 2 ] \cdots$ $l _ { 1 } [ k \mathrm { - } 1 ] l _ { 2 } [ k \mathrm { - } 1 ]$ 。

$$
\begin{array} { r l } & { s . t . \ ( l _ { 1 } \Big [ 1 \Big ] = l _ { 2 } \Big [ 1 \Big ] ) \wedge \Big ( l _ { 1 } \Big [ 2 \Big ] = l _ { 2 } \Big [ 2 \Big ] \Big ) \wedge \ldots \wedge \Big ( l _ { 1 } \Big [ k - 2 \Big ] = l _ { 2 } \Big [ k - 2 \Big ] \Big ) } \\ & { \qquad \wedge \ ( l _ { 1 } \Big [ k - 1 \Big ] = l _ { 2 } \Big [ k - 1 \Big ] ) } \\ & { \qquad \boxdot { 1 } \ l _ { 1 } \Big [ k - 1 \Big ] < l _ { 2 } \Big [ k - 1 \Big ] } \end{array}
$$

c)剪枝步。 $C _ { k }$ 是 $L _ { k }$ 的超集，它的成员可以是也可以不是频繁的，但所有频繁 $\mathbf { k }$ -项集都包含在 $C _ { k }$ 中。扫描数据库，确定 $C _ { k }$ 中每个候选的计数，根据式（1）最小支持度确定Lk。然而 $C _ { k }$ 可能很大，这样所涉及的计算量就很大。任何非频繁的(k-1)-项集都不可能是频繁 $\mathbf { k } .$ 项集的子集。因此，如果一个候选 $k \mathrm { . }$ 项集的(k-1)-子集不在 $L _ { k - 1 }$ 中，则该候选也不可能是频繁的，从而可以从 $C _ { k }$ 中删除。

2)产生强关联规则在频繁项集产生之后，通过可信度来输出强关联规则，若 $A$ ， $B$ 为事务项集，则可信度为

$$
c o n d i f e n c e \big ( A \Longrightarrow B \big ) = \frac { S u p \_ c o u n t ( A \cup B ) } { S u p \_ c o u n t ( A ) }
$$

如果min_conf表示为最小可信度阈值，对于每一个频繁项集1，产生1的所有非空子集。对于每个非空子集S，如果满足式（4)，则输出规则： $s \Longrightarrow ( l - s )$ 0

$$
{ \frac { S u p \_ c o u n t ( l ) } { S u p \_ c o u n t ( s ) } } \ge \operatorname* { m i n } _ { - } c o n f
$$

# 2.2Apriori算法的流程

Apriori算法的流程如算法1所示。

算法1Apriori 使用根据候选生成的逐层迭代找出频繁项集。

输入：事务数据库D；最小支持阈值min_sup。

输出： $D$ 中的频繁项集 $L$ 。

方法：

1）扫描数据库D，找到频繁1项集；

2) for $( k { - } 2 ; L _ { k - 1 } \neq 0 ; k { + } + )$   
3) $C _ { k } { = } \mathrm { a p r o i r i \_ g e n } ( L _ { k - 1 } , m i n \_ s u p ) ; / / \vec { p } ^ { 3 }$ 生候选集，并剪枝  
4) for 每个事物 $t \in \mathbf { D } \{ \mathbf { \Omega } / \mathrm { ~ \Omega ~ }$ /扫描 $\mathrm { ~ D ~ }$ 进行候选集计数  
5) $C _ { t } { = } \mathrm { s u b s e t } ( C _ { k } , t ) ;$ //得到 $t$ 的子集  
6) for 每个候选集 $c \in C _ { t }$   
7） $c . \mathrm { c o u n t + + } ;$ （20  
8) }  
9) $L _ { k } { = } \{ c \in C _ { k } \mid c . \mathrm { c o u n t } { \geqslant } m i n \_ s u p \}$   
10) }  
11) return $L = \cup _ { k } L _ { k }$ //所有的频繁集;

procedure aproiri_gen( $L _ { k - 1 }$ :frequent (k-1)-itemsets;min_sup: minimum support threshold)

1) for 每个项集 $l _ { 1 } \in L _ { k - 1 }$ 2) for 每个项集 $l _ { 2 } \in L _ { k - 1 }$ 3) i $\cdot ( l _ { 1 } [ 1 ] = l _ { 2 } [ 1 ] ) \wedge ( l _ { 1 } [ 2 ] = l _ { 2 } [ 2 ] ) \wedge \cdots \wedge ( l _ { 1 } [ k - 2 ] = l _ { 2 } [ k - 2 ] )$ $\land ( l _ { 1 } [ k - 1 ] = l _ { 2 } [ k - 1 ] )$ then $\{$ 4) $c = l _ { 1 } \bowtie l _ { 2 }$ ；//连接步：产生候选集 5) if has_infrequent_subset $( c , L _ { k - 1 } )$ then 6 delete $c$ ；/／剪枝步：删除非频繁候选集 7) else 增加 $\mathbf { \Psi } _ { c }$ 到 $C _ { k }$ 集合中; 8） $\}$ 9) return $C _ { k }$

procedure has_frequent_ subset(c:candidate $k$ -itemset; $L _ { k - 1 }$ 0frequent(k-1)-itemset)//利用先验知识1) for 每个 (k-1)-subset $s$ of $c$ 2) if $s \notin L _ { k - 1 }$ then3) return TRUE;4) return FALSE;

# 3外生警源隐含特征挖掘实例应用

# 3.1数据获取及预处理

通过相关文献查阅、网站资料搜索、专家访谈和实地调研等方式，获取了近年来我国各地区发生的区域能源安全外生警源事件信息。经过数据提取、分析和预处理，构建了区域能源安全外生警源事务数据库。把表2中五个典型外生警源案例作为事务，通过对五个事务中隐含的规则进行挖掘来说明多维关联规则方法的应用过程和验证方法的可行性。

从表2可知，事务由多维属性来描述，即由多个谓词构成规则，因此利用多维关联规则方法来挖掘隐含在事务中的规律。首先利用表1对事务的特征属性划分，把多维属性转换为事务项，从而构建了事务数据库。转换的结果见表3。

# 3.2频繁项集的生成

为方便扫描事务信息表，假定事务中的项按属性的次序存放，事务数据库中有五个事务。设定最小支持度阈值$\operatorname* { m i n } _ { - } s u p { = } 6 0 \%$ ，即支持度计数阈值为3。图2给出了频繁项集的生成过程。

a)在第一次迭代过程中，表3中的每个事务项都是候选集，  
扫描事务数据库，记录每个事务项在事务中出现的次数，把大  
于等于支持度计数阈值的事务项作为频繁1-项集 $L _ { 1 }$ 。b）为发现频繁2-项集，执行连接 $L _ { 1 } { \Join } L _ { 1 }$ ，得到频繁2-项集  
的候选集。扫描事务数据库，记录每个候选项集出现的次数，  
把大于等于支持度计数阈值的候选项集作为频繁2-项集L2。c）执行连接 $L _ { 2 ^ { \ J } \circ L _ { 2 } }$ ，满足式（2）的两个频繁2-项集可连接  
得到频繁3-项集候选集。例如 $\{ T _ { d } , P _ { a } \}$ 和 $\{ T _ { d } , P _ { b } \}$ 满足条件，连接  
得到频繁3-项集候选集 $\left\{ T _ { d } , P _ { a } , P _ { b } \right\}$ 。同时，要用剪枝步删除不  
可能的项集。例如 $\{ T _ { d } , P _ { a } \}$ 和 $\{ T _ { d } , I _ { c } \}$ 连接时， $\{ P _ { a } , I _ { c } \}$ 不属于频繁

项集 $L _ { 2 }$ ，因此，连接后的结果 $\{ T _ { d } , P _ { a } , I _ { c } \}$ 不可能是频繁3-项集，要删除。得到频繁3-项集的候选集后，扫描事务数据库，记录每个候选项集出现的次数，把大于等于支持度计数阈值的候选项集作为频繁3-项集L3。同理，频繁4-项集、频繁5-项集都是按照步骤c）的方法产生。

<html><body><table><tr><td colspan="8">表2 外生警源数据表</td></tr><tr><td>事件编号 发生时间</td><td>E001 2008.01</td><td>E002 2009.11</td><td></td><td>E003 2011.10</td><td>E004 2012.11</td><td>E005</td><td>2013.11</td></tr><tr><td></td><td>上海、浙江、江苏、安徽、江西、河 南、湖北、湖南、广东、广西、重</td><td colspan="2"></td><td colspan="2">四川、重庆、江苏、</td><td colspan="2">北京、河北、江苏、浙江、</td><td>北京、天津、河北、内</td></tr><tr><td>发生地点</td><td colspan="2">庆、四川、贵州、云南、陕西、甘 肃、青海、宁夏、新疆</td><td colspan="2">武汉、西安、 南京、杭州</td><td colspan="2">浙江、山东、河北、 湖北</td><td colspan="2">山东、湖北、湖南、陕西、 蒙古、山西、陕西、四 内蒙古 川、云南、贵州、重庆</td></tr><tr><td>事件类型</td><td colspan="2">电力安全事件</td><td colspan="2">天然气安全事件</td><td colspan="2">石油安全事件</td><td colspan="2">天然气安全事件 天然气安全事件</td></tr><tr><td>诱发原因</td><td colspan="2">自然灾害</td><td colspan="2">自然灾害</td><td colspan="2">能源价格波动 季节交替变化</td><td colspan="2">季节交替变化</td></tr><tr><td>波及范围(省)</td><td colspan="2"></td><td colspan="2">4</td><td colspan="2">9</td><td colspan="2">10</td></tr><tr><td>持续时间(月)</td><td colspan="2">19</td><td colspan="2">0.5</td><td colspan="3">2</td><td>2</td></tr><tr><td>能源缺口程度</td><td colspan="2">1</td><td colspan="2">中等</td><td colspan="3">大</td><td>大</td></tr><tr><td></td><td colspan="2">非常大</td><td colspan="2"></td><td colspan="2">很大</td><td></td><td>很大</td></tr><tr><td>经济损失程度</td><td colspan="2">非常大</td><td colspan="2">中等</td><td colspan="2">很大</td><td colspan="2"></td></tr><tr><td>社会反响 非常大</td><td colspan="8">中等 大</td></tr><tr><td colspan="8">表3外生警源信息表 E002 E003</td></tr><tr><td>事件编号</td><td colspan="3">E001 Td,Pb,Pc,Pa,PfPg,Id, Td,Pb,Pc,Pg,Ic,Ce,</td><td colspan="2">Tc,Td,Pa,Pb,Pc,Pf,Ia, Ca,Rb,Db, Ge,Lf,Fe</td><td colspan="2">Td,Pa,Pb,Pc,Pg,Ic,</td><td>Td,Pa,PfPg,Ic,Cg,</td></tr><tr><td>相关信息</td><td colspan="3">Ce,Rd,Da,Gg,Lg,Fg</td><td>项集 {TdPa）</td><td>项集</td><td colspan="2">Cg,Rb,Db, Ge,Le,Ff</td><td>Rb,Db, Ge,Lf,Ff</td></tr><tr><td rowspan="12"></td><td>Td</td><td colspan="2">Ra,Da,Gd, Ld,Fd 项集支持度计数 5</td><td></td><td colspan="2">支持度计 {PD</td><td colspan="2">支持度计数</td></tr><tr><td></td><td>Pa 3 4</td><td></td><td></td><td>3 4</td><td>3 {P,G} 3</td><td></td></tr><tr><td>扫描信息表</td><td>P</td><td></td><td>{TdPb} {TdP</td><td></td><td>4</td><td rowspan="8"></td></tr><tr><td>得到频繁1-项集L</td><td>P P</td><td></td><td></td><td>4</td><td>{PP</td></tr><tr><td></td><td>4</td><td></td><td></td><td>3 {PbP</td><td>3</td></tr><tr><td></td><td>3</td><td>连接L</td><td>{TdPB</td><td></td><td></td></tr><tr><td>P</td><td>4</td><td></td><td>{TdP}</td><td>4 {PP</td><td>3</td></tr><tr><td></td><td></td><td>得到频繁2-项集L</td><td>{TdI</td><td>3</td><td>{P 3</td></tr><tr><td></td><td>3</td><td></td><td>{TdRb}</td><td>3</td><td>{R,Db 3</td></tr><tr><td></td><td>3</td><td></td><td>{TdDb}</td><td>3</td><td>{Rb,G} 3</td></tr><tr><td rowspan="12"></td><td>R D</td><td>3</td><td rowspan="2"></td><td>{TaG 3</td><td>{D，G 3</td><td></td><td rowspan="4"></td></tr><tr><td>G</td><td>3</td><td>{PaR}</td><td>3</td><td>连接L</td></tr><tr><td>项集</td><td>支持度计数</td><td></td><td colspan="2">得到频繁3-项集L</td><td></td></tr><tr><td>{T，PaRb,D} {Td,PaR,Ge}</td><td>3</td><td>项集</td><td>支持度计数</td><td>项集</td><td>支持度计数</td></tr><tr><td>{Td，PaD,G}</td><td>3</td><td>{Td,PaRb}</td><td>3</td><td>{TdDb,G}</td><td>3</td></tr><tr><td>{T,Pb,P,Pg}</td><td>3</td><td></td><td></td><td></td><td>3</td></tr><tr><td></td><td>3</td><td>{TaPa,Db}</td><td>3</td><td>{P,Rb,D</td><td></td></tr><tr><td>{Td,Rb，D,G} {P,Rb,D,G}</td><td>3</td><td>{TdPaG {TaPb，P}</td><td>3</td><td>{PaRb，G</td><td>3 3</td></tr><tr><td>连接L4</td><td>3</td><td colspan="2">连接L</td><td>3</td><td>{PaD,Ge} {P,PcPg</td></tr><tr><td colspan="2"></td><td></td><td rowspan="5">得到频繁4-项集L4</td><td colspan="2">{TdPbP</td><td>3</td><td>3 3</td></tr><tr><td>得到频繁5-项集L</td><td>支持度计数</td><td colspan="2" rowspan="4"></td><td>{T,PPg</td><td>3</td><td>{R,Db，G} {Td,R,Db}</td></tr><tr><td>项集</td><td></td><td>{TdPcP</td><td>3</td><td>3</td></tr><tr><td>{TdPaRb，Db,G}</td><td>3</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>{TdPgId</td><td>3</td><td>{TdRb，G</td><td>3</td></tr></table></body></html>

# 3.3强关联规则的产生

得到频繁项集后，按照式（4）来产生关联规则，设定最小可信度阈值 $\operatorname* { m i n } _ { - } c o n f { = } 1 0 0 \%$ 。在外生警源数据频繁项集中共挖掘出187条规则，构成了规则集。本文从规则集中截取部分规则，并对规则进行了解读，具体见表4所示。

通过对挖掘出的规则集进行分析，系统归纳出了隐藏在区域能源安全外生警源五个典型案例中的共性特征。

a)区域能源安全外生警源衍化性不论何种性质和规模的区域能源安全外生警源爆发，均会在短时间内不同程度地蔓延到其他地区，滋生出更严重、更广泛的能源安全事件。通过对区域能源安全外生警源规则集分析可知，187条规则中共有12条规则支持衍化特性，如规则16，华东地区爆发的能源安全事件会蔓延到华中地区。基于此类衍化特征分析结果，有助于缩减外生警源诱发的区域能源安全事件的波及范围，因为当某一地区外生警源爆发后，预警信号就会传递到相邻地区，使其快速作出有效的能源安全预警方案，以此降低能源安全风险发生的

概率或程度。

b)区域能源安全外生警源季节性基于对挖掘出的规则集进行归纳分析可知，区域能源安全外生警源表现出较强的季节性，多数区域能源安全事件爆发在冬季，187条规则中共有124条规则支持此类时间特性，如规则47和124等。其主要原因在于：在季节交替变化时，多数地区冬季对能源的需求量骤增，加之冬季易爆发雪灾等突发事件频率较高，这会在一定程度上影响能源的生产及供应。基于此类季节性特征表现，能有利于各地区根据季节性变化规律，在特定时期做好能源储备，并对季节性因素诱发的突发能源事件进行实时预警，降低区域能源缺口风险发生的概率。

表4部分规则及说明  

<html><body><table><tr><td>规则编号</td><td>规则</td><td>可信度</td><td>规则说明</td></tr><tr><td>规则11</td><td>{Pa}{Db}</td><td>100%</td><td>规则11表明华北地区能源安全外 生警源爆发要后持续1-3个月。</td></tr><tr><td>规则16</td><td>{Pb}{Pc}</td><td>100%</td><td>规则16表明华东地区爆发的能源 安全事件会蔓延到华中地区。</td></tr><tr><td></td><td>规则47{Pg,Ic}={Td}100%</td><td></td><td>规则47表明西北地区的天然气能 源的外生警源多爆发在冬季。</td></tr><tr><td>规则75</td><td>{Pa,Db} {Ge}</td><td></td><td>规则75表明华北地区能源安全外 100%生警源爆发时如果持续1-3 个月， 则能源缺口程度等级为大。</td></tr><tr><td>规则124</td><td>{Pb,Pc,Pg} {Td}</td><td></td><td>规则124表明华东地区、华中地区 100%和西北地区能源安全外生警源同时 爆发时多发生在冬季。</td></tr><tr><td>规则130</td><td>{Td,Pc,Pg} {Pb}</td><td>100%</td><td>规则130表明华中地区和西北地区 在冬季同时爆发能源安全外生警源 事件，则华东地区也会发生能源安 全事件。</td></tr><tr><td>规则156</td><td>{Td,Pa,Db,Ge} {Rb}</td><td>100%</td><td>规则156表明表明华北地区能源安 全外生警源在冬季爆发时如果持续 时间为1-3个月，能源缺口程度为 大，则波及范围为5-10个地区。</td></tr></table></body></html>

c)区域能源安全外生警源危害性基于对挖掘出的规则集分析可知，区域能源安全外生警源爆发后，所诱发的能源缺口的危害程度等级为大，187条规则中共有26条规则支持外生警源的危害特性，如规则75。其原因在于能源作为区域经济发展的主要基石，一旦出现缺口，势必会对地区生产及生活产生不利影响，进而阻碍地区的经济发展。基于此类危害性特征表现，有助于警示各地区在外生警源爆发后，努力通过各种途径积极调配能源，缩减能源缺口，以此降低外生警源爆发所带来的危害程度。

d)区域能源安全外生警源持续性区域能源安全外生警源爆发后，一般持续的时间较长。分析规则集可知，外生警源爆发后持续的时间一般为1\~3个月，187条规则中共有20条规则支持持续特性，如规则11。基于对此类持续性特征分析，能有利于警示各地区提早做好打持久战的预案，一旦在外生警源爆发后，可以有效应对外生警源持久性所带来的不利影响。

# 3.4在大规模数据中的应用效果

为验证多维关联规则挖掘算法在大量数据中的应用效果，本文收集了从1999年到2015年发生的100余个区域能源安全外生警源事件，并对外生警源事件进行数据提取、分析和预处理，构建了区域能源安全外生警源事务数据库。利用多维关联规则挖掘算法进行了规则挖掘，挖掘结果见图3。从图3可知，在区域能源安全外生警源事件数量较大时，多维关联规则挖掘算法是可行的，最小支持度的设定决定了挖掘出的关联规则数，随着最小支持度的增加，挖掘出的关联规则数逐渐减少。

![](images/8d1475707201e27437f057b25dcf1cbe794ebcef73cd18c6c2f045ecb3facfaa.jpg)  
图3多维关联规则在大量数据中的应用

# 4 结束语

通过对区域能源安全外生警源基本理论与多维规则挖掘方法的研究，对隐含在外生警源案例中的规律进行了分析，得到以下结论：

a）对区域能源安全外生警源的内涵进行了界定，通过外生警源典型案例的分析，抽取了各类外生警源的共性特征，构建了外生警源的特征属性。b）设计了外生警源多维规则挖掘方法，对外生警源特征属性进行了划分，将外生警源多维属性转换为了事务项。在此基础上，提出了频繁项集和强关联规则的产生方法。c)从外生警源案例集中截取了五个典型案例来验证多维关联规则方法的可行性，挖掘结果证明该方法是可行的，发现了隐藏在外生警源中的规律。

由于区域能源安全外生警源事件具有突发性、复杂性等特点，所以以下尚待解决的问题是今后研究重点：一是在外生警源数据中挖掘出的规则较多，以后重点应放在如何剪枝上；二是规则的解读效率较低，需要增加领域知识来加强对案例的理解。

# 参考文献：

[1]Vlado V.Evaluatingenergy security in the Asia-Pacific region:a novel methodological approach [J].Energy Policy,2010,38 (9): 5258-5263. [2]Loschel A,Moslener U,Rübbelke D.Indicators of energy security in industrialized countries [J].Energy Policy,2010,38 (4):1665-1671.

[3]刘立涛，沈镭，张艳．中国区域能源安全的差异性分析——以广东省和 陕西省为例 [J].资源科学,2011,33(12):2386-2393.(LiuLitao,Shen Lei, Zhang Yan.Regional differences in energy security of china: a case study of guangdong and shanxi provinces [J].Resources Science,2011,33 (12): 2386-2393.)

[4]赵春富，刘耕源，陈彬．能源预测预警理论与方法研究进展[J].生态 学报,2015,35(7):1-19.(Zhao Chunfu,Liu Gengyuan, Chen Bin.Advances in theories and methods of energy forecasting and early warning [Jl.Acta Ecologica Sinica,2015,35(7): 1-19.)

[5] 范秋芳．基于BP神经网络的中国石油安全预警研究[J].运筹与管理, 2007,16 (5):100-105.(Fan Qiufang. Research on China oil security prewarning based on BP neural networks [J].Operations Research and Management Science,2007,16 (5):100-105.)

[6]郭金栋，王恩元.煤炭能源安全测度指标体系与综合评价[J]．中国安 全科学 学报．2010,20(11):112-118.(Guo Jindong，Wang Enyuan Measurement indicator system & comprehensive appraisal for coal energy security in China[J].China Safety Science Journal,2010,20(11): 112-118.)

[7]苏飞，张平宇．中国区域能源安全供给脆弱性分析[J]．中国人口·资源 与环境,2008,18(6):94-99.(Su Fei, Zhang Pingyu.Vulnerability analysis ofregional energy security supply in china [J]. China Population,Resources and Environment.,2008,18(6): 94-99.)

[8]吴初国，何贤杰，盛昌明，等．能源安全综合评价方法探讨.[J]．自然资 源学报.2011,26(6): 964-970.(Wu Chuguo,He Xianjie,Sheng Changming, et al. Comprehensive method for evaluating energy security [J]. Journal of Natural Resources,2011,26(6): 964-970.)

[9] 胡剑波，吴杭剑，胡潇．基于PSR模型的我国能源安全评价指标体系构 建.[J]．统计与决策.2016(8):62-64.(Zhang Jianbo,Wu Hangjian,Hu Xiao.Construction ofChina's energy security evaluation index system based on PSR model[J]. Statistics& Decision,2016(8): 62-64.)

[10]张强．基于开放复杂巨系统理论的能源安全及预警研究[J].中国科技 论坛,2011 (2): 95-99.(Zhang Qiang.National energy security research based on complex giant system [J].Forum on Science and Technology in China,2011 (2):95-99.)

[11]周德群，鞠可一，周鹏，等．石油价格波动预警分级机制研究[J]．系 统工程理论与实践,2013,33(3):585-592.(Zhou Dequn,Ju Keyi,Zhou Peng,et al. Early-warning grading system for oil price shocks based on Hilbert-Huang transform[J].System Engineering Theory and Practice,2013, 33 (3): 585-592.)

[12]郭玲玲，武春友，于惊涛．中国能源安全系统的仿真模拟[J].科研管 理,2015,36(1): 112-119.(Guo Lingling,Wu Chunyou,Yu Jingtao.A study on simulating energy security system of China [J]. Science Research Management,2015,36(1): 112-119.)

[13]郝平，倪国华，余育青．基于OLAP分析和关联规则的区域能耗预警系 统研究[J].浙江工业大学学报,2013,41(5):534-538.(Hao Ping,Ni Guohua,Yu Yuqing.The research of regional energy consumption EWS based on OLAP analysis and association rules [J]. Journal of Zhejiang Universityof Technology,2013,41(5):534-538.)

[14]迟春洁．中国能源安全监测与预警研究[M].上海：上海交通大学出 版社，2011:101-1021.(Chi Chunjie.Research on energy security monitoring and early warning in China [M]. Shanghai: Shanghai Jiao Tong University Press,2011.)

[15]魏一鸣，吴刚，梁巧梅，等．中国能源安全报告 (2012)：能源安全研究 [M].北京：科学出版社,2012:226-229.(Wei Yiming,Wu Gang,Liang Qiaomei,et al. China energy re-port (2Ol2): energy security research [M]. Beijing:Science Press,2012.)

[16]魏一鸣，廖华，王科，等．中国能源安全报告 (2014)：能源贫困研究 [M].北京:科学出版社,2014: 56-87.(Wei Yiming,Liao Hua,Wang Ke, et al. China energy re-port (2Ol4): energy poverty research [M]. Beijing: Science Press,2014.)