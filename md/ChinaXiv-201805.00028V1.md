# 一种改进的DNN算法在雷达信号分选中的应用

陈春利，金炜东

(西南交通大学电气工程学院，成都 610031)

摘要：针对深度神经网络能自动学习数据深层特征的优点进行了研究，提出一种基于深度信念网络的信号分选方法，来解决传统雷达信号分选中人工提取特征的耗时、特征冗余等问题。通过堆叠多层的深度模型对原算法进行改进，克服单一模型学习力的不足，对不同信号的本质特征进行深入学习，融合各个深度模型的后验概率进行分类决策，从而进一步提高了信号的识别率。采用改进方法对七种不同类型的雷达信号进行分选识别，并与其他信号分选方法进行对比，实验结果表明，该方法取得了更好的分类效果，展现出较强的学习数据本质特征的能力，从而验证了算法的有效性和优越性。

关键词：信号分选；深度信念网络；堆叠多层模型；后验概率 中图分类号：TP181 doi:10.3969/j.issn.1001-3695.2017.09.1005

# Application of improved DNN algorithm in radar signal sorting

Chen Chunli, Jin Weidong, Zhang Wenqiang (School ofElectrical Engineering,SouthwestJiao tong University,Chengdu 6loo31,China)

Abstract:Theadvantageofdeepneural network toautomaticallylearn thedeepcharacteristicsofdatawasstudied.This paper proposeda signal sorting method basedon multilayer deep belief networks,in order tosolve the problems of time consuming intraditional radar signal selection,featureredundancyand soon.Basedonthe improved algorithmof depth of stacked multilayermodel,iovercametheproblemofinsuicienttothsinglemodelofearngabilityanddeplysdiedtheetial featuresoftedieretsignal,andfusedteposterorprobabilityofteodeltoakeacasifiationdecision,ostofurther improve thesignalrecognitionrate.Byusing this method tosort7diferenttypes ofradar emitersignal sorting.Compared with otherperformancesignalsorting method,theexperimentalresultsshowthatthis methodobtains betterclassificationresults,and exhibits strong learning ability tonature features,thus itverifies the effectivenessand superiorityofthis algorithm.

KeyWords: signal sorting; deep belief network; stacked multilayer model; the posterior probability

# 0 引言

深度神经网络(depthneuralnetwork,DNN)是近年来热点研究的人工智能算法，又称深度学习。它通过模拟人脑分析问题，对低层次的数据进行组合、学习，从而得到更抽象的高层特征，有利于信号的分类[1。自2006年提出以来，深度学习在手写字体、语音识别、图像处理领域有很广泛的应用，同时深度神经网络拥有深度信念网络、卷积神经网络、自动编码器等多种模型[2]。其中，深度信念网络（deep beliefnetworks，DBN)作为构造这种深层神经网络结构的先驱，具备强大的数据特征表达能力。它能够建立数据与标签之间的一个联合分布，通过层级间的网络训练从原始样本中学习到数据的深层联系作为本质特征进行分类识别。

未知雷达辐射源信号分选是电子对抗战中的重要基础部分，通过分析和处理长期累积的大量的雷达辐射源信号，对进一步研究雷达类型和威胁性质有重要意义[1]。

传统的基于脉冲描述字(pulse description word,PDW)的特征，如：TOA、RF、PA、PW、DOA已经无法满足现代电子战的需求[1]。近几年，时频特征[1]、小波包特征[2]和小波脊频特征[4]等参数在信号识别领域中均取得了较好的识别效果，但这些特征仍存在一些值得考虑的问题，特征提取方法在信号识别系统的有效性和普适性值得深入思考；特征提取过程存在耗时，人工定义特征不充分，特征冗余等问题。若能获得强区分力的信号本质特征，对后续分类器设计和识别性能的改善有很大的帮助[3]。

随着现代化军事技术的高速发展，雷达信号逐渐变得参数多变、形式复杂，导致信号分选变得困难。而DBN模型能自动地深入学习信号的本质特征，适合处理信号的分选识别问题[6]，但单一模型存在学习力不足、精度不高等情况，在此基础上，通过堆叠多个不同网络结构的DBN模型得到一种新的改进方法：堆叠深度信念网络(stackingDBN)。这种方法考虑从多角度分析数据、更全面地学习到更多的特征，从而更准确地分类[4]。

# 1 深度神经网络

2006年，Hinton提出一种深度神经网络的概率生成模型：深度信念网络[4,5]。通过训练其神经元间的权重，按照最大概率来生成训练数据。

