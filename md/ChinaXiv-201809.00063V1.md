# 基于时序性面部动作信息的驾驶员状态检测框架

崔子岩ä，汪剑鸣ab，金光浩a

(天津工业大学 a.计算机科学与软件学院;b.电子与信息工程学院，天津 300380)

摘要：在安全驾驶领域，驾驶员的身心状态对于交通安全至关重要。通过网络摄像头获取驾驶员面部视频输入网络进行检测，是检测疲劳等异常驾驶的有效手段。之前的方法主要通过分析驾驶员口型等面部表情来分析是否打哈欠，从而判断是否疲劳驾驶，因此说话等很多类似的状态也被误检为疲劳。针对以上问题提出了一种基于时序性面部动作信息的检测框架，对驾驶员状态进行检测，从而提高检测准确率、降低误检率。该框架主要包含两个关键部分：a）通过检测视频中的脸部轮廓，提取脸部的多种特征，形成面部动作单元；b）通过训练对应的LSTM网络，形成时序性的面部动作单元，根据其相关性进行多种动作单元融合，检测最终驾驶员的状态。在公共YAW-DD数据集上的检测结果表明，相比于现有的方法，准确率提高到了 $9 3 . 1 \%$ ，同时大幅降低了疲劳状态的误检率。

关键词：异常驾驶；时序性信息；面部检测 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.05.0356

# Driver state detection framework based on temporal facial action information

Cui Ziyana, Wang Jianminga, b, Jin Guanghaoat (a.ScholofComputerScience&Software,b.SholofElectronics&InformationEngineering,TianjinPolytechnic University Tianjin 300380, China.)

Abstract:Inthefeldofsafedriving,thedriver's physicaland mentalstateiscritical totraficsafety.Itisaneffective means to detect abnormal driving such as fatigueby detecting the driver's face video input network through a webcam.The previous method mainlyanalyzes the facial expresions such as the driver's mouth shape to analyze whether ornotto yawn,thereby judging whetherornotfatiguedriving,andthereformanysimilarstatessuchasspeakingarealso mistakenlydetectedasfatigue. Aimingattheabove problems,adetection framework basedonsequential facial motion information is proposed todetectthe driver's state,thus improvingthe detection accuracyandreducing the false detectionrate.The framework mainlyconsistsof two keyparts:(1)bydetecting thecontourofthefaceinthevideo,extracting various featuresofthefacetoformafacialaction unit;and(2)formingasequentialfacialactionbytraining thecorrespondingLSTMnetwork.Theunitperformsapluralityof actionunit fusionsaccording to itscorrelationtodetecte stateofthfialdriver.Thetestresultsonthe publicYAW-DDdata set show that the accuracy rate is increased to $9 3 . 1 \%$ compared with the existing method,and the false detection rate of the fatigue state is greatly reduced.

Key words:abnormal driving; temporal information; facial action coding system

# 0 引言

进行判断和评估是十分重要的。

除自然灾害外，交通事故是造成死亡人数最多的灾害之一，同时也会造成重大的财产损失[1].据查证,造成交通事故的原因有驾驶员状态、车辆状况、天气情况和道路状况，其中有 $9 5 \%$ 的事故原因是由驾驶员状态造成的。因此对驾驶员的驾驶状态

一般来说，检测驾驶状态异常的技术可以分为两类[2]。一是指道路或车辆相关因素[3]的环境,二是关于驾驶员的行为，本文的研究重点是对驾驶员的状态进行检测，从而判断驾驶员状态是否异常。驾驶员状态异常主要有以下的类别：疲劳驾驶、酒后驾车、愤怒驾驶和分心驾驶[4]。现有许多基于视觉分析的驾驶员疲劳检测系统，将摄像机安装在仪表板上，并将摄像机直接对准驾驶员的脸部，主要捕捉面部和眼睛特征，进而对驾驶员的状态进行判别。

