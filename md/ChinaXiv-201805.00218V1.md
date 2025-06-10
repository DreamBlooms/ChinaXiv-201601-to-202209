# 基于雅克比稀疏自动编码机的手写数字识别算法

王慧玲a，宋威a,b

(江南大学a.物联网工程学院;b.物联网技术应用教育部工程研究中心，江苏 无锡 214122)

摘要：由于手写数字边缘轮廓差异大造成书写风格的不同，为了提高识别准确度，通过在自动编码机中加入稀疏约束项和雅克比正则项，提出一种雅克比稀疏自动编码机(JSAE)的算法进行手写数字识别。加入稀疏约束项能够有效提取数据中的隐藏结构，而雅克比正则化可以描述数据点的边缘特征，提高自动编码器算法的学习能力，从而更准确地抽取样本的本质特征。实验结果表明，JSAE 在分类准确率上要高于自动编码机（AE）和稀疏自动编码机（SAE）算法。

关键词：手写数字识别；雅克比正则化；稀疏约束项；自动编码机；边缘特征 中图分类号：TP391.4 doi: 10.3969/j.issn.1001-3695.2017.07.0684

# JSAE: Jacobian regularized sparse auto-encoders on MNIST database

Wang Huilinga, Song Weia, b (a.SchoolofInternetofThings Engineering,b.Engineering ResearchCenterofInternetofThingsTechnologyApplications, Ministry of Education Jiangnan University,Wuxi Jiangsu 214122,China)

Abstract: Due tothediferenceofhandwritingcausedbythelargediferences inedgecontour,thispaperproposedanalgorithm named Jacobianregularized sparse automatic encoding machine (JSAE)for handwriting identification.This algorithmadded sparse constraint and Jacobi regular item into the automatic coding machine,which improves therecognition accuracy.The sparse constraintcan extract hidden structure from thedata effectivelyand theregularized Jacobican describe the marginal featuresof point data,thus itenables the learningabilityof auto-encoder algorithm to improveandobtaintheessential characteristicsofthe sample more accurately.Experimentalresults showthat JSAE outperforms the basicauto-encoders (AE) and sparse auto-encoders(SAE) .

Key Words: MNIST database; Jacobi regularization; sparse constraint; Auto-encoder; marginal feature

# 0 引言

深度学习是在人工神经网络的基础上发展起来的，具有多层隐含层的多层感知机就是一种深度机构。深度学习通过组合低层特征形成抽象的高层特征来表示对象属性的类别或者特征，可以发现数据的分布式特征。深度学习采用了不同的训练机制来克服传统的神经网络中的常见问题。传统的神经网络一般采用梯度下降法，它的步骤是：随机初始化参数、计算结果、求误差、修正等，通过反复迭代来训练网络，但是会出现数据获取、局部极值、梯度弥散等问题。深度学习的深层次部分采取梯度下降法会导致残差变得极小，梯度扩散，不能达到修正效果，所以梯度下降法不适合应用在深度学习的研究中，深度学习采用逐层初始化的方法，通过无监督学习实现。

随着信息技术的发展，手写数字识别[II[2]的应用需求越来越广泛。在手写数字识别这个方向上，研究工作者已经开始把它推广到各种实际应用中。比如，大规模数据统计中的应用；财务、税务、金融领域的应用；邮件分拣中的应用等。按照提取字符特征的不同，现有的数字手写识别算法主要分成两类：一类是基于结构特征的手写字体识别算法，它们通过识别字符图像内部包含的凹陷区特征、轮廓特征、结构突变点特征等基元，采用模板匹配的方式实现手写数字的自动识别[3]4]。这类方法能够直观地描述字符的结构，但是存在着对字符形变及噪声鲁棒性差的问题；另外一类是基于统计特征的手写数字识别算法，这类算法基于大量样本的表征、变换和学习，通过估计不同样本类别的特征空间分布训练相应的分类器，并利用这些分类器对未知模式进行分类。当训练样本选取足够充分时，这类算法能够具有很好的识别能力[5.6]。

自动编码机(auto-encoder,AE)是一种很有前景的非概率表示范式的机器学习算法，它可以很好地学习有效特征来发掘隐藏在巨大数据下的潜在解释性因素。近些年来，自动编码机受到越来越多的关注，并且被申请作为机器学习和信号处理的应用程序，比如领域适应[7,8]、散列法[9]、人脸对齐[10]、人类手势识别[I]、语音信息处理[12]和自然语言处理[13]。

