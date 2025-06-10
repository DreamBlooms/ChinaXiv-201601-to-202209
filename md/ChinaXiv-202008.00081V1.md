# 认知诊断CAT选题策略：特征、关系及新进展

唐倩12 毛秀珍1 何明霜」　何洁1

（1四川师范大学教育科学学院，四川成都，610066）（2德阳市东汽小学，四川德阳，618000）摘要随着认知诊断计算机化自适应测验（cognitive diagnostic computerized adaptive testingCD-CAT）理论与实践的发展，兼顾知识状态与能力的双目标CD-CAT逐渐受到重视。选题策略是CAT 的核心，通过梳理传统CD-CAT 和双目标CD-CAT选题策略的研究，并对它们的特点、关系及表现进行介绍和评析。最后，基于认知诊断模型与CAT实践发展指出未来应加强一般化认知模型、复杂测验条件认知诊断模型下选题策略的研究；应开发双目标诊断测验的项目和测验特征指标；还应加强非参数选题方法和CD-CAT的实践应用研究。关键词 计算机化自适应测验；认知诊断模型；选题策略；测量精度；非统计约束

# 1引言

项目反应理论（itemresponse theory,IRT）通过分析项目反应数据评估被试连续潜在特质（ $\theta$ ）水平，常用于比较与甄选被试。随着国内、外教育改革的不断深入，教育质量评估要求加强对学生学习过程的形成性评价，并提供详细的教学指导信息以促进教育发展。认知诊断理论（cognitive diagnostic theory,CDT）在教育质量评估实践中应运而生。它能评估被试对特定领域知识的掌握情况、加工技能和认知过程，还能为被试进行补救学习提供个性化的帮助。IRT 和CDT作为现代心理与教育测量理论，已广泛应用于分析教育与心理测验数据，并成为计算机化自适应测验（computerized adaptive testing,CAT）的理论基础。

CAT 是一种新型测验模式，实现了测验的量体裁衣。与传统纸笔测验相比，它在获得相似测量精度的条件下既能保证测验效度、测验公平和测验安全，还缩短了测验长度和测验时间，进而提高测验效率（Cheng,2009）。CAT 自提出以来就倍受研究者和教育实践者的广泛关注。它包括题库、初始项目的选择、选题策略、能力估计方法和测验终止规则几个重要组成部分。若把CAT比作一台机器，那么题库便是物质基础，选题策略决定CAT的运转方式，能力估计方法是推动力，终止规则就是停止键。其中，选题策略决定了单个项目的适切性，也决定着整个测验的效率和测验公平，还是影响测验成本和测验安全的重要因素。于是，选题策略成为CAT研究的核心内容之一，影响着CAT未来发展的方向。

起初，CAT仅评估被试宏观的单维（多维）连续潜在特质水平（0）或者微观离散的知识状态（knowledge states,KS）（α）。虽然连续潜在特质与离散KS 代表被试不同侧面的特征，但它们并不相互排斥，而是密切联系的统一体。因而，CAT中如何同时评估被试的θ和α成为一个有价值的研究问题，推动了兼顾KS和能力的双目标CD-CAT（dual-objectiveCD-CAT）的研究。于是，本文首先系统梳理了传统CD-CAT（以估计被试KS为目的的CD-CAT）和双目标CD-CAT选题策略的研究进展。然后，通过对各类选题策略的特点、关系及表现进行介绍和评价，以期把握其发展脉络和趋势。最后，基于认知诊断模型与CAT实践指出未来研究的几个方向：应加强一般化认知模型、复杂测验条件认知诊断模型下选题策略的研究；应开发双目标诊断测验的项目和测验特征指标；还应加强非参数选题方法和CD-CAT的实践研究。

下文用 $K \cdot L$ 和 $T$ 分别表示测验考察的属性个数、测验长度和已施测项目数， $\{ i _ { 1 } , i _ { 2 } , . . . , i _ { T } \}$ 与 ${ \sf X } _ { _ T } = ( x _ { 1 } , x _ { 2 } , . . . , x _ { _ T } )$ 代表已施测项目及反应， $R$ 与 $R _ { \scriptscriptstyle T } = R / \{ i _ { 1 } , i _ { 2 } , . . . , i _ { \scriptscriptstyle T } \}$ 表示题库和剩余题库， $\mathtt { a }$ 和 $\hat { \mathsf { a } }$ 分别表示真实的和当前估计的KS。另外，所有KS 的集合为 $\Omega = \{ \mathfrak { a } _ { 1 } , \mathfrak { a } _ { 2 } , . . . , \mathfrak { a } _ { 2 ^ { \kappa } } \}$ ，所有KS对的集合为 $\Omega _ { 0 } = \{ ( \mathtt { a } _ { u } , \mathtt { a } _ { \nu } ) | \mathtt { a } _ { u } , \mathtt { a } _ { \nu } \in \Omega \}$ 。 $\Omega _ { 0 }$ 的子集$\Omega _ { 1 } = \{ ( \mathfrak { a } _ { u } , \mathfrak { a } _ { \nu } ) | \alpha _ { u k } \neq \alpha _ { \nu k } , k \in \{ 1 , 2 , . . . , K \} , \forall m \neq k , \alpha _ { u n } = \alpha _ { \nu m } , \}$ 表示仅在某一个属性上具备不同掌握状态的 KS 对的集合。集合 $\Omega _ { 1 k } = \{ ( { \mathtt { a } } _ { u } , { \mathtt { a } } _ { \nu } ) | { \alpha } _ { u k } = 1 , { \alpha } _ { \nu k } = 0 , \forall m \not = k , { \alpha } _ { u m } = { \alpha } _ { \nu m } \}$ 是$\Omega _ { 1 }$ 的子集，仅与属性 $k$ 相关。

# 2传统CD-CAT项目选择策略

测量精度是CAT的首要目标，但CAT又不能一味追求高测量精度而不顾一些非统计约束条件，如内容约束和项目曝光控制。因而，CAT发展至今，其选题策略的研究几乎都围绕这些方面展开。

# 2.1提高测量精度的选题方法

