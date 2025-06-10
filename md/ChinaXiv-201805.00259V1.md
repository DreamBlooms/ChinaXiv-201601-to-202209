# 三维片上网络正四面体裂变拓扑结构研究

郑亚振，张大坤

(天津工业大学 计算机科学与软件学院，天津 300387)

摘要：旨在研究新型三维片上网络正四面体裂变拓扑结构，给出了该拓扑结构的生成过程；对该拓扑结构进行了编码设计和路由设计。通过对 gpNoCsim片上网络仿真器进行三维扩展，对正四面体裂变拓扑结构进行性能仿真实验。仿真结果表明，在均匀负载模式下，正四面体裂变拓扑结构的平均延时和平均跳数均低于Mesh结构，当注入率为0.02时，平均延时比Mesh结构低 $1 6 . 8 \%$ 、平均跳数比Mesh结构少 $5 . 5 \%$ ；在局部负载模式下，当注入率大于0.008时，正四面体裂变拓扑结构的平均延时和平均跳数与Mesh结构相比，均有明显改善；当注入率为0.014时，平均延时比 Mesh结构降低 $1 8 . 7 \%$ 、平均跳数比 Mesh 结构减少 $9 . 6 \%$ 。说明正四面体裂变拓扑结构可用于三维片上网络拓扑结构设计。

关键词：三维片上网络；正四面体裂变；拓扑结构；平均延时；平均跳数中图分类号：TP39 doi:10.3969/j.issn.1001-3695.2017.08.0888

# Research on tetrahedron fission topology in three dimensional network-on-chip

Zheng Yazhen, Zhang Dakun (SchoolofComputer Science&Software Engineering,Tianjin Polytechnic University,Tianjin 300387)

Abstract:Thispaperaimstoresearch thetetrahedronfissontopologythatisanewtypeofthr dimensionalNetwork-on-Chip topology,gives generationprocessoftopologyand thedesignofencodingandrouting.Throughathreedimensionalextension of the gpNoCsim which is asimulatoronchip network,the simulation experimentof the tetrahedron fision topology is conducted.Thesimulationresultsshow,tetrahedron fissiontopologycanachievelower average latencyand feweraveragehops than Mesunderuniformtrafficpattrn,Whenthe injectionrateis0.O2,comparing withMesh,theaveragelatencydegrades by （204号 $1 6 . 8 \%$ and the average hops decrease $5 . 5 \%$ ; Under localized traffic pattern,the average delay of tetrahedral fission topology andtheaveragehopsaresignficantlyimprovedwhentheinjectionrateis greaterthanOOo8,Comparing withMesh,tetrahedron fission leads to $1 8 . 7 \%$ decrease of the average latency and $9 . 6 \%$ decrease of the average hops when the injection rate is 0.014. It is shown thatthetetrahedron fisiontopologycan beused in the designofthreedimensional Network-on-Chip topology. Key Words: thre-dimensional network on chip; tetrahedron fission; topology; average latency; average hops

# 0 引言

随着大规模集成电路技术的发展，片上系统(system-onchip,SoC)和二维片上网络(twodimensionalnetwork-on-chip,2DNoC)相继产生。2DNoC 规模逐渐增大，使2DNoC 在面积、功耗、布局布线以及封装密度等方面都达到了瓶颈[11，因而产生了三维片上网络(three dimensional net-work-on-chip,3D NoC),并已成为研究热点[2\~5]。在3DNoC的研究中，拓扑结构是关键问题之一[6]；3DNoC 拓扑结构包括规则拓扑和非规则拓扑两大类，在经典规则拓扑结构基础上进行性能分析的研究较多，如3D Mesh[7]结构和3DTorus[8]结构等，但关于新型非规则 3DNoC拓扑结构的研究较少。与规则拓扑结构相比，非规则拓扑结构可以面向不同的领域，根据特定的应用需求而定制、具有很好的应用前景，这方面的研究已取得了一些进展。如芬兰图尔库大学Yin 等人提出的蜂窝状3DNoC拓扑结构[]；湖南大学贺旭等人提出的三维超立方体片上网络拓扑结构[10]；西安电子科技大学刘有耀等人对NoC拓扑结构与通信方法进行了研究，对典型的3DNoC架构进行了总结，并提出了3种3DNoC的架构，包括提出了三维超立方体双环架构、三维Torus连接的Petersen 图架构、三维长方形扭花环网格架构[1]。本文旨在研究新型非规则3DNoC拓扑结构，提出了正四面体裂变拓扑结构（选题源于国家自然科学基金课题：61272006)。该拓扑结构具有节点度低(恒为3)、对称性好、路由简单等优点，并使网络扩展从“加法"转为"裂变”，可以用于个性化3DNoC拓扑结构设计，研究具有探索性和创新性。

