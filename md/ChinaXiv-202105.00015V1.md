# 基于FasterR-CNN的日冕物质抛射检测方法

# 洗祥贵，尚振宏，袁梅宇，杨志鹏

（昆明理工大学信息工程与自动化学院，云南昆明650500）

摘要：日冕抛射物质(CoronalMass Ejection，CME)是一种强烈的太阳爆发现象，对空间天气和人类生活都有着巨大的影响，因此CME检测对预报CME、保障人类的生产生活安全有重要意义。现有检测方法多采用人为定义特征和人为界定阈值等方法检测CME。由于人为定义特征不能很好表征CME且具有普适性的阈值难于选择,现有CME检测方法对CME的检测效果有待提升。本文提出一种基于FasterR-CNN的日冕抛射物质检测算法。该方法首先结合CDAW、SEEDS、CACTus三个著名CME目录信息，人工标注了包含9113幅日冕图像的数据集，然后根据CME的图像特征较自然图像少、目标尺寸与自然图像有差异等特点，在特征提取和锚点选择方面对FasterR-CNN进行了改进。以2007年6月的CME标注数据为测试集，本文算法检测出了22个强CME事件中的22个和151个弱CME事件中的138个，且对CME事件的中心角和角宽度等特征参数的检测误差分别在5度和10度以内。

关键词： 日冕物质抛射；目标检测；图像处理

# 0 引言

CME 是一种日冕物质从太阳日冕层向行星际空间抛射的强烈空间天气现象[1]。由于CME 具有巨大的速度和能量且与背景太阳风在磁场、速度、温度上存在差异，它在行星际空间传播时会引起太阳风扰动，严重时甚至引起磁暴等极端空间天气。这些会导致太空中的卫星故障和数据丢失、地面电力系统崩溃及短波通信中断等。为了预防CME对人类生活的影响和伤害，实现对CME的预报具有重要意义，而CME 检测是CME预报的重要基础和前提。

![](images/d7a74ba1b2a37d2f0d842bc8240b54fc606d96bcc8b9bca3effc82c778d17089.jpg)  
图1日冕图像。（a）LASCOC2图；（b）LASCOC2 图的差分图。  
Fig.1Coronal image.(a) LASCO C2 image:(b) Running difference image of LASCO C2 image.

SOHO(Solar and Heliospheric Observatory）和 STEREO(Solar Terrestrial RelationsObservatory)等卫星为人类提供了大量的日冕图像资料。图1(a)(b)是 SOHO 提供的LASCOC2 图和差分图。CME目标在日冕图像上表现为一个明亮的、纹理复杂的增亮结构，且尾随着一个亮度不足的暗区域。基于这些图像资料，人们提出了多种检测方法来检测CME 的发生频率、角度、速度、质量、能量等特征。现有的CME检测方法可以分为传统检测方法和基于学习的检测方法两类。有关CME 检测方法的详细介绍可见参考文献[2]。

传统检测方法利用日冕图像的灰度或纹理特征和空间域图像处理方法实现CME 检测。Berghmans 等人[3]4]开发的计算机辅助CME 跟踪软件包(Computer Aoded CME Trackingsoftware package，CACTus)通过霍夫变换和图像形态学等方法对CME 进行检测，得到CME事件的位置、角度及速度等信息。CACTus生成的CACTus 目录是第一个自动检测的CME目录。Olmedo 等人[5]]提出的太阳爆发事件检测系统(Solar Eruptive Even Detection System,SEEDS)利用日冕图像的灰度信息检测CME的前缘和后缘。其生成的SEEDS目录和CACTus目录、协调数据分析研讨会数据中心(Coordinated Data Analysis Workshop Data Center,CDAW)目录一起组成CME的三大参考目录。其中，CDAW是人工标记的目录。人工检测CME 费时费力，且弱CME 检测结果往往受人为主观因素影响；利用计算机技术检测CME 势必成为趋势和发展方向。但是，传统的CME自动检测方法基本使用阈值的方式判别CME，不能较好地判别CME。基于简单的阈值分析对CME 判别存在以下缺陷：(1)阈值难以选定；(2)选定的阈值难以兼顾强CME 和弱CME。因此，当强CME 检测效果好时，它们对特征不明显的弱CME 检测效果变差，且对CME 的角宽度和中心角等信息的检测误差大。

