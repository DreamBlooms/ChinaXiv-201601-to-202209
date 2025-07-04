# 纵向题目作答时间模型：对潜在加工速度的发展追踪

> 詹沛达\*\* 陈琦鹏（浙江师范大学教师教育学院，金华321004）

5摘要为实现对潜在加工速度发展的客观追踪，基于多元正态分布和潜在增长曲线提出了四个纵向  
6 题目作答时间(RT)模型。四个模型的测量模型一致，差异主要为描述潜在加工速度随时间变化的结构  
7 模型。实证研究结果表明四个模型均有实践可应用性，且它们的数据分析结果具有较高的一致性。模  
8 拟研究1表明四个模型在不同模拟条件下的参数估计返真性良好，且基于潜在增长曲线的纵向RT模型  
9 对潜在加工速度的估计精度略高于基于多元正态分布的纵向RT模型的。模拟研究2结果表明四个模型对中低比例 $( < 6 0 \% )$ 的随机缺失数据均具有一定的耐受性。总之，本文提出的四个纵向RT模型具有实践可应用性且心理计量学性能良好，不仅丰富了纵向RT数据的分析方法,还拓展了纵向模型的应用范围。

关键词题目作答时间；纵向数据；对数正态作答时间模型；潜在增长曲线；项目反应理论

# 1.引言

在心理与教育研究中，研究者通常对个体或群体在特定时间跨度中的认知或行为的发展变化感兴趣。这类研究的目标侧重于刻画每个个体的发展趋势和群体的平均变化轨迹。对潜在建构随时间发展的测量需要基于纵向研究设计对个体及其所在群体进行多次测量。相比于横断研究，纵向研究可以得到更有说服力的变量关系(e.g.，因果推论)论证(刘红云，孟庆茂,2003；刘源等,2022；温忠麟,2017)。目前，针对不同的观测变量类型和潜变量类型(连续或分类)研究者们提出了众多纵向数据分析模型，比如纵向Rasch/IRT模型(Andersen,1985; Embretson,1991; von Davier er al.,2011)、潜在增长曲线模型(Kaplan,2000)和潜在转换分析模型(Colins& Lanza,2010)等。近些年，随着测验情境复杂性的增加和对精准测量/追踪的追求，一些更复杂的纵向数据分析模型被提出，如增长混合模型(Muthen& Muthen,2000)、纵向诊断分类模型(Zhan et al.,2019)、深度知识追踪模型(Piech et al.,2015)和分段潜变量增长模型(Kohli& Harring,2013)等。尽管纵向模型本身并没有限制所分析的数据类型及所测量的潜在建构，但纵观已有研究可发现几乎所有纵向模型仅关注对传统题目作答结果(response accuracy,RA)数据(e.g.，答对答错或李克特式题目得分)的分析，忽略了其他模态数据，进而局限于追踪 RA 数据测量的心理建构(e.g.，潜在能力)的发展变化。

在智能时代背景下，随着计算机(网络)化测评的普及，除传统RA数据外，对诸如题目作答时间(response time,RT)等过程数据的采集已越发普遍(韩雨婷等,2022；刘耀辉等,2022)。在心理与教育测评中，RT数据作为一种RA数据的补充或平行数据1，描述了个体解决单一问题的总耗时，可用于分析个体解决问题时的潜在加工速度。这在一定程度上打破了传统心理测量中对速度测验和难度测验的功能划分。另外，因RT数据"具有标准化数据结构,符合心理计量模型的建模与分析要求"(詹沛达,2022,p2)，近些年受到了研究者们的广泛关注，开发了诸多RT模型(de Boeck&Jeon,2019；郭磊等,2017；詹沛达，2018)。比如对数正态RT 模型(lognormal RTmodel,LRTM) (van derLinden,2006; Klein Entink,Fox et al.,2009)、多维 LRTM(詹沛达等,2022)、Box-Cox 正态 RT模型(Klein Entink,van der Linden et al.,2009)、变速 LRTM(Fox & Marianti,2016)和一些关注速度-精度权衡的RT 模型(e.g.,Ferrando& Lorenzo-Seva,2007)。但纵观已有研究可发现几乎所有RT模型都仅适用于分析横断测评数据，即仅能分析被试在单一时间点测验中的潜在加工速度，无法追踪个体潜在加工速度的发展轨迹。

39 《深化新时代教育评价改革总体方案》(中共中央，国务院,2020)明确指出应“改进结果评价，强  
40 化过程评价，探索增值评价，健全综合评价，充分利用信息技术，提高教育评价的科学性、专业性、  
41 客观性。”近些年，随着学测融合(assessment as leaming)理念的普及，以学生为中心、以学习为中心的  
42 测评理念逐步得到认可，进而可提供及时反馈及干预的形成性学测项目逐渐受到人们的关注，如诊断  
43 性补救教学(王立君等,2020; Tang& Zhan,2021)、自适应学测系统(张华华，汪文义,2016; Zhang &  
44 Chang,2016)和智能导学系统(Woolf,2009)等。如图1所示，通常形成性学测项目会根据对个体在时间  
45 点 $p \left( p = 1 , . . . , P \right)$ 上RA数据的分析结果提供相应反馈和学习材料，然后在时间点 $p + 1$ 上对其再次测试,  
46 后再次提供反馈和学习材料，如此往复；最终，可以通过对多个时间点上RA数据(即纵向RA数据)的  
47 分析来刻画学生的发展轨迹(Chen et al.,2018;Wang,S.,Yang et al.,2018; Zhan,2020)。目前，随着计算  
48 机化测验的普及，一些形成性学测项目已经可以便捷地采集每个时间点上个体对每道题目的RT数据(即  
49 纵向 RT 数据)(e.g., Wang,S., Hu et al.,2020; Wang,S., Zhang et al.,2018)。Wang,S., Zhang 等人(2018)发  
50 现在自适应学测系统中，随着干预(反馈/学习)次数的增加，学生群体在下一个时间点上作答所有题目  
51 的平均RT会呈现下降趋势。Shi等人(2018)发现在阅读理解任务中借助智能导学系统能够在一定程度  
52 上降低被试的RT。而上述例子中导致观测变量RT降低的一个主要可能原因是被试的潜在加工速度随  
53 时间发生了增长。此时，如何合理分析纵向RT数据以实现对潜在加工速度发展的客观追踪，是一个兼  
54 具理论与实践意义的议题。

对此，Wang,S., Zhang et al.(2018)及Wang,S., Zhang 和 Shen (2019)提出了动态 RT 模型。该模型假设个体潜在加工速度的变化是由当前时间点上个体是否掌握题目所需属性或其他协变量导致；而这一定程度上会限制该模型的实践应用。首先，该模型需要在认知诊断测评中与RA数据分析模型联合使用,但实践中单独关注RT数据的分析也很常见(e.g.,Guo et al.,2021; van der Linden,2006;Wang,C.et al.,2013；詹沛达等,2020)，且非认知诊断测评也可常采集RT数据。其次，该模型假设但也同时约束了潜在加工速度的变化原因，对一些测验时间点间隔比较长的纵向研究而言，这可能导致一些其他因素(如,自然成长和知识迁移)的影响被忽视。另外，实践中并不是所有研究都采集了协变量，也不是所有研究都对协变量的影响感兴趣。因此，仍有必要建构一些应用约束较少、适用场景更宽泛的纵向RT模型。综上所述，已有的纵向数据分析模型主要聚焦对纵向RA 数据的分析，缺乏对纵向RT数据的关注;且已有的RT模型多限于分析横断测评数据，无法追踪学生潜在加工速度随时间的发展。对此，本研究拟基于两类常见的纵向数据分析方法(i.e.，多元正态分布建模和潜在增长曲线建模)对最具代表性的LRTM 进行拓展，提出四个纵向RT模型；以期实现对个体潜在加工速度发展的客观追踪并丰富纵向RT数据的分析方法。对此，下文将按如下逻辑撰写。首先，简单回顾横断LRTM，并基于此提出四个纵向RT模型。其次，通过对一则有关空间旋转能力的纵向RT数据的分析，呈现新模型的实践表现。然后，通过两则模拟研究来探究新模型的心理计量学性能。最后，总结研究结果并讨论研究局限和展望。

![](images/a68d160d0161bd948b9f3c5ddceb37a94e06a0efc4aba8d0177a9d9cc697c212.jpg)  
图1形成性学习/测评项目示意图

# 2.纵向题目作答时间模型

在心理计量模型中，纵向模型的一个核心作用是描述不同时间点上被试潜在建构的变化关系。根据描述方式的不同，通常可将纵向模型分类两类：一类是基于多元正态分布的纵向模型(e.g.,Andersen,1985;Embretson,1991; Paek,Li,&Park,2016; von Davier er al.,2011; Zhan et al.,2019)，另一类是基于潜在增长曲线的纵向模型(e.g.,Bollen & Curran,2006; Kaplan,2000; Paek,Li,&Park,2016; Wang, C.,&Nydick,2020)。前者类似于多维 IRT模型，直接利用多元正态分布对被试在各时间点上的潜在建构进行建模，并可利用均值向量描述不同时间点上群体的发展轨迹；后者通过构建潜在建构与测验时间点之间的线性或非线性回归函数来描述潜在建构随时间点增加的变化趋势。

基于上述两种建模逻辑，本文拟提出两类纵向RT模型，分别为基于多元正态分布的纵向RT模型和潜在增长曲线纵向RT模型。进一步，基于不同的模型假设，本文在每类模型中再分别提出两个模型(即共四个模型)。从结构方程模型视角看，上述两类模型的差异在于描述各时间点上潜在构建关系的结构模型，而非测量模型。因此，下文先介绍统一的测量模型，然后再结合不同的结构模型逐一阐述四个新模型。

# 2.1.模型建构

# 2.1.1.测量模型

针对横断RT 数据，LRTM是目前最常用的 RT 测量模型之一。设定 $T _ { n i }$ 为被试 $n \left( n = 1 , . . . , N \right)$ 对题

