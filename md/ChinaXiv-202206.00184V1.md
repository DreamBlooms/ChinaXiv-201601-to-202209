# 面向SKA-1时代的科学数据流及阵列模拟分析

郭绍光1\*，陆扬1，安涛1，劳保强1，徐志骏¹，伍筱聪1，吕唯佳1

1.中国科学院上海天文台SKA区域中心联合实验室，上海2000302.鹏城实验室SKA区域中心联合实验室，深圳518066\* 联系人,E-mail: sgguo@shao.ac.cn

收稿日期:2022-06-28；接受日期:2022-07-xX;  
SKA 专项（编号:2020SKA010300)，国家重点研发计划（编号:2018YFA0404603）、国家自然科学基金（批准号:11873079,12041301）和中国科学院青年创新促进会项目（编号：2021258）资助项目

摘要作为下一代射电望远镜，平方公里阵列望远镜（SKA）经过多年的筹备，第一阶段(SKA1)已经在2021年7月开工建设，SKA1正式运行后预计每年将产生750PB的科学归档数据，这些数据将存储在世界各地的 SKA区域中心供科研工作者使用。本文将SKA观测台站、中央信号处理器、科学数据处理及区域中心等各个阶段的模型进行量化分析，以 SKA1的高优先级科学观测为主要依据，得出每个阶段的数据流评估情况，以及对科学数据处理算力的需求。以当前SKA1-low和 SKA1-mid的阵列为例，总结了包括分辨率、灵敏度、UV覆盖等影响干涉阵列布局的关键因素；最后使用OSKAR进行干涉阵列的数据模拟，通过对SKA1-mid的模拟得出系统的可扩展性和稳定性，通过对SKA1-loW在CSRC-P上的模拟，可以看出中国 SKA区域中心原型机设计经过了充分的论证和优化，并得出了详细的算力需求以及数据量的详细信息。SKA对数据处理、计算、存储等的需求，将需要电子、通信、信息、计算机等技术和交叉学科的联合推动。

关键词平方公里阵列射电望远镜，数据模拟，综合孔径，数据格式PACS: 47.27.-i, 47.27.Eq, 47.27.Nz, 47.40.Ki, 47.85.Gj

# 1引言

平方公里阵列望远镜（SquareKilometreAr-ray,简称 SKA）[1-4] 是一项国际大科学工程，将建造成为世界上最大、最灵敏的射电望远镜。经过多年的准备工作，具备SKA望远镜接收能力 $1 0 \%$ 的第一阶段SKA-1（SKAPhase1，简称SKA-1)已经于2021年7月开始建设，SKA-1由位于澳大利亚的SKA1-low和南非的SKA1-mid两个台址组成，覆盖频率为 $5 0 M H z \sim 1 5 . 3 ~ G H z$ 。

SKA使用综合孔径技术，将阵列中的信号进行合成处理，提供一个等效口径为1公里的射电望远镜。SKA将产生海量的数据，以SKA1-mid为例，位于阵列附近的中央信号处理器（Centre Sig-nalProcess，简称CSP）对18Tb/s的数字化数据流进行波束和相关处理[5]，然后将其传输到开普敦的专用超级计算机进行进一步处理。这些数据流的处理过程对 SKA整个系统的设计至关重要，也带来了对后续数据管理及数据处理的巨大挑战。根据当前的数据估算以及与全球大型强子对撞机计算网格（Worldwide Large Hadron Collider ComputingGrid,简称WLCS)的比较，将数据从台址国的科学数据处理器(ScienceDataProcess,简称SDP)传输到各个SKA区域中心（SKARegionalCentre，简称 SRC）需要高速稳定的洲际网络支持[6]。根据每个SRC数据分担的评估，为了满足SKA1的数据传输，网络带宽至少需要达到100Gbps 的带宽[7],才能保证SKA1产生的数据稳定及时地到达各个SRC，SKA1正式运行后分发到SRC的数据流预估为每年710PB，算力至少需要 25PFlops[1,6]。这给 SKA设计人员带来了两大技术挑战：如何以较低功耗提供足够的算力来处理数据流；如何将如此大量的数据分发传输到位于全球各地的 SRC[7-9]。

