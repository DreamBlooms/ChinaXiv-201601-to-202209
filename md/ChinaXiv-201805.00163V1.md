# 基于天射电阵的空间目标探测与测向方法研究

李佳威1²,高鹏骐',沈鸣1,金旺1,赵有1

3 (1．中国科学院国家天文台,北京 100012；2.中国科学院大学,北京 100049;  
4 3.中国电波传播研究所昆明电波观测站,云南曲靖 655333)  
6摘要：天籁计划射电望远镜阵列(简称天籁射电阵)具有大视场与高灵敏度双重优势，既可  
7 以在观测时探测到尺寸较小的空间目标，也能在同一时刻探测到多个空间目标，具有较强  
8 的空间目标探测能力，因此可作为空间目标监测设备之一。以曲靖非相干散射雷达作为发  
9 射源，对天籁射电阵的空间目标探测能力进行计算。随后提出了可用于该系统的基于相位  
10 差测量法的空间目标测向方法，并研究了测向误差与测向角度之间的关系。

1关键词：空间目标探测；天籁射电阵；相位差测量法；测向误差

2 中图分类号：P161 文献标识码：A文章编号:1672-7673(2018)03

# Study on detection and direction-finding method of space object based on Tianlai radio array

6 Li Jiawei1'2, Gao Pengqi', Shen Mingl, Jing Wang31, Zhao You1 .7 (1. National Astronomical Observatories, Chinese Academy of sciences,Beijing 10o0l2, China; 8 2.University of Chinese Academy of Sciences, Beijing 10o049, China; .9 3.Kunming Radiowave Observatory, China Research Institute of Radio-Wave propagation, Qujing :0 655333, China)

22 Abstract:Tianlai radio array, which has high sensitivity and large field of view, can detect and   
23 capture multiple small space objects at the same time. It has decent capability of detecting the   
24 space objects,and can be used as one of the space object monitoring equipment. In this paper, the   
25 detection capability of Tianlai radio array is calculated when the incoherent scatering radar in   
26 Qujing city is assumed as a source of transmission. Then a method for direction-finding of space   
27 objects is proposed, which is based on phase difference measurement. The relationship between   
28 direction-finding error and direction-finding angle of space objects is also analyzed.

Key word: space object detection; Tianlairadio array; phase difference measurement method; direction-finding error

31 随着航天技术的发展，越来越多的航天器被送入太空。截止2017年9月底，被编目且  
32 在轨运行的 $1 0 \mathrm { c m }$ 以上的空间目标为18700多个，其中包括在轨运行有效载荷与威胁空间  
33 财产安全的空间碎片。空间目标的观测主要有雷达、光电探测、卫星激光测距、电子篱笆  
34 等[]，特别是美国电子篱笆系统(Space Fence)—美国空军空间监视系统(Air Force Space  
35 Surveillance System,AFSSS)曾是美国空军空间监视网中不可或缺的组成部分。该系统由3  
36 个发射站与6个接收站组成，工作频率为216MHz，运行时在空间中形成东西宽，南北为  
37 的扇形波束屏，可覆盖到西经\~上空的空间目标。接收站在目标穿屏的瞬间接收到目标散射  
38 信号，从而实现对空间目标的探测，并且可监测到美国空间监视网编目目标数中 $40 \%$ 的低  
39 轨道(Low Earth Orbit,LEO)空间目标[2]。该系统的优点在于工作原理简单、系统可靠性高、  
40 覆盖范围广，原则上可以用来探测到进入到发射波束内的任何空间目标，并且发射与接收  
41 波束固定可进行连续工作。但缺点在于波束厚度较窄，导致空间目标穿屏时间过短，需要  
42 目标的多次穿屏才可定轨。正因为美国空军空间监视系统采用了扇形波束提高了视场覆盖  
43 范围，使得该系统可以同时捕获与探测到多个空间目标。目前，该系统正在升级改造中，  
44 改造后的系统将工作频率提高至S波段，可探测到低轨道直径5cm的空间目标[3]。

![](images/3a87452496e23d7a826e9dea7ce48e3c8f16a3b0fc41c73a6e03d767c69ce4a8.jpg)