目 $i ( i = 1 , . . . , I )$ 的作答时间。则LRTM可表示为

$$
\log T _ { n i } = \xi _ { \mathrm { i } } - \phi _ { i } \tau _ { n } + \varepsilon _ { n i } , \ \varepsilon _ { n i } { \sim } N ( 0 , \omega _ { i } ^ { - 2 } ) ,
$$

或

$$
\begin{array} { r } { \log T _ { n i } { \sim } N ( \xi _ { i } - \phi _ { i } \tau _ { n } , \omega _ { i } ^ { - 2 } ) , } \end{array}
$$

其中， $\tau _ { n }$ 是被试 $n$ 的潜在加工速度； $\xi _ { i }$ 为题目时间强度参数，表示解答题目 $i$ 所必需的时间； $\displaystyle { \mathfrak { P } } i$ 为题目时间区分度参数，反映潜在加工速度对观察作答时间的影响程度； $\mathbf { \varepsilon } _ { \varepsilon _ { n i } }$ 为残差， $\boldsymbol { \wp } _ { i }$ 是残差的标准差的倒数，可以将其视为题目时间峰度参数。

对于纵向测评而言，当整个测验包含 $P$ 个测验时间点，则第 $p$ 个时间点上纵向LRTM的测量模型可表示为：

$$
\begin{array} { r } { \log T _ { n i p } { \sim } N ( \xi _ { i p } - \phi _ { i p } \tau _ { n p } , \omega _ { i p } ^ { - 2 } ) , } \end{array}
$$

其中， $T _ { n i p }$ 是时间点 $p$ 上被试 $n$ 对题目 $i$ 的作答时间； $\xi _ { i p } \lsetminus \ \varphi _ { i p }$ 和 $\displaystyle { \mathfrak { o } } i p$ 分别是时间点 $p$ 上题目 $i$ 的时间强度参数、时间区分度参数和时间峰度参数； $\tau _ { n p }$ 是时间点 $p$ 上被试 $n$ 的潜在加工速度。

# 2.1.2.基于多元正态分布的纵向题目作答时间模型

为描述 $P$ 个时间点上 $. \tau _ { n p }$ 之间的关系，一种最直接的方法是构建多元正态分布,如图1(a)。即假设 ${ \bf \ddot { \tau } } _ { \bf n } =$ $( \tau _ { n 1 } , . . . , \tau _ { n P } ) ^ { \mathrm { T } }$ 是遵循多元正态分布的多维潜在加工速度向量：

$$
\pmb { \tau } _ { n } \sim M V N ( \pmb { \mu } , \Sigma ) = M V N ( \binom { \mu _ { 1 } } { \updownarrow } , \pmb { \rho } , \pmb { \sigma } _ { \uparrow 1 } ^ { 2 } \quad \cdots \quad \rho _ { 1 P } \sigma _ { \tau 1 } \sigma _ { \tau P } ) ) ,
$$

式中， $\mathbf { \mu } = ( \mu _ { 1 } , . . . , \mu _ { P } ) ^ { \mathrm { T } }$ 为 $P$ 个时间点的潜在加工速度的均值向量； $\Sigma$ 为方差协方差矩阵，描述了 $P$ 个时间点的潜在加工速度之间的关系。该模型直接估计的各个时间点上的潜在加工速度，因此可直接使用 $\hat { \mathbf { { \tau } } } _ { n }$ 描述被试个体潜在加工速度的发展轨迹。此时，可以用 $\hat { \tau } _ { n ( p + 1 ) } - \hat { \tau } _ { n p }$ 描述相邻时间点个体水平的变化程度，用 $\widehat { \mu } _ { p + 1 } - \widehat { \mu } _ { p }$ 描述相邻时间点群体均值的变化程度。

实际上，该模型可视为多维LRTM(詹沛达等,2020)在纵向RT数据分析中的应用。因此，与多维LRTM一样，该模型中£的所有元素均需自由估计，即 $\Sigma$ 中有 $P ( P + 1 ) / 2$ 个待估计参数。该做法相对优点是考虑了所有时间点上潜在加工速度之间的相互影响，相对缺点是当时间点 $P$ 数量较多时参数估计计算量较大且易出现估计不收敛问题。

为缩减待估计参数数量，可通过引入马尔可夫性质(Markov property)来约束Σ中的待估计参数，如图1(b)。目前已有许多研究将马尔可夫性质引入纵向数据分析中(e.g.,de Haan-Rietdijk et al.,2017; Wang,S.,Yang al.,2018;Zhan,2020)。基于马尔可夫性质，可假设被试在时间点 $p$ 的潜在加工速度只与其在时间点 $p - 1$ 的潜在加工速度有直接关系。对此，首先将Σ做如下转换：

ChinaXiv预印本

$$
\Sigma = { \bf S } \Omega { \bf S } \mathrm { ~ , ~ }
$$

$$
\begin{array} { r } { \pmb { S } = \left( \begin{array} { c c c } { \sigma _ { \tau 1 } } & { \cdots } & { 0 } \\ { \vdots } & { \ddots } & { \vdots } \\ { 0 } & { \cdots } & { \sigma _ { \tau P } } \end{array} \right) , } \end{array}
$$

$$
\Omega = \left( \begin{array} { c c c c } { { 1 } } & { { \rho _ { 1 2 } } } & { { \cdots } } & { { \rho _ { 1 P } } } \\ { { \rho _ { 2 1 } } } & { { 1 } } & { { \cdots } } & { { \rho _ { 2 P } } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { \rho _ { P 1 } } } & { { \rho _ { P 2 } } } & { { \cdots } } & { { 1 } } \end{array} \right) ,
$$

24其中，S为标准差矩阵， $\Omega$ 为相关系数矩阵。然后，因只考虑相邻时间点之间的直接关系，所以只需将相关矩阵Ω中相邻时间点的相关系数 $\rho _ { ( p - 1 ) p }$ 作为待估参数；而跨时间点的相关系数不视为待估计参数，由各相邻时间点上的相关系数连乘而来：

$$
\rho _ { a b } = \rho _ { a ( a + 1 ) } \rho _ { ( a + 1 ) ( a + 2 ) } \ldots \rho _ { ( b - 2 ) ( b - 1 ) } \rho _ { ( b - 1 ) b } \ ,
$$

其中, $\rho _ { a b }$ 为两个不相邻的两个时间点 $\mathbf { \Delta } _ { a }$ 和 $b$ 之间的相关系数。比如，当相邻时间点之间的相关系数 $\rho _ { 1 2 } =$ 0.9, $\rho _ { 2 3 } = 0 . 7$ ， ${ \rho } _ { 3 4 } = 0 . 8$ 时，则有不相邻时间点之间的相关系数 $\rho _ { 1 3 } = \rho _ { 1 2 } \rho _ { 2 3 } = 0 . 9 \times 0 . 7 = 0 . 6 3$ ， $\rho _ { 1 4 } =$ $\rho _ { 1 2 } \rho _ { 2 3 } \rho _ { 3 4 } = 0 . 9 \times 0 . 7 \times 0 . 8 = 0 . 5 0 4$ ， $\rho _ { 2 4 } = \rho _ { 2 3 } \rho _ { 3 4 } = 0 . 7 \times 0 . 8 = 0 . 5 6$ 。此时， $\Sigma$ 中待估计参数数量由$P ( P + 1 ) / 2$ 缩减为 $2 P - 1$ 。

为便于阐述，下文将不包含马尔可夫性质的和包含马尔可夫性质的模型分别简称为MVN-LRTM 和MVN-LRTM-M。另外，在采用锚题设计和重复测量设计的情况下，可将第一时间点上所有被试的潜在加工速度的均值和方差分别约束为 $\mu _ { 1 } = 0$ 和 $\sigma _ { \tau 1 } ^ { 2 } = 1$ 以保证模型的可识别性(Paek,Li,&Park,2016)。

# 2.1.3.基于潜在增长曲线的纵向题目作答时间模型

为描述 $P$ 个时间点上 $\displaystyle \boldsymbol { \tau } _ { n p }$ 之间的关系,多元正态分布外的另一种方法是构建潜在增长曲线,如图1(c):

$$
\tau _ { n p } = \pi _ { 0 n } + \pi _ { 1 n } ( p - 1 ) + \varepsilon _ { n p } , \ \varepsilon _ { n p } \sim N \big ( 0 , \sigma _ { \varepsilon p } ^ { 2 } \big ) \ \textrm { . }
$$

$$
\binom { \pi _ { 0 n } } { \pi _ { 1 n } } \sim M V N \left( \binom { \mu _ { \pi _ { 0 } } } { \mu _ { \pi _ { 1 } } } , \binom { \sigma _ { \pi _ { 0 } } ^ { 2 } } { \rho _ { \pi _ { 1 } \pi _ { 0 } } \sigma _ { \pi _ { 1 } } \sigma _ { \pi _ { 0 } } } \right) \ ,
$$

式中， $\pi _ { 0 n }$ 为被试 $n$ 的截距系数，表示被试 $n$ 的初始潜在加工速度水平； $\pi _ { 1 n }$ 为被试 $n$ 的增长系数，表示被试 $n$ 的潜在加工速度随时间变化的程度； $\pi _ { 0 n }$ 和 $\pi _ { 1 n }$ 服从二元正态分布，两者的均值 $\mu _ { \pi _ { 0 } }$ 和 $\mu _ { \pi _ { 1 } }$ 分别代表群体潜在加工速度的均值和群体潜在加工速度的平均增长率，方差协方差矩阵则描述了潜在加工速度的初始水平和增长系数之间的关系： $\rho _ { \pi _ { 1 } \pi _ { 0 } } > 0$ 意味着初始水平越高的被试，其潜在加工速度随时间的增幅越大，反之则反； $\mathfrak { \varepsilon } _ { n p }$ 为残差。与MVN-LRTM不同，该模型没有直接估计各时间点上的 $\tau _ { n p }$ ，而是估计了每个被试的增长曲线系数(i.e., $\pi _ { 0 n }$ 和 $\pi _ { 1 n } )$ ；此时，可以用 $\widehat { \pmb { \pi } } _ { 1 n }$ 描述相邻时间点个体水平的变化

