# 基于第三方回收模式考虑互惠偏好的闭环供应链决策分析

谢萍萍，李芳(上海理工大学 管理学院，上海 200090)

摘要：研究制造商委托第三方进行产品回收模式，考虑制造商与零售商之间具有互惠偏好特征，以及这种互惠偏好特征对闭环供应链成员的利润及效用的影响，并利用 Stackelberg 博弈模型对成员决策进行分析。最后使用数值仿真进行证明。研究表明，制造商与零售商之间的互惠偏好行为对闭环供应链系统利润是有利的，而零售商产品销售价格与制造商对零售商的互惠偏好行为呈负相关，第三方产品的回收率与制造商对零售商的互惠偏好行为呈正相关，零售商对制造商的互惠偏好行为对整个系统的影响效果不明显。

关键词：闭环供应链；委托回收；互惠偏好；Stackelberg 博弈 中图分类号：F274 doi:10.3969/j.issn.1001-3695.2018.01.0067

# Decision analysis of closed loop supply chain based on third party recycling model considering reciprocal preference

Xie Pingping†,Li Fang (Management School,University ofShanghai for Science& Technology,Shanghai 20oo90,China)

Abstract:To research that the manufacturer entrust the third party torecycle products.Thispaper studied thereciprocal preference characteristics between manufacturersandretailers.Itanalyzed the efectof mutual preferencecharacteristics for profitand utilityof theclosed-loop suplychain members.Itused the Stackelberg game model toanalyse the decisionof members.Finally,itusednumericalsimulationtoproveit.Researchshows thatthereciprocalpreferencebehaviorbetweenthe manufacturerandtheretailer is favorable for the profitofclosed-lopsupplychain,and there areanegativecorelationof reciprocal preferencebehaviorof manufacturertoproducts’sellngpriceofretailer,andthereareapositivecorelationof reciprocal preferencebehaviorofmanufacturer totherecoveryrateofthird party.Theeffectoftheretailer'sreciprocalpreference on the whole system is not obvious.

Key Words: closed-loop supply chain; entrustment recovery; reciprocal preference; stackelberg game

# 0 引言

随着科技的高速发展以及消费者的需求越来越多样化，如今的产品更新换代的速度越来越快，而产品的生命周期却越来越短，被人们淘汰和废弃的产品急剧增加。与此同时，地球的资源日益减少，人们对可持续发展的呼声越来越高。作为实现可持续发展的主要途径，废旧产品的回收再利用、再制造已经成为人们关注的热点问题。

目前闭环供应链管理相关内容引起了国内外的广泛关注。对其研究主要体现在如下几个方面：

