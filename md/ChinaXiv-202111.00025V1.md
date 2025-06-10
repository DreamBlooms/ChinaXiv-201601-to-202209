# 认知诊断缺失数据处理方法的比较：零替换、多重插补与极大似然估计法\*

1 1,2 3 宋枝璘 郭磊 郑天鹏

(西南大学心理学部，重庆 400715）（ 中国基础教育质量监测协同创新中心西南大学分中心，重庆 400715)( 北京师范大学中国基础教育质量监测协同创新中心，北京100088)

摘 要 数据缺失在测验中经常发生，认知诊断评估也不例外，数据缺失会导致诊断结果的偏差。首先，通过模拟研究在多种实验条件下比较了常用的缺失数据处理方法。结果表明：$\textcircled{1}$ 缺失数据导致估计精确性下降，随着人数与题目数量减少、缺失率增大、题目质量降低，所有方法的PCCR均下降，Bias 绝对值和RMSE均上升。 $\textcircled{2}$ 估计题目参数时，EM法表现最好，其次是MI，FIML和ZR法表现不稳定。 $\textcircled{3}$ 估计被试知识状态时，EM和FIML表现最好，MI和 ZR表现不稳定。其次，在PISA2015 实证数据中进一步探索了不同方法的表现。综合模拟和实证研究结果，推荐选用EM或FIML法进行缺失数据处理。

关键词认知诊断，GDINA模型，缺失数据，多重插补，极大似然估计

# 1引言

认知诊断评估(Cognitive Diagnosis Assessment,CDA)是最新一代的心理与教育测评技术，可以对个体认知过程、加工技能或知识结构进行诊断与评估。在CDA实施过程中，无法避免出现数据的缺失。已有研究表明，随着数据缺失率的增大，题目参数的估计精度及被试知识状态(Knowledge State,KS)的判准率均会下降，而选用不同的缺失值处理方法也会对模型拟合与参数估计带来不同影响(Dai,2017; Pan& Zhan,2020)。因此，在实际 CDA 测验中需要重视缺失数据问题，并选用合适方法处理，以提升诊断精度及题目参数估计精度。

目前，缺失数据的处理方法主要包括两大类：一是传统处理方法，如具有代表性的零替换(Zero Replace,ZR)方法。ZR法操作便捷，在处理大规模数据时非常快速，在绝大多数统计软件上均可实现，并且不会造成被试的大量流失。因此，ZR是研究者经常选用的方法之一，在 CDA中也有使用（Aryadoust& Goh,2001; Lee et al.,2011），且 ZR方法目前被较多大型教育评估，如PISA、TIMSS、PIRLS 所采纳(Xiao& Bulut,2020)。虽然传统方法比较便捷，但会导致统计效力和参数估计精度的下降，因此有研究者并不建议使用(Dong& Peng,2013;Enders,2010)。第二类是基于模型的处理方法，近年来，随着统计技术不断发展，基于模型的处理方法相继被提出，并被证明其处理效果优于传统方法，因此这些方法越来越受到重视。其中，极大似然估计(Maximum Likelihood Estimation,MLE)和MI(Multiple Imputation,MI)方法的应用最广泛(Rotnitzky,2008; Schafer& Graham,2002)。MLE 是通过加工似然函数对缺失数据进行处理，包括期望最大化算法(Expectation-Maximization algorithm,EM)和全息极大似然估计方法(Full Information Maximum Likelihood,FIML)。对于FIML、EM和MI三种方法，均有研究证明其表现优于传统方法(Graham,2009; Jelicic et al.,2010;Van Buuren,2018 ;Wothke,2000)。本文所采用方法的具体介绍请参见2.2部分。

CDA中探讨缺失值及其处理的研究中，一部分研究者仅探讨了缺失数据对诊断结果的影响，如Xu和 von Davier(2006)的研究表明：当数据缺失率达 $50 \%$ 时，认知诊断模型仍能得到较好的估计结果。但该研究未考虑不同的缺失机制，且仅考虑了缺失数据对参数估计的影响而未考虑缺失数据处理方法本身对结果产生的影响。Pan 和 Zhan(2020)在纵向诊断中探讨了缺失数据对诊断精度的影响，也得到相似的研究结果。Dai(2017)首次探讨了不同的缺失值处理方法在 CDA 中的表现，作者在 DINA(Deterministic Inputs,Noisy“and” Gate)模型(Junker& Sijtsma,2001)基础上，比较 EM和一些传统方法的表现，结果表明：在估计被试KS时，EM在多数条件下表现较好；在题目参数估计时，EM和传统方法的表现随条件改变而各不相同。

尽管已有上述文献研究了CDA中的缺失数据问题，但过往研究首先未曾考虑在缺失数据分析领域中表现较好、应用广泛的MI和FIML方法。其中，MI法已被证明其表现较为优异和稳健(Van Buuren,2018; Schafer& Graham,2002)，且于近年来被广泛用于缺失数据的处理中(Leacy et al.,2017; Rezvan et al.,2015)。FIML 采用“一步式”操作，直接使用带缺失值的作答数据进行模型拟合，比其它基于模型的方法更便捷(Graham,2009; Schafer &Graham,2002)，此外，基于模型的方法表现更加出色，但在不同研究背景下的表现有较大差异，取决于具体的模型、数据和条件(Newman,2003;Dai,2017)。因此，有必要在 CDA中系统地探索这些基于模型方法的表现，并与传统方法进行比较。

