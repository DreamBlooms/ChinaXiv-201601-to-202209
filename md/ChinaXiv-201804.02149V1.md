# 基于DWT最优多子图和SIFT几何校正的鲁棒水印算法

李莹莹1，张毅锋1,2,3，程旭1，孙一博1

(1．东南大学 信息科学与工程学院，南京 210096;2.东南大学 南京通信技术研究院，南京 21100;3．南京大学 计算机软件新技术国家重点实验室，南京 210023)

摘要：为提高水印系统鲁棒性，提出一种基于PSO算法优化的DWT多子图水印算法。算法选择 DWT变换后的多个子图作DCT变换，然后利用PSO算法寻找最优的多子图组合权重，利用扩展变换QIM原理嵌入和提取水印。为提高算法抵抗几何攻击的性能，提出基于改进 SIFT 的水印图像抗几何攻击方法，采用一种基于圆的特征点描述方法改进 SIFT，然后在水印提取前通过SIFT特征点匹配进行几何校正预处理。实验仿真结果表明，在保证水印不可察觉的基础上，基于PSO算法优化的DWT多子图水印算法的鲁棒性优于基于DWT单一子图的水印算法；加入改进 SIFT算法的水印系统抵抗几何攻击的能力明显提高。

关键词：DWT-DCT数字水印；扩展变换QIM；粒子群优化算法；尺度不变特征变换 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2018.01.0042

# Robust watermarking algorithm based on DWT optimal multi-subgraph and SIFT geometric correction

Li Yingying1, Zhang Yifeng1,2,3, Cheng $\mathrm { X u ^ { 1 } }$ , Sun Yibo1 (1.SchoolofInformationScience&Engineering,Southeast University，Nanjing1096,China;2.Nanjing Instituteof Communications Technology，SoutheastUniversity,Nanjing211oo,China;3.State KeyLaboratoryforNovel Software Technology,Nanjing University,Nanjing 210023, China)

Abstract: Inorder to improve the robustnessof watermarking system,this paper proposed a DWT multi-subgraph based watermarking algorithm with PSO algorithm.The algorithm selected multiple subgraphs after DWTtransform for DCT transform,thenused PSOalgorithm tofindtheoptimal combination weights of multiple subgraphs.The algorithm embedded and extracted the watermark byusing the spread transform QIM principle.To improve the performance of watermarking algorithm inresistingthe geometric atacks,this paper proposed ananti-geometric attck method based on improved SIFT.It adopted a round based feature point description method to improve the SIFT algorithm.Before watermark extraction,it performed geometric correction processing by SIFT feature point matching.Experimental results show,based on the imperceptibilityof watermark,the robustness ofDWT multi-subgraph based watermarking algorithm with PSO algorithmis better than watermarking algorithm based onDWT single-subgraph. Watermarking system with improved SIFT algorithm can significantly improve the resistance to geometric attacks.

Key words: DWT-DCTdigital watermarking; spread transform QIM; particle swarm optimization(PSO); scale invariant feature transform (SIFT)

# 0 引言

速发展，其为数字产权保护提供了一种安全有效的技术手段，并且被广泛应用于数字媒体领域。

21世纪以来，图像、文本等作品的数字化使用与传播越来越普及，这在给人们生活带来便利的同时也带来了隐患一电子盗版越来越猖獗。数字水印技术在此背景下应运而生并得以迅

