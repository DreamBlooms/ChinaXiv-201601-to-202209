# WPLoss:面向类别不平衡数据的加权成对损失

姚佳奇，徐正国，燕继坤，王科人(盲信号处理重点实验室，成都 610041)

摘要：类别不平衡数据是指不同类别的样本数目差异很大，AUC(Area Under the ROC Curve）是衡量不平衡数据分类器性能的一个重要指标，由于AUC不可微，研究者提出了众多替代成对损失函数优化AUC。成对损失的样本对数目为正负样本数目的乘积，大量成对损失较小的正负样本对影响了分类器的性能。针对这一问题，提出了一种加权的成对损失函数 WPLoSs，通过赋予成对损失较大的正负样本对更高的损失权重，减少大量成对损失较小的正负样本对的影响，进而提升分类器的性能。在20newsgroup和Reuters-21578数据集上的实验结果验证了WPLoss的有效性，表明WPLOSS 能够提升面向不平衡数据的分类器的性能。

关键词：不平衡分类；成对损失；AUC优化 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2020.02.0041

Wploss:weighted pairwise loss for class-imbalanced datasets

Yao Jiaqi, Xu Zhengguo, Yan Jikun, Wang Keren (National Key Laboratory ofScience&Technology on Blind Signal Processing,Chengdu 610041,China)

Abstract: Class-Imbalanceddata refers tothe large diffrence inthenumberofsamples indiferentclasss.AUC(areaunder the ROC curve)is an important metric to measure theperformanceofclasifiers on the imbalanced datasets.SinceAUC is not diferentiable,，researchers have proposed many surrogate pairwise loss functions to optimize AUC.The numberof pairwise losses is the product ofthe number of positive and negative samples.Many positive and negative pairs with smal pair loss affect the performance ofclasifiers.To solve this problem,this paper proposesa weighted pairwise los function WPLoss. By assgning higherloss weights to the positive and negative samples with higher pairwiselosses,WPLossreduces the impact ofpositive and negative sample pairs with smaller pairwise losses.The experimentalresults on 20 newsgroup and Reuters-21578datasetsverify thevalidityof WPLoss,indicating that WPLosscan improve theperformanceof theclasifier for class-imbalanced data.

Key words:class-imbalanced classification; pairwise loss;AUC optimization

# 0 引言

类别不平衡数据是指不同类别的样本数目差异较大，如图1所示，由 $( x _ { 1 } , x _ { 2 } )$ 构成二维样本集，其中红色表示少数样本的类别，灰色表示多数样本的类别。类别样本数目的不平衡导致以优化0-1替代损失函数为目标的分类器失灵，因为分类器倾向于将所有样本预测为样本数目较多的类别[1]。而在实际应用中，通常样本数目较少的类别是用户感兴趣的类别，如在信用卡欺诈检测应用中，需要从大量账号中挑选出哪些账号可能存在欺诈行为，而有欺诈行为的账号属于少数，但是对银行却至关重要[2]；再如从海量文本数据中挑选出用户感兴趣或者认为重要的文本[3]；以及目标检测任务中前景和背景的分类[4]等。

类别不平衡分类的处理方法大体上可以分为两大类，分别是数据层面的处理方法和算法层面的处理方法，如图2所示。

数据层面的处理方法通过样本的重采样处理类别不平衡的问题，包括降采样算法、升采样算法和类别重组方法。降采样算法是指通过减少多数类别的样本实现类别平衡的算法，最简单的处理方法是随机降采样多数类别样本。降采样算法减少了训练样本的数目，从而提升了算法训练速度，但是损失了未未被采样到的多数类别样本的信息。针对降采样算法导致的样本信息损失的问题，Liu等人提出了随机降采样多个多数类别的样本集，训练多个分类器然后集成[5]，另一些研究者研究了基于多数类别样本聚类的降采样算法 $ { \left[ 6 , 7 \right] } _ { \circ }$ 与降采样算法相反，升采样算法则通过增加少数类别的样本实现类别平衡的算法，最简单的处理方法是随机升采样少数类别的样本。随机升采样少数类别样本由于噪声样本的存在，导致分类器容易产生过拟合。Chawla等人提出了通过邻近样本合成产生新的少数类别样本的SMOTE算法[8]。随着生成对抗网络(generativeadversarialnetworks,GAN)的提出，研究者提出了一系列基于GAN 生成少数类别样本的方法[9,10]。ShicaiYang提出了一种在场景分类任务中的类别重组方法(labelshuffling)，首先按照最多数类别的样本数生成一个随机列表，其他类别则通过取其对应样本数的余数选取样本[]。

![](images/8cb2032b0987df45ac48a593a971487cb9193a43cd6812929b33670b77127ba2.jpg)  
图1不平衡数据分布示意图  
Fig.1Unbalanced data distribution diagram

![](images/702991b43612a5d59c2bb896b09bdf7b0921b3f97484ff093a5c72ee8892c1c5.jpg)  
图2类别不平衡分类的处理方法分类

Fig.2Taxonomy of methods for class-imbalancedclassification算法层面处理方法则通过改变分类算法处理类别不平衡的问题，主要包括代价敏感类算法和AUC优化类算法。代价敏感类算法通过赋予不同类别不同的损失权重，提升分类器在处理不平衡数据的分类性能[12]，损失权重通常由不同类别的样本数目或者混淆矩阵确定。Lin等人在代价敏感的基础上提出了FocalLoss损失函数，通过增加难以分类正确的样本损失权重进一步提升了分类器的性能[13]。AUC(areaundercurve)是衡量不平衡分类算法的一个关键指标，由于AUC不可直接优化，研究者提出了众多替代成对损失(surrogate pairwise loss)函数，包括指数损失(exponentialloss)[14][15]，合页损失(hinge loss)[16][17]和最小二乘损失(leastsquare loss)[18]等。

在计算AUC替代成对损失函数时，需要计算正负样本数乘积个成对损失，导致了大量成对损失较小的样本对占据了加大比重，从而主导了分类器梯度下降的方向。本文提出了一种加权成对损失WPLoss(weighted pairwise loss)，通过赋予成对损失较大的样本对更大的损失权重，使分类器着重优化难以区分的正负样本对，进而提升分类器的性能。在公开数据集 20newsgroup 和Reuters-21578 数据集上的实验结果，验证了本文提出方法的有效性，表明WPLoss提升了原始的AUC替代成对损失函数的分类性能，而且与其他不平衡分类算法相比，也具有较优的性能。

# 1 WPLoss:加权成对损失

本文提出的加权成对损失WPLoss是一种加权的AUC替代成对损失，旨在增加成对损失较大的正负样本对的损失权重，使得分类器着重优化难以区分的正负样本对。本节首先介绍了AUC优化方法，然后描述和分析了本文提出的WPLoss。

# 1.1 AUC 优化

AUC 是ROC(receiver operating characteristic)曲线下的面积。ROC 曲线的横坐标是假阳率(false positive rate,FPR)，纵坐标是真阳率(true positive rate,TPR)，如图3所示。

![](images/626ebb17c58ccf18b87b4d4017aaf8009894452907704f6921549d4122681ea8.jpg)  
图3ROC曲线示意图Fig.3Roc curve

令 $X = \{ x _ { 1 } , x _ { 2 } , \cdots , x _ { m } , x _ { m + 1 } , \cdots , x _ { m + n } \}$ ，其中前 $\mid m \mid$ 个样本为正类样本，后 $n$ 个样本为负样本， $f$ 表示分类函数， $\boldsymbol { t p }$ 为为 $f$ 正确预测为正类的样本个数， $f p$ 为 $f$ 错误预测为正类的样本个数，则 $F P R = \frac { f p } { n } , T P R = \frac { t p } { m }$ 。AUC 的形式定义如下所示。

$$
A U C \left( f \right) = \frac { 1 } { m n } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } I ( f \left( x _ { i } \right) > f \left( x _ { m + j } \right) )
$$

