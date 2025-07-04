# 稀疏和标签约束半监督自动编码机的分类算法 ：

王慧玲1，宋威1,²，王晨妮

(1．江南大学 物联网工程学院，江苏 无锡 214122;2.物联网技术应用教育部工程研究中心，江苏 无锡 214122)

摘要：自动编码机通过深度无监督学习能够表达数据的语义特征，但由于其隐含层节点个数难以有效确定，所处理的数据进一步用于分类时常会导致分类准确度低，稳定性弱等问题。针对这些问题，提出了一种稀疏和标签约束的半监督自动编码机(SLRAE)，以实现无监督学习与监督学习的有机结合，更准确地抽取样本的本质特征。稀疏约束项针对每个隐含结点的响应添加约束条件，从而在隐含神经元数量较多的情况下仍可发现数据中潜在的结构；同时引入标签约束项，以监督学习的方式比对实际标签与期望标签，针对性地调整网络参数，进一步提高分类准确率。为验证所提方法的有效性，实验中对多个数据集进行广泛地测试，其结果表明，相对传统自动编码机(AE)，稀疏自动机（SAE)，以及极限学习机(ELM)，SLRAE所处理的数据应用于同一分类器，能明显提高分类准确率和稳定性。

关键词：分类；稀疏约束；标签约束；自动编码机；极限学习机 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.02.0147

# Semi-supervised auto-encoder using sparse and label regularizations for classification

Wang Huiling1, Song Wei1,2, Wang Chenni1, 2 (1.SchoolofInternetofingsEngneering,JangnanUnversityWuxiJngsu22ina;2.EngineeingReeachtr ofInternet of Things Technology Applications for Ministry ofEducation,Wuxi Jiangsu 214122,China)

Abstract:Auto-Encodercanexpressthesemanticfeaturesofdatathroughdeepunsupervised learing,butitishardtodeterine thenodesofhiddenlayerandtheprocessngofdataforclasificationoftenleadstolowaccuracyandlowstabilityTosolvethe problems,this paper proposes asemi-supervised auto-encoder using sparse and label regularizations (LSRAE)to extract the essential features ofthe samples more acurately bycombining unsupervised learning with supervised learning.The sparse regularizationtermaddsconstraints totheresponseofeachhidden node,sothatthisalgorithmcanfind potential structures in thedata when the numberofhidden neurons is large.Atthesame time,this algorithm introducealabelregularization termto comparetheactual labels with desired labels bysupervised learming to adjust the network parameters and further improve the classificationaccuracy.Inorder to verify the validityof the proposed method,this algorithm tests manydatasets in he experiment.Theresults show thatcompared with traditional auto-encoders (AE)，sparse auto-encoder(SAE),and extreme learming machine (ELM),SLRAEcanobviously improve theclassificationaccuracyand stability when the processed data is applied to the same classifier.

Key words: classification; sparse regularization; label regularization; auto-encoder; extreme learning machine

# 0 引言

随着信息技术的飞速发展，数字数据库中的数据呈现指数增长，如何有效地从海量的信息中提取出有价值的特征，已成为当今数据挖掘和模式识别领域的研究热点之一。自2006 年以来，以特征学习[1l为代表的自动编码器（auto-encoder，AE)[2]表示学习在机器学习领域取得了突破性的进展，这些进展主要用来进行深度学习模型的初始化[3]。然而，常用的AE会因其复杂的网络结构而导致分类精度下降。为了解决这一问题，一些AE正则化方法被学者们提出：稀疏自动编码器（sparseauto-encoder，SAE）[4.5]是Bengio 等人于2007年提出来的，要求隐藏层神经元的激活度满足一定的稀疏性；降噪自动编码器（denoisingauto-encoder，DAE）[6,7]是由Vincent等人于 2008年提出的，是对输入向量加入干扰，训练编码器重构出原始输入，使网络具有更好的鲁棒性；压缩自动编码机（contractiveautoencoder，CAE)[8.9]是Bengio 等人在 2011年提出，通过将隐含层输出关于权重的雅克比矩阵的F范数的平方作为重构函数的正则化约束项，可以获取鲁棒性的中间层特征。

以上的正则化AE 都是无监督学习的过程[10]，无监督的深度学习方法是从数据本身分析，能有效提取出深层抽象的数据特征，但是由于先验标签信息的缺乏，所提取的特征不能描述特定类别，很难应用于分类[]。监督学习就可以很好地解决这个问题，但学习到的特征不能很好地表示原始的数据，泛化能力弱，很容易产生过拟合问题。

为了更好地解决无监督学习和监督学习方法存在的问题，本文提出了一种稀疏和标签约束的半监督自动编码机（SLRAE），用无监督学习中得到的基本语义特征和监督学习中描述标签的有鉴别性的特征来表示数据的特点，再进一步将这些特征用于分类。为了验证我们提出的方法的有效性，我们在USPS数据库[12]和6个UCI数据集[13]上做大量的实验。我们将本文提出的SLRAE方法与AE，SAE，ELM，LRAE(只使用标签约束项的自动编码机),DBN[14]和AdaptiveDBN[15]做比较，实验结果表明SLRAE具有更好的分类准确性。