项目特征与被试KS是CAT选择项目的依据。近二十年来，研究者不断突破传统CAT的研究思路，极大地丰富了CD-CAT选题策略的研究。总体上，传统CD-CAT选题策略沿着：项目反应分布、KS 后验分布和结合项目与被试特征视角建构提高测量精度的选题指标。

# 2.1.1基于项目反应分布的信息量选题指标

Kullback-Leibler（KL）是最基础的选题指标。项目 $j$ 的 KL 信息量等于反应分布 $P ( x _ { j } | \hat { \mathsf { a } } )$

和 $P ( x _ { j } | \mathfrak { a } _ { \mathfrak { c } } ) ( c = 1 , 2 , . . . 2 ^ { \kappa } )$ 的 KL 信息量之和，即 $\begin{array} { r } { K L _ { j } = \sum _ { c = 1 } ^ { 2 ^ { K } } K L _ { j } ( \hat { \mathbf { a } } \| \mathbf { a } _ { c } ) } \end{array}$ （Xu et al.,2003）。利用KS的后验分布 $P ( \mathfrak { a } _ { c } | \mathsf { X } _ { t } )$ 对KL信息加权就得到后验加权KL信息（posterior-weighted KL,PWKL）， $\begin{array} { r } { P W K L _ { _ j } = \sum _ { c = 1 } ^ { 2 ^ { K } } K L _ { _ j } ( \hat { \mathbf { a } } \| \mathbf { a } _ { c } ) \cdot P ( \mathbf { a } _ { c } \big | \mathsf { X } _ { t } ) } \end{array}$ 。如果进一步利用海明距离 $h ( \hat { \mathrm { a } } , \mathrm { a } _ { { \scriptscriptstyle c } } )$ 反映 $\hat { \mathsf { a } }$ 与 $\mathtt { a } _ { c }$ 的相似性，便得到 $\begin{array} { r } { H K L _ { \mathbf { \omega } _ { j } } = \sum _ { c = 1 } ^ { 2 ^ { K } } K L _ { \mathbf { \omega } _ { j } } ( \hat { \mathbf { a } } \| \mathbf { a } _ { c } ) \cdot P ( \mathbf { a } _ { c } \big | \mathsf { X } _ { \mathbf { \omega } _ { t } } ) \cdot \left( h ( \hat { \mathbf { a } } , \mathbf { a } _ { c } ) \right) ^ { - 1 } } \end{array}$ ，称为混合 KL信息（the hybrid KL,HKL）。最后，若PWKL中 $\hat { \mathsf { a } }$ 取遍所有可能情况，就是修订的PWKL方法，记为 $\begin{array} { r } { M P W K L _ { j } = \sum _ { d = 1 } ^ { 2 ^ { K } } P ( \widehat { \sf a } _ { d } | \sf X _ { t } ) \cdot P W K L _ { j } ( \widehat { \sf a } _ { d } ) \circ } \end{array}$ （204

KL、PWKL、HKL和MPWKL均选择信息量最大的项目。它们是几种最基础和常用的选题策略。研究表明，PWKL 和HKL 表现类似，均优于KL 方法（Cheng,2009;Wang,2013）。与PWKL相比，MPWKL计算更复杂，短测验测量精度更高。当测验长度达20及以上时二者无明显差异（Kaplan et al.,2015）。

# 2.1.2基于KS后验分布的信息量选题指标

香农熵（shannon entropy,SHE）和互信息（mutual information,MI）是基于KS后验分布的选题方法。前者选择使预测 $\hat { \mathsf { a } }$ 后验分布的期望香农熵最小的项目，后者选择使 $P ( { \mathsf { a } } | { \mathsf { X } } _ { T } )$ 与 $P ( \mathsf { a } | X _ { _ { T } } , x _ { _ { T + 1 } } )$ 的预测KL 信息最大的项目（Zheng＆Chang,2016）。换言之，

$$
\begin{array} { r } { { S H E } = \arg \operatorname* { m i n } _ { j \in R _ { T } } \{ \sum _ { x = 0 } ^ { 1 } H ( P ( \mathfrak { a } _ { c } \big | \mathsf { X } _ { T } , x _ { j } = x ) ) \cdot P ( x _ { j } = x \big | \mathsf { X } _ { T } ) \} , } \end{array}
$$

$$
M I = \arg \operatorname* { m a x } _ { j \in R _ { T } } \{ \sum _ { x = 0 } ^ { 1 } P ( x _ { j } = x \big | \mathsf { X } _ { T } ) \cdot \sum _ { c = 1 } ^ { 2 ^ { \boldsymbol { c } } } K L ( P ( \mathtt { a } _ { c } \mid \mathsf { X } _ { T } , x _ { j } = x ) \| P ( \mathtt { a } _ { c } \mid \mathsf { X } _ { T } ) ) \} .
$$

Wang（2013）指出在大多数情况下MI方法比PWKL、SHE 和KL的测量精度更高。由于 SHE 和MI方法涉及预测反应分布，计算比较复杂，他将MI展开并进行简化得到简化MI方法。该方法计算更简单、所需时间更短且不明显降低测量精度。

# 2.1.3结合项目与被试特征的选题指标

认知诊断模型中项目特征包括q向量、认知诊断区分度（cognitive discrimination index,CDI）（Henson & Douglas,2005）、属性区分度（attribute discrimination index,ADI）（Hensonet al.,2008）和广义决定性输入，噪音“与”门模型（the generalized deterministic inputs,noisy“and”gate model,G-DINA）区分度指标 $\xi ^ { 2 }$ （de la Torre&Chiu,2010），被试特征主要指 KS的后验概率 $P ( \mathfrak { a } _ { c } | \mathfrak { X } _ { \tau } ) ( c = 1 , 2 , . . . , 2 ^ { \kappa } )$ 和属性掌握概率 $P ( \alpha _ { i k } = 1 | \mathsf { X } _ { _ { T } } ) ( k = 1 , 2 , . . . , K )$ 。

一方面，基于 $P ( \mathsf { a } _ { c } | \mathsf { X } _ { T } )$ 与项目 $\mathsf { q }$ 向量建构了二分法（halving algorithm,HA）（汪文义等，2014），结合 $P ( \mathfrak { a } _ { c } | \mathsf { X } _ { T } )$ 与 $\xi ^ { 2 }$ 、CDI 和 ADI 提出G-DINA 模型区分度指标（the G-DINAmodel discrimination index,GDI）选题方法（Kaplan etal.,2015）、后验加权 CDI（posterior-weighted CDI，PWCDI）和后验加权 ADI（posterior-weighted ADI，PWADI）方法（Zheng＆Chang,2016），分别见式（3）～（6）。