a）基于回收渠道的角度。Savaskan 等人[1研究了各决策方在不同回收渠道下的最佳决策，这些回收渠道模式涵盖分销商负责回收、第三方负责回收以及制造商负责回收；舒秘等人[2]考虑有产能约束下的制造商生产，建立了闭环供应链中再制造回收渠道决策的Stackelberg博弈模型，得出了三种不同回收渠道下的零售价格、回收率以及供应链上制造商和零售商利润，研究了制造商的生产能力限度对回收渠道选择的影响。Karakayali等人[3分析了制造商主导或者回收商主导、垂直纳什均衡研究以及集中式决策等不同渠道权力结构下的逆向供应链的定价策略；高鹏等人4分析了考虑不同权力结构的独立再制造商技术创新策略影响，建立以及分析原制造商为领导(OL)、再制造商为领导(IRL)、无领导(NL)模式下的研发创新模型。

b）基于供应链制度角度。Giannoccaro 等人[5研究了三级供应链（其中包括制造商、经销商以及分销商）中利用收入共享契约的供应链协调办法，并通过分析发现调整供应链契约的参数，能够提高供应链的运行效率，增加供应链中各个节点成员的盈利。

c）基于政府规制的角度。王哲等人6通过建立由政府、制造商和分销商以及回收处理商组成的三阶段决策博弈模型，以此来研究政府规制对双渠道和双责任闭环供应链的影响。王玉燕等人7探讨了在政府进行宏观调控的情况下，闭环供应链系统如何应对突发事件的问题。

d)基于扰动角度。韩小花等人[8在需求和成本同时进行扰动的情况下，分析了一个制造商和两个互相竞争的零售商组合成的闭环供应链系统，这其中的最优协调机制的设计以及生产决策问题。

e)基于库存控制角度。初叶萍等人[9]应用切换控制理论研究混合切换库存控制策略。

以上的研究大多是集中在决策主体是理性的角度进行考虑，然而现实生活中的企业并非完全理性的，他们往往会有将一些行为偏好的因素考虑到决策中。姚锋敏等人10分析了由一个制造商、两个互相竞争的零售商和一个第三方回收商组成的闭环供应链系统，考虑公平关切行为对闭环供应链最佳策略的影响，并分别在两个竞争零售商公平关切和公平中性情况下建立了闭环供应链的决策分析模型，对这两种不同情况下的均衡结果作了对比；张克勇等人[11率先在闭环供应链中考虑公平关切因素，探讨了公平关切行为对闭环供应链的废旧产品回收量、产品定价策略及系统利润分配的影响；同时他又研究了制造商与零售商互惠偏好下考虑制造商进行回收的运作模式下闭环供应链定价策略[12]。Du等人[13针对供应链中销售商具有互惠偏好行为特征而供应商不具有和两者都具有互惠偏好的行为特征两种情况，研究了考虑互惠偏好行为的系统均衡协调以及供应链系统成员决策问题。

第三方回收模式的情况下，制造商不必自己承担产品的相关回收工作，而是通过委托第三方进行废旧产品的回收，如此一来制造商无须在产品的回收环节投入大量的人力和物力，而是将产品的回收责任进行转移，让第三方代替执行。这样做不仅制造商可以减少回收网络的投入成本，专注于自己的核心竞争力，同时也可以充分发挥第三方企业的专业化优势。这种回收模式的未来发展空间非常大，是将来的发展的必然趋势，因此考虑第三方回收是必要的选择。

基于此，本文针对已有文献中考虑互惠偏好的行为特征而忽略第三方进行产品回收的情形，探讨制造商，零售商和第三方回收商组成的闭环供应链的在考虑互惠偏好情况下的决策分析问题。

# 1 模型描述与基本假设

本模型主要探讨单一制造商、单一零售商和第三方回收商组成的闭环供应链的决策分析问题。制造商与零售商之间有互惠偏好行为特征，考虑这种互惠偏好对产品销售价格、产品批发价格以及第三方产品的回收率的影响，同时得出制造商、零售商以及第三方的利润和效用，并分析互惠偏好行为对利润和效用的影响，与无互惠偏好行为进行对比分析。本模型系统框架如下：首先建立了集中决策模型，制造商为唯一决策者，求解得出最优定价策略；其次建立第三方回收模式下的决策模型，此模型又被分为无互惠偏好下的闭环供应链决策模型以及考虑互惠偏好的闭环供应链决策模型，并分别利用Stackelberg 博弈理论求解得出最优定价策略；接着通过分析求解得出相关命题结论；最后通过数值仿真与分析进一步验证命题与结论的正确性。

笔者认为再制造品指的是通过对回收的废旧产品加工再制造的产品，新产品指的是用全新的原材料以及零部件生产的产品。假设再制造品和新产品的质量和性能是完全相同的，在同一个市场进行销售，并且市场是完全开放的，同时消费者对新产品和再制造产品的接受和认可程度是一致的；假设该闭环供应链包括单一制造商、单一零售商和第三方回收商，供应链上各级成员的目标都是自身利益最大化，同为独立决策者，均为风险中性，三方之间信息是完全共享的，无信息延迟的情况。制造商对原材料和废旧产品进行制造和再制造，设制造商生产新产品单位成本为 $c _ { { _ m } }$ ，利用废旧品进行再制造的单位成本为 $c _ { r }$ 令 $\Delta = c _ { m } - c _ { r } > 0$ ，表示再制造节约的成本；产品的需求函数为$D { = } a .$ -bp其中 $\textit { a } , \boldsymbol { b }$ 为常量且 $^ { a } , b { \geq } 0$ ， $a$ 代表市场容量， $b$ 表示市场需求对价格的灵敏度；设废旧品回收相关建设投资成本为$l = k \tau ^ { 2 }$ ， $k$ 为废旧品回收投资成本系数，现实生活中可以理解为回收废旧产品时的多种物流成本以及进行的营销费用， $\tau$ 为废旧品回收比率，即回收到的旧产品占产品总需求的比例，$\tau \in [ 0 , 1 ]$ ， $\scriptstyle { \tau = 1 }$ 表示废旧产品全部回收，制造商只用废旧产品进行再生产， $\scriptstyle { \tau = 0 }$ 表示不回收废旧产品，制造商只用原材料进行生产；制造商以批发价格 $w$ 将产品批发给零售商销售，零售商以销售价格 $p$ 向市场销售产品，制造商以单位产品转移支付价格 $B$ 从回收方处回收产品，为避免制造商无利可图，要求制造商再制造节约的成本不小于其回购单位废旧产品的价格即$\Delta \geq B$ 。本文中回收方负责回收产品，并将回收到的产品以转移支付价格回售给制造商，制造商回购的产品全部用于再制造。

$\Pi _ { j } ^ { i }$ 表示闭环供应链回收模型i中渠道成员 $j$ 的利润，i取$c$ 、 $3 P$ ，表示集中决策模型（模型 $c$ ）和第三方回收模型（模型 $3 P$ ）， $j$ 可以取 $m \ 、 r$ 和 $3 P$ ，分别表示制造商、零售商和第三方回收商。假设第三回收商支付给消费者的废旧产品的回收价格为零，在此需要指出的是即便该参数不为零，不会改变本文的结论，仅会增加数学处理的难度。本文考虑制造商为领导者，零售商及第三方作为追随者，以及在Stackelberg博弈决策的框架下进行博弈。

# 2 集中决策模式（模型 $c$ ）

$$
\Pi ^ { c } = ( p - c _ { _ m } ) ( a - b p ) + \Delta \tau ( a - b p ) - k \tau ^ { 2 }
$$

其中：决策变量为产品的销售价格 $p$ 和回收率 $\tau$ 。制造商是唯一决策者，对销售价格和回收率进行集中决策，求得进行集中决策情形下闭环供应链系统的最佳定价策略为

$$
p _ { c } ^ { * } = \frac { 2 a k - a b \Delta ^ { 2 } + 2 b k c _ { m } } { b ( 4 k - \Delta ^ { 2 } b ) } , \tau _ { c } ^ { * } = \frac { \Delta ( a - b c _ { m } ) } { 4 k - \Delta ^ { 2 } b }
$$

闭环供应链系统总收益为

$$
\Pi _ { c } ^ { * } = \frac { k ( a - b c _ { m } ) ^ { 2 } } { b ( 4 k - \Delta ^ { 2 } b ) }
$$

# 3 第三方回收模式（模型 $3 P$ ）

# 3.1无互惠偏好下闭环供应链定价策略

在模型 $3 P$ 中，第三方回收商负责回收废旧产品并转移给制造商，零售商仅负责对产品的销售，制造商负责生产以及再制造。制造商是Stackelberg 博弈的领导者，零售商和第三方回收商是跟随者。

$$
\Pi _ { \scriptscriptstyle m } ^ { 3 P } = ( w - c _ { \scriptscriptstyle m } ) ( a - b p ) + \Delta \tau ( a - b p ) - B \tau ( a - b p )
$$

$$
\Pi _ { r } ^ { 3 P } = ( p - w ) ( a - b p )
$$

$$
\Pi _ { 3 P } ^ { 3 P } = B \tau ( a - b p ) - k \tau ^ { 2 }
$$

其中：制造商的决策变量为批发价格 $w$ ；零售商的决策变量为  
销售价格 $p$ ；第三方回收商的决策变量为回收率 $\tau$ 。依据式(5)$p ^ { 3 P } = \frac { a + b w } { 2 b }$   
率为τ3P=Ba-Bbw 由上式可得命题1。

命题1零售商的零售价格与批发价格呈正相关，第三方产品的回收率与产品批发价格呈负相关。

将 $p ^ { 3 P }$ 、 $\tau ^ { 3 P }$ 带入式(4)可得最优批发价格为

$$
\boldsymbol { w } ^ { * 3 P } = \frac { a b \boldsymbol { B } ^ { 2 } - a b \Delta B + 2 a k + 2 b c _ { m } k } { b ( b B ^ { 2 } - b \Delta B + 4 k ) }
$$

继而可求得零售商最佳销售价格及第三方回收商的回收率：

$$
p ^ { * 3 P } = \frac { a b B ^ { 2 } - a b \Delta B + 3 a k + b c _ { m } k } { b ( b B ^ { 2 } - b \Delta B + 4 k ) }
$$

$$
\tau ^ { * 3 P } = \frac { B ( a - b c _ { m } ) } { 2 b B ^ { 2 } - 2 b \Delta B + 8 k }
$$

由此得到制造商、零售商和第三方的最优回收模式利润为

$$
\Pi _ { m } ^ { * 3 P } = \frac { k ( a - b c _ { m } ) ^ { 2 } } { 2 b ( b B ^ { 2 } - b \Delta B + 4 k ) }
$$

$$
\Pi _ { r } ^ { * 3 P } = \frac { k ^ { 2 } ( a - b c _ { m } ) ^ { 2 } } { b ( b B ^ { 2 } - b \Delta B + 4 k ) ^ { 2 } }
$$

$$
\Pi _ { 3 P } ^ { ^ { * 3 P } } = \frac { B ^ { 2 } k ( a - b c _ { m } ) ^ { 2 } } { 4 ( b B ^ { 2 } - b \Delta B + 4 k ) ^ { 2 } }
$$

# 3.2互惠偏好下闭环供应链定价策略

假设制造商和零售商，彼此对对方的收益表现出关心，而制造商和零售商对第三方回收商没有互惠偏好的特征，此时制造商、零售商和第三方回收商的渠道利润函数不变，本文参考文献[11]令制造商、零售商和第三方回收商的主观效用函数分别为

$$
U _ { _ { h m } } = \Pi _ { _ { m } } + \theta _ { _ { m } } \Pi _ { _ { r } }
$$

$$
U _ { _ { h r } } = \Pi _ { _ { r } } + \theta _ { _ { r } } \Pi _ { _ { m } }
$$

$$
U _ { { \scriptscriptstyle h 3 p } } = \Pi _ { { \scriptscriptstyle 3 p } }
$$

其中： $U _ { _ { h m } }$ 、 $U _ { _ { h r } }$ 和 $U _ { \scriptscriptstyle h 3 p }$ 分别为制造商、零售商和第三方回收商

互惠偏好下的主观效用； $\boldsymbol { \theta } _ { { m } }$ 、 $\theta _ { r }$ 和分别为制造商和零售商互惠偏好系数,令 $0 < \theta _ { { \scriptscriptstyle m } }$ ， $\theta _ { r } < 1$ ，零售商在决策时以自己主观效用最大化为前提，即零售商确定最优的产品市场价格来使自己的效用最大化，由 U" =0可得零售商的最佳反应函数p= α+bw+0(b(c-w)+Bbτ-b△t)，将零售商的价格P带入Un3p，并由一阶条件 U =0可以得到第三方互惠偏好下废旧产品回收率τ=(Bbw-Bbc）0,+Ba-Bbw ，将零售商价格和第三方回收率带入 $U _ { h m }$ ，并由一阶条件 U =0可以得到制造商互惠偏好下的最优批发价格 $w _ { h } ^ { * M }$ 、 $\tau _ { h } ^ { * }$ 和 $\boldsymbol { p } _ { h } ^ { * }$ 。

$$
\begin{array} { r l } & { w _ { h } ^ { * A t } = ( 4 a k + 4 b c _ { m } k - 4 a k \theta _ { _ m } + 2 B ^ { 2 } a b - 8 b c _ { m } k \theta _ { r } - 2 B a b \Delta \downarrow } \\ & { - 2 B ^ { 2 } b ^ { 2 } c \theta _ { r } ^ { 2 } + 2 B b ^ { 2 } c _ { m } \Delta \theta _ { r } ^ { 2 } + B ^ { 2 } a b \theta _ { r } ^ { 2 } \theta _ { _ m } + B ^ { 2 } b ^ { 2 } c _ { m } \theta _ { r } ^ { 2 } \theta _ { _ m } \downarrow } \\ & { + B ^ { 2 } b ^ { 2 } c _ { m } \theta _ { r } ^ { 3 } \theta _ { _ m } - 3 B ^ { 2 } a b \theta _ { _ r } \theta _ { _ m } + 4 b c _ { m } k \theta _ { _ r } ^ { 2 } \theta _ { _ m } - B a b \Delta \theta _ { r } ^ { 2 } \theta _ { _ m } \downarrow } \\ & { - B b ^ { 2 } c _ { m } \Delta \theta _ { _ r } ^ { 2 } \theta _ { _ m } - B b ^ { 2 } c _ { _ m } \Delta \theta _ { _ r } ^ { 3 } \theta _ { _ m } + 3 B a b \Delta \theta _ { _ r } \theta _ { _ m } ) / b ( \theta _ { _ r } - 1 ) ( 4 k \theta _ { _ m } \downarrow } \\ & { - 8 k - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { _ r } \theta _ { _ m } - 2 B ^ { 2 } b \theta _ { _ r } + 3 B ^ { 2 } b \theta _ { _ \theta } \theta _ { _ m } + B ^ { 2 } b \theta _ { _ r } ^ { 2 } \theta _ { _ m } \downarrow } \\ & { + 2 B b \Delta \theta _ { _ r } - 3 B b \Delta \theta _ { _ \theta } \theta _ { _ m } - B b \Delta \theta _ { _ r } ^ { 2 } \theta _ { _ m } ) ) } \end{array}
$$

$$
\begin{array} { r l } & { \tau _ { h } ^ { * } = ( B ( \theta , \theta _ { r } - 1 ) ( a - b c _ { m } ) ) / ( 4 k \theta _ { _ m } - 8 k - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { r } \theta _ { _ m } \downarrow } \\ & { - 2 B ^ { 2 } b \theta _ { _ r } + 3 B ^ { 2 } b \theta _ { _ r } \theta _ { _ m } + B ^ { 2 } b { \theta _ { _ r } } ^ { 2 } \theta _ { _ m } + 2 B b \Delta \theta _ { _ r } - 3 B b \Delta \theta _ { _ r } \theta _ { _ m } \downarrow } \\ & { - B b \Delta { \theta _ { _ r } } ^ { 2 } \theta _ { _ m } ) } \end{array}
$$

由上式 $\tau _ { h } ^ { * }$ 可得命题2。

命题2第三方产品的回收率随制造商对零售商的互惠偏好程度增大而增大。

证明由于

$$
\begin{array} { l } { \displaystyle \frac { \hat { \sigma } \tau _ { h } ^ { * } } { \hat { \sigma } \theta _ { m } } = ( B ( \theta _ { r } - 1 ) ( a - b c _ { m } ) ( b \theta _ { r } B ^ { 2 } - b \Delta \theta _ { r } B + 4 k ) ) / ( 4 k \theta _ { m } - 8 k \downarrow } \\ { \displaystyle - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { r } \theta _ { m } - 2 B ^ { 2 } b \theta _ { r } + 3 B ^ { 2 } b \theta _ { r } \theta _ { m } + B ^ { 2 } b { \theta _ { r } } ^ { 2 } \theta _ { m } \downarrow } \\ { \displaystyle + 2 B b \Delta \theta _ { r } - 3 B b \Delta \theta _ { r } \theta _ { m } - B b \Delta \theta _ { r } ^ { 2 } \theta _ { m } ) ^ { 2 } > 0 } \end{array}
$$

命题2表明，当制造商对零售商的互惠偏好程度增大时，零售商取得收益会相应增加，零售商收益增加会使得消费市场受益，由此来增加回收商的回收率，这有利于环境的保护。

$$
\begin{array} { r l } & { p _ { h } ^ { * } = ( ( c _ { m } \theta _ { m } B ^ { 2 } b ^ { 2 } + a \theta _ { m } B ^ { 2 } b - c _ { m } \Delta \theta _ { m } B b ^ { 2 } - a \Delta \theta _ { m } B b ) { \theta _ { r } } ^ { 2 } + ( 4 a k \theta _ { m } \downarrow } \\ & { - B ^ { 2 } b ^ { 2 } c _ { m } - 3 B ^ { 2 } a b + 4 b c k \theta _ { m } + B b ^ { 2 } c _ { m } \Delta + 6 B ^ { 2 } a b \theta _ { m } + 3 B a b \Delta \downarrow } \\ & { - 6 B a b \Delta \theta _ { m } ) \theta _ { r } - 4 a b B ^ { 2 } + 4 B a b \Delta - 1 2 a k - 4 b c _ { m } k + 8 a k \theta _ { m } ) \downarrow } \\ & { / ( 2 \theta _ { m } B ^ { 2 } b ^ { 2 } - 2 \theta _ { m } \Delta B b ^ { 2 } ) { \theta _ { r } } ^ { 2 } + ( 6 B ^ { 2 } b ^ { 2 } \theta _ { m } - 4 B ^ { 2 } b ^ { 2 } + 8 b k \theta _ { m } + 4 B b ^ { 2 } \Delta \downarrow } \\ & { - 6 B b ^ { 2 } \Delta \theta _ { m } ) \theta _ { r } + 8 b k \theta _ { m } - 4 B ^ { 2 } b ^ { 2 } - 1 6 b k + 4 B b ^ { 2 } \Delta ) } \end{array}
$$

由上式可得命题3。

命题3零售商的零售价格与制造商互惠偏好程度呈负相关。

证明由于

$$
\begin{array} { r l } & { \frac { \hat { \mathcal { O } } p _ { h } ^ { * } } { \hat { \mathcal { O } } \theta _ { m } } = ( \theta _ { r } - 1 ) ( a - b c _ { m } ) ( b \theta _ { r } B ^ { 2 } - b \Delta \theta _ { r } B + 4 k ) ^ { 2 } / ( 2 b ( 4 k \theta _ { m } - 8 k \downarrow } \\ & { - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { r } \theta _ { m } - 2 B ^ { 2 } b \theta _ { r } + 3 B ^ { 2 } b \theta _ { m } \theta _ { m } + B ^ { 2 } b \theta _ { r } ^ { 2 } \theta _ { m } \downarrow } \\ & { + 2 B b \Delta \theta _ { r } - 3 B b \Delta \theta _ { r } \theta _ { m } - B b \Delta \theta _ { r } ^ { 2 } \theta _ { m } ) ^ { 2 } ) < 0 } \end{array}
$$

命题得证。

命题3表明随着制造商互惠偏好程度的增强，零售商从制造商那里获取的收益会增加，因此没有必要通过增加市场销售价格来获取收益，相反会降低销售价格，达到薄利多销的目的。

进一步可求得互惠条件下制造商利润、零售商利润及第三方利润，同时还可求得制造商、零售商及第三方的主观效用。

$$
\begin{array} { r l } & { \Pi _ { h m } ^ { * } = ( ( \theta _ { r } \theta _ { m } - 1 ) ( a - b c _ { m } ) ^ { 2 } ( b \theta _ { r } B ^ { 2 } - b B \Delta \theta _ { r } + 4 k ) ( 4 k - 4 k \theta _ { m } + B ^ { 2 } b \downarrow } \\ & { - B b \Delta + B ^ { 2 } b \theta _ { r } - 2 B ^ { 2 } b \theta _ { r } \theta _ { m } - B b \Delta \theta _ { r } + 2 B b \Delta \theta _ { r } \theta _ { m } ) ) / ( 2 b ( \theta _ { r } - 1 ) ( 4 k \theta _ { m } \downarrow } \\ & { - 8 k - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { r } \theta _ { m } - 2 B ^ { 2 } b \theta _ { r } + 3 B ^ { 2 } b \theta _ { r } \theta _ { m } + B ^ { 2 } b { \theta _ { r } } ^ { 2 } \theta _ { m } \downarrow } \\ & { + 2 B b \Delta \theta _ { r } - 3 B b \Delta \theta _ { r } \theta _ { m } - B b \Delta \theta _ { r } ^ { 2 } \theta _ { m } ) ^ { 2 } ) } \end{array}
$$

$$
\begin{array} { r l } & { \Pi _ { h r } ^ { ' } = ( ( \theta _ { r } \theta _ { m } - 1 ) ( a - b c _ { m } ) ^ { 2 } ( b \theta _ { r } B ^ { 2 } - b B \Delta \theta _ { r } + 4 k ) ( 4 k - 1 2 k \theta _ { r } \downarrow } \\ & { + 4 k \theta _ { r } ^ { 2 } \theta _ { m } - 3 B ^ { 2 } b \theta _ { r } ^ { 2 } + 4 k \theta _ { r } \theta _ { m } - B ^ { 2 } b \theta _ { r } + 3 B b \Delta \theta _ { r } ^ { 2 } + 3 B ^ { 2 } b \theta _ { r } ^ { 2 } \theta _ { m } \downarrow } \\ & { + B ^ { 2 } b \theta _ { r } ^ { 3 } \theta _ { m } + B b \Delta \theta _ { r } - 3 B b \Delta \theta _ { r } ^ { 2 } \theta _ { m } - B b \Delta \theta _ { r } ^ { 3 } \theta _ { m } ) ) / ( 4 b ( \theta _ { r } - 1 ) ( 4 k \theta _ { m } \downarrow } \\ & { - 8 k - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { r } \theta _ { m } - 2 B ^ { 2 } b \theta _ { r } + 3 B ^ { 2 } b \theta _ { r } \theta _ { m } + B ^ { 2 } b \theta _ { r } ^ { 2 } \theta _ { m } \downarrow } \\ & { + 2 B b \Delta \theta _ { r } - 3 B b \Delta \theta _ { r } \theta _ { m } - B b \Delta \theta _ { r } ^ { 2 } \theta _ { m } ) ^ { 2 } ) } \end{array}
$$

$$
\begin{array} { r l } & { \Pi _ { h 3 p } ^ { * } = ( B ^ { 2 } ( \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } - 1 ) ^ { 2 } ( a - b c _ { _ m } ) ^ { 2 } ( b \theta _ { \mathrm { r } } B ^ { 2 } - b B \Delta \theta _ { \mathrm { r } } + 2 k ) ) / ( 2 ( 4 k \theta _ { \mathrm { m } } \downarrow } \\ & { - 8 k - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } - 2 B ^ { 2 } b \theta _ { \mathrm { r } } + 3 B ^ { 2 } b \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } + B ^ { 2 } b \theta _ { \mathrm { r } } ^ { 2 } \theta _ { \mathrm { m } } \downarrow } \\ & { + 2 B b \Delta \theta _ { \mathrm { r } } - 3 B b \Delta \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } - B b \Delta \theta _ { \mathrm { r } } ^ { 2 } \theta _ { \mathrm { m } } ) ^ { 2 } ) } \end{array}
$$

