# 基于小波包-AR谱和深度学习的轴承故障诊断研究

贺思艳1，刘亚²，田新诚²

(1．山东电子职业技术学院 智能制造工程系，济南 250200;2.山东大学 控制科学与工程学院，济南 250061)

摘要：针对轴承故障信号的非平稳性和非线性特点，采用小波包分解和自回归(auto-regresive，AR)谱估计相结合的方法提取振动信号特征值；为了提高诊断结果的精度，提出用深度信念网络（dep believe network，DBN）进行诊断模型训练。首先，对轴承振动信号进行小波包分解和自回归谱估计，计算不同频段的能量实现轴承故障特征提取；其次，将提取到的特征值作为深度信念网络的输入向量，进行模型训练；最后，用训练好的模型进行故障诊断。为验证本文所提方法的有效性，采用美国凯斯西储大学提供的旋转轴承数据集，将提出算法与三种故障诊断方法进行对比实验。实验结果表明，所提方法具有更好的诊断性能。

关键词：小波包分解；特征提取；深度信念网络；故障诊断 中图分类号：TP206.3 doi: 10.3969/j.issn.1001-3695.2018.04.0261

# Research on bearing fault diagnosis based on wavelet packet-auto regressive model spectrum and deep learning

He Siyan1, Liu $\mathrm { Y a } ^ { 2 \dagger }$ , Tian Xincheng² (1.Deptof Intelligent Manufacturing Engineering Shandong Colegeof Electronic Technology,Jinan 250200,China;2. School of Control Science & Engineering Shandong University,Jinan 25oo61,China)

