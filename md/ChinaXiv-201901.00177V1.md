# NMF和增强奇异值分解的自适应零水印算法

肖振久，宁秋莹，张晗，唐晓亮，陈虹(辽宁工程技术大学 软件学院，辽宁 葫芦岛 125105)

摘要：针对奇异值分解水印算法导致虚警率高、稳健性不强的问题，提出一种基于分块非负矩阵分解(NMF)和增强奇异值分解(BN-SVD)相结合的自适应零水印算法。首先将原始灰度图像进行二级离散小波变换(DWT)，对变换后的二级低频子带(LL2)进行不重叠分块，并对每一个子块进行秩为r的 NMF 分解;然后对 NMF 分解得到的特征矩阵采用增强奇异值分解，依据每一个块矩阵的最大奇异值与整体最大奇异值均值的大小关系构成特征向量;利用生成的特征向量与经过Amold变换与混沌映射双重置乱加密水印图像做异或运算生成零水印,并利用天牛须优化算法(BAS)自适应确定增强奇异值分解中最抗攻击缩放比例的参数β。实验结果表明，在虚警问题上NC值达到0.4以下，JPEG压缩、噪声、滤波、旋转、剪切以及混合攻击下，提取水印图像与原水印图像的归一化系数NC值均可达到 $9 9 \%$ 以上，该方案高效地解决虚警问题，具有较强的稳健性，能够有效地抵抗各种攻击。

关键词：非负矩阵分解；增强奇异值分解；Amold变换；混沌映射；天牛须优化算法 中图分类号：TP309.2 doi:10.19734/j.issn.1001-3695.2018.09.0751

# Adaptive zero-watermarking algorithm based on block NMF and boost normed singular value decomposition

Xiao Zhenjiu, Ning Qiuying, Zhang Han, Tang Xiaoliang, Chen Hong (CollgeofSoftwareLiaoning Technical University,Huludao Liaoning125ooo,China)

Abstract: For the problem of the singular value decomposition (SVD) watermarking algorithm caused high false alarm rate and low robustness,this paper proposed an adaptive zero watermarking algorithm，which was based on block NMF and boost normed singular value decomposition.First,the original gray image was transformed into two levelsof DWT transform,thenafterthe transformationoftheLL2 subbands were divided into non-overlapping blocks,andeach sub-block wasbrokendown intoNMF withrankr,then boost normedsingularvaluedecompositionwas used foreigenmatrix derived from NMF decomposition.According to the relationship betwee the maximum singular value of each block matrix and the mean value of the global maximum singular value,itconstructed feature-vector.Finally the generated feature vector was Xoroperation with therandomencrypted watermark imageofArnold andthe logistic mapto generateazero watermark.The parameter $\beta$ in the singular value matrix must be determined adaptivelyby the optimization algorithm (BAS),and find out the scalingratioof themostresistant attck.The experimentalresults showthat,inthe falsealarm problem,theNCvalue is below 0.4.Under theconditionofJPEGcompression,noise,filtering,rotation,shearingand mixed attack,thenormalized coefficient NC of the extracted watermark image and the original watermark image can reach more than $9 9 \%$ . The method can solve the false positive errors eficiently and has strong robustness.Can resist all kinds of attacks ffctively.

Key words: NMF; boost normed singular value decomposition(bn-svd); Armold; Logistic map; betle antennae search

# 0 引言

近20年来，数据压缩性能的提高和互联网带宽的不断增加，使得数字图像、视频和音频更容易被播放，复制与窜改。越来越多的人想要分享他们赋有创造性的数字作品。因此，所有数字作品的版权保护和所有权申报的都变得非常重要。为了保护数字作品免受盗版，数字水印提供了一种潜在的解决方案。因其在数字版权管理和保护中的重要应用，在很大程度上推动了数字水印研究的不断深入。

数字水印[1,2]是指将信息(水印)潜移默化地嵌入到数字文档中以提供内容保护或内容认证的过程。按照嵌入式算法分类，主要可分为两种：一种是空间域水印算法，一种是变换域水印算法。空间域水印通常是直接修改图像的灰度值来实现效果。变换域水印则是通过修改载体图像频域系数来达到嵌入目的。两者相比，变换域水印更鲁棒。小波域水印大多将水印嵌在中频域。文献[3]提出一种基于小波变换和NMF的数字图像水印算法，原始图像进行二级离散小波变换，选择图像中频区域进行嵌入，对LH2 做NMF分解，将经过Arnold变换后的水印以嵌入强度α嵌在到分解后的特征矩阵中。文献[4]在文献[3]的算法上进行了改进，将宿主图像进行三级小波变换，选择低频近似分量进行嵌入，最后通过量化系数矩阵得到表示原始图像的特征向量，然后通过计算水印和特征向量嵌入版权信息。引入离散小波变换后的算法，水印的不可见性得到提高。对一些图像退化过程和JPEG压缩的鲁棒性有所提升。因单一的小波变化无法使水印获得强鲁棒性，文献[5]提出奇异值分解与小波变换相结合的水印算法。先将图像进行小波变换，对低频部分进行SVD后将水印内容进行嵌入。文献[6]利用DCT与DWT嵌入鲁棒水印和脆弱水印实现双功能水印算法，可以有效抵抗压缩、噪声、局部剪切的攻击。虽然文献[5,6]两中算法均满足水印算法的隐蔽性和鲁棒性，但算法中奇异值分解带来的对角线失真以及虚警率问题没有得到良好的解决。文献[7]提出了一种基于奇异值分解与蜂群优化的鲁棒水印算法，利用蜂群优化算法来选取嵌入强度，自适应的均衡了水印算法的鲁棒性与透明性，但该优化算法收敛速度慢，寻找最优解时间较长。

