# 企业价值链协同知识创新影响因素的系统动力学建模与仿真

# 罗　政」李玉纳²

(武汉大学信息管理学院武汉 430072)2(武汉理工大学管理学院 武汉 430070)

摘要：【目的】对企业价值链协同知识创新过程进行因果关系分析和建模仿真，提高协同知识创新效率。【方法】提出一种企业价值链协同知识创新影响因素的系统动力学模型。在识别该过程影响因素的基础上，依据其因果关系分析，构建相应的系统动力学模型。【结果】利用 Vensim PLE 软件对企业价值链协同知识创新影响因素的系统动力学模型进行系统仿真，进一步验证其有效性和灵敏度。实验结果表明，该模型能够较贴切地拟合该过程的现实情况。【局限】系统仿真时采用模拟数据，还需使用企业价值链中的实际数据进一步验证。【结论】根据仿真结果提出协同知识创新优化方案，以此提高企业价值链协同知识创新的效率。

关键词：企业价值链 协同知识创新 影响因素 系统动力学

分类号：F270.7 G250.2

# 1引言

在知识经济时代，企业可持续创新发展离不开知识创新，而企业依靠自身力量进行知识创新已远远不能满足创新发展的需求。因此企业迫切需要通过协同知识创新活动，实现企业价值链中知识资源的共享与优势互补，以达到可持续创新发展的目标。然而，企业价值链中的协同知识创新活动具有参与主体多、利益关系复杂等特征[1]。现阶段我国企业已在协同知识创新方面进行了一些有益尝试，但仍存在着知识创新效率低下等诸多突出问题。

