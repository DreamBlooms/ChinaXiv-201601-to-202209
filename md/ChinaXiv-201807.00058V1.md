# 需求不确定的电动汽车换电站选址鲁棒模型

刘慧1，张 迪²，杨超²

(1．湖北经济学院 湖北物流发展研究中心，武汉 430205;2.华中科技大学 管理学院，武汉 430074)

摘要：在电动汽车换电站选址问题中，用户充电需求是重要的输入参数，而需求受到技术发展、电动汽车保有量、国家相关政策等因素的影响，通常较难准确预测。本文假设交通网络上用户需求是不确定的，利用基约束鲁棒优化方法提出基于用户路径流量不确定的换电站选址鲁棒模型，并将鲁棒模型转化为等价的线性规划。最后应用Nguyen-Dupius 网络作为数值算例进行分析，结果表明当解的鲁棒水平较低时，适当增加选址成本，可以较大程度地提高解的鲁棒性。同时，对模型的重要参数作灵敏性分析。随着鲁棒水平的提高，换电站选址成本对路径流量的波动越来越敏感，续航里程的改变对换电站选址策略影响较大。

关键词：电动汽车；换电站选址；需求不确定；鲁棒优化 中图分类号：0221 doi: 10.3969/j.issn.1001-3695.2018.04.0246

# Research on robust battery swap stations location model of electric vehicles

Liu Huia, Zhang Dib, Yang Chaob (1.Research Centerof Hubei Logistics Development Hubei UniversityofEconomics,Wuhan 430205,China;b.Schoolof Management,Huazhong University of Science & Technology,Wuhan 43oo74,China)

Abstract:The users’charging demand is important input parameters inthe batery swap stations location problemof electric vehicles.The demand is influenced bytechnological development,the numberof electricvehicles andtherelevant policies, and it isoften dificult topredictaccurately.This research examines therobust bateryswap stations location problem with flowuncertainty.Supposing theusers’demand on the traffic network path is uncertain,thecardinalityconstrained robust approach is employedto formulate the robust batery swap stations location model.The model can be transformed toalinear optimization problem.We usethe Nguyen-Dupius network as a numerical example.Theresults show that when the robust level of the solution islow,therobust levelcanbeimproved greatlybyappropriately increasing thelocationcost.Inaddition, thesensitivityanalysis isconducted for important parametersof the model.Theresultsshow that,the location cost is increasinglysensitive tothe fluctuationof path flow with the improvement ofrobust level.The change ofdriving range has a great impact on the location strategy.

Key Words: electric vehicles; batery swap stations location; uncertain demand; robust approach

# 0 引言

电动汽车因其清洁节能的显著优势，逐步成为汽车市场的主流发展方向。在巨大的环境压力和未来市场空间预期的双重作用下，各国政府纷纷介入电动汽车市场，并将发展电动汽车作为应对能源和环境问题的重要举措。然而，电动汽车市场的推广进展却很缓慢。其中一个重要原因是电动汽车续航里程短，使其一出生就遭遇了里程焦虑症(指驾驶电动汽车时因担心突然没电引起的精神痛苦和忧虑)。传统燃油汽车也有续航里程问题，只不过自前加油站星罗棋布，已使这个问题得以解决。而电动汽车相对传统汽车来说还是新生事物，在实际使用环节中的充电设施配套体系还不完善，充电难已经成为影响消费者购买电动汽车的最大障碍[1]。而已建成的部分充电设施却呈现出使用效率低甚至闲置的状况，形成了当前电动汽车发展的"充电怪圈"2]，即电动汽车充电难与充电设施闲置现象并存。因此，充电设施的选址布局成为当前亟待解决的问题。

换电站由于具有种种优势而备受企业和用户的喜爱，如换电站可用来做储能电站、削峰填谷、电网谐波、提高电网负荷率、可对电池进行慢充延长电池寿命、可用谷底电价进行充电降低成本等。目前，国内建换电站的企业主要是两家：一是北京的北汽，二是浙江的时空。北汽的换电模式是底盘换电，主要应用在出租车上；时空是侧方换电，主要支撑的也是出租车、物流车等工具用车。相关研究表明在电动汽车的体量和稳定且迫切的能量补给需求下，强大的服务能力很快能让换电站显现出比充电站更强的盈利能力[3]。然而，换电站投入成本高，建设难度大。为了避免电动汽车充电难与充电设施闲置并存的"充电怪圈”，研究如何在有限的资金和紧张的土地资源下，合理规划布局电动汽车换电站至关重要。

