# 基于深度学习的太阳活动区检测与跟踪方法研究

朱健¹，杨云飞¹²，苏江涛²，刘海燕¹，李小洁¹，梁波¹，冯松¹（1.昆明理工大学信息工程与自动化学院/云南省计算机技术应用重点实验室，云南 昆明 650500；2．中国科学院太阳活

动重点实验室，北京100101)

摘要：太阳活动区是各类太阳活动的主要能量来源，剧烈的太阳活动会直接影响人类的生存环境，因此准确地检测与跟踪太阳活动区对监控和预报空间天气非常重要。本文基于深度学习框架的YOLOv3-spp 和DeepSort提出了一种太阳活动区检测和跟踪方法(ActiveRegions Detection and TrackingMethod,ARDTM)，该方法较好地解决了传统图像处理方法易将一个太阳活动区误检测为多个，或者多个太阳活动区误检测为一个活动区的问题；及时捕获到新产生的太阳活动区和终止跟踪消失的太阳活动区，有效地提高了太阳活动区的跟踪准确率。实验结果表明该方法可以较好地检测和跟踪不同望远镜、不同时间间隔序列图像中的太阳活动区。

关键词：太阳活动区； 检测与跟踪； 深度学习；YOLOv3-spp；DeepSort中图分类号：TP391.413

太阳活动区是太阳强磁场区域，是太阳活动的主要能量来源。剧烈的太阳活动会导致恶劣的空间天气，比如耀斑和日冕物质抛射等，会对地球上电磁通信、电力系统、无线电传输等产生不利影响。因此对太阳活动区进行检测与跟踪，分析其演化规律，对人类的空间探索和地球生活有着重要的意义[1,2]。

目前用来解决太阳活动区检测与跟踪的方法主要采用传统的图像处理技术[1-11]。比如检测主要采用强度阈值法或区域生长等方法，这些方法一般需要设置参数，比如强度阈值、开闭算子阈值和区域生长的边界阈值。这些参数对于这些传统的方法来说至关重要，文[2,6]对参数进行了详细讨论，并给出了设置参数的一些准则。跟踪太阳活动区则主要根据纬向较差自转定律来预测其位置，然后根据欧式距离或特征的相关性进行目标关联[34]。

这些方法虽然较好地实现了太阳活动区的检测与跟踪，但是仍存在一些问题。比如，文[2-4]的方法容易导致一个太阳活动区被误检测为多个，或者多个相邻的太阳活动区被误检测为一个，从而导致误跟踪；SolarMonitor]使用的太阳活动区美国国家海洋和大气管理局(National Oceanic and Atmospheric Administration，NOAA)编号被广泛使用，但存在未能及时标注新浮现的太阳活动区和仍标注了已经在全日面像上消失的太阳活动区等现象。

