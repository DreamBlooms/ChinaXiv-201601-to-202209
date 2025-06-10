# 基于称名反应模型的CD-CAT选题方法比较

张杰1罗照盛\*\*1喻晓锋\*\*秦春影

(江西师范大学心理学院，南昌，330022)(南昌师范学院数学与信息科学学院，南昌，330032)

摘要当前大多数CD-CAT有关的研究都是基于0-1计分的数据资料展开的，而在实际的教育与心理测验中，还包含大量称名反应数据。本文基于称名反应认知诊断模型（NR-cRUM）开发了适用于称名反应数据的CD-CAT（以下简称NCD-CAT)，并将7种0-1计分CD-CAT 的选题方法引入NCD-CAT中。比较不同条件下，不同选题方法对被试判准率和测验效率的影响。结果表明NRPWCDI、NRMPWKL等PWKL系新方法和NR SHE/MI方法能较好地适用于NCD-CAT，且在大多数条件下优于基线方法NRPWKL。研究拓展了称名多级计分CD-CAT的选题方法。

关键词CD-CAT；称名反应；NR-cRUM；选题方法；多项选择题

# 1. 引言

认知诊断计算机化自适应测验（CD-CAT；Cheng，2009）结合了认知诊断评价（CDA;Leighton&Gierl,2007;von Davier&Lee,2019）和计算机化自适应测验（CAT）两者的优势（罗照盛 等,2015;Yuetal.,2019)。根据计分方式的不同，CD-CAT可分为0-1计分和多级计分的CD-CAT。目前多数的CD-CAT研究都是基于0-1计分数据展开的。

然而在实际的教育和心理测验中，也存在很多的多级计分项目（刘拓 等,2015;王晓庆等,2016)。根据作答类别（responsecategories）之间有无顺序或等级，多级计分项目又可分为称名多级（nominal polytomous）和顺序多级（ordinal polytomous）计分。其中，称名多级计分数据常见于多项选择题（multiplechoice items,MCI)、个性或态度量表中只反映不同倾向并无明确正确答案的题目中，是指多个作答类别之间相对独立、无顺序或等级之分的数据。称名多级计分数据可认为是最一般、测量级别最低的数据类型，基于顺序或等级的多级计分以及0-1计分数据均可看成是称名多级计分的特例（Mellenbergh,1995）。

为了能分析并提取称名反应数据中的信息，研究者们开发了相应的称名反应类模型。在 IRT的框架下，Bock（1972）开发了称名反应模型（nominal response model,NRM），并将该模型用于分析称名计分的多项选择题。结果表明，NRM能够利用错误选项中的信息，其能力估计精度显著高于普通0-1计分IRT 模型的估计精度；对于中低能力被试而言，NRM 模型的能力估计精度能够达到 2倍测验长度的 0-1 计分 IRT 模型的估计精度。Wang等（2017）将NRM用于构建可修改答案的CAT，利用NRM将被试的第一次作答及后续的修改作答均纳入到临时的和最终的能力估计中，从而提供更多的选题信息和更准确的能力估计值。该可修改答案的CAT方案正是利用了称名反应模型中各作答类别是称名计分这一特点。进一步，Wang 等（2019）对基于NRM的可修改答案的CAT方案从理论上讨论了其可行性。

在认知诊断的框架下，Templin等（2008）和dela Torre（2009）开发了称名反应认知诊断模型。依据传统0-1计分的认知诊断模型，被试只能被归为掌握组和未掌握组两个类别。而在称名反应认知诊断模型中，被试可以被分成更多的类别，从而能够提高对被试的$\star$ 本研究得到江西省教育科学十四五规划2021课题（21YB027）的资助$\star \star$ 通讯作者：喻晓锋，E-mail:xyu6@jxnu.edu.cn；罗照盛：luozs@jxnu.edu.cn

分类精度。Templin等（2008）将对数线性认知诊断模型（log-linearCDM,LCDM）进行称名多级化拓展，开发了 NR-DM（nominal response diagnostic model）及其缩减模型 NR-cRUM（nominal response compensatory reparameterized unified model，关于该模型的详细介绍见附录A)。与0-1计分cRUM相比，使用称名多级计分的NR-cRUM对被试的判准率更高。dela Torre（2009）将DINA模型进行称名多级化拓展，拓展后的MC-DINA模型的判准率显著高于DINA模型的判准率，原因是MC-DINA模型利用了干扰项中的诊断信息。郭磊和周文杰（2021）提出一类非参数化的诊断干扰项中信息的方法。

在查阅了国内外相关文献之后发现，仅有Yigit等（2019）开发了基于称名反应模型的CD-CAT。在该研究中，作者仅仅评估了一种选题方法的效率（通过与0-1计分的CD-CAT相比)，使用的称名反应认知诊断模型是MC-DINA 模型。MC-DINA 模型是一种非补偿模型，只适用于属性间的非补偿情形，且由于参数数量有限，模型不能直接解释每个属性与每个作答类别之间的关系，从而限制了模型参数解释的一般性（罗照盛 等,2020)。由于全模型的 NR-DM 参数较多，估计这些参数需要很大的样本量，所以其缩减形式 NR-cRUM实用性更大（李瑜,2014; Templin etal.,2008)，故本文采用 NR-cRUM模型来开发多级计分CD-CAT，将7种常见的选题方法拓展到适用于NR-cRUM的诊断测验中，并对它们在不同实验条件下的效率和精度进行综合比较。

# 2.基于称名反应的CD-CAT

# 2.1初始题

在CD-CAT的初始题阶段，研究者提出随机选取的方法；或给被试随机指定一种属性掌握模式（KS)，再利用选题方法选出相应的题（高椿雷 等,2017;Yu etal.,2019)。Zheng和 Chang（2016）提出的PWCDI和PWACDI选题法可以完全排除初始阶段KS估计不稳定的问题，天然地选出符合“T阵法”（涂冬波等,2013）初始选题法要求的题目。为了各选题法之间比较的公平，本研究拟采用随机选取1题并在各选题法中都使用这一题作为初始题的方法。

# 2.2适用于NCD-CAT的选题方法

在 0-1计分的CD-CAT中，研究者们提出了多种选题方法（郭磊 等,2016;李佳 等，2021;罗照盛 等,2015; Cheng,2009; Guo & Zheng,2019; Kaplan et al.,2015; Wang,2013; Yu etal.,2019；Zheng＆Chang,2016)。现有的多级计分CD-CAT选题方法（Gao et al.,2020）主要从0-1计分的CD-CAT拓展而来，本研究沿用这一方法，将传统CD-CAT中效果较好的几种选题方法拓展至NCD-CAT中。

假设有 $K$ 个属性将被试分为 $C = 2 ^ { K }$ 个潜在类，第 $j$ 题有 $b _ { j } + 1$ 个选项（1个正确选项，$b _ { j }$ 个干扰项)。则本研究所涉及的NCD-CAT选题方法介绍如下。

# $2 . 2 . 1 \mathrm { K L }$ 信息矩阵及其变式

在介绍选题方法之前，先简要介绍 KL 信息矩阵。KL 信息矩阵又称D 矩阵（Henson& Douglas,2005)，是一个 $2 ^ { K } \times 2 ^ { K }$ 的矩阵（ $K$ 为属性个数)，它的每个元素是（给定作答反应条件下）两个KS之间的KL距离期望值。计算公式如下：

$$
D _ { j u v } = E _ { \alpha _ { u } } \left[ \log \left( \frac { P _ { \alpha _ { u } } ( X _ { j } ) } { P _ { \alpha _ { v } } ( X _ { j } ) } \right) \right]
$$

其中， $D _ { j u v }$ 是给定题目 $j$ 的作答为 $X _ { j }$ 时， $\pmb { \alpha _ { u } }$ 和 $\pmb { \alpha _ { v } }$ 之间 KL 距离的期望值；当 $X$ 是0-1计

分时， $D _ { j u v }$ 计算公式如下：

$$
D _ { j u v } = E _ { \alpha _ { u } } \left[ \log \left( \frac { P _ { \alpha _ { u } } \bigl ( X _ { j } \bigr ) } { P _ { \alpha _ { v } } \bigl ( X _ { j } \bigr ) } \right) \right] = \sum _ { x _ { j } = 0 } ^ { 1 } P _ { \alpha _ { u } } \bigl ( x _ { j } \bigr ) \log \left[ \frac { P _ { \alpha _ { u } } \bigl ( x _ { j } \bigr ) } { P _ { \alpha _ { v } } \bigl ( x _ { j } \bigr ) } \right]
$$

在NCD-CAT中， $X$ 是称名计分的。相应地计算 $\mathrm { ~ D ~ }$ 矩阵（此时记为NRD）时，应该按照每个作答类别的概率求期望值，即：

$$
N R \_ D _ { j u v } = \sum _ { x _ { j } = 0 } ^ { b _ { j } } P _ { \alpha _ { u } } \big ( x _ { j } \big ) \log \Bigg [ \frac { P _ { \alpha _ { u } } \big ( x _ { j } \big ) } { P _ { \alpha _ { v } } \big ( x _ { j } \big ) } \Bigg ]
$$