# 1.1DBN 的结构

DBN由多个受限玻尔兹曼机(restrictedBoltzmannmachines,RBM)堆叠得到的深层网络，通过训练多层RBM来训练DBN[]。模型包含两个部分:可视层和隐含层，隐含层每个神经元通过RBM不断地训练挖掘数据的深层联系，即深层特征。如图1所示。

![](images/83189ad6d844bfb21c8d128e8e1f3aacecd2d071eaa6bde204f09702ba2946dd.jpg)  
图1DBN 结构示意图

在每一层训练中，先用数据向量来得到隐层量，再把这一隐层的学习输出当作下一层(高层)的输入数据，通过层层递进学习的信息来训练网络。这种方法被称做逐层贪心算法；最底层代表了原始数据向量，底层每一个神经元代表输入数据的一维特征。

# 1.2 RBM原理

RBM的训练过程，实际上是求出一个产生训练样本的概率分布[7]。通过输入信号和隐层特征来尽可能地重构输入信号，通过一个能量函数来表征，如式（1）所示。

$$
E \left( \nu \cdot h \left| \theta \right. \right) = - \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } w _ { i j } h _ { i } \nu _ { j } - \sum _ { j = 1 } ^ { m } b _ { j } \nu _ { j } - \sum _ { i = 1 } ^ { n } c _ { i } h _ { i }
$$

其中： $\theta = \{ \mathrm { w } , \mathrm { b } , \mathrm { c } \}$ 是RBM的模型参数，通过求解极大似然函数获得， $m$ 表示可视层节点数， $n$ 为隐层节点数， $b$ 、 $\mathbf { \Psi } _ { c }$ 分别表示可视层和隐层节点偏置， $w _ { i j }$ 表示层间的连接权值。

训练RBM的目的是使得能量函数取得最小值。基于上述分析，可得到RBM模型 $( \mathbf { v } , \mathbf { h } )$ 的联合概率分布，如式（2）所示。

$$
P ( { \mathrm { v } } | \theta ) { = } \frac { 1 } { Z ( \theta ) } { \sum _ { h } } { \exp } ( { - E } ( { \mathrm { v , h } } | \theta ) )
$$

其中： $Z ( \theta )$ 是一个归一化常数，表示所有 $( \mathbf { v } , \mathbf { h } )$ 的分布之和,计算公式如式（3）所示。

$$
Z ( \theta ) = - \sum _ { \nu , h } e ^ { - E ( \mathrm { v , h } | \theta ) }
$$

当输入一定的情况下，第 $j$ 个隐层节点的概率分布情况如式（4）所示。

$$
P ( h _ { j } = 1 | \mathrm { v } , \theta ) = g ( b _ { j } + \sum _ { j } \nu _ { i } \boldsymbol { W } _ { i j } )
$$

当隐层节点确定的情况下，第 $i$ 个重构信号的分布情况如式（5）所示。

$$
P ( \nu _ { i } = 1 | h , \theta ) = g ( \underset { C _ { i } } { \sum } + \underset { j } { \sum } h _ { j } w _ { i j } )
$$

# 1.3DBN 训练过程

a)输入新的数据向量 $X = \{ x _ { 1 } , x _ { 2 } , . . . x _ { m } \} ^ { T }$ ，初始化权重，训练第一层RBM的权值系数；

b)利用Gibbs采样进行数据的重构和不断学习，借助重构误差不断地更新层与层之间的权值 $w _ { i j }$ ·

c)采用非监督逐层贪婪训练方法对DBN进行训练，将第一层RBM的输出作为第二层RBM的输入，以此递归计算出每层的隐元向量和权值系数矩阵；

d)在模型顶层输出层加入原数据的标签集，使用BP（errorbackpropagation）算法微调整个网络，使各层连接权值尽可能达到最优，从而输出分类结果。

# 1.4算法参数的影响

在训练中，每增加一层网络或者增加每层节点数都会增加更多更深的学习环节，改善学习效果，从而更接近数据的真实表达。但网络层数和节点数过多增加会使结构复杂，计算量变大，反而会降低算法的效率和准确度。

DBN模型学习过程中，学习率的取值直接影响算法效率，如果学习率太小，则会使训练收敛过慢；反之则会导致代价函数振荡，无法收敛[8.9]。

# 2 基于StackingDBN的信号分选

# 2.1Stacking DBN过程

