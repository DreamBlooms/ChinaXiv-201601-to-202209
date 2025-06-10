# 基于深度学习的ADHD儿童和正常儿童脑电信号分类研究

田博帆1,²，严瀚莹1,²，王苏弘³，邹凌1,2†(1．常州大学 信息科学与工程学院，江苏 常州 213164;2．常州市生物医学信息技术重点实验室，江苏 常州 213164;3．苏州大学附属第三医院 脑科学研究中心，江苏 常州 213003)

摘要：针对注意缺陷多动障碍儿童（atentiondeficit hyperactivitydisorder，ADHD）和正常儿童的分类问题，实验采用经典干扰控制任务范式对两类儿童的事件相关电位（event-relatedpotential，ERP）进行了研究，旨在通过ERP 特征实现其分类。实验首次使用长短期记忆（long-shorttermmemory，LSTM）方法分析两类儿童前额叶与顶枕叶脑区最佳电极（ $_ { \cdot \mathrm { p } < 0 . 0 5 }$ ）潜伏期（ $2 0 0 { \sim } 4 5 0 \mathrm { m s }$ ）的脑电信号，并自动学习和分类其ERP特征。相比常规分类方法，LSTM方法的分类率略高，可达 $9 5 . 7 8 \%$ 。研究结果表明LSTM方法有助于ADHD儿童脑电信号的分类，为ADHD儿童个体诊断技术提供了一种新思路。

关键词：干扰控制任务实验；注意缺陷多动症；长短期记忆网络中图分类号：TN911.7 doi:10.3969/j.issn.1001-3695.2017.08.0870

# Study of EEG signal classification based on deep learning for adhd children and normal children

Tian Bofan1, ², Yan Hanying1,2, Wang Suhong³, Zou Ling1, 2† (1.FacultyofInformationScence&Engineering,ChangzhouUniversityChangzhouJiangsu213164,China;2.Changzhou KeyLaboratoryof Biomedical Biomedical Information Technology，Changzhou Jiangsu 213164,China;3.Departmentof Neuroscience,The Third Affiliated HospitalofSoochow University,Changzhou Jiangsu 213o03,China)

Abstract:Tosolve theclasification problemofAtention Deficit HyperactivityDisorderchildrenand normal children,the experiment studiedtheevent-related potentialof them with theclasicalinterferencecontroltask experimentalparadigminorder todistinguish twocategoriesofchildren through theERPcharacteristics.Intheexperiment,the Long Short-Term Memory (LSTM) method was firstlyused to analyze the EEG signals of two kinds of children's the optimal electrodes $( \mathrm { P } < 0 . 0 5 )$ in the frontalandparietal-ocipitalregions during thelatency(2oo\~45Oms），learn itscharacteristicsautomaticallandrealize classification.The classification rate was slightly higher than the conventional method,up to $9 5 . 7 8 \%$ .The results show that the LSTM method is helpful to clasify the EEG signals ofchildren with ADHD,which providesanew idea forthe individual diagnosis ofADHD children.

KeyWords: Interference control task experiment;ADHD;LSTM

# 0 引言

注意缺陷多动障碍(ADHD)俗称儿童多动症，是一种以注意力不集中、活动过多和冲动性行为为主要特征的神经精神疾病，近年来越来越多地受到社会和家庭的重视[I]。Salomone等人通过脑电图（electroencephalogram,EEG）等神经电生理技术研究已发现ADHD儿童在脑功能方面存在执行功能缺陷，其中执行功能最为核心的缺陷主要表现在三个方面：抑制过程、工作记忆和转换能力[2]。并已有实验采用干扰控制任务范式用于ADHD儿童抑制过程方面的研究，其结果显示ADHD儿童存在干扰控制功能缺陷，导致这一缺陷的主要原因是ADHD儿童脑部结构存在差异性[3]。同时有研究表明，与干扰控制功能缺陷相关的脑区主要是前额叶和顶枕叶[4]。

