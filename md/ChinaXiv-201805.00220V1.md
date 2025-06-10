# PCA+CHMM在设备性能退化状态识别中的应用研究

钟飞1，宁芊1,²，周新志1,²，赵成萍1(1．四川大学 电子信息学院，成都 610065;2.电子信息控制重点实验室，成都 610036)

摘要：为了准确识别机械设备当前所处的退化状态，研究了一种基于PCA（主成分分析）和CHMM（连续型隐马尔可夫模型）结合的性能退化状态识别方法。首先提取设备振动信号全寿命周期的时域、频域、时频域的特征，经过初步筛选后组成新的特征集，使用PCA方法对其进行降维处理；然后利用降维后的数据，训练一个全寿命周期CHMM用来确定退化状态数目，再针对每个退化状态训练一个CHMM，通过比较观测序列处于各个模型下的似然概率值判断设备当前所处的退化状态；最后通过实验对比了PCA $+$ CHMM和PCA+SVM、PCA+KNN、PCA $\cdot ^ { + }$ CART方法的各退化状态识别准确率，结果表明PCA+CHMM的平均识别准确率最高、识别效果较好，适用于设备退化状态的识别。

关键词：性能退化；主成分分析；连续隐马尔可夫模型；特征降维；退化状态识别; 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.07.0679

# Application of PCA $+$ CHMM in equipment performance degradation state recognition

Zhong Fei1, Ning Qian1,2, Zhou Xinzhi1,²2, Zhao Chengpingl (1.CollegeofElectronics&InformationEngineeringSchuan UniversityChengdu6lo65,China;2.Science&Techology on Electronic Information Control Laboratory,Chengdu 610036)

Abstract: Inordertoacurately identifythedegradationstateof mechanicalequipment,this paperresearchedarecognition method ofperformance degradation statebased onPCA (principal componentanalysis)and CHMM(continuous hidden markov model).Firstlyextractedthevibrationsgnal'stimedomain,frequencydomainandtime-frequencydomainfeaturesinfullie cycle,thenconstructed anew feature setbyscreening the features,then performed PCAdimensionality reduction for this set; Secondly,traineda fullifecycle CHMMtodeterminethenumberofdegraded states byusingofreduced dimension feature data,Andthentraininga CHMMforeach degradedstate,judgingthedegradationstateofthedevicebycomparing thelikeliood probability of the observation sequence under each model; Finally, the accuracy of PCA $^ +$ CHMMand PCA $^ +$ CHM, PCA $^ +$ KNN and PCA $+$ CART methods that to identify each degraded state are compared.Theresults show that the average recognition accuracy of PCA $^ +$ CHMM is the highest, the recognitioneffectis good,and it is suitable for the identificationofdevice degraded state.

Key Words: performance degradation; principalcomponent analysis;continuous hidden markov model; feature dimensionality reduction; degenerate state recognition

# 0 引言

