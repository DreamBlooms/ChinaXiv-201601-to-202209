# 基于深度置信网络的高分辨率雷达距离像识别

王泓霖¹a，李伟，许强¹a，徐建业la，张军²(1.空军工程大学a.研究生院；b.信息与导航学院，西安 710077；2.国防科技大学电子科学与工程学院，长沙410073)

摘要：为提高雷达目标识别准确率，提出了一种基于深度置信网络(DBN)的高分辨率雷达距离像(HRRP)识别方法。首先利用受限玻尔兹曼机(RBM)对 HRRP数据进行逐层无监督训练，根据对比散度(CD)算法更新网络参数，通过误差重构设计 DBN 深度，而后利用反向传播(BP)机制对 DBN模型参数进行有监督的微调，最后基于该模型实现了HRRP 的分类与识别。实验结果表明，与传统神经网络相比，基于本文设计的深度置信网络的识别准确率及噪声鲁棒性显著提高，识别准确率可提高 $8 . 5 \%$ 。

关键词：深度置信网络；高分辨距离像；重构误差；目标识别 中图分类号：TP391.41 doi:10.19734/j.issn.1001-3695.2018.09.0647

High resolution range profile recognition based on deep belief network

Wang Honglinla, Li Weilb, Xu Qiangla, Xu Jianyela, Zhang Jun² (1.a.GraduateCollege,b.Information&Navigation College,AirForceEngineering UniversityXi'an70Cina;2. Electronic Science&Engineering Collge,National UniversityofDefenseTechnology,Changsha4103,China)

Abstract: In order to improve the acuracyofradar target recognition,this paper proposes a high resolutionrange profile (HRRP)recognition method based on deep belief network (DBN).Firstly,the method uses arestricted Boltzmann machine (RBM)to perform layer-by-layer unsupervisedtraining on HRRPdata.The network parameters are updatedaccording to the contrast divergence(CD）algorithm,and the DBN depth is designed bythe reconstruction error method.Then,the DBN model parameters are supervised andfine-tuned through a back propagation (BP)mechanism.Finaly,based onthe model, theclassificationandrecognitionof HRRP isrealized.The experimental results show thatcompared with the traditional neural network，the recognition accuracyand noise robustness of the deep belief network basedon this paperare significantly improved,and the recognition accuracy can be improved by $8 . 5 \%$ ：

Key words: deep belief network, high resolution range profile,reconstruction error,target recognition

# 0 引言

雷达目标识别与分类是第四代雷达体制的关键技术之一，也是当前雷达主要研究领域之一。高分辨距离像(highresolutionrangeprofile，HRRP)是目标三维结构在一维空间上的投影，可很好地反映目标散射点沿雷达视线（radarlineofsight,RLOS）径向分布信息，不仅提供了比低分辨雷达目标回波信号更多特征信息，还避免了二维或三维成像过程中复杂的运动补偿和过多的成像耗时，具有易于获取和方便处理的独特优势[1]。因此，基于HRRP的目标识别是雷达自动目标识别（radar automatic target recognition，RATR）领域重要研究方向之一[2]。目前基于HRRP的识别方法主要有模板匹配法[3.4]、支持向量机[5.6]、聚类[7]、主成分分析[8-10]、稀疏表示[11,12]、神经网络[13-16]等。但以上方法在数据预处理时需人工进行特征提取，对复杂函数表示能力有限，目标泛化能力低，不可避免地造成一定信息损失，且常常面临维数灾难、局部最优及过学习问题，影响识别正确性的提高。

针对传统神经网络需要大量的标签样本集、收敛速度慢以及易出现局部最优解等问题，Hinton 等人[17]于 2006 年提出了非监督的逐层贪婪训练方法，解决了神经网络深度增加所带来的"梯度耗散"问题，显著提高网络分类和预测的准确性，使神经网络结构规模与识别精度与日俱增。

本文提出了一种基于深度置信网络的高分辨雷达目标检测方法，通过DBN有监督学习和无监督学习的训练过程，优化DBN模型参数，设计了一种基于RBM重构误差的隐含层深度确定方法，让网络通过计算自组织地训练，设计出既能满足精度要求，又能节约成本的网络深度，并通过实验仿真验证模型有效性。

# 1 深度置信网络模型

深度置信网络(deepbeliefnetwork，DBN)由若干个受限玻尔兹曼机(restrictedBoltzmannmachines,RBM)和一个反向传播网络（back-propagation，BP）叠加组成，其训练过程分为无监督预训练和有监督微调两个部分[18]。首先，使用无监督学习方法预训练每一层RBM，将低层RBM输出作为高层RBM输入，以贪婪方式训练每层RBM，利用对比散度(contrastivedivergence，CD)快速算法初始化RBM的权值和偏置，确保特征向量映射最优。然后，将训练好的RBM 连接到BP神经网络，利用BP算法有监督对DBN微调，通过顶层输出与期望输出间的误差函数，对整个网络的权值和偏置反向微调，优化DBN网络参数[19]。其结构如图1所示。

![](images/cbe783ced2f5420ea9d242067f4d990c96e1a62cd1c53aea87db53be16a0b20c.jpg)  
图1DBN 网络结构Fig.1 DBN model structure

# 1.1受限玻尔兹曼机

受限玻尔兹曼机是一种典型的基于能量的模型（energy-basedmodel，EBM），它由两层神经元构建组成：一层为可视层（visiblelayer） $\nu _ { \mathrm { i } }$ ，即数据输入层，一般为伯努利型或高斯型；一层为隐含层（hiddenlayer） $h _ { j }$ ，即特征提取层，一般为伯努利型[20]。RBM层间神经元双向全连接，层内神经元无连接，输入数据由可视层传播至隐含层，再由隐含层传回至可视层，如图2所示。

![](images/cfc3ad50ae3669273f683c31f501d6eb32e69b4ac80609f0383452b81809df4f.jpg)  
Fig.2RBM model structural

伯努利一伯努利型RBM采用二进制方式，可视层与隐含层均为二值变量，而雷达回波多为连续分布的实值数据，二值变量难以有效表示，存在变量不匹配问题[21]。因此本文采取高斯-伯努利型RBM构建模型，将可视层二值节点替换为高斯实值变量节点。高斯一伯努利型RBM能量函数如下：

$$
E ( \nu , h | \theta ) = - \sum _ { i = 1 } ^ { n } \frac { ( \nu _ { i } - a _ { i } ) ^ { 2 } } { 2 { \sigma _ { i } } ^ { 2 } } - \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } \frac { w _ { i j } \nu _ { i } h _ { j } } { \sigma _ { i } } - \sum _ { j = 1 } ^ { m } b _ { j } h _ { j }
$$

其中： $\theta = ( w _ { i j } , a _ { i } , b _ { j } )$ ， $w _ { i j }$ 表示可视层神经元 $\nu _ { i }$ 与隐含层神经元$h _ { j }$ 间的连接权值， $a _ { i }$ ， $b _ { j }$ 分别表示 $\nu _ { i }$ 与 $h _ { j }$ 对应的偏置值， $\sigma _ { i }$ 为 $\nu _ { i }$ 对应高斯噪声标准差。由式(1)求得可视层与隐含层神经元的联合概率分布为

$$
p ( \nu , h | \theta ) = \frac { e ^ { - E ( \nu , h | \theta ) } } { \displaystyle \sum _ { \nu } \sum _ { h } e ^ { - E ( \nu , h | \theta ) } }
$$

RBM同层神经元无连接，激活状态相互独立，当给定可视层神经元状态时，各隐含层神经元激活状态相互独立[22],此时第 $j$ 个隐含层神经元的激活概率如下：

$$
p ( h _ { j } = 1 , \big | \nu ; \theta ) = \frac { \displaystyle \sum _ { \nu } e ^ { - E ( h , \nu | \theta ) } } { \displaystyle \sum _ { u } \sum _ { \nu } e ^ { - E ( u , \nu | \theta ) } } = [ 1 + e ^ { - ( \sum _ { i = 1 } ^ { n } w _ { i j } \nu _ { i } + b _ { j } ) } ] ^ { - 1 }
$$

同理，给定隐含层神经元状态，第i个隐含层神经元的激活概率如下：

$$
p ( \nu _ { i } = 1 , | h ; \theta ) = \frac { \displaystyle \sum _ { h } e ^ { - E ( \nu , h | \theta ) } } { \displaystyle \sum _ { u } \sum _ { h } e ^ { - E ( u , h | \theta ) } } = [ 1 + e ^ { - ( \sum _ { j = 1 } ^ { m } w _ { i j } h _ { j } + a _ { i } ) } ] ^ { - 1 }
$$

采用最大似然化函数可使训练参数能够更好地拟合训练数据分布，求得

$$
L ( \theta ) = \prod _ { i = 1 } ^ { n } p ( \nu | \theta )
$$

RBM采用迭代方式进行训练，利用梯度下降算法求解参数 $\theta = ( w _ { i j } , a _ { i } , b _ { j } )$ 迭代公式如下：

$$
\theta = \theta + \eta \frac { \partial \ln \biggl [ \displaystyle \prod _ { i = 1 } ^ { n } p ( \nu | \theta ) \biggr ] } { \partial \theta }
$$

其中： $\eta$ 为预训练阶段的学习率。当数据维度较高时，梯度下降法求解模型期望十分困难。采用与梯度下降算法相似的CD算法对重构数据进行吉布斯采样，可大大提高RBM训练效率，得

$$
\langle \nu _ { i } h _ { j } \rangle _ { d a t a } - \langle \nu _ { i } h _ { j } \rangle _ { r e c o n } = \frac { \hat { \sigma } \ln p ( \nu | \theta ) } { \hat { \sigma } w _ { i j } }
$$

其中： $\langle \bullet \rangle _ { d a t a }$ 表示训练数据集的数学期望， $\left. \bullet \right. _ { r e c o n }$ 表示重构模型的数学期望，求得DBN权值与偏重的更新准则如下：

$$
\Delta w _ { i j } = \eta ( \langle \nu _ { i } h _ { j } \rangle _ { d a t a } - \langle \nu _ { i } h _ { j } \rangle _ { r e c o n } )
$$

$$
\Delta a _ { i } = \eta ( \langle \nu _ { i } \rangle _ { d a t a } - \langle \nu _ { i } \rangle _ { r e c o n } )
$$

$$
\Delta b _ { j } = \eta ( \langle h _ { j } \rangle _ { d a t a } - \langle h _ { j } \rangle _ { r e c o n } )
$$

通过式(8)\~(10)非监督预训练过程可将RBM各参数调整到合适初值，最大限度避免局部最优解。

# 1.2 反向传播网络

BP 神经网络是一种典型的误差反向传播机制，可对RBM预训练阶段的特征向量进行分类，微调DBN模型权值与偏置。BP神经网络的典型结构如图3所示。

![](images/7283e64d7731658ba6baac0ff1554b7ebece62f54c6d8fe347a9c96c6ba8f36d.jpg)  
图2受限玻尔兹曼机结构模型  
图3BP神经网络模型  
Fig.3BP neural network model

误差反向传播(back-propagation，BP)算法的主要思想是将网络学习过程分为两个阶段：a)信号正向传播，将输入信号经输入层、隐含层、输出层逐层处理，求解每个单元的实际输出值；b)误差反向传播，如果实际输出和期望输出存在误差，则将误差信号沿原连接通路返回，所得误差分摊给各层所有的单元来修正各层神经元权值。不断重复这两个过程，直到网络误差满足要求[23]。假设 $\boldsymbol { d } _ { k }$ 与 $y _ { k }$ 为输出层第 $k$ 个神经元的期望输出和实际输出，则节点的残差项为

