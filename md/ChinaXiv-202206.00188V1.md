# 中国SKA区域中心跨洲际高速数据传输进展及展望

郭绍光1,2\*，安涛1,2，徐志骏1,2，劳保强12，陆扬1，吕唯佳1,2，伍筱聪1,2

1.中国科学院上海天文台SKA区域中心联合实验室，上海2000302.鹏城实验室SKA区域中心联合实验室，深圳518066\* 联系人,E-mail: sgguo@shao.ac.cn

收稿日期:2022-06-28；接受日期: $2 0 2 2 \mathrm { - } 0 \mathrm { x } \mathrm { - } \mathrm { x } \mathrm { x }$   
国家重点研发计划（编号:2018YFA0404603)、SKA专项（编号:2020SKA0110300）、国家自然科学基金（批准号:11873079,12041301）和中国科学  
院青年创新促进会项目（编号:2021258）资助项目

摘要平方公里阵列望远镜(SKA）作为最大的射电望远镜，其观测产生的数据将首先由澳大利亚和南非两个台址国传输到百公里左右的科学数据处理中心，然后通过高速网络分发到上万公里距离的各个 SKA区域中心。具有SKA $1 0 \%$ 规模的 SKA1阶段，每年预计有750PB的数据需要通过至少100Gbps的网络分发到各个 SKA区域中心（SRC)，如此高的网络带宽和数据规模对数据的传输分发带来极大挑战。本文通过对 TCP/UDP/HTTP等不同网络协议的分析，并使用当前射电天文领域不同的软件进行测试和研究，得出了目前在10Gbps 网络的基础设施下最佳的传输方案参数，文中讨论了影响高速传输的因素，给出了相应的性能优化的策略，在 SKA1真正的观测数据产生之前，将为中国 SKA区域中心的网络建设和布局提供技术基础。描述的技术细节和方法可供相关科学应用参考和使用。最后讨论并展望了未来 SKA网络需求的挑战。

关键词平方公里阵列,SKA 区域中心，高速网络，数据传输PACS: 47.27.-i, 47.27.Eq, 47.27.Nz, 47.40.Ki, 47.85.Gj

# 1引言

平方公里阵列望远镜（SquareKilometre Ar-ray,简称 SKA）是一项国际大科学工程，是由全球多国合资建造和运行的世界最大规模综合孔径射电望远镜，也是由多个关键科学问题驱动的大科学工程，具有超大视场、超高分辨率和超高灵敏度的特点，其灵敏度预计提高50倍，巡天速度预计提高10000 倍[1-3]，SKA 的数据生成、传输、处理必然导致极高的数据流产生，也对从台站产生数据、传输到中央信号处理器（Central SignalProcessor，简称CSP)、及最后到SKA区域中心（SKARegionalCentre，简称SRC）等各个阶段的数据传输提出了很高的需求[1,4-6]。根据目前的规划，SKA 第一阶段（SKAPhase1，简称 SKA1）已于 2021年 7月正式启动建设，预计2029年底建成并投入运行，产生的数据需要同步传输到位于全球的各个SRC，根据每个SRC数据分担的评估，为了满足SKA1的数据传输，网络带宽至少需要100Gbps，才能保证SKA1产生的数据稳定及时地到达各个区域中心，SKA1正式运行后的SRC的数据分发量预计为每年 710PB，算力至少需要 22PFlops[4]。中国科学院上海天文台于 2019 年主持建设部署了第一个 SKA区域中心原型系统（CSRC-P）[7]，用于开展SRC前期的科学预研究，并为后期SRC的建设提供经验基础。作为SKA科学数据处理系统的一个重要组成部分，考虑到其重要性，SKA天文台（SKAObservatory，简称 SKAO）为此也专门成立了SKA 区域中心指导委员会（SRC SteeringCommittee，简称SRCSC），用于考虑SRC的相关需求。SRCSC 将SRC 的网络建设分为两个阶段[4]来推进，第一个阶段为 2020 年至 2025 年,网络功能达到 $8 0 \%$ 的能力，具备 SKA1基线能力的 $1 0 \%$ ；第二个阶段为 2025年至 2030 年，网络功能达到 $1 0 0 \%$ 的能力，具备SKA1基线能力的$1 0 0 \%$ 。这里描述的 SKA 区域中心基础设施建构类似于欧洲核子研究组织（Conseil Européenn pourla Recherche Nucléaire，简称CERN）[8] 的全球大型强子对撞机计算网格（WorldLargeHadron Col-lider Compute Griding,简称WLCG)技术,WLCG采用的分层数据处理模型利用协议来确定区域中心需要执行的数据处理。SRC 网络将提供给 SKA社区访问数据的权限及用于分析处理数据的工具和软件[5]。本文基于CSRC-P 系统，讨论中国 SRC 需要具备的网络基础和相关政策，通过与目前 SKA的先导项目默奇森宽视场阵列（MurchisonWidefieldArray，简称 MWA)、澳大利亚SKA先导者（Aus-tralian SquareKilometreArray Pathfinder，简称ASKAP）及南非SKA探路者项目MeerKAT等的合作来阐述CSRC-P数据传输的概况与将来的升级计划等。以此来探讨SKA1及全规模 SKA正式运行后，中国 SKA 区域中心的跨洲际高速网络的应对措施和解决方案。

介绍了一种支持SRC全球分布站点需求的网络结构和设计，通过当前与不同的国家和机构开展的实测数据传输，来得出目前使用的协议和软件需要进行的参数优化，并对未来SKA区域中心数据传输提出了一些建议和规划。

# 2 SKA网络和数据流

