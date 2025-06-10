# 基于四天线线阵的无线电干扰源来波方向的测试研究

刘道睿'，苗晟1，董亮²，王晓瑞'，田斌³，李升阳³，郭少杰²(1.西南林业大学大数据与智能工程学院，云南昆明650051)(2.中国科学院天体结构与演化重点实验室，云南昆明650051)（3.云南省无线电监测中心，云南昆明，650228）

摘要：本文针对射电天文观测中对周边电磁环境宁静区检测方法的不足，提出一种基于四天线线阵进行无线电干扰监测的方法，目的在于实时监测电磁宁静区有无干扰源并对干扰源的来波方向进行辨识。方法是采用便携式四天线阵布成线阵，使用线性阵列的MUSIC算法来计算干扰源来波方向。通过在室内和室外的不同距离和条件下进行测试，结果在相对空旷宁静的环境，四天线阵能够有效辨识干扰信号的来波方向，测量角度误差不超过 $5 ^ { \circ }$ 的可靠性约为$8 7 \%$ 。经过综合分析，本文得出采用便携式四天线线阵方式结合MUSIC算法在空旷区射电天文观测中能够较好辨识干扰源来波方向，有助于帮助射电望眼镜避开受干扰信道。

关键词：电磁环境监测 射电天文观测 无线电测向MUSIC 测向技术中图分类号：P165 文献标识码：A 文章编号：

# Research on Measurement of Radio Interference Source Based On Four-antenna Line Array

Daorui Liu, Sheng Miao, Liang Dong, Xiaorui Wang .College of Big Data and Intelligent Engineering, Southwest Forestry University, Kunming 650051, China 2.Key Laboratory for the Structure and Evolution of Celestial Objects, Chinese Academy of Sciences Yunnan Kunming, CO 650011 China

Abstract: Aiming at the deficiency of the detection method of the quiet area of the surrounding electromagnetic environment in radio astronomical observation， this paper proposes a radio interference monitoring method based on four antenna linear array. The purpose is to monitor whether there are interference sources in the quiet area in real time and identify the incoming direction of the interference sources.The method is to use the portable four antenna array to form a linear array,and use the music algorithm of the linear array to calculate the incoming wave direction of the interference source. Through the test under different distances and conditions indoors and outdoors,the results show that in a relatively open and quiet environment, the four antenna array can effectively identify the incoming direction of the interference signal,and the reliability of the measurement angle error of no more than $5 ^ { \circ }$ is about $87 \%$ . After comprehensive analysis,it is concluded that the portable four antenna linear array combined with music algorithm can better identify the direction of the incoming wave of the interference source in the radio astronomical observation in the open area, which is helpful to help the radio telescope avoid the disturbed channel.

Key words: Electromagnetic environment monitoring; Radio astronomical observations; Radio

# 0引言

射电天文观测电测环境宁静有较高的要求，而随着社会的发展，各地电测环境变得越来越复杂，给射电天文的观测带来极大的挑战。

在日益复杂的电磁环境中，主要还是人为制造的发射源发射的电磁波。比较典型的主要有：民用航天信号（Civil Aviation Signal，CAS)，各类通信基站，大功率信号发生器等。这些干扰源的发射频率和射电天文观测频率会发生重叠，从天线旁瓣进入接收机系统，进而降低系统灵敏度，影响观测数据的有效性，增加数据处理的复杂性，严重时甚至直接污染射电天文在此频段内的观测数据，使得大型射电科学仪器在该时空段内无法进行观测。

针对目前越来越复杂的电磁环境，射电天文的观测前一般需要在观测中对观测区域的电磁环境进行检测，通过不断调整射电望远镜的观测区域从而在特定时段和空域中达到暂时有效的观测宁静区。但想要达到这个效果，则需要我们利用无线电测向技术，提前预测干扰源的来波方向，从而有针对性的进行规避。

无线电测向技术是十分重要的无线电应用热点，一般在远场范围内，通过放置多天线来构建天线阵，再结合使用达到时间差技术就可以确定来波方向。如果采用更多天线布成天线阵，则可以有效提高测量精度。目前有不少文献提出相关的应用。