基于系统全面比较缺失值处理方法这一主旨，本研究还做了如下推进： $\textcircled{1}$ Dai(2017)采用的 DINA属于简约模型，它的非补偿模型特点往往与现实测验情景不符。而饱和模型，如 GDINA(Generalized Deterministic Inputs, Noisy“and" Gate)模型(de la Torre,2011)等受到了较多关注，并应用于多数研究中(Bai,2020;高旭亮等,2018)，GDINA不仅包含属性主效应，还将属性间交互作用考虑在内，更加符合现实情况，对实际测验拟合更佳，对GDINA及DINA模型的介绍及含义参见2.1部分。 $\textcircled{2}$ 现有诊断测验中比较缺失数据处理方法的研究仅使用了模拟研究，但模拟研究的生态效度如何并未在实证数据中得到检验，因此结果是否能进一步推至实际情况有待进一步验证。 $\textcircled{3}$ 除了MI和FIML，本文还选取了传统方法中具有代表性的ZR法，以及插补后可以得到无偏估计结果且在处理CDA及其它测验类型的数据缺失值时，表现较为优异的 EM方法(Dai.2017; Newman,2003;Rasmussen,2007)。

综上，本研究的主要目的是将MI和MLE法引入CDA中，对不同缺失数据处理方法进行全面比较，并提出实践中处理缺失数据的建议。下文首先对认知诊断模型和各缺失数据处理方法进行简单介绍。其次，通过模拟研究，在不同实验条件下探究了各缺失数据处理方法的表现。第三，以PISA2015年基于计算机测评中的数学素养为例，比较不同缺失数据处理方法在实证数据中的效果，验证不同方法的生态效度。最后，我们讨论了研究结果及未来研究的发展方向。

# 2认知诊断模型及缺失数据介绍

# 2.1认知诊断模型

本研究所采用的诊断模型为GDINA，其表达形式见公式(1):

$$
\begin{array} { r } { P \big ( \boldsymbol { Y } _ { i j } = 1 \big | \alpha _ { i j } ^ { * } \big ) = \delta _ { j 0 } + \sum _ { k = 1 } ^ { K _ { j } ^ { * } } \delta _ { j k } \alpha _ { i k } + \sum _ { k = k + 1 } ^ { K _ { j } ^ { * } } \sum _ { k = 1 } ^ { K _ { j } ^ { * } - 1 } \delta _ { j k k ^ { \prime } } \alpha _ { i k } \alpha _ { i k ^ { \prime } } + . . . + \delta _ { j 1 , . . . , K _ { j } ^ { * } } \prod _ { k = 1 } ^ { K _ { j } ^ { * } } \alpha _ { i k } \alpha _ { i k ^ { \prime } } . } \end{array}
$$

在 GDINA 模型中，被试在每道题目上被归为 $2 ^ { K _ { j } ^ { * } }$ 个潜类别，其中 $\begin{array} { r } { K _ { j } ^ { * } = \sum _ { k = 1 } ^ { K } q _ { j k } } \end{array}$ ，表示题目 $j$ 所考察的属性数量， $q _ { j k } { = } 1$ 表示题目 $j$ 考察了属性 $k$ 。 ${ \pmb { \alpha } } _ { \mathrm { i j } } ^ { * } = \left( \alpha _ { i j 1 } , . . . , \alpha _ { i j K _ { j } ^ { * } } \right)$ 为在被试属性向量 $\pmb { \alpha } _ { i j } = \left( \alpha _ { i j 1 } , . . . , \alpha _ { i j K _ { j } } \right)$ 基础上，仅保留题目 $j$ 所考察属性，形成的坍塌(collapse)属性向量 $( K _ { j }$ 为测验考察的所有属性个数)。 $\delta _ { j o }$ 为题目 $j$ 的截距项，即当被试未掌握题目所考察属性时正确作答的基线参数。 $\delta _ { j k }$ 为属性 $k$ 的主效应，表示当被试仅掌握某一属性 $k$ 时，对正确作答概率的影响。 $\delta _ { j k k } ^ { \quad }$ 是题目 $j$ 在属性 $k$ 和 $k ^ { \prime }$ 上的二阶交互效应，表示同时掌握两个属性对正确作答概率的影响。 $\delta _ { j 1 , . . . , K _ { j } ^ { * } }$ 为题目 $j$ 在属性 $I , 2 , . . . , K _ { j } ^ { * }$ 上的最高阶交互作用，表示掌握了题目 $j$ 考察的所有属性时，对正确作答概率的影响。其中，截距项 $\delta _ { j o }$ 衡为非负数，主效应项为非负数，而交互作用项可以取任意值。

GDINA模型属于饱和模型，对GDINA进行约束，即仅保留公式（1）中的截距项和最高阶交互项，便可得到 DINA模型： $\begin{array} { r } { P \big ( Y _ { i j } = 1 \big | \pmb { \alpha } _ { i j } ^ { * } \big ) = \delta _ { j 0 } + \delta _ { j 1 , \dots , K _ { j } ^ { * } } \prod _ { k = 1 } ^ { K _ { j } ^ { * } } \alpha _ { i k } } \end{array}$ 。其含义为：当且仅当被试i掌握了题目j考核的所有属性时，该被试倾向于答对这道题目；而当被试i未掌握题目j考核的所有属性时，即认为该被试倾向于答错这道题目。

# 2.2缺失数据机制介绍

缺失数据可以通过缺失机制进行分类，Rubin(1976)定义了三种缺失的数据机制；完全随机缺失(missing completely at random,MCAR)，随机缺失(missing at random,MAR)和非随机缺失(missing not at random,MNAR)。在 MCAR 机制下，数据的缺失是完全随机的，不依赖于任何变量，即不论其它变量（如题目难度、区分度、被试能力值等）如何变化，数据产生缺失的概率都是均等的；在MAR机制下，数据缺失的概率并不是随机的，会受到数据集中已观测到的、不含缺失值的变量（如被试年龄、能力值等）的影响，但不受缺失数据自身的影响；在MNAR机制下，数据缺失的概率与缺失变量本身相关，如某一问题设计的过于敏感造成的缺失。

在心理教育测评中，这三种缺失数据的机制都有可能存在。Huisman 和 Molenaar(2001)认为，测评中缺失的作答是由学生无意中报告的，因此将测评中的缺失数据视为MCAR机制下的缺失；还有研究者假设测评中存在MAR机制，因为数据的缺失与特定的个体特征有关(De Ayala elal.,2001;Finch,2008);还有研究表明在某道题目上数据的缺失是受到题目本身特征的影响，即存在MNAR 缺失机制(Brown et al.,2014)。

# 2.3缺失数据的处理方法

依据前文综述，本研究选取了常见且被广泛使用的传统方法 ZR法(Aryadoust＆Goh,2001; Lee et al.,2011)。基于模型的缺失数据处理方法中应用最为广泛(Rotnitzky,2008;Schafer & Graham,2002; Leacy et al.,2017; Rezvan et al.,2015)，处理缺失值效果更具优势(Rasmussen,2007; Graham,2009; Jelicic etal.,2010;Wothke,2000)并且适用于二分变量插补(Marshall et al.,2010; Van Buuren, 2018)的 MI-PMM、MI-CART、MI-LOGREG.BOOT、EM和 FIML 这几种方法。

# 2.3.1零替换(ZR)

零替换，即将缺失的作答视为错误回答，用“0”值替换缺失数据。再将替换好的完整数据集输入模型，进行分析。

# 2.3.2多重插补(MI)

多重插补(Rubin,1976)是一种基于重复模拟的缺失数据处理方法，MI包括三个步骤：

插补(imputation)、分析(analysis)和合并(pooling)。首先，MI依据具体的插补模型(MI-PMM、MI-CART、MI-LOGREG.BOOT)对缺失数据进行多次插补，最终得到多个经插补后的完整数据（最好是 20个或更多；Graham et al.,2007）。然后依照模型（如线性模型、广义线性模型等）对这20或更多个完整数据集进行分析，依据Rubin规则计算各完整数据的参数估计值，最后将参数估计最佳的插补结果输出（Mazzaetal.,2015）。最终输出的插补结果将作为完整数据集输入模型，进行分析。

由于本研究考虑的是二级计分形式，且具备局部独立性，因此在使用MI对作答矩阵进行插补时，分别选择各插补模型对数据进行多次插补（ $\scriptstyle { m = 2 0 }$ ），并从插补好的数据集中随机抽取一个完整数据集作为插补结果。MI系列方法中的分类回归树方法(Classificationand regression trees,MI-CART)、预测均值匹配(Predictive mean matching,MI-PMM)和自助比率对数回归(Logistic regression with bootstrap,MI-LOGREG.BOOT)均适用于二分变量插补,且在处理缺失数据时表现较好(Marshallet al.,2010; Van Buuren,2018)，因此本研究主要选择了这三种 MI模型。MI系列方法的具体公式和详细操作步骤可参见Van Buuren(2018)书中的具体介绍，下面对各方法原理与基本步骤进行介绍。

（1）MI-PMM：PMM即预测均值匹配，它根据指定的回归模型计算缺失值的预测值，从而进行插补。已知Y为作答矩阵，记Y'为删除Y中作答存在缺失值的被试后，由所有不含缺失值被试的作答数据构成的矩阵。PMM大致步骤如下：1)使用Y'数据，建立多元回归模型，估计得到回归参数。2)对第一步中得到的回归参数进行修正，得到一个适用于Y中所有被试的回归模型，并使用这一回归模型计算出所有被试的估计值。3)针对每一个存在缺失数据的被试，匹配多个估计值与其估计值近似且不含缺失数据的被试，构成捐赠者库，从捐赠者库中随机抽取数值替换缺失数据，实现对缺失数据的插补。此方法假设缺失值的分布与候选数据集相同，并使用已有数据中非缺失部分对缺失值进行插补，从而避免了无意义插补的问题（例如，身高为负值）(Van Buuren,2018)。

（2）MI-CART：CART即分类回归树，是一种回归与分类技术。该方法一般使用递归划分法构建预测模型，将待处理的所有变量划分为尽可能同质的类别，最终形成决策树，并从与缺失作答相似的节点中随机抽取完整作答，对缺失数据进行插补。其操作步骤如下：1）使用递归法对作答矩阵中的数据进行多次切分，模型将选择具有最佳分裂和最均匀子群的切分点作为最佳切分点，将数据切分为两个子节点。2）多次重复第一步，直至数据不可再分。此时，每一个子节点下的数据均同质，经切分得到的结果即为作答矩阵的分类回归树。3）对每一个缺失作答，根据分类回归树找到它所属的终端节点，并从该节点中随机抽

取作答对缺失数据进行插补。

（3）MI-LOGREG.BOOT：该方法使用基于Bootstrap 的贝叶斯逻辑回归模型对缺失数据进行插补。Bootstrap 法的原理是以样本代表总体，在样本中进行有放回抽样，每次重复抽取 $n$ 个数据组成一个样本，重复这一过程多次得到多个样本，最后基于这些样本进行统计计算。MI-LOGREG.BOOT通过贝叶斯逻辑回归模型进行，对经 bootstrap 法处理后的作答矩阵进行回归分析，通过计算和比较拟合所得参数，选取拟合结果最佳的数据对缺失值进行插补(Van Buuren,2018)。

# 2.3.3 期望最大化算法(EM)