通过监视设备来获取驾驶视频，并通过计算机视觉的方法[5]来区分驾驶状态，是一种投入成本少、快捷的方法。在论文[回中，提出了一种基于眼睛状态，及头部姿势的监测驾驶过程中的驾驶员状态的方法。他们的结果表明，可以通过结合眼睛和头部信息来实现更为有效的驾驶员状态检测。McCall等人使用的司机行为推理（DII）[7的方法，来代替轨迹预测（TF)方法。DII方法推断驾驶员是否故意变换车道，并且预测车辆会不会通过车道边界，而不管驾驶员的状态如何。

这些工作虽然在很多方面实现了更为有效的驾驶员状态检测，但基于视频的疲劳检测仍然充满挑战。主要因为照明条件变化，头部姿态变化和时间依赖性等原因。特别是，头部姿势的大的变化幅度，会导致视频中的面部形状的严重变形，这使得常规方法难以提取有效的数据。基于对齐脸部点[8的方法是表示疲劳特征的更好的方式，然而，忽略视频中的时间关系，意味着它不能有效区分正常的眨眼和因疲劳引起的眨眼。因此论文通过收集时间信息，区分具有时间上的长期依赖性的状态，如打呵欠和说话。

由于人类行为及脸部表情的复杂性，本文提出了一个基于时序性信息的，多特征融合的面部动作识别框架，来对驾驶员的驾驶状态进行一个综合性判别。首先本文基于驾驶员的面部视觉信息对驾驶员面部状态，采用编码系统（FACS）对驾驶员的面部肌肉动作等进行判断。接下来通过数据的时序信息对多帧数据进行连续性判别，从而更加精准的判别驾驶员的状态。本文采用普通网络摄像头（webcam）用于捕捉视觉信息，研究脸部特征与驾驶员状态之间的关系。本文的方法主要贡献有以下三个方面：a）综合利用面部的多种特征信息，对驾驶员的面部动作进行判别；b)通过连续帧的时序性信息对驾驶员的状态进行判断;c）将面部动作进行强度区分进而更加精准的判别测试人员面部表情信息。本文的方法通过上述改进，建立了更为有效的驾驶员状态检测框架，在提高检测准确率的同时，降低了误检率。

# 1 相关工作

# 1.1面部动作编码系统

面部动作编码系统(FACS)是一种根据瑞典解剖学家Carl-HermanHjortsjo[0]的理论开发的系统，通过脸部外观对人体脸部运动进行分类的系统。Ekman，Friesen 和JosephC.Hager[11]于 2002 年发表了一篇重要的 FACS 系统改进方案[12]。采用FACS系统，对面部外观的轻微不同即时变化来编码，用于检测单个面部肌肉的运动。FACS已经成为一种计算机自动化系统，可以检测视频中的脸部，提取脸部的几何特征，然后生成每个脸部运动的运动特征[13]。

![](images/f6d76115df0056f3146c60738fb8b9bc7d9d50fbf4a34bc726f0ca14a3d5eeb5.jpg)  
图1面部动作编码系统中的面部分解示例

面部动作编码系统（FACS）可以说是行为科学中用于编码面部表情的最广泛使用的方法。该系统根据46个分量运动描述面部表情，大致对应于各个面部肌肉运动。图1显示了一个例子。FACS提供了一种客观而全面的分析面部状态或动作的方式，已经被证明可用于检测人的情感状态。FACS可以编码几乎任何解剖学上可能的面部表情，并将其解构成特定行动单位（AU）来客观描述不同的面部表情。因此在本文中使用该系统来对驾驶员的表情及状态进行判别，通过视频检测下巴（AU17），鼻唇沟深度（AU11），外部（AU2）和内部眉毛提升（AU1）等，进而通过这些行动单位的组合来判断驾驶员此时的状态。

# 1.2 长短期记忆网络

长短期记忆网络（LSTM）是一种特殊的RNN网络，能够学习特征中的时序性信息。LSTM由 Sepp Hochreiter 和 JurgenSchmidhuber于1997年提出，在近些年被 Alex Graves 进行改善并推广。在众多有关时序性问题的检测中，LSTM都取得了不俗的表现。

通过引入LSTM来解决检测中的长期依赖问题。LSTM默认记忆时序性信息，并且不需要多余的消耗。LSTM的巧妙之处在于通过增加输入门，遗忘门和输出门，使得自循环的权重是随时变化的，这样一来在模型参数固定的情况下，不同时刻可以进行动态的积分改动，从而避免了深度神经网络系统中的梯度消失或者梯度膨胀的问题。

在存在时间动态特性的问题中，LSTM网络被应用于连续帧上的空间特性的表示，可以区分具有时间关系的状态，诸如打呵欠和笑，眨眼和闭眼等。因此，本文的框架加入了LSTM网络来挖掘视频中的时间线索。

# 2 本文的方法

众所周知，作为疲劳的表现，昏昏欲睡等状态信息集中在几个主要的面部部位如眼睛、鼻子和嘴巴。说话和愤怒等表情状态的信息同样集中这些面部部位。因此所提出的方法是利用面部动作编码系统来对视频中驾驶员的面部信息进行分析，然后通过面部外观的轻微不同与即时变化来编码单个面部肌肉的运动，再通过组合这些动作单元来对单帧数据中驾驶员的面部状态进行综合性判断。接下来，将获取的帧数据进行时序性分析，从而对该时间段的驾驶员状态进行更为科学的判断。其步骤如图2所示。

在以往的方法中都只是对驾驶员是否疲劳这一状态进行判断，由于说话和打哈欠在某些方面有相似性，这就会导致许多说话的动作被误判成打哈欠。在实际应用中这种误判可能会，影响对驾驶员驾驶状态的判断，从而无法作出有效的判定及防范。为了降低误判的概率，本文将说话这一动作单独列为一项，对说话时的动作单元也进行时序性学习，从而减少说话被认为是疲劳的误判。本文的实验部分，充分说明了这些误判的存在及本文方法对减少此类误判中起到的关键性作用。

图2系统框架：从视频中采集信息，结合AU分析及LSTM网络时序分析，判断驾驶员状态

# 2.1 面部关键点标记

本文对测试人员状况的判断基于面部信息。脸部信息可以通过脸部的关键点呈现。为了获得关键点，首先需要根据如下所示的ASM形状模型函数构造人脸形状模型：

$$
\mathbf { \boldsymbol { x } } = \overline { { \boldsymbol { x } } } + P B
$$

其中： $\textbf { x }$ 表示平均脸形，P是由形状变化的主成分构成的矩阵，其通过M张图片中的每张图片的 $\mathrm { ~  ~ N ~ }$ 个特征点。图像上的 $\mathrm { ~  ~ N ~ }$ 个特征点的坐标向量表示为

$$
\mathbf { x } = \left[ x _ { 1 } , y _ { 1 } , x _ { 2 } , y _ { 2 } \cdots x _ { N } , y _ { N } \right]
$$

所有图像的平均脸形可以通过如下公式表示：

$$
\overline { { { x } } } ~ = ~ \frac { 1 } { M } ~ \sum _ { i = 1 } ^ { m } x ^ { ( i ) }
$$

从平均脸部向量中减去每个脸部的向量以得到具有均值0的形状变化矩阵X，如下所示：

$$
\mathbf { x } = \left( \begin{array} { c c c } { x _ { 1 } ^ { ( 1 ) } y _ { 1 } ^ { ( 1 ) } } & { \hdots } & { x _ { N } ^ { ( M ) } y _ { N } ^ { ( M ) } } \\ { \vdots } & { \ddots } & { \vdots } \\ { x _ { 1 } ^ { ( M ) } y _ { 1 } ^ { ( M ) } } & { \hdots } & { x _ { N } ^ { ( M ) } y _ { N } ^ { ( M ) } } \end{array} \right)
$$

![](images/8a27d092c2211cdda5a82c6e4f78e05ed54f2f0066999fc23ce226de71047d50.jpg)  
图3.面部关键点标记

必须指出的是，此时X是一个零均值形状变化矩阵，因为从每个行向量中减去平均面向量，所以与平均面的偏差，XX的主分量分析给出了决定性形状变化分量，即特征向量 $\mathbf { P _ { j } }$ 和相应的特征值 $\mathrm { \lambda _ { j } }$ ，选择第一K个特征向量以列形式排出，并形成形状变化矩阵P.这些特征向量实际上是所有样本变换的基础，并且可以表示样本中的任何变化。形状变化矩阵P，B可以通过：

$$
B = P ^ { T } ( x { - } \overline { { x } } )
$$

在构建形状模型之后，可以在检测到的人脸上初始化人脸形状模型。接下来的工作是让每个点在其附近找到最佳匹配点。在这里，本文分别训练了眼睑和眉毛分布模型。然后，结合每个模型来匹配关键点。长时间面部追踪很容易导致追踪漂移或面部消失，因此需要在面部（关键点）确认步骤。可以训练简单的卷积神经网络（CNN）来检测人脸并生成关键点。关键点生成在图3中示出。

17008 2 240 025 0370 。 39 270 430 0360 。 o 280 420 。 454↑ 40 290 47 46 16  
。 300  
0 3 132330 35 15  
2° 50 0000 51 3o 14  
。 A90 =。 。 。 。 6 S 013  
3 40 48 590 。 6 。 0 0 00 0 6 64 5 12s0 60 58 8 57 56 010 011,° 08 0

# 2.2 面部动作编码

通过面部关键点可以将人脸各个部位进行提取，进而进行面部动作编码。本文借鉴Tada's等人的方法[14]来实现面部动作编码系统。

# 2.2.1脸部追踪

可以通过参数 $\mathbf { p } = [ \mathbf { s } , \ \mathbf { R } , \ \mathbf { p }$ ，t]来描述使用的 $\mathrm { C L M } ^ { [ 1 5 ] }$ 模型，这些参数可以变化以获取模型的各种实例：比例因子s；对象旋转R（3D旋转矩阵的前两行）；2D翻转，t；描述形状p的非刚性变化的矢量。点分布模型（PDM）是：

$$
\chi _ { \mathrm { i } } = { \bf s } \cdot { \bf R } ( \overline { { x } } _ { \mathrm { i } } + { \Phi _ { i } } \mathrm { p } ) + t
$$

# 2.2.2对齐和标记

为了更好地分析脸部的纹理，需要将其映射到公共参考框架并去除由于缩放和平面旋转引起的变化。为此，使用从当前检测到的地标到中性表达（来自3DPDM[14]的平均形状的投影)的正面界标的表示的相似变换。得到的是具有45像素瞳距的$1 1 2 \times 1 1 2$ 像素的脸部图像。为了计算相似性变换，使用普鲁克叠加，其使对准的像素之间的均方误差最小化。