例如文献[中提出一种方法，即通过航空信号位置信号估算了飞机到测站距离，评估了航空信号到测站的功率损耗，通过分析，从而确定航迹分布在已划定区域范围内的概率以减少CAS 信号的影响。文献2中用五阵元天线圆阵天线作为接收天线,接收来波信号,用双通道干涉仪作为接收机将信号送入处理单元,通过实时建立相位差样本库,减小了样本库的规模,确定信号的来波方向。文献中对空管设备环境的电磁信号进行采集与测量,计算频域、时域的参数特性,结合地理信息等数据融合，展示信号定位结果,分析设备台站状态,经数据比对反映出设备性能及周围环境的变化趋势。文献4中提出了一种雷达与无线电测向融合定位方法，利用时空校准、数据标准化、航迹融合等技术,实现多元异构数据的融合定位，并将该技术应用于水上执法和水上搜救中,有效提高了船舶定位精度。文献5中基于无线电测向与卫星定位相结合的技术,实现落水者搜索定位，并通过无线电回传落水者身份识别和生命体征信息。

上述文献方法中，一般需要大型设备进行检测才能达到较好的效果。但是设备过大，带来移动测试不方便。本文针对上述不足，提出一种基于四天线线阵的干扰源测向的方法，使用的设备轻巧便捷，适用于需要反复移动的场合。我们对该方法的实际测试效果进行了室内和室外试验，证明了本文方法的有效性。本文第二节简要介绍相关测向算法，第三节介绍设备参数及测试结果，最后一节进行讨论分析。

# 1四天线阵的无线电测向系统

本文采用一种基于四天线线阵的方式搭建的一套测向系统，系统由四天线按照线性阵排列方式组成接收系统。系统的结构如图1所示。

![](images/21a0adec391cc40c1aec30d1ee1d99390612fb8a7d7bd70e924b923f3e8b4f53.jpg)  
图1系统框图

FIG.1 System block diagram

无线电测向的目的是通过测量和估算电磁波的参数来确定无线电发射机的方向，进而实现定位。如图2所示，一般情况下，通过测量方位角 $\alpha$ 即可确定无线电发射机的方向；但对于安装在飞行器的发射机和短波发射机，还需要测得来波的仰角 $\beta$ ，最终确定发射机的位置。

![](images/0fc5a2902fd3b77d7ae1a0c6fcb96063f3a0fc8772bf2f9abe787656fdc7bd59.jpg)  
图2测向方位角示意图  
FIG.2 Direction finding schematic diagram

# 2 MUSIC 测向算法

假设有 $\mathtt { M }$ 个完全相同的天线阵元。若有D个窄带信号 $S _ { \mathrm { { K } } } ( { \mathrm { t } } )$ 分别从 $\Theta _ { \mathrm { K } } ( \mathrm { k \pi = 1 , 2 , \cdots , D \ } )$ 入射,考虑测量噪声和所有信号源的来波，则第i个阵元的输出信号为：

$$
X _ { i } ( t ) = \sum _ { K = 1 } ^ { D } a _ { k } s _ { k } ( t ) \exp ( - j w ( i - 1 ) ) { \frac { 2 \pi d \sin \theta _ { k } } { \lambda } } + { \bf n } _ { i } ( t )
$$

式中： ${ \bf n } ( t )$ 为测量噪声,所有 $i$ 表示该变量属于第 $i$ 个阵元, $k$ 表示第 $k$ 个信号源， $a _ { k }$ 为阵元对第 $k$ 个信号源的影响,实验中假设各阵元完全相同,即 $a k = 1$ ， $w$ 为信号的中心频率, $\lambda$ 为载波波长。

假设入射各信号相互独立,假定各阵元的噪声为零均值的高斯白噪声,方差为 $\sigma ^ { 2 }$ ,且与信号不相关。将式(1)写成向量形式,可以得到阵列输出信号矩阵：

$$
X ( T ) = A S ( t ) + N ( T )
$$

式中： $X ( t ) = [ x _ { 1 } ( t ) , x _ { 2 } ( t ) , . . . , x _ { m } ( t ) ] ^ { T }$

$$
A = [ a ( \theta _ { 1 } ) , a ( \theta 2 ) , . . . , ( \theta _ { D } ) ]
$$

$$
\boldsymbol { S } ( t ) = [ s _ { 1 } ( t ) , s _ { 2 } ( t ) , . . . , s _ { D } ( t ) ] ^ { T }
$$

$$
N ( t ) = \left[ n \mathfrak { n } ( t ) , n \mathfrak { 2 } ( t ) , . . . , n \mathfrak { m } ( t ) \right] ^ { T } a ( \theta _ { k } ) = \left[ 1 , e ^ { j 2 \pi \frac { d } { \lambda } \cos ( \theta _ { k } ) } , . . . , e ^ { j 2 \pi ( M - 1 ) \frac { d } { \lambda } \cos ( \theta _ { k } ) } \right] ^ { T }
$$

$A$ 为 $\mathsf { M } \times \mathsf { N }$ 维的阵列,其各列向量代表天线阵在观察平面的某种观察特性,是待估参数 $\theta _ { k }$ 的函数，称之为阵列向量。

$X$ 的协方差矩阵可写成：

$$
R x = E [ X ( t ) X ^ { H } ( t ) ]
$$

将R进行特征值分解,特征值排序为 $\lambda _ { 1 } , \lambda _ { 2 } , . . . , \lambda _ { M }$ ；特征值所对应的特征向量分别为$e 1 , e 2 , . . . , e _ { M }$ 。

由于微弱信号特征值与噪声信号特征值不易区分，因此划分特征值为：

$$
D s = \mathrm { d i a g } ( \lambda _ { 1 } , \lambda _ { 2 , . . . , } \lambda _ { D - 1 ) }
$$

$$
D _ { n } = d i a g ( \lambda _ { D } , \lambda _ { D + 1 , . . . , \lambda _ { M } } )
$$

相应地划分信号子空间和噪声子空间为：

$$
E s = [ \mathbf { e } _ { 1 } , \mathbf { e } _ { 2 } , . . . , \mathbf { e } _ { \mathrm { D } - 1 } ]
$$

$$
E _ { N } = [ e _ { { \cal D } } , e _ { { \cal D } + 1 } , . . . , e _ { M } ]
$$

利用噪声子空间和信号子空间的正交关系,即在信号所在方向 $\theta _ { K }$ 上,有 $E _ { \mathrm { n } } ^ { H } a ( \theta _ { k } ) = 0$ ，实验中构造如下函数：

$$
P _ { M U S I C } ( \theta ) = \frac { a ^ { H } ( \theta ) a ( \theta ) } { a ^ { H } ( \theta ) E _ { 2 n } E _ { 2 n } ^ { H } a ( \theta ) }
$$

找出 $P _ { M U S I C } ( \phi )$ 的 $D$ 个最大峰值,就得到波达方向的估计。

MUSIC 算法的基本思想是将任意阵列输出数据的协方差矩阵进行特征分解，从而得到与信号分量相对应的信号子空间和与信号分量相正交的噪声子空间,然后利用这两个子空间的正交性来估计信号的参数(入射方向、极化信息及信号强度等)。

# 3实验

我们的试验在云南天文台进行，试验分为室内近场和室外远场两个部分，使用函数发生器模拟干扰源信号，通过N9020AMXA频谱分析仪对发射信号强度进行监测，采用四天线阵接收信号，将数据传输到树莓派上进行处理，估计来波方向。

![](images/b4ef4ad044450042c44fb92d6d067a9c3dddc77c3cd7e899039524329f37ebf5.jpg)  
图3实验设备  
FIG.3 Experimental equipment

所用设备及相关设备参数：

1. Kerberos SDR:频率范围：24MHz-1.7GHz，ADC 采样率:2.4MSpS，数据精度：8位通道数：4通道  
2. 信号源：频率范围： $1 0 \mathrm { H z } \mathrm { \stackrel { \sim } { 1 } } 1 0 0 \mathrm { H z }$ ， $1 0 0 \mathrm { { H z } ^ { \sim } 1 0 0 0 \mathrm { { H z } } }$ ，1kHz\~10kHz。  
3. 树莓派CPU 型号：Broadcom BCM2711，四核 Cortex-A72（ARM v8）64位 SoC@1.5GHz。内存： 2GB，4GB 或 8GB LPDDR4-3200 SDRAM（取决于型号）。无线网卡：2.4GHz 和5.0 GHzIEEE 802.11ac 无线，蓝牙5.0，BLE。

# 3.1室内测试

室内测试中，我们在空旷的室内进行，发射源与接收天线距离在 $4 . 8 \mathrm { m } ^ { - 8 . 8 \mathrm { m } }$ 之间，通过变换不同频率，不同水平位置进行多轮测试，测试结果如表一所示。假设无线信号的波长是lambda，则kerberosSDR连接的四根天线之间相距距离 $\mathrm { _ { { s * } } }$ ambda，即天线之间的距离为波长乘以“s”参数，波长 $\underline { { \underline { { \mathbf { \Pi } } } } } = :$ 波速/频率（波速 $\boldsymbol { \underline { = } } 3 \mathrm { x } 1 0 \ \mathrm { \hat { ~ } } 8$ ，频率是设好的 $9 \mathrm { x } 1 0 \ \hat { \ } 8 \ )$ ），spacing[lambda]参数会影响 kerberosSDR 的测向分辨率，spacing［lambda]参数“s”越大，则测向分辨率越高，但是天线之间的距离也就随之变大。测向分辨率越大，“DOA Estimation”选项卡中右边的图形中，波峰会越尖。文献7中以0.33计算。故我们的实验均以0.33为基础进行，在图一中所有数据均以水平向右为正，向左为负。

