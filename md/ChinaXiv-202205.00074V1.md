# 基于模仿学习的机场停机位再分配决策算法

邢志伟¹，张前前‘，罗谦²，陈肇欣²

(1．中国民航大学 电子信息与自动化学院，天津 300300;2.中国民用航空局第二研究所 工程技术研究中心，成都610041)

摘要：针对机位再分配算法结果难以满足不同操作人员操作习惯的问题，提出一种符合实际业务人员操作习惯的机位再分配推荐算法。首先以航班特征属性和停机位的资源占用状态构建决策环境空间模型，将人工操作数据转换为多通道时空矩阵，再以卷积神经网络构建的生成对抗网络(generative adversarial network，GAN)拟合其序贯决策操作策略。仿真结果表明，可靠度在 $90 \%$ 以上的调整动作占比最高达到 $84 . 4 \%$ 。经过在3个数据集上的测试，模型对不同来源的操作数据具有较好的区分能力。对比不同扰动下的动态调整结果，算法能够得到航班-机位属性特征与原有人工操作属性特征接近的调整方案。

关键词：航空运输；停机位分配；模仿学习；马尔可夫决策过程；生成对抗网络中图分类号：V351 doi:10.19734/j.issn.1001-3695.2022.02.0071

Decision-making algorithm for airport gate reassignment based on imitation learning

Xing Zhiwei1, Zhang Qianqian1,Luo Qian²†, Chen Zhaoxin² (1.SchoolofEectronicIformation&utomation,CivilAviation Unversityofha,njin33,China;2Enieing TechnologyResearch Center,The SecondResearch InstituteofCivilAviationAdministrationofChina,Chengd 610041, China)

Abstract:Inorder to solve the problem that theresultsof the gate reassignmentalgorithmcan't met habitsof different operators,thispaperproposedamethodthataccordswiththeactualoperators'operatinghabits.Firstly,this paper established thespatial modelofdecision-making environmentbyusing flights characteristicsand occupancyofgate resources.The model transforms manual operating data into a multi-channel time-space matrix.Then,makeuseof CNN-based generative adversarial network to match the order decision-making operation strategy.The simulation results show that actions with reliability scores of more than $90 \%$ account for up to $84 . 4 \%$ .The model has a good ability to distinguish the operation data from 3 diffrent operators. Compared with dynamic adjustment result under perturbance,this algorithm can obtain an adjustment scheme whose flight-gate atribute characteristics are closer to the original manual operation.

Key words:air transportation;airportgate assignment; imitationlearing; Markovdecisionproce;generative adversarial network

# 0 引言

停机位分配算法是辅助机场调度人员完成航班停机位指派的重要技术手段，该问题作为机场运行控制领域重要的研究方向持续受到关注[1]。

