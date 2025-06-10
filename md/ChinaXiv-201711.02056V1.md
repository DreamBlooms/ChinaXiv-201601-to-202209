# 基于复杂网络的虚拟社区创新知识传播机制研究

叶腾」韩丽川」邢春晓2,张妍2,31(上海交通大学安泰经济与管理学院上海 200030)2(清华大学信息技术研究院北京 100084)3(清华信息科学与技术国家实验室北京 100084)

摘要：【目的】通过构建知识传播理论模型，探究虚拟社区中知识传播效果的内在影响机制。【方法】基于虚拟社区GitHub 的实际数据，利用社会网络分析法和回归分析法，实证研究社区成员的位置特性、区域特性和创新认可度对知识传播速度和传播范围的影响。【结果】位置中心性通过改变潜在受众数量影响知识传播范围。创新认可度通过影响传播概率影响知识传播速度。区域密集度与知识传播速度和传播范围呈负相关关系。【局限】研究结果仅基于一个大型虚拟社区，结论的普遍性有待进一步证实。【结论】对虚拟社区的管理策略以及创新成员在虚拟社区中的知识分享策略和创新策略提出建议。

关键词：合作创新 复杂网络 虚拟社区知识传播分类号：G206.3 G350

# 1引言

创新是新技术的研究、开发、生产到首次实现商业化全过程的经济活动，是企业乃至国家核心竞争力的主要来源。日趋激烈的市场竞争和快速变化的市场需求要求多元化的创新主体在创新过程中协同完成复杂的创新，创新应该是开放式的，合作创新成为非常重要的创新模式。

随着互联网和计算机技术的快速发展，网络上涌现出大量具有软件开发和项目开发功能的虚拟社区，如开源社区Linux、开源中国社区等。虚拟社区是基于信息网络和计算机技术并由拥有共同兴趣及需求的成员组成的，成员可以分散在不同地区，通过在线方式传播和扩散创新知识。虚拟社区是合作创新的主要力量，获取、传播和创造知识成为维系社区参与度的主要原因，创新知识的传播也成为影响虚拟社区创新绩效的关键因素，研究创新知识的传播机制对虚拟社区的成功和发展具有重要意义。

