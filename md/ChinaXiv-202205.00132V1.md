# 带有超长方体约束的少数类样本生成机制

贺作伟1，陶佳晴1，冷强奎²，翟军昌1，孟祥福²(1.渤海大学 信息科学与技术学院，辽宁 锦州 121013;2.辽宁工程技术大学 电子与信息工程学院，辽宁 葫芦岛125105)

摘要：合成少数类过采样技术(SMOTE)是解决类不平衡问题的有效方法之一。但是，SMOTE 的线性插值机制将合成样本限制在原始样本的连线上，导致新样本缺乏多样性，并且这条连线穿过多数类区域时可能会生成噪声样本。针对上述问题，提出一种带有超长方体约束的少数类样本生成机制。该机制使用超长方体作为新样本的生成区域来代替线性插值，以增加合成样本与原始样本的差异性。并通过检测超长方体内是否存在多数类样本来决定是否修正此超长方体，从而防止新合成样本落入多数类区域内。使用所提机制替换线性插值，并集成在三种过采样方法SMOTE、Borderline-SMOTE 和ADASYN中，然后在KEEL的11个标准数据集上进行了实验评估。结果表明，相比于原始方法，集成后的方法能够帮助分类器取得更高的F1值和相当的G-mean。这说明超长方体生成机制能够显著改善分类器对少数类样本的识别能力，并且能够兼顾到多数类样本。

关键词：不平衡分类；过采样技术；SMOTE；生成机制；超长方体约束 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.03.0099

Generation mechanism for minority samples with hypercuboid constraints

He Zuowei1, Tao Jiaqingl,Leng Qiangkui2†, Zhai Junchang1, Meng Xiangfu² (1.CollegeofnformationScience&TchnologyBohaiUniversityJinzhouLiaoningl3,China;2.hoolofEctroi &Information Engineering,Liaoning Technical University,Huludao Liaoning 125105,China)

Abstract: Synthetic minority oversampling technology(SMOTE) isone of the effective methods to solve the classimbalanced problem.However,the linear interpolation mechanism of SMOTErestricts the synthesized samples to the conecting lineoftheoriginalsamples,resulting inalackof diversityfornew samples,and maygenerate noisysamples when this linepasses through the majorityclassregion.Inresponse totheabove isues,this paper proposedageneration mechanism for minority samples with hypercuboid constraints.This mechanism constructed a hypercuboid as the generation region of new samples insteadoflinearinterpolation,therebyincreasingthe variabilitybetweenthesynthesizedsamplesandtheoriginal samples.Then,it detected whether there were majority samples in the hypercuboid todetermine whether to adjust the hypercuboid,which aimed at preventing the new samples into the region of the majority clas.This paper integrated the proposed mechanism into three oversampling methods,i.e.,SMOTE,Borderline-SMOTE,and ADASYN,byusing it to replace linear interpolation,andthen experimentallevaluatedthe integrated methods on11benchmarkdatasets from KEEL. Theresults showedthatcompared totheoriginal methods,the integrated methods could helptheclasifier toobtain higher Fl and omparable G-mean.It verifies thatthe hypercuboid generation mechanism can significantly improve the classifier's ability to recognize minority samples,and meanwhile the majority samples are also taken into account.

Key Words: imbalanced clasification; oversampling technique; SMOTE; generation mechanism; hypercuboid constraints

# 0 引言

针对不平衡数据的分类问题是机器学习与数据挖掘领域面临的一项挑战[1,2]。在二分类问题中，数据不平衡意味着少数类样本的数量远远小于多数类样本的数量[3,4]。这种类间不平衡会引起标准分类器的偏斜，即分类面更容易被推向少数类样本，导致部分少数类样本不能被正确识别[5]。然而，在一些重要的应用领域中，如医学诊断[6]、软件缺陷预测[]、恶性肿瘤分级[8]等，少数类通常包含更关键的信息[9]。因此，如何提高针对少数类样本的分类性能是不平衡学习中的关键问题