$$
\begin{array} { r l } & { U _ { h m } ^ { * } = ( ( \theta _ { r } \theta _ { m } - 1 ) ^ { 2 } ( a - b c _ { m } ) ^ { 2 } ( b \theta _ { r } B ^ { 2 } - b \Delta \theta _ { r } B + 4 k ) / 4 b ( \theta _ { r } - 1 ) \downarrow } \\ & { ( 4 k \theta _ { m } - 8 k - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { r } \theta _ { m } - 2 B ^ { 2 } b \theta _ { r } + 3 B ^ { 2 } b \theta _ { r } \theta _ { m } \downarrow } \\ & { + B ^ { 2 } b { \theta _ { r } } ^ { 2 } \theta _ { m } + 2 B b \Delta \theta _ { r } - 3 B b \Delta \theta _ { r } \theta _ { m } - B b { \Delta \theta _ { r } } ^ { 2 } \theta _ { m } ) } \end{array}
$$

$$
\begin{array} { r l } & { U _ { _ { h r } } ^ { * } = ( \theta _ { r } \theta _ { _ m } - 1 ) ^ { 2 } ( a - b c _ { _ m } ) ^ { 2 } ( b \theta _ { r } B ^ { 2 } - b \Delta \theta _ { r } B + 4 k ) ^ { 2 } / ( 4 b ( 4 k \theta _ { _ m } - 8 k \downarrow } \\ & { - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { r } \theta _ { _ m } - 2 B ^ { 2 } b \theta _ { _ r } + 3 B ^ { 2 } b \theta _ { _ r } \theta _ { _ m } + B ^ { 2 } b \theta _ { _ r } ^ { ^ { 2 } } \theta _ { _ m } \downarrow } \\ & { + 2 B b \Delta \theta _ { _ r } - 3 B b \Delta \theta _ { _ r } \theta _ { _ m } - B b \Delta \theta _ { _ r } ^ { ^ { 2 } } \theta _ { _ m } ) ^ { 2 } ) } \end{array}
$$

$$
\begin{array} { r l } & { U _ { h 3 p } ^ { * } = ( B ^ { 2 } ( \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } - 1 ) ^ { 2 } ( a - b c _ { m } ) ^ { 2 } ( b \theta _ { \mathrm { r } } B ^ { 2 } - b B \Delta \theta _ { \mathrm { r } } + 2 k ) ) / ( 2 ( 4 k \theta _ { \mathrm { m } } \downarrow } \\ & { - 8 k - 2 B ^ { 2 } b + 2 B b \Delta + 4 k \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } - 2 B ^ { 2 } b \theta _ { \mathrm { r } } + 3 B ^ { 2 } b \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } + B ^ { 2 } b \theta _ { \mathrm { r } } ^ { 2 } \theta _ { \mathrm { m } } \downarrow } \\ & { + 2 B b \Delta \theta _ { \mathrm { r } } - 3 B b \Delta \theta _ { \mathrm { r } } \theta _ { \mathrm { m } } - B b \Delta \theta _ { \mathrm { r } } ^ { 2 } \theta _ { \mathrm { m } } ) ^ { 2 } ) } \end{array}
$$