自动编码机是一种非监督学习算法，尝试学习一个函数使得函数的输出近似表示输入，用于提取输入数据的高层特征。模型是通过最小化输入样本数据与样本重构之间的误差，学习得到模型的参数。为了取得更好的泛化特征，近年来研究人员提出了许多不同的正则化自动编码机来获取潜在的数据分布结构。一般来说，自动编码机可以分为以下四类：稀疏自动编码机[14]；降噪自动编码机[15]；收缩自动编码机[16]；拉普拉斯算子自动编码机[17]。稀疏自动编码机通过在隐藏层节点中加入一个稀疏性限制来达到学习数据特征的目的，从而获得输入数据维数更有意义的表示。降噪自动编码机是尝试通过最小化降噪重构误差，从含有随机噪声的数据中重构真实的原始输入。收缩自动编码机的训练目标函数是重构误差和收缩惩罚项的总和，通过最小化该目标函数使已学习到的特征表示尽量对输入数据保持不变。拉普拉斯算子自动编码机使用拉普拉斯算子正则化来增强数据点所学到的编码器的局部保留性能。

受到稀疏自动编码机和拉普拉斯算子自动编码机这些具有代表性的自动编码机思想的启发，本文把雅克比正则化和稀疏性约束融入到自动编码机算法中，提出了一个新的自动编码机即雅克比稀疏自动编码机（JSAE)。本文所提出的JSAE具有两个优势：a）把雅克比正则化加入到编码中，JSAE可以保留边缘特征的结构，使得特征提取更加完备，信息利用更加充分;b)把稀疏性约束加入到编码中，JSAE对噪声有很好的鲁棒性，还可以有效地提取数据中隐藏的结构，使分类效果达到更好。

为了评估实验的有效性，本文对手写数字数据集做了大量的实验，还与自动编码机，稀疏自动编码机进行比较，实验结果表明JSAE在准确率上要优于其他的算法。

# 1 自动编码机(AE)

自动编码器的概念是20世纪80年代晚期被提出来的，基本的自动编码器由三层神经网络组成，包括输入层、隐含层和输出层，输入层与输出层的神经元的节点数相同，其结构如图1，其中 $L _ { \mathrm { _ { 1 } } }$ 层为输入层， $L _ { _ 2 }$ 层为隐含层， $L _ { _ 3 }$ 层为输出层，输入层与隐含层以及隐含层与输入层的神经元之间都由不同的权值W连接，每个隐含层神经元和输出层神经元都连接着偏置 $b$ ，隐含层节点数和输入输出节点数可根据不同情况设定。

图2为自动编码机模型[18]，用函数 $f _ { \theta }$ 对输入向量 $x$ 进行映射，获得中间层表示 $y$ ，再用函数 $g _ { \theta }$ 对中间层表示进行映射获得重构数据 $z$ 。自动编码机通过最小化损失函数 $L ( x , z )$ 来微调网络权值 $w$ ，通过最小化重构误差调整和优化参数 $\theta$ ，$\theta = \{ { W } , { b } \} ;$

$$
\begin{array} { l } { { \theta ^ { * } , \theta ^ { * } = \arg \operatorname* { m i n } _ { \theta , \theta } \sum _ { i = 1 } ^ { n } L \big ( x ^ { i } , z ^ { i } \big ) } } \\ { { = \arg \operatorname* { m i n } _ { \theta , \theta } \sum _ { i = 1 } ^ { n } L ( x ^ { i } , g _ { \theta } , ( f _ { \theta } ( x ^ { i } ) ) ) } } \end{array}
$$

其中： $n$ 为训练数据的数量， $x$ 是训练样本，$y = f _ { \theta } ( x ) = s ( W x + b )$ 和 $\boldsymbol { Z } = \boldsymbol { g } _ { \boldsymbol { \theta } ^ { \prime } } ( \boldsymbol { y } ) = s ( W ^ { \prime } \boldsymbol { y } + \boldsymbol { b } ^ { \prime } )$ 分别为编码与解码函数。 $\mathbf { \Omega } _ { L }$ 为损失函数，比如传统的平方差函数$L ( x , z ) = \left\| x - z \right\| ^ { 2 } \circ$

![](images/e97b7aeb210b99a6c53574f1fe5f325e55944713ee12151a42e7d717a7340924.jpg)  
图1自动编码机结构图

![](images/8e6e6836354b76ae0d202b49c1169a17845311edc2fda81557c7c38bbc221cb5.jpg)  
图2自动编码机模型

自编码训练算法使用BP算法,此时自动编码器的损失函数可表示为

$$
J = J _ { _ { A E } } + \lambda J _ { _ { w d } }
$$