截至到2021年底公布的最快的高性能计算机(HighPerformanceComputing，简称HPC）为安装在日本神户Riken计算科学中心的Fugaku1）,HPL基准测试能力为442PFlops，该超算基于富士通定制的ARMA64FX处理器，并使用富士通的TofuD 互联技术进行节点之间的数据传输；另外随着网络新技术的发展，包括多芯光纤技术（Multi-CoreFiber，简称MCF）等，当前全球互联网的总带宽已经达到了618Tbps。与业界最快的HPC 和全球的互联网络相比较，SKA1的算力需求与数据传输规模不算很大，但在单一科学研究领域已经属于相当海量的规模，另外由于SKA科学研究方向较多，观测模式多样[10-12]，由此导致科学处理的数据流程十分复杂[13]，HPC 通常并不能满足其多样化、定制化的需求，SRC的处理将需要异构硬件对不同的科学观测使用不同的处理管线[14-16]，而这些管线根据数据密集型、计算密集型、存储密集型等进行分类处理。

本文从阵列的数据接收开始，到最后到达SRC的科学数据（含图像、元数据、脉冲星候选体等数据[17]）的详细情况，通过对其主要包括的数据传输速率以及算力需求来介绍SKA1的具体数据流，由于SKA1的观测配置目前尚未最终固化，当前对数据流仅进行模型预估处理；通过对SKA1的阵列布局具体情况及阵列部署的具体原则，对数据流进行定量化的描述；并通过对不同阵列在目前CSRC-P上进行的实验和测试，得出具体数据流，以此来阐述SKA1数据流的概况与全规模SKA正式运行后，对CSRC-P计算、存储和算力的影响。从而给出对未来CSRC-P数据模拟的一些建议和规划。

# 2 SKA数据流

来自射电源的无线电信号到达SKA望远镜阵列后被天线接收，经过模拟数字转换器（Analogto digitalconverter，简称ADC）转换为数字信号，随后数据流进人中央信号处理系统（CenterSignalProcessing，简称CSP）进行相关处理，输出可见度数据，这些数据将经过初步预校准，产生校准数据、图像数据和其他元数据，经深度处理后，这些数据将开放给科学团队，进行后续的科学研究工作。

如图1所示，在整个数据观测处理流程中，SKA1-low的外围站通过远程处理设施（RemoteProcessingFacilities，简称RPF）处理后与核心站通过中央处理设备（Central Processing Facilities,简称CPF)处理后的数据传输到科学操作中心（Sci-enceOperations Centre，简称 SOC），SKA1-mid的所有台站直接通过CPF传输到SOC，后续经由科学处理中心（ScienceProcessingCentre，简称SPC）分发到分布于各大洲的 SRC，由 SRC 将数据开放授权给科学家和用户。

![](images/74a14b38c4d557555c7680357b94aadf4031d50494ac53f1a55b725d899df7fb.jpg)  
图1SKA观测数据流示意图Figure 1 Data Flow Diagram of SKA Observation

根据当前最新的设计基线[18]，SKA1 的详细参数如表1所示，其中的 $N _ { f }$ 为观测频率通道最大值，实际观测中不会超过该值，对于SKA1-mid观测而言，大多数的观测模式下该值较小，以SKA-VLBI为例，频率通道一般64K 就可以满足观测需求[19]。

表1 SKA1 阵列参数Table 1 Parameters of SKA1 Array  

<html><body><table><tr><td></td><td>SKA1-low</td><td>SKA1-mid</td></tr><tr><td>天线数量Nant</td><td>131072</td><td>197</td></tr><tr><td>积分时间tdump</td><td>0.6s</td><td>0.08s</td></tr><tr><td>频率通道Nf</td><td>256,000</td><td>256,000</td></tr><tr><td>波束Nbeam</td><td>1</td><td>1</td></tr><tr><td>阵列/口径大小Ds</td><td>35米</td><td>13.5米/15米</td></tr><tr><td>最大基线Bmax</td><td>80公里</td><td>150公里</td></tr><tr><td>观测带宽△v</td><td>300MHz</td><td>770MHz</td></tr><tr><td>分辨率</td><td>0.25arcsec</td><td>7arcsec</td></tr></table></body></html>