为从根本上解决水印的透明性与鲁棒性不均衡问题，温泉等人[8提出了零水印算法，利用原始载体图像的内部特征来构造零水印。在保证了原始载体图像完整性同时，又有效地解决了水印算法鲁棒性与透明性的矛盾问题。曲长波等人[9]提出基于Curvelet-DSVD 和视觉密码的强鲁棒零水印。依据视觉密码生成的共享份与双奇异值分解得到的特征矩阵异或生成零水印。该算法在抵抗JPEG压缩、噪声、滤波、剪切方面都表现出较好的鲁棒性，但算法复杂且在抵抗几何攻击方面还存在很大的提升空间。在虚警率问题上实验结果仍不理想。本文借鉴文献[10]的思路提出一种基于分块的NMF和BN-SVD的自适应零水印。对图像进行二级小波变换后的低频区域不重叠分块，借助图像的非负特性利用NMF对不重叠子块分解，得到基数矩阵 $\pmb { W }$ 和特征矩阵 ${ \pmb H }$ ，对特征矩阵进行增强奇异值分解生成特征向量与经过Arnold与混沌映射双重置乱加密水印图像进行异或运算生成零水印。利用天牛须优化算法（BAS）自适应确定增强奇异值分解中最抗攻击缩放比例的参数 $\beta$ 。该算法的优势在于解决奇异值分解水印算法提取时出现的高虚警错误和稳健性不强问题并结合天牛须搜索算法实现自适应过程提升鲁棒性。

# 1 算法理论基础

# 1.1非负矩阵分解

非负矩阵分解 (non-negative matrix factorization,NMF)[1,12]算法是信号处理,计算机视觉和图像工程等研究领域中最受欢迎的多维数据处理工具之一，是一种基于矩阵中多有元素均为非负数约束条件下的矩阵分解方法。算法描述如下：

给定矩阵 $V \in R _ { * } ^ { n \times m }$ ，寻找非负基矩阵 $\pmb { W } \in { \cal R } _ { + } ^ { n \times r }$ 和非负特征矩阵 $\pmb { H } \in R _ { + } ^ { r \times m }$ ，使得 $V \cong W \times H$ ，分解前后可理解为：原始矩阵 $\boldsymbol { V }$ 的列向量是对左矩阵 $W$ 中所有列向量的加权和，而权重系数就是右矩阵 $\textbf {  { H } }$ 对应列向量的元素，故称 $W$ 为基矩阵， $\textbf {  { H } }$ 为系数矩阵或特征矩阵。r为要分解矩阵的秩，一般情况下 $r$ 的选择要比 $n$ 和 $m$ 小，即满足 $( m + n ) r < m n$ ，这时用特征矩阵代替原始矩阵，就可以实现对原始矩阵进行降维，得到数据特征的降维矩阵。NMF矩阵分解实现优化目标过程：最小化原始矩阵 $\boldsymbol { V }$ 和 $W$ 矩阵 $\textbf {  { H } }$ 矩阵的乘积之差。算法的关键是目标函数的设定和迭代的选择。定义如下：

目标函数为

$$
\operatorname* { m i n } \lVert V - W H \rVert ^ { 2 } W , H \geq 0
$$

$$
H _ { r m } \gets H _ { r m } \frac { ( W ^ { T } V ) _ { r m } } { ( W ^ { T } W H ) _ { r m } }
$$

迭代规则为

$$
\mathbf { \boldsymbol { W _ { n r } } }  \mathbf { \boldsymbol { W _ { n r } } } \frac { ( \mathbf { \boldsymbol { V } } \mathbf { \boldsymbol { H } } ^ { T } ) _ { n r } } { ( \mathbf { \boldsymbol { V } } ^ { T } \mathbf { \boldsymbol { V } } \mathbf { \boldsymbol { H } } ) _ { n r } }
$$

NMF与PCA、FA、ICA等常用的信号变换方法不同的是，分解后的所有分量均为非负值并且实现非线性的维数约减。这种非负性的限制导致了相应描述在一定程度上的稀疏性，更能体现智能数据处理的本质，使得对数据的描述变得方便与合理，同时还在一定程度上抑制外界变化对特征提取造成的影响，所以NMF分解算法相较于传统的一些算法而言，具有实现上的简便性、分解形式和分解结果上的可解释性，以及占用存储空间少等诸多优点。

# 1.2 奇异值分解

奇异值分解(SVD)是最著名，最广泛使用的矩阵分解方法。经过奇异值分解后，对应的正交矩阵表示图像的几何结构，奇异矩阵表示图像的亮度信息。因该分解算法拥有强稳定性，被广泛地应用于图像处理领域。设定数字图像矩阵$A \in R ^ { N \times N }$ ， $R$ 为实数域。正交矩阵 ${ \pmb U } \in { \pmb R } ^ { N \times N }$ 、 $V \in R ^ { N \times N }$ 和对角矩阵 $\pmb { S } \in R ^ { N \times N }$ 使得 $A$ 表示为

$$
\pmb { A } { = } \pmb { U } \times \pmb { S } \times \pmb { V } ^ { T }
$$

其中 $\pmb { U }$ 表示左奇异值正交矩阵和 $\mathbf { \Psi } _ { V ^ { T } }$ 表示右奇异值正交矩阵且各自满足 $\pmb { U } \times \pmb { U } ^ { T } = \pmb { l }$ ， $V = V ^ { - 1 }$ 。 $s$ 是一个非对角元素值都为0的矩阵满足 $\lambda _ { i } \left( i = 1 , 2 , . . . , r \right)$ 且 $\lambda _ { I } \ge . . . \ge \lambda _ { i } > 0$ 。 $\boldsymbol { r }$ 为矩阵 $A$ 的秩。于是有

$$
\begin{array} { r } { \mathbf { \boldsymbol { S } } = \left( \begin{array} { l l l } { \lambda _ { I } } & { O } & { O } \\ { O } & { \ddots } & { O } \\ { O } & { O } & { \lambda _ { r } } \end{array} \right) } \end{array}
$$

$\lambda _ { i }$ 是由分解而唯一确定的,记做矩阵 $A$ 的奇异值,分解式$\pmb { U } \times \pmb { S } \times \pmb { V } ^ { T }$ 记做 $A$ 的奇异值分解。

图像在增强奇异值分解后，图像与奇异值向量构成一一对应的关系，不同的图像可以拥有相同的奇异值，但两幅图像结构却没有任何联系，因这一缺点导致经过奇异值向量进行水印信息嵌入时，可能在并无水印信息的图像中提取出水印信息，造成了水印提取阶段的虚警问题。

# 1.3增强奇异值分解

增强奇异值分解（BN-SVD）[13]是基于奇异值分解的理论提出的一种新的分解算法，对奇异值矩阵进行修改引入参数 $\beta$ 。其作用是均衡奇异值矩阵对角线方向上的灰度。设数字图像 $A$ 大小为 $M \times M$ ，对其进行增强奇异值分解，则存在${ \pmb U } _ { \scriptscriptstyle M \times M }$ 、 $\boldsymbol { V } _ { \boldsymbol { M } \times \boldsymbol { M } }$ 的正交矩阵和 $\boldsymbol { S } _ { \boldsymbol { M } \times \boldsymbol { M } }$ 的对角矩阵,公式成立如下：

$$
A = \pmb { U } \times ( \pmb { S } ) ^ { \beta } \times \pmb { V } ^ { T } , 0 < \beta < 1
$$

其中：矩阵 $A$ 的左奇异矩阵是 $\pmb { U }$ ，右奇异矩阵是 $V ^ { T }$ 。

增强奇异值矩分解是将数字图像 $A$ 进行奇异值分解后的对角矩阵 $\boldsymbol { S } _ { N \times N }$ 做 $\beta$ 次幂运算。在处理不同的数字图像时，可以根据图像自身固有的信息对参数进行合理的调整，以达到最佳的抗攻击效果。其增强奇异值分解的优势在于：图像奇异值得到放大，降低了图像矩阵在受到攻击时的敏感性，一定程度上提高了算法的鲁棒性。而且在解决奇异值分解中存在的虚警错误问题上，增强奇异值分解对奇异值向量做特殊化处理后，向量与图像就存在一对一的关系，奇异值可代表图像的特征，这样的处理方式使虚警问题得到更好的解决。

# 1.4自适应天牛须优化算法

天牛须(beetle antennae search，BAS)算法[14]是李帅等人受甲虫搜索行为启发，在2017年提出了一种基于甲虫觅食原理的优化算法。与粒子群，遗传算法相似，无须知道具体的函数形式和梯度信息自主实现寻优过程。因天牛个体单一，省去大量运算同时提升寻优速度。算法的生物理论[15]：天牛是根据食物气味的强弱来寻找食物，它使用两个触角随机地在周边地区进行觅食。依据左右触角接收的气味强度值进行比较，天牛则飞向气味浓度强的一边。依据这一简单原理天牛就可以有效找到食物。

算法原理如下：

a)初始化随机天牛位置气味强度 $\boldsymbol { \cal X }$ 和天牛须朝向的随机向量 $\textbf { \textit { b } }$ 并对此归一化，设置最大迭代次数 $M A X$ 。

