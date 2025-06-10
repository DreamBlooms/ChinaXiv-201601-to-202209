# 基于FPGA的万兆以太网UDP_IP硬件协议栈设计与实现

董永吉，王钰，袁征(解放军战略支援部队信息工程大学，郑州 450002)

摘要：针对传统的基于软件协议栈无法满足高速数据传输处理的需求，提出了一种基于硬件加速的 UDP 协议栈设计方案，该方案基于硬件高效并行的特点，实现了UDP/IP 协议栈，满足了万兆以太网数据传输高带宽需求的问题，通过实际测试表明，该设计最高可以达到9.32Gbps传输速率，满足10Gbps带宽下线速处理的需求，与传统软件实现相比，处理能力更接近理论极限。

关键词：FPGA；万兆以太网；硬件协议栈；UDP协议 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2021.12.0689

Design and implementation of 10G ethernet UDP/IP hardware protocol stack based on FPGA

Dong Yongji, Wang Yu, Yuan Zheng (PLA Strategic support force information engineering university,Zhengzhou 45oo02,China)

Abstract: Aiming atthe problem that the traditional software protocolstack cannot meet the performance requirementof high-speeddatatransmision,thispaper presentsadesignschemeofUDP protocolstack basedonhardware aceleration.The design is basedonthecharacteristicsofefficientand parallelhardware toimplements the UDP/IPprotocolstack.and solves theproblem ofpoor performanceofhigh-speeddatatransmision.Theactual testshows thatthe designcanreach the highest level.To 9.32 Gbps transmissionrate,it meets the needof10 Gbps bandwidth downlink speed processing.Compared with traditionalsoftwareimplementation,itshows that theprocessingcapacityoftheproposed methodisclosertothetheoretical limit.

Key words: FPGA; 10G ethernet; hardware protocol stack;UDP protocol

# 0 引言

随着网络技术的飞速发展、网络带宽的迅速提升，数以万计的视频、图像等业务数据逐渐成为高速链路传输的主要组成，面对海量数据的传输压力，传统操作系统内置协议栈或以软件为核心的协议栈加速技术已经不能满足高速、低延迟传输的需求。

根据网络处理经验，1Gbps的以太网传输需要1GHz的处理器频率，面对万兆高速网络的传输需求，大量CPU计算资源都被将消耗网络协议的处理上。基于硬件实现的UDP/IP协议栈，因通过硬件固化协议栈的处理逻辑，进而能提供高吞吐率、低延迟、高带宽的传输性能[1]。

鉴于FPGA兼备灵活可配置和高速并行处理的特性，尤其适合在高速传输领域固化协议栈来提升系统的处理能力。熊光阳[2]等人提出了一种基于FPGA实现MAC及UDP/IP协议栈的方法，旨在解决千兆以太网高速传输的问题；崔鹤[3]等利用硬件实现了UDP/IP协议数据的封装和拆封；GuixéOrriols $\mathbf { G } ^ { [ 4 ] }$ 面向DAQ应用，基于INTELFPGA实现了一个通用的千兆UDP/IP协议核；冯琛[5]面向高性能协议协议处理需求，设计了一个高效的千兆协议栈；NianyunLiu等人提出了一个适用于大型传感器网络的UDP/IP协议栈，比软件处理提升了8倍的性能。面对万兆应用场景，王禹衡设计了一个10G以太网UDP/IP处理器视频传输接口；夏杨[8设计了一种万兆以太网分发平台，满足万兆以太网UDP传输的需求；彭鹏[面向核物理低时延的处理需求，实现了一个高速协议处理模块，而国外厂商PLDA[10]、FraunhoferHH[11]、Intilop[12]以及DiniGroup[13]等公司也分别提出价格不菲的商

用IP核。

综上可知，当前硬件协议栈研究主要集中在千兆以太网环境，而万兆以太网的硬件协议栈是当前的应用热点。本文基于FPGA实现的UDP/IP协议栈为面向10G网络环境设计，具有以下优势：1.集协议帧的解析、处理、发送和接收于一体，大幅提升系统UDP应用的传输效能。2.基于FPGA可重构可配置的特点，可以部署于不同场景的网络环境中；3.面向服务器应用设计，可支持多端口多点业务的并发连接。

# 1 硬件结构设计思路

为了提高UDP协议的传输效能，本文提出一种基于FPGA的UDP协议栈设计方案，该设计基于斯坦福大学的NetFPGA-10G[14]板卡实现，能够尽可能多地支持各种应用。本方案利用该板卡PCIExpress接口的便携扩展能力强的特点，方便在服务器应用场景中通过扩展物理接口的方式，部署该硬件协议栈到服务器系统中，提升服务器中各种应用UDP协议的加速传输处理。

FPGA作为硬件子系统设计中的重点和难点，根据FPGA硬件结构特点实现了协议处理功能，并将硬件部分划分为10GMAC接口模块、协议解析模块、ARP响应模块、ICMP响应模块、协议封装模块、UDP协议处理模块、PCIE-DMA模块，模块划分如图1所示。

1)协议解析模块

该模块主要实现数据报文的协议解析处理，并为后续响应报文的生成和封装提取用户的相关信息。首先该模块对到达系统的数据报文协议逐层进行解析，最终实现对本地支持的UDP协议请求协议报文的解析、本地协议报文的提取以及无关报文的过滤三部分功能，鉴于FPGA硬件结构的特殊性，无法完整实现所有协议的解析和处理，针对于设计的应用场景，实现的具体处理算法流程如下图2所示。

![](images/75fba54322a212529f05df45d2389576b2d519de7313da4b5c68ed33831605c0.jpg)  
图1系统结构组成框图

![](images/3c47a2513e71f20089769ad7e29fd62abd7de8377cd0e229cb403b2bff705ba8.jpg)  
Fig.1System structure composition block diagram   
Fig.2Protocol processing flowchart

具体处理算法步骤如下所示。

step 1)：判断到达以太网帧的以太类型是否为 $0 \mathrm { x } 0 8 0 0$ ，如果为 $0 \mathrm { x } 0 8 0 0 ( \mathrm { I P v } 4$ 协议)，则执行 step 2，否则执行 step7;