其中 $I$ 为示性函数，当括号内的表达式成立时值为1，否则为 $0 _ { \circ }$ AUC的取值范围在[0.5.]之间，值越大表明分类器的性能越好。从AUC的定义可以看出，分类器的AUC值是非凸和离散的，从而无法直接优化。

在实际应用中，研究者采用替代成对损失函数实现AUC的优化：

$$
R \left( f \right) = \frac { 1 } { m n } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \varphi \left( f \left( x _ { i } \right) - f \left( x _ { m + j } \right) \right)
$$

其中 $\varphi$ 凸函数，如：

指数损失 $\begin{array} { r l } & { \varphi ( t ) = e ^ { - t } } \\ & { \varphi ( t ) = \ln \left( 1 + e ^ { - t } \right) } \\ & { \varphi ( t ) = \operatorname* { m a x } \left( 0 , \ P - t \right) } \\ & { \varphi ( t ) = \operatorname* { m a x } \left( 0 , \ P - t \right) ^ { 2 } } \end{array}$   
逻辑斯蒂损失   
合页损失   
最小二乘合页损失

Gao 等人研究了替代成对损失与AUC优化的一致性问题，指出指数损失、逻辑斯蒂损失和最小二乘合页损失具有与 AUC优化的一致性，而合页损失不具有[19]。