$$
\delta _ { k } = y _ { k } ( 1 - y _ { k } ) \big ( d _ { k } - y _ { k } \big )
$$

误差反向传播对于第 $\mathbf { \xi } _ { l }$ 层神经元 $\delta _ { k } ^ { l }$ 的表达式如下：

$$
\delta _ { k } ^ { l } = y _ { k } ^ { l } ( 1 - y _ { k } ^ { l } ) \sum _ { j = 1 } ^ { m } w _ { i j } ^ { l } \delta _ { j } ^ { l + 1 }
$$

根据梯度下降法，微调阶段网络的权值与偏置根据式(13)(14)更新，其中 $\boldsymbol { \varepsilon }$ 为微调阶段的学习率。

$$
\begin{array} { c } { { w _ { i j } ^ { l } = w _ { i j } ^ { l } + \varepsilon y _ { i } ^ { l } \delta _ { i } ^ { l + 1 } } } \\ { { b _ { j } ^ { l } = b _ { j } ^ { l } + \varepsilon \delta _ { j } ^ { l + 1 } } } \end{array}
$$

# 2 深度置信网络设计

# 2.1 网络深度设计

不同深度的网络其识别性能及训练时间等均不相同，主要体现在：DBN 训练精度随网络深度增加而提高[24]；DBN计算性能随网络深度增加而下降[25]；顶层单元达到阈值后，DBN识别效率基本维持不变[26]。