目前，处理数据不平衡问题的方法可以分为两类[10]：算法层面方法和数据层面方法。算法层面方法通过修改分类器来强调其对少数类样本的重视[11,12]。数据层面方法在分类器介入之前先对输入样本进行预处理，以减少数据不平衡的影响[13,14]。数据层面方法主要包括欠采样技术和过采样技术。欠采样技术通过移除部分多数类样本来实现平衡，但是可能丢失重要的分布信息[15,16]。而过采样通过增加少数类样本使数据集达到平衡，其中最经典的方法是Chawla 等[17提出的合成少数类过采样技术(Synthetic MinorityOversamplingTEchnique，SMOTE)。SMOTE通过在原始的少数类样本之间进行线性插值[18来生成新的少数类样本，能够提高分类器在测试集上的泛化能力。

近年来，许多SMOTE类的方法被相继提出。这些方法或关注类间不平衡问题或致力于改善类内不平衡问题[19]。对于类间不平衡问题，Han 等[20]认为位于类边界的少数类样本更容易被误分类，并提出一种只针对边界少数类样本进行合成过采样的Borderline-SMOTE方法。He 等[21]提出一种自适应合成少数类过采样技术ADASYN，该技术根据近邻中多数类样本所占比例来决定少数类样本的合成权重。但无论是Borderline-SMOTE还是ADASYN，它们受近邻参数 $K$ 的影响很大，当 $K$ 取不同的值时，新合成样本的分布具有明显的差异。严等[22]提出基于构造性覆盖算法的过采样技术CMOTE，该技术根据覆盖密度进行根样本的选择。但对于两个阈值参数 $P$ 和 $D$ 的设定，一直是需要探讨的问题。王等[23]提出的AdaNSMOTE根据精度下降来自适应地决定少数类的近邻值，并根据噪声等其他因素调整近邻大小。该方法合成的新样本能够保留少数类样本明显的聚类特征，并可以有效避免噪声、小分离和复杂形状的影响。李等[24]通过融合支持度 SD和影响因素posFac 来指导边界样本的合成，它不仅可以避免SMOTE方法选择样本的盲目性，而且能够综合考虑总体样本的分布情况。但SDRSMOTE算法仍需要进一步优化，以提高其运行效率。

对于类内不平衡问题(指少数类样本呈多聚簇分布[25])，盛等[26]使用Box-Cox变换和 $\sigma$ 准则改进了密度峰值聚类，并将其与SMOTE算法相结合。该方法能够有效剔除各类噪声数据，且获得的聚簇不受空间形状限制，避免了手动输入参数带来的主观因素干扰。Bunkhumpornpat等[27]将少数类划分为多个任意形状的子聚簇，然后在随机选择的少数类样本与子聚簇中心之间合成新样本。然而，该方法容易导致类间数据发生重叠，且不能有效标识具有较高过采样权重的边界样本。Nekooeimehr等[28]提出了一种自适应半/无监督加权过采样方法A-SUMO。在使用层次聚类算法后，它自适应确定每个子聚簇的过采样大小。此外，A-SUMO在标识边界样本方面也取得了较好的效果。但也要指出，该方法在聚类时仅考虑距离因素，忽略了样本分布信息，导致抗噪声干扰能力较弱。Douzas 等[29]提出了一种基于 $K \cdot$ -Means和SMOTE的启发式过采样方法。它根据每个聚簇的大小和密度来估计采样权重。然而， $K$ -Means聚类算法无法找到任何不规则的聚簇。并且该方法也未提供可行的策略来确定最佳聚簇数。Tao等[30]使用密度峰值聚类算法来改进 $K$ -Means 算法在处理类内不平衡问题上的不足。根据欧式距离和密度分布，少数类样本的合成权重被自适应地计算，边界和低密度样本将获得更高的采样机会。尽管该方法能够有效避免噪声数据的合成，但安全距离阈值的设定依赖于一个待调参数y，它的合理取值区间目前只能通过实验来获得。

实际上，每一个SMOTE类的方法均可被分解为两个机制：数据选择机制和数据生成机制。而上述这些方法均是对数据选择机制的改进，它们在生成新样本时采用与SMOTE相同的线性插值。然而，这种线性插值方式限制了合成样本的数据质量，同时它也是一些过采样方法不能克服类内不平衡问题的主要原因[31]。文献[32]也指出，合成的新样本应该具备扩展少数类区域的能力，以强调少数类在数据总体分布中的重要性。特别地，当少数类样本为多聚簇分布时，线性插值会在聚簇之间执行合成操作，这将导致新样本落入多数类区域而形成噪声，并进一步加重两类数据之间的重叠[3]。

为了解决线性插值生成机制存在的问题，并使新样本更具随机性和多样性，本文提出一种带有超长方体约束的数据生成机制(简称超长方体生成机制)。该机制首先以少数类根样本及其选定近邻的连线为对角线，构造一个超长方体，新样本将在此超长方体内生成。但在生成之前，需要检测此超长方体内是否存在多数类样本，若存在，则修正此超长方体。最后，在没有多数类样本的安全区域内生成新的少数类样本。

超长方体生成机制是一个独立模块，能够替换线性插值，并可被集成在多数SMOTE类的方法中。接下来，本文将首先解释本文提出的超长方体生成机制，然后将其嵌入到SMOTE、Borderline-SMOTE和ADASYN三种过采样方法中，并与原始方法进行实验对比，以评估该机制的有效性。

# 1 超长方体数据生成机制

# 1.1 SMOTE和线性插值

SMOTE以迭代搜索方式[34]依次从少数类中选择一个样本作为根样本，并计算根样本到其他少数类样本之间的欧式距离，得到距离根样本最近的 $k$ 个少数类近邻。然后，在根样本和其随机选择的一个近邻之间，使用线性插值合成新的少数类样本。

给定 $d$ 维欧式空间 $R ^ { d }$ 中的少数类样本集 $\scriptstyle { \boldsymbol { X } }$ ，假设 $\pmb { x } _ { i } \in { \pmb X }$ 是当前选定的根样本，在 $k = 5$ 时，得到 $\mathbf { x } _ { i }$ 的近邻集合$S = \{ \boldsymbol { x } _ { n n 1 } , \boldsymbol { x } _ { n n 2 } , \boldsymbol { x } _ { n n 3 } , \boldsymbol { x } _ { n n 4 } , \boldsymbol { x } _ { n n 5 } \}$ 。根据 SMOTE 的线性插值原理，如果 $\boldsymbol { x } _ { n n 2 }$ 被随机选中(图1(a))，则新样本 $\mathbf { x } _ { s y n 1 }$ 将被合成在 $\pmb { x } _ { i }$ 和$\pmb { x } _ { n n 2 }$ 的连线上，即：

$$
{ \pmb x } _ { s y n 1 } = { \pmb x } _ { i } + \varepsilon \big ( { \pmb x } _ { n n 2 } - { \pmb x } _ { i } \big )
$$

其中， $\boldsymbol { \varepsilon }$ 是一个 $( 0 , 1 )$ 之间的随机数。直观来看， $\mathbf { x } _ { s y n 1 }$ 被限制在一条线段上，文献[31]也指出这种线性插值将影响合成新样本的质量。另外，如果选定的近邻样本为 $\mathbf { x } _ { n n 5 }$ (图1(b))，则 $\pmb { x } _ { i }$ 与 $\displaystyle \boldsymbol { x } _ { n n 5 }$ 的连线将穿过多数类区域，新样本 $\scriptstyle \mathbf { x } _ { s y n 2 }$ 将在多数类样本之间合成，从而导致噪声的产生。

![](images/1f837528e367cb2b8d1217d8ba40bf4f95f8c687e9ffb3cacbd701dc3f791aba.jpg)  
图1SMOTE生成新样本示意图  
Fig.1Illustration of generating new samples by SMOTE

# 1.2超长方体内生成

为了解决上述线性插值存在的问题，本文提出超长方体生成机制来扩展少数类样本的分布范围。给定 $R ^ { d }$ 中的少数类根样本 $\pmb { x } _ { i } \in { \pmb X }$ ，如果它的近邻 $\textstyle | x _ { n n 2 } $ 被随机选中(图2(a))，则新样本 $\textbf { \em x } _ { s y n 3 }$ 将在 $\pmb { x } _ { i }$ 和 $\textstyle | x _ { n n 2 } $ 确定的超长方体内合成，即：

$$
\pmb { x } _ { s y n 3 } = \pmb { x } _ { i } + \pmb { A } \times \left( \pmb { x } _ { n n 2 } - \pmb { x } _ { i } \right)
$$

其中， $A = \mathrm { d i a g } \left\{ \alpha _ { 1 } , \alpha _ { 2 } , . . . , \alpha _ { d } \right\}$ 是 $d$ 阶对角矩阵， $\alpha _ { i } ( i { = } 1 , 2 , . . . , d )$ 是一个 $( 0 , 1 )$ 之间的随机数。如果本文将少数类样本按维度展开，则 $\pmb { x } _ { i } = \left\{ \pmb { x } _ { i } ^ { 1 } , \pmb { x } _ { i } ^ { 2 } , . . . , \pmb { x } _ { i } ^ { d } \right\} ^ { T }$ ， $\pmb { x } _ { n n 2 } = \{ \pmb { x } _ { n n 2 } ^ { 1 } , \pmb { x } _ { n n 2 } ^ { 2 } , . . . , \pmb { x } _ { n n 2 } ^ { d } \} ^ { T }$ ， $\textbf { \em x } _ { s y n 3 }$ 将被表示为

$$
\pmb { x } _ { s y n 3 } = \left\{ \begin{array} { l } { \left( \pmb { x } _ { i } ^ { 1 } - \alpha _ { 1 } \left( \pmb { x } _ { n n 2 } ^ { 1 } - \pmb { x } _ { i } ^ { 1 } \right) \right) } \\ { \left( \pmb { x } _ { i } ^ { 2 } - \alpha _ { 2 } \left( \pmb { x } _ { n n 2 } ^ { 2 } - \pmb { x } _ { i } ^ { 2 } \right) \right) } \\ { \qquad \ \vdots } \\ { \left( \pmb { x } _ { i } ^ { d } - \alpha _ { d } \left( \pmb { x } _ { n n 2 } ^ { d } - \pmb { x } _ { i } ^ { d } \right) \right) } \end{array} \right\}
$$

通过式(3)可以看出，对比于线性插值，在超长方体内生成将增加新样本的随机性和分布范围。但值得注意的是， ${ \pmb x } _ { s y n 3 }$ 还是存在一定可能被合成在 $\pmb { x } _ { i }$ 和 $\textstyle | x _ { n n 2 } $ 的连线上，这时超长方体生成机制就退化为线性插值。

这种退化概率是可以被估计的，假设 $\alpha _ { i }$ 包含 $\boldsymbol { r }$ 位小数，则合成样本位于 $\pmb { x } _ { i }$ 和 $\textstyle { \mathbf { x } } _ { n n 2 }$ 连线上的概率为

$$
P = \frac { 1 } { \left( 1 0 ^ { r } \right) ^ { d - 1 } }
$$

例如，当 $d = 2$ 且 $r = 2$ 时， $P { = } 0 . 0 1$ ；当 $d = 3$ 且 $r = 2$ 时，$P = 0 . 0 0 0 1$ 。由此可得到，当高维数据被应用时，超长方体生成机制退化为线性插值的概率是非常低的。

# 1.3防止噪声生成策略

如图2(b)所示，当选定的近邻样本为 $\mathbf { \lambda } _ { \pmb { x } _ { n n 5 } }$ 时，由 $\displaystyle \boldsymbol { x } _ { n n 5 }$ 和 $\pmb { x } _ { i }$ 确定的超长方体与多数类区域发生重叠。如果在该超长方体内合成新样本，则这个新样本会落在多数类样本之间而形成噪声。为了避免合成噪声，本文为超长方体生成机制附加了一个检测及修正策略。首先，计算并检测落入该超长方体内的多数类样本，即得到 ${ \pmb y } _ { n n 1 } - { \pmb y } _ { n n 4 }$ 。然后，从 ${ \bf y } _ { n n 1 } - { \bf y } _ { n n 4 }$ 中找到距离 $\pmb { x } _ { i }$ 最近的多数类样本 ${ \bf y } _ { n n 4 }$ 。最后，执行修正策略，将初始由$\boldsymbol { x } _ { n n 5 }$ 和 $\pmb { x } _ { i }$ 确定的超长方体修正为由 $\mathbf { y } _ { n n 4 }$ 和 $\pmb { x } _ { i }$ 确定的新的超长方体，并最终以其作为新样本的生成区域。

下面给出该检测及修正策略的形式化描述。给定多数类样本集 $\pmb { Y } \in \pmb { R } ^ { d }$ ，该策略首先检测 $\mathbf { y } _ { j } \in \pmb { Y }$ 是否位于初始超长方体内。对于 $\mathbf { y } _ { j }$ 的第 $t$ 维，判断依据如式(5)所示。

$$
\mathrm { M i n } \big ( { \pmb x } _ { i } ^ { t } , { \pmb x } _ { n n 5 } ^ { t } \big ) \leq { \pmb y } _ { j } ^ { t } \leq \mathrm { M a x } \big ( { \pmb x } _ { i } ^ { t } , { \pmb x } _ { n n 5 } ^ { t } \big )
$$

如果 $\boldsymbol { y } _ { j }$ 的每一维度均满足式(5)，则表明 $\mathbf { y } _ { j }$ 位于初始超长方体内，此时将 $\mathbf { y } _ { j }$ 放入集合 $_ { T }$ 中。上述检测步骤要遍历 $\textbf {  { Y } }$ 中每一个样本，遍历完成后若 $\pm \infty$ ，则从 $_ { T }$ 中找到距离 $\pmb { x } _ { i }$ 最近的 $\boldsymbol { y } _ { p }$ ：

$$
{ \pmb y } _ { p } = \underset { { \pmb y } _ { j } } { \arg \operatorname* { m i n } } \left\{ \left\| { \pmb y } _ { j } - { \pmb x } _ { i } \right\| , { \pmb y } _ { j } \in { \pmb T } \right\}
$$

然后，使用修正策略依据 $\mathbf { y } _ { p }$ 和 $\pmb { x } _ { i }$ 重新构造超长方体，新样本将在修正后的超长方体内生成。需要说明的是，修正策略只需执行一次即可保证修正后的超长方体中不包含多数类样本。这是因为，如果存在 ${ \bf y } _ { q } \left( { \bf y } _ { q } \in { \cal T } \right.$ 且 $\mathbf { y } _ { q } \neq \mathbf { y } _ { p }$ )落入修正后的超长方体内，则式(7)成立，这显然与式(6)矛盾。

![](images/fd7ca6d59ae3dfd798b03a856e31f8eda52248259c89bfdbeb479b311557f127.jpg)  
图2超长方体机制生成新样本示意图  
Fig.2Ilustration of generating new samples by hypercuboid mechanism

# 1.4算法描述

超长方体生成机制的操作步骤如算法1所示。其中，第4-8步用于检测某个多数类样本 $\mathbf { y } _ { j }$ 是否位于由 $\pmb { x } _ { i }$ 和 $\scriptstyle { \pmb { x } } _ { n n }$ 构造的初始超长方体内。若是，将 $\mathbf { y } _ { j }$ 放入集合 $_ { T }$ 中。第13-15步用于找到 $_ { T }$ (不为空时)中距离 $\pmb { x } _ { i }$ 最近的样本 $\mathbf { y } _ { p }$ 。第16-18步用于合成新的少数类样本。在具体细节上，Y表示集合 $\boldsymbol { \mathbf { \mathit { Y } } }$ 的基数， $\mathit { f l a g } $ 用作 $\boldsymbol { y } _ { j }$ 是否存入 $_ { T }$ 的开关。

该算法的时间复杂度可被估计为 $O ( d | Y | )$ ，要高于线性插值的 $O ( d )$ 。但由于该机制需嵌入到合成过采样算法中，而过采样过程属于数据预处理阶段，是独立于分类器的，因此它不会对分类器的训练时间构成影响。

算法1超长方体数据生成机制输入：少数类根样本 $\boldsymbol { x _ { i } } = \left\{ \boldsymbol { x } _ { i } ^ { 1 } , \boldsymbol { x } _ { i } ^ { 2 } , . . . , \boldsymbol { x } _ { i } ^ { d } \right\}$ ，近邻 $\boldsymbol { x _ { n n } } = \{ x _ { n n } ^ { 1 } , x _ { n n } ^ { 2 } , . . . , x _ { n n } ^ { d } \}$ ，多数类样本集合 $Y$ 。

输出：一个合成的少数类样本 $x _ { s y n }$ 。

a) 初始化 $T = \mathcal { O }$ ;   
b) For $j = 1$ to [Y   
c） $f l a g = 1$ ;   
d) For $t = 1$ to $^ d$ （204号   
e) If $y _ { j } ^ { t } > \mathbf { M a x } \left( x _ { i } ^ { t } , x _ { n n } ^ { t } \right)$ or $y _ { j } ^ { t } < \mathbf { M i n } \big ( x _ { i } ^ { t } , x _ { n n } ^ { t } \big )$ then f) $\hbar a g = 0$ ；goto step i); g) End If   
h) End For   
i) If $f l a g = = 1$ then   
j) T←yj；   
k) End $\tt { I f }$   
1) End For   
m） If $T \neq \emptyset$ then   
n) $y _ { p } = { \underset { y _ { j } } { \operatorname { a r g m i n } } } \left\{ \left\| y _ { j } - x _ { i } \right\| , y _ { j } \in T \right\} ~ ; ~ x _ { n n } = y _ { p } ~ ;$ 0） End If   
p) For $t = 1$ to $^ d$   
q） $\boldsymbol { x } _ { s y n } ^ { t } = \boldsymbol { x } _ { i } ^ { t } + r a n d o m ( 0 , 1 ) ^ { * } \big ( \boldsymbol { x } _ { n n } ^ { t } - \boldsymbol { x } _ { i } ^ { t } \big ) \mathrm { ~ ; ~ }$ （2   
r） End For

