# 2840MHz太阳射电辐射流量计的升级改造

杜静1,²，颜毅华¹，徐之材³，殷兴辉4，王威¹，谭程明¹，陈志军1（1.中国科学院国家天文台太阳活动重点实验室，北京100012；2.中国科学院大学，北京100049;3.南京射电天文技术研究所，江苏 南京 210024；4.河海大学，江苏 南京 211100)

摘要：叙述了国家天文台升级改造后的 $2 8 4 0 \mathrm { M H z }$ 太阳射电辐射流量计的设计特点、性能、结构及观测结果。升级改造后的太阳射电辐射流量计将在较高时间分辨率上实时得到 $2 8 4 0 ~ \mathrm { M H z }$ 频率上的太阳流量，为太阳物理研究积累丰富的观测数据，是太阳活动监测和预报的重要参数之一。

关键词：射电天文；太阳射电辐射流量计；流量观测；辐射计中图分类号：P111.44 文献标识码：A 文章编号：1672-7673(2016)01-0052-06

太阳微波辐射流量与黑子相对数、耀斑爆发、X射线爆发以及高能电子质子事件均有一定的关系[1]，而 $2 8 4 0 ~ \mathrm { M H z }$ （波长为 $1 0 . 7 \mathrm { c m } \dot { } \mathrm { \Omega } ,$ )的太阳射电辐射流量与黑子相对数及高能电子和质子事件的关系最为密切，是地球空间物理的重要输入参数。因此， $2 8 4 0 ~ \mathrm { M H z }$ 的射电辐射流量监测对研究太阳活动规律、太阳长期演化行为，建立更加完善的太阳活动预报模型以及太阳射电天文学的发展等具有极其重要的意义。国家天文台怀柔 $2 8 4 0 ~ \mathrm { M H z }$ 太阳射电辐射流量计长期参与国际联网观测，连续三十多年为国际太阳和地球物理数据中心提供观测数据，为国际太阳活动预报提供可靠的数据支持。文[2]利用怀柔 $2 8 4 0 \mathrm { M H z }$ 太阳射电辐射流量计的长期观测数据研究太阳活动周的相似性行为，并预测第24活动周的开始时间和最大活动强度。文|3 利用 $2 ~ 8 4 0 ~ \mathrm { M H z }$ 射电辐射流量的长期观测数据研究了太阳长期活动行为，发现太阳活动的中短时间尺度的周期性与太阳系行星运动之间有较强的相关性。同时， $2 8 4 0 ~ \mathrm { M H z }$ 太阳射电辐射流量计也是中国空间环境监测网的重要组成部分，为国家航空航大任务提供空间环境保障发挥了重要作用。

$2 8 4 0 ~ \mathrm { M H z }$ 太阳射电辐射流量计位于国家天文台怀柔太阳观测基地怀柔水库北岸，距离北京市中心约 $6 0 ~ \mathrm { k m }$ ，北纬 $4 0 . 3 ^ { \circ }$ ，东经 $1 1 6 . 6 ^ { \circ }$ ，海拔高度 $6 4 ~ \mathrm { m }$ 。附近有较强的机场雷达信号干扰，但干扰信号特征明显，数据处理过程中，可通过成熟的数据处理方法予以剔除。21世纪初，该设备由于长年运行，多数元器件老化停止了观测，考虑到 $2 8 4 0 ~ \mathrm { M H z }$ 太阳射电辐射流量计是国内唯一的单频射电辐射流量计及其在太阳活动研究方面的重要意义，经过充分调研，对 $2 8 4 0 ~ \mathrm { M H z }$ 太阳射电辐射流量计进行了升级改造。新设备对包括微波前端（从低噪放开始）、模拟接收系统、数字采集系统、存储及显示系统都进行了升级改造，天线采用 $2 \mathrm { m }$ 抛物面反射面天线，赤道式装置。同时，采用了K因子辐射计和新的定标技术，使得定标更加高效，定标结果更加精确可信[4]。目前，该设备已获取了一些良好的观测结果。

# 1系统指标

太阳射电望远镜系统是自动化程度较高的空间探测装备，具有定标系统、自动采集观测数据、自动生成和传送设备，同时具有较高的可靠性、稳定性，能全天候长期、连续地运行。系统指标如表1。

表1 $2 8 4 0 \mathbf { M H z }$ 太阳射电辐射流量计系统指标  
Table1The system specifications of the upgraded Solar Radio Flux Telescope working at 2840MHz   

