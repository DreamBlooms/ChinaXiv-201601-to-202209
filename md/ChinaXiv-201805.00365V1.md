# 虚拟化与数字仿真融合的网络仿真任务划分

吴文燕la，姜鑫²，王晓锋la，刘渊1b

(1．江南大学a.物联网工程学院;b.数字媒体学院，江苏无锡 21412;2.江南计算技术研究所，江苏无锡 214083)

摘要：为提升网络仿真性能，面向虚拟化与数字仿真融合的网络仿真体系架构，研究相应的网络仿真任务划分方法。综合考虑虚拟化与数字仿真各自优势，将网络拓扑分为虚拟化拓扑区域与数字仿真拓扑区域，结合给定物理资源，以负载均衡与远程通信量最小化为目标，对两种区域进行融合划分。实验表明，通过该方法进行网络仿真任务划分相对于随机算法与均衡负载平衡算法，远程通信量分别平均降低 $3 3 . 7 \%$ ， $2 5 . 1 \%$ ，负载均衡度分别平均提升 $56 . 3 \%$ ， $3 8 . 0 \%$ 。该方法可有效降低远程通信量与提升负载均衡度。

关键词：虚拟化；数字仿真；融合仿真；任务划分；远程通信量；负载均衡度 中图分类号：TP393 doi: 10.3969/j.issn.1001-3695.2017.09.0943

# Task dividing of network emulation for fusion of virtualization and digital simulation

Wu Wenyanla, Jiang Xin², Wang Xiaofengla, Liu Yuan1b (1.a.SchoolofInterntofingsEngineering,b.hoolofigitalMedia,JiangnanUniversityWuxiJiangsu21Cina; 2.Jiangnan InstituteofComputing Technique,Wuxi Jiangsu 214083, China)

Abstract:Researchedon the task dividing method based on thearchitectureof thenetwork emulation for the fusionof virtualizationanddigitalsimulationtoimprovetheperformance.This methodtook intoaccounttheadvantagesofvirtualization anddigitalsimulation,andtheemulation network topologywas divided intovirtualization topologyareaanddigitalsimulation topologyarea,andthen divided thetwotopologyarea combined with given physicalresources aimingatloadbalancing and remotetraffic minimizing.Extensiveexperiments showedthatusingthe methodtodividethenetworkemulationtask,theremote traffic was reduced by $3 3 . 7 \%$ 0 $2 5 . 1 \%$ averagely,and the degree of load balancing was improved by $56 . 3 \%$ $3 8 . 0 \%$ averagely, compared with therandomalgorithmand theuniform loadbalancing algorithm.The task dividing methodcanefectivelyeduce the remote trafic and improve the degree of load balancing.

Key Words: virtualization; digital simulation; fusion emulation; task dividing; remote traffic; degree ofload balancing

# 0 引言

网络技术研究与信息系统安全评估平台为计算机技术与网络安全评估提供了有力支撑，而网络仿真技术是整个平台的基石。但是，如何进一步提高网络研究实验中的大规模性与高逼真性仍是目前亟需解决的问题，针对此问题，虚拟化与数字仿真融合的网络仿真技术成为网络研究新的趋势。例如，文献[1]综合分布式网络模拟技术以及基于虚拟化的网络仿真技术，实现了模拟、仿真相融合的实验平台，重点研究了网络模拟与网络仿真间的同步问题；文献[2]针对网络实验中路由器仿真的规模性、扩展性以及逼真度的问题，结合虚拟化技术和数字仿真技术，提出了一种虚拟化的路由仿真平台设计方法；文献[3,4]结合虚拟化平台技术，通过将物理资源虚拟化，并将多个全功能网络节点和模拟通信链路实体部署在虚拟机层面，设计了一种网络仿真准实验测试床；文献[5]提出了一个集成了虚拟化仿真系统和并行离散事件网络模拟器的网络测试平台，设计了一个全球同步的算法来管理虚拟时间与仿真时间的转换。

