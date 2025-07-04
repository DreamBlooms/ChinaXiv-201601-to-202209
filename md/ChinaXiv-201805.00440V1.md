# 改进的单幅图像的自学习超分辨率重建方法

王晓明ab，黄凤a，刘少鹏a，徐涛a(西华大学a.计算机与软件工程学院;b.机器人研究中心，成都 610039)

摘要：针对传统超分辨率重建方法稀疏表示依赖大训练样本字典的局限性问题，基于l范数的弱稀疏性特点，提出一种改进的单幅图像自学习超分辨率重建方法。首先，通过自学习建立非金字塔阶梯式训练图像集；然后，采用自定义的方法分别提取训练集中低分辨率和相应高分辨率图像特征块及特征像素值；最后，结合l范数的协作表示(collaorativerepresentation，CR）理论和支持向量回归(supportvectorregression，SVR)技术学习多层超分辨率映射模型。实验结果表明，提出的超分辨率方法不仅可行有效，而且与传统的单幅图像的超分辨率方法比较，其PSNR平均提高了0.06\~3.92dB，SSIM平均提高了 $0 . 0 0 2 4 { \sim } 0 . 0 3 4 8$ 。从客观数值和主观视觉证明了所提方法的优秀性。

关键词：单幅图像超分辨率；l范数；协作表示；支持向量回归中图分类号：TP181 doi: 10.3969/j.issn.1001-3695.2018.02.0184

# Improved super-resolution reconstruction method for self-learning of single image

Wang Xiaominga, b, Huang Fenga†,Liu Shaopenga, Xu Taoa (a.SchoolofComputer&SoftwareEngineering,b.Robotics Research Center,Xihua University,Chengdu Sichuan610039, China)

Abstract: Aimingatthe limitationofsparserepresentationdependedonlarge trainingsampledictionaries fortraditionalsuperresolutionreconstruction method,this paper proposed an improved super-resolutionreconstruction method forself-leaing of single image based on the characteristic of $l _ { 2 }$ norm's weak sparsity. Firstly, it used self-learning to established the non pyramid stepped training images;then,itusedthecustom method to extractfeature blocks and feature pixel values ofcorresponding LR and HR images; finally, combined with the collaborative representation (CR) theory of $l _ { 2 }$ norm and support vector regression (SVR)technology,itestablished mapping modelofthesuper-resolution.Experimentalresultsshowthatthe proposedsuperresolution method is not only feasible and effective,but also the average PSNR increases for $0 . 0 6 { \sim } 3 . 9 2$ dB and SSIM increases for0.0024\~0.034 8compared with other conventional super-resolutionapproachesof single image.From the objectiveand subjective vision, it is proved that the proposed method is excellent.

Key words: super-resolutionof single image; l norm; collaborativerepresentation (CR); support vector regression (SVR)

# 0 引言

近年来，计算机视觉和图像处理领域得到了广泛的关注，其中数字图像的超分辨率重建问题一直是研究热点。图像超分辨率（superresolution，SR）重建是指从一幅低分辨率(lowresolution,LR)图像或多幅LR 图像中恢复出高分辨率(highresolution,HR)图像[1\~9]的过程。根据图像的输入/输出情况，超分辨率问题可分为基于重建的超分辨率问题、视频超分辨率问题和单幅图像超分辨率问题；根据有无训练样本，单幅图像超分辨率问题，可以分为没有训练样本的增强边缘的单幅图像超分辨和有训练样本的基于学习的单幅图像超分辨率[2]。本文研究基于学习的单幅图像超分辨率问题。

基于学习的单幅超分辨率技术是图像超分辨率算法研究的一个重大突破。它主要通过机器学习方法学习的LR图像与HR图像映射关系预测测试图像丢失的高频细节信息，重建SR 图像。目前，基于学习的单幅图像超分辨率技术在建立HR和LR图像关系时主要有以下几种：a)通过冗余字典建立HR和LR图像块特征的投影矩阵[3-6];b)通过回归模型建立LR 图像块与相应 HR 图像像素值之间的函数关系[5,7-9]，包括支持向量回归（supportvectorregression，SVR）模型、固定邻域回归（anchoredneighborhood regression，ANR)模型和岭回归(ridgeregression,RR）模型等。

2008年，Yang等人[3首次从压缩感知的角度提出基于稀疏表达（sparse representation）建立LR和HR图像的投影矩阵的超分辨率方法；2009年，Yang等人[4对之前的超分辨率研究工作作出改进，提出LR图像字典和HR 图像字典的双字典的稀疏表达超分辨率方法。2013年，Yang 等人[7结合稀疏表达和SVR，提出了单幅图像自学习的超分辨率方法（self-learmingapproach to single image super-resolution，SLSR）。该方法前期利用稀疏表达理论和冗余字典稀疏化训练图像集的特征，得到图像特征的稀疏系数；后期基于稀疏系数，利用SVR理论建立LR与HR图像之间像素的回归映射模型，实现图像的超分辨率重建。该实验结果证明结合稀疏表达和SVR的 SLSR方法较Yang等人[34]借助外部图像数据库的稀疏表达超分辨率方法效果更好。然而这些基于稀疏表示的超分辨率重建方法表明，重建超分辨率图像的关键在于表示图像特征的系数必须足够稀疏，而系数的强稀疏性取决于构建的冗余字典。

随着范数的发展，为了提高范数最小化的计算速度，2011年，Zhang 等人[10]发表关于 $l _ { 0 }$ 和 $l _ { 1 }$ 范数的稀疏表达及 $l _ { 2 }$ 范数的协作表达（collaborative representation,CR）的论文，集中阐述了稀疏表示分类的理论机制，并在文中证明：在分类中， $l _ { 1 }$ 范数的稀疏度并不是提高分类效果的关键，信号和编码字典之间的协作性才是分类的关键。本文最后给出，基于 $l _ { 2 }$ 范数的CR不仅提高分类精确度，而且提高了分类效率，降低了数据计算的复杂度。随后，Tian等人[5在CR理论的发展上提出了基于固定邻域回归的单幅图像自学习样本的超分辨率算法（anchoredneighborhood regression based single image super-resolution fromself-examples,ANRSR），并证明该算法比基于稀疏表达的超分辨率方法更有效；同时，Zhang等人[6利用外部图像库提出了基于聚类和CR结合的快速单幅图像超分辨率算法（clustering andcollaborative representation for fast single image super-resolution,CCRSR）。

针对基于稀疏表示的超分辨率重建方法中图像特征的强稀疏性系数依赖冗余字典的问题[34,7]，利用 $l _ { 2 }$ 范数的CR 可替代稀疏表示的弱稀疏性的特点[10]，提出一种基于CR的改进超分辨率方法。首先，利用图像退化模型，通过自学习的方法对输入的原始图像建立多个LR图像，并逐一对LR图像集插值放大，形成同时有HR 和LR 图像的同尺寸图像集合；然后，提取LR图像的特征和HR图像对应的像素值，并用CR理论对LR 图像的特征弱稀疏化，保留图像全部特征；最后，基于LR图像特征的协作系数和HR图像的像素值，建立SR 图像的多个重建映射模型和误差模型，根据最小误差选择最优重建模型的超分辨率像素值，实现单幅图像的超分辨率重建。

# 1 相关工作

基于学习的单幅图像超分辨率方法在学习LR和HR图像的关系模型时，一般有两种图像训练集：一是以输入图像为原型，通过图像退化模型自学习图像训练集；二是直接从输入图像以

外收集大量的图像作为图像训练集。

设图像的一般退化模型为

$$
I _ { \mathit { l o w } } = S B I _ { \mathit { h i g h } } + n
$$

其中： $I _ { l o w }$ 是LR 图像； $I _ { h i g h }$ 是HR 图像； $s$ 代表下采样过程;$B$ 代表模糊过程（高斯模糊、运动模糊等）； $n$ 代表噪声（高斯噪声、椒盐噪声等）。超分辨率重建的过程即是退化模型的逆过程。

# 1.1 $l _ { 0 }$ 范数和 $l _ { \mathrm { { l } } }$ 范数的稀疏表示理论

设某图像信号 $X = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } ] \in \mathbb { R } ^ { m \times n }$ ，字典$D = [ d _ { 1 } , d _ { 2 } , \cdots , d _ { k } ] \in \mathbb { R } ^ { m \times k }$ ，则基于 $l _ { 0 }$ 范数的稀疏表示模型：

$$
\begin{array} { r l } { \underset { \alpha } { \arg \operatorname* { m i n } } } & { { } \left\{ \| x - D \cdot \alpha \| _ { 2 } ^ { 2 } + \lambda \| \alpha \| _ { 0 } \right\} } \end{array}
$$

其中： $\lambda$ 为模型的正则化参数。通过求解式（2）返回图像信号$x _ { i }$ 在字典 $D$ 上的一个近似解 $\alpha _ { i }$ ，且 $\alpha _ { i }$ 是由多个零元素组成的稀疏向量。设矩阵 $A = [ \alpha _ { 1 } , \alpha _ { 2 } , \cdots , \alpha _ { n } ]$ ，则 $A \in \mathbb { R } ^ { k \times n }$ 。

由于式（2）在求解过程中是一个非确定多项式难题（non-deterministic polynomial hard，NPH)，Efron 等人[11]对 $l _ { 0 }$ 范数的稀疏表示作了改进，提出 $l _ { 1 }$ 范数的稀疏表示模型：

$$
\begin{array} { r l } { \underset { \alpha } { \arg \operatorname* { m i n } } } & { { } \left\{ \| x - D \cdot \alpha \| _ { 2 } ^ { 2 } + \lambda \| \alpha \| _ { 1 } \right\} } \end{array}
$$

该模型具有更好优化求解的特性，同时能通过获得的稀疏系数 $A$ 恢复图像信号 $x$ 。

# 1.2 $l _ { 2 }$ 范数的协作表示理论

鉴于稀疏表示中 $l _ { 1 }$ 和 $l _ { 0 }$ 范数计算耗时等问题[10]，Zhang 等人提出结合最小二乘和 $l _ { 2 }$ 范数的协作表示方法。其复杂度低于稀疏表示，计算速度高于稀疏表示。

设测试图像数据为 $x$ ，字典样本为 $D$ ，增加 $l _ { 2 }$ 范数的稀疏约束，则协作表示的问题模型为

$$
\begin{array} { r l } { \underset { \alpha } { \arg \operatorname* { m i n } } } & { { } \left\{ \| x - D \cdot \alpha \| _ { 2 } ^ { 2 } + \lambda \| \alpha \| _ { 2 } ^ { 2 } \right\} } \end{array}
$$

其中： $\left\| \bullet \right\| _ { 2 } ^ { 2 }$ 表示 $l _ { 2 }$ 范数； $\lambda$ 为模型的惩罚参数，旨在平衡最小二乘和 $\alpha$ 的 $l _ { 2 }$ 范数之间的关系，保证最小二乘解的稳定性，同时为系数 $\alpha$ 引入一定数量的稀疏度，提高运算速度。

# 1.3基于线性核的支持向量回归理论

SVR 是在支持向量机(support vector machine,SVM)的基础上被提出的。它的目标是寻找最优回归函数 $y = \langle \omega , x \rangle + b$ ，$\omega \in \mathbb { R } ^ { m }$ ， $b \in \mathbb { R }$ ， $\langle \cdot , \cdot \rangle$ 表示在空间 $\mathbb { R } ^ { m }$ 的内积。最优回归函数对应于空间 $\mathbb { R } ^ { m } \times \mathbb { R }$ 上的一个超平面。设训练集$\{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , \cdots , ( x _ { n } , y _ { n } ) \} \subset \mathbb { R } ^ { m } \times \mathbb { R }$ ，则 SVR对应的原始优化问题[12]为

$$
\operatorname* { m i n } \frac { 1 } { 2 } \| \omega \| ^ { 2 } + c \sum _ { i = 1 } ^ { n } \big ( \xi _ { i } + \xi _ { i } ^ { * } \big )
$$

$$
\begin{array} { r l } { s . t . } & { \left\{ \begin{array} { c } { \langle \omega , x _ { i } \rangle + b - y _ { i } \leq \varepsilon + \xi _ { i } , i = 1 , 2 , \cdots , n } \\ { y _ { i } - \langle \omega , x _ { i } \rangle - b \leq \varepsilon + \xi _ { i } ^ { * } , i = 1 , 2 , \cdots , n } \end{array} \right. } \\ & { \qquad \xi _ { i } , \xi _ { i } ^ { * } \geq 0 , i = 1 , 2 , \cdots , n } \end{array}
$$

其中： $\omega$ 是非线性映射函数法线矢量; $\mathbf { \Psi } _ { c }$ 是惩罚参数，且 $c > 0$ ：$b$ 是回归偏移量； $\varepsilon$ 是不敏感函数； $\xi _ { i } ^ { ( * ) }$ 是训练误差上（下)限，松弛变量。

令线性核 $K \big ( x _ { i } , x _ { j } \big ) = x _ { i } ^ { T } x _ { j }$ ，为解决优化问题式（5)，引进拉格朗日算子 $\beta \setminus \beta ^ { * }$ ，采用Lagrange 法把原始问题转化为对偶优化问题求解：

$$
\begin{array} { r } { \operatorname* { m a x } \left\{ - \displaystyle \frac { 1 } { 2 } \sum _ { i , j = 1 } ^ { n } \big ( \beta _ { i } - \beta _ { i } ^ { * } \big ) \big ( \beta _ { j } - \beta _ { j } ^ { * } \big ) K \big ( x _ { i } , x _ { j } \big ) \right. } \\ { \left. - \varepsilon \displaystyle \sum _ { j = 1 } ^ { n } \big ( \beta _ { i } + \beta _ { i } ^ { * } \big ) + \sum _ { i = 1 } ^ { n } y _ { i } \big ( \beta _ { i } - \beta _ { i } ^ { * } \big ) \right\} } \end{array}
$$

$$
s . t . \quad \left\{ \begin{array} { l } { \displaystyle \sum _ { i = 1 } ^ { n } \left( \beta _ { i } - \beta _ { i } ^ { * } \right) = 0 } \\ { \beta _ { i } , \beta _ { i } ^ { * } \in [ 0 , c ] } \end{array} \right.
$$

最后得到基于线性核的SVR函数:

$$
f \left( x \right) = \sum _ { i = 1 } ^ { n } \bigl ( \beta _ { i } - \beta _ { i } ^ { * } \bigr ) K \left( x _ { i } , x \right) + b
$$

# 2 基于同尺寸图像的 $l _ { 2 }$ 范数的超分辨率方法

研究单幅图像的超分辨率重建问题，关键在于学习LR图像和HR图像之间的关系。考虑图像的差异性，本文采用自学习的方法学习每幅图像的训练图像集。相比文献[5,7,9]提出的金字塔阶梯式图像集的自学习方法，本文提出建立同尺寸图像集的自学习方法。

# 2.1自学习同尺寸图像集

设输入高清原始图像为 $I$ ，模拟图像的退化过程得到训练单幅图像超分辨率方法的图像集。首先通过模型式（1)，对图像 $I$ 用自定义的高斯模糊函数进行模糊；然后以 $z$ 的倍率下采样图像；最后对经过高斯模糊和下采样的图像加入 $4 0 ~ \mathrm { d B }$ 信噪比的高斯白噪声得到待超分辨率重建的LR 图像Iow。

随后，对图像 $I _ { l o w }$ 以同样的高斯模糊函数及下采样倍率建立LR 图像金字塔。利用双三次插值(bicubic interpolation,BI)的方法将低分辨率的图像金字塔放大至原始图像 $I$ 的尺寸，得到具有超分辨率图像尺寸，但清晰度依次降低的训练图像集$M = \{ I _ { 1 } , I _ { 2 } , \cdots , I _ { N } \}$ ，其中图像 $I _ { i }$ 的清晰度高于 $I _ { i + 1 }$ ，分别适时地定义为HR和LR图像。图1描述了自学习同尺寸图像集的大致流程。图像集 $M$ 的大小由LR图像金字塔的层数决定，金字塔的层数主要由下采样倍率及图像分块大小决定。

观察图1描述的多分辨率训练图像集合的全局展示图，易知道这些图像集满足分辨率逐渐递进的规律。超分辨率重建研究的目的是在放大图像时提高图像分辨率，增加图像的清晰度。根据构建的图像集满足分辨率逐渐递进的规律，本文只需找出相邻图像 $I _ { i }$ 和 $I _ { i + 1 }$ 之间的关系模型，从多个关系模型中选择最优模型重建超分辨图像 $I _ { s r }$ 即可，且分辨率逐渐提高的图像 $I _ { i }$ 和$I _ { i + 1 }$ 满足本文后期重建超分辨率图像映射模型的自变量和因变

量条件。

# 2.2图像特征提取及 $l _ { 2 }$ 范数协作表达

根据 2.1节单幅图像的自学习过程，本文超分辨率重建 $I _ { l o w }$ 的关键在于学习同尺寸图像集 $M$ 中相邻LR图像和HR 图像的最优关系模型。由图1可知，虽然图像 $I _ { 3 } \setminus I _ { 2 } \setminus I _ { 1 }$ 的尺寸相同,但其是由越接近真实图像的LR图像插值而来，清晰度不一样，故学习这些同尺寸图像之间的多个关系，用具有最小误差的关系模型重建 $I _ { l o w }$ 的超分辨率图像 $I _ { s r }$ 。

![](images/c4ba0e769605fb9f370566f2751afc530e9e73798cb1e71bef42fc4bff4fe9a2.jpg)  
图1单幅图像自学习同尺寸多分辨率图像过程

2.2.1特征提取

设图像块大小为 $\textit { p } , \quad \left\{ I _ { h } ^ { i } \right\} _ { i = 1 } ^ { N - 1 } = \left\{ I _ { 1 } , I _ { 2 } , \cdots , I _ { N - 1 } \right\}$ 是训练的HR图像集， $\left\{ { I _ { l } ^ { i } } \right\} _ { i = 2 } ^ { N } = \left\{ { I _ { 2 } , I _ { 3 } , \cdots , I _ { N } } \right\}$ 是对应的LR 图像集，分别以步长为1的 $p$ 大小滑动窗口提取 LR 图像 $I _ { l } ^ { i }$ 的图像块集合{ ∈R"和对应 HR 图像I的图像块的中心像素值集合（20 $\left\{ y _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } } \in \mathbb { R }$ 。考虑本文的重建模型是 LR 图像块和HR 的像素值的回归模型，借鉴文献[13]，对每一个 $x _ { \scriptscriptstyle { l } }$ 点乘 $p$ 大小的权重分配矩阵 $\boldsymbol { G }$ ，使得 $X _ { \scriptscriptstyle { l } }$ 的中心取得更大的权重值。更新LR特征集（20 $\left\{ \boldsymbol { X } _ { l } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ ，得到重建超分辨率图像的学习模型训练集 $\left\{ \boldsymbol { X } _ { l } ^ { i } , \boldsymbol { y } _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ 。

# 2.2.2 $l _ { 2 }$ 范数协作表达

由于特征 $x _ { \scriptscriptstyle { l } }$ 通过 $l _ { 1 }$ 范数稀疏表达得到的系数 $\alpha$ 大部分等于0，主动忽略了提取到的部分图像特征，在后期LR和HR图像的映射模型中容易产生误差。而 $x _ { \scriptscriptstyle { l } }$ 通过 $l _ { 2 }$ 范数协作表达求解到的系数 $\alpha$ 趋近于0但不等于0，保留了图像全部特征。本文基于文献[10]中关于 $l _ { 1 }$ 范数的稀疏表达和 $l _ { 2 }$ 范数的协作表达的人脸分类时效和准确率实验，提出结合 $l _ { 2 }$ 范数和最小二乘法协作表达 $\left\{ \boldsymbol X _ { l } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ 的方法，既提高 LR 和 HR 图像映射模型的准确率，又降低系数化图像特征过程的计算复杂度。

对每一幅 LR 图像 $I _ { \iota } ^ { j }$ ( $j = 1 , 2 , \cdots , N - 1 \$ ）提取的特征集$\left\{ \boldsymbol X _ { l } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ 的每一块矩阵 $x _ { \scriptscriptstyle { l } }$ 列向量化，则 $\left\{ \boldsymbol { X } _ { l } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } } \in \mathbb { R } ^ { p ^ { 2 } }$ 。令X={}，其协作表示系数A，则

$$
\operatorname* { m i n } _ { A } \left\| X _ { j } - D _ { j } A \right\| _ { 2 } ^ { 2 } + \lambda \left\| A \right\| _ { 2 } ^ { 2 }
$$

其中： $D$ 由数据矩阵 $x$ 的特征值及特征向量决定。为解决问题式（8)，利用正则化的最小二乘法求解协作系数，得到 $x$ 在字典 $D$ 上的近似解：

$$
\hat { \boldsymbol { A } } = \left( \boldsymbol { D } _ { j } ^ { T } \boldsymbol { D } _ { j } + \boldsymbol { \lambda \cdot I } \right) ^ { - 1 } \boldsymbol { D } _ { j } ^ { T } \boldsymbol { X } _ { j }
$$

其中： $\mathbf { \xi } _ { I }$ 是单位矩阵。最后重建超分辨率图像的映射模型训练集更新为 $\left\{ \alpha _ { i } , y _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } } , \alpha \in \mathbb { R } ^ { p ^ { 2 } }$ 。如此反复，构建多个映射模型的数据集 $T _ { j } = \left\{ \alpha _ { { } _ { j i } } , y _ { h } ^ { j i } \right\} _ { i = 1 } ^ { N _ { d } }$ 。

# 2.3超分辨率重建模型

文献[3\~6]中，Yang、Tian及Zhang 等人均提出用自定义的四个方向的高通滤波算子提取LR图像的图像特征块，最后借助 $l _ { \mathrm { { l } } }$ 范数的稀疏表达或 $l _ { 2 }$ 范数的协作表达建立LR 和 HR 图像块特征的超分辨率重建模型。本文将使用基于线性核的SVR重建LR图像特征到相应的HR图像空间的映射模型，重建超分辨率图像 $I _ { s r }$ 。

# 2.3.1重建映射模型

输入图像 $I$ 通过自学习同尺寸图像训练集、LR和HR图像特征提取及LR 图像特征 $l _ { 2 }$ 范数的协作表达，得到映射模型训练集T={aj,ySi=1 ， $j = 1 , 2 , \cdots , N - 1$ 。随后对每一组数据集

（20 $\left\{ \alpha _ { i } , y _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ 根据位置的奇偶性二分为训练集 $T r = \left\{ \alpha _ { i } , y _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { t r a i n } }$ 和测试集 $T e = \left\{ \alpha _ { i } , y _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { t e s t } }$ ，其中训练集 $T r$ 用于构建重建映射模型 $F$ ，测试集 $T e$ 用于构建误差模型 $E$ 。

对训练集 $T r$ 利用式（5）建立LR图像特征 $\boldsymbol { \mathfrak { a } }$ 与HR图像的像素值 $y _ { h }$ 的线性核 SVR 模型，解得LR 图像特征到相应的HR 图像空间的映射模型：

$$
F ( \alpha ) = \sum _ { i = 1 } ^ { N _ { t r a i n } } \bigl ( \beta _ { i } - \beta _ { i } ^ { * } \bigr ) K ( \alpha _ { i } , \alpha ) + b _ { t r }
$$

其中： $K ( \alpha _ { i } , \alpha )$ 表示 $\boldsymbol { \mathfrak { a } } _ { i }$ 和 $\boldsymbol { a }$ 之间的线性核函数；$b _ { t r } = y _ { h } - \sum \bigl ( \beta _ { i } - \beta _ { i } ^ { * } \bigr ) K \bigl ( \alpha _ { i } , \alpha _ { j } \bigr ) - \varepsilon$ 。类似地，建立每一组LR 和HR 图像的映射模型 $F _ { j }$ $( \mathbf { \Phi } _ { j = 1 , 2 , \cdots , N - 1 } )$ 。

2.3.2误差模型

借鉴Yang 等人[提出的 SLSR方法同时建立误差模型 $E$ ，通过误差选择最小误差对应的重建模型的 $\hat { y } _ { h }$ 作为HR图像的像素值。

对每一组训练集对应的测试集数据 $T e$ ，用 2.3.1节重建的映射模型式(10)恢复测试数据 $\boldsymbol { \mathfrak { a } }$ 对应的 HR 图像的像素值 $\hat { y } _ { h }$ ，然后利用 SVR理论对 $\{ \boldsymbol { a } _ { i } , \boldsymbol { e } _ { i } \} _ { i = 1 } ^ { N _ { t e s t } }$ 建立LR 图像特征到相应的 HR图像空间的误差模型，其中$e = \left| { \hat { y } } _ { h } - y _ { h } \right| - \operatorname* { m i n } ( \left| { \hat { y } } _ { h } - y _ { h } \right| ) / \left( \operatorname* { m a x } \left( \left| { \hat { y } } _ { h } - y _ { h } \right| \right) - \operatorname* { m i n } ( \left| { \hat { y } } _ { h } - y _ { h } \right| ) \right)$

$$
E ( \alpha ) = \sum _ { i = 1 } ^ { N _ { t e s t } } \bigl ( \beta _ { i } - \beta _ { i } ^ { * } \bigr ) K ( \alpha _ { i } , \alpha ) + b _ { t e }
$$

$b _ { t e } = e - \sum \left( \beta _ { i } - \beta _ { i } ^ { * } \right) K \left( \alpha _ { i } , \alpha _ { j } \right) - \varepsilon$ 。类似地建立每一组LR和HR 图像的误差映射模型 $E _ { j }$ $\langle \mathbf { \delta } _ { j = 1 , 2 , \cdots , N - 1 } \rangle$ 。

最后根据LR图像特征集建立的误差模型，选择最小误差对应的重建映射模型的 $\hat { y } _ { h }$ 作为HR图像的像素值。图2显示了本文提出的重建超分辨率图像模型的大致流程。

同尺寸多分辨率 特征提取 特征训练集 LR特征块 $x _ { \iota }$ （204号 更新训练集 $\boldsymbol { l } _ { 2 }$ 范数 模型训练集 模型建立 重建模型 $F$ 训练集M 1 $\left\{ x _ { l } ^ { i } , y _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ 点乘G，列 {y 协作表达 $\left\{ \alpha _ { i } , \mathbf { y } _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ 误差模型 $E$ 向量化

# 3 实验

本文的实验图像均从南加州大学(Universityof SouthernCaliformia,USC)图像数据库[14]下载。实验平台为处理器Inte $\textsuperscript { \textregistered }$ Core(TM)i3-4130 CPU $\textcircled { a } 3 . 4 0 \mathrm { G H z }$ 的64位Windows7旗舰版，MATLAB R2015a。

# 3.1实验及部分参数设置

为验证本文所提超分辨率方法的公正性，本文将其他传统的超分辨率方法（Yang 等人[4]SCSR方法、Yang 等人[7]SLSR方法、Wang等人[15]提出的基于稀疏编码和级联网络的CSCN 方法、Tian 等人[5]ANRSR方法及Zhang等人[CCRSR方法，相关代码均可在作者主页下载)中待超分辨率重建的 LR 图像 $I _ { l o w }$ 的预处理方式均设置成本文的方法。

为验证本文所提超分辨率方法的有效性，本文将此方法得到的超分辨率图像 $I _ { s r }$ 与其他传统的超分辨率方法重建的图像$I _ { s r }$ 作比较。用图像评价中最常用的指标：峰值信噪比（peaksignal to noise ratio,PSNR）和结构相似性（structure similarityimagemeasure,SSIM）作为超分辨率图像质量的客观评价标准。

实验的多类型图像（图3)均来自图像库[14]。若图像为RGB彩色空间，根据人眼对亮度差异的高度敏感特性，首先将RGB彩色空间图像转换为YCbCr彩色空间图像，然后选取Y分量上的亮度图像信号应用超分辨率方法，其他色度分量(Cb和Cr)均做BI的超分辨率方法。

实验过程中，设置下采样倍率 $z = 2$ ，高斯模糊方差 $\sigma = 0 . 1$ 图像集 $M$ 的大小 $N = 5$ ，图像块 $\scriptstyle p = [ 5 , 5 ]$ ，其中相邻图像块间的重合像素点数为4。 $l _ { 2 }$ 范数的协作表达中数据特征向量维度（204号 $K = 1 0 0$ ，SVR 重建映射模型参数通过LIBSVM[15]工具箱的gridregessionly函数训练数据 $\left\{ \alpha _ { i } , \mathbf { y } _ { h } ^ { i } \right\} _ { i = 1 } ^ { N _ { d } }$ 得到，取 $c = 4$ 、$\varepsilon = 0 . 0 1$ 的 ${ \bf \Pi } _ { \mathcal { E } - S V R }$ 为 $F$ 模型参数，误差模型 $E$ 的参数选取$\mathbf { \sigma } _ { \nu - S V R }$ 的默认值 $c = 1 \cdot \ \nu = 0 . 5 \circ \mathrm { L R }$ 图像的权重分配矩阵 $\boldsymbol { G }$ 以图像块 $p$ 大小的高斯函数设置。

![](images/7fef4959876cef2d4d46f5ddc9e26b641a1892e129078c6ec821c67270e86b1a.jpg)

![](images/f2cdb23725127fae32dfc50729c16b9afba5766ea7b1228945032f769e92fe74.jpg)  
图312幅实验图像 $\mathrm { ( [ ^ { * } X ^ { * } }$ 表示图像尺寸])

# 3.2正则化参数 $\lambda$ 对实验结果的影响

由于参数 $\lambda$ 的取值影响着LR图像特征块的近似系数，本文将对 $\lambda$ 的取值做如下探讨：

取 $\lambda \in [ 5 \mathrm { e } { - } 7 , 5 ]$ ，对同一组图像数据（图3(a)4.1.01）进行多次超分辨率重建，测试 $\lambda$ 对重建的超分辨率图像的质量评价指标 PSNR和SSIM的影响。图4、5分别显示了不同的 $\lambda$ 取值对重建超分辨率图像的PSNR和SSIM的波动。

![](images/1dbd706bcee60dbdc1aff657cb230c78e2a6dc9d94e5517a4e4ff5a0c6265949.jpg)  
图4 $\lambda$ 值对超分辨率重建的PSNR值波动图

![](images/b24779d26fec73e20d786e878476ff29259a4cfb6cd40820c1efeab2d5272f87.jpg)  
图5 $\lambda$ 值对超分辨率重建的SSIM值波动图

结合图4和5，容易观察得到：当 $\lambda \in [ 5 \mathrm { e } . 7 , 0 . 1 ]$ 时， $\lambda$ 的取值对重建超分辨率图像的PSNR和SSIM指标值的影响较小，可忽略不计；而当 $\lambda > 0 . 1$ 时，重建的超分辨率图像的PSNR 和SSIM指标值的波动范围较大。明显，取太大的 $\lambda$ 时，其重建的超分辨率图像的视觉效果较差。此结论，本文取实验参数$\lambda = 5 e - 4$ 。

# 3.3实验结果与分析

根据3.1节实验及参数设置、3.2节 $\lambda$ 值的探讨，本文对实验图像的LR图像 $I _ { l o w }$ 进行多种超分辨率方法图像重建，并分别计算它们的PSNR、SSIM值得到表1。图6显示了部分实验图像的重建超分辨率图像。

表1多种方法重建超分辨率图像的PSNR(/dB)和SSIM比较  

<html><body><table><tr><td rowspan="2">图像</td><td colspan="2">BI</td><td colspan="2">SCSR[4]</td><td colspan="2">SLSR[7]</td><td colspan="2">CSCN[15]</td></tr><tr><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td></tr><tr><td>4.1.01</td><td>29.81</td><td>0.9820</td><td>25.58</td><td>0.9583</td><td>31.73</td><td>0.9885</td><td>29.63</td><td>0.9445</td></tr><tr><td>4.1.03</td><td>30.21</td><td>0.9656</td><td>27.41</td><td>0.9514</td><td>31.66</td><td>0.9722</td><td>29.87</td><td>0.9595</td></tr><tr><td>4.1.04</td><td>29.19</td><td>0.9842</td><td>26.82</td><td>0.9829</td><td>30.94</td><td>0.9896</td><td>27.51</td><td>0.9730</td></tr><tr><td>4.1.05</td><td>27.33</td><td>0.9733</td><td>25.24</td><td>0.9555</td><td>28.50</td><td>0.9786</td><td>28.96</td><td>0.9649</td></tr><tr><td>4.1.06</td><td>23.34</td><td>0.9691</td><td>22.33</td><td>0.9504</td><td>24.52</td><td>0.9759</td><td>23.37</td><td>0.9563</td></tr><tr><td>4.1.08</td><td>28.89</td><td>0.9846</td><td>24.59</td><td>0.9691</td><td>32.90</td><td>0.9938</td><td>30.31</td><td>0.9788</td></tr><tr><td>4.2.03</td><td>20.46</td><td>0.8609</td><td>19.47</td><td>0.8872</td><td>23.42</td><td>0.9224</td><td>20.36</td><td>0.8282</td></tr><tr><td>4.2.05</td><td>26.78</td><td>0.9730</td><td>25.96</td><td>0.9595</td><td>31.29</td><td>0.9896</td><td>26.76</td><td>0.9681</td></tr><tr><td>5.1.10</td><td>23.11</td><td>0.9207</td><td>22.38</td><td>0.8955</td><td>24.45</td><td>0.9384</td><td>23.37</td><td>0.9088</td></tr><tr><td>5.1.11</td><td>27.08</td><td>0.9540</td><td>26.27</td><td>0.9393</td><td>31.94</td><td>0.9792</td><td>27.40</td><td>0.9512</td></tr><tr><td>5.1.12</td><td>26.19</td><td>0.9769</td><td>25.93</td><td>0.9677</td><td>26.37</td><td>0.9774</td><td>27.10</td><td>0.9737</td></tr><tr><td>5.1.13</td><td>18.93</td><td>0.9022</td><td>19.38</td><td>0.8830</td><td>19.94</td><td>0.8827</td><td>21.36</td><td>0.8887</td></tr><tr><td>平均值</td><td>25.94</td><td>0.9539</td><td>24.28</td><td>0.9416</td><td>28.14</td><td>0.9657</td><td>26.33</td><td>0.9413</td></tr><tr><td rowspan="2">图像</td><td></td><td>ANRSR[5]</td><td></td><td>CCRSR[6]</td><td></td><td></td><td>本文方法</td><td></td></tr><tr><td colspan="2">PSNR</td><td>SSIM</td><td>PSNR</td><td>SSIM</td><td>PSNR</td><td></td><td>SSIM</td></tr><tr><td>4.1.01</td><td>28.58</td><td>0.9722</td><td></td><td>29.78</td><td>0.9574</td><td>32.29</td><td></td><td>0.9898</td></tr><tr><td>4.1.03</td><td>29.48</td><td>0.9347</td><td></td><td>28.75</td><td>0.9348</td><td>33.63</td><td></td><td>0.9823</td></tr><tr><td>4.1.04</td><td>28.23</td><td>0.9795</td><td></td><td>29.19</td><td>0.9998</td><td>31.57</td><td></td><td>0.9907</td></tr><tr><td>4.1.05</td><td>27.08</td><td>0.9621</td><td></td><td>27.73</td><td>0.9574</td><td>28.95</td><td></td><td>0.9818</td></tr><tr><td>4.1.06</td><td>22.92</td><td>0.9566</td><td></td><td>23.46</td><td>0.9992</td><td>24.55</td><td></td><td>0.9767</td></tr><tr><td>4.1.08</td><td>27.93</td><td></td><td>0.9783</td><td>28.68</td><td>0.9898</td><td>34.07</td><td></td><td>0.9954</td></tr><tr><td>4.2.03</td><td>19.88</td><td></td><td>0.7993</td><td>20.16</td><td>0.9998</td><td>21.54</td><td></td><td>0.8913</td></tr><tr><td>4.2.05</td><td>26.62</td><td></td><td>0.9640</td><td>22.69</td><td>0.9057</td><td>28.99</td><td></td><td>0.9836</td></tr><tr><td>5.1.10</td><td>22.18</td><td>0.8853</td><td></td><td>21.44</td><td>0.8926</td><td>25.26</td><td></td><td>0.9466</td></tr><tr><td>5.1.11</td><td>26.30</td><td>0.9356</td><td></td><td>27.02</td><td>0.9460</td><td>28.33</td><td></td><td>0.9644</td></tr><tr><td>5.1.12</td><td>26.05</td><td>0.9648</td><td></td><td>24.73</td><td>0.9676</td><td>28.33</td><td></td><td>0.9857</td></tr><tr><td>5.1.13</td><td>20.87</td><td></td><td>0.8674</td><td>16.90</td><td>0.8830</td><td>20.90</td><td></td><td>0.9293</td></tr><tr><td>平均值</td><td>25.51</td><td></td><td>0.9333</td><td>25.04</td><td>0.9528</td><td>28.20</td><td></td><td>0.9681</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

比较表1中超分辨率重建图像 $I _ { s r }$ 的多个PSNR和SSIM指标值，除图像4.1.04、4.1.06、4.2.03、4.2.05、5.1.11外，其他7幅图像的 LR 图像 $I _ { l o w }$ 在通过本文提出的超分辨率方法重建后，其客观数值PSNR和SSIM相比其他六种方法均表现最优。

观察表1可以发现，Zhang等人提出的CCRSR方法虽然重建图像的PSNR相对较小，但是其SSIM却比其他方法高，更接近原始HR图像。其中图像4.1.04、4.1.06、4.2.03的SSIM表现更为突出。分析其原因，CCRSR方法在提取LR图像的特征时，采取了四个方向的高通滤波方式，并对图像特征进行了聚类分类，这样使得每类的特征保留了图像大量相似的结构性。

通过SLSR方法重建的图4.2.05和5.1.11的超分辨率图像，不仅在PSNR指标上表现最高，而且也在SSIM指标上表现最高。分析其可能的原因：因为图4.2.05和5.1.11的图像特点比较单一和统一，而Yang 等人提出的SLSR方法正好在提取特征时，仅进行了图像的一个轮廓边缘检测，所以导致它们重建的超分辨率图像 $I _ { s r }$ 客观指标值均最优。Wang等人提出的CSCN方法虽然在重建图像4.1.05和5.1.13上取得了最优的PSNR，但是其最优数值分别仅比本文提出的方法高0.01和0.46，而通过本文方法重建的图4.1.05和5.1.13的SSIM分别比CSCN方法高0.0169和 $0 . 0 4 0 \ 6$ ，证明了本文提出的方法比基于稀疏编码和深度网络的超分辨率方法更优秀。

图6给出了部分图像的多种超分辨率结果，从视觉主观上进一步证明了本文提出方法的有效性和相对最优性。观察图5.1.13很容易发现，通过本文构建的超分辨率图像（f）的细节更清晰，呈现了其他重建图像不具有的细节信息，如图像最右边数字0下面的1。同时图（f）的分辨率相对其他五种超分辨率方法构建的图像更高。图4.1.08和4.2.03虽然大体图像一样，但是仔细观察可以发现，图4.1.08(f)的每颗豆子清晰度更高，豆子周边没有光晕，边缘光滑，相比其他图像，其更贴切真实图像，同时图像质量评价的客观指标也证明了图（f）的质量相比其他五幅图像更好；图4.2.03（b）的胡须清晰明了，而图(f)的胡须虽然不如图(b)历历可数，但仍可辨识，其细节信息较完善，失真度较低。从主观上整体反映了本文提出的方法有效，但仍需改进。

4.1.08 ###8#.#0#.###.#00#.3#8#  
4.2.030 0 0 1 0 0 0二 三 三 三 1 三 三三 三 1 三3 Im 1 品 三 三三 1 司 1三 三三 I 山川 三三三 1 三三 川 u 1 5  
5.1.13 T三 三 三0 三三 三三 中 5 三三 5三三 三三 山三(a)SCSR (b)SLSR (c)CSCN (d)ANRSR (e)CCRSR (f)本文方法

# 4 结束语

本文针对传统超分辨率方法稀疏表示图像特征的局限性，及稀疏系数存在容易忽略部分图像关键特征的问题，提出基于同尺寸图像训练集的 $l _ { 2 }$ 范数协作表达的超分辨率重建方法。对多个同尺寸的LR图像提取特征块，重新分配图像块的特征大小，并使用 $l _ { 2 }$ 范数的协作表达方式替代稀疏表示系数化LR 图像的特征，建立包含图像全部特征信息的更高效的LR和 HR图像的线性核SVR模型。实验结果表明，本文提出的方法与其他基于稀疏表达、协作表达及SVR的超分辨率方法相比，总体上其重建的超分辨率图像 $I _ { s r }$ 具有更好的视觉效果和更高的质量评价分数。从主观和客观角度证明了本文方法的有效性和优秀性。由于本文提出的方法在特征选择这一块比较单一，对于图像内容比较空泛和统一的图像的超分辨率重建结果不是很理想，未来将进一步改进图像特征的提取方式，尽可能多地提取和保留图像有效特征，建立适应多类型图像的超分辨率重建模型。

# 参考文献：

[1]杨欣．图像超分辨率技术原理及应用[M].北京：国防工业出版社, 2013:2-9,93.(Yang Xin. Image super resolution technology principle and application [M].Beijing: National Defend Industry Press,2013: 2-9,93.)

[2]苏衡，周杰，张志浩．超分辨率图像重建方法综述[J]．自动化学报, 2013,39 (8):1202-1213.(Su Heng, Zhou Jie,Zhang Zhihao.Survey of super-resolution image reconstruction methods [J].Acta Automatica Sinica, 2013,39 (8): 1202-1213.)   
[3]Yang Jianchao,Wright J,Huang T,et al. Image super-resolution as sparse representation of raw image patches [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.20o8:1-8.   
[4]Yang Jianchao,Wright J, Huang T,et al. Image super-resolution via sparse representation [J].IEEE Trans on Image Processing APublication of the IEEE Signal Processing Society,2010,19(11): 2861-2873.   
[5]Tian Yapeng,Zhou Fei,Yang Wenming,et al.Anchored neighborhood regression based single image super-resolution from self-examples [C]// Proc of IEEE International Conference on Image Processing.2016:2827- 2831.   
[6]Zhang Yongbing,Zhang Yulun,Zhang Jian,et al. CCR:clustering and collaborative representation for fast single image super-resolution [J]. IEEE Trans on Multimedia,2016,18 (3): 405-417.   
[7]Yang Minchun,Wang Y C F.A self-Learning approach to single image super-resolution [J].IEEE Trans on Multimedia,2013,15 (3):498-508.   
[8]王宇，吴炜，严斌宇，等．基于 SVR的人脸图像超分辨率复原算法[J]. 四川大学学报：自然科学版,2013,50(4):728-736.(Wang Yu,Wu Wei, Yan Binyu,et al.Face hallucination based on SVR[J]. Journal of Sichuan

University:Natural Science Edition,2013,50(4):728-736.)

[9]王宏，卢芳芳，李建武．结合支持向量回归和图像自相似的单幅图像超 分辨率算法 [J].中国图象图形学报,2016,21(8):986-992.(Wang Hong, Lu Fangfang,Li Jianwu. Single image super-resolution via support vector regression and image self-similarity [J]. Journal of Image and Graphics, 2016,21(8): 986-992.)   
[10] Zhang Lei,Yang Meng,Feng Xiangchu.Sparse representation or collaborative representation:which helps face recognition?[C]//Proc of International Conference on Computer Vision.[S.1.]:IEEE Computer Society, 2011: 471-478.   
[11] Efron B,Hastie T, Johnstone I,et al.Least angle regression [J].Annals of Statistics,2004,32 (2):407-451.   
[12] Basak D,Pal S,Patranabis D C. Support vector regression [J]. Neural

Intormation Processing-Letters and Reviews,2007,1l(10): 203-224.   
[13]黄凤，王晓明．增强的单幅图像自学习超分辨方法[J].计算机应用, 2017,37(9): 2636-2642,2699.(Huang Feng,Wang Xiaoming.Enhanced self-learning super-resolution approach for single image [J]. Journal of Computer Applications,2017,37(9): 2636-2642,2699.)   
[14]University of southern california, SIPI image database [EB/OL].[2016-08- 20]. http://sipi.usc.edu/database/.   
[15] Wang Zhaowen,Liu Ding,Yang Jianchao,et al.Deep networks for image super-resolution with sparse prior [Cl//Proc of IEEE International Conference on Computer Vision.2015:370-378.   
[16] Chang C,Lin C J.LIBSVM: a library for support vector machines [EB/OL]. (2001)[2016-10-18].https://www.csie.ntu.edu.tw/\~cjlin/libsvm/.