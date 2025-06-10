# 基于车载自组织网络的紧急报文传输方法

慕健1，高强1，殷柯欣²，朱建启1\*

(1．吉林大学 计算机科学与技术学院，长春 130012;2.长春工业大学 计算机科学与工程学院，长春 130012)

摘要：针对车载自组网中信息传输时延问题进行了研究，提出一个紧急报文的传输方法。通过Netfilter架构截取得到报文的数据信息，利用Linux虚拟设备重新组装安全警告信息报文，直接指向物理网卡发送给目的终端。传输过程减少了传统的缓存等待时间和TCP/IP对等层的额外开销，结果表明在传输过程中有效降低了传输时延，提高了车辆的行驶安全。

关键词：车载自组织网络；紧急报文；Netfilter架构；虚拟设备中图分类号：TP393.04 doi:10.3969/j.issn.1001-3695.2017.11.1013

# Emergency message transmission method based on VANET

Mu Jian1,Gao Qiangl, Yin Kexin², Zhu Jianqi1t (1.CollegeofComputerScience&TechnologyJilinUniversityChangchunl300l2,China;2.ColegeofComputerScience& Engineering,Changchun University of Technology,Changchun 130012,China)

Abstract: This paper studied theproblem ofinformation transmission delayin VANET,and proposed an emergencymessage transmissionmethod.The method gotthe messages datathrough netfilterarchitecture,reassembledthe warning messges with Linux virtualdevice,thendirectedthephysical networkcardandsentittothedestination terminal.The transmission proce both reduces the time delayoftraditional cacheandtheoverheadof TCP/IPpeerlayers.Theresult shows itis efectively reducing the transmission delay during the transmission process,and improving the driving safety of the vehicle.

Key Words:VANET; emergency message; Netfilter architecture; virtual device

# 0 引言

车载自组织网络(vehicular ad-hoc network，VANET)[1,2]即由道路上的车辆与车辆及车辆与路边设施动态构建的一个分布式控制的短距离通信网络，其真实网络结构如图1所示。VANET中出现了很多V2X的模式，包括车对车(V2V)、车对基础设施(V2I)、车对互联网(V2N)和车对行人(V2P)等。其中VANET技术典型的应用涵盖了行驶安全预警、协助驾驶、分布式交通信息发布、交通流量控制等多个方面。

![](images/5c9e0e00f72b7d06121db430862313007af053853eb22c201eb721033fd4b629.jpg)  
图1 VANET网络结构示图

在模拟安全事故实验中，根据实验数据，系统响应时间越低，安全警告信息就能越早传递到驾驶员手中，相当于留给驾驶员更多的反映时间。这对避免安全事故发生起着相当重要的影响。VANET构建的一个重要目标在于提高车辆的行驶安全，使得车辆之间能够及时的分享安全相关信息，因此对与安全相关的紧急报文的发送与接收的及时性要求较高。

近年来，关于车载自组织网络协议栈[3.4]以及路由算法[5-8]的研究不少，文献[10]为了实现高效数据路由传输，提出基于停车骨干网络的数据传输策略，将停放车辆组成虚拟网络实现数据传输，与传统协议相比具有较高的传输成功率和较低的传输延迟，但随着车辆产生消息速率提升传输成功率有所下降，此外数据包大小和RSU数量对协议性能也有影响；文献[11]则针对紧急消息提出了一种基于距离的接收者定向的路由协议BDRO，该协议具有选择性、被动型和转发节点候补机制的特征，用节点与源节点的距离作为选择转发节点的依据，但紧急报文的传输仍然是以 TCP/IP协议方法，对于紧急报文的传输可以做进一步简化；文献[12]针对高速公路安全预警要求提出了一种VANET协作安全预警路由算法，通过方向性广播转发路由技术达到快速传播目的，在报文产生和接收阶段其思想与正常报文传送无异。现已有的报文发送方法主要是传统的TCP/IP协议方法。TCP/IP协议采用分层的模块化协议栈设计思想，主要分为应用层、传输层、网络层和网络接口层。每一层完成数据包传输时的一部分功能，数据包按照协议栈从上到下依次打包发送出去。但在车载自组织网络发送紧急报文的应用中，TCP/IP协议存在一些不足，主要表现在：

