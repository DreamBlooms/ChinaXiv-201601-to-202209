# 计算机化分类测验终止规则的类别、特点及应用

# 任赫 黄颖诗 陈平

（北京师范大学中国基础教育质量监测协同创新中心，北京，100875）

摘要计算机化分类测验（Computerized Classification Testing,CCT）能够高效地对被试进行分类，已广泛应用于合格性测验及临床心理学中。作为CCT的重要组成部分，终止规则决定测验何时停止以及将被试最终划分到何种类别，因此直接影响测验效率及分类准确率。已有的三大类终止规则（似然比规则、贝叶斯决策理论规则及置信区间规则）的核心思想分别为构造假设检验、设计损失函数和比较置信区间相对位置。同时，在不同测验情境下，CCT的终止规则发展出不同的具体形式。未来研究可以继续开发贝叶斯规则、考虑多维多类别情境以及结合作答时间和机器学习算法。针对测验实际需求，三类终止规则在合格性测验上均有应用潜力，而临床问卷则倾向应用贝叶斯规则。

关键词计算机化分类测验，终止规则，似然比，随机缩减，贝叶斯决策理论

# 1引言

由于能够改变传统纸笔测验中相对固化的试题形式、更深刻地体现“因材施测”和“高效施测”，计算机测验尤其是计算机化自适应测验（Computerized Adaptive Testing,CAT）近年来得到飞速发展。对于CAT 而言，其测验目的一般是准确估计被试能力，而计算机化分类测验（Computerized Classification Testing,CCT）——作为CAT 的一个重要分支——则以分类考生为目的。具体来说，CCT在CAT的基础上可以根据预设的分界分数将被试划分到两个（比如，掌握和未掌握）或多个（比如，合格、良好和优秀）不同的类别中。相比于传统纸笔测验，CCT的优势在于：首先，CCT不仅可以自适应地呈现最适合被试作答的题目，还可以在保持相同决策精度下大大缩短测验长度（Spray& Reckase,1996），进而降低测验成本、减少被试疲劳效应的影响；其次，CCT依托于计算机施测的特点使其能够为被试呈现更加丰富的测验内容和题目形式，并获取更多元细致的被试数据(比如交互式测评)；再者，

CCT 的高效计算力使得更精细测量模型和算法的使用成为可能，比如融入过程性或多模态数据的模型（Sie,etal.,2015; Zhan,etal.,2021）能够进一步满足各种测验需求、提升分类决策的可靠性。目前，CCT已经在合格性测验（比如，职业资格考试）以及临床心理学或医学诊断（比如，焦虑、抑郁等精神疾病的自我报告问卷和健康与护理问卷）中得到广泛应用（Finkelman et al.,2011; Huebner & Fina, 2015; Smits & Finkelman,2013）。

作为CAT的特例，完整的CCT同样包括心理测量模型、标定的题库、选题策略、能力参数估计方法以及终止规则五个核心部分。但是如前所述，两者在测验目的上并不相同：CAT的目的是对被试能力进行准确估计（陈平,2016)，而CCT是要对被试的类别进行准确划分。因此，终止规则是区分CCT与CAT的一项主要特征（任赫，陈平,2021）。总体而言，CCT终止规则关注的核心是系统是否有足够的把握将被试划分到某个特定的类别，或者说系统是否可以接受当前所做出的决策（比如：继续测验、将被试划分到掌握/未掌握类别）可能产生的成本（如：测验效率的牺牲、第I类或第Ⅱ类错误率）。由此，终止规则决定测验何时停止以及将被试最终划分到何种类别，将直接影响测验的效率和分类准确率。已有的CCT 终止规则包括定长（fixed-length）的规则（即每名被试作答固定数量的题目）以及变长（variable-length）的规则（即每名被试作答数量不定的题目）。定长的规则比较简单，不再赘述，本文主要关注变长的规则。需要指出的是，尽管定长终止规则的效率较低，但是它可以保证所有被试作答相同长度的测验，能够减少被试对测验公平的质疑，主要应用于在高利害测验中。与之相对应，变长的规则具有高效的特点，能够大大地缩短测验长度，可以广泛应用于各类低利害测验中。

变长CCT的实施过程可以看作一种序贯抽样方案，即"在抽样时不规定总的抽样个数，而是根据已抽取的样本结果决定是否继续抽样，直至停止”。最早的变长终止规则是Ferguson（1969）根据序贯检验（Wald，1947）提出的序贯似然比方法（Sequential Probability RatioTest,SPRT）。SPRT方法通过事先设定第I和第II类错误率来控制不同决策的损失，并使用二项分布对被试作答进行建模，相当于假设题库中所有题目的正确作答概率相同，相应地以随机或固定顺序呈现题目。但是，Lewis 和 Sheehan（1990）则认为应该在测验过程中直接控制每一步可能造成的损失，这就需要利用贝叶斯理论进行决策。另外，为了使序贯抽样过程能够与被试能力相适应，Reckase（1983）与Kingsbury 和Weiss（1983）分别引入项目反应理论（Item Response Theory,IRT）模型。前者使用IRT 模型代替二项分布，进而发展出允许自适应选题的 SPRT方法（也即对Ferguson 方法的改进），而后者利用能力估计的置信区间进行分类决策。综上，前人分别从不同的视角出发，基于不同的统计学理论建构出三类终止规则，它们分别是似然比规则、贝叶斯决策理论规则（后文简称贝叶斯规则）和置信区间规则（Ability Confidence Intervals,ACI）。

此外，在构造具体的CCT终止规则时，还需要考虑不同测验情境的特点，主要包括被试的类别数和测验的维度数。在被试类别方面，有时只需要将被试划分到两个不同类别，而有时则需要将被试划分到三个及以上的不同类别，它们分别对应于二分类的CCT与多分类的CCT。在测验维度方面，一些测验只需要考虑被试在单个维度上的潜在特质，但是更多的心理或教育测验往往需要同时考察被试在多个维度上的潜在特质（康春花，辛涛,2010），这就分别对应于单维 CCT（Unidimensional CCT,UCCT）与多维 CCT（Multidimensional CCT,MCCT）。需要说明的是，多分类的CCT终止规则在构造上与二分类的相比有较大差异，而 MCCT的终止规则通常可以由UCCT经过较为直接的推广而得到。

基于此，本文将结合不同的测验情境，对似然比规则、贝叶斯规则以及置信区间规则分别进行详细述评，然后对各种规则的优劣进行讨论分析，最后对CCT 终止规则的未来研究方向及应用进行说明。

# 2似然比规则

似然比规则的核心是通过构造似然比统计量（likelihood ratio statistics）进行假设检验。一般而言，似然比规则的构建主要包含四个步骤（任赫，陈平,2021）：（1）构造被试能力属于特定类别的假设检验；（2）在任意两个相邻的类别之间确定能力阈值；（3）在每个阈值的上下给定一个δ邻域。当被试的能力值落在该区间时，认为被试能力与阈值没有显著差异，因此该区间也被称为无差别区间；（4）构建似然比统计量并确定拒绝域。具体地说，根据不同的假设检验与统计量，似然比规则可以被划分为 SPRT 和广义似然比方法（GeneralizedLikelihood Ratio,GLR），下面进行详细介绍。

# 2.1序贯似然比方法 (SPRT)

# 2.1.1 二分类的 SPRT方法