面向大规模网络仿真的性能需求，如何实现合理、有效的网络仿真任务划分方法，保证待划分拓扑与计算集群间的有效映射以及在合理利用物理资源的基础上降低计算集群间的通信开销、满足负载平衡是关键。文献[6]综合考虑了具体的同构计算环境和所要模拟的网络模型，将负载平衡、通信开销与同步开销最小化作为划分目标；文献[7]重点分析了如何有效评估所要仿真的网络拓扑中各网络节点的数据包转发量，并以此作为基础，研究了分布式网络仿真平台的数据包转发模拟任务的负载平衡方法；文献[8]以流量估计为基础，研究了基于抽象消减的网络模拟拓扑划分方法，以此来均衡数据包转发模拟任务，减少远程链路数，并提高网络拓扑划分效率；文献[9]提出了一种基于多项式时间复杂度的负载均衡划分算法，该方法能在均衡负载的同时尽可能的减少通信消耗；文献[10]提出了一种基于虚拟拓扑预配置及可重用技术的虚拟网络映射算法以提高映射公平性，将虚拟网路映射过程分为两个步骤：拓扑预配置过程和映射过程，该算法在物理网络资源利用率、收益/成本比及虚拟网络接受公平性等方面优于部分同类算法；文献[11]为加强测试资源集中管理，结合实际中ATF(automation testframework，自动化测试框架)拓扑映射，提出了智能云测试平台自动拓扑映射实现的方法，该拓扑映射算法扩展性及保密性较好，在发现效率、准确性、有效性上有了很大提高；文献[12]针对网络虚拟化环境中的能耗问题，根据网络拓扑属性以及底层物理网络中物理节点和网络设备的能耗特性，建立网络拓扑一致、高效节能的虚拟网络映射模型，将相邻的虚拟节点映射到能耗增幅较小的邻接物理节点上，同时协调使用最小能耗路由算法，将虚拟链路映射到能耗最小的物理路径上，该算法有效地提高了休眠物理节点和休眠物理链路数量,显著地降低了虚拟网络映射的资源代价和系统能耗。

以上网络仿真任务划分方法兼顾了物理资源利用率与仿真性能，但都是基于单一的虚拟化或数字仿真技术，并未考虑到虚拟化与数字仿真融合的网络拓扑划分情况。但是，在实际网络环境下，一个网络拓扑中往往有不止一种网络节点，进行网络仿真实验时，不同的网络节点使用不同的网络映射方式，因此融合网络拓扑划分方法就显得尤为重要。

鉴于虚拟化与数字仿真融合的网络仿真是一种趋势，本文面向基于云计算平台构建的虚拟化与数字仿真融合的网络仿真体系架构，针对性的研究了虚拟化与数字仿真融合的网络仿真任务划分方法。该方法兼顾了网络拓扑中的虚拟化与数字仿真节点，并在尽可能确保计算集群间负载平衡的基础上大大降低计算集群间的远程通信开销，提升了融合网络仿真的性能。

# 1 虚拟化与数字仿真融合的网络仿真分析

# 1.1虚拟化与数字仿真融合的网络仿真体系架构

如图1所示，是基于OpenStack云平台的虚拟化与数字仿真融合的网络仿真体系架构。OpenStack 的基本架构包括一个控制节点，一个网络节点和若干个计算节点，控制节点负责系统的管控功能，网络节点负责提供诸如DHCP(dynamic hostconfigurationprotocol，动态主机配置协议)服务和路由服务等网络服务，计算节点负责为虚拟主机的建立提供资源。在OpenStack云平台上进行面向虚拟化与数字仿真两个尺度融合的网络仿真，而实现融合网络仿真的关键在于解决虚拟化、数字仿真和OpenStack平台的虚实互联、路由配置与运行协议等问题。虚实互联技术可以实现虚拟化、数字仿真与OpenStack平台的无缝连通，路由配置与TCP/IP协议族则是融合仿真时数据包正常存储转发的基础。

![](images/cd64e96411040c52afd0b11409607a83a4a0bb3a36d49b102fcdd57c36fea570.jpg)  
图1虚拟化与数字仿真融合的体系架构

