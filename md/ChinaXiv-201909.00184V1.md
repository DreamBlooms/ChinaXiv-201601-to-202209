# 基于类别水平的多级计分认知诊断Q矩阵修正：相对拟合统计量视角\*

汪大勋」高旭亮²蔡艳」涂冬波1（1江西师范大学心理学院，南昌，330022）（²贵州师范大学心理学院，贵阳，550000）

摘要 多级计分认知诊断模型的开发对认知诊断的发展具有重要作用，但对于多级计分模型下的Q矩阵修止还有待研究。本研究尝试对多级计分认知诊断Q矩阵修止进行研究，并聚焦更具诊断价值的基于项目类别水平的Q矩阵修正。将相对拟合统计量应用于多级计分认知诊断Q矩阵修正，并与已有方法 stepwise 方法（Ma&de la Torre,2019）进行比较。研究表明：BIC方法对多级计分认知诊断模型的Q矩阵修正具有较高的模式判准率和属性判准率，其对Q矩阵的恢复率也高于 stepwise方法，BIC 方法修正后的Q矩阵与数据更加拟合；在复杂模型中，相对拟合指标 BIC 比 AIC 和-2LL 表现更好，在实践中，使用者可以选择 BIC 法进行测验Q矩阵修正；Q矩阵修正效果受到被试人数的影响，增加被试人数可以提高Q矩阵修正的正确率。总之，本研究为多级计分认知诊断Q矩阵修正提供了重要的方法支持。

关键词 认知诊断；Q矩阵；seq-GDINA；BIC

# 1引言

传统心理与教育测验通过对学生的能力进行评估和排序，来评价学生的学习效果或者进行选拔，而对分数背后的心理加工过程和认知技能无法提供详细的信息。随着测评技术的发展，人们希望测验能够提供更详细的诊断信息，从而进行针对性的补救或因材施教。认知诊断作为认知心理学和心理测量学的结合，可以实现对人的内部心理加工过程和认知技能的诊断，从而为针对性地补救和教师因材施教提供依据(Chang,2015;Chen，2017；张华华，汪文义,2016)。为此，研究者们开发了许多具有认知诊断功能的计量模型（Cognitive DiagnosisModels,CDMs），常见的有 DINA（Haertel,1984;）、NIDA（Maris,1999;）、DINO（Templin& Henson,2006）、R-RUM（Hartz & Roussos,2008）、A-CDM 和 G-DINA（de la Torre,2011)等，这些模型均适用于0-1计分的测验情境。为了适应多级评分的测验情景，研究者们也开发出了能用于多级计分的认知诊断模型，如多级计分的GDM(von Davier,2008)，P-DINA模型（涂冬波，蔡艳，戴海琦，丁树良，2010）、多级的LCDM（Hansen,2013）、seq-GDINA（Ma&de la Torre,2016）等。与其他的多级计分模型不同，seq-GDINA 模型可以从项目水平和得分类别水平分别定义Q矩阵，Ma 和dela Torre（2016）将基于项目水平的Q阵定义为非约束化的Q阵(UnrestrictedQ),而基于类别水平的Q阵定义为约束化的Q阵(RestrictedQ)。如对于算式 $\sqrt { 4 5 / 3 - 6 }$ 的求解分为三个步骤：即 step 1 计算 $4 5 / 3 { = } 1 5$ ,step 2计算 $1 5 - 6 = 9$ ，step 3计算 ${ \sqrt { 9 } } = 3$ 。三个步骤分别考察了三个属性 A1(除法)、A2(减法)、A3(根号运算)。项目水平的Q矩阵将该题测量Q阵定义为 $q _ { j } = \left[ 1 1 1 \right]$ ，即该题测量了三个属性；而基于得分类别的Q矩阵则需要对该题的每一步骤（或每一个得分类别）进行Q矩阵标定，将该题基于类别水平的Q矩阵定义为 $q _ { j } = \left[ { 1 0 0 } \atop { 0 1 0 } \right] ,$ 即 step1测量了A1，step 2测量了A2，step 3测量了A3。相比较而言，基于得分类别的Q矩阵可以更加深入地探测出学生的解题过程，从而能提高被试分类的准确性（Ma&dela Torre,2016）。关于项目水平Q矩阵和类别水平Q矩阵的详细介绍可以参考Ma和de la Torre (2016)的文献。总体来讲，基于得分类别的Q矩阵能更准确地反应出被试每个步骤需要的属性。而在实际中得分类别的Q矩阵的标定比项目水平Q矩阵的标定更为复杂，为每个类别标定Q矩阵也增加了专家的工作负担。在Q矩阵的修正上，对得分类别的Q矩阵修正也比项目水平Q矩阵修正的难度更大，因为对得分类别Q矩阵的修正需要考察所有题目每个类别的Q矩阵，而项目水平的Q矩阵则只需考虑整个项目整体测量了哪些属性，因此相对容易。

在对Q矩阵的修正上，国内外研究者提出许多种方法。其中一部分方法只适用于简化的认知诊断模型（如DINA 和DINO 模型），如：γ法（涂冬波，蔡艳，戴海崎，2012）、海明距离的方法（汪大勋，高旭亮，韩雨婷，涂冬波，2018）、ICC-IR法（汪大勋，高旭亮，蔡艳，涂冬波，2018）、δ法（dela Torre，2008）、RSS法（Chiu，2013）。除此之外，研究者还提出一些适用于饱和认知诊断模型的Q矩阵修正方法，如GDI法(de la Torre＆ Chiu,2016)、基于似然的方法（Xu& Shang，2018）和基于残差的方法（Chen,2017)。相比较而言，后三种方法的适用范围更广，既适用于饱和的认知诊断模型也适用于简化的认知诊断模型。而三种可以适用于饱和模型的方法中，GDI方法计算相对复杂，且需要设定一个截断值中 $\mathrm { P V A F = } 0 . 9 5$ ）。并且通过预研究发现，该方法受样本量影响较大，在小样本量（ $\scriptstyle \cdot - 1 = 5 0 0$ ）中该方法表现不理想。而基于残差的方法虽然可以在测验层面考察测验属性是否多余或缺失，但该方法对题目层面的属性多余不够敏感(Chen,2017)。而 Xu 和 Shang（2018）的方法采用 TLP(truncated L1 penalty function)的正则化算法，由估计的项目参数稀疏矩阵来推断题目的 $q$ 向量，并结合信息指标（BIC）来进行Q矩阵估计或修正，他们的研究不仅进行了理论证明，Monte Carlo 实验也表明其方法具有较好的效果。此外，Chen，de la Torre 和 Zhang（2013）将-2LL、AIC 和BIC 指标用于对不同Q矩阵的鉴别。研究发现在DINA 模型中，-2LL 指标表现较好；而在饱和模型中，-2LL 倾向于选择在原有Q矩阵基础上增加属性的Q矩阵，而BIC 指标的表现是最出色的。以上方法均是在0-1模型中的Q矩阵修正方法，而对于多级计分模型中的Q矩阵修正的研究,Ma 和 de la Torre (2019)提出了GDI和 wald 检验相结合的 stepwise 方法进行 seq-GDINA 模型的Q矩阵修正。该方法先选择单属性 $q$ 向量中具有最大GDI值的 $q$ 向量作为基础，再用wald 检验是否显著来决定是否增加或删除属性，并通过计算wald 检验以后 $q$ 向量的GDI值来决定是否终止。该方法在确定每个类别的 $q$ 向量时，需要进行多次的wald 检验，并计算标准误，计算相对复杂。此外，该方法是从属性的角度来考察属性是否缺失或冗余，而对于Q矩阵修正后模型的整体拟合并没有考虑。