# 2.2.3外观特征

将脸部图像对齐为 $1 1 2 \times 1 1 2$ 大小的图像，从中提取外观特征。在这一步中，本文使用Felzenswalb[6]等人提出的提取面向梯度的直方图（HOG），使用 $8 \times 8$ 像素的 $2 \times 2$

单元块。形成 $1 2 \times 1 2$ 的 31维直方图，导入描述人脸的4464维矢量。

# 2.3 动作单元选择

本文通过结合多个面部动作单元信息来判断驾驶员的状态。针对本文所要解决的问题需，选择合适的面部动作单元，去除多余的信息，从而减少噪声、提高效率。在接下来的过程中，对多组数据进行实验来对面部动作进行筛选，最终选定部分单元（AU2、AU4、AU7、AU9、AU26和AU45作）为主要动作单元进行判别。动作单元的选择在实验部分有详细的说明过程。

# 2.4时序性动态特征的创建

LSTM 模型是由一个输入门，一个忘记门，一个输出门和一个存储单元组成。由于有三个门，LSTM模块可以学习顺序数据中的长期依赖关系，并且其参数更容易被训练。存储器单元可以将长期信息存储在其向量中，这可以在下一个时间步骤中重写或完成其他操作。

打哈欠说话等行为是一个连续性的动作，因此仅通过单张图片中的动作单元信息进行判别容易出现较大的误差。将连续数据作为判断依据将会更加合理。驾驶员的状态应该是由一段时间中所有帧数据进行判断的，而不是某一帧中的状态。因此可以应用LSTM来建模驾驶员状态的时间上的动态特性。

