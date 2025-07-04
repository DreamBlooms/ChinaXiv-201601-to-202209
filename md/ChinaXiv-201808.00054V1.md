# 联合特征选择和潜在子空间回归的跨媒体检索\*

刘芸1，于治楼²，付强(山东师范大学 信息科学与工程学院，济南 250358)

摘要：由于多模式数据的大量存在，跨模式检索近来备受关注，并且通常涉及两个基本问题：相关性度量和特征选择。目前的大多数方法都只关注解决第一个问题：将多模态数据投影到一个公共子空间中，测量不同数据模式之间的相似性然后进行检索。针对第二个问题，为了可以从特征空间中选择相关和判别特征，对投影矩阵施加21范数惩罚项。同时，采用谱回归方法学习所有模态数据共享的最优潜在空间正交约束。然后构建一个图模型将多模态数据投影到潜在空间中，保留了模态内的相似性关系。在两个数据集进行了广泛的实验，跨模态检索任务的实验结果表明显示了本文提出的方法的有效性。

关键词：跨媒体检索；特征选择；子空间学习；谱回归 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.04.0333

Joint feature selection and latent subspace regression for cross-media retrieval

Liu Yun1, Yu Zhi Lou²†,Fu Qiang³ (Schoolof Information Science& Engineering Shandong Normal University,Jinan 25o358,China)

Abstract: Cross-modal retrieval has recentlydrawn much attention due tothe widespread existence of multi-modalitydata, generallyinvolves twobasic problems:the measureof relevance and coupled feature selection.However,mostof thecurent methods only focus on solving the first problem:To mappng multi-modality data intoa common subspace,in which the similaritybetween diferent modalitiesofdatacanbemeasured.The21-normpenalties are imposedonthe projectionmatrices separatelyto solve the second problem,which selects relevantand discriminative features from different feature spaces.Then this paperadopt thespectralregresion methodtolearn theoptimallatent space shared bydataofallmodalities basedon the orthogonal constraints.And thispaperconstruct a graph model to project he multi-modalitydata into thelatentspace,which preserves the intra-modality similarityrelationships.The paper conduct extensive experiments on two datasets.The experimental results of cross-modal retrieval show the method is effective.

Key words: cross-media retrieval; feature selection; subspace learning; spectral regression

# 0 引言

随着互联网技术的迅速发展，多模态数据（如图像、文本、视频或音频）已经在互联网上广泛使用。跨媒体检索的目的是将一种类型的数据作为查询来检索另一种类型的相关数据对象。例如，用户可以使用文本来检索相关图片（图1），或者通过提交有趣的图像作为查询来搜索相关的文字描述（图2）。跨模式检索使用户可以将任何形式的内容作为查询检索各种模态的数据，比单模态检索的结果更全面。