常规脑电特征提取方法在脑电分析中有着广泛应用，如：波段功率法，共空间模式法（Common SpatialPattern,CSP），多元自适应自回归法以及独立成分分析法等[56]。常规方法对脑电数据的处理较为繁琐，特征选择比较单一。深度学习方法具有特征自学习能力，是通过组合简单非线性模块，将原始数据转变成为更高层次、更加抽象的表达[7]。深度学习能够利用自身网络的特点对数据进行学习，从海量的数据中学习到更多隐含信息。使用深度学习方法处理常规脑电数据，已成为研究的热点[8.9]。例如Davidson 等人首次运用LSTM方法实时分析健康被试在视觉运动跟踪任务中的EEG特征，当检测到被试精神运动出错时，系统能够及时给予错误警报，避免事故的发生，预测准确率高达 $8 4 \% ^ { \mathrm { ( 9 ] } }$ 。本研究采用LSTM方法处理多动症儿童和正常儿童的脑电信号，并与AdaBoost和Bagging等常规方法比较，研究结果为多动症儿童计算机辅助诊断和治疗提供新的思路。

# 1方法

# 1.1被试

所有被试均由常州市第一人民医院经临床确诊，共筛选出符合实验条件的 ADHD儿童69 例，年龄（ $8 . 5 7 \pm 2 . 4 1$ ）岁，其中混合型（ADHD-C）54例，注意缺陷型（ADHD-I）4例，多动冲动型（ADHD-HI）11例；健康儿童73例，年龄（ $\cdot 8 . 3 7 \pm 2 . 1 6 )$ （20岁。ADHD 组和正常对照组之间的年龄差异无统计学意义（ $( \mathsf { p } { \mathord { > } } 0 . 0 5 )$ ）。

两组儿童的实验研究已通过常州市第一人民医院伦理委员会批准。所有受试者均由其本人或其监护人在签署知情同意书的情况下，自愿参加了本实验。

# 1.2实验设备

采用EGI公司128导联10-10脑电采集系统，采样频率为${ 5 0 0 } \mathrm { H z }$ ，电极阻抗设定在 $8 0 ~ \mathrm { k } \Omega$ 以下，分别使用Net Station 软件和EEGLAB工具箱做前期预处理操作，参考电极使用平均参考。

# 1.3实验范式

实验范式来自经典的干扰控制任务（simon-spatial stroop）范式[4]。实验范式的具体内容如图1所示，实验任务分训练和测试两个阶段，训练分为两次。

![](images/61db41fa36056ee46c1255451c199409d8f4ed73a9decbe605f65f21806c87e4.jpg)  
图1实验范式训练过程

第一次训练，屏幕随机呈现向上和向下的箭头刺激，被试可根据不同的箭头指示方向在按键盒上作出对应的按键选择，当箭头方向朝上时被试使用左手按下对应的左按键，当箭头方向朝下时被试使用右手按下对应的右按键。第二次训练，屏幕的中心会出现一个十字注视点，向上和向下的箭头会随机出现在以注视点为中心的上、下、左、右四个方位，一共有8种不同的呈现方式，如图2所示，组合成4种刺激类型，分别为：

Simon Congruent(SmC)、Simon Incongruent(SmI)、Stroop Congruent(StC)、和 Stroop Incongruent(StI)。正式实验以第二次训练模式进行，整个实验过程包括两次会话，每次会话有144次实验，共计288次实验，实验中四种刺激模式等概率随机呈现，每种刺激呈现时间为 $1 0 0 0 \mathrm { { m s } }$ ，每次刺激的时间间隔分别从2000、2500、3000、3500四个时间段随机选取，一次会话结束，被试有 $2 \mathrm { m i n }$ 的休息时间。

![](images/837ff853c7dfdf6373630caa0cdbd70254892cca8c6289a32aa08998908a766f.jpg)  
图2四种刺激组合

# 1.4最佳电极选择

有文献采用Simon-spatialStroop 范式研究多动症抑制功能缺陷，结果表明多动症儿童和正常儿童的前额叶及顶枕叶ERP波幅存在显著差异性（ $\cdot \mathrm { p } { < } 0 . 0 5 \$ ），使用最佳电极脑电数据能有效区分多动症儿童和正常儿童[4]。本实验选取不同刺激模式下前额叶和顶枕叶脑区的最佳电极，如表1所示。

表1最佳电极选取结果 $( \mathsf { p } { < } 0 . 0 5 )$ 0  