利用多层次的DBN 模型能得到不同的预测结果，这样能克服单个模型学习力不足、网络结构设计欠缺的问题，学习到更全面的本质特征，从而得到更准确的分类准确度。其基本结构如图2所示。

![](images/c2457a0c46a1c689b9e4e5fec8def267321973ccd6ec23fda15463e9e70d4857.jpg)  
图2StackingDBN方法的结构图

基本步骤如下：

a)先将研究的数据集按一定比例分为训练集和测试集，通过多个DBN模型（每层节点数为100/200/300）对信号进行不同层次地深入学习，将学习结果通过SoftMax方法变成基本概率输出;

b)针对训练集，通过多个深度学习模型建立层叠泛化的学习框架，组成本文的StackingDBN模型;

c)将训练得到的层叠深度模型进行新的数据(测试集)的学习预测，输出每个输入的分类概率；

d)再将结果综合起来进行最终的决策判别，输出结果。其中，输入量X指本文中雷达信号样本的频谱变化值特征，Y为每个输入样本的真实标签，即信号属于某部雷达的类别号。通过学习得到不同模型的后验概率进行最终的分类决策。

# 2.2信号分选流程

本文基于改进的堆叠DBN 模型的雷达辐射源信号分选识别流程如图3所示。

预处理 深度训练 Stacking 预测结果 分类(FFT) 模型 DBN （后验概率） 决策

首先将对雷达时序信号进行预处理，先通过FFT，获取基本频域信息即频谱波形分布特征，作为深度模型训练网络的输入X；然后按照图2中方法来进行多层模型的训练和学习，得到多层DBN的分类后验概率，并进行线性融合[12,15]；最后采用泛化能力强的SVM作为分类决策层，得到最终的分类结果。

![](images/7a4ec5acd42c0895b6eb21ba7cf62b85c3973b1345c25b7febb0207d7c15a11a.jpg)  
图3改进的雷达信号分选算法框图

# 3 雷达辐射源信号分选

信号分选识别的实质就是从接收机接收到的脉冲流中分离出属于单部的雷达辐射源脉冲序列的过程[2]，其基本过程如图4所示。

# 3.1雷达信号特征分析

雷达信号分选主要是根据混合雷达信号参数之间存在相似性和差异性的规律实现的[2]。表征信号特征的参数主要有频域参数，包括载波率、频谱、频率变化规律等；空域参数包括信号的到达方向、方位角等；时域参数包括脉冲到达时间、脉冲宽度、脉冲变化规律；以及时频域、小波变换域特征等。

# 3.2数据介绍

本文所采用的实验数据来源于某重点实验室提供的雷达仿真监测数据，其中研究的雷达信号类型的参数均参考已投入使用雷达的参数进行设置。

在数据仿真实验中，第一类雷达信号的载频为 $9 5 0 0 \mathrm { M H z }$ 脉宽 $1 . 2 ~ \mu \mathrm { s }$ ，PRI抖动范围 $1 6 5 6 { \sim } 1 7 5 0 ~ \mu \mathrm { s }$ ；第二类雷达的载频为$9 6 8 2 ~ \mathrm { M H z }$ ，脉宽固定 $8 ~ \mu \mathrm { s }$ ；第三部类雷达为 $9 5 4 0 ~ \mathrm { M H z }$ ，脉宽$0 . 5 ~ \mu \mathrm { s }$ ；第四类雷达的载频为 $9 5 3 0 \mathrm { M H z }$ ，脉宽固定 $0 . 5 ~ \mu \mathrm { s }$ ，第五类雷达的载频按照 $9 5 1 3 \mathrm { M H z } \mathrm { , } 9 5 1 8 \mathrm { M H z } \mathrm { , } 9 5 2 3 \mathrm { M H z } \mathrm { , } 9 5 4 8 \mathrm { M H z }$ $9 5 5 3 \mathrm { M H z }$ 、9563MHz六个频点波位组变线性调频，脉宽是3\~5个一组，每一组固定，取值 $6 { \mu \mathrm { s } }$ 、 $1 2 \mu \mathrm { s }$ 、 $1 8 \mu \mathrm { s }$ 任意；第六类雷达载频按照 $9 6 1 2 ~ \mathrm { M H z }$ 、 $9 6 1 8 ~ \mathrm { M H z }$ 、 $9 6 2 4 ~ \mathrm { M H z }$ 、 $9 6 4 8 ~ \mathrm { M H z }$ 、$9 5 5 3 \mathrm { M H z }$ 、 $9 6 5 4 \mathrm { M H z }$ 频点波位组变线性调频，取值 $2 5 \mu \mathrm { s }$ 、32${ \mu \mathrm { s } } , 5 0 { \mu \mathrm { s } }$ 任意；第七类雷达载频 $9 5 0 0 { \sim } 9 7 0 0 \mathrm { M H z }$ ，脉宽 $1 . 1 ~ \mu \mathrm { s }$ PRI固定 $1 2 6 9 ~ { \mu \mathrm { s } }$ 。

