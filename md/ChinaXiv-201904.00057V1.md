# 基于微博的UVFR谣言传播模型研究及仿真

肖晓艳，刘万平，王越，范海波(重庆理工大学 计算机科学与工程学院，重庆 400054)

摘要：社交网络的迅速发展，使得对网络谣言的管控变得愈加重要。针对微博网络谣言的传播机制进行了研究，根据其传播特征将微博谣言的受众用户划分为未知者、浏览者、转发者、评论者四类，从而构建一个UVFR网络谣言传播模型。利用该模型分析主要参数对传播过程的影响，提出相应的控制策略。模型的主要特点是重新定义了谣言传播规则和传播动力学方程，使得传播过程的描述更加符合微博用户行为。使用多主体仿真平台在无标度网络结构下对谣言的传播行为进行了仿真研究。通过将仿真结果与新浪微博真实数据进行比较，证实了所得结论的合理性、有效性。仿真实验结果表明，初始传播节点越多，谣言传播的速度越快；转发概率越大，谣言传播的范围越广。

关键词：微博；无标度网络；谣言传播；多主体仿真 中图分类号：TP391.9 doi:10.19734/j.issn.1001-3695.2018.10.0813

Research and simulation of uvfr rumor propagation model based on Microblog

Xiao Xiaoyan, Liu Wanping †, Wang Yue, Fan Haibo (SchoolofComputerScience&Engineering,Chongqing UniversityofTechnology,Chongqing 40o054,China)

Abstract: With therapiddevelopmentofsocial networks,thecontrolof network rumors becomes moreand more important. This paper studied the disemination mechanism of rumors on microblog networks.According to its propagation characteristics,thepaperdividedtheaudienceusersofmicroblogrumors into fourcategories:Unknown,Viewer,Forwarder and Reviewer,thus constructinganetwork rumor propagation modelof UVFR.Itusedthe model toanalyze theinfluenceof the main parameters on the propagation processand proposed the corrsponding control strategies.The main featureof the modelredefined the rules of rumor propagation and the propagation dynamicsequation，which made the propagation formula more in line with thereal use habitsof micro-blogusers.The paper used a multi-agent simulation platform to simulatethe spreadofrumors in scale-freenetwork structure,andcomparedthe simulationresults with thereal dataof Sina Weibo toverify therationalityand validityoftheconclusions.Thesimulationresults showthatthe more initial propagation nodes,the faster the rumor spread,and the greater the forwarding probability,the wider range the rumor spread.

Key words: micro-blog; scale-free network; rumor propagation; multi-agent simulation

# 0 引言

在信息爆炸的时代，随着在线社交网络等新型媒体大量出现，谣言传播的成本越来越小。所谓谣言，是指关于对人民群众所关注的事件、社会或自然现象等问题未经证实的描述和解释，是通过人与人之间进行传播的不确定信息。微博作为人们的第一舆论场，因其时效性和随意性的特点，逐渐成为人们发布和获取最新信息的重要渠道。然而微博信息传播速度快、范围广、监管不严等特征，使微博成为各类谣言事件传播的温床。第40次《中国互联网络发展状况统计报告》数据显示，截至2017年6月，中国网民规模来到7.51亿，互联网普及率为 $54 . 3 \%$ ；手机网民规模达7.24亿，移动互联网已渗透到人们生活的方方面面1，这给保护信息安全及维护社交网络良好的舆论环境带来了极大的挑战。《2017年度微博辟谣数据报告》统计了2017年的微博辟谣数据，一年中，微博官方有效处理不实信息2.8万余条，标记不实信息1064条[2]。微博信息传播机制的本质是，它把人类的社会关系引入到了信息的传播中，使社会关系成为影响信息传播效果的一个重要因素。由于微博传播更多的依赖社会网络这一传播媒介，所以微博上的信息传播行为并不是一种单纯的信息传播活动，它体现了网民的社会关系和这背后关于价值的、心理的各种不同层面的文化认同。因此，研究在线社交网络中的谣言传播特点，掌握其传播规律，从而进行有效地免疫和控制，是一个非常值得关注的问题。

