# 基于GPU异构平台的实时CT图像重建系统的研究

夏松竹1，杨静1，方宝辉1，徐金秀²(1.哈尔滨工程大学 计算机科学与技术学院,哈尔滨 150000;2.江南计算技术研究所,江苏 无锡 214083)

摘要：针对采用单CPUCT图像重建时间长，采用CPU集群重建成本及能耗高的问题，提出了CPU多线程+GPU的异构重建模型。这种模型采用CPU 多线程流水线模式，将整个任务分解为若干个处理阶段，相邻的两个阶段之间以循环缓存连接，上一阶段完成一次计算任务后将数据放到循环缓存里，然后继续下一次的计算任务，下一阶段探测到循环缓存里有数据后，从缓存里取出数据开始计算。各个任务是并行处理任务的，针对某一耗时瓶颈模块再采用GPU并行加速，充分发挥CPU和GPU的计算资源。CPU多线程 $\cdot ^ { + }$ GPU模型相对于CPU多线程模型加速16.45倍，相对于串行CT图像重建加速20.5倍以上。将CPU多线程 $. +$ GPU模型重建的图像与CPU串行程序重建的CT图像相比较，数据结果在误差范围内，满足实验设计要求。提出的图像重建模型采用成本较低的GPU 显卡就实现了性能大幅提升，大大降低了CT图像重建系统的成本及功耗，而成本及功耗的降低会引起CT医疗诊断费用的降低，最终惠及广大病患。

关键词：GPU；CT图像重建；流水线 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.12.0859

# Research on real-time computed tomographic reconstruction system based on GPU heterogeneous platform

Xia Songzhul†, Yang Jing1, Fang Baohui1, Xu Jinxiu² (1.Collegeofomputerience&echnlogy,HrbinEngineeing University,Harbin5o,China;2.Jangnanite of Computing Technology,Wuxi Jiangsu 214083, China)

Abstract: In order to solve long time consuming problems of single CPU computed tomographic reconstruction and the problems of high cost and high energy consumption in the reconstruction using CPU cluster,this paper proposed a heterogeneous reconstruction model of CPU multithreads $^ +$ GPU .This model used the CPU multithread pipelining pattern, it dividedte whole taskinto several stages,and itconnectedeach twoadjacentphases byaloopbuer.Once thecalculation ofthecurrentask stagecompletes,thedatawouldbeputinto theloopbuffer,and thenthenextcomputing task wouldcontinue to execute.Whenthe data intheloop buffers was detectedbythe laterstage,the data wouldberemovedfromtheloop bffrs andcalculated.Inthiswayeachthread processs tasks inaparallelway.Foratimeconsumingbotleneck module,theparallel aceleration of GPU was adopted to give fullplayto the computing resources ofCPU and GPU.The CPU multithreads $+ \mathbf { G P U }$ （204号 model is16.45 times fasterthan the CPU multithreaded model,andaccelerates morethan 20.5times fasterthanserial CT image reconstruction.Bycomparing with experimentalresultsofCPU serial program,theresult of the CPU multithreads $^ +$ GPU model can meet the experimental design requirementin the range of eror tolerance.The image reconstruction model proposed byusing low cost GPU has greatly enhanced performance,greatly reduces thecost and power consumption of the CTsystem.Thereduction incostand powerconsumption willeadtoa reduction in thecostofCTmedical diagnosis,which will eventually benefit patients.

Key words:GPU; CT image reconstruction; pipeline

# 0 引言

CT（computedtomography）是指计算机断层重建技术，现在已经是医学诊断不可或缺的一种手段[I]。CT图像重建具有计算量大、计算密集、高可并行等特点，医疗诊断对CT图像的成像速度有较高的要求。现在加速CT图像重建的主要有两种方法，一是减少图像重建过程中的浮点计算量，二是并行处理图像重建过程。前者是通过巧妙设计优化现有算法；后者利用高性能计算平台，提升运算速度[2]。GPU具有计算核心多、计算能力强，被越来越多的应用在图形处理之外的通用计算[3]。GPU在通用计算的普及可以使个人计算机获得大规模集群才能提供的计算能力，而且GPU具有成本低、功耗小的优势，可以大幅减少CT成本。本文的整体软件框架采用多线程流水线模式，将整个任务分解为若干个处理阶段，各个任务是并行的，充分利用CPU 资源，然后针对耗时长的瓶颈模块，再采用GPU进一步加速。