DBN模型训练过程中，通过RBM无监督预训练，网络权值已经处于较优位置，BP网络反向微调仅在较小范围内调节网络权值，故选择合适RBM隐含层数，对模型优化有重要意义。为满足训练精度，节约网络成本，本文基于重构误差方法设计网络隐含层数，利用经RBM一次吉布斯采样重构后的数据与初值数据的差异量进行评估，如下式所示：

$$
R _ { e r r o r } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m } \left( c _ { i j } - x _ { i j } \right) } { n m p } }
$$

其中： $R _ { e r r o r } { } ~$ 为重构误差， $x _ { i j }$ 为初值数据， $c _ { i j }$ 为网络重构数据，$p$ 为取值范围， $\boldsymbol { L }$ 为RBM层数， $e _ { c }$ 为期望误差。通过重构误差与期望误差进行对比，计算并确定DBN深度，规则如下：

$$
\begin{array} { l } { \left\{ L = N _ { R B M } + 1 , R e r r o r > e _ { c } \right. } \\ { L = N _ { R B M } , R e r r o r < e _ { c } } \end{array}
$$

如果预训练阶段RBM重构误差精度达到期望误差要求，网络进入反向微调阶段；若不满足期望误差要求，则增加一层RBM，继续对网络进行预训练，直到网络重构误差满足要求，选取合适的DBN深度。网络训练流程如图4所示。

![](images/5c6854d0331b5fc09ad51b6e2d27974838435a7198c32cec659d70127d57e872.jpg)  
图4DBN训练流程图 Fig.4DBN training flow chart

# 2.2隐含层节点设计

网络深度及节点数增加可以降低网络误差，提高精度，但也使网络复杂化。目前DBN节点数确定方法没有完善理论依据，本文通过实验方法确定网络节点数。

设计DBN模型由1层RBM输入层，L层RBM隐含层以及1层BP输出层构成，为简便起见，设DBN各隐含层节点数相同。针对不同隐含层节点数，根据重构误差方法设计各网络模型，进行对比测试，结果如表1所示。

由表1可以看出，DBN重构误差的精度与网络节点数及网络深度息息相关，当隐含层节点数较多时，只需数层RBM便可满足重构误差目标要求，实现较高的识别率，当隐含层节点数较少时，为使网络达到目标误差，必须增加隐含层个数。同时训练时间也会随网络深度及节点数的增加而延长。分析可知，当隐含层节点数规模较小时，神经元之间的连接较少，对特征的提取能力有限；而隐含层数目过多则会降低网络泛化性能，出现过拟合问题。

Table 1 DBN training data for different hidden layer nodes   

<html><body><table><tr><td>隐含层节点数</td><td>隐含层深度</td><td>重构误差</td><td>识别率</td><td>训练时间/s</td></tr><tr><td>256</td><td>1</td><td>0.29441</td><td>98.4375%</td><td>5.499</td></tr><tr><td>128</td><td>1</td><td>0.34209</td><td>97.7051%</td><td>4.214</td></tr><tr><td>64</td><td>2</td><td>0.40886</td><td>99.8535%</td><td>4.363</td></tr><tr><td>32</td><td>2</td><td>0.36126</td><td>97.168%</td><td>4.026</td></tr><tr><td>16</td><td>2</td><td>0.34703</td><td>81.1523%</td><td>3.830</td></tr><tr><td>8</td><td>3</td><td>0.19571</td><td>78.735%</td><td>3.838</td></tr></table></body></html>

实验发现，隐含层节点设置为64时，DBN分类精度最高，根据重构误差方法，此时网络隐含层数为2层。

# 3 实验分析

# 3.1实验参数选取

实验选取外场所测4类越野车雷达回波数据，每类目标测得1280幅距离像，每幅距离像的长度为256，如图5所示。抽取总数据的 $60 \%$ 作为训练集，余下 $40 \%$ 作为测试集。

![](images/7cc2c986321ef54f94560222c2722006c0eef6201e1db3070fcf40a798a31ea2.jpg)  
图5雷达一维距离像  
Fig.5High resolution radar range profile

根据文献[27]，利用网格搜索寻优的方法，设置DBN参数如下：预训练阶段和微调阶段的学习率为0.1，最小样本数量为32，由于样本在迭代20次后趋于稳定，设置迭代次数为20，输入层节点数为256，输出层节点数为4。设计网络结构为256-64-64-4。经多次实验确定重构目标期望误差设置为0.5时，网络性能最佳，如表2所示。

表1不同隐含层节点DBN训练数据  
表2期望误差对网络影响  

<html><body><table><tr><td>期望误差</td><td>隐含层深度</td><td>重构误差</td><td>识别率</td><td>训练时间(s)</td></tr><tr><td>1</td><td>1</td><td>0.71363</td><td>97.3652%</td><td>3.848</td></tr><tr><td>0.5</td><td>2</td><td>0.40886</td><td>99.8535%</td><td>4.363</td></tr><tr><td>0.1</td><td>4</td><td>0.025667</td><td>75%</td><td>5.514</td></tr><tr><td>0.05</td><td>4</td><td>0.025667</td><td>75%</td><td>5.514</td></tr><tr><td>0.01</td><td>5</td><td>0.0025682</td><td>99.5605%</td><td>6.195</td></tr></table></body></html>

# 3.2 DBN深度影响分析

为测试本文基于重构误差方法设计的 DBN 模型是否有效，针对隐含层节点为64，深度不同时的DBN进行对比测试如表3所示。

Table 2Impact of expected error on the network   
表3不同隐含层深度DBN训练数据  
Table 3DBN training data with different hidden layer depths   

<html><body><table><tr><td>隐含层节点数</td><td>隐含层深度</td><td>重构误差 识别率</td><td></td><td>训练时间(s)</td></tr><tr><td>64</td><td>1</td><td>0.71363</td><td>97.3652%</td><td>3.848</td></tr><tr><td>64</td><td>2</td><td>0.40886</td><td>99.8535%</td><td>4.363</td></tr><tr><td>64</td><td>3</td><td>0.17143</td><td>85.7305%</td><td>4.966</td></tr><tr><td>64</td><td>4</td><td>0.025667</td><td>75%</td><td>5.514</td></tr></table></body></html>

由表3可以看出，随网络深度增加，网络重构误差逐渐降低，运算时间逐渐增大，在隐含层深度为2时，DBN识别率达到最高，为 $9 9 . 8 5 3 5 \%$ ，训练时间为 $4 . 3 6 3 \mathrm { ~ s ~ }$ ，继续增加网络深度，虽然重构误差会继续降低，但识别率却逐渐下降，网络出现严重过拟合问题。证明本文根据重构误差方法进行的网络设计、参数选取准确有效。

针对增加隐含层数量，网络识别率下降的问题，本文分析原因如下：

a)隐含层数目增加只能令预训练阶段RBM的重构误差减小，并不能缩减BP微调阶段的网络误差。

