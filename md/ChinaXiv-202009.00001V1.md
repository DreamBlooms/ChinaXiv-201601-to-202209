# 基于基尼指数的双目标CD-CAT选题策略

罗芬1.2 王晓庆²蔡艳」 涂冬波\~（江西师范大学心理学院，南昌，330022）（江西师范大学计算机信息工程学院，南昌，330022）

摘要 双目标CD-CAT的测验结果既可用于形成性评估也可用于终结性评估。基尼指数可度量随机变量的不确定性程度，值越小则随机变量的不确定程度越低。本文用基尼指数度量被试知识状态类别以及能力估计置信区间后验概率的变化，提出基于基尼指数的选题策略。MonteCarlo 实验表明与已有的选题策略相比，新策略的知识状态分类精度和能力估计精度都较高，同时能有效兼顾题库利用均匀性，并能快速实时响应，且受认知诊断模型和被试知识状态分布的影响较小，可用于实际测验中含多种认知诊断模型的混合题库。

关键词认知诊断；项目反应理论；基尼指数；双目标CD-CAT；选题策略

# 1引言

终结性评价用一个连续标量 $\theta$ （常称为潜在特质或能力）来刻画学生在某个学习阶段的学习效果，基于项目反应理论（itemresponse theory,IRT）的计算机化自适应测验（computerized adaptive testing,CAT）以“量体裁衣”的方式能更高效地实施终结性评估。形成性评价用一个离散向量 $\alpha$ （常称为潜在认知模式或知识状态）来帮助教师了解每个学生的潜在认知状态，为教师提供教学反馈，以便更好的“因材施教”，这有利于学生学业和教师职业发展，基于认知诊断理论（cognitive diagnostic theory,CDT）的CAT 以“个性化”测验方式快速诊断被试认知的长处和短板。教学需要终结性评价与形成性评价相互结合，既关注结果又关注过程，使学习过程和对学习结果的评价达到和谐统一。IRT-CAT 关注终结性评价，CD-CAT（cognitive diagnostic computerized adaptive testing,CD-CAT）关注形成性评价，两者结合的双目标CD-CAT（dual objective CD-CAT,Dual-CAT）可以将它们的优势互补，从而更好的完成测验目标。

Dual-CAT的两个重点研究主题：一是建构题库的心理计量学指标，正如 IRT-CAT 依赖于项目反应模型（item response method,IRM)，CD-CAT 依赖于认知诊断模型（cognitivediagnostic model,CDM)，Dual-CAT也依赖于测验模型，测验模型与题库的心理计量学指标息息相关。现有文献，只有统一模型（unified model，也称为 fusion model）（Hartz,2002; Rupp,Templin,&Henson,2010）和高阶模型（de la Torre&Douglas,2004）将被试的知识状态 $\alpha$ 与能力 $\theta$ 建构在一个模型中，但统一模型所含参数较多，在统计上难以估计（Hartz,2002），因此实际应用较少，而高阶模型采用层级结构，将潜在特质视为比潜在属性更高层的一般能力，能力 $\theta$ 与项目的正确作答概率之间的关系是通过被试知识状态 $\alpha$ 间接相关，只有当属性个数较多时（例如大于10），能力 $\theta$ 的估计才会比较准确（de la Torre& Douglas,2004; Hsu& Wang,2015;Huang,2020)。因此Dual-CAT 的选题策略研究大多并不基于上述两种模型而采用分离建模的方法，使用统一模型还是使用分离建模这两种方式决定了选题策略的构造方法也不同，对于分离建模方式需要 IRM 和CDM的模型参数，如何为这两套模型参数建立联系是实施Dual-CAT 的基础。

de la Torre 和Douglas（2004）的研究表明对于同一批数据，高阶模型估计的θ与IRT 中2PLM（two-parameter logistic model）模型估计的θ 有较高的相关性；Wang,Zheng 和 Chang（2014）的研究也表明，单维项目反应模型（IRM）和DINA 模型（Junker& Sijtsma,2001）在属性间高度相关或线性层级相关时，能够很好地拟合相同的数据，他们的研究为分离建模方式提供了支持，采用两步估计方法通过考虑各自的心理模型可获得稳定的 $\alpha$ 和 $\theta$ 估计（Kang, Zhang,& Chang,2017）。

二是选题策略。选题策略是实施Dual-CAT的关键技术，优良的选题策略应该既能达到较高的分类精度和估计精度以满足测验目的；又能保证较为均匀的题库利用率以提高题库安全，还需具有较快的运算速度以满足实时响应的需求，研究者们围绕这个目标提出了多种选题策略。

IRT-CAT 和CD-CAT 的选题策略分别注重潜在特质的评估和潜在认知结构的评估，如何将这两者有效的结合起来？学者们提出了若干种适合Dual-CAT 的选题策略，文献中已有的 Dual-CAT 选题策略主要有两类：第一类是影子测验选题法；第二类是组合策略选题法。

McGlohen和Chang（2008）在分离建模方式下讨论了影子测验选题法与IRT-CAT和

CD-CAT 的单一目标选题法的性能：（1）利用 IRT-CAT中最大信息量策略（maximumfisher information,MFI）（Lord,1980）或极大化Kullback-Leibler（KL）（Chang&Ying,1996）信息量策略选择适合被试当前估计能力 $\hat { \boldsymbol { \theta } }$ 的项目，测验结束再估计被试的知识状态$\hat { \alpha }$ ；（2）利用CD-CAT 中的极小化香农熵策略（shannon entropy,SHE）或极大化KL 信息量（Tatsuoka,2002;Xu,Chang,&Douglas,2003）选择适合被试当前知识状态估计值 $\hat { \alpha }$ 的项目，测验结束再估计被试的能力 $\hat { \boldsymbol { \theta } }$ ；（3）适应被试当前能力估计值 $\hat { \boldsymbol { \theta } }$ 和知识状态估计值 $\hat { \alpha }$ 的影子测验（shadow test）选题，即先根据被试能力估计值 $\hat { \boldsymbol { \theta } }$ ，采用（1）的方法构建最合适（204号 $\hat { \boldsymbol { \theta } }$ 的影子题库，再从影子题库中采用（2）的方法选取最适合当前知识状态估计值 $\hat { \alpha }$ 的项目作为下一题的备选。他们将这三种方案在能力 $\theta$ 估计精度、认知状态 $\alpha$ 分类精度和项目曝光控制等3个指标上进行对比，研究结果表明影子测验选题的表现更优。

杜宣宣（2010）也采用了影子测验选题法，与McGlohen 和Chang（2008）不同之处在于，他先构建最适合当前知识状态估计值 $\hat { \alpha }$ 的影子题库，再从影子题库中选取最适合当前能力估计值 $\hat { \boldsymbol { \theta } }$ 的项目作为下一题的备选，并在不同属性层级结构下对能力θ估计精度、知识状态 $\alpha$ 分类精度等指标进行对比，他的研究结果也表明与单一目标选题策略相比，影子测验选题的表现更优。

McGlohen 和Chang（2008）、杜宣宣（2010）的影子测验选题是两步估计法，有学者认为（Cheng,2007;Dai,Zhang&Li,2016）两步“局部优化”的组合并不一定保证“良好的综合结果”，更理想的项目选择方法应该在一个步骤内同时考虑 $\hat { \alpha }$ 和 $\hat { \boldsymbol { \theta } }$ 以获得更适合的项目，因此提出基于 $\hat { \alpha }$ 和 $\hat { \boldsymbol { \theta } }$ 的组合策略选题法。

Cheng（2007）和Dai等人（2016）用线性加权组合 $o b j e c t i v e = w f \bigl ( \hat { \theta } \bigr ) + ( 1 - w ) g ( \hat { \alpha } )$ 的指标代替影子测验选题， $f \left( { \hat { \theta } } \right)$ 是关于 $\hat { \boldsymbol { \theta } }$ 的信息量，如MFI或KL等， $g ( \hat { \alpha } )$ 是关于 $\hat { \alpha }$ 的信息量，如 SHE、KL、PWKL（posterior-weighted KL）（Cheng,2009）、MPWKL（modified PWKL）（Kaplan, de la Torre,& Barrada, 2015）和 PWACDI（posterior-weightedattribute cognitive discrimination index）（Zheng& Chang,2016）等。他们的研究表明在能力$\theta$ 估计精度、认知状态 $\alpha$ 分类精度和项目曝光控制等3个指标上，与影子测验选题法相比，合成指标表现更优。

Wang,Chang 和Douglas（2012）也基于分离建模方式，将对被试知识状态的诊断视为约束条件，使用 IRT-CAT 中最大优先级指标方法（maximum priority index,MPI）（Cheng&Chang,2009）来选题，即一种乘法组合策略：objective $= M P I _ { j } \left( { \hat { \alpha } } \right) ^ { * } f { \bigl ( } { \hat { \theta } } { \bigr ) }$ ，使得IRT-CAT既可以测量被试能力又能对被试认知状态进行分类。他们的研究表明，由KL信息量构造的 MPI指标能够获得较好的测量精度。