在射电天文领域，通过使用可形成扇形波束屏的射电干涉阵对空间目标进行探测已有先例，如意大利梅迪奇纳的射电天文站曾于2008年利用北十字射电望远镜阵列（TheNorther Cross Radio Telescope）与雷达协同工作的方式对美国军用卫星USA-193进行探测，并且根据计算该阵列有能力探测 $8 0 0 \mathrm { k m }$ 上空直径为 $2 . 2 \mathrm { c m }$ 的空间目标[5-6]。因此，有可能利用可形成扇形波束屏的射电干涉阵通过双基地雷达系统的方式对空间目标进行捕获与探测。

# 1天射电阵探测能力分析

![](images/9dec9fb1260cf48f5153b71a41d7122c75b4740dea726c4962ecad667bc301f3.jpg)  
图1.升级改造前美国空军空间监视系统位置分布及波束屏形状[4]Fig.1 AFSSS position distribution and the shape of beambefore the system upgrade

位于我国新疆巴里坤地区的“天籁计划”射电望远镜阵列主要用于对宇宙中的暗能量进行大面积天区的射电观测。阵列在一定条件下可被用于空间目标的探测。阵列由3面 $4 0 \mathrm { m } 1 5 \mathrm { m }$ 的抛物柱面天线、96个双线极化馈源组成，工作频率在400\~1400MHz，运行时可形成类似于“电子篱笆”的扇形波束，随着地球的自转，波束可以扫过大面积天区，从而达到巡天的目的。天籁射电阵具有高灵敏度、大视场的的优点，不仅可以对空间目标进行探测，还可以在同一时刻探测到多个空间目标。

天籁射电阵接收机灵敏度可表示为

70其中，（）表示玻尔兹曼常数； $\phantom { 0 } { 0 } = 5 0 \mathrm { K }$ 表示接收机系统温度（包括接收机系统的环境温度与

71热噪声）；干涉阵包含的天线数；表示积分时间；工作带宽 ${ \bf \Lambda } = 4 \mathrm { M H z }$ 。当把积分时间设定为1s 时，得到天籁射电阵的接收机灵敏度约为- $1 6 8 . 4 \mathrm { d B m }$ 。

曲靖非相干散射雷达属于单脉冲雷达，发射频率为 ${ 5 0 0 } \mathrm { M H z }$ ，满足天籁射电阵的接收频率要求，因此可以考虑将天籁射电阵与曲靖非相干散射雷达组成双基地雷达系统对空间目标进行探测。根据文[7]，曲靖非相干散射雷达位于东经 $1 0 3 . 7 ^ { \circ }$ 、北纬 $2 5 . 6 ^ { \circ }$ ，天线口径达$2 9 \mathrm { m }$ ，发射机峰值功率为2MW，平均功率 $1 0 0 \mathrm { k W }$ ，工作带宽 $4 \mathrm { M H z }$ ，系统噪声温度为130K，天线增益 $4 2 . 7 \mathrm { d B }$ 。在不考虑各种系统损耗与大气衰减的前提下，可利用双基地雷达基本方程对天籁射电阵的空间目标探测能力进行计算。双基地雷达基本方程为[8]

其中，，表示雷达发射功率与射电阵接收机灵敏度；，分别为发射天线的增益与接收天线增益；表示系统工作频率；表示空间目标雷达散射截面积；与分别表示空间目标分别到雷达与到射电阵之间的距离。

![](images/ccee9d6edfafcff4751db3ab93ad3c5d07c6ccfb87e5062b2a66bc80d1cdf2fa.jpg)  
图3.天籁射电阵一非相干散射雷达系统空间目标探测示意图 Fig.3 the schematic diagram of space objects detection in Tianlai& incoherent scattering radar system

由于雷达发射功率受限，双基地雷达系统通常用于观测低轨道的空间目标，因此将探测高度设定为 $4 0 0 { \sim } 2 0 0 0 \mathrm { k m }$ 。将非相干散射雷达发射机平均功率 $1 0 0 \mathrm { k W }$ 设为系统的发射功率，工作频率 ${ 5 0 0 } \mathrm { M H z }$ ，根据两站实际的地理位置并利用(2)式对天籁射电阵的探测能力进行计算，计算结果如表1。

表1.天籁射电阵-非相干散射雷达系统可探测目标能力  

