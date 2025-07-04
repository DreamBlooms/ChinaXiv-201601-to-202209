# 基于贝叶斯网络的民航突发事件因果关系分析方法研究

王红，郭笑丹，祝寒(中国民航大学 计算机科学与技术学院，天津 300300)

摘要：针对民航突发事件因果关系无法有效评估与关联分析的问题，提出了一种基于贝叶斯网络的民航突发事件因果关系分析方法。在民航突发事件应急管理领域本体的基础上引入贝叶斯理论，首先通过规则设计实现了领域本体中概念、关系与实例的贝叶斯网络转换，然后采用贝叶斯网络知识合成算法 E-IPFP构建贝叶斯网络节点的条件概率表，并通过消息传递机制计算父子节点间的概率关系，获得民航突发事件因果关系的概率分布。采用民航突发事件应急管理领域本体和世界民航事故调查跟踪报告中的案例作为实验数据，给出了民航突发事件因果间关系的分析，为基于大数据的突发事件关联分析与推理提供了方法支持。

关键词：民航突发事件；领域本体；贝叶斯网络；因果关系；条件概率 中图分类号：TP399 doi:10.3969/j.issn.1001-3695.2017.09.0926

# Research on causal reasoning method of domain ontology based on Bayesian network

Wang Hong, Guo Xiaodan, Zhu Han (SchoolofComputer Science&Technology,CivilAviation University ofChina,Tianjin 300300,China)

Abstract: According tothefactthatcivilaviationemergencycannoteffectivelyevaluatecausalityandcorrelationanalysis,this paper proposed acausal analysis method for civilaviation emergencies based on Bayesian Network.The method introduces Bayesian theoryonthe basisof the domain ontologyof civil aviation emergency management.Firstly,the Bayesian network realizesthetransformationofconcepts,relationsand instances in domainontology withrules design.Then constructthe conditional probabilitytable for Bayesian network nodesusing Bayesiannetwork knowledge synthesis algorithmE-IPFP,and calculate the probabilityrelationship between parent nodes and child nodes hrough the message pasing mechanism,to obtain theprobabilitydistribution ofcivil aviation incidents causation.This paperadopts thecivil aviation emergency management domain ontologyandthe worldcivil aviation accident investigation trackingreportas experimental data,gives the analysis of thecausalrelationship between civil aviation emergencies,which provides the methodto support thecorelationanalysis and reasoning of unexpected events based on large data.

Key Words: civil aviation emergencies; domain ontology; bayesian networks; causality; conditional probability

# 0 引言

民航突发事件应急管理是为了应对民航突发事件而进行的一系列有计划有组织的管理过程，主要任务是如何有效地预防和处置各种突发事件，最大限度地减少突发事件的负面效应、人员伤亡和财产损失[1]。事件间因果关系[2-3]的分析对民航突发事件应急管理中的预防与处置具有重要的意义。目前基于领域本体的民航突发事件应急管理的相关研究主要集中在领域本体的构建、采用SWRL和描述逻辑等基于规则的应急方案的推理和相似案例的检索[4,5,6]等方面，缺乏基于领域本体的突发事件因果关系分析与推理的研究。

贝叶斯网络[7lBN(Bayesian network)于1985年由JudeaPearl首先提出，是一种基于概率推理的图形化网络，针对不确定性知识推理与数据分析的模型[8,9,10]。蔡炳万[11]等提出了一种基于本体的贝叶斯网络知识推理方法，主要思想是依据产品设计过程中设计任务、设计人员、设计知识三个本体模型来建立贝叶斯网络的拓扑结构，没有考虑本体与贝叶斯网络的转换问题。张什永[12]等针对本体到贝叶斯网络转换中概率不一致的问题，提出了一种改进的贝叶斯网络知识合成算法E-IPFP[13]，该方法通过加入约束集合有效的解决了BN中概率不一致时的合成问题。

本文将E-IPFP 算法与民航突发事件应急管理领域本体相结合，设计了一组将领域本体转换为贝叶斯网络的规则，实现了本体与贝叶斯网络的的转换；在获取突发事件因果关系证据节点概率的基础上，采用E-IPFP算法与消息传递机制进一步计算节点的后验概率，从而获得突发事件的因果关系的概率分布关系，该方法旨在解决基于领域本体的民航突发事件因果关系关联分析与推理问题，为突发事件的预防与处置提供更好的数据支持。

# 1 研究思路

基于贝叶斯网络的民航突发事件因果关系分析思路如图1所示。

![](images/a7225e102e170b21da405dfa4e27b964dd03ceba6573f2b2b56ccf071b004663.jpg)  
图1基于贝叶斯的民航突发事件因果关系分析过程

a)数据预处理。将民航突发事件应急管理领域本体解析为RDF 图，并根据世界民航事故调查跟踪信息报告[14]中的专家分析对RDF图中的节点设置概率属性生成节点的概率文件。