# 1.2虚拟化与数字仿真融合的网络仿真性能分析

虚拟化与数字仿真融合的网络仿真技术是基于OpenStack云平台来部署虚拟化与数字仿真融合的网络拓扑。本文中使用$\mathrm { K V M } ^ { [ 1 3 ] }$ (kernel-based virtual machine)虚拟化技术来部署虚拟化节点，KVM在Linux内核部署，任何场景下都可以直接和硬件进行交互，而不需要修改虚拟化的操作系统，可以方便控制虚拟化进程；使用 $\mathrm { N S } 3 ^ { [ 1 4 - 1 6 ] }$ 仿真技术来部署数字仿真节点的，NS3是一个极具特色的新型网络模拟器，具有完备性、开源性、易用性和可扩展性等方面的特色，优于现有的大多数主流网络模拟器。

图2为在OpenStack云平台中实验测试KVM节点和 NS3节点的吞吐量对比图，从实验结果可得出KVM节点的吞吐量要远远优于NS3节点；图3为一个16G内存，24逻辑CPU配置的计算节点可以启动的KVM节点（4G内存，2逻辑CPU)与 NS3节点数量对比图，从实验结果可以得出NS3节点的规模性远远优于KVM节点。

![](images/60285617585e44d72b27abd2f26eedcc10048a3b50ed39701b280ddd9206fa60.jpg)  
图2吞吐量对比图

![](images/dcf6734d6ead26b6dc62e22af0397dde2ca485135a88a0c182b49f6bb78d5d59.jpg)  
图3启动个数对比图

总的来说，KVM吞吐量高，但由于KVM节点在保证正常工作情况下的启动个数受计算节点内存大小和逻辑CPU个数限制，所以一个计算节点能够启动的KVM节点数比较少，成个数级；而NS3吞吐量低，在保证正常工作情况下的启动个数虽然也受计算节点逻辑CPU个数的限制，但是计算节点的内存大小对它的启动个数几乎没有影响，一个高性能计算节点上能同时运行数千个NS3仿真节点。所以，KVM逼真度优于NS3，但是规模性是NS3优于KVM，因此面向虚拟化与数字仿真融合的网络仿真技术，可有效解决仿真网络的逼真性和可伸缩性需求。

# 1.3融合的网络仿真任务划分问题描述

虚拟化与数字仿真融合的网络仿真任务划分方法充分考虑了不同节点间的差异性与不同节点组成的链路间通信量的需求，在尽可能节约物理资源的基础上，从计算环境整体角度，综合考虑计算节点的负载均衡与计算集群间的远程链路通信量，以此为依据进行网络仿真拓扑的快速准确划分。

一个网络拓扑中会有不同的节点类型，总体可分为路由节点和主机节点，而路由节点又可分为终端路由节点和非终端路由节点，网络拓扑中的终端路由节点在去掉与主机节点相连的链路以后，只与拓扑中另外一个节点相连，即度为1。一个网络拓扑中，不同类型的节点可以使用不同的映射方式，本文算法主要从吞吐量与规模性两方面来考虑不同类型的节点适用的映射方式。

基于KVM节点和NS3节点的优缺点，本文提出了虚拟化与数字仿真融合的网络仿真任务划分方法。根据实际网络情况可知，网络拓扑中的终端路由节点和主机节点的通信量较小，负载也较小，而非终端路由节点的通信量较大，负载也较大，且主机节点数目远远超过路由节点数目；基于上述特点，将所要划分的网络拓扑中的终端路由节点与主机节点采用NS3进行映射，将非终端路由节点采用KVM进行映射。

# 2 虚拟化与数字仿真融合网络仿真任务划分方法

# 2.1分布式网络仿真任务划分