<html><body><table><tr><td>探测高</td><td>Taoie.TDetcctioncapaortyor alaidicoicrct 散射截面积/dBm2</td><td>目标直径 /cm</td><td>scattergTadarSyste 覆盖纬度 /0</td></tr><tr><td>度/km 400</td><td>0.0003</td><td>6.2</td><td>39~49</td></tr><tr><td>800</td><td>0.0013</td><td>7.9</td><td>34.5~53.5</td></tr><tr><td>1200</td><td>0.0034</td><td>9.3</td><td>31~57</td></tr><tr><td>1600</td><td>0.0069</td><td>10.5</td><td>28~60</td></tr><tr><td>2000</td><td>0.0128</td><td>11.6</td><td>25.5~62.5</td></tr></table></body></html>

由表1可知，随着探测轨道高度的提升，天籁射电阵可探测到一段纬度范围上空低轨道范围内直径 $1 0 \mathrm { { c m } }$ 以下的空间目标。

# 2全波段探测空间目标雷达散射截面积分析

由于探测目标的雷达散射截面积(Radar Cross Section，RCS)与系统工作频率有关，根据天射电阵的参数可知，接收机工作频率为 $4 0 0 { \sim } 1 4 0 0 \ \mathrm { M H z }$ ，因此可以对满足该工作频率范围内可探测的雷达散射截面积进行计算。假设某雷达发射功率为 $1 0 0 \mathrm { k W }$ ，与天籁射电阵之间基线长度为 $1 0 0 0 { \mathrm { k m } }$ ，雷达的其他各项指标与非相干散射雷达相同且可以调节发射频率使其满足天籁射电阵的所有工作频率，利用(2)式可以得到在不同探测高度下工作频率与雷达散射截面积关系，如图4。

在探测高度相同时，随着双基地雷达系统工作频率的增加，可探测到的目标雷达散射截面积减小，即可看到更小的碎片，根据目前天籁射电阵的指标进行计算，当工作频率为 $4 0 0 \mathrm { M H z }$ 时，系统可探测到$4 0 0 \mathrm { k m }$ 、 $8 0 0 \mathrm { k m }$ 与 $1 2 0 0 \mathrm { k m }$ 处直径约为$5 . 9 \mathrm { c m }$ 、 $7 . 9 \mathrm { c m }$ 与 $9 . 8 \mathrm { c m }$ 的空间碎片；当工作频率为 $1 4 0 0 \mathrm { M H z }$ 时，可探测到$4 0 0 \mathrm { k m }$ 、 $8 0 0 \mathrm { k m }$ 与 $1 2 0 0 \mathrm { k m }$ 处直径约为

![](images/46604978835eca9b878594a14fc51b92fdf5179d2c59dcf75547c17ecec4edf1.jpg)

$1 . 7 \mathrm { c m }$ 、 $2 . 3 \mathrm { c m }$ 与 $2 . 8 \mathrm { c m }$ 的空间目标。通过上述分析，天籁射电阵有能力探测到直径为10cm 以下的空间目标，并且随着工作频率的增加，探测能力可提高至直径5cm以下的空间目标。

# 3探测空间目标效率分析

利用卫星工具软件(Systems ToolKit,STK)对天籁射电阵的空间目标探测效率进行分析。将软件运行时间设定为UTC2017.05.2300:00:00\~2017.05.2400:00:00，对随机选取的已编目的低轨道范围内的部分在轨目标进行仿真，通过对目标的穿屏次数进行统计得到天籁射电阵对低轨道目标的探测效率。在仿真中，随机选取了1079个空间目标进行仿真分析，结果如图5、图6。

![](images/c5b4a6667e6d7cc81a6899aded304add44baad20d329b8006470594097228da4.jpg)

![](images/3fea6c0ed53779b83a476a658a1db96a6b5c296d945bb8e2ad74359a4ca1a96d.jpg)  
图5．LEO在轨目标探测次数统计图图6．空间目标的穿屏时间分布图 ig.5 The bar graph ofLEO space objectsFig.6 Time distribution graph of space objects detection times cross the beam