综合来看，组合策略相对于影子测验选题法而言，能更加细致的刻画 $\hat { \alpha }$ 和 $\hat { \boldsymbol { \theta } }$ 之间相互作用对选题的影响。究竟采用加法组合策略还是乘法组合策略，与 $f \left( { \hat { \boldsymbol { \theta } } } \right)$ 和 $g ( \hat { \alpha } )$ $( M P I _ { j } ( \hat { \alpha } )$ ）采用何种信息量度量有关。Zheng,He 和Gao（2018）对比了多种信息量的加法组合策略和乘法组合策略，他们的研究结果表明这两种组合方式在不同信息量下各有优劣。

加法组合策略的研究有Cheng(2007)的两种 KL 信息量组合的DIM（dual informationmethod）策略，Wang 等人（2014）为消除 KL和PWKL信息量差异提出的ASI（aggregatestandardized information method）策略和 ARI（aggregate ranked information method）策略，Kang 等人（2017）用对称KL 信息量提出的JSD（Jensen shannon divergence）策略以及KL 和MPWKL 信息量组合的MASI（modified ARI）和MARI（modified ASI）等。

乘法组合策略的研究有Wang 等人（2012）提出的MPI的加权策略，Dai等人（2016）用对数转换消除MFI信息量和 SHE信息量量纲差异，将加法组合策略转换为乘法组合策略的DWI（dapperness with information）策略，Zheng等人（2018）提出的 IPA（information product approach）策略等。

这些选题策略在一定条件下，都有各自的优势，或精度较高但因运算量大选题耗时较多，如IPA策略；或精度稍低但可预先计算减少选题用时，如ASI策略；或精度更低但用时少且题库利用率较均匀，如JSD 策略。另外这些选题策略，还可能存在因两种信息量量纲差异较大造成合成指标有所偏向，或因进行转换以消除量纲差异所带来的信息损失等问题。我们希望开发一种对 $\hat { \alpha }$ 和 $\hat { \boldsymbol { \theta } }$ 而言量纲比较统一的信息指标，既保证估计精度和分类精度较高，又能兼顾题库利用率均匀性且选题耗时较少的新策略。

在CD-CAT中，大多采用贝叶斯决策对被试进行分类，被试的知识状态类别是一个随机变量，当类条件概率和先验概率已知的情况下，通过贝叶斯公式计算被试属于每个类别的后验概率，将被试的类别决策为后验概率大的一类，理论上已证明这种决策的平均错误率最低（张学工，2010，P14-15)，因此贝叶斯决策通常也称最小错误率贝叶斯决策。研究表明（陈平，李珍，辛涛，2011；韩雨婷，高旭亮，汪大勋，蔡艳，涂冬波，2018；Wang＆Chang,2011)，基于被试知识状态类别的后验概率所构造的选题策略（Zheng＆Chang,2016）和基于被试能力估计置信区间的后验概率所构造的选题策略具有较高分类精度和估计精度，如CD-CAT 中的香农熵策略（Tatsuoka,2002;Xu et al.,2003）和多维 IRT-CAT 中连续熵（也称微分熵）策略（Wang& Chang,2011；韩雨婷等,2018）。

熵用于度量随机变量不确定性，熵越大，随机变量的不确定性就越大。在CD-CAT中，用熵度量被试知识状态类别后验概率的变化，然后采用贝叶斯决策根据被试知识状态类别的后验概率进行分类，熵的变化直接反映各类别后验概率的变化，因而基于熵所构建的选题策略的分类准确性较高，如香农熵策略（Tatsuoka,2002;Xu etal.,2003)。统计学中，基尼指数也是一种度量随机变量不确定性的指标，并应用于决策树的分类算法，如既有基于熵的 ID3 算法（Quinlan,1986）和C4.5 算法（Quinlan,1993)，也有基于基尼指数的CART 算法（Breiman,Friedman, Stone,& Olshen,1984)，这些算法都是机器学习中的经典算法（周志华，2016)。

本研究拟采用基尼指数构建双目标CD-CAT的选题策略。基尼指数和熵有共性也有差异。两者的共性在于它们都可以度量随机变量的不确定性程度且既可以处理连续型随机变量又可以处理离散型随机变量。设离散型随机变量 $X$ 所有可能取的值为 $x _ { v } ( v = 1 , 2 , . . V )$ ，（20 $X$ 取各个可能值的概率 $p \{ X = x _ { v } \} = p _ { v } , v = 1 , 2 , . . . , V$ ，且 $\textstyle \sum _ { v = 1 } ^ { V } p _ { v } = 1$ ，那么随机变量 $X$ 的熵可以表示为： $\begin{array} { r } { E n t { ( X ) } = - \sum _ { v = 1 } ^ { V } p _ { v } \mathrm { l n } p _ { v } } \end{array}$ ，随机变量 $X$ 的基尼指数可以表示为：$\begin{array} { r } { G i n i ( X ) = \sum _ { v = 1 } ^ { V } p _ { v } ( 1 - p _ { v } ) = 1 - \sum _ { v = 1 } ^ { V } p _ { v } ^ { 2 } } \end{array}$ 。令 $f ( y ) = - \ln y$ ，在 $y = 1$ 处进行一阶泰勒展开（忽略高阶无穷小）， $f ( y ) = f ( 1 ) + f ^ { \prime } ( 1 ) \left( y - 1 \right) + O ( \cdot ) \approx 1 - y$ ，因此，在 $p _ { v } = 1$ 处熵可近似转化为：（204号 $\begin{array} { r } { E n t ( X ) = - \sum _ { v = 1 } ^ { V } p _ { v } \ln p _ { v } = \sum _ { v = 1 } ^ { V } p _ { v } ( - \ln p _ { v } ) \approx \sum _ { v = 1 } ^ { V } p _ { v } ( 1 - p _ { v } ) = G i n i ( X ) ^ { 1 } , } \end{array}$ 说明在极值点处，信息熵和基尼指数取得相同值。从数学表达式上看，熵对随机变量的概率使用对数加权，反映的是一种非线性关系，而基尼指数使用线性加权，反映的是一种线性关系。

熵的计算公式中含有对数运算，基尼指数只需求平方和，因此基于基尼指数构造的选题策略会和香农熵选题策略一样具有较高的分类精度，而运算速度快于香农熵策略，且基尼指数的线性加权方式对测验过程中各类别的后验概率变化更加敏感，从而有助于扩大选题范围，有利于提高题库利用率。

本文利用基尼指数的上述优良性质，提出基于基尼指数的选题策略，期望新策略能保证测量精度，同时兼顾题库利用均匀性并能快速实时响应，为同时兼顾宏观能力评估和微观认知诊断提供新的更优的方法。

# 2已有双目标CD-CAT选题策略简述

我们介绍三种有代表性的Dual-CAT 的选题策略。ASI策略是加法组合策略的代表，通过标准化消除了两种信息量量纲差异后再将转换后的信息量进行线性加权；IPA策略是乘法组合策略的代表；JSD 策略是题库利用率最均匀且选题耗时最少的选题策略代表。

# 2.1ASI策略

Cheng（2009）提出用PWKL策略代替KL策略，极大地提高了被试的知识状态 $\alpha$ ( $\alpha$ 是一个0和1构成的向量）的分类精度，设测验测量 $K$ 个独立属性，被试的知识状态有 $2 ^ { K }$ 类，测验结束将被试划分到其中的一类，PWKL 选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m a x } _ { j \in { \cal { R } } _ { t } } \left( P W K L _ { j } ( \hat { \alpha } ) \right)
$$

$$
P W K L _ { j } ( \hat { \alpha } ) = \sum _ { c = 1 } ^ { 2 ^ { \kappa } } [ \pi _ { t } ( \alpha _ { c } | Y ) ^ { * } K L _ { j } ( \hat { \alpha } | | \alpha _ { c } ) ]
$$

$$
K L _ { j } ( \hat { \alpha } | | \alpha ) = \sum _ { y = 0 } ^ { 1 } \log \biggl ( \frac { p ( Y _ { j } = y | \hat { \alpha } ) } { p ( Y _ { j } = y | \alpha ) } \biggr ) p ( Y _ { j } = y | \hat { \alpha } )
$$

其中 $R _ { t }$ 为被试作答 $t$ 题后的剩余题库。 $j$ 为剩余题库中的项目， $c = 1 , 2 , . . . , 2 ^ { \kappa }$ 为被试知识状态的类别下标， $\alpha _ { c }$ 为 $2 ^ { K }$ 种知识状态的第 $\boldsymbol { c }$ 个类别， $\pi _ { t } ( \alpha _ { c } | Y )$ 为在 $t$ 个项目的得分模式$Y = ( Y _ { 1 } , Y _ { 2 } , . . . , Y _ { t } )$ 下类别 $\alpha _ { c }$ 的后验概率， $\boldsymbol { Y } _ { j }$ 为被试在项目 $j$ 的得分， $y$ 为项目的可能得分，对于两级评分项目而言， $y = 0$ 或 $1$ ， $\hat { \alpha }$ 为被试知识状态的当前估计值， $p ( Y _ { j } = y | \hat { \alpha } )$ 为给定CDM和已知 $\hat { \alpha }$ 时，被试作答第 $j$ 题的答对概率。

Chang 和Ying（1996）用KL策略代替MFI策略来测量被试的能力 $\theta$ （ $\theta$ 是一个连续变量)，以克服当作答项目比较少时能力估计不准确的问题，KL选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m a x } _ { j \in \cal { R } _ { t } } \left( K L _ { j } \Bigl ( \widehat { \theta } \Bigr ) \right)
$$

$$
K L _ { j } \big ( \hat { \theta } \big ) = \int _ { \hat { \theta } - \delta } ^ { \hat { \theta } + \delta } K _ { j } \big ( \hat { \theta } | | \theta \big ) d \theta
$$

$$
K _ { j } \Big ( \hat { \theta } | | \theta \Big ) = \sum _ { y = 0 } ^ { 1 } \log \Bigg ( \frac { p \Big ( Y _ { j } = y | \hat { \theta } \Big ) } { p ( Y _ { j } = y | \theta ) } \Bigg ) p \Big ( Y _ { j } = y | \hat { \theta } \Big )
$$

其中 $\delta$ 建议取 $3 / { \sqrt { t } }$ ， $\mathbf { \Psi } _ { t }$ 为被试已作答的项目数， $\hat { \boldsymbol { \theta } }$ 为能力 $\theta$ 的当前估计值， $p \big ( Y _ { j } = y | \hat { \theta } \big )$ 为给定IRT中的IRM和已知 $\hat { \boldsymbol { \theta } }$ 时，被试作答第 $j$ 题的答对概率。

Cheng（2007）提出DIM选题策略，将关于 $\hat { \boldsymbol { \theta } }$ 的 KL 信息和关于 $\hat { \alpha }$ 的 KL信息线性组合为单个信息量以满足双目标CD-CAT选题的要求，DIM选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m a x } _ { j \in \cal { R } _ { t } } \Big ( D I M _ { j } \big ( \hat { \alpha } , \hat { \theta } \big ) \Big )
$$

$$
{ D I M _ { j } } \Big ( \hat { \alpha } , \hat { \theta } \Big ) = w K L _ { j } ( \hat { \alpha } ) + ( 1 - w ) K L _ { j } \Big ( \hat { \theta } \Big )
$$

其中 $w$ 为权重。

Wang 等人（2014）将DIM策略中关于 $\hat { \alpha }$ 的信息度量用PWKL信息量代换，并认为$P W K L _ { j } \left( \hat { \alpha } \right)$ 和 $K L _ { j } \left( { \hat { \boldsymbol { \theta } } } \right)$ 量纲不一致，可采用标准化方法消除两者之间的差异，进而提出了ASI策略，ASI选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m a x } _ { j \in { \cal R } _ { t } } \left( A S I _ { j } \Big ( \hat { \alpha } , \hat { \theta } \Big ) \right)
$$