SKA具有超大视场、超高分辨率、超高灵敏度的特点，同时也面临在新技术背后产生的海量数据的挑战，针对不同的科学目标，从天线数据的获取、存储，然后将数据在中央信号处理器（Central SignalProcessor，简称CSP）上进行在线或离线的相关处理，进一步到达科学数据处理器(ScienceDataProcessor，简称 SDP）对数据质量进行检查，包括初始校准、快速成像等预处理，生成不同类型的科学产品，最后将预处理的数据传输到分布于各大洲的 SRC[9]进行软件环境的搭建[10]，科学数据的优化处理[11-13]。

其中位于澳大利亚和南非的两个观测台站会将所有经过SKA科学数据处理器预处理后的科学数据发送到世界各地的 SRC，每个SRC需要保存数据副本的一部分[14,15]，同时发送该部分到另一个SRC产生一个副本。该网络需要支持SKA数据从观测台站到SRC进行数据的移动，以及SRC之间的数据交换。

![](images/9c3d40696b74718ac746aeb0220670893f85968ecb4d2ab2188d07f0113f1f03.jpg)  
图1 SKA1数据交付模型图[14]Figure 1 Data Deliver Model of SKA1

海量的数据对网络、计算和存储都提出了新的需求，数据的传输、存储、归档和处理都面临很大的挑战。对于SKA科学数据处理系统（ScienceDataProcessing，简称SDP）而言，数据的处理可以在距离台站较近的地方进行，但此时的数据仅仅经过了最初的校准处理和质量检查，而后续的编辑、校准、成像、识别、工具开发、归档管理、基准测试、数据分析及相关科学均需要在SRC进行，所以，SKA天文台的 SDP或者CSP产生的数据并非最终的科学分析数据，而且，如此大的数据流交付给最终的用户是不可行的，且SKAO也规定 SDP只能由天文台的操作人员访问[16]，科学用户只能从 SRC获取 SKA 的科学数据[4，另外由于观测台站、区域中心以及最终科学用户分布在全球，需要涉及到SKA的信号传输与网络子部件（SignalTransportand Networks for the SKA，简称 SaDT)，这些都对 SRC的全球网络协作提出了很高的要求。一般来说，传输到SRC的数据产品将会是非常大的数据文件，单个文件在100GB左右，通过网络数据包往返时间（Round-TripTime，简称RTT）高达100$\sim 3 0 0$ 毫秒的长距离路径传输到SRC，这些连续的数据流需要稳定、无损的端到端网络，并且没有瓶颈限制。这里有两种网络的操作模型如图1所示，一种为通过100Gbps 的网络带宽将 SKAO 的数据产品依次发送到每个SRC，另外一种为数据产品同时向多个SRC并行传输，并发向5个SRC传输，每个数据链路仅需要 20Gbps 的网络带宽即可。

SKA的详细的数据网络拓扑图如图2所示。台站产生的原始观测数据，在SDP经过初步处理，通过数据路由分发到每个SRC的子网络，天文学家通过互联网连接到区域数据中心进行深度数据处理，包括数据的分析、可视化、建模以及软件工具的开发，此时的数据称为高级数据产品（AdvancedDataProducts，简称ADP)，此时的数据将通过云的方式提供给科研人员。

![](images/a0afc9f95e9866985f072a406056654e018c0b515b97bdc830265c42003e8bfd.jpg)  
图2数据交付拓扑图Figure 2 Data Deliver Tier

根据当前SKA1的规模可知，中频阵列单个天线的数据输出速率为64Gbps；低频阵列单个台站的数据输出速率为16Tbps，需要传输到区域中心的数据量在710PB左右[4]。如图2所示，目前预估从SKA1产生并需要传输到每个SRC的数据流在$2 0 0 \sim \mathrm { { 3 0 0 P B / y e a r } }$ ，其最终处理后的数据通常会比这个数据量小，但是在未确定最终处理模型的情况下，多个模型对比产生的数据很可能会比原始数据还大。

以 $2 0 1 3 \sim 2 0 1 5$ 年银河系和银河系外MWA巡天（The GaLactic and Extra-galactic All-sky MWASURVEY，简称GLEAM）[17]为例，该巡天的瞬时频率带宽为 $3 0 . 7 2 \mathrm { M H z }$ ，在72MHz至231MHz之间分为五个频段，为了避免太阳的影响，观测只在夜间进行，观测分为一系列的120 秒的快照，故10分钟以内可以完成5个频段的观测，每次2分钟的观测时间所产生的原始可见度数据为46GB，对其做2秒积分，平均 $\mathrm { 4 0 k H z }$ 频率分辨率，产生的数据在26GB，最终的coarse 通道的数据在 200MB左右，如果将积分时间降低，频率分辨率提升，会直接增加产生的数据量。后续的GLEAM 扩展巡天（THEGALACTICANDEXTRA-GALACTICALL-SKYMWA EXTENDED SURVEY，简称GLEAM-X）[18],将阵列的天线数量增加了一倍，阵列的最大基线也增加了一倍，有效提高了uv 覆盖，并将成像的信噪比提高了一个数量级，由于在成像中使用了精细化的fine通道，单个时间片的最终数据量增加到100GB以上，所以在数据处理过程中，产生的数据可能会大大多于原始数据，特别是有特殊研究目的或有偶然的发现，可能会对原始数据进行二次甚至多次的深度分析。SKA最初的观测将聚焦在几个核心科学项目（KeyScienceProject，简称 KSP）上面，比如脉冲星与宇宙再电离，而对这些数据的处理，均需要研发新的方法、算法、软件等，这些工作均需要在配套的平台上进行部署和测试，这也对 SRC提出了很高的要求。

# 2.1 SRC的网络需求

SRC接收来自SKA天文台站的科学数据产品，并且为用户提供对科学数据产品的访问，以及配套的工具和处理方法[5]。SRC 可以帮助科学家快速地访问数据、处理数据以及发布数据。SRC将支持通用的协作基础设施和中间件工具，以提供对数据、计算资源和存储资源的统一访问，而不受位置的影响。