国内的相关学者们对微博谣言传播的研究始于2010年，很多研究都是从用户心理学和信息传播学的角度来分析微博谣言的传播，很少涉及到模型的定量研究。由于谣言在微博网络中的传播与传染病传播具有相似性，所以学者们对谣言的研究大部分都借鉴了SI、SIS和SIR等传染病传播模型的研究方法和思路[3\~5]。后来随着复杂网络研究的兴起，为了刻画网络拓扑结构对网络谣言传播的影响，Zanette[6首先将复杂网络理论应用于谣言传播研究，分别基于静态和动态小世界网络建立了谣言传播系统动力学模型，证实了谣言传播临界值的存在；朱冠桦等人[7考虑到社交网络中的谣言具有全局信息特征，其从众效应具有个体差异性，以及社交网络的规模和拓扑特性（均质和异质网络）对谣言传播的影响；

Moreno等人[8基于无标度网络建立了谣言传播模型，证实了不同个体相信谣言的概率有差异，而不同网络拓扑结构对谣言传播也会产生影响；沈贤[9围绕无标度网络的谣言传播特性进行研究，通过分析现实世界中网络谣言的传播特性和方式，提出一种HKASI模型，建立了基于HKASI模型的动力学方程组。微博作为新兴的社交网络平台，其独特的信息传播机制和用户关系网络也成为影响谣言传播的主要因素。宋之杰等人[10]通过分析微博用户获取以及传播谣言的行为特征，考虑微博谣言获取的非常规渠道以及谣言传播的滞后性等特点，基于传染病动力学，构建了适用于微博网络的SCCIR谣言传播模型；王亚奇等人[I]基于复杂网络理论研究微博用户关系网络的内部特征，提出一种微博用户关系网络演化模型，借助于平均场理论，分析该演化模型的拓扑统计特性；刘咏梅等人[12]基于传染病的基础模型，将受众扩展为五类（无知者、接触者、传播者、沉寂者、失去兴趣者)，引入兴趣衰减系数描述个体多次接触谣言时转发兴趣降低状态，同时考虑了个体只会转发一次的现实状况。众所周知，谣言的传播是一种社会现象，更是一种典型的社会群体心理行为的体现。谭振华等人[13]借鉴引力学思想，从用户和谣言信息两个角度出发，以用户为核心，基于用户间的关系、信息在用户间的传播关系、谣言接触率、转发率等对用户影响力、谣言影响力进行建模，对谣言信息的传播进行量化，并充分考虑用户的个性化特征，构建相应的建模与分析函数；王筱莉等人[14]充分考虑了用户具有怀疑特性，提出了更加符合社会实际情况的具有怀疑机制的SIQR谣言传播模型，并分析了模型的稳定性；王彦本等人[15]根据 Ebbinghaus 遗忘规律，研究遗忘机制对谣言传播的影响规律，建立了以遗忘率为指数函数形式的谣言传播模型。

但是，目前很多类似SIR模型的谣言传播模型的假设与现实情况都大相径庭，如免疫个体永久免疫、传播谣言的个体不管经过多久都在传播谣言等，这种假设并不能反映网络群体对待谣言的真实心理，真实的情况应该是谣言对个体产生一定的累计效应，是与历史有关的，此类真实的群众心理应该在模型中有所体现[16]。另外，由于微博网络用户在个体生活、知识背景等方面的差异，传统的SIR模型并不能完全表征微博网络谣言传播过程中用户的所有状态[17]。因此，有必要根据现实情况对经典SIR传染病模型进行改进，对微博网络中谣言的受众人群和感染状态进行重新分类。

综上，本文根据微博网络的用户行为特征和微博谣言的传播机制以及微博网络的拓扑结构，引入未知者、浏览者、转发者和评论者四种状态，构造新的微博谣言传播模型。考虑了无标度网络环境，通过计算机多主体仿真实验，对微博网络中的谣言传播机制进行仿真研究，并分析模型中某些主要参数变化对谣言传播过程及各状态峰值的影响，在此基础上提出相应的控制策略。

# 1 微博谣言的传播机制

通过近几年社交网络的不断发展，微博已经成为中国网民的主流应用之一，庞大的用户规模进一步巩固了其网络舆论传播核心的地位。移动终端的使用，使得微博摆脱了定时定点上网的限制，极大地增强了微博用户的真实性、地域性和交互的实时性[18]。新浪2017年Q3 微博财报数据显示，截至2017年9月，微博月活跃用户共3.76亿，与2016年同期相比增长 $2 7 \%$ ,其中移动端占比达 $92 \%$ ；日活跃用户达到1.65亿，较去年同期增长 $2 5 \% [ 1 ]$ 。微博终端软件与用户手机号的绑定保证了微博网络用户的真实性；位置信息的选择性引入，给用户带来了地域信息等多样化的社交网络服务；移动终端利用移动通信设备（如手机）的移动性及便携性等特点，让用户在网络覆盖的空间里，随时随地地进行沟通和交流，“始终在线”的特性，为用户提供了实时的信息交互，使用户可以及时的对谣言信息进行转发和评论。

新浪微博采取的是单向跟随的人际关系，微博用户之间的关注与被关注关系形成了独特的信息分享与传播模式[19]。用户通过互相“关注”，就可成为彼此的粉丝，通过留言、评论、转发等方式，实现互动和交流。微博的传播路径一般有两个：一个是“粉丝式路径”，即某一被关注的用户发布信息后，其所有粉丝都可接收信息；另一个是“转发式路径”，即用户甲对用户乙的微博感兴趣，进行转发，甲的粉丝将实时收到信息，从而实现近乎裂变式的信息传播。这种传播方式蕴涵着巨大的舆论威力。对谣言信息感到好奇或是疑惑的用户借助微博传播的迅捷性，将个人的意见与观点迅速在微博平台上得以交换，交换后的意见，形成共同的群体意见，从而形成群体式舆论，这种群体式舆论和微博其他用户形成的其他群体舆论进一步交换、讨论和交流，形成更大范围的公共舆论[20]。近来发生的“严书记女儿”事件、鸿茅药酒事件、全国严查棋牌室60岁以下一律逮捕事件、空姐深夜滴滴打车遇害事件、小男孩狂犬病发作学狗叫事件、微信付款码截图盗取财产事件等，微博成为这些事件传播话题产生及传播的最主要场所，平台传播量占比高达 $8 0 . 0 0 \%$ 以上，可见其影响力之大。

当用户浏览到某条谣言微博时，可能采取的动作有以下四种：转发、评论、转发并评论、不转发也不评论。转发可以直接将谣言信息传播出去，是最高效的传播行为；评论不直接传播谣言，但会增加谣言的热度，也会激发部分浏览者的从众心理等，以此间接的影响谣言的传播；转发并评论的用户，将转载的谣言微博作为传播的背景，加上自己的评论后进行转发，在信息增值的同时构成了新一轮的传播，转发量和评论为话题增强了传播效果和影响力；既不转发也不评论的用户无法传递谣言信息，不能起到传播的效果，暂时不予考虑。微博谣言传播示意图如图1所示。

![](images/d28efb6680d94de23a5836507a426f1207a010ba4be5ae21d03b719b2437185e.jpg)  
图1微博谣言传播示意图  
Fig.1Sketch map of rumor dissemination on micro-blog

# 2 模型建立

# 2.1模型的基本假设

本文借助新浪微博平台传播的网络谣言为研究对象，将模型涉及到的软硬件条件、受众用户、交互规则假定如下：

a）在微博谣言传播过程中，本文假设不存在微博卡顿或闪退等硬件或网络环境问题。

b）在微博的使用过程中，由于关注的人数多且杂乱，用户会选择将关注人分组，同一时间只能选择查看其中一组关注人的消息，有可能错过一些谣言信息，所以本文假设微博用户不设置关注人分组，只要是关注人发布的微博信息，用户都能以某个概率浏览到其内容。

c）事实上，用户在发布或转发微博信息时，可以选择该条信息为公开状态（对所有关注该用户的粉丝可见）或只对部分选择的用户可见。微博用户发布微博是为了能够随时随地记录自己对某件事的观点、分享自己内心最真实的想法，并且通过粉丝的留言和评论等行为来进行交流、探讨，因此绝大部分用户是愿意公开发布微博信息的。所以本文假设用户发布（或转发）的微博信息皆为公开状态。

d)根据微博网络谣言的传播机制以及传播特征，将微博网络谣言的受众用户划分为四种状态，即未知状态U（尚未接触微博谣言，unknown）、浏览状态V（已浏览到微博谣言，viewer）、转发状态F（转发即传播微博谣言，forwarder）和评论状态R(评论微博谣言但暂时不传播，reviewer)，其传播过程如图2所示。

![](images/ebc013834094d4e2f7fe36cf758fe3424dfba4ddc148140e52c91836c84df967.jpg)

图2描述的微博网络谣言传播模型的交互规则如下：

a）微博用户在注册之后，会通过软件的提示关注自己感兴趣的用户或去搜寻通信录列表，用户可选择关注通信录列表里已注册微博的用户。关注之后，用户将在微博的首页看到关注人的微博信息。假定在单位时间内，未知者U在微博关注列表里浏览到谣言的概率为 $\alpha$ ，此时未知者U会转换为浏览者V。

b）假定浏览者V看到谣言后的反映为转发传播或评论，不考虑忽略谣言事件的情况。浏览者可能会立即转发该谣言信息，或是怀有疑虑先写下自己的评论表达态度但暂时不转发，观望其他用户对此谣言的反映。此时浏览者V在单位时间内，会以概率 $\beta$ 转换为转发者F，或以概率转换为评论者R。

c）评论者在评论谣言信息时，将会看到他人对该事件的评论内容与其所持有的态度。假定存在社会加强正向效应，即一件事情的发生、发展受到了社会行为的刺激，促进了其正向发展。随着评论数量的增长，在单位时间内，部分评论者R在看到他人的评论内容后，将因从众心理或猎奇心理等原因，以概率 $\delta$ 转换为转发者F。

d)转发者与评论者在海量的信息轰炸下，可能会遗忘或对该谣言信息失去兴趣，也可能看到其他关注者发布的相似谣言信息。因此，本文假定微博用户在对谣言进行转发传播、评论一段时间后，由于遗忘效应及兴趣衰减效应，或重新浏览到另一条相似内容的谣言，转发者与评论者将重新转换为未知者，重新参与该网络谣言的传播过程。此时转发者F在单位时间内以概率 $\varepsilon$ 转换为未知者U，评论者R在单位时间内以概率 $\theta$ 转换为未知者U。

# 2.2模型的构建

根据上述微博谣言传播模型的基本假设和交互规则，将微博网络谣言传播的动力学模型构建为

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { d U ( t ) } { d t } = - \alpha U ( t ) V ( t ) + \varepsilon F ( t ) + \theta R ( t ) } \\ { \displaystyle \frac { d V ( t ) } { d t } = \alpha U ( t ) V ( t ) - \beta V ( t ) - \gamma V ( t ) } \\ { \displaystyle \frac { d F ( t ) } { d t } = \beta V ( t ) + \delta R ( t ) - \varepsilon F ( t ) } \\ { \displaystyle \frac { d R ( t ) } { d t } = \gamma V ( t ) - \delta R ( t ) - \theta R ( t ) } \end{array} \right.
$$