表1室内测量数据  
Table 1 Short-range measurement data   

<html><body><table><tr><td>frequency</td><td>spacing</td><td>Antenna distance</td><td>Straight-line distance</td><td>Distance</td><td>Transmission power</td><td>Measuring Angle</td><td>Real Angle</td></tr><tr><td>440Hz</td><td>0.33</td><td>22cm</td><td>4.8m</td><td>1. 6m</td><td>0dbm</td><td>17°±2°</td><td>18°</td></tr><tr><td>440Hz</td><td>0.33</td><td>22cm</td><td>4.8m</td><td>0.8m</td><td>0dbm</td><td>6°±4°</td><td>9.5°</td></tr><tr><td>440Hz</td><td>0.33</td><td>22cm</td><td>4.8m</td><td>0m</td><td>0dbm</td><td>0°±5°</td><td>0°</td></tr><tr><td>440Hz</td><td>0.33</td><td>22cm</td><td>4.8m</td><td>-0.8m</td><td>0dbm</td><td>-6°±4°</td><td>-9.5°</td></tr><tr><td>440Hz</td><td>0.33</td><td>22cm</td><td>4.8m</td><td>-1. 6m</td><td>10dbm</td><td>-15°±5°</td><td>-18°</td></tr><tr><td>440Hz</td><td>0.33</td><td>22cm</td><td>4.8m</td><td>-2.4m</td><td>10dbm</td><td>-25°±5°</td><td>-26.6°</td></tr></table></body></html>