$$
A S I _ { j } \big ( \hat { \alpha } , \hat { \theta } \big ) = w P W K L _ { j } ^ { * } ( \hat { \alpha } ) + ( 1 - w ) K L _ { j } ^ { * } \big ( \hat { \theta } \big )
$$

$$
P W K L _ { j } ^ { * } ( \hat { \alpha } ) = \frac { \left( P W K L _ { j } ( \hat { \alpha } ) - m e a n \left( P W K L \left( \hat { \alpha } \right) \right) \right) } { S D \left( P W K L \left( \hat { \alpha } \right) \right) }
$$

$$
K L _ { j } ^ { * } \Big ( \hat { \theta } \Big ) = \frac { \Big ( K L _ { j } \Big ( \hat { \theta } \Big ) - m e a n \Big ( K L \Big ( \hat { \theta } \Big ) \Big ) \Big ) } { S D \Big ( K L \Big ( \hat { \theta } \Big ) \Big ) }
$$

其中 $m e a n \left( P W K L \left( { \hat { \alpha } } \right) \right)$ 为剩余题库 $R _ { t }$ 所有项目关于被试知识状态当前估计值 $\hat { \alpha }$ 的PWKL 信息量均值， $S D \big ( P W K L ( \hat { \alpha } ) \big )$ 为其标准差。 $m e a n \big ( K L \big ( \hat { \theta } \big ) \big )$ 为剩余题库 $R _ { t }$ 所有项目关于能力当前估计值 $\hat { \boldsymbol { \theta } }$ 下 $\mathrm { \Sigma } \mathrm { K L }$ 信息量的均值， $S D \big ( K L \big ( \hat { \theta } \big ) \big )$ 为其标准差。Wang 等人（2014)还建议权重 $w$ 取值为 $1 - t / T L$ ， $\mathbf { \Psi } _ { t }$ 为已做答项目数， $T L$ 为预设的测验长度。

# 2.2 IPA 策略

Zheng 和 Chang（2016）提出适用于 CD-CAT 短测验的 PWACDI（posterior-weightedattribute cognitive discrimination index）选题策略，PWACDI选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m a x } _ { j \in { \cal { R } } _ { t } } { ( P W A C D I _ { j } ) }
$$

$$
P W A C D I _ { j } = \sum _ { k = 1 } ^ { K } \frac { 1 } { 2 ^ { K } } \sum _ { a l l \ r e l e v a n t \ c e l l s } P W D _ { j u v }
$$

$$
P W D _ { j u v } = \pi ( \alpha _ { u } | Y ) ^ { * } \pi ( \alpha _ { v } | Y ) ^ { * } \sum _ { y = 0 } ^ { 1 } \biggl [ p ( Y _ { j } = y | \alpha _ { u } ) ^ { * } \mathrm { l o g } \biggl ( \frac { p ( Y _ { j } = y | \alpha _ { u } ) } { p ( Y _ { j } = y | \alpha _ { v } ) } \biggr ) \biggr ]
$$

其中， $u$ 和 $\boldsymbol { v }$ 为被试知识状态的类别下标， $\alpha _ { u }$ 和 $\alpha _ { v }$ 为 $2 ^ { K }$ 种知识状态中不相同的两个类别， $P W D _ { j u v }$ 为根据项目 $j$ 构造的 $2 ^ { K } \times 2 ^ { K }$ 的 KL 信息矩阵，矩阵内的元素为任意两个知识状态的期望加权KL 距离。all relevant cells 是指 $P W D _ { j u v }$ 矩阵中两种不同知识状态 $\alpha _ { u }$ 和 $\alpha _ { v }$ 所对应位置的所有元素，且这两种知识状态仅在第 $k$ 个属性值是不同的，其他属性值相同。PWACDI选题策略与被试当前知识状态估计值 $\hat { \alpha }$ 无关，并且注重区分 $2 ^ { K }$ 种模式中，那些差异较小的模式，这不同于PWKL策略。

Zheng 等人（2018）提出适用于双目标CD-CAT的IPA策略，认为该策略能提供一个统一的框架来连接其他的双目标选题策略，将"权重"视为与IRT信息相等的对应项，则不需考虑公式（10）中的权重。信息量乘法的选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m a x } _ { j \in \cal { R } _ { t } } \left[ P _ { j } \times K L _ { j } \left( \widehat { \theta } \right) \right]
$$

$P _ { j }$ 可以是 $P W K L _ { j } \left( \hat { \alpha } \right)$ 或 $P W A C D I _ { j }$ 等其他 CD-CAT 的选题策略，根据 Zheng 等人（2018）的研究， $P W A C D I _ { j } \times K L _ { j } \left( \hat { \theta } \right)$ 的表现更好。

# 2.3 JSD 策略

Kang 等人（2017）提出JSD 选题策略，不同于PWKL 策略，它是对称的KL信息，令 $\boldsymbol { \eta } = \left( \hat { \alpha } , \hat { \boldsymbol { \theta } } \right)$ ，JSD 选题策略的目标函数为：

$$
\begin{array} { r l } & { O b j e c t i v e = a r g \underset { j \in R _ { t } } { \operatorname* { m a x } } \left( J S _ { j } \Bigl ( \hat { \alpha } \| \hat { \theta } \Bigr ) \right) } \\ & { J S _ { j } \Bigl ( \hat { \alpha } \| \hat { \theta } \Bigr ) = w K L _ { j } ( \hat { \alpha } \| \eta ) + ( 1 - w ) K L _ { j } \Bigl ( \hat { \theta } \| \eta \Bigr ) } \\ & { g _ { j } ( \eta ) = w p \left( Y _ { j } = y | \hat { \alpha } \right) + ( 1 - w ) p \Bigl ( Y _ { j } = y | \hat { \theta } \Bigr ) } \end{array}
$$

$$
K L _ { j } ( \hat { \alpha } | | \eta ) = \sum _ { y = 0 } ^ { 1 } p ( Y _ { j } = y | \hat { \alpha } ) \mathrm { l o g } \bigg ( \frac { p ( Y _ { j } = y | \hat { \alpha } ) } { g _ { j } ( \eta ) } \bigg )
$$

$$
K L _ { j } \Big ( \hat { \theta } | | \eta \Big ) = \sum _ { y = 0 } ^ { 1 } p \Big ( Y _ { j } = y | \hat { \theta } \Big ) \mathrm { l o g } \Bigg ( \frac { p \Big ( Y _ { j } = y | \hat { \theta } \Big ) } { g _ { j } ( \eta ) } \Bigg )
$$

特别说明，为了更清楚的描述 JSD 策略，我们补充了一些符号，因此本文中JSD 选题策略中的表达式与原文（Kang etal.,2017)不是完全相同，但没有改变选题策略本身的含义。

# 3基于基尼指数的双目标CD-CAT选题策略

本研究分别定义了基于被试知识状态类别的后验概率和基于被试能力估计置信区间的后验概率的基尼指数，并将两者组合构成基于基尼指数的双目标CD-CAT新策略，以期达成高精度、高题库利用率和快速反馈的测验需求。

# 3.1基于基尼指数的CD-CAT选题策略

设测验考查 $K$ 个属性，在 $t$ 个项目的得分模式 $Y = \left( Y _ { 1 } , Y _ { 2 } , . . . , Y _ { t } \right)$ 下类别 $\alpha _ { c }$ （ $c = 1 , 2 , . . . , 2 ^ { \kappa }$ ）的后验概率为 $\pi _ { t } \left( \alpha _ { c } | Y \right)$ （简记为 $\pi _ { t } ( \alpha _ { c } )$ ）且 $\textstyle \sum _ { c = 1 } ^ { 2 ^ { K } } \pi _ { t } ( \alpha _ { c } ) = 1$ ，根据基尼指数的定义（李航，2012)，则被试知识状态类别后验概率的基尼指数定义为：

$$
\begin{array} { r } { \phantom { } _ { - } C D ( \pi _ { t } ) = \sum _ { c = 1 } ^ { 2 ^ { \kappa } } [ \pi _ { t } ( \alpha _ { c } ) ^ { * } ( 1 - \pi _ { t } ( \alpha _ { c } ) ) ] = 1 - \sum _ { c = 1 } ^ { 2 ^ { \kappa } } [ \pi _ { t } ( \alpha _ { c } ) ] ^ { 2 } } \end{array}
$$

$$
\begin{array} { r } { \pi _ { t } ( \alpha _ { c } ) \propto \pi _ { 0 } ( \alpha _ { c } ) \prod _ { h = 1 } ^ { t } [ ( p _ { h } ( \alpha _ { c } ) ) ^ { Y _ { h } } ( 1 - p _ { h } ( \alpha _ { c } ) ) ^ { 1 - Y _ { h } } ] } \end{array}
$$

$\pi _ { t }$ 为 $t$ 个项目的反应模式 $Y = ( Y _ { 1 } , Y _ { 2 } , . . . , Y _ { t } )$ 下知识状态类别后验概率的集合， $\pi _ { 0 } \left( \alpha _ { c } \right)$ 是类别 $\alpha _ { c }$ 的先验概率，一般取 $1 / 2 ^ { K }$ ， $p _ { h } \left( \alpha _ { c } \right)$ 为给定CDM下知识状态为 $\alpha _ { c }$ 的被试答对第 $h$ 题的概率， $Y _ { h }$ 为被试在项目 $h$ 的得分，其他符号的含义同第2节。

Gini_ $C D ( \pi _ { t } )$ 刻画在 $\mathbf { \chi } _ { t }$ 个项目的反应模式 $Y = ( Y _ { 1 } , Y _ { 2 } , . . . , Y _ { t } )$ 下，被试知识状态类别后验概率分布的离散程度，其值越小则概率分布越集中，即一个或某些类别的后验概率会远大于其他类别，从而有助于提高贝叶斯决策对被试分类的准确性。遍历并选择剩余题库中使Gini_ $C D ( \pi _ { t } , Y _ { j } )$ 取得最小值的项目 $j$ 作为下一题的候选。

由于被试对候选项目 $j$ 的作答反应 $Y _ { j }$ 未知，对于两级评分项目， $Y _ { j }$ 的值为0或1（即$y = 0$ 或1)，定义被试知识状态类别后验概率的期望基尼指数：