a）TCP/IP协议的传输层和IP层在将应用层报文放到网络接口层传输之前，需要对数据层层打包(加报头)这个过程中就可能涉及到对数据的解析和拷贝。对于紧急报文而言，无论是数据的解析、拷贝，还是传输层和IP层所必须的打包，都会增加紧急报文的传输延迟。

b）针对IP层来说，IP层主要是添加IP报头并通过不同的IP 地址找到合适的路由并将数据包发送到指定的终端。而在车载自组织网络中，与安全相关的紧急报文只要传输到事故车辆周围一定范围的车辆即可，所以采取广播的方式最为合适。并且车载网络采用802.11p无线通信协议，该协议的有效传输范围为300米，对于紧急报文要传输的车辆范围足够。从这个角度来看，TCP/IP协议的IP层功能对于紧急报文传输是不必要的，其只会增加紧急报文的传输时间。

c）针对传输层来说，传输层主要是添加传输层报头并通过传输层报头实现连接控制(可靠传输、差错控制、流量控制)。而在车载自组织网络中，安全相关的紧急报文不需要太多的应用处理，事故车辆在事故结束前会不断的向周围广播紧急报文。因此，传输层的功能对于紧急报文的传输是不必要的，其反而增加了紧急报文的传输延迟。

由此可见，车载自组织网络中传输安全相关的紧急报文时，传统的TCP/IP协议的传输层和IP层功能不仅是不必要的，而且在这两层中的处理还会增加紧急报文的传输延迟。

# 1 紧急报文传输方法

针对上一节的分析，提出了如图2所示的协议模型。图2给出了一个紧急报文处理模块，该模块的传输过程减少了传统的缓存等待时延和TCP/IP协议中多余的IP层和传输层功能的额外开销，抢占了其他传输资源直接通过物理层，实现了紧急报文在产生后的第一时间内立即发送出去的目的。

![](images/df49cc20d258a829d4555021259108067e9dcc76f378551269bf57ed862d8466.jpg)  
图2协议模型的结构框图

根据图2的协议模型，本文给出了一个紧急报文传输方法，该方法通过netfilter架构的截取得到报文的数据信息，利用Linux虚拟设备重新组装安全警告信息报文，直接指向物理网卡发送到目的接收终端。该方法的流程框图如图3所示，包括主要步骤如下：

a）紧急报文产生阶段。紧急报文处理模块在车辆发生紧急情况时产生紧急报文，紧急报文格式如图4所示。在车辆发生事故或其他紧急情况时，车载系统中的紧急报文处理模块的系统进程抢占CPU资源快速产生相应的紧急报文，或者由拥有权限的用户进程调用紧急报文处理模块产生紧急报文。

b)紧急报文发送阶段。紧急报文处理模块将产生的紧急报文组织并发送。紧急报文处理模块组织需要发送的紧急报文，加入必要的位置信息和紧急报文类型，如：车辆碰撞，救护车，协同防撞，要将紧急报文的长度组织在20个字节以内，因为IP报文的有效长度大于等于20字节，紧急报文处理模块和TCP/IP协议的网络层可以通过报文的长度区分报文的类型，然后紧急报文处理模块将组织好的紧急报文直接交给网络接口层，通过广播的方式发送到802.11p无线通信协议的有效范围即300米内的车辆。

d)紧急报文接收阶段。紧急报文处理模块接收紧急报文并处理。根据紧急报文的长度信息，紧急报文处理模块判断收到的是否为紧急报文；当周围车辆的网络接口层收到报文时并不判断报文的类型，而是将报文分别交给TCP/IP协议的网络层和紧急报文处理模块，TCP/IP协议的网络层直接丢弃长度小于20 字节的报文并处理长度大于等于20字节的普通报文；同时紧急报文处理模块直接丢弃长度大于等于20字节的报文并处理长度小于20字节的紧急报文。当紧急报文处理模块收到紧急报文时，对应的系统进程抢占CPU资源，优先处理安全相关的紧急报文。

如图4所示，紧急报文格式中报文类型字段占用16位（2Byte)，该报文类型字段主要区分紧急报文所代表车辆的紧急事务的类型(事故后告警、车辆协同防撞、交叉路口协同防撞等)，16位可以表示65535种不同的类型。保留位用于以后可能的扩展应用，数据部分(最多15字节)主要存储车辆的位置信息。该紧急报文的长度最长为19字节，而IP报文的有效长度为至少20Byte，如此便可通过报文的长度来区分不同的报文类型。

