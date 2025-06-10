# 应用于射电天文的高效实时管道数据流传输与处理技术

张萌"²，张海龙1,2.3,4\*，王杰1,2,4，李健¹，冶鑫晨4，王万琼¹，李嘉¹，王博群²，张亚州12(1．中国科学院新疆天文台，新疆 乌鲁木齐，830011；2．中国科学院大学，北京，100049;中国科学院射电天文重点实验室，江苏 南京 210008；4.国家天文科学数据中心，北京，100101)

摘要：针对超宽带及多波束接收系统海量天文信号实时高效传输与处理问题，对基于FPGA+GPU的主流终端设备软件系统进行了测试分析，超宽带接收设备要求终端系统软件能够在更宽带宽，更高时间、频率分辨率条件下，实现实时数据流传输与处理。结合大口径射电观测设备未来发展方向提出了利用高速并行环形缓冲区实现数据流缓存、基于GPU集群实现数据流实时处理、基于BeeGFS实现分布式并行数据存储，模块化构建射电天文信号传输管道软件的设计思路。

关键词：数据传输与处理；射电天文；实时；FPGA+GPU中图分类号：P161.4文献标识码：A 文章编号：

# 0引言

多波束和PAF 接收技术的发展使得天文观测设备获取数据的能力不断提升，射电天文观测数据止在以一种实时、海量、持续的模式增长，终端系统中海量大文信号的高效传输、实时处理，需要异构的分布式计算与存储平台作为支撑，数据传输过程中首先将接收到的信号进行数字化,实现通道划分、RFI消减等预处理,这些处理可在ROACH[1]、SNAP'、RFSoC[2]等系列开发板卡上执行。硬件板卡与服务器平台通过高速网络连接，将数据打包并通过网络传输至GPU 服务器进行复杂算法处理。基于FPGA+GPU 的混合架构平台对软件性能提出了更高要求，高速实时传输天文数据包时需要考虑高IO 环境下的网络数据包丢失问题，Linux 内核在处理宽带网络流量时有很大的开销，由于网络协议是UDP，系统必须处理丢失、无序和重复的数据包，否则会造成相位信息缺失，针对脉冲星数据，丢包可对脉冲星的周期预测和折叠等产生严重影响。实现CPU与GPU之间数据高速流转时，GPU 高效实时数据处理阶段，CPU与GPU之间通信速率可能会造成的性能瓶颈，也是需要考虑并解决的问题。

射电天文数字终端系统中可实现数据包高速率实时传输与预处理的程序称为管道[3]。管道是一种编程实现，数据被链式的连接在一起，全部同时在其内部流动。管道包含多个处理单元，每个单元执行特定任务，最基础和主要的功能是提供缓存模块，暂时存储数据，实现数据的实时流转。应用于射电天文异构终端系统的管道数据传输主要包括三个阶段，数据接收阶段、基于CPU/GPU的处理阶段、数据输出阶段，通过缓冲模块实现从数据接收到写入磁盘流程中的高效传输，通过调用不同阶段的程序模块实现数据流传输过程中的实时处理。