# 1 CT原理

根据朗伯定律,一单色X 线束通过一密度均匀原子序数均匀的小物体时，其能量因与物质的原子相互作用而减弱[4.5],减弱的程度可用下式表达：

$$
\mathrm { I } = I _ { 0 } e ^ { - u d }
$$

其中： $I _ { 0 }$ 为入射的X射线强度；I为穿过物体后的X射线强度；  
u 为物质对该波长的线性衰减系数； d 为穿过  
均匀密度物体的路径长度;  
e为自然对数底。

当高度准直的X射线束环绕人体某一部位作断面扫描时，其中一部分光子被人体组织吸收，X射线强度衰减，未被吸收的剩余光子穿透人体后，被检测器接收，然后经放大并转化为电子流，作为原始的模拟信号数据输入到计算机进行运算处理，重建生成图像，然后将重建图像传给显示设备显示，供医疗诊断用[]。

反投影过程是将滤波后的投影数据累加到输出图像中，通过不同角度下多次的叠加来实现反投影[]。反投影重建过程简介如下。

输入：

反投影重建输入参数如表1所示。

表1反投影重建输入参数  

<html><body><table><tr><td>Prodata</td><td>滤波后的投影数据</td></tr><tr><td>Rs</td><td>射线源到旋转中心的距离</td></tr><tr><td>Rd</td><td>探测器到射线焦点的距离</td></tr><tr><td>wd</td><td>沿着X方向的探测器宽度</td></tr><tr><td>cen_det</td><td>探测器中心位置</td></tr><tr><td>FOV</td><td>感兴趣区域尺寸</td></tr><tr><td>xo,yo</td><td>感兴趣区域中心相对于旋转中心的位置偏移</td></tr></table></body></html>

<html><body><table><tr><td>w,h</td><td>重建图像的宽度和高度</td></tr><tr><td>V,C</td><td>投影View数，以及View中的通道数</td></tr></table></body></html>

输出：

重建图像，尺寸为w\*h的数组，数组中各点的值代表了感兴趣区域内各点的CT值。实现反投影的过程其实是一个逆向的过程，首先是图像坐标下各个像素点与图像中心的相对坐标位置，如图1所示。需要注意的是，在图像坐标系中Y轴向下为正；可计算出图中点 $( x _ { p } , y _ { p } )$ 在该坐标系下与图像中心的相对位置，单位为像素。

![](images/fe513e9d9824b04618ca6913017af33e233f61f9052bdff06a2fee6cdde9d6e3.jpg)  
图1重建图像坐标系

此时的重建图像为投影坐标下的一个FOV（图2），可根据图像像素尺寸与FOV空间距离之间建立对应关系，将像素关系转为空间距离关系比例为scale。

![](images/b2746f4e58a5a4428cae896e64dd64525cd469850368689757e7440bfc050668.jpg)  
图2FOV中心及平行投影示意图

在投影坐标下，经过旋转中心的射线在探测器上的投影位置为cen_det。而FOV的中心与旋转中心存在位置的偏移，偏移量为 $( \mathbf { \boldsymbol { x } } _ { 0 } , \mathbf { \boldsymbol { y } } _ { 0 } )$ 。根据像素-距离对应关系以及中心偏移量，可以通过以下公式计算出像素中的各点与旋转中心在空间的相对距离。

$$
\mathrm { ( x , y ) = { s c a l e * } \left[ - ( c e n t e r X , c e n t e r Y ) \right] + ( x _ { 0 } , y _ { 0 } ) }
$$

得到了（x，y）之后，可以通过以下公式计算出该点在探测器上的投影与旋转中心投影cen_det的相对距离。

$$
\operatorname { t } ( \mathbf { x } , \mathbf { y } , \ \Theta \ ) = \operatorname { y } \cos \Theta - \mathbf { x } \sin \Theta
$$

由于在探测器上的投影位置 $\mathrm { c e n \_ d e t + t ( x , y , \ \theta ) }$ 未必是整数，需要根据其位置进行线性插值得到投影值；然后将投影值累加到图像中对应的像素，并乘上系数 $\pi / \mathrm { V }$ ；最后将投影值

