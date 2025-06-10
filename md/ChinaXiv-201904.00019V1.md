# 基于自适应半耦合字典学习的超分辨率图像重建

黄陶冶，孙恬恬，周正华，赵建伟(中国计量大学 理学院 应用数学系，杭州 310018)

摘要：在超分辨图像重建领域，如何平衡字典学习中表示系数的稀疏性和协同性对重建效果具有重要意义。针对该问题，在半耦合字典学习的超分辨重建基础上，利用核范数构建一个新的正则项，将稀疏性和协同性作为一个整体进行考虑，并用交替方向乘子法(ADMM)求解优化模型，得到了基于自适应半耦合字典学习的超分辨率图像重建算法。实验结果表明，该方法比现有的一些基于字典学习的重建方法具有更好的重建效果。所提出的算法能根据字典的变化自适应地平衡稀疏性与关联性，并通过两者之间的协调产生一个最合适的系数，因此在噪声环境下具有一定的抗干扰能力。

关键词：超分辨率重建；半耦合字典学习；自适应；核范 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.11.0852

Image super-resolution reconstruction based on adaptive semi-coupled dictionary learning

Huang Taoye,Sun Tiantian,Zhou Zhenghua, Zhao Jianwei (Dept. ofApplied Mathematics, Colege of Sciences, China Jiliang University, Hangzhou 310018, China)

Abstract:In the fieldof image super-resolution,how to balance thesparsityand cooperation of therepresentation coeficients in the dictionary learning is of great significance forthereconstruction result.Forthis problem,this paper proposes anadaptive semi-coupled dictionary learning super-resolution method based on semi-coupled dictionary-learning method.The method uses the kernel norm to construct a new regularization term to consider the sparsity and cooperation together,and adopts the alternating direction multiplier method(ADMM) to solve theoptimal model.The experimental results show that the proposed method is more efective thansome other existing dictionary-learning based reconstruction methods.The proposed methodcan balancethe sparsityand corelation according to the variation ofdictionaryto produce an appropriate coefficient adaptively. Hence, it has anti-interference ability to the noisy environment.

Key Words: super-resolution reconstruction; semi-coupled dictionary learning; adaptivity; nuclear norm

# 0 引言

现实生活中，低分辨率图像往往是由原始的高分辨图像经过下采样、模糊、噪声污染等退化过程得到的。图像超分辨率重建是上述图像退化的逆过程，旨在从低分辨率图像中恢复出高分辨率图像，它是计算机视觉领域中的一个研究热点[1]。目前，图像超分辨率重建已在多个领域得到广泛应用，如智能监控[2]、地理遥感[3]、医学诊断[4]等。