b)隐含层数目增加导致微调阶段反向误差累积过大。

c)隐含层数目增加降低DBN泛化性能，导致出现过拟合问题。

d)隐含层数目增加导致算法时间复杂度提高，效率降低。

# 3.3与其他分类方法对比

为验证DBN对HRRP的识别效能及网络稳定性，将深度置信网络与传统神经网络(NN)、支持向量机(SVM)方法及卷积神经网络(CNN)进行对比。其中NN采用BP优化机制，SVM核函数采用径向基函数，参数选取参考文献[6]；由文献[16]可知虽然CNN更适合处理二维图像，但由于HRRP形成机理与光学图像并不相同，将雷达一维距离像转变为二维像会破坏内部的结构信息，因此卷积神经网络采用一维卷积神经网络最佳，网络结构根据文献[16]确定。对HRRP数据加入 $\operatorname { S N R } = 3$ dB 的高斯白噪声进行对照实验，识别结果如表4所示。

表4不同方法分类效果比较  
Table 4Comparison of different methods   

<html><body><table><tr><td>识别方法</td><td>识别率</td><td>加噪后识别率</td><td>训练时间(s)</td></tr><tr><td>NN</td><td>91.33%</td><td>90.74%</td><td>2.802</td></tr><tr><td>SVM</td><td>94.36%</td><td>93.29%</td><td>2.137</td></tr><tr><td>CNN</td><td>99.09%</td><td>98.08%</td><td>7.308</td></tr><tr><td>DBN</td><td>99.85%</td><td>98.12%</td><td>4.363</td></tr></table></body></html>