$$
{ \vec { b } } = { \frac { \mathrm { r a n d s } ( k , 1 ) } { \left\| \mathrm { r a n d s } ( k , 1 ) \right\| } }
$$

其中：randsO为随机函数； $k$ 表示空间维度。

b）天牛个体两须采集自身附近两点的气味强度 $X _ { n } , ~ X _ { l t }$ 并朝向食物的坐标。

$$
\left\{ \begin{array} { c } { { } } \\ { { X _ { r t } = X ^ { t } + d _ { o } \times { \vec { \pmb { b } } } \displaystyle { \not | 2 } } } \\ { { } } \\ { { X _ { l t } = X ^ { \prime } - d _ { o } \times { \vec { \pmb { b } } } \displaystyle { \not | 2 } } } \end{array} \right.
$$

其中：表示在第 $\mathbf { \Psi } _ { t } \mathbf { \Psi } _ { t }$ 次迭代时，天牛左右须位置坐标为 $X _ { l t } , X _ { r t }$ ：天牛质心坐标 $X ^ { \prime }$ ；两须之间的距离 $d _ { o }$ 0

c)迭代更新天牛位置的气味强度 $X ^ { t + I }$ □

$$
X ^ { t + l } = X ^ { t } - \delta ^ { t } \times { \vec { b } } \times \mathrm { s i g n } ( f ( X _ { n } \mid - f ( X _ { l t } ) ) ( 8
$$

其中： $\delta ^ { t }$ 表示在 $t$ 次迭代时的步长因子；signO为符号函数

d）由于参数 $\beta$ ，取值范围属于[0,1]，即在本实验中气味强度 $\boldsymbol { \cal X }$ 需要进行分段约束。

$$
X = \left\{ \begin{array} { l l } { { l } } & { { X ^ { t + l } > l } } \\ { { O } } & { { X ^ { t + l } < O } } \\ { { X = X ^ { t + l } } } & { { e l s e } } \end{array} \right.
$$

e)天牛个体两须附近两点的气味强度坐标 $( X _ { l t } \ , X _ { r t } \ )$ 利用式(9)确定当前天牛空间位置气味强度和气味强度测定函数$f$ （即适应度函数）来求出天牛个体位置 $f ( X )$ ：

$$
f \left( X \right) = f \left( X ^ { t + l } \right)
$$

f)通过测定函数 $f$ 寻到天牛个体位置两须中最优的气味强度 $\boldsymbol { \cal X }$ □

$$
\left[ f , X \right] = \operatorname* { m a x } \left( X \right)
$$

g)测定天牛位置最强气味强度Xbest并探寻到最优测定函数 $f b e s t$ 奔向该位置。