EM 算法是一种通过计算极大似然对缺失进行处理的迭代算法(Dempster et al.,1977)。此方法原理是认为存在一个估计参数，与缺失数据相关且可以互相推导。因此给定估计参数的初始值，即可以通过不断迭代对缺失数据进行插补。每一次迭代包括了E步和M步。E 步即期望步，依据现有数据和前一次迭代所得到的估计参数，对缺失数据进行填补，并计算其对数似然函数的条件期望；M步即极大化步，用极大化对数似然函数进一步确定估计参数的值，并用于下一步迭代。算法在E步和M步之间不断迭代，直至两次迭代之间的参数变化较小时结束(叶素静等,2014)。EM的具体公式和详细操作步骤可以参考 Dempster等(1977)研究中的具体介绍，下面对其原理与基本步骤进行介绍。定义 $Y _ { o b s }$ 为已观测到的、未缺失的数据，定义 $Y _ { m i s }$ 为缺失数据，则含有缺失数据的作答矩阵 $\boldsymbol { Y = } ~ ( \boldsymbol { Y _ { o b s } } , \ : Y _ { m i s } )$ ，EM法就是使用待估参数 $\theta$ 和 $Y _ { o b s }$ ，对 $Y _ { m i s }$ 进行插补。EM方法在CDA中的实现过程为：

1)首先给定参数0的初始值， $\theta$ 是一系列用于定义 $Y$ 分布的参数合集。例如通过定义均值和方差，假设作答矩阵Y为正态分布，则此时初始估计参数θ可记作： $\scriptstyle \theta = ( \mu , \sigma ^ { 2 } )$ 。

2)E步：对于 $Y _ { m i s }$ 中的任一缺失数据 $y _ { \mathrm { i j } }$ ，使用第一步给定的 $\theta$ 和 $Y _ { \mathrm { o b s } }$ ，计算 $Y _ { o b s }$ 的条件期望值，并用这一期望值代替缺失数据，如公式(2)所示。其中 $i$ 为被试， $j$ 为题目， $\mathbf { \chi } _ { t }$ 为迭代次数。

$$
y _ { i j } ^ { ( t ) } = E ( y _ { i j } | Y _ { o b s } , \theta ^ { ( t ) } )
$$

3)M步：使用似然函数 $\varrho$ 与经E步处理后的作答矩阵Y，计算最大似然的参数估计值，如公式(3)所示，并选取满足最大似然值的参数值 $\theta$ ，作为新一轮迭代中的参数估计值。

$$
Q ( \theta ^ { ( t + 1 ) } | \theta ^ { ( t ) } , Y ) = \operatorname* { m a x } { ( Q \big ( \theta \big | \theta ^ { ( t ) } , Y \big ) ) }
$$

4)不断重复步骤2-3直到参数估计结果收敛，例如前后两次迭代之间参数估计的变化量： $\| Q ( \theta ^ { ( t + 1 ) } | \theta ^ { ( t ) } , Y ) - Q ( \theta ^ { ( t ) } | \theta ^ { ( t - 1 ) } , Y ) \|$ 小于特定值（如.0001）。

同MI法相同，将EM处理后的完整数据集输入模型，进行后续的分析。

# 2.4.4全息极大似然估计算法(FIML)

与删除方法不同，FIML不排除缺失作答的情况。包括不完整案例的观察分数可以提高准确性，因为不完整变量与其他（完整或不完整）变量之间的关联会告知估计程序哪些参数值最有可能（Mazza etal.,2015）。FIML 使用缺失数据中所有的可用数据建立模型，并运用似然函数估计参数，对缺失数据进行处理(Eekhout et al.,2015)。例如，在运用 FIMI方法对包含缺失值的数据进行题目参数估计时，其似然函数的计算只连乘在该题目上有作答的数据的正确作答概率值，而未作答的数据不参与计算。不同于其它方法需要先插补再估计，FIML仅需要一步，就可以同时实现缺失数据处理和参数估计过程，因此更加高效(Graham,2009)。不同于以上几种方法，在本研究中，使用R中的GDINA 包进行 FIML方法的处理，FIML方法为GDINA包的默认处理缺失值方法，即当输入的作答矩阵为包含缺失数据的矩阵时，软件默认使用FIML方法进行处理和模型的分析。

# 3模拟研究

# 3.1研究设计

为了充分探讨不同缺失数据处理方法在CDA中的表现，本研究采用 $2 \times 3 \times 3 \times 3 \times 3 \times$ 6的完全交叉实验设计，共包含六个自变量，其设置如下所示：

