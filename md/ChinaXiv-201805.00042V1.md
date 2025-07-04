# 基于稀疏表示的脑电（EEG）情感分类

邓欣aʰ，高峰星ab，米建勋a,b，李丹妮ab，王进aʰ，唐云a,b(重庆邮电大学 a.计算机科学与技术学院;b.计算智能重庆市重点实验室，重庆 400065)

摘要：计算机对人类情绪与情感的识别研究已经成为了脑机接口领域的研究热点。通过分析人类在生活中的各种情感状态，提取脑电信号的特征并对情感状态进行识别、分类是情感智能化领域的重要方向。针对基于音乐视频诱导的情感数据集 DEAP 进行了研究，提取脑电信号的频域特征后，提出了采用加速近邻梯度算法（APG)和正交匹配算法(OMP）求解稀疏编码的稀疏表示分类模型进行情感分类，并与支持向量机算法（SVM)做效果比较。实验结果表明，APG算法通过L1范数正则近似求解以其快速的收敛速度在情感数据集上有着较好的分类表现，而OMP算法与 SVM算法的分类效果相差无几，实现了情感脑电信号的分类。

关键词：脑电信号；稀疏表示；情感；加速近邻算法；正交匹配算法中图分类号：TP391.4

# Classifying emotional EEG using sparse representation method

Deng Xina,b, Gao Fengxinga,b, Mi Jianxuna,bt, Li Dannia,b,Wang Jina,b,Tang Yuna, b (a.SchoolofComputer Science & Technology,b.Chongqing KeyLaboratory of Computational Inteligence,Chongqing University ofPosts& Telecommunications, Chongqing 40oo65,China)

Abstract: Computer recognitionof human emotion hasbecomeahot topic in the fieldof brain computer interface (BCI) in recently years.By analyzing the various emotional states in people's life,extracting the features of EEG and clasifying emotionalstates isan important direction inthefieldofemotional intellgence.Basedontheemotiondata setinduced bythe music video,thisresearch extractedthe frequency-domainfeaturesofEEG.Afterthat,the AceleratedProximalGradient (APG) and Orthogonal Matching Pursuit (OMP)algorithms for the sparse representation method were adopted to clasify the EEG signals.By comparing with other algorithms,the experimentalresults show that theAPG withLl norm performs well in the emotion dataset with fastconvergence speed,andthe greedyidea based OMPalgorithmcanachieve thesameefectwithother algorithms.Thecomparative analysis in this paper showthe effctivenessand feasibilityof theproposed method formotional EEG signals classification.

Key Words:EEG; sparse representation; emotion;APG; OMP

# 0 引言

在过去很长的一段时间内，人类情感的研究一直被认知科学研究者所忽略。直到20世纪末，情感作为认知过程中重要的一部分才被人们所重视。与人类运动的研究相比，研究参与情感活动的神经元的具体功能难度更大。神经生理学和心理学的研究发展在一定程度上把情感的由来从神秘莫测中揭露出来。情感是人类特有的生理活动，包括情感的表达、情感的识别以及情感的转变等。计算机对于人类情感的识别是人工智能、认知科学以及人机自然交互关键的一环。根据现代认知科学与心理学，情感是人脑对外界的客观事物的一种反映，它是人对客观事物是否满足自己的需求而产生的态度体验。因此，研究人脑与情感的关系对于未来计算机识别人类情感的研究至关重要。