IMS(intelligentmaintenance systems)概念由美国威斯康星大学Lee[1教授率先提出，其中，设备性能退化过程的评估与预测是IMS的核心技术。正确识别设备当前所处的性能衰退状态是进行预测性维护的前提条件，将性能退化识别技术应用到实际的工业生产中去，可以极大程度地减少设备的维修时间和避免设备故障引起的灾难性事故的发生，对降低维护成本和提高生产效率具有十分重要的意义。

设备性能退化状态识别的主要流程包括原始数据的特征提取和识别模型的选取和建立。在特征提取阶段，由于单一性能特征参数包含信息量少、抗干扰性差、故障敏感度低、信息冗余等[2]缺点，一般会同时提取多个特征参数进行设备的性能衰退评估。特征参数维度很高时不可避免地会包含一些冗余信息和噪声，使得模型训练容易出现过拟合的现象，所以必须采用特征降维方法对特征数据进行降维。特征降维可通过特征选择(feature selection)或者特征抽取(feature extraction)实现[3]，特征选择只是简单地从原特征集里面选取子特征集，而特征抽取则是对原特征集的某种映射变换。PCA就是一种常用的特征抽取算法，它能在保证数据信息丢失最少的原则下用更少的不相关综合变量替代原本较多的变量；HMM（隐马尔可夫模型）是关于时序的概率模型，在语音识别、自然语言处理、模式识别等领域有着广泛的应用，考虑到设备的故障诊断和语音识别在模式分类与识别中存在一定的相通性，因此HMM可以用于设备的性能退化过程建模[4I。HMM定义的观测数据类型为离散值，当观测值为连续型数据时，先要对特征集进行矢量量化才能进行HMM的建模，这势必导致特征信息的丢失，从而影响到模型的识别精度。CHMM使用混合高斯密度函数来描述连续型观测值的分布，可以直接利用连续观测值进行模型训练，避免了矢量量化带来的信息丢失。文献[5]采用PCA和DHMM（离散型隐马尔可夫模型）结合的方式应用于发动机的故障诊断；文献[引入状态条件概率矢量对HMM进行不确定性改进后对机载设备的健康状态进行评估；文献[7]提出了一种基于小波包变换和隐马尔可夫模型结合的轴承性能退化评估方法；文献[8]提取设备振动信号的小波包熵作为特征向量，结合高斯混合模型对轴承性能退化过程进行评估；文献[9]成功将EEMD和SVM结合起来应用到滚动轴承的退化状态识别；文献[10]则采用隶属度函数和CHMM对轴承的性能退化过程建模，取得了较好的评估效果。本文研究了一种PCA特征降维和CHMM结合的设备性能退化状态识别方法，并通过一个全寿命周期轴承数据的分析实验证明了此方法拥有较好的识别效果。

# 1 基本理论

# 1.1 PCA介绍

PCA（principalcomponent analysis）是一种较为常用的特征降维方法，由Pearson[1]于1901年提出。主成分分析的基本原理是通过一个正交化线性变换将分量相关的原随机向量转换为分量不相关的新随机向量，新随机向量的分量按方差贡献率的大小分别称为第一主分量、第二主分量、第三主分量，依次类推。一般选取其中综合贡献率超过 $8 5 \%$ 的部分主分量就可以代替原随机变量，达到数据降维的目的。PCA在最大程度地保留原随机向量信息的前提下，消除了特征参数之间的相关性。PCA的计算步骤描述如下：

a)将原始特征集的每个特征作为列向量，构造 $\mathbf { N } ^ { * } \mathbf { M }$ 的样本矩阵X，N为特征长度，M为特征集的特征个数；

b)对X进行中心化处理（矩阵中心化就是先将每个列向量减去对应的均值得到新矩阵，然后新矩阵和新矩阵的转置相乘，各分量再除以N-1）；

c)求解X的 $\mathbf { M } ^ { * } \mathbf { M }$ 协方差矩阵C；

d)求解协方差矩阵C的特征值和特征向量；

将第d)步得到的特征值按从大到小的顺序排列并构造成一个列向量，依此顺序将对应的特征向量作为列向量组合成特征向量矩阵；

e)矩阵X和特征向量矩阵相乘就得到PCA的主分量组成的矩阵；计算各主分量的贡献率（贡献率 $\ L _ { \cdot } =$ 单个特征值/特征值总和），按需选取其中部分主分量。

# 1.2 CHMM定义

HMM（隐马尔可夫模型）最初由Baum等人提出，它是一个关于时序的概率模型，具有很强的时序模式分类能力。HMM是双重随机过程：一个是隐含马尔可夫链的状态转移过程，一个是描述隐含状态与观测序列之间关系的观测过程。不同于HMM，CHMM的观测序列为连续值，观测概率矩阵由混合高斯密度函数组成。

CHMM可以由下面四个参数描述[12]：

a)隐含的状态个数N，可将隐含状态分别记为 $S _ { 1 }$ 、 $\mathbf { S } _ { 2 }$ 、$\mathrm { S } _ { 3 } \cdots \mathrm { S } _ { \mathrm { N } }$ ，时刻t的状态记为 $q _ { t }$ ，那么有 $q _ { t } \in ( S _ { 1 } , S _ { 2 } , S _ { 3 } . . . . . . S _ { \mathrm { N } } )$ b)初始时刻 $t = 0$ 时的各状态分布概率$\pi = ( \pi _ { 1 } , \pi _ { 2 } , \pi _ { 3 } . . . . . . \pi _ { \mathrm { N } } )$ ，简记为 $\pi _ { i } = P _ { r } ( q _ { 0 } = S _ { i } ) $ ， $1 { \le } \mathrm { i } \le N$ ；

c)隐含状态之间互相转移的概率矩阵 $\mathrm { \bf A } = \{ { \bf a } _ { \mathrm { i j } } \} _ { \mathrm { N \times N } }$ ， $a _ { i j }$ 就是状态 $S _ { i }$ 转移到 $S _ { j }$ 的条件概率值，记为 $a _ { i j } = P _ { r } ( q _ { t + 1 } = S _ { j } \mid q _ { t } = S _ { i } )$ ，$1 \leq \mathrm { i } , \mathrm { j } \leq N$ ;