转换为CT值，单位为HU。

$$
\mathrm { C T } = 1 0 0 0 * { \frac { \mu - \mu _ { H 2 0 } } { \mu _ { H 2 0 } } }
$$

# 2 实时CT系统实现

# 2.1 CT系统架构

如图3所示，CT系统的软件主要由三大部分组成，分别是扫描控制系统、用户接口、图像重建系统。扫描控制系统主要负责扫描床、机架的运动控制，用户接口是CT系统与用户交互的接口，图像重建系统负责对探测器采集的数据进行图像的重建。图像重建系统是本文的关注点，扫描控制系统和用户接口不作详述。

![](images/76332115070ff592b42b10ca8ed7c44fa137557f554d09f4ee2385ec470c38d9.jpg)

图3CT系统

# 2.2流水线图像重建系统

本文设计的CT系统图像重建系统采用的是CPU多线程加图像处理器（GPU）的异构混合加速模型。多线程采用的是多线程设计模式中的流水线模式，首先将CT图像重建任务划分为若干个处理阶段，上一个阶段任务的运算结果交给下一个阶段来继续处理，这样线程与线程之间是并行处理的，可以充分利用CPU的计算资源，进而提高整个图像重建系统的计算效率[1]。如图4 所示，本文图像重建系统包括原始数据读取（RawData）、校准(correction）、扇形束转为平行束(rebin)、滤波(filter)、反投影重建(BPR)、图像后处理(img)等模块。每个模块是一个线程，上一个模块的计算结果放到循环buffer中，下一个模块检测到循环buffer中有数据，则从buffer中读出数据进行运算。图5是图像重建流水线框图。同一行中的各个模块表示不同次图像重建的相同处理阶段，相同颜色表示同一条流水线的不同处理阶段，如后缀为数字标记为1淡蓝色模块RawDatal、correctionl、rebinl、filter1、BPR1、img1分别表示第一条流水线的读取、校准、扇形束转为平行束、滤波、反投影重建、图像后处理等阶段。

![](images/c79a3cc919e756f53de38a0cefa89e1edeeb513f5e30c30fd73f2011e31c73eb.jpg)  
图4图像重建系统  
图5图像重建流水线框图

<html><body><table><tr><td></td><td>Time t1</td><td>t2</td><td></td><td>t3</td><td>t4</td><td>t5</td><td>t6</td><td>t7</td><td>t8</td><td>t9</td><td>t10</td><td>t11</td></tr><tr><td>threadl</td><td>RawData1</td><td>RawData2</td><td>RawData3</td><td>RawData4</td><td>RawData5</td><td>RawData6</td><td></td><td></td><td></td><td></td><td></td><td>/</td></tr><tr><td>thread2</td><td></td><td>Correction1</td><td>Correction2</td><td>Correction3</td><td></td><td></td><td>Correction4 Correction5 Correction6</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>thread3</td><td></td><td></td><td>Rebin1</td><td>Rebin2</td><td>Rebin3</td><td>Rebin4</td><td>Rebin5</td><td>Rebin6</td><td></td><td></td><td></td><td></td></tr><tr><td>thread4</td><td></td><td></td><td></td><td>Filter1</td><td>Filter2</td><td>Filter3</td><td>Filter4</td><td>Filter5</td><td>Filter6</td><td></td><td></td><td></td></tr><tr><td>thread5</td><td></td><td></td><td></td><td></td><td>BPR1</td><td>BPR2</td><td>BPR3</td><td>BPR4</td><td>BPR5</td><td>BPR6</td><td></td><td></td></tr><tr><td>thread6</td><td></td><td></td><td></td><td></td><td></td><td>Img1</td><td>Img2</td><td>Img3</td><td>Img4</td><td>Img5</td><td>Img6</td><td></td></tr></table></body></html>

# 2.3 CUDA架构

CUDA(compute unified device architecture)是 Nvidia公司推出的专门应用于图像处理单元（GPU）进行通用计算的并行编程模型。简单地讲，CUDA是便于编程人员利用NvidiaGPU进行通用计算的并行开发环境，目前支持 $\mathrm { C / C ^ { + + } }$ 语言。在CUDA编程模型中，一个程序被分为host和device端。host端是在CPU上运行的，device端则是在被视为协处理器的GPU上运行[]。由于GPU 能够提供成百上千的计算核心，所以拥有极大的并行计算能力。

# 2.4GPU并行算法设计

通过软件耗时测试，rebin（扇形束转平行束）、filter（滤波）、BPR（反投影重建）这三个模块是整个图像重建软件的耗时瓶颈。因此，本文将这三个模块采用GPU进行CUDA并行，减少这三个模块的耗时，进而提升整个图像重建系统软件的运算速度。本文限于篇幅的原因，仅介绍最为核心反投影重建算法（BRP）GPU并行设计。反投影重建算法的本质是对经过断层平面的某像素点的所有射线投影值求和。整幅图像的重建是将所有角度下投影值累加[8\~10]。如下文反投影重建伪代码， $2 { \sim } 6$ 行计算探测器上各个像素点在某一旋转角度下的投影值；第1行进行调整旋转角度，计算该角度下各个像素点的投影值，然后累加到之前计算得到的相同像素点的投影值上。重复上述过程，直至所有旋转角度的投影值都累加完毕。本文图像域是 $5 1 2 * 5 1 2$ 个像素点。因此每幅图像的重建需要作views $* 5 1 2 * 5 1 2$ 次乘加操作。

反投影重建算法的伪代码：

1 for each view in sonogram domain   
2 for each row in image domain   
3 for each pixel of row   
4 Accumulate the projection value through this pixel   
5 end For   
6 end For

7 end For

反投影重建并行设计方案：

比较直观的任务划分方式是在投影域按view进行划分，首先为每个线程开辟一个像素矩阵空间，每个线程负责几view像素点的累加，再将各个线程像素矩阵按对应像素进行规约求和。这种方法存在线程之间有相关性，需要各个线程的同步操作以及规约时的锁操作，耗时相对较多。本文是在图像域进行任务划分（图6），1个网格Grid里开启6个线程块（Block），每个Block里面有512个线程，每个Block负责图像坐标系下85或86行数据的重建，每个线程负责图像域每行的一个像素点的重建；优势是线程间没有关联性，减少同步带来的开销，减少GPU存储空间的开辟。

![](images/b72a33fdcc68e4a0a34720004401525e916cdb53bbc8180c5bf187e72fac03fd.jpg)  
图6 并行任务划分

# 2.5优化方案

a）采用异步流并行。Rebin、filter、BPR这三个模块分别位于三个cuda 流上，可以实现流之间数据拷贝与内核（kernel）计算的重叠[12\~15]。

b)本文提出的流水线图像重建模型的各个模块之间是通过循环缓存连接。为了避免因为缓存过小造成某些节点运算堵塞和缓存过大造成存储资源浪费，本文通过反复实验来确定最佳的缓存大小。同时平衡各个节点的计算量，确保在优化后各个节点运算时间相当，避免某些节点过慢，成为整个运算流程的瓶颈，造成其前面的节点由于输出循环缓存满了而停滞工作，其后节点因输入循环缓存没有数据而停滞工作，进而影响到整个流水线的运算速度。