音乐是人类思想感情和艺术创作的结合，从古到今无数的音乐家用音乐诠释各式各样的情感，可想而知音乐对人类情感的产生与诱发是有着特殊意义的。脑电波信号(EEG)在很大程度上能够反映人的心理和生理状态的改变。通过研究人脑中枢神经系统产生的生物电信号发现，人在情绪波动或者受到不同形式的感官刺激时，脑电波信号会产生特定模式的变化。脑电波信号是一种自发的、非平稳、非线性的神经电活动，其频率变动处于低频节律与超低频节律之间，可划分为多个波段，常见的波段频率有：delta 波 $( 0 . 5 { \sim } 3 \mathrm { H z } )$ 、theta波 $( 4 { \sim } 7 \operatorname { H z } )$ 、alpha 波（20 $( 8 \mathrm { \sim } 1 3 \mathrm { H z } )$ 、beta波 $\scriptstyle 1 4 \sim 3 0 \mathrm { H z } )$ ，gamma波 $( 3 1 { \sim } 4 7 \operatorname { H z } )$ 等。幅值范围为 $5 { \sim } 3 0 0 ~ \mu \mathrm { ~ A ~ }$ 。Karthick等人[1通过采集玲听古典音乐和摇滚音乐以及安静闭眼休息三种状态下的额叶脑电信号，采用去趋势波动分析(detrended fluctuation analysis,DFA)算法和多尺度熵(multiscaleentropy,MSE)分析脑电信号发现有、无音乐时脑电信号有着显著的差异。Nie等人[2]用不同情感类别的奥斯卡经典电影镜头片段，设计了一个以电影片段作为刺激的实验，通过提取被试脑电信号频域特征，开进行正负情绪的分类。Sander等人[3]以 40 个一分钟时长的音乐视频(music videos,MV)作为刺激素材，采集脑电信号和生理信号进行情感识别研究，并且记录了被试面对不同的音乐视频刺激时的主观评价以及被试在实验时的面部表情视频，建立了情感分析数据库“DEAP”。

目前脑电信号的采集设备主要是脑电图仪，它可以记录放置在头皮的电极所检测出来的微弱脑电信号，通过电极导联耦合到差动放大器进行适当的放大并且数字化，最后通过与其配套的PC上的记录系统记录下信号数据。关于头皮电极的位置，有许多放置法如Montreal法，Cohn法以及Gibbs 法等。但应用最多的是10/20系统法，即国际脑电图学会建议采用的标准电极安放法。采集脑电信号的电极数通常有16导、32导、64导、128导。在图1中展示了64导电极的分布情况。

![](images/be37acb54cd8b5dbbda83044d22e8a60705dddcc0370e2f51d8ee01423473e4c.jpg)  
图164导电极安放示意图

# 1 情绪的维度

情感往往产生于特定的环境当中，而人的情感又是变化无常的。目前研究中最常用是基于情感的认知理论的二维空间模型：效价（valence）和唤醒度（arousal）。其中效价是指人的情感的愉快程度，从消极情绪到积极情绪；而唤醒度指的是人的兴奋程度，从无聊到兴奋。丹麦心理学家卡尔·格(CarlLange)提出喜欢-兴奋二维空间[4]，与效价与唤醒都二维空间模型相似，横坐标表示愉快程度，纵坐标表示兴奋程度，不同的情绪分布在二维空间的不同位置，如图2所示。

![](images/36bff3485ffaf22eb69a09e3145f4d4866a5807585fc6ea4d9d9d3e3ab91ff97.jpg)  
图2效价-唤醒度二维空间

# 2 DEAP数据集

DEAP（database for emotion analysis using physiologicalsignals）数据库是SanderKoelstra[3]等人利用多模态的生理信号和音乐视频进行情感分析的数据集。其中生理信号包括被试的多通道脑电信号（EEG）和外围生理信号。这是一个公开的情感类EEG数据集，研究人员可以基于此数据库来测试各种的情感状态分类方法。本文采用了此数据库中的部分数据进行研究。

实验选取了32名被试，男女各一半，平均年龄26.9岁。在实验前告知被试实验的目的以及实验的各个细节。实验在有可控照明的实验室内进行，实验室内保持安静的状态以保证被试在实验时情绪不受打扰。被试坐在距离屏幕将近1米的位置，实验中的音乐视频在17英寸的液晶显示屏中播放。实验前通过与被试沟通将音乐音量调试到恰当大小，确保被试能够更好的投入到实验环境当中。准备工作完善之后，通过下面的流程开始播放40首音乐视频素材。

实验流程如下：a)显示2s的音乐编号，以提醒被试当前实验进度；b)5s的基线时间；c)播放 $1 ~ \mathrm { m i n }$ 的音乐视频，并且记录生理信号，采样频率为 ${ 5 1 2 } \mathrm { H z }$ ；d)被试自我评估。其中被试进行自我评估是根据自我评估系统SAM（self-assessmentmanikins）表格进行的，该系统记录了用户对40首音乐视频的唤醒度，效价、喜欢程度和控制力度的评分，每项评分的评分标准均为1\~9分。

根据国际10-20电极法，实验用于采集实验信号的电极帽是32个导联。实验数据已经经过了简单的预处理，其中采样频率降至 $1 2 8 \mathrm { H z }$ 。为了去除噪声，首先用带通滤波器将脑电信号滤波至 $4 { \sim } 4 5 ~ \mathrm { H z }$ ，然后用盲源分离法去除了眼电伪迹。每首音乐视频对应的脑电信号被截取为 $6 3 \mathrm { ~ s ~ }$ ，其中60s为音乐视频的播放时间，3s为基线数据时间。63s的数据共计8064个采样点，本文在处理数据时，去除了前3s的基线数据，因此采样点降为7680个。

鉴于不同的被试对于音乐的敏感程度不一样，本文通过分析被试的自我评估系统表（SAM），选取了10个效价和控制力度评估较高的被试作为测试样本，他们分别是：S04，S06，S09，S17，S19，S20，S21，S22，S26，S27。

