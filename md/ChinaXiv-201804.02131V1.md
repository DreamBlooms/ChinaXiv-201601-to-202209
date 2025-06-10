# 结合稀疏重构与能量方程优化的显著性检测

赵恒，安维胜，田怀文(西南交通大学 机械工程学院，成都 610031)

摘要：针对现有算法在复杂背景图像显著目标检测中存在背景被错误凸显的问题,为抑制背景提取更加准确的前景，提出一种结合稀疏重构与能量优化的显著性检测算法。首先将输入图像分割为超像素以去除不必要的细节；然后选取图像边界超像素作为背景模板，利用其作为稀疏字典计算重构误差，并作为超像素初始显著值；最后构造新的能量方程对初始显著值优化，并在优化后对其前景增强生成最终显著图。在包含真值图像的 MSRA10K和 ECSSD1000 数据集上，将提出的算法与其他10种算法进行对比测试，PR 曲线图、准确率P、F值的效果优于其他10 种算法的结果。实验结果表明，所提算法在复杂背景图像的显著目标检测中，相比于已有的多种算法鲁棒性更好，能够对背景进行有效的抑制，提取显著目标也更加精确。

关键词：显著性检测；超像素；稀疏重构；能量方程；显著图 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.01.0057

# Saliency detection combined with sparse reconstructionand optimization of energy equation

Zhao Heng,An Weisheng, Tian Huaiwen (School of Mechanical Engineering,Southwest Jiao tong University,Chengdu 6loo31,China)

Abstract:Asextant method wronglyhighlightsbackgrounds insalientobjectdetection fromcomplexbackground images,this paper proposed a new algorithm of saliency detection to suppressbackground in combination with sparse reconstruction and energyoptimization,which extracted foregroundmoreaccurate instantaneously.Firstly,itdecomposed the inputimage into superpixel withinAbstract: ngunnecessrydetail.Then,itselectedimageboundarysuperpixelsasbackgroundtemplates,which usedassparsedictionaries toalculatereconstruction erors tatassuperpixelsinitialsaliency.Fnall,itintroducedtheergy equationtooptimize theinitial saliency,and generatedthe final saliency mapafter the foregroundofoptimizedsaliency was enhanced.It testedthe proposed algorithmandother10algorithms on MSRA10Kand ECsSD10o0 datasetwith ground truths. ThePR Curve,Precision(P)andF-measure(F)of te proposedalgorithmhadbeterperformance thanother10algorithms.The experimentalresultsshowthattheproposedalgorithmis more robusttosuppressbackground efectively,and theextractionof salient object is more precise.

Key words: saliency detection; superpixel ; sparse reconstruction; energy equation; salient map

# 0 引言

人类视觉系统能够迅速关注图像中强烈刺激视觉神经元的区域。为能够从图像中提取出关键信息进行后续处理，研究人员模拟人类视觉注意机制提出了显著性检测算法。由于显著性检测能够集中有限资源于优先处理的图像信息，从而降低计算量，在图像索引错误!未找到引用源。、目标识别分割[1]、图像视频压缩错误!未找到引用源·等领域应用日益增多。显著性检测是结合计算机视觉、神经生物学、心理学等多学科交叉的综合研究问题错误！未找到引用源·，已经成为一个热门研究课题。针对目前数据处理方式的不同，显著性检测算法分为自顶向下和自底向上两类算法模型错误!未找到引用源。。自顶向下模型由目标驱动，需要高级先验知识，根据训练样本学习总结经验；自底向上模型由数据驱动，根据图像视觉内部特征差异提取显著目标错误;未找到引用源。。自底向上模型计算复杂度通常低于自顶向下的模型，目前大多数算法采用这种模型。

1998 年 Itti 等人错误!未找到引用源。研究人眼的视觉特性，提出中心一周围差异算法，利用图像颜色、灰度、方向特征计算区域显著值。根据 Iti 等人开创性的工作，Li等人错误!未找到引用源。构建超图模型，将显著区域检测转换为超图顶点显著值的计算，然后基于中心-周围差异的对比度迭代分析，并在迭代过程中不断用支持向量机优化；Xie等人错误！未找到引用源·提出基于低层与中层特征的贝叶斯框架显著性检测算法，用Laplace 矩阵的稀疏子空间聚类算法与凸包先验相结合计算区域先验概率，然后计算基于

中心一周围差异准则的区域观察概率，最后用贝叶斯框架将先验概率与观察概率相结合计算显著值。由于中心一周围差异是基于局部特征的对比，所以这几种算法常使得图像边缘或者孤立点区域高亮，背景噪声较多。研究人员从不同角度提出了基于全局特征的显著检测模型。Achanta 等人错误!未找到引用源。提出频域调谐算法，分析图像显著性与其频域之间的联系，但由于其在像素级水平进行显著性分析，不能高亮整个显著目标区域，噪声较多。Ran 等人错误!未找到引用源·提出主成分分析算法，取图像特征变化较大的前 $2 5 \%$ 的区域分析显著性，因此边缘较为突出。Hornung 等人错误!未找到引用源。提出显著优化算法，将颜色特征唯一性与空间分布紧凑度相结合作为高斯权重，计算每个区域所有高斯权重的总和并归一化为最终的显著值；Cheng 等人错误!未找到引用源。将基于区域的颜色直方图特征差异对比度与空间距离融合，对于区域颜色特征差异较小，空间分布邻接的区域赋予更高的显著值。若显著目标相对于全局特征对比度差异小，这类算法不能突出显著目标，背景也被错误凸显。近年来，基于边界背景先验的算法取得了较好的效果。Li等人错误!未找到引用源。在计算基于边界背景先验的稀疏和密集重构误差后，根据区域特征聚类进行显著值传播，与算法错误!未找到引用源。有所类似，但其然后又采用高斯核函数和贝叶斯框架进行后处理，从而抑制背景增强前景，但高斯核函数使显著区域几何中心高亮，而远离中心的区域则较为暗淡。Yang 等人错误!未找到引用源-通过计算能量函数的最优解提出了流形排序算法，预设背景标签向量，计算图像各区域与背景的特征差异得到排序得分，从而获取区域显著值。Zhu 等人错误!未找到引用源·提出鲁棒的边界背景先验优化显著性检测算法，应用边界连通性赋予每个边界超像素不同的权值，再计算每个超像素基于背景的特征差异和。基于背景先验的方法取得了很大的进展，目前应用也较广泛，但由于只是单一的利用边界背景先验，若图像背景复杂，区域颜色特征变化以及空间分布都较为离散时，显著图目标虽较为完整，但背景也会错误凸显。

