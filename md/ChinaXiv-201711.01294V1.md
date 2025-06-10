# GuidetechGT668SLR-1事件计时器在卫星激光测距中的应用研究

皮晓宇¹，鞠青华¹，汤儒峰1,²，和丽娟¹，张海涛(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京 100049)

摘要：高重频卫星激光测距系统中，激光脉冲飞行时间通过事件计时器分别测量主波和回波时刻获得。为了采用更高重频且高精度的事件计时器，将Guidetech公司的GT668SLR-1事件计时器应用于中国科学院云南天文台的 $1 . 2 \mathrm { m }$ 望远镜激光测距系统，对其结构原理进行分析，并利用其测量由信号发生器产生的固定信号、地靶测距和卫星测距等试验，采集数据的处理结果达到激光测距精度要求，由此判定GT668SLR-1事件计时器可用做卫星激光测距系统的时间测量单元。

关键词：事件计时器；卫星激光测距；高重频；测距数据处理中图分类号：P111.3 文献标识码：A 文章编号：1672-7673(2017)04-0429-07

卫星激光测距(Satellite Laser Ranging，SLR)的原理是通过精确测定激光脉冲在地面观测站与激光测距卫星之间的往返时间间隔 $\Delta t$ ，从而算出地面观测站到卫星的距离 $r ^ { [ 1 ] }$ 。千赫兹激光测距技术是近几年发展起来的新的测距方式，它通过增加测距频率来增加观测数据，提高标准点精度[2]，观测数据量的增加，可以有效提高标准点的精度，利于卫星的精密定轨，是激光测距的发展方向之一。

在千赫兹测距中，采用时间间隔计数器测量激光脉冲在地面测站和卫星之间飞行时间的方法已经不适用，从而出现了事件计时器[3]。事件计时器将激光发射脉冲和回波脉冲视为事件并记录脉冲前沿到达的精确时刻，即主波时刻和回波时刻，二者之差即为激光脉冲飞行时间。自从千赫兹测距系统对事件计时器提出需求后，很多公司或大学开始研制事件计时器，有PET4（Dassualt）、A032-ET（Latvia)和AO33-ET(Latvia)等，价格从几十万美元降至几万美元，促进了全球千赫兹激光测距系统的快速发展。云南天文台 $1 . 2 \mathrm { m }$ 望远镜千赫兹激光测距系统4采用A033-ET，该仪器有测量精度高、时间抖动小等优点，但其最高工作频率只有 $1 2 \mathrm { k H z }$ 。因此，为了适应更高频率的事件测量，研究团组使用由Guidetech 公司提供的GT668SLR-1事件计时器测试板进行了测试试验。

# GT668SLR-1事件计时器

由 Guidetech 公司生产的GT668SLR-1（以下简称 GT668）是基于新型时间间隔分析仪（Time IntervalAnalyzer，TIA）系统的事件计时器，主要由GT668SLR系列电路板、PCIe/PXIe 机箱与控制软件组成。输入为1PPS(Pulse Per Second)信号，具有多路可编程触发的输出端口，可以与UTC 时间进行同步设置，软件可以与外联卫星激光测距软件进行通信设置编程。

事件计时器主要应用于卫星激光测距的时间测量与记录，集成于内部的时间间隔分析仪记录输入信号事件发生的时刻。此处事件定义为信号的电压从正方向或负方向跨越设定阈值到另一侧的电信号脉冲变化情况。脉冲的时间点标签以及脉冲的统计编号被记录至事件计时器的存储器。

相较于之前使用的A033-ET型事件计时器，GT668具有更高的时间分辨精度，单发时间分辨率可达到约$0 . 9 \mathrm { p s }$ ，死时间方面有了极大改善。采样率达到 $4 \ : \mathrm { M / s }$ ，而测试板配合通信机箱的结构使得整体上有了极大的提升空间，按用户需求可以支持2\~34通道的输入输出。表1为GT668与A033-ET的性能对比，图1为一块单通道的GT668测试板，集成至机箱后整体外观以及测试环境如图2。

表1GT668 和A033-ET 性能对照表Table1PerformanceofGT668and Ao33-ET  

<html><body><table><tr><td>计时器型号</td><td>A033-ET</td><td>GT668</td></tr><tr><td>单发精度</td><td><5 ps</td><td>~0.9 ps</td></tr><tr><td>死时间</td><td>50ns</td><td>~0</td></tr><tr><td>测量频率</td><td>12 kHz</td><td>2.9 GHz</td></tr></table></body></html>