Abstract:Asthebearing fault signalis non-stationaryand non-linearin nature,thispaperused the wavelet packet decomposition （WPD）and auto-regresive (AR）spectrum estimating method to extract features.Inorder to improve the accuracy of diagnosis,the deep believe network wasproposed to train diagnostic models.Firstly,using the WPDad AR spectrumestimating methodtocalculate theenergyof different signal bands torealizethe feature extractionof vibration signals.Then,using the extracted eigenvaluesas inputvectorsof thedeepbelief network toconductmodel training.Fialy, using thetrained model tocarryout bearing fault diagnosis.Inordertoverify theefectiveness of the proposed method,using therotating bearingdataset providedbytheCase WesternReserveUniversityin the United States,the algorithmis compared with threefaultdiagnosis methods.Experimentalresults show that theproposed method has better diagnostic performance.

Key Words: wavelet packet decomposition; feature extraction; deep believe network; fault diagnosis

# 0 引言

滚动轴承是机电设备中应用最广泛的机械部件，其工作状态正常与否直接影响整体设备的性能。同时，它也是最易损坏的部件之一。因此，对轴承的状态监测和故障诊断尤为重要[1,2]。

设备在异常状态下伴随着振动的变化。因此，振动信号分析方法已广泛应用于旋转机械故障诊断中。基于信号分解的特征提取已经得到了广泛的研究[3,4]。轴承发生故障时，由于受到刚性、非线性、摩擦力等因素的影响，其振动信号往往会表现出非平稳特征，因此，傅里叶变换难以准确提取轴承故障状态信息。经验模式分解方法虽然理论上适用于非线性非平稳过程，但是其显著的“模态混叠”问题，使其存在一定局限性，难以获取有效信息[5]。近年来，有学者提出基于集合经验模态分解(ensemble empirical mode decomposition，EEMD）的信号特征提取方法。EEMD在一定程度上解决了模态混叠问题，但是仍然存在计算量大、复杂度高等问题[6]。

小波包分解可以对检测信号进行多通道滤波，通过不同频率的小波与检测信号相互作用，将信号划分成不同的频段，减少信号间干扰。同时，AR谱估计具有外推功能，可以有效分析短样本信号[7]。

目前，国内外不少学者对轴承的故障诊断开展研究。常用的故障识别算法[8.9]有灰色关联分析(greyrelational analysis,GRA)、支持向量机(support vector machine,SVM)、反向传播神经网络(backpropagation,BPNN)等。GRA易于实现与理解，但是在分类精度上存在很大不足。SVM适用于小样本的训练分类，而且存在惩罚系数难以确定、核函数必须满足Mercer定理等问题。BPNN存在容易陷入局部最优的缺点。

深度学习是近年来神经网络发展史上的一波新浪潮，随着AlphaGo战胜人类围棋的冠军，深度学习成为学术界和工业界共同关注的焦点。深度学习在图像，音频和人工智能等领域发挥着重要作用。例如，在语音识别方面，邓力等人发现利用深度信念网络(deep believe network,DBN)预训练一个深层前馈神经网络再调优，能够显著提高语音识别准确率[10\~12]。考虑到轴承的故障诊断和语音识别在模式分类与识别中存在一定的相通性，将DBN应用于轴承故障诊断。

DBN由一个可见层和多个隐藏层组成，可以提取训练数据的多层表示，并且对输入数据进行重构。DBN的训练过程是逐层训练，这样的机制使得DBN成为深度学习中有效且快速的网络之一。考虑到随着数据维度的增加，算法学习需要的样本数量呈指数增加。而且从大数据集中学习需要更多的内存和处理能力[13,14]。因此本文在DBN 训练之前进行信号的特征提取。

综上所述，本文采用小波包分解_AR谱估计特征提取方法，获得能反映轴承状态信息的特征值，采用深度信念网络训练分类器，实现故障诊断。

# 1 基本理论

本文提出的故障诊断算法主要由基于小波包-AR谱估计的特征提取和基于深度信念网络的故障分类两部分组成。算法流程图如图1所示。

![](images/6f49c42ee2570dbdac33e33302f1f1583ec6eb3e2c5f6a511b718c0abe6df562.jpg)  
图1故障诊断算法流程图

特征提取是从原始振动数据出发，构建新的特征。这些特征可以很好的描述原始数据，并且利用它们建立的模型在未知数据上的表现性能可以达到最优。

# 1.1基于小波包分解和AR谱估计的特征提取

小波包分解实现特征信息与干扰信息的分离，有一定的降噪作用。对分解得到的各频带信号进行AR谱估计，提取出包含轴承状态信息的频带能量。具体分为以下四步：

1） 小波包分解。

对振动信号进行 $n$ 层分解，得到 $2 n$ 个小波包系数$X ( n , i ) ( i = 0 , 1 , \cdots , 2 n )$ 0

2）分频段重构时域信号。

以 $W ( n , i )$ 表示对应的 $n$ 个频段小波包系数 $X ( n , i )$ $( i = 0 , 1 , \cdots , 2 n )$ 的重构信号，则总的信号可以用公式(1)表示。

$$
W = W ( n , 0 ) + W ( n , 1 ) + \cdots + W ( n , 2 ^ { n } )
$$

其中 $n$ 表示小波包分解层数， $2 ^ { n }$ 为分解频段数。

3） AR 谱分析。

对每一频段重构的信号进行AR谱估计，得到仅含特定频率信息的AR谱。

4）计算小波包-AR 谱频带能量。

$n$ 个频带的能量值组成 $n$ 维特征向量，用来表征轴承状态。

# 1.2 深度信念网络

DBN是由Hinton等人在2006年提出来的,它是在受限玻尔兹曼机（RestrictedBoltzmannMachine，RBM）基础上构建的[15,16]。

RBM由一个可见层（visible layer）和一个隐藏层（hiddenlayer）组成，层内神经元间无连接，层间神经元全连接，如图2所示。

![](images/7cc8e7307a19f9f67a23942c045208daf4102aa107d6664fe7b46469e6da58f5.jpg)  
图2RBM结构图

如图2所示，RBM可见层用 $\nu$ 表示，用来接收输入信号，隐藏层用 $h$ 表示，相当于输入信号的特征提取器。假若可见层有 $m$ 个神经元，用下标 $i$ 代表第 $i$ 个神经元，隐藏层有 $n$ 个神经元，用下标 $j$ 表示第 $j$ 个神经元。

根据RBM结构图，基于能量函数定义隐藏单元和可见单元上的概率分布。RBM能量函数如式(2)所示。

$$
E ( \nu , h ) = - \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } \nu _ { j } W _ { i j } h _ { i } - \sum _ { j = 1 } ^ { m } b _ { j } \nu _ { j } - \sum _ { i = 1 } ^ { n } c _ { i } h _ { i }
$$

其中: $W _ { i j }$ 为可见层神经元 $i$ 到隐藏层神经元 $j$ 的连接权值， $b _ { j }$ 为可见层第 $j$ 个神经元的偏置， $c _ { i }$ 为隐藏层第 $i$ 个神经元的偏

置。

RBM是一种概率图模型，可见层和隐藏层的联合概率分布为

$$
p ( \nu , h ) = \frac { 1 } { Z } \mathrm { e x p } ( - E ( \nu , h ) )
$$

其中 $Z$ 为归一化因子，其定义如下：

$$
Z = \sum _ { \nu , h } \mathrm { e x p } ( - E ( \nu , h ) )
$$

隐藏层节点之间是条件独立的，即

$$
P ( h \vert \nu ) = \prod _ { j } P ( h _ { j } \vert \nu )
$$

最大似然学习算法可以通过简单地交替更新同一层的所有隐藏单元以及同一层的的所有可见单元来训练网络。

$$
\frac { \hat { \sigma } \log P ( \nu ) } { \hat { \sigma } w _ { i j } } { = \left. \nu _ { i } h _ { j } \right. _ { 0 } - \left. \nu _ { i } h _ { j } \right. _ { \infty } }
$$

为了加强RBM的学习，采用对比散度(contrastivedivergence，CD）算法，其总体思想是从可见单元开始并行更新所有隐藏单元，从隐藏单元重构可见单元，最后更新隐藏单元。

训练DBN的第一步是利用CD算法学习可见单元的一层特征，然后，将先前训练的特征激活视为可见单元，并学习第二隐含层中的特征。最后，当完成最终隐藏层的学习时，整个DBN网络训练完成。DBN学习过程如图3所示。

![](images/c59021b8f482134fef38eb9d0a4cd5b89b8bd36fdc6b59ac48e304fd48febd82.jpg)  
图3DBN学习过程  
图5四种状态下轴承振动信号的时域波形

如图3所示，DBN学习过程主要分为预训练和调优两步。预训练一方面可以产生非常好的参数初始值，另一方面通过逐层训练RBM网络，并将训练好RBM堆叠成DBN，解决了大型网络训练速度慢和训练时间长的问题[17]。调优过程通过对学习样本的作用和反馈，使得网络的输出不断的逼近期望的结果[18]。

# 2 实验验证

# 2.1实验数据描述

为了验证所提出的故障诊断方法的有效性，使用美国凯斯西储大学电气工程实验室轴承中心的振动信号。该轴承数据采集系统试验台如图4所示。

![](images/4b01021858dcc256794661a55089214ad8e08b8c3fc5b3beb05f51f706b6c4e6.jpg)  
图4滚动轴承试验台

该数据集以 $1 2 \mathrm { k H z }$ 的采样频率，在四种不同负荷下采集得到(Load $\scriptstyle 0 = 0$ 马力/1797RPM、负载 $1 { = } 1$ 马力/1772 RPM、负载 $2 { = } 2 \ \mathrm { H P } / 1 7 5 0 \ \mathrm { R P M }$ 、Load $3 { = } 3 \ \mathrm { H P } / 1 7 3 0 \ \mathrm { R P M } )$ 。该试验台模拟了轴承的内圈故障、外圈故障和滚动体故障三种故障类型，每种故障类型有三种损伤程度，损伤尺寸分别为 $0 . 1 8 ~ \mathrm { m m } . \ 0 . 3 6$ mm、 $0 . 5 4 \mathrm { m m }$ 。

本文采用故障尺寸为 $0 . 1 8 \mathrm { m m }$ 的三种故障信号和正常信号，以验证算法对早期故障的诊断性能。图5为Load0中四种轴承状态的振动信号时域波形，每个状态含有120617个数据点。使用包含1024个点的窗口对采集的原始振动信号进行划分，则每种轴承状态得到100个样本。

正常信号时域波形0.50 1000 2000 3000 400050006000 7000 8000 9000 10000采样点数外圈故障信号时域波形505 ++++++0 1000200030004000500060007000 8000 900010000采样点数内圈故障信号时域波形20 p HPNRFFH-20 100020003000400050006000700080009000 10000采样点数滚动体故障信号时域波形10 嘉富年皇寧本菜麻王寒事学字增雪空百牛日坐雪禽老書年零雪章萬正童安-10 1000 2000 3000 4000 5000 6000 7000 8000 9000 10000采样点数

由图5可知，滚动轴承处于正常状态时，其振动信号振幅较小；故障信号幅值出现一定程度的增大，但有些状态下的振动信号时域波形相近再加上外界环境干扰，导致难以区分轴承状态。因此，需要对振动信号进行特征提取。

# 2.2振动信号特征提取

每个负载条件包含400个样本，每个样本是包含1024个数据点的振动信号。对每组样本信号利用小波包分解_AR谱估计方法进行特征提取，分别得到以8个频带能量值组成的特征向量，部分数据如表1所示。

表1特征提取部分数据  

<html><body><table><tr><td rowspan="2">样本 序号</td><td colspan="4">特征向量</td><td rowspan="2">故障 类型</td></tr><tr><td></td><td></td><td></td><td>E1E2EE4E5E6E7E8</td></tr><tr><td>1</td><td></td><td></td><td></td><td>0.20 0.12 1.02 0.11 0.01 0.01 1.56 0.08</td><td>1</td></tr><tr><td>2</td><td></td><td></td><td></td><td>0.19 0.09 0.98 0.110.010.011.68 0.09</td><td>1</td></tr><tr><td>3</td><td></td><td></td><td></td><td>0.611.43 5.08 1.40 0.09 0.19 4.59 0.78</td><td>2</td></tr><tr><td>4</td><td></td><td></td><td></td><td>0.581.514.571.15 0.09 0.204.29 1.16</td><td>2</td></tr><tr><td>5</td><td></td><td></td><td></td><td>0.530.3224.272.340.45 0.4339.92 3.65</td><td>3</td></tr><tr><td>6</td><td></td><td></td><td></td><td>0.560.26 29.462.22 0.50 0.50 42.23 5.13</td><td>3</td></tr><tr><td>7</td><td></td><td></td><td></td><td>0.29 0.38 0.02 0.120.0010.007 0.003 0.007</td><td>4</td></tr><tr><td>8</td><td></td><td></td><td></td><td>0.320.400.02 0.110.0010.0070.002 0.007</td><td>4</td></tr></table></body></html>

其中，故障类型1，2，3，4分别表示内圈故障，外圈故障，滚动体故障，正常四种轴承状态。

以Load0中轴承状态信号为实验数据，图6左图是对本文方法获得的特征值进行主成分分析[19得到的散点图。图6右图是振动信号三个时域特征(方差(Val)、均方根(Rm)、峭度(Ks))的散点图。

![](images/0b3f66cb18f4933ce78b5585bc62739f50b238c16104fbc76de99553e7cf0d77.jpg)  
图6特征提取可视化散点图

由图6可知，前者特征信息更集中，同一种运行状况很好地聚集在一起，而不同运行状况都有效地分离开来，后者正常状态和滚动体故障重合较多，难以区分。从而验证了本文特征提取方法的有效性。

# 2.3基于DBN的故障诊断模型训练

每个训练样本包含两部分记录，一部分是特征序列，一部分是类别标签。将Load0中200个训练样本集输入到深度信念网络进行模型训练，为避免样本数据的不平衡性，本文在每种状态下选取同等数量的样本。

本文DBN 模型的结构参数如表2所示。

表2DBN 结构参数设置  

<html><body><table><tr><td>输入层</td><td>RBM1</td><td>RBM2</td><td>输出层</td></tr><tr><td>8</td><td>100</td><td>100</td><td>4</td></tr></table></body></html>

表2中，输入层节点数根据样本特征维数确定，输出层节点数根据状态类别确定。通过对多种不同深度的DBN 模型，进行相同输入数据的诊断实验，决定采用2个RBM堆栈。参考Geoffrey Hinton [20]给的建议，DBN的学习参数设置如表3所示。

表3DBN 学习参数设置  

<html><body><table><tr><td>Batch Size</td><td>学习速率</td><td>动量值</td><td>迭代次数</td></tr><tr><td>10</td><td>0.1</td><td>0.05</td><td>100</td></tr></table></body></html>

模型调优过程中训练集的均方误差曲线如图7所示。

由图7得知，当迭代次数在100次的时候，模型性能已经达到较好的训练效果且趋向于稳定状态。虽然迭代次数的增加有利于提高故障识别效果，但是计算时间同时也会大大增加。

综合考虑识别效果和计算成本，本文选取迭代次数为100。

![](images/1368d982649f1801248b61d65ff959828ed66161dcece9ebe17ec37db4ae6201.jpg)  
图7调优过程中训练集的均方误差曲线

# 2.4 实验结果分析

为检验模型的训练效果，将Load0中剩余的200个样本组成测试样本集，如表4所示。

表4故障诊断测试集  

<html><body><table><tr><td>样本类型</td><td>正常</td><td>内圈故障</td><td>外圈故障</td><td>滚动体故障</td></tr><tr><td>样本个数</td><td>50</td><td>50</td><td>50</td><td>50</td></tr><tr><td>样本序号</td><td>1-50</td><td>51-100</td><td>101-150</td><td>151-200</td></tr></table></body></html>

将表4所示的测试集输入到训练完毕的DBN模型，分析输出数据，统计诊断准确率。准确率被定义为正确结果和总结果的比值。结果如图8所示。

![](images/a8742d64faa978bb97e368a4517da7be4fb3c25f3822868736713a5aaa9eb975.jpg)  
图8测试集识别分类结果

图8中，红色型号表示预测分类标签，黑色点表示真实样本标签。蓝色线上值为0的样本点表示预测结果和实际结果一致，值为-1的点表示误分类。由图8可知，200个测试样本，只有第50个测试样本误分类为第二类外圈故障。识别准确率为$9 9 . 5 \%$ 。

为了减少随机因素的影响，实验重复进行10次，每次识别准确率如图9所示。

![](images/1d3af2dce1c5d1f7f54cd797afd434752d981659c93c0e5c460ec270c5cbdf31.jpg)  
图9十次轴承故障诊断识别准确率

10次诊断识别率分别为 $9 9 . 5 \%$ ， $9 9 \%$ ， $9 9 . 5 \%$ 、 $100 \%$ 、 $9 9 . 5 \%$ 、$9 9 . 5 \%$ 、 $9 9 . 5 \%$ 、 $9 9 \%$ 、 $9 9 . 5 \%$ 、 $100 \%$ ，平均准确率为 $9 9 . 5 \%$ ，验证了算法具有较高的诊断精度和鲁棒性。

# 3 实验对比分析

为了进一步评价本文所提方法的有效性，对以下三种情况进行进一步的分析讨论。

# 3.1和其他算法对比

将DBN与GRA、SVM，BPNN进行对比，分别计算四种方法各自10次试验的平均诊断准确率以及相应的标准差，结果如表5所示。

表5四种故障诊断算法分类结果比较  

<html><body><table><tr><td>算法</td><td>平均准确率(%)</td><td>标准差</td></tr><tr><td>GRA</td><td>89.78</td><td>3.25</td></tr><tr><td>SVM</td><td>92.35</td><td>1.36</td></tr><tr><td>BPNN</td><td>94.78</td><td>0.98</td></tr><tr><td>DBN</td><td>99.5</td><td>0.002</td></tr></table></body></html>

从表5可知，所提出的方法比GRA、SVM、和BPNN具有更高的精度和稳定性。其原因是所提出的深度学习方法具有较强的自学习能力。

# 3.2变负载对算法精度的影响

为进一步验证模型的泛化能力，用同样的数据处理方式，以Load0、Load1、Load2、Load3这4种负载下的实验数据依次作为训练集，不同负载下的数据集组成测试样本，进行诊断实验。识别结果如表6所示。

表6变负载诊断结果  

<html><body><table><tr><td rowspan="2">训练集</td><td colspan="4">不同测试集的平均诊断精度(%)</td></tr><tr><td>Loado</td><td>Load1</td><td>Load2</td><td>Load3</td></tr><tr><td>Loado</td><td>99.5</td><td>99.2</td><td>98.8</td><td>98.6</td></tr><tr><td>Load1</td><td>99.25</td><td>99.65</td><td>95.5</td><td>97.15</td></tr><tr><td>Load2</td><td>98.15</td><td>98.5</td><td>99.4</td><td>98.15</td></tr><tr><td>Load3</td><td>96.55</td><td>97.5</td><td>98.8</td><td>99</td></tr></table></body></html>

由表6可知，本文所提方法即使是在变负载情况下，也能获得 $9 5 \%$ 以上的分类识别率。该方法能够在保持分类精度的同时提高鲁棒性和泛化能力。

# 3.3不同样本规模对算法精度和效率的影响

以Load0中400组样本作为实验数据，在总体样本数目不变的情况下，改变训练样本数目和测试样本数目的大小，分别代入DBN 模型进行训练和诊断实验。具体数据集和实验结果如表7所示。

表7不同训练集的诊断结果  

<html><body><table><tr><td>训练集/测试集</td><td>平均测试精度(%)</td><td>耗时(s)</td></tr><tr><td>360/40</td><td>100</td><td>17.614</td></tr><tr><td>320/80</td><td>100</td><td>15.793</td></tr><tr><td>280/120</td><td>99.8</td><td>14.854</td></tr><tr><td>240/160</td><td>99.7</td><td>12.714</td></tr><tr><td>200/200</td><td>99.5</td><td>11.196</td></tr></table></body></html>

表7给出了训练样本数目不同对本文算法诊断结果的影

响。可以看出，随着训练样本的增加，本文算法的精度保持增长，并且总是超过 $9 9 . 5 \%$ 。因此，所提方法能够有效避免过拟合。一般来说，训练样本规模越大，将会达到更高的测试精度和更多的计算时间。由于本文采用特征提取方法缩小了深度学习输入的数据维度，因此，时间消耗不会大幅度增加。如果直接将原始数据输入到DBN进行模型训练，时间消耗将成数十倍增加，尤其是训练集的样本增多时。

# 4 结束语

本文提出基于小波包_AR谱估计和深度学习的轴承故障诊断算法，并将所提出方法应用于轴承信号的分析。结果表明，本文方法在同等负载情况下诊断精度达到 $9 9 . 5 \%$ ，变负载仍达到 $9 5 \%$ 以上识别率，验证了该方法可以实现更高更可靠的诊断性能。

该方法具有以下优势：对数据集进行了特征提取，可以滤除一部分的噪声，同时大大降低了模型训练的时间;DBN具有较强的自学习功能，大大提高模型诊断精度。

下一步研究方向是：将这种方法应用于更多类型的机械;对复杂工况下的故障诊断技术进行进一步的研究。

# 参考文献：

[1]Wei Zexian,Wang Yanxue,He Shuilong,et al.A novel intelligent method for bearing fault diagnosis based on ainity propagation clustering and adaptive feature selection [J]. Knowledge-Based Systems,2017,116: 1-12.   
[2]武哲．旋转机械故障诊断与预测方法及其应用研究[D].北京：北京交 通大学，2O16.(Wu Zhe.Research on Fault Diagnosis and Prognosis Method and Its Application for Rotating Machinery [D]. Beijing: Beijing Jiaotong University,2016.)   
[3]邓飞跃.滚动轴承故障特征提取与诊断方法研究[D].北京：华北电力 大学，2O16.(Deng Feiyue.Research on fault feature extraction and diagnosis method of rolling element bearing [D].Beijing: North China Electric Power University,2016.)   
[4]邢欣，崔亚辉，刘晓琳，等．一种自适应提取有效信号的滚动轴承故障 诊断方法[J].噪声与振动控制，2018,38(2):150-153.(Xing Xin,Cui Yahui,Liu Xiaolin,et al.A fault diagnosis method for rolling bearings based on adaptive extraction of efective signals [J].Noise and Vibration Control,2018,38 (2): 150-153.)   
[5]Chen Jinglong,Li Zipeng,Pan Jun,et al.Wavelet transform based on inner product in fault diagnosis of rotating machinery:A review [J].Mechanical systems and signal processing,2016,70:1-35.   
[6]Zhao Hongshan,Xu Fanhao,Xu Wenqi,et al.Feature extraction method of transformer vibration based on ensemble empirical mode decomposition subband [C]// Proc of IEEE International Conference on Power System Technology. 2016:1-6.   
[7]张玲玲，肖静．基于 MATLAB 的机械故障诊断技术案例教程[M].北 京：高等教育出版社，2016:140-150.(Zhang Lingling,Xiao Jing.Case

study of mechnical fault diagnosis technology based on MATLAB [M]. Beijing:Higher Education Press,2016:140-150.)

[8] 常春，王国威，梅检民，等．基于小波包-AR 谱和支持向量机的连杆轴 承故障诊断 [J]．军事交通学院学报,2015,17(4):40-44.(Chang Chun, Wang Guowei,Mei Jianmin,et al. Connecting rod bearing fault diagnosis based on the wavelet packet-auto regressive model spectrum and support vector machine [J].Journal of Military Transportation University,2O15,17 (4): 40-44. )   
[9]Liu Ruonan,Yang Boyuan,Enrico Zio,et al.Artificial intelligence for fault diagnosis of rotating machinery:A review [J].Mechanical Systems and Signal Processing,2018,108:33-47.   
[10]吴魁，王仙勇，孙洁，等．基于深度学习的故障检测方法[J].计算机 测量与控制,2017,25(1O): 43-47.(Wu Kui,Wang Xianyong,Sun Jie,et al.Fault diagnosis method based on the deep belief network [J]. Computer Measurement & Control.2017,25(10): 43-47.)   
[11] Hinton G,Deng Li,Yu Dong,et al.Deep neural networks for acoustic modeling in speech recognition: the shared views of four research groups [J].IEEE Signal Processing Magazine,2012,29 (6): 82-97.   
[12] Jiang Mingyang,Liang Yanchun,Feng Xiaoyue,et al.Text classification based on deep belief network and softmax regression [J]．Neural Computing and Applications,2018,29 (1): 61-70.   
[13]雷亚国，贾峰，周昕，等．基于深度学习理论的机械装备大数据健康监 测方法[J].机械工程学报,2015,51(21):49-56.(Lei Yaguo,Jia Feng,

Zhou Xin,et al.A deep learning-based method for machinery health monitoring with big data[J]. Journal of Mechanical Engineering,2O15,51

(21):49-56.)   
[14]李艳峰，王新晴，张梅军，等．基于奇异值分解和深度信度网络多分类 器的滚动轴承故障诊断方法[J].上海交通大学学报，2015，49(05): 681-686.(Li Yanfeng,Wang Xinqing,Zhang Meijun,et al.An approach to fault diagnosis of roling bearing using svd and multiple DBN classifiers [J].Journal of Shanghai JiaoTong University,2015,49 (O5): 681-686.)   
[15]Hinton G E,Osindero S,The YW.A fast learning algorithm for deep belief nets [J].Neural Computation,2006,18:1527-1554.   
[16] Fischer A,Igel C.An introduction to restricted Boltzmann machines [C]// Proc of Iberoamerican Congress on Pattern Recognition.Berlin: Springer, 2012: 14-36.   
[17] Larochelle H, Erhan D,Courville A,et al. An empirical evaluation of deep architectures on problems with many factors of variation [C]//Proc of the 24th International Conference on Machine Learning.New York:ACM Press,2007:473-480.   
[18] Ackley D H,Hinton G E,Sejnowski T J.A learning algorithm for Boltzmann machines [M// Readings in Computer Vision.1987: 522-533.   
[19] KarlPL.On lines and planes of closest fit to systems of points in space [J]. Philosophical Magazine Series 6,1901,2 (11) .   
[20] Hinton GE,Osindero S,Teh YW.A fast learning algorithm for deep belief nets [J].Neural Computation,2006,18(7): 1527-1554.