step 2)：判断到达的 IPv4 协议报文中目的IP字段是否匹配本地配置的多个服务IP，如果命中本地多个服务IP中的一个，则执行step3，否则丢弃该报文；

step3)：判断到达的IPv4协议报文头中协议字段是否为ICMP，如果为ICMP 协议，则执行 step4，否则执行 step 6;

step4):提取到达的ICMP协议报文中源IP地址和ICMP协议号，用于后续ICMP响应报文的生成，并跳转结束协议解析处理;

step 5)：判断到达的IPv4协议报文头中协议字段是否为UDP，如果为UDP协议，则执行 step6，否则丢弃该报文;

step6)：提取到达的UDP协议报文中源IP地址，用于后续UDP响应报文的封装，并跳转结束协议解析处理；

step 7)：判断到达以太网帧的以太类型是否为 $0 \mathrm { x } 8 0 6$ ，如果为 $0 \mathrm { x } 0 8 0 6$ (ARP 协议)，则执行 step8，否则丢弃该报文;

step8)：判断到达的ARP协议报文中目的IP字段是否匹配本地配置的多个服务IP，如果命中本地多个服务IP中的一个，则执行step9，否则丢弃该报文；

step9)：判断到达数据帧的目的MAC地址是否为全F(广播地址)，如果为全F，则执行 step 10，否则执行 step 12;

step10)：判断到达数据帧的目的MAC地址是否为本地MAC，如果是本地MAC地址，则执行step11，否则丢弃该报文；

step11)：提取到达的ARP协议报文中源MAC地址和源IP 地址，用于构建ARP缓存表以及后续APR响应报文的重组，并跳转结束协议解析处理；

step12)：提取到达的ARP协议报文中源MAC地址和源IP 地址，用于构建ARP缓存表以及后续ARP响应报文的生成，并跳转结束协议解析处理。

# 2)ARP 响应模块

该模块实现ARP请求、响应报文的构建以及ARP缓存表的维护功能。基于FPGA构建该模块时，采用FPGA片内BLOCKRAM存储ARP表项，鉴于硬件资源的有限性，故在标准的ARP协议处理的基础上，该模块增加了硬件资源这一限制条件，即当BLOCKRAM中存储的 ARP表即将溢出时，会选择性删除老化时间最长的表项，进而维持整个ARP表的正常操作。

首先根据ARP请求报文信息，构建ARP响应报文；其次响应协议封装模块请求，提供IP-MAC映射服务，并定时刷新ARP缓存表，根据老化时间删除过期表项；再次根据需求，对于缓存表中未存在的IP-MAC映射关系，主动组织ARP请求报文内容。ARP缓存表维护的算法流程如下图3所示。

![](images/81dac5739503cb8759783ac73121f2c69a08b0ccb362f70094e1aa7b8597d019.jpg)  
图2协议处理流程图  
图3ARP缓存表维护算法流程图  
Fig.3ARP cache table maintenance algorithm flowchart

ARP缓存表维护具体步骤如下所示。

step1)：判断使用待发送数据包的目的IP地址与缓存表空间中的表项进行匹配，如果匹配，执行step2，否则执行step 3;