$$
H A = \arg \operatorname* { m i n } _ { j \in R _ { T } } \{ | \sum _ { c : \mathfrak { a } _ { c } \mathfrak { q } _ { j } \geq \mathfrak { q } _ { j } \mathfrak { q } _ { j } } ( \mathfrak { a } _ { c } | \mathsf { X } _ { _ T } ) - 0 . 5 | \}
$$

（204号 $G D I = \underset { j \in { \cal R } _ { T } } { \arg \operatorname* { m a x } } \{ \sum _ { c = 1 } ^ { 2 ^ { { \boldsymbol { \kappa } } } } P ( \mathfrak { a } _ { c } \mid \mathsf { X } _ { T } ) [ P ( { \boldsymbol { x } } _ { i j } = 1 \mid \mathfrak { a } _ { c } ) - \sum _ { c = 1 } ^ { 2 ^ { { \boldsymbol { \kappa } } } } P ( \mathfrak { a } _ { c } \mid \mathsf { X } _ { T } ) P ( { \boldsymbol { x } } _ { i j } = 1 \mid \mathfrak { a } _ { c } ) ] ^ { 2 } \} ,$ (4)$\begin{array} { r } { P W C D I = \arg \operatorname* { m a x } _ { j \in R _ { r } } \{ ( \sum _ { \Omega _ { 0 } } h ( \mathbb { a } _ { u } , \mathbb { a } _ { v } ) ^ { - 1 } ) ^ { - 1 } \sum _ { \Omega _ { 0 } } h ( \mathbb { a } _ { u } , \mathbb { a } _ { v } ) ^ { - 1 } P ( \mathbb { a } _ { u } \lvert \mathsf { X } _ { T } ) \cdot P ( \mathbb { a } _ { v } \lvert \mathsf { X } _ { T } ) \cdot K L _ { j } ( \mathbb { a } _ { u } \parallel \mathbb { a } _ { v } ) \} } \end{array}$ ,(5)

$$
\mathit { P W A D I } = \arg \operatorname* { m a x } _ { j \in R _ { T } } \{ ( K \cdot 2 ^ { K } ) ^ { - 1 } \cdot \sum _ { \Omega _ { 1 } } \mathit { P } ( \mathfrak { a } _ { u } \mid \mathsf { X } _ { T } ) { \cdot } P ( \mathfrak { a } _ { \nu } \mid \mathsf { X } _ { T } ) { \cdot } K L _ { j } ( \mathfrak { a } _ { u } \parallel \mathfrak { a } _ { \nu } ) \} .
$$

值得注意的是，MPWKL 是所有 KS 对 $( \mathsf { a } _ { u } , \mathsf { a } _ { \nu } )$ 的KL 信息量与 ${ \mathfrak { a } } _ { u } \cdot { \mathfrak { a } } _ { \nu }$ 后验概率乘积之和，实质上与汪文义等（2014）的KLED方法等价。PWCDI本质上是对MPWKL各项取加权平均，PWADI则是MPWKL中特定项的平均值。PWCDI最复杂，PWADI最简单，研究发现它们的模式判准率无明显差异（Zheng&＆Chang,2016）。

另一方面，项目与被试特征指标还常作为权重对信息量加权构建选题指标。例如，郭磊等（2016）运用CDI、ADI对PWKL信息量加权得到CDIPWKL和ADIPWKL方法，能提高PWKL的测量精度。又如，罗照盛等人（2015）利用边际属性掌握概率之差$\begin{array} { r } { \sum _ { k = 1 } ^ { K } \vert P ( \alpha _ { i k } = 1 \vert \mathsf { X } _ { _ { T } } , x _ { j } ) - P ( \alpha _ { i k } = 1 \vert \mathsf { X } _ { _ { T } } ) } \end{array}$ 对 PWKL 和HKL 加权得到 PPWKL和PHKL方法,也能提高PWKL和HKL 在测量精度和项目曝光均匀的综合表现。此外，研究者还分析特定模型的项目特征指标，如DINA 模型的项目鉴别力指数：高分组的通过率（1与失误参数 $s _ { j }$ 之差）减去低分组通过率（猜测参数 $g _ { j }$ ），记为 $w _ { j } = 1 - ( s _ { j } + g _ { j } )$ （Rupp et al.,2010），并作为DINA模型下项目信息量的加权指标（郭磊等，2016）。由此可见，除了一般项目特征指标外，研究特定模型下的项目特征也具有重要意义。

# 2.2属性平衡的选题策略

认知属性是诊断测验的显著特点，也是最小的内容单元。平衡属性考察次数是保证测验效度的关键。

# 2.2.1最大优先指标（maximum priority index,MPI）方法

最大优先指标 $M P I = \prod _ { k = 1 } ^ { K } [ ( u _ { k } - b _ { k } ) / u _ { k } ] ^ { q _ { j k } }$ 结合了属性 $k$ 的目标最大测量次数 $\boldsymbol { u } _ { k }$ 、当前已考察次数 $b _ { k }$ 和 $\varrho$ 矩阵元素 $q _ { j k }$ （Cheng,2010）。运用MPI对项目信息量加权选题可以提高测量精度。事实上， $[ ( u _ { k } - b _ { k } ) / u _ { k } ]$ 的值总小于等于1。于是，MPI的值随项目考察的属性增多而减小，并倾向于选择考察属性较少的项目，导致项目曝光不均匀。鉴于此，余丹等人（2011）、刘舒畅等人（2018）、孙小坚等人（2019）对MPI进行修订，分别提出$M P I _ { 1 } = \prod _ { k = 1 } ^ { K } [ ( u _ { k } - b _ { k } ) / u _ { k } + 1 ] ^ { q _ { j k } } \ , M P I _ { 2 } = \sum _ { k = 1 } ^ { K } [ ( u _ { k } - b _ { k } ) / u _ { k } ] ^ { q _ { j k } } \ \mathfrak { F } \mathfrak { K }$ $M P I _ { 3 } = [ \prod _ { k = 1 } ^ { K } ( u _ { k } - b _ { k } ) ^ { q _ { j k } } ] / C , ( C > 0 )$ 。此外，刘舒畅等人（2018）利用当前（目标）标准误 $S E _ { b k }$ （ $S E _ { B k }$ ）建立了 $M P I _ { 4 } = \sum _ { k = 1 } ^ { K } [ ( S E _ { b k } - S E _ { B K } ) / S E _ { B K } ] ^ { q _ { j k } }$ ；孙小坚等人（2019）还将Kuo 等人（2016）针对测验建构提出的平衡属性模式的权重指标RTA用于满足属性的最少测量次数。其中， $R T A _ { j } = \left( 1 + I ( ( T / K ) < 3 ) { \sum } _ { t = 1 } ^ { T } { I ( { \bf q } _ { j } = { \bf q } _ { t } ) ) ^ { - 1 } } \right.$ ， $I ( \cdot )$ 为指示函数， $\mathsf { q } _ { j }$ 和 $\mathsf { q } _ { t }$ 分别是未作答和已作答题目的 $\mathsf { q }$ 向量。