$\begin{array} { r } { E [ G i n i \_ C D ( \pi _ { t } , Y _ { j } ) ] = \sum _ { y = 0 } ^ { 1 } G i n i \_ C D ( \pi _ { t + 1 } | Y _ { j } = y ) ^ { * } P ( Y _ { j } = y | \pi _ { t } ) } \end{array}$ 由全概率公式

$$
\begin{array} { r } { P ( Y _ { j } = y | \pi _ { t } ) = \sum _ { c = 1 } ^ { 2 ^ { \kappa } } [ \left( p _ { j } \left( \alpha _ { c } \right) \right) ^ { y } \left( 1 - p _ { j } \left( \alpha _ { c } \right) \right) ^ { 1 - y } ] \pi _ { t } \left( \alpha _ { c } \right) } \end{array}
$$

Gini $\mathit { C D }$ 选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m i n } _ { j \in { \cal R } _ { t } } \left( E \left[ G i n i \_ C D \left( \pi _ { t } , Y _ { j } \right) \right] \right)
$$

$R _ { t }$ 为被试的剩余题库，即从剩余题库中选择具有最小 $E [ G i n i \_ C D ( \pi _ { t } , Y _ { j } ) ]$ 的项目 $j$ 。

# 3.2基于基尼指数的IRT-CAT选题策略

在IRT-CAT测验初始阶段，由于被试当前能力估计值 $\hat { \theta }$ 往往与被试真实能力值偏差较大，此时基于 $\hat { \theta }$ 的Fisher信息量不是一个好的测验效率指示量，因此在测验初始阶段不能发挥重要作用（Chang&Ying,1996)。Veerkamp 和Berger（1994）提出用基于置信区间中信息函数的最高均值代替基于某一点的项目的区间信息选题准则，较好地克服了由于 $\hat { \theta }$ 估计不准带来的低效选题问题。

优良的选题策略使得被试能力估计值 $\hat { \theta }$ 随着测验的进行，越来越接近其真实值，根据Chang 和Ying（1996）以及Wang和Chang（2011）中KL全局信息量和连续熵的定义，我们定义了基于被试能力估计值 $\hat { \theta }$ 的置信区间后验概率的基尼指数，它类似于KL全局信息量，利用区间信息代替某个估计点的信息。令 $\widehat { \widehat { \boldsymbol { \theta } } } = \widehat { \boldsymbol { \theta } } + i \triangle \boldsymbol { \theta }$ ，

$$
G i n i \_ I R T \Big ( \pi _ { t } \Big ( \hat { \theta } \Big ) \Big ) = \int _ { \hat { \theta } - \delta } ^ { \hat { \theta } + \delta } \big [ \pi _ { t } ( \theta ) ^ { * } ( 1 - \pi _ { t } ( \theta ) ) \big ] d \theta \approx \sum _ { i = - s } ^ { s } \Big [ \pi _ { t } \Big ( \hat { \theta } \Big ) ^ { * } \Big ( 1 - \pi _ { t } \Big ( \hat { \theta } \Big ) \Big ) \Big ] \ : \Delta \theta
$$

$$
\begin{array} { r } { \pi _ { t } \big ( \hat { \theta } \big ) \propto \pi _ { 0 } \big ( \hat { \theta } \big ) \prod _ { h = 1 } ^ { t } \\\\Big [ \big ( p _ { h } \big ( \hat { \theta } \big ) \big ) ^ { Y _ { h } } \big ( 1 - p _ { h } \big ( \hat { \theta } \big ) \big ) ^ { 1 - Y _ { h } } \Big ] } \end{array}
$$

其中， $\pi _ { t } ( { \hat { \theta } } )$ 为 $t$ 个项目的反应模式 $Y = ( Y _ { 1 } , Y _ { 2 } , . . . , Y _ { t } )$ 下，能力估计值 $\hat { \theta }$ 的置信区间内后验概率的集合，Chang 和Ying（1996）建议 $\delta = 3 / \sqrt { t }$ ，根据BILOG 程序中计算后验期望概率的推荐值，取求积结点数为与 $2 \sqrt { t }$ 相近的自然数， $s = \lceil 2 \sqrt { t } \rceil / 2$ ，“「]”表示向上取整，$\pi _ { 0 } \big ( \hat { \theta } \big )$ 是 $\hat { \theta }$ 的先验概率，若能力先验信息未知则取均匀分布。 $p _ { h } \big ( \hat { \theta } \big )$ 为给定IRM下能力为 $\hat { \theta }$ （204号的被试答对第 $h$ 题的概率，其他符号的含义同第2节。

遍历并选择剩余题库中使 $G i n i \_ I R T { \Big ( } \pi _ { t } { \Big ( } { \hat { \theta } } { \Big ) } , Y _ { j } { \Big ) }$ 取得最小值的项目 $j$ 作为下一题的候选。

由于被试对候选项目 $j$ 的作答反应 $Y _ { j }$ 未知，对于两级评分项目， $Y _ { j }$ 的值为0或1（即$y = 0$ 或1)，定义能力估计值 $\hat { \theta }$ 的置信区间后验概率的期望基尼系数：

$$
\begin{array} { r } { E \big [ G i n i \_ I R T \big ( \pi _ { t } \big ( \widehat \theta \big ) , Y _ { j } \big ) \big ] = \sum _ { y = 0 } ^ { 1 } G i n i \_ I R T \big ( \pi _ { t + 1 } \big ( \widehat \theta \big ) | Y _ { j } = y \big ) ^ { * } P \big ( Y _ { j } = y | \pi _ { t } \big ( \widehat \theta \big ) \big ) } \end{array}
$$

$$
P \Big ( Y _ { j } = y | \pi _ { t } \Big ( \hat { \theta } \Big ) \Big ) = \int _ { \hat { \theta } - \delta } ^ { \hat { \theta } + \delta } \Big [ \Big ( p _ { j } \Big ( \hat { \theta } \Big ) \Big ) ^ { y } \Big ( 1 - p _ { j } \Big ( \hat { \theta } \Big ) \Big ) ^ { 1 - y } \Big ] \pi _ { t } \Big ( \hat { \theta } \Big ) d ( \theta )
$$

Gini_IRT选题策略的目标函数为：

$$
O b j e c t i v e = a r g \operatorname* { m i n } _ { j \in R _ { t } } \left( E { \left[ { G i n i \_ I R T { \left( \pi _ { t } { \left( \hat { \theta } \right) } , Y _ { j } \right) } } \right] } \right)
$$

$R _ { t }$ 为被试的剩余题库，即从剩余题库中选择具有最小 $E \big [ G i n i \_ I R T \big ( \pi _ { t } \big ( \hat { \theta } \big ) , Y _ { j } \big ) \big ]$ 的项目 $j$ 。

# 3.3组合策略

Cheng（2007）和Wang 等人（2014）提出将基于被试知识状态 $\hat { \alpha }$ 的KL信息函数和能力 $\hat { \theta }$ 的 KL 信息函数进行加权线性组合以得到单一信息量形式的双目标选题策略,如公式（8)和（10）。Zheng等人（2018）提出将两个函数相乘的双目标选题策略，如公式（16)。由于乘法运算更加费时。我们采用Cheng（2007）和Wang 等人（2014）的线性加权和方式获得基于基尼指数的双目标选题策略目标函数。

本文提出的新策略基于两个随机变量后验概率的基尼指数构造的新指标，由于每个随机变量后验概率的取值范围为[0,1]，且后验概率的累加和为1，这两个后验概率构造的基尼指数指标的量纲不会有很大差异，不需要像Wang等人（2014）将两个KL信息量进行标准化再进行线性组合，因转化还是会带来信息损耗，新策略的合成方法保持了原有信息。

Gini选题策略的目标函数为：

$$
\begin{array} { r l } & { G i n i _ { j } \Big ( \hat { \alpha } , \hat { \boldsymbol { \theta } } \Big ) = w ^ { * } E [ G i n i \_ C D ( \pi _ { t } , Y _ { j } ) ] + ( 1 - w ) E \Big [ G i n i \_ I R T \Big ( \pi _ { t } \Big ( \hat { \theta } \Big ) , Y _ { j } \Big ) \Big ] } \\ & { O b j e c t i v e = a r g \operatorname* { m i n } _ { j \in { \cal R } _ { t } } \Big ( G i n i _ { j } \Big ( \hat { \alpha } , \hat { \boldsymbol { \theta } } \Big ) \Big ) } \end{array}
$$

其中， $\scriptstyle w$ 是权重，根据Wang等人（2014）的建议，在高质量题库中建议使用理论权重 $w = 1 - t / T L$ ， $\mathbf { \Psi } _ { t }$ 为已做答项目数， $T L$ 为预设的测验长度。

# 4模拟实验设计

为考察不同CDM、被试不同知识状态分布以及不同测验长度下新策略的性能及其与其

他选题策略的比较，开展了Monte Carlo 模拟实验研究。实验考察了3种CDM（G-DINA,DINA,R-RUM) $\times 3$ 种被试知识状态的分布（高阶模型、高相关多元正态模型和低相关多元正态模型） $\times 4$ 种测验长度（5、10、15、20） $= 3 6$ 种情形下新策略的表现。

# 4.1认知诊断模型

在饱和模型 G-DINA（de la Torre,2011）和缩减模型（DINA,R-RUM)（Hartz,2002; Junker& Sijtsma,2001）下讨论各选题策略表现。G-DINA模型在适当约束条件下可简化为不同的缩减模型：若G-DINA所有主效应和低阶交互效应值为0，则其简化为DINA模型；若对数连接函数的所有交互效应的值为0，则可得R-RUM。

# 4.2题库参数和被试知识状态

# 4.2.1模拟题库项目的属性向量

设题库考察5个独立属性，每个项目最多考察3个属性即共25（ $C _ { 5 } ^ { 1 } + C _ { 5 } ^ { 2 } + C _ { 5 } ^ { 3 } = 2 5$ ）种项目属性向量，每种属性向量重复10次，可得题库中250个项目的属性向量。

# 4.2.2模拟被试知识状态的真值

被试知识状态采用两种方式模拟，一种采用 HO-CDM（Wang et al.,2012,2014; Huang,2020)，另一种采用多元正态分布生成（Dai etal.,2016;Kang etal.,2017）。考察这两种模拟方式是因为他们的作答反应数据可以同时拟合CDM和IRT 的模型，也是双目标CD-CAT中常用的模拟方法。

