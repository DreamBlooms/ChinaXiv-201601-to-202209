# 考虑制造商公平关切的强势零售商自有品牌导入策略研究

黄宗盛‘²，冯婷1

(1．上海海事大学 经济管理学院，上海 201306;2．复旦大学 计算机科学技术学院，上海 200433)

摘要：研究了制造商公平关切下强势零售商的自有品牌导入策略，在有强势零售商存在的供应链中，考虑弱势一方制造商的公平关切对供应链决策的影响。将零售商是否导入自有品牌以及制造商是否具有公平关切行为进行组合，得到了四种情景，分析了四种情景下的供应链博弈模型，得到均衡策略、利润以及相应自有品牌的导入条件；进一步对模型进行比较分析，探讨自有品牌导入以及制造商公平关切对供应链成员决策以及利润的影响。研究发现，制造商的公平关切会使其批发价格和利润提高；零售商导入自有品牌会使零售商和供应链的利润增加，当自有品牌产品替代率较大时也会有利于制造商利润水平的提高。

关键词：自有品牌；公平关切；强势零售商；供应链管理 中图分类号：F270；TP391 doi:10.3969/j.issn.1001-3695.2018.08.0631

Impact of fairness concern on store brand strategy of powerful retailer

Huang Zongsheng1,2, Feng Tingl (1.SchoolofEconomics&Management,Shanghai MaritimeUniversity,Shanghai2O1306,China;2.SchoolofComputer Science,Fudan University,Shanghai 20O433,China)

Abstract:This paper establisheda Stackelberggame toresearch the store brand introducing strategy forapowerfulretailer inasuplychain which isconsistedof amanufacturerand aretailer.As the leaderof the supplychain,theretailerchooses whether to introduce the store brand,while the manufacturer mayhave fairnessconcern towards the channel leader.Firstly, the paper resolved theoptimal strategyaswell as the profit for both manufacturerand retailer.Secondly，the paper investigated the impactof store brand introducing and fairnessconcern ofthe manufacturer bycomparingfour models.The results show that the manufacturer wouldraise the wholesale price and also the profit level when considering the fairness concern.Theretailer would result in profit increasing withthe introducingofstore brand.Formanufacturers,thestore brand does notalways harm their interests.The store brand would also beneficial to the manufactureronconditionthat the substitution rate of the store brand is quite large.

Key words: store brand; fairness concern; powerful retailer; supply Chain management

# 0 引言

近年来，由于生产制造水平不断提升，销售商在供应链中占据越来越重要的地位。世界范围内大型零售商的出现及崛起，使得零售商占据供应链主导地位的趋势愈加凸显出来，例如沃尔玛、家乐福、亚马逊、京东等。这种转变使得零售商在供应链利润分配中取得了较大优势，而上游的制造商则处于一种相对不太公平的状态，此时制造商会具有公平关切的诉求。那么，在零售商领导的供应链中，制造商的公平关切会如何影响供应链成员的决策及利润？处于领导地位的零售商会如何反应？

与此同时，零售商自有品牌发展势头迅猛。瑞士和英国的自有品牌零售额在全球占比最高，整个欧洲的自有品牌占比均值在 $30 \% { \sim } 4 0 \%$ 。中国的自有品牌建设也呈现出增长的态势。中国连锁经营协会在2016年的百强年度报告中提到百强中已经有超过 $80 \%$ 的企业开始做自有品牌。自有品牌的引入增加了企业的差异化，同时又给零售商带来很可观的利润。沃尔玛、家乐福、麦德龙这些国际连锁零售的巨头纷纷参与其中。另外电子商务领域的亚马逊和京东近些年也在积极布局自有品牌。