# 1 相关工作

# 1.1 自动编码机(AE)

自动编码机的概念是20世纪80年代晚期被提出来的，基本的自动编码机由三层神经网络组成，包括输入层、隐含层和输出层，输入层与输出层的神经元的节点数相同。在编码阶段，用函数 $f _ { \theta }$ 对输入向量 $x$ 进行映射，获得中间层表示 $y$ ，在解码阶段用函数 $g _ { \theta }$ 对中间层表示 $y$ 进行映射获得重构数据 $z$ 。自动编码机通过最小化重构误差 $L ( \boldsymbol { x } , \boldsymbol { z } ) = \sum _ { i = 1 } ^ { n } \left\| \boldsymbol { X } _ { i } - \boldsymbol { Z } _ { i } \right\| ^ { 2 }$ 来微调网络参数，其中 $\pmb { \chi } _ { i }$ 是第 $i$ 维训练样本， $Z _ { i }$ 是第 $i$ 维输出数据， $n$ 是训练样本的数量。

在 AE 中需要调整的参数是 $\theta = \{ W , b , W ^ { \prime } , b \}$ ，其中 $b$ 和 $b ^ { \prime }$ 是编码和解码的偏置， $w$ 和 $w$ 是编码和解码的权重， $w ^ { \prime }$ 是W的转置。通常采用经典的梯度下降法获得最优值作为参数 $\theta$ □与有着较大的人工数据特征提取工作量的传统的BP神经网络[16]相比，AE 可以提高特征提取的工作效率，减少原始输入数据的维数，还可以很好地学习到给定数据集的压缩和分布式特征表示。

# 1.2极限学习机(ELM)

极限学习机[17,18]是由黄广斌教授提出的一种具有快速学习特点的单隐层前馈神经网络，隐含层输入权值和偏置都是随机产生的，只需要设置隐含层神经元的个数，计算该网络的输出权值。传统的ELM包括输入层、隐含层和输出层，假设有 $N$ 个任意的样本 $\left\{ \left( x _ { j } , t _ { j } \right) \right\} _ { j = 1 } ^ { N }$ ，该 ELM 网络结构在输入为 $x$ 的隐含层输出矩阵为 $H$ ，则整个网络的输出层可表示为

$$
H \beta = T
$$

其中：β 是隐含层和输出层的权重矩阵T=[t,tz,.,ty]mxN

表示样本的目标标签值，这样前馈神经网络的训练就可以转化成一个求解输出权值矩阵的最小二乘解 $\hat { \boldsymbol { \beta } }$ 的问题，输出权值 $\beta$ 可由下列公式得出：

$$
\stackrel { \wedge } { \beta } = H ^ { \dagger } T
$$

其中 $\boldsymbol { H } ^ { \dagger }$ 表示隐含层输出矩阵 $H$ 的 Moore-penrose(MP)广义逆。与传统的需要多次选代反馈的前馈神经网络不同的是，ELM利用最小二乘法直接计算出权值矩阵，训练速度快，泛化性能好。

# 2 稀疏和标签约束的半监督自动编码机(SLRAE)

本文提出了一种使用稀疏和标签约束的半监督自动编码机（semi-supervisedAE），其中无标签样本的无监督学习过程可以提高半监督自动编码机学习的泛化能力，有标签样本的监督学习过程可以提高半监督自动编码机模型的分类准确度。

在自动编码机中加入标签项，减少训练数据的实际输出标签和期望输出标签之间的误差，从而弥补无监督学习的分类准确度低的缺点。我们还利用稀疏正则化来实现输入数据的稀疏编码，通过约束隐含层节点数从而有效地提取数据的隐藏结构，具有良好的学习数据集的能力，然后将学习到的特征表达输入到分类器中，分类结构验证了所提出的半监督自动编码机的有效性。图1显示的是SLRAE的用于分类的框架。SLRAE的代价函数由 $J _ { _ { A E } }$ ， $J _ { { \scriptscriptstyle w d } }$ ， $J _ { \it { s p a r s e } }$ ， $J _ { \mathit { l a b e l } }$ 组成。 $J _ { _ { A E } }$ 是输入与输出数据的重构误差，通过最小化 $J _ { _ { A E } }$ 使得输入数据尽可能地接近输出数据，从而更准确地重构出输出数据。 $J _ { { \scriptscriptstyle w d } }$ 是为了减小权重的幅度，防止过度拟合。在此基础上，我们所提出的SLRAE还包括稀疏约束项 $J _ { \it { s p a r s e } }$ 和标签误差项 $J _ { \mathit { l a b e l } } \circ J _ { \mathit { s p a r s e } }$ 限制隐含层使得表达更稀疏，可以使得SLRAE有效地从大量的数据中提取出潜在的本质特征。 $\boldsymbol { J } _ { l a b e l }$ 是实际标签与期望标签的误差项，通过使误差项最小调整网络参数，然后将网络输入到分类器中，可以进一步提高分类的准确性。因此， $J _ { _ { A E } }$ ， $J _ { { \scriptscriptstyle w d } }$ 和 $J _ { \it { s p a r s e } }$ 是通过无监督学习获得， $\boldsymbol { J } _ { l a b e l }$ 是通过有监督学习获得。本文提出的半监督自动编码机SLRAE结合了非监督和监督学习的优点，并利用上述4个约束来调整权值和偏置，提取出数据的特征表达，并结合分类器，通过构建具有高准确率与高泛化能力的半监督学习网络，进一步实现分类应用。