当前 SKA确定了5个首要的科学目标（KeyScienceProject，简称KSP)，包括宇宙黎明和黑暗时期探测，星系演化、宇宙学与暗能量研究，利用脉冲星和黑洞进行引力的强场检验，宇宙磁场的起源和演化，孕育生命的摇篮，这些KSP均包括基础物理学、天体物理学或者宇宙学中尚未解决的问题[1,20,21]，同时也孕育着包括宇宙第一缕曙光的重大科学发现。随着 SKA1的开工建设，不需要整个SKA 阵列灵敏度、分辨率或者频率覆盖范围的重要科学主题被确定为高优先级（HighPriority Sci-enceObjective，HPSO）项目，经过广泛的论证和讨论，我国也确定了‘ $\cdot 2 { + } 1 ^ { \ ' }$ 的战略部署，即确保两个优先突破领域和若干具有特色的研究方向，并于2020年启动了2项 SKA科学专项，分别为宇宙再电离（theEpochofReionisation，简称EoR）项目和脉冲星项目，EoR将利用当前SKA先导阵列的观测数据再现宇宙的黎明，同时参加大天区的低频巡天，从统计上揭示宇宙再电离时代的宇宙整体结构特性；脉冲星项目主要包括脉冲星搜索（PulsarSearch，简称PSS）和脉冲星计时（Pulsar Timing,简称PST)，两者主要聚焦于检验引力波理论和探测发现超大质量黑洞的合并事件[1]。

根据当前SKA先导阵列MWA、ASKAP、LO-FAR等的经验，需要传输归档到SRC的数据除了数据立方体数据外，还包括整个流水线处理优化的UV数据、用于校准流水线的中间产品、UV格点化数据、点源扩散函数（PointSpreadFunction，简称PSF）立方体以及多种分辨率的加权和权重信息等[22-25]。

接下来数据流的预估将主要依据HPSO 科学目标[10,26]及其观测时间占比，整个流程包括观测数据的初步生成、经过相关处理、预处理等流程。当然除此以外，最终的科学数据还包括项目负责人(PrincipalInvestigator，简称PI）领导的各个重要观测、其他科学发现以及SKA-VLBI项目等。

# 2.1 观测台站端

阵列中的天线接收到原始的模拟信号后，首先将信号数字化，为了提高信号的时间和频率分辨率，还会使用有限脉冲滤波(Finite Impulse Response,简称FIR）和快速傅里叶变换(FastFourierTrans-form，简称FFT)操作。对于SKA1-low还会进行波束合成来进行信号的校准和时延补偿操作。

此处假定天线数目为 $N _ { a n t }$ ，每个天线有 $N _ { p o l }$ 路极化输出，信号的采集带宽为 $\Delta \nu$ ，由奈奎斯特采样定理可知，采样率至少为 $2 \Delta \nu$ ，在使用N阶FIR时，计算量大约为 $2 N _ { t a p }$ ，根据FFT的算法复杂度$O ( n l o g _ { n } )$ 可知，FFT运算的运算数为 $N l o g _ { N }$ ，此时每个站经过多项滤波器后需要的操作总数量级为：

$$
2 N _ { t a p } N _ { a n t } N _ { p o l } \Delta \nu + 2 N _ { b a n d s } l o g _ { 2 } ( 2 N _ { b a n d } ) N _ { a n t } N _ { p o l } \Delta \nu _ { b a n d }
$$

对于波束合成而言，通过给每个天线提供正确的延迟来进行校准，主要用于高时间分辨率和高频率分辨率的科学应用，比如脉冲星、行星际闪烁等，SKA1-low的相关处理机波束合成部件（CorrelatorBeamFormer，简称CBF）接收512个站的数据，并生成斯托克斯的四个参数数据。不过此时的校准相对于FFT和FIR而言，计算运算量较小，此处评估暂时忽略该项，所以此时对于每个观测台站而言，其输出的整体数据速率大约为：

由上式可知，采集带宽和采样比特数极大地影响了每个台站或阵列的数据流，根据表1进行估算，可知从台站端到达CSP的速率约在Tbps 量级。中频阵列共计197 (其中64面属于当前MeerKAT)面望远镜，原始数据输出速率约为2TB/s；低频阵列共计131072个天线，原始数据输出速率为158TB/s.

# 2.2 CSP

CSP主要用于将来自台站端的数据进行相关处理操作，在相关之前会进行诸如时延补偿的操作，用于消除由于地球自转引起的条纹旋转；同时进行更精细的信道化，用于提高分辨率，并做带通滤波用于矫正台站多项滤波的影响。根据科学目标的不同，划分的精细化通道不一定相同，此处假定为 $N _ { c h a n }$ 。在CSP还会进行射频干扰的去除(Fadio FrequencyInterference，简称RFI），由于其计算量较小，此处估算暂时不考虑，所以此时CSP输出的数据速率主要为台站的两两相关处理产生的：

$$
R _ { c s p } \propto \frac { N _ { b e a m s } N _ { c h a n } N _ { s t a t } ^ { 2 } N _ { p o l } ^ { 2 } } { t _ { d u m p } }
$$

由于数据输出速率与台站数的通道数和台站数目的平方成正比，从表1可知，对于输入可见度的数据速率预估为SKA1-low的数据数据速率为7.15Tbps,SKA1-mid的数据数据速率为6.4Tbps.

以SKA1-mid 为例，CSP将来自天线的输入带宽划分为多个频率通道，然后分别做互相关处理，此时的数据流输入为：133个SKA天线（每个100Gbps输出带宽）和64个MeerKAT天线（每个40Gbps输出带宽）接收数据，CSP的总输入带宽约为57Tbps，由于成像数据处理与脉冲星处理的流程不同，对于成像而言，采用两级信道化，第一级为512个粗信道，第二级为64000精细化通道；对于脉冲星搜索而言，在300MHz的子频带上提供约 $7 5 \mathrm { k H z }$ 的信道化通道，将时间分辨率降低到约～$6 4 \mu \mathrm { s }$ ；以6.4Tbps 的速度输出数据[18]。

相关处理将输出可见度数据，最大的分辨率在SKA1-mid的所有基线上可以达到0.1s的积分时间。而相关处理的输出结果主要取决于积分时间和通道数目。基线依赖平均（BaselineDependentAv-eraging，简称BDA）技术可以减少基于射电干涉仪基线分布的可见度数据量，通过对全规模SKA1-low的模拟，预计使用BDA可以将可见度数据量在不同的时间间隔上减少约 $5 0 \% \sim 8 5 \%$ [27-29]。

# 2.3 SDP

SDP接收来自CSP输出的数据进行初步成像预处理，虽然目前SKA最终的成像策略尚未确定，不过从当前几个SKA探路者项目（包括欧洲的LO-FAR、澳大利亚的MWA和ASKAP）来看，将主要包括校准、成像的迭代主循环（Major）和反卷积的迭代次循环（Minor)，其中的Major/Minor 为主要的计算资源部分。经过数次迭代后，SDP使用改进的天空模型推导出新的校准参数，并开始新的校准循环以进一步增强模型，最后通过恢复残差图像中的源来创建最终的天空图像。SKA1阶段SDP从相关处理设备获取的数据主要包括图像和校准数据等，通常不会保留可见度数据，但对于SKA1-low的高优先级项目宇宙再电离EoR例外，因为该项目需要保留可见度数据才能有效地去除前景干扰。SKA1-mid的SDP接收来自CSP的输入数据以及来自望远镜管理(TelescopeManager,简称TM)的数据[30]，并生成包含科学产品和校准产品的数据，主要为连续谱、谱线立方体数据成像数据，脉冲星搜索的候选数据，暂现源探测数据，单天线强度数据以及消除大气和电离层影响的校准数据等。

# 2.4 SRC计算负载需求

SKA一个重要的挑战就是需要管理和处理来自不同数据处理流程的数据，并产生高动态范围的图像和其他数据产品，提供对后续科学的支持[31]。根据SDP的当前设计，标准的数据产品将根据每个观测项目来制定。对于成像观测而言，均可以在三个维度(两个空间，一个光谱)、偏振及图像中产生最大分辨率的数据产品[32]，而其中数据量缩减最多的阶段就在将可见度数据进行成像处理的操作过程。

郭绍光等.

![](images/bb428b4e0ff4d87d9f788a50556afe138647414dfafb359f1e08b49f97fc6871.jpg)  
图2数据流示意图Figure 2 Data Flow Diagram

详细的观测数据流示意图如图1所示，各个阶段的产品数据流示意图如图2所示。台站产生的原始观测数据，在SDP经过初步处理生成初步的科学数据产品，主要包括成像的数据（比如图像或者格点化的可见度数据）和其他数据，其中成像数据的大小十分依赖于通道数量，最后的文件大小正比于通道数量，这些数据通过洲际网络分发到每个区域数据中心的子网络，天文学家通过互联网连接到区域数据中心进行数据处理，此时的数据称为高级数据产品（AdvancedDataProducts，简称ADP),此时的ADP可以通过SKA区域中心或者云的方案提供给最终的科研人员。

![](images/c1636b6a9edfc97e0d2fc0fe561ab07bb7901c5478e759293786fc66b05d7146.jpg)  
图3SKA1高优先级项目观测时间与计算负载评估Figure 3 Estimation observate time and compute load ofSKA1 HPSO

在SKA-1的所有处理流水线中，成像管道占据了主要的计算需求和资源，如图3约占SKA1-low观测时间 $1 5 \%$ 和 $3 1 \%$ 的EoR成像和功率谱观测，对应的计算负载约为 $3 1 \%$ 和 $5 5 \%$ ；非成像处理管道对计算的需求相对较小，比如脉冲星搜索流水线系统(Pulsar SearchPipeline,简称PSP),约占SKA1-low上HPSO 时间的 $3 9 \%$ 和 SKA1-Mid 的 $5 \%$ 的时间。对于SKA1-low而言，如果不包含EoR的UV可见度数据，科学数据速率约为3Gbps，如果增加UV可见度数据，那么数据率将增加到25Gbps；对于SKA1-mid而言，科学数据速率约为9Gbps [33]。

以PSP为例，仅需要实时校准（Real-timecal-ibration，RCAL)；但对于连续谱成像而言，还需要迭代自校准（Iterativeself-calibation，ICAL），生成泰勒项图像的数据准备管线（Data preparationpipeline producing Taylor-term images，DPrepA),生成粗信道化图像的数据准备管线（Data prepa-ration pipeline producing coarse channelised im-ages，DPrepB)；而谱线成像管线还需要额外的生成精细信道化图像的数据准备管线（Data prepa-ration pipeline producing fine channelised images,DPrepC)。

