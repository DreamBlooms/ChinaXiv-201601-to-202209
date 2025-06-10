# 谎报行为下基于区块链的物流服务商道德风险防范研究

李军祥，张志(上海理工大学 管理学院，上海 200093)

摘要：考虑以一个电商平台和一个第三方物流服务商构成的两级电商供应链为研究对象，针对第三方物流服务商完全掌控自身物流服务水平而引发的道德风险问题，分析采用区块链技术对防范第三方物流服务商道德风险的策略。通过借助以区块链技术为基础的物流服务水平监控系统，考虑采用区块链技术和不采用区块链技术两种情景，分别建立分散决策下电商平台与第三方物流服务商之间的 Stackelberg 博弈模型，研究区块链技术应用前后供应链利润的变化情况以及与技术成本投入的关联性，最后通过数值分析验证结论的正确性。结果表明：当区块链技术的成本投入控制在一定的范围内时，应用该技术可以有效降低第三方物流服务商存在的道德风险，提高整个供应链利润的同时促进供应链各节点企业收益的有效提升，助力供应链的健康有序发展。

关键词：区块链；物流服务水平；道德风险；Stackelberg博弈中图分类号：F204;TP31 doi:10.19734/j.issn.1001-3695.2020.05.0085

Research on prevention of moral hazard of logistics service providers based on blockchain

Li Junxiang, Zhang Zhi† (BusinessSchool,UniversityofShanghai for Science&Technology,Shanghai 2Ooo93,China)

Abstract: Considering the two-level e-commerce supply chain composed of an e-commerce platform and a third-party logisticsservice provideras theresearchobject,aiming atthe moral hazard problemcausedbythethird-partylogisticsservice provider's completecontrolofitsown logistics service level,this paperanalyzes thestrategyofusing blockchain to prevent themoralhazardofthethird-partylogisticsservice provider Withthehelpofthelogisticsservicelevelmonitoringframework basedonblockchain,consideringthetwoscenariosofadopting blockchainandnotadopting blockchain,the Stackelberggame model between e-commerce platformand the third partylogistics service provider under decentralized decision-making is established,andthechangesofsupplychainprofitsbeforeandaftertheapplicationof blockchainandthecorrelationwith technologycost inputare studied.Afterthat,thecorectnessoftheconclusionisverifiedbynumericalanalysis.Theresults showthat when the cost inputof blockchain iscontrolled within acertainrange,the applicationof this technologycan efectivelyreducethe moralhazardofthe third-partylogisticsservice providers,improve theprofitsofthewholesupplychain, promotethe improvementofthe profits ofeach nodeofthesupplychain,andhelpthehealthyandorderlydevelopmentofthe supply chain.

Key words: blockchain; logistics service level; moral risk; Stackelberg game

# 0 引言

随着国内第三方物流行业的深入发展，越来越多的企业将非核心的物流业务外包给第三方物流服务商，然而第三方物流服务商往往会隐藏私有信息或行为以最大化自己的利润，夸大自身物流服务水平损害委托方利润的行为，而委托方因信息不对称无法对物流配送的过程进行实时监控，并且配送契约中无法标明第三方物流服务商保障服务水平的努力程度，故第三方物流服务商可能借机降低成本投入，即产生道德风险。要想治理道德风险，监督和激励是必不可少的，但治理成本代价高昂，故而违规操作损害委托方利益的行为依旧发生。因此，迫切需要新方法和新技术来解决此类问题。而区块链技术的出现为防范物流服务商的道德风险带来了创新的可能性。区块链1的共识信任机制、分散治理以及可追溯等特性，能够有效应对第三方物流服务商的道德风险。借助区块链标准化的规范和协议[2]，以不可窜改的信息和可追踪的记录为基础，实时掌握以及事后追踪第三方物流服务商的动态和责任。区块链技术将传统的集中式系统进一步发展为多中心或分散式系统，使不同利益集团在同一系统中权力共享，有助于降低利益集团机会主义的发生概率[3]。例如：全链通有限公司提出工业制造业供应链协同应用，建立了基于区块链的以合同签订和履约跟踪为核心的企业信用机制和基于区块链的质量保障能力和履约综合能力认证应用，解决了多方数据共享的信任问题，实现供应链透明化管理。