# 1 正四面体裂变拓扑结构及路由设计

# 1.1正四面体裂变拓扑结构生成

正四面体是柏拉图立体之一[12]，正四面体裂变拓扑结构是由正四面体“裂变"而来，带标注的正四面体模型如图1所示。正四面体节点一级裂变拓扑过程为：从图1任选一个节点Noo，从Noo出发沿与之相连的3条棱移动一段距离后生成3个新节点No00、Nooi、Noo2，然后依次相连这3个节点（把互连的3个节点称为裂变簇）并删除 $\mathbf { N o } _ { 0 }$ ，这样就完成了Noo的裂变，Noo裂变过程如图2所示。图中圆圈表示网络节点。一般的网络节点中包含一个路由器和若干个IP 核，IP 核可以是处理器、存储器或具有其他功能的器件，IP核通过本地端口和路由器相连。

![](images/2a723b65cb6ef446310adadb0d67a59e5b492aeebee5a3e2cd7e065ebe70fb72.jpg)  
图1正四面体标注

![](images/b9c1b1d260a7df0d5ac33123c0b6cc3d01699775f6cb02f8187319629d04a78a.jpg)  
图2正四面体节点 $\mathbf { N o } _ { 0 }$ 裂变过程  
图3正四面体裂变拓扑结构球棍模型

按照上述裂变过程依次完成图1中各个节点的裂变和互连，就得到了正四面体裂变拓扑结构。在该结构中有12个网络节点，每个节点的度都是3，有4个裂变簇，用A、B、C和D来表示。正四面体裂变拓扑结构球棍模型如图3所示。

V

# 1.2正四面体裂变拓扑结构节点编码与路由

1）节点编码

合理的节点编码方案能够简化路由协议的复杂度、提高网络性能、降低延时。正四面体裂变拓扑结构是由正四面体裂变而来，为了方便寻址需要给裂变簇A、B、C和D进行编码，该结构中共有12个网络节点需要4bit来编码，各个网络节点的编码是由裂变簇通过向左移动两位加上节点在裂变簇内的编号而生成，具体编码如表1所示。

表1正四面体裂变结构各节点及裂变簇编码  

<html><body><table><tr><td>正四面体节点</td><td>裂变簇</td><td>编码</td></tr><tr><td>Noo节点 Noi节点</td><td>Noo 节点经过裂变后变成裂变簇A，裂 N 00 变簇中有 No0、Noo1、No02三个节点 NOu</td><td>裂变簇A编码为00，其内部节 点编码为 N000：0000，No01: 0001，N002：0010</td></tr><tr><td rowspan="3">No2节点</td><td>Noi节点经过裂变后变成裂变簇B，裂 N010 01 变簇中有 Nolo、Nol1、No12三个节点 No12 No11</td><td>裂变簇B编码为01，其内部节 点编码为N010：0100，Noll:</td></tr><tr><td>No2节点经过裂变后变成裂变簇C，裂 QN020 10 变簇中有 N020、No21、N022三个节点</td><td>0101，No12：0110 裂变簇C编码为10，其内部节 点编码为N020：1000，No21:</td></tr><tr><td>NO21 No22 No节点经过裂变后变成裂变簇D，裂 QN030 11 变簇中有N030、N031、No32三个节点 N031 N032 1100，N031:1101，N032：1110</td><td>1001，No2i：1010 裂变簇D 编码为11, 其内部节点编码为N030:</td></tr></table></body></html>