针对现有算法都存在背景错误凸显的问题，为提升显著区域检测的准确性，在文献错误！未找到引用源。错误！未找到引用源。启发下，提出一种结合稀疏重构与能量方程优化的显著性检测算法。将输入图像分割为超像素，选取图像边界超像素作为背景模板，为计算图像各个区域与背景的特征差异，将背景模板作为稀疏字典对各个超像素进行稀疏重构，再将重构误差作为超像素前景先验知识。为了对背景进行较强程度的抑制，使前景均匀一致平滑，构造新的能量方程，并将前景和背景先验同时代入能量方程得到优化结果，对优化后的结果进行前景增强便生成最终显著图。图1是本文算法对部分图像的显著性检测计算过程。为说明本文算法在减少背景错误凸显，提升前景检测准确率的有效性，将本文算法与其他10种显著性检测算法在两个大型数据集进行实验测试对比说明。

# 1 本文算法

# 1.1图像超像素分割

采用简单线性迭代聚类（simple linear iterative clustering,SLIC）算法将图像分割为超像素错误!未找到引用源。。超像素分割是将图像分割为颜色特征较为均匀一致的图像子区域，这些子区域空间较为紧凑且大小均匀，在去除区域内影响较小的颜色特征变化细节的同时，保留了图像目标与背景的边界细节，因此本文将超像素作为显著性检测的最小单位。SLIC算法的基本思想是：a）提取像素的（ $^ { \cdot } l , a , b , x , y \rangle$ ）五维特征，其中（ $^ { \prime } l , a , b$ ）为超像素在CIE-Lab空间的像素颜色特征， $\mathbf { \Psi } ( x , y )$ 为图像像素的坐标；b)假设图像像素总数为 $X _ { n , \astrosun }$ .初始化超像素种子点个数为 $\mid m$ ，得到初始种子点间距 $S = \sqrt { X _ { n } / m }$ ；c）计算以种子点为聚类中心的$2 S \times 2 S$ 区域内像素点相似度差异，将与聚类中心特征差异较小的像素点合并到聚类中心区域，并更新聚类中心的五维特征，不断

![](images/e03a3ae6aaa182caf7784b19e06380967ac0b7c21b8601e03d8959b237f59775.jpg)  
图1本文算法计算过程

地迭代直到整个过程收敛。两个像素点的相似性度量 $D$

$$
D = d _ { c } + \frac { h } { S } d _ { s }
$$

$D$ 值越小表明两个像素点相似程度高。式(1)中, $h$ 为常数，

综合代表颜色和空间特征在相似性度量中的权重； $d _ { c }$ 为任意两像素点 $i , j$ 在CIE-Lab空间的颜色特征欧氏距离； $\boldsymbol { d } _ { s }$ 是其空间距离。其中：

$$
d _ { c } = \sqrt { ( l _ { i } - l _ { j } ) ^ { 2 } + ( a _ { i } - a _ { j } ) ^ { 2 } + ( b _ { i } - b _ { j } ) ^ { 2 } }
$$

$$
d _ { s } = \sqrt { ( x _ { i } - x _ { j } ) ^ { 2 } + ( y _ { i } - y _ { j } ) ^ { 2 } }
$$

图1(a)是原始图像；(b)为SLIC算法的分割结果。超像素图像中超像素颜色特征取其区域内的平均颜色特征。从计算仿真结果看，原图像颜色特征相似邻近的像素合并为一个小区域时，颜色特征变化大的边缘得以保留，而区域内的颜色特征细节被去除。

# 1.2稀疏表示与重构误差

稀疏表示是指在同一个复杂高维数据空间中，任意子数据可由其他数据信息进行简洁的仿射线性表示，通过这一过程可求得每个子数据与其他数据信息的联系。对于维度为 $D$ 的数据点 $X _ { i }$ 和稀疏字典数据集 $B , \ X _ { i }$ 可被 $\textbf {  { B } }$ 稀疏表示，其数学计算过程如式(4)所示。

$$
r _ { i } = \underset { r _ { i } } { \arg \operatorname* { m i n } } \left\| X _ { i } - B r _ { i } \right\| _ { 2 } ^ { 2 } + \lambda \left\| r _ { i } \right\| _ { 1 } , ( r _ { i } ^ { T } \mathbf { 1 } = 1 )
$$

其中： $\lambda$ 为平衡参数； $r _ { i }$ 为稀疏系数。对于图像信息，文献错误！未找到引用源。中指出图像任意区域可由图像其他区域稀疏表示，本文用边界背景先验知识，对图像任意子区域进行稀疏重构。提取超像素的（ $l , a , b , x , y$ ）五维特征，构成数据集合 $\scriptstyle { X = }$ $( { \cal X } _ { 1 } , { \cal X } _ { 2 } , . . . { \cal X } _ { M } )$ ， $M$ 为图像超像素数量，提取 $X$ 中边界超像素特征构成稀疏字典 $B { = } \{ B ^ { 1 } , B ^ { 2 } , { \ldots } , B ^ { N } \}$ ， $N$ 为背景超像素数量，其中边界超像素数据集合 $\textbf {  { B } }$ 定义为稀疏字典。因此，用背景对其他区域进行稀疏重构时，式（4）中 $X _ { i }$ 为 $\boldsymbol { \cal X }$ 中元素， $\pmb { B }$ 为边界超像素特征。其中对图像边界区域的提取结果示例如图1(c)所示。根据式(4)得到稀疏系数 $r _ { i } { = } \{ { r _ { i } } ^ { 1 } , { r _ { i } } ^ { 2 } , { \ldots } { \ldots } , { r _ { i } } ^ { N } \}$ 。对数据稀疏重构的计算过程如式(5)所示。

$$
\bar { X } _ { i } = B ^ { 1 } r _ { i } ^ { 1 } + B ^ { 2 } r _ { i } ^ { 2 } + . . . . . . + B ^ { N } r _ { i } ^ { N }
$$

通过仿射线性表示得到的 ${ \bar { X } } _ { i }$ 与超像素本身 $X _ { i }$ 真实特征之间存在着差异,通过 ${ \bar { X } } _ { i }$ 与 $X _ { i }$ 差异的大小可以了解各个超像素 $X _ { i }$ 与稀疏字典 $\textbf {  { B } }$ 的高维特征差异程度。 ${ \bar { X } } _ { i }$ 与 $X _ { i }$ 的差异通过式(6)计算得到。

$$
\varepsilon _ { i } = { \left\| { \boldsymbol { X } } _ { i } - { \boldsymbol { \overline { { X } } } } _ { i } \right\| } _ { 2 } ^ { 2 }
$$