根据目前国内外相关研究结果，数字水印主要分为变换域数字水印和空(时)域数字水印两大类。基于空间域的水印算法直接将水印信息嵌入到载体图像的像素信息中；变换域算法则是先将图像变换到相应的变换域，再在变换域中进行水印信息的嵌入。基于变换域的数字水印技术又分为离散傅里叶变换(DFT)、离散余弦变换(DCT)和离散小波变换(DWT)。小波变换是一种时频的局域变换，可以使得信号分析在不同尺度上进行。一幅图像在经过一级小波变换后，会得到四幅子图像(图1)，分别为低频子图LL和高频子图HH、LH、HL。低频子图中保存了原始图像的大部分基本特征，多级小波分解后得到的最高层的低频子图会汇集图像的绝大部分重要信息，它是对图像的主体特征的描绘，因此这部分也被称为逼近子图，人眼视觉对它相对的会更加敏感；其他三个高频子图保存了图像的一些细节信息，是对图像边缘信息的描绘，人眼对这部分的敏感度略低，但是因为其包含图像的边缘信息，高频部分发生的细小改动又容易影响到图像的视觉效果[1,2]。离散余弦变换(DCT)是一种实数正交变换，能用来进行去相关和能量压缩操作，它是对语音和图形信号的一种准最佳变换。基于DCT的数字水印算法计算简单且易于实现，其易于将水印信号分布至时域的所有像素，并且易与人眼视觉模型相结合，兼容于国际数据压缩标准，被研究界普遍关注[I]。结合DCT变换的解相关与能量集中性能和DWT 变换的时频与多分辨率分析特性，Cheng 等人[3]提出在DWT-DCT的混合域中嵌入水印，并用logistics序列进行水印加密提高系统的安全性。Saini等人[4]对DWT-DCT，包括SVD分解的各种组合域水印嵌入算法进行攻击检测仿真分析。Singh等人[5提出另一种DWT-SVD与DCT相结合的水印算法，对载体图像DWT变换后的水平和垂直分量作SVD分解，水印图像作DCT变换后利用猫映射置乱加密，然后将加密水印嵌入载体的DWT-SVD变换系数中，提高水印系统的鲁棒性与安全性。

本文综合DWT和DCT变换的特点，以扩展变换QIM为基础算法，研究基于DWT和DCT联合变换的鲁棒性数字水印技术。与通常的DWT或DWT-DCT混合域水印算法利用某个或某两个DWT子图嵌入水印的方法不同，本文在研究比较基于DWT不同子图的水印算法的性能后，还提出基于DWT多子图的水印算法。选择DWT变换后的多个子图作DCT变换，通过一定的权重系数将其组合起来用于水印嵌入。为寻找较优的多子图组合方法，引入了粒子群优化算法(PSO)[]，设置合理的优化函数，通过粒子群优化算法的迭代运算来寻找多子图的最优组合。

针对水印的攻击，常见的有两种：一是常规信号处理攻击，即噪声攻击、滤波攻击、压缩攻击等；二是几何攻击，如旋转、剪切、尺度缩放等处理。实验仿真表明提出的基于粒子群优化的DWT多子图水印算法在抵抗常规信号攻击时表现出了较好的鲁棒性，但在抵抗几何攻击上存在不足，因此本文又提出加入几何校正算法对受攻击载体进行预处理。Lowe7提出的SIFT算法是计算机视觉中一种经典的匹配算法，具有比例尺度和旋转不变性等特点，进行图像匹配的可靠性非常高，但该算法在性能方面，如计算时间复杂度、匹配速度等还需进一步提升。

本文中提出基于改进SIFT的水印图像抗几何攻击算法，将SIFT算法中基于矩形域或圆环的特征描述方法[7,8]改进为基于圆的特征描述方法，在保证算法几何校正准确性的基础上大大节省运行时间，然后将其用于水印算法中来提高算法的抗几何攻击能力。

# 1 DWT-DCT联合变换水印算法基础

本文算法在仿真过程中使用的载体图像为 $M ^ { * } N$ 的灰度图像，水印为 $m ^ { * } n$ 的二值图像 $( M { \geq } 8 m , N { \geq } 8 n )$ 。基于量化索引调制(QIM)的水印算法具有较好的鲁棒性，其嵌入信息量大而且可实现盲检测；基于扩展变换的量化索引调制(ST-QIM)算法将扩频思想用于QIM算法，不仅具有QIM算法特点，还可将原本集中于单一系数上的失真进行扩展，具有更好的安全性和鲁棒性。Li和Jiang 等人[10,11]对算法中的量化步长、投影向量和嵌入点选择等问题进行了详细的研究。本文算法将利用基于扩展变换的量化索引调制算法(ST-QIM)实现水印嵌入。为便于下文描述，将基于DWT单一子图的DWT-DCT联合变换水印算法记为 STQIM-DWCT-single。

STQIM-DWCT-single算法结合DCT变换与DWT变换来嵌入水印。首先将载体图像进行二级小波分解（图1），取二层中单一子图用于水印嵌入；然后将该区域进行 $\frac { M } { 4 m } { \times } \frac { N } { 4 n }$ 的分块并作DCT变换。

![](images/4c5046a52c42b5f6d06ae588046d281274ad39c16a55f5bc9c6a763df38f9cee.jpg)  
图1小波分解图

水印嵌入流程见图2。具体过程如下：

a)分别读取载体图像 $\boldsymbol { { \cal I } }$ 和水印图像 $\boldsymbol { W } _ { \circ }$

b)采用Haar小波将载体图像I进行二级小波分解，得到多个分辨率下的逼近子图和细节子图，取第二层分解的单一子图(LL2,HL2,LH2,HH2)。

c)将对应子图进行分块作DCT变换，读取DCT块中除了(1,1)的其他系数作为向量 $\mathbf { x }$ ，(1,1)系数用来决定量化步长，然后使用logistics混沌系统来产生投影向量 $\mathbf { v }$ ，由式（1）得到待嵌入系数y:

$$
y = \pmb { x } ^ { \mathrm { T } } \pmb { \nu }
$$

d)利用以下公式将水印信息嵌入子图的系数中：

$$
q e = \frac { y } { \Delta }
$$

$$
m e = \operatorname { r o u n d } ( q e )
$$

$$
\delta e = m e - q e
$$

$$
\mathrm { ~  ~ { ~ \sigma ~ } ~ } \mathrm { m o d } ( \mathrm { ~  ~ \it ~ { ~ m e ~ } ~ } , 2 ) = w _ { i }
$$

$$
y _ { \scriptscriptstyle  { w } } = m e \cdot \Delta
$$

$$
\mod ( m e , 2 ) \neq w _ { i }
$$