其中： $J _ { _ { A E } } = \frac { 1 } { 2 m } \sum _ { i = 1 } ^ { m } \Bigl ( \bigl \| h _ { _ { w , b } } \bigl ( \boldsymbol { X } ^ { ( i ) } \bigr ) - \boldsymbol { y } ^ { ( i ) } \bigr \| ^ { 2 } \Bigr )$ 为重构误差项, $h _ { w , b } \left( \boldsymbol { X } ^ { ( i ) } \right)$ 为第 $i$ 个神经元的激活值， $J _ { _ { w d } } = \frac { 1 } { 2 } \sum _ { l = 1 } ^ { n _ { l } - 1 } \sum _ { i = 1 } ^ { s _ { l } } \sum _ { j = 1 } ^ { s _ { l + 1 } } \bigl ( W _ { j i } ^ { l } \bigr ) ^ { 2 }$ 为权重衰减项,衰减项目的是减小权重的幅度，防止过拟合， $\lambda$ 为系数。

# 2 雅克比稀疏自动编码机（JSAE)

本文把稀疏性约束和雅克比正则化融入到自动编码机算法中，提出了一种新的自动编码机即雅克比稀疏自动编码机（JSAE)。和人脑一样，若某个输入只是刺激到某些神经元，则其他大部分神经元是受到抑制的。本文引入稀疏约束项，使隐含层只有很少几个非零元素或只有很少几个远大于零的元素，让隐含层神经元的激活度满足一定的稀疏性，能够更有效地找出隐含在输入数据内部的结构与模式，因此稀疏的表达往往比其他的表达有效。手写数字图像中变化剧烈的像素点也就是边缘轮廓比较重要，蕴含着丰富的内在信息图像。雅克比正则项是求得输入数据的一个雅克比矩阵，将其局部线性化，局部空间收缩，获得图像的边缘特征，挖掘图像中关于形状和反射或透射比的信息，对输入数据的微小的变化具有不变性和鲁棒性。简而言之，它的优点有两个：第一，把雅克比正则化加入到编码中，JSAE可以保留边缘特征的结构，第二，把稀疏性约束加入到编码中，JSAE对噪声有很好的鲁棒性，还可以有效地提取数据中隐藏的结构，有效的利用了特征，达到更好的应用效果。图3为JSAE用于分类的框架。

![](images/64473ea0d1d696c7dcf4558b09a2a5e0844167e893d537db94e89b5f0d2955a5.jpg)  
图3JSAE用于分类的框架

输入向量表示为 $\boldsymbol { x } \in [ 0 , 1 ] ^ { n }$ ， $\boldsymbol { y } \in [ 0 , 1 ] ^ { s }$ 表示把输入映射到隐藏层，其中 $\pmb { y } = f _ { \theta } ( \pmb { x } ) = s ( \pmb { W } \pmb { x } + \pmb { b } )$ ，其中网络参数 $\theta = \{ { W } , { b } \}$ ，$s ( x ) = 1 / \left( 1 + e ^ { - x } \right)$ 是 sigmoid 函数。 $w$ 是 $s \times n$ 的权值矩阵， $b$ 是偏置向量，中间层输出 $y$ 再次通过映射构造出向量 $\boldsymbol { z } \in [ 0 , 1 ] ^ { n }$ ，映射函数 $Z = g _ { _ { \theta } } ( y ) = s ( W y + b )$ ，其中网络参数为 $\theta ^ { ' } = \{ { w } , { b } \}$ w是大小为 $n \times s$ 的权值矩阵，并且可以通过限定使得W=WT [19]。

当中间层神经元数量较多时，通常加入稀疏性限制，这样可以保证学习到更加局部并且信息丰富的结构。每次迭代之前先统计中间层神经元对所有训练样本的平均激活度：

$$
\rho _ { j } ^ { \ast } = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } [ \pmb { \mathscr { a } } _ { j } ^ { ( 2 ) } ( { \pmb { X } } ^ { i } ) ]
$$

其中： $\mathbf { \Sigma } _ { m }$ 为样本数量， $i$ 为样本编号 $i \in { \left( 1 , 2 , 3 , . . . , m \right) }$ ， $j$ 为中间层神经元编号， $a _ { _ j } \big ( \boldsymbol x ^ { i } \big )$ 为第 $j$ 个神经元对第 $i$ 个样本的激活值。在稀疏性限制的条件下，可得公式：

$$
{ \rho } _ { _ j } ^ { \ast } = \rho
$$

其中： $\rho$ 是稀疏性参数，通常情况下，设定稀疏性限制参数为一个接近于0的数，加入限制项让隐含层节点的平均激活值接近稀疏性参数，常用的限制为KL相对熵，即