基于学习的检测方法的思路是先使用机器学习方法训练CME分类器，再使用分类器对CME 与背景信息进行分类。Zhang 等人[7]8]提出基于 AdaBoost 的日冕图像识别方法，该方法直接识别扇形区域的CME。与 Zhang 等人不同，Yin 等人[9提出在极坐标下检测CME 的学习方法，该方法提取图像的纹理、灰度和 HOG（Histogram of Oriented Gradient）等特征，训练多特征融合的分类器进行CME 检测。然而，基于学习的检测方法基本使用人为定义特征进行CME 建模，而CME的图像特征复杂多变，不同的CME之间的特征差异大，这导致人为定义特征对CME 的建模效果较差。

Faster R-CNN[10] 是现阶段最好的目标检测算法之一。基于深度学习神经网络，FasterR-CNN 通过自主学习数据集的特征训练出一个优秀的目标检测网络。FasterR-CNN 在PASCAL VOC（Pattern Analysis, Statistical Modeling and Computational Learning）数据集[11]上检测结果的 mAP(mean Average Precision)高达 $7 3 . 2 \%$ ，检测效果良好，现已被应用到多种检测场景[12][13]。Faster R-CNN 的特征提取网络能对CME 进行较好建模，解决了现有CME检测方法存在的人为定义特征无法很好表达CME的问题。另外，FasterR-CNN使用神经网络训练出的分类器比基于学习的方法的分类器的效果相对较好。基于以上原因，本文提出一种基于FasterR-CNN 的日冕物质抛射检测方法。本文的主要工作包括：(1)参考CDAW、CACTus、SEEDS等CME目录和通过人工校验标注数据集，本文标注了包含9113幅日冕图像的目标检测数据集；(2)针对日冕图像的特点改进FasterR-CNN模型，使其更适合CME检测。

# 1 深度学习算法及FasterR-CNN

随着机器学习的发展和计算机硬件水平的提高，基于深度学习的目标检测算法层出不穷。在该类算法中，R-CNN(Region-based Convolutional Neural Networks)系列（Faster R-CNN是其中的突出代表）、SSD(Single Shot MultiBox Detector)[14]和 YOLO(You Only Look Once)[15]是现有性能比较突出的几种算法。该类算法按处理流程主要分为两类：单步（one-state）检测算法和双步（two-state）检测算法。双步检测算法分两个步骤处理目标检测问题，先通过选择性搜索算法或区域建议网络选取一定数量的候选框，然后通过分类网络和回归网络确定目标物体的类别和位置。由于候选框选取阶段比较耗时，双步检测算法实时性略差，但精度高。为了提高目标检测的实时性，WeiLiu等和Joseph Redmon等分别提出了SSD 和YOLO等单步检测算法。这类算法不需要候选框选取，直接从原图产生目标的类别和位置，实时性好，但精度略逊于双步检测算法。这两类算法在自然图像集上的检测效果都远超于传统检测方法。通过实验对比，FasterR-CNN在日冕图像等非自然图像的检测鲁棒性比SSD 和YOLO好，我们选择FasterR-CNN 作为基础网络搭建CME 检测网络。

FasterR-CNN 是FastR-CNN[16]的改进算法。FastR-CNN 使用选择性搜索算法选取候选框，这一步骤消耗时间长，成为该方法提高实时性的瓶颈。FasterR-CNN将选择性搜索算法替换为区域建议网络（Region ProposalNetwork,RPN），提高了候选框选取的效率而检测精度不受影响。FasterR-CNN的网络模型如图2所示，该网络可分为特征提取网络、区域建议网络和分类器三个模块。

![](images/f222eaef58ad49628532128c57c7de3b5c48b5e588f8c8f60ec54c745099a73a.jpg)  
图2Faster R-CNN 模型框架图  
Fig.2FasterR-CNN model framework

特征提取网络使用卷积层 $+$ 激活层 $+$ 池化层提取图像的特征图，FasterR-CNN使用VGG16 网络[17]作为特征提取网络。特征图被共享用于后续的区域建议网络和分类器。

区域建议网络用两个分支处理特征提取网络输出的特征图。一个分支结合锚点选取可能包含目标的候选框，另一个分支生成候选框包含目标的概率。结合两个分支得到候选目标的位置和置信度。锚点是RPN的精髓，是基于特征图的每个特征点生成的一组矩形框。RPN设置了九种锚点，由三种尺寸和三种长宽比组合组成。三种尺寸为 $6 4 \times 6 4$ ， $1 2 8 \times 1 2 8$ 和$2 5 6 \times 2 5 6$ ，三种长宽比为1：1，1：2和2：1。特征图上每一个元素都根据这九种锚点生成九个候选框。 $\mathrm { N } { \times } \mathrm { N }$ 特征图生成 $\mathrm { N } { \times } \mathrm { N } { \times } 9$ 个候选框。训练过程中随机选择128个正候选框和128 个负候选框进行训练。

分类器利用特征图和区域建议，通过全连接层与 softmax函数计算每个候选框的类别，输出类别概率向量；同时利用边框回归反计算获得每个候选框的位置偏移量，获得更加精确的目标位置。

# 2 改进的 FasterR-CNN框架

FasterR-CNN在自然图像数据的检测表现比较好，但由于日冕图像与自然图像的差异，FasterR-CNN直接用于日冕图像检测的效果比较差，主要有以下两方面的原因：

a）本文数据集所用的日冕图像的差分图是灰度图，所含色彩与纹理等特征不如PASCALVOC、COCO[18]等数据集中的自然图像丰富。  
b）日冕图像中的CME目标尺寸与自然图像集的目标尺寸存在差异，使用针对自然图像设置的原始锚点检测效果较差。

基于上述原因，本文根据日冕图像的特点在特征提取网络和锚点参数方面改进了FasterR-CNN。改进的FasterR-CNN模型如图3所示。

![](images/a0d57bacb86c9c1663486d51b3beb6727c1dfad60cc9c1168684ef5e2a82a25a.jpg)  
图3本文改进的FasterR-CNN模型框架，t0表示当前时刻， $_ \mathrm { t - 1 }$ 表示前一时刻，t-2表示前第二时刻。

# 2.1特征提取网络改进

在目标检测领域，VGG16 网络能提取目标的抽象语义特征。但用于日冕图像等非自然图像特征提取时，其存在着随卷积深度的增长导致特征退化而丢失浅层特征的问题。而ResNet101[19]网络通过引入残差网络可解决随卷积深度的增长导致特征退化的问题，残差网络相对于普通网络所不同的是引入了跳跃连接，可以使上一个残差块的信息没有阻碍的流入到下一个残差块，提高信息流通和保留浅层特征,并且也避免了由于网络过深所引起的梯度消失问题和退化问题。日冕图像所含信息量比自然图像少，随着卷积深度增加容易退化，需要保留浅层特征。因此，本文算法选择ResNet101网络作为特征提取网络。

![](images/4f30b385d2d4092fb94343f1f276fc7b6420d7380f94b86d34ebc2f911da3ee7.jpg)  
Fig.3FasterR-Codelframewrkisimproedintispap，tepresentstheurentoment,t-epresentsthepreviousoent and t-2 represents the penultimate moment.   
图4相邻CME 的差分图及极坐标差分图。（a）2014年1月1日15时12分的差分图；（b）2014年1月1日15时 24分的差分图；（c）a图的极坐标图；（d）b图的极坐标图。

Fig.4CMErunningdiferenceimageand polar diferenceimage. (a)Therunningdifference imageat15:12onJanuary2014;(b) Running difference image at15:24on1January2O14;(c)Polarcoordinates ofimagea;(d)Polar coordinatesofimage b.

日冕图像具有明显的时间连续性，相邻时刻的日冕图像具有相似性。图4(a)(b)所示为2014年1月1日15时12分和2014年1月1日15时24分两相邻时刻的日冕图像差分图，由于日冕物质随时间向外抛射，相对前一时刻，后一时刻日冕物质离太阳中心稍远，且两幅图像的背景相似性较高。如图4(c)(d)所示，日冕图像差分图转化为极坐标图后，相邻两幅日冕图像的CME目标在水平方向基本重合，在垂直方向上，后一时刻的CME目标高度稍微变高。由于相邻时刻的日冕图像的CME目标的特征和位置有相似性，相邻图像的特征融合能加强目标特征的表达，更好地将CME目标与背景区分开。为了更好利用日冕图像的时间序列相似性和加强CME目标的特征建模，我们检测某一时刻日冕图像时，将当前时刻特征与前两时刻的特征融合。具体做法为：三个时刻的日冕图像经过同一个特征提取网络生成三幅特征图，三幅特征图由全连接层卷积融合成一幅新的特征图，新的特征图作为RPN 和分类器的输入。

# 2.2修改锚点

K-means[20]是基于距离的聚类算法。它采用距离作为相似性的评价指标，即认为两个对象的距离越近，其相似度就越大。该算法认为类簇是由距离靠近的对象组成的，因此把得到紧凑且独立的类簇作为最终目标。

FasterR-CNN中的原始锚点是针对自然图像设置的,其生成的矩形框面积较大。而CME目标的面积较小且长宽比差异较大，与原始锚点不匹配。基于本文数据集，本文对CME目标的面积和长宽比进行聚类，获得面积和长宽比组合。根据 $\mathbf { k }$ -means 得到的聚类结果，本文设置了九种锚点，为尺寸（ $1 6 \times 1 6 , 3 2 \times 3 2 , 1 2 8 \times 1 2 8$ ）和长宽比（1:1,1:2,1:4）的组合。

# 3 数据集标注

目前还没有关于深度学习及目标检测的CME 数据集，本文采用自制的数据集。本文从SOHO①下载2007年6月至9月、2014年1月至4月共8个月时长的LASCOC2日冕图像数据。LASCOC2图像经过图形形态学、帧间差分、极坐标转化等处理后得到极坐标差分图。差分图能更好分辨出CME目标的运动趋势和减少背景信息及噪声、冕流等非CME信息的影响。极坐标图相对于原始日冕图像更有利矩形框的标注和检测。因此，本文以日冕图像的极坐标差分图作为检测模型的输入。

(a)

![](images/97621a039e8e03d435ae7eb6ab6139fa69e14c55942573b9f7290c9503d9a600.jpg)  
图5CME分类：（a）强CME;(b)弱CME。  
Fig. 5 CME classification :(a) the strong CME;(b) the weak CME.

本文的数据集参考了SEEDS、CDAW、CACTus三大目录的信息标注CME，并通过人工校验进行纠正微调。根据CDAW 目录对CME 种类定义，我们将CME 分为强CME 和弱

CME。强CME[22]是指日冕层在太阳剧烈活动期间抛射出的大量物质，其在日冕图像上表现为：高亮特征区域面积较大、呈扩张状且扩张速度较快、亮度特征明显、抛射角宽度一般大于40度的日冕物质抛射现象，类似CDAW目录中种类标记为空的CME；而弱CME[22]是指太阳活动前后期发生的日冕层抛射物质，在日冕图像上表现为：抛射物质较少、高亮特征不明显、抛射角宽度一般小于30度、一般呈现为小区域的暗团或微亮的细条等日冕物质抛射现象，类似CDAW目录中种类标记为弱或非常弱的CME。如图5所示，(a)、(b)图的左子图矩形框区域分别表示强CME和弱CME，右子图为左子图矩形框区域的放大图。

表1为2007年6月1日至3日期间三大目录的CME标记情况，共标记了16个CME事件，三大目录同时都标记的CME 事件有4个。三大目录都较好地标记了CME 事件，但它们之间存在较大差异且有各自的缺陷。如表1的CME 事件1所示，CDAW在2007年6月1日0时6分标记了这个CME 事件,但CACTus 和SEEDS没有标记。同时也存在CACTus或 SEEDS标记了某CME事件，而其他两个目录没有标记的情况。如表1的CME事件3所示，三大目录都标记了2007年6月1日7时30分时刻起始的CME 事件，但三大目录标记的位置信息差异较大。有时，某一目录标记为两个在角度上相邻的CME 事件，而在另一个目录会将它们标记为同一个CME 事件。另外，三大目录标记的一些CME 事件的位置与图像中CME目标的真实位置有差异。

表12007年6月1日至3日三大目录的CME标记情况对比  
'ab.1 June 1， 2007 solstice 3 three log CME mark comparisor   

<html><body><table><tr><td rowspan="2">CME 事件</td><td colspan="3">CDAW</td><td colspan="3">CACTus</td><td colspan="3">SEEDS</td></tr><tr><td>起始时间</td><td>中心角 （度）</td><td>角宽度 （度）</td><td>起始时间</td><td>中心角 （度）</td><td>角宽度 （度）</td><td>起始时间</td><td>中心角 （度）</td><td>角宽度 （度）</td></tr><tr><td>1</td><td>2007/6/1 0:06</td><td>227</td><td>13</td><td>11</td><td>11</td><td>11</td><td></td><td>11</td><td>1</td></tr><tr><td>2</td><td>2007/6/1 5:06</td><td>248</td><td>14</td><td>1</td><td>1</td><td>1</td><td>1</td><td></td><td></td></tr><tr><td>3</td><td>2007/6/1 7:30</td><td>88</td><td>53</td><td>2007/6/1 6:54</td><td>91</td><td>28</td><td>2007/6/1 7:54</td><td>84</td><td>38</td></tr><tr><td>4</td><td>2007/6/1 14:06</td><td>228</td><td>7</td><td>1</td><td>1</td><td>11</td><td>1</td><td>1</td><td>1</td></tr><tr><td>5</td><td>2007/6/1 22:06</td><td>288</td><td>121</td><td>1</td><td>1</td><td>11</td><td>1</td><td>1</td><td>1</td></tr><tr><td>6</td><td>2007/6/1 23:54</td><td>86</td><td>75</td><td>2007/6/2 0:06</td><td>101</td><td>32</td><td>2007/6/2 0:06</td><td>107</td><td>21</td></tr><tr><td>7</td><td>1</td><td></td><td>1</td><td>2007/6/2 1:31</td><td>272</td><td>18</td><td>1</td><td></td><td>1</td></tr><tr><td>8</td><td>2007/6/2 3:54</td><td>275</td><td>40</td><td>1</td><td>1-</td><td>11</td><td>1</td><td>1</td><td></td></tr><tr><td>9</td><td>2007/6/2 7:06</td><td>284</td><td>35</td><td>11</td><td>1</td><td>1</td><td>2007/6/2 5:30</td><td>277</td><td>12</td></tr><tr><td>10</td><td>1</td><td>11</td><td>1</td><td>1</td><td>1</td><td>11</td><td>2007/6/27:30</td><td>113</td><td>8</td></tr><tr><td>11</td><td>2007/6/2 17:30</td><td>58</td><td>49</td><td>2007/6/2 16:54</td><td>78</td><td>10</td><td>2007/6/2 17:54</td><td>74</td><td>13</td></tr><tr><td>12</td><td>2007/6/3 4:30</td><td>71</td><td>21</td><td>1</td><td>1</td><td>11</td><td>1</td><td>1</td><td>1</td></tr><tr><td>13</td><td>2007/6/3 6:54</td><td>84</td><td>36</td><td>一</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>14</td><td>2007/6/3 9:54</td><td>86</td><td>71</td><td>2007/6/3 9:54</td><td>83</td><td>40</td><td>2007/6/3 9:54</td><td>81</td><td>45</td></tr><tr><td>15</td><td>2007/6/3 16:30</td><td>249</td><td>30</td><td></td><td>1</td><td>1</td><td>1</td><td>1</td><td></td></tr><tr><td>16</td><td>11</td><td></td><td></td><td></td><td></td><td></td><td>2007/6/3 13:32</td><td>76</td><td>16</td></tr></table></body></html>

针对上述问题，我们先利用三大目录信息自动生成目标框，再使用 lambelImg工具进行手工调整。自动生成和人工调整目标框的步骤：(1)取并集，取三大目录标记的CME 事件的信息的并集；(2)去重，当某个CME 事件被两个以上的目录标记时，首先以CDAW的信息为准，当CDAW没有标记时以SEEDS的信息为准，确定目录信息后将其标注于日冕图像；(3)人工检验，当三大目录出现误检时，手工将误检信息剔除，当参考目录给出的位置偏离CME 真实位置较大时，进行手工调整。进行手工调整时，CME目标的边缘设置为目标区域块的灰度值比图像平均灰度值高于5的像素，当两个目标块的边缘距离小于10个像素点时，两个目标块归为同一个CME目标，边缘重新设置为两个目标块合并后的边缘，最后沿边缘标注CME的矩形目标框。如图6（a）所示，三幅图像分别表示2007年5月1日12时54分日冕图像的CDAW、SEEDS 和本文数据集的标记结果，本文数据集的标记结果是参考CDAW目录信息为主进行微调而产生的。如图6（b）所示，三幅图像分别表示2014年2月16日18时12分日冕图像的 SEEDS、CACTus和本文数据集的标记结果，CDAW在该日冕图像上没有标记CME，本文数据集的标注结果是参考SEEDS目录的信息为主进行微调而产生的。如图6（c）所示，三幅图像分别表示CDAW、SEEDS 和CACTus 的误检情况：第一幅图为CDAW目录在2007年5月2日11时6分日冕图像上标注的CME区域，但此区域并未存在CME目标；第二幅图像为SEEDS目录在2014年2月19日3时24分日冕图像检测到的CME区域，但此区域属于已抛射的CME 留下的尾部，并非一个新的CME 目标；第三幅图像显示CACTus目录在2014年2月19日4时24分的日冕图像上检测到的CME区域，但该区域并未存在CME目标。在人工校验阶段，这些被误检的CME目标将被剔除。

![](images/17f0b322b5749ed9b36d4eaa2aec454197660a07329b5966caa7a995487283d6.jpg)  
图6本文数据集标注示意图。（a）以CDAW为主的情况；（b）以SEEDS 为主的情况；（c）三大目录误检现象。红框表示CDAW，黄框表示 SEEDS，蓝框表示CACTus，白框表示本文数据集。

Fig.6Theanotatedschematicdiagramofthedatasetin thispaper.(a)IncaseswhereCDAWpredominates;(b)InthcaseofSEEDS;(c) Three logerrors.TeredoxesrepresentCDAW,teyellwboxesrepresentSeeds,teblueoxesrepresetCactusndteiteo

represent the text dataset.

基于上述标准，我们标记了从 SOHO 下载的8个月时长的日冕图像数据。其共包含19524幅图像，其中含有CME 目标的图像有9113幅，共标注了1537个CME 事件和13599个标注框。本文选取 2007年7-9 月和2014年1-3月的数据作为训练集，2014年4月数据作为验证集，而2007年6月数据作为测试集。训练集包含有6255幅图像、128个强CME 事件和997个弱CME 事件，验证集包含有1983幅图像、44个强CME 事件和195个弱CME事件，测试集包含有875 幅图像、22个强CME 事件和151个弱CME 事件。

# 4实验训练与结果验证

本文模型在主频2.6GHZ、内存16.00Gb、搭载GTX1070 显卡的联想电脑上训练完成。在ImageNet训练参数的基础上，采用本文自制数据集对本文网络进行Finetune 训练。初始学习率设置为0.001，迭代到35000次时，学习率减小到0.0001，最大迭代次数为70000。为了评价检测模型的检测效果，本文采用召回率、准确率和mAP 等指标进行评估。这三个指标都是强CME和弱CME两个类别的平均值。

# 4.1验证FasterR-CNN改进的有效性

为了验证我们对FasterR-CNN 的改进的有效性，本文设置了五组对比实验，分别为FasterR-CNN、FasterR-CNN+ResNetl01、Faster R-CNN $^ +$ 三个时刻特征融合、FasterR-CNN+锚点改进和集合所有改进的本文模型。在本文数据集的验证集上的实验结果如表2所示。

表 2模型改进的实验结果  
Tab.2 Experimental results of model improvement   

<html><body><table><tr><td>模型</td><td>召回率</td><td>准确率</td><td>mAP</td></tr><tr><td>Faster R-CNN</td><td>0.651</td><td>0.556</td><td>0.591</td></tr><tr><td>FasterR-CNN+ResNet101</td><td>0.699</td><td>0.718</td><td>0.706</td></tr><tr><td>FasterR-CNN+三个时刻特征融合</td><td>0.712</td><td>0.688</td><td>0.694</td></tr><tr><td>FasterR-CNN+锚点改进</td><td>0.792</td><td>0.733</td><td>0.771</td></tr><tr><td>本文模型</td><td>0.873</td><td>0.753</td><td>0.815</td></tr></table></body></html>

首先，分析不同改进对召回率的影响。每一种改进都在召回率上有所提升，锚点改进对召回率提升效果最好，ResNet101网络的提升较小。这是因为改进的锚点更匹配CME 目标的面积和长宽比。在准确率指标上，改进的锚点一样取得最好的提升效果，其他两种改进取得的提升效果也较明显。最后，由于ResNet101保留了日冕图像的浅层特征，三个时刻特征融合更是利用日冕图像的时间相关性加强了当前时刻的CME 特征，三种改进在mAP指标上都提升 $10 \%$ 以上，提升效果比较明显。

最终，集合了三种改进的本文模型在各个指标上都比FasterR-CNN有所提升，其中，召回率提升 $2 2 . 2 \%$ 、准确率提升 $1 9 . 7 \%$ 、mAP提升 $2 2 . 4 \%$ 。这表明了本文基于日冕图像的特点对FasterR-CNN的改进是有效的。

# 4.2不同目标检测算法对比

为了验证本文模型的CME 检测效果，本文分别用本文模型、FasterR-CNN、SSD 和YOLOV3[21]等四类检测模型对本文数据集的验证集进行测试。实验结果如表3所示。

表3四类检测模型的实验结果  
Tab. 3 Experimental results of four kinds of detection models   

<html><body><table><tr><td>模型</td><td>召回率</td><td>准确率</td><td>mAP</td></tr><tr><td>Faster R-CNN</td><td>0.701</td><td>0.557</td><td>0.594</td></tr><tr><td>SSD</td><td>0.671</td><td>0.473</td><td>0.522</td></tr><tr><td>YOLO V3</td><td>0.645</td><td>0.438</td><td>0.504</td></tr><tr><td>本文模型</td><td>0.873</td><td>0.753</td><td>0.815</td></tr></table></body></html>

SSD 和YOLOV3等一步检测算法由于仅提取图像的深层特征、缺少第二次边框回归等原因，在CME 检测上表现较差。FasterR-CNN也存在一步检测算法的缺点，但由于其是两步回归，能通过第二步回归提高检测效果，具有更强的鲁棒性和检测效果。FasterR-CNN的检测效果比 SSD、YOLOV3 略好，但比本文算法检测效果差。本文模型拥有最好的检测表现，mAP为 $8 1 . 5 \%$ 。

# 4.3与传统CME目录对比

如图7所示，一个CME 事件在极坐标图上表现为一系列水平方向上有重合，垂直方向上逐渐升高的具有明亮特征的CME目标。从另一方面说，就是当前时刻日冕图像中的CME目标与前一时刻图像中的某个CME目标在水平方向上重合且在垂直方向上升高时，这两个目标就属于同一CME 事件。利用这个特征，我们在本文模型检测出的结果数据上定义了CME 事件的认证标准：相邻时刻图像上的两个目标框在水平方向上重叠率超过 $50 \%$ 并且在垂直方向上随时间升高，即可认定这两个目标框属于同一个CME 事件，重叠率为两个目标框在水平方向的重叠宽度除于宽度较小的目标框的水平宽度。根据认证标准，我们确定一个CME 事件所包含的多个CME目标框。如果这些目标框超三分之二为弱CME目标，则该CME 事件为弱CME，反之，认为其为强CME。角宽度为该CME 事件的多个目标框的右边界的最大值与左边界的最小值之差；中心角为该CME 事件的多个目标框的左边界的最小值加上角宽度的二分之一。根据定义，我们遍历本文模型的检测结果生成本文的CME目录。本文2007 年6 月的 CME 目录被发布于 https://gitee.com/xian-xianggui/faster-rcnn-cme。

![](images/3492b5b0f0713c0f6c5a65085cf2b9d2870b9b7b78d54e411c4f0b05653a0a86.jpg)

![](images/305140930c406333896336c06f1451f38f3c54be9858edd147ac67ac03569042.jpg)

图72007年6月9日16时 54分起始的弱CME 事件前三帧的检测效果，红框为CDAW检测结果，黄框为SEEDS 检测结果，白框为本文数据集标注结果，CACTus 没有检测到此事件。（a）-（c）为16时54分、17时06分、17时30分的极坐标差分图；（e)-（f）为（a）-（c）对应的日冕图像差分图。