需要说明的是，如果本文不把超长方体生成机制当作一个独立模块并用于替代SMOTE类过采样算法中的线性插值，那么算法1中的修正查找过程可以进一步优化。本文可以预先计算得到训练集中任意两个少数类样本所构成超长方体中包含的多数类样本的信息，然后在每次合成新样本时利用此信息。

令 $G ( i , n n )$ 表示由少数类样本 $x _ { i }$ 和 $x _ { n n }$ 所构成超长方体中包含的多数类样本的索引。例如， $G ( 1 , 5 ) = \{ 2 , 3 , 7 , 9 \}$ 表明由 $x _ { 1 }$ 和$x _ { 5 }$ 构成的超长方体中包含多数类样本 $y _ { 2 } , y _ { 3 } , y _ { 7 } , y _ { 9 }$ 。在过采样之前，本文将所有的 ${ \cal G } ( i , n n )$ 均计算出来，那么在合成新样本时就可以直接使用这些信息，这将大大缩短算法的运行时间。值得注意的是， $G ( i , n n ) = G ( n n , i )$ 。

在获得 ${ \cal G } ( i , n n )$ 的基础上，本文没有必要再遍历整个多数类样本集 $Y$ 。相应地，算法1中步骤b)\~1)可以简化为一个步骤，即 $T \gets y _ { j } , j \in G ( i , n n )$ 。此时算法1的输入中需要包含一个新的参数 ${ \cal G } ( i , n n )$ ，算法的时间复杂度将由 $O ( d | Y | )$ 下降到$O ( d | G ( i , n n ) | )$ 。