![](images/5e8efd8fe21be03655894e81bd895ef7072b2dd6136c17e793055fca9b646fd1.jpg)  
图1GT668 测试板Fig.1GT668 test board

![](images/e758e19cfe7a6bcb450b511c62005f83094f48768df5369109f86e33a23f0af9.jpg)  
图2 GT668整体外观 Fig. 2 GT668 global view

# 2仪器结构与工作流程

# 2.1事件计时器结构

GT668SLR-1型事件计时器测试板主要模块结构如图3，测量模块与时钟模块保持同步，输入信号在进入输入模块进行信号预处理后送到测量逻辑进行时间间隔的测量，控制逻辑对上述模块进行控制，并将测量输出处理后送至PC端接口。

用户输入为探测器测量得到的脉冲信号[5]送到输入模块。输人模块首先进行滤波，然后通过模数转换进入预分频器，输人信号经预分频后

![](images/d1b6699bf516a0b47f0351de5794e309a308b3c33fd40132e31b82692eab998c.jpg)  
图3GT668SLR-1型事件计时器测试板结构Fig.3GT668SLR-1 event timer structure

分别对应用户选择通道[6]。通道的分配通过在PC 端配置 ARM指令并在硬件上由数据选择器实现。

测量逻辑主体为时间间隔分析仪配合ARM模块完成。其中，ARM主要负责时间同步与测量分配，时间间隔分析仪为主要测量模块，通过利用延迟单元造成两输入信号间延迟量的变化来统计延迟单元数量，从而计算信号间精确的延迟量。

时钟模块主要由ARM组成，负责将测量时钟信号与输入的作为参照信号的实时协调世界时或1PPS进行同步，同时也可通过利用外接时钟自我校准。该模块使用的关键点在于外接参考时钟的准确度，它决定了整个计时器系统的测量精度。

控制逻辑通过由ARM发出指令进行寄存器读写来对以上模块进行控制。测量逻辑的输出信号在控制逻辑端进行处理后，根据用户指令发送到PC 端。

整个事件计时器模块主要由ARM构成，对输入信号的上升沿敏感，输入端信号线采用 SMA格式，PC 端为内嵌的WINDOWS系统。

# 2.2 测量流程

为保证测量时间与UTC时间保持一致，需要将来自外接全球定位系统时钟的参考时钟信号引入仪器。采用的外部时钟与仪器采样使用的内部时钟信号存在偏差，为此，程序需要首先进行同步。同步程序从PC端发送指令至时钟模块的 Block_ARM上执行，将来自全球定位系统时钟的CLK 时钟信号和1pps信号，与来自仪器内部的CLK时钟信号进行同步。在此基础上，开始数据的采集和测量。

测量主要在测量逻辑中进行，输入信号类型为脉冲信号，有两组输入，分别为 $A$ 通道的 start信号即发射信号，与 $B$ 通道的 stop信号即回波信号。以发射信号的上升沿为开始测量的标志，接收到回波信号上升沿时测量停止。开始信号与停止信号间的时间间隔由时间间隔分析仪测量，测量输出需经软件解码，然后依次写入存储单元。输出文件格式为“编号 $^ +$ 时间点”，为纯数据文本，第1列事件编号为在PC 端点击出光且开始采数后激光发射的脉冲计数，该列可在输出配置中选择为不显示;第2列为事件时间点，以开始采数的信号作为0点基准。输出配置中可将两个输入通道的事件时间点在一个文件中显示，以一行开始信号一行结束信号依次排列；或将 $A$ 通道事件时间与 $B$ 通道事件时间分别显示在不同文件中。

# 3 测试试验

测试试验的主要目的在于验证设备对卫星激光测距工作的适用性，测试的关键点是测试在各种应用环境下测量所采集的数据精度是否达到所需的数据精度要求[7-8]。据此原则，依次开展了固定信号测量、地靶测距与卫星测距，从功能配置、性能等不同侧重点对仪器进行了测试试验。

采集的数据需经过一系列运算，才能确定该数据是否达到精度要求[7]。数据精度指数据的标准偏差，精度从统计点直方图上最直观的表现为非噪声数据点的集中程度，采集的点在时间轴上形成一条线，线的宽窄程度一定程度上可以反映后期处理得出的精确程度，但具体精度仍需要数据处理后才能得出。

# 3.1 固定信号测量

初步的地面信号试验目的侧重于确保实验仪器的可用性与功能测试，主要测试了仪器的基本功能，以及仪器对输入信号的敏感程度。试验侧重于测试仪器的最大采样率。