其中： $\ \varepsilon _ { i }$ 表示第 $i$ 个超像素的重构误差。若根据式(6)计算得到的超像素重构误差值较小，则说明其与背景特征的相似度较高，对于该超像素区域其显著性较低；若计算所得的重构误差值较大，则说明其与背景特征的相似度较小，该超像素区域显著性较高。因此，本文根据式(4)(5)和(6)计算得到的稀疏重构误差 $\varepsilon _ { i }$ 作为超像素的初始显著值，并作为图像的前景先验知识。根据重构误差计算得到显著先验图如图1(d)所示。

# 1.3 显著值优化

# 1.3.1求解目标函数

观察图1(d)与真值图像图1(g)可知，相比于人工标记的真值图像，稀疏重构误差先验图较为粗糙，显著区域不平滑，目标轮廓不清晰，并且存在背景噪声，需进一步处理。文献错误！未找到引用源。错误！未找到引用源。在计算超像素稀疏重构误差后都通过 $K$ -means算法进行聚类分割，从而实现区域显著特征的传播平滑。但由于聚类数目仍需要人为指定，鲁棒性不够强，所以本文较为新颖地提出用能量方程对稀疏重构误差显著特征进行平滑。在计算机视觉领域，能量方程已经得到广泛应用错误！未找到引用源。错误！未找到引用源。本文根据已有的背景先验知识对现有能量方程进行改造，然后应用于显著特征的优化。文献错误！未找到引用源。在PageRank和聚类算法基础上提出了基于求解能量方程最小化的流形排序算法，其能量方程定义为

$$
\scriptstyle { E ( S ) = \mu E _ { d a t a } ( S , \ S _ { 1 } ) + E _ { s m o o t h } ( S ) }
$$

其中： $s$ 为能量方程优化待求解的节点向量； $\pmb { S } _ { 1 }$ 为已知的给定数据的观察向量，可以为前景或者是背景索引向量。文献错误！未找到引用源。中指出 $E _ { d a t a } ( S , \ S _ { \mathbf { 1 } } )$ 为匹配项，用来约束优化后的节点向量 $s$ 与初始节点向量 $s _ { 1 }$ 不应差异太大； $E _ { s m o o t h } ( S )$ 为平滑项，用来约束数据优化后区域差异小，而边界不连续，即颜色特征相似的区域显著值差异不大，颜色特征不相似的区域显著值离散。本文为保证能量方程在匹配平滑数据的同时，增强图像背景区域的抑制程度，利用已有的背景先验知识，对式(7)的计算过程进行改进，在其基础上添加背景抑制项 $E _ { s u p p r e s s } ( y , \ S ) , \ y$ 为背景先验索引向量。式(7)能量方程改进如式(8)所示。求解式(8)中最小 $E ( S )$ ，便可得到最优节点向量 $\boldsymbol { s } ^ { * }$ 。

$$
E ( S ) = \mu E _ { \mathit { d a t a } } ( S , \ S _ { \mathit { 1 } } ) + E _ { s m o o t h } ( S ) + E _ { s u p p r e s s } ( Y , \ S )
$$

本文改进的能量方程对初始显著值优化的具体计算过程如下：

首先，把超像素分割后的图像映射为无向图模型 $G \mathrm { = } ( V , E )$ ，在图模型 $G$ 中 $V$ 为超像素节点集， $E$ 为超像素邻接边集。构建Laplace 矩阵 $\scriptstyle { L = D - W }$ ， $\pmb { W }$ 矩阵是无向图 $\textbf { \textit { G } }$ 边集 $E$ 的权值矩阵（204号 $W { = } \Big [ w _ { i j } \Big ] _ { M \times M } \ ( i , j \in V )$ ，其中 $w _ { i j } = 1 / ( d c _ { i j } )$ 为邻接节点间的颜色特征差异。在式（2）基础上将图像像素颜色特征替换为超像素颜色特征可计算 $d c _ { i j } = d _ { \mathrm { c } } ^ { 2 }$ ，当 $i { = } j$ 时 $w _ { i j } = 0$ 。最后需对 $\pmb { W }$ 矩阵作归一化处理。 $\textbf {  { D } }$ 是对角矩阵，为无向图度矩阵， $d _ { i i } = \sum _ { j } w _ { i j }$ 是其矩阵中元素， $\boldsymbol { \mathsf { Y } }$ 是节点向量 $y$ 对角化的结果。

其次，用超像素稀疏重构误差 $\varepsilon _ { i }$ 构建前景索引节点向量 $\pmb { S } _ { 1 }$ 。根据式(8)，具体的构造新的能量方程如式(9)所示。

$$
E ( S ) = \mu \sum _ { i } ( S ( i ) - S _ { 1 } ( i ) ) ^ { 2 } + \frac { 1 } { 2 } \sum _ { i , j } w _ { i j } ( \frac { S ( i ) } { \sqrt { d _ { i i } } } - \frac { S ( j ) } { \sqrt { d _ { j j } } } ) ^ { 2 } + \sum _ { i } y _ { i } S ( i ) ^ { 2 }
$$

其中： $S ( i )$ 、 $S _ { 1 } ( i )$ 分别为节点向量 $s$ 和 $\pmb { S } _ { 1 }$ 的的元素值； $y _ { i }$ 为背景索引向量 $_ y$ 的元素。在2.1节进行稀疏重构时已经定义了背景先验知识，即图像边界超像素为背景，在此处将其应用于标签向量 $y$ 。当 $y$ 中元素序列对应于背景时，其值 $y _ { i } { = } K$ ， $K$ 为值较大的正常数； $_ y$ 中未标记的元素序列，设 $y _ { i } { = } 0$ 。对式（9）的能量方程进行分析，当 $y _ { i }$ 值较大时，为保证能量方程的最小化，与之对应的超像素背景区域的显著值 $S ( i )$ 需保持较低的数值，即能够保证图像背景区域得到较好的抑制。因此，同时应用前景先验和背景先验，不仅能够较好地匹配平滑前景，还能够较好地抑制背景。

最后，求解能量方程最优解。将式(9)改写为矩阵形式：

$$
E ( S ) { = } { \mu } ( S - S _ { 1 } ) ( S - S _ { 1 } ) ^ { T } { + } S D ^ { - 1 / 2 } L D ^ { - 1 / 2 T } S ^ { T } { + } S Y S ^ { T }
$$

其中： $Y$ 为 $y$ 对角化的结果。对 $s$ 求导，可得

