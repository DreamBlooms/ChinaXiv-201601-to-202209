# 基于DAE+CNN辐射源信号识别算法

叶文强，俞志富，张奎(国防科技大学 电子对抗学院，合肥 230037)

摘要：针对利用卷积神经网络进行辐射源信号识别过程中时间复杂度高的问题进行研究，提出一种基于降噪自编码器和卷积神经网络结合的算法。首先对雷达辐射源信号进行短时傅里叶变换，获取时频图像；然后对图像进行灰度和阈值二值化处理，将处理后的图像向量化操作输入到降噪自编码器中，提取降噪自编码器隐藏层特征数据完成降维处理，再重构成图片矩阵输入到卷积神经网络中，利用常用的 Softmax分类器进行分类识别。通过仿真表明，添加降噪自编码器降维处理后的模型相比较原模型，时间复杂度大幅度下降，在 $\mathrm { S N R = } . 6 ($ IB，识别效果能达到 $80 \%$ 以上，与利用传统降维方式性能相比，识别效果明显提高。

关键词：雷达辐射源；短时傅里叶；降噪自编码器；卷积神经网络；Softmax 中图分类号：TN911.7 doi:10.3969/j.issn.1001-3695.2018.07.0409

# Recognition algorithm of emitter signal based on DAE $^ { + }$ CNN

Ye Wenqiang, Yu Zhifu, Zhang Kui (Institute ofElectronic Countermeasure,National UniversityofDefense Technology,Hefei 23oo37,China)

Abstract: Inordertosolve theproblemofhightimecomplexity inthe signalrecognitionprocess byusing convolution neural network,this paper proposedanew algorithm basedondenoisingauto-encoderand convolution neural network.Firstly,it performed the STFTontheradar emiter signalto obtain the time frequency image.And itused grayand threshold.It put processed image vectorization into the denoisingauto-encoder.Then thedenoisingauto-encoder extracted the featuredataIt putthe reconstituted image matrix into theconvolution neural network and use Softmax clasifier as clasification and recognition.Thesimulation shows thatthemodelusingDAEis beterthan theoriginalmodelandthe timecomplexitydecreases greatly. The recognition rate can reach $80 \%$ under SNR $\scriptstyle =$ -6dB.Besides,compared with the traditional way,the performance of reducing the dimension is better.

KeyWords:radaremiter;short timeFourier transform(STFT);denoisingauto-encoder(DAE);convolution neural network (CNN); softmax

# 0 引言

雷达辐射源信号识别在现代化作战中起到无可替代的作用，直接影响到电子侦察设备的发挥并对后续的作战决策起到非常重要的影响。它不仅能够侦察系统信号，而且又能够判断敌方武器是否构成威胁，对战场走向有重要意义。随着战争的演变和科技的发展，战场对雷达辐射源信号识别有了更高的要求。传统人工识别已经不能够满足现代化战争的要求，需要引入人工智能，提出智能信息处理的方式[1]。文献[2]利用栈式稀疏编码器对常规雷达辐射源信号识别，识别效果相对于常规识别方法得到明显提高，但是时间复杂度较高。文献[3]在利用栈式稀疏编码器识别之前对信号数据进行PCA和随机投影联合降维，虽然降低了时间复杂度，但是识别效果大幅度下降。文献[4]利用卷积神经网络对辐射源信号进行识别，通过改进激活函数和核大小，改善了Loss函数收敛情况，信号也取得了较好的识别效果，前期没有对双谱图像预处理，数据维度太大，导致网络结构过于复杂。

利用机器学习的方法对雷达辐射源信号进行识别可以取得很好的识别效果，机器学习需要大量数据训练，很容易造成维数灾难，会提高模型的时间复杂度，最常见的解决方式就是通过降维处理。通过降维将数据从高维映射到低维空间中，常见的由PCA、LDA、LLE等降维方式[51，这些传统的降维方式只能保留数据的单一特征，降维后的数据再作为输入数据输入到深度学习模型中训练学习，会对识别效果造成很大影响。

2006，Hinton在《Science》发表文章，提出可以使用多个隐藏层来实现高维向低维编码，学习的低维编码可以更接近原始数据的本质[6]。因此，本文在已经构建好的卷积神经网络框架中，加上自编码器进行前期处理，将数据通过DAE 隐藏层完成降维，然后再输入到已经构建好的卷积神经网络中完成识别任务。

# 1 深度学习

# 1.1降噪自编码器

在2010年Vincent等人提出了降噪自编器结构，这类降噪自编码器通过对输入数据进行加噪处理来实现更好的特征表达。自编码器（Auto-Encoder,AE）主要是由输入层、隐藏层和输出层构成的非监督式的三层神经网络[8，网络训练主要是编码和解码的过程，网络结构如图1所示。

![](images/701b0fcce3905cecc7c50b651dcd3fa3ee0a48e58fe91e399001afc8907bc0c5.jpg)  
图1自编码器结构示意图

将输入向量映射到隐藏层的过程就是编码，经过编码可以得到新的特征表达，表示如下：

$$
\boldsymbol { Z } = \boldsymbol { f } ( \boldsymbol { x } ) = \boldsymbol { f } ( \boldsymbol { W } ^ { ( 1 ) } \boldsymbol { x } + \boldsymbol { b } ^ { ( 1 ) } )
$$

其中： $x \in R ^ { n \times 1 }$ 是输入向量， $\boldsymbol { W } ^ { ( 1 ) } \in \boldsymbol { R } ^ { m \times n }$ 为隐藏层权值矩阵，（20 $\boldsymbol { b } ^ { ( 1 ) } \in \boldsymbol { R } ^ { \mathrm { m } \times 1 }$ 为隐藏层的输入偏置， $\boldsymbol { z } \in \boldsymbol { R } ^ { \mathrm { m } \times 1 }$ 是输出向量。f()

为激活函数，常用的激活函数有 Sigmoid 函数： $\mathrm { f } \left( x \right) = \frac { 1 } { 1 + e ^ { - x } }$

以及 tanh 函数：f(x)= $\operatorname { f } \left( x \right) = { \frac { e ^ { x } - e ^ { - x } } { e ^ { x } + e ^ { - x } } } \circ$

将隐藏层 $z$ 映射回输入 $x$ 就是解码的过程，函数表示为

$$
\boldsymbol { X } = \boldsymbol { g } ( \boldsymbol { Z } ) = \boldsymbol { s } ( \boldsymbol { W } ^ { ( 2 ) } { } _ { \boldsymbol { z } + \boldsymbol { b } } ^ { ( 2 ) } )
$$

其中： $W ^ { ( 2 ) } { } _ { \in {  R } ^ { n \times m } } ; \quad { \boldsymbol b } ^ { ( 2 ) } { } _ { \in {  R } ^ { n \times 1 } }$ ，综合式（1）和（2），可以得到数据的重建误差为

$$
L = \left\| x - g ( f ( x ) ) \right\| ^ { 2 }
$$

定义代价函数为

$$
\begin{array} { r l } & { J ( W , b ) = \left[ \displaystyle \frac { 1 } { N } \sum _ { \mathrm { i = 1 } } ^ { N } ( \frac { 1 } { 2 } \Big \| x ^ { ( i ) } - g ( f ( ( x ) ) \Big \| ^ { 2 } ) \right] + } \\ & { \quad \quad \quad \quad \lambda \underset { \quad 2 } { \underbrace { \lambda \quad 2 } } \displaystyle \sum _ { l = 1 } ^ { s _ { l } } \sum _ { i = 1 } ^ { s _ { l + 1 } } ( W _ { j i } ^ { ( l ) } ) ^ { 2 } } \\ & { \quad \quad \quad \quad 2 ^ { l = 1 } i ^ { \mathrm { i } = 1 } j ^ { \mathrm { = 1 } } } \end{array}
$$

其中： $\boldsymbol { x } ^ { ( i ) }$ 代表第i个样本； ${ W } _ { j i } ^ { ( l ) }$ 代表第1层第i个单元与第$l + 1$ 层第j单元之间的连接权重；N代表样本的数量； $s _ { l }$ 代表第1层的单元数； $\lambda$ 是正则化系数，本文取1。

通过使用误差方向传导和批量下降算法9这两种方法可以得到最优解 $w$ 和 $b$ 。

在自动编码器中，将噪声加入到训练数据中，就可以得到降噪自编码器，通过加噪迫使自动编码器学习去除噪声。为了可以得到未被污染的输入数据[10]，在输入已经有噪声污染的情况下，降噪自编码器可以找到更稳定和更深层次的特征，这些特征组成了更高级的输入数据，大大提高了整个模型的稳定性，降噪训练的原理如图2所示。

![](images/444a15ed627a17c25982c9fc22f71f976fabb45c4f4f0f5b882c7568bed1a6f0.jpg)  
图2降噪自编码器结构

图2中， $x$ 表示原始输入数据， $\tilde { x }$ 表示受损的输入数据，$y$ 是对 $\tilde { x }$ 进行编码得到的新数据， $z$ 是对 $y$ 进行解码后的输出。重建误差表示为

$$
L _ { D } = \left\| X - g ( f ( \tilde { x } ) ) \right\| ^ { 2 }
$$

代价函数为

$$
\begin{array} { r l } & { \boldsymbol { J } _ { D } ( \boldsymbol { W } , \boldsymbol { b } ) = \left[ \frac { 1 } { N } \displaystyle \sum _ { \mathrm { i } = 1 } ^ { N } ( \frac { 1 } { 2 } \Big \| \boldsymbol { x } ^ { ( i ) } - \boldsymbol { g } ( f ( \boldsymbol { \tilde { x } } ) ) \Big \| ^ { 2 } ) \right] + } \\ & { \boldsymbol { \mathcal { \lambda } } \underset { - } { \underbrace { \lambda \mathrm {  ~ 2 ~ } s _ { l } \mathrm {  ~ \ } s _ { l + 1 } } } } \\ & { \boldsymbol { \mathcal { Z } } \underset { l = 1 } { \underbrace { \sum } } \sum _ { i = 1 } ^ { s _ { l } } \sum _ { j = 1 } ^ { s _ { l + 1 } } ( { \boldsymbol { W } } _ { j i } ^ { ( l ) } ) ^ { 2 } } \end{array}
$$

# 1.2 卷积神经网络

卷积网络也称做卷积神经网络(CNN)，这种神经网络主要是用来处理具有网络结构的数据[11]。比如时间序列数据（可以看作是时间轴上具有有规律地采样形成的一维网络）和图像数据（可以认为是二维的像素网络)。卷积神经网络在诸多应用领域都表现优异。卷积是一种特殊的线性运算。

卷积神经网络主要有三个重要的思想，运用这三个思想来帮助改进和优化学习系统：稀疏交互（sparseinteraction）参数共享（parametersharing）、等变表示（equipment） ）[12]。并且，卷积提供了一种可以处理大小可变的输入的方法。

![](images/ec8024ecbe22bb1fcb37dcf54e95a5521d5563d8dfc2825da397c9f47aaf942c.jpg)  
图3卷积神经网络基本框架

卷积神经网络是一种深度前馈人工神经网络，在图像分类识别中取得了非常大的成功。它包括卷积层、池化层和全连接层，图片经过这些特殊的网络层，经过转换会变成特定的输出，在这些网络层中核心是卷积层和池化层，这两个网络层的设置参数会对整个网络的识别效果带来重要的影响。

在卷积层中，主要是输入图像或者特征图与卷积核进行卷积运算，卷积核以既定的步长与图像进行卷积运算，每次往后“滑动”一次就进行一次卷积，一个卷积核会产生一个特征图，n 个卷积核就会产生 $\mathrm { ~ n ~ }$ 个特征图。

卷积的计算公式为

$$
\mathbf { X } _ { j } ^ { l } = f ( \sum _ { i \in M _ { j } } X _ { i } ^ { l - 1 } ) ^ { * } K ^ { l } + b _ { j } ^ { l }
$$

其中：1代表卷积神经网络中的第几层；K为卷积核； ${ M } _ { { j } }$ 为感受野； $\mathbf { b } _ { j }$ 为偏置值。

池化/采样。目的主要是较少矩阵维度，减少计算量，常用的池化方法有最大值池化，平均值池化， $\mathrm { L } ^ { 2 }$ 范数池化，基于中心像素距离的加权平均数池化等等[13]。池化的计算公式为

$$
x _ { j } ^ { l } = \beta _ { j } ^ { l } d o w n s a m p l e ( X _ { \mathrm { j } } ^ { l - 1 } ) + b _ { j } ^ { l }
$$

# 1.3 Softmax分类器

主流的分类器主要有Softmax分类器，SVM分类器，贝叶斯分类器等[14]。本文选用softmax分类器。Softmax分类器主要用来解决多分类问题，即样本类标签y的可取值个数 $\mathbf { k }$ 满足$k > 2$ 。现在有训练集 $\left\{ ( x ^ { ( 1 ) } , y ^ { ( 1 ) } ) , \cdots ( x ^ { ( m ) } , y ^ { ( m ) } ) \right\}$ ，其中的$y ^ { ( i ) } \in \{ 1 , 2 \cdots k \}$ 。该分类器是一种有监督的学习算法，输入的样本间类别要十分明确，同一个样本不能同时属于多个类别。假设输入为 $\mathbf { x }$ ，那么它是类别j的概率表示为 $p ( y = j / k )$ 。具体来说，Softmax分类器所对应的神经网络的假设函数为

$$
h _ { \theta } ( \mathbf { x } ^ { ( \mathbf { i } ) } ) = \left[ \begin{array} { l } { p ( \mathbf { y } ^ { ( \mathbf { i } ) } = 1 \bigg \vert x ^ { ( \mathbf { i } ) } ; \theta ) } \\ { p ( \mathbf { y } ^ { ( \mathbf { i } ) } = 2 \bigg \vert x ^ { ( \mathbf { i } ) } ; \theta ) } \\ { \quad \cdot } \\ { \quad \cdot } \\ { p ( \mathbf { y } ^ { ( \mathbf { i } ) } = k \bigg \vert x ^ { ( \mathbf { i } ) } ; \theta ) } \end{array} \right] = \frac { 1 } { \displaystyle \sum _ { j = 1 } ^ { k } e ^ { \theta _ { j } ^ { T } x ^ { ( \mathbf { i } ) } } } \left[ \begin{array} { l } { \theta _ { 1 } ^ { T } } \\ { e ^ { ( \mathbf { i } ) } x ^ { ( \mathbf { i } ) } } \\ { e ^ { 2 } x ^ { ( \mathbf { i } ) } } \\ { \quad \cdot } \\ { \quad \cdot } \\ { e ^ { \theta _ { k } ^ { T } x ^ { ( \mathbf { i } ) } } } \\ { e ^ { \theta _ { k } ^ { T } } x ^ { ( \mathbf { i } ) } } \end{array} \right]
$$

其中： $\boldsymbol { \theta } = \left[ \theta _ { 1 } , \theta _ { 2 } \cdots \theta _ { k } \right] ^ { T }$ ， $\theta _ { \mathrm { i } } \in R ^ { n + 1 }$ 表示第i个输出神经元与输入层相连接的权重； $\frac { 1 } { \displaystyle \sum _ { j + 1 } ^ { k } e ^ { \theta _ { j } ^ { T } { \bf x } ^ { ( i ) } } }$

出的概率值和为1[15]。

雷达辐射源信号时频特征区别很小，在区别较小的样本，Softmax会找到一个权重值，以近可能放大样本之间的差异，Softmax的分类会更加精细，SVM分类器主要用来区别较大的样本，并且Softmax分类器可以将logistics回归二分类问题变为k分类问题，每个类别利用公式得出输出概率，计算简单，所以，本文选用Softmax分类器。

# 2 基于DAE $^ +$ CNN的辐射源信号识别算法实现

对雷达辐射源信号进行短时傅里叶变换，得到时频图像，但是时频图像不能直接作为DAE网络的输入，因此需要对时频图像进行预处理。

# 2.1 图像预处理

以LFM信号s(t)为例进行说明，对LFM信号加汉明窗进行短时傅里叶变换，得到S(t,f)，如图4所示。

![](images/f93c91e5add545c4713dc09d7246f013ccfb4399059307e4fe5eacfa650e676c.jpg)  
图4LFM信号时频图像

对时频图像每个点作归一化处理

$$
S ^ { \alpha } ( t , f ) = \frac { \left| S ^ { \alpha } ( t , f ) \right| } { \left| S ( t , f ) \right| _ { \operatorname* { m a x } } }
$$

将图像转换为灰度图像，如图5所示，

![](images/0084ecaa1c7762a9938bffda50e824f0c83eba28c42e24e74b60ad5b3db1b72f.jpg)  
图5时频图像灰度图

为了去除一部分噪声，减少噪声对后续识别的影响，对灰度图像进行阈值二值化操作，本文采用自动阈值分割选取阈值：

$$
\mathbf { S } ^ { \alpha } ( \mathbf { t } , \mathbf { \Delta f } ) \mathbf { \Psi } = \left\{ \begin{array} { l } { \mathbf { S } ^ { \alpha } ( \mathbf { t } , \mathbf { \Delta f } ) \mathbf { \Psi } { S } ^ { \alpha } ( t , f ) \geq t h r e d } \\ { \mathbf { 0 } \qquad \quad \mathbf { S } ^ { \alpha } ( t , f ) < t h r e d } \end{array} \right.
$$

将处理后的时频图像进行向量化操作，变成向量 $\boldsymbol { \alpha } _ { n } ^ { T }$ ，作为特征向量输入到网络模型中，那么 $\mathfrak { n }$ 个输入样本就可以表示成

$$
V { = } \big ( \alpha _ { o } ^ { \tau } , ~ \alpha _ { \scriptscriptstyle 1 } ^ { \tau } , { \cdots } { \alpha _ { n } ^ { \tau } } \big ) ^ { T }
$$

# 2.2 DAE降维

DAE降维主要是利用隐藏层神经元进行数据压缩，利用压缩后的数据尽可能保留原数据特征，经过隐藏层输出的数据的维度为隐藏层神经元个数。

单个样本维数为 ${ \mathfrak { m } } , { \mathfrak { n } }$ 个输入样本，所以输入样本$V \in R ^ { n \times m }$ ,DAE 第一层神经元个数为 $\mathrm { \Delta h }$ ，偏置项为 $b \in { \boldsymbol { R } } ^ { n \times 1 }$ ，权值矩阵为 $\boldsymbol { W } \in \boldsymbol { R } ^ { m \times h }$ ，特征输出为Z。

$$
Z = f ( V W + b )
$$

式（13）与（1）中产生差异的原因是样本数据行列发生转置，本实验中用行数 $\mathrm { ~ n ~ }$ 代表样本数，列数 $\mathfrak { m }$ 代表单个样本维数，与前面介绍发生转置，不影响结果。在这里由于b的维数与前面的维数不一样，不能相加，所以，必须要复制b的维数，会导致计算量特别大。因此，在实验中，直接在输入样本中加入一列1元素，作为偏置项，这样输入样本就变成 $V \in R ^ { n \times ( m + 1 ) }$ ，相应权值矩阵变为 $W \in R ^ { ( m + 1 ) \times h }$ 。输出矩阵 $\boldsymbol { Z } \in \boldsymbol { R } ^ { n \times h }$ 。这样数据就从原m维变成h维，维数就是隐藏层神经元的个数。

# 2.3本文算法识别流程

本文提出的算法框架(图6)流程如下所示：

a)数据预处理。对雷达辐射源信号进行短时傅里叶时频变换，对信号的时频图像进行图像处理，主要包括归一化、灰度、阈值二值化操作，最后将处理后的时频图像进行向量化操作，得到输入样本 $V _ { \mathrm { ~ ~ } }$ 0

b)将 $\nu$ 输入到DAE 网络中，调节网络参数，确定合适的网络结构，输出特征矩阵 $H _ { \circ }$

c)将 $\pmb { H }$ 重构成图片矩阵,输入到卷积神经网络中，确定合适的卷积神经网络参数。

d)分类识别。结合本文的深度学习模型和识别任务，利用最后的Softmax分类器进行分类识别，输出每一种信号的识别概率。

