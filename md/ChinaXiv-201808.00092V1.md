# 基于脑电信号的情感识别研究

张家瑞，王刚

(空军工程大学 防空反导学院，西安 710051)

摘要：针对如何提高脑电信号情感识别的正确率这一问题，在得到的原始脑电信号进行分频带特征提取后，一方面采用支持向量机、K近邻算法、朴素贝叶斯和神经网络算法对小波熵、近似熵、功率谱密度、微分熵，进行训练和分类学习；另一方面，基于4种不同的电极放置方式，对微分熵特征采用支持向量机和经遗传算法参数寻优的支持向量机算法进行训练。结果显示，在12通道条件下能够得到 $9 1 . 9 9 \%$ 的总体准确率，最高情感识别准确率已经达到 $9 7 . 5 9 \%$ 。研究结果表明，减少电极可以获得较高的情感识别分类结果，并且采用参数寻优后的支持向量机算法能够有效提升准确率。

关键词：脑电信号；情感识别；微分熵；通道选择；遗传算法 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.05.0295

# Research on emotion recognition based on EEG signals

Zhang Jiarui, Wang Gang (CollegeofAir&MissileDefense,AirForce EngineeringUniversity,Xi'an71oo51,China)

Abstract:Therelationship betweenEEGand emotionrecognition hasatracted wide atention,however,the partialacuracy ofemotionrecognition islow.For improving theaccuracyrate,afterfilteredtheoriginalEG signal to5bands,this paper thenextracted4features,thedierentialentropy,powerspectralensitywaveletetropyandapproximateentropy.Finally selected the features and used the support vector machine, $\mathbf { k }$ -nearest neighbor,naive Bayesian model and multi-layer perceptron for classification learning.The paper trained DE feature toget the higher acuracywith 4 different electrode placement methods by Support vector machine,moreover, the accuracy rate reach $9 1 . 9 9 \%$ of all EEG band energy in the case of 12 channels. What’s more, we get the average accuracies up to $9 7 . 5 9 \%$ with SVM that using genetic algorithm to acquire the optimization parameters.

Key Words: EEG signal; emotion recognition; differential entropy; selection of channels; genetic algorithm

# 0 引言

随着人工智能的蓬勃发展，如何使得计算机实现与人类相似的感知功能、思维功能和行为功能已成为研究人员关注的热点问题，智能化、人性化的人机交互的重要环节就是情感计算技术[1]。Anderson、McOwan[2]和Ang[3]利用指头、面部表情，声音、手势[4等反应作为辨识情感的特征表现来辨识人的不同情感状态，然而这些人体信号往往容易被掩盖；另一些人体的生理信号如心跳、呼吸、体表温度等，也是由于其准确率不高而不被引入到情感识别领域。正因为如此，近年来脑电信号由于其分类识别准确率高的优点，逐渐被引入到了情感识别研究领域，并得到了广泛的应用。Hosseini等人[提取脑电信号的近似熵特征，利用支持向量机进行情感识别，正确率达到$7 3 . 2 5 \%$ ；Yuen等人[提取脑电信号的六种时域统计特征，利用神经网络识别愤怒、悲伤、惊奇、愉快等情绪，识别正确率最高可达 $9 5 \%$ ；Madsen等人7采用时间信息表达了的情感的重要性；Li[8]等人提出了一种选择情感识别最佳波段的频带搜索方法台湾大学的Lin 等人[9采用支持向量机模型，根据脑电信号将情感状态分喜、怒、哀、乐四类，得出了30个与之有关的脑电情感特征，并验证了大脑中对于情感识别有巨大作用区域的位于额叶和顶叶；瓦伦齐[10]通过了8个电级：AF3，AF4，F3，F4，F7，F8，T7和T8，实现了 $8 7 . 5 \%$ 的分类准确率；北京航空航天大学毛峡教授对情感的生理信号的一些现象进行了初步研究，同时清华大学蔡莲红老师对情感的多模态也进行研究分析。虽然在采用脑电信号对情感识别研究取得了一些进展，但如何采用多种分类方法在多频带条件下提取多个特征去充分挖掘脑电信号的内在信息，目前的研究不太多，并且在如何选择关键的通道和频带以及如何评价选定的电极方面还尚未得到

充分的研究。

基于上述原因，本文针对脑电信号和情感模型做了深入分析，进行特征的提取并采用多种分类器进行分类训练学习，找出了脑电信号与情感之间的相关频带和通道，结合支持向量机（support vector machine，SVM)、K 近邻(k-nearest neighbor,KNN)、朴素贝叶斯（naiveBayesian model，NB）、多层感知器神经网络模型（multi-layer perceptron，MLP）以及遗传算法对SVM进行参数寻优，实现了基于脑电信号的情感识别。

# 1 脑电情感识别

# 1.1实验设置及数据

设计高效、可靠的情感刺激对情感实验具有重要意义。现在，在情感研究中有各种各样的刺激，如图片、音乐和电影等。与其他刺激相比，使用电影有几个优点，由于电影片段通常都有一定的情节，代入感较强，情感电影包含场景和音频，它们可以使主题暴露于更真实的场景，并引发强大的主观和生理变化。因此本实验采用电影片段作为情感的诱发的素材。所以在实验中，选择有三个类别情感(积极、中立和消极)评价的情感电影片段来帮助诱发受试者的情绪。情感状态的变化是瞬时的，更是难以用数据扑捉到。大量研究表明，有些生理信号指标是对人体所处的特定唤醒水平的反应，这些生理指标所展示的信息能够反应出多种不同的情感状态。目前公开的情感识别训练集情况并不乐观，很多都是研究者私有的训练集，本次的实验数据来源[1I:12]，该数据集选取15 个剪辑片段，每一个片段都持续大约 $4 \mathrm { m i n }$ 。

# 1.2脑电情感识别流程

基于脑电信号的情感识别，按如图1进行处理，所示的脑电情感识别循环包含几个主要过程：

![](images/233e0605d25ae6a2cd6953c26835ed98774c2e4acbd3d28c8932ac6dc9a1486e.jpg)  
图1脑电信号情感识别流程图

主要采用脑电图信号进行测量，从人体大脑皮层的62个通道上获得受试者观看电影片段时的脑电信号。为了得到更加准确的结果，本文将6位受试者，每位都得到的15个电影片段下的脑电数据，按照9：6的比例随机构建训练集和测试集进行分类训练。我们选择的窗口长度为1s，表明62个电极都是每隔1s 对脑电数据进行记录，得到的脑电信号在分五个频带和不分频带的情况下都进行分类训练学习，得到准确率。另一方面，在多通道条件下采用SVM进行分类训练后采用遗传算法对SVM的参数寻优后得到分类结果。

# 2 脑电信号数据建模

# 2.1特征提取

无论是信号检测分类还是识别处理，都基于对信号的特征提取，有了能够代表所测信号的特征，才能对大量的信号进行分类和识别。我们认为情绪的变化正是大脑的特定活动，情感和大脑之间相互映射，互相依存，脑电信号正是将两者联系起来的桥梁。但对于原始的脑电信号，数量非常巨大且非常微弱，与此同时其噪音又很强。因此原始脑电数据应该进行特征的提取，即根据相应公式进行计算，将其具有代表性的特征表现出来。

对于脑电信号的特征提取方法有很多，包括时域上的[13]、频域上的[14]、时频域上的以及非线性动力学特征[15]。由于脑电信号波形的形态非常复杂，至今没有一个统一的有效分析方法，导致往往需要丰富的经验对其进行直观分析，因此我们主要采用频域、时频域特征和非线性动力学特征进行分析。此次数据中对情感作了三分类，采用单一的特征量就能获得较好的分类结果，在频域我们提取出微分熵特征和功率谱密度。

由于EEG数据具有较高的低频能量，作为香农思维是一个推广，微分熵特征(differential entropy，DE)[16]具有能够分辨出高频能量和低频能量的脑电模式的能力，我们以近似地对连续型变量的取值进行离散化来使用DE 特征。功率谱密度表明了信号或者时间序列的功率在频率上的分布，对于所有时间的连续信号必须定义功率谱密度(power spectral density，PSD)[17]。在这里的功率是为了方便而使用的抽象信号，我们用信号的平方来识别。

时频特征的分析是同时在时域和频域这俩者上对信号进行分析，更加有利于非平稳信号和时变信号的特征的表现，更加突出信号的瞬态特征。在文献[18]中，作者采用了短时傅里叶变换对脑电特征提取，并通过SVM进行分类，最高可达到$9 1 . 3 5 \%$ 的准确率。小波熵（wavelet entropy，WE）[19]是用于脑电分析中典型的时频特征，既发展了短时傅立叶变换的思想，又克服了窗口固定的缺点，在高频和低频都能自动适应，取得良好的分类效果。

非线性单元的集合产生了脑电信号，即神经细胞信号的非线性藕合。因此近年来非线性动力学特征也用在情感计算方面。非线性动力学特征能够表现出系统的内在随机性，一个典型代表就是近似熵（approximate entropy，ApEn）[20]。它可定义为相似向量由 $\mathrm { ~ m ~ }$ 维度增长到 $\mathbf { m } { + } 1$ 维时继续保持其相似性的条件概率，当 $\mathbf { m }$ 发生变化时，时间序列产生出新模式的概率越大，对应熵值也就越大。

在对脑电信号数据进行特征提取之后，还要对各个特征进行带通滤波处理，科学上公认的脑电信号常用有五种波段[21,如图2所示，分别为 $\delta , \ \theta , \ a , \ \beta ,$ $\boldsymbol { \gamma }$ 波。本文对于脑电信号的研究，主要是对微分熵、小波熵、近似熵、功率谱密度进行提取分析，然后通过带通滤波器，将这些特征滤波到delta（1\~4$\mathrm { H z }$ ）频带、theta（ $\scriptstyle ( 4 \sim 8 \mathrm { ~ H z }$ ）频带、alpha（ $8 { \sim } 1 3 \mathrm { H z }$ ）频带、beta（ $1 3 { \sim } 3 0 \mathrm { H z }$ ）频带、gamma（ $3 6 { \sim } 4 4 \mathrm { H z }$ ）频带等五个频带中去。

波   
50 0 M   
-50 0 500 1000 1500 2000 2500 3000 3500 4000 4500 波   
20   
20 0 500 1000 1500 2000 α波 t2500 3000 3500 4000 4500   
20   
-20 0 500 1000 1500 2000β波2500 3000 3500 4000 4500   
10 0   
-10 0 500 1000 1500 2000 2500 3000 3500 4000 4500 波   
20 0   
-20 0 500 1000 1500 2000 2500 3000 3500 4000 4500

# 2.2分类训练

经过前面对采集到的情感数据进行特征提取，得到了能够反映情感状态的脑电信号特征，最后还要基于一定的分类准则去构建一个情感识别的计算模型，通过这些情感识别模型，对没有经过训练的样本进行分类。对于本文中的三分类，不同的分类器往往得到不同的识别准确率，因此也说明情感的识别在一定程度上依赖分类器的优劣。

情感模型的分类训练和学习是整个实验过程中的一个重要环节，也是将脑电信号与情感识别进行连接的重要桥梁，更是在实际过程中对情感状态进行预测的重要手段。

# 1）多频带训练

对脑电数据的分类可用的方法比较多，本文首先采用支持向量机、K近邻算法、朴素贝叶斯、神经网络四种分类器对微分熵、小波熵、近似熵、功率谱密度四类特征进行分类训练学习。

支持向量机是与学习算法有关的监督学习模型，它在对样本较少、非线性信号以及高维模式的识别中有很多独特的优势[22]。SVM 的主要思想就是将要训练的向量数据，采用非线性的方法将其映射到一个高维空间，并在此高维空间中寻找一个分类面，使得原本不可分的数据集合按照种类进行最优的分类。与另外三种方法相比，即在贝叶斯定理基础上的朴素贝叶斯分类算法[23]，简单的机器学习算法之一的K最近邻类算法[24]和多层感知器神经网络模型[25]相比，SVM在处理高维问题中具有较大优势，可以避免神经网络结构选择和局部最小点的问题。

2)多通道训练

另一方面，采用62导的电极帽，因为其数据量大，测量脑电信号、研究脑电信号对情感识别都不是很方便，因此我们在国际通用标准电极10-20系统基础上，采用四种不同的电极放置方法去减少通道数，如图3所示，（a）四通道：FT7、FT8、T7 和 T8；（b）六通道：FT7、FT8、T7、T8、TP7和 TP8；（c）九通道：FP1、PFZ、FP2、FT7、FT8、T7、T8、TP7和TP8：（d）十二通道：FT7、FT8、T7、T8、C5、C6、TP7、TP8、CP5、CP6、P7和P8。

采用少量通道以期望过滤掉那些对情感识别影响不是很大的通道，进而得到较高的准确率。根据一些统计量来选择一些通道，在本文中，利用深度信念网络（DBN）可以在进行无监督和有监督学习时进行特征提取和特征选择的结合，根据DBN模型在非监督学习时的系数权重,按数值从高到低选取四种电极放置方式，得出通道选择的方案[26]。

0000 @0   
@oooao ①oo000@O   
ceec. coeece.   
⊙⊙② @@@   
o8805cc cooo0cco   
ooD2oo o0000o   
80000 eoe @@@ 0@@ (a) (b) A   
C0O C0008o0   
6@6e6330 e.   
③⊙①@@③ ⑥⑥④·   
@00000000 C0000000   
@00000e 00000 @@@ 000@ (c) (d)

3）参数寻优训练

支持向量机在解决非线性高纬模式识别方面有其独特优势，因此广泛的使用在情感识别当中。但是，支持向量机的核函数和参数对训练效果影响比较大，本文是多次尝试按经验取值，为了进一步提高识别准确率，在多通道电极放置方式的基础上，采用遗传算法对其参数寻优[27]。遗传算法（GA）是一种灵感源于达尔文自然进化论的启发式搜索算法，从种群中最适合环境的个体开始，后代继承父母的特性，并将这些特性添加到下一代中。迭代进行该自然选择过程，最后实现寻优[28]。GA 将惩罚因子c和核函数参数 $\mathbf { g }$ 进行二进制编码，对随机产生的初始群体利用适应度函数进行淘汰，保持种群的总量稳定，之后采用交叉和变异产生下一代，不断寻优直到满足终止条件，输出c和 $\mathbf { g }$ 的最优解[29]。

# 3 训练结果及分析

# 3.1多频带结果

对于原始的脑电信号数据，本文采用支持向量机、K近邻算法、朴素贝叶斯、神经网络四种分类器对其微分熵、小波熵、近似熵、功率谱密度进行分类训练，得到准确率，其中SVM采用线性核函数，KNN算法 $\scriptstyle \mathrm { K = } 2 0$ 。对WE 特征采用SVM、KNN、NB、MLP四种分类器进行训练测试的准确率和方差如表1所示。

表1WE特征的多种平均分类准确率及标准差示意图  

<html><body><table><tr><td>分类器</td><td>SVM</td><td>KNN</td><td>NB</td><td>MLP</td></tr><tr><td>准确率(方差)</td><td>55.13(4.05)</td><td>48.72(2.39)</td><td>47.91(3.05)</td><td>49.49(3.55)</td></tr></table></body></html>

表2中将ApEn、PSD、DE三种特征通过带通滤波器分为Delta、Theta、Alpha、Beta、Gamma五个频带，对未分频的EEG数据和每个频带分别采用SVM、KNN、NB、MLP四种分类器进行训练，得出准确率及方差。

表2不同频带多种平均分类准确率及标准差示意图MEAN(SD)  

<html><body><table><tr><td>特征</td><td>分类器</td><td>Delta</td><td>Theta</td><td>Alpha</td><td>Beta</td><td>Gamma</td><td>Total</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td></td><td>SVM</td><td>43.34(3.47)</td><td>36.08(2.29)</td><td>43.47(6.28)</td><td>42.4(3.43)</td><td>58.66(5.43)</td><td>69.57(8.33)</td></tr><tr><td rowspan="4">ApEn</td><td>KNN</td><td>34. 05(3.31)</td><td>40.51(1.82)</td><td>39.31(4.06)</td><td>39.17(2.61)</td><td>54.6(6.84)</td><td>66.64(9.84)</td></tr><tr><td>NB</td><td>36.84(3.09)</td><td>39.78(2.96)</td><td>41.93(5.47)</td><td>44.83(2.57)</td><td>52.3(3.33)</td><td>56.36(7.65)</td></tr><tr><td>MLP</td><td>33.77(2.63)</td><td>36.8(1.62)</td><td>37.36(5.04)</td><td>41.01(2.12)</td><td>55.06(6.6)</td><td>66.73(9.02)</td></tr><tr><td>SVM</td><td>39.52(4.21)</td><td>39.99(7.49)</td><td>45.43(6.01)</td><td>56.81(12.18)</td><td>68.82(10.73)</td><td>80.18(10.94)</td></tr><tr><td rowspan="4">PSD</td><td>KNN</td><td>66.32(4.94)</td><td>58.55(5.12)</td><td>62.63(9.12)</td><td>76.52(4.35)</td><td>79.03(4.0)</td><td>85.46(3.21)</td></tr><tr><td>NB</td><td>38.14(4.83)</td><td>41.39(4.21)</td><td>43.18(5.56)</td><td>46.82(7.7)</td><td>49.08(8.98)</td><td>51.73(7.64)</td></tr><tr><td>MLP</td><td>47.46(10.92)</td><td>54.61(6.99)</td><td>56.88(10.59)</td><td>67.07(8.62)</td><td>73.03(6.17)</td><td>75.10(11.92)</td></tr><tr><td>SVM</td><td>63.71(3.42)</td><td>61.70(7.38)</td><td>71.35(8.97)</td><td>88.19(5.37)</td><td>93.35(3.74)</td><td>98.45(0.82)</td></tr><tr><td rowspan="3">DE</td><td>KNN</td><td>64.03(3.81)</td><td>69.07(7.19)</td><td>77.79(9.98)</td><td>86.86(5.31)</td><td>91.76(2.0)</td><td>93.99(2.6)</td></tr><tr><td>NB</td><td>49.49(3.66)</td><td>46.54(3.11)</td><td>50.73(10.01)</td><td>63.13(10.9)</td><td>67.47(9.36)</td><td>71.22(7.86)</td></tr><tr><td>MLP</td><td>71. 96(5.74)</td><td>77.52(8.61)</td><td>82.7(8.71)</td><td>95.4(3.03)</td><td>98.10(0.78)</td><td>98.1(0.95)</td></tr></table></body></html>

对于表1和2来说，采用了4种分类器对脑电信号进行情感识别的分类训练，其结果从总体上来看都是具有参考价值的，具体到每一个分类器上，SVM的分类效果是明显好于其它几种的。从特征上来说，DE 特征的分类结果总体上要更好一些，这也说明DE特征和人脑的情感的相关性更大。

对于小波熵，对其分别采用4种分类器进行训练学习，得到的准确率与表2中三种特征所有EEG频带能量的总合所得出的准确率及方差相比，采用SVM对DE频带进行滤波的准确率以及方差结果具有较大优势，如图4所示。

![](images/4a4c3f43c55eec560485306f4146b4dff500d962ee8ed2d077199b88a07269f4.jpg)  
图4频带总能量的准确率

# 3.2多通道结果

根据表1、2所测得的各个特征的分类结果，可以明显看出采用SVM进行DE特征训练的分类结果较好。因此在多通道的分类训练中，我们根据上文中图3所示的a、b、c、d四种电极放置方式，对DE特征采用SVM进行多通道的分类训练学习，如表3所示。

表3不同电极放置方式下平均分类准确率及标准差示意图  

<html><body><table><tr><td colspan="6">MEAN(SD)</td></tr><tr><td>Delta</td><td>Theta</td><td>Alpha</td><td>Beta</td><td>Gamma</td><td>Total</td></tr><tr><td>43.45 a</td><td>46.59</td><td>53.94</td><td>69.46</td><td>73.12</td><td>81.13</td></tr><tr><td>(3.38)</td><td>(5.13)</td><td>(13.49)</td><td>(10.23)</td><td>(9.89)</td><td>(7.03)</td></tr><tr><td>44.44 b</td><td>46.97</td><td>56.12</td><td>72.5</td><td>78.33</td><td>85.5</td></tr><tr><td>(3.41)</td><td>(5.51)</td><td>(12.81)</td><td>(10.35)</td><td>(7.81)</td><td>(9.22)</td></tr><tr><td>47.86 C</td><td>49.28</td><td>58.34</td><td>75.39</td><td>81.82</td><td>91.44</td></tr><tr><td>(4.74)</td><td>(6.28)</td><td>(12.16)</td><td>(8.49)</td><td>(6.22)</td><td>(7.79)</td></tr><tr><td>49.62 d</td><td>48.7</td><td>59.09</td><td>64.46</td><td>81.1</td><td>91.99</td></tr><tr><td>(2.78)</td><td>(6.39)</td><td>(12.74)</td><td>(8.83)</td><td>(8.19)</td><td>(7.52)</td></tr></table></body></html>

从表3来看，对DE特征在较少的通道下训练，依然能够得到较高的分类效果，尤其是在十二通道的情况下，采用SVM训练的整体准确率已经达到 $9 1 . 9 9 \%$ ，表明减少电极不仅可以节省计算成本,还可以提高情感识别模型的性能和鲁棒性。

# 3.3参数寻优结果

根据表2所得结果，对十二个通道的电极放置方式下产生的脑电信号形成的训练集，采用gaSVMcgForClass 对参数c、g进行多次寻优，得到c、g的平均值分别为1和2。寻优后的参数用于采用RBF核的SVM模型的训练，最终得到准确率[30],如图5所示。

![](images/c9f1d1bb612863353ac123b268ade100276e5a37fd38bcb1f9f24976c13196bd.jpg)  
图5在12通道电极放置方式下的平均分类准确率

在12通道的电极放置下，采用遗传算法对SVM的参数寻优之后每个频带的准确率都有相应提高，从图5来看，总体准确率提高了大约 $5 . 6 \%$ 。

通过上面的三张表和图，我们可以看出对于所有的受试者，总体的趋势上来看频带越高，准确率也随之增大，Gamma 频带的分类效果相对于其他频带来说是最好的。总体的分类结果准确率在趋势比每一分频带要好。频带越高，其能量也越大，所包含的信息也就越多，因此对于正面的情感， $\beta$ 和 $\boldsymbol { \gamma }$ 频段能量较大，而中性和负性情绪具有较低的 $\beta$ 和 $\boldsymbol { \gamma }$ 频段能量。

# 4 结束语

目前情感识别是通过计算机去识别情感的各类状态所表现出来的特征。本文基于多频道和多通道的脑电情感识别研究，将脑电信号数据进行特征的提取，采用微分熵、小波熵、近似熵和功率谱密度来评价与情感状态的相关程度。对提取出的 4类特征采用支持向量机、K近邻算法、朴素贝叶斯、神经网络进行分类训练学习。在采用SVM对DE特征训练能够得到较高准确率的基础上，减少电极的放置方式，对SVM进行参数寻优，得到分类训练学习的准确率。

实验结果表明，每一位受试者整体的准确率要高于其每一频带的准确率，随着频带频率的提高，相应的识别准确率也随之提高；DE 频带的准确率要比其余三个更好；较少的通道也能获得较高的识别率。这一结果也部分反映了高频带在情感活动中比低频带发挥更重要的作用。

# 参考文献：

[1]Li Wu,Zhang Yanhui,Fu Yingzi. Speech emotion recognition in E-learning system based on affective computing [C]// Proc of the 3rd Conference on Natural Computation. 20o7: 809-813.   
[2] Anderson A K, Sobel N. Dissociating intensity from valence as sensory inputs to emotion [J]. Neuron,2003,39 (4): 581-583.   
[3]Ang J,Dhillon R,Krupski A,et al.Prosody-based automatic detection of annoyance and frustration in human-computer dialog [C]/ Proc of the 8th International Conference on Spoken Language Processing. 2002: 2037-2040.   
[4]Bos D O.EEG-based emotion recognition [EB/OL]. 2008.https:/pdfs. semanticscholar. org/5097/b37a30b8d7a8d2bb03b307be5bf5deab73c4. pdf.   
[5]Hosseini S A,Naghibi-Sistani M B. Emotion recognition method using entropyanalysisof EEGsignals[J].International Journal of Image, Graphics and Signal Processing,2011,3(5):30-36.   
[6]Yuen CT,Woo S S,Tan C S,et al.Classification of human emotions from EEG signals using statistical features and neural network [J]. International Journalof IntegratedEngineering,2009,1(3):71-79.   
[7]Madsen J, Jensen B S,Larsen J. Modeling temporal structure in music for emotion prediction using pairwise comparisons [C]// Proc of the 15th International Society for Music Information Retrieval Conference.2014: 319-324.   
[8]Li Mi,Lu Baoliang. Emotion classification based on gamma-band EEG [C]// Proc of IEEE International Conference Engineering in Medicine and Biology Society. 2009: 1223-1226.   
[9]Lin Yuanping,Wang Chihong,Tzy Ping Jung,et al. EEG-based emotion recognition in music listening [J]. IEEE Trans on Biomedical Engineering, 2010,57 (7): 1798-1806.   
[10] Mallat S G.A theory for multiresolution signal decomposition: the wavelet representation [J].IEEE Journals & Magazines,1989,11(7): 674-693.   
[11] Zheng Weilong，Zhu Jiayi，Peng Yong，et al.EEG-based emotion classification using deep belief networks [C]/ Proc of IEEE International Conference on Multimedia and Expo.2O14:1-6.   
[12] Zheng Weilong,Guo Haotian,Lu Baoliang.Revealing critical channels and frequency bands for emotion recognition from EEG with deep belief network [Cl// Proc of International IEEE/EMBS Conference on Neural

Engineering.2015:154-157.

[13] George Zouridakis,Udit Patidar,Nikhil S.Padhye,et al. Spectral power of brain activity associated with emotion —a pilot MEG study [C]// Proc of the 17th International Conference on Biomagnetism Advancesin Biomagnetism. Berlin: Springer, 2010: 354-357.

[14] Zhang Qing,Lee Minho.A hierarchical positive and negative emotion understanding system based on integrated analysis of visual and brain signals [J]. Neurocomputing,2010,73 (16-18): 3264-3272.   
[15] Aftanas L I,Lotova N V,Koshkarov V I,et al. Non-linear analysis of emotion EEG:calculation of Kolmogorov entropy and the principal Lyapunov exponent [J]. Neuroscience Letters,1997,226(1): 13.   
[16] Shi Lichen, Jiao Yingying,Lu Baoliang.Differential entropy feature for EEG-based vigilance estimation [Cl//Proc of the 35th Annual International Conference of the IEEE Engineering in Medicine and Biology Society. 2013: 6627-6630.   
[17] DanielaS,Maren $\mathbf { G }$ ThomasF,et al.Musicand emotion: electrophysiological correlates of the processing of pleasant and unpleasant music [J].Psychophysiology,2007,44(2): 293-304.   
[18]吴乃玉．基于 EEG 信号的情绪分类研究[D].北京：中央民族大学， 2013.(Wu Naiyu. EEG-based emotion classification research [D]. Beijing: Minzu University of China, 2013.）   
[19] Murugappan M, Mohamed R,Ramachandran N,et al. EEG feature extraction for classifying emotions using FCM and FKM[C]// Proc of Wseas International Conference on Applied Computer and Applied Computational Science.World Scientific and Engineering Academy and Society,2008: 299-304.   
[20] Steve P. Approximate entropy (ApEn) as a complexity measure [J]. Chaos An Interdisciplinary Journal of Nonlinear Science,1995,5(1): 110.   
[21] Saeid S,Chambers JA.EEG signal processing [M]// The Fernow Watershed Acidification Study. Netherlands: Springer, 2007: 207-236.   
[22] Vapnik VN.Statistical learning theory[J].Encyclopedia of the Sciences of Learning,2008,41 (4): 3185-3185.   
[23]邓维斌，王国胤，王燕．基于Rough set的加权朴素贝叶斯分类算法[J]. 计算机科学,2007,34 (2): 204-206.(Deng Weibin,Wang Guoyin,Wang Yan. Weighted naive Bayes classification algorithm based on rough set[J]. Computer Science,2007,34 (2): 204-206.）   
[24]江涛，陈小莉，张玉芳，等．基于聚类算法的 KNN 文本分类算法研究 [J].计算机工程与应用,2009,45(7):153-155.(Jiang Tao,Chen Xiaoli, Zhang Yufang，et al. Improved KNN using clustering algorithm [J]. Computer Engineering and Applications,2009,45(7): 153-155. ）   
[25]胡金滨，唐旭清．人工神经网络的 BP 算法及其应用[J]．信息技术， 2004 (4):1-4. (Hu Jinbin,Tang Xuqing. BP algorithm and its application in artificial neural network[J].Information Technology,2004,28 (4):1-4.)   
[26] Zheng Weilong,Lu Baoliang.Investigating critical frequency bands and channels for EEG-based emotion recognition with deep neural networks [J]. IEEE Trans on Autonomous Mental Development,2015,7(3): 162-175.

[27] Zheng Chunhong,Jiao Licheng.Automatic parameters selection for SVM based on GA[C]//Proc of the 5th World Congress Intelligent Control and Automation,2004:1876-1879.

[28] Liu Hao,Qiu Jianxin. Improved adaptive genetic algorithm in optimal layout of leather rectangular parts [J].Advances in Natural Science,2015, 8(3):20-26.

[29]Lalit Mohan Saini,Sahil Kumar Aggarwal,Kumar Atul.Parameter optimisation using genetic algorithm for support vector machine-based price-forecasting model in National electricity market [J]. IET Generation

Transmission& Distribution,2009;4(1):36-49.

[30]任浩，叶亮，李月，等．基于多级SVM分类的语音情感识别算法[J]. 计算机应用研究,2017,34(6):1-4.(Ren Hao,Ye Liang,Li Yue,et al.A speech emotion recognition algorithm based on multi-layer SVM classification [J].Application Research of Computers，2017,34 (6): 36-49. )