2）路由器结构设计

在正四面体裂变拓扑结构中，每个网络节点中的器有3个与相邻网络节点连接的端口和若干个本地端口，本设计中每个节点搭载4个IP核，故需要4个本地端口，本地端口的一端与路由器相连，另一端与本地IP核相连。每个端口包括输入通道和输出通道，每个通道可以从相连接的路由器或者IP核接收数据包或者发送数据包。其中每个物理通道又被划分为多个虚通道，一般被划分为2个、4个或8个，本设计选取4个，以便有效地避免死锁。路由器中包括路由逻辑、交换开关和虚通道仲裁单元等，通过路由计算把网络节点接收的数据包发送到正确的输出通道上，物理通道被各个虚通道采用轮转法使用。

# 3）路由算法设计

正四面体裂变拓扑结构中有12个网络节点、4个裂变簇。

表1为正四面体裂变拓扑结构的编码具体情况。由于本结构具有分级的特征，故采用分级路由的思想，其中dest代表目的节点，curr代表当前节点， $a$ 值判断数据包是否到达dest所在的裂变簇，result值判断数据包是否到达dest节点。具体的路由过程如下：

a)数据包中包含有目的节点地址dest，当正四面体裂变拓扑结构节点curr收到一个数据包时，计算resuli $\fallingdotseq$ currdest,其中 $\oplus$ 为异或运算，转向步骤b);

b)判断result值，若result值不为0，则转向步骤Step3，否 则转向步骤 $\mathcal { f }$

c)计算 currA=curr/4，destA $\ c =$ dest/4，currB $\ O =$ curr mod 4,destB $\ c =$ dest mod 4， $\mathbf { a } =$ currA $\oplus$ destA，并判断a的值，若a值不为0，则转向步骤d)，否则转向步骤e);

d)判断currA、destA、destB的值将数据包发送到相邻的裂变簇或者发送到距目的裂变簇最近的节点并将其节点更新为当前节点curr，转向步骤a);

e）目的节点和当前节点在同个裂变簇，然后判断currB和destB的值，将数据包发送到相应的节点并将其节点更新为当前节点curr，转向步骤 $| a \rangle$

$f )$ 数据包已经到达目的节点，则将数据包发送到对应的IP核。

# 2 正四面体裂变拓扑结构性能仿真

# 2.1 仿真实验设计

# 1）仿真平台与实验方案

本实验采用美国切斯特大学Hossain等人研发的gpNoCsim[13]片上网络仿真器，对该仿真器进行了三维扩展，实现了正四面体裂变拓扑结构的编码。将正四面体裂变拓扑与2DMesh结构在同等网络规模下进行仿真实验，比较两种结构的吞吐量、平均延时和平均跳数等性能指标，以验证正四面体裂变拓扑结构的优越性。正四面体裂变拓扑结构共有12个网络节点，故2DMesh网络规模大小需要设置为 $4 { \times } 3$ ，共12个网络节点。每个网络节点中的路由器通过本地端口与4个IP核相连，故两种结构搭载的IP核数都是48个。实验中，2DMesh采用XY路由算法，正四面体裂变拓扑结构变采用本文1.2中所设计的路由算法。实验采用局部负载模式和均匀负载模式进行仿真。均匀负载模式下，网络中的流量分布均匀，每个节点收到数据包的概率相等；局部负载模式下， $70 \%$ 的流量限制在簇内4个IP核中， $30 \%$ 的流量随机地发送到簇外的其他节点。

# 2）参数配置

对gpNoCsim仿真器所有需要的参数进行了设置，其中主要的网络参数配置如下：每个物理通道中虚通道数设置为4，每个虚通道的大小设置为存储4个flit，消息长度设置为200字节，微片长度设置为150位，仿真实验每次运行20000个时钟周期，其中预热期设置为前 $10 \%$ 的时钟。为了使仿真结果更为精确，仿真器在相同的参数配置下重复运行20次，将算术平均值作为仿真结果输出值。

# 2.2 吞吐量对比分析