目前针对第三方物流服务商道德风险的防范主要是基于委托代理理论进行分析，很少涉及到信息技术的应用研究，主要有朱立龙等[4基于委托代理理论,研究了信息不对称条件下道德风险对供应商的质量预防以及采购商的质量评价决策的影响，并对道德风险值的影响因素进行了有效分析；陈玲[5]研究了在第三方物流企业能力类型和努力水平均不可观测条件下，构建第三方物流合作契约激励模型，探究了能够选择合适的第三方物流企业并激励其努力工作的一般性合作契约激励机制；徐伟[考虑风险偏好和道德风险，对外包激励模型按单、双边道德风险进行扩展分析，并深入探讨了委托方和受托方风险态度的博弈策略；徐鹏等[运用委托代理理论,从供应链核心企业协助银行及与银行合作两个角度，研究银行对第三方物流的激励监督问题；王崇光等[8研究了基于博弈双方有限理性的假设前提上,构建生鲜电商与第三方物流企业的道德风险动态演化博弈模型；Huang等[9]研究了委托代理框架下的外包物流风险管理问题，提出基于交货质量的契约，以激励第三方物流为外包任务作出最佳努力；Jiang等[10]研究针对第三方物流供应商的激励机制，既能避免道德风险行为，又能促进服务绩效不断提高。

区块链技术的集成应用对新的技术革新和产业变革具有重要作用，区块链的分布式账本、非对称加密、共识机制以及智能合约等核心技术，能够有效串联供应链上下游企业信息，通过区块链可实时掌握货物运输过程的具体情况，确保交易信息的真实可靠[1]，能够有效解决激励措施的弊端。目前有关区块链的集成应用研究主要包括：张夏恒[12]研究借助区块链技术搭建授信融资、采购资金融资、白条、仓单质押融资、跨企业积分兑换等,致力于实现时间缩短、成本降低、品质提高、需求满足的供应链管理目标；邓爱民等[13]结合供应链保理业务相关理论,对区块链技术与供应链保理业务进行了耦合分析，提出了区块链智能合约技术在供应链保理业务中的具体应用场景；范贤丽等[14]针对粮食供应链中信息共享时各主体面临的隐私问题,设计研究基于区块链和星际文件系统技术的隐私保护系统；尤瑶等[15]为解决数字化资产背景下的交易描述及溯源问题,提出一种基于区块链的数字化资产交易模型和基于交易链的混合索引机制；Minjae等[16]研究将区块链和智能合约应用于供应链管理系统的价格跟踪部分，提出了一个保证产品分销结构透明度的系统，通过在区块链网络中自动存储分发详细信息和更安全地管理信息来降低管理成本。Schmidt 等[17]研究区块链对机会主义行为、环境和行为不确定性的限制作用，能够降低交易成本，因为它允许透明和有效的交易。上述文献涉及道德风险防范的研究主要围绕被动的激励措施，效果有待考验，区块链技术与供应链管理的集成应用将实现由被动转换为主动，弥补被动激励的弊端，更具考验性。

综上所述，目前的研究很少涉及借助区块链技术防范第三方物流服务商的道德风险，但区块链技术本身的特性又能够很好的防范道德风险。故构建以电商平台和第三方物流服务商组成的两级供应链，分别分析不采用区块链时道德风险度以及采用区块链技术时技术成本投入和共担比例对供应链最优决策的影响。最后通过数值实验分析道德风险度、区块链技术成本投入、货运成本弹性系数、价格弹性系数以及物流服务水平弹性系数对销售价格、委托价格、货运量、货运成本以及供应链双方利润和总利润的影响，确定实现道德风险防范的区块链技术成本投入范围，打造良好的供应链环境。

# 1基于区块链的物流服务水平监控系统架构

构建基于区块链的物流服务水平监控系统架构，组建新的供应链物流系统，保证信息透明度以及服务水平可控。除了供应链上的企业外，该框架还包括区块链、智能合约和各种物联网传感器，区块链提供带有货物质量信息和物流服务水平信息的分布式账本，智能合约为该系统提供隐私保护、自动化和智能化，而物联网传感器则从现实世界收集各种数据。

该框架和相应的体系结构根据功能的不同分为四层。如图1所示，底层是物联网的传感器层。物流过程中利用GPS定位产品，利用RFID技术记录物流交易信息。考虑到RFID成本相对较高，在精度标准不高、数据类型不多的情况下，条码可以在一些过程中交替使用。此外，还将使用各种传感器收集温度、振动、湿度等信息[18,19]，判断物品配送需求是否达标。最后，考虑到许多企业都有自己的信息系统，开发一些接口从这些不同的信息系统获取信息更为有效[20]。

![](images/0344fda92226a3a557473bbb564ee32801456b0f5775401896c49b0ce7f17c0d.jpg)  
图1基于区块链的物流服务水平监控系统架构  
Fig.1Architecture of logistics service level monitoring system based on blockchain

区块链分布式数据库提供货物质量数据和物流服务水平数据，所有的企业都有一份关于供应链的数据，包括电商平台、第三方物流服务商以及客户，非对称加密技术保证节点的身份信息无须公开，时间戳技术保证交易顺序，共识机制保证共同验证交易信息的合法性，智能合约被用来实施物流服务水平控制，提高供应链的效率。

合约层强调仅仅数据共享是不够的，以上各层的数据收集不仅有利于数据共享，而且有助于服务水平控制和提高供应链效率，数据共享的首要问题可能是隐私问题，数据共享需要考虑隐私问题，由于分散型供应链双方独立决策，为了自身的竞争优势，有些信息需要保密。因此，数字身份被用来控制数据的访问权限，智能合约具有实时的服务水平数据，可以利用物流数据进行实时的服务水平监控，智能合约可以自动规划物流，此外，利用交易数据和智能合约，商业合约可以自动高效地执行智能合约，帮助客户将需求从物流服务商传递给电商平台。

业务层包括企业的各种经营活动，电商平台作为博弈的主体，在区块链的支持下，供应链各节点企业都能够对物流服务水平进行控制和管理，还可根据智能合约提供的建议，就采购和委托活动作出决定，从而得到Stackelberg博弈的均衡解。

# 2 问题描述与模型假设

# 2.1问题描述

考虑由一个电商平台(R)和一个第三方物流服务商(L)构成的两级供应链，电商平台向客户销售某种产品，产品由第三方物流服务商配送交付给客户。电商平台首先会根据产品的单位生产成本 $\mid c \mid$ 以及市场情况确定产品的单位市场售价$p$ ，并以每单 $w$ 的价格委托第三方物流服务商在其约定的服务水平要求下进行配送，然后第三方物流服务商再依照电商平台提供的单位委托价格确定自身所要投入的单位货运成本$\boldsymbol { c } _ { L }$ ，但由于物流服务水平为第三方物流服务商的私有信息，可能会偷懒以降低物流配送过程中的努力程度，即存在道德风险。 $\varphi ( c _ { L } )$ 表示契约协定的物流服务水平， $\mu ( 0 \leq \mu < 1 )$ 表示第三方物流服务商的道德风险度， $\varphi \big ( ( 1 - \mu ) c _ { L } \big )$ 表示产生道德风险下的物流服务水平。

因此，借助以区块链技为基础的物流服务水平监督框架体系，可以有效助力电商平台准确掌握物流配送过程中的相关情况，实时查阅第三方物流服务商的服务水平是否达标，避免道德风险的发生而给企业带来的损失。区块链技术在防范道德风险的同时也会增加成本，在此不考虑区块链技术应用前期的固定成本投入，只考虑对货物物流服务水平单次监测的区块链技术投入成本 $\boldsymbol { c } _ { B }$ 。假设当电商平台以及第三方物流服务商采用区块链技术时，道德风险度 $\scriptstyle \mu = 0$ ，第三方物流服务商必须将货物运输中的相关参数信息准确地上传至基于区块链技术的物流服务水平监督系统，区块链技术去中心化以及信息不可窜改等特性，能够有效抑制过度中心化信息被窜改的可能性，第三方物流服务商存在的道德风险得到明显改善。

# 2.2模型假设

a）供应链各节点企业均优先考虑自身利益的最大化，并且处理相关问题时均考虑过决策所带来的各种影响，保持完全理性。电商平台具有充分的实力作为Stackelberg博弈的领导者。

b）假设产品的市场需求同时受电商平台的产品销售价格和第三方物流服务商的物流服务水平的影响，可得市场的需求函数为 ${ } ^ { 2 1 ] } Q = \kappa p ^ { - x } \varphi ( c _ { L } ) ^ { y }$ ，其中 $\kappa$ 表示基础市场的需求，$x \left( x \ge 1 \right)$ 表示产品销售价格变动对需求函数的影响系数，$y \ ( 0 < y < 1 )$ 表示物流服务水平变动对需求函数的影响系数。需要指出，依据Kaya 等[22]的假设，第三方物流服务企业的物流服务水平影响产品需求。另外， $0 < c + w < p , c _ { L } < w < p$ 。

c）假设物流服务水平与货运成本投入相关，单位物流服务水平与其自身成本投入成正比。因此其物流服务水平函数可以表示为 $\left[ 2 3 \right] _ { \varphi \left( c _ { L } \right) = } \left( \frac { 2 c _ { L } } { \eta } \right) ^ { 1 / 2 }$ (2)²，其中n(n>0)表示物流服务水平随物流成本变化而变化的弹性系数。

d）假设采用区块链的成本投入由电商平台和第三方物流服务商共同承担，考虑到能够有效降低电商平台的损失，故假设电商平台的承担比例为 $t ( 0 . 5 < t \leq 1 )$ ，则第三方物流服务商承担的比例为 $_ { 1 - t }$ 。

# 2.3符号说明

模型参数以及决策变量符号说明如表1所示。

表1相关符号说明与定义  
Tab.1Description and definition of relevant symbols   

<html><body><table><tr><td colspan="2">模型参数</td><td colspan="2">决策变量</td></tr><tr><td>c</td><td>产品的单位生产成本</td><td>Q</td><td>市场的需求量即货运量</td></tr><tr><td>K</td><td>市场基础需求规模</td><td>p</td><td>电商平台的单位产品销售价格</td></tr><tr><td>μ</td><td>道德风险度</td><td>W</td><td>单位委托价格</td></tr><tr><td>CB</td><td>区块链单位成本投入</td><td>φ(c)</td><td>物流服务水平</td></tr><tr><td>X</td><td>价格弹性系数</td><td></td><td>ct第三方物流服务商的单位货运成本</td></tr><tr><td>y</td><td>物流服务水平弹性系数</td><td>IR</td><td>电商平台的利润</td></tr><tr><td>n</td><td>货运成本弹性系数</td><td>I</td><td>第三方物流服务商利润</td></tr><tr><td></td><td>t区块链成本投入分摊比例</td><td>IIsc</td><td>供应链的总利润</td></tr></table></body></html>

本文规定"\*"表示最优解，上标“ $\mathbf { \Omega } _ { N }$ ”表示不采用区块链技术，“B”表示采用区块链技术，下标“R”表示电商平台，“ $\textbf { \em L }$ ”表示第三方物流服务商，“ $s c$ ”表示整体供应链。

# 3 模型构建与求解

分散决策时供应链双方各自独立决策，以实现自身利益最大化为最终目标，作为代理方的第三方物流服务商时常发生损害委托方利润的行为。因此考虑不采用区块链技术以及采用区块链技术两种情况，分析通过区块链技术防范道德风险的应用条件，有效防范道德风险的再次发生。

# 3.1不采用区块链技术时的最优策略

传统电商供应链模式[24\~28]，尽管事先第三方物流服务商就物流服务水平与电商平台达成契约，但是第三方物流服务商为了自身利益会偷懒私自降低货运的成本至 $( 1 - \mu ) c _ { L }$ ，即存在道德风险，致使实际物流服务水平下滑，市场需求动荡，因此需求降至为 $\tilde { Q } = \kappa p ^ { - x } \varphi \big ( ( 1 - \mu ) c _ { L } \big ) ^ { y }$ ；而电商平台无法掌握物流运输的真实情况，依旧会依照契约约定的服务水平备货，进而导致货物积压产生的亏损为 $( Q - \tilde { Q } ) c$ 。此时以电商平台为主导的Stackelberg博弈模型：

$$
\operatorname * { m a x } _ { p > 0 , w > 0 } \ \Pi _ { R } ^ { \scriptscriptstyle N } ( p , w ) = ( p - c - w ) Q - ( Q - \tilde { \bar { Q } } ) c
$$

$$
\operatorname* { m a x } _ { Q > 0 } ~ \Pi _ { L } ^ { N } ( Q ) = \big ( w - ( 1 - \mu ) c _ { L } \big ) Q
$$

结合前文假设可知 $Q = \kappa p ^ { - x } \left( 2 c _ { L } / \eta \right) ^ { y / 2 }$ ，故其关于货运成本 $\boldsymbol { c } _ { L }$ 的反函数为 $c _ { L } = \frac { \eta Q ^ { 2 / y } } { 2 \kappa ^ { 2 / y } p ^ { - 2 x / y } }$ ，将其代入式(2)中可得;

$$
\Pi _ { L } ^ { N } ( Q ) = \left( w - ( 1 - \mu ) \frac { \eta Q ^ { 2 / y } } { 2 \kappa ^ { 2 / y } p ^ { - 2 x / y } } \right) Q
$$

依据逆向归纳法，可以求出第三方物流服务商的货运成本以及货运量。因为二阶导数 $\frac { \widehat { \sigma } ^ { 2 } \Pi _ { L } ^ { \cal N } } { \widehat { \sigma } Q ^ { 2 } } = - \left( \frac { 2 + y } { y ^ { 2 } } \right) \left( \frac { ( 1 - \mu ) \eta Q ^ { ( 2 / y ) - 1 } } { \kappa ^ { 2 / y } p ^ { - 2 x / y } } \right) < 0$ ，所以存在最优解，令其一阶导数 $\hat { \sigma } \Pi _ { L } ^ { N } / \hat { \sigma } Q = 0$ ，可得：

$$
Q = \left( \frac { 2 y w \kappa ^ { 2 / y } p ^ { - 2 x / y } } { \eta ( 1 - \mu ) ( 2 + y ) } \right) ^ { y / 2 } ; c _ { L } = \frac { y w } { ( 1 - \mu ) ( 2 + y ) }
$$

将式(4)代入式(1)可得：

$$
\begin{array} { l } { \Pi _ { R } ^ { N } ( p , w ) { = } \Bigg ( p - c - w - \Bigg ( 1 { - } \frac { \varphi \big ( ( 1 - \mu ) c _ { L } \big ) } { \varphi ( c _ { L } ) } \Bigg ) c \Bigg ) Q } \\ { { = } \Big ( p - w - ( 2 - \sqrt { 1 - \mu } ) c \Big ) \Bigg ( \frac { 2 y w \kappa ^ { 2 / y } p ^ { { - } 2 x / y } } { \eta ( 1 - \mu ) ( 2 + y ) } \Bigg ) ^ { y / 2 } } \end{array}
$$

由于关于 $p$ 和 $w$ 的二阶导数为 $\begin{array} { r } { \hat { \mathcal { O } } ^ { 2 } \prod _ { R } ^ { N } / \hat { \mathcal { O } } p ^ { 2 } < 0 \ , \hat { \mathcal { O } } ^ { 2 } \prod _ { R } ^ { N } / \hat { \mathcal { O } } w ^ { 2 } < 0 } \end{array}$ ，故存在最优解。令其一阶导数 $\hat { c } \Pi _ { R } ^ { \scriptscriptstyle N } / \hat { c } p = 0$ ， $\hat { v } \Pi _ { R } ^ { N } / \hat { v } w = 0$ ，能够得到电商平台的最优销售价格以及最优委托价格分别为

$$
p ^ { N ^ { * } } = \frac { 2 x } { 2 x - y - 2 } ( 2 - \sqrt { 1 - \mu } ) c
$$

$$
w ^ { N ^ { * } } = \frac { y } { 2 x - y - 2 } ( 2 - \sqrt { 1 - \mu } ) c
$$

将式(6)代入到式(4)中可得第三方物流服务商的最优货运量以及货运成本：

$$
{ Q ^ { \scriptscriptstyle N } } ^ { * } = \left( \frac { 2 y ^ { 2 } ~ \kappa ^ { 2 / y } ( 2 - \sqrt { 1 - \mu } ) c } { \eta ( 1 - \mu ) ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 } \left( \frac { 2 x } { 2 x - y - 2 } ( 2 - \sqrt { 1 - \mu } ) c \right) ^ { - x }
$$

$$
c _ { L } ^ { ~ N } { } ^ { * } = \frac { y ^ { 2 } ( 2 - \sqrt { 1 - \mu } ) c } { ( 1 - \mu ) ( 2 + y ) ( 2 x - y - 2 ) }
$$

此外，将式(6)和式(7)同时代入式(1)和式(2)，并进行化简整理可得不采用区块链技术时各节点企业的最大利润分别为

$$
\Pi _ { R } ^ { \cal N } = \left( \frac { 2 ( 2 - \sqrt { 1 - \mu } ) c } { 2 x - y - 2 } \right) \left( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } ( 2 - \sqrt { 1 - \mu } ) c } { \eta ( 1 - \mu ) ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 }
$$

$$
\left( \frac { 2 x } { 2 x - y - 2 } ( 2 - \sqrt { 1 - \mu } ) c \right) ^ { - x }
$$

$$
\Pi _ { L } ^ { \cal N ^ { * } } = \left( \frac { 2 y ( 2 - \sqrt { 1 - \mu } ) c } { ( 2 + y ) ( 2 x - y - 2 ) } \right) \left( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } ( 2 - \sqrt { 1 - \mu } ) c } { \eta ( 1 - \mu ) ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 }
$$

$$
\left( \frac { 2 x } { 2 x - y - 2 } ( 2 - \sqrt { 1 - \mu } ) c \right) ^ { - x }
$$

因此，根据式(8)和式(9)可知无区块链技术应用时电商供应链的总利润为

$$
\begin{array} { l } { { \Pi _ { S C } ^ { ^ N } \displaystyle = \left( \displaystyle \frac { 4 ( y + 1 ) ( 2 - \sqrt { 1 - \mu } ) c } { ( 2 + y ) ( 2 x - y - 2 ) } \right) \left( \displaystyle \frac { 2 y ^ { 2 } ~ \kappa ^ { 2 / y } ( 2 - \sqrt { 1 - \mu } ) c } { \eta ( 1 - \mu ) ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 } } } \\ { { \left( \displaystyle \frac { 2 x } { 2 x - y - 2 } ( 2 - \sqrt { 1 - \mu } ) c \right) ^ { - x } } } \end{array}
$$

命题1当第三方物流服务商的道德风险度 $\mu$ 不断上升时，电商平台的利润 $\Pi _ { R } ^ { N ^ { * } }$ 、第三方物流服务商的利润 $\Pi _ { L } ^ { N ^ { * } }$ 以及供应链的总利润 $\Pi _ { S C } ^ { N ^ { * } }$ 均呈现下降趋势。

证明：观察到供应链双方以及总利润函数是关于道德风险 $\mu$ 的函数，对式(8)求解关于道德风险度 $\mu$ 的一阶导数可得：

$$
\hat { \sigma } \Pi _ { R } ^ { N ^ { * } } \big / \hat { \sigma } \mu = ( 1 + y / 2 - x ) \frac { 2 c ( 2 - \sqrt { 1 - \mu } ) ^ { - x + y / 2 } ( 1 - \mu ) ^ { ( y - 1 ) / 2 } } { 2 ( 1 - \mu ) ^ { y } ( 2 x - y - 2 ) } \Bigg ( \frac { 2 x } { 2 x - y - 2 } \Bigg ) ^ { - x }
$$

$$
\left( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } } { \eta ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 }
$$

由于 $x \geq 1$ ， $\scriptstyle 0 < y < 1$ ，故当 $1 + y / 2 - x > 0$ 时， $2 x - y - 2 < 0$ ，此时，$\partial \Pi _ { R } ^ { N ^ { * } } / \partial \mu < 0$ ；当 $1 + y / 2 - x < 0$ 时， $2 x - y - 2 > 0$ ，此时， $\partial \Pi _ { R } ^ { N ^ { * } } / \partial \mu < 0$ ，显然在可行域内随着道德风险度 $\mu$ 的上升，电商平台的利润 $\Pi _ { R } ^ { N ^ { * } }$ 不断下滑。同理可得 $\hat { c } \Pi _ { L } ^ { N ^ { * } } / \hat { c } \mu < 0$ ； $\hat { \sigma } \Pi _ { S C } ^ { N } { } ^ { * } / \hat { \sigma } \mu < 0$ ，故可知随着道德风险度 $\mu$ 的上升，第三方物流服务商的利润 $\Pi _ { L } ^ { N ^ { * } }$ 以及供应链的总利润 $\Pi _ { S C } ^ { N ^ { * } }$ 均呈现下滑趋势，故命题1得证。

命题1表明，第三方物流服务商存在的高度道德风险会导致供应链各节点企业以及总利润受损。可见第三方物流服务商注重片刻利益而忽略长远发展，不仅会损害委托方以及整个供应链的利润，而且对自身也不利。因此，应用新技术防范第三方物流服务商存在的道德风险，使供应链上各节点企业能够作出合理的决策，优化供应链各方以及整体利润至关重要。

# 3.2采用区块链技术时的最优策略

借助以区块链为基础构建的物流服务水平监督系统，利用共识机制实现信用重构，建立透明、可信和高效沟通的互助机制，利用时间戳技术保证数据唯一性。供应链各节点企业均将涉及自身产品以及服务的相关信息上传至系统，由于区块链技术是以分布式数据库和智能合约为业务逻辑的点对点基础设施，分布式账本技术消除了中间人的干扰，信息的准确性得以提高；区块链技术的去中心化、信息防窜改以及可追溯等特性能够准确有效监督第三方物流服务商的服务质量，使得 $\scriptstyle \mu = 0$ 。故以电商平台为主导的Stackelberg博弈模型为

$$
\operatorname * { m a x } _ { p > 0 , w > 0 } ~ \Pi _ { R } ^ { B } ( p , w ) { = } ( p - c - w - t c _ { B } ) Q
$$

$$
\operatorname * { m a x } _ { Q > 0 } \ \Pi _ { L } ^ { B } ( Q ) = \big ( w - c _ { L } - ( 1 - t ) c _ { B } \big ) Q
$$

由于 $c _ { L } = \frac { \eta Q ^ { 2 / y } } { 2 \kappa ^ { 2 / y } p ^ { - 2 x / y } }$ 是关于货运量 $\varrho$ 的函数，因此对目标函数式(12)求关于 $\boldsymbol { \mathscr { Q } }$ 的二阶导数，得 $ { \partial } ^ { 2 } \prod _ { L } ^ { B } /  { \partial } Q ^ { 2 } < 0$ ，可知第三方物流服务商的利润函数是关于 $\boldsymbol { \mathscr { Q } }$ 的凹函数，故存在最优解使得第三方物流需求企业的利润达到最大值。对式(12)求关于 $\varrho$ 的一阶导数并令其等于0可得：

$$
\scriptstyle Q = \left( { \frac { 2 y ^ { 2 } \kappa ^ { - 2 x / y } \left( w - ( 1 - t ) c _ { B } \right) } { \eta ( 2 + y ) } } \right) ^ { y / 2 }
$$

$$
c _ { L } = \frac { y } { 2 + y } \big ( w - ( 1 - t ) c _ { B } \big )
$$

将式(13)代入式(11)，可得；

$$
\begin{array} { r } { \prod _ { R } ^ { B } ( p , w ) = ( p - c - w - t c _ { B } ) \Bigg ( \frac { 2 y ^ { 2 } K ^ { - 2 x / y } \left( w - ( 1 - t ) c _ { B } \right) } { \eta ( 2 + y ) } \Bigg ) ^ { y / 2 } } \end{array}
$$

对式(14)分别求关于 $p$ 和 $w$ 的二阶导数 $\hat { \sigma } ^ { 2 } \prod _ { R } ^ { B } \big / \hat { \sigma } p ^ { 2 } < 0$ ：$ { \hat { \sigma } } ^ { 2 } \prod _ { R } ^ { B } /  { \hat { \sigma } } w ^ { 2 } < 0$ ，故电商平台的利润函数是关于 $p$ 和 $w$ 的联合凹函数，故存在最优解使得电商平台的利润最大化。令其一阶导数 $\hat { c } \Pi _ { R } ^ { B } / \hat { c } p = 0$ ； $\hat { \sigma } \Pi _ { R } ^ { B } / \hat { \sigma } w = 0$ ，可得电商平台的最优销售价 $p ^ { B ^ { * } }$ 格以及最优委托价格 $\boldsymbol { w ^ { B ^ { * } } }$ 分别为

$$
p ^ { B ^ { \ast } } = \frac { 2 x ( c + c _ { B } ) } { 2 x - y - 2 }
$$

$$
w ^ { B ^ { * } } = \frac { y c } { 2 x - y - 2 } + \frac { y t + 2 ( x - 1 ) ( 1 - t ) } { 2 x - y - 2 } c _ { B }
$$

将式(15)分别代入式(13)中可得采用区块技术时第三方物流服务商的最优货运量 $Q ^ { B ^ { * } }$ 以及最优货运成本 ${ c _ { L } } ^ { B ^ { * } }$ 分别为

$$
Q ^ { B ^ { * } } = \left( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } ( c + c _ { B } ) } { \eta ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 } \left( \frac { 2 x ( c + c _ { B } ) } { 2 x - y - 2 } \right) ^ { - x }
$$

$$
{ c _ { L } } ^ { B } { } ^ { * } = \frac { y ^ { 2 } ( c + c _ { B } ) } { ( 2 + y ) ( 2 x - y - 2 ) }
$$

此外，将式(15)和式(16)分别代入式(11)和式(12)中，通过

化简整理可得采用区块技术时各节点企业的最大利润分别为

$$
\Pi _ { R } ^ { s } = \frac { 2 ( c + c _ { B } ) } { 2 x - y - 2 } \Bigg ( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } ( c + c _ { B } ) } { \eta ( 2 + y ) ( 2 x - y - 2 ) } \Bigg ) ^ { y / 2 } \Bigg ( \frac { 2 x ( c + c _ { B } ) } { 2 x - y - 2 } \Bigg ) ^ { - x }
$$