# 3 模型建立及实验分析

本次实验使用了两组数据集，第一组为通过模拟器模拟驾驶收集自建数据集，第二组为公开的Yaw-DD数据集。通过这两组数据集对框架进行框架搭建和实验验证。

# 3.1数据集

针对本文所使用的Yaw-DD数据集[17]，被广泛用于验证疲劳检测算法和模型。该数据集包含来自不同年龄，种族和面部特征的57名男性和50名女性志愿者的视频。

对于Yaw-DD数据集，首先进要行初步的数据分割及筛选，在该数据集的每段视频中测试人员都会进行以下三种行为，自然（无动作）、说话和打哈欠，本文对这三种行为分别进行标记并分割。在重新生成的数据集中，分析本文框架及现有方法的性能。

在该数据集中，收集的视频主要是在白天，但也包含在各种照明条件下录制的视频，即光照环境从清晨到日落。此外，天气情况包含了晴天雨天等，营造出不同的驾驶条件。在一些视频中，还有其他乘客在车内移动，因此有一些背景动作。数据集中的测试人员还分为无眼镜和有眼镜两类。视频是在真实和变化的照明条件下拍摄的。视频采用 $6 4 0 \times 4 8 0 \ 2 4$ 位真彩色（RGB）30fps的AVI格式，无音频。