近年来，随着深度学习[12]的普及和CNN等神经网络的发展，一些基于深度学习的目标检测和跟踪的算法被提了出来。比如,典型目标检测算法有:R-CNN[13]、Fas ter R-CNN[14]、YOL0[15]、YOLOv3[1]等。其中，YOLOv3借鉴残差网络的思想采用了新的特征提取网络Darknet $^ { - 5 3 }$ ，并结合多尺度特征进行目标检测，取得了较好的检测性能。典型多目标跟踪方法有：EAMTT[17]、STAM[18、DeepSort[19等。其中，DeepSort具有较好的跟踪性能和较高的实时性能。在天文领域的研究中，越来越多的深度学习方法被采用[20-22]。

本文针对太阳活动区的演化特性，采用YOLOv3-spp作为检测算法和DeepSort作为跟踪算法并进行改进，提出了一种太阳活动区检测和跟踪方法(Active Regions Detection and

Tracking Method，ARDTM)。该算法可以有效地检测并跟踪不同时间间隔序列图像中的太阳活动区。第一节介绍了所使用的数据和制作的数据集，第二节简述了ARDTM方法，第三节是实验结果与分析，第四节对本文进行总结与展望。

# 1数据和数据集

本文采用了太阳动力学天文台(Solar Dynamics Observatory，SDO)卫星的日震及磁场成像仪(Helioseismic and Magnetic Imager，HMI)与日球天文台(Solar and HeliosphericObservatory，SOHO)的迈克逊多普勒成像仪(Michelson Doppler Imager，MDI）两个设备的太阳全日面纵向磁图作为数据来源，制作了太阳活动区检测与跟踪的深度学习的训练和验证数据集。

表1列出了分别用于太阳活动区检测与跟踪的数据集。D1共选取了3017张全日面图像用作制作太阳活动区检测网络的训练和验证集，共选取了16 361个太阳活动区样本，其中$8 0 \%$ 作为训练样本用于训练深度学习网络模型， $2 0 \%$ 作为验证样本在训练过程中用于防止过拟合的验证。D2共选取了33515个太阳活动区样本用于跟踪过程中重识别网络的训练和验证，将太阳活动区局部区域缩放为 $1 2 8 \times 1 2 8$ 像素尺寸，同样 $8 0 \%$ 用于训练， $2 0 \%$ 用于验证。本文根据 SolarMonitor 网站上标注的太阳活动区NOAA编号，结合人工辅助判断的方式，采用labelImg 标注软件标注了数据集。

表1太阳活动区检测和跟踪数据集  
Table 1 The dataset of active regions detection and tracking   

<html><body><table><tr><td>数据用途</td><td>数据集编号</td><td>设备来源</td><td>目的</td><td>时间/间隔</td><td>样本数量</td></tr><tr><td rowspan="2">训练／验证</td><td>D1</td><td>HMI</td><td>检测</td><td>2011.01.01-2017.12.31</td><td>16 361</td></tr><tr><td>D2</td><td>HMI</td><td>跟踪</td><td>2011.11.01-2011.11.30/12分钟</td><td>33515</td></tr></table></body></html>

# 2方法

ARDTM算法主要分为两个部分：检测与跟踪。在检测部分，本文采用了 $\mathrm { Y 0 L 0 v 3 - s p p }$ 模型。该模型的网络结构如图1所示，由Darknet $- 5 3$ (图1.a)与yolo层(图1.b)两部分组成，分别用于提取图像特征与多尺度预测。方法步骤主要如下： (1)将全日面图像压缩为 $6 0 8 \times$ 608 的尺寸输入网络。 (2)输入图像经过一个卷积单元(Convolutioanl)得到32个 $6 0 8 \times 6 0 8$ 的特征图。卷积单元包含卷积、批量归一化和leakyrelu激活函数三个部分。(3)特征图经过步长为2、64个卷积核的卷积单元实现降采样，得到64个 $3 0 4 \times 3 0 4$ 的特征图，然后送入残差单元(Residual)，输出64个 $3 0 4 \times 3 0 4$ 的特征图(1x残差块)。1x表示此残差块由1个残差单元组成。残差单元是将输入与两个卷积单元进行残差操作。(4)上一步得到的特征图经过降采样和2x残差块得到128个 $1 5 2 \times 1 5 2$ 的特征图。其中 $2 \mathrm { x }$ 表示此残差块由2个残差单元组成。 (5)接下来依次执行降采样、 $8 \mathrm { x }$ 残差块、降采样、 $8 \mathrm { x }$ 残差块、降采样， $4 \mathrm { x }$ 残差块操作。三个残差块依次得到256 个 $7 6 \times 7 6$ 、512个 $3 8 \times 3 8$ 和1024个 $1 9 \times 1 9$ 的特征图。(6)将 $8 \mathrm { x }$ 、8x 和 4x三个残差块的结果送入yolo 层(图1.b)。(7) $1 9 \times 1 9$ 的特征图经过金字塔卷积集(convolutional-spp Set)等操作得到第一次的检测结果(Output1)；同时，将金字塔卷积集的结果上采样至 $3 8 \times 3 8$ 与第四个残差块的 $3 8 \times 3 8$ 的特征图融合，经过卷积集(Convolutional Set)等操作得到第二次的检测结果(Output2)；依次类推，得到第三次的检测结果(0utput3)。其中，卷积集操作包含5个卷积单元；金字塔卷积集是在卷积集基础上添加了空间金字塔池化[23]。(8)将以上三次的检测结果使用非极大抑制算法去除交并比较大的预测框，保留置信得分较高的预测框作为太阳活动区的检测结果。该网络的损失值由三个部分合成：目标定位偏移量损失、目标置信度损失和目标类别损失。其中，目标置信度损失和类别损失采用了二元交叉熵损失，目标定位损失则采用了均方误差进行计算。

Darkent53 yolo Type Filters Size Output Convlutional Convolutional   
1 Convolut ioanal 32 3x3 608x608x32 一 Set 3x3   
1 Convolutioanal 64 3x3/2 304x304x64 ↑ 1 1   
一 Convolutioanal 32 1x1 304x304x32 Concat Conv Output3   
1 1x Convolut ioanal 64 3x3 304x304x64 ↑ 1x1   
1 Residual Up Sampling   
一 Convolutioanal 128 3x3/2 152x152x128 ↑ 1   
一 Convolut ioanal 64 1x1 152x152x64 Convolutional 一 一   
一 2x Convolut ioanal 128 3x3 152x152x128 1x1 一   
1 Residual 4 一   
一 Convolutioanal 256 3x3/2 76x76x256 Convlutional Convolutional Set 3x3 1   
一 Convolut ioanal 128 1x1 76x76x128   
1 8x Convolutioanal 256 3x3 76x76x256 ↑ 1   
一 1 Resvdlut ioanal 512 3x3/2 38x38x512 Concat Coxv Output2   
一 Convolut ioanal 256 1x1 38x38x256 Up Sampling   
1 8x Convolutioanal 512 3x3 38x38x512 4   
1 Convg gtaa Convolut ional COxY Output1   
一 1024 1x3/2 19x19x5024 1   
一 4x Convolut ioanal 1024 3x3 19x19x1024 一 Convolutional- Convolutional 一_ 1 (a) (b)

在跟踪部分，本文基于DeepSort算法对其进行改进，主要步骤如下：

(1)根据太阳活动区的特性改进了DeepSort 的特征提取网络，本文将其称之为太阳活动区重识别网络，如图2所示。首先将检测到的太阳活动区缩放为 $1 2 8 \times 1 2 8$ ，经过2次 $3 \times 3$ 的卷积、1次最大池化以及6个残差块，特征图的大小减小到 $1 6 \times 1 6$ ，再经过一个全连接层得到128 维的全局特征向量，最后采用L2归一化得到特征向量。在训练过程中，采用CosineSoftmax函数得到分类结果，采用交叉熵计算损失值。需要说明的是检测部分的网络和太阳活动区重识别网络虽然都提取太阳活动区的特征，但是作用不同。检测部分的网络主要用于检测太阳活动区，而太阳活动区重识别网络主要为了判定太阳活动区在演化过程中的特征相似性。

(2)用太阳活动区重识别网络提取已跟踪到的太阳活动区(称为轨迹，假设数量为L)和当前帧检测到的太阳活动区(假设数量为J)的特征向量，计算之间的余弦距离，得到关联矩阵 $\mathrm { C } _ { \mathrm { L } \times \mathrm { J } }$ 。然后，根据前一帧所有太阳活动区的位置，采用纬向较差自转[24,25]预估在当前帧的位置。接着，计算所有预测位置和所有检测位置的欧氏距离，若过大则将关联矩阵中对应的值设置为无穷大。

(3)对关联矩阵 $\mathrm { C } _ { \mathrm { L } \times \mathrm { J } }$ 采用匈牙利匹配算法[26]，得到三类匹配结果：匹配到检测结果的轨迹、未匹配到轨迹的检测结果和未匹配到检测结果的轨迹。对于匹配到检测结果的轨迹则继续跟踪；未匹配到轨迹的检测结果则为之分配一个新的轨迹，当新轨迹连续3帧匹配到检测结果时，则认为该太阳活动区产生，否则，删除该轨迹。对于未匹配到检测结果的轨迹则提取使用纬向较差自转预测结果的特征向量，与前一帧对应的特征向量计算余弦距离。若其值在一定范围内(本文实验结果为0.7)则采纳该预测结果作为轨迹的一部分，否则该活动区结束。但如果连续3帧均为预测结果则也判定该活动区结束。

input (Convolution) 32x128x128 (Convolution) 32x128x128 (MAX Pooling) 32x64x64 Patch size:3x3 Patch size:3x3 Patch size:3x3 Stride:1 Stride:1 Stride:2 Residual 4 (Convolut ion) (Convolution) 32x64x64 Residual_5 32x64x64 Patchisize:3x3 Patchrsize:3x3 Patch sze13x3 add Residual 6 64x32x32 Residual 7 64x32x32 Residual 8 128x16x16 (Residual) (Residual) (Residual) Patch size:3x3 Patch size:3x3 Patch size:3x3 Stride:2&1 Stride:1&1 Stride:2&1 Patesdua19x3 128x16x16 Densel10 128 normalization 128 connected) Stride:1&1

# 3实验结果与分析

本文采用 HMI和MDI的四组全日面序列图像进行了测试。这四组数据分别代表了不同的观测设备和活动区数量。表2列出了数据的基本信息，为了便于描述，分别用D3—D6 表示。其中，D3 和 D4 选取了MDI纵向磁图，D5 和 D6 选取了HMI纵向磁图。D4 和 D6 选取了太阳活动区数量较多的序列图像，而D3和D5 选取了活动区数量较少的序列图像。由于时间间隔较长的数据太阳活动区的特征变化大，跟踪难度较高，因此四组数据均采用时间间隔较长的序列图像(为了便于与 SolarMonitor 结果进行比较，数据与SolarMonitor 提供的数据时间基本一致)。

表2列出了四组数据集的跟踪结果，并与 NOAA进行了对比。包括 SolarMonitor上标注的 NOAA 活动区数量、ARDTM方法标注的太阳活动区数量、ARDTM结果与NOAA 结果相同的活动区的数量（ARDTM∩NOAA)、NOAA 活动区数量与交集的差值(NOAA-（ARDTMNOAA)）、ARDTM活动区数量与交集的差值(ARDTM-（ARDTM∩NOAA)）、交集与NOAA活动区数量的百分比（（ARDTMONOAA)/NOAA）。NOAA一共标注了806个活动区，ARDTM标注了872个，两者的交集为755个。ARDTM方法标注的活动区比NOAA的多一些，主要由以下四种情况产生：（1）ARDTM及时标注了新出现的活动区，而NOAA存在未能及时标注的现象；（2)ARDTM较完整地标注了活动区的演化末期，而NOAA已经提前结束了对其标注；（3)ARDTM标注了一些没有被 NOAA标注的活动区，这些活动区的特点均为磁场强度较弱、磁结构特征不太明显，但日面已有黑子产生且持续了3帧以上；(4)一些已具有磁场特征但未形成黑子的活动区被ARDTM误跟踪。这三种情况所占比例分别为 $5 2 \%$ 、 $1 0 \%$ 、 $3 2 \%$ 和 $6 \%$ 。这意味着一半以上的情况是ARDTM及时标注了新出现的活动区。反过来，NOAA 标注的活动区比交集多了51个，这意味着ARDTM 没有标注51个被NOAA标注的活动区。造成此情况的主要原因有：(1)太阳活动区的特征已经在纵向磁图上消失但仍被NOAA标注；(2)ARDTM漏标注一些磁场强度较弱且特征不明显的活动区。两种情况所占比例分别为 $8 8 \%$ 和 $1 2 \%$ 。在这四组数据中，NOAA在D4数据集上及时地跟踪了新活动区和终止跟踪消失的活动区，所以本文方法和NOAA的结果相似度最高。