刘舒畅等人（2018）和孙小坚等人（2019）系统考察了各个优先指标与CDI、KL、PWKL、MPWKL 和MI乘积的选题表现。结果一致表明，改进的优先指标比MPI的测量精度更高。大部分测验条件下， $M P I _ { 4 }$ 优于 $M P I _ { 2 }$ ， $M P I _ { 2 }$ 优于 $M P I _ { 1 }$ ； $M P I _ { 3 }$ 与 $M P I _ { 2 }$ 与不同选题策略结合选题各有优势。一般而言， $M P I _ { 3 }$ 较 $M P I _ { _ 2 }$ 更能平衡项目曝光，测量精度稍低。

# 2.2.2基于加权离差思想构建的选题方法

Lin 和Chang（2018）借鉴加权离差模型（Swanson& Stocking,1993），建立了属性偏差指标 $\begin{array} { r } { W D _ { j } = \sum _ { k = 1 } ^ { K } w _ { k } ( l _ { k } - b _ { k } - q _ { j k } ) + \sum _ { k = 1 } ^ { K } w _ { k } ( u _ { k } - b _ { k } - q _ { j k } ) } \end{array}$ 和标准化加权属性偏差指$S W D _ { j } = \frac { M a x ( W D _ { j } ) - W D _ { j } } { M a x ( W D _ { j } ) - M i n ( W D _ { j } ) }$ 。 $w _ { k }$ 为属性 $k$ 的权重， $W D _ { j }$ 只计算每个属性与其上、（204号下界的正离差的加权和。类似地，KL可标准化为SKL=Max(KL(@)Min(KL()°他们比较了 $( - W D _ { j } ) \cdot K L _ { j }$ （记为WDKL）和 $S W D _ { j } \cdot S K L _ { j }$ （记为SWDKL）的结果，指出SWDKL 虽然在平衡属性测量次数和模式判准率方面比WDKL表现更好，但它们的项目曝光不均匀。

# 2.3曝光控制的选题方法

针对项目曝光不均匀性问题，研究者考察了传统CAT中限制阈值方法（restrictivethreshold,RT）、限制进度方法（restrictiveprogressive,RPG）、分层方法和最大优先指标的表现（Wang et al.,2011；毛秀珍，辛涛,2013; Cheng,2008）。Lin 和Chang（2018）还对RPG 适当变形并结合SWDK 和优先指标，提出约束渐进的 SWDKL方法（the constrainedprogressive SWDKL, CP_SWDKL） :

$$
C P _ { - } S W D K L _ { j } ( \hat { \bf a } _ { i } ) = \frac { e r _ { \mathrm { m a x } } } { e r _ { j } } [ ( 1 - \frac { T } { L } ) R _ { j } + \frac { T } { L } \times R _ { j I } ]
$$

ermax 与erj表示要求的最大曝光率和项目j的曝光率，令$a = \operatorname* { m i n } \left\{ S W D K L _ { _ { j } } , j \in R _ { _ { T } } \right\} \setminus { } \ b = \operatorname* { m a x } \left\{ S W D K L _ { _ { j } } , j \in R _ { _ { T } } \right\} ,$ 随机数 $R _ { j } \in U ( a , b )$ ，$R _ { j l } \in { \cal U } ( S W D K L _ { j } - ( S W D K L _ { j } - a ) / s ) , S W D K L _ { j } + ( b - S W D K L _ { j } ) / s ) \ ,$ $s$ 是调整 $R _ { j I }$ 区间长短的量，值越小，区间越大，选题越随机。研究表明，CP_SWDKL 能显著提高 SWDKL 和KL 的项目曝光均匀性，但也在一定程度上降低测量精度。总体上讲，RT 和 RPG 方法能较好地控制项目曝光率并提高题库利用率。

# 2.4CD-CAT选题策略简评

除了依据测量目的外，还可以从选题方法的建构思路对传统CD-CAT的选题策略分类（见表1）。对选题策略的研究，有以下几点思考。第一：除依据KS后验分布定义香农熵和互信息外，还可以运用其它特征变量，如预测反应分布建立香农熵和互信息选题方法。鉴于SHE 和MI等方法计算复杂，研究简化基于KS后验分布的选题方法、挖掘它们的关系都具有重要意义。第二，属性偏差指标是各个属性测量次数离差的加权和，优先指标是各个属性测量次数离差与目标占比的等权重加权和，二者实质上具有相同的建构思路。因此，基于属性其它特征，如测量信息量离差建立加权指标也是建构选题方法的一种重要思路。第三，加权选题方法集中在对反应分布信息量指标的加权，研究适合其它基础选题指标的加权方法也是未来有价值的研究问题。最后，结合多种思路的方法主要解决项目曝光不均匀问题，但大部分研究局限于传统CAT的思想，缺乏系统对比。因此，基于认知诊断测验的特点发展结合多种思路的选题方法是今后研究的重点。

传统CAT（CD-CAT）在测验结束时只报告 $\hat { \theta }$ （ä）。兼顾KS和能力的双目标CD-CAT能同时评估á和 $\hat { \boldsymbol { \theta } }$ ，引领CD-CAT 的发展方向，具有重要的实践价值。

表1传统CD-CAT选题策略汇总表  

<html><body><table><tr><td>分类标准</td><td>特点</td><td>具体方法</td><td>适用情景</td></tr><tr><td rowspan="3">基础选题指标</td><td>反应分布信息量指标</td><td>KL、PWKL、HKL、MPWKL</td><td rowspan="3">提高测量精度</td></tr><tr><td>KS 后验分布信息量指标</td><td></td></tr><tr><td>基于项目、被试特征选题</td><td>HA、GDI、PWCDI、PWADI</td></tr><tr><td rowspan="3"></td><td></td><td>PPWKL、PHKL</td><td></td></tr><tr><td>MPI,(i = 1,2,3,4)</td><td>MPWKL、MI）加权；</td><td rowspan="3"></td></tr><tr><td>属性偏差指标加权</td><td>WDKL、SWDKL</td></tr><tr><td>结合多种思路</td><td>运用多个步骤或方法</td><td>RT、RPG、分层方法、优先指</td></tr></table></body></html>

# 3双目标CD-CAT的项目选择策略

如何表征项目关于能力与KS的信息是双目标CD-CAT选题策略的核心，也是区别于传统CD-CAT的重要特征。根据KS与能力信息量的结合方式，可将双目标CD-CAT的选题方法分为三类：两阶段选题法、信息量加权平均方法和约束加权信息量方法。

# 3.1两阶段选题方法

两阶段选题方法包括两步法和影子测验方法。首先，两步法在传统CAT（或CD-CAT）测验结束时利用所有项目的反应估计α（或 $\theta$ ），是实现双目标CD-CAT最直接的方法。其次，CAT中影子测验方法在选题之前依据一定标准构造影子测验，然后在影子测验中选择最优项目，通过两步选题为实现双目标CD-CAT 提供了可能。例如，McGlohen 和 Chang（2008）、杜宣宣（2010）分别以 $\hat { \theta }$ 和 $\hat { \mathsf { a } }$ 构造影子测验，然后分别选择使 $\hat { \mathsf { a } }$ 和 $\hat { \theta }$ 信息量最大的项目。

两步法简单易行，但仅依据α（或 $\theta$ ）的信息选题，不能同时保证 $\hat { \mathsf { a } }$ 和 $\hat { \theta }$ 的测量精度（McGlohen&Chang,2008）。与两步法相比，影子测验方法能有效提高α和 $\theta$ 的估计精度，还提高了项目曝光均匀性。但影子测验方法也是将α和 $\theta$ 的信息独立地应用于选题，往往只能优先保证a或 $\theta$ 的估计精度。因此，结合a和 $\theta$ 的信息建立项目选择指标成为探索双目标

CD-CAT研究的新方向。

# 3.2信息量加权平均方法

# 3.2.1双信息选题方法(dual information,DI)

Cheng 和Chang（2007）首次依据 $P W K L _ { j } ( \hat { \mathbf { a } } )$ 和 $K L _ { j } ( \hat { \theta } )$ 提出项目 $j$ 的 DI信息量指标$\begin{array} { r } { D I _ { j } = w P W K L _ { j } ( \hat { \mathbf { a } } ) + \big ( 1 - w \big ) K L _ { j } ( \hat { \theta } ) } \end{array}$ 。DI方法结合了KS 和能力估计值的信息，选择使DI值最大的项目。但是 $P W K L _ { j } ( \hat { \mathsf { a } } )$ 和 $K L _ { j } ( \hat { \theta } )$ 的取值相差较大，后者对DI 的影响很小（Wanget al.,2014）。于是，将它们转换到相同量表再加权平均无疑是一种更合理的方法。

# 3.2.2信息量统一量纲加权平均方法

百分等级、标准化转换与对数值转换是统计学上常用的统一量纲方法。鉴于此，Wang等人（2014）提出先对 $P W K L ( \hat { \mathsf { a } } )$ 和 $P W K L ( \hat { \theta } )$ 进行百分等级（ $p e [ \cdot ]$ ）或标准分数（s[-])转换后再加权平均，得到百分等级合成法（aggregate ranked information method,ARI）和标准差合成法（aggregate standardized information method,ASI），即：