![](images/1914621d7504b722246d8f5bcc3f9aba5401c4c6c520fcf1a67829a3f863c5dd.jpg)  
图6算法运行框图

# 3 仿真实验

为了验证本文算法有效性和准确性，利用常见雷达辐射源信号进行仿真实验，分别是常规信号(CW)、二相编码信号(BPSK)、二频率编码信号(BFSK)和四频率编码信号(QFSK)、线性调频信号(LFM)、非线性调频信号(NLFM)。信号参数设置载频为 ${ 2 0 0 } \mathrm { M H z }$ ，采样率为 $2 \mathrm { G H z }$ ，BPSK和BFSK采用11位Barker码，QFSK采用16位Frank码，信号在信噪比-6dB到4dB 的范围内，每种信号每隔2dB产生200个辐射源信号,作为测试集，在 $S N R \in [ 0 d B , 1 0 d B ]$ 范围内每种信号随机产生 500 个样本，六种信号总共3000个样本作为训练集。

在探讨 $\mathrm { \Delta D A E + C N N }$ 模型对辐射源信号识别的具体效果之前，首先搭建CNN进行单独识别，然后再进行比较分析。

实验1利用CNN作为深度学习结构，确定网络参数：两层卷积层，第一层12个卷积核，第二层6个卷积核，卷积核大小都是 $5 { * } 5$ ，下采样层为 $^ { 2 * 2 }$ ，学习率为1，使用均值采样。输入为 $4 0 { * } 4 0$ 矩阵，改变信噪比进行仿真，如表1所示。