Davinson 和Petrantonakis 等人[56的研究表明，人脑的前额叶皮层在情感调节和意识经验中起着主要作用，故本文选取了处于前额的FP1，FP2电极与额区F3，F4电极的四个导联做

测试。

综上所示，在本文的研究当中，每一个被试的EEG信号数据形式为 $4 0 { \times } 4 { \times } 7 6 8 0$ ，其中40代表有40首音乐视频；4代表所选的电极，分别是FP1，FP2，，F3，F4电极；7680代表被试在 $1 \mathrm { m i n }$ 音乐视频下的脑电采样信号。10位被试的数据均是在MATLAB2014下处理的，如图3所示为S06被试在FP1通道的原始采样信号。

![](images/d81db615de9c327f9b13b8e1a3942ac3cb59f87f3052205a5108bfdc008a87eb.jpg)  
图3S06被试在FP1通道下的采样信号

# 3 算法流程

# 3.1算法框架

本文的算法流程框架如图4所示。

![](images/0c758e6eb3110eddbe636c873e7c3a4f1beca44ee0b43aec732a47b1864a3c28.jpg)  
图4算法流程

# 3.2z-score数据标准化

数据标准化是数据处理前的一项基本工作，对于脑电信号来说，往往具有多个评价指标，但是多个评价指标的量纲是不同的，因此，为了消除量纲对于数据分析结果的影响，需要对数据进行标准化的处理。基于数理统计学，常用的数据标准化方法有min-max 标准化、log 函数转换、z-score 标准化[7]等。本文选取标准分数（ $\cdot$ -score）对数据进行处理。如式（1）所示，处理前的数据为 $x$ ， $\mu$ 为变量的均值， $\sigma$ 为标准差值， $z$ 值表示标准化后的数据。被处理后的脑电信号采样点数据被缩放到[-

1,1]内。

$$
\ z = { \frac { \left( x - \mu \right) } { \sigma } }
$$

# 3.3小波变换

EEG信号是典型的非平稳时变、非高斯信号，而传统的频域分析方法要求信号是平稳信号，因此，研究人员想到采用时/频分析方法。小波变换（wavelettransform,WT）是一种典型的时频分析方法，它的数学形式是有Grossman和Morlet[8]在1984年提出的。1987年，法国信号处理专家Mallet将多尺度分析的思想理论引入小波分析中，其中包括了小波函数的分解以及信号按照小波函数重构等，完善了小波分析的理论体系。

情感脑电信号是大脑中各种神经元之间相互作用的随机组合，组合的非线性导致了脑电信号具有随机性、非线性、非平稳性的特点。传统的信号处理方法为傅里叶变换，它需要利用信号全部的时频信息，具有一定的局限性。小波变换在傅里叶变换的基础上，采用了时间窗和频率窗都可变的分析方法，更适合于处理低频信号变化较慢的一些非平稳信号。对于活动频域主要在低频和超低频的情感脑电信号而言，小波变换可以通过在大尺度下使用宽窗口表现脑电的低频信息，在小尺度下使用短窗口表现高频信息，同时呈现脑电信号的细节系数和近似系数，这样就可以在不同尺度上提取脑电信号中不同节律的波段。在处理情感脑电信号的过程中，小波变换体现了对信号的自适应特性。

小波变换（WT）的定义为式（2），其中 $\mathbf { \Omega } _ { a }$ 是伸缩系数，$\boldsymbol { \tau }$ 是平移系数。小波变换对信号分析处理时通过母小波函数 h(t)来完成的，其中 $\overline { { ( \bullet ) } }$ 表示其共轭复数，母小波函数在时域中的变换可以选择出被分析的信号，信号通过 $a$ 尺度的伸缩、平移，对于频率而言也是相似的。

$$
{ \bf W T } _ { x } ( \tau , a ) = \frac { 1 } { \sqrt { a } } \int _ { - \infty } ^ { + \infty } x ( t ) h ( \overline { { \frac { t - \tau } { a } } } ) d t = \sqrt { a } \int _ { - \infty } ^ { + \infty } x ( a t ) h ( \overline { { \frac { t - \tau } { a } } } ) d t
$$

小波变换通过在特定范围子集上对信号缩放和平移变换，将原始情感脑电信号分解到不同尺度的近似分量和细节分量上，每一层的近似系数再次分解为新的近似分量和细节分量，以此类推，将信号分解成 $n$ 层，每层对应一组近似分量和细节分量。如式（3）所示，对于原始信号 $\mathbf { x ( t ) } .$ 小波分解过程为

$$
x ( t ) = \sum _ { k = - \infty } ^ { \infty } C _ { n , k } \sigma ( 2 ^ { - ^ { N } t - k ) + \sum _ { j = 1 } ^ { n } } \sum _ { k = - \infty } ^ { \infty } D _ { j , k } 2 ^ { - j / _ { 2 } } \varphi ( 2 ^ { - j } t - k )
$$

其中： $C _ { n , k }$ 为第 $n$ 层的第 $k$ 个近似分量， $D _ { j , k }$ 代表第 $\mathrm { j }$ 层的第$k$ 个细节分量， $\sigma ( \mathrm { t } )$ 表示伸缩函数， $\boldsymbol { \varphi ( \mathrm { t } ) }$ 是伸缩函数。

本文中DEAP情感脑电数据已经过预处理，采样频率为128HZ，根据奈奎斯特采样定理，有效频率为采样频率的一半，即 $6 4 \mathrm { H z }$ 。根据式（3），将脑电信号分解为四层，从每层的细节分量和近似分量中提取出：delta 波 $( 0 . 5 { \sim } 3 \ \mathrm { H z } )$ 、theta 波(4\~7Hz)、alpha 波 $( 8 \mathrm { \sim } 1 3 \ \mathrm { H z } )$ 、beta波 $\cdot 1 4 { \sim } 3 0 ~ \mathrm { H z } )$ ，gamma 波(31\~47Hz)五个波段，本文选取db4作为小波基，图5为其对应的4层小波频域分解树。图6、7为被试S06原始脑电信号小波分解对应的近似系数和细节系数。

