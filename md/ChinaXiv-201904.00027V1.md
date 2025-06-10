# 基于IBU模型的信息传播

范海波，刘万平，肖晓艳(重庆理工大学 计算机科学与工程学院，重庆 400054)

摘要：网络用户对信息假性的判定是信息传播过程中的关键阶段，大众群体对所获信息的个人评价以及对信息内容真实性的判定，将直接影响信息的传播广度和传播效果。考虑到发布信息用户的可信度差异对信息传播过程具有一定的影响，针对真假信息传播的广度和效果，提出了一个新的IBU模型，研究了信息内容真实性以及发布信息用户的可信度对信息传播动力学过程的影响。通过MATLAB 仿真对该模型的传播效果进行实验，实验结果表明，无论发布信息用户的可信度有多大，与信息可信本身无关，只与信息内容本身是否可信有关；信息发布者可信度越大，对于信息传播的时间就越长；相反，信息发布者的可信度越低，传播时间越短，但并不会改变信息内容真假的性质。研究成果为相关职能部门在信息管控方面提供了理论基础。

关键词：用户可信度；信息传播；传播效果；网络谣言中图分类号：TP309 doi:10.19734/j.issn.1001-3695.2018.10.0832

InformationdisseminationbasedonIBUmodel

Fan Haibo, Liu Wanping†, Xiao Xiaoyan (SchoolofComputer Science & Engineering,Chongqing University of Technology,Chongqing 40o54,China)

Abstract:Judgmentof network users on information falseness isakey stage in the process of information dissemination. The personal evaluationof the informationobtainedbythe masesandthe determinationof theauthenticityof the informationcontent willdirectlyafect thebreadthand spreadof the information.Considering thatthecredibilitydifference of usersof publishing information has certain influence on the information dissemination process,a new IBU model is proposed forthe breadthand effectof trueandfalse information dissemination,and the authenticityof information content and thecredibilityof userswho forward information on thedynamics of information dissemination are studied.The propagationeffectof the modelis tested byMatlab simulation.The experimentalresults showthatno materthe credibility oftheuser who publishes the information,ithas nothing todo withthecredibilityof the information itself,onlyelatedto whetherthe informationcontentitselfiscredible;thecredibilityoftheinformationpublisherThelarger thetime,thelonger theinformation istransmited;onthecontrary,the lowerthecredibilityof theinformation publisher,theshorter the propagationtime,butitdoes notchange thetrueand false natureofthe information content.Theresearch results provide a theoretical basis for relevant functional departments in information management and control.

Key words: credibility of users; information dissemination; communication effect; network rumors

# 0 引言