b)贝叶斯网络的转换。设计规则实现领域本体RDF图到贝叶斯网络BN的转换，并采用贝叶斯知识合成算法E-IPFP实现概率的合成，生成领域本体贝叶斯网络BN_O。

c)事件因果关系分析。采用基于消息传递机制的贝叶斯网络推理，实现事件因果关系概率值传递，获得事件因果关系的概率分布。

# 2 基于领域本体的BN构建方法

贝叶斯网络包括一个有向无环图DAG(directedacyclicgraph)和一个条件概率表集合CPT(conditional probability table)。定义 $B N = \{ G , P \}$ ， $G$ 代表有向无环图 $G = \{ V , \ E \}$ ，其中 $V$ 表示图中的节点（随机变量）集合， $E$ 表示有向边集合代表变量之间的关系； $P$ 表示节点条件概率表的集合，每个节点对应一个条件概率分布表，该表是对节点变量与其父节点之间关系程度描述。若存在节点 $V _ { i }$ 直接影响到节点 $V _ { i + 1 }$ ，即 $V _ { i } \to V _ { i + 1 }$ ，则建立有向弧 $( V _ { i } , \ V _ { i + l } )$ ， $( V _ { i } , \ V _ { i + 1 } )$ 的权值(即连接强度)用条件概率 $P ( V _ { i + 1 } \mid V _ { i } )$ 来表示，存储于条件概率表中。

# 2.1 转换规则的定义

领域本体是对概念、概念间关系的描述，包括类、关系、实例，领域本体RDF是由一系列三元组（主体，谓语，客体）组成的，其中主体、客体代表本体中的概念 $C$ ，谓语代表本体中的关系 $R$ ，这些三元组形成如图2所示的领域本体RDF图。

根据以下规则将领域本体RDF图转换为贝叶斯网络：

规则1对于本体RDF图中的概念集合$C = \{ C _ { 1 } , ~ C _ { 2 } , . . . , ~ C _ { \mathrm { { n } } } \}$ ， $C _ { i }$ 对应到贝叶斯网络中的节点$V C _ { i } = \left( a , \ { \overline { { a } } } \right)$ （ $i \in { \mathfrak { n } }$ ）， $( a , \ { \overline { { a } } } )$ 分别表示概念 $C _ { i }$ 的状态属性中True 和False 的概率值。

规则2 $R = \{ R _ { 1 } , R _ { 2 } , . . . , R _ { \mathrm { S } } \}$ 表示本体的关系集合，若本体中概念 $C _ { i }$ 与概念 $C _ { i + 1 }$ 存在关系 $R _ { \mathrm { x } }$ ，且 $C _ { i }$ 直接影响 $C _ { i + 1 }$ ，则将两个概念之间的影响关系 $R _ { \mathrm { x } }$ （ $\mathbf { \boldsymbol { x } } \in S$ ）映射为 $B N$ 中节点 $V _ { i }$ 与 $V _ { i + 1 }$ 之间的有向边 $E _ { \mathrm { x } }$ 口

规则 3对于本体中实例 $I = \{ I _ { 1 } , I _ { 2 } , . . . , I _ { \mathrm { { m } } } \}$ ，将 $I _ { j }$ （ $\mathbf { j } \in \mathbf { m }$ )对应到贝叶斯网络中的节点 $\boldsymbol { W } _ { \mathrm { j } } = ( a , ~ \overline { { a } } )$ ，$( a , \ { \overline { { a } } } )$ 分别表示实例 True 和 False 的概率值。