在确定模型的临界条件以及可行条件的过程中，笔者结合实际情况认为制造商虽然是市场的领导者，但零售商能够与制造商进行合作的最低条件是零售商能够获利，即 $\boldsymbol { \Pi } _ { h r } ^ { * } > 0$ ，同时第三方回收商进行合作的条件同样是能够从中获利，即$\Pi _ { h 3 p } ^ { * } > 0$ ，在此种可行条件下，得出边界条件$0 < \theta _ { { } _ { m } } < 1 , 0 < \theta _ { { } _ { r } } < 0 . 4 1 2$ ，由此确定的区间称之为制造商、零售商和第三方回收商持续稳定合作区域。

对于互惠偏好下的制造商、零售商和第三方的利润及主观效用与互惠偏好系数的关系，由于受多方面因素的影响，通过解析式无法推断出其中的相互关系，因此本文在数值仿真部分进行讨论。

# 4 数值仿真与分析

本文参考文献[14]的里参数，令 $a = 1 0 0 0$ ， $b = 5$ ， $c _ { { \scriptscriptstyle m } } = 1 0 0$ ，$c _ { r } = 5 0$ ， $k = 1 0 0 0 0$ ， $B = 5 0$ ， $0 < \theta _ { { \scriptscriptstyle m } } , \theta _ { { \scriptscriptstyle r } } < 1$ ，通过数值仿真分析双方互惠偏好程度对零售商产品销售价格，产品批发价格，产品回收率及对制造商零售商和第三方利润的影响。首先分析制造商和零售商互惠偏好程度对零售商市场销售价格的影响。由图1可看出，在给定区间内，零售商的销售价格 $p$ 随着制造商对其的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 的增加而减少，而其本身的互惠偏好程度 $\theta _ { { r } }$ 对其销售价格 $p$ 没有明显影响，同时在给定的区域

