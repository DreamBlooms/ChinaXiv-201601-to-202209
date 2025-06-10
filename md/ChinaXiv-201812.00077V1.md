# 基于SDR平台的噪声聚合物理层安全传输方案的设计与实现

秦鹏翔‘²，任品毅²，杜清河}²，孙黎1,2(1.西安交通大学电子与信息工程学院，西安 710049;2.陕西省智慧网络与泛在互联工程技术研究中心，西安710049)

摘要：噪声聚合物理层安全方案通过编码设计，结合反馈控制可以充分地挖掘无线链路中引入的固有噪声资源，恶化窃听者的信道质量，增强通信系统的安全性能。为了在实际系统中验证与评估该方案的性能，基于软件无线电平台设计并实现了融合噪声聚合抗窃听功能的发射机、接收机方案；在此基础上，搭建了包含源节点、目的节点与窃听节点的抗窃听测试环境。以图像传输业务为测试案例，对误帧率、峰值信噪比等客观指标以及图像主观效果进行了评估。测试结果表明，合法接收端相比于窃听端在同一误帧率条件下可获得良好的信噪比增益；在同一信噪比条件下具有高峰值信噪比且清晰可辨的接收图像，验证了噪声聚合方案的有效性。

关键词：软件无线电；无线物理层安全；噪声聚合；图像传输 中图分类号：TN915.08 doi:10.19734/j.issn.1001-3695.2018.08.0555

# Design and implementation of noise aggregation scheme in physical layer security based on software defined radio

