# 适用于迭代型去模糊算法的自适应迭代终止条件

江顺亮，姜尹楠，曾小霞，唐祎玲，徐少平(南昌大学 信息工程学院，南昌 330031)

摘要：由于缺乏有效的迭代终止条件(iterative stopping criterion，ISC)，目前大多数去模糊算法简单采用固定的迭代次数实现，存在着执行效率低、去模糊效果不够理想等问题。为此，提出一种基于残差图像(迭代过程中所获得的中间估计图像和模糊核卷积后与模糊图像之间的差值)的去模糊效果度量(deblurrng measure，DM)，并在该 DM度量的基础上设计了一种自适应的迭代终止条件(adaptive ISC，AISC)。将所提出的 AISC 迭代终止条件应用于经典的NCSR(nonlocallycentralized sparse representation）迭代型去模糊算法中。在均匀模糊、高斯模糊和运动模糊三种典型模糊失真类型下大量的实验数据表明，与采用固定迭代次数的原NCSR算法相比，采用自适应迭代条件后NCSR算法执行效率得到显著提升，且所复原图像在PSNR、SSIM和FSIM图像指标值上与原算法差别不大。

关键词：图像去模糊；执行效率；迭代终止条件；残差图像；去模糊效果度量 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.09.0920

# Adaptive iterative stopping criterion for deblurring algorithm

Jiang Shunliang, Jiang Yinnan, Zeng Xiaoxia, Tang Yilingm, Xu Shaoping† (School of Information Engineering,Nanchang University,Nanchang 33oo31,China)

Abstract:Currently，due tolack of efective iterative stopping criterion (ISC），mostof the IDalgorithmsareusually implementedwith fixed iterationsteps,leadingtotheloweficiencyandpoordeblurringresults.Therefore,thispaperproposed a debluring measure (DM)basedontheresidual image(the diference between the intermediate estimated image convoluted with blur kerneland blur image during each iterative step).Based onthe proposed DM metric,it designed and applied an adaptive iterative stopping criterion (AISC） to the clasic nonlocally centralized sparse representation (NCSR）.Extensive experiments onuniformblur,Gausian blurand motion blurshow that,compared with theoriginal NCSR algorithm using fixed iteration steps，the NCSR algorithm adopting AISC has an obvious advantages in terms of effciency and the reconstructed images have asimilar imagequality in terms of peak signal-to-noiseratio (PSNR),structural similarity(SSIM) and feature similarity (FSIM) .

Key Words: image deblurring; execution efficiency;iterative stopping criterion;residual image; deblurring measure

# 0 引言

图像模糊失真过程一般可以形式化的表示为

其中： $g$ 和 $f$ 分别是模糊图像(即观测图像)和原始图像； $h$ 是点扩散函数(point spread function,PSF)，通常称为退化函数； $^ *$ 为卷积运算符。图像去模糊是一个典型的求逆问题，主要基于观测到的模糊图像通过求解关于某个目标函数的最优值实现对原始无失真图像的最佳估计。由于图像去模糊问题属于典型的欠约束条件问题，得到了众多学者的关注并已经提出了很多图像去模糊(image deblurring)算法[l\~6]。其中，基于正则化的求解方法是一类比较常见和有效的解决方案。在基于正则化的去模糊算法中，主要利用原始图像 $f$ 的先验知识构造合适的正则项，并对求解的复原图像和退化函数进行正则化约束。其数学模型[1\~4]如式（2）所示。

$$
C _ { \lambda } ( f , h ) = \frac { 1 } { 2 } \Big \| g - f * h \Big \| _ { 2 } ^ { 2 } + \lambda \Phi ( x )
$$

其中：第一项为数据保真项； $\Phi ( x )$ 是正则项表示图像先验知识；

$\lambda$ 是正则化参数。求解式(2)中所定义的优化问题，全变分(totalvariant,TV)[5.6]一类方法因具备良好的边缘保持和抑制噪声的能力，得到了广泛的应用。但由于忽略了图像细节与结构特性，容易造成图像平坦区域产生阶梯效应(staircasingeffect)，所以许多改进的 TV 去模糊算法被提出来。近年来，受NLM(non-localmeans)降噪算法[7的启发，许多学者把图像的非局部自相似性引入到正则化方法中，提出了基于非局部正则化约束的去模糊算法，解决了基于TV 正则化去模糊算法中的不足[8.9]。在这些算法中，利用图像的非局部自相似性特性将传统的图像局部空间邻域概念扩展到更广义范围意义下的邻域，充分利用了图像中局部结构的相似性，在纹理和结构保持方面都有很大的改善。例如，Kheradmand等人[9]利用归一化图拉普拉斯操作符(normalized graph laplacian)作为正则项，充分发挥了空间自相似的特点。该算法通过内外两层迭代过程实现，在外部迭代中，基于先前估计来更新重计算相似性权重(similarityweights)，内部迭代使用共轭梯度法来更新最小化目标函数。最近，学者们把图像的非局部自相似性与稀疏性相结合，提出许多新的图像复原算法[10\~13]。例如，Zhang 等人[10]为了解决传统基于图像块的稀疏表示在算法执行效率和稀疏系数估计不准确的情况，提出了基于组稀疏表示的(group sparse reprentation, GSP)图像复原算法。该算法成功地把图像稀疏性与非局部自相似结合，并使用Bregman 分裂迭代(split bregman iteration,SBI)方法求解复原图像的最优估计；类似的，Wang 等人[提出基于迭代增量的GSP(group sparse regularization)正则化去模糊算法，运用在遥感图像去模糊上。该算法主要利用非负约束和稀疏约束以迭代方式更新对原始图像的估计；Liu 等人[12]在3D 转换域上提出了一种联合稀疏表示(joint sparse reprentation,JSR)算法。JSR 通过引入非局部的规则项，能有效刻画图像的非局部统计特征，相对现有的稀疏表示方法更为准确；Liu 算法在贝叶斯框架下使用 SBI迭代方法来求解关于原始未失真图像的最优解。Dong 等人[13]提出的 NCSR(nonlocally centralized sparse representation)算法把关于图像稀疏先验知识与非局部相似结合在一起，首先利用图像非局部重复的特性估计噪声图块的稀疏系数，然后采用迭代收缩图块稀疏系数的方法实现图像的复原，相比与大多数算法都有更好的复原效果。

目前，就基于正则化技术实现的各类去模糊算法而言，通常通过迭代方法来求解目标函数最优值实现对原图像的最佳估计[14]。然而由于缺乏判断迭代终止的条件，这些算法常常只能根据经验，采用固定的迭代次数来实现。这种实现方法存在着执行效率不高和去模糊效果未必最佳的问题。以NCSR 算法[13]为例，算法采用了内外两层循环，外循环设置迭代次数为6次，内层循环为120次，共有720次迭代。通过实验可以发现，NCSR算法采用固定的迭代次数的实现方法会导致以下两种情况：

a)执行效率不高。在某些时候，该算法在较少的迭代次数下就已达到了比较高的图像质量值。在后继的迭代中，图像质量值仅是缓慢上升，直到720次迭代完成所得到的图像质量值提升量很小(视觉上不易感觉到差别)。换句话来说，采用固定迭代次数的方法浪费了较多的执行时间，却没有大幅度提高去模糊化效果。

b)去模糊后的图像质量未必是最佳的。在某些时候，经过较少迭代步骤完成后，迭代中间过程产生的中间估计图像的质量值就达到了最佳。然后随着迭代次数的增加，图像质量值反而下降。

因此，上述两种情况表明需要研究一种迭代终止条件应用于以NCSR算法这类迭代型去模糊算法中，使得这些算法能够以少的执行代价获得最佳的去模糊化效果。

解决NCSR去模糊算法上述问题一个简单方法就是在迭代过程中利用无参考的图像质量评价算法(no-reference imagequalityassessment,NR-IQA)对每一步迭代产生的中间估计图像进行评价，根据评价值的高低决定迭代过程是否可以终止。但由于NR-IQA算法并非专门为去模糊算法而设计，其计算复杂度一般比较高。目前评价效果比较好的NR-IQA算法本身的执行时间比较长，大多达到秒的量级，有些甚至高达几十秒[15\~17]。如果在NCSR算法迭代求解过程中反复频繁调用NR-IQA算法实现获得最佳的去模糊图像的质量，将会导致去模糊算法本身的执行效率同时急剧下降。为此，本文不采用以去模糊算法迭代过程中所获得的中间估计图像为评价对象的常规做法，而是根据在迭代过程中中间估计图像和模糊核卷积后与模糊图像之间的差值图像(本文将差值图像称为残差图像)设计一种自适应的迭代终止条件(adaptive iterative stopping criterion,AISC)。具体地，基于残差图像中像素点之间亮度值差异大小定义了专用于去模糊算法的评价去模糊效果的度量(deblurring measure,DM),然后基于该DM度量设计了AISC自适应迭代终止条件。为验证AISC的实际效果，将所提出的AISC迭代终止条件应用于经典的NCSR算法中。在均匀模糊、高斯模糊和运动模糊典型模糊失真类型下大量的实验数据表明，与采用固定迭代次数的原算法相比，采用AISC迭代条件后NCSR算法所复原图像在PSNR、SSIM[18]和FSIM[19]图像指标值上比原算法相差不大，而执行效率则显著得到提升。

# 1 相关工作

# 1.1 NCSR 算法简介

在经典的NCSR[13]算法中，先基于给定的模糊图像本身在线构造字典，然后将模糊图像分解成图块并基于所学习的字典对每个图块进行稀疏编码，利用收缩(shrinkage)方法处理每个图块的稀疏系数值后，再按照上述方法的逆过程重构图像从而实现图像去模糊。其中，稀疏编码是核心技术，其任务是在给定字典情况下计算出图块的稀疏系数值。对于图像 $g \in \mathfrak { R } ^ { N }$ ，$f _ { i } = R _ { i } g$ 表示在像素点 $i$ 处提取大小为 ${ \sqrt { n } } \times { \sqrt { n } }$ 的图块，其中 $R _ { i }$ （204号是从 $g$ 中像素点 $i$ 处提取图块 $y _ { i }$ 的矩阵操作。给定字典$\phi \in \Re ^ { n \times m } , n \leq M$ ，从图像中提取的某个图块可稀疏表示为$g _ { i } = \phi \alpha _ { g , i }$ ，图像的去模糊问题通过求解如下的 $L _ { \mathrm { 1 } }$ 优化问题实现

$$
\begin{array} { r l } & { \operatorname* { m i n } _ { \alpha _ { i } } \sum _ { i = 1 } ^ { P } ( \left\| g _ { i } - \phi \alpha _ { i } \right\| _ { 2 } ^ { 2 } + \lambda \left\| \alpha _ { i } \right\| _ { 1 } ) } \end{array}
$$

其中： $P$ 是从图像 $g$ 中提取的图块总数； $\alpha _ { i }$ 相对于字典 $\phi$ 而言是指图块 $g _ { i }$ 的稀疏系数； $\lambda$ 表示正则化参数。图像 $g$ 可以通过稀疏系数集合 $\left\{ \alpha _ { g , i } \right\}$ 来表示。从集合 $\left\{ \alpha _ { g , i } \right\}$ 对图像 $g$ 进行重建是一个超定系统(over-determined system)问题，可采用最小二乘方法求解：

$$
f \approx ( \sum _ { i = 1 } ^ { N } R _ { i } ^ { T } R _ { i } ) ^ { - 1 } { \sum _ { i = 1 } ^ { N } } ( R _ { i } ^ { T } \phi \alpha _ { g , i } )
$$

为便于表示，式(5)可改写为

$$
\begin{array} { r } { g \approx \phi \circ \alpha _ { g } = ( \sum _ { i = 1 } ^ { N } ( R _ { i } ^ { T } \phi \alpha _ { g , i } ) ) } \end{array}
$$

其中： $\alpha _ { g }$ 表示所有 $\alpha _ { g , i }$ 的级联。这样式(4)可以写为

$$
\begin{array} { r } { \alpha _ { { \scriptscriptstyle f } } = \arg \operatorname* { m i n } _ { { \boldsymbol \alpha } } ( \left\| g _ { i } - \phi \circ { \boldsymbol \alpha } \right\| _ { 2 } ^ { 2 } + \lambda \| { \boldsymbol \alpha } \| _ { 1 } ) } \end{array}
$$

在 NCSR算法中，通过解决下面的最小化问题实现从 $g$ 估计出 $f$ ：

$$
\alpha _ { f } = \arg \operatorname* { m i n } _ { \alpha } ( \left\| g _ { i } - \phi \circ \alpha \right\| _ { 2 } ^ { 2 } + \lambda \sum _ { i } \left\| \alpha _ { i } - \beta _ { i } \right\| _ { p } )
$$

其中： $\lambda$ 是平衡保真度与稀疏项的参数； $\beta _ { i }$ 是未知关于稀疏系数 $\alpha _ { i }$ 的估计。NCSR算法应用于图像去模糊，主要依靠迭代过程求解式(8)。在每一步迭代步骤中都会产生关于原图像 $x$ 的估计值

$$
\hat { f } ^ { ( j + \big / 2 ) } = \hat { f } ^ { ( j ) } + \delta h ^ { T } ( g - h \hat { f } ^ { ( j ) } )
$$

其中： $\delta$ 是预定义的常量； $g$ 是模糊图像； $h$ 是模糊核； ${ \hat { \boldsymbol { f } } } ^ { ( j ) }$ 是第 $j$ 次迭代所估计的图像； $\hat { \boldsymbol f } ^ { ( j + \not \gamma _ { 2 } ) }$ 表示中间结果，将用于获得 $j + 1$ 步的稀疏编码。去模糊主要依靠收缩方法计算新的 $\alpha _ { i } ^ { j + 1 }$ 实现，定义如下：

$$
\alpha _ { i } ^ { j + 1 } = S _ { \tau } ( \alpha _ { i } ^ { j } - \beta _ { i } ^ { j } ) + \beta _ { i } ^ { j }
$$

式(10)中的 $S _ { \tau } ( \cdot )$ 是经典软阈值算子； $\boldsymbol { \tau }$ 是软阈值参数。在每次内层迭代中， $\alpha _ { i } ^ { j + 1 }$ 一旦获得，去模糊的中间图像就可以重建为

$$
\hat { f } ^ { ( j + 1 ) } = \phi \circ \alpha ^ { \left( j + 1 \right) }
$$

需要说明的是，在NCSR 算法中，固定地采用 $\hat { f } ^ { ( 7 2 0 ) }$ 作为原图像的最终估计值(即去模糊后的图像)。

# 1.2存在问题

在迭代次数的选择上，NCSR算法是以设置固定值的方式来处理的。然而各种图像的内容和模糊失真类型有着各自的特点，在算法中固定设置的720次迭代不能保证对不同内容的图像和各类失真都能够得到很好的去模糊效果。为了分析NCSR算法采用固定选代次数实现所产生的问题，采用常用测试图像Barbara(大小为 $2 5 6 ^ { * } 2 5 6 )$ 为例，对算法在均匀模糊、高斯模糊、运动模糊三种典型模糊失真下在720次迭代过程中图像的图像质量值PSNR、SSIM、FSIM的变化趋势。实验的参数设置中，尽量保证模糊类型和失真程度大小的全面性。在均匀模糊下，模糊核(Kermel size，简记K)大小设置为[55]、[1515]、[2525];高斯模糊参数设置为：模糊核大小K 设置为[55]、[99]、[1515]，标准偏差 Sigma(简记S)为1和3；运动模糊参数为：距离Length(简记L)为10、20、40，角度Angel(简记A)为0。表1数据记录了三种模糊类型下，NCSR 算法在某些关键迭代步骤上的图像质量值。从表1数据可以看出，图像质量值有两种变化趋势：a)情况A，图像质量值在前面较少的迭代次数时便达到峰值，在随后的迭代次数中，图像质量值一直下降；b)情况B，图像质量在迭代前期提升很快，在后期的迭代次数非常缓慢的上升。对于情况A来说，算法发生了过迭代的现象，过多的迭代不仅给算法造成了很大的时间开销，而且随着迭代次数的增加复原的图像质量越来越低；就情况B而言，算法在前面的迭代中图像质量值变化很大，有非常明显的提升，而后期次迭代中图像质量值变化缓慢，图像质量值变化不大(从人眼视觉观察角度)。总之，无论是对于上述哪种情况而言，需要自适应的设置迭代终止条件下从而保障NCSR算法在获得最佳的去模糊图像质量的同时具有令人满意的执行效率。

为了更为直观地反映复原图像随着迭代变化的趋势，图1分别列出了两种情况下Barbara图像的去模糊效果。其中图1(a)(b)反映的是上述变化趋势中的A情况。从图1(a)（b）(运动模糊 $_ { \mathrm { A = 0 , ~ L = 1 0 } }$ 可以发现，720次迭代去模糊后的图像(左图)明显较最佳质量值图像(右图)要模糊；图1(c)(d)反映的是上述变化趋势中的B情况，在图1(c)(d)(高斯模糊K=[1515], $\mathrm { S } { = } 3$ ）中，左图为720次迭代后获得的图像,右图为整个去模糊过程中最佳的图像(在迭代200次获得)。可以发现，两张图像的差别非常小，凭人眼无法辨别出差别。由此说明，NCSR算法需要添加一个迭代终止条件，在合理的迭代次数下实现完成效率和复原图像质量之间的平衡。

# 2 自适应选代终止条件

# 2.1残差图像

由上文可知,本文所指的残差图像是指在迭代过程中的中间估计图像和模糊核卷积后与模糊图像之间的差值图像。

$$
r = g - \hat { f } * h
$$

理论上讲，去模糊算法在刚开始进行迭代的过程中，由于对于原图像的估计不是很准确，这个时候残差图像 $r$ 中各个像素点之间在差异比较大(尤其是较难复原的图像边缘细节部分)随着迭代次数的逐渐增加，估计图像 $\hat { \boldsymbol f }$ 越来越准确，则 ${ \hat { f } } * h$ 越来越与失真图像 $g$ 近似，这样导致残差图像 $\cdot r$ 图像中各个像素点亮度值变小且趋于在0值附近变动,像素点亮度值之间的差异也趋于变小。以一张 $2 5 6 ^ { * } 2 5 6$ 大小的Barbara 图像为例，分别提取去模糊迭代过程中第1、10、20、50和720共5个迭代位置的残差图像，5个迭代位置的残差图像如图2所示(为便于视觉观察，亮度值已经规范化到[0255]间。限于篇幅，这里只给出运动模糊类型下( $\scriptstyle \mathbf { A = } 0 , \mathbf { L = } 1 0 )$ 的残差图像图，均匀模糊与高斯模糊情况类似)。

由图2可以看出，在迭代刚开始的第一步时，残差图像中明显看到能反映图像内容的关键边缘信息。到第20步的时候，尚能看到不明显的结构信息。之后，随着迭代次数的增加，残差图像像素点亮度值之间的差异越来越小。在迭代次数为50时，从视觉上已经无法观察出残差图像中有关于图像内容的信息，说明图像去模糊效果接近最优值。图3是上述5个迭代步骤中残差图像像素点亮度值对应的直方图。由图3可知，残差图像中亮度值的变化范围随着迭代次数增加，在逐渐收窄，说明中间估计图像在逐渐接近原图像。

表1Barbara图像去模糊过程中图像质量值变化趋势   

<html><body><table><tr><td>模糊类型</td><td>参数</td><td>评价标准</td><td>第1步</td><td>第10步</td><td>第20步</td><td>第50步</td><td>第720步</td><td>变化类型</td></tr><tr><td></td><td></td><td>PSNR</td><td>22.65</td><td>29.42</td><td>29.60</td><td>29.14</td><td>28.70</td><td>A</td></tr><tr><td rowspan="3">均匀模糊</td><td>K=[5 5]</td><td>SSIM</td><td>0.6127</td><td>0.8433</td><td>0.8303</td><td>0.8035</td><td>0.7856</td><td>A</td></tr><tr><td></td><td>FSIM</td><td>0.7472</td><td>0.9257</td><td>0.9243</td><td>0.9152</td><td>0.9075</td><td>A</td></tr><tr><td></td><td>PSNR</td><td>20.84</td><td>23.11</td><td>23.52</td><td>23.91</td><td>24.64</td><td>B</td></tr><tr><td>均匀模糊</td><td>K=[15 15]</td><td>SSIM</td><td>0.4554</td><td>0.6065</td><td>0.6296</td><td>0.6510</td><td>0.6878</td><td>B</td></tr><tr><td rowspan="3">均匀模糊</td><td></td><td>FSIM</td><td>0.6173</td><td>0.7603</td><td>0.7868</td><td>0.8082</td><td>0.8349</td><td>B</td></tr><tr><td></td><td>PSNR</td><td>19.30</td><td>21.72</td><td>22.14</td><td>22.64</td><td>23.67</td><td>A</td></tr><tr><td>K=[25 25]</td><td>SSIM</td><td>0.3871</td><td>0.5156</td><td>0.5387</td><td>0.5644</td><td>0.6211</td><td>B</td></tr><tr><td rowspan="3">高斯模糊</td><td></td><td>FSIM</td><td>0.5568</td><td>0.6696</td><td>0.6989</td><td>0.7270</td><td>0.7612</td><td>B</td></tr><tr><td></td><td>PSNR</td><td>22.99</td><td>28.70</td><td>29.01</td><td>28.18</td><td>25.98</td><td>A</td></tr><tr><td>K=[5 5] S=3</td><td>SSIM</td><td>0.6369</td><td>0.8292</td><td>0.8081</td><td>0.7612</td><td>0.6763</td><td>A</td></tr><tr><td rowspan="3"></td><td></td><td>FSIM</td><td>0.8025</td><td>0.9177</td><td>0.9141</td><td>0.8969</td><td>0.8622</td><td>A</td></tr><tr><td></td><td>PSNR</td><td>22.84</td><td>24.32</td><td>24.79</td><td>25.38</td><td>25.81</td><td>B</td></tr><tr><td>K=[9 9]</td><td>SSIM</td><td>0.5909</td><td>0.6877</td><td>0.7029</td><td>0.7072</td><td>0.6796</td><td>A</td></tr><tr><td rowspan="3">高斯模糊</td><td>S=3</td><td>FSIM</td><td>0.7216</td><td>0.8165</td><td>0.8355</td><td>0.8527</td><td>0.8522</td><td>A</td></tr><tr><td></td><td>PSNR</td><td>22.30</td><td>23.46</td><td>23.55</td><td></td><td></td><td>B</td></tr><tr><td>K=[15 15] SSIM</td><td></td><td></td><td></td><td></td><td>23.66</td><td>23.89</td><td></td></tr><tr><td rowspan="3">运动模糊</td><td>S=3</td><td></td><td>0.5571</td><td>0.6416</td><td>0.6483</td><td>0.6546</td><td>0.6639</td><td>B</td></tr><tr><td></td><td>FSIM</td><td>0.6886</td><td>0.7829</td><td>0.7908</td><td>0.7981</td><td>0.8087</td><td>B</td></tr><tr><td>A=0</td><td>PSNR</td><td>23.02</td><td>26.61</td><td>27.12</td><td>26.66</td><td>25.38</td><td>A</td></tr><tr><td rowspan="3"></td><td>L=10</td><td>SSIM</td><td>0.5943</td><td>0.7640</td><td>0.7486</td><td>0.7053</td><td>0.6560</td><td>A</td></tr><tr><td></td><td>FSIM</td><td>0.7655</td><td>0.8771</td><td>0.8780</td><td>0.8645</td><td>0.8448</td><td>A</td></tr><tr><td>A=0</td><td>PSNR</td><td>20.99</td><td>23.77</td><td>24.18</td><td>24.41</td><td>24.75</td><td>B</td></tr><tr><td rowspan="3">运动模糊</td><td>L=20</td><td>SSIM</td><td>0.4751</td><td>0.6485</td><td>0.6496</td><td>0.6293</td><td>0.6263</td><td>A</td></tr><tr><td></td><td>FSIM</td><td>0.6806</td><td>0.8130</td><td>0.8231</td><td>0.8211</td><td>0.8201</td><td>A</td></tr><tr><td>A=0</td><td>PSNR</td><td>18.92</td><td>22.48</td><td>23.17</td><td>23.55</td><td>24.03</td><td>B</td></tr><tr><td rowspan="2">运动模糊</td><td>L=40</td><td>SSIM</td><td>0.3944</td><td>0.5893</td><td>0.6079</td><td>0.5980</td><td>0.5917</td><td>A</td></tr><tr><td></td><td>FSIM</td><td>0.6105</td><td>0.7626</td><td>0.7920</td><td>0.8038</td><td>0.8069</td><td>B</td></tr></table></body></html>

![](images/597ea45a63058192ed6578d31783aae2c97ebef6fcfdb5bc1e8511be12fc4e26.jpg)  
图1迭代过程中不同迭代步骤下所获得的图像质量在视觉上的对比

![](images/04fdd54dab3217dfaff6d8b3cbd2300461b60ccc6e1496bcbad2bea4232d0ec7.jpg)  
图2去模糊时关键迭代步数下所得到的残差图像

![](images/a5e2999b2c4078085de4f730d8ae92910ba5e12642daeb90b660546d9e5c22dc.jpg)  
图3去模糊时关键迭代步数下所得到的残差图像的直方图

# 2.2 迭代终止度量

基于图2和3对残差图像中各个像素点亮度值的变化趋势分析可以知道，随着迭代次数的增加，去模糊后的估计图像越来越接近原图像，这样导致残差图像中各个像素点的亮度值变小，之间的差异程度也越来越小。基于此，本文采用下面的方法定义了一种衡量去模糊效果好坏的DM度量。具体地，根据式(11)计算出残差图像，然后对残差图像进行归一化，归一化后残差图像的均值为零，方差为1。

$$
r ^ { \prime } = \frac { r - \overline { { r } } } { \sqrt { \operatorname { v a r } ( r ) } }
$$

其中： $\mathbf { \boldsymbol { r } } ^ { \prime }$ 代表归一化后的残差图像； $\overline { { r } }$ 和 $\mathbf { v a r } ( r )$ 分别是残差图像的均值和残差图像的方差。基于此，假设在残差图像中当前像素点坐标为 $( i , j )$ ,将其与间隔 $( m , n )$ 位置的像素点亮度值求积，重复对 $\boldsymbol { r }$ 中所有像素点做上述运算并求和，可以表示为

$$
\begin{array} { r } { C o e _ { r } , ( m , n ) = \sum _ { i , j } r ^ { \prime } ( i , j ) r ^ { \prime } ( i - m , i - n ) } \end{array}
$$

由式(13)的定义可知， $C o e _ { r ^ { \prime } } ( m , n )$ 的值越小，表明像素点之间的差异越小。为了计算邻域范围内像素点亮度值的差异程度，可以定义 $( 2 \mathrm { L } + 1 ) ^ { * } ( 2 \mathrm { L } + 1 )$ 邻域窗口范围下中心像素点与邻域内各个像素点的差异总和 $D M _ { \ r { r } }$ .作为衡量复原图像整体去模糊效果的度量。

$$
{ D M _ { r ^ { \prime } } } = \sum _ { \stackrel { ( m , n ) = ( - L , - L ) } { ( m , n ) \neq 0 } } ^ { L , L } ( C o e _ { r ^ { \prime } } ( m , n ) ) ^ { 2 }
$$

其中：L是邻域范围的半径。表2是大小为 $2 5 6 ^ { * } 2 5 6$ 的Barbara图像分别在均匀模糊 $N = [ 5 ~ 5 ]$ 、高斯模糊(K=[1515], $\mathrm { S } { = } 3$ )和运动模糊 $( \mathrm { A } { = } 0 , \ \mathrm { L } { = } 1 0 ) ,$ 中的度量值 $D M _ { r }$ .的变化情况。从表2中数据可以看出：

a)度量值 $D M _ { r }$ .的变化非常有规律。在迭代过程中的初始阶段，度量值变化比较大且下降非常快，这说明图像质量提升很快；随着迭代次数的增加，度量值 $D M$ 下降得越来越慢，说明图像质量趋于稳定。

b)对于不同类型模糊、不同模糊程度和不同图像内容的图像，很难依据值 $D M _ { r }$ 本身大小来决定是否迭代过程应该终止。例如，表2中度量值 $D M _ { r }$ 在0.38、0.05和0.59处趋于稳定，因此无法直接根据度量值 $D M _ { r }$ .的大小决定迭代过程是否应该终止。

表2均匀模糊 $( \mathrm { K } { = } [ 5 ~ 5 ] )$ 下部分选代步数的度量值 $D M _ { r ^ { \prime } }$ 变化情况  

<html><body><table><tr><td>Step</td><td>1</td><td>5</td><td>10</td><td>20</td><td>50</td><td>120</td><td>240</td><td>360</td><td>480</td><td>720</td></tr><tr><td>DM,</td><td>5.58</td><td>0.92</td><td>0.23</td><td>0.29</td><td>0.35</td><td>0.36</td><td>0.38</td><td>0.38</td><td>0.38</td><td>0.38</td></tr></table></body></html>

表3高斯模糊(K=[15 15], $\mathrm { S } { = } 3$ 下部分迭代步数的度量值 $D M _ { r ^ { \prime } }$ 变化情况  

<html><body><table><tr><td>Step</td><td>1</td><td>5</td><td>10</td><td>20</td><td>50</td><td>120</td><td>240</td><td>360</td><td>480</td><td>720</td></tr><tr><td>DM</td><td>27.03</td><td>0.02</td><td>0.03</td><td>0.04</td><td>0.04</td><td>0.04</td><td>0.05</td><td>0.05</td><td>0.05</td><td>0.05</td></tr></table></body></html>

表4运动模糊( $\scriptstyle \mathbf { A } = 0$ $\mathrm { L } { = } 1 0 \rangle$ 下部分迭代步数的度量值 $D M _ { r ^ { \prime } }$ 变化情况  

<html><body><table><tr><td>Step</td><td>1</td><td>5</td><td>10</td><td>20</td><td>50</td><td>120</td><td>240</td><td>360</td><td>480</td><td>720</td></tr><tr><td>DM</td><td>14.10</td><td>0.78</td><td>0.59</td><td>0.49</td><td>0.48</td><td>0.54</td><td>0.59</td><td>0.59</td><td>0.59</td><td>0.59</td></tr></table></body></html>

# 2.3自适应送代终止条件

从上文给出的去模糊度量 $D M _ { r }$ .的值随迭代次数变化的趋势来看，很难依据评价度量值本身值的大小来决定是否迭代过程应该中止。为此，本文提出依据 $D M _ { r }$ 值变化趋势确定AISC条件，即通过检测连续步数 Step 范围内 $D M ,$ .值变化的绝对值是否小于预设的阈值e来判定图像质量是否已经趋于稳定。若AISC条件满足，则去模糊算法的迭代过程终止。因此，连续步数Step和阈值e是AISC条件两个重要的参数，它们具体值的设置主要根据特定去模糊算法的迭代收敛速度，依据大量实验数据来确定。

为了设置一个合理的步数和阈值，选取如图3中10 张图像进行实验分析，图像均来自目前文献中常用的TID2013数据库[20]。实验选用高斯模糊 $\mathrm { ( K = } [ 9 9 ] , \mathrm { S = } 3 )$ 在连续搜索步数Step 为15、20、25下进行，阈值e的值设置为0.01、0.02和0.03。表5数据为10张图像终止时与720次终止时图像质量值差值的平均值，表5给出了PSNR、SSIM、FSIM值三种图像质量评价指标的差值，其中正值表示采用本文所提出的AISC条件后所获得的图像质量优于NCSR算法原720步固定迭代次数所获得的结果，负值则表示要差。表5中加粗加下画线的为PSNR、SSIM、FSIM值在不同设置条件下的最佳值。综合来看，只有阈值e被设置为0.01时，FSIM值才为正值，且连续步数 Step为20时在 $\mathrm { ~ e ~ } ^ { - 0 . 0 1 }$ 时最好的去模糊效果。因此本文选用步数为20、阈值为0.01作为迭代终止条件的参数。下文所有的实验数据都是在这个参数设置条件下获得的。

![](images/3ee57c24ffb954de514a6ca9f99a291ba8b8ea0885748a5a71050857f2ea53bb.jpg)  
图3TID2013图像集[20]中10 张图像

表5不同阈值和步数下自适应迭代终止对应的质量值与第720步质量值的平均误差  

<html><body><table><tr><td>阈值</td><td></td><td>0.01</td><td></td><td></td><td>0.02</td><td></td><td></td><td>0.03</td><td></td></tr><tr><td>步数</td><td>PSNR</td><td>SSIM</td><td>FSIM</td><td>PSNR</td><td>SSIM</td><td>FSIM</td><td>PSNR</td><td>SSIM</td><td>FSIM</td></tr><tr><td>15</td><td>0.2817</td><td>0.0407</td><td>0.0001</td><td>0.2456</td><td>0.0500</td><td>-0.0012</td><td>0.3111</td><td>0.0550</td><td>-0.0008</td></tr><tr><td>20</td><td>0.2964</td><td>0.0373</td><td>0.0017</td><td>0.1969</td><td>0.0469</td><td>-0.0020</td><td>0.2501</td><td>0.0516</td><td>-0.0019</td></tr><tr><td>25</td><td>0.2670</td><td>0.0343</td><td>0.0010</td><td>0.1659</td><td>0.0449</td><td>-0.0025</td><td>0.2139</td><td>0.0493</td><td>-0.0025</td></tr></table></body></html>

# 3 实验结果及其分析

# 3.1实验测试平台和运行环境

为了验证方法的有效性和稳定性，选取两个具有代表性的图像集上进行测试：第一个图像集由各大文献中广泛使用的测试图像构成，如图4所示，这些图像是Barbara、Boat、Cameraman、Couple、Elk、Goldhill、House、Lena、Man 和Peppers 图像;第二个图像集由上文使用到的 $\mathrm { T I D } 2 0 1 3 ^ { [ 2 0 ] }$ 中的 10 张图像和文献[17]中的90 张图像(部分图像如图5所示)构成。由于图像集中内容复杂、纹理特征丰富，本文称之为挑战性图像集合，非常适合用来验证所提出的AISC条件的鲁棒性。算法运行的硬件平台为Intel Core(TM)i7-6700 3.40 GHz CPU 处理器，8GMB内存。软件系统配置为Windows7操作系统，编程环境为MATLAB $2 0 1 4 \mathrm { a } .$ 。为了说明迭代终止条件的有效性，采用PSNR、SSIM[18]和FSIM[19]图像质量评价指标衡量去模糊后图像质量的高低。

![](images/967041cc8baf4694d657b6d51d88d915cee34c5650eb964b1355f55f4b4c4817.jpg)  
图4常用图像集10张图像

![](images/0b24eb832e931c5c5efbadbcd2597584d2a1dcb5a8f78caa3897af196a493c6a.jpg)  
图5挑战性图像集中10张有代表性的图像

# 3.2 常用图像集

为了验证AISC迭代终止条件的有效性，首先在常用图像集上进行测试，测试结果如表6\~8所示。从表6\~8中数据可以看出：a)终止步数分布在200步以内，远少于原NCSR算法的720次固定的迭代次数；b)终止步数对应的图像质量值与第720步质量值(即原NCSR 算法获得的图像质量值)差别不大，人的肉眼其实比较难于区分。具体的分为两种情况，如图6所示，从左到右分别对应的是Elk 图像在参数为 $( \mathrm { K } { = } [ 1 5 1 5 ] , \mathrm { S } { = } 3 )$ 的高斯模糊下原始未失真图像、模糊图像、自适应迭代终止步数对应的图像和第720步对应的图像。720步迭代完成后的图像质量较自适应终止获得的图像质量稍有改善，但不易被觉察到；如图7所示，Lena图像参数 $( \mathrm { K } { = } [ 5 5 ] )$ 的均匀模糊下原始未失真图像、模糊图像、自适应迭代终止步数对应的图像和第720步对应的图像。720步迭代完成后的图像质量较自适应终止获得的图像质量稍差，但也不易被觉察到。由此可见，采用AISC终止条件后，改进算法可以适时终止迭代过程，极大提高了计算效率。在图像质量方面存在提高和降低两种可能，但是这两种情况与原算法所获得的图像在图像质量方面的差别很小，人的肉眼较难区分。改进算法在不损失太多图像质量的前提下实现了大幅度提高计算效率的目的。

表6均匀模糊下自适应迭代终止对应的质量值与第 720步质量值的平均误差比较  

<html><body><table><tr><td>模糊类型</td><td>中止步数范围</td><td>PSNR</td><td>SSIM</td><td>FSIM</td></tr><tr><td>均匀模糊(K=[5 5])</td><td>41~54</td><td>0.25</td><td>0.0135</td><td>0.0030</td></tr><tr><td>均匀模糊(K=[7 7])</td><td>16~53</td><td>-0.42</td><td>-0.0032</td><td>-0.0085</td></tr><tr><td>均匀模糊(K=[9 9])</td><td>12~47</td><td>-0.85</td><td>-0.0142</td><td>-0.0166</td></tr></table></body></html>

<html><body><table><tr><td>模糊类型</td><td>中止步数范围</td><td>PSNR</td><td>SSIM</td><td>FSIM</td></tr><tr><td>高斯模糊(K=[5 5],S=3)</td><td>70~85</td><td>1.05</td><td>0.0427</td><td>0.0173</td></tr><tr><td>高斯模糊(K=[99],S=3)</td><td>6~16</td><td>-0.85</td><td>0.0401</td><td>-0.0248</td></tr><tr><td>高斯模糊(K=[1515],S=3)</td><td>6~15</td><td>-1.55</td><td>-0.0537</td><td>-0.0494</td></tr></table></body></html>

表7高斯模糊下自适应迭代终止对应的质量值与第720步质量值的平均误差比较  

<html><body><table><tr><td>模糊类型</td><td>中止步数范围</td><td>PSNR</td><td>SSIM</td><td>FSIM</td></tr><tr><td>运动模糊(A=0,L=10)</td><td>106~163</td><td>0.56</td><td>0.0220</td><td>0.0033</td></tr><tr><td>运动模糊(A=0,L=20)</td><td>91~150</td><td>0.27</td><td>0.0177</td><td>0.0072</td></tr><tr><td>运动模糊(A=0,L=40)</td><td>77~90</td><td>-0.05</td><td>0.0090</td><td>0.0020</td></tr></table></body></html>

![](images/30759cb433566bac489ca055a89a2f27880c370be567c423ca881c9515efd091.jpg)  
图6高斯模糊(K=[1515] $\mathrm { S } { = } 3$ )条件下EIk图像的视觉效果对比

![](images/21d1fb829e0d745bf2ed23ea2edfc585ff8519c70a3135790f341d2926eec2a9.jpg)  
图7均匀模糊 $( \mathrm { K } { = } [ 5 ~ 5 ]$ )条件下Lena图像的视觉效果对比

# 3.3挑战性图像集

为了进一步验证AISC是否具有较强的鲁棒性，在挑战性图像集合上完成了实验。表9\~11列出的是三种模糊类型下的实验结果，整体情况与常用图像集的情况类似。总体来讲，本文提出的AISC迭代终止条件能够在保证图像质量损失较少的情况下(也有部分情况提升图像质量)，对算法迭代适时的终止，有效地改善了计算效率。

表8运动模糊下自适应迭代终止对应的质量值与第720步质量值的平均误差比较  
第 720步质量值的平均误差比较  

<html><body><table><tr><td colspan="5">第</td></tr><tr><td>模糊类型</td><td>中止步数范围</td><td>PSNR</td><td>SSIM</td><td>FSIM</td></tr><tr><td>均匀模糊(K=[5 5])</td><td>39~63</td><td>0.22</td><td>0.0161</td><td>0.0208</td></tr><tr><td>均匀模糊(K=[7 7])</td><td>37~60</td><td>-0.32</td><td>0.0012</td><td>-0.0058</td></tr><tr><td>均匀模糊(K=[9 9]</td><td>15~55</td><td>-0.72</td><td>-0.0070</td><td>-0.0133</td></tr></table></body></html>

表9均匀模糊下自适应迭代终止对应的质量值与  
表10高斯模糊下自适应迭代终止对应的质量值与第720步质量值的平均误差比较  

<html><body><table><tr><td>模糊类型</td><td>中止步数范围</td><td>PSNR</td><td>SSIM</td><td>FSIM</td></tr><tr><td>高斯模糊(K=[5 5],S=3)</td><td>57~91</td><td>1.01</td><td>0.0441</td><td>0.0175</td></tr><tr><td>高斯模糊(K=[99],S=3)</td><td>4~36</td><td>-0.47</td><td>0.0556</td><td>-0.0080</td></tr><tr><td>高斯模糊(K=[1515],S=3)</td><td>4~19</td><td>-1.33</td><td>-0.0458</td><td>-0.0442</td></tr></table></body></html>

表11运动模糊下自适应迭代终止对应的质量值与第720步质量值的平均误差比较  

<html><body><table><tr><td>模糊类型</td><td>中止步数范围</td><td>PSNR</td><td>SSIM</td><td>FSIM</td></tr><tr><td>运动模糊(A=0,L=10)</td><td>67~164</td><td>0.58</td><td>0.0234</td><td>0.0091</td></tr><tr><td>运动模糊(A=0,L=20)</td><td>22~151</td><td>0.25</td><td>0.0206</td><td>0.0076</td></tr><tr><td>运动模糊(A=0,L=40)</td><td>22~76</td><td>-0.64</td><td>0.0213</td><td>-0.0075</td></tr></table></body></html>

# 3.4执行时间

为了测试引入去模糊效果度量后所增加的运行时间，以一张大小 $2 5 6 ^ { * } 2 5 6$ 的Lena图像为测试图像，记录NCSR内循环执行一步和计算去模糊度量所需执行时间，列在表12中。由表12中可知，本文所提出的去模糊图像质量度量所增加的时间非常少(都在毫秒量级上)，几乎可以忽略不计。其原因在于本文所提出的去模糊效果度量是专门针对去模糊算法的特点而设计的，其最大的计算量在于中间估计图像与模糊核的卷积操作，而卷积操作对于目前的计算机来说有大量成熟的加速算法可以利用，故执行时间不长。而现有的评价准确性比较好的NR-IQA算法很多运行时间都在秒的量级上(有的甚至高达几十秒)，因此，本文所提出的DM度量远比引入现有的NR-IQA算法所增加的执行时间要少很多。另外由上文可知，采用ASIC条件后NCSR算法一般情况下在迭代200步以内就会终止，因此执行时间大为缩短。其实，不仅仅是在内循环中减少了迭代步数所获得的提升，在外循环的中所节省的字典学习(dictionarylearning)时间也是非常可观的。因此，引入AISC条件后，NCSR算法在计算性能方面的提升是非常可观的，而且在多数时候，所获得的去模糊图像质量还有一定程度上升。虽然在某些时候所获得的图像质量不如原NCSR算法，但在视觉上差别也不大。

表12NCSR 算法迭代一步所需要时间和计算DM度量所需时间对比/ms  

<html><body><table><tr><td>Blur type</td><td>Parameters</td><td>One step</td><td>DM metric</td></tr><tr><td>Uniform blur</td><td>K=[5 5]</td><td>102.1</td><td>4.4</td></tr><tr><td>Gaussian blur</td><td>K=[9 9], S=3</td><td>88.7</td><td>4.3</td></tr><tr><td>Motion blur</td><td>A=0,L=40</td><td>69.3</td><td>4.4</td></tr></table></body></html>

# 4 结束语

现有基于迭代求解方式的去模糊算法在实现时采用固定的迭代次数，并不能保证所获得的去模糊图像质量是最佳的，且存在着算法的时间效率比较低的问题。本文通过分析残差图像的特点，利用残差图像中各个像素点之间的亮度值差异作为衡量去模糊效果的度量值，并基于这个度量设计了ASIC自适应的迭代终止条件。采用ASIC迭代中止条件后的NCSR算法较原来采用固定迭代次数的方法在保证图像质量的前提下，能够自适应地终止迭代过程，改善了原算法耗时长的问题。需要特别说明的是，本文所提出的ASIC迭代中止条件并非只能用于NCSR 算法，其工作原理适用于所有迭代型的去模糊算法。当

然它的两个关键参数需要根据某个特定去模糊算法在迭代过程   
中的收敛速度合理设置后方可应用。   
参考文献:   
[1]ChristianJS,Michael H,StefanH,etal.Learning to deblur[J].IEEE Trans on Pattern Analysis& Machine Intelligence,2016,38(7):1439-1451   
[2]Yang Hang，Zhang Zhongbo,Guan Yujing.An adaptive parameter estimation for guided filter based image deconvolution [J].Signal Processing,2017,138 (September):16-26.   
[3]Jeon HG,LeeJY，Han Y,etal. Multimage deblurringusing complementary sets of flutering patterns [J]. IEEE Trans on Image Processing,2017,26 (5): 2311-2326.   
[4]Zhou Luoyu,Tang Jiaxin.Fraction-order total variation blind image restoration basedonL1-norm [J].Applied Mathematical Modelling,2017, 51 (November): 469-476.   
[5]Chambolle A.An algorithm for total variation minimization and applications [J]. Journal ofMathematical Imaging andVision,2004,20(1-2):89-97.   
[6]Oliveira JP,Bioucas-Dias JM,Figueiredo MAT.Adaptive total variation imagedeblurring:a majorization-minimization approach [J]. Signal Processing,2009,89 (9): 1683-1693.   
[7]BuadesA,Coll B,Morel JM.A non-local algorithm for image denoising [C]//Proc of IEEE Computer Society Conference on Computer Vision and Patern Recognition. Washington DC: IEEE Computer Society,2005:60-65.   
[8]Mignotte M.A non-local regularization strategy for image deconvolution [J]. Patern Recognition Letters,2008,29 (16): 2206-2212.   
[9]KheradmandA,Milanfar P.A general framework forregularized,similarity based image restoration[J]. IEEE Trans on Image Processing,2014,23 (12); 5136-5151.   
[10] Zhang Jian, Zhao Debin,Gao Wen. Group-based sparse representation for image restoration [J].IEEE Trans on Image Processing,2014,23(8): 3336- 3351.   
[11] Wang Z, Yang X. Group sparse regularization based iterative incremental image deblurring[C]//Proc of IEEE International Geoscience and Remote Sensing Symposium.Washington DC: IEEE Computer Society,2016:2951 2954.   
[12] Liu Shujun, Wu Guoqing,Liu Hongqing, et al. Image restoration approach usinga joint sparse representation in 3D-transform domain [J].Digital Signal Processing, 2017, 60: 307-23.   
[13]Dong Weisheng,Zhang Lei, Shi Guangming,et al. Nonlocally centralized sparserepresentation for image restoration [J]. IEEE Trans on Image Processing,2013,22(4):1620-1630.   
[14]蔡源涛．基于稀疏约束的图像去模糊迭代方法研究[D].成都：电子科 技大学,2015.   
[15] Zhu X,Milanfar P.Automatic parameter selection for denoising algorithms using a no-reference measure of image content [J]. IEEE Trans on Image Processing,2010,19 (12):3116-3132.   
[16] Mittal A,Soundararajan R,Bovik A C.Making a"completely blind"image quality analyzer[J].IEEE Signal Processing Letters,2013,20(3): 209-212.   
[17] Zhang Lin,Zhang Lei,Bovik A C.A feature-enriched completely blind image quality evaluator[J].IEEE Trans on Image Processing,2O15,24 (8): 2579-2591.   
[18] Wang Zhou,Bovik AC,Sheikh HR,et al. Image quality assessment: From error visibility to structural similarity[J].IEEE Trans on Image Processing, 2004,13(4):600-612.   
[19] ZhangLin,ZhangLei,Mou Xuanqin, etal.FSIM: a feature similarity index for image quality assessment[J].IEEE Trans on Image Processing,2011,20 (8): 2378-2386.   
[20] Ponomarenko N,Jin L, Ieremeiev O,and et al. Image database TID2013: peculiarities,results and perspectives [J]．Signal Processing:Image Communication,2015,30(1): 57-77.