因此本研究尝试使用模型的相对拟合统计量对多级计分认知诊断模型Q矩阵进行修正，并聚焦更具诊断价值的基于项目类别水平的Q矩阵修正方法。具体来讲，本研究将模型拟合统计量中的-2LL、AIC(Akaike's Information Criterion）和 BIC(Bayesian Information Criteria）指标用于多级计分认知诊断模型的Q矩阵修正。本文采用的方法与 $\mathrm { \Delta X u }$ 和 Shang (2018)方法有相似之处，都是需要对模型参数进行估计，并使用信息指标来进行Q矩阵修正。并且在修正Q矩阵时都是在其余题目Q矩阵保持不变的情况下，逐题（或类别）对 $q$ 向量进行确定。而两种方法的区别在于，Xu 和 Shang（2018）的方法采用 TLP(truncatedL1 penaltyfunction)的正则化算法，由估计的项目参数稀疏矩阵来推断题目的 $q$ 向量，并结合信息指标（BIC）来进行Q矩阵修正，因此并不需要对所有可能的 $q$ 向量进行估计。而本文则在所有可能的 $q$ 向量中通过拟合统计量挑选出最优的 $q$ 向量。此外 $\mathrm { \Delta X u }$ 和 Shang（2018）的方法是用于二级计分的Q矩阵估计或修正，而本文则是对多级计分Q矩阵修正进行研究。通过Monte Carlo模拟研究和实证数据分析来验证本文的方法并与Ma和de la Torre (2019)提出的stepwise方法进行比较，从而为实际工作者在多级计分认知诊断中Q矩阵的修正与标定提供方法支持。

# 2seq-GDINA模型介绍

前已述及，在众多多级计分CDMs中，seq-GDINA模型能从得分类别标定Q矩阵，从而更深入细致地探查被试的解题过程。此外，该模型使用G-DINA模型作为每个类别上的链接函数，在不同的假设条件下，seq-GDINA 模型可以转化为不同的多级计分模型（如seq-DINA 和 seq-RRUM），因此该模型更加灵活。因此本研究采用 Ma 和de la Torre（2016）开发的seq-GDINA模型进行研究。对该模型的介绍如下：

对于属性掌握模式为 $\alpha _ { c }$ 的被试，其在项目 $j$ 上 $h$ 类别的正确作答概率为 $S _ { { \scriptscriptstyle j } } ( h \vert \alpha _ { { \scriptscriptstyle c } } )$ 。那么，

$$
S _ { j } ( h | \alpha _ { c } ) = { \left\{ \begin{array} { l l } { 1 , } & { { \mathrm { i f ~ } } h = 0 } \\ { 0 , } & { { \mathrm { i f ~ } } h = H _ { j } + 1 } \end{array} \right. }
$$

其中 $H _ { _ j }$ 为题目 $j$ 的类别总和，则该被试在项目 $j$ 上得 $h$ 分的概率为：

$$
p \big ( X _ { j } = h | \alpha _ { c } \big ) = \big [ 1 - S _ { j } \big ( h + 1 | \alpha _ { c } \big ) \big ] \prod _ { x = 0 } ^ { h } S _ { j } \big ( x | \alpha _ { c } \big )
$$

则对于每一种掌握模式的被试，其在项目 $j$ 上得各种分数的概率之和为1。

$$
\sum _ { h = 0 } ^ { H _ { j } } P \big ( \boldsymbol X _ { j } = h | \alpha _ { c } \big ) = 1 \ \forall c
$$

被试在题目 $j$ 上每个类别的得分概率受到题目 $j$ 每个类别测量属性的影响。如在一个属性个数为 $K$ 的测验中，设定 $\boldsymbol { K } _ { j } ^ { * }$ 为题目 $j$ 测量的属性个数， $\boldsymbol { K } _ { j h } ^ { * }$ 为项目 $j$ 类别 $h$ 所测量的属性个数。 $L = 2 ^ { K _ { j h } ^ { * } }$ 为所有简化后的掌握模式， $\boldsymbol { \alpha } _ { l j h } ^ { * }$ 表示第 $l$ 种掌握模式。对于掌握模式 $\boldsymbol { \alpha } _ { l j h } ^ { * }$ ，其在项目 $j$ 上 $h$ 类别的概率函数表示为：

$$
S _ { j } \left( h \middle | \alpha _ { l j h } ^ { * } \right) = \phi _ { j h 0 } + \sum _ { k = 1 } ^ { K _ { j h } ^ { * } } \phi _ { j h k } \alpha _ { l k } + \sum _ { k ^ { \prime } = k + 1 } ^ { K _ { j h } ^ { * } } \sum _ { k = 1 } ^ { K _ { j h } ^ { * } - 1 } \phi _ { j h k k ^ { \prime } } \alpha _ { l k } \alpha _ { l k ^ { \prime } } + \dots + \phi _ { j h 1 2 \dots K _ { j h } ^ { * } } \prod _ { k = 1 } ^ { K _ { j h } ^ { * } } \alpha _ { l k } \alpha _ { l k ^ { \prime } } .
$$

其中 $\phi _ { j h 0 }$ 是截距参数， $\phi _ { j h k }$ 是属性 $\alpha _ { l k }$ 的主效应， $\phi _ { j h k k ^ { \prime } }$ 是属性 $\alpha _ { l k }$ 和 $\alpha _ { l k ^ { \prime } }$ 的交互效应，（20 $\phi _ { j h 1 2 . . . k _ { j } ^ { * } }$ 是所有属性的交互效应。与GDINA 模型相似（de la Torre,2011），在不同约束条件下 seq-GDINA 模型可以转换为 seq-DINA、seq-RRUM 等模型。

# 3多级计分认知诊断Q矩阵修正

在认知诊断中定义题目 $j$ 的 $q$ 向量时，在其他题目Q矩阵不变的情况下，在所有可能的$q$ 向量中能使模型相对拟合更好的 $q$ 向量应该为题目 $j$ 的 $q$ 向量。而认知诊断中常用的模型相对拟合指标包括-2LL、AIC 和BIC。在约束模型（如DINA）中，题目 $q$ 向量标定错误会导致题目猜测参数和失误参数增加，从而降低模型的似然值，因此在约束模型中-2LL 指标可以挑选出恰当的 $q$ 向量。而在复杂模型中，已有研究（Chen etal.，2013；Chen，2017）表明，若在原有Q矩阵基础上增加属性（overspecified）会产生更大的模型似然（由于模型参数个数增多）。所以在复杂模型中，-2LL 指标通常会挑选全为1的 $q$ 向量 $\mathbf { \check { q } } = [ I I I I ]$ ）作为题目 $j$ 的 $q$ 向量。因此在复杂模型中对题目 $j$ 的 $q$ 向量进行标定时需要对模型的参数个数进行惩罚，而AIC 和BIC 指标则是在-2LL 的基础上对模型的参数个数进行了惩罚。

# 3.1-2LL方法

在0-1 计分模型Q矩阵修正中,如果一个测验包含了 $J$ 个题目， $K$ 个属性，用 $Q _ { r }$ (reducedQ-matrix）来表示所有可能的属性模式的集合，当属性之间没有关系时 $Q _ { r }$ 里包含了 $2 ^ { K } - 1$ 种属性模式。使用-2LL方法来进行Q矩阵标定时，是将最小-2LL所对应的属性模式作为题目$j$ 的属性模式。即分别将 $\boldsymbol { \mathcal { Q } } _ { r }$ 里的属性模式作为题目 $j$ 的属性模式（其余 $J { - } 1$ 个题目的Q矩阵不变），与其余 $J { - } 1$ 个题目一起进行参数估计，并计算-2LL。将最小-2LL所对应的属性模式作为题目 $j$ 的属性模式，公式表示为：

$$
\stackrel { \wedge } { q } _ { j } = \arg \operatorname* { m i n } _ { q _ { l } \in \mathcal { Q } _ { r } } \quad - 2 \mathrm { l n } ( L ( X \big | \stackrel { \wedge } { \beta } , \mathcal { Q } _ { j l } ^ { T } ) )
$$

其中 $L ( X | \hat { \boldsymbol { \beta } } , Q _ { \mathcal { I } \mathcal { I } } ^ { T } ) = \prod _ { i = 1 } ^ { N } \prod _ { j = 1 } ^ { J } \sum _ { \alpha _ { c } \in Q _ { s } } L \bigg ( X _ { i j } \Big | \alpha _ { c } , \hat { \boldsymbol { \beta } } _ { j } , q _ { j } \bigg ) \pi ( \alpha _ { c } ) , L \bigg ( X _ { i j } \Big | \alpha _ { c } , \hat { \boldsymbol { \beta } } _ { j } , q _ { j } \bigg )$ 是当被试 $i$ 的掌握模式为 $\alpha _ { c }$ 时，题目 $j$ 的似然， $\pi ( \alpha _ { c } )$ 是掌握模式为 $\alpha _ { c }$ 的后验概率， $Q _ { s }$ 是所有可能掌握模式的集合。 $\boldsymbol { Q } _ { j l } ^ { T }$ 是当题目 $j$ 的属性模式为第 $l$ 种属性模式时，整个测验的Q矩阵。

与0-1计分情况下不同，在多级计分模型中，需要依次对每个题目的每个类别 $q$ 向量进行验证与修正。同样可以将最小-2LL所对应的属性模式作为题目 $j$ 第 $h$ 类别的属性模式。分别将 $\boldsymbol { \mathcal { Q } } _ { r }$ 里的属性模式作为题目 $j$ 第 $h$ 类别的属性模式（题目 $j$ 的其余类别和其他 $J { - } 1$ 个题目的所有类别Q矩阵均保持不变），与其余题目一起进行参数估计，并计算-2LL。最小-2LL所对应的属性模式作为题目 $j$ 第 $h$ 类别的属性模式，表示为：

$$
\stackrel { \wedge } { q } _ { j h } = \arg \quad \operatorname* { m i n } _ { q _ { l } \in \mathcal { Q } _ { r } } \quad - 2 \mathrm { l n } ( L ( X \big | \stackrel { \wedge } { \beta } , Q _ { j h l } ^ { T } ) )
$$

其中 $\boldsymbol { Q } _ { j h l } ^ { T }$ 是当题目 $j$ 第 $h$ 类别的属性模式为第 $l$ 种属性模式 $q _ { l }$ 时，整个测验的Q矩阵。

使用-2LL方法来修正Q矩阵时，需要对所有题目的所有类别依次循环验证，由此可进行Q矩阵修正。

# 3.2 AIC方法

AIC（Akaike's InformationCriterion）指标是由Akaike（1974）开发的信息指标，是心理测量领域常用的测验相对拟合指标，可用于比较模型的相对拟合程度。与-2LL方法相似，在使用AIC 指标对题目 $j$ 第 $h$ 类别的 $q$ 向量进行标定时，将 $\boldsymbol { \mathcal { Q } } _ { \boldsymbol { r } }$ 里的所有属性模式依次作为题目 $j$ 第 $h$ 类别的属性模式，与其余题目一起进行参数估计，并计算模型的AIC 指标，将AIC 指标最小的属性模式作为题目 $j$ 第 $h$ 类别的属性模式。AIC指标的计算公式如下：

$$
A \mathbf { I C } = - 2 L L + 2 d
$$

其中 $L$ 为模型的边际似然，其计算方法与-2LL方法相同， $d$ 为需要估计参数的个数。相对于-2LL方法，AIC 指标考虑了参数个数的影响，参数个数多的属性模式将会受到惩罚。

# 3.3BIC方法

BIC（Bayesian Information Criteria）指标是由 Schwarz（1978）开发的信息指标，通常与 AIC 指标一起用于模型比较。与AIC 指标相比，BIC 指标还考虑了样本量对模型拟合度的影响。BIC 指标的计算公式如下：

$$
\mathrm { B I C } = - 2 L L + d { \times } l n ( N )
$$

其中 $N$ 为被试样本量， $L$ 和 $d$ 分别为模型的边际似然和参数个数。使用BIC指标来标定题目 $j$ 第 $h$ 类别的属性模式的方法与AIC 指标相同，最后选择具有最小BIC 指标的属性模式作为题目 $j$ 第 $h$ 类别的属性模式。

3.4 穷尽算法（exhaustive search algorithm）和顺序算法（sequential search algorithm）假设 $q ^ { ( h ) } \not \to \mathcal { Q } _ { r }$ 中第 $h$ 个 $q$ 向量， $K ^ { ( h ) }$ 为 $q ^ { ( h ) }$ 的属性个数， $q ^ { ( h ^ { \prime } ) } \leq q ^ { ( h ) }$ 表示 $q ^ { ( h ^ { \prime } ) }$ 嵌套于 $q ^ { ( h ) }$ （de la Torre,2011）。用 $S _ { j }$ 表示 $q$ 向量的集合。

穷尽算法是分别将 $Q _ { r }$ 中的属性模式作为题目 $j$ 第 $h$ 类别的属性模式，计算出相对拟合指标后挑选出最优的属性模式，即集合 $S _ { j } = \bigl \{ q ^ { ( h ) } \bigl | q ^ { ( h ) } \in Q _ { r } \bigr \}$ 中拟合最好的 $q$ 向量作为题目 $j$ 第 $h$ 类别的 $q$ 向量。这样的方法计算比较耗时，如当 $K { = } 5$ 时，对每个类别的 $q$ 向量的确定，穷尽算法需要估计 $2 ^ { 5 } - 1 = 3 1$ 次。

顺序算法包括：（1）增加属性算法（forward search algorithm）是先从单属性 $q$ 向量中挑选出拟合最好的 $q$ 向量，记为 $q ^ { ( y ) }$ ，再比较集合$S _ { \jmath } = \left\{ q ^ { ( h ) } \middle | q ^ { ( h ) } \in \mathcal { Q } _ { r } , q ^ { ( \upsilon ) } \leq q ^ { ( h ) } , K ^ { ( h ) } = K ^ { ( \upsilon ) } + 1 \right\}$ $q$ 向量与 $q ^ { ( y ) }$ 的拟合。如果集合中拟合最好的 $q$ 向量的拟合指标优于 $q ^ { ( y ) }$ ，则用该 $q$ 向量更新 $q ^ { ( y ) }$ 。重复该步骤直到 $S _ { j }$ 中没有 $q$ 向量拟合优于 $q ^ { ( y ) }$ 或 $q ^ { ( y ) }$ 包含了所有属性（即 $\pmb q ^ { ( y ) } = \pmb I ^ { \dag }$ ）。（2）删除属性算法（backward searchalgorithm）是从全为1的 $q$ 向量出发，即 $\pmb q ^ { ( y ) } = \pmb I$ 。然后比较集合（204号 $S _ { j } = \left\{ q ^ { ( h ) } \middle | q ^ { ( h ) } \in \mathcal { Q } _ { r } , q ^ { ( h ) } \leq q ^ { ( \nu ) } , K ^ { ( h ) } = K ^ { ( \nu ) } - 1 \right\} ^ { ( h ) }$ 的 $q$ 向量与 $q ^ { ( y ) }$ 的拟合，如果集合中拟合最好的 $q$ 向量的拟合指标优于 $q ^ { ( y ) }$ ，则用该 $q$ 向量更新 $q ^ { ( y ) }$ 。重复该步骤直到 $S _ { j }$ 中没有 $q$ 向量拟合优于 $q ^ { ( y ) }$ 或 $q ^ { ( y ) }$ 只测量了一个属性（即 $K ^ { ( y ) } = 1$ ）。（3）先增加属性后删除属性算法（forward-then-backward search algorithm）是将原始 $\mathrm { ~ Q ~ }$ 矩阵中专家给定的 $q$ 向量作为 $q ^ { ( y ) }$ 在此基础上先进行增加属性算法，然后进行删除属性算法。（4）先删除属性后增加属性算法（backward-then-forward search algorithm）也将原始Q矩阵中专家给定的 $q$ 向量作为 $q ^ { ( y ) }$ ，在此基础上先进行删除属性算法，然后进行增加属性算法。

顺序算法中增加属性算法（forward search algorithm）和删除属性算法（backward searchalgorithm）并没有利用到专家给定的Q矩阵信息，而后两种算法则是在专家给定 $q$ 向量的基础上进行的搜索算法。此外，后两种顺序算法在每个类别上需要估计的次数会根据该类别$q$ 向量的错误程度变化，但相对于穷尽算法，顺序算法可以大大减少计算次数。

# 3.5Q矩阵修正步骤

将需要修正的原始Q矩阵定义为 $\boldsymbol { Q } ^ { ( 0 ) }$ ，这个Q矩阵通常是由专家界定。假设一个测验包含 $J$ 个题目，每个题目包含 $H _ { j }$ 个类别（每个题目类别数可能不同），则该测验共有$H = \sum _ { j = 1 } ^ { J } H _ { j }$ H=∑H,个类别，将所有类别的集合定义为S°={,,H}。具体步骤如下:

步骤1：从测验（ ${ S } ^ { \left( 0 \right) }$ ）中抽取出第一个题目 $j$ ，对其第1个类别的 $q$ 向量进行验证。其他 $J { - } 1$ 个题目以及题目 $j$ 其他类别的Q矩阵保持不变。

步骤2：使用顺序算法根据-2LL 指标（如果修正方法为AIC或BIC方法，则分别计算AIC 和 BIC 指标）挑选出题目 $j$ 第1个类别最优-2LL 指标（或 AIC、BIC 指标）所对应的 $q$

向量。

步骤3：重复步骤1-步骤2，确定第 $j$ 题其他类别的最优 $q$ 向量，方法与题目 $j$ 第1个类别的方法相同。

步骤4：根据步骤1-步骤3，则完成对题目 $j$ 所有类别最优 $q$ 向量的确定。重复步骤1-步骤3，对剩余题目所有类别的最优 $q$ 向量进行确定。直到确定完所有类别的最优 $q$ 向量。

步骤5：在所有类别中，挑选修改后相对拟合指标（-2LL、AIC、BIC）达到最优的 $q$ 向量进行修改，并将该类别从 ${ S } ^ { \left( 0 \right) }$ 中移除。删除类别后的集合表示为 ${ S } ^ { ( 1 ) }$ ，修改后的Q矩阵表示为 $\boldsymbol { Q } ^ { ( 1 ) }$ 。

步骤6：验证 $\boldsymbol { Q } ^ { ( 1 ) }$ 与 $\boldsymbol { Q } ^ { ( 0 ) }$ 是否相同。如果 ${ \boldsymbol { Q } } ^ { ( 0 ) } \neq { \boldsymbol { Q } } ^ { ( 1 ) }$ ，则将 $\boldsymbol { Q } ^ { ( 0 ) }$ 替换为 $\boldsymbol { Q } ^ { ( 1 ) }$ ， ${ S } ^ { \left( 0 \right) }$ 替换为 $S ^ { ( 1 ) }$ ，重复步骤1-步骤5。当 ${ S } ^ { \left( 0 \right) } = \varnothing$ 或 $Q ^ { ( 0 ) } = Q ^ { ( 1 ) }$ ，则算法停止。

为了探讨不同方法在多级计分认知诊断中Q矩阵修正的效果。模拟研究考查了不同方法在不同样本量、Q矩阵错误类型以及不同的多级计分认知诊断模型下的效果，并将其与Ma 和dela Torre（2019）的 stepwise方法进行比较。具体为：研究一：不同方法在简化多级计分认知诊断模型（seq-DINA 和 seq-RRUM）的效果及其比较研究；研究二：不同方法在饱和多级计分认知诊断模型（seq-GDINA）的效果及其比较研究。

# 4 研究一：不同方法在 seq-DINA 和 seq-RRUM模型中的比较研究

# 4.1研究一实验设计

# 4.1.1Q矩阵

本研究采用的Q矩阵（Ma&delaTorre，2016）如下，共包含了21个题目，5个属性，Q矩阵见表1。

表1测验Q矩阵  

<html><body><table><tr><td>题目</td><td>类别</td><td>A1</td><td>A2</td><td>A3</td><td>A4</td><td>A5</td><td>题目</td><td>类别</td><td>A1</td><td>A2</td><td>A3</td><td>A4</td><td>A5</td></tr><tr><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>11</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>1</td><td>2</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>11</td><td>2</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>2</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>12</td><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td></tr><tr><td>2</td><td>2</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>12</td><td>2</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td></tr><tr><td>3</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>13</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>3</td><td>2</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>13</td><td>2</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td></tr><tr><td>4</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>14</td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>4</td><td>2</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>14</td><td>2</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>5</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>14</td><td>3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr></table></body></html>

<html><body><table><tr><td>5</td><td>2</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>15</td><td>1</td><td></td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>6</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>15</td><td>2</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td></tr><tr><td>6</td><td>2</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>15</td><td>3</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>7</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>16</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>7</td><td>2</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>16</td><td>2</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>8</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>16</td><td>3</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td></tr><tr><td>8</td><td>2</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>17</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>9</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>18</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>9</td><td>2</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>19</td><td>1</td><td></td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>10</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>20</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>10</td><td>2</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>21</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr></table></body></html>

# 4.1.2认知诊断模型、被试参数和题目参数模拟

研究一使用的模型为 seq-DINA 和 seq-RRUM模型。被试掌握模式由多元正态分布(multiimensioaloaldistrbtion） $M V N ( \mathbf { 0 } , { \boldsymbol { \Sigma } } )$ 产生,参考已有研究（chen,2017;Liu, Xin,Andersson,& Tian,2019）属性间相关设置为0.5。样本量分别为 500、1000 和 2000人，代表小样本、中等样本和大样本。题目参数模拟方法为掌握项目 $j$ 第 $h$ 类别全部属性的被试得（204号 $h$ 分的概率从[.75\~1]中随机产生,即 $S _ { \ j } \big ( h \big | \alpha _ { l j h } ^ { * } = 1 \big ) = U [ 0 . 7 5 , 1 ]$ ，未掌握项目 $j$ 第 $h$ 类别任何属性的被试得 $h$ 分的概率从 $[ 0 \sim . 2 5 ]$ 中随机产生，即 $S _ { \mathrm { \Lambda } _ { j } } \big ( h \big | \alpha _ { l j h } ^ { \ast } = 0 \big ) = U [ 0 , 0 . 2 5 ]$ 。对于 seq-RRUM模型，其他掌握模式的被试得 $h$ 分的概率从 $\left[ S _ { j } \big ( h | \alpha _ { l j h } ^ { * } = 0 \big ) , \ S _ { j } \big ( h | \alpha _ { l j h } ^ { * } = 1 \big ) \right] \mathsf { I }$ 中随机产生且服从单调性约束，即掌握属性个数多的被试在题目 $j$ 上得 $h$ 分的概率大于掌握属性个数少的被试，即当 $\alpha _ { l } \geq \alpha _ { l } ^ { \prime }$ ， $S _ { \ j } \big ( h | \alpha _ { l } \big ) \geq S _ { \ j } \big ( h | \alpha _ { l } ^ { \prime } \big ) _ { \circ }$

# 4.1.3Q矩阵错误模拟

参考已有研究（Chen et al.,2013；Liu, Tian,& Xin,2016；Chen，2017；Liu et al.,2019),分别考察Q矩阵中有属性冗余、属性缺失、属性既缺失又冗余等情况，分别设置了以下6种Q矩阵错误类型。Q1为随机挑选5个测量了一个属性的类别，随机将每个类别中一个为“0"的属性改为"1”。Q2为随机挑选5个测量了2个属性以上的类别，随机将每个类别中一个为"1"的属性改为"0”。Q3为随机挑选5个测量了2个属性以上的类别，随机将每个类别中一个为"0"的属性改为"1”，将其中一个为"1"的属性改为"0”。Q4 则包含了前三个Q 向量的所有错误。Q5 和Q6 则分别模拟了 $10 \%$ 和 $20 \%$ 的随机错误，但保证每个类别测量了最多3 个属性最少1个属性。

# 表2Q矩阵错误类型

<html><body><table><tr><td>Q</td><td>Q矩阵错误模拟规则</td><td>调整的类别</td><td>调整的属性个数</td><td>备注</td></tr><tr><td>Q1</td><td>qjk =0→qjk =1</td><td>K 的类别</td><td>5</td><td>属性冗余</td></tr><tr><td>Q2</td><td>qjk =1→qjk =0</td><td>K>2 的类别</td><td>5</td><td>属性缺失</td></tr><tr><td>Q3</td><td>qjk =0→qjk=1,qjk=1→qjk =0</td><td>K>2 的类别</td><td>10</td><td>属性既冗余又缺 失</td></tr><tr><td>Q4 qjk =0→qjk=1,qjk=1→qjk =0</td><td>qjk =0→qjk =1 qjk =1→qjk =0</td><td>分别为Q1、 Q2和Q3的类 别</td><td>20</td><td>Q1、Q2和Q3的 组合</td></tr><tr><td colspan="5">Q5 10%随机调整 随机 20</td></tr><tr><td>Q6 20%随机调整</td><td></td><td></td><td></td><td>1<Kh<3 调整后</td></tr></table></body></html>

# 4.1.4被试作答模拟

根据模拟的被试参数和题目参数分别计算被试 $i$ 在题目 $j$ 上所有类别的得分概率$P _ { i j } = \big [ P ( X _ { j } = 0 \big | \alpha _ { i j } ^ { * } ) , \cdots , P ( X _ { j } = H _ { j } \big | \alpha _ { i j } ^ { * } ) \big ]$ ，以 $P _ { i j }$ 为概率在类别分布（Categorical distribution）中产生被试 $i$ 在题目 $j$ 上的作答反应得分，即 $X _ { _ { i j } } = C a t ( P _ { _ { i j } } )$ 。

# 4.1.5评价指标

计算每次修正后的Q矩阵与真实Q矩阵每个类别属性模式的一致性作为模式判准率（patterm match ratio，PMR）。计算每次修正后的Q矩阵与真实Q矩阵属性的一致性作为属性判准率（attribute match ratio,AMR）。以及FPR（False Positive Rate）和 TPR（True PositiveRate）分别代表错误标定的属性未被修改的比例和正确标定的属性未被修改的比例。所有实验均重复200次，然后再计算200 次实验的平均PMR、AMR、FPR以及TPR

$$
P M R = \frac { \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { h = 1 } ^ { H _ { j } } n _ { j h _ { - } c o r r e c t } } { \displaystyle \sum _ { j = 1 } ^ { J } H _ { j } }
$$

$$
\mathit { A M R } = \frac { \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { h = 1 } ^ { H _ { j } } \sum _ { k = 1 } ^ { K } n _ { j h k \_ c o r r e c t } } { \displaystyle K \times \sum _ { j = 1 } ^ { J } H _ { j } }
$$

公式9和10中， $J$ 为题目个数， $\boldsymbol { H } _ { j }$ 为第 $j$ 题的类别数量， $n _ { j h \_ c o r r e c t }$ 为修正后的第 $j$ 题第 $h$ 类别的 $q$ 向量是否与真实Q矩阵中第 $j$ 题第 $h$ 类别一致，完全一致则为1，否则为0。公式（10）中， $K$ 为属性个数，njhk_coreet表示修正后的第 $j$ 题第 $h$ 类别的第 $k$ 个属性（为0或者1）是否与真实Q矩阵中第 $j$ 题第 $h$ 类别第 $k$ 个属性一致，如果一致则为1，否则为0。

为了比较修正前后Q矩阵的优劣，分别计算Q矩阵修正前后的绝对拟合指标RMSEA（Liu etal.,2016），并计算 200 次试验的平均值。

在复杂模型（seq-RRUM和 seq-GDINA）中，三种模型相对拟合统计量在所有实验条件下均是BIC 指标的Q矩阵恢复率最高，且-2LL 和AIC 指标修正后Q矩阵的RMSEA 指标均不如BIC 方法修正后的结果。而在简化模型（seq-DINA）中，AIC、BIC 指标与-2LL 指标是等价的。同时，四种顺序算法中先增加属性后删除属性的算法（forward-then-backwardsearch algorithm）与先删除属性后增加属性的算法（backward-then-forward search algorithm）的表现几乎一致，而增加属性算法（forward search algorithm）和删除属性算法（backwardsearch algorithm）在一些实验条件下略低于前两种算法。而相对于穷尽算法，先增加属性后删除属性的算法并不会降低Q矩阵修正的正确率，穷尽算法与先增加属性后删除属性的算法之间属性判准率差异不超过 $1 \%$ 。因此为了报告的简洁性，本文只报告先增加属性后删除属性算法的BIC 方法和 stepwise 方法Q矩阵修正后的结果及RMSEA指标。

# 4.2研究一实验结果

表3 和表4分别呈现了BIC 方法和 stepwise方法在 seq-DINA 模型以及 seq-RRUM模型中的实验结果。根据表3的结果可知，在 seq-DINA模型下，使用 BIC 方法进行Q矩阵修正具有很好的效果。在所有试验条件下，BIC方法修正Q矩阵的平均模式判准率和属性判准率分别为 $8 3 . 0 \%$ 和 $9 6 . 9 \%$ ；stepwise方法的平均模式判准率和属性判准率为 $78 . 1 \%$ 和 $9 5 . 7 \%$ 。总体上，BIC 方法的模式判准率和属性判准率略高于 stepwise 方法，大多数条件下两者属性判准率差异不超过 $1 \%$ 。

在不同Q矩阵错误类型上，BIC 方法对Q1-Q5 的恢复率相当，属性判准率在 $9 5 \% - 9 8 \%$ 之间；而对于Q6的修正结果略差于前5个Q矩阵，属性判准率在 $9 3 \% - 9 5 \%$ 之间。Stepwise方法在不同错误Q矩阵上表现也相近，属性判准率均在 $92 \%$ 以上。因此在 seq-DINA 模型下,不同Q矩阵的错误类型对BIC方法和 stepwise方法的整体修正效果影响不大。

对于FPR和TPR指标，BIC方法的TPR指标在所有实验条件下均能达到 $9 5 \%$ 左右，表明 BIC 方法不会轻易更改正确标定的属性。而 BIC 方法的FPR 指标，在Q2 时低于其他Q矩阵，这也许是由于DINA 模型的特性造成的，即需要掌握题目测量的所有属性才能答对，因此 BIC 方法倾向于将缺失的属性修改过来。而 stepwise 方法的 TPR 指标与 BIC 方法相差不大，而 FPR 指标在Q2-Q4下比其他错误Q矩阵更高，说明 stepwise 方法对属性缺失不够敏感。

在样本量对Q矩阵修正效果的影响上，样本量越大，两种方法对Q矩阵的恢复率越高。当 $\scriptstyle 1 = 5 0 0$ 时，BIC 方法和 stepwise 方法的平均属性判准率 $9 5 . 6 \%$ 和 $9 4 . 6 \%$ ；当 $\scriptstyle 1 = 2 0 0 0$ 时，BIC 方法和 stepwise方法的平均属性判准率为 $9 7 . 9 \%$ 和 $9 6 . 7 \%$ 。因此增加样本量可以提高两种方法的Q矩阵的修正效果。

在修正前后Q矩阵的拟合上来看，两种方法修正后的Q矩阵的RMSEA值均低于修正前的Q矩阵，说明修正后的Q矩阵与数据更加拟合。在所有实验条件下，修正前的Q矩阵平均RMSEA值为0.048,BIC方法和 stepwise方法修正以后Q矩阵的平均RMSEA值为0.007和0.017。BIC 方法修正后的Q矩阵比 stepwise 方法修正后的Q矩阵拟合更好，平均差异为0.01。此外，样本量越大，BIC 方法修正后的Q矩阵的RMSEA值更小，如在Q1-Q5中且$N { = } 2 0 0 0$ 时，BIC方法修正后的RMSEA值在 $0 . 0 0 3 { \sim } 0 . 0 0 4$ 左右。

根据表4的结果，在 seq-RRUM模型中，总体上BIC 方法表现优于 stepwise 方法。在所有实验条件下，stepwise 方法和BIC 方法的模式判准率分为 $78 . 1 \%$ 和 $87 . 5 \%$ ，属性判准率分别为 $96 \%$ 和 $98 \%$ 。

对于样本量的影响，两种方法对Q矩阵修正的模式判准率和属性判准率随着被试人数的增加而增加。当 $\scriptstyle \mathbf { N } = 5 0 0$ 时，stepwise 方法和BIC 方法的平均属性判准率为 $9 4 . 8 \%$ 和 $9 7 . 4 \%$ 当 $N { = } 2 0 0 0$ 时，stepwise方法和BIC 方法的平均属性判准率为 $9 6 . 9 \%$ 和 $9 8 . 6 \%$ 。

在不同Q矩阵错误类型上，stepwise 方法和BIC 方法对Q矩阵的整体恢复率受Q矩阵错误类型的影响不大。如在Q1-Q5 中，stepwise 方法和 BIC 方法的属性判准率均在 $96 \%$ 和$98 \%$ 左右波动。而在Q6中，两种方法的属性判准率有所降低，但是降幅不大。

对于FPR和 TPR 指标，在所有Q矩阵错误类型下，两种方法的 TPR 指标相近，均在$9 5 \%$ 以上，而两种方法的FPR 指标在Q2-Q6中略高于Q1中，说明两种方法对属性冗余更加敏感。这同样也说明Q矩阵中包含属性缺失对两种方法的影响更大。

对于修正前后Q矩阵的绝对拟合，与 seq-DINA 模型中略有不同，即在Q1条件下，两种方法修正后的Q矩阵与修正前的Q矩阵的RMSEA指标几乎一致。这是由于Q1为属性冗余，而在复杂模型中，属性冗余并不会导致拟合变差。而在Q2-Q6中，修正前的Q矩阵的平均RMSEA分别为0.037，stepwise方法和BIC 方法修正后的Q矩阵平均RMSEA分别为0.007 和0.005，说明两种方法修正后的Q矩阵与数据更加拟合。而BIC 方法修正后的Q矩阵平均拟合要优于 stepwise 方法修正后的Q矩阵。同样，随着样本量的增加，stepwise方法和BIC方法修正后的Q矩阵具有更好的拟合值，如当 $\scriptstyle 1 = 2 0 0 0$ 时，stepwise 方法和 BIC方法修正后的Q矩阵的平均RMSEA为0.006 和0.003。

表3BIC方法和 stepwise方法在 seq-DINA模型中200 次实验的平均结果  

<html><body><table><tr><td rowspan="2">Q-matrix</td><td rowspan="2">N</td><td colspan="2">PMR</td><td colspan="2">AMR</td><td colspan="2">FPR</td><td colspan="2">TPR</td><td colspan="3">RMSEA</td></tr><tr><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Qw</td><td>Qstepwise</td><td>QBIC</td></tr><tr><td></td><td>500</td><td>0.795</td><td>0.788</td><td>0.957</td><td>0.963</td><td>0.118</td><td>0.157</td><td>0.958</td><td>0.965</td><td>0.017</td><td>0.015</td><td>0.007</td></tr><tr><td rowspan="3">Q1</td><td>1000</td><td>0.879</td><td>0.863</td><td>0.975</td><td>0.977</td><td>0.065</td><td>0.074</td><td>0.975</td><td>0.978</td><td>0.018</td><td>0.009</td><td>0.005</td></tr><tr><td>2000</td><td>0.918</td><td>0.911</td><td>0.984</td><td>0.986</td><td>0.048</td><td>0.049</td><td>0.985</td><td>0.986</td><td>0.019</td><td>0.005</td><td>0.003</td></tr><tr><td>500</td><td>0.763</td><td>0.790</td><td>0.953</td><td>0.962</td><td>0.367</td><td>0.021</td><td>0.958</td><td>0.962</td><td>0.017</td><td>0.016</td><td>0.007</td></tr><tr><td rowspan="3">Q2</td><td>1000</td><td>0.826</td><td>0.856</td><td>0.967</td><td>0.975</td><td>0.257</td><td>0.004</td><td>0.971</td><td>0.975</td><td>0.016</td><td>0.011</td><td>0.005</td></tr><tr><td>2000</td><td>0.865</td><td>0.903</td><td>0.976</td><td>0.984</td><td>0.219</td><td>0.002</td><td>0.980</td><td>0.984</td><td>0.017</td><td>0.008</td><td>0.003</td></tr><tr><td>500</td><td>0.758</td><td>0.786</td><td>0.952</td><td>0.962</td><td>0.339</td><td>0.126</td><td>0.963</td><td>0.966</td><td>0.033</td><td>0.016</td><td>0.006</td></tr><tr><td rowspan="3">Q3</td><td>1000</td><td>0.815</td><td>0.861</td><td>0.964</td><td>0.976</td><td>0.251</td><td>0.089</td><td>0.972</td><td>0.979</td><td>0.034</td><td>0.010</td><td>0.005</td></tr><tr><td>2000</td><td>0.856</td><td>0.910</td><td>0.974</td><td>0.985</td><td>0.180</td><td>0.065</td><td>0.980</td><td>0.987</td><td>0.035</td><td>0.009</td><td></td></tr><tr><td>500</td><td>0.680</td><td>0.776</td><td>0.938</td><td>0.961</td><td>0.363</td><td>0.110</td><td>0.962</td><td></td><td></td><td></td><td>0.004</td></tr><tr><td>Q4</td><td>1000</td><td>0.721</td><td>0.853</td><td>0.950</td><td>0.975</td><td>0.288</td><td>0.064</td><td>0.968</td><td>0.966 0.978</td><td>0.041 0.041</td><td>0.020 0.015</td><td>0.007 0.005</td></tr><tr><td></td><td>2000</td><td>0.745</td><td>0.905</td><td>0.956</td><td>0.984</td><td>0.251</td><td>0.040</td><td>0.972</td><td>0.986</td><td>0.042</td><td>0.013</td><td>0.003</td></tr><tr><td rowspan="3">Q5</td><td>500</td><td>0.760</td><td>0.777</td><td>0.951</td><td>0.959</td><td>0.112</td><td>0.068</td><td>0.956</td><td>0.961</td><td>0.075</td><td>0.020</td><td></td></tr><tr><td>1000</td><td>0.835</td><td>0.851</td><td>0.968</td><td>0.975</td><td>0.082</td><td>0.041</td><td>0.972</td><td>0.976</td><td>0.073</td><td>0.011</td><td>0.008</td></tr><tr><td>2000</td><td>0.874</td><td>0.903</td><td>0.975</td><td>0.984</td><td>0.065</td><td>0.022</td><td>0.978</td><td>0.984</td><td></td><td></td><td>0.004</td></tr><tr><td rowspan="3">Q6</td><td>500</td><td>0.629</td><td>0.687</td><td>0.924</td><td>0.933</td><td>0.184</td><td>0.105</td><td>0.943</td><td>0.940</td><td>0.076 0.100</td><td>0.013 0.035</td><td>0.004</td></tr><tr><td>1000</td><td>0.656</td><td>0.744</td><td>0.931</td><td>0.942</td><td>0.173</td><td>0.097</td><td>0.949</td><td>0.949</td><td>0.102</td><td>0.038</td><td>0.015 0.017</td></tr><tr><td>2000</td><td>0.687</td><td>0.793</td><td>0.935</td><td>0.953</td><td>0.163</td><td>0.081</td><td>0.951</td><td>0.959</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.102</td><td>0.037</td><td>0.010</td></tr></table></body></html>

注： $\mathrm { Q } _ { \mathrm { w } }$ （Q_wrong）为修正前的Q矩阵，下同。

表4BIC 方法和 stepwise方法在 seq-RRUM模型中 200 次实验的平均结果  

<html><body><table><tr><td rowspan="2">Q-matrix</td><td rowspan="2">N</td><td colspan="2">PMR</td><td colspan="2">AMR</td><td colspan="2">FPR</td><td colspan="2">TPR</td><td colspan="3">RMSEA</td></tr><tr><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Qw</td><td>Qstepwise</td><td>QBIC</td></tr><tr><td>Q1</td><td>500</td><td>0.750</td><td>0.841</td><td>0.952</td><td>0.975</td><td>0.083</td><td>0.022</td><td>0.952</td><td>0.975</td><td>0.006</td><td>0.007</td><td>0.006</td></tr><tr><td rowspan="4"></td><td>1000</td><td>0.823</td><td>0.884</td><td>0.968</td><td>0.982</td><td>0.037</td><td>0.041</td><td>0.968</td><td>0.983</td><td>0.005</td><td>0.005</td><td>0.005</td></tr><tr><td>2000</td><td>0.864</td><td>0.915</td><td>0.976</td><td>0.987</td><td>0.029</td><td>0.020</td><td>0.977</td><td>0.987</td><td>0.004</td><td>0.005</td><td>0.004</td></tr><tr><td>500</td><td>0.746</td><td>0.839</td><td>0.953</td><td>0.975</td><td>0.332</td><td>0.199</td><td>0.958</td><td>0.978</td><td>0.027</td><td>0.008</td><td>0.007</td></tr><tr><td>1000</td><td>0.819</td><td>0.890</td><td>0.968</td><td>0.983</td><td>0.264</td><td>0.153</td><td>0.972</td><td>0.986</td><td>0.026</td><td>0.006</td><td>0.005</td></tr><tr><td></td><td>2000</td><td>0.843</td><td>0.919</td><td>0.974</td><td>0.988</td><td>0.252</td><td>0.117</td><td>0.978</td><td>0.990</td><td>0.026</td><td>0.005</td><td>0.003</td></tr><tr><td rowspan="3">Q3</td><td>500</td><td>0.734</td><td>0.847</td><td>0.949</td><td>0.976</td><td>0.300</td><td>0.121</td><td>0.959</td><td>0.980</td><td>0.022</td><td>0.008</td><td>0.006</td></tr><tr><td>1000</td><td>0.794</td><td>0.877</td><td>0.963</td><td>0.981</td><td>0.241</td><td>0.086</td><td>0.971</td><td>0.983</td><td>0.023</td><td>0.006</td><td>0.005</td></tr><tr><td>2000</td><td>0.843</td><td>0.914</td><td>0.973</td><td>0.987</td><td>0.171</td><td>0.057</td><td>0.979</td><td>0.989</td><td>0.023</td><td>0.005</td><td>0.003</td></tr><tr><td rowspan="3">Q4</td><td>500</td><td>0.714</td><td>0.832</td><td>0.946</td><td>0.974</td><td>0.275</td><td>0.123</td><td>0.963</td><td>0.981</td><td>0.030</td><td>0.008</td><td>0.007</td></tr><tr><td>1000</td><td>0.770</td><td>0.881</td><td>0.959</td><td>0.982</td><td>0.215</td><td>0.085</td><td>0.973</td><td>0.987</td><td>0.031</td><td>0.006</td><td>0.005</td></tr><tr><td>2000</td><td>0.796</td><td>0.917</td><td>0.966</td><td>0.987</td><td>0.195</td><td>0.058</td><td>0.978</td><td>0.991</td><td>0.032</td><td>0.005</td><td>0.003</td></tr><tr><td rowspan="3">Q5</td><td>500</td><td>0.751</td><td>0.841</td><td>0.952</td><td>0.975</td><td>0.098</td><td>0.047</td><td>0.956</td><td>0.976</td><td>0.039</td><td>0.008</td><td>0.006</td></tr><tr><td>1000</td><td>0.807</td><td>0.880</td><td>0.965</td><td>0.982</td><td>0.073</td><td>0.038</td><td>0.968</td><td>0.983</td><td>0.035</td><td>0.005</td><td>0.005</td></tr><tr><td>2000</td><td>0.849</td><td>0.914</td><td>0.974</td><td>0.987</td><td>0.053</td><td>0.021</td><td>0.976</td><td>0.987</td><td>0.039</td><td>0.005</td><td>0.004</td></tr><tr><td rowspan="3">Q6</td><td>500</td><td>0.686</td><td>0.817</td><td>0.941</td><td>0.968</td><td>0.134</td><td>0.063</td><td>0.953</td><td>0.973</td><td>0.063</td><td>0.014</td><td>0.008</td></tr><tr><td>1000</td><td>0.726</td><td>0.848</td><td>0.948</td><td>0.973</td><td>0.127</td><td>0.058</td><td>0.960</td><td>0.978</td><td>0.070</td><td>0.012</td><td>0.007</td></tr><tr><td>2000</td><td>0.748</td><td>0.896</td><td>0.953</td><td>0.982</td><td>0.120</td><td>0.032</td><td>0.966</td><td>0.984</td><td>0.063</td><td>0.009</td><td>0.004</td></tr></table></body></html>

# 5研究二：不同方法在 seq-GDINA模型中的比较研究

研究一中多级计分的认知诊断模型在每个类别上的链接函数具有一定的约束，可以由seq-GDINA 模型转换而来。而 seq-GDINA 是饱和的模型，因此具有更广的适用性。研究二则是对不同方法在 seq-GDINA 模型中的效果进行验证及比较。

# 5.1研究二实验设计

研究二的实验设计与研究一的实验设计相似，不同的是研究二使用的是 seq-GDINA 模型。其余实验条件请见研究一。

# 5.2研究二实验结果

表5 呈现了BIC 方法和 stepwise 方法在 seq-GDINA 模型中的实验结果。从表5可以看出，与研究一的结果相似，总体上BIC 方法略优于 stepwise 方法，BIC 方法和 stepwise 方法的平均模式判准率分别为 $9 0 . 5 \%$ 和 $84 . 5 \%$ ，属性判准率分别为 $9 8 . 6 \%$ 和 $9 7 . 1 \%$ 。两种方法的Q矩阵恢复率随着被试人数的增加而逐渐增加，如当 $\scriptstyle \mathbf { N } = 5 0 0$ 时，BIC 方法的平均模式判准率和平均属性判准率分别为 $86 \%$ 和 $9 7 . 9 \%$ ，stepwise 方法的平均模式判准率和属性判准率分别为 $78 \%$ 和 $9 5 . 9 \%$ ；当 $N { = } 2 0 0 0$ 时，BIC方法的平均模式判准率和平均属性判准率分别为$9 4 . 8 \%$ 和 $9 9 . 3 \%$ ，stepwise方法的平均模式判准率和属性判准率分别为 $9 0 . 8 \%$ 和 $9 8 . 5 \%$ 。不同Q矩阵错误类型下两种方法对Q矩阵的整体恢复率差异不大。在修正前后Q矩阵的绝对拟合上，在Q1条件下，两种方法修正后Q矩阵的RMSEA指标几乎与修正前Q矩阵一致。这与 seq-RRUM模型中结果一样，这是由于Q1矩阵中属性冗余导致的。而在Q2-Q6 中，修正前Q矩阵的平均RMSEA为0.036，stepwise方法和BIC 方法修正后Q矩阵的平均RMSEA分别为0.007和0.006，说明修正后的Q矩阵与数据更加拟合。随着样本量的增加，两种方法修正后的Q矩阵具有更好的拟合值。

表5BIC方法和 stepwise方法在 seq-GDINA 模型中200 次实验的平均结果  

<html><body><table><tr><td rowspan="2">Q-matrix</td><td rowspan="2">N</td><td colspan="2">PMR</td><td colspan="2">AMR</td><td colspan="2">FPR</td><td colspan="2">TPR</td><td colspan="3">RMSEA</td></tr><tr><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Stepwise</td><td>BIC</td><td>Qw</td><td>Qstepwise</td><td>QBIC</td></tr><tr><td rowspan="3">Q1</td><td>500</td><td>0.795</td><td>0.861</td><td>0.961</td><td>0.979</td><td>0.075</td><td>0.006</td><td>0.962</td><td>0.979</td><td>0.007</td><td>0.007</td><td>0.007</td></tr><tr><td>1000</td><td>0.875</td><td>0.913</td><td>0.978</td><td>0.987</td><td>0.032</td><td>0.004</td><td>0.978</td><td>0.987</td><td>0.005</td><td>0.006</td><td>0.005</td></tr><tr><td>2000</td><td>0.919</td><td>0.950</td><td>0.986</td><td>0.993</td><td>0.020</td><td>0.001</td><td>0.986</td><td>0.993</td><td>0.004</td><td>0.005</td><td>0.004</td></tr><tr><td rowspan="3">Q2</td><td>500</td><td>0.799</td><td>0.864</td><td>0.964</td><td>0.980</td><td>0.209</td><td>0.211</td><td>0.967</td><td>0.983</td><td>0.029</td><td>0.008</td><td>0.009</td></tr><tr><td>1000</td><td>0.877</td><td>0.916</td><td>0.979</td><td>0.988</td><td>0.108</td><td>0.110</td><td>0.980</td><td>0.990</td><td>0.030</td><td>0.006</td><td>0.006</td></tr><tr><td>2000</td><td>0.915</td><td>0.948</td><td>0.986</td><td>0.993</td><td>0.093</td><td>0.067</td><td>0.987</td><td>0.994</td><td>0.030</td><td>0.004</td><td>0.004</td></tr><tr><td rowspan="3">Q3</td><td>500</td><td>0.794</td><td>0.867</td><td>0.961</td><td>0.980</td><td>0.236</td><td>0.125</td><td>0.969</td><td>0.984</td><td>0.022</td><td>0.007</td><td>0.008</td></tr><tr><td>1000</td><td>0.854</td><td>0.910</td><td>0.974</td><td>0.987</td><td>0.170</td><td>0.069</td><td>0.979</td><td>0.989</td><td>0.025</td><td>0.006</td><td>0.006</td></tr><tr><td>2000</td><td>0.904</td><td>0.949</td><td>0.984</td><td>0.993</td><td>0.106</td><td>0.038</td><td>0.988</td><td>0.994</td><td>0.025</td><td>0.005</td><td>0.003</td></tr><tr><td rowspan="3">Q4</td><td>500</td><td>0.775</td><td>0.863</td><td>0.958</td><td>0.979</td><td>0.193</td><td>0.106</td><td>0.970</td><td>0.985</td><td>0.033</td><td>0.009</td><td>0.008</td></tr><tr><td>1000</td><td>0.840</td><td>0.912</td><td>0.972</td><td>0.987</td><td>0.136</td><td>0.062</td><td>0.981</td><td>0.991</td><td>0.033</td><td>0.007</td><td>0.006</td></tr><tr><td>2000</td><td>0.884</td><td>0.945</td><td>0.981</td><td>0.992</td><td>0.112</td><td>0.040</td><td>0.989</td><td>0.994</td><td>0.034</td><td>0.005</td><td>0.004</td></tr><tr><td rowspan="3">Q5</td><td>500</td><td>0.786</td><td>0.866</td><td>0.959</td><td>0.980</td><td>0.086</td><td>0.040</td><td>0.962</td><td>0.981</td><td>0.034</td><td>0.009</td><td>0.009</td></tr><tr><td>1000</td><td>0.859</td><td>0.911</td><td>0.975</td><td>0.987</td><td>0.053</td><td>0.023</td><td>0.977</td><td>0.988</td><td>0.036</td><td>0.006</td><td>0.006</td></tr><tr><td>2000</td><td>0.912</td><td>0.949</td><td>0.985</td><td>0.993</td><td>0.031</td><td>0.011</td><td>0.987</td><td>0.993</td><td>0.041</td><td>0.005</td><td>0.004</td></tr><tr><td rowspan="3">Q6</td><td>500</td><td>0.731</td><td>0.838</td><td>0.948</td><td>0.973</td><td>0.122</td><td>0.059</td><td>0.960</td><td>0.978</td><td>0.061</td><td>0.015</td><td>0.009</td></tr><tr><td>1000</td><td>0.784</td><td>0.885</td><td>0.959</td><td>0.980</td><td>0.104</td><td>0.039</td><td>0.970</td><td>0.983</td><td>0.066</td><td>0.010</td><td>0.007</td></tr><tr><td>2000</td><td>0.913</td><td>0.948</td><td>0.985</td><td>0.992</td><td>0.037</td><td>0.015</td><td>0.987</td><td>0.993</td><td>0.041</td><td>0.004</td><td>0.004</td></tr></table></body></html>

# 6研究三：实证数据分析

本研究采用两个 TIMSS（Trends in International Mathematics and Science Study）数据,分别为2011年8年级和 2007年4年级数学测试的数据。TIMSS 2011年的数据由Park,Lee 和Johnson（2017）标定了Q矩阵，Ma和dela Torre(2019)将该数据用于多级计分Q矩阵修正的分析。该数据共包括23个题目、7个属性，共748名学生的作答。其中第11题为多级计分的题目，其余题目为0-1计分的题目，Q矩阵见表6。

表6TIMSS2011（8年级）数据Q矩阵及修正结果  

<html><body><table><tr><td>Item</td><td>Code</td><td>类别</td><td>A1</td><td>A2</td><td>A3</td><td>A4</td><td>A5</td><td>A6</td><td>A7</td></tr><tr><td>1</td><td>M042041</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>2</td><td>M042024</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>3</td><td>M042016</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1*#</td></tr><tr><td>4</td><td>M042002</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>5</td><td>M042198A</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0*#</td></tr><tr><td>6</td><td>M042198B</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>7</td><td>M042198C</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0*</td><td>0</td><td>0</td></tr><tr><td>8</td><td>M042077</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>9</td><td>M042235</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0*</td><td>0</td><td>0</td></tr><tr><td>10</td><td>M042150</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>11</td><td>M042300Z</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td></tr><tr><td>11</td><td>M042300Z</td><td>2</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>12</td><td>M042169A</td><td>1</td><td>0*</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>13</td><td>M042169B</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>14</td><td>M042169C</td><td>1</td><td>0*</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>15</td><td>M032352</td><td>1</td><td>1</td><td>0</td><td>1*#</td><td>0</td><td>0</td><td>0</td><td>1*</td></tr><tr><td>16</td><td>M032725</td><td>1</td><td>0</td><td>1*</td><td>0</td><td>0</td><td>0</td><td>0*#</td><td>0</td></tr><tr><td>17</td><td>M032738</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>18</td><td>M032295</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>19</td><td>M032331</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td></tr><tr><td>20</td><td>M032679</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1*</td><td>0</td></tr><tr><td>21</td><td>M032047</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1*#</td><td>0</td><td>0</td><td>0</td></tr><tr><td>22</td><td>M032398</td><td>1</td><td>0*</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>23</td><td>M032424</td><td>1</td><td>0</td><td>0*#</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

注：A1,整数和自然数；A2，分数、小数和比例；A3，模式；A4，表达式、方程式和函数；A5，线条、角度和形状；A6，位置和运动；A7，数据的组织、表达和解读。“\*"为BIC 方法调整的属性；“#"为 stepwise 方法调整的属性。

分析之前先比较该数据与各模型之间的拟合指标（偏差、AIC、BIC），结果显示各个指标对应的最优模型不同，因此为了避免模型选择错误，这里使用 seq-GDINA 模型来拟合数据，而对于0-1计分的题目则等价于用GDINA模型来拟合数据。两种方法对原始Q矩阵的调整结果见表6，其中带"\*"的属性为BIC 方法建议调整的属性，带"#"的属性为 stepwise方法建议调整的属性。BIC 方法共调整了12个题目14个属性，stepwise 方法调整了共6个题目6个属性，并且 stepwise 方法调整的6个属性全部包含于BIC 方法调整的属性中。而对于第11题，两种方法均未对该题的两个类别 $q$ 向量进行调整。

表7呈现了不同Q矩阵之间的一致率，BIC 方法和 stepwise方法修正后的Q矩阵与原始Q矩阵之间的一致率分别为0.92 和0.96，而 BIC 方法和 stepwise 方法修正后的Q矩阵之间的一致率为0.95，Q矩阵之间具有较高的一致率。

表7TIMSS2011（8年级）数据不同方法Q矩阵修正一致率  

<html><body><table><tr><td></td><td>Qoriginal</td><td>QBIC</td><td>Qstepwise</td></tr><tr><td>Qoriginal</td><td>1</td><td></td><td></td></tr><tr><td>QBIC</td><td>0.92</td><td>1</td><td></td></tr><tr><td>Qstepwise</td><td>0.96</td><td>0.95</td><td>1</td></tr></table></body></html>

为了比较两种方法修正后的Q矩阵与原有的Q矩阵，分别计算修正前后Q矩阵的相对拟合指标 $( - 2 ^ { * } \mathrm { L L }$ 、AIC、BIC）和绝对拟合指标（ $\mathbf { \dot { M } } _ { 2 }$ 检验(Liu et al., 2016)、RMSEA(Liu et al.,2016)和 SRMSR），结果如表8。从表8可以看出，两种方法修正后的Q矩阵在相对拟合指标上均优于原有Q矩阵。在绝对拟合上，修正前的Q矩阵 $\mathbf { M } _ { 2 }$ 检验为 $\mathsf { p } { < } 0 . 0 1$ ，而修正后的Q矩阵检验结果为 $\scriptstyle \mathtt { p } = 0 . 2$ 和0.3，因此修正后的Q矩阵与数据更加拟合。在RMSEA和SRMSR指标上，两种方法修正后的Q矩阵也优于原有Q矩阵。而两种方法修正后Q矩阵的拟合指标相近，Qstepwise 的 $\mathbf { M } _ { 2 }$ 检验和RMSEA 优于与QBIC，而QBIc 的相对拟合指标和 SRMSR 优于Qstepwise o

表8TIMSS2011（8年级）数据原有Q矩阵和两种方法修正后Q矩阵的拟合指标  

<html><body><table><tr><td rowspan="3">Q</td><td colspan="3">相对拟合指标</td><td colspan="5">绝对拟合指标</td></tr><tr><td rowspan="2">-2*LL</td><td rowspan="2">AIC</td><td rowspan="2">BIC</td><td colspan="3">M2检验</td><td rowspan="2">RMSEA</td><td rowspan="2">SRMSR</td></tr><tr><td>M2</td><td>df</td><td>P</td></tr><tr><td>Qoriginal</td><td>18888.23</td><td>19274.23</td><td>20165.39</td><td>123.51</td><td>83</td><td>0.003</td><td>0.026</td><td>0.059</td></tr><tr><td>QBIC</td><td>18624.73</td><td>19014.73</td><td>19915.13</td><td>89.02</td><td>81</td><td>0.254</td><td>0.012</td><td>0.044</td></tr><tr><td>Qstepwise</td><td>18757.88</td><td>19139.88</td><td>20021.88</td><td>89.90</td><td>85</td><td>0.337</td><td>0.009</td><td>0.050</td></tr></table></body></html>

此外，我们又对 TIMSS 2007年的数据进行了分析。该数据由Lee,Park 和 Taylan（2011)标定了Q矩阵，Ma 和de la Torre(2016)将该数据用于多级计分模型的分析。该数据共包括11个题目、8个属性，共823名学生的作答，其中第3、7、9题为多级计分的题目，其余题目为0-1计分的题目。该数据原始Q矩阵如表9所示。

表9TIMSS2007（4年级）数据Q矩阵及修正结果  

<html><body><table><tr><td>Item</td><td>Code</td><td>类别</td><td>A1</td><td>A2</td><td>A3</td><td>A4</td><td>A5</td><td>A6</td><td>A7</td><td>A8</td></tr><tr><td>1</td><td>M041052</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>2</td><td>M041281</td><td>1</td><td>0</td><td>1</td><td>1*</td><td>0</td><td>1*</td><td>0</td><td>0</td><td>0</td></tr><tr><td>3</td><td>M041275</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1*</td></tr><tr><td>3</td><td>M041275</td><td>2</td><td>1*</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1*</td></tr><tr><td>4</td><td>M031303</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>5</td><td>M031309</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>6</td><td>M031245</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>7</td><td>M031242A</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>7</td><td>M031242B</td><td>2</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>8</td><td>M031242C</td><td>1</td><td>0</td><td>1*</td><td>1*</td><td>0</td><td>1</td><td>0</td><td>1*</td><td>0</td></tr><tr><td>9</td><td>M031247</td><td>1</td><td>0</td><td>1*</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>9</td><td>M031247</td><td>2</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>10</td><td>M031173</td><td>1</td><td>0*</td><td>1*</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>11</td><td>M031172</td><td>1</td><td>1*</td><td>1*</td><td>0</td><td>0</td><td>0</td><td>1*</td><td>0</td><td>1</td></tr></table></body></html>

注：A1，表示、比较和排序整数以及说明排序位置的价值；A2，识别倍数，使用四步操作计算整数并估算；A3，解决问题，包括现实情境中的问题（如测量和资金问题）；A4，查找缺失数据，或对包含未知的句子和表达进行操作和建模；A5，描述模式及其扩展的关系，通过给定规则生成整数对，并为给定整数对的每个关系确定规则；A6，从表格，象形图，条形图和饼图中读取数据；A7，比较和理解如何使用数据中的信息；A8，了解不同的表达，用表格、象形图和条形图组织数据。“\*"为BIC 方法调整的属性。

分析结果为 stepwise 方法和 BIC 方法分别调整了17个属性和14 个属性，而 stepwise方法调整后属性5（A5）没有被任何题目测量，因此这里不详细展示该方法的具体结果，BIC 调整后的Q矩阵如表9。同样计算BIC方法修正后的Q矩阵与原始Q矩阵的绝对拟合和相对拟合指标，由于该Q矩阵修正前后 $\mathbf { M } _ { 2 }$ 检验的自由度过低，因此这里不能进行 $\mathbf { M } _ { 2 }$ 检验。原有Q矩阵和BIC方法修正后的 SRMER指标分别为0.0312和0.0246。在相对拟合指标上，BIC方法修正后的Q矩阵（AIC=11222.25;BIC=12677.42）也比原有Q矩阵(AIC=11513.79; BIC $\circleddash$ 13195.01）拟合更好。因此两个实证数据分析的结果均显示BIC方法修正后的Q矩阵与数据拟合更好。

# 7结论与讨论

# 7.1结论

本研究探讨了基于类别水平的多级计分认知诊断测验Q矩阵修正，并采用Monte Carlo模拟研究和实证研究验证和比较了stepwise 方法和相对拟合指标用于Q矩阵修正的效果及特性，为实践中多级计分的测验Q矩阵修正提供了方法支持。研究发现：（1）BIC方法对多级计分认知诊断模型的Q矩阵修正具有较高的模式判准率和属性判准率，其对Q矩阵的恢复率也高于 stepwise方法，BIC 方法修正后的Q矩阵与数据更加拟合。（2）在复杂模型中，相对拟合指标 BIC 比AIC 和-2LL 表现更好，在实践中，使用者可以选择 BIC 法进行测验Q矩阵修正。（3）Q矩阵修正效果受到被试人数的影响，增加被试人数可以提高Q矩阵修正的正确率。

# 7.2讨论

（1）多级计分认知诊断Q矩阵修正方法

多级计分的题目是实际测验中常见的题型，并且多级计分题目比0-1计分题目能提供更多的信息，因此多级计分认知诊断模型的开发对认知诊断的发展具有重要作用。本研究将相对拟合统计量用于多级计分认知诊断模型Q矩阵修正中，并改进Q矩阵修正算法，研究发现BIC 方法在多级计分模型中的Q矩阵修正具有很好的效果。并且该方法受到被试人数的影响较少，在不同Q矩阵错误类型下均有较好的修正效果。为了提高运算效率，本文中使用了顺序算法，模拟研究发现本文中使用的顺序算法与穷尽算法之间的属性判准率差异不超过 $1 \%$ 。而本文中的顺序算法为先增加属性后删除属性的算法，其表现与先删除属性再增加属性的算法一致。增加属性算法和删除属性的算法略差，这可能是由于后两种算法没有利用到专家给定的 $q$ 向量信息。此外在模型不确定的情况下，可以使用饱和模型（seq-GDINA)来进行Q矩阵修正，模拟研究显示使用饱和模型进行Q矩阵修正并不会降低Q矩阵修正的效果。

（2）多级计分认知诊断下类别水平与项目水平Q矩阵修正

类别水平的Q矩阵需要在每个类别上分别标定Q矩阵，因此能更准确地探查出被试的解题过程，且分类准确性也更高。但是为每个类别标定Q矩阵不仅有难度且会增加Q矩阵标定的工作量。而项目水平的Q矩阵的标定相对简单，但产生的结果是忽略了每个步骤的信息，从而分类准确性有所降低(Ma＆dela Torre，2016)。在Q矩阵修正上，对类别水平Q矩阵的修正也更难。本研究在多级计分模型下对类别水平的Q矩阵修正进行研究，并且发现 BIC方法具有较好的效果，为多级计分模型下类别水平Q矩阵的标定与修正提供了方法支持。

（3）Q矩阵修正结果应与专家意见相结合

从作答数据出发提出Q矩阵修正方法可以避免专家标定Q矩阵的主观性，也可以减轻专家的负担。但是客观方法标定的Q矩阵不能直接作为最终的Q矩阵，应该与专家的意见相结合。从作答数据出发进行的Q矩阵标定可以作为专家标定Q矩阵的参考和依据，但是不能忽视专家在测验设计和Q矩阵标定中的重要作用。而本文中BIC 方法修正后的Q矩阵与数据更加拟合也并不代表修改的属性恰当，需要由专家最后决定是否对Q矩阵进行修改。

当客观方法得出的Q矩阵与专家意见不同时，可以由多个专家讨论决定，或者将有争议的题目删除。

（4）未来研究方向

本研究尝试提出在多级计分模型下的Q矩阵修正方法，并发现BIC方法可用于多级计分认知诊断模型的Q矩阵修正。但是本研究还存在一些需要进一步探究的地方，如不同题目参数质量对Q矩阵修正的影响、项目水平Q矩阵下不同方法的表现如何、属性间有层级关系时Q矩阵的修正效果等。此外对于多级计分模型下Q矩阵的标定还有更多的问题需要进行研究，如Q矩阵完备性和可识别性的推导证明、当属性个数有误时如何自动识别以及更多的真实数据研究等。总之，对多级计分模型下的Q矩阵修正方法还需要进一步的研究。

# 参考文献

Akaike,H.(1974).Anewlookatthetatisticalidentificationmodel.IEEEransactionsonAutomatedControl,19,16-723.   
Chang,H.-H.(20l5).Psychometrics behind computerized adaptive testing.Psychometrika,80,1-20.   
Chang,H.-H.,&Wang,W.Y.(o16).“Internetplus”measurementandevaluation:anewwayforadaptivelearing.JournalofJiangxi Normal University(Natural Science),40(5),441-455.   
[张华华，汪文义.(2016).“互联网 $+ ^ { , }$ 测评:自适应学习之路．江西师范大学学报(自然科学版),40(5),441-455.]   
Chen,J.S.().sidalsedroachtateatrixsicatiosApledholgicalesurement,4.   
Chen,J.Tore,J&Zang,Z(l3).RelativeandbsoutefitevauationincgnitivediagnosismodelingJoualfductional Measurement,50,123-140.   
Chiu,C.-Y.(l3).tatisticalemntofteatrioiieagoisApledologiclesuement,968.   
delaToe,J.(o8).AnmpiicallyasedmetodofQ-matrixationfotheAmodel:developmentandaplicatios.Joualof Educational Measurement,45,343-362.   
de la Torre,J.(2011).The generalized DINA model framework.Psychometrika,76,179-199.   
de laTorre,J.,&Chiu,C.-Y.(O16).Ageneral methodof empirical Q-matrix validation.Psychometrika,81,253-273.   
Haertel,E.H.(984).lcaioflentlasodels tssssmntata.Apedsholoicalesurement346.   
Hansen,M.(3).eracclitspoeodelsforgnitivedagosispubsdoctraldertatioUivesityCalifoa at Los Angeles.   
HartzS.M.,oussos,L.A.(O8).efusionodelforsilagnosis:blendingthorywitpracticeEducationalTstingice Research Report,RR-O8-71.Princeton,NJ:Educational Testing Service.

Lee,Y.-S.,Park,n.().oiegosicoelioftrbutesteiassacsesotade U.S.national sample using the TIMSS 2007.International Journal of Testing,I1,144-177.

Liu,Y.,Tian,W.,&Xin,T.(l6).AnpicationofM2tatistictovaluatethefitofcognitivediagnosticmodels.Joualof Educational and Behavioral Statistics,41(1),3-26.

Liu,Y.,Xin,derss.nW9).oaiatriitiorodesfiegostcde JournalofMathematicalandStatisticalPsychology,72,18-37   
Ma,W.&delaTorr,J.(6).squentialgnitivdagosisodelfoolmoussposs.ritishualofatematld StatisticalPsychology,69,253-275.   
Ma,W.&Tore,J.(2019).Anempirical Q-matrixvalidationmethodforthesequentialgeneralizedDNAmodel.BritishJournalof Mathematical and Statistical Psychology.https://doi.org/10.1111/bmsp.12156.   
Maris,E.(1999).Estimating multiple clasification latent class models.Psychometrika,64,187-212.   
Park,J.Y.,L,YS.,&Johson,M.S.O7).AnecintstandarderorestimatorofteAmodelparameterswhnaalysing clustered data.International Journal ofQuantitative Research in Education,4,159-190.   
Schwarz,G.(1978).Estimating the dimension of a model.Annals of Statistics,6,461-464.   
Templin,J.L.，&Hnson,R.A.().Measurementofpsyhologicaldisordersusingcognitivediagnosismodels.Psychological Methods,11,287-305.   
Tu,D.B.,CaiY,&Dai,H.Q. (2012).AnewmethodofQ-MatrixvidationbasedonDNAmodel.ActaPsychologicaSnica,44(4), 558-568.   
[涂冬波，蔡艳，戴海崎.(2012).基于DINA 模型的Q矩阵修正方法．心理学报,44(4),558-568.]   
Tu,D.B.,CaiY,Dai,H,ing,S.L.().Atomosognitivediagnosismodel:modelActasyhologicainic 42(10),1011-1020.   
[涂冬波,蔡艳,戴海琦,丁树良.(2010).一种多级评分的认知诊断模型:P-DINA 模型的开发.心理学报,42(10),1011-1020.]   
vonDavier,M.(o8).AgeneraldiagnosticmodelapliedtolanguagetestingdataBritishoualofathematicalandtatistical Psychology,61,287-307.   
Wang,D.X.,GaoX.L,CaiY,&Tu,D.B.(2018).AnewQ-matrixestimationmethod:ICCbasedonidealresponse.Joualof Psychological Science,41(2),466-474.   
[汪大勋,高旭亮,蔡艳,涂冬波.（2018）.一种非参数化的Q矩阵估计方法:ICC-IR方法开发．心理科学,4I(2),466-474.]   
Wang,D.X.,GaoX.L.,Han,Y.T.,&Tu,D.B.(218).AsimpleandeffectiveQ-matrixestimationmethod:fromnon-parametric

perspective.Journal ofPsychological Science,41(1),180-188.

[汪大勋，高旭亮，韩雨婷，涂冬波.(2018).一种简单有效的Q矩阵估计方法开发：基于非参数化方法视角．心理科学,4l(1),180-188.]

Xu,G.&angZ.).entifgltettcturesistctedlatetsoelsJoulftmecistclo https://doi.0rg/10.1080/01621459.2017.1340889.