$$
\delta e > 0 \quad y _ { \scriptscriptstyle w } = ( m e - 1 ) \cdot \Delta
$$

$$
\begin{array} { r l } { \delta e < 0 } & { { } y _ { \scriptscriptstyle { w } } = ( m e + 1 ) \cdot \Delta } \end{array}
$$

其中： $y$ 为待嵌入系数； $y _ { \mathrm { w } }$ 为嵌入水印后的系数； $\Delta$ 为步长； $w _ { i }$   
为水印信息。

e)然后由式(7)得到嵌入水印后的DCT系数值 $\mathbf { x w }$ ，对其进行DCT反变换得到小波系数值，再对得到的系数矩阵进行二级小波重构，最后得到了含水印的载体图像 $\operatorname { I w }$ 。

$$
\pmb { x } _ { \nu } = ( y - y _ { \nu } ) \pmb { \cdot } \pmb { \nu } + \pmb { x }
$$

f)根据下式计算峰值信噪比：

$$
P S N R { = } 1 0 ^ { * } \mathrm { l o g } \Bigg ( \frac { 2 5 5 ^ { 2 } } { M S E } \Bigg )
$$

$$
M S E = \frac { 1 } { M N } \sum _ { i } \sum _ { j } \big [ I ( i , j ) - I _ { w } ( i , j ) \big ] ^ { 2 }
$$

其中： $I ( i , j )$ 和 $I _ { w } ( i , j )$ 分别为嵌入水印前后载体图像的像素值；MSE为载体图像嵌入水印前后的均方误差。理论上 $P S N R$ 值在$4 0 ~ \mathrm { d B }$ 以上，水印图像已具有较好的不可见性。

g)水印的提取过程是嵌入的逆过程。

$$
q _ { _ D } = { \frac { { \mathbf { x } } _ { _ D } ^ { \mathrm { T } } \nu } { \Delta } }
$$

$$
m _ { _ D } = \mathrm { r o u n d } ( q _ { _ D } )
$$

$$
w _ { i } ^ { \prime } { = } \bmod { ( } m _ { \scriptscriptstyle D } , 2 )
$$

比特误码率（biterrorratio,BER）用来衡量提取水印的恢复情况，其值越小说明水印恢复的越好，计算方法为：

![](images/c444d1620e7f63b8dcfd73285d833d94179692e3ebbfedb1127f109041426253.jpg)  
BER $\underline { { \underline { { \mathbf { \Pi } } } } } =$ 传输中的误码/传输的总码数  
图2基于DWT单一子图的DWT-DCT联合变换水印算法

为便于区分，将基于二次DWT分解后LL2子图的STQIM-DWCT-single 算法，也是文献[3]中使用的联合变换方法，记做DWCT(LL2)，采用其他三个高频子图的 STQIM-DWCT-single算法分别记为DWCT(HL2)、DWCT(LH2)、DWCT(HH2)。

# 2 基于粒子群算法优化的DWT多子图水印算法

与之前的基于DWT单一子图的联合变换水印算法不同，本文提出选择DWT的多个子图用来水印嵌入。本文提出选择一层逼近子图进行再分解后得到的二层四个子图用来水印嵌入，

将每个二层子图均做分块DCT变换，就形成了四个DCT系数矩阵，从四个矩阵中选取相应的DCT系数，然后对每个系数给予一个权重 $\boldsymbol { a } _ { 1 }$ ， $a _ { 2 }$ ， $a _ { 3 }$ 和 $a _ { 4 }$ ，将其组合起来，即

$$
y = \alpha _ { 1 } \cdot D C T _ { 1 } + \alpha _ { 2 } \cdot D C T _ { 2 } + \alpha _ { 3 } \cdot D C T _ { 3 } + \alpha _ { 4 } \cdot D C T _ { 4 }
$$

得到的系数 $y$ 即为待量化的值用来嵌入水印。用扩展变换的思想来说，基于DWT单子图的算法中的扩展变换系数来自同一个DWT子图的DCT变换，而基于DWT多子图的算法中的扩展变换系数来自于DWT的多个不同子图的DCT变换，即

其中： $\pmb { x } = [ D C T _ { \mathrm { _ 1 } } , D C T _ { \mathrm { _ 2 } } , D C T _ { \mathrm { _ 3 } } , D C T _ { \mathrm { _ 4 } } ]$ ， $D C T _ { i }$ 代表第 $i$ 个子图的DCT系数值； $\pmb { \nu } = [ \alpha _ { 1 } , \alpha _ { 2 } , \alpha _ { 3 } , \alpha _ { 4 } ]$ 。权重 $\alpha _ { 1 }$ ， $a _ { 2 }$ ， $a _ { 3 }$ 和 $a _ { 4 }$ 的选择对算法的性能至关重要，本文将通过粒子群算法来搜索其最优解。粒子群优化算法(particle swam optimization,PSO)是一种全局优化算法，算法通过模拟鸟类飞行觅食时相互之间的群体协作行为使得整体最优化。在PSO优化算法中，待优化题目的所有潜在解被看做是搜素空间内的一群鸟，每个解相当于一只鸟，每只鸟都由一个矢量来决定它飞行的速度与方向即速度矢量，在算法中解也就是粒子。根据实际问题确定对应的优化函数来决定适应值，根据适应度值寻找最优粒子。粒子通过跟踪局部和全局的最优粒子更新自己，通过迭代的方法找到最终的最优解[6]。粒子群算法的运算规则比遗传算法简单，它不同于遗传算法中的“交叉”和“变异”，而是通过已搜索到的最优值来寻求全局最优解。PSO算法因其算法简单易于实现、收敛精度高等得到了研究界的广泛关注。

