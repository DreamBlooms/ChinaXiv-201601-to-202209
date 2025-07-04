# 基于OpenCL的射电干涉阵成像gridding算法实现\*

冯勇'，王锋1,2.3，邓辉1,²，卫守林，梅盈1,2,3，戴伟1,³石聪明(1.昆明理工大学 云南省计算机技术应用重点实验室，云南 昆明 6505002.广州大学 天体物理中心/物理与电子工程学院，广东 广州 5100063.中国科学院云南天文台 云南 昆明 650011)

摘要：天文软件开发与应用中迫切需要在单机环境下进行高性能的科学数据处理工作，由于机器配置不同，采用传统的CUDA+GPU技术存在明显的局限，不利于天文软件的快速移植和无缝运行。针对明安图频谱射电日像仪（MingantU SpEctral Radioheliograph，MUSER）数据处理中的网格化（Gridding）算法，采用并行计算0penCL技术进行多线程编程实现。实验结果表明，基于OpenCL实现的gridding算法不仅能够在多种GPU上运行，而且能够在纯CPU上运行。当选择在GPU上执行时，算法的执行效率与基于CUDA实现的gridding算法执行效率大致相当，但算法不局限于NVIDIAGPU，解决了算法对CUDA+GPU的依赖；同时算法也能在纯CPU上较快速地执行，适用于单机模式下进行天文软件的开发和测试，也便于天文软件的应用与推广。

关键词：Gridding；并行计算；OpenCL；MUSER中图分类号：TP311.1 文献标识码：A 文章编号：1007-2276-(2004)4-0338-05

0引言 1一级标题：小四，黑体，上下空一行

中国新一代厘米-分米波射电日像仪一明安图频谱射电日像仪(MingantU SpEctralRadioheliograph，MUSER)是基于利用综合孔径成像原理实现在频率范围0.4-15.0GHz 内对太阳进行高分辨率（时间、空间）观测并成像的射电望远镜[1,2]。

MUSER 主要由天线(天线阵)、接收系统、数据处理系统三部分组成。天线阵由低频阵(MUSER-I，共40面天线)和高频阵(MUSER-II，共60面天线)两部分组成，天线阵的拓扑结构为螺旋阵[34]。在 MUSER 观测过程中，低频阵和高频阵分别每3 ms 产生一个数据帧，每个数据帧分别用100 KBytes和256 KBytes存储，数据流量分别为32 MB/s和86MB/s，以每天观测10小时为例，每日原始观测数据量分别约为1.2 TB和3.2 TB[5,6]。