其中： $U ( t )$ 、 $V ( t )$ 、 $F ( t )$ 和 $R ( t )$ 分别表示未知者、浏览者、转发者和评论者在时刻 $t$ 的数量； $\alpha , \beta , \gamma , \delta , \varepsilon , \theta$ 分别表示未知者转换为浏览者的概率、浏览者转换为转发者的概率、浏览者转换为评论者的概率、评论者转换为转发者的概率、转发者转换为未知者的概率和评论者转换为未知者的概率。特别地，未知者U转换为浏览者V时，考虑到网络的拓扑结构，所以在 $t$ 时刻的转换量为 $\alpha U ( t ) V ( t )$ 0

假设微博网络中全部用户数量为 $N$ ，那么在任一时刻，$U ( t ) + V ( t ) + F ( t ) + R ( t ) = N$ 。

# 3 基于Netlogo 的仿真实验

根据上述微博的基本假设与微博网络谣言的传播特征，利用NetLogo软件进行多主体仿真实验。每个主体都代表一个微博用户，主体共有四种状态，分别为未知状态U（unknown）、浏览状态V（viewer）、转发状态F（forwarder）和评论状态R(reviewer)。初始状态下，主体都处于未知状态。

关于微博网络的构造，本文使用了无标度网络的生长模型，首先构造了1000个节点的无标度网络。图3描述了无标度网络的生长过程。从图3(a)\~(e)可以明显地看出无标度网络中优先连接和“富者愈富”的特点。