在自有品牌方面，研究人员做了大量广泛而深入的研究。从实证方面的研究来看，Hara等人[1]研究了制造商和零售商的产品开发合作，发现当自有品牌产品价值提高时，虽然面临制造商品牌强烈的市场竞争，但双方都能从中受益。而Fornari等人[2]利用来自322种产品在2010-2013年间于某超市的销售面板数据，对制造商品牌与自有品牌的竞争进行实证研究。还有一部分学者研究影响自有品牌产品购买意愿的因素。Rubio等人[3]提出了消费者对自有品牌的忠诚度是影响消费者对零售商忠诚和信任的三个决定因素之一。Liu等人[4]在研究消费者对制造商品牌与自有品牌产品的偏好时，发现那些自我意识更强的人更偏好于制造商品牌产品。Chung等人[5探究了分销门店对制造商品牌与自有品牌的介绍对制造商与零售商价格领导关系的影响，发现零售商重塑价格领导环境的能力可以提高零售商的议价能力。在实证研究方面，学者们普遍认为引入自有品牌会给零售商带来一系列好处，如利润增加、顾客忠诚度提升、议价能力增强等，但关于自有品牌对制造商的影响的结论则不尽相同。同时，自有品牌的感知质量、门店形象、商品陈列等因素都是影响顾客是否愿意购买自有品牌产品的重要因素。

部分研究则从自有品牌导入策略和产品质量决策入手。

Chung等人[在一个垂直差异化的产品类别中研究自有品牌质量决策，发现自有品牌产品的质量并非越接近制造商品牌产品越好，它受消费者支付意愿分布的影响。Choi等人[7在由一个制造商和两个均引入自有品牌的零售商组成的供应链系统中，探讨自有品牌与制造商品牌以及自有品牌之间的竞争，发现零售商应当使自有品牌产品与其他自有品牌产品区分开，尽可能的接近制造商品牌；而制造商应该尽可能将其产品与自有品牌产品区别开来。Fang等人[8发现在制造商品牌产品的成本大于自有品牌产品成本时，零售商引入自有品牌会使供应链的总利润下降，这种情况可以通过最小订购量合同来协调。Jin等人[9在单、双渠道共5种供应链模型中对比零售商和制造商Stackelberg博弈下的渠道策略和自有品牌引入策略。Nalca 等人[10]研究了制造商与零售商的信息共享问题，发现当零售商将所掌握的消费者品味信息共享给制造商时，虽然制造商品牌与自有品牌的竞争加剧了，但是这对双方都有利。李凯等人[1研究表明在某些领导权结构下，当市场竞争一定程度地加剧，自有品牌的模仿反而会促进被模仿的品牌制造商利润增长。李海等人[12]研究了零售商引入自有品牌和制造商引入直销渠道之间的博弈竞争关系，并得出了均衡策略。这一部分研究在理性经济人假设下，得到了不同情况下自有品牌导入和质量决策的结论，但是忽略了决策者行为偏好特别是处于弱势一方的制造商的行为偏好对于自有品牌决策产生的影响。

公平关切作为一种很重要的非理性行为，近年来吸引了许多学者的关注。Cui等人[9]将成员的公平问题引入渠道协调，假设一个线性需求函数，在只有零售商或者双方都关心公平时，设计了一个用来协调供应链的批发价格合同。Caliskan-Demirag等人[20]将上一篇论文的研究成果推广到了非线性需求函数中，发现与线性需求函数相比，只有零售商考虑公平时，指数需求函数的供应链模型可以在稍宽松的条件下实现协调。杜少甫等人[13]通过构建Nash讨价还价模型改进传统的公平参考框。张克勇等人[14将零售商公平关切行为倾向引入闭环供应链的差别定价中，发现这对制造商是有利的。Li等人[15]考虑制造商引入直销渠道，零售商在销售产品时会给产品增加附加价值，且具有公平关切的情景，发现渠道效率随顾客对零售渠道的忠诚度提高而提高，随零售商公平关切程度增大而减小。Yang等人[6在包含一个供应商和一个具公平关切的零售商分销渠道中研究合作广告决策，分析零售商公平关切对决策的影响。Qin等人[17研究在零售商有限理性下，公平关切对供应链决策的影响，公平关切使供应链上的利润增大，使制造商与零售商之间的利润分配更加平衡。Nie 等人[18]在包含一个制造商和两个零售商（一个只关注公平分配，另一个还关注同济公平）的供应链中，研究数量折扣问题，并用数量折扣合同与固定费用相结合的方式对供应链进行协调。可以发现，学者们将公平关切的因素引入的不同的供应链结构和环境中，来讨论公平关切对供应链成员产生的重要影响，但是对于制造商面对强势零售商时所具有的公平关切还有待更加深入的研究，尤其是该零售商引入自有品牌产品时。

综上所述，关于自有品牌的研究一般都是在理性经济人假设下，研究自有品牌本身的产品定位以及影响消费者购买的因素等，或者是零售商导入自有品牌后，研究制造商与零售商的互动博弈问题，而较少研究行为范畴的供应链自有品牌问题，而在公平关切下研究自有品牌导入策略的文献则鲜少见到。而在实际中，决策者并不总是理性的，他会受到各种行为因素的影响，例如公平关切、风险偏好、锚定效应等。

在供应链中，参与成员的公平关切行为或许会导致其决策偏离理性时的结果，面对非理性的合作伙伴，各成员应当如何应对？本文试图将公平关切引入到一个二级供应链中，考虑强势零售商的自有品牌导入战略以及制造商的公平关切行为，建立斯坦伯格博弈模型，采用逆向归纳法研究零售商的自有品牌导入以及制造商的公平关切对供应链产生的影响。研究结果表明，当制造商具有公平关切时其批发价格会提高，同时利润水平也会提升；而随着两种产品竞争强度的不同，自有品牌对于供应链双方的影响也不同。

# 1 模型描述

考虑一个由单个制造商和单个零售商所组成的二级供应链，其中零售商为该供应链的领导者，制造商为跟随者。制造商将自己生产的全国性产品以批发价卖给零售商，零售商再将该产品销售给消费者。同时，零售商会考虑是否应该引入与制造商产品具有一定替代性的自有品牌；制造商作为跟随者，对供应链的利润分配存在“不公平”的感受。根据零售商是否导入自有品牌以及制造商是否具有公平关切，有四种供应链模型，即：零售商不引入自有品牌，不考虑制造商公平关切(NN模型)；零售商引入自有品牌，不考虑制造商公平关切(SN模型)；零售商不引入自有品牌，考虑制造商公平关切(NF模型)；零售商引入自有品牌，考虑制造商公平关切（SF 模型)。以下将分别分析四种模型下的 Stackelberg博弈的均衡策略，以期找到对供应链双方而言都有利的策略组合。

# 1.1符号约定

在本文中将用到表1所示的符号。

表1模型参数定义  
Table1 Table of Notations   

<html><body><table><tr><td>参数</td><td>模型含义</td></tr><tr><td>@</td><td>制造商销售给零售商的产品批发价格</td></tr><tr><td>A</td><td>制造商品牌和零售商自有品牌市场基本需求</td></tr><tr><td>Cn,Cs</td><td>制造商产品和零售商自有品牌产品的制造成本</td></tr><tr><td>0</td><td>消费者对零售商自有品牌产品的认可度</td></tr><tr><td>α</td><td>制造商的公平关切程度</td></tr><tr><td>PnPs</td><td>制造商产品和零售商自有品牌产品的市场销售价格</td></tr><tr><td>qn,qs</td><td>制造商产品和零售商自有品牌产品的市场需求</td></tr><tr><td>πm,π,,πsc</td><td>制造商、零售商以及供应链的总利润</td></tr><tr><td>un,us</td><td>消费者购买制造商产品和零售商自有品牌产品的效用</td></tr><tr><td>Um</td><td>具有公平关切制造商的效用函数</td></tr></table></body></html>

# 1.2模型假设

a)零售商自有品牌产品一般为制造商品牌产品的替代性产品，在产品质量和消费者认可度上会低于制造商品牌产品[21]。假定消费者对于制造商品牌产品的估值为 $\nu$ ，而对零售商自有品牌产品的估值为 $\theta \nu$ ，且 $\theta \in \left[ 0 , 1 \right]$ ，即在同等条件下，消费者更愿意购买制造商品牌产品。这主要是因为制造商产品是全国性的品牌，在质量和口碑上更有保障。

b)参考 Mills 的消费者购买模型[21]，假设消费者对产品的估值在[0.A]上均匀分布，即 $\nu \sim \operatorname { U } [ 0 , A ]$ 。此时，消费者购买制造商品牌产品的效用为 $u _ { n } = { \left( \nu - p _ { n } \right) }$ ，购买自有品牌产品的效用为 $u _ { s } = \left( \theta \nu - p _ { s } \right)$ 。因此，消费者购买制造商品牌产品的条件为 $u _ { n } > 0$ 且 $u _ { n } > u _ { s }$ ，购买零售商自有品牌产品的条件为 $u _ { s } > 0$ 且 $u _ { s } > u _ { n }$ 。

c)本文在假设a)中假定制造商品牌产品质量高于零售商自有品牌产品，因而假设制造商品牌产品的成本大于自有品牌产品成本，即 $c _ { n } > c _ { s }$ 。与此类似，Bontems等人[22]认为制造商品牌与自有品牌有着不同的边际成本，并且这一成本会随着产品质量的提高而上升。Mills[21]假设制造商与自有品牌的可变成本相同，而制造商品牌产品需要进行市场推广，因而其固定成本大于自有品牌产品。而在实际生产销售中，零售商自有品牌价值链中的相对较低的成本主要来自于物流成本、交易成本、销售推广成本的节约。

d)公平关切下的制造商效用函数采用相对公平时的效用函数，即 $U _ { m } = \pi _ { m } - \alpha ( \pi _ { r } - \pi _ { m } )$ 。其中 $\alpha \ ( \alpha > 0 )$ 为制造商的公平关切程度系数， $\alpha$ 越大，表明制造商对公平的关切程度越深。Li等人[15]将效用函数设定为 $U _ { r } = \pi _ { r } - \alpha ( \gamma \pi _ { m } - \pi _ { r } )$ ，其中 $\alpha$ 表示不平等厌恶因素，即本文中的公平关切系数，》表示零售商认为的公平时，其利润应当是制造商的／倍。当 $\scriptstyle \gamma = 1$ 时，即为本文中的效用函数。

e)若制造商存在公平关切，则零售商为寻求与制造商长期稳定的供应链合作关系，将会考虑制造商的公平，即将制造商的公平关切纳入自己决策的考虑范围。

# 1.3需求函数和目标函数

a)在零售商未引入自有品牌时，市场上只有制造商品牌产品在销售。根据前文假设，消费者购买制造商品牌产品的效用为正时，即 $u _ { n } = \nu - p _ { n } > 0$ 时，消费者才会选择购买。据此可得 $q _ { n } = A - p _ { n }$ 。制造商的利润函数为 $\pi _ { m } = q _ { n } \left( \omega - c \right)$ ，因具有公平关切行为，其目标函数为 $U _ { m } = \pi _ { m } - \alpha ( \pi _ { r } - \pi _ { m } )$ ，而零售商目标函数为其利润函数 $\pi _ { r } = q _ { n } \left( p _ { n } - \omega \right)$

b)在零售商选择引入自有品牌时，市场上同时具有制造商品牌产品和自有品牌产品。消费者购买制造商品牌产品的效用为 $u _ { n } = \nu - p _ { n }$ ；购买自有品牌产品的效用为 $u _ { s } = \theta \nu - p _ { s }$ 。根据假设b)中的条件推导可得出制造商品牌产品和自有品牌产品的需求分别为