然而多模态数据通常有不同的特征空间，不同模态特征之间的异质差异是跨媒体检索任务的一项巨大的挑战。解决这个问题，最直接的方法是将不同模态的数据映射到一个共享空间，在共享空间中不同模态之间的相似性可以直接测量。典型相关分析（CCA）[I是最流行的方法，它寻找两组变量的最优基本向量建立相关性来学习潜在子空间。CCA可以表述如下：

$$
\begin{array} { l } { { m a x \ t r \ W _ { \uparrow } ^ { T } X _ { \uparrow } X _ { \ Z } ^ { T } W _ { \bar { Z } } \ \sigma _ { X } ^ { 2 } } } \\ { { W _ { \uparrow , } W _ { \bar { Z } } } } \\ { { s . \ t . \ W _ { \uparrow } ^ { T } X _ { \uparrow } X _ { \uparrow } ^ { T } W _ { \uparrow } = / { , } W _ { \bar { Z } } ^ { T } X _ { \bar { Z } } X _ { \bar { Z } } ^ { T } W _ { \bar { Z } } = / { \qquad } } } \end{array} \qquad ,
$$

其中： $w _ { \mathscr { I } }$ 和 $w _ { 2 }$ 代表每种模态特征的映射矩阵。

基于CCA，其他算法也被提出来处理不同模态问题，如偏最小二乘（PLS）[2]、双线性模型（BLM）[3]，它们也试图学习子空间来进行跨模态检索。

除了CCA、PLS和BLM之外，还有一些方法可用于解决跨模态问题。如，Mahadevan等人[4提出最大协方差展开，将来自不同输入模态的数据进行降维的流形学习算法。Mao等人[5]介绍了一种平行字段对齐检索的跨媒体检索方法，从矢量场的角度整合了一个流形对齐框架。Lin等人[提出了一种通用的判别特征提取（CDFE）方法来学习一个共同的特征子空间，其中散布矩阵内与散布矩阵之间的差异被最大化。Sharma7将线性判别分析（LDA）和边际Fisher分析（MFA）扩展到它们的多视图中，如广义多视图LDA（GMLDA）和广义多视图MFA（GMMFA），使用它们处理跨媒体检索问题.GMLDA和GMMFA考虑了语义类别，并且获得了较好的结果。

![](images/4414612d8e95f271b63e6556511359c20ec77cbe71b21a25a1f2bc177761bfef.jpg)  
图1文本检索图像

![](images/b0fb462cb3d2dafe48b0dca80d49a5da6bb75d82e59573cfaf66c9785f602e7d.jpg)  
图2图像检索文本

此外，Zhai等人[8进一步提出了联合表示学习（JRL）方法，联合使用成对关联和语义信息到一个统一的优化框架中。Zhuang等人[9提出了一个监督耦合词典学习算法，其目的是为跨媒体检索学习耦合词典。此外，Zhai等人[0]提出了异构度量学习方法，能够测量不同媒体类型之间的内容相似度。

受深度学习近期进展的启发，Ngiam等人[1]应用深度网络学习多种模态的特征，其重点是学习语音音频的表示，并与嘴唇的视频相结合。深度限制玻耳兹曼机器[12]成功地学习多模态数据的联合表示，它首先使用单独的模态友好的潜在模型来学习每个模态低维表示，然后融入到更高维度的深层架构中的联合表示中。受深度网络的表示学习的启发Andrew等人[13]提供了深度典型相关分析（DCCA），这是一种深度学习方法，可以学习不同形式的数据的复杂非线性投影，从而使得结果表示呈高度线性相关。

然而其中大多数主要集中在相关性度量上，耦合特征选择没有得到很好的解决。由于现实世界数据的维度往往很高，有多余和不相关的特征，所以选择不同模态数据的辨别特征很重要。

# 1 联合特征选择与潜在空间学习、回归

# 1.1潜在空间学习

根据式（1）可以发现，CCA试图将不同模态的特征投影到正交空间中使不同模态之间的相关性最大。在这方面，希望通过正交约束学习一个公共空间，而不是直接使用二进制标签空间。由于谱回归（SR）[14]在特征学习中有非常好的表现，并且图嵌入方法可以很好地表征局部关系，采用SR来学习潜在空间。本文首先构造一个图来获得模态内部之间的关系。对于有监督的检索任务，基于标签信息，权重矩阵W定义如下：

其中： $\boldsymbol { \mathscr { N } } _ { t }$ 代表第 $\mathbf { \Psi } _ { t }$ 类的样本数量。在学习的潜在子空间中，希望保持邻域关系并且属于同一类的样本应该共享相同的表示。$\boldsymbol { y } _ { j }$ 表示第 $\mathbf { \chi } _ { j }$ 个样本在学习的潜在空间中的表示。潜在空间学习的目标函数是

$$
m { \dot { \cal I } } n { \frac { \cal I } { 2 } } \sum _ { i , j } \left\| y _ { i } { - } y _ { j } \right\| _ { 2 } ^ { 2 } { \mathcal W } _ { i j } = t r { \cal Y } ^ { \bar { \cal I } } L { \cal Y } \quad \quad s . t . { \cal Y } ^ { \bar { \cal I } } { \cal Y } = { \cal I }
$$

其中： $L = D - W$ 是图拉普拉斯矩阵; $D$ 是对角矩阵，且 $D _ { i i } = \Sigma _ { j } W _ { i j }$ ，$\boldsymbol { Y } = \left[ y _ { 1 , } y _ { 2 , } \ldots y _ { n } \right] ^ { T }$ 。式（3）可以通过特征值分解解决。

# 1.2潜在空间回归与特征选择

1.2.1特征选择

特征选择旨在使用选择标准来定位一组最佳特征，通过保留一些原始特征，保持了原始特征的物理意义，并为模型提供了更好的可读性和可解释性。它是模式分析中广泛使用的一项重要技术。它通过消除不相关和多余的特性来降低数据的差异性，减少了存储和计算成本，提高学习的准确性，并有助于更好地理解学习模型或数据。因此，特征选择被视为有效的降维技术。

本文首先简要介绍一下这里使用的一些符号。对于矩阵（204号 $M \in { \mathfrak { R } } ^ { n * m }$ ， ${ { \mathbf { \mathit { m } } } _ { i } }$ 代表矩阵的第 $\mathbf { \chi } _ { j }$ 行， $m _ { j }$ 表示矩阵的第 $j$ 列。矩阵$\pmb { M }$ 的 $\boldsymbol { \mathsf { \Pi } } _ { F }$ 范式定义为： $\left. M \right. _ { F } = \sqrt { \sum _ { i = 1 } ^ { n } \left. m ^ { ' } \right. _ { 2 } ^ { 2 } } \mathrm { , ~ } \left. M \right. _ { 2 7 }$ 代表矩阵 $M$ 所有行2范式的和： $\| M \| _ { 2 7 } = \sum _ { i = 1 } ^ { n } \left\| m ^ { i } \right\| _ { 2 }$ 。

1.2.2 潜在空间回归与特征选择

假设给出了来自 $\boldsymbol { \mathscr { M } }$ 种模态的 $M$ 组特征，（204号 $X _ { p } = \ x _ { 1 } ^ { p } , x _ { 2 } ^ { p } , . . . , x _ { n } ^ { p }$ $\pmb { \operatorname { \mathscr { p } } } = 1 , \dotsc , \pmb { \mathscr { M } }$ ，其中在 $\chi _ { p }$ 中的特征是 $d _ { p }$ 维的， $\boldsymbol { n }$ （204号是样本的总数目。通常，在跨媒体检索任务中将 $M$ 设置为2,即图像与文本。给定潜在空间 $\gamma \in { \mathfrak { R } } ^ { n ^ { * } c }$ ，将每个样本回归到其低维嵌入。对于每个模态的特征 $\boldsymbol { \chi } _ { p } \in \boldsymbol { R } ^ { d _ { p } * _ { n } }$ ，想要学习映射矩阵矩阵 $U _ { p } \in \mathcal { R } ^ { d _ { p } * _ { c } }$ 将每个模态特征映射到公共空间。潜在空间回归的目标函数可以表示为$\underset { \ b { U } } { m } \overset { \ b { M } } { \ b { \sum } } \underset { p = \ b { \mathscr { I } } } { (  \ b { U } _ { p } ^ { T } \boldsymbol { X } _ { p } - \boldsymbol { Y } ^ { T }  _ { F } ^ { 2 } +  \beta  \boldsymbol { U } _ { p }  _ { \ b { 2 1 } } \ast \gamma \mathrm { t r } \ U _ { p } ^ { T } \boldsymbol { X } _ { p } \iota \boldsymbol { X } _ { p } ^ { T } \boldsymbol { U } _ { p } ) } \qquad 4$ 其中： $\beta$ 和 $\gamma$ 是平衡参数。式（4）中的回归问题可以看做是一个扩展的正则化最小二乘问题。

式（4）的第二项为特征选择，通过文献[15]中对21范式的分析，定义 $\textit { f x } = \sqrt { x ^ { 2 } + \varepsilon }$ ，使用 $\sum _ { i = 1 } ^ { d _ { p } } \mathcal { \epsilon } \Big ( \Big \| \omega _ { p } ^ { i } \Big \| _ { 2 } \Big )$ 代替 $\left\| \boldsymbol { U } _ { p } \right\| _ { 2 1 }$ ， $\varepsilon$ 是平滑项，通常被设置成一个很小的数值。可以证明 $\textit { f x } = \sqrt { x ^ { 2 } + \varepsilon }$ 满足以下所有条件：

然后,可以按照下面的引理1以半二次型方式[16]优化 $\textit { \textbf { f } } _ { X }$ 。

引理1设 $\textit { \textbf { f } } _ { X }$ 是满足式（5）中所有条件的函数，对于固定的 $\left\| u ^ { i } \right\| _ { 2 }$ ，存在一个双重潜在函数：

$$
\phi \Bigg ( ~ \left\| \ U ^ { \prime } \right\| _ { 2 } \Bigg ) = \operatorname * { \Pi } _ { s \in R } f _ { s } \Bigg \{ s ~ \left\| u ^ { \prime } \right\| _ { 2 } ^ { 2 } + \phi ~ s ~ \Bigg \} \qquad 6 \
$$

其中： $s$ 由最小化函数 $\phi \textbf { \em s }$ 决定。

根据引理1，式（4）中的目标函数可以重新表述如下：

$$
\underset { \ b { U } } { m } \underset { \ b { p } = \ b { f } } { \overset { M } { \sum } } \left( \left\| \ b { U } _ { p } ^ { T } \boldsymbol { X } _ { p } - \boldsymbol { Y } ^ { T } \right\| _ { \ b { F } } ^ { 2 } + \beta ~ t r ~ \boldsymbol { U } _ { p } ^ { T } \boldsymbol { R } _ { p } \boldsymbol { U } _ { p } + \gamma ~ t r ~ \boldsymbol { U } _ { p } ^ { T } \boldsymbol { X } _ { p } \iota \boldsymbol { X } _ { p } ^ { T } \boldsymbol { U } _ { p } \right)
$$

其中： $R _ { p } = D / a g \ r _ { p } ; r _ { p }$ 是 21 范式的附加向量，第i个元素$r _ { p } ^ { i } = 1 2 \left\| \boldsymbol { u } _ { p } ^ { i } \right\| _ { 2 }$ ， $r _ { p }$ 的元素规则化如下：

$$
r _ { p } ^ { j } = \frac { 1 } { 2 \sqrt { \left\| \mathbf { \epsilon } u _ { p } ^ { j } \right\| _ { 2 } ^ { 2 } + \varepsilon } }
$$

值得注意的是， $\left\| \omega _ { p } ^ { i } \right\| _ { 2 }$ 在理论上可以为零。但是不能将 $r _ { p } ^ { i }$ 设置为零，否则迭代算法不能保证收敛。为了解决这个问题，在式（8）中规则化 $r _ { p } ^ { j }$ （204号

对于方程式的第三项，拉普拉斯图是保留原始数据的结构。在这里本文使用与式(2)中相同的权重矩阵 $\boldsymbol { \mathcal { W } }$ 来定义邻域关系。

# 1.3潜在空间学习、回归与特征选择

通过结合式（3）和（7）中的目标函数，得到统一目标函数：

$$
\begin{array}{c} \begin{array} { r c l } { { \displaystyle e { \it \Delta } U , Y } } & { { = } } & { { \displaystyle a r g \ : \operatorname * { m } _ { U , Y } \stackrel { m i n } { _ { Y } } \ : \ : \ : t r \ : \ : \ : \gamma ^ { T } { _ { L } } \gamma } } \\ { { } } & { { } } & { { \displaystyle \ : + \ : \left. \alpha \begin{array} { c } { { \displaystyle M } } \\ { { \displaystyle e { \it \Delta } } } \end{array} \left( \left\| U _ { \rho } ^ { T } \chi _ { p } - Y ^ { T } \right\| _ { F } ^ { 2 } + \mathrm { ~ \it \beta ~ t r \ : \ : U _ { \rho } ^ { T } R _ { p } U _ { p } } + \gamma \ : t r \ : \ : U _ { \rho } ^ { T } \chi _ { p } { _ { L } } \chi _ { p } ^ { T } U _ { p } \right) \right\} } \end{array} }   \end{array} \ : \ : \ : \rho \ : \ : \ : \rho \ : ,
$$

其中： $\boldsymbol { a }$ 、 $\beta$ 和 $\gamma$ 是平衡参数。

对于上述问题，通过固定Y（或 $U )$ ，可以直接计算 $U$ （或$\boldsymbol { \mathit { Y } }$ 。将在下面给出一个关于联合优化问题的封闭解决方案。

固定 $\boldsymbol { Y } ,$ 在式（9）中相对于 $U$ 是凸的。通过对目标函数中的 $U _ { p }$ 求导使其等于零，可以得到

$$
\frac { \partial + U ^ { \gamma } } { \partial U _ { p } } = 2 \ X _ { p } X _ { p } ^ { T } U _ { p } - X _ { p } Y + \beta \ R _ { p } U _ { p } + \gamma X _ { p } L X _ { p } ^ { T } U _ { p } \ = 0 \qquad 1 0
$$

然后可以通过计算得到相应的投影矩阵：

$$
U _ { p } = \ : \chi _ { p } \ = \chi _ { p } \ = \chi _ { p } \ = e \ = e \ = e \ = \chi _ { p } \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ = e \ , p \ \in \{ 1 , \ldots , N \} .
$$

将式（11）中的 $U _ { p }$ 代入式（9），式（9）的第二部分可以替换为

$$
\begin{array} { r l } & { a \overset { M } { \underset { p = - f } { \sum } } ( \| \boldsymbol { v } _ { p } ^ { T } \boldsymbol { X } _ { p } - \boldsymbol { Y } ^ { T } \| _ { F } ^ { 2 } + \beta \textit { T r } \boldsymbol { U } _ { p } ^ { T } \boldsymbol { R } _ { p } \boldsymbol { U } _ { p } \boldsymbol { \theta } _ { p } + \gamma \mathrm { t r }  \boldsymbol { U } _ { p } ^ { T } \boldsymbol { X } _ { p } \boldsymbol { L } \boldsymbol { X } _ { p } ^ { T } \boldsymbol { U } _ { p }  ) } \\ & {  \quad p = T ( \boldsymbol { t r } \cdot \boldsymbol { U } _ { p } ^ { T } \boldsymbol { X } _ { p } \boldsymbol { X } _ { p } ^ { T } \boldsymbol { U } _ { p } - 2 \boldsymbol { t r }  \boldsymbol { U } _ { p } ^ { T } \boldsymbol { X } _ { p } \boldsymbol { Y } ^ { T }    } \\ & {      \boldsymbol { \alpha } _ { \alpha } \boldsymbol { \Sigma } | + \beta \gamma \boldsymbol { U } _ { p } \boldsymbol { U } _ { p } ^ { T } \boldsymbol { \theta } _ { p } \boldsymbol { U } _ { p } + \gamma \boldsymbol { t r }  \boldsymbol { U } _ { p } ^ { T } \boldsymbol { X } _ { p } \boldsymbol { L } \boldsymbol { X } _ { p } ^ { T } \boldsymbol { U } _ { p }    ) } \\ & {  \quad p = \alpha \underset { \beta = - f } { \sum } ( - t r \Big \langle \boldsymbol { U } _ { p } ^ { T } \boldsymbol { X } _ { p } \boldsymbol { X } _ { p } ^ { T } \boldsymbol { \xi } ^ { p } + \beta \boldsymbol { R } _ { p } \boldsymbol { \xi } \boldsymbol { r }  \boldsymbol { X } _ { p } ^ { T } \boldsymbol { \xi } \boldsymbol { U } _ { p } ^ { T } \boldsymbol { U } _ { p }   ) \boldsymbol { t r }  \boldsymbol { \hat { \ell } } _ { t } \boldsymbol { r }   } \\ & {  \quad p = T ( \boldsymbol { U } _ { p } ^ { T } \boldsymbol { \hat { \chi } } _ { p } \boldsymbol { \hat { \chi } } _ { p } ^ { T } + \beta \boldsymbol { \hat { \ell } } _ { p } \boldsymbol { \hat { \chi } } _ { p } ^ { T } \boldsymbol { \hat { \chi } } _ { p } ^ { T } \boldsymbol { \hat { \chi } } _ { p } ^ { T } ) \boldsymbol { x } _ { p }  \boldsymbol { \hat { \chi } } _ { p }  } \\ &  \quad = t r  \boldsymbol { Y } ^ { T } ( \boldsymbol { a } _ { \ell } \cdot \boldsymbol { \hat { \chi } } _ { p } ^ { T }  \boldsymbol { \hat { \chi } } _ { p } ^ { T } \boldsymbol { \hat { \chi } } _ { p } ^ { T } \boldsymbol { \hat { \chi } } _  \end{array}
$$

通过定义 $Q = X _ { p } X _ { p } ^ { T } + \beta R _ { p } + \gamma X _ { p } L X _ { p } ^ { T }$ ，式（9）中关于 $Y$ 的优化问题可以重新表述为

$$
{ \underset { { Y } ^ { \prime } { Y } = { I } _ { c } } { m i n } } { \underset { { t r } } { t r } } ( { \underset { { I } ^ { + } { a } } { \overbrace { { I } ^ { + } { a } } } } { \underset { { P } ^ { - } { a } } { \overset { M } { \sum } } } { \underset { { X } ^ { T } { Q } } { \overbrace { { A } _ { P } ^ { - } { I } } } } { \chi } _ { P } ^ { T } ) { Y } ) \qquad { \quad \qquad } { \quad } { \mathrm { 1 3 } }
$$

（204号 $\boldsymbol { Y }$ 可以通过矩阵 $L + a \ { / } _ { { n } } - a \ { \sum _ { p = 1 } ^ { M } \chi _ { p } ^ { T } } \bar { q } _ { p } ^ { - 1 } { \chi _ { p } }$ 的特征分解得到解决，选取20个最小特征值相对应的特征向量。

总之，可以有效地解决模型的近似解。对于潜在的空间学习，可以很容易地看到在式（13）中得到的正交空间能够很好地保持基于图形的标签信息的相关性，并且与多模态特征密切相关。对于潜在的空间回归与特征选择，投影矩阵得到了很好的正则化，在投影过程进行特征选择，选取有效的特征；在回归到公共空间时也可以保持局部关系。

# 2 实验结果

# 2.1实验设置

本文在两个常用数据集评估了提出的方法，即Wiki图像文本数据集[17]和PascalVOC[18]数据集。本文主要考虑图像查询文本数据库和文本查询与图像数据库两种跨模态检索任务。将提出的方法与几种相关的最先进方法进行比较，如PLS[I]、

BLM[3]、CCA[1]、CDFE[6]、CCA-3V[19]、GMLDA[7]、GMMFA[7]、LCFS[20]、SM[17]、SCM[17]。

·PLS、BLM、CCA：是三种经典方法，使用成对信息来学习多模态数据中的常见潜在子空间。在公共子空间中，可以测量不同数据模式之间的相似性。

·CDFE：学习一个共同的特征子空间，其中散布矩阵内部和散布矩阵之间的差异被最大化。

·CCA-3V：三视图典型相关性分析。

·GMLDA：找到一组投影矩阵，使得来自同一类的样本彼此接近而来自不同类别的样本分开。

·GMMFA：是CCA的监督扩展，同时考虑CCA约束和语义约束。

·LCFS：将耦合线性回归，21范数和迹范数整合到一个通用最小化公式，子空间学习和耦合特征选择可以同时执行。

·SM：在高维度的抽象层面上分析图像和文本的表示。更具体地说，它使用多类逻辑回归来对图像和文本进行分类。

·SCM：是CCA和SM的组合。SCM首先使用CCA获得特征表示，然后使用特征表示来构建语义空间，这可以提高CM和SM的检索性能。

为了评估所提出的方法的性能，进行了图像查询文本数据库与文本查询图像数据库两种跨模态检索任务。

平均平均精度（MAP）[17]是跨模态检索的经典性能评估标准。具体来说，给定一组查询，每个查询的平均精度（AP）被定义为：

$$
A P = \frac { 1 } { T } \sum _ { r = 1 } ^ { R } P r \delta r
$$

其中： $T$ 是在检索集合中相关文档的数量； $P ( r )$ 表示前 $\mathbf { r }$ 个检索文档的精度。如果第 $\boldsymbol { r }$ 个检索到的文件是相关的（相关代表属于查询的类），则 $\delta \textit { r } = \boldsymbol { \mathscr { 1 } } ;$ ，否则 $\delta \ r \ = 0 _ { \circ }$

然后对查询集中所有查询的 $A P$ 值进行平均来计算MAP。MAP值越大，跨模态检索的表现越好。

除了MAP之外，本文还使用精度召回曲线来评估不同方法的有效性。

![](images/0fe0add1dc0bad645fc0309228b107dbe6337bf1c85069299a3b194952ca96e7.jpg)  
图3Wikipedia数据集上图像检索文本召回率比较

![](images/3ad88ae746dcefa7f96cd44537525a488745aea201d3afa9b273e3a29d752639.jpg)  
图4Wikipedia数据集上文本检索图像召回率比较

# 2.2Wiki数据集实验结果

Wiki数据集[17]包含来自10个专业类的2866个图像文本对。将2173个图像文本对用于训练，693个图像文本对用于测试。对于文本，采用潜在的Dirichlet分配（LDA）来提取10个维度表示。128 维 SIFT描述子直方图[21用于表示图像。

本文设置α $= 0 . 0 0 1$ $\mathrm { r } = 1 4$ and $\mathrm { ~ \textit ~ { ~  ~ } ~ } = 4$ 。表1显示了本文的方法和其他相关算法的MAP分数。图3、4显示了跨模态检索的召回率。本文中对图像查询的MAP分数为0.2871，对文本查询的MAP分数为0.2232，表现优于之前的算法。由于加入了语义信息，可以看到CDFE、GMMFA、GMLDA、CCA-3V和本文方法比PLS、BLM和CCA表现更好。

表1Wikipedia数据集的跨媒体检索性能比较  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">平均精度均值/mAP</td></tr><tr><td>图像查询</td><td>文本查询</td><td>平均值</td></tr><tr><td>PLS</td><td>0.2402</td><td>0.1633</td><td>0.2032</td></tr><tr><td>BLM</td><td>0.2562</td><td>0.2023</td><td>0.2293</td></tr><tr><td>CCA</td><td>0.2549</td><td>0.1846</td><td>0.2198</td></tr><tr><td>CDFE</td><td>0.2655</td><td>0.2059</td><td>0.2357</td></tr><tr><td>GMMFA</td><td>0.2750</td><td>0.2139</td><td>0.2445</td></tr><tr><td>GMLDA</td><td>0.2751</td><td>0.2098</td><td>0.2425</td></tr><tr><td>CCA-3V</td><td>0.2752</td><td>0.2242</td><td>0.2497</td></tr><tr><td>LCFS</td><td>0.2798</td><td>0.2141</td><td>0.2470</td></tr><tr><td>Proposed</td><td>0.2871</td><td>0.2232</td><td>0.2552</td></tr></table></body></html>

![](images/aaafd0f4de670ec455b77d1c92a03d8a3b5ed4d985c2f21a9c133ff772005d7c.jpg)  
图5PascalVOC数据集上图像检索文本召回率比较

![](images/c752b4f1341bd273e06ef75d4fdfb434641c817996a71ac48d65e41c4c04c220.jpg)  
图6PascalVOC 数据集上文本检索召回率比较

# 2.3PascalVOC 数据集实验结果

PascalVOC 数据集[18]由来自20个不同类别的5011/4952（训练/测试）图像标签对组成。在实验中选择仅对应一个对象的图像，这导致训练集合为2808对，测试集合为2841对。使用512维GIST特征来表示图像，399维度词频特征来表示文本。

本文设置 $\mathrm { ~ \textit ~ { ~ a ~ } ~ } = 0 . 0 1 , \mathrm { r } = 3$ and $\mathrm { ~ \textit ~ { ~  ~ } ~ } = 4$ 。表2显示了本文的方法和其他相关算法的MAP分数。图5、6显示了跨模态检索的召回率。本文中对图像查询的MAP分数为0.2871，对文本查询的MAP分数为0.2232，表现优于之前的算法。

表2PascalVOC 数据集的跨媒体检索性能比较  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">平均精度均值/mAP</td></tr><tr><td>图像查询</td><td>文本查询</td><td>平均值</td></tr><tr><td>PLS</td><td>0.2757</td><td>0.1997</td><td>0.2377</td></tr><tr><td>BLM</td><td>0.2667</td><td>0.2408</td><td>0.2538</td></tr><tr><td>CCA</td><td>0.2655</td><td>0.2215</td><td>0.2435</td></tr><tr><td>CDFE</td><td>0.2928</td><td>0.2211</td><td>0.2569</td></tr><tr><td>GMMFA</td><td>0.3090</td><td>0.2308</td><td>0.2699</td></tr><tr><td>GMLDA</td><td>0.3094</td><td>0.2448</td><td>0.2771</td></tr><tr><td>CCA-3V</td><td>0.3146</td><td>0.2562</td><td>0.2854</td></tr><tr><td>LCFS</td><td>0.3438</td><td>0.2674</td><td>0.3056</td></tr><tr><td>Proposed</td><td>0.4043</td><td>0.3264</td><td>0.3653</td></tr></table></body></html>

# 2.4不同的特征类型的表现

本文还使用Wiki数据集中图像和文本的不同类型的特征来测试跨模态检索的性能。除了Wiki数据集本身提供的特征外，对于图像，通过Caffe 提取了4096 维的图像CNN特征；对于文本，通过LDA提取100 维的文本特征。表3显示了Wiki数据集上具有不同类型特征的GMMFA、GMLDA、SM和SCM的MAP分数。

表3Wikipedia数据集的跨媒体检索性能比较  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">平均精度均值/mAP</td></tr><tr><td>图像查询</td><td>文本查询</td><td>平均值</td></tr><tr><td>GMMFA</td><td>0.371</td><td>0.322</td><td>0.346</td></tr><tr><td>GMLDA</td><td>0.372</td><td>0.322</td><td>0.347</td></tr></table></body></html>

<html><body><table><tr><td>SCM</td><td>0.351</td><td>0.324</td><td>0.337</td></tr><tr><td>SM</td><td>0.403</td><td>0.357</td><td>0.380</td></tr><tr><td>Proposed</td><td>0.4132</td><td>0.3731</td><td>0.3932</td></tr></table></body></html>

# 3 结束语

在本文中提出了一种新的联合学习框架来解决跨模态检索问题，该框架包括不同模态的潜在空间学习，用于特征选择的21范式、潜在空间回归以及图模型。在所提出的框架下，学习不同的投影矩阵以将不同的模态数据映射到公共子空间，并且在投影过程中选择不同模态的相关和判别特征，使用图模型表征局部关系。在Wikipedia数据集和PascalVoc两个数据集上的实验结果表明所提出的方法提高了多模态之间的检索效率。在以后的工作中，可以通过添加模态之间的相关性，实现在映射的共同的空间中保持模态之间的关系，或结合多视图从而找到最优的表示，从多视图空间学习共同的特征空间。

# 参考文献：

[1]Hardoon DR, Szedmak S,Shawe-Taylor J. Canonical correlation analysis: an overview with application to learning methods [J].Neural Computation, 2004,16 (12): 2639-2664.   
[2]Rosipal R,Krmer N. Overview and recent advances in partial least squares [C]// Proc of International Conference on Subspace,Latent Structure and Feature Selection.[S.1.] : Springer-Verlag,20o5: 34-51.   
[3]Tenenbaum JB,Freeman W T. Separating style and content with bilinear models [J]. Neural Computation,200o,12 (6): 1247.   
[4]Mahadevan V, Pereira JC,Vasconcelos N,et al.Maximum covariance unfolding-manifold learning for bimodal data [Cl// Advances in Neural Information Processing Systems.2011: 918-926.   
[5]Mao Xiangbo,Lin Binbin,Cai Deng,et al.Parallel field alignment for cross media retrieval [C]// Proc of ACM International Conference on Multimedia.[S.1.] :ACMPress,2013: 897-906.   
[6]Lin D,Tang X. Inter-modality face recognition [J].2006,3954 (4): 13-26.   
[7]Sharma A.Generalized multiview analysis:a discriminative latent space [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.[S.1.] : IEEE Computer Society, 2012: 2160-2167.   
[8] Zhai Xiaohua,Peng Yuxin,Xiao Jianguo.Learning cross-media joint representation with sparse and semisupervised regularization [J].IEEE Trans on Circuits & Systems for Video Technology,2014,24(6): 965-978.   
[9] Zhuang Yueting，Wang Yanfei，Wu Fei，et al. Supervised coupled dictionary learning with group structures for multi-modal retrieval [C]/ Proc of AAAI Conference on Artificial Intelligence.2013.   
[10] Zhai Xiaohua,Peng Yuxin, Xiao Jianguo. Heterogeneous metric learning with joint graph regularization for cross-media retrieval [C]// Proc of the 27th AAAI Conference on Artificial Intelligence.[S.1.]:AAAI Press, 2013: 1198-1204.   
[11] Ngiam J,Khosla A,Kim M,et al.Multimodal deep learning [C]// Proc of International Conference on Machine Learning.2O11: 689-696.   
[12] Srivastava N, Salakhutdinov R.Multimodal learning with deep boltzmann machines [C]/ Proc of International Conference on Neural Information Processing Systems.[S.1.]:Curran Associates Inc,2012:2222-2230.   
[13] Andrew G, Arora R,Bilmes J,et al.Deep canonical correlation analysis [C]// Proc of International Conference on International Conference on Machine Learning.2013: III-1247.   
[14] Deng Cai,He Xiaofei,Han Jiawei. Spectral regression for efficient regularized subspace learning [C]//Proc of IEEE International Conference on Computer Vision.[S.1.] :IEEE Press,2007:1-8.   
[15] He Ran,Tan Tieniu,Wang Liang,et al.l2,1 Regularized correntropy for robust feature selection [J].2012,157(10): 2504-2511.   
[16] Nikolova M,Ng MK. Analysis of half-quadratic minimization methods for signal and image recovery [M].[S.1.] $\because$ Society for Industrial and Applied Mathematics,2005.   
[17]Rasiwasia N,Pereira JC,Coviello E,et al.A new approach to cross-modal multimedia retrieval [C]//Proc of International Conference on Multimedia. ACM, 2010: 251-260.   
[18] Hwang S J,Grauman K.Reading between the lines: object localization using implicit cues from image tags.[J]. IEEE Trans on Pattern Analysis & Machine Intelligence,2012,34 (6): 1145-1158.   
[19] Gong Yunchao,Ke Qifa,Isard M,et al.A multi-view embedding space for modeling internet images,tags，and their semantics [J]. International Journal of Computer Vision,2014,106 (2): 210-233.   
[20] Wang Kaiye,He Ran,Wang Wei,et al.Learning coupled feature spaces for cross-modal matching [C]// Proc of IEEE International Conference on Computer Vision.[S.1.] : IEEE Computer Society,2013: 2088-2095.   
[21] Lowe D G. Distinctive image features from scale-invariant keypoints [J]. International Journal of Computer Vision,2004,60 (2): 91-110.   
[22] Wu Jianlong,Lin Zhouchen,Zha Hongbin. Joint latent subspace learning and regression for cross-modal retrieval [C]// Proc of International ACM SIGIR Conference.[S.1.] : ACMPress,2017: 917-920.   
[23] Wang Kaiye,He Ran,Wang Liang，et al.Joint feature selection and subspace learning for cross-modal retrieval [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2016,38 (10): 2010-2023.   
[24] Peng Yuxin，Zhai Xiaohua,Zhao Yunzhen，et al.Semi-supervised cross-media feature learning with unified patch graph regularization [J]. IEEE Trans on Circuits & Systems for Video Technology,2016,26 (3): 583-596.   
[25] Wang Kaiye,Yin Qiyue,Wang Wei,et al. A comprehensive survey on cross-modal retrieval [J].2016.   
[26] Wei Yunchao，Zhao Yao,Zhu Zhenfeng，et al.Modality-dependent cross-media retrieval [J].ACM Transactions on Intelligent Systems & Technology,2016,7(4): 57.   
[27] Zhou Jile,Ding Guiguang,Guo Yuchen.Latent semantic sparse hashing for cross-modal similarity search [M].[S.1.]: ACM Press,2014.   
[28] Yu Zhou,Wu Fei,Yang Yi,et al.Discriminative coupled dictionary hashing for fast cross-media retrieval [C]// Proc of International ACM SIGIR Conference on Research & Development in Information Retrieval. [S.1.]:ACM Press,2014: 395-404.   
[29] Wei Yunchao,Zhao Yao,Lu Canyi,et al. Cross-modal retrieval with CNN visual features:a new baseline [J]. IEEE Trans on Cybernetics,2017,47 (2): 449-460.   
[30] Kang Cuicui,Xiang Shiming,Liao Shengcai,et al. Learning consistent feature representation for cross-modal multimedia retrieval [J]. IEEE Trans on Multimedia,2015,17 (3): 370-381.   
[31] Yan Jihong,Zhang Huaxiang,Sun Jiande,et al.Joint graph regularization based modality-dependent cross-media retrieval [J].Multimedia Tools & Applications,2017 (6): 1-19.