最早的二分类似然比终止规则就是Wald（1947）提出的 SPRT。在此基础上，研究者们主要致力于解决两个方面的问题：一是如何进一步提升二分类 SPRT 的决策效率；二是如何将单维的二分类 SPRT 拓展到多维情境。对于第一个问题，Finkelman（2003,2010）发现如果将随机缩减（stochasticcurtailment）技术与 SPRT方法相结合可以进一步提高测验效率，因此在 SPRT 的基础上结合随机缩减技术开发出随机缩减的 SPRT（Stochastically CurtailedSPRT,SCSPRT）。需要指出的是，上述方法仅适用于单维情境。对于第二个问题，即将已有方法推广至MCCT时，规则的构建思路基本没有变化，但是能力参数的多维性会导致UCCT中的能力分界点转变为多维空间中的能力分界曲线或曲面（任赫，陈平,2021）。为此，Nydick（2013)从两个不同的角度解决这一问题，分别提出约束的 SPRT(Constrained SPRT,C-SPRT）以及使用空间投影方法构建的投影 SPRT（Projected SPRT,P-SPRT）。另外，Nydick（2013）还在C-SPRT 的基础上结合随机缩减技术开发出随机缩减的多维 SPRT（MultidimensionalSCSPRT,M-SCSPRT）。下文依次介绍单维的 SPRT与SCSPRT以及多维的C-SPRT、P-SPRT与 M-SCSPRT。

（1）单维的SPRT方法（SPRT与SCSPRT）

在UCCT中，SPRT使用一组简单假设来判断被试的能力分类，即

$$
\begin{array} { l } { { H _ { 0 } { : } \theta = \theta _ { l } { = } \theta _ { 0 } { - } \delta } } \\ { { H _ { 1 } { : } \theta = \theta _ { u } { = } \theta _ { 0 } { + } \delta ^ { , } } } \end{array}
$$

其中， $\theta$ 是被试的能力值， $\theta _ { 0 }$ 为事先确定的分界分数， $\delta$ 为邻域大小的一半，即无差别区间宽度的一半， $[ \theta _ { l } , \theta _ { u } ]$ 就是构造的无差别区间。由此， $H _ { 0 }$ 表示被试恰好被划入未掌握的一类， $H _ { 1 }$ 表示恰好被划入掌握的一类。

由此，SPRT（Wald,1947）构造对数似然比统计量如下，

$$
C _ { i j ^ { \prime } } = \log \left[ \mathrm { L R } ( \theta _ { u } , \theta _ { l } | Y _ { i , j ^ { \prime } } ) \right] = \log \left[ \frac { L \big ( \theta _ { u } \big | Y _ { i , j ^ { \prime } } \big ) } { L \big ( \theta _ { l } \big | Y _ { i , j ^ { \prime } } \big ) } \right] ,
$$

其中， $L \left( \theta \left| Y _ { i , j ^ { \prime } } \right. \right)$ 为基于 IRT 的似然函数， $\pmb { Y } _ { i , j ^ { \prime } } = ( Y _ { i 1 } , Y _ { i 2 } , \ldots , Y _ { i j ^ { \prime } } )$ 为被试 $i$ 在题目 $j = 1 , 2 , \dots , j ^ { \prime }$ 上的作答向量。记第I类、第 $\mathrm { I I }$ 类错误率分别为 $\alpha$ 和 $\beta$ ，令 $A = \beta / ( 1 - \alpha )$ 、 $B = ( 1 - \beta ) / \alpha$ ，$C _ { l } = l o g ( A )$ 、 $C _ { u } = l o g \left( B \right)$ （Finkelman,2003）。被试i完成 $j ^ { \prime }$ 道题目后，计算对数似然比统计量 $C _ { i { j ^ { \prime } } }$ ，并按如下规则对被试给出判断：若 $C _ { i j ^ { \prime } } \leq C _ { l }$ ，则考生的分数更有可能低于分数线，判断被试属于“未掌握”，并结束测验，记测验长度为j'；若 $C _ { i j ^ { \prime } } \geq C _ { u }$ ，则考生的分数更有可能高于分数线，判断被试属于“掌握”，并结束测验，记测验长度为 $j ^ { \prime }$ ；否则，要求被试继续作答下一道题。例如，图1展示了使用两参数逻辑斯蒂克模型模拟数据得到的“不同能力取值下的对数似然函数值”，当分界分数取 $- 0 . 5 \cdot \delta = 0 . 1 \cdot \alpha = \beta = 0 . 0 5$ 时，得到 $\theta _ { l } = - 0 . 6$ $\theta _ { u } = - 0 . 4 , C _ { l } = - 2 . 9 4 , C _ { u } = 2 . 9 4 ,$ 此时， $\begin{array} { r } { \log \left[ \mathrm { L } ( \theta _ { u } | \boldsymbol { Y } _ { i , j ^ { \prime } } ) \right] = - 9 . 6 8 , \log \left[ \mathrm { L } ( \theta _ { l } | \boldsymbol { Y } _ { i , j ^ { \prime } } ) \right] = - 1 2 . 4 1 , } \end{array}$ （204号于是计算得到对数似然比统计量 $C _ { i j ^ { \prime } } = ( - 9 . 6 8 ) - ( - 1 2 . 4 1 ) = 2 . 7 3$ 。由于 $C _ { l } < C _ { i { j ^ { \prime } } } { < } C _ { u }$ ，所以继续测验。

![](images/d343b8908cea6c0e365ca49a963c7558c4a3311c53cb8215e3cc5f59ae01d0d4.jpg)  
图1不同能力取值下的对数似然函数值示例

Wald-Wolfowitz 定理（Wald&Wolfowitz,1948）表明：在“测验持续进行直至满足 $C _ { i j ^ { \prime } } \leq$ $C _ { l }$ 或 $C _ { i j ^ { \prime } } \geq C _ { u }$ 而停止”的情况下，SPRT 是根据同样观测个数进行的检验中具有最大检验力的假设检验，即最优序贯检验。但是，受制于现实情境下的疲劳效应、练习效应等因素的影响，不可能要求被试持续作答直至满足上述条件（任赫，陈平,2021）。因此在CCT 的实际使用中，一般需要事先设定最大测验长度J。于是，研究者在设计CCT终止规则时一般规定，若在被试完成/道题目时测验仍未结束，则通过下述准则对被试进行强制分类：若 $C _ { i J } \leq C _ { 0 }$ 则停止测验，测验长度为J，并判断被试属于“未掌握”；若 $C _ { i J } > C _ { 0 }$ ，则停止测验，测验长度为』，并判断被试属于“掌握”。其中， $C _ { 0 } = ( C _ { l } + C _ { u } ) / 2$ 。

将被试最终结束测验时实际作答的题目数记为 $K$ ，对被试的分类判断结果记为 $D$ （其中，$D = m$ 表示被试属于“掌握”， $D = n$ 表示被试属于“未掌握”），则SPRT的判断准则可以概括如下，

$$
\begin{array} { r } { \{ \begin{array} { l l } { \{ \mathop { \mathbb { E } } _ { 1 } ^ { \Rightarrow } \lfloor \mathrm { L } \hat { y } \| \frac { \| \hat { y } \| _ { \infty } ^ { \delta } } { \partial \mathrm { S } _ { 1 } ^ { \prime } } , K = j ^ { \prime } , D = n \quad } & { \{ j ^ { \prime } < J , C _ { i j ^ { \prime } } \leq C _ { l } \} \not \exists \hat { \zeta } \{ j ^ { \prime } = J , C _ { i j ^ { \prime } } \leq C _ { 0 } \} } \\ { \{ \mathop { \mathbb { E } } _ { 2 } ^ { \Rightarrow } \lfloor \mathrm { L } \hat { y } \| \frac { \| \hat { x } \| _ { \infty } ^ { \delta } } { \partial \mathrm { S } _ { 1 } ^ { \prime } } , K = j ^ { \prime } , D = m \quad } & { \{ j ^ { \prime } < J , C _ { i j ^ { \prime } } \geq C _ { u } \} \not \exists \hat { \zeta } \{ j ^ { \prime } = J , C _ { i j ^ { \prime } } > C _ { 0 } \} . } \\ { \{ \mathop { \mathbb { E } } _ { 1 } ^ { \flat } \jmath _ { \infty } ^ { \star } \hat { z } \} \| \| \frac { \tilde { \eta } \langle \boldsymbol { x } \rangle } { \partial \mathrm { S } _ { 1 } ^ { \prime } } } \end{array}  } \end{array}
$$

值得注意的是，在 SPRT中引入最大测验长度J虽然能够解决一些现实问题，但是它违背Wald-Wolfowitz定理的前提假定，导致 SPRT不再是最优序贯检验。在现实测验中，这不仅会增加测验长度和测验时间，而且会提高题目曝光率。因此，在维持 SPRT 的分类准确率基本不变的基础上，尝试缩短测验长度可以减轻上述问题，有助于CCT的应用。随机缩减技术（Finkelman,2008;Huebner&Fina,2015）正是一种尝试缩短测验长度的方法。它的核心思想是：如果被试未来的作答不太可能会改变当前对被试的分类判断，那么此时便结束测验是合理的。

SCSPRT 规则就是一种将随机缩减技术与 SPRT 相结合的似然比终止规则。在完整保留公式（3）所定义的判断准则的基础上，SCSPRT 对原本需要继续作答的被试i进行预分类，并预测预分类结果能否保持。具体地说，SCSPRT首先按照SPRT方法计算等式（2）所定义的对数似然比统计量 $C _ { i { j ^ { \prime } } }$ ，然后再计算“被试完成整份测验，即作答完/题后，得到的分类结果”与当前的预分类结果一致的概率。使用 $D _ { j ^ { \prime } }$ 表示在被试完成j"道题目后对被试的预分类;$D _ { J }$ 表示被试作答的题目数达到最大测验长度j时得到的分类结果。上述概率就可以表示为$P \big ( D _ { J } = D _ { j ^ { \prime } } \big | C _ { i j ^ { \prime } } \big )$ ，同样使用 $C _ { 0 }$ 作为判断准则。于是，对于预分类为“未掌握”的被试，$P \big ( D _ { J } = D _ { j ^ { \prime } } \big | C _ { i j ^ { \prime } } \big ) = P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big ) \circ$

在公式（3）中，若 $j ^ { \prime } < J$ 且 $C _ { l } < C _ { i j ^ { \prime } } < C _ { u }$ ，被试将继续进行作答。但是，SCSPRT方法在 $j ^ { \prime } < J$ 时，对公式（3）所定义的判断准则进行如下调整，停止测验 $\begin{array} { r l r } & { , K = j ^ { \prime } , D = n } & { \{ C _ { i j ^ { \prime } } \leq C _ { l } \} \boxplus \widehat \Sigma \{ C _ { l } < C _ { i j ^ { \prime } } \leq C _ { 0 } , P ( D _ { J } = n | C _ { i j ^ { \prime } } ) \geq 1 - \epsilon _ { 1 } \} } \\ & { , K = j ^ { \prime } , D = m } & { \{ C _ { i j ^ { \prime } } \geq C _ { u } \} \boxplus \widehat \{ C _ { u } > C _ { i j ^ { \prime } } > C _ { 0 } , P ( D _ { J } = m | C _ { i j ^ { \prime } } ) \geq 1 - \epsilon _ { 2 } \} , } \end{array}$ 停止测验 （204 (4)继续测验 否则

其中，临界值 $\epsilon _ { 1 }$ 与 $\epsilon _ { 2 }$ 由测验开发者事先给定。以往的模拟研究表明：在保证一定分类精度的前提下，当 $\epsilon _ { 1 }$ 与 $\epsilon _ { 2 }$ 都取0.05 时，SCSPRT 能大幅缩短测验长度（Finkelman,2008,2010）。$P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big )$ 的具体计算详见Finkelman（2008）与任赫和陈平（2021）。需要指出的是，在自适应选题的情境下，无法提前确定接下来选取的题目，这会给 $P \big ( D _ { J } = n \big | C _ { i j ^ { \prime } } \big )$ 的计算带来一定困难。此时，可以选择一组“合适”的题目替代被试未来实际作答的题目。例如，若使用最大信息量选题策略，可以选择在被试“当前能力估计值”具有最大信息量的 $J - j ^ { \prime }$ 道题作为替代题目。有研究者指出，如果使用替代题目，需适当减小 $\epsilon _ { 1 }$ 和 $\boldsymbol { \epsilon } _ { 2 }$ 的取值（Finkelman,2008）。

（2）多维的SPRT方法（C-SPRT、P-SPRT与M-SCSPRT）

在上述的UCCT中，通过事先确定的能力阈值 $\theta _ { 0 }$ ，可以很容易获得公式（1）中所需要的 $\theta _ { l }$ 与 $\theta _ { u }$ ，并由此计算公式（2）所构造的 SPRT统计量 $C _ { i { j ^ { \prime } } }$ 。但是在MCCT中，事先确定的只能是能力分界曲线或曲面，导致无法直接得到某个确定的阈值 $\theta _ { 0 }$ 。此外，即使获得 $\theta _ { 0 }$ ，多维空间中的 $\theta _ { 0 }$ 在不同方向上可以构造任意多个δ邻域，因此如何选择可用于 $C _ { i { j ^ { \prime } } }$ 计算的 $\theta _ { l }$ 和 $\theta _ { u }$ 是另一个需要解决的问题。

C-SPRT使用“约束在分界曲线上的能力估计值”作为能力分界点 $\theta _ { 0 }$ 的近似 $( \widehat { \pmb { \theta } } _ { 0 }$ ），并在该点处，沿分界曲线的法向量方向计算相应的 $\pmb { \theta } _ { l }$ 和 $\pmb { \theta } _ { u }$ 的近似（ $\widehat { \pmb { \theta } } _ { l }$ 和 $\widehat { \pmb { \theta } } _ { u }$ ）。具体地说，被试i完成 $j ^ { \prime }$ 道题目后，C-SPRT算法首先在能力分界曲线或曲面（ $\overset { \cdot } { \boldsymbol { g } } ( \pmb { \theta } ) = 0$ ）上计算能力参数的极大似然估计值，并将其作为阈值的近似，即

$$
\widehat { \pmb { \theta } } _ { 0 } = \underset { \pmb { \theta } \in \Theta _ { 0 } } { \arg \operatorname* { m a x } } \big [ \log L \big ( \pmb { \theta } \big | \boldsymbol { Y } _ { i j ^ { \prime } } \big ) \big ] ,
$$

其中， $\pmb { \Theta } _ { 0 } = \{ \pmb { \theta } : g ( \pmb { \theta } ) = 0 \}$ 。然后，在 $\widehat { \pmb { \theta } } _ { 0 }$ 处沿 $g ( \pmb \theta ) = 0$ 的法向量方向构造 $\delta$ 邻域。记 $\pmb { \theta } _ { \delta }$ 为该方向上的单位向量，可得到无差别区间的上、下限分别为 $\widehat { \pmb { \theta } } _ { u } = \widehat { \pmb { \theta } } _ { 0 } + \delta \pmb { \theta } _ { \delta }$ 与 $\widehat { \pmb { \theta } } _ { l } = \widehat { \pmb { \theta } } _ { 0 } - \delta \pmb { \theta } _ { \delta }$ 。最后，再按照 SPRT构造似然比统计量（如公式（2）），就可以得到对数似然比统计量 $C _ { i j ^ { \prime } } =$ $\log \left[ \mathrm { L R } \big ( \widehat { \pmb { \theta } } _ { u } , \widehat { \pmb { \theta } } _ { l } \big | \mathbf { Y } _ { i j ^ { \prime } } \big ) \right] \circ$

P-SPRT与C-SPRT唯一的区别在于它采用“空间投影”而非“似然函数约束”的方法将分界曲线或曲面转换为可用于假设检验的分界点。具体地说，P-SPRT 将基于极大似然估计的被试能力估计值投影至能力分界曲线或曲面 $g ( \pmb \theta ) = 0$ 上，并将投影点视作单维情境下能力阈值的近似，即

$$
\widehat { \pmb \theta } _ { 0 } = \underset { \pmb \theta \in \Theta _ { 0 } } { \arg \operatorname* { m i n } } \big \| \widehat { \pmb \theta } _ { i } - \pmb \theta \big \| _ { 2 } ,
$$

其中， $\widehat { \pmb { \theta } } _ { i }$ 表示被试i的能力估计值， $\| \cdot \| _ { 2 }$ 表示欧式空间的距离。确定 $\widehat { \pmb { \theta } } _ { 0 }$ 后，P-SPRT与C-SPRT一样计算得到 $\widehat { \pmb { \theta } } _ { u }$ 、 $\widehat { \pmb { \theta } } _ { l }$ 以及 $C _ { i { j ^ { \prime } } }$ ，并按照等式（3）所定义的准则对被试进行分类判断。

此外，与单维随机缩减方法类似，同样可以在多维似然比统计量的基础上融入随机缩减技术。M-SCSPRT 就是将多维情境下的C-SPRT与随机缩减相结合的终止规则。具体地说，与单维的SCSPRT类似，M-SCSPRT使用C-SPRT的方法（等式（5））计算似然比统计量，并按照随机缩减技术计算 $P \big ( D _ { J } = D _ { j ^ { \prime } } \big | C _ { i j ^ { \prime } } \big )$ ，进而根据公式（3）和（4）对被试进行分类。

# 2.1.2 多分类的SPRT方法

多分类情境是指测验要将被试划分到三个及以上的不同类别中。在此情境下，如果被试需要被分到 $S + 1$ 个不同的类别之中，就需要定义S个能力分界点将不同被试区分开来。目前，在多分类情境下的终止规则研究仅限于UCCT。这些研究在二分类方法的基础上，使用不同的思路在多个分界点处构造假设检验与检验统计量以完成对被试的分类。下面对单维多分类CCT中的 SPRT方法进行介绍。

以上述的 $S + 1$ 个类别为例，多分类的 SPRT 规则根据所确定的S个能力分界点，建立S个无差别区间以及与之对应的S个二分类 SPRT 检验。为便于理解，图2展示的是一个三分类问题的示意图。其中， $\theta _ { 1 u }$ 和 $\theta _ { 1 l }$ 分别表示能力分界点 $\theta _ { 1 }$ 的无差别区间的上、下界， $\theta _ { 2 u }$ 和 $\theta _ { 2 l }$ 分别表示 $\theta _ { 2 }$ 的无差别区间的上、下界。

![](images/813f863b300507271a4d8e667f9e1ffcbe4f68c5817ff1537993950ebef15d3d.jpg)  
图2一个三分类问题的示意图

（1）Sobel-Wald方法

Sobel和Wald（1949）所提出的多分类 SPRT方法在每个能力分界点 $\theta _ { s }$ 处，构建一组简单假设，即

$$
\begin{array} { c } { { H _ { s 0 } \colon \theta \leq \theta _ { s l } = \theta _ { s } - \delta } } \\ { { H _ { s 1 } \colon \theta \geq \theta _ { s u } = \theta _ { s } + \delta ^ { \prime } } } \end{array} ,
$$

其中， $\theta _ { s l }$ 和 $\theta _ { s l }$ 分别表示能力分界点 $\theta _ { s }$ 所对应无差别区间的上、下界。基于公式（7）的假设检验，可以按照2.1.1中的 SPRT构造似然比统计量，

$$
C _ { s i j ^ { \prime } } = \log \Bigg [ \frac { L \big ( \theta _ { s u } \big | { \cal Y } _ { i j ^ { \prime } } \big ) } { L \big ( \theta _ { s l } \big | { \cal Y } _ { i j ^ { \prime } } \big ) } \Bigg ] .
$$

由此，即可在每个 $\theta _ { s }$ 处完成一组二分类的 SPRT检验。Sobel-Wald方法按照如下准则对被试进行分类判断：结合所有的S组检验，如果 $H _ { 1 0 }$ 被接受，就停止测验，测验长度为j'，判断被试属于能力最低的类别，即类别1；如果 $H _ { S 1 }$ 被接受，也停止测验，测验长度为j'，判断被试属于能力最高的类别，即类别 $S + 1$ ；如果 $H _ { s 1 }$ 和 $H _ { ( s + 1 ) 0 }$ 被同时接受，同样停止测验，测验长度为j'，判断被试属于类别 $s + 1$ ；否则，就继续进行测验。如果测验达到最大长度J，则停止测验，测验长度为J，并根据被试i的能力极大似然估计值 $\widehat { \theta } _ { i }$ 和分界点的相对位置对其进行分类。该方法最早由 Eggen（1999）应用于CCT，后来被 Thompson（2009）以及van Groen等人（2014）在三分类的情境下进行过评估。然而，Ghosh（1970）认为，在考虑更多的类别数时，Sobel-Wald方法可能无法得出一个明确的分类判断。

（2）Armitage方法

为解决Sobel-Wald方法可能无法得出结论的缺陷，Armitage（1950）提出一种比较所有可能的类别组合的 SPRT方法。具体地说，对于S个能力分界点，就需要构造 $S ( S + 1 ) / 2$ 组假设检验（Armitage,1950; Seitz&Frey,2013; Spray,1993）。此时，任一组假设检验的原假设$H _ { p }$ 与备择假设 $H _ { q }$ 分别表示考生属于类别 $p$ 和 $q$ 0 $\begin{array} { r } { p < q \in \{ 1 , \dots , S + 1 \} . } \end{array}$ ），即

$$
\begin{array} { c } { { H _ { p } \colon \theta \le \theta _ { p l } = \theta _ { p } - \delta } } \\ { { H _ { q } \colon \theta \ge \theta _ { ( q - 1 ) u } = \theta _ { q - 1 } + \delta ^ { . } } } \end{array}
$$

对应的检验统计量为，

$$
C _ { p q i j ^ { \prime } } = \log \left[ \frac { L \big ( \theta _ { ( q - 1 ) u } \big | Y _ { i j ^ { \prime } } \big ) } { L \big ( \theta _ { p l } \big | Y _ { i j ^ { \prime } } \big ) } \right] .
$$

Armitage方法的分类准则为：如果所有包括假设 $H _ { p }$ 的检验都接受假设 ${ \mathrm { \Delta } } H _ { p }$ ，则停止测验,测验长度为j'，判断被试属于类别 $p$ ；否则，测试将继续进行，直到满足上述条件或达到最大测试长度为止。

需要说明的是，只有当 Sobel-Wald方法无法给出准确的分类判断时，其与 Armitage 的方法才存在差异（Wang etal.,2021）。而在大多数情况下，这两种方法所得到的结果都一致，但是Armitage方法需要进行更多次检验。Wang 等人（2021）的研究中使用一个四分类问题为例，对其进行理论分析，感兴趣的读者可以参阅。也就是说，Sobel和Wald方法在测验的分类准确率上应与 Armitage 方法相近，但在测验耗时上应更胜一筹，这与已有研究的结果一致（Govindarajulu,1987; Ghosh & Sen,1991）。

# 2.2广义似然比方法（GLR)

在 SPRT中，最大测验长度的使用可能会降低分类准确率。为此，Bartroff等人（2008）将 GLR 应用于UCCT。之后，研究者又将随机缩减技术与GLR 相结合，提出随机缩减的GLR 方法（Stochastically Curtailed GLR,SCGLR; Huebner & Fina,2015）。另外,Nydick（2013）也将 GLR方法推广到多维情境中，提出多维的广义似然比方法（Multidimensional GLR,M-GLR）。

# 2.2.1 二分类的GLR方法

（1）单维的GLR方法（GLR与SCGLR）

不同于SPRT方法使用一组简单假设（即公式（1）），GLR使用下述的一组复合假设对被试进行分类判断，

$$
\begin{array} { c } { { H _ { 0 } \colon \theta \le \theta _ { l } } } \\ { { H _ { 1 } \colon \theta \ge \theta _ { u } \cdot } } \end{array}
$$

由此，GLR 统计量 $C _ { i { j ^ { \prime } } }$ 是在“无差别区间”两侧各自的对数似然函数最大值之比，即

$$
C _ { i j ^ { \prime } } = \log \frac { \underset { { \theta _ { 1 } \geq \theta _ { u } } } { \operatorname* { s u p } } \left[ L \left( \theta _ { 1 } \big | Y _ { i j ^ { \prime } } \right) \right] } { \underset { { \theta _ { 2 } \leq \theta _ { l } } } { \operatorname* { s u p } } \left[ L \left( \theta _ { 2 } \big | Y _ { i j ^ { \prime } } \right) \right] } .
$$

例如，在图1中，相比于SPRT 使用在 $\theta _ { u }$ 处的对数似然函数值（-9.68），GLR使用在$\theta _ { u }$ 右侧的似然函数最大值（即 $\theta _ { 1 }$ 处的-6.60），此时在 $\theta _ { l }$ 左侧的似然函数最大值与 SPRT 时一致，于是计算得到 $C _ { i j ^ { \prime } } = 5 . 8 1$ 。在得到广义似然比统计量 $C _ { i { j ^ { \prime } } }$ 后，GLR 规则也按照公式（3）所定义的准则对被试进行分类判断。

此外，也可以将随机缩减技术与GLR相结合，得到随机缩减的GLR方法。与 SCSPRT类似，SCGLR 是在GLR 的基础上结合随机缩减技术而得到的。具体而言，它使用与 GLR方法相同的统计量 $C _ { i { j ^ { \prime } } }$ （如等式（12）所示），然后根据随机缩减技术的要求计算$P \big ( D _ { J } = D _ { j ^ { \prime } } \big | C _ { i j ^ { \prime } } \big )$ ，最后根据公式（3）和（4）对被试做出分类判断。

（2）多维的GLR方法

等式（12）所示的GLR统计量 $C _ { i { j ^ { \prime } } }$ 是在“无差别区间”两侧各自的对数似然函数最大值之比，不再需要等式（2）中的 $\theta _ { u }$ 和 $\theta _ { l }$ 。因此，在将GLR推广到 MCCT时，不再需要考虑如何进行“分界曲线或曲面”和分界点的转换的问题。M-GLR统计量的定义为

$$
C _ { i j ^ { \prime } } = \log \frac { \underset { { \theta _ { 1 } \in \Theta _ { m } } } { \operatorname* { s u p } } \left[ L \left( \pmb { \theta } _ { 1 } \big | { \pmb Y } _ { i j ^ { \prime } } \right) \right] } { \underset { { \theta _ { 2 } \in \Theta _ { n } } } { \operatorname* { s u p } } \left[ L \left( \pmb { \theta } _ { 2 } \big | { \pmb Y } _ { i j ^ { \prime } } \right) \right] } ,
$$

其中， $\Theta _ { m }$ 表示多维空间中属于掌握类别的被试能力范围， $\Theta _ { n }$ 表示多维空间中属于未掌握类别的被试能力范围。因此，上式可以理解为对数似然函数在能力分界曲线或曲面两侧的最大值之比。与等式（12）所定义的单维GLR 统计量相比，等式（13）与其形式一致，仅将似然函数求极大值的区域由两个单维的区间扩展到两个多维的空间。因此，通过广义似然比的方式得到 $C _ { i { j ^ { \prime } } }$ 后，M-GLR 规则与GLR一样，也是按照等式（3）的准则对被试进行分类。

# 2.2.2 多分类的GLR方法

回到2.1.2中 $S + 1$ 个分类的问题，针对所定义的S个无差别区间，将由它们隔开的 $S + 1$ 个不同类别的被试能力区间分别记为 $\begin{array} { r } { \cdot \theta _ { 1 } \equiv \{ \theta \leq \theta _ { 1 l } \} , \ldots , \theta _ { s } \equiv \big \{ \theta _ { ( s - 1 ) u } \leq \theta \leq \theta _ { s l } \big \} , \ldots , \theta _ { s + 1 } \equiv } \end{array}$ $\{ \boldsymbol { \theta } \geq \boldsymbol { \theta } _ { S u } \}$ 。按照Wang 等人（2021)提出的多分类的GLR方法（multi-category GLR,mGLR），得到如下的复合假设

$$
H _ { s } \colon \theta \in \Theta _ { s } .
$$

由此，Wang等人（2021）指出可以根据序贯分析中的多假设GLR 检验（Tartakovsky,etal.,2014），为上述复合假设构造如下的多分类GLR统计量

$$
C _ { i j ^ { \prime } } ^ { s } = \log \left[ \frac { \prod _ { j = 1 } ^ { j ^ { \prime } } L ( \widehat { \theta } _ { i } | \boldsymbol { Y } _ { i j ^ { \prime } } ) } { \operatorname* { s u p } \prod _ { j = 1 } ^ { j ^ { \prime } } L ( \theta | \boldsymbol { Y } _ { i j ^ { \prime } } ) } \right] ,
$$

其中，分子部分表示似然函数的极大值，分母部分表示在能力区间 $\theta _ { s }$ 内似然函数的极大值。基于此，mGLR方法定义如下的分类准则：

(1）当 $\widehat { \theta } _ { i }$ 不属于任何一个无差别区间时，如果存在 $s$ ，对所有 $t \neq s$ ，有 $C _ { i j ^ { \prime } } ^ { t } \geq a _ { s t }$ ，则停止测验，测验长度为j'，判断被试属于类别s。这是因为当 $H _ { s }$ 为真时，在 $\Theta _ { s }$ 内的似然函数值会

大于在其他无差别区域内的似然函数值，从而使得 $C _ { i j ^ { \prime } } ^ { s }$ 的值较小而其他的 $C _ { i j ^ { \prime } } ^ { t }$ 的值较大。其中，$a _ { s t }$ 是一个事先给定的值，表示在 ${ \bf \mathcal { H } } _ { s }$ 为真时接受 $H _ { t }$ 的概率。

（2）否则，如果 $\widehat { \theta } _ { i }$ 落入由 $\theta _ { s }$ 所定义的无差别区间，则如等式（8）一样计算 $C _ { s i j ^ { \prime } }$ 以决定将被试划分到类别s或 $s + 1$ 或继续测验。

# 2.3似然比规则简评

似然比检验的核心思想是比较有约束条件的似然函数的最大值与无约束条件的似然函数的最大值。如果两者之间的差异不大，就可以认为对参数的约束有效；反之，则认为对参数的约束无效。基于此，似然比规则在不同类别下，建立符合该类别约束的似然函数，并比较不同类别约束条件的似然函数的最大值。如果某个类别的似然函数显著大于其他类别，就可以认为将考生划分到该类别是可信的，反之继续测验。由于似然比检验发展较为完备且具有良好的理论性质和检验效果，因此基于似然比检验的似然比规则是目前研究最为集中的一类CCT终止规则。已有研究也表明似然比规则还具有较好的稳健性，比如Huang 等人（2000）认为即使题目参数没有得到准确标定，SPRT方法也能获得较为准确的分类结果。但是，似然比规则也有一定的缺点，例如：（1）δ的取值在很大程度上影响着 SPRT方法的准确性与效率。尽管δ越大能使测验越快结束，但是大的δ会影响决策的精度。特别是对于多分类情境，如果δ过分大的话，不同的无差别区域很容易会出现重叠，从而使得我们很难去解释决策的结果。所以，δ的取值范围也是研究者需要注意的一个方面；（2）似然比规则在复杂测验情境（比如，多维和多分类）下的拓展比较复杂；（3）分界分数的选取具有较大的主观性。

# 3 贝叶斯决策理论规则

贝叶斯规则是另一类重要的CCT终止规则。不同于蕴含假设检验的规则，贝叶斯规则以贝叶斯决策论为基础，通过定义后验概率与损失函数，就可以选择期望损失最小的决策以完成对被试的分类判断。其中，损失由错误决策所产生，具体可分为阈值损失和线性损失。目前为止，研究者对贝叶斯规则的研究基本仍限于UCCT情境。

# 3.1 阈值损失

# （1）二分类的阈值损失规则

Lewis 和 Sheehan（1990）在二分类情境下提出一种阈值损失函数，也即用不同的常数来评估决策所有可能结果的损失。表1展示的是Lewis 和 Sheehan（1990）的研究中，作答$j ^ { \prime }$ 道题目后的阈值损失。

表1阶段j"时的二分类阈值损失函数  

<html><body><table><tr><td>决策</td><td>0=0</td><td>0=0u</td></tr><tr><td>被试属于“未掌握”</td><td>j'lc</td><td>l01+j'lc</td></tr><tr><td>被试属于“掌握”</td><td>l0+j'lc</td><td>j'lc</td></tr></table></body></html>

其中， $l _ { c }$ 表示被试作答一道题目的损失，以此控制测验效率（一般要求作答每道题目的损失是一样的）； $l _ { 1 0 }$ 为“将一位未掌握的考生划分到掌握类别”的损失， $l _ { 0 1 }$ 为“将一位掌握的考生划分到未掌握类别"的损失，以此控制测验精度。为简便起见，Lewis 和 Sheehan(1990)将各个测验阶段和各个决策的损失值都设置为相同。需要指出的是，正确分类所对应的损失$l _ { 0 0 }$ 与 $l _ { 1 1 }$ 并未在表1中呈现。这是因为，这里假定正确分类的损失相同并且损失值非常小。表1所展示的损失函数是重新量尺化后的结果， $l _ { 0 0 }$ 与 $l _ { 1 1 }$ 在量尺转换后变为0。此外，表1中并没有呈现“继续作答一道题目”的损失，这是因为继续作答的损失可以表示为与测验未来阶段中的分类决策（即掌握/未掌握）相关的损失的加权平均，权重等于得到相应决策的概率。

根据贝叶斯理论，被试i在作答 $j ^ { \prime }$ 道题后属于掌握类别的后验概率 $P _ { m | j ^ { \prime } }$ 可以如下式一般进行迭代计算，

$$
P _ { m | j ^ { \prime } } = P \big ( \theta = \theta _ { u } \big | F _ { i , j ^ { \prime } } \big ) = \frac { P \big ( Y _ { i , j ^ { \prime } } \big | \theta _ { u } \big ) \cdot P _ { m | j ^ { \prime } - 1 } } { P \big ( Y _ { i , j ^ { \prime } } \big | \theta _ { u } \big ) \cdot P _ { m | j ^ { \prime } - 1 } + P \big ( Y _ { i , j ^ { \prime } } \big | \theta _ { l } \big ) \cdot P _ { n | j ^ { \prime } - 1 } } ,
$$

其中，当 $j ^ { \prime } = 1$ 时， $P _ { m | j ^ { \prime } - 1 }$ 为被试为掌握类别的先验概率 $P _ { m }$ 。并且， $P _ { n | j ^ { \prime } } = 1 - P _ { m | j ^ { \prime } }$ 。在被试作答题目数量为j'时，被试i被划分为掌握类别的期望损失（也称为风险函数）为，

$$
\mathbb { E } _ { \theta } \big [ l ( \theta , m ) | { \cal Y } _ { i , j ^ { \prime } } \big ] = j ^ { \prime } \cdot l _ { c } + l _ { 1 0 } \cdot \big ( 1 - P _ { m | j ^ { \prime } } \big ) ,
$$

其中， $l ( \cdot , \cdot )$ 为损失函数。被试 $i$ 此时被划分为未掌握类别的期望损失为，

$$
\mathbb { E } _ { \theta } \big [ l ( \theta , n ) | { \cal Y } _ { i , j ^ { \prime } } \big ] = j ^ { \prime } \cdot l _ { c } + l _ { 0 1 } \cdot P _ { m | j ^ { \prime } } .
$$

此外，被试i还可能被要求继续测验。而计算此时继续测验的期望损失就需要考虑在 $j ^ { \prime } +$ 1时的所有可能决策的损失。为此，首先计算被试在第 $j ^ { \prime } + 1$ 道题目上的作答为 $\mathbf { \sigma } _ { s }$ 的概率，记为 $P _ { s \vert j ^ { \prime } }$ 。可以将 $P _ { s \vert j ^ { \prime } }$ 表示为 $P _ { m | j ^ { \prime } }$ 的函数，即，

$\begin{array} { r } { P _ { s | j ^ { \prime } } = P \big ( \boldsymbol { Y } _ { i , j ^ { \prime } + 1 } = s | \boldsymbol { Y } _ { i , j ^ { \prime } } \big ) = P \big ( \boldsymbol { Y } _ { i , j ^ { \prime } + 1 } = s \big | \theta _ { l } \big ) P _ { n | j ^ { \prime } } + P \big ( \boldsymbol { Y } _ { i , j ^ { \prime } + 1 } = s \big | \theta _ { u } \big ) P _ { m | j ^ { \prime } } , } \end{array}$ (19)其中， $P \big ( Y _ { i , j ^ { \prime } + 1 } = s \big | \theta _ { l } \big )$ 和 $P \big ( Y _ { i , j ^ { \prime } + 1 } = s \big | \theta _ { u } \big )$ 分别是“未掌握”与“掌握”的被试在第 $j ^ { \prime } + 1$ 题上作答为 $\mathbf { \sigma } _ { s }$ 的概率在整个题库水平上的平均值。

在贝叶斯规则中，使用最小化风险函数的方式给出决策。具体地说，在最大测验长度（即$j = J ;$ 时，由于必须对被试做出判断而不能继续要求被试作答，因此可以直接根据公式（17)

和（18）给出此时的风险函数，并取使得风险函数最小的分类判断作为决策。该决策可以表示为 $P _ { m | J }$ 的函数，即

$$
\begin{array} { r } { d _ { J } ( P _ { m | J } ) = \operatorname* { m i n } \bigr \{ \mathbb { E } _ { \theta } \bigl [ l ( \theta , m ) | Y _ { i J } \bigr ] , \mathbb { E } _ { \theta } \bigl [ l ( \theta , n ) | Y _ { i J } \bigr ] \bigr \} . } \end{array}
$$

在 $j < J$ 时，还需要考虑继续作答的损失。此时，根据上式就可以依次迭代，得到测验在达到最大长度之前继续作答的期望损失。比如，如图3所示，对于二级计分的题目，在 $j =$ $J - 1$ 时，被试分别以 $P _ { 0 | J - 1 }$ 和 $P _ { 1 | J - 1 }$ 的概率答错或答对下一题（第J题）。被试作答第J题后，由于达到最大测验长度，只需要做出分类决策而不需要继续作答，所以此时的风险函数就如同等式（20）。

![](images/690df69e6575f826d603290b4f8f110414edb50f2873850ab3372a47261570e1.jpg)  
图3在第/-1题时要求被试继续作答的损失 (以二级计分题为例)

于是，在 $j = J - 1$ 时要求被试继续作答的期望损失就可以用预期被试作答到第J题时的风险函数表示，即

$$
{ \mathbb E } _ { \theta } \big [ l ( \theta , c ) | Y _ { i , J - 1 } \big ] = \sum _ { s = 0 } ^ { 1 } P _ { s | J - 1 } \cdot d _ { J } \big ( P _ { m | J } \big ) = P _ { 0 | J - 1 } \cdot d _ { J } \big ( P _ { m | J _ { 0 } } \big ) + P _ { 1 | J - 1 } \cdot d _ { J } \big ( P _ { m | J _ { 1 } } \big ) ,
$$

其中， $\scriptstyle { c }$ 表示对考生的判断为需要继续做答， $P _ { m | J _ { 0 } }$ 和 $P _ { m | J _ { 1 } }$ 分别表示被试在第/道题上作答为0 或1时被判断为掌握类别的后验概率，其计算按公式（19）进行。由此，在 $j = J - 1$ 时的决策可记为，

$$
\begin{array} { r } { d _ { J - 1 } \big ( P _ { m | J - 1 } \big ) = \operatorname* { m i n } \bigl \{ \mathbb { E } _ { \theta } \big [ l ( \theta , m ) | Y _ { i , J - 1 } \big ] , \mathbb { E } _ { \theta } \big [ l ( \theta , n ) | Y _ { i , J - 1 } \big ] , \mathbb { E } _ { \theta } \big [ l ( \theta , c ) | Y _ { i , J - 1 } \big ] \bigr \} . } \end{array}
$$

根据上式就可以对被试进行分类判断。具体地说，系统将选择使得期望损失最小的决定（将被试划分为掌握，未掌握或要求继续作答），即

$$
\{ \begin{array} { l l } { | \widehat { \Xi } | . \mathrm { E i } | | \widehat { \underline { { u } } } | | \widehat { \underline { { u } } } \rangle , K = j ^ { \prime } , D = m \qquad } &  \begin{array} { l } { \quad \widehat { \Xi } | \mathbb { E } _ { \theta } \bigl [ l ( \theta , m ) | Y _ { i , j - 1 } \bigr ] \stackrel { \mathrm { E i } } { \Sigma \mathcal { U } } / \bigr ] \times } \\ { | \widehat { \Xi } |  { \mathrm { E i } } |  { \mathrm { E i } } |  { \mathrm { E i } } \rangle , K = j ^ { \prime } , D = n \qquad } & { \begin{array} { l } { \quad \widehat { \Xi } | \mathbb { E } _ { \theta } \bigl [ l ( \theta , n ) | Y _ { i , j - 1 } \bigr ] \stackrel { \mathrm { E i } } { \Sigma \mathcal { U } } / \bigr ] \times } \\ { \quad \widehat { \Xi } | \mathbb { E } _ { \theta } \bigr [ l ( \theta , n ) | Y _ { i , j - 1 } \bigr ] \stackrel { \mathrm { E i } } { \Sigma \mathcal { U } } / \bigr ] \times } \end{array}  } \\ { \langle \widehat { \Xi } | \mathbb { E } \widehat { \Xi } \rangle \langle \hat { \Xi } |  { \mathrm { E i } } | | \widehat { \Xi } | \rangle . } \end{array}  \end{array}
$$

以此类推，就可以得到在 $j = j ^ { \prime }$ 时被试继续作答的期望损失，并选择使得期望损失最小

的决定完成对被试的判断。

（2）多分类的阈值损失规则

对于贝叶斯规则而言，从二分类到多分类的推广比较简单。对于一个三分类的UCCT，只需要将表1中的阈值损失函数替换为表2中内容，再选择最小的损失即可完成对被试的分类判断（Vos,1999）。

表2阶段j'的三分类阈值损失函数  

<html><body><table><tr><td>决策</td><td>θ≤01</td><td>01u<θ<02l</td><td>0≥02u</td></tr><tr><td>被试属于“类别1”</td><td>j'lc</td><td>l12+j'lc</td><td>l13+j'lc</td></tr><tr><td>被试属于“类别2”</td><td>l21+ j'lc</td><td>j'lc</td><td>l23+ j'lc</td></tr><tr><td>被试属于“类别3”</td><td>l31+j'lc</td><td>l32+j'lc</td><td>j'c</td></tr></table></body></html>

# 3.2线性损失

表1中的阈值损失函数具有一个明显的缺点：它假定对于不同能力值的被试的损失是恒定的，而不考虑这些被试能力值与分界分数的距离。但事实上，能力值离分界分数更远的被试被错误分类所造成的损失往往更严重。此外，阈值损失函数的值也不是连续变化的，这在很多情况下也不符合现实。因此，一种更合理的假设是：损失函数是关于能力与分界分数间距离的连续增函数（van derLinden&Mellenbergh,1977; van derLinden& Vos,1996; Vos,1997a,1997b）。

# （1）二分类的线性损失规则

Van derLinden 和Mellenbergh（1977）在二分类情境下，提出一种线性损失函数，如表3所示。可以发现，相比于阈值损失，线性损失使得决策成本可以随“能力值θ离分界分数$\theta _ { 0 }$ 的距离”的变化而线性变化。

表3阶段j'的二分类线性损失函数  

<html><body><table><tr><td>决策</td><td>0=0</td><td>θ=0u</td></tr><tr><td>被试属于“未掌握”</td><td>j'lc</td><td>b1(00-0)+j'lc</td></tr><tr><td>被试属于“掌握”</td><td>b2(0。-0)+j'lc</td><td>j'lc</td></tr></table></body></html>

其中，斜率 $b _ { 1 }$ 与 $b _ { 2 }$ 是由有经验的专家确定。在给定损失函数后，就可以按照后验概率得到损失最小的决策，从而完成对被试的分类。

# （2）多分类的线性损失规则

与阈值损失函数类似，在多分类情境下，只需要将表3中的线性损失函数替换成表4中的内容即可得到一种三分类的线性损失函数（Vos,1999）。

表4阶段j'的三分类线性损失函数  

<html><body><table><tr><td>决策</td><td>0≤01</td><td>01u<θ<02l</td><td>0≥02u</td></tr><tr><td>被试属于“类别1”</td><td>j'lc</td><td>b1(0-01)+j'lc</td><td>b1(0-0)+j'lc</td></tr><tr><td>被试属于“类别2”</td><td>b2(10-0*|-0')+j'lc</td><td>j'lc</td><td>b2(10-0*|-0')+j'lc</td></tr><tr><td>被试属于“类别3”</td><td>b(0-0)+j'lc</td><td>b(0-0)+j'lc</td><td>j'lc</td></tr></table></body></html>

其中， $\theta ^ { * } = ( \theta _ { 2 } + \theta _ { 1 } ) / 2$ ， $\theta ^ { \prime } = ( \theta _ { 2 } - \theta _ { 1 } ) / 2$ 0

# 3.3 贝叶斯规则简评

贝叶斯规则所提供的思路与似然比规则的完全不同。似然比规则是通过构造似然比统计量进行假设检验，贝叶斯方法则是通过作答更新被试能力的后验分布，并使用后验概率计算损失函数值，从而基于贝叶斯决策论完成对被试的判断。

需要指出的是，在贝叶斯规则中，有无数种可能的损失函数，没有哪一种损失函数一定是最好的。这一特点既是贝叶斯规则最大的优点，也是其饱受诟病的一点。支持者认为这使得该方法能够考虑多样的损失函数，具有更大的灵活性；但是，反对者认为损失函数的选择具有一定程度的任意性。在使用该方法之前，研究者需要考虑清楚如何客观、科学地选择需要的损失函数。

# 4置信区间规则

除似然比规则和贝叶斯规则外，CCT 终止规则中还有一种是ACI方法。ACI方法通过比较分界分数与“被试能力估计值的置信区间”的相对位置，来完成对被试的分类判断。

# 4.1置信区间规则介绍

目前，对于这种方法的研究较少且集中在二分类的UCCT中。值得注意的是，ACI中所涉及到的被试能力估计，既可以使用极大似然估计也可以使用贝叶斯估计。具体而言，如果使用极大似然估计，则通过测量标准误（Standard Error of Measurement, SEM）构造置信区间；如果使用贝叶斯估计，则使用贝叶斯后验方差的平方根构造置信区间。分类测验过程中，不断更新的被试i的能力估计值的置信区间可以表示为，

$$
\hat { \theta } _ { i } - z _ { \epsilon } \times \delta _ { e r r o r } < \theta < \hat { \theta } _ { i } + z _ { \epsilon } \times \delta _ { e r r o r } ,
$$

其中， $z _ { \epsilon }$ 为 $( 1 - \epsilon )$ 的置信区间所对应的标准正态分布分位数， $\epsilon = \alpha + \beta$ 为两类错误率之和，$\delta _ { e r r o r } \$ 表示对能力的极大似然估计中的 SEM或贝叶斯估计中后验方差的平方根。例如，如果设置第I类、第ⅡI类错误率均为0.025，那么 $\epsilon$ 为0.05，这时 $\mathbf { \sigma } _ { z _ { \epsilon } }$ 等于1.96。在极大似然估计中，SEM根据被试i的所有已作答题目的Fisher信息量计算，即

$$
S E M = \frac { 1 } { \sqrt { \Sigma _ { j = 1 } ^ { j ^ { \prime } } I _ { i j } } } ,
$$

其中， $I _ { i j }$ 表示题目 $j$ 为被试i提供的Fisher信息量，对 $j ^ { \prime }$ 道题目的信息量求和即得到该被试在已作答的j'道题目上的总信息量。Thompson（2011）的研究指出，有两种方式可以实现等式（25）的计算：一是理论最大值的 SEM；二是观察分数的 SEM。根据被试已作答题目所组成的测验，理论最大值的SEM是在被试能力所有可能取值的范围内每隔一定步长（比如，在[-3,3]的区间内每隔0.01）计算一个的 SEM，并取其最大值；观察分数的 SEM则是在被试的能力估计值处，计算 SEM。简小珠和陈平（2020）指出，在大多数研究中都使用观察分数的 SEM进行计算。

得到置信区间 $\left[ \widehat { \theta } _ { i } - z _ { \epsilon } \times S E M , \widehat { \theta } _ { i } + z _ { \epsilon } \times S E M \right] .$ 后，ACI方法的分类准则如下：如果分界分数低于该区间的下界（即 $\widehat { \theta } _ { i } - z _ { \epsilon } \times S E M )$ ，那么停止测验，测验长度为j'，并判断被试属于“未掌握”；如果分界分数高于该区间的上界（即 $\widehat { \theta } _ { i } - z _ { \epsilon } \times S E M )$ ），那么停止测验，测验长度为j'，并判断被试属于“掌握”；否则就继续进行测验。