c）各个节点之间通过缓存连接，上一阶段完成一次计算任务后将数据放到循环缓存里，然后继续下一次的计算任务。下一阶段探测到循环缓存里有数据后，从缓存里取出数据开始计算，如果探测循环缓存里没有数据，则需要挂起线程，避免持续判断，造成CPU资源的极大浪费，需要适当调节线程的挂起时间，避免时间过长，造成本阶段任务的工时过长，影响整个任务的时间。通过实际测试，本文将各个节点探测不到数据后的挂起时间设置在200us，使得整个运算流程的耗时最短

d）GPU没有复杂的分支预测能力，同一warp中的thread必须执行相同的指令，如果warp中的线程进入不同的分支，那么同一时刻除了正在执行的分支，其余分支都被阻塞了，十分影响性能。因此，本文通过边界扩充（padding）去除for循环里面的用于判断图像重建范围的if判断语句。

e）由于Global memory 寻址时钟周期是 Share memory的 $2 0 { \sim } 3 0$ 倍，所以本文将Global memory 中的数据先拷贝到Shared memory 中[],然后再从 shared memory 中取数据进行运算。这样每个线程只需一次Global memory 寻址，128 次Shared memory 寻址。

f）Device 端初始化过程中开辟 static memory，避免重 建过程中反复开辟。

