# 基于CNN-LSTM的QAR数据特征提取与预测

张鹏1，杨 涛²，刘亚楠²，樊志勇1，段照斌1(1．中国民航大学 工程技术训练中心，天津 300300;2.中国民航大学 电子信息与自动化学院，天津 300300)

摘要：针对传统数据驱动的故障诊断方法难以从QAR 数据中提取有效特征的问题，提出一种融合卷积神经网络(convolutional neural network,CNN)与长短时记忆网络(long short-term memory,LSTM)的双通道融合模型 CNN-LSTM。CNN 与LSTM分别作为两个通道，通过注意力机制(attention)融合，从而使模型能同时表达数据在空间维度和时间维度上的特征，并以时间序列预测的方式验证融合模型特征提取的有效性。实验结果表明，双通道融合模型与单一的CNN、LSTM相比，能够更有效地提取数据特征，模型单步预测与多步预测误差平均降低 $3 5 . 3 \%$ 。为基于QAR数据的故障诊断提供一种新的研究思路。

关键词：深度学习；CNN；LSTM；特征提取；时间序列预测 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.04.0214

# Feature extraction and prediction of qar data based on CNN-LSTM

Zhang Peng1,Yang Tao²,Liu Yanan²,Fan Zhiyong1,Duan Zhaobinl (1.EngineeringTraining Center，CivilAviation Universityof China,Tianjin300300,China;2.CollgeofElectronic Information & Automation,Civil Aviation University of China,Tianjin 3oo30o,China)

Abstract:Aimingatthe problem thatitisdifcultforthetraditionalfault diagnosis methodtoextracteffective features from QAR data,this paper proposedadual-channel fusion model,CNN-LSTM,which combines the Convolutional Neural Network(CNN) and the Long Short-Term Memory(LSTM).Respectivelyas two channels,CNNand LSTM fused through the attention mechanism tomakethe modelable tosimultaneously expressthe featuresof thedatainboth space dimensionand timedimensionandverified thevalidityofthefeature extractionofthefusionmodel throughtime series prediction.Resultsof the experiment show that when compared with single CNNorLSTM,the dual-channel fusion modelcanextractdata features more effectively, make the errors of both single-step prediction and multi-step prediction reduceby an average of $3 5 . 3 \%$ ,and provide a new research idea for fault diagnosis based on QAR data.

Key Words: deep learning; CNN;LSTM; feature extraction; time series prediction

# 0 引言

QAR用于记录飞机在飞行过程中的各项参数，连续完整地反映了飞机系统在运行中的实际状态或失效的征兆信号[1]，对飞行安全性起着至关重要的作用。由于QAR数据所记录的多是来自于飞机上各传感器测量的直接参数，无法直观的得出各参数间的关联性，难以直接对飞行品质进行评价。从QAR数据中提取反应系统运行状态的特征向量，从而发掘飞机各系统之间的潜在关联性，并将其应用于各系统的故障诊断当中，是该领域一大挑战性问题。

以飞机操纵系统中的动力控制组件(power control unit,

PCU)故障诊断为例，故障现象有PCU不跟随、PCU 锁定阀门错位、PCU旁路阀门错位、PCU作动可靠性测试未通过；涉及的交联系统包括：电源系统、液压系统、传感系统等。在实际排故中，需要维护人员花费大量时间按照复杂的信号分析逻辑对每一种可能产生故障的原因进行排除，维护人员不仅需要掌握本系统的工作原理，还需要了解交联系统的工作原理。如果将PCU的故障诊断抽象为一个分类问题，从监控PCU的相关QAR数据中提取特征，建立特征与故障类别的对应关系，并进行智能故障诊断，对提高排故效率、保障航班正常运行与飞行安全具有重要意义。解决上述问题的核心之一在于如何从QAR数据中有效提取完备的特征向量。