从图3可知，通过相应的加权计算，最后的计算负载约为SKA1-low需要至少13.6PFLOPS，SKA1-mid需要至少11.5PFLOPS，所以SKA1阶段SRC需要的算力预估为25.1PFLOPS.

# 3 SKA1阵列布局

为了实现SKA的科学目标，在建设成本与技术方面要均衡考虑，需要建造一个满足极端性能要求而且造价相对可控的望远镜。这需要对当前的科学需求及各种技术参数（阵列的基线长度、尺寸大小、天线灵敏度、功耗等）进行评估。最终确认了由包含澳大利亚和南非为台址的方案。

在 SKA的阵列布局和设计中，优先考虑了KSP科学观测的需要，通过基线长度的增加，来提高空间分辨率，采用核心阵列，用于增加UV覆盖，提高灵敏度。另外在设计中还考虑了包括但不限于频率范围、灵敏度、观测带宽、极化能力、采集面积、基线长度、处理能力等因素。其中最重要的几个因素如下：

·分辨率：实现高优先级科学所需要的分辨率需求。分辨率取决于频率设置，高频相对于低频而言，更容易实现高空间分辨率。比如150KM的阵列，在8GHz观测时，其分辨率可以达到0.0629arcsec·UV 快照覆盖：基线向量的二维分布决定了瞬时空间频率的覆盖范围，应该尽可能多地覆盖到UV平面，在螺旋阵列的布局中，快照覆盖主要由螺旋的旋转角度、螺旋臂上天线的位置以及螺旋臂的数量决定。在图4，5可以看到螺旋的角度以及天线的位置都经过了调整，以提供良好的UV覆盖