g）适当增加grid中的线程数目来提高GPU的Occupancy（占用率）。流水线中的各个节点对于GPU资源是共享关系，同时各个节点之间也是竞争关系。随着更多的节点将任务放到GPU 上运算，GPU 的Occupancy 将有很大提升。但由于各个节点分属不同的CPU线程，各个线程抢占式的将自己的任务offload到GPU上，而GPU上的寄存器、共享缓存等硬件资源有限，必将导致某些节点提交到GPU上的计算任务由于得不到硬件资源而等待，同时引起很大的调度开销。因此图像重建速度首先会随着更多的计算任务放到GPU上而有所提升，同时GPU 的Occupancy也会大幅增大，但到达某个临界点后，随着资源竞争大增大图像重建速度不会再提升，反而有下降，而GPU 的Occupancy 继续增加。因此，本文不将Occupancy 作为本文图像重建程序的唯一性能指标，盲目追求Occupancy 的增大。而是尽量平衡GPU与CPU的计算量，确保两者同时保持较高的占有率，如采用openmp加速CPU端的计算瓶颈。

# 3 实验结果及分析

测试平台如表2所示。

表2测试平台  

<html><body><table><tr><td>Host</td><td>Device</td></tr><tr><td>处理器：Intel() Xeon R）</td><td>芯片厂商 NVIDIA</td></tr><tr><td>CPU E5-2630 v4 @ 2.20 GHz</td><td>显卡芯片 GeForce GTX</td></tr><tr><td>OS Type：Linux 64位</td><td>1050 Ti</td></tr><tr><td rowspan="3">核数：物理核10，逻辑核20</td><td>显存类型GDDR5</td></tr><tr><td>显存容量 4096 MB 显存位</td></tr><tr><td>宽128 bit 流处</td></tr><tr><td></td><td>理单元768</td></tr></table></body></html>

采用上述实验平台进行扫描，扫描人体模型长度 $3 6 5 ~ \mathrm { \ m m }$ 重建层厚 $5 ~ \mathrm { m m }$ ，重建间隔1，得到780 幅 $5 1 2 * 5 1 2$ 像素的重建图像，如图7、8所示。从图中能清楚地辨识出人体器官，通过与串行程序结果数值相比，误差在可接受范围内。

CPU性能测试结果如表3、4所示。

A

![](images/8b8195ce2b2c1fb2ae8c3d1f3b5a682120f7ac7ab0061a2869f61cbda9ff8e3f.jpg)  
图7纵隔窗重建图像  
图8肺窗重建图像

表3CPU性能测试结果  

<html><body><table><tr><td colspan="2">CPU多线程</td></tr><tr><td>模块</td><td>运算次数 时间/s</td></tr><tr><td>Rebin 780</td><td>36. 0774</td></tr><tr><td>Filter 780</td><td>47. 1297</td></tr><tr><td>BPR 780</td><td>327. 098</td></tr><tr><td>总耗时</td><td>329s</td></tr></table></body></html>

表4GPU性能测试结果  

<html><body><table><tr><td colspan="3">CPU多线程+GPU</td></tr><tr><td>模块</td><td>运算次数</td><td>时间/s</td></tr><tr><td>Rebin</td><td>780</td><td>18.3326</td></tr><tr><td>Filter</td><td>780</td><td>17. 3781</td></tr><tr><td>BPR</td><td>780</td><td>13.6265</td></tr><tr><td>总耗时</td><td>20s</td><td></td></tr></table></body></html>

由表中可以看出，CPU多线程 $+ \mathrm { G P U }$ 比仅有CPU多线程，Rebin模块加速1.96倍，filter模块加速2.71倍，BPR加速

24倍，整个图像重建软件加速16.45倍，加速效果明显。本文加速效果是CPU多线程 $+ \mathrm { G P U }$ 异构模型与CPU多线程流水线模型耗时比较，而CPU多线程本身是一种并行结构，对软件有加速效果。如果图像重建系统软件是串行结构，那么软件整体耗时是各个模块耗时之和，以本文测试为例，串行图像重建耗时应该大于Rebin+Filter+BRP 耗时，即 410.3051s。因此CPU多线程+GPU异构模型相对于串行模型加速超过20.5倍。另外需要说明的是，本文所得的加速比是在CPU多线程流水线模型已经做了较好的优化的基础上比较得出的。