![](images/07c2863132815e5a0a8174e6d9ad0aaa4275ff5b39840f78b1ff35d6a6bec4f5.jpg)  
图2微博谣言传播过程中用户状态转移示意图 Fig.2Diagram of user state transition in spreading of micro-blog rumors   
图3无标度网络生成过程 Fig.3Scale-free network generation process

以下为生成无标度网络的核心算法：$\scriptstyle \mathsf { n } = \theta$ ：while( $\scriptstyle \mathbf { n } < 1 0 0 0 ^ { \cdot }$ 0{创建一个节点a，设为未知状态(白色)；if( $\texttt { n } > \texttt { 1 }$ ）{以概率 $w$ 创建节点a到节点i的连接，设为绿色；广}

优先连接：一个新的节点与一个已经存在的节点 $i$ 相连的概率w与节点i的度 $\mathbf { k } _ { i }$ 之间的关系为$w = k _ { i } / \left( k _ { 1 } + k _ { 2 } + k _ { 3 } + \cdots + k _ { n } \right)$ ，其中 $n$ 为网络中的节点的总个数。

微博网络谣言传播仿真实验的规则如下：

a）随机选择 $m$ 个节点作为初始浏览者。b)在每一个时间步，浏览者以概率 $\beta$ 接受谣言成为转发者或者以概率》成为评论者，评论者以概率 $\delta$ 成为转发者。接着，转发者向她周围连接着的所有未知者传播谣言，未知者以概率 $\alpha$ 浏览到谣言成为浏览者。c）转发者与评论者分别以概率 $\varepsilon$ 和 $\theta$ 转换成未知者。d)重复规则b)和c，直到所有转发者周围不存在未知者时，整个传播过程结束。