如此海量的天文数据，对于MUSER 数据处理工作而言是一个巨大的挑战，但挑战与机遇并存。在前期研究工作中，为了满足数据处理需求，研究人员一方面采用分布式计算技术，设计并实现了一套分布式数据处理执行框架 OpenCluster[；另一方面采用并行计算技术并借助高性能计算设备，专注于底层算法研究，实现了一套高效的射电干涉阵数据处理管线[8。特别地，采用 MPI（Message Passing Interface，消息传递接口）、CUDA（Compute Unified DeviceArchitecture，统一计算设备架构）以及OpenCL（Open Computing Language，开放运算语言）技术已经在天文中有相关的应用，并已经取得一定的成果[9.0.11]。证明这些技术稳定性与性能可以满足天文应用软件开发的要求。

为了便于MUSER数据处理系统的开发、部署、应用以及推广，同时满足单机环境下仍旧能够进行高性能的成像数据处理工作。在前期对OpenCL 技术研究基础上，进一步采用OpenCL 技术对射电干涉阵成像中的网格化（Gridding）算法进行并行优化，在保证gridding 算法执行效率的同时，提升算法对各种硬件平台的适应性，便于后期MUSER 数据处理软件的应用与推广。

# 1基于OpenCL的gridding算法实现

# 1.1Gridding算法

射电干涉阵成像过程是基于综合孔径成像原理对采样的可见度数据进行网格化（Gridding）、快速傅里叶变换（Fast Fourier Transformation，FFT）、去卷积（Deconvolution）等操作，最后产生射电源的观测图像[12]。

为了借助离散傅里叶变换（Discrete Fourier Transform，DFT）的快速方法—FFT一的计算效率，进行快速成像，射电干涉阵采集到的可见度数据必须落在一个均匀划分的网格上（如图1左图所示)。实际中，由于UV采样点分布不均匀，干涉仪得到的是非均匀采样可见度数据(Non-uniform Sampled Visibility Data）（如图1右图所示)，将非均匀采样可见度数据插值到均匀划分的网格点上的过程称为网格化（Gridding） ）[13,14]

![](images/39c805a364ecd7e52ad5402dd346ac79071e7a9fdd7818c8e09cf282182caff0.jpg)  
图1均匀划分的网格（左）与非均匀分布的可见度数据示意图（右）

将非均匀采样可见度数据转换成均匀采样可见度数据，即对未知像素点的数据进行重采样，主要有两类方法：内插法和卷积核法。一些内插值方法被开发用于重建非均匀采样，如最邻近插值，双线性插值等；文献[15]表明最优的网格化方法是卷积一个无限扩展的 sinc 函数，即卷积核法，出于实际考虑，有限的卷积函数取代了无限扩展的sinc 函数。常用的网格卷积函数（GriddingConvolution Function，GCF）有截断 sinc 函数，截断指数函数，拟合的球面波函数，文献[16」讨论了这些网格卷积函数在不同尺寸大小下的性能。在MUSER 数据处理中，我们选取了大小为6的拟合的球面波函数作为网格卷积函数。

![](images/37a5a3d512583c6d6d5a51be6bb163a2d1f7757f13e389d2ee8ddfd142e00f07.jpg)  
Fig.1 Regular grid (left） and the schematic diagram of non-uniform visibility data (right)   
图2卷积网格化并成像 Fig.2 Convolutional gridding and imaging

# 1.2Gridding算法并行化

根据 OpenCL 编程规范，OpenCL程序主要由两部分组成：一部分是采用OpenCL语言（类C语言）编写的内核函数，执行在OpenCL设备（多核CPU、GPU、Cell、DSP、FPGA等）上；另一部分是通过调用OpenCL的应用编程接口（Application Programing Interface，API）管理内核函数的主机程序，执行在主机（CPU）上。

本文将gridding 过程中的关键步骤，由OpenCL 语言编写成内核函数，以便在 OpenCL 设备上并行执行，再通过在主机上调用这些内核函数，从而实现gridding 算法的并行化。主要改写成的内核函数有：gridding_kernel，correct_grid_kernel，normalize_kernel，point_symmetric_kernel，shift_kernel 等。此外，成像过程的傅里叶变换是通过调用基于OpenCL 实现的快速傅里叶变换FFT，包含于python的pyfft包中。

![](images/bec8bdbf52399353f778673e3c4053d005150f0d4d6fa84c458a1d2a8cd44183.jpg)  
图3Gridding并行执行流程图Fig.3 The flow diagram of parallel gridding

本文处理的图像数据是以二维数组的形式表示，在采用OpenCL语言编写内核函数过程中，  
由 OpenCL 提供的二维数组索引get_global_id(O)和 get_global_id(1)，唯一标识二维数组中  
的元素，为方便计算，需借助传递给内核函数的二维数组的参数（宽度或高度)，将二维数组按  
行或按列转换成一维数组，这样，二维索引get_global_id(O)和get_global_id(1)转换成一维  
索引值-id，当内核函数在并行设备中执行时，每个线程处理由索引值-id唯一标识的二维数组元素。

![](images/3924a745f9aecad6de552bec5d6986e3f91e463f2c28dc4ddf76c909e96ac443.jpg)  
图4OpenCL二维索引转换一维索引示意图

在gridding执行过程中，由于可见度数据共轭对称，故在对可见度数据进行插值网格化时，为减少网格化的计算量，先对一半的可见度数据进行插值网格化，再通过中心点对称方式计算得到另一半数据。将中心点对称操作编写成内核函数point_symmetric_kernel，示意图如下。

![](images/b1f5f09cc9abe46b5f8e1e8b046d203a80be7882e44ef293eac8b03d65189adb.jpg)  
Fig.4 The schematic diagram of OpenCL two-dimensional index to one-dimensional index

Fig.5 The schematic diagram of point symmetric operatiolpoint_symmetric_kernel伪代码如下：  

<html><body><table><tr><td>OpenCL kernel function:point_symmetric_kernel</td><td></td></tr><tr><td>//Obtain two dimensional array index (ix,iy)</td><td>Input parameter:a twodimensional array im,a flag hfac,the two dimensional array height Hand width W</td></tr><tr><td>ix←get_global_id(0)</td><td></td></tr><tr><td>iy←get_global_id(1)</td><td></td></tr><tr><td>//Stay within the bounds</td><td></td></tr><tr><td>If ix>O and ix<Hand iy >O and iy<W/2 then</td><td></td></tr><tr><td>nix←H-ix</td><td></td></tr><tr><td>niy←W-iy</td><td></td></tr><tr><td>im[ix*W + iy].x←im[nix*W + niy].x</td><td></td></tr><tr><td>im[ix*W +iy].y←hfac*im[nix*W +niy].y Output:a new two dimensional array im</td><td></td></tr></table></body></html>

在傅里叶变换过程中，为使变换后的图像是一个完整的周期，需要进行平移（shift）操作。将shift操作编写成内核函数shift_kernel，示意图如下。

![](images/139d3f8223a10b9e20bb0c75b116ca82b035441630bd23916f40ed057703f5bd.jpg)  
图5中心点对称操作示意图  
图6傅里叶变换平移操作示意图

在 gridding 执行过程中，由于可见度数据与一个网格卷积函数GCF 进行了卷积，为消除GCF 的影响，需进行网格校正操作。将网格校正操作编写成内核函数correct_grid_kernel。此外，进行网格校正后，需要对脏图和脏束进 $\stackrel { } { = }$ 步的进行归一化或标准化。将脏束进行归 $\stackrel { } { = }$ 化，即将脏图和脏束中所有元素除以脏束中的最大值；对脏图进行标准化，即以及将脏图中所有所以元素除以脏束中的最大值，从而保证脏束的峰值为1以及脏图与脏束具有相同量纲标准化后的脏束和脏图具有相同的量纲，便于后续进行洁化。

![](images/c4b6e8b21204923e100a32fb8d7a4eccf38b50caea70304a0c4c4c317c38d3c7.jpg)  
Fig.6 The schematic diagram of Fourier transform shift operatior   
图7标准化操作示意图  
Fig.7 The schematic diagram of normalize operation

# 1.3并行加权

由于UV采样点太少，对可见度函数采样值进行傅里叶逆变换得到的图像（称为脏图）包含一些虚假信息，通过对UV采样点赋予不同的权值来改善图像质量的操作称之为加权[17]。常用的加权方式有自然加权，统一加权以及Taper 加权，本文将这三种加权方式改写成OpenCL内核函数 weight_natural_kernel、weight_uniform_kernel 和weight_taper_kernel。

三种加权方法伪代码如下：

<html><body><table><tr><td></td><td>OpenCLkernel function:weight_natural_kernel、weight_uniform_kernel、weight_taper_kernel Input parameter:a twodimensional array nim,the numberof samples falling intocellcnt,the twodimensional array</td></tr><tr><td>heightHandwidthW</td><td></td></tr><tr><td>//Obtain two dimensional array index (ix,iy)</td><td></td></tr><tr><td>ix←get_global_id(0)</td><td></td></tr><tr><td>iy←get_global_id(1)</td><td></td></tr><tr><td>id←iy+ix*W</td><td></td></tr><tr><td>//Stay within the bounds</td><td></td></tr><tr><td>If ix>O and ix<Hand iy>O andiy<W then</td><td></td></tr><tr><td>if cnt[id] !=O then</td><td></td></tr><tr><td>//natural weighting</td><td></td></tr><tr><td>wgt←1.</td><td></td></tr><tr><td>//uniform weighting</td><td></td></tr><tr><td></td><td></td></tr><tr><td>wgt←1./cnt[id]</td><td></td></tr><tr><td>//taper weighting</td><td></td></tr><tr><td>wgt←exp(-((ix-H/2)*(ix-H/2)+(iy-W/2)*(iy-W/2))/(2*0.5*0.5*W*W))</td><td></td></tr><tr><td>nim[id].xnim[id].x*wgt</td><td></td></tr><tr><td>nim[id].y←nim[id].y*wgt</td><td></td></tr><tr><td></td><td></td></tr><tr><td>Output:weighted nim</td><td></td></tr></table></body></html>

自然加权赋予相应像素点的权重为1，统一加权赋予相应像素点的权重为区域内采样点频数的倒数，Taper加权赋予相应像素点的权重为对应高斯函数值。通过改变像素点的权重大小，对可见度数据进行加权操作，从而改善图像质量。

# 2 实验结果

# 2.1实验环境

OpenCL 定义不同的公司或厂商为不同的平台(Platform)，每个公司或厂商提供不同的OpenCL设备(Device）。本文选用的OpenCL设备有 NVIDIA的GPU（GeForce GTX TITANX，Tesla$\mathrm { k 2 0 m ) }$ 和Intel的CPU（Intel Xeon E5-2620 V2)，平台及设备参数见表2。

表2平台和设备参数信息  
Tab.2 The information of platformand device   

<html><body><table><tr><td>Parameter</td><td>Intel CPU</td><td>GTX TITAN X GPU</td><td>Tesla k20m GPU</td></tr><tr><td>Platform vendor</td><td>Intel(R) Corporation</td><td>NVIDIA Corporation</td><td>NVIDIA Corporation</td></tr><tr><td>Platform version</td><td>OpenCL 1.2 LINUX</td><td>OpenCL 1.2 CUDA 7.5.18</td><td>OpenCL 1.2 CUDA 7.5.18</td></tr><tr><td>Device name</td><td>Intel(R) Xeon(R) CPU E5-2620 V2 @ 2.10GHz</td><td>GeForce GTX TITAN X</td><td>Tesla k20m</td></tr><tr><td>Device type</td><td>CPU</td><td>GPU</td><td>GPU</td></tr><tr><td>Device max clock speed</td><td>2100 MHz</td><td>1215 MHz</td><td>705 MHz</td></tr><tr><td>Device compute units</td><td>24</td><td>24</td><td>13</td></tr><tr><td>Device cores</td><td>6</td><td>2496</td><td>2496</td></tr><tr><td>Device max work group size</td><td>8192</td><td>1024</td><td>1024</td></tr></table></body></html>

# 2.2实验结果

实验数据来源于MUSER 2015年11月1日12时8分49秒354毫秒时刻对太阳的观测数据，原始观测数据经过一系列预处理（坏天线标记，星表查询等）合成为标准天文数据格式(UVFITS文件)，数据文件被命名为 20151101-120849_354161240.uvfits。通过 MUSER 数据处理系统执行网格化和快速傅里叶变换等操作，生成相应时刻太阳亮度分布图像（未经过去卷积操作的图橡称为脏图）以及对应的点扩散函数（Point Spread Function，PSF)，PSF 也称为脏束。

