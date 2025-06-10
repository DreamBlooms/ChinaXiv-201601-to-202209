# 基于K-均值聚类的彩色图像质量评价及优化

吴明明，陈勇，房昊

(重庆邮电大学 工业物联网与网络化控制教育部重点实验室，重庆 400065)

摘要：针对彩色图像质量无法实时评价及优化的问题，提出了基于K-均值聚类的彩色图像质量评价及优化算法。该算法首先利用K-均值聚类的方式构建样本数据集；然后通过待评价图像与聚类数据集之间的相似性来构建特征集；之后再将待优化图像与聚类数据集之间进行融合，对融合后的矩阵进行PCA变换实现了图像质量的优化;通过实验证明，所提评价算法与人眼主观视觉具有较好的一致性；同时，还能通过评价结果实现图像质量的自适应优化。

关键词：图像质量评价；K均值聚类；主成分分析；图像优化 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.04.0334

# Color image quality assessment and optimization based on K-mean clustering

Wu Mingming, Chen Yong, Fang Hao (KeyLaboratory of Industrial Internet of Thing & Network Control，MOE，Chongqing University of Posts& Telecommunications, Chongqing 40o065, China)

Abstract:In view of the problem that thecolor imagequalitycan’t beevaluatedandoptimized inreal time,this paper proposedacolor image qualityassessment and optimization method based on K-means clustering.This algorithm used K-means clustering tobuildthesample set,andsetupfeature sets bythe similaritybetweenthe imageand theclusterdataset. Then,it fusedthe image withtheclusterdatasetandoptimizedthequalityofthe image byprincipal component analysis (PCA）transformation of the fused matrix.Experiments shows that the assessment algorithm has good consistency with humansubjective vision,andatthesame time,itcan alsoachieveadaptive optimizationofimagequalitythrough assessment results.

Key words: image quality assessment (IQA); K-mean clustering; principal component analysis(PCA); image optimization

# 0 引言

由于图像在处理、传输和存储过程中会产生不同类型、不同程度的降质，致使最终的成像出现一定的失真，严重妨碍了图像的理解和分析[1]。因此设计一种量化失真程度和等级的无参考图像质量评价方法，是图像评价领域极其重要且亟待解决的问题[2]。

图像质量评价可分为三大类：第一类是全参考图像质量评价（fullreferenceIQA，FR-IQA）。该类方法需要衡量降质图像与未失真图像间的相似度来衡量图像好坏。最具代表性的全参考图像质量评价方法是SSIM[3]和VIF[4]，这些方法都符合人眼视觉感知对图像质量的判断。第二类是半参考图像质量评价（reducedreferenceIQA，RR-IQA）。该类方法仅需部分信息即可。第三类是无参考图像质量评价（noreferenceIQA，NR-IQA）。该类评价因不需要要任何参考图像，更符合实际使用情况，故引起非常广泛的关注。不难发现，现阶段关于彩色

图像的评价较少。

现有的彩色图像评价方法大多是：首先对彩色图像分解成不同的颜色通道，再用灰度图像的评价方法处理每个颜色通道；然后为每个通道赋予不同的权重；最后联合求得最终的评价结果。如Seghir等人[5在YIQ空间内对图像的Y通道提取边缘的相似度，对I和Q通道计算像素点间信息相似程度，经融合后得到图像质量评价值。Samani 等人[提出了一个基于DCT 变化域的彩色图像评价算法，将图像在YCbCr空间内分为亮度和色度两部分，将每部分图像划分为不重叠的图像块并对其提取DCT变换系数，根据系数与失真程度的变化关系对图像进质量评价。He等人[7计算图像LAB空间中每一个通道的保真度，然后最后将三个通道的结果融合。Lee等人[8将图像变换至CIELAB感知空间后分为亮度、色调与色度三部分，利用每部分的角度、均值、标准差等构造评价测度。然而该类方法难以确定最佳权重值。针对这一问题，文献[9」提出了一个通用的无参考彩色图像质量评价方法CQE，该方法固定权重后再从色度、锐利度和对比度三个方面进行评价。在此基础上，刘建磊[10]在 CQE 方法的基础上提取了斜坡边缘的锐利度局部特征和对比度局部特征，提出了基于局部特征的无参考彩色图像质量评价。闻武等人[1从亮度和色度两方面分别找到对应的直方图统计特征并直接相加评价，提出一种基于色彩特征的彩色图像质量评价方法。

综合可知，目前的彩色图像质量评价存在的不足，以及对图像质量自适应优化的缺少，对此本文提出了一种基于K均值聚类的无参考彩色图像质量评价及优化方法。该方法在构建聚类样本的基础上实现图像质量的自适应优化，实际应用广泛。

# 1 图像预处理

从LIVE图像数据库中选取16幅不同场景和不同纹理的无失真彩色图像，作为原始训练样本。由于彩色图像包含R、G、B三个颜色分量，所以分别对各个颜色分量进行分块处理，分解成尺度为 $d { \times } d$ 的互不重叠图像块。

在像素域中，图像的分布可由像素间的相关性来体现。为了描述像素间的相关性，设图像块的块点为 $x _ { c }$ ，而相距为 $d$ 的像素点有 $\left( x _ { 1 } , x _ { 2 } , \cdots , x _ { p } \right)$ ，则该图像块的像素相关性为

$$
X = \left( x _ { 1 } - x _ { c } , x _ { 2 } - x _ { c } , \cdots x _ { n } - x _ { c } \right) ^ { T }
$$

由于像素相关性符合人眼非线性感知特性[12]，所以图像块的局部特征为

$$
z = s i g n ( X ) \cdot \log \left( \left| X \right| + 1 \right)
$$

通过式（2）可将图像块以向量的形式表示。然后利用利用主成分分析（PCA）法[13]对训练集的图像块进行白化，可消除图像块的冗余信息。其数学表达式为

$$
z _ { P C A w h i t e , i } = \frac { z _ { i } } { \sqrt { \lambda _ { i } + C } }
$$

$$
\lambda _ { i } = \frac { 1 } { m } \sum _ { 1 } ^ { m } { \left( z ^ { i } \right) \left( z ^ { i } \right) ^ { T } }
$$

其中： $x _ { i }$ 是原图像块的特征； $x _ { P C A w h i t e , i }$ 是白化后的图像块特征； $\lambda _ { i }$ 是PCA变换矩； $C$ 是避免分母为0时的一个小常数。依次对每个图像块都进行上述操作，并放入到训练样本集U中，（204号 $U = \left\{ z _ { 1 } , z _ { 2 } , \cdots , z _ { m } \right\} _ { \mathrm { { c } } }$

# 2 K-均值聚类

K-均值聚类算法是无监督分类中的一种自适应搜索算法[14]。其实质是通过反复迭代寻找K个最佳的聚类中心，把全部样本划分为 $\mathrm { ~  ~ K ~ }$ 类，使得全部样本到其所属类的类中心的欧氏距离之和最小[15]。

在已知 $U = \bigl \{ z _ { 1 } , z _ { 2 } , \cdots , z _ { m } \bigr \}$ 的情况下，按照 K-均值聚类的思路将 $\mathrm { ~ m ~ }$ 个图像块样本划分到K个簇心中，构成数据集

$S = \left\{ s _ { 1 } , s _ { 2 } , \cdots s _ { K } \right\}$ 。若划分给某一聚类中心的图像块样本有 $n$ 个，则样本与中心之间的欧式距离为

$$
D ( z _ { i } , \sigma _ { k } ) = \sqrt { \sum _ { j = 1 } ^ { n } \left( z _ { i , j } - \sigma _ { k } \right) ^ { 2 } }
$$

其中： $\sigma _ { k }$ 是聚类中心。由此可知，要使式(5)取得最小值，则需要取该类子集 $s _ { k }$ 中所有样本点的平均数值作为类中心 $\sigma _ { k }$ □K-均值聚类的具体步骤如下：

a)初始化。已知 $U = \bigl \{ z _ { 1 } , z _ { 2 } , \cdots , z _ { m } \bigr \}$ ， $s$ 为聚类的数据集,有K个初始簇心。

b)分配。按照式（5）将 $\mathrm { ~ \tt ~ U ~ }$ 中的每一个 $z _ { i }$ 分配到离其最近的簇心。

c)计算。根据 $D ( z _ { i } , \sigma _ { k } )$ 计算均值，并使该均值作新的簇心。

d)判断。判断所有的聚类中心是否有更新变化，如果有则跳到步骤b)；反之则结束搜索，输出聚类数据集$S = \left\{ s _ { 1 } , s _ { 2 } , \cdots s _ { K } \right\}$

聚类后部分数据的效果示意图如图1所示。

![](images/cd20124f0292cad2e5de2217428fd8b6b4777c5ff54073e1c70ada301a2db581.jpg)  
图1聚类后部分数据的效果示意图

# 3 图像评价特征提取

将待评价彩色图像进行如文中第1章相同的预处理方法，得到每个颜色分量的图像块集向量，即

$$
X _ { c } ^ { t } = \left. \boldsymbol { x } _ { c , 1 } ^ { t } , \boldsymbol { x } _ { c , 2 } ^ { t } , \cdots \boldsymbol { x } _ { c , m } ^ { t } \right.
$$

其中： $c \in \left\{ R , G , B \right\}$ ； $\boldsymbol { x } _ { i } ^ { t }$ 是该颜色通道内的第 $i$ 个图像块,$i = 1 , 2 , \cdots m$ 。

然后利用式（5）来计算图像块与 $s$ 中原子间的最小欧氏距离，即

$$
y _ { c , i } = \operatorname* { m i n } _ { x _ { c , i } \in X _ { c } , s _ { j } \in S } \left\{ x _ { c , i } \cdot s _ { j } \right\} \ \ 1 \leq j \leq K
$$

其中： $x _ { c , i } \cdot s _ { j }$ 表示 $x _ { c , i }$ 与 $s$ 第 $j$ 个原子间的欧式距离。将所有图像块求得的结果汇总，用一个一维特征向量来表示图像特征，即

$$
Y _ { c } = \left\lfloor y _ { c , 1 } , y _ { c , 2 } , \cdots y _ { c , m } \right\rfloor
$$

由于该特征向量维度过高，为了更简洁直观地表现出图像失真特性，将该特征向量进行特征池化。具体是按照升序的形式进行排列，并筛选特征池中 $6 0 \%$ 的数据，其概率分布直方图如图2所示。图中是以LIVE 图像数据库中的“Womanhat”为示例，选取原始未失真图像和对应五种不同失真图像，包括JPEG 压缩失真、JPEG200 压缩失真（JP2K）、FastFading 失真（FF）、高斯模糊失真（GB）和白噪声失真（WN）。

![](images/8a686be8b8fcf1bf19ef4bc0861ad1242b12f5dbafcfb0905291f00d07ae6475.jpg)  
图2原始图像及5种失真的概率统计图

从图2中可以直观地看到，相较于原始图像的概率折线图，五种失真均出现不同程度的变化，其中以WN失真最为明显，其余四种失真虽然均低于原始图像且两两互不相同，因此本文评价特征可以有效地用于图像评价。为了便于计算，本文选择一维特征向量的平均值、方差、偏斜度和峰度这四个特征来表征彩色图像的质量评价特征。

$$
f = \big ( m e a n \big ( Y _ { c } \big ) , \mathrm { v a r } \big ( Y _ { c } \big ) , s k e w \big ( Y _ { c } \big ) , k u r \big ( Y _ { c } \big ) \big )
$$

彩色图像共有3个颜色分量，故最终可得到12个特征值。最后利用支持向量回归(support vector regression，SVR)[16的思想应用到图像质量的评价中，选用基于支持向量机(SVM)的综合性软件库LIBSVM[17]用于预测模型。

# 4 图像优化

# 4.1 图像预处理

对一幅待优化的彩色失真图像，失真会同时出现在R、G、B三个颜色分量中，故本节将分别从三个颜色分量中进行展开。由于三个颜色分量的优化方法相同，所以本节优化方法仅从R颜色分量中展开。首先，对R颜色分量进行对数变换，以使其符合人眼非线性感知特性。其数学表达式为

$$
X _ { R } ( i , j ) = \log \Bigl ( I _ { R } ( i , j ) \cdot 1 0 ^ { 6 } + 1 \Bigr )
$$

其中： $( i , j )$ 表示图像在该点的像素。

然后，按照 $d \times d$ 大小，重叠2个尺度的方式进行分块。分块后的图像块用一个集合 $x _ { c }$ 来表示，并计算该图像块集合$X$ 的像素平均值，用 $M$ 来表示。两者相减可以求得图像块的结构信息：

$$
G = X - o \cdot M
$$

其中： $\mathbf { \xi } _ { o }$ 是一个维度与 $X$ 相同的全1矩阵。这主要是因为噪声常出现在图像的高频部分，所以式（11）可以有效地得到包含图像噪声的高频信息。该高频信息中除了噪声外还有图像自身的结构信息，故如何在保留结构信息的基础上去除噪声，这是本节需要解决的问题。

# 4.2 聚类和 PCA变换

对图像的结构信息 $G$ ，本文按照欧氏距离将与 $G$ 相似的数据集原子，并构建成一个协方差矩阵，记为 $\Phi$ 。并将半正定协方差矩阵 $\Phi$ 进行特征分解。其最大特征值相关的特征向量能够表示该簇中最重要的共同结构，故该特征矩阵可看做是一个主成分分析（PCA）变换矩阵。具体的数学表达式如下：

$$
\Phi = Q \Lambda Q ^ { - 1 }
$$

$$
\boldsymbol { P } = \boldsymbol { Q } ^ { T }
$$

其中：矩阵 $\boldsymbol { Q }$ 由 $\Phi$ 的特征向量构成； $P$ 表示主成分分析（PCA）变换矩阵。然后将PCA矩阵与 $G$ 相结合，即

$$
y = P \cdot \overline { { x } } _ { c }
$$

式（14）变换后仅将图像的结构信息放大，故 $y$ 中的数值较大的是图像的结构信息，而较小的是图像的噪声等干扰信息。对 $y$ 中数值较大的进行保持或增强，并抑制后面的噪声干扰，可实现有效的图像去噪和增强。设用参数 $h$ 来控制噪声的去噪程度，去噪参数 $h$ 的取值为 $0 < h < 1$ ，且当 $h \geq 1$ 时图像会出现模糊的情况。具体公式如下：

$$
y = { \left\{ \begin{array} { l l } { y \cdot \left| y \right| } & { , \quad \left| y \right| \geq { \big ( } { \mathrm { m a x } } { \big | } y { \big | } \times h { \big ) } } \\ { y \cdot { \big ( } { \mathrm { m a x } } { \big | } y { \big | } \times h { \big ) } , } & { \left| y \right| < { \big ( } { \mathrm { m a x } } { \big | } y { \big | } \times h { \big ) } } \end{array} \right. }
$$

然后采用S型曲线中的arctan函数对 $y$ 进行调整，即

$$
y ^ { a } = { \frac { 1 . 6 } { \pi } } \cdot \arctan ( a \cdot y )
$$

根据文献[18]可知参数 $a$ 是细节增强参数，增强参数a 的取值是 $a \geq 1$ ，当 $a > 1$ 时实现图像细节增强， $a = 1$ 时图像不变化，而 $a < 1$ 时会使图像更加模糊。最后，通过与最大特征值相关的特征向量矩阵 $\boldsymbol { Q }$ 想成，可得到优化后的图像，即

$$
X _ { R } = Q \cdot y ^ { a } + o \cdot M
$$

经过上述变换，可通过控制参数 $h$ 或者 $a$ 实现图像去噪和增强等功能。

# 5 实验结果与分析

# 5.1图像评价实验结果分析

图像评价实验主要采用LIVE图像库。该库有29幅原始图像和经过五种常见失真的图像。其中JPEG2000压缩失真图像

227幅、JPEG压缩失真图像233幅、加性白噪声WN图像174幅、高斯模糊失真GB 图像174幅、快衰弱FF 失真图像145幅，共计953幅，并且有对应的人类主观质量评价DMOS值。通过借助经典的四种质量评价指标对算法性能进行评判：CC、SROCC、KROCC和RMSE。评价分值与主观一致性越强，则CC、SROCC与KROCC的值越接近1，说明算法预测越准确；而RMSE则正好相反，值越小说明算法性能越好。为了保证实验的公平性，随机选择每种类型的 $8 0 \%$ 作为训练对象， $20 \%$ 作为测试对象，并进行1000次的迭代实验。在LIVE 数据库中各失真类型的质量评价结果如表1所示。

表1LIVE数据库中各失真类型的评价指标  

<html><body><table><tr><td>类型</td><td>CC</td><td>SROCC</td><td>RMSE</td><td>KROCC</td></tr><tr><td>JPEG</td><td>0.9580</td><td>0.9470</td><td>7.3246</td><td>0.8392</td></tr><tr><td>JPEG2000</td><td>0.9272</td><td>0.9188</td><td>8.8997</td><td>0.7630</td></tr><tr><td>FF</td><td>0.9128</td><td>0.8902</td><td>7.2160</td><td>0.7563</td></tr><tr><td>GBLUR</td><td>0.9478</td><td>0.9359</td><td>7.0585</td><td>0.8280</td></tr><tr><td>WN</td><td>0.9898</td><td>0.9862</td><td>4.5204</td><td>0.9243</td></tr><tr><td>ALL</td><td>0.9516</td><td>0.9531</td><td>7.7230</td><td>0.8251</td></tr></table></body></html>

并将本文算法和当前主流的全参考（FR）和无参考（NR）方法进行了对比测试，选择CC和SROCC这两个指标的结果做对照。其中，PSNR[19]、SSIM[3]和VIF[4]为全参考评价方法;而GSCDM[5]、BRISQUE[20]、CQE[9]和BCIQBCC[11]为具有代表性的无参考彩色评价方法。表2和3为1000次迭代测试后评价指标。

表2LIVE 数据库中各IQA算法CC 的中值(1000 次)  

<html><body><table><tr><td>algorithm</td><td>JP2K</td><td>JPEG</td><td>Gblur</td><td>FF</td><td>WN</td><td>ALL</td></tr><tr><td>PSNR</td><td>0.8762</td><td>0.9029</td><td>0.7801</td><td>0.8795</td><td>0.9173</td><td>0.8592</td></tr><tr><td>SSIM</td><td>0.9405</td><td>0.9462</td><td>0.9004</td><td>0.9014</td><td>0.9805</td><td>0.9366</td></tr><tr><td>VIF</td><td>0.9711</td><td>0.9817</td><td>0.9743</td><td>0.9696</td><td>0.9931</td><td>0.9524</td></tr><tr><td>GSCDM</td><td>0.9486</td><td>0.9611</td><td>0.9293</td><td>0.9328</td><td>0.9738</td><td>0.9578</td></tr><tr><td>BRISQUE</td><td>0.9229</td><td>0.9724</td><td>0.9506</td><td>0.9093</td><td>0.9851</td><td>0.9424</td></tr><tr><td>CQE</td><td>0.9170</td><td>0.9364</td><td>0.9345</td><td>0.8928</td><td>0.9573</td><td>0.9047</td></tr><tr><td>BCIQBCC</td><td>0.9301</td><td>0.9749</td><td>0.9395</td><td>0.9311</td><td>0.9855</td><td>0.9492</td></tr><tr><td>本文方法</td><td>0.9372</td><td>0.9736</td><td>0.9580</td><td>0.9118</td><td>0.9749</td><td>0.9516</td></tr></table></body></html>

表3LIVE 数据库中各IQA 算法 SROCC 的中值(1000 次)  

<html><body><table><tr><td>Algorithm</td><td>JP2K</td><td>JPEG</td><td>Gblur</td><td>FF</td><td>WN</td><td>ALL</td></tr><tr><td>PSNR</td><td>0.8646</td><td>0.8831</td><td>0.7515</td><td>0.8736</td><td>0.9410</td><td>0.8636</td></tr><tr><td>SSIM</td><td>0.9389</td><td>0.9466</td><td>0.9046</td><td>0.9093</td><td>0.9635</td><td>0.9329</td></tr><tr><td>VIF</td><td>0.9735</td><td>0.9813</td><td>0.9722</td><td>0.9644</td><td>0.9892</td><td>0.9678</td></tr><tr><td>GSCDM</td><td>0.9551</td><td>0.9767</td><td>0.9258</td><td>0.9095</td><td>0.9764</td><td>0.9603</td></tr><tr><td>BRISQUE</td><td>0.9139</td><td>0.9647</td><td>0.9511</td><td>0.8768</td><td>0.9786</td><td>0.9304</td></tr><tr><td>CQE</td><td>0.9162</td><td>0.9582</td><td>0.9261</td><td>0.8794</td><td>0.9562</td><td>0.9135</td></tr><tr><td>BCIQBCC</td><td>0.9371</td><td>0.9741</td><td>0.9405</td><td>0.9883</td><td>0.9239</td><td>0.9516</td></tr><tr><td>本文方法</td><td>0.9454</td><td>0.9601</td><td>0.9595</td><td>0.9079</td><td>0.9746</td><td>0.9531</td></tr></table></body></html>

分析表2和3中可知，对比无参考彩色评价方法(如

BRISQUE、CQE和BCIQCC），本文算法的综合评价性能佳，并能比肩主流的全参考评价方法，其结果也很相近。实验结果证明了本文方法的有效性。

# 5.2图像优化实验结果分析

图像优化实验主要从LIVE库选择高斯模糊（GB）图像和白噪声（WN）图像作为实验测试图像。在图像增强时令噪声控制参数 $\mathrm { { h } = 0 . 0 0 1 }$ ，而在图像去噪时令增强控制参数 $\mathsf { a } { = } 1$ 。具体的实验结果见图3、4。

![](images/61b9cc40c56ee69951d98ecdab7169446efdb98c6789aad577f3d2e7417cfed5.jpg)  
图3模糊图像的增强图

![](images/12a42ea65f1f29a5f0b3087bba171edbc58cf0494fa9e15143efbc529db17c4e.jpg)  
图4含噪图像及去噪图

从图3可以明显地看出，本文算法有效地实现了图像去模糊的增强效果，且不同增强参数 $a$ 会有不同的增强效果。但随着参数为 $a$ 的变大，会出现过度图像锐化的情况。图4也出现了相同的情况，随着参数 $h$ 的增大会出现模糊现象。为了客观地反映本文算法对图像的优化效果，选择PSNR和SSIM算法作为评判依据。其中PSNR算法侧重于检验图像的去噪能力，其值越高说明去噪效果越好；而SSIM算法则倾向于检验图像的结构增强效果，其值接近1表明增强效果越好。从表4、5可知，图3的图像是PSNR值近似相等而SSIM值不相同，而图4的图像是SSIM近似相等而PSNR值不同。

表4客观评价图3的优化效果  

<html><body><table><tr><td>指标</td><td>图3(a)</td><td>图3(a1)</td><td>图3(a2)</td><td>图3(b)</td><td>图3(b1)</td><td>图3(b2)</td></tr><tr><td>PSNR</td><td>26.7868</td><td>26.7872</td><td>26.7863</td><td>27.4912</td><td>27.4525</td><td>27.1054</td></tr><tr><td>SSIM</td><td>0.9588</td><td>0.9996</td><td>0.9948</td><td>0.9476</td><td>0.9985</td><td>0.9955</td></tr><tr><td></td><td></td><td>表5</td><td>客观评价图4的优化效果</td><td></td><td></td><td></td></tr><tr><td>指标</td><td>图4(a)</td><td>图4(a1)</td><td>图4(a2)</td><td>图4(b)</td><td>图4(b1)</td><td>图4(b2)</td></tr><tr><td>PSNRRR</td><td>19.8825</td><td>26.9946</td><td>23.2704</td><td>16.2385</td><td>29.1941</td><td>22.4508</td></tr><tr><td>SSIM</td><td>0.9968</td><td>0.9999</td><td>0.9985</td><td>0.9862</td><td>0.9995</td><td>0.9987</td></tr><tr><td></td><td>表6</td><td></td><td></td><td></td><td>LIVE 数据库中失真类型的识别准确率(100 次)</td><td></td></tr><tr><td>类型</td><td>JP2K</td><td>JPEG</td><td>GBLUR</td><td>FF</td><td>WN</td><td>ALL</td></tr><tr><td>准确率</td><td>85.94%</td><td>98.15%</td><td>95.02%</td><td>88.26%</td><td>100%</td><td>92.95%</td></tr></table></body></html>

# 5.3 图像自适应优化

为了实现图像自适应优化，需要提前判断图像失真类型，故本文在提取图像评价特征的同时利用LIBSVM建立图像失真类型识别模型。在LIVE 数据库进行100次迭代测试，将分类准确率的结果取均值作为识别结果，如表6所示。从表6可知，本文利用评价特征建立的失真类型识别模型具有较高的准确率，能准确地区分判别噪声图像和模糊图像。在此基础上，可以实现自主选择去噪参数还是增强参数。

从5.2节可知，选择合适的参数可以实现最佳的优化效，利用本文所提出的图像评价算法来选择最佳的优化参数就能实现图像的自适应优化。因此本文选择模糊图像如图3（d）为例，利用本文评价算法求得不同优化参数的优化图像的预测DMOS值，具体如图5所示。图5也证明了不同的优化参数会有不同的优化效果，而如何选择合适的优化参数又需要评价结果来辅助。故本文优化算法结合了图像失真类型识别模型和图像质量评价模型，可以实现失真图像的自适应优化，得到优化后的图像更接近人眼主观评价，并能再次干扰失真，具有强鲁棒性。

![](images/ea8e0b94139b7b8cb377598bfa42e41d976f891e27f536124fe1ccc4e7838746.jpg)  
图5不同参数h的优化图像的预测DMOS值

# 6 结束语

本文从K-均值聚类出发，提出了一种基于K-均值聚类的彩色图像质量评价及优化方法。该方法首先利用K-均值聚类的方式构建样本数据集；然后通过聚类数据集与待优化图像之间的相似性进行特征编码；之后再将待优化图像与聚类数据集之间进行融合，对融合后的矩阵经PCA变换后实现了图像质量的优化。通过实验证明，本文评价算法与人眼主观视觉具有较好的一致性；同时，还能通过评价结果实现图像质量的自适应优化。如何快速高效地通过评价来确定控制参数，是笔者下一步研究的重点。

# 参考文献：

[1]Manap R A, Shao L.Non-distortion-specific no-reference image quality assessment: a survey [J].Information Sciences,2015,301: 141-160.   
[2]褚江，陈强，杨曦晨．全参考图像质量评价综述[J].计算机应用研究， 2014,31(1): 13-22.(Chu Jiang, Chen Qiang, Yang Xichen.Review on full reference image quality assessment algorithms [J]. Application Research of Computers,2014,31(1): 13-22. )   
[3]Wang Zhou,Bovik A C, Sheikh HR,et al. Image quality assessment: from error visibilityto structural similarity[J]. IEEE Trans on Image Processing, 2004,13 (4): 600-612.   
[4]Sheikh HR,Bovik AC.Image information and visual quality [J]. IEEE Trans on Image Processing,2006,15 (2): 430-444.   
[5]Seghir Z A,Hachouf F. Image quality assessment scheme based on gradient similarity and color distortion [C]// Proc of the 12th International Symposium on Programming and Systems.[S.1.] : IEEE Press,2015:1-8.   
[6] Samani A,Panet K, Agaian S. TDMEC,a new measure for evaluating the image quality of color images acquired in vision systems [C]// Proc of IEEE International Conference on Technologies for Practical Robot Applications. [S.1.] : IEEE Press,2015:1-5.   
[7]He L,Gao X,Lu W,et al. Image quality assessment based on S-CIELAB model[J]. Signal,Image and Video Processing,2011,5 (3): 283-290.   
[8]Lee D,Plataniotis K N. Towards a ful-reference quality assessment for color images using directional statistics [J]. IEEE Trans on Image Processing,2015,24 (11): 3950-3965.   
[9]Paneta K, Gao C,Agaian S. No reference color image contrast and quality measures [J].IEEE Trans on Consumer Electronics,2013,59 (3): 643-651.   
[10]刘建磊．结合局部特征的无参考彩色图像质量评价[J]．光学 精密工 程,2016,24 (5): 1176-1184. (Liu Jianlei. No-reference color image quality assessment based on local features [J]. Optics and Precision Engineering, 2016,24 (5): 1176-1184. )   
[11]闻武，左凌轩．基于色彩特征的无参考彩色图像质量评价[J].计算机 科学,2017 (S1):151-156.(Wen Wu,Zuo Lingxuan.Blind color image quality assessment base on color characteristics [J]. Computer Science, 2017 (S1): 151-156.)

[12] Chen Y,Xiao X,Liu H,et al.Dynamic color image resolution compensation under low light [J].Optik-International Journal forLight and Electron Optics,2015,126 (6): 603-608.

[13]赵军，赵艳，杨勇，等．基于降维的堆积降噪自动编码机的表情识别方 法[J].重庆邮电大学学报：自然科学版，2016,28(6):844-848.(Zhao Jun,Zhao Yan,Yang Yong,et al.Facial expression recognition method based on stacked denoising auto-encoders and feature reduction [J]. Journal of Chongqing University of Posts and Telecommunications: Natural Science Edition,2016,28 (6): 844-848.)

[14]郑恩，林靖宇．基于图像质量约束的无序图像关键帧提取[J].计算机 工程,2017,43 (11): 210-215.(Zheng En,Lin Jingyu.Disordered image key frame extraction based on image quality constraint [J].Computer Engineering,2017,43(11): 210-215.)

[15]吴迪，刘伟峰，胡胜，等．基于Lab 空间的 K-均值聚类彩色图像分割 [J].电子科技,2017,30(10):29-32.(Wu Di,Liu Weifeng,Hu Sheng,et al.Color image segmentation using K-mean clustering based on Lab space [J].Electronic Science and Technology,2017,30 (10): 29-32.)

[16]WuF,YuE,YuP,et al.Modeling and prediction of the air permeability of fabrics based on the support vector machine [J].Journal of Testing and Evaluation,2016,45 (4): 1388-1395.

[17]王璐烽，刘辉元．基于机器学习的图像块效应盲评价算法[J].重庆邮 电大学学报：自然科学版，2014，26(6):856-860.(WangLufeng，Liu Huiyun.Blind evaluation of blocking artifacts in images based on machine learning[J]. Journalof ChongqingUniversityofPostsand Telecommunications:Natural Science Edition,2014,26 (6): 856-860.)

[18]Li H, Jia X,Zhang L. Clustering based content and color adaptive tone mapping [J]. Computer Vision and Image Understanding，2O18,168: 37-49.

[19]Lukas FXJ,Budrikis ZL.Picture quality prediction based ona visual model[J].IEEE Trans on Communications,1982,30(7):1679-1692

[20]卢鹏，林根巧，邹国良．基于信息熵和深度学习的无参考图像质量评价方法研究[J/OL].计算机应用研究，2018，35（12）．[2018-05-07].http://www.arocmag.com/article/02-2018-12-082.html.(Lu Peng，LinGenqiao,Zou Guoliang.Research on non-reference image qualityevaluation method based on information entropy and deep learning [J].Application Research of Computers，2018，35(12）．[2018-05-017].http://www.arocmag.com/article/02-2018-12-082.html.)