# 4.2置信区间规则简评

在某种程度上，可以认为ACI方法将被试的分类问题转化为被试的能力估计问题。这样做的好处是使得对被试的分类变得非常直观、简洁。但是，这种方法的稳健性相对较差。因为使用该方法需要有足够大的标定题库作为前提，否则就可能会导致较高的错误率。同时，Eggen 和 Straetmans（2000）以及Thompson（2009）的研究都表明：该方法所需的测验长度一般高于似然比规则。

# 5 三类终止规则的综合分析

# 5.1三类终止规则的构造思路与优缺点分析

综上所述，三类终止规则各有优缺点。其中，似然比规则基于似然比检验，具有较好的理论性质，大多数测验情境下最为准确、高效，相关研究也较多。但是，由于需要定义无差别区间大小和第I、第Ⅱ类错误率，引入了主观因素的影响，并且该方法在多维、多分类等复杂测验情境下的拓展难度较大。已有的多分类 SPRT终止规则（Sobel-Wald方法与Armitage方法）是对多个能力分界点独立进行假设检验，因此会隐含多重比较的问题，即实际的第I和第ⅡI类错误率远大于设定标准。尽管已有研究者留意到这一点（Wang,2019;Wang et al,2021），但由于第I和第II类错误率的变化并不是影响 SPRT 规则的分类准确性的主要因素，所以较少有研究对其进行校正。