网络仿真任务划分的原理是将网络仿真拓扑分成多个子网，每个子网的仿真任务分别交给不同的计算节点来执行，而各子网之间的通信则通过计算节点之间的真实链路实现。如图4所示，是一个简单的分布式网络仿真任务划分模型，描述了同构计算环境下的网络仿真任务划分问题。图4中N为所要仿真的网络拓扑中的拓扑节点总数，W为所要仿真的网络拓扑中的各拓扑节点负载之和(一个拓扑节点的负载为该拓扑节点的权值)。设同构计算环境中共有M个计算节点，分别用计算节点1\~M表示。在总网络拓扑划分后，计算节点1\~M所分配到的拓扑节点个数分别为 $\mathrm { \ n l { \sim } n M }$ ，所分配到的拓扑节点的负载之和分别为w1\~wM。其中每个计算节点所分配到的拓扑节点个数反映计算节点被分配的路由仿真任务量，每个计算节点所分配到的拓扑节点负载之和反映计算节点被分配到的数据包转发仿真任务量。

![](images/b54c8f9f54502c3e065af35d51c956298b8b7add3dfea9f67e765c6d0d3aefca.jpg)  
图4分布式网络仿真任务划分模型

本文中待划分的网络仿真拓扑，非终端路由节点由虚拟化节点映射，终端路由节点和主机节点由数字仿真节点映射。并且虚拟化与数字仿真融合的网络仿真任务划分的目的是使整个计算环境中负载平衡与通信开销最小，这里的通信开销主要是指远程链路之间的通信开销，因为在分布式网络仿真中，网络拓扑被划分为一些小的拓扑，原来的网络拓扑之间的链路被划分开并作为远程链路分派到不同的计算节点上，这样数据包在转发时的开销就会显著增加。

# 2.2虚拟化与数字仿真融合的网络仿真任务划分算法

虚拟化与数字仿真融合的网络仿真任务划分算法步骤如下，划分时只划分终端路由节点和非终端路由节点，主机节点划分在与之相连的终端路由节点的划分结果中。

假设有一网络拓扑，其中共有N个路由节点，则分别编号为1\~N，创建矩阵Topo[N][N]用来存储网络拓扑相对负载值信息。例如，编号为i与编号为j的路由节点之间若有链路，则将此链路相对负载值存储在Topo[i-1][j-1]中；若无链路，则Topo[i-1][j-1]的值为0；Topo[i-1][i-1]存储的则是编号为i的路由节点的相对负载值，网络拓扑中路由节点的相对负载值为与此路由节点相连的链路负载值之和。

输入：赋权无向图：G(V,E)，其中点集合： $\mathrm { v } =$ {v1,...,.vj,..,$\mathrm { v N } \}$ ，点权值：wv(vj)，边权值：we(vi,vj);

终端路由节点个数为Z;

非终端路由节点个数为F;

计算节点的计算能力（数据包转发模拟能力)：K；

计算节点的虚拟承受能力（能够启动的虚拟机数)：Q;

计算节点个数（子网数)：M；

输出：划分结果{G1.,...,Gi,., $\mathrm { G M } _ { \mathrm { 3 } } ^ { \mathrm { 3 } }$ 。

算法步骤：

初始化矩阵Topo[N][N],Topo[i-1][j-1]存储编号为i和编号为j的路由节点之间链路的边权值，Topo[i-1][i-1]存储编号为i的路由节点的点权值；

遍历整个网络拓扑，找到拓扑中的终端路由节点，记录Z值，并将终端路由节点的点权值设为1，再将连接终端路由节点的边的边权值设为1，最后记录到矩阵Topo[N][N]中，确保METIS初始划分时，终端路由节点的相对负载值不影响非终端路由节点的划分结果；

遍历整个网络拓扑，找到拓扑中的非终端路由节点，记录F 值，对于每个非终端路由节点，将与它相连接的每条边的边权值记录到矩阵Topo[N][N]中，边权值之和为该路由节点的点权值，也记录到矩阵Topo[N][N]中；

得出拓扑图划分个数即计算节点个数；

编号为i的路由节点的点权值为Topo[i-1][i- $1 ] =$ $\sum _ { j = 0 } ^ { N - 1 } { T o p o [ i - 1 ] [ j ] } ;$ （

$\mathrm { A } { = } \sum _ { i = 0 } ^ { N - 1 } T o p o [ i ] \left[ i \right]$ /K，A取整数，若有小数，则去小

数再加1;

$\scriptstyle { \mathrm { { B = F / ~ Q } } }$ ，B取整数，若有小数，则去小数加1；

拓扑图的划分个数为 $\scriptstyle \mathbf { M } = \operatorname* { m a x } \{ \mathbf { A } , \mathbf { B } \}$ ：

初始化矩阵R[M][N]，R[M][N]记录划分结果；

基于METIS 获得初始划分,METIS 能基于矩阵 Topo[N][N]中的数据，并根据计算节点的数据包转发模拟能力K，计算节点个数M，获得数据包转发模拟任务负载较均衡以及远程通信开销较小的初始划分，设置 $\scriptstyle { \mathrm { l o o p } } = 0$

进行检验，如果每个计算节点上的路由节点权值之和不超过计算节点的计算能力K（阈值1）且每个计算节点上的路由节点数量小于等于一个计算节点上最多可以启动的虚拟化节点数量Q（阈值2)，将划分结果输入到R[M][N]中，然后进行步骤 8；如果以上两个条件有任何一个条件没有满足，则进行步骤9;