通过由实验室内信号发生器模拟类似于卫星测量信号，送至事件计时器进行数据采集。试验仪器连接如图2，通过信号发生器产生信号，利用示波器将信号调整至合理范围后接入事件计时器，在PC端接收测试板的输出数据。

仪器设置中设置输入触发方式为正向上升沿触发，输出文件格式为事件时刻点数据。输入电压由外接信号源产生，电压范围为 $0 \sim 5 \mathrm { ~ V ~ }$ 的正向脉冲TTL信号，信号波形为连续脉冲，输入信号频率在MHz级别。输入信号分别接入 $A$ 或$B$ 通道，在测试板自带的系统平台上进行了数据测量采集，采集的数据结果如图4。

图4为测量采集到的数据结果，采样点数为250000个，均方根为 $7 9 2 . 0 ~ \mathrm { n s }$ 。初步的地面试验为测试板的功能测试试验，MHz级别的高频率的输入能够被仪器顺利采集。测试板的基本功能得以验证。相对于A033-ET型，采样率有了大幅提升，而高采样率的有效利用将是系统集成中的一个关注点。

![](images/40b60e0be489ba1e9749b954a748ce45ff726a52b2efc417644bd6986a516fe2.jpg)  
图4固定信号测量处理结果 Fig.4Stable signal sampling and processing result

# 3.2 地靶测距