![](images/0d0de9f8d1c95855a49283c0be216db6bfdf1fe4eb282c7105a490d71c4cb198.jpg)  
图3紧急报文传输方法的流程框图  
图4紧急报文格式

<html><body><table><tr><td>报文类型（16位）</td><td>保留位（16位）</td></tr><tr><td colspan="2">数据（主要是位置信息）</td></tr></table></body></html>

因此，本文提出一种基于车载自组织网络的紧急报文传输方法，具有以下特点：

a)本文所述的基于车载自组织网路的紧急报文传输方法在传输车载自组织网络的紧急报文时，可以越过TCP/IP协议的传输层与IP层的打包过程；

b)本文所述的基于车载自组织网路的紧急报文传输方法同时使用专门的系统内核模块处理紧急报文可以方便的抢占CPU，省去进程排队的时间。

以长春市为例，假设在长春市卫星广场发生撞车事故时，由于受到外部硬件的触发，事故车辆车载系统中紧急报文处理模块的紧急报文产生单元调用紧急报文处理模块的系统进程抢占CPU资源，快速产生相应的紧急报文，并将该紧急报文交给紧急报文发送单元，或者由拥有权限的用户进程来调用该系统进程产生紧急报文并交给紧急报文发送单元。

紧急报文发送单元将事故车辆的位置信息“卫星广场”加入到紧急报文的“数据”字段，占用8Byte；假设用“0000000000000001”代表撞车事故的事故类型，将事故类型“0000000000000001”加入到紧急报文的“报文类型”字段，占用2Byte；假设没有其他重要信息则紧急报文的“保留位”字段为空，这样该紧急报文占用10Byte，然后将组织好的紧急报文交给网络接口层，通过广播的方式发送到802.1lp无线通信协议的有效范围 $( 3 0 0 ~ \mathrm { m } )$ 内的车辆。

周围车辆的网络接口层收到该紧急报文时，将该紧急报文分别交给TCP/IP协议的网络层和紧急报文处理模块的紧急报文接收单元，TCP/IP协议的网络层直接丢弃该紧急报文，因为报文的长度小于20Byte，而紧急报文处理模块的紧急报文接收单元根据报文长度判断该报文为紧急报文，于是调用紧急报文处理模块的系统进程抢占CPU资源，优先处理该紧急报文。

# 2 紧急报文发送机制的实现

本文利用局域网环境，选取两台正常联网的PC机分别用作开发平台（发送端）和测试平台（接收端)，以linux-gcc-3.2.2-5作为本系统开发的整体编译环境，操作系统都选择RedHat9.0Linux，局域网中的所有PC机同时可以支持 IPv4/IPv6地址协议。

本文提出紧急报文发送机制实现的结构如图5所示，主要完成以下任务：在用户空间中运行了基于IPv6 地址协议的 tcp报文发送进程(tcpclient)、tcp 报文接收进程(tcpserver)、udp 报文接收进程(udpserver)；在Linux 操作系统的内核空间中有两个重要的模块被加载并且正常运行，分别是包含了netfilter 架构的packet 模块和包含了Linux 虚拟设备的vdev 模块，两者技术都源于Linux设备驱动程序。这些程序相互组合起来就可以用于实现在基于Linux 操作系统的车载高速移动终端生成VANET紧急报文并在生成后的第一时间内立即发送出去。

# 2.1 Netfilter架构

Linux2.4内核以后出现的netfilter，是一种防火墙架构，主要实现了状态检测、包过滤等功能。可以利用它的开放性接口，在相应的协议层中实现自己的功能模块。netfilter架构在网络协议中为IPv4和IPv6地址协议各定义了5个钩子(HOOK)函数，如图6所示，在IPv6协议中分别为：

HOOK(1),NF_IP6_PRE_ROUTING;   
HOOK(2),NF_IP6_LOCAL_IN;   
HOOK(3),NF_IP6_FORWARD;   
HOOK(4),NF_IP6_POST_ROUTING;   
HOOK(5),NF_IP6_LOCAL_OUT。