$N R \_ D _ { j u v }$ 矩阵包含了各个作答类别区分不同KS 的能力信息，将会比传统0-1计分的D 矩阵包含更多的信息。本研究中的PWKL系列选题法（NR_PWKL，NR_PWCDI,NRPWACDI,NRMPWKL）都是以NRD矩阵为基础，再结合相应0-1计分CD-CAT选题法的思想拓展而来，下文相同情况不再赘述。

题目水平的D矩阵能够表示该题的信息量，有研究者对D矩阵进行了不同形式的加权求和，得到 CDI和 ACDI指标（Henson & Douglas,2005; Henson et al.,2008)。其中 CDI是D 矩阵中的所有元素按两KS之间的海明距离（hamming distance）进行加权求平均的结果，而 ACDI是将D矩阵中海明距离为1的元素相加后求平均值，计算公式如下：

$$
\mathop { C D I _ { j } } = \frac { \displaystyle \sum _ { u \ne v } h ( \pmb { \alpha } _ { u } , \pmb { \alpha } _ { v } ) ^ { - 1 } \cdot D _ { j u v } } { \displaystyle \sum _ { u \ne v } h ( \pmb { \alpha } _ { u } , \pmb { \alpha } _ { v } ) ^ { - 1 } }
$$

$$
A C D I _ { j } = \sum _ { k = 1 } ^ { K } A C D I _ { j k } = \sum _ { k = 1 } ^ { K } \frac { 1 } { 2 ^ { K } } \sum _ { a l l r e l e v a n t c e l l s } D _ { j u v }
$$

其中，all relevantcells指 $\mathrm { ~ D ~ }$ 矩阵中两KS的海明距离为1的单元格。

# 2.2.2NR_PWKL

NCD-CAT的 PWKL 指标（以下称 NR_PWKL）是 PWKL（posterior-weighted KL）选题法（Cheng，2009）的称名多级化拓展。PWKL选题法对 $\mathrm { ~ D ~ }$ 矩阵的每个元素按每种KS 的后验概率加权求和，得到PWKL指标。而NRPWKL选题法对NRD矩阵中每个元素进行相同加权求和，计算公式如下：

$$
N R _ { - } P W K L _ { j } ( \widehat \alpha _ { i } ) = \sum _ { c = 1 } ^ { 2 ^ { K } } \{ [ \sum _ { y = 0 } ^ { b _ { j } } \log ( \frac { P ( Y _ { i j } = y | \widehat \alpha _ { i } ) ) } { P ( Y _ { i j } = y | \alpha _ { c } ) } ) P ( Y _ { i j } = y | \widehat \alpha _ { i } ) ] \pi ( \alpha _ { c } | y _ { t } ) \}
$$

其中， $\pi ( \pmb { \alpha } _ { c } | \pmb { y } _ { t } )$ 是观察到作答向量为 $\mathbf { \boldsymbol { y } } _ { t }$ 时，被试的属性掌握模式是 $\pmb { \alpha } _ { c }$ 的后验概率。

# 2.2.3NR PWCDI和NR PWACDI

Zheng 和Chang（2016）遵循 PWKL的思想，在 $\mathrm { ~ D ~ }$ 矩阵的行和列同时加入KS 的后验概率，构造出 PWD 矩阵（posterior-weighted D matrix)，再按照CDI和 ACDI指标加权的思想对 PWD 矩阵进行不同加权处理，得到 PWCDI和 PWACDI 指标。类似地，本文在NR D矩阵的行和列同时加入后验概率得到NRPWD矩阵，即公式（7)。再根据两种不同的加权思想将 NR_PWD矩阵和 NR_D矩阵加权求均值后得到 NR_PWCDI和 NR_PWACDI指标，即公式（8)，（9）。

$$
N R _ { - } P W D _ { j i c } = \pi ( \alpha _ { i } ) \times \pi ( \alpha _ { c } ) \times \left[ \sum _ { y = 0 } ^ { b _ { j } } \log \left( \frac { P \left( Y _ { i j } = y \middle | \widehat { \alpha } _ { i } \right) } { P \left( Y _ { i j } = y \middle | \alpha _ { c } \right) } \right) P \left( Y _ { i j } = y \middle | \widehat { \alpha } _ { i } \right) \right]
$$

$$
N R \_ P W C D I _ { j } = \frac { \displaystyle \sum _ { i \neq c } h ( \pmb { \alpha } _ { i } , \pmb { \alpha } _ { c } ) ^ { - 1 } \cdot N R _ { \_ P W D _ { j i c } } } { \displaystyle \sum _ { i \neq c } h ( \pmb { \alpha } _ { i } , \pmb { \alpha } _ { c } ) ^ { - 1 } }
$$

$$
N R \_ P W A C D I _ { j } = \frac { 1 } { 2 ^ { K } } \sum _ { a l l \ r e l e v a n t \ c e l l s } N R _ { - } D _ { j u v }
$$

同理，all relevantcells 指NRD矩阵中两KS的海明距离为1的单元格。

# 2.2.4NR MPWKL

Kaplan 等（2015）、Zheng 和Chang（2016）的研究都指出，在KL系列方法中，若仅使用当前KS 估计值的后验概率加权，不利于选出最合适的题。因为当测验较短时，当前KS的估计值通常都不太准确。除上述PWCDI类方法外，Kaplan等（2015）的MPWKL方法也能很好地解决这个问题。MPWKL方法对PWKL指标按照各KS 的后验概率再进行加权求和。本研究对 NRPWKL指标按照KS的后验概率再次加权求和，得到NR MPWKL指标，计算公式如下：

$$
N R _ { - } M P W K L _ { j } ( \widehat { \pmb { \alpha } } _ { i } ) = \sum _ { d = 1 } ^ { 2 ^ { K } } \{ \sum _ { c = 1 } ^ { 2 ^ { K } } [ \sum _ { y = 0 } ^ { b _ { j } } \log ( \frac { P ( Y _ { i j } = y | \widehat { \pmb { \alpha } } _ { i } ) } { P ( Y _ { i j } = y | \alpha _ { c } ) } ) P ( Y _ { i j } = y | \widehat { \pmb { \alpha } } _ { i } ) \pi ( \alpha _ { c } | y _ { t } ) ] \pi ( \alpha _ { d } | y _ { t } ) \} ( \widehat { \pmb { \alpha } } _ { i } ) ,
$$

与0-1计分一样，上述4种PWKL系新方法也是选择相应指标最大的题目。

# 2.2.5NR SHE

将香农熵（Shannon Entropy,SHE）应用于选题方法中，通过选择题库中期望香农熵最小的题目，使估计的KS 后验概率分布的不确定性最小。与 SHE不同的是，计算期望香农熵 NR_SHE 时，应该按照每个作答类别 $( \ b _ { j } + 1$ 个）的概率求香农熵的期望值，而不是仅仅考虑0和1两个作答类别。计算公式如下：

$$
N R _ { - } S H E = \sum _ { y = 0 } ^ { b _ { j } } \left[ \sum _ { c = 1 } ^ { 2 ^ { K } } \left( \pi ( \alpha _ { c } | y _ { t } , Y _ { t + 1 } = y ) \log { \frac { 1 } { \pi ( \alpha _ { c } | y _ { t } , Y _ { t + 1 } = y ) } } \right) P _ { r } ( Y _ { t + 1 } = y | y _ { t } ) \right]
$$

其中 $P r ( Y _ { t + 1 } = y | y _ { t } )$ 是观察到前 $\mathbf { \chi } _ { t }$ 次作答的向量为 $\mathbf { \boldsymbol { y } } _ { t }$ ，第 $t + 1$ 题的得分为 $y$ 的条件概率,其计算公式如下：

$$
\sum _ { c = 1 } ^ { 2 ^ { K } } P ( Y _ { t + 1 } = y | \pmb { \alpha } _ { c } ) \pi ( \pmb { \alpha } _ { c } | \pmb { y } _ { t } )
$$

其中 $\pi ( \pmb { \alpha } _ { c } | \pmb { y } _ { t } )$ 是被试完成 $t$ 道题目后，被试的属性掌握模式是 $\pmb { \alpha } _ { c }$ 的后验概率。

# 2.2.6NR MI

互信息（Mutual Information，MI）选题法是Wang（2013）提出的一种更适用于短测验的选题方法。类似地，求 NR_MI时，也应该分别按照 $b _ { j } + 1$ 个作答类别的概率求 MI 的期望，计算公式如下：

$$
N R _ { - } M I = \sum _ { y = 0 } ^ { b _ { j } } \left[ \sum _ { c = 1 } ^ { 2 ^ { K } } \left( \pi ( \alpha _ { c } | y _ { t } , Y _ { t + 1 } = y ) \log \frac { \pi ( \alpha _ { c } | y _ { t } , Y _ { t + 1 } = y ) } { \pi ( \alpha _ { c } | y _ { t } ) } \right) \sum _ { c = 1 } ^ { 2 ^ { K } } P ( Y _ { t + 1 } = y | \alpha _ { c } ) \pi ( \alpha _ { c } | y _ { t } ) \right]
$$

该方法选择题库中NRMI指标最大的题目。

# 2.2.7NR_GDI

Kaplan等（2015）将GDI（G-DINA discrimination index,GDI）指标用于CD-CAT的选题中，其中 $\bar { P } _ { j }$ 是除第一个选项外，其他选项（ $b _ { j }$ 个）的平均得分。

$$
N R _ { - } G D I = \sum _ { c = 1 } ^ { 2 ^ { K } } \pi ( \pmb { \alpha } _ { c } | \pmb { y } _ { t } ) \left[ \sum _ { y = 1 } ^ { b _ { j } } P \big ( Y _ { i j } = y | \pmb { \alpha } _ { c } \big ) - \bar { P } _ { j } \right]
$$

$$
\bar { P } _ { j } = \sum _ { c = 1 } ^ { 2 ^ { K } } \pi ( \pmb { \alpha } _ { c } | \pmb { y } _ { t } ) \sum _ { y = 1 } ^ { b _ { j } } P \big ( Y _ { i j } = y \big | \pmb { \alpha } _ { c } \big )
$$

与 PWKL 系列指标一样，GDI指标越大，表示区分不同 KS 的能力越强。所以，NR_GDI方法选择题库中NR_GDI指标最大的题目。

# 2.3曝光控制

Zheng 和Wang（2017）基于计算机领域的二分搜索算法，开发了SDBS与DBS方法。通过与已有的控制题目曝光的方法（RP,RT,SHTVOR等）相比，新方法能够更高效地处理好测验准确率与曝光控制之间的权衡问题。本研究聚焦于各选题方法在被试分类精度和测验效率上的表现，故没有考虑曝光控制的问题。

# 2.4参数估计方法

在CD-CAT中有三种参数估计方法，分别是MLE,MAP,EAP（Huebner&Wang,2011）。其中 EAP计算的是被试属性掌握模式的期望后验概率，是在给定作答为 $\mathbf { \boldsymbol { y } } _ { t }$ 的条件下，将所有可能的KS与其对应的后验概率相乘再求期望值（公式16)，最后再进行二分取值转换。（涂冬波等,2017)。本研究采用的是EAP方法。