d)观测值概率矩阵 $\mathbf { B } = \{ \mathbf { b } _ { \mathrm { j } } ( \mathbf { O } _ { \mathrm { k } } ) \} _ { \mathrm { N } \times \mathrm { M } }$ ，其中，$b _ { j } ( O _ { k } ) = \sum _ { m = 1 } ^ { M } c _ { j m } N ( o _ { k } , \mu _ { j m } , U _ { j m } )$ ， $1 \leq j \leq N$ ， $M$ 代表混合高斯元的个数， $c _ { j m }$ 是混合高斯元的权重， $\mu _ { j m }$ 是均值向量， $U _ { _ { j m } }$ 是协方差矩阵，同时满足： （204号 $\sum _ { m = 1 } ^ { \mathrm { M } } c _ { j m } = 1$ ， $c _ { j m } \geq 0$ 愛和樂 $\int _ { - \infty } ^ { \infty } b _ { j } ( x ) d x = 1$ ；

综上所述，CHMM可以表示成 $\lambda = ( \pi , N , A , c _ { j m } , \mu _ { j m } , U _ { j m } )$

CHMM包括三个基本问题：评估问题、解码问题和学习问题，相对应的算法分别称为前向一一后向算法、Viterbi算法和Baum-Welch算法。算法相关的详细推理过程同样可参考文献[9]。

# 2 PCA+CHMM退化状态识别方法

设备健康状态从正常到失效会经历一系列的退化状态，对退化状态的识别实质上是模式识别问题，常见的模式识别算法有KNN、朴素贝叶斯、决策树和SVM等。如果能正确识别出设备当前时刻的运行状态，就可以在故障发生之前采取相应的预防或者修复措施，从而避免重大故障的发生，减少维护成本，利用PCA和CHMM结合的方法就可以实现对设备性能状态的准确识别。进行设备退化状态识别之前需要采集设备的运行数据，传感器获取的原始信号数据量大且包含噪声，所以有必要对原始数据进行预处理。

本文提出的退化状态识别方法流程描述如下：

a)对设备原始数据进行预处理，为保证提取特征的全面性和有效性，分别从时域、频域和时频域三个方面进行提取。时域特征分为有量纲和无量纲两种，有量纲特征包括均值、均方根值、方根幅值、绝对平均值、歪度、峭度、方差、最大值、最小值、峰峰值10种，无量纲特征包括波形指标、峰值指标、脉冲指标、裕度指标，峭度指标和偏斜度指标6种；提取频域特征时先对原始信号做快速傅里叶变换，再用频谱和各频率分量值构造共13种特征，顺序编号为频率特征1-13；时频域特征是原始数据的非线性特征，EMD（经验模态分解法）能够提取出原信号中的微弱特征，利用EMD将原始信号分解为6个IMF（本征模态函数）分量，各IMF分量的能量值组成6种时频域特征。以上特征共计35种组成特征集，各特征参数的定义式可参考文献[13];

b)PCA特征降维，从上一步获取的特征集中筛选出能够明显体现设备退化趋势的特征组成新的特征集，按照1.1小节描述的步骤对新的特征集进行PCA降维，并分别计算各主分量的贡献率，选取综合贡献率超过一定阈值的主分量组合成最后的样本数据;

c)确定设备退化状态数目，具体做法是用上一步获取的所有特征序列训练全周期CHMM，全周期CHMM的隐含状态数目分别设置为[4,10]，再利用Viterbi算法进行解码，选取退化状态划分误差小且符合设备退化状态时序转移规律的状态数作为最终的退化状态数目；

d)针对不同的退化状态训练不同的CHMM，共训练N个，通过计算当前观测序列在这N个模型下的似然概率值，似然概率值大的模型就是当前设备的退化状态。

![](images/ea932ebbd1f15e66df03264c14a6a233a3a1dbc16681676656704d97f0c00653.jpg)  
图1PCA+CHMM设备性能退化状态识别方法流程图

# 3 实验分析

# 3.1数据说明

实验采用美国辛辛那提大学智能维护系统(IMS)的第2组Bearing1的全寿命周期加速疲劳振动数据，轴承型号为ZA-2115，实验时转速 $2 0 0 0 r / \mathrm { { m i n } }$ ，径向载荷 $2 6 . 6 \mathrm { k } N$ ，采样频率$2 0 4 8 0 H z$ ，每10分钟采样一次，每次采样持续1秒，第984次采样后轴承失效。如图2所示。原始数据并不能清晰地反映轴承的性能退化趋势。

# 3.2 特征提取和PCA降维

从时域、频域、时频域提取原始信号的35种特征，筛选出对退化状态变化敏感的特征组成特征集。例如，时域的均方根值随着时间变化，具有一定的趋势规律，而歪度特征则在设备失效前几乎看不出有什么变化，显然在特征选取时应该剔除歪度、保留均方根值。