![](images/fe061679d644968aa683eaeb71597375bf743ff24c7873047744e47f4dc51964.jpg)  
图4无标度网络仿真实验的传播过程 Fig.4Propagation process of scale-free network simulation experiment

图4为该仿真实验的局部图。图中白色节点表示未知者，  
绿色表示浏览者，红色表示转发者，黄色表示评论者。以下  
为谣言在无标度网络上传播的核心算法：while(1){与转发节点 $F$ 相连的未知节点 $U$ 以概率 $\alpha$ 转换为浏览节点 $V$ ；浏览节点 $V$ 以概率 $\beta$ 转换为转发节点 $F$ ，以概率／转换为评论节点$R$ ：评论节点 $R$ 以概率 $\delta$ 转换为转发节点 $F$ ，以概率 $\theta$ 转换为未知节点$U$ ;转发节点 $F$ 以概率 $\varepsilon$ 转换为未知节点 $U$ ：}

发传播人数迅速增加，30日之后增加的速度减缓并逐渐趋于平稳。为进行对比实验，选取参数令 $\scriptstyle \alpha = 0 . 8$ ， $\beta { = } 0 . 5$ ， $\scriptstyle \gamma = 0 . 4$ ，$\scriptstyle { \delta = 0 . 2 }$ ， $\scriptstyle { \varepsilon = \theta = 0 . 0 1 }$ ，并根据3月27日的传播量设定初始传播者为2。对比实验结果如图5所示。从图5可以看出，真实数据的转发量趋势与仿真数据的转发量趋势基本吻合，即该模型能较好的描述现实生活中的网络谣言传播进程，因此本模型具有一定的有效性。