$$
\left\{ \begin{array} { l l } { f = \operatorname* { m a x } ( f b e s t ) } \\ { X = \operatorname* { m a x } ( X b e s t ) } \end{array} \right.
$$

h)重复执行步骤 $\mathsf { b } ) { \sim } \mathsf { f } )$ ，迭代优化来寻找最优解，在每次迭代结束时，判断气味，如果当前气味强度优于前一次迭代的好则执行g)，当执行最大迭代次数MAX 则结束整个过程，得到最优结果 $\boldsymbol { \cal X }$ 即参数 $\beta$ 。

# 2 数字水印算法实现

# 2.1水印图像的预处理

Arnold变换[15]俗称猫脸映射是一种从规则位置到随即位置的映射，是一种传统的混沌系统。对一副大小为 $M \times M$ 的图像，Arnold置乱定义如下：

$$
{ \begin{array} { r l } { [ { \begin{array} { l } { x ^ { \prime } } \\ { y ^ { \prime } } \end{array} } ] } & { = { \begin{array} { r l } { [ 1 } & { 1 } \\ { 1 } & { 2 } \end{array} } [ { \begin{array} { l } { x } \\ { y } \end{array} } ] ( { \bmod { \ N } } ) } \\ & { x , y \in \{ 0 , 1 , \cdots , N - 1 \} } \end{array} }
$$

其中前后像素点的位置分别由 $\displaystyle ( x , y )$ 和 $( x ^ { \prime } , y ^ { \prime } )$ 表示。 $x , y , N$ 为正整数， $N$ 代表图像矩阵的阶数， $\mod$ 为取余运算。其变换的实质是改变像素位置，来减弱相邻像素之间的关联性，提高了图像安全性。拥有周期性，经过有限次的迭代便可恢复出原始图像。

Logistic 映射[16]具有遍历性高、伪随机性强对初值高敏感型等优点。其定义如下：

$$
x _ { i + I } = \mu x _ { i } ( I - x _ { i } \ ) \ x _ { i } \in ( O , I ) \ \mu \in [ O , 4 ]
$$

其中： $\mu$ 为Logistic 混沌系统的控制参数, $x _ { i }$ 为映射的混沌序列。当 $x _ { i } \in ( 0 , 1 )$ 时，Logistic映射工作处于混沌状态，也就是说，有初始条件 $\mathbf { x _ { 0 } }$ 在Logistic 映射作用下产生的序列是非周期性的，不收敛的，而在此范围之外，生成的序列必将收敛于某一个特定的值，当 $3 . 5 6 9 4 5 6 < \mu < 4$ 时，特别是比较靠近4时，迭代生成的值是处于一种伪随机分布状态即混沌状态，而在取其他值时，在经过一定次数的迭代之后，生成的值将收敛到一特定的数值。

# 2.2零水印构造

本文采用离散小波变换算法作基底，对原图像进行二级离散小波变化。因原始图像能量高度集中于图中位于低频频段的LL2区域，而细节信息则主要分布于高频频段。由于低频系数稳定性高，所以选择在其中嵌入水印信息，保证水印的强鲁棒性且抗攻击能力得到大大提升。

![](images/90cc2af6b06d56c768b1ea48bc8b8084a573a704a6ed4deb94ff676d2edb8d42.jpg)  
图1零水印构建图  
Fig.1Zero watermark construction diagram

a)大小 $\mathbf { M } \times \mathbf { M }$ 原始灰度图像 $I$ 进行2级DWT；对2级DWT 变换后的得到的低频逼近子带LL2 进行 $\scriptstyle n \times n$ 分块，生成不重叠子块 $A _ { i } \bigg ( i = 1 , 2 , \cdots , \frac { M \times M } { 4 \times n \times n } \bigg )$ 并对 $A _ { i }$ 进行秩 $\boldsymbol { r }$ 的NMF分解，且 $r \leq n$ ，即

$$
\pmb { A } _ { i } \approx \pmb { W } _ { i } \pmb { H } _ { i }
$$

其中： $\boldsymbol { W } _ { i }$ 和 $\pmb { H } _ { i }$ 分别是 $m \times r$ 和 $r \times n$ 的非负矩阵

b)对特征矩阵 $\pmb { H } _ { i }$ 进行增强奇异值分解，即

$$
{ \pmb { H } } _ { i } = { \pmb { U } } _ { i } \times ( { \pmb { S } } _ { i } ) ^ { \beta } { \pmb { V } } _ { i } ^ { T } ~ ( 0 < \beta < 1 )
$$

其中： $U _ { i } , V _ { i }$ 为正交矩阵； $\boldsymbol { S } _ { i }$ 为对角矩阵。其参数 $\beta$ 用上述1.4天牛须搜索找到最优。

c)取对角矩阵 $\boldsymbol { S } _ { i }$ 中第一个奇异值共有 $( M / 2 n ) { \times } ( M / 2 n )$ 个， 记作 $\eta _ { i } \left( i = 1 , 2 , \cdots , ( M / 2 n ) \times ( M / 2 n ) \right)$

d)计算 $( M / 2 n ) { \times } ( M / 2 n )$ 个最大奇异值的平均值 $m e a n ( \eta _ { i } )$ 。依据 $\eta _ { i }$ 和 $m e a n ( \eta _ { i } )$ 的大小关系构成一个特征向量 $F$ 。

$$
F _ { i } = \left\{ { \begin{array} { l l } { I } & { \eta _ { i } \rangle m e a n ( \eta _ { i } ) } \\ { O } & { o t h e r w i s e } \end{array} } \right.
$$

e)将原始二值水印图像 $W$ 作 $K _ { I }$ 次 Arnold 置乱，得到置乱后水印图像 $\pmb { W } _ { I }$ 。然后对水印图像 $\pmb { W } _ { I }$ 进行Logistic 映射，经过二次加密后水印图像 $\pmb { W } _ { 2 }$ 和密钥 $K _ { 2 }$ □