为了说明以上几种情况，表3详细列出了D6 测试集中前十天的跟踪结果，第2—6 列的数据含义与表2相同，第7列详细列出了ARDTM方法与NOAA标注结果不同的具体情况。比较典型的是AR12185于10月5日出现，但NOAA于7日才开始标注；AR12183左侧有个活动区，于10月5日形成了黑子，一直到14日才消失，但该活动区一直未被N0AA标注；AR12173已于10月3日消失于日面，但NOAA仍做了标注。

# 表2跟踪结果

Table 2 The tracking results   

<html><body><table><tr><td>数据 集编 号</td><td>数据 来源</td><td>时段</td><td>NOAA 结果</td><td>ARDTM 结果</td><td>ARDTM N NOAA</td><td>NOAA-(ARDT M O NOAA)</td><td>ARDTM-(ARD TM N NOAA)</td><td>(ARDTMN NOAA)/NO</td></tr><tr><td>D3</td><td>MDI</td><td>2005.03.01-2005.03.31/24小时</td><td>68</td><td>72</td><td>62</td><td>6</td><td>10</td><td>91.18%</td></tr><tr><td>D4</td><td>MDI</td><td>2000.07.12-2000.08.11/24小时</td><td>410</td><td>415</td><td>398</td><td>12</td><td>17</td><td>97.07%</td></tr><tr><td>D5</td><td>HMI</td><td>2010.11.05-2010.12.04/24 小时</td><td>103</td><td>108</td><td>91</td><td>12</td><td>17</td><td>88.35%</td></tr><tr><td>D6</td><td>HMI</td><td>2014.10.01-2014.10.31/24小时</td><td>225</td><td>277</td><td>204</td><td>21</td><td>73</td><td>90.67%</td></tr><tr><td>合计</td><td></td><td></td><td>806</td><td>872</td><td>755</td><td>51</td><td>117</td><td>91.82%</td></tr></table></body></html>