PSO 算法中几个重要定义：粒子I在 $N$ 维空间的位置矢量为 $\pmb { p } _ { i } \mathrm { = } ( p _ { I } , \ p _ { 2 } , \ \cdots , \ p _ { N } )$ ，飞行速度矢量为 $\bullet _ { i } { = } ( s _ { l } , ~ { \cal s } _ { 2 } , ~ { \cdots } , ~ { s } _ { N } ) _ { \mathrm { \scriptsize { c } } }$ 每个粒子根据目标函数计算相应的适应度值(fitness)，根据适应度值记录单个粒子的当前位置 ${ \pmb p } _ { i }$ 和到目前为止所发现的最好位置 $( p b e s t _ { i } )$ 。此外，还要记录群体粒子中截止目前所找到的全局最优位置 $( g b e s t )$ 。然后粒子通过自己单个的最好记录和群体的最好记录来决定下一步的进化。

PSO算法是一种迭代算法，它需要先初始化一群随机解作为粒子群，然后进行迭代运算来寻找到最优解。在每一次迭代中，粒子通过与两个最好位置(pbesti，gbest)比较来更新自己。粒子通过下面的两个公式来进行速度和位置的更新：

$$
\begin{array} { r } { \mathsf { s } _ { i } = \pmb { s } _ { i } + c _ { 1 } \cdot \operatorname { r a n d } ( ) \cdot ( p b e s t _ { i } - p _ { i } ) + c _ { 2 } \cdot \operatorname { r a n d } ( ) \cdot ( g b e s t - p _ { i } ) } \end{array}
$$

$$
\pmb { p } _ { i } = \pmb { p } _ { i } + \pmb { s } _ { i } \qquad i = 1 , 2 , . . . , N
$$

其中： $\mathbf { \sigma } _ { \pmb { s } _ { i } }$ 是粒子的速度矢量； ${ \pmb p } _ { i }$ 代表粒子当前的位置；pbesti和gbest如上述定义； $\mathbf { c } _ { 1 }$ 和 $\mathbf { c } _ { 2 }$ 是学习因子。对于每个粒子，在每一维中都会对其速度设置一个阈值 $V _ { \mathrm { m a x } } ( V _ { \mathrm { m a x } } > 0 )$ 来限制粒子的速度，使得粒子的速度不超过最大速度（或最小速度）。

为便于计算，将基于PSO优化的DWT多子图的DWT-DCT联合变换水印算法记为 STQIM-DWCT-PSO multi。STQIM-DWCT-PSOmulti算法流程框图见图3。

![](images/d5cf19934c6a7dd01f00786b855aa9d774e739044754f1e039db4bacaa840a82.jpg)  
图3基于PSO优化的水印算法流程

PSO算法优化水印系统的过程如下：

a)初始化 $\mathbf { m }$ 个系数组(α1，α2，α3，α4)作为粒子群初始位置pi，并产生一组随机粒子作为变换速度si。

b)初始化所有pbesti和 gbest 的适应度值为0。

c)由峰值信噪比和误码率设计适应度函数，根据水印算法进行水印嵌入与提取并计算每个粒子的适应度值fitness。

d)每个粒子都将其当前的适应度值与本粒子对应的最好位置(pbesti)的适应度值比较，如果其结果更好，则更新该粒子的最好位置pbesti为当前位置。

e)将每个粒子的适应度值与整个群体粒子经过的最好位置(gbest)的适应度值作比较，如果某个粒子的结果较好，则将其位置作为当前整体的最好位置gbest。

f)根据式(16)(17)调整粒子的速度和位置。

g)判断是否达到结束条件，没有达到结束条件则跳至c);若满足条件，则此时的gbest即为最优的系数组。

常用的算法迭代终止方法有两种：一是确定最大迭代次数G；二是确定最小（或最大）适应阈值，当粒子群搜索到的最优位置满足预定的适应阈值则迭代终止。本文中选择最大迭代数作为终止条件。

# 3 基于改进SIFT的水印图像抗几何攻击方法