遍历拓扑，将终端路由节点划分到与该终端路由节点相连的非终端路由节点所在的划分结果中，进行步骤16；之所以这样做是因为终端路由节点的负载较小，不会对计算节点的负载之和造成很大影响导致负载不均衡或超过K值(即阈值1)，且终端路由节点为数字仿真节点，不受Q值（即阈值2)的限制，还可以降低计算集群间的远程通信开销；

将路由节点权值之和不超过阈值1、路由节点数量等于阀值2的计算节点的划分结果输入到R[M][N]中，符合条件的划分结果中的路由节点的点权值和与之相连的边的边权值都设为1,记录到Topo[N][N]。如果Topo[N][N]中有路由节点与R[M][N]中的路由节点有相连边，则相连边的边权值随之变成1，并重新计算该路由节点的点权值;如果Topo[N][N]的值有新的变化，说明有新的符合条件的划分结果，返回步骤6再次划分，否则进行步骤10；

loop=loop $^ { + 1 }$ ，返回步骤6，直到loop $\scriptstyle 1 = 5$ ，即进行了5次划分结果无变化的划分且还有不符合条件的划分结果，则转入步骤11，进行微调；

选取超过阈值（任意一个阈值）的划分子网上的拓扑节点集Vc，该集合中的节点必须与待接收(低于阈值(所有阈值))计算节点中的某个节点之间存在链路，如果没有链路存在，则Vc为超过阈值的划分子网上的所有拓扑节点组成的集合；

针对Vc，选取其中点权值最小的拓扑节点，并构成集合Vc

（点权值最小的拓扑节点可能有多个)，之所以选取点权值最小的拓扑节点，是因为要使得拓扑节点迁移对数据包转发模拟任务负载平衡的影响最小；

选取Vc中与待迁移（超过阈值）划分子网中其他拓扑节点之间链路权值和最小的拓扑节点（如果有多个满足条件的节点则随机选取其中的一个）作为最合适移动的节点vm，之所以这么选择是因为要使得拓扑节点迁移后新增的远程通信开销最小。

选取vm进行节点迁移；

返回步骤7进行检验；

输出划分结果{G1.,..,Gi,..,GM}。

# 3 实验验证与分析

实验环境：一套OpenStack平台，包含1个控制节点，1个网络节点，8个计算节点，计算节点均为服务器R730，CPU类型为2个IntelE5620处理器，且均为24逻辑CPU，16G内存配置，计算节点的吞吐量均为 $2 2 0 0 0 \mathrm { M / s }$