<html><body><table><tr><td>550Hz</td><td>0.33</td><td>18cm</td><td>4.8m</td><td>1. 6m</td><td>10dbm</td><td>20°</td><td>18°</td></tr><tr><td>550Hz</td><td>0.33</td><td>18cm</td><td>4.8m</td><td>0.8m</td><td>10dbm</td><td>9°</td><td>9.5°</td></tr><tr><td>550Hz</td><td>0.33</td><td>18cm</td><td>4. 8m</td><td>0m</td><td>10dbm</td><td>0°</td><td>0°</td></tr><tr><td>550Hz</td><td>0.33</td><td>18cm</td><td>4.8m</td><td>-0.8m</td><td>10dbm</td><td>-9°</td><td>-9.5°</td></tr><tr><td>550Hz</td><td>0.33</td><td>18cm</td><td>4. 8m</td><td>-1. 6m</td><td>10dbm</td><td>-15°</td><td>-18°</td></tr><tr><td>550Hz</td><td>0.33</td><td>18cm</td><td>4.8m</td><td>-2.4m</td><td>10dbm</td><td>-40°</td><td>-34.6°</td></tr><tr><td>750Hz</td><td>0.33</td><td>13cm</td><td>7.2m</td><td>0.8m</td><td>10dbm</td><td>0°</td><td>5.4°</td></tr><tr><td>750Hz</td><td>0.33</td><td>13cm</td><td>7. 2m</td><td>0m</td><td>10dbm</td><td>0°</td><td>0°</td></tr><tr><td>750Hz</td><td>0.33</td><td>13cm</td><td>7. 2m</td><td>-0.8m</td><td>10dbm</td><td>-7°±1°</td><td>-6.3°</td></tr><tr><td>750Hz</td><td>0.33</td><td>13cm</td><td>7. 2m</td><td>-1.6m</td><td>10dbm</td><td>-12°</td><td>-12.5°</td></tr><tr><td>750Hz</td><td>0.33</td><td>13cm</td><td>7. 2m</td><td>-2.4m</td><td>10dbm</td><td>-18°±2°</td><td>-18.5°</td></tr><tr><td>900Hz</td><td>0.33</td><td>11cm</td><td>8.8m</td><td>1.6m</td><td>10dbm</td><td>9°</td><td>10°</td></tr><tr><td>900Hz</td><td>0.33</td><td>11cm</td><td>8.8m</td><td>0.8m</td><td>10dbm</td><td>5°</td><td>5°</td></tr><tr><td>900Hz</td><td>0.33</td><td>11cm</td><td>8.8m</td><td>0m</td><td>10dbm</td><td>0°</td><td>0°</td></tr><tr><td>900Hz</td><td>0.33</td><td>11cm</td><td>8.8m</td><td>-0.8m</td><td>10dbm</td><td>-6°</td><td>-6°</td></tr><tr><td>900Hz</td><td>0.33</td><td>11cm</td><td>8.8m</td><td>-1. 6m</td><td>10dbm</td><td>-9°</td><td>-10°</td></tr><tr><td>900Hz</td><td>0.33</td><td>11cm</td><td>8.8m</td><td>-2.4m</td><td>10dbm</td><td>-10°</td><td>-15°</td></tr></table></body></html>