根据仿真结果可知，天籁射电阵可探测到低轨道范围内1079个空间目标中的518个，探测效率约为 $48 \%$ 。其中有518个被探测的目标中某些目标在该段时间内被多次探测到，有17个目标可被探测到5次。在目标穿屏的过程中，如果将采样周期设定为1s，则对于穿屏时间较长的目标在一次穿屏过程中可实现多次采样，每一次采样的结果可作为一次观测结果。通过图6可知，大部分空间目标穿屏时间主要集中为 $3 { \sim } 2 0 ~ \mathrm { s }$ ，因此对于穿屏时间较长的目标可以进行在其穿屏时间内多次完整探测。在所有的目标中，穿屏时间最短的空间目标FLOCK-3P38(NORADID:42037)约为0.05 秒；穿屏时间最长的空间目标 SWARM-B(NORADID：39451)为164.88s，即当该目标在穿过天籁射电阵的接收波束时，可以进行多次观测。根据统计结果还可以得到，天籁射电阵对于轨道倾角接近 $9 0 ^ { \circ }$ 且轨道高度较高的空间目标具有更长的观测时间。

天籁射电阵不需要对单个星系进行观测，因此对角分辨率的要求并不高，只需要15即可满足自身的科学目标。这就导致当使用天籁射电阵对角秒级的空间目标很难通过成像的方式进行定位。由于天籁射电阵为平面阵，因此可用相位差测量的方法对空间目标进行测向定位。

# 4测向方法及误差分析

# 4．1.一维干涉阵测向方法

当发射源至射电干涉阵的距离远大于馈源间的基线长时，发射源信号可以近似为平行方向被馈源接收，并且由于传播路径之间的差值产生相位差，如(3)式，可得到一维射电阵的相位测向公式为

其中，为基线的相位差；D为基线长度；为从基线法线方向测得的信号入射角；为信号波长。