在线社交网络中存在着许多偏激和虚假的内容（消息)，微博也被大量的垃圾内容和谣言信息严重污染。甚至，当今社会的在线新闻媒体也被大量没有被证实的“新闻”所充斥[1]，这些现象直接影响到了主流媒体。正如Liu 等人[2-4]所研究的恶意软件在网络上的传播一样，如果是恶意信息在网络上传播，那么将会给人们的生活带来巨大的恶劣影响。因此，信息内容可信与否的研究具有重大的历史意义，可以减少人们对谣言信息的传播，降低不可信信息对社会的影响。蒋盛益等人[5在微博中对信息可信度分析做了简要的描述和对微博信息可信度的研究以及微博信息可信度分析等相关概念进行了界定。现如今对微博信息(内容)可信度研究的主要有微博信息内容检测[6]，谣言检测[7和话题新闻的可信度分析[8]。同时Liu等人在文献[9，17]中提出了网络特征对恶意软件传播的影响，因此考虑了网络结构的特征对现实网络的任意连接网络上的传播的影响。在国外，Howell等人[10]将海量数字化虚假内容信息列为影响现代社会发展的重大威胁之一。Gupta等人[11]的研究结果表明：在Twitter中有将近 $52 \%$ 的内容是确定可信的、 $3 5 \%$ 的内容是大致可信的、 $13 \%$ 的内容是确定不可信的。然而，在张明新[12]的可信度理论中发现：在不同的媒介和不同类型的信息之间，可信度存在显著差异。网络和广播可信度显著低于电视和报纸；网上的新闻和参考信息最为可信，其次是娱乐信息，商业信息是最不可信的。Liu 等人[13]提出了一种用于新的网络谣言仓室隔离模型，并将其谣言的行为纳入了网络模型传播的动态特性，解决了模型系统的平衡稳定性。Fogg[14]提出一个评判互联网信息可信度过程的"关注一释义"模型，该模型认为人们对信息往往是先关注后释义，即：当判断在线信息的可信度时，人们首先会观察到一些需要关注的信息要素，然后再对这些元素进行解释和释义。在现实生活运中，对于商业活动营销的策略，利用结构方程建模的方法研究了品牌微博信息内容与品牌微博评论内容对品牌微博可信度的影响机制[15]。

目前，针对上述问题的研究虽已取得一定的成果，但是面对多样化的语言及其风格变化，对信息可信度理论的分析及方法等的研究仍然有很多的缺陷。因此，这对未来研究信息传播方向的相关人员来说仍具有很大的挑战。本文从信息的可信度出发，研究当信息传播开始时，无论无知者发布的原始信息是否可信，仅仅针对人的可信度判断信息是可信；而后随着人们对信息认识的加深以及对知识的获取，有一定的知识储备之后，逐渐转换为可信信息用户和不可信信息用户。但最终的结果显示：当不可信用户向可信用户转换的概率大于反向转换的概率时，最终达到平衡后的状态是认为信息可信的用户数量大于认为信息不可信的用户；相反，当可信用户向不可信用户转换的概率大于反向转换的概率时，那么认为信息不可信的用户数量就会大于认为信息可信的用户数量。

# 1 理论模型

在“狼来了”这则故事中，可以运用贝叶斯概率问题来判断小孩可信度的问题。本文假设：两个互斥事件H和-H，其发生概率分别为P(H)和P(-H)，H和-H存在一个共同的特征，特征D在上述两个互斥事件中发生的概率分别为 $\mathrm { { \cal P } ( D | H ) }$ 和 $\mathrm { P ( D | \mathrm { - } H ) }$ ，所以由贝叶斯推理可知：

$$
P ( H / D ) = { \frac { P ( H ) P ( D / H ) } { P ( H ) P ( D / H ) + P ( - H ) P ( D / - H ) } }
$$

假设 $\mathrm { ~ D ~ }$ 表示“小孩说谎"事件， $\mathrm { ~ H ~ }$ 表示“小孩可信”事件，刚开始村民对小孩的可信程度为 $\mathrm { P ( H ) } { = } 0 . 8$ ，那么 $\mathrm { P } ( \mathrm { - H } ) { = } 0 . 2$ 可信孩子说谎的可能性为 $\mathrm { { P ( D | H ) } = 0 . 1 }$ ，不可信孩子说谎的可能性为 $\mathrm { P ( D | \mathrm { - } H ) } { = } 0 . 5$ 。由此可知，村民在小孩第一次说谎后，对小孩的可信度如表1所示，且小孩说谎与不说谎后的可信度变化趋势对比如图1所示。

表1小孩可信度对比表  
Table1 Comparison of child credibility   

<html><body><table><tr><td>事件</td><td>可信概率</td><td>不可信概率</td></tr><tr><td>可信小孩</td><td>P(H)=0.8</td><td>P(-H)=0.2</td></tr><tr><td>可信小孩说谎</td><td>P(D|H)=0.2</td><td>P(D|-H)=0.5</td></tr><tr><td>可信小孩第一次说谎</td><td>P(D|H)=0.444</td><td>P(D|-H)=0.556</td></tr><tr><td>可信小孩第二次说谎</td><td>P(D|H)=0.138</td><td>P(D|-H)=0.872</td></tr><tr><td>可信小孩第三次说谎</td><td>P(D|H)=0.031</td><td>P(D|-H)=0.969</td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

![](images/3cacf27dcc1474eaef38f9edfc3d55e5275afe93b56b93a94fdee647b61ef8fe.jpg)  
图1小孩说谎与不说谎后的可信度变化趋势  
Fig.1Trends in credibility of children lying and not lying

以上故事说明，小孩的可信度会随着他说谎次数的增加而逐渐下降，导致没有人愿意相信他说的话，结果只能被狼吃掉。

如今，在社交网络的信息传播过程中，考虑信息本身的可信度来建立仓室模型。将能够收到信息的网络用户看做一个整体，用户总数记为N。最初均认为所有网络用户都是无知者（ignorant)；随着信息在网络上的传播，这些用户可进一步分为两类：认为信息可信的用户（believed）以及认为信息不可信的用户（unbelieved)。基于此，本文定义了信息本身可信度的衡量基准，以此来判别信息发布者发布该条信息时，认定该条信息真假性的概率，提出一个新的仓室模型（IBU模型）来研究信息在传播过程中的动力学行为。