1）均匀负载模式吞吐量对比分析

通过仿真实验在均匀负载模式下，得到了正四面体裂变拓扑结构和2DMesh结构网络吞吐量的实验数据。分析实验室数据可知，当注入率小于0.016时，此时网络未发生拥塞，两者在相同的注入率下，网络吞吐量基本一致；随着数据包注入率的继续增加，网络逐渐变得繁忙，正四面体裂变拓扑结构将达到饱和状态。对于正四面体裂变拓扑结构，当注入率到达0.018时，网络达到饱和状态，饱和时的吞吐量为0.17；对于2DMesh结构，当正四面体裂变拓扑结构网络达到饱和时，2DMesh结构网络的吞吐量为0.18；正四面体裂变拓扑结构饱和时的吞吐量比2DMesh结构低 $5 . 6 \%$ 。两种拓扑结构吞吐量与注入率的

关系曲线如图4所示。

![](images/9256d5896a51c1d540937d263244b02eef229e3b6f051ad97768a1dbd59aa000.jpg)  
图4均匀负载模式下两种拓扑结构吞吐量的对比

# 2）局部负载模式吞吐量对比分析

在局部负载模式下，对正四面体裂变拓扑结构和2DMesh结构吞吐量实验数据进行分析，当注入率小于0.004时，两种拓扑结构的网络吞吐量基本一致；随着数据包注入率的增加，网络流量也随之增大，两种拓扑结构相继达到饱和状态。对于正四面体裂变拓扑结构，当注入率增加到0.008时，其吞吐量为0.39，网络达到饱和状态；对于2DMesh结构，当注入率增加到0.008时，其吞吐量为0.41，网络达到饱和状态；在饱和状态下，正四面体裂变拓扑结构的吞吐量比2DMesh 结构低$4 . 9 \%$ ；但当网络达到饱和后随着数据包注入率的增加，与正四面体裂变拓扑结构相比，2DMesh结构的吞吐量明显下降，在注入率为0.01时，正四面体裂变拓扑结构的吞吐量比2DMesh结构高 $6 . 1 \%$ ；在注入率为0.012时，正四面体裂变拓扑结构的吞吐量比2DMesh 结构高 $1 6 . 7 \%$ 。两种拓扑结构在局部负载模式下吞吐量与注入率的关系曲线如图5所示。

![](images/faa394e77cd5ee7c04ce64987f0f3de6c31a530bed1443f64b3115748922a293.jpg)  
图5局部负载模式下两种拓扑结构吞吐量的对比

# 2.3 平均延时对比分析

1）均匀负载模式平均延时对比分析

实验室数据表明在均匀负载模式、不同注入率下，正四面体裂变拓扑结构的平均延时均优于比2DMesh结构，但随着数据包注入率的增加，两者的平均延时也随之增加。在注入率为0.016时，正四面体裂变拓扑结构的平均延时比2DMesh结构低 $7 . 2 \%$ ；当注入率为0.018时，正四面体裂变拓扑结构的平均延时比2DMesh结构低 $1 1 . 0 \%$ ；当注入率为0.02时，正四面体裂变拓扑结构的平均延时比2DMesh结构低 $1 6 . 8 \%$ 。两种拓扑结构在均匀负载模式下平均延时与注入率的关系曲线如图6所示。

![](images/424259dc6386b35f07bac130c40d4a97f2c4e5781ab8b8701e9bbdec5eae0a88.jpg)  
图6均匀负载模式下两种拓扑结构平均延时的对比

# 2）局部负载模式平均延时对比分析