通过表1分析到，单独利用CNN框架结构对辐射源信号进行识别，能够取得很好的识别效果，在 $S N R { = } { - } 6$ dB 的时候，识别率达到 $9 0 \%$ 以上，但是时间复杂度较高，单次迭代时间21.75s,深度学习通过多次迭代训练，达到学习特征的目的，通过牺牲大量时间达到高识别率，在实际中往往不是有很大的使用价值，所以有效降低时间复杂度很有必要。

实验2将输入数据利用DAE 降维模型中，模型结构设置两层隐藏层网络结构，隐藏节点分别为1400和1024，然后将经过两个隐藏层后的输出数据 $3 0 0 0 * 1 0 2 4$ 重构成 $3 2 * 3 2 * 3 0 0 0$ 输入到CNN结构中，模型结构也是保持与实验1模型一致；同时进行另一组实验，将一开始的输入数据分别利用PCA、随机投影（RP）、联合 $\mathrm { P C A } { + } \mathrm { R P } ^ { [ 3 ] }$ 进行降维，也降维成 $3 2 * 3 2 * 3 0 0 0$ ，输入到同样的CNN结构中，实验数据如表2所示。

表1基于CNN 辐射源信号识别效果 $( \% )$   

<html><body><table><tr><td rowspan="2">深度学习结构</td><td colspan="6">SNR(dB)</td><td rowspan="2">单次迭代时间t/s</td></tr><tr><td>-6</td><td>-4</td><td>-2</td><td>0</td><td>2</td><td>4</td></tr><tr><td>CNN</td><td>92.82</td><td>98.83</td><td>99.72</td><td>100</td><td>100</td><td>100</td><td>21.75</td></tr></table></body></html>