$$
\hat { p } _ { i k } = \sum _ { c = 1 } ^ { 2 ^ { K } } \pi ( \pmb { \alpha } _ { c } | \pmb { y } _ { t } ) \alpha _ { c k }
$$

# 2.5终止策略

目前 CD-CAT 的终止策略主要有定长和变长两类。Guo 和 Zheng（2019）指出：变长终止策略中的Tatsuoka规则和双标准规则在属性个数不同时，存在不稳定问题；并从信息论的视角提出了变长终止策略的新方法。本研究的重点是选题方法的比较，因此终止策略仅考虑定长和最大后验概率达到某一固定精度的变长策略（Yuetal.,2019)。

# 3.模拟研究

为考察和比较NCD-CAT不同选题方法的性能，本研究开展了两项实验。

# 3.1实验一：定长NCD-CAT

实验一是一个 $2 \times 4 \times 7$ 的三因素完全随机实验设计。自变量分别是题目质量、题长、选题方法。其中题目质量有高、低两个水平，题长有5,10,15,20四个水平，选题方法有NR_PWKL,NR_PWCDI,NR_PWACDI,NR_MPWKL,NR_SHE,NR_MI,NR_GDI7种方法。具体实验过程描述如下：

# 3.1.1数据模拟

被试方面，本实验假设5个独立属性共32种属性掌握模式的被试在人群中均匀分布，模拟生成3200名被试。

题库方面，本实验采用Ma 和dela Torre（2016）类似的模拟方法生成高、低质量的题库（各600题）， $\varrho$ 矩阵采用dela Torre（2009）的 $\varrho$ 矩阵（见附录B)。对于高（或低）质量的题目，掌握该题目所考察的属性的被试选择正确答案的概率为0.8（或0.6)；被试选择错误答案的概率按均匀分布模拟。

模拟作答方面，先在（0,1）中生成一个均匀分布的随机数，然后比较这个随机数落在A,B,C,D哪一个累积作答概率区间内，就选择这个选项作为答案。（例如，当某被试选择各选项的概率依次是0.1,0.3,0.5,0.1，则累积作答概率分布为0.1,0.4,0.9,1，如果随机数为0.63，则模拟该被试选择第三个选项)。

# 3.1.2评价指标

定长NCD-CAT 的评价指标包括模式判准率（pattern match ratio,PMR）、 $\chi ^ { 2 }$ 和测验重叠率（testoverlap rate,TOR）。各评价指标的详细说明见附录C。

# 3.1.3实验一结果

实验一结果在表1，附录D：表D-1，图D-1，图D-2中。

表1七种选题方法的模式判准率、与NRPWKL比较的差值  

<html><body><table><tr><td rowspan="2">题长</td><td rowspan="2">方法 (NR-)</td><td colspan="2">高质量</td><td colspan="2">低质量</td></tr><tr><td>PMR</td><td>Difference</td><td>PMR</td><td>Difference</td></tr><tr><td rowspan="7">5</td><td>PWKL</td><td>0.624</td><td></td><td>0.335</td><td></td></tr><tr><td>PWCDI</td><td>0.711</td><td>0.087</td><td>0.367</td><td>0.032</td></tr><tr><td>PWACDI</td><td>0.714</td><td>0.090</td><td>0.373</td><td>0.038</td></tr><tr><td>MPWKL</td><td>0.704</td><td>0.080</td><td>0.357</td><td>0.022</td></tr><tr><td>SHE</td><td>0.736</td><td>0.112</td><td>0.352</td><td>0.017</td></tr><tr><td>MI</td><td>0.736</td><td>0.112</td><td>0.352</td><td>0.017</td></tr><tr><td>GDI</td><td>0.672</td><td>0.048</td><td>0.322</td><td>-0.013</td></tr><tr><td rowspan="6">10</td><td>PWKL</td><td>0.917</td><td></td><td>0.621</td><td></td></tr><tr><td>PWCDI</td><td>0.948</td><td>0.031</td><td>0.643</td><td>0.022</td></tr><tr><td>PWACDI</td><td>0.948</td><td>0.031</td><td>0.633</td><td>0.012</td></tr><tr><td>MPWKL</td><td>0.948</td><td>0.031</td><td>0.641</td><td>0.020</td></tr><tr><td>SHE</td><td>0.951</td><td>0.034</td><td>0.646</td><td>0.025</td></tr><tr><td>MI</td><td>0.951</td><td>0.034</td><td>0.646</td><td>0.025</td></tr><tr><td rowspan="7">15</td><td>GDI</td><td>0.948</td><td>0.031</td><td>0.607</td><td>-0.014</td></tr><tr><td>PWKL PWCDI</td><td>0.988</td><td></td><td>0.789</td><td></td></tr><tr><td>PWACDI</td><td>0.993</td><td>0.005</td><td>0.798</td><td>0.009</td></tr><tr><td></td><td>0.993</td><td>0.005</td><td>0.808</td><td>0.019</td></tr><tr><td>MPWKL</td><td>0.994</td><td>0.006</td><td>0.803</td><td>0.014</td></tr><tr><td>SHE</td><td>0.993</td><td>0.005</td><td>0.808</td><td>0.019</td></tr><tr><td>MI GDI</td><td>0.993 0.993</td><td>0.005</td><td>0.808</td><td>0.019</td></tr><tr><td rowspan="7">20</td><td>PWKL</td><td>0.999</td><td>0.005</td><td>0.772</td><td>-0.017</td></tr><tr><td>PWCDI</td><td>0.999</td><td>0</td><td>0.888</td><td></td></tr><tr><td>PWACDI</td><td>0.999</td><td>0</td><td>0.892 0.897</td><td>0.004 0.009</td></tr><tr><td>MPWKL</td><td>1</td><td>0.001</td><td>0.895</td><td>0.007</td></tr><tr><td>SHE</td><td>0.999</td><td>0</td><td>0.902</td><td>0.014</td></tr><tr><td>MI</td><td>0.999</td><td>0</td><td>0.902</td><td>0.014</td></tr><tr><td>GDI</td><td>0.998</td><td>-0.001</td><td>0.874</td><td>-0.014</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 整体趋势 (表1)：

（1）随着题目质量由低变高，各选题方法的PMR都明显提高，提升效果在短测验（5 题、10题）中尤为明显。例如当题长为5题时，各选题法的PMR几乎提升了一倍。（2）随着题长的增加，各选题法的PMR都有提高，提高的程度因题长和题目质量而异。具体而言，当题长由5题增加到10题时，不管题目质量高或低，它们的PMR都有超过 $20 \%$ 的提升；当题长由10题增加到15或20题时，低质量题目NCD-CAT的PMR仍有接近或超过 $10 \%$ 的提升。相较而言，提高题目质量比增加题长更能提高NCD-CAT的判准率。