程度，用 $\hat { \mu } _ { \pi _ { 1 } }$ 描述相邻时间点群体均值的变化程度。

公式9假设 $\tau _ { n p }$ 随测验时间点的增加呈线性增长，而现实中 $\tau _ { n p }$ 随测验时间点的增加也可能呈非线性增长。此时，可在公式9中增加二次增长项来实现对潜在加工速度的非线性变化的描述，如图 1(d):

$$
\tau _ { n p } = \pi _ { 0 n } + \pi _ { 1 n } ( p - 1 ) + \pi _ { 2 n } ( p - 1 ) ^ { 2 } + \varepsilon _ { n p } , \ \varepsilon _ { n p } \sim N \big ( 0 , \sigma _ { \varepsilon p } ^ { 2 } \big ) \ ,
$$

$$
\binom { \pi _ { 0 n } } { \pi _ { 1 n } } \sim M V N \left( \left( \begin{array} { c c c c } { { \mu _ { \pi _ { 0 } } } } \\ { { \mu _ { \pi _ { 1 } } } } \\ { { \mu _ { \pi _ { 2 } n } } } \end{array} \right) , \left( \begin{array} { c c c c } { { \sigma _ { \pi _ { 0 } } ^ { 2 } } } & { { \rho _ { \pi _ { 0 } \pi _ { 1 } } \sigma _ { \pi _ { 0 } } \sigma _ { \pi _ { 1 } } } } & { { \rho _ { \pi _ { 0 } \pi _ { 2 } } \sigma _ { \pi _ { 0 } } \sigma _ { \pi _ { 2 } } } } \\ { { \rho _ { \pi _ { 1 } \pi _ { 0 } } \sigma _ { \pi _ { 1 } } \sigma _ { \pi _ { 0 } } } } & { { \sigma _ { \pi _ { 1 } } ^ { 2 } } } & { { \rho _ { \pi _ { 1 } \pi _ { 2 } } \sigma _ { \pi _ { 1 } } \sigma _ { \pi _ { 2 } } } } \\ { { \rho _ { \pi _ { 2 } \pi _ { 0 } } \sigma _ { \pi _ { 2 } } \sigma _ { \pi _ { 0 } } } } & { { \rho _ { \pi _ { 2 } \pi _ { 1 } } \sigma _ { \pi _ { 2 } } \sigma _ { \pi _ { 1 } } } } & { { \sigma _ { \pi _ { 2 } } ^ { 2 } } } \end{array} \right) \right) \ ,
$$

式中， $\pi _ { 2 n }$ 为被试 $n$ 的二次增长系数，其余参数同上。

实际上，这两个模型可视为变速LRTM(Fox&Marianti,2016)在纵向RT数据分析中的应用。当然，除包含二次增长项外，非线性增长模型中还可以进一步包含三次增长项或自由估计时间参数(Meredith& Tisak,1990;Paek,Li,&Park,2016)，但限于篇幅原因本文暂不关注它们。为便于阐述，下文将基于线性增长曲线和基于非线性增长曲线的模型分别称为LGC-LRTM-L 和 LGC-LRTM-N。另外，在采用锚题设计和重复测量设计的情况下，可将第一时间点上所有被试的潜在加工速度的均值和方差分别约束为 $\mu _ { \pi _ { 0 } } = 0$ 和 $\sigma _ { \pi _ { 0 } } ^ { 2 } + \sigma _ { \varepsilon 1 } ^ { 2 } = 1$ 以保证模型的可识别性(e.g.,Wang,C.,&Nydick,2020)。

![](images/4c3c7dcfb33b1de7c4c9b4e36aa672af7276ae91c0357d44676ef19481e44dd3.jpg)  
图1四个纵向题目作答时间模型示意图 $( P = 3 )$ ：

160注：虚线表示非相邻时间点之间的相关；“\*”表示该相关系数由相邻时间点相关系数连乘得到.

# 2.1.4.四个纵向题目作答时间模型的对比