![](images/4f440cc3aaddaae45ed2e8527b7718ce681539e1025809200e80b83c9a1697ed.jpg)  
图2轴承振动信号的全寿命周期时域图

![](images/3394a6e8e9730def58e398d0a73f1a7067318b6b5c402b4f881796d2f8887b41.jpg)  
图3时域特征选取对比图

用同样的方法，对频域和时频域的特征进行筛选。最后选出了均值、均方根值、方根幅值、绝对平均值、最大值、最小值、峰峰值、波形指标、偏斜度指标、峭度指标、频域特征1、频域特征2、频域特征6、频域特征10、频域特征13、IMF1能量值、IMF3能量值、IMF4能量值、IMF5能量值、IMF6能量值共20种特征，此时特征维数仍然较高，如果将其直接作为样本数据，一方面数据量大，处理起来不方便，另一方面很多特征的趋势非常相似，存在信息冗余。

![](images/6f77408de4abf7b84044f90a68fb09b5841f72059ea5c21dd0fd7ad5a70edc12.jpg)  
图4时频域特征存在相似性(冗余）

对这20种特征进行PCA降维，得到第一主分量贡献率为$9 9 . 3 3 \%$ ，第二主分量贡献率为 $0 . 6 3 \%$ ，第三主分量贡献率为

$0 . 0 2 \%$ ，前两个主分量综合贡献率达 $9 9 . 9 6 \%$ ，所以选取第一和第二主分量作为最终的样本数据（特征集）。

![](images/a8ffad1cbffaa77c649e3596efbf2738e8776bf8637912c2a3bae7060040c9ad.jpg)  
图5PCA降维后的特征

# 3.3 CHMM建模与测试

上一小节PCA降维得到的全周期样本数据作为训练序列，分别设置隐含状态数为4至10，利用Baum-Welch算法训练得到不同的全周期CHMM，再分别采用Viterbi算法对样本序列进行解码，通过对比退化状态划分效果来确定退化状态数目。

![](images/5c771c1ae50a3608376804b920770ec3cbd780a2897bb6e8a2abe97473e385d4.jpg)  
图6状态数为4时的划分效果

![](images/7d3211f5e9ef8e3bbd120d54765388c109c79bdbfa01c381cf2b032c55915c68.jpg)  
图7状态数为5-10时的划分效果

如图，状态数设置为5、6、7时，最后一个状态的数据点只有1个，显然不符合实际；状态数设置为8,、9、10时，划分结果出现交错现象，也不符合设备性能的退化规律，只有状态数设置为4时的划分结果较为符合性能退化的时序变化规律，所以将设备退化状态数设置为4，划分区间见表1。

将全周期样本数据分成4个状态区间，每个状态区间的样本数据均按7:3的比例划分训练序列和测试序列，4个训练序列训练得到4个不同退化状态下的CHMM，通过比较当前观测序列在每个退化状态模型下的似然概率值即可实现设备退化状态的识别。

表1设备性能退化状态区间划分及CHMM数据划分  

<html><body><table><tr><td>状态</td><td>正常状态</td><td>轻度退化</td><td>中度退化</td><td>重度退化</td></tr><tr><td>区间</td><td>[1,700]</td><td>[701,879]</td><td>[880,957]</td><td>[958,984]</td></tr><tr><td>训练序列</td><td>[81,570]</td><td>[731,855]</td><td>[891,944]</td><td>[962,980]</td></tr><tr><td>测试序列</td><td>210组</td><td>54组</td><td>23组</td><td>8组</td></tr></table></body></html>

如表1所示，分别将各个状态的测试序列输入到4个模型中，得到4种似然概率输出值的对比如图 $8 { \sim } 1 1$ 所示。

![](images/cc31f313a7dbb9722331f379f17f9ec3c9eca417dbd968b6d5cfa57719cf496d.jpg)  
图8正常状态测试集的似然概率值比较

![](images/b7b1512b0cefde45dce320602080f4e0bc49d76cc02223c52bab00c98b26edf4.jpg)  
图9轻度退化测试集的似然概率值比较

![](images/dac7c9a6d0225a34313e7b7cc5e326ea3dc0a0767b6a2f852644814ac9effadc.jpg)  
图10中度退化测试集的似然概率值比较

![](images/b16e058b6e2fdd707b8cee2e39772225ea14fa832e6ad9ace092315dda008406.jpg)  
图11重度退化测试集的似然概率值比较

同样地，将全寿命周期样本数据（特征集）按7:3划分为训练集和测试集，分别训练KNN、CART、SVM（多分类）模型，对轴承的性能退化状态进行识别，CHMM、KNN、CART和SVM识别准确率对比如表2所示。

表2轴承退化状态识别效果对比  

<html><body><table><tr><td rowspan="2">状态</td><td rowspan="2">正常 状态</td><td rowspan="2">轻度 退化</td><td rowspan="2">中度</td><td rowspan="2">重度</td><td rowspan="2">平均 准确率</td></tr><tr><td>退化</td></tr><tr><td>PCA+CHMM</td><td>99.52%</td><td>96.30%</td><td>100%</td><td>退化 100%</td><td>98.21%</td></tr><tr><td>PCA+SVM</td><td>99.52%</td><td>100%</td><td>86.96%</td><td>75%</td><td>90.37%</td></tr><tr><td>PCA+CART</td><td>97.62%</td><td>92.59%</td><td>95.65%</td><td>50%</td><td>83.97%</td></tr><tr><td>PCA+KNN</td><td>98.10%</td><td>96.30%</td><td>100%</td><td>75%</td><td>92.35%</td></tr></table></body></html>

表2中， $\mathrm { P C A + C H M M }$ 在四种方法里退化状态识别的平均准确率最高，且每种状态的识别准确率均超过 $96 \%$ ，比较均衡；$\mathrm { P C A + C A R T }$ 的平均识别准确率最低，它对重度退化状态的识别效果非常差； $\mathrm { P C A ^ { + } S V M }$ 和 $\mathrm { P C A + K N N }$ 的平均识别准确率均在$90 \%$ 以上，但是对各退化状态的识别准确率却不是很均衡。不同于KNN、SVM和CART等模式识别算法，CHMM可以为每个退化状态训练一个模型，具有较强的时序模式识别能力，恰好符合设备退化状态在时间上分布不均衡的情形。PCA和CHMM结合的方法在设备性能退化状态识别上能够取得了较高的识别准确率，实验证明此方法可行且有效。

# 4 结束语

本文提出PCA和CHMM结合的设备性能退化状态识别方法，PCA起到了去除信息冗余、降低数据维度的作用，CHMM不仅具有很强的时序模式识别能力，而且避免了矢量量化带来的信息损失。利用美国辛辛那提大学提供的轴承数据，通过实验对比知道，此方法适用于设备退化性能状态的识别，具有较高的识别准确率。因为此方法只能识别当前设备所处的退化状态，未来的工作可以从回归算法和CHMM结合的方向着手，实现对设备性能退化状态的预测。

# 参考文献：

[1]Lee J,Kramer B M.Analysis of machine degradation using a neural networkbased pattern discrimination model [J]. Journal of Manufacturing Systems,1993,12 (5): 379-387.  
[2]王建利.滚动轴承性能退化评价与趋势预测研究[D]．大连：大连理工大学,2013.  
[3]汪万紫．对交互特征和自适应聚类算法的研究[D].西安：陕西师范大学,2011.  
[4]夏丽莎，方华京，罗贞．基于隐马尔可夫模型的故障诊断与预报综述[C]//中国控制与决策会议论文集.2013:4881-4884.  
[5]黄家善，张平均．基于PCA与DHMM的发动机故障诊断研究[J]．厦门大学学报：自然科学版,2010,49(5):617-621.  
[6]张金春，张继军，曹彪．基于HMM的机载设备状态健康评估方法研究[J].计算机测量与控制,2015,23(2):491-493.  
[7]肖文斌，陈进，周宇，等．小波包变换和隐马尔可夫模型在轴承性能退化评估中的应用[J].振动与冲击,2011,30(8):32-35.  
[8]李巍华，戴炳雄，张绍辉．基于小波包熵和高斯混合模型的轴承性能退化评估[J].振动与冲击,2013,32(21):35-40.  
[9]魏永合，王明华．基于 EEMD 和 SVM 的滚动轴承退化状态识别[J].计算机集成制造系统,2015,21(9):2475-2483.  
[10]姜万录，杨凯，董克岩，等．基于CHMM 的轴承性能退化程度综合评估方法研究[J].仪器仪表学报,2016,37(9):2014-2021.  
[11] Karl PLII. On lines and planes of closest fit to systems of points in space[J]. Philosophical Magazine Series 6,1901,2(11):.  
[12]RabinerLR.Atutorial on Hidden Markov Modelsand Selected Applicationsin Speech Recognition [J].Readings in Speech Recognition,199o,77 (2):267-296.  
[13]董绍江．基于优化支持向量机的空间滚动轴承寿命预测方法研究 [D].重庆：重庆大学,2012.