![](images/bc09027af1bd3ecd1e24b2e0ff39c4193fb12af0c5139dbf7817fd4a191a25db.jpg)  
图5真实数据与仿真数据的对比结果  
Fig.5Comparison of real data and simulated data

本文将上述的仿真实验以不同的影响因素分别进行仿真，并且记录了不同影响因素的传播过程。

# 3.2初始传播节点的数量对传播过程的影响

本文进行了传播节点初值敏感性对比仿真实验，分别把初始传播节点的数量设定为10、50和100，分别进行三次实验，并记录四种用户状态变换的曲线，UVFR模型在不同初始传播节点数量下的传播结果如图6所示。

# 3.1与真实案例的对比

由新浪舆情通发布的介于2018年3月27日到4月11日的有关“景甜”的微博传播效果分析中，转发量趋势图如图5红色折线所示。初始27日有2条微博，随后开始转发传播。可以看出，27日至30日是谣言传播的快速爆发期，转时，传播达到稳定的时间大约为1550个时间步；而在 (b)中初始传播节点的数量为50，传播达到稳定的时间约为1250个时间步；在(c)中初始传播节点的数量为100，传播达到稳定的时间仅约900个时间步。这组实验的结果充分体现了初始传播节点的数量对谣言传播的促进作用。所谓“三人成虎”，这一点和社会心理学关于谣言传播的观点相符[2],这个结论有助于各官方媒体在微博社交网络中有效消除网络谣言负面影响的工作。

![](images/25a1e9a64f9fc7da4cc82a5f504728c2be2b19b93072419715e634058e9f88d5.jpg)  
图6UVFR模型在无标度网络中，不同F(O)下的传播结果Fig.6Propagation results of UVFR model in scale-free networks withdifferent F(O)在图6(a)中本文可以看到，在初始传播节点的数量为10

# 3.3转发概率 $\beta$ 对传播过程的影响

与上述实验相同，本文分别进行三次不同转发概率的对比实验并分别记录四种用户状态变换的曲线，把初始传播节点的数量设为50，分别把转发概率 $\beta$ 设定为0.3、0.5和0.8，UVFR模型在不同转发概率下的传播结果如图7所示。

![](images/5e416d48e994fc1496f8d2c62139df183113767e2889f4e602971b31e7f2a9c7.jpg)  
图7UVFR模型在无标度网络中，不同 $\beta$ 下的传播结果Fig.7Propagation results of UVFR model under different $\beta$ inscale-free networks

在图7(a)中本文可以发现，在转发概率 $\beta$ 为0.3时，传播达到稳定时，转发者的比例大约为 $34 \%$ ；而在 (b)中转发概率 $\beta$ 为0.5，转发者的平衡比例约为 $45 \%$ ；在(c)中转发概率 $\beta$ 为0.8，转发者的平衡比例约为 $47 \%$ 。据图7所示的数据对比分析可知，转发概率 $\beta$ 显著影响谣言的覆盖范围，转发概率 $\beta$ 越大，最终达到平衡时转发者所占的比例越多，对社会产生的影响范围也越大，而转发概率对于谣言传播达到平衡的时间的影响并不显著。

# 4 结束语

力学方程，使得传播公式更加符合微博用户的使用习惯；b)考虑到微博用户在大量的信息轰炸下，可能会遗忘或对某个谣言信息失去兴趣。因此，转发者与评论者将以一定的概率重新转换为未知者，使传播过程得以不断延续。在仿真实验中，借助多主体仿真平台对比了初始传播节点数量和转发概率 $\beta$ 在无标度网络中的传播效果。结果发现，初始传播节点越多，谣言传播的速度越快；转发概率越大，谣言传播的范围越广。就像谚语“谣言止于智者”所说的一样，本文可以通过发布完整准确的信息，降低人们对谣言信息的疑虑，或者对谣言中的疑点给出专业的说明，使人们降低对谣言的好奇心理等，减小初始传播节点的数量和转发概率。在对微博信息的管控中，这些措施可以有效地控制谣言的传播。