# 2 实验结果与分析

提出的超长方体生成机制是一个独立模块，可被嵌入到SMOTE类算法中替换线性插值以改善合成数据的质量。本文将所提机制嵌入到SMOTE、Borderline-SMOTE（简称为BLSMOTE)、ADASYN 三个过采样算法中，嵌入后的算法称为HC-SMOTE、HC-BLSMOTE、HC-ADASYN，然后分别通过人工合成数据集实验和标准数据集实验来评估该机制的有效性，

# 2.1人工合成数据集实验

人工合成数据集如图3所示，其中少数类样本用红色星形表示，多数类样本用灰色圆形表示。图3(a)(c)(e)分别表示使用原始的SMOTE、BLSMOTE、ADASYN对少数类样本进行过采样后的结果，新合成样本使用三角形表示；图3(b)(d)(f)分别表示使用HC-SMOTE、HC-BLSMOTE、HC-ADASYN进行过采样的结果，新合成样本使用菱形表示。

从图3可以看出，SMOTE、BLSMOTE、ADASYN使用线性插值方式合成少数类样本，新样本均位于原始少数类样本之间的连线上，呈现出明显的线段分布；嵌入超长方体生成机制后，HC-SMOTE、HC-BLSMOTE、HC-ADASYN合成了分布更为均匀的少数类样本，并且扩展了少数类的分布范围。另外，图3(a)(c)出现了合成样本跨越多数类区域的情况，这些新样本会成为噪声而使得分类器性能下降。但使用本文所提机制中的防止噪声生成策略后，这种情况不再发生，如图3(b)(d)所示。