step 2)：检查表项空间中的表项地址上是否已经全部建立了缓存表项(表项空间是否已经被使用完毕)，如果是，执行step 6，否则执行step 7;

step 3)：依据缓存表中存储的时间戳与当前时刻进行对比，判断待匹配的缓存表项是否已经超时，如果是，执行 step4，否则执行 step 5;

step4)：删除超时的缓存表项信息，并生成对应的ARP请求报文内容；

step 5)：更新缓存表项的时间戳信息；

step6)：删除缓存表空间中的一条老化时间最长的表项；

step7)：在表项空间中未被占用的地址上创建新的缓存表项。

3)ICMP协议响应模块

该模块实现了ICMP协议的一个子集。每当收到ICMP请求报文之后，根据当前系统的状态，按照ICMP协议规定，对应生成相应的响应报文。本文设计的UDP协议栈目标部署在服务器端，故根据服务终端的协议特性，实现了包括“回显应答”、“超时”和“目标不可达”三类响应功能。其中“回显应答”用于支持客户端的PING信息，“超时”用于支持数据段TTL过期，“目标不可达”用于指示服务器端未开放的端口。

# 4）协议封装模块

该模块主要实现两个功能，其一是对UDP数据报进行协议封装；其二是对封装后的UDP协议数据帧、ICMP协议数据帧和ARP协议数据帧进行数据合流，统一发送到10GMAC接口。其中针对UDP报进行IP协议的封装时，需要根据用户的IP地址(目的IP地址)信息在ARP响应模块的ARP缓存表中匹配查找表项，并获取该IP地址对应MAC地址信息，进而将该IP包封装成数据帧，协议封装模块的结构如下图4所示。

ICMP响应模块 ICMP协议数据帧↓  
协议封装模块  
→2 -P包封装 获取目的– MAC帧封装 数据合流入队FIFO 出队FIFO  
ARP响应模块ARP缓存表 ARP 协议数据帧

该模块主要实现UDP协议的封装和拆装，以及UDP校验和的计算，以及与应用软件的套接字接口和数据通道。UDP协议处理模块与应用软件接口如下图5所示。

UDP协议处理模块 接收接口 接收的应用数据 / 软件应用发送接 目的IP+源/目的端口发送的应用数据□L_J

软件应用运行在服务端，软件功能在提供服务之前，需要通过配置端口向硬件协议栈申请/释放服务端口，硬件模块根据服务端口的状态，决定提供或是拒绝服务。

当该模块接收到来自线路的数据时，若通信的目的端口为开放状态，硬件则进行UDP协议的拆装，提取通信套接字和接收数据；若通信的目的端口为关闭状态，硬件则丢弃该UDP 数据段。

当该模块接收到来自软件的数据时，若通信的源端口为开放状态，硬件则根据软件提供的套接字和应用数据，封装成UDP数据段；若通信的源端口为关闭状态，硬件则丢弃该应用数据。

为了实现服务器场景下对众多UDP端口状态的管理，支持多端口多点业务的并发连接，该模块内部采用双口BRAM建立了一个地址为16bit位宽的端口状态表，软件系统通过申请/释放操作将该查找表中对应端口号设置为开放/关闭，状态表中共有 $2 ^ { 1 6 }$ 个地址，可以将UDP所有的端口号一一映射到该表中，且每个表项内有1bit指示位用于标志该端口号是否开放，如下图6所示，53端口(DNS协议)状态开放。并结合时间和事件触发机制轮询整个状态表，实现对整个UDP端口的生存周期管理。通过在FPGA片内资源搭建这样一个端口状态查找表，支持多端口状态的并行查找，实现多端口多业务的共存，利用双端口RAM的操作特性，也可以有效提升多端口多业务时状态的查找速率。

6)PCIe-DMA模块

PCIe-DMA 模块主要包括XilinxPCIeIP核和DMA模块。PCIeIP核直接在Vivado中调用，用来实现PCIe协议的物理层和数据链路层。如图5所示，PCIe-DMA模块主要实现了UDP协议处理模块与上位机软件的透明通信。

（地址位数据位一0 01 02 02^16 . 053 10? 2^16-1 0

![](images/dc7c2be367e62bb063e2872a719da3a38d3d4d7f2a3ed2d0eebf5a2aea17d9b6.jpg)  
Fig.4Protocol encapsulation module composition diagram 5)UDP协议处理模块   
图5UDP协议处理模块应用接口  
Fig.5UDP protocol processing module application interface   
图6服务端口开放标志  
Fig.6Schematic diagram of service port open sign   
图7功能测试结果  
Fig.7Functional test results

# 2 设计验证