$$
\prod _ { L } ^ { B ^ { * } } = \left( \frac { 2 y ( c + c _ { B } ) } { ( 2 + y ) ( 2 x - y - 2 ) } \right) \left( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } ( c + c _ { B } ) } { \eta ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 } \left( \frac { 2 x ( c + c _ { B } ) } { 2 x - y - 2 } \right) ^ { - x }
$$

因此，结合式(17)和(18)可知，采用区块链技术时电商供应链的总利润为

$$
\prod _ { S C } ^ { B ^ { \ast } } = \left( \frac { 4 ( y + 1 ) ( c + c _ { B } ) } { ( 2 + y ) ( 2 x - y - 2 ) } \right) \left( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } \left( c + c _ { B } \right) } { \eta ( 2 + y ) ( 2 x - y - 2 ) } \right) ^ { y / 2 } \left( \frac { 2 x ( c + c _ { B } ) } { 2 x - y - 2 } \right) ^ { - x }
$$

对比采用区块链技术前后电商供应链上各节点企业利润的变化情况，可以发现采用区块链技术对电商供应链各方的利润具有重要影响。但电商供应链考虑是否采用区块链技术的基础是采用该技术之后能否有效防范道德风险致使供应链各方利润较传统模式有所提升。

另外，易知电商平台以及第三方物流服务商的销售价格、委托价格、货运量以及货运成本均受区块链技术应用的影响，可见技术带来的优势远超过想象，将有助于助力构建数字供应链，大大提高整个供应链的效率。