$$
\begin{array} { r l } & { A R I _ { j } = \arg \operatorname* { m a x } \{ w \cdot p e [ P W K L _ { j } ( \hat { \mathbf { u } } ) ] + ( 1 - w ) \cdot p e [ P W K L _ { j } ( \hat { \theta } ) ] , j \in R _ { T } \} } \\ & { A S I _ { j } = \arg \operatorname* { m a x } \{ w \cdot s [ P W K L _ { j } ( \hat { \mathbf { u } } ) ] + ( 1 - w ) \cdot s [ K L _ { j } ( \hat { \theta } ) ] , j \in R _ { T } \} } \end{array}
$$

不同于百分等级和标准化思想，Dai等人（2016）提出先对 $\hat { \theta }$ 的 Fisher 信息量 $I _ { j } ( { \hat { \theta } } )$ 和$S H E _ { j } ( \hat { \mathbf { a } } )$ 进行对数值转换，然后加权求和得“带有信息量的有序度”(dappermess withInformation,DWI)选题指标 $w \log ( I _ { j } ( \hat { \theta } ) ) - ( 1 - w ) \log ( S H E _ { j } ( \hat { \mathsf { a } } ) )$ 。他们通过模拟研究表发现$\omega$ 取0.5 时表现最佳。于是，DWI方法便简化为选择使 $I _ { j } ( \hat { \theta } ) / S H E _ { j } ( \hat { \mathsf { a } } )$ 最大的项目。研究表明，DWI与影子测验方法相比，模式判准率相似，能力估计更准确。

由此可见，ARI、ASI与 DWI都基于DI方法对 $\hat { \mathsf { a } }$ 和 $\hat { \theta }$ 的信息量进行量纲统一转换而来。ARI对连续信息量排序获得对应的百分等级，在一定程度上导致信息丢失，且容易受题库大小的影响；DWI能避免题库大小和极端值对选题的影响（Zheng et al.,2018）。总体上讲，与 DI方法相比，在KS 和能力估计方面，ARI的表现更差，ASI方法更优，DWI方法的能力估计精度更高。此外，ASI和ARI方法不局限于PWKL 信息量。例如，Kang 等人（2017）在ASI和ARI方法中运用MPWKL 信息量后分别得到MASI和MARI方法。