# 4 结束语

本文研究CPU多线程 $^ +$ GPU的混合异构CT图像重建实现方法，重建速度有明显提升。这种CPU多线程 $+ \mathbf { G P U }$ 异构软件模型能够同时发挥CPU和GPU的计算能力，相对于集群并行重建会大幅减少成本及功耗，而成本及功耗的降低将在市场竞争中表现为价格的优势，这种价格优势必将最终惠及广大病患。本文提出的CPU多线程流水线模式 $+ \mathbf { G P U }$ 的异构并行软件模型不依赖于特定的算法，因此对于其他应用的性能优化也有一定的借鉴经验。另外，该方法也有良好的硬件可扩展性，随着计算量的增加，可以扩展更多的GPU硬件资源，提高运算速率。

# 参考文献：

[1]杨英,张学军.X射线在医学诊断领域的应用机理[C]//首届X射线管学 术会议论文集.北京:北京真空电子技术研究所,2015:21-23.   
[2]Tang M,Zhao JY,Tong R F,et al.GPU accelerated convex hull computation [J].Computers & Graphics,2012,36 (5): 498-506.   
[3]丁科,谭营.GPU通用计算及其在计算智能领域的应用[J].智能系统学 报,2015,10(1): 1-11.   
[4]Hsieh J. Computed tomography:principles,design,artifacts,and recent advances [M].2nd.Washington USA: SPIE Press,2009:36-41.   
[5]Yu T,Wang R. Scene parsing using graph matching on street-view data [J]. Computer Vision and Image Understanding.2016,145:70-80.   
[6]孙万捷,高瞻,潘海燕,等.动态任务分配CUDA 线程束步进体绘制[J]. 计算机辅助设计与图形学学报，2016,28(10):1630-1638.   
[7] Dzmitry S.Real-Time 3D cone beam reconstruction [C]// Proc of IEEE Nuclear Science Symposium Conference Record. 2004: 3648-3652.   
[8] Zhao X. GPU-based 3D cone-beam CT image construction: application to micro CT [Cl// Proc of IEEE Nuclear Science Symposium Conference Record. 2007: 3922-3925.   
[9]Kachelrieβ M.Hyperfast parallel-beam backprojection [C]//Proc of IEEE Nuclear Science Symposium Conference Record.2006 [C] $\because$ 3111-3114.   
[10] Knaup M,Kachelriel M. Real-time cone-beam CT image reconstruction using a mercury's dual cell-based system (DCBS) and a sony's playstation 3 (PS3) cluster [C]//Proc of IEEE Nuclear Science Symposium Conference Record.2007:3926-3928.   
[11]孙涛,韩善清,汪家旺.PET//CT成像原理、优势及临床应用[J].中国医 学物理学杂志,2010,27(1):1581-1587.   
[12] 柳有权,刘学慧,吴恩华.基于GPU 带有复杂边界的三维实时流体模拟 [J].软件学报,2006,17(3):568-576.   
[13] NVIDIA. NVIDIA CUDA computeunified device architecture programming guide.1.O edn [R]. Santa Clara, CA: [s.n.],2007.   
[14] Seherl H,Keek B,Kowarsehik M,et al.Fast GPU-based CTreconstruction using the common unified device architecture (CUDA)[C]// Proc of IEEE Nuclear Science Symposium Conference. Honolulu, Hl: IEEE Press, 2007: 4464-4466.   
[15] Pratx G,Chinn G, Oleott D P,et al.Fast,accurate and shift-varying line projections for iterative reconstruction using the GPU [J]. IEEE Trans on Medical Imaging,2009,28: 435-445.   
[16] Smith B D. Image reconstruction from cone-beam projection: necessary and sufficient condition and reconstruction methods [J]. IEEE Trans on Medical Imaging,1985,4(1): 14-25.   
[17]Muller K,Xu F.Practical considerations for GPU-accelerated CT [C]// Proc of IEEE International Symposium on Biomedical Imaging: Macro to Nano. 2006: 1184-1187.