# 1.2加权成对损失

从AUC的替代成对损失的定义式(2)可以看出， $R \left( f \right)$ 是正负样本数乘积m个样本对距离的平均值。然而，不同的样本对有不同的距离，距离较小的样本对为较难区分的正负样本对，如图4中的样本对1，而距离较大的样本对为较易区分的正负样本对，如图4中的样本对2。式(2)中定义的AUC的替代成对损失采用了算术平均值，将导致大量的较容易区分的样本对占据损失的主要部分，从而主导了梯度方向。因而，本文提出了一种加权成对损失WPLoss，使分类器着重优化难以区分的样本对。

![](images/6cf2b4e683863c91ddde910bb79b20aaa5b7f11f69ba66ade949aacaea918f91.jpg)  
图4样本对距离示意图  
Fig.4Pairwise distance diagram

令 $p _ { i j } = \varphi ( f ( x _ { i } ) - f \left( x _ { m + j } \right)$ ，则WPLoss 的形式定义如下所示。

$$
\alpha _ { i j } = \frac { \exp \left( p _ { i j } \right) } { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \exp \left( p _ { i j } \right) }
$$

$$
W P L o s s \left( f \right) = \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \alpha _ { i j } \cdot p _ { i j }
$$

WPLoss采用softmax函数(式(3))加权不同样本对的成对损失，并实现归一化。WPLoss给予较小距离的样本对较大的权重，较大距离的样本对较小的权重，使得优化算法着重优化难以区分的正负样本对，进而提升分类器的性能。同时，WPLoss 随着训练的进程，依据样本对的成对损失大小动态调整损失权重。

# 2 实验

针对不平衡数据的分类问题，本文提出了加权成对损失

WPLoss。本节通过两个公开的数据集上的实验，验证了WPLoss的有效性

# 2.1 数据集

# a) 20newsgroup 数据集

20newsgroup(http://qwone.com/jason/20Newsgroups/）包括大约20.000 篇文档，大约被平均分成20组，即对应着 20个类别，本文指定一个类别为正类，其余类别为负类，构造了20个二分类的数据集。

# b)Reuters-21578 数据集

Reuters-21578是一个公开的新闻数据集[20]，本文选择了样本数最多的十个类别，分别是 acq、crude、earn、grain、interest、money-fx、 money-supply、ship、sugar 和 trade，然后以某一类为正类，其余类别为负类，构造了10个二分类的数据集。

# 2.2基础模型

本文采用卷积神经网络(convolutionalneuralnetwork,CNN)作为文本特征提取器[22]，整体架构如图5所示，首先将文本使用词向量表示，然后依次经过卷积层、池化层和全连接层获取最终的特征向量。

![](images/f93661b27b5681d9e36d819e021e02c492f78168e437cedc6dca91270858f33a.jpg)  
图5卷积神经网络架构  
Fig.5Architecture of convolutional neural network

卷积网络的参数配置如表1所示。此外，本文采用了在谷歌新闻数据集上训练得到的词向量初始化卷积网络中的词向量矩阵[22]，并采用Adam优化算法[23]。

Tab.1Settings of convolutional neural network   

<html><body><table><tr><td>参数名称</td><td>参数设置</td></tr><tr><td>卷积核尺寸</td><td>3×300,4×300,5×300</td></tr><tr><td>卷积核个数</td><td>256</td></tr><tr><td>激励函数</td><td>Relu</td></tr><tr><td>池化函数</td><td>最大池化</td></tr><tr><td>随机失活率</td><td>0.5</td></tr></table></body></html>

# 2.3对比方法

本文对比了原始CNN，数据层面处理方法中的类别重组

方法，算法层面处理方法中的代价敏感类方法，如偏置CNN和Focal-Loss方法，以及AUC优化方法。下面分别介绍每种方法的具体设定。

# a）原始CNN

原始CNN方法忽略类别不平衡的问题，在使用CNN 提取文本特征向量后，经过激活函数为softmax的全连接层，获取不同类别的概率，最后使用与真实标签交叉熵(Cross-Entropy)计算损失。令 $y _ { i } \in \{ 0 , 1 \}$ 第 $i$ 个样本 $x _ { i }$ 的真实标签， $p _ { i }$ 表示分类器预测为正类的概率，则该样本的交叉熵损失为

$$
C E ( f ( x _ { i } ) ) = - y _ { i } \log \left( p _ { i } \right) - ( 1 - y _ { i } ) \log \left( 1 - p _ { i } \right)
$$

# b）类别重组

类别重组在原始CNN的基础上，重采样了正类样本。首先按照负类的样本数生成一个随机列表，正类则使用该随机列表通过取正类样本数的余数采样。

# c）偏置CNN

偏置(Biased)CNN在原始CNN的基础上，令正类样本的损失权重为1，负类样本的损失权重为正负类样本数目比 $\alpha$ ，如下所示。

$$
B i a s e d C E \left( f \left( x _ { i } \right) \right) = - y _ { i } \log \left( p _ { i } \right) - \alpha \left( 1 - y _ { i } \right) \log \left( 1 - p _ { i } \right)
$$

d) Focal-Loss

Focal-Loss在偏置CNN的基础上，改造了交叉熵损失，如下所示。

$$
F L ( f ( x _ { i } ) ) =
$$

$$
- y _ { i } \left( 1 - p _ { i } \right) ^ { \gamma } \log \left( p _ { i } \right) - \alpha \left( 1 - y _ { i } \right) p _ { i } ^ { , \gamma } \log \left( 1 - p _ { i } \right)
$$

从Focal-Loss的定义可以看出，Focal-Loss拓展了交叉熵损失的定义，当 $\gamma = 0$ 时即为交叉熵损失，本文在实验时，取 $\gamma = 2$ 。

e) AUCloss