（1）被试知识状态用HO-CDM（de la Torre＆Douglas,2004）生成。高阶模型假定考生是否掌握某个属性与泛化的潜在能力有关。通过logit链接，给定高阶能力 $\theta _ { i }$ ，被试 $i$ 掌握属性 $k$ 的概率定义为： $P ( \alpha _ { i k } | \theta _ { i } ) = \frac { \exp \left( \lambda _ { 1 k } \left( \theta _ { i } - \lambda _ { 0 k } \right) \right) } { 1 + \exp \left( \lambda _ { 1 k } \left( \theta _ { i } - \lambda _ { 0 k } \right) \right) }$ ，类似IRT 中的2PLM 模型，其中 $\lambda _ { 1 k }$ 和 $\lambda _ { 0 k }$ 是区分度参数和位置参数， $\theta _ { i } { \sim } N ( 0 , 1 )$ ， $\ln \lambda _ { 1 k } { \sim } N ( 0 , 1 )$ （将值的约束在[0.2,2.5]区间范围内）， $\lambda _ { 0 k } { \sim } N ( 0 , 1 )$ ，另生成随机数 $r$ ， $r$ \~uniform $( 0 , 1 )$ ，如果$P ( \alpha _ { i k } | \theta _ { i } ) \geqslant r$ ，则令 $\alpha _ { i k } = 1$ ，否则令 $\alpha _ { i k } = 0$ （Ma& de la Torre,2020）。

（2）被试知识状态用多元正态模型生成。采用多元正态阈值模型（均值为0；变量间的相关分别设0.8，0.2两种水平，分别代表属性间存在高相关和低相关）生成被试真实属性掌握模式，用0作为截断点获得离散值知识状态（Ma&de la Torre,2020）。

# 4.2.3模拟题库CDM项目参数和IRT模型参数

采用第1节介绍的分离建模方法构建题库，CDM模型分别采用G-DINA、DINA和R-RUM模型，IRT模型采用2PLM，这些模型是研究和实践中经常使用的模型。

题库参数用R软件中的GDINA包和mirt包模拟和估计。

以G-DINA模型和被试的知识状态采用高相关多元正态模型生成为例介绍题库项目参数的模拟。

（1）根据GDINA包（Ma&de la Torre,2020）的说明文档，CDM参数的设定可以采用三种方法。第一种方法，为每个项目指定猜测参数 $p ( 0 )$ 和失误参数 $1 - p ( 1 )$ ，其中，$p ( 0 )$ 表示未掌握项目任何一个考察属性的被试正确作答概率， $p ( 1 )$ 表示掌握了项目所有考察属性的被试正确作答概率，其他类型的被试作答概率从 $[ p ( 0 ) , p ( 1 ) ]$ 中生成，需符合约束单调性原则，即掌握项目考察属性个数多的被试的正确作答概率大于掌握项目所考察属性个数少的被试的正确作答概率；第二种方法，为每个项目的每种知识状态指定答对概率；第三种方法，为每个项目指定G-DINA模型中的delta 参数。

因第一种方法简单易操作，本研究采用第一种方法，利用GDINA包中的 simGDINA函数模拟G-DINA 模型的项目参数，设 $p ( 0 )$ \~uniform(0.05,0.25),$p ( 1 ) { \sim } u n i f o r m ( 0 . 7 5 , 0 . 9 5 )$ ，其他掌握了项目所考察的部分属性的被试正确作答概率从$[ p ( 0 ) , p ( 1 ) ]$ 中生成，正确作答概率保证单调性。

（2）因为2PLM的项目参数估计需要1000以上样本才能获得较好的精度，本文利用高相关多元正态模型模拟3000个被试的知识状态，根据已知的每个项目属性向量和G-DINA 模型的项目参数获得每个被试在每个项目上的正确作答概率 $p$ ，另外生成随机数 $r$ ，r\~uniform $( 0 , 1 )$ ，如果 $p \geqslant r$ ，则令得分为1，否则令得分为0，即获得 $3 0 0 0 ^ { * } 2 5 0$ 的完全得分阵（Wang etal.,2012,2014)。将得分阵用R 软件中的mirt包（Chalmers,2012）中mirt函数拟合2PLM可得题库中250个项目的区分度和难度参数，用R软件中的GDINA包中GDINA函数对G-DINA 模型参数进行校正，以获得更准确的参数。

按照上述方法，可以获得相应的3（G-DINA,DINA,R-RUM） $^ { * _ { 3 } }$ （高阶模型、高相关多元正态模型和低相关多元正态模型） $\scriptstyle = 9$ 种题库的CDM的参数和2PLM参数。

# 4.2.4模拟被试能力的真值

被试对项目的反应是根据CDM模型模拟生成，模拟被试作答题库所有项目的反应数据，将反应数据用期望后验算法（Bock& Mislevy,1982）估计被试的能力值作为其真值（Wanget al., 2012, 2014; Dai et al., 2016; Kang et al., 2017）。

# 4.3选题策略

DIM 策略（Cheng,2007）是首个将两个KL信息量进行线性组合的策略，ASI策略将两个信息量标准化以消除两个信息量的量纲差异后再线性组合，根据Wang 等人（2014）的研究结果，ASI策略优于DIM策略。根据 Zheng等人（2016，2018）的研究结果，PWACDI策略在短测验上的分类精度优于PWKL 策略,PWACDI\*KL 策略和DWI策略(Dai et al.,2016)都属于双信息量的乘法组合策略 IPA，研究（Zheng etal.,2016,2018）表明，PWACDI\*KL 在一簇 IPA 策略中表现更好。JSD 策略（Kang et al.,2017）基于被试当前知识状态估计值和能力估计值的对称KL信息选题，在选题过程中不需要积分运算，因此运算简单，选题速度很快，根据Kang 等人（2017）的研究，JSD 策略与其他策略相比在选题用时和题库利用均匀性上有较大的优势。

本文将Gini 策略与 ASI策略（Wang et al.,2014）、IPA 中的代表PWACDI\*KL 策略（Zheng et al.,2018)，JSD（Kang et al.,2017）策略在9种题库下进行对比，从测量精度（包含知识状态分类精度和能力估计精度）、题库利用均匀性和选题用时等方面考查新策略的性能。

# 4.4终止规则

实验均采用定长测验，定长测验设置了4个水平：5、10、15和20 题。

# 4.5评价指标

# 4.5.1知识状态分类精度指标

模式判准率是评价知识状态分类精度的指标，值越大，分类精度越高。

$$
P M R = \frac { \sum _ { i = 1 } ^ { N } { I ( \hat { \alpha } _ { i } = \alpha _ { i } ) } } { N }
$$

其中 $I ( \bullet )$ 表示当条件·为TRUE 时，计数为1，否则为0。 $N$ 为被试人数。 $\hat { \alpha } _ { i }$ 是被试知识状态的估计值， $\alpha _ { i }$ 是被试知识状态的真值。

# 4.5.2能力估计精度指标

用 Bias 和RMSE作为能力估计精度的指标。值越小，参数返真性越高。

$$
B i a s = \frac { 1 } { N } { \sum } _ { i = 1 } ^ { N } \lvert \hat { \theta } _ { i } - \theta _ { i } \rvert
$$

$$
R M S E = \sqrt { \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( \hat { \theta } _ { i } - \theta _ { i } ) ^ { 2 } }
$$

其中 $\hat { \boldsymbol { \theta } } _ { i }$ 被试能力估计值， $\theta _ { i }$ 被试能力真值。其他变量含义同上。

# 4.5.3题库使用均匀性指标

卡方值和测验重叠率是评价题库使用均匀性的重要指标，值越小，题库使用越均匀，利用率越高。

其中 $m _ { j }$ 为项目 $j$ 的曝光次数， $L$ 为题库容量， $T L$ 设定的测验长度，其他变量含义同上。

# 4.5.4选题用时

$$
T C = \frac { \sum _ { i = 1 } ^ { N } T _ { i } } { N }
$$

其中， $T _ { i }$ 为第 $i$ 个被试完成测验所需时间（单位：秒)。由于模拟研究的时间消耗主要在选题上，其他用时可忽略不计，因此 $T C$ 即为选题耗时。值越小，选题速度越快。

# 4.6CAT实施过程

整个CAT 的程序，运行于Python3，硬件配置为4核处理器 IntelCore i51.9GHz，内存8G。以G-DINA 模型和高相关多元正态模型模拟被试知识状态的实验条件为例，说明CAT的实施过程。

（1）选择对应实验条件下在R环境中用GDINA包和mirt包构建的题库（细节参照第4.2 节);

（2）采用高相关多元正态模型模拟被试的知识状态作为被试知识状态的真值，并模拟被试采用G-DINA模型作答题库所有题，用期望后验法估计其能力值作为被试能力真值（细节参照第 4.2 节);

（3）随机分配3题给被试作答，根据初始3题的反应，估计被试知识状态初值和能力初值；

（4）分别采用Gini策略，ASI策略，IPA策略，JSD 策略选题进入各自CAT的过程

被试每作答一个项目，采用最大后验法估计被试知识状态和采用期望后验法估计被试能力；

（5）重复（4）直到满足测验停止要求；

（6）测验结束后根据每种策略下的最终被试知识状态估计值和被试能力估计值计算第4.5 节中的评价指标。

为消除随机效应，每次模拟1000个被试，每种实验条件重复10次，计算每种实验条件下各评价指标的平均值（见第5节的表格，SD表示其标准差）。

# 5实验结果

# 5.1分类精度的比较

表1表明，Gini 策略和 IPA 策略的模式判准率远高于ASI策略和JSD 策略，且整体而言Gini策略的模式判准率略高于IPA策略，这两种策略在不同实验条件下的模式判准率均超过 $9 5 \%$ 且标准差都较小，说明他们的分类结果稳定可靠，可适用于不同CDM的题库或多种CDM混合题库。

图1是各选题策略在不同测验长度上的表现，随测验长度的增加，各选题策略的模式判准率逐渐提高。Gini策略和IPA策略的变化曲线非常相似，增长最快，始终保持最好的判准率。在短测验（ $\mathrm { . T L } { < } 1 5 \$ )中，Gini、IPA和ASI策略的模式判准率很接近，在中长测验（ $\mathrm { \ T L } { > } 1 5$ ）后，ASI策略的增长速度要低于前两者。与表1的结论相同，Gini和 IPA策略在不同实验条件下的变化曲线没有太大差异，因此他们在短测验和中长测验下均能获得较好的分类精度。

表120题各选题策略的模式判准率均值及标准差  