因此，基于以上考虑，可以将网络中的用户状态分为三类：

a)无知者(ignorant)。该状态指在网络中，当一条信息尚未传播时，在朋友圈没看到信息的用户；或者，当信息发布之后，不知道该条信息的真假且还未作出判断的用户。

b)发布可信信息的用户(believed)。当微信用户在朋友圈看到信息后，作出判断，认为该微信好友发布的信息是可信的，即将该好友用户认作信息可信用户状态

c)发布不可信信息的用户(unbelieved)。当微信用户看到信息后作出判断，认为该微信好友发布的信息是不可信的，即将该好友用户认作信息不可可信用户状态；

信息传播过程中，网络节点状态转换示意图如图2所示。

![](images/0bcfdd00161d8a0784d32b1b00fb7e72ebbf554fd3e9ed12148ff81b0ff3d506.jpg)  
图2网络节点状态转变示意图  
Fig.2Schematic diagram of network node state transition

图2确定的信息传播过程的交互规则如下：

假设某人某一时刻，在朋友圈公开发布了一条信息，朋友圈中的好友在没有看到该条信息之前，可以将朋友圈中的好友看做是无知者I（ignorant)。

假设信息在该朋友圈中都是可以被看到的，正如文献[18]中提出的C类连通度网络模型一一推广型连通度网络模型。那么，在以t时刻为起点的单位时间内，该条信息被朋友圈的好友看到，好友认为该信息是可信的概率为 $\alpha$ ，将该条信息转发出去；与此相反，朋友圈的好友认为该条信息是不可信的概率为 $\beta$ ，则不对该信息进行转发传播。

随着时间的推移，自身学习的知识及认识的积累，朋友圈可信好友用户与不可信好友用户之间的状态都会发生改变。因此，假设在以t时刻为起点的单位时间内，可信用户认为该条信息是不可信的概率为》，那么此时表现出，可信信息用户转换为不可信信息用户，然后对已发布在朋友圈中的信息进行删除或者屏蔽；与此同时，不可信信息用户认为该条信息是可信的概率为 $\delta$ ，那么不可信信息用户就转换为可信信息用户，然后对未转发的信息进行转发或者评论。

因此，根据以上基于信息内容真假模型的交互规则建立如下动力学微分方程组：

$$
\left\{ \begin{array} { c } { \displaystyle \frac { d I ( t ) } { d t } = - I ( t ) [ \alpha B ( t ) + \beta U ( t ) ] } \\ { \displaystyle \frac { d B ( t ) } { d t } = \alpha B ( t ) I ( t ) - \gamma B ( t ) + \delta U ( t ) } \\ { \displaystyle \frac { d U ( t ) } { d t } = \beta U ( t ) I ( t ) - \delta U ( t ) + \gamma B ( t ) } \end{array} \right.
$$

其中： $I ( t )$ 、 $B ( t )$ 、 $U ( t )$ 分别表示未知者用户、可信信息用户、不可信信息用户在 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 时刻分别占朋友圈总人数的比例； $I _ { 0 }$ 、$B _ { 0 }$ 、 $U _ { 0 }$ 表示初始状态下各状态人数的值，且均为非负数。

在以上信息传播过程的交互规则中，关于朋友圈好友对信息发布人的可信度衡量，可以定义为：假设朋友圈的好友对该信息发布人的信任度为 $T _ { \mathrm { i } } ( 0 \le T _ { \mathrm { i } } \le 1 )$ ，当朋友圈中的好友看到该信息时，朋友圈好友可以通过对该条消息的发布人的直观印象（对发布人的信任度 $T _ { \mathrm { i } } ( 0 \le T _ { \mathrm { i } } \le 1 )$ )，来直接的判断该信息是否可信，那么该朋友圈中的好友对发布信息人的平均可信度概率为