映射过程如图2所示。

![](images/436fd2d17483707b5f9f5f0356882371a3b178baeef9739af685e14687e1de31.jpg)  
图2映射过程

# 2.2基于E-IPFP的 BN节点条件概率表构建

2.2.1基于E-IPFP的贝叶斯知识合成算法

贝叶斯知识合成算法是将给定的概率知识合成到贝叶斯网络的过程，基本思路如下：

a)输入联合概率 $P _ { 0 } ( X ) = \prod _ { i = 1 } ^ { n } P _ { 0 } ( X _ { i } \mid \pi _ { i } )$ ,并将 BN 中概率集合 ${ \cal D } = \{ D _ { 1 } , D _ { 2 } , . . . , D _ { \mathrm { m } } \}$ 作为约束条件;

b)判断其在新的约束条件下是否收敛，若收敛，计算当前联合概率分布 $P _ { k } ( X ) ( k \in \mathbf { m } )$ ：若 $P _ { k - 1 } ( Y ^ { i } ) = 0$ ，则 $P _ { k } ( X ) = 0$ ，否则

$$
P _ { k } ( X ) = P _ { k - 1 } ( \mathrm { X } ) \bullet { \frac { D ( Y ^ { i } ) } { Q _ { k - 1 } ( Y ^ { i } ) } }
$$

循环计算直至收敛；

c)若不收敛，则分别在约束集与概率上加入 $\mathfrak { a }$ 参数，$D _ { 1 } ( Y ^ { i } ) = ( 1 - \alpha ) D ( Y ^ { i } ) + P _ { k - 1 } ( Y ^ { i } )$ 作为新的约束循环计算 $P _ { k } ( X )$ 直至收敛。其中: $X$ 代表贝叶斯网络中的节点随机变量， $\mathfrak { n }$ 代表变量个数，$P ( X \mid \pi )$ 为节点的条件概率， $\alpha \in ( 0 , 1 )$ 为约束条件的参数，$P _ { k } ( X )$ 表示当前的联合分布， $Q ( Y )$ 表示子节点联合概率分布，Y为 $X$ 的子节点集， $\pi$ 为 $X$ 的父节点集合， $D$ 表示新的约束条件, $\mathbf { m }$ 为约束集个数。

# $2 . 2 . 2 ~ \mathrm { B N }$ 节点条件概率表构建

节点条件概率表的构建是将RDF图中节点概率文件中True和False的状态值转换到BN中节点条件概率表的过程，转换的方法：

a)本体 RDF 图中节点概率属性值不为空时，即当节点 $C _ { i }$   
直接影响到节点 $C _ { i + 1 }$ 时，则将其对应于BN 中的 $V _ { i } \setminus V _ { i + 1 }$ 节点，  
此时 $C _ { i + 1 }$ 的条件概率为 $P _ { C _ { i + 1 } } ( a _ { i + 1 } \vert a _ { i } )$ ，其中 $a _ { i }$ 代表  
$C _ { i } = T r u e$ ， $a _ { i + 1 }$ 代表 $C _ { i + 1 } = T r u e$ ，在概率文件中的表示为<owl:Probabilityrdf:ID $\scriptstyle \gamma = " \mathrm { P } ( \mathrm { a } _ { \mathrm { i } + 1 } | \mathrm { a } _ { \mathrm { i } } ) " >$ <hasProposition ${ \tt > } { \tt a } _ { \mathrm { i } + 1 } { \tt < } ,$ /hasProposition><hasCondition>ai</hasCondition><hasValue $> 0 . 6 3 < /$ hasValue></owl:Probability>

转换到贝叶斯网络中以条件概率表的形式存储， $V _ { i }$ 直接影响到 $V _ { i + 1 }$ 并作为 $V _ { i + 1 }$ 的父节点，节点 $V _ { i + 1 }$ 的条件概率如表1所示。

表1 $V _ { i + I }$ 节点条件概率  

<html><body><table><tr><td>Vi</td><td>P(Vi+1 |Vi)</td></tr><tr><td>True</td><td>0.63</td></tr><tr><td>False</td><td>0.371</td></tr></table></body></html>