<html><body><table><tr><td>刺激模式</td><td>前额叶电极（f)</td><td>顶枕叶电极 (p)</td></tr><tr><td>SmC</td><td>9</td><td>67</td></tr><tr><td>SmI</td><td>11</td><td>71</td></tr><tr><td>StC</td><td>9</td><td>71</td></tr><tr><td>StI</td><td>10</td><td>89</td></tr></table></body></html>

# 1.5算法流程

首先，预处理脑电数据，将预处理数据分为训练样本集和测试样本集；其次，选择ADHD儿童和正常儿童前额叶和顶枕叶两个脑区最佳电极处的脑电信号；最后，分别使用常规方法和深度学习方法处理脑电信号。常规方法使用共空间模式法（commonspatialpattern,CSP）提取两脑区间的ERP共特征，并对提取到的特征使用boost分类器和Bagging分类器分类。深度学习方法则采用长短期记忆单元网络自动学习ERP特征并分类。

# 1.5.1脑电信号预处理

先采用Net Station软件预处理数据，具体操作步骤包括：低通滤波、高通滤波（ $ { \mathrm { ~ \textrm ~ { ~ ~ } ~ } } _ { 0 . 1 \sim 3 0 \mathrm { H z } }$ ）、分段 $( - 2 0 0 { \sim } 1 0 0 0 \mathrm { m s } )$ 、人工伪迹检测、坏通道替换、叠加平均、参考点转换及基线校正（-$2 0 0 { \sim } 0 \mathrm { m s }$ ）；然后选择预处理后的脑电数据，潜伏期范围（ $2 0 0 { \sim } 4 5 0 \mathrm { m s }$ ），再使用EEGLAB工具箱进行人工数据挑选。

数据集的具体信息如表2所示。

表2数据集  

<html><body><table><tr><td>样本</td><td>分类</td><td>人数</td><td>Trial数</td></tr><tr><td rowspan="2">训练集</td><td>正常组</td><td>51</td><td>2119</td></tr><tr><td>ADHD</td><td>48</td><td>2033</td></tr><tr><td rowspan="2">测试集</td><td>正常组</td><td>22</td><td>908</td></tr><tr><td>ADHD</td><td>21</td><td>871</td></tr></table></body></html>

# 1.5.2LSTM算法及网络结构

长短期记忆算法是一种基于网络结构的深度学习算法，是增加了记忆功能的递归神经网络[I0]。使用LSTM算法处理脑电信号，可直接将每个被试的原始脑电信号输入至网络，网络依靠自身具有的记忆功能特性，可以在任意的时间尺度上学习复杂的时间关系，并能够保留过去每一时刻信号间的内在信息,预

测下一时刻可能的结果。

实验模型是基于Tensorflow 和Keras 框架构建，具体的LSTM网络结构如图3所示，整个深度学习网络分三个层次，第一层为输入层，第二层为隐含层，第三层为输出层。其中隐含层包含LSTM网络结构层、全连接层及softmax层。为了提高网络的学习效率并能够快速学习特征，全连接层被设计成三层，但随着网络层数的增加，每层间的学习率大小都会随之改变，进而导致不稳定的梯度问题发生，为均衡全连接层中三层的学习率大小，实验采用了Keras 框架中的Adam 算法，它是一种基于梯度的优化算法，有着更快的收敛速度。为了使ROC损失曲线下降更快，经多次实验，Adam 算法中的学习率参数默认值调整为0.0001；由于Kappa是个灵活的实时处理架构，能够启动多个实例进行重复计算，有利于模型的调优，因此，Adam算法中架构参数 lambda 改为kappa，其他参数均保持默认值。

![](images/fe8750a7191d768549aaf474bb272d066ae9554312111183d24bf59a909fbf59.jpg)  
图3LSTM网络结构图

输入层输入的数据为训练集数据，它是由4152试次的两导联潜伏期的脑电信号构成。由于采样频率 ${ 5 0 0 } \mathrm { H z }$ ，选取$2 0 0 { \sim } 4 5 0 \mathrm { m s }$ 潜伏期脑电信号，采样点共计126个，数据为$1 2 6 ^ { * } 2 ^ { * } 4 1 5 2$ 的矩阵。为了与采样点维度保持一致，对应输入层的节点数设置为126个。训练过程共有20次迭代，每次选取$20 \%$ 的训练样本用作交叉验证以提高迭代准确率。