SRC将有助于充分利用其提供的计算资源和存储资源，因为随着SKA的持续运行，这些资源会保持持续的更新和升级，比如通过CERN[8」项目，可知即使SRC并不位于其设施的运行地理区域，项目也可以正常的运行。

SRC除了主要提供从SKA站点移动数据、进行相关计算和存储外，还提供数据的后续处理，并允许相关的科研人员共享这些数据，如果政策和协议允许，这些数据也可以提供给其他科研人员共享和处理。

在网络带宽允许的情况下，SRC将作为主要站点生成数据产品的异地备份设施，这样SDP站点就不需要保留该数据，但需要确保SKA对这些数据的访问权限。

综上，SRC将提供的功能包括但不限于：

数据处理功能数据存储功能网络优化功能异地备份功能

根据 SKAO的规划，预计到2025年左右，只有少量SKA天线建成，每个台站的数据速率将不超过 20Gbps，随着建设的推进和科学观测的全面开展，2028年左右SKA的数据流量将剧增，到2030年左右向 SRC 的输出速率将达到100Gbps[19]。

# 3数据传输软件与协议

传统模式下，观测数据会在本地进行存储和处理，但是随着SKA观测数据量的巨量增加，本地已经不足以支撑如此巨量的数据处理和分析，此时就需要通过高速网络传输到各个SRC进行分布式计算和存储。而影响长距离跨洲际的海量数据的传输主要包括：硬件设备、交换机设备、软件程序、使用的协议及对应的带宽等因素。

# 3.1 数据传输协议

在数据传输的测试中，使用了传统的提供端到端服务器的传输控制协议（TransmissionControlProtocol,简称TCP),用户数据报协议(UserData-gramProtocol,简称UDP),其中 TCP 稳定可靠且面向连接，UDP简单易用不面向连接。由于TCP加入了各种安全保障功能，在实际执行的过程中会占用大量的系统开销，使得数据传输速度受到较大影响。随着数据流的增加，TCP和UDP的性能均受到比较大的影响。

此时就出现了优化TCP协议的系列工作，大多从TCP的参数、窗口设置以及并发性来考虑和优化这些协议[20]。最初的有针对单端优化 Tuningknobs，但都需要专业的管理员配置，且如果数据的双端不同时优化，可能会因为不同的网络情况而导致数据传输较慢。其他优化方法主要包括：修改TCP 参数的 HighSpeed [21]，BiC [22]，FAST[23] 和H-TCP[24]；并行化 TCP 协议的 PSockets [25]和GridFTP[26]；基于效率可靠UDP的RBUDP[27],Tsunami[28] 和 FOBS [29]；还有 SABUL [30]（UDT协议的最早原型）及基于UDP的数据传输协议[31](UDP-based Data Transfer Protocol，简称 UDT)1)协议。

对于数据传输协议而言，需要满足流的特性、可靠性、支持单路和多路广播的功能；对于拥塞控制而言，也需要满足高效、公平及分布特性。

目前的这些协议也存在很多问题，比如对于改进的TCP就需要从内核层面进行编译部署，提高了测试门槛，参数的调优也需要人工干预。

对于UDT协议而言，该协议提供了应用层面的调用，提供与TCP类似的面向连接的功能，全新的协议设计和应用，新的拥塞控制算法，可配置的拥塞控制框架。第3.2.4节及第3.2.5节均使用了该协议。

安全远程登陆和文件传输协议（SecureRemoteLogin and File Transfer，简称 $\mathrm { S S H ^ { 2 } } )$ ）用于以加密的方式远程登陆其他计算机，该协议提供了几种不同的加密认证选项，保证通讯的安全性，SSH依赖于openssh，但代价是降低了整体的传输速率。

同时还有应用层的超文本传输协议（HyperText Transfer Protocol，简称 HTTP），HTTP 最初用于Web浏览器和服务器端的通信，现在也用于数据的传输工作。

# 3.2 数据传输软件

通过第3.1节的讨论，一般TCP协议用于专用线缆或短距离的数据传输；对于广域网或者长距离大多数使用UDP或其他协议。接下来介绍的基本为基于UDP的各类软件以及更高层的协议来实现的。

# 3.2.1 wget

wget)是一个免费的命令行工具，基本在每个Linux 发行版都默认安装。它使用Internet 协议HTTP、HTTPS、FTP和FTPS来检索下载文件，可以通过前台或后台的方式工作。

wget在低速网络上工作的非常好，可以保持获取数据的完整性，并且可以通过增量的方式重新更新获取文件。因为HTTP和FTP均带有时间戳，所以wget可以通过检索该属性来确认是否需要更新获取的文件。

wget主要用于将数据通过Internet协议开放的用例，这个命令不需要对数据存储服务器或节点有访问权限就可以对公开数据进行下载。但这也会导致由于无法对网络进行优化而引起的性能问题。在同等网络条件下，相对于3.2.6数据传输的速率仅有100Mbps。这种情况可以通过多线程的wget和axel4等来进行改进，在使用这种方法对南非MeerKAT的数据进行传输时，实测下来，多线程有相当大的速率提升，单线程只有100Mbps，在开启4个线程的时候能够达到500Mbps的速率。但这里也取决于服务端对网络接口的限制。

# 3.2.2 scp

安全文件拷贝（SecureFileCopy，简称 scp）用于在不同的计算机之间传输数据，该程序使用SSH协议，在大多数的Linux和Unix发行版默认安装。在测试中，scp性能相对而言比较差，其中的加密校验增加了部分负荷，主要原因还是openssh的架构设计，其内部的 windowing 机制阻碍了快速连接的实现。特别是在长距离高延迟的情况下，这种影响尤为突出。SSH通常将数据传输的窗口设定为64KB，这在大数据流传输的情况下，是极大的瓶颈所在。通过动态定义窗口的缓存大小，可以将性能提升一个数量级以上[32],这种方法通过定义一个输入参数，来动态的调整窗口的大小，可以利用内核TCP 栈的最佳效率[20]。目前该方法的缺点在于,需要从源码编译，并且要保证数据发送端和接收端保持同样的版本。这对于网格化的多点传输而言，有比较大的困难，因为这需要具备管理员权限。在使用这种方法对澳大利亚SKA区域中心Pawsey超算中心数据服务器的数据进行传输时，单线程只有100Mbps的传输速率，这种情况下只能通过同时开启多个终端来加速数据的传输。

