# 基于稀疏贝叶斯估计的单图像超分辨率算法

袁桂霞‘，周先春²

(1.江苏开放大学 信息与机电工程学院，南京 210017;2.南京信息工程大学 电子与信息工程学院，南京 210044)

摘要：针对现有超分辨率方法对不同低分辨率图像的超分辨率效果差异较大的问题，提出了一种基于稀疏贝叶斯估计的单图像超分辨率方法。该方法将单图像超分辨率问题看做是回归问题，采用Kronecker脉冲函数作为回归基函数，综合利用图像的局部信息和全局信息寻找特定预测的最优稀疏解决方案，采用贝叶斯方法估计权重，据此重构超分辨率图像。实验结果表明，采用该方法对14幅测试图像进行单图像超分辨率，得到的平均峰值信噪比高、方差小、耗时少，证实了该方法的超分辨率效果好、适应性强，且运算效率高。

关键词：单图像超分辨率；超分辨率；贝叶斯估计；回归；稀疏表示 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.09.0959

Single image super-resolution method based on sparse Bayesian estimation

Yuan Guixial, Zhou Xianchun² (1.SchoolofInformation&Mechanical&ElectricalEngineringJangsuOpenUniversityNanjingol7,China;2.hool ofElectronic&InformationEngineeing,NnjingUniversityofInformationSience&TchnologyNanjingoChina)

Abstract: Aimingatthe problemthathe super-resolutioneffectondiferentlow-resolutionimages ofexisting super-resolution methods has large diference,this paper proposed a new single image super-resolution method based onsparse Bayesian estimation.Intismethod,itregardedthsingleimagesuper-resolutionproblemasaregressonproblem.ItusedtheKronecker pulsefunctionsas theregressionbasisfunctions,andobtainedtheoptimalsparsesolutionofthespeificpredictionbycombiing the localinformationandglobal informationoftheimage.Itusedthe Bayesianmethodtoestimate the weights，thereby reconstructingthe super-resolution image.Theexperimentalresultsshow that this methodcanobtain highaverage peak signal to noiseratio,smallvarianceandlesstime-consuming,whencarriedouton14testing imagesforsingle imagesuper-resolution. It is proved that this method has good super-resolution effect, strong adaptability,and high efficiency.

Key Words: single image super-resolution; super-resolution; Bayesian estimations; regresson; sparse representation

# 0 引言

单图像超分辨率（single image super-resolution，SISR）是计算机视觉中的一个经典问题，近年来引起了广泛的关注。SISR的任务是在给出相应的低分辨率图像的情况下恢复高分辨率图像[I]。现有SISR方法通常分为盲超分辨率方法和非盲超分辨率方法两类。盲目超分辨率方法假设高分辨率图像和模糊核都是未知的。非盲超分辨率方法假设只有高分辨率图像是未知的，而模糊核是已知的。非盲超分辨率方法可以有效处理不同模糊核下的低分辨率图像，一般不需要任何训练阶段，超分辨率效果较好。但是自然图像中模糊核一般是未知的，或者难以满足理想的模糊核假设条件，这限制了此类方法的应用。盲超分辨率方法是一种普适性很强的单图像超分辨率方法，此类方法从大量训练样本集中学习低分辨率图像到高分辨率图像的映射规则[2-6]。这里假设训练样本和测试样本的模糊核是相同的，也即训练样本集的学习结果适用于测试样本集。目前，超分辨率方法通常采用机器学习方法来进行学习和推理。但是这些方法大都是针对图像去卷积而定制的，过度依赖模糊核的选择，适应性不强，表现在对不同的低分辨率图像的超分辨率处理效果可能存在较大的差异。为了解决这一问题，本文将稀疏贝叶斯估计引入到超分辨率方法中去，将单图像超分辨率问题看做是一个回归问题，采用稀疏贝叶斯估计来求解回归问题，实现图像的超分辨率增强。在本文方法中超分辨率效果不依赖于模糊核的选择，适应性更强。

# 1 相关工作