文章研究并分析了可部署在射电望远镜终端系统上的数据管道，提出了基于FPGA+GPU 的动态、高性能实现海量射电天文数据流实时传输、处理和监控的管道设计思路，为未来新疆110米射电望远镜（QTT）[4开发定制多功能实时数据流传输与处理管道软件提供参考。

# 1现有射电天文数据流管道软件

针对射电天文数据的实时高速传输，国外已取得了系列研究成果，提供了开源CPU/GPU数据流管道软件，包括GUPPI_daq²、PSRDADA³、Hashpipe、Bifrost、Kotekan4、Pelican5、Cobalt，国内相关研究现正处于起步阶段。

GUPPI_daq 是GUPPI数据采集子系统，通俗灵活、使用简单，已有十多年的历史;PSRDADA和Hashpipe均为高吞吐量流数据处理而设计，最初分别应用于Parkes[5]和GBT;Bifrost 是用于快速管道开发的开源软件框架，专门为射电天文实时数据流处理而设计，用于LWA[后端；Kotekan 作为CHIME高度优化的流数据处理框架，更注重效率和吞吐量；Pelican 提供了高度抽象的应用程序接口，为静态、准实时处理目的而设计；Cobalt 管理通过网络和GPU 的数据流，主要应用于LOFAR 波束合成。

# 1.1 GUPPI_daq

应用于GBT 的 GUPPI_daq，是脉冲星数字终端 GUPPI 的数据采集软件，GUPPI_daq实现了数据流实时接收和处理，并以PSRFITS 格式记录文件，实时处理选项包括基础模式、

折叠模式和子带模式。

GUPPI基于CASPERFPGA板卡处理800MHz带宽、8bit量化数据，在10Gb以太网环境下封装成UDP 数据包发送，由GUPPI_daq 负责接收，并将数据保存至磁盘上。传输过程中实现与控制子系统交互，提供人机交互的软件界面，并记录监控参数，保存到输出文件中。

GUPPI_daq 使用多线程模式工作，线程之间通过基于共享内存的环形缓冲区传输数据。在基础模式下，GUPPI_daq 只使用两个处理线程和一个数据缓冲区，由网络处理线程负责接收FPGA生成的UDP数据包，通过检查自定义的序号来判断数据包是否丢失，将收到的数据保存在环形缓冲区内，丢弃的数据填充为零，同时从状态缓冲区读取头信息，将其复制到数据块头中。写盘处理线程读取已写满的缓冲区并解析数据块头信息，以PSRFITS 格式保存在磁盘上。

高速率运行时，GUPPI_daq 存在磁盘写入速度的限制问题。通过高速以太网接收数据时，800MB/s 数据接收速率下，出现了少量数据丢包[9]。

# 1.2 Hashpipe

Hashpipe 是早期GUPPI_daq 的衍生,最初作为NRAO VEGAS[10]的高效共享管道引擎,由 David Macmahon改写，可用于FX 相关器、波束合成器、脉冲星观测、FRB、SETI，亦可应用于我国FAST、“天籁”项目[]。

Hashpipe 设置共享内存段和信号量机制等功能，在运行时基于命令行参数动态构建管道，整体结构如图1所示，采用模块化架构设计，蓝色部分表示插件，Hashpipe 插件是一个共享库，定义了应用程序特定的线程模块、共享数据缓冲区等功能模块，并且插件允许用户创建，以便在Hashpipe 运行时中调用；红色部分表示可执行文件，在Hashpipe 运行时动态调用已定义插件。

![](images/ba25c4d160a82dc8c0c2fb4dd1aca9a45d7a4955e6ab3446560f7edadf977bc0.jpg)  
图1Hashpipe 整体框架  
Figure1Hashpipe overall framework

Hashpipe核心是灵活的环形缓冲区，模拟连续内存块，并实现了数据在多个线程之间的流转和共享，利用CPU控制启动和关闭等操作，通过环形缓冲区暂存并传递UDP数据包，保证数据快速捕获并按正确顺序分发。

Hashpipe将任务传输到单独的线程中，每个线程之间共享内存缓冲区，并通过信号量机制控制任务实现线程间互斥。定义数据接收线程、处理线程、输出线程3个线程，各个线程实现各自的任务。数据接收线程net_thread，接收来自计算机万兆网卡的高速网络数据包，根据数据包格式提取文件头和有效数据并解析包头，来自FPGA的数据包都有时间戳，如果无序到达，可以重新排列为适当的时间序列，并将数据写入第一个输入数据缓冲区，一旦连续的数据块写满，该块将交由下一个线程处理[12]；处理线程 gpu_thread 从输入数据缓冲区获取数据传输至GPU执行复杂计算，然后将结果写入输出数据缓冲区；输出线程output_thread 从输出数据缓冲区获取数据，将其写入文件存储在磁盘上。通过定义监控线程监听来自FPGA的UDP 数据包，通过转置线程重新格式化数据，使时间样本在内存中正确对齐。

后端由 $\mathrm { C / C + + }$ 编写，头文件中定义多个结构体变量以便调用，定义数据缓冲区hashpipe_databuf，包含需传输的数据类型、缓冲区空间的大小、缓冲区ID、数据存储块数、块 ID 等基本信息；hashpipe_thread_desc 结构用于存储描述 Hashpipe 线程的元数据；hashpipe_udp_params 结构体变量，用于保存网络连接参数，包括端口号、IP、数据包的大小等信息。hashpipe_clean_shmemO函数用来清除状态缓冲区占用；hashpipe_status_unlock_safe()、hashpipe_status_lock_safe()函数用于状态缓冲区的线程安全锁或解锁，确保状态缓冲区处于锁定状态。借助Hashpipe已有函数基本满足了数据传输需要，可根据实际需求实现调用。

界面监控采用David Macmahon 编写的 ruby 程序 rb-Hashpipe，作为Hashpipe 的可视化前端可以展示数据包接收、线程状态、缓冲区状态等信息，在更高级别将管道抽象以提供简洁和直观的界面监控数据。Hashpipe及rb-Hashpipe 均可部署在服务器平台，环境配置主要步骤如下：

（1）更新GNU系列工具到最新版本提供Hashpipe 编译环境;  
（2）安装Ruby管理器rvm；  
（3）使用RubyGems更新所需库文件;  
（4）获取Hashpipe 版本信息并实现安装；  
（5）配置 gnome 终端在 shell下启动。  
实现数据传输状态监控界面如图2所示。

![](images/c53e6658b2fceceec37c340305a3f633a5b599bc069c71f37d0386864489eb1a.jpg)  
图2数据传输监控界面  
Figure 2Data transmission monitoring interface

# 1.3PSRDADA

PSRDADA由澳大利亚斯威本科技大学开发维护，支持脉冲星信号分布式采集和数据分析，主要运用于脉冲星基带数据记录和处理，管理从ADC 信号采样到GPU 集群数据分析整个过程的数据流。PSRDADA 可实现 APSR、BPSR、CASPSR 基带记录数据分发管理和监控,现阶段主要应用于澳大利亚Parkes 的ASPSR、BPSR、CASPSR、HIPSR[13],欧洲PuMa-II等射电望远镜的终端系统'。

在基础层次来看，PSRDADA是一个灵活且易管理的环形缓冲区，其核心功能是在环形缓冲区之间传递数据流。每个缓冲区划分为描述文件信息的文件头存储块，以及多个存储数据的子块，接收到数据时按顺序写入子块，当一个子块被填满时，标志位被触发，表示子块中的数据可以读取。利用环形缓冲区实现对数据集进行出队和入队，多个数据集可以利用多线程并行在多个环形缓冲区排队，主要通过共享内存、信号量机制进行线程之间互斥通信。在高级别配置来看，可在集群中各节点启动PSRDADA 配置，通过可视化界面监控相关流程，管理数据的传输和归档。

PSRDADA基于模块化设计实现，包括用于执行特定任务的独立进程，整齐分离数据传输、命令、控制指令、数据分析等不同操作；创建环形缓冲区，实现进程之间数据传输；配置文件、脚本等，完成分布式工作流程中各种基础配置；基于web 的用户接口，提供基于web 浏览器的监控界面，并可通过gridbus发送到远程计算设备实现远程监控。

PSRDADA基于C 语言实现了针对 APSR、BPSR、CASPSR、PUMA2不同设备的相应开发，通过多命令行执行，dada_db 可以创建或删除一个缓冲区，dada_dbmonitor 监控已开辟的缓冲区，dada_dbdisk 命令实现从缓冲区数据写入本地磁盘，dada_header 获取数据文件头信息，dada_dbcopydb、dada_dbdisk、dada_diskdb 实现缓冲区与缓冲区及缓冲区与磁盘间数据拷贝等。

PSRDADA配置与基本使用步骤如下：

（1）安装或更新PSRDADA 需要的GNU工具autoconf（2.59及以上版本），automake（1.9.3及以上版本)，libtool（1.5.8及以上版本）， $\mathrm { m } 4$ （1.4及以上版本）；

（2）获取dada格式的数据；  
（3）创建特定key 值的环形缓冲区：\$dada_db-kkey_value;  
（4）数据写入环形缓冲区：\$dada_diskdb-k key_value-f filename.dada;  
（5）从环形缓冲区读出数据：\$dada_dbdisk-D.-kkey_value -s;  
（6）实现数据读写过程中的状态监控：\$dada_dbmonitor-kkey_value;  
（7）删除特定key 值的环形缓冲区：\$dada_db-k key_value -d。

缓冲区创建及数据传输情况如图3所示，开辟共享内存键为100的缓冲区结构，包括4个大小为 524288bytes 的数据存储缓冲区，总容量为2MB，8个大小为4096bytes 的文件头存储缓冲区，总容量为32KB。dada_dbmonitor命令打开监控界面，实现对文件头和数据缓冲区读写状态监控。

zhangmeng@ubuntu:\~\$ dada_db -k 100   
Created DADA data block with nbufs=4 bufsz=524288 nread=1   
Created DADA header block with nhdrs = 8， hdrsz = 4096 bytes，nread=1   
zhangmeng@ubuntu:\~\$ dada_dbmonitor -k 100 0 0 4 0 4 ®   
HEADER BLOCK: 8 0 0 2 65 64   
Numberofbuffers:8 8 。 O 3 81 81   
Buffer size: 4096 8 0 0 3 99 99   
Total buffermemory:32 KB 8 0 2 113 112   
DATA BLOCK: 8 0 3 131 131   
Numberofreaders:1 8 0 2 145 144   
Numberofbuffers:4 8 0 0 171 168   
Buffer size:524288 8 0 G 3 183 183   
Totalbuffer memory:2 MB 88 。。 。。 23 213 217   
8 0 0 2 273 272   
HEADER DATA 8 0 0 2 301 300   
FRE FUL CLR W R FRE FUL CLR W R 8 0 0 3 323 323   
7 1 0 1 0 0 4 0 4 0 8 0 4 0 3 345 345   
7 1 0 1 0 0 4 0 4 0 8 0 0 3 365 365

# 1.4 Bifrost

Bifrost专门为射电天文数字信号处理而设计，实现流数据处理高性能管道的快速开发，用于CPU与GPU之间数据高效传输。现阶段Bifrost用于处理LWA的数据，实现了在波束合成、相关器上的应用[14]。

Bifrost利用Python 实现了高级管道接口，可用于数据传输；利用 $\mathrm { C } { + } { + }$ 实现了支持GPU的高性能后端，包括一系列与天文数据处理相关的高性能数据结构和算法，为干涉测量、脉冲星消色散、计时及瞬态信号搜寻等应用而设计的库函数，用于CPU 和GPU上数据计算与处理[15]。

其中接口和函数都被称为块，通过灵活的环形缓冲区可以同时实现多个块之间通信，同时执行多线程，使得块可以异步操作。有三种类型的数据块：tasks，从环中读取数据，并实现数据转换，将结果写入到输出环形缓冲区；source，生成数据的块，从文件或以太网数据流的管道外获取数据，将数据写入输出缓冲区；sink，可以直接从输入环形缓冲区读取数据并绘制数据的块，或将其写入文件。

Bifrost 安装步骤简洁，适合快速部署，安装完成后，通过 import bifrost 实现模块调用。例如bifrost.pipeline 处理管道构建，首先自动创建环形缓冲区，并通过这些环形缓冲器构建有向图，为用户提供高级视图，pipeline.run 语句执行管道，为每个块创建一个线程；通过bifrost.blocks 加载功能块，调用 FFT、FDMT、量化、转置等实现数据处理；网络相关模块bifrost.udp，用于捕获UDP数据包，可统计并分析包传输信息。如果数据流传输过程中，需

要一些中间操作，用户可自定义模块

以wav格式的声音文件为例，Bifrost执行步骤一般为，读取wav文件到环形缓冲区;使用GPUFFT 实现数据信道化等操作；将filterbank文件写入磁盘。

（1）读取.wav格式的文件;  
（2）将原始数据拷贝到GPU;  
（3）将时间轴分割成小块，对新生成的小块执行FFT;  
（4）取这些FFT模的平方；  
（5）将数据转置为sigproc 兼容的格式，进行标准化；  
（6）将数据拷贝到CPU;  
（7）将数据转换为整数型，并将数据以filterbank存储。

# 1.5 Kotekan

Kotekan[16]是 Andre Recnik 使用 $\mathrm { C / C + + }$ 组合开发的软件框架，主要应用于射电天文望远镜数据传输，最早为CHIME 后端应用开发，旨在实现更高的效率和吞吐量。

Kotekan 管道是模块化的，由一系列对数据执行不同操作的单元组成，实现了实时管理X 引擎上数据流，包括接收来自F引擎的UDP 数据包，GPU 结点内数据流实时处理及结果存储。核心结构是FIFO环形缓冲区，通过系统内存中环形缓冲区，实现了CPU与AMD GPU之间通信，及传输到GPU 进行处理之前数据检查和暂存[17]。

Kotekan 创建网络线程、GPU 线程、GPU回调线程、GPU后处理线程和输出线程，每个线程都与一个或多个环形缓冲区对象的接口相关联，接收到的数据均通过环形缓冲区暂存，实现边读边写，这些线程和缓冲区形成了如图4所示的数据路径，管道可以多线程并行的产生多个结果数据集[18]。

![](images/89a4adfb06a92c953a2fd8bf8f2ef0e431abc36608608a7f7f22324556f9406a.jpg)  
图4Kotekan中数据流   
Figure4DataflowinKotekan

缓冲数据由Kotekan::stage 处理模块写入和读取，从网络或外部设备获取数据，通过数据处理算法实现数据操作，最后将处理后的数据通过网络传输或存储于本地。

# 1.6 Pelican

Pelican[是由牛津电子中心开发的实时数据流处理框架，具备高效、模块化、轻量级、可校准的特点，主要应用于LOFAR 和 BEST-II，通过GPU 服务器对数据进行并行处理。Pelican 提供了高度抽象的API，适合用于静态、准实时处理。

Pelican用 $\mathrm { C } { + } { + }$ 实现了可重用的模块化组件，分离了数据的获取和处理，具有灵活性和通用性，具备读取UDP 数据的机制，将数据流传递给各计算服务器，完成数据缓冲、处理和最后文件写入，可对望远镜接收数据进行实时处理，也可用于任何需要处理传入数据流的

应用程序[20]

Pelican 可用于脉冲星搜寻的数据预处理，SKA早期计划使用Pelican 处理非成图的基于GPU 实时射电脉冲检测[21]，流程如图5所示，首先通过软件服务器读取UDP数据，去除窄带频谱干扰的峰值，实现GPU 中进一步窄带划分，完成复杂数据到功率数据的转换，将数据传输至GPU 处理模块执行分散搜索算法[22]。

Pelican server Collecting the data   
Pelican module   
Flagging for interference   
Pelicanmodule Channelisation   
Pelicanmodule   
Voltage to Power(Stokes)   
Pelican module dis persion search

短时间内成像导致非常大的相关器输出速率，为了实现数据传输速率并产生更新的校准系数，需对输出数据流进行实时处理。Pelican 可用于实现射电望远镜数据转换成科学图像之前的数据校准和成像方程求解。Pelican 实现科学成像的框架如图6所示，接收来自ROACH2的子带数据，通过实时更新相关器的相位和振幅系数，提供初始校准，然后基于GPU 的2D-FFT生成脏图像，洁化后执行基于特定步长的图像差分比较，阈值检测器用来发现瞬态事件，最后堆叠模块用来形成一个高动态范围的图像12。

![](images/74cbb23cf5345b439bd0def9b9585b246110097eff16da73008841fc222b77e8.jpg)  
图6Pelican实现成像框架  
Figure 6 Pelican realized imaging framework   
图7Cobalt数据流示意图  
Figure 7 Cobalt data flow

# 1.7 Cobalt

Cobalt 是基于GPU 设计与开发的 LOFAR 望远镜软件相关器和波束形成器[23]，软件部分实现了数据管道，用于管理通过网络和CPU、GPU的数据流，并完成数据存储。

图7为数据流从外部系统到Cobalt内部数据流示意图，接收数据存入输入缓冲区，完成子带处理后进行存储，模块间以all-to-all模式进行通信。

水 Subband XInput Buffering Storage ClusterProcessing

Cobalt 的软件由几个交互子系统组成，管理来自网络的数据流，实现高速率、可持续数据传输，并持久性存储数据；进行控制、监控、记录日志和元数据。图8显示了Cobalt 的组件、依赖关系和数据流,Cobalt 处理大量独立的数据流,每个 AntennaFieldInput接收10GbE端口的UDP数据包，并将有效数据转发到TransposeSender，通过环形缓冲区移动整数倍执行延迟补偿。这些数据流在没有相互依赖的情况下结合MPI实现并行处理，GPU上的信号处理管道GPUpipeline 包含 TransposeReceiver 组件,传输子带数据,与MPI_Isend和MPI_Irecv非阻塞发送和接收相结合传输相关或波束数据。输出组件接收GPU 子带数据，最终使用casacore 以 MeasurementSet 或 HDF5 格式存储[24]。

![](images/2c51fe42c7b5ae5a6b4df2b1733747a861288e3d4271fcddd69b899ce4ac2511.jpg)  
图8Cobalt组件依赖关系和数据流  
Figure 8 Cobalt component dependencies and data flow

Cobalt 可以处理离线任务，包括自动标记、校准、平均、脉冲星数据相干消色散和动态光谱产生以及脉冲星数据在线折叠和搜索。Cobalt具备可扩展性，如子阵列并行观测、中断响应以及其他的观测模式。在网络带宽和计算能力方面，提供了显著的额外容量，效率有显著的提高，例如低波段天线和高波段天线的并行观测。一般来说相关器只能处理单个项目的数据，Cobalt 因拥有巨大的计算和吞吐能力可以同时处理多个项目数据1。

现已有更新版本Cobalt2.0，具备更好的灵活性和吞吐量，接收数据量速率超过1TB/s，更大限度利用GPU的优势，实现高性能计算和数据实时处理。

# 2面临的问题

现阶段数据流管道软件面临的重点与难点：

（1）现有射电天文数据流管道软件均针对特定观测设备设计，为满足特定需求开发，并不适用于所有类型的观测设备及观测模式。针对具体观测设备，应根据各观测设备的接收系统需求来实现相应的软件功能，部分软件系统虽然可移植到不同的观测设备终端系统，使用时并不需要其全部功能，需要深入研究其底层代码，完成二次开发及调试，开发成本高、难度大。

（2）已有大型射电望远镜终端系统，多采用基于XilinxFPGA的ROACH系列、SNAP系列硬件板卡，近几年推出了集成度更高的RFSoC，可提供高速以太网数据传输接口，对服务器端数据流实时接收能力提出了更高的要求。部署在服务器端的管道需要满足基于RFSoC平台更高带宽的数据接收需求，提升数据传输效率。

（3）数据实时高效传输与处理能力是管道软件性能提升方向，数据处理平台多采用GPU 集群实现大规模数据处理，然而数据分发与收集并没有得到有效的处理，高效实现数据流在多GPU上的分发与汇总，将大大提高传输与计算效率。

（4）为满足多功能数字终端系统的数据处理要求，应形成一套配置灵活的系统软件，构建的管道软件应实现数据处理与分析所需算法，针对不同观测模式提供可调用的类库，满足多观测课题的需求。

# 3大口径射电望远镜数据流管道软件设计思路

应用于大口径射电望远镜数据流传输与处理的管道软件，作为多功能终端系统软件中重要的组成部分，将完成数据流获取、传输、管理与监控。高效捕获并暂存来自FPGA 的网络数据包，实现数据在CPU与GPU之间高速流转及相关处理，提供GPU 内部数据处理算法调用，实现原始数据格式到标准文件格式的转换及数据类型的匹配，最终数据高效写入磁盘存储。

# 3.1基于零拷贝和环形缓冲区的数据传输

QTT 多功能数字终端采用 $\mathrm { F P G A + G P U }$ 集群架构模式，如图9 所示[25]。RFSoC 实现数据采样和预处理，单块RFSoC 芯片可实现8通道，每通道最大采样速率 4.096GSPS，12bit采样，采样后每通道的数据量约为48Gbps,经过RFSoC预处理将采样数据划分成多个子带，利用 RFSoC 提供100Gb 的数据传输接口，通过高速以太网传输至GPU集群实现数据相关联进行数据预处理。

![](images/23859db5918b1ee6301799be5337d546ddec3ee4695a2f0876888b92e60e9a01.jpg)  
图9QTT终端系统框架  
Figure9TheblockdiagramofQTTbackendsystem

![](images/13f6a72f43c174aa0867fbef05fb844f9947ea3333c3f7303eff0fdfb0f2679b.jpg)  
图10 标准数据传输与零拷贝数据传输  
Figure 1O Standard data transfer and zero-copy data transfer

网络数据传输使用UDP协议，网卡缓冲区中数据通过Linux内核协议栈传输至用户应用程序，数据包在内核态与用户态之间拷贝，系统消耗大且存在传输瓶颈，为了有效降低系统资源占用，满足GPU 服务器端传输的低丢包率和低延迟，GPU服务器端可基于零拷贝技术实现高IO 环境下的高性能数据获取，对比如图10所示。管道软件实现基于零拷贝的数据传输模块，创建并行网络输入线程在用户态以轮询方式读取网卡缓冲区中数据包，实时写入动态创建的环形缓冲区，避免标准内核协议栈的处理，减少网卡到管道软件过程中的数据拷贝次数，以提高数据访问效率。

# 3.2基于GPU集群的数据实时处理

基于混合架构的QTT多功能终端系统计划实现脉冲星、暂现源、分子谱线、总功率、VLBI、基带数据等多种观测模式，GPU集群内部数据流如图10所示，FPGA预处理后的数据传输至GPU 集群实现数据处理，数据流经解码、RFI消减后，针对不同观测模式完成相应处理，并最终以VDIF、PSRDada或PSRFITS 等格式存储。

![](images/46ee802835be2c437afef74a09ab70b1436dd1b8dfe80bac2553089417c1bacb.jpg)  
图10QTT多功能数字终端GPU集群内部数据流  
Figure1O QTT multifunctional digital backend GPUcluster internal data flow

管道软件应提供GPU内部数据处理模块，并应充分整合天文学算法，实现解码、RFI识别、校准、折叠、标准格式输出等常用功能，实现到标准文件格式的转换及数据类型的匹配。基于Web 提供友好的访问界面，以模块化的方式提供更好的灵活性并支持扩展，提供用户自定义模块功能，允许用户根据实际需求调用模块或编写自定义模块。

针对QTT多功能数字终端数据流，管道软件数据传输过程的顶层结构如图11所示。网络线程捕获来自RFSoC的数据并存放至输入数据环形缓冲区，管道软件运行在多台GPU 服务器上，每台GPU 服务器接收一个频率通道子带，为实现GPU集群上多线程并行和分布式执行，高效及时运行和数据块转发，集群节点中结合MPI实现数据的分发和获取，采用 MPI提供的非阻塞消息接收与发送调用接口MPI_Isend、MPI_Irecv，实现计算和通信重叠进行，提高数据处理效率。GPU 集群处理后数据暂存于输出数据缓冲区，并通过并行输出线程传输至存储系统。

![](images/bcde9ca39495c051ff14b0ffe52c2049626eee60099c27eb3c6b6352d821066d.jpg)  
图11数据传输流程图  
Figure 11 Data transmission flowchart

# 3.3基于BeeGFS的数据存储

随着数据量的迅速增加，HPC 系统需要更复杂、更高效的方法管理与存储大量数据。通过部署分布式文件系统将数据分布到众多存储设备上，对数据进行分布式存储和管理，实现分布式读写。借助并行分布式文件系统 BeeGFS14构建更高效的数据存储后端，提高 I/O性能，实现高性能和可扩展性。

![](images/53943bd4697157caa1fb8173072c0d78950207baa45f8f8ae9d1a477bf0dcbbf.jpg)  
图12基于BeeGFS的数据存储系统  
Figure 12 Data storage system based on BeeGFS

基于BeeGFS 的数据存储系统整体框架如图12所示，GPU集群处理后的数据，进行整合后封装成特定的格式，通过构建并行输出管理线程同时传输一个或者多个数据流，相同格式的数据写入同一环形缓冲区，传输至文件存储系统，通过BeeGFS 提供的Client读写数据，利用多个独立I/O实现高并发读写。基于BeeGFS 分布式文件系统实现元数据分离，分别利用 MDS、OSS 的本地文件系统承载元数据和数据的存储，其中文件头中包含的日期时间、观测环境参数等观测信息，作为元数据信息的主要组成部分，存储于元数据服务器。MDS、OSS 以及Client 的扩展性使得基于BeeGFS数据存储系统能够满足大规模数据存储扩展需求。

# 4结语

射电天文望远镜数字终端系统越来越依赖实时处理来克服数据存储和分析的瓶颈，天文领域已经开发并研究了数据流处理管道，用以提高数据传输和处理的效率，简化天文学家数据处理代码开发难度。文章综述了现有射电天文数据传输管道软件，介绍了射电天文数据传输管道软件的结构、功能，并在GPU 服务器上进行了测试。在总结现有管道软件的基础上，给出了未来大口径射电望远镜多功能终端系统应根据实际观测需求设计数据传输管道的一般思路，未来多功能数字终端系统基于FPGA+GPU实现，应该向易升级、改造、灵活、可扩展的方向发展。

致谢：感谢国家自然科学基金(11873082,11803080,12003062)；中国科学院青年创新促进会；国家重点研发计划(2018YFA0404704)；天文财政专项；国家天文科学数据中心，中科院科学数据中心体系的资助。本论文得到中国虚拟天文台、国家天文科学数据中心、中科院科学数据中心体系提供的数据资源和技术支持。

# 5参考文献

[1]张萌,张海龙,王杰,李健,托乎提努尔.基于ROACH2 的数字终端实验平台搭建[J].天文研究与技术,2020,17(02):244-251. Zhang Meng,Zhang Hailong,Wang Jie,LiJian,Tohtonur.The Constructionof Digital Backend Experiment PlatformBasedon ROACH2[J].Astronomical Research & Technolog,2020,17(02):244-251.   
[2] FarleyB,Mcgrath J,Erdmann C.AnAl-Programmable16-nmRFSoC forDigital-RFCommunications[J].IEEE Micro,2018, 38(2):61-71.   
[3] Paine D,LeeCP.Producingdataproducing software: Developing aradio astronomyresearch infrastructure[C/0l4 IEEE0thI nternational Conference on e-Science.IEEE,2O14,1: 231-238.   
[4] Wang N. Xinjiang Qitai 110 m radio telescope[J].entia Sinica,2014,44(8):783.   
[5] 张海龙,王杰，王万琼,聂俊,冶鑫晨,朱艳,托乎提努尔.新疆天文台数据中心建设与应用[J].天文研究与技 术,2017,14(01):94-102. Zhang Hailong,Wang Jie,Wang Wanqiong,Nie Jun,Ye Xinchen,Zhu Yan,Tohtonur.ConstructionandAplicationof the Data Center in Xinjiang Astronomical Observatory[J].Astronomical Research & Technolog,2017,14(O1):94-102.   
[6] SrikanthS,NorrodR,KingL,etal.AovervieoftheGreenBankelescopeC/Antennas&ropagationSocietyItetioal Symposium. IEEE,2002.   
[7] 梅丽,苏彦,周建锋.极低频射电天文观测现状与未来发展[J].天文研究与技术,2018,15(02):127-139. Mei Li,Su Yan,Zhou Jianfeng.The HistoryandDevelopmentof The Low-FrequencyRadio Observation[J].Astronomical Research & Technolog,2018,15(02):127-139.   
[8] Bandura K, Adison GE,Amiri M,et al. Canadian hydrogen intensitymapping experiment (CHIME)pathfinder[J].Proceedings of SPIE - The International Society for Optical Engineering,2014,9145.   
[9] Duplain R,Ransom S,Demorest P,et al.LaunchingGUPPI:the GreenBank Ultimate PulsarProcessing Instrument[J].2008, 7019:70191D.   
[10]PrestageRM,BlossM,BrandtJ，etal.Theversatilegbtastronomicalspectrometer(vegas):Curentstatusandfuture plans[C]//2015 USNC-URSI Radio Science Meeting (Joint with AP-S Symposium). IEEE,2015: 294-294.   
[11]Chen-Hui NiuQun-Xiong Wang,DavidMacMahon,Feng-QuanWu,Xue-LeiCen,Ji-XiaLi,Hai-JunTanGuilumeSeeDan Werthimer,Xiao-Ping Zheng.The design and implementation of a ROACH2 $^ +$ GPU based correlator on the Tianlai dish array[J].Research in Astronomy and Astrophysics,2019,19(O7):135-144.   
[12]MacmahonDHE,PriceDC,LebofskyM,etal.TeBreakthroughListenSearchforIntellgentLife:AWidebandDataRecorder SystemfortheRobertC.ByrdGrenBankTelescopeJ].Publicationsof teAstronomicalSocietyof teacific,20l7,30(986): 044502.   
[13]PriceDC,Staveley-SmithL,Bailes M,etal.HPSR:ADigitalSignalProcesorfortheParkes21-cmMultibeamReceiver[J]. Jourmal of Astronomical Instrumentation, 2016,5.   
[14]Cranmer MD,Barsdell B R,Price DC,et al.Bifrost: a Python $/ \mathrm { C } + +$ Framework for High-Throughput Stream Processing in Astronomy[J]. Journal of Astronomical Instrumentation,2017.   
[15]Kaszyk K,Wagstaff H,Sink T,etal.Ful-systemsimulationof mobilecpu/gpuplatformsC/2019 IEE Interational Symposium on Performance Analysis of Systems and Software (ISPASS).IEEE,2O19: 68-78.   
[16]RecnikA,BanduraK,Denman N,etal.AnEficientReal-timeDataPipelinefortheCHIMEPathfinderRadioTelescope X-Engine[C]//015IEE26th Intemational ConferenceonAplication-spcific Systems,ArchitecturesandProcessors ASAP). IEEE,2015.   
[17]Pinsonneault Marote T.Towards precision measurementsof the Hubbleconstant with the Canadian Hydrogen Intensity Mapping Experiment[D]. University of British Columbia,2018.   
[18]Denman N,AmiriM,BanduraK,etal.AGPU-basedCorrelator X-engineImplementedonthe CHMEPathfinder[J].015.   
[19]MortB,DulwichF,WiliamsC,etal.Pelican:PipelineforExtensible,Lightweight ImagingandCAlibratioN[J].Astropyics Source Code Library, 2015.   
[20]KarastergioACheamangalmJ,AourWetal.Limitsonfastadiourstsat145MzwithEMS,real-teotare backend[J].Monthly Notices of the Royal Astronomical Society,2015,452(2): 1254-1262.   
[21]Trefethen AE.Extreme Computing: Challenges,Constraints and Opportunities[J].2010.   
[22]KaraStergiou A.SKA NON IMAGING PROCESSING CONCEPT DESCRIPTION: GPU PROCESSING FOR REAL-TIME ISO LATED RADIO PULSE DETE-CTION[J].2011.   
[23]BroekemaPC,MolJJD,NijboerR,etal.Cobalt:AGPU-basedcorelatorandbeamformer forLOFAR[J].Astronomyand computing,2018,23:180-192.   
[24]PrasadP,HuizingaFKooistraE,etal.TheAARTFAACal-skymonitor:Systemdesignandimplementation[J].Joualof Astronomical Instrumentation,2016,5(04): 1641008.   
[25]张海龙，张萌，聂俊,等．脉冲星数字终端技术综述[J]．中国科学:物理学,力学,天文学，2019(9):15-28. Zhang Hailong,Zhang Meng,Nie Jun,etal.Pulsar digitalbackend technologiesreview[J].SCIENTIA SINICAPhysica, Mechanica & Astronomica,2019(9):15-28.

# Efficient real-time data transmission and processing technologies applied to radio astronomy

Zhang Meng1,2，Zhang Hailong1,234，WangJie124，LiJian’，Ye Xinchen14，Wang Wanqiong，LiJiat, Wang Boqun1,2，Zhang Yazhou1.2 (1. Xinjiang Astronomical Observatory, Chinese Academy of Sciences, Urumqi 83o011, China ; 2.University of Chinese Academy of Sciences,Beijing 1Ooo49,China ; 3.Key Laboratory of Radio Astronomy,Chinese Academy of Sciences,Nanjing 21ooo8,China ; 4.National Astronomical Data Center,Beijing lOo101,China)

Abstract : Aiming at problems of massive signals real-time transmission and processing in ultra-wideband and multi-beam receiving systems,tested and analyzed the related software of the mainstream backend system based on $\mathrm { F P G A + G P U }$ ，the ultra-wide band receiving equipment requires the backend system software to be capable of wider bandwidth and higher time resolution and higher frequency resolution conditions,realized real-time data stream transmission and processing. Combined with the future development direction of large aperture radio observation equipment, it was proposed to use high-speed parallel ring buffers to achieve data stream caching, GPU clusters to achieve data stream real-time processing,and distributed parallel data storage based on BeeGFS,modular construction of data stream transmission pipelines software design ideas.

Key words: Data transmission and processing；Radio astronomy；Real-time； FPGA+GPU