·核心区域：核心区域主要考虑提供足够的灵敏度，用于支持脉冲星搜索观测和HI线的观测

# 3.1 SKA1-mid

SKA1-mid望远镜的运行频段为 $0 . 3 5 \ \sim \ 1 5 . 3$ $\mathrm { G H z }$ ，位于南非的卡鲁沙漠，主要进行脉冲星、21厘米中性氢和连续谱的高灵敏度观测等科学研究[18]。该望远镜由133个直径为15米的偏置格里高利天线，和MeerKAT望远镜建造的64个直径为13.5米的天线组成。SKA1-mid有一个直径为1公里的核心阵，一个随机放置的3公里的二维阵列和三个螺旋臂，最长基线为150 公里[5,34]，具体的布局示意图如图4所示。

# 3.2 SKA1-low

SKA1-low望远镜的运行频段为 $5 0 \sim 3 5 0 ~ M H z$ ，部署在澳大利亚西部的默奇森射电天文台，主要进行宇宙再电离、脉冲星、太阳系外星系等科学研究[18]。SKA1-low共有131072个对数周期天线，这些天线分为512个站，每个站 256个天线。这些站点中的 296个将被配置到一个中心核心区域，其余216个沿三个旋臂部署，最长基线65公里[34。具体的布局示意图如图5所示。

当前的孔径综合阵列技术在进行校准和成像算法方面已经相对成熟，但对于SKA1-mid的量级数据还需要进行软件和算法的研发，才能支持如此海量的数据，并在减少人工输入的情况下得到更好的动态范围[18]。

# 4 实验测试

本章节列举了使用 $\mathrm { O S K A R ^ { 2 } } )$ 进行 SKA1-low和SKA1-mid的模拟数据生成，主要阐述了模拟过程的思路、方法、运行及计算的时间和最后产生的数据文件大小等。

OSKAR为剑桥大学开发的用于SKA模拟的一套软件，基于射电干涉测量方程（RadioInterfer-ometerMeasurement Equation，简称RIME）模拟生成可见度数据，主要功能为模拟台站波束、干涉阵列数据，可以生成对应的二进制可见度数据或测量集数据（MeasurementSet，简称MS），同时还可以将FITS文件转变为天空模型、对可见度数据增加噪声等功能。

模拟实验的策略为选取不同的天空模型源数目，分别为9,100,1024,10000；观测时间从1秒到24小时，分别为1s,6s,60s,600s,1200s，2400s,3600s,7200s，14400s，28800s，43200s，54000s，72000s,86400s，频率通道默认为1，SKA1-mid的观测频率选定为 $1 . 4 \mathrm { G H z }$ ，带宽为1KHz，SKA1-low的观测频率选定为200MHz，带宽为 $\mathrm { 3 0 M H z }$ 。

# 4.1 SKA1-mid模拟数据测试

对于SKA1-mid的模拟试验，因为计算量不高，故使用了2种不同的GPU板卡，用于评估整套模拟系统的可扩展性和稳定性，板卡分别为NVIDIA的TeslaK40M和TeslaK20X.其中TeslaK20X基于Kepler架构，有2688个核，具备6GB的内存，总线带宽可达249.6GB/s，双精度的理论值为1312GFLOPS；Tesla $\mathrm { K 4 0 m }$ 基于Kepler 架构,有 2880个核，具备12GB的内存，总线带宽可达288.4GB/s，双精度的理论值为1682GFLOPS;可知从具备的核心数、内存、总线带宽和理论值，Tesla $\mathrm { K 4 0 m }$ 均优于K20X，从对阵列的实测结果图6,7,8也可以看到， $\mathrm { K 4 0 m }$ 的试验参数比K20X有所提升，不过提升不大，主要因为两个板卡属于同一个系列，不过 $\mathrm { K 4 0 m }$ 还是具有优势的，在多点模拟过程中，消耗的时间均低于对应的K20X显卡。