b)本体RDF图中节点概率属性值为空时，则在转换过程中，遵循默认值的设定，即节点的状态初始值设为 $0 . 5 ( \mathrm { T r u e } { = } 0 . 5 \$ False $\scriptstyle : = 0 . 5$ ）

设领域本体中事件的原因 $S .$ 、结果 $R$ 、事件严重程度 $G$ 为3个类概念，事件实例集合 $E$ ，根据映射规则，采用以下的E-IPFP的贝叶斯知识合成算法进行转换：

(a)采用规则1为RDF图中概念节点 $C _ { i }$ 设置状态属性True和False并赋值，其中突发事件类中事件原因节点 $S _ { i }$ 转换成BN中的节点 $V S _ { i }$ ，事件结果节点 $R _ { i }$ 转换成BN中的节点 $V R _ { i }$ ，事件严重程度节点 $G _ { i }$ 转换为BN 中的节点 $V G _ { i }$ ：

(b)采用规则2对突发事件本体中事件实例、原因、结果之间的关系 $R _ { i }$ 进行映射转换为网络中的有向边 $E _ { i }$ ，并严格遵守上下层次关系，上层概念为下层概念的父节点；

(c)采用规则3对RDF图中事件实例节点 $E _ { i }$ 进行转换，为节点状态属性赋值并对应到贝叶斯网络中的节点 $V E _ { i }$ ，根据其原因属性与结果属性决定父子节点；根据人员伤亡、经济损失、航空器损坏程度3个数据属性值确定节点 $V E _ { i }$ 到事件严重程度节点 $V G _ { i }$ 的连接关系。

转换后的领域本体贝叶斯网络如图3所示。

![](images/816a258894aa6645d9216b96a4a913277932eadc76d3e3ff29bd54d05d92e42d.jpg)  
图3领域本体的贝叶斯网络(BN_O)

# 2.3基于消息传递的贝叶斯推理

消息传递是根据节点集合 $V$ 中每个节点自身的条件概率$P ( V )$ 与相邻节点传递概率值来求解后验概率[15]的过程。定义网络中节点状态True $_ { : = 1 }$ 的节点为证据节点 $V$ ，反之为非证据节点 $V ^ { \prime }$ ，如图4所示子节点 $V "$ 向父节点 $V ^ { \prime }$ 传递的消息称为$\lambda$ 消息，父节点返回给子节点称为 $\rho$ 消息，通过给定的证据来计算所有节点的后验概率 $P ( V ^ { \prime } )$ 。

![](images/9f20c04a3050e51b2a4f18fa52180dafcd8e59f2db7c0126bc8445f3cb9ff601.jpg)  
图4节点消息传递过程

基于消息传递的推理算法：

a)输入条件概率 $P ( V )$ ，证据节点集合 $V = \{ V _ { 1 } , V _ { 2 } , . . . , V _ { i } , . . . , V _ { n } \} \circ$ （202

b)如果非证据节点 $V ^ { \prime }$ 有父节点，则受到其父节点传递的消息，用式(2)求出 $\rho _ { v _ { i } } ( V _ { i } ^ { \prime } )$ 。

$$
\rho _ { \mathrm { v i } } ( \mathbf { V } _ { \mathrm { i } } ) = \sum _ { V } P \ \left( \mathbf { V } _ { \mathrm { i } } | V _ { i } \right) \prod _ { j = 1 } ^ { p } \rho _ { V _ { j } V _ { i } ^ { \prime } } ( V _ { i } ^ { \prime } )
$$

如果 $V ^ { \prime }$ 有子节点，子节点集合为 $V "$ ，用公式(3)计算$\lambda _ { V _ { i } ^ { \prime } } ( V _ { i } ^ { \prime } )$