地靶测距是通过发射激光到固定距离外的地面目标，接收回波信号，通过测量发射、回波信号间的时间差计算发射源与地靶间的距离[9。输入信号来自通常卫星激光测距的经输出处理的探测器输出，时间同步信号来自全球定位系统时钟，除了瞄准目标为地靶之外，电路系统配置与通常卫星激光测距使用的配置相同。地靶测距的精度要求为 $5 \mathrm { m m } ^ { [ 7 ] }$ 。

地靶实验中，数据采集程序重新进行了编写，加入了时间同步的功能，即首先进行时间同步，再进行数据采集。

如图5为地靶数据的测量结果图像化显示的O-C 图，数据经处理后可以达到地靶测量精度即 $5 \mathrm { m m }$ 内，数据处理后精度达到A033-ET型仪器的水平。

![](images/1b96178347f4ac019506fe560fcd5ec013a7027ae123771a2038b445811cb3ab.jpg)  
图5地靶测量采集数据O-C图

# 3.3 卫星测距

卫星测距为该仪器测试的最主要阶段，其间对在轨的lageos、ajisai 等卫星目标进行了测量。卫星测距的精度要求，对于lageos 为 $1 . 5 \mathrm { c m }$ ，对于其他目标为 $2 \mathrm { c m } ^ { [ 7 ] }$ 。

仪器接人卫星测距系统中[9]，输入信号来自探测器输出电路，时间同步信号来自全球定位系统时钟。如图6为卫星lageos 的测量数据结果，数据经处理后，精度达到 $1 . 5 \mathrm { c m }$ 内，满足实用需求。

![](images/1dc031979f1e45f4ca420999c66001a47918b717784c919540f20d94309af39b.jpg)  
Fig.5O-C result of ground target sampling data   
图6 SLR-lageos 测距采集数据 Fig.6Ranging sampling data of SLR-lageos

如图7为卫星ajisai的测量数据结果，处理后的数据精度达到 $2 \mathrm { c m }$ 内，满足实验规定需求。

![](images/831002bf29535a8c3af87bf480d654c37a9109f44aec528450944a860e7b45cc.jpg)  
图7SLR-ajisai 测距采集数据O-C图 Fig.7Ranging sampling data of SLR-ajisai

如图8为卫星beaconc 的测量数据结果，处理后的数据精度达到 $2 \mathrm { c m }$ 内，满足实验规定要求。

![](images/4d446cebb06aba3882eaf2e2a2876f080c503a800ed950611c812a094c48a757.jpg)  
图8SLR-beaconc 测距采集数据O-C图 Fig.8O-C result of SLR-beaconc ranging

如图9为卫星beaconc 的测量数据结果，处理后的数据精度达到实验规定要求的 $2 \mathrm { c m }$ 内。

![](images/f5be96682e36d0561a0ebac0bfcc68bb0925668e37a61806f52fdd2406d98338.jpg)  
图9SLR-compassi5 测距采集数据O-C图 Fig.9O-C result of SLR-compassi5 ranging

# 4总结

本文描述了对GT668SLR-1型测试板进行卫星激光测距试验测量数据采集的一系列试验，测试板以ARM为主要模块，方便了软件程序的编写，而通过PXI集成在NI机箱上的设计具有灵活的可扩展性，对于今后多通道事件计时器的应用有很大的帮助。对测试板的结构及工作原理等进行了分析说明，并开展了固定信号测量试验、地靶试验及卫星测距试验，验证了测试板的主要功能及其在卫星测距工作中的适用性。采集的数据精度符合卫星激光测距的要求，可以投入卫星激光测距工作中作用。

# 参考文献：

[1] 叶叔华，黄城.天文地球动力学［M].济南：山东科学技术出版社，2000：91-118.  
[2] 李欣，王培源，邹彤，等.kHz激光器在武汉卫星观测站的测距实验［J].强激光与粒子束，2011，23(2)：367-370.Li Xin，Wang Peiyuan，Zhou Tong，et al. Expriment on kHz laser ranging at Wuhan satellitelaser ranging station [J]. High Power Laser and Particle Beams，2011,23(2）:367-370.  
[3] 李祝莲，熊耀恒.云南天文台卫星激光测距中的测时仪器［J］．天文研究与技术—国家天文台台刊，2008，5(2)：161-166.Li Zhulian，Xiong Yaoheng. Timing device used in Kunming satellite laser ranging station [J].Astronomical Research & Technology———Publications of National Astronomical Observatories ofChina，2008，5(2):161-166.  
[4] 李祝莲，熊耀恒，何妙婵，等.云南天文台人造卫星激光测距系统原理［J].天文研究与技术——国家天文台台刊，2008，5(3)：248-252.Li Zhulian，Xiong Yaoheng，He Miaochan，et al.Principle of $1 . 2 \mathrm { m }$ telescope satellite laserranging system [J].Astronomical Research & Technology———Publications of National AstronomicalObservatories of China，2008，5(3）:248-252.  
[5] 李祝莲，何少辉，伏红林，等.激光测月回波探测器位置控制系统设计［J].激光与光电子学进展，2012，49(5)：88-91.Li Zhulian，He Shaohui,Fu Honglin，et al.Position control system design of return laser pulsedetector for lunar laser ranging [J]. Laser & Optoelectronics Progress，2012，49(5）: 88-91.  
[6] 樊昌信.通信原理教程［M].北京：电子工业出版社，2007：71-82.  
[7] 李熙，汤儒峰，李祝莲，等.基于二值图像的卫星激光测距数据处理［J]．中国激光，2014,41(12) : 182-189.Li Xi，Tang Rufeng,Li Zhulian，et al. Laser ranging data processing based on the analysis of thebinary image [J]. Chinese Journal of Lasers，2014，41(12）：182-189.  
[8] 房庆海，赵永丽.卫星激光测距数据处理算法的研究进展［J]．激光技术，2008，32（4)：417-419.Fang Qinghai，Zhao Yongli. The research progress in data processing algorithm of satellite laserranging ［J]. Laser Technology，2008，32(4）: 417-419.  
[9] 黄涛，李祝莲，张海涛，等. $5 3 \ \mathrm { c m }$ 双筒激光测距望远镜控制系统的设计与实现［J].现代电子技术，2014，37(16)：1-7.Huang Tao,Li Zhulian，Zhang Haitao,et al. Design and implementation for control system of $5 3 ~ \mathrm { c m }$ binocular laser ranging telescope [J]. Modern Electronics Technique，2014，37(16） : 1-7.

# Application of GT668SLR-1 Event Timer in Satellite Laser Ranging

Pi Xiaoyu'，Ju Qinghua'，Tang Rufeng1,²，He Lijuan'，Zhang Haitao1 (1.Yunnan Observatories，Chinese Academy of Sciences,Kunming 65ool1,China,Email；pixiaoyu@ynao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China)

Abstract:In high-frequency satelite laser ranging（SLR）system，the flight time of laser pulse is acquired by an event timer（ET）which measures the event epochs of laser transmiting and photon receiving. In orderto put an ETwith higher frequency and precision into good use,the GT668SLR-1 type from Guidetech is introduced into the $1 . 2 \mathrm { m }$ telescope SLR system during our system upgrading，its principle and structure are analyzed.By means of measuring fixed signals from signal generator，ground target measurement and satelite laser ranging，the new event timer is tested for the SLR system，and the processng results of sampled data meet the demand of ranging standards.Therefore，it is concluded thatthe GT668SLR-1 type is capable to be integrated as the time measuring unit for the SLR system.

Key words: Event timer; Satellite laser ranging；High repetition rate； Ranging data processing