$$
q _ { n } = A - \frac { p _ { n } - p _ { s } } { 1 - \theta } , q _ { s } = \frac { \theta p _ { n } - p _ { s } } { \theta ( 1 - \theta ) } .
$$

此时制造商决策的目标函数为 $U _ { m } = \pi _ { m } - \alpha ( \pi _ { r } - \pi _ { m } )$ ，零售商因为新增了自有品牌这一收入来源，相应地，其目标函数应该变为 $\pi _ { r } = q _ { n } \left( p _ { n } - \omega \right) + q _ { s } \left( p _ { s } - c _ { s } \right)$

# 2 供应链博弈模型分析

分别用上标"NN"SN"NF""SF"来表示：零售商不引入自有品牌，制造商不具公平关切(NN模型)；零售商引入自有品牌，制造商不具公平关切（SN模型)；零售商不引入自有品牌，制造商具有公平关切(NF模型)；零售商引入自有品牌，制造商具有公平关切（SF模型)。以下分别分析四种模型下供应链成员的均衡策略。

# 2.1零售商不引入自有品牌，制造商不具公平关切（NN 模型）

此时，零售商选择不引入自有品牌，同时制造商不具公平关切行为，市场上只有制造商品牌产品。双方的博弈顺序为：零售商作为领导者首先决定制造商品牌产品的零售价格，随后制造商决定产品的批发价格。采用逆向递推法得到命题1中的结果。

命题1在NN 模型中，零售商与制造商的最优决策分别为 $p _ { n } ^ { N N } = \frac { 3 A + c _ { n } } { 4 }$ ， $\omega ^ { N N } = \frac { A + 3 c _ { n } } { 4 }$