![](images/99e302734fcebf799befef75092f26181860922e1b6b5b5e695e0c46e49f9e4b.jpg)  
图14层小波分解树

如图5所示，原始的64HZ信号被分解成四层，每层包括一组近似分量 SRC 与细节分量 SRD，其中alpha 波分布于细节分量SRD2上，beta 波段分布在细节分量 SRD3上，theta 波分布于细节分量SRD1上，gamma 波分布于细节分量SRD4上，delta 波分布于近似分量 SRC1上。

Detail Coefficients 10   
4 0 m -10 0 100 200 300 400 500 10   
8 -10 0 200 400 600 800 1000 5 -5 0 500 1000 1500 2000   
0 7 0 500 1000 1500 2000 2500 3000 3500 4000 sampled signal

![](images/07f98928a6b576ca46902e3438039af17588e4e8bc0be9b4bdc2a7dea29b244c.jpg)  
图6细节系数  
图7近似系数

# 3.4功率谱分析

情感脑电信号有着其幅值小、噪声干扰大的特点，因此，如何从中提取有用的特征是一个很重要的问题。目前基于频域的分析是研究脑电信号和临床应用的主要分析方法。通过小波变换已提取出情感脑电信号的频域信息。频域分析可以将幅值随着时间移动的时域信号转变为功率随时间变化的频域信号的谱图。经典的频谱分析方法是以有限时间段数据的傅里叶变换为基础的周期法，同时信号采用窗口截断对信号功率谱进行估计。根据维纳-辛钦定理，信号 $\mathbf { x } ( \mathbf { n } )$ 的功率谱和它的自相关函数可构成一对傅里叶变换，它的定义为式（4），该方法通过将随机信号 $\mathbf { x } ( \mathbf { n } )$ 的N 个观测数据看做是能量有序的序列，计算 $\mathbf { x } ( \mathbf { n } )$ 的傅里叶变换,然后取其幅值的平方除以N,作为序列 $\mathbf { x } ( \mathbf { n } )$ 的真实功率谱估计。

$$
{ \bf I } _ { \scriptscriptstyle N } ( w ) = { \frac { 1 } { N } } \big | { \boldsymbol { X } } _ { \scriptscriptstyle N } ( w ) \big | ^ { 2 }
$$

$\mathbf { x } ( \mathbf { n } )$ 的傅里叶变换具有周期性，所以 $\mathrm { I _ { N } ( w ) }$ 也有周期性，并且是有偏估计。先计算N个数据点的傅里叶变换（即频谱），如式（5）所示。

$$
X _ { \scriptscriptstyle N } ( w ) = \sum _ { n = 0 } ^ { \scriptscriptstyle N - 1 } x ( n ) e ^ { - j n w }
$$

然后频谱域与其共轭函数的相乘，得到其功率谱，如式(6)所示。

$$
P _ { x } ( w ) = \frac { 1 } { N } \big | X ( w ) \big | ^ { 2 } = \frac { 1 } { \mathbf { N } } \bigg | \sum _ { n = 0 } ^ { N - 1 } x ( n ) e ^ { - j n w } \bigg | ^ { 2 }
$$

基于经典的谱估计方法，本文分别计算出已提取出的五种节律波形的功率谱，如图，并将其选取为特征，四个通道总共$4 \times 5 = 2 0$ 个特征。

![](images/24ac69c671674943ae1d2910f856bebc4074760d002a34f041e3359bfec31027.jpg)  
图8五个频带的功率谱

# 3.5稀疏表示（sparse representation）

稀疏表示最早由美国的Olshausen和Field提出[9]，它的基本原理是将输入的信号表示为从字典中选取的过完备基上的线性组合，其中对于一个N维向量x,如果其中大部分元素均为0,只有少部分元素是非零的，那 $\mathbf { x }$ 被称之为是稀疏的。Donoho 于2006年提出了压缩感知（CS）理论，使信号的稀疏表示得以发展[0]。压缩感知使得信号的采集和测量方法不再受奈奎斯特（Nyqyist）采样定理的限制，对信号的带宽不再严格要求，取而代之的是数据的稀疏性[1]。

