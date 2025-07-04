# 认知诊断模型Q矩阵修正：完整信息矩阵的作用

刘彦楼」吴琼琼²

( 曲阜师范大学教育大数据研究院;²曲阜师范大学心理学院，济宁 273165)

摘要Q矩阵是CDM的核心元素之一，反映了测验的内部结构和内容设计，通常由领域专家根据经验进行主观界定，因此需要对可能存在的错误进行修正。本研究提出了一种新的Q矩阵修正方法——基于完整经验交叉相乘信息矩阵的Wald-XPD方法。采用 Monte Carlo模拟检验了新方法的表现，并与同类方法进行了比较。研究表明：新开发的Wald-XPD方法在Q矩阵恢复率、保留正确标定属性的比例以及修正错误标定属性的比例这三个主要指标上均有较好的表现，且整体上优于其他方法，尤其是在修正错误标定的属性方面。通过实证数据展示了Wald-XPD方法在Q矩阵修正中的良好表现。总之，本研究为Q矩阵修正提供了有效的方法。

关键词认知诊断模型，Q矩阵，XPD矩阵，Wald检验

# 1引言

经典心理测量理论及项目反应理论采用单一的测验分数来描述被试在某个阶段的学习效果。作为新一代心理测量理论，认知诊断(cognitive diagnosis)的主要目的是提供关于被试的多维、细粒度潜在特质(如知识、认识过程、技能、策略、人格特质或心理障碍等，统称为属性)的诊断性评价信息，认知诊断模型(cognitive diagnostic model,CDM)是研究者为了实现以上主要目的而提出的一类离散潜变量模型(Rupp et al.,2010)。目前，CDM已广泛应用于心理、教育、精神病理学等领域(Sorrel et al.,2016)。