$$
\begin{array} { r l } & { \nabla _ { s } E ( S ) { = } \nabla _ { s } ( \mu ( S - S _ { 1 } ) ( S - S _ { 1 } ) ^ { T } { + } S D ^ { - 1 / 2 } L D ^ { - 1 / 2 T } S ^ { T } { + } S Y S ^ { T } ) ) } \\ & { { = } \nabla _ { s } ( \mu ( S _ { 1 } S _ { 1 } ^ { T } { - } 2 S S _ { 1 } ^ { T } { + } S S ^ { T } ) { + } S S ^ { T } { - } S D ^ { - 1 / 2 } W D ^ { - 1 / 2 T } S ^ { T } { + } S Y S ^ { T } ) } \\ & { { = } \nabla _ { s } t r \mu ( S S ^ { T } - 2 S S _ { 1 } ^ { T } ) { + } t r ( S S ^ { T } { - } S D ^ { - 1 / 2 } W D ^ { - 1 / 2 T } S ^ { T } ) { + } t r ( S Y S ^ { T } ) } \\ & { \qquad { = } 2 \mu S { - } 2 \mu S _ { 1 } { + } 2 S { - } 2 D ^ { - 1 / 2 } W D ^ { - 1 / 2 } S + 2 Y S } \end{array}
$$

其中： $t r$ 为矩阵的迹。 $\nabla _ { s } E ( S ) { = } 0$ 时，可以求得最优解向量$\boldsymbol { s } ^ { * }$ 。

$$
{ \cal S } ^ { * } = ( { \cal I } - \frac { 1 } { 1 + \mu } { \cal D } ^ { - 1 / 2 } W { \cal D } ^ { - 1 / 2 } + \frac { Y } { 1 + \mu } ) ^ { - 1 } \frac { \mu } { 1 + \mu } S _ { 1 }
$$

设 $\alpha = 1 / \left( 1 { + } \mu \right)$ ，由于 $s ^ { * }$ 最终会归一化，式(12)可写为

$$
\boldsymbol { S } ^ { * } = ( \boldsymbol { I } { - } \alpha \boldsymbol { D } ^ { - 1 / 2 } \boldsymbol { W } \boldsymbol { D } ^ { - 1 / 2 } { + } \alpha \boldsymbol { Y } ) ^ { - 1 } \boldsymbol { S } _ { 1 }
$$

根据文献错误！未找到引用源。，式（13）为规范化的结果，将其非规范化后匹配平滑特征的效果更好，结果如式(14)所示。

$$
\pmb { S } ^ { * } = ( \pmb { D } \mathbf { - } \alpha \pmb { W } \mathbf { + } \alpha \pmb { D } \pmb { Y } ) ^ { - 1 } \pmb { S } _ { 1 }
$$

由于 $\alpha$ 和 $\boldsymbol { \varsigma }$ 为常数，并且 $Y$ 值较大，所以 $\alpha$ 和 $\pmb { D }$ 不对其产生较大影响，则式(14)进一步改写为

$$
\pmb { S } ^ { * } = ( \pmb { D } \pmb { - \alpha } \pmb { W } \pmb { + } \pmb { Y } ) ^ { - 1 } \pmb { S } _ { 1 }
$$

# 1.3.2确定目标函数参数

根据式(15)可以看出，对于给定的图像，在前景先验和边界背景先验知识的条件下，要使得区域平滑边界离散， $\alpha$ 和 $\boldsymbol { \mathsf { Y } }$ 的取值对算法性能表现起着关键作用。

由于 $\boldsymbol { \mathsf { Y } }$ 矩阵主要的作用是对图像背景区域进行抑制，所以$Y$ 中对角线上背景序列元素 $Y _ { i i } ^ { B }$ 值理应设置较大的数值，暂时设 $Y _ { i i } ^ { B } { = } 1 0 0 0$ ，从而在图像背景抑制程度较高的情况下，通过实验单独地确立最佳平滑参数 $\alpha$ 。 $\alpha$ 参数值为0\~1，文献错误！未找到引用源。错误！未找到引用源。根据经验设置$\scriptstyle \alpha = 0 . 9 9$ ，并且文献错误！未找到引用源。指出 $\alpha$ 参数值越接近于1，区域显著值平滑的效果越好。在本文中为确立最佳经验参数，在文献错误！未找到引用源。基础上通过设置 $\alpha$ 从0.99\~1的不同逼近值进行实验，然后通过实验结果确定参数。在ECSSD数据集上随机选取100张图像进行测试，然后以准确率召回率（ $. P R$ ）曲线错误！未找到引用源。作为参考指标选择参数。图2为 $\alpha$ 独立设定不同参数值的实验结果，图3为Y独立设定不同参数值的实验结果。

![](images/c0b0f478bb44acb586bb7462145f5cfe8923987aee2a61fa35fd2b957b0b89a1.jpg)  
(a) 不同值下PR曲线图

![](images/29021e8d9ec8484a2df8bea7543360a6e9d020e407bbd0a3765b8cc676b2c483.jpg)  
图2 $\alpha$ 单参数变量实验结果

$P R$ 曲线在 $P R$ 曲线图坐标系上越靠近右上角区域，说明算法性能好，也即参数选择越合适。从图2（a）中可以看出，随着 $\alpha$ 值逐渐逼近于1，算法性能越好，并且当1 $- \alpha { < } 0 . 0 1 \%$ 时， $\alpha$ 的3个不同参数值下的 $P R$ 曲线几乎完全重合，没有太明显的差距，由此说明在 $1 { - } \alpha { < } 0 . 0 1 \%$ 内能够取得最佳参数。图2（b）是图1（d）稀疏先验图经式（15）目标函数在不同$\alpha$ 值下优化后的显著图像。可以看出，随着 $\alpha$ 值的增加，整体平滑效果在进一步的改善，当 $_ { 1 - \alpha }$ 变化小于 $0 . 0 1 \%$ 时，整体视觉效果并没有明显的差异，与图2（a）的表现和文献错误！未找到引用源。的说明基本一致。由于 $\alpha$ 越接近于1平滑效果仍然会越好，所以本文最终设定参数 $\scriptstyle { \alpha = 1 }$ 。

![](images/4fdd3bb6da1e3ec51d52c25292080863da3b0329899bf9c67da81c07a5a14370.jpg)  
(a) $Y _ { i i } ^ { B }$ 不同值下 $P R$ 曲线图

![](images/48aa08907faa6efa84baee891e77c249027e4877880a1335849aa965bf7d71b8.jpg)  
0 （204 $1 0 ^ { - 3 }$ 10-²10-1 1 10 10²10104(b) $Y _ { i i } ^ { B }$ 取不同值下平滑图像