# 4 仿真实验与分析

# 4.1数据预处理

由于实际电磁环境的复杂性和信号接收机的局限性，接收到的脉冲会存在漏脉冲和虚假脉冲等不确定情况，针对脉冲维数不一致的问题，对仿真的雷达脉冲长度进行一定的筛选，剔除掉过长和过短的脉冲序列。每部雷达通过采样得到400个信号样本，并进行FFT变换，作为数据集的增强处理，获取频谱波形信息特征，作为深度网络的输入向量。

# 4.2参数选取

4.2.1网络结构对分类效果的影响

DBN选取多隐层结构，无监督学习过程速率与有监督学习速率均先设为1，激活函数设定Sigmoid函数的情况下，来研究其他重要参数对算法的影响。

a）在设定每层节点数为100，改变训练次数的情况下研究不同网络层数的效果，实验结果如图5所示。

![](images/ad813b0bb6a3dfa98cbec102d475f0f60dab8a2229677afa7095f0da059e40f2.jpg)  
图4雷达辐射源信号分选基本过程  
图5不同隐层层数下分类性能变化情况

由上述实验可知，不同隐层数的网络随着训练次数的增加，运算变得复杂，其分类性能整体呈现缓慢下降的趋势。针对本文的仿真信号，具有2个隐层的DBN算法在训练次数较少的情况下能获得比较好的分类性能。

b)基于上述实验的结果，研究不同的隐层节点数对信号分类性能的影响，结果如图6所示。

![](images/c303e8f53dd7ec7caca5ad2c607a83c15f332be8baab971dd60dd2dd30ac2fec.jpg)  
图6不同隐层节点数下的分类性能研究

由上述实验可得，针对本文仿真的信号，随着隐层节点数的不断增加，其结构变得复杂、不稳定，其分类性能整体呈现先上升后缓慢下降的趋势，在节点数为120时取得最高的分类准确率，整体的平均识别率在 $93 \%$ 以上。

# 4.2.2学习率对分类效果的影响

参考相关文献和经验值可对深度信念网络结构作如下设置[12-13]:DBN 选取两层隐含层结构，设定每层节点数为120，研究无监督与有监督学习过程学习速率因子的影响，实验结果如图7所示。

![](images/6329859d9f4e978b82ef5f09bf8fcb6583cb3e8956cb99e1b4354afeccba967e.jpg)  
图7不同DBN学习率因子的影响情况

由上述实验可得， $R I$ 在 $0 { \sim } 0 . 3 6$ 比较小的范围有稳定值，而R2在0.5时能取得比较高准确率，随着学习率的增加，会导致代价函数振荡，无法收敛。所以，一般结合实际情况，经过实验验证选取合理的值。

# 4.2.3堆叠模型层数对分类效果的影响

设定DBN模型基本结构为：两层隐层，每层隐层节点数为120，在上述实验基础上，研究本文所提算法中堆叠模型的层数对分类结果的影响，实验结果如图8所示。

![](images/e42fc4de9a6c7d5f4c9cce62850e323cbee7b9da30de5261c13823aa06dff6f7.jpg)  
图8不同DBN 模型堆叠层数对分类性能的影响

由以上实验可知，针对仿真的雷达信号的频谱分布特征，当 StackingDBN模型堆叠层数达到4层时，取得最好的分类效果，其准确率达到 $9 7 \%$ 以上。而随着堆叠层数的继续增加，模型结构变得复杂，学习到的信号特征可能存在误差、冗余等情况，所以其准确率有所下降。

# 4.3不同分类方法性能比较

通过实验进行不同分类方法的性能比较和分析[15]。其中，SAE方法是通过堆叠多个自动编码器形成的模型，它能学习数据集中的特征，具有较强的鲁棒性和特征表达能力；SVM分类器是目前模式识别、分类领域具有强泛化能力的方法；后一种方法是基于脉冲描述字特征的信号分类方法，这种方法特征提取耗时，受先验知识的制约。