$$
\lambda _ { V _ { i } ^ { \prime } } ( V _ { i } ^ { \prime } ) { = } \prod _ { j { = 1 } } ^ { \mathrm { m } } \lambda _ { V " , V " _ { i } } ( V " _ { i } )
$$

如果 $V ^ { \prime }$ 既有父节点又有子节点，分别计算

$$
\rho _ { { { \scriptscriptstyle V } } _ { \mathrm { i } } { { \scriptscriptstyle V } } _ { \mathrm { i } } ^ { \mathrm { * } } \mathrm { _ { j } } }  ( V _ { i } ^ { \prime } ) = \rho _ { { { \scriptscriptstyle V } } _ { \mathrm { i } } \mathrm { _ { \scriptscriptstyle V } } ^ { \mathrm { * } } } ( V _ { \mathrm { i } } ^ { \prime } ) { \prod } _ { k \ne j } { \lambda } _ { { { \scriptscriptstyle V } } _ { k } { \cdot } { { \scriptscriptstyle V } } _ { i } } . ( V _ { i } ^ { \prime } )
$$

$$
\lambda _ { V _ { i } ^ { \prime } } ( V _ { i } ^ { \prime } ) { = } \prod _ { j { = 1 } } ^ { \mathrm { m } } \lambda _ { V _ { j } " V _ { i } ^ { \prime } } ( V _ { i } ^ { \prime } )
$$

发事件 $U _ { 1 }$ 与非航空器突发事件 $U _ { 2 }$ ；与 $U _ { 1 }$ 、 $U _ { 2 }$ 事件相关的原因 $S = \left\{ S _ { 1 } , \ S _ { 2 } , . . . , \ S _ { i } , . . . S _ { n } \right\} ( i \in n \ ) , S _ { i }$ 的子类为 $S _ { i j }$ ；突发事

c)输出 $P _ { V _ { \mathrm { i } } ^ { \prime } } ( V _ { \mathrm { i } } ^ { \prime } )$ 。

件中与航空器相关的事件结果如表2 所示；事件严重程度 $G _ { j }$ 分为：一般 $G _ { 1 }$ 、较大 $G _ { 2 }$ 、重大 $G _ { 3 }$ 、特大 $G _ { 4 }$ 四个类别。

$$
R _ { i } \colon ( V _ { i } ^ { \prime } ) = \lambda _ { V _ { i } } \colon ( V _ { i } ^ { \prime } ) \rho _ { V _ { i } } \colon ( V _ { i } ^ { \prime } )
$$

# 3 应用与效果分析

# 3.1领域本体的贝叶斯网络转换

表2民航突发事件中与航空器相关的事件结果  

<html><body><table><tr><td>ID</td><td>事件结果</td></tr><tr><td>R1</td><td>航空器坠毁</td></tr><tr><td>R2</td><td>航空器失联</td></tr><tr><td>R</td><td>航空器重着陆</td></tr><tr><td>R4</td><td>航空器暂停使用</td></tr><tr><td>R5</td><td>航空器空中遇袭</td></tr><tr><td>R6</td><td>航空器冲偏出跑道</td></tr><tr><td>R7</td><td>跑道入侵</td></tr></table></body></html>

民航突发事件应急管理领域本体中的核心概念包含应急预案、应急资源、应急演练、突发事件、应急处置、资源报告、善后处置等类，突发事件及其因果关系的RDF图如图5所示。其中：突发事件 $U = \{ U _ { 1 } , \ U _ { 2 } , . . . , \ U _ { i } , . . . , \ U _ { \mathrm { n } } \} ( \ i \in n$ )包含航空器突

航空器结构故障S2人 地面指挥原因S7操纵系统故障 Cause 环境原因Sn Rdf :partof ?S4 _Cause :partof- Cause（ Owl:classvent Cause vent_ 小 空管指挥不当 S71 string←Redf:type 天气原因Sn1 机组原因SiCauseFrdfs:range>7.29MS-667 Rdf.type- 航空器突发事件U Event_ Event_Cause -Rdf:partof-t_CausCause 2 -EventCayse 飞行员操纵失机载电子设备 Rdf.typ rdfs:subClassOf> 8.24VD8387 误Si1 （ Owl:Namedindividual)-Event_Cause/ rdfs Cause突发事件U s:type-11.4QF-32295机翼尾翼故障 S3 Event_R Event_Grade t_Result Ever -rdfs:type Cause -Death_Persons- -rdfs:type- -rdfs:type- 9 rdfs:rany intOwl:classR6 √ 非航空器突发事件G 发动机故障S11 Cause 起落装置故障 U2 rdfs:type- Rdf:type- 7.17MH17 -Event_Cat -Event_Cause 恐怖行为S81 Owl:dataPropertydfs-rdfs:type- dfs:r range- Rdf: （ Owl:class dfs rangeX stringstring Cause -Rdf:partof- s:type-Owl:dataProperty of 航器动力装 COwl:dataProperty乘客原因S8 危险品Sn1说明：实线椭圆：本体概念，RDF三元组的主体（subjects）、客体（objects）。虚线椭圆：本体属性，RDF三元组的客体（objects）。有向箭头：语义关系，RDF三元组的谓词（predicates）。