虽然国内外学者在知识管理领域已有诸多研究，但对协同知识创新方面的研究仍存在不足。知识创造理论模型的研究起始于Nonaka[2提出的SECI模型,即知识的“社会化”（Socialization）、“外在化”(Externalization)、“组合化"(Combination)、“内隐化"(Internalization)过程，该模型以隐性知识为起点，涵盖隐性知识和显性知识相互转化的过程。然而该模型是一个封闭系统，知识创新被局限于组织内部，忽视了外部知识的关键作用。丁志慧等[提出企业知识创新价值链模型，该模型能够较好地展示知识创新与知识共享的过程，但只是着重分析企业内部知识增长与知识转化过程的内在机理，并没有提出详细的运行机制。

目前，国内外学者对协同知识创新的研究大多集中于知识创新过程中共享、转移和整合等过程的内在机理，以及协同创新模型等方面。但本文认为，协同知识创新要达成预期目标，必须将企业价值链协同知识创新的因果关系分析清楚，将各影响因素的动态变化纳入模型考虑。因此本文从系统动力学的视角进行研究，旨在提高企业价值链协同知识创新的效率，以供国内企业参考。

# 2企业价值链协同知识创新影响因素的因果关系分析

企业价值链协同知识创新指的是企业价值链成员充分利用彼此的知识资源进行优势互补，价值链上企业成员通过相互协同创造出新的知识，扩充各自的知识存储量，进而达到提升各企业成员的核心竞争力以及价值链整体竞争实力的目的。企业价值链协同知识创新系统，研究的是知识流在企业价值链上企业间的知识吸收、创造和转移，具有明确的边界，同时协同知识创新过程符合实际中知识吸收、创造和转移的基本规律，存在着明显的互动和反馈关系。这种反馈以及系统运行趋势很难单纯凭借经验来判断，而借助系统动力学能够根据协同知识创新系统的因果关系来构建反馈模型，并利用计算机仿真模拟对企业价值链协同知识创新过程的反馈结构和动态关系进行深入分析。

# 2.1 影响因素分析

(1）影响因素识别企业价值链协同知识创新是一个包含多种影响因素的复杂过程，各种因素相互关联、作用，进而形成非常复杂的递阶因素链。Warfield[4指出，应用解释结构模型(Interpretive Structural Modeling,ISM)方法可以从众多影响因素中识别出复杂社会经济系统结构问题的多层次影响因素。笔者应用ISM模型对企业价值链协同知识创新影响因素进行识别，总结出其直接与深层影响因素。本文综合国内外学者在协同知识创新影响因素研究[5-7的基础上，将9个影响企业价值链协同知识创新的因素分为两个层次：企业价值链协同知识创新直接影响因素，包括知识共享意愿、知识创新能力;企业价值链协同知识创新深层因素，包括企业价值链关系强度、利益分配机制、企业协同知识创新资金投入、企业领导行为、创新团队结构、信息技术支持、协同知识创新激励策略，如图1所示：

![](images/43c34d778f97a9190cf974804e0269af5b16eeb758b12bd11747f9df95e2e72d.jpg)  
图1企业价值链协同知识创新影响因素的解释结构模型

在上述9个影响因素中，知识共享意愿指企业在价值链协同知识创新平台上共享创新知识的意愿。知识创新能力指企业通过吸收其他企业知识创造新知识的能力。企业价值链关系强度指主导企业与其他协同企业的关系紧密程度[8]。利益分配机制指价值链获得协同知识创新收益后各企业的利益分配方式与比例。企业协同知识创新资金投人指企业价值链外部对协同知识创新活动投入的资金数额。企业领导行为指价值链各企业的领导层对协同知识创新问题的重视程度。创新团队结构指各企业负责协同知识创新的团队组成。信息技术支持指协同知识创新活动中信息网络技术提供的技术保障。协同知识创新激励策略指为激发知识型员工创新潜能，企业价值链与协同创新团队分别设计的激励策略。

# (2）影响因素分析

在直接影响因素层面，企业的协同知识共享意愿越强烈，其与价值链中其他企业进行知识共享的过程将更有效率。同理，企业的知识创新能力越强，它更可能通过吸收新知识创造企业价值链上不存在的知识[9]。知识共享意愿与知识创新能力相辅相成，将大幅提高知识创新效率。在深层影响因素层面，企业价值链关系强度越强、利益分配机制越合理、企业协同知识创新资金投入越大，都将提升知识共享意愿[10]。同时，企业协同知识创新资金投人越大、企业领导对协同知识创新越重视、创新团队结构更合理、信息技术支持越有力、协同知识创新激励策略越完善，都将为知识创新能力的提升提供保障。

随着时间不断推移，在企业领导行为、创新团队组织、协同知识创新激励策略和信息技术支持等影响因素的作用下，主导企业与协同企业的知识创新能力不断增强，知识创新量不断增加，企业知识存量也不断增加，知识共享量和企业知识淘汰量均随之不断增加[11]。同时，知识共享意愿在企业价值链关系强度和利益分配机制的影响下不断提升，这同样使知识共享量不断增加。而主导企业和协同企业知识存量的增加将带来知识整合量的增加，间接提升知识转化能力、商业化程度，从而提高企业盈利和知识创新收益，最终带来企业协同知识创新资金投入的增加[12]。反之,企业协同知识创新资金投人的增加带来了知识共享意愿和企业知识创新能力的提升，这间接增加了知识共享量。如此，企业价值链协同知识创新系统形成一个动态有序的循环结构。

在这个循环结构中，知识存量指的是企业内部所储存的知识总量，包含企业本身拥有的知识储备、企业自身创新获得的知识量，以及企业内化外部共享知识的知识资源[13]。知识创新量指的是企业通过自身知识创新投人，运用知识创新能力而获取的知识创新资源，其增长体现为企业知识存量的提高[14]。知识共享量指的是主导企业和协同企业为了达到协同知识创新的目标，而将自身企业知识存量共享到企业价值链的知识资源量[15]。知识淘汰量指的是企业为了更好地适应市场环境变化，而将自身知识存量更新淘汰的知识量。

# 2.2影响因素因果关系图分析

为使分析过程更为明晰，本文将研究主导企业如何与价值链上某一协同企业实施协同知识创新。主导企业指在价值链上具有控制与领导权的核心型企业，协同企业指的是价值链上围绕主导企业进行分工作业的其他辅助型企业[1]。基于前文对协同知识创新影响因素的识别和分析，本文构建企业价值链协同知识创新影响因素因果关系，如图2所示：

企业领导行为主导企业知 +创新团队主导企业 + +识创新量+知识存量 能组织? 主导企业知主导企业知 识淘汰量 识整合量+转花能力 主导企业知 +品商业化程度 主导企业知识产 +主导企业利 主导企业知 识创新投入× ?/ 润增长率主导企业知业值链 主导企业利润  
美众 识共享能力 主导企业盈利 +主导企业知 识创新收益 1知识共享阈值 知识共享量+ 知识共享意愿 业值 创业协知识  
协同企业知 + ++?  
识淘汰速率+ 具拿能利益分配机制 协同企业利协同企业盈利 收协同企业利 ￥协同企业知 +协同企业知 润增长率 协同企业知识淘汰量 协同企业知+ 识转化能力 协同企业知识产又 识创新投入+识整合量 品商业化程度+协同企业 协同企业知知识存量+ + +识创新能力协同企业知 + ?++识创新量 协同知识创信息技术支持 新激励策略

图2中主要包括以下回路:

(1）主导企业知识存量 $$ 主导企业知识创新量 $$ 主导企业知识创新能力 $$ 主导企业知识创新量 $$ 主导企业知识存量(2）主导企业知识存量 $$ 主导企业知识淘汰量 $$ 主导企业知识淘汰速率 $$ 主导企业知识淘汰量 $$ 主导企业知识存量(3）主导企业知识存量 $$ 知识共享阈值 $$ 知识共享量 $$ 主导企业知识存量

(4）协同企业知识存量 $$ 协同企业知识创新量 $$ 协同企业知识创新能力 $ ^ { \cdot }$ 协同企业知识创新量 $ ^ { \cdot }$ 协同企业知识存量(5）协同企业知识存量 $$ 协同企业知识淘汰量 $$ 协同企业知识淘汰速率 $\stackrel { \cdot } { \longrightarrow }$ 协同企业知识淘汰量 $ ^ { \cdot }$ 协同企业知识存量(6)协同企业知识存量 $$ 知识共享阈值 $$ 知识共享量 $$ 协同企业知识存量

上面6条反馈回路都是正反馈回路，体现了协同知识创新影响因素的因果关系。其中知识共享量受知识共享意愿、主导企业知识存量、协同企业知识存量和知识共享阈值4个因素影响。4个因素对知识共享量都是正方向的影响关系。知识共享的意愿越强烈，知识共享量越大，该因素受到企业价值链协同知识创新平台投入、关系强度和利益分配影响，最终体现在企业价值链协同知识创新资金投入上。主导企业知识存量受到主导企业知识创新量和主导企业知识淘汰量影响。协同企业知识创新量与知识淘汰量会影响到协同企业的知识存量。知识共享阈值反映企业价值链协同知识创新者对于拥有自身知识产权或技术机密知识的保护，对这部分知识不再进行共享。

# 3企业价值链协同知识创新影响因素的系统动力学模型构建

# 3.1模型边界及假设条件

构建模型第一步要考虑的就是系统的边界，界限内指的是系统本身，即建模需要关注的部分，界限外指的是系统的外部环境。本文选择企业价值链的协同知识创新过程以及协同知识创新的影响因素作为模型边界。

为了明确企业价值链协同知识创新系统运行的前提，本文从三个角度对基本假设进行分析。

(1）企业价值链协同知识创新开始后，主导企业和协同企业无时无刻不在开展协同知识创新，且这些活动相互交替进行，故提出假设1。

假设1：主导企业与其他协同企业的协同知识创新是一个连续、渐进的过程。

(2）企业价值链上协同企业的数量众多，故其知识存量和知识创新量在绝对值上都超过主导企业，且主导企业更接近于市场，知识更新速度更快，故提出假设2。

假设2：协同企业知识存量大，其知识创新量比主导企业高；主导企业的知识淘汰速率比协同企业高。

(3）主导企业作为企业价值链的核心企业，其知识创新效率更高，并且主导企业拥有分配价值链上最终收益的主动权，其知识创新意愿更高，故提出假设3。

假设3：主导企业的知识创新效率和知识创新意愿均高于协同企业。

# 3.2 系统流图

通过分析数据可计算性并考虑数据现实性，本文对企业价值链协同知识创新影响因素的因果关系图进行概括，进一步得出企业价值链协同知识创新影响因素的系统流图，在此系统中，包含状态变量(L）2个，流率变量(R)5个，辅助变量(A)21个，常量(C)15个,共43个变量，如图3所示。

# 3.3 方程设计及变量

L主导企业知识存量=INTEG(主导企业知识创新量 $+$ 知识共享量-主导企业知识淘汰量,20）(1)

R主导企业知识淘汰量 $\cdot =$ 主导企业知识存量 $\cdot \times$ 主导企业知识淘汰率 (

A主导企业知识创新量 $\mathbf { \bar { \rho } } = \mathbf { \rho }$ 主导企业知识存量 $\cdot { \bf { \sigma } } _ { \times }$ 主导企业知识创新能力

C主导企业知识淘汰率 $\scriptstyle = 0 . 0 4$

L协同企业知识存量=INTEG(协同企业创新知识量 $+$ 知识共享量-协同企业知识淘汰量,100）(5)

R协同企业知识淘汰量 $\cdot =$ 协同企业知识存量×

协同企业知识淘汰率

A协同企业知识创新量 $\mathbf { \bar { \rho } } = \mathbf { \rho }$ 协同企业知识存量 $\cdot { \bf { \sigma } } _ { \times }$ 协同企业知识创新能力

C协同企业知识淘汰率 $\scriptstyle = 0 . 0 2$

A知识共享阈值=IFTHENELSE(主导企业知识存量协同企业知识存量 ${ \bf < } 0 . 9$ ，主导企业知识存量/协同知识存量,0.9) (9

知识共享阈值体现了知识共享的程度，当知识共享阈值达到0.9时，主导企业和协同企业将不再进行知识共享活动。

A知识共享量 $\mathbf { \bar { \rho } } = \mathbf { \rho }$ DELAY1I(IFTHENELSE(知识共享阈值 $_ { < 0 . 9 }$ 主导企业知识共享能力 $\times$ 协同企业知识共享能力 $\times$ 知识共享意愿,0),2,0) (10)

公式(10)表示，当知识共享阈值达到0.9时，企业价值链中的知识共享暂时停止。而现实企业进行协同知识创新的过程中，各企业都要对所发送的知识进行选择、过滤，并经过理解吸收和再准备的阶段。所以此公式中的一阶延迟函数反映了知识共享在模型进行两个月后开始，此处初始知识共享量设为0。

A知识共享意愿 $. =$ 关系强度 $\mathbf { \nabla } _ { \cdot } \times$ 利益分配×LN (企业协同知识创新价值链投入)

知识共享意愿由关系强度、利益分配和企业协同知识创新价值链投入等三个因素共同决定。这三者与知识共享意愿均为正相关。

![](images/569b130168755abe5e5d324fe5ef52b7eac87257c7ca19b558f3dfd367342522.jpg)  
图3企业价值链协同知识创新影响因素系统流

A主导企业知识创新投入 $\ c =$ 企业协同知识创新资金投入×主导企业知识创新投入比例 (12)  
A协同企业知识创新投入 $\ c =$ 企业协同知识创新资金投入 $\times$ 协同企业知识创新投入比例 (13)  
A主导企业盈利 $\ c =$ 主导企业利润 $\times ( 1 +$ 主导企业利润增长率) (14)  
A协同企业盈利 $\ c =$ 协同企业利润 $\times ( 1 +$ 协同企业利润增长率) (15)  
A企业协同知识创新资金投入 $\underline { { \underline { { \mathbf { \Pi } } } } } = \underline { { \underline { { \mathbf { \Pi } } } } }$ 主导企业知识创新收益 $+$ 协同企业知识创新收益 (16)  
A企业协同知识创新价值链投入 $\ c =$ 企业协同知识创新资金投入-主导企业知识创新投入-协同企业知识创新投入 (17)

# 4模拟仿真及应用

# 4.1初值选取和参数设置

本文通过构建VensimPLE软件环境完成模型仿真。模型仿真的时间设置为60个月；根据假设2,协同企业的知识存量比主导企业大，故将主导企业知识存量的初始值设定为20，协同企业知识存量的初始值设定为100；企业价值链以主导企业为核心进行知识共享，在企业价值链协同知识创新过程中，协同企业将比主导企业投入更多知识资源，协同企业的知识共享能力比主导企业更强，故此处设定主导企业知识共享能力为0.6，协同企业知识共享能力为0.9；主导企业和协同企业的利润每个月都是60万元；其中，知识共享意愿的两个影响因素(关系强度和利益分配)分别在[0,1]区间取值。

# 4.2 有效性检验

模型仿真运行的目的是为了对模拟结果的有效性和灵敏度进行检验，有效性检验目的是验证模型是否体现实际系统的特点与其变化规律，对模型进行分析研究从而判断能否客观正确地理解所要解决的问题。

因为协同知识创新概念相对较为抽象，因此本文采用理论检验的方式，目的是对模型的有效性、一致性和适应性进行检验。模型仿真结果如图4所示。

![](images/6a896eec56e3b42fb9935cf90a96f57831cf100d193835e5c733943a90b210a8.jpg)  
图4系统仿真结果

(1）由图4(a)和图4(b)看出，知识差距呈现先增加后减少的趋势。通过对其主要原因进行剖析，发现在知识共享最开始的阶段，主导企业知识存量比较少，且知识创新能力相对较弱，但是协同企业拥有较高的知识创新能力，这就造成了双方的知识差距在短期内具有逐渐扩大的趋势；伴随着知识共享的进行，主导企业知识创新能力增强，知识创新量增加，知识存量增多，与协同企业的知识差距不断缩小；尽管随着主导企业知识存量的增加，知识共享趋于平缓，但此时主导企业的知识创新能力已占据控制地位，导致双方知识差距迅速缩小。

(2）由图4(c)和图4(d)看出，主导企业和协同企业的知识创新量的增长率均呈现逐渐加快的趋势，且在后期主导企业知识创新量增长迅猛。主导企业经过一段时间的知识共享储备后，逐渐增强自身知识创新能力，导致主导企业的知识创新绝对数量高于协同企业，增长速度也更快。

(3）由图4(e)和图4(f)看出，从知识淘汰量的绝对数量这个方面来看，主导企业比协同企业更高。这是因为主导企业更接近于市场，其知识更新换代速度比协同企业更快。

(4）由图4(g)和图4(h)看出，主导企业和协同企业的盈利状况都趋于增长态势，然而其增长速度却在渐渐变慢。因为知识共享在初始阶段，主导企业和协同企业知识存量比较少，当知识存量逐渐增加时，知识整合量也在逐步增加，知识转化能力不断加强，知识产品商业化程度不断提高，最终导致盈利也在逐步增加。当双方企业知识转化能力到达一定程度时，知识产品商业化程度的增长速度减慢，盈利的增长速度也随之放缓。

主导企业和协同企业的知识存量可以根据知识差距和知识共享量来反映，所以没有将其单独列出来探讨。本模型仿真的运行结果显示，一些重要的规律与现实具有较高的吻合度，这表示本模型可以对企业价值链协同知识创新的动态过程进行较为逼真的模拟，此外还能够为企业带来有价值的决策参考。

# 4.3 灵敏度分析

灵敏度分析是通过改变模型中的变量或者结构，并比较模型的输出，以此对其影响程度进行分析，使企业在实际工作中能够得到理论支撑，在决策方面也能够得到有效支持。本文进行灵敏度分析时考虑各变量重要性，对模型中的知识共享意愿、知识共享阈值等两个变量进行改变。

(1）改变知识共享意愿

首先保持企业协同知识创新价值链投入不变，增加关系强度与利益分配，得到改进方案1；在改进方案1的基础上，增加企业协同知识创新价值链投入，得到改进方案2。仿真结果如图5所示：

![](images/631f20b2508947dd124bdb989a82d931c6db9f4e251f256d705e7248751080d4.jpg)  
图5模型对知识共享意愿的灵敏度分析

从原方案到改进方案1，再到改进方案2，知识差距都呈现出很明显的缩小态势，但其走势却保持相对一致的情形；在不断改进方案后，主导企业和协同企业的知识存量均呈现升高的趋势。从而得出，模型对知识共享意愿具有较高的灵敏度。针对这个结果，本文认为，应建立企业价值链协同知识创新机制，加强企业协同知识创新价值链建设，明确企业价值链上主导企业和协同企业的利益分配，促进企业价值链成员间的知识共享和知识融合，这将有效提高企业价值链协同知识创新主体间的信任程度和整体知识架构。

# (2）改变知识共享阈值

将知识共享量方程中的知识共享阈值边界下调到0.7，得到改进方案1；继续下调为0.5，得到改进方案2。模型仿真结果如图6所示：

![](images/72a3d7648548d48edb96a6454d42402c55768c64d941c0a0244fe037582100bd.jpg)  
图6模型对知识共享阈值的灵敏度分析

从图6可知，随着主导企业和协同企业知识存量不断提高，知识共享阈值达到临界值，双方企业为了避免知识产品同质化趋势，停止进行知识共享；而正是由于知识共享的缺失，主导企业和协同企业的知识存量都出现了不同程度的减少。从而可以得出结论，模型对知识共享阈值具有较高的灵敏度。因此,本文认为应不断推进企业价值链协同知识创新系统中各方企业密切合作，扩大协同创新的层面，将有助于企业价值链中进行知识的吸收、转移与共享，这都将为企业价值链中的各方企业带来知识存量上的增长。

# 5 创新点与结论

# 5.1 创新点分析

综合比较本文与以往研究，本文有以下创新之处：

(1）刘岩芳等[17]从知识创新的主体和特性着手展开研究；王玉梅等[18]主要从各因素对知识创新的正反影响作用进行分析；裴乐[19从知识创新的内外部需求角度进行分析。上述文献的研究对象均为知识创新的直接因素，而本文在对知识创新直接因素分析的基础上，运用ISM模型进一步挖掘协同知识创新直接因素的更深层次影响因素。

(2）部分文献[18-20]针对知识创新的影响因素及其运行机制和传导路径进行了详细分析，但在此过程中并未使用系统动力学方法，而本文在对知识创新的影响因素进行识别和分析的基础上，构建了具体的系统动力学模型并进行仿真研究。

(3）以往文献只针对协同知识创新中的某个环节如知识转移[21]、知识吸收[22]、知识创造[23]等进行系统动力学建模，而本文的系统动力学建模覆盖协同知识创新的全过程，包括知识创新、知识共享、知识淘汰、知识转化等知识全生命周期。

(4）部分文献[23-24]使用系统动力学建模对协同创新问题进行研究，但其系统动力学建模与仿真均在对协同创新的各个子过程进行分析的基础上展开，而并未涉及协同创新的影响因素。本文对企业价值链协同知识创新的影响因素进行深人的识别和分析，将整个协同知识创新过程的内在机理分析得更加透彻，在此基础上构建更具体的系统动力学模型，从而得出更加准确的结论。

# 5.2结论

本文从系统动力学视角探讨企业价值链协同知识创新的过程，分析协同知识创新过程的主要影响因素，从而构建企业价值链协同知识创新影响因素的系统动力学模型。在VensimPLE软件环境中进行系统仿真，对知识共享意愿和知识共享阈值这两个参数做了灵敏度分析。结论如下：

(1）知识共享意愿对知识创新量有较高的灵敏度,企业价值链应该建立合理的利益分配机制，提升企业价值链各成员间的关系强度，从而提高主导企业和协同企业的知识创新量。此外，应该加大企业协同知识创新价值链的投入，进一步提升价值链各企业的知识创新能力。

(2)）知识共享阈值对知识创新量有较高的灵敏度。应该不断加强价值链中各企业间的联系，提升主导企业和协同企业之间的信任感，提高协同创新力度，从而增加企业价值链上的知识创新量。

根据结果可以得出，模型能够较好地拟合实际企业价值链协同知识创新的过程，这表明运用系统动力学的方法对协同知识创新进行研究是可行的。因为企业价值链中协同知识创新是一个复杂且难以具体化的过程，其影响因素很难做到全面的思考，模型对一些变量做了简化处理，因此更详尽的模型构建还需要深层次的研究。此外，本文在对模型进行模拟时所采用的是仿真数据，如果仿真过程采用企业价值链中的实际数据，将会带来更有价值的决策参考消息。

# 参考文献：

[1]李朝明．基于动态能力的企业协同知识创新[M].北京：清 华大学出版社,2013.(LiChaoming.Enterprise Collaborative KnowledgeInnovationSystemBasedonDynamic Abilities[M].Beijing: Tsinghua University Press,2013.)   
[2] Nonaka I.A Dynamic Theory of Organizational Knowledge Creation[J]. Organization Science,1994,5(1):14-37.   
[3] 丁志慧，刘伟，黄紫微．面向用户创新社区的企业知识创 新价值链模型研究[J]．科技进步与对策，2015，32(12): 129-133.(Ding Zhihui,Liu Wei,Huang Ziwei.Value Chain Model of Knowledge Innovation Based on User Virtual Community[J]. Science & Technology Progress and Policy, 2015,32(12):129-133.)   
[4] Warfield JN.Interpretive Structural Modeling[A].// Olsen S A．Group Planning and Problem-Solving Methodsin Engineering[M].Wiley Press,1982:155-201.   
[5]董媛媛，王宏起．基于系统动力学R&D联盟知识转移行为 研究[J]．情报科学，2014，32(6):51-63.(Dong Yuanyuan, Wang Hongqi. Research on Knowledge Transfer Behavior in R&D Alliance Based on System Dynamics[J]. Information Science,2014,32(6): 51-63.)   
[6]江俊桦，施琴芬，于娱．产学研合作中知识转移的系统动 力学建模与仿真[J]．情报科学，2014,32(8):50-55.(Jiang Junhua,Shi Qinfen，Yu Yu,Modeling and Simulation of System Dynamics on Knowledge Transfer in IndustryUniversity-Research Cooperation [J]. Information Science, 2014, 32(8): 50-55.)   
[7]郭伟，王灿，叶子兰．高新区知识创新能力影响因素的实 证研究[J]．武汉理工大学学报：信息与管理工程版，2010, 32(3):446-449.(Guo Wei,Wang Can,Ye Zilan.Influential Factors of Knowledge Innovation Capacity in High-tech Zone [J].Journal of Wuhan University of Technology: Information & Management Engineering,2010,32(3): 446-449.)   
[8]Lin W. Factors Affecting the Correlation Between Interactive Mechanismof StrategicAllianceandTechnological Knowledge Transfer Performance [J]. Journal of High Technology Management Research,2007,17(2): 139-155.   
[9]史丽萍，苑婧婷，唐书林，等．内部控制机制、团队共享心 智模型对知识共享的作用机理——扩展知识共享实现路径 的视角[J]．现代图书情报技术，2013(11):40-45.(Shi Liping, Yuan Jingting,Tang Shulin, et al.Role Mechanism of Internal Control Mechanism and Shared Mental Model on KnowledgeSharing:The Perspectivesof Extending Knowledge Sharing Achievement Paths [J]. New Technology of Library and Information Service,2013(11): 40-45.)   
[10] Zaim S,Bayyurt N, Tarim M,et al. System Dynamics Modeling of a Knowledge Management Process: A Case Study in Turkish Airlines [C].In:Proceedings of the 9th International Strategic Management Confernece. 2013.   
[11] Peschl MF,Fundneider T.Designing and Enabling Spaces for Collaborative Knowledge Creation and Innovation: From Managing to Enabling Innovation as Socio-epistemological Technology [J].Computers in Human Behavior,2014,37: 346-359.   
[12]聂峰英，黄夔．基于演化博弈的企业价值链协同知识创新 研究[J]．现代情报，2015，35(1):38-48．(Nie Fengying, Huang Kui. Evolutionary Game Analysis of Collaboration Knowledge Creation in Enterprise Value Chain[J]. Journal of Modern Information, 2015,35(1): 38-48.)   
[13] Mundbrod N, Kolb J,Reichert M. Towards a System Support of Collaborative Knowledge Work [A].// Business Process Management Workshops [M]. Springer Berlin Heidelberg, 2013: 31-42.   
[14] Young A L.Understanding & Advancing Collaborative Scientific Knowledge Creation [C]. In: Proceedings of the Companion Publication of the 17th ACM Conference on Computer Supported Cooperative Work & Social Computing. ACM,2014: 101-104.   
[15]罗洪云，林向义，王磊，等．产学研协同知识创新体系创 新绩效评价研究[J]．现代情报，2015，35(2)：8-11.(Luo Hongyun，Lin Xiangyi,Wang Lei, et al. Evaluation on Innovating Performanceof Industry-University-Research Collaborative Knowledge Innovation System [J]. Journal of Modern Information,2015,35(2): 8-11.)   
[16] Merx-Chermin M,Wim JN.Factors Influencing Knowledge Creation and Innovation in an Organization [J]. Journal of European Industrial Training,2005,29(2): 135-147.   
[17]刘岩芳，袁永久．面向知识创新的研究型大学内部知识整 合影响因素实证研究[J]．科技进步与对策，2013，30(7): 139-145.(Liu Yanfang,Yuan Yongjiu. Empirical Research on Effect Factorsof Knowledge Integration in Research University Toward Knowledge Innovation [J]. Science & Technology Progress and Policy,2013,30(7): 139-145.)   
[18] 王玉梅，张靖．基于系统动力学的组织知识创新影响因素 分析[J]．青岛科技大学学报：社会科学版，2009，25(4): 58-62.(Wang Yumei, Zhang Jing.Analysis of the Innovation Factors of Knowledge Organization Based on the System Dynamics[J]. Journal of Qingdao University of Science and Technology: Social Sciences,2009,25(4): 58-62.)   
[19] 裴乐．非政府组织的知识创新：需求，影响因素与路径[J]. 北华大学学报:社会科学版,2014,15(1):127-131.(Pei Le. Knowledge Innovation of Non-Government Organization: Demands,Influencing Factors and Routes [J].Journal of Beihua University: Social Sciences,2014,15(1):127-131.)   
[20] 袁静，王坤．知识创新的过程与影响因素研究[J]．科技管 理研究，2012，32(11):195-198.(Yuan Jing，Wang Kun. Research on the Process and Influencing Factors of Knowledge Innovation [J]. Science & Technology Management Research, 2012, 32(11): 195-198.)   
[21］ 刘亭亭，吴洁，张宇洁．产学研合作中高校知识创新能力 提升的动态模型构建研究——基于知识转移视角[J].科技 管理研究,2013,33(10): 92-95.(Liu Tingting,Wu Jie,Zhang Yujie. Research on Dynamic Model Constructionof University Knowledge Innovation Ability in the UniversityIndustryCooperation[J].ScienceandTechnology Management Research,2013,33(10):92-95.) [22]易力，胡振华．知识吸收能力对集群企业自主创新影响的 系统动力学分析[J]．中国科技论坛,2013(1):78-84.(YiLi, Hu Zhenhua.System Dynamic Analysis on the Effects of KnowledgeAbsorptiveCapacitiesof Cluster Firms' Indigenous Innovation[J].Forum on Science and Technology in China,2013(1):78-84.) [23]姚艳虹，周惠平．产学研协同创新中知识创造系统动力学 分析[J]．科技进步与对策，2015，32(4):110-117.(Yao Yanhong，Zhou Huiping. System Dynamic Analysison Knowledge Creation in the University-Industry Collaborative Innovation [J]. Science & Technology Progress and Policy,   
2015,32(4): 110-117.) [24]王延荣，宋磊，赵文龙．产学研协同创新的系统动力学建 模与仿真[J]．华北水利水电大学学报：社会科学版，2015,   
31(4):90-95.(Wang Yanrong，Song Lei，Zhao Wenlong. System Dynamics Modeling and Simulation of IndustryUniversity Research Institute Collaborative Innovation [J]. Journal of North China University of Water Resources and Electric Power:Social Science Edition,2015,31(4): 90-95.)

# 作者贡献声明：

罗政：设计研究方案，论文撰写及最终版本修订;  
李玉纳：提出模型验证方案，修改论文。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版http://www.infotech.ac.cn。  
[1]罗政，李玉纳．企业协同知识创新因果关系图.mdl．企业协同知识创新因果关系图.  
[2]罗政，李玉纳.企业协同知识创新流图.mdl.企业协同知识创新流图.

收稿日期:2015-12-16   
收修改稿日期:2016-01-20

# Influencing Factors of Collaborative Knowledge Creation in Enterprise Value Chain

Luo Zheng'Li Yu'na² 1(School of Information Management, Wuhan University, Wuhan 430072, China) 2(School of Management, Wuhan University of Technology, Wuhan 430070, China)

Abstract:[Objective]This research aims to identify causal relationshipofcollaborative knowledge creation in the enterprise value chain.It also creates a model to improve the effectiveness of knowledge innovation.[Methods] We proposed a dynamics model for influencing factors ofcollaborative knowledge creation in enterprise value chain. Upon identifying these factors,we built the model based on findings from the causal relationshipanalysis.[Results]Using the Vensim PLE package,we constructed a simulation system with the proposed dynamics model, which further examined itseffectivenessand sensitivity.This model represented theactual processofcollaborative knowledgecreation. [Limitations] We employed simulation data to examine the model.Further test is needed with actual data from the enterprise value chain.[Conclusions] We propose an optimization plan for colaborative knowledge creation based on the simulation results,aiming to improve its effectiveness in the enterprise value chain.

Keywords: Enterprise value chain Collaborative knowledge creation Influencing factorsSystem dynamics

# AndrewW.Mellon基金会资助斯坦福大学图书馆等多家单位研究关联开放数据

Andrew W.Mellon基金会资助斯坦福大学图书馆1500万美元研究项目，以支持其与多家单位共同发展和推进关联开放数据的使用。斯坦福大学图书馆将与一系列图书馆进行紧密协作，包括哥伦比亚大学图书馆、康奈尔大学图书馆、哈佛大学图书馆、美国国会图书馆和普林斯顿大学图书馆，以提升现有图书馆基础设施水平来创造、存储和共享文献数据。

目前，世界各地的图书馆依靠的是20 世纪60年代提出的信息交流和存储标准系统。尽管这一系统变革了整个行业，将图书从对卡片目录的依赖中解脱出来，并且使得图书馆迈人网络时代，但是语义网的发展依旧使得该系统的进一步使用面临着困难。

项目组成员将会开发一个新的、分布式的基于网络架构的模型，根据斯坦福大学技术和访问服务部助理馆长 PhilirSchreur的说法，“这将会从根本上改变图书馆与语义网的交互方式。”

对于语义网来说，图书馆中的很多信息要么不可利用，要么不够智能。“图书馆的大部分数据以历史格式锁存，很难将其与网络相连接，”Schreur说道。“关联数据使用基础的网络标准来发布数据，从而能相互连接，并在网络上更为可见”

改进现有系统正稳步推进，每个图书馆也都在试验新的方法；这一项目能将所有这些努力进行有机整合。斯坦福大学图书馆将会进一步推进以上的工作，建设一个共享环境，使得研究机构在其中能相互通气，持续参与并交流想法。

“该项目将会使得图书馆数据的呈现从只能被操作电脑界面的人所理解转变为机器能够理解并且进行语义连接，”Schreur说道，“连接跨时空概念和内容的大门已经被打开。”

(编译自:http:/library.stanford.edu/news/2016/04/stanford-libraries-leads-collaborative-grant)

(本刊讯)