# (2）室外测试

室外环境中，我们将测试天线与发射源的距离调整到 $5 0 0 \mathrm { m }$ 以上，以观测在远场环境中，系统测向的性能。在不同频率，不同方位的试验下，测试数据如表2和表3所示，且表中所有数据均以向右为正，向左为负。

Table 2 Remote direction finding (Kerberos SDR)   
表3远场测向 (信号源)  

<html><body><table><tr><td>Frequency</td><td>Theoretical point of Angle</td><td>The measured Angle</td></tr><tr><td>900Hz</td><td>0°</td><td>2°±8°</td></tr><tr><td>900Hz</td><td>20°</td><td>16°</td></tr><tr><td>900Hz</td><td>-60°</td><td>-70°</td></tr><tr><td>750Hz</td><td>0°</td><td>1°±5°</td></tr><tr><td>750Hz</td><td>20°</td><td>19°±1°</td></tr><tr><td>750Hz</td><td>-30°</td><td>-20°</td></tr><tr><td>550Hz</td><td>0°</td><td>11°</td></tr><tr><td>550Hz</td><td>20°</td><td>13o±30</td></tr><tr><td>550Hz</td><td>-30°</td><td>-30°</td></tr><tr><td>440Hz</td><td>0°</td><td>-11°</td></tr><tr><td>440Hz</td><td>30°</td><td>280±20</td></tr><tr><td>440Hz</td><td>-15°</td><td>-26°</td></tr><tr><td>440Hz</td><td>-40°</td><td>-40°</td></tr></table></body></html>

表2远场测向（Kerberos SDR)  
Table 3 Remote direction finding (Function transmitter)   

<html><body><table><tr><td>frequency</td><td>Theoretical point of Angle</td><td>The measured Angle</td></tr><tr><td>900Hz</td><td>0°</td><td>2°±8°</td></tr><tr><td>900Hz</td><td>20°</td><td>16°</td></tr><tr><td>900Hz</td><td>50°</td><td>53°±2°</td></tr></table></body></html>

<html><body><table><tr><td>900Hz</td><td>-15° 16°±4°</td></tr><tr><td>750Hz</td><td>0°</td></tr><tr><td></td><td>-5°±1° 19°±1°</td></tr><tr><td>750Hz 750Hz</td><td>20°</td></tr><tr><td>-10°</td><td>-5°±1°</td></tr><tr><td>750Hz -60°</td><td>-57°±2°</td></tr><tr><td>550Hz</td><td>0° 0°±8°</td></tr><tr><td>550Hz 20°</td><td>19°±1°</td></tr><tr><td>550Hz</td><td>-30° -28°±2°</td></tr><tr><td>440Hz</td><td>0° 0°±10°</td></tr><tr><td>440Hz 20° 440Hz -45°</td><td>15°±5° -35°±5°</td></tr></table></body></html>

# 4讨论

在表一中，进行了23次测试，如果对测试次数进行增加并且对数据离散性进行统计分析，则测量误差在 $5 ^ { \circ }$ 以内。以误差不超过5度的视为成功，共成功20次，失败3次，成功率约为 $8 7 \%$ 。且2次失败情况是发射源与接受源水平距离在 $2 . 4 \mathrm { { m } }$ 处，不排除此处有其他较强干扰源的可能性或着是发射源距离过远，天线数量较少，观测强度较弱的可能性。剩下一次的失败情况是发射源与接受源水平距离在0.8m处，此时测量角度处于 $0 ^ { \circ }$ ，可能是Kerberos SDR的运算时间过长，机器过热导致测量不准。图4为室内测量曲线趋势图，可以直观地看出整体的趋势。