![](images/67610400c4254da87295b4d4fd8e00c4b0004a32d6b71464d2a1220771dc56dd.jpg)  
图4 SKA1中频阵列布局示意图Figure 4 Layout diagram of SKA1-mid Array

![](images/8479cb1b6c8cd02c22128bd9d6c9850d77d95795725d0a7656889e464361ea8d.jpg)  
图7SKA1中频阵列 $\mathrm { K 4 0 m }$ 模拟 Figure 7 Simulation of SKA1-mid based on Tesla $\mathrm { K 4 0 m }$

![](images/70eb9721d377d42dc16f9392c3e2660b8930cc71d322f9d2baa08f2c1781fd27.jpg)  
图6SKA1中频阵列K20X 模拟 Figure 6 Simulation of SKA1-mid based on Tesla K20X

郭绍光等.

![](images/68fbbcfa96003ed6555ca07a1030f0743c6cc196260e8a848f6f9ba1d1ec0c68.jpg)  
图5SKA1低频阵列布局示意图Figure 5 Layout diagram of SKA1-low Array

![](images/504e1c003ffbe175e7b69d6b87266a70dc33f5caded19cafdab594fe253cfb44.jpg)  
图8SKA1中频阵列K20X与 $\mathrm { K 4 0 m }$ 模拟对比 Figure 8 Simulation compare of SKA1-mid between Tesla K20X and $\mathrm { K 4 0 m }$

# 4.2 SKA1-low模拟数据测试

由于SKA1-low的台站较多，算力需求比较大，将使用China-SRC平台进行上述模拟测试，CSRC-P搭载的GPU 型号为NVIDIA TeslaV100SXM2,该GPU采用Volta架构，有5120个核，具备32GB内存，总线带宽可达897GB/s，双精度的理论值为7834TFLOPS。在对SKA1-low进行模拟时，可以看到对于观测时长在2400s以内的数据，模拟时间均在100 秒以内，充分显示了V100 芯片在计算方面的强大优势。

![](images/5f1fd76da492756c62b13fc8c279256847d4f0df3079b24fce19a5d9a0a46c9d.jpg)  
图9SKA1低频阵列模拟数据生成消耗时间Figure 9 Simulation data generation time consumption ofSKA1-low Array

从表2看到，最终的模拟数据大小与天空模型中的源相关性不大，模拟所花费的时间也基本一致，模拟的时间与最终生成的可见度数据的大小，主要取决于观测的时间。并且通过设定观测的频率通道可知，文件的最终大小正比于该值，对于SKA1-low模拟而言，如果使用表1中最大的频率通道，每秒产生的可见度数据大小约为2.048GB，约2TB/s。

# 5总结与展望

SKA无疑将是有史以来最大的射电观测基础设施之一，通过对SKA1整套系统的数据流进行了基于模型的预估、分析和模拟，其Tbps的数据流、PB级的存储归档需求及观测复杂性，对后续的数据管理、处理、计算、存储和网络都提出了最严峻的挑战，通过对整个数据流的讨论，为后续的中国SKA区域中心的正式运行提供数据系统级的支持。项目将结合射电天文技术以及包括信息、通信、计算机等现代信息技术。SKA 的超大数据流将极大地改变天文研究的方式，而使SKA成功运行则需要对传统框架设计进行革命性的改进和突破。在 SKA1阶段就需要联合电子学、计算机技术、信息等领域多个学科的专业知识来进行应对。SKA也将特别推动信息技术、天文软件和通讯技术等的发展。