推论1在 NN 模型中，制造商品牌产品的销售量为$q _ { n } ^ { N N } = \left( A - c _ { n } \right) / 4$ ；制造商、零售商以及供应链整体的利润水平分别为πm =(A-c）², ${ \mathrm {  ~ \sigma ~ } } ^ { \prime } = \frac { \left( A - c _ { n } \right) ^ { 2 } } { 1 6 } , \quad \pi _ { r } ^ { _ { N N } } = \frac { \left( A - c _ { n } \right) ^ { 2 } } { 8 } , \pi _ { s c } ^ { _ { N N } } = \frac { 3 \left( A - c _ { n } \right) ^ { 2 } } { 1 6 } \ ,$

由推论1可知，在NN模型中，零售商占去了供应链的总体利润2/3，而制造商仅仅占去了总利润的1/3。同一条供应链中的不同成员，由于渠道地位的差异，产生了较大的分配不均衡。对于供应链中处于弱势一方的制造商，对分配的结果可能具有“不公平"的感受。

# 2.2零售商引入自有品牌，制造商不具公平关切(SN 模型)

在 SN模型中，零售商选择引入自有品牌，制造商不具公平关切行为，市场上有两种相互竞争的产品供消费者选择。双方的博弈顺序为：零售商首先决定制造商品牌产品与其自有品牌产品的零售价格，制造商再依据零售商的决策制定其产品的批发价格。

命题2在 $\theta \in \left[ 0 , 1 \right]$ 上存在 $\theta ^ { * }$ 使得在 $[ 0 , \theta ^ { \ast } ]$ 上零售商不能引入自有品牌，在 $( \theta ^ { * } , 1 ]$ 上零售商可以引入自有品牌。

证明：利用零售商的利润函数构建拉格朗日函数，以自有品牌产品销量为正为约束条件可得

$$
\begin{array} { r } { \pi _ { r } ^ { S N } = q _ { n } \left( p _ { n } - \omega \right) + q _ { s } \left( p _ { s } - c _ { s } \right) + \mu 1 \left( \theta p _ { n } - p _ { s } \right) } \end{array}
$$

库恩一塔克条件为$\hat { \sigma } \pi _ { r } ^ { S N } / \hat { c } p _ { n } = 0 , \hat { \sigma } \pi _ { r } ^ { S N } / \hat { c } p _ { s } = 0 ,$ $\mu 1 ( \theta p _ { n } - p _ { s } ) { = } 0$ 。以下分两种情况$\mu 1 = 0$ 和 $\mu 1 > 0$ 来讨论。

a）当 $\mu 1 = 0$ 时，有 $\theta p _ { n } - p _ { s } { = } \frac { { - } A \theta ^ { 2 } - 2 c _ { s } } { 4 } { \ + } \frac { \theta ( A + c _ { n } + c _ { s } ) } { 4 } { > } 0$ ，即$\theta { > } \theta ^ { * }$ ， $\theta ^ { * }$ 为 $A \theta ^ { 2 } + 2 c _ { s }$ $- \theta { \left( A + c _ { n } + c _ { s } \right) } = 0$ 根。此时，零售商自有品牌产品的需求为正，零售商选择引入自有品牌。

b）当 $\mu 1 > 0$ 时，有 $\theta p _ { n } - p _ { s } = 0$ ，可解得$\mu 1 = \frac { A \theta ^ { 2 } - \theta ( A + c _ { n } + c _ { s } ) + 2 c _ { s } } { \theta ( 1 - \theta ) ( 2 - \theta ) } > 0$ ，即 $\theta { < } \theta ^ { * }$ 。此时，零售商自有品牌产品的需求为0，零售商不会引入自有品牌。证毕。\*

命题2表明，当消费者对自有品牌认可度较低时，零售商无法导入自有品牌产品。只有当消费者对自有品牌产品的认可度高于一定的临界值，零售商才能够成功导入自有品牌产品。此时，特别是对于价格比较敏感的消费者，更愿意选择相对低价的自有品牌产品。命题3则给出了SN模型中当零售商能导入自有品牌时，双方的均衡策略。

命题3在 SN 模型中，零售商和制造商的最优决策为$p _ { s } ^ { S N } = \frac { A \theta + c _ { s } } { 2 } , p _ { n } ^ { S N } = \frac { A \big ( 3 - \theta \big ) + c _ { n } + c _ { s } } { 4 } , \omega ^ { S N } = \frac { A \big ( 1 - \theta \big ) + 3 c _ { n } + c _ { s } } { 4 } .$

推论2在 SN 模型下，制造商品牌与自有品牌产品的销售量分别为 $q _ { n } ^ { S N } = \frac { A ( 1 - \theta ) - c _ { n } + c _ { s } } { 4 ( 1 - \theta ) } , q _ { s } ^ { S N } = \frac { - A \theta ^ { 2 } + \theta \big ( A + c _ { n } + c _ { s } \big ) - 2 c _ { s } } { 4 \theta ( 1 - \theta ) } .$ 制造商、零售商与供应链总体的利润为

$$
\pi _ { m } ^ { S N } = \frac { \left( A \theta - A + c _ { n } - c _ { s } \right) ^ { 2 } } { 1 6 ( 1 - \theta ) } ,
$$

$$
\pi _ { r } ^ { S N } = \frac { - A ^ { 2 } \theta ^ { 3 } + 2 A \theta ^ { 2 } \left( c _ { n } + c _ { s } \right) + \Psi \theta + 2 { c _ { s } } ^ { 2 } } { 8 \theta ( 1 - \theta ) } ,
$$

$$
\pi _ { s c } ^ { S N } = \frac { - A ^ { 2 } \theta ^ { 3 } + 2 A \theta ^ { 2 } \left( - A + 3 c _ { n } + c _ { s } \right) + \mathbf { M } \theta + 4 c _ { s } ^ { ~ 2 } } { 1 6 \theta ( 1 - \theta ) }
$$

其中,

$$
\Psi = A ^ { 2 } - 2 A c _ { n } - 2 A c _ { s } + { c _ { n } } ^ { 2 } - 2 c _ { n } c _ { s } - { c _ { s } } ^ { 2 } ,
$$

$$
\mathbf { M } = 3 A ^ { 2 } - 6 A c _ { n } - 2 A c _ { s } + 3 { c _ { n } } ^ { 2 } - 6 { c _ { n } } { c _ { s } } - { c _ { s } } ^ { 2 } .
$$

由命题3可以得到：对制造商产品来说，其批发价格与零售价格均是 $\theta$ 的减函数，当 $\theta$ 增大，即自有品牌产品与制造商品牌产品的替代性越强时，制造商品牌产品的批发价格与零售价格越低。表明自有品牌与制造商品牌之间的竞争较为激烈，制造商产品不得不通过降低价格来吸引消费者，此时消费者受益于两种产品之间的竞争。而对于自有品牌产品来说，其价格随产品替代水平的增加而增大，当替代性越强意味着消费者越偏好零售商自有品牌产品，此时对零售商越有利。然而，这势必会加重制造商的不公平感受。

# 2.3零售商不引入自有品牌，制造商具有公平关切行为（NF模型)

本模型中，零售商不导入自有品牌，制造商具有公平关切行为，此时市场上只有制造商品牌商品。博弈顺序为：零售商先根据其利润函数确定制造商品牌产品的零售价格，接着制造商根据其效用函数确定其产品的批发价格。采用逆向递推法求解得到以下命题。

命题4在 NF 模型下，制造商与零售商的最优决策分$\omega ^ { N F } = \frac { A ( 4 \alpha + 1 ) + c _ { n } ( 4 \alpha + 3 ) } { 4 ( 2 \alpha + 1 ) }$ $p _ { n } ^ { N F } = \frac { 3 A + c _ { n } } { 4 }$

推论3NF模型下，制造商品牌产品的销售量为$q _ { n } ^ { N F } = \left( A - c _ { n } \right) / 4$ ，制造商、零售商以及供应链总体的利润分别为

$$
\pi _ { m } ^ { N F } = \frac { ( 4 \alpha + 1 ) { ( A - c _ { n } ) } ^ { 2 } } { 1 6 ( 2 \alpha + 1 ) } ,
$$

$$
\pi _ { r } ^ { N F } = \frac { \left( \alpha + 1 \right) \left( A - c _ { n } \right) ^ { 2 } } { 8 { \left( 2 \alpha + 1 \right) } } , \pi _ { s c } ^ { N F } = \frac { 3 { \left( A - c _ { n } \right) } ^ { 2 } } { 1 6 } .
$$

零售商的零售价格并不会受到其不公平感受的影响。因此对于存在具公平关切制造商的供应链，产品市场价格不会受影响，供应链也不会产生额外利润。当零售商考虑制造商的不公平感受，制造商可以获得供应链分配水平的提升。当制造商越关注公平因素，制造商的利润会越高。而相应零售商的利润则会下降。且当 $\alpha { > } 1 / 2$ 时，制造商的利润会大于零售商利润。

# 2.4零售商引入自有品牌，制造商具有公平关切行为（SF模型)

当零售商选择引入自有品牌，同时制造商具有公平关切行为时，双方的博弈顺序为：零售商先决定制造商品牌产品与自有品牌产品的零售价格，然后，制造商确定其产品的批发价格。根据前文的需求函数计算可得以下命题。

命题5与模型SN一致，当 $\theta \in \left( \theta ^ { * } , 1 \right]$ 时，零售商可以导入自有品牌。且在SF 模型下，制造商和零售商的最优决策为

$$
p _ { n } ^ { S F } = \frac { A ( 3 - \theta ) + c _ { n } + c _ { s } } { 4 } ,
$$

$$
p _ { s } ^ { S F } = \frac { A \theta + c _ { s } } { 2 } , \omega ^ { S F } = \frac { \big [ A ( 1 - \theta ) + c _ { s } \big ] ( 4 \alpha + 1 ) + c _ { n } ( 4 \alpha + 3 ) } { 4 ( 2 \alpha + 1 ) } .
$$

推论4在SF模型下，制造商品牌与自有品牌产品的销量分别为： $q _ { n } ^ { S F } = \frac { A ( 1 - \theta ) - c _ { n } + c _ { s } } { 4 ( 1 - \theta ) } , q _ { s } ^ { S F } = \frac { - A \theta ^ { 2 } + \theta \left( A + c _ { n } + c _ { s } \right) - 2 c _ { s } } { 4 \theta ( 1 - \theta ) } .$ 制造商、零售商以及供应链总体利润分别为

$$
\begin{array} { l } { { \pi _ { m } ^ { s F } = \displaystyle \frac { ( 4 \alpha + 1 ) \big ( A \theta - A + c _ { n } - c _ { s } \big ) ^ { 2 } } { 1 6 \big ( 1 - \theta \big ) \big ( 2 \alpha + 1 \big ) } \mathrm { , } } } \\ { { \pi _ { r } ^ { s F } = \displaystyle \frac { - \big ( 3 \alpha + 1 \big ) A ^ { 2 } \theta ^ { 3 } + 2 A \theta ^ { 2 } \mathrm { K } + \Lambda \theta + 2 c _ { s } ^ { 2 } \big ( 2 \alpha + 1 \big ) } { 8 \theta \big ( 1 - \theta \big ) \big ( 2 \alpha + 1 \big ) } \mathrm { , } } } \\ { { \pi _ { s c } ^ { s F } = \displaystyle \frac { - A ^ { 2 } \theta ^ { 3 } + 2 A \theta ^ { 2 } \big ( - A + 3 c _ { n } + c _ { s } \big ) + \mathrm { M } \theta + 4 c _ { s } ^ { 2 } } { 1 6 \theta \big ( 1 - \theta \big ) } \mathrm { . } } } \end{array}
$$

其中， $\Lambda = \left( \alpha + 1 \right) \Psi + 2 A c _ { s } \left( 3 \alpha + 1 \right)$

$$
\mathrm { K } = \alpha A + c _ { n } \left( \alpha + 1 \right) + c _ { s } \left( 3 \alpha + 1 \right) .
$$

从命题5可以看出，当制造商具有公平关切时，并未影响零售商关于自有品牌的导入条件，说明即使制造商具有公平关切，零售商会通过转移支付来安抚制造商的情绪，但不会改变其关于自有品牌的策略。在SF 模型中，对制造商品牌产品来说，其批发价格是公平关切参数 $\alpha$ 的增函数，是产品替代水平 $\theta$ 的减函数；其销售量是 $\theta$ 的减函数。表明制造商的公平关切促使其提高产品的批发价格，而自有品牌产品的进入又迫使制造商降低批发价格，目前的批发价格是制造商两相权衡下的结果。制造商品牌产品的销量不受公平关切参数的影响，但会随产品替代水平的提高而减少。对于零售商自有品牌产品来说，其零售价格和销售量均随 $\theta$ 的增大而增大，说明自有品牌对制造商品牌模仿程度越高，对零售商越有利。

# 3 模型比较及结果分析

第2章得到四种模型下的最优决策以及供应链各成员的利润，在本部分将分别对比不同模型下的决策和利润，分析零售商引入自有品牌和制造商存在公平关切对双方的决策及利润产生的影响。

# 3.1制造商公平关切对供应链的影响

分别对比NF 模型与NN模型，SF 模型与SN 模型，分析制造商公平关切对与供应链产生的影响，所得结论归纳为命题6。

# 命题6

$$
\omega ^ { I F } > \omega ^ { I N } , \ p _ { n } ^ { I F } = p _ { n } ^ { I N } , p _ { s } ^ { S F } = p _ { s } ^ { S N } , \quad q _ { n } ^ { I F } = q _ { n } ^ { I N } , q _ { s } ^ { S F } = q _ { s } ^ { S N } \ ;
$$

b) $\pi _ { m } ^ { I F } > \pi _ { m } ^ { I N } , \pi _ { r } ^ { I F } < \pi _ { r } ^ { I N } , \pi _ { s c } ^ { I F } = \pi _ { s c } ^ { I N }$