命题2当区块链技术应用的成本投入不断增加时，电商平台的利润 $\Pi _ { R } ^ { B ^ { * } }$ 、第三方物流服务商的利润 $\Pi _ { L } ^ { B ^ { \ast } }$ 以及供应链的总利润 $\Pi _ { S C } ^ { B ^ { * } }$ 将不断减少。

证明对采用区块链技术时电商平台的最优利润函数$\Pi _ { R } ^ { B ^ { * } }$ 求解关于技术成本投入 $c _ { B }$ 的一阶导数为

$$
\hat { \sigma } \Pi _ { R } ^ { B ^ { * } } / \hat { \sigma } c _ { B } = - ( x - 1 - y / 2 )
$$

$$
( c + c _ { B } ) ^ { - x + y / 2 } \frac { 2 } { 2 x - y - 2 } \Bigg ( \frac { 2 x } { 2 x - y - 2 } \Bigg ) ^ { - x } \Bigg ( \frac { 2 y ^ { 2 } \kappa ^ { 2 / y } } { \eta ( 2 + y ) ( 2 x - y - 2 ) } \Bigg ) ^ { y / 2 }
$$

与命题1类似可知 $\hat { c } \Pi _ { R } ^ { B ^ { * } } / \hat { c } c _ { B } < 0$ ，因此可见随着该技术投入成本 $\boldsymbol { c } _ { B }$ 的增加，电商平台的利润 $\Pi _ { R } ^ { B ^ { * } }$ 不断减少。同理可得$\hat { c } \Pi _ { L } ^ { B ^ { * } } / \hat { c } c _ { B } < 0$ ； $\hat { \sigma } \Pi _ { S C } ^ { B } { } ^ { * } / \hat { \sigma } c _ { B } < 0$ ，故第三方物流服务商的利润 $\Pi _ { L } ^ { B ^ { * } }$ 以及总利润 $\Pi _ { S C } ^ { B ^ { * } }$ 也均随着技术投入成本 $\boldsymbol { c } _ { B }$ 的增加而不断减少，命题2得证。