AUCloss为AUC替代成对损失的方法，在实验中，本文采用了指数损失，即令式(2)中的 $\varphi$ 为 $\varphi ( t ) = e ^ { - t }$ 。

# f) WPLoss

WPLoss即本文提出的方法，为了验证WPLoss的有效性，采用与AUCloss的设定一样采用指数损失。

# 2.4实验结果及分析

令TP表示正确预测为正类的样本个数，FP表示错误预测为正类的样本个数，FN为错误预测为负类的样本个数，则精确率 $P = { \frac { T P } { T P + F P } }$ TP+FP，召回率R= $R = { \frac { T P } { T P + F N } }$ TP+FN，F1= PPR。本文采用了F1指标评估了不同算法的性能，20newsgroup 实验结果如表2所示，Reuters-21578实验结果如表3所示，表中的不平衡率为负类样本数与正类样本数的比值，性能最优的结果使用粗体表示。

表1卷积神经网络的配置  
表220newsgroup 实验结果  
Tab.2Results on 20newsgroup   

<html><body><table><tr><td>正类类别</td><td>不平衡率</td><td>原始CNN</td><td>类别重组</td><td>偏置CNN</td><td>Focal-Loss</td><td>AUCloss</td><td>WPLoss</td></tr><tr><td>alt.atheism</td><td>20.0481</td><td>0.8362</td><td>0.8580</td><td>0.8622</td><td>0.8625</td><td>0.8535</td><td>0.8638</td></tr><tr><td>comp.graphics</td><td>19.2269</td><td>0.8633</td><td>0.9142</td><td>0.9233</td><td>0.9339</td><td>0.9329</td><td>0.9336</td></tr><tr><td>comp.os.ms-windows.misc</td><td>18.5216</td><td>0.8979</td><td>0.9167</td><td>0.9279</td><td>0.9414</td><td>0.9414</td><td>0.9353</td></tr><tr><td>comp.sys.ibm.pc.hardware</td><td>19.6445</td><td>0.9169</td><td>0.9243</td><td>0.9519</td><td>0.9553</td><td>0.9553</td><td>0.9569</td></tr><tr><td>comp.sys.mac.hardware</td><td>19.5838</td><td>0.9210</td><td>0.9416</td><td>0.9585</td><td>0.9576</td><td>0.9496</td><td>0.9493</td></tr><tr><td>comp.windows.x</td><td>18.7698</td><td>0.9050</td><td>0.9416</td><td>0.9441</td><td>0.9469</td><td>0.9449</td><td>0.9468</td></tr><tr><td>misc.forsale</td><td>18.7141</td><td>0.8032</td><td>0.8784</td><td>0.9322</td><td>0.9072</td><td>0.9282</td><td>0.9262</td></tr><tr><td>rec.autos</td><td>18.8539</td><td>0.9489</td><td>0.9583</td><td>0.9744</td><td>0.9611</td><td>0.9641</td><td>0.9556</td></tr><tr><td>rec.motorcycles</td><td>18.5216</td><td>0.9746</td><td>0.9893</td><td>0.9893</td><td>0.9889</td><td>0.9839</td><td>0.9875</td></tr><tr><td>rec.sport.baseball</td><td>19.0530</td><td>0.9866</td><td>0.9983</td><td>0.9983</td><td>0.9981</td><td>0.9983</td><td>1.0000</td></tr><tr><td>rec.sport.hockey</td><td>18.8821</td><td>0.9949</td><td>0.9949</td><td>0.9983</td><td>0.9923</td><td>0.9933</td><td>0.9949</td></tr><tr><td>sci.crypt</td><td>18.7698</td><td>0.9554</td><td>0.9628</td><td>0.9573</td><td>0.9549</td><td>0.9429</td><td>0.9666</td></tr><tr><td>sci.electronics</td><td>18.3864</td><td>0.9396</td><td>0.9615</td><td>0.9597</td><td>0.9663</td><td>0.9613</td><td>0.9632</td></tr></table></body></html>