表1呈现了本文所提出的四个纵向题目作答时间模型的对比(以 $P = 3$ 为例)。其中，当 $p = 1$ 时，有 $\tau _ { n 1 } = \pi _ { 0 n }$ 和 $\mu _ { 1 } = \mu _ { \pi 0 }$ ，即在起始点所有模型是完全等价的。其次，如上文所述，基于多元正态分布的两个模型和基于潜在增长曲线的两类模型在追踪学生发展时侧重点不同。具体而言，前者直接估计被试在各时间点上潜在加工速度的水平，并未直接关注潜在加工速度随时间的变化过程；而后者则估计被试潜在加工速度随时间的(线性或非线性)增长曲线系数，没有直接估计被试在各时间点上潜在加工速度的水平(可以计算出)。再次，对于纵向研究中可能出现的马太效应(e.g.,von Davior et al.,2011; Zhan et al.,2019)，即被试之间的差异会随时间而增大，两类模型的描述视角也不一样。具体而言，前者直接估计群体在各时间点上潜在加工速度的标准差，可根据@(p+1/g是否大于1来判断是否存在马太效应，$\sigma _ { \tau ( p + 1 ) } \ / _ { \sigma _ { \tau p } > 1 }$ 时存在马太效应， $\sigma _ { \tau ( p + 1 ) } \big / _ { \sigma _ { \tau p } } \approx 1$ 时则不存在；而后者可根据 $\rho _ { \pi _ { 1 } \pi _ { 0 } }$ 是否大于0米判断，$\rho _ { \pi _ { 1 } \pi _ { 0 } } > 0$ 则存在马太效应， $\rho _ { \pi _ { 1 } \pi _ { 0 } } \approx 0$ 时则不存在。需要强调的是MVN-LRTM-M和两个LGC-LRTM适用于 $P \ge 3$ 的测验情境；而当 $P = 2$ 时，直接使用MVN-LRTM即可。

表1.四个纵向题目作答时间模型的对比 $( P = 3 )$   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="4">个体水平</td><td colspan="2">群体水平</td></tr><tr><td>p=1</td><td>p=2</td><td>p=3</td><td>p=1</td><td>p=2</td><td>p=3</td></tr><tr><td>MVN-LRTM</td><td>Tn1</td><td>Tn2</td><td>Tn3</td><td>μ1</td><td>μ2</td><td>μ3</td></tr><tr><td>MVN-LRTM-M</td><td>Tn1</td><td>Tn2</td><td>Tn3</td><td>μ1</td><td>μ2</td><td>μ3</td></tr><tr><td>LGC-LRTM-L</td><td>TOn</td><td>πon+π1n</td><td>πon+2π1n</td><td>μπ0</td><td>μπo+μπ1</td><td>μπo+2μπ1</td></tr><tr><td>LGC-LRTM-N</td><td>Ton</td><td>πon+π1n+π2n</td><td>πon+2π1n+4π2n</td><td>μπ0</td><td>μπo+μπ1+μπ2</td><td>μπo+2μπ1+4μπ2</td></tr></table></body></html>

# 2.2.参数估计

本研究使用全贝叶斯马尔可夫链蒙特卡洛(MCMC)算法对四个纵向RT模型进行参数估计，并基于JAGS (Ver 4.3.0) (Plummer,2015)实现。相应的 JAGS 示例代码见 ttp:/.。根据已有数据分析经验以及已有研究结果(詹沛达等,2020;Fox&Marianti,2016;Wang,S.,Zhang et al.,2018)，本文选取了特定的先验分布。网络版附录 S1章节中呈现了模型参数估计对高、中和低信息先验分布的稳健性分析结果，结果表明四个新模型对包含不同信息量的先验分布均具有较高的稳健性。关于如何使用 JAGS 进行贝叶斯 MCMC 参数估计，可参阅 Curtis (2010)及 Zhan,Jiao,Man 和 Wang (2019)。

ChinaXiv预印本

# 3.实证数据分析

# 3.1.数据描述与分析

本研究以一则有关空间旋转能力的自适应学测数据(Wang,S.,Yang et al.,2018)为例来展现所提出模型的实践可应用性。该数据集包含350名被试在5个时间点上对 50道题目(即每个时间点10道题目)的作答数据。具体而言，为平衡题目位置效应，该测验采用拉丁方设计(见表2)，测验总共包含5个组块，每个组块包含10题(共 50题)，并根据施测顺序形成5个版本的测验。在每个时间点施测时，每位学生随机抽取其中1个版本的测验。该数据已经被一些研究用于探究学生的学习轨迹(Chen etal.,2018;Wang,S.,Yang et al.,2018;Wang,S.,Zhang et al.,2019)。本研究拟分析该数据集中的RT数据来追踪被试潜在加工速度的发展。

实际上，该测验本质是一个采用了重复测量设计的纵向测验，只不过每名被试由于施测设计导致其在每个时间点上只作答了10道题目(1个组块),缺失另外40道题目(i.e.，设计缺失[missing by design])。因此，可将该数据重新整理为350人在5个时间点上共250 道题目(每个时间点50题)上的纵向数据；其中，由设计缺失导致的缺失数据被视为完全随机缺失。图2呈现了50道题目的对数RT随时间变化趋势(剔除缺失值)，可发现明显的下降趋势。

分别使用 MVN-LRTM、MVN-LRTM-M、LGC-LRTM-L 和 LGC-LRTM-N 作为数据分析模型。四个模型均使用两条马尔可夫链，均预热10,000次，采样 5,000次。使用潜在量尺缩减因子(PSRF;Brooks&Gelman,1998）对作为MCMC算法的收敛指标，通常 $\mathrm { P S R F } < 1 . 1$ 或1.2表示参数估计已收敛。使用后验预测模型检验(posterior predictive model checking,PPMC)来评估模型-数据绝对拟合，其中后验预测概率(posterior predictive probability,ppp)接近0.5表明模型与数据拟合。本研究使用测验统计量(teststatistics)(即仅关注真实数据与预测数据之间的差异，不涉及具体模型参数)(Levy&Mislevy,2016)作为PPMC的差异测度。使用-2LL( $- 2 \times$ log likelihood)和 DIC (deviance information criterion) (Spiegelhalter etal.,2002)作为模型-数据相对拟合指标，指标值越小说明模型和数据拟合的越好。前者不包含模型复杂性惩罚，单纯反映模型与数据的拟合情况；而后者包含模型复杂性惩罚，在反映模型与数据拟合情况的同时还考虑了实践应用中的简约原则(parsimony principle)(Beck,1943).

表2.实证研究的拉丁方设计.  

<html><body><table><tr><td rowspan="2">测验版本</td><td colspan="5">测验顺序(P= 5)</td></tr><tr><td>p=1</td><td>p=2</td><td>p=3</td><td>p=4</td><td>p=5</td></tr><tr><td>版本1</td><td>组块1</td><td>组块2</td><td>组块3</td><td>组块4</td><td>组块5</td></tr><tr><td>版本2</td><td>组块2</td><td>组块3</td><td>组块4</td><td>组块5</td><td>组块1</td></tr><tr><td>版本3</td><td>组块3</td><td>组块4</td><td>组块5</td><td>组块1</td><td>组块2</td></tr></table></body></html>

3 该设定下MVN-LRTM中潜在加工速度的方差协方差矩阵中部分元素未达到收敛标准(PSRF $< 1 . 2 \dot { }$ ，随后将每条链迭代次数增加至100,000次(预热90,000)，这些参数仍未完全达到收敛标准；其余参数均达到收敛标准。

<html><body><table><tr><td>版本4</td><td>组块4</td><td>组块5</td><td>组块1</td><td>组块2</td><td>组块3</td></tr><tr><td>版本5</td><td>组块5</td><td>组块1</td><td>组块2</td><td>组块3</td><td>组块4</td></tr></table></body></html>

![](images/7dedd45547899857a75f0a49e9c8d49fddd9188095145d5e29b4d72c117ce95c.jpg)  
图2实证研究5个时间点上50道题目的对数题目作答时间分布.

# 3.2.结果

需要强调的是，由于MVN-LRTM中潜在加工速度的方差协方差矩阵中部分元素没有达到收敛标准 $( \mathrm { P S R F } < 1 . 2 )$ ，所以该模型与数据的拟合结果仅供参考(其余参数均达到收敛标准)；可能的原因是五元正态分布较难实现稳健的参数估计(e.g.,Cai,2010)，且该数据中样本量较小还包含较大比例的缺失值。其他三个模型的所有模型参数均达到收敛标准。

表3呈现了四个模型对实证数据的拟合情况。首先，根据各时间点上的ppp 值，表明四个模型均拟合该数据。其次，不考虑MVN-LRTM时，剩余三个模型的对数据的相对拟合比较接近。其中，-2LL指标值表明，在不考虑模型复杂性惩罚的前提下，LGC-LRTM-N对该数据的拟合相对最好，即该模型得到的参数估计值相对最能反映数据的特征。而DIC 指标值表明MVN-LRTM-M对该数据拟合相对最好,LGC-LRTM-L次之且和 LGC-LRTM-N几乎没有差异。总之,在简约原则下推荐使用 MVN-LRTM-M分析该数据；但单纯从反映数据本身特征的角度看，LGC-LRTM-N 的拟合最好。

图3呈现了四个模型中所有被试潜在加工速度随时间的变化趋势(含群体均值变化)。首先，对任何模型而言，潜在加工速度的群体均值都呈较明显的增长趋势。具体而言，MVN-LRTM 的潜在加工速度均值向量 ${ \pmb { \mu } } =$ (0,0.297,0.728,0.996,1.384)T，MVN-LRTM-M的潜在加工速度均值向量 $\mu = ( 0 , 0 . 3 1 1$

0.757,1.030,1.393)T，LGC-LRTM-L的潜在加工速度均值向量 $\pmb { \mu } = ( 0 , 0 . 4 3 3 , 0 . 8 6 6 , 1 . 2 9 9 , 1 . 7 3 2 ) ^ { \mathrm { T } }$ LGC-LRTM-N 的潜在加工速度均值向量 $\mathbf { \ddot { \mu } } \mathbf { \Phi } \mathbf { \Phi } \cdot \mathbf { \Phi } \mathbf { \Phi } \mathbf { \Phi } ( 0 , 0 . 4 8 3 , 0 . 9 5 5 , 1 . 4 1 6 , 1 . 8 6 7 ) ^ { \mathrm { T } }$ 。其次，同一类增长模型的变化趋势更接近，不同类模型之间的略有差异：两个LGM-LRTM对各时间点上群体均值的估计值大于两个MVN-LRTM对各时间点上群体均值的估计值。总之，被试潜在加工速度随时间增长的趋势可以较好地解释图2中RT 随时间的下降趋势。

图4呈现了四个模型中所有时间点上潜在加工速度的估计值之间的相关系数图。可以看到，无论是同一模型对5个时间点上潜在加工速度的估计值之间，还是不同模型对同一时间点上潜在加工速度的估计值之间，均呈现高程度相关。一方面表明不同模型的估计值之间具有高度一致性，另一方面表明不同时间点上潜在加工速度之间也具有高度一致性(主要原因是该测验中各时间点之间的间隔较短)。

图5呈现了四个模型的题目参数估计值。因为该测验采用重复测量设计，所以仅有50道题目的题目参数。首先，四个模型的题目参数估计值之间具有较高的一致性，尤其是时间强度参数和时间峰度参数。其次，同一类模型的时间区分度参数估计值相对更接近。由于LRTM中时间区分度参数与潜在加工速度之间存在交互，导致两类模型的时间区分度参数估计值之间存在细微差异的可能原因是两类模型对潜在加工速度估计值存在细微差异性。具体而言，因为LGC-LRTM对潜在加工速度的估计值略大于MVN-LRTM的，所以LGC-LRTM对时间区分度参数的估计值略小于MVN-LRTM的。

此外，MVN-LRTM 和 MVN-LRTM-M可以计算潜在加工速度随时间进展的量尺变化(i.e.,$\sigma _ { \tau ( p + 1 ) } / _ { \sigma _ { \tau p } } )$ ，见表4。可发现，在该测验中被试不存在马太效应，且被试之间的差异随时间进展还略微减小。另外，LGC-LRTM-L 中 $\hat { \rho } _ { \pi _ { 1 } \pi _ { 0 } } = - 0 . 0 5 1$ (i.e.，被试增长系数与初始值成极弱负相关)也印证了该结论。

综上所述，实证研究结果表明四个纵向RT模型均具有实践可应用性且对同一批数据的分析结果具有较高的一致性。当然，由于实证数据分析主要用于呈现新模型的实践可应用性，其他一些数据本身相关的结论(e.g.，导致发展的原因)不再探讨。

表3.实证研究中模型-数据拟合结果  

<html><body><table><tr><td>模型</td><td>-2LL</td><td>DIC</td><td>ppp_1</td><td>ppp_2</td><td>ppp_3</td><td>ppp_4</td><td>ppp_5</td></tr><tr><td>MVN-LRTM</td><td>39123.936</td><td>39703.615</td><td>0.381</td><td>0.445</td><td>0.526</td><td>0.593</td><td>0.592</td></tr><tr><td>MVN-LRTM-M</td><td>39094.366</td><td>39872.355</td><td>0.419</td><td>0.457</td><td>0.489</td><td>0.556</td><td>0.600</td></tr><tr><td>LGC-LRTM-L</td><td>39056.191</td><td>39965.569</td><td>0.463</td><td>0.378</td><td>0.632</td><td>0.496</td><td>0.576</td></tr><tr><td>LGC-LRTM-N</td><td>39051.008</td><td>39967.630</td><td>0.455</td><td>0.341</td><td>0.634</td><td>0.506</td><td>0.605</td></tr></table></body></html>

注:MVN-LRTM的方差协方差矩阵中部分元素估计未收敛，结果仅供参考.

![](images/9cba4095fc0a14c3ae1163cdf26741c55b3e8d40e16c23384cebf22205e7f0f0.jpg)  
图3．实证研究中潜在加工速度随时间的变化趋势.

注：红线为群体均值变化.

![](images/f21de804a49f3ac2b4531e4ce29c0bb15f06d188a42c3264d93b4cf710a41a13.jpg)  
图4．实证研究中所有模型对所有时间点上潜在加工速度的估计值之间的相关系数图.注:M1 $\mathbf { \Sigma } = \mathbf { \Sigma }$ MVN-LRTM; $\mathbf { M } 2 =$ MVN-LRTM-M;M3 $\mathbf { \Sigma } = \mathbf { \Sigma }$ LGC-LRTM-L; M4 $\mathbf { \Sigma } = \mathbf { \Sigma }$ LGC-LRTM-N；下三角区域包含平滑拟合曲线和置信椭圆，上三角区域包含散点图.

![](images/6b25b9386bbf548a069deece58571f48ef75abbdac9ec9fd2b101ddb4a41a747.jpg)  
图5．实证研究中所有模型的题目参数估计值.

6注: $\mathbf { M } \mathbf { l } = \mathbf { M } \mathbf { V } \mathbf { N }$ -LRTM; $\mathbf { M } 2 =$ MVN-LRTM-M; $\mathbf { M } 3 =$ LGC-LRTM-L; M4 $\mathbf { \Sigma } = \mathbf { \Sigma }$ LGC-LRTM-N.

表4.实证研究中潜在加工速度随时间进展的量尺变化  

<html><body><table><tr><td>模型</td><td>Ot2/0t1</td><td>Ot3/0t2</td><td>0t4/0t3</td><td>0t5/0t4</td></tr><tr><td>MVN-LRTM</td><td>0.933</td><td>1.096</td><td>0.948</td><td>0.925</td></tr><tr><td>MVN-LRTM-M</td><td>0.887</td><td>1.131</td><td>0.910</td><td>0.981</td></tr></table></body></html>

注:MVN-LRTM的方差协方差矩阵中部分元素估计未收敛，结果仅供参考.

# 4.模拟研究

实证数据分析表明新模型具有实践可应用性，下文通过两则模拟研究进一步探究四个模型的心理计量学性能。模拟研究1主要探究四个模型在不同模拟条件下的参数估计返真性；模拟研究2主要探究四个模型对数据缺失比例的耐受性。

# 4.1.研究1：参数返真性

# 4.1.1.研究设计与数据生成

研究1中测验时间点数量固定为 $P = 5$ ，另外包含4个操纵变量，分别是样本量 $N = 1 0 0$ 和300,每个时间点测验长度 $I _ { p } = 1 5$ 和30，相邻时间点潜在加工速度的均值增幅 $\Delta \mu = 0 . 2 5$ 和0.5，以及各时间点潜在加工速度的方差 $\begin{array} { r } { \pmb { \sigma } _ { \tau } ^ { 2 } = } \end{array}$ 无变化 $( 1 , 1 , 1 , 1 , 1 ) ^ { \mathrm { T } }$ 、线性变化(1,1.25,1.5,1.75,2)T和非线性变化(1,1.1,1.3, 1.6,2)T。

如图6所示，采用锚题设计，设定时间点 $p$ 的后 $20 \%$ 题目(i.e., $I _ { p } = 1 5$ 时3题， $I _ { p } = 3 0$ 时6题)和时间点 $p + 1$ 的前 $20 \%$ 题目为相同锚题(i.e.，共4组锚题)。参考相关研究(Fox&Marianti,2016；詹沛达等,2020)，各题目参数按如下分布生成： $\xi _ { i p } { \sim } N ( { \mu } _ { \xi } , \sigma _ { \xi } ^ { 2 } ) = N ( 4 , 0 . 2 5 )$ ， $\Phi _ { i p } { \sim } N ( \mu _ { \phi } , \sigma _ { \phi } ^ { 2 } ) = N ( 1 , 0 . 0 5 )$ 和$\omega _ { i p } { \sim } N ( \mu _ { \omega } , \sigma _ { \omega } ^ { 2 } ) = N ( 2 , 0 . 0 5 )$ 。5 个时间点的题目参数生成后，对于相同锚题而言，再将时间点 $p + 1$ 上锚题的题目参数固定为时间点 $p$ 上锚题的题目参数，如 $\xi _ { i p } \Rightarrow \xi _ { i ( p + 1 ) }$ 。潜在加工速度依多元正态分布生成，各时间点上潜在加工速度的均值和标准差依不同模拟条件而定，各时间点上潜在加工速度之间的相关系数固定为0.9。

最后，基于各生成数据，依据公式3生成各时间点上的观测RT。每个模拟条件均生成 50组数据。

<html><body><table><tr><td>p=1</td><td></td><td></td><td>23</td><td>4</td><td>5</td><td>6</td><td>7</td><td></td><td>8</td><td>9</td><td>10</td><td>12</td><td></td><td>:13:::14:15</td><td></td><td></td></tr><tr><td>p=2</td><td></td><td>88188882818238</td><td></td><td>4</td><td></td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11 11</td><td>12</td><td></td><td>131415</td><td></td></tr><tr><td>p=3</td><td></td><td></td><td>3</td><td>4</td><td>5</td><td></td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td></td><td>3115</td><td></td></tr><tr><td>p=4</td><td></td><td></td><td></td><td>4</td><td>5</td><td></td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td></td><td>1W</td><td></td></tr><tr><td>p=5</td><td></td><td></td><td></td><td>4</td><td>5</td><td></td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td></tr></table></body></html>

注：相同颜色方框表示相同组锚题，

# 4.1.2.分析

在不同模拟条件下分别使用模型MVN-LRTM、MVN-LRTM-M、LGC-LRTM-L 和LGC-LRTM-N作为数据分析模型；数据分析过程与实证数据部分保持一致(e.g.，两条马尔可夫链，每条链含10000 次

迭代，其中预热 5000 次)。采用均方根误差 RMSE 评估参数估计返真性： $\begin{array} { r } { \mathrm { R M S E } ( \hat { { \boldsymbol x } } ) = \sqrt { \sum _ { r = 1 } ^ { R } \left( \hat { x } _ { r } - x _ { r } \right) ^ { 2 } / } \overset { \quad } { R } } \end{array}$ ，其中，$x _ { r }$ 和 $\hat { x } _ { r }$ 分别第 $r \left( r = 1 , 2 , . . . , R = 5 0 \right)$ 组数据中某单一参数的真值和估计值。

# 4.1.3.结果

表5呈现了MVN-LRTM-M和LGC-LRTM-L 两模型中各模型参数的均方根误差(限于篇幅原因，四个模型的完整结果汇总详见 htps://docs.qq.com/sheet/DTUJoVEhDUG1LSkpR)。在阐述结果之前需说明的是，同一类模型受操作变量水平变化的影响趋势是一致的，正文仅以 MVN-LRTM-M 和LGC-LRTM-L 进行阐述；另外，操作变量的水平变化对两类模型的影响存在差异。具体结果如下：第一，当样本量增加时，MVN-LRTM-M 的潜在加工速度均值的RMSE 减小，而 LGC-LRTM-L 的增大;两模型的潜在加工速度的RMSE 均减小，三个题目参数的RMSE 均减小。第二，当题目数量增加时，MVN-LRTM-M的潜在加工速度均值的RMSE 增大，而 LGC-LRTM-L 的减小；两模型的潜在加工速度的RMSE均增大，题目时间强度参数的RMSE略减小，题目时间区分度参数增加。第三，当潜在加工速度的均值增幅 $\Delta \mu$ 增加时，两模型的潜在加工速度均值的RMSE 均增大，潜在加工速度的RMSE 均增大，三个题目参数几乎不受影响。第四，不同方差变化类型对两模型中各参数的影响均较小；但对潜在加工速度而言，似乎方差无变化时的RMSE 最小。第五，LGC-LRTM-L 对潜在加工速度和潜在加工速度均值的RMSE 普遍小于MVN-LRTM-M的;且前者的时间区分度参数的RMSE 也普遍小于后者的;第六，随着时间发展(i.e., $p = 1  p = 5$ )，MVN-LRTM-M的潜在加工速度均值的RMSE 增大，而LGC-LRTM-L 的减小；两模型的潜在加工速度的 RMES 均增大，两模型的题目时间峰度参数均增大，其余参数几乎不受影响。整体而言，模拟研究1结果表明四个模型在多种模拟条件下的参数估计返真性良好，且两个LGC-LRTM对潜在加工速度的估计精度略高于两个MVN-LRTM的。

15表5.模拟研究1中各模型参数的均方根误差汇总(仅呈现LGC-LRTM-L 和 MVN-LRTM-M).  

<html><body><table><tr><td colspan="2">模型 N</td><td rowspan="2">△μ</td><td rowspan="2">方差变化</td><td rowspan="2"></td><td rowspan="2">T</td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2">@</td></tr><tr><td></td><td>线性</td></tr><tr><td rowspan="4"></td><td></td><td>0.25</td><td>无</td><td>0.119 0.112</td><td>0.256 0.227</td><td>0.073 0.069</td><td>0.261 0.270</td><td>0.172</td></tr><tr><td rowspan="3">15</td><td></td><td>非线性</td><td>0.120</td><td>0.246</td><td>0.071</td><td></td><td>0.176</td></tr><tr><td></td><td>线性</td><td>0.229</td><td>0.317</td><td>0.082</td><td>0.262 0.275</td><td>0.168 0.173</td></tr><tr><td>0.5</td><td>无</td><td></td><td></td><td>0.089</td><td></td><td></td></tr><tr><td rowspan="12"></td><td></td><td></td><td>非线性</td><td>0.220 0.245</td><td>0.298</td><td></td><td>0.269</td><td>0.172</td></tr><tr><td rowspan="3">100</td><td></td><td>线性</td><td>0.141</td><td>0.323 0.290</td><td>0.078 0.060</td><td>0.287 0.355</td><td>0.172 0.166</td></tr><tr><td rowspan="2">0.25</td><td></td><td>0.131</td><td>0.260</td><td>0.060</td><td>0.361</td><td>0.167</td></tr><tr><td>无 非线性</td><td>0.146</td><td>0.293</td><td>0.057</td><td>0.365</td><td>0.168</td></tr><tr><td rowspan="4">30</td><td rowspan="2">0.5</td><td>线性</td><td>0.282</td><td>0.380</td><td>0.069</td><td>0.373</td><td>0.172</td></tr><tr><td>无</td><td>0.276</td><td>0.362</td><td>0.074</td><td>0.375</td><td>0.170</td></tr><tr><td rowspan="2"></td><td>非线性</td><td>0.285</td><td>0.375</td><td>0.063</td><td>0.368</td><td>0.166</td></tr><tr><td></td><td>0.055</td><td>0.152</td><td>0.049</td><td>0.108</td><td>0.131</td></tr><tr><td rowspan="10">15</td><td rowspan="3">0.25</td><td rowspan="3"></td><td>线性</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>无</td><td>0.061</td><td>0.150</td><td>0.059</td><td>0.129 0.117</td><td>0.134</td></tr><tr><td>非线性 线性</td><td>0.059 0.106</td><td>0.156</td><td>0.056</td><td>0.114</td><td>0.135 0.137</td></tr><tr><td rowspan="3">0.5</td><td>无</td><td>0.119</td><td>0.179 0.187</td><td>0.054 0.058</td><td>0.134</td><td></td></tr><tr><td></td><td>非线性</td><td>0.125</td><td></td><td></td><td>0.140</td><td>0.140 0.131</td></tr><tr><td rowspan="3"></td><td>线性</td><td>0.081</td><td>0.201 0.193</td><td>0.053 0.044</td><td>0.195</td><td>0.134</td></tr><tr><td rowspan="3">0.25</td><td>无</td><td>0.085</td><td>0.178</td><td>0.046</td><td>0.205</td><td>0.135</td></tr><tr><td>非线性</td><td>0.086</td><td>0.191</td><td>0.044</td><td>0.195</td><td>0.133</td></tr><tr><td>线性</td><td>0.165</td><td>0.230</td><td>0.046</td><td>0.196</td><td>0.136</td></tr><tr><td rowspan="12">15 100</td><td></td><td>0.5</td><td>无</td><td>0.162</td><td>0.226</td><td>0.047</td><td>0.198 0.139</td></tr><tr><td rowspan="3"></td><td></td><td>非线性</td><td>0.167 0.229</td><td>0.048</td><td></td><td>0.194 0.134</td></tr><tr><td>0.25</td><td>线性</td><td>0.070 0.143</td><td></td><td>0.076</td><td>0.080</td><td>0.172</td></tr><tr><td>无 非线性</td><td></td><td>0.040</td><td>0.119</td><td>0.071</td><td>0.060</td><td>0.176</td></tr><tr><td rowspan="3"></td><td></td><td>0.059</td><td>0.128</td><td>0.071</td><td>0.062</td><td>0.168</td></tr><tr><td rowspan="2">0.5</td><td></td><td>0.081</td><td>0.152</td><td>0.096</td><td>0.078</td><td>0.173</td></tr><tr><td>线性</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="4">30</td><td rowspan="2">0.25</td><td>非线性</td><td>0.081</td><td>0.149</td><td>0.078</td><td>0.074</td><td>0.172</td></tr><tr><td>线性</td><td>0.087</td><td>0.192</td><td>0.062</td><td>0.195</td><td>0.166</td></tr><tr><td rowspan="3"></td><td>无</td><td>0.058</td><td>0.140</td><td>0.060</td><td>0.139</td><td>0.167</td></tr><tr><td>非线性</td><td>0.085</td><td>0.182</td><td>0.055</td><td>0.183</td><td>0.168</td></tr><tr><td>线性</td><td>0.172</td><td>0.24</td><td>0.073</td><td></td><td></td></tr><tr><td rowspan="10">LGC-LRTM-L 300</td><td rowspan="3">0.5</td><td></td><td></td><td></td><td></td><td>0.148</td><td>0.172</td></tr><tr><td>非线性</td><td>0.151</td><td>0.215</td><td>0.064</td><td>0.171</td><td>0.166</td></tr><tr><td>线性</td><td>0.038</td><td>0.126</td><td>0.048</td><td>0.065</td><td>0.131</td></tr><tr><td>0.25</td><td>无</td><td>0.029</td><td>0.116</td><td>0.058</td><td>0.050</td><td>0.134</td></tr><tr><td rowspan="2">15</td><td>非线性</td><td>0.038</td><td>0.121</td><td>0.056</td><td>0.049</td><td>0.135</td></tr><tr><td>线性</td><td>0.062</td><td>0.135</td><td>0.055</td><td>0.062</td><td>0.136</td></tr><tr><td rowspan="3"></td><td>0.5</td><td>0.045</td><td>0.120</td><td>0.062</td><td>0.046</td><td>0.141</td></tr><tr><td>无 非线性</td><td>0.051</td><td>0.127</td><td>0.052</td><td>0.053</td><td>0.131</td></tr><tr><td>线性</td><td>0.060</td><td>0.154</td><td>0.047</td><td>0.139</td><td>0.134</td></tr><tr><td rowspan="3">0.25</td><td>无</td><td>0.045 0.058</td><td>0.118 0.138</td><td>0.044 0.047</td><td>0.105 0.115</td><td>0.135 0.133</td></tr><tr><td>非线性</td></table></body></html>

注：所有数值均为5个时间点上的均值.

# 4.2.研究2：缺失值影响

# 4.2.1.研究设计、数据生成与分析

实证数据中被试在每个时间点上的RT有较大比例 $( 8 0 \% )$ 的缺失，尽管这是设计缺失，但我们仍想了解新模型对缺失数据的耐受性。因此，研究2拟探讨不同数据缺失比例对四个模型的参数估计精度的影响。本研究聚焦于1个操作变量，即被试在每个时间点上RT 的缺失值比例 $M S = 0 \%$ 、 $20 \%$ 、 $40 \%$ 、$60 \%$ 和 $80 \%$ 。为使研究2的结果更具实践意义，其他变量参考实证研究设定： $P = 5$ 、 $N = 3 5 0$ 、 $I _ { p } = 5 0$ （对应MS各水平，分别缺失0、10、20、30和40 题)、 $\Delta \mu = 0 . 5$ 和 $\pmb { \sigma } _ { \tau } ^ { 2 } = ( 1 , 1 , 1 , 1 , 1 )$ 。采用与实证研究一致的重复测量设计,50道题目的参数和350 名被试的潜在加工速度完全按照实证数据中的估计值设定。在不考虑参数估计惩罚时，LGC-LRTM-N对数据的拟合相对最好(i.e.,-2LL 最小)，因此，我们将LGC-LRTM-N在实证研究中得到的题目参数估计值和被试参数估计值视为模拟研究2中的相应参数的真值。依据公式3生成各时间点上的观测RT，每个模拟条件均生成50 组数据。

图7显示了每种缺失值比例条件下，50组生成中所有被试在每道题目(共250题)上的平均对数 RT和实证数据中每道题目上的平均对数RT之间的Lowess 平滑拟合曲线(局部加权多项式回归曲线)(Cleveland,1981)。每种条件下的 50条Lowess 平滑拟合曲线均趋近于对角线(i.e.,，两组数据之间具有高线性相关)，表明每种条件下的 50组生成数据均能很好地代表实证数据(i.e.,，对数据缺失的操纵没有对数据其他特征[e.g.，群体均值和方差]产生影响)。

分别使用模型 MVN-LRTM、MVN-LRTM-M、LGC-LRTM-L 和 LGC-LRTM-N 分析数据。数据分析过程及参数估计返真性指标与实证研究和模拟研究1中保持一致。

![](images/4c2fac9b3715b13699358884bed9138be1c3671395cbdc9f7c3fab0a96d8373e.jpg)  
图7．模拟研究2五种缺失比例下生成数据与实证数据之间的平滑拟合曲线.

# 4.2.2.结果

图8呈现了研究2中各时间点潜在加工速度的和题目参数的估计返真结果。首先，随缺失比例增加四个模型的估计返真性均呈现下降趋势(i.e.,RMSE 增大)。其次，缺失比例增加对被试参数返真性的影响大于对题目参数返真性的影响。再有，当缺失比例由 $6 0 \%  8 0 \%$ 时，各返真性指标会出现一个较大幅度的变化；因此，推荐在实践应用中将完全随机缺失比例控制在 $60 \%$ 以下。最后，结合模拟研究2结果，回顾实证研究结果，需要意识到实证研究结果中对被试潜在加工速度的发展轨迹描述可能存在一定的偏差。

ChinaXiv预印本

![](images/08abaf9c8ad215105b290ec1b3980ca4f8d2a74d52d6ba593d04237d979d2a4a.jpg)  
图8.模拟研究2被试参数的和题目参数的均方根误差

# 5.总结与讨论

为实现对个体潜在加工速度发展的客观追踪，本文基于多元正态分布和潜在增长曲线提出了四个纵向RT模型，分别为MVN-LRTM、MVN-LRTM-M、LGC-LRTM-L 和 LGC-LRTM-N。四个模型的测量模型一致，差异主要体现在描述潜在加工速度如何随时间变化的结构模型上。具体而言，前两个模型直接估计各时间点上的潜在加工速度，未直接关注变化的过程；相反，后两个模型直接估计潜在加工速度随时间的变化(增长)系数，没有直接估计各时间点上的潜在加工速度。实证研究结果表明四个模型均有实践可应用性，且它们的数据分析结果具有较高的一致性。模拟研究1表明四个模型在不同模拟条件下的参数估计返真性良好，且两个LGC-LRTM对潜在加工速度的估计精度略高于两个MVN-LRTM的。模拟研究2结果表明四个模型对不同比例的随机RT缺失均具有一定的耐受性，建议在实践应用中将完全随机缺失比例控制在 $60 \%$ 以下。总之，本文提出的四个纵向RT模型具有实践可应用性，且心理计量学性能良好，不仅丰富了心理与教育测量中纵向RT数据的分析方法，也拓展了纵向潜变量模型的应用范围。

但限于精力和能力，本文也有一些局限性有待未来研究做进一步探讨。第一，尽管本文一次性提出了四个纵向RT模型，但鉴于纵向数据分析的快速发展，目前还有诸如增长混合建模和多水平增长建模等多种纵向建模方法。未来可尝试在纵向RT数据分析中引入更多的纵向建模方法，以期进一步丰富纵向RT数据的分析方法。

第二，模拟研究涉及的条件有限，未来可尝试探究更多操纵变量(e.g.，更多更密集的时间点、不同锚题设计)或已涉及变量的更多水平(e.g，更大样本量)对新模型表现的影响，以期为新模型的实践应用提供更多的理论指导。

第三，本文仅关注单维潜在加工速度随时间的变化，随着测评情境复杂性日益增加，如何追踪多维潜在加工速度(詹沛达等,2020)随时间的变化也值得关注和探究。

第四，模拟研究2仅关注了完全随机缺失RT数据对参数估计返真性的影响，并没有进一步探讨其他类型缺失数据(e.g.，非随机缺失)的影响，也没有关注不同缺失数据插补法的表现(e.g.，陈楠，刘红云,2015)；同时，模拟研究2中不存在由样本流失导致的缺失数据。而纵向研究中样本流失是一种常见现象，未来可探讨该类型缺失数据对新模型参数估计的影响。

第五，为增加模型的普适性，本文没有考虑协变量对潜在加工速度发展的影响。如有需求，未来也可考虑在四个纵向RT模型中引入协变量参数，以探究不同协变量对被试潜在加工速度发展的影响。

第六，本研究采用了贝叶斯 MCMC 算法。在贝叶斯参数估计值中，先验分布的选择反映了数据分析者对模型参数的已有经验或信念。根据已有数据分析经验以及已有研究结果(詹沛达等,2020;Fox&Marianti,2016;Wang,S.,Zhang et al.,2018)，本文选取了特定的先验分布。尽管稳健性分析结果表明新模型的模型参数估计受不同先验分布的影响不大，但这并不意味着本文所用的先验分布适用于所有测验情境。在后续实践中，数据分析者可尝试使用其他先验分布或超先验分布来探索恰当的先验分布。另外，实践者也可尝试使用诸如Mplus 等其他软件实现参数估计。

# 参考文献

Andersen,E.B.(1985).Estimating latent correlations between repeated testings.Psychometrika,50,3-16. Beck,L. W.(1943).The principle of parsimony in empirical science.The Journal of Philosophy, 40,617-633. Bollen,K. A., & Curran,P.J. (20o6).Latent curve models: A structural equation perspective. Hoboken, NJ: Wiley-Interscience. Brooks,S.P.,& Gelman,A. (1998). General methods for monitoring convergence of iterative simulations. Journal of Computational and Graphical Statistics, 7(4), 434-455 Cai,L. (2010).High-dimensional exploratory item factor analysis by a Metropolis-Hastings Robbins-Monro algorithm. Psychometrika, 75(1),33-57. Cleveland, W. S. (1981) LOWESS: A program for smoothing scaterplots by robust locally weighted regression. The American Statistician, 35, 54. doi: 10.2307/2683591. Chang,H.-H.,& Wang, W. (2O16)."Internet Plus"measurement and evaluation: A new way for adaptive 396 learning. Journal of Jiangxi Normal University (Natural Science), 40(5), 441-455. 397 [张华华,汪文义.(2016)．“互联网+”测评：自适应学习之路．江西师范大学学报(自然科学版),40(5), 398 441-455.] 399 Chen,N.,& Liu,H. (2015). Comparison of methods addressing MNAR missing data when fiting a latent 400 growth model: Selection model and ML. Journal of Psychological Science, 38(2), 446-451. 401 [陈楠，刘红云.(2015).基于增长模型的非随机缺失数据处理：选择模型和极大似然法．心理科学,38(2) 402 446-451.] 403 Chen,Y., Culpepper, S.A., Wang,S.,& Douglas,J. (2018).A hidden Markov model for learning trajectories 404 in cognitive diagnosis with application to spatial rotation skils.Applied Psychological Measurement, 42, 405 5-23. 406 Collins,L. M.,& Lanza, S.T. (2010). Latent class and latent transition analysis: With applications in the 407 social, behavioral, and health sciences.New York: Wiley. 408 Curtis,S. M. (2010). BUGS code for item response theory. Journal of Statistical Software,36(1),1-34. 409 de Boeck, P.,& Jeon, M. (2019). An overview of models for response times and processes in cognitive tests. 410 Frontiers in Psychology， 10,102

411 de Haan-Rietdijk, S., Kuppens, P., Bergeman, C.S.,Sheeber,L. B.,Allen, N. B.,& Hamaker,E.L. (2017). On   
412 the use of mixed Markov models for intensive longitudinal data.Multivariate behaviral research, 52(6),   
413 747-767.   
414 Embretson,S.E.(1991). Implications of a multidimensional latent trait model for measuring change.In L.M.   
415 Colins & J.L. Horn (Eds.), Best methods for the analysis of change: Recent advances, unanswered   
416 questions, future directions (pp. 184-197). Washington, DC: American Psychological Association.   
417 Ferrando, P. J., & Lorenzo-Seva, U. (20o7).A measurement model for Likert responses that incorporates   
418 response time. Multivariate Behavioral Research, 42(4), 675-706.   
419 Fox,J.-P.,& Marianti, S. (2016). Joint modeling ofabilityand differential speed using responses and response   
420 times. Multivariate Behavioral Research, 51(4),540-553.   
421 Guo, J.,Xu, X., Ying, Z.,& Zhang, S. (2021). Modeling not-reached items in timed tests: A response time   
422 censoring approach. Psychometrika, 1-33.   
423 Guo,L. Shang, P.,& Xia,L.(20l7). Advantages and ilustrations of application of response time model in   
424 psychological and educational testing. Advances in Psychological Science, 25(4), 701-712.   
425 [郭磊，尚鹏丽，夏凌翔.(2017).心理与教育测验中反应时模型应用的优势与举例．心理科学进展,25(4)   
426 701-712.]   
427 Han, Y., Xiao,Y.,Liu, H. (2O22). Feature extraction and ability estimation of process data in the   
428 problem-solving test. Advances in Psychological Science, 30(6), 1393-1409.   
429 [韩雨婷，肖悦，刘红云.(2022).问题解决测验中过程数据的特征抽取与能力评估．心理科学进展,30(6)   
430 1393-1409.]   
431 Kaplan,D. (2oo0). Structural equation modeling: Foundations and extensions. Newbury Park, CA: Sage   
432 Publications.   
433 Klein Entink,R. H.,Fox, J.-P.,& van der Linden, W. J. (2009). A multivariate multilevel approach to the   
434 modeling of accuracy and speed of test takers. Psychometrika, 74(1), 21-48.   
435 Klein Entink,R. H.,van der Linden, W. J.,& Fox,J.-P.,(2009). A box-cox normal model for response times.   
436 British Journal of Mathematical and Statistical Psychology, 62, 621-640.   
437 Kohli,N.,& Harring, J.R. (2013). Modeling growth in latent variables using a piecewise function.   
438 Multivariate Behavioral Research, 48(3),370-397.   
439 Levy,R., & Mislevy,R. J.(2016). Bayesian psychometric modeling. Boca Raton,FL: CRC Press.   
440 Liu,H.,& Meng, Q. (2003). Areview on longitudinal data analysis method and it's development. Advances in   
441 Psychological Science, 11(5), 586-592   
442 [刘红云，孟庆茂.(2003).纵向数据分析方法．心理科学进展,11(5),586-592.]   
443 Liu, Y.,Xu, H., Chen, Q.,& Zhan,P. (2022). The measurement of problem-solving competence using process   
444 data. Advances in Psychological Science, 30(3), 522-535.   
445 [刘耀辉，徐慧颖，陈琦鹏，詹沛达.(2022).基于过程数据的问题解决能力测量及数据分析方法．心理科   
446 学进展,30(3),522-535.]   
447 Liu, Y.,Du, H.,Fang, J.,& Wen, Z.(2022). Methodology study and model development for analyzing   
448 longitudinal data in China's mainland. Advances in Psychological Science, 30(6), 1-13.   
449 [刘源，都弘彦，方杰，温忠麟.(2022)．国内追踪数据分析方法研究与模型发展．心理科学进展,30(6),   
450 1-13.]   
451 Meredith, W.,& Tisak, J. (1990).Latent curve analysis. Psychometrika, 55,107-122.   
452 Muthen, B.,& Muthen,L. K. (2000). Integrating person-centered and variable-centered analyses: Growth   
453 mixture modeling with latent trajectory classes. Alcoholism: Clinical and experimental research, 24(6),   
454 882-891.   
455 Paek,I,Li, Z.,& Park, H. (2016). Specifying ability growth models using a multidimensional item response   
456 model for repeated measures categorical ordinal item response data. Multivariate Behavioral Research,   
457 51,569-581.   
458 Piech, C., Spencer, J., Huang, J., Ganguli S., Sahami, M., et al. (2015). Deep knowledge tracing. arXiv:   
459 1506.05908. https://doi.0rg/10.48550/arXiv.1506.05908   
460 Plummer, M. (2015). Jags: Just another Gibbs sampler (version 4.0.0). Retrieved from   
461 http://mcmc-jags.sourceforge.net/   
462 Tang,F.,& Zhan,P. (2O21). Does diagnostic feedback promote learning? Evidence from a longitudinal   
463 cognitive diagnostic assessment. AERA Open, 7.   
464 van der Linden, W. J. (2006).A lognormal model for response times on test items.Journal of Educational and   
465 Behavioral Statistics, 31(2), 181-204.   
466 von Davier, M., Xu, X., & Carstensen, C. H. (2011). Measuring growth in a longitudinal large-scale   
467 assessment with a general latent variable model. Psychometrika, 76, 318-336.   
468 Wang, C., Chang,H.,& Douglas, J. (2013).The linear transformation model with frailties for the analysis of   
469 item response times. British Journal of Mathematical and Statistical Psychology, 66,144-168.   
470 https://doi.0rg/10.1111/j.2044-8317.2012.02045.x   
471 Wang, C.,& Nydick, S. W. (2020). On longitudinal item response theory models: A didactic.Journal of   
472 Educational and Behavioral Statistics,45(3),339-368.   
473 Wang,L.,Tang,F.,& Zhan,P. (2020).Efect analysis of individualized remedial teaching based on cognitive   
474 diagnostic assessment: Taking “linear equation with one unknown” as an example. Journal of   
475 Psychological Science, 43(6), 1490-1497.   
476 [王立君，唐芳，詹沛达.(2020).基于认知诊断测评的个性化补救教学效果分析：以"一元一次方程"为   
477 例．心理科学,43(6),1490-1497.]   
478 Wang, S.,Hu, Y., Wang, Q., Wu,B., Shen,Y.,& Carr, M. (202O). The development of a multidimensional   
479 diagnostic assessment with learning tools to improve 3-D mental rotation skils. Frontiers in Psychology,   
480 11:305.   
481 Wang, S., Yang, Y., Culpepper, S.A.,& Douglas, J.A. (2018). Tracking skillacquisition with cognitive   
482 diagnosis models: A higher-order, hidden Markov model with covariates.Journal of Educational and   
483 Behavioral Statistics, 43,57-87.   
484 Wang, S., Zhang, S., Douglas, J.,& Culpepper, S. (2018). Using response times to assesslearning progress: A   
485 joint model for responses and response times. Measurement: Interdisciplinary Research and Perspectives   
486 16(1), 45-58.   
487 Wang, S., Zhang, S.,& Shen, Y. (2019). A joint modeling framework of responses and response times to   
488 assess learning outcomes. Multivariate Behavioral Research, 55, 49-68.   
489 Wen,Z. (2017). Causal inference and analysis in empirical studies. Journal of Psychological Science, 40(1),   
490 200-208.   
491 [温忠麟.(2017).实证研究中的因果推理与分析．心理科学,40(1),200-208.]   
492 Woolf, B.P. (20o9). Building intelligent tutoring systems. Morgan Kaufman, Burlington   
493 Zhan, P.(202O).A Markov estimation strategy for longitudinal learning diagnosis: Providing timely diagnostic   
494 feedback. Educational and Psychological Measurement, 80(6), 1145-1167.   
495 Zhan, P. (2018). Bayesian cognitive diagnosis modeling incorporating time information: joint analysis of   
496 response times and response accuracy data (Unpublished doctoral dissertation). Beijing Normal   
497 University.   
498 [詹沛达.(2018)．引入时间信息的贝叶斯认知诊断建模：对作答时间和作答精度数据的联合分析(博士   
499 学位论文).北京师范大学.]   
500 Zhan,P. (2022). Joint-cros-loading multimodal cognitive diagnostic modeling incorporating visual fixation   
501 counts. Acta Psychologica Sinica, 54(4), 1-23.   
502 [詹沛达.(2022).引入眼动注视点的联合-交叉负载多模态认知诊断建模．心理学报,54(4),1-23]   
503 Zhan, P.,Jiao,H., Man, K. (2020).The multidimensional log-normal response time model: An exploration of   
504 the multidimensionality of latent processing speed. Acta Psychologica Sinica, 52(9),1132-1142.   
505 [詹沛达,Jiao,H.,&Man,K.(2020).多维对数正态作答时间模型：对潜在加工速度多维性的探究．心理   
506 学报,52(9),1132-1142.]   
507 Zhan,P., Jiao,H.,Liao,D.,&Li,F. (2o19).A longitudinal higher-order diagnostic classfication model.   
508 Journal of Educational and Behavioral Statistics, 44(3),241-281.   
509 Zhan, P., Jiao,H., Man, K,& Wang,L. (2019). Using JAGS for Bayesian cognitive diagnosis modeling: A   
510 tutorial. Journal of Educational and Behavioral Statistics, 44(4), 473-503   
511 Zhang, S.,& Chang, H.-H. (2016).From smart testing to smart learning: How testing technology can assist   
512 the new generation of education. International Journal of Smart Technology and Learning, 1, 67-92.   
513 中共中央，国务院.(2020)．深化新时代教育评价改革总体方案.URL:   
514 http://www.gov.cn/zhengce/2020-10/13/content_ 5551032.htm   
515

# Longitudinal Item Response Times Models for Tracking Change in Latent Processng Speed

# Abstract

In psychological，educational,and behavioral studies，measuring change over time is essential to developmental study. These changes can sometimes be captured by longitudinal latent variable models,such as longitudinal item response theory models and latent growth curve models. With the spread of computerized (or web-based) assessments,ithas become common to collect process data such as item response time (RT) in additio to traditional item response accuracy (RA) data. RT data is used as a complement to RA data, describes the total time taken by individuals to solve problems and can be used to analyze the latent processing speed of individuals. However, a review of the existing studies reveals that existing longitudinal models focus on longitudinal RA data and lack atention to longitudinal RT data;Moreover,most of the existing RT models are limited to analyzing cross-sectional RT data and cannot track the development of students' latent processing speed over time.To this end,four longitudinal RT models based on two commonly used longitudinal modeling methods (i.e., multivariate normal distribution modeling and latent growth curve modeling) were proposed to achieve objective tracking of individual potential processng speed development and enrich the analysis methods of longitudinal RT data.

Based on the most commonly used cross-sectional RT model, the lognormal RT model (LRTM), four longitudinal RT models were proposed, including the multivariate normal distribution-based LRTM(denoted as MVN-LRTM) and its constraint model with the Markov property (denoted as MVN-LRTM-M),the linear latent growth curve-based LRTM (denoted as LGC-LRTM-L),and the nonlinear latent growth curve-based LRTM (denoted as LGC-LRTM-N). The measurement models are consistent across the four models, with diferences mainly in the structural model describing how the latent processing speed changes over time. First, an adaptive learning/assessment dataset about spatial rotation ability was used as an empirical example to show the practical applicability of the proposed models. Second,two simulation studies were conducted further to explore the psychometric performance of the proposed models.The purpose of simulation study 1 was to explore the recovery of parameter estimation under different simulated conditions.The purpose of simulation study 2 was to explore the tolerance of the proposed models to different proportions of missing RT data.

The results of the empirical study mainly indicated that all four longitudinal RT models are practically applicable and have high consistency in the analysis results for the same cohort of data.The results of simulation study 1 showed that the parameters of the proposed models can be well recovered under various simulated conditions.The results of simulation study 2 mainly indicated that the proposed models are tolerant to different proportions of missing RTdata,and it was suggested that the proportion of missing RTdata should be controlled below $60 \%$ in practical applications.

Overall the four longitudinal RT models proposed in this paper have practical applicability and good psychometric performance，which enriches the analysis of longitudinal RT data in psychological and

ChinaXiv预印本 educational assessments.

Keywords: response times； longitudinal data; lognormal response times model; latent growth curve; item response theory

ChinaXiv预印本

附录：

# S1.先验分布对参数估计的影响

# S1.1．低、中和高信息先验分布

# S1.1.1．中信息先验分布

在贝叶斯MCMC 参数估计中，先验分布的选择反映了数据分析者的经验和对模型参数的预判。根据已有分析经验和研究结果(詹沛达等,2020;Fox& Marianti,2016; Wang,S., Zhang et al.,2018)，中信息先验分布(i.e.，包含适量信息的先验分布)设定如下：

首先，所有模型的题目参数的先验分布一样：

$$
\begin{array} { r } { \xi _ { i } { \sim } \mathrm { N } ( 4 , 1 ) , \ \Phi _ { i } { \sim } \mathrm { N } ( 1 , 1 ) \mathrm { I } ( \Phi _ { i } > 0 ) , \omega _ { i } { \sim } \sqrt { \mathrm { I n v G a m m a } ( 1 , 1 ) } . } \end{array}
$$

其次，两个MVN-LRTM而言，潜在加工速度均值的先验分布为：

$$
\begin{array} { r } { \mu _ { p \geq 2 } { \sim } N ( 0 , 1 ) . } \end{array}
$$

对LGC-LRTM-L而言，增长曲线系数的先验分布为：

$$
\begin{array} { r } { \mu _ { \pi _ { 1 } } \sim N ( 0 , 1 ) . } \end{array}
$$

对LGC-LRTM-N而言，增长曲线系数的先验分布为：

$$
\mu _ { \pi _ { 1 } } { \sim } N ( 0 , 1 ) \operatorname { \mathcal { F } } \mathbb { I } \mu _ { \pi _ { 2 } } { \sim } N ( 0 , 1 ) .
$$

# S1.1.2.低信息先验分布

低信息先验分布以大方差为变异范围，在S1.1.1的基础上，低信息先验分布设定如下：

$$
\begin{array} { r l } & { \xi _ { i } \sim \mathrm { N } ( 0 , 1 0 ) , \ \phi _ { i } \sim \mathrm { N } ( 0 , 1 0 ) \ \mathrm { I } ( \phi _ { i } > 0 ) , \ \omega _ { i } \sim \sqrt { \mathrm { I n v G a m m a } ( 1 0 , 1 0 ) } . } \\ & { \qquad \mu _ { p \geq 2 } \sim N ( 0 , 1 0 ) . } \\ & { \qquad \mu _ { \pi _ { 1 } } \sim N ( 0 , 1 0 ) , \ \mu _ { \pi _ { 2 } } \sim N ( 0 , 1 0 ) . } \end{array}
$$

# S1.1.3.高信息先验分布

高信息先验分布围绕“真值”设定，并以小方差为变异范围，在 S1.1.1的基础上，高信息先验分布设定如下：

$$
\begin{array} { c } { { \xi _ { i } { \sim } \mathrm { N } ( 4 , 0 . 5 ) , ~ \phi _ { i } { \sim } \mathrm { N } ( 0 . 2 5 , 0 . 5 ) ~ \mathrm { I } ( \phi _ { i } > 0 ) , \omega _ { i } { \sim } \sqrt { \mathrm { I n v G a m m a } ( 2 , 6 ) } . } } \\ { { \mu _ { p \geq 2 } { \sim } N ( 0 . 5 ( p - 1 ) , 0 . 5 ) . } } \\ { { \mu _ { \pi _ { 1 } } { \sim } N ( 0 . 5 , 0 . 5 ) , \mu _ { \pi _ { 2 } } { \sim } N ( 0 , 0 . 5 ) . } } \end{array}
$$

# S1.2.参数估计一致性

选用正文所用实证研究数据，该数据包含较大比例缺失值，意味着参数估计结果更易受到先验分布的影响，因此更适合用于探究模型参数对先验分布的敏感性。模型的参数估计设定与实证研究保持一致。图 S1呈现了四个模型在不同信息量先验分布下的题目参数估计值。图 S2呈现了四个模型在不同信息量先验分布下的潜在加工速度之间的相关散点图(由于篇幅限制，对5个时间点的潜在加工速度求均值)。整体而言，当采用包含不同信息量的先验分布时，每个模型的参数估计结果均无明显变化、较为稳定，即模型对不同信息量先验分布具有较高的稳健性。

![](images/69051d91af7e2f176b075f61b6885f62620927791337c5d2451be6bfaf2c0e3c.jpg)  
图S1.四模型在不同信息量先验分布下的题目参数估计值，

![](images/da2522c45ab41d5d4f663abd9148227f8b04279bcd3e2bdfdbd9f8ef1cc50260.jpg)  
图 S2.四模型在不同信息量先验分布下的潜在加工速度估计值之间的相关散点图(以低信息量为 $\mathbf { x }$ 轴)