现有的停机位预分配算法研究大多采用动态规划的思路进行算法建模[2]，停机位再分配算法通常以最小化与原计划之间的变化为优化目标[3-9]。Deng[3]通过遗传-蚁群混合算法(genetic algorithm and ant colony optimization,GA-ACO)最小化乘客、机场和航司的经济损失。Zhang[4构建机位再分配为网络流模型并通过变滚动层位算法求解。姜雨[8等在对航班延误后实时调度问题的研究中考虑到延误的等级划分，在不同的延误严重程度下，针对不同的优化目标分别优化，使用非支配排序遗传算法求解，得到差异化多目标机位分配模型。Maharjan[9]等提出了一种基于传统确定性模型的机位动态分配模型，建立了最小化旅客的传递距离的二次整数规划模型。

根据上述的研究，既有的机位分配算法会综合考虑航班靠桥率、鲁棒性等若干复杂多样的优化目标，算法模型构建过程中往往通过人为权重参数分配或优先级设定方式平衡各优化目标之间的关系以进行动态规划求解。然而实际运用中对于大量优化目标或约束条件，业务人员很难主观精确量化符合机场实际运行目标的算法参数配置，导致算法计算得到分配结果后仍然需要人工进行核查及再分配调整。

模仿学习(ImitationLearning，IL)，也称为示例学习，通过相对简单的方法模仿某种行为策略作出反映。它从数据集中提取有用的知识，在类似于演示的环境中重现其行为策略以实现与之类似的决策方式。IL的存在有助于自主控制系统的研究和人工智能策略模型的设计，因为此类算法在现实场景中表现出良好的前景和策略训练的效率。在连续控制领域，模仿学习可应用于自主车辆操纵，以在动态环境中再现适当的驾驶行为[10,I1]、机器人控制[12\~14]等。在离散控制领域，模仿学习在导航任务[15\~17]等领域作出了贡献。一般而言，算法采用的演示数据是从人类专家或人工代理与环境

收稿日期：2022-02-13；修回日期：2022-04-02基金项目：国家重点研发计划资助项目(2018YFB1601200；四川省青年科技创新研究团队专项计划资助项目(2019JDTD001)；四川省科技计划资助项目(2021003)；成都市重点研发支撑计划资助项目(2019-YF08-00265-GX)

作者简介：邢志伟(1970-)，男，辽宁沈阳人，教授，硕导，博士，主要研究方向为民航装备与系统、民航智能规划与调度、机场运行控制与信息；张前前(1997-)，男，湖南衡阳人，硕士研究生，主要研究方向为机场运行控制与信息；罗谦(1975-)，男(通信作者)，四川宜宾人，研究员，硕导，博士，主要研究方向为机场运营管理、数据挖掘(cacsr_luoqian@163.com)；陈肇欣(198-)，男，江苏南京人，中级工程师，博士，主要研究方向为机场运营管理、数据挖掘.

交互中收集获得。

IL 按惯例分为行为克隆(BehaviouralCloning，BC)、逆向强化学习(InverseReinforcementLearning,IRL)和对抗结构模仿学习(Adversarial Structured Imitation Learning,ASIL)。BC 和IRL方法使用不同的方法来产生专家行为。一般而言，通过IRL 构建得到了奖励(成本)函数后，需要进一步采用该奖励函数代入RL中得到被学习的专家策略，这种间接的方式在较小的空间中求解是可行的，而当环境空间进一步扩大时，将会面临求解成本高昂的问题。而行为克隆算法直接通过专家轨迹数据得到相应的策略，但该算法会在专家轨迹未出现的状态上产生偏移问题，所以需要大量的训练数据，不适合数据获取成本较高的应用场景。ASIL最初产生于由Ho 和 Ermon 提出的GAIL 算法[18]，尽管 ASIL与IRL有着密切的联系，但大多数对抗性结构IL都不能恢复奖励函数。BC 通常利用在环境中没有交互作用的专家之间的交互作用，故BC的计算成本是最低的；IRL方法通常在其算法内环中与环境有着较多的交互作用，对系统动态的评估使IRL计算量大；ASIL方法在迭代更新策略参数和鉴别器参数时，还涉及与环境的频繁交互。

人工再分配调整本质是一种决策策略，与动态规划算法模型对某些航班的决策存在偏差，这种偏差产生于模型参数的主观设置。为了消除这种偏差并更准确地刻画人工的决策过程，将人工再分配调整建模为序贯决策问题，提出了一种基于特征嵌入的生成对抗模仿学习方法(feature embedding-generative adversarial imitation learning，FE-GAIL)的停机位再分配决策模型，通过直接学习人工操作数据，解决静态参数下的人工主观参数配置不准确的问题。

# 1 航班停机位再分配模型设计

# 1.1问题描述

机场通常提前一天获取次日航班时刻表，经过机位分配算法计算得到的预分配计划以甘特图(图1)的形式呈现。在当天实际运行时，航班时刻变化可能导致机位使用冲突，算法会在该计划上进行再分配以消解冲突。

航班的机位调整在同一场景下往往存在多种可行解。如图1所示，当103机位上的航班5发生延误时，将与航班6产生冲突，需要将航班6调整至其他机位。图中 $\textcircled{1}$ 、 $\textcircled{2}$ 和 $\textcircled{3}$ 分别代表了3种可行的调整方案，传统多目标优化的算法得到最优解 $\textcircled{1}$ 。

经过对机场操作人员的调研，不同的操作人员对传统算法中配置参数方案的认知是不一致的，这导致实际业务中难以给定一个具有广泛适用性的参数配置，算法输出的结果中不同的操作人员可能选择不同的推荐方案，甚至其选择并非算法输出的最优解。

例如，设103机位为远机位，101机位为廊桥，操作人员1倾向于调整更少航班数量而选择了方案 $\textcircled{2}$ ，而操作人员2 倾向于更高廊桥靠桥率选择了可行解 $\textcircled{3}$ 。

这种算法计算结果和员工实际行为上的偏差来自于个人主观经验与参数主观设置的偏差，传统的多目标优化算法难以通过参数优化设置方式消除这种偏差。针对上述问题，通过在多目标优化过程中引入机器学习算法，实现主观设置参数的偏差纠正。再分配过程中，一个航班机位的人工调整可能需要多个航班机位的连锁调整以得到可行解，因此停机位再分配可以视为一个序贯决策过程，针对序贯决策的策略学习问题通常采用模仿学习算法[19]。其中生成对抗模仿学习(Generative AdversarialImitationLearning，GAIL)算法主要通过示例决策轨迹数据学习其中的决策策略，得到近似于示例的决策策略，在自动驾驶等序贯决策场景具有较好的状态泛化效果[20]。综上，基于GAIL算法的思想，将航班与机位的状态特征信息进行特征值嵌入操作(feature embedding，FE),通过学习人工操作轨迹数据来拟合人工停机位再分配的决策过程，以消除主观经验与参数主观设置的偏差。

![](images/321c6edec9651b7d9bbe6c9c2b8b3da04040c91ef22051fbb854dbb610ca7b49.jpg)  
Fig.1Process of gate reassignment

图2给出了基于FE-GAIL的停机位分配策略学习算法流程。首先通过航班计划表和停机位属性构建决策环境空间，之后设计基于该决策环境空间下的神经网络用以决策输出。

![](images/f8f58fcf74f25da64628983585717efbd716b8f8beeaeb652b89369264e46d25.jpg)  
图1机位再分配过程  
图2基于FE-GAIL 的停机位分配策略学习算法Fig.2Algorithm of gate reassignment based on FE-GAIL

# 1.2决策环境空间模型

为更好地描述决策环境空间模型，首先定义相关概念：

定义1待分配航班 $\mathbf { f } _ { o }$ ：指当前需要被调整机位的航班。

定义2动态滑动窗口 $T _ { \nu } ( \mathrm { m i n } )$ ：指再分配过程中划定需要考虑的时间范围的窗口。停机位的再分配问题中可调整对象一般为落地时间晚于待分配航班 $\mathbf { f } _ { o }$ 的其他航班，起始点是待分配航班 $\mathbf { f } _ { o }$ 的实际落地时间。

GAIL是一种基于马尔可夫决策过程(markovdecisionprocess,MDP)的算法，根据各个时间点观察环境得到的状态，选择需要执行的动作，并根据环境返回值循环往复得到执行动作序列。机位再分配调整过程中，交互环境模型以及状态转移概率处于未知状态，随参数的迭代而迭代更新，故将MDP描述为一个四元组 $\langle S , A , R , \gamma \rangle$ 。

其中 $s$ 为状态空间即 ${ \cal { S } } = \{ { \mathrm { s } } _ { 1 } , s _ { 2 } , . . . , s _ { i } , . . . \}$ 。表示某一时刻t下的机位使用计划的特征空间描述 $s _ { \mathrm { i } }$ 。动作空间 $A$ 是可以执行的动作 $\boldsymbol { a }$ 的集合，即 $A { = } \{ \mathsf { a } _ { 1 } , a _ { 2 } { , } { , } { \ldots } , a _ { i } { , } { \ldots } , a _ { N } \}$ ，其中 $a _ { i }$ 表示操作人员将待分配航班 $\mathbf { f } _ { o }$ 的调整至机位i。 $R$ 为奖励函数，而 $\gamma$ 表示学习率。

# 1.2.1多通道机位状态特征矩阵

为定义机位状态空间 $s _ { t }$ ，首先需要明确机位分配的决策因素。影响人工机位再分配决策的因素主要包括机位特征(机型尺寸属性、业务属性、航空公司属性)、航班特征(机型尺寸属性、业务属性、航空公司属性)、待分配航班属性(同航班特征)及机位前后时段占用状态等，因此本文建立了如图3所示的机位状态环境特征模型，将动态滑动窗口内的机位甘特图映射为状态特征矩阵。

图3左侧为停机位占用状态的甘特图，其中每行对应于一个机位，每列对应于一个时间块。右侧为针对停机位再分配中特征信息提出的多通道机位状态特征矩阵，其中每个通道表示一种航班属性或停机位属性所对应的嵌入编码，具体的编码嵌入方式在1.2.3节中进一步展开叙述。

假设停机位总数量为 $N$ ，为了减小状态维度，以10分钟为一个时间块，动态滑动窗口中需要表征的时间块数量为$T _ { \mathrm { b } } = T _ { \mathrm { w } } / 1 0$ ，故占用矩阵每个通道的矩阵维度大小为 $T _ { b } \times N$ 。

![](images/ab0186dce355e024afa2a64ce429360c002ccc7985c03ac1887905e1d8b9fc3d.jpg)  
图3多通道机位占用状态矩阵  
Fig.3Multi-Channels occupation state matrix   
图4状态矩阵中机型尺寸属性通道  
Fig.4Flight size attribute channel in the state matrix

1.2.2属性特征

航班和停机位的特征是决定航班和停机位匹配关系的重要因素，表1给出了部分典型的属性特征说明。

Tab.1Attribute features list   

<html><body><table><tr><td>属性名称</td><td>属性值</td><td>属性说明</td></tr><tr><td></td><td></td><td>机型尺寸属性A/B/C/D/E/F航班的机型尺寸不得超过停机位尺寸</td></tr><tr><td>业务属性</td><td>国际/国内/地区</td><td>国际航班应停靠在国际机位，国内亦 同，部分远机位无限制</td></tr><tr><td>航空公司属性</td><td>CA、CZ等</td><td>航班应停靠对应航司归属停机位</td></tr></table></body></html>

以航班-机位尺寸匹配属性为例，传统的停机位分配算法中需要人工设置匹配关系的优先级权重表(如表2所示)，以尽可能减少小飞机占用大机位的情况。为了避免大量属性权重值的人为给定，通过将航班和停机位的属性以特征编码的形式建立状态特征矩阵，其权重匹配关系不显性地体现在算法模型中，而是通过神经网络的参数表示，再通过GAIL的方式进行参数学习。

表1属性特征表  
Tab.2Flight-gate size matching weight   

<html><body><table><tr><td>飞机\机位</td><td>A类</td><td>B类 C类</td><td></td><td>D类 E类</td><td>F类</td></tr><tr><td>A类</td><td>100</td><td>80</td><td>60</td><td>40</td><td>20 10</td></tr><tr><td>B类</td><td>/</td><td>100</td><td>60</td><td>40 20</td><td>10</td></tr><tr><td>C类</td><td>/</td><td>/</td><td>100</td><td>70 50</td><td>30</td></tr><tr><td>D类</td><td>/</td><td>/</td><td>/</td><td>100 80</td><td>60</td></tr><tr><td>E类</td><td>/</td><td>/</td><td>/</td><td>/ 100</td><td>80</td></tr><tr><td>F类</td><td>/</td><td>/</td><td>/</td><td>/</td><td>/ 100</td></tr></table></body></html>

根据表1的属性特征表，设航班集合为 $F$ ，则第 $k$ 个航班的属性以向量的形式表示为

$$
A _ { f k } = [ a _ { f 1 k } , a _ { f 2 k } , a _ { f 3 k } ]
$$

其中 $\boldsymbol { a } _ { f 1 k }$ 表示航班 $k$ 的机型尺寸属性， $\boldsymbol { a } _ { f 2 k }$ 表示业务属性，$a _ { f 3 k }$ 表示航空公司属性。

第i个停机位的属性向量表示为

$$
A _ { g i } = [ a _ { g 1 i } , a _ { g 2 i } , a _ { \mathrm { g } 3 i } ]
$$

其中 $a _ { \scriptscriptstyle \mathrm { g l } i }$ 表示停机位 $i$ 机位尺寸属性， $a _ { g 2 i }$ 表示业务属性， $a _ { g 3 i }$ 表示航空公司属性。

# 1.2.3属性特征的编码嵌入

由于航班属性特征与机位的占用情况相关，故首先定义机位的占用状态特征矩阵。设图3中停机位占用状态特征矩阵表示如下：

$$
O = \left[ \begin{array} { c c c c } { { o _ { 0 0 } } } & { { o _ { 0 1 } } } & { { \cdots } } & { { o _ { 0 T } } } \\ { { o _ { 1 0 } } } & { { o _ { 1 1 } } } & { { \cdots } } & { { o _ { 1 T } } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { o _ { N 0 } } } & { { o _ { N 1 } } } & { { \cdots } } & { { o _ { N T } } } \end{array} \right]
$$

其中 $o _ { i j } \in \{ 0 , 1 \}$ 表示第 $i$ 个机位在第 $j$ 个时间块上的决策变量，若航班 $k$ 停靠于机位i则取1，反之取0。

根据1.2.2节中定义的属性特征，需要将属性值对应成编码的形式嵌入到机位占用状态矩阵的元素中，即特征嵌入(FeatureEmbedding，FE)。停机位和航班的相对关系与电子游戏中的地图与可操作单位的相对关系具有一定的相似性，OriolVinyals[21]等将 StarCraft II中的小地图信息进行基本编码，而可操作单位用特征向量进行表征并放置于地图中，从而得到信息编码后的完整状态。

表2航班-机位尺寸匹配权重  

<html><body><table><tr><td rowspan="5">g1 g2 g3</td><td>t1</td><td>t2</td><td>t</td><td></td><td>tT-1</td><td>tT</td></tr><tr><td>0.67</td><td>0.67</td><td>0.67</td><td>：</td><td>0</td><td>0</td></tr><tr><td>0</td><td>1</td><td>1</td><td>：</td><td>1</td><td>0</td></tr><tr><td>0</td><td>0.33</td><td>0.33</td><td>：</td><td>0</td><td>0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>gN-1</td><td>0.17</td><td>0.17</td><td>0</td><td>：</td><td>0</td><td>0</td></tr><tr><td>gN</td><td>0</td><td>0</td><td>0</td><td>：</td><td>1</td><td>1</td></tr></table></body></html>

根据上述特征嵌入(FE)方式，首先对属性值进行编码。将每种属性值单独编码成为一个通道，以机型尺寸属性为例，机型尺寸属性特征值可取 $\{ A , B , C , D , E , F \}$ ，按照等间距的方式取值，若机位在某一时间块被机型尺寸属性为 $D$ 的飞机占用(属性排序为4)，则该飞机对应占用的时间块的属性值取$4 / 6 = 0 . 6 7$ 。

再将编码后的属性值嵌入到状态矩阵中。航班第 $\nu$ 种属性对应的通道中第 $k$ 个航班对应的元素可以表示如下：

$$
x _ { i j k } = a _ { f w k } \cdot o _ { i j }
$$

$$
( 0 \le i \le N , 0 \le j \le T , k \in F )
$$

根据上式的表述，当某个时间块上没有航班占用，则对应值为0，反之则为属性值。

对于停机位属性通道，则无须表征占用状态特征，第 $u$ 种属性对应的通道中，第 $i$ 个停机位所对应的矩阵元素表示为如下形式：

$$
x _ { i j u } = a _ { g u i }
$$

$$
( 0 \le i \le N , 0 \le j \le T )
$$

完成所有航班的属性值嵌入后，最终得到该属性对应的矩阵通道如图4所示，其他属性对应的矩阵通道的构建方式同理。

# 2 模仿学习算法设计

模仿学习是一种基于序贯决策过程的人工数据学习决策策略算法(Feature Embedding-Generative Adversarial ImitationLearning，FE-GAIL)，本章将说明FE-GAIL算法在停机位再分配决策场景的算法设计。

按照上述业务场景的建模，拟采用生成对抗模仿学习(GAIL)求解机位再分配策略学习问题，为了便于描述数据的特性，在说明算法流程之前先定义相关概念一一占用度量p(occupancy measure)。

定义3占用度量p：使用策略 $\pi$ 时在环境中得到的状态-动作对 $( \mathbf { s } _ { i } , a )$ 的分布，且占用度量 $\rho$ 和策略 $\pi$ 之间存在唯一的对应关系[18]:

$$
\rho _ { \pi } ( \mathrm { s } _ { i } , a ) = \pi ( a | s _ { i } ) \sum _ { t = 0 } ^ { \infty } P ( s _ { t } = s _ { i } | \pi )
$$

其中， $\pi ( a | s _ { i } )$ 和 $P ( s _ { t } = s _ { i } | \pi )$ 分别表示动作和状态的边缘分布。根据上述定义可知，当策略与人工停机位再分配策略的占用度量越接近时，两个策略之间越相似。将GAN结合到正则优化器 $\varphi$ 中，将优化器定义为

$$
\curlyeqcirc ( \rho _ { \pi } , \rho _ { E } ) =
$$

$$
\rho _ { \pi _ { E } } ( s , a ) \mathrm { l n } ( 1 - D ( s , a ) )
$$

其中 $D$ 为生成对抗网络中的鉴别器。生成器 $\pi$ 生成用于混淆鉴别器 $D$ 的样本，而 $D$ 则用于区分和人工策略样本。

将策略 $\pi$ 的占用度量类比为生成器 $\pi$ 生成数据的概率分布，人工策略类推。此概率分布可以刻画为选择状态下的动作概率分布向量 $\pmb { \nu } _ { \pi } = [ p _ { a 1 } , p _ { a 2 } , . . . , p _ { a N } ] \ , \mathbf { p } _ { a i } \in [ 0 , 1 ]$ ，其中的元素为在给定状态下各动作被选择概率。当鉴别器 $D$ 无法区分两者时，认为 $\pi$ 具备产生与人工样本相近似样本的能力。

算法流程图如图5所示。

![](images/a6258cf9dd47d21ef9816ea34bdb7979cb11d3142f867f663c552b9e5efc43f1.jpg)  
图5FE-GAIL算法流程图  
Fig.5FE-GAIL algorithm flow chart

基于FE-GAIL的停机位再分配决策算法的基本训练流程如下：

Setp1初始化生成器 $\pi$ 和鉴别器 $D$ 的网络参数，设置训练批量大小;

Step2将人工停机位再分配操作数据以状态-动作对$( \mathrm { s } _ { i } , a )$ 进行特征嵌入(FE)作为生成器 $\pi$ 的输入，得到选择机位的动作概率分布向量 $\nu _ { \pi }$ ：

Step3按照动作概率分布向量 $\nu _ { \pi }$ 选择机位，得到生成器的输出 $( \mathrm { s } _ { i } , a _ { \pi } )$ ;

Step4将人工停机位再分配操作数据和生成器产生的样本同时输入鉴别器 $D$ 中，得到的鉴别结果根据式(7)，利用梯度更新鉴别器 $D$ 和生成器 $\pi$ 的网络参数 $\theta$ 。

通过上述算法，最终得到能够满足需求的生成器 $\pi$ 和鉴别器 $D$ ，其中生成器即为策略模型，而鉴别器将在3.3节中用于测试模型区分度。

# 3 实验分析

本章将通过数据实验的方式证明根据停机位再分配特性提出的算法可以学习到人工再分配决策策略。下文将首先介绍实验所用的数据，将通过三类实验对比IRL和BC算法，验证算法的性能。

# 3.1实验数据

根据1.1节可知，机场不同的操作人员具有各自不同的算法调参策略，即对统一参数有不同的参数配置方式。在此假设同一员工在进行行为决策时始终遵循相同的行为逻辑，利用基于 $\mathbf { A } ^ { * }$ 的启发式搜索算法模拟人工决策过程，以扩充原生较少的人工操作数据，生成足够训练算法模型的行为决策数据。

$\mathbf { A } ^ { * }$ 算法通过判断当前位置与起点之间的距离以及与终点之间的预估代价来求解代价最小的可行解，适用于多步决策下的最优决策路径搜索问题。其代价预估函数计算式如下：

$$
F ( \mathrm { s } ) { = } G ( \boldsymbol { s } ) + H ( \boldsymbol { s } )
$$

其中 $G ( \mathrm { s } )$ 为当前路径的实际代价， $H ( \mathrm s )$ 为行为预估代价。对于第 $i$ 个停机位和第 $k$ 个航班， $G ( s )$ 可以表示如下：

$$
G ( s ) = \phi ( A _ { \mu } , A _ { g i } , A _ { p k i } )
$$

其中， $\textstyle A _ { f k }$ 和 $A _ { g i }$ 分别为由式(1)和(2)得到的航班和机位属性，$A _ { p k i }$ 为根据表2的形式得到的航班-机位匹配属性。

按照上述权重计算方式，将待分航班可选机位作为可扩展的相邻节点，通过路径搜索的方式得到如图1所示的动态调整动作序列。

实验采用国内某机场中的40个停机位，分为4个指廊，共计45700余条原计划时间表的真实数据，如表3所示。

表3航班-停机位原始计划表  
Tab.3Original schedule of flight-gates   

<html><body><table><tr><td>航空公司</td><td>航班属性</td><td>机型</td><td>机位</td><td>起飞时间</td><td>落地时间</td></tr><tr><td>1</td><td>国际</td><td>333</td><td>103</td><td>5/19 02:34</td><td>5/18 23:30</td></tr><tr><td>2</td><td>国内</td><td>773</td><td>128</td><td>5/19 10:47</td><td>5/1823:33</td></tr><tr><td>3</td><td>国际</td><td>321</td><td>101</td><td>5/19 1:24</td><td>5/1823:34</td></tr><tr><td>4</td><td>国际</td><td>738</td><td>102</td><td>5/19 7:18</td><td>5/18 23:52</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

在此基础上对航班落地和起飞时间加入随机扰动，用于模拟机场发生延误时的实际变动情况，再利用 ${ \mathbf A } ^ { * }$ 算法模拟人工分配的决策行为，以得到人工分配操作行为轨迹数据。根据历中延误信自将航班的延误分布情况田泊松分布描述，

$$
P ( x = k ) = { \frac { \lambda ^ { k } } { k ! } } e ^ { - \lambda }
$$

其中 $k$ 为延误时间块的数量。定义航班 $f _ { k }$ 与停机位 $\mathbf { g } _ { i }$ 对应的权重参数集 $W$ 如下所示。

$$
W = [ A _ { f k } , A _ { g i } , A _ { p k i } ]
$$

根据策略不变假设，对于员工i而言其行为参数集 $W$ 始终保持不变。为了测试模型对于不同员工行为逻辑的学习能力和区分度，本文设置了三组参数集 $W _ { i } , i \in \{ 1 , 2 , 3 \}$ 以模拟三种不同的分配操作行为逻辑，利用上述的 $\mathbf { A } ^ { * }$ 算法生成三组数据集 $D _ { i } , i \in \{ 1 , 2 , 3 \}$ ，每组数据集 $D _ { i }$ 包括训练数据10000条，测试数据2000条。

# 3.2模型可靠度结果分析

为了量化训练后的模型分配结果与人工操作行为的一致性水平，根据2.1节中的动作概率分布向量 $\boldsymbol { \nu } _ { \pi }$ ，本文定义归一化的可靠度评分R如下：

$$
r _ { i } = \left\{ \begin{array} { l } { { 1 , \mathrm { i f } \ p _ { a i } \leq \ p _ { a _ { E } } \ , \ p _ { a _ { E } } , \mathsf { p } _ { a i } \in \nu _ { \pi } \ , } } \\ { { i \in [ 1 , N ] } } \\ { { 0 \ , o t h e r w i s e } } \end{array} \right.
$$

$$
\mathrm { R } { = } \frac { 1 } { M N } \sum _ { i { = 0 } } ^ { M } \sum _ { i { = 0 } } ^ { N } r _ { i }
$$

其中 $M$ 为每次测试采样的样本数量， $\mathbf { \Omega } _ { N }$ 为停机位数量， $a _ { E }$ 为人工操作动作。

取动态滑动窗口时间长度 $T _ { \mathrm { w } }$ 为300分钟，对应的时间块数量为30，状态空间维度为 $4 0 ^ { * } 3 0 ^ { * } 9$ 。训练过程中每训练100次作为一次迭代，并进行一次测试，每次测试采样的人工轨迹样本数量为1000，设置学习率 $\gamma = 0 . 0 0 1$ ，测试10轮得到平均可靠度评分的变化趋势图如图6所示，其中三条曲线分别表示来自三名不同操作人员给定的权重参数所对应的数据集进行FE-GAIL模型训练，图中纵坐标为训练过程中单步平均可靠度评分，横坐标为经历的迭代次数。

如图6所示，经过250次迭代后模型达到收敛，通过测试集测试模型，每次测试采样的样本数量为200，采样10次得到的测试结果取平均，得到平均单步可靠度评分，结果如表4所示，三个数据集下模型的单步可靠度评分达到 $89 . 3 0 \%$ ，$8 7 . 4 5 \%$ 和 $91 . 3 3 \%$ ，相较于IRL和BC算法平均可靠度评分分别提升 $9 . 1 6 \%$ 和 $1 5 . 8 4 \%$ ，表明算法策略能够收敛于与被学习的人工策略具有较低的偏差的结果。

![](images/4865d9cb65e352807585ea8760fac62455671d12a25e05bbafbe82360c900931.jpg)  
图6不同数据集下模型训练平均可靠度评分

为更好地掌握模型结果与人工数据之间的可靠度评分具体分布情况，采用2000条测试样本测试可靠度评分得到其分布，得到单步可靠度评分的分布如表5所示，可靠度评分在 $90 \%$ 以上的步数的占比分别达到 $7 5 . 2 \%$ 、 $7 2 . 6 \%$ 和 $8 4 . 4 \%$ ，而可靠度评分低于 $80 \%$ 的区间包含步数的占比 $1 3 . 8 5 \%$ 、$1 6 . 2 0 \%$ 和 $7 . 2 0 \%$ ，说明人工分配方案在本模型结果中保持较

高的可靠度。

Tab.4Average reliability score of single step   

<html><body><table><tr><td></td><td>D</td><td>D</td><td>D3</td><td>Average</td></tr><tr><td>FE-GAIL</td><td>89.30%</td><td>87.45%</td><td>91.33%%</td><td>88.38%</td></tr><tr><td>IRL</td><td>78.37%</td><td>76.64%</td><td>82.61%</td><td>79.22%</td></tr><tr><td>BC</td><td>73.35%</td><td>68.94%</td><td>74.83%</td><td>72.54%</td></tr></table></body></html>

表5单步可靠度评分分布

表4平均单步可靠度评分统计  
Tab.5Single step reliability score distribution   

<html><body><table><tr><td></td><td>D</td><td>D</td><td>D3</td></tr><tr><td>91%-100%</td><td>75.20%</td><td>72.60%</td><td>84.35%</td></tr><tr><td>81%-90%</td><td>10.95%</td><td>11.20%</td><td>8.45%</td></tr><tr><td><80%</td><td>13.85%</td><td>16.20%</td><td>7.20%</td></tr></table></body></html>

# 3.3模型区分度结果分析

不同策略之间存在的差异将导致结果之间存在差异，为证明模型对于不同来源数据的区分度，本节通过3组不同数据集训练模型，分别代表不同的操作策略，测试模型对于各个数据集的鉴别效果。混淆矩阵是一种描述评价分类结果错误率的常用方式，其中根据模型结果正确与否和实际正反例之间的关系，将样本分为四个类别TP、FN、FP、TN。样本$p$ 的所属标签类别 $c _ { s p }$ 可以通过设置不同的阈值 $\mathbf { V } _ { t h }$ ，设通过数据集 $\mathrm { ~ D ~ } _ { i }$ 训练得到的模型预测样本 $p$ 标签值在采样数据中预测标签值排名为 $\nu$ ，即：

$$
\scriptstyle \left\{ \mathbf { c } _ { s p } = \mathrm { T P } , { \mathrm { i f ~ } } \mathbf { v } > \mathbf { v } _ { \mathrm { t h } } \ , \ \mathbf { p } \in \mathbf { D } _ { i } \right.
$$

PR曲线是通过计算不同的正例阈值下的精确率 $P$ (Precision)和召回率 $R$ (Recall)得到变化曲线，两者的计算公式如下：

$$
P = { \frac { T P } { T P + F P } }
$$

$$
R = { \frac { T P } { T P + F N } }
$$

为了综合考虑精确率和召回率，采用综合度量指标F度量值来评价其结果，其计算公式如下：

$$
F = { \frac { 2 P R } { P + R } } = { \frac { 2 T P } { 2 T P + F N + F P } }
$$

区分度测试集包含全部三组数据共6000个样本数据，分别采用三个模型对样本是否来自于该模型所对应的训练数据集进行判别，以此计算混淆矩阵。按照 $10 \%$ 为间隔分别选取不同的阈值 $\mathbf { v } _ { t h }$ ，根据不同模型对应的混淆矩阵，得到不同训练数据集下FE-GAIL模型的P-R曲线如图7所示，图中被标注点表示各个模型取最大F值的点，说明在不同数据集下本模型的区分度性能接近，模型区分度性能受数据集影响小。

![](images/911ac48d9b63e1360695f1e142f21db375b2684dec27b4c058271bcec23cac4c.jpg)  
Fig.6Average model training reliability score in different datasets   
图7不同数据下模型PR曲线Fig.7PR curves of the models under different data

图7中被标注的三个点为模型在三组数据下的最大F值，其值如表6所示，三个数据集的F值分别为0.7632、0.7892和0.8071，说明模型对不同来源数据的区分能力较好。

Tab.6Fvalues of the models underdifferent data   

<html><body><table><tr><td></td><td>D</td><td>D</td><td>D3</td></tr><tr><td>FE-GAIL</td><td>0.7632</td><td>0.7892</td><td>0.8071</td></tr><tr><td>IRL</td><td>0.6743</td><td>0.6912</td><td>0.6843</td></tr><tr><td>BC</td><td>0.5958</td><td>0.6191</td><td>0.6367</td></tr></table></body></html>

# 3.4算法同等参数误差水平分析

由于本算法是通过对神经网络进行参数学习的方式得到与人工决策相匹配的隐性参数设置，无法直接和人工参数配置进行相似度对比，因此将通过间接实验的方式测试算法同等参数误差水平。本实验中对三个数据集的生成过程加入一定的参数误差，测试参数误差下的分配结果与原始分配结果间的相似度，同时测试通过本算法进行参数学习所得的分配结果与原始分配结果的相似度，以获得本算法分配结果的同等参数误差水平。

定义相似度评分 $q _ { s c o r e }$ 的计算公式如下：

$$
q _ { s c o r e } = \alpha _ { 1 } N _ { s } + \alpha _ { 2 } N _ { s a } + \alpha _ { 3 } N _ { \mathrm { d i f } }
$$

其中与人工操作行为相比， $ { N _ { s } }$ 为与其相同的动作数量， $N _ { s a }$ 为航班、机位属性 $\textstyle A _ { f k }$ 和 $A _ { g i }$ 与其相同的动作数量， $N _ { \mathrm { d i f } }$ 为航班、机位属性 $A _ { \mathcal { \hat { k } } }$ 和 $A _ { g i }$ 与其不同的动作数量， $\alpha _ { \mathrm { { l } } }$ 、 $\alpha _ { 2 }$ 、 $\alpha _ { 3 }$ 分别为三者对应的权重参数。

表7为三个数据集在不同参数误差下，生成的新数据集与原数据集以及通过原数据训练的模型得到的分配结果之间的对比情况。

表6不同数据下模型的F值  
表7不同参数误差的数据集  
Tab.7Datasets of different parameter errors   

<html><body><table><tr><td>数据集</td><td>参数集误差</td><td>Ns</td><td>Nsa</td><td>Ndif</td><td>qscore</td></tr><tr><td rowspan="7">D</td><td>5</td><td>10355</td><td>201</td><td>1444</td><td>0.7780</td></tr><tr><td>10</td><td>9149</td><td>1088</td><td>1763</td><td>0.6185</td></tr><tr><td>15</td><td>7007</td><td>2299</td><td>2694</td><td>0.1530</td></tr><tr><td>20</td><td>6730</td><td>2479</td><td>2791</td><td>0.1045</td></tr><tr><td>25</td><td>6418</td><td>2768</td><td>2814</td><td>0.0930</td></tr><tr><td>FE-GAIL</td><td>7097</td><td>3709</td><td>1194</td><td>0.9030</td></tr><tr><td>IRL</td><td>6488</td><td>3344</td><td>2168</td><td>0.416</td></tr><tr><td></td><td>BC</td><td>5988 3246</td><td>2766</td><td>0.117</td><td></td></tr><tr><td rowspan="4">数据集</td><td>参数集误差</td><td>Ns</td><td>Nsa</td><td>Ndif</td><td>qscore</td></tr><tr><td>5</td><td>9328</td><td>460</td><td>2212</td><td>0.3940</td></tr><tr><td>10</td><td>8227</td><td>1186</td><td>2587</td><td>0.2065</td></tr><tr><td>15</td><td>7101</td><td>2260</td><td>2639</td><td>0.1805</td></tr><tr><td rowspan="4">D2</td><td>20</td><td>6749</td><td>2454</td><td>2797</td><td>0.1015</td></tr><tr><td>25</td><td>6445</td><td>2748</td><td>2807</td><td>0.0965</td></tr><tr><td>FE-GAIL</td><td>7663</td><td>2377</td><td>1960</td><td>0.5200</td></tr><tr><td>IRL</td><td>6925</td><td>2546</td><td>2529</td><td>0.2355</td></tr><tr><td></td><td>BC</td><td>6858</td><td>2287</td><td>2855</td><td>0.0725</td></tr><tr><td rowspan="4">数据集</td><td>参数集误差</td><td>Ns</td><td>Nsa</td><td>Ndif</td><td>qscore</td></tr><tr><td>5</td><td>10524</td><td>154</td><td>1322</td><td>0.8390</td></tr><tr><td>10</td><td>8732</td><td>1418</td><td>1850</td><td>0.5750</td></tr><tr><td>15</td><td>7058</td><td>2903</td><td>2039</td><td>0.4805</td></tr><tr><td rowspan="5">D3</td><td>20</td><td>6994</td><td>2931</td><td>2075</td><td>0.4625</td></tr><tr><td>25</td><td>6638</td><td>3222</td><td>2140</td><td>0.4300</td></tr><tr><td>FE-GAIL</td><td>7732</td><td>2981</td><td>1287</td><td>0.8565</td></tr><tr><td>IRL</td><td>6985</td><td>2687</td><td>2328</td><td>0.336</td></tr><tr><td>BC</td><td>6628</td><td>2442</td><td>2930</td><td>0.035</td></tr></table></body></html>

在三个数据集下，与 $5 \%$ 参数设置偏差下的结果相比，模型结果中 ${ N _ { \mathrm { d i f } } }$ 的数量较少，但同时 $ { N _ { s } }$ 的数量也较少，说明本模型的分配结果能够得到与人工数据属性特征更为接近的结果。对比IRL和BC 算法模型，FE-GAIL 算法模型在不同数据集上的相似度评分均有较为明显的提升。FE-GAIL模型的分配结果的相似度评分分别为0.903、0.52、0.8565，分数较 $5 \%$ 参数设置偏差所带来的分配结果仍有优势，因此可以认为本算法进行参数学习后所得结果同等于 $5 \%$ 人工参数偏差下的分配结果。

# 4 结束语

针对机位再分配问题特性，提出了基于特征嵌入的生成对抗模仿学习算法从航班的机位再分配操作数据中学习其对应的操作策略的方法，用以解决航班延误时机场的停机位动态调整问题。在环境建模的过程中加入特征嵌入的表征方式提升机位和航班属性特性可读性，且由于GAN网络的加入缓解了动态环境中样本效率低下的问题，对比IRL和BC算法在停机位动态分配策略学习任务中多项指标均有较明显的优势。对多组不同的机场调度人员的调度策略数据进行了策略学习，对比不同参数误差情况下与原有操作数据之间的差异，证明通过本模型得到的结果可以规避 $5 \%$ 左右的参数设置偏差。本文研究方向为停机位动态分配，基于本文提出的FE-GAIL算法策略模型的机位分配模型输出指派方案具有与人工操作方式更高的一致性，可减少机位调度操作人员对算法推荐方案的二次调整，从提升算法结果的实用性的角度提升机场运行效率。

目前在被模仿策略的复杂度上，算法还有进一步的提升空间，后续的工作中可以加强算法对更为接近实际操作人员操作复杂性的数据进行策略拟合。

# 参考文献：

[1]Pternea M.Optimal Reassignment of Flights to Gates Focusing on Transfer Passengers [D],2019.   
[2]Das G S,Gzara F,Stitzle T.A review on airport gate assignment problems: Single versus multi objective approaches [J]. Omega,2020,92: 102146.   
[3]Deng Wu,Li Bo,Zhao Huimin. Study on an Airport Gate Reassignment Method and Its Application [J].Multidisciplinary Digital Publishing Institute,2017,9(11): 258.   
[4] Zhang Dong，Klabjan D.Optimization for gate re-assignment [J]. Transportation Research Part B,2017,95:260-284.   
[5]Pternea M，Haghani A.Mathematical models for flight-to-gate reassignment with passenger flows: State-of-the-art comparative analysis, formu-lation improvement,and a new multidimensional assignment model[J].Computers & Industrial Engineering,2018,123:103-118.   
[6]Pternea M,Haghani A.An aircraft-to-gate reassignment framework for dealing with schedule disruptions [J]．Journal of Air Transport Management,2019,78:116-132.   
[7]Yu Chuhang,Zhang Dong, Lau HYKH.A heuristic approach for solving an integrated gate reassignment and taxi scheduling problem[J]. Journal of Air Transport Management, 2017,62:189-196.   
[8]姜雨，胡志韬，童楚，刘振宇，陈丽丽，张洪海．面向航班延误的停 机位实时指派优化模型[J].交通运输系统工程与信息，2020,20 (05):185-190,217．(Jiang Yu，Hu Zhitao，Tong Chu，et al.An Optimization Model for Gate Re-assignment under Flight Delays [J]. Journal of Transportation Systems Engineering & Information Technology,20 (5): 185-190,217.)   
[9]Maharjan B,Matis TI,An optimization model for gate reassignment in response to flight delays,Journal ofAir Transport Management,2011,17 (4): 256-261.   
[10] Chen Dian,Zhou Bragy,Koltun V,et al.Learning by cheating [C]// Conference on Robot Learning.PMLR,2020: 66-75.   
[11] Zhou Yang,Fu Rui,Wang Chang，et al.Modeling Car-Following Behaviors and Driving Styles with Generative Adversarial Imitation Learning[J]. Sensors,2020,20(18):5034.   
[12]Lioutikov R,Neumann G,Maeda G,et al.Learning movement primitive libraries through probabilistic segmentation [J]. The International Journal of Robotics Research,2017,36 (8): 879-894.   
[13] Finn C,Levine S,Abbeel P.Guided cost learning:Deep inverse optimal control via policy optimization [C]//International conference on machine learning.PMLR,2016:49-58.   
[14] Sun W,Venkatraman A,Gordon G J,et al.Deeply aggrevated: Differentiable imitation learning for sequential prediction[C]// International Conference on Machine Learning.PMLR,2017:33o9-3318.   
[15] Pan Menghai,Huang Weixiao,Li Yanhua,et al.xGAIL:Explainable Generative Adversarial Imitation Learning for Explainable Human Decision Analysis [C]// Proceedings of the 26th ACM SIGKDD International Conference on Knowledge Discovery& Data Mining.2020: 1334-1343.   
[16] Shou Zhenyu,Di Xuan,Ye Jieping,et al. Optimal passenger-seeking policies on E-hailing platforms using Markov decision process and imitation learning [J].Transportation Research Part C:Emerging Technologies,2020,111: 91-113.   
[17] Hussein A,Elyan E,Gaber MM,et al.Deep imitation learning for 3D navigation tasks [J].Neural computing and applications,2018,29(7): 389-404.   
[18] Ho J,Ermon S.Generative adversarial imitation learning [J].Advances in neural information processing systems,2016,29:4565-4573.   
[19] Torabi F,Warnell G,Stone P.Recent advances in imitation learning from observation [J].arXiv preprint arXiv:1905.13566,2019.   
[20] Chen Xia,Kamel A E.Neural inverse reinforcement learning in autonomous navigation [J].Robotics and Autonomous Systems,2016,84: 1-14.   
[21] Vinyals O,Babuschkin I,Wojciech M.Czarnecki Grandmaster level in StarCraft II using multi-agent reinforcement learning [J].Nature,2019, Vol 575,350-354.