f)将特征向量 $_ F$ 与置乱后的水印图像 $\pmb { W } _ { 2 }$ 进行异或运算，生成零水印图像 $\textbf { \em M }$ ：

$$
\pmb { M } = \mathrm { X O R } \left( \pmb { F } , \pmb { W } _ { 2 } \right)
$$

# 2.3 零水印检测

水印的检测即为水印构造的逆过程,如图2所示。

![](images/3940a6a8a7aba2d51141924384f00932517d60b689034ee94ed167d48200b8e5.jpg)  
图2零水印检测图

选取原始灰度图像 $I ^ { \prime }$ ，大小为 $M \times M$ 。零水印检测步骤如下：

a)对原始灰度图像 $I ^ { \prime }$ 进行2级DWT，对得到的低频逼近子带LL2进行 $\scriptstyle n \times n$ 分块,生成不重叠子块， $A _ { i } ^ { \prime } \biggl ( i = 1 , 2 , \cdots , \frac { M \times M } { 4 \times n \times n } \biggr )$ 并对 $\mathbf { A } _ { i } ^ { \prime }$ 进行秩 $\boldsymbol { r }$ 的NMF分解，且 $r \leq n$ ,即

$$
\mathbf { A } _ { i } ^ { \prime } \approx \mathbf { W } _ { i } ^ { \prime } \mathbf { H } _ { i } ^ { \prime }
$$

b)对特征矩阵 $\pmb { H } _ { i } ^ { \prime }$ 进行增强奇异值分解(BN-SVD)，得到对角矩阵 $\boldsymbol { S } _ { i } ^ { \prime }$ 。

c)取对角矩阵 ${ \bf \nabla } _ { S _ { i } ^ { ' } }$ 中第一个奇异值共 $( M / 2 n ) { \times } ( M / 2 n )$ 个记作： $\eta _ { i } ^ { \prime } \left( i = 1 , 2 , \cdots , ( M / 2 n ) \times \left( M / 2 n \right) \right)$ 。

d)求取平均值 $\mathrm { m e a n } ( \eta _ { i } ^ { \prime } )$ 。根据 $\eta _ { i } ^ { ' }$ 和 $\mathrm { m e a n } ( \eta _ { i } ^ { \cdot } )$ 的大小关系得到特征向量 $\boldsymbol { F }$ 。

e)将零水印图像 $\textbf { \em M }$ 与 4)中得到的特征向量 $F ^ { \prime }$ 进行异或运算，得到加密之乱后的水印图像 ${ \pmb W } _ { 2 }$ 。

$$
{ \pmb W } _ { 2 } = { \bf X } { \bf O } { \bf R } \left( { \pmb M } , { \pmb F } ^ { \prime } \right)
$$

f)最后对水印图像 $\pmb { W } _ { 2 }$ 进行逆Logistic映射和 $K _ { \iota }$ 次Arnold逆置乱得到原始水印图像 $W$ 。

# 3 仿真实验结果与分析

本实验主要在matlab2016a 实验平台下仿真，实验中选取图3(a)\~(c)Lena,Baboon,Plane 大小均为 $5 1 2 \times 5 1 2$ 像素的标准灰度图像作为测试图像，水印图像选取图(d)大小为 $3 2 \times 3 2$ 像素的二值图像“辽宁工大”。设置天牛须优化迭代次数为20。通常水印算法的评价指标是不可见行和鲁棒性，但在本文中，对于零水印算法，水印信息没有嵌入到载体图像中，即需要鲁棒性作为评价指标。仿真实验采用归一化相关(NC)函数来评价提取的水印与原水印的相似度，即

$$
N C ( x I , x 2 ) = \frac { \displaystyle \sum _ { i = I } ^ { M } \sum _ { j = I } ^ { N } x _ { I } ( i , j ) x _ { 2 } ( i , j ) } { \sqrt { \displaystyle \sum _ { i = I } ^ { M } \sum _ { j = I } ^ { N } x { I } ( i , j ) ^ { 2 } } \sqrt { \displaystyle \sum _ { i = I } ^ { M } \sum _ { j = I } ^ { N } x _ { 2 } ( i , j ) ^ { 2 } } }
$$

其中： $x I$ 表示为初始水印， $x 2$ 表示为提取的水印

# 3.1鲁棒性实验

为验证本文水印算法具有较好的鲁棒性，本文采用NC作为算法鲁棒性的评价标准。针对 $3 2 \times 3 2$ 大小的水印图像，本实验利用天牛须优化算法在第16次实验中得到Lena、Baboon 和Plane 三幅灰色图像的最优参数 $\beta$ 值为0.4289,

0.5070，0.1382，达到强鲁棒性效果。分别对三幅灰色图像进行了几何攻击和非几何攻击，图4为部分表1中Lean图像受到不同类型攻击后的实验效果图，表1列出了待测图像在受到各种不同攻击后提取出 $3 2 \times 3 2$ 大小水印图像的NC值，从表中数据可以得出，本算法可以有效抵抗各种攻击，NC值的平均值高于0.9984，随着攻击强度的增加和混合攻击，水印的NC值受到一定的影响。其中，当旋转攻击强度为10度时，提取出的水印的NC值最低为0.9988。由此可见本文算法可以有效抵抗旋转攻击。对于剪切攻击，剪切面积增大提取出的水印NC值在0.9984以上；噪声、滤波、缩放、压缩和混合攻击在强度增加时，提取出的水印NC值都接近于1。

![](images/685a316d5469472d3ee3abc22b7fd11ba2f7a84ed19899d08782491a5d66c19e.jpg)  
Fig.2Zero watermark detection diagram   
图3原始灰度图像与水印图像  
Fig.3Original grayscale image and watermark image

分析以上的结果可得，通过NMF和BN-SVD结合的算法，并利用天牛须优化算法智能搜索最佳的参数 $\beta$ ，增强了该水印算法的鲁棒性。

表1待测图像攻击后提取出 $3 2 \times 3 2$ 水印的NC值