# 3.2.3iperf3

$\mathrm { I P e r f 3 ^ { 5 ) } }$ 是一个开源的、支持多平台的工具，由美国能源网和劳伦斯伯克利国家实验室7开发，用于主动测量IP网络上可实现的最大网络带宽。支持调整与时序、协议和缓冲区的各种相关参数，每次的测试都会显示测试的吞吐量、比特率等参数。IPerf3支持目前常规的协议，比如TCP、UDP和SCTP.

在本文研究中，主要使用IPerf3进行最初的相关测试，在4.3与西班牙SKA区域中心的评测中，也主要使用这款软件，以确保所有的参数均为最优状态。在网络传输中，传输窗口的大小对于测试非常重要，窗口指明了在接收应答信号（acknowledge-mentcharacter，简称ACK）之前允许传输的字节数目和数据包大小。窗口过小可能会导致直接连接的服务器和客户端频繁地切分网络数据包，导致传输速率被极大地影响。特别是随着RTT的增加，数据包和ACK之间的时间变长，如果窗口太小而无法容纳数据包，则发送方将被缩减以满足接收端的需求。

IPerf3的用法为在其中一端使用iperf3－s开启服务器程序，另外一端作为客户端进行测试，可以通过IPerf3提供的众多选项设定各个参数，比如

$$
i p e r f 3 - c 1 9 2 . 1 6 8 . 1 . 1 2 3 - P 4 - t 3 0 - b 1 0 G - u
$$

代表的是开始一个UDP传输，目标端地址为192.168.1.123，并发开启4个线程，持续时间为30秒，带宽为10Gbps。通过不同线程、及带宽的测试，可以动态调整所需要指定的窗口大小，以此完成对UDP 协议的抖动、丢包率分析，TCP和UDP 协议的带宽适应性测试，从而找到最佳的传输性能参数。

# 3.2.4 NGAS

下一代归档系统（NextGenerationArchiveSystem，简称NGAS）最初为欧洲南方天文台（Eu-ropean SouthernObservatory，简称ESO）的数据归档和分发而设计[33]，主要目标为整套系统可扩展并支持大数据的传输和检索。NGAS的主要特点包括但不限于：

·支持Linux不同的发行版操作系统  
·服务端使用Python开发·具体实现使用多线程HTTP  
·基于URL 的命令行接口  
$\cdot$ 支持不同数据类型的插件架构  
·基于XML配置文件和消息传递

该技术后续也被用于ALMA[34]、NRAO、MIT等天文观测设备和观测台。目前MWA也使用了该技术[35],并对其进行了定制，优化了NGAS 的高吞吐数据输入、数据流管理、多层次数据存储和数据处理的缓存，以满足MWA数据400MB/s持续可见度数据的需求，该技术也用于MWA的数据分发工作。MWA首先通过NGAS在台站以400MB/s的数据进行在线归档（OnlineArchive，简称OA），后面通过10Gbps的网络传输到位于Perth超算的长期存储设备（Long-termArchive，简称LTA)，并同步发送到位于澳大利亚珀斯、美国MIT和新西兰VUW的数据处理中心。

NGAS目前支持三种协议，分别为HTTP、FTP和GridFT。基于NGAS和无限滑动窗口（Un-limitedSliding-Window，简称USW）技术，通过ZeroMQ中间件技术，增强的NGAS（EnhancedNGAS，简称ENGAS）可以把NGAS的性能提升3到12倍。同时ENGAS还减少了通讯时间，改进了带宽的利用率，解决了远程同步的问题，从而达到更好的数据传输性能[36]。

# 3.2.5jive5ab

jive5ab[37] 由欧洲VLBI 联合所（Joint Insti-tuteforVLBIERIC，简称JIVE）为欧洲甚长基线干涉网络 (European VLBINetwork，简称 EVN)开发的一套软件。该软件旨在替换Dimino，主要功能包括数据记录、读取和传输等。JIVE为EVN的核心组织，主要工作为运行和开发EVN的观测数据及处理，EVN的数据分散于全球22个望远镜和台站，这些望远镜最远距离JIVE有10000多公里。由于观测数据需要被统一传输到JIVE 进行相关处理，所以需要一套实时数据传输的软件来进行运维，jive5ab被用于将这些数据传输到相关处理中心进行处理，其中的工具 m5copy 基于UDT 协议，可以开展长距离高速的数据传输及监测。目前上海天文台的天马65米射电望远镜与佘山25米射电望远镜作为 EVN 的两个参与台站，参与常规的EVN观测，观测的数据传输目前使用jive5ab来进行，EVN的大多数台站（比如Effelsberg、Yebes、Onsala 等）在 2017年将 eVLBI 的带宽从 1Gbps升级到了2Gbps，天马65米射电望远镜与佘山25米射电望远镜也在2018年5月举行技术运行组会（Technical Operations Group，简称 TOG）之前，升级配置了FlexBuff 用于通过fila1Og支持 2Gbps 的速率，后续随着中国科技网（China Sci-ence and Technology Net，简称 CSTNet）的带宽升级，两个台站的数据传输带宽也从1Gbps 升级到了2Gbps，欧洲的大部分台站现在已经升级到了4Gbps 带宽[38]。

# 3.2.6MWA download

全天虚拟天文台（TheAll-SkyVirtualObser-vatory，简称ASVO）通过将澳大利亚所有的天文设施联合的方式，使研究人员和科学家可以访问所有的数据集。其中ASVO-MWA节点主要为MWA观测服务，通过在线服务和相应的工具为研究人员提供MWA的数据处理服务和获取，数据可以是原始可见度数据或校准可见度数据，可以通过后台搭载的软件来进行转换，同时ASVO节点强制实施元数据的完整性以及数据的访问权限设置。