# A method of Q-matrix validation for polytomous response cognitive diagnosis model based on relative fit statistics

WANG Daxun1; GAO Xuliang²; CAI Yanl; TU Dongbol (l School of Psychology, Jiangxi Normal University,Nanchang, 330022) (² School of Psychology, Guizhou Normal University, Guiyang, 550000)

# Abstract

Cognitive diagnostic assessments (CDAs） can provide fine-grained diagnostic information about students' knowledge states,so as to help to teach in accordance with the students' aptitude. The development of cognitive diagnosis model for polytomous response data expands the application scope of cognitive diagnostic assessment. As the basis of CDAs, Q-matrix has aroused more and more attention for the subjective tendency in Q-matrix construction that is typically performed by domain experts. Due to the subjective process of Q-matrix construction, there inevitably have some misspecifications in the Q-matrix, if left unchecked,can result in a serious negative impact on CDAs. To avoid the subjective tendency from experts and to improve the correctness of the Q-matrix, several objective Q-matrix validation methods have been proposed. Many Q-matrix validation methods have been proposed in dichotomous CDMs, however, the research of the Q-matrix validation method under polytomous CDMs is stalling lacking. To address this concern，several relative fit statistics (i.e.，-2LL，AIC,BIC） were applied to the Q-matrix validation for polytomous cognitive diagnosis model in this research. The process of Q-matrix validation is as follows:

First,the reduced Q-matrix is represented by $Q _ { r }$ ，which represents a set of potential q-vectors and contains $2 ^ { K } - 1$ possible q-vectors when atributes are independent. When validating the q-vector of the first category of item $j$ ,all possible $\mathfrak { q }$ -vectors in $Q _ { r }$ can be used as the q-vector of the first category of item $j _ { : }$ ，and the Q-matrix of remaining items remains intact. From this,the item parameters and the atribute pattrns of students can be estimated,and the -2LL,AIC,and BIC can be calculated accordingly. The q-vector with the largest likelihood (or smallest AIC/BIC) is regarded as the q-vector of the first category of item $j$ .The q-vector of the next category of the item $j$ can also be obtained in the same way. The algorithm stops when the validated Q-matrix is same as the previous Q-matrix, or every item has been reached. In order to improve the eficiency of the method, a sequential search algorithm was proposed.

Several simulation studies were conducted to evaluate the effectiveness and practicality of these methods,and the performance of the methods in this paper was compared with the stepwise method (Ma & de la Torre, 2O19). Three experimental factors were considered in simulation studies,including sample size,Q-matrix error types and CDMs.The results show that (1） BIC method can be used for Q-matrix validation under polytomous response CDMs,and the performance of the BIC method is beter than the stepwise method.(2） In general， the performance of the three methods from good to bad is the BIC method, AIC method,and -2LL method. (3) The performance of Q-matrix validation methods is affected by the sample size,and increasing the number of sample size can improve the accuracy of the Q-matrix validation.

In this study, Q-matrix validation methods for polytomous response CDMs were studied. It was found that the BIC method can be used for the Q-matrix validation under polytomous response CDMs. The method proposed in this paper can not only improve the accuracy of Q-matrix specification but also increase the model-data fit level. Besides,the data-based Q-matrix validation method can also reduce the workload of experts in Q-matrix construction and improve the classification accuracy of cognitive diagnosis.

Key words cognitive diagnostic assessment; Q-matrix; seq-GDINA; BIC