$$
J _ { _ { s p a r s e } } = \sum _ { j = 1 } ^ { s } K L \Big ( \rho \left. \rho _ { j } ^ { \cdot } \right. = \sum _ { j = 1 } ^ { s } \rho \log \frac { \rho } { \rho _ { j } ^ { \cdot } } + ( 1 - \rho ) \log \frac { 1 - \rho } { 1 - \rho _ { j } ^ { \cdot } } +
$$

具体来说，JSAE主要包含三项：重构误差项；稀疏约束项；雅克比正则项。重构误差项是训练样本与它所重构出的数据的差值。稀疏约束项是加强所学特征的稀疏性，有效地提取数据中的隐藏结构。雅克比正则项是描述数据点的边缘特征，保留手写数字最重要的特征。雅克比稀疏自动编码机的代价函数为

$$
J _ { _ { J S A E } } = J _ { _ { A E } } + \lambda J _ { _ { w d } } + \beta J _ { _ { s p a r s e } } + \nu J _ { _ { j a c o b i } }
$$

其中： $\lambda \stackrel { , } { \quad } \beta$ 和 $\nu$ 是用来控制公式中各项的相对重要性的参数。第一项 $J _ { _ { A E } } = \frac { 1 } { 2 m } \sum _ { i = 1 } ^ { m } \bigl ( \| h _ { _ { w , b } } \bigl ( X ^ { \left( i \right) } \bigr ) - y ^ { \left( i \right) } \| ^ { 2 } \bigr )$ 是训练样本的重构误差项，第二项 $J _ { _ { w d } } = \frac { 1 } { 2 } \sum _ { l = 1 } ^ { n _ { l } - 1 } \sum _ { i = 1 } ^ { s _ { i } } \sum _ { j = 1 } ^ { s _ { l + 1 } } ( W _ { j i } ^ { l } ) ^ { 2 }$ 是为了防止权重过度拟合的权重衰减项 第三项$J _ { _ { s p a r s e } } = \sum _ { j = 1 } ^ { s } K L \Big ( \rho \left. \rho _ { j } ^ { \circ } \right. \rho _ { j } ^ { \circ } \Big ) = \sum _ { j = 1 } ^ { s } \rho \log \frac { \rho } { \rho _ { j } ^ { \circ } } + ( 1 - \rho ) \log \frac { 1 - \rho } { 1 - \rho _ { j } ^ { \circ } } *$ 1-，是稀疏惩罚项，在隐藏神经元数量较多的情况下仍然可以发现输入数据中重要的结构。用 $K L ( \rho \| \rho _ { _ j } ^ { * } )$ 表示隐层神经元 $j$ 的惩罚因子,即 $K L ( \rho \left. \right. \rho _ { j } ^ { * } ) = \rho \log \frac { \rho } { \rho _ { j } ^ { * } } + \bigl ( 1 - \rho \bigr ) \log \frac { 1 - \rho } { 1 - \rho _ { j } ^ { * } }$ 其中，$\rho _ { j } ^ { \cdot } = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } [ \pmb { \mathscr { a } } _ { j } ^ { \scriptscriptstyle ( 2 ) } ( { \pmb { \chi } } ^ { i } ) ]$ 表示隐含层神经元 $j$ 的平均激活度， $\rho$ 为稀疏性参数，通常 $\rho$ 是一个接近于0 的较小的值，当 $\rho _ { j } ^ { * } = \rho$ 时，$K L ( \rho \| \rho _ { ; } ^ { * } ) = 0$ ，且随着 $\rho _ { j } ^ { * }$ 与 $\rho$ 之间的差异增大而单调递增。设定 ${ \rho } = 0 . 1$ ， $K L ( \rho \| \rho _ { j } ^ { * } )$ 随着 $\rho _ { j } ^ { * }$ 变化的曲线图如图4所示。最后一项 $J _ { _ { j a c o b i } } = \frac { 1 } { 2 m } { \sum _ { i = 1 } ^ { m } } \Bigl ( \left\| X ^ { ( i ) } - J ^ { ( i ) } \right\| ^ { 2 } \Bigr )$ 为描述手写字体识别数据点的边缘特征的雅克比正则项，其中 $J ^ { ( i ) }$ 是用训练样本用Jacobi 函数计算出来的雅克比矩阵。

![](images/6e38977c6522c537ea23ca1e2b84872ed1d653e4a08b30a9e3587da9e598fd33.jpg)  
图4惩罚因子曲线图

本文中，用梯度下降法最小化代价函数[20]，通过以下公式迭代更新 $w$ 和 $b$ ：

$$
W _ { _ { i j } } ^ { ( l ) } = W _ { _ { i j } } ^ { ( l ) } - \alpha \frac { \hat { \sigma } J ( W , b ) } { \hat { \sigma } W _ { _ { i j } } ^ { ( l ) } }
$$