# 2.2标准数据集实验

为了体现客观性，从KEEL不平衡数据库[35]中选择11个标准数据集进行实验，数据集描述见表1。每一个数据集中均已采用5折交叉验证方式划分为训练集和测试集，实验结果将报告5次实验的平均值。实验参数按默认设置，

SMOTE、BLSMOTE、ADASYN在合成样本时近邻参数分别为5、5、7，BLSMOTE在判定边界样本时近邻参数为7。分类器使用 $C 4 . 5 ^ { [ 3 6 ] }$ 和 AdaBoost[37]。

![](images/7dbbea962bb4de2bd48ed95a2765b2f2d5244c6ae7e30ca3ccaad7314c5dfe2d.jpg)  
图3原始方法(左)与集成后方法(右)的对比 Fig.3Comparison of the original methods (left) with the integrated methods (right)

评价指标包括 $F 1$ 和 $G$ -mean。 $F 1$ 是精准率(Precision)和召回率(Recal)的调和平均，反映分类器对少数类样本的分类能力； $G$ -mean是敏感性(Sensitivity)和特异性(Specificity)的几何平均，反映分类器兼顾两类样本时的分类能力。这些指标均以混淆矩阵(表2)为基础，计算公式为

$$
P r e c i s i o n = \frac { T P } { F P + T P }
$$

$$
R e c a l l = S e n s i t i \nu i t y = \frac { T P } { T P + F N }
$$

$$
S p e c i f i f i c i t y = \frac { T N } { T N + F P }
$$

$$
F 1 = \frac { 2 \times R e c a l l \times P r e c i s i o n } { R e c a l l + P r e c i s i o n }
$$

$$
G - m e a n = \sqrt { S e n s i t i \nu i t y \times S p e c i f i f i c i t y }
$$

Tab.1Description of the datasets   
表2二分类问题的混淆矩阵  

<html><body><table><tr><td>数据集名称</td><td>关键字</td><td>样本个数 维度</td><td>不平衡率</td></tr><tr><td>Wisconsin</td><td>Wi</td><td>683 9</td><td>1.86</td></tr><tr><td>Vehicle2</td><td>Ve2</td><td>846 18</td><td>2.88</td></tr><tr><td>New-thyroid2</td><td>N2</td><td>215 5</td><td>5.14</td></tr><tr><td>Segment0</td><td>S0</td><td>2308 19</td><td>6.02</td></tr><tr><td>Glass6</td><td>G6</td><td>214 9</td><td>6.38</td></tr><tr><td>Yeast3</td><td>Y3</td><td>1484 8</td><td>8.10</td></tr><tr><td>Vowel0</td><td>Vo0</td><td>988 13</td><td>9.98</td></tr><tr><td>Ecoli4</td><td>E4</td><td>336 7</td><td>15.80</td></tr><tr><td>Page-blocks-1-3_vs_4</td><td>P4</td><td>472 10</td><td>15.86</td></tr><tr><td>Shuttle-c2-vs-c4</td><td>S4</td><td>129 9</td><td>20.50</td></tr><tr><td>Yeast5</td><td>Y5</td><td>1484 8</td><td>32.73</td></tr></table></body></html>

表1数据集基本信息  
Tab.2Confusion matrix of the two-class problem   

<html><body><table><tr><td>实际情况</td><td>预测为少数类</td><td>预测为多数类</td></tr><tr><td>实际为少数类</td><td>TP</td><td>FN</td></tr><tr><td>实际为多数类</td><td>FP</td><td>TN</td></tr></table></body></html>

表3给出了HC-SMOTE与原始SMOTE的对比实验结果。C4.5分别在9个数据集上和5个数据集上取得了更高的$F 1$ 和 $G$ -mean，这说明经过HC-SMOTE过采样后，显著提升了C4.5针对少数类样本的识别能力，但在兼顾多数类方面还存在不足；AdaBoost在全部11个数据集上均取得了更高的 $F 1$ ，同时也在8个数据集上获得了更好的 $G$ -mean，这说明HC-SMOTE对AdaBoost产生了积极影响。

表3SMOTE与HC-SMOTE的对比

Tab.3Comparison of SMOTE with HC-SMOTE   