![](images/12ba8034ca5a65d08681b8cd15674284908075da81e76562fbd04357f6d9d476.jpg)  
图87 MUSER 成的脏图（左）和点扩散函数PSF（右)，观测时间是 2015年11月1日12:08:49:354，频率是 $1 . 7 1 2 5 ~ \mathrm { G H z }$ ，极化方式是右旋Fig.87The dirtyimage(left）and PSF(right）of MUSERat12:08:49:354on November11th,2015(Frequency:1.7125 GHz,Polarization:right)

在同一台服务器上，分别在CPU（Intel Xeon E5-2620 V2)、GPU（GeForce GTX TITAN X,Tesla k20m)并行设备上执行基于OpenCL 实现的 gridding 算法和在GPU(GeForce GTX TITAN X,Tesla k20m)上执行基于CUDA 实现的gridding 算法，并进行快速傅里叶变换成图，分别生成大小为 $1 0 2 4 * 1 0 2 4$ pixels和 $2 0 4 8 * 2 0 4 8$ pixels的脏图。网格化并成图（Gridding+IFFT）过程执行时间参照下表。

表3Gridding+IFFT过程执行时间表 Tab.3 the Execution time of Gridding and FFT   

<html><body><table><tr><td>Device-设备</td><td>Imagesize图像大小</td><td>Executiontime（s）执行时间（s）</td></tr><tr><td rowspan="2">CPU OpenCL</td><td>1024*1024</td><td>0.904</td></tr><tr><td>2048*2048</td><td>4.407</td></tr><tr><td rowspan="2">GPU OpenCL(TITAN X)</td><td>1024*1024</td><td>0.350</td></tr><tr><td>2048*2048</td><td>0.713</td></tr><tr><td rowspan="2">GPU OpenCL(k20m)</td><td>1024*1024</td><td>0.372</td></tr><tr><td>2048*2048</td><td>0.782</td></tr><tr><td rowspan="2">GPU CUDA(TITAN X)</td><td>1024*1024</td><td>0.323</td></tr><tr><td>2048*2048</td><td>0.610</td></tr><tr><td rowspan="2">GPU CUDA(k20m)</td><td>1024*1024</td><td>0.344</td></tr><tr><td>2048*2048</td><td>0.760</td></tr></table></body></html>