表2不同降维模型结构识别效果对比  

<html><body><table><tr><td rowspan="2">不同模型结构</td><td colspan="6">SNR(dB)</td><td rowspan="2">单次迭代时间t/s</td></tr><tr><td>-6</td><td>-4</td><td>-2</td><td>0</td><td>2</td><td>4</td></tr><tr><td>PCA+CNN</td><td>42.26</td><td>57.47</td><td>69.15</td><td>81.75</td><td>90.14</td><td>96.68</td><td>9.84</td></tr><tr><td>RP+CNN</td><td>39.86</td><td>54.81</td><td>64.32</td><td>77.62</td><td>88.42</td><td>96.41</td><td>8.47</td></tr><tr><td>(PCA+RP)+CNN</td><td>45.21</td><td>61.56</td><td>75.23</td><td>85.67</td><td>93.77</td><td>98.62</td><td>10.12</td></tr><tr><td>DAE+CNN</td><td>84.96</td><td>93.25</td><td>99.45</td><td>100</td><td>100</td><td>100</td><td>14.53</td></tr></table></body></html>

通过表2可以分析到，由于输入到CNN网络中的数据维度大幅度下降，导致 $\mathrm { D A E + C N N }$ 模型较CNN 模型时间缩短了8s 左右，一次迭代快8s，深度学习训练需要迭代多次，所以可以节约大量的时间。 $\mathrm { \Delta D A E + C N N }$ 识别效果较原模型CNN在$S N R \leq - 4 d \mathbf { B }$ 有所下降，主要是因为降维后的数据与原数据相比很难保持所有的特征，会造成特征缺失，导致识别效果出现下降，但是在 $S N R \geq 2 d B$ ， $\mathrm { D A E + C N N }$ 的识别效果与CNN 基本一致，在综合时间复杂度和识别效果， $\mathrm { \Delta D A E + C N N }$ 模型更具有应用价值，更符合实际应用场景。在PCA、RP和 $\mathrm { P C A } { + } \mathrm { R P }$ 降维方法模型中，$\mathrm { P C A } { + } \mathrm { R P }$ 联合降维的效果最好，因为联合降维既保留PCA的能量特征又保留了随机投影的子空间较小失真度的特征，但是与DAE降维效果相比，识别效果差距很大，因为DAE可以保持多种特征，特征越多更有利于后续的CNN训练学习，识别效果也会越好。