<html><body><table><tr><td>工作频率</td><td>灵敏度</td><td>输出中频带宽</td><td>时间分辨率</td><td>噪声系数</td><td>输出功率</td><td>步进衰减器范围</td></tr><tr><td>/MHz 2 840</td><td>/sfu</td><td>/MHz</td><td>/ms</td><td>/dB</td><td>/dBm</td><td>/dB</td></tr><tr><td></td><td>≤1</td><td>10</td><td>1</td><td>≤3</td><td>≥10</td><td>0~31</td></tr></table></body></html>

# 2系统结构

$2 8 4 0 ~ \mathrm { M H z }$ 太阳射电辐射流量主要用于太阳活动长期行为的研究和太阳预报，对测量精度和数据的稳定性要求很高，因此，在本次升级改造过程中采用镜像抑制的超外差式接收机方案，可很好地抑制干扰，选用K因子辐射计保证仪器的灵敏度和稳定性。同时，近年来关于太阳活动的短期行为也不断受到太阳物理学家的高度重视，而 $2 ~ 8 4 0 ~ \mathrm { M H z }$ 太阳射电流量有最灵敏的响应，因此，为了满足这方面的科学需求，采用了衰减器和对数放大器2种方法以提高数据的动态范围。系统结构如图1。

# 3系统特点

# 3.1 良好的抗干扰设计

采用镜像抑制的超外差式接收机，在混频器前加 $2 ~ 8 4 0 ~ \mathrm { M H z }$ 的声表面带通滤波器，选用较高中频 $f _ { \mathrm { o } } { = } 2 2 5 ~ \mathrm { M H z }$ ，中频带宽 $B W _ { _ { \mathrm { I F } } } = 1 0 ~ \mathrm { M H z }$ ，采用 $B W / f _ { \mathrm { o } } = 5 \%$ 的声表面带通滤波器，矩形系数接近1，带外衰减大，对镜频可抑制 $2 0 \sim 3 0 ~ \mathrm { d B }$ ，从而有效抑制镜频干扰和带外干扰，保证观测数据

![](images/e1ebc4f698b71cfeed5ce452773a1d42a6aca0400b1606e2beb7b9537b614a2a.jpg)  
图1 $2 8 4 0 \ \mathrm { M H z }$ 太阳射电辐射流量计方框图 Fig.1The block diagram of the upgraded Solar Radio Flux Telescope working at $2 8 4 0 \mathrm { M H z }$

的可靠性。同时，采用合理的微波放大器，有效抑制交调互调干扰信号的产生，采用良好的电磁兼容性设计，防止干扰信号寄生耦合到信号通道。模数转换器放在接收机机箱内，与低放输出短线相接，减小 $5 0 \ \mathrm { H z }$ 等低频干扰。

# 3.2大动态范围