Q矩阵是CDM的核心元素之一，定义了测验所测属性与项目之间的对应关系(Tatsuoka,1990)，它不仅决定着测验的内部结构，也关系到认知诊断结果的准确性。正确设定的Q矩阵是获得准确的模型参数估计和被试分类的关键因素(Na'jera etal.,2020)，错误设定的Q矩阵会产生很多不良的影响，如降低模型参数估计准确性、导致较差的模型—数据拟合、导致错误的属性估计和被试分类等(Chiu,2013;de la Torre,2009; Rupp& Templin,2008)。CDM中获取Q矩阵的方法主要是由领域专家根据经验构建(Sorrelet al.,2016)，但这种方法包含一定的主观性。实践中，原始Q矩阵有较大可能包含一些错误设定(Rupp& Templin,2008)，如何修正原始Q矩阵中可能存在的错误是研究者面临的重要理论与现实问题。

为」狄侍止佣以定的矩阡，国内外听九有捉山」多种修止刀法(字住 寺,2U21)。根据是否采用参数化的CDM描述Q矩阵与观察作答数据之间的关系，可以将Q矩阵修正方法分为两类：参数化和非参数化的修正方法，前者需要参数化CDM的参与，后者不需要。例如，欧氏距离法(Chiu,2013)、海明距离(汪大勋，高旭亮，韩雨婷 等,2018)、交差方法(intersection and difference;Wang et al.,2018)等属于非参数化的修正方法。一般而言，非参数化方法比较的是理想反应与观察作答反应之间的拟合，从而达到修正Q矩阵的目的。在非参数化方法中，理想反应大多都是在限制条件较为严格的情景下获得的，例如，限定所有项目只适用于某个或某几个特殊的(亦称，简化的)CDM。换言之，非参数化的Q矩阵修正方法具有样本量要求小、易实现等优点，但严格的前提条件限制了这些方法的拓展性及实用性。参数化Q矩阵修正方法是在参数化模型框架下，使用各种统计量估计出最能拟合观察数据的Q 矩阵。在特殊的 CDM 框架下，如 DINA、DINO、R-RUM 等(de la Torre,2011)，研究者开发的参数化修正方法主要有： $\delta$ 法(delaTorre,2008)、γ法(涂冬波 等,2012)、S 统计量方法(Liu et al.,2012)、迭代修正序列搜索(iterative modified sequential search; Terzi& de la Torre,2018)、RMSEA 统计量(Kang etal.,2019)、加权残差R法(Yu&Cheng,2020)、最优反应分布纯度方法(李佳 等,2022)等。在饱和 CDM 框架下(如,G-DINA,generalized deterministic inputnoisy output“and”gate; de la Torre,2011)的参数化Q矩阵修正方法主要包括：GDI(G-DINAdiscrimination index)方法(de la Torre & Chiu,2016)、残差方法(Chen,2017)、iJSD (iterativeJensen-Shannon divergence)方法以及 iGDI (iterative GDI)方法(Terzi, 2017)、TLP (truncated $L _ { 1 }$ penalty function)方法(Xu& Shang,2018)、相对拟合统计量方法(汪大勋 等,2020)、Ma 和 dela Torre (2020)提出的 GDI 和基于不完整信息矩阵(incomplete information matrix)的 Wald 检验相结合的 Stepwise 方法(为了便于理解且与本文中提出的新方法加以区分，将 Stepwise 方法称为Wald-IC 方法)、以及Hull方法(Na'jera etal.,2021)等。尽管一些参数化的修正方法可能存在运算量大、速度慢的不足之处，但是，这类修正方法尤其是在饱和的CDM框架下开发的方法的优点在于灵活性高、不需要非参数化方法那样严格的前提假设。因为饱和模型包含多类特殊模型作为特例，且在Q矩阵没有错误设定或存在少量错误时，可以较为容易地通过模型比较的方法获得恰当的特殊模型。

在饱和CDM框架下开发的以上八种参数化Q矩阵修正方法中，残差方法对于属性过度设定不敏感且在测验长度较短时统计检验力可能会偏低；当样本量较小时，TLP方法会高估错误设定项目的数量且用于减少错误报告率的重抽样校正方法(bootstrap bagging method)的耗时可能会特别长；模拟研究表明iGDI的表现与iJSD 的表现相当、甚至在一些条件下优于iJSD(Terzi,2017)；相对拟合统计量方法需要比较测验的所有项目关于属性所有可能组合的相对拟合值，尽管研究者提出一些减少计算次数的方法，但是在测验长度较长或属性数量较多的情况下，计算耗时仍有可能特别长。GDI在饱和CDM框架下采用单个项目所有可能的属性掌握模式中正确答对概率的方差来衡量Q矩阵中相对应的 $\mathbf { q }$ 向量的区分能力，选择有最大区分能力的q向量作为正确设定的q向量。相对于GDI而言，iGDI的估计效果有了一定程度的改善，但是这类方法的主要缺点是需要人为地确定一个截止值(Na'jera et al.,2019)。以GDI研究为基础，Ma 和de la Torre(2020)将Q矩阵修正的视角延伸到多级计分模型，在 seq-GDINA 模型(the sequential GDINA model; Ma & de la Torre,2016)下提出了 GDI和基于不完整信息矩阵的Wald 检验相结合的Wald-IC 方法。Wald-IC 方法首先采用GDI方法从单一属性的q向量中确定第一个所需属性，再逐步多次采用Wald 统计量决定是否增加或删除属性来选择恰当的q向量。即，在单个项目上Wald-IC 仅需执行K-1个统计检验即可完成。Hul1方法试图在模型拟合与简约之间找到一种平衡以此选择恰当的 $\textbf { q }$ 向量，研究者(Na'jera et al.,2021)通过模拟研究比较了GDI、Wald-IC 以及Hull方法，结果表明在大多数条件下 Hull 的表现最好、Wald-IC 的表现稍逊于Hull。但是，Hull 和 Wald-IC 在修正错误标定的属性方面的表现较差，尤其是Q矩阵中存在较多错误设定时。研究者(Ma&dela Torre,2020;Na'jera et al.,2021)构建的Wald-IC 统计量是使用不完整信息矩阵计算的。先前研究表明，采用不完整信息矩阵构建的统计量在后续研究中会导致一些问题，如低估模型参数标准误(Philipp et al.,2018)、用于项目功能差异检验及项目水平模型比较时导致一类错误控制率膨胀(Liu,Andersson et al.,2019;Liu, Yin et al.,2019；刘彦楼 等,2016)等。基于此，本研究认为Wald-IC方法在修正错误标定属性方面表现较差的主要原因可能是在Wald统计量的计算中采用了不完整的信息矩阵。

研究者(Liu et al., 2016; Liu,Xin et al., 2019; Liu et al., 2021; Philipp et al.,2018；刘彦楼等,2016)认为CDM中同时存在两种类型的模型参数：项目参数和结构参数。不完整信息矩阵(de la Torre,2009;2011)忽略了结构参数，计算量较小，有较大可能导致Q矩阵修正结果不够准确。以往研究者提出了多种完整信息矩阵估计方法(Liu,Xin et al.,2019;Liu et al.,2021;Philipp etal.,2018；刘彦楼 等,2016)，但是这些关于模型参数的信息矩阵无法直接用于Q矩阵修正中Wald 统计量的计算，因为此类Wald 统计量中使用的是关于模型参数的方差—协方差矩阵。此外，与其他完整信息矩阵相比，经验交叉相乘信息矩阵(empirical cross-productinformation matrix,XPD;Liu et al.,2021; Philipp et al.,2018；刘彦楼 等,2016)计算量较小，故本研究在包含全部模型参数的XPD 矩阵的基础上，经过转换获得关于项目正确作答概率的方差—协方差矩阵，以此构建用于Q矩阵修正的Wald 统计量(记为Wald-XPD)

本文的主要目的在于提出一种新的Q矩阵修正方法，并通过模拟研究与实证数据分析考察新方法的表现。模拟研究参考了以往研究者研究中采用的模拟条件(de la Torre& Chiu,2016;Ma&de la Torre,2020; Na'jera et al.,2021)，考察新开发的方法在Q矩阵修正中的表现，并与同类方法进行比较，希望能够为实践研究者在Q矩阵修正方法的选用方面提供方法支持。本研究选择GDI、Hull、Wald-IC 方法与Wald-XPD 方法进行比较的原因是：首先，Wald-XPD 是在Wald-IC 方法基础上提出的，新方法与旧方法表现的异同有待探索；其次，先前研究表明在GDI、Hull、Wald-IC 三种方法中，Hull 的表现是最好的，故有必要比较 Hull与Wald-XPD 两种方法的表现；第三，限制GDI及iGDI方法实践应用的主要原因是这两种方法均需要人为地设置一个截止值，与iGDI相比，固定的截止值对GDI方法的影响相对较小(Na'jera etal.,2020)，因此本研究将GDI也纳入比较。本文的第二部分介绍了以往研究者在饱和的CDM框架下提出的参数化Q矩阵修正方法。第三部分介绍了新开发的Wald-XPD方法。第四部分采用模拟研究，在较广泛和真实的条件下探索Wald-XPD方法的具体表现，并与GDI、Hull以及Wald-IC 方法进行比较。第五部分探讨Wald-XPD方法在实证数据分析中的应用，并与Hull方法、Wald-IC方法进行比较。最后对Wald-XPD方法进行了讨论与展望。

# 2饱和CDM框架下的参数化Q矩阵修正方法

在认知诊断测验中，Q矩阵是建立可观察的被试作答反应和不可观察的项目特征之间联系的桥梁。一般而言，二值计分测验中的Q是 $J \times K$ 维的矩阵，表示 $J$ 个项目测量了 $K$ 个属性。通常也将属性假定为二值计分，根据项目 $j$ 是否测量了属性 $k$ ， $q _ { j k }$ 可以取0或者1。假如，一份测验包含3个项目，共考察了2个属性，那么根据项目和属性之间的关系，可以构建如下Q矩阵：

$$
\mathbf { Q } = { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \\ { 1 } & { 1 } \end{array} \right] }
$$

其中， $\mathbf { q } _ { 1 } ^ { \prime } { = } \lbrack 1 , 0 \rbrack$ 表示测验中的第一个项目测量了属性1(即 $\alpha _ { 1 } ^ { \cdot }$ )。但是，不同专家界定的Q矩阵不尽相同，合理设定Q矩阵并非易事。譬如，国内外研究者对于分数减法数据中(Tatsuoka,1990)的属性设定，至今仍存在争议(dela Torre&Chiu,2016；汪大勋，高旭亮，蔡艳 等,2018)。因此，对原始Q矩阵进行修正是非常必要的。

本研究以G-DINA 模型为例，考察新提出的 Wald-XPD 方法在Q 矩阵修正的表现，并与以往研究者提出的GDI、Wald-IC、Hull 方法进行比较。G-DINA 模型是一般、饱和的 CDM模型，对其进行适当约束，可以获得多种特殊模型(de la Torre,2011)。令 $\mathbf { \delta } \mathbf { u } _ { \iota }$ 表示第 $l$ 种属性掌握模式， $\mathbf { q } _ { j } ^ { ' } = \left[ q _ { j 1 } , . . . , q _ { j K } \right]$ 表示项目 $j$ 与测验中 $K$ 个属性之间的对应关系，在饱和的 G-DINA 模型中，正确答对项目 $j$ 的概率可表示为：

$$
p _ { j } \left( \mathbf { a } _ { l } ^ { } \right) = p _ { j } \left( \mathbf { a } _ { l } ^ { } , \mathbf { q } _ { j } ^ { } \right) = \delta _ { j 0 } + \sum _ { k = 1 } ^ { K } \delta _ { j k } ^ { } \alpha _ { l k } q _ { j k } ^ { } + \sum _ { k = 1 } ^ { K - 1 } \sum _ { k = k + 1 } ^ { K } \delta _ { j , 2 , \left( k , k \right) } ^ { } \alpha _ { n k } ^ { } \alpha _ { n k } ^ { } q _ { j k } ^ { } q _ { j k ^ { \prime } } ^ { } + \cdots
$$

其中， $\delta _ { j 0 }$ 是项目 $j$ 的截距项参数， $\delta _ { j k }$ 是這 $\alpha _ { l k }$ 的主效应参数， $\delta _ { j , 2 , \left( k , k ^ { ' } \right) }$ 是這 $\alpha _ { l k }$ 与寶 $\alpha _ { _ { l k ^ { \prime } } }$ 之间的交互效应参数。需要特别说明的是，在公式(1)中，如果 $\mathbf { \delta } \mathbf { u } _ { \iota }$ 或 ${ \bf q } _ { j }$ 中的某个元素等于0，那么对应的项目参数 $\delta$ 也等于0。

# 2.1 GDI方法

GDI方法(de la Torre& Chiu,2016)是在G-DINA 模型框架下提出的，其基本思想是：使用项目 $j$ 中所有可能的属性掌握模式条件下的正确答对概率的方差来衡量 $\textbf { q }$ 向量的分辨能力，选择有最大分辨能力的q向量作为正确设定的q向量，即正确设定的 $\mathbf { q }$ 向量能够使不同属性掌握模式的被试正确作答概率方差最大化。GDI 方法采用辨别指数 $\varsigma _ { j } ^ { 2 }$ (discriminatingindex)表示正确作答概率的方差，即项目 $j$ 的某个 $\mathbf { q }$ 向量关于所有可能的属性掌握模式的被试正确作答概率的方差：

$$
\mathcal { G } _ { j } ^ { 2 } = \sum _ { l = 1 } ^ { 2 ^ { K } } w ( \mathbf { \mathbf { \mathbf { a } } } _ { l } \big | \mathbf { x } ) [ p _ { j } ( \mathbf { \mathbf { \mathbf { a } } } _ { l } ) - \overline { { p } } _ { j } ] ^ { 2 }
$$

其中， $p _ { j } ( { \pmb a } _ { l } )$ 表示拥有属性掌握模式为 $\mathbf { \delta } \mathbf { u } _ { \iota }$ 的被试正确作答的概率； $\overline { { \boldsymbol { p } } } _ { j }$ 表示所有被试平均的正确作答概率。另外， $w ( \mathbf { \boldsymbol { a } } _ { l } \left| \mathbf { \boldsymbol { x } } \right. )$ 表示在测验项目的观察反应矩阵 $\mathbf { x }$ 中属性掌握模式为 $\mathbf { \delta } \mathbf { u } _ { \iota }$ 的被试的后验概率：

$$
w \big ( \mathbf { a } _ { l } | \mathbf { x } \big ) = \sum _ { i = 1 } ^ { N } w \big ( \mathbf { a } _ { l } | \mathbf { x } _ { i } \big ) { = } \sum _ { i = 1 } ^ { N } { \frac { L \big ( \mathbf { x } _ { i } | \mathbf { a } _ { l } \big ) \pi \big ( \mathbf { a } _ { l } \big ) } { \displaystyle \sum _ { l = 1 } ^ { 2 ^ { K } } { L \big ( \mathbf { x } _ { i } | \mathbf { a } _ { l } \big ) \pi \big ( \mathbf { a } _ { l } \big ) } } }
$$

公式(3)中， $N$ 表示样本量； $L \left( \mathbf { x } _ { i } \left| \mathbf { a } _ { l } \right. \right)$ 表示属性掌握模式为 $\mathbf { \delta } \mathbf { u } _ { \iota }$ 的被试 $i$ 在所有项目上作答反应$\mathbf { X } _ { i }$ 的条件似然函数； $\pi \big ( \mathfrak { a } _ { l } \big )$ 表示拥有第 $l$ 种属性掌握模式的被试在总体中所占的比例，即第$l$ 个结构参数。

辨别指数 $\varsigma _ { j } ^ { 2 }$ 用来衡量一个项目的辨别力，即区分不同属性掌握模式的被试的能力。有最大GDI且需要最少属性数的 $\mathbf { q }$ 向量，才是正确设定的 $\mathbf { q }$ 向量。但是，实践中由于随机误差，过度设定(over-specifications,OS)的 $\mathbf { q }$ 向量比正确设定的 $\mathbf { q }$ 向量有更大的GDI值，如全为1的 $\mathbf { q }$ 向量（ $\bf q ^ { ' } = [ l , . . . , l ]$ )有最大的GDI值。因为在原有 $\mathbf { q }$ 向量的基础上增加属性会导致潜在组差异，使成功概率的方差变大，故 $\mathbf { q } ^ { \prime } = \left[ 1 , . . . , 1 \right]$ 时的 $\varsigma _ { 1 : K } ^ { 2 }$ 是最大的。然而，这种较高的潜在组之间的差异是虚假的。本着合适与简约原则，正确设定的 $\mathbf { q }$ 向量应是简单且有最大成功作答概率方差的,故de la Torre 和Chiu(2016)计算了 $\mathbf { q }$ 向量的所占方差PVAF(the proportionof variance accounted for):

$$
\mathrm { P V A F } = { \frac { \varsigma _ { j } ^ { 2 } } { \varsigma _ { 1 : K } ^ { 2 } } }
$$

其中， $\varsigma _ { 1 : K } ^ { 2 }$ 表示项目 $j$ 的全为1的 $\mathbf { q }$ 向量关于所有可能的属性掌握模式的被试正确作答概率的方差。

截止值用来判断一个 $\mathbf { q }$ 向量的 PVAF 是否合适。一个正确设定的 $\mathbf { q }$ 向量需要满足两个条件：(1)PVAF大于截止值；(2)包含的属性数最少。若多个 $\mathbf { q }$ 向量同时满足以上两个条件，则选择PVAF值最大的q向量作为正确设定的q向量。

# 2.2 Hull方法

Hull方法(Na'jera etal.,2021)的基本原理是：在项目水平上比较所有可能q向量的拟合指标。将所有可能的q向量呈现在Hull图上，Hull图的横坐标表示与每个q向量相关的参数数量，纵坐标表示拟合指标。Hull方法选取的拟合指标有两个：第一个是PVAF，用来评估不同q向量的项目区分度大小；第二个是绝对模型拟合指数 McFadden pseudo- $R ^ { 2 }$ (McFadden,1974)，用于衡量观察反应中方差所占的比例，评估获得的估计值与观察反应之间的拟合度(Hull 方法的两个指标在下文分别表示为 HulIP 和 HullR)。选择项目 $j$ 中不同参数数量下有最大PVAF或McFaddenpseudo- $R ^ { 2 }$ 值的 $\mathbf { q }$ 向量作为候选 $\mathbf { q }$ 向量，任意两个候选$\mathbf { q }$ 向量之间会形成一条线段，将该线段下方的所有 $\mathbf { q }$ 向量移除，故Hull图成一条单调递增的曲线。假设项目 $j$ 的 $K { = } 3$ ，那么以PVAF为指标的Hull图如图1所示，图中上方蓝色字体表示候选 $\mathbf { q }$ 向量，下方黑色字体表示该候选q向量的PVAF。

![](images/2860dac0903176a4a181023be3e0ab71985a3cc2ba90fbe61a3dcae5ae7c4ccd.jpg)  
图1 $K = 3$ 时，以PVAF 为指标的 Hull 图

对于Hull方法的两个拟合指标而言，添加项目中相关联的属性会显著增加拟合指标的值；添加不关联的属性也会增加拟合指标的值，但影响可能较小。故从拟合—简约相平衡的视角出发，在Hul图中选择先使拟合指标显著增加，然后使拟合指标平缓增加的候选q向量作为正确设定的 $\mathbf { q }$ 向量。基于此，研究者采用 $s t$ 指数(Ceulemans & Kiers,2006)计算每个候选 $\mathbf { q }$ 向量的拐角大小(the magnitude of the elbow)，选择 $s t$ 指数最大的候选 $\mathbf { q }$ 向量作为正确设定的 $\mathbf { q }$ 向量：

$$
s t _ { j K } = \frac { \left( f _ { j K } - f _ { j K - 1 } \right) / \left( n p _ { K } - n p _ { K - 1 } \right) } { \left( f _ { j K + 1 } - f _ { j K } \right) / \left( n p _ { K + 1 } - n p _ { K } \right) }
$$

其中， $f _ { j K }$ 和 $n p _ { K }$ 分别表示项目 $j$ 的 $K$ 个候选 $\mathbf { q }$ 向量的拟合指标和参数数量。

需要强调的是，移除候选 $\mathbf { q }$ 向量下方所有的 $\mathbf { q }$ 向量之后，若图中仅剩下原点处和全为1的 $\mathbf { q }$ 向量 $\bf \ddot { q } = \left[ 1 , \dots , 1 \right] .$ )，则选择全为1的 $\mathbf { q }$ 向量作为该项目正确设定的 $\mathbf { q }$ 向量；若图中仍有两个或多个 $\mathbf { q }$ 向量，则计算每个 $\mathbf { q }$ 向量的 $s t$ 指数， $^ { s t }$ 指数最大的候选 $\mathbf { q }$ 向量即为该项目正确设定的 $\mathbf { q }$ 向量。

# 2.3 Wald-IC方法

用于Q矩阵修正的Wald 统计量也是在项目水平上进行的，其基本原理是：假设项目 $j$ 所对应的 $\mathbf { q }$ 向量定义了2个及以上的属性，如果将某一属性从 $\mathbf { q }$ 向量中移除而没有导致模型—数据拟合变差，那么这个属性就不是必需的。为便于理解，现举例说明。假设一个测验共测量了2个属性，即 $K = 2$ ，那么，所有可能的属性掌握模式有4种，可以表示为：

$$
\mathbf { a } = { \left[ \begin{array} { l } { \mathbf { a } _ { 1 } } \\ { \mathbf { a } _ { 2 } } \\ { \mathbf { a } _ { 3 } } \\ { \mathbf { a } _ { 4 } } \end{array} \right] } = { \left[ \begin{array} { l l } { 0 } & { 0 } \\ { 1 } & { 0 } \\ { 0 } & { 1 } \\ { 1 } & { 1 } \end{array} \right] }
$$

假设待检验的 $\mathbf { q }$ 向量为 $\begin{array} { r } { \mathbf q ^ { ' } = \left[ 1 , 1 \right] } \end{array}$ ，那么相应的项目正确作答概率的向量可以表示为：

$$
\mathbf { p } _ { j } \left( \mathbf { a } \right) = \left[ \begin{array} { c } { p _ { j } \left( \mathbf { a } _ { 1 } \right) } \\ { p _ { j } \left( \mathbf { a } _ { 2 } \right) } \\ { p _ { j } \left( \mathbf { a } _ { 3 } \right) } \\ { p _ { j } \left( \mathbf { a } _ { 4 } \right) } \end{array} \right] = \left[ \begin{array} { c } { \delta _ { j 0 } } \\ { \delta _ { j 0 } + \delta _ { j 1 } } \\ { \delta _ { j 0 } + \delta _ { j 2 } } \\ { \delta _ { j 0 } + \delta _ { j 1 } + \delta _ { j 2 } + \delta _ { j 1 2 } } \end{array} \right]
$$

检验属性1(即 $\alpha _ { \mathrm { { 1 } } }$ )是否是必需的，首先需要构建 $\alpha _ { \mathrm { { 1 } } }$ 的 $\mathbf { R }$ 矩阵：

$$
\mathbf { R } = \left[ { \begin{array} { c c c c } { 1 } & { - 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { - 1 } \end{array} } \right]
$$

本文中， $^ { 6 6 } \times$ "用于矩阵或向量时，表示矩阵相乘。若 $\alpha _ { \mathrm { { 1 } } }$ 在统计上不是必需的，那么 $\mathbf { R } \times \mathbf { p } _ { j } ( \mathbf { a } ) { = } \mathbf { 0 }$ 。即：

$$
\begin{array} { r } { \bigg [ \mathbf { 1 } \quad - \mathbf { 1 } \quad 0 \quad 0 \bigg ] \times \left[ \begin{array} { l } { p _ { j } \left( \mathbf { a } _ { 1 } \right) } \\ { p _ { j } \left( \mathbf { a } _ { 2 } \right) } \\ { p _ { j } \left( \mathbf { a } _ { 3 } \right) } \end{array} \right] = \left[ \begin{array} { l } { - \delta _ { j 1 } } \\ { - \left( \delta _ { j 1 } + \delta _ { j 1 2 } \right) } \end{array} \right] = \mathbf { 0 } } \end{array}
$$

表明掌握 $\alpha _ { \mathrm { { 1 } } }$ 不会增加正确答对项目 $j$ 的概率，故 $\alpha _ { \mathrm { { 1 } } }$ 不是必需的。此外，检验属性2(即 $\alpha _ { 2 }$ )是否必需的 $\mathbf { R }$ 矩阵为：

$$
\mathbf { R } = \left[ { \begin{array} { c c c c } { 1 } & { 0 } & { - 1 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { - 1 } \end{array} } \right]
$$

需要说明的是，对于项目 $j$ 而言，不同的待检验属性所对应的 $\mathbf { q }$ 向量是不同，也就是项目参数估计值是不同的，因此，向量 ${ \bf p } _ { j } ( { \bf a } )$ 的值不是固定的。

Wald-IC统计量的形式为：

$$
{ \mathrm { W a l d } } _ { _ { \mathrm { ( I C ) } } } = \Bigl [ { \bf R } \times { \bf p } _ { j } ( { \bf u } ) \Bigr ] ^ { \prime } \Bigl ( { \bf R } \times { \bf V } _ { _ \mathrm { ( I C ) } j } \times { \bf R } ^ { \prime } \Bigr ) ^ { - 1 } \Bigl [ { \bf R } \times { \bf p } _ { j } ( { \bf u } ) \Bigr ]
$$

其中， ${ \bf V } _ { \mathrm { ( I C ) } j }$ 是基于不完整信息矩阵计算的项目 $j$ 正确作答概率的方差—协方差矩阵。

Wald-IC 方法修正Q矩阵的步骤为：首先，需要构建一个 $2 ^ { K _ { j } ^ { * } - 1 } \times 2 ^ { K _ { j } ^ { * } }$ 的 $\mathbf { R }$ 矩阵， $\boldsymbol { K } _ { j } ^ { * }$ 表示待检验的 $\mathbf { q }$ 向量中定义的项目 $j$ 需要的属性数量。在零假设下，即属性 $k$ 在统计上不是必需

的，那么 $\mathbf { R } \times \mathbf { p } _ { j } ( \mathbf { a } ) { = } \mathbf { 0 }$ 。其次，需要对不完整信息矩阵求逆获得项目正确作答概率的方差—协方差矩阵 ${ \bf V } _ { ( \mathrm { I C } ) j }$ 来构建Wald 统计量。Ma 和de la Torre (2020)采用的是 de la Torre (2009)提出的考虑全部项目正确作答概率的不完整信息矩阵估计方法 $\mathcal { T } _ { D 0 9 }$ ：

$$
\mathcal { T } _ { _ { D 0 9 } } = \frac { \partial \ell ( \mathbf { x } ) } { \partial \left[ \mathbf { p } _ { j } ( \mathbf { u } ) \right] } \times \frac { \partial \ell ( \mathbf { x } ) } { \partial \left[ \mathbf { p } _ { j } ( \mathbf { u } ) \right] ^ { \prime } }
$$

其中， $\ell ( \mathbf { x } )$ 表示观察数据的对数似然函数。理论上，用于 $\mathbf { Q }$ 矩阵修正的Wald统计量渐近 $\chi ^ { 2 }$ 分布，自由度是 $2 ^ { K _ { j } ^ { * } - 1 }$ 。但是,Wald-IC 统计量中方差—协方差矩阵的计算存在不准确的问题，可能导致Q矩阵修正的效果不理想。

# 3基于完整XPD 矩阵的Wald-XPD方法

# 3.1使用 XPD 矩阵构建Wald-XPD 统计量

Philipp 等人(2018)和Liu等人(2021)用结构参数 $\pmb { \pi }$ 描述被试总体的潜在属性掌握模式 $\mathbf { a }$ 的分布状况， $\pmb { \pi } = \left( \pi _ { 1 } , \cdots , \pi _ { L } \right) ^ { \prime }$ 。假设 $K = 2$ ，那么在这个测验中被试所有可能的属性掌握模式$\mathbf { \delta } \mathbf { u } _ { \iota }$ 有 $L = 4$ 种， $\pi _ { l } = \pi \big ( \mathbf { a } _ { l } \big )$ 表示被试总体中具有第 $l$ 种属性掌握模式 $\mathbf { \delta } \mathbf { u } _ { \iota }$ 的分布比例。例如，$\pi \big ( { \bf q } _ { _ { 1 } } \big )$ 是被试总体中具有第1种属性掌握模式 $\pmb { a } _ { 1 } ^ { ^ { \prime } } = \left[ 0 , 0 \right]$ 的分布比例。

研究者提出了很多完整信息矩阵的估计方法，主要有：完整的经验交叉相乘信息矩阵(Liu et al.，2021;Philipp et al.，2018；刘彦楼 等,2016)、完整的观察信息矩阵(observedinformation matrix;Liu et al.,2021；刘彦楼 等,2016)、完整的三明治信息矩阵(sandwich-typeinformation matrix;Liu,Xin et al.,2019;Liu et al.,2021)等。由于考虑所有模型参数，完整信息矩阵的计算量较大，尤其是观察信息矩阵以及三明治信息矩阵涉及观察数据的对数似然函数关于所有模型参数的二阶偏导，计算量非常大。本文采用观察数据对数似然函数关于项目参数8和结构参数 $\pmb { \pi }$ 的一阶导向量交叉相乘而计算的 XPD 矩阵：

$$
\mathcal { T } _ { \mathrm { x p D } } = \left[ \begin{array} { c c c } { \displaystyle \frac { \partial \ell ( { \bf x } ) } { \partial \delta _ { 1 } } \times \frac { \partial \ell ( { \bf x } ) } { \partial \delta _ { 1 } } } & { \displaystyle \ldots } & { \displaystyle \frac { \partial \ell ( { \bf x } ) } { \partial \delta _ { 1 } } \times \frac { \partial \ell ( { \bf x } ) } { \partial \pi _ { L - 1 } } } \\ { \vdots } & { \ddots } & { \vdots } \\ { \displaystyle \frac { \partial \ell ( { \bf x } ) } { \partial \pi _ { L - 1 } } \times \frac { \partial \ell ( { \bf x } ) } { \partial \delta _ { 1 } } } & { \displaystyle \ldots } & { \displaystyle \frac { \partial \ell ( { \bf x } ) } { \partial \pi _ { L - 1 } } \times \frac { \partial \ell ( { \bf x } ) } { \partial \pi _ { L - 1 } } } \end{array} \right]
$$

在构建Wald统计量之前，本研究首先对XPD矩阵做了以下三个方面的处理：

(1)对 XPD 矩阵求逆，获得方差—协方差矩阵 $\pmb { \Sigma } _ { \mathrm { X P D } }$ ，即： $\pmb { \Sigma } _ { \mathrm { X P D } } = \pmb { \mathrm { Z } } _ { \mathrm { X P D } } ^ { - 1 }$ 。选取 $\pmb { \Sigma } _ { \mathrm { X P D } }$ 中项目$j$ 对应方差—协方差矩阵 $\Sigma _ { j }$ 。

(2)采用 $\mathbf { M } _ { j }$ 矩阵(dela Torre,2011)通过矩阵乘法将项目参数的方差—协方差矩阵 $\Sigma _ { j }$ ，转换为项目正确作答概率的方差—协方差矩阵 ${ \bf V } _ { ( \mathrm { X P D } ) j }$ ，即： ${ \bf V } _ { ( \mathrm { X P D } ) j } = { \bf M } _ { j } \times { \bf \Sigma } _ { j }$ 。 $\mathbf { M } _ { j }$ 矩阵是$2 ^ { K _ { j } ^ { * } } \times 2 ^ { K _ { j } ^ { * } }$ 维的矩阵，表示项目 $j$ 中各个属性掌握模式与项目参数之间的对应关系，可以将项目参数转换为各个属性掌握模式下的正确作答概率。例如，假设项目 $j$ 中 $\boldsymbol { K } _ { j } ^ { * } { = } 2$ ，则对于饱和G-DINA模型而言该项目的 $\mathbf { M } _ { j }$ 矩阵可以表示为：

$$
\mathbf { M } _ { j [ 4 \times 4 ] } = { \left[ \begin{array} { l l l l } { 1 } & { 0 } & { 0 } & { 0 } \\ { 1 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 0 } & { 1 } & { 0 } \\ { 1 } & { 1 } & { 1 } & { 1 } \end{array} \right] }
$$

通过 $\mathbf { M } _ { j }$ 矩阵，可以获得该项目中各个属性掌握模式下的正确作答概率向量 ${ \bf p } _ { j } ( { \bf a } )$ ：

$$
\begin{array} { r } { \mathbf { p } _ { j } ( \mathbf { a } ) = \left[ \begin{array} { c c c c } { 1 } & { 0 } & { 0 } & { 0 } \\ { 1 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 0 } & { 1 } & { 0 } \\ { 1 } & { 1 } & { 1 } & { 1 } \end{array} \right] \times \left[ \begin{array} { c } { \delta _ { j 0 } } \\ { \delta _ { j 1 } } \\ { \delta _ { j 2 } } \\ { \delta _ { j 1 2 } } \end{array} \right] = \left[ \begin{array} { c } { \delta _ { j 0 } } \\ { \delta _ { j 0 } + \delta _ { j 1 } } \\ { \delta _ { j 0 } + \delta _ { j 2 } } \\ { \delta _ { j 0 } + \delta _ { j 1 } + \delta _ { j 2 } + \delta _ { j 1 2 } } \end{array} \right] } \end{array}
$$

根据统计学中模型参数方差—协方差矩阵的性质(或参考Li&Wang,2015)，可以通过 $\mathbf { M } _ { j }$ 矩阵将项目参数的方差—协方差矩阵 $\Sigma _ { j }$ 转换为项目正确作答概率的方差—协方差矩阵 ${ \bf V } _ { ( \mathrm { X P D } ) j }$ 。因此，基于XPD 矩阵构建Wald统计量的形式为：

$$
\operatorname { W a l d } _ { ( \operatorname { X P D } ) } = \left[ \mathbf { R } \times \mathbf { p } _ { j } ( \mathbf { a } ) \right] ^ { \prime } \left( \mathbf { R } \times \mathbf { V } _ { ( \operatorname { X P D } ) j } \times \mathbf { R } ^ { \prime } \right) ^ { - 1 } \left[ \mathbf { R } \times \mathbf { p } _ { j } ( \mathbf { a } ) \right] ^ { - 1 }
$$

(3)对比完整和不完整信息矩阵可知，完整信息矩阵考虑模型中的全部参数，计算量较大，修正过程较为耗时。故本研究采用 $\mathrm { C } { + } { + }$ 语言编写 XPD 矩阵，提高 $\mathbf { Q }$ 矩阵修正的速度。

# 3.2 Wald-XPD方法的具体实施步骤

Wald-XPD方法用于Q矩阵修正是逐个项目进行的。假设项目 $j$ 的 $\mathbf { q }$ 向量的集合是由单一属性构成的。A是所需属性的集合，B是需要修正的目标属性的集合，修正之初， $\mathbf { A } = \varnothing$ ，$\mathbf { B } = \left\{ 1 , 2 , . . . , K \right\} \circ$ （204

![](images/e220830cf089b30e1f161751cedbc4f5192d1effbc5cee79489a4101fde579d8.jpg)  
图2Wald-XPD方法用于 ${ \bf q } _ { j }$ 向量的修正流程图

本研究新提出的Wald-XPD方法的修正步骤如下：

步骤(1):选择项目 $j$ 中具有最大PVAF值的单一属性q向量中包含的属性为第一个所需属性，更新集合A、B。

步骤(2)：将该单一属性q向量的PVAF值与0.95进行比较，大于0.95说明该q向量是合适的，停止修正，否则继续修正。

步骤(3)：更新集合A、B。选出具有较大PVAF的 $\mathbf { q }$ 向量进行修正，将该q向量中各属性使用Wald-XPD 统计量进行显著性检验，确定该 $\mathbf { q }$ 向量对应的集合A和集合B中的属性是否应该移除或添加，然后判断q向量的PVAF是否大于0.95，大于0.95说明这个 $\mathbf { q }$ 向量是合适的，停止修正，否则继续修正。

步骤(4)：重复步骤(3)，直到某个 $\mathbf { q }$ 向量的PAVF值大于0.95，或者没有属性移除或添加则停止修正。

步骤(5)：在单个项目修正结束后，重新计算PVAF以及Wald-XPD 统计量，直到达到最大迭代或者某次迭代结束后的 $\mathbf { q }$ 向量与前一次迭代的 $\mathbf { q }$ 向量完全相等则停止修正。

为了便于理解，现举例说明Wald-XPD方法用于某个项目的q向量的修正算法。假设项目 $j$ 中 $\mathbf { q }$ 向量的属性数 $K = 3$ ，Wald-XPD方法修正该 $\mathbf { q }$ 向量的过程如图2所示。

# 4模拟研究

模拟研究的目的是在较为广泛和真实的条件下探讨Wald-XPD方法在Q矩阵修正中的表现，并与以往研究者提出的GDI、Wald-IC 以及Hull(HulIP、HulIR)方法进行比较。

# 4.1方法

# 4.1.1研究设计

为便于比较，本研究参考以往研究设计(Ma&de la Torre,2020;Na'jera et al.,2021)，共操纵了5种因素:项目数和属性数的比例(ratio ofnumber of items to attribute, $J K )$ 、样本量 $( N )$ 、Q矩阵错误设定的比例(Q-matrix misspecification rate, $Q M )$ 、属性分布(attribute distribution,$A D )$ 、项目质量(itemquality, $I Q )$ 。本研究将属性数设置为 $K { = } 4$ ，因为这是应用类文章中最经常出现的属性数(Na'jera et al.,2020)。以往研究中常用的项目数是11到30(Sessoms&Henson,2018)，故本研究将项目数设置为16和 32，所以，本研究共考虑2种测验结构：$J = 1 6 { \Big [ } { \big ( } K = 4 { \big ) } \times { \big ( } J K = 4 { \big ) } { \Big ] } , J = 3 2 { \Big [ } { \big ( } K = 4 { \big ) } \times { \big ( } J K = 8 { \big ) } { \Big ] }$ 。样本量有两个水平：500和1000(Chen,2017; de la Torre,2011;Ma& dela Torre,2016)，分别代表小样本和大样本。本研究共有 48 个实验条件，各因素水平如表1所示。

表1模拟研究中各因素水平汇总  

<html><body><table><tr><td>因素</td><td>因素水平</td></tr><tr><td>样本量N</td><td>500、1000</td></tr><tr><td>项目数和属性数的比例JK</td><td>4、8</td></tr><tr><td>属性数K</td><td>4</td></tr><tr><td>平均项目质量IQ</td><td>0.4、0.6、0.8</td></tr><tr><td>属性分布AD</td><td>均匀分布、高阶分布</td></tr><tr><td>错误设定的比例QM</td><td>0.15、0.3</td></tr><tr><td>链接函数</td><td>G-DINA 模型</td></tr><tr><td>Q矩阵修正方法</td><td>GDI、Wald-IC、Hull(HullP、HullR)、Wald-XPD</td></tr></table></body></html>

# 4.1.2数据生成

被试的属性掌握模式从两种分布中产生：均匀分布和高阶分布(de la Torre& Douglas,2004)。对于均匀分布，每个被试的属性掌握模式是从所有可能的属性掌握模式中以相等的概率随机生成的；对于高阶分布，被试的能力 $( \theta )$ 来自于标准正态分布，属性难度参数 $\delta _ { k }$ 在[-1.5,1.5]之间给出等距值(Ma& de la Torre,2020)

项目质量分为高、中、低3个水平。高项目质量： $P _ { j } \left( 0 \right) \sim U ( 0 , 0 . 2 )$ 且 $P _ { j } \left( 1 \right) \sim U ( 0 . 8 , 1 )$ 中等项目质量： $P _ { j } \left( 0 \right) \sim U ( 0 . 1 , 0 . 3 )$ 且 $P _ { j } \left( 1 \right) \sim U ( 0 . 7 , 0 . 9 )$ ；低项目质量： $P _ { j } \left( 0 \right) \sim U ( 0 . 2 , 0 . 4 )$ 且$P _ { j } \left( 1 \right) \sim U ( 0 . 6 , 0 . 8 )$ 。其中， $P _ { j } \left( 0 \right)$ 表示仅凭猜测答对的概率， $P _ { j } \left( 1 \right)$ 表示掌握项目所要求的全部属性的被试答对该项目的概率。成功的概率有两种限制：(1)项目反应函数在属性数上具有单调性；(2)与单个属性相联系的项目参数的总和限制为大于0.15。这两个条件保证所有的属性都具有不可忽视的作用。

真实Q矩阵符合以下限制：(1)每个Q矩阵至少包含两个单位矩阵(identity matrix)；(2)除了两个单位矩阵外，每个项目至少测量一个属性；(3)Q矩阵由一个属性 $\mathbf { q }$ 向量 $( 5 0 \% )$ 、两个属性q向量 $( 2 5 \% )$ 和三个属性 $\mathbf { q }$ 向量 $( 2 5 \% )$ 组成。这个比例主要是参考之前研究(Na'jera etal.,2021)，使用较高比例的单一属性 $\mathbf { q }$ 向量的原因是满足每个Q矩阵至少包含两个单位矩阵的模型可识别条件(Guetal.,2018)。错误设定的Q矩阵的比例为：0.15 和0.3。错误设定是在两个约束条件下随机引入：(1)所有项目必须至少测量一个属性；(2)始终保留一个单位

矩阵。

在每个条件下，均生成 500个数据集，每个数据集中生成新的真实Q矩阵和项目参数。所有的模拟研究和分析都在R软件中进行。

# 4.1.3评价指标

QRR(Q-matrixrecoveryrate)用来测量Q矩阵的恢复比例，可以表示为：

$$
\mathrm { Q R R } = \frac { \displaystyle \sum _ { J = 1 } ^ { J } \sum _ { k = 1 } ^ { K } I \Big ( q _ { j k } ^ { ( s ) } = q _ { j k } ^ { ( t ) } \Big ) } { J \times K }
$$

其中， $I ( \bullet )$ 是指示函数，若修正前后项目 $j$ 的 $\textbf { q }$ 向量完全一致，则 $I \big ( q _ { j k } ^ { ( s ) } = q _ { j k } ^ { ( t ) } \big ) = 1$ ，否则$I \Big ( q _ { j k } ^ { ( s ) } = q _ { j k } ^ { ( t ) } \Big ) { = } 0$ 。 $q _ { j k } ^ { ( s ) }$ 和 $q _ { j k } ^ { ( t ) }$ 分别表示项目 $j$ 中属性 $k$ 的建议 $q$ 元素和真实 $q$ 元素。

TPR(truepositiverate)表示保留正确标定属性的比例：

$$
\mathrm { T P R } = \frac { \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { k = 1 } ^ { K } I \left( q _ { j k } ^ { ( s ) } = q _ { j k } ^ { ( t ) } \mid q _ { j k } ^ { ( o ) } = q _ { j k } ^ { ( t ) } \right) } { \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { k = 1 } ^ { K } I \left( q _ { j k } ^ { ( o ) } = q _ { j k } ^ { ( t ) } \right) }
$$

其中， $q _ { j k } ^ { ( o ) }$ 表示项目 $j$ 中属性 $k$ 的原始 $q$ 元素。

TNR(truenegativerate)表示修正错误标定属性的比例：

$$
\mathrm { T N R } = \frac { \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { k = 1 } ^ { K } I \left( q _ { j k } ^ { \left( s \right) } = q _ { j k } ^ { \left( t \right) } \mid q _ { j k } ^ { \left( o \right) } \neq q _ { j k } ^ { \left( t \right) } \right) } { \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { k = 1 } ^ { K } I \left( q _ { j k } ^ { \left( o \right) } \neq q _ { j k } ^ { \left( t \right) } \right) }
$$

本研究除了使用QRR、TPR、TNR 来考察各个方法总体的表现之外，还参考其他指标来获得更加全面具体的结果。OS 表示过度设定，US(under-specifications)表示吝啬设定，表达式分别为：

$$
\mathrm { O S } = \sum _ { j = 1 } ^ { J } \sum _ { k = 1 } ^ { K } I \left( q _ { j k } ^ { ( s ) } > q _ { j k } ^ { ( t ) } \right)
$$

$$
\mathrm { U S } = \sum _ { j = 1 } ^ { J } \sum _ { k = 1 } ^ { K } I \left( q _ { j k } ^ { ( s ) } < q _ { j k } ^ { ( t ) } \right)
$$

以上五个指标从不同方面反映了Q矩阵的修正效果。其中，QRR、TPR、TNR的值越高，表示该修正方法的Q矩阵恢复率以及保留正确标定属性和修正错误标定属性的比例越高，修正效果越好。OS 和US 的值越小，表示该修正方法存在较少过度设定和吝啬设定的趋势，修正效果越好。

# 4.2 研究结果

4.2.1 GDI、Hull、Wald-IC以及Wald-XPD在各因素不同水平上的表现

表2呈现了GDI、Hull(HulIP、HullR)、Wald-IC 以及Wald-XPD 方法在各因素不同水平上的QRR、TPR、TNR、OS 和US 值，表中加粗数据是相同条件下的最优结果。

首先，比较的是各实验条件的综合影响。Q矩阵错误设定的比例、项目质量、样本量以及属性分布对于GDI、Wald-IC、Hull(HulIP、HulIR)以及Wald-XPD 方法在各个指标上的表现有明显影响。除 Hull(HulIP、HulIR)方法的 TPR 指标受项目质量的影响较小外，在项目质量较高的条件下，所有方法的表现均优于其他水平。Q矩阵错误设定的比例和样本量对于四种方法在各个指标上的表现也存在一定的影响，随着Q矩阵错误设定的比例降低和样本量增大，四种方法均有更好的Q矩阵修正表现。均匀分布下，四种方法在各个指标上的表现均优于高阶分布。就JK 因素而言，JK 对于GDI、Wald-IC 和 Wald-XPD在QRR 指标上的表现，以及所有的修正方法在TNR指标上的表现影响明显，所有指标在 $J K { = } 8$ 水平下的结果优于 $J K { = } 4$ 。

其次，比较的是四种修正方法的综合表现。所有方法在QRR以及TPR指标上没有表现出明显优劣。其中，本研究中新提出的Wald-XPD在 TNR 指标上的表现明显优于其他方法;GDI在OS 指标上的表现较优，但是在US 指标上表现相对较差；HulIR在OS 指标上的表现较差，但是在US 指标上表现相对较优；Wald-IC在US指标上表现相对较差。

根据以上综合比较可知，Wald-XPD以及HulIP 在各个指标上有相对较好的表现，且在TNR 指标上Wald-XPD 的表现最好。此外，鉴于Wald-XPD 是在Wald-IC 基础上新提出的方法，故接下来本研究主要探讨 Wald-XPD、Wald-IC 以及HulIP 方法在QRR、TPR 以及 TNR这三个主要指标上的具体表现，并重点关注Wald-XPD 在TNR 指标上的表现，即 Wald-XPD修正Q矩阵中错误标定属性的能力。

# 4.2.2Wald-XPD在修正错误标定属性时的表现

图3呈现的是HullP、Wald-IC 以及Wald-XPD 方法在 48 种具体的模拟条件下获得的QRR 的值。由图3可知，项目质量对于这三种方法的表现影响最为明显，随着项目质量的提高，QRR 的值也在增加。另外，样本量、Q矩阵错误设定的比例以及属性分布对于这三个方法在QRR 指标上的表现稍有影响，且趋势一致。就QRR 指标而言，HulIP、Wald-IC 以及Wald-XPD方法的表现仅有细微差异，即当 $I Q { = } 0 . 4$ 时Wald-XPD 的表现略微低于另外两种方法。

表2不同因素水平的结果  

<html><body><table><tr><td colspan="4">QM</td><td colspan="2">10</td><td colspan="2">N</td><td colspan="2">JK</td><td colspan="2">AD</td></tr><tr><td>QRR</td><td>方法</td><td>0.15</td><td>0.3</td><td>0.4</td><td>0.6</td><td>0.8</td><td>500</td><td>1000</td><td>4</td><td>8</td><td>均匀分布</td><td>高阶分布</td></tr><tr><td rowspan="5"></td><td>GDI</td><td>0.906</td><td>0.828</td><td>0.859</td><td>0.922</td><td>0.945</td><td>0.922</td><td>0.922</td><td>0.906</td><td>0.930</td><td>0.938</td><td>0.906</td></tr><tr><td>Wald-IC</td><td>0.945</td><td>0.813</td><td>0.844</td><td>0.922</td><td>0.969</td><td>0.906</td><td>0.938</td><td>0.891</td><td>0.930</td><td>0.938</td><td>0.906</td></tr><tr><td>HullP</td><td>0.930</td><td>0.852</td><td>0.875</td><td>0.945</td><td>0.953</td><td>0.938</td><td>0.953</td><td>0.938</td><td>0.945</td><td>0.953</td><td>0.930</td></tr><tr><td>HullR</td><td>0.891</td><td>0.797</td><td>0.844</td><td>0.891</td><td>0.922</td><td>0.898</td><td>0.906</td><td>0.906</td><td>0.906</td><td>0.914</td><td>0.891</td></tr><tr><td>Wald-XPD</td><td>0.937</td><td>0.867</td><td>0.820</td><td>0.938</td><td>0.969</td><td>0.906</td><td>0.953</td><td>0.906</td><td>0.945</td><td>0.953</td><td>0.906</td></tr><tr><td rowspan="8">TPR TNR</td><td>GDI</td><td>0.944</td><td>0.922</td><td>0.933</td><td>0.936</td><td>0.953</td><td>0.936</td><td>0.945</td><td>0.944</td><td>0.936</td><td>0.954</td><td>0.926</td></tr><tr><td>Wald-IC</td><td>0.945</td><td>0.933</td><td>0.908</td><td>0.954</td><td>0.969</td><td>0.933</td><td>0.956</td><td>0.944</td><td>0.945</td><td>0.956</td><td>0.938</td></tr><tr><td>HullP</td><td>0.963</td><td>0.936</td><td>0.963</td><td>0.961</td><td>0.956</td><td>0.953</td><td>0.969</td><td>0.963</td><td>0.956</td><td>0.967</td><td>0.953</td></tr><tr><td>HullR</td><td>0.936</td><td>0.911</td><td>0.953</td><td>0.927</td><td>0.930</td><td>0.927</td><td>0.944</td><td>0.956</td><td>0.922</td><td>0.944</td><td>0.926</td></tr><tr><td>Wald-XPD</td><td>0.944</td><td>0.900</td><td>0.835</td><td>0.944</td><td>0.969</td><td>0.917</td><td>0.953</td><td>0.920</td><td>0.944</td><td>0.953</td><td>0.927</td></tr><tr><td>GDI</td><td>0.800</td><td>0.684</td><td>0.421</td><td>0.789</td><td>0.900</td><td>0.711</td><td>0.737</td><td>0.579</td><td>0.842</td><td>0.800</td><td>0.684</td></tr><tr><td>Wald-IC</td><td>0.789</td><td>0.579</td><td>0.405</td><td>0.700</td><td>0.900</td><td>0.632</td><td>0.684</td><td>0.526</td><td>0.789</td><td>0.700</td><td>0.632</td></tr><tr><td>HullP</td><td>0.800</td><td>0.684</td><td>0.368</td><td>0.833</td><td>0.947</td><td>0.737</td><td>0.800</td><td>0.600</td><td>0.895</td><td>0.816</td><td>0.700</td></tr><tr><td>OS</td><td>HullR</td><td>0.684</td><td>0.579</td><td>0.263 0.676</td><td>0.895</td><td>0.600</td><td>0.632</td><td>0.421</td><td>0.763</td><td>0.684</td><td></td><td>0.579</td></tr><tr><td rowspan="6"></td><td>Wald-XPD</td><td>0.900</td><td>0.816</td><td>0.684</td><td>0.900</td><td>0.947</td><td>0.840</td><td>0.894</td><td>0.700</td><td>0.920</td><td>0.900</td><td>0.830</td></tr><tr><td>GDI</td><td>0</td><td>3</td><td>3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>Wald-IC</td><td>1</td><td>5</td><td>3</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td></tr><tr><td>HullP</td><td>1</td><td>5</td><td>5</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>HullR</td><td>8</td><td>11</td><td>9</td><td>9</td><td>6</td><td>8</td><td>8</td><td>5</td><td>11</td><td>7</td><td>8</td></tr><tr><td>Wald-XPD</td><td>1</td><td>3</td><td>4</td><td>1</td><td>0</td><td>2</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td rowspan="6">US</td><td>GDI</td><td>7</td><td>10</td><td>9</td><td>7 5</td><td>7</td><td>6</td><td>5</td><td>9</td><td></td><td>5</td><td>8</td></tr><tr><td>Wald-IC</td><td>6</td><td>10</td><td>11</td><td>6</td><td>3</td><td>8</td><td>5</td><td>5</td><td>8</td><td>5</td><td>7</td></tr><tr><td>HullP</td><td>5</td><td>8</td><td>6</td><td>5</td><td>4</td><td>5</td><td>4</td><td>3</td><td>6</td><td>4</td><td>6</td></tr><tr><td>HullR</td><td>2</td><td>5</td><td>5</td><td>2</td><td>1</td><td>2</td><td>1</td><td>1</td><td>2</td><td>1</td><td>2</td></tr><tr><td>Wald-XPD</td><td>5</td><td>8</td><td>12</td><td>4</td><td>3</td><td>7</td><td>5</td><td>5</td><td>6</td><td>4</td><td>7</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

注：粗体表示各指标不同水平下的最好结果

![](images/d0728576ffb9e27457e5b91f9e2ca29bb9d6afd8671c0905e48274efe344bfb8.jpg)  
图3HulIP、Wald-IC与Wald-XPD方法在QRR指标上的表现

![](images/d047e87af25f0987b8d27d29c0cabe0736dc2bb1d9a2031cef8da511b6a16496.jpg)  
图4HulIP、Wald-IC与Wald-XPD方法在TPR指标上的表现

![](images/3d7719744ad5270a4eff1098d6a77cccae3dec665008f8846efbbdc28e4ef79d.jpg)  
图5HulIP、Wald-IC与Wald-XPD方法在TNR指标上的表现

图4呈现的是三种方法在TPR指标上的表现。由图4可知，在所有条件下Wald-IC以及HulIP方法均能获得较高的TPR值。项目质量对于Wald-XPD方法的表现有一定的影响，当项目质量较低时，Wald-XPD在TPR指标上的表现不如Wald-IC 以及HulIP方法；随着项目质量的提高，三种方法在TPR指标上的表现相当。

图5呈现的是三种方法在TNR指标上的表现。在所有条件下，Wald-XPD方法在TNR指标上的表现均是最优的，对比Wald-XPD方法在TPR及TNR上的表现可知，低项目质量条件对这个方法产生了一些不利影响，而在中等或高项目质量条件下，Wald-XPD 能有效保留Q矩阵中正确标定的属性，也能有效修正Q矩阵中错误标定的属性。测验长度较短、项目质量较低及Q矩阵错误设定比例较高时HulIP方法的表现较差，结合同样条件下HulIP 在TPR 指标上的表现可知，虽然HulIP方法在保留正确标定属性方面略微优于Wald-XPD，但是它较多地保留了错误标定的属性。即,HulIP方法倾向于较少地修正原始Q矩阵中的属性。在低项目质量条件下的多数情景中，虽然Wald-IC 方法在TNR上的表现优于HulIP，但是在随着项目质量的提高HulIP 在多数情景中的表现优于Wald-IC。HulIP、Wald-IC 以及Wald-XPD 方法在TNR 指标上的表现受样本量、测验长度、项目质量、属性分布及错误设定比例的影响明显。随着Q矩阵错误设定比例降低、项目质量提高、测验长度增加，HulIP 和 Wald-

IC方法的TNR值有所提高，但仍低于Wald-XPD方法的TNR值。

# 5实证数据分析

本研究采用实证数据进一步考察Wald-XPD方法的表现，并与HulIP、Wald-IC 方法进行比较。被试反应数据及测验项目获取自R软件包pks (Heller&Wickelmaier,2013)，来自德国图宾根(Tuebingen)大学的一个学习实验，包含 504 名被试在12 个概率论测验项目上的作答。Philipp 等人(2018)认为这个数据集共测试了四种不同的属性： $\alpha _ { \mathrm { { 1 } } }$ (计算某事件发生概率)、 $\alpha _ { 2 }$ (计算某事件的对立事件发生的概率)、 $\alpha _ { 3 }$ (计算两个无关事件同时发生的概率) $\alpha _ { 4 }$ (计算两个独立事件发生的概率)，并定义了表3所示的原始Q矩阵。

表3原始Q矩阵以及各方法对属性的修正情况  

<html><body><table><tr><td rowspan="2">项目</td><td colspan="4">原始Q矩阵</td></tr><tr><td>a</td><td>a2</td><td>a3</td><td>α4</td></tr><tr><td>1</td><td></td><td>0</td><td>0</td><td>0</td></tr><tr><td>2</td><td>0</td><td>1*</td><td>0*</td><td>0</td></tr><tr><td>3</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>4</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>5</td><td>1*</td><td>1</td><td>0</td><td>0</td></tr><tr><td>6</td><td>1*</td><td>1</td><td>0</td><td>0</td></tr><tr><td>7</td><td>1*</td><td>0*</td><td>1*</td><td>0</td></tr><tr><td>8</td><td>1*</td><td>0*</td><td>1</td><td>0*</td></tr><tr><td>9</td><td>1</td><td>0</td><td>0</td><td>1*#^</td></tr><tr><td>10</td><td>0</td><td>1*#^</td><td>0</td><td>1</td></tr><tr><td>11</td><td>1*#></td><td>1*#^</td><td>0</td><td>1</td></tr><tr><td>12</td><td>1*</td><td>0</td><td>1*#^</td><td>1</td></tr></table></body></html>

注：\*为Wald-XPD 方法调整的属性，#为Wald-IC方法调整的属性，^为HulP 方法调整的属性

本研究在饱和G-DINA模型框架下，使用HulIP、Wald-IC 以及Wald-XPD方法对原始Q矩阵进行了修正。表3中的结果显示，HulP 方法共修正了6个元素，Wald-IC 方法共修正了5个元素，Wald-XPD方法一共修正了16个元素，Wald-IC方法修正的5个元素均包括在 Wald-XPD方法修正的元素之中。使用相对拟合、绝对拟合及近似拟合指标比较原始Q矩阵、HulIP、Wald-IC及Wald-XPD方法修正后的Q矩阵的模型—数据拟合表现。拟合指标包括：相对拟合指标 AIC (Akaike information criterion)和 BIC (Bayesian information criterion)、有限信息绝对拟合(limited-information absolute fit)指标 $M _ { 2 }$ 及近似拟合指标 RMSEA2 (rootmean square error of approximation;Liu et al.,2016)，结果见表 4。就相对拟合指标而言， $\mathbf { Q } _ { \mathrm { H u l l P } }$ 获得最佳的 AIC 指标， $\mathbf { Q } _ { \mathrm { X P D } }$ 的 AIC 指标与其接近; $\mathbf { Q } _ { \mathrm { X P D } }$ 获得最佳的 BIC 指标，其次是 $\mathbf { Q } _ { \mathrm { I C } }$ $\mathbf { Q } _ { \mathrm { H u l l P } }$ 的 BIC 指标最差。即，Wald-XPD方法修正后的Q矩阵的相对拟合指标更优。在绝对拟合指标 $M _ { 2 }$ 上， $\mathbf { Q } _ { \mathrm { I C } }$ 的 $p { < } 0 . 0 1$ ，表明 Wald-IC 方法修正的Q矩阵与数据失拟; $\mathbf { Q } _ { \mathrm { H u l l P } }$ 和QxPD的 $p$ 值分别为：0.029 和0.019，表明 HulIP 和Wald-XPD方法修正后的Q矩阵没有在0.01显著性水平上拒绝模型—数据拟合的原假设。对于RMSEA2指标而言，其值越接近0 修正效果越好，其中 $\mathbf { Q } _ { \mathrm { X P D } }$ 的RMSEA2最接近于0，即QxPD 在RMSEA2指标上有最好的表现(Liuetal.,2016)。综合考虑相对拟合、绝对拟合和近似拟合指标，本研究认为Wald-XPD 方法修正后的Q矩阵在模型一数据拟合方面表现最优。

需要特别说明的是，本研究的目的是在一般性的CDM框架下开发具有广泛适用性的Q矩阵修正方法。因此，实证数据分析的重点是原始Q矩阵的修正，没有在饱和G-DINA 模型的基础上进一步在项目水平上进行模型比较(Liu,Andersson,etal.,2019)。另外， $M _ { 2 }$ 统计量在模型参数过度设定时，即模型中冗余参数过多时，可能存在统计检验力不足的问题(参考Chen et al.,2018)。举例而言，对比原始 $\mathbf { Q } _ { \mathrm { o r i g i n a l } }$ 矩阵及修正后的 $\mathbf { Q } _ { \mathrm { X P D } }$ 矩阵可知， $\mathbf { Q } _ { \mathrm { o r i g i n a l } }$ 中可能存在较多过度设定的元素，因此，导致 $\mathbf { Q } _ { \mathrm { o r i g i n a l } }$ 的 $M _ { 2 }$ 统计量的 $p$ 值大于0.01。参考先前研究(Liu etal.,2016)，本文认为在模型—数据拟合评价方面，近似拟合统计量RMSEA2可能更具参考价值。

根据表3的结果可知，Wald-XPD方法修正的属性中，对 $\alpha _ { \mathrm { _ 1 } }$ 修正最多，共修正6个题目，均是将 $\alpha _ { \mathrm { _ 1 } }$ 从1变成0。例如，第6题"一个盒子包含 20个以下颜色的大理石：4个白色，14个绿色，2个红色。随机抽取的大理石不是白色的概率是多少？"解决这个问题可以先计算出该事件的对立事件发生的概率 $( \alpha _ { 2 } ^ { \cdot }$ )，即随机抽取的大理石是白色的概率，然后再用1减去该对立事件发生的概率即可得出正确结论。对于5、6、7题来说，当被试掌握 $\alpha _ { 2 }$ 时即能够解决问题，故 $\alpha _ { \mathrm { _ 1 } }$ 不是必需的。再如，第11题"车库里有50 辆车。20 辆是黑色的，10 辆是柴油动力的。假设汽车的颜色与燃料种类无关。随机选择的汽车不是黑色的，而是柴油动力的概率是多少？"题中汽车颜色与燃料种类是独立事件，计算随机选择的汽车不是黑色的而是柴油动力的概率即两个独立事件发生的概率 $( \alpha _ { 4 } )$ ，当被试掌握 $\alpha _ { 4 }$ 时即能够解决问题，故 $\alpha _ { \mathrm { _ 1 } }$ 不是必需的。在5、6、7、8、11、12这6道题中， $\alpha _ { \mathrm { { 1 } } }$ 不是必需的，Wald-XPD 方法均正确修正了错误标定的 $\alpha _ { \mathrm { { _ 1 } } }$ 。所以说，使用Wald-XPD 修正方法获得的 $\mathbf { Q } _ { \mathrm { X P D } }$ 矩阵在理论上具有合理性。

值得注意的是，本研究中提出的Q矩阵修正方法是从作答数据出发的，在一定程度上可以避免专家标定Q矩阵的主观性，减轻专家负担，但是客观方法标定的Q矩阵不能直接作为最终的Q矩阵，应该作为专家标定Q矩阵的重要参考(Xu& Shang,2018)。

表4基于三种方法修正前后Q矩阵的拟合指标  

<html><body><table><tr><td rowspan="2">Q</td><td colspan="2">相对拟合指标</td><td colspan="4">有限信息拟合指标</td></tr><tr><td>AIC</td><td>BIC</td><td></td><td>M2</td><td></td><td>RMSEA2</td></tr><tr><td>Qoriginal</td><td>4979.256</td><td>5245.278</td><td>M2</td><td>df</td><td>p</td><td></td></tr><tr><td>QxPD</td><td>4962.484</td><td>5152.500</td><td>23.919 51.991</td><td>15 33</td><td>0.067 0.019</td><td>0.0343 0.0338</td></tr><tr><td>QIC</td><td>4964.200</td><td>5171.110</td><td>50.051</td><td>29</td><td>0.009</td><td>0.0380</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>QHullP</td><td>4954.912</td><td>5178.709</td><td>40.037</td><td>25</td><td>0.029</td><td>0.0345</td></tr></table></body></html>

# 6讨论与展望

# 6.1 结论与讨论

CDM 依赖正确设定的Q矩阵以获得准确的属性剖面分类(Rupp& Templin,2008)。以往研究者提出的GDI、Wald-IC、Hull方法在多数的应用情景中虽然有较好的表现，但这些方法对Q矩阵中错误标定的属性不够敏感。本研究提出使用完整的 XPD 矩阵计算用于Q 矩阵修正的方法(Wald-XPD 方法)，并系统探讨了样本量、测验长度、Q矩阵错误设定比例、属性分布等因素对Q矩阵修正结果的影响。采用实证数据展示了新提出的Wald-XPD 方法在实际应用中的表现与价值。

本研究结果表明：(1)整体而言，Wald-XPD 方法的表现优于GDI、Hull、Wald-IC 方法。Wald-XPD 方法能够弥补GDI、Hull、Wald-IC 方法在一些条件下对于错误标定属性不敏感的不足之处，且在Q矩阵恢复率和保留正确标定属性的比例方面也有较好的表现。(2)GDI、Hull、Wald-IC 和 Wald-XPD 方法随着项目质量的提高、样本量增大、测验长度增加以及Q矩阵错误设定比例的降低，在修正Q矩阵上有更好的表现。(3)由HulIP、Wald-IC 以及Wald-XPD 方法进一步比较的结果可知，三种方法在Q矩阵恢复率方面差异较小，HulIP、Wald-IC 在保留正确标定的属性方面的表现略优于Wald-XPD方法，但在所有模拟条件下，Wald-XPD 方法在修正错误标定的属性方面的表现均优于另外两种方法。(4)实证数据分析的结果表明，Wald-XPD方法修正后的Q矩阵与原始数据有最优的拟合度。

在本研究操纵的5种因素中，项目质量对GDI、Hull、Wald-IC、Wald-XPD 方法表现的影响较大，样本量和测验长度也对四种修正方法的表现有一定的影响。出现这种现象的原因可能是，项目质量越高、样本量越大以及测验长度越长，被试观察作答反应矩阵中包含的关于 CDM中未知参数的信息越多，因此，以上四种方法的表现也就越好。与以往研究类似(Kang et al.,2019;Ma& de la Torre,2020; Na'jera et al.,2021)，本研究同样认为属性分布对于GDI、Hull、Wald-IC、Wald-XPD 方法在 TNR 指标上的表现有细微的影响。出现这种现象的原因可能是，当属性服从均匀分布时所有可能属性掌握模式分布的概率是相等的，即被试观察作答反应矩阵中包含的关于结构参数的信息是一样的。当属性服从高阶分布时，属性之间存在一定的关联性，使某些属性掌握模式分布的概率可能会比较高，另外一些属性掌握模式分布的概率会比较低，故被试观察作答反应矩阵中包含的结构参数的信息量较少。于是，当属性服从均匀分布时，四种方法在各个指标上的表现略优。Q矩阵错误设定的比例对GDI、Wald-IC、Hull方法表现的影响较大，随着Q矩阵错误设定比例的降低，它们能够获得更高的 QRR、TPR 和 TNR 值,这与已有研究结果一致(Ma& de la Torre,2020; Na'jera et al.,2021)。然而，Q矩阵错误设定的比例对Wald-XPD方法表现的影响则相对较小，结合Wald-XPD 在TNR 指标上的表现，本研究认为可能是Wald-XPD 在迭代结束前的循环中能够有效修正Q矩阵错误标定的属性。

此外，研究结果表明，Wald-XPD方法在TPR 和TNR 指标上与Wald-IC、HulIP方法的表现不同。在TPR 指标上，Wald-XPD受项目质量低的影响明显，在 TNR 指标上，Wald-IC和 HulIP 受项目质量低以及测验长度短的因素的影响明显。TPR 指标数值低，说明Q矩阵修正方法倾向于修改正确标定的属性，TNR数值低则说明Q矩阵修正方法修改错误标定属性的能力弱。综合 TPR、TNR 两个指标可知，虽然Wald-XPD 方法在项目质量较低的条件下能够较为有效地修正错误标定的属性，但是存在过度修改正确标定属性的倾向。换言之，Wald-XPD方法虽然提高了Q矩阵修正的表现，但是在项目质量较低的情境下，有可能会错误地修正了正确标定的 $q$ 元素。Wald-IC以及HulIP虽然在项目质量较低的条件下不存在过度修改正确标定属性的倾向，但却无法有效修正错误标定的属性，尤其是HulIP方法。所以，本研究建议使用Q矩阵修正方法时，需要注意项目质量，若项目质量较低，可以结合多种修正方法、参考专家意见进而获得准确的Q矩阵。

本研究采用 $\mathrm { C } { + } { + }$ 语言编写XPD 矩阵，在一定程度上能够提高Q矩阵修正的速度，但是，由于Wald-XPD方法考虑模型中的全部参数且采用迭代的方式进行，在一些条件下可能耗时较长。例如，Wald-XPD 方法最短的平均用时是12.50s，最长的平均时间需要 746.01s。

Wald-XPD方法在各个模拟条件下的平均运行时间参见附录中的表A1。

# 6.2 研究展望

本研究提出的Wald-XPD方法在Q矩阵修正中有较好的表现，但仍存在一些不足之处值得后续研究者进一步探讨。(1)虽然Wald-XPD 统计量有明确的渐近分布( $\chi ^ { 2 }$ 分布)，不需要像GDI类方法那样人为地确定一个截止值，但限于研究目的和篇幅本文仅在0.05 显著性水平上对于Wald-XPD 统计量的表现进行了显著性检验，未来研究者可以进一步探讨不同的显著性水平对于Wald-XPD 统计量表现的影响。(2)本研究仅以完整信息矩阵中的 XPD 矩阵构建 Wald 统计量进行Q矩阵修正，除了XPD 矩阵之外，研究者还可以将其他完整信息矩阵构建的Wald 统计量用于Q矩阵修正，如Liu 等人(2021)提出改进的观察信息矩阵以及三明治信息矩阵。不同类型的完整信息矩阵构建的Wald统计量在Q矩阵修正中的表现也值得进一步研究。(3)本研究仅在G-DINA 模型下对Q矩阵修正方法进行了对比研究，G-DINA 模型适用于0-1计分的测验情景，但在心理与教育测验中存在较多的多级计分数据。研究者们开发了很多能用于多级计分的CDM，如多级计分GDM(von Davier,2008)，研究者可以将Wald-XPD方法拓展到多级计分模型中，并考察其在多级计分模型中的表现。(4)本研究在考察新提出的Wald-XPD方法的表现时，仅与一次修正的GDI、Wald-IC 方法进行了比较，研究者也认为GDI、Wald-IC 方法可以迭代进行，如迭代GDI方法(Na'jera et al.,2020)。此外，还有其他迭代修正的方法，如迭代修正序列搜索(Terzi&dela Torre,2018)等，研究者也可以尝试将这些方法与Wald-XPD方法进行比较。(5)Wang 等人(2020)评估了在Q矩阵部分已知的情况下，GDI和Wald-IC 方法在估计新项目的 $\mathbf { q }$ 向量中的表现。基于此，未来研究者可以在Q矩阵部分已知的情况下进一步评估Wald-XPD方法估计Q矩阵的表现，并与已有的Q矩阵估计方法，如ICC-IR方法(汪大勋，高旭亮，蔡艳 等,2018)、似然比 $\mathrm { D } ^ { 2 }$ 方法(喻晓锋 等,2015)、非参数Q矩阵校准(Lim&Drasgow,2017)、两阶段搜索算法(Feng,2013)、似然比检验(Wang et al.,2020)等方法进行比较。

# 参考文献

Chen,F.,Liu, Y.,Xin,T.,& Cui,Y. (2018).Applying the $M _ { 2 }$ statistic to evaluate the fit of diagnostic classification models in the presence of atribute hierarchies.Frontiers in Psychology, 9,Article 1875.

Chen, J.(2017). Aresidual-based approach to validate Q-matrix specifications.Applied Psychological Measurement, 41(4), 277-293.   
Chen,Y.,Liu,J.,Xu, G.,& Ying,Z. (2015).Statistical analysis ofQ-matrix based diagnosticclassificationmodels. Journal of the American Statistical Association,110(510),850-866.   
Chiu,C.-Y. (2013). Statistical refinement of the Q-matrix in cognitive diagnosis. Applied Psychological Measurement, 37(8), 598-618.   
de la Torre,J. (20o8).Anempirically based method ofQ-matrix validation for the DINA model: Development and applications. Journal of Educational Measurement, 45(4),343-362.   
de la Torre,J. (2o09).DINA model and parameter estimation: A didactic. Journal of Educational and Behavioral Statistics,34(1),115-130.   
de la Torre,J. (2011).The generalized DINA model framework. Psychometrika,76(2),179-199.   
de la Torre,J.,& Chiu, C.-Y.(2016).Ageneral methodofempirical Q-matrix validation.Psychometrika,81(2),253- 273.   
de laTorre,J.,& Douglas,J.A.(2O4).Higher-order latent trait models forcognitive diagnosis.Psychometrika, 69(3),333-353.   
Feng, Y. (2013). Estimation and $\boldsymbol { \mathcal { Q } }$ -matrix validation for diagnostic classification models (Unpublished doctoral dissertation). University of South Carolina, Los Angeles, America.   
Gu,Y.,Liu,J.,Xu,G.,& Ying,Z. (2018). Hypothesis testing of theQ-matrix.Psychometrika, 83(3),515-537.   
Heler, J.，& Wickelmaier,F. (20l3). Minimum discrepancyestimation in probabilistic knowledge structures. Electronic Notes in Discrete Mathematics,42(10),49-56.   
Kang, C.H., Yang, Y.K.,& Zeng,P.H.(2019). Q-matrix refinement based on item fit statistic RMSEA. Applied Psychological Measurement, 43(7), 527-542.   
Li, J.,Mao, X.,& Wei,J. (2022). A simple and efective new method of Q-matrix validation. Acta Psychologica Sinica,54(7), 1-13.   
[李佳，毛秀珍，韦嘉.(2022)．一种简单有效的Q 矩阵修正新方法．心理学报,54(7),1-13.]   
Li, J.,Mao,X.,& Zhang,X. (2021). Q-matrix estimation (validation) methods for cognitive diagnosis.Advances in Psychological Science,29(12),2272-2280.   
[李佳，毛秀珍，张雪琴.(2021).认知诊断Q矩阵估计(修正)方法．心理科学进展,29(12),2272-2280.]   
Li,X.,& Wang,W. (2015).Assessmentofdifferential itemfunctioning under cognitive diagnosis models: The DINA model example. Journal of Educational Measurement, 52(1),28-54.   
Lim,Y.,& Drasgow,F. (2o17).Nonparametric calibrationof item-by-atribute matrix in cognitive diagnosis. Multivariate Behavioral Research, 52(5),562-575.   
Liu,J.,Xu, G.,& Ying,Z. (2012). Data-driven learning of Q-matrix. Applied Psychological Measurement, 36(7), 548-564.   
Liu,Y.,Andersson,B., Xin,T.,Zhang,H.,& Wang,L. (2019).Improved Wald statisticsfor item-level model comparison in diagnostic clasification models. Applied Psychological Measurement, 43(5), 402-414.   
Liu,Y., Tian, W., & Xin, T. (2016). An application of $M _ { 2 }$ statistic to evaluate the fit of cognitive diagnostic models. Journal of Educational and Behavioral Statistics,41(1),3-26.   
Liu,Y.,Xin,T.,Andersson,B.,&Tian, W. (2o19).Information matrix estimationprocedures forcognitivediagnostic models. British Journal of Mathematical and Statistical Psychology,72(1),18-37.   
Liu,Y.,Xin,T.,&Jiang,Y.(2O21).Structuralparameterstandarderor estimationmethodindiagnosticcassification models: Estimation and application. Multivariate Behavioral Research. Advance online publication. https://doi.0rg/10.1080/00273171.2021.1919048   
Liu,Y.,Xin,T.,Li,L.,Tian, W.,&Liu,X. (216).Animproved method fordifferential item functioningdetection in cognitive diagnosis models: An application of Wald statistic based on observed information matrix. Acta Psychologica Sinica, 48(5), 588-598.   
[刘彦楼，辛涛，李令青，田伟，刘笑笑.(2016).改进的认知诊断模型项目功能差异检验方法——基于观察 信息矩阵的Wald 统计量．心理学报,48(5),588-598.]   
Ma, W.,& de la Torre,J. (2016).Asequential cognitive diagnosis model for polytomous responses.British Journal of Mathematical and Statistical Psychology, 69(3),253-275.   
Ma,W.,& de la Torre,J. (202O).An empirical Q-matrix validation method for the sequential generalized DINA model.British Journal ofMathematical and Statistical Psychology,73(1),142-163   
McFadden,D.(1974).Conditional logit analysis of qualitative choice behavior.InP. Zarembka(Ed.),Frontiers in economics (pp. 105-142). New York, NY: Academic Press.   
N'ajera,P.,Sorrel,M.A.,& Abad,F.J. (2019). Reconsidering cutoff points inthe general method of empirical Qmatrix validation. Educational and Psychological Measurement, 79(4),727-753   
N'ajera,P.,Sorrel,M.A.,de laTrre,J.,&Abad,F.J. (202).Improvingrobustnessin Q-Matrix validationusing an iterative and dynamic procedure. Applied Psychological Measurement, 44(6), 431-446.   
N'ajera,P.,Sorrel,M.A.,de la Torre,J.,&Abad,F.J. (2o21).Balancing fitand parsimonytoimprove Q-matrix validation. British Journal of Mathematical and Statistical Psychology,74(Suppl1),110-130.   
Philipp,M.,Strobl, C.,delaTore,J.,&Zeileis,A.(2o18).Onthe estimationofstandarderors incognitive diagnosis models. Journal of Educational and Behavioral Statistics,43(1),88-115.   
Rupp,A., & Templin,J. (2o08). The effects of Q-matrix misspecification on parameter estimates and classification accuracy in the DINA model. Educational and Psychological Measurement, 68(1),78-96.   
Rupp,A. A.,Templin,J.,& Henson,R.A. (20l0). Diagnostic measurement: theory,methods,and applications. Guilford.   
Sessoms,J.,&Henson,R.A. (2018). Applications ofdiagnosticclassification models: Aliterature reviewand critical commentary. Measurement: Interdisciplinary Research and Perspectives,16(1),1-17.   
Sorrel,M.A.,Olea,J.,Abad,F.J.,de la Torre,J.,Aguado,D.,&Lievens,F.(2O16). Validityand reliabilityof situational judgment test scores: Anew approach based on cognitive diagnosis models. Organizational Research Methods,19(3),506-532.   
Tatsuoka,K. K. (1990). Toward an integration of item-response theory and cognitive error diagnosis. In N. Frederiksen,R.Glaser,A. Lesgold & M.Shafto (Eds.)，Diagnostic monitoring of skill and knowledge acquisition (pp. 453-488). Hillsdale, NJ: Erlbaum.   
Terzi,R. (2017). New $\mathcal { Q }$ -matrix validation Procedures (Unpublished doctoral dissertation). The State University of New Jersey, New Brunswick, America.   
Terzi,R.& de la Torre,J. (2018).An iterative method for empirically-basedQ-matrix validation. International Journal ofAssessment Tools in Education, 5(2),248-262.   
Tu,D., Cai, Y.,& Dai, H. (20l2). Anew method of Q-Matrix validation based on DNA model.Acta Psychologica Sinica, 44(4), 558-568.   
[涂冬波，蔡艳，戴海琦.(2012).基于 DINA 模型的Q矩阵修正方法．心理学报,44(4),558-568.]   
vonDavier,M. (2oo8).A general diagnostic model applied to language testing data. British Journalof Mathematical and Statistical Psychology,61(2),287-307.   
Wang,D., Cai,Y.,& Tu,D. (202O). Q-matrix estimation methods for cognitive diagnosis models: Based on partial known Q-matrix. Multivariate Behavioral Research. Advance online publication https://doi.0rg/10.1080/00273171.2020.1746901   
Wang,D., Gao, X.,Cai, Y.,& Tu,D.(2018). A new Q-matrix estimation method: ICC based on ideal response. Journal of Psychological Science, 41(2),466-474.   
[汪大勋，高旭亮，蔡艳，涂冬波.(2018).一种非参数化的Q 矩阵估计方法:ICC-IR 方法开发．心理科学 41(2), 466-474.]   
Wang,D., Gao, X., Cai,Y.,& Tu,D. (2020). Amethod of Q-matrix validation for polytomous response cognitive diagnosis model based on relative fit statistics. Acta Psychologica Sinica, 52(1),93-106. [汪大勋，高旭亮，蔡艳，涂冬波.(2020).基于类别水平的多级计分认知诊断Q矩阵修正：相对拟合统计量 视角．心理学报,52(1),93-106.]   
Wang,D.,Gao,X., Han, Y.,& Tu, D.(2018). A simple and effctive Q-matrix estimation method:From nonparametric perspective. Journal of Psychological Science, 41(1),180-188.   
[汪大勋，高旭亮，韩雨婷，涂冬波.(2018).一种简单有效的Q矩阵估计方法开发：基于非参数化方法视角. 心理科学,41(1),180-188.]   
Wang,W.,Song,L.,Ding,S.,Meng,Y.,Cao,C.,& Jie,Y.(2018). AnEM-based method for Q-matrix validation. Applied Psychological Measurement, 42(6),446-459.   
Yu,X.F.，& Cheng,Y. (2020).Data-driven Q-matrix validation using a residual-based statistic in cognitive diagnostic assessment. British Journal ofMathematical and Statistical Psychology,73(Suppl1),145-179.   
Yu, X.,Luo,Z.,Qin,C.,Gao,C.,& Li,J. (2015). Joint estimation of model parametersand Q-matrix based on response data. Acta Psychologica Sinica, 47(2),273-282.   
[喻晓锋，罗照盛，秦春影，高椿雷，李喻骏.(2015).基于作答数据的模型参数和Q矩阵联合估计．心理学报， 47(2), 273-282.]

# An empirical Q-matrix validation method using complete information matrix

LIU Yanlou, WU Qiongqiong

(AcademyofBigDataforEducation;SchoolofPsychology,QufuNormalUnversityJining273165,China)

# Abstract

A Q-matrix, which defines the relations between latent atributes and items,is a central building block of the cognitive diagnostic models (CDMs). In practice,a Q-matrix is usually specified subjectively by domain experts, which might contain some misspecifications. The misspecified Qmatrix could cause several serious problems, such as inaccurate model parameters and erroneous attribute profile classifications. Several Q-matrix validation methods have been developed in the literature, such as the G-DINA discrimination index (GDI),Wald test based on an incomplete information matrix (Wald-IC),and Hull methods. Although these methods have shown promising results on Q-matrix recovery rate (QRR) and true positive rate (TPR), a common drawback of these methods is that they obtain poor results on true negative rate (TNR). It is important to note that the worse performance of the Wald-IC method on TNR might be caused by the incorrect computation of the information matrix.

A new Q-matrix validation method is proposed in this paper that constructs a Wald test with a complete empirical cross-product information matrix (XPD). A simulation study was conducted to evaluate the performance of the Wald-XPD method and compare it with GDI, Wald-IC,and Hull methods.Five factors that may influence the performance ofQ-matrix validation were manipulated. Attribute patterns were generated following either a uniform distribution or a higher-order distribution. The misspecification rate was set to two levels: $Q M = 0 . 1 5$ and $Q M = 0 . 3$ . Two sample sizes were manipulated: 50O and 1000. The three levels of IQ were defined as high IQ, $P _ { j } \left( 0 \right) \sim U ( 0 , 0 . 2 )$ and $P _ { j } \left( 1 \right) \sim U ( 0 . 8 , 1 )$ ; medium IQ, $P _ { j } \left( 0 \right) \sim U ( 0 . 1 , 0 . 3 )$ and $P _ { j } \left( 1 \right) \sim U ( 0 . 7 , 0 . 9 ) _ { ! }$ ： and low IQ, $P _ { j } \left( 0 \right) \sim U ( 0 . 2 , 0 . 4 )$ and $P _ { j } \left( 1 \right) \sim U ( 0 . 6 , 0 . 8 )$ . The number of attributes was fixed at $K { = } 4$ . Two ratios of the number of items to atribute were considered in the study: $J = 1 6$ $\left[ ( K { = } 4 ) \times ( J K { = } 4 ) \right]$ and $J = 3 2 \left[ ( K { = } 4 ) \times ( J K { = } 8 ) \right] ,$

The simulation results showed the following.

(1) The Wald-XPD method always provided the best results or was close to the best-performing method across the diferent factor levels, especially in the terms of the TNR.The HullP and WaldIC methods produced larger values of QRR and TPR but smaller values of TNR. A similar pattern was observed between HullP and HullR, with HullP being better than HullR.Among the Q-matrix validation methods considered in this study, the GDI method was the worst performer.

(2) The results from the comparison of the HullP, Wald-IC,and Wald-XPD methods suggested that the Wald-XPD method is more preferred for Q-matrix validation. Even though the HullP and Wald-IC methods could provide higher TPR values when the conditions were particularly unfavorable (e.g.,low item quality, short test length,and low sample size), they obtain very low TNR values. The practical application of the Wald-XPD method was illustrated using real data.

In conclusion, the Wald-XPD method has excellent power to detect and correct misspecified q-entry. In addition,it is a generic method that can serve as an important complement to domain experts’ judgement, which could reduce their workload.

Key words cognitive diagnostic models, Q-matrix, XPD information matrix, Wald test

# 附录：Wald-XPD方法在各模拟条件下的平均运行时间

表 A1Wald-XPD 方法在各模拟条件下的平均运行时间(s)  

<html><body><table><tr><td>模拟条件</td><td>AD</td><td>QM</td><td>10</td><td>N</td><td>JK</td><td>时间</td></tr><tr><td></td><td>均匀分布</td><td>0.15</td><td>0.4</td><td>500</td><td>4</td><td>476.16</td></tr><tr><td>1</td><td>高阶分布</td><td>0.15</td><td>0.4</td><td>500</td><td>4</td><td>195.68</td></tr><tr><td>2</td><td>均匀分布</td><td>0.15</td><td>0.4</td><td>500</td><td>8</td><td>706.40</td></tr><tr><td>3</td><td>高阶分布</td><td>0.15</td><td>0.4</td><td>500</td><td>8</td><td>654.93</td></tr><tr><td>4</td><td>均匀分布</td><td></td><td></td><td>1000</td><td></td><td></td></tr><tr><td>5</td><td></td><td>0.15</td><td>0.4</td><td></td><td>4</td><td>302.90</td></tr><tr><td>6 7</td><td>高阶分布 均匀分布</td><td>0.15</td><td>0.4</td><td>1000 1000</td><td>4</td><td>746.01*</td></tr><tr><td></td><td>高阶分布</td><td>0.15</td><td>0.4</td><td>1000</td><td>8</td><td>505.79</td></tr><tr><td>8 9</td><td>均匀分布</td><td>0.15</td><td>0.4</td><td>500</td><td>8</td><td>320.67</td></tr><tr><td>10</td><td>高阶分布</td><td>0.15 0.15</td><td>0.6</td><td>500</td><td>4</td><td>68.17</td></tr><tr><td>11</td><td>均匀分布</td><td></td><td>0.6</td><td>500</td><td>4</td><td>67.66</td></tr><tr><td></td><td>高阶分布</td><td>0.15</td><td>0.6</td><td></td><td>8</td><td>54.11</td></tr><tr><td>12</td><td>均匀分布</td><td>0.15</td><td>0.6</td><td>500 1000</td><td>8</td><td>81.36</td></tr><tr><td>13</td><td>高阶分布</td><td>0.15</td><td>0.6</td><td>1000</td><td>4</td><td>21.35</td></tr><tr><td>14</td><td>均匀分布</td><td>0.15</td><td>0.6</td><td>1000</td><td>4</td><td>90.22</td></tr><tr><td>15</td><td>高阶分布</td><td>0.15</td><td>0.6</td><td>1000</td><td>8</td><td>56.11</td></tr><tr><td>16</td><td>均匀分布</td><td>0.15</td><td>0.6</td><td></td><td>8</td><td>113.40</td></tr><tr><td>17</td><td>高阶分布</td><td>0.15</td><td>0.8</td><td>500</td><td>4</td><td>12.93</td></tr><tr><td>18</td><td>均匀分布</td><td>0.15</td><td>0.8</td><td>500 500</td><td>4</td><td>21.20</td></tr><tr><td>19</td><td>高阶分布</td><td>0.15</td><td>0.8</td><td></td><td>8</td><td>23.63</td></tr><tr><td>20</td><td>均匀分布</td><td>0.15</td><td>0.8</td><td>500</td><td>8</td><td>46.23</td></tr><tr><td>21</td><td>高阶分布</td><td>0.15</td><td>0.8</td><td>1000</td><td>4</td><td>12.97</td></tr><tr><td>22</td><td>均匀分布</td><td>0.15</td><td>0.8</td><td>1000</td><td>4</td><td>12.50#</td></tr><tr><td>23</td><td>高阶分布</td><td>0.15</td><td>0.8</td><td>1000</td><td>8</td><td>48.36</td></tr><tr><td>24</td><td>均匀分布</td><td>0.15</td><td>0.8</td><td>1000</td><td>8</td><td>32.42</td></tr><tr><td>25</td><td>高阶分布</td><td>0.3</td><td>0.4</td><td>500</td><td>4</td><td>114.85</td></tr><tr><td>26</td><td>均匀分布</td><td>0.3</td><td>0.4</td><td>500</td><td>4</td><td>223.68</td></tr><tr><td>27</td><td></td><td>0.3</td><td>0.4</td><td>500</td><td>8</td><td>750.26</td></tr><tr><td>28</td><td>高阶分布 均匀分布</td><td>0.3</td><td>0.4</td><td>500</td><td>8</td><td>310.86</td></tr><tr><td>29</td><td></td><td>0.3</td><td>0.4</td><td>1000</td><td>4</td><td>163.41</td></tr><tr><td>30</td><td>高阶分布 均匀分布</td><td>0.3</td><td>0.4</td><td>1000</td><td>4</td><td>226.47</td></tr><tr><td>31</td><td></td><td>0.3</td><td>0.4</td><td>1000</td><td>8</td><td>510.00</td></tr><tr><td>32</td><td>高阶分布</td><td>0.3</td><td>0.4</td><td>1000</td><td>8</td><td>696.73</td></tr><tr><td>33</td><td>均匀分布</td><td>0.3</td><td>0.6</td><td>500</td><td>4</td><td>63.20</td></tr><tr><td>34</td><td>高阶分布</td><td>0.3</td><td>0.6</td><td>500</td><td>4</td><td>111.59</td></tr><tr><td>35 36</td><td>均匀分布</td><td>0.3</td><td>0.6</td><td>500</td><td>8</td><td>64.36</td></tr><tr><td>37</td><td>高阶分布 均匀分布</td><td>0.3</td><td>0.6</td><td>500</td><td>8</td><td>111.91</td></tr><tr><td></td><td></td><td>0.3</td><td>0.6</td><td>1000</td><td>4</td><td>61.61</td></tr><tr><td>38</td><td>高阶分布</td><td>0.3</td><td>0.6</td><td>1000</td><td>4</td><td>77.84</td></tr><tr><td>39</td><td>均匀分布</td><td>0.3</td><td>0.6</td><td>1000</td><td>8</td><td>95.48</td></tr><tr><td>40</td><td>高阶分布</td><td>0.3</td><td>0.6</td><td>1000</td><td>8</td><td>152.57</td></tr><tr><td>41</td><td>均匀分布</td><td>0.3</td><td>0.8</td><td>500</td><td>4</td><td>45.05</td></tr><tr><td>42</td><td>高阶分布</td><td>0.3</td><td>0.8</td><td>500</td><td>4</td><td>12.75</td></tr><tr><td>43</td><td>均匀分布</td><td>0.3</td><td>0.8</td><td>500</td><td>8</td><td>22.22</td></tr><tr><td>44</td><td>高阶分布</td><td>0.3</td><td>0.8</td><td>500</td><td>8</td><td>72.12</td></tr><tr><td>45</td><td>均匀分布</td><td>0.3</td><td>0.8</td><td>1000</td><td>4</td><td>15.34</td></tr><tr><td>46</td><td>高阶分布</td><td>0.3</td><td>0.8</td><td>1000</td><td>4</td><td>25.56</td></tr><tr><td>47 48</td><td>均匀分布 高阶分布</td><td>0.3 0.3</td><td>0.8 0.8</td><td>1000 1000</td><td>8 8</td><td>54.40 190.39</td></tr></table></body></html>

主：\*为Wald-XPD方法在模拟条件下的最长运行时间，#为Wald-XPD方法在模拟条件下的最短运行时间