$S = \left\{ ( \theta _ { { } _ { m } } , \theta _ { r } ) \left| 0 < \theta _ { { } _ { m } } < 1 , 0 < \theta _ { r } < 0 . 4 1 2 \right. \right\}$ 内，制造商和零售商能够持续稳定合作，当超出这个边界条件时，销售价格出现异常增长的情况。图2反映的是制造商和零售商的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 、$\theta _ { { } _ { r } }$ 对第三方产品回收率 $\tau$ 的影响。由图中可看出，在持续稳定合作区间内，第三方产品的回收率 $\tau$ 随着制造商对零售商的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 的增加而增加，与零售商对制造商的互惠偏好程度 $\theta _ { { r } }$ 没有明显影响，而超出这个区域内则出现异常。制造商对零售商互惠偏好程度 $\theta _ { { _ m } }$ 增加时往往以较低的产品批发价格出售给零售商，此时零售商不必增加产品销售价格 $p$ 来达到增加利润的目的，相反会降低产品销售价格 $p$ 来扩大产品销售量，达到薄利多销的目的。此时消费者市场上该产品增多，在其他条件不变的情况下，第三方产品的回收率 $\tau$ 也会因此而增加。

![](images/b80bf71ed22c5ef0ed3ed935b8e37574fc8a1da966f1993535bb8adc8f6c8a55.jpg)  
图1制造商和零售商互惠偏好程度对零售商销售价格影响