续表2   
表3Reuters-21578 实验结果  

<html><body><table><tr><td>正类类别</td><td>不平衡率</td><td>原始CNN</td><td>类别重组</td><td>偏置CNN</td><td>Focal-Loss</td><td>AUCloss</td><td>WPLoss</td></tr><tr><td>sci.med</td><td>18.9672</td><td>0.9672</td><td>0.9744</td><td>0.9694</td><td>0.9739</td><td>0.9779</td><td>0.9698</td></tr><tr><td>sci.space</td><td>19.4038</td><td>0.9572</td><td>0.9558</td><td>0.9760</td><td>0.9531</td><td>0.9741</td><td>0.9662</td></tr><tr><td>soc.religion.christian</td><td>18.5216</td><td>0.9982</td><td>0.9982</td><td>0.9982</td><td>0.9982</td><td>0.9982</td><td>1.0000</td></tr><tr><td> talk.politics.guns</td><td>18.6036</td><td>0.8905</td><td>0.8939</td><td>0.8862</td><td>0.8895</td><td>0.8885</td><td>0.8923</td></tr><tr><td>talk.politics.mideast</td><td>18.8539</td><td>0.9149</td><td>0.9287</td><td>0.9276</td><td>0.9293</td><td>0.9283</td><td>0.9267</td></tr><tr><td>talk.politics.misc</td><td>19.9223</td><td>0.6512</td><td>0.7375</td><td>0.7344</td><td>0.7540</td><td>0.7540</td><td>0.7688</td></tr><tr><td>talk.religion.misc</td><td>18.9672</td><td>0.6515</td><td>0.6877</td><td>0.7186</td><td>0.7357</td><td>0.7167</td><td>0.7466</td></tr><tr><td>平均值</td><td></td><td>0.8987</td><td>0.9208</td><td>0.9294</td><td>0.9300</td><td>0.9294</td><td>0.9325</td></tr></table></body></html>

Tab.3Results on Reuters-21578   