贝叶斯规则通过后验概率与损失函数，完成对被试的分类判断。该方法无需事先给定第I和第ⅡI类错误率，它以更全局的角度动态优化决策，从测验最后的阶段向前倒推，因此每一步的损失判断都能考虑到整个测验过程。损失函数的多样性使得该方法的形式非常灵活，也使得该方法很容易就可以被应用于不同的测验情境中。但是，该方法也存在一定问题：(1)当结合 IRT 模型时，从后向前的损失函数计算量会变得十分巨大，不利于该方法的实施；（2）正如公式（19）所示，已有的贝叶斯方法在计算“下一道题得到特定作答的概率，即（204 $P \Big ( Y _ { i , j ^ { ' } + 1 } = s \Big | \theta _ { l } \Big ) .$ 或膚 $P \left( { Y } _ { i , j ^ { ' } + 1 } = s \Big | \theta _ { u } \right) ^ { , }$ 时使用的是在题库所有题目上的概率的平均值（即认为每道题目在下一阶段具有同等地位），这显然不符合自适应的特性；（3）损失函数形式的灵活会不可避免地导致使用者在损失函数的选择上产生疑问，也可能会在实际应用中产生由于损失函数选取不恰当而导致的误差。

ACI方法直接将分界分数与能力估计值的置信区间进行比较，无需划定无差别区间，并且计算简单且计算量小，是三种方法中最直接的一类方法。但是，这种方法的稳健性较差，测验效率也相对较低。表5是对上述各种方法的总结。