$$
b _ { i } ^ { ( l ) } = b _ { i } ^ { ( l ) } - \alpha \frac { \hat { \sigma } J \big ( W , b \big ) } { \hat { \sigma } b _ { i } ^ { ( l ) } }
$$

其中： $\alpha$ 是学习速率，其中关键步骤是计算偏导数，用反向传播算法来计算偏导数。通过单个样例 $\big ( x , y \big )$ 的代价函数$J ( W , b ; x , y )$ 推导出整个代价函数 $\boldsymbol { J } ( W , b )$ 的偏导数：

$$
\frac { \hat { \sigma } J ( W , b ) } { \hat { \sigma } W _ { i j } ^ { ( l ) } } = \left[ \frac { 1 } { m } \sum _ { i = 1 } ^ { n } \frac { \hat { \sigma } } { \hat { \sigma } W _ { i j } ^ { ( l ) } } J ( W , b ; \pmb { \chi } ^ { ( i ) } , \pmb { \chi } ^ { ( i ) } ) \right] + \lambda W _ { i j } ^ { ( l ) }
$$

$$
\frac { \hat { \sigma } J ( W , b ) } { \hat { \sigma } b _ { i } ^ { ( i ) } } { = } \frac { 1 } { m } { \sum _ { i = 1 } ^ { m } } \frac { \hat { \sigma } } { \hat { \sigma } b _ { i } ^ { ( i ) } } J ( W , b ; x ^ { ( i ) } , y ^ { ( i ) } )
$$

可以得到JSAE的偏导数如下：

$$
\frac { \hat { \sigma } J _ { _ { J S A E } } } { \hat { \sigma } W } = \frac { \hat { \sigma } J _ { _ { A E } } } { \hat { \sigma } W } + \lambda \frac { \hat { \sigma } J _ { _ { w d } } } { \hat { \sigma } W } + \beta \frac { \hat { \sigma } J _ { _ { s p a r s e } } } { \hat { \sigma } W } + \nu \frac { \hat { \sigma } J _ { _ { j a c o b i } } } { \hat { \sigma } W }
$$

$$
\frac { \hat { \sigma } J _ { _ { J S A E } } } { \hat { \sigma } b } = \frac { \hat { \sigma } J _ { _ { A E } } } { \hat { \sigma } b } + \lambda \frac { \hat { \sigma } J _ { _ { w d } } } { \hat { \sigma } b } + \beta \frac { \hat { \sigma } J _ { _ { s p a r s e } } } { \hat { \sigma } b } + \nu \frac { \hat { \sigma } J _ { _ { j a c o b i } } } { \hat { \sigma } b }
$$

整个算法主要过程描述如下：

输入： $N$ 个输入样本 $X _ { i } = \left[ x _ { _ { i 1 } } , X _ { _ { i 2 } } , . . . , X _ { _ { i n } } \right] ^ { T } \in R ^ { n }$

a)计算出训练样本的重构误差项 $J _ { _ { A E } }$ ’  
$J _ { _ { A E } } = { \frac { 1 } { 2 m } } { \sum _ { i = 1 } ^ { m } } \bigl ( \| h _ { _ { w , b } } \bigl ( X ^ { \left( i \right) } \bigr ) - y ^ { \left( i \right) } \| ^ { 2 } \bigr ) ;$ （20b)计算出防止过拟合的权重衰减项 $J _ { _ { w d } }$ ，  
$J _ { _ { w d } } = { \frac { 1 } { 2 } } \sum _ { l = 1 } ^ { n _ { l } - 1 } \sum _ { i = 1 } ^ { s _ { l } } \sum _ { j = 1 } ^ { s _ { l + 1 } } ( W _ { j i } ^ { l } ) ^ { 2 } \ ;$ （2c)计算出使隐含层节点具有稀疏性质的稀疏惩罚项 $J _ { \it { s p a r s e } }$ （204号  
$J _ { _ { s p a r s e } } = \sum _ { j = 1 } ^ { s } \rho \mathrm { l o g } \frac { \rho } { \rho _ { j } ^ { \ast } } + \left( 1 - \rho \right) \mathrm { l o g } \frac { 1 - \rho } { 1 - \rho _ { j } ^ { \ast } } \mathrm { ~ ; ~ }$ d)计算出具有保留边缘特征的雅克比正则项Jjoi，  
$J _ { _ { _ { j a c o b i } } } = { \frac { 1 } { 2 m } } { \sum _ { i = 1 } ^ { m } } \Big ( \Big \| X ^ { ( i ) } - J ^ { ( i ) } \Big \| ^ { 2 } \Big ) \quad ;$ （2e)得出雅克比稀疏自动编码机的代价函数：  
$J _ { _ { J S A E } } = J _ { _ { A E } } + \lambda J _ { _ { w d } } + \beta J _ { _ { s p a r s e } } + \nu J _ { _ { j a c o b i } }$ ：f)随机初始化权值 $w$ 和偏置 $b$ ，前向传播计算出隐含层节  
点的值;g)使用梯度下降法最小化代价函数，得到最优的权值 $w$ 和  
偏置 $b$ ：输出：编码参数 $\theta = \{ { W } , { b } \}$ 和解码参数 $\theta ^ { \prime } = \{ { W } , { b } \}$ 。