# 各选题方法与基线方法NR_PWKL的比较（表1)：

（1）NR_PWKL 系新方法（NR_PWCDI,NR_PWACDI,NR_MPWKL）和NR_SHE/MI方法的PMR在所有条件下都高于或等于NRPWKL法，尤其是在题长为5和高质量题目条件下；（2）随着题长的增加，其余方法相较于NR_PWKL 法的 PMR 优势不断减小；这一趋势与Zheng 和Chang（2016）研究中PWCDI,PWACDI和MPWKL方法的变化一致；NR_PWCDI和NR_PWACDI与NR_MPWKL和NR_SHE/MI方法的比较（表1):

（1）NR_PWCDI和 NR_PWACDI方法与 NR_MPWKL 方法表现非常接近，与 Zheng和 Chang（2016）的结果一致，因为这类方法都是基于PWKL的改进；（2）香农熵类方法（SHE/MI）的PMR 高于或等于NR_PWKL系方法；Wang（2013）指出，MI选题法是一种在短测验中表现较好的方法。

NR_GDI方法在低质量题目条件下是7种方法中表现最差的，而在高质量题目条件下略微好于基线方法NR_PWKL。

# 测验重叠率（TOR）和卡方值（ $\chi ^ { 2 }$ ）（见附录表D-1)：

（1）NRGDI的TOR 和卡方值最大，题库安全性较差；NRMPWKL次之；（2）除NR GDI方法外，随着题目质量的提升，同等题长条件下其它方法的TOR均下降；随着题长的增加，同等题目质量条件下其它方法的TOR均上升；上述两点与Gao等（2020）的研究结果一致；（3）NRPWCDI和NRPWACDI方法的TOR 和卡方值大于NRPWKL法，但小于 NR_MPWKL 法；（4）相较而言，NR_SHE/MI方法的 TOR 和卡方值在不同条件下变化较平稳。

# 不同类型KS被试的判准率（见附录图D-1，图D-2)：

实验一还进一步分析了各选题方法对不同类型KS被试的判准率。由于所有题长条件下其变化趋势一致，故仅列出题长为10这一种情况。结果表明：

（1）题目质量对判准率的影响较大。题目质量由高到低，各方法对不同KS的PMR整体下降了 $30 \%$ 左右；（2）当题目质量高时，NRPWKL对不同KS的PMR较低；而当题目质量低时，NR_GDI取代 NR_PWKL 成为 PMR 最低的选题方法；上述两点在表1中也得到印证。

# 3.2实验二：变长NCD-CAT

实验二是 $2 \times 3 \times 7$ 的三因素完全随机实验。实验二将实验一的题长因素替换成最大后验概率的因素，其余自变量、数据模拟和参数估计方法均与实验一相同。实验二中最大后验概率分别是0.8,0.85,0.9；终止条件除了最大后验概率，还增设一个最大题长为20 题的条件。

实验二的评价指标是PMR和测验效率，后者主要体现在最大、最小、平均题长及题长的标准差指标上。

# 3.2.1实验二结果

实验二结果在表2，附录D：表D-2，图D-3，图D-4中。各选题方法的平均题长以及与NRPWKL的比较（表2)：

（1）NR_PWCDI,NR_PWACDI,NR_MPWKL,NR_SHE,NR_MI选题法在所有实验条件下，都比NRPWKL的平均题长更短；尤其题目质量高时优势更明显，差值大于0.738题；（2）NRGDI方法则受题目质量影响，在高（或低）质量条件下题长小（或大）于NR_PWKL；（3）NR_PWCDI,NR_PWACDI和NR_MPWKL三种方法在所有变长条件下表现接近；与 NR_SHE/MI法比较方面，当终止规则较宽松或题目质量较好时，NR_SHE/MI的题长更短；反之前面三种方法的题长更短。

题长的其他描述统计量汇总见附录表D-2。

表2各选题方法的平均题长以及与NRPWKL比较的差值  

<html><body><table><tr><td rowspan="2">终止 规则</td><td rowspan="2">方法 (NR-)</td><td colspan="2">高质量</td><td colspan="2">低质量</td></tr><tr><td>Mean</td><td>Difference</td><td>Mean</td><td>Difference</td></tr><tr><td rowspan="7">0.8</td><td>PWKL</td><td>7.108</td><td></td><td>13.6</td><td></td></tr><tr><td>PWCDI</td><td>6.249</td><td>0.859</td><td>13.258</td><td>0.314</td></tr><tr><td>PWACDI</td><td>6.251</td><td>0.857</td><td>13.301</td><td>0.271</td></tr><tr><td>MPWKL</td><td>6.262</td><td>0.846</td><td>13.268</td><td>0.299</td></tr><tr><td>SHE</td><td>6.119</td><td>0.989</td><td>13.297</td><td>0.252</td></tr><tr><td>MI</td><td>6.119</td><td>0.989</td><td>13.297</td><td>0.252</td></tr><tr><td>GDI</td><td>6.492</td><td>0.616</td><td>14.227</td><td>-0.529</td></tr><tr><td rowspan="7">0.85</td><td>PWKL</td><td>7.72</td><td></td><td>15.009</td><td></td></tr><tr><td>PWCDI</td><td>6.822</td><td>0.897</td><td>14.702</td><td>0.284</td></tr><tr><td>PWACDI</td><td>6.823</td><td>0.896</td><td>14.694</td><td>0.285</td></tr><tr><td>MPWKL</td><td>6.83</td><td>0.889</td><td>14.648</td><td>0.304</td></tr><tr><td>SHE</td><td>6.766</td><td>0.953</td><td>14.781</td><td>0.194</td></tr><tr><td>MI</td><td>6.766</td><td>0.953</td><td>14.781</td><td>0.194</td></tr><tr><td>GDI</td><td>7.056</td><td>0.663</td><td>15.737</td><td>-0.558</td></tr><tr><td rowspan="7">0.9</td><td>PWKL</td><td>8.394</td><td></td><td>16.884</td><td></td></tr><tr><td>PWCDI</td><td>7.549</td><td>0.844</td><td>16.588</td><td>0.24</td></tr><tr><td>PWACDI</td><td>7.585</td><td>0.808</td><td>16.535</td><td>0.252</td></tr><tr><td>MPWKL</td><td>7.563</td><td>0.83</td><td>16.52</td><td>0.274</td></tr><tr><td>SHE</td><td>7.655</td><td>0.738</td><td>16.693</td><td>0.148</td></tr><tr><td>MI</td><td>7.655</td><td>0.738</td><td>16.693</td><td>0.148</td></tr><tr><td>GDI</td><td>7.884</td><td>0.509</td><td>17.653</td><td>-0.505</td></tr></table></body></html>

# 不同类型KS被试的平均题长（见附录图D-3，图D-4)：

实验二也进一步分析了不同 KS 类型的被试在各选题方法下的测验效率。由于所有条件下其变化趋势一致，故仅列出最大后验概率为0.85这一种情况。结果表明：

（1）NR_PWKL 对几乎所有KS 被试的题长最长，第二长的方法是NR_GDI；（2）NR SHE/MI方法对所有KS被试的题长最短；这两点发现与表2的结果是一致的。（3）随着被试掌握的属性个数增加，所有选题方法的平均题长呈现阶跃式下降，下降的拐点都出现在属性个数增加的地方；即在低质量题目条件下，能够通过多选择一些考察多个属性的题目给被试，以使得测验效率有较大提升；（4）在低质量题目条件下对于所有KS的被试，NR_GDI方法的平均题长最长，测验效率最低；NR_PWKL次之，其余方法差异不明显;这与表2的发现也是一致的。

# 4.总结与展望

认知诊断评价以诊断被试的认知优势和劣势见长，而CAT的优点是高效、精准地测量被试的能力。结合了两者优势的CD-CAT将会给教育工作者带来极大的便利。然而目前CD-CAT 应用于实践还不多，主要是还有不少问题亟待解决。本研究从CD-CAT无法充分利用称名反应数据中的信息入手，开发NCD-CAT选题方法。研究一比较了各选题方法在不同题长和不同题目质量条件下的 NCD-CAT表现，研究二对变长条件下各选题方法的表现进行了探究。结果表明：（1）NR_PWCDI,NR_PWACDI和NR_MPWKL方法在各实验条件下表现近似，且一致优于 NR_PWKL 方法；NR_SHE/MI方法与上述3种 NR_PWKL系新方法相比，在短测验时优于它们，但优势不大；（2）题目质量对测验判准率和测验效率的影响较大，在实际应用时应该挑选高质量的题目进入题库。研究拓展了称名多级计分CD-CAT的选题方法。