表5CCT终止规则的总结  

<html><body><table><tr><td>核心原理</td><td>类别数</td><td>维度数</td><td>终止规则</td><td>构造思路</td></tr><tr><td colspan="5">似然比规则</td></tr><tr><td>序贯似然比</td><td>二分类</td><td>单维</td><td>SPRT</td><td>在分界点处构造一组简单假设及对应的序贯似</td></tr><tr><td rowspan="10">广义似然比</td><td rowspan="5"></td><td rowspan="3">多维</td><td></td><td>然比统计量</td></tr><tr><td>SCSPRT</td><td>在 SPRT的基础上结合随机缩减技术</td></tr><tr><td>C-SPRT</td><td>通过似然函数约束转化为SPRT</td><td></td></tr><tr><td></td><td>P-SPRT</td><td>通过欧氏空间投影转化为SPRT</td></tr><tr><td rowspan="2">多分类</td><td>M-SCSPRT</td><td></td><td>在C-SPRT的基础上结合随机缩减技术</td></tr><tr><td>单维</td><td>Sobel-Wald 方法</td><td>在每个分类点处进行一次SPRT</td></tr><tr><td rowspan="3">二分类</td><td>单维</td><td>Armitage方法 GLR</td><td>为所有可能的类别组合进行 SPRT 在分界点处构造一组复杂假设及对应的广义似</td></tr><tr><td></td><td></td><td>然比统计量</td></tr><tr><td>多维</td><td>M-GLR SCGLR</td><td>将GLR中的能力区间转化为多维能力空间 在GLR的基础上结合随机缩减技术</td></tr><tr><td rowspan="3">多分类</td><td>单维</td><td></td><td></td></tr><tr><td></td><td>mGLR</td><td>对被试属于每个类别构造一组复杂假设及对应</td></tr><tr><td></td><td></td><td>的广义似然比统计量</td></tr><tr><td colspan="6">贝叶斯规则</td></tr><tr><td rowspan="4">阈值损失 线性损失</td><td>二分类</td><td>单维</td><td>Lewis-Sheehan方法</td><td>确定每种决策所对应的损失</td></tr><tr><td>多分类</td><td></td><td>Vos方法</td><td>确定每种决策所对应的损失</td></tr><tr><td>二分类</td><td></td><td>Linden-Mellenbergh方</td><td>确定每种决策所对应的损失，并考虑能力估计</td></tr><tr><td></td><td>法</td><td></td><td>值与分界点的距离</td></tr><tr><td rowspan="3"></td><td rowspan="3">多分类</td><td></td><td></td><td></td></tr><tr><td></td><td>Vos方法</td><td>确定每种决策所对应的损失，并考虑能力估计</td></tr><tr><td></td><td></td><td>值与分界点的距离</td></tr><tr><td colspan="6">置信区间规则</td></tr><tr><td rowspan="3">置信区间</td><td rowspan="3">二分类</td><td rowspan="3">单维</td><td>ACI</td><td></td></tr><tr><td></td><td>比较能力估计值的置信区间与分界点的相对位</td></tr><tr><td></td><td>置</td></tr></table></body></html>