注： $\mathrm { I } { = } \mathrm { N }$ 或S。 $\mathrm { I } { = } \mathrm { N }$ 代表无自有品牌； $\mathrm { I } { = } \mathrm { S }$ 代表有自有品牌。

从命题6中可以看到，无论零售商是否引入自有品牌，制造商的公平关切都会使它会提高制造商品牌产品的批发价格；而零售商的最优定价决策不变，产品的销量也没有变化。制造商因为提高了批发价格而使自身利润增加，零售商利润减少，但供应链总利润不变。零售商将一部分通过销售制造商品牌产品所获得的利润转移给制造商，满足制造商的公平关切诉求，以寻求更加长远广泛的合作；但其引入的自有品牌产品的销量、价格、利润没有因为制造商的公平关切行为而有所改变。

# 3.2零售商引入自有品牌对供应链的影响

对比SN 模型与NN 模型、SF 模型与NF模型，可以分别得到在制造商考虑和不考虑公平关切时，零售商引入自有品牌对供应链产生的影响。所得结论可见命题7。

# 命题7

a) $p _ { n } ^ { S I } < p _ { n } ^ { N I }$ ， $\omega ^ { S I } < \omega ^ { N I }$ ·b)当 $c _ { s } > \theta c _ { n }$ ， $q _ { n } ^ { S I } > q _ { n } ^ { N I }$ ；反之， $q _ { n } ^ { S I } < q _ { n } ^ { N I }$ ·c) $\pi _ { r } ^ { S I } > \pi _ { r } ^ { N I }$ $\pi _ { s c } ^ { S I } > \pi _ { s c } ^ { N I }$ ；当$\theta \in [ \theta ^ { * } , \bar { \theta } ) , \ \pi _ { m } ^ { S I } < \pi _ { m } ^ { N I } ; \ \theta \in ( \bar { \theta } , 1 ] , \ \pi _ { m } ^ { S I } > \pi _ { m } ^ { N I }$