当前 MWA 的数据下载主要通过 manta-ray-client8来进行批量下载，使用基于TCP协议的应用层传输协议-超文本传输协议（HyperTextTrans-fer Protocol，简称HTTP)，并通过多线程加速，默认为开启4个线程，数据块为64KB。

ASVO-MWA 关于数据的原则称为FAIR [39]规则如下：

·方便寻找的(Findable)：所有的MWA观测都有唯一的标识（使用obsid来查找)MWAASVO也提供与国际虚拟天文台联盟(InternationalVirtualObservationAlliance，简称IVOA）的表访问协议(TableAccessProtocol，简称TAP)，方便与IVOA兼容的软件来访问观测信息

·可访问的（Accessible），可以通过TAP协议便捷地访问·可互换的（Interoperable)，MWA可以生成两种标准的射电天文数据格式，即CASA 测量集数据[40]（Measurement Set，简称 MS）或者 fits 格式的数据[41]

·可重用的（Reusable），提供的数据包括元信息，比如观测、望远镜设置以及数据处理的细节

这些规则也适用于后续SRC对数据的需求。

# 3.3 网络参数

通过带宽延迟（BandwidthDelayProduct，简称 BDP）的公式(1)可知，BDP的大小决定了终端主机需要的缓冲量，很大程度上会影响数据传输速度，而最大传输速率很大程度上取决于网络数据包的窗口大小[42]。

$$
B a n d w i d t h ~ D e l a y = B a n d w i d t h \times R T T
$$

按照较优的RTT，比如 $4 0 \mathrm { m s }$ 为例，如果Band-width为1Gbps，那么最佳的BDP应该设置为4.77MB，同样如果Bandwidth为10Gbps，最佳的BDP应该设置为47.68MB。如果RTT 为10ms,在1Gbps 带宽的时候，BDP应该设置为此时的数据流为1.19MB。

再结合socket缓冲区大小的计算(2)如下所示：

$$
s o c k e t \_ b u f f e r \_ s i z e = 2 \times b a n d w i d t h \times d e l a y
$$

这个值可以通过 BSD setsocket的选项SO_SNDBUF和SO_RCVBUF分别设定发送缓冲区和接收缓冲区的大小，这两个参数还会影响接收的窗口（ReceiverWindow，简称RWND）。

系统初始的网络参数如下以及根据实际的输出传输测试，初始以及经过优化后的参数值如表1所示，其中各个配置位于net 配置文件。

其中net.core.netdev_max_backlog用于控制net__rx_action软中断的最大值。

这些值系统默认情况下设置的比较小，需要根据内核的版本、数据的带宽以及可容忍的延迟来适当调整。

# 3.4 其他优化

对网络进行的调优也可以通过下面的操作来进行。使用大的数据块将改善性能，一般情况下推荐8KB的数据块。64KB是更好的选择，这里需要网卡的硬件支持。另外创建并使用多个socket数据流

郭绍光等.

表1系统初始网络参数设置Table1 Network Parameter Setting  

<html><body><table><tr><td>参数</td><td>初始值</td><td>优化值</td></tr><tr><td>core.rmem_max</td><td>212992</td><td>16777216</td></tr><tr><td>core.rmem_default</td><td>212992</td><td>16777216</td></tr><tr><td>core.wmem_max</td><td>212992</td><td>16777216</td></tr><tr><td>core.wmem_default</td><td>212992</td><td>16777216</td></tr><tr><td>ipv4.tcp_rmem</td><td>4096/87380/6291456</td><td>4096/87380/16777216</td></tr><tr><td>ipv4.tcp_wmem</td><td>4096/16382/4194304</td><td>4096/87380/16777216</td></tr><tr><td>core.netdev_max_backlog</td><td>1000</td><td>250000</td></tr></table></body></html>

可以极大地改善数据的传输性能。可以使用iperf的 -P选项来进行实测。另外bbcp 和 gridFTP也支持并行数据流的传输。不过需要特别注意磁盘的性能，其性能也可能是数据读写的瓶颈。

如图所示，目前CSRC-P的数据传输节点读写性能均在20Gbps，满足高速传输的要求。

# 4实验测试

本章节列举了CSRC-P与运行中的位于澳大利亚的 SKA探路者项目默奇森宽视场阵[17]、位于荷兰的JIVE 研究以及与西班牙 SRC 进行的数据传输测试。传输测试详细阐述了使用的软件、方法及采用的相关优化等工作。

# 4.1 中澳实验

在CSRC-P与澳大利亚的测试中，传输的数据主要来自SKA的先导阵列MWA、ASKAP以及用于脉冲星观测的Parkes望远镜。主要使用了三种传输方案，分别为 NGAS、ASVO以及 scp。其中NGAS方案为最开始在CSRC-P与澳大利亚举办的大数据研讨会上9开展，当时的网络由CSTnet 和澳大利亚学术与研究网（AustralianAcademicRe-search Network，简称AARNET）提供，带宽为1Gbps。后续根据需要开通了常规的 2Gbps 带宽的网络以及突发的 5Gbps 的网络。

传输的数据格式主要包含MeasurementSet数据，FITS数据以及处理的结果文件。CASAMS格式的数据有一个极大的数据文件和很多小文件，这种格式不利于数据的长距离传输，最好的办法是将其打包压缩为一个文件。而 FITS 文件主要为相关处理后的数据，数据量一般在每个文件40GB$\sim 6 0 \mathrm { G B }$ 。处理的结果文件主要为一些文本文件和图像文件。

一种办法就是在Pawsey 进行处理，后续直接在Pawsey的超算上进行下载，然后把数据处理的初步结果通过Pawsey 超算的数据传输节点 hpc-data.pawsey.org.au传输到CSRC-P，此时可以通过判断位于数据节点的manifest文件来判断文件是否更新，数据是否需要下载等信息，这种情况下因为使用的为scp，所以每一组的数据速率仅仅能达到150Mbps 左右。