# 5.2三类终止规则的适用情境

需要指出的是，CCT是一个非常复杂的测验系统。终止规则的优劣还会受到CCT 中其他部分（比如，心理测量模型、题库结构、被试能力分布以及选题策略）的影响，三类终止规则在不同的测验情境下各占鳌头。因此，实践者在选择终止规则时需要综合考虑CCT 的各个部分以明确三类终止规则的适用情境。另外，还需要注意相应情境下可能面临的现实问题。

对于似然比规则，想要准确且快速做出决策的关键在于最大程度地区分不同类别被试的似然函数值，而这通常和选题策略密切相关。举例而言，在UCCT中，两种常见的选题策略是基于能力估计值的最大信息量选题方法（estimate-based maximumFisher information）和基于分界分数的最大信息量选题方法（cutscore-based maximumFisher information）。因此，当选题策略为后者时，所选的题目能够为假设检验提供更多的信息，因此似然比规则在基于分界分数的最大信息量选题方法下的效率最高。但是由于基于分界分数会因为固定点选题而导致题目高曝光的问题，所以似然比规则更适用于低风险的测验，而且要求题库中大部分题目在分界分数处具有高信息量。此外，由于GLR考虑无差别区间两侧的所有对数似然函数值（不仅着眼于上、下界两个点），所以相比于 SPRT，GLR在基于当前能力估计选题时也能保持一定的效率。