# 3.2.3Jensen-Shannon（JS）距离选题方法

根据Lin（1991）中JS距离的定义，Kang等人（2017）首先定义加权分布$g = w f _ { \hat { \mathrm { a } } } + ( 1 - w ) f _ { \hat { \theta } }$ ，然后对 $K L ( f _ { \hat { \boldsymbol { \alpha } } } \| _ { g } )$ 与 $K L ( f _ { \hat { \theta } } \| g )$ 求加权平均，进而定义项目 $j$ 的JS距离如下：

$$
J S _ { j } ( f _ { \hat { \mathsf { a } } } \parallel f _ { \hat { \theta } } ) = w K L _ { j } ( f _ { \hat { \mathsf { a } } } \parallel g ) + ( 1 - w ) K L _ { j } ( f _ { \hat { \theta } } \parallel g ) \circ
$$

JS 距离满足非负、对称和三角不等式性质。不同于KL、MI和 SHE，还可以定义有限个概率分布的JS 距离，并且允许根据各个概率分布的重要性加权。研究表明，JS方法通过选择使JS 距离最大的项目，其模式判准率明显高于ARI、ASI、MARI和MASI方法，而且JS 方法的项目曝光更均衡，计算时间更短。此外，Kang等人（2017）还基于香农熵定义了JS 距离，并研究了JS距离与互信息、Fisher信息量的关系。

# 3.3约束加权信息量方法

Wang 等人（2012）和Zheng等人（2018）都指出双目标CD-CAT中可将认知诊断判准率视作内容约束，分别提出加权信息量方法和信息量乘积选题方法（information productapproach,IPA）。Wang 等人（2012）考虑到优先指标MPI中 $q _ { j k }$ 作为指数导致求和或求积的项数等于项目考察的属性个数从而带来不可比问题。于是，他们改变 $q _ { j k }$ 的位置提出 $\varrho$ 矩阵控制指标： $P _ { 1 } = \prod _ { k = 1 } ^ { K } [ ( u _ { k } - b _ { k } - q _ { j k } ) / u _ { k } ] \cdot [ ( ( L - l _ { k } ) - ( t - b _ { k } - q _ { j k } ) ) / ( L - l _ { k } ) ]$ 、KL 信息控制指标 $\begin{array} { r } { P _ { 2 } = \sum _ { k = 1 } ^ { K } ( u _ { k } - b _ { k } ) [ \sum _ { \Omega _ { 1 k } } K L ( \mathtt { a } _ { u } , \mathtt { a } _ { \mathrm { v } } ) / 2 ^ { K - 1 } ] } \end{array}$ 和 DINA 模型 $\varrho$ 区分控制指标$P _ { 3 } = ( 1 - s _ { j } ) ( 1 - g _ { j } ) \cdot P _ { 1 }$ ，然后分别对 $\hat { \theta }$ 的 Fisher 信息量加权选题。其中， $l _ { k }$ 是属性 $k$ 的目标最小测量次数。与 $P _ { 1 }$ 和 $P _ { 3 }$ 相比， $P _ { 2 }$ 加权选题对KS 和 $\theta$ 的估计精度都最高（Wang et al.,2012）。注意到，除 $P _ { 3 }$ 仅适用于DINA模型外，其它优先指标可用于任何诊断模型。由此，针对特定模型提出切合模型特点的指标同样具有重要意义。

IPA方法将认知诊断项目信息量视作极大优先指标并与能力信息量相乘而得。Zheng 等人（2018）考察了 $P W K L _ { j } ( \hat { \mathbf { a } } ) \cdot K L _ { j } ( \hat { \theta } )$ 与 $P W A D I _ { j } \cdot K L _ { j } ( \hat { \theta } )$ 的选题表现，指出 IPA方法对α和 $\theta$ 的估计比ASI和ARI更准确，同时 IPA没有权重要求，不受题库和极端值的影响。特别地，DWI方法中 $1 / S H E ( \hat { \mathbf { a } } )$ 可视为极大优先指标，从而DWI方法也是一种 IPA方法。另外，若对 IPA方法取对数就转换为信息量对数之和，即 $\log { I P A } = \log { P W K L ( \hat { \mathbf { a } } ) } + \log { K L ( \hat { \boldsymbol { \theta } } ) }$ 这又成为 $\log { P W K L ( \hat { \mathsf { a } } ) }$ 和 $\log K L ( \hat { \theta } )$ 的加权平均。因此，IPA在一定程度上具备双目标CD-CAT项目选择方法的一般性框架。

# 3.4双目标CD-CAT选题策略简评

两阶段方法、信息量加权平均方法和约束加权信息量方法是三类双目标CD-CAT选题策略，见表2。首先，两阶段选题方法将α和 $\theta$ 的信息量独立地应用于选题。于是，将测验按比例分成多个阶段或者结合两者信息建构影子测验都可能提高两阶段方法选题表现。其次，信息量加权平均方法创新性地将α和 $\theta$ 的信息量统一为一个选题指标，但二者取值相差较大。于是，研究者一方面运用百分等级、标准分数、对数转换改进信息量加权平均方法，另一方面通过对α和 $\theta$ 的反应分布加权来建立JS距离选题方法。信息量加权平均方法主要运用了CD-CAT中常用的PWKL、KL 和 SHE 选题指标，并且表现较好的DWI、ARI 和 JS方法在大部分测验条件下对KS上午判准率在0.9左右,RMSE 在0.4左右(Wang etal.,2014;Dai et al.,2016;Kang etal.,2017），测量精度不够高。因此，今后还应考察多种信息量指标、开发双目标CD-CAT项目特征指标等方式研究双目标CD-CAT选题策略，提高测量精度。

注意到，权重是信息量加权平均方法的重要部分。通过比较0到1之间多个权重，Cheng和Chang（2007）指出除极端权重值外，不同权重对DI方法的影响很小，Dai等人（2016）发现权重为0.5时，DWI方法表现最优。Wang等人（2014）则系统对比了三类权重指标。第一，理论的权重，即选择第 $t$ 个项目时权重为 $w = t / ( L + 1 )$ ；第二，实证的权重，即基于累积信息量 $I n f _ { \theta } ^ { ( T ) }$ 和 $I n f _ { \mathfrak { a } } ^ { ( T ) }$ 与目标信息量 $I n f _ { \theta }$ 和 $I n f _ { \mathrm { a } }$ 的差距占目标信息量比重，如$w _ { \theta } = w _ { 1 } / \big ( w _ { 1 } + w _ { 2 } \big )$ （其中 $w _ { 1 } = ( I n f _ { \theta } - I n f _ { \theta } ^ { T } ) / I n f _ { \theta }$ ， $w _ { 2 } = ( I n f _ { \mathrm { a } } - I n f _ { \mathrm { a } } ^ { T } ) / I n f _ { \mathrm { a } } \ )$ ；第三，通过属性的权重向量 $( \tau _ { 1 } , \tau _ { 2 } , . . . \tau _ { K } )$ 与属性水平信息量向量的数量积构造属性层面的权重。他们指出，ASI和ARI方法中运用理论或实证权重都优于等权重。理论权重适用于高质量题库，实证权重适用于信息量较少的题库，属性层面的权重则适用于属性具有不同权重的情况。

