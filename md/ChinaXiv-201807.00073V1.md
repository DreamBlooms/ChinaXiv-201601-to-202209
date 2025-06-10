# 幸运成像算法的FPGA实现

赵盼孜，李彬华， 毛拢哗, 陶勇（昆明理工大学信息工程与自动化学院，云南昆明650051)

摘要：幸运成像技术是用于消除天文图像中大气湍流影响的高分辨率图像重建技术，传统的基于CPU的幸运成像算法难于实时化。本文利用FPGA并行处理的优势，设计了一种基于FPGA的幸运成像算法并构建了一个FPGA实验系统。该系统用FPGA完成了选图、配准、叠加的全部幸运成像算法流程，所得高分辨率图像与基于传统CPU算法处理的结果完全相同，但幸运成像算法的处理速度比传统CPU的处理速度快19倍。该算法在FPGA上的实现，为幸运成像技术的实时或准实时化提供了一种可行的方案。

关键词：图像处理；高分辨率图像重建；幸运成像；FPGA中图分类号：TP391.4 文献标识码 文章编号

# 引言

地基大口径光学望远镜对天体成像的分辨率受制于大气湍流[I。为了消除大气湍流对目标成像质量的影响，常见且有效的方法是采用自适应光学（AdaptiveOptics，AO）技术，以及事后处理方式的图像复原技术，幸运成像技术就是其中之一。幸运成像技术利用部分短曝光图像中包含的目标高分辨率的结构信息，在观测后进行图像重建，以便消除大气湍流的干扰从而获得高分辨率图像[1,2]。本世纪初出现的电子倍增电荷耦合器件（ElectronMultiplying Charge-Coupled Devices，EMCCD）成像技术具有高分辨率、高读出速度、低噪声等诸多优点，适合于曝光时间在毫秒及其以上量级的微光成像领域[3]。该技术的出现，使得幸运成像技术获得了长足的进步，并在在天文观测领域取得了极大的成功，2013年以前发表的论文就已超过200 多篇[2]。典型的幸运成像系统包括英国剑桥大学的LuckyCam、德国马普研究所的AstraLux和西班牙加那利群岛天文研究所的FastCam，他们在双星或多星系统中的暗伴星的发现、天测天力参数计算等方面，科学产出极为丰富[4,5]。

幸运成像技术是一种简单可行的图像复原方法，但由于图像复原是在观测完成后的一段时间内进行，其缺点也是明显的，即天文观测人员对于所拍摄图像的实时信息了解不多难以及时发现并纠正观测中可能存在的偏差或错误。解决此问题的一个办法是改进算法，增加硬件的处理能力[3]，将幸运成像技术实时或准实时化。

传统的中央处理器（Central ProcessngUnit，CPU）对图像数据的处理采用的是串行方式，对于大量图像的幸运重建来说，难以实现实时或准实时化。相较于CPU，现场可编程逻辑阵列（Field Programmable Gate Array，FPGA）器件有着先天的并行性和灵活性优势，能提供强大的并行计算能力，可加速数据或信号的处理，特别是图像处理[]，在天文观测和数据设备中使用越来越多[7]。将FPGA用于幸运成像，是将该技术实时或准实时化的一种有效方法。2008年FastCam项目研究过程中，首次将幸运成像技术在FPGA硬件上实现，并获得了实时的高分辨率图像[1,8]；2015年Jackson 也将幸运成像算法在FPGA和GPU 中实现。不过，他们在论文中并没有对算法的FPGA实现进行细致的描述。FPGA与幸运成像算法结合的研究工作国内尚无报道。

本文对传统的基于CPU和程序设计语言的幸运成像基本算法进行了简短的分析，结合FPGA 技术的特点，提出了一种适合于FPGA处理的幸运成像方案，用Verilog 硬件描述语言（HDL）进行各功能模块的设计，并将幸运成像算法成功地在FPGA开发板上实现，最后利用中国科学院云南天文台丽江观测站 $2 . 4 \mathrm { m }$ 天文望远镜拍摄的大量目标短曝光图像进行硬件算法设计的可行性验证。

# 1基于FPGA的幸运成像算法处理流程

幸运成像算法的基本思想是按照一定的评价标准，从一系列短曝光图像中选出符合评价标准的“幸运图像”或区域，之后再对其进行配准叠加处理，以获得不受或少受大气湍流影响的高分辨率图像[2]。本文所构建的幸运成像系统在实现过程中按照基本的幸运成像算法的设计要求进行，只是在为了适应本系统所用FPGA的处理逻辑与资源限制，在不改变幸运算法基本处理流程（选图、配准、叠加）的基础上将该算法用VerilogHDL重新进行了设计。

# 1.1幸运图像的选取

在一系列短曝光序列图像中选出“幸运图像”是最终获得高分辨图像的关键因素。然而为获得“幸运图像”必须选取一个合适的像质评价函数。对于空间点源目标图像来说，像质评价函数通常采用图像的斯特列尔比（StrehlRatio，SR）作为评价标准。由于SR定义为存在像差时图像的峰值光强与不存在像差时图像的峰值光强之比，因此，计算时需要理想的无像差峰值光强。但这个理想的峰值光强在现实中并不容易获得，故通常采用其它的替代方案。一个简单且有效的方法是使用瞬时的斯特列尔比作为图像的像质评价函数[2,10]，即只对图像上的峰值光强像素点的灰度值进行SR值估算。

对于FPGA这类运算资源有限的硬件，计算SR只能采用简单的处理方式。具体来说，在本系统实现过程中，直接使用有像差时图像的峰值光强像素点的灰度值。由于在配准过程中对每帧图像的峰值光强像素点灰度值的位置有要求，故在本系统选图过程中，以图像的峰值光强像素点灰度值及其位置共同对图像进行像质评价。

# 1.2图像的配准与叠加

配准是幸运成像处理中最重要的一环，如若配准不当就会直接导致叠加后的图像模糊不清，分辨率下降，从而无法将暗弱目标图像显示出来。由于本系统使用的是恒星的图像，所以最常用的配准方法有两种，一种是以整幅图像中的最大灰值为中心截取所需的成像区域，另一种则是以图像的质心为配准基点。由于FPGA硬件逻辑及资源的限制，本系统采用前一种配准方法。

图像配准完成后，则需要对配准图像进行叠加。在本系统中由于所选图像数量偏小，所以采用的直接叠加方法。叠加后所得像图再进行灰度变换（即锐化）便可得到易于观察的高分辨率图像。

# 2 幸运成像算法的FPGA实现

本文所述的幸运成像算法实现的硬件平台是以Xilinx公司 Spartan-6系列的XC6SLX16芯片为核心的开发板。开发环境为ISEDesign Suite 14.7，逻辑设计所用HDL是Verilog，采用 ChipScope pro 14.7和ModelSim10.1d进行硬件设计的验证与调试。

# 2.1算法总体设计

由于本项目设计的主要目的是在FPGA硬件上实现幸运成像算法，因此为读取图片像素数据，首先将天文短曝光图像存储在开发板外挂的安全数据卡（SecureDigitalCard，即SD卡）中，以便给算法模块读取图像数据。此外，为满足算法对速度及片内存储的要求，同时由于所用芯片逻辑资源和存储空间的限制，故在数据处理方式上本文采用数据流，即逐像素处理的方式，但在每个模块内以及各个模块间均采用的是并行的方式对数据进行处理。与此同时在片内数据的存储上为使处理速度和存储器之间达到最佳状态，采用片内的双端口随机存储器（Random Access Memory，RAM）模块作为数据缓存器。然而，由于所用FPGA芯片RAM资源以及逻辑资源的约束，只能对1000张 $1 2 8 \times 1 2 8$ 像素大小的短曝光图像作选图处理，并且在配准过程中只能最大截取 $6 4 \times 6 4$ 像素大小的图片进行配准处理，并最终以 $6 4 \times 6 4$ 像素大小显示幸运成像结果。

对于整个算法的硬件构架来说，为了算法实现过程中修改及调试的方便，采用了模块化的设计方式。主要模块包括数据的读写、保存模块，短曝光图像的选图、配准、叠加模块以及最终的重建高分辨率图像显示模块，并用VerilogHDL进行设计实现。基于FPGA实现的幸运成像算法的结构框图如图1所示。这一幸运成像的FPGA硬件的工作流程可描述如下。

![](images/abcbd4eaa9d7b9ce69cad480b2156df4e800400c17bdad79565a50c46a822d80.jpg)  
图1基于FPGA的幸运成像算法的结构框图  
Fig.1 Structure block diagram of lucky imaging algorithm based on FPGA

系统上电后，SD卡中存储的天文图像数据会通过串行外设接口（Serial PeripheralInterface，SPI）以 $6 . 2 5 \mathrm { M b / s }$ 的速度不断地向SD卡顶层模块传送，经SD卡顶层模块处理过的数据经先入先出（First-In First-Out，FIFO）缓冲器不断地向第三代双倍数据率同步动态 随 机 存 取 存 储 器（Double-Data-Rate Three Synchronous Dynamic Random AccessMemory，DDR3）写数据模块中写入（DDR3速度 666Mb/s），然后再通过DDR3写数据模块的处理，向FPGA芯片外部的DDR3存储器中写入图像数据。在写数据模块向DDR3 写入像素数据的同时，选图模块也不断地对每帧图片的像素值进行最大灰度值求解，然后再对求出的所有图片的最大灰度值排序；当排序结束，也就说明选图结束，产生选图结束信号。

其后，便向配准模块发送要截取的原始图片的序号以及该图片最大灰度值位置参数，以便配准模块向DDR3读数据模块发送所选图片首像素地址。与此同时，选图结束信号也会发送给DDR3读数据模块，当选图结束信号和所选图像首像素地址同时作用于DDR3读数据模块时，该模块便会将数据从DDR3存储器中读出满足条件的图片像素进行叠加处理。虽然从图1的流程上看，配准、DDR3读出与叠加这三个模块是串行的，但用HDL设计及FPGA实现时，它们是并行的，它们的运行从时间上看是重叠的。

当所选的全部图片叠加完成后，再将结果进行分段线性灰度变换的处理，以增强目标区域的可视性。然后再将最终高分辨率图像的像素数据保存在片内RAM中。当保存完毕后，再通过视频图形阵列（Video Graphics Array，VGA）驱动模块驱动，将灰度图在VGA 显示器上显示。

# 2.2选图模块的设计

在选图模块的实现上本系统主要采用最大灰度值求解模块以及最大灰度值排序模块共同搭建而成，这两个子模块的搭建主要是由比较器、计数器以及片内RAM存储器来完成的。其中最大灰度值查找模块的状态转移图如图2所示。

![](images/7c62606d66d25174be37463e0b588f11b08046a635ba19b754d655ec509f57a6.jpg)  
图2最大灰度值查找的状态转移图  
Fig.2 State transfer graph of maximum gray value lookup

在图2中myvaild $_ { = 1 }$ 表示SD卡中的数据可以取出，cnt表示已读取的一帧图像的像素数目，其中 $\mathrm { c n t = 0 }$ 表示一帧图像的全部像素已读完。eve_ $\scriptstyle { \mathrm { t } } = 1$ 表示单帧图像的最大灰度值开始取出，pic_num表示图像的帧数，wea_max $_ { \cdot } = 1$ 表示可以开始向RAM中写数据。从3.1节中可知，在本设计中所用的图像大小为 $^ { 1 2 8 \times 1 2 8 }$ ，帧数为1000，所以cnt最大为16383，pic_num最大为999。

从图2中可以看出，该模块的主要功能是对从SD卡中读出的图片像素值逐个进行比较，以找出每帧图像的最大灰度值并将其保存在片内RAM中供排序使用。值得注意的是，在每求出一帧图像最大灰度值后，在条件触发时先将其缓存，然后等相应条件到来时再将其进行判断，看其是否满足配准对最大灰度值位置的要求。满足则在RAM相应的地址空间中保存该像素值，不满足则在RAM相应的地址空间中存入与该最大灰度值相同比特位数的零值。其次，在向RAM中保存每帧图像最大灰度值时，要同时将该最大灰度值所在的图片序号及位置参数一并保存在RAM相应地址空间中，以便进行并行串行混合排序。

# 2.3配准模块的设计

在配准算法的实现上，采用以最大灰度值为图片中心，截取 $6 4 \times 6 4$ 像素大小进行叠加处理，其设计主要是通过选图模块中发送的最大灰度值所在图片序号以及其位置参数，再根据式(1)计算出要截取的图片首地址，然后发送给DDR3 读数据模块，用以从DRR3存储器中读出相应的图片像素值，供叠加模块处理，该模块并不占用片内RAM资源，只是少量的使用了Slices资源。

$$
c ^ { 3 } - p ^ { 0 } \_ c m d \_ a d d r \_ r = ( ( p i c \_ c n t - 1 ) \times 6 5 5 3 6 ) + ( ( ( ( \operatorname { I n Y } ( \operatorname* { m a x } _ { - } c n t / 2 ^ { 7 } ) - 3 1 ) \times 1 2 8                 ( ( p d \ x \_ { - } c n t - 1 ) \times 6 5 5 3 6 ) + ( ( ( ( ( \operatorname* { I n Y } ( \operatorname* { m a x } _ { - } c n t - 1 8 ) ( \operatorname* { m a x } _ { - } c n t / 2 ^ { 7 } ) \times 1 2 8 ) - 3 1 ) ) - 1 ) \times 4 ) )
$$

其中， $c 3 _ { - } p 0 _ { - } c m d _ { - } a d d r _ { - } r$ 表示要读取的DDR3的地址，pic_cnt表示要读取的最大灰度值所在的图片序号，max_cnt表示要读取的最大灰度值在图片中的位置参数，$\mathrm { I N T } \big ( \operatorname* { m a x } _ { - } c n t / 2 ^ { 7 } \big )$ 表示max_cnt除以 $2 ^ { 7 }$ 之后只取整数部分，在FPGA实现时用移位寄存器实现。

# 2.4叠加模块的设计

对于图像的叠加主要是通过片内RAM资源的使用实现的，在叠加模块设计中占用的片内RAM个数为12个约 $3 7 . 5 \%$ 。该模块的结构框图如图3所示。

![](images/5498add469c34a541d473bd13661855688c8a0f7cd2a1e428b2a2c2b28acc479.jpg)  
Fig.3Block diagram of stacking module

# 3 实验结果及其分析

为了验证前面所述的幸运成像算法在FPGA上实现的正确性，我们拟用MATLAB 对相同的幸运成像算法编程并将其在PC机上的处理结果与FPGA处理结果进行对比。而对于FPGA上运行幸运成像算法的处理时间问题，也只能与PC机的运行时间做比较。所以本文设计了两个实验，一是与MATLAB处理结果的对比实验，一是本系统自身处理结果与数据实验。

幸运成像实验，必须有天文目标短曝光图像。本文采用的是2016年10月20日在云南天文台丽江观测站对天文双星HDS70的观测图像，共10000帧，这组图像的观测条件和参数参见毛拢哗等人的论文[1]。在图像帧数以及图像大小的选取上，由于所用的FPGA开发板资源的限制，多次随机从10000帧图像中抽取1000帧，并裁剪成 $^ { 1 2 8 \times 1 2 8 }$ 像素大小的天文目标短曝光图像进行处理。

![](images/30827470312b348167fd9f46ae980280cfa732dd147329e011b48697ba52aef3.jpg)  
图3叠加模块结构框图

# 3.1幸运成像算法在CPU+MATLAB上的平台上处理实验

实验硬件平台是：Dell Precision T5500 图像工作站、16GB 内存、NVIDIA GTX1050Ti显卡，运行的软件环境是Windows 7操作系统、MATLAB R2014a。

将随机抽取的1000 帧 $^ { 1 2 8 \times 1 2 8 }$ 像素大小的图像进行分组，然后在MATLAB分别对每组图像均进行同样的算法处理，在实际处理中我们只截取了 $6 4 \times 6 4$ 像素大小的目标区域。根据毛拢哗等人的研究结果[10]，选图比取为 $1 \%$ ，所得到如图4所示的高分辨率图像和三维灰度分布图。这一结果与毛拢哗所得结果一致。

![](images/0e52dcfdd2c87b514efc13315b5525ce314ec4f7f5822afc34af0905a644299f.jpg)

(a）二维灰度图 (b)三维灰度分布图 (a) 2D gray image (b) 3D gray distribution map

# 3.2幸运成像算法在FPGA上的实验验证

硬件平台是以Xilinx 公司 Spartan-6系列的XC6SLX16芯片为核心的开发板。基于FPGA上实现的幸运成像算法设计的验证，采用 $1 \%$ 的选图比，即随机的1000帧选10帧，执行与MATLAB相同幸运成像的算法处理，然后用ChipScope捕捉最终结果图中最大灰度值周围部分像素数据值，得到了如图5(a)图所示的经FPGA实现的幸运成像算法处理所得的高分辨率图像部分像素数据值，并与如图5(b)图所示的经MATLAB实现的幸运成像算法处理所得的高分辨率图像的相同部分像素值做对比。

ApplySetings andArmTrigger(XC6SLX16) UNIT:0 MylLAO (ILA) 叫区 Bus/Signal X 。 8 1 2 31 41 51 61 7 8 9 10 11 12 13 14 15 -dina4 3869 3869 3869 4373 6436 4615 4261 3920 3925 3785 3706 3697 3796 3879 3877 3679 3655 3485 ru4_addr_r 2013 2013 2013X2014 2015 20162017 2018 2019 2020 2021 20222023 2024 20252026 2027 2028

# a) FPGA处理的结果

# (a）Results of FPGA processing

![](images/bfd363e435cbfb40380cee42e688ab753566c80023c2ff68081f434db961304f.jpg)  
Fig.4High-resolution imageobtained at $1 \%$ selection rate   
图5分别用FPGA与MATLAB处理所得图像像素数值  
Fig.5Image pixel values processed by FPGA and MATLAB respectively

通过图5可知，经FPGA上实现的幸运成像算法处理所得图像的最终像素数据与在MATLAB上做同样算法处理所得图像像素数据完全相同。

从处理效果上来看，最终得到的高分辨率图像像素值较小，直接通过显示器显示图像时，无论在MATLAB上还是FPGA上做算法处理所得的高分辨率图像都比较模糊，所以，在FPGA和MATLAB上均对算法处理所得的高分辨率图像做了相同的灰度变换处理—一锐化或图像增强，将最终得到的高分辨率图像中感兴趣的目标或区域突出出来，分别得到了如图6(a)图、6(b)图所示的最终高分辨率图像。

![](images/03465546126b076b5fdc1d2e0531d561ef35992932bf218eac14e0168e75cca6.jpg)  
图4 $1 \%$ 选图比下所得的高分辨率图像  
图6基于FPGA和MATLAB实现的幸运成像算法处理所得的高分辨率图像

Fig. 6 High-resolution images Obtained by lucky imaging algorithm based on the FPGA and the MATLAI

图6(a)是经FPGA上实现的幸运成像算法处理所得的高分辨率图像以 $1 0 2 4 \times 7 6 8$ 的分辨率在XGA显示器上显示并通过手机拍摄得到的，在此采用手机拍摄获得，是因为本系统实现所采用的FPGA开发板是一个独立的外部系统，它是脱离PC机单独工作的，所以基于FPGA硬件实现的幸运成像算法处理后所得的高分辨率图像要通过单独的XGA显示器进行显示，因此它与PC机上MATLAB所得高分辨率结果图获取方式不同，它不能像

MATLAB一样直接进行图像截屏，而只能采用外部的图像采集设备进行图像获取，所以经FPGA上实现的幸运成像算法处理所得的高分辨率图像在本文中采用手机拍摄得到。而图6(b)经MATLAB处理后显示的最终高分辨率图像是以 $1 2 8 0 \times 7 6 8$ 的WXGA分辨率显示的。由于两图的显示器分辨率不同导致纵横比不同，导致相同图像在显示上稍有差异。此外，图6(a)是手机拍摄获得的，由于手机拍摄角度及分辨率的不同所以导致图像有些许变化。不过，仍然可看出这两幅图像是基本相同的，这说明经FPGA上实现的幸运成像算法处理后的结果与经MATLAB实现的幸运成像算法处理后的结果一致，从而说明基于FPGA实现的幸运成像算法设计正确。

综上所述，无论是从最终高分辨率图像中的像素数据值对比来看，还是从灰度变换后的直观显示出来最终高分辨率图像对比来看，都说明了基于FPGA实现的幸运成像算法设计与实现的正确性。

# 3.3FPGA上实现幸运成像算法的优势

FPGA的并行性和灵活性是其最大的优势，因此相较于传统的CPU，FPGA对同样算法的处理速度肯定快。但对于所研究的幸运成像算法来说，具体快多少，必须通过实验来说明。为此，分别在FPGA和CPU+MATLAB上对相同幸运算法的运算速度进行了测试。实验过程中，统计1000帧图像的处理时间，选图比采用 $1 \%$ 。FPGA及CPU $^ { + }$ MATLAB平台上均采用2.1节中介绍的算法进行实现。由此得到了不同平台下相同算法的平均运行时间：对于FPGA是2.45s，对于CPU $^ +$ MATLAB是46.93s；运行所得结果(高分辨率图像)分别如图6(a)、6(b)图所示。显然，相同的算法在不同的平台处理下，得到相同的高分辨率图像，FPGA平台上算法处理速度比CPU $^ { + }$ MATLAB平台上算法处理速度快约19倍。如果采用更先进的FPGA器件，速度还将加快。

不过受制于SD卡的速度，总体运行时间并没有明显的优势。目前，我们正在设计基于USB3 和千兆以太网的高速数据接口，以加速整个幸运成像处理的速度。另外，采用处理能力更强、逻辑资源更多的FPGA器件，可以更多地引入并行计算、减少串行处理过程，充分发挥FPGA硬件加速的优势。

# 4结论

本文首先简述了幸运算法的基本思想及处理流程，根据所用FPGA的硬件资源，用Verilog HDL设计了幸运成像算法的选图、配准、叠加等关键模块，详细介绍了这些模块的实现方案，并在FPGA开发板上实现了这一幸运成像系统。然后，通过将FPGA处理的结果与PC上用MATLAB处理得到的结果进行对比，证明了此系统设计和实现过程的正确性。最后，通过对FPGA与CPU+MATLAB平台下实现相同算法所需的处理时间的对比分析，说明了FPGA在处理速度上快19倍的优势。虽然本设计方案还有一些可以改进之处，但就幸运成像算法在FPGA开发板上的具体实现，为构建实时化的高速幸运成像系统探索了一种可行的技术方法。

# 致谢

中国科学院云南天文台张西亮、季凯帆、金振宇为本研究工作提供了原始天文图像，特此致谢。

# 参考文献：

[1] Oscoz A., Rebolo R., Lopez R., et al. FastCam: a new lucky imaging instrument for mediumsized telescopes,Proc.Of SPIE,2008,7014: 701447.

[2] Mackay C.D., High-Efficiency Lucky Imaging[J], MNRAS,2013, 432(1),702-710.   
[3]胡泊,李彬华.低温下EMCCD电子倍增模型[J].电子学报,2013,41(9):1826-1830. Hu B.,Li B.. Electron Multiplication Model of EMCCD in Low Temperature[J].Acta Electronica Sinica,2013,41(9):1826-1830.   
[4] Law N.M., Hodgkin S.T., Mackay C.D.. The LuckyCam survey for very low mass binaries - II. 13 new M4.5-M6.0 binaries, MNRAS,2008, 384(1): 150-160.   
[5] Woller M., Bandner W.,A Lucky Imaging search for stellar sources near 74 transit hosts, 2015,A&A, 579,A129.   
[6] Treece B. CPU or FPGA for image processing: Which is best? [J], Vision Systems Design, 2017, 22(8): 23-24.   
[7]印琪骏,朱亮,等.基于高性能芯片的射电天文厘米-分米波谱线观测方法[J].天文研究与 技术,2017,14(1): 103-109. Yin Q.， Zhu L.， et al. A New Method to Observe Radio Astronomy Signal: CentimeterDecimeter Spectral Line— —Based on High Performance Integrated Circuit.Astronomical Research & Technology, 2017,14(1): 103-109.   
[8] Piqueras J, Rodriguez-Ramos L, Martin Y, et al. FastCam: Real-Time Implementation of the Lucky Imaging Technique using FPGA[C]. Programmable Logic,2008, Southern Conference on. IEEE,2008:155-160.   
[9] Jackson C R. Real time mitigation of atmospheric turbulence in long distance imaging using the lucky region fusion algorithm with FPGA and GPU hardware acceleration[D]. University of Delaware,2015.   
[10]毛拢哗，李彬华，张西亮，季凯帆，金振宇.基于 $2 \mathrm { m }$ 级大口径望远镜的幸运成像算法 的实验研究[J].光学技术，2018，44(5)（待刊）. Mao L., Li B.， Zhang X.， Ji K.， Jin Zh.. Experimental investigation of lucky imaging algorithm based on $2 . 4 \mathrm { m }$ astronomical telescope [J]. Opt Techn, 2018, 44(5） （In press）.

# Implementation of Lucky Imaging Algorithm Based on FPGA

Zhao Panzi, Li Binhua, Mao Longhau, Tao Yong (Faculty of information engineering and automation, Kunming University of Science and Technology, Kunming, Yunnan 650051, China)

ABSTRACT: Lucky imaging is a kind of high-resolution image reconstruction techniques used to eliminate the influence of atmospheric turbulence on astronomical images.Its algorithm is usually implemented on the CPU-based platform,and cannot meet the requirement of real-time highresolution imaging. Taking advantages of FPGA parallel processing, this paper presents a new lucky imaging algorithm based on FPGA,and builds an experimental system which uses FPGA to complete all the lucky imaging processes of the image selection,registration, stacking. The obtained image reconstructed by the FPGA system is exactly the same with the image processed by the traditional CPU platform. Nevertheless,it is important that the processing speed of the system is 19 times faster than that of the CPU platform.The implementation of the algorithm on FPGA provides us with a feasible scheme to make lucky imaging technology real-time or quasi real-time.

Keywords: Image processing; High-resolution image reconstruction; Lucky imaging; FPGA