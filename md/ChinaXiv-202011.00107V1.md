# 基于多进程并行加速的太阳高分辨图像重建方法

邓涛，陈东²，代红兵¹，王新华²,3(1.云南大学 信息学院 云南 昆明 650504;2.中国科学院云南天文台 云南 昆明 650011;3.中国科学院大学 北京 100049)

摘要：目前太阳高分辨图像重建往往采用斑点干涉术和斑点掩模法重建目标的模和相位，由于分组分块数据量大，算法复杂等因素，难以满足实时重建的要求。为了能缓解数据处理的压力，在现有在单组分块数据CPU/GPU混合计算方法的基础上，提出通过多进程将多组分块数据分配到GPU上同时并行处理的方法。实验表明，基于多进程并行加速方法可提高CPU和GPU资源利用效率，使GPU能同时处理多组分块数据，可显著提升图像分块处理的速度，加速比达4.7左右，相关研究可为天文数据并行化处理提供借鉴参考。

关键词：多进程；并行计算；图像重建；斑点掩模法；斑点干涉法中图分类号： $\mathsf { P 1 8 2 . 2 + 1 }$ TP751.2 文献标识码：A

# 1引言

太阳是影响人类活动的最大一颗恒星，尤其是太阳活动对地球环境、气候和天气的影响[1]等。由于太阳光线在穿过地球大气层时受到大气湍流的影响会产生波前误差，使得光路发生偏转，观测的太阳图像出现不同程度的偏移、抖动、模糊等形态，导致地基式望远镜的观察图像质量下降[2。为了消除大气湍流对望远镜成像结果的影响，通常采用空间望远镜、自适应光学以及图像重建技术等方式获取太阳高分辨图像。

目前图像重建技术常用的算法主要有相位差法、多帧盲反卷积法、斑点干涉术、K-T 算法、斑点掩模法、简单位移叠加法、迭代位移叠加法以及选帧位移叠加法等。这些算法都是通过大量的短曝光图像重建出太阳高分辨图像，但往往因为处理的数据量很大、算法复杂导致无法达到实时重建的需求。

近年，国内外在太阳高分辨图像重建算法并行化研究方面做了很多工作，并获得一定的加速比。Denker等人在BBSO 基于双节点集群，提出一种帧选择和斑点掩模法的并行计算方法，采用多线程方法在57s内完成重建一张 $2 5 6 \times 2 5 6 \mathrm { p i x e l }$ 图像。FriedrichWöger[4]等人使用 ATST,利用改写于KISIP 的算法，采用GPU一次处理单组分块数据，实现4.2s 内重建 225个 $1 2 8 \times 1 2 8$ pixel 子块的相位。LiXuebao[5等人从NVST的TiO 通道中选取一组子块图像（ $1 0 0 \times 2 5 6 \times 2 5 6$ （204号pixel)。采用OpenMP方法实现了一组子块图像的并行化，重建单帧 $2 5 6 \times 2 5 6$ pixel 的子块图像,运行时间减少至 $2 . 7 \mathrm { s }$ ，获得2.5倍加速.郑艳芳[等人采用GPU的CUDA构架对光球TiO 通道中的一组子块（ $1 0 0 \times 2 5 6 \times 2 5 6$ pixel）实现并行化，基于CUDA方法重建单组子图像组的运行时间减少到大约 $0 . 7 \mathrm { s }$ 。宣经纬等人基于CUDA并行计算架构，在斑点掩模算法中实现单个子块GPU内的并行化，采用CUDA并行方法比纯CPU上运行的串行算法加速比达7。

综上所述，太阳高分辨图像重建在采用斑点掩模法下的图像并行化研究方面已经取得一定的研究成果，但大多还局限于单纯的CPU或GPU加速，而且GPU一次只能处理一组分块数据，CPU/GPU的并行化能力没有完全发挥出来。如何将多组分块数据分配到GPU上同时并行处理，进一步提高CPU 和GPU的并行计算能力和资源效率，本文提出了基于多进程并行加速太阳高分辨图像重建方法。

# 2太阳高分辨图像重建方法

一米新真空太阳望远镜(New Vacuum Solar Telescope,NVST)[8]坐落在抚仙湖畔，主要的观察波段有：G-band $( 4 3 0 5 \mathrm { \AA } )$ 、 $\mathrm { H a } ( 6 5 6 2 . 8 \AA )$ 、TiO(7058A)。NVST太阳高分辨图像重建使用了两个级别：Level1级别是采用位移叠加法来重建色球图像，Levell $^ +$ 则是采用斑点掩模法重建光球或色球图像。Levell $+$ 级别计算复杂度比Level1高，但Levell $+$ 级别在视宁度好得时候重建的图像质量更好、信噪比更高。

NVSTLevel1 $^ +$ 级别太阳高分辨图像重建流程：图像预处理，图像初对齐，视宁度估计，图像分块处理，子块拼接，其中图像分块处理主要采用斑点干涉术和斑点掩模法重建太阳高分辨图像的模和相位。图像分块处理包含若干处理环节，其中相位递推环节由于数据量大、计算复杂，并且需要考虑多个递推路径的整合，使得图像分块处理在Level1 $^ +$ 级别的重建流程中最为耗时，因此子块处理的好坏严重影响重建的效果和时效，其中最关键过程描述如下：

# 2.1振幅重建

在满足等晕区情况下，短曝光像是目标和系统的点扩展函数的卷积：

$$
\mathbf { i } \big ( x , y \big ) = o ( x , y ) \otimes p ( x , y )
$$

上式 $\otimes$ 为卷积符号，时域中的卷积对应于频域中的乘积。上式在频域中满足：

$$
I \left( u , \nu \right) { = } O ( u , \nu ) ^ { * } P ( u , \nu )
$$

其中 $I { \bigl ( } u , \nu { \bigr ) }$ ， $O ( u , \nu )$ ， $P ( u , \nu )$ 分别是时域中对应项的傅里叶变换功率谱统计为：

$$
\left. \left| I \left( u , \nu \right) \right| ^ { 2 } \right. = \left. \left| O ( u , \nu ) \right| ^ { 2 } \right. \ast \left. \left| P ( u , \nu ) \right| ^ { 2 } \right.
$$

其中 $\langle \rangle$ 为系综平均， $\left. \left| P ( u , \nu ) \right| ^ { 2 } \right.$ 就是 SITF.其中 SITF可以有两种方法得到：1.观测目标的近参考星多幅斑点图的平均功率谱建模计算得到 SITF。2.使用谱比法计算大气相干长度 $r _ { 0 }$ ，从而使用功率谱退卷积得到SITF。

# 2.2相位重建

目标斑点图的三重相关为：

$$
i ^ { ( 3 ) } ( x , \dot { x _ { \ O } } ) = \int i ( \dot { x _ { \ O } } ) i ( \dot { x _ { \ O } } , \dot { x _ { \ O } } ) i ( \dot { x _ { \ O } } , \dot { x _ { \ O } } ) d \dot { x _ { \ O } }
$$

目标斑点图的三重自相关的傅里叶变换有：

$$
I ^ { ( 3 ) } ( u , \nu ) = I ( u ) I ( \nu ) I ( - u , - \nu )
$$

其中 $\boldsymbol { I } ( \boldsymbol { u } )$ 是 $i ( x )$ 的傅里叶变换。 $u$ 和 $\nu$ 是二维空间频率。

目标斑点图的平均重谱有：

$$
\left. I ^ { ( 3 ) } ( u , \nu ) \right. { = } O ^ { ( 3 ) } ( u , \nu ) \Bigl \langle P ^ { ( 3 ) } ( u , \nu ) \Bigr \rangle
$$

其中， $\Leftrightarrow$ 为取其系综平均。 $\left. P ^ { ( 3 ) } ( u , \nu ) \right.$ 为平均斑点掩模法传递函数。

在得到平均重谱后，由低频到高频的相位元逐步递推恢复其目标斑点图全部相位。

# 3多进程并行加速方法

# 3.1CPU/GPU混合计算方法

为了满足整个视场线性空间平移不变性，需要把预处理和初对齐后的图像分割成一个个子块，然后把相同位置上的子块合并成子块组。NVSTLevel11 $^ +$ 级别的太阳高分辨图像重建中现有并行加速方法大多还局限于CPU/GPU混合计算方法，即GPU一次只能处理单个子块组，不同子块组之间依然还是串行计算。基于CPU/GPU 混合计算方法的图像分块处理流程如图1所示。

![](images/331f661560459c3d3b7708d044aaf7e43834f8ddf95caa40401345c0e4d74086.jpg)  
图1基于CPU/GPU混合计算方法的图像分块处理流程  
Figure1 Image block processing flow based on CPU/GPU hybrid computing method

按照等晕区分块后，每一个子块组都含有多帧子块，在处理一个子块组时，除了相位递推计算比较复杂适合在CPU 端完成外，其他都是在GPU 端完成。相位递推需要用到四维重谱[9]，从低频相位点到高频相位点依次遍历全部有效的相位点。每个相位点都是由多个相位点和对应的重谱计算得到，计算复杂度高。在遍历的过程中，相位递推伴随着大量的逻辑判断，导致适合在CPU 端处理。

虽然以上方法比纯CPU端在图像分块串行处理的处理时间少，但这种方法存在两个问题：一是子块组间的处理是依次进行的（串行)，在GPU 处理时，CPU存在空闲状态，CPU利用率不高；二是GPU上一次只处理一个子块组，GPU 利用率不高。为此，本文提出了基于多进程对图像分块处理并行加速方法。

# 3.2多进程并行加速方法

针对以上现有方法存在的问题，引入多进程，提升CPU 利用率，并且通过多进程让GPU处理更多的子块组，同时提高CPU和GPU的并行化处理能力。将待处理多帧图像分割成很多子块后，子块合并为若干子块组，把所有的子块组加入任务列表中。每个进程都顺序选择任务列表中的一个子块组，多个进程同时操作GPU并行处理多组子块组。基于多进程并行加速方法的图像分块处理流程如图2所示。

![](images/9d299b543764f52876c6a48ee4156352a5a2c6b7b3660deb4ab5422b893d07b6.jpg)  
图2基于多进程并行加速方法的图像分块处理流程

Figure 2 Image block processing flow based on multi-process parallel acceleration method 多进程并行加速方法的图像分块处理流程如下：

1、创建任务列表。创建并初始化列表，将图像分块后的子块组加入到任务列表中。2、创建进程池。创建并初始化一个进程池，并在进程池中可以添加适当的子进程数量。3、分配进程任务。由主进程依次把任务列表中的任务分配给处于空闲状态下的子进程。4、传递参数。将处于CPU端的任务数据传递到GPU端，以及子块组处理过程需要的其他参数。5、处理子块组。进程池开启多少子进程，就有多少个子块组同时并行计算。子块对齐、模的重建、平均重谱的计算以及初始相位的计算等过程都是在GPU 端并行完成。GPU 端完成初始相位计算后，把初始相位数据传递给CPU端的相应子进程开始相位递推，完成相位递推后，子进程将相位数据从CPU端传递到GPU端。最后进行模和相位的合成。6、再次分配任务。每个处理完子块组后处于空闲状态的子进程，并不会被销毁而是返回进程池，进程池将空闲子进程信息反馈给主进程，若子块组任务列表仍有待执行的子块组，主进程将待执行的子块组分配给进程池中的空闲子进程。7、关闭进程池。主进程反复检测子块组任务列表，当任务列表中没有待处理子块组时，并等待所有子进程执行完毕，进程池将所有空闲子进程信息反馈给主进程，释放所有子进程并关闭进程池。由上述过程可知，各个子块组处理相互独立、互不影响，进程池中每个子进程处理相应的子块组同时并行运行。子块对齐、模的重建、初始相位计算以及模和相位的合成都是由多个子进程在GPU端并行完成的，但每个子块组的相位递推是由相应的子进程在CPU端并行计算的。值得注意的时，在创建和初始化进程池时，进程并不是越多越好，创建新进程会耗费系统资源，所以进程池中只能添加合适数量的子进程，其数量取决于CPU 和GPU的资源能力。此外，为避免不必要的系统开销，并不立即撤销完成任务的子进程，而是在任务列表还有任务时选择进程复用，再次分配任务。

下面以Python 为例，其实现方法如下。多进程管理Multiprocessing 模块提供了Pool类，通过import命令导入Multiprocessing 模块，使用 multiprocessing.Pool函数导入Pool类。创建并初始化任务列表blocklist $ = [ ]$ ，将子块组加入到任务列表中。设置指定的工作子进程数目(num)，使用pool=Pool(num)，按照指定数量子进程创建和初始化进程池，供用户调用。使用pool.apply_async(、pool.map(、pool.applyO、pool.map_async(等方法，调用子块组处理函数并传递子块组任务列表参数，然后提交给进程池。当新子块组任务请求提交到进程池时，如果Pool不满，则会创建一个新进程来执行该任务请求，如果Pool满了，告知请求等待。通过Cupy 模块中 cupy.asarray(方法和 cp.asnumpyO方法来进行 CPU 端和 GPU 端数据传输。每个子块组计算完成使用列表收集结果。当任务列表没有待处理子块组时，使用 pool.close()方法，使进程池不再接受新的任务，当所有子块组计算完成后，工作进程会退出。最后使用pool.join(方法，等待进程池中所有的子进程结束完毕结束子进程，返回主进程。关键过程的代码实现如下表1所示。

<html><body><table><tr><td colspan="2">from multiprocessing import Pool</td></tr><tr><td colspan="2">import cupy as cp</td></tr><tr><td colspan="2">def block_process(cubesub):</td></tr><tr><td colspan="2">cuberc_gpu=cp.asarray(cubesub) # Transfer subblock groups from the CPU to the GPU</td></tr><tr><td colspan="2"># Sub-block alignment,Reconstruction of amplitude s,Calculation of bispectrum,Initial phase</td></tr><tr><td colspan="2">phalxp_cpu =cp.asnumpy(x) #Phase recursion transfers data X from the GPU to the CPU</td></tr><tr><td colspan="2"># phase recursion</td></tr><tr><td colspan="2">phatmp_gpu=cp.asarray(y)</td></tr><tr><td></td><td># Amplitude and phase synthesis</td></tr><tr><td colspan="2">if__name__=='__main__:</td></tr><tr><td>blocklist =[]</td><td># Create and initialize task lists</td></tr><tr><td>blocklist.append(cubesub)</td><td># Add subblock group tasks to the task list</td></tr><tr><td>num=n</td><td># Set the number of n sub-processes</td></tr><tr><td>pool = Pool(num)</td><td># Create and initialize process pools</td></tr><tr><td colspan="2">for i in blocklist:</td></tr><tr><td>pool.apply_async(block_process,(i,))</td><td>#Commit functions and arguments to the process pool</td></tr><tr><td>pool.close()</td><td># Close the process pool and accept no more tasks</td></tr><tr><td>pool.join()</td><td># Block waits for all tasks to complete before continuing</td></tr></table></body></html>

# 4结果和分析

# 4.1实验环境

硬件：Intel(R) Core(TM) i5-8400 CPU $@$ 2.80GHz(2801MHz)的处理器（6核)，8GBRAM,NVIDIA GeForce GTX 1050 Ti，4095 MiB。软件：Microsoft Windows 10，Spyder 4.0.13，CUDA10.2， Python 3.7.6。

# 4.2并行加速结果

以图像分块处理为例，对第三章两种方法进行测时比较，实验结果如下表2所示。

表2两种方法处理时间  
Table 2 Processing time of two methods   

<html><body><table><tr><td>Parallelization method</td><td>Ha-band image block processing average time (s)</td><td>TiO-band image block processing average time (s)</td></tr><tr><td>CPU/GPU hybrid computing method</td><td>740.68</td><td>957.31</td></tr><tr><td>Multi-process parallel acceleration method</td><td>157.76</td><td>203.32</td></tr></table></body></html>

为了验证代码的正确性，实验数据选取2020年6月6日NVSTHa波段的观测数据10组，每组选取100帧（ $1 0 2 8 \times 1 0 2 4$ pixel)，每帧采用重叠方式分割成 $9 6 \times 9 6$ pixel，将每帧相同位置对应的子块合并成一组，划分为625组子块组。实验数据还选取2020年6月8日NVSTTiO波段的观测数据10组，由于受到显存大小的限制，每组选取50帧 $( 2 1 6 0 \times 2 5 6 0 \mathrm { p i x e l } )$ ，每帧采用重叠方式分割成 $1 2 8 \times 1 2 8$ pixel。将每帧相同位置对应的子块合并成一组，划分为1050组子块组。

实验表明，Ha波段和TiO波段数据在采用多进程并行加速方法时图像分块处理的平均处理时间相对较少，采用多进程并行加速方法在Ha波段和TiO 波段数据的图像分块处理部分中加速比分别可达4.69 和4.71。通过大量实验结果分析，由于在CPU/GPU 混合计算方法中，子块组之间仍然是串行计算，使得GPU一次只能处理单组分块数据，而在多进程并行加速方法中，子块组之间是并行计算，使得GPU能同时处理多组分块数据。由此可以说明基于多进程并行加速方法可提高CPU和GPU资源利用效率，可显著提升图像分块处理的速度。

在多进程并行加速方法中，不同的进程数有不同的图像分块处理时间如图3所示。

![](images/7941d9afc7abdd8dc09120702495ec9fa9229ad56aaa4e2ce35939b08b6c74e7.jpg)  
图3图像分块处理在不同进程数下的耗时情况  
Figure 3 The time consuming of image block processing under different number of processes

图3显示不同的进程数对图像分块处理并行加速的耗时情况，随着进程池中子进程数量的增加，Ha 波段的所有子块处理的时间降低到157.76s，TiO 波段的所有子块处理的时间降低到203.32s，并行加速的效果明显。但是在使用6个进程以后，受到CPU核心数、GPU显存大小以及多进程调度开销的影响，图像分块处理时间会上下浮动并呈现上升的趋势。在选择合适的子进程后，使用多进程并行加速方法处理时，CPU 和GPU 利用率都提高了，CPU 利用率可以达到 $100 \%$ 。

# 5结语

针对现有方法子块组间低效的串行处理而导致CPU和GPU利用率都不高的问题，本文提出了基于多进程并行加速太阳高分辨图像重建的方法，利用多核和多进程技术，有效提升了CPU/GPU的利用率和重建过程速度，其研究可为天文数据并行化处理提供借鉴参考。要进一步提高CPU/GPU的并行化程度，仍然有许多亟待突破的关键问题，其中CPU端承担的相位递推压力最大，耗费图像分块处理过程 $80 \%$ 的时间，下一步将考虑基于相位递推的特点进行并行化，同时对相关算法进行优化改进，使CPU/GPU 计算负载达到均衡，是下一阶段研究的重点。此外，相关研究还需要在MPI/GPU异构环境中进行验证。

# 参考文献

[1]丁一汇．太阳活动对地球气候和天气的影响[J].气象,2019,45(3):297-304.Ding Yihui.Effect of solar activity on earth's climate and weather [J]. Meteorological Monthly, 2019, 45(3): 297-304. [2] Van Noort M, Van Der Voort L R,Lofdahl M G. Solar image restoration by use of multi-frame blind de-convolution with multiple objects and phase diversity[J]. Solar Physics，2OO5,28(1-2): 191-215.   
[3] Denker C, Yang G, Wang H. Near real-time image reconstruction[J]. Solar Physics,2O01, 202(1): 63-70. [4] Woger F, Ferayorni A,Radziwill N M, et al. Accelerated speckle imaging with the ATST visible broadband imager[J]. Proceedings of SPIE - The International Society for Optical Engineering,2012, 8451:84511C-84511C-9.   
[5] Li X B,Zheng Y F.A novel parallel method for speckle masking reconstruction using the OpenMP[J]. Journal of The Korean Astronomical Society, 2016, 49(4): 157-162.   
[6] Zheng YF,Li X B,Tian HF, et al. GPU-accelerated speckle masking reconstruction algorithm for high-resolution solar images[J]. Journal of The Korean Astronomical Society, 2O18, 51(3): 65-71. [7] 宣经纬,饶长辉,钟立波,等.基于GPU 的太阳图像斑点重建技术实现[J].大气与环境光学学 报,2020,15(O2):9O-100. Xuan Jingwei, Rao Changhui, Zhong Libo,et al. Implementation of solar speckle image reconstruction based on GPU[J]. Journal of Atmospheric and Environmental Optics, 2020,15(02): 90- 100.   
[8] Liu Z, Xu J, Gu B Z, et al. New vacuum solar telescope and observations with high resolution[J]. Research in Astronomy and Astrophysics,2014,14(6): 705   
[9]向永源．太阳高分辨高速重建算法的研究[D]．昆明：中国科学院云南天文台，2016.Xiang Yongyuan. Research on high speed high resolution solar image reconstruction algorithm[D]. Kunming: Yunnan Observatory, Chinese Academy of Sciences,2016.

# High-resolution solar image reconstruction method based on multi-process parallel acceleration

Deng Tao', Chen Dong²,Dai Hongbing1,Wang Xinhua2.3 (1. School of Information Science and Engineering, Yunnan University, Kunming 65o5o4. China;   
2. Yunnan Astronomical Observatory, Chinese Academy of Science, Kunming 65o011 China;   
3.University of Chinese Academy of Science, Beijing 1Ooo49 China)

Abstract:At present, speckle interferometry and speckle masking are often used to reconstruct the mode and phase of the target in high-resolution solar image reconstruction. However, due to a large amount of grouped and partitioned data and the complexity of the algorithm, it is diffcult to meet the requirements of real-time reconstruction. In order to alleviate the pressure of data processing,based on the existing CPU/GPU hybrid computing method of single block data,a method of allocating multi-component block data to GPU through multi-process and parallel processing is proposed. The experiment shows that the method based on a multi-process parallel acceleration method can improve the utilization efficiency of CPU and GPU resources,enable GPU to process multi-block data at the same time, and significantly improve the speed of image block processing with an acceleration ratio of about 4.7. Relevant studies can provide a reference for the parallel processing of astronomical data.

Key words: Multi-process; Parallel Computing; Image Reconstruction; Speckle Masking； Speckle Interferometry