事实上，我们的标签约束利用监督学习提高分类的准确率，这个标签项是用极限学习机(ExtremeLearningMachine,ELM)的思想计算的。由于原始输入数据往往庞大且冗余，难以直接获取本质语义特征，稀疏约束限制隐含层节点数使得表达更稀疏，加入稀疏限制可以获取输入的主要信息，所以本文提出的SLRAE不但可以有效地从大量数据中提取潜在的本质特征，还可以提高分类的准确度。

![](images/2564216255f0891106ab012b4afd66c8d8dc7f9f9c1d6e17405016e6ccb40cec.jpg)  
图1SLRAE 用于分类的框架

在 SLRAE 中，假设 $n$ 个样本 $\pmb { X } = \left\{ \pmb { X } _ { i } \right\} _ { i = 1 } ^ { n }$ 输入到 $d$ 维空间，每一个样本表示为 $X _ { i } = \left[ x _ { i 1 } , x _ { i 2 } , . . . , \mathbf { X } _ { i d } \right] ^ { T } \in R ^ { d }$ ，编码函数yi=fe(x）=s(Wx+b)将x 映射l到维隐含层上得到中间表示 $\boldsymbol { y } _ { i }$ ，解码函数 $\begin{array} { r } { Z _ { i } = \mathbf { g } _ { \theta } \left( \pmb { y } _ { i } \right) = s \left( \pmb { W } \pmb { y } _ { i } + \pmb { b } ^ { \ast } \right) } \end{array}$ 重构 $X _ { i }$ 得到 $Z _ { i }$ 。它们可以简洁地表示为 $a _ { \mathrm { 1 } } = W x _ { \mathrm { i } } + b , y _ { \mathrm { i } } = s ( a _ { \mathrm { 1 } } ) , a _ { \mathrm { 2 } } = W ^ { \prime } y _ { \mathrm { i } } + b ^ { \prime }$ ，其中 $s ( x ) = 1 / \left( 1 + \mathrm { e } ^ { - x } \right)$ 是 sigmoid 激活函数。 $w$ 和 $b$ 分别表示输入层与隐含层之间的权重和偏置， $w ^ { \prime }$ 和 $b ^ { \prime }$ 分别表示隐含层和输出层之间的权重和偏置。我们用 $\boldsymbol { X } \in \boldsymbol { R } ^ { d \times n }$ 表示输入层的样本特征矩阵， $\pmb { Y } \in { \pmb { R } } ^ { l \times n }$ 表示隐含层的样本特征矩阵， $Z \in { \cal R } ^ { d \times n }$ 表示输出层对于输入数据的样本特征矩阵。

在本文中，隐含层的节点数远远大于输入层的节点数，我们可以在隐含层上加入一个稀疏限制，它可以保证学习到更多的局部结构信息。在每次迭代，SLRAE 计算出平均激活度ρj=(1/n)∑,a(x)，其中n是样本数，i是第i个样本，$i \in { \left( 1 , 2 , 3 . . . n \right) } , a _ { j } ( x _ { i } )$ 表示第 $i$ 个样本情况下，第 $j$ 个隐含神经元的激活度。在稀疏约束条件下，p是稀疏性参数，且p=p,通常情况下， $\rho$ 是一个接近于0的较小的值。这里，相对熵（KLdivergence）是一种用来测量两个分布之间差异的方法，计算公式如下：

$$
J _ { _ { s p a r s e } } = K L \Big ( \rho \| \rho _ { j } ^ { * } \Big ) = \rho \mathrm { l o g } \frac { \rho } { \rho _ { j } ^ { * } } + \big ( 1 - \rho \big ) \mathrm { l o g } \frac { 1 - \rho } { 1 - \rho _ { j } ^ { * } } ( 3 )
$$

在本文中也使用了数据的标签，{Xn,Tn}={x,t}=ti=[tl,ti2,tn]gi(x)=s(Wx +b)是隐含层第i个节点的输出值。用 $h ( \boldsymbol { x } ) = \left[ g _ { 1 } ( \boldsymbol { x } ) , g _ { 2 } ( \boldsymbol { x } ) , . . . g _ { h } ( \boldsymbol { x } ) \right]$ 表示输入数据在隐含层的输出，用 $H$ 表示隐含层的输出矩阵$H = \left[ h ^ { T } ( x _ { 1 } ) , h ^ { T } ( x _ { 2 } ) , . . . , h ^ { T } ( x _ { n } ) \right] ^ { T }$ 。因为将自动编码机用于分类前的特征提取，ELM 可以直接用作分类器[19]，所以虚拟出一个标签层，也就是分类的结果，之后将AE的输入层和隐含层以及虚拟标签层看做 ELM，然后用 $\stackrel { \wedge } { \beta } = H ^ { \dagger } T$ 计算出隐含层和虚拟标签层之间的权值和偏置。在该 ELM可以计算出实际的输出

标签，公式如下：

$$
\pmb { L } = \pmb { H } \hat { \pmb { \beta } }
$$

在已知所给的标签 $\tau$ 和 ELM计算出的实际输出标签 $\boldsymbol { L }$ 的基础上，得到实际标签与给定标签之间的标签误差，并最小化标签误差 $P ( L , T )$ ，可表示为

$$
\operatorname* { m i n } _ { \theta } \mathbf { J } _ { l a b e l } \left( \theta \right) = \operatorname* { m i n } _ { \theta } \sum _ { i = 1 } ^ { n } P ( L , T )
$$

那么SLRAE的目标函数如下：

$$
J _ { _ { L S R A E } } = J _ { _ { A E } } + \lambda J _ { _ { w d } } + \beta J _ { _ { s p a r s e } } + \gamma J _ { _ { l a b e l } }
$$

其中： $\lambda ^ { \mathbf { \nu } , \mathbf { \Lambda } } \beta$ 和 $\gamma$ 是控制公式中各项相对重要性的参数，第一项 $J _ { _ { A E } } = { \frac { 1 } { 2 n } } { \sum _ { i = 1 } ^ { n } } \bigl ( \| h _ { _ { w , b } } \bigl ( X ^ { ( i ) } \bigr ) - y ^ { ( i ) } \| ^ { 2 } \bigr )$ 是训练样本输入与输出的重构误差项，第二项 $J _ { { } _ { w d } } = \frac { 1 } { 2 } \underset { i = 1 } { \overset { d } { \sum } } \underset { j = 1 } { \overset { l } { \sum } } ( W _ { j i } ) ^ { 2 }$ 是为了防止权重过度拟合的权重衰减项，第三项 Jspare=∑KL(ρllρp)是稀疏惩罚项，在隐藏神经元数量较多的情况下仍然可以发现输入数据中重要的结构，最后一项是标签误差项，用来表示原始标签与实际标签的误差，表示如下：

$$
J _ { \mathit { l a b e l } } = \sum _ { i = 1 } ^ { n } P ( L , T ) = { \frac { 1 } { 2 n } } \sum _ { i = 1 } ^ { n } \left\| L - T \right\| ^ { 2 } = { \frac { 1 } { 2 n } } \sum _ { i = 1 } ^ { n } \left\| H { \hat { \boldsymbol { \beta } } } - T \right\| ^ { 2 }
$$

其中： $\tau$ 为输入样本的原始标签， $H$ 表示隐含层的输出矩阵，$\hat { \boldsymbol { \beta } }$ 是隐含层与输出标签层的权值与偏置，通过公式 $\stackrel { \wedge } { \beta } = H ^ { \dagger } T$ 计算可得。

用梯度下降法来优化目标函数，更新 $w$ 和 $b$ 公式如下：

$$
W _ { i j } ^ { ( l ) } = W _ { i j } ^ { ( l ) } - \alpha \frac { \widehat { \partial } J _ { _ { L S R A E } } ( W , b ) } { \partial W _ { i j } ^ { ( l ) } }
$$

$$
b _ { i } ^ { ( l ) } = b _ { i } ^ { ( l ) } - \alpha \frac { \hat { \sigma } J _ { _ { L S R A E } } ( W , b ) } { \hat { \sigma } b _ { i } ^ { ( l ) } }
$$

其中： $\alpha$ 为学习率，对于重构误差项 $J _ { _ { A E } }$ ，关于 $z$ 的偏导数可以表示为 $\frac { \partial J _ { _ { A E } } } { \partial Z } = - \frac { 1 } { n } ( X - Z )$ ，那么得到 $J _ { _ { A E } }$ 关于 $b ^ { \prime }$ 和樂 $w$ 的偏导数为

$$
\begin{array} { r l } & { \cfrac { \hat { \alpha } J _ { _ { A E } } } { \hat { \alpha } b ^ { \prime } } = \biggr [ \cfrac { \hat { \alpha } J _ { _ { A E } } } { \hat { \alpha } Z } \circ s ^ { \prime } \bigl ( W ^ { \prime } Y + b ^ { \prime } \otimes \mathrm { \bf l } _ { n } ^ { \mathrm { \scriptscriptstyle T } } \bigr ) \biggr ] \boldsymbol { 1 } _ { n } } \\ & { \cfrac { \hat { \alpha } J _ { _ { A E } } } { \hat { \alpha } W ^ { \prime } } = \biggr [ \cfrac { \hat { \alpha } J _ { _ { A E } } } { \hat { \alpha } Z } \circ s ^ { \prime } \bigl ( W ^ { \prime } Y + b ^ { \prime } \otimes \mathrm { \bf l } _ { n } ^ { \mathrm { \scriptscriptstyle T } } \bigr ) \biggr ] \boldsymbol { Y } ^ { \mathrm { \scriptscriptstyle T } } } \end{array}
$$

相同地， $J _ { _ { A E } }$ 关于隐含层表示 $\gamma$ 的偏导数可以表示为[as(WY+b81)]，那么得到JAE关于b和W的偏导数为

$$
\frac { \hat { \sigma } J _ { A E } } { \hat { \sigma } b } = \left[ \frac { \hat { \sigma } J _ { A E } } { \hat { \sigma } Y } \circ s ^ { \prime } \big ( W X + b \otimes 1 _ { n } ^ { \operatorname { T } } \big ) \right] \mathbf { 1 } _ { n }
$$

$$
\frac { \hat { \sigma } J _ { A E } } { \hat { \sigma } W } = \left[ \frac { \hat { \sigma } J _ { A E } } { \hat { \sigma } Y } \circ s ^ { \prime } \big ( W X + b \otimes 1 _ { n } ^ { \mathrm { T } } \big ) \right] X ^ { \mathrm { T } }
$$

其中：。是阿达玛积， $\otimes$ 是外积， $\mathbf { l } _ { n } ^ { \mathrm { T } }$ 表示数值为1的维列向量，

$s ^ { \prime } ( x ) = s ( x ) [ 1 - s ( x ) ]$ 是 sigmoid 函数的偏导数，我们可以结合(11)和(13)可得

$$
\frac {  { \partial } J _ { A E } } {  { \partial } W } : = \frac { 1 } { 2 }  { \left\{ \left[ \frac {  { \partial } J _ { A E } } {  { \partial } Z } \circ s ^ { \prime } \bigl ( W ^ { \prime } Y + b ^ { \prime } \otimes 1 _ { n } ^ { \mathrm { T } } \bigr ) \right] Y ^ { \mathrm { T } } + \left[ \frac {  { \partial } J _ { A E } } {  { \partial } Y } \circ s ^ { \prime } \bigl ( W X + b \otimes 1 _ { n } ^ { \mathrm { T } } \bigr ) \right] X ^ { \mathrm { T } } \right\} }
$$

因为权重衰减项 $J _ { { \scriptscriptstyle w d } }$ 只作用于 $w$ ，所以 $J _ { { \scriptscriptstyle w d } }$ 关于 $w$ 的偏导数可以表示为 $\frac { \hat { \sigma } J _ { _ { w d } } } { \hat { \sigma } W } = W$ 。

对于稀疏约束项 $J _ { \it { s p a r s e } }$ ，关于 $\rho _ { j } ^ { * }$ 的偏导数可以表示为$\frac { \partial J _ { s p a r s e } } { \partial \rho _ { j } } = \frac { - \rho } { \rho _ { j } ^ { \ast } } + \frac { 1 - \rho } { 1 - \rho _ { j } ^ { \ast } }$ 。因为稀疏约束项是对隐含层进行稀疏，在使用反向传播方法时只需要对编码阶段反馈，所以 $J _ { \it { s p a r s e } }$ 关于 $b$ 和 $w$ 的偏导为

$$
\frac { \hat { \mathcal { D } } J _ { s p a r s e } } { \hat { \mathcal { D } } b } = \left[ \frac { \hat { \mathcal { D } } J _ { s p a r s e } } { \hat { \mathcal { D } } \rho _ { j } ^ { \ast } } \circ s ^ { \prime } \big ( W X + b \otimes 1 _ { n } ^ { \mathrm { T } } \big ) \right] \mathbf { 1 } _ { n }
$$

$$
\frac { \hat { \sigma } J _ { s p a r s e } } { \hat { \sigma } W } = [ \frac { \hat { \sigma } J _ { s p a r s e } } { \hat { \sigma } \rho _ { j } ^ { \mathrm { ~ * ~ } } } \circ s ^ { \prime } \big ( W X + b \otimes 1 _ { n } ^ { \mathrm { ~ \mathrm { ~ \mathrm { ~  ~ } } } } \big ) ] X ^ { \mathrm { T } }
$$

对于标签误差项 $\boldsymbol { J } _ { l a b e l }$ ，关于隐含层表示 $\gamma$ 的偏导数可以表示为 $\frac { \partial J _ { l a b e l } } { \partial Y } = Y \bigg ( Y \hat { \mathcal { \beta } } - T \bigg )$ 。相同地，标签误差项只作用于输入与隐含层之间，只产生它们之间的误差，所以 $\boldsymbol { J } _ { l a b e l }$ 关于 $b$ 和 $w$ 的偏导为

$$
\frac { \partial J _ { _ { l a b e l } } } { \partial b } = \left[ \frac { \partial J _ { _ { l a b e l } } } { \partial Y } \circ s ^ { \prime } \big ( W X + b \otimes 1 _ { n } ^ { \mathrm { T } } \big ) \right] \mathbf { 1 } _ { n }
$$

$$
\frac { \hat { \sigma } J _ { l a b e l } } { \hat { \sigma } W } = \left[ \frac { \hat { \sigma } J _ { l a b e l } } { \hat { \sigma } Y } \circ s ^ { \prime } \big ( W X + b \otimes 1 _ { n } ^ { \mathrm { \scriptscriptstyle T } } \big ) \right] X ^ { \mathrm { \scriptscriptstyle T } }
$$

综合以上重构误差，权重衰减项，稀疏约束项和标签误差项的偏导数，可以得到 SLRAE的目标函数 $J _ { _ { L S R A E } }$ 的偏导数为$\frac { \hat { \sigma } J _ { _ { L S R A E } } } { \hat { \sigma } b } = \frac { \hat { \sigma } J _ { _ { A E } } } { \hat { \sigma } b } + \lambda \frac { \hat { \sigma } J _ { _ { w d } } } { \hat { \sigma } b } + \beta \frac { \hat { \sigma } J _ { _ { s p a r s e } } } { \hat { \sigma } b } + \nu \frac { \hat { \sigma } J _ { _ { l a b e l } } } { \hat { \sigma } b }$ Jlabel (19)$\frac { \hat { \sigma } J _ { L S R A E } } { \hat { \sigma } W } = \frac { \hat { \sigma } J _ { A E } } { \hat { \sigma } W } + \lambda \frac { \hat { \sigma } J _ { { } _ { w d } } } { \hat { \sigma } W } + \beta \frac { \hat { \sigma } J _ { { } _ { s p a r s e } } } { \hat { \sigma } W } + \nu \frac { \hat { \sigma } J _ { { } _ { l a b e l } } } { \hat { \sigma } W }$ Jabel (20)

# 3 实验结果与分析

为了测试算法的性能，将提出的SLRAE与AE，SAE，ELM在一些数据集上做对比实验，然后应用到softmax分类器上进行分类。数据集主要包括6个UCI数据集，分别为PenDigits，Iris，Glass，Seeds，ISOLET，PageBlocks 和1个USPS数据集。具体数据信息如表1所示。算法是在MATLABR2014a环境下进行，操作系统为Windows 7，CPU为 Intel(R)Core(TM)$\mathrm { i } 3 { + } 3 { \cdot } 4 0 \mathrm { G H z }$ ，4GB内存。

表1数据集的规格  

<html><body><table><tr><td>#</td><td>Data sets</td><td>Training</td><td>Testing</td><td>Total</td><td>Attribution</td><td>Classes</td></tr><tr><td>1</td><td>Pen Digits</td><td>7294</td><td>3498</td><td>10992</td><td>16</td><td>10</td></tr><tr><td>2</td><td>USPS</td><td>7291</td><td>2007</td><td>9298</td><td>256</td><td>10</td></tr><tr><td>3</td><td>Iris</td><td>75</td><td>75</td><td>150</td><td>4</td><td>3</td></tr><tr><td>4</td><td>Glass</td><td>214</td><td>140</td><td>354</td><td>10</td><td>7</td></tr><tr><td>5</td><td>Seeds</td><td>210</td><td>150</td><td>360</td><td>7</td><td>3</td></tr><tr><td>6</td><td>ISOLET</td><td>4000</td><td>1473</td><td>5473</td><td>10</td><td>54</td></tr><tr><td>7</td><td>Page Blocks</td><td>6238</td><td>1559</td><td>7797</td><td>617</td><td>26</td></tr></table></body></html>

SLRAE 算法的参数有 $\lambda \ : , \ : \ : \beta$ 和 $\gamma$ ，它们是用来控制公式中各项的相对重要性。对这些参数进行讨论，将这些参数以$\{ 1 \times 1 0 ^ { \mathrm { e } } | \mathrm { e } { = } - 5 , - 4 , - 3 , - 2 , - 1 , 0 , 1 , 2 , 3 , 4 \}$ 的规则变化。图2讨论了SLRAE 使用Pen Digits 数据库时的参数 $\lambda = 0 . 0 0 0 0 1 \mathrm { ~ } , \lambda = 0 . 0 0 0 1$ 和 $\lambda = 0 . 0 0 1$ 的性能。每张图表示一个不同的 $\lambda = 0 . 0 1$ 的值，$\lambda = 0 . 1$ 和 $\lambda = 1$ 轴表示了参数的变化范围，彩条表示精度。可以从图2看出当 $\lambda = 1 0$ ， $\lambda = 1 0 0$ ， $\lambda = 1 0 0 0$ 时，SLRAE 达到最优的情况，分类的准确度达到 $9 9 . 4 \%$ 。 $\lambda { = } 1 0 0 0 0$ ， $\beta$ 和 $\gamma$ 数量级相差大的原因是为了调整惩罚项达到同一个数量级。

![](images/ca1f79f1a71cf1ae1ad5b86c40199b9ca210e9ff36f076cf1838957829781b2f.jpg)

![](images/2b818610ddf8f2bb5f284d74722212316fa24ba21b9bedc8363a075051ae9abd.jpg)  
图2不同 $\lambda \cdot \beta$ 和y下 SLRAE 的性能

为了使比较公平，对比的网络结构有相同的网络结构(即有相同的深度和隐含层节点数)。以上实验得到分类结果最高的参数，之后我们研究神经元数目对性能的影响。本文首先为每个数据集设置最佳的模型参数，然后改变神经元隐含层节点数且固定其他参数。图3显示了PenDigits、USPS和ISOLET数据集的分类结果。根据每个数据集的原始特征数来设置隐含层神经元的节点数。改变隐含层神经元的个数，SLRAE在分类准确率上明显均优于其它算法，如图3(a)可以看出当隐含层节点个数达到100 时，SLRAE用于分类的准确率就达到一个平稳的状态，分类的准确率接近于 $100 \%$ 。从图3(b)中可以看出SLRAE用于分类的准确率差不多维持在 $93 \%$ 上下，实验结果一直比较平稳。SLRAE 用于分类的准确率是很明显高于其它算法。图 3(c)显示可以看出SLRAE用于分类的准确率是明显优于其它算法，不论隐含层节点个数为多少，SLRAE的分类准确率差不多维持在 $9 5 . 5 \%$ 左右。

![](images/9891ed789f6045ec44b46d53791557d6935672a1e858b9f2fd93fb34a2295b00.jpg)  
图3隐含层神经元个数的影响

在接下来的实验中研究不同的迭代次数对 SLRAE，SAE，AE，ELM，LRAE，DBN以及AdaptiveDBN的分类准确率的影响，将其进行对比实验。在刚刚隐含层节点个数对分类准确率的影响的实验中获得了每个方法在每个数据集上分类准确率最高的隐含层节点个数。图4是在PenDigits、USPS和ISOLET数据集上迭代次数对各方法的影响。

![](images/e90c19127bd398df7d009b64d72e044d0e78de21029eae221b20575c553a425c.jpg)  
图4迭代次数的影响

从图4可以看出在各迭代次数的情况下，SLRAE 用于分类的准确率都是很明显高于 SAE，AE，ELM，LRAE，DBN 以及Adaptive DBN这些算法的。从图4(a)中看出迭代次数的对 SLRAE的分类准确率的影响不大，分类准确率高大 $9 9 . 4 1 \%$ 。从图4(b)中看出当迭代次数达到400 时，SLRAE 用于分类的准确率达到稳定状态，分类准确率达到 $9 4 . 4 \%$ 。从图4(c)中看出 SLRAE用于分类的准确率是光滑的，并不随着迭代次数的增加而发生巨大改变，当迭代次数为800时，SLRAE分类准确率最高为 $9 5 . 7 \%$ 。

表2各数据库上运行100次准确率范围  

<html><body><table><tr><td></td><td>AE</td><td>SAE</td><td>ELM</td><td>LRAE</td><td>DBN</td><td>Adaptive DBN</td><td>SLRAE</td></tr><tr><td rowspan="2">Pen Digits</td><td>92.73+0.63</td><td>94.58+0.73</td><td>94.30+1.33</td><td>99.18+0.25</td><td>93.07+2.03</td><td>96.67+1.64</td><td>99.34+0.26</td></tr><tr><td>-0.66</td><td>-0.95</td><td>-1.34</td><td>-0.68</td><td>-2.06</td><td>-4.58</td><td>-0.25</td></tr><tr><td rowspan="2">USPS</td><td>85.87+2.87</td><td>87.79+1.95</td><td>89.75+0.78</td><td>90.55+0.89</td><td>70.35+0</td><td>73.49+1.49</td><td>93.86+0.41</td></tr><tr><td>-2.81</td><td>-3.34</td><td>-1.11</td><td>-1.16</td><td>-0</td><td>-1.48</td><td>-0.44</td></tr><tr><td rowspan="2">Iris</td><td>96.82+1.85</td><td>96.91+1.76</td><td>93.68+4.99</td><td>96.83+1.84</td><td>97.33+0</td><td>95.83+1.5</td><td>98.13+0.54</td></tr><tr><td>-0.82</td><td>-0.91</td><td>-5.68</td><td>-6.16</td><td>-0</td><td>-11.8</td><td>-0.8</td></tr><tr><td rowspan="2">Glass</td><td>83.87+14.73</td><td>96.93+3.07</td><td>90.06+8.07</td><td>85.63+13.44</td><td>98.07+0</td><td>84.46+14.14</td><td>99.24+0.76</td></tr><tr><td>-19.85</td><td>-8.61</td><td>-15.26</td><td>-23.01</td><td>-0</td><td>-24.18</td><td>-0.84</td></tr><tr><td rowspan="2">Seeds</td><td>87.68+8.32</td><td>96.80+1.20</td><td>98.02+1.31</td><td>87.78+6.89</td><td>97.33+0</td><td>98.03+1.97</td><td>98.67+1.33</td></tr><tr><td>-13.68</td><td>-1.47</td><td>-2.69</td><td>-11.78</td><td>-0</td><td>-5.36</td><td>-1.34</td></tr><tr><td rowspan="2">ISOLET</td><td>84.66+2.83</td><td>84.39+2.52</td><td>78.27+3.77</td><td>94.05+1.20</td><td>82.26+1.68</td><td>87.62+2.37</td><td>94.25+1.06</td></tr><tr><td>-2.49</td><td>-2.99</td><td>-2.84</td><td>-1.31</td><td>-1.24</td><td>-2.54</td><td>-1.18</td></tr><tr><td rowspan="2">Page Blocks</td><td>88.35+5.46</td><td>86.33+1.31</td><td>92.41+2.49</td><td>92.71+1.71</td><td>86.33+0</td><td>88.55+4.85</td><td>94.25+0.95</td></tr><tr><td>-18.35</td><td>-2.56</td><td>-3.16</td><td>-14.89</td><td>-0</td><td>-2.36</td><td>-2.18</td></tr></table></body></html>

表2中各数据的上一行表示的是平均准确率与到最大准确率的波动，下一行表示的是到最小准确率的波动。通过表2可以看出SLRAE方法在各数据集上的分类准确率的波动都较小，有时波动大于DBN，DBN在数据集USPS、Iris、Glass、Seeds和PageBlocks上的波动为0，但是SLRAE的平均分类准确率是高于DBN以及其它算法的，所以SLRAE用于分类的优势是明显高于其他算法的。

# 4 结束语

在本文中，将稀疏和标签正则化加入到自动编码机中提出一个半监督自动编码机(SLRAE)。添加稀疏约束项可以有效地提取隐含层结构，学习更复杂的非线性函数，更准确地提取样本的本质特征，添加标签约束项通过减小实际标签和期望标签的误差，使分类精度高于有监督和无监督模型。单独使用稀疏约束项没有用到目标信息不利于用到分类中，单独的加入标签项导致学习到的特征不能很好的表示原始的数据，泛化能力变弱，模型容易过度拟合。所以针对这一问题，为了发挥无监督学习与监督学习的优势，提出了加入稀疏约束项和标签项的半监督自动编码机，通过对自编码参数和分类参数的同时优化来达到既可以保留原数据特征，保证模型的泛化能力，又可以实现较好分类效果的目的。

# 参考文献：

[1]Hinton G E,Osindero S,Teh YW.A fast learning algorithm for deep belief nets [J].Neural Computation,2014,18(7):1527-1554.   
[2]Bengio Y.Learning deep architectures for AI[M].[S.1.] $\because$ Now Publishers, 2009.   
[3]Li Deng，Dong Yu.Deep learning:methods and applications [J]. Foundations & Trends in Signal Processing,2014,7(3):197-387.   
[4]Bengio Y,Lamblin P,Popovici D,et al. Greedy layer-wise training of deep networks [Cl//Advances in Neural Information Processing Systems.2007: 153-160.   
[5]Sun Wenjun,Shao Siyu, Zhao Rui,et al.A sparse auto-encoder-based deep neural network approach for induction motor faults classification [J]. Measurement,2016,89:171-178.   
[6]Vincent P,Larochelle H,Bengio Y,et al. Extracting and composing robust features with denoising autoencoders [C]//Proc of International Conference on Machine Learning.New York:ACM Press,2008:1096-1103.   
[7]Vincent P,Larochelle H, Lajoie I,et al. Stacked denoising autoencoders: learning useful representations in a deep network with a local denoising criterion [J]. Journal of Machine Learning Research,2010,11(12): 3371- 3408.   
[8]Rifai S,Mesnil G,Vincent P,et al.Higher order contractive auto-encoder [M]//Machine Learning and Knowledge Discovery in Databases.Berlin: Springer,2011: 645-660.   
[9]Liu Yanan,Feng Xiaoqing,Zhou Zhiguang.Multimodal video classification with stacked contractive autoencoders [J]. Signal Processing,2016,120: 761-766.   
[10]Du Bo,Wei Xiong,Jia Wu,et al. Stacked Convolutional Denoising AutoEncoders for Feature Representation [J].IEEE Trans on Cybernetics,2016, 99: 1-11.   
[11]Liu Weifeng,Ma Tengzhou,Xie Qiangsheng,etal.LMAE:a large margin auto-encoders for classification [J]. Signal Processing,2017,141:137-143.   
[12] http://www.datatang.com/data/11927 [EB/OL].   
[13] Blake C,Merz C.Uci repository of machine learning databases [DB/OL]. 1998.   
[14] Liu Ping,Han Shizhong,Meng Zibo,et al.Facial expression recognition via a boosted deep belief network [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.Washington DC:IEEE Computer Society, 2014:1805-1812.   
[15]Kamada S,Ichimura T.An adaptive learning method of deep belief network by layer generation algorithm [C]// Proc of Region 10 Conference.2017: 2967-2970.   
[16] Zou Qiang,Fang Hui,Liu Fei,et al.Comparative study of distance discriminant analysis and BP neural network for identification of rapeseed cultivars using visible//near infrared spectra [C]// IFIP Advances in Information & Communication Technology,2017,347: 124-133.   
[17] Huang GuangBin, Zhu QinYu, Siew C K.Extreme learning machine: Theory and applications [J].Neurocomputing,2006,70 (1-3): 489-501.   
[18] Huang Guangbin,Wang Dianhui, Lan Yuan.Extreme learning machines: a survey [J].International Journal of Machine Learning& Cybernetics,2011, 2 (2): 107-122.   
[19]林雨．极限学习机与自动编码器的融合算法研究[D].长春：吉林大学, 2016.(Lin Yu.Research on fusion algorithm of extreme learning machine and auto-encoder [D]. Changchun: Jilin University,2016.)