Table1 Extracting the NC value of the $3 2 \times 3 2$ watermark after attacking the image to be detected   

<html><body><table><tr><td>攻击</td><td>强度</td><td>Lena</td><td>Baboon</td><td>Plane</td></tr><tr><td rowspan="2">高斯噪声</td><td>0.01</td><td>0.9999</td><td>0.9998</td><td>1.0000</td></tr><tr><td>0.02</td><td>0.9999</td><td>0.9999</td><td>1.0000</td></tr><tr><td rowspan="2">中值滤波</td><td>3×3</td><td>1.0000</td><td>0.9999</td><td>1.0000</td></tr><tr><td>5×5</td><td>0.9999</td><td>0.9999</td><td>1.0000</td></tr><tr><td>高斯滤波</td><td>0.5</td><td>1.0000</td><td>0.9999</td><td>1.0000</td></tr><tr><td rowspan="2">压缩攻击</td><td>20</td><td>1.0000</td><td>1.0000</td><td>1.0000</td></tr><tr><td>10</td><td>1.0000</td><td>0.9999</td><td>1.0000</td></tr><tr><td>缩放</td><td>0.5</td><td>1.0000</td><td>0.9999</td><td>1.0000</td></tr><tr><td>混合</td><td>高斯滤波加中 心剪切1/4</td><td>0.9988</td><td>0.9990</td><td>0.9990</td></tr><tr><td rowspan="2">剪切攻击</td><td>左上角1/16</td><td>1.0000</td><td>0.9999</td><td>1.0000</td></tr><tr><td>左上角1/4</td><td>0.9990</td><td>0.9984</td><td>0.9992</td></tr><tr><td rowspan="2">椒盐噪声</td><td>0.01</td><td>1.0000</td><td>0.9999</td><td>1.0000</td></tr><tr><td>0.02</td><td>1.0000</td><td>0.9999</td><td>1.0000</td></tr><tr><td rowspan="2">旋转攻击</td><td>向左10°</td><td>0.9988</td><td>0.9990</td><td>0.9990</td></tr><tr><td>向右10°</td><td>0.9987</td><td>0.9990</td><td>0.9990</td></tr></table></body></html>

# 3.2 安全性分析

在整个算法中，安全性是不容忽视的。本文算法对水印图像进行Arnold变换和Logistic 映射,实现水印图像特征的二次加密，加密密匙分别为 $K _ { \mathrm { l } }$ ， $K _ { 2 }$ ，这样即使零水印信息泄露，在不确定密匙的情况下，是无法恢复出水印信息的，说明本算法的安全性较高。

![](images/58dfa24960747ec817c8f8198d918039448d0724d53cbc1306c84114f40fa506.jpg)  
图4受攻击后的实验图像

![](images/af92e1350d6db3fc065d647b17c12a811ec21125cfb661ef8736992ec6b204eb.jpg)  
Fig.4Attacked experimental images   
图5不同密钥提取的错误水印信息  
Fig.5Falsewatermark information extracted fromdifferent keys由图5可知在密匙错误的情况下提取出的水印情况，图

5中，(a)为在密匙 $K _ { \iota }$ 正确 $K _ { 2 }$ 错误的情况下提取出的水印信息；(b)为在密匙 $K _ { 2 }$ 正确 $K _ { \iota }$ 错误的情况下提取出的水印信息；(c)为在密匙 $K _ { 1 } \ K _ { 2 }$ 都错误的情况下提取出的水印信息。从图5中可以得到，在密匙错误的情况下是无法提取出水印信息，因此可以表明本文算法的安全性较高。

# 3.3虚警率问题实验测试

为了验证本文是否能够真实有效的解决SVD的虚警错误问题，将本文算法与文献[17]和传统SVD算法进行对比实验，图6中，(a)为原始灰度图像， (b)为伪造的水印图像，(c)为本文算法提取出的水印。实验表明，本算法引入参数 $\beta$ 后，便存在图像与奇异值向量一一对应的关系，在不确定参数 $\beta$ 值的情况下不能正确的提取出水印信息。

![](images/5ff92403b25aecbe4ad5df0f7da09d792eb41cc689fb36d8de7ed7dd1d3c47d5.jpg)  
图6虚警错误仿真实验结果  
Fig.6Simulation results of false positive errors

表2中三种算法都采用离散小波低频分块，区别在于对矩阵使用了不同的分解方法。其中文献[17]提出了Schur 算法。由表2可知实验后Schur算法与本文算法提取的水印图像与原始水印图像的NC值都在0.5以下，SVD算法虚警问题明显居高，但本文算法NC值在0.4以下，说明本文算法处理虚警问题能力强。

表2本文算法与文献[17]NC值对比  
Table 2The NC value of the algorithm is compared with the literature   

<html><body><table><tr><td colspan="4">[17]</td></tr><tr><td>图像</td><td>SVD 算法</td><td>文献[17]</td><td>本文算法</td></tr><tr><td>Lena</td><td>0.9963</td><td>0.4999</td><td>0.3558</td></tr><tr><td>Bridge</td><td>0.9896</td><td>0.4875</td><td>0.3146</td></tr><tr><td>Plane</td><td>0.9942</td><td>0.4968</td><td>0.3348</td></tr></table></body></html>

# 3.4本文算法与文献[10,18,19]的对比实验