针对本文仿真的7类不同类型的雷达信号，经过FFT变换获得的频域波形分布特征作为实验数据。参考相关文献其他算法进行比较，其中，SAE 深度模型方法经过实验选择较优的参数进行雷达信号识别；SVM分类方法经过5折交叉验证方法和网格寻优实验获得较优的参数，进行信号分类。实验结果如表1所示。

表1不同信号分选方法性能比较  

<html><body><table><tr><td>分类方法</td><td>本文算法</td><td>DBN</td><td>SAE</td><td>SVM</td><td>PDW+SVM</td></tr><tr><td>准确率/%</td><td>97.25</td><td>93.5</td><td>90.21</td><td>88.25</td><td>92.5</td></tr></table></body></html>

从表1中可以看出，针对仿真的雷达信号，DBN方法能取得 $9 3 . 5 \%$ 的准确率，而本文所改进的StackingDBN方法得到了更高的准确率 $9 7 . 2 5 \%$ ，比堆叠自动编码器SAE方法分类准确率高出约 $7 \%$ ，比直接采用SVM对频域特征进行分类的方法高出 $9 \%$ 左右，比基于脉冲描述字特征的分类方法高了 $5 \%$ 左右。表明本文方法通过多层网络的特征学习，能够提取到更充分、全面的本质特征[16]，从而很好地改善了分类效果。

# 5 结束语

本文从雷达信号频域波形分布特征出发，结合多层次的深度信念网络改进模型对深层特征进行更全面、自动地学习，并探讨了DBN的隐含层参数、迭代次数以及学习率对信号分类的影响，从而优化和简化了网络结构。其次通过融合多个深度学习模型的预测结果进行决策分析，取得了较理想的分类效果，其分类准确率都高于其他分类方法。

# 参考文献：

[1]Salakhutdinov R,Hinton G E.Deep Boltzmann machines [C]//Proc of the   
12th International Conference on Artificial Intelligence and Statistics.2009:   
448-455. [2] 张葛祥，荣海娜，金炜东．基于小波包变换和特征选择的雷达辐射源信 号识别[J].电路与系统学报,2006,11(6):45-49. [3]Zhou Zhiwen,Huang Gaoming,Gao Jun, et al.A deep learning algorithm forradar emitter recognition [J].Journal of Xi'an Electronic and Science University,2017,44(3):85-90.   
[4]余志斌．基于脉内特征的雷达辐射源信号识别研究[D]．成都：西南交 通大学,2010.   
[5]Sarikya R,Hinton G,Deoras A.Application of deep belief networks for natural language understanding [J].IEEE Transon Audio,Speech,and Language Processing,2014,22(4):778-784.   
[6]Jurgen S.Deep learning in neural networks:an overview [J].Neural Networks,2015,61: 85-117.   
[7]Welling M,Hinton G E.A new learning algorithm for mean field Boltzmann machines [C]// Proc of International Conference on Artificial Neural Networks.2002:351-357.   
[8]Hinton G,Salakhutdinov R.Reducing the dimensionality of data with Neural Networks [J]. Science,2006,313 (5786): 504-507.   
[9]Bengio Y,Lamblin P,Popovici D.Greed layer-wise training of deep networks [J].Advances in Neural Information Processing Systems,2o07,19: 153-160.

[10] Hinton G.Deep neural networks for acoustic modeling in speech recognition: the shared views of four research groups [J]. IEEE Signal Processing

Magazine,2012,29 (6): 82-97.   
[11] Qiu Xueheng, Zhang Le,Ponnuthurai N,etal.Ensemble deep learning for regression and time series forecasting[C]//Proc of IEEE Symposium on Computational Intelligence in Ensemble Learning.2014:122-126.   
[12] Deng Li,Yu Dong,Platt J. Scalable stacking and learning for building deep architectures [C]// Proc of IEEE International Conference on Acoustics, Speech and Signal Processing.2012.   
[13] Sun Zhijun,Xue Lei,Xu Yang.Feature extraction algorithm for marginal Fisher analysis based on deep learning [J].Journal of Electronics and Information,2013,35(4): 805-811.   
[14] Chamasemani FF,Singh Y P.Multi-class support vector machine (SVM) classifiers-anapplication inbioinspiredcomputing: theoriesand applications(BIC-TA)[C]//Proc of the 6th International Conference on BioInspired Computing: Theories and Applications.2011.   
[15]Mohamed A,Dahl G E,Hinton G.Acoustic modeling using deep belief networks [J]. IEEE Trans on Audio, Speech and Language Processing,2012, 20: 14-22.