本文提出的 NCD-CAT 适用于称名反应数据，虽然可用于分析多选题各选项中的信息，但其应用范围仍然受到限制。后续研究有以下几个方面值得进一步探讨。（1）本文的NCD-CAT是以一个特殊的认知诊断模型为基础开发的多级计分CD-CAT，未来可以考虑使用一般的多级计分认知诊断模型（Gao et al.,2021)。（2）本文 NCD-CAT 的选题方法都是由0-1计分的CD-CAT拓展而来，未来可考虑开发针对多级计分CD-CAT特点的选题方法。例如 Yigit等（2019）使用 JSD（Jensen Shannon divergence）指标作为基于MC-DINA模型的 CD-CAT 选题方法，未来可将 JSD 法应用于 NCD-CAT中，以考察该选题方法的效果。（3）本研究的实验条件较为理想，还有很多实际的问题没有考虑进来，例如曝光控制、初始阶段的选题法、其他变长终止规则等，相关议题的最新研究成果值得借鉴。例如，未来可考虑 Zheng 和 Wang（2017）开发的 SDBS与 DBS方法，以处理好测验准确率与曝光控制之间的权衡问题；可利用 Zheng 和Chang（2016）提出的 PWCDI和 PWACDI选题法选出更合适的初始题；可结合Guo 和 Zheng（2019）提出的变长CD-CAT 终止策略的新方法，检验新方法在不同CDM中的稳定性。（4）基于称名反应数据的CDM最自然的应用是用于提取多选题干扰项中的诊断信息，未来可考虑比较不同称名反应认知诊断模型挖掘干扰项信息的效果。（5）本文研究的测验数据是基于0-1属性、多级计分，该类型数据能够提供更丰富的诊断信息。然而在0-1计分的框架下，也可通过属性多级化的方式来丰富测验数据中的信息，尤其是当考虑多级属性之间的顺序时（夏梦连等,2018;Ma,2021)。

虽然本研究的结果表明基于NR-cRUM的CD-CAT有很好的发展前景，但是这仍然没有充分发挥称名反应模型的优点。称名反应模型一个非常重要的优点是可以实现可修改答案的CAT（Wang et al.,2017,2019)。基于称名反应模型、可修改答案的CD-CAT 值得进一步深入研究。

# 参考文献

陈平,李珍,辛涛.(2011).认知诊断计算机化自适应测验的题库使用均匀性初探.心理与行为研究，9(2), 125-132, 153.

高椿雷,罗照盛,郑蝉金,喻晓锋,彭亚风,郭小军.(2017).CD-CAT初始阶段项目选取方法.心理科学,40(2),485-491.郭磊,郑蝉金,边玉芳,宋乃庆,夏凌翔.(2016).认知诊断计算机化自适应测验中新的选题策略：结

合项目区分度指标.心理学报,48(7),903-914.郭磊,周文杰.(2021).基于选项层面的认知诊断非参数方法.心理学报,53(9),1032-1043.李佳，丁树良，况天昊.(2021).区分度与测验进程相匹配的CAT选题策略．江西师范大学学报(自

然科学版),45(4),384-389.李瑜.(2014).多选题认知诊断测验编制及多策略的多选题认知诊断模型的开发(博士学位论文).

江西师范大学.刘拓,张佳慧,辛涛.(2015).多项选择题中干扰项信息的利用.心理学探新,35(3),261-265.罗照盛,杭丹丹,秦春影,喻晓锋.(2020).可以处理补偿作用的认知诊断模型:CDINA模型.江西师

范大学学报(自然科学版),44(5),441-453.罗照盛，喻晓锋,高椿雷,李喻骏,彭亚风,王睿,王钰彤.(2015).基于属性掌握概率的认知诊断计

算机化自适应测验选题策略.心理学报,47(5),679-688.涂冬波，蔡艳，戴海琦.(2013).认知诊断CAT选题策略及初始题选取方法．心理科学，36(2),469-涂冬波,郑蝉金,戴步云,汪文义.(2017).计算机化自适应测验：理论与方法.北京师范大学出版社王晓庆,罗芬,丁树良，熊建华.(2016).多级评分计算机化自适应测验动态调和平均选题策略．心

理学探新，36(3),270-275.

夏梦连,毛秀珍,杨睿.(2018).属性多级和项目多级评分的认知诊断模型.江西师范大学学报(自然 科学版),42(2),134-138.   
Bock, R. D.(1972). Estimating item parameters and latent ability when responses are scored in two or more nominal categories. Psychometrika, 37(1),29-51.   
Cheng,Y. (2009). When cognitive diagnosis meets computerized adaptive testing: CD-CAT. Psychometrika, 74(4), 619-632.   
de la Torre, J. (2009). A cognitive diagnosis model for cognitively based multiple-choice options. Applied Psychological Measurement, 33(3),163-183.   
Gao, X. L., Ma, W. C., Wang, D. X., Cai, Y.,& Tu,D. B. (2021). A class of cognitive diagnosis models for polytomous data. Journal of Educational and Behavioral Statistics, 46(3),297-322.   
Gao,X.L., Wang, D. X., Cai, Y.,& Tu, D.B. (2020). Cognitive diagnostic computerized adaptive testing for polytomously scored items. Journal of Classification, 37(3), 709-729.   
Guo,L.,& Zheng, C.J. (2019). Termination rules for variable-length CD-CAT from the information theory perspective. Frontiers in Psychology， 10, Article 1122. https://doi.0rg/10.3389/fpsyg.2019.01122   
Henson, R.,& Douglas,J. (2005). Test construction for cognitive diagnosis. Applied Psychological Measurement, 29(4), 262-277.   
Henson，R.，Roussos,L.， Douglas，J.，& He， X. M. (2008). Cognitive diagnostic atribute-level discrimination indices. Applied Psychological Measurement, 32(4),275-288.   
Huebner, A., & Wang, C. (2011). A note on comparing examinee classification methods for cognitive diagnosis models. Educational and Psychological Measurement, 71(2), 407-419.   
Kaplan，M.， de la Torre,J.，& Barrda, J. R. (2015). New item selection methods for cognitive diagnosis computerized adaptive testing. Applied Psychological Measurement, 39(3),167-188.   
Leighton, J. P., & Gierl, M. J. (2007). Cognitive diagnostic assessment for education: Theory and applications. Cambridge University Press.   
Ma, W. C,& de la Torre, J. (2016). A sequential cognitive diagnosis model for polytomous responses. British Journal of Mathematical and Statistical Psychology, 69(3),253-275.   
Ma,W. C. (2021).A higher-order cognitive diagnosis model with ordinal atributes for dichotomous responsedata.MultivariateBehavioralResearch.Advanceonlinepublication. https://doi.0rg/10.1080/00273171.2020.1860731   
Mellenbergh， G. J. (1995). Conceptual notes on models for discrete polytomous item responses. Applied Psychological Measurement, 19(1),91-100.   
Templin, J., Henson, R., Rupp,A., Jang,E.,& Ahmed, M.2o08, March). Cognitive diagnosis models for nominal response data. Paper presented at the annual meeting of the National Council on Measurement in Education, New York.   
von Davier, M., & Lee, Y.-S. (2019). Handbook of diagnostic classification models. Springer.   
Wang,C. (2013). Mutual information item selection method in cognitive diagnostic computerized adaptive testing with short test length. Educational and Psychological Measurement, 73(6),1017- 1035.   
Wang,S. Y., Fellouris,G.，& Chang, H.-H. (2017). Computerized adaptive testing that allows for response revision: Design and asymptotic theory. Statistica Sinica,27(4),1987-2010.   
Wang, S.Y., Felouris, G.,& Chang, H.-H. (2019). Statistical foundations for computerized adaptive testing with response revision. Psychometrika, 84(2),375-394.   
Yigit, H. D.， Sorrel, M. A.,& de la Torre,J. (2019). Computerized adaptive testing for cognitively based multiple-choice data. Applied Psychological Measurement, 43(5),388-401.   
Yu,X.F.，Cheng，Y.，& Chang，H.-H. (2019). Recent developments in cognitive diagnostic computerized adaptive testing (CD-CAT): A comprehensive review. In M. von Davier, & Y. S. Lee (Eds.), Handbook of diagnostic classification models (pp. 307-331). Springer.   
Zheng,C.J.，& Chang,H.-H. (2016). High-efficiency response distribution-based item selection algorithms for short-length cognitive diagnostic computerized adaptive testing. Applied Psychological Measurement, 40(8), 608-624.   
Zheng,C. J.,& Wang, C. (2017). Application of binary searching for item exposure control in cognitive diagnostic computerized adaptive testing. Applied Psychological Measurement, 41(7), 561-576.

# A Comparative Study of Item Selection Methods in CD-CAT

based on Nominal Response Model

Zhang Jie，Luo Zhaosheng，Yu Xiaofeng，QinChunying² (1School of Psychology, Jiangxi Normal University,Nanchang,330022) (School of Mathematics and Information Science，Nanchang Normal University， Nanchang 330032)

