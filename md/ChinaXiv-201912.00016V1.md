# 基于ROACH2的数字终端实验平台搭建

张萌1.2，张海龙 $^ { 1 , 2 , 3 ^ { \star } }$ ，王杰1，李健1，托乎提努尔1(1．中国科学院新疆天文台，新疆乌鲁木齐，830011;2.中国科学院大学，北京，100049；

3．中国科学院 射电天文重点实验室，南京210008)

摘要：面向天文信号实时处理需求，搭建了基于 ROACH2 的射电天文数字终端实验平台。利用MATLAB、Xilinx等开发环境进行仿真，取得了原始实验数据；利用CASPER硬件平台实现了信号控制和预处理，并通过高速以太网将数据包传输至计算服务器进行后处理。搭建的实验平台实现了仿真、编译、运行的完整流程，为天文信号实时处理研究提供了良好的实验环境。

关键字：数字终端；ROACH2；实验平台；CASPER中图分类号：P111.44 文献标识码：A 文章编号：

# 0引言

采用多波束及PAF1（Phased Array Feed）接收技术使射电观测获取的天文观测信号数据量成倍增长，观测数据需要实时处理来克服传输和存储速度的瓶颈。应用高速宽带数字终端[1进行信号的实时处理，可以满足未来海量数据实时处理的需求，当前数字终端系统主要包括对天文信号控制和预处理的可编程硬件平台和进行控制及复杂处理的高性能计算系统。

CASPER[2]（ Collaboration for Astronomy Signal ProcessingandElectronicsResearch）的硬件平台因其免费、开源、可重用，目前得到许多大型射电望远镜的数字终端平台使用。美国GBT（Green Bank Telescope）的脉冲星终端系统 GUPPIl3]( Green Bank UItimate Pulsar Processing Instrument)、Arecibo 使用的脉冲 星终端 PUPPl² (The Puerto Rico UItimate PulsarProcessing Instrument),以及澳大利亚 Parkes 的 CASPSR[4] (CASPER ParkesSwinburne Recorder)均采用 CASPER 早期的硬件系统 IBOB[5]（InterconnectBreak-out Board）和 BEE2[6]（Berkeley Emulation Engine）。美国 GBT 的VEGAS3，德国 Effelsberg 的 PSRIX[7]终端，以及澳大利亚 Parkes 的 BPSR[8](Berkeley Parkes Swinburne Recorder)采用了第一代 ROACH系统构建，利用多台ROACH进行通道划分,将来自IBOB和BEE2平台的信号合并到一个板中。我国贵州 FAST[9][10]、上海Tianma4均使用了 ROACH25构建终端系统，进行频率通道划分，完成高速流数据处理。

为进一步研究现有的数字终端系统，实现高速天文信号实时处理，需要构建稳定的实验平台，为高速天文信号实时处理研究提供良好的实验环境，由于CASPER的数字终端软硬件平台通用性和开源性，本文基于CASPER软硬件实现了实验平台的搭建，并对所搭建的实验环境进行了系统测试。

# 1硬件平台

