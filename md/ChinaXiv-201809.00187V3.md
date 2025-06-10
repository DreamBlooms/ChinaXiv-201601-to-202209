# 一种基于多阶认知诊断模型测评\*科学素养的方法

詹沛达 于照辉　李菲茗 王立君(浙江师范大学教师教育学院，金华 321004)

摘要科学素养是指作为一名有反思意识的公民所具有的解决科学问题和运用科学理念的能力。为实现在认知诊断中对科学素养的测评，本文基于 PISA 2015 科学素养测评框架首次提出科学素养包含的三阶潜在结构，使用新提出的多阶认知诊断模型对PISA2015科学测评数据进行分析，并通过模拟研究探究新模型的心理测量学性能。结果表明:(1)新模型能够较好地分析包含三阶潜在结构的科学素养;(2)科学知识对科学素养的影响最大，科学背景次之，科学能力的影响最小;(3)全贝叶斯 MCMC 算法能够为新模型提供较精准的参数估计。

关键词 科学素养；认知诊断;PISA;DINA模型 分类号 B841

# 1引言

“科学技术推动了生产力的发展、经济的繁荣和社会的进步，促进了人们的生产方式、生活方式和思维方式的变革。科学技术的快速发展对每一位公民的科学素养提出了新的要求”（中华人民共和国教育部，2017)。实际上，关于如何提高个体或公民的科学素养是一个交叉学科问题，它一直以来都是科学教育、教育心理学和学习科学等学科领域的学者们共同关注的重难点。科学素养是一个不断发展的概念，它的内涵和界定方式会随时代发展而发生改变(see Miller，1983；OECD，2006)。2017 年,《义务教育小学科学课程标准》将“科学素养"定义为“了解必要的科学技术知识及其对社会与个人的影响，知道基本的科学方法，认知科学本质，树立科学思想，崇尚科学精神，并具备一定的运用它们处理实际问题、参与公共事务的能力”，从本质上讲，该定义就是说“科学素养是指作为一名有反思意识的公民所具有的解决科学问题和运用科学理念的

能力”(OECD,2016)。

为实现对科学素养的客观测评，国际学生评估项目(Programme for International Student Assessment,PISA)在2015年把科学素养的内涵划分为科学能力(Competencies)、科学知识(Knowledge)、科学背景(Contexts)和科学态度(Attitudes)四个相互关联的维度，并给出了相应的测评或评估框架，见图1。这就要求学生在一定的科学背景中，根据自己的科学态度，运用科学知识来解决科学问题，从而展现出自己的科学能力(刘克文，李川,2015)。PISA2015测评框架是在 PISA 2006 科学测评框架(OECD,2006)的基础上修订而来的，其发展主要体现在对科学知识维度的更详细划分。科学测评框架的逐步完善，是在实践基础上不断重新认识科学素养的结果。可以说，PISA2015科学素养测评框架是目前最新最具可操作性的科学素养测评框架。

除具有可操作性的测评框架外，一个适宜测评方法也同样重要。适宜的测评方法应能够匹配测评框架，并能够实现对科学素养客观且准确的评价。

![](images/5031f8faabbda426c815913babdd92663f4d5344085ca713a7cc0fcf3cbfada2.jpg)  
图1PISA2015 科学素养测评框架(来源：OECD (2016)第 23页图 2.2).

然而，目前国内外已有研究绝大多数只是对公民或中小学学生科学素养的问卷调查(e.g.，Roos，2014;高宏斌,2011；秦浩正，钱源伟,2008)，这仅是对科学素养整体现状的大致了解。而且这些调查多采用自我报告法，主观性较强，存在一定的社会赞许性。仅有少许研究关注到了对科学素养的测评(e.g.,胡咏梅，杨素红，卢珂，2012)。除研究方法有待改进外，目前绝大多数研究所使用的测评/数据分析方法和理论也较为落后，仍以经典测量理论为主(e.g.，R00s，2014；任磊，张超，何薇，2013)，仅有个别研究使用到了题目作答理论(item responsetheory,IRT)模型(e.g.，胡咏梅等,2012)。另外，需要强调的是尽管PISA为科学素养建构了多维结构，但数据分析时仍使用了单维IRT 模型(OECD,2017)。即PISA现有的测评方法并不匹配测评框架，其主要原因之一是因为PISA更关注的是国家/经济体的整体现状而非个体参与者，所以对个体使用一个笼统的单维潜在特质可以简化整体研究的复杂性。而当把个体视为测评主体时，就需要更复杂的测评方法(e.g.,Zhan,Jiao,&Liao,2018)。综上所述,为在PISA2015科学素养测评框架下实现对科学素养客观且准确的测评，需要尝试从新的视角切入，使用或开发更适宜的测评方法。

近些年，随着认知心理学的发展，研究者们逐渐发现被试在完成某项任务时常需要多种能力的相互配合，因此，早期心理测量模型中的单维性假设并不符合实际(Reckase，2009；Wang& Chen,2004；康春花，辛涛，2010；詹沛达，王文中，王立君，2013)。另外，除了简单的总分外，人们也希望能从被试的实际作答情况中获得更丰富的信息，以便对被试做出更客观的评价和补救。基于此，认知诊断测评(cognitive diagnostic assessment,CDA)在近一二十年内受到了国内外学者的更多关注(Rupp,

Templin，&Henson，2010；涂冬波，蔡艳，丁树良，2012)。CDA是指在心理与教育测量学中对个体认知过程、加工技能或知识结构(统称为属性)的诊断性测评。作为一种将形成性评价和终结性评价相结合的综合评价形式(詹沛达，陈平，边玉芳，2016),CDA的初衷是通过测评个体对属性的掌握状态为教师或干预者提供诊断反馈报告，进而帮助他们实施补救教学或有针对性的干预(Zhan et al.,2018)。CDA改变了以往评价方法重结果、轻过程的弊端，符合当前我国一些教育政策导向。比如：《基础教育课程改革纲要(试行)》中“改变课程评价过分强调甄别与选拔的功能，发挥评价促进学生发展、教师提高和改进教学实践的功能"的具体目标。因此，如何在CDA中实现对科学素养的测评是一个兼具理论意义和实践意义的议题。

下文中，我们首先将对PISA2015科学素养测评框架做进一步解读，明确该框架所包含的三阶潜在结构；其次，对现有的高阶认知诊断模型(higher-order cognitive diagnosis model;HO-CDM)进行介绍并阐明其局限性；然后，提出一种新的多阶认知诊断模型(multi-order CDM；MO-CDM)，以期在CDA中满足对三阶或更高阶潜在特质的分析需求，并匹配PISA2015科学素养测评框架，实现对科学素养的准确测评。再然后，我们以PISA2015科学测评数据分析为例来说明新模型的现实可应用性，并对数据分析结果进行解读。最后，通过一个模拟研究来探究新模型的参数估计返真性。

# 2科学素养包含的三阶潜在结构

PISA2015认为科学素养的核心是科学能力，而科学能力的展现需要在特定的科学背景下辅以足够的科学知识，并受到科学态度的影响。这4个维度相辅相成，共同组成了科学素养，即科学素养是科学能力、科学知识、科学背景和科学态度的高阶/高位概念，个体科学素养的高低决定了他在这4个维度方面的表现情况。进一步，根据《PISA2015测评与分析框架》(OECD,2016)：

