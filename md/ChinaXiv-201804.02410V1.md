# 基于训练样本评估的CSP滤波器增量更新方法

韩震宇，刘锦，吴小培(安徽大学 计算机科学与技术学院，合肥 230039)

摘要：由于脑电图(electro encephalo gram，EEG)能反映不同状态下大脑的思维活动，因此，基于EEG的运动想象识别已经成为一个新的研究热点。为了降低低质量样本对 CSP(common spatialpaterm)滤波器模型的组间传输性能的影响，提高正确率，提出了一种基于样本筛选的CSP滤波器增量更新方法。首先通过样本筛选的方法对 EEG数据进行质量评估，然后剔除低识别率对应的单次训练数据，最后对优化后的样本所设计的CSP滤波器进行增量更新。实验室环境下，对EEG信号进行运动想象识别，其平均正确率达到 $8 0 . 9 2 \%$ ，相比传统的CSP方法，五位受试者测试集的平均识别率分别提高了 $5 . 4 \%$ 、 $5 . 6 \%$ 、 $1 . 5 \%$ 、 $8 . 6 \%$ 和 $7 . 7 \%$ ，实验结果验证了所提算法的有效性。

关键词：脑电图；共同空间模式；样本筛选；增量更新中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.01.0074

# Incremental updating algorithm for CSP filter based on training sample evaluation

Han Zhenyu, Liu Jin,Wu Xiaopei† (Collegeof Computer Science&Technology Anhui University,Hefei23o039,China)

Abstract:Electroencephalogram(EEG)canreflectthethinkingactivityoftebrainunderdiferentconditions,therefore,motor imagery recognition based on EEG has become anew research hot spot.Toreduce the influence oflowqualitysamples on the session-to-sesiontransferperformance ofCSPfiltermodelsandimprovetherecognitionaccuracyratio,this paper proposedan incrementalupdatingalgorithmforCSPfilterbasedontrainingsample evaluation.Totart with,itusedsample selectionmethod to evaluate thequalityofEEGdata.Thenitremovedasetof trainingdatacorrespondingtolowrecognitionrate.Finaly,it updated the CSP filter incrementally which designed by the optimized sample.In label environment,the motor imagery recognition of EEG signals reaches average accuracy of $8 0 . 9 2 \%$ . Compared with the traditional CSP method, the average recognition rate of the five subjects' testing sets increases by $5 . 4 \%$ $5 . 6 \%$ $1 . 5 \%$ $8 . 6 \%$ ,and $7 . 7 \%$ ,respectively.The experimental results verify the effectiveness of the proposed algorithm.

Key words: electroencephalogram; common spatial pattern; samples selection; incremental update

# 0 引言