<html><body><table><tr><td>正类类别</td><td>不平衡率</td><td>原始CNN</td><td>类别重组</td><td>偏置CNN</td><td>Focal-loss</td><td>AUCloss</td><td>WPLosS</td></tr><tr><td>acq</td><td>3.0547</td><td>0.9711</td><td>0.9792</td><td>0.9730</td><td>0.9720</td><td>0.9698</td><td>0.9854</td></tr><tr><td>crude</td><td>18.1355</td><td>0.8889</td><td>0.8818</td><td>0.8876</td><td>0.8708</td><td>0.9034</td><td>0.8994</td></tr><tr><td>earn</td><td>1.2436</td><td>0.9885</td><td>0.9880</td><td>0.9849</td><td>0.9894</td><td>0.9921</td><td>0.9940</td></tr><tr><td>grain</td><td>17.3653</td><td>0.9462</td><td>0.9513</td><td>0.9270</td><td>0.9407</td><td>0.9457</td><td>0.9621</td></tr><tr><td>interest</td><td>35.8447</td><td>0.7174</td><td>0.7838</td><td>0.7376</td><td>0.7949</td><td>0.7826</td><td>0.7945</td></tr><tr><td>money-fx</td><td>13.5037</td><td>0.7379</td><td>0.7742</td><td>0.7572</td><td>0.7439</td><td>0.7365</td><td>0.7799</td></tr><tr><td>money-supply</td><td>49.7009</td><td>0.7636</td><td>0.8182</td><td>0.8000</td><td>0.7536</td><td>0.8000</td><td>0.9000</td></tr><tr><td>ship</td><td>48.8487</td><td>0.6444</td><td>0.7482</td><td>0.7237</td><td>0.7361</td><td>0.7114</td><td>0.7500</td></tr><tr><td>sugar</td><td>64.1868</td><td>0.8679</td><td>0.8966</td><td>0.8308</td><td>0.8182</td><td>0.8571</td><td>0.8966</td></tr><tr><td>trade</td><td>19.1085</td><td>0.8756</td><td>0.8889</td><td>0.8308</td><td>0.8475</td><td>0.8815</td><td>0.8950</td></tr><tr><td>平均值</td><td></td><td>0.8402</td><td>0.8710</td><td>0.8368</td><td>0.8467</td><td>0.8580</td><td>0.8857</td></tr></table></body></html>

从实验结果中可以看出原始CNN在两个数据集上的性能都较差，尤其是当类别极不平衡时，如在Reuters-21578数据集上，当正类类别为 money-supply 和ship 等，说明以0-1损失为优化目标的算法在面对不平衡数据分类时性能受限。类别重组算法在两个数据集上的平均性能都较优，但是由于升采样了正类样本，相当于增加了训练样本数，从而导致相比其他算法所需的训练时间更长。而代价敏感类的算法Focal-Loss相对于偏置CNN算法的性能有所提升，表明Focal-Loss对偏置CNN改进的有效性。

实验结果同时表明，本文提出的WPLoss在绝大部分数据集上的性能优于其他方法，并且在两个数据集上的平均性能取得最优结果，从而验证了WPLoss的有效性。与原始的AUCLoss相比，WPLoss几乎在所有数据集上都取得了较优的性能，表明WPLoss通过着重优化难以区分的正负样本对提升了分类器的性能。当正负类别极为不平衡时，WPLoss与AUCLoss相比性能优势更加明显。如Reuters-21578中，正类类别为money-supply时，不平衡率为49.7009，WPLoss与AUCLoss相比提升了 $12 . 8 \%$ ；正类类别为ship 时，不平衡率为48.8487，WPLoss与AUCLoss相比提升了 $5 . 4 \%$ ；正类类别为sugar时，不平衡率为64.1868，WPLoss与AUCLoss相比提升了 $4 . 6 \%$ 。

# 3 结束语

本文提出了一种面向不平衡数据的加权成对损失WPLoss，通过赋予距离较小的正负样本对更大的损失权重，使得优化算法着重优化难以区分的正负样本对，从而提升分类器的性能。在公开数据集20newsgroup 和Reuters-21578上的实验结果表明，WPLoss不仅仅相对原始的成对损失有较优的性能，同时，与其他处理不平衡数据的方法相比，也取得了较优的性能，尤其在不平衡率较高的时候。