拓扑场景：具体的，通过拓扑生成工具，生成3组网络拓扑。第一组网络拓扑共有2026个网络节点，其中26个为路由节点，编号为1\~26，路由节点中非终端路由节点为22个，终端路由节点为4个，并且该拓扑中每一个终端路由节点上均连接500个主机节点；第二组网络拓扑中共有4027个网络节点，其中27个为路由节点，编号为1\~27，路由节点中非终端路由节点为19个，终端路由节点为8个，拓扑中每一个终端路由节点上均连接 500个主机节点；第三组网络拓扑中共有2530 个网络节点，其中30个为路由节点，编号为1\~30，路由节点中非终端路由节点为25个，终端路由节点为5个，拓扑中每一个终端路由节点上均连接500个主机节点。基于上述实验环境，将生成的3组网络拓扑分别部署在此同构计算环境下。

本文算法是基于虚拟化与数字仿真融合的网络仿真任务划分算法，且由于该算法的独特性，主机节点对远程链路通信量没有影响，所以对网络拓扑的划分落实在对拓扑中路由节点的划分上。

算法1均衡负载平衡算法ULB

针对给定的计算环境，METIS划分能获得数据包转发仿真任务与路由仿真任务负载较均衡的划分结果，将面向数据包转发仿真任务与路由仿真任务负载均衡的METIS划分算法称为ULB算法；

定义1远程链路通信量RLT。用于评判网络拓扑仿真运行时，各计算节点数据包转发仿真任务远程链路通信量的情况，RLT值越小，则表明依据算法得到运行结果的计算节点的远程链路通信量越小。

定义2总远程链路通信量TRLT。各计算节点远程链路通信量的累加和为计算集群的总远程链路通信量TRLT，TRLT值越小，则表明依据算法得到运行结果的计算集群的总远程链路通信量越小。

定义3算法负载均衡度DLB。用于评判网络拓扑仿真运行时，各计算节点路由仿真任务综合负载均衡情况，该值越趋近于0，则表明该计算环境路由仿真任务负载越均衡。用如下公式描述：

$$
D L B = { \sum _ { i = 1 } ^ { n } } { \frac { 1 } { \mathfrak { n } } } ( x _ { i } - { \overline { { x } } } ) ^ { 2 } ;
$$

因为实验拓扑是虚拟化与数字仿真融合的网络拓扑，且数字仿真节点的吞吐量远远低于虚拟化节点的吞吐量，所以本文主要考虑虚拟化路由节点对路由仿真任务负载均衡的影响，因此公式中， $\mathfrak { n }$ 为使用到的计算集群规模， $x _ { i }$ 为各计算节点上所部署的虚拟化路由节点个数， $\overline { { x } }$ 为计算节点上所部属的虚拟化路由节点个数的期望值。由负载均衡度公式计算得出的数值越小，负载均衡度越高，反之亦然。

基于给定实验环境和网络拓扑使用虚拟化与数字仿真融合的网络仿真任务划分算法进行拓扑划分，依据算法划分结果，在Opentack 平台上实施部署。为了验证部署在Openstack 平台上的虚拟化与数字仿真融合的网络拓扑确实可以如真实的网络拓扑一样通信，用融合网络拓扑中的不同主机互相执行ping 命令，结果显示融合网络拓扑中的主机可以互相ping通。从测试结果来看，本文提出的算法可以快速划分给定的融合网络拓扑，且根据算法得出的划分结果，可以将融合网络拓扑高逼真度地部署在 Openstack 平台上。

将融合算法的运行结果的总远程链路通信量与随机算法的划分结果以及ULB算法的划分结果进行比较。三组网络拓扑依据融合算法和随机算法、ULB算法得到的划分结果的计算集群的总远程链路通信量对比如图5所示，其中，第一组网络拓扑通过融合算法得出的划分结果的TRLT $= 1 6 2 0 6$ ，随机算法得出的划分结果的TRLT $\scriptstyle \mathbf { \dot { \mu } } = 3 0 0 6 4$ ，ULB算法得出的划分结果的TRLT $= 2 3 2 3 0$ ，第二组网络拓扑通过融合算法得出的划分结果的TRLT $= 1 2 2 9 6$ ，随机算法得出的划分结果的TRLT $\mathbf { \bar { \rho } } = \mathbf { \rho }$ 19646，ULB算法得出的划分结果的 $\mathrm { T R L T } { = } 1 7 3 6 8$ ，第三组网络拓扑通过融合算法得出的划分结果的 $\mathrm { T R L T } { = } 2 7 5 7 0$ ，随机算法得出的划分结果的TRLT $\scriptstyle = 3 3 6 3 4$ ，ULB算法得出的划分结果的TRLT $\scriptstyle \mathbf { \dot { \varepsilon } } = 3 3 0 1 0$ U经计算得出融合算法相对于随机算法与ULB算法，划分结果的总远程链路通信量分别平均降低 $3 3 . 7 \%$ ， $2 5 . 1 \%$ 。