不妨把一个数据集D看做是一个矩阵，若将其每一行看做一个样本，每一列看做是一个特征，那么特征选择过程中要考虑的就是这些特征的“稀疏性”，若去掉矩阵中与学习任务无关的特征，则训练过程的难度以及计算和存储的开销也会减小。

另一方面，若D中存在很多零元素，但它们不是以整行或者整列的形式出现，这时对于数据集来说，它同样是具有稀疏性的，当样本具有这样的稀疏表达形式时，不仅可以使得大多数的问题变得线性可分，而且存储的负担大大降低，因为稀疏矩阵已有很多高效的存储方法。基于压缩感知理论的信号采样只需使用不到原信号一半的样本数，即可高质量地重建原信号。本研究利用情感脑电信号不同节律的稀疏特性（或可压缩性）的先验条件，通过不同的解码算法可以很高的概率重建原始脑电信号或者高维信号，对于重要的节律特征波形能够很好的保持，并且找与情感高度相关的节律特征。

信号的稀疏表示问题可以通过求解稀疏正则化问题得以实现，如式（7）所示。

$$
\operatorname* { m i n } _ { a \in A } g ( a ) \triangleq f ( a ) + \lambda \Omega ( a )
$$

其中： $\varOmega$ 为稀疏正则项， $\lambda$ 为非负参数， $A$ 为凸集， $a$ 为 $A$ 中的向量。

系数a具备稀疏性， $\Omega$ 可以取 $\mathrm { L } _ { 0 }$ 范数，如式（8）所示。

$$
\Omega ( a ) = \left\| a \right\| _ { 0 } \triangleq \left| \{ k | \mathbf { a } _ { k } \neq 0 \} \right|
$$

其中·为集合的势。

f(a)表示信号的误差项，通常取其平方误差，式（9）所示。

$$
\mathbf { f } \left( a \right) = \frac { 1 } { 2 } \big \| x - D a \big \| _ { 2 } ^ { 2 }
$$

稀疏表示在用于分类时的模型被称之为是稀疏分类方法（Sparse Representation based Classification，SRC）[l2]。该模型主要是将输入信号表示为稀疏的过完备基原子的线性组合，如式（10）所示。

$$
\operatorname* { m i n } \| { \boldsymbol { x } } \| _ { \mathrm { { o } } } { \mathrm { s u b j e c t { t o } } } \ \mathrm { A x = y }
$$

其中： $\Vert { \boldsymbol { x } } \Vert _ { 0 }$ 表示 $x$ 中非零的元素个数，即 $L _ { \theta }$ 范数。通过 $L _ { 0 }$ 范数表示稀疏性虽然理论可行，但是在数学上很难实现。常见的做法是将 $L _ { \theta }$ 范数转换为 $L _ { I }$ 规范化处理，如式（11）所示。

$$
\operatorname* { m i n } \parallel x \parallel _ { 1 } { \mathrm { ~ s u b j e c t ~ t o ~ } } \mathrm { \bf A x { = } y }
$$

可见，式（11）转换为一个最优凸近似问题，典型的凸松弛测量是通过 $L _ { I }$ 正则近似得到，如式（12）所示。

$$
\operatorname* { m i n } _ { \alpha \in R ^ { p } } g ( \alpha ) \triangleq \frac { 1 } { 2 } \| x - D \alpha \| _ { 2 } ^ { 2 } + \lambda \| \alpha \| _ { 1 }
$$

式（12）是统计学中的Lasso问题，可以看做是一个正则最小二乘问题。本文采用原始情感脑电信号作为过完备基，利用过完备基的冗余特性可以更好的捕捉信号脑电信号中的本质特征这一特点，提出了采用SRC分类算法对情感脑电信号进行分类。

SRC分类框架的具体流程如下：

a)输入训练样本矩阵 $A = [ A _ { 1 } , A _ { 2 } , . . . A _ { k } ] \in \mathbb { R } ^ { m ^ { * } n }$ ，测试样本b)规则化矩阵 $A$ 的列，使其具有 $\mathbf { L } _ { 2 }$ 范数；

c)解决L1范式最小化问题:

$\operatorname* { m i n } \| x \| _ { \mathrm { l } }$ subject to （204号 $\| A x - y \| _ { 2 } \leq \varepsilon$ ,其中ε为常量，表示重构误差限制;

d)计算残差： $\mathbf { r } _ { i } ( y ) = \parallel y - A \delta _ { i } ( x ) \parallel _ { 2 } \ \mathrm { i } = 1 , 2 ;$

e)根据重构样本和测试样本的冗余误差确定测试样本的标 签:identity $\mathbf { \chi } ( y ) = \arg \operatorname* { m i n } _ { i } ( r _ { i } ( y ) )$

稀疏正则化求解通常有两种方法，一种是通过贪婪算法求解近似解，另一种是将其转换为凸优化问题。