注： $_ \mathrm { I = N }$ 或F。 $\mathrm { I } { = } \mathrm { N }$ 不存在公平关切； $\mathrm { I } { = } \mathrm { F }$ 存在公平关切.

证明

a)制造商利润。比较 SF 模型与 NF 模型中制造商的利润 $\pi _ { m } ^ { S F } - \pi _ { m } ^ { N F } = \frac { ( 4 \alpha + 1 ) F ( \theta ) } { 1 6 ( 1 - \theta ) ( 2 \alpha + 1 ) }$ 其中$\boldsymbol { F } ( \theta ) = \left( - A ^ { 2 } - 2 A c _ { s } + { c _ { n } } ^ { 2 } \right) \theta + A ^ { 2 } \theta ^ { 2 } + 2 A c _ { s } - 2 c _ { n } c _ { s } + { c _ { s } } ^ { 2 }$ 易知 $F ( 0 ) > 0$ 和$F ( 1 ) > 0$ ， $F ( \theta )$ 为一二次函数，且判别式为$\left( A - c _ { n } \right) ^ { 2 } \left( A ^ { 2 } + 2 A c _ { n } - 4 A c _ { s } + { c _ { n } } ^ { 2 } \right) > 0$ ．因此在 $\theta \in ( 0 , 1 )$ 间必然存在 $\overline { { \theta } }$ 使得 $F \left( { \overline { { \theta } } } \right) = 0$ 且由于 $\theta { > } \theta ^ { * }$ 舍去较小的根，此时可知当$\theta ^ { * } < \theta < \overline { { \theta } }$ 时 $F ( \theta ) { < } 0$ 即 $\pi _ { m } ^ { S F } < \pi _ { m } ^ { N F }$ ，当 $\scriptstyle { \overline { { \theta } } } < \theta < 1$ 时 $F ( \theta ) > 0$ 即$\pi _ { m } ^ { S F } > \pi _ { m } ^ { N F }$ （20