根据数据集中给出的状态，本文的方法进一步对数据集视频进行分割。由于每个Yaw-DD数据集中的视频，包含了很长一段时间的驾驶员状态，即混杂着疲劳状态及非疲劳状态的多次转换，这对于精确判断驾驶员状态来说是一个问题。在使用公开数据集的基础上，为了进一步验证框架的有效性，本文自建了一个数据集用于框架的实验验证。真实的驾驶数据不容易获取，因此出于安全的考虑，本文通过驾驶模拟器来获取数据。实验装置如图4所示。

![](images/ddfe7dfea053fc7067d7e48a15aaf9d1b2d9ba75df1cb5fdfe5d747ad9a412c1.jpg)  
图4模拟驾驶装置

在该数据集中，使用驾驶模拟器来模拟驾驶并通过普通摄像头捕捉驾驶员的视觉信息。本数据集包含10位测试员（6男，4女），他们在三种不同的交通状况（城市，国道和乡村道路）中模拟三种驾驶状态（正常，疲劳和交流）。在仿真过程中，测试人员处于最佳驾驶状态并符合驾驶规则。本数据集采用与YAW-DD 相同的 $6 4 0 { \bf x } 4 8 0 2 4$ 位真彩色（RGB）每秒30帧的AVI格式，有音频。共生成了300分钟的数据量。

在实际用中，也会在非疲倦状态中，作出错误的操作及防范（如提醒或者给出警报)，从而影响产品实用体验及信任度。同时，这些存在不同状态转换的视频，无法直接用于训练LSTM并获取某种状态的时序信息。为了解决这些问题，分割并重新标记了这些视频。这些视频被剪切成只包含说话、疲劳，及其他状态之一的视频片段，并进行标记（标记状态）。为了描述这三种状态之间的过渡特征，在每类状态剪辑的头部和尾部保留10帧正常帧。

# 3.2动作单元选择实验

# 3.2.1疲劳信息单元筛选

为了理解疲劳相关的脸部动作单元，本文的方法将每个面部动作进行了单独训练并测试（CNN 网络）。对每个脸部动作单元的检测结果，揭示了哪些单元对于疲劳检测有效。表1显示了疲劳与部分面部动作相关程度。

通过上述实验，能够得出最能预测疲劳的六个面部动作分别是AU45（眨眼/眼闭合），AU2（外眉提高），AU7（眼轮匝肌内圈收紧），AU4（皱眉），AU9（鼻子皱起）和AU26（下颌骨下拉）。因此本文的方法将这六个面部动作单元进行组合来检测疲劳。

在对视频的研究中还发现，当打哈欠时许多受试者试图抬起眉毛保持眼睛睁开，实验中的AU2探测器的强关联性与该观察结果一致。

表1面部动作与疲劳相关度  