<html><body><table><tr><td rowspan="3">CDM 模型</td><td rowspan="3">知识状 态生成 模型</td><td colspan="8">选题策略</td></tr><tr><td colspan="2">Gini</td><td colspan="2">ASI</td><td colspan="2">IPA</td><td colspan="2">JSD</td></tr><tr><td>Mean</td><td></td><td>SD</td><td>Mean</td><td>SD</td><td>Mean</td><td>SD</td><td>Mean</td><td>SD</td></tr><tr><td rowspan="4">G-DINA</td><td>HO</td><td>97.00%</td><td>0.009</td><td>89.28%</td><td>0.025</td><td>96.10%</td><td>0.010</td><td>85.04%</td><td></td><td>0.024</td></tr><tr><td>MV-0.8</td><td>97.22%</td><td>0.004</td><td>93.05%</td><td>0.011</td><td>97.44%</td><td>0.008</td><td></td><td>92.02%</td><td>0.014</td></tr><tr><td>MV-0.2</td><td>96.84%</td><td>0.007</td><td>90.78%</td><td>0.014</td><td>96.35%</td><td></td><td>0.006</td><td>87.51%</td><td>0.016</td></tr><tr><td>HO</td><td>97.45%</td><td>0.010</td><td>90.99%</td><td>0.032</td><td>97.18%</td><td>0.011</td><td></td><td>75.31%</td><td>0.060</td></tr><tr><td></td><td>MV-0.8</td><td>97.24%</td><td>0.011</td><td>93.45%</td><td>0.017</td><td></td><td>97.06%</td><td>0.010</td><td>91.46%</td><td>0.023</td></tr><tr><td></td><td>MV-0.2</td><td>97.57%</td><td>0.006</td><td>93.76%</td><td>0.007</td><td></td><td>96.93%</td><td>0.008</td><td>86.23%</td><td>0.050</td></tr><tr><td>R-RUM</td><td>HO</td><td>95.41%</td><td>0.010</td><td>87.61%</td><td>0.021</td><td></td><td>95.38%</td><td>0.010</td><td>76.64%</td><td>0.028</td></tr></table></body></html>

<html><body><table><tr><td></td><td>MV-0.8</td><td>97.09%</td><td>0.009</td><td>92.45%</td><td>0.014</td><td>96.82%</td><td>0.008</td><td>91.67%</td><td>0.010</td></tr><tr><td></td><td>MV-0.2</td><td>96.81%</td><td>0.008</td><td>87.88%</td><td>0.022</td><td>96.82%</td><td>0.012</td><td>80.52%</td><td>0.038</td></tr></table></body></html>

注：HO 指被试知识状态用HO-CDM生成，MV-0.8指被试知识状态用多元正态模型生成且属性间相关系数为0.8，MV-0.2指被试知识状态用多元正态模型生成且属性间相关系数为0.2。

# 5.2能力估计精度的比较

表2表明，除在DINA模型下属性间低相关的实验条件外，4种策略对能力估计基本是无偏的。ASI策略的估计偏差最小，其次是Gini 策略。IPA 策略具有最小的能力估计均方差值，与之相比，Gini 策略稍稍差一些，但最大差异也仅有0.04。当属性间高相关时，4种选题策略的能力估计均方差值非常接近，最大差异仅有0.03，而在其他条件下，最大差异达0.22，这说明属性间高相关时，4 种选题策略均可用，而其他条件下可优先考虑 IPA 和Gini策略。Gini 和 IPA 策略的能力估计精度与CDM有关，Gini 策略所受影响更小一些。ASI和JSD 策略的能力估计精度既与CDM有关又与被试知识状态分布有关。

图2表明随测验长度的增加被试能力估计的均方差值在下降，即参数估计精度在上升，Gini 和IPA策略均方差值下降速度最快，且两种策略的下降曲线基本相同，JSD 策略的下降趋势最慢。当属性间高相关时，4种选题策略的曲线基本重合，在其他条件下，与图1类似，在短测验（ $\mathrm { T L } { < } 1 5$ ）中，Gini、IPA和ASI策略的曲线基本一致，在中长测验（ $\mathrm { T L } { > } 1 5$ ）后，ASI策略不如前两者。因此Gini 和 IPA 策略在短测验和中长测验下均能获得较好的能力估计精度。

表220题各选题策略的Bias和RMSE  

<html><body><table><tr><td rowspan="3">CDM 模型</td><td rowspan="3">知识状 态生成 模型</td><td colspan="8">选题策略</td></tr><tr><td colspan="2">Gini</td><td colspan="2">ASI</td><td colspan="2">IPA</td><td colspan="2">JSD</td></tr><tr><td>Bias</td><td>RMSE</td><td>Bias</td><td>RMSE</td><td></td><td>Bias RMSE</td><td></td><td>Bias</td><td>RMSE</td></tr><tr><td>G-DINA</td><td>HO</td><td>0.02</td><td>0.32</td><td>0.00</td><td>0.41</td><td>0.04</td><td>0.28</td><td>0.02</td><td>0.40</td></tr><tr><td rowspan="5">DINA</td><td>MV-0.8</td><td>0.00</td><td>0.29</td><td>0.01</td><td>0.29</td><td>0.02</td><td>0.29</td><td>0.02</td><td>0.30</td></tr><tr><td>MV-0.2</td><td>0.03</td><td>0.27</td><td>0.02</td><td>0.32</td><td>0.07</td><td>0.27</td><td>0.05</td><td>0.42</td></tr><tr><td>HO</td><td>-0.08</td><td>0.40</td><td>-0.02</td><td>0.41</td><td>-0.14</td><td>0.37</td><td>-0.05</td><td>0.46</td></tr><tr><td>MV-0.8</td><td>0.02</td><td>0.34</td><td>0.01</td><td>0.32</td><td>-0.03</td><td>0.35</td><td>-0.08</td><td>0.35</td></tr><tr><td>MV-0.2</td><td>-0.12</td><td>0.38</td><td>-0.09</td><td>0.36</td><td>-0.24</td><td>0.42</td><td>-0.28</td><td>0.52</td></tr></table></body></html>

<html><body><table><tr><td>R-RUM</td><td>HO</td><td>-0.07</td><td>0.35</td><td>-0.01</td><td>0.42</td><td>-0.14</td><td>0.35</td><td>-0.02</td><td>0.45</td></tr><tr><td></td><td>MV-0.8</td><td>0.00</td><td>0.30</td><td>-0.02</td><td>0.30</td><td>-0.03</td><td>0.30</td><td>-0.03</td><td>0.32</td></tr><tr><td></td><td>MV-0.2</td><td>-0.04</td><td>0.31</td><td>-0.01</td><td>0.43</td><td>-0.10</td><td>0.29</td><td>-0.05</td><td>0.51</td></tr></table></body></html>

# 5.3题库使用均匀性的比较

表320题各选题策略的题库使用均匀性指标  

<html><body><table><tr><td rowspan="3">CDM 模型</td><td rowspan="3">知识状 态生成 模型</td><td colspan="8">选题策略</td></tr><tr><td colspan="2">Gini</td><td colspan="2">ASI</td><td colspan="2">IPA</td><td colspan="2">JSD</td></tr><tr><td>x²</td><td>TOE</td><td>x²</td><td>TOE</td><td>七²</td><td>TOE</td><td>七²</td><td>TOE</td></tr><tr><td>G-DINA</td><td>HO</td><td>82.38</td><td>0.41</td><td>98.75</td><td>0.47</td><td>85.34</td><td>0.42</td><td>44.45</td><td>0.26</td></tr><tr><td rowspan="4">DINA</td><td>MV-0.8</td><td>69.37</td><td>0.36</td><td>77.30</td><td>0.39</td><td>77.11</td><td>0.39</td><td>53.26</td><td>0.29</td></tr><tr><td>MV-0.2</td><td>72.50</td><td>0.37</td><td>91.36</td><td>0.44</td><td>82.94</td><td>0.41</td><td>37.08</td><td>0.23</td></tr><tr><td>HO</td><td>70.91</td><td>0.36</td><td>86.88</td><td>0.43</td><td>72.68</td><td>0.37</td><td>53.52</td><td>0.29</td></tr><tr><td>MV-0.8</td><td>56.55</td><td>0.31</td><td>66.74</td><td>0.35</td><td>58.98</td><td>0.32</td><td>59.31</td><td>0.32</td></tr><tr><td rowspan="4">R-RUM</td><td>MV-0.2</td><td>72.11</td><td>0.37</td><td>83.17</td><td>0.41</td><td>67.31</td><td>0.35</td><td>58.41</td><td>0.31</td></tr><tr><td>HO</td><td>95.78</td><td>0.46</td><td>109.29</td><td>0.52</td><td>94.55</td><td>0.46</td><td>58.22</td><td>0.31</td></tr><tr><td>MV-0.8</td><td>85.70</td><td>0.42</td><td>84.99</td><td>0.42</td><td>87.92</td><td>0.43</td><td>56.27</td><td>0.30</td></tr><tr><td>MV-0.2</td><td>88.92</td><td>0.44</td><td>105.01</td><td>0.50</td><td>95.48</td><td>0.46</td><td>60.78</td><td>0.32</td></tr></table></body></html>

表3表明，JSD 策略的题库利用均匀性优于其他3种策略。Gini和 IPA策略的题库利用率指标值相近，整体而言，Gini策略的题库利用均匀性稍好于IPA策略，且两者均好于ASI策略。当在DINA 模型下属性间高相关时，4种选题策略的题库利用率指标值比较接近，而在其他条件下差异较大。4种选题策略的题库利用均匀性指标既与CDM有关，又与被试知识状态的分布有关。

图3表明，随测验长度的增加，各选题策略的卡方值在下降，即题库使用均匀性逐渐提高。每种选题策略在不同条件下的曲线变化基本相似，JSD 的下降曲线最好，其次是Gini策略，当在DINA 模型下属性间高相关时，4种选题策略的下降曲线基本重合。

# 5.4选题用时的比较

# 表420题各选题策略的选题用时指标（单位：秒）