同样，比较 SN 模型与NN 模型中的制造商利润（ $\pi _ { m } ^ { S N } - \pi _ { m } ^ { N N } ,$ ，即分析在制造商不考虑公平关切时，自有品牌对制造商利润的影响。剩余分析过程及结果同制造商考虑公平时类似。综上所述，无论制造商是否考虑公平关切，当$\theta ^ { * } < \theta < \overline { { \theta } }$ 时 $F ( \theta ) { < } 0$ 即 $\pi _ { m } ^ { I F } < \pi _ { m } ^ { I F }$ ，当 $\scriptstyle { \bar { \theta } } < \theta < 1$ 时 $F ( \theta ) > 0$ 即$\pi _ { m } ^ { I F } > \pi _ { m } ^ { I F }$ 。

b)零售商利润。制造商不考虑公平时， $\pi _ { r } ^ { S N } - \pi _ { r } ^ { N N }$ 的结果中分母小于0，分子为关于 $\theta$ 的一元三次函数，为分析方便，令 $c _ { s } = 0$ ，可将分子化简为 $A ^ { 2 } \theta ^ { 3 } - A ^ { 2 } \theta ^ { 2 } - c _ { n } ^ { 2 } \theta ^ { 2 }$ ，此时，分析可得该函数有两个零点： $\scriptstyle \theta = \mathrm { C }$ 或 $\textstyle { \left( A ^ { 2 } + { c _ { n } } ^ { 2 } \right) } / { A ^ { 2 } }$ ，因此在制造商不考虑公平时，在 $\scriptstyle \theta \in \left[ 0 , 1 \right]$ 上，引入自有品牌会使零售商的利润增大，即 $\pi _ { r } ^ { S N } > \pi _ { r } ^ { N N }$ 。同理，在制造商考虑公平时，可以得到 $\pi _ { r } ^ { S F } - \pi _ { r } ^ { N F }$ 的结果有两个零点： $\theta { = } 0 \not \equiv \not \zeta 1 { + } c _ { n } { } ^ { 2 } \left( \alpha { + } 1 \right) / \left[ A ^ { 2 } \left( 3 \alpha { + } 1 \right) \right]$ ，因此在制造商考虑公平时，在 $\scriptstyle \theta \in \left[ 0 , 1 \right]$ 上，引入自有品牌会使零售商的利润增大，即 $\pi _ { r } ^ { S F } > \pi _ { r } ^ { N F }$ 。

c)供应链总利润。前文推得 $\pi _ { s c } ^ { S F } = \pi _ { s c } ^ { S N }$ ， $\pi _ { s c } ^ { N N } = \pi _ { s c } ^ { N F }$ ,通过计算有$\pi _ { s c } ^ { S F } - \pi _ { s c } ^ { N F } = \pi _ { s c } ^ { S N } - \pi _ { s c } ^ { N N }$ 。结果中分母小于0。同样令 $c _ { s } = 0$ ，可将分子化简为 $- \big ( A ^ { 2 } + 3 { c _ { n } } ^ { 2 } \big ) \theta ^ { 2 } \ + A ^ { 2 } \theta ^ { 3 }$ ，此时，分析可得该函数拥有两个零点：即 $\scriptstyle \theta = 0 \not \exists \not \mathrm { X } 1 + 3 c _ { n } ^ { 2 } / A ^ { 2 }$ 。因此，在 $\theta \in \left[ 0 , 1 \right]$ 上，自有品牌的引入会增加整条供应链的总利润，即 $\pi _ { s c } ^ { S F } > \pi _ { s c } ^ { N F }$ ， $\pi _ { s c } ^ { S N } > \pi _ { s c } ^ { N N }$ 证毕。

从命题7中可以发现，无论制造商是否具有公平关切，只要零售商引入自有品牌，必然会导致品牌之间的竞争，从而促使制造商品牌产品市场价格和批发价格的下降。自有品牌的进入会抢夺制造商的市场，但制造商产品的销量却不一定下降。一方面，制造商会通过降低价格来提高产品的吸引力。另一方面，自有品牌产品会吸引部分对价格比较敏感的消费者，当自有品牌产品的成本非常小时，其定价的优势会抢走部分制造商品牌的销售量；而当自有品牌产品的成本优势不高时，自有品牌的出现反而促进了制造商产品的销售。有意思的是，自有品牌的引入提高了零售商和供应链总体的利润水平。这主要是因为自有品牌的出现降低了供应链的双边际化效应。对制造商而言，当产品替代率较小时，自有品牌会对制造商品牌产品造成冲击，使制造商利润的减少；当产品替代率较高时，自有品牌反而会使制造商利润增加。因此，零售商对于制造商品牌模仿程度不高时，对制造商不利，而两种产品的替代率很大时，反而出现相互促进的现象，供应链总利润以及双方利润同时得到增加。

命题8在 $\theta \in [ 0 , \theta ^ { \ast } ]$ 时，无论制造商是否具有公平关切，零售商的最优策略为“不引入自有品牌”；在 $\theta \in ( \theta ^ { * } , 1 ]$ 时，无论制造商是否具有公平关切，零售商的最优策略为“引入自有品牌”。

无论制造商是否具有公平关切行为，并不会改变领导型零售商关于自有品牌的战略选择。零售商的战略选择只与消费者对自有品牌的偏好程度相关。当消费者对自有品牌的偏好度较低时，零售商不会引入自有品牌，而当消费者对自有品牌的偏好度较高时，零售商可以引入自有品牌。

# 4 结束语