对于神经肌肉系统功能严重丧失的患者，与外界环境的信息交互变得异常困难甚至无法正常交流[12]，使患者的生活质量降低，给家庭和社会造成十分沉重的负担。脑一机接口是一种计算机设备与人类之间的非肌肉通信系统[3,4]，通过检测用户的大脑信号，为那些不能移动、说话或者眨眼的患者提供了一个强大的工具[5]。脑机一接口(brain-computer interface,BCI)通过提取大脑信号特征，并将这些特征转换成控制设备或者屏幕上光标的命令，因此允许用户在不使用肌肉控制或者言语的情况下控制计算机设备。BCI也在医疗康复[和精神状态检测[7]中得到应用。

当人在执行某个肢体运动或者想象运动时，大脑皮层的某个区域中脑电信号会发生变化，这类现象伴随着脑电信号能量的增加和减少。将脑电信号能量减少称为事件相关去同步(event-relateddesynchronization,ERD)，能量增加称为事件相关同步(event-related synchronization,ERS)[8.9]。在 EEG 节律信号中，mu 节律信号 $( 8 { \sim } 1 2 ~ \mathrm { H z } )$ 和beta 节律信号 $( 1 8 { \sim } 2 6 ~ \mathrm { H z } )$ 是ERD/ERS现象相关的固定频率信号[10]。例如受试者进行左手和右手运动想象时，大脑对侧运动皮层的mu和beta节律被抑制。

CSP作为一种EEG分析工具，可以有效地提取ERD/ERS相关特征[II]，利用CSP对两分类训练样本进行特征提取时，产生的特征向量互不相关，相互独立，可以很好地用来进行分类。在不同时间的运动想象实验中，必须对CSP滤波器重新训练，并调整特征。在CSP滤波器进行训练时，无法判断训练数据的优劣，由于CSP是一种空间滤波器，与标签信息不匹配或者运动想象不明显的低质量训练数据会严重影响CSP滤波器的设计性能[12]。假设在运动想象实验中受试者运动皮质中的源的位置及其产生的信号频谱含量是相对恒定的，每当获取新的EEG数据时，可以通过批量学习所收集的数据构建临时系统。但是由于系统需要保持巨大的存储器来存储先前学习或新收集的数据，所以这种系统的运行需要大内存和高计算费用。此外，即使在以前的训练中已经学习了 $9 9 . 9 \%$ 的数据，该系统也必须舍弃过去所学的知识，并且每当获得新样本时，就要从一开始重复学习。为了提高CSP滤波器泛化的性能，近年来人们提出了一系列针对传统CSP的改进和优化方法，如正则化共同空间模式(regularized common spatial pattern,RCSP)，以及增量CSP 和自适应CSP等[13\~15]。然而这些改进并未涉及训练样本的优化选择问题。

针对以上问题，本文提出一种基于EEG训练样本筛选的CSP 滤波器增量更新方法。通过对单次EEG样本筛选并剔除低质量单次训练数据[16]，与CSP滤波器增量更新相结合。基于这种方法，确保了特征的一致性。实验结果表明，经该方法所设计的CSP滤波器能更准确地检测到任务相关神经活动信息，有效提高了BCI系统的识别性能。

# 1 数据集

本文所用数据集为实验室自主采集的两类运动想象数据(http://iiphci.ahu.edu.cn/resources.php），采集设备为美国NeuroScan公司生产的40导脑电放大器、电极帽、采集软件和连接线等。电极的安放位置严格按照国际10/20电极导联定位标准。数据采集设备的电极分布如图1所示。数据采样频率为$2 5 0 ~ \mathrm { H z }$ ，所得标准数据集中含2 导联眼电(Electrooculargram,EOG)数据和14导联运动想象EEG数据，电极的位置为VEOU、VEOL、Fp1、Fp2、FC3、FCz、FC4、C3、Cz、C4、CP3、CPz、CP4、O1、Oz和O2。

![](images/c00dfd738ff03849bd58b552a9a7a8d4ea5a2126374664bc609db824ce6079ea.jpg)  
图1实验电极分布图

采集单次EEG数据的时间为 $1 0 \mathrm { ~ s ~ }$ ，0\~1s电脑黑屏并发出“beep”提示音，受试者听到声音后开始准备运动想象，1s后电脑屏幕出现向左或向右的红色箭头，受试者根据箭头方向进行左手或者右手运动想象，直至第6s结束。受试者休息4s并等待下一次实验开始。实验范式如图2所示。在本文后续章节的CSP滤波器设计中，均选用了位于运动皮层附近的9导联EEG 数据(FC3、FCz、FC4、C3、Cz、C4、CP3、 $\mathrm { C P z }$ 和 CP4)。选取单次EEG数据中 $0 . 5 { \sim } 5 \mathrm { ~ s ~ }$ 时间段作为有效运动想象数据段。另外，对于所有受试者的运动想象数据集，均选取ERS/ERD现象比较明显的mu 节律频带 $( 1 0 { \sim } 1 4 \mathrm { H z } )$ 滤波数据[17]。

![](images/ae45355d34b917e98959dcf841cc3d2d955d17d5b11c15e22b4e796a7ff2db76.jpg)  
图2单次运动想象实验范式图

# 2 方法

# 2.1共同空间模式(CSP)

在两分类的BCI中，CSP算法已经被证明是一种有效的特征提取方法，通过空间投影寻找最优的投影方向，使其中一类信号方差最大(如左手想象运动)，另一类信号方差最小(如右手想象运动)，从而实现分类的目的[18]。设单次实验EEG为矩阵 ${ \cal E } _ { N \times T }$ ，其中： $N$ 为导联数； $T$ 为每个导联采样点数。则可得到标准的空间协方差矩阵为

$$
C _ { i } = \frac { E _ { i } E _ { i } ^ { T } } { t r a c e ( E _ { i } E _ { i } ^ { T } ) }
$$

其中： $i$ 代表运动想象类别； $L$ 为左手想象运动； $R$ 为右手想象运动；trace(:)表示矩阵的迹。两类平均协方差矩阵之和为

$$
\boldsymbol { C } = \overline { { \boldsymbol { C } } } _ { L } + \overline { { \boldsymbol { C } } } _ { R }
$$

对 $c$ 进行特征值分解：

$$
\boldsymbol { C } = \boldsymbol { U } \boldsymbol { \Lambda } \boldsymbol { U } ^ { T }
$$

其中： $\pmb { U }$ 是特征向量矩阵； $\boldsymbol { A }$ 是由非零特征值组成的对角矩阵，并且降序排列。从而得到变换矩阵 $P$ 为

$$
P = \Lambda ^ { - \frac { 1 } { 2 } } U ^ { T }
$$

将其与左、右两类协方差矩阵平均值进行变换，有

$$
H _ { \scriptscriptstyle L } = P \overline { { C } } _ { \scriptscriptstyle L } P ^ { \scriptscriptstyle T } , H _ { \scriptscriptstyle R } = P \overline { { C } } _ { \scriptscriptstyle R } P ^ { \scriptscriptstyle T }
$$

则 $\pmb { H } _ { L }$ 和 $H _ { R }$ 有相同的特征向量 $\pmb { B }$ ，且对应的特征值之和为1。 即

$$
H _ { \scriptscriptstyle L } = B \lambda _ { \scriptscriptstyle L } B ^ { T } , H _ { \scriptscriptstyle R } = B \lambda _ { \scriptscriptstyle R } B ^ { T } \mathrm { H } \lambda _ { \scriptscriptstyle L } + \lambda _ { \scriptscriptstyle R } = I
$$

其中： $\boldsymbol { \mathit { I } }$ 为单位阵。由于两类想象任务的特征值之和为1，即在$H _ { L }$ 特征值最大的方向上， $H _ { R }$ 的特征值最小；反之亦然，使两类信号差别最大。投影矩阵 $\pmb { W }$ 可得

$$
W = B ^ { T } P
$$

$\pmb { W }$ 是一个 $N { \times } N$ 的矩阵， $\pmb { W }$ 的行称为空间滤波器， $\pmb { W }$ 的列

称为空域模式。原始信号 $\boldsymbol { \mathscr { X } }$ 可以通过空间滤波器 $\pmb { W }$ 得到新的信号 $z$ 。

$$
Z = W X
$$

经过CSP处理以后，由 $\pmb { W }$ 的前几行滤波产生的信号，在属于类别L时方差最大，属于类别R时方差最小，而 $\pmb { W }$ 的后几行滤波产生的信号则相反。在本文中对CSP滤波器的输出进行分类时，选用基于方差比较的简单分类准则(零训练分类器)替代常用的机器学习分类器，具体分类准则如图3所示。

![](images/7ee0a110446beec0f358c84ba18b060de9e472d58b97238616bacb4e68369fc5.jpg)  
图3基于方差比较的分类准则

# 2.2基于单次样本对的CSP

EEG数据的采集过程中，受试者很难一直保持高度精力集中的状态，并且正确地想象左右手动作。因此，不可避免地会产生与标签不匹配的低质量单次训练数据。低质量的训练数据会严重影响CSP 滤波器的性能。基于单次样本对的CSP(single-trial-basedCSP,s_CSP)的目的是把这些无法通过人工检查的低质量的数据进行剔除，从而提高CSP滤波器的性能。图4和5分别给出了单次EEG 样本对在不同情况下设计的空间滤波器在头皮电极的投影。

![](images/303ab0be6fb7f6a7d2ac2335f56c15d8a9059d21b2f1e86ce70b5f074606f59a.jpg)  
图4正常的左右手空间滤波器在头皮电极的投影

![](images/476048bd379841da60d92eb319ccbdb325ddcbd65d31615f538ed8e03773fdbb.jpg)  
图5低质量的左、右手空间滤波器在头皮电极的投影

s_CSP的设计步骤与传统CSP滤波器基本一致。区别在于设计s_CSP滤波器时，仅用单次EEG数据的协方差矩阵替换传统方法中采用的平均协方差矩阵。把采集的原始训练样本分为左手、右手两个子集： $X _ { L } { = } \{ x _ { l } ( 1 ) , \ x _ { l } ( 2 ) , \ x _ { l } ( 3 ) , { \ldots } , \ x _ { l } ( n ) \}$ 和$X _ { R } { = } \{ x _ { r } ( 1 ) , x _ { r } ( 2 ) , x _ { r } ( 3 ) , { \ldots } , x _ { r } ( m ) \}$ 。其中 $x _ { l } ( i )$ 是标签信息为左手的单次运动想象训练数据； $x _ { r } ( j )$ 是标签信息为右手的单次训练数据； $X _ { L }$ 和 $X _ { R }$ 分别包含左、右手单次EEG数据 $n$ 次和 $\mathbf { \nabla } _ { m }$ 次。s_CSP算法具体实现步骤如下：

a)分别从 $X _ { L }$ 和 $X _ { R }$ 中取出 $x \iota ( i )$ 和 $x _ { r } ( j )$ 设计CSP 滤波器，得到CSP 滤波器组 $\{ W _ { L } ( i ) , W _ { R } ( j )$ ;其中 $\scriptstyle i = 1 \ldots n , j = 1 \ldots m \}$ 。

b)用所得 $m { \times } n$ 个CSP滤波器分别对该组训练集进行运动想象分类，将得到的 $m { \times } n$ 个识别率存放于二维矩阵 $\scriptstyle R _ { m \times n }$ 中。