![](images/248caabb66d21ab4d0ba9df8345f619e8fefffd34d82ceceb24ac23ed8d07388.jpg)  
图5VANET紧急报文发送机制结构示意图

![](images/74801359700184feef561d0d30303c66eb8c6b21985a1fe3ab73ed6283055d88.jpg)  
图6netfilter架构钩子机制

netfilter架构具体的数据处理流程为：当传输在网络中的各种数据包要从数据链路层进入操作系统时，首先要进行IP地址校验，第一个钩子HOOK(1)（NF_IP6_PRE_ROUTING）开始作用，它决定该数据包是进入本机还是转发。如果它是被转发的，接下来会被钩子HOOK(3)(NF_IP6_FORWARD)钓到并转发处理；如果它是要进入本机的，接下来会被钩子HOOK(2)(NF_IP6_LOCAL_IN)钓到，并向上层协议传递。经过转发后的数据包会被第 4 个钩子 HOOK(4) (NF_IP6_POST_ROUTING)钓到并处理。进入本机经过本机处理过的数据包会被钩子HOOK(5)(NF_IP6_LOCAL_OUT)钓到并处理，最后经过路由处理，在钓点被第4个钩子HOOK(4)(NF_IP6_POST_ROUTING)钓到并处理后再次被传输到网络中去。协议中的每一个钩子函数，在经过处理完成后，其返回值将是某一个整型常量，Linux内核对数据包所做的相应处理就是根据这些返回值，具体来讲这些返回值包括：

a）NF_DROP：丢弃不做任何处理;  
b）NF_ACCEPT：接收进行下一步处理;  
c）NF_STOLEN：异常分组;

d）NF_REPEAT：再进入这个钩子；

e)NF_QUEUE：进入用户空间排队，等待相应进程处理。

VANET紧急报文发送机制中的packet模块主要是用到了netfilter架构中5个HOOK（钩子函数）中的NF_IP6_LOCAL_OUT这个HOOK(钩子函数)，实现了在数据包从本地进程发送出去时，对其进行捕获然后进行相应的连线跟踪和包处理操作，netfilter架构技术的具体工作流程可以用图7所示。

# 2.2Linux设备驱动程序技术

在Linux操作系统中，所有的一切都是文件，实际硬件设备所对应的就是一个个“设备文件”，概括来讲这些设备主要有三种类型：字符设备、块设备和网络接口，并且独立于内核存在，必要时可以在插入，不必要时就删除。Linux设备驱动程序的工作原理如图8所示。

![](images/a043309c74723d0efc89f88faa5bc80114fcc4529cc6b9dda4a3a63db97489ae.jpg)  
图7netfilter架构工作流程

![](images/503201280cbf8dfc66203b6e1d39816d3bc3bc65ad4d829a13cdb3a72fc78380.jpg)  
图8Linux设备驱动程序工作原理

Linux设备驱动程序的结构如图9所示。在本文所研究的VANET紧急报文发送机制中主要应用到的技术就是linux设备驱动程序中网络设备部分的驱动程序技术，即网络接口。

![](images/68e02a0ac397389d39b960d461c57af0c8f36b49bf34fea42de7256532ab8d6c.jpg)  
图9Linux设备驱动程序结构

本文中用到的Linux 设备驱动程序模块为“vdev”模块，该模块中主要实现了三个功能：从含有netfilter 架构技术的“packet”模块中获得TCP报文中的有用信息；将其中原始的要发送的信息提取出来重新组装成符合要求的UDP紧急报文；将新组装的UDP报文不经过协议栈和各种缓存队列直接指向网卡“eth0”发送出去。

# 2.3VANET紧急报文发送机制实现过程

VANET紧急报文发送机制利用Linux下socket网络编程技术、netfilter架构技术和Linux设备驱动程序技术，完整发送机制的详细工作流程如图10所示。由图10可知，紧急报文发送机制按照所涉及的程序运行在计算机体系结构中的位置可以分为三部分，第一部分是运行在用户空间的进程程序；第二部分是用于管理用户空间和内核空间的Linux操作系统和与网络信息传输相关的协议栈；第三部分主要是对于本机制加速报文发送紧密相关两个内核模块packet 模块和vdev 模块。按照整个网络通信过程又可以将其分为两部分，第一部分是负责产生和发送VANET紧急报文的发送终端部分；另一部分是负责接收紧急报文和负责验证整个VANET紧急报文发送机制正常运行的接收终端。一个发送终端，一个接收终端加上整个信息传输过程经过的局域网环境共同组成了一个网络信息传输测试平台。