传统数据驱动的故障诊断方法需要基于信号处理理论和统计理论从原始数据中人工提取特征，不足之处在于需要大量工程实践与信号处理技术来提取信号特征[2]，该方式严重依赖于人员的专业知识。同时，QAR数据具有高维、海量的"大数据"特点，使得传统的特征提取方式难以适用。

Hinton等人[3]提出的深度学习理论是近年来机器学习领域内的研究热点，旨在研究如何从数据中自动地提取多层特征表示[4。近年来，深度学习在特征提取与模式识别方面显示出独特的优势与潜力，并逐步应用于复杂工业系统的故障诊断当中[5]。文献[6]中提出一种基于深度置信网络(Deep Belief Nets,DBN)[3]的飞行器故障特征诊断方法，通过DBN完成故障特征的提取，并实验证明了DBN比传统的故障诊断方法具有更高的鲁棒性和准确性；文献[7]首次将LSTM[8]网络用于锂电池剩余寿命(RUL)预测当中，准确预测了一个周期内的剩余寿命曲线；文献[9]将自动编码器(Autoencoder)用于磨削系统的故障诊断当中，诊断准确率达到 $9 2 . 4 \%$ ，远高于传统BP神经网络算法。文献[10]中将卷积神经网络(CNN)[1I]用于齿轮箱的故障识别和分类当中，并取得了最佳效果。

上述研究表明，基于深度学习的故障诊断算法比传统方法性能上更加优越，能够摆脱传统算法前期特征提取的复杂工作。目前深度学习在计算机视觉、机器翻译、自然语言处理、自动驾驶等领域取得了巨大的成功，但是在故障诊断领域的研究还处于起步阶段，随着深度学习理论的不断完善，其在解决复杂工业系统的故障方面具有很大的潜力[5]。

本文在将研究深度学习理论的基础之上，提出一种双通道融合深度学习模型CNN-LSTM，用于QAR数据特征提取，并以QAR数据预测的方式验证所提特征的完备性。在未使用预测参数（俯仰角）历史值的情况下，预测飞机俯仰角在500个点内的变化，结果表明，模型特征表达性能更优，单步预测与多步预测精度均高于CNN、LSTM。

# 1 深度学习理论

深度学习的概念起源于人工神经网络的研究，有多个隐含层的多层感知器是深度学习模型的显著特征[5]。相对于浅层学习算法，前者具有更好逼近复杂函数的能力，由于具有多隐层结构，能够实现数据特征的逐层转换，保证最有效地信息提取与特征表达[12-13]。深度学习是一种数据驱动的算法，无需建立系统的准确物理模型，只需要收集系统运行的历史数据，即可获得系统的最优特征表示，从而完成故障诊断、故障分类、故障预测等任务。本文主要研究CNN与LSTM两种算法。

拓扑结构特征。随着层数的不断增加，提取的特征越来越抽象，最后将这些抽象特征通过全连接层汇合，并通过softmax 或sigmoid激活函数解决分类问题和回归问题。CNN的特点之一在于可提取输入数据的局部特征，并逐层组合抽象生成高层特征，有效实现故障诊断与识别。

CNN 是由LeCun[1提出，是一种前馈神经网络。典型的卷积神经网络LeNet-5模型如图1所示。其中包括输入层(input）、卷积层（C）、池化层（S）、全连接层（F）以及输出层（output)。

CNN的本质在于构建多个能够提取数据特征的滤波器，通过对输入数据进行逐层卷积和池化操作来提取数据之间隐藏的

# 1.1 卷积神经网络(CNN)

![](images/354b685e8f3d4522ad526347dd6f7be9685cba239626610ba9a2bd2e413a0089.jpg)  
图1LeNet-5模型

# 1.2长短时记忆网络(LSTM)

LSTM是一种时间递归的神经网络，非常适合处理时间序列数据。相较与传统的递归神经网络（RNN)，LSTM通过引入了记忆单元，解决了RNN在实际应用中长期依赖的问题。

LSTM由输入层、隐含层和输出层构成，其结构如图2所示。其中， $g ( t )$ 表示输入单元， $h ( t )$ 表示状态输出单元， $\mathbf { \Omega } _ { M }$ 表示记忆单元， $i ( t )$ 、 $o ( t )$ 、 $f ( t )$ 分别表示输入门限、输出门限以及遗忘门限。

![](images/4f71d3f78cb0d4d06929fd990ad6ee22df6d2a57243060ad96210e1594e691d8.jpg)  
图2LSTM结构

由图2可以看出，M的读、写和遗忘操作由三个门限单元来控制。设输入时间序列为 $x$ ， $\textit { t }$ 为当前时刻，则各单元的状态可用如下公式表示。

输入单元：

$$
g ( t ) = \operatorname { t a n h } ( W _ { x g } g ( t - 1 ) + W _ { h g } h ( t - 1 ) + b _ { g } )
$$

门控单元：

$$
\begin{array} { r } { \begin{array} { r l } & { i ( t ) = \sigma ( W _ { _ { x i } } i ( t - 1 ) + W _ { _ { h i } } h ( t - 1 ) + b _ { i } ) } \\ & { f ( t ) = \sigma ( W _ { _ { x f } } i ( t - 1 ) + W _ { _ { h f } } h ( t - 1 ) + b _ { f } ) } \\ & { o ( t ) = \sigma ( W _ { _ { x o } } i ( t - 1 ) + W _ { _ { h o } } h ( t - 1 ) + b _ { o } ) } \end{array} } \end{array}
$$

记忆单元：

$$
M ( t ) = f ( t ) M ( t - 1 ) + i ( t ) g ( t )
$$

状态输出单元：

$$
h ( t ) = o ( t ) \operatorname { t a n h } ( M ( t ) )
$$

其中， $\sigma$ 表示 sigmoid 激活函数。

# 2 双通道融合模型

CNN与LSTM都是深度学习的主流算法，相对而言，CNN更适合进行空间扩展，提取数据的局部特征，并组合抽象成高层特征。而LSTM更适合进行时间扩展，具有长期记忆功能，更适合处理时间序列。在QAR数据的特征提取中，不仅需要考虑不同参数之间的空间联系，还需要考虑数据在时间维度上的变化，因此本文将CNN与LSTM两种模型以Attention[14]的方式相结合，提出一种双通道融合模型(CNN-LSTM)，使模型具有时间、空间的特征表达能力，模型结构如图3所示。

y(t+1)sigmoidOOOOO融合特征表达Attention0000C ： 隐 B特征表达 ·含层 ，CNNh² h h”LSTMH0N左通道 右通道

其中， $p _ { i }$ 为输入样本中的第i个参数， $T$ 为样本的时间长度， $C _ { r } ^ { i }$ 为CNN网络提取的第i个特征， $h _ { c } ^ { i }$ 为LSTM第 $i$ 个隐含层的输出。

样本分别从左右两个通道输入网络，其中左通道为CNN网络。CNN 网络的最后一层由 $n$ 个神经元输出，得到 $1 \times n$ 维特征向量：

$$
C _ { r } = [ c _ { r } ^ { 1 } , c _ { r } ^ { 2 } , \cdots , c _ { r } ^ { n } ]
$$

右通道为LSTM网络，序列长度为 $n$ ，LSTM隐含层输出维度为 $m$ ，因此得到 $n \times \mathbf { m }$ 维特征向量：

$$
H _ { c } = [ h _ { c } ^ { 1 } , h _ { c } ^ { 2 } , \cdots , h _ { c } ^ { n } ]
$$

得到样本数据在两个通道的特征表达之后，采用Attention机制得到融合特征图，Attention层结构如图4所示：

O： map f_f_f_f A aaα UB softmax(p(h,C,)) OO:O C

其过程可按如下公式描述：

$$
\varphi ( h _ { c } ^ { i } , C _ { r } ) = \operatorname { t a n h } ( h _ { c } ^ { i } \bullet W _ { a } \bullet C _ { r } ^ { \textit { T } } + b _ { a } )
$$

$$
\alpha _ { i } = \frac { \exp ( \varphi ( h _ { c } ^ { i } , C _ { r } ) ) } { \displaystyle \sum _ { j = 1 } ^ { n } \exp ( \varphi ( h _ { c } ^ { j } , C _ { r } ) ) }
$$

$$
f _ { m a p } = \sum _ { i = 1 } ^ { n } \alpha _ { i } h _ { c } ^ { i }
$$

其中： ${ \mathbf { } } W _ { a }$ 为 $m \times n$ 维的权值矩阵， $b _ { a }$ 为偏置项，均由训练时学习得到。 $\boldsymbol { C } _ { r } ^ { \scriptscriptstyle T }$ 是 $C _ { r }$ 的转置。

式(9)将CNN的特征向量与LSTM的特征向量融合成一组“权重"，并通过式(10)Softmax 激活函数将"权重"归一化到0-1之间。最后通过式(11)，将LSTM不同时间点的隐含层输出向量 $h _ { c } ^ { i }$ 与对应的"权重” $\alpha _ { i }$ 相乘，并求和，以此作为样本最终的特征表达，即 $f _ { m a p }$ 。其意义在于：将CNN组合抽象局部特征的能力通过注意力机制的方式来调节LSTM时间维度的特征表达，使其特征在某些区域加强，在某些区域减弱，从而使模型具有时间、空间的特征表达能力。

# 3 算例分析

# 3.1数据集构造

本文以飞行控制系统中的俯仰通道为研究对象，从相关参数中提取特征，来预测俯仰角的变化情况。根据飞控系统工作原理[15]，从QAR数据选取22个相关参数，采样间隔为1秒，各参数含义如表1所示。

表1相关参数表  

<html><body><table><tr><td>参数名称</td><td>参数注释</td><td>单位</td></tr><tr><td>ALTITUDE(1013)</td><td>高度</td><td>FT</td></tr><tr><td>COMPUTEDAIR SPEED</td><td>计算空速</td><td>KT</td></tr><tr><td>VERTICALACCEL</td><td>垂直加速度</td><td>G</td></tr><tr><td>FLIGHTPATHACCELERATION</td><td>飞航加速度</td><td>G</td></tr><tr><td>ALTITUDERATE</td><td>高度变化率</td><td>FT/MIN</td></tr><tr><td>WIND SPEED</td><td>风速</td><td>KT</td></tr><tr><td>DRIFTANGLE</td><td>偏流角</td><td>DEG</td></tr><tr><td>BODYPITCHRATE</td><td>机体俯仰速率</td><td>DEG/SEC</td></tr><tr><td>BODYROLLRATE</td><td>机体滚转速率</td><td>DEG/SEC</td></tr><tr><td>BODY YAWRATE</td><td>机体偏航速率</td><td>DEG/SEC</td></tr><tr><td>FLIGHTDIRECTOR-PITCH</td><td>飞行指引-俯仰角</td><td>DEG</td></tr><tr><td>FLIGHTDIRECTOR-ROLL</td><td>飞行指引-滚转角</td><td>DEG</td></tr><tr><td>FLIGHTPATHANGLE</td><td>飞行航迹角</td><td>DEG</td></tr><tr><td>GROUND SPEED</td><td>地速</td><td>KT</td></tr><tr><td>INDICATEDAOA</td><td>迎角指示</td><td>DEG</td></tr><tr><td>MACHNUMBER</td><td>马赫数</td><td>M</td></tr><tr><td>PITCHATTITUDE</td><td>俯仰角</td><td>DEG</td></tr><tr><td>PITCHATTITUDERATE</td><td>俯仰角速率</td><td>DEG/SEC</td></tr><tr><td>ROLLATTITUDE</td><td>滚转角</td><td>DEG</td></tr><tr><td>STABILIZERPOS</td><td>水平安定面位置</td><td>DEGRVDT</td></tr></table></body></html>

<html><body><table><tr><td>TOTALAIRTEMPERATURE</td><td>大气总温</td><td>DEG C</td></tr><tr><td>VERTICALSPEED</td><td>垂直速度</td><td>FT/MIN</td></tr></table></body></html>

其中，俯仰角(PITCH ATTITUDE)为预测参数，其余数据为训练参数。

样本构造方式如图5所示。将归一化的数据按照时间进程依次排列，组成二维数据矩阵形式，以滑动窗口截取方式构造训练集，其中预测标签为 $N$ 时刻之后预测参数 $y$ 的值，如图5中的 $y _ { 1 }$ 、 $y _ { 2 }$ 。考虑到本实验为一个时间序列预测任务，为保证预测参数在时间进程上的连续性，故选取步长 $s = 1$ ；同时，为便于CNN做卷积操作，选取与训练参数个数相同的滑动窗口大小，即 $w = 2 1$ ，故每个样本为一个 $2 1 \times 2 1$ 的方阵。同时，为检验模型单步预测与多步预测的性能，分别选取 $N = 1 , 5 , 1 0$ 并按上述方式构造样本得到数据集 $S _ { \mathrm { 1 } }$ 、 $S _ { 2 }$ 、 $S _ { 3 }$ 。

![](images/6e96d59efc8f78903e92a4f8849540794c22b8138cca162892b542ae85c17187.jpg)  
图5样本构造方法  
图6各模型结构和参数

$S _ { \imath }$ 、 $S _ { 2 }$ 、 $S _ { 3 }$ 中训练集、验证集、测试集样本划分情况如表2所示。

表2数据集划分  

<html><body><table><tr><td></td><td>训练集</td><td>验证集</td><td>测试集</td></tr><tr><td>S</td><td>14144</td><td>3537</td><td>500</td></tr><tr><td>S</td><td>14141</td><td>3536</td><td>500</td></tr><tr><td>S</td><td>14137</td><td>3535</td><td>500</td></tr></table></body></html>

# 3.2实验与结果

为验证所提双通道融合模型的有效性，在基于TensorFlow的Keras 深度学习平台上实现该模型。并与单一的LSTM 与CNN模型在数据集 $S _ { \mathrm { 1 } }$ 、 $S _ { 2 }$ 、 $S _ { 3 }$ 上分别做对比实验。各模型结构参数如图6所示。

(2.1个   
一一 (？,1) r8 11 一 CTid   
1 (？,32) Dense(32) 一 Dense (1)   
11 (?,1,50) 1 (2.1↑ Dropout (0.2) Attention 1 Dense(32)   
1 (？,21) (？,21,50 1 sigmoid 个 Dense(1)   
1 Dense (21) LSTM_Hidden Flatten   
一 Flatten (50) Dropout (0.2) 最大池化(2)   
1(?,3,16) 最大池化(2) (2,21,21右通道 Dense (32) Conv1D(16,3) (?,1,50)   
I(?,7,16) Conv1D(16,3) LSTM(50) 最大池化(2)   
(?,9,32) 最大池化(2) ！(,21.2D↑ Conv1D(32,3)   
(,19,32) Conv1D(32,3) 一 (?,21,21 一   
1 (?,21,21)左通道 1 CNN-LSTM模型 LSTM模型 CNN模型 一

以数据集 $S _ { 1 }$ 为例，数据输入形式是一个三维的张量(?,21,21)，？表示每批次训练送入样本的数量。

在CNN-LSTM模型中，左(CNN)通道的数据先经过一维卷积层(Conv1D)，含有 32 个 $1 \times 3$ 的卷积核，激活函数为Relu 函数，此时张量形状变为(?,19,32)；再经过一个窗口为2的最大池化层(Maxpooling1D)，张量维度变为(?,9,32)；然后经过含有16个 $1 \times 3$ 卷积核的卷积层，张量维度变为(?,7,16)；再经过窗口为2的最大池化层，张量维度变为(?,3,16)；最后由Flatten 层将数据“压平”，并经过输出维度为21的全连接层(Dense)，此时张量维度为(?,21)。右(LSTM)通道的数据经一个输出维度为50的LSTM单元，并取其隐含层输出，得到一个(?,21,50)的张量。将两个通道张量由按式(9)实现的Attention层融合，张量形状变为(?,1,50)，得到数据的融合特征表达。再通过输出维度为32的全连接层，并施加Dropout层，防止过拟合，最后由输出维度为1的全连接层激活输出，激活函数为Sigmoid。

LSTM 模型与CNN-LSTM 右通道类似，输入数据经由一个输出为50维的LSTM单元，但只取其隐含层最后的输出，输出张量维度为(?,1,50)，之后的处理方式与CNN-LSTM 模型Attention层后的类似。CNN模型与CNN-LSTM左通道类似。

为衡量模型性能，参考相关文献[16]，采用平均绝对误差（MAE）、平均绝对百分比误差（MAPE）、均方根误差（RMSE）、均方根对数误差（RMSLE）作为评价指标，计算公式如式(12)\~(15)所示。

$$
M A E = \frac { 1 } { n } \times \sum _ { t = 1 } ^ { n } \bigl | A _ { t } - F _ { t } \bigr |
$$

$$
M A P E = \frac { 1 } { n } \times \sum _ { t = 1 } ^ { n } \left| \frac { A _ { t } - F _ { t } } { A _ { t } } \right| \times 1 0 0 \%
$$

$$
R M S E = \sqrt { \frac { 1 } { n } \times \sum _ { t = 1 } ^ { n } ( A _ { t } - F _ { t } ) ^ { 2 } }
$$

$$
R M S L E = \sqrt { \frac { 1 } { n } \times \sum _ { t = 1 } ^ { n } ( \log ( A _ { t } + 1 ) - \log ( F _ { t } + 1 ) ) ^ { 2 } }
$$

其中： $A _ { t }$ 为预测值， $F _ { t }$ 为真实值。以上四种指标越小表明预测值越接近真实值，证明模型性能越好、特征表达能力越强。

上述三种模型在三份测试集上的预测结果如图7(a)-(c)所示。误差指标计算如表3所示。

比较图 7(a)\~(c)的结果可知：在数据集 $S _ { \mathrm { 1 } }$ 上，由于是单步预测，预测时间间隔较短，三种模型都能准确预测出俯仰角真实值，CNN模型在第350个点之后开始偏离真实曲线，但总体趋势与真实曲线一致；在数据集 $S _ { 2 }$ 上，预测时间间隔增加到5步，与 $S _ { \mathrm { 1 } }$ 比较，三种模型均不同程度偏离真实值，其中CNN-LSTM模型的偏离程度最小；在数据集 $S _ { 3 }$ 上，预测时间间隔扩大到10步，各模型进一步偏离真实曲线，且整体存在一个滞后效应，在第 450个点之后，CNN与LSTM均存在偏离真实趋势的震荡，只有CNN-LSTM 模型与真实曲线趋势保持一致。同时，表3中误差计算结果表明：CNN-LSTM在数据集 $S _ { 1 }$ 与 $S _ { 2 }$ 上四种误差指标均明显优于CNN于LSTM；在 $S _ { 3 }$ 上，

CNN-LSTM与LSTM性能接近，在MAE指标上两者持平，在MAPE 指标上,LSTM要稍好于CNN-LSTM;在三份数据集中，LSTM均好于CNN，说明LSTM比CNN更适合处理时间序列数据。结合各项评价指标，在单步预测上：CNN-LSTM比CNN误差平均降低 $6 9 . 8 \%$ ，比LSTM误差平均降低 $3 8 . 2 \%$ ；在五步预测上：CNN-LSTM比CNN误差平均降低 $5 1 . 0 \%$ ，比LSTM误差平均降低 $3 3 . 1 \%$ ；在十步预测上：CNN-LSTM比CNN误差平均降低 $1 9 . 6 \%$ ，比LSTM误差平均降低 $1 . 5 \%$ ；综合而言，CNN-LSTM单步预测与多步预测误差比单一CNN与LSTM平均降低 $3 5 . 3 \%$ 。

![](images/880f36c683e536d195180d0ccd7b4dfb7351f2a20ea41dec1df26601e5f7879e.jpg)  
(a) $S _ { \mathrm { 1 } }$ 预测结果

![](images/ff4f6a3f60f710417d946741ea194539f3eb975dc8492622bf53ef390cbcb069.jpg)  
(b) $S _ { 2 }$ 预测结果

![](images/28ec5070cf1df5a85f5332a9fcbca47bc967352e2ac0166d82ab16a6df9e0371.jpg)  
图7各模型预测结果对比

表3误差对比结果  

<html><body><table><tr><td></td><td></td><td>MAE</td><td>MAPE</td><td>RMSE</td><td>RMSLE</td></tr><tr><td rowspan="2">S</td><td>CNN</td><td>0.021</td><td>15.6%</td><td>0.026</td><td>0.023</td></tr><tr><td>LSTM</td><td>0.009</td><td>9.0%</td><td>0.012</td><td>0.011</td></tr><tr><td rowspan="5">S</td><td>CNN-LSTM</td><td>0.006</td><td>6.1%</td><td>0.007</td><td>0.006</td></tr><tr><td>CNN</td><td>0.029</td><td>21.2%</td><td>0.035</td><td>0.031</td></tr><tr><td>LSTM</td><td>0.021</td><td>16.5%</td><td>0.025</td><td>0.022</td></tr><tr><td>CNN-LSTM</td><td>0.013</td><td>11.5 %</td><td>0.017</td><td>0.015</td></tr><tr><td>CNN</td><td>0.041</td><td>27.0%</td><td>0.051</td><td>0.044</td></tr><tr><td>S</td><td>LSTM</td><td>0.033</td><td>22.1%</td><td>0.042</td><td>0.036</td></tr><tr><td></td><td>CNN-LSTM</td><td>0.033</td><td>22.4%</td><td>0.040</td><td>0.035</td></tr></table></body></html>

上述实验结果表明：所提融合方式能够结合CNN与LSTM各自的特点，更加完备的从QAR数据中提取特征。

# 4 结束语

QAR数据的有效分析与利用对提高航班运行效率、保障飞行安全显得尤为重要，受限于QAR数据高维、海量的样本特性，传统特征提取方式难以适用，目前对QAR数据的分析主要集中在统计分析上。本文提出一种基于深度学习的双通道融合模型CNN-LSTM，模型将CNN与LSTM以Attention 的方式结合，使得模型能够更完备地提取QAR数据的特征，从而为QAR数据提供一种更为有效的利用方法。通过对飞行过程中俯仰角参数的预测表明：CNN与LSTM二者结合起来的融合模型在特征表达上比单一模型更有效，单步预测与多步预测精度更高。同时，本文介绍了一种适合工业大数据的数据集构造方式，通过选取不同的窗口大小、步长、时间间隔以适应不同的实际问题。本文为后续开展基于QAR数据的故障诊断等提供了一种新的研究思路。

# 参考文献：

[1]耿宏，李萍萍.QAR 数据处理在气动力矩参数辨识中的应用[J].航空 电子技术,2012,43 (03): 25-29.(Geng Hong,Li Pingping.Application of QAR data processing in aerodynamic moment parameter identification [J]. Avionics Technology,2012,43(03): 25-29.)   
[2] 鞠建波，胡胜林，祝超，等．基于深度学习的装备故障诊断方法[J]. 电光与控制,2018,25(02):103-106.(Ju Jianbo,Hu Shenglin,Zhu Chao, et al.A deep learning based method for equipment fault diagnosis [J]. Electronics Optics &Control,2018,25(02): 103-106.)   
[3]Hinton G E, Osindero S,Teh YW.Afast learning algorithm for deep belief nets [J]. Neural Computation,2006,18(7): 1527-1554.   
[4] 张军阳，王慧丽，郭阳，等．深度学习相关研究综述[J/OL].计算机应 用研究,2018,35(7).[2018-03-21].htp://kns.cnki.net/kcms/detail/51. 1196.tp.20170818.1709.084.html.(Zhang Junyang,Wang Huili,Guo Yang,et al. Review of Deep Learning [J/OL]，Application Research of Computers，2018，35（7）．[2018-03-21].htp://kns.cnki. net/kcms/detail/51.1196.tp.20170818.1709.084.html.)   
[5] 任浩，屈剑锋，柴毅，等．深度学习在故障诊断领域中的研究现状与挑 战[J].控制与决策,2017,32(8):1345-1358.(Reng Hao,Qu Jianfeng, Chai Yi,et al.Deep learning for fault diagnosis: The state of the art and challenge [J].Control and Decision,2017,32(8):1345-1358.)   
[6]Jiang Hongkai, Shao Haidong,Chen Xinxia,et al. Aircraft Fault Diagnosis Based on Deep Belief Network [C]// Proc of International Conference on Sensing,Diagnostics,Prognostics,and Control. 2017:123-127.   
[7]Zhang Yongzhi, Xiong Rui,He Hongwen,et al. A LSTM-RNN method for the lithuim-ion battery remaining useful life prediction [C]// Proc of Prognostics and System Health Management Conference.2017:1-4.

[8]Hochreiter S,Schmidhuber J.Long Short-term memory [J].Neural

Computation,1997,9(8):1735-1780.   
[9]Qu Xingyu,Zeng Peng,Fu Dongdong，et al.Autoencoder-based fault diagnosis for grinding system [C]//Proc of Chinese Control and Decision Conference.2017:3867-3872.   
[10] Chen Zhiqiang,Li Chuan,Sanchez R V.Gearbox fault identification and classification with convolutional neural networks [J].Shock & Vibration, 2015,2015 (2): 1-10.   
[11]Lecun Y,Bottou L,Bengio Y,et al.Gradient-based learning applied to document recognition [J].Proceedings of the IEEE,1998，86 (11): 2278-2324.   
[12] Jia Feng,Lei Yaguo,Lin Jing,et al.Deep neural networks:a promising tool for fault characteristic mining and intelligent diagnosis of rotating machinery with massive data [J].Mechanical Systems & Signal Processing, 2016,72-73:303-315.

[13] Zhang Qingchen,Yang L T, Chen Zhikui.Deep computation model for

unsupervised feature learning on big data [J].IEEE Trans on Services Computing,2016,9 (1): 161-171.   
[14] Bahdanau D,Cho K,Bengio Y. Neural machine translation by jointly learning to align and translate [J]. Computer Science,2014.   
[15]徐军．飞行控制系统：设计、原型系统及半物理仿真实验[M].北京： 北京理工大学出版社，2015.(Xu Jun.Flight Control System:Design, Prototype and Semi Physical Simulation Experiment [M]. Beijing: Beijing Institute of Technology Press,2015.)   
[16]张承钊．一种金融市场预测的深度学习模型:FEPA模型[D]．成都：电 子科技大学，2016.(Zhang Chengzhao.A Deep Learning Model for Financial Market Forecasting:FEPAModel[D].Chengdu:University of Electronic Science and Technology of China,2016.)