<html><body><table><tr><td rowspan="3">Data</td><td colspan="4">C4.5</td><td colspan="4">AdaBoost</td></tr><tr><td colspan="2">F1</td><td colspan="2">G-mean</td><td colspan="2">F1</td><td colspan="2">G-mean</td></tr><tr><td>SMOTE</td><td>HC-SMOTE</td><td>SMOTE</td><td>HC-SMOTE</td><td>SMOTE</td><td>HC-SMOTE</td><td>SMOTE</td><td>HC-SMOTE</td></tr><tr><td>Wi</td><td>0.9460</td><td>0.9278</td><td>0.9600</td><td>0.9470</td><td>0.9383</td><td>0.9454</td><td>0.9556</td><td>0.9580</td></tr><tr><td>Ve2</td><td>0.9230</td><td>0.9202</td><td>0.9586</td><td>0.9546</td><td>0.9176</td><td>0.9453</td><td>0.9592</td><td>0.9643</td></tr><tr><td>N2</td><td>0.7918</td><td>0.9405</td><td>0.9258</td><td>0.9527</td><td>0.8695</td><td>0.9275</td><td>0.9484</td><td>0.9503</td></tr><tr><td>S0</td><td>0.9730</td><td>0.9804</td><td>0.9878</td><td>0.9929</td><td>0.9792</td><td>0.9818</td><td>0.9952</td><td>0.9919</td></tr><tr><td>G6</td><td>0.7785</td><td>0.7809</td><td>0.8888</td><td>0.8829</td><td>0.7484</td><td>0.8508</td><td>0.8615</td><td>0.9173</td></tr><tr><td>Y3</td><td>0.7482</td><td>0.7723</td><td>0.9033</td><td>0.9209</td><td>0.7125</td><td>0.7732</td><td>0.8677</td><td>0.9027</td></tr><tr><td>Vo0</td><td>0.8988</td><td>0.9166</td><td>0.9786</td><td>0.9600</td><td>0.9068</td><td>0.9307</td><td>0.9747</td><td>0.9770</td></tr><tr><td>E4</td><td>0.7141</td><td>0.7691</td><td>0.9502</td><td>0.8789</td><td>0.7245</td><td>0.7429</td><td>0.9282</td><td>0.8519</td></tr><tr><td>P4</td><td>0.8539</td><td>0.9667</td><td>0.9887</td><td>0.9977</td><td>0.8595</td><td>0.9667</td><td>0.9887</td><td>0.9977</td></tr><tr><td>S4</td><td>0.9600</td><td>1.0000</td><td>0.9958</td><td>1.0000</td><td>0.9000</td><td>1.0000</td><td>0.9826</td><td>1.0000</td></tr><tr><td>Y5</td><td>0.6584</td><td>0.7136</td><td>0.9401</td><td>0.9193</td><td>0.6803</td><td>0.7246</td><td>0.9273</td><td>0.9200</td></tr></table></body></html>

表4给出了HC-BLSMOTE与原始BLSMOTE的对比实验结果。C4.5分别在7个数据集上和9个数据集上取得了更高的 $F 1$ 和 $G$ -mean，AdaBoost在8个数据集上取得了更高的$F 1$ 和 $G$ -mean。由于BLSMOTE在数据选择阶段只对边界少数类样本进行过采样，而本文所提机制与BLSMOTE结合后表现出优异的性能，说明在边界处对少数类样本进行超长方体区域内的合成，能够极大改善新合成样本的质量，并有助于提高分类器的泛化性能。

表5给出了HC-ADASYN与原始ADASYN的对比实验结果。C4.5和AdaBoost分别在11个和10个数据集上取得了更高的F1，但仅在6个和3个数据集上取得了更高的G-mean。ADASYN为每个少数类样本施加一个合成权重，即当邻域内多数类样本越多时该合成权重越大。在嵌入超长方体生成机制后，HC-ADASYN将更关注权重大的少数类样本，但可能导致部分多数类样本被忽视。

图4是上述实验结果的箱线图，红色菱形点表示平均值，绿色虚线表示中位数。SM、BD、AD分别是过采样方法SMOTE、BLSMOTE 和ADASYN的缩写。C45和Ada分别是分类器C4.5和AdaBoost的缩写。从子图4(a)(c)(e)可以看出，改进后的方法在 $F 1$ 上取得了大幅的领先，这说明本文所提机制能够明显提升分类器对少数类的识别。同时，改进后的HC-SMOTE和HC-BLSMOTE在 $G$ -mean的表现上也优于原始方法。整体来看，超长方体生成机制嵌入到Borderline-SMOTE后的性能最好。

表4BLSMOTE与HC-BLSMOTE 的对比

Tab.4Comparison of BLSMOTE with HC-BLSMOTE   