在 $\alpha$ 取得最佳参数值的情况下，通过改变 $\boldsymbol { \mathsf { Y } }$ 中非零数值进行多次实验，可确立 $\boldsymbol { \mathsf { Y } }$ 初始选取的数值是否合理。由于实验初始设定 $Y _ { i i } ^ { B } { = } 1 0 0 0$ ，所以以1000 作为界限，利用ECSSD 随机选取的100 张图像进行实验。在实验中发现算法性能随着$Y _ { i i } ^ { B }$ 值改变呈非线性变化：在 $Y _ { i i } ^ { B } \ge 1 0 0 0$ 时，不同 $Y _ { i i } ^ { B }$ 值下通过实验得到的平滑显著图像没有明显差别；在 $1 0 0 0 \geq Y _ { i i } ^ { B } \geq 0$ 时，随着 $Y _ { i i } ^ { B }$ 的减小并逐渐逼近0时，平滑显著图像的背景抑制程度先保持平稳，而后背景抑制程度渐渐降低。具体实验结果如图3所示。从图3（a）可知，在 $1 0 > Y _ { i i } ^ { B } > 0$ 时，随着 $Y _ { i i } ^ { B }$ 值数值的增大， $P R$ 曲线逐渐的靠近右上角区域，体现出算法性能逐渐提升，并且算法性能提升速度从较快转向缓慢，特别是在0\~1时，算法性能出现较大变化，而在1\~10内变化较为缓慢；在 $Y _ { i i } ^ { B } \ge 1 0$ 时，随着 $Y _ { i i } ^ { B }$ 数值逐渐增大，各个 $Y _ { i i } ^ { B }$ 下的 $P R$ 曲线几乎完全重合没有明显差别，算法性能提升到最大程度并且保持稳定。从图3（b）可以看出，在 $1 0 > Y _ { i i } ^ { B } > 0$ 时，显著图像背景区域出现离散噪声，背景错误凸显，并且随着 $Y _ { i i } ^ { B }$ 值的增大背景抑制情况有所改善；在 $Y _ { i i } ^ { B } \ge 1 0$ 时显著图像背景抑制较好，并且随着数值的增大，显著图像并没有出现明显的变化，显著图像目标和背景区域趋向于稳定的状态，与图3（a）PR曲线图的表现相符合，也与1.3.1节所构造新能量函数的理论分析一致。此外，观察图3（b）中平滑后的显著图像可知，在同一条件下，不同图像随着 $Y _ { i i } ^ { B }$ 值的变化，背景抑制的程度有所差异，说明不同复杂背景图像在背景抑制程度相同的情况下，对 $Y _ { i i } ^ { B }$ 值的大小有其自身固有的要求。考虑到在 $Y _ { i i } ^ { B } > 1 0$ 并且设定不同 $Y _ { i i } ^ { B }$ 值时，算法在所测试图像中的性能表现都十分平稳。因此，初始设定 $Y _ { i i } ^ { B } { = } 1 0 0 0$ 为较大数值较为合理，可以不失一般性地在进行图像显著目标检测时，对背景进行较高程度的抑制，也从侧面说明针对 $\alpha$ 值的独立参数变量实验是合理有效的，从而最终设定式（15）目标函数参数 $\scriptstyle \alpha = 1$ ，$Y _ { i i } ^ { B } { = } 1 0 0 0$ 0

图2（e）是图1(d)稀疏先验的经式（15）目标函数在参数$\scriptstyle \alpha = 1$ ， $Y _ { i i } ^ { B } { = } 1 0 0 0$ 情况下优化的平滑显著图像。可以看出，图像显著目标区域完整性，均匀高亮一致性和离散背景噪声的抑制程度都有巨大的改善。

# 1.4 后处理

为进一步提升显著目标区域均匀高亮的程度，需对显著图进行后处理。显著图的后处理，目前已有多种方法，贝叶斯增强错误未找到引用源。、高斯函数中心聚焦错误！未找到引用源。、本文在显著图背景区域已经得到较强抑制的情况下，用指数函数来强化前景，增加前景与背景的对比度。具体计算过程如式(16所示。

$$
S _ { m } ( i ) = \left\{ \begin{array} { c } { { 1 ~ , ~ e ^ { S ^ { * } ( i ) } > 2 } } \\ { { e ^ { S ^ { * } ( i ) } - 1 , ~ \sharp \sharp / \sharp } } \end{array} \right.
$$

其中： $\boldsymbol { S } ^ { * } ( i )$ 为图割优化后的显著值； $S _ { m } ( i )$ 为增强前景后的最终显著值。图1(f)是经式(16)突出前景的结果，相比于图1(e)，背景区域没有太大变化，显著目标区域却更加均匀一致高亮，也最为接近图1(g)人工标记的真值图。

由于超像素不同的尺度对分割结果有较大影响，超像素个数较多时，显著性检测结果细节信息能得到较多的保留；超像素个数较少时，显著性检测结果能保留图像的整体结构信息错误未找到引用源。。因此，参照文献错误!未找到引用源。在本文中则具体地选用超像素内像素个数为10、15和20三种尺度生成超像素图像，使显著性检测结果在保留整体结构信息时能够体现较多局部细节。对不同尺度超像素下的显著值进行多尺度平均融合如式(17)所示。

$$
S _ { m a p } ( k ) = \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } S _ { m } ^ { i } ( k ) }
$$

其中： $S _ { \scriptscriptstyle m a p } ( k )$ 表示像素 $k ( x , y )$ 的显著度融合结果； $S _ { m } ^ { i } ( k )$ 表示像素 $k$ 在第 $i$ 个尺度下的显著度。上述出现的各个阶段的显著图像均为多尺度融合图像。为验证本文算法相比于其他算法更具普遍性的性能提升效果，在第2章有更加详细的测试说明对比。

本文算法基本步骤如下：

结合稀疏重构与能量方程优化的显著性检测。

输入：一幅图像。

a)利用SLIC算法将图像分割为超像素，并提取超

![](images/cbabbb8cc79af4af5caa65cf045e3709d457a55f6f4fa80774af98c3e41fa278.jpg)  
图4各种算法显著性检测结果对比

像素颜色空间特征。

b)选取图像边界区域的超像素作为背景构建稀疏字典 $\textbf {  { B } }$ ，利用稀疏字典计算超像素重构误差 $\boldsymbol { \varepsilon } _ { i }$ ，将其作为图像前景先验知识并构建节点向量 $s _ { 1 }$

c)由超像素图像构建无向图 $\textbf { \textit { G } }$ 与Laplace矩阵，同时利用前景先验 $s _ { 1 }$ 和背景先验 $y$ ，代入式(15)目标函数求解最优节点向量$\boldsymbol { s } ^ { * }$ ，再据式(16)计算前景增强的显著值 $\pmb { S } _ { m }$ 。

d)改变超像素分割尺度，重复步骤b)和c)得到不同尺度下的显著图像 $\pmb { S } _ { m }$ ，并用式(17)平均融合生成最终的显著图像 $\pmb { S } _ { m a p }$ 。

输出：显著性检测图像。

# 2 实验评价分析