# 表3D6数据集部分跟踪结果

Table 3 The tracking results of D6 dataset   

<html><body><table><tr><td rowspan="2">日期</td><td rowspan="2">NOAA 结果</td><td rowspan="2">ARDTM 结果</td><td rowspan="2">ARDTM N NOAA</td><td rowspan="2">NOAA-(ARDTM</td><td rowspan="2">ARDTM-(ARDTM N NOAA)</td><td rowspan="2">备注</td></tr><tr><td>N NOAA)</td></tr><tr><td>2014-10-1</td><td>10</td><td>10</td><td>9</td><td>1</td><td>1</td><td>AR12171已从全日面消失，NOAA 仍标记；NOAA 未及时标注AR12182；</td></tr><tr><td>2014-10-2</td><td>9</td><td>9</td><td>8</td><td>1</td><td>1</td><td>AR12175已从全日面消失，NOAA仍标记；NOAA 未及时标注AR12182；</td></tr><tr><td>2014-10-3</td><td>8</td><td>10</td><td>7</td><td>1</td><td>3</td><td>AR12173已从全日面消失，NOAA仍标记；NOAA 未及时标注AR12182、AR12183、AR12184;</td></tr><tr><td>2014-10-4</td><td>10</td><td>9</td><td>9</td><td>1</td><td>0</td><td>AR12172已从全日面消失，NOAA仍标记；</td></tr><tr><td>2014-10-5</td><td>9</td><td>10</td><td>8</td><td>1</td><td>2</td><td>AR12176已从全日面消失，NOAA仍标记；NOAA 未及时标注AR12185；ARDTM标注但NOAA未标</td></tr><tr><td>2014-10-6</td><td>9</td><td>9</td><td>7</td><td>2</td><td>2</td><td>注1个活动区 AR12176 和AR12180 已从全日面消失，NOAA仍 标记；NOAA未及时标注AR12185；ARDTM标注但 NOAA未标注1个活动区；</td></tr><tr><td>2014-10-7</td><td>8</td><td>10</td><td>8</td><td>0</td><td>2</td><td>NOAA 未及时标注AR12186；ARDTM标注但NOAA 未标注1个活动区；</td></tr><tr><td>2014-10-8</td><td>9</td><td>10</td><td>9</td><td>0</td><td>1</td><td>ARDTM标注但NOAA未标注1个活动区</td></tr><tr><td>2014-10-9</td><td>8</td><td>8</td><td>7</td><td>1</td><td>1</td><td>AR12181已从全日面消失，NOAA仍标记；ARDTM 标注但NOAA未标注1个活动区</td></tr><tr><td>2014-10-10</td><td>7</td><td>6</td><td>5</td><td>2</td><td>1</td><td>AR12178和AR12179已从全日面消失，NOAA仍 标记；ARDTM标注但NOAA 未标注1个活动区</td></tr><tr><td>合计</td><td>87</td><td>91</td><td>77</td><td>10</td><td>14</td><td></td></tr></table></body></html>

