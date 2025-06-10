# 基于跳白块编码和深度神经网络对脉冲星候选体诊断图像的压缩研究

姜家涛1.2,3，\*谢晓尧1.3，于徐红1.3

(1.贵州师范大学，贵州省信息与计算科学重点实验室，贵州贵阳 550001;2.贵州师范大学,数学科学学院,贵州贵阳 550001;3.FAST早期科学数据中心 贵州贵阳 550001)

摘要：FAST脉冲星搜索产生的候选体诊断图量级呈指数级增长，给科学数据管理工作带来挑战,迫切需要研究压缩方法实现诊断图的有效存储和加快其在网络中传输共享。脉冲星诊断图像由稀疏的黑白图像、随机分布的灰度图和彩色图像组成，简单视为彩色图像用同一种压缩方法处理显然是不合理的。提出跳白块编码和深度网络压缩编码压缩模型对脉冲星候选体诊断图分区压缩。使用近年来FAST巡天搜索项目脉冲星候选体诊断图来训练和验证。结果表明，改进的WBS压缩稀疏黑白图像的性能是PNG的5倍；深度网络压缩算法处理灰度图和彩色图PSNR性能优于JPEG和JPEG200O算法，与BPG算法性能相当，SSIM性能远超传统压缩算法。

关键词：候选体诊断图压缩；深度网络压缩模型；跳白块编码；500米口径球面射电望远镜；图分类号：P162文献标识码：A

# 1引言