Abstract Cognitive Diagnostic Computerized Adaptive Testing (CD-CAT） combines the advantages of cognitive diagnosis and CAT, which could improve the efficiency and accuracy of CD-CAT. CD-CAT can be divided into two types: dichotomous and polytomous.Presently, the majority of researches on CD-CAT are based on dichotomous CD-CAT. However, among the practical tests in psychology and education, there are many polytomous items,which can be further divided into nominal polytomous and ordinal polytomous items according to whether there is an order or grade between every response category. Nominal polytomous items are items whose response categories are independent and without orders or grades between every response category. Although researchers have developed (ordinal) polytomous CDMs and corresponding CD-CAT, few nominal CDMs and CD-CAT are based on nominal responses.

This study introduces seven commonly used item selection methods in dichotomous CD-CAT into NCD-CAT (CD-CAT based on nominal response models). PMR (pattern match ratio) and test efficiency index are evaluated under different conditions between these item selection methods. Here are details of two simulation studies below. Study 1 compared the performance of NR_PWKL，NR_PWCDI, NR_PWACDI， NR_MPWKL，NR_SHE，NR_MI，and NR_GDI methods under different test lengths (5,10,15,20) and item pool qualities (high and low) in NCDCAT.Results showed that: (1) the PMRs of NR_PWCDI, NR_PWACDI, NR_MPWKL,NR_SHE, and NR_MI are higher than or equal to that of NR_PWKL, especially in short tests. (2) as test length gets longer, that PMR advantage is missing, which is the same as the results of Zheng and Chang (2016). (3） compared to test length, item quality has a greater impact on PMR.For instance, with item quality descending, the PMR declined about $30 \%$ among all conditions. Study 2 is an experiment on variable-length NCD-CAT that was conducted to compare the performance of each item selection method under the conditions of three maximum posterior probabilities (0.8, 0.85,0.9） and two item qualities (high and low). The results showed that: (1)under all experimental conditions the average test lengths of NR_PWCDI, NR_PWACDI, NR_MPWKL, NR_SHE,and NR_MI are shorter than that of NR_PWKL; the difference is more than 0.738. (2)affected by item quality, the average length of NR_GDI is smaler than that of NR_PWKL under high-quality conditions and larger than it under low-quality conditions.

To sum up, this study compared the performance of 7 commonly used item selection methods of dichotomous CD-CAT in NCD-CAT with different conditions (fixed and variable length). The simulation study showed that under most conditions， the NR_PWCDI， NR_PWACDI, NR_MPWKL，NR_SHE,and NR_MI methods performed well when compared to baseline algorithm NR_PWKL. This study has expanded the alternatives of item selection methods in NCD-CAT.

Keywords CD-CAT; nominal responses; NR-cRUM; item selection methods; multiple-choice items

# 附录A

本研究中 NR-cRUM 模型是全模型 NR-DM（nominal response diagnostic model）的缩减形式。NR-DM是 Templin 等（2008）基于 LCDM 和 LCA 模型，融入称名反应模型（NRM）思想而开发的称名反应认知诊断模型。其项目反应函数如下所示：

$$
P ( X = x ) = \sum _ { c = 1 } ^ { C } \eta _ { c } \prod _ { j = 1 } ^ { I } \left[ \prod _ { m _ { j } \epsilon M _ { j } } \pi _ { j , c , m _ { j } } ^ { I ( x _ { j } = m _ { j } ) } \right]
$$

其中，测验 $\boldsymbol { \mathcal { Q } }$ 矩阵为 $Q = ( q _ { k j } ) _ { K \times J }$ ， $K$ 为属性个数， $J$ 为项目个数， $C = 2 ^ { K }$ 表示 $K$ 个属性把被试分成 $C$ 个潜在类。 $\pi _ { j , c , m _ { j } }$ 表示对于项目 $j$ ，第 $\mathbf { \Psi } _ { c }$ 类被试选择选项 $m _ { j }$ 的概率，且有（204号 $\begin{array} { r } { \sum _ { m _ { j } \in M _ { j } } \pi _ { j , c , m _ { j } } = 1 , \ \forall j , c } \end{array}$ ， $\eta _ { c }$ 是第 $\mid c \mid$ 类被试在被试群体所占的比例，且 $\begin{array} { r } { \sum _ { c = 1 } ^ { 2 ^ { K } } \eta _ { c } = 1 . ~ M _ { j } } \end{array}$ 是项目 $j$ 所有可能的选项，这里的 $x$ 是反应向量， ${ \pmb x } = ( x _ { 1 } , \dots , x _ { J } )$ 。 $I ( \cdot )$ 是一个指示函数，当$x _ { j } = m _ { j }$ 时，它的值为1，当 $x _ { j } \neq m _ { j }$ 时，它的值为0.下面是 $\pi _ { j , c , m _ { j } }$ 的参数化形式：

$$
\begin{array} { c } { { \displaystyle \pi _ { j , c , m _ { j } } = P \big ( X _ { j } = m _ { j } \big | \alpha _ { c } \big ) = \frac { e x p \Big ( \lambda _ { 0 , j , m _ { j } } + \lambda _ { j , m _ { j } } ^ { T } h \big ( \alpha _ { c } , q _ { j } \big ) \Big ) } { \displaystyle \sum _ { m _ { j } \in M _ { j } } e x p \Big ( \lambda _ { 0 , j , m _ { j } } + \lambda _ { j , m _ { j } } ^ { T } h \big ( \alpha _ { c } , q _ { j } \big ) \Big ) } } } \\ { { \lambda _ { j , m _ { j } } ^ { T } h \big ( \alpha _ { c } , q _ { j } \big ) = \displaystyle \sum _ { k = 1 } ^ { K } \lambda _ { 1 , j , k , m _ { j } } \big ( \alpha _ { c , k } q _ { j , k } \big ) + \displaystyle \sum _ { k = 1 } ^ { K - 1 } \sum _ { l = k + 1 } ^ { K } \lambda _ { 2 , j , k , l , m _ { j } } \big ( \alpha _ { c , k } \alpha _ { c , l } q _ { j , k } q _ { j , l } \big ) + \cdots } } \end{array}
$$

$\boldsymbol { \alpha } _ { c } = ( \alpha _ { c 1 } , \dots , \alpha _ { c K } ) ^ { \prime }$ 是第 $\boldsymbol { c }$ 类被试的属性掌握模式。对于项目 $j$ 的每个选项都有三类参数，分别是：（1）截距参数 $\lambda _ { 0 , j , m _ { j } }$ ；（2）属性 $k$ 的主效应参数 $\lambda _ { 1 , j , k , m _ { j } }$ ；（3）属性 $k$ 与属性$l$ 的交互效应参数 $\lambda _ { 2 , j , k , l , m _ { j } }$ ，以及两个以上属性的交互效应参数。为了模型的可识别性，需要约束各类参数之和为0，如： $\begin{array} { r } { \sum _ { m _ { j } \in M _ { j } } \lambda _ { 0 , j , m _ { j } } = 0 , ~ \forall j ; ~ \sum _ { m _ { j } \in M _ { j } } \lambda _ { 1 , j , k , m _ { j } } = 0 , ~ \forall j , k } \end{array}$ 等。

由于NR-DM是基于LCDM模型的拓展，因此它是一个更一般、更广义的称名反应认知诊断模型。在NR-DM中，若仅考虑题目考察的所有属性的交互效应，则该模型等价于MC-DINA模型，是一个非补偿模型；若不考虑题目考察的所有属性的交互效应，则该模型属于补偿模型。在实际应用中，考虑了交互效应的 NR-DM 需要估计的参数非常多，需要非常大的样本量才能够进行准确的参数估计，所以NR-cRUM模型是一个更实际的选择，具有较大的实用性（Templin etal.,2008)。NR-cRUM模型的项目反应函数如下所示：

$$
\pi _ { j , c , m _ { j } } = P \big ( X _ { j } = m _ { j } \big | \alpha _ { c } \big ) = \frac { e x p \left( \lambda _ { 0 , j , m _ { j } } + \sum _ { k = 1 } ^ { K } \lambda _ { 1 , j , k , m _ { j } } \big ( \alpha _ { c , k } q _ { j , k } \big ) \right) } { \sum _ { m _ { j } \in M _ { j } } e x p \left( \lambda _ { 0 , j , m _ { j } } + \sum _ { k = 1 } ^ { K } \lambda _ { 1 , j , k , m _ { j } } \big ( \alpha _ { c , k } q _ { j , k } \big ) \right) }
$$

其中， $\begin{array} { r } { \sum _ { m _ { j } \in M _ { j } } \lambda _ { 0 , j , m _ { j } } = 0 , \ \forall j ; \sum _ { m _ { j } \in M _ { j } } \lambda _ { 1 , j , k , m _ { j } } = 0 , \ \forall j , k } \end{array}$ .且如果 $m _ { j }$ 是项目 $j$ 的正确答案选项，则 $\lambda _ { 1 , j , k , m _ { j } } > 0 , \ \forall k .$

根据上面的项目反应函数可以看出，在全模型和缩减模型中，属性定义在选项水平上，属性的定义更精细。且项目参数定义在题目和选项的交互水平上，模型参数的可解释性更强。

为了更好地理解 NR-cRUM 模型，不妨借助下面这个数学推理题来理解（Templin etal.,2008)。

甲住在距离乙家 $\frac { 2 } { 3 }$ 米的地方，甲从家出发朝着乙家走去，某时刻甲距离乙家还有 $\frac { 1 } { 4 }$ 米，问：此时甲已经走了多少路程？下面哪个选项表示甲走过的路程。（注：各选项的线段长度这道题考察了两个属性：1.识别一个指定量的参照单位；2.分数减法。

![](images/2f9eb8810d1a13f2431ef373e765ea074ab6b072c1443434454377587e3a702b.jpg)  
图A-1

假定该题目各选项的参数如表A-1所示，根据公式（A-4）可算出不同属性掌握模式的被试选择不同选项的概率，如图A-2所示（该题正确选项为D）。

表A-1NR-cRUM模型题目各选项的参数  

<html><body><table><tr><td></td><td>A</td><td>B</td><td>C</td><td>D</td></tr><tr><td>0,jmj</td><td>1</td><td>0.5</td><td>0.5</td><td>-2</td></tr><tr><td>1,j1.m</td><td>-1</td><td>-1</td><td>0</td><td>2</td></tr><tr><td>1,j2.mj</td><td>-1</td><td>0</td><td>-1</td><td>2</td></tr></table></body></html>

为1米)