隐含层主要负责特征学习和特征模型建立，LSTM网络结构层的记忆单元节点数与输入层节点数一致，即126个。每个单元包含有三个门控，分别为：输入门、遗忘门和输出门，每个门控均由一个激活函数完成自身状态的激活，从而对输入的信息进行有效读、写、遗忘操作，门控间通过协同作用可实现完成单元节点的状态更新。而tanh函数更适合于求解非线性问题，选择它作为LSTM单元输入门的激活函数，可减少迭代次数。三个门控状态的计算分别为式 $( 1 ) \sim ( 3 )$ ，状态变换及状态更新计算分别为式（4）～（6）。

输入门：

$$
\boldsymbol { i } _ { t } = g ( w _ { x i } x _ { t } + w _ { h i } h _ { t - 1 } + \boldsymbol { b } _ { i } )
$$

遗忘门：

$$
f _ { t } = g ( w _ { x f } x _ { t } + w _ { h f } h _ { t - 1 } + b _ { f } )
$$

输出门：

$$
o _ { t } = g ( w _ { x o } x _ { t } + w _ { h o } h _ { t - 1 } + b _ { o } )
$$

输入门和单元的状态变换：

$$
c _ { - } i n _ { t } = \operatorname { t a n h } ( w _ { x c } x _ { t } + w _ { h c } h _ { t - 1 } + b _ { c _ { - } i n } )
$$

状态更新：

$$
c _ { t } = f _ { t } \cdot c _ { t - 1 } + i _ { t } \cdot c _ { - } i n _ { t }
$$

$$
h _ { t } = o _ { t } \cdot \operatorname { t a n h } ( c _ { t } )
$$

其中： ${ { w } _ { x i } }$ 表示单元 $x$ 到单元 $i$ 的连接权值， $x _ { t }$ 表示 $t$ 时刻脑电向量， $b _ { i }$ 表示激活函数的一个激活阈值。 $g$ 表示输入的激活函数，其中输入门为 tanh 函数，遗忘门和输出门为 $\sigma$ 函数， $i _ { t }$ 表示输入门候选值， $h _ { t }$ 表示 $t$ 时刻脑电向量 $\boldsymbol { x } _ { t }$ 经LSTM记忆单元后的输出，其他类推。

为了防止神经网络过度拟合，避免神经元参数过多导致训练模型太复杂，全连接层经调整后每层节点数都设置为150个，同时在全连接层的第二层引用了Dropout技术用于节点的随机断连接，其中Dropout 的比率设置为0.4。softmax 层主要是通过提取到的特征向量进行归一化处理，计算出每一类的概率值。

输出层是将隐含层中每个LSTM记忆单元的输出值 $h _ { t }$ 经全连接层和softmax层计算后转换成yt，yt表示预测分类结果，最后计算得出分类率。

# 2 结果与讨论

# 2.1刺激模式分析及选择

N2 可作为诊断 ADHD儿童冲突监测功能的参考指标，N1、P2 与视觉注意力、忽略无关信息能力有关[,12]。研究发现，四种刺激模式下，ADHD儿童和正常儿童前额叶与顶枕叶脑区最佳电极叠加平均后的ERP波形如图4所示。

![](images/5b0c8db629ad610ec74d5bb18948d314264a88a4e663e7a660502952aa78e2ac.jpg)  
图4四种刺激模式下两脑区的ERP波形图