CSRC-P最早利用CSTNet提供的1G 网络使用NGAS开展了网络传输测试，当时的传输速率在500Mbps\~750Mbps，如图3,4所示：在1Gbps 网络带宽的时候，使用NGAS进行数据的传输下载，在使用1个数据流传输的时候平均传输速率只有514Mbps的速率，通过增加SOCKET 接收缓冲区的大小，并使用4个并行传输的线程，进行了10分钟约64GB的数据传输测试，平均传输速率达到了738Mbps。考虑到从上海经由北京，然后通过公共互联网，到达澳大利亚珀斯，这个传输速率是比较理想的。

![](images/2f3396ada232138ce74cffdcc70fd626d3976fbb8bfce531df80d7128ebf4def.jpg)  
图32017年5月19日CSRC-P与MWA的数据流基准测试Figure 3 Benchmark of NGAS using 1Gbps bandwidth on May19 2017

月1日02时开始到09时左右的数据速率为0，后续分析得知，该段时间ASVO节点处于维护阶段，暂停所有的数据处理，后续的数据传输恢复正常。

![](images/d9adc8578298ba0ee4b688e5bf5e8fe7c9fc266337ef1727a812a5b39ceacfc4.jpg)

![](images/8aac11ac3f830ffe173828b375f68b07dc5f57f29ce441b2388c23f27861ba3d.jpg)  
图52020 年10 月1日CSRC-PChina-ASVO 测试Figure 5 Benchmark of ASVO using 5Gbps bandwidth on Oc-tober 1 2020

CSTNet于2020年开通了5G带宽的测试条件，CSRC-P与MWA重新开展了数据传输，并使用全新的全天虚拟天文台（All-SkyVirtualObser-vatory，简称ASVO）接口，通过manta-ray-client来进行数据下载，如图5数据的传输速率最高可达4.5Gbps。目前ASVO的工作方式为，提交job到ASVO 服务器，然后ASVO会将原始数据从长期存储的磁带中读回到硬盘缓冲区，在数据完整地读取到硬盘缓冲区以后，才可以进行下载，所以在提交新的数据下载请求时，可以看到会有一段时间的等待，此时即为数据的准备时间。而从2021年10

# 4.2 中荷实验

![](images/b8decc232ca7a2bc6a38dbbc312c8a4d0e79b52237f77f4aadee82d68a85651f.jpg)  
图42017年8月28日CSRC-P与MWA的NGAS数据流传输实验Figure 4 Benchmark of NGAS between CSRC-P and ICRARon August 28 2017  
图62021年10月18日China-Jive 数据常规传输 2Gbps带宽Figure 6 Data transfer between China and JIVE on October18 2021 using 2Gbps bandwidth

上海天文台有2台射电望远镜参加EVN观测，会有常规的数据传输工作。在与JIVE进行的数据传输中，传输的数据主要为EVN的观测数据，数据格式当前主要为Mark5B，根据观测计划的不同，单个数据文件的大小在10GB\~150GB，基于UDT协议使用 jive5ab 来传输。当前的网络带宽为2Gbps,如图6所示，数据传输的平均速率在1.8Gbps左右，带宽利用率在 $9 0 \%$ 左右。数据传输已经经过了优化，本次的观测波动主要在首次读取文件的时刻。

郭绍光等.

Data Rate extractfrom directory   
[test-004/tcp]   
iperf3-client-ength-128KB-window-2MB.20200803T045111   
iperf3-clent-Iength-1MB-windeu-2MB.20200803T051615   
gth-128KB-γ dow-4MB.20200803T045213   
-128KB -500KB.20200803T044906   
4MB.20200803T051717   
erf3-clent-ength-256KB-window-1MB.20200803T045829   
iperf3-client-length-256KB-window-16M8.20200803T050239   
iperf3-clent-ength-512K-window-4MB.20200803T050855   
3-client-length-128KB-window-1MB.20200803T045008   
Jength-128KB- -250KB.20200803T 44804   
1100   
9.10 -client-ength-1MB-windew-5 F051410   
心 20 Duraten (a) 40 50 武   
45727   
perf3-clent-ength-1 IT051922   
iperf3-client-Iength-512KB-window-1MB.20200803T050651   
iperf3-clent-Iength-256KB-window-BMB.20200803T050136   
20200803T045932

# 4.3 中西实验

2020年7月开始，CSRC-P与西班牙安达卢西亚天体物理研究所（TheInstitutoAstrofisicaAn-dalucia，简称IAA)开展了关于SRC之间的网络测试研究，用于分析出在跨洲际的情况下，影响网络性能的因素。主要分析了短距离10Gbps及25Gbps带宽情况下，基于UDP和TCP协议影响数据传输的情况。由图7,8，9,10可知，在10Gbps 带宽的情况下，TCP 数据包在256KB以上，其传输速率基本保持比较稳定的状态，TCP窗口对速率的影响在 $2 \%$ 左右；在 25Gbps 带宽的情况下，TCP 数据包在256KB及512KB时，其传输速率可以达到较好的状态，TCP窗口在4MB，数据包为512KB时，速率最高，基本可以到到19Gbps，对速率的影响较大，可以达到在 $1 0 \%$ 左右。在对CSRC-P与IAA 进行数据传输时，在网络带宽为1Gbps 的情况下传输的测试速率仅仅在150Mbps左右。分析可能的情况为受到了中间路由的限制。

![](images/c931b58479e77510776bcb4024a669bf65f0bc9b7b1b95d547ab81c8f25c0652.jpg)  
图82020 年8月6日10Gbps不同TCP 窗口大小测试Figure 8 Benchmark of different TCP length using l0Gbpsbandwidth on August 6 2020

![](images/86971ab259183cc28fd5a6c9a08c212815cd94bda3fb6f41989f7722e140d222.jpg)  
图92020 年8月6日25Gbps不同TCP长度测试Figure 9 Benchmark of different TCP length using 25Gbpsbandwidth on August 6 2020  
图102020年8月6日25Gbps不同TCP窗口大小测试Figure 10 Benchmark of different TCP length using 25Gbpsbandwidth on August 6 2020