为了提高数字水印算法抗几何攻击的鲁棒性，近年来研究者们提出了许多抵抗几何攻击的水印方案，其中包括几何不变域方法、矩估计方法和基于特征点的方法等。其中较为典型的是基于特征点的 SIFT算法。SIFT算法是计算机视觉中一种有效的匹配算法，具有旋转不变性和比例尺度不变性等特点。SIFT算法是局部特征提取算法，它通过在不同尺度空间内计算极值点，并将对应的位置、尺度和主方向等特征量提取出来。SIFT的特征点是通过将差分高斯图像中的每一个像素点与当前尺度上和相邻的上、下层尺度上的26个邻域点相比较而得到的极大值或极小值，并通过泰勒展开式和Hessian矩阵计算过滤掉不稳定的极值点。描述特征点时，首先计算特征点的像素精度位置，再在高斯图像上统计特征点特定邻域内像素的梯度方向与梯度和，确定特征点的主方向。描述特征点时，利用关键点所在的尺度空间（高斯金字塔的某一层）确定特征点周围的16个 $4 ^ { * } 4$ 矩形邻域，计算每个子域的梯度方向直方图（梯度方向均匀分为 $\mathbf { \nabla } _ { m }$ 个方向，通常 $\mathbf { \nabla } _ { m }$ 为8）；然后将计算出的方向梯度直方图按位置进行排序，进而构成了 $1 6 ^ { * } 8$ 即128维的特征描述子向量；最后对特征描述子向量进行归一化处理，以减少光照亮度变化的影响。图像匹配时通常通过计算特征点之间的欧氏距离来进行图像特征点的匹配判定。

经典SIFT算法保持有较高的匹配准确率，但因为要生成128维的描述子，不但要耗费较多的时间，还占用较大的内存空间，当特征点较多时严重影响特征匹配的速度。之后研究者们提出了多种SIFT改进算法。文献[8]提出一种在极坐标下的特征描述方法，以特征点为圆心扩散出多个圆，每个圆拆分成四个扇形；然后以 $x$ 坐标为界进行垂直镜面反射，得到新的特征描述区域计算特征描述子。Amin 等人[12]提出一种自适应分区的 SIFT改进算法，在对数极坐标网络中，划分三个圆形区域，在每个圆形区域中划分出多个扇形区域，在每个扇形区域内统计不同的梯度方向直方图来描述特征点。卢官明等人[1]提出基于圆环域的特征描述改进方法，以特征点为圆形，向外扩散出多个圆形区域，计算每个圆形区域内的梯度直方图来描述特征点。但它们或是在提高描述质量时未考虑算法运行时间，或是在提高算法速度时影响了匹配的准确率。

本文对SIFT 算法的特征描述子提出一种新的改进，同样采用同心圆的形式，但不同于统计圆环内点的方向梯度直方图，而是选择圆上的像素点来统计其方向梯度直方图。改进算法首先以特征点为圆心，选取4个不同半径的同心圆上的点作为采样点，在同一个圆上的采样点之间具有相同的间距，每个圆上的点在特征点的指定方向上。然后统计相同半径圆上的点的方向梯度直方图，根据圆的不同对其进行排序继而构成了 $^ { 4 ^ { * } 8 }$ 即32维的特征描述子向量。本文算法选择与矩形邻域一样个数的64个采样点（图4），采样点的确定方式如下：设采样点的坐标为 $( \mathrm { X } ( i ) , \mathrm { Y } ( i ) ) , i { = } 1 , 2 , . . . , 6 4$ ，其中：

$$
r ( i ) = 4 ( 1 + ( ( i - 1 ) \mathrm { m o d } 4 ) )
$$

$$
\varphi ( i ) = \mathrm { f i x } ( \begin{array} { c } { { i - 1 } } \\ { { 4 } } \end{array} )
$$

$$
\begin{array} { l } { { X \left( i \right) = r \left( i \right) \cos ( \displaystyle \frac { 2 \pi \varphi \left( i \right) } { 1 6 } ) } } \\ { { } } \\ { { Y \left( i \right) = r \left( i \right) \sin ( \displaystyle \frac { 2 \pi \varphi \left( i \right) } { 1 6 } ) } } \end{array}
$$

![](images/fe1045bebaa5313787bff18c052d4fa07f0907085d63130e6a2d9236752b3e6a.jpg)  
图4改进的特征描述子采样模式

加入改进SIFT进行几何校正预处理的水印算法流程框图见图5。具体步骤如下：读取载体图形I对其进行DWT-DCT联合变换，组合多个DWT子图的DCT系数用于嵌入水印，利用ST-QIM算法进行水印嵌入，嵌入水印后的系数先进行DCT反变换再进行小波重构，最后得到含水印的载体图像。对嵌入水印后的载体图像进行SIFT 特征点提取与描述，保存这些特征点作为密钥用于后期校正。经过传输使用后的载体图像会受到各种攻击，在水印提取之前，先对受攻击载体进行SIFT特征点提取与描述，然后与保存的特征点密钥进行匹配，判断图像是否经历了几何攻击，确定受到几何攻击的类型与尺度；然后进行相应的校正处理；最后再对校正后的载体图像进行水印提取操作。

![](images/9dd4830e08f9e03c7eaff2af99f1de08729813bdcb3bc1be983a3d9778a66fec.jpg)  
图5基于改进SIFT的抗几何攻击水印算法流程

# 4 实验仿真及分析