本设计的验证分为功能仿真验证和物理性能验证。验证的硬件平台依托于斯坦福大学的NetFPGA-10G板卡，具有4个10Gb/s的PCIExpress适配卡，采用Virtex-5XC5VTX240T-2 FPGA作为主处理芯片，该FPGA可用的逻辑资源为18,720 可编程逻辑单元(configurable logic blocks)、2,400Kbit分布式存储单元(DistributedRAM)和11,664K(324x36K)bit块存储单元(BlockRAMs)，整个系统采用verilog语言开发，基于Xilinx 公司的Vivado2016.4工具进行开发，并使用XilinxISIM工具进行了仿真验证，仿真结果表明该协议栈设计能够正确完成ARP、ICMP、IPv4、UDP等协议报文的发送和接收等功能。如下图7所示，协议栈实现了10G速率下数据线速的接收和发送功能。

为了对本文所提出的设计方案进行性能验证，采用斯博伦TestCenter3.61的两个10G接口进行实际发包测试，采用逐步增大测试数据包MTU长度的方法，测试本系统以及基于LINUX原生UDP协议栈在处理不同数据包长情况下的性能，测试结果如图8所示。

![](images/ac258a36e21aed3bfbebbbeb330d92e4c12a47b02987a207773cf8795160cb8b.jpg)  
图4协议封装模块组成图  
图8性能测试结果  
Fig.8Performance test results

从图8中看以看出，随着数据报文MTU值的增加，硬件协议栈对于UDP协议负载的传输能力越发贴近理论值，而软件实现的UDP协议栈限于处理器串行处理能力的瓶颈，与本方案的性能差距愈发明显；当MTU达到1400 字节时，协议栈对于UDP数据可以达到9.32Gbps 的传输速率，接近理论值9.7Gbps，达到了设计的要求，满足10G 链路上线速传输数据的需求。

# 3 结束语

传统基于FPGA的UDP/IP协议栈研究都是集中在一对一的点到点传输，无法适用于10G网络环境下提供多点并发连接的服务器场景，本文研究了一种面向服务器应用场景的UDP硬件协议栈，本设计充分利用硬件在并行处理上的优势，流水化设计UDP协议处理流程，将UDP协议处理固化在FPGA中，降低于传输层协议对处理器的处理需求，提升系统的传输效能，通过实验结果表明，该协议栈可以适用于10G网络UDP协议的线速处理。在未来的工作中，将面向5G应用场景上一些传输速率非常高的服务进行研究和讨论，并研究其与智能网卡方向的结合与应用。

# 参考文献：

[1]柯洋．基于FPGA的高速数据传输板设计与开发[D].武汉：华中师范大学,2020.  
[2]熊光阳，王野，李志茹，等．基于FPGA的千兆UDP/IP协议栈的实现及其在高速图像传输中的应用[J].仪器仪表用户，2020,27(03):38-41.  
[3]崔鹤，刘云清，盛家进．基于FPGA 的 UDP/IP协议栈的研究与实现[J].长春理工大学学报（自然科学版)，2014(2):133-137.  
[4]Guixé Orriols G.Design and implementation of an UDP/IP Ethernethardware protocol stack for FPGA based Systems [D].Barcelona:UniversitatPolitécnicade Catalunya,2019.  
[5]冯琛．基于 SAR 的高性能协议处理引擎技术研究[D].杭州：浙江大学,2021.  
[6]Nianyun Liu, Zhiqiang Xu. The Design of High-Speed Hardware UDP/IPStack Based on FPGA for Large-Scale Sensing Systems.Journal ofInternet Technology,2017,18 (3): 579-587.  
[7]王禹衡．基于FPGA的 10G以太网UDP/IP 处理器视频传输接口设计[D].沈阳：沈阳工业大学 2018.  
[8]夏杨．基于FPGA的万兆以太网数据分发平台设计[D].北京：北京理工大学 2016.  
[9]彭鹏．基于万兆以太网的核物理实验高速数据传输系统研究[D].兰州：西北师范大学，2021.  
[10]https://www.plda.com/products/fpga-ip/xilinx/fpga-ip-tcpip/quicktcp-xilinx/.  
[11]LangenbachU,Berthe A,Traskov B,et al.A10 GbE TCP/IP hardwarestack as partof a protocol acceleration platform[C]//Proc of2013 IEEEThird International Conference on Consumer Electronics.Berlin (ICCE-Berlin).IEEE,2013:381-384.  
[12] http://www. intilop.com/tcpipengines. php/.  
[13] http://www. dinigroup.com/new/TOE. php/.  
[14]刘宇寒．基于NetFPGA10G的网络数据包加密实现及其低功耗研究[D]．杭州：杭州电子科技大学,2018.