为了进一步验证本算法的优势，本算法对DWT后的二级低频区域分块利用NMF算法分解后得到的特征矩阵，并对特征矩阵进行增强奇异值分解，通过分解后均衡化对角线方向上的灰度，使水印拥有强鲁棒性，利用天牛须优化算法自适应确定参数 $\beta$ ，使水印的鲁棒性达到最佳。本文选取Lena图像作为原始灰度图像，与文献[10,18,19]算法得到的实验结果进行了对比；文献[10]采用的是离散小波低频分块后作离散余弦变换再通过增强奇异值分解构成特征向量，并通过细胞神经网络确定可逆逻辑运算构成零水印；文献[18]是在时域上使用非均匀NURP构造特征矩阵，并通过SURF来对图像进行几何校正；文献[19]对像素近似无损的安全区域进行二级冗余离散小波变换的低频区域分块，再SVD分解构造特征矩阵；而本文算法采用的是二级离散小波低频分块后使用NMF分解，提取出特征矩阵对其进行增强奇异值分解，并利用天牛须优化算法智能搜寻最优参数 $\beta$ ，因此本文算法具有强鲁棒性。不同文献方法下实验结果对比见表3。

表3本文算法与文献[10,18,19]的NC值对比  
Table 3Comparison of NC values between this algorithm and   

<html><body><table><tr><td colspan="5">reference [10,18,19]</td></tr><tr><td>攻击</td><td>强度</td><td>文献[10]</td><td>文献[18]</td><td>文献[19]</td><td>本文算法</td></tr><tr><td rowspan="2">旋转攻击</td><td>向左1°</td><td>0.9860</td><td>-</td><td>-</td><td>0.9998</td></tr><tr><td>向右1°</td><td>0.9861</td><td>-</td><td>-</td><td>0.9998</td></tr><tr><td>剪切攻击</td><td>左上角 1/16</td><td>1.0000</td><td>0.9942</td><td>-</td><td>1.0000</td></tr><tr><td rowspan="5">椒盐噪声</td><td>左上角1/4</td><td>0.9987</td><td>0.9377</td><td>0.8488</td><td>0.9990</td></tr><tr><td>0.01</td><td>1.0000</td><td>-</td><td>0.9968</td><td>1.0000</td></tr><tr><td>0.02</td><td>0.9875</td><td></td><td>0.9923</td><td>1.0000</td></tr><tr><td>0.05</td><td>-</td><td>0.9724</td><td>-</td><td>0.9999</td></tr><tr><td>0.1</td><td></td><td>0.9621</td><td>-</td><td>0.9999</td></tr><tr><td rowspan="7">高斯噪声</td><td>0.001</td><td>1.0000</td><td>-</td><td></td><td>1.0000</td></tr><tr><td>0.002</td><td>0.9987</td><td>-</td><td></td><td>1.0000</td></tr><tr><td>0.01</td><td></td><td>-</td><td>0.9911</td><td>0.9999</td></tr><tr><td>0.02</td><td></td><td>-</td><td>0.9852</td><td>0.9999</td></tr><tr><td>0.05</td><td></td><td>0.9010</td><td>-</td><td>0.9999</td></tr><tr><td>0.1</td><td></td><td>0.8521</td><td>-</td><td>0.9999</td></tr><tr><td>0.5</td><td></td><td>0.7854</td><td>-</td><td>0.9997</td></tr><tr><td rowspan="3">中值滤波</td><td>3×3</td><td>1.0000</td><td>0.9365</td><td>0.9968</td><td>1.0000</td></tr><tr><td>5×5</td><td>0.9962</td><td>-</td><td>0.9929</td><td>0.9999</td></tr><tr><td>10</td><td>0.9962</td><td>0.8681</td><td>0.9858</td><td>1.0000</td></tr><tr><td rowspan="2">压缩攻击</td><td>20</td><td>0.9987</td><td>-</td><td>0.9936</td><td>1.0000</td></tr><tr><td>70</td><td></td><td>0.9827</td><td>-</td><td>0.9999</td></tr><tr><td rowspan="3">缩放</td><td>0.5</td><td></td><td></td><td>0.9981</td><td>1.0000</td></tr><tr><td></td><td>-</td><td>-</td><td></td><td></td></tr><tr><td>1.5</td><td>-</td><td>-</td><td>1.0000</td><td>0.9999</td></tr></table></body></html>

从表3中数据可分析，本文算法抵抗旋转攻击的鲁棒性要明显优于文献[10]，本文抵抗旋转攻击的平均NC值都达到了0.9998；本文算法在抵抗剪切攻击上，随着剪切面积增加抗攻击能力随之下降，但都要优于文献[10,18,19]，提出水印 NC 值最大为1，最小为0.9999;在噪声、滤波攻击方面本文算法要显著优于文献[10,18,19]，其NC值都接近于1。从受到不同程度JEPG压缩攻击后提取出的水印来看，本文算法在压缩强度达到70时，抗攻击能力有所下降，但明显优于文献[10，18,19]在缩放攻击方面，随着缩放强度增加本文的抵抗能力较文献[19]下降。通过上述分析，本文算法在缩放攻击上抵抗能力不如文献[19],在其他攻击方面都表现出了强鲁棒性的特点。

# 4 结束语

本文分析了传统 SVD分解水印算法中，对于提取出的水印存在虚警错误和鲁棒性不强的问题，提出了一种基于分块NMF和增强奇异值分解相结合的自适应零水印算法。利用Arnold变换和Logistic映射对水印进行双重加密，得到的加密图像更加安全，提高了水印的安全性；采用NMF分解具有一定的线性无关性和稀疏性，可以很好地表达图像数据的特征和结构，结合增强奇异值分解并利用天牛须优化算法自适应确定最优参数 $\beta$ ，有效的解决了虚警错误和鲁棒性不强

的问题；此外在原始灰度图像受到几何攻击与非几何攻击下所提取出的水印NC值均可达到 $98 \%$ 以上，增强了算法的鲁棒性。然而本文算法在压缩攻击和缩放攻击方面仍需进一步探索。