$$
T _ { \mathrm { i } } { = } \frac { 1 } { N - 1 } \sum _ { \mathrm { j } = 1 } ^ { N - 1 } T _ { j  i } \qquad \mathrm { ( i \ne j ) }
$$

不可信的概率为

$$
\overline { { T _ { \mathrm { i } } } } = 1 - T _ { \mathrm { i } } = 1 - \frac { 1 } { N - 1 } \sum _ { \mathrm { j = 1 } } ^ { N - 1 } T _ { j  i } \quad \mathrm { ( i \neq j ) }
$$

因此，针对信息发布人的可信度，可以将式(2)改为基于信息发布用户的可信度的模型建立方程组如下：

$$
\left\{ \begin{array} { c } { \displaystyle \frac { d I ( t ) } { d t } = - I ( t ) [ T B ( t ) + \overline { { T } } U ( t ) ] } \\ { \displaystyle \frac { d B ( t ) } { d t } = T B ( t ) I ( t ) - \gamma B ( t ) + \delta U ( t ) } \\ { \displaystyle \frac { d U ( t ) } { d t } = \overline { { T } } U ( t ) - \delta U ( t ) + \gamma B ( t ) } \end{array} \right.
$$

那么在该模型中，朋友圈好友对信息发布用户所发布信息的可信度概率为

$$
T ^ { \prime } { = } { \frac { { \alpha } + { T } } { 2 } } ( 0 { \leq } T ^ { \prime } { \leq } 1 )
$$

信息发布用户发布的不可信信息的概率为

$$
T ^ { \prime \prime } { = } \frac { \beta + \overline { { T } } } { 2 } ( 0 \leq T ^ { \prime } { \leq } 1 )
$$

因此考虑朋友圈信息发布用户的可信度对信息内容的影响可以对式(2)改进为

$$
\left\{ \begin{array} { c } { \displaystyle \frac { d I ( t ) } { d t } = - I ( t ) [ T ^ { \prime } B ( t ) + T ^ { \prime \prime } U ( t ) ] } \\ { \displaystyle \frac { d B ( t ) } { d t } = T ^ { \prime } B ( t ) I ( t ) - \gamma B ( t ) + \delta U ( t ) } \\ { \displaystyle \frac { d U ( t ) } { d t } = T ^ { \prime } U ( t ) I ( t ) - \delta U ( t ) + \gamma B ( t ) } \end{array} \right.
$$

那么在网络信息的传播过程中，经过一段时间后，信息在网络传播中达到平衡，即此时网络中的三种状态（I、B、U）比例基本保持稳定不再变化，此时网络将处于平衡态。因此假设该系统在传播初始时满足以下条件：$I ( t ) + B ( t ) + U ( t ) = 1 \ ; B ( 0 ) = B _ { 0 } \ ; U ( 0 ) = U _ { 0 }$ 。根据图2中网络节点状态转换可知，可 $I ( 0 ) = I _ { 0 }$ 以将该系统分为2个不同的仓室，即

$$
\begin{array} { l } { \displaystyle { \left\{ \frac { d B ( t ) } { d t } = \alpha B ( t ) ( 1 - B ( t ) - U ( t ) ) - \gamma B ( t ) + \delta U ( t ) \right. } } \\ { \displaystyle { \left. \frac { d U ( t ) } { d t } = \beta U ( t ) ( 1 - B ( t ) - U ( t ) ) - \delta U ( t ) + \gamma B ( t ) \right. } } \end{array}
$$

同时在网络模型达到平衡时的解为

$$
\left\{ \begin{array} { r l } { \cfrac { d I ( t ) } { d t } = 0 } \\ { \cfrac { d B ( t ) } { d t } = 0 } \\ { \cfrac { d U ( t ) } { d t } = 0 } \end{array} \right. \Leftrightarrow \left\{ \begin{array} { r l } { - I ( t ) [ \alpha B ( t ) + \beta U ( t ) ] = 0 } & { { } } \\ { \alpha B ( t ) I ( t ) - \gamma B ( t ) + \delta U ( t ) = 0 } \\ { \beta U ( t ) I ( t ) - \delta U ( t ) + \gamma B ( t ) = 0 } & { { } } \\ { { } } & { { } } \end{array} \right.
$$

设平衡点 ${ \mathrm { E } } { = } ( \mathrm { I } , \mathrm { B } , \mathrm { U } ) ^ { \mathrm { T } }$ 求解上式，可以得到是上面方程组的解为

$$
E _ { 0 } = ( 1 , 0 , 0 )
$$

$$
E _ { 1 } = ( 0 , \frac { \delta } { \gamma + \delta } , \frac { \gamma } { \gamma + \delta } )
$$

$$
\Bigg \vert E _ { 2 } = ( \frac { \alpha \delta + \beta \gamma } { \alpha \beta } , \frac { \alpha \delta - \alpha \beta + \beta \gamma } { \alpha ( \alpha - \beta ) } , \frac { \alpha \beta - \alpha \delta - \beta \gamma } { \beta ( \alpha - \beta ) } )
$$

则在式(11)求得IBU信息传播模型的平衡点有三个值$E _ { 0 } , E _ { 1 } , E _ { 2 }$ ，达到平衡后，网络信息传播属于一个动态平衡。

再由传染病传播的“阈值定理”得到在信息传播中的传播阈值 ${ \bf R } _ { 0 }$ 。即根据Driessche 和Warmough提出的计算一般仓室模型阈值的方法[16]，可以计算出模型式(3)的传播阈值$R _ { 0 } = \operatorname* { m a x } \left\{ \frac { \alpha + \delta } { \gamma } , \frac { \beta + \gamma } { \delta } \right\} \circ$

在上述的描述中，在无知者、可信信息用户与不可信信息用户的转换过程中，人们随着时间的变化获取相关的信息，考虑到每个人的学习能力及对信息获取情况的差异，暂时将自我学习率定义为一个定值1，根据已具有的信息辨别能力，可以自我判断该条信息是否可信。同时，在可信信息用户与不可信信息用户之间的转换都是以一定的概率进行相互的转换，但在现实网络当中，两者之间的转换是一个动态变化的过程。在整个系统中，考虑了人的心理变化情况，所有的人是都可以持有自己的观点并进行选择信息是否可信的，在没有进行验证信息真假时，这种选择只有两种，一种是可信信息（认为该条信息是可信的)，另外一种就是不可信信息（认为该条信息是不可信的）。

# 2 实验数值仿真结果分析

根据已建立的模型和规则，利用MATLAB软件进行数值仿真实验，来验证该模型是否与模型的交互规则相符合。

1)初始时，在理想特殊状态下，假设 $\alpha$ 和 $\beta$ 满足 $\alpha + \beta { =                 } 1$

$\gamma = 0 . 0 1$ ， $\delta = 0 . 3$ ， $I , B , U$ 的初始值分别为 $I _ { 0 } = 0 . 9 5$ ，$B _ { 0 } = 0 . 0 5$ ， $U _ { 0 } = 0$ 。那么可以分析满足假设的情况下，随着 $\alpha$ 值的增大(相反 $\beta$ 的值在减小， $\beta = 1 - \alpha$ )，以此来分析信息在该模型(IBU 模型)下传播，对模型中各状态随时间变化的影响。

a）分别在 $\alpha = 0 , \alpha = 0 . 5 , \alpha = 1$ 条件下时观察 IBU 三种状态在不同的 $\alpha$ 值下的演化。图3(a)\~(c)显示结果可以看出I,B 和U的状态最终达到平衡时，三种状态在系统中的占比是相同的；而且，从图3中可以看出I状态的比例一直递减，B状态的比例一直递增，最终达到稳定平衡。而U状态的比例在图3(a)中是先增后减，与(b)和(c)的曲线缓慢增长的曲线走势完全不一样。这说明了在IBU模型中，初始状态下将I状态全部转换为U状态，致使U状态增长达到最大值后，由于U状态与B状态之间转换有一定的概率 $\delta = 0 . 3$ ，虽然B状态与U 状态之间也有一定的概率 $\gamma = 0 . 0 1$ ，但由于 $\delta \gg \gamma$ ，所以最终在图3(a)中U的状态出现先增后减的曲线。这与本文模型的假设是符合的。当系统达到平衡时，I、B、U各状态在系统中的占比为0、0.97、0.03，此时系统的状态处在平衡。

b)从图3的三个子图中可以看出，由于 $\alpha$ 值的改变，使得信息在传播过程中，改变了信息的传播过程，致使在图3(a)中U状态出现增长达到最大值后衰减到稳定值，但不会改变信息在传播过程中达到稳定时的各状态的比例。

图4的三个子图分别显示了在不同 $\alpha$ 值情况下的，系统达到稳定时，系统耗时t的变化的曲线对比情况。通过对比图4(a)\~4(c)可以观察到， $\scriptstyle { \alpha = 0 }$ 时的系统达到平衡时的用时$T _ { \mathrm { a } } = 3 0 \mathrm { s }$ ； $\scriptstyle \alpha = 0 . 5$ 时， $T _ { \mathrm { b } } = 1 5 \mathrm { s }$ ； $\scriptstyle \alpha = 1$ 时， $T _ { \mathrm { c } } { = } 7 . 5 \mathrm { s }$ 。由此可知，当信息传播时，随着 $\alpha$ 值的改变，系统达到稳定平衡时的时间是呈现出倍数关系的，这也同样的可以说明在IBU模型中 $\alpha$ 值的增加会加快系统稳定平衡时的时间，呈现出倍数关系。在IBU模型中无知者用户I转换为信息可信用户B和信息不可信用户U的状态转换图，由于B、U状态的转换概率是给定值，再根据 $R _ { 0 } = m a x \left\{ \frac { \alpha + \delta } { \gamma } , \frac { \beta + \gamma } { \delta } \right\}$ 满足传播阈值判断，该模型最终达到平衡时，信息是否在网络上传播，以及可以决定系统传播的方向。

![](images/4699de5ae567046c1c8628a6a5ba23f2f680da9f500ca4d2a0deba385d67f44f.jpg)

但是这都只能改变信息传播过程系统各仓室达到平衡时的时间，但最终不会影响各状态在系统中的比例。只是加速了系统达到平衡时，系统收敛的时间。

![](images/778acf0f9ddd4c28e48ed7369553cd01d858722625eb3edbf4269391aa069558.jpg)  
IBU模型中I、B、U状态随时间t的变化图

![](images/cc306ecbc058da1b9448b9db23ba3f3ac3664dbe3ff5c73e5b7d277fb7edcca2.jpg)  
图3IBU 模型中I、B、U状态随时间t的变化图Fig.3Change of I,B,U state with time tin IBU model  
图5不同参数值下I状态随时间变化图

Fig.5Shows the change of I state with time under different parameter values.

![](images/9baf374ecc7b00547590ef89a7c1c4f9f821cd5cfb47544a05f938e68067a69f.jpg)  
图4IBU模型中，各状态达到平衡时的时间t图Fig.4Time t diagram when each state reaches equilibrium in the IBUmodel  
图6不同参数值下B状态随时间变化图 Fig.6Shows the change of B state with time under different parameter values.

从图5和6中可以清楚的看到，当 $\alpha$ 和 $\beta$ 满足 $\alpha + \beta = 1$ 时，随着 $\alpha$ 值的不断增大，图5中的I状态和图6中的B状态都很明显的都很快的达到平衡点。那么说明在该系统中，系统达到平衡时间会随着 $\alpha$ 的增大而减小，或者说随着 $\alpha$ 的增大会加快该系统平衡的时间消耗。

2）在其他条件不变情况下，假设 $\alpha$ 和 $\beta$ 不满足 $\alpha + \beta = 1$

假设 $\scriptstyle \alpha = 0 . 4$ 时， $\beta$ 取任意值，IBU模型中I状态随时间变化的曲线图如图7(a)所示；同理在图7(b)中，假设 $\beta { = } 0 . 4$ 时，$\alpha$ 任意值，I状态随时间变化的情况。在图7(a)中很明显地说明了在 $\alpha$ 的给定情况下，随着 $\beta$ 的值的增大，但是系统中I状态随时间变化的情况基本没有变化，或者变化很小。同时在图7(b)中很明显的说明了在 $\beta$ 的给定情况下，随着 $\alpha$ 的值的增大，系统中I状态随时间变化的情况幅度很大。以上经过图7(a)(b)两图的对比说明了在该模型中，在其他参数不变的情况下， $\alpha$ 对可信信息用户的影响较大，可以影响信息在传播过程中时间的长短，而 $\beta$ 的值对可信信息用户的影响很小，或者基本没有影响。同样在针对单个因素（人的本身可信度或者信息本身可信度）分析时，刚好都满足1）中的一种特殊的情况。但当同时考虑发布信息的人和信息本身的可信度时满足2）中的情况。

![](images/064e36f9e59d85db1b77180a52429b0b0a7d43d636fc452757a972023fcae7fd.jpg)  
图7(a) $\scriptstyle \alpha = 0 . 4$ 时， $\beta$ 的取值与I状态的变化 (b)图中 $\beta { = } 0 . 4$ 时， $\alpha$ 的取值与I状态的变化  
Fig.7(a) $\scriptstyle \alpha = 0 . 4$ ，the value of $\beta$ and the change of I state (b） inthe figure $\beta { = } 0 . 4$ ,the value of $\alpha$ and the change of Istate

综上所述，如果只考虑单个因素对该信息传播模型的影响，基本上变化不大。在传播过程中针对单因素考虑时，系统各状态的随时间变化的情况不会因为因素的不同而导致结果不同。但是考虑多因素时，很明显地，在图7(a)(b)两图很明显地说明了，当假设对人的可信度一定时，信息内容的可信度对传播的影响很大，在这里图7(b)很好地说明这个情况。同时当信息内容的可信度一定时，人的可信度对信息的传播影响很小，基本没有影响。但是又根据1）中特殊情况下，人的可信度会影响信息在朋友圈中的传播过程，很明显的，系统平衡的时间会因人的可信度的增大而减小；即人的可信度会影响系统收敛时间的长短，但不会改变信息真假的性质。

# 3 结束语

本文以《伊索寓言》中的一篇文章引出信息可信以及人的可信与否，根据信息传播的特点，由此提出基于信息传播的IBU模型。根据现实当中的可信信息用户与不可信信息用户之间的转换，基本上能够将信息分为两大类。之所以将对信息真假难分的无知者分成可信信息用户与不可信信息用户，是因为人们对信息的认识以及知识的储备不足，导致对信息的真假分辨不明。

在该实验中，仿真结果表明：该模型能够基本地符合信息在社交网络传播时的特征，能够将信息分为对立的两部分。通过单位时间内的固定转换率，可信信息用户与不可信息用户之间的变化显示了信息在传播过程当中是动态的，最终在系统当中达到稳定的状态。事实上这和真实信息网络传播过程是一致的。无论在原始信息的可信概率（0\~1）从小变大的过程中，最终的平衡结果是一样的。说明信息可信与否，与发布信息的人是否可信无关，与信息本身是否可信有关；而且用户主观态度对信息的可信概率会影响信息传播的过程，增加（或减少）传播过程的时间，但与最终的结果没有关系。

本论文模型的不足之处，只考虑了未知者用户分成了两类（可信信息用户与不可信信息用户)，没有考虑朋友圈中的好友可能认为信息可能持有怀疑的用户，保持中立的角色。还有在学习过程当中，每个人的学习吸收情况（学习率）不一样，学习知识的容量是随着时间积累变化的，所以学习情况是一个随时间变化的函数。所以综上，研究信息可信与否仍有很大的挑战，同时这也给信息传播提供了一个更深的研究方向，也对研究信息管控的相关人员对信息辨别提供了理论性依据。

# 参考文献：

[1]Hardalov M,Koychev I,Nakov P.In search of credible news [C]//Proc of International Conference on Artificial Intelligence: Methodology, Systems,and Applications.Berlin: Springer,2016:172-180.   
[2]Liu Wanping，Zhong Shouming.A novel dynamic model for web malware spreading over scale-free networks [J].Physica A:Statistical Mechanics and its Applications,2018,505:848-863.   
[3]Liu Wanping,Zhong Shouming.Web malware spread modelling and optimal control strategies [J]. Scientific Reports,2O17,7(1): 42308.   
[4]Liu Wanping,Liu Chao,Yang Zheng,et al.Modeling the propagation of mobile malware on complex networks [J].Communications in Nonlinear Science & Numerical Simulation,2016,37:249-264.   
[5]蒋盛益，陈东沂，庞观松，等．微博信息可信度分析研究综述[J]. 图书情报工作,2013,57(12):136-142.(Jiang Shengyi,Chen Dongyi, Pang Guansong，et al.Research Review of Information Credibility Analysis on Microblog [J].Library and Information Service,2013, 57(12): 136-142.)   
[6]Jain P,Rodrigues T,Magno G, et al.Cross-pollination of information in online social media: a case study on popular social networks [C]// Proc of the 3rd IEEE International Conference on Privacy, Security,Risk and Trust and the 3rd IEEE International Conference on Social Computing. Piscataway,NJ:IEEE Press,2011:477-482.   
[7]Liu Xiaomo,Nourbakhsh Armineh,Li Quanzhi,et al.Real-time rumor debunking on twitter [C]//Proc of the 24th ACM International on Conference on Information and Knowledge Management.New York: ACMPress,2015:1867-1870.   
[8]Shu Kai, Sliva Amy,Wang Suhang,et al.Fake news detection on social media:a data mining perspective [J].ACM SIGKDD Explorations Newsletter,2017,19(1): 22-36.   
[9]Liu Wanping,Zhong Shouming.Modeling and analyzing the dynamic spreading of epidemic malware by a network eigenvalue method [J]. Applied Mathematical Modelling,2018,63:491-507.   
[10] HowellL.,Bessi A,Caldarelli G,et al. Social determinants of content selection in the age of (mis）information [C]//Proc of International Conference on Social Informatics.Cham: Springer, 2O14:259-268.   
[11] Gupta A，Kumaraguru P,Castillo C,et al.Tweetcred:Real-time credibility assessment of content on twitter [C]//Proc of International Conference on Social Informatics.Cham: Springer,2014: 228-243.   
[12]张明新．网络信息的可信度研究：网民的视角[J]．新闻与传播研究, 2005(2):17-27.(Zhang Mingxin. Research into Internet Information Credibility:The Internet User’s Perspective [J].Journalism& Communication,2005(2):17-27.)   
[13]Liu Wanping，Wu Xiao，Yang Wu，et al.Modeling cyber rumor spreading over mobile social networks:a compartment approach [J]. Applied Mathematics and Computation,2019,343:214-229.   
[14]Fogg B J.Prominence-interpretation theory:Explaining how people assess credibility online [C]//Extended Abstracts on Human Factors in Computing Systems.New York:ACM Press,2003:722-723.   
[15]杨学成，葛婷婷，兰冰．品牌微博可信度影响因素研究[J].山西财 经大学学报,2013,35(10): 68-80.(Yang Xuecheng,Ge Tingting,Lan Bing.Research on Influential Factors of the Brand Microblog Credibility [J].Joumal of Shanxi Finance and Economics University, 2013,35(10):68-80.)   
[16] Van den Driessche P,Watmough J.Reproduction numbersand sub-threshold endemic equilibria for compartmental models of disease transmission [J].Mathematical biosciences,20O2,18O(1-2):29-48.   
[17]Liu Wanping,Liu Chao,Liu Xiaoyang,et al.Modeling the spread of malware with the influence of heterogeneous immunization [J].Applied mathematical modelling,2016,40(4): 3141-3152.   
[18]阎春宁，张欢欢，刘瑞辉．微信网络的连通度模型机制设计[J]．复 杂系统与复杂性科学，2015,12(4):50-5.（Yan Chunning，Zhang Huanhuan,Liu Ruihui.Mechanism Design of Connectivity Model in Wechat Network[J].Complex Systems and Complexity Science.2015, 12(4): 50-5.).