本文的仿真实验中选取多幅分辨率为 $2 5 6 ^ { * } 2 5 6$ 的灰度图像作为载体图像，带有“东学”字样的二值图像作为水印图像。水印嵌入与提取算法以 ST-QIM算法为基础。

# 4.1基于粒子群算法优化的DWT多子图水印算法

仿真实验时，基于DWT单子图的DWT-DCT联合变换水印算法中，首先将载体图像进行二级DWT变换，然后只选择二层子图中的一幅子图进行相应的DCT变换用来水印嵌入，并对其仿真结果进行比较。基于DWT多子图的DWT-DCT联合变换水印算法中提出选择二层子图中的多幅子图，均作相应的DCT变换,然后结合多个子图用来水印嵌入。为了选择合适的子图组合系数，首先需要由粒子群优化(PSO)算法来求解出最优的系数因子。在PSO算法中，需要选择合适的适应度函数，本文中利用峰值信噪比(PSNR)和误码率(BER)来构造适应度函数，即

$$
\begin{array} { r l } { f i t m e s s } & { = P S N R \ + \mu \cdot \sum _ { i } \left( 1 - B E R \ ( i ) \right) } \end{array}
$$

其中： $\mu$ 为参数； $B E R ( i )$ 指不同攻击后提取出水印的误码率。当PSNR值愈大，表示水印图像的不可见性越好；BER值愈小，表示恢复出的水印图像质量越好。综合两个指标，当适应度值fitness越大，表示算法综合性能越好。

为验证所提算法性能，本文将基于DWT单一子图的四个算法，即 DWCT(LL2)（文献[3]），DWCT(HL2),DWCT(LH2),DWCT(HH2)，与本文提出的基于PSO 算法优化的DWT多子图水印算法(DWCT-PSO)进行比较。为了便于比较算法鲁棒性，通过调节水印嵌入强度，将所有算法的峰值信噪比调节至45dB，以保证嵌入水印图像具有相同的不可见性，然后对其鲁棒性进行比较。仿真结果见图6。

从图6对几种算法进行仿真得到的结果对比可以看出，基于DWT单个子图的四种算法中，选择逼近子图用于水印嵌入的算法在综合鲁棒性上优于其他三种算法。而本文提出的基于DWT多个子图，并经过PSO算法优化的DWCT-PSO算法效果最优，其不仅保证水印的不可见性，在抵抗各种信号攻击的鲁棒性上明显优于基于DWT单个子图的水印算法。

![](images/6063b9de9fb595773a5270438f415c429abc28d7545b5cd8f3f13c1c22ee29fe.jpg)  
(b)JPEG压缩攻击

![](images/7c4667be74cbb75c327f70b8c5ab0467ee407001a9b9a0bfa9455c8d1e7a5722.jpg)  
图6不同算法鲁棒性比较

图7和8分别是利用DWCT(LL2)算法即文献[3]算法与DWCT-PSO算法进行水印嵌入后的含水印载体和通过提取算法提取出的水印图像。

![](images/f87e7b26a860463360a8d5a00f2b6a89b063c3816f89f7e9f59dbccb357bad88.jpg)  
图7文献[3]算法(LL2 子图)，含水印载体(左)，提取水印(右)

![](images/bd21545cc2ed88bceadb1ef751ac0028cebc60c09e82a6cdfceaf1d204158c54.jpg)  
图8DWCT-PSO 算法，含水印载体（左），提取水印（右）

# 4.2基于改进SIFT的水印图像抗几何攻击方法

表1和2给出了经典 SIFT算法(文献[7])、文献[13]中的基于圆环域的改进SIFT算法与本文提出的改进SIFT算法的抗几何攻击的校正检测预估结果与特征提取时间的比较。

表1几何校正预估结果比较  

<html><body><table><tr><td rowspan="2">攻击</td><td colspan="3">几何校正预估结果</td></tr><tr><td>文献[7]</td><td>文献[13]</td><td>改进SIFT</td></tr><tr><td>尺度缩放0.5</td><td>0.4997</td><td>0.4995</td><td>0.4995</td></tr><tr><td>尺度缩放1.5</td><td>1.4970</td><td>1.4981</td><td>1.4993</td></tr><tr><td>尺度缩放2.0</td><td>2.0010</td><td>2.0014</td><td>2.0008</td></tr><tr><td>旋转2°</td><td>2.0710</td><td>2.0607</td><td>2.0462</td></tr><tr><td>旋转15°</td><td>15.014</td><td>14.995</td><td>14.992</td></tr><tr><td>旋转30°</td><td>30.033</td><td>30.052</td><td>30.013</td></tr><tr><td>旋转60°</td><td>60.017</td><td>60.063</td><td>60.022</td></tr><tr><td>旋转120°</td><td>119.998</td><td>120.016</td><td>120.008</td></tr><tr><td>平移(50,0)</td><td>(50,0.017)</td><td>(49.9804,0)</td><td>(50,0.018)</td></tr><tr><td>平移(0,50)</td><td>(0,49.985)</td><td>(0,49.985)</td><td>(0.279,49.41)</td></tr><tr><td>平移(50,50)</td><td>(50.01,49.99)</td><td>(50.027,49.95)</td><td>(50.30,49.90)</td></tr></table></body></html>