c)分别求矩阵 $\pmb { R } _ { m \times n }$ 行和列的平均识别率 $\pmb { { \cal D } } _ { - } { \pmb R }$ 和 $\pmb { D } _ { - } \pmb { L }$ 。

d)剔除 $\pmb { D } _ { - } \pmb { R }$ 和 $\pmb { D } _ { - } \pmb { L }$ 中低识别率所对应的单次EEG数据，得到两个子集 $X _ { L } \prime { = } \{ x _ { l } ( 1 ) , x _ { l } ( 2 ) , x _ { l } ( 3 ) { , } . . . , x _ { l } ( n { - } g ) \}$ 和 $X _ { R } { ' } { = } \{ x _ { r } ( 1 )$ $x _ { r } ( 2 ) , x _ { r } ( 3 ) , . . . , x _ { r } ( m { - } h ) \}$ 。其中：输出 $X _ { L }$ 和 $X _ { R }$ 为原始训练样本通过 $\mathrm { \bf s \underline { { \bf \Lambda } } C S P }$ 算法将低质量单次训练数据剔除后的左手、右手两个训练数据子集； $g$ 和 $h$ 分别是剔除的单次左、右手EEG数据的个数。具体剔除多少低质量单次训练数据达到最优化，可以通过多组数据的组间交叉测试识别率决定[16]。在本文的后续研究中，通过对识别率向量 $\pmb { D } _ { - } \pmb { R }$ 和 $\pmb { D } _ { - } \pmb { L }$ 设置一个阈值，对于识别率低于阈值的单次训练数据，将其作为低质量训练数据并剔除。

图6为矩阵 $\pmb { R }$ 的可视化表达图。图中横坐标代表单次左手实验，纵坐标代表单次右手实验。每个方格代表所对应的单次左手与右手实验数据所设计的s_CSP滤波器的对应识别率。图6(b)为受试者 S2的其中一组训练样本。从图中可以看出第4、12和13次右手实验的识别率较低，其中平均识别率分别为$5 0 . 4 6 \%$ 、 $56 . 7 7 \%$ 和 $4 8 . 6 9 \%$ ，应视为低质量数据将其剔除。

![](images/592b5388305a72f99390a19c052edc29a10a7a39e64e5458bd7ede18da733dac.jpg)  
图6基于单次样本对的识别率矩阵图

![](images/5f97c8d67b5d431eff04226fe99041b495b2301681e4b0888d82bd81f5118929.jpg)  
(a)数据集S3_C在 $1 4 \mathrm { ~ s ~ }$ 时标签信息为1(左手)的脑电信号图

![](images/beae36e2f64c2d3d437b5cfb04cad4398ddb42aa93a6c17f1650bf819c8f80a7.jpg)  
(b)数据集 S2_C在106s时标签信息为2(右手)的脑电信号图

图7为采集的单次运动想象脑电信号图。其中图7(a)为数据集S3C在14s时第1次标签为1(左手)的正常想象脑电图。从图6(a)可视化表达矩阵图中可以看到，此次单次左手实验与24个单次右手实验所设计的sCSP滤波器在进行交叉测试时都有较高的识别率，所以可以视为高质量数据将其保存。而图7(b)为数据集 S2_C在 $1 0 7 \mathrm { ~ s ~ }$ 时第12次标签为2(右手)的异常想象脑电图。从图6(b)可以看到，此次右手单次实验与所有单次左手实验所设计的s_CSP滤波器对应的识别率较低，平均识别率仅有 $56 . 7 7 \%$ 。这是由于运动想象受到干扰或者精神不集中的影响，导致EEG数据干扰比较严重，所以应视为低质量数据将其剔除。

# 2.3CSP滤波器增量更新

增量学习是指一个学习系统能不断地从新样本中学习新的知识，并能保存以前已经学习到的知识。就是每当新增数据时，并不需要重建所有的知识库，而是在原有知识库的基础上，仅作由新增数据所引起的更新[19]，具有存储空间占用少、更新速度快等特点。通过单次样本对的CSP滤波器的设计，将低质量单次左、右手想象EEG数据剔除，通过式（9）对采集的多组EEG数据的空间协方差矩阵进行增量更新。

$$
\overline { { C } } _ { i } ^ { n e w } = \overline { { C } } _ { i } ^ { o l d } + \frac { C _ { i } - \overline { { C } } _ { i } ^ { o l d } } { n }
$$

其中： $\overline { { C } } _ { i } ^ { o l d }$ 和 $\overline { { C } } _ { i } ^ { n e w }$ 是 CSP 滤波器空间协方差矩阵更新前和更新后； $C _ { i }$ 为当前采集的单次EEG数据的空间协方差矩阵；$n$ 为设计CSP 滤波器所用的全部单次EEG 数据的总和。如果得到的空间协方差矩阵为一组EEG数据的平均协方差矩阵时(如式（2）所示)，可以通过式（10）进行增量更新。

$$
\overline { { C } } _ { i } ^ { n e w } = \frac { n \overline { { C } } _ { i } ^ { o l d } + m \overline { { C } } _ { i } } { n + m }
$$

其中： $\overline { { C } } _ { i }$ 为当前采集的一组 EEG 数据的平均协方差矩阵； $\mathbf { \nabla } _ { m }$ 是这组EEG数据左右手运动想象次数的总和； $n$ 为CSP滤波器更新前全部单次EEG数据的总个数。通过增量更新算法得到空间协方差矩阵，并重新设计CSP 滤波器。这样，对CSP滤波器的增量更新，就能得到一个对单个受试者最优的CSP滤波器图8展示了两位受试者的训练数据所设计的空间滤波器增量更新前后在头皮电极的投影。在滤波器增量更新后，其投影更接近真实左、右手运动想象空间滤波器的投影。选取受试者S1和S2 的各五组实验数据(A、B、C、D、E)，其中S1_C 和 S2_D作为测试数据，每个受试者的其他四组实验数据作为训练数据，每组数据通过s_CSP进行样本筛选，证明算法的性能。S1_C和S2_D组数据在滤波器增量更新时的识别率如图9所示。从图9可以看出，测试数据S1_C和S2_D的识别率在CSP 滤波器更新以后不断提高。

![](images/089acc3c1690792dd514499d60e8514b4a6dcb20d1ce8a057e46b77aad631fc4.jpg)  
图7单次运动想象脑电信号图  
图8受试者训练数据所设计的空间滤波器在头皮电极的投影

![](images/fee20fcae7d38924eef31ce6d2f7584b348e7cb6b22d488601ef4922965ff128.jpg)  
图9S1_C和S2_D组数据在滤波器增量更新时的识别率

# 3 实验结果

五位受试者{S1(HX),S2(CB),S3(RJ), S4(LWC),S5(JX)}参与了本次实验(2位男性，年龄在23\~25岁之间，均参加过多次运动想象实验)，每位受试者采集五组数据集(非同天)，分别表示为A、B、C、D、E。运动想象类型为左手和右手，每组数据集由50个单次EEG数据构成，左手26次和右手24次，并对原始EEG数据进行 $0 . 5 { \sim } 1 0 0 \mathrm { H z }$ 的带通滤波和 ${ 5 0 } \mathrm { H z }$ 的工频陷波处理。

需要注意的是，CSP作为一种有监督设计方法的空间滤波器，不仅对训练样本的质量要求较高，对训练样本的数量也较为敏感，少量的标签样本也会严重影响滤波器性能。因此，在训练样本筛选的过程中，应避免大量地剔除质量相对较差的单次实验数据[I6]。在进行CSP滤波器增量算法之前，通过s_CSP方法把训练样本中低质量数据剔除。对测试数据进行分类时，选用该受试者其他四组数据作为训练数据。图10列出了标准CSP和s_CSP方法以及基于训练样本评估的CSP滤波器增量更新方法在交叉验证下的分类识别率。当对一位受试者的一组数据进行测试时，将该受试者的其他四组数据作为训练数据。

图11给出了在三种方法下五位受试者EEG数据识别率的均值。从图中可以看出，相比较于标准CSP算法，基于训练样本评估的CSP 滤波器增量更新算法对受试者组间的运动想象数据测试识别率有了明显提高。五位受试者五组测试集的平均识别率分别提高了 $5 . 4 \%$ 、 $5 . 6 \%$ 、 $1 . 5 \%$ 、 $8 . 6 \%$ 和 $7 . 7 \%$ 。若原始训练数据质量相对较好时，s_CSP方法对分类识别率没有显著的提高，而基于训练样本评估的CSP滤波器增量更新方法可以有效地提升滤波器的性能，提高分类识别率。对于质量相对较差的训练数据，若剔除低质量训练样本数量较少，增量更新算法会使滤波器的性能得到显著提升，如数据集S4_A、S4_B、S4_C；若剔除低质量训练样本数量较多，将会使滤波器的性能变差，如数据集 S3_D、S4_D。总体上看，基于训练样本评估的CSP滤波器增量更新算法对提高受试者的组间传输性能，即泛化性能有较大帮助。

![](images/c1c58df76c3bdcd76bc35223b7579ce6d0e2108a7cb82abbacf4dfebdcb62d4d.jpg)  
图10五位受试者的五组实验数据在不同方法下的识别率/%

![](images/5804cc7c7b8feaba11eb8a63149f29c2ad9746fc6a7a03893fde145bc7d6068a.jpg)  
图11每位受试者五组实验数据平均识别率 $\%$

# 4讨论

CSP作为一种有监督的空间滤波方法，其优点在于简单方便、复杂度低，可以有效地对两类运动想象信号进行分类。但是在有监督模型学习过程中，低质量训练样本(或噪声样本)往往是造成“过学习”现象的主要原因之一。在BCI系统的实现中，“过学习”问题也是需要解决的主要问题。即基于训练集设计的CSP滤波和分类器模型在组间和不同受试者间的分类测试实验中，往往不具备良好的迁移性。对于BCI系统的在线实验，必须要对CSP滤波器重新训练，调整特征。若采集少量的训练数据设计CSP滤波器，则会降低滤波器的性能，并且采集过程中无法人工判断训练数据的优劣，与标签信息不匹配的训练数据也会影响滤波器的性能。若在实验过程中采集更多的训练数据，对实验操作者和受试者是一种考验，受试者在长时间的采集过程中容易出现疲劳以及注意力不集中等问题，实验设备的故障率也会增加，这都会影响训练样本的采集质量。因此，在本文中首先使用受试者之前采集的大量训练数据提前设计出CSP 滤波器，然后在实验过程中受试者只需要进行少量的单次运动想象实验，最后通过增量更新算法即可设计出一个新的具有良好迁移性能的空间滤波器。

CSP方法不依赖真实物理模型，虽然这一特点简化了CSP滤波器的设计过程，但也是造成“过学习”现象的原因之一。在相关研究中，独立分量分析方法(independentcomponentanalysis,ICA)在BCI系统中实现[20]。研究结果表明，ICA方法的泛化性能相比CSP方法有明显改善，这与ICA方法的盲源分离性能以及隐含利用真实物理模型信息有关[2I]。不过ICA空间滤波器设计过程相对复杂，并对初始参数和EEG导联分布的设置敏感。迁移学习[22]的目标是从一个或者多个源领域任务中提取有用信息，并将其用在新的目标任务上，本质上就是信息的迁移再利用。所以在迁移学习方法中，可以不需要大量的训练数据。Jayaram等人[23]通过域适应方法以及规则适应的方法，实现了迁移学习在BCI系统中的应用，证明了迁移学习在BCI系统中的有效性。

# 5 结束语

本文基于训练样本质量的优劣对CSP滤波器影响的思想，通过增量学习的方法，结合对EEG单次数据的筛选以及CSP滤波器增量学习的设计，将大量的训练数据进行学习并应用于测试数据。实验结果验证了本文方法的有效性，低质量数据对CSP 滤波器更新时所造成的影响得到初步解决。本文虽然使用了传统CSP方法中两类运动想象模式，但是经实验验证，CSP方法也可以直接应用到多类模式，所以接下来的研究将围绕多类模式进行。虽然经过单次样本优化后所设计的滤波器性能已得到明显改善，但CSP滤波器对于不同受试者间的模型并不具有良好的迁移性能。因此，在未来希望可以通过迁移学习的思想，进一步优化EEG数据以及CSP滤波器，使EEG数据的差异降到最小，进而提高运动想象分类识别的准确率，从而解决BCI系统的问题。

# 参考文献：

[1]Wolpaw JR,Birbaumer N,McFarland D J,et al.Brain-computer interfaces for communication and control[J]. Clinical neurophysiology,2oo2,113 (6): 767-791.   
[2]Alotaiby T,El-Samie FEA,Alshebeili SA,et al.A review of channel selection algorithms for EEG signal processing [J].EURASIP Journal on Advances in Signal Processing,2015,2015 (1): 66.   
[3]Dormhege,Guido,ed Dornhege G,Millan JD R,Hinterberger T.Toward brain-computer interfacing [M]. [S.1.] $\vdots$ MIT Press,2007.   
[4]Vallabhaneni A,Wang T,He B. Brain-computer interface [M]// Neural Engineering.2005: 85-121.   
[5]Birbaumer N, Ghanayim N,Hinterberger T, et al.A speling device for the paralysed [J]. Nature,1999,398 (6725): 297-298.   
[6] Daly JJ，Wolpaw JR.Brain-computer interfaces in neurological rehabilitation [J]. The Lancet Neurology,2008,7(11):1032-1043.   
[7]Muller KR,Tangermann M, Dornhege G,et al. Machine learning for realtime single-trial EEG-analysis: from brain-computer interfacing to mental state monitoring [J].Journal of neuroscience methods,20o8,167(1): 82-90.   
[8]Toro C,Deuschl G,Thatcher R,et al. Event-related desynchronization and movement-related cortical potentials on the ECoG and EEG [J]. Electroencephalography and Clinical Neurophysiology//Evoked Potentials Section,1994,93 (5):380-389.   
[9]Babiloni C,Carducci F,Cincotti F,et al.Human movement-related potentials vs desynchronization of EEG alpha rhythm:a high-resolution EEG study[J]. Neuroimage,1999,10 (6): 658-665.   
[10] HuangSijuan，WuXiaoming.Symbolfeatureextractionof electroencephalogram for imagery movement based on Mu//beta rhythm [J]. Journal of Clinical Rehabilitative Tissue Engineering Research,2010,14 (43): 8061-8064.   
[11l Zhang Y. Zhou G.Jin J.et al. Optimizing spatial patterns with sparse filter

bands for motor-imagery based brain-computer interface [J].Journal of neuroscience methods,2015,255: 85-91.   
[12] TsuiC SL,Gan JQ,Roberts SJ.A self-paced brain-computer interface for controlling a robot simulator:an online event labelling paradigm and an extended Kalman filter based algorithm for online training[J].Medical & biological engineering& computing,2009,47(3): 257-265.   
[13] Li Y, Sun Y,Taya F,et al.Single trial EEG classification of lower-limb movements using improved regularized common spatial pattern [C]//Proc of the 7th International IEEE//EMBS Conference on Neural Engineering. 2015:1056-1059.   
[14] Zhao Qinbin, Zhang Liqing,Cichocki A,et al. Incremental common spatial pattern algorithm for BCI [C]// Proc of IEEE World Congress on Computational Intelligence;Proc of IEEE International Joint Conference on Neural Networks.2008:2656-2659.   
[15] Mobaien A,Boostani R.ACSP:adaptive CSP filter for BCI applications [C]//Proc of the 24th Iranian Conference on Electrical Engineering.2016: 466-471.   
[16]刘锦，吴小培，周蚌艳，等．单次样本对的CSP滤波器设计及其在脑电 训练样本优化中的应用[J].信号处理,2017,33(7):993-1001.(Liu Jin,

Wu Xiaopei, Zhou Bangyan,et al. CSP filter calculation of single training pairs and its application in EEG training set optimization [J]. Journal of signal processing,2017,33(7): 993-1001.)

[17] Zhou Bangyan，Wu Xiaopei,Lyu Zhao,et al.A fully automated trial selection method for optimization of motor imagery based brain-computer Interface [J].PloS one,2016,11(9):e0162657.   
[18] Li Xinyang,Guan Cuntai,Zhang Haihong,et al.Adaptation of motor imagery EEG classification model based on tensor decomposition [J]. Journal of neural engineering,2014,11 (5): 056020.   
[19]Karp R M.On-line algorithms versus off-line algorithms:how much is it worth to know the future?[C]//Proc of IFIP Congress.1992: 416-429.   
[20]吴小培，周蚌艳，张磊，等.运动想象脑-机接口中的ICA 滤波器设计 [J]．生物物理学报,2014(7):540-554.(Wu Xiaopei,Zhou Bangyan,Zhang Lei,et al.ICA filter desgin in brain-computer interface of motor imagery [J]. Acta Biophysica Sinica,2014(7):540-554.)   
[21] Delorme A,Palmer J,Onton J,et al. Independent EEG sources are dipolar [J].PloS one,2012,7(2): e30135.   
[22] Pan SJ,Yang Qiang.A survey on transfer learning [J].IEEE Trans on Knowledge and Data Engineering,2010,22(10): 1345-1359.   
[23] Jayaram V,Alamgir M,Altun Y,et al. Transfer learning in brain-computer interfaces [J].IEEE Computational Intelligence Magazine,2016,11(1): 20- 31.