![](images/ceb8abe7d4fe057f748a0b1910e9dedd0287fcf2b98b27cd38741d98bcd54d99.jpg)  
图5总远程链路通信量对比图

由实验结果可知，融合算法是优化的网络任务划分方法，可以减少计算集群间的总远程链路通信量。图6\~8分别是三组网络拓扑依据不同算法得到的划分结果的各个计算节点的远程链路通信量对比图。从图5与图6\~8的对比可知，通过融合算法进行划分得出的结果，虽然各个计算节点的远程链路通信量不一定小于随机算法划分结果或ULB 算法划分结果，但是计算集群的总远程链路通信量明显小于后两者。而且，因为本文算法是虚拟化与数字仿真融合的网络仿真任务划分算法，依靠该算法划分得出的结果可以节省计算资源，如图6所示，随机算法划分结果以及ULB算法划分结果均比本文算法划分结果多出1个计算节点，如图7所示，随机算法划分结果以及ULB算法划分结果均比本文算法划分结果多出2个计算节点，如图8所示，随机算法划分结果以及ULB算法划分结果均比本文算法划分结果多出1个计算节点。

![](images/e34f35b1bae73881badaff92e0e98a89327d1b8d2d8b5debfee381631d87d874.jpg)  
图6第一组网络拓扑远程链路通信量对比图

![](images/f75bf0460babf6f6d4c1abe990a16096ddd008f2e01e13815b876a00773289c2.jpg)  
图7第二组网络拓扑远程链路通信量对比图

![](images/ca453dcf6a6ecae43d10b3cfd2454333e3820a10fd774b1bcf0ba3a7a595bffc.jpg)  
图8第三组网络拓扑远程链路通信量对比图

除了远程链路通信量，本文还就计算集群的负载均衡度进行了计算。第一组网络拓扑通过融合算法得出的划分结果的$\mathrm { D L B } { = } 0 . 2 2$ ，随机算法得出的划分结果的 $\mathrm { D L B } { = } 0 . 4 1$ ，ULB 算法得出的划分结果的 $\mathrm { D L B } { = } 0 . 3 9$ ，第二组网络拓扑通过融合算法得出的划分结果的 $\mathrm { D L B } { = } 0 . 1 6$ ，随机算法得出的划分结果的DLB $_ { - 0 . 5 8 }$ ，ULB 算法得出的划分结果的 $\mathrm { D L B } { = } 0 . 3 7$ ，第三组网络拓扑通过融合算法得出的划分结果的 $\mathrm { D L B } { = } 0 . 5 3$ ，随机算法得出的划分结果的 $_ { \mathrm { D L B = 1 } . 0 8 }$ ，ULB算法得出的划分结果的DLB $\scriptstyle \mathsf { \bar { \rho } } = 0 . 6 1$ ，对比如图9所示。经计算得出融合算法相对于随机算法与ULB算法，划分结果的负载均衡度分别平均提升 $56 . 3 \%$ $3 8 . 0 \%$ 。

![](images/9c2c5308967ecbb9c8796aae8519831c78337ecc6a7dc5129f01e7346aab267a.jpg)  
图9负载均衡度对比图