图像超分辨率是计算机视觉的一个基础研究课题。该领域主要包括两个分支，一是依据多摄像机或者单摄像机采集的不同角度的低分辨率图像序列进行图像超分辨率重建，这一类超分辨率方法需要依赖于图像子像素的精确对准（通常采用SIFT等进行关键点配对)，以便推断高分辨率域中的丢失像素的值[7-9]；二是从单个低分辨率图像中重构高分辨率图像，即单图像超分辨率。本文主要关注单图像超分辨率方法。

单图像超分辨率方法进一步可以分为盲超分辨率方法和非盲超分辨率方法，如引言中所述。盲超分辨率方法通常尝试推断未知模糊核和高分辨率图像。目前优秀的SISR方法都是基于不同的机器学习原理，从大量训练图像集合中直接学习低分辨率和高分辨率域之间的映射规则。譬如，字典学习方法在高分辨率和低分辨率两个领域训练耦合词典来有效地表示训练数据。在推理时，低分辨率图像用低分辨率字典进行编码（如稀疏编码)，使用高分辨率字典重构高分辨率数据[10-13]。而邻域嵌入法不需要学习字典，可以直接使用所有训练数据进行编码[14\~16]。文献[17]提出了一种结合稀疏学习和邻域嵌入的超分辨率方法，该方法在计算邻居时使用与字典原子的相关性而不是欧几里德距离，并提出了锚定邻域回归，将低分辨率块的邻域嵌入到字典中最近的原子，并预先计算相应的嵌入矩阵，提高超分辨率效率。文献[18提出了一种基于随机森林的超分辨率方法。该方法在训练树的过程中优化了一种新颖的正则化目标，不仅可以对输出空间进行操作，还可以对输入空间进行操作，特别适合单图像超分辨率的回归任务。文献[19]所述单图像超分辨率方法也是基于稀疏表示的，该方法通过MMSE估计获得高分辨率图像块的预测结果，采用神经网络进行学习，兼顾图像超分辨率质量和计算复杂度。文献[20]将深度学习技术应用于单图像超分辨率，采用深度卷积神经网络学习低分辨率到高分辨率之间的端到端映射，实现图像的超分辨率增强。

然而现有盲超分辨率方法通常是针对图像去卷积而定制的，对不同的低分辨率图像的超分辨率处理效果差异较大，适应性不强。本文将稀疏贝叶斯估计引入到超分辨率方法中去，不依赖于模糊核的选择，适应性更强。

# 2 本文方法

本文所述的基于稀疏贝叶斯估计的超分辨率方法采用Kronecker脉冲函数作为回归基函数，描述单图像超分辨率的回归问题，综合利用图像的局部信息和全局信息寻找特定预测的最优稀疏解决方案，采用贝叶斯方法估计权重，将输入的低分辨率图像转换为高分辨率图像。

# 2.1超分辨率重构模型

给定形式为 $\{ x _ { i } , I _ { i } | i = 1 , 2 , \cdots , N \}$ 的数据集，其中$\mathbf { x } = \left[ x _ { 1 } , x _ { 2 } , \cdots , x _ { N } \right]$ 是已知的输入向量， $\mathbf { I } = \left[ I _ { 1 } , I _ { 2 } , \cdots , I _ { N } \right]$ 是期望的输出目标，N是输入向量的数量。对于新输入的向量 $\mathbf { x }$ ，可以采用回归模型对输出目标作出准确的预测。记观测样本集合为$\left\{ { { I } _ { l } } \right\}$ ，该集合中的图像是低分辨率图像。超分辨率算法的目标是从观测到的低分辨率图像集合中获取高分辨率图像集合。在超分辨率上下文中， $\textbf { x }$ 与图像采样网格中的位置相关联，其中$x _ { \scriptscriptstyle { l } }$ 对应低分辨率图像的采样位置， $x _ { h }$ 对应高分辨率图像的采样位置。给定 $\left\{ x _ { l } , I _ { l } \right\}$ 和 $\left\{ x _ { h } \right\}$ ，超分辨率重构可以表示为

$$
I = f ( x )
$$

其中： $f ( x )$ 表示图像采样位置 $x$ 处的亮度值或颜色值，是一个连续函数。

于是，超分辨率问题可以看做是从一个离散的、非规则的样本采样网格中，寻找样本连续信息的最优搜索，这是一个经典的回归问题。

对于数字图像而言，其信号是离散的，也即图像 $f ( x )$ 无法用一个连续函数来表示。在回归过程中，通常将图像信号近似表示为一个连续函数：

$$
\hat { f } = \sum _ { j = 1 } ^ { J } I _ { h , j } \delta \bigl ( x _ { h , j } \bigr )
$$

其中： $\hat { \boldsymbol f }$ 表示高分辨率位置 $x _ { h }$ 处 $f$ 的离散函数； $J$ 为采样点数量。记

$$
\begin{array} { c } { { \displaystyle { \bf w } = \left[ w _ { 1 } , w _ { 2 } , cdots , w _ { J } \right] } } \\ { { \mathrm { } } } \\ { { \mathrm { } = \left[ I _ { h , 1 } , I _ { h , 2 } , \cdots , I _ { h , J } \right] ^ { T } } } \end{array}
$$

$$
\begin{array} { l } { { \Phi = \left[ \phi _ { 1 } , \phi _ { 2 } , \cdots , \phi _ { J } \right] } } \\ { { \mathrm { } } } \\ { { \mathrm { } = \left[ \delta \left( x _ { h , 1 } \right) , \delta \left( x _ { h , 2 } \right) , \cdots , \delta \left( x _ { h , J } \right) \right] } } \end{array}
$$

则有

$$
{ \hat { f } } = \mathbf { w } \cdot \Phi 
$$

其中： $\textbf { w }$ 表示待学习的权重向量； $\Phi$ 表示空间位置 $x _ { h }$ 上的离散基。

# 2.2 稀疏贝叶斯估计

超分辨率重建的困难在于采集网格的不确定性，这里采用稀疏贝叶斯框架来处理该问题。从稀疏的角度来看，超分辨率问题可以看做是对权重向量 $\mathbf { w }$ 的估计，寻找最优的权重，使得回归值与观测值尽可能接近，即

$$
\left[ I _ { 1 } , I _ { 2 } , \cdots , I _ { J } \right] ^ { T } \approx \left[ \phi _ { 1 } , \phi _ { 2 } , \cdots , \phi _ { J } \right] \mathbf { w }
$$

与传统方法不同的是，本文所提出的方法通过假设在预定义的邻域内设置权重来约束稀疏条件，其目标是最大化权重之间的协方差。

回归基对应于放置在预定义高分辨率网格上的单位脉冲函数，权重对应于将图像颜色空间转换为Gibbs分布的核函数。该核函数用于调制似然函数，可以用观测值与线性模型之间的差异的高斯函数来近似。

给定一个回归基 $\Phi$ ，采用贝叶斯处理得到预测分布。预测分布通常可以采用似然项和先验项的概率之积来表示：

$$
p \big ( \mathbf { w } \big | I _ { \iota } , \Phi \big ) = p \big ( I _ { \iota } \big | \mathbf { w } , \Phi \big ) p \big ( \mathbf { w } , \Phi \big )
$$

似然项 $p ( I _ { l } \mid \mathbf { w } , \phi )$ 是从可能的回归器 $\Phi$ 生成观测数据 $I _ { \iota }$ 的能力的度量，有

$$
p \left( I _ { l } | \mathbf { w } , \phi \right) = \frac { 1 } { \left( 2 \pi \right) ^ { \frac { M } { 2 } } } \exp \left( - \frac { 1 } { 2 } \big \| \left( I _ { l } - g _ { l } \left( \mathbf { w } \Phi \right) \right) \big \| _ { 2 } \right)
$$

其中：M是图像分块数量，图像块尺寸为 $3 { \times } 3$ ； $g _ { l }$ 是将高分辨率映射到低分辨率图像的子采样。

先验模型遵循Gibbs分布，这样可以提供了一个具有全局最小值的凸成本函数，更容易求解。于是，该模型可以改写为

$$
p \big ( \mathbf { w } \big | \phi \big ) = \frac { 1 } { \left( 2 \pi \right) ^ { M } \sqrt { \left| k \right| } } \exp \left( - \frac { 1 } { 2 } \big ( \mathbf { w } \cdot \Phi \big ) ^ { T } \mathbf { k } ^ { T } \left( \mathbf { w } \cdot \Phi \right) ^ { T } \right)
$$

其中： ${ \bf k } = k _ { i } k _ { i } ^ { T }$ 是要学习的 $\mathbf { M } { \times } \mathbf { M }$ 的内核矩阵，$\boldsymbol { k } _ { i } = \left[ k _ { i , 1 } , k _ { i , 2 } , \cdots , k _ { i , M } \right] ^ { T }$ 表示一个系数向量，是关于w值之间的局部关系的先验假设集合。内核矩阵采用Gibbs分布和预定义的邻域来学习，表示为

$$
\hat { \mathbf { k } } = \arg \operatorname* { m a x } _ { \mathbf { k } } p \big ( { I } _ { l } | \mathbf { k } \big ) = \arg \operatorname* { m a x } _ { \mathbf { k } } \int p \big ( { I } _ { h } , { I } _ { l } | \mathbf { k } \big ) \hat { \mathcal { O } } I _ { h }
$$

最大后验可以通过一个期望最大化框架来解决，这里将高分辨率图像 $\boldsymbol { I } _ { h }$ 作为隐含变量，在此基础上将最大后验问题视为通常的期望最大化问题。期望最大化框架包括两个步骤，即E和 $\mathbf { M }$ 步骤。E步骤使用当前内核估计高分辨率图像及其协方差，M步骤使用E步骤中的高分辨率图像确定最佳内核。简要描述如下：

1）E步骤

令 $p \big ( I _ { h } \big ) = p \big ( I _ { h } \big | I _ { l } , \mathbf { k } \big )$ ，计算高分辨率图像 $\boldsymbol { I } _ { h }$ 的平均估计和协方差。

2）M步骤

通过最小化 $E _ { I _ { h } } \left( \left\| \mathbf { k } I _ { h } - { I _ { l } } ^ { 2 } \right\| \right)$ 估计 $\mathbf { k }$ 。

这里，基函数 $\phi$ 用Kronecker脉冲函数近似。

上述步骤仅考虑了图像不同采样点的局部信息，不够完备。本文结合低分辨率图像的全局平滑估计信息对先验项进行补偿，提高数据回归精度。具体地，对低分辨率图像进行平滑处理，得到一个平滑估计图像 $\bar { \bf w }$ ，平滑窗口尺寸为 $3 { \times } 3$ ，窗口各位置权重都为 $\frac { 1 } { 9 }$ 。通过使数据 $\mathbf { w }$ 围绕低分辨率图像的平滑变化的估计值来对来自低分辨率图像的全局信息进行补偿，即

$$
p \big ( \mathbf { w } \big | \overline { { \mathbf { w } } } \big ) = \frac { 1 } { \big ( 2 \pi \big ) ^ { M } } \mathrm { e x p } \Bigg ( { - \frac { 1 } { 2 } \big ( \mathbf { w } \cdot \Phi - \overline { { \mathbf { w } } } \cdot \Phi \big ) ^ { 2 } } \Bigg )
$$

本文使用似然项的成本函数来求解完整的贝叶斯公式，这样局部和全局先验项可以定义为

$$
\hat { \mathbf { w } } = \arg \operatorname* { m i n } _ { \mathbf { w } } \left( - \ln \left( p \left( I _ { l } | \mathbf { w } , \Phi \right) \right) - \ln \left( p \left( \mathbf { w } \left| \Phi \right. \right) \right) - \ln \left( p \left( \mathbf { w } \left| \bar { \mathbf { w } } \right. \right) \right) \right)
$$

成本函数为

$$
\begin{array} { l } { { \displaystyle { \cal L } \big ( { \bf w } \big ) = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \Biggl ( I _ { i , i } - g _ { l } \sum _ { j = 1 } ^ { J } w _ { j } \phi _ { j } \Biggr ) ^ { 2 } } } \\ { { \displaystyle ~ + \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \Biggl ( \sum _ { j = 1 } ^ { J } k _ { i , j } w _ { j } \phi _ { j } \Biggr ) ^ { 2 } + \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \Biggl ( \sum _ { j = 1 } ^ { J } \Bigl ( w _ { j } \phi _ { j } - \overline { { w } } _ { j } \phi _ { j } \Bigr ) \Biggr ) ^ { 2 } } } \end{array}
$$

本文采用梯度下降法进行估计，公式为

$$
\hat { \mathbf { w } } ^ { n + 1 } = \hat { \mathbf { w } } ^ { n } - \varepsilon \nabla L \big ( \hat { \mathbf { w } } ^ { n } \big )
$$

其中：

$$
\nabla L \left( \hat { \mathbf { w } } ^ { n } \right) = \left[ \frac { \nabla L \left( \hat { \mathbf { w } } ^ { n } \right) } { \hat { \partial } w _ { 1 } } , \frac { \nabla L \left( \hat { \mathbf { w } } ^ { n } \right) } { \hat { \partial } w _ { 2 } } , \cdots , \frac { \nabla L \left( \hat { \mathbf { w } } ^ { n } \right) } { \hat { \partial } w _ { J } } \right] ^ { T }
$$

# 2.3图像超分辨率

基于学习的图像超分辨率方法通常需要先进行训练，学习权重向量；然后利用训练得到的权重向量重构超分辨率图像。本文选择公开的数据集 Set5子集[17进行训练。该子集中共有五幅图像，见图1。其中，数据集中的图像都是彩色图像。考虑到人类的视觉感知强度比颜色变化更敏感，本文首先将图像转换到YUV颜色空间，仅对Y分量采用上述方法进行图像超分辨率的学习和重构。训练时，将原始尺寸的图像作为高分辨率图像，而将采用双线性插值方法亚采样的图像作为低分辨率图像，通过前面的描述进行学习，得到权重向量W。

图像超分辨率时，对于灰度图像，依据学习得到的权重向量进行超分辨率重构。对于彩色图像，先将彩色图像转换到YUV颜色空间，仅对Y分量采用上述方法进行图像超分辨率重构。而对于U和V分量，采用标准的双三次插值方法得到相同尺寸高分辨率下的颜色分量。最后将高分辨率下的YUV分量再转换到RGB颜色空间，得到最终的超分辨率结果。

![](images/bba1cdf2c337d5aee1ddf9f37ba304ecf216c059fbe78b290d8c0b15c7312f22.jpg)  
图1训练样本图像

# 3 实验结果与分析

为验证本文方法的单图像超分辨率效果，本文选择公开的数据集Set14子集[17]进行测试。样本图像如图2所示。

![](images/490b77344c8ee4ca63c023448b54297d9029c470c756f7eda899ac93200610f3.jpg)  
图2测试样本图像

算法评测采用客观评价和主观评价两种方式，在客观评价阶段，选择目前图像质量评价常用的峰值信噪比（peaksignaltonoiseratio，PSNR）指标，通过不同方法所得到的超分辨率图像的PSNR值来评价算法的超分辨率性能，通过对比不同图像对应的PSNR值的方差来评价算法的适应性。另外，通过对比不同方法的超分辨率耗时来评价算法的运算效率。在主观评价阶段，对比不同方法所得到的超分辨率图像，人工观测超分辨率效果。实验中所选择的对比方法有四种，分别为文献[17\~20]所述方法，这些方法是目前单图像超分辨率领域性能靠前的几种方法。这四种方法和本文方法都使用Set5子集进行训练，使用Set14子集进行测试，相关过程可以参考文献[17]。

# 3.1客观评价

表1给出了五种方法对Set14子集中14幅图像进行超分辨率之后得到的图像的PSNR值。其中，加粗的字体为对应图像的最大PSNR值。可见，本文方法对12幅图像的超分辨率增强结果的PSNR值都大于其他四种方法，仅对2幅图像的超分辨率增强结果的PSNR值略小于文献[18]所述方法，这说明本文方法的超分辨率增强性能优于其他四种方法。

图3给出了了五种方法对Set14子集中14幅图像进行超分辨率之后得到的图像的PSNR值的均值和方差。可见，本文方法除了PSNR均值高于其他四种方法之外，其方差也小于其他四种方法。这是因为本文方法对模糊核的依赖小、适应性强，从而对不同的低分辨率图像的超分辨率处理效果差异较小。

表2给出了五种方法进行图像超分辨率的平均耗时（不包括训练耗时)。其中，五种方法所用计算机平台相同，主要参数为：IntelI7CPU、16GBDDR3内存、64位Windows764bit操作系统、VisualStudio2010 软件平台。可见，本文方法的平均耗时最少，说明本文方法的运算效率最高。

表1超分辨率图像PSNR值  

<html><body><table><tr><td>方法</td><td>文献[17]</td><td>文献[18]</td><td>文献[19]</td><td>文献[20]</td><td>本文方法</td></tr><tr><td>baboon</td><td>23.56</td><td>23.79</td><td>23.03</td><td>23.66</td><td>25.02</td></tr><tr><td>barbara</td><td>26.69</td><td>27.18</td><td>25.57</td><td>26.66</td><td>27.15</td></tr><tr><td>bridge</td><td>25.01</td><td>25.63</td><td>25.31</td><td>25.07</td><td>26.83</td></tr><tr><td>coastguard</td><td>27.08</td><td>27.82</td><td>27.34</td><td>27.20</td><td>29.44</td></tr><tr><td>comic</td><td>24.04</td><td>24.64</td><td>24.13</td><td>24.39</td><td>26.36</td></tr><tr><td>face</td><td>33.62</td><td>34.10</td><td>33.29</td><td>33.58</td><td>34.14</td></tr><tr><td>flowers</td><td>28.49</td><td>29.27</td><td>28.22</td><td>28.97</td><td>29.89</td></tr><tr><td>foreman</td><td>33.23</td><td>34.12</td><td>33.12</td><td>33.35</td><td>34.21</td></tr><tr><td>lenna</td><td>33.08</td><td>34.43</td><td>33.34</td><td>33.39</td><td>34.46</td></tr><tr><td>man</td><td>27.92</td><td>28.15</td><td>28.02</td><td>28.18</td><td>29.33</td></tr><tr><td>monarch</td><td>31.09</td><td>31.15</td><td>31.17</td><td>32.39</td><td>32.46</td></tr><tr><td>pepper</td><td>33.82</td><td>35.22</td><td>34.11</td><td>34.35</td><td>34.67</td></tr><tr><td>ppt3</td><td>25.03</td><td>26.39</td><td>25.69</td><td>26.02</td><td>29.89</td></tr><tr><td>zebra</td><td>28.43</td><td>29.56</td><td>28.74</td><td>28.87</td><td>30.46</td></tr></table></body></html>

![](images/1480f8500df7151287a759875f10de1bfa8e8ede1459525ba88635a06556716e.jpg)  
图3超分辨率图像PSNR值的均值和方差

表2超分辨率平均耗时  

<html><body><table><tr><td>方法</td><td>耗时/ms</td></tr><tr><td>文献[17]</td><td>533</td></tr><tr><td>文献[18]</td><td>898</td></tr><tr><td>文献[19]</td><td>437</td></tr><tr><td>文献[20]</td><td>216</td></tr><tr><td>本文方法</td><td>199</td></tr></table></body></html>

# 3.2 主观评价

限于篇幅，下面仅给出baboon图像的局部超分辨率结果，如图4所示。其中，图4(a)为Groundtruth，图4(b\~f)分别为采用文献[17\~20]所述四种方法和本文方法进行超分辨率得到的增强结果。可见，采用本文方法得到的超分辨率图像的细节比较清晰，也即主观上来看本文方法的超分辨率增强效果也优于其他四种方法。

![](images/3a882d508c543723131d14a7fa510603744790e8381b8bdac642034794dcf7fc.jpg)  
图4baboon图像局部超分辨率结果

综上所述，无论是主观评价还是客观评价，本文方法都优于其他四种方法，在进行单图像超分辨率时可以对不同低分辨率的图像得到更高的PSNR值，超分辨率增强效果好、适应性强，且运算效率高。

# 4 结束语

本文所述的基于稀疏贝叶斯估计的单图像超分辨率方法是一种盲超分辨率方法，该方法将单图像超分辨率问题看做是回归问题，采用Kronecker脉冲函数作为回归基函数，综合利用图像的局部信息和全局信息寻找特定预测的最优稀疏解决方案，采用贝叶斯方法估计权重，实现图像超分辨率。本文方法的突出优点是不依赖于模糊核，对不同低分辨率图像的超分辨率效果差异较小、适应性强。而且本文方法在进行单图像超分辨率时可以得到更高的PSNR值，且运算效率高。

# 参考文献：

[1]Ding L,Wang Z,Wen B,et al.Robust single image super-resolution via deep networks with sparse prior [J].IEEE Trans on Image Processing A Publication of the IEEE Signal Processing Society,2016,25(7):3194-3201.   
[2]Yang MC,Wang Y C F.A self-learning approach to single image superresolution [J].IEEE Trans on Multimedia,2013,15 (3):498-508.   
[3]Wang L,Xiang S,Meng G,et al.Edge-Directed single-image superresolution via adaptive gradient magnitude self-interpolation [J].IEEE Trans on Circuits & Systems for Video Technology,2013,23(8):1289-1299.   
[4]Zhang K, Gao X, Tao D,et al. Single image super-resolution with multiscale similarity learning.[J]. IEEE Trans on Neural Networks & Learning Systems,2013,24(10): 1648-1659.   
[5]Rueda A,MalpicaN,Romero E.Single-image super-resolution ofbrain MR images using overcomplete dictionaries [J].Medical Image Analysis,2013, 17 (1): 113-132.   
[6]Zhang K,Tao D,Gao X,et al. Learning multiple linear mappings for efficient single image super-resolution. [J]. IEEE Trans on Image Processing, 2015,24 (3): 846-860.   
[7]李银辉，吕晓琪，于荷峰．基于L1和L2混合范式的序列图像超分辨率 重建[J].计算机应用,2015,35(3):840-843.   
[8] 郭琳，叶波，陈庆虎，等．融合几何变换相似块的序列图像超分辨率重 建[J].光电工程,2015,42(8):79-85.   
[9] 丁兰，傅志中，李晓峰，等．使用非均匀采样复原理论进行裂纹修复的 混合分辨率多视角图像超分辨[J]．光电工程,2013,40(1): 76-82.   
[10] Tang Y, Yuan Y, Yan P,et al. Greedy regression in sparse coding space for single-image super-resolution [J]. Journal of Visual Communication & Image Representation,2013,24 (2): 148-159.   
[11] Xu H, Zhai G,Yang X. Single image super-resolution with detail enhancement based on local fractal analysis of gradient[J].IEEE Trans on Circuits & Systems for Video Technology,2013,23(10): 1740-1754.   
[12] Jiang J, Hu R, Zhen H,et al. Efficient single image super-resolution via graph-constrained least squaresregression [J].Multimedia Tools& Applications,2014,72 (3): 2573-2596.   
[13] Zhu Z,Guo F,Yu H,et al.Fast single image super-resolution via selfexample learning and sparse representation [J]. IEEE Transon Multimedia, 2014,16 (8): 2178-2190.   
[14] Chen X,Qi C.Low-rank neighbor embedding for single image superresolution [J]. Signal Processing,2014,94(1): 6-2.   
[15] Bevilacqua M, Roumy A, Guillemot C, et al. Single-image super-resolution via linear mapping of interpolated self-examples [J]. IEEE Trans on Image Processing,2014,23 (12): 5334-4537.   
[16] Li J,Gong W,Li W,et al. Single-image super-resolution reconstruction based on global non-zero gradient penaltyand non-lcal Laplacian sparse coding [J]. Digital Signal Processing,2014,26(1):101-112.   
[17] Timofte R,De V, Van Gool L.Anchored neighborhood regression for fast example-based super-resolution [C]//Proc ofIEEE International Conference on Computer Vision. 2013: 1920-1927.   
[18] Schulter S,Leistner C,Bischof H. Fast and accurate image upscaling with super-resolution Forests [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.2015: 3791-3799.   
[19]Peleg T,Elad M.A statistical prediction model basedonsparse representations for single image super-resolution. [J]. IEEE Trans on Image Processing A Publication of the IEEE Signal Processing Society,2014,23 (6): 2569-2582.   
[20]Dong Chao,Loy C C,He Kaiming,etal.Learninga deep convolutional network for image super-resolution [Cl//Proc of European Conference on Computer Vision.[S.1.]: Springer International Publishing,2014: 184-199.