从表中可以看出，执行基于OpenCL 和基于CUDA实现的gridding 算法并成图，在GPU环境下所消耗的时间基本相当，同时，基于OpenCL 实现的gridding 算法还能在纯CPU环境下较快速地被执行。

# 2.3讨论

本文采用并行计算OpenCL技术,基于Python 语言导入PyOpenCL与PyFFT扩展包,对 MUSER成像过程中的gridding算法以及快速傅里叶变换FFT成图过程进行了实现。基于OpenCL实现的gridding算法具有如下优点：

（1）能够在GPU环境中执行，并且不局限与NVIDIAGPU（实验条件限制，只选用了NVIDIAGPU和IntelCPU),执行效率与基于CUDA实现的gridding 算法执行效率大致相当，保证了MUSER成图的性能;

（2）能够在多核CPU环境下执行，适用于在单机环境下进行开发与测试，便于MUSER软件的推广与应用。

综上所述，采用OpenCL实现的并行gridding 算法，在保证算法执行效率的同时有效地提升了算法对硬件平台的适应性。此外，本工作进一步验证了OpenCL在天文软件开发中的可用性，从CUDA到OpenCL，异构系统从NVIDIAGPU+CPU的异构模式转变成并行设备+CPU的异构模式。这种异构模式的转变将扩展并行计算在天文高性能软件开发中的应用。