<html><body><table><tr><td rowspan="3">Data</td><td colspan="4">C4.5</td><td colspan="4">AdaBoost</td></tr><tr><td colspan="2">F1</td><td colspan="2">G-mean</td><td colspan="2">F1</td><td colspan="2">G-mean</td></tr><tr><td>BLSMOTE</td><td>HC-BLSMOTE</td><td>BLSMOTE</td><td>HC-BLSMOTE</td><td>BLSMOTE</td><td>HC-BLSMOTE</td><td>BLSMOTE</td><td>HC-BLSMOTE</td></tr><tr><td>Wi</td><td>0.9243</td><td>0.9414</td><td>0.9456</td><td>0.9604</td><td>0.9244</td><td>0.9442</td><td>0.9417</td><td>0.9590</td></tr><tr><td>Ve2</td><td>0.9192</td><td>0.9323</td><td>0.9447</td><td>0.9581</td><td>0.9566</td><td>0.9560</td><td>0.9728</td><td>0.9681</td></tr><tr><td>N2</td><td>0.9119</td><td>0.9273</td><td>0.9353</td><td>0.9501</td><td>0.8894</td><td>0.9581</td><td>0.9396</td><td>0.9798</td></tr><tr><td>S0</td><td>0.9759</td><td>0.9717</td><td>0.9870</td><td>0.9888</td><td>0.9743</td><td>0.9759</td><td>0.9868</td><td>0.9871</td></tr><tr><td>G6</td><td>0.7578</td><td>0.7921</td><td>0.8642</td><td>0.8913</td><td>0.8264</td><td>0.8636</td><td>0.8794</td><td>0.9201</td></tr><tr><td>Y3</td><td>0.7773</td><td>0.7939</td><td>0.9117</td><td>0.9274</td><td>0.7423</td><td>0.7454</td><td>0.8638</td><td>0.8793</td></tr><tr><td>Vo0</td><td>0.9381</td><td>0.8544</td><td>0.9882</td><td>0.9425</td><td>0.9576</td><td>0.8996</td><td>0.9905</td><td>0.9638</td></tr><tr><td>E4</td><td>0.7254</td><td>0.7667</td><td>0.8759</td><td>0.9077</td><td>0.7048</td><td>0.7476</td><td>0.8496</td><td>0.8775</td></tr><tr><td>P4</td><td>0.9227</td><td>0.9667</td><td>0.9943</td><td>0.9977</td><td>0.9227</td><td>0.9667</td><td>0.9943</td><td>0.9977</td></tr><tr><td>S4</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td></tr><tr><td>Y5</td><td>0.7413</td><td>0.7104</td><td>0.9331</td><td>0.9420</td><td>0.7190</td><td>0.7371</td><td>0.8722</td><td>0.9429</td></tr></table></body></html>

表5ADASYN与HC-ADASYN的对比

Tab.5Comparison ofADASYN with HC-ADASYN

![](images/6eb363b193699d26404081860cfb61d2f790eb86bb50addc9133fc3039d7c005.jpg)  
图4标准数据集实验结果的箱线图  
Fig.4Boxplots of experimental results on benchmark datasets

# 3 结束语

本文提出一种新的数据生成机制来改进合成过采样方法，它使用超长方体作为新样本的生成区域来代替线性插值，以增加新合成样本与原始样本的差异性。为防止新样本落入多数类区域内，一个检测及修正策略被附加到该超长方体生成机制中，从而避免了噪声的产生。

在标准数据集上的实验表明，当该机制集成到SMOTE、Borderline-SMOTE、ADASYN三个过采样方法后，两个标准分类器在大部分数据集上均取得了更高的 $F 1$ 值，说明超长方体生成机制能够显著改善分类器对少数类样本的识别能力。在 $G$ -mean评价指标上，集成后的方法表现与原始方法相当，说明其在关注少数类样本的同时，也能够兼顾多数类样本。

本文工作从数据生成机制出发，为不平衡学习中过采样方法的研究提供了一个新的思路。但提出的超长方体生成机制是启发式的，其有效性建立在实验评估的基础之上。下一步工作将在理论层面上深入研究数据生成机制对合成样本质量的影响。

# 参考文献：

