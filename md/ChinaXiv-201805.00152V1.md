# 基于STM32的可调恒温滤光片转轮盒的设计

徐艺灵，张鸿飞，姜逢欣，陈金挺，陈亚奇，贾明皓，董书成，陈杰，杨臣威，王坚  
（中国科学技术大学近代物理系，核探测与核电子学国家重点实验室，安徽 合肥 230026)

摘要：为了满足1.2m望远镜天文成像系统对科学目标的观测，设计了一个基于STM32控制的可调恒温滤光片转轮盒。转轮盒内有三个转轮，在各自电机驱动下可配合转动，实现最多15个滤光片的自动切换。为确保滤光片的稳定工作波长，转轮盒内置基于PID温控算法的保温系统，以保持转轮盒内部在设定温度。上位机可通过串口与电控盒进行指令通信，并由电控盒直接驱动转轮电机及加热保温。整个系统结构紧凑，电控安全性好，单片机程序功能完备。最后测试证明该转轮盒在低温 $- 2 5 ^ { \circ } C$ 时能正常工作，在恒温模式下能使温度保持在目标温度±1℃以内，长时间工作时性能稳定，切换一次滤光片的用时在10s以内。

关键词：滤光片切换； STM32；温控算法； 电机驱动中图分类号：TP232 文献标识码：A文章编号：1672-7673（2018）03

超大质量黑洞的吸积过程及其与寄主星系的共同演化是黑洞物理和星系行程与演化的基本问题。活动星系核是超大质量黑洞高速增长的阶段，其观测特征为高光度、多波段的连续谱辐射及较强的发射线。连续谱和发射线均存在不同程度光变，且光学-紫外波段主要宽发射线光变受到连续谱光变激发。通过测量活动星系核宽发射线对连续谱光变的响应时延能测量出谱线发射区气体到中心黑洞的距离（反响映射测量），结合光谱测量获得的谱线速度展宽，可以估计中心黑洞质量。传统反响映射测量主要依靠光谱测量长期监测活动星系核目标，由于光谱仪效率限制，需要大口径望远镜，且耗时长，定标精度低杨臣威恒星潮汐撕裂事件与类星体吸收线光变[D]．合肥：中国科学技术大学，2015。为了实现高效率高精度反响映射测量，中国科学技术大学研制了1.2m望远镜天文成像系统。主要利用宽窄带滤光片多波段测光来监测活动星系核连续谱和发射线光变。计划将反响映射样本数目增加4

，并大幅增加高光度、高红移活动星系核目标以改善样本的参数空间覆盖。为了实现该科学目标，需要长时间（几个月到数年）监测一批活动星系核，要求整体测光精度优于 $1 \%$ ，因此对滤光片提出了相当高的要求，特别是系统所用的窄带滤波片中心波长随温度漂移。

1.2m望远镜天文成像系统的结构和光路图如图1。这是一个红/蓝二通道成像系统，望远镜入射光焦比 $\epsilon / 8 . 4 2 9$ ，光束通过准直系统变为平行光束，由分光器分为红/蓝两端光束。其中红端为透射，波长范围为650nm\~1000nm，蓝端为反射，波长为 $4 0 0 \mathsf { n m } \widetilde { \mathbf { \Omega } } 6 5 0 \mathsf { n m }$ 。之后光束通过滤光片系统，每个通道最多需要更换14片滤光片，窄带滤光片带宽范围为 $8 ^ { \sim } 1 7 \mathrm { n m }$ 。平行光束经过滤光片系统滤光后进入成像系统，焦比变为 $+ / 5$ ，之后通过相机成像。

![](images/7e435414f022a28fc587cdabecc9ec336e260c0c7a8e8638e1939dadb0a4b1f7.jpg)  
图 $1 1 . 2 \mathrm { m }$ 量子望远镜双通道成像仪 Fig.1 The astronomical imaging system of $1 . 2 \mathrm { m }$ telescope

系统中所用的窄带滤光片由于带宽小，中心波长和带宽对温度响应灵敏。抽取一组用自行搭建的滤光片性能检测系统对其做了性能标定，观察了其带宽和中心波长的温漂。如图2，在 $\boldsymbol { 1 0 ^ { \sim } 2 3 ^ { \circ } C }$ 温度范围内，中心波长的漂移可以基本忽略，而温度越低带宽越大，在 $\triangle 1 3 ^ { \circ } \mathrm { C }$ 测试范围内带宽变化约为 $0 . 0 3 \mathsf { n m }$ ，占全带宽约 $0 . 2 \%$ 。一般天文台所在的高海拔地区，环境温度变化大，周年典型夜间温差可达 $4 0 ^ { \circ } \mathsf { C }$ ，冬季昼夜温差约 $1 5 ^ { \sim } 2 0 ^ { \circ } C$ 。按环境周年夜间温差跨度 $4 0 ^ { \circ } \mathsf { C }$ 估算，带宽变化将达到 $0 . 6 \%$ 。所以有效的温控对高精度窄带测光至关重要。除了温控以外，对于某些科学观测目标需要同时或准同时多波段测光检测，能快速实时切换滤光片对科学目标的实现也十分重要。