本文简单分析了雅克比优化算法的时间复杂度，计算出$J _ { _ { A E } }$ 和偏导 $ { \hat { o } } J _ { _ { A E } }$ 的时间复杂度是 $O ( s n m )$ ，计算出 $J _ { _ { w d } }$ 和偏导$ { \hat { o } } J _ {  { w d } }$ 的时间复杂度是 $O ( s n )$ ，计算出 $J _ { _ { \it s p a r s e } }$ 和偏导 ${ \partial J } _ { \it { s p a r s e } }$ 的时间复杂度是 $O ( s n m )$ ，计算出 $J _ { _ { j a c o b i } }$ 和偏导 ${ \hat { \partial } } J _ { _ { j a c o b i } }$ 的时间复杂度是$O ( s n ^ { 2 } m )$ 。因此，本文所提出的JSAE 算法对于每次迭代总的时间复杂度是O(sn²m)

# 3 实验结果与分析

实验是在MATLABR2014b上进行，计算机系统配置如下:CPU为Intel(R)Coreli3-3240；主频为 $3 . 4 0 ~ \mathrm { G H z }$ ；内存为4GB；操作系统为MicrosoftWindows7。本文实验使用的数据库为MNIST手写数字识别数据集，Pen-Based RecognitionofHandwrittenDigits 和USPS 数据集。

# 3.1实验数据集

<html><body><table><tr><td>数据集名称</td><td>样本数属性数分类数</td><td></td></tr><tr><td>MNIST手写数字</td><td>70000 784</td><td>10</td></tr><tr><td>Pen-Based Recognition of Handwritten Digits 10992</td><td>16</td><td>10</td></tr><tr><td>USPS</td><td>9298 256</td><td>10</td></tr></table></body></html>

# 3.2 实验结果分析

3.2.1MNIST手写数字

MNIST具有60000张手写数字图像的训练库和10000张手写数字图像的测试库。图像一共分为10类，是0到9的阿拉伯手写数字。每张图片均是 $2 8 ^ { * } 2 8$ 个像素点，每个像素点取0到255之间的灰度值，0是黑色，255是白色，其中白色作为背景。图5随机显示的72张MNIST手写数字识别图像库中的图片。

D 回 □ □ 回 @ D 回 D0_971.bmp 0,972.bmp 0.973.bmp 0.974.bmp 0,975.bmp 0,976.bmp 0,977.bmp 0_978.bmp 0,979.bmp1 1 1 1 1 1 1 ■ 11,126.bmp 1_1127.bmp 1_1128.bmp 1_1129.bmp 1,1130.bmp 1,1131bmp 1,1132.bmp 1,1133.bmp 1,1134.bmp国 国 国 国 ? 因 ② 3 32_1025.bmp 2_1026.bmp 2_1027.bmp 2_1028.bmp 2,1029.bmp 2_1030.bmp 2_1031.bmp 3_1003.bmp 3_1004.bmpB 国 E 国 国 图 国 四 M3_1005.bmp 3_1006.bmp 3_1007.bmp 3_1008.bmp 3_1009.bmp 4,974.bmp 4_975.bmp 4,976.bmp 4,977.5mp? 国 日 图 国 □ 国 G G4,978.bmp 4_979.bmp 4_980.bmp 4_981.bmp 5_887.bmp 5.888.bmp 5_889.bmp 5_890.bmp 5_891.bmp□ N 4 国 □ 4 □ 4 □6_948.bmp 6_949.bmp 6_950.bmp 6_951.bmp 6.952.bmp 6_953.bmp 6_954.bmp 6_955.bmp 6_956.bmp回 7 1 2 7 2 7 2 76_957.bmp 7_1020.bmp 7_1021.bmp 7_1022.bmp 7_1023.bmp 7_1024.bmp 7_1025.bmp 7_1026.bmp 7_1027.bmp? 区 √ E ? 国 1 国8_969.bmp 8,970.bmp 8_971.bmp 8_972.bmp 8.973.bmp 9_1005.bmp 9_1006.bmp 9_1007.bmp 9_1008.bmpD 回 D □ 回 回 回 回 D