<html><body><table><tr><td>AU</td><td>动作名称</td><td>与疲劳相关度 (%)</td></tr><tr><td>1</td><td>抬起眉毛内角</td><td>68</td></tr><tr><td>2</td><td>抬起眉毛外角</td><td>82</td></tr><tr><td>4</td><td>皱眉</td><td>80</td></tr><tr><td>6</td><td>眼轮匝肌外圈收紧</td><td>72</td></tr><tr><td>7</td><td>眼轮匝肌内圈收紧</td><td>86</td></tr><tr><td>9</td><td>皱鼻</td><td>79</td></tr><tr><td>15</td><td>拉动嘴角向下倾斜</td><td>73</td></tr><tr><td>17</td><td>推动下唇向上</td><td>71</td></tr><tr><td>25</td><td>嘴唇微张</td><td>72</td></tr><tr><td>26</td><td>下颌骨下拉</td><td>77</td></tr><tr><td>45</td><td>眨眼</td><td>92</td></tr></table></body></html>

# 3.2.2说话动作单元筛选

表2面部动作单元与说话相关度  

<html><body><table><tr><td>AU</td><td>动作名称</td><td>与说话相关度 (%)</td></tr><tr><td>1</td><td>抬起眉毛内角</td><td>58</td></tr><tr><td>2</td><td>抬起眉毛外角</td><td>61</td></tr><tr><td>6</td><td>眼轮匝肌外圈收紧</td><td>62</td></tr><tr><td>7</td><td>眼轮匝肌内圈收紧</td><td>67</td></tr><tr><td>9</td><td>皱鼻</td><td>54</td></tr><tr><td>15</td><td>拉动嘴角向下倾斜</td><td>63</td></tr><tr><td>17</td><td>推动下唇向上</td><td>75</td></tr><tr><td>25</td><td>嘴唇微张</td><td>91</td></tr><tr><td>26</td><td>下颌骨下拉</td><td>80</td></tr><tr><td>45</td><td>眨眼</td><td>45</td></tr></table></body></html>

驾驶过程中说话也是一种十分常见的行为，并且这种行为与疲劳中的打哈欠行为容易混淆，因此在疲劳检测中正确的区分说话和打哈欠也是十分有必要的。与疲劳检测相比，说话这种行为涉及的面部动作将会有所减少，主要集中在嘴部区域。同样本文针对每个动作单元与说话间的相关性进行了测试得到表2。

在表2中，可以看到与说话这一行为相关度最高的动作单元就是AU25、AU26和AU17。

因此本文的方法在对三种状态进行区分时选择以下8个动作单元，即AU2、AU4、AU7、AU9、AU17、AU25、AU26和AU45动作单元。

# 3.3动态特征分析实验

针对为了区分三种状态而选取的8个单元，在相同数据格式的（ $\lvert 5 \mathrm { s } \backslash 1 5 0$ 帧）数据集中，对时序过程中的动作强度变化规律进行了比较分析，得到如图5所示结果。

![](images/3a0df27d2a8a46a016ffa179a28122fd5e552ecc07af38ace91cf0ee68040c32.jpg)  
图5不同脸部动作单元和驾驶员状态之间的关系

根据上面的实验结果，可以清晰的看到在相同的时间窗内，不同状态下各动作单元的强度变化趋势还是有相当大的差异，因此根据这些数据情况，进行三种状态的区分，是有效的。

# 3.4LSTM网络训练及测试

根据上述实验结果，建立LSTM网络框架，并进行了相关验证实验。针对所选取的脸部动作单元，进行训练。从最能够有效检验疲劳的AU45动作开始，然后再此基础上添加下一个检测特征，直到所有特征相加。选取不同特征的LSTM网络的准确率结果如表3所示。

表3特征选择组合准确率  