实验采用民航突发事件应急管理领域本体以及世界民航事故调查跟踪信息报告中2014-2016 年间的案例与专家结论，为领域本体RDF中每个节点设置状态属性值。在突发事件概念类中航空器突发事件和非航空器突发事件的发生或存在的可能性初始值为0.5，生成本体RDF的节点概率文件：

<owl:Variablerdf:ID $\scriptstyle 1 = 1$ 航空器突发事件">   
<hasClass>CAEDO.航空器突发事件</hasClass>   
</owl:Variable>   
<owl:Proposition rdf:ID $\vDash$ "a1">   
<hasVariable>航空器突发事件 ${ < } /$ hasVariable>   
<hasState>True</hasState>   
</owl:Proposition>   
<owl:Proposition rdf:ID $\vDash$ "b1">   
<hasVariable>航空器突发事件 ${ < } /$ hasVariable>   
<hasState>False</hasState>   
</owl:Proposition>   
<owl:Probabilityrdf:ID $\vDash$ "P(al|a)">   
<hasPropCollection>ml</hasPropCollection>

<hasValue $> 0 . 5 < /$ hasValue> </owl:Probability> </owl:Proposition>

本体数据与概率数据作为输入，采用2.2.1的方法将概率属性值 $P ( C )$ 作为算法的输入，形成完整的贝叶斯网络BN_O。其中突发事件原因节点 $S _ { i }$ 对应BN 的节点 $V S _ { i }$ （ $i \in { \mathfrak { n } }$ ）；事件结果 $R _ { i }$ 对应为叶子节点 $V R _ { i }$ （ $i \in \mathbf { X }$ ）；事件严重程度 $G _ { i }$ 对应为叶子节点 $V G _ { i }$ （ $i \in { \mathfrak { q } } \ )$ ；事件实例 $E _ { i }$ 对应贝叶斯网络中的节点 $V E _ { i }$ （ $i \in \mathbf { m }$ ）。

# 3.2基于消息传递的贝叶斯推理

采用2.3算法设置BN_O中的证据节点集合，以集合中节点条件概率作为消息传递推理算法的输入，对节点的后验概率进行推理。

设节点 $\boldsymbol { V } \boldsymbol { E } _ { I }$ 、 $V E _ { 2 }$ 代表非航空器突发事件（如：7.17MH17马航客机被导弹击中坠毁事件、8.24VD8387河南航空8月24日伊春坠机事件）， $V E _ { 3 }$ 、 $V E _ { 4 }$ 代表航空器突发事件（如11.4QF-32澳大利亚快达航空飞机发动机非包容性失效事件、7.29MS-667埃及航空飞机驾驶舱失火事件）；节点 $V S _ { i l }$ （飞行员操纵失误）、 $ { V }  { S } _ { 7 I }$ （空管指挥不当）、 $\phantom { } _ { V S _ { n 2 } }$ （天气原因）代表事件原因。

基于消息传递的推理实现如下：

输入：贝叶斯网络BNO（网络结构和条件概率表集合），证据节点 $V E _ { 2 }$ 取值状态True $\scriptstyle : = 1$ ·

输出：非证据节点 $\mathrm { V S } _ { \mathrm { i } 1 } , \mathrm { V S } _ { 7 1 } , \mathrm { V S } _ { \mathrm { n } 2 }$ 的条件概率分布： $\mathrm { { P } ( V S _ { i l } ) }$ 、$\mathrm { P ( V S _ { 7 1 } ) . ~ \ P ( V S _ { n 2 } ) }$

设置证据节点 $V E _ { 2 }$ 传递消息初始值：

$$
\rho _ { { _ { V E 2 } } } \left( F \right) = 0 . 0 , ~ \rho _ { { _ { V E 2 } } } \left( T \right) = 1 . 0
$$

