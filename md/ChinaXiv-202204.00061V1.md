# 一种基于沙漏网络的多层次协同搜索方法

陈桂荣，邱仲禹，粟涛，陈弟虎(中山大学 电子与信息工程学院，广州 510006)

摘要：目前，人工智能快速发展，人们可以通过探索硬件设计空间使优秀的神经网络算法高效部署在FPGA加速器。然而，由于参数量大、操作过于复杂而导致算法与硬件难以匹配，加速效率不高。为了算法和硬件二者匹配性更强，提出了一种多层次协同搜索的方法，采用 SPOS搜索策略并以检测准确率和延时为评估目标，搜索出最优神经网络架构、量化方式和硬件设计参数组合。该方法应用在姿态识别中具有优异性能的沙漏网络中，在获取候选子网络量化前、后的检测准确率的同时对硬件设计参数使用遍历搜索得到预估延时，根据目标函数获取最高得分的最优组合。为了保证获取的数据有效性，子网络需要进行重新训练、量化后重新推理得到检测准确率，获取硬件设计参数则利用基于 Spinal HDL 设计的加速器模板进行仿真测试得到测试延时。就平均而言，该方法比文献[1]减少了$8 3 . 3 \%$ 的参数，准确率只下降了0.69；比传统加速方法平均减少了 $3 3 . 2 \%$ 参数量，准确率只下降了0.46，网络推理的测试总延时减少 $2 2 . 1 \%$ ，在沙漏块的测试延时减少 $67 . 8 \%$ 。总体而言，该协同搜索方法对于沙漏网络的优化有一定效果，比传统加速设计方法更有优势。

关键词：神经网络；FPGA；协同搜索；沙漏网络；延时模型中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.01.0018

Multi-level co-exploration method based on hourglass network

Chen Guirong,Qiu Zhongyu, Su Tao†, Chen Dihu (SchoolofElectronics&Information Technology,Sun Yat-Sen University,Guangzhou 510oo6,China)

Abstract:Atpresent,withtherapiddevelopmentofAI,peoplecanefficientlydeployexcellentneuralnetworkalgorithmson FPGA accelerators by exploring the hardware design space.However,due to the large amount ofparametersand complex operation,itisdifcult tomatch thealgorithmwiththe hardware,andtheacelerationeficiencyislow.Inordertobeter match the algorithm and hardware,this paper proposed amulti-level co-exploration method,adopted SPOS search strategy, aimedat accuracyand latency,toobtaintheoptimal neural network architecture,quantization method and hardwaredesign combination.Itapplied the method to hourglass network which have high accuracy in pose estimation.While obtained the accuracy before and afterquantizationof candidate sub networks,it used traversal method to search hardware design parameters and obtain the estimated latency,and then gotthe optimalcombination with the highest score according to the target function.Inorder toensure the effectiveness oftheobtaineddata,itretrained the sub network,then quantified and inferencedagain toobtain the accuracy.It simulated theobtained hardware design parameters to gethe testing latency,using the accelerator template designed basedon Spinal HDL.On average, Co-exploration method reduced the parameters by $8 3 . 3 \%$ （204 and with only O.69 accuracy loss compared with the original structure; reduced the parameters by $3 3 . 2 \%$ ，with only 0.46 accuracy loss,reduced the total testing latency of network inference by $2 2 . 1 \%$ and reduced the testing latency in hourglass block by $67 . 8 \%$ compared with the traditional acceleration method. Overall, the co-exploration method in this paper has a certain effectontheoptimizationof hourglass network,andithas moreadvantages than thetraditionalacceleration method.

Key words: neural network;FPGA; co-exploration; hourglass network; latency model

# 0 引言

随着人工智能快速发展，姿态估计是计算机视觉领域的主要研究方向之一，在很多领域有着重要研究价值和应用前景。堆叠式沙漏网络1在二维姿态估计算法中，表现优异，目前很多算法都是基于沙漏网络的变体[2.3]。但是设计者的初衷更多是考虑其检测准确率，而该网络模型复杂、参数量大在边缘计算加速推理方面有很大的挑战。目前在边缘加速方面，大都是预先有算法网络结构，然后基于该固定结构进行加速推理，却缺乏对于算法、硬件等多方面协同设计的方法，因此存在高准确率算法却难以匹配到硬件进行加速推理的问题[4.5]，所以在加速计算方面仍有改进的空间。