表2特征提取时间比较  

<html><body><table><tr><td rowspan="2">攻击</td><td colspan="3">特征点提取时间/s</td></tr><tr><td>文献[7]</td><td>文献[13]</td><td>改进SIFT</td></tr><tr><td>尺度缩放0.5</td><td>1.9</td><td>1.3</td><td>0.5</td></tr><tr><td>尺度缩放1.5</td><td>9.3</td><td>6.5</td><td>4.3</td></tr><tr><td>尺度缩放2.0</td><td>21.2</td><td>17.5</td><td>5.4</td></tr><tr><td>旋转2°</td><td>7.0</td><td>4.6</td><td>1.2</td></tr><tr><td>旋转15°</td><td>8.5</td><td>5.8</td><td>1.6</td></tr><tr><td>旋转30°</td><td>11.2</td><td>7.5</td><td>3.0</td></tr><tr><td>旋转60°</td><td>7.9</td><td>5.3</td><td>3.1</td></tr><tr><td>旋转120°</td><td>11.1</td><td>7.6</td><td>3.1</td></tr><tr><td>平移(50,0)</td><td>8.9</td><td>5.9</td><td>1.4</td></tr><tr><td>平移(0,50)</td><td>5.8</td><td>3.7</td><td>2.4</td></tr><tr><td>平移(50,50)</td><td>4.7</td><td>3.1</td><td>1.2</td></tr></table></body></html>

由表1和2中已有的SIFT算法与本文提出的改进SIFT算法的几何攻击校正和描述子生成时间的比较可以看出，改进的SIFT算法仍保持较高的校正准确性，但描述子生成时间相比于文献[7]缩短了近四倍。这是因为对于特征点的描述，越靠近特征点的邻近点对描述的贡献越大，所以取点时在距离特征点最近的圆上取点最为密集；为了增加描述准确性，将原算法中邻近域由16扩大为32，从而保证了较高的校正准确性。因为只需计算四个同心圆上的点，且每个圆上的所有点距离特征点的方向与距离都是一定的，大大减少了运算量。同时，每个特征点的特征描述向量由128 维减少至32 维，也大大节省了程序运行所需的内存空间。

将提出的SIFT改进算法与水印算法结合使用，载体图像嵌入水印后，先由改进SIFT算法提取出特征点并记录下特征描述子用于后期校正。在水印提取时，算法首先对受攻击载体图像进行特征点提取，然后将其与之前保存的特征点及描述子作匹配，以此来判断含水印载体图像是否受到几何攻击并判断出几何攻击类型。若图像受到了几何攻击，则先对含水印载体进行几何校正，然后再提取水印。图9\~11为未引入SIFT校正的水印算法与本文抗几何攻击水印算法的比较。左一为受到几何攻击后的载体图像左二为未进行几何校正提取出的水印图像。由图9\~11可看出，与未使用几何校正的水印算法相比，基于改进SIFT的抗几何攻击水印算法能较准确的校正图像并提取出水印。

![](images/5815c1b4f110a71b3e6c1e963870e5a126b60b9c8854197a247c9c5136da04ae.jpg)  
图9图像放大2倍，未校正(左二),图像较正及提取的水印(右一二)

![](images/802b0950411fdf8ffced2ef8623c7f895b2d1c3cca4e49766f06762d57da9d67.jpg)  
图10图像平移,未校正(左二)图像较正及提取的水印(右一二)

![](images/8d584a0dd0dcb1ce2831768e9fac6758b884086c024c894e9bb455bd08e8cadf.jpg)  
图11图像旋转 $2 ^ { \circ }$ ,未校正(左二),图像较正及提取的水印(右一二)

同时，为了验证本文提出的抗几何攻击水印算法的有效性，将本文算法与Fazli等人[14]提出的算法进行抗几何攻击仿真比较。为进行鲁棒性比较，将基础水印算法的PSNR值设置为57dB。表3给出了分别利用两种算法进行几何校正后提取出的水印和原水印的NC值。由表中数据可看出，虽然本文算法抗几何攻击的鲁棒性稍逊色于文献[14],但恢复出水印的平均NC值在0.95以上。通常利用水印算法恢复出的水印NC值在0.7以上，则认为该水印算法是行之有效的[15]，因此本文提出的基于改进SIFT的抗几何攻击水印算法是一种有效的、校正精度高、性能稳定的抗几何攻击水印算法。

表3本文算法与文献[14]算法的抗几何攻击性能比较(NC)   

<html><body><table><tr><td>攻击</td><td>文献[14]</td><td>本文算法</td></tr><tr><td>尺度缩放0.5</td><td>0.980</td><td>0.965</td></tr><tr><td>尺度缩放1.5</td><td>0.986</td><td>0.985</td></tr><tr><td>旋转30°</td><td>0.975</td><td>0.936</td></tr><tr><td>旋转80°</td><td>0.977</td><td>0.973</td></tr><tr><td>平移（35,25)</td><td>0.987</td><td>0.983</td></tr><tr><td>中心剪切20%</td><td>1</td><td>0.98</td></tr></table></body></html>