射电干涉阵在观测天体或空间目标时得到的复数形式的数据，其相位主值在之间，则测量得到的相位差在(或)的范围内。所以当基线长度时，对于任一方向信号的相位差在以内，此时通过测量值可以得到真实信号的入射角。而当时，由于  
l61 对某一方向信号实际的相位差可能  
[62 超出测量值相位差的范围，因此很  
l63 难从测量值推算真实的信号入射角，  
[64 导致相位模糊的产生。相位差为产

![](images/8246341e6b1e0a0ba0cd00fe13d3fb292981e30b4f9639ce2cf719ab961118f8.jpg)

生相位模糊的边界值，此时通过计算得到的入射角可定义为最大不模糊视场角，而随着入射角增大，相位差逐渐增大并且大于，出现相位模糊的情况。最大不模糊视场角与基线长D 的关系如图7。

为避免产生相位模糊，要求基线长 $D$ 必须小于或等于。由(3)式可知，在方位角确定的条件下，相位差的变化受基线长度的影响较大，因此对基线长度的限制不仅会影响到相位差的测量，同时也影响测向的精度，特别是长基线对相位差测量的影响更加明显。通常情况下利用长基线测量得到的相位差信息求解目标的入射角，但是由于长基线产生多个入射

172 角度的情况，所以可采用长短基线结合的方式，利用短基线与长基线之间的比值关系得到  
173 实际方向角的精值，解决相位模糊的问题。

# 4．2.二维射电干涉阵测向方法

二维相位干涉测向是以等长的直角三角形各顶点布置测向天线单元为例，如图8，二维相位干涉测向公式为

180 其中，为基线的相位差；为基线的相位差； $D$ 为基线长度；为信号入射方向角；为信号入  
181 射高度角；为信号波长。

![](images/509c5d4b6530e20fd726a9840a18dff8922030a6e23dbed9c756354d73d6c195.jpg)  
图8.二维相位干涉阵测向原理图  
Fig.8 Direction-finding principle of 2-D phase interference array

根据(4)式、(5)式可以求出信号的入射角与高度角为

与一维干涉阵相同的是，当测向天线间距时，对于任一方向信号的相位差在以内，不存在多个信号入射角。当时，对某一方向信号的相位差可能超过的范围，存在多个信号入射角，造成相位模糊的情形。

在对射电干涉阵上的馈源进行排布时，为让阵列满足一定观测要求，将一些馈源排布方式设计为不规则排布的形式，使不同馈源之间的基线长度不同。假定一个五元馈源阵列如图9。

![](images/07b44611d0d019e2b9d410a49eea6e5d46725178510b48c8a4e2205e2403743c.jpg)  
图9.非均匀五元阵列测向原理图 Fig.9 Uneven distribution five element array direction-finding schematic diagram

根据图9，设定4条基线分别为，，与，基线的长度分别用，，，表示，基线上不同天线间的相位差分别为，，，。根据天线位置几何关系可以得到：

其中，为入射波波长；为目标入射波入射方位角；为入射波入射高度角。

由于在解算长基线的相位模糊时使用多个馈源辅助求解，使得长基线进行测向时的精度更高。因此，利用得到的长基线相位差对目标方位角与高度角的测向信息进行求解后得到

针对长基线的测量相位差与实际相位差之间存在相位模糊问题，在求解长基线的实际相位差时需要求解相位模糊。当基线长、时，有

其中，，与，表示基线，的相位差精确值与测量值。此时，短基线的相位差的测量值与精确值相等。

此时，当基线长、时，有

其中，，与，表示基线，的相位差精确值与测量值，，为基线，的相位差粗值。因为基线相位差与基线长度存在比值关系，所以有

228 将，代入粗值中，并与精确值进行匹配后可以得到周期值，并求得相位差的精确值。再将  
229 相位差精确值代入(12)式、(13)式后，便可得到目标信号的入射方位角与高度角，从而实现  
230 对目标的测向。  
231

4．3.误差分析

233 如(3)式，以一维干涉阵测向方法对空间目标的入射角测量值为例进行误差分析。在各  
234 个量相互独立的前提下对(1)式两边分别关于入射角、入射波波长与基线长度求全微分可以  
235 得到

用相位差测量误差、基线长测量误差与信号波长测量误差来表示，则有

239 根据误差传播定律可以得到[10：

241 其中，为入射角的标准差；为测量相位差的标准差；为测量入射信号波长的标准差；为测  
242 量基线长的标准差。一般情况下，基线长度与信号的波长可以精确测定。因此在式中，主  
243 要的误差来源于右边第1项，并且当该项系数越小，则入射角的标准差越小，该项系数可  
244 用误差比表示。  
15 通过(24)式可知，入射角误差与入射波波长、基线长度和入射角角度有关。设入射波  
16 波长为 $0 . 6 \mathrm { m }$ ，基线长分别为 $0 . 3 \mathrm { m }$ 、 $0 . 6 \mathrm { m }$ 和 $1 . 2 \mathrm { m }$ ，计算结果如图10。

![](images/d3ab1e48d92c90fd14b1c73789b49a93b38cebc7ae807c087b14616052d67042.jpg)  
图10.入射角误差与入射角关系图  
Fig.1O The relationship between incident angle and error

由于(24)式中入射角取值不能为，因此将设定在与的区间内进行计算。根据图10 可知，当基线长度相同，入射角在与之间时，误差比随着方位角的增大而增大，说明此时当目标的实际方位角越大，计算得到的入射角结果误差越大；而当入射角在与之间时，误差比随着入射角的增大而减小，说明此时当目标的实际入射角越大，计算得到的入射角结果误差越小。其次，当入射角确定时，误差比随着基线长度的增加而减小，说明长基线对目标方位角进行测量时的精度更高。最后，当入射角越趋近时，误差比的变化速度急剧增加；当入射角逐渐靠近与时，变化强度趋于缓和，变化的幅度不大。

同样的，当基线长度一定时，可以得到入射角误差与频率之间的关系。为了方便计算，将频率范围设定在 $5 0 0 \mathrm { M H z } { \sim } 1 5 0 0 \mathrm { M H z }$ 。如图11，误差比随着入射波频率的增加而减小。由此可得，利用相位差测向方法对目标的入射角进行测向时，入射波频率越高，方位角测向

260 精度越高。此外，当入射角越靠近方向时，误差比随着频率的变化较为明显，特别是在低  
261 频波段时变化幅度较大，但是随着频率的增加，这种变化趋于平缓；而当入射角靠近或方  
262 向时，误差比随着频率的变化相对不明显。

![](images/eb31cf755d3adb3c5a41cb40bce8830dd76676945ddcf372cc4a61b861fbf2db.jpg)  
图11.入射角误差与频率关系图  
Fig.11 The relationship between incident angle error and frequency

# 5总结

射电干涉技术是天文观测的重要手段之一，依靠这项技术不仅可以对已知或者未知天  
体进行观测，同时也可以对地球轨道上的人造空间目标进行探测。天籁射电阵具有大视场  
与高灵敏度的优点，能够更好地实现对空间目标捕获与探测。通过分析可知，利用天籁射  
电阵与曲靖非相干散射雷达组成的双基地雷达系统有能力探测到低轨道范围内 $1 0 \mathrm { { c m } }$ 以下  
的空间目标，但由于该阵列角分辨率不高，对于较小的空间目标很难通过成像方法得到其  
位置信息。因此本文提出通过长短基线结合的方式，利用相位差测量法对空间目标进行测  
向，并提出了解决在测量与计算中存在的相位模糊问题。同时对测向误差进行分析，得到  
了测向误差与测向角之间的关系。根据文[11]，目前天射电阵已初步具备一定空间目标  
探测实验的可行性条件，本文的研究也可以为今后利用天射电阵进行空间目标探测提供  
了理论依据。  
参考文献  
[1]于欢欢,高鹏骐,沈鸣,等.空间碎片激光测距探测能力分析[J].天文研究与技术,2016,13(4):416-421Yu Huanhuan, Gao Pengqi, Shen Ming, et al. Detection capability analysis of space debris laserranging[J]. Astronomical Research and Technology, 2016,13(4):416-421.  
[2]汪洋,韩长喜.美国“太空篱笆”计划概述[J].现代雷达,2014,36(3):16-18Wang Yang, Han Changxi. Overview of US space fence program[J]. Modern Radar,2014,36(3):16-18  
[3]ShumacherP W J. US naval space surveillance upgrade program 1999-2003[C]/ Proceedingsof. $5 ^ { \mathrm { t h } }$ European Conference on Space Debris. 2009.  
[4]郭伟,崔海英.国外电磁篱笆建设要素分析[J].现代雷达,2010,32(2):31-34.Guo Wei, Cui Haiying. Analysis of dominant construction factors of foreign electromagneticfences[J]. Modern Radar, 2010,32(2):31-34.  
[5]Montebugnoli S_， Salerno E_，PupilloG_, et al.A potential integrated multiwavelength radarsystem at the medicinaradiotelescopes[C]// Proceedings of $5 ^ { \mathrm { t h } }$ European Conference on SpaceDebris.2009.  
[6]Montebugnoli S， Pupillo G_， Salerno E ，et al，The bistatic radar capabilities of themedicinaradiotelescopes in space debris detection and tracking[J]. Advances in SpaceResearch,2010,45(5):676-682.  
[7]金旺,张希亮,杨勇志,等。潜在的 500MHz雷达网及其应用[J].天文研究与技术，2015,12(4):443-446.  
Jin Wang, Zhang Xiliang, Yang Yongzhi, et al. A potential radar network working in the500MHz band and its applications[J]. Astronomical research and technology,2015,12(4):443-446.  
[8]杨振起,张永顺,骆永军.双(多)基地雷达系统[M].北京:国防工业出版社,1998:34-35.  
Yang Zhenqi, Zhang Yongshun, Luo Yongjun. Bistatic(Multistatic) Radar Systems[M].Beijing: National Defense Industry Press: 1998:34-35.  
[9]陈学雷,施浒立.天籁计划：暗能量的射电探测及平方千米阵(SKA)[J].物理,2013,42(1):2-  
11.  
Chen Xuelei, Shi Huli. The Tianlai project: radio detection of dark energy and the SquareKilometer Array[J]. Physics, 2013,42(1):2-11.  
[10]袁孝康.相位干涉仪测向定位研究[J].上海航天,1993(3):1-7.Yuan Xiaokang. Study on dirction-finding and position with phase interferometers[J].Aerospace Shanghai, 1993(3):1-71993(3):1-7.  
[11]刘成，施浒立，陈学雷.利用天籁暗能量观测阵列开展空间目标探测新技术试验[J].宇航  
学报,2017,38(11):1243-1252.Liu Chen ，Shi Huli， Chen Xueleii. A new space target detection technology and itsexperiment by using Tianlaidark energy radio detection array[J]. Journal of Astronautics,2017,38(11):1243-1252.