本文考虑了在微博社交网络中谣言传播的特征，构建了一个UVFR 谣言传播模型。本模型的主要特点是：a)根据微博的传播机制以及网络的拓扑结构定义了传播规则和传播动

但是同样需要指出的是，本文对微博谣言的研究并不很完整，还存在一定的局限。现实中一条微博能涉及到的人数非常巨大，由于仿真软件及硬件的条件限制，生成网络的规模有所限制，只能根据节点的比例大致得到微博网络谣言传播的过程。还有在社交网络上的谣言形式往往多种多样，用户很难作出理性的判断来选择接受或拒绝谣言，浏览到谣言的次数和传播者的权重往往成了用户作出判断的重要依据。另外，本文的仿真实验生成的无标度网络是静态的，网络节点达到1000后就不再变化，而现实中的在线社交网络是动态变化的，也不一定是严格的无标度网络[22]。在后续的研究中，将利用复杂网络理论和最优控制理论[23,24]，研究复杂网络上的谣言传播动力学行为以及基于传播模型的网络谣言控制策略。此外，还将考虑更真实更细致的用户心理状态和随机的用户接受阈值，构建微博谣言传播的动态网络环境，为微博平台和各官方媒体监控谣言、抑制谣言和辟谣等工作提供一定的建议。

# 参考文献：

[1]新浪微博数据中心.2017微博用户发展报告 [EB/OL].(2017-12-25) [2018-05-23]. http://data. weibo. com/report/reportdetail?id=404&sudaref=www.baidu.com.   
[2]微博辟谣．2017 年度微博辟谣数据报告[EB/OL].(2018-01-22) [2018-05-23]. https://weibo. com/1866405545/FFwn4EnNV?from=page_1002061866405545_profil e&wvr=6&mod=weibotime&type $\mathrel { \mathop : }$ comment#_rnd1545203670303.   
[3]张芳，司光亚，罗批．谣言传播模型研究综述[J]．复杂系统与复杂 性科学,2009,6(4):1-11.(Zhang Fang,Si Guangya,Luo Pi.A review ofrumor dissemination models [J].Complex Systems and Complexity Science,2009,6(4): 1-11.)   
[4]Liu Wanping，Wu Xiao,Yang Wu,et al.Modeling cyber rumor spreading over mobile social networks:Acompartment approach [J]. Applied Mathematics andComputation,2019,343:214-229.   
[5]Liu Wanping, Zhong Shouming,Modeling and analyzing the dynamic spreading of epidemic malware by a network eigenvalue method [J]. Applied Mathematical Modelling,2018,63:491-507.   
[6]Zanette D H. Critical behavior of propagation on small-world networks [J].Physical Review E,Statistical,Nonlinear,and Soft Matter Physics, 2001,64(1): 050901.   
[7]朱冠桦，蒋国平，夏玲玲，等．社交网络上从众现象对谣言传播影响 的研究[J].计算机科学,2016,43(2):135-139.(Zhu Guanhua,Jiang Guoping,Xia Lingling,et al.A study on the impact of conformity on rumor dissemination on social networks [J].Computer Science,2016, 43 (2): 135-139.)   
[8]Moreno Y,Nekovee M,Pacheco AF,Dynamics of rumor spreading in

complex networks [J].Physical Review E,Statistical, Nonlinear,and