# 2.1数据集测试比较

为验证本文结合稀疏重构与能量方程优化的显著性检测算法的实际应用效果，引入固定阈值分割的 $P R$ 曲线图，自适应阈值分割得到的准确率 $P$ 、召回率 $R$ 和 F-measure、以及MAE值五种客观评价指标，在领域内通用的MSRA10K和

ECSSD 两个大型数据集错误!未找到引用源。上，与本文所参考的两种算法，以及其他几种经典和近年来应用较多较为先进的总共11种显著性检测算法进行实验对比。实验设备为 $\mathrm { I n t e l } ~ 3 . 4 ~ \mathrm { G H z }$ 处理器,4GB内存的Windows7系统台式电脑，软件采用MATLABR2014b。

MSRA10K包含10000幅图像，有相应的人工标记的真值图，包含不同复杂自然场景的图像。ECSSD包含1000幅图像，带有人工标记真值图像，相比于MSRA10K其自然场景更为复杂，显著性检测的挑战难度更大。测试算法包括CHM错误!未找到引用源。、DSR 错误!未找到引用源。、FT错误！未找到引用源。、GMR错误!未找到引用源。、IT错误！未找到引用源。、LMLC错误！未找到引用源。、PCA错误！未找到引用源。、RBD 错误!未找到引用源。、RC 错误!未找到引用源。、SF错误!未找到引用源。（算法首字母排序)，其中本文主要所参考的算法是LMLC、GMR两种算法。所对比的显著性检测算法的图像结果，由文献作者网页提供，或者是文献作者网页公开源代码生成。

# 2.1.1视觉效果对比

显著性检测算法是模拟人类视觉注意机制的信息提取方法，所以首先对各种算法的显著性检测结果进行视觉效果

![](images/b907030b0e7a6e61ea0774be76c1df98d1e1a9d3e359a04b9806054b5fd556d7.jpg)  
图5PR曲线图对比

表1自适应阈值P，R， $F$ ，MAE对比  

<html><body><table><tr><td rowspan="2">算法</td><td colspan="4">MSRA 10K</td><td colspan="4">ECSSD 1000</td></tr><tr><td>P</td><td>R</td><td>F</td><td>MAE</td><td>P</td><td>R</td><td>F</td><td>MAE</td></tr><tr><td>OUR</td><td>0.910</td><td>0.761</td><td>0.853</td><td>0.111</td><td>0.802</td><td>0.668</td><td>0.730</td><td>0.166</td></tr><tr><td>CHM</td><td>0.850</td><td>0.719</td><td>0.792</td><td>0.142</td><td>0.748</td><td>0.584</td><td>0.659</td><td>0.194</td></tr><tr><td>DSR</td><td>0.851</td><td>0.741</td><td>0.807</td><td>0.121</td><td>0.746</td><td>0.649</td><td>0.689</td><td>0.171</td></tr><tr><td>FT</td><td>0.691</td><td>0.488</td><td>0.595</td><td>0.235</td><td>0.463</td><td>0.317</td><td>0.379</td><td>0.289</td></tr><tr><td>GMR</td><td>0.890</td><td>0.753</td><td>0.834</td><td>0.126</td><td>0.772</td><td>0.644</td><td>0.693</td><td>0.187</td></tr><tr><td>IT</td><td>0.570</td><td>0.269</td><td>0.428</td><td>0.213</td><td>0.507</td><td>0.169</td><td>0.312</td><td>0.271</td></tr><tr><td>LMLC</td><td>0.776</td><td>0.760</td><td>0.748</td><td>0.163</td><td>0.638</td><td>0.549</td><td>0.562</td><td>0.260</td></tr><tr><td>PCA</td><td>0.800</td><td>0.684</td><td>0.746</td><td>0.185</td><td>0.658</td><td>0.530</td><td>0.579</td><td>0.247</td></tr><tr><td>RBD</td><td>0.869</td><td>0.798</td><td>0.837</td><td>0.108</td><td>0.725</td><td>0.667</td><td>0.677</td><td>0.171</td></tr><tr><td>RC</td><td>0.851</td><td>0.780</td><td>0.815</td><td>0.137</td><td>0.734</td><td>0.672</td><td>0.680</td><td>0.186</td></tr><tr><td>SF</td><td>0.848</td><td>0.594</td><td>0.747</td><td>0.175</td><td>0.656</td><td>0.425</td><td>0.543</td><td>0.228</td></tr></table></body></html>

直观的对比。在图4中仅展示各种算法的部分显著性检测图像结果，其中包含原图像以及真值图像。从图4可以看出，针对不同复杂背景图像，各种算法的结果与真值图相比，都有一定程度上的差异，但本文算法的结果最接近于真值图。基于局部特征对比的IT算法，对图像颜色特征变化较大的区域敏感，显著图呈现出一些离散的点、线带状区域；CHM，LMLC算法都采用了IT 算法的思想，虽显著性检测效果有大幅度提升，但不能避免背景噪声较多的缺陷，特别是LMLC算法对图像背景抑制较弱。基于全局特征对比的FT、PCA、SF、RC 算法的显著性检测结果中，FT算法结果较差，其是在像素层面计算显著性，凸显的显著像素分布较为离散，无法辨别显著目标；PCA基于图像主成分分析，显著目标边缘相比于区域内部还更加高亮；SF、RC算法相对较好但图像目标相对于背景颜色特征不具有明显差异时，显著目标不够平滑完整，并且仍然不能较好地抑制背景。本文算法以及DSR、GMR、RBD几种较为先进的算法都能够较为完整均匀一致凸显图像的显著目标，但是观察显著图细节，这三种先进算法的显著图在完整突出显著目标的同时，部分背景区域也处于高亮状态，前景背景分离不够彻底，而本文算法对背景区域的抑制优于这三种算法，背景噪声最少。从显著图的视觉效果看，本文提出的算法比所参考改进的算法性能有明显提升，而且与其他算法相比，总体上在均匀一致高亮显著目标的同时，成功地对背景区域进行了更强的抑制，背景错误凸显的情况明显减少，对图像显著目标的提取最为准确。

# 2.1.2显著性检测客观评价

1）固定阈值分割 $P R$ 曲线图对比对所有算法的显著图进行固定阈值分割，将得到的二值图与其所对应的真值图进行比较计算平均准确率 $P$ 和召回率 $R$ 。将阈值从0变换到255，便能得到一系列的 $P$ 和 $R$ 值，再将 $P$ 、 $R$ 值的变化绘制成图，从而得到 $P R$ 曲线。 $P$ ， $R$ 计算过程如下：

$$
P = { \frac { \sum _ { ( x , y ) } G T ( x , y ) S b ( x , y ) } { \sum _ { ( x , y ) } S b ( x , y ) } }
$$