表A-2NR-cRUM模型不同KS的被试选择各选项的概率  

<html><body><table><tr><td></td><td>A</td><td>B</td><td>C</td><td>D</td></tr><tr><td>(0,0)</td><td>0.442</td><td>0.268</td><td>0.268</td><td>0.022</td></tr><tr><td>(0,1)</td><td>0.235</td><td>0.387</td><td>0.143</td><td>0.235</td></tr><tr><td>(1,0)</td><td>0.235</td><td>0.143</td><td>0.387</td><td>0.235</td></tr><tr><td>(1,1)</td><td>0.041</td><td>0.068</td><td>0.068</td><td>0.824</td></tr></table></body></html>

![](images/60fe684c0d2ebb02d57de8f797cbf54d09b4445c95ba7d65a6dd7569aa045788.jpg)  
NR-cRUM不同被试选择各选项的概率

![](images/ddc0a3e38f98d3a7da90fbd41ef92aae9f7ff0ddbce084f048103ead47635225.jpg)  
图A-2NR-cRUM模型下不同KS的被试选择各选项的概率  
图A-3cRUM模型下不同KS的被试答对或答错的概率

经过上面这个例子，可以看出 NR-cRUM 模型对被试选择每个选项的概率都进行了参数化，每个选项都有一套参数，根据公式（A-4）可以计算出被试选择每个选项的概率。结合表A-2和图A-2可知，两个属性都掌握了的被试（1,1）有0.824的概率会选择正确选项D，而被试（0,0），（0,1），（1,0）分别有较大概率选择A,B,C选项，即被试会选择与其能力相"匹配"的选项，所以说该模型能够利用每个选项的信息，从而能用更少的题目达到对被试能力更准确的测量。相较于传统0-1计分的CDM（cRUM)，对比图A-2和图A-3可知，NR-cRUM模型可以根据被试选择不同选项，区分出被试属于四种KS中的哪一种，而在cRUM模型中，只能将（1,1）与其它KS区分出来。很显然，通过对不正确选项的建模，NR-cRUM模型可以最大限度地获取选择题的诊断信息，并以此提高属性掌握模式的估计准确性和效率。

# 附录B

$\varrho$ 矩阵

<html><body><table><tr><td>0 0 0 ＩＩＩＩＩＩ 0 0 0 ００ OＩＩＩＩ 0 0 0 0 I 0 0 0 0 0 0 I</td></tr><tr><td>0 I I I 0 0 0 I I I 0 0 0 I I I 0 0 0 I 0 0 0 I 0</td></tr><tr><td>I 0 I I 0 II 0 OL 0 II 0 OI 0 0 I 0 0 0 I 0 0 0 0 I 0</td></tr><tr><td>I I 0 I I 0 I OI 0 I 0 I OI 0 OI 0 0 0 I 0 0 0 OI 0 0</td></tr><tr><td>0 0</td></tr><tr><td>I I 0 I I 0 I 0 0 I I 0 I 0 0 I 0 0 0 I 0 0 0 0 I 0 0 0</td></tr></table></body></html>

# 附录C

# 评价指标

判准率指标有属性判准率（attribute match ratio,AMR）和模式判准率（patterm matchratio,PMR)，计算公式如（C-1)，（C-2）。

$$
A M R _ { k } = \frac { \sum _ { i = 1 } ^ { N } I ( \widehat { \alpha } _ { i k } , \alpha _ { i k } ) } { N } , ( k = 1 , 2 , \dots , K )
$$

$$
P M R = \frac { \sum _ { i = 1 } ^ { N } I ( \widehat { \pmb { \alpha } } _ { i } , { \pmb { \alpha } } _ { i } ) } { N }
$$

其中 $K$ 表示属性总个数， $N$ 表示被试人数， $\hat { \alpha } _ { i k }$ 和 $\alpha _ { i k }$ 分别是 $\widehat { \pmb { \alpha } } _ { i }$ 和 $\pmb { \alpha } _ { i }$ 的第 $K$ 个元素。若$\hat { \alpha } _ { i k } = \alpha _ { i k }$ ，则称判准属性 $k$ 一次，AMR 的值越大，说明对单个属性的判准率越高。 $\widehat { \pmb { \alpha } } _ { i }$ 和${ \pmb { \alpha } } _ { i }$ 分别是第 $i$ 个被试的 KS 估计值和 KS 真值，若 $\widehat { \pmb { \alpha } } _ { i } = { \pmb { \alpha } } _ { i }$ 时，则称判准被试的 KS一次,PMR的值越大，说明对被试整个属性掌握模式的判准率越高。

题库安全性指标主要有 $\chi ^ { 2 }$ 和测验重叠率（test overlap rate,TOR）。 $\chi ^ { 2 }$ 指标描述的是理想项目曝光率分布与真实项目曝光率分布之间的差异，其计算公式如下：

$$
\chi ^ { 2 } = \frac { \displaystyle \sum _ { j = 1 } ^ { J } \left( e r _ { j } - { \cal L } _ { \big / J } \right) ^ { 2 } } { \displaystyle \left( { \cal L } _ { \big / J } \right) }
$$

其中 $J$ 是题库大小， $L$ 是测验的长度， $L / J$ 是均匀分布的项目曝光率。 $e r _ { j }$ 是第 $j$ 个题目的曝光率。 $\chi ^ { 2 }$ 指标越小越好，说明题库使用越均匀。测验重叠率反映的是不同被试调用相同题目的比例，其定义为两个随机抽取的被试作答相同题目的期望数除以题长，计算公式如下：

$$
T O R = \frac { { \sum _ { j = 1 } ^ { J } { T _ { j } \times \left( { { T _ { j } } - 1 } \right) } } } { L \times N \times ( N - 1 ) }
$$

其中， $T _ { j }$ 是第 $j$ 题被调用的次数。测验重叠率也是越小越好（陈平等,2011)。

# 附录D

表D-1七种选题方法的模式判准率、测验重叠率和卡方值  