$$
\lambda _ { \scriptscriptstyle { V E 2 } } \left( F \right) = 0 . 0 , \lambda _ { \scriptscriptstyle { V E 2 } } \left( T \right) = 1 . 0
$$

根据非证据节点 $\mathit { V S } _ { \mathit { I I } } , \mathit { V S } _ { \mathit { i I } } , \mathit { V S } _ { 7 \mathit { I } }$ 的条件概率表设置如下：

$$
\begin{array} { l } { \rho _ { _ { V S _ { 1 1 } } } ( F ) = 0 . 4 5 , ~ \rho _ { _ { V S _ { 1 1 } } } ( T ) = 0 . 5 5 } \\ { \rho _ { _ { V S 7 1 } } ( F ) = 0 . 5 0 , ~ \rho _ { _ { V S 7 1 } } ( T ) = 0 . 5 0 } \\ { \rho _ { _ { V S _ { 1 2 } } } ( F ) = 0 . 4 0 , ~ \rho _ { _ { V S _ { 1 2 } } } ( T ) = 0 . 6 0 } \end{array}
$$

通过式(3)计算出 $V E _ { 2 }$ 的 $\lambda _ { V E _ { 2 } }$ ：

$$
\lambda _ { \scriptscriptstyle { V E 2 } } \left( F \right) = 0 . 2 5 , \lambda _ { \scriptscriptstyle { V E 2 } } \left( T \right) = 0 . 7 4
$$

对于节点 $V S _ { i l }$ $\ Y _  i l \setminus \} \ V S _  7 l \setminus \} \ V S _ { n }$ ，获得子节点传递的消息 $\lambda$ ，输入 $\rho , \lambda$ 值采用公式(6)计算 $P ( V S _ { i l } ) , ~ P ( V S _ { 7 l } ) , ~ P ( V S _ { n 2 } )$ ；同理计算出节点 $V E _ { 2 }$ 的后验概率。

直至整个网络中无消息传递，输出节点的后验概率，图6给出了与事件因果关系相关的部分概率分布计算结果。

# 3.3效果分析

根据图6中领域本体突发事件因果关系的概率分布以及各个节点的条件概率表，在以节点 $V E _ { i }$ 为证据节点的计算中，可得出事件原因概率分布，图中事件节点 $V E _ { 2 }$ 的条件概率表如表3所示。

![](images/f6c4fe2e08f89a6e53afb27e679311f9d8afc5cf44e712055ef3a6a908352f92.jpg)  
图6突发事件因果概率分布部分结果

表3 $V E _ { 2 }$ 节点的条件概率  

<html><body><table><tr><td>VSi1</td><td>VS71</td><td>VSn2</td><td>P(VE2|VSi,VS7i,VSn2)</td></tr><tr><td>T</td><td>T</td><td>T</td><td>1</td></tr><tr><td>T</td><td>T</td><td>F</td><td>0.86</td></tr><tr><td>T</td><td>F</td><td>T</td><td>0.84</td></tr><tr><td>T</td><td>F</td><td>F</td><td>0.7</td></tr><tr><td>F</td><td>T</td><td>T</td><td>0.3</td></tr><tr><td>F</td><td>T</td><td>F</td><td>0.16</td></tr><tr><td>F</td><td>F</td><td>T</td><td>0.14</td></tr><tr><td>F</td><td>F</td><td>F</td><td>0</td></tr></table></body></html>

表3给出了图6中节点 $V E _ { 2 }$ 代表的突发事件与3个原因父节点 $V S _ { i l }$ 、 $ { V }  { S } _ { 7 l }$ 、 $\phantom { } _ { V S _ { n 2 } }$ 之间的的概率传递关系。其中：

a)当3个原因节点 $V S _ { i l }$ 、 $V S \gamma _ { I }$ 、 $\cal { V } S _ { n 2 }$ 状态都为T（即3个原因都存在）时， $V E _ { 2 }$ 事件发生的概率为1。