Soft matter Physics,2004,69(2): 066130.   
[9]沈贤．基于无标度网络的谣言传播模型与控制策略的研究[D]．南 京：南京邮电大学，2013．（Shen Xian．Research on rumor dissemination model and control strategy based on scaleless network[D]. Nanjing:Nanjing University of Posts and Telecommunications,2013.)   
[10]宋之杰，王建，石蕊．基于无标度网络的突发事件微博谣言传播研 究[J]．情报杂志,2015(12):111-115.(Song Zhijie,Wang Jian,Shi Rui.Research on rumor dissemination of emergency microblog based on scale-free network [J]. Intelligence Magazine,2015 (12): 111-115.）   
[11]王亚奇，王静，杨海滨．基于复杂网络理论的微博用户关系网络演 化模型研究[J].物理学报，2014，63(20):404-410.(Wang Yaqi, Wang Jing,Yang Haibin. Research on evolution model of microblog user relation network based on complex network theory [J].Journal of Physics,2014,63 (20):404-410.)   
[12]刘咏梅，彭琳，赵振军．基于小世界网络的微博谣言传播演进研究 [J]．复杂系统与复杂性科学,2014,11(4):54-60.(Liu Yongmei,Peng Lin,Zhao Zhenjun.Research on evolution of rumor dissemination in microblog based on small world network [J].Complex Systems and Complexity Science,2014,11 (4): 54-60.)   
[13]谭振华，时迎成，石楠翔，等．基于引力学的在线社交网络空间谣言 传播分析模型[J]．计算机研究与发展，2017，54(11)：2586-2599. (Tan Zhenhua,Shi Yingcheng,Shi Nanxiang,et al.An analysis model of spatial rumor dissemination in online social networks based on gravitation [J]. Computer Research and Development,2017,54 (11): 2586-2599.)   
[14]王筱莉，赵来军．社会网络中具有怀疑机制的谣言传播模型[J]．上 海理工大学学报,2012,34(5):424-428.(Wang Xiaoli, Zhao Laijun. Rumor dissemination model with suspicion mechanism in social networks [J].Journal of Shanghai University of Technology,2012,34 (5): 424-428.)   
[15]王彦本，蔡皖东．社交网络中考虑遗忘机制的谣言传播[J].西北工 业大学学报，2016,34(2):349-355.(Wang Yanben,Cai Wandong. Rumor dissemination considering forgeting mechanism in social networks [J]. Journal of Northwest Polytechnic University,2016,34 (2): 349-355.)   
[16]石琰鑫.社交媒体平台上的谣言传播现象——以微博谣言传播为例 [J]．新媒体研究,2018.(Shi Yanxin.Rumor dissemination on social media platform: a case study of rumor dissemination on microblog [J]. New Media Research,2018.)   
[17]杨晓春，丁一．基于新浪微博的地震谣言传播特点分析[J].科技资 讯,2017 (33): 237-237.(Yang Xiaochun,Ding Yi.Analysis of the characteristics of earthquake rumor dissemination based on Sina Weibo [J].Technology Information,2017 (33): 237-237.)   
[18]王玉祥，乔秀全，李晓峰，等．上下文感知的移动社交网络服务选择 机制研究[J].计算机学报,2010,33(11):2126-2135.(Wang Yuxiang, Qiao Xiuquan,Li Xiaofeng,et al. Research on context-aware service selection mechanism in mobile social networks [J].Journal of Computer Science,2010,33 (11):2126-2135.)   
[19]刘兴亮．微博的传播机制及未来发展思考[J]．新闻与写作,2010 (3): 32-34.(Liu Xingliang. The communication mechanism and future development of microblog [J].News and Writing,2010 (3):32-34.)   
[20]吴海园．微博在舆论中的传播机制与对策措施[J]．中国市场，2011 (52):139-140.(Wu Haiyuan．The communication mechanism and countermeasure of microblog in public opinion [J]. Chinese Market, 2011 (52): 139-140.)   
[21] Krech D.The psychology of rumor [J].Jornal of Daonal Yhology,1948 (2): 171-173.   
[22] Liu Wanping,Liu Chao,Liu Xiaoyang,et al. Modeling the spread of malware with the influence of heterogeneous immunization [J].Applied Mathematical Modelling,2016,40 (4): 3141-3152.   
[23]Liu Wanping,Zhong Shouming.Web malware spreadmodelling and optimal control strategies [J]. Scientific Reports,2017,7: 42308.   
[24] Liu Wanping,Liu Chao,Yang Zheng,et al.Modeling the propagation of mobile malware on complex networks [J].Communications in Nonlinear Science and Numerical Simulation,2016,37: 249-264.