Fig.7ForthedetectioneectoftefisteeframesofweakCMEvetstartigat16:54onJune9,7,teedboxistetestsult ofCDAW,theyellowboxis tetestresutofSEEDS,andthewhiteboxisteanotationresultoftedatasetithispaper.Cactusdid notdetectthisevet(a)-(c)is tepolacoordiateruingdierenedagaat6:54,7:06and17:30;(e)-(f)isteng difference diagram of coronal image corresponding to (a) - (c).

目前，学术界对CME 事件的定义并不明确，在CME 检测的正确率方面也没有公开的评价标准。本文标注的数据集参考了现有的CDAW、CACTus、SEEDS 等三大CME 目录，综合了它们的优点，并通过人工校验进行人工调整，具有一定的准确性和全面性。以我们自制的数据集为参照标准，我们对比了本文目录与现有三大目录的检测效果。以2007年6月的数据集作为测试集，本文从两个方面对CME 检测效果进行评估：CME 事件数量的检测和CME事件参数的检测。

# 4.3.1CME正确检测数量

在CME 事件数量检测方面。强CME 是活动比较激烈的太阳活动，对太空天气和人类生活的影响大，因此能正确检测出强CME 非常重要。本文首先在强CME 正确检测数量上与现有三大目录比较。另外，现有的检测方法在弱CME 检测上表现均不如强CME。因此，提高对弱CME 的检测正确率也是CME 检测方法改进的重要目的。