自2016 年9月 500 米口径球面射电望远镜FAST(Five-hundred-meter Aperture Sphericalradio Telescope)在我国贵州落成[1]以来，脉冲星搜索一直是 FAST 重要科学项目之一。截止目前 FAST 早期科学数据中心已计算发现了240个新的脉冲星候选体[2]，其中123 颗脉冲星候选体已经证实为新脉冲星。J1859-0131和J1931-01是我国射电望远镜首次发现两颗新脉冲星。 $\mathbf { J 0 } 3 1 8 \substack { + 0 2 5 3 }$ 是FAST发现的首个毫秒脉冲星[3]，是至今发现的射电流量最弱的高能毫秒脉冲星之一，展示了FAST对国际低频引力波探测做出实质贡献的潜力，是FAST的重要成果。巡天观测数据经过计算处理[4,产生海量级脉冲星候选体诊断图图像。以每天处理 2000个数据文件为例，单日产生图像就达300000张，存储空间需要 20G，脉冲星候选体诊断图量级呈指数级增长，给科学数据管理工作带来挑战。脉冲星候选体诊断图像是天文科学家们对巡天数据进行检查、脉冲星搜索判断重要科学数据，是探究新搜索技术方法的数据基础，是天文科研科普开放共享的重要资源。日常工作中脉冲星识别软件在专用网络中不断传输脉冲星候选体诊断图像；科学家基于脉冲星候选体诊断图像探索新的科研方法，如 zhu 等[2]提出PICS方法；FAST云平台上公布的共享信息包含大量的脉冲星候选体诊断图。因此，研究压缩技术实现脉冲星候选体诊断图像有效存储与加快其在网络中传输共享迫切必要。

传统主流图像标准算法，如 JPEG[5],JPEG2000lBPG 等，采用变换编码。JPEG 对图像分块作DCT变换，将图像信息从空间域变换到系数能量相对集中的到DCT域，然后量化变换系数和熵编码错误!未找到引用源。；而 JPEG2000 对图像做离散小波变换DWT，分层熵编码。但DCT、DWT变换是固定不变的线性变换函数，近似固定卷积核图像卷积操作，手工设计的变换矩阵对脉冲星图像数据去相关性不一定是最优的。近年来神经网络学习的图像压缩编码方法[7}-[10越来越受到研究者青睐。Toderici等[提出基于RNN 图像编码框架，Balle 等提出了基于卷积神经网络的压缩编码结构，学习网络瓶颈层数据表征的分布熵模型，更好地移除了图像的内部冗余。基于神经网络图像压缩利用大量图像优化学习，在对图像去相关紧凑化压缩变换方面比传统手工设计压缩模块方法更有效。但是现有压缩方法都是针对自然图像的，没有充分考虑到脉冲星诊断图像不同于自然图像特性。脉冲星诊断图像由稀疏的黑白图像、随机分布的灰度图和彩色图像组成，简单视为彩色图像用一种变换压缩算法处理显然是不合理的。

针对脉冲星候选体诊断图的特征提出使用跳白块编码和和深度网络图像压缩模型相结合的压缩方法。针对诊断图像的曲线和文字等黑白图像，首先二值化图像，然后使用改进的自适应分层跳块算法压缩。对于深度神经网络压缩模型的设计，首先，图像压缩模型采用卷积神经网络自编码器结构，整体结构由正向编码网络、量化器、熵编码器和反向编码网络组成。其次，将量化特征的编码率与失真误差的加权和作为损失函数，利用大量脉冲星候选体诊断图像自适应地学习各个模块函数，基于 SGD方法。为了有效使用算术编码器工作，对潜在表示特征的分布使用网络学习非线性函数逼近实际的数据分布模型。为了验证提出算法的有效性，实验将FAST近年来巡天项目生成的脉冲星候选体诊断图作为数据集，分别应用 JPEG、JPEG2000 算法、BPG 算法和本文提出的DNCM算法比较。结果表明，DNCM算法的PSNR值优于JPEG 算法与JPEG2000 相当，但SSIM值远远超过传统压缩算法，特别是在低比特率下重构图像较高的SSIM值保证了图像感官质量。诊断图本是目视判断脉冲星候选体的辅助依据，证明了提出的算法的针对脉冲星候选体诊断图压缩应用的有效性。

# 2分区图像压缩

脉冲星候选体诊断图是观测数据经过消色散、周期折叠处理后得到可能的脉冲星旋转参数组合和统计量分布结果数据绘制图像[1，用于天文学家判定是否为脉冲星。如图1所示。

2 Pulses of Best Profile Search InformationCandidate:7.71ms_Cand RAJ2000 =15:27:30.5100 DECJ2000 45:39:44.9000Telescope:FAST Folding ParametersEpochiopo Epoch =58242.72949611111 58242.73297696025 DOF p7483 二 30:22 x / P(Noise）<1.01e-12（7.0σ) 7704788（33Datesded ■ 52219204 0.0(1.6）x10-10 Pobary (/27.Profile Bins = 64 Pob（s）=N/A e=N/AProfileAvg 1.479e+08 sin（i）/c（s）=N/A （rod）=N/AProfile StdDev 9264 =N/A10010 094 MwwM80 4×10” 2x108 中 (2H) aunbe -dot 2.2317e-13(s/s）34N210ai 5×10 0 -5×10°C 24 Period-7.70510179（ms）4 0.4 0.8 1.2 1.6 2 5/） Freq−129.784139(Hz) （/H）016+10-Phase OLx-20 2 X3peonpay Z 2。0.5 1 1.5 321 0 30 31 32 33 op-d 5x10 -5x10”\* -10Phase Reduced X² DM（pc/cm³） Period-7.70510179(ms)

诊断图主要包含8个子图，可以直观上可粗略分为三类，其中2、3子图为二维灰度散度图包含大量随机噪声点，1、4、5、6、7为稀疏的曲线图或文字表示的黑白图像，8为彩色图像。观察可知，子图们特征差异较大，图像通道数量不一，子图的数据稀疏程度差别较大，显然使用一种单一的压缩算法或一种压缩模型是不合理的。本文将图像区域划分三类，采用不同方法压缩编码，与黑白图像区域使用跳白块编码，灰度图和彩色图分别训练一个深度网络隐变量压缩模型。3类图像区域自动定位切割，并分发到对应编码器压缩处理。

# 2.1跳白块编码方法

跳白块编码是一种充分利用二值图像中单色区域占大部分位置的特征游程编码变体。一维跳白块编码也称跳白条，将二值图像的各扫描行分成若干块，每块 N 个像素[]。全白像素的块用1比特字“0”表示，对于至少含有一个黑像素的块，用 $\mathsf { N } { + } 1$ 比特码字表示；含有黑色像素的块的第1个比特位表示“1”称为前缀码；其余N比特直接自身的二值幅值表示，白为“0”，黑为“1”。推广到二维，将整个图像分割为 $M \times N$ 像素的块，若块为全白像素时用1比特“0”表示；非全白块用 $1 + M \times N$ 个比特码字表示；一个前缀比特“1”其余MN其余N比特直接自身的二值幅值表示。将脉冲星候选体图像中的1类区域分割出来，指定阈值变换成为二值图像，白色像素用“0”表示，黑像素用“1”表示。

如图2所示，用跳白块编码二值图像生成二进制数据流，再送入自适应算术编码器（QM编码器），进一步压缩数据流中的位流冗余。其中，在本文使用跳白块编码改进的自适应分层跳块算法。

![](images/e33d9985ac2864adbca631a8185a51a1dcbc5ec85c13ebd0b7e709e6b81674a6.jpg)  
Figure 2: White Block Skipping Coding for Binary Image

![](images/f2b63ed24c64094074da53edb15836c432913179434636997a5c3c549a6c1ffd.jpg)  
图2跳白块编码二值图像  
图3深度神经网络图像压缩模型结构图  
Figure 3.Architecture Diagram of Deep Neural Network Image Compression Model

# 2.2深度网络隐变量压缩模型

对于灰度图像和彩色图像，本文分别训练两个学习型的深度网络隐变量压缩模型压缩相应的图像块。深度网络隐变量压缩模型的整体网络结构是一个自编码器结构，如图3所示，压缩网络模型包含四个部分组成：分析变换网络模块 Encoder、量化器Quantizer,熵编码模块Entropy Coder 和集成变换网络模块 Decoder。分析变换网络 Encoder 由多个堆叠的卷积层组成，经过一系列下采样，提取特征去相关等变换操作，将输入图像映射到弱相关的紧凑的隐变量表示。潜在表示保留了图像的全部必要信息，是待编码的压缩信息。集成变换网络Decoder是 Encoder的逆操作，也是由一系列堆叠的逆卷积层组成，通过上采样生成图像信息。熵编码模块Entropy Coder是依赖神经网络学习得到的潜在表示分布的参数估计的模型，指导算术编码器将被量化器量化后的潜在表示信息生成可以保存和网络传输的二进制码流，即压缩信息。

分析变换 $E _ { \phi } ( x )$ 图像特征数据 $x$ 映射为潜在表示 $y$ ，量化器Quantizer 将量化为 $\hat { y }$ ， $y$ 熵模型 $Q ( \hat { \mathrm { y } } ; \theta )$ 中逼近潜在表示的统计分布，指导算术编码器将 $\hat { y }$ 编码为二进制流；解码时算术编码器依赖熵模型将二进制流重新译成量化特征 $\hat { y }$ ，集成变换 $D _ { \varphi } ( z )$ 将根据 $\hat { y }$ 的信息生成图像 $x ^ { \prime }$ 。这其中主要模块为分析变换器 $E _ { \phi } ( x )$ 、熵模型 $Q ( \hat { \mathrm { y } } ; \theta )$ 和集成变换器 $D _ { \varphi } ( z )$ 。与传统的变换编码方法不同，它们都是利用大量图像优化学习优化得到的，而非手工设计的。

神经网络基于一个损失函数，反向传播误差梯度，学习得到模型的参数 $( \phi , \theta , \varphi )$ ，以权值和偏置形式保存在神经网络中。本文采用RDO优化策略学习网络，即联合图像压缩损失和码率函数，拉格朗日乘子 $\beta$ 控制着码率与率失真的平衡。如公式(1)表示。

$$
L = D ( x , \hat { x } ) + \beta H ( \hat { y } )
$$

$$
s t . ~ H ( \hat { y } ) = - \mathrm { l o g } _ { 2 } \mathrm { p } ( \hat { \mathrm { y } } ) ~ , ~ \mathrm { D } ( x , \hat { x } ) = \left\| x - \hat { x } \right\| _ { 2 }
$$

# 2.2.1量化器

由于压缩编码的需要对潜在表示层输出 $y$ 量化处理，通常使用取整round操作。本文采用量化器量化间隔步长为1，用间隔的中心来表示量化输出。量化公式如下：

$$
\hat { y } _ { i } = q _ { i } = r o u n d ( y _ { i } )
$$

其中，指示符 $i$ 贯穿向量的所有元素，包括通道和空间坐标。这样做的好处是， $\hat { y } _ { i }$ 的的边际密度可以用一个可训练的离散概率质量函数得到，其权重等价于概率质量函数 $q _ { i }$ 。如下一小节中，公式（2）连续变量的边际密度可以由离散的概率密度函数的单位1的累积密度函数上下限差值逼近得到。

然而分析损失函数公式（1）可以发现，损失函数依赖于量化值，但是取整量化函数的梯度几乎总是0，使得码率R与失真D组成的损失函数不可微，这就导致无法再使用梯度下降优化损失。为了继续能够使用随机梯度下降优化，在训练过程中，我们加入独立同分布的随机均匀噪声 $\varepsilon$ 的实现抖动的量化器， $\varepsilon$ 的分布区间和量化器的量化间隔的宽度都等于1;在测试和实际编码过程中，我们直接使用取整函数；如公式（3）表示。

$$
\hat { y } _ { i } = q _ { i } = \left\{ \begin{array} { l l } { r o u n d ( y _ { i } + \varepsilon ) , \quad \varepsilon \sim u ( - 0 . 5 , 0 . 5 ) } \\ { r o u n d ( y _ { i } ) \quad \quad , w h e n \ t e s t i n g } \end{array} \right.
$$

# 2.2.2分段线性函数熵模型

图像压缩模型需要对分析变换得到的紧凑的潜在表示信息无损编码，生成二进制码流，本文采用算术编码实现熵编码。算术编码算法是一种基于信源信息统计的概率分布将所有编码信息映射到实轴上[0,1)内的小区间表示的最优无损熵编码算法。算术编码的基础是的潜在表示分布模型的精准估计，影响码率R和损失D，即压缩器的压缩性能，我们使用一个网络无参数分段线性密度函数模型逼近实际数据的分布。

假定潜在表示空间中数据是独立同分布，则可以建立一个完全因子分解模型，其似然函数为样本的积分，如公式（4）。概率密度模型有潜在表示数据先验分布密度函数卷积一个标准均匀分布密度函数得到，将编码器的输出特征映射作为输入，生成潜在表示特征的概率密度。

$$
\begin{array} { c } { { p _ { \psi } ( \hat { y } _ { i } ) { = } \prod _ { i } p ( q ( \mathrm { y } _ { \mathrm { i } } ) ^ { * } u ( { - } 0 . 5 , 0 . 5 ) ) } } \\ { { { } } } \\ { { { = } c ( \hat { y } _ { i } + 0 . 5 ) { - } c ( \hat { y } _ { i } - 0 . 5 ) } } \end{array}
$$

其中 $c ( * )$ 是先验分布密度模型的累积函数，得到一个以实际数据 $y _ { i }$ 为中心的单位概率质量密度。

参考8设计一个基于深度神经网络的无参数分段线性密度函数模型，通过迭代训练优化实现样本数据与模型之间的拟合。使用卷积网络构建的无参数分段线性密度函数，包括 K个阶段的非线性变换函数卷积，其中第K阶段向量映射函数 $f _ { K } : R ^ { m } \to R ^ { n }$ ，其中 $f _ { \scriptscriptstyle K }$ '为密度 $f _ { \scriptscriptstyle K }$ 的梯度，是一个雅克比矩阵，可以将模型的累计密度链式计算法则表示如下：

$$
\mathsf { c } = f _ { \boldsymbol { K } } \mathsf { o } f _ { \boldsymbol { K } - 1 } \Lambda f _ { 1 }
$$

$$
p = f _ { \boldsymbol { K } } ^ { \phantom { * } } { } ^ { \prime } f _ { \boldsymbol { K } - 1 } ^ { \phantom { * } } { } ^ { \prime } \Lambda \ f _ { 1 } ^ { \prime }
$$

非线性函数具体实现公式如下：

$$
f _ { k } ( \boldsymbol { x } ) = g _ { k } ( H ^ { ( k ) } \boldsymbol { x } + \boldsymbol { b } ^ { ( k ) } ) \qquad 1 \leq k < K
$$

$$
f _ { \scriptscriptstyle K } ( x ) = s i g m o i d ( H ^ { \scriptscriptstyle ( K ) } x + b ^ { \scriptscriptstyle ( K ) } )
$$

$$
g _ { \boldsymbol { k } } \left( \boldsymbol { x } \right) = \boldsymbol { x } + a ^ { ( k ) } \mathrm { o t a n h } ( \boldsymbol { x } )
$$

其中 $f _ { k } ( x )$ 表示量化函数前面 $1 \leq k < K$ 层变换函数形式； $f _ { K } ( x )$ 为量化函数最后一层函数形式，使用非线性激活函数 $\sigma ( \cdot )$ 将概率分布映射到一个[0,1]区间，即是概率密度的标准分分布。

# 3实验与结果分析

实验将近年来FAST脉冲星搜索巡天项目的部分结果数据作为图像压缩训练集和测试模型，数据源包括脉冲星图像样本1159个和RFI图像样本998个8位无损PNG图像。网络模型是在NVIDIA GeForce GTX1080 GPU上使用Pytorch 框架实现的。为了验证提出算法性能，随机从测试集中抽取5幅脉冲星图像，测试压缩算法。对黑白图像处理后使用跳白码压缩和PNG压缩结果比较；灰度图和彩色图区域，将本文设计的深度压缩算法与JPEG、JPEG2000、BPG 算法比较。其中，JPEG 采用开源库 libjpeg，JPEG2000 使用 openjpeg 实现，BPG 使用开源库 libbpg。

# 3.1跳白块编码过程

分割候选体诊断图中1类图像区域，此类图像区域为稀疏的黑白图像，计算像素幅值直方图选定阈值为200，将图像二值化映射为{0,1}。其次选择跳白块尺寸，经过大量候选体诊断图像压缩实验，选取最优跳白块尺寸大小为5X4，获得最优压缩码流。最后跳白块编码后送入QM算术编码器。

# 3.2深度网络模型结构

自编码器的输入与输出尺寸一致，即输入图像的大小通道数与压缩模型重构图像大小一样。本文设计的压缩网络，图像块大小256x256,Encoder模块包括4个卷积层和3个GDN层，4个ResNet层。卷积层2倍下采样，第1个卷积层用128个 $9 \mathrm { x } 9$ 的卷积核，步长2，填充位4；第2和第3个卷积层有128个5x5卷积核，步长为2，填充2，bottleneck层也是卷积层，步长2，填充2，可调节通道数指定16x16特征图数量控制码率。Decoder 模块的与Encoder 模块参数相似，Conv2d 替换为ConvTranspose2d，顺序相反。

本文的网络模型基于RDO优化，即压缩损失Distortion 和码率Rate 联合作为目标损失函数，针对灰度图和彩色图训练了两类压缩模型。其中 $\lambda$ 为拉格朗日乘子，用作调节不同的Distortion与Rate组合满足不同压缩质量要求的场景，即可变码率压缩。在实验中，我们训练了10中 $\lambda$ 模型，λ 取值（16,32,64,128,512,1024,2048,4096.6144,8192）。以自适应动量估计算法（ADAM）来优化模型，初始学习率为 $1 0 ^ { - 3 }$ ，动量因子为0.99，权重衰减率 $1 0 ^ { - 4 }$ 。迭代优化次数设置为100000次，每次迭代的训练样本批次大小为16。首先训练高码率模型，然后基于这个模型作为预训练模型分别调整 $\lambda$ 值训练其他模型。

# 3.3实验结果与分析

跳白块编码性能评价。将候选体诊断图中1类图像区域，用改进的WBS压缩的结果与WBS 基本压缩和PNG 压缩结果比较，如表1所示，结果显示改进的WBS 压缩性能是 PNG的5倍，加入了QM的WBS压缩性能得到进一步提升；从图5可以看到，PNG 和WBS 的黑白图像基本相同，PNG 图像边缘更平滑。

表1跳白码编码与PNG编码比较  
Table1: Compare Preformance of WBS and PNG   

<html><body><table><tr><td></td><td></td><td>img1</td><td>img2</td><td>img3</td><td>img4</td><td>img5</td></tr><tr><td rowspan="2">WBS</td><td>num of bits</td><td>237866</td><td>238666</td><td>235646</td><td>231986</td><td>243126</td></tr><tr><td>bpp</td><td>0.23</td><td>0.23</td><td>0.23</td><td>0.22</td><td>0.23</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">PNG</td><td>num of bits</td><td>1020392</td><td>1079816</td><td>1038808</td><td>970120</td><td>1114472</td></tr><tr><td>bpp</td><td>0.98</td><td>1.03</td><td>0.99</td><td>0.93</td><td>1.07</td></tr><tr><td>NEW</td><td>num of bits</td><td>201548</td><td>202144</td><td>199230</td><td>196092</td><td>206869</td></tr><tr><td>WBS</td><td>bpp</td><td>0.193</td><td>0.194</td><td>0.191</td><td>0.188</td><td>0.198</td></tr></table></body></html>

2 Pulses of Best Profile Search Information Candidate:15.14ms_Cand RAJ2000=20:51:41.4500 DECJ200 =45:32:07.8000 Telescope:FAST Folding Parameters Epochtope=58242.95401759259 DOFeff=44.53Xreg=17.014P(Noise）<2.16e-183（28.9g) Epochbary = 58242.95348284396 Dispersion Measure (DM; pc/cm³) = 448.000 Data Folded =5.0002 ( Data Avg = 3.481e+04 p(s/s=00（7.8）x1（s/s=078）1 Data StdDev ■ 211 Binary Parameters Profile Bins ■ 64 Por(（s)=N/A e = N/A Profile Avg 2.83e+08 asin(i)/c (s) = N/A ω (rad) = N/A Profile StdDev 1.903e+04 Tperi =N/A (a) PNG 2 Pulses of Best Profile Search Information Candidate:15.14ms_Cand RA2000=20:51:41.4500 DECJ2000=45:32:07.8000 Telescope:FAST Folding Parameters Epochtopo=58242.95401759259 DOFen=44.53Xrg=17.014P(Noise）<2.16e-183（28.9g) Epochbery =58242.95348284396 Dispersion Mecsure(DM; pc/cm)=448.000 Data Folded ample =0.0002 =520192 Ptopo(ms）=15.141968(17） (s/s）=-2.6（1.2） Pby(ms）=15.142658(17） by(/s)=2.6（1 DataAvg =3.481e+04 (s/s）=0.0（7.8）0 bry (s/s）=0.0（7.8）x10-1 Data StdDev =211 Binary Parameters Profile Bins 4 64 P（s）=N/A e = N/A Profile Avg =2.83e+08 sin(i)/c(s)=N/A ω (rad)= N/A Profile StdDev = 1.903e+04 Teri =N/A (b) WBS

网络模型客观评价。设置灰度图像区域和彩色图像的神经网络潜在表示层通道数分别为$\scriptstyle 1 = 6 4 , 1 2 8$ ,下采样倍率为16，训练深度网络压缩模型。由于两类模型方法相同，受篇幅限制，文中仅描述彩色图像网络模型在不同码率下的PNSR和SSIM性能。实验结果如图5-b 为PSNR-Rate曲线，反映各种算法在不同码率下解码图像与原本图像像素之间均方误差。整体上，提出深度网络压缩模型(DNCM)算法性能与JPEG2000 相近，明显优于JPEG 算法但不及BPG 算法。在bpp 为0.4时,我们DNCM的PSNR 值为31dB,与JPEG2000 交叉，比 JPEG高1.4dB，比BPG算法低8dB。压缩效果就明显优于JPEG和JPEG压缩算法，接近于BPG算法。接近无损压缩时，传统压缩算法超出神经网络方法，这是卷积神经网络的过平滑造成的.图5-b为SSIM-码率曲线，反映各种算法在不同码率下解码图像与原本图像图像结构相似度 SSIM.BNCM 算法明显高于 JPEG 和 JPEG2000 算法，略高于 BPG 算法。在bpp 为0.2时，DNCM算法的 SSIM值高于0.99,而最好的传统算法BPG 的 SSIM值为0.95，而 ${ \tt b p p } { < } 0 . 7$ 时，DNCM算法 SSIM依然高于0.95,说明在较低比特率高压缩比情况下，DNCM算法在保持图像感知质量上的绝对优势。

网络模型主观评价。如图6所示，展示了不同的图像压缩算法在相近码率的视觉结果。可以看到，JPEG 算法出现块效应，我们提出的DNCM算法多数情况下与BPG性能相近，比JPEG和JPEG2000效果好，图中两幅诊断图彩色图在相对小的码率下取得最好的视觉质量。

总之，脉冲星诊断图包含大量稀疏的曲线、随机噪声点灰度图和彩色图像块，任何一种传统的有损压缩算法都不是最优选择，而本文依据分区策略利用跳白块编码和神经网络压缩模型对诊断图像压缩具有针对性专用性。曲线文字图像块，转化为二值图像后跳白块压缩几乎没有损失却得到极高的压缩比；特别是网络压缩模块的功能函数是利用大量的诊断图学习得到，最大程度反映了诊断图像数据空间特征，进一步反应得到模型的专用性。脉冲星诊断图最重要的作用是辅助人类目视判断脉冲星候选体，识图时观测的重点就是曲线图像的结构和这子图图像中结构信息，本文提出算法在低比特率下任保持较高的 SSIM值反映了视觉感

知质量上的优势。

![](images/4cc7b74e7d280e3009d430343654f48c39f20d22ceb45ae09f86ff56cd41f9e6.jpg)  
图5图像压缩PSNR、SSIM性能率失真曲线比较

Figure 5 : Rate-Distortion Curves of Image Compression Using PSNR and SSIM Metric

![](images/c87f51ff4683c6ef6434d06a49a013be1edb67a04dc63aa0ba26897b4370187b.jpg)  
图6可视化结果比较JPEG,JPEG2000,BPG 和DNCM的质量 Figure 6 : Visual Comparsion among JPEG,JPEG2OO0,BPG,DNCM and Original Image

# 4结束语

脉冲星诊断图像由稀疏的黑白图像、随机分布的灰度图和彩色图像组成，简单视为彩色图像用一种变换压缩算法处理显然是不合理的.为此，本文提出跳白块编码和深度网络压缩方法对诊断图像分区压缩。跳白块编码是针对单色区域占大部分的二值图像具有较好压缩效果的方法，提取脉冲星诊断图中的曲线子图和文字描述子图，选定量化阈值，将图像二值化为比特位矩阵表示的图像，选取最优跳白块尺寸实现WBS编码后送入QM压缩器进一步提升压缩性能，最终压缩比是PNG的5倍。基于深度网络压缩方法对灰度图和彩色图分别训练模型。深度网络压缩模型是由卷积神经网络实现的自编码器结构，由分析变换编码网络、量化器、熵编码器和合成变换编码网络组成。各个压缩模块均由学习方法利用大量脉冲星候选体诊断图像优化；变换映射能力比传统手工设计模块更有效，图像经过分析变换映射为潜在表示，是去相关的更紧凑的图像信息表示；学习到的熵编码模块是对潜在表示空间的分布的拟合逼近，是比累积概率直方图更精准的更容易操作的概率模型，指导基于统计分布的算术编码器无损编码。实验结果表明，提出深度网络压缩算法对近年来FAST巡天搜索项目脉冲星候选体诊断图的压缩性能，在PSNR比较上优于 JPEG 算法与JPEG2000 相当，而 SSIM性能比较远超过传统压缩算法。本文充分利用子图间特征显著差异性，制定分区压缩策略将图像分成三类子图区域，依赖子图图像特征分别使用WBS和深度网络压缩方法，提升了编码效率。我们也观察到，本文中利用神经网络实现的熵估计模型是十分简洁易操作的方式，估计的熵模型是否能够精准有效性匹配真实的潜在分布直接影响码率 Rate 和损失Distortion，因此，考虑新方法提高熵模型的精准估计可以进一步改善压缩性能。

# 参考文献：

[1] Xu Yuyun,Li Di,Liu Zhijie,Wang Chen,Wang Pei,Zhang Lei,Pan Zhicheng. Application of Aritificial Intelligence in the selection of Plusar Candidate[J]. Progress in Astronomy，2017, 35(003):304-315.   
[2] Zhu W W， Berndsen A， Madsen E C ,et al. Searching for Pulsars Using Image Pattern Recognition[J]. The Astrophysical Journal, 2014, 781(2):117.   
[3] Qian L,Pan Z C,Li D ,et al. The first pulsar discovered by FAST[J].Scientia Sinica Physica, Mechanica & Astronomica,2019,62(5):71-74.   
[4] Yu Q,Pan Z, Qian L,et al. A PRESTO-based Parallel Pulsar Search Pipeline Used for FAST Drift Scan Data[J]. Research in Astronomy and Astrophysics,2019,20(6):215:222.   
[5] Wallace G K . The JPEG still picture compression standard[J]. Communications of the Acm, 1992, 38(1):xviii-xxxiv.   
[6] Taubman D S ,Marcellin M W . JPEG 2Ooo: Image Compression Fundamentals,standards and practice[J].Journal of Electronic Imaging,2002,11(2):286.   
[7] Toderici G，O'Malley S M，Hwang S J，et al. Variable Rate Image Compression with Recurrent Neural Networks[J].aXiv:1511.06085,2015.   
[8] JBalle,Laparra V， Simoncelli EP .End-to-end Optimized Image Compression[J].arXiv preprint arXiv:11611.01704,2016,1,2.   
[9] Theis L， Shi W， Cunningham A，et al. Lossy Image Compression with Compressive Autoencoders[J].arXiv:1703.00395,2017.   
[10] J Liu,Lu G,Hu Z，et al.A Unified End-to-End Framework for Efficient Deep Image Compression[J].arXiv:2002.03370,2020.   
[11] Liu Yong,Yin Lixin， Zhao Yang.New Adaptive Block Skipping Coding of Binary Image[J].Computer Engineering,2009,13(35),219:221.

# Research on Compression of Pulsar Candidate Diagnostic Images Based on WBS and Deep Neural Network

Jiatao Jiang1,2.3, Xiaoyao Xie1.3,Xuhong Yu1.3

(1.Guizhou Key Laboratory of Information and Computing Science,Guizhou Normal University,Guiyang 550001,China;2.School of mathematical Science,Guizhou Normal University,Guiyang 550ool,China;3.FAST Early Science Data Center,Guiyang 550001)

Abstract: The magnitude of candidate diagnostic images generated by FAST pulsar search has increased exponentially, which brings challenges to scientific data management. It is urgent to study compression methods to achieve effective storage of diagnostic images and speed up their transmission and sharing in the network. It is not reasonable to simply treat the whole image as a color image and compress it with the same method. We propose a skip white block coding and a deep network compresson coding model to compress pulsar candidate diagnostic images. we take the pulsar candidate diagnostic images from recent FAST sky survey search projects to train and verify the model.The results show that the performance of the improved WBS compression for sparse black and white images is 5 times than PNG. The performance of deep network compression algorithm for PSNR is better than JPEG and JPEG2OOO,comparable to BPG.And it is much better than traditional compression algorithm for SSIM.

Key words: Pulsar Candidate Diagnostic Image Compression； Deep network compression model ;WBS; FAST