[1]Shi Hongbo,Gao Qigang,Ji Suqin,et al.A hybrid sampling method based on safe screening for imbalanced datasets with sparse structure [C]/ 2018 International Joint Conference on Neural Networks (IJCNN) . New York: IEEE Press,2018:1-8   
[2]Li Junnan, Zhu Qingsheng,Wu Quanwang,et al.A novel oversampling technique for class-imbalanced learning based on SMOTE and natural neighbors [J].Information Sciences,2021,565:438-455.   
[3]杨浩，陈红梅．结合样本局部密度的非平衡数据集成分类算法[J]. 计算机科学与探索,2020,14(2):274-284.(Yang Hao,Chen Hongmei. Ensemble classification algorithm for imbalanced data combined with local area density [J].Journal of Frontiers of Computer Science and Technology,2020,14 (2): 274-284.)   
[4]Barua S,Islam M M, Yao X,et al. MWMOTE-majority weighted minority oversampling technique for imbalanced data set learning [J]. IEEE Trans on Knowledge and Data Engineering,2012,26 (2):405-425.   
[5]Zheng Ming,Li Tong, Zheng Xiaoyao,et al. UFFDFR: Undersampling framework with denoising,fuzzy c-means clustering,and representative sample selection for imbalanced data classification [J].Information Sciences,2021,576:658-680.   
[6]Parvin H,Minaei-Bidgoli B,Alizadeh H. Detection of cancer patients using an innovative method for learning at imbalanced datasets [C]// International Conference on Rough Sets and Knowledge Technology. Berlin: Springer Press,2011: 376-381.   
[7]Wang Shuo,Yao Xin.Using class imbalance learning for software defect prediction [J].IEEE Trans on Reliability,2013,62 (2): 434-443.   
[8]Krawczyk B,Galar M,Jelen L,et al. Evolutionary undersampling boosting for imbalanced classification of breast cancer malignancy [J]. Applied Soft Computing,2016,38:714-726.   
[9]徐玲玲，迟冬祥．面向不平衡数据集的机器学习分类策略[J].计算 机工程与应用,2020,56(24):12-27.(Xyu Lingling,Chi Dongxiang. Machine Learning Classification Strategy for Imbalanced Data Sets [J]. Computer Engineering and Applications,2020,56 (24):12-27.)   
[10]He Haibo,GarciaEA.Learning from imbalanced data [J].IEEE Trans on Knowledge and Data Engineering,2009,21 (9):1263-1284.   
[11]Dubey H,Pudi V. Class based weighted k-nearest neighbor over imbalance dataset [Cl// Pacific-Asia Conference on Knowledge Discovery and Data Mining.Berlin: Springer Press,2013:305-316.   
[12]Fan Wei, Stolfo SJ,Zhang Junxin,et al.AdaCost: misclassification cost  
[13] Elreedy D,Atiya AF.A comprehensive analysis of synthetic minority oversampling technique (SMOTE） for handling class imbalance [J]. Information Sciences,2019,505:32-64.   
[14] Zhu Yuanwei, Yan Yuanting,Zhang Yiwen,et al. EHSO: Evolutionary Hybrid Sampling in overlapping scenarios for imbalanced learning [J]. Neurocomputing,2020,417: 333-346.   
[15]Fernandez A,Garcia S,Herrera F,et al.SMOTE for learning from imbalanced data:progress and challenges，marking the 15-year anniversary [J]. Journal of Artificial Intelligence Research,2018,61: 863-905.   
[16]吴艺凡，梁吉业，王俊红．基于混合采样的非平衡数据分类算法[J]. 计算机科学与探索,2019,13(2):342-349.(WuYifan,Liang Jiye,Wang Junhong.Classification algorithm based on hybrid sampling for unbalanced data [J]. Journal of Frontiers of Computer Science and Technology,2019,13 (2): 342-349.)   
[17] Chawla NV,Bowyer K W, HallL O,et al. SMOTE: synthetic minority over-sampling technique [J]. Journal ofArtificial Intelligence Research, 2002,16:321-357.   
[18] Blu T,Thevenaz P,Unser M.Linear interpolation revitalized [J]. IEEE Trans on Image Processing,2004,13 (5): 710-719.   
[19] Tao Xinmin, Zheng Yujia,Tao Weichen,et al. SVDD-based weighted oversampling technique for imbalanced and overlapped dataset learning [J].Information Sciences,2022, 588: 13-51.   
[20] Han Hui,Wang Wenyuan,Mao Binghuan. Borderline-SMOTE: a new over-samplingmethod inimbalanced datasetslearning [C]/ International Conference on Inteligent Computing.Berlin: Springer Press, 2005: 878-887.   
[21] He Haibo,Bai Yang, Garcia E A,et al. ADASYN: Adaptive synthetic samplingapproachforimbalanced learning[C]//2008 IEEE International Joint Conference on Neural Networks (IEEE World Congress on Computational Intelligence) .New York: IEEE Press,2008: 1322-1328.   
[22]严远亭，朱原玮，吴增宝，等．构造性覆盖算法的 SMOTE 过采样方 法[J].计算机科学与探索,2020,14(6): 975-984.(Yan Yuanting,Zhu Yuanwei,Wu Zengbao,et al. Constructive covering algorithm-based SMOTE over-sampling method[J]. Journalof Frontiers of Computer Science and Technology,2020,14 (6): 975-984.)   
[23]王芳，吴文通，张立立，等．邻域自适应SMOTE算法研究[J].计算 机应用研究,2021,38(06):1673-1677.(Wang Fang,Wu Wentong, Zhang Lili,et al. Research on neighborhood adaptive SMOTE algorithm [J].Application Research of Computers,2021,38 (06):1673-1677.)   
[24]李克文，林亚林，杨耀忠．一种改进的基于欧氏距离的 SDRSMOTE 算法[J].计算机工程与科学,2019,41(11):2063-2070.(Li Kewen, Lin Yalin, Yang Yaozhong.An improved SDRSMOTE algorithm based on Euclidean distance [J]. Computer Engineering & Science,2019,41 (11):2063-2070.)   
[25] Leevy JL, KhoshgoftaarTM,Bauder R A,etal. A survey on addressing high-class imbalance in big data[J].Journal ofBig Data,2018,5 (1): 1- 30.   
[26]盛凯，刘忠，周德超，等．面向不平衡分类的 IDP-SMOTE 重采样算 法[J].计算机应用研究，2019,36(01):115-118.(Sheng Kai,Liu Zhong,Zhou Dechao，et al. IDP-SMOTE resampling algorithm for imbalanced classification [J].Application Research of Computers,2019, 36 (01): 115-118.)   
[27] Bunkhumpornpat C， Sinapiromsaran K,Lursinsap C.DBSMOTE: density-based synthetic minority over-sampling technique [J].Applied Intelligence,2012,36 (3):664-684.   
[28] Nekooeimehr I,Lai-Yuen S K.Adaptive semi-unsupervised weighted oversampling (A-SUWO) for imbalanced datasets [J].Expert Systems with Applications,2016,46:405-416.   
[29] Douzas G,Bacao F,Last F.Improving imbalanced learning through a heuristic oversampling method based on k-means and SMOTE [J]. Information Sciences,2018,465:1-20.   
[30] Tao Xinmin,Li Qing,Guo Wenjie,et al.Adaptive weighted oversampling for imbalanced datasets based on density peaks clustering with heuristic filtering [J].Information Sciences,2020,519: 43-73.   
[31] Li Yihong,Wang Yunpeng,Li Tao,et al.SP-SMOTE:A novel space partitioning based synthetic minority oversampling technique [J]. Knowledge-Based Systems,2021,228:107269.   
[32]Douzas G,Bacao F.Geometric SMOTE a geometrically enhanced dropin replacement for SMOTE [J].Information Sciences,2019,501:118- 135.   
[33] Zhu Tuanfei,Lin Yaping,Liu Yonghe.Improving interpolation-based oversampling for imbalanced data learning [J].Knowledge-Based Systems,2020,187:104826.   
[34] Raghuwanshi B S,Shukla S.SMOTE based class-specific extreme learning machine for imbalanced learning [J].Knowledge-Based Systems,2020,187:104814.   
[35] Moreno-torres JG,Saez JA,Herrera F.Study on the impact of partitioninduced dataset shift on k-fold cross-validation[J].IEEE Trans on Neural Networks and Learning Systems,2012,23 (8):1304-1312.   
[36]Elyan E,Moreno-garcia CF,Jayne C.CDSMOTE:class decomposition and synthetic minority class oversampling technique for imbalanced-data classification [J].Neural Computing and Applications,2021,33(7): 2839-2851.   
[37] Niu Kun,Zhang Zaimei,Liu Yan,et al.Resampling ensemble model based on data distribution for imbalanced credit risk evaluation in P2P lending [J].Information Sciences,2020,536:120-13.