由于CME 定义与背景冕流的影响,CDAW等人工标记目录和自动检测的目录得到同一个CME 事件的特征参数有差异。虽然不同目录得到同一个CME 事件的参数有一定偏差，但从相关性上可确定为同一CME事件。本文定义检测正确的CME 事件为：目录标记的CME事件在水平方向上的角度与数据集标注的CME事件的角度重叠率大于 $50 \%$ ，且CME事件的起始时刻与数据集CME 事件的起始时刻相差在1.5个小时以内，则目录标记的该CME事件被认定为一个检测正确的CME 事件。如图7所示为检测正确的CME：CDAW检测到的CME位置与数据集的重叠率为 $100 \%$ ，且起始时间与数据集标注的起始时间一样都是在16 时54分，即CDAW 的检测结果是正确的；SEEDS 检测到的CME 位置与数据集的重叠率为 $100 \%$ ，且起始时间与数据集标注的起始时间相差12分钟，即 SEEDS 的检测检测结果也是正确的。

![](images/4ee935224bc2ab98ad61b8d370b141ab0df98688f5c3510397040483eba3f162.jpg)  
图8各个目录的正确CME数量的对比图

各个目录的正确CME 数量的对比结果如图8所示。我们使用的2007年06月的测试集共标记了22个强CME 和151个弱CME。强CME 检测方面，CDAW、SEEDS、CACTus分别检测出22个、11个和9个。弱CME 检测方面，CDAW、SEEDS、CACTus分别检测出127个、15个和11个。而本文算法检测出了22个强CME 和138个弱CME。因此，在强CME 和弱CME 检测上，本文算法都取得最好的效果。这是因为在标注数据集时我们综合了三个目录的信息，标注一些在CDAW 没有的，但可以在 SEEDS或CACTus 目录找到的CME。如图9所示，(a)图为本文方法和其他CME 目录对强CME 的检测效果；(b)图为本文方法和其他CME目录对弱CME的检测效果。