虚拟化与数字仿真融合的网络仿真任务划分算法的优越性在于，不但将METIS划分结果通过节点迁移进行优化，降低了融合算法的负载均衡度；而且由于终端路由节点划分在与终端路由节点相连接的非终端路由节点所在的划分结果中，不存在终端路由节点对远程链路通信量的影响，降低了融合算法的远程链路通信量。此外，依据虚拟化与数字仿真融合的网络仿真任务划分方法对以上3组网络拓扑进行划分所用的运行时间均小于1s。由此可见算法的时间复杂度并不高，可以适用于更大规模的网络拓扑。

# 4 结束语

网络仿真是当前进行网络研究的主要方法，虚拟化与数字仿真融合的网络仿真方法是网络研究新的趋势。本文重点研究了虚拟化与数字仿真融合的网络仿真任务划分算法，该算法能在节约计算资源的基础上有效降低计算集群间的远程链路通信量、提升计算集群的负载均衡度。在下一步的研究中，将重点考虑虚拟化与数字仿真融合的网络仿真任务划分方法在网络安全实验中的应用。

# 参考文献：

[1]Jin Du,ZhengYi,Nicol DM.A parallel network simulation and virtual timebased network emulation testbed[J].Journal of Simulation,2014,8(3): 206-

214.   
[2] 黄敏桓，张尧学，许飞，等．基于虚拟化技术的路由仿真实验平台设计 [J]．系统仿真学报,2014,26(8):1672-1677.   
[3] 黄锦松，杨艺，王文鼐．一种基于虚拟化平台的网络仿真准实验床[J]. 计算机技术与发展,2015,08(9):208-212.   
[4]何新华，金国柱，王琼．仿真实验中的虚拟化技术应用[J].兵器装备 工程学报,2011,32 (8):71-73.   
[5]Gu Yun,FujimotoR.Applyingparallanddistributedsimulationtormote network emulation [C]// Proc of Winter Simulation Conference.2007: 1328- 1336.   
[6]Xu Ding,Ammar M.BencHMAP: Benchmark-based, hardware and modelaware partitioning for parallel and distributed network simulation [C]/ Proc of International Symposium on Modeling,Analysis,and Simulation of Computer and Telecommunications Systems. Washington DC: IEEE Computer Society, 2004: 455-463.   
[7]Wilinger W,Taqqu M S, Sherman R,et al. Self-similarity through highvariability: statistical analysis ofethernet LAN traffc at the sourcelevel[J]. IEEE//ACM Trans on Networking,1997,5 (1): 71-86.   
[8]Peschlow P，Honecker T, Martini P.A flexible dynamicpartitioning algorithm for optimistic distributed simulation [C]// Proc of International Workshop on Principlesof Advanced and Distributed Simulation.2007: 219-228.   
[9] Grande R E D,Boukerche A,Ramadan H.Distributed re-arrangement scheme for balancing computational load and minimizing communication delays in HLA-based simulations [J]. Concurrency& Computation Practice & Experience,2013,25 (5): 626-648.   
[10]王聪，苑迎，彭三城，等．基于拓扑预配置的公平虚拟网络映射算法 [J]．计算机研究与发展,2017,54(1):212-220.   
[11]王亮，韩连钢，谢锡海．智能云测试下拓扑映射算法实现的研究[J]. 电子技术应用,2017,43(3):116-119.   
[12]彭利民．拓扑一致性绿色虚拟网络映射算法[J].小型微型计算机系统, 2016,37 (5): 1079-1083.   
[13] Qumranet A K, Qumranet Y K,Qumranet D L,et al. kvm: the Linux virtual machine monitor[J]. Proc Linux Symposium,2012,10(7):104-112   
[14] Kumar S,Paul S,Amar A K.Communication in vehicular cloud network using ns3[J].International Journal ofControlTheory& Applications,2017, 12 (4): 159-167.   
[15]Riley G F,Henderson TR.The ns-3 network simulator[J].Modeling& Tools forNetwork Simulation,2010,20(5):15-34   
[16]Font JL,InigoP,Dominguez M,etal.Analysisofsource code metrics from ns-2 and ns-3 network simulators [J]. Simulation Modelling Practice & Theory,2011,19 (5): 1330-1346.