# 5 结束语

本文在DWT域和DCT域图像水印算法基础上，研究基于DWT与DCT联合变换的水印算法。实验仿真结果表明，基于DWT单一子图的水印算法中，利用逼近子图嵌入水印的算法性能最优；本文提出的基于粒子群算法优化的DWT多子图水印算法的鲁棒性明显优于基于DWT单一子图的水印算法。针对所提算法在抵抗几何失真方面的缺陷，本文提出利用SIFT算法进行几何校正预处理，并针对SIFT算法的不足进行了改进。改进后的SIFT 算法用于接收图像的几何校正预处理，不仅具有较高的校正准确率，算法运行时间也大大减少了，还降低了程序运行所需的内存空间。将改进的SIFT算法应用于水印算法中对含水印载体图像进行几何攻击判断并校正，明显提高了水印提取的准确率，是一种有效可行的水印算法。综上所述，本文所提的水印算法是一种盲检测的鲁棒性数字水印方法，对水印有较好的不可见性，对常见的攻击具备较强的鲁棒性，并可推广至彩色图像水印算法中。下一步，如何将SIFT算法与水印昇法史有双地结台为一体，实现更加间洁尚双的水印检测系统仍需要进行深入的研究。

参考文献:   
[1]王颖，肖俊，王蕴红．数字水印原理与技术[M].北京：科学出版社, 2007: 63-65. (Wang Ying, Xiao Jun, Wang Yunhong.Digital watermarking principles and techniques [M].Beijing: Science Press,2007: 63-65.)   
[2]倪林．小波变换与图像处理[M].北京：中国科学技术大学出版社， 2010: 15-24.(Ni Lin. Wavelet Transform and Image Processing [M]. Beijing: Universityof Science and Technologyof China Press,2010: 15-24.)   
[3] Cheng Wei, Li Zhaodan.Robust watermarking algorithm of color image based on DWT-DCT and chaotic system [C]//Proc of IEEE International Conference on Computer Communication and the Internet. 2016: 370-373.   
[4]SainiLK,Shrivastava V.Analysis of attackson hybrid DWT-DCTalgorithm for digital image watermarking with MATLAB[J]. International Journal of Computer Science Trends and Technology,2014,2(3):123-126.   
[5] Singh D,Singh SK.DWT-SVD and DCT based robust and blind watermarking scheme for copyright protection [J]. Multimedia Tools and Applications,2017,76 (11): 13001-13024.   
[6]恩格尔伯里特．计算群体智能基础[M].谭营，译.北京：清华大学出 版社，2009:65-89.(Engelbrecht AP.Fundamentalsof Computational Swarm Intelligence [M].Tan Ying,Trans.Beijing:Tsinghua University Press,2009: 65-89.)   
[7]Lowe DG.Distinctive image features from scale-ivariant keypoints[J]. International JournalofComputer Vision,2004,60 (2): 91-110.   
[8]Liao Kaiyang,Liu Guizhong,Hui Youshi.An improvement to the SIFT descriptor for image representation and matching [J]. Pattrn Recognition Leters,2013,34 (11): 1211-1220.   
[9]Chen B, WornellG W. Quantization index modulation: a class of provably good methods for digital watermarking and information embeddng [J]. IEEE Trans on Information Theory,2001,47 (4): 1423-1443.   
[10] Li Xinchao,Liu Ju, Sun Jiande,et al.Step-projection-based spread transform dither modulation [J].IET Journal on Information Security,2011, 5 (3): 170-180.   
[11] Jiang Yanling， Zhang Yifeng，Pei Wenjiang，et al. Adaptive image watermarking algorithm based on improved perceptual models [J].AEUInternational Journal ofElectronics and Communications,2013,67(8): 690- 696.   
[12] Amin S,Hamid E.Remote sensing image matching based on adaptive binning SIFT descriptor[J]. IEEE Trans on Geoscience and Remote Sensing,2015,53 (10): 5283-5293.   
[13]卢官明，刘瑞珍．基于圆形邻域 SIFT 特征描述子的 3D 人脸识别[J]. 南京邮电大学学报：自然科学版,2015,35 (3):11-17.(Lu Guanming,Liu Ruizhen.3D face recognition based on SIFT feature descriptor in circular neighborhood[J].JournalofNanjing UniversityofPosts&

Telecommunications:NATURAL SCIENCE EDITION,2015,35 (3):11- 17.)

[14]Fazli S,Moeini M.A robust image watermarking method based on DWT, DCT,and SVD using a new technique for correction of main geometric attacks [J]. Optik-International Journal for Light and Electron Optics,2016,

127 (2): 964-972.

[15]Li Jianzhong,Zhu Yinghui.A geometric robust image watermarking scheme based on DWT-SVD and Zernike moments [C]// Proc of the 3rd IEEE International Conference on Computer Science and Information Technology. 2010:367-371.