![](images/11d9fb09971637fe805a85842731c5b1190d68425152950f165b2a1d18124f0d.jpg)  
图2制造商和零售商互惠偏好程度对第三方回收率影响

图3反映的是制造商和零售商之间互惠偏好程度 $\theta _ { { \scriptscriptstyle m } } \ : , \ : \theta _ { { \scriptscriptstyle r } }$ 对产品批发价格 $w$ 的影响。可见，在持续稳定合作区域内，产品的批发价格 $w$ 随着制造商对零售商的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 增加而减少，随着零售商对制造商的互惠偏好程度 $\theta _ { r }$ 的增加而增加，这与人们的预期是相符合的。这是因为当制造商对零售商的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 增加时，往往会以降低产品批发价格 $w$ 的方式来达到让利的目的；相反，零售商对制造商互惠偏好程度 $\theta _ { r }$ 增强时，往往会以增加产品批发价格 $w$ 的方式来达到让利的目的，而当超出稳定合作区域时，产品的批发价格则出现异常增长，这与实际不符。接着本文从横向对比分析图1\~3，考虑制造商与零售商之间的互惠偏好对 $p$ 、𝜏、 $w$ 之间影响的区别。由图中得知在持续稳定合作区域内产品销售价格 $p$ 及批发价格 $w$ 随制造商对零售商互惠偏好程度 $\theta _ { { _ m } }$ 的增加而减少，并且对销售价格 $p$ 的影响要大于对批发价格 $w$ 的影响，同时制造商对零售商的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 的增加会促进第三方产品回收率 $\tau$ 的增加。整体来说，零售商对制造商的互惠偏好程度 $\theta _ { { } _ { r } }$ 对 $p$ ， $\tau$ ， $w$ 的影响不大。