本文研究了考虑制造商公平关切下强势零售商自有品牌导入问题，对比了四种模型下，制造商与零售商的最优决策，找到了供应链双方Stackelberg博弈的均衡。求解得到四种模型下制造商与零售商的最优决策；通过模型比较分析，研究了制造商公平关切程度以及消费者对自有品牌的认可度对双方决策和利润的影响；最后，得到了不同条件下制造商与零售商博弈的均衡策略组合。

研究发现制造商考虑公平对于供应链的影响主要表现在：它不会改变供应链总体的利润，只会调节利润在渠道上的分配。无论零售商是否引入自有品牌，制造商考虑公平关切都会提高其产品的批发价格，而不影响两种产品的零售价格和销售量，这就使得供应链的总利润不变，零售商将通过接受制造商提高批发价的行为，将一部分利润转让给制造商。

从供应链的角度来看，无论制造商是否考虑公平，零售商引入自有品牌对供应链产生的影响基本类似。引入自有品牌会迫使制造商抬高批发价格以平衡自有品牌对其带来的冲击；同时，零售商会降低制造商品牌产品的零售价格，这是两种产品相互竞争的结果。最后，引入自有品牌会使供应链总体的利润和零售商的利润增加。

# 参考文献：

[1]Hara R,Matsubayashi N.Premium store brand: product development collaboration between retailers and national brand manufacturers [J]. International Journal of Production Economics,2017,185(3): 128-138.   
[2]Fornari D,Fornari E,Grandi S,et al.Leading national brands facing store brands competition: Is price competitiveness the only thing that matters?[J].Journal of Retailing & Consumer Services,2O16,30(5): 234-241.   
[3]Rubio N,Villasenor N,Yagie M J.Creation of consumer loyalty and trust in the retailer through store brands:The moderating efect of choice of store brand name [J].Journal of Retailing & Consumer Services,2017,34(1): 358-368   
[4]Liu Richie L, Sprott D E,Spangenberg ER,et al. Consumer preference for national vs.private brands: the influence of brand engagement and self-concept threat [J]. Journal of Retailing & Consumer Services,2018, 41 (3): 90-100.   
[5]Chung H,Lee E.Effect of store brand introduction on channel price leadership:An empirical investigation[J].Journal of Retailing,2017, 94(1): 21-32.   
[6]Chung H, Eunkyu L. Store brand quality and retailer's product line design [J]. Journal of Retailing,2017,93(4):527-540.   
[7]Choi S,Fredj K.Price competition and store competition: Store brands Vs.national brand [J]. European Journal of Operational Research,2013, 225(1): 166-178.   
[8] Fang Xiang, Gavirneni S,Rao VR. Supply chains in the presence of store brands [J]. European Journal of Operational Research,2O13,224 (2): 392-403.   
[9]Jin Yannan，Wu Xiaole,Hu Qiying.Interaction between channel strategy and store brand decisions [J]. European Journal of Operational Research,2016,256 (3): 911-923.   
[10] Nalca A，Boyaci T,Ray S. Brand positioning and consumer taste information [J].European Journal of Operational Research,2018, 268(2): 555-568.   
[11]李凯，万凯，严建援.多制造商情境下考虑自有品牌模仿策略的渠道 博弈分析[J]．系统工程,2015,33(10):22-27.(LiKai,Wan Kai,Yan Jianyuan.Channel game analysis of private brand imitation strategy under multi-manufacturer situation[J]. System Engineering,2015,33 (10): 22-27.)   
[12]李海，崔南方，徐贤浩.零售商自有品牌与制造商直销渠道的互动博 弈问题研究[J].中国管理科学,2016,24(1):107-115.(Li Hai,Cui Nanfang,Xu Xianhao.Study on the interactive game between retailer's store brand and manufacturer's direct selling channel [J].Chinese Journal of Management Science,2016,24(1):107-115.)   
[13]杜少甫，朱贾昂，高冬.Nash 讨价还价公平参考下的供应链优化决 策[J]．管理科学学报，2013，16(3):68-72.(Du Shaofu，Zhu Jiaang, Gao Dong. Nash bargain fair reference to the supply chain optimization decisions [J].Journal of Management Science in China,2O13,16(3): 68-72.)   
[14]张克勇，吴燕，侯世旺．具公平关切零售商的闭环供应链差别定价 策略研究[J].中国管理科学，2014，22(3):51-58.(Zhang Keyong, Wu Yan,Hou Shiwang.A study on differential pricing strategy for closed-loop supply chain with retailer’s fair concern [J].Chinese Journal of Management Science,2014,22(3):51-58.)   
[15] Li Qinghua,Li Bo.Dual-channel supply chain equilibrium problems regarding retail servicesand fairnessconcerns[J].Applied Mathematical Modeling,2016,40(15-16):7349-7367.   
[16] Yang Jing,Xie Jinxing,Deng Xiaoxue,et al. Cooperative advertising in a distribution channel with fairness concerns[J].European Journal of Operational Research,2013,227(2):401-407.   
[17] Qin Fei,Mai Feng,Fry Michael J,et al.Supply-chain performance anomalies: fairness concerns under private cost information [J]. European Journal of Operational Research,2016,252(1):170-182.   
[18] Nie Tengfei,Du Shaofu.Dual-fairness supply chain with quantity discount contracts [J].European Journal of Operational Research,2016, 258(2): 491-500.   
[19] Cui HT,Raju J S,Zhang ZJ.Fairness and channel coordination [J]. Management Science,2007,53(8):1303-1314.   
[20] Caliskan-Demirag O,Chen Youhua,Li Jianbin.Channel coordination under fairness concerns and nonlinear demand [J].European Journal of Operational Research,2010,207(3):1321-1326.   
[21] Mills DE.Why retailers sell private labels [J].Journal of Economics& Management Strategy,2010,4(3): 509-528.   
[22]BontemsP,Monier-Dilhan S,Réquillart V. Strategic effects of private labels [J].European Review of Agricultural Economics,2Ooo,26(2): 147-165.