参考文献：   
[1] Zheng Qiumei, Zhang Mengmeng. Research on several algorithms of digital image watermarking [J]. Automation $\&$ Instrumentation, 2017, 38 (9): 38-39.   
[2]叶天语.DWT-SVD 域全盲自嵌入鲁棒量化水印算法[J]．中国图象 图形学报，2012，17(6):644-650.(Ye Tianyu.Perfectly blind self-embedding robust quantization-based watermarking scheme in DWT-SVD domain [J]. Jourmal of Image and Graphics,2012,17 (6): 644-650)   
[3]Li Jing,Fu Bo,LiLi,et al. Digital Image Watermarking Algorithm Based on Wavelet Transform and the NMF [C]//Proc of the 3rd International Conference on Intelligent Human-Machine Systems and Cybernetics,Piscataway,NJ: IEEE Press,2011:27-30.   
[4] Gong Yunfeng,Cui Delong,Yu Gulian,et al.An improved image watermarking algorithm based on NMF and DWT [C]// Procof International Conference on Information and Network Security.[S.l.]: IET Press,2014: 6-11.   
[5] 熊祥光，王力．一种改进的 DWT-SVD 域参考水印方案[J].计算机 工程与应用，2014，50（7):75-79.(Xiong Xiangguang，Wang Li. Impored reference watermarking scheme in DWT-SVD domain. [J]. Computer Engineering and Applications, 2014,50 (7): 75-79)   
[6] 张利，吕建平，杨龙．基于 DCT 和 DWT 变换域的双功能水印方法 [J]．西安邮电大学学报,2013,18(1):50-53.(Zhang Li,LuJianping, Yang Long.Dual watermarking method based on DCT and DWT transform domain [J].Journal of Xi'an University of Postsand Telecommunications,2013,18 (1): 50-53)   
[7] 杨俊成，李淑霞，李亮．基于奇异值分解与蜂群优化的鲁棒图像水 印算法[J].控制工程,2017,24(9):1935-1941.(Yang Juncheng,Li Shuxia,Li liang. Singular value decomposition and bee colony optimization based robust image watermark algorithm [J]. Control Engineering of China,2017,24 (9):1935-1941)   
[8]温泉，孙锋，王树勋．零水印的概念与应用[J]．电子学报，2003, 31 (2): 214-216. (Wen Quan, Sun Tanfeng,Wang Shuxun. Concept and application of zero-watermark [J].Acta Electronica Sinica,20o3,31 (2): 214-216)   
[9]曲长波，吴德阳．基于Curvelet-DSVD 和视觉密码的强鲁棒零水印 算法[J/OL].计算机应用研究,2019,,36 (3).[2018-11-15].http://kns. cnki.net/kcms/detail/51.196.TP.20180209.115.064.html.（Qu Changbo，Wu Deyang. Strong robust zero watermarking algorithm based on Curvelet-DSVD and visual cryptography [J/OL].Application Research of Computer,2019,36 (3).[2018-11-15]. htp://kns.cnki. net/kcms/detail/51.1196.TP.20180209.1115.064.html.)   
[10]肖振久，张晗，陈虹等．增强奇异值分解和细胞神经网络的零水印 [J]．中国图象图形学报，2017,22(3):0288-0296.(Xiao Zhenjiu, Zhang Han,Chen Hong,et al.Zero-watermarking based on boost normed singular value decomposition and cellular neural network [J]. Journal of Image and Graphics,2017,22 (3): 0288-0296.)   
[11]汪鹏．非负矩阵分解：数学的奇妙力量[J].计算机教育，2004,10 (20):38-40 (Wang Peng. Non-negative Matrix decomposition: the Wonderful Power of Mathematics[J] Computer Education,2004，10 (20): 38-40)   
[12] Chen Zigang,Li Lixiang,Peng Haipeng,et al.A Novel Digital Watermarking Based on General Non-Negative Matrix Factorization [J]. IEEE Trans on Multimedia,2018,20 (8):1973-1986.   
[13] Rao Y R,Nagabhooshanam E.A novel image zero-watermarking schemebased on DWT-BN-SVD[Cl//Procof International Conference on Information Communication and Embedded Systems. Piscataway,NJ:IEEEPress,2014:1-6.   
[14] Zhu Zongyao,Zhang Zhiyu,Man Weishi,et al.A new beetle antennae search algorithm for multi-objective energy management in microgrid. [C]//Proc of the 13th IEEE Conference on Industrial Electronics and Applications.Piscataway,NJ:IEEE Press,2018:1599-1603.   
[15]Preet C,AggarwalRK.Multiple image watermarking using LWT,DCT and arnold transformation [C]//Proc of International Conference on Trends in Electronics and Informatics .Piscataway,NJ: IEEE Press,2017: 158-162.   
[16] Dhoka M Sl,Patki A.Robust and dynamic image zero watermarking using hessian laplace detector and logistic map [C]//Proc of IEEE International Advance Computing Conference.Piscataway,NJ:IEEE Press,2015:930-935.   
[17]刘万军，孙思宇，曲海成．Schur 分解的快速零水印算法[J/OL]．计 算机科学与探索[EB/OL]．[2018-11-15]．http://kns.cnki. net/kcms/detail/11.5602.TP.20180628.1557.008.html.(Liu Wanjun, Sun Siyu,Qu Haicheng,et al.Fast zero-watermarking algorithm based on Schur decomposition [EB/OL].Journal of Frontiers of Computer Science&Technology.[2018-11-15].htp://kns. cnki. net/kcms/detail/11.5602.TP.20180628.1557.008.html.)   
[18] Shen Zhangle,Kintak U.A novel image zero-watermarking scheme based on non-uniform rectangular[C]//Proc of International Conference on Wavelet Analysis and Pattern Recognition.Piscataway,NJ:IEEE Press,2017: 78-82.   
[19]刘万军，孙思宇，曲海成,等．一种抗几何旋转攻击零水印算法 [J/OL].计算机应用研究,2019,36（10)．[2018-11-15].http://www. arocmag.com/article/02-2019-10-021.html.(Liu Wanjun, Sun Siyu, Qu Haicheng，et al. Anti-geometric rotation attack zero watermarking algorithm [J/OL].Application Research of Computer,2019,36(10）. [2018-11-15].http://www.arocmag.com/article/02-2019-10-021. html.)