# 3.5.1贪婪算法求解

贪婪算法以其高效的特性在压缩感知和稀疏信号重建中得到广泛应用，它的基本原理是通过多次迭代字典中与信号最为相似的原子来逼近原始信号。贪婪算法主要包括匹配追踪（matching pursuit,MP)[13]、正交匹配追踪（orthogonal matchingpursuit，OMP）[14]，分级正交匹配追踪（stagewise orthogonalmatching pursuit）[15]等。

MP 算法在每次迭代中，选择与当前误差向量 $r = x - D a$ 最相关的向量，并求出残差，然后选择与残差最匹配的原子投影到选择的原子上，构成该原子的系数增量。具体步骤如下：

a)初始化误差向量 $\mathbf { r } _ { 0 } = x$ ，迭代次数 $t { : = } 1$ ·b)搜索与误差向量相关性最大的原子索引：

$$
\mathbf { l } _ { t } : = \arg \operatorname* { m a x } _ { i \in [ [ 1 : \mathrm { ~ \ p l ] ~ } } \left. d _ { i } ^ { T } r _ { t - 1 } \right. ;
$$

c)更新重构系数与误差向量:

$$
\mathbf { a } _ { l _ { t } } : = \mathbf { a } _ { l _ { t } } + d _ { l _ { t } } ^ { T } r _ { t - 1 }
$$

$$
\mathbf { r } _ { t } : = r _ { t - 1 } - ( d _ { l _ { t } } ^ { T } r _ { t - 1 } ) d _ { l _ { t } } ;
$$

（204号 $\mathrm { d } ) t : = t + 1$ 若 $t < k$ ，返回步骤b)，否则退出。

MP算法中，更新后的误差向量与当前的原子正交，即$r _ { t } ^ { T } d _ { l _ { \prime } } = 0$ ，但是却无法保证其与其他原子正交，因此在已选字典原子构成的子空间上每次迭代的信号可能是次最优的。也就是说，MP算法不能保证信号的最优逼近[16]。

针对这些问题，PATI提出了OMP 算法[14]，该算法将每次选择的新的原子添加到已选择原子的活跃集中，当达到要求的稀疏度时停止迭代。然后根据最大程度减小目标函数值选取下个原子，如式（13）所示。

$$
1 { : = } \arg \operatorname* { m i n } _ { i = \Lambda ^ { c } }
$$

$$
\operatorname* { m i n } _ { \beta \in R ^ { | \Lambda | + 1 } } \frac { 1 } { 2 } \| \ b { x } - \ b { D } _ { \Lambda \cup \{ i \} } \beta \| _ { 2 } ^ { 2 }
$$

其中： $\Lambda$ 为已选择的原子活跃基。OMP算法需要解决的问题是 $\left| \Lambda ^ { \mathrm { c } } \right|$ 个最小二乘问题，更新后的活跃基、误差项、重构系数如式（14）所示。

$$
\begin{array} { r l } & { \Lambda { : = } \Lambda \cup \{ 1 \} } \\ & { \alpha : = ( D _ { \Lambda } ^ { \operatorname { T } } D _ { \Lambda } ) ^ { - 1 } D _ { \Lambda } ^ { T } x } \\ & { r : = x - D _ { \Lambda } ( D _ { \Lambda } ^ { T } D _ { \Lambda } ) ^ { - 1 } D _ { \Lambda } ^ { T } } \end{array}
$$

# 3.5.2凸优化求解算法

对于无约束的凸优化问题，可以通过线性规划、梯度下降等方法凸优化求解。当目标函数可微且具有Lipschtiz[17连续梯度函数f和一个不可微函数 $\boldsymbol { \lambda \Omega }$ 组成时，特别适合采用加速近邻梯度法（APG）。

在每次迭代过程当中，当 $f$ 在当前点处线性化，求解转换为

$$
\operatorname* { m i n } _ { a \in R ^ { \beta } } f ( a ^ { t } ) + \nabla f ( a ^ { t } ) ( a - a ^ { t } ) + \lambda \Omega ( a ) + \frac { L _ { f } } { 2 } \left. a - a ^ { t } \right. _ { 2 } ^ { 2 }
$$

其中二次项为近邻项，它可以保持更新后的f与线性近似偏差控制在一定范围内； $L _ { f }$ 为Lipschtiz常数。式（15）可以重写为式（16）。

$$
\operatorname* { m i n } \frac { 1 } { 2 } \left\| a - ( a ^ { t } - \frac { 1 } { L _ { f } } f ( a ^ { t } ) ) \right\| _ { 2 } ^ { 2 } + \frac { \lambda } { L _ { f } } \Omega ( a )
$$

APG算法求解稀疏表示问题的步骤如下：

a)计算：v $\mathbf { v } ^ { t } = a ^ { t } - \frac { 1 } { L _ { f } } \nabla f ( a ^ { t } )$ b)求解： $\begin{array} { l } { { \mathbf { u } ^ { t } = \displaystyle \arg \operatorname* { m i n } _ { u } \{ \frac { L _ { f } } { 2 } \| u - \nu ^ { t } \| _ { 2 } ^ { 2 } + \lambda \Omega ( \nu ^ { t } ) \} } } \\ { { \Omega ( \nu ^ { t } ) = \displaystyle \| \nu ^ { t } \| _ { 1 } } } \end{array} ,$ c)更新学习率： $\sigma ^ { \smash { \mathrm { t + 1 } } } : = 1 + \sqrt { 1 + 4 ( \sigma ^ { t } ) ^ { 2 } } / 2$ d)更新迭代结果： $\mathbf { a } ^ { t + 1 } : = u ^ { t } + \frac { \sigma ^ { t } - 1 } { \sigma ^ { t + 1 } } ( u ^ { t } - u ^ { t - 1 } )$ e) $\mathrm { t } \langle = t + 1$ 若达到迭代条件则退出。