# 3 下一步工作

本文研究的射电干涉阵成像过程局限于小视场，在大视场成像中w项引起的视场扭曲是不可忽略的，传统的二维FFT成像将不再适用，因此，下一步我们将在此研究工作的基础上，采用OpenCL 技术对大视场成像中的关键算法，例如w-pro jection，faceting以及大视场混合算法，进行并行优化。

# 4致谢

衷心感谢以下项目对本项工作的资助。基金项目：国家重点研发计划(2016YFE0100300)，国家自然科学基金委员会-中国科学院天文联合基金(No.U1531132,U1631129,U1231205)，国家自然科学基金(No.11403009,11463003,11773012)，赛尔网络下一代互联网技术创新项目(No.NGII20170204)。

感谢国家天文台-阿里云天文大数据联合研究中心对本项工作的支持。

# 参考文献

[1]YanY,ZhangJ,WangWetal.TheChineseSpectraladioeliograp—CRH[J].Earthoon&Planets,O,04(-4)90.   
[2] 赖铖，梅盈，邓辉,等.MUSER可见度数据积分方法与实现[J].天文研究与技术,2018(1):78-86.   
Lai Cheng,MeiYing,DengHui,etal.IntegralMetodandImplementationofMUSERVisibilityData[J].AstronomicalResearch& Technology- Publications of National Astronomical Observatories of China,2O18(1):78-86.   
[3]周鑫磊，王威，王锋,等．基于QT的MUSER观测数据多屏图形化实时显示的设计与实现[J].天文研究与技术,2015, 12(4):503-509.   
Zhou Xinlei,WangWei,WangFeng,etal.Designand ImplementationofaMulti-MonitorDisplaySystemBasedontheQTforNAOC MUSER Observations[J].Astronomical Research& Technology—Publications of National Astronomical Observatoriesof China,2015,12(4): 503-509.   
[4]Shi C,WangF,DengH,etal.HighPerformanceNegativeDatabaseforMasive Data ManagementSystemofThe Mingantu Spectral Radioheliograph[J].Publications of the Astronomical Society of the Pacific,2Ol7,129(978).   
[5]DaiHM,MeiY,Wang W,etal.AnAuto-flag MethodofRadioVisibilityDataBasedonSupportVectorMachine[J].Chinese Astronomy & Astrophysics,2017,41(1):125-135.   
[6]Feng W,HuiD,Wei W.HighperformancedistributeddataprocessngpipelineforChineseSpectralRadioHeliographC/adi Science Conference.IEEE,2015:1-1.   
[7]Wei S,WangF,DengH,etal.OpenCluster:AFexibleDistrbuted ComputingFrameworkforAstronomicalDataProcesing[J]. Publications of the Astronomical Society of the Pacific,2016,129(972):024001.   
[8]WangF,JiKF.DistributedData-ProcessingPipelineforMingantuUltrawide SpectralRadioheliographJ].Publicationsofthe Astronomical Society of the Pacific,2015,127(950):383-396.   
[9]陈泰燃，王威，王锋,等．基于MPI的高性能UVFITS数据合成研究与应用[J].天文研究与技术,2016,13(2):184-189.   
Chen Tairan,Wang Wei,WangFeng,etal.The Studyand ApplicationofaHigh PerformanceUVFITSAssemblySystem Basedon MPI[J.Astronomical Research &Technology—Publications of National AstronomicalObservatoriesof China,2016, 13(2):184-189.   
[10]MeiY,WangF,Wang W,etal.GPU-BasedHigh-Performance Imaging for Mingantu Spectral RadioHeliograph[J].2017.   
[11] 冯勇，陈坤，邓辉,等．基于OpenCL的MUSERCLEAN算法研究与实现[J].天文学报,2017,58(2):55-64.   
FengYong,ChenKun,DengHui,etal.TheResearchand ImplementationofMUSERCLEANAlgorithmBasedonOpenCL[J].Acta Astronomica Sinica, 2017,58.   
[12]HogbomJA.Aperture Synthesis withaNon-Regular Distributionof Interferometer Baselines[J].Astronomy&Astrophysics Supplement,2011,15(15):417.   
[13]Thompson,racewellIterpolatioadouriertasforationffingevisibilites[J].stronomicalJoual97, 79(1):11-24.   
[14]SedaratH,NishimuraDG.Ontheoptimalityofthegridingreconstructionalgorithm[J].IEEETransactionsonMedicalaging, 2000,19(4):306.   
[15]O'SullivanJD.AFastSincFunctionGriddingAlgorithmforFourierInversioniComputerTomography[J].IEEETransactiosor Medical Imaging,1985,4(4):200-207.   
[16]JacksonJ,eerCHsuraG,etalelectiofConvolutionunctionfoFourierIversioUngiddingEE Trans.Medical Imaging.1991:473-478.   
[17]Boone F.Weighting interferometric data fordirectimaging[J].Experimental Astronomy,2O13,36(1-2):77-104.

# Implementation of gridding algorithm for radio interferometric imaging based on OpenCL

Feng Yong1，WangFeng23，Deng Hui12，Wei Shoulin1，MeiYing123，Dai Wei13，ShiCongMing (1.ComputerTechnologyAplicationKeyLabofYunnanProvince,KunmingUniversityofScienceandTchologyKuming650500, China 2.AstrophysicsCenter/stituteofhysicsandElectroicEnginering,GuangzouUniversityGuangzou,Guangzouo,Cina 3.Yunnan Astronomical Observatories,Chinese Academy of Sciences,Kunming 65oo11,China)

Abstract: It's urgent to carry out high-performance scientific data processing with a single machine in the development and application of astronomical software.However,due to the different configurations of machines，the traditional CUDA $^ +$ GPU technology has obvious limitations in portability and seamlessness. According to gridding algorithm in MingantU SpEctral Radioheliograph (MUSER） data processing,the OpenCL technology is used in parallel to implement multi-thread programming. The experimental results show that the gridding algorithm based on OpenCL can not only can run on various-GPUs, but also merely on CPUs.While choosing execution on GPU,the execution efficiency of gridding algorithm is approximately equal with it based on CUDA.At the same time,the algorithm is not limited to the NVIDIA's GPU,which has solved the problem of environmental dependence of $\mathrm { C U D A + G P U }$ . And the algorithm also has an acceptable execution effciency high implementation with the merely CPU, which is suitable for development and testing astronomy software with a single machine ,but-alse and willfacilitate the application and promotion of astronomical software.

Key words: Gridding; Parallel computing; OpenCL; MUSER