(1）科学能力又被细分为3种子能力，分别是科学地解释现象、评估和设计科学探究和科学地解释数据和证据。即科学能力是3这子能力的高阶概念，个体科学能力的高低决定了其3项子能力的高低;

(2）科学知识又被细分为3种子知识，分别是内容性知识、程序性知识和认知性知识。即科学知识是这3种子知识的高阶概念，个体对科学知识的掌握程度决定了其对3种子知识的掌握程度;

(3）科学背景又被细分为3种子背景，分别是个人的、当地/国家的和全球的。即科学背景是这3个子背景的高阶概念，个体对科学背景的熟悉程度影响着其对3种子背景的熟悉程度;

(4）科学态度又被细分为3种子态度，分别是对科学的兴趣、评估科学探究方法的价值和环境意识。即科学态度是这3种子态度的高阶概念，个体的科学态度影响其3种子态度。

综上所述，基于PISA2015科学素养测评框架，科学素养包含三阶潜在结构，如图2所示。其中，第三阶潜在特质为科学素养，是PISA2015科学素养测评框架中的最高阶概念；第二阶潜在特质包括：科学能力、科学知识、科学背景和科学态度，是该测评框架中的4个主要概念；而第一阶潜在特质为科学地解释现象、评估和设计科学探究等12项，是该测评框架中的低阶概念。

为在 CDA 中实现对科学素养的测评，需要一种能够分析科学素养三阶潜在结构的CDM。鉴于目前尚未有CDM能够处理三阶潜在结构，这就需要我们建构新的模型，以期满足测评需求。

# 3多阶认知诊断模型

# 3.1 高阶认知诊断模型及其局限性

在心理学和教育学中，潜在特质除了可能存在多维性外，还可能进一步存在层阶关系，这被称为高阶(层阶)潜在特质，比如，图2所示的科学素养所包含的三阶潜在结构；再比如，韦氏成人智力量表中也测量了三阶潜在特质：第一阶中包含了13个子测验并分别测量了一种潜在特质，在第二阶中这13种潜质就被归为4种外延更广的潜在特质(言语能力、知觉推理、工作记忆和信息加工速度)，而在第三阶中这4种潜在特质又包含在一般智力之中(Ryan& Schnakenberg-Ott,2003)。

高阶潜在特质的概念是建构在多维潜在特质概念之上的，用于描述多个潜在特质之间可能存在的结构关系。基于此，研究者们开发了两类不同的高阶心理测量模型(陈飞鹏，詹沛达，王立君，陈春晓，蔡毛，2015)：基于多维IRT模型建构的高阶IRT模型(de la Torre & Song,20o9;Huang,Wang, Chen,& Su，2013；Rijmen，Jeon，von Davier，& Rabe-Hesketh,2014)和基于CDM建构的高阶认知诊断模型(HO-CDM) (de la Torre & Douglas,2004; TemplinHenson，Templin,& Roussos,20o8；Zhan,Wang，&Li,inpress)，本文聚焦于后者。

在CDA中，鉴于被试对属性的掌握可能受到一个(或多个)更高阶的潜在特质的影响且为减少参数估计的数量，dela Torre 和Douglas(2004)提出了高阶潜在结构模型

$$
\mathrm { l o g i t } ( P ( { \mathfrak { a } } _ { k } = 1 | \mathbf { \theta } _ { n } ) ) = \lambda _ { 1 k } \theta _ { n } - \lambda _ { 0 k } .
$$

$\mathrm { l o g i t } ( x ) = \log \left( \frac { x } { 1 - x } \right) ; P ( \mathfrak { a } _ { n k } = 1 \mid \theta _ { n } ) .$ 为给定第二阶潜在特质 $\boldsymbol { \theta } _ { n }$ 后被试 $n$ 掌握属性 $k$ 的概率； $\lambda _ { 0 k }$ 为属性 $k$ 的难度参数， $\lambda _ { 1 k }$ 为属性 $k$ 的区分度参数。式(1)所描述的潜在结构见图3。式(1)是潜在结构模型，将它们与测量模型相结合即可得到HO-CDM。比如，将它们与 DINA 模型(Junker& Sijtsma,2001;Macready&Dayton，1977)相结合即可得到高阶DINA (HO-DINA)模型。限于高阶潜在结构模型的理论局限，HO-DINA模型只能处理包含二阶潜在结构的数据，无法实现对科学素养所包含的三阶潜在结构的测评，不满足本研究的需求。

![](images/59237f57552ad8c3efb47342d65ab921feee00faa7d41ca0b6ea4e416ed329c3.jpg)  
图2PISA2015科学素养所包含的三阶潜在结构

![](images/64fac611d3f43e3f4976ba3e79254ba35e5c4393f397ec9a3c5d7fe8816e2554.jpg)  
图3CDA中二阶潜在特质与属性间的关系示例图注：0为第二阶潜在特质; $\mathfrak { a }$ 为(第一阶)属性; $K$ 为总属性数量; $I$ 为总题目数量

# 3.2 多阶认知诊断模型的建构

# 3.2.1 多阶潜在结构模型(MO-LSM)

针对目前缺乏可处理三阶或更高阶潜在结构的CDM这一问题，本研究借鉴高阶IRT模型的建模思路，把线性潜在结构模型引入到当前的二阶潜在结构模型(式(1))之上，提出多阶潜在结构模型(multi-order latent structural model; MO-LSM)。首先，假设潜在特质存在多阶结构， ${ \boldsymbol { \theta } } _ { n m } ^ { ( h ) }$ 表示被试 $n$ 在第 $h$ $( h \geqslant 2 )$ 阶中的第 $\mathbf { \nabla } _ { m }$ 个潜在特质，则 $\theta _ { n m } ^ { ( h ) }$ 与更高阶的潜在特质 $\mathbf { \boldsymbol { \mathfrak { \mathbf { \theta } } } } _ { n } ^ { ( h + 1 ) }$ 之间的线性潜在结构关系可被描述为：

$$
\Theta _ { n m } ^ { ( h ) } = { \boldsymbol { \Upsilon } } _ { m } ^ { \prime ( h ) } \mathbf { \bullet } _ { n } ^ { ( h + 1 ) } + \mathbf { \varepsilon } _ { n m } ^ { ( h ) } = \sum _ { p = 1 } ^ { P } \gamma _ { m p } ^ { ( h ) } \Theta _ { n p } ^ { ( h + 1 ) } + \pounds _ { n m } ^ { ( h ) } \ ,
$$

式中， $\gamma _ { m } ^ { \prime ( h ) }$ 为第 $h$ 阶回归向量； $\mathfrak { E } _ { n m } ^ { ( h ) }$ 为第 $h$ 阶中的第 $\mathbf { \nabla } _ { m }$ 个潜在特质的残差； $\Theta _ { n p } ^ { ( h + 1 ) }$ 为被试 $n$ 在第 $h + 1$ 阶中的第 $p$ 个潜在特质。需要说明的是，除了线性关系外，式(2)也可以修改为非线性关系(e.g.，多项式)，但鉴于心理学研究中通常假设潜变量之间为线性关系(e.g.，结构方程模型)，且为降低模型复杂性，本研究暂只关注线性关系(de la Torre& Song,2009;Huang et al.,2013;Rijmen et al.,2014)。将式(2)引入式(1)中即可得到MO-LSM：

$$
\begin{array} { r } { \mathrm { l o g i t } ( P ( \mathfrak { a } _ { n k } = 1 | \mathbf { \theta } _ { n } ^ { ( h ) } ) ) = \sum _ { m = 1 } ^ { M } \lambda _ { 1 m k } \theta _ { n m } ^ { ( h ) } - \lambda _ { 0 k } = } \end{array}
$$

$$
\begin{array} { r } { \sum _ { m = 1 } ^ { M } \lambda _ { 1 m k } ( \sum _ { p = 1 } ^ { P } \gamma _ { m p } ^ { ( h ) } \Theta _ { n p } ^ { ( h + 1 ) } + \pounds _ { n m } ^ { ( h ) } ) - \lambda _ { 0 k } . } \end{array}
$$

基于条件独立性假设，MO-LSM假设当给定更高一阶的潜在特质时，各低阶潜在特质之间相互独立。需要说明的是，尽管式(3)在理论上能够处理多阶的潜在特质，但考虑到现实测验情境中出现四阶潜在特质的可能性已经较小，且为匹配PISA2015科学素养所包含的三阶潜在结构，本研究聚焦于仅包含1个第三阶潜在特质的三阶潜在结构模型，如图4，该模型可被描述为：

$$
\log \mathrm { i t } ( P ( \mathfrak { a } _ { n k } = 1 | \mathbf { \theta } _ { n } ^ { ( 2 ) } ) ) = \sum _ { m = 1 } ^ { M } \lambda _ { 1 m k } \theta _ { n m } ^ { ( 2 ) } - \lambda _ { 0 k } =
$$

$$
\sum _ { m = 1 } ^ { M } \lambda _ { 1 m k } ( \gamma _ { m } ^ { ( 2 ) } \mathsf { \theta } _ { n } ^ { ( 3 ) } + \mathsf { \pm } _ { n m } ^ { ( 2 ) } ) - \lambda _ { 0 k } .
$$

为使模型可识别，设定 ${ \Theta } _ { n } ^ { ( 3 ) } { \sim } N ( 0 , \ 1 )$ 且 $\mathfrak { E } _ { n m } ^ { ( 2 ) } { \sim } N ( 0 ,$ （20$1 - \gamma _ { m } ^ { ( 2 ) ^ { 2 } } )$ ，进而有 $\Theta _ { n m } ^ { ( 2 ) } { \sim } N ( 0 , \ 1 )$ ，此时，任意两个第二阶潜在特质之间的相关系数等于 $\gamma _ { m } ^ { ( 2 ) } \times \gamma _ { m ^ { \prime } } ^ { ( 2 ) }$ 。当γ2) =1时，有ε(2)=0，则式(4)退化为式(1)。

![](images/f60d8e4579a4d94b02d6aadc2d7d97fcb86b0ae63e3f066eb3125a8699f68387.jpg)  
图4CDA中第三阶潜在特质与属性间的关系示例图.注： ${ \boldsymbol { \theta } } ^ { ( 3 ) }$ 为第三阶潜在特质; ${ \boldsymbol { \theta } } ^ { ( 2 ) }$ 为第二阶潜在特质; $\textbf { \em a }$ 为(第一阶)属性； $K$ 为总属性数量; $I$ 为总题目数量。

# 3.2.2 MO-DINA模型

通常，CDM由两部分组成：测量模型和潜在结构模型(Ruppetal.,2010)，前者定义了被试作答题目的正确概率，后者描述了属性之间的结构关系。在3.2.1中，我们已经定义了MO-LSM，为提高参数估计的精度和效率，我们选用引入题目内特征依赖性的贝叶斯DINA 模型(Zhan,Jiao,Liao,& Bian,2018)作为测量模型，模型详述见附录。

本研究采用全贝叶斯马尔可夫链蒙特卡洛(MCMC)算法来实现对MO-DINA模型的参数估计,并基于JAGS 软件(Version 4.3.0)实现。各待估计参数的先验分布详见附录，相应的JAGS代码也可向作者索取。关于如何使用JAGS实现对贝叶斯CDM的参数估计，可参阅 Zhan、Jiao、Man 和Wang (in press)。

# 4PISA2015科学测评数据分析

# 4.1 研究问题与目的

通过对PISA2015科学测评数据的分析，呈现出 MO-DINA模型的现实需求和可应用性。基于上文中对科学素养所包含的三阶潜在结构划分，在针对科学素养的测评中，我们想测评被试在所有第一阶、第二阶和第三阶潜在特质(属性)上的表现情况。因此，本研究欲回答两个问题：(1)MO-DINA模型是否适用于测评含三阶潜在结构的科学素养？如果可以，那么(2)科学素养的子维度中哪个对它的影响最大？即在PISA2015中，科学素养的核心维度是哪个？

# 4.2 数据描述

# 4.2.1 多阶潜在特质设定

根据本文第2节的内容，PISA2015科学素养包含了三阶潜在结构，各阶潜在特质的名称及它们之间的结构关系见图2。在数据分析时，我们依据MO-DINA模型将模型参数与多阶潜在特质进行匹配，第三阶潜在特质： ${ \theta } ^ { \left( 3 \right) } \mathrm { \longrightarrow }$ 科学素养；第二阶潜在特质： ${ \theta _ { 1 } } ^ { ( 2 ) } \longrightarrow$ 科学能力， ${ \theta _ { 2 } } ^ { ( 2 ) } \longrightarrow$ 科学知识, ${ \theta _ { 3 } } ^ { ( 2 ) } \longrightarrow$ 科学背景；第一阶潜在属性： $ \mathrm { A l }  $ 科学地解释现象， $\mathbf { A } 2 \longrightarrow$ 评估和设计科学探究, $\mathrm { \bf A } 3 \longrightarrow$ 科学地解释数据和证据，$\Delta 4 $ 内容性知识, $\lvert \mathrm { A } 5 $ 过程性知识， $\mathbf { A 6 } {  }$ 认知性知识, $\lvert \mathrm { A } 7 $ 个人背景， $\bf { A 8 } \longrightarrow$ 地区/国家背景， $\lvert \mathrm { A } 9 $ 全球背景。需要说明的是，在第二阶潜在特质中，因为科学态度是通过学生问卷来获取的，并不包含在认知题目数据中，所以本研究暂不涉及。

# 4.2.2 被试与题目

根据《PISA2015技术报告》(OECD,2017)的“附录A：题池的分类(ItemPoolClassification)"，数据清理过程如下：(1)选用"2015fieldtrialandmainsurveycluster"中S01所包含的18道题目，共47548人；(2)选用中国(QCH)样本，共1079人；(3)将数据中"not reached"和"no response"等设定为缺失值NA;(4)删除在18题中全部缺失作答的3名被试，剩余1076人;(5)将剩余所有缺失值视为完全随机缺失。全贝叶斯MCMC算法可以根据其他参数的估计值计算出缺失值的后验分布，这是一种“自动填补"的过程，无需做其他设定。另外,DS519Q01原为三级评分题目(i.e., ${ Y _ { n i } } ~ \in \{ 0 , ~ 1 , ~ 2 \} )$ ，限于MO-DINA模型暂只能处理二级评分题目，我们将该题目分数二级化： $0 { \stackrel { \textstyle \to 0 } { \longrightarrow } } 0 , 1 { \stackrel { \textstyle \to 0 } { \longrightarrow } } 0 , 2 { \longrightarrow } 1$ 。最终，清理后的数据包含$N = 1 0 7 6$ 人在 $I = 1 8$ 题上的二级评分数据。属性与题目之间的对应关系(i.e.,Q矩阵)见表1。

表1PISA2015科学测验部分题目的Q矩阵  

<html><body><table><tr><td>CS466Q05 CS466Q0 CS466Q CS527Q0 CS527Q0 CS527Q01 DS519Q0 CS519Q0 0 10 0 10 0 I ＩＩ I II IＩ I I I I I</td></tr></table></body></html>

注：空白为"O"；选用"2015 field trial and main survey cluster” $\mathbf { \Sigma } = \mathbf { \Sigma }$ S01的题目。

# 4.3 分析

本研究选用MO-DINA、HO-DINA和DINA模型分别对该数据进行分析并比较。在潜在结构模型方面：对MO-DINA而言，其多阶潜在结构依据图2中结构设定(不考虑科学态度)；对于HO-DINA模型而言，假设第一阶属性直接受科学素养的影响，忽略第二阶潜在特质，即约束 $\gamma _ { m } ^ { ( 2 ) } = 1$ ；对于 DINA模型而言，忽略所有多阶潜在结构，直接使用无结构潜在结构模型。

三模型均使用两条马尔可夫链(随机起点)，每条链包含10,000次迭代，其中预热5，000次迭代,稀疏值1。最终剩余10,000次迭代用于参数估计。使用潜在量尺缩减因子(PSRF)(Brooks&Gelman,1998)进行参数估计收敛检验，本研究中所有参数的PSRF均小于1.2，表示参数估计已收敛。

本研究使用AIC、BIC和DIC作为模型-数据相对拟合指标，指标值越小的模型表明该模型与数据的拟合相对更好。另外，本研究使用后验预测模型检验(posterior predictive model checking,PPMC)来评估模拟-数据绝对拟合指标，其中后验预测概率(ppp)，接近0.5则表明模型与数据拟合，小于0.05或大于0.95则表示该模型不拟合该数据。

# 4.4结果

表2呈现了3个模型的各项模型-数据拟合指标值。首先，根据ppp值,3个模型均拟合该数据。其次，4个相对拟合指标都判断DINA模型的相对拟合最差，说明针对该数据应考虑高阶潜在结构。然后，在4个相对拟合指标中， $- 2 \mathrm { L L }$ 和AIC均判断MO-DINA模型的相对拟合更好，而BIC和DIC则判断HO-DINA 模型的相对拟合更好，这是由 BIC和DIC对模型复杂性的惩罚相对更高导致的。另外，由于HO-DINA 模型是 MO-DINA 模型的特例(i.e.,约束 ${ \gamma _ { m } } ^ { ( 2 ) } = 1 _ { . }$ )，似然函数比检验 $( \Delta - 2 \mathrm { L L } = 1 3$ ， $d f = 3$ $p \ < \ 0 . 0 5 )$ 认为两模型差异显著，应选择 MO-DINA模型。最后，再结合本研究的研究目的和问题，我们综合认为MO-DINA模型更适宜于本研究。下文将基于MO-DINA模型的分析结果进行解读。

表2PISA2015科学测验部分题目数据的模型-数据拟合指标值.  

<html><body><table><tr><td>模型</td><td>-2LL</td><td>AIC</td><td>BIC</td><td>DIC</td><td>PPp</td></tr><tr><td>MO-DINA</td><td>19332</td><td>19389</td><td>19673</td><td>24775</td><td>0.738</td></tr><tr><td>HO-DINA</td><td>19345</td><td>19399</td><td>19668</td><td>24644</td><td>0.716</td></tr><tr><td>DINA</td><td>19415</td><td>19962</td><td>22687</td><td>24856</td><td>0.692</td></tr></table></body></html>

表3PISA2015科学测验部分题目的参数估计值.  

<html><body><table><tr><td>题目</td><td>gi</td><td>Si</td><td>95% CI (gi)</td><td>95% CI (si)</td><td>IDIi</td></tr><tr><td>DS269Q01</td><td>0.325</td><td>0.119</td><td>(0.263,0.386)</td><td>(0.082,0.158)</td><td>0.556</td></tr><tr><td>DS269Q03</td><td>0.459</td><td>0.070</td><td>(0.397,0.521)</td><td>(0.042,0.102)</td><td>0.471</td></tr><tr><td>CS269Q04</td><td>0.237</td><td>0.351</td><td>(0.190,0.289)</td><td>(0.304,0.398)</td><td>0.412</td></tr><tr><td>CS408Q01</td><td>0.434</td><td>0.181</td><td>(0.373,0.489)</td><td>(0.142,0.222)</td><td>0.385</td></tr><tr><td>DS408Q03</td><td>0.033</td><td>0.810</td><td>(0.015,0.058)</td><td>(0.776,0.843)</td><td>0.157</td></tr><tr><td>CS408Q04</td><td></td><td></td><td>(0.374,0.487)</td><td>(0.219,0.300)</td><td>0.310</td></tr><tr><td></td><td>0.429</td><td>0.261</td><td></td><td></td><td></td></tr><tr><td>CS408Q05</td><td>0.295</td><td>0.213</td><td>(0.220,0.357)</td><td>(0.160,0.266)</td><td>0.492</td></tr><tr><td>CS521Q02</td><td>0.548</td><td>0.133</td><td>(0.494,0.602)</td><td>(0.097,0.170)</td><td>0.319</td></tr><tr><td>CS521Q06</td><td>0.849</td><td>0.008</td><td>(0.809,0.883)</td><td>(0.002,0.017)</td><td>0.143</td></tr><tr><td>DS519Q01</td><td>0.106</td><td>0.524</td><td>(0.047,0.163)</td><td>(0.457,0.582)</td><td>0.370</td></tr><tr><td>CS519Q02</td><td>0.281</td><td>0.304</td><td>(0.231,0.332)</td><td>(0.256,0.353)</td><td>0.415</td></tr><tr><td>DS519Q03</td><td>0.323</td><td>0.228</td><td>(0.212,0.404)</td><td>(0.174,0.282)</td><td>0.449</td></tr><tr><td>CS527Q01</td><td>0.033</td><td></td><td>(0.012,0.055)</td><td>(0.742,0.831)</td><td>0.179</td></tr><tr><td>CS527Q03</td><td></td><td>0.788</td><td></td><td>(0.289,0.371)</td><td>0.277</td></tr><tr><td></td><td>0.393</td><td>0.330</td><td>(0.343,0.442)</td><td></td><td></td></tr><tr><td>CS527Q04</td><td>0.281</td><td>0.373</td><td>(0.203,0.343)</td><td>(0.316,0.423)</td><td>0.346</td></tr><tr><td>CS466Q01</td><td>0.448</td><td>0.182</td><td>(0.378,0.514)</td><td>(0.140,0.226)</td><td>0.370</td></tr><tr><td>CS466Q07</td><td>0.649</td><td>0.050</td><td>(0.543,0.726)</td><td>(0.026,0.080)</td><td>0.301</td></tr><tr><td>CS466Q05 0.342 0.243</td><td></td><td></td><td>(0.284,0.398)</td><td>(0.184,0.300)</td><td>0.415</td></tr></table></body></html>

注： $9 5 \%$ $C I = 9 5 \%$ 贝叶斯可信区间; $g _ { i } =$ 猜测参数, $s _ { i } =$ 失误参 数； $I D I _ { i } =$ 题目区分度.

表4PISA2015科学测验部分题目的题目均值向量和方差协方差矩阵估计值.  

<html><body><table><tr><td colspan="2">参数</td><td>后验均值</td><td>95% CI</td><td>相关系数</td></tr><tr><td rowspan="3">£</td><td></td><td>1.773</td><td>(0.873,3.571)</td><td>1.000</td></tr><tr><td>Pβ8OβOs</td><td>-1.833</td><td>(-3.719,-0.856)</td><td>-0.890</td></tr><tr><td>0²</td><td>2.394</td><td>(1.145,4.778)</td><td>1.000</td></tr><tr><td rowspan="2">μ</td><td>μβ</td><td>-0.783</td><td>(-1.408,-0.154)</td><td></td></tr><tr><td>μs</td><td>-1.212</td><td>(-1.924, -0.493)</td><td></td></tr></table></body></html>

表3呈现了题目参数的估计值。整体看这18道题的质量一般，有个别题目的猜测参数或失误参数达到了0.8左右。这点根据题目区分度 $( I D I _ { i } = 1 -$ $s _ { i } - g _ { i } )$ (delaTorre,2008)也能够发现，部分题目的区分度已经低于0.2。这其中可能原因是(1)测验Q矩阵不完备(Kohn&Chiu,2017);(2)题目涉及了Q矩阵以外的其他属性。另外，表4呈现了logit转换后的题目参数的均值向量和方差协方差矩阵，可以看到两类题目参数之间呈高程度负相关，这符合Zhan 等人(2018)的观点。

就高阶潜在特质的估计值而言，首先，1个第三阶潜在特质和3个第二阶潜在特质的估计值整体分布形态基本一致，这是因为它们之间的相关性较高(3个回归系数分别为：0.847( $\cdot S E = 0 . 0 9 4 \rangle$ 、0.9731 $\langle S E = 0 . 0 2 5 \rangle$ 和0.927（ $S E = 0 . 0 5 7 _ { , }$ ，因此，它们之间相关系数约为0.8)。需要说明的是，特质之间在统计上有高相关并不一定代表它们是同一个特质。比如，尽管身高和体重之间呈高相关，但两者绝非同一种特质。因此，当特质之间存在高相关时，能否用一个笼统的高阶特质来囊括它们是需要做进一步理论判定的。基于PISA2015科学素养测评框架，我们认为这3个第二阶潜在特质在定义和内涵上都是不一样的，不应将它们视为同一特质。另外，我们还使用HO-DINA 模型和单维两参数Logistic 模型(Birnbaum，1968)分析了该批数据，发现MO-DINA模型中的第三阶潜在特质估计值与HO-DINA模型的高阶潜在特质估计值的相关系数为0.996，且与单维两参数Logistic模型的潜在特质估计值的相关系数为0.936，表明三者对“科学素养"的估计值具有高相关性，同时也表明MO-DINA模型可提供更多的分析结果信息。

图5呈现了高阶潜在结构参数的估计值，包括第三阶与第二阶潜在特质之间的回归系数和第二阶潜在特质与属性之间的属性区分度参数。首先,3个回归系数均接近于1，说明PISA2015 科学素养测评框架中把科学能力、科学知识和科学背景作为科学素养的主要组成部分的做法是合理的。其次，根据这3个回归系数的大小可知：对科学素养而言，科学知识的影响最大，科学背景的影响次之，科学能力的影响最小。然后，根据属性区分度的大小可发现，(1)科学地解释现象对科学能力的影响最大;(2)过程性知识对科学知识的影响最大；(3)地区/国家背景对科学背景的影响最大。

表5呈现了个别被试的诊断结果示例。使用MO-DINA模型进行分析时，除了能够得到9个属性的诊断分类结果外，还能够得到被试在多阶潜在特质上的估计值。以2号和23号被试为例，尽管两者在属性模式上完全一样，但他们在多阶潜在特质上的表现还是有所差异的，说明它们对属性的掌握概率存在差异。

总体而言，根据对PISA2015科学测验数据的分析结果，可以说MO-DINA模型满足本文的分析需求，在匹配PISA2015科学素养测评框架的基础上，实现了对科学素养的客观测评。

# 5模拟研究：参数估计返真性探究

# 5.1 研究设计与分析

在探讨完MO-DINA模型的现实可应用性后，我们通过一个简单的模拟研究来探讨它的参数估计返真性。模拟研究中的部分设定参考上文的实证数据分析结果，使用图7中的三阶潜在结构，即第三阶潜在特质1个，第二阶潜在特质3个，属性 $K =$ 9个；题目数量设定为 $I = 3 0$ ，Q矩阵设定见图6；题目参数按如下方法生成：(logit(gi), $\mathrm { l o g i t } ( s _ { i } ) ) ^ { \prime } = ( \beta _ { i } ,$ 注：bias $\mathbf { \Sigma } = \mathbf { \Sigma }$ 偏差;RMSE $\mathbf { \Psi } = \mathbf { \Psi }$ 均方根误差.

![](images/3ca12644500a2d3141c4a23bed6cda7fc0585937cb6af2dcf92c30e4e7cb8c34.jpg)  
图5PISA2015 科学测验中潜在结构参数估计值(基于 MO-DINA 模型).注：括号内为 $9 5 \%$ 贝叶斯可信区间.

表5PISA2015科学测验部分题目数据的诊断结果示例(基于MO-DINA模型).  

<html><body><table><tr><td>被试</td><td>a</td><td>0(2)</td><td>0(2)</td><td>0(2)</td><td>0(3)</td></tr><tr><td>2</td><td>111111111</td><td>0.582(-0.863,2.194)</td><td>0.661 (-0.586,2.174)</td><td>0.656 (-0.572,2.175)</td><td>0.664(-0.581,2.194)</td></tr><tr><td>5</td><td>010001000</td><td>-0.873 (-2.317,0.537)</td><td>-0.940 (-2.290,0.276)</td><td>-0.910 (-2.307,0.357)</td><td>-0.939 (-2.302,0.263)</td></tr><tr><td>7</td><td>010000000</td><td>-0.919 (-2.429,0.541)</td><td>-1.022 (-2.432,0.198)</td><td>-1.028 (-2.445,0.211)</td><td>-1.027 (-2.453,0.183)</td></tr><tr><td>23</td><td>111111111</td><td>0.202(-1.182,1.950)</td><td>0.283 (-1.057,1.961)</td><td>0.338(-0.999,1.959)</td><td>0.294(-1.035,1.968)</td></tr><tr><td>54</td><td>010101000</td><td>-0.831 (-2.414,0.620)</td><td>-0.880 (-2.319,0.461)</td><td>-0.870 (-2.368,0.525)</td><td>-0.886 (-2.341, 0.426)</td></tr><tr><td>86</td><td>111101110</td><td>-0.404 (-2.082,1.368)</td><td>-0.462 (-2.054,1.314)</td><td>-0.468 (-2.034,1.293)</td><td>-0.467 (-2.062,1.300)</td></tr></table></body></html>

注：括号内为 $9 5 \%$ 贝叶斯可信区间.

<html><body><table><tr><td>A1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A2</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A3</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A4</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A5</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A6</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A7</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A8</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>A9</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

![](images/c7c18972387df9e6eceb13097ddc94f096405ac95a770b31a2d6ed6939e55359.jpg)  
图6模拟研究中的 $K \times I$ 的Q’矩阵．灰色表示"1”，白色表示"0”  
图7模拟研究中题目参数的返真性.

${ \delta _ { i } } ) ^ { \prime } \sim N \left( { \bf { \mu } } , { \bf { \sigma } } \Sigma \right)$ ，其中 $\mu _ { \beta } = \mu _ { \delta } = - 2 . 1 9 7$ ， $\Sigma = [ 1 , - 0 . 6$ $- 0 . 6 , \ 1 ]$ ；属性截距向量 ${ \lambda } _ { 0 } = ( - 1 , 0 , 1 , - 1 , 0 , 1 , - 1$ ，0,1)，所有属性区分度均设定为 $\lambda _ { 1 m k } ~ = ~ 1 . 5$ ，即假设属性之间为中等程度相关；被试量设定为 $N = 1$ ，000，第三阶潜在特质从标准正态分布中生成，第三阶与第二阶潜在特质之间的3个载荷均设定为 $\gamma _ { m }$ （204号 $^ { ( 2 ) } \ = \ 0 . 8$ ，即假设各二阶潜在特质之间相关系数为0.64。模拟研究中，迭代次数、预热次数等与实证研究中的保持一致，本研究中所有参数的PSRF均小于1.2，表示参数估计已收敛。另外，使用偏差(Bias)、均方根误差(RMSE)和皮尔逊相关系数(Cor)来探究连续变量(e.g.，题目参数，潜在特质)的返真性。使用属性正确判准率(ACCR)和属性模式正确判准率(PCCR)来探究属性的返真性。

# 5.2结果

图7呈现了题目参数返真性。就Bias而言，绝大多数题目的参数Bias小于0.01，猜测参数和失误参数的Bias的平均绝对值分是0.002和0.004。就RMSE 而言，所有题目参数的RMSE 均小于0.05,猜测参数和失误参数的RMSE的均值分别是0.018和0.026。还可发现，猜测参数的RMSE随着题目测查的属性数量的增加而下降，而失误参数的RMSE随着题目测查的属性数量的增加而增加，这与以往一些研究的结论是一致的(e.g.，dela Torre,2009;Zhan,Jiao,Liao,etal.,2018)。此外，猜测参数和失误参数的Cor分别是0.981和0.964，即题目参数的估计值与真值之间呈高相关。整体而言，MO-DINA模型的题目越参数返真性较好。

图8呈现了属性参数的 $\mathsf { A C C R } _ { \circ } 9$ 个属性的ACCR均高于0.900，表明单个属性的参数估计返真性很好。另外，PCCR为0.512，考虑到属性数量为9，即有512种可能的属性模式需要被估计，根据已有研究经验，该判准率符合预期。

![](images/8b5bc4fd6ea9b5c45c2cc767f93e827c5b879d1f2ee375d93ec3b8d52a5ccaf3.jpg)  
图8模拟研究中属性参数的属性正确判准率(ACCR).

表6呈现了高阶潜在特质参数的返真性。首先,4 个高阶潜在特质的返真性类似，1，000名被试的bias 的平均绝对值约为0.1,RMSE的均值约为0.69,Cor均高于0.7。参考以往关于HO-DINA模型的研究结果(e.g.,de la Torre&Douglas,20o4;dela Torre,2009；Zhanetal.，2018)，整体而言，高阶潜在特质参数的返真性良好，满足实际应用需求。

表6模拟研究中高阶潜在特质参数的返真性.  

<html><body><table><tr><td rowspan="2">参数</td><td colspan="4">tbias</td><td colspan="4">RMSE</td><td rowspan="2">Cor</td></tr><tr><td>平均绝对值</td><td>标准差</td><td>最小值</td><td>最大值</td><td>平均值</td><td>标准差</td><td>最小值</td><td>最大值</td></tr><tr><td>0(3)</td><td>0.100</td><td>0.124</td><td>-0.380</td><td>0.368</td><td>0.686</td><td>0.090</td><td>0.408</td><td>0.983</td><td>0.721</td></tr><tr><td>0,(2)</td><td>0.100</td><td>0.125</td><td>-0.378</td><td>0.352</td><td>0.689</td><td>0.092</td><td>0.385</td><td>0.983</td><td>0.719</td></tr><tr><td>0（2)</td><td>0.104</td><td>0.126</td><td>-0.372</td><td>0.351</td><td>0.683</td><td>0.089</td><td>0.416</td><td>0.947</td><td>0.726</td></tr><tr><td>0(2)</td><td>0.104</td><td>0.130</td><td>-0.481</td><td>0.381</td><td>0.690</td><td>0.095</td><td>0.358</td><td>1.050</td><td>0.715</td></tr></table></body></html>

注：bias $\mathbf { \Psi } = \mathbf { \Psi }$ 偏差;RMSE $\mathbf { \Psi } = \mathbf { \Psi }$ 均方根误差;Cor $\mathbf { \Sigma } = \mathbf { \Sigma }$ 皮尔逊相关系数.

表7模拟研究中潜在结构参数的返真性  

<html><body><table><tr><td rowspan="2">参数</td><td colspan="4">bias</td><td colspan="4">RMSE</td><td rowspan="2">Cor</td></tr><tr><td>平均绝对值</td><td>标准差</td><td>最小值</td><td>最大值</td><td>平均值</td><td>标准差</td><td>最小值</td><td>最大值</td></tr><tr><td>20k</td><td>0.042</td><td>0.048</td><td>-0.066</td><td>0.072</td><td>0.189</td><td>0.062</td><td>0.129</td><td>0.305</td><td>0.982</td></tr><tr><td>21km</td><td>0.116</td><td>0.051</td><td>0.015</td><td>0.172</td><td>0.346</td><td>0.057</td><td>0.245</td><td>0.429</td><td>0.982</td></tr><tr><td>γ1(2)</td><td></td><td>-0.031</td><td></td><td></td><td></td><td>0.053</td><td></td><td></td><td></td></tr><tr><td>2</td><td colspan="4">-0.012</td><td colspan="4">0.076</td></tr><tr><td>23（2</td><td colspan="4">-0.012</td><td colspan="4">0.076</td></tr></table></body></html>

注：bias $\mathbf { \Sigma } = \mathbf { \Sigma }$ 偏差;RMSE $\mathbf { \Sigma } = \mathbf { \Sigma }$ 均方根误差; $\mathbf { C o r } = \mathbf { \partial }$ 皮尔逊相关系数; $\lambda _ { 0 k } =$ 属性难度参数, $\lambda _ { 1 k m } =$ 属性区分度参数,Y,Y2, $\gamma _ { 3 } =$ 第三阶与第二阶潜在特质之间的回归系数.

表7呈现了高阶潜在结构参数的返真性。首先，对于属性难度参数的返真性优于属性区分度参数的返真性，与以往关于HO-DINA模型的研究结论一致。其次，第三阶潜在特质与3个第二阶潜在特质之间回归系数的返真性也较好，RMSE均小于0.08。整体而言，潜在结构参数的返真性较好。

# 6 总结与讨论

为实现对科学素养的客观且准确的测评，本文首先根据PISA2015科学素养测评框架，提出了科学素养所包含的三阶潜在结构。然后，鉴于当前尚未有CDM能够处理包含三阶潜在结构的数据，我们提出了多阶认知诊断建模思路，并以DINA模型为例，建构了多阶DINA(MO-DINA)模型。新模型采用全贝叶斯MCMC算法实现参数估计。新模型与PISA2015科学素养测评框架相匹配，满足对科学素养的客观且准确测评的需求。之后，本文以PISA2015科学测验数据分析为例来说明新模型的现实需求和可应用性。最后，通过一个模拟研究来探究新模型的参数估计返真性。实证研究结果表明当测验数据结构存在多阶潜在结构或者数据分析者需要了解被试在多阶潜在特质方面的表现时，可考虑使用MO-DINA模型。模拟研究结果表明本文提出的全贝叶斯MCMC算法能够为MO-DINA模型提供较好的参数估计返真性。

本文中，尽管 MO-DINA 模型是针对 PISA2015科学素养所包含的三阶潜在结构而提出的，且因为 MO-DINA 模型是 HO-DINA 模型的拓广，所以理论上该模型也可以适用于其他包含二阶及以上阶潜在结构的测验，比如国际数学和科学趋势研究(TIMSS)和(中国)国家义务教育阶段教育质量监测等大规模测验均包含了多阶潜在结构。当然，本研究并不是为了说明任何包含多阶潜在结构的测验或者任何针对科学素养的测验都需要使用MO-DINA模型来进行分析，而只是从“为学习而评价(assessment for learning)"的新测评理念出发，向读者提供一种新的测评视角和方法，以期进一步丰富数据分析模型的可选项。在实践中，我们除了可根据测验编制的理论和实际测验需求等来选择分析模型外，还可以尝试使用数据驱动方法，依据模型-数据拟合指标(e.g.,AIC、BIC和DIC等)来选择合适的模型，进而得到客观的、准确的以及满足需要的数据分析结果。

需要强调的是，一般存在3个及以上的低阶潜在特质时才会考虑使用高阶模型。具体而言，对于二阶LSM(见式(1))，当 $K = 3$ 时，使用无结构潜在结构模型需要估计 $2 ^ { 3 } - 1 = 7$ 个结构参数，而使用二阶LSM仅需要估计6个参数(包含3个属性区分度和3个属性难度)；而对于第三阶与第二阶潜在特质而言，当第二阶潜在特质属性数量为3时，直接估计3者之间的相关系数和估计第三阶与第二阶潜在特质之间的载荷均需要3参数，而当第二阶潜在特质数量大于3时，则使用高阶结构可以减少待估计参数数量。比如，就图5的三阶潜在结构而言，直接使用DINA模型需要估计 $2 ^ { 9 } - 1 = 5 1 1$ 个结构参数，使用MO-DINA模型仅需要估计21个结构参数(包含9个属性区分度、9个属性难度和3个载荷),可以大幅降低待估计参数数量。但若使用包含三个维度的二阶DINA模型，则同样需要估计21个结构参数(包含9个属性区分度、9个属性难度和3个相关系数)，但此时就无法实现对“科学素养"维度的测量。因此，是否选用高阶模型，可以从理论(测验框架)和模型简约两个角度进行考虑，但究竟高阶模型是否合理，最终还要回归到理论，因为并不是所有潜在特质都适合建构高阶结构。比如，大五人格的五个维度就不应用高阶潜在特质“性格"去解释，因为从理论上讲人格的五个维度应该是独立的(尽管数据分析结果会存在低相关)。

尽管本研究将科学素养划分为了三阶潜在结构，但第一阶的属性粒度仍然较大，而通常CDA可能更适用于测评一些粒度较小的属性(see Leighton &Gierl，2007；詹沛达等，2016)。实际上，基于PISA2015科学测评框架，本研究中的第一阶属性还能够进一步划分为粒度更小的概念，比如，A1"科学地解释现象"还能够进一步划分为“回忆并应用适当的科学知识(Recall and apply appropriate scientifcknowledge)”和"提供解释性假设(Offer explanatoryhypotheses)"等小粒度概念，详见OECD(2016)的表$2 . 4 \mathrm { a }$ 。尽管理论上我们可以使用包含四阶潜在结构的MHO-DINA模型做进一步分析，但受限于《PISA2015技术报告》中并未呈现题目与小粒度概念之间的具体对应关系(即没有相应的Q矩阵)，所以本文暂只关注到对科学素养所包含的三阶潜在结构的测评。另外，如有需要，后续还可以尝试使用三阶IRT 模型(e.g.,Huang etal.,2013)来分析该数据，并与本文的分析结果进行对比研究。

当然，由于能力和精力有限，本研究仍有一些局限值得后续做出进一步探究，比如：(1)尽管本文主要关注的是潜在结构模型，但仍仅使用了DINA模型作为测量模型，后续可尝试探究基于其他测量模型时的性能;(2)未考虑属性之间可能存在的层级结构(Leighton,Gierl,&Hunka,2004)，如何将属性层级结构引入到多阶潜在结构中值得今后进一步关注(e.g.,Zhan,Ma,Jiao &Ding,in press);(3)仅涉及二分属性，而未考虑更为精细的多分属性(Karelitz,2004)，如何将 MO-LSM拓广到多分属性是一个有意义的话题(e.g.,Zhan,Wang et al.,in press); (4)假设多阶潜在结构建构合理，而现实测验中多阶潜在结构的界定可能会存在偏差，在这种情况下MO-DINA模型的表现情况值得做进一步研究;(5)MO-DINA模型仅考虑了单一的作答数据源，并未考虑诸如题目作答时间、鼠标点击次序数据等过程性数据，如何将过程性数据引入到当前建模思路中非常值得关注(e.g.，Liu,Liu,& Li,2018；Zhan et al.,2018);(6)MO-DINA模型仅针对横断测验数据，暂无法处理纵向测验数据，后续可尝试对其做进一步拓广(e.g.,Li, Cohen,Bottge,& Templin,2016； Zhan,Jiao,Liao&Li,in press);(7)实证数据分析中，未考虑科学态度维度，如何将由学生问卷测评的科学态度和由认知题目测评的其他3个维度一同纳人到对科学素养的测评中值得今后做进一步探索。

# 参考文献

Birnbaum,A.(1968).Some latent trait models and their use in inferringa student'sability.InF.M.Lord&M.R.Novick (Eds.).Statistical theories of mental test scores.AddisonWesley,Reading,MA.   
Brooks,S.P.，& Gelman，A.(1998).General methods for monitoring convergence of iterative simulations.Journal of Computational and Graphical Statistics.7(4),434-455.   
Chen,F., Zhan,P.,Wang,L., Chen,C.,& Cai,M.(2015).The development and application of higher-order item response models.Advancesin Psychological Science,23,150-157.   
[陈飞鹏，詹沛达，王立君，陈春晓，蔡毛.(2015).高阶项目 反应模型的发展与应用．心理科学进展,23,150-157.]   
de la Torre,J. (2oo8)．An empirically-based method of Q-matrix validation for the DINA model:Development and applications.Journal of Educational Measurement,45(4), 343-362.   
de la Torre,J.(2oo9)．DINA model and parameter estimation: A didactic.Journal of Educational and Behavioral Statistics,34(1), 115-130.   
de la Torre,J.,& Douglas,J.A.(20o4).Higher-order latent trait models for cognitive diagnosis.Psychometrika, 69(3), 333-353.   
de la Torre,J.,& Song,H.(2oo9). Simultaneously estimation of overall and domain abilities:A higher-order IRT model approach． Applied Psychological Measurement, 33(8), 620-639.   
Gao,H.B.(2011).Results of the eighth survey on Chinese citizens' scientific literacy were released.Bulletin of National Natural Science Foundation ofChina,25,63-64.   
[高宏斌.(2011)．第八次中国公民科学素养调查结果发布. 中国科学基金,25,63-64.]   
Hu,Y.,Yang,S.,& Lu, K.(2012). The research of assessment tools of adolescents’scientific literacy and its quality analysis.EducationResearchMonthly,3,16-21. 研发及质量分析．教育学术月刊,3,16-21.]   
Huang, H.-Y.,Wang, W.-C.,Chen, P.-H.,& Su, C.-M. (2013). Higher-order item response models for hierarchical latent traits. Applied Psychological Measurement， 37(8),619- 637.   
Junker,B. W.，& Sijtsma,K. (2001). Cognitive assessment models with few assumptions, and connections with nonparametric item response theory. Applied Psychological Measurement, 25,258-272.   
Karelitz, T. M. (2004). Ordered category attribute coding framework forcognitive assessments(Unpublished doctoral dissertation). University of Illinois at Urbana-Champaign   
Kang,C.,& Xin, T. (2010).New development in test theory: multidimensional item response theory. Advancesin Psychological Science,18(3),530-536   
[康春花，辛涛.(2010)．测验理论的新发展：多维项目反应 理论．心理科学进展,18(3),530-536.]   
Kohn, H.-F.,& Chiu, C.-Y. (2017). A procedure for assessing the completeness of the Q-matrices of cognitively diagnostic tests.Psychometrika,82(1),112-132   
Leighton,J.,& Gierl, M. (Eds.). (2007). Cognitive diagnostic assessment for education: Theory and applications. Cambridge University Press.   
Leighton,J.P.,Gierl,M.J.,& Hunka,S.M.(2004).The attribute hierarchy method for cognitive assessment: A variation on Tatsuoka's rule-space approach.Journal of Educational Measurement, 41(1),205-237.   
Li,F.,Cohen,A.,Bottge,B,& Templin,J.(2016).A latent transition analysis model for assessing change in cognitive skills. Educational and Psychological Measurement, 76(2), 181-204.   
Liu,H., Liu, Y.,& Li, M. (2018). Analysis of process data of PISA 2012 computer-based problem solving: Application of the modified multilevel mixture IRT model.Frontiers in Psychology, 9, 1372.   
Liu, K., Li, C.(2015). The content and characteristic of PISA 2015 draft science framework. Comparative Education Review,37(7),98-105.   
[刘克文，李川.(2015).PISA 2015 科学素养测试内容及特点. 比较教育研究,37(7),98-105.]   
Macready,G.B.，& Dayton,C.M.(1977). The use of probabilistic models in the assessment of mastery. Journal of Educational and Behavioral Statistics,2(2),99-120.   
Miller,J. D.(1983). Scientific literacy: A conceptual and empirical review. Daedalus,1l2(2),29-48.   
OECD. (2006). Assessing Scientific, Reading and Mathematical Literacy:A Framework for PISA 2006.Paris: PISA,OECD Publishing   
OECD. (2016). PISA 2015 Assessment and Analytical Framework: Science,Reading，Mathematic and Financial Literacy. Paris: PISA, OECD Publishing   
OECD.(2017). PISA 2015 Technical Report. Paris: PISA, OECD Publishing   
Qin,H.，& Qian,Y. (2008)．A survey report on Shanghai adolescents’ scientific literacy. Research in Educational Development, (24), 31-35.   
[秦浩正，钱源伟.(2008)．上海青少年科学素养调查报告. 教育发展研究,(24),31-35.]   
Reckase, M.D. (2oo9). Multidimensional item response theory. New York: Springer.   
Ren,L.，Zhang,C.，& He，W.(2013). Constructing and anallysis of the model of how the factors affect the scientific literacy of Chinese citizens and a comparative investigation.Studiesin Science of Science,31,983-990.   
[任磊，张超，何薇.(2013)．中国公民科学素养及其影响因 素模型的建构与分析．科学学研究,31(7),983-990.]   
Rijmen，F.， Jeon,M.，von Davier,M.，& Rabe-Hesketh，S. (2014).A third-order item response theory model for modeling the effects of domains and subdomains in large-scale educational assessment surveys. Journal of Educational and Behavioral Statistics,39(4),235-256.   
Roos,J. M. (2014). Measuring science or religion? A measurement analysis of the National Science Foundation sponsored science literacy scale 2006-2010.Public Understanding of Science, 23(7), 797-813.   
Rupp,A. A., Templin, J.,& Henson, R.A. (2010). Diagnostic Measurement: Theory，Methods,and Applications. New York, NY: Guilford Press   
Ryan，J. J.，& Schnakenberg-Ott， S.D. (2003).Scoring reliability on the Wechsler Adult Intelligence Scale-Third Edition (WAIS-III).Assessment, 10(2),151-159.   
Templin, J.L., Henson,R.A., Templin, S.E.,& Roussos,L. (2008).Robustness of hierarchical modeling of skill association in cognitive diagnosismodels. Applied Psychological Measurement, 32(7),559-574.   
The Ministry of Education of the People's Republic of China. (2017). Compulsory education primary school curriculum standards. Retrieved June 2， 2017， from http://www.moe.edu.cn/srcsite/A26/s8001/201702/t201702 15_296305.html   
[中华人民共和国教育部.(2017)．义务教育小学科学课程标 准.2017-06-02 取自 http://www.moe.edu.cn/srcsite/A26/ s8001/201702/t20170215_296305.html]   
Tu,D., Cai, Y.,& Ding, S. (2012). Cognitive diagnosis: Theory，Methods， and Applications. Beijing: Beijing Normal University Publishing Group.   
[涂冬波，蔡艳，丁树良.(2012)．认知诊断理论、方法与应用. 北京：北京师范大学出版社。］   
Wang，W.-C.，& Chen，P.-H. (2004). Implementation and measurement efficiency of multidimensional computerized adaptive testing. Applied Psychological Measurement, 28(5),295-316.   
Zhan,P.,Chen,P.，& Bian,Y.(2016).Using confirmatory compensatory multidimensional IRT models to do cognitive diagnosis. Acta Psychologica Sinica, 48(10),1347-1356.   
[詹沛达，陈平，边玉芳.(2016)．使用验证性补偿多维 IRT 模型进行认知诊断评估．心理学报,48(10),1347-1356.]   
Zhan,P.，Jiao,H.，& Liao,D.(2018).Cognitive diagnosis modelling incorporating item response times. British Journal of Mathematical and Statistical Psychology, 71(2), 262-286.   
Zhan,P., Jiao, H.,Liao,D.,& Li,F. (in press).A longitudinal higher-order diagnostic classification model.Journal of Educational and Behavioral Statistics.   
Zhan,P., Jiao,H.,Liao,M.,& Bian, Y. (2018).Bayesian DINA modeling incorporating within-item characteristic dependency. Applied Psychological Measurement. Advanced online publication. URL https://doi.org/10.1177/0146621618781594   
Zhan,P.,Jiao,H., Man, K.,& Wang,L.(in press). Using JAGS for Bayesian cognitive diagnosis modeling:A tutorial.JournalofEducational andBehavioral Statistics.   
Zhan,P.,Ma,W.,Jiao,H.,& Ding,S.(in press).A sequential higher-order latent structural model for hierarchical attributes in cognitive diagnostic assessments.Applied Psychological Measurement.   
Zhan,P.,Wang,W.-C.,& Li, X. (in press). A partial mastery, higher-order latent structural model for polytomous attributes in cognitive diagnostic assessments.Journal of Classification.   
Zhan,P.,Wang,W.-C.,& Wang,L.(2013). Testlet response theory:an introduction and new developments.Advances in Psychological Science,21(12),2265-2280.   
[詹沛达，王文中，王立君.(2013).项目反应理论新进展之 题组反应理论．心理科学进展,21(12),2265-2280.]

# 附录：

# 1.MO-DINA模型

测量模型选用引入题目内特征依赖性的贝叶斯DINA模型(Zhan,Jiao,Liao,&Bian,2018)，可表示为：

$$
P ( Y _ { n i } = 1 | \mathbf { a } _ { n } , \Psi _ { i } ) = \frac { \exp ( \beta _ { i } ) } { 1 + \exp ( \beta _ { i } ) } + ( 1 - \frac { \exp ( \delta _ { i } ) } { 1 + \exp ( \delta _ { i } ) } - \frac { \exp ( \beta _ { i } ) } { 1 + \exp ( \beta _ { i } ) } ) \prod _ { k = 1 } ^ { K } \alpha _ { n k } ^ { q _ { i } } \ ,
$$

$$
{ \pmb { \Psi } } _ { i } = \left( { \beta _ { i } \atop \alpha } \right) \sim M V N _ { { \scriptscriptstyle 2 } } ( { \pmb { \mu } } , { \pmb { \Sigma } } ) ,
$$

式中， $Y _ { n i }$ 为被试 $n$ 作答题目 $i$ 的结果; $\pmb { \Psi } _ { i } = ( \beta _ { i } , \delta _ { i } ) ^ { \prime }$ 为logit量尺上满足二元正态分布的题目参数向量(两者通常为负相关)，它们与常规DINA模型中的猜测和失误参数之间的关系为： $\log \mathrm { i t } ( g _ { i } ) = \beta _ { i }$ ，log $\mathrm { i t } ( s _ { i } ) = \delta _ { i }$ ; $q _ { i k }$ 为Q矩阵中元素， $q _ { i k } = 1$ 表示题目 $i$ 考查了属性 $k$ ，反之， $q _ { i k } = 0$ 。将该模型与正文中式(4)相结合即可得到MO-DINA模型。

# 2.MO-DINA模型中各待估计参数的先验分布设定如下：

首先，基于局部独立性假设， $Y _ { n i } \sim$ Bernoulli ( ${ \mathrm { \Delta } P } ( Y _ { n i } =$ $1 \mid { \bf a } _ { n } , \Psi _ { i } ) ) , \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm$

其次，关于题目参数的先验分布，参考Zhan，Jiao,Liao 等人(2018)，设定如下：

$$
{ \binom { \mathrm { l o g i t } ( g _ { i } ) } { \mathrm { l o g i t } ( s _ { i } ) } } = { \binom { \beta _ { i } } { \delta _ { i } } } \sim N ( { \mu } , \ \Sigma ) ,
$$

${ \pmb { \mu } } = ( { \mu } _ { \beta } , { \mu } _ { \delta } )$ 为logit转换后的题目参数均值， $\boldsymbol { \Sigma }$ 为方差协方差矩阵，有

$$
\Sigma = \left( \begin{array} { c c } { { \sigma _ { \beta } ^ { 2 } } } & { { } } \\ { { \rho _ { \beta \delta } \sigma _ { \beta } \sigma _ { \delta } } } & { { \sigma _ { \delta } ^ { 2 } } } \end{array} \right) ,
$$

${ \rho } _ { \beta \delta }$ 为logit转换后的题目参数之间的相关系数。其中， $\mu _ { \beta }$ 和 $\mu _ { \delta }$ 的超先验(hyper-prior)分布分别设定为 $\mu _ { \beta } \textrm { -- }$ $N ( - 1 . 0 9 6 , \ 4 )$ 和 $\mu _ { \delta } \sim N ( - 1 . 0 9 6 , \ : 4 )$ ，鉴于 $\mathrm { l o g i t } ( - 1 . 0 9 6 ) ~ \approx$ 0.25，所以该设定与四则一选择题的理论猜测概率相符合；另外，设定 $\Sigma \sim \mathrm { I n v W i s h a r t } ( \mathbf R , 2 )$ ，其中 $\textbf { R }$ 为二维单位矩阵。

再有，关于高阶潜在特质参数，参考Huang 等人(2013)，设定如下：$\Theta _ { n } ^ { ( 3 ) } { \sim } N ( 0 , \ 1 ) , \varepsilon _ { n m } ^ { ( 2 ) } \sim N ( 0 , \ 1 - \gamma _ { m } ^ { ( 2 ) } ) , \gamma _ { m } ^ { ( 2 ) } { \sim } N ( 0 . 5 , \ 0 . 2 5 ) I ( - 1 , \ 1 ) .$ （204号

最后，关于高阶潜在结构参数，参考Zhan，Jiao 和Liao (2018)，设定如下：

$$
\lambda _ { \scriptscriptstyle 0 k } \sim N ( 0 , 4 ) , \lambda _ { \scriptscriptstyle 1 m k } \sim N ( 0 , 4 ) I ( \lambda _ { \scriptscriptstyle 1 m k } > 0 )
$$

# Using a multi-order cognitive diagnosis model to assess scientific literacy

ZHAN Peida; YU Zhaohui; LI Feiming; WANG Lijun (College ofTeacher Education,Zhejiang Normal University,Jinhua,32loo4,China)

# Abstract

In PISA 2015,scientific literacy is defined as “the ability to engage with science-related issues,and with the ideas of science,as a reflective citizen".There are four interdependent dimensions are specified in the scientific literacy assessment framework for PISA 2015: Competencies, Knowledge, Contexts,and Atitudes. Given that knowledge of scientific literacy contributes significantly to individuals’personal， social，and professional lives,itis of vital importance to find an objectivelyand accurately assssment method for scientific literacy.However,only unidimensional IRT models were used in the analysis in PISA 2015.Which means that the analysis model does not match with such a multidimensional assessment framework.It is desired to develop a new analysis model. This study attempts to measure scientific literacy in cognitive diagnostic assessment for the first time.

According to the scientific literacy assessment framework for PISA 2O15,a third-order latent structure for scientific literacyis firstpointedout.Specifically,thescientific literacyis treatedasthe third-orderlatent trait; Competencies, Knowledge, Contexts，and Atitudes are all treated as second-order latent traits； And nine subdomains, e.g.,explain phenomena scientifically and content knowledge, were treated as first-order traits (or atributes). Unfortunately,however,there is still a lack of cognitive diagnosis models that can deal with such a third-order latent structure.To this end,a multi-order DINA (MO-DINA) model was developed in this study. The new model is an extension of the higher-order (HO-DINA) model, which is similar to the third-order IRT models.To illustrate the application and advantages of the MO-DINA model, a sub-data of PISA 2015 science assessment data were analyzed.Items were chosen from the SOl cluster,and participants were chosen from China.After data cleaning,1076 participants with 18 items were retained.Three models were fited to this sub-data and compared,the MO-DINA model, in which the third-order latent structure of scientific literacy was considered;the HO-DINA model,in which the scientific literacy was treated as a second-order latent trait and contacted with attributes directly; and the DINA model.

Allthree models appear to provide a reasonably good fit to data according to the posterior predictive model checking.According to the-2LL,AIC,BIC,and DIC,the DINA model fits the data worst,and the MO-DINA model fits the data best,the results of MO-DINA model are used to make further interpretations.The results indicated that (1)the quality of 18 items are not good enough; (2) The correlations among second-order latent traits are high (0.8,approximately); (3) Knowledge has the greatest influence on scientific literacy,Contexts second,and Competencies least; (4) Explain phenomena scientificall,procedural knowledge,and local/national has the greatest influence on Competencies, Knowledge,and Contexts,respectively. In addition,a simulation study was conducted to evaluate the psychometric properties of the proposed model.The results showed that the proposed Bayesian MCMC estimation algorithm can provide accurate model parameter estimation.

Overall,the proposed MO-DINA model works well in real data analysis and simulation study and meets the needs of assessment for PISA 2015 scientific literacy which included a third-order latent structure. Key Wordsscientific literacy; cognitive diagnosis; PISA; DINA model