Beck和Teboulle 证明APG 算法的收敛速度为 ${ \mathbf O } ( t ^ { - 2 } )$ ，证明APG算法是求解稀疏问题的有效方法[18]。

# 4 情感识别实验结果分析

本文基于DEAP情感数据库进行情感分类。总共10位被试，每位被试的实验数据被处理为 $4 0 { \times } 4 { \times } 7 6 8 0$ ，其中40 表示被试观看了40首音乐视频，4表示前额与额区的四个通道，7680表示一分钟的采样数据。根据每个被试的自我评估系统SAM表格打标签，可将情感状态分为四个类别，分别为：高效价高唤醒度；高效价低唤醒度；低效价高唤醒度；低效价低唤醒度。基于以上标签对情感数据分别进行二分类与四分类实验，其中二分类是主要效价维度来识别被试的积极/消极情绪状态。本文根据小波变换提取被试的alpha、beta、theta、gamma、delta 节律，并计算出每个波形的功率谱，取其均值作为特征，那么经过特征提取后的数据为 $4 0 \times 4 \times 5$ ，其中5表示每个通道中5种节律的平均功率谱值。不同的波形在积极情绪与消极情绪下的功率谱有着明显的差异，如图9所示。

![](images/81c7ad5d26d080957701569e7242e617e8407b5be85f5b579f1ec8e1b4681f20.jpg)  
图9五种波形在不同情绪下的比较

可以看出消极情绪下 theta 节律、alpha 节律、beta 节律功率谱值较高，而转换为积极情绪时delta节律和gamma节律显著增强。

由于脑电信号是典型的非线性信号，支持向量机（SVM)以其对非线性数据的处理优势以及较好的泛化能力成为了当前情感脑电分类的主流算法。本文提出使用的稀疏表示分类算法将与经典的SVM算法做效果比较。将特征数据导入Matlab中的 SPAMS 稀疏建模工具箱以及Libsvm工具箱中，分别采用SVM算法、通过OMP和APG 算法解码的稀疏分类算法进行二分类和四分类实验，其中 SVM算法选择径向基核函数[19],三种分类方法均用10折交叉验证法进行验证，图10为三种分类方法的经过交叉验证后的准确率对比：

![](images/07c6a82dbc0937a6de0fecc19dcfa481671d9121ef5ebf9fe850c302c0f28a2d.jpg)  
图10稀疏表示分类与SVM算法分类效果比较

通过图10可知，稀疏分类中的加速近邻梯度法（APG）对于样本数据的分类效果较好，二分类中最高准确率可达到 $8 5 \%$ ，平均准确率为 $70 \%$ 左右；四分类中最高准确率可达到 $6 7 . 2 5 \%$ 平均准确率为 $57 . 5 \%$ 左右。而正交匹配追踪算法（OMP）和支持向量机（SVM）的平均分类准确率要差一些，二分类准确率分别为 $6 4 . 2 \%$ 和 $6 4 . 5 \%$ ，而四分类准确率分别为 $4 8 . 5 5 \%$ 和 $44 \%$ 。

本文提取了频域上的五个频带的功率谱作为特征，图11和图12分别呈现了单个频带作为特征时APG算法和OMP算法的分类准确率，其中，gamma节律相较于其他四个波段的效果最好也较为稳定，APG算法以gamma 节律功率谱作为特征时，二分类平均准确率能够达到 $6 4 . 2 \%$ ，四分类平均准确率为 $47 \%$ ，而OMP算法在二分类时平均准确率能够达到 $6 3 . 2 5 \%$ ，四分类平均准确率为 $43 . 3 \%$ 。这个结果证实了gamma 节律在情感识别中具有重要的作用[20]。

![](images/e64e91c1991e2ec52110cd4dff316396a19b363910061cb7feb84d9951cf28bd.jpg)  
图11五种波形分别在APG 算法下的准确率