![](images/98cf41da9d56e1001f34cd1ba930d3dfd33cf96b1fc686015e6c1d2ce9d4c07b.jpg)  
图10紧急报文发送机制详细工作流程

第一部分处于整个网络协议的最高层，它主要负责完成用户的具体要求。它在本机制整体的开发环境中即涉及到了负责产生和发送紧急报文的发送终端又涉及到了负责接收紧急报文和测试整个紧急报文发送机制的接收终端。在三种最主要的关键技术中，它用到的是Linux下socket网络编程技术[9]，实现的是整个网络信息的传输的整体过程。具体拆解开可以分为相互独立的三个进程，它们分别是运行在发送终端实现TCP紧急报文生成和发送的TCP报文发送进程(tcpclient)，运行在接收终端实现经过netfilter 架构截获却不做任何处理再次正常传输TCP紧急报文的TCP报文接收进程(tcpserver)，运行在接收终端实现经过netfilter架构捕获和处理，然后在虚拟设备中被重新组装成UDP 紧急报文，最后由虚拟设备直接指向网卡(eth0)发送的UDP 紧急报文的UDP 报文接收进程(udpserver)。

第二部分是用于管理用户空间和内核空间的Linux操作系统和与网络信息传输相关的协议栈。在本文提出的紧急报文发送机制中没有作修改，还是使用的TCP/IP协议栈工作。

第三部分，运行在内核空间与本机制加速报文发送方法密切相关的两个内核模块，分别是包含了Linux下netfilter架构技术的packet 模块和实现虚拟设备技术的vdev 模块。在packet模块中，主要应用的技术是Linux下netfilter架构技术。首先，将packet 模块用insmod 命令加载到Linux 内核中，接下来通过使用netfilter架构提供的钩子(HOOK)函数NF_IP6_LOCAL_OUT捕获相关的TCP报文，然后将其存储到结构体 skbuff中，接着应用指针移动获得其中要传输的数据信息data，并将这些数据信息data传递给vdev 模块，同时整个netfilter架构返回值为NF_ACCEPT，意味着所捕获的TCP紧急报文又原样返回到被捕获处继续按照传统的发送机制进行了发送，说明从发送终端发送出含有相同信息的 TCP格式和UDP格式两种紧急报文。所有任务完成后就可以执行rmmod命令卸载packet模块。这样packet模块就完成了属于它负责的获取报文信息和将紧急信息传递给 vdev 模块的两个主要作用。vdev 模块首先要被加载到内核中，使用insmod命令，判断是否成功使用lsmod命令，然后通过packet模块调用vdev 模块中的函数vdev_module_rx(data)将 packet 模块获取的TCP紧急报文中有用信息传输给vdev 模块，vdev 模块通过函数vdev_module_rx将获取的有用信息重新组转换成UDP紧急报文，然后在函数vdev_module_rx中调用函数vdev_xmit将重新组装的UDP报文直接指向网卡(eth0)直接发送出去。任务完成后，vdev模块就可以被rmmod命令卸载了。经过上述流程后，vdev 模块就完成了属于它负责的从packet 模块中获取有用信息、将这些有用信息重新组装成UDP紧急报文和最终直接指向网卡(eth0)发送出去的三个主要作用。

本文实现了VANET紧急报文发送方法测试程序，它工作在一个局域网范围内，网内相互通信的两台主机间都配置IPv6协议栈。发送终端只运行一个TCP报文发送进程(tcpclient)，将存储在文本文件中的涉及行车安全问题的紧急报文生成并发送出去，而在接收终端同时运行的负责接收TCP紧急报文的TCP报文接收进程(tcpsever)和负责接收UDP紧急报文的UDP报文接受进程会收到包含相同紧急信息的报文。运行测试结果可知，TCP紧急报文接收进程和UDP紧急报文接收进程都接收到了紧急报文信息，表明本文所研究与实现的VANET紧急报文发送机制准确的完成了发送紧急报文的功能。此外，在实际运行过程中可以体会到UDP紧急报文接收进程接收到的报文的速度快于TCP紧急报文接收进程的速度，可以有效地的降低紧急报文的传输延迟时间。