$$
R = \frac { \sum _ { ( x , y ) } G T ( x , y ) S b ( x , y ) } { \sum _ { ( x , y ) } G T ( x , y ) }
$$

式（18)（19)中， $ { G T } ( x , y )$ 为人工标注的真值图像灰度值;$S b ( x , y )$ 为显著性检测的二值化图像灰度值。

图5是多种算法在两个数据集上的 $P R$ 曲线图。对显著性检测算法来说，在 $P R$ 曲线图上，随着召回率 $R$ 的提升，准确率 $P$ 处于较高水平区间的持续范围越广，表明算法性能越好，即 $P R$ 曲线在图中表现为在更加靠近右上角区域，并且趋向于扁平。

在MSRA10K数据集上，本文算法的 $P R$ 曲线准确率在 $80 \%$ 以上的高水平区间持续范围优于所有其他对比的算法；ECSSD的数据集上包括其他对比算法在内的 $P R$ 曲线结果，相比于MSRA10K数据集上的结果性能都有所降低，也说明其显著性检测挑战性更大，但本文算法准确率高于 $70 \%$ 的高水平持续区间范围优于所有对比的算法，相比于其他算法性能有提升明显。在两个数据集上本文算法的 $P R$ 曲线都最靠近于右上角区域，性能优于其他算法。

2）自适应阈值准确率 $P$ 、召回率 $R$ 、F-measure $( F )$ 值对比在显著目标检测召回率较高的情况下，图像背景错误凸显的程度越低，越能获得较高的准确率 $P$ 和 $F$ 值，算法性能越好。在两个数据集上对图像显著图进行自适应阈值二值化分割，自适应阈值取显著图所有像素灰度平均值的两倍。阈值计算如式(20)所示。

$$
T h r = \frac { 2 } { M \times N } { \sum _ { x = 1 } ^ { M } } { \sum _ { y = 1 } ^ { N } } S _ { m a p } ( x , y )
$$

计算所有算法在两个数据集上显著性检测结果的自适应阈值分割图像的平均准确率 $P$ 、召回 $R$ 率，再进一步计算 $F$ 值，其中 $F$ 值按式(21)计算。

$$
F = \frac { ( 1 + \beta ^ { 2 } ) P R } { \beta ^ { 2 } P + R }
$$

其中： $\beta$ 为衡量准确率与召回率的权值；此处 $\beta ^ { 2 } { = } 0 . 3 \ _ { \circ } \ P _ { \circ } \ R .$ ，$F$ 值越大，说明算法性能越好。不同算法显著性检测结果自适应阈值分割得到的平均 $P$ ， $R$ 、 $F$ 值如表1所示。可以看出，在两个数据集上，本文算法的准确率 $P$ 和 $F$ 值高于其他所有对比算法的结果；在MSRA10K 数据集上， $R$ 值略低于RBD、RC 算法；在ECSSD数据集上， $R$ 值略低于RC算法，但差异都不是太大。从整体上来说本文召回率 $R$ 仍处于较为优异的水平，从而本文算法在获得较高召回率的情况下， $P$ 和 $F$ 值的结果要优于其他所有算法的结果，说明本文算法针对显著目标检测的精确性最高，背景错误凸显程度最低，算法性能优于其他算法。

3）平均绝对误差MAEMAE是显著图与其对应二值真值图之间的平均绝对误差，反映了显著图与真值图的相似程度。MAE值计算如下：

$$
\mathrm { M A E } = \frac { 1 } { M \times N } \sum _ { x = 1 } ^ { M } \sum _ { y = 1 } ^ { N } \Bigl | S _ { m a p } ( x , y ) - G T ( x , y ) \Bigr |
$$

其中： $M$ 和 $N$ 代表输入图像的大小，即宽度和高度； $S ( x , y )$ 代表图像像素灰度值； $ { G T } ( x , y )$ 为真值图像灰度值。MAE 值越小，说明算法的性能越好。不同算法显著性检测结果MAE值如表1所示。可以看出，与其他几种算法的结果相比，在MSRA10K数据集上，本文算法的MAE与RBD算法相当，优于其他9种算法的结果；在ECSSD数据集上，所有算法的MAE值都有所增大，说明ECSSD数据集更具挑战性，但本文算法的MAE值优于其他所有对比的算法，与真值最为相似，说明本文算法相对于其他算法，针对自然场景更为复杂的图像显著性检测性能更为鲁棒。

# 2.2显著性检测算法在物景分离中的应用

在某些摄像需要突出图像主题增加层次感的自然场景，普通相机难以通过控制景深达到这样的艺术效果。因此，本文将所对比的全部自底向上的算法用于图像显著目标与背景分离的后处理过程，并对背景区域进行高斯滤波模糊处理，从而达到突出前景虚化背景的目的。具体步骤是：首先利用显著性检测算法获得显著图像；然后对显著图像进行自适应阈值二值分割，再分别获取原图像显著目标和背景；最后在高斯滤波对背景进行虚化后与前景叠加，从而增加物景之间的层次感。应用图像进行测试，并且以图6部分图像作为展示示例。

图6中两个原图像示例自然场景都较为复杂，目标颜色特征不统一，背景特征也较为离散，目标和背景从总体上存在着大面积的相似颜色特征区域。从图6中物景分离的结果可以看出，几乎所有算法都能够在一定程度上使得主要物体突出，但由于各种算法本身对显著目标提取性能的差异，有的算法并没有能够保证图像主要物体完整，并且内部产生了变形。在图6（a)中，CHM、FT、IT、LMLC、PCA、RBD、RC、SF 算法，同质的背景区域出现了虚化不足的离散清晰带状像素团，而显著目标区域也受到背景虚化的影响，DSR和本文算法效果较好，但查看图像细节，DSR算法在目标边缘外仍存在背景虚化不足的离散点区域，而本文算法物景分离较为彻底。在图例6(b)中，图像整体颜色特征对比度不够明显，全部算法对目标凸显的程度都不是特别的高。可以看出，除本文算法和DSR算法外，其他所有算法得到的结果都出现了图像显著目标丢失，整体上大面积虚化，不能较为完整地突出目标的情况。本文算法与DSR 算法相比，目标则相对的更加完整，查看图像细节可知本文算法在目标边缘处的效果优于DSR算法的结果。实验结果说明，显著性检测算法可以从整体上改善图像主题从整体分离的不足，进而提升图像品质。从复杂自然背景图像物景分离实验结果可以看出，本文算法在完整凸显图像显著目标，彻底虚化同质背景区域的性能优于其他对比的算法，也从侧面表明了本文算法针对复杂背景图像，除能够更加完整一致地提取显著目标区域外，对于同