虚拟社区中成员间的关系可以看作一种知识型社会网络，一种由大量的知识传播者与知识接收者之间建立的、有向的、动态的、复杂的知识网络。随着互联网和计算机技术的发展，网络数据便捷的存储和获取为大规模复杂网络的实证研究提供了便利条件，如博客[1]、社交媒体[2-3]、航空交通[4]。社会网络作为一种复杂网络，其度分布通常符合幂律形式(Power-Law)[5-9],并且具有社区结构(Community Structure)[1,10]。网络的结构可以决定网络的功能[11]，如信息传递功能[12]、社交功能[2等，社会网络的结构属性也影响动态传播过程。本文基于社交编程和代码托管社区GitHub中的大量真实数据，从复杂网络的视角，将静态网络性质和动态传播模型相结合，建立创新知识传播的理论模型，实证探索虚拟社区中创新知识传播的动态机制。

# 2相关研究

虚拟社区中创新知识的传播研究已经引起了学者们的广泛关注，越来越多的研究也开始从复杂网络的视角研究虚拟社区中的知识传播问题。这些研究主要分为两类。

(1）使用静态网络性质研究传播问题。如Cha 等[3]获取了照片在社交网络中的传播范围和传播速度，并发现过半照片的“收藏"行为是由网络中的好友关系(即复杂网络中的边)决定的。Facebook上的实验研究发现强连接(Strong Tie)更具有影响力，然而弱连接的数量才是决定新信息能否大规模传播的主要影响因素[13]。彭红彬等针对CSDN 技术论坛，以用户为节点，知识交流关系为边，建立知识交流网络，发现知识传播网络具有三角形的基本结构特征。然而该研究只涉及知识分享的静态网络性质，并未考虑知识传播的动态过程。刘佩等基于"知乎"精华区用户的社会网络，定量研究网络的静态性质，如小世界性质，并通过个案分析指出中介中心度高有利于知识传播。邹儒楠等[14]以小木虫生命科学论坛为例，充分分析了非正式学术交流的特点，认为交流过程中权威的弱化、交流过程的多中心性，有利于知识的转移和扩散，但同样未涉及传播的动态过程。

(2）应用动态传播模型分析传播过程。一部分研究建立模型，通过传播结果推算传播路径乃至传播网络[15-16]，并根据测得的传播路径预测传播效果[17]。另有很多研究借鉴传染病领域的经典SIR模型及其改进模型[18-21]，分析信息的传播机制。如Pastor-Satorras 等[22]基于SIS模型分析网络结构与计算机病毒传播的关系，发现在度分布服从幂律分布的网络中，病毒流行的门槛为零，永远可以发生。Girvan等[23研究了可突变的SIR模型，发现在特定网络参数下，疾病可以周期性爆发。Gruhl 等[21将博客中的信息传播分为传播话题和个体传播两层，并分别使用SIR和SIRS模型进行实证研究。国内的学者也在这方面进行了有益探索，如魏静[24使用SIR模型研究网络流行语在不同的虚拟社区中的传播机制、王晓明[2基于SIR模型提出微博信息的传播模型、张立凡等[26基于 SIR改进模型探讨媒体干预下网络舆情的传播规律。这些研究大多都是仿真研究，并且没有实际数据支持仿真结论；而其中的实证研究[21]也未考量网络的结构性质对网络动态传播过程的影响。

综上所述，在虚拟社区知识传播的相关研究中，基于静态网络性质的实证研究缺乏对传播动态过程的探索，这样的研究只能得到网络性质和传播结果的相关关系，需要进一步借助动态模型才能了解产生该相关关系的内在影响机制；而基于动态传播模型的研究又多为仿真研究，使用模拟数据的研究结论具有一定的局限性；少数关于传播模型的实证研究也未涉及网络的静态性质对网络动态传播过程的影响。为了填补这个空白，本文尝试把虚拟社区的静态网络性质、动态传播过程和实际数据相结合，实证探求结构性质对传播过程的影响。

# 3理论模型与变量计算

# 3.1 研究假设

位置中心性表示了一个节点在网络中位置的重要性。一个节点连接的节点越多、重要性越高，则该节点的中心性越高。因此，位置中心性高的节点产生的创新成果容易被更多的创新成员接触到，即潜在受众越多。潜在受众越多，最终的传播范围应当更广。Stieglitz等[27]的实证研究发现，网络社交媒体Twitter上被关注人数(即网络节点的入度)越多的人所发的信息可以被更多的社区成员转发。文献[9]研究发现，在问答社区知乎中入度较高的成员更容易吸引其他成员阅读和讨论。网络节点的人度是位置中心性的重要影响因素。因此，有以下假设：

H1：位置中心性越大，潜在受众则越多，进而扩大传播范围。

创新认可度是节点的属性，指的是虚拟社区中创新成员的创新绩效被认同的程度，取决于其他虚拟社区成员对该创新成员此前创新水平和创新绩效的认可。虚拟社交社区信息传播的实证研究发现，信息发布成员的权威性可以对信息传播起到积极作用[28]，并且信息发布成员在平台上的历史时间越长，越容易获得其他成员的信任，其发布的信息也被认为具有较高的可信度和价值[29-30]。研究结果表明，基于信任的"认同"因素可以提高知识欲求[31]，进而提高传播动机。创新认可度高的节点在虚拟社区中是被广泛认同的或最值得信任的创新成员，当易感者接触到该节点的新增创新成果时，会即刻共享并传播。所以得出以下假设:

H2：节点创新认可度越高，潜在受众的传播概率则越大，进而提高传播速度。

聚集系数是节点附近的区域特性，代表了与该节点相连节点的紧密程度。聚集系数越高，表明“朋友”的"朋友"彼此之间也是“朋友"的概率越大。因此，创新知识越容易集中在该“朋友"圈子中，所以传播范围越小，传播速率(单位时间内新增传播者的数量)也越小。虚拟社区的相关研究中,Lerman等[12]通过比较两个虚拟社区Twitter和Digg发现，聚集系数高的网络虽然起初传播效率比较高，但是后期动力不足，最终传播范围较小。此前关于传染病传播的研究也表明，聚集系数越高的网络，传染病的传播效率越低[32]。由此，有以下假设:

H3a：区域聚集程度越大，创新成果的传播范围越小。

H3b：区域聚集程度越大，创新成果的传播速率越小。

# 3.2 理论模型

根据以上假设，本文建立创新成果在网络中传播的理论模型，如图1所示：

![](images/8d49500363a0ec8dc68b5e188e46bc7e5f35345e416c7e6d4a23bcc2b040a738.jpg)  
图1理论模型

# 3.3 变量计算

(1）自变量计算

$\textcircled{1}$ 位置特性计算[33]。节点的PageRank 中心性(后文用位置中心性指代)是节点的位置属性，度量了节点在网络中重要程度。一个节点的重要程度与该节点所连接节点的重要程度相关。若一个节点连接了很多具有较高中心性的节点，那么该节点将具有较高的中心性。定义 $\textbf { D }$ 为对角矩阵,$\mathrm { D } _ { \mathrm { i i } } = \mathrm { m a x } ( \mathrm { k } _ { \mathrm { i } } ^ { \mathrm { o u t } } , 1 )$ ，A为网络的邻接矩阵，则所有节点的中心性组成的向量 $\mathbf { x }$ 计算如下：

$$
\mathbf { x } = \mathbf { D } ( \mathbf { D } - \boldsymbol { \alpha } \mathbf { A } ) ^ { - 1 } \boldsymbol { 1 }
$$

经过数据清洗和整理后，以创新成员为节点，关注关系为边(关注者指向被关注者)建立创新成员关注网络，并使用Gephi软件计算每个节点的位置特性PageRank，参数$\mathbf { \alpha } \propto 0 . 8 5$ 。

$\textcircled{2}$ 区域特性计算。聚集系数(ClusteringCoefficient)是节点的区域特性，描述网络中节点间的聚集情况，即目标节点附近区域网络的紧密程度。例如，在朋友网络中，一个人朋友的朋友可能也是他的朋友，或者说他的两个朋友彼此可能也是朋友。聚集系数c就是表示一个人朋友的朋友也是他的朋友的概率。若节点i与其他 $\mathbf { k }$ 个节点相连，且这 $\mathbf { k }$ 个节点之间存在e条边，则节点i的聚集系数计算方法如下：

$$
\mathbf { C _ { i } } = \mathbf { e } / [ \mathbf { k } ( \mathbf { k } - 1 ) / 2 ]
$$

本文使用Gephi 软件计算关注网络中每个用户的聚集系数作为区域聚集程度的度量。

$\textcircled{3}$ 创新认可度计算。由于点赞是对创新成果的认可，是创新绩效的一种衡量，因此，使用该成员所有创新成果获得的总赞数来衡量其他创新成员对该成员创新成果的认可度。为了更准确地描述创新成员开发某一个信息库时的认可度，使用该创新成员开发该信息库前获得的所有点赞数作为创新认可度的度量。

(2）中介变量和因变量计算

SIR模型为创新知识传播的内在机制提供了很好的研究依据。本文使用SIR模型中的变量对研究模型中的变量(潜在受众、传播概率、传播范围和传播速率)进行度量。

在传染病模型SIR模型中，S为易感状态,I为感染状态，R为康复状态。根据虚拟社区创新知识传播的方式，重新定义模型中的变量如下：S状态是可能接触到创新知识并传播创新知识的状态,I是向其他创新用户传播创新知识的状态,R是不再传播该知识的状态，参数β为网络中的节点从S状态到I状态的状态转移概率，参数γ为网络中的节点从I状态到R状态的转移速率， $\mathrm { \Delta S _ { 0 } }$ 为易感者的初始数量， $\mathrm { ~ N ~ }$ 为网络中的节点总数。因此有微分方程[13]如下：

$$
\mathrm { { \frac { d S } { d t } } = - \beta I S / N }
$$

$$
\mathrm { \frac { d I } { d t } } = - \beta \mathrm { I S / N } - \gamma \mathrm { I }
$$

$$
\frac { \mathrm { d } \mathrm { R } } { \mathrm { d t } } { } = \gamma \mathrm { I }
$$

由于微分方程的参数有 ${ \bf S } _ { 0 } \setminus \mathrm { I } _ { 0 } \setminus \mathrm { R } _ { 0 } \setminus \beta \setminus \gamma _ { \circ }$ 。每一组参数可以唯一确定出 S(t)，I(t)，R(t)曲线。根据传播真实数据，可以计算出真实数据与该曲线的均方根误差(RMSE)。使用Matlab 中的 fminsearch 函数寻找最小化均方根误差的一组参数，获得最佳的拟合曲线，并将其中的 $\mathrm { ~ S _ { 0 } ~ } , \mathrm { ~ \beta ~ } , \mathrm { ~ \gamma ~ }$ 、最终传播范围、最大传播速率5个参数值记录下来。

$\textcircled{1}$ 潜在受众计算：潜在受众对应SIR模型中的 $\mathrm { s } _ { \mathrm { 0 } }$ ，即传播时的易感人群。$\textcircled{2}$ 传播概率计算：传播概率对应 SIR 模型中的 $\beta ,$ ，即易感状态到感染状态的状态转移概率。$\textcircled{3}$ 传播范围计算：t趋于无穷时，处于康复状态的节点有极限值，这个极限值就是所有“感染"过或者传播了新知识的个体。因此，传播范围对应 $\operatorname { R } ( { \mathfrak { t } } \to \infty )$ 0

$\textcircled{4}$ 传播速率计算：由于传播速率没有解析解，只能通过数值解获知每个时刻的传播速率。然而，传播范围依时间收敛，因此平均传播速率又没有意义，故而本文选取最大传播速率，也就是Ⅰ变化最快时的速率，作为传播速率的度量，即max(dI/dt)。在变化速率最大处附近，变化速率相对稳定，速率具有代表意义。

# 4实证研究与结果

# 4.1 数据准备

以全球最大的社交编程及代码托管网站GitHub为例，研究创新知识在虚拟社区中的传播机制。在GitHub网站上，创新成员将自己的创新成果写在信息库中(本文认为，一个信息库就是一单位的创新知识)其他创新成员通过点赞行为将该创新知识传递给更多的创新成员。本文利用GitHub的应用程序接口数据备份收集了约500万个创新成员的关注关系数据，并根据关注关系建立社会网络。此外，收集了2008年至今的全部传播历史，随机选取250个传播人数超过100的信息库，除去异常值，用于创新知识传播的研究。

# 4.2 回归模型建立

记节点的位置中心性为 $X _ { 1 }$ ，创新认可度为 $X _ { 2 }$ ，区域聚集程度为 $X _ { 3 }$ ，潜在受众为 $\mathbf { M E } _ { 1 }$ ，传播概率为 $ { \mathrm { M E } } _ { 2 }$ 传播范围为 $\mathrm { Y } _ { 1 }$ ，传播速率为 $\mathrm { Y } _ { 2 }$ ，根据研究假设和研究框架，建立如下回归模型:

$$
\begin{array} { r l } & { \mathrm { Y } _ { 1 } = \mathfrak { b } _ { 1 0 } + \mathfrak { b } _ { 1 1 } \mathrm { X } _ { 1 } + \mathfrak { c } _ { 1 } } \\ & { \mathrm { M E } _ { 1 } = \mathfrak { b } _ { 2 0 } + \mathfrak { b } _ { 2 1 } \mathrm { X } _ { 1 } + \mathfrak { c } _ { 2 } } \\ & { \mathrm { Y } _ { 1 } = \mathfrak { b } _ { 3 0 } + \mathfrak { b } _ { 3 1 } \mathrm { X } _ { 1 } + \mathfrak { b } _ { 3 2 } \mathrm { M E } _ { 1 } + \mathfrak { c } _ { 3 } } \\ & { \mathrm { Y } _ { 1 } = \mathfrak { b } _ { 4 0 } + \mathfrak { b } _ { 4 1 } \mathrm { X } _ { 2 } + \mathfrak { c } _ { 4 } } \\ & { \mathrm { M E } _ { 2 } = \mathfrak { b } _ { 5 0 } + \mathfrak { b } _ { 5 1 } \mathrm { X } _ { 2 } + \mathfrak { c } _ { 5 } } \\ & { \mathrm { Y } _ { 2 } = \mathfrak { b } _ { 6 0 } + \mathfrak { b } _ { 6 1 } \mathrm { X } _ { 2 } + \mathfrak { b } _ { 6 2 } \mathrm { M E } _ { 2 } + \mathfrak { c } _ { 6 } } \\ & { \mathrm { Y } _ { 1 } = \mathfrak { a } _ { 1 0 } + \mathfrak { a } _ { 1 1 } \mathrm { X } _ { 1 } + \mathfrak { a } _ { 1 2 } \mathrm { M E } _ { 1 } + \mathfrak { a } _ { 1 3 } \mathrm { X } _ { 3 } + \mathfrak { c } _ { 7 } } \\ & { \mathrm { Y } _ { 2 } = \mathfrak { a } _ { 2 0 } + \mathfrak { a } _ { 2 1 } \mathrm { X } _ { 2 } + \mathfrak { a } _ { 2 2 } \mathrm { M E } _ { 2 } + \mathfrak { a } _ { 2 3 } \mathrm { X } _ { 3 } + \mathfrak { c } _ { 8 } } \end{array}
$$

# 4.3 实证研究结果

对回归分析的基本假设进行检验，数据符合多重共线性等基本假设，可以用于回归分析。使用SPSSProcessMacro中的Model4对H1和H2进行中介关系检验，使用SPSS回归分析对H3a和H3b进行假设检验。

(1)H1的检验结果如表1所示，可知 $\mathsf { b } _ { 1 1 } = . 1 4$ $\mathbf { t } = 2 . 1 9 , \mathbf { p } < . 0 5$ ，位置中心性与传播范围呈正相关;$\mathsf { b } _ { 2 1 } = - . 2 8 , \mathsf { t } = 4 . 4 2 , \mathsf { p } < . 0 0 1$ ，位置中心性与潜在受众呈正相关； $\mathsf { b } _ { 3 2 } = . 4 8 , \mathsf { t } = 7 . 8 9 , \mathsf { p } < . 0 0 1$ ，潜在受众与传播范围呈正相关； $\mathsf { b } _ { 3 1 } = . 0 1 , \mathsf { t } = . 1 5 , \mathsf { p } = . 8 8$ ，引入间接效应后直接效应不再显著，因此该中介效应为完全中介效应，H1成立，即社区成员处于社区网络中的核心位置(位置中心性)可以提高创新知识的潜在受众数量，进而扩大创新知识的传播范围。

表1H1中介关系检验结果  

<html><body><table><tr><td>Outcome</td><td>Model</td><td>coeff</td><td>se</td><td>t</td><td>p</td><td>LLCI</td><td>ULCI</td></tr><tr><td>Y1(传播范围)</td><td>X1(位置中心性)</td><td>0.1441</td><td>0.0657</td><td>2.1939</td><td>0.0293</td><td>0.0147</td><td>0.2735</td></tr><tr><td>ME1(潜在受众)</td><td>X1(位置中心性)</td><td>0.2816</td><td>0.0637</td><td>4.4208</td><td>0.0000</td><td>0.1561</td><td>0.4070</td></tr><tr><td>Y1(传播范围)</td><td>ME1(潜在受众)</td><td>0.4790</td><td>0.0608</td><td>7.8852</td><td>0.0000</td><td>0.3593</td><td>0.5987</td></tr><tr><td></td><td>X1(位置中心性)</td><td>0.0092</td><td>0.0608</td><td>0.1518</td><td>0.8795</td><td>-0.1105</td><td>0.1289</td></tr></table></body></html>

(2)H2 的检验结果如表 2 所示，可知 $\mathsf { b } _ { 4 1 } = . 1 6$ $\mathbf { t } = 2 . 4 9 , \mathbf { p } < . 0 5$ ，创新认可度与传播速率呈正相关;$\mathsf { b } _ { 5 1 } = . 2 9 , \mathsf { t } = 4 . 5 2 , \mathsf { p } < . 0 0 1$ ，创新认可度与传播概率呈正相关； $\mathsf { b } _ { 6 2 } = . 2 0 , \mathsf { t } = 2 . 9 2 , \mathsf { p } < . 0 1$ ，传播概率与传播速率呈正相关; $\mathsf { b } _ { 6 1 } = . 1 1 , \mathrm { t } = 1 . 5 8 , \mathsf { p } = . 1 2$ ，引入间接效应后直接效应不再显著，因此该中介效应为完全中介效应，H2成立，即创新认可度增加了创新知识的传播概率，进而提高了创新知识的传播速率。

(3）由表3可知，在传播范围的回归模型中，区域聚集程度对应的卡方增量显著 $( \mathsf { p } { < } . 0 0 1 )$ 。区域聚集程度与传播范围呈负相关( $\mathbf { \dot { a } } _ { 1 3 } = - . 2 0 2 , \mathrm { t } = - 3 . 5 3 1 , \mathbf { p } = . 0 0 1 )$ ，H3a成立，即区域聚集减小了传播范围。由表4可知，在传播速率的回归模型中，区域聚集程度对应卡方增量显著 $( \mathsf { p } { < } . 0 0 1 )$ ，区域聚集程度与最大传播速率呈负相关( $\mathrm { \Delta a } _ { 2 3 } = - . 2 4 7 , \mathrm { t } = - 3 . 9 0 3 , \mathrm { p } < . 0 0 1 \mathrm { \Omega }$ ，H3b 成立，即区域聚集降低了传播速率。

<html><body><table><tr><td>Outcome</td><td>Model</td><td>coeff</td><td>se</td><td>t</td><td>p</td><td>LLCI</td><td>ULCI</td></tr><tr><td>Y2(传播速率)</td><td>X2(创新认可度)</td><td>0.1628</td><td>0.0655</td><td>2.4860</td><td>0.0136</td><td>0.0338</td><td>0.2918</td></tr><tr><td>ME2(传播概率)</td><td>X2(创新认可度)</td><td>0.2872</td><td>0.0636</td><td>4.5181</td><td>0.0000</td><td>0.1620</td><td>0.4125</td></tr><tr><td rowspan="2">Y2(传播速率)</td><td>ME2(传播概率)</td><td>0.1964</td><td>0.0673</td><td>2.9193</td><td>0.0039</td><td>0.0638</td><td>0.3289</td></tr><tr><td>X2(创新认可度)</td><td>0.1064</td><td>0.0673</td><td>1.5818</td><td>0.1151</td><td>-0.0261</td><td>0.2389</td></tr></table></body></html>

表2H2中介关系检验结果  

<html><body><table><tr><td>H3a因变量：传播范围</td><td>Beta</td><td>t</td><td>Sig.</td></tr><tr><td>潜在受众</td><td>.467</td><td>7.863</td><td>.000</td></tr><tr><td>位置中心性</td><td>.000</td><td>.007</td><td>.994</td></tr><tr><td>区域聚集程度</td><td>-.202</td><td>-3.531</td><td>.001</td></tr></table></body></html>

表3H3a回归结果  
表4H3b 回归结果  

<html><body><table><tr><td>H3b 因变量：传播速率</td><td>Beta</td><td>t</td><td>Sig.</td></tr><tr><td>传播概率</td><td>.183</td><td>2.804</td><td>.005</td></tr><tr><td>创新认可度</td><td>.076</td><td>1.164</td><td>.246</td></tr><tr><td>区域聚集程度</td><td>-.247</td><td>-3.903</td><td>.000</td></tr></table></body></html>

![](images/b70c59ce834e66cabb5e3fa832ee4feeda80ce123d0181ba4e2a8f69d2117517.jpg)  
总结理论模型的检验结果如图2所示：  
图2检验结果(回归系数)(注： $\ast _ { \mathrm { p } < . 0 5 }$ $\ast \ast _ { \mathrm { p } < . 0 1 }$ ${ } ^ { * * * } \mathrm { p } { } ^ { < } . 0 0 1 \rangle$

综上，统计检验的结果支持了研究假设。H1认为，位置中心性通过增加潜在受众数量扩大传播范围。Stieglitz等[27在关于Twitter的研究中发现，关注者的数量和转发次数呈正相关关系。然而，节点在网络中的重要性不仅与关注者的数量相关，还可能与这些关注者的“质量"相关。网络中的位置中心性很好地体现出创新成员的关注者的数量和这些关注者本身在网络中的重要性。结果表明，与社会媒体类似，在创新社区中位置中心性和创新认可度在创新社区中同样可以对知识传播起到积极作用。本文进一步结合传播的动态模型，证明位置中心性是通过中介变量潜在受众的数量，正向影响了传播范围。

统计检验的结果支持了H2，证明了创新认可度可以提高传播速率。此前关于微博的研究使用了回归的方法，发现信息发布者的权威性可以提高信息的转发次数[28]。本文的结果表明，创新认可度作为对创新成员权威性的一种体现，可以有效地提高创新成果的传播速率。此外，传播动态模型帮助解释该正相关关系的内在机制：当创新成果的发布者具有的创新认可度越高，接触到创新成果的创新成员越可能进一步传播该成果，因此传播速率也越大。

本文的研究结果还说明，区域聚集性会减小传播范围，并且降低最大传播速率。Lerman 等[12]在此前的研究中，通过对比信息在Twitter和Digg两个社交媒体上的传播发现，相比于Twitter,Digg用户网络节点间的联系更为密集，信息虽然在最初的传播中速度比较快，但是后期动力不足，并且整体传播范围次于Twitter。然而两个社会媒体平台可能存在除网络结构性质外的其他差异，比如信息传播效果不同可能是由参与两个社交媒体的人本身的不同导致的。本文研究对比了创新成果在同一平台上的传播效果，降低了其他差异的混杂影响，验证了在创新社区中区域聚集性与创新成果传播呈负相关关系。

# 5结语

随着互联网的发展和网络社区的大量涌现，虚拟社区中的知识传播问题得到了越来越广泛的关注。本文针对虚拟社区知识传播的特点，结合复杂网络静态性质和动态传播模型，构建了虚拟社区创新知识传播的理论模型，采用实证的方法研究了创新知识传播的动态机制。较之已有的研究，本文充分考虑了虚拟社区所具有复杂网络的结构特性同时又兼顾了虚拟社区中创新知识传播的动态过程，并在研究中使用了大量有效的实际数据，讨论了结构特性对传播效果的内在影响机制，验证并延伸了此前的研究结论，具有理论和实践意义。由于本文结论基于旨在共享和交流的社交创新社区，该机制是否适用于其他虚拟社区有待后续研究进一步分析探讨。此外，未来研究工作需要进一步探索如何通过虚拟社区结构设计、成员间的交互方式设计、社区推荐系统算法设计等方法有效提高创新成员位置中心性和创新认可度、降低区域聚集程度。

# 参考文献：

[1]Adamic L A,Glance N.The Political Blogosphere and the 2004 US Election: Divided They Blog [C].In: Proceedings of the 3rd International Workshop on Link Discovery.ACM, 2005:36-43.   
[2]Lewis K,Kaufman J,Gonzalez M,et al.Tastes,Ties,and Time:A New Social Network Dataset Using Facebook.com [J]. Social Networks,2008,30(4): 330-342.   
[3]Cha M,Mislove A,Gummadi K P.A Measurement-driven Analysis of Information Propagation in the Flickr Social Network [C]. In: Proceedings of the 18th International Conference on World Wide Web.ACM,2009:721-730.   
[4]Colizza V,Barrat A,Barthélemy M,et al.Prediction and Predictability of Global Epidemics:The Role of The Airline Transportation Network [J].Proceedings of the National Academy of Science of the United States of America,2005, 103(7): 2015-2020.   
[5] Barabäsi A L,Albert R.Emergence of Scaling in Random Networks [J]. Science,1999,286(5439): 509-512.   
[6] Adamic L A,Huberman B A.Power-law Distribution of the World Wide Web [J]. Science,2000,287(5461): 2115.   
[7]Newman M.Applied Mathematics: The Power of Design [J]. Nature,2000,405(6785): 412-413.   
[8]彭红彬，王军．虚拟社区中知识交流的特点分析——基于 CSDN 技术论坛的实证研究[J]．现代图书情报技术, 2009(4): 44-49.(Peng Hongbin,Wang Jun. Topology of the Knowledge Communication Network in Virtual Communities -Based on CSDN [J].New Technology of Library and Information Service,2009(4): 44-49.)   
[9]刘佩，林如鹏．网络问答社区“知乎”的知识分享与传播 行为研究[J].图书情报知识,2015(6):109-119.(LiuPei,Lin Rupeng. Research on Knowledge Sharing and Dissemination Behavior of Online Q&A Services: Taking Zhihu asan Example [J]. Documentation, Information and Knowledge, 2015(6): 109-119.)   
[10] Newman M E.The Structure of Scientific Collaboration Networks[J]. Proceedings of the National Academy of Sciences,2001,98(2): 404-409.   
[11] Ma M,Agarwal R.Through a Glass Darkly: Information Technology Design， Identity Verification，and Knowledge Contribution in Online Communities [J].Information Systems Research,2007,18(1): 42-67.   
[12]Lerman K,Ghosh R.Information Contagion:An Empirical Study of the Spread of News on Digg and Twitter Social Networks[OL]. arXiv: 1003.2664v1.   
[13] Bakshy E,Rosenn I,Marlow C,et al. The Role of Social Networks in Information Diffusion [C]. In: Proceedings of the 21st International Conference on World Wide Web.ACM, 2012: 519-528.   
[14]邹儒楠，于建荣．数字时代非正式学术交流特点的社会网 络分析——以小木虫生命科学论坛为例[J]．情报科学, 2015,33(7):81-86. (Zou Ru'nan,Yu Jianrong.Social Network Analysis of Informal Scholarly Commnication Characteristics in Digital Age—Take BBS.BIOON.NET for Example[J]. Information Science,2015,33(7): 81-86.)   
[15]Myers S A,Zhu C,Leskovec J. Information Diffusion and External Influence in Networks [C].In: Proceedings of the 18th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. ACM, 2012: 33-41.   
[16]Gomez-Rodriguez M,Leskovec J，Krause A. Inferring Networks of Diffusion and Influence [C].In: Proceedings of the 16th ACM SIGKDD International Conferenceon Knowledge Discovery and Data Mining. ACM,2010: 1019-1028.   
[17] Yang J,Leskovec J.Modeling Information Diffusion in Implicit Networks[C].In:Proceedingsof the10th International Conference on Data Mining (ICDM).IEEE, 2010: 599-608.   
[18] Cannarella J,Spechler JA．Epidemiological Modeling of Online Social Network Dynamics[OL]. arXiv: 1401.4208, 2014.   
[19] Zhao L,Wang Q,Cheng J,et al. Rumor Spreading Model with Consideration of Forgetting Mechanism: A Case of Online Blogging Livejournal [J].Physica A: Statistical Mechanics and its Applications,2011,390: 2619-2625.   
[20]Bettencourt L M,Cintrón-Arias A,Kaiser D I,et al. The Power of a Good Idea: Quantitative Modeling of the Spread of Ideas from Epidemiological Models [J].Physica A: Statistical Mechanics and its Applications，2006,364: 513-536.   
[21]Gruhl D,Guha R,Liben-Nowell D，et al.Information Diffusion Through Blogspace[C]. In: Proceedings of the 13th International Conference on World Wide Web.ACM,2004: 491-501.   
[22] Pastor-Satorras R,Vespignani A. Epidemic Spreading in Scale-Free Networks [J].Physical Review Letters,2001, 86(14): 3200-3203.   
[23]Girvan M,Callaway D S,Newman ME,et al. Simple Model of Epidemics with Pathogen Mutation[J].Physical Review E, 2002,65(3): 031915.   
[24]魏静．基于复杂在线网络的知识转移研究[D]．南京：南京 航空航天大学，2010.（Wei Jing．Research of Online Knowledge Transfer Based on Complex Network [J]. Nanjing: Nanjing University of Aeronautics and Astronautics, 2010.)   
[25]王晓明．微博信息传播网络的属性研究[D].太原：太原理 工大学，2014.(Wang Xiaoming.Research of Microblog Information Diffusion Network Properties [D]. Taiyuan: Taiyuan University of Technology,2014.)   
[26] 张立凡，赵凯．媒体干预下带有讨论机制的网络舆情传播 模型研究[J]．现代图书情报技术，2015(11):60-67.(Zhang Lifan,Zhao Kai. Study on the Internet Public Opinion Dissemination Model with Discussion Under the Effect of Media [J]. New Technology of Library and Information Service,2015 (11): 60-67.)   
[27] Stieglitz S,Dang-Xuan L.Political Communication and Influence Through Microblogging-An Empirical Analysis of Sentiment in Twitter Messages and Retweet Behavior [C]. In: Proceedings of the 45th Hawaii International Conference on System Science.2012: 3500-3509.   
[28] Zhang L,Peng T Q,Zhang Y P,et al. Content or Context: WhichMattersMore in Information Processingon Microblogging Sites [J]. Computers in Human Behavior, 2014,31: 242-249.   
[29]Huffaker D.Dimensions of Leadership and Social Influence in Online Communities [J].Human Communication Research, 2010,36(4): 593-617.   
[30]Castillo C,Mendoza M,Poblete B.Information Credibility on Twitter [C].In: Proceedings of the 2Oth International Conference onWorldWideWeb.ACM,2011:675-684.   
[31]刘丽群，宋咏梅．虚拟社区中知识交流的行为动机及影响 因素研究[J]．新闻与传播研究，2007，14(1):43-51.(Liu Liqun， Song Yongmei. A Study on Motivation and Influencing Factors in the Knowledge Communication of the Virtual Community [J]. Journalism and Communication. 2007,14(1): 43-51.)   
[32]Wu X,Liu Z.How Community Structure Influences Epidemic Spread in Social Networks [J].Physica A: Statistical Mechanics and its Applications,2008,387:623-630.   
[33]Newman M.Networks: An Introduction [M].Oxford University Press,2010.

# 作者贡献声明：

叶腾：提出和设计研究命题，获取与分析数据，论文写作;  
韩丽川：提出研究思路，设计研究方案，论文修订;  
邢春晓：提出实验模型，论文修订;  
张妍：实验分析，论文修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail: zxhui0@163.com。[1]叶腾．gh.csv.基于复杂网络的虚拟社区创新知识传播机制研究.

收稿日期:2016-02-29   
收修改稿日期:2016-04-22

# Knowledge Dissemination Mechanism in Virtual Communities: Case Study Based on Complex Network Theory

Ye Teng’Han Lichuan’Xing Chunxiao 2,3Zhang Yan 2,3 1(Antai College of Economics and Management, Shanghai JiaoTong University, Shanghai 20o30,China) 2(Research Institute of Information Technology, Tsinghua University, Beijing 10o084, China) 3(Tsinghua NationalLaboratory for Information Scienceand Technology,Tsinghua University,Beijing 10o084,Chin

Abstract: [Objective] This paper studies the mechanism of knowledge disemination in virutal communities with the help of a new theoretical model.[Methods]First, we collected data from the virtual community GitHub.Second,we examined these data with social network and regresionanalysis techniques.Finally，weexplored the influenceof community member’s online position,physical location as well as atitude towards innovation to the knowledge dissemination speed and scope.[Results] We found that the number of online community members could change the scope of knowledge dissemination.The atitude towards innovation could affct the knowledge dissemination speed. The clustering extent posed negative efects to the knowledge dissmination scope and speed.[Limitations]This study was based onone virtual community.More research is needed to generalize the findings.[Conclusions] This study provides some strategical suggestion to virtual community management as wellas members’ knowledge sharng and innovation activities.

Keywords: Collaborative innovation Complex network Virtual communities Knowledge dissemination

# ProQuest书库提供更多内容并进行技术创新

近日,ProQuest进一步丰富了其书库，添加了新的印刷品和电子书，同时还简化了读者对内容的访问流程。除了在电子书中心平台推出其"Acces-to-Own"电子书采购模型，该公司还在 OASIS 平台推出了新的电子书订阅服务，即在线的电子书目和扩展的印刷本图书和电子图书采购方案。所有这些都旨在改进图书馆员的工作流程。

在过去的几个月里，ProQuest推出了新的电子书订阅服务，帮助图书馆建设有针对性的、有价值的馆藏。其订阅来源中的193所大学出版商提供了近24000种高质量图书，包括哈佛大学出版社、美国天主教大学出版社和约翰·霍普金斯大学出版社等。电子参考书订阅则增加了很多需求量高的参考内容，包括 500多份参考书、手册、百科全书、指南、词典等，其中很多是首次订阅就能访问的。

ProQuest还为其旗舰电子书订阅产品增加了很多图书，光是Academic Complete资源库就增加了3000多本，这些新书包括18 种优秀学术成果和来自Wiley 出版社的近1000 种电子书。此外,Collge Complete 资源库增加了1000 多本图书,PublicLibrary Complete 资源库增加了 800 多本图书，Schols & Educators Complete 资源库增加了30 多本图书。这些资源库由ProQuest的在职馆员进行维护，遵循质量高于数量的标准，确保每本图书都能被最大范围地使用。

为了进一步简化电子书的采购和访问流程，ProQuest 推出了电子书预览中心，这是一个在线目录，允许图书馆员和读者检索 85万多本来自世界各大出版商的权威图书所组成的大型的跨学科的电子书馆藏。预览的同时，用户能够轻松下载自己感兴趣的图书列表，也可以将图书进行过滤并以主题、特色或是出版商等维度分类展现。

在线采购和选择信息系统(Online Acquisitions and Selection Information System,OASIS)是 ProQuest 免费的基于 Web 的印刷图书和电子图书检索、选择和订购系统。其采购功能也有了更新：改善了用户体验，并简化了图书采购工作流。具体的改进包括：更快速地处理电子书订单、更好的用户界面，以及OASIS 和AIma的API整合，从而实现更快速的订单信息传送和处理。牛津出版社等多家著名出版社很快将通过OASIS 来提供他们的电子书，为图书馆提供了更多的选择。

(编译自:http:/www.proquest.com/about/news/2016/ProQuest-Books-Delivers-More-Content-and-Technology-Innovatio.html)

(本刊讯)