# 涡轮后机匣流场性能实验研究

冯亚辉刘火星

(北京航空航天大学能源与动力工程学院，航空发动机气动热力国家级重点实验室，北京100191)

摘要对低压涡轮后机匣进行实验研究。对不同来流马赫数及不同来流气流角下的涡轮后机匣流场参数进行测量，分析其在不同来流条件下的整流及损失情况。研究结果表明：支板叶型为前加载且按最大厚度积叠的涡轮后机匣在设计点及非设计点状态都将气流从偏离轴向偏转到基本接近轴向，且总压损失都较小。来流马赫数的改变对后机匣出口气流角影响不大，但来流马赫数的增加会导致其总压损失增加；而来流气流角改变对其出口气流角及总压损失的影响相对较小，但出□气流角及总压损失沿径向的分布会随来流气流角的改变发生变化。

关键词涡轮后机匣；实验研究；流场；性能中图分类号：V231.3 文献标识码：A 文章编号:0253-231X(2017)05-0941-09

# Experimental Research on Flow Field and Performance of Turbine Rear Frame

FENG Ya-Hui LIU HuXing (National KeyLaboratoryof Scienceand Technologyon Aero-EngmesAero-Thermaldynamics,SchoolofEnergyandPower Engineering, Beihang UniversityBeijing 100191, China)