图4（a）（b）分别为SmC刺激模式下，前额叶脑区第9导联和顶枕叶脑区第67导联的ERP波形显示结果。图4（c)（d）分别为SmI刺激模式下，前额叶脑区第11导联和顶枕叶脑区第71导联的ERP波形显示结果。图4（e）（f）分别为StC刺激模式下，前额叶脑区第9导联和顶枕叶脑区第71导联的ERP 波形显示结果。图4（g）（h）分别为StI刺激模式下，前额叶脑区第10导联和顶枕叶脑区第89导联的ERP波形显示结果。从图4（a）（c）（e）（g）中可以看出前额叶脑区多动症儿童N2振幅峰值比正常儿童要高，从图4（b）（d）（f）（h)可得出顶枕叶脑区多动症儿童P2振幅峰值比正常儿童要低。比较四种刺激模式，虽然 ADHD 组和正常对照组在刺激位置和反映位置不一致的刺激模式（SmI和StI）下，比一致刺激模式（SmC和StC）下的N2振幅略高，但是 $\mathrm { s m C }$ 刺激模式下两实验组的N2、P2的振幅差异最大，因此 $\mathrm { s m C }$ 刺激模式被选择用于后续分析。

# 2.2SmC刺激模式下特征选择

根据实验任务范式，绘制出前额叶和顶枕叶脑区在刺激任务段（潜伏期）中的最佳电极脑电波形，如图5和图6所示。

![](images/8131b4d9c6d12eaed41679df75cb40d3fb83b63d1f4f04aa54903ba6ca1318ae.jpg)  
图5SmC刺激下前额叶脑区潜伏期ERP波形

图5是 $\mathrm { S m C }$ 刺激模式下，ADHD儿童和正常儿童前额叶脑区第9导联最佳电极潜伏期ERP波形的显示结果。图6是 $\mathrm { s m C }$ 刺激模式下，ADHD儿童和正常儿童前额叶脑区第67导联最佳电极潜伏期ERP波形的显示结果。从图中可以清楚地发现在

SmC刺激模式下，ADHD儿童和正常儿童脑电幅值差异明显，此特征可用于对两者进行分类。

![](images/8ea855a63c735938cd04a50397df1c6e7476c352f0819d5b1d3cbac6922d06c9.jpg)  
图6 $\mathrm { s m C }$ 刺激下顶枕叶脑区潜伏期ERP波形

# 2.3前额叶和顶枕叶脑区最佳电极共特征的提取

同一种刺激模式下根据前额叶和顶枕叶脑区脑电表现出的不同，使用共空间模式算法CSP对两个脑区的电极数据进行特征提取并将其可视化，如图7所示。通过四种刺激模式的共特征可以发现，只有 $\mathrm { S m C }$ 刺激模式下的特征易于区分。因此，利用SmC刺激模式下两脑区共特征进行分类能有效区分多动症儿童和正常儿童。

# 2.4常规方法分类结果

使用常规的AdaBoost分类器和Bagging分类器对CSP 提取到的两个脑区最佳电极的脑电共特征进行分类，选择SmC刺激模式下最具有区分性的脑电共特征，两种分类器的迭代训练错误率曲线如图8所示。

# 2.5深度学习分类结果

LSTM网络训练脑电样本数据集的ROC曲线如图9所示，从图中曲线可清楚地看出，每次训练迭代过程中分类正确率大小呈递增趋势，相反由损失函数计算得出的损失率大小呈递减趋势。在经过20次迭代训练后其分类正确率趋于稳定且高达$90 \%$ 以上，而损失率低至 $0 \%$ 左右。

![](images/576da41a81e965df933684956ef20b8f40651d128b0f719b18ceae564d147626.jpg)  
图7脑区最佳电极间共特征

![](images/cde4e3219b4c7ad567762f3b2ba06d1604ee20ea777bc3e55d36ae646fede6ae.jpg)  
图8迭代训练错误率曲线

![](images/3645fd2caa392387dee10f7cc99a10f36f48e4c46575b11f0d6c620fbe5bc1f1.jpg)  
图9LSTM训练ROC曲线

# 2.6 分类结果比较

两类方法的比较结果如表3所示，其分类率都在 $90 \%$ 以上，而LSTM方法要高于常规方法2.03个百分点。相比常规分类器，LSTM深度学习方法仅在少量的迭代次数下其分类率即趋向稳定，且在ADHD儿童和正常儿童的训练和测试过程中始终保持着较高的分类率，测试样本分类率高达 $9 5 . 7 8 \%$ 。

表3分类结果比较  