采用衰减器和对数放大器2种方法扩大测量动态范围的技术，构成2个并行输出的信号。衰减器法采用1dB步进的最大衰减量为31dB的数控步进衰减器，用它调整中频输出信号电平，数控步进衰减器由计算机自动控制[5。衰减器法测宁静太阳和小爆发的精度较高，但观测大爆发时由于衰减量变化，产生观测数据的跳变，虽然计算处理后能恢复连续变化特性，但精度有所下降。对数放大器法可获得连续变化的记录，特别适用于记录大爆发，精度可达 $0 . 2 \ \mathrm { d B }$ 。

# 3.3采用K因子辐射计

K因子辐射计是根据德国天文学家Keen提出的K因子测量原理而发展的新型辐射计，其信号路工作在全功率计状态，灵敏度高。采用天线温度定标的噪声源与K因子辐射计调制式噪声源合一的方案，通过测量定标常数 $C _ { \mathrm { s } }$ 对系统进行定标，实现观测与温度标定同时自动进行，提高了标定精度[6-7]。升级改造后的 $2 8 4 0 \mathrm { M H z }$ 太阳射电辐射流量计采用K因子式辐射计，其原理图如图2，图中对应部件代码和符号见表2。

表2原理图中的部件代码和符号  
Table 2The component codesand symbols in the block diagram   

<html><body><table><tr><td>部件代码或符号</td><td>A</td><td></td><td>MNS</td><td>RF/IF</td><td>+</td><td>DC</td><td>AC</td><td>PD</td><td>己</td></tr><tr><td colspan="2">说明</td><td>天线</td><td>被调制 噪声源</td><td>高中频 单元</td><td>平方律 检波器</td><td>直流 放大器</td><td>交流 放大器</td><td>相敏 检波器</td><td>同步 信号源</td></tr><tr><td colspan="2">代码</td><td>T</td><td></td><td>2△T</td><td>G</td><td>kc</td><td>kAc</td><td></td><td></td></tr><tr><td rowspan="3">说明</td><td>Ta</td><td></td><td>噪声源</td><td></td><td>RF/IF等效</td><td></td><td></td><td>VDc</td><td>VAC</td></tr><tr><td>天线</td><td>接收机</td><td></td><td></td><td>增益</td><td>直流路 放大量</td><td>交流路 放大量</td><td>直流路</td><td>交流路</td></tr><tr><td>T</td><td>T</td><td>交变量峰峰值</td><td></td><td></td><td></td><td></td><td>输出</td><td>输出</td></tr></table></body></html>

# 3.3.1K因子辐射计的基本关系

K因子辐射计天线口面的噪声分量和时变状态如图3。直流分量 $\overline { { T } } = T _ { a } \ : + \ : T _ { r } \ : + \ : \Delta T$ ，交流分量$\Delta { T _ { \mathrm { { c } } } }$ （204号

采用理想平方律检波器，且放大器工作在线性态时， $V _ { \mathrm { D C } }$ 和 $V _ { \mathrm { A C } }$ 两路输出与 $T _ { \mathrm { a } } , \ T _ { \mathrm { r } }$ 和 $\Delta { T }$ 的关系[8-9].

$$
V _ { \mathrm { { D C } } } = k o G _ { \mathrm { e } } k _ { \mathrm { { D C } } } ( T _ { \mathrm { { a } } } + T _ { \mathrm { { r } } } + \Delta T ) ,
$$

$$
V _ { \mathrm { { A C } } } = k o G _ { \mathrm { e } } k _ { \mathrm { A C } } \Delta T .
$$

K因子定义： $K = V _ { \mathrm { D C } } / V _ { \mathrm { A C } }$ ，将(1）、（2)代入上述关系式，得： $K = \big ( T _ { \mathrm { a } } ^ { } + T _ { \mathrm { r } } ^ { } + \Delta T _ { \mathrm { r } } ^ { } \big ) / C$ ，式中：

$$
C = \Delta T k _ { \mathrm { A C } } / k _ { \mathrm { D C } } ,
$$

故 $T _ { \mathrm { { a } } } = C K - T _ { \mathrm { { r } } } - \Delta T _ { \circ }$

3.3.2用 $\mathrm { \Delta K }$ 因子辐射计观测射电源

(1)对准射电源时：得到的K因子为 $K _ { \mathrm { s } }$ ，此时， $T _ { \mathrm { a } } = T _ { \mathrm { s } } + T _ { \mathrm { b } }$ ， $T _ { \mathrm { { s } } } + T _ { \mathrm { { b } } } = C K _ { \mathrm { { s } } } - T _ { \mathrm { { r } } } - \Delta T _ { \circ }$

(2)对准射电源背景时：得到的K因子为$K _ { \mathrm { b } }$ ，此时， $T _ { \mathrm { a } } = T _ { \mathrm { b } }$ ， $T _ { \mathrm { b } } = C K _ { \mathrm { b } } \ : - \ : T _ { \mathrm { r } } \ : - \ : \Delta T _ { \circ }$ 以上两式相减得到：

$$
\begin{array} { r } { T _ { \mathrm { s } } = C ( K _ { \mathrm { s } } \ – \ K _ { \mathrm { b } } ) . } \end{array}
$$

$T _ { \mathrm { s } }$ 为天线温度中射电源分量； $T _ { \mathrm { b } }$ 为天线温度中背景噪声温度分量。

# 3.3.3 定标常数 $C _ { \mathrm { s } }$ ：

![](images/15c852e0f4e6a7ce1eb0b222809ac8ee23fe555906dbcadfe6ee17ec2bb56fab.jpg)  
图2K因子辐射计原理图 Fig.2The block diagram of the radiometer for the K-factor measurement

![](images/7a8681e5b36b97c9af9b2ac55c64c53b2e880e66b06c59816908f496af7d995b.jpg)  
图3K因子辐射计天线口面的噪声分量和时变状态图  
Fig.3The diagram of the noise components and time varying state for the antenna of the radiometer with the K-factor measurement

当天线的波束宽度远大于射电源视角径时， $ { T _ { \mathrm { s } } } =  { A _ { \mathrm { e } } } S / 2 k$ ，$A _ { \mathrm { e } }$ 为天线的有效接收面积； $k$ 为玻尔兹曼常数。

结合(3）、（4)两式：

$$
C ( K _ { \mathrm { s } } - K _ { \mathrm { b } } ) = A _ { \mathrm { e } } S / 2 k ,
$$

由此可得到：

$$
S = C _ { \mathrm { s } } ( K _ { \mathrm { s } } ^ { } - K _ { \mathrm { b } } ^ { } ) ,
$$

$$
\begin{array} { r } { C _ { \mathrm { s } } = 2 k C / A _ { \mathrm { e } } = S / ( K _ { \mathrm { s } } - K _ { \mathrm { b } } ) . } \end{array}
$$

实际操作中，首先采用其它射电望远镜获得太阳等射电源流量 $s$ ，然后分别对太阳和背景进行观测获得 $K _ { \mathrm { s } }$ 和 $K _ { \mathrm { b } }$ ，相对测量的望远镜与它比对后，依据(6)式可获得定标常数 $C _ { \mathrm { s } }$ 。将 $C _ { \mathrm { s } }$ 数值输入定标

软件中作为配置参数使用，之后分别对背景和太阳进行观测，依据(5)式即可获得太阳流量值，相对测量转换为绝对测量。

# 4系统性能

# 4.1灵敏度

在射电天文观测中，灵敏度是射电望远镜的重要指标，决定了接收系统检测弱信号的能力，定义为“最低可测”的辐射流量密度Smin [1,10]。

宁静太阳射电辐射流量： $S = 8 0 \ \mathrm { s f u ^ { ( \mathrm { 1 } ) } }$

天线有效面积： $A _ { \mathrm { e } } = \eta \pi d ^ { 2 } / 4 = 2 . 6 7 ~ \mathrm { m } ^ { 2 }$ ，式中，天线直径 $d = 2 { \mathrm { ~ m ~ } }$ ；天线效率 $\eta = 8 5 \%$ 天线温度的太阳分量： $T _ { \mathrm { s } } = A _ { \mathrm { e } } S / 2 k = 2 . 6 7 \times 8 0 \times 1 0 ^ { - 2 2 } / ( 2 \times 1 . 3 8 \times 1 0 ^ { - 2 3 } ) = 7 7 4 \mathrm { K }$ 辐射计的工作参数见表3。

表3 $\mathbf { K }$ 因子辐射计的工作参数  
Table 3The working parameters of the radiometer with the K-factor measurement   

<html><body><table><tr><td>参数名</td><td>天线温度的 太阳分量</td><td>天线温度的 背景分量</td><td>接收机噪声温度 (NF=3 dB)</td><td>馈线插损</td><td>带宽</td><td>时间 常数</td><td>工作 温度</td><td>辐射计 注入噪声</td></tr><tr><td>符号</td><td>T</td><td>Tb</td><td>T.</td><td>L</td><td>BW</td><td>T</td><td>T。</td><td>△T</td></tr><tr><td>参数值</td><td>774 K</td><td>30K</td><td>290 K</td><td>0.89(-0.5 dB)</td><td>10 MHz</td><td>1s</td><td>290 K</td><td>290 K</td></tr></table></body></html>

K因子辐射计理论灵敏度（ $S / N { = } 1 \$ ：总插损 $L _ { \mathrm { i } } { = } 0 . 8 9$ 天线温度： $T _ { \mathrm { a } } = T _ { \mathrm { s } } + T _ { \mathrm { b } } = 8 0 4 \ : \mathrm { K }$

系统噪声温度：

$T _ { \mathrm { s y s } } = L _ { \mathrm { i } } T _ { \mathrm { a } } + \left( 1 - L _ { \mathrm { i } } \right) T _ { \mathrm { o } } + T _ { \mathrm { r } } + \Delta T = 0 . 8 9 \times 8 0 4 + \left( 1 - 0 . 8 9 \right) \times 2 9 0 + 2 9 0 + 2 9 0 = 1 3 2 7$ K噪声起伏： $\Delta T _ { \mathrm { { m i n } } } = T _ { \mathrm { { s y s } } } / ( 2 B w \tau ) ^ { 1 / 2 } = 0 . 2 9 7 \mathrm { { K } / \mathrm { { H z } } }$ （20系统灵敏度： $\Delta S _ { m i n } = 2 k T _ { \mathrm { m i n } } / A _ { \mathrm { e } } = 2 \times 1 . 3 8 \times 1 0 ^ { - 2 3 } \times 0 . 2 9 7 / 2 . 6 7 = 0 . 0 3 1 \ \mathrm { s f u }$

4.2计算机系统及软件功能

(1)用4路 $\boldsymbol { \mathrm { A } } / \boldsymbol { \mathrm { D } }$ 采集监测电压 $V _ { \mathrm { m } }$ 、直流输出电压 $V _ { \mathrm { d c } }$ 、交流输出电压 $V _ { \mathrm { a c } }$ 和对数放大器输出电压 $V _ { \mathrm { l o g } }$ 。根据 $V _ { \mathrm { m } }$ 值控制步进衰减器，令接收机处于合理工作状态。根据人工输入的‘S'（观测太阳)和‘B'（观测背景)确定 $V _ { \mathrm { d c } }$ 和K因子是 $V _ { \mathrm { d c s } }$ 、 $K _ { \mathrm { s } }$ 还是 $V _ { \mathrm { d c b } }$ 、 $K _ { \mathrm { b } }$ 。进行数字积分时，标准的积分时间为 $1 ~ \mathrm { m s }$ 和1s两种，两种数据可同时显示和记录。升级改造后的 $2 8 4 0 \mathrm { M H z }$ 太阳射电辐射流量计的观测软件界面如图4。