![](images/f5dbb339a59db58450939543decce2a9320fc632b5c7bef42feaf63197a13f3a.jpg)  
Fig.8A comparison of the correct number of CME entries for each log   
图9本文方法检测效果，（a）强CME 检测效果；（b）弱CME 的检测效果。红框表示CDAW,黄框表示 SEEDS，蓝框表示CACTus，白框表示本文检测结果。  
Fig.9Thedetectionefecofthismethodis(a)strongCMEetectionefect;(b)WeakCMEdetectionefetRedboxesrepresntCDAW yellow boxes represent SEEDS, blue boxes represent Cactus,and white boxes represent article logs.

# 4.3.2CME特征参数

CME特征参数检测的准确性是评价CME检测算法的重要部分。本文将以2007年06月测试集为基准，对比本文算法与其他三个目录在CME的中心角和角宽度的检测上的表现。CME 事件在极坐标图上表现为一系列水平方向上有重合，垂直方向上逐渐升高的具有明亮特征的CME目标。本文取测试集CME 事件标注的多个CME目标的最小左边缘作为整个CME 事件的左边缘，多个CME目标的最大右边缘作为整个CME 事件的右边缘，左右边缘的宽度即为CME 事件的角宽度，中心点的角度即为中心角。由此，本文得到测试集的各CME 事件的中心角和角宽度的参数。检测结果显示，本文算法与三大目录同时都标记到的强CME有9个，弱CME有10个。以这19个CME 事件为对象，参照测试集的参数为标准，本文统计本文目录和三大目录各自的相对于测试集的中心角和角宽度的平均误差。统计结果如图10 所示。