在局部负载模式下、注入率较小时，正四面体裂变拓扑结构和2DMesh结构的平均延时均较低；随着数据包注入率的逐渐增加，正四面体裂变拓扑结构和2DMesh结构的平均延时也随之增加；当注入率小于0.008时，正四面体裂变拓扑结构的平均延时增长幅度略大于2DMesh结构；当注入率大于0.008时，与正四面体裂变拓扑结构相比2DMesh结构的平均延时增长幅度较大，这是由于2DMesh结构最外侧节点的节点度较小，当注入率增加时，这些节点更容易发生阻塞，所以处理数据包的等待时间明显增加；当注入率较高时，与均匀负载模式相比，两种拓扑结构在局部负载模式下的平均延时更大，这是由于网络阻塞导致增加的时间要远大于由于平均跳数缩短而减少的时间；注入率为0.01时，正四面体裂变拓扑结构的平均延时比2DMesh结构低 $1 9 . 1 \%$ ；注入率为0.014时，正四面体裂变拓扑结构的平均延时比2DMesh结构低 $1 8 . 7 \%$ 。两种拓扑结构在局部负载模式下平均延时与注入率的关系曲线如图7所示。

![](images/6575a2bb6828c36fc1e1649d50325a55cd5f053747888c60c21ded803ff90644.jpg)  
图7局部负载模式下两种拓扑结构平均延时的对比

# 2.4平均跳数对比分析

1）均匀负载模式下平均跳数对比分析在均匀负载模式、不同的注入率下，2DMesh结构和正四

面体裂变拓扑结构收到数据包的总数、平均跳数的实验数据如表2所示，由实验数据可知，该负载模式下正四面体裂变拓扑结构的平均跳数比2DMesh结构大约减少 $5 . 5 \%$ 。

表2均匀负载模式下两种拓扑结构平均跳数的对比  

<html><body><table><tr><td rowspan="2">注入率</td><td colspan="3">NoC 结构</td></tr><tr><td>2D mesh</td><td></td><td>正四面体裂变结构</td></tr><tr><td></td><td>收包 总数</td><td>平均 跳数</td><td>收包 平均 总数 跳数</td></tr><tr><td>0.002</td><td>1915.30</td><td>4.1807</td><td>1909.00 3.9651</td></tr><tr><td>0.004</td><td>3835.20</td><td>4.1889</td><td>3840.70 3.9547</td></tr><tr><td>0.006</td><td>5626.80</td><td>4.1815 5639.90</td><td>3.9567</td></tr><tr><td>0.008</td><td>7665.80</td><td>4.1836</td><td>7686.85 3.9607</td></tr><tr><td>0.010</td><td>9537.85</td><td>4.1847</td><td>9569.50 3.9573</td></tr><tr><td>0.012</td><td>11668.60</td><td>4.1795</td><td>11637.35 3.9579</td></tr><tr><td>0.014</td><td>13626.65</td><td>4.1856</td><td>13600.05 3.9582</td></tr><tr><td>0.016</td><td>15378.55</td><td>4.1858</td><td>15347.10 3.9568</td></tr><tr><td>0.018</td><td>17329.90</td><td>4.1844</td><td>16515.30 3.9575</td></tr></table></body></html>

# 2）局部负载模式下平均跳数对比分析

在局部负载模式、不同的注入率下，2DMesh结构和正四面体裂变拓扑结构在不同的注入率下收到数据包的总数、平均跳数的实验数据如表3所示。由实验数据可知，该负载模式下正四面体裂变拓扑结构的平均跳数比2DMesh结构约少 $9 . 6 \%$ 。两种拓扑结构在局部负载模式下的平均跳数均小于均匀负载模式下的实验值。

表3局部负载模式下两种拓扑结构平均跳数的对比  

<html><body><table><tr><td colspan="4">NoC结构</td></tr><tr><td>注入率</td><td>2D mesh</td><td>正四面体裂变结构</td><td></td></tr><tr><td>收包 总数</td><td>平均 跳数</td><td>收包 总数</td><td>平均 跳数</td></tr><tr><td>0.002</td><td>1914.65</td><td>2.8193</td><td>1931.10 2.6318</td></tr><tr><td>0.004</td><td>3492.35</td><td>2.8206</td><td>3513.50 2.5953</td></tr><tr><td>0.006</td><td>3927.50</td><td>2.8614</td><td>3804.25 2.5448</td></tr><tr><td>0.008</td><td>3917.40</td><td>2.8245</td><td>3702.50 2.5169</td></tr><tr><td>0.010</td><td>3482.20</td><td>2.7009</td><td>3624.55 2.5015</td></tr><tr><td>0.012</td><td>3146.10</td><td>2.63091 3354.30</td><td>2.5030</td></tr><tr><td>0.014</td><td>3362.05</td><td>2.60823 2900.85</td><td>2.5058</td></tr></table></body></html>