b)当3个原因节点 $V S _ { i l }$ 、 $V S \gamma _ { I }$ 、 $V S _ { n 2 }$ 中同时存在2个原因时，事件发生的概率与原因1和原因2的相关程度会不一样，表3中概率为0.86时与 $\phantom { } _ { V S _ { n 2 } }$ 更相关，而概率为0.84时则与 $V S _ { 7 I }$ 更相关，特别值得注意的是概率为0.3时与 $V S _ { i l }$ 更相关，反映出不同原因对事件的影响差异较大。

c)当3个原因节点 $V S _ { i l }$ 、 $V S _ { 7 I }$ 、 $\phantom { } _ { V S _ { n 2 } }$ 中只存在1个原因时，不同原因导致事件发生的概率最大为0.7（甚至高于多个原因的情况），最小为0.14，进一步反映出不同原因对航空安全事件的不同影响。

d)当3个原因节点 $V S _ { i l }$ 、 $V S _ { 7 I }$ 、 $\phantom { } _ { V S _ { n 2 } }$ 状态都为F（即3个原因都不存在）时， $V E _ { 2 }$ 事件发生的概率为0。

由此可以进一步推理出不同事件与多种原因的概率关系。

# 4 结束语

基于贝叶斯网络的民航突发事件因果关系分析方法结合了领域本体的语义知识表达与贝叶斯网络的概率推理能力，通过领域本体与贝叶斯网络转换规则的设计实现了基于领域本体的贝叶斯网络构建，采用世界民航事故调查跟踪信息报告中专家的评价给出了贝叶斯网络证据节点的概率属性设置，将E-IPFP概率融合算法与消息传递机制引入贝叶斯网络完成了突发事件因果关系节点变量的后验概率值的计算，在获得不同类别突发事件因果关系分布的同时，有效解决了基于领域本体的民航突发事件因果关系的分析，为进一步基于领域本体的因果关系推理奠定了很好的数据基础。未来将针对海量的领域本体RDF 图与贝叶斯网络转换及其分布式推理进行深入的研究。

# 参考文献：

[1]CCAR396-R3，民用航空安全信息管理规定[S].  
[2]干红华．基于事件的因果关系可计算化分析研究[D].杭州：浙江大学,2003.  
[3]钟军，禹龙，田生伟，等．基于双层模型的维吾尔语突发事件因果关系抽取[J]．自动化学报,2014,40(4):771-779.  
[4]周文涛，王红，王静.民航应急决策方案语义模型构建方法的研究[J].计算机应用研究,2013,30(1):195-198.  
[5]李林，王红，付宇，等．民航突发事件应急案例语义检索方法研究[J]计算机工程与设计,2011,32(3):1130-1133.  
[6]王红，杨璇，王静，等．基于本体的民航应急决策知识表达与推理方法研究[J].计算机工程与科学,2011,33(4):129-133.  
[7]吴贤国，丁保军，张立茂，等．基于贝叶斯网络的地铁施工风险管理研究[J]．中国安全科学学报,2014,24(1):84.  
[8] 谢红薇，闫婷，车晋强．本体驱动的贝叶斯网络模型在医学诊断中的应用[J]．太原理工大学学报,2016,47(3):389-393.  
[9]Elster C,Wübbeler G.Bayesian inference using a noninformative prior forlinear Gaussian random coefficient regression with in homogeneous within-class variances [J]. Computational Statistics,2O17,32:1-19.  
[10] WoodF,Willem VDMJ,Mansinghka V.A New Approach to ProbabilisticProgramming Inference [J].Computer Science,2015:1024-1032.  
[11]蔡炳万，石宇强，李明辉，等．基于本体的贝叶斯网络知识推理研究[J]．机械设计与制造,2016(1):84-87.  
[12]张什永．贝叶斯网不确定性推理研究[D].合肥：中国科学技术大学，2010.  
[13]Liu Y,Chen S,Li S,etal. Bayes-SWRL:a probabilistic extension of SWRL[C]//Proc of the 9th International Conference on Computational Intelligenceand Security.Washington DC: IEEE Computer Society,2013: 702-706.  
[14] http://safety.caac. gov.cn/index/initpage.act [EB/OL]. 2017.  
[15]赵建喆，李凯．一种改进的多模块贝叶斯网络局部推理算法[J]．东北大学学报：自然科学版,2015,36(9):1251-1255.