![](images/e6e88333e31bfadaae5c2bd9aea0384a4604226a86a4b4ff521aa3f0c7e3f06f.jpg)  
图72020年8月6日10Gbps不同TCP长度测试Figure 7 Benchmark of different TCP length using l0Gbpsbandwidth on August 6 2020

# 5讨论

相对于UDP而言，TCP提供了更多的控制机制，比如sliding 窗口，数据重传，Nagle算法，拥塞控制等。对于短距离传输而言，UDP是比较好的通讯协议，但是对长距离，比如洲际之间的传输，大多仍需使用TCP传输协议，或者也可以在UDP的基础上增加一些可靠性的机制。下一步将进一步对TCP协议的高速存储技术进行研究和测试,包括对多核多进程开展相关研究。当前40Gbps/100Gbps

郭绍光等.

的网络也在快速研发中，由于其价格昂贵，基本用于洲际的骨干网和数据中心，相信随着新技术的发展，硬件也会逐步升级。当前北京与上海已经具备了100Gbps的高速网络，后续将尽快开展相关的优化工作，提升100Gbps 网络的性能，以应对未来的挑战。

# 6总结与展望

SKA的科学潜力是前所未有的，也是国际天文学界的最高优先事项之一。同样SKA产生数据的规模、速率以及复杂度，都对当前业界的数据管理、网络和计算提出了很大的挑战。通过对数据速率、存储和处理等流程的估算，每个SKA望远镜台站每年有超过300PB的数据需要传输到各个区域中心，观测台站到每个 SRC 需要具备100Gbps的网络，这些工作十分依赖于国家的骨干网络设施、设备和相应的软件。随着技术的进步和SKA项目的稳步推进，新的技术和方法也将对业界产生比较好的推动作用。

致谢 向评审人和对该文有帮助的人士表示谢意.本研究使用了中国SKA区域中心原型机的资源。

# 参考文献