# 3 结束语

目前，3DNoC技术是解决片上系统集成度越来越高带来的通信瓶颈问题的重要手段。拓扑结构则是3DNoC研究的一个重要分支。正四面体裂变结构是一种非规则拓扑结构，本文通过仿真实验将该拓扑结构与2DMesh结构在同等网络规模、相实验同条件下，主要从吞吐率、平均延迟和平均跳数三个方面与2DMesh结构进行了性能对比分析。实验结果表明，在均匀负载模式下、不同的注入率条件下，正四面体裂变拓扑结构与 2DMesh结构相比，平均延时更低、平均跳数更少；在局部负载模式、注入率大于0.008时，正四面体裂变拓扑结构与2DMesh结构相比平均延时更低，在不同的注入率下，正四面体裂变拓扑结构与2DMesh结构相比平均跳数更少；在吞吐量方面两种拓扑结构性能相近。实验表明：本文提出的正四面体裂变拓扑结构用于3DNoC拓扑结构设计是可行的。目前只是在仿真器中实现和分析了正四面体裂变拓扑结构及其性能，今后进一步的工作重点是其物理结构的设计和实现。

# 参考文献：

[1]Zhang Dakun, Song Guozhi,Lin Huazhou,et al. Double improved genetic algorithm and low power task mapping in 3D Networks-on-chip [J].Journal of Computer Research and Development,2016,53 (4): 921-931.   
[2]Dang K N,Meyer M,Okuyama Y,etal.A low-overhead softhard faulttolerant architecture,design and management scheme for reliable highperformance many-core 3D-NoC systems [J]. Journal of Supercomputing, 2017: 1-25.   
[3]Lee D,Das S,Pande PP.Performance-thermal trade-offs fora VFI-enabled 3D NoC architecture [Cl// Proc of International Symposium on Quality Electronic Design.2017:271-276.   
[4]Rezaei S H S,Modarressi M,Daneshtalab M,et al.A Three Dimensinal Networks-on-Chip architecture with dynamic buffer sharing[C]//Proc of Euromicro International Conference on Parallel,Distributed,and NetworkBased Processing.2016:771-776.   
[5]Eghbal A,Yaghini PM,Bagherzadeh N,etal.Analytical fault tolerance assessment and metrics for TSV-Based 3D Network-on-Chip [J].IEEE Trans on Computers,2015,64(12): 3591-3604.   
[6] 张大坤，宋国治，王莲莲，等.三维片上网络拓扑结构研究综述[J]. 计算机科学与探索,2015,9(2):129-164.   
[7]Feero B S,Pande PP.Networks-on-chip in a three-dimensional environment: a performance evaluation [J]. IEEE Trans on Computers,20o9,58(1):32- 45.   
[8]Jiao Jiajia,Fu Yuzhuo,Liu Ting，et al.Performance analysisand optimization for homogenous multi-core system based on 3D torus network on chip [C]//Proc of Newcas Conference.2010: 313-316.   
[9]Yin A W,Xu TC,Liljeberg P,et al. Explorations of honeycomb topologies for network-on-chip [C]//Proc of the 6th IFIP International Conference on Network and Parallel Computing.20o9:73-79.   
[10] He Xu,You Zhiqiang,Kuang Jishun.Performance analysis of three dimensional hypercube network topology [OL]. China Science and Technology Papers Online,2011.   
[11]刘有耀，韩俊刚．片上网络拓扑结构与通信方法研究[D].西安：西安 电子科技大学,2009.   
[12]张大坤，王光兴．基于群论的柏拉图立体着色方案三维模型构造[J]. 软件学报,2004,15(2):292-299.   
[13] Hossain H,Ahmed M, Al-Nayeem A,et al. Gpnocsim: a general purpose simulator for network-on-chip [C]// Proc of International Conference on Information and Communication Technology.2007: 254-257.