实验3利用DAE 降维，改变 DAE 结构，同样使用两层隐藏层结构，隐藏神经元个数分别为1400、625，将输入数据降成625维，其它条件不变，探究维度不同对实验结果的影响，如图7所示。

![](images/b5753f8c247ffd85f399799889fcc12c9097f8ee13764458218163209e73b569.jpg)  
图7不同维度对识别效果的影响

从图7可以分析到，数据的维度对识别结果有很大影响，利用同样的降维方式降到不同的维数，维数高的数据识别效果好，维数低的识别效果差。在信噪比高的情况下，缩小输入数据维度会造成特征缺失，信噪比低的情况下，会造成数据失真，但是在 $\mathrm { S N R { = } 2 }$ dB 的情况下，625维的输入数据还是能够达到$1 0 0 \%$ 。

实验4上述实验中将数据降维到设定维数都是通过两次隐藏层实现降维，在此次实验中，分别改用一层和三层隐藏层实现降维，都在经过1024这层隐藏层时将数据提取出来，然后输入到CNN结构中，参数设置不变，进行实验，如图8所示。

![](images/51e01eb53f5fa5244d1ccfa546f655956c986859acc78e9d80a864b14d1d0208.jpg)  
图8不同隐藏层层数识别效果对比

从图8分析得到，DAE中设置三层隐藏层降维的识别效果最差，两层的效果最好。浅层DAE结构通过一个隐藏层就可以完成降维，这会导致编码的过程中损失信息现象严重，重构误差大。但是深层次的DAE结构，利用三层的隐藏层结构完成降维也会造成识别效果下降，过深层次的结构由于编码次数较多，会造成提取特征更加抽象，损失细节信息，重构误差也会变大，识别效果变差，因此，需要确定合适的DAE结构才能使识别效果最佳。