（1）被试数量：包括三个水平，200人、400人和1000人(Dai,2017;de la Torre,2011);(2）题目数量：包括两个水平：15 题和30题(Dai,2017);（3）题目质量：参照Ma等人(2016)的设置包含三个水平：高质量、中等质量和低质量。题目为低质量时，参数设定为： $\mathsf { P } \big ( Y _ { i j } = 1 \big | \alpha _ { \mathbf { i j } } ^ { * } = \mathbf { 0 } \big ) \in U ( 0 . 0 5 , 0 . 1 5 )$ ，$\mathsf { P } \big ( Y _ { i j } = 1 \big | \alpha _ { \mathbf { i j } } ^ { * } = \mathbf { 1 } \big ) \in U ( 0 . 8 5 , 0 . 9 5 )$ ；题目为中等质量时，参数设定为： $\mathrm { P } \big ( Y _ { i j } = 1 \big | { \pmb \alpha } _ { \mathbf { i j } } ^ { * } = \mathbf { 0 } \big ) \in$ U(0.15,0.25)， $\mathsf { P } \big ( Y _ { i j } = 1 \big | \alpha _ { \mathbf { i j } } ^ { * } = \mathbf { 1 } \big ) \in U ( 0 . 7 5 , 0 . 8 5 )$ ；题目为高质量时，参数设定为：（24 $P \big ( Y _ { i j } = 1 \big | \alpha _ { i j } ^ { * } = \mathbf { 0 } \big ) \in U ( 0 . 2 5 , 0 . 3 5 ) , P \big ( Y _ { i j } = 1 \big | \alpha _ { i j } ^ { * } = \mathbf { 1 } \big ) \in U ( 0 . 6 5 , 0 . 7 5 ) , P \big ( Y _ { i j } = 1 \big | \alpha _ { i j } ^ { * } = \mathbf { 0 } \big )$ 表示被试 $i$ 未掌握题目 $j$ 考察的所有属性时，答对题目的概率。 $\mathrm { P } \big ( Y _ { i j } = 1 \big | { \pmb \alpha } _ { \mathrm { i j } } ^ { * } = { \bf 1 } \big )$ 表示被试$i$ 掌握了题目 $j$ 考察的所有属性时，答对题目的概率。其中， $Y _ { i j }$ 为被试 $i$ 在题目 $j$ 上的作答情况， $\pmb { \alpha } _ { i j } ^ { * }$ 为在被试原属性向量基础上，仅保留题目 $j$ 所考察属性形成的坍塌属性向量。

（4）数据缺失机制：包括三种缺失机制：MCAR、MAR 和 MNAR(De Ayala,2001;Finch, 2008);（5）数据缺失率：包括三个水平： $10 \%$ 、 $20 \%$ 、 $30 \%$ (Dai, 2017);

（6）缺失数据处理方法：ZR、MI-CART、MI-PMM、MI-LOGREG.BOOT、EM 和FIML方法；其中， $\varrho$ 矩阵设定参见附录一。

3.2模拟过程

（1）完整数据生成：被试KS真值从多元正态分布中生成，即 $\alpha { \sim } M V N ( 0 _ { K } , \Sigma )$ ，协方差设定为0.5(如下所示)。被试作答数据使用R软件中GDINA包的 simGDINAO函数生成(Ma & de la Torre,2020)。

$$
\Sigma = \ { \left[ \begin{array} { l l l } { 1 } & { \ldots } & { . 5 } \\ { \ldots } & { \ldots } & { \ldots } \\ { . 5 } & { \ldots } & { 1 } \end{array} \right] }
$$

(2）缺失数据生成：缺失数据的生成参考De Ayala等(2001)和Finch(2008)提出的方法，具体的生成过程参见附录二。

（3）缺失数据处理：使用R软件与 SPSS26.0实现。首先，ZR法通过自编R代码实现。MI方法使用R 软件中的 MICE 包(van Buuren& Groothuis-Oudshoorm,2011)完成。为了保证处理效果，参照Chen 等(2020)的研究将 MI插补次数设定为20次。其次，在使用 EM方法插补缺失数据时，我们首先采用了R软件中 TestDataImputation 包中的 EMimpute 函数，但在数据规模大、缺失比例较高（例：1000人、30题、 $30 \%$ 缺失率）时，R软件无法运行。因此，最终选用了SPSS26.0进行EM插补处理。FIML方法通过R软件中的GDINA包完成。

3.3评价指标

参数估计精度评价指标为偏差Bias、均方根误差RMSE(Ma&dela Torre,2016)，计算见公式(2)和公式(3)。

$$
{ \cal B } \mathrm { i } \mathrm { a s } = \frac { \sum _ { r = 1 } ^ { R } \sum _ { c = 1 } ^ { 2 ^ { K } } \sum _ { j = 1 } ^ { J } [ \hat { P } ^ { ( r ) } ( Y _ { \jmath } = 1 | \alpha _ { c } ) - P ^ { ( r ) } ( Y _ { \jmath } = 1 | \alpha _ { c } ) ] } { J \times 2 ^ { K } \times R }
$$

$$
R M S E = \sqrt { \frac { \sum _ { r = 1 } ^ { R } \sum _ { c = 1 } ^ { 2 ^ { K } } \sum _ { j = 1 } ^ { J } [ \hat { P } ^ { ( r ) } ( Y _ { \jmath } = 1 | \alpha _ { c } ) - P ^ { ( r ) } ( Y _ { \jmath } = 1 | \alpha _ { c } ) ] ^ { 2 } } { J \times 2 ^ { K } \times R } }
$$

其中， $\hat { P } ^ { \mathrm { ( r ) } } ( Y _ { _ { J } } = 1 | \alpha _ { _ c } )$ 表示KS为 $\alpha _ { c }$ 的被试答对第 $j$ 题的估计作答概率，$P ^ { \mathrm { ( r ) } } ( Y _ { \mathnormal { J } } = 1 | \alpha _ { \mathnormal { c } } )$ 表示KS为 $\boldsymbol { \alpha } _ { c }$ 的被试答对第 $j$ 题的真实作答概率， $R$ 表示总循环次数， $\boldsymbol { r }$ 表示当前循环次数。Bias和RMSE越大，表明题目参数估计误差越大。

被试属性掌握的估计精度评价指标采用模式判准率(Pattern Correct Classification Rate,

PCCR)，计算见公式(4)。

$$
\mathit { P C C R } = \frac { \sum _ { \mathrm { { r } = 1 } } ^ { R } \sum _ { i = 1 } ^ { I } \mathit { p m } _ { i r } } { \mathit { R } \times I }
$$

其中， $I$ 为被试总数， $p m _ { i r } { = } 1$ 表示第 $\boldsymbol { r }$ 次循环中被试的KS判断正确，反之表示判断错误。

3.4模拟研究结果和讨论

由于MAR与MCAR机制下的结果基本相同，遂将MCAR的结果呈现于附录三。

3.4.1MAR机制的结果和讨论（1）题目参数估计结果与讨论

图1和图2呈现了MAR机制下题目参数的估计结果，共包含324个条件。随被试数量和题目数量的增多，题目质量的提高和缺失率的降低，题目参数估计精度在提升。

整体来看，题目参数的估计偏差均较低，各方法表现均较好。其中，EM法的表现最好，其后依次为MI、FIML 和 ZR法。EM倾向于产生无偏估计，其 Bias 值分布范围为-0.003\~0.001，非常接近0；RMSE分布范围为0.014\~0.100，是所有处理方法中值最小的。MI也倾向于产生无偏估计，但其表现略差于EM，其Bias分布范围为！ $- \ 0 . 0 0 3 { \sim } 0 . 0 0 1$ ，RMSE 分布范围为0.013\~0.101。FIML倾向于高估题目参数，其Bias值分布范围为-$0 . 0 0 0 1 { \sim } 0 . 0 0 8$ ；RMSE分布范围为0.013\~0.113。ZR倾向于低估题目参数，其Bias值分布范围为 $- \ 0 . 0 1 9 \sim - \ 0 . 0 0 3$ ，均小于0；RMSE分布范围为0.025\~0.105。首先，不难看出，EM和 MI处理缺失数据后估计得到的题目参数精度最高，但其余方法的表现也不差，仅是相对而言略差，因为其中最大的Bias绝对值及RMSE 值仅为0.019和0.113。这一结果表明，这些方法处理缺失数据均能够得到较为理想的题目参数估计精度。其次，MI系列中的三种方法的Bias 和RMSE 相似性较高，因此若要选用MI方法，MI系列中的任一方法均可。最后，被试数量越多，题目质量越高，基于模型的方法表现越好，而 ZR的表现则相反。这表明与传统插补方法相比，基于模型的方法更适合用于规模较大的测验情景。出现该结果的原因可能是基于模型的方法使用了数据中未缺失的作答信息进行建模，数据质量越好，规模越大，就越能从已有的作答数据中获得有效信息，从而提升了处理后的数据质量，使得估计结果更好。而 ZR法将未作答信息全部用零值替换，这种替换会增大作答数据集当中的噪音，扭曲真实数据结构，当数据集越大，其噪音也就越大，最终导致估计精度下降。因此，在测验尤其是大规模测验中，应该使用基于模型的插补方法。

![](images/c9f9a0f5eb1861879a0bd08a184f6f7c7de449a17867160af83a801e059fe35d.jpg)  
图1不同处理方法下题目参数的Bias(MAR机制)

注：横坐标条件中第一个字母表示题目质量（H:高质量，M：中等质量，L：低质量），第二个数字表示缺失率( $10 \%$ ， $20 \%$ $30 \%$ )。Zero Replacement 代表零替换法，mice-pmm,mice-logreg.boot, mice-cart 依次代表了多重插补中的预测均值匹配，基于Bootstrap 的贝叶斯逻辑回归和分类回归树法，EM代表期望最大化法，FIML 代表了全息极大似然估计法。

![](images/71b9bc7ba4a6599995537c4cd47fc76f16a5a19af0157c29275670c0afffa459.jpg)  
图2不同处理方法下题目参数的RMSE(MAR机制)

（2）PCCR估计结果与讨论

图3呈现了MAR机制下模式判准率的估计结果，共包含324个条件。随着被试和题目数量的增多，题目质量的提高和缺失率的降低，各方法的模式判准率均会增大。

总体而言，EM和FIML表现最好，其后依次为MI和 ZR。首先，EM法的PCCR 在多数条件下最高，其范围为0.144\~0.855。FIML和EM相似，其PCCR的范围为 $0 . 1 2 3 { \sim } 0 . 8 6 6$ 值得注意的是，FIML 估计PCCR时表现较好，尽管它在估计题目参数时不是表现最好的方法，例如在MAR机制下，FIML与表现最佳的EM法之间的Bias 差值最大仅为0.008,RMSE 差值最大仅为0.014，尤其在题目数量较大、题目质量较高时，其表现尤佳。且FIML 法的操作比EM和MI法更加便捷，前者属于“一步式”操作，即无需填充未作答数据，仅用已作答数据即可进行参数估计；后两者属于“两步式"操作，需要先将缺失数据插补出来，之后再使用诊断模型进行参数估计。因此，出于便捷性考虑，可将FIML作为首选方法。其次，MI法表现居中，且MI系列中的三种方法的PCCR曲线相似度也较高，其PCCR 的范围为0.114\~0.838，略低于FIML和EM法，但高于ZR（PCCR范围为

![](images/7c756b111bf8d7293d1c016c8e9318b5bc0545715548d6cf368a8c9135e44429.jpg)  
图3不同处理方法下题目参数的PCCR（MAR机制）

# 3.4.2MNAR机制的结果与讨论

（1）题目参数结果和讨论

图4和图5呈现了MNAR机制不同条件下题目参数的估计结果，共包含324个条件。随被试和题目数量的增多，题目质量的提高和缺失率的降低，各方法的题目参数估计精度均在提升。

与MAR类似，MNAR机制下题目参数的Bias绝对值和RMSE整体较低，表明各方法表现均较好。其中，EM表现最好，其后依次为ZR、MI和FIML。EM倾向于高估题目参数，其 Bias分布范围为-0.003\~0.010，RMSE分布范围为0.015\~0.109。ZR倾向于低估题目参数，其Bias分布范围为 $- \ 0 . 0 1 1 { \sim } \ - \ 0 . 0 0 1$ ，RMSE分布范围为0.017\~0.099。MI倾向于高估题目，其Bias分布范围为-0.0005\~0.010，RMSE分布范围为0.015\~0.107。FIML 倾向于高估题目参数，其Bias值分布范围为0.002\~0.016，RMSE分布范围为 $0 . 0 1 4 { \sim } 0 . 1 1 5$ 。结果显示：首先，与MAR机制相比，MNAR机制下EM和MI法的Bias 绝对值增大，由无偏估计变为高估题目参数，ZR法的Bias绝对值和RMSE变小，表现变好。其次，ZR的表现和MI相似但不如MI稳定，它主要受题目质量的影响，例如，在30题目400人、低题目质量、缺失率为 $30 \%$ 时，ZR法的RMSE在所有方法中最小，而相同条件下高题目质量时，ZR的RMSE在所有方法中最大。同 MAR与MCAR机制类似，EM的总体偏差较小，表现较好，且随着被试量的增多表现变得更好。这也和前文的结果一致，题目质量越高，ZR 表现越差，基于模型的方法表现越好。MI系列中的三种方法的表现较为相似。

![](images/c8f1fc833d4de881432fe128d3c785c21219c8c39730ffdb2fd99403c5ad5836.jpg)  
图4不同处理方法下题目参数的Bias(MNAR机制）

![](images/425be77e200c036b3e15c35f965ee1eb6baf19cc14a17d86e6d6aa458f2f1efd.jpg)  
图5不同处理方法下题目参数的RMSE（MNAR机制）

（2）PCCR的结果和讨论

图6呈现了在MNAR机制下题目参数的估计结果，共包含324个条件。随被试和题目数量的增多，题目质量的提高和缺失率的降低，各方法的模式判准率均增大。

在30题、1000人、高题目质量且缺失率 $30 \%$ 时，PCCR最高的ZR法与最低的MILOGREG.BOOT法相差0.134，因此，与题目参数的估计不同，估计被试KS时，各方法间的差异较大。具体而言，EM、FIML 和 ZR并列为表现最好的方法，MI次之。其中，EM法的PCCR 范围为0.128\~0.857，FIML的范围为 $0 . 1 2 1 { \sim } 0 . 8 7 0$ ，ZR 的范围为0.111\~0.863。MI和另三种方法相比表现略差但差异不明显，其PCCR 范围为 $0 . 1 0 5 { \sim } 0 . 8 4 3$ 。首先，综合题目参数和PCCR的结果，相较于MAR 和MCAR机制，ZR在MNAR机制下表现更好，这一现象的原因可能是：MNAR机制下，缺失数据对应的原始作答为"0”（即答错）的可能性更高，即认为缺失的产生是由于被试无法作答，与被试的知识掌握状态有关；而 ZR方法正好使用“0”替换缺失值，同样将缺失看作是由于被试不会作答产生的。因此，使用“0"替换缺失数据的 ZR法正符合MNAR的缺失原理，ZR 法在MNAR机制下的表现更好。

其次，与MAR机制类似，几乎在所有条件下，MI的系列方法对被试KS和题目参数估计结果均较为相似，这是因为MI系列方法均基于MI框架进行缺失数据插补。

![](images/db06a62d29ba64fcbeac1ff8eb731626128ecdf8fabb340acf41a73c709f0089.jpg)  
图6不同处理方法下题目参数的PCCR（MNAR机制）

# 4实证研究

# 4.1研究数据

为进一步探讨不同缺失值处理方法的生态效度，本研究参考 Shan 和 Wang(2020)的实证研究，使用了PISA2015年基于计算机测评的数学测验数据作为实证数据，主要原因为：$\textcircled{1}$ 缺失比例合适，能够展现出不同缺失值处理方法之间的差异。若缺失率较小，不同缺失值处理方法得到的效果可能差异不会很明显；缺失率较大时（如 $30 \%$ ），所有的缺失值处理方法均表现较差，此时的比较也没有任何意义。 $\textcircled{2}$ 具备已标定好的Q矩阵。 $\textcircled{3}$ 属于大型测验，结果可靠。数据包含了九道题目，这些题目在PISA2015中的题号分别为CM033Q01, CM474Q01, CM155Q01, CM155Q04, CM411Q01, CM411Q02, CM803Q01,CM442Q02和CM034Q01，题目作答结果均为二分变量。这些题目共考察了四个属性：区别与联系 $( \alpha _ { 1 } )$ 、数量 $( \alpha _ { 2 } )$ 、空间与形状 $( \alpha _ { 3 } )$ 和不定性与数据 $( \alpha _ { 4 } )$ 。实证 $\varrho$ 矩阵参考了Shan 和

Wang(2020)的研究，参见附录四。本研究选择了多米尼加共和国的735名被试进行分析，被试作答结果中，0表示作答错误，1表示作答正确，5\~9表示作答缺失。该数据集的缺失比率在各题目上的分布从 $0 { \sim } 2 4 . 0 8 \%$ 不等，总缺失率为 $1 4 . 0 2 \%$ ，缺失比例适中。使用模拟研究中的六种方法对该数据集中的缺失数据进行处理，并采用GDINA模型进行估计。

# 4.2评价指标

由于实证数据中的KS和题目参数真值未知，无法使用模拟研究的评价指标，因此，采用以下几个评价指标：1）相对拟合指标：偏差(Deviance)、赤池信息准则(Akaikeinformation Criterion,AIC; Akaike,1974)和贝叶斯信息准则(Bayesian information criterion,BIC; Schwarz,1978)。2）绝对拟合指标：Limited-information statistic $\mathbf { M } _ { 2 }$ 和 root mean squareerror of approximation (RMSEA2)(Liu et al.,2016)。3）其他指标：题目参数估计标准误(Standard Error, SE)和相关性(Correlation, Cor)。

各指标中，Deviance、AIC 和BIC 值越小，数据与模型拟合效果越佳，表明经该方法处理的缺失值效果更好。 $\mathbf { M } _ { 2 }$ 和RMSEA2都是衡量模型与数据的拟合程度的指标，这两个指标越小，表明模型拟合结果越好。此外，对于RMSEA2，Liu等(2016)认为，0.045 是模型良好拟合的标准，0.03 是最佳拟合的标准。SE 指模型估计所得题目参数的标准误，SE 越小，表明题目参数估计结果的离散程度越小，数据越稳定。在估计 SE时，采用不同的信息矩阵会得到不同精度的结果(Liuetal.,2021)。本研究采用GDINA包中的经验交叉相乘方法计算SE，该方法的优点是操作便捷，且估计参数时表现较好，在CDM研究中也较常使用（De la Torre,J,2009; Najera et al.,2021; Xu et al.,2020)。相关性指被试在测验上的原始得分与其估计的属性掌握数量之间的相关性，该指标的原理是，被试属性掌握数量越多，其原始得分理应越高(郭磊,周文杰,2021)。使用某一种方法对缺失值进行处理后，得到的相关性指标越高，说明缺失值处理效果越好。

# 4.2实证研究结果与讨论

实证研究估计得到的各指标结果如表1（相关性和相对拟合指标）和表2（绝对拟合指标）所示。就相关性指标而言，EM的相关性最高，为0.809，表明这种方法处理缺失数据的效果最佳；其次是FIML和 ZR法，相关性分别为0.808 和0.804，但它们的相关性仅略低于EM，表明它们处理缺失数据的效果基本相似；之后依次为MI-LOGREG.BOOT、MI-PMM和MI-CART，相关性分别为0.800、0.793和0.756。Deviance 分布范围为4169.45\~4633.08，AIC 分布范围为4235.45\~4694.79，BIC分布范围为4387.25\~4846.59。其中，FIML的Deviance、AIC和BIC 值均最小，表明拟合效果最好，之后依次是 MI

LOGREG.BOOT、EM、ZR、MI-CART和MI-PMM法。SE 指标分布范围为0.243\~0.268,其中 MI-PMM法的 SE最小，之后依次是 ZR、EM、FIML、MI-LOGREG.BOOT 和 MI-CART法，表明MI-PMM的题目参数估计稳定性表现最好。在绝对拟合指标中，EM、ZR和 MI-PMM的 $\mathbf { M } _ { 2 }$ 值的 $\mathfrak { p }$ 值均大于.05，表明对这批实证数据的拟合效果较好；EM、ZR 和MI-PMM的RMSEA2均小于0.03，表明其拟合效果更佳。

综合各项指标（选取了每项指标上表现最好的三种方法，用“一”表示，并呈现了各方法得到“ $\nu$ ”的总数和排名），如表3所示。在各个指标的表现上，EM、FIML、MI-PMM三者均在某一个或多个指标上表现最好。从表3汇总结果看，EM在所有指标上表现均较好，是最佳选择。ZR 和FIML方法次之，然后为MI-PMM、LOGREG.BOOT 和 MI-CART，该结果与NMAR机制下的实验结果类似。实证研究与模拟研究的MNAR机制下得到的结果很相似。PISA作为大型国际测验，十分受到重视，被试由于个人或环境原因退出测验的可能性较小，由于不会作答而放弃造成作答缺失的可能性较大，这也是ZR法表现较好的原因之一。同时这也与 Shan 和Wang(2020)的研究结果相符。她们运用引入题目层面的缺失数据机制的CDM对阿尔巴尼亚共和国的数据进行分析，发现数据的缺失机制更接近MNAR机制。此外，MI系列方法在模拟研究中表现相似，但在实证研究中差异较大，说明选用MI系列方法时需要结合实际数据进行模型拟合验证，并根据拟合结果进行选择。

综上，实证研究进一步支持了模拟研究结果，所探讨的缺失数据处理方法具有较高的生态效度。

表1实证研究结果1  

<html><body><table><tr><td rowspan="2">处理方法</td><td colspan="5">参考指标</td></tr><tr><td>Cor</td><td>Deviance （-2LL)</td><td>AIC</td><td>BIC</td><td>SE</td></tr><tr><td>ZR</td><td>0.804</td><td>4345.98</td><td>4411.98</td><td>4563.77</td><td>0.256</td></tr><tr><td>MI-PMM</td><td>0.793</td><td>4633.08</td><td>4648.78</td><td>4800.58</td><td>0.243</td></tr><tr><td>MI-LOGREG.BOOT</td><td>0.800</td><td>4170.47</td><td>4347.45</td><td>4499.24</td><td>0.263</td></tr><tr><td>MI-CART</td><td>0.756</td><td>4628.56</td><td>4694.79</td><td>4846.59</td><td>0.268</td></tr><tr><td>EM</td><td>0.809</td><td>4343.13</td><td>4409.13</td><td>4560.93</td><td>0.258</td></tr><tr><td>FIML</td><td>0.808</td><td>4169.45</td><td>4235.45</td><td>4387.25</td><td>0.260</td></tr></table></body></html>

表2实证研究结果2  

<html><body><table><tr><td rowspan="2">处理方法</td><td colspan="5">绝对拟合指标</td></tr><tr><td>M2</td><td>df</td><td>p</td><td>RMSEA2</td><td>90%CI</td></tr><tr><td>ZR</td><td>16.69</td><td>12</td><td>0.162</td><td>0.023</td><td>[0,0.047]</td></tr><tr><td>MI-PMM</td><td>13.81</td><td>12</td><td>0.313</td><td>0.014</td><td>[0,0.042]</td></tr><tr><td>MI-LOGREG.BOOT</td><td>22.54</td><td>12</td><td>0.032</td><td>0.035</td><td>[0.01,0.056]</td></tr><tr><td>MI-CART</td><td>22.14</td><td>12</td><td>0.036</td><td>0.034</td><td>[0.009,0.056]</td></tr></table></body></html>

<html><body><table><tr><td>EM</td><td>17.19</td><td>12</td><td>0.143</td><td>0.024</td><td>[0,0.048]</td></tr><tr><td>FIML</td><td>22.64</td><td>12</td><td>0.031</td><td>0.035</td><td>[0.01,0.057]</td></tr></table></body></html>

表3实证研究结果汇总  

<html><body><table><tr><td rowspan="2">处理方法</td><td colspan="7">参考指标</td><td>√的总数</td><td>排序</td></tr><tr><td>Cor</td><td>-2LL</td><td>AIC</td><td>BIC</td><td>SE</td><td>p</td><td>RMESA2</td><td></td><td></td></tr><tr><td>ZR</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>4</td><td>2</td></tr><tr><td>MI-PMM</td><td></td><td></td><td></td><td></td><td></td><td><</td><td>v</td><td>3</td><td>3</td></tr><tr><td>MI-LOGREG.BOOT</td><td></td><td></td><td>√</td><td></td><td></td><td></td><td></td><td>3</td><td>3</td></tr><tr><td>MI-CART</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0</td><td>4</td></tr><tr><td>EM</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>7</td><td>1</td></tr><tr><td>FIML</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>4</td><td>2</td></tr></table></body></html>

# 5结论与展望

# 5.1研究结论

（1）缺失数据会对认知诊断估计产生影响，缺失率的增大会导致所有方法的PCCR 和题目参数估计精度下降。此外，随着被试与题目数量的减少和题目质量的下降，所有方法的PCCR均下降，Bias 绝对值和RMSE均上升，表现变差。

（2）整体而言，所有方法都能得到较为精确的题目参数估计值，不同方法间差异不大。其中，在MAR/MCAR机制下，EM的表现最好，其后依次为MI、FIML和 ZR法；在MNAR 机制下，EM表现最好，其后依次为ZR、MI和FIML。

（3）估计被试KS时，不同方法间PCCR差异较大。MAR/MCAR机制下，EM 和FIML 表现最好，其后依次为MI和 ZR；MNAR 机制下，EM、FIML 和 ZR并列表现最好，MI次之。

# 5.2方法选择建议

综合模拟与实证研究结果，本研究建议首选 EM或FIML方法。各方法中，EM在各个指标上均表现较好，是最推荐的方法。但EM需要先插补后估计，而FIML无需插补便可估计，且FIML得到的PCCR也较高，尽管FIML 在估计题目参数时表现不如其它基于模型的方法，但仅是相对而言，其Bias 绝对值和RMSE也均较小，且与同条件下EM的表现差异很小。因此，若出于一步到位的处理角度来看，可以优先考虑使用FIML进行缺失数据处理。同时，在缺失机制为MAR或者MCAR，以及测验长度较短情况下，研究者应避免使用ZR法处理缺失值。

# 5.3研究局限及展望

本研究将目前表现效果更好的基于模型的缺失数据处理方法引入CDA中，对不同的缺失数据处理方法进行全面比较，并提出了实践中处理缺失数据的建议。但仍有一些局限，如本研究仅关注了0-1计分测验形式，未考虑多级计分情况，而多级计分在现实中也很常见，且能提供更加丰富的作答信息。未来研究可以在多级计分测验中，探究不同缺失数据处理方式对估计结果的影响。其次，近年来纵向CDA受到了研究者们的关注(Zhang&Wang,2018;Kaya&Leita,2017)，且纵向CDA中也存在数据缺失问题，因此，如何处理纵向CDA中的缺失数据值得进一步探究。此外，本研究使用了经验交叉相乘法计算实证数据的题目参数标准误。但一些研究指出在估计题目参数标准误时，观察信息矩阵及三明治信息矩阵也是常用且有效的方法（刘彦楼等,2016;Liuetal.,2019）。因此，在后续研究中可以在缺失值领域进一步对比三种信息矩阵的表现，选取更适合的方法计算标准误。最后，本研究虽然对三种缺失机制分别进行了分析，但实际测验中数据的缺失机制往往不明确，未来研究可以进一步结合包含缺失机制判定的CDM(Shan&Wang,2020)，研究实际测验情境下的缺失数据处理模型。

# 参考文献

Akaike,H.(1974).A new look at the statistical model identification.IEEE transactionsonautomatic control, 19(6),716-723.   
Aryadoust,V.,& Goh,C.C. (2001).Exploring the relative merits of cognitive diagnostic models and confirmatory factor analysis for assessing listening. Exploring Language Frameworks,405.   
Bai,S. (2020).Developing a learning progression for probability based on the GDINA model in China.Frontiers in Psychology,11,2561.   
Brown,N.J.S., Svetina,D.,& Dai,S.(2O14).Impactof methods of scoring omited responses onachievement gaps. In annual meeting of the National Council on Measurement in Education, Philadelphia, PA.   
Chen,L., Savalei, V.,& Rhemtulla, M. (2020).Two-stage maximum likelihood approach for item-level missing data in regression. Behavior research methods,52,2306-2323.   
Dai,S.(20l7). Investigation of missing responses in implementation of cognitive diagnostic models (doctorial dissertation). Indiana University.   
De Ayala,R.J.,Plake,B.S.,& Impara,J. C. (2oo1).The impact of omited responses on the accuracyof ability estimation in item response theory.Journal of educational measurement, 38(3),213-234.   
De la Torre,J. (2009). DINA model and parameter estimation: A didactic.Journal of Educational and Behaviral Statistics,34,115-130.   
De La Torre,J. (2011).The generalized DINA model framework. Psychometrika,76(2),179-199.   
Dempster,A.P.,Laird,N.M.,& Rubin,D.B.(1977).Maximum likelihood from incomplete data via the EM algorithm. Journal of the Royal Statistical Society: Series B (Methodological),39(1),1-22.   
Dong,Y.,& Peng, C.Y.J.(20l3).Principled mising data methods for researchers. SpringerPlus,2(1),1-17.   
Eekhout, I., Enders, C. K.,Twisk, J.W. de Boer, M.R.,de Vet, H. C.,& Heymans,M.W. (2015).Analyzing incomplete item scores in longitudinal data by including item score information as auxiliary variables. Structural Equation Modeling: A Multidisciplinary Journal, 22(4),588-602.   
Enders,C. K. (2010). Applied missing data analysis. Guilford press   
Finch,H. (20o8). Estimation of item response theory parameters in the presence of missing data. Journal of Educational Measurement, 45(3),25-245.   
Gao, X.,Wang,D., Cai, Y.,& Tu,D. (2018). Comparison of CDM and its selection: A saturated model, a simple model or a mixed method. Journal of Psychological Science, 41(03),727-734.   
[高旭亮,汪大勋,蔡艳,涂冬波.(2018).认知诊断模型的比较及其应用研究:饱和模型、简化模型还是混合方 法.心理科学,41(03),727-734.]   
Graham,J. W. (2o09). Missing data analysis: Making it work in the real world. Annual review of psychology, 60, 549-576.   
Graham, J. W. Olchowski, A. E.，& Gilreath, T. D. (2007). How many imputations are really needed? Some practical clarififications of multiple imputation theory. Prevention Science, 8(3), 206-213.   
Guo L.,& Zhou W. (2021). Nonparametric methods for cognitive diagnosis to multiple-choice test items. Acta Psychologica Sinica, 53(9),1032-1043.   
[郭磊,周文杰.(2021).基于选项层面的认知诊断非参数方法.心理学报,53(9),1032-1043.]   
Huisman M.,Molenaar I.W. (2001) Imputation of Missng Scale Data with Item Response Models. In: A. Boomsma, M.A. J.van Duijn,T.A. B. Snijders (Eds.), Essays on Item Response Theory.   
Jelicic,H.,Phelps,E.,& Lerner,R.M. (2010). Why missing data mater in the longitudinal study of adolescent development: Using the 4-H Study to understand the uses of different missing data methods. Journal of youth and adolescence, 39(7), 816-835.   
Junker,B.W.,& Sijtsma, K. (0o1).Cognitive assessment models with few assumptions,and connections with nonparametric item response theory. Applied Psychological Measurement, 25(3),258-272.

Kaya,Y.,&Leite,W.L.(2017).Assessing change in latent skils across time with longitudinal cognitive diagnosis modeling: An evaluation of model performance.Educational and psychological measurement, 77(3), 369-388.

Leacy,F.P.,Floyd,S., Yates,T.A.,& White,I.R.(2017).Analysesof sensitivity to the missing-at-random assumption using multiple imputation with delta adjustment: application to a tuberculosis/HIV prevalence survey with incomplete HIV-status data.American journal of epidemiology, 185(4),304-315.   
Lee,Y.S.,Park,Y.S.,&Taylan,D.(2Ol1).A cognitive diagnostic modeling of atribute masteryinMassachusets, Minnesota, and the US national sample using the TIMSS 20o7. International Journal of Testing, 11(2), 144-177.   
Liu,Y., Tian, W.,& Xin, T.. (2016). An application of $\mathrm { m } 2$ statistic to evaluate the fit of cognitive diagnostic models. Journal of Educational and Behavioral Statistics,41(1), 3-26.   
Liu,Y.,Xin,T.,& Jiang, Y. (2O21,June). Structural parameter standard eror estimation method in diagnostic classification models: Estimation and application.multivariate behavioral research,1-20.   
Liu,Y., Xin,T.，Andersson,B.，& Tian,W. (2019). Information matrix estimation procedures for cognitive diagnostic models. British Journal of Mathematical and Statistical Psychology, 72,18-37.   
Liu,Y., Xin,T.,Li,L.,Tian, W.,&Liu, X. (2o16) Improved method for diferential item functioning detectionin cognitive diagnosis models: an application of Wald statistic based on observed information matrix. Acta Psychologica Sinica, 48, 588-598.   
[刘彦楼,辛涛,李令青,田伟,刘笑笑.(2016).改进的认知诊断模型项目功能差异检验方法—一基于观察信息 矩阵的Wald 统计量.心理学报,48,588-598.]   
Ma,W.,& C.，& de la Torre,J. (2016).Model similarity,model selection,and attribute clasification.Applied Psychological Measurement, 40(3),200-217.   
Ma, W.,& de la Torre, J. (2020). GDINA: An R package for cognitive diagnosis modeling. Journal of Statistical Software, 93(14),1-26.   
Ma,W.,&de la Torre,J. (2o16).Asequential cognitive diagnosis model for polytomous responses.British Journal ofMathematical and Statistical Psychology, 69(3),253-275.   
Mazza, G.L.,Enders, C.K.,& Ruehlman,L. S.. (2015). Addressing item-level missing data: acomparison of proration and fullinformation maximum likelihood estimation. Multivariate Behavioral Research, 50(5), 504-519.   
Marshall,A.,Altman,D.G.,Royston,P.,& Holder,R.L. (2010). Comparisonof techniques for handling missing covariate data within prognostic modelling studies: a simulation study. BMC medical research methodology, 10(1),1-16.   
Najera,P., Abad,F. J.，& Sorrel, M. A. (2021). Determining the number of atributes in cognitive diagnosis modeling. Frontiers in psychology,12,321.   
Newman, D.A. (20o3). Longitudinal modeling with randomly and systematically missing data: A simulation of ad hoc, maximum likelihood,and multiple imputation techniques. Organizational research methods, 6(3), 328-362.   
Pan, Y.,& Zhan, P. (2020). The Impact of Sample Atrition on Longitudinal Learning Diagnosis: A Prolog. Frontiers in psychology,11,1051.   
Rasmussen, K. (2007). Encyclopedia ofmeasurement and statistics 1. Sage.   
Rezvan,P.H.,Lee, K.J.,& Simpson, J.A. (2015).The rise of multiple imputation: areview of the reporting and implementation of the method in medical research. BMC medical research methodology,15(1),1-14.   
Rotnitzky，A. (2oo8). Inverse probability weighted methods.In Longitudinal data analysis (pp. 467-490). Chapman and Hall/CRC.   
Rubin,D.B. (1976). Inference and missing data. Biometrika,63(3),581-592.   
Schafer,J.L.,& Graham,J. W.(20o2).Missing data: our view of the stateof the art.Psychological methods,7(2), 147.   
Schwarz, G. (1978). Estimating the Dimension ofa Model. The Annals of Statistics, 6(2), 461-464.   
Shan,N.,& Wang, X. (2020). Cognitive diagnosis modeling incorporating item-level missing data mechanism. Frontiers in psychology,11,3231.   
Van Buuren, S. (2018). Flexible imputation of missing data. CRC press.   
Van Buuren, S.,& Groothuis-Oudshoorm, K. (2011). mice: Multivariate Imputation by Chained Equations in R. Journal of Statistical Software, 45(3),1-67.   
Wothke,W. (2ooo).Longitudinal and multigroup modeling with mising data. In Modeling longitudinal and multilevel data (pp.205-224). Psychology Press.   
Xiao, J.,& Bulut, O.(2O20).Evaluating the performances of missing data handling methods in ability estimation from sparse data. Educational and Psychological Measurement, 80(5), 932-954.   
Xu, X.,& von Davier,M. (2oo6). Cognitive diagnosis for NAEP proficiency data.ETS Research Report Series, 2006(1), i-25.   
Xu,X.,delaTorre,J.,Zhang,J.,Guo,J.,& Shi,N. (2020).Estimating CDMsusing the slice-within-gibbs sampler Frontiers in psychology,11,2260.   
Ye,S.J.,Tang,W. Q., Zhang,M.Q.,& Cao,M.C. (2004). Techniques for mising data in longitudinal studies and its application.Advances in Psychological Science,22(12),1985-1994.   
[叶素静,唐文清,张敏强,曹魏聪.(2014).追踪研究中缺失数据处理方法及应用现状分析.心理科学进展, 22(12), 1985-1994.]   
Zhang,S.,& Wang,S.(2018). Modeling learner heterogeneity: A mixture learning model with responses and response times.Frontiers in psychology, 9,2339.   
Comparison of missing data handling methods in cognitive diagnosis: zero   
replacement, multiple imputation and maximum likelihood estimation   
SONG Zhilin1， GUO Lei1,2， ZHENG Tianpeng3   
(1 Faculty of Psychology, Southwest University, Chongqing 400715, China)   
(2 Southwest University Branch, Collaborative Innovation Center of Assessment toward Basic   
Education Quality, Chongqing 400715, China)   
(3 Collaborative Innovation Center of Assessment toward Basic Education Quality at   
Beijing Normal University, Beijing 100088, China)

# Abstract

The problem of missing data is common in research,and there is no exception for cognitive diagnostic assessment (CDA). Some studies have revealed that both the presence of missing values and the selection of different missing data processing methods would affect the results of CDA.Therefore,it is necessary to attach more attntion to the problem in CDA and choose appropriate methods to deal with it. Although the problem in CDA has been explored before, previous studies did not consider multiple imputation (MI) and full information maximum likelihood (FIML)，which are widely used in the field of missng data analysis. Moreover, previous studies neglected the comparison using empirical data and saturation models such as GDINA model. In summary, the main purpose of this study are to introduce MI and FIML into CDA, thus making a comprehensive comparison of different missng data handling methods, and further putting forward suggestions for handling missing data in practice.

Simulation study considered six factors: (1） Sample size: 200 participants, 400 participants, and 1000 participants; (2) Test length: 15 test items and 30 test items; (3) Quality of items: high quality, medium quality, and low quality; (4) Missing data mechanisms: missing completely at random (MCAR), missing at random (MAR), and missing not at random (MNAR); (5) Missing rate: $10 \%$ ， $20 \%$ ,and $30 \%$ ; (6) Missing data handling methods: zero replacement (ZR), MI-CART, MI-PMM，MI-LOGREG.BOOT,Expectation-Maximization algorithm (EM)， and FIML. The GDINA model was used, and the analysis process was realized by the GDINA package in R software. Secondly, the PISA 2015 computer-based mathematics data were applied to compare the practical value of the proposed methods.

The results of simulation study revealed that: (1） Missing data results in a decrease in estimation accuracy.The absolute value of Bias and RMSE both increased and PCCR values of all methods decreased as the sample size,test length and the quality of the items decreased and the mising rate increased; (2) When estimating item parameters, EM performed best, followed by M1. Meanwhile,FIML and ZR methods were unstable; (3) When estimating the KS of participants, EM and FIML performed best as the missing data mechanism was MAR or MCAR. When the missing data mechanism was MNAR, EM, FIML and ZR performed best. The empirical study results further supported the simulation research results. It showed that: (1） For all empirical indicators,EM, FIML,and MI-PMM perform best on one or more indicators; (2) The results obtained under the empirical study and simulation study under the MNAR mechanism are very similar; (3) EM performs well on all indicators,and ZR and FIML methods are slightly worse than EM, followed by MI-PMM, LOGREG.BOOT and MI-CART.

In addition, based on the research results,the following suggestions were provided: (1) EM and FIML should be the first choice.However, if researchers do not want to get the complete data set, FIML could be used as a priority for missing data handling; (2) When the missing data mechanism was MAR or MCAR and the test length was not enough, researchers should avoid using the ZR method to deal with missing data. Finally,this paper ends with the prospects of future researches: (1) The multilevel scoring situation should also be studied; (2) The effectiveness of these methods should be tested in longitudinal research; (3) The performance of more methods of information matrix can be further compared in calculating the standard error to handle missing data; (4) Future research could focus on the missing mechanisms of data onto the real data. Keywords cognitive diagnosis, GDINA model, missing data, multiple imputation, maximum likelihood estimation

# 附录一模拟研究Q矩阵

表1模拟研究Q矩阵（5属性15题目条件）  

<html><body><table><tr><td>属</td><td colspan="13">题目</td></tr><tr><td>性</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td></tr><tr><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td></tr><tr><td>2</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>3</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td></tr><tr><td>4</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>5</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td></tr></table></body></html>

表2模拟研究Q矩阵（5属性30题目条件）  

<html><body><table><tr><td>属</td><td colspan="10">题目</td><td colspan="7"></td></tr><tr><td>性</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td></td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td>13</td><td>14</td><td></td><td>15</td></tr><tr><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td></td><td></td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td></td><td>1</td><td>1</td><td>0</td></tr><tr><td>2</td><td>0</td><td>1</td><td>0</td><td>0</td><td></td><td></td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td></td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>3</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td></td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td></td><td>1</td><td>0</td><td>0</td><td>1</td></tr><tr><td>4</td><td>0</td><td>0</td><td>0</td><td>1</td><td></td><td></td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td></td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>5</td><td>0</td><td>0</td><td>0</td><td>0</td><td></td><td></td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td></td><td>0</td><td>1</td><td>1</td><td>0</td></tr><tr><td>属</td><td colspan="14">题目</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>性</td><td>16</td><td>17</td><td>18</td><td>19</td><td></td><td>20</td><td>21</td><td>22</td><td>23</td><td>24</td><td>25</td><td>26</td><td></td><td>27</td><td>28</td><td>29</td><td>30</td></tr><tr><td>1</td><td>0</td><td></td><td>0</td><td>0</td><td></td><td>0</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td><td></td><td></td><td>0</td><td>0</td></tr><tr><td>2</td><td>1</td><td>1</td><td>0</td><td>0</td><td></td><td></td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td></td><td>1</td><td>0 1</td><td>1</td><td>0</td></tr><tr><td>3</td><td>0</td><td>0</td><td>1</td><td>1</td><td></td><td></td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td></td><td>1</td><td>1</td><td>0</td><td>1</td></tr><tr><td>4</td><td>1</td><td>0</td><td>1</td><td>0</td><td></td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td></td><td>1</td><td>0</td><td>1</td><td>1</td></tr><tr><td>5</td><td>0</td><td>1</td><td>0</td><td>1</td><td></td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>1</td><td></td><td>0</td><td>1</td><td>1</td><td>1</td></tr></table></body></html>

# 附录二生成缺失数据的具体步骤

MCAR机制的数据与其他因素均无关。首先，将该条件下的总缺失率（如0.1，0.2或0.3）设为每个被试在每道题目上的目标缺失率。然后，对每个被试的每一个作答，都会生成一个服从均匀分布 $U$ （0,1）的值，并将其与被试的目标缺失率进行比较。若这一数值小于等于目标缺失率，将当前作答替换为缺失，反之则保留原始作答结果。

MAR 机制下缺失数据与已观测到的变量有关，而与产生缺失的变量本身无关。首先，为每个被试生成一个服从标准正态分布N（0,1）的代理变量，这个变量在现实情景中可能是能力、年龄、学习程度等，是对缺失可能性造成影响的个体变量。一般情况下被试的代理变量值越大，在某道题目上的目标缺失率就越低。其次，根据生成的代理变量将被试划分为六个分数段，为每个分数段的被试分配相应的目标缺失率，保证代理变量得分越大，目标缺失率越小。且使所有目标缺失率的平均值等于该条件的总缺失率（即0.1、0.2或0.3）。对每个被试的每一个作答，再生成一个服从均匀分布 $U$ （0,1）的值，并将其与被试的目标缺失率进行比较。若其小于目标缺失率，将当前作答替换为缺失，反之不进行处理，保留原始作答结果。

MNAR机制下缺失数据与缺失前被试是否能正确作答该题目有关，而与其他条件无关。在完整数据基础上，为每个作答分配目标缺失率，原始数据中的错误作答有更高的目标缺失率，正确作答的被试则有更低的目标缺失率。并使所有题目的目标缺失率的均值等于该条件下的总缺失率（即0.1、0.2或0.3）。例如，以一个包含十位被试的数据集为例，如果在完整数据中有五位被试对目标题目作答正确，五位被试作答错误，该条件下缺失率为0.15，我们向五位作答错误的被试分配0.10的缺失率，向五位作答正确的被试分配0.20的缺失率。对于每一个被试的每一个作答，都会生成一个服从均匀分布U（0,1）的值，并将其与被试的作答缺失率进行比较。若均值小于缺失率，将当前作答替换为缺失，反之不进行处理，保留原始作答结果。

![](images/38765826bbd092f40219ba8008b4b1c3ad36087acf123f61c388c18ebd4bbcd6.jpg)  
附录三五属性条件下MCAR机制的结果  
图1不同处理方法下题目参数的Bias（MCAR机制）

![](images/7729739ef6495a1304b588ddfb35288641c818e9942719dc30d6984c9f4d50ff.jpg)  
图2不同处理方法下题目参数的RMSE（MCAR机制）

![](images/76edf83061575e18bc2eb3018f38753cd72d0df33c181f049c7fe898c018ce19.jpg)  
图3不同处理方法下题目参数的PCCR（MCAR机制）

# 附录四实证研究Q矩阵

表3实证研究Q矩阵  

<html><body><table><tr><td>属</td><td colspan="10">题目</td></tr><tr><td>性</td><td>CM033Q01</td><td>CM474Q01</td><td>CM155Q01</td><td>CM155Q04</td><td>CM411Q01</td><td>CM411Q02</td><td>CM803Q01</td><td>CM442Q02</td><td>CM034Q01</td></tr><tr><td>α1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>α2</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>α3</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>α4</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td></tr></table></body></html>