CASPER 团组研发设计的许多设备都是基于Xilinx公司的FPGA[11芯片，通常典型的CASPER 信号处理平台都有一个或者两个ADC与其连接，进行信号采集和少量的预处理，然后通过网络链路将数据发送到其他FPGA 板或者CPUs、GPUs，进行复杂的信号处理。目前可用的CASPER支持的 FPGA 板有 IBOB、ROACH系列、SKARAB、SNAP系列。本文实验平台的搭建选用稳定且使用较广泛的CASPER硬件平台ROACH2，实验室实物如图1所示。

ROACH（Reconfigurable Open Architecture Computing Hardware）系列板卡是可重构开放式计算机硬件体系结构，是用于射电天文信号处理的独立可编程平台。ROACH2是ROACH系列的最新版本,使用XilinxVirtex-66系列FPGAs。保留了ROACH的优点，但在处理能力、I/O吞吐量和内存带宽方面提高了总体性能。它使用与ROACH相同的PowerPC 440EPx，但是增加了用于芯片内部测试的 JTAG7（ Joint Test Action Group）接口。

如图2所示，从结构上看ROACH2硬件平台主要被分成五个相互独立的子系统，包括FPGA子系统、处理器子系统、板卡管理子系统、测试调试子系统、信号存储子系统。核心部分是Virtex-6系列XC6VSX475TFPGA，用于信号处理；PowerPC440EPx独立处理器运行简易Linux系统提供控制功能；四个36$\times 2 M$ 的 QDR2（Quad Data Rate2）SRAMs，以及单个 72bit 的 DDR3 RDIMM（RegisteredDual In-lineMemoryModule）卡槽连接到FPGA，可用于数据计算与存储；两个ZDOK接口，用于连接ADC等设备，四个SFP $^ +$ ( Quad SFP+Mezzanineboard）端口，支持多达 $8 \times 1 0 \mathsf { G e }$ 的数据链路，能够将数据包向下一级高速输出。

![](images/ba442a06b63402ea583f8e627db270a58e16a01c39720e8a9c7ca4bfb47e1089.jpg)  
图1ROACH2实物图Fig.1The picture of ROACH2

![](images/ac7203a1a281cf1e611e0d29dff739acaa66502a5545d4636f4f8ed8bca64eb2.jpg)

# 2软件环境

CASPER工具包提供了一个用于CASPER硬件平台的设计环境。主要组件简称 MSSGE8（MATLAB/Simulink/System Generator/EDK），MSSGE 工具包是针对基于CASPER硬件平台的一个软件开发平台，它们整合在一起形成一个设计和开发的平台环境。这个开发环境早期是由伯克利无线电研究中心为BEE硬件平台设计开发的BEE_XPS工具包，后将这个开发环境升级扩展到可以通用于所有的CASPER硬件平台。开发环境提供了图形化的设计界面，使用Xilinx系统生成工具包，使得设计编译实现过程整体化。

MSSGE工具包的各个组件中，MATLAB为Simulink提供了一个可编写脚本的后端，所有脚本均可通过 MATLAB 实现。Simulink 既可作为 CASPERROACH2的系统模型的原理图绘图工具，也可作为一种高层次的可以用于信号处理系统设计的仿真环境。System Generator 可以用于 FPGA 编程实现，是Xilinx 公司的系统级设计工具,可以将其理解成一个转换工具，自动地将Simulink中设计的抽象模块映射成可靠的硬件实现[12]。System Generator在编译期间将Simulink 原理图转换为HDL代码（VHDL或Verilog），这大大简化了开发数字信号处理算法的设计过程。EDK（Embedded Development Kit）组件是用于FPGA的嵌入式开发，CASPER硬件的编译基于XilinxEDK，通过它能够将上一步生成的硬件描述语言的代码编译成比特流文件并转换成操作系统可执行的bof文件，EDK是ISE的扩展功能工具集合。

该实验平台软件可搭建在Ubuntu x64、RHEL、CentOSx64系统上。经过实际测试 MALTAB 服务包与 Xilinx 的 XSG、System Generator 存在版本兼容差异，须下载对应版本的MATLAB和Xilinx，以及相应MSSGE库。

本文以系统CentOS7，软件MATLAB2012b、Xilinx14.7为例进行说明，环境搭建流程如图3所示,在CentOS7上依次安装Xilinx14.7、MATLAB2012b。工具包需要两个库，即 DSP 块的CASPER 库和硬件支持块的 BEEXPS 库，现两个库已捆绑在一个mlib_devel 目录中，用户可以从github下载，需要注意的是在开发环境搭建过程中，应注意软件版本、安装路径与库文件存放路径的一致性。

在Xilinx14版本中删除了ROACH2依赖的部分模块，这些模块存在于EDK中，称为pcores（peripheral cores），因此需要将删除的部分复制到XPS_ROACH2_base/pcores 文件夹中进行更新。下载并安装完成后,编辑 startsg的默认路径为文件存放的真实路径。更改完成后，直接运行startsg，即可启动MATLAB，等待成功导入Xilinx库和CASPER库后即可进行设计工作。

安装操作系统 x安装软件 下载mlib_devel 更新pcores 更新xiiindevelMATLAB2012b MATLAB的地址

# 3实验分析

实验平台的软硬件系统搭建完成后，需要实例验证其可用性。本文利用CASPER平台提供的实例对所搭建的平台进行了测试。

实例测试实现了从平台软件设计到硬件执行的完整处理流程，如图4所示。使用 MATLAB 中的 Simulink 进行设计、仿真，使用casper_xps 编译文件，文件编译生成可执行文件后，将后缀名为bof的可执行文件上传到ROACH2平台的相应文件夹中，通过Python 脚本远程控制文件在 ROACH2上执行。

使用 上传bof文件利用Simulink 远程控制casper_xps 到ROACH2 显示输出进行仿真 编译 平台 可执行文件

首先在Simulink编译界面里进行图形化设计。创建新的仿真图形,添加Xilinx系统生成器和XSG核心配置块，然后按照描述的设计构架图，通过定位库基本元素选择需要的模块，并设置参数，搭建完整的顶层设计结构，本文以建立宽带频谱仪为例，其整体图形化程序如图5所示。在Simulink中建立架构图时主要应用三个库，CASPERXPS库，包括封装了硬件之间接口等的黄色块;CASPERDSP 库，包括实现输出DSP功能等的绿色块；Xilinx库，提供复用、延迟、添加等低级功能的蓝色块。

E 回m in_reg dz^2a→[ab] cnt_rst][cnt_rst] rst sync_gen] a2\~1nout dz\~1a gpio_outsim_out 面 cnt_rst Latency =2 [sync_gen] e++ + Z out_regsim_out Latency=1 Latency =1 led0_sync   
三 in_reg 2 acc_len] [cnt_rst] sync_cntr sync_cnt 1output [new_acc] \~u \~ gpioutsi 面 16777215sim_1 in_reg 2\~2q quant_gain] ++ 日 out_regsim_out   
XSG_core_config 1nint Latency =2 [nev gce acc.ut [adc_clip]> gpio.utsir 山 out sync_out dz^-1 [acc_len] acc_len   
sim_syc_period=167772160 Latency=1 [sync_gen] 4095 [cnt_rst] new_acc [new_ace] Constant2 acc_cntrl [sync_gen] dz\~1q sync sync_out 22 synsynz ut 四 z\~1q [new_acc] 1q 国 子 z\~poe1 1new.co eet poll_inl poll_outl £ x>>2 syncsyncout [new_acc]   
rsm. oil.i 002.001 douto 山 a\~1q pol1_in4poll_out4 in03 面 [quant_gain] gain dout1 Latency =1 din valid we sim_q outofrangeio Latency = 1 taps=4fe 盛 quanto 国 vacc1 odd   
□ sim_syncOutotrangeqo Guo o [adc_clip] Round (unbiased Even Values synco 贝贝贝贝 sync1   
□ Dsim_data_valid sync2 sync3 data_valid adc

在Simulink中的设计完成之后，可直接在其内部进行仿真，确保在编译之前没有错误，点击顶部工具栏中的执行按钮，即可实现仿真。如有错误则会弹出诊断窗口，可以单独处理，有些设计也可以查看示波器中的显示是否与设置一致以判断对错。

验证设计功能正确后，需将其编译成FPGA可以识别的代码。在MATLAB中输入指令casper_xps来启动编译器模块，这时将会弹出如图6所示的编译界面，所有选项保持默认，确保列出的设计是想要编译的，然后单击gcs返回最近选择的模块所在的系统路径，最后单击RunXPS开始编译。

![](images/5bb91da4e41258d009e0384261d6b96c57b12ba5eaf54345125faf6c5cd858a9.jpg)  
图6编译启动界面  
Fig.6 Compile startup interface

经过较长一段时间的等待，编译正确并且完成之后，将会弹出一个成功实现编译的对话框如图7所示。

![](images/c8fe0b1695a53f62878f7c0a58843c8e77f260cc9b92cded35450e53854d9d4b.jpg)  
图7编译通过图示  
Fig.7The diagram of successful compilation

编译通过之后会在右侧文件夹目录栏显示生成了多个文件，其中在bit_files文件夹中能够找到后缀名为bof的二进制文件，\*.bof文件即是可以在ROACH2上运行的文件。

设计、仿真、执行、编译等过程都在CASPER的软件开发平台上实现的，要在硬件平台ROACH2上执行下一步操作，需要将编译生成的bof文件上传到ROACH2平台相应文件夹中。经过多次尝试，针对bof文件上传，建议采用NFS（Network File System）方式，远程mount其它服务器相关目录到ROACH2平台相应目录，这样只需复制bof文件到服务器上即可实现bof文件上传。再远程控制将编译的可执行文件在ROACH2上运行，完成配置和通信并实现显示输出。

本文以建立2048 通道的频谱仪为例，使用BPSG49信号发生器产生800MHz 时钟信号，将时钟源连接到ADC上的cIk_i，并将ROACH2的时钟频率设置为200MHz，输入信号由ADC 数字化产生4个并行时间序列。利用 python控制频谱仪在ROACH2上执行，将其转换为频域信号，最终输出频谱。

实验过程中，首先利用噪声源产生宽带信号，再利用带宽为98-122MHz的带通滤波器选择指定范围内的频率分量，积分60次时信号频谱如图8所示。

![](images/039615e6230fa3eb0d0171118a3b2daca84beef298dd3abda84aa74f89cf451b.jpg)  
图8带宽98-122MHz信号频谱  
Fig.8 Bandwidth 98-122MHz signal spectrum

搭建的实验平台可以通过10GbE的 SFP $^ +$ 端口实现实验平台硬件设备之间的数据传输，通过PPC的1GBE端口读出预处理数据，通过ZDOK端口传输ADC 数字化信号到FPGA；可在Simulink 设计中嵌入HDL定义的模块并进行实例化，创建新的 Xilinx 模块、CASPER 模块；利用 Simulink 和 CASPER 库中的模块，可以构建新的硬件设计，实现相关的天文信号处理功能。经过测试，本文搭建的实验平台可满足射电天文数字终端算法测试需求。

由于操作系统及应用软件版本不断更新并且相互不兼容，在实验过程中遇到了一系列版本不匹配问题。由于软硬件平台的更新换代，设计模块也在不断修正、替换、弃用、添加等，都影响了对不同版本库的调用，在建设过程中遇到了模块版本老、EDK版本落后、参数不存在等报错提示，通过尝试替换不同版本的软件包解决了相关问题。CASPER 教程说明现已不在原网站上更新，本文实验平台搭建涉及到的库、实验中的 bof 文件可以到新疆天文台数据中心下载，网址http://data.xao.ac.cn/static/RAOCH2_platform.tar.gz。

# 4总结

本文根据射电天文海量信号实时处理需求，对数字终端系统环境建设进行了研究，借助通用性良好的CAPSER硬件开发平台及其相应软件环境，搭建了基于ROACH2的数字终端系统实验平台。利用CAPSER提供的示例对搭建的实验平台进行了测试、调试和分析，实现了相关实例设计、仿真、编译、运行的完整过程。实验结果表明，本文所搭建的平台运行平稳、可靠。目前所搭建的数字终端环境已经应用在脉冲星信号仿真处理，射频干扰抑制算法测试与高速数字信号传输等相关研究领域。

# 参考文献

[1]杨文军,杨军,江悟,夏博,李健,崔朗,张华,李鹏,高志福.新疆天文台南山站 DBBC2 数字终端系统的建立[J].天文研究与技术,2018,15(01):32-39.

[2] WERTHIMER D.The CASPER collaboration for high performance open source digitalradio astronomy instrumentation. In: Proceedings of General Assembly a nd Scientifc Symposium. Istanbul: IEEE，2011.

[3] RANSOM S M, DEMOREST P, FORD J,et al. GUPPI: Green bank ultimate pulsar processing instrument[C]//American Astronomical Society Meeting Abstracts# 214. 2009, 214.

[4]SARKISSIAN J M, CARRETTI E,STRATEN W V. The Parkes Pulsar Backends[C].

AIP Conference Proceedings,2011,1357,351-352.

[5]PARSONS A R, BACKER D C, SIEMION A,et al. A Scalable Correlator Architecture Based on Modular FPGA Hardware, Reuseable Gateware,and Data Packetization[J]. Publications of the Astronomical Society of the Pacific,2008,120(873): 1207-1221.

[6] CHANG C，WAWRZYNEK J，BRODERSEN R W，et al. BEE2: a high-end reconfigurable computing system[J]. IEEE Design & Test of Computers,2005,22(2): 114-125.

[7] LAZARUS P, KARUPPUSAMY R，GRAIKOU E,et al. Prospects for high-precision pulsar timing with the new Effelsberg PSRIX backend[J]. Monthly Notices of the Royal Astronomical Society, 2016, 458(1): 868-880.

[8] KEITH M J， JAMESON A，VAN STRATEN W，et al. The High Time Resolution Universe Pulsar Survey l: System configuration and initial discoveries[J]. Monthly Notices of the Royal Astronomical Society, 2010, 409(2):619-627.

[9] NAN R D，LI H X. Progress of FAST in science，technique and instrument (inChinese).Sci Sin-Phys Mech Astron,2014,44:1063-1074[南仁东，李会贤.FAST的进展—科学、技术与设备[J]．中国科学:物理学 力学 天文学,2014,44(10):1063-1074.]  
[10] YU Y Z， PENG B， LIU K，et al. FAST ultra-wideband observation of abnormalemission-shift events of PSR B0919+06[J].Science China(Physics,Mechanics &Astron0my),2019,62(05):36-41.

[11]赵盼孜,李彬华,毛拢哗,陶勇.幸运成像算法的FPGA实现[J/OL].天文研究与技术:1-7.[12]纪志成，高春能，吴定会.FPGA数字信号处理设计教程:System Generator入门与提高[M]．西安电子科技大学出版社，2008.

# The construction of digital backend experiment platform based on ROACH2

ZHANG Meng1.2, ZHANG HaiLong1.2,3,WANG Jie1, LI Jian1, Tohtonur1

(1. Xinjiang Astronomical Observatory, Chinese Academy of Sciences, Urumqi 830011, China;

2.University of Chinese Academy of Sciences, Beijing 10o049, China ;

3. Key Laboratory of Radio Astronomy, Chinese Academy of Sciences, Nanjing 210008,

# China)

Abstract : An experimental platform of radio astronomy digital backend based on ROACH2 was built for the real-time processing requirements of astronomical signals. UsingMATLAB， Xilinx and other development environments to simulate the process of astronomical signals，and the raw data were obtained; the signal control and pre-processing were realized by CASPER hardware platform，and the data packet was transmitted to the computing server through high-speed Ethernet for post-processing. The experimental platform has realized the complete process of simulation, compilation and operation, and provided a good experimental environment for the real-time processing of astronomical signals.

Keywords : Digital Backend ; ROACH2 ； Experimental Platform ； CASPER