命题2表明，区块链技术应用的成本投入会导致供应链上各方利润以及总利润的减少。对于供应链各企业而言，增添技术的使用便意味着基础性支出的增加，这是不可避免的。但是投入区块链技术的使用能否减少传统供应链弊端引发的损失才应该是链上企业所关注的重点。

# 4 对比分析

采用区块链技术的成本投入是供应链各节点企业决定是否应用该技术防范道德风险的重要影响因素。合理的成本投入以达到降低道德风险目的的同时，为各节点企业创造更多的利益才是供应链双方所追求的，因此，对区块链技术的成本投入进行决策分析，具体如下：

命题3当 $0 < c _ { B } < \overline { { c } } _ { B }$ 时，采用区块链技术后其总利润增加，供应链双方愿意采用该技术；当 $c _ { B } > \overline { { c } } _ { B }$ 时，供应链双方不愿意采用该技术，其中B=c(-√-μ (1-)(-2x2-1)。

证明不采用区块链技术则要受道德风险的影响，采用区块链技术则要承担该技术的应用成本，因此，采用区块链技术的一个必要条件就是供应链的总利润增加，即满足不等式 $\Pi _ { S C } ^ { B ^ { * } } - \Pi _ { S C } ^ { N ^ { * } } > 0$ ，将式(10)和(20)代入化简可得$0 < c _ { B } < c ( \frac { 2 - \sqrt { 1 - \mu } } { ( 1 - \mu ) ^ { y / ( y - 2 x + 2 ) } } - 1 )$ （---1)，因此命题3得证。

命题3确定了采用区块链技术时既要防范第三方物流服务商的道德风险，又要提高整个供应链利润的成本投入约束条件，表明只要将该技术的成本投入控制在合适的范围内，供应链各节点企业的利润均会增加，总利润也会随之上升，此时无论是电商平台还是第三方物流服务商都会积极主动选择该技术，拓展区块链技术在供应链领域更深层次的应用，助力区块链技术集成应用的发展以及供应链领域企业运作更加透明高效。

命题4当 $c _ { B } > \tilde { c } _ { B }$ 时，电商平台会提高销售价格；当$c _ { B } < \tilde { c } _ { B }$ 时，电商平台会降低销售价格，其中 $\tilde { c } _ { B } = ( 1 - \sqrt { 1 - \mu } ) c$ 。