对于贝叶斯规则，高效分类的关键在于最大程度地区分不同决策损失的差异。由于不同决策损失函数的计算同样基于 $\theta _ { l }$ 和 $\theta _ { u }$ ，所以在基于分界分数的选题方法下会有更好的表现。同样，考虑到题目曝光率的问题，贝叶斯方法更适用于低风险的测验。另外，由于贝叶斯方法能够针对不同的决策损失进行控制，所以适用于需要降低特定类型决策损失的测验。

对于置信区间规则，保障决策效率的关键在于不断地减小能力估计标准误。因此，ACI方法在基于能力估计值的最大信息量选题方法下的效率最高，该选题策略可以减小置信区间的大小。此外，根据不同被试的能力，ACI规则能够为不同被试呈现不同的题目，在一定程度上能降低高信息量题目的曝光率，所以它可以用于高风险的测验，相应地需要题库中的题目在不同能力位置具有高信息量。但是Tian（2018）在控制分类准确性一致的前提下，采用基于能力估计值的选题方法，比较单维二分类的似然比规则和置信区间规则。结果发现：当被试能力分布远离分界分数时，ACI规则的效率要高于似然比规则；但是在被试能力分布靠近分界分数时，ACI规则效率低于GLR方法。这意味着ACI规则的表现还会受到被试能力分布与分界分数相对位置的影响，因此更适用于要求高通过率或低通过率的测验。

# 6 未来研究方向及应用

# 6.1CCT终止规则的未来研究方向

本文对多种测验情境下的CCT终止规则进行系统梳理与述评。目前，对CCT终止规则的研究已经比较丰富，但仍有一些地方有待完善。未来研究方向主要表现在以下四方面：

（1）完善基于贝叶斯的终止规则。构建CCT终止规则的思路主要有三个角度，即似然比方法、贝叶斯方法和置信区间方法。基于似然比方法的终止规则已经得到充分的发展，但如前所述，以贝叶斯方法为基础的终止规则仍然较少。未来，研究者可以考虑基于贝叶斯方法对前人研究进行完善。例如，在现实测验情景中，除考虑决策的准确率和测验长度之外，还需要满足其他非统计约束（如：内容均衡，即让试卷充分涵盖所要考察的知识模块）。由于贝叶斯损失函数具有灵活性，研究者可以考虑将各种非统计约束纳入终止规则的考虑范围。

此外，正如5.1部分所言，目前贝叶斯方法没有利用已有的信息对被试即将作答的下一道题进行预测，未来研究可以借鉴似然比方法中随机缩减的思想来构造一组“合适”的题目替代被试未来实际作答的题目。最后，研究者还可以对损失函数中损失值的选取如何影响测验结果进行讨论。

（2）开发多维多分类的CCT终止规则。多维或多分类的CCT终止规则是近期的一个研究热点，但尚未有研究者探究同时满足多维、多分类要求的CCT终止规则。在现实应用中，许多测验不仅要同时考察被试在多个维度上的潜在特质，而且也需要将被试分到多于两个的类别中。例如，教育工作者希望将学生的数学成就水平划分为基础、熟练和高级三个类别（比如，美国国家进步教育评估NAEP）；而数学测验也往往同时考察学生的算术、阅读和问题解决能力等，呈现出多维的能力结构（Reckase,2009）。这就对构建多维、多分类的CCT 终止规则提出迫切需求。

（3）开发融合作答时间（Response Time,RT；詹沛达 等,2020）的CCT终止规则。近几年来，心理测量学的研究重点大都放在如何同时衡量多个维度的潜在特质，以向被试提供更详细、更完善的反馈。但是这些研究大多只考虑被试的作答信息，而很少使用行为信息。在CCT测验中，有一类很容易获得的行为信息，即被试作答所用的时间。Sie等人（2015）尝试构建融入RT的CCT，他们的研究结果表明：融入RT后，测验在分类精度轻微提高的同时还能够减少平均测验时间。但是，Sie等人（2015）的研究主要集中在限制被试作答时间，而未考虑更普遍的限制测验长度的情况。未来，研究者可以在上述研究的基础上进一步展开探索，开发新的结合RT的CCT终止规则，在保持判断准确率的基础上缩短测验长度，而不仅仅是控制测验时间。另外，可以考虑如何利用作答时间提高分类决策的精度，进而间接提高测验效率（Man et al.,2019；詹沛达,2019）。

（4）开发结合机器学习算法的CCT终止规则。目前的三类终止规则均为基于心理测量模型的方法，模型的正确设定和前提假设的满足对结果有重要的影响，然而实践中的数据往往掺杂着各式各样的噪音。机器学习是近年来各个领域研究的热点，其中许多算法都是用来解决分类问题，这与CCT的目的相一致。Gonzalez（2021）认为，相比于比较“通过各种模型估计得到的被试能力”与“黄金标准”来获得被试的类别，机器学习算法通过被试的作答就能直接预测被试属于某个类别的概率，避免模型不拟合等引起的误差。Zheng 等人（2020)基于机器学习算法中的决策树方法，开发出一个短的基于树的自适应分类测验。未来，研究者可以考虑使用其他的分类算法(比如，逻辑斯蒂克回归、支持向量机以及随机森林等方法)完成自适应分类测验。

# 6.2CCT终止规则的应用

CCT 测验主要包含两种类型：合格性测验与临床医学问卷。在为不同类型的测验制定终止规则时，应充分考虑测验的考生群体、试题特点以及决策影响。

在合格性测试中，通过设置不同难度的试题，将考生划分到不同能力水平，根据考生的等级水平，来决定其从业资格、学业进度或升学。许多职业资格考试都属于这类测验，比如教师资格考试、司法考试和执业医师资格考试等；此外，还有一些学业水平考试也属于合格性测验，比如大学英语四、六级考试、计算机二级考试以及初中学业水平测试等。对于此类测验，往往每年均有数量庞大的考生群体，具有充足的测验经费和考生样本，相应地能够建立起一定规模的题库，并在一定程度上能保障题目参数的稳定估计，使得合格性测验具有运用三类终止规则的潜力。但是，似然比规则与贝叶斯规则的原理较为复杂，且正如5.2部分所言，这些方法在实践中伴随着题目曝光率过高的问题。因此，在现有的合格性测验尤其是高风险的合格性测验中，鲜有这两类方法的应用。与上述两种规则的困境形成对比的是，置信区间规则原理简明易懂、分类结果清晰，更能为大众和教育工作者所理解，更具有推广性，在现实中就显得更加可行。比如，美国联合委员会注册护士执照考试（the NationalCouncilLicensure Examination for Registered/Practical Nurse,NCLEX-RN）就使用 ACI 规则来决定测验何时终止。

在临床医学问卷中，通过评价患者在不同指标上的轻重程度或近期的心理生理状态，将患者划分到不同症状水平，来为其后续的治疗和诊断提供依据。比如，汉密尔顿抑郁量表（Hamilton Rating Scale for Depression,HRSD）和创伤后应激障碍量表（Postraumatic StressDisorderChecklist,PCL）。对于此类测验，被试群体往往很小，且问卷的题项并不具有一般意义上的难度。更重要的是，假阴性（false negative）的分类结果所带来的代价不可忽视。因此，考虑到相比于另外两类终止规则，贝叶斯终止规则能够对各种分类损失有更精细的控制，在临床医学问卷中更为适用。目前，终止规则在临床医学问卷中的应用目的主要为：在保证决策准确基础上缩短已有问卷的长度，使得诊断过程更高效，比如利用机器学习模型或随机缩减技术进一步缩减问卷长度（Gonzalez,2021; Smits et al.,2016）。还需要注意的是，临床问卷以往直接使用观测分数与诊断临界值相比较，而已有的终止规则主要基于潜在特质进行计算。但随着IRT研究的推进，越来越多的研究者使用IRT模型对临床问卷建模，比如Li等人（2019）将等级反应模型（GradedResponseModel,GRM）应用于病人健康问卷（thePatient HealthQuestionnaire,PHQ）。因此，相比于 Smits 等人（2016）使用基于观测分数的CCT并选择随机缩减的倒计时法（countdownmethod）作为终止规则，贝叶斯规则或许既能够缩短测验长度，又能在每一步中严格控制诊断的损失。