为了验证本文提出的方法的有效性，在手写字体识别数据库上做实验，其中分别选取了1500张，2000张，2500张，3000张，3500张和4000张训练图片，原始的测试数据集10000 张图片。本文使用了softmax分类器对所学到的编码进行分类。本文还将所提出的JSAE 算法与基础的自动编码机和稀疏自动编码机做了对比实验。

![](images/01b7d71e42f58762dd0c9f497884abd2c0c1bac4decccb4de93f1d3122521bdc.jpg)  
图5MNIST手写数字图像库原库  
图6在MNIST数据集上的三种自动编码机的分类准确率

图6显示了三种自动编码机在手写字体识别数据库上的分类准确率。由于MNIST数据库较大，本文的实验都是做10次实验取其平均值，从中随机抽取训练样本，测试样本数保持不变，所以导致小数据库的分类准确率小于原库的分类准确率。可以看出，在6种数据集中，本文提出的雅克比稀疏自动编码机在MNIST的小数据库的分类准确率均要优于自动编码机与稀疏自动编码机，JSAE通过描述数据点的边缘特征并有效地提取数据中的隐藏结构，因此性能优势更加明显。而且随着训练数据集的增加准确率也随之增加。

在训练样本个数为 2000 的情况下，还对 JSAE 的参数 $\lambda$ ，β和γ进行讨论，将这些参数以{1×10|e=-6,-5,-4,-3,-2,-1,0,1,2} 的规则变化，本文通过大量的实验表明 $\gamma$ 的变化不影响分类的准确率，因为雅克比正则项是对数据点边缘特征的描述，是对输入数据作线性化处理，再将其求和使得每一个学习到的特征具有局部不变性，所以改变γ的值是不会对结果有影响。因而只需对 $\lambda$ 和 $\beta$ 进行讨论，能够完全反映代价函数中参数对实验结果的影响。图7是 $\lambda$ 和$\beta$ 的不同取值对JSAE 的分类准确率的影响， $\lambda$ 和 $\beta$ 轴显示的是参数的变化范围， $z$ 轴显示的是手写字体识别分类的准确率。通过该三维的图像可以看出JSAE分类结果稳定，基本在 $90 \%$ 以上。在原库的情况下，分类的准确率要更高。

![](images/06e4849f26518ea968e8cbc44f4862c31b991d295294303154fcf0355e616d88.jpg)  
图7不同 $\lambda$ 和 $\beta$ 下的 JSAE 分类准确率

本文还讨论了JSAE 算法的训练迭代次数对分类准确性的影响，分别在迭代次数250,350,450,550,650,750进行实验，将其与AE和SAE对比，图8为迭代次数的不同对三种算法的分类准确率的影响。可以看出相同迭代次数下JSAE的分类准确率大部分是高于AE和SAE，在迭代次数为450时，结果达到最好，而AE和SAE在迭代次数为150时结果达到最好，说明在迭代次数多时JSAE更能体现准确率的优势。

![](images/536acf057a855eb691054a4d8f8e184932e0d913626e363e0e00a1c46490a8b2.jpg)  
图8在MNIST数据集上的三种自动编码机不同选代次数的分类准确率

# 3.2.2Pen-Based Recognition of Handwritten Digits 数据集

Pen-Based Recognition ofHandwrittenDigits 数据集有10992个样本，其中7494个是训练样本，3498个是测试样本（数据集出自http://archive.ics.uci.edu $/ \mathrm { m l } / \$ )，为了避免实验结果的偶然性，每次实验从10992个样本中随机抽取5496个作为训练数据集，5496个作为测试数据集。图9为在Pen-BasedRecognitionofHandwrittenDigits数据集上的三种自动编码机不同迭代次数的分类准确率比较，可以看出JSAE的准确率明显高于另外两个自动编码机，基本保持在 $96 \%$ 以上，当迭代次数为350时，JSAE准确率达到 $9 7 . 5 3 \%$ 。

![](images/d79f04cbca3b9c67cdc5f382dfad6a6c9b44dafed193da51783aa686c07f52cf.jpg)  
图9在 Pen-Based Recognition of Handwritten Digits数据集上的三种自动编码机不同迭代次数的分类准确率

# 3.2.3USPS数据集

USPS数据集是采用USPS美国邮政服务手写数字识别库，库中均为 $1 6 ^ { * } 1 6$ 像素的灰度图像的值，（数据集出自http://www.datatang.com/data/11927)，灰度值已被归一化。库中共有9298个手写数字图像，其中7291个数据用于训练，2007个数据用于测试。图10为在USPS数据集上的三种自动编码机不同迭代次数的分类准确率比较，可以看出JSAE的分类准确率相对比较稳定，维持在 $96 \%$ 左右，分类准确率均高于SAE和SAE，具有一定的意义。