![](images/34996c613b269ef2db00669f1cedda4282d51841a9481ad73b4e0f3b37d60d9b.jpg)  
图10各个目录的CME参数的平均误差  
Fig.10Average error of CME parameters for each log

从图10可以看出，本算法和CDAW目录在中心角和角宽度上与测试集相差不大，本文目录的中心角和角宽度平均误差分别为3.3度和8.2度，CDAW目录平均误差为5.6度和10.4度。而SEEDS和CACTus目录由于采用简单阈值的方法判别CME，它们的中心角和角宽度的平均误差相对较大。本文算法在CME 中心角和角宽度的检测方面都比现有三大目录更精确。

# 5 结束语

由于人为定义CME 特征和设定CME分割阈值，现有的CME检测方法难以很好建模CME 及选取普适性的阈值，存在检测效果不好的问题。因此，本文引入基于深度学习的目标检测模型检测CME。首先，参考CDAW、CACTus 和SEEDS等目录标注CME数据集，利用自制数据集训练出的特征提取网络能够很好提取CME 特征信息。另外，深度学习检测模型自主训练分类器，避免了人为设定阈值的缺陷，因此本文算法对CME有较好的检测效果。以2007年6月的测试集为基准，本文算法有以下优势：一、本文算法对强CME 和弱CME的检测正确率分别达到 $100 \%$ 和 $91 . 4 \%$ 。其中对全部CME的检测准确率为 $9 2 . 5 \%$ ，分别比CDAW、SEEDS 和CACTus 高出 $6 . 4 \%$ 、 $72 \%$ 和 $81 \%$ ；二、能够检测出CDAW目录漏标的弱CME 事件，我们检测出的CDAW 漏掉的弱CME有一部分是 SEEDS 或CACTus 标注的弱CME，另一部分根据我们给出的弱CME 的定义可认证为弱CME；三、在本文标注的测试集上，本文算法检测出的CME中心角和角宽度等参数比现有三大目录更精确。