![](images/58f8f2995b50ae91cee1a45a6a852a1ac23cfc64c0af90e21d8c9d49c36a897c.jpg)  
图12五种波形分别在APG算法下的准确率

经过分析比较单个节律功率谱与五个节律功率谱融合起来作为特征时的效果，可知以五个节律功率谱作为特征的分类效果要比单个节律功率谱作为特征效果要好。

# 5 结束语

本文详细介绍了基于音乐视频诱导的DEAP情感数据集，预处理之后通过小波变换和快速傅里叶变换提取其频域特征，然后运用通过OMP和APG算法求解稀疏编码的稀疏表示分类算法进行分类，并与SVM算法做效果比较。脑电信号通过稀疏向量重构之后与测试样本作比较，通过冗余误差进行分类。实验结果表明，加速近邻梯度算法（APG）通过 $L I$ 范数正则近似求解以其快速的收敛速度在情感数据集上有着较好的分类表现，而贪婪算法中的正交匹配追踪算法（OMP）与SVM分类的效果相差无几，实现了情感脑电信号的分类。情感脑电信号的分类与识别是一个值得努力研究的领域，而基于稀疏表示重构信号进行分类是对其有效的方法，值得再深入研究。

# 参考文献：

[1]Karthick NG,Ahamed VIT,Paul JK.Music and the EEG: a study using nonlinear methods [C]//Proc of IEEE International Conferenceon Biomedical and Pharmaceutical Engineering.2oo6:424-427.   
[2]Nie D, Wang X W, Shi L C,et al. EEG-based emotion recognition during Watching movies [C]//Proc of International Ieee//embs Conference on Neural Engineering.2011: 667-670.   
[3]Sander K,Christian M,Mohammad S,et al.DEAP: a database for emotion analysis using physiological signals[J]. IEEE Trans on Affective Computing, 2011, 3 (1): 18-31.   
[4]Russell JA.A circumplex model of affect [J]. Journal of Personality and SocialPsychology,1980,39 (6):1161.   
[5]Davidson RJ, Jackson D C,Kalin NH. Emotion,plasticity,context,and regulation[J].Psychological Buletin,2000,126.   
[6]Petrantonakis PC,Hadjileontiadis LJ.Emotion recognition from EEG using higher order crossings [J].IEEE Trans on Information Technology in Biomedicine,2010,14 (2): 186.   
[7]Runyon R P, Coleman K A,Pittenger D J. Fundamentals of behavioral statistics [J].Stomatologie DerDdr,1996,36 (12): 733.   
[8] 李孔震，王炳和，娄昊，等．基于小波变换和二维非负矩阵分解的人脸 识别算法[J].计算机应用研究,2013,30(4):1275-1277.   
[9]Olshausen B A,Field D J.Emergence of simple-cell receptive field properties by learning a sparse code for natural images [J]. Nature,1996, 381 (6583): 607-9.   
[10] Tsaig Y,Donoho D L.Extensions of compressed sensing [J].Signal Processing,2006,86 (3): 549-571.   
[11]刘继承，陈佳伟．基于改进 StOMP 算法图像压缩感知重构[J].计算机 应用研究,2016,33(9):2869-2872.   
[12] YinJ,Liu Z,Jin Z,etal. Kernel sparse representation based classification [J]. Neurocomputing,2012,77(1):120-128.   
[13] Mallat S G, Zhang Z. Matching pursuits with time-frequency dictionaries [J]. IEEE Trans On Signal Processing,1993,41(12): 3397-3415.   
[14] Pati YC,Rezaiifar R,Krishnaprasad P S.Orthogonal matching pursuit: recursivefunctionapproximationwithapplicationstowavelet decomposition[C]//Proc of IEEE ConferenceRecordof the27thAsilomar Conference on Signals,Systems and Computers.2002: 40-44 vol.1   
[15] Donoho DL,Tsaig Y,Drori I,et al. Sparse solution of underdetermined systems of linear equations by stagewise orthogonal matching pursuit [J] IEEE Trans on Information Theory,2012,58 (2):1094-1121.   
[16]孙君顶，赵慧慧．图像稀疏表示及其在图像处理中的应用[J].红外技 术,2014 (7).   
[17] Aronson G,Crandall M,Juutinen P.A tour of the theoryof absolutely minimizing functions [J]. Bulletin of the American Mathematical Society, 2004,41 (4): 439-505.   
[18] Beck A,Teboulle M.Fast gradient-based algorithms for constrained total variation image denoising and deblurring problems [J].IEEE Trans on Image Processing,2009,18 (11): 2419.   
[19]黄应清，赵错，蒋晓瑜．基于核空间类间平均距的径向基函数一支持向 量机特征选择算法 [J].计算机应用研究,2012,29(12):4556-4559.   
[20] LiM,LuBL.Emotion classification based on gamma-band EEG [C]//Proc of IEEE International Conference on Medicine and Biology Society.2009: 1223-1226.