ARDTM较好地解决了文[4]中提到的一个太阳活动区被误检测为多个，或者多个太阳活动区被误检测为一个活动区的问题。图3(a)采用了文[4]图11(a)的MDI同时间数据(2002年5月4日12:48UT)，红色实线框为ARDTM的检测结果，蓝色虚线框为文[4]的结果。其中，

1和2两个区域分别为AR09934和AR09936，而文[4]误把他们识别成了一个活动区。（b)为HMI的2010年11月12日数据。同样，3和4分别为AR11123和AR11121，而用文[4」方法误识别成了一个活动区。（c)为HMI的2010年11月7日的AR11120，ARDTM顺利检测为一个活动区，但采用文[4]方法将其检测成了两个活动区。

![](images/9186116938136834441a22f467a081b36021e13598e4e21b2be7ee0ae9f4c44e.jpg)  
Fig.3 The detection results images diagram of ARDTM

图4展示了D6数据集中连续三帧的跟踪结果(a)、(b)和(c)，时间分别是2014年10月20日22:48UT、21日23：00UT和22日22:48UT。图中粗框代表了检测到的太阳活动区匹配到了轨迹；虚框表示该区域未被检测或未被跟踪匹配，而采用预测机制填补的结果。跟踪框的左上角数字表示ARDTM对太阳活动区的跟踪编号。通过与对应时间的NOAA对比，ARDTM具有良好的跟踪结果。比如，（1)ARDTM及时捕获到了新的活动区。ARDTM在(a)及时捕获了AR12194，而NOAA在（c)才被标注，ARDTM比NOAA提前了2天。NOAA中AR12183、AR12186、AR12189、AR12190、AR12191、AR12192和AR12195这几个活动区，ARDTM均比NOAA更早检测到并及时开始跟踪。(2)ARDTM及时终止跟踪消失的活动区。ARDTM在22日（c)及时终止跟踪AR12189，而NOAA直到26日才终止跟踪该活动区。同样，(a)图的AR12186也是类似的情况。（3)预测机制较好地弥补了检测算法漏检带来的漏跟踪或误跟踪问题。ARDTM在(a)和(b)都通过预测机制连续跟踪了AR12189。(4)ARDTM检测并跟踪到了NOAA漏检的活动区。(a)图中编号为23和29的活动区和(b)中编号为33的活动区，在演化过程中都形成了黑子，生命期分别为8、6和6帧，但都未被NOAA标注。