<html><body><table><tr><td rowspan="2"></td><td colspan="2">SmC 刺激模式</td></tr><tr><td>分类器 训练样本分类率</td><td>测试样本分类率</td></tr><tr><td>LSTM</td><td>99.98%</td><td>95.78%</td></tr><tr><td>AdaBoost</td><td>98.12%</td><td>93.75%</td></tr><tr><td>Bagging</td><td>97.21%</td><td>91.44%</td></tr></table></body></html>

# 3 结束语

常规特征提取和分类方法虽在数据处理速度上占有优势，但需手动选择特征，且特征的选择较为单一，这种局限性在对大量数据处理时尤为突出。而深度学习方法无须人工干预，可自动学习特征，学习到的特征包含有更多隐含信息，利于分类率的提高，有助于提高诊断的准确性。另一方面，常规方法每次分类都因输入数据的差异而重新建立训练模型，数据变化对模型影响较大，不具有较好的容错性。深度学习LSTM方法能够基于大样本数据建立起统一的训练模型。随着计算机硬件的提升发展，深度学习方法与常规方法在处理多导脑电数据的速度差异将逐渐减小，深度学习的优势将更加明显。

本研究采用干扰控制任务的空间整合范式，通过深度学习LSTM方法自动完成脑电信号的特征学习和分类，并与常规分类器AdaBoost和Bagging进行对比，LSTM方法分类准确率高达 $9 5 . 7 8 \%$ 。研究初步认为，SmC刺激模式下，ADHD组和正常对照组不同脑区组内叠加平均后的ERP振幅差异最为显著，其ERP特征能够高效区分ADHD儿童和正常儿童，为临床对ADHD儿童个体化诊断提供了重要的科学依据。

# 参考文献：

[1]Salari R,Bohlin G,RydellAM,et al.Neuropsychological functioning and attachment representations in early school age as predictors of adhd symptoms in late adolescence [J].Child Psychiatry & Human Development, 2017,48 (3): 370-384.   
[2]Salomone S,Fleming GR,Bramham J,et al.Neuropsychological deficits in adult ADHD:evidence for differential attentional impairments,deficient executive functions,and high self-reported functional impairments [J]. Journal of Attention Disorders,2016,1-12.   
[3]Ma I,van Holstein M,Mies G W,et al. Ventral striatal hyperconnectivity during rewarded interference control in adolescents with ADHD[J].Cortex; a journal devoted to the study of the nervous system and behavior,2016,82- 225.   
[4]邹凌，杨娇娇，王苏弘，等．基于脑电主成分分析和k-最近邻的多动症 儿童与正常儿童分类研究[J].生物医学工程杂志,2016,33(2):232- 238.   
[5]Billinger M,Brunner C,Muller-Putz G R,et al. Single-trial connectivity estimation for classification of motor imagery data [J].Journal of neural engineering,2013,10 (4): 1-8.   
[6]Wang Y,Wang Y T,Jung TP,et al.Translation of EEG spatial filters from resting to motor imagery using independent component analysis [J].Plos One,2012,7(5): 1-12.   
[7]LeCun Y,Bengio Y, Hinton G,et al. Deep learning [J]. Nature,2015,521 (7553): 436-444.   
[8]Soleymani M,Asghari-Esfeden S,Fu Y,et al.Analysis of EEG signals and facial expressions for continuous emotion detection [J].IEEE Transactions on Affective Computing,2016,7(1): 17-28.   
[9]Davidson PR,JonesRD,Peiris MTR,et al.EEG-based lapse detection with high temporal resolution [J].IEEE Transactions on Biomedical Engineering,2007,54 (5): 832-839.   
[10] Dong H, Supratak A,Pan W,et al. Mixed Neural Network Approach for Temporal Sleep Stage Classification [J]. IEEE Trans on Neural Systems and Rehabilitation Engineering,2017,99:1-11.   
[11] Michelini G,Kitsune G L,Hosang G M, et al. Disorder-specific and shared neurophysiological impairments of attention and inhibition in women with attention-deficit//hyperactivity disorder and women with bipolar disorder [J]. Psychological medicine,2016,46 (3): 493-504.   
[12] Xie L,Ren M,Cao B,et al. Distinct brain responses to different inhibitions: Evidence from a modified Flanker Task [J]. Scientific Reports,2017,7(1): 1-10.