![](images/55a2b23cd68788544b59c3616f76f1f6725aeb1443ebb850ec1d2b83ba3d6f1e.jpg)  
图6物景分离效果

质化背景还能够进行更好的抑制，算法性能相比于其他算法有明显的优势。

# 3 结束语

本文较为新颖地将能量方程应用于稀疏重构误差前景先验图的优化，既不同于聚类算法显著性传播，也不同于利用能量函数进行两次排序。为更好地抑制背景，利用已有的边界先验知识构造新的能量方程，使优化后的显著图像在区域平滑，边界不连续的同时，背景区域也得到更强的抑制。在后处理中基于背景已经得到较好的抑制，提出用指数函数突出前景区域的方法，使得前景区域更加均匀一致高亮。将本文提出的方法与所主要参考的两种方法，以及其他多种共11种显著性算法在两个大型数据集上进行实验对比，综合视觉效果、五个客观评价指标的对比，以及一个实际应用示例表明，本文提出的稀疏重构与能量方程优化的算法是有效的，面对各种复杂背景图像时能够更加精准的分离前景与背景，背景错误凸显的情况降低，对前景目标的提取更加的精确完整，算法鲁棒性好，综合性能有所提升，具有一定的使用价值。

# 参考文献：

[1]Zheng Liang,Wang Shengjin,Liu Ziqion, et al. Fast image retrieval: query pruning and early termination [J].IEEE Trans on Multimedia,2015,17 (5):

648-659.

[2]Liu Zhi,Shi Ran，Shen Liquan，et al.Unsupervised salient object segmentation based on kernel density estimation and two-phase graph cut [J].IEEE Trans on Multimedia,2012,14(4):1275-1289.   
[3]Shen Liquan,Liu Zhi,Zhang Zhaoyang.A novel H. 264 rate control algorithm with consideration of visual attention [J].Multimedia Tools & Applications,2013,63 (3): 709-727.   
[4]Chen Zhihui,Wang Hanzi, Zhang Liming,et al.Visual saliency detection based on homology similarity and an experimental evaluation [J].Journal of Visual Communication & Image Representation,2016,40 (Part A):251-264.   
[5]Lie Maiko,Borba GB,Neto HV,et al. Fast saliency detection using sparse random color samples and joint upsampling [C]// Proc of SIBGRAPI Conference on Graphics,Patterns and Images.Sao Paulo,Brazil: IEEE Computer Society,2017:217-224.   
[6]郑重，姚婷婷，孙永宣，等．基于高层颜色语义名称的显著性检测 [J/OL].计算机应用研究,2018,35,(6):1-6 [2018-03-14].http://kns.cnki. net/kcms/detail/51.1196.TP.20170614.1351.164.html.(Zheng Zhong, Yao Tingting,Sun Yongxuan,et al. Saliency detection based on high-level color semantic names [J/OL].Application Research of Computers.2018,35 (6):1-6 [2018-03-14]. http://kns.cnki．net/kcms/detail/51．1196.TP. 20170614.1351.164. html.)   
[7]IttiL,Koch C,Niebur E.Amodel of saliency-based visual attention for rapid

scene analysis [J].IEEE Trans on Pattern Analysis & Machine Intelligence, 1998,20 (11): 1254-1259.

[8]Li Xi, Li Yao,Shen Chunhua,et al.Contextual hypergraph modeling for salient object detection [C]// Proc of IEEE International Conference on Computer Vision. Sydney,Australia: IEEE Computer Society,2014:3328- 3335.   
[9]Xie Yulin,Lu Huchuan, Yang MH.Bayesian saliency via low and mid level cues [J].IEEE Trans on Image Processing APublication of the IEEE Signal Processing Society,2013,22 (5): 1689-1698.   
[10]Achanta R,Hemami S,Estrada F,et al. Frequency-tuned salient region detection [Cl//Proc of IEEE Conference on Computer Vision and Patern Recognition.Miami,FL,USA: IEEE Xplore,2009:1597-1604.   
[11] Ran M,Tal A,Zelnik-Manor L.What makes a patch distinct?[C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.Portland, OR,USA:IEEE Xplore,2013:1139-1146.   
[12]Hornung A,Pritch Y,Krahenbuhl P,et al. Saliency filters:contrast based filtering for salient region detection [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.Providence,Riusa:ACM Press, 2012: 733-740.   
[13] Cheng Mingming,Mitra NJ,Huang Xiaolei,et al.Global contrast based salient region detection [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2015,37(3): 569-582   
[14] Li Xiaohui,Lu Huchuan,Zhang Lihe,et al. Saliency detection via dense and sparse reconstruction [C]// Proc of IEEE International Conference on Computer Vision.Sydney,Australia: IEEE Computer Society,2013:2976- 2983.

[15] Yang Chuan,Zhang Lihe,Lu Huchuan,et al. Saliency detection via graphbased manifold ranking [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition. Portland, OR,USA: IEEE Computer Societys, 2013:3166-3173.

[16] Zhu Wangjiang,Liang Shuang,Wei Yichen,et al.Saliency optimization from robust background detection [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.Portland,OR,USA:IEEE Computer Society,2014: 2814-2821.

[17]Achanta R, ShajiA,SmithK,et al. SLIC superpixels compared to state-ofthe-art superpixel methods [J].IEEE Trans on Pattern Analysis& Machine Intelligence,2012,34(11): 2274-2282.

[18] Zhang Geng,Yuan Zejian,Liu Yuehu,et al.Video object segmentation by integrating trajectories from points and regions [J].Multimedia Tools & Applications,2015,74 (21): 9665-9696.

[19]崔丽群，吴晓冬，赵越．一种基于CRF-MR的自顶向下显著性目标检测 方法[J/OL].计算机应用研究,2018,35(7):1-2[2018-03-14].http://kns. cnki. net/kcms/detail/51.1196.TP.20170727.2120.114. html. (Cui Liqun, Wu Xiaodong,Zhao Yue.Top-down saliency target detection dased on CRFMR[J/OL].Application Research of Computers.2018,35(7): 1-2 [2018- 03-14].http://ns.cnki. net/kcms/detail/51.1196.TP.20170727.2120.114. html.)

[20]张巧荣．利用背景先验的显著性检测算法[J].中国图象图形学报， 2016,21(2): 165-173.(Zhang Qiaorong.Saliency detection algorithm based on background prior[J]. Journal of Image & GRAPHICS.2016,21(2): 165- 173.)

[21]Borji A,Cheng Mingming,Jiang Huaizu,et al. Salient object detection: a benchmark[J].IEEE Trans on Image ProcessingAPublication of the IEEE Signal Processing Society,2015,24(12): 5706.