![](images/ba72e57fe1386fa5d8eeb07c25af661617702b7907d585ffafb4d45e49d79a98.jpg)  
图10在USPS数据集三种自动编码机不同迭代次数的分类准确率

# 4 结束语

学习手写数字识别的有效特征是分类达到好的效果的重要因素之一，本文对自动编码机进行改进，提出了一种雅克比稀疏自动编码机(JSAE)，通过雅克比正则化描述数据点的边缘特征，线性化输入数据，将手写数字图像最有意义的特征部分提取出来，并利用稀疏约束有效地提取数据中的隐藏结构，将隐层进行约束，可以学习到一种更复杂的非线性函数，使其具有良好的学习数据集特征的能力，从而更准确地抽取样本的本质特征。在MNIST手写数字识别数据集，Pen-based recognition ofhandwrittendigits 和Usps 数据集上做实验，通过与自动编码机，稀疏自动编码机进行比较，实验结果表明JSAE在分类准确率上要优于这些算法，验证了理论的正确性。分析了JSAE的训练数据集个数对分类准确率的影响，训练数据集越多分类的结果越准确，还描述出代价函数的参数对准确率的影响，找到分类准确率达到最高时的参数，具有一定的实践指导意义。本文还讨论了JSAE的训练迭代次数，证明了迭代次数对分类准确率有一定的影响。

# 参考文献：

[1]任丹，陈学峰.手写数字识别的原理及应用[J].计算机时代,2007(3): 17-21.   
[2]宋志坚，余锐．基于深度学习的手写数字分类问题研究[J].重庆工商 大学学报,2015,32(8):49-53.   
[3]陈军胜．组合结构特征的自由手写体数字识别算法研究[J].计算机工 程与应用,2013,49(5):179-184.   
[4] 吴忠，朱国龙，黄葛峰．基于图像识别技术的手写数字识别方法 [J]. 工业控制计算机,2011,21(12):48-51.   
[5]石会芳，胡小兵，刘瑞杰．基于启发式GA-SVM的手写数字字符识别 的研究[J].计算机技术与发展,2012,22(10):5-9.   
[6]石会芳．支持向量机及其在手写数字识别中的应用[D].重庆：重庆大 学,2013:1-30.   
[7]Yang X, Zhang T,Xu C. Cross-domain feature learning in multimedia [J]. IEEE Trans on Multimedia,2014,17(1): 64-78.   
[8]Chen M,Xu Z,Weinberger K.Marginalized denoising auto-encoders for domain adaptation [J]. Computer Science,2012.   
[9]Carreiraperpinan M A,Raziperchikolaei R.Hashing with binary autoencoders [J/OL].(2015) .http://eecs.ucmerced.edu.   
[10] Zhang J, Shan S,Kan M,et al. Coarse-to-fine auto-encoder networks (CFAN) for real-time face alignment [C]//Proc of Computer Vision ECCV 2014:1- 16.   
[11] Li S Z,YuB,Wu W.Feature learning based on SAE-PCA network for human gesture recognition in RGBD images [J].Neurocomputing,2015,151(151): 565-573.   
[12] Deng L,Seltzer M, Yu D,et al. Binary coding of speech spectrograms using a deep auto-encoder [C]//Proc of Interspeech.2010.   
[13] Liou C Y,Cheng C W, Liou JW,et al.Autoencoder for words [J], Neurocomputing,2014,139 (139): 84-96.   
[14] Scholkopf B，Platt J，Hofmann T. Eficient Learning of Sparse Representations with an Energy-Based Model [C]// Advances in Neural Information Processing Systems.2006: 1137-1144.   
[15] Vincent P,Larochelle H, Lajoie I. Stacked denoising autoencoders: learning useful representations in a deep network with a local denoising criterion [J]. Journal of Machine Learning Research,2010,11(12): 3371-3408.   
[16] Rifai S,Vincent P,Muller X.Contractive Auto-Encoders:Explicit Invariance During Feature Extraction [C]//Proc of ICML.2011.   
[17] Jia K, Sun L, Gao S. Laplacian auto-encoders [J]. Neurocomputing,2015, 160 (C): 250-260.   
[18]杨阳，张文生．基于深度学习的图像自动标注算法[J].数据采集与处 理,2015,30(1):88-97.   
[19]郭海凤，李广水，仇彬任．降噪自动编码机在图像识别中的应用[J] 金陵科技学院学报,2015,31(3):32-35.   
[20] Liu W,Ma T,Tao D.HSAE: a Hessian regularized sparse auto-encoders [J]. Neurocomputing,2016,187: 59-65.