# 参考文献：

[1]向鸿鑫，杨云．不平衡数据挖掘方法综述[J].计算机工程与应用,

2019,55 (O4): 6-21.(Xiang Hongxin, Yang Yun.Survey on Imbalanced Data Mining Methods [J].Computer Engineering and Applications,2019, 55 (04): 6-21.)

[2]Garcia V,MarquésAI, SanchezJS.Exploring the synergetic effects of sample types on the performance of ensembles for credit risk and corporate bankruptcy prediction [J].Information Fusion,2019,47: 88- 101.   
[3]Padurariu C,Breaban M E.Dealing with Data Imbalance in Text Classification [J].Procedia Computer Science,2019,159:736-745.   
[4]Oksuz K,Cam B C,Kalkan S,et al.Imbalance Problems in Object Detection:A Review [J]．arXiv:Computer Vision and Pattern Recognition,2019.   
[5]Liu,Xuying,Wu Jianxin, Zhou Zhihua.Exploratory Undersampling for Class-Imbalance Learning [J]．IEEE Trans on Systems Man& Cybernetics PartB,2009,39 (2):539-550.   
[6]Lin Weichao,Tsai C,Hu Yahan,et al.Clustering-based undersampling in class-imbalanced data [J]. Information Sciences,2017,409/410:17- 26.   
[7]Ofek N,Rokach L,Stern R,et al.Fast-CBUS:a fast clustering-based undersampling method for addressing the class imbalance problem [J]. Neurocomputing,2017,243: 88-102.   
[8]Chawla NV,Bowyer KW,HallL O,et al.SMOTE: synthetic minority over-sampling technique [J]. Journal of Artificial Intelligence Research, 2002,16(1): 321-357.   
[9]Fiore U,De Santis A,Perla F,et al.Using generative adversarial networks for improving classification effectiveness in credit card fraud detection [J].Information Sciences,2019,479: 448-455.   
[10] Douzas G,Bacao F.Effective data generation for imbalanced learning using conditional generative adversarial networks [J].Expert Systems with applications,2018,91: 464-471.   
[11] Shicai Yang. Several tips and tricks for ImageNet CNN training. Technique Report pages 1-12,2016.   
[12] Zhou Z H. Cost-sensitive learning [M].Modeling decision for artificial intelligence.Berlin,Heidelberg:Springer,2011:17-18.   
[13] Lin,Tsung-Yi,Goyal,Priya,Girshick,Ross,et al.Focal Loss for Dense Object Detection[J].IEEE Transactions on Pattern Analysis& Machine Intelligence,2017,PP(99): 2999-3007.   
[14]Freund Y,IyerRD,SchapireRE,etal.An efficient boosting algorithm for combining preferences [J].Journal of Machine Learning Research, 2003,4(6):933-969.   
[15] Rudin C,Schapire R E.Margin-based Ranking and an Equivalence between AdaBoost and RankBoost [J]. Journal of Machine Learning Research,2009:2193-2232.   
[16]UlfB,Tobias S.AUC maximizing support vector learning.[C]//Proc of ICML,2005.   
[17] Joachims T.A support vector method for multivariate performance measures [C]//Proc ofICML,2005: 377-384.   
[18]Wei Gao,Rong Jin,Shenghuo Zhu,et al. One-Pass AUC Optimization [J].arXiv:Learning,2013.   
[19] Gao Wei,Zhou Zhihua.On the consistency of AUC pairwise optimization [C]// Proc of 24th International Joint Conference on Artificial Intelligence.2015,939-945.   
[20] Yang Yiming and Liu Xin.A re-examination of text categorization methods [C]//Proc of 22nd Annual International SIGIR Conference on Research and Development in Information Retrieval,1999,42-49   
[21] Kim Y. Convolutional neural networks for sentence classification [J]. arXiv preprint arXiv:1408.5882,2014.   
[22] Mikolov T,Sutskever I,Chen K,et al.Distributed representations of words and phrases and their compositionality [C]// Proc of NIPS,2013, 3111-3119.   
[23] Kingma D P,Ba J.Adam: A Method for Stochastic Optimization [J]. arXiv: Learning,2014.