Qin Pengxiang1,², Ren Pinyi1,², Du Qinghe1, ², Sun Li1,2 (1.Schoolof Electronics& Information Engineering，Xi'an Jiaotong University，Xi'an710049,China;2.Shaanxi Intelligent Network &Ubiquitous Interconnection Engineering Technology Research Center,Xi'an71o049,China)

Abstract:With feedback control method,the physical layer security schemevia noiseaggregation can degrade the eavesdropper's channel qualityand enhance thesecurity performance ofcommunicationsystem by fully extracting the resourcesofinherent noise in wireless communication.Inordertovalidate and evaluate the performanceofthe scheme,this paper designed and realized a practical scheme fortransmiter and receiver with anti-wiretapping functions based on software defined radio platform.On basisof that,this paper established theanti-wiretappingtestenvironment，which includes a source node,adestination node and an eavesdropper node.Taking the testcaseof image transmision,this paper evaluated some objective indicators,such as frame error,peak signal noiserate and the subjective qualityof images.Test results show thatthere is satisfied SNRgain between Boband Eveforthesame frame errorrate.Moreover,clearand recognized received images with higher peak signal noiserate prove the effectiveness of the noise aggregation scheme.

Key words: software defined radio; wireless physical layer security; noise aggregation; image transmission

# 0 引言

随着无线通信技术的持续革新，多样化的移动业务融入了人们的生活。然而，无线传播环境的固有开放特性使通信系统始终面临着数据易被窃取、隐私难于保护等安全威胁[1]。基于密码学理论，传统的安全机制通过对数据进行秘钥加密来确保信息的安全传输。它的基本思想是使得窃听者破解信息时需要极高的计算复杂度，致使无法破解信息或者破解时间过长从而失去信息的时效性。然而，近年来高性能芯片正在快速发展，传统以计算复杂度为基础的加密机制面临巨大挑战。

物理层安全技术[2]则从另一角度去探索无线通信中的安全传输。不同于传统安全机制，物理层安全基于香农信息论，利用无线信道的物理特征，在不依赖于计算复杂度的情况下可以恶化窃听者信道质量，以此来增强安全。贺洪亮等人[3.4]结合网络编码与ARQ反馈关联数据包来增强文件的传输安全并研究了噪声反馈对提高物理层安全性能的关键作用。徐洪斌等人[5.6基于双向协作系统提出了星座旋转辅助方法与星座重叠方法来防止不可信中继对保密信息进行解码。丁志国等人7研究了天线选择对系统安全性能的影响。

噪声聚合[8物理层安全方案是近几年才被提出的新型物理层安全技术，其可以利用无线链路中固有噪声从而恶化窃听者的信道质量。配合反馈重传机制，可保证合法接收者可靠传输的同时，使窃听者解密极少甚至无法解密保密信息，从而实现安全传输。噪声聚合物理层安全方案利用了通常被认为有害的固有噪声，不需要引入人工噪声；仅仅配合反馈重传机制即可保证安全，实现简单且保密效果好；与大部分物理层安全技术相结合，可以进一步提高安全等级。

当前关于噪声聚合物理层安全方案的研究还处在理论分析和仿真评估阶段。文献[8]阐述了噪声聚合物理层安全方案原理，并仿真对比了应用噪声聚合方案时不同信道质量下合法接收者与窃听者的误码率、误帧率等指标。文献[9]分析了应用噪声聚合方案时二进制对称信道下合法接收者与窃听者的平均私密速率。截止目前，相关研究均未从实际系统中验证与评估噪声聚合物理层安全方案，现实意义较小。

基于以上思想和前人所做的研究工作，本文利用NI公司的通用软件无线电[10]外设（USRP-RIO）设计并搭建了面向噪声聚合安全方案的通信系统。以图像传输业务为例，测试并验证了噪声聚合物理层安全方案的有效性。

# 1 系统模型

面向噪声聚合的系统模型如图1所示，其中包含单个源节点Alice、单个目的节点Bob和单个窃听节点Eve。相比于Wire-tap 模型[1I]，该网络除了存在合法链路外，在Bob 与Alice之间还存在一条反馈链路。在Eve存在的情况下，Alice需要向Bob传输保密信息。

![](images/f5a08b5592c270230cd0e75479038be213b070156cedee5eff6b83dc377a886b.jpg)  
图1面向噪声聚合的系统模型

图1中， $M$ 表示需要发送的保密信息，经过安全方案处理后变为待传输信息 $\boldsymbol { \cal X }$ ； $h _ { \scriptscriptstyle B }$ 与 $h _ { \scriptscriptstyle E }$ 分别表示合法信道与窃听信道的信道增益； $n _ { \scriptscriptstyle B }$ 与 $n _ { { } _ { E } }$ 分别表示Bob与Eve 接收端噪声；Y与z表示Bob与Eve的接收信息； $\boldsymbol { M } _ { \scriptscriptstyle B }$ 与 $\boldsymbol { M } _ { \scriptscriptstyle E }$ 分别表示Bob与Eve恢复的保密信息。

当Alice向Bob传输保密信息时，由于无线传播环境的开放性，Alice发出的信号不仅经过合法信道被Bob所接收，也经过窃听信道被Eve所接收。假设Bob与Eve的接收机完全相同，合法信道与窃听信道均为准静态衰落信道且相互独立。由于Bob与Alice之间存在反馈链路，当Bob发生丢帧时，其可以通过反馈及时告知Alice并要求重传丢帧。但Eve与Alice之间没有反馈链路，当Bob收到正确帧后，Eve有可能仍未正确接收该帧。此时，Eve将永远失去其包含的保密信息，导致Eve无法完整接收，从而实现了安全传输。

在上述系统模型中，若没有安全方案，则Bob相比于Eve 仅仅存在反馈的优势。在此基础上，当合法信道质量与窃听信道质量相当且误帧率均接近于1时，Bob正确接收一帧后Eve仍未正确接收该帧的概率仅为 $5 0 \%$ 。此时，Eve大致可以正确接收一半的保密信息，保密效果差。

# 2 噪声聚合方案原理

噪声聚合方案可以利用信道中的固有噪声恶化信道质量。配合反馈机制，大大提高Bob正确接收一帧后Eve仍未正确接收该帧的概率，使Eve接收到的有效信息极少甚至为零，从而保证信息安全。现已被提出的噪声聚合方案原理如图2所示。

以错误概率为 $\boldsymbol { \varepsilon } _ { i }$ 的二进制对称信道为例。原始帧$X _ { 1 } , X _ { 2 } , . . . , X _ { n }$ 由等长分组的预发送的比特数据形成。在发送第奇数帧 $X _ { 2 t - 1 }$ 时，直接发送 $X _ { 2 t - 1 }$ ；当发送偶数帧 $X _ { 2 t }$ 时，则发送该偶数帧与上一个奇数帧的异或，即 $X _ { 2 t - 1 } \oplus X _ { 2 t }$ 。 $W _ { i }$ 为接收第$i$ 个帧时伴随的噪声。

噪声聚合方案使偶数帧需要与上一个奇数帧共同解包。若Eve丢失了一个偶数帧，则无法解密其包含的信息。即使Eve 正确接收到了偶数帧，但丢失了上一个奇数帧，也无法解密。由此看出，噪声聚合方案增大了偶数帧的丢帧率，等效恶化了偶数帧信道。虽然Bob与Eve的偶数帧信道同时收到了恶化，但是Bob与Alice间存在反馈链路，可以通过反馈协议进行可靠传输。

![](images/b8e66be8d7760383b49ef62ab5730a7ddff64971562ec247673e0251d24b1706.jpg)  
图2噪声聚合方案原理  
Fig.2Principles of noise aggregation

# 3 噪声聚合技术验证系统设计与实现

# 3.1验证系统概述

本文利用USRP-RIO设备，根据上文中的系统模型以及噪声聚合方案原理，设计并搭建面向噪声聚合的无线通信系统与测试场景。

测试方案的网络拓扑结构如图3（a）所示，测试场景如图3（b）所示。图3（a）中 $\mid h _ { b } \mid e ^ { j \varphi _ { b } }$ 、 $\mid h _ { e } \mid e ^ { j \Phi _ { e } }$ 、 $\mid h _ { b } ^ { ' } \mid e ^ { j \dot { \varphi _ { b } } }$ 分别表示合法传输信道、窃听信道以及反馈信道的信道增益。

系统中硬件部分主要由三台PC机、三台USRP-RIO 设备与一个外接时钟源构成。三台设备分别代表Alice、Bob 和Eve。

![](images/72e021a68f5610d7d02f0af6aba281d207736a9e1ffdd3920cc45cbdce12d127.jpg)  
Fig.1System model for noise aggregation   
图3测试方案的网络拓扑与测试场景  
Fig.3Network topology and testing scenario for noise aggregation

USRP-RIO设备以射频电路为主，实现无线信号收发、混频、数模或模数转换、数字上下变频等处理。三台设备采用同一个外接时钟源并各自通过一根PCIe总线分别与一台PC 机连接进行高速数据传输，实现无线信号的实时采集与基带处理。软件部分对基带数字采样信号进行处理，采用Windows平台下的Labview与Matlab 软件。此外，Labview通过.VI文件的前面板实现了人机交互。在Labview 中调用Matlab 脚本并编写代码，可以实现噪声聚合物理层安全方案以及其他基带数据处理；利用Labview多线程并行、模块化的特点，编辑.VI文件中的程序框图可以同时进行组帧与解帧，进而实现节点间实时的数据传输或反馈。

# 3.2链路与帧结构设计

根据对应用场景以功能需求的分析，面向噪声聚合的数字通信链路与帧结构设计如图4所示。

发射机 接收机目的地址 源地址 总字节数 子帧编号 有效位数 FCS8 bits 8 bits 32 bits 32 bits 16 bits 16 bits  
噪声聚合 解噪声聚合  
信道编码 MAC头 22 FCiss 信道解码解交织交织 同步头帧长度 FCS 导频 MAC协议数据单元 +512 bits16 bits16 bits 64 bits 4864 bits(QPSK); 9728 bits(16QAM) 数字解调  
数字调制 BPSK BPSK QPSK; 16QAM +信道估计+导频 MAC协议数据单元 匹配滤波  
脉冲成型 64 symbols 2432 symbols T1 位同步  
数字上变频 子帧1 子帧2 子帧18 4T 2496 symbols 2496 symbols 2496 symbols 数字下变频DAC物理帧头 聚合物理服务数据单元 ADC1 544 symbols 44928 symbols 4混频器 帧结构 混频器（) Z Z ）信道

aggregation

# 3.3 发射机设计

面向噪声聚合方案的发射机由基带部分与上变频部分组成。基带部分包括噪声聚合、信道编码、交织、数字调制、脉冲成型滤波，实现对数据的基带处理。上变频部分包括数字上变频、DAC（digital to analogconverter，数模转换器）与混频器，实现对数据的上变频处理。比特数据经过基带处理与上变频处理后转变为无线射频信号，通过天线发送出去。

# 3.3.1帧结构设计

链路的帧结构参考802.11标准。根据 802.11n中的帧聚合机制[12]，链路采用改进后的A-MPDU（MPDUaggregation）帧作为物理帧结构，如图4所示。

考虑到实际场景中信道的时延扩展、时变性以及通信系统的基带速率，设计的物理帧由544符号长度的物理帧头与44928符号长度的聚合物理服务数据单元组成。

物理帧头包含同步头、帧长度以及FCS（framechecksequence,帧检错序列)。其影响着位同步，故采用BPSK调制方式。由于过长的同步头会导致有效数据占物理帧长的比重变小，效率降低，而过短则会降低同步精度，故同步头选取长度适中的512位 $\mathrm { ~ m ~ }$ 序列。利用 $\mathbf { m }$ 序列良好的相关特性可以实现精确的位同步。16位的帧长度表明了该物理帧包含的有效子帧个数。物理帧头的FCS采用16位CRC校验。

聚合物理服务数据单元由18个2496符号长度的子帧组成。每个子帧包括64符号长度的导频与2432符号长度的MAC协议数据单元。考虑室内信道相干时间与发射机的基带速率，导频间隔长度即子帧长度应近似为2500符号长度。又考虑到导频需满足01出现概率相同、长度必须适中等原则，子帧选取64位m序列作为导频，用作直流偏执消除与信道估计。

MAC协议数据单元由经过卷积编码和交织的MAC帧头、MAC服务数据单元、FCS组成。其中，MAC帧头占112位，FCS占32位，MAC服务数据单元的长度由调制方式决定。若调制方式为QPSK，MAC服务数据单元占2288位；若调制方式为16QAM，MAC 服务数据单元占4720位。32位FCS采用CRC校验，用作对MAC服务数据单元检错。

MAC帧头由8位目的地址、8位源地址、32位总字节数、32位子帧编号、16位有效位数、16位FCS组成。其中，32位总字节数表示传输文件的总字节大小。16位有效位数表示该子帧中MAC协议数据单元所含有效信息位数。FCS采用16位CRC校验，用做对MAC帧头检错。

# 3.3.2信源数据处理

图像在无线保密通信中是常用的传输对象，通过对比Bob和Eve的图像质量也能够直观地看出安全方案的保密效果，故选取图像作为数据源。为了防止Eve由于图像配置信息丢失而无法显示图像，事先将图像文件拆分为配置信息部分与像素信息部分。测试时，Alice只传输像素信息部分。Bob与Eve接收完毕后将接收信息与已知的配置信息部分组合生成图像文件。

若Alice按图像行顺序发送像素点数据。当Eve彻底丢帧时，其只会失去该帧所含的行方向像素点信息。由于失去不相邻行方向信息并不影响整个图像识别，而同时失去相邻行方向信息的概率又极小，故Alice按图像行顺序发送无法实现图像保密。按图像列顺序发送像素点数据同理。

为了解决上述问题，在解析图像的像素信息时，将图像分割为合适大小的矩形块，并且对这些块随机排序并组帧发送。若Eve发生丢帧，由于每个帧含有许多相邻行列的像素点信息，故Eve将丢失该帧包含的图像块信息。此时，Eve将无法识别图像，达到图像保密效果。

# 3.4接收机设计

面向噪声聚合方案的接收机由下变频部分与基带部分组成。下变频部分包括混频器、ADC（analogto digitalconverter，模数转换器）与数字下变频，实现对数据的下变频处理。基带部分包括位同步、匹配滤波、信道估计、数字解调、解交织、信道解码与解噪声聚合，实现对数据的基带处理。无线射频信号被天线接收，经过下变频处理与基带处理后转变为比特数据。Eve与Bob接收机相同，但没有发射机。

# 3.4.1直流偏执消除

实验设备USRP-RIO为直接变频接收机[13]，即零中频接收机。与超外差接收机不同，其本振频率与载波频率近似相同，虽然简化了接收机结构，却引入了额外的直流偏执。

位同步需要选取相关峰值，而直流偏执的存在会导致相关后序列出现“假峰值"的情况。不仅如此，直流偏执还会改变判决量与标准星座点的欧氏距离，从而影响符号判决。如果不消除直流偏执，位同步以及符号判决等操作均无法正常进行。

Hanning窗可使大多数交流能量从直流区间中分离，从而消除位同步时出现的"假峰值”。但是Hanning窗会将基带信号在零频处的冲激同时消除，故仅利用此方法辅助实现位同步。位同步完成后，未经过Hanning窗的基带信号匹配滤波后如下：

$$
\begin{array} { r l } {  { y _ { k } = ( \sqrt { S } H m _ { k } + \sqrt { N } Z _ { k } + C _ { k } ) ^ { * } h _ { - k } ^ { * } } } \\ & { = \sqrt { S } H \sum _ { l } h _ { l } m _ { k - l } + \sqrt { N } \sum _ { l } h _ { l } Z _ { k - l } + C _ { k } \sum _ { l } h _ { l } } \end{array}
$$

其中： $\sqrt { s }$ 为发送与接收的联合增益， $H$ 为信道系数， $m _ { k }$ 为发送波形采样， $N$ 为噪声方差， $Z _ { \boldsymbol { k } }$ 为噪声， $C _ { k }$ 为直流分量，$\boldsymbol { h } _ { - \boldsymbol { k } } ^ { * }$ 为匹配滤波器的单位脉冲响应。

$y _ { k }$ 在最高信噪比 $n N _ { s s }$ 时刻采样后的 $y _ { n }$ 如下：

$$
y _ { n } = y _ { k } \mid _ { k = n N _ { s s } } = \sqrt { S } H a _ { n } + \sqrt { N } w _ { n } + C _ { k } \sum _ { l } h _ { l }
$$

其中： $w _ { n } = \sum _ { l } h _ { l } Z _ { k - l } \big | _ { k = n N s s }$ 为噪声采样， $\boldsymbol { a } _ { n }$ 为发送符号。根据 $\mathrm { ~ m ~ }$ 序列0与1数量相同的特征、导频为BPSK调制、 $w _ { n }$ 为0均值的高斯白噪声可知， $y _ { n }$ 取均值后只会留下 $C _ { k } \sum _ { l } h _ { l }$ 一项。消去 $C _ { k } \sum _ { l } h _ { l }$ 项即达到消除直流分量的目的，而且不会损失基带信号在零频率处的冲激信息。

# 3.4.2反馈协议设计

上文的系统模型中，反馈链路是Bob区别于Eve的重要方面，它保证了Bob的可靠传输。反馈链路需要反馈协议的支持，而反馈协议的选择会影响Eve的接收效果，进而影响系统的保密性能。目前，实际通信系统中的反馈协议大多采用ARQ（automatic repeat request，自动重传请求）协议。常用的ARQ协议有停止等待ARQ协议，连续ARQ协议以及选择性重传ARQ协议。

若采用停止等待 ARQ协议，发送端会不断重传一帧直到收到该帧对应的ACK（ACKnowledgement，确认）帧。但在信道质量不好时，发送端会长时间重传相同帧，导致传输效率过低。

若采用连续ARQ协议，由于存在滑动窗口，发送端可以在未收到ACK帧的情况下继续发送下一帧。但在信道质量不好时，会出现Go-back-N情况。此时，Aliec会重传Bob已正确接收的帧，导致Eve有更大概率接收正确帧从而降低系统保密性能。

若采用选择性重传ARQ协议，发送端可以不用等待接收端的应答，并持续发送多个帧，且只重传丢失帧。相比于停止等待ARQ协议，传输效率大大提高；相比于连续 ARQ协议，不会因为Go-back-N而重传Bob已正确接收的帧。

# 4 实验评估与性能测试

# 4.1实验参数

在实际的无线通信系统中，Alice与Bob之间为频分半双工通信，单载波调制，传输频段为5GHz，反馈频段为$2 . 4 \mathrm { G H z }$ 。由于Eve没有发射机，Eve只能在传输频段上被动窃听信息。无线数字通信链路的指标参数如表1、2所示。

表1数字通信链路指标与方法  
Table 1Indicators and methods in digital communication link   
表2数字通信链路参数与参数值   

<html><body><table><tr><td>指标</td><td>方法</td></tr><tr><td>信道编码</td><td>1/2卷积编码</td></tr><tr><td>交织编码</td><td>块交织</td></tr><tr><td>数字调制</td><td>QPSK；16QAM</td></tr><tr><td>脉冲成型(匹配)滤波器</td><td>根升余弦滤波器</td></tr><tr><td>位同步</td><td>最大似然时延估计[14]</td></tr><tr><td>相关峰值阈值设置</td><td>均值法[15]</td></tr><tr><td>信道估计</td><td>迫零估计</td></tr><tr><td>判决方式</td><td>最大似然判决</td></tr><tr><td>信道解码</td><td>维特比译码</td></tr></table></body></html>

Table 2Parameters and corresponding values in digital communication link   

<html><body><table><tr><td colspan="2">Comhmnunhcatronrhnk</td></tr><tr><td>参数</td><td>参数值</td></tr><tr><td>卷积编码八进制生成矩阵 块交织深度</td><td>[133,171]</td></tr><tr><td>根升余弦滤波器相关符号长度</td><td>24</td></tr><tr><td>根升余弦滤波器滚降系数</td><td>100</td></tr><tr><td>基带速率</td><td>0.25</td></tr><tr><td>发射机过采样速率</td><td>100kHz</td></tr><tr><td>接收机过采样速率</td><td>300ksps 1Msps</td></tr></table></body></html>

其中由于信道编码采用1/2码率的卷积编码，且物理帧包含帧头、导频等冗余信息。故实际中，QPSK调制方式下的传输速率大约为10kBps；16QAM调制方式下的传输速率大约为20kBps。

# 4.2观测界面

由于Alice、Bob、Eve实现的功能不同，各节点的人机交互界面略有差异但大致相同。以Eve节点为例，基于Labview的人机交互界面如图5所示。人机交互界面主要分为射频配置、基带配置、实时观测三部分。

在射频配置模块中，用户可以轻松配置收发天线口、过采样频率、发送或接收增益、生成或捕获方式、过采样速率等参数。

在基带配置模块中，用户可以对子帧个数、子帧长度、数字调制方式、脉冲成型滤波器相关符号数与滚降系数、接收序列长度、基带速率等参数进行设置。

在实时观测模块中，用户可以实时观测到接收信号的基带波形、功率谱、功率电平以及文件的实时接收进度、当前丢帧号、平均接收功率等信息。在接收完毕后，还可以读取到接收图像相比于原图的峰值信噪比、误帧率等指标。

![](images/a96d4e93ab980ab7d6622d8bfd233590127b28b149ea7b96ce4258e22c7345f9.jpg)  
图5基于Labview 的人机交互界面（Eve)  
Fig.5Interactive interface at Eve based onLabview

除了上述的主要模块外，人机交互界面还包括时钟源选择、发送文件选择、接收地址选择、对比文件选择等部分。

# 4.3测试结果

由于三台USRP-RIO 设备相同，故Bob与Eve 的噪声方差可认为近似相同，此时的平均接收信噪比只由平均接收功率决定。通过调整Bob与Eve的平均接收功率，就可以保证两者平均接收信噪比相同。

以图像传输业务为例，实验记录了不同调制方式、不同平均接收功率条件下，Bob与 Eve 的误帧率，如表3、表 4所示。

对比表3与4可以看出，在QPSK与16QAM调制方式下、同一误帧率条件下，Bob总比Eve 获得良好的平均接收功率增益，窃听者信道遭到了恶化。

表3QPSK 调制方式下Eve 与Bob 的误帧率

Table3 Frame error rate atBob andEve in QPSK modulation   

<html><body><table><tr><td>平均接收功率/uW</td><td>Bob 的误帧率(1)</td><td>平均接收功率/uW</td><td>Eve 的误帧率(1)</td></tr><tr><td>131</td><td>0.5726</td><td>136</td><td>0.6806</td></tr><tr><td>140</td><td>0.4420</td><td>145</td><td>0.4971</td></tr><tr><td>152</td><td>0.2856</td><td>149</td><td>0.4070</td></tr><tr><td>159</td><td>0.2157</td><td>162</td><td>0.2755</td></tr><tr><td>170</td><td>0.1329</td><td>170</td><td>0.2179</td></tr><tr><td>180</td><td>0.0655</td><td>178</td><td>0.1428</td></tr><tr><td>186</td><td>0.0337</td><td>185</td><td>0.0983</td></tr><tr><td>204</td><td>0.0174</td><td>202</td><td>0.0453</td></tr><tr><td>224</td><td>0.0076</td><td>226</td><td>0.0136</td></tr><tr><td>234</td><td>0.0042</td><td>237</td><td>0.0076</td></tr></table></body></html>

表416QAM调制方式下Eve与Bob 的误帧率

Table 4Frame error rate atBob and Eve in 16QAM modulation   

<html><body><table><tr><td>平均接收功率/uW</td><td>Bob 的误帧率(1)</td><td>平均接收功率/uW</td><td>Eve 的误帧率(1)</td></tr><tr><td>364</td><td>0.7496</td><td>347</td><td>0.8377</td></tr><tr><td>428</td><td>0.3513</td><td>419</td><td>0.5687</td></tr><tr><td>429</td><td>0.3655</td><td>435</td><td>0.4485</td></tr><tr><td>441</td><td>0.3110</td><td>452</td><td>0.4374</td></tr><tr><td>465</td><td>0.2132</td><td>457</td><td>0.3531</td></tr><tr><td>482</td><td>0.1357</td><td>492</td><td>0.2432</td></tr><tr><td>509</td><td>0.1132</td><td>506</td><td>0.1726</td></tr><tr><td>550</td><td>0.0423</td><td>543</td><td>0.1123</td></tr><tr><td>575</td><td>0.0203</td><td>556</td><td>0.0903</td></tr><tr><td>648</td><td>0.0086</td><td>633</td><td>0.0194</td></tr></table></body></html>

为了更加直观地体现噪声聚合方案的优势，图6展示了16QAM调制方式下，Alice发送图像与Eve、Bob在373uw平均接收功率大小时的接收图像。

![](images/56b0a03d4b945dba0ddba74f5bcc013aaeadb2b731074f9a67d2832870122bd6.jpg)  
图6Alice发送图像与Bob、Eve 接收图像 Fig.6Transmitted image at Alice,received images at Bob and Eve

可以看出，在同一平均接收功率条件下，同一信道质量条件下，Eve的接收图像受到严重污染，完全无法识别图像。但是Bob却能恢复出原始图像，实现了保密传输。

图像质量的客观评价与主观评价同样重要。通过计算图像的PSNR（peaksignaltonoiseratio，峰值信噪比）可以得出对图像客观的评价，其表现为图像间的相似程度。图像间PSNR值越小，则越失真。

由于Bob是可靠接收，所以只有Eve存在PSNR值。实验记录了在不同调制方式、不同平均接收功率条件下，Eve接收图像与原图相比的PSNR值，如表5所示。

由表5可以看出，在QPSK与16QAM调制方式下、不同平均接收功率条件下，Eve接收图像相比于原图的PSNR值均低于普遍基准即30dB。故可以认为Eve 的图像较Bob劣化明显，证实了噪声聚合方案的有效性。

表5Eve接收图像的峰值信噪比  
Table 5PSNR of received image at Eve   

<html><body><table><tr><td rowspan="2">平均接收功率/uW</td><td rowspan="2">QPSK 调制下 PSNR/dB</td><td rowspan="2">平均接收功率/uW</td><td rowspan="2">16QAM调制下 PSNR/dB</td></tr><tr><td></td></tr><tr><td>131</td><td>7.16</td><td>364</td><td>6.72</td></tr><tr><td>140</td><td>7.99</td><td>428</td><td>7.32</td></tr><tr><td>152</td><td>7.99</td><td>429</td><td>7.85</td></tr><tr><td>159</td><td>9.03</td><td>441</td><td>8.92</td></tr><tr><td>170</td><td>9.34</td><td>465</td><td>8.92</td></tr><tr><td>180</td><td>10.00</td><td>482</td><td>9.54</td></tr><tr><td>186</td><td>10.41</td><td>509</td><td>10.41</td></tr><tr><td>204</td><td>11.14</td><td>550</td><td>11.14</td></tr><tr><td>224</td><td>12.79</td><td>575</td><td>11.14</td></tr><tr><td>234</td><td>13.98</td><td>648</td><td>13.01</td></tr></table></body></html>

# 5 结束语

基于软件无线电平台，本文设计了融合噪声聚合抗窃听能力的发射机与接收机方案，并搭建了相应的抗窃听测试环境。以图像传输业务为例，用实测数据验证了噪声聚合物理层方案的保密性能。在现有理论分析及仿真评估的基础上，为噪声聚合方案的有效性提供了现实依据。另外，基于软件无线电的数字通信链路与帧结构设计对于后续完善以及其他物理层安全方案的原型实现提供了参考与借鉴。

# 参考文献：

[1]沈昌祥，张焕国，冯登国，等．信息安全综述[J]．中国科学：技术 科学,2007,37(2):129-150.(Shen Changxiang,Zhang Huanguo,Feng Dengguo,et al. Summary of information safety [J]. Scientia Sinica: Technologica,2007,37(2):129-150.)   
[2]Bloch M, Barros J.Physical-layer security: from information theory to security engineering [M].Cambridge:Cambridge University Press, 2011.   
[3]He Hongliang，Ren Pinyi.Secure ARQ protocol for wireless communications:performance analysis and packet coding design [J]. IEEE Trans on Vehicular Technology,2018,PP(99): 1-1.   
[4]He Hongliang,Ren Pinyi,Sun Li,et al. Secure communication using noisy feedback [C]//Proc of Global Communications Conference.IEEE, 2016: 1-6.   
[5]Xu Hongbin,Sun Li,Ren Pinyi,et al. Securing two-way cooperative systems with an untrusted relay:a constellation-rotation aided approach [J].IEEE Communications Letters,2015,19 (12): 2270-2273.   
[6]Xu Hongbin,Sun Li,Li Fan.Towards enhanced security for two-way untrusted relaying systems:a constellation overlapping scheme [C]// Proc of IEEE International Conference on Communications.IEEE, 2018: 1-7.   
[7]Ding Zhiguo,Ma Zheng,Fan Pingzhi．Asymptotic studies for the impactofantennaselectiononsecuretwo-wayrelaying communications with artificial noise [J]. IEEE Trans on Wireless Communications,2014,13(4): 2189-2203.   
[8]Hussain Mukhtar,Du Qinghe,Sun Li,et al. Security enhancement for video transmission via noise aggregation in immersive systems [J]. Multimedia Tools & Applications,2016,75(9):5345-5357.   
[9]Xu Qian,Ren Pinyi,Du Qinghe,et al. On achievable secrecy rate by noise aggregation over wireless fading channels [C]//Proc of IEEE International Conference on Communications.IEEE,2O16:1-6.   
[10]向新．软件无线电原理与技术[M]．西安：西安电子科技大学出版 社,2008.(Xiang Xin.Principle and technology of software radio [M]. Xi’an:Xidian University Press,2008.)   
[11]WynerAD.The wire-tap channel[J].BellLabs Technical Journal,1975, 54(8):1355-1387.   
[12]刘维穆，刘厚泉．无线局域网IEEE802.11n标准分析[J].信息通信， 2008,21(4):36-39.(Liu Weimu,Liu Houquan.Analysis of WLAN IEEE 802.1ln standard [J].Information & Communications,2008, 21(4): 36-39.)   
[13]Razabi B.Design Consideration for Direct-Conversion Receivers [J]. IEEE Trans.on Circuits Syst.ii,1997,44(6): 428-435.   
[14] Forney G.Maximum-likelihood sequence estimation of digital sequences in the presence of intersymbol interference [J].IEEE Trans on Information Theory,2003,18(3): 363-378.   
[15]王森．基于软件无线电的通信系统设计与实现[D]．西安：西安电 子科技大学，2O15.(Wang Sen．Design and implementation of communication system based on Software Radio [D].Xi’an:Xidian university,2015.)