![](images/56b6134b3a6fc23e46e9933ae1e2d45ce48d0e5253d6c72173304478d8ce630a.jpg)  
图3ARDTM的检测结果图。  
图4ARDTM在D6数据集中连续3帧的跟踪结果。（a)2014年10月20日22：48UT；（b)2014年10月21日23：00UT；（c）2014年10月22日22：48UT。  
Fig.4ARDTMtracking resultsof three consecutive frames in theD6dataset.(a)Oct.20,2014 22:48UT;(b)Oct.21, 201423:00UT；(c)0ct.22，2014 22:48UT.

图5展示了图4中AR12194以及D4数据集中AR09093两个活动区的完整跟踪结果。(a)到(1)子图是AR12194从出现到消失的跟踪过程，时间从2014年10月20日22:48:00UT到31日19:48:00UT。该活动区穿越了整个日面，磁场结构和面积变化都非常大。(n)到(t)子图是AR09093从出现到消失的跟踪结果，时间从2000年7月16日12:48:00UT到22日

12:48:00UT。(m)和(u)是AR09093 产生的前一帧和消失的后一帧对应位置图。该活动区演化周期时间较短，特征变化也很大。ARDTM及时捕获且及时停止了跟踪该活动区。其中，（t)时刻通过预测机制填补了漏检，(u)时刻及时停止了跟踪。图6显示了图5中AR09093 和AR12194两个活动区的磁通量和面积的变化曲线(均已进行了投影改正)，可以看出其磁通量和面积都具有较强的渐变性。

![](images/b44e682dc5980434bcef59d5b04302645b96d41db178da47e3f37553abc3e152.jpg)  
图5(a)到(k)是D6数据集中AR12194完整的跟踪结果。(n)到(t)是 D4数据集中AR09093完整的跟踪结果