证明对技术应用前后电商平台的销售价格式(6)和(16)进行比较，若 $p ^ { N ^ { * } } < p ^ { B ^ { * } }$ ，则有 $c _ { B } > ( 1 - \sqrt { 1 - \mu } ) c$ ，若 $p ^ { N ^ { * } } > p ^ { B ^ { * } }$ ，则有$c _ { B } < ( 1 - \sqrt { 1 - \mu } ) c$ ，因此命题4得证。

命题4表明，采用区块链技术后电商平台会提高销售价格，并且随着区块链技术成本投入的增加而增加，电商平台希望通过提高产品销售价格的方式来保证自身的收益。

命题5当 $c _ { B } > \hat { c } _ { B }$ 时，采用区块链技术时电商平台给予第三方物流服务商的委托价格会提高；当 $c _ { B } < \hat { c } _ { B }$ 时，电商平台会选择降低给第三方物流服务商的委托价格，弥补自身产生的损失，其中eB=y-√-μ)c $\widehat { c } _ { B } = \frac { y ( 1 - \sqrt { 1 - \mu } ) c } { y t + 2 ( x - 1 ) ( 1 - t ) }$

证明对区块链技术应用前后的委托价格式(6)和(16)进 行比较，若 $w ^ { B ^ { * } } > w ^ { N ^ { * } }$ ，则有 $c _ { B } > \frac { y ( 1 - \sqrt { 1 - \mu } ) c } { y t + 2 ( x - 1 ) ( 1 - t ) }$ ；若 $w ^ { B ^ { * } } < w ^ { N ^ { * } }$ ，则 $c _ { B } < \frac { y ( 1 - \sqrt { 1 - \mu } ) c } { y t + 2 ( x - 1 ) ( 1 - t ) }$ 故命题5得证。

命题5表明区块链技术应用后，电商平台选择提高给予第三方物流服务商的委托价格，电商平台能够实时监测货物配送途中的服务水平状况，希望利用更高的委托价格提升其积极性和主动性。

命题6当 $c _ { B } > \bar { c } _ { B }$ 时，采用区块链技术后，第三方物流服务商的货运成本投入有所增加，当 $c _ { B } < \breve { c } _ { B }$ 时，第三方物流服务商的货运成本投入有所减少，其中ε=c(2+y(2-√-μ)-1)