![](images/3f4a7232ea4adbdf66c172f2f3de3450852d58f3c854aee1a4211f82941a97aa.jpg)  
图3制造商和零售商互惠偏好程度对产品批发价格的影响

![](images/3e0e9d95963b08d25f01791f71d0f568844545edbf3cf3a880822d39cdc1c63c.jpg)  
图4制造商和零售商互惠偏好程度对制造商利润的影响

![](images/6bff8131e65894ac94d02e3eb2abb08bc50f3df2298c3375ba1ba5bb40f5daab.jpg)  
图5制造商和零售商互惠偏好程度对零售商利润的影响

![](images/3abb3e2c1c354847f8b77d2cea0dad07b1b938bd1a489afeb03992e5d413c35d.jpg)  
图6制造商和零售商互惠偏好程度对第三方利润的影响

图4反映的是制造商和零售商之间互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 、 $\theta _ { r }$ 对制造商利润 $\Pi _ { { \scriptscriptstyle m } }$ （式19）的影响。由图中可看出，制造商利润$\Pi _ { { \scriptscriptstyle m } }$ 随着零售商对其的互惠偏好程度 $\theta _ { { r } }$ 的增加而增加，随着本身对零售商的互惠偏好程度 $\theta _ { { _ m } }$ 的增加而减少，当超出稳定区域时，则会出现异常变化，这与上述的原因相同。图5反映的是零售商的利润 $\Pi _ { r }$ （式20）随着本身对制造商的互惠偏好程度$\theta _ { { r } }$ 的增加而减少，随着制造商对其互惠偏好程度 $\theta _ { { _ m } }$ 的增加而增加，当超出稳定合作区域时，则会异常变化。图6反映的是第三方的利润 $\Pi _ { { \scriptscriptstyle 3 p } }$ （式21）与制造商和零售商之间的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 、 $\theta _ { r }$ 的关系。由图中可看出，第三方利润 $\Pi _ { { \scriptscriptstyle 3 p } }$ 随着制造商对零售商的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 的增加而增加，而与零售商对制造商的互惠偏好程度 $\theta _ { r }$ 关系不大。这是因为制造商对零售商互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 增加使得零售商降低产品销售价格 $p$ ，扩大产品销售量，使得第三方产品的回收率 $\tau$ 增加，由此增加第三方的利润。接着本文从横向对比分析图4\~6，讨论制造商和零售商之间的互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 、 $\theta _ { r }$ 对制造商、零售商和第三方回收商利润 $\Pi _ { { \scriptscriptstyle m } }$ ， $\Pi _ { { r } }$ ， $\Pi _ { { \scriptscriptstyle 3 p } }$ 的影响。由图中得知，制造商与零售商之间的互惠偏好对彼此具有促进作用，对本身利润的增加则具有阻碍作用，而第三方回收商的利润受制造商对零售商互惠偏好程度 $\theta _ { { \scriptscriptstyle m } }$ 的影响明显大于零售商对制造商的互惠偏好程度 $\theta _ { r }$ 。同时由图7可看出，有一定的互惠偏好能够增加供应链系统的利润Ⅱ，更有利于供应链系统的各成员间的协调发展。并且制造商作为领导者，更应该作出互惠偏好的措施，不仅有利于系统其他成员获得收益，同时还有利于系统整体收益，从长远来看，更加能够保持供应链的持续运行。由于制造商、零售商以及第三方的主观效用与其各自利润呈现正相关关系，在此不做赘述。