# 3 结束语

VANET紧急报文发送机制是一个全新的研究领域，涉及通信技术、网络技术、计算机技术和交通技术等很多方面的知识。本文深入研究和分析了报文发送机制，并给出了一个VANET紧急报文传输方法。该方法通过netfilter架构的钩子函数截取得到报文的数据信息，再利用Linux虚拟设备重新组装安全警告信息报文，并直接指向物理网卡发送到目的接收终端。该方法在传输车载自组织网络的紧急报文时，可以越过TCP/IP协议的传输层与IP层的打包过程；同时使用专门的系统内核模块处理紧急报文可以方便的抢占CPU，省去进程排队的时间。

与通过路由转发协议[12]相比，紧急报文传输机制在车辆发生事故或其他紧急情况时，紧急报文处理模块快速产生相应的紧急报文，或者由拥有权限的用户进程调用紧急报文处理模块产生紧急报文；在发送阶段将紧急报文控制在20字节内交付网络接口层进行广播；在接收阶段，通过TCP/IP协议的网络层和紧急报文处理模块，当紧急报文处理模块收到紧急报文时，对应的系统进程抢占CPU资源，优先处理安全相关的紧急报文。

本文的主要贡献有：

a）制定了相对完整VANET紧急报文发送机制的解决和实施方案；b)选择合适的软硬件环境来进行本紧急报文发送机制的开发。分别选取了RedHat9.0的linux作为开发平台的操作系统和纯IPv6测试环境；c）利用socket网络编程技术完成了应用于VANET紧急报文发送机制的高层应用程序开发；d)设计了一个紧急报文格式，可以有效区分紧急报文和普通报文，为VANET紧急报文发送机制的提出做了准备；e）利用Linux下的netfilter架构技术实现了VANET紧急报文发送机制中紧急报文信息的捕获；f）运用netfilter架构技术处理紧急报文信息重新组装成UDP紧急报文，并直接指向网卡发送出去，做到快速转发。

# 参考文献：

[1]Rene O,Carlos M,Azzedine B,et al.Reliable datadissemination protocol for VANET trafc safety applications [J].Ad hoc Networks,2017,63:30- 44.   
[2]Jun Tao,Yifan Xu,Ziyi Zhang,et al.A resource allocation game with restriction mechanism in VANET cloud [J].Concurrency & Computation Practice & Experience,2016,29(14).   
[3]Barakat P M, Tarek R S,Khaled S.Performance study of manet routing protocols in VANET[J].Arabian Journal for Science & Engineering,2016: 1-12.   
[4]Tariq E,Layth AKAD,Yamaan M.Review and performance comparison of VANET protoCols:AODV,DSR,OLSR,DYMO,DSDV& ZRP [C]// Proc of AIC-MITCSA.2016:1-6.   
[5]Raj KJ,Jaidhar CD.Location prediction algorithm for a nonlinear vehicular movementin VANET using extended Kalman filter[J].Wireless Networks, 2016: 1-16.   
[6]Lochert C,Hartenstein H, Tian J,et al.A routing strategy for vehicular ad hoc networks in city environments [C]//Proc of IEEE Intelligent Vehicles Symposium.2003,156-161.   
[7]Sharma HL,Agrawal P,Kshirsagar R V.Multipath reliable range node selection distance Vector routing for VANETT: design approach [C]//Proc of International Conference on Electronic Systems, Signal Processing and Computing Technologies.2014: 280-283.   
[8]Feng Huifang,Liu Chunfeng,Shu Yantai,et al. Location Prediction of Vehicles in VANET Using A Kalman Filter [J].Wireless Personal Communications,2015,80 (2): 543-559.   
[9]杨秋黎，金智.Windows 网络编程[M].2版.北京：人民邮电出版社, 2015.   
[10]朱金奇，马春梅，刘明，等．车载自组织网络中基于停车骨干网络的数 据传输[J].软件学报,2016,27(2):432-450.   
[11]冯硕.VANET中紧急报文路由机制研究[D].长春：吉林大学,2014.   
[12]徐波，徐守志，郭鹏飞，等．基于最短时延优先的交通安全预警 VANET路由协议[J].华中科技大学学报：自然科学版.2013,41(S2): 242-246.