实验结果表明，在相同数据条件下，相对于NN，DBN通过RBM无监督预训练为网络提供了合适的初值，模型识别准确率提高 $8 . 5 2 \%$ ；对于SVM，DBN利用多层网络结构，学习到深层抽象的数据特征，识别准确率提高 $5 . 4 9 \%$ ，可见DBN结合无监督学习和有监督学习特点，相对于传统算法，取得了更好分类性能。由表4可知，与CNN相比，二者识别效率相差不大，但采用DBN结构网络运算时间可缩短$4 0 . 3 \%$ 。由于CNN内部卷积池化特性，网络运算复杂，更适合提取二维图像特征，在处理HRRP数据方面，DBN则具备更明显的优势。在加入 $\mathrm { S N R } { = } 3 \mathrm { d B }$ 高斯白噪声后，识别率仍可达到 $9 8 . 1 2 \%$ ，识别率显著高于其他网络，表明DBN结构噪声鲁棒性较高。

# 4 结束语

针对雷达高分辨率距离像的识别问题，提出了一种基于深度置信网络的目标识别方法，通过RBM无监督预训练及BP 有监督微调优化DBN模型，基于重构网络误差方法，设计DBN隐含层深度。利用实测数据对该模型进行验证表明，在不需要进行人工特征提取情况下，本方法在雷达目标的分类实验中，达到了 $9 9 . 8 5 \%$ 的识别准确率，相对其他分类算法有较大提升，网络鲁棒性优良。证明了深度置信网络在HRRP识别中的应用价值。