在二维姿态识别领域中，存在很多较为优秀的算法[1,6\~9]。以 $\operatorname { P C K h } ( \varnothing 0 . 5$ 的值作为检测准确率衡量指标，文献[1]的沙漏网络检测准确率是90.9，但是其参数量有25.1M;文献[7]的SimpleBaselines准确率是91.5，虽然采用简单有效的结构，但是其参数量高达 $6 8 . 6 \mathrm { M }$ ；文献[8]的HRNet其检测准确率是92.3，但是其参数量也有28.5M之多，而且参数均为浮点数。这些优秀的算法无论是在整体网络的实现过程还是参数量，在边缘加速的实现过程都是巨大的挑战，难以匹配到硬件进行加速。

近年来，科研团队在神经网络算法、压缩量化、硬件设计等方面的性能提升作出很大的贡献。首先为了实现提高神经网络的性能这一目标，很多研究人员采用神经网络架构搜索[10\~13](neural network architecture search,NAS)这种先进的方法，从人工调参的繁琐工作中脱离出来。文献[11]提出了NASNet，设计一个新颖的搜索空间，并使用强化学习优化方法提高了搜索性能。文献[12]引入ENAS，利用权重参数共享方法提升了NAS的效率，GPU运算时间缩短了1000倍以上。文献[14]提出了One-Shot的方法，通过训练一个超网络作为辅助模型，整体搜索速度很快。其次，为了减少神经网络的参数，加快神经网络推理，不少科研人员在量化方面取得很好的进展[15]。文献[16]将网络权值二值化让计算主要在正1或负1间进行，降低了网络大小和计算量。文献[17]将推断过程中的浮点数运算量化为整数运算，最终将权重和激活函数量化为8位。文献[18采用混合精度量化方式以找到合适的量化位宽，实现降低能耗的目标。为了能更快的实现神经网络推理，在加速器硬件设计中有很多地方值得关注，如处理单元(Process element，PE)数目、并行度、数据流复用方式等等，目前设计人员在这些方面做了很多探索。文献[19]利用Roofline 模型对卷积神经网络(Convolution NeuralNetwork，CNN)加速器数据流技术的设计空间探索，探索不同数据流复用方式的性能。文献[20]在探索了PE的利用率和并行度，实现了性能的大幅度提升。文献[21]提出了一种加速器架构可以进行卷积层间流水，在输出特征图数、宽度和高度三个维度进行展开实现并行化计算的。然而这些工作都是从单一角度出发，例如从算法准确率、硬件参数量、硬件设计方法等单一优化，并未协同考虑进行共同优化，以便获取最优性能。

在多目标协同搜索和硬件感知搜索[4,5,18,22\~30]相关研究越来越多，设计者不仅考虑算法层面的准确率而且考虑很多硬件性能，如功耗、耗时、面积、资源利用等等。文献[4]考虑了层和数据流复用模式之间的适应性，选择最合适的数据流复用模式，高效部署所搜索的网络。文献[24]利用强化学习方法搜索，搜索空间包括算法架构、混合精度量化方式等，并建立延时模型和能耗约束，实现能耗和延时的下降。文献[29]定义了一个新的硬件搜索空间，在目标FPGA平台上生成具有延时保证的最优神经网络模型。文献[30]等提出了一种器件-电路-架构的协同探索框架，包括器件类型、电路拓扑结构和神经网络超参数等实现性能的优化。但是这些工作基本都是基于图像分类，而对于姿态识别、沙漏网络却缺乏该方面的研究工作。

综上所述，在姿态识别方面，优异的算法缺乏硬件的适配性；在网络优化、压缩、硬件加速方面却更多的考虑单一性能优化；在多目标优化的协同方法中缺乏对姿态识别方面的研究工作。而神经网络架构搜索方法可以自动探索神经网络的设计优化空间，设计者可以更进一步改变网络结构实现更高精度。与此同时，设计者还可以将其他硬件端的目标作为优化对象。这些方法很好的解决了高准确率算法与硬件难以匹配的问题，可以以很低的精度损失实现更简便的方式进行高速推理。

本文兼顾检测准确率和延时提出了一种面向姿态识别的沙漏网络多层次协同搜索方法，充分探索算法和硬件设计等方面的优化空间，主要的贡献有：针对沙漏网络的结构，提出了算法、压缩量化、硬件设计等方面的协同优化方法，以低准确率损失实现了性能较大的提升；.建立了一个接近加速器真实运行的延时模型进行分析指导协同搜索过程；为了对延时模型的准确性进行验证，利用SpinalHDL设计了加速器模板对获取的数据流、并行度硬件设计参数进行仿真测试。

# 1 多层次协同搜索方法

# 1.1问题定义

在传统的神经网络到硬件加速部署设计过程中，算法设计者关注网络模型的准确率，因此各种NAS工作的目标是寻找一个精度更高的网络结构，然而硬件设计师更多地关注加速器的性能，如延时、功耗等，所以很容易出现算法和硬件不匹配的问题。多层次协同方法旨在优化沙漏网络的推理延时，同时保证准确率损失最小。

准确率的获取需要候选模型对验证集进行推理，本文所有的准确率都是MPII数据集特定指标值PCKh $@ 0 . 5$ 。在利用MPII数据集评估时，通常利用关节点正确定位百分比(percentage ofcorrectkeypoints，PCK)评估人体关节点定位的准确率，通常记为PCK@k。当关键点i的预测位置与真实位置间的距离di小于头部长度Lhaed一定比例 $\mathbf { k }$ ，称为 $\operatorname { P C K h } ( \omega \mathbf { k }$ 计算公式如下。

$$
\mathrm { P C K h } = \frac { \displaystyle \sum _ { i } \delta \left( d _ { i } < k L _ { \mathrm { h e a d } } \right) \delta \left( v _ { i } > 0 \right) } { \displaystyle \sum _ { i } \delta \left( v _ { i } > 0 \right) }
$$

当 $\mathbf { k }$ 的值为0.5时，即表示为 $\operatorname { P C K h } ( \varnothing 0 . 5$ 0

而网络推理延时的获取是使用数学建模来预测，延时可以用以下式(2)来描述，延时模型后续会专门进行介绍。

$$
\mathrm { L _ { t o t a l } = L _ { c a l c } + L _ { o n - c h i p } + L _ { o f f - c h i p } }
$$

总延时 $\mathbf { L } _ { \mathrm { t o t a l } }$ 包括计算延时 $\mathbf { L } _ { \mathrm { c a l c } }$ ，片上数据移动延时$\mathbf { L } _ { \mathrm { o n - c h i p } }$ ，片外内存访问延时 $\mathrm { L _ { o f f - c h i p } }$ ：

为了更好评估搜索的网络模型和加速器的设计参数，本文提出一个目标函数，同时目标函数可以用于指导整个协同搜索过程，如式(3)所示

$$
\mathrm { S c o r e } = ( \alpha ^ { * } \mathrm { A c c } + \beta ^ { * } \mathrm { Q } _ { - } \mathrm { A c c } + \gamma ^ { * } \mathrm { L } _ { \mathrm { t o t a l } } )
$$

Acc,Q-Acc为候选模型量化前、量化后的准确率,二者主要是保证量化前后都有较好的准确率。这里准确率和延时进行归一化处理，保证 Score 在0-100 的范围。 $\alpha , \beta , \gamma$ 为比例因子，根据多次调参后获得合适的比例，本文采用的比例分别为0.4,0.4,0.2。

# 1.2方法概述

多层次协同搜索方法框架主要包含超网络训练、协同搜索和硬件部署等部分，如图1所示。SPOS[15](SinglePath OneShot)将超网络训练和搜索分开进行，搜索过程是采用遗传算法进行多次迭代。协同搜索方法的输入约束主要是在算法端的沙漏块的模型、中间压缩的量化方式以及加速器设计的数据流复用方式和并行度，其中并行度会以FPGA的综合实现结果的DSP数目反映出来。搜索的输出是目标函数的评估得出最优的网络模型、量化方式、加速器数据流和并行度参数。网络架构需要进行重新训练、量化、推理，以保证该网络结构的有效性和准确性。而加速器设计参数则会在加速器模板进行修改参数以获取RTL(Register transferlevel)代码，最终目标是在FPGA实现高速推理。

![](images/da6f0a1ed6355d5ae34faab08eadfd254f9027ad06a582d8bd18db29de03e64e.jpg)  
图1多层次协同搜索方法 Fig.1Multi-level co-exploration method

整个搜索过程的实现是先对超网络的沙漏块进行编码，方便使用遗传算法对沙漏块结构完成交叉、变异等遗传操作，再对超网络训练、量化，然后进行搜索；在搜索阶段，根据沙漏块的编码随机采样获得候选子网络作为初始种群，将量化前的候选子网络在验证集进行推理，同时将使用不同量化方式的子网络进行推理，获取量化前、后的准确率以便返回到目标函数进行评估，在候选子网络中最优的子网络会被遗传算法选取出来作为遗传的对象进行下一轮的迭代。在验证集验证的同时，硬件设计会采用遍历的方式进行搜索，将延时模型评估获得最低延时返回到目标函数同时获得相应的硬件设计参数。通过将量化前、后的准确率和预估延时，目标函数会获得相应的得分以便确保该子网络结构、量化方式、硬件设计参数均为最优。

由于超网络训练时采用权值共享的方式，子网络的准确率还有提升的空间，所以当获得了目标的网络模型，会对其结构进行重新训练、量化、验证等，以保证获取更好的准确率。获取的硬件设计参数，会调整加速器模板的参数，获取新的RTL代码之后进行综合、实现等后续过程。

# 2 多层次协同搜索空间定义

# 2.1算法层面

原始的沙漏块结构如图2所示，每一个小块都是残差块，残差块操作在硬件的实现较为复杂，并且沙漏块的每一条支路特征融合都需要额外的缓存，因此在支路的特征融合方面和特征提取的操作存在优化的空间。

![](images/d46fc94d1262327a8bc261e73fefc25995c500ae6e709f5d09020c1bdf1472ae.jpg)  
图2沙漏块的原始结构[1]

在支路的特征融合方面，本文的搜索空间有三种选择，第一种是无特征融合，即去除旁路分支，不保留以前的特征，第二种是无卷积的直接融合，即没有任何卷积开销的快捷方式，第三种是原来的卷积特征融合，如图3所示。无卷积特征融合比卷积特征融合减少很多的缓存、计算时间和额外的权重参数。无特征融合减少缓存时间最多。在操作算子块搜索空间方面，原来的残差块需要很多的计算和缓存时间，本文尝试用深度可分离卷积块替换以减少计算和缓存的开销。

为了方便对优异的沙漏块结构进行遗传，这里对沙漏块在加速器的计算顺序进行编码，融合方式分别是0,1,2，操作算子块分别是0,1，例如原始的卷积特征融合其对应为2，在原始的残差操作块编码为0，所以原始结构的编码为[2,0,2,0,2,0,2.0.0.0,0.0.0]，一共13个位置编码，而图3则表示[2,0,1,000,2,0,00,000]

![](images/8191d65dd767d06b4f7f7b6978fb1e5490cd49003dce18b513010ada94d44da9.jpg)  
Fig.2Original structure of hourglass block[1]   
图3.特征融合搜索空间  
Fig.3Search space of feature fusion

# 2.2 量化层面

在神经网络压缩方面，有量化、剪枝、稀疏化、蒸馏等方式，其中量化是最为常用的。因为神经网络每一层的数据分布都不一样，每一种量化方式有一定的差异，所以使用不同量化方式对不同的结构进行量化可能出现不同的结果。为了探索最好的量化方式，本文量化的探索空间是定点和整型。对于8位定点型量化，本文采用式(4)对整数位的位宽分别是1、2、3位进行探索，其中 $\mathrm { ~ m ~ }$ 表示有符号二进制补码，b表示小数位宽， $\mathrm { ~  ~ N ~ }$ 表示量化的总位宽。

$$
m = ( 1 / 2 ^ { b } ) \left[ - 2 ^ { N - 1 } x _ { N - 1 } + \sum _ { n = 0 } ^ { N - 2 } 2 ^ { n } x _ { n } \right]
$$

例如Fix8(2)表示整数位有2位，1位为符号位，其余的是小数位，如图4所示。

![](images/a10da2bb2f59605f026d6aba8b291c16d10e08badc8568a403814575736862a3.jpg)  
图4Fix8(2)的定点数表示  
Fig.4The fixed point representment ofFix8(2)

另一种方式是8位整型的方式进行探索，主要为如下式(5)(6)所示。

$$
f = S \left( q - Z \right)
$$

$$
q = { \mathrm { ~ r o u n d ~ } } \left( { \frac { f } { S } } + Z \right)
$$

其中：f为浮点数，S表示缩放系数， $\mathsf { q }$ 为量化后整数， $Z$ 表示零点。

# 2.3 硬件设计层面

CNN加速器设计需要根据FPGA的资源情况设计较为合理的数据流复用方式和并行度，因为数据流和并行度都会影响加速器性能，如果数据流不适合可能造成额外的延时开销，如果并行度过大可能资源不够，并行度过小造成资源浪费。

# 1）数据复用方式

数据流是指卷积计算的顺序，主要分为输出复用(OutputReuse,OR)、输入复用(InputReuse,IR)和权值复用(WeightReuse,WR)[20]，不同数据流在加速器表现为计算的顺序不同，每一种计算的顺序有不同的运行时间。因此，在加速器设计需要根据FPGA的资源情况确定其最优的数据流。其中输出复用伪代码如下算法1所示，相应的符号注解如表1所示。

表1部分符号解释  
Tab.1Explanation of Some notations   

<html><body><table><tr><td>符号</td><td>解释</td></tr><tr><td>Ic,Oc、Oh、Ow Tic,Toc、Tox、Toy、Kh,Kw Pic,Poc，Pox，Poy</td><td>输入通道，输出通道、长、宽 输入通道，输出通道、长、宽分块、卷积核长、宽 输入通道，输出通道、长、宽并行度、</td></tr><tr><td>x,y,m,n等 算法1： 输出数据流复用(OR)</td><td>循环变量</td></tr><tr><td>输出：OFM[Oc][Oh][Ow]</td><td>输入：IFM[Ic][iw][ih]，Weight[Ic][Oc][Kw][Kh]</td></tr><tr><td>1 for(y=0;y<Oh;y+=Toh){</td><td></td></tr><tr><td>2 for(x=0;x<Ow;x+=Tox){</td><td></td></tr><tr><td>3 for(m=0;m<Oc;m+=Toc){</td><td></td></tr><tr><td>4</td><td></td></tr><tr><td></td><td>for(n=0;n<Ic;n+=Tic){</td></tr><tr><td>5</td><td>//从 DDR 读数据</td></tr><tr><td>2)并行度</td><td></td></tr></table></body></html>

并行度是指在卷积计算时可以进行多少个并行的计算，即表示同时计算多少个乘法。并行计算的方式可以在不同的维度展开，例如卷积核、输入输出通道，特征图的长宽等等。在上述三种数据流下，Pic、Poc分别对应于输入和输出通道的并行计算，Pox、Poy 则表示卷积窗口的并行计算，即输出特征图的长、宽方向的特征点，不同的并行度组合也会表现出不一样的计算时间。

如图5所示，表示输入通道的并行计算，即在完成输出特征图的计算过程中，需要对卷积核与输入特征图对应通道相乘并累加后得到一个输出特征点，而该过程在FPGA上实现是利用多个乘法器并行计算完成的，因此并行度高其计算延时可能就少。其他维度的并行都是基于卷积计算的原理进行，这里不再赘述。

![](images/b01dbebcbdfed3c8d10920267e1579d5dfd50741e68b5c5486d61c4f5da5d690.jpg)  
图5输入通道并行计算

# 2.4多层次协同搜索空间

经过上面的分析，这里总结了本文多层次协同搜索的空间，如下表2所示。

表2多层次协同搜索空间  
Tab.2Search space of multi-level co-exploration   

<html><body><table><tr><td colspan="2">变量</td><td colspan="2">算法端搜索空间</td></tr><tr><td rowspan="2">算子块</td><td></td><td>量化方法搜索空间 硬件设计搜索空间</td><td></td></tr><tr><td>残差卷积块</td><td>Int8</td><td>数据流总并行度</td></tr><tr><td rowspan="4">支路融合操作</td><td>深度可分离卷积块</td><td>Fix8(1)</td><td>IR</td></tr><tr><td>无特征融合</td><td>Fix8(2)</td><td>OR <=1600</td></tr><tr><td>直接特征融合</td><td>Fix8(3)</td><td>WR</td></tr><tr><td>卷积特征融合</td><td>----</td><td>---</td></tr></table></body></html>

# 3 延时模型

为了准确的评估协同搜索的结果好坏，本文建立了一个接近加速器真实运行的延时模型，如上面式(2)。延时模型充分考虑了计算、片上和片外数据访问的时间成本，比简单地用网络模型参数和计算量估计延时更加准确和全面。在 $\mathbf { L } _ { \mathrm { c a l c } }$ 的建模中，本文考虑了由于PE利用而导致的实际计算性能低于峰值计算性能的问题；在$\mathbf { L } _ { \mathrm { o f f - c h i p } }$ 的建模中，充分考虑了不同数据流下的重复数据访问模式。该模型适用于描述具有不同资源约束、数据流和并行性的普通CNN加速器的延时估计。

# 3.1计算延时

计算延时表示计算整个网络所需要的时间，其中卷积占网络计算的 $90 \%$ 以上。计算延时可以表示为计算量除以总并行度和利用率的乘积，如式(7)所示，其中普通卷积的计算量如式(8)所示。PE的利用率可以表示为式(9)。

$$
\pmb { L } _ { \mathrm { c a l c } } = \frac { \sqrt [ 4 ] { \frac { \hbar } { 2 } } \pmb { \mathrm { i } } \pmb { \mathrm { E } } } { \pmb { \mathrm { \mathcal { H } } } \pmb { \mathrm { \mathcal { I } } } \pmb { \mathrm { \mathcal { I } } } \pmb { \mathrm { \mathcal { H } } } \times \mathbf { P E } \mp \mathbf { \underline { { I } } } \mathbf { \underline { { J } } } \mathbf { \overline { { H } } } \pmb { \mathrm { \mathcal { Z } } } }
$$

$$
\mathrm { L } _ { \mathrm { c a l c } } = \sum _ { \mathrm { l a y e r } } { \frac { O _ { w } \times O _ { h } \times I _ { c } \times O _ { c } \times K _ { w } \times K _ { w } } { P _ { o x } \times P _ { o y } \times P _ { i c } \times P _ { o c } \times P E _ { - } U t i l i t y } }
$$

$$
\mathrm { P E } _ { \mathrm { U } } \mathrm { t i l i t y } = \frac { P E \ \overleftrightarrow { \sharp } \rlap { / } \overleftrightarrow { \sharp } \overleftrightarrow { \sharp } \equiv \equiv \ } { \mathrm { P E } _ { \mathrm { c a s } } ^ { \sharp } \overleftrightarrow { \underline { { \dot { \tau } } } } \equiv \ } =
$$

$$
\frac { O _ { w } \times O _ { h } \times I _ { c } \times O _ { c } \times K _ { w } \times K _ { h } } { ( O _ { w } + O _ { w } \mathcal { Y } _ { 0 } P _ { o x } ) \times ( O _ { h } + O _ { h } \mathcal { Y } _ { 0 } P _ { o y } ) \times ( I _ { c } + I _ { c } \mathcal { Y } _ { 0 } P _ { i c } ) \times ( O _ { c } + O _ { c } \mathcal { Y } _ { 0 } P _ { o c } ) }
$$

# 3.2片上访存延时

片上访存延时是指在片上缓冲区与计算阵列之间的搬运时间，由于在本文的加速器设计中采用是流水线方式设计，片上数据搬运时间会隐藏在网络计算当中，所以 $\mathbf { L } _ { \mathrm { o n - c h i p } }$ 为零。

# 3.3 片外访存延时

片外访存延时表示从DDR到片上缓存的读和写数据的时间，更具体是某种数据流下的总数据量 $\mathbf { M } ^ { \mathrm { d t f l w } }$ 乘以位宽DW除以总线带宽BW，如式(10)所示。由于FPGA的片上容量有限，单层的数据可能超过片上缓冲区的大小，因此数据应该被分割成更小的块进行缓冲。在不同的数据流下，首先重用某种类型的数据，而其他类型的数据分块需要重复读取或写。所以每一种数据流都有不一样的访存数量。

$$
\begin{array} { l } { { \displaystyle { \mathrm { \cal { L } } _ { \mathrm { o f f - c h i p } } } = \frac { { \cal { M } } ^ { d t f l w } \times { \cal { D } } W } { B W } = } \ ~ } \\ { { \displaystyle ~ \sum _ { \mathrm { l a y e r } } \frac { \left( { \cal { M } } _ { \mathrm { i f f } w } ^ { d t f l w } + { \cal { M } } _ { \mathrm { w g t } } ^ { d t f l w } + { \cal { M } } _ { \mathrm { o f m } } ^ { d t f l w } \right) \times { \cal { D } } W } { B W } } } \end{array}
$$

# 4 加速器设计

为了验证延时模型的准确性和整个多层次协同设计的有效性，本文采用SpinalHDL这种新颖的硬件描述语言去设计了硬件的 CNN 加速器模板。Spinal HDL 类似Verilog，采用硬件的思想，而不像高层次综合更多的考虑算法层面而忽略硬件设计的细节。由于在硬件端搜索加入了很多硬件参数，因此本文的CNN加速器模板实现了不同比特位、并行度参数化，从而可以使得整个模板可以通过不同的测试脚本用来测试不同的硬件参数组合。测试延时的获取是先获取对应子网络结构的配置指令，完成每一层的参数配置，再通过对加速器的控制模块状态机的读、写过程进行波形采样获取周期数。

整个加速器结构包含以下几部分：控制模块内部包含控制的状态机可以控制计算、读、写等过程，本文设计了不同的控制器来支持搜索空间中的不同数据流。访存模块是片内和片外访存的桥梁，可以将片上的数据写回DDR，将DDR数据送到片上缓存。片上缓存模块实现数据和权值的缓存，分为两个数据Buffer和一个权值Buffer。重排模块实现在缓存数据在输送到计算阵列之间的重新排布。计算阵列采用层间复用模式设计，每一层重复利用计算阵列，包含三个维度的并行(输入通道，卷积窗口和输出通道)以适配硬件端搜索的并行度设置，可以完成卷积、池化和矩阵相加等计算操作，如图6所示。

![](images/ed3d9c4eb442b1138db84555fd6144739413a2088ebdad973bfb7ebebb34086b.jpg)  
Fig.5The parallel computing of input channel   
图6加速器结构  
Fig.6The structure of accelerator

# 5 实验

# 5.1实验设置

本文的实验环境配置如下：Ubuntu16.04LST64位系统，PyTorch1.71深度学习框架,NVIDIAGTX1080tiGPU。本文采用的数据集是MPII数据集，包含25K张图像，采用PCKh $@ 0 . 5$ 评测指标。沙漏块堆叠数为1，采用RMS作为网络训练时的优化器，学习率是1e-3，超网络训练220轮，其中遗传算法搜索20 次。利用的FPGA平台是XilinxZynq系列中的7z045作为资源约束。基于资源利用率过高会出现难以布线的情况的考虑，在搜索实验中，DSP限制设置为800个，片上缓冲区总大小设置为1.312MB，两个数据Buffer为512KB，权值Buffer为288KB。

# 5.2实验结果

a)传统加速方法。传统加速方法是基于固定算法结构，来考虑硬件设计的加速方法，因此本文针对原始沙漏网络结构进行数据流、并行度硬件参数和量化方式进行设计搜索。

图7是并行度与延时的关系，可以知道在相同数据流下，总并行度为1536的情况下延时最低，而并非在最大并行度1600的情况下，延时最低。这也体现出搜索的意义所在，并非并行度越高，其延时就越低，需要与具体卷积计算的通道数等契合。图8是数据流与延时的关系，可以知道在相同并行度下，针对于沙漏网络输出复用(OR)方式具有较低的延时。表3为不同量化方式的关键点检测结果，可以知道各种量化方式的每个关键点的检测结果，采用不同量化方式对原始沙漏网络结构量化后各个关节点的检测准确率有所下降，其中Int8损失最少，仅为0.2。由于脚踝是比较容易被遮挡的部分，脚踝的检测效果最差，量化后其检测准确率下降最多。

1.45 x107 Total Parallelism--Latency . Parallelism 1.4 ：   
1.25 1.2   
1.15 1350 1400 1450 1500 1550 1600 Total Parallelism

![](images/e1e9118d229155c3a067fdda670d735820828a066a1ada84b46d22197125ae61.jpg)  
图7总并行度与延时的关系  
Fig.7Relationship between total parallelism and latency   
图8数据流与延时的关系  
Fig.8Relationship between dataflow and latency

表3不同量化方式的关键点检测结果  
Tab.3Key point estimation results of different quantization methods   

<html><body><table><tr><td>方法</td><td>头</td><td>肩</td><td>手肘</td><td>手腕</td><td>臀部</td><td>膝盖</td><td>脚踝</td><td>平均</td></tr><tr><td>None</td><td>95.3</td><td>94.0</td><td>85.6</td><td>80.6</td><td>84.9</td><td>78.8</td><td>74.2</td><td>84.92</td></tr><tr><td>Int8</td><td>95.5</td><td>94.0</td><td>85.4</td><td>80.1</td><td>84.9</td><td>78.1</td><td>73.9</td><td>84.69</td></tr><tr><td>Fix8(1)</td><td>95.4</td><td>93.5</td><td>84.3</td><td>78.2</td><td>84.7</td><td>76.8</td><td>71.4</td><td>83.61</td></tr><tr><td>Fix8(2)</td><td>93.6</td><td>90.1</td><td>81.0</td><td>74.3</td><td>79.9</td><td>71.6</td><td>65.1</td><td>79.62</td></tr><tr><td>Fix8(3)</td><td>80.9</td><td>70.0</td><td>45.7</td><td>44.3</td><td>54.9</td><td>35.7</td><td>28.9</td><td>51.62</td></tr></table></body></html>

针对沙漏网络原始结构搜索结果的前五名，如表 4所示，其中包括量化前、后的准确率、参数量以及数据流和并行度等。预测延时是指建立的延时模型获取的预测值，测试延时是指经过加速器模板仿真测试得到的延时，仿真测试主要是为了验证延时模型建模的正确性。经过多次重复测试得到，预测的时间延时和测试的时间延时平均误差只有 $4 . 0 2 \%$ ，足以表明延时模型的有效性。在表4可以知道，传统加速方法的搜索实验中，并行度组合为[Pox,Poy,Pic,Poc]=[8,3,8,8],数据流复用方式为输出复用OR，量化方式为Int8，延时最低，准确率损失最少，性能最优。

表4沙漏网络原始结构的搜索结果  
Tab.4Search results of the original structure of hourglass network   

<html><body><table><tr><td>排名</td><td>原始准确率</td><td>量化后准确率</td><td>量化方式</td><td>参数量/MB</td><td>复用方式</td><td>并行度组合</td><td>DSP数目/个</td><td>预测延时/周期数</td><td>测试延时/周期数</td></tr><tr><td>1st</td><td>84.92</td><td>84.69</td><td>Int8</td><td>3.40</td><td>OR</td><td>[8,3,8,8]</td><td>768</td><td>1.250*10^7</td><td>1.284*10^7</td></tr><tr><td>2nd</td><td>84.92</td><td>84.69</td><td>Int8</td><td>3.40</td><td>OR</td><td>[8,4,8,6]</td><td>768</td><td>1.256*10^7</td><td>1.290*10^7</td></tr><tr><td>3rd</td><td>84.92</td><td>84.69</td><td>Int8</td><td>3.40</td><td>OR</td><td>[6, 8,8,4]</td><td>768</td><td>1.257*10^7</td><td>1.291*10^7</td></tr><tr><td>4th</td><td>84.92</td><td>84.69</td><td>Int8</td><td>3.40</td><td>OR</td><td>[8, 8,4,6]</td><td>768</td><td>1.253*10^7</td><td>1.330*10^7</td></tr><tr><td>5th</td><td>84.92</td><td>84.69</td><td>Int8</td><td>3.40</td><td>OR</td><td>[8,12,4, 4]</td><td>768</td><td>1.281*10^7</td><td>1.359*10^7</td></tr></table></body></html>

# b）多层次协同搜索结果

针对沙漏模块重新构建了超网络进行训练，采用多层次协同搜索方法进行搜索，其搜索结果的前五名如下表5所示，表中包含沙漏块编码的网络结构、量化前、后的准确率、参数量、测试延时等。可以看到，最优的沙漏块结构为[0,1,1,0,1,1,2,0,1,0.0,1,0]，其量化后的准确率为84.10，参数量为2.23MB。由于在量化方式、数据流、并行度的搜索方面与传统方法一样采用遍历的方式进行，所以在这些参数的搜索基本一致。就平均而言，多层次搜索方法的原始准确率为84.29，量化后准确率也有84.23，损失很小，并且参数只有2.27MB。至于测试延时的对比，会在后面进行。

# c）实验结果对比

由于本文工作是基于沙漏网络进行优化的，因此最直接的性能对比是针对原始结构，即文献[1]中的堆叠块为1时的结果以及传统针对原始结构的加速方法进行比较，如表6所示。

表6中的传统方法最优和平均分别是指表4的传统加速方法最优结果和前五名的平均结果，协同搜索最优和平均是指表5中的最优结果和前五名平均结果。就平均而言，本文方法比文献[1]堆叠块为1的结果减少了 $8 3 . 3 \%$ 的参数，准确率只下降了0.69；比传统加速方法平均减少了 $3 3 . 3 \%$ 参数量，准确率只下降了0.46，网络推理的测试总延时下降 $2 2 . 1 \%$ 在沙漏块的测试延时下降了 $67 . 8 \%$ 。与其他姿态识别算法相比，本文的参数量是文献[7]的 $0 . 8 3 \%$ ，是文献[8]的 $2 \%$ ，是文献[9]的 $0 . 9 \% _ { \odot }$ 。本文工作在准确率方面可能与优秀的算法存在一定的差距，但是在参数量和网络结构复杂度方面有一定的优势，更能适配到FPGA进行加速推理。

综上所述，本文的协同搜索方法在减少运行延时方面以很低的准确率损失，表现出比较好的性能。总体而言，多层次协同搜索比传统的设计过程具有更好的加速效果。

表5多层次协同搜索结果  
Tab.5Search results of multi-level co-exploration   
表6实验结果对比  

<html><body><table><tr><td>网络结构排名</td><td>原始准确率</td><td>量化后准确率</td><td>量化方式</td><td>复用方式</td><td>并行度组合</td><td>参数量/MB</td><td>整个网络延时/周期数 沙漏模块延时/周期数</td><td></td></tr><tr><td>[0,1,1,0,1,1,2,0,1,0,0,1,0]</td><td>84.21</td><td>84.10</td><td>Int8</td><td>OR</td><td>[8,3,8,8]</td><td>2.23</td><td>1.009*10^7</td><td>1.115*10^6</td></tr><tr><td>[0,0,1,0,1,0,2,0,1,1,0,0,0]</td><td>84.87</td><td>84.85</td><td>Int8</td><td>OR</td><td>[8,3,8,8]</td><td>2.50</td><td>1.050*10^7</td><td>1.541*10^6</td></tr><tr><td>[0,1,1,0,1,1,2,0,1,0,1,1,0]</td><td>83.96</td><td>83.92</td><td>Int8</td><td>OR</td><td>[8,3,8,8]</td><td>2.09</td><td>1.006*10^7</td><td>1.084*10^6</td></tr><tr><td>[0,0,1,1,0,0,2,1,0,0,0,1,0]</td><td>84.47</td><td>84.43</td><td>Int8</td><td>OR</td><td>[8,3,8,8]</td><td>2.37</td><td>1.036*10^7</td><td>1.385*10^6</td></tr><tr><td>[0,1,1,0,1,1,2,0,1,1,0,1,0]</td><td>83.92</td><td>83.87</td><td>Int8</td><td>OR</td><td>[8,3,8,8]</td><td>2.09</td><td>1.006*10^7</td><td>1.089*10^6</td></tr><tr><td>平均</td><td>84.29</td><td>84.23</td><td>Int8</td><td>OR</td><td>[8,3,8,8]</td><td>2.27</td><td>1.021*10^7</td><td>1.243*10^6</td></tr></table></body></html>

Tab.6Comparison of experimental results   

<html><body><table><tr><td>比较对象</td><td></td><td></td><td></td><td>参数量/MB 准确率 总延时/周期 沙漏块延时/周期</td></tr><tr><td>文献[1]</td><td>13.60</td><td>84.92</td><td>----</td><td></td></tr><tr><td>传统方法最优</td><td>3.40</td><td>84.69</td><td>1.250*10^7</td><td>3.868*10^6</td></tr><tr><td>传统方法平均</td><td>3.40</td><td>84.69</td><td>1.311*10^7</td><td>4.046*10^6</td></tr><tr><td>协同搜索最优</td><td>2.23</td><td>84.10</td><td>1.009*10^7</td><td>1.115*10^6</td></tr><tr><td>协同搜索平均</td><td>2.27</td><td>84.23</td><td>1.021*10^7</td><td>1.243*10^6</td></tr></table></body></html>

# 6 结束语

本文针对姿态识别的沙漏网络，将沙漏块的结构、量化方式和硬件设计结合，以运行延时和准确率作为目标，建立了一个接近FPGA加速器真实运行的延时模型，提出了多层次协同搜索的方法，并经过设计的可配置的加速器模板验证其有效性。最终结果显示，这种协同设计方法在参数量和延时方面都优于传统的设计方法，并且只有很少的准确率下降。该方法对解决沙漏网络算法和硬件不匹配的问题有一定效果

当然该工作仍有改进空间，例如考虑不同沙漏块的数目，卷积通道数等等，可以加入到搜索空间获取更高准确率的网络的同时保持更低的延时。

# 参考文献：

[1]NewellA,Yang K,Deng,J.Stacked hourglass networks for human pose estimation [C]// Proceedings of the 14th European Conference on Computer Vision, Springer,2016: 483-499   
[2]周燕，刘紫琴，曾凡智，等．深度学习的二维人体姿态估计综述[J]. 计算机科学与探索,2021,15 (4):641-657(Zhou Yan,Liu Ziqin,Zeng Fanzhi,et al. Overview of 2D human pose estimation based on deep learning [J] Computer science and exploration,2021,15 (4): 641-657)   
[3]刘勇，李杰，张建林，等．基于深度学习的二维人体姿态估计研究进 展[J].计算机工程,2021,47(3):1-16.(Liu Yong,LiJie,Zhang Jianlin, et al.Research progress of 2D human pose estimation based on deep learning [J] Computer Engineering,2021,47 (3):1-16.)   
[4]Li Chuxi,Fan Xiaoya,Zhang Shengbing,et al.Hardware-Aware NAS Framework with Layer Adaptive Scheduling on Embedded System [C]/ ASPDAC'21: 26th Asia and South Pacific Design Automation Conference.2021.   
[5]Zhen Dong,Gao Yizhao,Huang Qijing,et al. HAO:Hardware-aware neural Architecture Optimization for Efficient Inference [J].2021.   
[6]Wei SE,Ramakrishna V,Kanade T,et al.Convolutional Pose Machines [J].IEEE,2016.   
[7]Xiao Bin,Wu Haiping,Wei Yichen. Simple Baselines for Human Pose Estimation and Tracking[J].arXiv e-prints,2018.   
[8]Sun Ke,Xiao Bin,Liu Dong,et al.Deep High-Resolution Representation Learning for Human Pose Estimation [J].arXiv e-prints,2019.   
[9]Zhang Feng,Zhu Xiatian，Dai Hanbin,et al.Distribution-Aware Coordinate Representation for Human Pose Estimation [J].2019.   
[10l Baker B.Gunta O.Naik N.et al.Designing Neural Network Architectures using Reinforcement Learning [J]. 2016.   
[11] Zoph B，Vasudevan V,Shlens J，et al.Learning Transferable Architectures for Scalable Image Recognition [J].2017.   
[12] Pham H, Guan MY, Zoph B,et al. Eficient Neural Architecture Search via Parameter Sharing [J].2018.   
[13] Cai Han，Yang Jiacheng，Han Song，et al.Path-Level Network Transformation for Efficient Architecture Search.In ICML,2018.3   
[14] Brock A,Lim T,Ritchie J M,et al. SMASH:One-Shot Model Architecture Search through HyperNetworks [J].2017.   
[15] Guo Zichao,Zhang Xiangyu,Mu Haoyuan,et al. Single Path One-Shot Neural Architecture Search with Uniform Sampling [J].2019.   
[16] Courbariaux M, Hubara I, Soudry D,et al. Binarized Neural Networks: Training Deep Neural Networks with Weights and Activations Constrained to+1 or-1[J].2016.   
[17] Jacob B,Kligys S,Chen B,et al. Quantization and Training of Neural Networks for Efficient Integer-Arithmetic-Only Inference [J].2017.   
[18] Wang Kuan,Liu Zhijian,Lin Yujun,et al.HAQ:Hardware-Aware Automated Quantization With Mixed Precision [C]//2019 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR).IEEE, 2020.   
[19] Chan P,Park S,Park C S.Roofline-Model-Based Design Space Exploration for Dataflow Techniques of CNN Accelerators [J]. IEEE Access,2020,8: 172509-172523.   
[20] Chen Y H,Krishna T,Emer JS,et al.Eyeris:An Energy-Efficient Reconfigurable Accelerator for Deep Convolutional Neural Networks [J]. IEEE Journalof Solid-State Circuits,2017,52(1):127-138.   
[21] Chen YH, Yang TJ,Emer J,et al.Eyeriss v2: AFlexible Accelerator for Emerging Deep Neural Networks on Mobile Devices [J].IEEE Journal on Emerging and Selected Topics in Circuits and Systems,vol. 9, no. 2, pp.292-308,June 2019   
[22] Ma Yufei, Cao Yu,Vrudhula S,et al. Optimizing the Convolution Operation to Accelerate Deep Neural Networks on FPGA,in IEEE Transactions on Very Large Scale Integration(VLSI) Systems,vol.26, no.7,pp.1354-1367,July 2018   
[23] Sharma H,Park J,Suda N,et al. Bit Fusion:Bit-Level Dynamically Composable Architecture for Accelerating Deep Neural Networks [J]. 2017.   
[24] Gong Chengyue,Jiang Zixuan,Wang Dilin,et al.Mixed Precision Neural Architecture Search for Energy Efficient Deep Learning [C]// ICCAD 2019. pp. 1-7   
[25] Jiang Weiwen,Li Yang，Sha H M,et al.Hardware/Software CoExploration of Neural Architectures [J]. IEEE Transactionson Computer-Aided Design of Integrated Circuits and Systems,2020, PP (99): 1-1.   
[26] Luo Xiangzhong,Liu Di,Huai Shuo,et al.HSCoNAS:HardwareSoftware Co-Design of Efficient DNNs via Neural Architecture Search [J].In DATE,2021.   
[27] Jiang Yuhang,Wang Xin, Zhu Wenwu. Hardware-Aware Transformable Architecture Search with Efficient Search Space [C]//2O20 IEEE International Conference on Multimedia and Expo (ICME).IEEE,2020.   
[28] Qiu Zhongyu,Li Jianli,Liang Dongbao,et al.A CNN/FPGA CoExploration Method Based on Hourglass Network.[C]//2021 IEEE 4th International Conference on Electronics Technology (ICET),2021,pp. 333-337   
[29] Jiang Weiwen,Zhang Xinyi, Sha HM,et al.Accuracy Vs.Efficiency:

Achieving Both through FPGA-Implementation Aware Neural Architecture Search.[C]// 2019 56th ACM/IEEE Design Automation Conference (DAC),2019,pp.1-6. [30] Jiang Weiwen，Lou Qiuwen，Yan Zheyu，et al.Device-CircuitArchitectureCo-Exploration for Computing-in-MemoryNeural Accelerators [J].IEEE Transactions on Computers,2020,PP (99):1-1.