1 武向平．中国 SKA 科学白皮书．北京：科学出版社，2017   
2 AnT,WuXP,HongXY,etal.SienceApplicationsand ChallengesofSKABig Data(inChinese).Bulltinof theChiese Academyof Sciences．2018，8:871-876[安涛，武向平，洪晓瑜，等．SKA 大数据的科学应用和挑战．中国科学院院刊，2018，8: 871-876]   
3 Guo S G,Zheng XY,Mao YF,et al.Scheme and Prospectof the SKA Big Data Transferrng(in Chinese).E-science Technology& Application,2018，9(3):3-13[郭绍光，郑小盈，毛羽丰，等．SKA 海量数据传输的方案及展望．科研信息化技术与 应用，2018，9(3):3-13]   
4 QuinnP,van Haarlem M,AnT,etal.SKARegional CentresWhitePaperv1.0.Technical Report,SquareKilometre Array Organisation.2020   
5 Chrysostomou A,the SRCCG.SKA REGIONAL CENTRES:BACKGROUND AND FRAMEWORK. Techinical Report, Square Kilometre Array Organisation. 2017   
6 An T,Wu X C,LaoB Q,et al. Status and progress of China SKA Regional Centre prototype.arxiv:2206.13022   
7 An T,Wu XP,Hong X Y,SKA data take centre stage in China.Nat Astron,2019,3:1030-1030   
8 ShuT,Todorovic S,ZhuS.CERN:confidence-energyrecurent network forgroupactivityrecognition.In:Procedingsof the IEEE conference on computer vision and pattern recognition. 20l7.eprint arXiv:1704.03058   
9 Guo SG,LuY,AnT,etal.Scientificdatafowandarraysimulationanalysis forthe SKA-1era(in Chinese).inprepare (2022)[郭绍光，陆扬，安涛，等．面向 SKA-1时代的科学数据流及阵列模拟分析.准备中(2022).   
10 Lao B Q，Zhang Y K，An T，et al.Software Platform on China SKA Regional Center Prototype System(in Chinese).ChinaXiv:202206.00173．[劳保强，张迎康，安涛，等.(2022)．中国 SKA 区域中心原型系统－软件平 台.ChinaXiv:202206.00173]   
11 Xu Z J,An T,Guo S G,et al. A machine learning dataset for FRB detection in raw data(in Chinese).ChinaXiv:T202206.00321.[徐志骏，安涛，郭绍光，等.(2022)．一个面向原始数据搜寻的快速射电暴数据集.ChinaXiv: T202206.00321]   
12Wei JW,Zhang CF,Zhang ZL,etal.Paraleloptimizationofthe pulsar search pipelineon China SKA Regional Centre Prototype (in Chinese)．ChinaXiv:T202206.00297．[韦建文，张晨飞，张仲莉，等.(2022)．低频射电脉冲星搜索的性能优化方法. ChinaXiv:T202206.00297]   
13Wei JW,ZhangCF,LaoBQ,etal.Optimization of paralel procesing of Square Kilometre Array low frequency imaging pipeline (in Chinese)．ChinaXiv:T202206.00292．[韦建文，张晨飞，劳保强，等.(202).SKA 低频成像管线并行优化 化.ChinaXiv:T202206.00292]

郭绍光等.

14Bolton R C,te SRCCG.SKA REGIONAL CENTRE REQUIREMENTS.Technical Report,Square Kilometre Array Organisation.2019   
15Ivashina M V,ArdenneA V,Bregman JD,etal.Activitiesfor the square kilometer array (SKA)in Europe.In:4th International Conference on Antenna Theory and Techniques (Cat.No.03EX699).IEEE,2003.Vol.2   
16Santander-Vela,Juande,Lorenzo Pivetta,and Nick Rees."Statusof the Square Kilometre Array”Proc.of International Conference on Acceleratorand Large Experimental Control Systems (ICALEPCS’17),Barcelona,Spain,8-13October017. 2017.   
17Whitney A,Boler T,Bowman J,etal.The Murchison Widefield Array(MWA):Curent Statusand Plans.In:American Astronomical Society,AAS Meeting #218.Bulletinof the American Astronomical Society,2011.Vol.43,id.132.07   
18Wayth R,Tingay S,Trott C.The phaseIIMurchison widefield array:design overview.Publicationsof theAstronomical Society of Australia,2018,35:id.e033   
19Ford,D,Bolton,R,Colegate,T,etal.(2010).TheSKAcostingand design tool.SKA Memo Series,Memo,10,1-31.   
20 Semke,Jeffrey,Jamshid Mahdavi,and Matthew Mathis."Automatic TCPbufertuning"”Proceedings of theACM SIGCOMM'98 conference on Applications,technologies,architectures,and protocols for computer communication.1998.   
21 Imran A,ZulkarN,Md SQ,et al.OneDataShare:A Vision for Cloud-hosted Data Transfer Scheduling and Optimizationas a Service.2019.eprint arXiv:1712.02944   
22Xu,Lisong,KhaledHarfoush,andInjongRhee."Binaryincreasecongestioncontrol(BIC）forfastlong-distancenetworks" IEEE INFOCOM 2004.Vol.4.IEEE,2004.   
23Jin,Cheng，David X.Wei,and Steven H.Low."FAST TCP:motivation,architecture,algorithms，performance”IEEE INFOCOM 2004．Vol.4.IEEE,2004.   
24Leith,Doug,andRobert Shorten."H-TCP:TCPcongestioncontrolforhighbandwidth-delayproductpaths”draft-leith-tcphtcp-06 (work in progress）(2008).   
25Sivakumar,Harimath,tuartBaileyandRobertL.Grossman."PSockets:Thecaseforaplication-levelnetworksipingfor dataintensive applications using high speed wide area networks.”SC'0: Proceedings of the 2000 ACM/IEEE Conference on Supercomputing.IEEE,2000.   
26Alcock,Wiliam,etal."The Globus striped GridFTPframeworkandserver"SC05:Proceedingsofthe2005 ACM/IEEE conference on Supercomputing. IEEE, 2005.   
27He,Eric,etal."Reliable blastUDP:Predictablehigh performance bulk data transfer”Proceedings.IEEE International Conference on Cluster Computing. IEEE, 2002.   
28Meis,Mark R."Tsunami: A high-speed rate-controled protocol for file transfer”Indiana University (2004).   
29Dickens,Philip M."FOBS:A lightweight communication protocol for grid computing”European Conferenceon Paralel Processing.Springer,Berlin,Heidelberg,2003.   
30Gu,Yunhong,and Robert Grossman."SABUL:A transport protocol for grid computing.”Journal of grid Computing1.4 (2003):377-386.   
31 Gu, Yunhong,and Robert L.Grossman."UDT: UDP-based data transfer for high-sped wide area networks"” Computer Networks 51.7 (2007): 1777-1799.   
32Rapier,Chris,and M.Stevens."Application Layer Network Window Management in the SSH Protocol” Supercomputing Conference.2004.   
33Wicenec A,Knudstrup J, Johnston S.ESO's Next Generation Archive System.The Messenger,2011,106:11-13   
34WicenecA,FarrwS,GaudetS,etal.TheALMAArchive:ACentralized SystemforInformationServices.In:Astronomical Data Analysis Software and Systems (ADASS)XII San Francisco: Astronomical Society of the Pacific,2004.93-96   
35Wu C,WicenecA,Palot D,etal.Optimising NGASfortheMWA Archive.Experimental Astronomy,2013,36(3):679-694.   
36ShiC,Deng H,WangF,etal.Enhancedremoteastronomicalarchivesystembasedonthefle-levelUnlimitedSliding-Window technique.Research in Astronomy and Astrophysics,2021,21(10):253-260   
37 Harro Verkouter. jive5ab documentation Version 2.5,2020   
38 EUROPEAN VLBI NETWORK biennial report 2017-2018. Technical Report,EVN. 2018   
39 O'Toole S, Tocknel J. FAIR standards for astronomical data. 2022.arXiv preprint arXiv:2203.10710   
40 McMulin,J.P.etal. "ASPConf.Ser.Vol.376,Astronomical Data Analysis Software and Systems XVI"(2007):127.   
41 Greisen,E.W.Aips memo series,AIPS FITS File Format.AIPS Memo 117, 2019.

# Progress and Prospect of transcontinental high-speed data transmission at SKA Regional Center in China

GUO ShaoGuang1\*， AN Tao $^ 1$ , XU ZhiJun $\cdot ^ { 1 }$ , LAO BaoQiang $^ 1$ LU Yang $^ { 1 }$ , LU WeiJia $^ { 1 }$ & WU Xiaocong1

1.ShanghaisronoicalbservatoryKeyaboratoryofadiostronomyinesecaemyofiences,angh003 China

The Square Kilometer Array (SKA) is the largest radio telescope,and the data generated by its observations willbe transmitted from Australia and South Africa to the scientific data processng center about one hundred kilometers away at frst,and then distributed to various SKA Regional Centres(SRC)with a distance of tens of thousands of kilometers through high-speed network.In the SKA Phase One (SKA1) stage with a scale of $1 0 \%$ of SKA,it is estimated that about 750PB of data needs to be distributed to each SRC through a network of at least lOoGbps each year.Such high network bandwidth and data scale bring great challenges to data transmission and distribution.This paper analyzes different network protocols such as TCP/UDP/HTTP and uses different software in the feld of radio astronomy for testing and research,and then the optimal transmisson scheme parameters under the current infrastructure of 10Gbps network are obtained. In this paper,the factors afecting high-speed transmission are discussed,and the corresponding performance optimization strategies are given.Before the real observation data of SKA1 is generated,it wil provide the technical foundation for the network construction and layout of China's SKA regional center. The technical details and methods described are available for reference and use in relevant scientific applications. Finally, the challenges of future SKA network requirements are discussed and prospected.