(2)进行预处理，如：

$\textcircled{1}$ 步进衰减器的跳变式记录变为连续渐变式记录；  
$\textcircled{2}$ 显示实时的太阳流量;  
$\textcircled{3}$ 显示全天太阳流量变化;  
$\textcircled{4}$ 对数值变换为比值显示。

(3)数据存储：可同时存储积分时间为 $1 \mathrm { m s } ( . \mathrm { n w m } )$ 和1s(.nws)的观测数据。采用整型数据存储，包括 64字节文件头和观测数据，每2字节表示一个采样点（观测数据点）。毫秒级文件是每10s存一个文件，每个文件 $2 0 ~ \mathrm { K B }$ ，每天的数据量约为 $5 6 \mathrm { ~ M ~ }$ ，秒级文件每天的数据量约为 $6 0 ~ \mathrm { K B }$ （按每天观测$^ { 8 \mathrm { ~ h ~ } }$ 计算）。

(4)数据发布：望远镜从1977年开始观测，2010年进行设备的升级改造，其数据已连续积累三十多年，定期发布在国家天文台太阳数据中心（http://csrh.bao.ac.cn/data/），用户可自由下载。

![](images/3d9b6af0702a59091b8c5ac77f72b01f0c000af9bae9497392b0c5db43a35b61.jpg)  
图4观测软件界面