<html><body><table><tr><td>特征选择</td><td>准确率/%</td></tr><tr><td>AU45</td><td>62.1</td></tr><tr><td>AU45+AU2</td><td>67.5</td></tr><tr><td>AU45+AU2+AU4</td><td>69.2</td></tr><tr><td>AU45+AU2+AU4+AU7</td><td>73</td></tr><tr><td>AU45+AU2+AU4+AU7+AU9</td><td>74.1</td></tr><tr><td>AU45+AU2+AU4+AU7+AU9+AU17</td><td>80.2</td></tr><tr><td>AU45+AU2+AU4+AU7+AU9+AU17+AU25</td><td>84.7</td></tr><tr><td>AU45+AU2+AU4+AU7+AU9+AU17+AU25+AU26</td><td>92</td></tr><tr><td>包含所有特征(未进行筛选）</td><td>83.2</td></tr></table></body></html>

# 3.5状态二分类VS 状态三分类

本文选取准确率最高的特征组合（ $\mathrm { A U } 4 5 { + } \mathrm { A U } 2$ $+ \mathrm { A U } 4 + \mathrm { A U } 7 + \mathrm { A U } 9 + \mathrm { A U } 1 7 + \mathrm { A U } 2 5 + \mathrm { A U } 2 6 \ )$ ，对二分类（疲劳、自然），和三分类（疲劳、说话、自然）时，对本文的方法进行了对比实验，其结果如图6所示。

![](images/8157c79d0ea0fce05406d80b4ab9ff7092461512da719e3e22d6dd3f5e73dd3c.jpg)  
图6数据分类比较

从图6中能清晰地看到，将说话这一行为单独作为一类分离出来，能够极大地降低误判的概率，同时提升疲劳状态的判断准确率。

# 3.6传统算法VS本文算法

本文选取几种典型的传统机器学习算法与加入了时许信息的本文算法，进行疲劳检测准确率和对误判率进行了对比实验，结果如表4所示。

实验结果表明在相同特征下加入时序性信息将能够有效的降低误判率并大幅度提高状态判断的准确率。

同时，本文选取最新的方法[18,19,20]进行比较，表5 给出了本文的方法和以前的方法[18,19,20]的比较。实验表明，本文所提出的方法在疲劳判断中达到 $93 . 1 \%$ 的准确率，比以往的方法准

确率有所提升。

表4传统算法与本文算法比较  

<html><body><table><tr><td>算法</td><td>误判率(%)</td><td>准确率(%)</td></tr><tr><td>DT</td><td>28.91</td><td>72.31</td></tr><tr><td>LR</td><td>18.36</td><td>75.35</td></tr><tr><td>GBDT</td><td>17.34</td><td>77.93</td></tr><tr><td>SVM</td><td>10.2</td><td>82.5</td></tr><tr><td>本文算法</td><td>2.4</td><td>93.1</td></tr></table></body></html>

表5与现有方法进行比较  

<html><body><table><tr><td rowspan="2">方法</td><td rowspan="2">判断所需数据 量/s</td><td rowspan="2">特征选取</td><td rowspan="2">时间特征选取</td><td rowspan="2">准确率/%</td></tr><tr><td></td></tr><tr><td>文献[20]</td><td>30</td><td>生理信号</td><td>无</td><td>90</td></tr><tr><td>MSTN[19]</td><td>4</td><td>面部视觉</td><td>LSTM</td><td>85.52</td></tr><tr><td>文献[18]</td><td>12</td><td>表情信息</td><td>MLR</td><td>90</td></tr><tr><td>本文方法</td><td>5</td><td>表情信息</td><td>LSTM</td><td>93.1</td></tr></table></body></html>

# 4 结束语

本文提出了一种通过监视器获取的视频，自动检测驾驶员状态的框架。本文针对的应用场景主要为，利用放在仪表盘上方等位置的普通摄像头，对驾驶员面部视频数据进行采集，并作出疲劳检测。本文的方法将面部动作单元进行编码，并通过实际实验获取合适的面部动作单元组合。同时，为了提高检测驾驶状态的准确率，本文的框架添加了长短期记忆网络进行时间序列信息分析，相对于现有的方法，实现了对驾驶员状态的更为有效识别。通过Yaw-DD数据集的测实验证了该方法适用于多个人种。与之前其他方法比较该框架成本低廉，无须对驾驶员添加任何装置，因此不会对驾驶员的驾驶行为产生其他影响。在接下来的研究中本文还将会对更多更复杂的驾驶员状态进行判别，以期能够更好更加精准的判别驾驶行为是否异常。

# 参考文献：