AbstractExperimental research on the_tubine rear frame(TRF） was conducted. The flow field parameters were measured in diferent inletMach numbers and different inlet flow angles to analyze the angle rectification ability and thelss of the turbine rear frame. The research results show that the turbine rear frame whose bladprofile has an extreme front loaded pressure distribution and is stacked at maximum thicknessCan turn the flow angle from the deflected axial direction to the axial direction and has little total pressure loss on the design point and off the design point. The change of the inlet Mach number has litle efect on the outlet fow angle,but the increase of the inlet Mach number can lead to the increase of the total pressure loss. Moreover,the change of the inlet flow angle has relatively litte impact on both the outlet flow angle and tle total pressure loss, but the radial direction distribution of the outlet flow angle and total pressure loss will change when the inlet flow angle changes. etp

Key wordsturbine rear frame; experimental research; flow field; performance

# 0引言

航空发动机经济性和高性能的设计目标要求涡轮部件采用更少的级数以及承受更高的负荷，导致低压涡轮出口气流有更大的预旋，也就意味着涡轮后机匣的进口气流条件更加恶劣，这对涡轮后机匣的气动性能提出了更高的要求。涡轮后机匣(TurbineRearFrame，TRF，以下简称后机匣）是发动机承力系统的一部分，用于支撑低压转子，同时连接低压涡轮和尾喷管构成气流通道的一部分。后机匣结构上包括轮毂，机匣和内置的整流支板(OutletGuideVane，OGV)。整流支板的作用包括支撑、提供管道通路及整流。从气动角度上，整流支板主要作用是在付出尽可能小的总压损失代价下将低压涡轮出口气流转为轴向，同时要求在较为宽广的工况范围内无流动分离。

国外对涡轮后机匣进行了大量的研究工作并取得了较好的效果。瑞典Chalmers 理工大学搭建了一套专用于涡轮后支板流动研究的低速叶栅试验台[1]，研究了不同湍流模型对涡轮后支板数值模拟结果的影响[2-3]。PW 公司与美国空军合作，采用非系列叶型代替标准系列叶型来对涡轮后支板进行了气动设计[4]，发现非系列叶型在达到设计要求的前提下，其静压升系数较原型有所增大，而总压损失有明显降低。Sonoda等[5]通过调整叶片的负荷分布进行了涡轮后支板叶栅的设计，认为在低雷诺数下采用“超前加载”的负荷分布形式有利于叶片的气动性能。Koch等[]通过调整叶型和栅距对涡轮后支板叶栅进行了改型设计，发现改型叶栅的损失几乎在整个工作范围内均明显小于原型Chalmers大学的Skoog开发了可实现后支板叶型设计、积叠、子午流道设计修改、计算网格生成及二、三维数值模拟一体化功能的后支板气动设计软件Volvane[7]。Chalmers大学研究了非设计点状态对涡轮后支板的流动和损失的影响[2]，发现在非设计点下后支板的流动损失均大于设计点，转角增大的工况其流动损失有显著的提升。Hjarne等[8]研究了吊挂对后支板流动和损失的影响，发现吊挂在很大程度上影响了流场内的二次流发展。Chernoray 等[9」研究了支板表面几何形变对后机匣流动及性能的影响，发现几何形变的位置对流动影响最大，应当竭力避免出现形变的位置是支板吸力面前缘吸力峰附近处。国内对涡轮后机匣设计及流场研究相对较少，主要利用数值模拟手段来开展研究。北航闫晨[10]分析了湍流模型、网格密度、转捩模型和来流边条等计算参数对后支板数值模拟的影响。北航张颜[11]根据给定的条件对涡轮后机匣进行了设计研究，其设计的两种后机匣方案在给定的条件下均满足设计要求，气流接近轴向，同时损失较小。

本文利用实验的手段对涡轮后机匣流场性能进行研究，分析了后机匣在设计点及非设计点状态的整流及损失情况，以及不同的来流马赫数及来流气流角对后机匣气动性能的影响，为涡轮后机匣设计及流场数值模拟提供支持。

为 $2 9 8 . 9 \ \mathrm { m m }$ ，叶高为 $8 0 ~ \mathrm { m m }$ 。后机匣叶片如图3所示，支板长度为 $1 2 0 . 8 \ \mathrm { m m }$ ，支板弦长为 $1 6 0 ~ \mathrm { { m m } }$ ，最大厚度 $\mathrm { 2 4 ~ m m }$ ，支板叶型为前加载方式并采用最大厚度进行积叠。后机匣设计进口流量为 $5 8 . 3 7 ~ \mathrm { k g / s }$ 现有试验台最大流量为 $1 1 ~ \mathrm { { k g / s } }$ ，全压 $1 5 0 0 0 \ \mathrm { P a }$ 需进行扇形段实验，扇形段出口为 $1 4 0 ^ { \circ }$ ，大于六个通道周期。对于扇形段试验，后机匣在几何上保证支

![](images/7301e5b821a8db783ac10bb3b27be5a1360d91c63bc0802f73ee35f093669526.jpg)  
图1后机匣环形叶栅实验台 Fig.1 TRF annular experimental system

# 1 实验装置

# 1.1 实验台

实验在北京航空航天大学的后机匣环形叶栅实验台上完成的，实验台如图1所示。该试验台由六部分组成：气源、扩张段、稳定段、收敛段、导流段和测试段。气源是由一台离心式风机提供，额定功率 $2 2 0  { \mathrm { k W } }$ ，空气流量 $3 5 0 0 0 \mathrm { { m } ^ { 3 } / h }$ ，全压 $\mathrm { 1 5 0 0 0 P a }$ 工作。风机提供的空气经扩张段流入稳定段。稳定段后接一个圆变扇段，由圆形通道变成扇形通道，见图1中收敛段1。然后经一段收敛段将流道收缩成更小的扇形通道，可保证气流均匀收敛，见图1中收敛段2。测试段前接有导流段，装有导流叶片用来调整来流角度。

![](images/7ee07b2df48b85121b22d778a5ed65bdea76018c1774eeb1521e2d9f3838e9c6.jpg)  
图2后机匣试验件Fig.2 TRF test article

# 1.2 实验件

![](images/f808ab4dd1158371161fd16420bc5c126816fe76fa7dbbd470e15c73642a1413.jpg)  
图3后机匣叶片Fig.3 TRFblade

后机匣试验件如图2所示，试验件为全环，支板数目为16，无倾斜，轮毂半径为 $2 1 8 . 9 \mathrm { m m }$ ，机匣半径板稠度、展弦比、轮毂比参数，在气动上保证后机匣平均进口 $\ b { M a }$ 数以及平均进口气流角。经计算，扇形试验设计点后机匣进口流量约为 $8 ~ \mathrm { { k g / s } }$ ，小于试验台最大流量 $1 1 ~ \mathrm { k g / s }$ ，在试验台允许范围内。

# 1.3测试方案

在设计点状态下，测量后机匣进出口截面处总压、静压和速度分布，后机匣支板表面压力分布。在非设计点状态下，分别改变来流马赫数和来流气流角，对后机匣流场进行相同的测量。

后机匣进出口截面处总压、静压和速度分布测量用气动五孔探针来完成。五孔探针测得的压力由压力管引出到压力传感器，再将数据传输到数据采集软件进行数据采集。

对于后机匣进口截面流场测量，将测点布置在导流段上靠近出口处，在导流叶片后法向开孔保证探针通过。对于后机匣出口截面测量，利用位移机构控制两自由度移动来实现，测量范围大于一个栅距，在尾迹及端壁区对测点进行加密，出口截面测点布31列，共961个测点。

置18个测点。支板叶片的吸力面及压力面静压孔布置分别如图5、图6所示。

![](images/4373756b754950bebba6d706adcc82358040541026f061f883a9c43aaa8bdf50.jpg)  
图6叶片压力面静压孔

# 2实验结果分析

在不同的来流条件下，对后机匣内流场进行了测量，并对实验结果进行了处理，得到了后机匣在设计点及非设计点时的整流及损失情况，以及来流条件对后机匣性能的影响。

# 2.1后机匣设计点状态性能分析

本文总压恢复系数 $\sigma$ 定义如式（1）所示，其中$P _ { \mathrm { { t } } }$ 为当地总压， $P _ { \mathrm { t , i n } }$ 为进口总压。

![](images/4bf6571b1ac95973240f5b60cff9b070ef494b331e6fc3cc1696ea5c0a2e2131.jpg)  
图4出口截面测点布置

$$
\sigma = { \frac { P _ { \mathrm { t } } } { P _ { \mathrm { t , i n } } } }
$$

本文气流角 ${ \bf \Delta } _ { \mathrm { \Delta \omega } } ^ { \sf C }$ 的定义如图7所示。

![](images/cc7d363fe944420c84081aebb2a83fd7960a49f388553ecbcd30b7d8cc1e8940.jpg)  
Fig.6 Static pressure hole ofblade pressure surface   
图7气流角定义 Fig.7Flow angle definition

![](images/611ed7ef9b0fd16386c69ef8d6755006b51ef89a791ede27df1ec889d6c4bac9.jpg)  
Fig.4 Measuring point layout of outlet section   
图5叶片吸力面静压孔  
Fig.5 Static pressure hole of blade suction surface

后机匣支板表面静压的测量通过在支板表面布置静压孔来完成。支板表面布置的静压孔，由压力管引出到压力扫描系统，然后由计算机软件完成数据采集。在支板表面 $1 0 \%$ ， $5 0 \%$ ， $9 0 \%$ 叶高处布置静压孔，支板吸力面及压力面测点分布在两个不同支板上以减小测点布置难度，不同叶高轴向方向上布

通过对实验数据的处理，得到设计点状态下后机匣进口流场参数如表1所示，出口流场参数如表2 所示。各流场参数均为流量平均后的结果。

从表1中可以看出，在设计点时，后机匣实验件进口平均马赫数为0.363，进口平均气流角为109.4度；从表2中可以看出，设计点后机匣出口平均马赫数为0.358，出口平均气流角为 $8 8 . 6 ^ { \circ }$ 。经过后机匣试验件，气流速度变小，说明气流在后机匣通道内有一定程度的扩压。经过后机匣，气流偏转角度为 $2 0 . 8 ^ { \circ }$ 。总压恢复系数为后机匣出口流量平均总压除以后机匣进口流量平均总压，为0.993。实验结果表明，在设计点时，该后机匣试验件将气流从偏离轴向 $1 9 . 4 ^ { \circ }$ 偏转到基本接近轴向，且气流的总压损失较小。

Table1 Inlet parametersof TRF in the design point   
表2后机匣设计点出口参数  

<html><body><table><tr><td>condition</td><td>Ma</td><td>α/(）</td></tr><tr><td>1</td><td>0.363</td><td>109.4</td></tr></table></body></html>

表1后机匣设计点进口参数  
Table2 Outlet parametersof TRF in the design point   

<html><body><table><tr><td>condition</td><td>Ma</td><td>α/()</td><td>0</td></tr><tr><td>1</td><td>0.358</td><td>88.6</td><td>0.993</td></tr></table></body></html>

设计点状态下，后机匣进出口气流角沿径向分布如图8所示。其中“1_in”代表设计点状态进口，“1_out”代表设计点状态出口。可以看出，设计点状态下，后机匣进口气流角在 $2 0 \%$ 叶高以上分布较为均匀，在 $2 0 \%$ 叶高以下出现小的波动；后机匣出口气流角在 $2 0 \%$ 叶高以上分布较为均，出口气流角接近轴向；在 $2 0 \%$ 叶高以下，出气流角出现波动，稍微偏离轴向。后机匣进、出气流角分布趋势基本一致。这表明，后机匣出口气流角沿径向分布受进口气流角分布影响较大伺时，在后机匣支板靠近下端壁处，出口气流角分布波动相对较大，这一方面是受进口气流角分布的影响，另一方面由于后支板下端与机匣下端壁装配时存在缝隙，导致支板下端靠近端壁处二次流较为严重，进而使支板下端的出口气流角分布波动较大。

![](images/55f5d767f876ca7bed01b09fc560e41fecebe54cd2d48331dcc2a5c6fb9bf781.jpg)  
图8 设计点进出口气流角沿径向分布 Fig.8 Inlet and outlet flow angle distribution in the design point

设计点状态下，后机匣总压恢复系数沿径向分布如图9所示。设计点状态下，后机匣总压恢复系数在 $2 0 \%$ 叶高以上、 $7 5 \%$ 叶高以下沿径向分布较为均匀，波动较小；在 $2 0 \%$ 叶高以下、 $7 5 \%$ 叶高以上，总压恢复系数分布波动较大，且总压恢复系数较小。这是由于后机匣在上下端壁存在边界层损失，以及后支板靠近上下端壁处存在端壁二次流损失，导致后机匣在上、下端壁附近总压损失较大且总压分布波动较大。同时，在后机匣 $8 0 \%$ 叶高附近以及 $1 0 \%$ 叶高附近出现了总压损失分布转折点，总压损失相对附近区域较大，这说明在转折点处二次流较严重，总压损失较大。

![](images/2767eeadc90a8bb21e3637ee6498c567616d3e6a0b04437e537098545bcfb4d1.jpg)  
图9设计点总压恢复系数沿径向分布 Fig.9 Total pressure recovery coefficient distribution in the 1 design point

后机匣支板表面静压系数 $C _ { \mathrm { p } }$ 定义如式（2）所示，其中 $P _ { \mathrm { s } }$ 为静压， $P _ { \mathrm { s , i n } }$ 为进口静压， $P _ { \mathrm { t , i n } }$ 为进口总压。

$$
C _ { \mathrm { p } } = ( P _ { \mathrm { s } } - P _ { \mathrm { s , i n } } ) / ( P _ { \mathrm { t , i n } } - P _ { \mathrm { s , i n } } )
$$

设计点状态下，后机匣支板表面静压分布如图10所示。图例中0.1、0.5、0.9分别代表 $1 0 \%$ 叶高位置、 $5 0 \%$ 叶高位置、 $9 0 \%$ 叶高位置，suc代表吸力面，pre代表压力面。例如，0.1_suc代表支板 $1 0 \%$ 叶高位置吸力面的静压系数分布，以此类推。设计点状态下，在不同的叶高位置，支板表面的静压分布都呈现出明显的前加载趋势，支板压力面的分布趋势基本相同，支板吸力面的分布在 $4 5 \%$ 轴向弦长位置以前分布差异较大，在 $4 5 \%$ 轴线弦长位置以后分布基本相同。其中， $5 0 \%$ 叶高位置的支板吸力面的逆压梯度更小，流动也更加均匀；在 $1 0 \%$ 叶高位置，支板吸力面在 $3 0 \%$ 轴向弦长位置处出现了较大的逆压梯度；在 $9 0 \%$ 叶高位置，支板吸力面在 $3 5 \%$ 轴向弦长位置处出现了较大的逆压梯度。实验结果表明：不同的叶高位置，支板负荷分布呈现前加载特征；不同叶高位置的支板压力面静压分布受上、下端壁二次流影响较小，分布趋势基本相同；不同叶高位置的支板吸力面静压分布受上、下端壁二次流的影响较大，从而导致在支板吸力面靠近上下端壁处的不同轴向位置处出现了较大的逆压梯度。

从图11中可以看出，在设计点状态下，后机匣出口总压在支板尾迹区较小。这是由于气流在流过支板后产生了尾迹损失以及尾迹和主流互相掺混产生了掺混损失，从而使出口截面尾迹区的总压损失较大。同时，出口总压在靠近下端壁的支板尾迹区范围明显较大且总压较小，这说明该区域尾迹和主流掺混比较厉害，二次流较为严重；这是由于装配时支板下端和后机匣下端壁存在缝隙，使靠近支板下端处二次流较严重，总压损失较大。而且，后机匣出口总压在上、下端壁附近数值较小，总压损失较大，这说明由于壁面边界层的影响，端壁二次流的损失较大，从而使该区域总压损失较大。

![](images/a0a99b7e75c559b514d6d572b4386478c68bf5079fc8f3e15fbb26ec2677743b.jpg)  
图10不同叶高位置支板表面静压分布

设计点状态下，后机匣出口马赫数云图如图12所示。可以看出，设计点状态下，后机匣出口马赫数在支板尾迹区明显较小，且在靠近支板下端的尾迹区范围较大，同时在上、下端壁附近，出口马赫数较小这表明，由于靠近支板下端存在装配缝隙，尾迹和二次流互相掺混，使下端尾迹区的范围更大，速度亏损也更大；在后机匣上、下端壁附近由于壁面边界层及二次流的影响，速度较小。

设计点状态下，后机匣出口总压系数分布云图如图11所示。总压系数 $C _ { \mathrm { p , t } }$ 的定义如式（3）所示，其中 $P _ { \mathrm { t . o u t } }$ 为出口总压， $P _ { \mathrm { t - o u t - a v e } }$ 为出口截面平均总压。

$$
C _ { \mathrm { p t } } = P _ { \mathrm { t . o u t } } / P _ { \mathrm { t . o u t . a v e } }
$$

![](images/2360b7bc82b57d845f81e9a3dc9102bccab20b4d33e28cc2293751821a78e128.jpg)  
Fig.10 Blade surface static pressure distrbution in different blade height positimsy   
图12设计点出口马赫数云图  
Fig.12 Outlet Mach number distribution in the design point

![](images/e38b47bc3717247ee241e1cad8af5996f00dc861c24dee95f9a491d084073e36.jpg)  
图11设计点出口总压系数云图  
Fig.11 Outlet total pressure coefficient distribution in the design point

设计点状态下，后机匣出口气流角云图如图13所示。可以看出，设计点状态下，后机匣出口气流角分布较为均匀，除了后支板下端尾迹区以及后机匣上下端壁处气流角稍微偏离轴向，其余区域气流角都接近轴向，且变化范围不大。在上、下端壁处，端壁二次流的存在导致端壁区附近后机匣出口气流角稍微偏离轴向。在支板下端尾迹区由于装配缝隙的存在，气流偏离轴向稍大。

# 2.2来流马赫数对后机匣流动及性能的影响

实验在保证来流气流角不变的情况下，分别改变来流马赫数，来研究不同的来流马赫数对后机匣

流动及性能的影响，本文中分别对应实验工况的1、2、3。实验所测得的工况1、2、3后机匣进口参数如表3所示，后机匣出口参数如表4所示。

![](images/49e27393c9a4e350ea98e4514ea0b5f4e9ee9694c1d0540038b12cc8420b5be6.jpg)  
图13设计点出口气流角云图 Fig.13 Outlet flow angle distribution in the design point

# 表3工况1、2、3后机匣进口参数

Table 3 Inlet parameters of TRF under thcondition 1,2,3 电学  
表4工况1、2、3后机匣出口参数  

<html><body><table><tr><td>condition</td><td>Ma</td><td>wxe</td></tr><tr><td>1</td><td>0.363</td><td>109.4 程热</td></tr><tr><td>2</td><td>0.417</td><td>109.4</td></tr><tr><td>3</td><td>0.314</td><td>109.4</td></tr><tr><td></td><td>厂</td><td></td></tr></table></body></html>

Table 4 Outlet parameters of TRF under the condition 1,2,3   

<html><body><table><tr><td>condition</td><td>Ma</td><td>α/(</td><td></td></tr><tr><td>1</td><td>0.358</td><td>88.6</td><td>0.993</td></tr><tr><td>2</td><td>0.412</td><td>88.7</td><td>0.990</td></tr><tr><td>3</td><td>0.305</td><td>88.3</td><td>0.996</td></tr></table></body></html>

从表3及表4中可以看出，在不同来流马赫数下，后机匣出口气流角变化不大，基本接近轴向；这说明，后机匣在不同马赫数下都可以将气流偏转到接近轴向。即来流马赫数的改变对出口气流角影响不大。从表中还可以看出，随着来流马赫数的增加，后机匣总压恢复系数呈现减小趋势，这说明随着来流马赫数的增加，后机匣内所产生的总压损失增加。这表明，马赫数的增加会使后机匣内部的叶型损失和二次流损失增加，从而导致总压损失增加。

工况1、2、3下，后机匣进出口气流角沿径向分布如图14所示。可以看出，不同的来流马赫数下，后机匣进、出口气流角沿径向分布基本相同，出口气流角均基本偏转到轴向。这再次说明，马赫数的改变对该后机匣的整流能力基本没有影响。

![](images/a372a0da048eeccc2b01cc3fddf413ab4d86f74acb9d6a934f8aa6ccab7708c4.jpg)

况1、2、3下，后机匣总压恢复系数沿径向分布如图 15所示。可以看出，不同的来流马赫数下，后机匣总压恢复系数沿径向分布趋势基本相同，即在中间叶高附近总压恢复系数较大，上下端壁附近总压恢复系数较小。随着来流马赫数增加，总压恢复系数沿径向分布波动变大，分布更不均匀。尤其是在上下端壁附近，总压恢复系数随着马赫数增加波动更加明显。这表明随着马赫数增加，端壁二次流损失增加。从图中还可以看出，在 $7 0 \%$ 叶高处，随着马赫数增加，总压恢复系数基本相同，从 $7 0 \%$ 叶高处开始往上、，总压恢复系数都随着马赫数的增加而减小而且，靠近后支板下端总压恢复系数对马赫数变化反应更加明显，这也再次说明，支板下端的装配缝隙导致的端壁二次流随着马赫数增加更加严重，所造成的总压损失也随着马赫数的增加而增大。

![](images/cf95ea4cc735ab789d07dc325d482494997774c8b314cdca55505eaa8421f59e.jpg)  
图14不同工况进出口气流角沿径向分布 Fig.14 Inlet and outlet flow angle distribution under different conditions   
图15不同工况总压恢复系数沿径向分布 Fig.15 Total pressure recovery coefficient distribution under different conditions

工况1、2、3下，后机匣支板表面静压系数在$1 0 \%$ 叶高、 $5 0 \%$ 叶高、 $9 0 \%$ 叶高处沿轴向分布分别如图$1 6 { \sim } 1 8$ 所示。图例0.1_suc_1代表工况1支板 $1 0 \%$ 叶高吸力面的静压系数分布，以此类推。

![](images/a5840105f7a070523424385b54afa51e53cd7367af4ccbba0b9109c8503840e8.jpg)  
图16不同工况 $1 0 \%$ 叶高处支板表面静压分布 Fig.16 Blade surface static pressure distribution in $1 0 \%$ blade height under different conditions X

![](images/f961bebff01d9c36cb0d8359f2f2e0c18c773ea7032bf114011fee07c5e572ea.jpg)  
图17不同工况 $5 0 \%$ 叶高处支板表面静压分布 Fig.17 Blade surface static pressure distribution in $5 0 \%$ blade height under different conditions

从图 $1 6 { \sim } 1 8$ 中可以看出，不同叶高处表面静压系数的分布趋势随马赫数的改变基本不变。不同马赫数下，压力面表面静压系数变化相对较小，吸力面表面静压系数变化相对较大，尤其是在 $1 0 \%$ 叶高处吸力面表面静压系数变化相对明显，这是由于后机匣支板下端二次流较为严重导致的。

# 2.3来流气流角对后机匣流动及性能的影响

实验在保证来流马赫数不变的情况下，分别改变来流气流角，来研究不同的来流气流角(即不同攻角)对后机匣内部流动及性能的影响，本文中分别对应实验工况的1、4、5。实验所测得的工况1、4、5后机匣进口参数如表5所示，后机匣出口参数如表6所示。可以看出，后机匣进口平均气流角为正攻角$( + 2 . 9 ^ { \circ } )$ 时，出口平均气流角与设计点出口平均气流角相比差别较小，为 $1 . 1 ^ { \circ }$ ；进口平均气流角为负攻角 $( - 7 . 5 ^ { \circ } )$ 时，出口平均气流角与设计点出口平均气流角相比差别稍大，为 $1 . 8 ^ { \circ }$ ；无论进口平均气流角为正攻角还是负攻角，后机匣出口平均气流角虽较设计点出口平均气流角稍微偏离轴向，但变化较小，出口平均气流角基本接近轴向，这说明后机匣的整流能力受攻角变化影响较小。从表中还可以看出，进口平均气流角为正、负攻角时，后机匣总压恢复系数都与设计点状态基本相同，这说明在一定范围内，来流气流角的改变对后机匣的总压损失影响较小。

![](images/cdf61c9a6dbc54ed99415dbcd1f82af8a5bae8193f6c0c41d8c9548570ea9576.jpg)  
图18不同工况 $9 0 \%$ 叶高处支板表面静压分布 Eig.18 Blade surface static pressure distribution in $9 0 \%$ blade height under different conditions

# 表5工况1、4、5后机匣进口参数

Table 5 Inlet parameters of TRF under the condition 1,4,5   
表6工况1、4、5后机匣出口参数  

<html><body><table><tr><td>condition</td><td>Ma</td><td>α/()</td><td>attack angle/(°)</td></tr><tr><td>1</td><td>0.363</td><td>109.4</td><td>0</td></tr><tr><td>4</td><td>0.363</td><td>112.3</td><td>+2.9</td></tr><tr><td>5</td><td>0.363</td><td>101.8</td><td>-7.5</td></tr></table></body></html>

Table 6 Outlet parameters of TRF under the condition 1,4,5   

<html><body><table><tr><td>condition</td><td>Ma</td><td>α/()</td><td>0</td></tr><tr><td>1</td><td>0.358</td><td>88.6</td><td>0.993</td></tr><tr><td>4</td><td>0.362</td><td>87.5</td><td>0.994</td></tr><tr><td>5</td><td>0.364</td><td>86.8</td><td>0.993</td></tr></table></body></html>

工况1、4、5下，后机匣进出口气流角沿径向分布如图19所示。

![](images/9c0fde560ee51c9b2dde5a4fe0b87641e94249cccd86931a9a1be47ad11d025e.jpg)  
图 19不同工况进出口气流角沿径向分布Fig.19 Inlet and outlet flow angle distribution underdifferent conditions

从图19中可以看出，在不同的来流气流角条件下，后机匣出口气流角沿径向分布非常接近在正、负攻角来流条件下，后机匣出口气流角均比设计点状态出口气流角偏离轴向较多。相比面言，负攻角来流条件由于负攻角数值较大,相比正攻角来流条件出口气流角沿径向分布偏离轴向稍多。从图中还可以看出，不同工况下后机匣出口气流角沿径向分布受进口气流角沿径向分布影响很大。在不同的来流气流条件下，后机匣出口气流角在 $2 0 \%$ 叶高以上沿径向分布较为均匀，在 $2 0 \%$ 叶高下，受来流气流条件以及端壁二次流的影响，后机匣出口气流角沿径向出现小的波动，偏离轴向较多。从整体上来说，在不同的来流气流角条件下，后机匣出口气流角沿径向分布都基本接近轴向，这再次说明，在一定范围内，后机匣的整流能力受攻角改变影响很小。

工况1、4、5下，后机匣总压恢复系数沿径向分布如图20所示。

从图20中可以看出，不同的来流攻角下，后机匣总压恢复系数在 $4 0 \%$ 叶高以上沿径向分布相差不大；在 $4 0 \%$ 叶高以下，来流正负攻角时均存在总压损失较大的转折点，且都位于 $3 0 \%$ 叶高左右。这说明，不同的来流攻角下，后机匣的总压损失沿径向分布会发生变化，且变化主要位于 $4 0 \%$ 叶高以下。同时，不同来流气流角下，后机匣上、下端壁附近的总压损失分布变化不大。这表明，在一定范围内，后机匣端壁的边界层损失、二次流损失等受来流气流角的改变影响也很小。

![](images/bd8b15064cf3cdab5b404ad0fb94955a00c41207c7422540272248ff321e53d5.jpg)  
图20不同工况总压恢复系数沿径向分布

Fig.20 Total pressure recovery coefficient distribution under 物 different conditions

工况1、4、5下，后机匣支板表面静压系数在$\dot { 1 0 \% }$ 叶高、 $5 0 \%$ 叶高、 $9 0 \%$ 叶高处沿轴向分布分别如图 $2 1 { \sim } 2 3$ 所示。

从图 $2 1 { \sim } 2 3$ 中可以看出，不同叶高支板表面静压系数的分布趋势随攻角的改变基本不变。不同攻角下，受上下端壁二次流的影响，在 $1 0 \%$ 叶高及$9 0 \%$ 叶高处，后支板吸力面均在不同的轴向位置处出现了较大的逆压梯度。同时，在正攻角状态下，不同叶高处的压力面静压系数均比设计点高，吸力面的逆压梯度比设计点偏大；在负攻角状态下，不同叶高处的吸力面静压系数均比设计点高，同时吸力面的逆压梯度也比设计点要小。

![](images/ca1e6c0bebbbfda0908f01481049b9386c0dd0203db315040d545c9cf2cf3073.jpg)  
图21不同工况 $1 0 \%$ 叶高支板表面静压分布  
Fig.21 Blade surface static pressure distribution in $1 0 \%$ blade height under different conditions

![](images/7a6ebdeb4819606e26037717720aa5b68b6d497344fead3830e423e0cded82c2.jpg)  
图22不同工况 $5 0 \%$ 叶高支板表面静压分布Fig.22 Blade surface static pressure distribution in $5 0 \%$ blade height under different conditions  
图23不同工况 $9 0 \%$ 叶高支板表面静压分布Fig.23 Blade surface static pressure distribution in $9 0 \%$ （204号blade height under different conditions

1.6 0.9_pre_1 1.2 —0.9_suc_1 0.8 ·—0.9_pre_4 O—0.9_suc_4 0.4 ▲—0.9_pre_5 0.0 △—0.9suc 5 1 C²-0.4 L -0.8 □ -1.2 O- 程热物理学 -1.6 -2.0 -2.4 0.00.10.20.30.40.50.60.70.80.91.0 Axial position

# 3结论

本文通过实验的手段分析了涡轮后机匣在设计点及非设计点状态下的整流及损失情况，同时分析了不同来流马赫数以及不同来流气流角下对后机匣内流动及性能的影响，得出以下结论：

1)支板叶型为前加载且按最大厚度积叠的涡轮  
后机匣在设计点及非设计点状态都将气流从偏离轴  
向偏转到基本接近轴向，且总压损失都较小。2)来流马赫数的改变对后机匣出口气流角影响  
不大，但来流马赫数的增加会导致其总压损失增加，  
且其沿径向分布更不均匀。3)来流气流角改变对其出口平均气流角及总压  
损失的影响都相对较小。但出口气流角及总压损失  
沿径向的分布会随来流攻角的改变发生变化4)支板压力面静压分布受端壁二次流影响较小,  
支板吸力面静压分布受端壁二次流影响较大，支板

吸力面靠近上下端壁的不同轴向位置处出现了较大的逆压梯度。不同叶高支板表面静压系数的分布趋势随马赫数的改变基本不变，不同叶高支板表面静压系数的分布趋势随来流攻角的改变变化很小。

# 参考文献

[1] Hjärne J,Larsson J,Lofdahl L.Design of a Modern TestFacility for LPT/OGV flows [C]//ASME Turbo Expo 2003,Collocated With the 2Oo3International Joint Power Generation Conference.American Society of Mechanical Engineers,2003:137-145   
[2] Hjarne J，Larsson J，Lofdahl L. Performance and Off-design Characteristics for Low Pressure Turbine Outlet Guide Vanes:Measurements and Calculations [C]//ASME Turbo Expo 2006: Power for Land, Sea, and Air．American Society of Mechanical Engineers,2006: 649-658   
[3]Hjarne Chernoray V,Larsson J,et al．An Experimental Investigation of Secondary Flows and Loss Development Downstream of a Highly Loaded Low Pressure Turbine Outlet Guide Vane Cascade [C]//ASME Turbo Expo 2006:Power for Land, Sea,and Air. American Society of Mechanical Engineers, 2006: 681-690   
[4] Monello JA, Mitchell W S, Tall WA.Application of Nonseries Airfoil Design Technology to Highly Loaded Turbine Exit Guide Vanes [J]. Journal of Engineering for Power, 1979,101(1): 202-211   
[5] Sonoda T,Schreiber H A，Arima T.Endwall Performance of Outlet Guide Vane Cascades With Different Blade Loading Distributions [C]//ASME Turbo Expo 2008:Power for Land, Sea,and Air.American Society of Mechanical Engineers, 2008:601-615   
[6] Koch H,Kozulovic D,Hoeger M. Outlet Guide Vane Airfoil for Low Pressure Turbine Configurations [C]//42nd AIAA Fluid Dynamic Conference and Exhibit, 2012: 2979   
[7] SkoQg JA. Investigation and Evaluation of the Volvo Aero Tool Volvane for Outlet Guide Vane Design [D].Gothenburg:Chalmers University of Technology, 2012   
[8] Hjärne J,Chernoray V,Larsson J.Experimental Investigations and Numerical Validation of an Outlet Guide Vane With an Engine Mount Recess [C]//ASME Turbo Expo 2008:Power for Land,Sea,and Air.American Society of Mechanical Engineers, 2008:989-998   
[9] Chernoray V,Ore S,Larsson J. Effect of Geometry Deviations on the Aerodynamic Performance of an Outlet Guide Vane Cascade [C]//ASME Turbo Expo 2010: Power for Land, Sea,and Air. American Society of Mechanical Engineers,2010:381-390   
[10]闫晨.大涵道比涡扇发动机涡轮若干问题研究[D].北京：北 京航空航天大学，2013 Yan Chen. Research on Some Issues About High Bypass Ratio Turbofan Engine Turbine [D].Beijing: Beihang University, 2013   
[11] 张颜.涡轮过渡段内部流动和性能研究[D].北京:北京航空 航天大学，2014 Zhang Yan. Internal Flow and Performance Research on the Intermediate Turbine Duct [D].Beijing: Beihang University,2014