3020 17 2018 9 910 5.4 50 18 N 0 9 0 00 9.5 -6 9.5 -9 7 -12 10 -6 -9 -101020 -9.5- 1 -25 -9.5 / -6.3 -12.5 18.5 -10 > -15-30-26.6-40 -34.6-50 0dbmOdbmOdbm0dbm10db10db 10db10db10db 1db10db10dbdbbdbdbdbbdbbb 10db1.6m0.8m 0m -0.8m-1.6m-2.4m1.6m0.8m 0m -0.8m-1.6m-2.4m0.8m 0m -0.8m-1.6m-2.4m1.6m0.8m 0m -0.8m-1.6m-2.4m4.8m4.8m4.8m4.8m4.8m4.8m 4.8m4.8m4.8m 4.8m4.8m4.8m7.2m7.2m7.2m7.2m7.2m8.8m8.8m8.8m8.8m8.8m8.8m22cm22cm22cm22cm22cm22cm18cm18cm18cm18cm18cm18cm13cm13cm13cm13cm13cm1cm1cm1cm11cm11cm11cm0.33 0.33 0.330.330.33 0.33 0.33 0.33 0.33 0.33 0.33 0.33 0.33 0.33 0.33 0.33 0.33 0.330.330.330.33 0.33 0.33440H2440H2440z440z440440H505H5505505507575z75z50z75900909090900H900z  
Measuring Angle 17 6 0 -6 -15 -25 20 9 0 -9 -15 -40 0 0 -7 -12 -18 9 5 0 -6 -9 -10  
Measure the Angle 18 9.5 0 -9.5 -18 -26.6 18 9.5 0 -9.5 -18 -34.6 5.4 0 -6.3-12.5-18.5 10 5 0 -6 -10 -15Measuring Angle Measure the Angle

在表二中，进行了13次测试，如果对测试次数进行增加并且对数据离散性进行统计分析，则测量误差在 $1 0 ^ { \circ }$ 以内，以 $1 0 ^ { \circ }$ 为最大误差，小于 $1 0 ^ { \circ }$ 视为成功。共成功10次，失败3次，成功率为 $7 7 \%$ 。2次失败处于 $4 4 0 \mathrm { { H z } }$ ，且测量处于户外，不排除当时附近有电子产品的干扰。剩下一次失败，是处于 $5 5 0 \mathrm { H z }$ ，鉴于只有这一次失败情况，不排除是操作失误的可能，亦或者是天线数量较少使得 Kerberos SDR的测量准确性下降。图5为远场测向（Kerberos SDR）的

曲线趋势图，明显地可以看出整体的趋势。

![](images/5ab70c2f254b5560a8127f6eebb67681bd8ac7d4d7641405180a6d8915cb8e90.jpg)  
FIG.5Remote direction finding(Kerberos SDR) curve trend diagram

在表三中，进行了14次测试，测量结果都处于实际结果的范围内，成功率达到 $1 0 0 \%$ 。充分表明 N9020A MXA频谱分析仪的测量准确，也间接表明我们的方法具有可行性。图6是远场测向（信号源）曲线趋势图，通过曲线对比能够更清晰的展现实验结果。

![](images/ae45a853a5fc281a1f0d4367c74be69290d3dff80206ddc37a1d5c2b1c295dab.jpg)  
图5远场测向（KerberosSDR）曲线趋势图  
图6远场测向（Kerberos SDR）曲线趋势图

FIG.6 Remote direction finding(Function transmitter) curve trend diagram

由表二与表三对比得知，表二中测试误差大的可能是 Kerberos SDR 的天线数量太少，接受信号受到的干扰更多，所以可以增加更多天线来使得 Kerberos SDR 的测量准确性提高。针对表一中的情况，则可以对 Kerberos SDR 设备增加降温措施。亦或者可以利用多个阵相互补充，最终确定准确的测量方向。

# 5结论