# 5观测结果

利用经过上述升级改造后的 $2 ~ 8 4 0 ~ \mathrm { M H z }$ 太阳射电辐射流量计对太阳进行观测，成功观测到2011年2月15日X2.2级大耀斑爆发(图5）。该事件是一个典型的长持续(近1个小时)复杂型(多峰)射电爆发事件。复杂的多峰结构对应同频率的频谱观测中有斑马纹、脉动、慢漂移等丰富的精细结构[1]

# 6 结论

本文介绍了国家天文台怀柔观测站 $2 8 4 0 \mathrm { M H z }$ 太阳辐射流量计的升级改造。新设备采用了K因

![](images/3cec07305b316f030aea3692d081479d5b2221f3992a45355fc3acc4853dfb4f.jpg)  
Fig.4The interface of the observation software   
图52011.2.15X2.2级耀斑-新系统Fig.5The X2.2 solar flareon Feb.15，2011observed with the new system

子辐射计及新的定标技术，对微波前端、模拟接收系统、数字采集系统、存储显示系统也进行了升级改造。通过设备的升级改造，改进了天线的观测性能，其数据对研究耀斑物理动力学过程、能量释放、太阳活动规律及太阳长期演化行为等具有重要意义，为相关研究提供了丰富的观测依据。

致谢：衷心感谢设备安装、调试过程中南京射电天文技术研究所吴枫、河海大学沈亚明等的大力支持和帮助。

# 参考文献：

[1] 赵仁扬，金声震，傅其骏．太阳射电微波爆发［M].北京：科学出版社，1997.  
[2] Wang Jialong，Zong Weiguo，Le Guiming，et al.Predicting the start and maximum amplitude ofsolar cycle 24 using similar phases and a cycle grouping [J]. Research in Astronomy andAstrophysics，2009，9(2）：133-136.  
[3] Tan Baolin，Cheng Zhuo.The mid-term and long-term solar quasi-periodic cycles and the possiblerelationship with planetary motions ［J]. Astrophysics & Space Science，2013，343（2）: 511-521.  
[4] 彭树生.提高微波辐射计绝对测量精度的研究［D].南京：中国科学院紫金山天文台，1995.  
[5] 董亮，何乐生，施硕彪．太阳射电 $8 0 0 { \sim } 9 7 5 ~ \mathrm { M H z }$ 波段高动态范围模拟接收机的研制［J].天文研究与技术——国家天文台台刊，2014，11(2)：111-117.Dong Liang，He Lesheng，Shi Shuobiao.Design of a high dynamic range analog receiver for solarradio observation in 8OO-975MHz ［J].Astronomical Research & Technology——Publications ofNational Astronomical Observatories of China，2014，11(2）：111-117.  
[6] 杨精一.微波辐射计定标方程研究［J].长春光学精密机械学院学报，2001，24（3)：21-24.Yang Jingyi.Research of the establish standard of equation with the microwave radiator [J].Journal of Changchun Institute of Optics and Fine Mechanics，2001，24(3）:21-24.  
[7] 刘丽佳，刘彬，董亮，等.云南天文台40米射电望远镜S波段总流量观测系统研制和测试[J].天文研究与技术——国家天文台台刊，2013，10(2)：134-141.Liu Lijia,Liu Bin,Dong Liang，et al.Development and testing of an S-band flux measurement systemfor the $4 0 \mathrm { m }$ radio telescope of the Yunnan Observatory [J]. Astronomical Research & Technology-Publications of National Astronomical Observatories of China，2013，10(2）：134-141.  
[8] 彭树生，殷兴辉，徐之材．五毫米大气遥感微波辐射计［J].遥感技术与应用，1995，10(2):38-41.Peng Shusheng，Yin Xinghui，Xu Zhicai. 5mm microwave radiometer for atmosphere remotesensing ［J].Remote Sensing Technology and Application，1995，10(2）:38-41.  
[9] 吴礼.毫米波辐射计特性参数与性能测试研究［D].南京：南京理工大学，2004.  
[10] 王威，窦玉江，颜毅华，等.CSRH灵敏度分析［J].天文研究与技术—国家天文台台刊，2013，10(1):22-25.Wang Wei，Dou Yujiang，Yan Yihua，et al.Analysis of the sensitivity of the CSRH［J].Astronomical Research & Technology———Publications of National Astronomical Observatories ofChina，2013，10(1)：22-25.  
[11]Tan Baolin，Yan Yihua，Tan Chengming，et al. Microwave zebra pattern structures in the X2.2solar flare on 2011 February 15 [J]. Astrophysical Journal,2012，744(2）:1-10.

# Upgrading the Solar Radio Flux Telescope with the Frequency of 2.84GHz

Du Jing $^ { 1 , 2 }$ ，Yan Yihua'， Xu Zhicai $^ 3$ ， Yin Xinghui $^ 4$ ，Wang Wei’，Tan Chengming’， Chen Zhijun $^ { 1 }$   
(1.KeyLaboratoryofSlarActivity，NationalAstronomicalObservatories，Chinese AcademyofSiences，Beijingol,China, Email：jdu@ nao.cas.cn；2.UniversityofChinese Academyof Sciences，Beijing 10o049,China；3.Nanjing Instituteof Radio Astronomical Technology，Nanjing 210024,China；4.Hehai University，Nanjing 21100,China)

Abstract：The solar radio flux telescope with the frequency of 2.84GHz is an important instrument to monitor and forecast the solar activities bycolecting and analyzing the solarradio fluxes.At the beginning of the 2lst century，the regular monitoring by using such an instrument was stopped due to ageing of most components and dificult to repair during the long running.Now we have updated the microwave front-end,the analog receiving system，the digital acquisition system，the storage and display system，and the $2 \mathrm { m }$ parabolic antenna to the system.In the new system we adopted a radiometer for $\mathbf { k }$ -factor measurement and a new selfcalibration technique which makes the calibration more eficient and accurate.At present，the upgraded solar radio flux telescope working at 2.84GHz has achieved some good results.

Key words:Radio astronomy； Solar radio flux telescope；Flux measurement；Radiometer