# 参考文献：

[1]周云.基于高分辨距离像的雷达目标识别研究[D]．成都:电子科技 大学,2O16.(Zhou Yun.Research on radar target recognition based on high resolution range profile[D]. Chengdu: University of Electronic Science and Technology of China,2016.)   
[2]刘宏伟，杜兰，袁莉，等．雷达高分辨距离像目标识别研究进展[J]. 电子与信息学报，2005,27(8):1328-1334.(Liu Hongwei，Du Lan, Yuan Li,et al. Progress in radar automatic target recognition based on high range resolution profile [J]. Journal of Electronics and Information Technology,2005,27(8): 1328-1334.)   
[3] Jiang Yuan,Li Yang，Cai Jinjian，et al.Robust automatic target recognition via HRRP sequence based on scatterer matching[J]. Sensors, 2018,18(2): 593.   
[4]Du Lan,Liu Hongwei, Bao Zheng,et al. Radar HRRP target recognition based on higher order spectra [J]. IEEE Trans on Signal Processing, 2005,53(7):2359-2368.   
[5]高倩，吴仁彪．一种基于 SVM分类器的 HRRP-ATR 方法[J]．现代 雷达，2004,26(5):20-23.(Gao Qian,Wu Renbiao.HRRP-ATR based on SVM Classifier[J].Modern Radar,2004,26(5):20-23.)   
[6]张欢．基于射频隐身的机载雷达系统软件实现及HRRP目标识别研 究[D]．南京:南京航空航天大学，2016.(Zhang Huan.RF stealth based airborne radar system simulation and HRRP target recognition research[D]. Nanjing:Nanjing University of Aeronauticsand Astronautics, 2016. )   
[7]吴佳妮，陈永光，代大海,等.基于快速密度搜索聚类算法的极化 HRRP分类方法[J]．电子与信息学报,2016,38(10):2461-2467.(Wu Jiani,Cheng Yongguang，Dai Dahai,et al.Target recognition for polarimetric HRRP based on fast density search clustering method. [J]. Journal of Electronics and Information Technology，2016,38(10): 2461-2467.)   
[8] Du Lan,Liu Hongwei,Bao Zheng，et al. Radar automatic target recognition using complex high-resolution range profiles [J]. IET Radar Sonar and Navigation,2007,1(1):18-26.   
[9]李龙，刘峥.基于核主分量相关判别分析特征提取方法的目标 HRRP 识别[J]．电子与信息学报，2018,40(1):173-180.(Li Long，Liu Zheng.Kernel principal component correlation and discrimination analysis feature extraction method for target HRRP recognition [J]. Journal of Electronics and Information Technology，2018，40(1): 173-180.)   
[10]赵东波，李辉．基于平移不变核主分量分析的雷达目标识别研究 [J]．计算机应用研究,2011,28(10):3907-3909.(Zhao Dongbo,Li Hui. Algorithm research of radar target recognition based on kernel principal component analysis [J]. Application Research of Computers,2011, 28(10): 3907-3909.)   
[11] Yuan Jiawen,Liu Wenbo,Yang Mengjiao,et al. Radar HRRP target recognition based onHilbert Huang transform [J]. Electronic Measurement Technology,2018,41(14): 78-82.   
[12] Guo Yu, Xiao Huaitie,Kan Yingzhi,et al.Learning using privileged information for HRRP-based radar target recognition [J]. IET Signal Processing,2018,12(2): 188-197.   
[13]Lundén J，Koivunen V.Deep learning for HRRP-based target recognition in multistatic radar systems[C]//Proc of IEEE Radar Conference. Piscataway, NJ: IEEE Press,2016: 1-6.   
[14]徐彬，陈渤，刘宏伟，等．基于注意循环神经网络模型的雷达高分辨 率距离像目标识别[J]．电子与信息学报，2016,38(12)：2988-2995. (Xu Bin,Cheng Bo,Liu Hongwei，et al.Attention-based recurent neural network model for radar High-resolution range profile target recognition.[J]. Journal of Electronics and Information Technology, 2016,38(12): 2988-2995.)   
[15] Feng Bo,Chen Bo,Liu Hongwei. Radar HRRP target recognition with deep networks [J]. Pattern Recognition,2017,61(1): 379-393.   
[16]杨予昊，孙晶明，虞盛康，彭雄伟．基于卷积神经网络的高分辨距离 像目标识别[J]．现代雷达,2017，39(12):24-28.(Yang Yuhao，Sun Jingming，Yu Shengkang，et al.High resolution range profile target recognition based on convolutional neural network [J].Modern Radar, 2017,39(12):24-28.)   
[17] Hinton G E, Salakhutdinov R R.Reducing the dimensionality of data with neural networks [J]. Science,2006,313(5786):504-507.   
[18] Hinton G E,Osindero S,Teh Y W.A fast learning algorithm for deep belief nets [J].Neural Computation,2006,18(7): 1527-1554.   
[19]廖强，张杰．基于信息熵的DBN网络结构优化[J].信息通信,2018, 181(1):44-48.(Liao Qiang,Zhang Jie. Optimization of DBN network structurebasedoninformationentropy[J].Informationand Communications,2018,181(1): 44-48.)   
[20] Hinton G E.Training products of experts by minimizing contrastive divergence [J].Neural Computation,2002,14(8):1771-1800.   
[21] Cho K,Ilin A，Raiko T. Improved learning of gaussian-bernoulli restricted Boltzmann machines [C]// Proc of International Conference on Artificial Neural Networks.Berlin: Springer,2O11:10-17.   
[22]吕启,窦勇,牛新,等．基于DBN模型的遥感图像分类[J].计算机研究 与发展,2014,51(9):191l-1918.(Lyu Qi,Dou Yong,Niu Xin,et al. Remote sensing image classification based on DBN model [J]. Journal of Computer Research and Development,2014,51(9):1911-1918.)   
[23]Lv Yumin,Tang Dazhen,Xu Hao,et al.Productivity matching and quantitative prediction of coalbed methane wells based on BP neural network [J]. Science China Technological Sciences,2011,54(5): 1281-1286.   
[24]Le Roux N,Bengio Y.Representational power of restricted Boltzmann machines and deep belief networks[J].Neural Computation,2Oo8,20(7): 1631-1649.   
[25]Larochelle H,Bengio Y,Louradour J,et al.Exploring strategies for training deep neural networks[J]. Journal of Machine Learning Research,2009,10(1):1-40.   
[26]潘广源,柴伟,乔俊飞.DBN网络的深度确定方法[J].控制与决策， 2015,30(2):256-260.(Pan Guangyuan，ChaiWei，Qiao Junfei. Calculation for depth of deep belief network [J].Control and Decision, 2015,30(2):256-260.)   
[27]Hinton G E.A practical guide to training restricted Boltzmann machines, UTML TR 2O10-O03 [R]. Toronto:Department of Computer Science, University of Toronto,2010.