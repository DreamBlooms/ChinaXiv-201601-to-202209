基金项目：国家自然科学基金项目(51707196)。

Funding: This work is supported by National Natural Science Foundation of China (No.51707196).

# 深度学习在低频非侵入式负荷分解中的应用与比较

李一鸣1，巨云涛1，瞿李傲1(1.中国农业大学信息与电气工程学院，北京100083)

摘要：非侵入式负荷分解能够充分解析用户用电数据，是分析评估用户柔性调控潜力的关键技术。鉴于深度学习方法在负荷分解的广泛应用，首先深入探讨了降噪自编码器、循环神经网络、卷积神经网络等主流深度学习网络结构应用在负荷分解问题时的工作机理，并对它们在负荷分解领域中的应用与发展进行了展望分析；之后，提出了基于不同维度的分解算法评价框架，并补充了评价过程中测试数据的选择规范；最后，利用该评价框架对主流的深度学习分解模型进行评价，并对模型代码进行了开源，评价结果证明所提框架更能综合地评价给定超参设置下的深度学习分解模型，并揭示模型性能关于网络结构、特征输入等因素的敏感性。

关键词：深度学习；非侵入式负荷分解；卷积神经网络；循环神经网络；用电大数据

# 0 引言

非侵入式负荷监测(Non-intrusive LoadMonitoring，NILM)，最早由Hart于20世纪80年代提出[1，是指在居民用电入口处安装智能电表，经过一系列数据挖掘步骤，将总负荷信息表征为各独立设备的用电情况。通过这种方式获得的终端数据可为用户提供反馈信息，提升家庭的节能意识[2.3]，并为需求响应[4]提供数据支撑。

负荷分解是NILM的核心问题[5]。传统的负荷分解算法大多基于负荷事件探测，以组合优化(Combination Optimization,CO)[6]、聚类匹配[7]为主，但由于负荷印记重叠、难以处理功率连续变化电器等问题的存在，分解精度较低。因子马尔可夫(FactorialHiddenMarkovModel,FHMM)、深度神经网络等模型可以有效地提升分解精度，成为解决负荷分解问题的主流算法[8]。

FHMM族模型依赖较少的监督信息即可达到一定的分解精度。文献[9]将家用电器的使用模式作为附加特征，分别基于四种不同的FHMM建立分解模型，文献[10]通过对信源的信号约束，将FHMM的推断问题转化为凸二次规划问题进行求解。然而，受限于马尔可夫链的性质，FHMM族模型无法对功率连续变化及未知电气设备进行建模，且解码的时间复杂度随设备数目呈指数级别增长，这些都限制了FHMM 族模型的应用[11]。

理论上，深度学习通过加深神经网络可以实现对任意物理模型的近似[12]。文献[13]利用双向长短期记忆(Bidirectional Long Short Term Memory, Bi-LSTM）、降噪自编码器（Denoising AutoEncoder,DAE)等深度学习模型为设备功率建模。相较于传统方法，深度学习方法具有：i.无需进行人工特征提取ii.算法复杂度随电气设备数量增加呈线性增长iii.可以对功率连续变化的设备进行建模，并忽略未知设备的影响iv.可利用GPU并行计算等天然优势[14]。

然而，深度学习模型参数众多、解释性差、对超参的选择敏感，因而揭示网络结构背后的工作机理对于算法设计、参数调整等尤为重要。同时，由于测试数据与评价指标选取的不同，研究者们难以系统地比较分解算法的优劣[15]，找出模型表现欠佳的原因，并有针对性地改进分解算法。

基于非侵入式负荷分解领域的研究现状，本文首先探讨了降噪自编码器、循环神经网络(RecurrentNeuralNetwork,RNN)、卷积神经网络(Convolutional Neural Network,CNN)三大主流网络应用于负荷分解问题的工作机理，指出Bi-

LSTM层对有效负荷信息的双向编码及卷积层对不同负荷事件的抽取是深度学习模型应用的关键。之后，提出了考虑不同维度的负荷分解算法评价框架，并从数据集与待测电器两方面对测试数据的选择做出规范。最后，利用该评价框架对主流的深度学习分解算法做出评价，揭示了不同模型性能的差异主要源于网络结构对不同负荷信息建模的侧重不同，之后通过算例分析说明了输入特征等因素对于模型分解性能的影响，并对改进算法提出了意见。此外，本文还对模型实现及评价的代码进行了开源(https://github.com/Ming-er/NeuralNILM_Pytorch）。

# 1深度学习模型在负荷分解中的工作机理

负荷分解要求将一段时间序列的总负荷信息表示为相应组成信号的线性组合，对于序列当中的一个时间节点，负荷分解问题可以被抽象成如下的数学形式：

$$
y _ { t } = \sum _ { i = 1 } ^ { I } x _ { i , t } + u _ { t } + { \dot { 0 } } _ { t }
$$

式中： $y _ { t }$ 代表 $t$ 时刻的总功率， $x _ { i , t }$ 为第 $i$ 个电气设备在 $t$ 时刻的功率， $\boldsymbol { u } _ { t }$ 为未知电气设备在 $t$ 时刻的总功率， $\dot { \phi } _ { t }$ 为随机噪声，满足 ${ \dot { \mathbf { o } } } _ { t } \sim N \left( 0 , \sigma ^ { 2 } \right)$ ， $I$ 代表电气设备的数量。

考虑到神经网络对端到端映射强大的表征能力，深度学习模型通常直接学习一段时间内总功率序列与第 $i$ 个电气设备功率序列间的映射关系（204号 $f : [ y _ { t + 1 } , y _ { t + 2 } , \cdots , y _ { T } ] \in \varTheta \mid _ { + } ^ { T } \to [ x _ { i , t + 1 } , x _ { i , t + 2 } , \cdots x _ { i , T } ] \in \varTheta \mid _ { + } ^ { T }$ ”而不需要考虑用户不感兴趣的电气设备及其它未知电气设备对分解效果的影响。深度学习模型多采用如下形式定义问题，

$$
y _ { t } = x _ { i , t } + o _ { i , t } + \partial _ { t }
$$

式中： $o _ { i , t }$ 为除第 $i$ 个电气设备以外其它电气设备在 $t$ 时刻的功率。

目前，应用在负荷分解领域的深度学习模型以降噪自编码器、循环神经网络、卷积神经网络等网络为主。

# 1.1 DAE类模型

DAE接受含噪声的数据作为输入，并将其重构为原始不含噪声的数据输出[16]，在图像去噪、语音增强等领域有着广泛的应用[17,18]。在负荷分解问题中，总功率序列与其它序列(时间戳信息[19]及无功功率等电气特征[20]可作为补充的语义背景，辅助模型更好地理解负荷信息)可以被看作DAE的输入，待预测独立电气设备的功率序列被视作DAE的输出，而其它电气设备在同时段的功率则被作为模型需要消除的噪声。

![](images/493643046b69e28c639d0b2fe33fa85f69d4dbfdfda5d907cc028e0bffea7d5d.jpg)  
图1DAE类模型基本结构示意图 Fig.1Schematicdiagramof thebasic structureof the DAE models

图1是DAE类模型的基本结构示意图，其网络结构可分为编码器、解码器两个部分。其中，编码器对输入特征进行特征提取与组合，并将其压缩成一个紧凑表达形式一一瓶颈层，而解码器则需要根据瓶颈层所蕴含的信息对特定电器设备的功率序列进行重构。DAE对重构损失的梯度优化限制了瓶颈层特征蕴含总功率序列中利于重构当前电器功率的信息，也提升了之后解码器的解码能力。

文献[13]最早将DAE应用于负荷分解，得到的分解效果优于CO、FHMM等传统方法，但由于网络结构较为简单，并未真正体现出DAE模型的优势。随后，文献[20-22]尝试将DAE 网络加深，并在编码、解码过程中添加了卷积、归一化、残差连接等设计，进一步提升了DAE 模型的分解精度。

![](images/29db2a2a0d813be352d81c61ecd6c9429fe9463f1c0edbb014faa3865c88478d.jpg)  
图2将GAN融入负荷分解模型 Fig.2 Traininga GAN that maps main readings to target individual appliance readings.

近些年来，随着生成对抗网络[23](GenerativeAdversarialNetwork,GAN)的兴起，许多研究[24-27]尝试将GAN 融入DAE 模型对负荷编码、解码的过程，其基本思想如图2所示。这种方式的优势在于不改变DAE模型的结构，而是引入判别器对其预测的输出序列进行真假判别，并通过优化判别所产生的判别损失来逐次更新DAE与判别器使其对抗制约，在提升判别器分辨能力的同时，也可以使得DAE的输出更加接近真实值。

# 1.2 RNN类模型

RNN是一类以序列数据为输入，在序列的演进方向进行递归且所有节点按链式连接的递归神经网络[28]，在时间序列建模中被广泛使用。其中，较为典型的模型是长短期记忆[29](Long ShortTermMemory,LSTM)与门控循环单元[30] (GatedRecurrentUnit,GRU)，它们解决了传统RNN梯度消失的问题，使得RNN可以把握功率序列中间隔较长的时间依赖关系，并对负荷数据前后的关联信息做出记忆与判断，如功率序列中时间间隔较长的负荷事件等。

![](images/f8105ccc151ae29d853f900a1dc04958c0ee22509babbaa647357815cba5e6bb.jpg)  
图4LSTM细胞工作原理示意图

图3是RNN类模型的基本结构示意图，以Bi-LSTM为主要组成，图4是LSTM细胞工作原理图，模型的工作过程可分为编码、解码两个主要过程。首先，Bi-LSTM层接收输入窗口内的序列特征，并按照正、反两个方向对其中的负荷信息与语义背景进行信息组合与编码传递：与待分解时间点相关联的有效信息被传递给后一个LSTM细胞，不相关联的无效信息则被丢弃，正反两个方向的信息传递可以进一步地增强模型对负荷事件之间因果关系的推理能力。随后，LSTM隐藏状态所记住的有效编码信息被最后的全连接层整合归纳，最终解码得到相应时段的电器功率序列。

文献[13,31]最早将RNN应用在负荷分解问题其为每个用电器构建了较为原始的LSTM模型，使模型能够学习总功率序列到电器功率序列的映射关系，文献[32]将结构更为简单的双向门控循环网络(Bidirectional Gated Recurrent Unit, Bi-GRU)模型应用于负荷分解，并利用滑动窗口来预测总功率序列中间时间点所对应的用电器功率。

![](images/3e02c77bf40af2643002ac46f0a7c27e6bfa24ee07fd7f58f21e0ee0d979c6df.jpg)  
Fig.4 Working principle diagram for LSTM cell

随后，对RNN类模型应用的研究开始着重于提升模型编码、解码的能力，以进一步优化模型性能。文献[33]在Bi-LSTM上游加入了不同尺寸的平行卷积核进一步增强了模型对负荷数据特征的抽取能力，使得负荷信息在编码前得到了有效的过滤。文献[34]与文献[35]都对连续的功率信息进行了人为的离散编码，并结合序列翻译的序列到序列(Sequence-to-Sequence,Seq2Seq)模型进行训练,同时，文献[34]在解码过程中采用了Attention 机制，使得模型对负荷信息解码的不同时刻有不同的侧重，提升了对负荷信息的利用能力。文献[36]考虑到特定电器经常工作在特定时段，将负荷数据的时间戳编码到Bi-GRU模型中。

同时，也有许多研究尝试从整体上优化RNN类模型。文献[37]利用参数权重共享的Bi-GRU进行多任务学习，同时学习电器的开关状态及功率消耗情况，在推断时相较于只学习功率变化模式的分解模型对噪声具有更好的鲁棒性。文献[38]针对[13]中Bi-LSTM模型训练时可能出现的过拟合问题给出了正则化的方式，文献[39,40]则分别利用贝叶斯优化及TPE算法给出了Bi-LSTM模型超参数的较优选择策略，使得模型对于现实问题的适应性得到了增强。

![](images/d820a0f1005afe24227d32d9f997cb34d0be746b561daf1be4cd049a76321281.jpg)  
图3RNN类模型基本结构示意图  
Fig.3Schematic diagramof the basic structureof theRNN models   
图5CNN类模型基本结构示意图  
Fig.5 Schematic diagram of the basic structure of the CNN models

# 1.3 CNN类模型

CNN是一类由卷积层、池化层为主要组成的前馈神经网络，由于卷积运算的特性，神经元可以响应一部分覆盖范围内的周围单元，因而CNN对局部特征有较强的抽取能力，如功率序列中某个时间点正在发生的负荷事件等。CNN在句法分析[40]、文本分类[41]等序列建模任务中有着广泛应用，研究表明，CNN对于某些时序数据的表达能力要胜过RNN[42]。

图5是CNN类模型的基本结构示意图，以尺寸不同的卷积核为主要组成。一维卷积层对输入窗口内的序列信息进行特征提取：不同层内，尺寸不同的卷积核探测不同时间尺度的负荷事件；同一层内，不同通道的卷积核则探测不同强度(功率变化幅值大小)的负荷事件；附加的序列特征类似于图像的背景像素，可作为语义信息被卷积核一起捕捉，靠前的卷积层感受野较小，通常只能把握序列的简单变化模式，但具有较高的分辨率，靠后的卷积层则可以对这些简单模式进行组合，学到更为复杂的负荷特征及语义信息。最后的全连接层对之前卷积层所探测到的负荷特征进行信息整合，并输出最终的电器功率序列。

文献[43]利用多个不同尺寸的卷积核与顶端的全连接层搭建了序列到点(Sequence-toPoint,Seq2Point)模型，并对卷积核进行了可视化，说明了不同通道的卷积核对不同的负荷事件有着不同的激活程度。

之后的许多研究开始对CNN的这一特性加以利用，文献[44]根据CNN 所提取的负荷特征判断回归网络所产生的功率序列是否属于当前电器，文献[24,45]构建了门控分支网络，一个卷积网络用于输出电气设备的开关状态，另一个卷积网络用于预测电气设备的功率值，两个网络输出的哈达玛积被作为最终的预测结果。它们的研究都是希望利用CNN对负荷事件的辨识能力产生额外的信息流，抑制假阳性样本的出现，以此提高负荷分解的准确性。

对于CNN类模型性能优化的研究主要集中在提升卷积核对负荷事件的探测能力。文献[46]在[43]研究的基础上提出了卷积块注意力机制，从通道维、空间维两方面定义卷积特征的重要程度，使得模型对于中间特征的把握更有侧重；文献[46]借鉴了音频生成网络WaveNet[47]扩张卷积、跳层连接等设计思想，构建的WaveNILM网络拥有更大的感受野，对长期负荷事件有了更强的把握能力；文献[48]借鉴了图像分割网络U-Net[49]多分辨率特征融合的设计思想，构建的U-NetNILM网络可以兼顾长短期负荷事件；文献[50-52]都将负荷信号建模为二维图像，类比卷积神经网络对图像局部特征的学习能力构建了负荷分解模型。

# 2负荷分解算法评价框架

本节首先提出比较负荷分解算法的评价框架，然后对其中的具体细节进行说明，评价框架的流程图如图6所示。

![](images/8184d56b62a958a8131172798f43856f8d38ce9a93df32ed1e05112aa0d7a680.jpg)  
图6负荷分解算法评价框架流程图  
Fig.6Flowchart of the proposed evaluation framework of energy disaggregation algorithms

从上述流程图中可以看出，本文所提出的评价框架涉及多个维度的比较，这些评价维度的选取都是基于综合比较负荷分解算法而设定的。

在训练过程中，预先评估模型训练、部署、应用时的时空效率。训练效率直接影响着迭代开发时的训练成本，同时决定了一个负荷分解算法能否通过数据增广扩展到更复杂的现实场景。同时，随着边缘计算物联网架构在电力领域得到部署应用[53]负荷分解模型未来将广泛存在于嵌入式终端，模型的空间复杂度将直接影响模型的部署难度。此外，模型分解的计算效率也决定着嵌入式终端能否给予用户实时的信息反馈。

在相同的场景下对模型进行测试，主要考虑模型的辨识准确性与回归准确性。辨识准确性与模型对负荷事件的判断息息相关，在异常检测、环境辅助生活等领域有着重要的应用，回归准确性主要考察功率分解值的准确度，以向用户提供及时准确的功耗信息，辅助决策者进行决策，这也是非侵入式负荷分解非常关注的数值特征。

在不同的场景下对模型进行测试，可以比较分解模型的泛化性能。泛化性能的考察是必须的，在现实生活中，获得独立电器设备负荷信息的代价是巨大的，这也正是非侵入式负荷分解相较于侵入式负荷分解的优势所在。泛化性能的好坏反映了一个分解模型在有限的训练数据中提取了足够有效的负荷特征信息，还是只记住了数值变化的简单模式，这直接决定了一个负荷分解模型能否在现实生活中得到广泛应用。

值得注意的是，本文所提出的评价框架是对负荷分解算法的一种综合性评价流程，实际操作时，研究者可以自行根据模型的应用范畴有针对性地进行相应的删改与侧重。

# 2.1评价指标选择

# 2.1.1 模型预评估

# I．训练效率

为了衡量分解模型的训练效率，本文选择了模型训练收敛的平均时间t作为主要评价指标。t越小的模型，相应地在学习与参数调整上花费的时间也越少，可以认为其对待解决问题具有更强的适应性，同时，也可以减少算法研究的迭代成本。

# ⅡI．部署难度

为了衡量分解模型的部署难度，本文选择了模型参数所占用内存大小 $\mathbf { \Sigma } _ { m }$ 作为主要评价指标。 $\mathbf { \Sigma } _ { m }$ 越小的模型，相应地更容易部署在嵌入式终端。

# III．实时应用

为了衡量分解模型的实时性，本文选择了模型的平均推理速度 $\mathbf { \sigma } _ { \nu }$ 作为主要评价指标。 $\mathbf { \Lambda } _ { \nu }$ 越大的模型对于电器负荷信息有着更好的实时反馈能力。特别地，在3.3.1的推理速度比较中，本文采用模型分解一月负荷所需的时间定量估计模型的推理速度。

# 2.1.2 辨识准确性

为了衡量负荷分解模型的辨识准确性，本文参考相关的统计学习理论及研究[54-56],选取了召回率recall、准确率precision、马修斯相关系数3个指标作为辨识准确性评估的参数，指标的具体计算方式如下：

$$
| \mathrm { R e c a l l } = \frac { \mathrm { T P } } { \mathrm { T P } + \mathrm { F N } }
$$

$$
\mathrm { P r e c i s i o n } = { \frac { \mathrm { T P } } { \mathrm { T P } + \mathrm { F P } } }
$$

$$
\mathrm { M C C } = { \frac { \mathrm { T P } \cdot \mathrm { T N } - \mathrm { F P } \cdot \mathrm { F N } } { { \sqrt { \left( \mathrm { T P } + \mathrm { F P } \right) \cdot \left( \mathrm { T P } + \mathrm { F N } \right) \cdot \left( \mathrm { T N } + \mathrm { F P } \right) \cdot \left( \mathrm { T N } + \mathrm { F N } \right) } } } }
$$

式中：TN代表真阴性样本，即用电器实际未处于工作状态且算法分解结果也为不工作的时间戳个数；TP代表真阳性样本，即用电器实际处于工作状态且算法分解结果也为该工作状态的时间戳个数；FN代表假阴性样本，即用电器实际处于工作状态但算法分解结果为不工作的时间戳个数；FP代表假阳性样本，即用电器实际未处于工作状态但算法分解结果为工作状态的时间戳个数。recall为召回率，即阳性样本被预测正确的比率；precision为准确率，即做出阳性样本判断的正确率；MCC为马修斯相关系数，其值介于-1到1之间，越接近于1说明算法的辨识性能越好。

在以上三个指标中，MCC相较于以往研究常采用的F1分数对于不平衡二分类问题的评估具有更好的鲁棒性[57]，而这与电器负荷事件的稀疏性[58]天然适应。但与此同时，保留召回率与准确率作为评价指标可以指出分解模型的潜在问题在哪里，比如召回率较大而准确率较小的模型可能倾向于认为一个用电器有较大概率处于开启状态，尽管事实并非如此，这启发研究者们通过调整正负样本的比例等方式来改进分解模型的辨识性能。

# 2.1.3 回归准确性

为了衡量负荷分解模型的回归准确性，本文参考相关实验及理论[54-56]，选取了平均绝对误差MAE、归一化误差NEP、开启时平均绝对误差OMAE等3个指标作为回归准确性评估的参数，指标的具体计算方式如下：

$$
\mathrm { M A E } = \frac { 1 } { T } \sum _ { t = 1 } ^ { T } \left| \hat { \boldsymbol { p } } _ { t } - \boldsymbol { p } _ { t } \right|
$$

$$
\mathrm { N E P } = \frac { \displaystyle \sum _ { t = 1 } ^ { T } \Big | \hat { p } _ { t } - p _ { t } \Big | } { \displaystyle \sum _ { t = 1 } ^ { T } p _ { t } }
$$

$$
\mathrm { O M A E } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \left| \hat { e } _ { i } - e _ { i } \right|
$$

式中： $p _ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻电器的真实功率， $\hat { p } _ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻模型分解得到的电器功率， $T$ 为测试序列的时间长度，$e _ { i }$ 为电器开启状态下第 $i$ 个时间戳的真实功率， $\hat { e } _ { i }$ 为电器开启状态下第 $i$ 个时间戳模型分解得到的电器功率， $N$ 为测试序列中电器开启状态的时间长度。

值得注意的是，以往的实验通常只选择MAE作为回归准确性的评价指标，这事实上并不能很好地反应模型的分解性能，只需要简单地将每一时刻的功率都预测为0，便可以使许多小功率用电器的MAE达到一个较小的值，对此，本文建议采用归一化误差NEP来消除这个影响。同时，如果只使用MAE与NEP，许多不常使用的家用电器的回归误差也会因为测试序列的时间长度T较大的基数而被平滑，着重于评估用电器开启时分解效果的OMAE可以较好地解决这一问题。

# 2.1.4 泛化性能

泛化性能的考察一直是负荷分解乃至深度学习领域的开放性问题[59]。文献[59]提出了负荷分解模型泛化性能损失的概念，但它只衡量模型在不可见场景相较于可见场景性能的下降程度，忽略了模型可能在可见场景下表现较差这一问题。迁移学习领域的研究[60][61]大多直接考虑模型在目标域(即未见场景下)的性能，因此，本文也建议研究者们在比较不同模型的泛化性能时计算分解模型在未见场景下的MCC、MAE等指标，并与可见场景下的指标结果进行比较。

# 2.2现有公开测试数据分析

在进行负荷分解算法评价时，测试数据的选择同样会对评价的准确性与全面性产生影响。不同数据集由于属性上的差异可能会使同一分解算法产生差异较大的结果，同时，如果待测电器的选择过于单一，将会对分解算法的表现产生以偏概全的认识。在此，对评价框架中数据集与待测电器的选择做出如下规范。

# 2.2.1 现有数据集特点

为了对不同数据集间的属性差异有一个更加清晰的认识，本文根据文献[60]所提负荷事件统计方法，利用NILMTK框架[61]，对NILM领域的相关数据集做了如下整理，如附录A表A1所示，

从表A1中可以看出，AMPds2[62]、COMBED[63]等数据集由于采样频率较低，容易遗漏一些负荷信息，为负荷分解增加难度；iAWE[64]、REDD[65]等数据集由于数据采集的持续时长过短，难以为一些深度学习模型提供充足的训练数据；同时，日均负荷事件发生数量可以作为家庭用电活跃程度的考察，其值越大，代表负荷事件越密集，负荷事件重叠的可能性也就越大，这也给负荷分解算法提出了更高的要求。综上，本文建议使用UK-DALE[66]、REFIT[67]等数据集评价一般的单特征输入分解算法，对于融合了多种功率类型的多特征输入分解算法[68]则应相应地采用AMPds2、iAWE等数据集进行评估。

# 2.2.2 待测电器选择规范

根据文献[69]，家用电器可按其工作时的功率消耗模式分为以下四类：

表1四类电器设备的功率模式特点及示例  
Table1 Descriptions of four types of equipment   

<html><body><table><tr><td>类别</td><td>功率模式特点</td><td>示例</td></tr><tr><td>Type-I</td><td>工作模式只有开关两种状态的电器</td><td>水壶</td></tr><tr><td>Type-II</td><td>功率在有限离散集合内转换的电器</td><td>洗衣机</td></tr><tr><td>Type-III</td><td>功率在不断连续变化的电器</td><td>钻孔机</td></tr><tr><td>Type-IV</td><td>功率模式呈周期性变化的电器</td><td>冰箱</td></tr></table></body></html>

目前，绝大部分分解算法都能较好地处理Type-I、Type-IV类电器，但是在分解Type-II类电器时，许多算法仍然在状态转换的判断上存在一定缺陷，同时，Type-III 类电器的功率分解依然是NILM领域的难点之一。

为了更加综合地评价负荷分解算法，本文建议所测试的电气设备类型应尽量涵盖以上四类，并特别关注Type-II、Type-III类电器的分解情况。

# 3算例分析

为验证本文提出的负荷分解算法评价框架对于算法评估的有效性，本节利用该框架对于不同网络结构的主流深度学习分解模型进行评价与比较，并探究了输入特征对于模型性能的影响。

# 3.1 实验设定

# 3.1.1 硬件环境及软件平台

实验硬件环境为 $6 \times$ Intel (R) Xeon (R) CPU E5-2678 v3 $@$ $\textcircled { \mathscr { v } } 2 . 5 0 \mathrm { G H z }$ 及GeForceRTX 2080Ti(每秒浮点运算次数为13.13TFLOPS，显卡内存为11GB)的 64 位计算机。软件平台为 python 3.7(64 位）、PyTorch1.7.0深度学习框架及JupyterLab集成开发环境。在训练深度学习模型时使用PyTorch 的GPU 版本，利用 GPU 进行硬件加速[70]。

# 3.1.2 模型选择

实验涉及模型包括文献[13]所提Bi-LSTM模型、DAE 模型、[43]所提 Seq2Point 模型、[45]所提SGN-sp 模型、[46]所提CNN_Attention 模型及[25]所提EnerGAN模型。其中，Bi-LSTM属于RNN类模型，Seq2Point、SGN-sp、CNN_Attention 属于CNN类模型，DAE、EnerGAN属于DAE类模型。网络模型的拓扑结构见附录A图A1-A6。在实际实现过程中，我们对于原始论文中的网络模型进行了改进并收获了更好的分解性能，如对于Bi-LSTM模型，将其第二个Bi-LSTM层输出的所有隐藏状态拼接起来作为全连接层的输入[71]；对于EnerGAN 模型，借鉴大多数pix2pix 任务的思想[72][73],将重建损失融入生成器的训练过程，使其迭代收敛更加稳定等。

更多的网络模型实现细节及相关代码请参考：https://github.com/Ming-er/NeuralNILM_Pytorch。

# 3.1.3实验数据选择及预处理

实验选取了UK-DALE 数据集及冰箱、水壶、洗衣机、微波炉、洗碗机五类电器用以评估实验。其中，水壶、微波炉是典型的Type-I类电器，洗衣机、洗碗机为Type-II类电器，而冰箱则属于Type-IV类电器，上述选择参考了以往负荷分解算法对比工作[43,45,71],待测电器多为研究者们所关注的类别，可以在一定程度上反映不同分解算法对于不同电器适应性的差异。对于特定的电器，保证其在相同场景受测时测试集与训练集无重叠部分，并对总、分电表数据进行下采样，使其采样间隔为30秒，训练场景与测试场景的具体时段划分及各电器设备的输入序列长度见附录A表A2、A3。对于训练数据与测试数据，均对其进行了文献[13]所述的z

score 归一化预处理。

# 3.1.4实验方法及训练设定

实验时，考虑到不同的超参组合对于模型性能的影响，学习率、优化器、初始化方法等均为研究者所推荐使用的参数设定[25,45,46,71]，这些设定由研究者经过大量的数值实验比较得出，可以认为对于不同场景下的负荷分解问题都有较强的适应性。此外，考虑到训练的随机性对于模型性能的影响，实验均换用不同的随机数种子重复进行多次并对评价指标计算均值，以尽可能真实地反映模型性能。最后，为了防止网络模型对可见场景的过拟合，实验设置模型训练的最大迭代次数为200次，并采用早停法控制网络的训练过程，即设置3个迭代周期后模型在验证集损失不下降便停止迭代训练。

# 3.2不同网络结构的深度学习分解模型性能评估

本小节选取了不同网络结构的CNN_Attention、Bi-LSTM、DAE、Seq2Point、SGN-sp、EnerGAN 模型在所提算法评价框架下进行性能评估。模型的输入特征均为有功功率序列 $P$ ，实验依3.1小节所述设定进行，实验过程中模型分解得到的功率曲线见附录B图B1-B5。

# 3.2.1模型预评估

使用2.1.1小节所提评价指标对上述模型进行预评估，结果如附录表A4。可以看出，Bi-LSTM模型的训练、推理用时均较长，这是因为RNN类模型对当前时间步负荷信息编码时需整合前一时间步有效的负荷信息，这样的工作机理使其每一时间步的训练都要在CPU 和GPU 之间来回调度，难以在GPU上很好地并行。得益于卷积操作对负荷特征的并行抽取能力，Seq2Point 模型有着更优的训练、推理效率，CNNAttention 模型虽然在Seq2Point模型的基础上引入了额外的注意力块，但并未明显地影响网络的训练、推理用时及内存占用，而同属于CNN 类模型的 SGN-sp 模型则因其庞大的参数量与分支门控的结构设计有着较大的训练、推理开销。最后，对比同样结构简单的DAE模型，EnerGAN模型较长的训练用时则源于对抗训练的过程。

总体来看，DAE等轻量级网络在模型预评估环节表现较好，而若想将SGN-sp等大规模网络部署到嵌入式终端，则需要通过相关技术压缩网络模型并提高其实时推理速度[72-75]。

# 3.2.2辨识准确性对比

使用2.1.2小节所提评价指标对上述模型进行辨识准确性对比，结果如附录图A6所示。可以看出，上述模型对于开关变化模式较为简单的水壶、冰箱两类电器辨识的MCC指标都达到了0.75以上，但对于同属于type-I类电器的微波炉，网络辨识的召回率Recall较低，这是因为数据集中微波炉的负荷事件极为稀疏，网络更加倾向于预测微波炉出于关闭状态。而对于洗碗机、洗衣机等 Type-II 类电器，除 SGN-sp 模型外，其它模型的辨识精度都有不同程度的下降。此外，Seq2Point、SGN-sp 等 CNN类模型对于 Type-II类电器的辨识准确性优于其他模型，这在一定程度上说明了卷积操作对于功率幅值变化的探测是多时间跨度、多功率尺度的。同时，EnerGAN模型对电器状态的辨识精度要优于DAE模型，这说明判别器的存在可以在对抗训练的过程中纠正模型对于负荷事件的推理。

总体来看，CNN类模型多层次、多尺度的卷积核增强了其对不同持续时长、不同功率变化幅值负荷事件的把握能力。同时，电器种类的不同使不同模型的辨识表现出现了较大差异，说明了对待测电器选择做出规范的必要性。对于辨识精度不高的模型，研究者们可以效仿EnerGAN模型进行对抗学习，以提升模型对于负荷事件的把握能力。

# 3.2.3回归准确性对比

使用2.1.3小节所提评价指标对上述模型进行回归准确性对比，结果如附录图A7所示。单从MAE指标可以看出，SGN-sp等CNN类模型对于用电器的功率预测更为准确，原因在于卷积核擅长提取局部信息并学习功率的不同变化模式，且CNN类模型的辨识准确性较优，而状态辨识与功率预测两个任务间存在较强的相关关系；但从OMAE及附录图B1\~B5的分解曲线来看，Bi-LSTM模型对于电器开启时的功率回归较为准确，这是由于RNN类模型每一时间步都会整合上一时间步的负荷信息，在对负荷信息建模的连续性上更有优势。同时，SGN-sp、CNN_Attention 模型在 Type-I、II、IV 类用电器的分解精度均优于Seq2Point，这说明引入用电器的开关信息流及加权融合卷积中间特征等手段都可以促进网络对电器功率的分解。

此外，如果只依据MAE这一指标进行评价，则会得出“模型在水壶等电器上性能优异”这一错误结论，因为较高的NEP、OMAE指标表明许多模型对电器开启时的功率预测仍有较大误差，这说明本文所提评价框架较以往更为综合全面。

注意到EnerGAN模型对于水壶、冰箱的分解精度不逊于 SGN-sp等模型且具有更少的参数量、更快的推理速度，而Bi-LSTM、SGN-sp 等模型对于功率状态复杂电器的分解更有优势，研究者们可以考虑利用模型对于不同电器设备的适应性，对于不同的电器设备训练不同的模型，并通过模型集成的方式给出最终的分解结果。

# 3.2.4泛化性能对比

对分解算法在不可见场景测试下的MAE、MCC指标整理如图A8所示。可以看出，上述五类深度学习模型在不可见场景下分解水壶、冰箱等用电器相较于可见场景下并未出现明显的泛化性能损失。但是，模型在分解功率模式更为复杂的Type-II类用电器时，其MAE、MCC等指标均出现了不同程度的下降，且网络结构相对更为复杂的SGN-sp等模型指标下降的幅度更为明显。这说明深度学习模型对于Type-II类用电器的泛化性能有待增强，并且越复杂的网络应对不可见场景时的结构风险也越大。研究者们可以考虑通过数据增强[76-78]、迁移学习[79-81]等方式来提升模型的泛化性能，并通过正则化等方法避免复杂网络对可见场景的过拟合。未来，对于模型在不同场景的泛化问题仍然是负荷分解研究的核心。

# 3.3不同输入特征下的深度学习分解模型性能评估

本小节选取了Bi-LSTM、DAE、Seq2Point 模型，在所提算法评价框架下评估了它们在输入特征分别为有功功率序列 $P$ ，有功功率序列 $P$ 及无功功率序列 $\varrho$ ，有功功率序列 $P$ 及视在功率序列 $s$ ，有功功率序列 $P$ 、无功功率序列 $\varrho$ 及视在功率序列 $s$ 时的模型性能，实验依3.1小节所述设定进行。

# 3.3.1模型预评估

使用2.1.1小节所提评价指标对上述模型进行预评估，结果如附录表A5。可以看出，输入特征维数的增加并不会显著地增加模型的时空复杂度,却可以在训练时帮助网络更快地学习收敛。但在实际部署负荷分解网络时，更多的特征维数意味着更大的数据存储需求与传输带宽占用，研究者们可以考虑采取压缩感知[82.83]等技术对多传感器采集得到的数据进行处理，以减小嵌入式终端的运行负荷

# 3.3.2辨识准确性对比

使用2.1.2小节所提评价指标对上述模型进行辨识准确性对比，结果如附录图A9所示。可以看出，当增加一个维度的输入特征时，模型的辨识准确性便可以得到显著提升。具体地，由于视在功率S 的主要成分为有功功率 $P$ ，二者间存在较强的共线性关系，因此使用无功功率 $\varrho$ 作为附加序列特征可使网络学到更为丰富的负荷信息，对于辨识性能的提升也更加明显。此外，当使用 $P$ 、Q、 $S$ 三个输入作为特征有可能造成网络输入的信息冗余，相较于 $P$ 、 $\varrho$ 两个输入作为特征时的辨识性能并没有较大提升。最后，多维特征输入使得模型辨识水壶、微波炉的召回率Recall提升明显，在一定程度上帮助网络克服了负荷事件过于稀疏等问题，而对于洗衣机、洗碗机等运行模式复杂的TypeII类电器，模型辨识的准确率Precision提升显著，说明多维特征的引入强化了模型对于复杂负荷事件的推理判断。

# 3.3.3回归准确性对比

使用2.1.3小节所提评价指标对上述模型进行回归准确性对比，结果如附录图A10所示。从图A10及附录图B6\~B10的分解曲线可以看出，多维特征的引入都显著地提升了模型的分解性能，但是不同特征引入对于不同电器分解效果的提升也不尽相同。此外，多维特征输入模型的OMAE相对较低，说明多维信息的加入可以提升模型对于电器开启时的功率预测精度。

从不同网络间性能及分解曲线的横向对比来看，二维特征输入的轻量级DAE 网络甚至可以取得接近于一维特征输入的Bi-LSTM等复杂网络的辨识、回归准确性，故有效额外特征的引入不失为一种提升模型性能的高效方法。

# 3.3.4泛化性能对比

对分解算法在不可见场景测试下的MAE、MCC指标整理如图A11所示。可以看出，多维特征的引入显著地提升了模型对于冰箱、洗衣机及洗碗机的泛化能力，但是对于水壶、微波炉，多维特征的引入甚至可能会使网络的学习出现负迁移现象。因此，若想通过引入附加特征的方式提升模型的泛化性能，研究者们需要更仔细地考虑可见训练场景与不可见测试场景下不同电器在各个特征维度下的电气特性。

# 4展望

通过上文的讨论中不难看出，目前非侵入式负荷分解领域内的深度学习方法众多，且有不少模型可以达到较高的辨识与分解准确率，但模型在实用性、鲁棒性、泛化性等方面离应用仍有一定差距，未来将深度学习应用至低频非侵入式负荷分解领域可以重点着眼于以下几个方面：

1）边缘计算物联网架构在电力领域逐渐得到部署应用[53]，然而目前基于深度学习的分解模型时空复杂度依然较高，可以通过借鉴模型压缩方向的知识蒸馏[84]、权重剪枝[85]、网络量化[86]、神经结构搜索[87等策略对模型进行压缩处理。此外，边缘计算的嵌入大多依赖于云边协同等技术，边缘节点与云计算中心通信时的数据传输效率、用户隐私保护等问题也亟待解决。

2）目前，对于分解模型泛化性能的评估尚无统一指标，分解算法也大多集中于监督式学习方法，需要海量的标签数据对模型进行训练，而在现实场景中获得用户内部的先验数据难度极大。目前，已有的迁移学习方法依然需要部分目标域数据（用户内部的先验数据)支持训练过程[79-81]，深度学习其它子领域的元学习[88]与零样本学习[89]方法几乎不依赖目标域内的样本，可以极大程度地减少模型对于现实场景的数据需求，为解决负荷分解模型在未见场景的泛化问题提供可行思路。

3）图信号处理通过定义节点和加权邻接矩阵来表示数据集，具有训练时间短、表征能力强等优势，已有研究将其应用于负荷分解问题[90]。近年来，将图信号处理与神经网络相结合的图神经网络[91]可以充分挖掘数据样本间的联系，有效地处理社交网络等图关系型数据。若能将图神经网络应用于负荷分解问题，有望兼有二者的优势，并显著地提升模型的分解性能。此外，将深度学习方法与其它传统方法结合，也可以在克服深度学习方法对标签数据依赖的同时大幅提升传统分解方法的性能。

4)此外，功率序列中长短距离时序依赖的有效把握、不常用设备负荷事件的稀疏性引起的数据集长尾分布、小功率用电器易被同时段大功率用电器覆盖等问题依然是目前限制深度学习分解模型性能进一步提升的瓶颈所在。对于时序建模，能够利用序列全局信息的Transformer架构[92]、动态调整时间窗大小的时间自适应卷积[93]等方法都可以进一步增强深度学习分解模型对于不同时间尺度负荷事件的把握能力；对于稀疏事件，也可以尝试计算机视觉领域重加权[94]、混合训练[95]等策略以提升分解模型对于不平衡样本训练的适应性。

# 5结语

本文对低频非侵入式负荷分解中的深度学习方法进行了综述、比较与展望。然而，受限于深度学习方法超参众多、解释性差、训练随机等固有局限，本文对于不同深度学习负荷分解模型间比较的探索仍是初步的、粗粒度的。未来，本文将继续应用所提负荷分解算法综合评价框架探索深度学习分解模型对于超参选择等方面的敏感性，并对文中算法比较未涉及的Type-III类电器进行后续研究。

# 参考文献

[1]HART G W．Nonintrusive appliance load monitoring[J].Proceedings of the IEEE,1992,80(12):1870-1891.   
[2] EHRHARDT-MARTINEZ K,DONNELLY K A. Advanced Metering Initiatives and Residential Feedback Programs:A Meta-Review for Household Electricity-Saving Opportunities[R].USA:ACEEE,2010. Intelligent Home Energy Management and Ambient Asssted Living: A Review:11[J].Energies,2019,12(11): 2203.   
[4]田世明,王蓓蓓,张晶.智能电网条件下的需求响应关键技术[J].中国 电机工程学报,2014,34(22):3576-3589. TIAN Shiming,WANG Beibei, ZHANG Jin. Key Technologies for Demand Response in Smart Grid[J]. Proceedings of the CSEE,2014, 34(22): 3576-3589.   
[5]程祥,李林芝,吴浩,等.非侵入式负荷监测与分解研究综述[J].电网 技术,2016,40(10):3108-3117. CHENG Xiang,LILinzhi,WU Hao,et al.A survey of the research on non-intrusive load monitoring and disaggregation[J]. Power System Technology,2016,40(10): 3108-3117.   
[6] BHOTTO M, MAKONIN S, BAJIC I.Load disaggregation based on aided linear integer programming[J]. IEEE Transactions on Circuits and Systems II:Express Briefs,2017,64(7): 792-796.   
[7] WEISS M, HELFENSTEIN A, MATTERN F, et al. Leveraging smart meter data to recognize home appliances[C]/2012 IEEE International Conference on Pervasive Computing and Communications.March 19- 23,2012,Lugano,Switzerland: 190-197.   
[8] FAUSTINE A,MVUNGI NH,KAIJAGE S,et al.A Survey on NonIntrusive Load Monitoring Methods and Techniques for Energy Disaggregation Problem[J/OL].arXiv:1703.00785,2017.   
[9] KIMH,MARWAHM, ARLITT M, et al. Unsupervised Disaggregation of Low Frequency Power Measurements[C]//The 11th SIAM International Conference on Data Mining,April 28-30,2011,Mesa, USA:747-758.   
[10] ZHONG M，GODDARD N, SUTTON C. Signal Aggregate Constraint in Additive Factorial HMMs,with Aplication to Energy Disaggregation[C]//The 28th International Conference on Neural Information Processing Systems. December 8-13, 2014,Montreal, Canada: 3590-3598.   
[11] 邓晓平,张桂青,魏庆来,等.非侵入式负荷监测综述[J].自动化学报: 1-21. DENG Xiaoping, ZHANG Guiqing,WEI Qinglai, et al. A Survey on the Non-intrusive Load Monitoring[J/OL]. Acta Automatica Sinica: 1-21.   
[12] HORNIK K, STINCHCOME M, WHITE H. Multilayer feedforward networks are universal approximators[J]. Neural Networks,1989, 2(5): 359-366.   
[13] KELLY J, KNOTTENBELT W. Neural NILM: Deep neural networks applied to energy disaggregation[C]/The 2nd ACM International Conference on Embedded Systems for Energy-Efficient Built Environments.November 4-5,2015,Seoul, South Korea:55-64.   
[14] CUI G,LIU B,LUAN W,et al. Estimation of Target Appliance Electricity Consumption Using Background Filtering[J]. IEEE Transactions on Smart Grid,2019,10(6): 5920-5929.   
[15] NALMPANTIS C, VRAKAS D. Machine Learning Approaches for Non-Intrusive Load Monitoring:From Qualitative to Quantitative Comparation[J]. Artificial Intelligence Review,2019,52(1): 217-243.   
[16] VINCENT P,LAROCHELLE H, BENGIO Y,et al. Extracting and Composing Robust Features with Denoising Autoencoders[C] //Proceedings of the 25th International Conference on Machine Learning.July 5-9,2008,Helsinki,Finland:1096-1103.   
[17] CHO K. Simple Sparsification Improves Sparse Denoising the 30th International Conference on Machine Learning. June 16-21, 2013,Atlanta,USA,2013: 432-440.   
[18] LU X, TSAO Y, MATSUDA S,et al. Speech Enhancement Based on Deep Denoising Autoencoder[C]/ INTERSPEECH. August 25-29, 2013,Lyon,France: 436-440.   
[19] DINESH C, MAKONIN S,BAJIC I V. Incorporating Time-of-Day Usage Patterns into Non-Intrusive Load Monitoring[Cl/017 IEEE Global Conference on Signal and Information Processing. November 14-16,2017,Montreal,QC,Canada: 1110-1114.   
[20]VALENTI M,BONFIGLI R,PRINCIPI E,et al.Exploiting the Reactive Power in Deep Neural Models for Non-Intrusive Load Monitoring[C]//2o18 International Joint Conference on Neural Networks. July 8-13,2018,Rio de Janeiro,Brazil: 1-8.   
[21] BONFIGLI R，FELICETTI A，PRINCIPI E,et al． Denoising Autoencoders for Non-Intrusive Load Monitoring:Improvements and Comparative Evaluation[J].Energy and Buildings,2018,158(1): 1461-1474.   
[22] BARSIM K S,YANG B.On the Feasibility of Generic Deep Disaggregation for Single-Load Extraction[J/OL].arXiv:1802.02139, 2018.   
[23] GOODFELLOW I J，POUGET-ABADIE J，MIRZA M,et al. Generative Adversarial Networks[J/OL].arXiv:1406.2661,2018.   
[24] CHEN K, ZHANG Y,WANG Q,et al. Scale and Context-Aware Convolutional Non-Intrusive Load Monitoring[J].IEEE Transactions on Power Systems,2020,35(3): 2362-2373.   
[25] KASELIMI M, VOULODIMOS A, PROTOPAPADAKIS E, et al. EnerGAN:A Generative Adversarial Network For Energy Disaggregation[C]//2020IEEEInternationalConferenceon Acoustics,Speech and Signal Processing.May 4-8,2020,Barcelona, Spain: 1578-1582.   
[26] PAN Y,LIU K, SHEN Z, et al. Sequence-To-Subsequence Learning With Conditional Gan For Power Disaggregation[C]//2020 IEEE International Conference on Acoustics,Speech and Signal Processing. May 4-8,2020,Barcelona,Spain: 3202-3206.   
[27] 成贵学,陈博野,赵晋斌,费敏锐.基于条件生成对抗网络的非侵入 式负荷分解[J/OL].电力系统及其自动化学报:1-7. CHENG Guixue,CHEN Boye,ZHAO Jinbin.Non-intrusive Load Disaggregation Based on Conditional Generative Adversarial Network[J/OL]. Proceedings of the CSU-EPSA:1-7.   
[28] GOODFELLOW I, BENGIO Y, COURVILLE A. Deep learning [M]. Cambridge: MIT Press,2016.   
[29] HOCHREITER S,SCHMIDHUBER J. Long short-term memory[J]. Neural Competition,1997,9(8): 1735-1780.   
[30] CHUNG J,GULCEHRE C,CHO K,et al. Empirical Evaluation of Gated Recurrent Neural Networks on Sequence Modeling[J].arXiv: 1412.3555,2014.   
[31] MAUCH L,YANG B.A New Approach for Supervised Power Disaggregation by Using a Deep Recurrent LSTM Network[C]//2015 IEEE Global Conference on Signal and Information Processing. December14-16,2015,Orlando,FL,USA:63-67.   
[32] KRYSTALAKOS O，NALMPANTIS C，VRAKAS D.Sliding Window Approach for Online Energy Disaggregation Using Artificial Neural Networks[C]//The 10th Hellenic Conference on Artificial Intelligence.July 9-15,2018,Patras,Greece:1-6.   
[33]HE W,CHAI Y.An Empirical Study on Energy Disaggregation via 非侵入式负荷分解[J].中国电机工程学报,2019,39(01):75-83. WANG Ke, ZHONG Haiwang,YU Nanpeng,et al. Nonintrusive Load Monitoring based on Sequence-to-sequence Model With Attention Mechanism[J]. Proceedings of the CSEE,2019,39(1):75- 83.   
[35]任文龙,许刚.基于深度序列翻译模型的非侵入式负荷分解方法[J] 电网技术,2020,44(01):27-37. REN Wenlong，XU Gang.Non-intrusive Load Decomposition Method Based on Deep Sequence Translation Model[J],Power System Technology,2020,44(01): 27-37.   
[36] 刘耀先,孙毅,李彬,等.基于边缘嵌入深度学习的非侵入式负荷分 解方法[J]．电网技术,2019,43(12):4329-4337. LIU Yaoxian，SUN Yi，LI Bin，et al． Non-intrusive Load Disaggregation Method Based on Edge Embedded Deep Learning[J], Power System Technology,2019,43(12): 4329-4337.   
[37] CIMEN H, CETINKAYA N,VASQUEZ J C,et al. A Microgrid Energy Management System Based on Non-Intrusive Load Monitoring via Multitask Learning[J].IEEE Transactions on Smart Grid,2020: 1-1..   
[38] RAFIQ H, ZHANG H, LI H, et al. Regularized LSTM Based Deep Learning Model: First Step towards Real-Time Non-Intrusive Load Monitoring[C/OL]/IEEE International Conference on Smart Energy Grid Engineering.August 12-15,2018,Oshawa,Canada: 234-239.   
[39] KASELIMI M,DOULAMIS N,DOULAMIS A,et al.BayesianOptimized Bidirectional LSTM Regression Model for Non-Intrusive Load Monitoring[C]/2019 IEEE International Conferenceon Acoustics,Speech and Signal Processing.May 12-17,2019,Brighton, United Kingdom: 2747-2751.   
[40] 罗平,樊星驰,章坚民,李俊杰.基于电器运行状态和深度学习的非 侵入式负荷分解[J/OL].电力系统自动化,2021:1-12. LUO Ping,FAN Xingchi, ZHANG Jianmin, et al. Non-intrusive Load Decomposition Based on Operation State of Electrical Appliances and Deep Learning[J]. Automation of Electric Power Systems,2021: 1- 12.   
[40] GREFENSTETTE E,BLUNSOMP;DEF,etal.A Deep Architecture for Semantic Parsing[J]. arXiv: 1404.7296,2014.   
[41]KIM Y. ConvolutionalNeuralNetworksforSentence Classification[C]//Conference on Empirical Methods in Natural Language Processing.October 25-29,2014,Doha, Qatar: 1746-1751.   
[42] BAI S,KOLTER J Z,KOLTUN V.An Empirical Evaluation of Generic Convolutional and Recurrent Networks for Sequence Modeling[J].arXiv:1803.01271,2018.   
[43] ZHANG C, ZHONG M, WANG Z, et al. Sequence-to-point learning with neural networks for non-intrusive load monitoring[C]//The 32nd AAAI Conference on Artificial Intelligence.February 2-7,2018, Louisiana, USA: 2604-2611.   
[44] KONG W,DONG Z Y,WANG B.A Practical Solution for NonIntrusive Type II Load Monitoring Based on Deep Learning and PostProcessing[J].IEEE Transactionson Smart Grid,2020,11(1):148- 160.   
[45] SHIN C, JOO S,YIM J. Subtask Gated Networks for Non-Intrusive Load Monitoring[J].Proceedings of the AAAI Conference on Artificial Intelligence,2019,33(01): 1150-1157.   
[46] 徐晓会,赵书涛,崔克彬.基于卷积块注意力模型的非侵入式负荷 分解算法[J/OL].电网技术,2021:1-8. XU Xiaohui, ZHAO Shutao,CUI Kebin． Non-intrusive Load Disaggregate Algorithm Based on Convolutional Block Attntion Module[J/0L]. Power System Technology,2021: 1-8.   
[46] HARELL A, MAKONIN S,BAJIC I V. Wavenilm: A Causal Neural Network for Power Disaggregation from the Complex Power Signal[C]//2019 IEEE International Conference on Acoustics,Speech and Signal Processing.May 12-17,2019,Brighton, UK:8335-8339.   
[47] OORD A van den,DIELEMAN S, ZEN H,et al. WaveNet: A Generative Model for Raw Audio[C]/The 9th ISCA Speech Synthesis Workshop,September 13-15,Sunnyvale,USA: 125.   
[48] FAUSTINE A,PEREIRA L, BOUSBIAT H,et al. UNet-NILM: A Deep Neural Network for Multi-Tasks Appliances State Detection and Power Estimation in NILM[C]//Proceedingsof the 5th International WorkshoponNon-Intrusive Load Monitoring. November18,2020,Virtual Event,Japan: 84-88.   
[49] RONNEBERGER O,FISCHER P,BROX T. U-Net: Convolutional NetworksforBiomedical ImageSegmentation[J/OL].arXiv: 1505.04597, 2015.   
[50] JIA Y, BATRA N, WANG H.A Tree-Structured Neural Network Model for Household Energy Breakdown[C]/International World Wide Web Conference.May 13-17，2019，San Francisco, USA: :2872-2878.   
[51] 张玉天,邓春宇,刘沅昆,等.基于卷积神经网络的非侵入负荷辨识 算法[J].电网技术,2020,44(06):2038-2044. ZHANG Yutian,DENG Chunyu,LIU Yuankun,et al. Non-intrusive Load Identification Algorithm Based on Convolution Neural Network [J].Power System Technology,2020,44(06): 2038-2044.   
[52]HAFSA BOUSBIAT，CHRISTOPH KLEMENJAK，WILFRD ELMENREICH.ExploringTimeSeriesImaging forLoad Disaggregation[C]//The 7th ACM International Conference on Systems for Energy-Efficient Buildings,Cities,and Transportation. November18-20,2020,Virtual Event, Japan: 254-257.   
[53] 白昱阳,黄彦浩,陈思远,等.云边智能:电力系统运行控制的边缘计 算方法及其应用现状与展望[J].自动化学报,2020,46(3):397-410. BAI Yuyang,HUANG Yanhao,CHEN Siyuan,et al. Cloud-edge inteligence: status quo and future prospective of edge computing approaches and applications in power system operation and control[J]. Acta Automatica Sinica,2020,46(3):397-410.   
[54] PEREIRA L,NUNES N.Performance Evaluation in Non-intrusive Load Monitoring:Datasets,Metrics,and Tools-A Review[J/OL]. Wiley Interdisciplinary Reviews: Data Mining and Knowledge Discovery,2018,8(6).   
[55] MAKONIN S,POPOWICHF.Nonintrusive Load Monitoring (NILM) Performance Evaluation:A Unified Approach for Accuracy Reporting[J].Energy Efficiency,2015,8(4): 809-814.   
[56] NALMPANTIS C,VRAKAS D. Machine Learning Approaches for Non-Intrusive Load Monitoring:From Qualitative to Quantitative Comparation[J].Artificial Intelligence Review,2019,52(1):217-243.   
[57] CHICCO D，JURMAN G. The Advantages of the Matthews Correlation Coeficient (MCC)over F1 Score and Accuracy in Binary Classification Evaluation[J].BMC Genomics,2020,21(1): 6.   
[58] MAKONIN S,POPOWICHF,BAJICIV,er al. Exploiting HMM Sparsity to Perform Online Real-Time NonintrusiveLoad Monitoring[J].IEEE Transactions on Smart Grid,2016,7(6): 2575 2585   
[59] KLEMENJAK C,FAUSTINE A, MAKONIN S,et al. On Metrics to Assess the Transferability of Machine Learning Models in NonIntrusiveLoadonitoring[J].arXivpreprintarXiv:191.06,19.   
[60]BOUSMALISK,TRIGRORGISG,SILBERMAN N,et al.Domain separation networks[Cl//In Advancesin Neural Information Processing Systems.December 5-10,2016,Barcelona,Spain: 343- 351.   
[61] GANIN Y, USTINOVA E,AJAKAN H, et al. Domain-adversarial training of neural networks[J]. Journal of Machine Learning Research, 2016,17(59): 1-35.   
[60] KLEMENJAK C，MAKONIN S，ELMENREICH W.ToWards Comparability in Non-Intrusive Load Monitoring:On Data and Performance Evaluation[J].arXiv: 2001.07708,2019.   
[61] BATRA N, KELLY J, PARSON O, et al. NILMTK: An Open Source Toolkit for Non-Intrusive Load Monitoring[C]//The 5th International Conference on Future Energy Systems.Cambridge,UK,2014: 13-27.   
[62] MAKONIN S,ELLERT B,BAJIC IV,et al. Electricity, Water, and Natural Gas Consumption of a Residential House in Canada from 2012 to 2014[J]. Scientific Data,2016,3(1): 160037.   
[63] BATRA N,PARSON O, BERGES M,et al.A comparison of nonintrusive load monitoring methods for commercial and residential buildings[J]. arXiv:1408.6595,2014.   
[64] BATRA N, GULATI M, SINGH A,et al. It's Different: Insights into home energy consumption in India[C]/The 5th ACM Workshop on Embedded Systems For Energy-Eficient Buildings.November 14-15, 2013, Roma, Italy: 1-8.   
[65] KOLTER J Z, JOHNSON M J. REDD: a public data set for energy disaggregation research [C]//SustKDD Workshop,2011,San Diego, USA: 6.   
[66] KELLY J,KNOTTENBELTW.The UK-DALE Dataset,Domestic Appliance-Level Electricity Demand and Whole-House Demand from Five UK Homes[J]. Scientific Data,2015,2(1):150007.   
[67] MURRAY D,STANKOVICL, STANKOVIC V.An Electrical Load Measurements Dataset of United Kingdom Households from a TwoYear Longitudinal Study[J]. Scientific Data,2017,4(1): 1-22.   
[68] KASELIMI M,PROTOPAPADAKIS E,VOULODIMOS A, et al. Multi-Channel Recurent Convolutional Neural Networks for Energy Disaggregation[J]. IEEE Access,2019,7: 81047-81056.   
[69] KIMJ,LE T-T-H,KIMH. Nonintrusive Load Monitoring Based on Advanced Deep Learning and Novel Signature[J]. Computational Intelligence and Neuroscience,2017: 4216281.   
[70] 陈铉,阐博文.刘广一.GPU 技术的新进展及其在电力系统中的应 用前景探讨[J].电力信息与通信技术,2018,16(3):16-25. CHEN Xuan，KAN Bowen，LIU Guangyi．The latest development of GPU and its prospective application in power system[J]. Electric Power Information and Communication Technology,2018,16(3): 16-25.   
[71] ZHOU P,QI Z, ZHENG S,et al. Text Classification Improved by Integrating Bidirectional LSTM with Two-dimensional Max Pooling[C]//The 26th International Conference on Computational Linguistics.December 13-16,2016,Osaka,Japan: 3485-3495.   
[72] ISOLA P,ZHU JY,ZHOU T,et al. Image-to-Image Translation with Conditional Adversarial Networks[C/OL]/017 IEEE Conference on Computer Vision and Pattern Recognition.July 22-25，2017, Honolulu, USA: 5967-5976.   
[73]Y LI,T JIANG,S QIN,et al. Multi-scale Generative Adversarial Networks for Speech Enhancement[C]//2019 IEEE Global Conference on Signal and Information Processing. November 11-14, 2019,Ottawa, Canada: 1-5.   
[71] BATRAN,KUKUNURIR,PANDEY A,et al. Towards Reproducible State-of-the-Art Energy Disaggregation[C]//The6thACM International Conference on Systems for Energy-Efficient Buildings, Cities,and Transportation.November 13-14,2019,New York,USA: 193-202.   
[72] KUKUNURI R,AGLAWE A,CHAUHAN J,et al. EdgeNILM: Towards NILM on Edge Devices[C]//The 7th ACM International Conference on Systems for Energy-Efficient Buildings,Cities,and Transportation. November 18-20,2020,Virtual Event, Japan: 90-99.   
[73] BARBER J, CUAYAHUITL H, ZHONG M,et al. Lightweight NonIntrusive Load Monitoring Employing Pruned Sequence-to-Point Learning[C]//Proceedings of the 5th International Workshop on NonIntrusive Load Monitoring.November 18,2020,Virtual Event Japan: 11-15.   
[74] CHANG F,CHEN C,LIN C.An Empirical Study of Ladder Network and Multitask Learning on Energy Disaggregation in Taiwan[C]// 2018 Conference on Technologies and Applications of Artificial Intelligence.November 30-December 12,2018,Taichung: 86-89.   
[75]AHMED S,BONS M.Edge Computed NILM:A Phone-Based Implementation Using MobileNet Compressed by Tensorflow Lite[C]//Proceedings of the 5th International Workshop on NonIntrusiveLoad Monitoring.November18,2020,VirtualEvent Japan: 44-48.   
[76] DELFOSSE A, HEBRAIL G, ZERROUG. A Deep Learning Applied toNILM:IsDataAugmentationWorthforEnergy Disaggregation[C]/The 9th International Conference on Prestigious Applications of Intelligent Systems. August 29-September 8,2020, Santiago de Compostela, Spain: 29.   
[77] KASELIMI M,DOULAMIS N, VOULODIMOS A,et al. Context Aware Energy Disaggregation Using Adaptive Bidirectional LSTM Models[J].IEEE Transactions on Smart Grid,2020,11(4):3054-3067.   
[78] HARELL A, JONES R, MAKONIN S, et al. PowerGAN: Synthesizing Appliance PowerSignaturesUsing GenerativeAdversarial Networks[J/OL].arXiv:2007.13645,2020.   
[79] D'INCECCO M, SQUARTINI S, ZHONG M. Transfer Learning for Non-Intrusive Load Monitoring[J].IEEE Transactions on Smart Grid, 2020,11(2): 1419-1429.   
[80] YANG Y, ZHONG J,LI W,et al.Semi-Supervised Multi-Label Deep Learning Based Non-Intrusive Load Monitoring in Smart Grids[J]. IEEE Transactions on Industrial Informatics,2020,16(11):6892- 6902.   
[81] WANG S,DU L, ZHOU Q.A Semi-Supervised Deep Transfer Learning Architecture for Energy Disaggregation[C/OL]//2019 IEEE Power & Energy Society General Meeting (PESGM). August 4-8, 2019, Atlanta, USA: 1-5.   
[82] 刘国龙,赵俊华,文福拴,毛一汝,吴占昕,薛禹胜.面向配用电侧负荷 数据的深度端到端超分辨率感知方法[J].电力系统自动 化,2020,44(24):28-40. LIU Guolong, ZHAO Junhua, WEN Fushuan, et al. Deep End-to-end Super-resolution Perception Method for Load Data at Distribution Side[J]. Automation of Electric Power Systems,2020,44(24): 28-40.   
[83] CLARK M,LAMPE L. Single-channel compressive sampling of electrical data for non-intrusive load monitoring[C]//2o15 IEEE Global Conference on Signal and Information Processing. December 14-16,2015,Orlando,FL,USA: 790-794.   
[84] HINTON G,VINYALS O, DEAN J. Distilling the Knowledge in a Neural Network[J/OL].arXiv: 1503.02531,2015.   
[85] HAN S,POOL J，TRAN J,et al. Learning Both Weights and Connections for Efficient Neural Networks[J/OL].arXiv:1506.02626, 2015.   
[86] HUBARA I,COURBARIAUX M,SOUDRY D,et al.Quantized Neural Networks: Training Neural Networks with Low Precision Weights and Activations[J/OL].arXiv:1609.07061,2017.   
[87] TAN M, CHENB,PANG R,et al.MnasNet: Platform-Aware Neural Architecture Search for Mobile [C]//2019 IEEE Conference on Computer Vision and Pattern Recognition. June 16-20,2019,Long Beach,USA: 2820-2828.   
[88]HOSPEDALES T，ANTONIOU A，MICAELLI P,et al．MetaLearning in Neural Networks:A Survey[J/OL].arXiv:2004.05439, 2020.   
[89]XIANY,LAMPERTCH, SCHIELEB,etal. Zero-Shot Learning-A Comprehensive Evaluation of the Good,the Bad and the Ugly[J]. IEEE Transactions on Pattern Analysis and Machine Intelligence, 2019,41(9): 2251-2265.   
[90]HE K，STANKOVIC L，LIAO J,et al. Non-Intrusive Load Disaggregation Using Graph Signal Processing[J]. IEEE Transactions on Smart Grid,2018,9(3): 1739-1747.   
[91] ZHOU J,CUIG, ZHANG Z,et al.Graph Neural Networks:A Review of Methods and Applications[J/OL].arXiv:1812.08434,2018.   
[92] VASWANI A,SHAZEERN,PARMARN,etal.Attention Is All You Need[J/OL].arXiv:1706.03762,2017.   
[93] LIOUTAS V, GUO Y. Time-aware Large Kernel Convolutions[J/OL]. arXiv:2002.03184,2020.   
[94] CUI Y,JIA M,SONG Y,et al.Class-Balanced Loss Based on Effective Number of Samples [C]/2019 IEEE Conference on Computer Vision and Pattern Recognition. June 16-20,2019,Long Beach,USA: 9268-9277.   
[95] VERMAV,LAMBA,BECKHAMC,etal.Manifold Mixup:Better Representations by Interpolating Hidden States[C]////Proceedings of the 36th International Conference on Machine Learning. June 9-15, 2019,Long Beach,USA,2019: 6438-6447.

# Applications and Comparison of Deep Learning in Low Frequency Nonintrusive Load Disaggregation

LI Yimingl,JU Yuntao1,QULiaol (1. College of Information and Electrical Engineering, China Agricultural University, Beijing 100083,China)

Abstract: Non-intrusive load disaggregation can comprehensively analyze user power consumption data and has been a crucial technology to evaluate users' flexible control potential. Since deep learning is currently the prevailing method of load disaggregation, the working mechanism of the three mainstream network structures, which includes denoising autoencoder, recurrent neural network and convolutional neural network, is discussed in detail when applying to load disaggregation， as well as their outlooks for applying in load disaggregation field. Afterwards, this paper proposes an evaluation framework for load disaggregation algorithms based on different dimensions and regularizes the selection of test data during the evaluation process accordingly. Finally, we make an empirical comparison of some mainstream deep learning disaggregation models by utilizing the proposed framework. And we also open source the code of the evaluation model. The evaluation result proves that the proposed framework can more comprehensively evaluate the deep learning disaggregation algorithms under specific hyperparameters setings，and reveal the sensitivity of model performance to distinct network architectures and input features.

Key words: deep learning; non-intrusive load disaggregation; convolutional neural network; recurrent neural network; electricity big data

# 附录A

TableA1 Acomparison of selected properties incommon public datasets   

<html><body><table><tr><td>数据集</td><td>房屋</td><td>持续时间/d</td><td>采样间隔(总)/s</td><td>采样间隔(分)/s</td><td>功率类型(总)</td><td>功率类型(分)</td><td>日均负荷事件数</td><td>其它信息</td></tr><tr><td>AMPds2</td><td>1</td><td>730</td><td>60</td><td>60</td><td>V,I,P, Q, S等</td><td>V,I,P, Q, S 等</td><td>319</td><td>水表、天然气表数据</td></tr><tr><td>COMBED</td><td>1</td><td>28</td><td>30</td><td>30</td><td>P</td><td>P</td><td>463</td><td>无</td></tr><tr><td>DRED</td><td>1</td><td>153</td><td>1</td><td>1</td><td>S</td><td>S</td><td>604</td><td>天气数据、入住率、</td></tr><tr><td>iAWE</td><td>1</td><td>73</td><td>1</td><td>6</td><td>P, Q, S</td><td>P, Q, S</td><td>497</td><td>房屋布局等 天气数据、用水量等</td></tr><tr><td>REDD</td><td>1</td><td>36</td><td>1</td><td>3</td><td>S</td><td>P</td><td>799</td><td>无</td></tr><tr><td>REFIT</td><td>1</td><td>638</td><td>8</td><td>7</td><td>P</td><td>P</td><td>320</td><td>天气、天然气表数据</td></tr><tr><td>REFIT</td><td>8</td><td>888</td><td>8</td><td>7</td><td>P</td><td>P</td><td>229</td><td>天气、天然气表数据</td></tr><tr><td>UKDALE</td><td>1</td><td>658</td><td>1</td><td>6</td><td>P, S</td><td>P, S</td><td>874</td><td>住户人员构成信息</td></tr><tr><td>UKDALE</td><td>2</td><td>176</td><td>1</td><td>6</td><td>P,S</td><td>P</td><td>733</td><td>住户人员构成信息</td></tr></table></body></html>

表A1常见公开数据集的属性对比  

<html><body><table><tr><td colspan="4">Table A2 Selection of training and testing scenes for specific appliances</td></tr><tr><td>用电器类别</td><td>训练房屋/时段</td><td>可见测试房屋/时段</td><td>不可见测试房屋(泛化)/时段</td></tr><tr><td>洗碗机、洗衣</td><td>1/2013-06-01~2014-01-01</td><td>1/2014-01-01~2014-02-01</td><td>2/2013-06-01~2013-07-01</td></tr><tr><td>机、冰箱</td><td>5/2014-07-15~2014-10-15</td><td>5/2014-07-01~2014-07-15</td><td></td></tr><tr><td>水壶、</td><td>1/2013-06-01~2014-01-01</td><td>1/2014-01-01~2014-02-01</td><td>2/2013-06-01~2013-07-01</td></tr><tr><td>微波炉</td><td>5/2014-07-15~2014-09-15</td><td>5/2014-07-01~2014-07-15</td><td></td></tr></table></body></html>

注：受限于UK-DALE数据集提供的功率类型，房屋5只被用于进行单输入特征负荷分解算法的训练与测试，即3.3小节算例不再使用房屋5进行训练与测试

表A2特定电器训练场景与测试场景的选择  
表A3特定电器训练时输入序列时间跨度及开启时功率阈值  
Table A3 Time span of input sequence and on threshold of specific appliances during training   

<html><body><table><tr><td>用电器类别</td><td>输入序列时间跨度/s</td><td>开启时功率阈值/W</td></tr><tr><td>洗碗机</td><td>3840</td><td>10</td></tr><tr><td>微波炉</td><td>1920</td><td>500</td></tr><tr><td>水壶</td><td>1920</td><td>2000</td></tr><tr><td>洗衣机</td><td>3840</td><td>20</td></tr><tr><td>冰箱</td><td>2880</td><td>50</td></tr></table></body></html>

Table A4Theresultsof model pre-evaluationin 3.2.1 section   

<html><body><table><tr><td>网络模型</td><td>t /min</td><td>m /MB</td><td>v/s</td></tr><tr><td>Bi-LSTM</td><td>21.7</td><td>17.05</td><td>112.9</td></tr><tr><td>Seq2Point</td><td>7.8</td><td>24.93</td><td>11.1</td></tr><tr><td>CNN_Attention</td><td>9.1</td><td>25.95</td><td>13.2</td></tr><tr><td>SGN-sp</td><td>44.0</td><td>78.67</td><td>35.3</td></tr><tr><td>DAE</td><td>5.5</td><td>4.73</td><td>0.01</td></tr><tr><td>EnerGAN</td><td>47.4</td><td>5.29</td><td>1.9</td></tr></table></body></html>

注：表头中变量t、 $m$ 、 $\nu$ 的定义同2.1.1小节

表A43.2.1小节网络模型预评估结果  
表A53.3.1小节网络模型预评估结果  
Table A5 The results of model pre-evaluation in 3.3.1 section   

<html><body><table><tr><td>网络模型</td><td>特征维数</td><td>■ t /min</td><td>m /MB</td><td>v /s</td></tr><tr><td rowspan="3">Bi-LSTM</td><td>1</td><td>16.2</td><td>17.05</td><td>111.4</td></tr><tr><td>2</td><td>14.6</td><td>17.05</td><td>114.7</td></tr><tr><td>3</td><td>13.1</td><td>17.05</td><td>117.8</td></tr><tr><td rowspan="3">Seq2Point</td><td>1</td><td>6.4</td><td>24.93</td><td>10.3</td></tr><tr><td>2</td><td>5.7</td><td>24.93</td><td>10.5</td></tr><tr><td>3</td><td>4.9</td><td>24.93</td><td>10.6</td></tr><tr><td rowspan="3">DAE</td><td>1</td><td>3.7</td><td>4.73</td><td>0.02</td></tr><tr><td>2</td><td>3.6</td><td>4.73</td><td>0.02</td></tr><tr><td>3</td><td>3.9</td><td>4.73</td><td>0.02</td></tr></table></body></html>

注：表头中变量t、 $m$ 、 $\nu$ 的定义同2.1.1小节

注：图A1-A5中省略了Padding、Flatten、Dropout 等非参数层，读者可根据前后网络层的输入输出尺寸自行推断，更多细节请参考相关源码。

维卷积层 一维卷积层 维卷积层 维卷积层 维卷积层  
输入层 全连接层 输出层卷积核尺寸：10 卷积核尺寸：8 卷积核尺寸：6 卷积核尺寸：5 卷积核尺寸：5  
序列长度：N 卷数量：U 卷积核数量：30 卷积核数量：40 卷积数量：LU 卷积数量：5U 神经元数：1024 神经元数Linear步长：1 步长：1 步长：1 步长：1 步长：1维卷积层 双向LSTM层 双向LSTM层  
输入层 全连接层 输出层卷积核尺寸：4 隐状态维数：64 隐状态维数：128  
序列长度：N 卷核数：1 双向：Linear 双向：Linear 神元个数：128 神经元个Linear步长：1 返回序列：是 返回序列：否

![](images/812d80fddb4bd14f7be762018226604eb6ac194e9b166634981a1198019a768f.jpg)  
Fig.A1 Schematic diagram of the structure of the Seq2Point model   
图A2 Bi-LSTM模型结构示意图  
Fig.A2 Schematic diagram of the structure of the Bi-LSTM model   
图A3DAE 模型结构示意图  
Fig.A3Schematic diagram of the structure of the DAE model

![](images/8fa843d393bc031c3b7a165ba32d0271f46b5ec06d148e4c91d161a31091df6e.jpg)  
图A1Seq2Point模型结构示意图  
图A4SGN-sp 模型结构示意图  
Fig.A4Schematic diagram of the structure of the SGN-sp model

![](images/cd03cbf2d08c51648a7b8d3030b8fab8bc0da0eb77cfba9dfaf4b900b28d5423.jpg)  
Fig.A5Schematic diagram of the structure of the EnerGAN model

![](images/f7664add40f1edd4bba10c491b83f19c19b07d129db5e36d2ad792d98dd697e0.jpg)  
图A5EnerGAN模型结构示意图  
图A6 CNN_Attention 模型结构示意图  
Fig.A6Schematic diagram of the structure of the CNN_Attention model

![](images/7596354e9214e917aa25398c4af1d5a2e7ccc7be9144acae6e1353bfa991b08b.jpg)  
图A7五种深度学习模型辨识准确性对比

![](images/071ec8b4fb333931551094a96bae509516f512dddec226da859074c6f2f63d46.jpg)  
Fig.A7A comparison of identification accuracy of five deep learning models   
图A8五种深度学习模型回归准确性对比

Fig.A8 A comparison of regression accuracy of five deep learning models

![](images/9d2faab686136c3abdf78fa88a3e5e2e401f5b18623d0a78750aaef395951c0c.jpg)  
图A9五种深度学习模型泛化性能对比

![](images/29d9348e2818ff38fe9d6854f57aebea0d00f44be15c2432cc0cae2d07d15f82.jpg)  
Fig.A9A comparison of transferabilityof five deep learningmodels

Recall Precision MCC1.0- 1.0- 1.0-  
0.5 906'0 £96.0 956.5 196'0 0.5- 606'0 006.4 966.0 846'0 0.5- 658.0 006.2 007.1 976'00.0- 0.0- 0.0-1.0- 1.0 1.0-  
精0.5 188.0 906'0 588.3 L68'0 0.5- L68'0 916'0 906'0 1£6.0 0.5- 888'0 116'0 £68.0 L16'00.0- 0.0- 0.0-1.0 1.0-606.0 06.3 106.0 846.4 0.5- 008.3 1160 [6L'0 003.3 0.5- 788.0 856.0 1/8.0 906'00.0 0.0- 0.0-1.0- 1.0- 1.0-796.0 686'0 986'0 486.0 0.5 908.3 007.5 816'0 646.0 0.5- 768.0 SL6'0 846.0 \$96'00.0- 0.0- 0.0-P1.0- 1.0-P+Q0555 £16.0 00/4 L680 0.5- 0 1080 668'0 088.2 588'0 0.5- 0994 906'0 18'0 1680 （20 $\mathrm { { \bf { P } } } { + } \mathrm { { \bf { Q } } } { + } \mathrm { { \bf { S } } }$ 0.0- 0.0 0.0(b)不同输入特征下Bi-LSTM模型辨识准确性对比Recall Precision MCC1.0 - 1.0 1.0  
0.5- 608.3 L06'0 816.0 916'0 0.5- 055.3 568.0 L68'0 £68'0 0.5 84/.4 1£8'0 848.0 048.30.0- 0.0- 0.01.0 1.0 1.0  
0.5 0555 £99.0 05.4 859.5 0.5 976.0 6563 L46.0 946.0 0.5 81/.1 L8L'0 811.0 88L00.0 0.0 0.01.0 1.0- 1.0106.0 106'0 007.44 053. 0.5- \$99.0 6LL'0 0.5 581'0 178.10.0- 0.0- 0.0-1.0- 1.0- 1.0-  
0 8.80 053.3 057.5 8460 0.5- £99.0 £06.0 08.1 16'0 0.5- 055.4 006.4 £06.0 076.40.0 0.0-P1.0 1.0-P+Q微 535.3 008.0 SL9.0 1180 0.5- SO/.0 098.4 G 0.5- 053 003.3 075.2 618'0 （20 $\mathrm { P + } \mathrm { Q + } \mathrm { S }$ 0.0- 0.0 0.0(c)不同输入特征下DAE 模型辨识准确性对比

Fig.A10 A comparison of identification accuracy of deep learning models with different input features

MAE NEP OMAE10-0.2- 10-33 5 100090- 0.0- 01  
2 0.2-30 27 29 05 e 200- 3 13033 8'Z10- 0.0- 0-1Y 15 0.1- LI'O 1F 15 2-0- 0.0- 04547 0.1- LI'O £10 14 50- 39 660- 0.0- 0-P500-4 5 0.5- 84 8 22 3534 P+Q2 17 0 4 250- 6 9.00% 328% P+SP+Q+S0- 0.0- 0(a)不同输入特征下 Seq2Point 模型回归准确性对比MAE NEP OMAE10-0.2- 10-  
箱 5- 3AR 0.1- 5- 9330- 0.0- 0-  
楂2D 24 38 0.2- 24 2 1 100- 160 10390- 0.0- 0-54 0.0- 0 L0'0 0 20-0- 0.00 04-0.10-50-37 35 0.05- 001 0 三 88 52500- 0.00 0-400- P  
2 AF2 0.50- 6 6 5 200-2 F P+$\mathbf { P + Q + S }$ 0 0.00 0(b）不同输入特征下 Bi-LSTM 模型回归准确性对比

![](images/d3943281b9a2cc06a22f4a52c02e88a12dd71723a26dc883cf59278beb6e367b.jpg)  
图A11不同输入特征下深度学习模型回归准确性对比

Fig.Al1 A comparison of regression accuracy of deep learning models with diferent input features

![](images/ac4bdc472d236fb78048eb75b9dc39a4bea4c764324d72f4ecf7c750cf25f1d7.jpg)

MAE MCC  
精10 11 111 2 0.5- 6690 76'0 106.0 £16.50- 0.0-  
特 L9'L L8'8 47.3 7'6 0.5- 08.4 708'0 98'0 88L'00 0.0-3'27 4.94 537 0.5- 99'0 870 00/.1 91L'00.0-  
4 8'61 2 0.5 0 22 6L9'0 L49.0 ££9.001 0.0-P  
1 LI'8 9'1 57.1 401 0.5- 659.5 180'0 L6L'0 440:0 L （20 $\mathbf { P } { + } \mathbf { Q }$ $\mathbf { P + S }$ （20（20 $\mathrm { P + Q + S }$ 01 0.0(b）不同输入特征下 Bi-LSTM 模型泛化性能对比MAE MCC  
箱10 1'81 4 3F 15 0.5 001.4 776.2 608'0 87500- 0.010  
季 0'01 L'01 £L6 8'01 0.5 10/.4 80L'0 0072 869'00 0.0  
20 4.31 6.L7 39 10 0.5 664 LL9'0 1855 £99.30- 0.0  
2 0.5244 1 S/0:0 1/55 509.0 £5.301 0.0-P  
10 2 555 0.5 6/5.0 0014 0554 605.5 （204号 $\mathbf { P + Q + S }$ （204号01 0.0(c）不同输入特征下 DAE 模型泛化性能对比

Fig.A12Acomparisonof transferability of deep learning models with different input features

# 附录B

![](images/4aa401358793551207d3412691ce073867eb46b63e950e1a2596979acef7fc47.jpg)  
图B13.2小节不同网络分解冰箱结果曲线图

Fig.B1 Curve of fridge disaggregation results among different models in session 3.2

![](images/ca7047cb1300d71ebc289e0d2117259373ab1d7ace3739e52e2d0d8f19573281.jpg)  
图B23.2小节不同网络分解水壶结果曲线图

Fig.B2 Curve of kettle disaggregation results among different models in session 3.2

![](images/5c18e535f061af7b6e95f6b667633043e14de89bc1101ff86319bb60d19bdacb.jpg)  
图B33.2小节不同网络分解洗碗机结果曲线图

Fig.B3 Curve of dish washer disaggregation results among different models in session 3.2

![](images/3c74c5a6cefa53953ca181f1ea24bed82c34f578dd3c3e56b1c65b6cb715f105.jpg)  
图B43.2小节不同网络分解洗衣机结果曲线图

Fig.B4 Curve of washing machine disaggregation results among different models in session 3.2

![](images/cde7d0f7cbda76b7f729463c87330713638a2e59e59cc3f482f280f740265360.jpg)  
图B53.2小节不同网络分解微波炉结果曲线图

Fig.B5 Curve of microwave disaggregation results among different models in session 3.2

![](images/3392c6ff8278e72be2cae7ba6f136eb608473d23dea5e32df02ab87cb7cbd3c6.jpg)

![](images/1420cc8c13725a19907f26c204792228f67f9d6ce021de2afa6ea653910934b9.jpg)

![](images/f64372a48b87b3a77a0ef6e9dcf540099d75fe992f253f5ed0f903b93a691e27.jpg)  
(b)DAE 模型在不同输入特征下分解冰箱结果曲线图

![](images/759f17684ead903d392b253faa0fe3a9536530ec54288f9e3f1da29482b30950.jpg)  
图B63.3小节不同特征下网络分解冰箱结果曲线图

Fig.B6 Curve of fridge disaggregation results among different input features in session 3.3

![](images/94fa56e48ad8cdf50a60ed8b15d4f51c37ccff39f533a80ca1fe04a3e4313464.jpg)  
(a)Bi-LSTM模型在不同输入特征下分解水壶结果曲线图

![](images/7b57a0b310f9c1c306a763116aa6f1f3cf33624de279c731635f92dfd8cb45c2.jpg)

![](images/e219a5e8f3c67ff7f86239f30ef943700107d7bc049edfcaed964f34300f988c.jpg)  
(b)DAE 模型在不同输入特征下分解水壶结果曲线图

![](images/a9d7e58618be9857b439a7cf28e934c1bbd30d091f80cbd4d6d80648b6426484.jpg)  
图B73.3小节不同特征下网络分解水壶结果曲线图

Fig.B7 Curve of kettle disaggregation results among different input features in session 3.3

![](images/3c4f0363d5d214544ca3fed2718cace46780b85418843c2969f877a1a3b64954.jpg)  
(a)Bi-LSTM模型在不同输入特征下分解洗碗机结果曲线图

![](images/913291b2a4f8e170931fd027acd6f46d71ac10e7634614bb9e24f328b962b1f5.jpg)

![](images/696142041654a19b3261f876ca4a05790da664311b45aa911846b97a9ea45c4c.jpg)  
(b)DAE模型在不同输入特征下分解洗碗机结果曲线图

![](images/80a34cc3fdf257c16106ae6d2ab50a1ed0376542b91b5007d25e720a029ee697.jpg)  
图B83.3小节不同特征下网络分解洗碗机结果曲线图

Fig.B8 Curve of dish washer disaggregation results among different input features in session 3.3

![](images/0af4d08f82a783c8c0e4021e167d1f5c851062db9ccf1b49e85bdedd32da4ab9.jpg)  
(a)Bi-LSTM模型在不同输入特征下分解洗衣机结果曲线图

![](images/d10045a3ca0d6190f63d30f3387d4d69f01c867b40d7d9f1834ff6490eccf2c3.jpg)

![](images/6f3abf3708b49fb33ac79b51a64743c52f742f16ef8bbe44269f28129fcf25c8.jpg)  
(b)DAE模型在不同输入特征下分解洗衣机结果曲线图

![](images/5c6fcad40996acf7780c1eb75bcf9b4dc0e9c5d79e872683b1d71aef3a5cb976.jpg)  
图B93.3小节不同特征下网络分解洗衣机结果曲线图

Fig.B9 Curve of washing machine disaggregation results among different input features in session 3.3

![](images/ff1e1d4e6be4142331c246e22ef27e510818cc81803f511c26a5d832d38971a0.jpg)  
(a)Bi-LSTM模型在不同输入特征下分解微波炉结果曲线图

![](images/96d1bcdb65452894a9cf30d26e1fca2ee3316636c80f3a18510bfe876100e92c.jpg)

![](images/3b817a835c9534b51b89b7bb38e738d6cbd67b54d3e4f33a79db96583880b6bb.jpg)  
(b)DAE 模型在不同输入特征下分解微波炉结果曲线图

![](images/9e2ce7995f9c4cb9371aa54ab32b115b6cb55be29e50d03e658fbfdd2b4a3dc9.jpg)  
图B103.3小节不同特征下网络分解微波炉结果曲线图

Fig.B10 Curve of microwave disaggregation results among different input features in session 3.3