致谢向评审人和对该文有帮助的人士表示谢意．本研究使用了由国家重点研发计划大科学装置前沿研究专项(2018YFA0404603）资助研制的中国SKA区域中心原型机的资源。

# 参考文献

1 武向平主编.中国 SKA 白皮书(中文版).北京：科学出版社，2017   
2 中国参加 SKA(第一阶段)综合论证报告.技术报告，科学技术部.2018   
3 An T,Wu X P,Hong X Y, SKA data take centre stage in China.Nat Astron, 2019,3:1030-1030   
4 Guo SG,ZhengXY,MaoYF,etal.Scheme and Prospectof the SKA Big Data Transfering(in Chinese).E-science Technology& Aplication,2018，9(3):3-13[郭绍光，郑小盈，毛羽丰，等.SKA 海量数据传输的方案及展望．科研信息化技术与 应用，2018，9(3):3-13]   
5 Swart GP,DewdneyPE.Highlightsof the SKA1-MidTelescopearchitecture.JournalofAstronomical Telescopes,struments,and Systems,2022,8(1):011021   
6 Quinn P,van Haarlem M,AnT,et al.SKA Regional Centres White Paperv1.0.Technical Report,Square Kilometre Array. 2020   
7 Guo SG,An T,Xu ZJ,etal.Progressand Prospectof transcontinental high-speed data transmissionatSKARegional Center in China(in Chinese).ChinaXiv:T202206.00291(2022）[郭绍光,安涛，徐志骏，等．中国 SKA 区域中心跨洲际高速数据 传输进展及展望．ChinaXiv:T202206.00291(2022)].   
8 JongeriusR,Wijnholds S,NijboerR,etal.AnEndToEndComputing Modelfor the SquareKilometreArray.Computer, 2014,47(9): 48-54   
9 An T,Wu X C,Lao B Q,et al. Status and progress of China SKA Regional Centre prototype.arxiv:2206.13022   
10 QuinnP,AxelrodT,BirdI,etal.DeliveringSKAscience.In:ProceedingsofAdvancing Astrophysics withtheSquare Kilometre Array (AASKA14).Giardini Naxos,2015   
11 An T.Science opportunities andchallenges associated with SKAbigdata.ScienceChina: Physics,Mechanics & Astronomy, 2019,62(8):121-126   
12Holit C,Johnston-HolittM,DehghanS,etalAnOverviewoftheSKA ScienceAnalysisPipeline.In:AstronomicalData Analysis Software and Systems XXV.San Francisco: Astronomical Society of the Pacific,20l7.367-370   
13 Lao B Q，Zhang Y K，An T,et al. Software Platform on China SKA Regional Center Prototype System(in Chinese).ChinaXiv:202206.00173．[劳保强，张迎康，安涛，等.(2022)．中国 SKA 区域中心原型系统－软件平 台.ChinaXiv:202206.00173]   
14 Xu Z J，An T,Guo S G,et al. A machine learning dataset for FRB detection in raw data(in Chinese).ChinaXiv:T202206.00321.[徐志骏，安涛，郭绍光，等.(2022)．一个面向原始数据搜寻的快速射电暴数据集.ChinaXiv: T202206.00321]   
15 Wei JW,Zhang CF,Zhang ZL,etal.Paraleloptimizationof thepulsarsearch pipelineon China SKA Regional Centre Prototype(in Chinese)．ChinaXiv:T20206.00297．[韦建文，张晨飞，张仲莉，等.(2022)．低频射电脉冲星搜索的性能优化方法. ChinaXiv:T202206.00297]   
16 Wei J W,Zhang CF,LaoB Q，etal.Optimization of paralel processing of Square Kilometre Array low frequency imaging pipeline (in Chinese)．ChinaXiv:T20206.00292．[韦建文，张晨飞，劳保强，等.(202).SKA 低频成像管线并行优化 化.ChinaXiv:T202206.00292]   
17 Braun R,BourkeTL,GreenJA,etal.Advancingastrophysics withthesquare kilometre arry.In:ProcedingsofAdvancing Astrophysics with the Square Kilometre Array (AASKA14).Giardini Naxos, 2015.id.174   
18 Dewdney P.SKA1 System Baseline Design. Technical Report, SKA Organisation. 2016   
19 Operational Model forinclusionof SKAin Global VLBI,JIV-ERICand SquareKilometre ArrayPhase1Project,Submision date:15/6/2020   
20 Carrlli CL,Rawlings S.Sience withthequare KilometerArray:Motivation,KeySience Projects,StandardsandAsumptions.New Astronomy Reviews,2004,48(11): 979-984   
21 Bourke,T,Braun,R,Fender,R,etal. (2015).Advancing Astrophysics with the Square Kilometre Array (AASKA14).   
22 WhitneyA,BoolerT,BowmanJ,etal.The MurchisonWidefield Array(MWA):Current StatusandPlans.In:American Astronomical Society,AAS Meeting #218.Buletinof the AmericanAstronomical Society2011Vol.43,id.132.07   
23Harlem MPV,WiseMW,GunstA W,et al.LOFAR:TheLowFrequency Array.Astronomy&Astrophysics,2013,556(7): 629-635   
24Jonas JL.MerKATas an SKA Pathfinder.Jonas JL.The MeerKAT SKA precursortelescope.In: Proceedings of Panoramic Radio Astronomy:Wide-feld1-2GHz research on galaxy evolution.Edited byG.Healdand P.Serra.Groningen,209.id.4   
25JohnstonS,Bailes M,BartelN,etal.Science with theAustralian Square KilometreArrayPathfinder.Publicationsof the Astronomical Society of Australia,2007,24(4):174-188   
26FordD,BoltonRCColegateT,etal.TheSKA Cost/Performance Tol: A HierarchicalSKA ModelingTool.In:Proceedings of Wide Field Astronomy& Technology for the Square Kilometre Array.Chateau de Limelette,2009.id.22   
27 Cotton W D.Special problems in imaging.In: Synthesis Imaging,ed.R.A.Perley,F.R.Schwab,&A.H.Bridle.1986. 123-136   
28 CottonWD.Special Problems in Imaging.InAstronomical Societyof thePacificConference Series，Vol.180,Synthesis Imaging in Radio Astronomy II,ed.G.B. Taylor, C.L.Carili,&R.A.Perley.1999.357-370   
29DengQW,WangF,Deng H,etal.Performance evaluationofbaseline-dependentaveraging basedonful-scale SKA-LOW simulation. Research in Astronomy and Astrophysics,2022, 22(4):045014   
30 Natarajan S,BarbosaD,BaracaJP,etal.SKATelescope Manager(TM):statusandarchitectureoverview.In:Proceedis of the SPIE.2016.9913:id.991302   
31Torchinsky SA,van Ardenne A,van den Brink-Havinga,et al.SKA DataFlowand Procesing.?Alexander P,BregmanJ A,Faulkner A J.SKA DataFlowandProcessng.In:Proceedingsof Wide Field Astronomy& Technology for the Square Kilometre Array. Chateau de Limelette,2009. id.16   
32 Spekkens K, Chiang C,Kothes R,et al. Final Report to LRP Panel: the Square Kilometre Array.   
33Broekema P C,van Nieuwport R V,Bal HE.The square kilometre array science data processor.Preliminary compute platform design. Journal of Instrumentation,2015,10(7):C07004.   
34 Grainge K,AlachkarB,AmyS,etal.Square Kilometre Array:Theradio telescopeof theXXIcentury.AstronRep,2017, 61,288-296

表2SKA1 低频阵列模拟数据大小 (字节)Table 2 SKA1-low simulation filesize (Bytes)  

<html><body><table><tr><td>观测时间丨天空源数目</td><td>9</td><td>100</td><td>1024</td><td>10000</td></tr><tr><td>1</td><td>8442505</td><td>8442023</td><td>8442025</td><td>8442024</td></tr><tr><td>6</td><td>50365065</td><td>50364583</td><td>50364584</td><td>50364584</td></tr><tr><td>60</td><td>503178874</td><td>503178392</td><td>503178394</td><td>503178394</td></tr><tr><td>600</td><td>5030775854</td><td>5030775370</td><td>5030775370</td><td>5030775372</td></tr><tr><td>1200</td><td>10061493857</td><td>10061493377</td><td>10061493373</td><td>10061493375</td></tr><tr><td>2400</td><td>20122929856</td><td>20122929375</td><td>20122929381</td><td>20122929377</td></tr><tr><td>3600</td><td>30184365864</td><td>30184365380</td><td>30184365381</td><td>30184365385</td></tr><tr><td>7200</td><td>60368673866</td><td>60368673380</td><td>60368673379</td><td>60368673381</td></tr><tr><td>14400</td><td>120737289864</td><td>120737289385</td><td>120737289380</td><td>120737289388</td></tr><tr><td>28800</td><td>241474521875</td><td>241474521391</td><td>241474521386</td><td>241474521386</td></tr><tr><td>43200</td><td>362211753879</td><td>362211753392</td><td>362211753398</td><td>362211753392</td></tr><tr><td>54000</td><td>452764677879</td><td>452764677396</td><td>452764677394</td><td>452764677392</td></tr><tr><td>72000</td><td>603686217875</td><td>603686217395</td><td>603686217390</td><td>603686217398</td></tr><tr><td>86400</td><td>724423449873</td><td>724423449399</td><td>724423449400</td><td>724423449397</td></tr></table></body></html>

# Scientific data flow and array simulation analysis for the SKA-1 era

GUO ShaoGuang $^ { 1 , 2 }$ \*, Lu Yang1，AN Tao $^ { 1 , 2 }$ , LAO BaoQiang $^ { 1 , 2 }$ . XU ZhiJun $^ { 1 , 2 }$ , WU Xiaocong $^ { 1 , 2 }$ & LV WeiJia $^ { 1 , 2 }$

1. SKARegional Centre JointLab,Shanghai AstronomicalObservatory,Key LaboratoryofRadioAstronomy,Chiese Academy of Sciences, Shanghai 200030, China; 2.SKA Regional Centre Joint Lab,Peng Cheng Laboratory,Shenzhen,518066,China

After years of planning for the next generation of radio telescopes,the Square Kilometer Array (SKA),the construction of the SKA phase one (SKA1) had started in July 2021.After the formal operation of SKA1, it is expected that 750 petabytes of scientifcally processed data will be generated every year.The data wil be stored at SKA regional centers around the world for further analysis by researchers. In this paper, the models of SKA observation station,central signal processr,scientifc data processing and regionalcenter are quantitatively analyzed.Based on the high-priority scientific observation of SKA1,the data fow evaluation at each stage and the demand for computing power of scientific data processng are obtained. Taking the current SKA1-lowand SKA1-mid arrays as examples,the key factors affecting the layout of interference arrays including resolution,sensitivity and UV coverage are summarized.Finaly,OSKAR is used fordata simulation of interference array. Through the simulation of SKA1-mid,the scalability and stability of the system are obtained.Through the simulation of SKA1-low on CSRC-P,it can be seen that the design of prototype SKA regionalcenter in China has been fully optimized.And the detailed requirements of computing power and the detailed information of data volume are obtained.The SKA's demand for data processing,computing and storage also requires a combination of technologies and interdisciplinary efforts from areas such as electronics, communication,information technology and computer.