# 4 结束语

本文利用降噪自编码器高效的非线性降维功能，对已经搭建好的卷积神经网络进行改进，降噪自编码器可以去除冗余信息，保留数据主要特征，对输入数据很好地实现高维向低维映射。通过仿真表明， $\mathrm { \Delta D A E + C N N }$ 模型的时间复杂度较CNN模型有大幅度降低，在 $\mathrm { S N R { = } { - } 2 }$ dB，识别效果基本一致，识别效果明显优于利用常规降维方式进行处理的模型。但是， $\mathrm { \Delta D A E + C N N }$ 模型在更低的信噪比的情况下识别效果不是很理想，如何进一步优化网络结构提高识别效果需要进一步研究。

# 参考文献：

[1]Frater M,Ryan M.Electronic warfare for the digitized battlefield [M]. Artech House, Inc.2001.   
[2] 郭立民，寇韵涵，陈涛，等．基于栈式稀疏自编码器的低信噪比下低截 获概率雷达信号调制类型识别[J].电子与信息学报,2018,40(4):875- 881.(Guo Liming,Kou Yunhan,Chen Tao.Et al.Low probability of intercept radar signal recognition based on stacked sparse auto-encoder [J]. Journal of Electronics & Information Technology,2018,40(4):875-881.)   
[3] 周志文，黄高明，高俊，等．一种深度学习的雷达辐射源识别算法[J]. 西安电子科技大学学报，2017,44 (3):77-82.(Zhou Zhiwen,Huang Gaoming, Gao Jun,et al Radar emitter recognition algorithm based on deep learning [J]. Jourmal of Xidian University,2017,44 (3): 77-82.)   
[4]方成，薛质．基于全双谱和卷积神经网络的信号分类方法[J].计算机 应用研究,2018,35 (12).htp://www.arocmag.com/article/02-2018-12- 022.html (Fang Chen, Xue Zhi. Signal classification method based on complete bispectrum and convolutional neural network [J].Application Research of Computers,2018,35 (12).   
[5]Yang Jian, Yang Jingyu.Why can LDA be performed in PCA transformed space [J].Pattern Recognition, 2003,36 (2): 563-566.   
[6]Hinton G E,Salakhutdinov R R,et al. Supporting online material for"reducing the dimensionality of data with neural networks”[J]. Science, 2006,504 (5786):504-507.   
[7]Pang Yanwei,Yuan Yuan,Li Xuelong.Gabor-based region covariance matrices for face recognition [J]. IEEE Trans on Circuits & Systems for Video Technology,2008,18(7): 989-993.   
[8]Zeng Kun,Yu Jun, Wang Ruxin, et al. Coupled deep autoencoder for single image super-resolution [J]. IEEE Trans on Cybernetics,2017,47(1): 27-37.   
[9] 张一飞，陈忠，张峰，等．基于栈式去噪自编码器的遥感图像分类[J]. 计算机应用,2016,36(2):171-174.(Zhang Yifei,Chen Zhong,Zhang Feng, etal. Remote sensing image classification based on stacked denoising autoencoder [J]. Journal of Comuputer Application,2016,36 (2): 171-174.)   
[10] Shao Ling,Cai Ziyun,Li Liu,etal. Performance evaluation of deep feature learning for RGB-D image//video classification [J]. Information Sciences, 2017,385 (C): 266-283.