![](images/876165d034aa39567352e40e2551d84d6794cdcf30be8af470583267147f5316.jpg)  
图2窄带滤光片中心波长（a）和带宽（b）随温度的漂移Fig.2 The thermal drift of the central wavelength(a)and the bandwidth(b) of the narrow band filter  
图3滤光片转轮盒系统框图 Fig.3The diagramof the system of filter wheel box

针对以上需求，本文设计了一个基于STM32电控的可调恒温多轮式滤光片转轮盒系统[2-4]，在保证滤光片温度的同时，能快速稳定地在14个滤光片中切换。该系统也同样适用于其它需要快速切换及温控的光学系统。

# 1系统结构

望远镜成像系统中红蓝两通道的滤光片转轮架构一样，如图3，由3部分组成：转轮盒、电控盒和上位机。转轮盒的电机和加热片由电控盒提供驱动，且转轮盒实时给电控盒位置和温度反馈信号；电控盒由主控板和电机驱动板组成，直接对接转轮盒，并通过串口接收、应答上位机命令。

转轮盒的机械结构[5如图4，转轮盒内有3个滤光片转轮，由各自独立控制的步进电机驱动。每个转轮有6个通光孔，通过放置滤光片盒子，最多可以安装5个滤光片，剩下1个空的通光孔。当某个转轮上的某个滤光片需要放在光路中时，另外两个转轮将空通光口与光路准直，即只有一个滤光片在光路上。每个通光孔附近都有位置感应片，有滤光片的通光孔附近安装一个感应片，空通光孔附近安装两个感应片与其他区别开作为HOME位。感应片与转轮盒外壳上的位置传感器配合可以获得转轮的当前位置通过接口反馈给电控盒。电机控制由电控盒内电机驱动板和控制板完成。转轮盒内壁覆有加热片和温度传感器，通过外部接口与电控盒内相应模块组成温控系统。

![](images/aebc3c9e030c2304ae572c385ffd61bafbb306468d6594f35decb50bf9d25377.jpg)  
图4转轮盒结构示意图Fig.4 The sketch of the wheel box  
图5控制电路结构图Fig.5 The diagram of the control circuit

电控盒作为底层硬件控制模块，由电机驱动板和单片机主控制板组成，安装在一个小巧的匣子里，并通过串口接收上位机命令和上传反馈信息。

使用人员通过上位机软件，可对电控盒指令设置使用的滤光片、启停温度控制、获取实时温度和转轮位置信息，并确认温控和转轮就位。在调试模式时还可设置目标温度、单独设置每个转轮的转动和复位、设置温控运行参数、控制转轮电机步级角、校准滤光片位置和设置转轮孔位和滤光片波段的映射等。

# 2控制电路

滤光片转轮的控制电路结构如图5，由主控制板和电机驱动板组成，二者一起放在一个电控盒内，只露出对外的传感接口、控制接口、通信接口以及电源接口。电控盒负责与上位机的通信，并实现对滤光片转轮盒电机和温控的底层控制、数据采集。其中主控板承担了温控功能和产生电机控制信号功能，电机驱动板作为电机控制模块的一环，将电机控制信号转化为直接驱动电机的二相电流。

主控制板是电控模块的核心，它根据上位机命令具体实现转轮电机控制和滤光片保温控制。它包括了主控芯片STM32，串口通讯模块，温控模块，电机控制模块。主控单片机STM32是一款基于Cortex-M3内核的32bit微控制器，具有足够通用IO和片上USART串口收发器、SPI接口等。

在电机控制模块中，主控板对驱动板的控制信号经过了三极管的电平转换；位置传感信号由转轮盒上的电感式接近传感器接入，用光耦合器作电平转换和防护隔离再输入到STM32。

温控模块包括温度采集和M0SFET驱动输出。本文选用了一款24bit的高精度ADC测试温度，自带电流源，用四线制测量方法抵消引线电阻对RTD（热电阻）测量精度的影响；对加热片的控制依次经过一级数字隔离和驱动芯片后，通过一个P沟道功率型MOSFET给转轮盒内壁的加热片提供PWM电流。

转轮的精确转动需要步进电机驱动，从最大同步转矩、保持转矩、最小步距角、价格等方面考虑，本文选用东方马达CMK243MAP型号2相步进电机组合，基本步级角为 $0 . 9 ^ { \circ }$ 。电机本身配有驱动板，但在系统中每个转轮盒需要3个电机，如果每个电机配一个驱动板无疑会体积过大，使电控结构冗余。所以本文将3个电机驱动集成设计到一块驱动板上，负责把控制板输出的3路电机控制信号转化成3路直接驱动电机的二相信号，并方便地和控制板安装在一个盒子里。

驱动板工作电源包括24V和3.3V，其中24V由主控板提供，3.3V由24V经过LDO产生。来自主控板的控制信号经过光耦合器电气隔离再输入电机驱动芯片上，提高了接口的安全性。电机驱动选用的DRV8825是一款双极步进电机驱动芯片，最大输出2.5A电流，实际使用时只需0.6A就可带动转轮电机；具有片上微步进分度器，最大可配置成32细分，这样电机的运转分辨率可达12800步/圈，提高滤光片切换的精度。

整个电控设计非常注重电气隔离和安全性，通过光耦合器和数字隔离芯片等使大功率用电模块或高电平模块与低压主控电路绝缘，以防止外部短路导致主芯片损坏；在保证功能的前提下设计紧凑，体积小巧，每个转轮盒配一个电控盒，可以方便地安装拆卸。经过后续实验证明电控模块能稳定可靠地实现既定功能。

# 3 STM32固件程序设计

电机控制信号和加热片控制信号的产生以及对上位机命令的解析由STM32单片机完成，固化在单片机内程序的结构如图6，包括初始化模块、命令解析模块、状态查询模块、ADS1248测温模块、PWM加热片控制模块、电机控制模块、位置传感器模块、参数修改和读取模块、串口通信模块等。

每次上电后，单片机先执行一系列初始化，包括系统时钟、通用I0、串口、中断、电机控制定时器、加热片驱动定时器、温度采样ADC的配置以及电机和加热片初始状态设定等。单片机通过串口接收命令，通过命令解析模块处理并触发其它功能块执行。命令的基本格式是：“>+命令字（+空格 $^ +$ 参数） $^ +$ #“,其中>是命令起始字符，命令解析模块接到该字符才认定接下来的命令字有效，#是命令结束符，表示该条命令结束，可进入等待下一条命令的进程。主要命令如表1，命令涵盖了系统对用户开放的基本功能。

<html><body><table><tr><td colspan="2">命令字</td><td>功能</td></tr><tr><td>通用 >ECHO#</td><td></td><td>测试下位机及串口</td></tr><tr><td rowspan="5">转轮控 制命令</td><td>>HOME [参数]#</td><td>复位指定编号的转轮</td></tr><tr><td>>SFLT［参数]#</td><td>设置目标滤光片</td></tr><tr><td>>RFP#</td><td>读取每个转轮的当前位置</td></tr><tr><td>>STOP#</td><td>使转轮从停止转动</td></tr><tr><td>>GFLT#</td><td>读取目标滤光片</td></tr><tr><td rowspan="4">加热控 制命令</td><td>>SPWM[参数]#</td><td>启停加热片驱动</td></tr><tr><td>>STT[参数]#</td><td>设置目标加热温度</td></tr><tr><td>>GCT#</td><td>读取当前温度</td></tr><tr><td>>GTAM#</td><td>读取加热状态</td></tr></table></body></html>

转轮电机控制流程见图7。转轮盒内3个转轮共15个可放置滤光片的孔位被标记为1\~15号，当收到指令要切换到某号滤光片时，程序会判断每个转轮分别要转到的孔位。假设命令要求转到8号滤光片时，程序会控制第1、3个转轮转到空孔位，第2个转轮转到第3个滤光片孔位。如果是上电后第1次操作，会先驱动电机将每个转轮转到HOME位复位，然后再转到目标位置，否则转轮会以当前为起点转到目标位置。每个滤光片位置都有位置感应片，每个感应片触发传感器都会触发中断，程序在当前位置寄存器上 $^ { + 1 }$ ，直到目标滤光片触发。由于感应片在传感器附近一段范围会造成触发，为了精确定位滤光片，需要在触发位置基础上再驱动电机运转一小段作偏移量修正，所以文本对每个滤光片位置都通过实验校准了这一修正量。到达目标滤光片位置后，程序将停止电机运转，并更新系统状态。

电机运转遵循如图8的S型加速曲线，这是一个加速度逐渐增大再逐渐减小的过程，目的防止电机突然启动或停止造成的失步。程序控制电机每5ms加速一次，从启动到匀速运转总共需要 $5 0 0 m s$ ，对应的PWM脉冲频率是1.5kHz增加到稳定的25kHz，占空比一直保持为 $5 0 \%$ 。

温控部分流程如图9，采用了PID算法（比例-积分-微分控制）[6-8]，这是一种常见的反馈控制算法。当单片机收到命令设定目标加热温度时，每个系统周期轮询到温控模块，都会进入PID控制函数，计算：当前温度与目标温度的温差 $\boldsymbol { \mathscr { e } }$ ，温度积分量 $i e { = } i e 0 { + } e$ ，温差微分量（变化量） $d e { = } e { - } e 0$ ，其中 $_ { i e 0 }$ 和 $e 0$ 分别为上一时刻的积分量和温差。计算 $P$ 值：

$$
P = ~ k p ^ { * } e ~ + ~ k ~  \substack { i ^ { * } i e } ~ + ~ k o ^ { * } d e
$$

然后判断是否有 $p \rangle$ MAX_duty_cycle或 $p { < } 0$ ，如果是则输出占空比对应上限/下限，否则占空比为 $p$ 。实际设置MAX_duty_cycle为 $8 5 \%$ 。为了使加热片的温度平稳上升并能在目标温度稳定，需要调整3个比例参数 $k { \mathfrak { p } } , k { \mathfrak { i } } , k { \mathfrak { d } }$ ，其中， $k \rho$ 是输出与输入误差的比例系数，决定了上升速度快慢； $k \mathrm { i }$ 是输出与输入误差积分的比例系数，随着时间积累会放大误差量，决定达到目标温度后的震荡程度；kd是输出与误差变化率的比例系数，具有抑制误差的作用。实际温控中前两项占据主导，经过实验确定出本系统的系数 $k _ { p } = 1 0$ ， $k \mathrm { i } { = } 0 . 0 2$ ，可保证加热速度的同时，尽量减小达到目标温度后的过冲和震荡。程序每秒调整一次PWM脉冲占空比为 $p$ ，达到持续控制实际加热片功率输出的目的。该过程持续到温度稳定在目标温度土 $2 ^ { \circ } \mathsf { C }$ 达到100s以上，此时更新系统状态为温度稳定。

整个程序借助STM32的固件函数库，可以轻松应用单片机外设，较快搭建一个应用工程。设计完成后使用KeilμVision5开发平台编译，通过STLINK固化到STM32中。

# 5测试结果

完成设计后，对滤光片转轮盒性能进行了测试，图10为转轮盒实验中的实拍图。在单次滤光片切换功能正常的基础上，本文用脚本持续 $2 4 \ h$ 对电控盒发送随机切换滤光片的命令，发现系统工作稳定性良好：单个转轮匀速转动一个孔位的时间间隔约为1.4s；若3个转轮的目标位置与当前位置都为所容许的最远距离5个孔位，则自动切换时间最长，约为10s。

![](images/33ff3f8f9996f89cd65869a2002cb2c1f61f9b8ae19b1632bf71fae2085850e3.jpg)  
图10滤光片转轮盒实拍图 Fig.10 The picture of the filter wheel box

另外，将滤光片转轮用保温棉包好后放入冰箱，模拟实际低温环境，冰箱温度设为 $\angle 2 5 ^ { \circ } C$ ，目标温度设为 $2 0 ^ { \circ } \mathsf { C }$ ，测试发现转轮盒加热片经过大约2.5h可达到目标温度。加热曲线见图11，可见在PID算法控制下，前期加热片驱动PWM一直以最大占空比 $8 5 \%$ 输出，功率最大；当温度逐渐接近目标，先是比例控制项 $k { \mathsf { p } } ^ { * } e$ 占据主导，占空比随着温差 $\boldsymbol { \mathscr { e } }$ 减小而线性减小，随之该项与积分控制项 $k \mathrm { i } * j _ { e }$ 之比变小，积分控制项占据主导，输出功率刚好能维持当前温度，没有震荡产生。如图12是温控在室温下达到稳定之后，滤光片转轮盒腔体内两个PT100 温度传感器返回的一组温度随时间变化。由于需要PT100测量的是腔内空气温度，而非紧贴加热片的温度，PT100 对加热片功率变化的响应有一定迟滞所以控温稳定程度受到限制。实测温度波动幅度稳定在±1℃以内，稳定度已经足够满足要求。

![](images/a59f8a8c4037bf8a810934efa3d18d4c7fa73b4ba0af9f67221a48b200507240.jpg)  
图11转轮盒加热过程温度变化及加热驱动PWM占空比 Fig.11 The temperature and the duty ratio of driving PWM during the process of heating of the wheel box

![](images/ae6e8b722d7bb8efc3673a77495c16dd80ef4fcec074b3a6d73f23ae62dfadbb.jpg)  
图12达到温控目标后转轮盒内部温度随时间变化曲线 Fig.l2The curve of the temperature change in thewheel box after it reached the target temperature

5总结

本文设计了一个结构紧凑的恒温滤光片转轮盒系统，转轮盒内部最多可放置15个滤光片，由基于STM32单片机的控制系统实现电机驱动、温控、状态查询等功能。在一系列测试中证明了系统性能良好，目前已在德令哈天文观测站的1.2m望远镜系统中稳定运行。该设计对其它需要滤光片切换的光学系统也有一定借鉴作用。

# The design of a programmable thermostatic filter wheel box based on STM32

Xu Yiling, Zhang Hongfei, Jiang Fengxin, Chen Jinting, Chen Yaqi, Jia Minghao, Dong Shucheng, Chen Jie, Yang Chenwei, Wang Jian (Department of Modern Physics，University of Science and Technology of China, State Key Laboratory of Nuclear Detection and Nuclear Electronics，Hefei Anhui，230026)

Abstract: In order to satisfy the observation of the astronomical imaging system of $1 . 2 \mathrm { m }$ telescope, a programmable thermostatic filter wheel box based on an STM32 MCU is introduced. The box has three wheels, which can be driven by their respective motor, and 15 optical filters can be switched at most. In order to avoid wavelength drift of the filters,a heat preservation system driven by PID temperature control algorithm is designed to keep temperature stable inside the box.A computer can communicate through serial port with an electronic control box, which is responsible for direct driving for the wheel motor and the heating. In summary, the system is compact-sized with secure electronic control circuit， and fully functioning MCU software. At the end of this paper, results of test show that when it is in the constant temperature mode, the wheel box works well below $- 2 5 ^ { \circ } C$ keeping the temperature inside within $\pm 1 ^ { \circ } \mathrm { C }$ around set temperature,and it costs 1Os at most to switch filter once .

Key words: Filter switching; STM32; Temperature control; Motor driving

参考文献：

[1］杨臣威.恒星潮汐撕裂事件与类星体吸收线光变[D].合肥：中国科学技术大学，2015.

[2]和寿圣,范玉峰,王传军.基于ASCOM标准的CCD自动观测系统[J].天文研究与技术—国家天文台台刊,2013,10(4):386-391.

He Shousheng, Fan Yufeng, Wang Chuanjun. An automatic CCD observation   
system based on the ASCOM standard[J]. Astronomical Research & Technology  
Publications of National Astronomical Observatories of China, 2013,10(4):386-391.   
[3] 陈永彦,马林,刘明博,等.一种X射线荧光分析仪滤光片切换系统的设计[J]. 分析仪器,2014(5):32-35. Chen Yongyan,Ma Lin, Liu Mingbo, et al. Design of an X-ray filter replacing system in X-ray fluorescence spectroscopy[J]. Analytical Instrumentation, 2004 (5): 32-35.   
[4]张海峰,庞其昌,刘浩,等.基于AT89C2051的滤光片自动切换系统[J].光电子 技术,2005,25(3): $2 0 1 - 2 0 3 + 2 1 0$ Zhang Haifeng, Pang Qichang,Liu Hao,et al. The auto switch system of ray filter based on AT89C2051[J]. Optoelectornic Technology, 2005, 25(3): 201-203+210.   
[5]王坚，陈杰，张鸿飞，等．一种可调恒温滤光片切换装置：中国， 201510971973.4 [P]. 2016-05-18. [6] Dong Shucheng, Jiang Fengxin, Chen Jie, et al. Fuzzy-PID based heating control system[C]// Real Time Conference. 2016.   
[7]艾力·玉苏甫,李永江,孙增武,等.基于模糊 PID控制的激光定位自动换馈控制 系统[J].天文研究与技术一国家天文台台刊,2013,10(2):162-170. Aili Yusup, Li Yongjiang, Sun Zengwu, Guo Shaoguang. An automatic control system for changing feeds based on fuzzy PID and laser ranging[J]. Astronomical Research & Technology,—Publications of National Astronomical Observatories of China, 2013, 10(2):162-170.   
[8] Chen Jie_，Dong Shucheng, Jiang Fengxin, et al. Shutter heating system of Antarctic bright star survey telescope[C]// Proceedings of SPIE. 9915.