<html><body><table><tr><td rowspan="2">CDM 模型</td><td rowspan="2">知识状态生 成模型</td><td colspan="4">选题策略</td></tr><tr><td>Gini</td><td>ASI</td><td>IPA</td><td>JSD</td></tr><tr><td>G-DINA</td><td>HO</td><td>2.27</td><td>0.82</td><td>22.27</td><td>0.16</td></tr><tr><td rowspan="5">DINA</td><td>MV-0.8</td><td>2.27</td><td>0.82</td><td>21.95</td><td>0.16</td></tr><tr><td>MV-0.2</td><td>2.27</td><td>0.81</td><td>22.18</td><td>0.16</td></tr><tr><td>HO</td><td>2.27</td><td>0.81</td><td>21.96</td><td>0.16</td></tr><tr><td>MV-0.8</td><td>2.28</td><td>0.80</td><td>21.91</td><td>0.16</td></tr><tr><td>MV-0.2</td><td>2.26</td><td>0.78</td><td>22.04</td><td>0.16</td></tr><tr><td rowspan="3">R-RUM</td><td>HO</td><td>2.28</td><td>0.86</td><td>21.96</td><td>0.16</td></tr><tr><td>MV-0.8</td><td>2.27</td><td>0.81</td><td>22.14</td><td>0.16</td></tr><tr><td>MV-0.2</td><td>2.26</td><td>0.81</td><td>22.01</td><td>0.16</td></tr></table></body></html>

表4表明，JSD 策略的选题用时最少，其次是ASI策略，接着是Gini策略，用时最多的 IPA策略。IPA策略的选题用时是Gini策略的近10倍。每种选题策略在不同条件下用时基本不变，因为选题时间主要与选题策略算法的运算量，属性个数和题库容量有关，当属性个数确定和题库容量已知，选题算法的运算量起决定性作用。

![](images/3e47ade99c268b45f1f99d4dfd8e290f0286544ee2a3e9ecaabed6713adf46aa.jpg)  
图1不同测验长度的模式判准率

![](images/f8581b8dd654c9ae17a2676470e7859ab9d8459502e214bf3a4e3f00e3525022.jpg)  
图2不同测验长度的能力估计均方差  
图3不同测验长度的卡方值

→Gini GDINA DINA R-RUM ASI 500 500 500 PWACDI\*KL 8 450 400 450 400 广V JSD 广 50 200 150 150 100 00 100 50 0 101520 5101520 101520 10 1520 101520 101520 101520 101520 101520 HO MV-0.8 MV-0.2 HO MV-0.8 MV-0.2 HO MV-0.8 MV-0.2

# 6总结和讨论

# 6.1总结

本文利用基尼指数的优良性质，构造一种新的双目标CD-CAT的选题策略，模拟实验表明新策略的测量精度较高，兼顾题库利用均匀性并能快速实时响应，为同时兼顾宏观能力评估和微观认知诊断提供了新的更优的方法。

实验考察了3种CDM和3种不同被试知识状态分布下，4种双目标选题策略（Gini策略、ASI策略、IPA 策略和 JSD 策略）的表现，综合来看，得到如下结论（1）Gini策略和IPA 策略在分类精度指标，能力估计精度指标和题库使用均匀性指标上均具有相似的表现，测量精度高且受CDM模型和被试知识状态分布的影响较小，可以适用于实际测验中含多种认知诊断模型的混合题库。总体而言，Gini 策略稍好于 IPA 策略，且Gini 策略的选题用时仅为IPA 策略的十分之一；（2)Gini策略和ASI策略都是两种信息量线性加权的组合策略，在短测验时，两种选题策略在测量精度指标上的表现很接近，而在中长测验时，虽然 ASI策略的用时是Gini 策略的1/3，但ASI策略的测量精度和题库使用均匀性均不如Gini 策略;（3）Gini策略与JSD 策略相比，JSD 策略在题库使用均匀性和选题用时指标上有较大的优势，但其测量精度远不如Gini策略。

综上所述，短测验时，Gini策略、IPA策略和ASI策略均有较好的测量精度，都值得推荐。对于中长测验时，对于属性个数少和题库容量较小的情况下，推荐使用Gini 策略和 IPA策略，而当属性个数增多和题库容量增大时，推荐使用Gini 策略。当属性间高相关且属性个数非常多和题库容量非常大时，推荐使用ASI策略和 JSD 策略，ASI策略的测验精度稍高于 JSD 策略。

# 6.2 讨论

Gini 策略是基于被试知识状态类别的后验概率和被试能力估计置信区间的后验概率构造的，因此受CDM和被试知识状态分布的影响较小，这种构造方法直接反映后验概率的变化且采用了最小错误率贝叶斯决策确定被试的知识状态，因而测量的精度也非常高。基尼指数的线性加权方式，使得其对后验概率的变化相比熵而言更加敏感，从而有助于扩大选题范围提高题库利用均匀性，且加法运算速度较快，能满足Dual-CAT实时响应的需求。

在某些条件下（如被试的知识状态由高阶模型生成)，Gini策略的能力估计精度会稍低于IPA 策略，而此时Gini策略的模式判准率会稍高于IPA策略，可能的原因是组合策略中能力的信息量和知识状态的信息量共同作用选择下一题，两种信息量在选题过程中互相均衡的结果。Zheng和Chang（2016）指出当已知题库参数，公式（3）中的KL信息量可以预先计算，缩短了ASI策略的选题用时，而Gini策略是定义在随机变量后验概率，必须根据被试的作答反应实时计算，因此选题用时会稍有增加。

JSD 策略仅计算基于当前估计值的KL距离，运算量小，选题非常快，而Gini策略需考虑有限集合和区间范围内后验概率变化，需要求和与积分运算，因此选题耗时会超过ASI策略和 JSD 策略。当测验长度较短时，能力估计值和被试知识状态估计值偏离真值较远，基于他们当前估计值的JSD 策略的选题范围比较宽泛，从而使得题库的利用率会更加均匀；Gini策略不依赖于能力和知识状态的当前估计值，而依赖于他们的概率分布，选题会更趋集中。

Gini策略的测验精较高，但其题库利用率不如JSD策略。Wang,Chang 和Huebner(2011)的研究表明限制渐进法（Restrictive Progressive Method：RP）和限制阀值法（RestrictiveThresholdMethod：RT）能均衡测量精度和项目曝光率，下一步研究拟将Gini策略与RP 和RT 方法结合，提高Gini策略的题库利用均匀性。测量精度和题库利用均匀性是一对相互冲突的指标。使用控制项目曝光技术后，题库利用均匀性会更好，但也会带来测量精度下降的不利影响，如何权衡需要进一步研究。另外，使用控制项目曝光技术后，各选题策略之间的差异是否会消除，也有待进一步研究。当属性个数较多时和题库容量较大时，Gini策略的选题用时可能会超过用户的期望值（延时超2秒）（Nah,2004)，下一步研究拟将Gini策略与动态搜索算法（Zheng＆Wang,2017）结合，对其优化以减少选题用时。

本文采用分离建模的方法获得两类模型的参数来构建Dual-CAT的题库，题库项目是否完全拟合所关注的模型还需要进一步探查以期获得更准确的测量结果。文中Dual-CAT的题库参数的建立过程是先模拟CDM的参数和项目的属性向量，根据CDM模型获得反应数据，然后用反应数据估计IRT参数，这是目前研究中常用的方法（Daietal.,2016;Kang et al.,2017;Wang et al.,2012,2014)，能否采用先模拟 IRT的项目参数，根据 IRT 模型获得反应数据，然后用反应数据估计CDM参数和项目属性向量的方法构建题库？在这种方式构建题库下各选题策略的表现有待进一步探查。

随着测验数据的复杂性和测验要求的限定，选题策略的发展也要适应新测验形式的发展，比如属性多级化项目测验（涂冬波，蔡艳，2015）、多级评分项目测验（蔡艳，苗莹，涂冬波，2016）、多维项目测验（韩雨婷等,2018;Hsu＆Wang,2019）、多阶段CD-CAT（罗芬，王晓庆，丁树良，熊建华，2018;Kaplan&dela Torre,2020）、融入非统计约束的多阶段测验（Lin &Chang,2019;Liu,Cai,&Tu,2018）以及结合反应时的CAT 测验（Fan,Wang,Chang,& Douglas,2012;Huang,2020)，可探讨基于基尼指数的选题策略在这些测验场景下的效果及其应用。