再次，约束加权信息量方法可以视作CD-CAT加权信息量方法的扩展。特别地，IPA方法经对数转换可视为信息量加权平均方法，而加权平均DWI方法又可视为IPA方法。因此，IPA方法具有双目标CD-CAT选题策略的一般性框架。最后，双目标CD-CAT选题策略集中于提高测量精度的研究，而项目曝光均匀性和内容约束相比于传统CD-CAT 都具有新的特点和挑战。因此，今后可以借鉴传统CD-CAT 中选题策略的思路和方法，结合项目特征、KS 和能力的信息建构双目标CD-CAT选题策略，结合多种方法研究具有非统计约束的选题

方法。

表2双目标CD-CAT选题策略汇总表  

<html><body><table><tr><td>分类标准</td><td>两阶段选题</td><td>信息量加权平均</td><td>约束加权信息量</td></tr><tr><td rowspan="2">具体方法</td><td>两步法</td><td>直接加权平均：DI</td><td>Q矩阵、KL 信息控制指标加权： P·FI(O)、P·FI(O)、P·FI(θ)</td></tr><tr><td rowspan="2">影子测验方法</td><td>统一量纲：ASI、ARI、</td><td rowspan="2">信息量乘积：IPA</td></tr><tr><td></td><td>MASI、MARI、DWI 分布反应加权：JS</td></tr></table></body></html>

# 4研究展望

CD-CAT 自提出以来，因其对知识结构的诊断功能和CAT的高效测验模式，得到研究者的广泛关注和深入研究。特别地，针对CD-CAT选题的测量精度、项目曝光和内容约束问题，研究者不仅将传统CAT的选题策略推广到CD-CAT，还基于认知诊断测验的特征发展了独特的选题方法。不仅如此，随着研究深入和实践需要，兼顾能力和KS的双目标CD-CAT也得到广泛关注，并有大量研究。传统CD-CAT和双目标CD-CAT结合了IRT、CDT和CAT的理论与技术。它们的发展与测量理论的研究与实践、计算机技术的发展密切相关。

首先，近二十年来认知诊断模型得到了极大的丰富和发展，呈现出从单一测验条件到复杂测验条件，从低阶到高阶，从特殊到一般的发展特点。一方面针对二级评分项目提出了一般化G-DINA 模型。它在一定约束条件下可得到 DINA、DINO、NIDA、NIDO、RUM 和ACDM。然而，目前CD-CAT研究还以约束化认知诊断模型为基础，并以DINA模型和RUM模型为主。因此，基于一般诊断模型研究CD-CAT具有重要意义。这不仅能统一不同模型下项目选择和能力估计算法的编码过程，还有利于比较它们在不同模型下的表现。

另一方面，认知诊断模型还围绕G-DINA和约束化诊断模型扩展了复杂测验条件模型，如多级评分、属性多级和高阶模型。当前CD-CAT以二级评分项目为主，并有少量多级评分项目的研究。于是，探索多策略、属性多级评分和项目多级评分甚至更复杂测验条件下CD-CAT选题策略同样是今后研究的重要方向。

其次，CD-CAT中结合项目和被试特征是改进选题策略的重要思路。于是，针对双目标CD-CAT，如何构建表征能力和认知特征的项目与测验特征指标，如区分度指标；如何基于双目标认知诊断测验项目特征构建选题策略都是具有意义的研究问题。此外，目前的选题方法各有优势与不足，有必要探讨它们的最佳组合模式，加强非统计约束选题策略的研究。

最后，CD-CAT在国内实践还处于起步阶段，仅2009-2011年教育部组织了数学和英语的大规模CD-CAT 测试（Liu etal.,2013）。因此，今后有必要研究非参数项目选择方法，既可用于小规俣课呈诊断头践，还为人规俣头践应用收集数据做准奋。