![](images/12a5fc38c5ee34094d3de666fe22e2335be7e734774c6df5f00e518235eb3b96.jpg)  
图7系统总利润在有互惠偏好和无互惠偏好下的对比

# 5 结束语

本文分析了制造商委托第三方进行产品回收模式，分别探讨了集中决策模型和分散决策模型，并利用Stackelberg博弈模型对成员决策进行分析，得出不同模型下的最优产品销售价格、产品批发价格、第三方产品回收率以及最大利润。同时引入制造商与零售商之间具有互惠偏好特征，以及这种互惠偏好特征对闭环供应链成员的利润及效用的影响，并得出结论：a）零售商的零售价格与批发价格呈正相关，第三方产品的回收率与产品批发价格呈负相关；b)制造商与零售商之间的互惠偏好行为对闭环供应链系统利润是有利的；c）零售商产品销售价格与制造商对零售商的互惠偏好行为呈负相关，第三方产品的回收率与制造商对零售商的互惠偏好行为呈正相关；d)零售商对制造商的互惠偏好行为对整个系统的影响效果不明显，制造商作为主导商应该多关心闭环供应链成员的利润及收益情况，这样更有利于合作的长远发展，达到合作与共赢的目的。由于本文中只考虑了制造商委托第三方进行回收，以及制造商和零售商之间的互惠偏好特征，进一步可以研究制造商、零售商和第三方之间都具有互惠偏好特征的的情况或者混合回收模式下的成员之间具有行为偏好特征的情况。

# 参考文献：

[1]舒秘，聂佳佳．产能约束对闭环供应链回收渠道选择的影响[J].运筹 与管理，2015,24(4):52-57.(Shu Mi,Nie Jiajia.Effect of capacity constraint on choice of collecting channels in closed-loop supply chain [J]. Operations Research and Management Science,2015,24(4): 52-57.)

[2]Karakayali I,Emir-FarinasH,Akcali E.An analysis of decentralized collection and processing of end-of-life products [J]. Journal of Operations Management,2007,25 (6): 1161-1183.

[3] 高鹏，杜建国，聂佳佳，等．不同权力结构对再制造供应链技术创新策 略的影响[J]．管理学报，2016,13(10):1563-1570.(Gao Peng,Du Jianguo,Nie Jiajia,et al. Impact of different power structure on technological innovation strategy of remanufacturing supply chain [J]. Chinese Journal of Management,2016,13 (10): 1563-1570.)

[4]Giannoccaro I,Pontrandolfo P. Supply chain coordination by revenue sharing contracts [J]. International Journal of Production Economics,2004, 89 (2): 131-139.

[5]王哲，李帮义，刘志，等.政府规制对双责任双渠道闭环供应链的影响 [J].计算机集成制造系统，2017,23(10):2260-2268.(Wang Zhe,Li Bangyi,Liu Zhi,et al.Impact of government regulation on closed-loop supply chain with dual responsibilities and dual channels [J].Computer Integrated Manufacturing Systems,2017,23(10): 2260-2268.)

[6]王玉燕，申亮．政府调控下闭环供应链应对突发事件的策略分析[J]. 管理工程学报,2015,29(4):145-151.(Wang Yuyan, Shen Liang.Analysis ofclosed-loop supply chain strategy in response to emergencies under government regulations [J].Journal ofIndustrial Engineering,2015,29 (04): 145-151. )

[7]韩小花，吴海燕，杨倩霞．成本与需求同时扰动下竞争型闭环供应链的 生产与协调决策[J].系统管理学报,2016,25(3):546-555,570.(Han Xiaohua,Wu Haiyan,Yang Qianxia.Production and coordination decisions in the competitive closed-loop supply chain with cost and demand perturbations [J].Journal of Systems& Management,2016,25(3): 546-555,

# 570.)

[8]初叶萍，张曙红．闭环供应链混合切换库存控制模型研究[J].计算机 应用研究,2017,34(6):1690-1693,1698.(Chu Yeping,Zhang Shuhong. Research onhybrid switching inventory control model of closed-loop supply chain [J].Application Research of Computers,2017,34(6):1690-1693, 1698.)

[9]姚锋敏，滕春贤．公平关切下的两零售商竞争闭环供应链决策模型[J]. 计算机集成制造系统，2017,23(8):1731-1738.(Yao Fengmin,Teng Chunxian.Decision model for closed-loop supply chain with competing retailersconsideringfairnessconcerns[J]. ComputerIntegrated Manufacturing Systems,2017,23(8):1731-1738.)

[10]张克勇，吴燕，侯世旺，零售商公平关切下闭环供应链定价策略研究 [J].山东大学学报：理学版,2013,48(5):83-91.(Zhang Keyong,Wu Yan, Hou Shiwang.Pricing strategy of considering retailer’s fairness concerns in the closed-loop supply chain [J]. Journal of Shandong University (Natural Science),2013,48 (5):83-91.)

[11]张克勇．互惠偏好下的闭环供应链系统定价决策分析[J].控制与决策， 2015,30 (9): 1717-1722. (Zhang Keyong.Analysis on closed-loop supply chain pricing decision under reciprocity preference [J]. Control and Decision, 2015,30 (9):1717-1722.)

[12]Du Shaofu,Nie Tengfei, Chu Chengbin,et al.Reciprocal supply chain with intention[J].European Journal of Operational Research,2014,239(2): 389- 402.

[13]赵琳．互惠利他偏好下的闭环供应链定价策略研究[D].太原：中北大 学,2016.(Zhao Lin.Pricing strategy of closed-loop supply chain with reciprocity and altruism [D]. Taiyuan: North University of China, 2016.)