[11]杨予昊，孙晶明，虞盛康，等．基于卷积神经网络的高分辨距离像目标 识别[J]．现代雷达，2017(12):24-28.(Yang Yuhao,Sun Jingming,Yu sheng-kang,etal. High Resolution Range Profile Target Recohnition Based on Convulution Neural Network [J].Modern Radar, 2017(12):24-28.)

[12] Zhang Kai, Zuo Wangmeng,Chen Yunjin,et al.Beyond a Gaussian denoiser: residual learning of deep CNN for image denoising[J].IEEE Trans on Image ProcessingAPublication of the IEEE Signal Processing Society,2017,26 (7):3142-3155.

[13] Niu Xiaoxiao,Suen Ching.A novel hybrid CNN-SVM classifier for recognizing handwritten digits [J].Pattern Recognition,2012,45(4):1318-

1325.

[14]陈景年，黄厚宽，田风占，等．一种有效的不完整数据分类器[J]．计 算机科学,2008,35(9):162-164.(Chen Jinnian,Huang Houkuan,Tian Fengzhan,etal. Effective Classifier for Incomplete Data [J]. Computer Science,2008,35 (9):162-164.)

[15]刘亚冲，唐智灵．基于softmax 回归的通信辐射源特征分类识别方法 [J].计算机工程,2018,44(2).(Liu Yachong,Tang Zhiling.Classification and identification method of communication radiation sourse feature based on softmax regression [J].Computer Engineering,2018,44(2): 98-102.)