奓考乂献   
Bock,R.D.,& Mislevy,R.J. (1982).Adaptive EAP estimation of ability in a microcomputer environment. Applied Psychological Measurement, 6(4), 431-444.   
Breiman,L.,Friedman,J.,Stone, C.J.,& Olshen,R.A.(1984). Classification and regression trees,Chapman& Hall /CRC, Boca Raton, FL.   
Cai,Y., Miao, Y. & Tu,D.B. (2016). The polytomously scored cognitive diagnosis computerized adaptive testing, Acta Psychologica Sinica, 48(10),1338-1346.   
[蔡艳，苗莹，涂冬波.(2016).多级评分的认知诊断计算机化适应测验．心理学报,48(10),1338-1346.]   
Chalmers,R.P. (2012). Mirt: a multidimensinal item response theory package for the R environment. Journal of Statistical Software, 48(6),1-29.   
Chang,H.H.,& Ying,Z.L.(1996). A global information approach to computerized adaptive testing. Applied Psychological Measurement, 20(3),213-229.   
Chen,P.,Li,Z.& Xin,T.(2O11).Anote on the uniformity ofitembank usage incognitive diagnostic computerized adaptive testing. Studies of Psychology and Behavior,37(1),212-216.   
[陈平，李珍，辛涛．(2011)．认知诊断计算机化自适应测验的题库使用均匀性初探．心理与行为研究,37(1), 212-216.]   
Cheng, Y. (2oo7). The dual information method for item selection in cognitive diagnostic computerized adaptive testing (Unpublished Master's thesis). University of Illinois at Urbana-Champaign.   
Cheng Y. (2009). When cognitive diagnosis meets computerized adaptive testing. Psychometrika.74(4),619-632.   
Cheng,Y.,& Chang, H. H. (20o9).The maximum priority index method for severely constrained item selection in computerized adaptive testing. British Journal of Mathematical and Statistical Psychology,62(2),369-383.   
Dai, B.Y., Zhang, M. Q.,&Li, G.M. (2016). Exploration of item selection in dual purpose cognitive diagnostic computerized adaptive testing: Based on the RRUM. Applied Psychological Measurement,40(8), 625-640.   
Du, X. X. (2010).Anew strategyofitem selection ofcognitive diagnosis computerized adaptive testing (Unpublished Master's thesis). Jiangxi Normal University, Nanchang, China.

[杜宣宣.(2010).具有认知诊断功能的计算机化自适应测验的选题策略研究(硕士学位论文).江西师范大学，

南昌.]   
de la Torre,J.(2011). The generalized DINA model framework.Psychometrika,76(2),179-199.   
de laTorre,J.,&Douglas,J. (2o04).Higher-order latent trait models forcognitive diagnosis.Psychometrika,69(3), 333-353.   
Fan, Z.,Wang, C., Chang,H. H.,& Douglas,J. (2012). Utilizing response time distributions for item selection in CAT. Journal of Educational and Behavioral Statistics,37(5), 655-670.   
Han,Y.T., Gao,X.L., Wang,D.X., Cai,Y.,& Tu,D.B. (2018). Item selection methods in multidimensional polytomous computerized adaptive testing. Journal of Psychological Science, 41(6),1500-1507.   
[韩雨婷，高旭亮，汪大勋，蔡艳，涂冬波.(2018).多级评分项目的多维 CAT 选题策略开发．心理科学, 41(6),1500-1507.]   
Hartz,S.M.(20o2).A bayesian framework for the unified model for assessing cognitive abilities: blending theory with practicality (Unpublished Doctoral dissertation). University of Ilinois at Urbana-Champaign, UrbanaChampaign, IL.   
Hsu, C.L.,& Wang,W.C.(2015). Variable-length computerized adaptive testing using the higher order DINA model. Journal of Educational Measurement, 52(2),125-143.   
Hsu, C.L.,& Wang, W. C.(2019). Multidimensional computerized adaptive testing using non-compensatory item response theory models. Applied Psychological Measurement, 43(6), 464-480.   
Huang,H. Y. (2020). Utilizing response times in cognitive diagnostic computerized adaptive testing under the higher-order deterministic input, noisy ‘and' gate model. British Journal of Mathematical and Statistical Psychology, 73(1),109-141.   
Junker,B.W.,& Sijtsma, K.(20o1).Cognitive assessment models with few assumptions,and connections with nonparametric item response theory. Applied Psychological Measurement, 25(3), 258-272.   
Kang,H.A., Zhang,S.S.,& Chang, H. H. (2017). Dual-objective item selection criteria in cognitive diagnostic computerized adaptive testing. Journal of Educational Measurement, 54(2),165-183.   
Kaplan,M.,& de la Torre, J. (2020). Ablocked-CAT procedure for CD-CAT.Applied Psychological Measurement, 44(1), 49-64.   
Kaplan, M., de la Torre, J.,& Barrada, J. R. (2o15). New item selection methods for cognitive diagnosis computerized adaptive testing. Applied Psychological Measurement,39(3),167-188.   
Li,H.(2012). Statistical learning method.Beijing: Tsinghua University Press.   
[李航.(2012)．统计学习方法.北京：清华大学出版社.]   
Lin, C.J.,& Chang,H.H. (2019). Item selection criteria with practical constraints in cognitive diagnostic computerized adaptive testing. Educational and Psychological Measurement, 79(2),335-357.   
Liu,S. C.,Cai,Y.&Tu,D.B. (2018). On-the-flyconstraint-controled assembly methods for multistage adaptive testing for cognitive diagnosis. Journal of Educational Measurement, 55(4),595-613.   
Lord, M.F.(1980).Applications ofitem response theory to practical testing problems. Hillsdale NJ: Erlbaum.   
Luo,F.,Wang, X. Q.,Ding,S.L., Xiong,J. H.(2018).The design and selection strategies ofadaptive multigroup Testing for Cognitive Diagnosis. Journal of Psychological Science,41(3),720-726.   
[罗芬，王晓庆,丁树良，熊建华.(2018).自适应分组认知诊断测验设计及其选题策略.心理科学,41(3),720- 726.]   
Ma, W.,& de la Torre, J. (2020). GDINA: The generalized DINA model framework. R package version 2.7.9, https://CRAN.R-project.org/package=GDINA.   
McGlohen, M. K.,& Chang, H. H. (2008). Combining computer adaptive testing technology with cognitively diagnostic assessment. Behavior Research Methods,40(3),808-821.   
Nah,F. F. H. (2004). A study on tolerable waiting time: how long are web users wiling to wait? Behaviour and Information Technology,23(3),153-163.   
Quinlan, J. R. (1986). Induction of decision trees.Machine Learning,1(1),81-106.   
Quinlan, J. R. (1993). C4.5: programs for machine learning. Morgan Kaufmann, San Mateo, CA   
Rupp,A.A.,Templin,J.,& Henson,R.A. (2o10).Diagnostic measurement: theorymethod,and application.New York: The Guilford Press.   
Tatsuoka, C.(2oo2). Data analytic methods for latent partially ordered clasification models.Journal of the Royal Statistical SocietySeries C:Applied Statistics,51(3),33750.   
Tu,D.B.,Cai,Y. (2015).The Development of CD-CAT with polytomous attributes.Acta Psychologica Sinica, 47(11), 1405-1414.   
[涂冬波，蔡艳.(2015).基于属性多级化的认知诊断计算机化自适应测验设计与实现．心理学报,47(11), 1405-1414.]   
Veerkamp, W. J.,& Berger, M. P.F. (1994). Some new item selection criteria for adaptive testing (Research Rep. 94-6).Enschede,The Netherlands: University of Twente, Department of Educational Measurement and Data Analysis.   
Wang,C.，& Chang,H.H. (2011). Item selection in multidimensional computerized adaptive testing-gaining information from different angles.Psychometrika,76(3),363-384.   
Wang,C.,Chang,H.H.,&Huebner,A. (20l1).Restrictive stochastic item selection methods incognitive diagnostic computerized adaptive testing. Journal of Educational Measurement, 48(3),255-273.   
Wang, C., Chang,H.H.,& Douglas,J. (2012). Combining CAT with cognitive diagnosis: a weighted item selection approach. Behavior Research Methods,44(1),95-109.   
Wang,C., Zheng,C.J.,& Chang,H.H.(2014).An enhanced approach to combine item response theory with cognitive diagnosis in adaptive testing.Journal of Educational Measurement,51(4),358-380.   
Xu, X.L., Chang,H.H.,&Douglas,J. (2O03,April). A simulation study to compare CAT strategies for cognitive diagnosis. Paper presented at the annual meeting of National Council on Measurement in Education, Chicago, IL.   
Zhang,X.G.(2010).Pattern recognition(Third Edition).Beijing: Tsinghua University Press.   
[张学工.(2010)．模式识别（第三版）．北京：清华大学出版社.]   
Zheng,C.J.,& Chang, H.H.(2016). High-eficiency response distribution-based item selection algorithms for short-length cognitive diagnostic computerized adaptive testing. Applied Psychological Measurement, 40(8), 608-624.   
Zheng, C.J., He,G.,& Gao,C.L.(2018).The information product methods: a unified approach to dual-purpose computerized adaptive testing. Applied Psychological Measurement, 42(4),321-324.   
Zheng, C.J.,& Wang,C. (2017).Application of binary searching for item exposure control in cognitive diagnostic computerized adaptive testing. Applied Psychological Measurement, 41(7),561-576.   
Zhou, Z. H. (2016). Machine learning. Beijing: Tsinghua University Press.   
[周志华.(2016)．机器学习．北京：清华大学出版社.]

# A New Dual-Objective CD-CAT Item Selection Method Based on the Gini Index

LUO Fen1,2; WANG Xiaoqing²; CAI Yan1; TU Dongbol

(1 School of Psychology, Jiangxi Normal University, Nanchang 33oo22,China) (² College of ComputerInformation Engineering,Jiangxi Normal University,Nanchang,330022) Existing literature has shown that dual-objective CD-CAT testing can facilitate the achievement of measurement objectives for both formative and summative assessments. And the Gini Index can be used as a measurement for the degree of uncertainty of random variables since a smaller Gini value indicates a lower degree of uncertainty. Hence, this paper proposed a Gini-Index-based selection method for dual-objective CD-CAT,and it measured the changes in the posterior probability of knowledge state and confidence interval for latent traits estimation. By adopting the Bayesian Decision Theory, the potential information of participants could be detected based on participants’ responses and changes in posterior probability distribution of two the random variables.

Monte Carlo Simulation was used to test the performances of the selection method based on Gini, ASI, IPA and JSD,respectively. The item banks measured 5 attributes consisting of 250 items in total, and each item measured 3 attributes at most. The true knowledge state of each participant was generated by HO-CDM and Multivariate Normal Models (both means were O and covariance coefficient was 0.8 and 0.2, respectively). G-DINA, DINA and R-RUM were adopted as the cognitive diagnostic models and the item bank of each of these three models included both CDM and 2PL parameters. Specifically, CDM parameters were generated by a G-DINA package in R software with the slipping and guessing parameters randomly selected from uniform distribution in a range from 0.05 to 0.25.The 2PL parameters were estimated by factoring in the responses elicited from 3,0oO participants'responses to allitems in item banks using the mirt package. Four indexes, namely the pattern measurement rates, root mean square error of latent trait, chi-square value and time needed for item selection,were adopted in comparing the efficiency of different item selection methods.The value for each index was the mean of 10 repeated simulations of 1,Ooo participants' responses to all item bank.

The results showed that (1) The Gini and IPA selection methods had similar performance in terms of pattern measurement rates, root mean square error of latent trait and chi-square value. Both methods were high in precision measurement and low in sensitivity to CDM and the distribution of participants' cognitive patterns, making both methods applicable to the item banks featuring a mixture of cognitive diagnosis models. By comparison, the Gini method outperformed slightly the IPA method in pattern measurement rates and time needed for item selection in which the Gini method was only one-tenth that of the IPA method; (2) Both the Gini and ASI selection methods were weighted linear combination approaches. The performances of the two methods were very close in the short test. In the long test, however, although time needed for item selection using the ASI method was only one-third that of the Gini method, the latter was superior to the former in terms of measurement accuracy and chisquare value; (3) Although the JSD method outperformed the Gini method in terms of uniformity of item bank usage and time needed for item selection, its measurement accuracy Was far less than the latter.

To summarize, the Gini, IPA and ASI selection methods all have good measurement accuracy and hence are all recommended for short tests. For medium and long tests with a limited number of atributes and a smaller item bank, the Gini and IPA selection methods are recommended.As the number of atributes and item bank size grow, the Gini method is recommended. When there are high correlations among different atributes, as well as a large number of attributes and big item bank size, the ASI and JSD selection methods are recommended with the ASI method slightly outperforming the JSD method in measurement accuracy.

Key Words Cognitive Diagnostic; Items Response Theory; Gini Index; Dual objective CDCAT; selection method