# 参考文献

陈平.(2016)．两种新的计算机化自适应测验在线标定方法．心理学报,48,1184-1198.   
简小珠，陈平.(2020).计算机化分类测验的特点与发展述评．考试研究,83,77-89.   
康春花，辛涛.(2010).测验理论的新发展:多维项目反应理论．心理科学进展,18,530-536.   
任赫，陈平.(2021).两种新的多维计算机化分类测验终止规则．心理学报,53,1044-1058.   
詹沛达.(2019).计算机化多维测验中作答时间和作答精度数据的联合分析．心理科学,42,170-178.   
詹沛达,Hong Jiao,Kaiwen Man.(2020).多维对数正态作答时间模型：对潜在加工速度多维性的探究．心理 学报,52,1132-1142.   
Armitage,P. (195o).Sequential analysis with more than two alternative hypotheses,and its relation to discriminant function analysis.Journal of the Royal Statistical Society, Series B,12,137-144.   
Bartroff,J.Finkelman,M.,&Lai,T.L. (2oo8). Modern sequential analysis and itsapplications tocomputerized adaptive testing. Psychometrika, 73,473-486.   
Eggen,T. J.H.M. (199). Item selection in adaptive testing with the sequential probability ratio test.Applied Psychological Measurement, 23,249-261.   
Eggen,T. J.H. M,& Straetmans, G. J. J. M. (2oo0). Computerized adaptive testing for classifying examinees into three categories.Educational and Psychological Measurement, 60,713-734.   
Ferguson, R.L. (1969). Computer-asisted criterion-referenced measurement (Working Paper No.41).Pitsburgh, PA: University of Pittsburgh, Learning and Research Development Center.   
Finkelman, M. (2003).An adaptation of stochastic curtailment to truncate Wald's SPRTin computerized adaptive testing (CSE Report 606).Los Angeles,CA: National Center for Research on Evaluation, Standards,and Student Testing.   
Finkelman, M.(008). On using stochastic curtailment to shorten the SPRT in sequential mastery testing.Journal of Educational and Behavioral Statistics,33,442-463.   
Finkelman, M. (2010). Variations on stochastic curtailment in sequential mastery testing. Applied Psychological Measurement, 34,27-45.   
Finkelman,M.,He,Y.,Kim,W.,&Lai,A.M. (20l1).Stochasticcurtailment of health questionnaires: A method to reduce respondent burden.Statistics in Medicine,30,1989-2004.   
Ghosh,B. K.(1970). Sequential tests of statistical hypotheses. Reading, MA: Addison-Wesley.   
Ghosh,B.K.,& Sen,P.K.(1991). Handbook of sequential analysis.New York,NY: Marcel Dekker.   
Gonzalez,O.(2O21).Psychometric and machine learning approaches for diagnostic assssment and tests of individual classification.Psychological Methods,26,236-254.   
Govindarajulu,Z.(1987).The sequential statistical analysisof hypothesis,testing,point and interval estimation, and decision theory (American series in mathematical and management sciences). Columbus, OH: American Sciences Press, Inc.   
Huang,C.-Y.,Kalon,J.C.,in,C.-J.,&pray,J.().Estmatingitemparametersfromclassicalindicsote pool development with a computerized classification test (Research Report 20o0-4). Iowa City,IA: ACT, Inc.   
Huebner, A.R.,& Fina,A.D. (2O15).The stochastically curtailed generalized likelihood ratio: A new termination criterion for variable-length computerized classification tests.Behavior Research Methods,47,549-561.   
Kingsbury,G. G.,& Weis,D.J. (1983). A comparison of IRT-based adaptive mastery testing and a sequential mastery testing procedure.In D. J. Weiss (Ed.)， New horizons in testing: Latent trait test theory and computerized adaptive testing (pp. 257-283). New York: Academic Press.   
Lewis, C.,& Sheehan, K. (1990). Using Bayesian decision theory to design a computerized mastery test. Applied Psychological Measurement, 14,367-386.   
Li, C.,Moore,S.C.Smith,J.,Bauermeister,S.,&Gallacher,J. (2l9).Thecostsofnegative affectatributableto alcoholconsumption in later life: A within-between random longitudinal econometric model using UK Biobank. PLOS ONE,14,Article e0211357. https://doi.org/10.1371/journal.pone.0211357   
Nydick,S. (2013). Multidimensional mastery testing with CAT (Unpublished doctoral dissrtation). Universityof Minnesota.   
Man,K.,Harring,J.R.,Jiao,H.,& Zhan,P.(2019). Joint modeling of compensatory multidimensional item responses and response times. Applied Psychological Measurement, 43, 639-654.   
Reckase, M.D. (1983). A procedure for decision making using tailored testing. InD. J. Weiss(Ed.), New horizons in testing: Latent trait test theory and computerized adaptive testing (pp.237-257). New York: Academic Press.   
Reckase, M. (2009). Multidimensional item response theory. New York, NY: Springer.   
Seitz,N.-N.,&Frey,A.(2Ol3).The sequential probability ratio test for multidimensional adaptive testing with between-item multidimensionality. Psychological Test and Assessment Modeling,55,105.   
Sie,H.,Finkelman, M.D.,Riley,B.,& Smits,N. (015). Utilizing response times in computerized clasification testing. Applied Psychological Measurement, 39,389-405.   
Smits,N.,& Finkelman, M. D. (2013). A comparison of computerized classification testing and computerized adaptive testing in clinical psychology. Journal of Computerized Adaptive Testing, 1,19-37.   
Smits,N.,Finkelman,M.D.,& Kelderman, H. (2O16).Stochastic curtailment of questionnaires for three-level classification: Shortening the CES-D for assessing low,moderate,and high risk of depression. Applied Psychological Measurement, 40,22-36.   
Sobel,M., & Wald,A. (1949). Asequential decision procedure for choosing one of three hypotheses concerning the unknown mean of a normal distribution. Annals of Mathematical Statistics,20,502-522.   
Spray, J.A. (1993). Multiple-category classification using a sequential probability ratio test (ACTResearch Report Series,No. 93-7). Iowa City, IA: Americn Colege Testing.   
Spray,J. A.，& Reckase, M. D. (1996). Comparison of SPRT and sequential Bayes procedures for clasifying examinees into two categories using acomputerized test.Journal of Educational and Behavioral Statistics, 21, 405-414.   
Tartakovsky,A., Nikiforov,I.,& Bassevile,M. (2014).Sequential analysis: Hypothesis testingand changepoint detection. Boca Raton, FL: Chapman and Hall/CRC.   
Thompson, N.A. (2oo9). Item selection in computerized classification testing. Educational and Psychological Measurement, 69,778-793.   
Thompson， N.A. (2011). Termination criteria for computerized classification testing.Practical Assessment, Research,& Evaluation, 16,1-7.   
Tian, C.(2018). Comparison offour stopping rules in computerized adaptive testing and examination of their application to on-the-fly multistage testing (Unpublished master's thesis). University of Illinois.   
van der Linden, W. J., & Melenbergh, G. J. (1977). Optimal cutting scores using a linear loss function. Applied Psychological Measurement, 1, 593-599.   
van der Linden, W. J.,& Vos, H. J. (1996). A compensatory approach to optimal selection with mastery scores. Psychometrika,61,155-172.   
van Groen, M.M.,Eggen,T.J.,& Veldkamp,B.P. (2014). Item selection methods based on multiple objective approaches for clasifying respondents into multiple levels. Applied Psychological Measurement,38,187-200.   
Vos,H. J. (1997a).Simultaneous optimization of quota-restricted selection decisions with mastery scores. British Journal ofMathematical and Statistical Psychology,50,105-125.   
Vos,H.J. (1997b).A simultaneous approach to optimizing treatment asignments with mastery scores. Multivariate Behavioral Research,32,403-433.   
Vos,H.J.(199).Applications of Bayesian decision theory to sequential mastery testing.Journal of Educational and Behavioral Statistics,24,271-292.   
Wald,A.(1947). Sequential analysis.New York,NY: John Wiley.   
Wald,A.，& Wolfowitz,J.(1948). Optimal character of the sequential probability ratio test.The Annalsof Mathematical Statistics,19,326-339.   
Wang, C., Chen,P.,& Huebner,A. (2021). Stopping rules for multicategory computerized clasification testing. British JournalofMathematical and Statistial Psychology，74,184-202.   
Wang,Z.(2019).Grid multi-clasification adaptive classification testing with multidimensional polytomous items (Unpublished doctoral dissertation).University ofMinnesota.   
Zhan,P.,Jiao,H.,Man,K.,Wang,W.C.,& He,K. (2021).Variable speed across dimensions of ability in the joint model forresponsesand responsetimes.Frontiersinpsychology，12， Article 469196. https://doi.org/10.3389/fpsyg.2021.469196   
Zheng,Y.,Cheon,H.,& Katz, C.M. (2020). Using machine learning methods to developa short tre-based adaptive classification test: Case study with a high-dimensional item pool and imbalanceddata.Applied Psychological Measurement,44,499-514.https://doi.org/10.1177/0146621620931198

# Types, characteristics and application of Termination Rules in Computerized Classification Testing

REN He, HUANG Yingshi, CHEN Ping (Collaborative Innovation CenterofAssessment forBasic EducationQuality,Beijing Normal University Beijing 100875,China)

Abstract: Computerized classification testing (CCT) has been widely used in eligibility testing and clinical psychology since it can efficiently classify participants. As an essential part of CCT, the termination rule determines when the test is to be stopped and what category the participants are ultimately classified into，directly affecting the test efficiency and classification accuracy. The existing termination rules can be roughly divided into the likelihood ratio,Bayesian decision theory, and confidence interval rules. And their core ideas are constructing hypothesis tests, designing loss functions,and comparing the relative positions of confidence intervals,respectively. Based on these ideas, in different test situations, CCT termination rules have various specific forms.Future research can further extend Bayesian rules,construct rules for multicategory MCCT, integrate process data into termination rules,and build rules under the framework of machine learning. In addition, from the perspective of practical requirement, all three types of rules have the potential to be applied in the eligibility test, while the clinical questionnaire tends to choose Bayesian rules.

Key words: computerized classification testing, termination rule, likelihood radio, stochastic curtailment,Bayesian decision theory