已有学者对充电设施的选址布局问题做了相关研究。Wang[4假设电动旅行车的行驶路径已知，研究电池换电站选址优化问题。MirHassani等人[5提出更为灵活的线性规划模型来解决能源补充设施选址问题。Jung等人[针对电动出租车充电站的布局问题提出双层仿真优化模型，该模型考虑行驶路线截流问题和排队延迟问题。Dong等人[7研究基于出行者活动的充电设施优化布局问题，并设计遗传算法求解模型。Zheng等人[8]研究续航里程约束下的电动汽车交通流量均衡和最优充电设施位置，提出双层模型，上层最优化充电设施位置，下层是流量均衡。Huang等人[9考虑交通网络上起讫点之间存在多条路径，提出基于流量的集覆盖模型。He 等人[10]对北京充电设施的选址布局问题做案例研究，其目标是将当地的供应限制和对充电设施的需求纳入三种选址模型，即集覆盖问题、最大覆盖问题和P-中位问题。杨珺等人[1提出了电动汽车物流配送系统的换电站选址与配送路径优化问题，建立了整数规划模型。陆坚毅等人[12]从充电站运营商的角度出发，在实时电价和每个充电任务时间必须连续的假设下，建立电动汽车充电成本最小模型。

从现有的研究文献来看，充电设施选址问题都是在经典选址模型上加入里程约束条件，且大多文献都假设用户的充电需求是确定已知的。然而，在实际问题中，先有充电设施，才会有用户来寻求充电服务，而用户需求受到众多不确定因素的影响，如电池技术的发展、交通路网状况、用户驾驶习惯、用户心理因素、电动汽车保有量等。因此，在充电设施选址问题中考虑需求的不确定性至关重要。目前，已经有学者将需求不确定性考虑进充电设施选址问题中。Yang等人[13]假设电动汽车用户的行驶路径已知，提出路径流量不确定的换电站选址库存问题。论文假设用户流量是随机变量，用概率约束作为约束条件。Mak等人[14]研究基于充电需求不确定的换电站选址鲁棒优化模型。Hosseini等人[15]研究基于不确定性的两阶段随机能源补充设施选址问题。

现有考虑不确定因素的充电设施选址问题，大多假设不确定参数概率分布已知，或者不确定事件可能发生的情景已知，目标是最优化期望，具有一定的局限性。本文假设不确定需求概率分布未知，用盒子（box）表示不确定参数的取值集合，利用基约束鲁棒优化方法研究基于需求不确定的换电站选址库存问题。首先介绍Bertsimas 和 $\mathrm { S i m } ^ { [ 1 6 ] }$ 提出的基约束鲁棒方法，该方法不仅保留了确定问题的线性规划框架，还能够通过改变不确定预算来调节解的鲁棒性。在需求确定的换电站选址模型基础上，假设需求取值于有界对称区间，提出基约束鲁棒选址模型，并将该模型转化为等价的线性规划。为了分析解的鲁棒水平对换电站选址成本的影响，本文最后应用Nguyen-Dupius 网络作为数值算例，说明解的鲁棒水平对电动汽车换电站选址成本的影响，分析解的鲁棒水平与选址成本之间的权衡关系，并对用户流量波动和续航里程两个参数作灵敏性分析。

# 1不确定需求下的换电站选址模型

# 1.1鲁棒优化

鲁棒优化经 Soyster、Ben-Tal、Nemirovski、El-Ghaoui[18\~20]等的发展，被研究人员广泛应用于各个领域[21,22]。本文采用文献[16]提出的基约束鲁棒方法。考虑如下线性规划问题：

$$
l \leq x \leq u
$$

其中： $x \in X \subseteq R ^ { n }$ 是决策向量， $b \in R ^ { m }$ 是右端项向量， $c \in R ^ { n }$ 是目标函数系数向量， $A \in { R } ^ { m \times n }$ 是约束矩阵，其元素是 $a _ { i j }$ 。对于矩阵 $A$ 的行 $i$ ，令 $J _ { _ i }$ 表示行 $i$ 中不确定参数的下标集合，a∈[aj-j,a+áj]，用áj表示不确定参数，a表示均值或常规值，áj表示最大绝对偏离值。令ni = $\eta _ { i j } = \frac { \tilde { a } _ { i j } - \overline { { a } } _ { i j } } { \hat { a } _ { i j } }$ a-a，ni∈[-1,1]且均匀对称。

记不确定预算为 $\Gamma _ { i } ^ { \phantom { } } \left( \begin{array} { l } { { i \in [ 1 , m ] } } \end{array} \right.$ )，其中 $\Gamma _ { i } \in [ 0 , | J _ { i } | ]$ ，Ji={jla>0}，则基约束鲁棒模型为

$$
\operatorname* { m i n } \ \sum _ { j = 1 } ^ { n } c _ { j } x _ { j }
$$

$$
\sum _ { j = 1 } ^ { n } \overline { { a } } _ { i j } x _ { j } + \operatorname* { m a x } \left\{ \sum _ { j \in J _ { i } } \hat { a } _ { i j } \left| x _ { j } \right| \eta _ { i j } : \sum _ { j \in J _ { i } } \eta _ { i j } \leq \Gamma _ { i } , \right\} \leq b _ { i } \quad \forall i
$$

$$
l _ { j } \le x _ { j } \le u _ { j } \quad \forall j
$$

引入对偶变量 $\alpha _ { i }$ 和 $\beta _ { i j }$ ，则上述问题等价于如下线性规划问题：

$$
\operatorname* { m i n } \ \sum _ { j = 1 } ^ { n } c _ { j } x _ { j }
$$

$$
\mathrm { s . t . } \sum _ { j = 1 } ^ { n } \overline { { { a } } } _ { i j } x _ { j } + \alpha _ { i } \Gamma _ { i } + \sum _ { j \in J _ { i } } \beta _ { i j } \leq b _ { i } \ , \forall i
$$

$$
\alpha _ { i } + \beta _ { i j } \ge \hat { a } _ { i j } y _ { j } \ , \forall i , \ \forall j \in J _ { i }
$$

$$
- y _ { j } \leq x _ { j } \leq y _ { j } , \forall j
$$

$$
l _ { j } \le x _ { j } \le u _ { j } ~ , ~ \forall j
$$

$$
\alpha _ { i } \ge 0 , \beta _ { i j } \ge 0 , y _ { j } \ge 0 , \forall i , \forall j \in J _ { i }
$$

# 1.2模型假设与问题描述

本文模型作如下假设：a）模型只考虑纯电动汽车的换电问题，而不考虑混合动力汽车既可以加油又可以充电的情况；

b）电动汽车用户日常行驶的路径已知，即从出发点到目的地的最短路径。c）电动汽车在起点的电量为续航里程 $R$ 的 $5 0 \%$ ，在终点的电量不低于续航里程 $R$ 的 $5 0 \% ^ { [ 2 5 ] }$ ，该假设能保证电动汽车往返一条路径。

如果用户能够驾驶电动汽车行驶完整条路径，则电量耗完时，必须有换电站为用户提供充电服务。如图1所示，设电动汽车的续航里程 $R = \ 1 0 0 \mathrm { k m }$ ，用户的行驶路径是$A \to B \to C \to D$ ，由于续航里程的限制，用户必须在 $B$ 换电池，也就是说只有在 $B$ 点建立换电站，电动汽车才能继续行驶。

![](images/f88aaa9d358f9118ef49fe6c76345530d75a29af05eac0b3d1e50fea42f85ace.jpg)  
图1一条路径 $q$

对于路径 $\boldsymbol { q }$ ，首先构造一个扩张网络，记为 $G = \left( \hat { N } ^ { q } , \hat { A } ^ { q } \right)$ 其中 $N ^ { q }$ 是路径 $q$ 节点集合， $\hat { N } ^ { q }$ 是扩张网络 $G$ 节点集合， $\hat { A } ^ { q }$ 是扩张网络 $G$ 边集合。 $\boldsymbol { d } _ { \boldsymbol { q } } ( { \boldsymbol { i } } , { \boldsymbol { j } } )$ 表示节点 $i$ 和 $j$ 之间的最短距离,$o r d _ { q } ( i )$ 表示节点 $i$ 在路径上的顺序标号，如图1路径 $q$ ：（20 $A \to B \to C \to D$ ， $o r d _ { q } ( B ) = 2$ 。通过以下四个步骤构造路径 $q$ 的扩张网络：

a）增加起始点 $s$ （ $A$ 之前）和目的点 $\mathbf { \Phi } _ { t }$ （ $D$ 之后)，并连接 $s \setminus A$ 和 $\mathbf { \nabla } _ { t } \cdot \mathbf { \nabla } _ { D }$ 。在图1中， $\hat { N } ^ { q } { = } \{ s , A , B , C , D , t \}$ ，将边 $\left( s , A \right)$ （20和 $( D , t )$ 加入到 $\hat { A } ^ { \textit { q } }$ 中；

b) $\forall i \in N ^ { q } : d _ { q } ( A , i ) \leq \frac { R } { 2 }  ( s , i ) \in \hat { A } ^ { q }$ ，则路径 $\boldsymbol { q }$ 增加边$^ { ( s , B ) }$ ;以 $\forall i \in N ^ { q } : d _ { q } ( i , D ) \leq \frac { R } { 2 }  ( i , t ) \in \hat { A } ^ { q }$ →(i,t)∈A，则路径q增加边$\scriptstyle ( C , t )$ ；

d)

$\forall i , j \in N ^ { q } : ( o r d _ { q } ( i ) < o r d _ { q } ( j ) ) \land ( d _ { q } ( i , D ) \leq R )  ( i , j ) \in \hat { A } ^ { q }$ ，则路径 $q$ 增加边 $( A , B ) \setminus \left( B , C \right) \setminus \left( B , D \right)$ 和 $( C , D )$ 。

通过以上四步，路径 $q$ 的扩张网络如图2所示。从起点 $s$ 到终点 $\mathbf { \Phi } _ { t }$ 的任意一条路径均对应一个可行的换电站点组合，如路径 $s  B  D  t$ 对应的有效换电站点组合为 $\{ B , D \}$ 。

![](images/2e689e9c4bc1f65b1599bf5201ce26d29480dc3c39b97ed84bc98504b06ce833.jpg)  
图2路径 $q$ 的扩张网络

本文研究的问题是：已知多个用户行驶路径的前提下，如何选择位置建立换电站以及确定每个站点的电池库存量，以此来满足用户的充电需求，即通过在换电站处换电池来行驶完路径。

先将文中用到的集合、参数和变量表示如下：

集合：

$\boldsymbol { \mathrm { \ell } }$ 一路径的集合， $q \in Q$ ；

$N$ 一路径包含的节点集合，即 $N = \cup _ { q \in Q } N ^ { q }$ ：

Qi—所有经过节点i的路径集合;

参数：

$c _ { i }$ 一在节点 $i$ 处建立换电站的固定成本， $i \in N$ ；$h _ { \scriptscriptstyle i }$ 一节点 $i$ 单位电池库存成本， $i \in N$ ；$f _ { q }$ 一路径 $q$ 上电动车用户的流量， $q \in Q$ ，

变量：[(1，在节点处建立换电站  
yi= $i \in N$ ：l0，否则  
$I _ { i }$ 一在节点 $i$ 处电池的库存量， $i \in N$ ；  
$\boldsymbol { x } _ { i j } ^ { q }$ 一路径 $q$ 的扩张网络 $\hat { A } ^ { q }$ 上边 $( i , j )$ 的流量， $i , j \in \hat { N } ^ { q }$ ：  
$z _ { i } ^ { q } = \left\{ { 1 , } \atop { 0 , } \right.$ 路径q上的车辆在节点处换电， $q \in Q \ , i \in N ^ { q } \ \circ$ 否则

需求确定的换电站选址库存模型为

$$
\operatorname* { m i n } _ { i \in N } \sum _ { i \in N } c _ { i } y _ { i } + \sum _ { i \in N } h _ { i } I _ { i }
$$

$$
. \mathrm { t . } \sum _ { \left\{ j : ( i , j ) \in \hat { A } ^ { q } \right\} } x _ { i j } ^ { q } - \sum _ { \left\{ j : ( j , i ) \in \hat { A } ^ { q } \right\} } x _ { j i } ^ { q } = \left\{ \begin{array} { l l } { 1 , } & { i = s } \\ { - 1 , } & { i = t } \\ { 0 , } & { i \neq s , t } \end{array} \right. , \forall q \in Q , \forall i \in \hat { N } ^ { q }
$$

$$
\sum _ { \left\{ j : ( j , i ) \in \hat { \cal A } ^ { q } \right\} } x _ { j i } ^ { q } \leq z _ { i } ^ { q } , \forall i \in { \cal N } , \forall q \in { \cal Q } _ { i }
$$

$$
z _ { i } ^ { q } \le y _ { i } , ~ \forall i \in N , \forall q \in Q _ { i }
$$

$$
\sum _ { q \in Q _ { i } } f _ { q } z _ { i } ^ { q } \leq I _ { i } , \ \forall i \in N
$$

$$
x _ { i j } ^ { q } \ge 0 , \forall ( i , j ) \in \hat { A } ^ { q }
$$

$$
I _ { i } \ge 0 , \forall i \in N
$$

$$
z _ { i } ^ { q } \in \{ 0 , 1 \} , \ \forall q \in Q , \forall i \in N ^ { q }
$$

$$
y _ { i } \in \{ 0 , 1 \} , \ \forall i \in N ^ { q }
$$

目标函数式(1)表示最小化总成本之和，包括换电站建站成本和电池库存成本。约束式(2)表示流量均衡，即每条路径上的电动汽车都能完成从起始点到目的地的行驶。约束式(3)表示路径q上电动车流经过N中的节点时，在该节点处换电。约束式(4)表示只有在节点处建立换电站，经过该节点的车辆才能在节点处换电。约束式(5)表示换电站点的电池库存不低于经过站点的车辆流量。约束式(6)\~(9)是对决策变量的限制。

# 1.3鲁棒选址模型

换电站的选址问题中存在很多不确定因素，如用户的需求，即本问题中路径上用户的车辆流量。而且决策者很难准确获得需求的概率分布信息，本节在上述确定模型的基础上，假设路径上用户的车辆流量是随机变量，建立换电站选址问题的鲁棒模型。

在换电站鲁棒选址问题中，设路径流量$\tilde { f } _ { q } \in \left[ \overline { { f } } _ { q } - \hat { f } _ { q } , \overline { { f } } _ { q } + \hat { f } _ { q } \right]$ ，其中 $\overline { { f } } _ { q }$ 表示路径流量的均值或常规值，$\hat { f } _ { \boldsymbol q }$ 表示路径流量的绝对偏离值。令 $\vert Q \vert = n ^ { \normalfont ( \forall i \in N ^ { \normalfont ( 1 ) } }$ ，即路径条数为 $n$ 条。在约束(5)中，对 $\forall i \in N$ ，引入不确定预算 $\Gamma _ { i }$ ，取值在区间 $[ 0 , n ]$ 上。参数 $\Gamma _ { i }$ 的作用是调节解的鲁棒水平，控制解的保守性。直观地讲，对于节点 $i$ ，不是所有的路径流量 $f _ { q }$ 都会变动，该鲁棒方法的目标是当最多有 $\lfloor \Gamma _ { i } \rfloor$ 条路径上的流量在其区间内发生变化，一条路径上的流量波动为(T,-[Γ;J)fg,其他路径上的流量都取均值时，鲁棒解仍是可行解，即满足约束条件式(5)。

需求不确定的换电站鲁棒选址模型为

$$
\operatorname* { m i n } _ { i \in N } \sum _ { i \in N } c _ { i } y _ { i } + \sum _ { i \in N } h _ { i } I _ { i }
$$

$$
\mathrm { . t . } \sum _ { q \in Q _ { i } } \overline { { f } } _ { q } z _ { i } ^ { q } + g _ { i } ( z , \Gamma _ { i } ) \leq I _ { i } \quad \forall i \in N
$$

其中：

$$
g _ { i } ( z , \Gamma _ { i } ) = \operatorname* { m a x } _ { \{ S \cup \{ t \} | S \subseteq Q _ { i } , | S | = \left[ \Gamma _ { i } \right] , t \in Q _ { i } \backslash S \} } \left\{ \sum _ { j \in S } \hat { f } _ { q } z _ { i } ^ { q } + \left( \Gamma _ { i } - \left\lfloor \Gamma _ { i } \right\rfloor \right) \hat { f } _ { t } z _ { i } ^ { t } \right\}
$$

（204号 $g _ { i } ( z , \Gamma _ { i } )$ 称为保护函数。当 $\Gamma _ { i }$ 取整数时，$g _ { i } ( z , \Gamma _ { i } ) = \operatorname* { m a x } _ { \{ S | S \subseteq Q _ { i } , | S | = \left\lfloor \Gamma _ { i } \right\rfloor \} } \left\{ \sum _ { j \in S } \hat { f } _ { q } z _ { i } ^ { q } \right\} \circ$

命题1鲁棒选址问题(RM)与混合整数规划问题 $( R M ^ { * } )$ 等价。

$$
\operatorname* { m i n } _ { i \in N } \sum _ { i \in N } c _ { i } y _ { i } + \sum _ { i \in N } h _ { i } I _ { i }
$$

$$
\sum _ { q \in Q _ { i } } \overline { { f } } _ { q } \ : z _ { i } ^ { q } + \alpha _ { i } \Gamma _ { i } + \sum _ { q \in Q _ { i } } \lambda _ { q } \leq I _ { i } \quad \forall i \in N
$$

$$
\alpha _ { i } + \lambda _ { q } \geq \hat { f } _ { q } z _ { i } ^ { q } \quad \forall i \in N , \forall q \in Q _ { i }
$$

$$
\alpha _ { i } \geq 0 \forall i \in N
$$

$$
\lambda _ { q } \geq 0 \forall i \in N , \forall q \in Q _ { i }
$$

证明引入辅助变量 $\lambda _ { _ q } \left( \forall j \in N \right)$ ，则函数 $g _ { i } ( z , \Gamma _ { i } )$ 可表示为如下线性规划问题：

(Pi) $g _ { i } ( x , \Gamma _ { i } ) = \operatorname* { m a x } \left\{ \sum _ { q \in Q _ { i } } \hat { f } _ { q } z _ { i } ^ { q } \lambda _ { q } : \sum _ { q \in Q _ { i } } \lambda _ { q } \leq \Gamma _ { i } , 0 \leq \lambda _ { q } \leq 1 , \forall q \in Q _ { i } \right\}$ 问题 $( P _ { i } )$ 的对偶问题为

$$
\operatorname* { m i n } \ \alpha _ { i } \Gamma _ { i } + \sum _ { q \in Q _ { i } } \lambda _ { q }
$$

$$
\begin{array} { r l r } { \mathrm { . t . } } & { { } \alpha _ { i } + \lambda _ { q } \geq \hat { f } _ { q } z _ { i } ^ { q } } & { \forall q \in Q _ { i } } \end{array}
$$

$$
\alpha _ { i } \geq 0
$$

$$
\lambda _ { q } \geq 0 \forall q \in Q _ { i }
$$

问题 $( P _ { i } )$ 可行且有界，由对偶定理可知，对偶问题 $( D P _ { i } )$ 可行且有界，则原问题与对偶问题的目标函数值一致。由此，约束(10)可转化为以下线性约束：

$$
\sum _ { q \in Q _ { i } } \overline { { f } } _ { q } z _ { i } ^ { q } + \alpha _ { i } \Gamma _ { i } + \sum _ { q \in Q _ { i } } \lambda _ { q } \leq I _ { i } \quad \forall i \in N
$$

$$
\alpha _ { i } + \lambda _ { q } \geq \hat { f } _ { q } z _ { i } ^ { q } \quad \forall i \in N , \forall q \in Q _ { i }
$$

$$
\alpha _ { i } \geq 0 \forall i \in N
$$

$$
\lambda _ { q } \geq 0 \forall i \in N , \forall q \in Q _ { i }
$$

鲁棒选址问题 $( R M )$ 与问题 $( R M ^ { * } )$ 等价，即可得命题1。证毕。

与确定模型 $( D M )$ 一样，鲁棒模型 $( R M ^ { * } )$ 也是线性规划。模型 $( R M )$ 可以通过现有的线性规划软件求解。由于最优解较容易求得，该方法在实际问题中更适用。

令 $\boldsymbol { P } _ { 0 } ^ { * }$ 和 $\boldsymbol { P } _ { 1 } ^ { * }$ 分别表示确定模型 $( D M )$ 和鲁棒模型 $( R M ^ { * } )$ 的最优解，显然：

$$
\alpha _ { i } \Gamma _ { i } + \sum _ { q \in Q _ { i } } \lambda _ { q } \geq 0 \forall i \in N , \forall q \in Q _ { i }
$$

即问题 $( R M ^ { * } )$ 的可行解也是问题 $( D M )$ 的可行解，所以，不难得出 $\boldsymbol { P } _ { 0 } ^ { * } \le \boldsymbol { P } _ { 1 } ^ { * }$ 。

令 $\boldsymbol { X } ^ { * }$ 表示问题 $( R M ^ { * } )$ 的最优解，基约束鲁棒方法保证了在约束式(5)中最多有 $\Gamma _ { i }$ 个参数 $f _ { q }$ 变动时， $\boldsymbol { X } ^ { * }$ 是可行解。若有多于 $\Gamma _ { i }$ 个参数 $f _ { q }$ 变动，此时可证明， $X ^ { * }$ 以一定的概率是可行解。对于约束式(5)，鲁棒解 $\boldsymbol { X } ^ { * }$ 是可行解的概率可计算如下：

$$
\begin{array} { c } { { \displaystyle P \Bigg ( \sum _ { q \in Q _ { i } } \tilde { f } _ { q } z _ { i } ^ { q } \geq I _ { i } \Bigg ) \leq B \big ( n , \Gamma _ { i } \big ) = } } \\ { { \displaystyle \frac { 1 } { 2 ^ { n } } \Bigg \{ ( 1 - \mu ) \sum _ { l = \lfloor \nu \rfloor } ^ { n } \binom { n } { l } + \mu \sum _ { l = \lfloor \nu \rfloor + 1 } ^ { n } \binom { n } { l } \Bigg \} } } \end{array}
$$

由于参数 $\Gamma _ { i }$ 能够控制解的保守性，参数 $\Gamma _ { i }$ 也称为保护水平，决策者通过调节参数 $\Gamma _ { i }$ 来控制鲁棒解违背约束条件的概率，从而控制解的鲁棒性。反之，给定解的鲁棒水平，通过式(16)可以计算参数 $\Gamma _ { i }$ 的取值。

事实上，可以利用二分法来计算参数 $\Gamma _ { i }$ 的取值。令 $S L ^ { \mathrm { { ; } } }$ \*表示鲁棒水平， $n _ { \mathrm { m a x } }$ 表示最大迭代次数， $\theta$ 表示误差容忍度。具体步骤如下所示：

a)令 $l _ { 0 } = 0 \quad , \qquad h _ { 0 } = n \quad , \qquad k = 0 \quad , \qquad \Gamma _ { i }  \frac { l + h } { 2 } \quad ,$ $S L _ { k } = 1 - \Biggl [ ( 1 - \mu ) C ( n , \lfloor \nu \rfloor ) + \sum _ { l = \lfloor \nu \rfloor + 1 } ^ { n } C ( n , l ) \Biggr ] , k \gets k + 1$ ，转到c)；

b) $M i d = \frac { l _ { k } + h _ { k } } { 2 } \qquad , \qquad \Gamma _ { i } \gets M i d$ $S L _ { k } = 1 - \Biggl [ ( 1 - \mu ) C \bigl ( n , \lfloor \nu \rfloor \bigr ) + \sum _ { l = \lfloor \nu \rfloor + 1 } ^ { n } C \bigl ( n , l \bigr ) \Biggr ] , k \gets k + 1  ;$ （20c)若 $S L _ { k } < S L ^ { * } \ , l _ { k }  M i d \ , h _ { k }  h _ { k - 1 }$ ；若 $S L _ { k } > S L ^ { * }$ ，$l _ { k } \gets l _ { k - 1 }$ ， $h _ { k } \gets M i d$ ；否则 $\Gamma _ { t } ^ { * } \gets \Gamma _ { t }$ ，停止；d)若 $\left| \frac { S L _ { k } - S L ^ { * } } { S L ^ { * } } \right| \leq \theta$ 或 $k \geq n _ { \operatorname* { m a x } }$ ， $\Gamma _ { t } ^ { * } \gets \Gamma _ { t }$ ，停止；否则，转到步骤b)。

应用基约束鲁棒方法，决策者可以通过选择恰当的参数 $\Gamma _ { i }$ 控制鲁棒解的保守程度。更重要的是，即使有多于 $\Gamma _ { i }$ 个参数 $f _ { q }$ 变动时，鲁棒解仍然以一定的概率可行。此外，鲁棒模型保留了原模型的线性特点，容易求解。对于不确定优化问题，鲁棒解能够满足约束条件的概率称为解的鲁棒水平。

# 2 数值算例与分析

# 2.1算例设计

本节利用Nguyen和Dupius[23]网络图作为算例，如图3所示，Nguyen-Dupius网络图被已被众多学者用来研究网络设施选址与交通问题。Kuby和 $\mathrm { L i m } ^ { [ 2 4 ] }$ 指出当节点之间的距离较大时，仅在节点处建立换电站并不能满足用户的充电需求，这时需要在网络的边上增加备选换电站点。Kuby和 $\mathrm { L i m } ^ { [ 2 5 ] }$ 提出三种在网络边上增加备选点的方法。本文采用如下方法：令 $t ( i , j )$ （204号表示网络中边 $( i , j )$ 上增加的节点，新增的备选点均匀分布在边上：

$$
t ( i , j ) = \{ \lceil \frac { l e n g t h ( i , j ) } { r } \rceil - 1 , l e n g t h ( i , j ) > r
$$

其中: $l e n g t h ( i , j )$ 表示边 $( i , j )$ 的长度。该方法避免了边长大于 $\boldsymbol { r }$ 的边上没有备选换电站节点的情况。

模型 $( R M ^ { * } )$ 由 AIMMS3.9生成、由CPLEX12.6求解，在CPU为IntelCorei7-4710HQ2.50 GHz，内存为 $8 . 0 0 \mathrm { G B }$ 的计算机上进行实验。图3表示13个节点的网络，每个节点既是起始点(rigins)，,也是终止点(destinations)，一共有 $\frac { 1 3 \times ( 1 3 - 1 ) } { 2 } = 7 8$ 个OD 对，OD对之间的最短路即为一条路径。OD对之间的流量(每条路径的流量)由重力模型求得，即：

$$
f _ { q } = \frac { w _ { i } w _ { j } } { d _ { i j } } { \times 1 . 5 }
$$

其中: $w _ { i } \setminus \boldsymbol { w } _ { j }$ 分别表示节点 $i$ 和 $j$ 的权重， $d _ { i j }$ 表示 $i \setminus j$ 之间的最短距离。

![](images/4a3e835d0e6a332b9523fb29b82728b2c9e99e02929fb794ddf47a030f8b50ac.jpg)  
图3Nguyen-Dupius 网络

# 2.2 数值结果与分析

假设在每个点(原有节点和边上新增节点)换电站固定建站成本和电池库存成本相同。路径流量的最大偏离值与路径流量成正比，令 $\hat { f } _ { q } = 0 . 2 \times \overline { { f } } _ { q }$ 。首先，在区间[1,50]上随机生成 13个节点权重，在鲁棒水平 $\Gamma$ 不同取值下，求解模型 $( R M ^ { * } )$ ，最优解如表1所示。然后，在区间[1,100]上随机生成13个节点权重，求解模型 $( R M ^ { * } )$ ，最优解如表2所示。从表1和表2可以看出当电动汽车的续航里程和模型的鲁棒保护水平取值不同时，利用CPLEX求解模型 $( R M ^ { * } )$ 耗时不超过30秒，可见利用CPLEX求解模型 $( R M ^ { * } )$ 十分有效。此外，当续航里程相同时，保护水平$\Gamma$ 越低，选址成本越低；保护水平 $\Gamma$ 越高，选址成本越高。

表1节点权重在区间[1,50]上的最优解  

<html><body><table><tr><td>续航里程R</td><td>保护水平</td><td>总成本</td><td>计算时间(秒)</td></tr><tr><td rowspan="4">50</td><td>1</td><td>19863.6</td><td>11.89</td></tr><tr><td>2</td><td>20156.5</td><td>14.25</td></tr><tr><td>3</td><td>23549.7</td><td>15.85</td></tr><tr><td>4</td><td>25364.1</td><td>19.44</td></tr><tr><td rowspan="4">100</td><td>1</td><td>12036.8</td><td>10.58</td></tr><tr><td>2</td><td>11548.5</td><td>12.55</td></tr><tr><td>3</td><td>13649.5</td><td>19.65</td></tr><tr><td>4</td><td>14089.6</td><td>23.56</td></tr><tr><td rowspan="4">150</td><td>1</td><td>8953.6</td><td>15.75</td></tr><tr><td>2</td><td>9015.8</td><td>15.64</td></tr><tr><td>3</td><td>9987.3</td><td>18.62</td></tr><tr><td>4</td><td>10034.9</td><td>21.77</td></tr><tr><td rowspan="4">200</td><td>1</td><td>7542.5</td><td>16.89</td></tr><tr><td>2</td><td>8012.6</td><td>19.23</td></tr><tr><td>3</td><td>8923.4</td><td>20.49</td></tr><tr><td>4</td><td>9232.3</td><td>21.67</td></tr><tr><td rowspan="4">250</td><td>1</td><td>6534.5</td><td>13.54</td></tr><tr><td>2</td><td>6926.4</td><td>20.49</td></tr><tr><td>3</td><td>7136.8</td><td>24.09</td></tr><tr><td>4</td><td>7582.6</td><td>18.91</td></tr></table></body></html>

<html><body><table><tr><td></td><td>2</td><td>4956.2</td><td>20.54</td></tr><tr><td>300</td><td>3</td><td>5189.4</td><td>23.09</td></tr><tr><td></td><td>4</td><td>5536.9</td><td>24.89</td></tr><tr><td colspan="4">表2 节点权重在区间[1,100]上的最优解</td></tr><tr><td>续航里程R</td><td>保护水平</td><td>总成本</td><td>计算时间(秒)</td></tr><tr><td></td><td>1</td><td>30782.1</td><td>15.89</td></tr><tr><td></td><td>2</td><td>31898.2</td><td>16.45</td></tr><tr><td>50</td><td>3</td><td>32694.2</td><td>18.65</td></tr><tr><td></td><td>4</td><td>34124.8</td><td>19.52</td></tr><tr><td></td><td>1</td><td>28603.5</td><td>12.98</td></tr><tr><td></td><td>2</td><td>30493.5</td><td>18.22</td></tr><tr><td>100</td><td>3</td><td>32841.7</td><td>19.65</td></tr><tr><td></td><td>4</td><td>34510.5</td><td>23.56</td></tr><tr><td></td><td>1</td><td>24369.4</td><td>15.75</td></tr><tr><td></td><td>2</td><td>25393.5</td><td>18.65</td></tr><tr><td>150</td><td>3</td><td>27263.7</td><td>20.47</td></tr><tr><td></td><td>4</td><td>28065.1</td><td>22.56</td></tr><tr><td></td><td>1</td><td></td><td>18.92</td></tr><tr><td></td><td></td><td>19863.6</td><td></td></tr><tr><td>200</td><td>2</td><td>20156.5</td><td>22.58</td></tr><tr><td></td><td>3 4</td><td>23549.7</td><td>24.92</td></tr><tr><td></td><td>1</td><td>25364.1 12036.8</td><td>28.47 19.51</td></tr><tr><td></td><td></td><td></td><td>20.49</td></tr><tr><td>250</td><td>2 3</td><td>11548.5 13649.5</td><td>25.19</td></tr><tr><td></td><td>4</td><td>14089.6</td><td>25.81</td></tr><tr><td></td><td>1</td><td>9534.1</td><td>15.86</td></tr><tr><td></td><td>2</td><td>9697.4</td><td>24.61</td></tr><tr><td>300</td><td>3</td><td>9862.9</td><td>28.43</td></tr><tr><td></td><td>4</td><td>10664.8</td><td>29.57</td></tr></table></body></html>

为了说明解的鲁棒水平对换电站选址成本的影响，在区间[1,100]上随机 13 个节点权重，令 $\hat { f } _ { q } = 0 . 1 8 \times \overline { { f } } _ { q }$ ， $n = \left| Q \right| = 7 8$ 根据公式(16)计算出不同 $\Gamma$ 值下的鲁棒水平。鲁棒水平 $\Gamma$ 取不同值，求解模型 $( R M ^ { * } )$ ，结果如表3所示。表3最后一列表示选址成本的变动，也就是保护水平取不同值时，鲁棒模型最优成本相对于确定模型最优成本的增加。保护水平与最优总成本之间的关系如图4所示。由图4可以看出，当 ${ \Gamma } _ { i } = 0$ 时，即所有路径上的用户流量都取均值时，总成本为19253.5，此时解的鲁棒水平为 $4 5 . 3 \%$ ，即换电站的电池库存能够满足电动汽车用户需求的概率是 $4 5 . 3 \%$ 。随着保护水平的增加，总成本也增加。当解的鲁棒水平较低时，曲线较平缓，表明适当增加选址成本，鲁棒水平就会有较大的提升。当鲁棒水平逐渐增加时，曲线变得陡峭，表明通过增加选址成本的方式较难提高鲁棒水平。

显然，解的鲁棒性是以提高选址成本为代价的，成本的增加量与是否值得是决策者要考虑的问题。图5表示选址成本的增加与解的鲁棒水平之间的关系。从图5可以看出，换电站选址成本的变化随着鲁棒水平的提高变化越来越剧烈。决策者可以根据选址成本的增加来决定解的鲁棒水平，或者根据需要达到的鲁棒水平来计算成本的增加量。

表3解的鲁棒性与选址成本变动  

<html><body><table><tr><td>保护水平</td><td>解的鲁棒水平(%)</td><td>总成本</td><td>成本变动(%)</td></tr><tr><td>0</td><td>45.32</td><td>19253.5</td><td>0.00</td></tr><tr><td>1</td><td>49.84</td><td>19920.4</td><td>0.03</td></tr><tr><td>2</td><td>54.35</td><td>20094.5</td><td>0.04</td></tr><tr><td>3</td><td>58.76</td><td>20699.6</td><td>0.08</td></tr><tr><td>4</td><td>63.16</td><td>21156.5</td><td>0.10</td></tr><tr><td>5</td><td>67.24</td><td>22036.9</td><td>0.14</td></tr><tr><td>6</td><td>71.33</td><td>22986.5</td><td>0.19</td></tr><tr><td>7</td><td>74.92</td><td>23936.4</td><td>0.24</td></tr><tr><td>8</td><td>78.52</td><td>24936.2</td><td>0.30</td></tr><tr><td>9</td><td>81.53</td><td>25698.1</td><td>0.33</td></tr><tr><td>10</td><td>84.54</td><td>26936.4</td><td>0.40</td></tr><tr><td>11</td><td>86.93</td><td>27956.3</td><td>0.45</td></tr><tr><td>12</td><td>89.33</td><td>29068.3</td><td>0.51</td></tr><tr><td>13</td><td>91.14</td><td>30934.5</td><td>0.61</td></tr><tr><td>14</td><td>92.95</td><td>31865.4</td><td>0.66</td></tr><tr><td>15</td><td>94.25</td><td>33053.3</td><td>0.72</td></tr><tr><td>16</td><td>95.55</td><td>35000.3</td><td>0.82</td></tr><tr><td>17</td><td>96.43</td><td>36009.5</td><td>0.87</td></tr><tr><td>18</td><td>97.31</td><td>38323.3</td><td>0.99</td></tr><tr><td>19</td><td>97.88</td><td>39523.5</td><td>1.05</td></tr><tr><td>20</td><td>98.46</td><td>40690.4</td><td>1.11</td></tr><tr><td>21</td><td>98.80</td><td>43909.3</td><td>1.28</td></tr><tr><td>22</td><td>99.15</td><td>45000.3</td><td>1.34</td></tr></table></body></html>

![](images/e15b6bd7bfc95b24258979a8e7d990b9b865e1003db7287eea5e2b6df62d8127.jpg)  
图4解的鲁棒水平与换电站选址总成本

![](images/db3f357dde4409050fe7fe707b0db3df73e541083ceebb060a65e166a2da3c5a.jpg)  
图5换电站选址成本增加与解的鲁棒水平

# 2.3 灵敏性分析

假设 ${ \hat { f } } _ { q } = \sigma { \overline { { f } } } _ { q }$ ，对路径用户流量波动，即 $\sigma$ 的值，作灵敏性分析，得出在不同鲁棒水平下，换电站选址总成本随流量波动的变化。当 $\sigma = 0 . 1 3$ 、0.18和0.23时，解的鲁棒水平与选址总成本之间的变化关系如图6所示，三条曲线的增长趋势基本相同：解的鲁棒水平较低时，曲线较平缓，表明适当增加选址成本，可以较大程度地提高鲁棒水平。随着鲁棒水平的提高，曲线较陡峭，表明即使提高总成本，也很难提高解的鲁棒水平。此外，同一鲁棒水平下，用户流量波动越大，选址总成本越高。随着鲁棒水平的提高，三个成本之间的差距逐渐变大，这表明随着鲁棒水平的提高，换电站选址总成本对路径流量波动越来越敏感。

对电动汽车的续航里程，即 $R$ 的值，作灵敏性分析。图7表示电池的续航里程对换电站建站成本、电池库存成本和选址总成本的影响。当续航里程从250增加到500时，建站成本从8803降低到 $4 6 0 1 ( 4 4 . 7 \%$ )，电池库存成本从29632降低到10032（ $6 6 . 1 \%$ )，总成本从38435降低到14633（ $6 1 . 9 \%$ )。灵敏性分析的结果表明续航里程的改变对换电站选址策略影响较大，且电池库存成本和选址总成本随续航里程变化较大。

![](images/2f54c5b9fa67d23ef94546b95aee7aac13ea5dddb24637eba044b1c6e00c3c22.jpg)  
图6用户流量波动的灵敏性分析

![](images/c3aa78ce9bf240274721fc80c75ac45953326e3ee56d579860321a15a8550092.jpg)  
图7续航里程的灵敏性分析

# 3 结束语

充电设施的合理布局是电动汽车发展的关键，换电站由于具有削峰填谷、电网谐波、提高电网负荷率、可对电池进行慢充延长电池寿命等优点，备受政府和企业的推崇。用户的充电需求是换电站选址模型的重要输入参数，而用户的需求受到电动汽车的保有量、技术的发展、交通网络的状况等众多因素的影响，因而是不确定的。本文假设不确定需求的概率分布未知，利用基约束鲁棒优化方法，研究基于需求不确定换电站选址库存鲁棒优化模型。该方法不仅保留了确定问题的线性规划框架，还能够通过改变不确定预算来调节解的鲁棒水平。在换电站选址确定模型基础上，假设需求取值于有界对称区间上，提出基约束鲁棒选址模型，并将该模型化为等价的线性规划。为了分析解的鲁棒水平对总选址成本的影响，本文最后应用Nguyen-Dupius网络作为数值算例，算例分析结果说明在不同的鲁棒水平，换电站选址总成本不同，当解的鲁棒水平较低时，适当增加成本，可以较大程度地提高解的鲁棒水平。此外，还对影响模型的重要参数作了灵敏性分析。分析结果表明，随着鲁棒水平的提高，换电站选址总成本对路径流量的波动越来越敏感，续航里程的改变对换电站选址策略影响较大，且电池库存成本和选址总成本随续航里程变化较大。本文的研究以为政府部门和电动汽车充电服务商决策电动汽车充电设施的位置和数量提供科学依据。

# 参考文献：

[1]张勇，蒲勇健，史乐峰．电动汽车充电基础设施建设与政府策略分析 [J].中国软科学,2014,6:167-181.(Zhang Yong,Pu Yongjian,Shi Lefeng Analysis on electric vehicle charging infrastructure and government strategy [J].China Soft Science,2014,6: 167-181.)   
[2]龙强．电动汽车发展陷入充电怪圈：闲置和充电难并存[J].能源研究 与利用，2013 (3):16-17.(Long Qiang.The development of electric vehicles is in a vicious cycle of charging: Idle and charging are difficult to coexist [J].Energy Research& Utilization,2013(3):16-17.)   
[3]Zheng Yu,Dong Zhaoyang，Xu Yan，et al.Electric vehicle battery charging//swap stations in distribution systems: comparison study and optimal planning [J].IEEE Trans on Power Systems,2O14,29(1):

221-229.

[4] Wang Yingwei. Locating battry exchange stations to serve tourism transport:a note [J].Transportation Research Part D:Transport and Environment,2008,13 (3): 193-197.   
[5]MirHassani S A,Ebrazi R.A flexible reformulation of the refueling station location problem [J]. Transportation Science,2013,47(4): 617-628.   
[6]Jung J,Chow JY J, Jayakrishnan R,et al. Stochastic dynamic itinerary interception refueling location problem with queue delay for electric taxi charging stations [J]. Transportation Research Part C,2014,40: 123-142.   
[7]Dong Jing，Liu Changzheng，Lin Zhenhong.Charging infrastructure planning for promoting battery electric vehicles: An activity-based approach using multiday travel data [J]. Transportation Research Part C, 2014, 38: 44-55.   
[8] Zheng Hong,He Xiaozheng,Li Yongfu,et al. Trafic equilibrium and charging facility locations for electric vehicles [J].Networks and Spatial Economics,2016,9,1-23.   
[9]Huang Yongxi,Li Shengyin,Qian Zhensean.Optimal deployment of alternative refueling stations on transportation networks considering deviation paths[J]. Networksand Spatial Economics，2015，15(1): 183-204.   
[10] He Sylvia,Kuo Yonghong,Wu Dan. Incorporating institutional and spatial factors in the selection of the optimal locations of public electric vehicle charging facilities:a case study of Beijing,China [J]. Transportation Research Part C,2016,67: 131-148.   
[11]杨珺，冯鹏祥，孙昊，等．电动汽车物流配送系统的换电站选址与路径 优化问题研究[J].中国管理科学,2016,23(9):88-96.(Yang Jun,Feng Pengxiang,Sun Hao. Batery exchange station location and vehicle routing problem in electric vehicle distribution system [J].Chinese Journal of Management Science,2016,23 (9): 88-96.)   
[12]陆坚毅，杨超，肖来元，等．基于单亲遗传算法混合动态规划的电动汽 车充电调度优化策略[J].计算机工程与科学，2015，37(5):967-973. (Lu Jianyi,Yang Chao,Xiao Laiyuan. An optimal charging schedule strategy of electric vehicles based on partheno-genetic algorithm and dynamic programming [J]. Computer Engineering & Science,2O15,37 (5): 967-973.)   
[13] Yang Jun,Sun Hao.A hybrid genetic algorithm for battery swap stations

location and inventory problem [J].International Journal of Shipping and Transport Logistics,2013,7(5):1-10.

[14]Mak Hoyin,Rong Ying,Shen Zuojun.Infrastructure planning for electric

vehicles with batery swapping [J]. Management Science,2013,59 (7): 1557-1575.   
[15]Hosseini M,MirHassani S A.Refueling-station location problem under uncertainty [J]. Transportation Research Part E,2O15,84:101-116.   
[16] Bertsimas D, Sim M. The price of robustness [J]. Operations Research, 2004, 52 (1): 35-53.   
[17] Lim S,Kuby M.Heuristic algorithms for siting alternative-fuel stations using the flow-refueling location model [J]. European Journal of Operational Research,2010,204 (1): 51-61.   
[18] Soyster A L. Convex programming with set-inclusive constraints and applications to inexact linear programming [J]. Operations Research,1973, 21 (5): 1154-1157.   
[19] Ben-Tal A，Nemirovski A.Robust optimization methodology and applications [J].Mathematical Programming Series B，2002,92 (3): 453-480.   
[20] El-Ghaoui L,Oustry F,Lebret H.Robust solutions to uncertain semidefinite programs [J]. SIAM Journal on Optimization,1998,9 (1): 33-52.   
[21]彭春，李金林，冉伦 等．基于两个不确定参数乘积的鲁棒设施选址模 型[J]．系统工程理论与实践,2017,37(12):3170-3181.(Peng Chun,Li Jinlin，Ran Lun，et al.Robust facility location model with two multiplicative uncertainties [J]. Systems Engineering-Theory& Practice,2017,37(12): 3170-3181.)   
[22]刘慧，杨超，宋广华.需求不确定的设施选址与多阶段生产鲁棒模型研 究[J].计算机应用研究，2018,35(3):760-764.(Liu Hui,Yang Chao, Song Guanghua,Facility Location and Multi-Period Production Problem Considering Robustness[J],Application Research of Computers,2018,35 (3): 760-764.)   
[23] Nguyen S,Dupius C.An efficient method for computing traffic equilibria in networks with asymmetric transportation costs [J]. Transportation Science,1984: 18:185-202.   
[24] Lim S,Kuby M.Heuristic algorithms for siting alternative-fuel stations using the flow-refueling location model [J]. European Journal of Operational Research,2010,204 (1): 51-61   
[25] Kuby M,Lim S.The flow-refueling location problem for alternative-fuel vehicles [J].Socio-Economic Planning Sciences,2005,39 (2):125-145   
[26] Kuby M,Lim S.Location ofalternative-fuel stationsusing the flow-refueling location model and dispersion of candidate sites on arcs [J]. Networks and Spatial Economic,2007,7 (2): 129-152.