综合上述讨论，使用便携式四天线阵提前辨识CAS 来波方向是可行的，虽然 Kerberos SDR远程测向还是会有一定误差，后续需要在算法上进行进一步改进，进一步提高测向精度。同时，后续可考虑通过Kerberos SDR把数据实时输出到云端服务器，再加以利用微信小程序的功能把干扰信号的来波方向直观的显示在手机上，这就方便工作人员去调整射电望远镜的探查区域来避开干扰，进而达到短暂的有效的观测宁静区。

# 致谢

本文得到国家自然科学基金，天文联合基金培育项目（U2031133），重点项目（U1831201），重点专项项目（11941003）,云南省应用基础研究计划面上项目（2019FB009）项目的支持。

# 参考文献：

[1］许红瑞、陈卯蒸、刘奇、尹航、王军、刘璇、袁力.关于射电望远镜台址航空信号处理方法研究[J]，天文学报，2018，59（02)：3-43 XuHongru,Chenaozen,LiuQi,YinHangWangJun,Li Xuan,YuanLi.Researchonairboesignalprocessingetodforradio telescope site [J],acta astronomica sinica, 2018,59 (02) : 33-43

[2]何伟杰.基于无人机平台的无线电测向技术研究[D].兰州交通大学通信与信息系统，2020 He Weijie.Research on Radio DirectiorFinding Technology Basedon UAVPlatform[D]. Communication and Information SystemofLanzhou Jiaotong University,2020

[3]徐如兰、潘云飞，基于开场测试的明航空管无线电信号监测与分析系统应用[J],中国新技术新产品,2021,(18):43-46 Xu Rulan andPanYnfei.AplicationofRadioSignalMonitoringandAnalysisSystemforMingAviationTubeBasedonOpeningTest[J.China New Technology and New Products,2021,(18):43-46

[4]王维圳、曾文浩，监视雷达与无线电测向融合定位在水上交通中的综合应用[J],网络安全技术与应用，2018，（12)：128-130 WangWeizhen,ZengWenao.ItegratedApplicatioofSurveillnceRadarandRadioDirectionFindingFusionlocalzationinWateic[JNetwork Security Technology and Application,2018,(12) :128-130

[5]王洵、梁懿、司高潮，某型海上落水人员搜索定位装置的研制[J],中华航海医学与高气压医学杂志,2014,21(06):398-400 Wangxun,liangyi,sigaogaodevelopmentofcertaintypeofsarchndlocatioevicefordongpeopleatseaJ],insejoalfMarine medicine and hyperbaric medicine,2014,21(O6):398-400

[6]郭强、赵国庆,基于矩阵变换的均匀线阵测向方法研究[J],国外电子测量技术,2006,（10)：10-13 Guo Qiang,Zhao Guoqing.StudyonUniformLinearArrayDiectionFidingMethodBasedonatrixTransformation[J].ForeignElectronicMeasurementTechology06(10) : 10-13

[7]ZuokunLi、Zhang Dongdong、Zhu Qichao、Gu Henghao、Huang Shuai、Kuang Yi、Liu Yingwen.Application Research on DOA EstimatioBasedftareDeeddioeceier[J]uaofis:ferecerisVle7sue,

[8]张海燕．中国射电天文频率保护进展[J]，天文学进展,2017,35(04):473-480 Progressinradio astronomical frequency protection in China [J].Progress in astronomy,2017,35(04):473-480

[9]斐海燕．探究无线电技术应用的重要性[J],电子信息工程,2015,(24):40Fei Haiyan.Research onthe Importance of RadioTechnology Application [J].Electronic Information Engineering,2O15,(24):40

[10]么仕君、杜川、史才晖.无线电测向设备的现状与发展[J],通讯世界，2016,(06)：20Yao Shijun,Du Chuan,Shi Caihui.Current

Situation and Development of Radio Direction Finding Equipment [J],Communications World,2O16,(O6):20

[1IlcevDimovStojce.NewAspectsofProgressintheModerzationoftheMaritimeRadioDirectionFinders[J],ransactioson Maritime Science,2021,10(1):68-83

[12]刘利军．浅论无线电测向技术及其应用[J]，中国高新技术企业,2009,(07)：7-8LiuLijun.Discussion on Radio Direction Finding Technology and its Application [J]. China High-tech Enterprise,2009,(07) : 7-8

[13]周霞、杨琳、王英翔．短波测向定位误差分析[J],中国无线电,2021,（O7):85 Zhou Xia,YangLin,Wang Yingxiang.Error Analysis of Short wave Direction Finding and Location [J],Radio China,2O21,(O7) : 85