本文工作有以下两个创新意义。首先，引入深度学习方法，自主提取CME 特征，能更好表达CME 目标，取得了较好的CME 检测效果。另外，参考CDAW、CACTus、SEEDS三大目录的CME信息，我们标注了目标检测的CME 数据集。这个数据集综合了三大CME目录的优势并经过人工校验调整，能一定程度正确反映CME的发生情况，也可为后续CME的检测提供数据集上的参考。虽然，本文对CME 检测进行了研究并取得了一定的进展，但限于时间和知识面的关系，后续还可进行以下改进：(1)数据集的信息相对单一且没有用到CDAW 等三大目录的速度和加速度等参数，后续可以加入这些信息。(2)本文算法没有测量CME 事件的速度等特征，后续可以检测这些CME参数。

# 参考文献：

[1]李波,赵寄昆.日冕物质抛射[J].天文学进展,2000(03):192-208.   
[2] 郭敏,尚振宏,强振平,黎敬涛,洗祥贵,杨志鹏.日冕物质抛射检测研究进展[J].天文研究与技术,2020,17(01):39-51.   
[3]BERGHMANSD,FOING B,FLECK B.Automated detectionof CMEs inLASCO data; proceedingsofthe fromsolarmin to max: Half a solar cycle with SOHO,F,2002 [C].   
[4]ROBBRECHTE,BERGHMANS D.Automated recognitionof coronal massejections (CMEs) innear-real-time data[J]. Astronomy & Astrophysics,2004,425(3): 1097-106.   
[5]OLMEDOO,ZHANGJ, WECHSLERH,etal. Automatic detectionandtracking ofcoronal mass jections incoronagraphtime series [M]. Solar Image Analysis and Visualization.Springer.2008: 275-89.   
[6]OLMEDO O,ZHANG J.Partial torus instability[J].The Astrophysical Journal,2010,718(1): 433.   
[7]ZHANGL,YIJ-Q,LIJ-B,etal.DetectionofcoronalmassejectiosusingAdaBoostongraysalestatisticfeatures[J].New Astronomy,2016,48: 49-57.   
[8]ZHANGLYIJ-Q,LIJ-B,etal.Detectioofcoronalmassjectionsusing multiplefaturesand spacetimecontiity[J]. Solar Physics,2017,292(7): 91.   
[9] YIN J, YAOH,LIN J,et al. Coronal Mass Ejections detection using multiple features based ensemble learning[J]. Neurocomputing, 2017,244: 123-30.   
[10]Ren S,HeK,GirshickR,etal.FasterR-CNNR-CNN:TowardsReal-TimeObjectDetectionwithRegioProposal Networks[J]. IEEE Transactions on Pattern Analysis & Machine Intelligence,2017,39(6):1137-1149.   
[1]EveringhamM,GoolLV,WillimsCKI,etal.ThePACALVisualObjectClass (VOC)Challnge[J].IterationalJoal of Computer Vision,2010,88(2): 303-338.   
[12]岳邦铮，韩松．基于改进Faster R-CNN 的 SAR 船舶目标检测方法[J].计算机与现代化,2019,000(009):90-95,101.   
[13]杨薇，王洪元，张继,等．一种基于Faster-RCNN 的车辆实时检测改进算法[J].南京大学学报:自然科学版,2019,55(2): 231-237.   
[14] Liu W,Anguelov D,Erhan D,et al. SSD: Single Shot MultiBox Detector[J].2015.   
[15] REDMONJ,DVVALAS,GRSHCKR,etal.Youonlylook once:Unified,real-teobjectdetection[C/Proeedingsofth 2016 IEEE Conference on Computer Vision and Pattern Recognition.2O16:779-788.   
[16] Girshick R.Fast R-CNN[J]. Computer ence,2015.   
[17]SimonyanK,ZiseranA.VeryDepConvolutionalNetworksforLrge-ScaleIageRecogition[J].ComputerScience,014.   
[18]LinTY,MaireM,Belongie S,etal.Mcrosoft COCO: CommonObjectsinContext[C//European ConferenceonComputer Vision. Springer International Publishing,2014.   
[19]He K,ZhangX,RenS,etal.DeepResidualLearningforImageRecognition[C/2016IEEConferenceonComputerVision and Pattern Recognition (CVPR). IEEE,2016.   
[20] Huang ZExtensionstothek-Means Algorithmfor Clustering Large DataSets with Categorical Values[J].Data Mining and Knowledge Discovery,1998,2(3): 283-304.   
[21] REDMONJ,FARHADI A YOLO v3: An incremental improvement[J]. Computer Science,2018:arXiv:1804.02767.   
[22]姚海，尹建芹，林佳本,等．一种端到端的日冕物质现象检测新方法[J].科学通报,2017(23):2680-2690.

# Detection algorithm of Coronal Mass Ejections based on Faster R-CNN

Xian Xianggui, Shang Zhenhong, Yuan Meiyu, Yang Zhipeng (FacultyofIformationEngineringndAutomation,KunmingUnversityofcienceandTechology,Kunming60o,Cina)

Abstract: Coronal Mass Ejection (CME) is a strong solar eruption, which has a great impact on space weather and human life. Therefore, CME detection is of great significance in predicting CME and ensuring the safety of human production and life. The existing detection methods mostly use artificial defined features and artificial defined threshold to detect CME.Because artificially defined features cannot well represent weak CMEs and it is difcult to select a universal threshold,the detection effect of existing CME detection methods for weak CMEs needs to be improved.A CME detection algorithm based on Faster R-CNN is proposed in this paper. In this method, a dataset containing 9113 coronal images was manually annotated by combining the log information of three famous CME catalog, CDAW, SEEDS and CACTus. Then, according to the characteristics of CME images with fewer features than natural images and the difference in target size from natural images,Faster R-CNN was improved in feature extraction and anchor point selection. Using the CME data in June 2007 as the test set, the algorithm detected 22 out of 22 strong CME events and 138 out of 151 weak CME events,and the detection errors of characteristic parameters such as center Angle and Angle width of CME events were within 5 degrees and 10 degrees,respectively.

Key words: Coronal Mass Ejection; Target detection; Image processing