<html><body><table><tr><td rowspan="2">题长</td><td rowspan="2">方法 (NR_)</td><td colspan="3">高质量</td><td colspan="3">低质量</td></tr><tr><td>PMR</td><td>TOR</td><td>x²</td><td>PMR</td><td>TOR</td><td>x²</td></tr><tr><td rowspan="9">5</td><td>PWKL</td><td>0.624</td><td>0.121</td><td>67.483</td><td>0.335</td><td>0.174</td><td>99.682</td></tr><tr><td>PWCDI</td><td>0.711</td><td>0.228</td><td>132.12</td><td>0.367</td><td>0.339</td><td>198.729</td></tr><tr><td>PWACDI</td><td>0.714</td><td>0.207</td><td>119.071</td><td>0.373</td><td>0.305</td><td>178.192</td></tr><tr><td>MPWKL</td><td>0.704</td><td>0.24</td><td>139.379</td><td>0.357</td><td>0.36</td><td>211.268</td></tr><tr><td>SHE</td><td>0.736</td><td>0.206</td><td>119.004</td><td>0.352</td><td>0.317</td><td>185.327</td></tr><tr><td>MI</td><td>0.736</td><td>0.206</td><td>119.004</td><td>0.352</td><td>0.317</td><td>185.327</td></tr><tr><td>GDI</td><td>0.672</td><td>0.434</td><td>255.219</td><td>0.322</td><td>0.307</td><td>179.57</td></tr><tr><td>PWKL</td><td>0.917</td><td>0.229</td><td>127.318</td><td>0.621</td><td>0.274</td><td>154.604</td></tr><tr><td>PWCDI</td><td>0.948</td><td>0.291</td><td>164.595</td><td>0.643</td><td>0.368</td><td>211.092</td></tr><tr><td></td><td>PWACDI</td><td>0.948</td><td>0.282</td><td>159.451</td><td>0.633</td><td>0.341</td><td>194.806</td></tr><tr><td>10</td><td>MPWKL</td><td>0.948</td><td>0.296</td><td>167.637</td><td>0.641</td><td>0.386</td><td>221.625</td></tr><tr><td>SHE</td><td></td><td>0.951</td><td>0.23</td><td>128.057</td><td>0.646</td><td>0.335</td><td>190.999</td></tr><tr><td>MI</td><td></td><td>0.951</td><td>0.23</td><td>128.057</td><td>0.646</td><td>0.335</td><td>190.999</td></tr><tr><td></td><td>GDI</td><td>0.948</td><td>0.426</td><td>245.786</td><td>0.607</td><td>0.401</td><td>230.914</td></tr><tr><td rowspan="7">15</td><td>PWKL</td><td>0.988</td><td>0.269</td><td>146.449</td><td>0.789</td><td>0.324</td><td>179.775</td></tr><tr><td>PWCDI</td><td>0.993</td><td>0.345</td><td>191.841</td><td>0.798</td><td>0.381</td><td>213.913</td></tr><tr><td>PWACDI</td><td>0.993</td><td>0.34</td><td>189.126</td><td>0.808</td><td>0.365</td><td>204.257</td></tr><tr><td>MPWKL</td><td>0.994</td><td>0.346</td><td>192.899</td><td>0.803</td><td>0.393</td><td>221.121</td></tr><tr><td>SHE</td><td>0.993</td><td>0.256</td><td>138.986</td><td>0.808</td><td>0.342</td><td>190.392</td></tr><tr><td>MI</td><td>0.993</td><td>0.256</td><td>138.986</td><td>0.808</td><td>0.342</td><td>190.392</td></tr><tr><td>GDI</td><td>0.993</td><td>0.417</td><td>235.127</td><td>0.772</td><td>0.435</td><td>245.966</td></tr><tr><td rowspan="7">20</td><td>PWKL</td><td>0.999</td><td>0.291</td><td>154.467</td><td>0.888</td><td>0.359</td><td>195.715</td></tr><tr><td>PWCDI</td><td>0.999</td><td>0.379</td><td>207.723</td><td>0.892</td><td>0.398</td><td>219.117</td></tr><tr><td>PWACDI</td><td>0.999</td><td>0.378</td><td>206.622</td><td>0.897</td><td>0.389</td><td>213.382</td></tr><tr><td>MPWKL</td><td>1</td><td>0.381</td><td>208.528</td><td>0.895</td><td>0.407</td><td>224.16</td></tr><tr><td>SHE</td><td>0.999</td><td>0.273</td><td>143.646</td><td>0.902</td><td>0.355</td><td>192.85</td></tr><tr><td>MI</td><td>0.999</td><td>0.273</td><td>143.646</td><td>0.902</td><td>0.355</td><td>192.85</td></tr><tr><td>GDI</td><td>0.998</td><td>0.425</td><td>235.231</td><td>0.874</td><td>0.451</td><td>250.801</td></tr></table></body></html>

表D-2各选题方法的判准率和题长的描述统计量  

<html><body><table><tr><td rowspan="2">终止 规则</td><td rowspan="2">方法 (NR)</td><td colspan="5">高质量</td><td colspan="5">低质量</td></tr><tr><td>PMR</td><td>Min</td><td>Max</td><td>Mean</td><td>SD</td><td>PMR</td><td>Min</td><td>Max</td><td>Mean</td><td>SD</td></tr><tr><td rowspan="7">0.8</td><td>PWKL</td><td>0.851</td><td>4</td><td>20</td><td>7.108</td><td>1.826</td><td>0.811</td><td>6</td><td>20</td><td>13.304</td><td>3.741</td></tr><tr><td>PWCDI</td><td>0.853</td><td>4</td><td>18</td><td>6.249</td><td>1.515</td><td>0.813</td><td>6</td><td>20</td><td>12.99</td><td>3.706</td></tr><tr><td>PWACDI</td><td>0.857</td><td>4</td><td>14</td><td>6.251</td><td>1.509</td><td>0.828</td><td>6</td><td>20</td><td>13.033</td><td>3.756</td></tr><tr><td>MPWKL</td><td>0.856</td><td>4</td><td>16</td><td>6.262</td><td>1.516</td><td>0.824</td><td>6</td><td>20</td><td>13.005</td><td>3.721</td></tr><tr><td>SHE</td><td>0.852</td><td>4</td><td>15</td><td>6.119</td><td>1.547</td><td>0.823</td><td>6</td><td>20</td><td>13.052</td><td>3.709</td></tr><tr><td>MI</td><td>0.852</td><td>4</td><td>15</td><td>6.119</td><td>1.547</td><td>0.823</td><td>6</td><td>20</td><td>13.052</td><td>3.709</td></tr><tr><td>GDI</td><td>0.866</td><td>4</td><td>14</td><td>6.492</td><td>1.32</td><td>0.803</td><td>6</td><td>20</td><td>13.833</td><td>3.77</td></tr><tr><td rowspan="6">0.85</td><td>PWKL</td><td>0.894</td><td>4</td><td>20</td><td>7.719</td><td>1.991</td><td>0.841</td><td>6</td><td>20</td><td>14.473</td><td>3.75</td></tr><tr><td>PWCDI</td><td>0.891</td><td>4</td><td>19</td><td>6.822</td><td>1.664</td><td>0.847</td><td>7</td><td>20</td><td>14.189</td><td>3.711</td></tr><tr><td>PWACDI</td><td>0.889</td><td>4</td><td>15</td><td>6.823</td><td>1.678</td><td>0.857</td><td>7</td><td>20</td><td>14.188</td><td>3.711</td></tr><tr><td>MPWKL</td><td>0.892</td><td>4</td><td>18</td><td>6.83</td><td>1.673</td><td>0.856</td><td>6</td><td>20</td><td>14.169</td><td>3.716</td></tr><tr><td>SHE</td><td>0.883</td><td>4</td><td>17</td><td>6.766</td><td>1.696</td><td>0.857</td><td>7</td><td>20</td><td>14.279</td><td>3.734</td></tr><tr><td>MI</td><td>0.883</td><td>4</td><td>17</td><td>6.766</td><td>1.696</td><td>0.857</td><td>7</td><td>20</td><td>14.279</td><td>3.734</td></tr><tr><td rowspan="6"></td><td>GDI</td><td>0.896</td><td>4</td><td>15</td><td>7.056</td><td>1.433</td><td>0.833</td><td>7</td><td>20</td><td>15.031</td><td>3.687</td></tr><tr><td>PWKL</td><td>0.932</td><td>5</td><td>20</td><td>8.393</td><td>2.101</td><td>0.866</td><td>7</td><td>20</td><td>15.872</td><td>3.536</td></tr><tr><td>PWCDI</td><td>0.926</td><td>5</td><td>19</td><td>7.549</td><td>1.831</td><td>0.869</td><td>7</td><td>20</td><td>15.632</td><td>3.564</td></tr><tr><td>PWACDI</td><td>0.927</td><td>5</td><td>19</td><td>7.585</td><td>1.862</td><td>0.874</td><td>7</td><td>20</td><td>15.62</td><td>3.56</td></tr><tr><td>MPWKL</td><td>0.928</td><td>5</td><td>19</td><td>7.563</td><td>1.833</td><td>0.874</td><td>8</td><td>20</td><td>15.598</td><td>3.569</td></tr><tr><td>SHE</td><td>0.922</td><td>5</td><td>18</td><td>7.655</td><td>1.82</td><td>0.881</td><td>7</td><td>20</td><td>15.724</td><td>3.56</td></tr><tr><td></td><td>MI</td><td>0.922</td><td>5</td><td>18</td><td>7.655</td><td>1.82</td><td>0.881</td><td>7</td><td>20</td><td>15.724</td><td>3.56</td></tr><tr><td></td><td>GDI</td><td>0.927</td><td>5</td><td>17</td><td>7.884</td><td>1.594</td><td>0.856</td><td>7</td><td>20</td><td>16.377</td><td>3.424</td></tr></table></body></html>

![](images/d70244cad9f02ab96edbb0bfd5cb444aa9b7779bb95e681906478dc19ecf3295.jpg)  
图D-1高质量题目（10题）条件下不同KS被试的PMR  
图D-2低质量题目（10题）条件下不同KS被试的PMR

不同属性掌握模式的被试的模式判准率10.90.80.7 W>酒 0.60.50.40.30.20.1000000 00001 00010 00100 10 000II OO1OI O1OOI 10001 OOIIO OIOIO 100IO 0 I1000 OOIII OIOII IO0II OIIOI IOTOI IIOOI OIIIO IOIIO IIOIO IIIOI OIIII [OIII IIOII IIIII IIIII IIIII被试属性掌握模式\*PWKL PWCDIPWACDI MPWKL SHE MI +GDI

![](images/7125bcc896f531e4661b23e53849b25163d088fcb7fa18e24b2fdeab22a35bed.jpg)

![](images/9aed07e1a9916b3f86586a51e773cbbe1309a8496716b6f56ef5d625de311c58.jpg)  
图D-3高题目质量和最大后验概率0.85条件下的平均题长  
图D-4低题目质量和最大后验概率0.85条件下的平均题长