关于图像超分辨率重建方法目前主要分为基于插值的方法[5]、基于重建的方法[和基于学习的方法[7]。其中，基于学习的超分辨率重建方法包括基于字典学习[8]、基于深度学习[9]等方法，通过学习高、低分辨率图像块之间的映射关系，以此获得先验知识并运用于图像重建过程中。本文讨论这类中的基于字典学习的超分辨率重建方法。

2008年，Yang等人[8基于压缩感知理论，首次提出了基于稀疏编码的图像超分辨率重建（sparsecodingsuper-resolution，SCSR）方法。该方法假设高、低分辨率图像块在各自的高、低分辨率字典下所对应的稀疏表示系数是相同的，那么就可以通过低分辨率图像块在低分辨率字典下求解得到的稀疏表示系数与高分辨率字典相乘重建出相应的高分辨率图像块。在此基础上，Zeyde 等人对训练高、低分辨率字典进行了改进，利用主成份分析对低分辨率图像块所提取的特征进行降维，并用K-奇异值分解算法[10]训练低分辨率字典，最后通过高分辨率图像块与稀疏系数的伪逆相乘得到高分辨率字典。该方法不仅比SCSR能取得更好的重建效果，重建速度也有所提高[1I]。Lu等人[12]认为图像中结构相似的图像块应该具有相似的表示系数，因此在约束模型中添加非局部自相似性正则项，提出了基于非局部自相似稀疏编码的超分辨率重建方法。该方法保持了图像的几何结构，同时也增强了模型的稳定性。Cao 等人[13]在 Yang 的基础上,将约束模型中的 $\ell _ { 1 }$ 正则项改成 $\ell _ { p } ( 0 < p < 1 )$ 正则项，得到更稀疏的表示系数，从而提出了更有效的基于 $\ell _ { p } ( 0 < p < 1 )$ 正则化的超分辨率重建方法。Hojjat 等人[14]考虑彩色通道之间交互信息，通过颜色信息将基于稀疏表示的超分辨率重建方法扩展到多个颜色通道。Xie 等人[15]为了抑制稀疏编码噪声采用双向相似点进行建模和构造，形成一对互补的正则化项，然后对原始稀疏系数进行了额外的对齐，从而获得了更好的恢复效果。Yang等人[16]利用局部子字典对图像块进行编码，较好地刻画了图像的局部结构。

另外，Cai等人[17考虑表示系数的协同性，将SCSR中的 $\ell _ { 1 }$ 正则项替换为 $\ell _ { 2 }$ 正则项，同时认为一个较小窗口内的图像具有相似的几何结构，提出了局部结构相似性和协同表示

(local structural similarity and collaborative representation,LCR)的重建方法[18]，该方法大大加快了图像重建速度。Zhao等人[19]将稀疏性和协同性作为一个整体考虑，利用核范在约束模型中构建了一个新的正则项，提出了自适应稀疏编码的超分辨率（adaptive sparse coding based super-resolution,ASCSR）重建方法，自适应地平衡表示系数的稀疏性和协同性。

上述基于稀疏编码的超分辨率重建方法都是在假设"高、低分辨率图像块在各自的高、低分辨率字典下所对应的稀疏表示系数是相同的”下进行的。而Wang等人[20考虑高、低分辨率图像块对应的稀疏表示系数存在某种线性关系，在SCSR方法的基础上提出了基于半耦合字典学习（semi-coupled dictionary learning，SCDL）的稀疏编码算法，并应用于超分辨率图像重建中，取得较好的重建效果。

本文在半耦合字典学习的重建方法基础上，考虑表示系数的稀疏性和协同性，提出一种自适应半耦合字典学习的超分辨率 图像(adaptive semi-coupling dictionary for super-resolution，ASCDSR)重建方法。该方法假设高、低分辨率图像块在高、低分辨率字典下所对应的表示系数并不相等，而是存在某种线性关系，并利用核范在约束模型中构建了一个新的正则项，平衡表示系数的稀疏性和协同性，然后用交替方向乘子法(alternating direction method of multipliers,ADMM)[2I求解模型，最后将高分辨率字典与高分辨率下的表示系数相乘得到重建的高分辨率图像块。本文的方法同时考虑了表示系数的稀疏性和协同性，能自适应地平衡两者之间的关系，对噪声污染等实际情况具有较好的重建效果。

# 1本文所提的超分辨率重建方法

本节将在基于半耦合字典学习的重建方法基础上，考虑表示系数的稀疏性和协同性，给出一种基于自适应半耦合字典学习的超分辨率图像重建方法，具体方法如下。

对于待重建的低分辨率图像 $I _ { \ell }$ ，设 $Y = [ y _ { 1 } , y _ { 2 } , \cdots , y _ { n } ]$ ，其中（204号 $y _ { i }$ 为该低分辨率图像的块拉成的列向量， $i = 1 , 2 , \cdots , n$ ;$X = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } ]$ ，其中 $x _ { i }$ 是与 $y _ { i }$ 相对应的待建的高分辨率图像块所拉成的列向量， $i = 1 , 2 , \cdots , n$ .本文首先利用外部图片训练高、低分辨率字典 $D _ { x }$ 和 $D _ { \scriptscriptstyle { Y } }$ 及其稀疏表示系数之间的映射关系。

设 $X ^ { \prime } = [ x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , \cdots , x _ { m } ^ { \prime } ]$ ， $Y ^ { \prime } { = } [ y _ { 1 } ^ { \prime } , y _ { 2 } ^ { \prime } , { \cdots } , y _ { m } ^ { \prime } ]$ ，其中 $x _ { i } ^ { \prime }$ 和 $y _ { i } ^ { \prime }$ 分别表示外部图片相应的高、低分辨率图像块拉成的列向量，$i = 1 , 2 , \cdots , m$ ，本文首先利用 SCDL 中的优化模型训练高、低分辨率字典 $D _ { x }$ 和 $D _ { Y }$ 及其高、低分辨率图像的稀疏表示系数之间的映射关系，具体数学模型如下：

$$
\begin{array} { r l } & { \underset { { D _ { \boldsymbol { \chi } } , D _ { \boldsymbol { \gamma } } , W _ { { \boldsymbol { \chi } }  \boldsymbol { \gamma } } , W _ { { \boldsymbol { \gamma } }  \boldsymbol { \chi } } } } { \operatorname* { m i n } } \| \boldsymbol { X } ^ { \prime } - { D _ { \boldsymbol { \chi } } } { \boldsymbol { \Lambda } _ { \boldsymbol { \chi } ^ { \prime } } } \| _ { F } ^ { 2 } + \| \boldsymbol { Y } ^ { \prime } - { D _ { \boldsymbol { \chi } } } { \boldsymbol { \Lambda } _ { \boldsymbol { \gamma } ^ { \prime } } } \| _ { F } ^ { 2 } + } \\ & { ~ \gamma _ { 1 } \| { \boldsymbol { \Lambda } _ { \boldsymbol { \chi } ^ { \prime } } } - { \boldsymbol { W } _ { { \boldsymbol { \gamma } }  \boldsymbol { \chi } } } { \boldsymbol { \Lambda } _ { \boldsymbol { \gamma } ^ { \prime } } } \| _ { F } ^ { 2 } + \gamma _ { 2 } \| { \boldsymbol { \Lambda } _ { \boldsymbol { \gamma } ^ { \prime } } } - { \boldsymbol { W } _ { { \boldsymbol { \chi } }  \boldsymbol { \gamma } } } { \boldsymbol { \Lambda } _ { \boldsymbol { \chi } ^ { \prime } } } \| _ { F } ^ { 2 } + } \\ & { ~ \gamma _ { 3 } \| { \boldsymbol { \Lambda } _ { \boldsymbol { \chi } ^ { \prime } } } \| _ { 1 } + \gamma _ { 4 } \| { \boldsymbol { \Lambda } _ { \boldsymbol { \gamma } ^ { \prime } } } \| _ { 1 } + \gamma _ { 5 } \| { \boldsymbol { W } _ { { \boldsymbol { \chi } }  \boldsymbol { \gamma } } } \| _ { F } ^ { 2 } + \gamma _ { 6 } \| { \boldsymbol { W } _ { { \boldsymbol { \gamma } }  \boldsymbol { \chi } } } \| _ { F } ^ { 2 } } \\ & { ~ \mathrm { s . t . } \| { D _ { \boldsymbol { \chi } } } ( : , \boldsymbol { k } ) \| ^ { 2 } \leq 1 , \| { D _ { \boldsymbol { \gamma } } } ( : , \boldsymbol { k } ) \| ^ { 2 } \leq 1 , ~ k = 1 , 2 , \cdots , K , } \end{array}
$$

其中: $\Lambda _ { X ^ { \prime } }$ 为高分辨率图像块 $X ^ { \prime }$ 在高分辨率字典 $D _ { x }$ 下的表示系数矩阵， $\Lambda _ { Y ^ { \prime } }$ 为低分辨率图像块 $Y ^ { \prime }$ 在低分辨率字典 $D _ { Y }$ 下的表示系数矩阵， $W _ { X  Y }$ 为表示系数矩阵 $\Lambda _ { X ^ { \prime } }$ 到 $\Lambda _ { Y ^ { \prime } }$ 之间的映射矩阵， $W _ { Y  X }$ 为表示系数矩阵 $\Lambda _ { Y ^ { \prime } }$ 到 $\Lambda _ { \chi ^ { \prime } }$ 之间的映射矩阵， $\gamma _ { i }$ 是非负的正则化参数， $i = 1 , 2 , \cdots , 6$ ， $D ( : , k )$ 表示矩阵的第 $k$ 列，即字典的第 $k$ 个原子， $\boldsymbol { K }$ 为字典的原子数。

对于式(1)，本文运用文献[20]中设计的迭代算法交替求解 $D _ { \scriptscriptstyle { X } } , D _ { \scriptscriptstyle { Y } } , W _ { \scriptscriptstyle { X \to Y } } , W _ { \scriptscriptstyle { Y \to X } }$ .在高、低分辨率表示系数相同的假设下，SCSR和SCDL方法采用 $\ell _ { 1 }$ 正则项来强调表示系数的稀疏性而忽视其协同性，LCR采用 $\ell _ { 2 }$ 正则项注重表示系数的协同性而忽视稀疏性.本文所提的方法将利用式(1)训练得到的高、低分辨率字典 $D _ { \scriptscriptstyle { X } } , D _ { \scriptscriptstyle { Y } }$ 和映射矩阵 $W _ { X  Y } , W _ { Y  X }$ ，在SCDL的基础上同时考虑不同的表示系数的稀疏性和协同性，提出自适应半耦合字典学习的超分辨率图像重建模型求解表示系数：

$$
\begin{array} { l } { \displaystyle \underset { \Lambda _ { x } , \Lambda _ { Y } } { \operatorname* { m i n } } \left\| X - D _ { X } \Lambda _ { Y } \right\| _ { F } ^ { 2 } + \left\| Y - D _ { Y } \Lambda _ { Y } \right\| _ { F } ^ { 2 } + } \\ { \displaystyle \quad \lambda _ { 1 } \left\| \Lambda _ { X } - W _ { Y \to X } \Lambda _ { Y } \right\| _ { F } ^ { 2 } + \lambda _ { 2 } \left\| \Lambda _ { Y } - W _ { X \to Y } \Lambda _ { X } \right\| _ { F } ^ { 2 } + } \\ { \displaystyle \quad \quad \lambda _ { 3 } \displaystyle \sum _ { i } ^ { n } \left\| D _ { X } d i a g ( \alpha _ { i } ) \right\| _ { * } + \lambda _ { 4 } \displaystyle \sum _ { i } ^ { n } \left\| D _ { Y } d i a g ( \alpha _ { y _ { i } } ) \right\| _ { * } } \\ { \displaystyle s . t . \left\| D _ { X } \left( \colon , k \right) \right\| ^ { 2 } \le 1 , \left\| D _ { Y } \left( \colon , k \right) \right\| ^ { 2 } \le 1 , \ k = 1 , 2 , \cdots , K , } \end{array}
$$

其中: $\| X \| _ { * }$ 为矩阵 $X$ 的核范，即矩阵 $\boldsymbol { \cal X }$ 的奇异值之和， $\alpha _ { x _ { i } }$ 和 $\alpha _ { y _ { i } }$ 分别为矩阵 $\Lambda _ { x }$ 和 $\Lambda _ { Y }$ 的第 $i$ 列，即第 $i$ 个图像块所对应的表示系数， $i = 1 , 2 , \cdots , n$ ， $D i a g ( \alpha )$ 为以向量 $\alpha$ 为对角线元素的对角矩阵， $\lambda _ { i }$ 是非负的正则化参数， $i = 1 , 2 , \cdots , n$ 。

由文献[22,23]可知， $\| D d i a g ( \alpha ) \| _ { * }$ 具有如下性质:

$$
\begin{array} { r } { \| \alpha \| _ { 1 } \leq \| D d i a g ( \alpha ) \| _ { * } \leq \| \alpha \| _ { 2 } . } \end{array}
$$

当矩阵 $D$ 各列不相关时，即 $D ^ { T } D = I$ ， $\| D d i a g ( \alpha ) \| _ { * }$ 会接近$\left\| \alpha \right\| _ { 1 }$ ;当矩阵各列 $D$ 高度相关时， $\| D d i a g ( \alpha ) \| _ { * }$ 会接近 $\left\| \alpha \right\| _ { 2 }$ 。在实际应用中，训练得到的高低分辨率字典的原子往往既不是完全独立或者高度相关，所以式(2)运用于图像超分辨重建中可以在稀疏性和协同性之间寻找到合适的系数，以达到好的重建效果。

接下来求解式(2)。首先将式(2)分解成两个子问题：

$$
\begin{array} { l } { \underset { \Delta _ { Y } } { \arg \operatorname* { m i n } } \left\| Y - D _ { Y } \Lambda _ { Y } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \left\| \Lambda _ { X } - W _ { Y \to X } \Lambda _ { Y } \right\| _ { F } ^ { 2 } + } \\ { \lambda _ { 2 } \left\| \Lambda _ { Y } - W _ { X \to Y } \Lambda _ { X } \right\| _ { F } ^ { 2 } + \lambda _ { 4 } \displaystyle \sum _ { i } ^ { n } \left\| D _ { Y } d i a g ( \alpha _ { y _ { i } } ) \right\| _ { * } } \\ { = \displaystyle \sum _ { i } ^ { n } \left[ \begin{array} { c } { y _ { i } } \\ { \sqrt { \lambda _ { 1 } } \alpha _ { x _ { i } } } \\ { \sqrt { \lambda _ { 2 } } W _ { X \to Y } \alpha _ { x _ { i } } } \end{array} \right] - \left[ \begin{array} { c } { D _ { Y } } \\ { \sqrt { \lambda _ { 1 } } W _ { Y \to X } } \\ { \sqrt { \lambda _ { 2 } } I } \end{array} \right] \alpha _ { y _ { i } } \Bigg \| _ { 2 } ^ { 2 } + \lambda _ { 4 } \left\| D _ { Y } d i a g ( \alpha _ { y _ { i } } ) \right\| _ { * } , } \end{array}
$$

$$
\begin{array} { l } { \underset { \Delta _ { X } } { \mathrm { a r g } \operatorname* { m i n } } \left\| X - D _ { X } \Lambda _ { X } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \left\| \Lambda _ { X } - W _ { Y \to X } \Lambda _ { Y } \right\| _ { F } ^ { 2 } + } \\ { \lambda _ { 2 } \left\| \Lambda _ { Y } - W _ { X \to Y } \Lambda _ { X } \right\| _ { F } ^ { 2 } + \lambda _ { 3 } \displaystyle \sum _ { i } ^ { n } \left\| D _ { X } d i a g ( \alpha _ { x _ { i } } ) \right\| _ { * } } \\ { = \displaystyle \sum _ { i } ^ { n } \left[ \left[ \begin{array} { c } { \lambda _ { i } } \\ { \sqrt { \lambda _ { 2 } } \alpha _ { y _ { i } } } \\ { \sqrt { \lambda _ { 1 } } W _ { Y \to X } \alpha _ { y _ { i } } } \end{array} \right] - \left[ \begin{array} { c } { D _ { X } } \\ { \sqrt { \lambda _ { 2 } } W _ { X \to Y } } \\ { \sqrt { \lambda _ { 1 } } I } \end{array} \right] \alpha _ { x _ { i } } \right\| _ { 2 } ^ { 2 } + \lambda _ { 3 } \left\| D _ { X } d i a g ( \alpha _ { x _ { i } } ) \right\| _ { * } . } \end{array}
$$

其次，运用ADMM算法求解式(4)(5)。由于式(4)(5)结构相似，这里只给出式(4)的具体求解过程。为了便于描述，下面给出式(4)的向量求解形式。令

$$
\overline { { y } } _ { i } = [ \begin{array} { c } { y _ { i } } \\ { \sqrt { \lambda _ { 1 } } \alpha _ { x _ { i } } } \\ { \sqrt { \lambda _ { 2 } } W _ { x  Y } \alpha _ { x _ { i } } } \end{array} ] , \overline { { D } } _ { Y } = [ \begin{array} { c } { D _ { Y } } \\ { \sqrt { \lambda _ { 1 } } W _ { Y  X } } \\ { \sqrt { \lambda _ { 2 } } I } \end{array} ] ,
$$

$$
e _ { i } = \overline { { y } } _ { i } - \overline { { D } } _ { Y } \alpha _ { y _ { i } } , Z _ { i } = D _ { Y } d i a g ( \alpha _ { y _ { i } } )
$$

此时，式(4)的向量形式为

$$
\arg \operatorname* { m i n } _ { \alpha _ { y _ { i } } } \big \| e _ { i } \big \| _ { 2 } ^ { 2 } + \lambda _ { 4 } \big \| Z _ { i } \big \| _ { * } ,
$$

则式(7)的增广拉格朗日函数为

$$
\begin{array} { l } { { \displaystyle { \cal L } ( Z _ { i } , \alpha _ { y _ { i } } , e _ { i } , \nu , H , \rho ) = \left\| e _ { i } \right\| _ { 2 } ^ { 2 } + \lambda _ { 4 } \left\| Z _ { i } \right\| _ { * } } } \\ { { \displaystyle ~ + \langle \nu , \overline { { { y } } } _ { i } - \overline { { { D } } } _ { Y } \alpha _ { y _ { i } } - e _ { i } \rangle + \langle H , Z _ { i } - D _ { Y } d i a g ( \alpha _ { y _ { i } } ) \rangle } } \\ { { \displaystyle ~ + \frac { \rho } { 2 } \Big ( \left\| \overline { { { y } } } _ { i } - \overline { { { D } } } _ { Y } \alpha _ { y _ { i } } - e _ { i } \right\| _ { 2 } ^ { 2 } + \left\| Z _ { i } - D _ { Y } d i a g ( \alpha _ { y _ { i } } ) \right\| _ { F } ^ { 2 } \Big ) , } } \end{array}
$$

其中： $\nu$ 和 $H$ 为拉格朗日乘子， $\langle \cdot , \cdot \rangle$ 表示矩阵或者向量的内积。根据ADMM算法，式(8)迭代流程如下：

$$
\left\{ \begin{array} { l l } { Z _ { i } ^ { k + 1 } = \arg \underset { z _ { i } } { \mathrm { m i n } } L ( Z _ { i } , \alpha _ { y _ { i } } ^ { k } , e _ { i } ^ { k } , \nu ^ { k } , H ^ { k } , \rho ^ { k } ) } \\ { \alpha _ { y _ { i } } ^ { k + 1 } = \arg \underset { \alpha _ { y _ { i } } } { \mathrm { m i n } } L ( Z _ { i } ^ { k + 1 } , \alpha _ { y _ { i } } , e _ { i } ^ { k } , \nu ^ { k } , H ^ { k } , \rho ^ { k } ) } \\ { e _ { i } ^ { k + 1 } = \arg \underset { e _ { i } } { \mathrm { m i n } } L ( Z _ { i } ^ { k + 1 } , \alpha _ { y _ { i } } ^ { k + 1 } , e _ { i } , \nu ^ { k } , H ^ { k } , \rho ^ { k } ) } \\ { \nu ^ { k + 1 } = \nu ^ { k } + \rho ^ { k } ( \bar { y } _ { i } - \bar { D } _ { \gamma } \alpha _ { y _ { i } } ^ { k + 1 } - e _ { i } ^ { k + 1 } ) } \\ { H ^ { k + 1 } = H ^ { k } + \rho ^ { k } ( Z _ { i } ^ { k + 1 } - D _ { \gamma } d i a g ( \alpha _ { y _ { i } } ^ { k + 1 } ) ) } \\ { \rho ^ { k + 1 } = \beta \rho ^ { k } } \end{array} \right.
$$

其中： $\overline { { \boldsymbol { x } } } _ { j } = [ \begin{array} { c } { \boldsymbol { x } _ { j } } \\ { \sqrt { \lambda _ { 2 } } \boldsymbol { \alpha } _ { y _ { j } } } \\ { \sqrt { \lambda _ { 1 } } \boldsymbol { W } _ { Y  X } \boldsymbol { \alpha } _ { y _ { j } } } \end{array} ] , \bar { \boldsymbol { D } } _ { X } = [ \begin{array} { c } { \boldsymbol { D } _ { X } } \\ { \sqrt { \lambda _ { 2 } } \boldsymbol { W } _ { X  Y } } \\ { \sqrt { \lambda _ { 1 } } \boldsymbol { I } } \end{array} ] ,$

式(9)中的 $Z _ { i } ^ { k + 1 }$ 的具体求解公式如下：

$$
\begin{array} { c } { { Z _ { _ { i } } ^ { k + 1 } : = } } \\ { { \displaystyle \operatorname * { a r g m i n } _ { Z _ { _ { i } } } \lambda _ { 4 } \| Z _ { i } \| _ { * } + \langle H ^ { k } , Z _ { i } - D _ { _ { Y } } d i a g ( \alpha _ { _ { y _ { i } } } ^ { k } ) \rangle + \displaystyle \frac { \rho ^ { k } } { 2 } \big \| Z _ { i } - D _ { _ { Y } } d i a g ( \alpha _ { _ { y _ { i } } } ^ { k } ) \big \| _ { _ { F } } ^ { 2 } = } } \\ { { \displaystyle \operatorname * { a r g m i n } _ { Z _ { _ { i } } } \lambda _ { _ { 4 } } \| Z _ { i } \| _ { * } + \displaystyle \frac { \rho ^ { k } } { 2 } \left\| Z _ { i } - ( D _ { _ { Y } } d i a g ( \alpha _ { _ { y _ { i } } } ^ { k } ) - \displaystyle \frac { H ^ { k } } { \rho ^ { k } } ) \right\| _ { _ { F } } ^ { 2 } = } } \\ { { \displaystyle \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \rho _ { _ { _ { j } } } } ^ { _ { \lambda _ { 4 } } } \left( D _ { Y } d i a g ( \alpha _ { _ { y _ { i } } } ^ { k } ) - \displaystyle \frac { H ^ { k } } { \rho ^ { k } } \right) }  \end{array}
$$

其中： $\varphi$ 为奇异值缩放算子，设 $D _ { Y } d i a g ( \alpha _ { y _ { i } } ^ { k } ) - \frac { H ^ { k } } { \rho ^ { k } }$ 的奇异值分解为 $U d i a g ( \sigma ) V ^ { T }$ ，其中 $\sigma$ 为奇异值 $\sigma _ { i }$ 组成的向量，则式(10)为

$$
Z _ { i } { ^ { k + 1 } } = U d i a g \left( \phi _ { \frac { \lambda _ { \mathrm { y } } } { \rho _ { k } } } ( \sigma ) \right) V ^ { T } = U d i a g \left( \operatorname * { m a x } \left\{ \sigma _ { i } - \frac { \lambda _ { \mathrm { y } } } { \rho _ { k } } , 0 \right\} \right) V ^ { T }
$$

式(9)中的 $\alpha _ { y _ { i } } ^ { k + 1 }$ 的具体求解公式如下：

$$
\begin{array} { l } { \displaystyle \alpha _ { y _ { i } } ^ { k + 1 } : = \arg \underset { \alpha _ { y _ { i } } } { \mathrm { m i n } } \langle \nu ^ { k } , - \bar { D } _ { Y } \alpha _ { y _ { i } } \rangle + \langle H , - D _ { Y } d i a g ( \alpha _ { y _ { i } } ) \rangle + } \\ { \displaystyle \quad \quad \frac { \rho ^ { k } } { 2 } \Bigg ( \left\| \overline { { y } } _ { i } - \bar { D } _ { Y } \alpha _ { y _ { i } } - e _ { i } ^ { k } \right\| _ { 2 } ^ { 2 } + \left\| Z _ { i } ^ { k + 1 } - D _ { Y } d i a g ( \alpha _ { y _ { i } } ) \right\| _ { F } ^ { 2 } \Bigg ) } \\ { \displaystyle \quad = A _ { Y } d i a g \Bigg ( ( D _ { Y } ) ^ { T } \Bigg ( \frac { 1 } { \rho ^ { k } } H ^ { k } + Z _ { i } ^ { k + 1 } \Bigg ) \Bigg ) + A _ { Y } ( \bar { D } _ { Y } ) ^ { T } \Bigg ( \frac { 1 } { \rho ^ { k } } \nu ^ { k } + \overline { { y } } _ { i } - e _ { i } ^ { k } \Bigg ) } \end{array}
$$

其中： $A _ { Y } : = \left( ( \bar { D } _ { Y } ) ^ { T } \bar { D } _ { Y } + P ( D _ { Y } ^ { T } D _ { Y } ) \right) ^ { - 1 }$ ， $P$ 为保留对角线元素，其他元素为零的矩阵操作。

式(9)中的 $e _ { i } ^ { k + 1 }$ 的具体求解公式如下：

$$
\begin{array} { r l } & { e _ { i } ^ { k + 1 } : = \underset { e _ { i } } { \arg \operatorname* { m i n } } \left\| e _ { i } \right\| _ { 2 } ^ { 2 } + \left. \nu ^ { k } , \overline { { y } } _ { i } - \overline { { D } } _ { Y } \alpha _ { y _ { i } } ^ { k + 1 } - e _ { i } \right. + \displaystyle \frac { \rho ^ { k } } { 2 } \left\| \overline { { y } } _ { i } - \overline { { D } } _ { Y } \alpha _ { y _ { i } } ^ { k + 1 } - e _ { i } \right\| _ { 2 } ^ { 2 } } \\ & { \quad \quad = \underset { e _ { i } } { \arg \operatorname* { m i n } } \frac { 1 } { e _ { i } } \left\| e _ { i } \right\| _ { 2 } ^ { 2 } + \displaystyle \frac { 1 } { 2 } \left\| \frac { 1 } { \rho ^ { k } } \nu ^ { k } + \overline { { y } } _ { i } - \overline { { D } } _ { Y } \alpha _ { y _ { i } } ^ { k + 1 } - e _ { i } \right\| _ { 2 } ^ { 2 } } \\ & { \quad \quad = \left( \frac { 1 } { \rho ^ { k } } \nu ^ { k } + \overline { { y } } _ { i } - \overline { { D } } _ { Y } \alpha _ { y _ { i } } ^ { k + 1 } - e _ { i } \right) \Biggl / \left( \frac { 2 } { \rho ^ { k } } + 1 \right) } \end{array}
$$

综上所述，式(9)的解为

$$
\begin{array} { r l } & { \Bigg [ Z _ { i } ^ { k + 1 } = \varphi _ { \underline { { \lambda } } _ { i } } \Bigg ( D _ { r } d i a g ( \alpha _ { y } ^ { k } ) - \frac { H ^ { k } } { \rho ^ { k } } \Bigg ) } \\ & { \Bigg | \alpha _ { y } ^ { k + 1 } = A _ { r } d i a g \Bigg ( ( D _ { r } ) ^ { r } \Bigg ( \frac { 1 } { \rho ^ { k } } H ^ { k } + Z _ { i } ^ { k + 1 } \Bigg ) \Bigg ) + A _ { r } ( \overline { { D } } _ { r } ) ^ { r } \Bigg ( \frac { 1 } { \rho ^ { k } } \nu ^ { k } + \overline { { y } } _ { i } - e _ { i } ^ { k } \Bigg ) } \\ & { \Bigg | e _ { i } ^ { k + 1 } = \Bigg ( \frac { 1 } { \rho ^ { k } } \nu ^ { k } + \overline { { y } } _ { i } - \overline { { D } } _ { r } \alpha _ { y } ^ { k + 1 } - e _ { i } \Bigg ) / \Bigg ( \frac { 2 } { \rho ^ { k } } + 1 \Bigg ) } \\ & { \Bigg | \nu ^ { k + 1 } = \nu ^ { k } + \rho ^ { k } ( \overline { { y } } _ { i } - \overline { { D } } _ { r } \alpha _ { y } ^ { k - 1 } - e _ { i } ^ { k + 1 } ) } \\ & { \Bigg | H ^ { k + 1 } = H ^ { k } + \rho ^ { k } ( Z _ { i } ^ { k + 1 } - D _ { r } d i a g ( \alpha _ { y } ^ { k + 1 } ) ) } \\ & { \Bigg ( \rho ^ { k + 1 } = \beta \rho ^ { k } } \end{array}
$$

类似地，可以得到式(5)的迭代解：

$$
\begin{array} { r l } & { \Bigg [ Z _ { j } ^ { k + 1 } = \underbrace { \varphi _ { _ { \lambda } } } _ { \rho ^ { k } } \Bigg ( D _ { x } d i a g ( \alpha _ { _ { \lambda } } ^ { k } ) - \frac { H ^ { k } } { \rho ^ { k } } \Bigg ) } \\ & { \Bigg | \alpha _ { x _ { \lambda } ^ { k + 1 } } ^ { \pm 1 } = A _ { x } d i a g \Bigg ( ( D _ { x } ) ^ { T } \left( \frac { 1 } { \rho ^ { k } } H ^ { k } + Z _ { j } ^ { k + 1 } \right) \Bigg ) + A _ { x } ( \bar { D } _ { x } ) ^ { T } \Bigg ( \frac { 1 } { \rho ^ { k } } \nu ^ { k } + \bar { x } _ { j } - e _ { j } ^ { k } \Bigg ) } \\ & { \Bigg \{ e _ { j } ^ { k + 1 } = \left( \frac { 1 } { \rho ^ { k } } \nu ^ { k } + \bar { x } _ { j } - \bar { D } _ { x } \alpha _ { _ { \lambda } ^ { k + 1 } } ^ { k + 1 } - e _ { j } \right) \Bigg / \left( \frac { 2 } { \rho ^ { k } } + 1 \right) } \\ & { \Bigg | \nu ^ { k + 1 } = \nu ^ { k } + \rho ^ { \downarrow } ( \bar { x } _ { j } - \bar { D } _ { x } \alpha _ { _ { \lambda } ^ { k + 1 } } ^ { k + 1 } - e _ { j } ^ { k + 1 } ) } \\ & { \Bigg | H ^ { k + 1 } = H ^ { k } + \rho ^ { k } ( Z _ { j } ^ { k + 1 } - D _ { x } d i a g ( \alpha _ { x _ { j } } ^ { k + 1 } ) ) } \\ & { \Bigg | \rho ^ { k + 1 } = \beta \rho ^ { k } } \end{array}
$$

$e _ { j } = \overline { { x } } _ { j } - \overline { { D } } _ { X } \alpha _ { x _ { j } } , A _ { X } : = \left( ( \overline { { D } } _ { X } ) ^ { T } \overline { { D } } _ { X } + P ( D _ { X } ^ { T } D _ { X } ) \right) ^ { - 1 }$ ， $P$ 为保留对角线元素，其他元素为零的矩阵操作。

本文中式(14)和(15)迭代的终止条件为

$$
\operatorname* { m a x } \left( \left\| { \overline { { c } } } - D \alpha - e \right\| _ { \infty } , \left\| Z - D d i a g ( \alpha ) \right\| _ { \infty } \right) \leq \varepsilon
$$

其中： $\varepsilon$ 为预设的阈值， $\overline { { c } }$ 在式(14)中为 $\overline { { y } } _ { i }$ ，在式(15)中为 $\overline { { \boldsymbol { x } } } _ { j }$ ，$D$ 在式(14)中为 $\overline { { D } } _ { \scriptscriptstyle Y }$ ，在式(15)中为 $\overline { { D } } _ { x }$ ， $\alpha$ 在式(14)中为 $\alpha _ { y _ { i } }$ ，在式(15)中为 $\alpha _ { x _ { j } }$ 。

利用式(1)训练出来的高分辨率字典 $D _ { x }$ 和式(4)(5)求解出来的高分辨率图像块所对应的系数矩阵 $\Lambda _ { x }$ ，可以重建出高分辨率图像块

$$
X \approx D _ { X } \Lambda _ { X }
$$

综上，本文所提的基于自适应半耦合字典学习的超分辨率图像重建算法如算法1所示。

算法1基于自适应半耦合字典学习的超分辨率图像重建算法

输入：需要重建的低分辨率图像 $I _ { \ell }$ ，外部训练图片相应的高、低分辨率图像块拉成的列向量所组成的矩阵 $X ^ { \prime } = [ x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , \cdots , x _ { m } ^ { \prime } ]$ ，$Y ^ { \prime } { = } [ y _ { 1 } ^ { \prime } , y _ { 2 } ^ { \prime } , { \cdots } , y _ { m } ^ { \prime } ]$ 。

通过式(1)训练得到高分辨率字典 $D _ { \chi }$ ，低分辨率字典 $D _ { \gamma }$ ，以及高、低分辨率系数之间的相互映射矩阵 $W _ { X  Y }$ 和 $W _ { Y  X }$ 。

先对图像 $I _ { \ell }$ 双三次插值，然后提取低分辨率图像块$Y = [ y _ { 1 } , y _ { 2 } , \cdots , y _ { n } ]$ 。

对于每一个低分辨率图像块 $y _ { i }$ ，通过式(4)(5)求解得到其对应的高分辨率字典下的表示系数 $\alpha _ { x _ { i } } ^ { * }$ ，并利用 $D _ { x } \alpha _ { x _ { i } } ^ { * }$ 得到 $y _ { i }$ 的重建图像块$x _ { i }$ 。

将所有重建后的图像块 $X = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } ]$ 融合成为图像 $I _ { h }$ 。输出：重建后的图像 $I _ { h }$ 。

# 2 实验与分析

本章将通过本文方法和Bicubic方法、SCSR[8方法、LCR[18]方法、ASCSR[19]方法和SCDL[20]等方法的比较实验说明本文提出的ASCDSR算法在图像超分辨重建中的重要作用。首先，在无噪声情况下进行实验比较；其次，为了验证本文方法的鲁棒性，将在高斯噪声、椒盐噪声等情况下进行图像重建比较。

实验均采用峰值信噪比（peak signal-to-noise ratio，PSNR）和结构相似性（structural similarity index，SSIM）作为图像超分辨率重建效果的评价指标。实验中所用到的测试图像如图1所示。

为了避免由于重建阶段提取图像块的步长和图像块的尺寸不同造成重建效果不同，实验中提取图像块的步长统一为4，尺寸为 $5 { \times } 5$ 。高、低分辨率字典大小均为512，重建模型的正则化参数 $\lambda _ { 1 } = \lambda _ { 2 } = \lambda _ { 3 } = \lambda _ { 4 } = 0 . 1$ 。本文实验在Intel®XeonCPUE5-1630v3 $@$ 3.70GHz、内存为96GB、操作系统为Windows10、MATLAB版本为R2016b的计算环境中进行。

# 2.1无噪声图像重建

本节将进行本文所提的ASCDSR方法和现有的Bicubic方法、SCSR[8]方法、LCR[18]方法、ASCSR[19]方法和SCDL[20]在无噪声环境下的实验比较。表1是上述方法对不同的测试图像在放大因子为2时重建图像的峰值信噪比(dB)和结构相似度的比较，其中效果排第一的指标值用黑色粗体标注，效果排第二的指标值用下划线标注。为了从视觉上直观感受重建效果，图2给出了不同方法对图像"Bird"的重建效果图。

![](images/783f2c8a3fdc8b941f43910ac24b813c60b59d3bb1ee4e3ab3223994f5014970.jpg)  
图1本文实验所用的测试图像  
Fig.1Testing images used in the experiments表1六种重建方法在无噪声环境下的比较结果

![](images/ab4faa2d174185f86f90eef6deb900f5e5158b9db987fda2650861bef8b05b88.jpg)  
图2六种重建方法在无噪声“Bird”图像上的重建效果图Fig.2.Reconstructed“Bird”images of six methodswithout noise

从表1可以看出，在无噪声的情况下本文所提的ASCDSR方法对所有7张测试图像都能达到最好的效果。即使本文方法和SCDL方法在图像Flower"上取得相同的峰值信噪比，但是本文方法重建图像的结构相似度要高于SCDL所重建的。

Table 1 Comparison results of six reconstruction methods undei   
表2六种重建方法在椒盐噪声下的比较结果  

<html><body><table><tr><td colspan="8">noiseless environment</td></tr><tr><td>图像</td><td>比较项</td><td>Bicubic</td><td>SCSR[8]</td><td>LCR[18]</td><td>ASCSR[19]</td><td>SCDL[20]</td><td>ASCDSR</td></tr><tr><td rowspan="2">pens</td><td>PSNR</td><td>32.00</td><td>32.94</td><td>33.11</td><td>33.20</td><td>33.18</td><td>33.30</td></tr><tr><td>SSIM</td><td>0.9210</td><td>0.9369</td><td>0.9402</td><td>0.9436</td><td>0.9417</td><td>0.9446</td></tr><tr><td rowspan="2">parrots</td><td>PSNR</td><td>31.38</td><td>32.65</td><td>33.04</td><td>33.03</td><td>33.14</td><td>33.18</td></tr><tr><td>SSIM</td><td>0.9376</td><td>0.9468</td><td>0.9473</td><td>0.9492</td><td>0.9503</td><td>0.9519</td></tr><tr><td rowspan="2">flower</td><td>PSNR</td><td>30.45</td><td>31.82</td><td>31.93</td><td>31.96</td><td>32.00</td><td>32.00</td></tr><tr><td>SSIM</td><td>0.8949</td><td>0.9219</td><td>0.9179</td><td>0.9221</td><td>0.9235</td><td>0.9246</td></tr><tr><td rowspan="2">bird</td><td>PSNR</td><td>36.69</td><td>37.92</td><td>38.15</td><td>38.30</td><td>38.14</td><td>38.59</td></tr><tr><td>SSIM</td><td>0.9710</td><td>0.9727</td><td>0.9756</td><td>0.9770</td><td>0.9755</td><td>0.9790</td></tr><tr><td rowspan="2">Elephant</td><td>PSNR</td><td>33.12</td><td>34.15</td><td>34.28</td><td>34.60</td><td>34.51</td><td>34.62</td></tr><tr><td>SSIM</td><td>0.9155</td><td>0.9247</td><td>0.9314</td><td>0.9351</td><td>0.9324</td><td>0.9354</td></tr><tr><td rowspan="2">Foreman</td><td>PSNR</td><td>32.71</td><td>33.57</td><td>34.08</td><td>33.84</td><td>34.14</td><td>34.20</td></tr><tr><td>SSIM</td><td>0.9447</td><td>0.9516</td><td>0.9549</td><td>0.9540</td><td>0.9561</td><td>0.9576</td></tr><tr><td rowspan="2">Pepper</td><td>PSNR</td><td>31.90</td><td>33.34</td><td>33.38</td><td>33.21</td><td>33.22</td><td>33.50</td></tr><tr><td>SSIM</td><td>0.9367</td><td>0.9455</td><td>0.9469</td><td>0.9468</td><td>0.9471</td><td>0.9506</td></tr></table></body></html>

# 2.2椒盐噪声

本节将设计实验考察本文ASCDSR方法和Bicubic方法、SCSR[8]方法、LCR[18]方法、ASCSR[19]方法、SCDL[20]对带有椒盐噪声图像的重建效果。对图像“elephant""foreman"和"pepper"分别添加噪声密度 $n$ 为 $5 { \times } 1 0 ^ { - 4 }$ 和 $1 \times 1 0 ^ { - 3 }$ 的椒盐噪声。表2是上述方法对带有椒盐噪声图像"elephant""foreman"和"pepper"在放大因子为2时的重建效果，其中效果排第一的指标值用黑色粗体标注，效果排第二的指标值用下划线标注。从表2可以看出，本文ASCDSR方法重建出来的图像在峰值信噪比和结构相似度上都要比其他方法所得的相应值要好。

Table 2Comparison results of six reconstruction methods with salt and pepper noise   

<html><body><table><tr><td></td><td>图像</td><td>比较项</td><td>Bicubic</td><td>SCSR[8]</td><td>LCR[18]</td><td>ASCSR[19]</td><td>SCDL[20]</td><td>ASCDSR</td></tr><tr><td rowspan="4">elephant</td><td rowspan="2">n=5×10-4</td><td>PSNR</td><td>32.77</td><td>33.15</td><td>33.22</td><td>33.51</td><td>33.43</td><td>33.51</td></tr><tr><td>SSIM</td><td>0.9111</td><td>0.9171</td><td>0.9236</td><td>0.9281</td><td>0.9249</td><td>0.9278</td></tr><tr><td rowspan="2">n=1×10-3</td><td>PSNR</td><td>32.59</td><td>32.70</td><td>32.75</td><td>32.90</td><td>32.93</td><td>33.01</td></tr><tr><td>SSIM</td><td>0.9091</td><td>0.9140</td><td>0.9202</td><td>0.9214</td><td>0.9213</td><td>0.9242</td></tr><tr><td rowspan="4">foreman</td><td>n=5×10-4</td><td>PSNR</td><td>32.56</td><td>33.11</td><td>33.57</td><td>33.38</td><td>33.62</td><td>33.66</td></tr><tr><td rowspan="2"></td><td>SSIM</td><td>0.9414</td><td>0.9455</td><td>0.9487</td><td>0.9436</td><td>0.9500</td><td>0.9514</td></tr><tr><td>PSNR</td><td>32.09</td><td>31.90</td><td>32.17</td><td>32.09</td><td>32.21</td><td>32.35</td></tr><tr><td rowspan="2">n=1×10-3</td><td>SSIM</td><td>0.9340</td><td>0.9333</td><td>0.9367</td><td>0.9351</td><td>0.9381</td><td>0.9394</td></tr><tr><td>PSNR n =5×10-4</td><td>31.66</td><td>32.59</td><td>32.17</td><td>32.47</td><td></td><td>32.49</td><td>32.71</td></tr><tr><td rowspan="3">pepper</td><td></td><td>SSIM</td><td>0.9326</td><td>0.9387</td><td>0.9359</td><td>0.9396</td><td>0.9403</td><td>0.9437</td></tr><tr><td rowspan="2">n=1×10-3</td><td>PSNR</td><td>31.61</td><td>32.35</td><td>32.00</td><td>32.27</td><td>32.28</td><td>32.49</td></tr><tr><td>SSIM</td><td>0.9309</td><td>0.9348</td><td>0.9324</td><td>0.9359</td><td>0.9367</td><td>0.9400</td></tr></table></body></html>

Table 3Comparison results of six reconstruction methods with Gaussian noise   

<html><body><table><tr><td colspan="2">图像</td><td>比较项</td><td>Bicubic</td><td>SCSR[8]</td><td>LCR[18]</td><td>ASCSR[19]</td><td>SCDL[20]</td><td>ASCDSR</td></tr><tr><td rowspan="3">elephant</td><td rowspan="3">g=0.01</td><td>PSNR</td><td>32.93</td><td>33.45</td><td>33.66</td><td>33.97</td><td>33.86</td><td>34.00</td></tr><tr><td>SSIM</td><td>0.9097</td><td>0.9073</td><td>0.9160</td><td>0.9200</td><td>0.9167</td><td>0.9201</td></tr><tr><td>PSNR</td><td>32.40</td><td>31.79</td><td>31.90</td><td>32.46</td><td>32.36</td><td>32.47</td></tr><tr><td rowspan="5">foreman</td><td>9=0.02</td><td>SSIM</td><td>0.8936</td><td>0.8643</td><td>0.8752</td><td>0.8796</td><td>0.8766</td><td>0.8796</td></tr><tr><td>g=0.01</td><td>PSNR</td><td>32.54</td><td>33.03</td><td>33.39</td><td>33.27</td><td>33.49</td><td>33.59</td></tr><tr><td></td><td>SSIM</td><td>0.9346</td><td>0.9231</td><td>0.9231</td><td>0.9308</td><td>0.9279</td><td>0.9297</td></tr><tr><td>9=0.02</td><td>PSNR</td><td>32.07</td><td>31.79</td><td>31.90</td><td>31.97 1.97</td><td>32.10</td><td>32.20</td></tr><tr><td></td><td>SSIM</td><td>0.9083</td><td>0.8579</td><td>0.8533</td><td>0.8630</td><td>0.8624</td><td>0.8639</td></tr><tr><td rowspan="4">pepper</td><td>9=0.01</td><td>PSNR</td><td>31.75</td><td>32.74</td><td>32.42</td><td>32.72</td><td>32.75</td><td>32.94</td></tr><tr><td></td><td>SSIM</td><td>0.9287</td><td>0.9208</td><td>0.9210</td><td>0.9246</td><td>0.9253</td><td>0.9282</td></tr><tr><td>9=0.02</td><td>PSNR</td><td>31.35</td><td>31.40</td><td>31.30</td><td>31.54</td><td>31.55</td><td>31.69</td></tr><tr><td></td><td>SSIM</td><td>0.9066</td><td>0.8608</td><td>0.8653</td><td>0.8673</td><td>0.8694</td><td>0.8722</td></tr></table></body></html>

# 2.3 高斯噪声

本节将设计实验考察本文ASCDSR方法和Bicubic方法、SCSR[8]方法、LCR[18]方法、ASCSR[19]方法、SCDL[20]对带有高斯噪声图像的重建效果。对图像"elephant""foreman"和"pepper"分别添加均值为0、标准差 $\sigma$ 为0.01和0.02的高斯噪声。表3是上述方法对带有高斯噪声图像“elephant""foreman"和"pepper"在放大因子为2时的重建效果，其中效果排第一的指标值用黑色粗体标注，效果排第二的指标值用下划线标注。

从表3可以看出，本文ASCDSR方法在峰值信噪比上都保持最高的效果，尤其 $\scriptstyle { \sigma = 0 . 0 2 }$ 时，SCDL等方法对图像“elephant"重建效果均比Bicubic差，只有本文的方法效果优于Bicubic。在结构相似度上本文方法基本排在第二或者第三，除了图像"elephant"在标准差为0.01的高斯噪声污染下，所有基于字典学习的方法的结构相似度均不如Bicubic。

# 2.4重建时间

本节将对本文ASCDSR方法和SCSR[8方法、LCR[18]方法、ASCSR[19]方法、SCDL[20]方法进行重建时间比较，具体重建时间见表4，其中表4中的时间是图1中七张图像的重建时间的平均值。

表3六种重建方法在高斯噪声下的比较结果  
表4五种算法的重建时间比较  
Table 4Reconstruction time comparison of five methods   

<html><body><table><tr><td>方法</td><td>重建时间/s</td></tr><tr><td>LCR[18]</td><td>1.55</td></tr><tr><td>SCSR[8]</td><td>4.72</td></tr><tr><td>SCDL[20]</td><td>57.73</td></tr><tr><td>ASCSR[19]</td><td>1373.92</td></tr><tr><td>本文ASCDSR</td><td>1798.05</td></tr></table></body></html>

从表4中可以看出，LCR、SCSR和SCDL方法的重建速度较快，ASCSR和本文的方法重建速度较慢。原因是LCR中用解析解来求解 $\ell _ { 2 }$ 正则化模型，无须迭代过程。SCSR和SCDL都是求解简单的 $\ell _ { 1 }$ 正则化模型，用压缩感知的方法就可以较快地求解。而ASCSR和本文的方法是求解带有核范的正则化模型，需要用ADMM来求解。在求解过程中，由于核范正则项需要涉及矩阵的奇异值分解，所以重建时间要比LCR、SCSR和SCDL长。另外，本文的方法比ASCSR多考虑高、低分辨率系数之间的线性映射关系，所以重建时间上又要比ASCSR方法长。

# 3 结束语

本文基于半耦合字典学习的超分辨率重建方法上，考虑表示系数的稀疏性和协同性，利用核范数构建一个新的正则项，并用交替方向乘子法(ADMM)求解优化模型，得到了基于自适应半耦合字典学习的超分辨率图像重建算法。该方法假设高、低分辨率系数存在某种映射关系，从而放宽了模型的约束条件，同时根据字典的变化能自适应地平衡稀疏性和协同性。实验说明本文所提方法要比目前已有的一些重建方法具有更好的峰值信噪比和结构相似度，且对于噪声干扰也具有一定的鲁棒性。

模型中没有考虑局部相似性等其他先验知识，下一步工作将考虑如何加入合理的先验知识来提高图像的重建效果。

# 参考文献：

[1]Sina F,Dirk R,Michael E,el al．Advances and challenges in super-resolution [J].International Journal of Imaging Systems and Technology,2004,2: 47-57.   
[2]Wang Nannan,Tao Dacheng,Gao Xinbo,et al.A comprehensive survey to face hallucination [J]. International Journal of Computer Vision, 2014,106(1):9-30.   
[3]Wang Lizhe,Lu Ke,Liu Peng.Compressed sensing of a remote sensing image based on the priors of the reference image [J].IEEE Geoscience and Remote Sensing Letters,2014,12(4):736-740.   
[4]Greenspan H. Super-resolution in medical imaging [J]. The Computer Journal,2009,52(1): 43-63.   
[5]Dodgson N A.Quadratic interpolation for image resampling [J].IEEE Trans on Image Processing,1997,6(9):1322-1326.   
[6]Irani M,Peleg S.Improving resolution by image registration [J]. CVGIP:Graphical Models and Image Processing，1991，53(3): 231-239.   
[7]Su Heng,Zhou Jie,Zhang Zhihao.Survey of super-resolution image reconstruction methods [J].ACTA Automatica Sinica,2013,39(8): 1202-1213.   
[8]Yang Jianchao,Wright J,Huang T S,et al.Image super-resolution via sparse representation [J].IEEE Trans on Image Processing，2010, 19(11): 2861-2873.   
[9]Yang Wenhan,Feng Jiashi,Yang Jianchao,et al.Deep edge guided recurrent residual learning for image super-resolution [J].IEEE Trans on Image Processing,2017,26(12): 5895-5907.   
[10] Aharon M, Elad M,Bruckstein A.K-SVD:An algorithm for designing overcomplete dictionaries for sparse representation [J].IEEE Trans on Signal Processing,2006,54(11): 4311-4322.   
[11] Zeyde R，Elad M，Proter M.On single image scale-up using sparse-representations [C]//Proc of the 7th International Conference on Curves and Surfaces.Berlin: Springer,201o:711-730.   
[12] Lu Xiaoqiang，Yuan Haoliang，Yan Pingkun，et al.Geometry constrained sparse coding for single image super-resolution [C]// Proc of IEEE Computer Vision and Pattern Recognition.Washington,DC: IEEE Computer Society,2012:1648-1655.   
[13] CaoFeilong，CaiMiaomiao，TanYuanpeng，etal. Image super-resolution via adaptive lp $( 0 < \mathrm { p } < 1 )$ regularization and sparse representation [J]. IEEE Trans on Neural Networks and Learning Systems,2016,27(7):1550-1561.   
[14]Mousavi HS,Monga V. Sparsity-based color image super resolution via exploiting cross channel constraints [J].IEEE Trans on Image Processing,2017,26(11): 5094-5106.   
[15] Xie Chao,Zeng Weili,Jiang Shenqin,et al.Bidirectionally aligned sparse representation for single image super-resolution [J]. Multimedia Tools and Applications,2017,77(7): 7889-7907.   
[16] Yang Wenming，Yuan Tingrong，Wang Wei,et al. Single-image super-resolution by subdictionary coding and kernel regression [J]. IEEE Trans on Systems,Man,and Cybernetics Systems,2017,47(9): 2478-2488.   
[17] Zhang Lei,Yang Meng，Feng Xiangchu.Sparse representation or collaborative representation:which helps face recognition?[C]// Proc of IEEE International Conference on Computer Vision.Piscataway,NJ: IEEE Press,2011: 471-478.   
[18]蔡苗苗，谈元鹏，曹飞龙．基于局部结构相似与协同表示的超分辨 率图像重建[J].模式识别与人工智能，2014，27(9):787-793.(Cai Miaomiao，Tan Yuanpeng，Cao Feilong． Super-resolution image reconstruction based on local structural similarity and collaborative representation [J].Pattern Recognition and Artificial Intelligence,2014, 27(9): 787-793.)   
[19] Zhao Jianwei,Hu Heping,Cao Feilong.Image super-resolution via adaptive sparse representation [J].Knowledge-Based Systems,2017, 124: 22-23.   
[20] Wang Shenlong,Zhang Lei,Liang Yan,et al. Semi-coupled dictionary learning with applications to image super-resolution and photo-sketch synthesis [C]//Proc ofIEEE Computer Vision and Pattern Recognition. Washington DC:IEEE Computer Society,2012:2216-2223.   
[21] Yang Junfeng,Yuan Xiaoming.Linearized augmented lagrangian and alternating direction methods for nuclear norm minimization [J]. Mathematics of Computation,2012,82(281):301-329.   
[22] Grave E,Obozinski G,Bach F.Trace lasso:a trace norm regularization for correlated designs [C]// Proc of the 25th Annual Conference on Neural Information Processing Systems.New York:Curran Associates Inc.,2011:2187-2195.   
[23]Wang Jing,Lu Canyi,Wang Meng,et al.Robust face recognition via adaptive sparse representation [J].IEEE Trans on Cybernetics,2014, 44(12): 2368-2378.