[1]Organization,World Health.World report on road traffic injury prevention. [M]//World Report On Road Traffic Injury Prevention.World Health Organization,2004: 270-275.   
[2]Al-Sultan S,Al-Bayatti A H,Zedan H.Context-aware driver behavior detection system in intelligent transportation systems [J].IEEE Trans on Vehicular Technology,2013,62(9): 4264-4275.   
[3] 王忠民，李卓，范琳．基于滑动窗特征融合的深信度网络驾驶行为识别 [J]．计算机应用研究,2018,35(4):1096-1100.(Wang Zhongmin,Li Zhuo, Fan Lin.Driving behacior recognition algorithm for deep belief network based on sliding window feature fusion [J].Application Research of Computers,2018 (4):1096-1100.)   
[4]杨秋芬，桂卫华，周书仁．疲劳驾驶面部表情识别算法[J].计算机应 用研究,2008,25 (10):3039-3041.(Yang Qiufen,Gui Weihua, Zhou Shuren. Facial expression recognition algorithm for fatigue driving[J].Application Research of Computers,2008,25 (10): 3039-3041.)   
[5]You Chuangwen,Lane N D,Chen Fanglin,et al. CarSafe app:alerting drowsy and distracted drivers using dual cameras on smartphones [C]//Proc of International Conference on Mobile Systems,Applications,and Services. New York:ACMPress,2013:13-26.   
[6]Mbouna R O,Kong SG,Chun MG. Visual analysis of eye state and head pose for driver alertness monitoring [J].IEEE Trans on Intelligent Transportation Systems,2013,14 (3):1462-1469.   
[7]Mccall JC,Trivedi MM,WipfDP,et al. Lane change Intent analysis using robust operators and sparse bayesian learning [J]. IEEE Trans on Intelligent Transportation Systems,2007,8(3):431-440.   
[8]Nakamura T,Maejima A,Morishima S.Detection of driver's drowsy facial expression [Cl//Pattern Recognition.2014: 749-753.   
[9]Akrout B,Mahdi W. Spatio temporal features for the automatic control of driver drowsiness state and lack of concentration [J].Machine Vision & Applications,2015,26(1): 1-13.   
[10]Hjortsjo"C H.Man's face and mimic language.Malmo: Nordens Boktryckeri,1970   
[11]Ekman P,Friesen WV.Facial action coding system (FACS): a technique for the measurement of facial actions [J].Rivista Di Psichiatria,1978,47 (2): 126-38.   
[12] Ekman P. CiNii articles [J]. Facial Action Coding System the Manual on Cd Rom,2002.   
[13] Hamm Jihun,Kohler C G,Gur R C,et al.Automated facial action coding system for dynamic analysis of facial expressions in neuropsychiatric disorders [J].Journal ofNeuroscience Methods,2011,200 (2): 237-56.   
[14] Baltrusaitis T,Mahmoud M, Robinson P.Cross-dataset learning and personspecific normalisation for automatic Action Unit detection [C]// Proc of IEEE International Conference and Workshops on Automatic Face and Gesture Recognition. 2015:1-6.   
[15] Cootes T. An Introduction to Active Shape Models [J].Reviews Computational Statistics,2010,2(4):503-508.   
[16]Felzenszwalb P,Mcallester D,Ramanan D.A discriminatively trained, multiscale,deformable part model [J]. Cvpr, 2oo8,8:1-8.   
[17] Abtahi S,Omidyeganeh M, Shirmohammadi S,et al. YawDD: a yawning detection dataset [C]//ACMMultimedia Systems.New York:ACM,2014: 24-28.   
[18] Vural E,Cetin M,Ercil A,et al.Drowsy driver detection through facial movement analysis [C]//Proc of IEEE International Conference on HumanComputer Interaction. Springer-Verlag,20o7: 6-18.   
[19] Shih TH,Hsu C T.MSTN: multistage spatial-temporal network for driver drowsiness detection [C]//Proc of Asian Conference on Computer Vision. Cham: Springer,2016:146-153.   
[20]王琳，张陈，尹晓伟，等．一种基于驾驶员生理信号的非接触式驾驶疲 劳检测技术 [J]．汽车工程,2018(3).333-341.(Wang Lin,Zhang Chen, Yin Xiaowei,et al.A non-contact driving fatigue detection technique based on driver's physiological signals [J].Automotive Engineering,2018 (3): 333-341.