证明对式(7)和(17)采用区块链技术前后的货运成本进行对比，若 ${ c _ { L } } ^ { B ^ { * } } - { c _ { L } } ^ { N ^ { * } } > 0$ ，则有 $c _ { B } > c \Bigg ( \frac { 2 + y } { y } ( 2 - \sqrt { 1 - \mu } ) - 1 \Bigg )$ ${ c _ { L } } ^ { B ^ { * } } - { c _ { L } } ^ { N ^ { * } } < 0$ ，则 $c _ { B } < c \left( \frac { 2 + y } { y } ( 2 - \sqrt { 1 - \mu } ) - 1 \right)$ (2+y(2-√-μ)-1，因此命题6得证。

命题6表明第三方物流服务商的货运成本投入会随着区块链技术成本投入的增加而增加。由于区块链技术的深度应用，供应链双方之间的透明度加强，受托方懒惰降低努力程度的机会渺茫，因此，第三方物流服务商选择不断优化服务水平，与电商平台保持长期稳定的合作。

命题7当 $0 < c _ { B } < \hat { c } _ { B }$ 时，采用区块链技术时第三方物流服务商的货运量会增加，当 $c _ { B } > \hat { c } _ { B }$ 时，第三方物流服务商的货$\hat { c } _ { B } = c ( \frac { 2 - \sqrt { 1 - \mu } } { ( 1 - \mu ) ^ { y / ( y - 2 x ) } } - 1 )$

证明对比区块链技术应用前后第三方物流服务商的货运量，采用区块链技术是货运量增加的一个必要条件，既满足不等式 $Q ^ { B ^ { * } } > Q ^ { N ^ { * } }$ ，则 $c _ { B } \leq c ( \frac { 2 - \sqrt { 1 - \mu } } { ( 1 - \mu ) ^ { y / ( y - 2 x ) } } - 1 )$ ,因此命题7得证。

命题7表明了第三方物流服务商货运量与区块链技术成本投入的相关关系，满足一定的技术成本投入范围，应用区块链技术会致使第三方物流服务商的货运量增加，超出范围则会减少。

# 5 数值实验分析

为验证理论的正确性，通过数值进行深入分析。参考某电商平台的实际运营数据，设定其产品的需求规模 $\kappa { = } 1 0 0 0 0$ 件，产品的单位成本 $c = 4$ 元，价格弹性 $x = 2$ ，物流服务水平弹性 $y = 0 . 5$ ，货运成本弹性系数 $\eta = 2$ ，区块链技术成本投入的分摊比例 $t = 0 . 6$ ，第三方物流服务商的道德风险度 $\mu \in ( 0 , 1 ]$ 。

# 5.1区块链技术成本投入 $\boldsymbol { c } _ { B }$ 对供应链最优决策的影响

该部分主要分析区块链技术成本投入对销售价格、委托价格、货运量、货运成本以及电商平台和第三方物流服务商的利润和总利润的影响。假定 $\boldsymbol { c } _ { B } \in [ 0 , 1 ]$ ， $c _ { B }$ 对供应链最优决策的影响见表2。

表 $\textit { 2 } \ : \ : c _ { B }$ 对供应链最优决策的影响  
Tab.2 $c _ { B }$ Influence on the optimal decision of supply chain   

<html><body><table><tr><td>CB</td><td>p</td><td>W*</td><td>Q*</td><td>CL</td><td>IIR*</td><td>II*</td><td>Ic*</td></tr><tr><td>0.1</td><td>10.94</td><td>1.40</td><td>60.44</td><td>0.28</td><td>331.21</td><td>65.28</td><td>396.49</td></tr><tr><td>0.3</td><td>11.47</td><td>1.55</td><td>55.61</td><td>0.29</td><td>319.20</td><td>63.40</td><td>382.60</td></tr><tr><td>0.5</td><td>12.01</td><td>1.70</td><td>51.35</td><td>0.30</td><td>308.61</td><td>61.62</td><td>370.23</td></tr><tr><td>0.7</td><td>12.54</td><td>1.84</td><td>47.59</td><td>0.32</td><td>298.87</td><td>59.49</td><td>358.36</td></tr><tr><td>0.9</td><td>13.07</td><td>1.99</td><td>44.24</td><td>0.33</td><td>289.33</td><td>57.51</td><td>346.84</td></tr></table></body></html>

由表2可知，随着应用区块链技术的成本投入不断增加，电商平台的销售价格、委托价格以及第三方物流服务商的货运成本也不断增加，但货运量以及供应链双方的利润和总利润均出现减少的趋势。这表明供应链双方受该技术应用的影响会采取不同的策略，对电商平台而言，为维持自身的利润，在采用该技术时会相应地通过提高产品销售价格来弥补支出，通过该技术电商平台可以很好地掌握和追溯第三方物流服务商的物流服务水平，选择给予委托报酬激励第三方物流服务商。对第三方物流服务商而言，采用区块链技术时道德风险降低，只好选择放弃压缩成本的策略，选择把服务做好，获取更多的货运量。

下面分析区块链技术应用前后决策变量以及利润的变化情况，确定防范道德风险的区块链技术成本投入范围。令道德风险度 $\scriptstyle \mu = 0 . 4$ ，画出采用区块链技术前后链上企业利润和委托价格的变化分别见图2和3。

从图2中可以看出，刚开始采用区块链技术时，供应链各节点企业利润以及总利润较传统模式下的利润均有所提升，但随着技术投入成本的逐渐增加，利润不断下降。这就表明要想在防范第三方物流服务商道德风险的同时提升供应链的总利润，只有当 $0 < c _ { B } < 0 . 6$ 时才可满足，因此并不是说区块链技术的应用就一定能防范道德风险，要考虑技术投入的成本因素。

450400 OΦ  
元350 1i01丨Φ1丨º丨º10||01四丨α1°金  
1α|i  
Y250不采用区块链时电商平台的利润采用区块链时电商平台的利润  
座150 A不采用区块链时第三方物流服务商的利润  
供 一采用区块链时第三方服务商的利润不采用区块链时的总利润100 O一采用区块链时的总利润△ △ A A500 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1区块链技术的投入成本（元）

从图3中可以看出，当区块链技术的成本投入达到一定范围后，电商平台给予第三方物流服务商的委托价格将超过传统模式下的委托价格，这表明该技术的投入使得第三方物流服务商的服务可追溯、可监控，电商平台掌握主动权，可以适当调整委托价格以达到激励第三方物流服务商的目的。

接下来分析采用区块链技术前后货运量的变化如图4所示(假设道德风险度分别是 $\scriptstyle \mu = 0 . 4$ 和 $\scriptstyle \mu = 0 . 6$ )。从图4中可以看出，采用区块链技术时，当第三方物流服务商的道德风险较低时，技术应用后的货运量始终高于传统模式下的货运量。当第三方物流服务商的道德风险较高，技术的成本投入达到一定范围时，货运量较传统模式下的有所下降。这表明第三方物流服务商的道德风险度高时，控制成本范围能有助于货运量的提升，反之，单纯依靠控制该技术的成本投入对第三方物流服务商的道德风险影响不大。

![](images/232a7c9da15726795bb665c982e08245473cff75adacab6c852bcdbde0248307.jpg)  
图3采用区块链技术前后委托价格的变化 Fig.3Change of commission price before and after adopting blockchain technology

![](images/61e503583b62c8b838ee460966bd625d4e0b7a249029f2716a468dfddfcd3879.jpg)

# 5.2 $\mu$ 、t、 $x$ 和 $y$ 对供应链最优决策的影响

该部分主要分析其道德风险度、技术投入成本的共担比例、价格弹性系数以及物流服务水平弹性系数对区块链应用前后电商平台和第三方物流服务商的利润和总利润的影响。假定区块链技术的成本投入 $c _ { B } = 0 . 5$ ，分别绘制图5\~8，并做具体分析。

从图5可以看出，不采用区块链技术时，供应链各节点企业的利润以及总利润随着道德风险度的不断增加而减少，这表明，第三方物流服务商只考虑自身利润而损坏了整条供应链的长远发展，由于第三方物流服务商降低物流服务水平致使市场需求转移或降低，本以为为自身谋取了利益，殊不知影响企业长久经营以及损害供应链合作伙伴，供应链的协同发展才是供应链各节点企业谋求自身利益最大化的有效途径和可行方式。

![](images/3cfd8533e40a473eef8f4f1b68e798f03e4f790b91fac8f05719054a66e6ad6d.jpg)  
图5道德风险度 $\mu$ 对企业利润的影响

从图6中可以看出，共担比例较低时，采用区块链技术的电商平台的委托价格更高，随着共担比例的逐渐增大，采用区块链时的委托价格远低于不采用区块链时的委托价格，这表明供应链各企业很看重采用区块链技术的成本问题，只有合适的成本投入方可拉动链上企业的积极性和主动性。

![](images/ffcaf54038a61f3f2a1b1c0b73200b0d6bcf9a92d2a6f62a152f26d8e87bc112.jpg)  
Fig.5Impact of moral hazard $\mu$ on corporate profits   
图6共担比例t对委托价格的影响   
Fig.6Effect of share proportion t on commission price

从图7可以发现，电商平台的利润、第三方物流服务商的利润以及供应链的总利润皆随着价格弹性系数的增加而不断下降，这表明采用区块链技术时，电商平台的销售价格并不是越高越有利，只有符合客户合理的销售价格采用才能给企业带来更多的利益。从图8可以看出，第三方物流服务商的利润随着物流服务弹性系数的增加而增加，电商平台的利润以及供应链的总利润随着物流服务水平弹性系数的增加而先减后增，这表明采用区块链技术时，第三方物流服务商采取提供优质的物流服务是为自身谋利益的有效措施，电商平台的利润波动深受其服务水平高低的影响。

![](images/a916900dda53411e61a974ed4ed2874f8547d0411b2b72471e7a106c4bd8a06f.jpg)  
图4不同道德风险度下区块链技术前后货运量的变化 Fig.4Changes of freight volume before and after blockchain technologyunder different moral hazard degrees   
图7价格弹性系数 $x$ 对企业利润的影响  
Fig.7Effect of price elasticity coefficient $x$ on enterprise profit

![](images/66118e22d9a78b71d30130e5a2f1b7c3f7106f6ecbb7610ede1c1884f93c75b6.jpg)  
图8物流服务水平弹性系数 $y$ 对企业利润的影响 Fig.8Impact of elasticity coefficient $y$ of logistics service level on enterprise profit

# 6 结束语

因道德风险而引发委托方利益受损的现象普遍存在，已经触及供应链的健康有序发展。区块链作为具有颠覆性意义的前沿技术之一，其分布式账本技术、共识机制、时间戳、非对称加密算法以及智能合约等优势对于防范第三方物流服务商的道德风险具有重要的现实作用。考虑物流服务商降低努力程度对供应链利润的影响，分别构建不采用区块链和采用区块链的Stackelberg博弈模型，通过数学模型分析电商供应链各节点企业分散决策时的主要结论有：a)不采用区块链技术时，电商平台的利润、第三方物流服务商的利润以及供应链的总利润随着道德风险度的增加而减少，道德风险阻碍供应链各节点企业的盈利；b)当道德风险度为0.4，区块链成本投入在区间(0.0.6)时，供应链双方愿意采用区块链技术，此时，通过区块链技术的应用不仅能够有效防范道德风险，而且还能够促进供应链收益的提升。

本文仅研究电商平台作为Stackelberg博弈领导者的情况，未来可以考虑研究第三方物流服务商作为博弈领导者或多个第三方物流服务商竞争情形下应用区块链防范道德风险的策略。

# 参考文献：