![](images/6f31239526f8d3ae7c281214ba340886b24032ec877699dc3aa960aa714a238d.jpg)  
Fig.5From(a)to(k)is thecomplete tracking resultof the number ARl2194inD6 dataset.From(n）to(t）is the complete tracking result of the number AR09093 in D4 dataset.   
图6 (a)图5中AR12194磁通量变化；(b)图5中AR09093 磁通量变化  
Fig.6(a) Thechange of magnetic flux of the ARl2194；(b)Thechange of magnetic flux of the AR09093

# 4总结与展望

本文基于深度学习提出了一种太阳活动区检测与跟踪的方法ARDTM。该方法首先使用YOLOv3-spp 网络检测太阳活动区，然后结合较差自转改进 DeepSort 算法跟踪太阳活动区。经过网络训练后，本文分别用四组数据进行了测试，并与NOAA 的结果进行了比较，ARDTM跟踪标注的结果与NOAA的交集约为NOAA的 $9 2 \%$ 。

本文的训练集只采用了HMI数据，但无论是测试HMI的数据，还是MDI的数据，都能很好地检测和跟踪太阳活动区，表现出了较好的泛化性。为了与SolarMonitor的结果进行逐一比较，本文主要采用与 SolarMonitor 网站公布的数据时间基本吻合的数据进行了测试，时间间隔约为24小时。本文还对不同时间间隔的HMI序列图像进行了测试，时间间隔选取为12 分钟、1小时、4小时…，一直到 48小时。总体来说，间隔为12分钟的数据由于活动区特征变化不大，跟踪结果最好；一直到24小时的时间间隔跟踪效果都还不错；超过 24小时的时间间隔就会出现较多的误跟踪现象。总的来说，该方法较好地解决了传统方法中一个太阳活动区被误检测为多个，或者多个相邻的太阳活动区被误检测为一个的问题。而且，该方法能及时捕获到新出现的活动区，亦能及时终止跟踪消失的活动区，并且通过预测机制弥补检测算法漏检带来的误跟踪或漏跟踪问题。当然，该方法也还存在一定的问题，比如由于单一地根据磁场结构的特征检测和跟踪活动区，会导致一些具有磁场结构但未形成黑子的特征被误跟踪情况。在未来的工作中，拟考虑结合其他波段观测的图像进一步提高算法的准确率。

# 参考文献：

[1] QAHWAJIR,COLAKT.Automatic detectionand verificationof solar features[J].InternationalJournalofImagingSystems & Technology,2005,15(4):199-210.   
[2] ZHANGJ,WANGY,LIUY.Statistical propertiesofsolaractiveregionsobtained fromanautomaticdetectiosystemandthe computational biases [J]. The Astrophysical Journal,201o,723(2):1006-1018.   
[3] CABALLERO C, ARANDA MC. Automatic tracking of active regions and detection of solar flares in solar EUV images [J]. Solar Physics,2014,289(5):1643-1661.   
[4] HIGGINS PA,GALLAGHERPT,MCATEERRTJ,etal.Solar magnetic feature detection andtracking for space weather monitoring [J].Advances in Space Research,2011,47(12):2105-2117.   
[5] TURMON M,PAPJM,MUKHTAR S.Statistical patern recognition forlabeling solar active regions: application toSOHO, MDI imagery [J]. The Astrophysical Journal, 2002,568(1):396-407.   
[6] ZHARKOVA VV,ABOUDARHAMJ,ZHARKOV S,et al. Solar feature catalogues inEGSO[J].Solar Physics,2005,228, 361-375.   
[7] MCATEER RTJ, GALLAGHERPT,IRELANDJ,etal. Automated boundary-extractionand region-growing techniques applied to solar magnetograms [J]. Solar Physics,2005,228(1-2):55-66.   
[8] COLAKT,QAHWAJIR.Automated mcIntosh-based classificationof sunspot groups usingMDIimages[J].SolarPhysics,2008, 248(2):277-296.   
[9] COLAK T, QAHWAJIR. Automated solar activity prediction: a hybrid computer platform using machine learning and solar imaging forautomatedpredictionofsolarflares[J].SpaceWeather-theInternationalJouralofResearch &Applicatios,2009, 7(6):-.   
[10]LABONTEBJ,GEORGOULIS MK,RUSTDM.Surveyof magnetic helicityinjectioninregions producing X-clas flares[J]. Astrophysical Journal,2008,671(1):955.   
[11]GALLAGHERPT,MOONYJ, WANGH. Active-region monitoring andflare forecasting-1.Data processng andfirstresults [J]. Solar Physics,2002,209(1):171-183.   
[12]LECUN Y,BENGIO Y,HINTON G.Deep learning [J]. Nature，2015，521: 436-444.   
[13] GIRSHICK R,DONAHUEJ,DARRELLANDT,etal. Rich feature hierarchies forobjectdetectionandsemantic segmentation [C]// 2014 IEEE Conference on Computer Vision and Pattern Recognition. IEEE,2014.   
[14]REN S,HEK,GRSHICKR,etal.FasterR-CNN:towardsreal-timeobjectdetectionwithregionproposalnetworks[J].EEE Transactions on Pattern Analysis & Machine Intelligence,2015,39(6):1137-1149.   
[15]REDMONJ,DIVVALA S,GIRSHICKR,et al.You only look once: unified,real-time object detection[J].2015.   
[16]REDMON J,FARHADI A. YOLOv3: an incremental improvement [J]. 2018.   
[17]WOJKEN,BEWLEYA,PAULUSD.Simpleonlineandrealtime tracking withadepassociationmetric[C].IEEEInteation Conference on Image Processing. IEEE,2017:3645-3649.   
[18]SANCHEZ-MATILLAR,POIESIF,CAVALLAROA. Online multi-target tracking with strong and weak detections[M]/ Computer Vision- ECCV 2O16 Workshops.Springer International Publishing,2016.   
[19]CHU Q,OUYANG W,LIH,etal. Online multi-object racking using CNN-based single objecttracker with spatial-temporal attention mechanism [J].2017.   
[20]付小娜，廖成武，白先勇,et al.基于LeNet-5卷积神经网络的太阳黑子检测方法 [J].天文研究与技术,2018,v.15; No.59(03):87-93.   
[21] 刘辉，季凯帆，金振宇．机器学习在太阳物理中的应用[J].中国科学：物理学 力学 天文学,2019,49,109601.   
[22] 崔顺，许允飞，苏丽颖,etal.基于卷积神经网络的全天空地基云图分类研究[J].天文研究与技术,2019,16(02):98-108.   
[23]HE K,ZHANG X,RENS,etal.Spatialpyramid pooling ideepconvolutional networks forvisualrecognition[J].IEEE Transactions on Pattern Analysis & Machine Intelligence,2014,37(9):1904-16.   
[24]HOWARD R. The rotation of the sun [J]. Reviews of Geophysics,1978,16(4):721-732.   
[25]HOWARDRF,HARVEYJW,FORGACHS.Solarsurface velocityfields determined fromsmallmagneticfeatures[J].Solar Physics,1990,130(1-2):295-311.   
[26] KUHNH W.The hungarian method for the asignment problem [J]. Naval Research Logistics,1955,2(1-2):83-97.

# A Detection and Tracking Method for Active Regions Based on Deep Learning

Zhu Jian'， Yang Yunfei1²,Su Jiangtao²， Liu Haiyan', Li Xiaojie'， Liang Bo’, FengSong1

(1.SchoolofInformationEngineeringandAutomation/KeyLaboratoryof ApplicationsofComputerTechnologyof theYunnan

Province,Kunming University of Science and Technology,Kunming 65o5Oo,China;

2.Key Laboratory of Solar Activity，Chinese Academy of Sciences，Beijing 1OolO1，China)

Abstract: Active regions(ARs) are the primary source of energy for various solar activities. The violent solar activities adversely affect human living environment. Therefore, accurate detection and tracking of ARs are very important for monitoring and forecasting the space weather. In this paper,we propose an AR detection and tracking method （ARDTM） based on the deep learning model comprising of the YOLOv3-spp and DeepSort. This paper solves the problem that one AR is mis-detected as multiple ARs,or multiple ARs are mis-detected as an AR.Besides that, it captures the new ARs and terminates the disappeared ARs in time. The method improves the precision and recall of detecting and tracking ARs. It can be used for detecting and tracking ARs in the solar full-disk longitudinal magnetograms observed from different telescopes, or different time interval series-images.

Keywords: active regions; detection and tracking; deep learning; YOLOv3-spp; DeepSort