参考文献：   
杜宣宣.(2010).一种新的认知诊断计算机自适应测验选题策略（硕士学位论文）．江西师范大学，南昌.   
郭磊，郑蝉金，边玉芳，宋乃庆，夏凌翔.(2016).认知诊断计算机化自适应测验中新的选题策略：结合项目区 分度指标.心理学报，48(7)，903-914.   
刘舒畅,涂冬波，蔡艳，赵 洋.(2018).四种新的基于属性平衡的CD-CAT选题策略开发研究．心理科学， 41(4)，976-981.   
罗照盛，喻晓锋，高椿雷，李喻骏，彭亚风，王睿，王钰彤．(2015)．基于属性掌握概率的认知诊断计算 机化自适应测验选题策略．心理学报，47(5)，679-688.   
毛秀珍，辛涛.(2013)．认知诊断CAT中项目曝光控制方法的比较.心理学报,45(6)，694-703.   
孙小坚，王钰彤，张世夷，辛涛.(2019).认知诊断计算机自适应测验中平衡属性收敛的新方法.心理科 学， $\boldsymbol { \mathscr { A } } \boldsymbol { \mathcal { Z } } ( 5 )$ ，1236-1244.   
汪文义，丁树良，宋丽红．(2014)．兼顾测验效率和题库使用率的CD-CAT选题策略．心理科学，37(1)， 212-216.   
余丹，潘奕娆，丁树良，杨庆红.(2011)．计算机化自适应诊断测验新的选题策略．江西师范大学学报（自 然科学版)，35(5)，580-550.   
Cheng,Y. (2008). Computerized adaptive testing-new development and application (Unpublished doctorial   
dissertation). UniversityofIlinois at Urbana-Champaign.   
Cheng,Y. (2009). When cognitive diagnosis meets computerized adaptive testing: CD-CAT. Psychometrika, 74(4), 619-632.   
Cheng,Y. (2010). Improving cognitive diagnostic computerized adaptive testing by balancing atribute coverage: The modified maximum global discrimination index method. Educational and Psychological Measurement, 70(6), 902-913.   
Cheng,Y.，& Chang, H.-H. (2oo7). Dual information method in cognitive diagnostic computerized adaptive testing.Paper presented at the meeting ofthe National Council on Measurement in Education, Chicago, IL.   
Dai,B.Y., Zhang,M.Q.,& Li, G. M. (2016).Explorationof item selection in dual-purpose cognitive diagnostic computerized adaptive testing: based on the RRUM. Applied Psychological Measurement, 40(8), 625-640.   
de la Torre, J.,& Chiu, C.Y. (2010,April). General empirical method of Q-Matrix validation.Paper presented at the annual meeting of the National Council on Measurement in Education, Denver, CO.   
Henson,R.,& Douglas,J. (2oo5). Test construction forcognitive diagnosis.Applied Psychological Measurement 29(4), 262-277.   
Henson,R.,Roussos,L.,Douglas,J.,& He,X. (2oo8). Cognitive diagnostic atribute-level discrimination indices. Applied Psychological Measurement, 32(4),275 - 288.   
Kang，H., Zhang,S.，& Chang,H.-H. (2017). Dual-objective item selection criteria in cognitive diagnostic computerized adaptive testing. Journal of Educational Measurement, 54(2),165-183.   
Kaplan,M.,de la Torre,J.,& Barrada, J.R. (2015). New item selection methods for cognitive diagnosis computerized adaptive testing. Applied Psychological Measurement, 39(3),167-188.   
Kuo,B.,Pai, H.，& de la Torre,J. (2016). Modified cognitive diagnostic index and modified atribute level discrimination index for test construction. Applied Psychological Measurement, 40(5), 315 - 330.   
Lin, J. (1991). Divergence measures based on the Shannon entropy. IEEE Transactions on Information Theory, 37(1), 145-151.   
Lin. C.,& Chang,H.-H. (2018). Item selection criteria with practical constraints in cognitive diagnostic computerized adaptive testing. Educational and Psychological Measurement ,79(2),335-357.   
Liu, H. Y., You, X.F., Wang, W. Y., Ding,S.L.,& Chang, H. H.(2013). The development ofcomputerized adaptive testing with cognitive diagnosis for an English achievement test in China. Journalofclassification, 30(2), 152.   
McGlohen,M.,& Chang, H.-H. (2008). Combining computer adaptive testing technology with cognitively diagnostic assessment. Behavior Research Methods,40(3),808-821.   
Rupp,A.A.,Templin,J.,& Henson,R.A. (2o10).Diagnostic Measurement:Theory,Methods,and Applications. New York: Guiford Press.   
Swanson,L.,& Stocking,M.L.(1993).A model and heuristic for solving very large item selection problems. Applied Psychological Measurement,17(2),151-166.   
Wang, C. (2013). Mutual information item selection method in cognitive diagnostic computerized adaptive testing with short test length. Educational and Psychological Measurement,73(6),1017-1035.   
Wang, C., Chang, H. -H.,& Douglas,J.(20l2). Combining CAT with cognitive diagnosis: A weighted item selection approach. Behavior Research Methods,44,95-109.   
Wang,C., Chang,H. H.，& Huebner,A. (2011). Restrictive stochastic item selection methods in cognitive

diagnostic computerized adaptive testing.Journal of Educational Measurement, 48(3),255-273.   
Wang, C., Zheng, C.,& Chang,H.-H. (2014).An enhanced approach to combine item response theory with cognitive diagnosis in adaptive testing. Journal of Educational Measurement, 51(4),358-380.   
Xu, X., Chang,H.,&Douglas,J. (2oo3). Computerized adaptive testing strategies for cognitive diagnosis.Paper presented at the meeting of the National Council on Measurement in Education, Montreal, Canada.   
Zheng, C.,& Chang,H.-H.(20l6).High-efficiency response distribution-based item selection algorithms for short-length cognitive diagnostic computerized adaptive testing. Applied Psychological Measurement, 40(8), 608-624.   
Zheng,C.,He,G.,& Gao,C.(2018).The information product methods: A unified approach to dual-purpose computerized adaptive testing. Applied Psychological Measurement, 42(4),321-324.

# Item selection methods for cognitive diagnostic computerized adaptive testing: Characteristics, relations and new development

TANG Qian1' ²; MAO Xiuzhenl; HE Mingshuangl; HE Jiel (1 Institute of Educational Science,Sichuan Normal University, Sichuan Chengdu,610066)

(2 Dongqi primary school,De Yang,618000)

Abstract: Dual-objective cognitive diagnostic computerized adaptive testing (CD-CAT),which considers knowledge status and ability simultaneously, has become more and more popular with the theoretical and practical development of CD-CAT. Item selection methods play a key role in CD-CAT. Thispapersystematicallyreviewsexistingitemselectionmethods on traditional and dual-objective CD-CAT, and summarizes the types, characteristics,relations,and performance of these methods. Furthermore, several future research directions were illustrated. First，it is necessary tostudy item selection strategy with general cognitive models and under complex test conditions. Second， it is important to develop indexes representing items and test characteristic of dual-objective diagnostic testing. Finally, it is meaningful to conduct research on non-parametric item selection methods and practical applications of CD-CAT.

Key words: computerized adaptive testing; cognitive diagnostic model; item selective strategy; measurement accuracy; non-statistical constraints