[1]Nakamoto S.Bitcoin:A peer-to-peer electronic cash system [EB/OL]. (2008-11-30) .https://bitcoin.org/bitcoin. pdf.   
[2]武岳，李军祥．区块链P2P网络协议演进过程[J].计算机应用研究, 2019,36 (10): $2 8 8 1 - 2 8 8 6 + 2 9 2 9$ （Wu Yue,Li Junxiang.Evolution process of blockchain P2P network protocol [J].Computer application research,2019,36 (10):2881-2886+2929)   
[3]黄建华，江亚慧，李忠诚．利用区块链构建公平的安全多方计算[J]. 计算机应用研究,2020,37(01): $2 2 5 - 2 3 0 + 2 4 4$ (Huang Jianhua, Jiang Yahui,Li Zhongxin. Building fair secure multiparty computing using blockchain [J].Computer application research，2020,37(O1):225- $2 3 0 \substack { + 2 4 4 }$   
[4]朱立龙，尤建新.非对称信息供应链道德风险策略研究[J].计算机 集成制造系统，2010,16(11):2503-2509.(Zhu Lilong，you Jianxin. Research on moral hazard strategy of asymmetric information supply chain [J].Computer integrated manufacturing system,2O10,16(11): 2503-2509)   
[5]陈玲．第三方物流契约激励机制研究[D]．大连理工大学，2012. (Chen Ling.Research on the incentive mechanism of the third party logistics contract [D].Dalian University of technology,2012)   
[6]徐伟．考虑风险偏好与道德风险的外包激励模型研究[D].华南理 工大学，2017.(Xu Wei.Research on outsourcing incentive model considering risk preference and moral hazard [D]. South China University of technology,2017)

[7]徐鹏，伏红勇，王磊，彭选华．农产品供应链金融中银行对3PL的激 励监督机制研究[J].管理评论,2018,30(10):26-39.(XuPeng,Fu Hongyong,Wang Lei,Peng Xuanhua.Study on the incentive and supervision mechanism of banks on 3PL in agricultural supply chain finance [J]. Management review,2018,30 (10): 26-39)

[8]王宗光，朱炳晓，廖世龙．契约协调下第三方物流企业道德风险研 究——以生鲜供应链为例[J].经济与管理，2019,33(02):23-31. (Wang Zongguang,Zhu Bingxiao,Liao Shilong. Study on the moral hazard of the third party logisticsenterprises under the contract coordination-taking fresh supply chain as an example [J].Economy and management,2019,33 (02): 23-31)   
[9]Huang M,Tu J, Chao X,et al. Quality risk in logistics outsourcing: A fourth party logistics perspective [J].European Journal of Operational Research,2019,276 (3): 855-879.   
[10] Jiang X G, Yang H. Prevention mechanism of moral hazard from vendors in outsourcing [J]. Journal ofInterdisciplinary Mathematics,2018,21 (5): 1315-1320.   
[11]王磊，赵晓永．基于区块链机制的云计算环境下服务组合策略的研 究[J].计算机应用研究,2019,36(01): $8 1 - 8 6 + 9 0$ . (Wang Lei, Zhao Xiaoyong. Research on service composition strategy in cloud computing environment based on blockchain mechanism [J]. Computer application research,2019,36 (01): $8 1 - 8 6 + 9 0$ ）   
[12]张夏恒．基于区块链的供应链管理模式优化[J].中国流通经济, 2018,32 (08):42-50. (Zhang Xiaheng. Optimization of supply chain management mode based on blockchain [J]. China's circulation economy, 2018,32 (08): 42-50)   
[13]邓爱民，李云凤．基于区块链的供应链“智能保理”业务模式及博弈 分析[J]．管理评论,2019,31(09): 231-240.(Deng Aimin,Li Yunfeng. Business model and game analysis of"intelligent factoring"in Supply Chain Based on blockchain [J].Management review,2019,31(09): 231- 240)   
[14]范贤丽，范春晓，吴岳辛．基于区块链和 IPFS 技术实现粮食供应链 隐私信息保护[J]．应用科学学报,2019,37(02):179-190.(Fan Xianli, fan Chunxiao, Wu Yuexin. Privacy information protection of food supply chain basedon blockchain and IPFs technology[J]. Journal of Applied Sciences,2019,37 (02): 179-190)   
[15]尤瑶，孔兰菊，肖宗水，郑永清，李庆忠．一种支持区块链交易溯源 的混合索引机制[J].计算机集成制造系统,2019,25(04):978-984. (Yu Yao, Kong Lanju,Xiao zongshui,Zheng Yongqing,Li Qingzhong.A hybrid index mechanism supporting block chain transaction traceability [J]. Computer integrated manufacturing system,2019,25 (04): 978-984)   
[16] Yoo M, Won Y.A study on the transparent price tracing system in supply chain management based on blockchain.[J].Sustainability,2018,10(11): 4037-4049.   
[17] Schmidt C G, Wagner S M. Blockchain and supply chain relations: A transaction cost theory perspective [J]. Journal of Purchasing and Supply Management,2019,25 (4): 100552-100567.   
[18] Ping H,Wang J,Ma Z,et al.Mini-review of application of IoT technology in monitoring agricultural products quality and safety [J]. International Journal of Agricultural and Biological Engineering,2018, 11 (5): 35-45.   
[19] Agrawal T K,Pal R. Traceability in textile and clothing supply chains: Classifying implementation factors and information sets via Delphi study [J].Sustainability,2019,11 (6): 1698-1712.   
[20] Steve Huckle,Rituparna Bhattcharya, Martin White,et al. Internet of things，blockchain and shared economy applications [J].Procedia Computer Science,2016,98 (5): 461-466.   
[21] Wang Y. Joint pricing-production decisions in supply chains of complementary products with uncertain demand [J].Operations Research,2006,54(6):1110-1127.   
[22] Kaya M, Ozer O.Quality risk in outsourcing: Noncontractible product quality and private quality cost information[J].Naval Research Logistics, 2009,56(7): 669-685.   
[23] Tsay A A,Agrawal N.Channel dynamics under price and service competition [J].Manufacturing & Service Operations Management, 2000,2 (4):372-391.   
[24]匡霞，杨扬．逆向供应链企业间知识共享行为的演化博弈分析[J]. 上海理工大学学报,2019,41(3):293-299.(Kuang Xia,Yang Yang. Evolutionary game analysis of knowledge sharing behavior among enterprises in reverse supply chain [J].Journal of Shanghai University of technology,2019,41 (3):293-299)   
[25]何建佳，蒋雪琳，徐福缘．基于供需网企业合作博弈模型的演化路 径分析[J].运筹与管理，2018,27(09):79-86.(He Jianjia,Jiang Xuelin,Xu Fuyuan.Evolutionary path analysis based on supply and demand network enterprise cooperation game model [J]. Operation

research and management,2018,27 (09):79-86)

[26]黄志强，何建佳，郭韵．考虑决策周期影响的离散契约供应链动力 学行为[J]．系统管理学报,2019,28(04):771-776.(Huang Zhiqiang, he Jianjia,Guo Yun.Dynamic behavior of discrete contract supply chain considering the influence of decision cycle [J].Journal of systems management,2019,28 (04):771-776) [27]李丽花，高岩，徐丽．基于混杂控制方法的生产库存策略的研究[J]. 数学的实践与认识.2019,49(6):236-242.(LiLihua,Gao Yan,Xu Li. Research on production inventory strategy based on hybrid control method [J].Practice and understanding of mathematics.2019,49 (6):   
236-242) [28]李芳，马鑫，洪佳，叶春明．政府规制下非对称信息对闭环供应链差 别定价的影响研究[J]．中国管理科学.2019,27(7):116-126.(Li Fang,Ma Xin,Hong Jia,ye Chunming.Research on the influence of asymmetric information on differential pricing of closed-loop supply chain under government regulation [J]. China management science.2019,   
27 (7): 116-126)