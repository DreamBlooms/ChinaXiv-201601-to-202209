# 基于观测图像识别的天文望远镜智能故障辅助诊断系统

张豫龙1²，王建峰」，李陶然」，葛亮」，兀颖1²，赵勇1²，姜晓军1.2(1.中国科学院光学天文重点实验室（国家天文台），北京100101

2.中国科学院大学天文与空间科学学院，北京100049）

摘要：我们设计并构建了基于观测图像识别的望远镜智能故障辅助诊断系统，通过收集望远镜在观测时的故障图像与传感器信息来综合判断望远镜在观测时所产生的故障，并给出相应的解决建议。我们利用卷积神经网络方法进行图像智能识别，并使用故障树分析法寻找望远镜系统的薄弱点。经过仿真与实测检验，证明了系统能够有效地发现判断故障并给出建议，提高了望远镜的可靠性，为故障诊断技术智能化做好了铺垫。

关键词：故障诊断；故障树；图像识别；天文望远镜中图分类号：TH751 文献标识码：A 文章编号：

# 0引言

望远镜是天文研究中的重要工具，其高效稳定运行是保证有效天文观测的前提。因此，为了实现长时间稳定的观测运行，故障诊断系统的使用是不可或缺的。

故障诊断系统是一种分析故障时的系统数据并迅速判断、定位故障点的程序系统，它能在望远镜发生故障时迅速响应，给出解决方案。故障诊断技术在多个领域中已有应用的先例，早在20世纪60年代，美国斯坦福大学首次提出了基于专家系统的故障诊断方法，将行业内专家的知识库应用在了故障诊断领域[1]。20世纪70年代，关于控制系统的故障诊断技术在麻省理工学院首次被提出[2]。而在天文方面，美国针对哈勃望远镜维护困难的问题开展了对望远镜控制系统故障诊断技术的研究[3。澳大利亚也于90 年代将故障诊断技术应用于澳大利亚望远镜(Australia Telescope)中，实现了基于传感器的望远镜故障诊断[4]。在国内，故障诊断技术在天文方面也有所应用。南极望远镜上使用了智能镜面除霜系统，用于加热望远镜镜面来确保其不受霜雪阻碍观测[5]。Mini-GWAC 也使用了基于故障树与传感器的望远镜故障诊断系统，实现了确保系统安全前提下全自动控制[]。

然而，传统的故障诊断系统在故障信息获取受限的条件下很难发挥出原有的作用。其诊断方法单一、信息获取渠道单一，例如上个世纪所研制的中小口径望远镜，往往没有完备的传感器设备，传统故障诊断系统无法准确的通过传感器获取系统所需信息，运行效果大打折扣。而如今人工智能技术突飞猛进，故障诊断系统也变得多方法融合化、多渠道信息化与智能化，利用这些技术可以很好地弥补传统故障诊断系统的不足，最大化发挥故障诊断的效果。

本文所提出的基于观测图像识别的天文望远镜智能故障辅助诊断系统使用了卷积神经网络的图像识别模块，利用了望远镜故障时所产生的观测图像，将图像的智能识别技术与故障诊断系统相结合，很好地解决传感器不完备的老式中小口径望远镜信息获取不充分的问题。此外，信息获取越充分，故障判定的准确性就越高，所以这一系统也可以辅助传统基于传感器的故障诊断系统，增加信息获取渠道，提高故障诊断的准确率。

# 1基于观测图像识别的望远镜智能故障辅助诊断系统设计

本文提出的故障辅助诊断系统是基于望远镜观测时的图像、过往的故障记录、故障的解决方案以及可能的传感器信息来运作的。传感器与图像信息经分析整合后，通过与过往故障记录比对可以给出关于望远镜可能的故障原因、故障概率并从故障的解决方案中给出相应建议。因此本系统采用以下的设计方案。

# 1.1系统总体设计

基于观测图像识别的望远镜智能故障辅助诊断系统主要由四个部分组成：信息收集模块，数据库模块，推理模块与人机交互界面。其结构图如图1所示：

![](images/d53ad675b5364c3f08984adda670b206f2bf35b9d8f68e8571ce5c7fc6372504.jpg)  
图1基于观测图像识别的望远镜智能故障辅助诊断系统结构框图  
Fig.1Structure of intelligentfault-assisted diagnosis system for telescope based onobservation image recognition

系统各组成部分功能如下：

(1）信息收集模块：负责接收传感器和观测图像所传递的信息，其中有基于卷积神经网络的图像识别算法，其负责根据重训练的故障模型来分辨实测图像的大致故障类型。之后它将收集到的故障信息传递给数据库模块与推理模块并展示到人机交互界面上。此外，信息收集模块也负责监视望远镜的实时运行状况，它通过判断图像质量以及判断传感器返回的参数来确定目前的状态，并且将数据与参数均存储于系统运行数据库中，以便出现故障时推理模块进行调阅。  
(2）数据库模块：为整个系统的知识储备与运行库，分为系统运行数据库与故障知识库。系统运行数据库中存储着故障ID，方法ID，路径权重，对应关系以及望远镜的运行数据，是整个系统运行的基本保障。故障知识库中则存储了故障树中所记述的相应故障知识，包括故障基础知识与概率性的权重信息。  
(3）推理模块：包含推理机与解释器，它负责将信息收集模块，系统运行数据库与故障知识库中的相关信息收集并推理，以一定的逻辑策略判断出可能的结果，并将结果送往人机

交互界面。推断故障成立时，推理模块也会将结果返回至知识库中储存，作为日后工程师维护望远镜的方向性依据。

(4）人机交互界面：用于展示信息并接受用户的控制，是用户与系统之间的重要交互渠道。

# 1.2 故障树设计与分析

本系统采用了基于故障树的逻辑结构设计，故障树是一种树型结构，能够清晰地反映出上层“树干”与下层“树枝”之间的逻辑与因果关系。系统从顶事件出发，逐步依据信息与树状结构向下层判断，一旦确定底事件，对应的故障就被确定了。故障树的顶事件是望远镜的实测图像异常，代表着望远镜系统失效。通过对以往故障记录进行电子化整理并统计兴隆观测基地8台望远镜的历史故障，建立故障库，咨询相关专家，决定将故障树中层分为“星像拉长”、“星像滑跃”、“星像消失”三个大类。其下依据望远镜的结构细分至系统乃至部件级别的失效，建立起兴隆观测基地8台光学望远镜的系统故障树如图2所示，故障标记说明如表1所示。

![](images/f5f2d35f57db375d58d281e66f6b1fc9ec49dc561d8dcca87cec426c3ed0ca12.jpg)  
图2望远镜系统故障树 Fig.2Fault tree of telescope system

表1望远镜系统故障树标记事件  
Table 1Description of the labels in telescope system fault tree   

<html><body><table><tr><td>Label</td><td>Fault</td><td>Label</td><td>Fault</td><td>Label</td><td>Fault</td></tr><tr><td>T</td><td>Telescope image abnormal</td><td>X</td><td>Optical path failure</td><td>X14</td><td>CCD communication system failure</td></tr><tr><td>A</td><td>Elongated star image</td><td>X</td><td>Tracking motor stopped for a short time</td><td>X15</td><td>Clouds obscured star image</td></tr><tr><td>A2</td><td>Slid star image</td><td>X4</td><td>Barrel center of gravity slipped</td><td>X16</td><td>The shutter not opened</td></tr><tr><td>A</td><td>Disappeared star image</td><td>X5</td><td>Transmission structure slid</td><td>X17</td><td>Cover motor failure</td></tr><tr><td>B1</td><td>Tracking system failure</td><td>X6</td><td>Tracking motor stopped</td><td>X18</td><td>Cover communication system failure</td></tr><tr><td>B2</td><td>Rotating eliminate system failure</td><td>X7</td><td>Transmission structure failure</td><td>X19</td><td>Tracking motor faults</td></tr><tr><td>B</td><td>CCD system failure</td><td>X8</td><td>User misoperation</td><td>X20</td><td>Dome motor failure</td></tr><tr><td>B4</td><td>The light path is completely blocked</td><td>X9</td><td>Oil pump failure</td><td>X21</td><td>Dome mechanical failure</td></tr><tr><td>C</td><td>Telescope cover not open</td><td>X10</td><td>Hardware limit</td><td>X22</td><td>Dome cover motor failure</td></tr><tr><td>C</td><td>The dome completely blocked the light path</td><td>X11</td><td>Inaccurate code wheel</td><td>X23</td><td>Dome cover communication system failure</td></tr><tr><td>D1</td><td>The dome not open</td><td>X12</td><td>Rotating eliminate motor failure</td><td>X24</td><td>Dome cover mechanical and component failure</td></tr><tr><td>X</td><td>The shutter not closed</td><td>X13</td><td>CCD failure</td><td></td><td></td></tr></table></body></html>

故障图像经由重训练的图像识别模型分类至三个图像大类之一，再与各系统通信来进一步判断至底事件。底事件拥有各自的权重，成功判定出的故障与工程师们反馈的故障都会被记入其中并实时进行调整，在因条件所限无法精确判断时可以作为概率的参考。因为对于单台望远镜的故障往往具有重复性，所以权重与概率的分布也具有较高的参考价值。

故障树的定性与定量分析能有效地找出系统的薄弱环节，工程师在维护时可以针对这些部位重点排查，从而降低望远镜在运行时的故障率，使用布尔代数化简法进行定性分析，过程如下：

$$
A _ { I } = B _ { I } + B _ { 2 } + X _ { I } + X _ { 2 } ; A _ { 2 } = X _ { 3 } + X _ { 4 } + X _ { 5 } ; A _ { 3 } = B _ { 3 } + B _ { 4 } ;
$$

则可以得出：

$$
T = X _ { I } + X _ { 2 } + X _ { 3 } + X _ { 4 } + X _ { 5 } + X _ { 6 } + X _ { 7 } + X _ { 8 } + X _ { 9 } + X _ { I 0 } + X _ { I I } + X _ { I I } + X _ { I 2 } + X _ { I 3 } + X _ { I 4 } + X _ { I 5 } + X _ { I 6 } + X _ { I 7 } + X _ { I 8 } + X _ { I 9 } + X _ { 2 0 } +
$$

$$
\begin{array} { r } { X _ { 2 I } + X _ { 2 2 } + X _ { 2 3 } + X _ { 2 4 } . } \end{array}
$$

即最小割集为：

$\{ X _ { I } \} \ \left\{ X _ { 2 } \right\} \ \left\{ X _ { 3 } \right\} \ \left\{ X _ { 4 } \right\} \ \left\{ X _ { 5 } \right\} \ \left\{ X _ { 6 } \right\} \ \left\{ X _ { 7 } \right\} \ \left\{ X _ { 8 } \right\} \ \left\{ X _ { 9 } \right\} \ \left\{ X _ { I 0 } \right\} \ \left\{ X _ { I I } \right\} \ \left\{ X _ { I 2 } \right\} \ \left\{ X _ { I 3 } \right\} \ \left\{ X _ { I 4 } \right\} \ \left\{ X _ { I s } \right\} \ \left\{ X _ { I 6 } \right\}$ $\{ X _ { I 7 } \} \ \{ X _ { I 8 } \} \ \{ X _ { I 9 } \} \ \{ X _ { I 2 0 } \} \ \{ X _ { 2 I } \} \ \{ X _ { 2 2 } \} \ \{ X _ { 2 3 } \} \ \{ X _ { 2 4 } \}$

共24个最小割集，均为一阶割集。即故障树中所包含的每个底事件均会直接影响望远镜的成像质量，薄弱部位和各底事件的故障概率直接相关。下面根据所统计的望远镜故障记录来计算各底事件的发生概率。

兴隆观测基地的望远镜在发生故障时，工程师们会在解决故障的同时填写故障报表并存档，分析统计这些存档可以获取望远镜故障树底事件的发生概率。统计兴隆观测基地2016-2018年8台望远镜故障报表并计算平均每台每年的底事件发生概率，所获得的结果如表2所示。

# 表2故障树底事件发生概率

Table 2Probability of fault tree bottom event   

<html><body><table><tr><td>Label</td><td>Fault</td><td>Probability</td><td>Label</td><td>Fault</td><td>Probability</td></tr><tr><td>X</td><td>The shutter not closed</td><td>20.83%</td><td>X13</td><td>CCD failure</td><td>8.33%</td></tr><tr><td>X2</td><td>Optical path failure</td><td>4.17%</td><td>X14</td><td>CCD communication system failure</td><td>20.83%</td></tr><tr><td>X</td><td>Tracking motor stopped for a short time</td><td>12.50%</td><td>X15</td><td>Clouds obscured star image</td><td>4.17%</td></tr><tr><td>X4</td><td>Barrel center of gravity slipped</td><td>4.17%</td><td>X16</td><td>The shutter not opened</td><td>4.17%</td></tr><tr><td>X5</td><td>Transmission structure slid</td><td>16.67%</td><td>X17</td><td>Cover motor failure</td><td>12.50%</td></tr><tr><td>X6</td><td>Tracking motor stopped</td><td>16.67%</td><td>X18</td><td>Cover communication system failure</td><td>20.83%</td></tr><tr><td>X7</td><td>Transmission structure failure</td><td>8.33%</td><td>X19</td><td>Tracking motor faults</td><td>4.17%</td></tr><tr><td>X8</td><td>User misoperation</td><td>4.17%</td><td>X20</td><td>Dome motor failure</td><td>12.50%</td></tr><tr><td>X9</td><td>Oil pump failure</td><td>12.50%</td><td>X21</td><td>Dome mechanical failure</td><td>8.33%</td></tr><tr><td>X10</td><td>Hardware limit</td><td>20.83%</td><td>X22</td><td>Dome cover motor failure</td><td>12.50%</td></tr><tr><td>Xl1</td><td>Inaccurate code wheel</td><td>8.33%</td><td>X23</td><td>Dome cover communication system failure</td><td>8.33%</td></tr><tr><td>X12</td><td>Rotating eliminate motor failure</td><td>4.17%</td><td>X24</td><td>Dome cover mechanical and component failure</td><td>8.33%</td></tr></table></body></html>

根据故障树分析，系统的最小割集均为一阶割集，即任意底事件的失效均会导致顶事件失效。根据表2中的结果计算平均每年顶事件至少失效一次的概率：

$$
P ( T ) = 1 - [ 1 - P ( X _ { 1 } ) ] [ 1 - P ( X _ { 2 } ) ] [ 1 - P ( X _ { 3 } ) ] [ 1 - P ( X _ { 4 } ) ] . . . . . . . [ 1 - P ( X _ { 2 4 } ) ] \approx 0 . 9 2 9 5 7 5
$$

其中发生的概率较大的故障有相机快门闭合失效，触发望远镜限位保护，CCD通讯系统故障与镜盖的通讯系统故障，平均每台望远镜一年有 $2 0 . 8 3 \%$ 的概率发生一次此类故障。望远镜维护人员在日常维护检修时，应重点注意上述薄弱部位的故障，及时发现问题并更换故障配件，可以提高望远镜系统的平日运行的可靠性，减少观测时因故障造成的损失。

# 1.3故障训练集的建立

卷积神经网络的图像识别模块需要故障训练集来进行重训练。在本系统中，要求模块能够识别出“星像拉长”、“星像滑跃”、“星像消失”与正常图像。故障训练集的图片来源渠道主要有三种：观测图像中筛选，望远镜实地拍摄与人工绘制。从观测中获得的图像主要为兴隆观测基地80cm 望远镜 2017-2018年的图像与85cm 望远镜在 2019 年的图像，其中筛选了星像滑跃23 张，星像拉长50张，正常观测图像1037张。望远镜实地拍摄使用的是兴隆观测基地60cm望远镜，人为拍摄故障的星像图像，其中拍摄星像拉长626张，星像消失1104张，鉴于保护望远镜的目的无法拍摄星像滑跃的图像。人工绘制是为了补充难以从常规渠道获得的故障图像，共补充星像滑跃44张，星像拉长73张。将上述图片标记并将其中$90 \%$ 作为训练集， $1 0 \%$ 作为测试集使用。

重训练参数中，训练步数设置为9000，学习率设置为0.01，无随机裁剪、缩放、翻转，经过重训练成功获得所需模型。测试准确率为 $9 7 . 6 3 \%$ ，其中特征明显的图像均分类正确，拉长较短、滑跃较长的图像有小概率出现混淆。

# 2初步测试结果

根据上文所述的系统设计，使用Python 编写代码，成功构建出基于图像的望远镜智能故障辅助诊断系统。为了测试系统是否能够正常运作，我们尝试人工模拟故障来进行检测。此外，还将实际观测中的故障数据输入至虚拟望远镜中检测来判断系统给出的结果是否与故障记录中的一致。

# 2.1模拟故障虚拟环境测试结果

使用望远镜控制软件“兴隆基地通用望远镜控制前沿机”生成的虚拟望远镜来进行本系统的实验测试。测试通过人为手动模拟望远镜的故障来检验该系统是否能够正常运作。模拟的故障为“用户误操作”，即用户因为不慎停止跟踪而导致产生望远镜的实测图像拉长的现象。实验过程中使用了实测的星像拉长图片对系统进行了引导，系统诊断结果如图3所示。

![](images/514c628caef23a8783f5a1a6ad3bbbdbac411963c3226297edda60c7a8dfe34e.jpg)  
图3模拟测试结果  
Fig.3The resultof simulationtest

结果显示，系统成功根据实测图片及虚拟望远镜的状态信息判断出了导致这张图片产生的故障原因，本系统在虚拟环境下使用成功。

# 2.2基于实测数据的测试结果

兴隆观测基地的80cm 望远镜于2016年1月18日在观测时发生故障，通过查询筛选获取了1月18日所拍摄的故障图像与望远镜当时的运行日志、系统与位置信息，调整虚拟望远镜的参数状态来还原故障场景。测试结果如图4所示。

![](images/517c3c11634a2a8e59f128ce4df94968ef73b753906643d776c3fd9f7c75b2a6.jpg)  
图4真实数据测试结果  
Fig.4 The result of real data test

系统成功判断出了图像的异常，且异常为“星像消失”。根据故障树的逻辑，在星像消失的分支下，系统先尝试与CCD系统通讯，获取了CCD状态正常且CCD通讯系统正常的反馈，之后与镜盖系统通讯，确认镜盖开启度小于阈值，通讯系统正常而镜盖很可能未打开，所以通过排除法寻找并给出了“镜盖电机故障”的底事件，与基地故障报表中所记述的一致。这代表着在望远镜的实际使用中，本系统可以发挥其应有的作用，可以帮助维护人员快速定位故障并参考对应的解决建议。

如果本系统因为条件所限无法精确判定至故障树的底事件，系统会根据以往的故障记录和工程师们的反馈来确定故障现象下可能原因的权重。每一台望远镜的故障通常会重复出现，所以故障原因的概率分布也具有一定的意义，故障解决后系统可以根据反馈对概率进行调整，系统对单个望远镜的模糊故障诊断的精确度，为维护人员提供一定的方向指导。

收集并统计判断了兴隆观测基地望远镜 2019 年所产生的48次故障，能够直接判定底事件的故障31次；根据权重模糊判断且参考项概率最高者为故障原因的故障10次；故障原因仅包含在参考项中5次；故障原因未包含在参考项中2次；综合判定正确率为 $8 5 . 4 2 \%$ ，错误率为 $1 4 . 5 8 \%$ 。

# 3结论

本文介绍并利用Python构建了一种基于观测图像识别的望远镜智能故障辅助诊断系统，分析了此系统的故障树，根据分析结果得出兴隆观测基地望远镜易发生镜盖电机故障，快门闭合失效，限位保护，CCD通讯故障与镜盖通讯故障。在日后的维护中着重关注这些部位可以有效提高望远镜的日常稳定性。本系统能够监视望远镜的运行状态，并且其创新之处在于望远镜系统故障时可以使用观测时的故障图像作为一条新的信息获取渠道，通过智能图像识别来初步进行故障的分类，并针对发现的故障给出相应的维修建议，为故障诊断系统的智能化做好了预研与铺垫。此系统经进一步完善也可以与其它故障诊断系统联合使用，辅助进行故障诊断，提高诊断的准确率，为望远镜的平稳运行提供保障。

# 参考文献：

[1] 姜长城.门式起重机远程监测及诊断分析系统研发[D].东南大学,2018.  
[2] 房汉鸣，税爱社，汪辉，等.基于大数据的控制系统故障诊断方法综述[J]．单片机与嵌入式系统应用，2016，16（04）：6-9.Fang Hanming, Shui Aishe, Wang Hui, et al .A Survey of Fault Diagnosis Methodsfor Control Systems Based on Big Data[J]. Microcontrollers & Embedded Systems,2016，16(04） : 6-9.

[3] Monahan C M,Patterson-Hine FA, Iverson D L.Automated telescope monitoring and diagnosis[C]//The Astronomical Society of the Pacific Conference Series.，1995 : 120-128.

[4] Landau R. Intelligent fault diagnosis at the Australia telescope[C]//Proceedings of the Astronomical Society of Australia ，1994 : 180-187.

[5] 冯晴晨，李晓燕.基于故障树的南极天文光学望远镜镜面除霜系统的可靠性分析[J]．天文研究与技术，2018，15（01）：111-118.Feng Qingchen, Li Xiaoyan. Fault Tree Analysis on Reliability of Mirror DefrostingSystem of Antarctica Astronomical Telescope[J]. AstronomicalResearch&Technology，2018，15（01）: 111-118.

[6] 付夏楠，黄垒，魏建彦.Mini_GWAC控制系统的故障诊断专家系统[J].天文研究与技术,2016，13（3）：366-372.Fu Xianan, Huang Lei, Wei Jianyan. The fault diagnosis expert system ofMini_GWAC[J].Astronomical Research&Technology，2016，13（3）: 366-372.

[7] 戴进，刘振宇．基于深度学习的图像识别算法研究的综述[J]．计算机产品与流通，2018（03）: 188.Dai Jin, Zhenyu Liu.A Survey of Research on Image Recognition Algorithm Basedon Deep Learning[J]. Computer Products and Circulation ，2O18（O3）:188.

# The intelligent fault auxiliary diagnosis system of astronomical telescope based on observation image

# recognition

Zhang Yulong1,2，Wang Jianfeng’，Li Taoran’，Ge Liang'，Wu Ying'，Zhao Yong', Jiang Xiaojun1.2

(1.KeyLaboratoryofSpaceAstronomyandTechology，NationalAstronomicalObservatories，ChineseAcademyofSciences，Beijing

100012，China，Email： zhangyulong@nao.cas.cn;

2.University of Chinese Academy of Sciences，School of Astronomyand Space Science,Beijing 10o049，China）

Abstract: We designed and built an intelligent fault auxiliary diagnosis system of telescope based on observation image recognition. The system collects the measured image and sensor information of the telescope to comprehensively judge the faults during observation,and gives corresponding solutions. We use the convolution neural network method to inteligently identify images and use fault tree analysis to find the weak points of the telescope system. The simulation and actual test prove that the system can effectively find, judge faults and give suggestions. It improves the reliability of the telescope and accumulates experience for the inteligentization of fault diagnosis technology.

Key words: Fault diagnosis； Fault tree； Image identification; Astronomical telescope