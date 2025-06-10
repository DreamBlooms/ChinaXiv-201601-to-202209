# 基于知识与数据驱动的高速路车辆速度计算方法模型研究

彭大芹，罗裕枫，范兴荣

(1．“新一代信息网络与终端”重庆市协同创新中心，重庆 400065;2.重庆邮电大学电子信息与网络工程研究院，重庆 400065)

摘要：由于目前通过蜂窝基站定位的精度不够高和信令数据产生的不确定性，所以通过手机信令数据估计交通信息参数的精确度仍然是一个巨大的挑战。高速路车辆速度参数是评估道路服务质量的最常研究的参数之一，目前基于手机信令数据的交通参数估计基本步骤为数据收集及预处理、地图匹配、用户路线匹配确定和交通信息参数估计。在此基础上，根据物理运动学知识，针对手机信令数据产生的不确定性和容易参杂平行公路噪声用户数据的影响，提出一种融合距离加权的改进车辆速度计算方法，并在此方法之上进一步提出一种消除平行公路干扰数据的车辆速度计算方法，提高计算准确度。利用某移动公司提供的平台进行实例验证，并采用平均绝对误差MAE、均方根误差RMSE、平均绝对百分比误差MAPE作为性能指标，该方法模型性能均优于传统方法模型，并且平均绝对百分比误差比传统方法降低 $10 \%$ 左右，具有重要的应用价值。

关键词：智能交通系统；手机信令数据；车辆速度；平行道路；噪声数据中图分类号：U doi:10.3969/j.issn.1001-3695.2018.03.0155

# Research on model of highway vehicle speed calculation based on knowledge and data driven

Peng Daqin, Luo Yufeng, Fan Xingrong (1.Chongqing Colaborative Innovation Center for Information Communication Technology,Chongqing 40o65,China; 2. Electronic Information &Networking Research Institute,Chongqing UniversityofPosts&Telecommunications,Chonging 400065, China)

Abstract:Due to the currnt high accuracyof positioning via celular base stations and the uncertaintyof signaling data, estimating the acuracyof trafic information parameters using cell phone signaling data remains asignificant challenge. Highwayspeed parameters areone ofthe most commonly studied parameters forevaluating road servicequality.At present,the basic steps of trafic parameter estimationbased oncell phone signaling data areas follows: Data collectionand preprocessing, map matching,userroute matching determinationandtrafic information parameter estimation.Onthis basis,according tothe knowledgeofphysical kinematics,aimingattheuncertaintyofhandset signalingdata andthe influenceofparalel highway noiseon user data,an improved vehicle sped calculation method based on weighted distance fusion is proposed and further proposedonthis methodA Methodof Vehicle Sped Calculation to Eliminate Paralel Highway InterferenceData and Improve Calculation Precision.Usingaplatform providedbya mobilecompanyfor instance verification,andusingtheaverageabsolute error MAE,rot mean square error RMSE,average absolute percentage errorMAPE as aperformance indicator, in this paper, the performanceof themethod model is beterthanthe traditional method model,and theaverageabsolute percentageeroris about $10 \%$ lower than the traditional method,which has important application value.

Key Words: intelligent transportation system; cell phone signaling data; Vehicle speed; Parallel road; Noisedata

# 0 引言

通信息系统越来越重要。目前高速路的交通流数据主要通过感应线圈、地磁、视频、雷达探测器以及红外等检测器，这些方式需要在道路上安装检测器设备，需要耗费大量的人力物力。或者通过GPS进行车辆信息采集，但这种方式需要在运行车辆

近年来，经济的增长和技术进步的崛起导致了智能交通系统（ITS）对交通服务的需求越来越高，如何构建ITS的实时交上装载GPS相关设备，初期投资成本高，并且收集数据不完整，具有一定的局限性。随着蜂窝网络的全面密集覆盖和手机的普及，使用手机信令数据来获取交通信息参数在目前已经成为一种有效可行的方式，由于其不仅成本底和全面覆盖，还可以准确实时全天候获取交通参数信息，所以基于蜂窝手机信令数据估计交通参数和状况已经成为了一种替代传统方式的热门的技术方案。

近年来，有很多关于通过移动手机信令数据来获取高速公路交通流参数和路况信息方面的国内外的研究，主要的交通流参数包括车辆速度、车辆密度、行程时间和车流量等错误未找到引用源。，其中车辆速度参数是高速公路交通信息中最重要参数之一，也是在评估道路服务质量的最常研究的参数之一。目前基于移动手机信令数据的高速公路车辆速度计算方法主要分为两种：第一种是通过两点的行程距离差与行程时间差的比值 $V _ { k } =$ S-S来计算速度；第二种是通过路段的交通流量（veh/h）与交1

通密度（veh/km）的比值 $\begin{array} { r } { V _ { k } = \frac { Q _ { i } } { K _ { i } } . } \end{array}$ 来计算速度。文献错误!未找到引用源。中基于对手机信令数据的分析验证了信令数据在交通拥堵识别方面的重要价值，并通过手机用户在行驶过程中在基站间切换产生的信令数据来计算行程距离差和行程时间来计算车辆速度，进而进行拥堵状态识别，证明了这种方法的可行性和实用性。当手机用户执行呼叫并从小区1移动到小区2时，产生并记录越区切换信号。此外，手机用户保持从小区2移动到小区3，还生成并记录另一越区切换信号。可以分析这两个越区切换信号以获得小区2的小区驻留时间和车辆行程距离。然后可以估计高速公路路段的车辆速度错误！未找到引用源。文献错误!未找到引用源。提出基于位置切换的交通速度估算方法，根据用户轨迹与目标路段切换序列使用求最长公共子序列的方法进行地图匹配，利用切换点距离与行程时间的比值来估算交通流速度，并取得了不错的效果，但速度波动较大，存在干扰数据，致使计算精度不够高。文献错误!未找到引用源。通过手机用户位置切换和正常位置更新的数量估计交通密度，并根据用户呼叫到达和周期性更新的数量估计交通流量，进而估算车辆速度，证明了方法可行，但是由于利用手机信令数据估计交通密度和交通流量的准确度不够高和计算复杂，故存在较大误差。后来研究者发现利用手机信令数据估计交通速度会存在大量噪声数据的影响，如高速路周边的行人、周边公路的车辆用户等，并有研究者提出对信令数据进行分类，区分机动车载体和非机动车载体，同时滤除噪声数据的方法，通过此方法计算的车辆速度准确度得到了提高错误！未找到引用源。文献错误!未找到引用源。提出了一种基于手机信令数据的高速路车速估计算法，引入了信令间隔区间阈值和时间间隔阈值，通过该阈值的限制，能够滤除一部分误差数据，能很大程度降低定位不准确导致的速度计算误差。

综合上述研究，由于手机信令数据产生的不确定性和容易参杂噪声数据的缺点，致使高速公路车辆速度计算准确度不够高。本文针对信令数据的产生的不确定性而在一个高速路段生成的距离长度不一的路程差的特点，提出利用两点的行程距离差与行程时间差的比值中引入与距离相关的加权因子函数来计算车辆速度的计算方法。还特别针对高速路周边平行公路干扰数据，进一步提出一种基于移动手机信令数据的平行公路干扰消除的车辆速度计算方法，很大程度提高了高速路车辆速度计算的准确度，对于基于手机信令手机获取交通信息的方法可以很好应用在现代智能交通系统(ITS)，进一步提高服务质量具有重要的意义。

# 1 基本概念

# 1.1产生手机信令数据的通信事件

当车载手机用户在高速公路上行驶的过程中会不确定性的在周边基站产生手机信令数据，手机信令数据的产生是由一些通信事件所驱动生成的，以下是产生手机信令数据的通信事件的一个简单的概括介绍，如图1（b）所示。

![](images/7258a317d59dcafdb619ee9b3c4d27d33e2f5c943caa2a6ce59d25e0b40d44bf.jpg)  
图1 (a)车载用户在高速路上行驶过程  
图1 (b)通信事件简介图

周期性位置位置更新 更新收发短信 正常位置更新呼叫连接通信事件 IMSI附着是手切换 机开机或SIM卡插入IMSI附着或分离IMSI分离是手机关机

由以上5类通信事件产生的手机信令数据经过移动运营商的手机原始信令数据采集系统平台并经过对数据进行过滤去噪等预处理后，再通过数据传输管道分发到各个处理模块。提取接收G85高速公路监测区域的基站的手机信令数据用于本文的实验研究，手机信令数据包含的主要字段与说明如表1所示。本文主要用到1，2，3，4，5的字段，其中通过LAC和CELLID可以匹配到基站的经度（Lng）和纬度（Lat）。

表1移动用户信令数据部分字段说明  

<html><body><table><tr><td>序号 字段名称</td><td></td><td>字段说明</td></tr><tr><td>1</td><td>IMSI</td><td>国际移动用户识别码，唯一的手机识别</td></tr><tr><td></td><td>2 TimeStamp</td><td>信令数据发生的时间戳，YYYYMMD</td></tr><tr><td></td><td></td><td>DHHMMSS，精确到秒</td></tr></table></body></html>

<html><body><table><tr><td>3</td><td>LAC</td><td>位置区编号</td></tr><tr><td>4</td><td>CELLID</td><td>小区位置区编号</td></tr><tr><td>5</td><td>EventID</td><td>通信事件类型：（1周期性更新，2正常位置更 新，3收发短信，4呼叫切换，5切换，6开关</td></tr><tr><td>6</td><td>Flag</td><td>机） 进出小区标识</td></tr><tr><td>7</td><td>Cause</td><td>切换原因</td></tr><tr><td>8</td><td>Result</td><td>事件结果</td></tr></table></body></html>

# 1.2手机信令数据的噪声数据

高速公路路网复杂，临近周边存在平行公路、乡村道路和省道路等，并且由于基站的定位精度不够高，所以原始手机信令数据中会引入大量的噪声用户数据，例如高速路周边道路的行人、周边的居民、高速路临近平行公路和乡村道路的用户等噪声用户数据。这些干扰噪声数据会在车辆速度计算时造成严重的影响，导致车辆速度计算的不准确。目前针对高速路周边居民和行人的干扰数据已经存在解决的方法，但是没有特别针对高速公路临近平行公路和乡村道路等的车辆用户干扰数据的解决方法。因此本文提出一种平行公路干扰消除的方法，并在此基础上进行车辆速度计算。高速路周边的平行道路图如图 2所示。

![](images/613acfe8e1292898697246a3c0fdd5727b8ddc30efdf1074c778fdd48af3c47b.jpg)  
图2平行道路图

# 2 高速路车辆速度计算方法原理

目前，对于利用手机信令数据获取高速公路交通流参数信息已经存在了一定深入的研究，特别的，研究者对于基于手机信令数据的高速公路车辆速度计算方法的研究也做出了巨大的贡献[6\~II]，为了从获取的手机信令数据中获取到高速路的车辆速度参数，可以包括以下基本步骤：信令数据预处理；路网匹配，进行高速路和基站序列的匹配；高速公路用户路径匹配，判断识别高速公路行驶车载用户；高速公路车辆速度计算。具体的流程框架图如图3所示。

# 2.1数据清洗与预处理

由于基站定位技术的定位精度不够高、高速路周边环境的复杂性和手机信令数据产生的不确定性，由移动运营商的手机原始信令数据采集系统平台收集的信令数据会存在大量的“脏数据”，所以必须对收集的原始手机信令数据进行字段提取、滤除脏数据、过滤乒乓效应数据等数据预处理操作，有利于下一步的快速计算，提高匹配精度。其数据预处理的处理步骤如图4所示。

![](images/d14b7e85a9a935e7bdf46a64ff7b17359dbc5cd25cb78f864b5b91f7364a80c1.jpg)  
图3传统高速路车辆速度计算方法流程图

![](images/e3f4a555c84034c2a3d02bc2df721baf4b1aa6e39eeb1a994af257e013e22cf6.jpg)  
图4数据预处理

# 2.2 路网匹配

路网匹配也就是高速公路路段与移动基站覆盖的匹配，根据高速公路路段序列建立与基站的映射关系表是进行高速公路用户路径匹配和车辆速度计算的基础前提，本文考虑到道路段与基站的距离和基站的扇区覆盖方向等影响因素进行高速路路段与基站的最大可能匹配，其主要的步骤如下：

a)根据高速公路道路的路线，建立一个矩形监测区域，使得矩形区域完全包括高速公路，以矩形区域的左下角点为原点建立二维坐标系，并以长为L的正方形栅格对矩形区域进行栅格划分。记录高速路为道路栅格序列

$\mathrm { S e g } = \{ S _ { x _ { 1 } , y _ { 1 } } ( \ln g , \ln \mathrm { t } ) , \dots , S _ { x _ { i } , y _ { i } } ( \ln g , \ln \mathrm { t } ) , \dots , S _ { x _ { n } , y _ { n } } ( \ln \mathrm { g } , \ln \mathrm { t } ) \}$ 记录监测区域的基站序列为

$$
\mathsf { s t a } = \{ M _ { x _ { 1 } , y _ { 1 } } ( \ln \mathbf { g } , \ln \mathbf { t } ) , \dots , M _ { x _ { i } , y _ { i } } ( \ln \mathbf { g } , \ln \mathbf { t } ) , \dots , M _ { x _ { n } , y _ { n } } ( \ln \mathbf { g } , \ln \mathbf { t } ) \}
$$

b)为每个道路栅格最大可能匹配对应的基站。通过经纬度计算道路栅格序列里每个栅格与基站序列的每个基站的欧式距离，并且确定基站扇区是否覆盖到道路栅格，选取距离最短并且基站扇区覆盖道路栅格的基站为该道路栅格的映射基站。

c)以二维坐标序列号升序方向 $\{ ( x _ { 1 } , y _ { 1 } ) , \ldots ( x _ { i } , y _ { i } ) , \ldots ( x _ { n } , y _ { n } ) \}$ 为高速路的正方向，降序方向 $\{ ( x _ { n } , y _ { n } ) , \ldots ( x _ { i } , y _ { i } ) , \ldots ( x _ { 1 } , y _ { 1 } ) \}$ 为高速路反方向，建立高速路段和基站的匹配库，如表2所示。

表2高速路与基站匹配说明表  

<html><body><table><tr><td>序号</td><td>字段名</td><td>字段说明</td></tr><tr><td>1</td><td>Road_ID</td><td>高速路道路栅格序号(xi,yi)</td></tr><tr><td>2</td><td>Road_Lng</td><td>道路栅格经度</td></tr><tr><td>3</td><td>Road_Lat</td><td>道路栅格纬度</td></tr><tr><td>4</td><td>Station_ID</td><td>基站栅格序号(𝑥i,yi)</td></tr><tr><td>5</td><td>Station_Lng</td><td>基站经度</td></tr><tr><td>6</td><td>Station_Lat</td><td>基站纬度</td></tr><tr><td>7</td><td>Flag</td><td>基站是否覆盖道路栅格，是：1，否：0</td></tr></table></body></html>

# 2.3高速公路用户路径匹配

高速公路用户路径匹配是为了将经过数据预处理后的用户手机信令数据轨迹序列与高速路栅格序列进行匹配，初步识别出在高速路上行驶的车载用户。其主要的步骤如下：

a)获取经过数据预处理得到的监测区域的用户手机信令数据轨迹序列集，提取每个用户的信令轨迹序列 $T r a c e _ { i } =$ $\{ M _ { x _ { j } y _ { j } } ( l n g , l a t ) , \ldots , M _ { x _ { k } y _ { k } } ( l n g , l a t ) \}$ 共有 N个轨迹点，将用户的信令轨迹序列与高速公路基站匹配库进行对比，统计用户的信令轨迹序列在高速公路基站匹配库中存在的 $N _ { 1 }$ 个轨迹点。

b)计算用户信令轨迹与高速路道路栅格序列的相似度入，当相似度入超过一定阈值并且具有一定方向性则判定为高速公路用户，用户的方向性通过二维坐标序列号 $( x _ { i } , y _ { i } )$ 的递增和递减来确定。

# 2.4高速公路车辆速度计算

文献[11传统高速公路道路栅格车辆用户速度的计算主要是通过两轨迹点的行程路程差和行程时间差的比值来计算。

$$
\begin{array} { r } { V _ { i } = \frac { d i s t \{ M _ { x _ { i } y _ { i } } ( l n g , l a t ) , M _ { x _ { j } y _ { j } } ( l n g , l a t ) \} } { T _ { j } - T _ { i } } } \end{array}
$$

其中 ${ \bf \cdot } M _ { x _ { i } y _ { i } } ( l n g , l a t )$ 是基站位置点，dist是计算两个基站位置点之间的欧式距离， $T _ { j } - T _ { i }$ 是两点的行程时间差。

若计算道路栅格K的平均速度，假设有 $\mathfrak { n }$ 个两两轨迹点经过并包括道路栅格K，则道路栅格K 的平均车辆速度为 $\mathsf { I } V _ { k }$ 。

$$
\textstyle V _ { k } = \sum _ { i = 1 } ^ { n } V _ { i } { \big / } _ { n }
$$

# 1)本文方法模型1

传统方法单纯考虑了行程路程差和行程时间差的比值来计算车辆速度，但由于手机信令数据产生的不确定性，进而会造成包含一个道路栅格会存在行程距离长度不一样的多个两两轨迹点。这种不确定性会对高速路车辆速度计算有一定的影响，因此文本在传统方法的基础上，根据物理运动学的思想知识，由统计意义的角度上可知包含一个道路栅格的两轨迹点计算单元的路程距离越短，则对该道路栅格平均速度的贡献值越大的特点，因此本文根据此特点提出一种融合路程加权的改进车辆速度计算方法，其改进方法的具体流程框图如图5所示。由流程图可知改进部分方法步骤如下：

a)计算包含某道路栅格的两两轨迹点的行程距离和行程时间，用于计算对该道路栅格的车辆平均速度的速度贡献值的其

中之一。

b)选择一个与行程距离呈反相关的加权因子函数 $\varphi _ { i j } ^ { l }$ 计算加权值，用于对速度贡献值进行加权。

c使用距离权值函数计算加权值然后与每个速度贡献值的乘积后的值进行求和运算得到最终的道路栅格车辆平均速度值。计算公式如下：

$$
\begin{array} { r } { V _ { k } = \sum _ { l = 1 } ^ { N _ { k } } \varphi _ { i j } ^ { l } \cdot \frac { d i s t \{ M _ { x _ { i } y _ { i } } ( l n g , l a t ) , M _ { x _ { j } y _ { j } } ( l n g , l a t ) \} } { T _ { j } - T _ { i } } } \end{array}
$$

其中i表示为第k个路段的第l个用户信令， ${ { N } _ { k } }$ 表示第 $\mathbf { k }$ 个路段的两两轨迹点数。

![](images/9bd712dacce05cfa72a6a1dcbcad677b9f922c20fc77dd07e554b644b914ca12.jpg)  
图5本文方法模型1方法流程

# 2)本文方法模型2

高速公路车辆速度计算准确度除了受手机信令数据产生不确定性特点的影响外，还很大程度受到了噪声用户数据的干扰，特别是高速路临近的平行公路、乡村道路和省道路的行车用户的影响。由于高速路的平行道路一般存在于高速路的路段周边，因此可以根据其前面不存在平行道路的路段的历史用户数据进行剔除干扰用户。因此针对平行道路干扰用户，在本文方法模型一改进的车辆速度计算方法的基础上进一步对平行公路干扰消除，然后重新计算含平行道路的高速路车辆速度。主要依据是存在平行公路路段的高速路与之前高速路段的用户数量差别和高速路与平行公路之间的速度差别的思想进行干扰剔除，其具体的流程框图如图6所示。其方法主要的原理如下：

d)获取当前时刻的存在平行公路的高速路道路栅格的用户数 $N _ { k }$ 个用户，并同时获取其历史时刻的后方不存在平行公路的高速路道路栅格的用户数 $N _ { \mathrm { t } }$ 个用户，用户数 ${ { N } _ { k } }$ 与用户数 $N _ { \mathrm { t } }$ 求交集运算 $N _ { k } ^ { 1 } = N _ { k } \cap N _ { t }$ ，那么 $N _ { k } ^ { 2 } = N _ { k } - N _ { k } ^ { 1 }$ ，则 $N _ { k } ^ { 1 }$ 部分用户是确定为高速公路上的用户， $N _ { k } ^ { 2 }$ 部分用户是不确定的用户；

e)根据确定为高速公路上的部分用户 $N _ { k } ^ { 1 }$ 来计算存在平行公路的道路栅格的平均速度值 $V _ { k } ^ { 1 }$ ，平均速度值 $V _ { k } ^ { 1 }$ 运用本文方法模型一的车辆平均速度计算方法来计算。然后根据平均速度值 $V _ { k } ^ { 1 }$ 来确定该道路栅格属于那种交通状态，交通状态分为畅通状态（204 $( V _ { k } ^ { 1 } \ge 8 0 k m / h )$ ，轻度拥堵状态（ $4 0 \mathrm { k m / h } \le V _ { k } ^ { 1 } < 8 0 \mathrm { k m / }$ h），拥堵状态 $( V _ { k } ^ { 1 } < 4 0 \mathrm { k m / h } )$ ）。

f)根据行程路程差和行程时间差的比值的速度计算公式计算 $N _ { k } ^ { 2 }$ 中每个用户的速度值 $V _ { k } ^ { 2 }$ ，然后与速度值 $V _ { k } ^ { 1 }$ 进行对比，如果某用户的速度值 $\textstyle V _ { k } ^ { 2 }$ 属于由 $V _ { k } ^ { 1 }$ 确定的道路状态的速度范围，则判定为高速公路上的用户，否则判定为平行公路干扰用户，并进行剔除处理。并且得到从不确定为高速公路用户的部分用户 $N _ { k } ^ { 2 }$ 中进一步确定为高速路上的用户 $N _ { k } ^ { 3 }$ 。

g)对 $\cdot N _ { k } ^ { 3 }$ 部分用户再利用本文方法模型1的车辆速度计算方法计算平均速度值 $V _ { k } ^ { 3 }$ （号

h)根据经过平行公路噪声数据用户消除后的用户数据重新进行道路栅格的车辆平均速度的计算。计算公式如下：

$$
\begin{array} { r } { V _ { k } = \frac { N _ { k } ^ { 1 } } { N _ { k } ^ { 1 } + N _ { k } ^ { 3 } } \times V _ { k } ^ { 1 } + \frac { N _ { k } ^ { 3 } } { N _ { k } ^ { 1 } + N _ { k } ^ { 3 } } \times V _ { k } ^ { 3 } } \end{array}
$$

开始+移动信令数据基站数据高速路GIS数据★数据预处理/数据维护↓路网匹配，构建地理栅格系统，根据最短欧式距离，进行基站与高速公路的路段匹配高速公路用户路径匹配，识别出高速公路用户N0 是否为高速公路用户？YES  
计算两两轨迹点的行程 与行程距离反相  
距离差和行程时间差来 关的加权权值函计算单个速度值 数加权值与单个速度值进行乘积运算 1得到平均速度贡献值↓对道路栅格里的多个平均速度贡献 11值进行求和运算得到路段栅格最终的车辆平均速度 1 1SRSES-ESE当前平行公路的高速路道路栅格用户与历史时刻的前面不存在平行公路高速路道路栅格用户进行交集运算↓确定高速公 不确定部路部分用户 分用户将确定部分用户，按照本文方法模型一计算速度V，确定交通状态剔除用户对不确定部分用户，计算每个用户的速度值Vi+V1是否属于由V确定的交通状 NO态的速度范围YES按照用户数加权的速度计算方法重新计算平行路段的高速路道路栅格车辆平均速度结束

# 3 实验

# 3.1 实验条件介绍

本文选择重庆市G85成渝高速西环立交至永川收费站路段作为模型的实验试点路段，路段全长56公里，使用矩形框区域对路段进行对路段的框定，如图6所示。

![](images/6fb7d04538fc01cf0116b04aad5891d06be0d5e7df8aaaa04a81babee0348ac5.jpg)  
图6本文方法模型2方法流程  
图6G85高速路测试路段  
图7移动信令数据原始数据示例图

手机信令数据采集系统实时全天候采集试点高速路段周边的基站的移动信令数据并通过ActiveMQ消息机制实时分发到模型进行计算处理。其采集的原始移动信令数据的示例如图7所示：

1312114619940491061231231false86123123|false1231231false40491061231231true）451617 3591 461994049（0623|23（tale）55354 404910612312319940491561231231tro61994049106(231231talse)049106123123151491061231231toloe)4045186|23123|false）06123(231false04918613713961true）23123(false)20141 1154049|movelG_ 451201612214 [3142 53103．

由图7可知，原始数据中主要包括了用户ID、产生时间、基站位置、进去小区标准和切换原因等字段，特别的，jumpin表示手机用户进入小区覆盖区，jumpout则表示用户离开小区覆盖区，move表示在小区覆盖区中移动。

以移动信令数据为数据输入源，模型结果的验证采用安装在高速路旁的固定检测器数据进行与模型的输出结果数据验证比对，为了验证消除平行公路噪声数据方法模型的有效性，选择了具有平行公路的高速路路段的两个固定检测器，固定检测器可检测每5分钟内的瞬时平均速度。模型的性能指标采用平均绝对误差MAE，均方根误差RMSE，平均绝对百分比误差MAPE，计算公式如下：

$$
\begin{array} { r } { \mathrm { M A E } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \left| x _ { i } - x _ { i } ^ { ' } \right| } \end{array}
$$

$$
\begin{array} { r } { \mathrm { R M S E } = \sqrt { \frac { \sum _ { i = 1 } ^ { N } ( x _ { i } - x _ { i } ^ { ' } ) ^ { 2 } } { N } } } \end{array}
$$

$$
\begin{array} { r } { \mathrm { M A P E } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \left| \frac { x _ { i } - x _ { i } ^ { ' } } { x _ { i } } \right| } \end{array}
$$

其中：N为样本量数； $x _ { i }$ 为检测器的结果； $x _ { i } ^ { \prime }$ 为模型计算的结果。

# 3.2 结果验证分析

测试路段监测区域的移动信令数据流由某移动运营商提供，数据流经过ActiveMQ消息机制进行实时分发，每接收五分钟的信令数据后分发给数据处理模型经过2.1、2.2、2.3节的步骤处理后的数据再分别经过如下三种高速路车辆平均速度计算模型进行处理得到路段的平均车辆速度：a)文献[11]模型：传统车辆平均速度计算模型；b)本文方法模型1：融合路程加权车辆平均速度计算模型；c本文方法模型2：融合距离加权 $. +$ 平行公路干扰数据消除车辆平均速度计算模型。

在2.4节的本文方法模型1中，为了取得最好的计算结果，需要选择一个最合适的路程反相关的加权函数，常用的加权函数有路程倒数函数 $\frac { 1 } { S }$ 、路程平方倒数函数 $\frac { 1 } { S ^ { 2 } }$ 、高斯加权函数$e ^ { - \mathrm { \Phi } ( ^ { \mathsf { S } } / _ { \delta } ) ^ { \mathrm { \Phi } ^ { 2 } } }$ ,其中 S是指车辆行程距离。将2017年5月17日6：00 至22：00的数据分别输入到使用以上的三种加权函数的车辆平均速度计算方法模型和传统的车辆平均速度计算模型进行处理，取两个固定速度检测器所在的路段模型的计算结果与固定速度检测器数据进行对比分析，得到误差性能对比表如表3所示。

表3本文方法模型1性能误差对比表  

<html><body><table><tr><td>模型名称</td><td>速度检测器</td><td>MAE RMSEMAPE</td></tr><tr><td rowspan="2">文献[11]方法模型</td><td>1</td><td>16.312 19.247 0.187</td></tr><tr><td>2</td><td>17.584 20.329 0.193</td></tr><tr><td rowspan="2">本文方法模型1(加权)</td><td>1</td><td>8.945 11.643 0.122</td></tr><tr><td>2</td><td>9.912 13.642 0.135</td></tr><tr><td rowspan="2">本文方法模型1(加权)</td><td>1</td><td>8.547 11.476 0.113</td></tr><tr><td>2</td><td>8.957 12.243 0.121</td></tr><tr><td rowspan="2">本文方法模型1（e-(S/）²加权)</td><td>1</td><td>7.983 10.671 0.105</td></tr><tr><td>2</td><td>8.256 10.968 0.110</td></tr></table></body></html>

从表3可以看出，本文方法模型1的计算结果都优于文献[11]方法模型结果，验证了本文方法模型1提出的融合路程加权的改进车辆速度计算方法的有效性，并且使用 $e ^ { - \mathbf { \Phi } ( \mathbf { S } / \mathbf { \Phi } _ { \delta } ) }$ 的加权模型的计算结果最优，因此选择 $e ^ { - \mathbf { \Phi } ( { } ^ { \mathsf { S } } / \mathbf { \Phi } _ { \delta } ) }$ ²作为加权函数。

进一步考虑平行公路干扰数据的影响，在融合路程加权的车辆平均速度计算模型的基础上加入平行公路干扰数据消除方法模型得到融合路程加权 $. +$ 平行公路干扰消除的车辆平均速度计算模型，本文命名为方法模型2，将该模型结果和本文方法模型1的结果与两个固定测速仪数据进行对比分析，得到误差性能对比如表4所示。

表4本文方法模型二性能误差对比表  

<html><body><table><tr><td>模型名称</td><td>速度检测器</td><td>MAE</td><td>RMSE</td><td>MAPE</td></tr><tr><td rowspan="2">本文方法模型1</td><td>1</td><td>7.983</td><td>10.671</td><td>0.105</td></tr><tr><td>2</td><td>8.256</td><td>10.968</td><td>0.110</td></tr><tr><td rowspan="2">本文方法模型2</td><td>1</td><td>6.838</td><td>8.404</td><td>0.086</td></tr><tr><td>2</td><td>7.015</td><td>8.517</td><td>0.091</td></tr></table></body></html>

从表4可知，在加入了平行公路干扰消除后，模型的车辆速度计算结果的 MAE、RMES和MAPE 都得到了进一步的提升，该方法能有效的消除平行公路的噪声用户数据，避免了高速路临近的平行道路的噪声用户对高速路车辆速度计算的影响。

在选定了加权因子函数为高斯加权函数后，给出2017年5月17日6：00至22：00的本文方法模型1、本文方法模型2与测速仪1的车辆平均速度结果对比图和误差分布图，分别如下图8、9所示，本文方法模型1、本文方法模型2与测速仪2的车辆平均速度结果对比图和误差分布图，分别如下图10、11所示，从图8、10中可以看出经过平行道路噪声数据消除的本文模型2的结果跳动幅度变小，更加接近测速仪的结果。从误差分布图9可以看出本文方法模型1相对误差 $10 \%$ 以内的占比为 $74 \%$ ，相对误差 $10 \% { \sim } 2 0 \%$ 以内占比为 $23 \%$ ；本文方法模型2相对误差 $10 \%$ 以内占比为 $84 \%$ ，相对误差 $1 0 \% { \sim } 1 5 \%$ 以内占比为 $1 6 \%$ ；从误差分布图11可以看出本文方法模型1相对误差$10 \%$ 以内的占比为 $68 \%$ ，相对误差 $10 \% { \sim } 2 0 \%$ 以内占比为 $2 6 \%$ 本文方法模型2相对误差 $10 \%$ 以内占比为 $7 5 \%$ ，相对误差$1 0 \% { \sim } 1 5 \%$ 以内占比为 $2 5 \%$ ，可以明显看出，本文方法模型2相对本文方法模型1消除了部分 $20 \%$ 以上的误差占比，结果更为准确，进一步证明了本文方法模型2对于平行公路噪声数据消除的有效性。综合来说，本文方法模型2的计算结果平均绝对误差为 $9 \%$ 左右，比本文方法模型1的平均绝对误差降低了 $2 \%$ 左右，比文献[11]方法模型的平均绝对误差降低了 $10 \%$ 左右。

![](images/7709f698ad225c4e36fde05e91333558429c0d75a3fbdb5dd4ef7b1029087166.jpg)  
图8模型计算结果与测速仪1结果对比图

![](images/b1ef77b3621767f0ab41e05ddd641c6b72b5fbc681da8a3d05579e68092b153b.jpg)

图9模型误差分布图

![](images/fa2f85a727e16794522953de3108a551fdb1c5e56e27bdde626a91cbad99c037.jpg)  
图10模型计算结果与测速仪2结果对比图

![](images/20f8745b5872ee9f147fa2808f8b5c244a56092bc74b2769766362b41913582f.jpg)  
图11模型误差分布图

# 4 结束语

利用手机信令数据获取高速路道路交通信息对于智能交通系统的发展具有重要的意义。本文简述了移动手机信令数据的特点和基于移动手机信令数据获取高速公路车辆速度基本方法原理，根据物理运动学知识，针对手机信令数据产生不确定性和容易参杂噪声数据特别是平行道路噪声数据的特点，分别提出了一种融合路程加权的车辆速度计算方法模型，并在此方法之上进一步提出一种消除平行公路干扰数据的车辆速度计算方法。以MAE、RMSE和MAPE为性能指标与文献[11]传统方法模型进行相互的对比分析验证，选定高斯加权函数作为加权因子函数，并证明了本文方法模型的性能指标均优于传统方法模型。本文方法对于促进智能交通系统的发展具有重要的应用价值，并且如果需要大规模的实现，可考虑使用相关的大数据平台进行实现[12]。

参考文献：   
[1]Caceres N,Wideberg JP, Benitez FG.Review of traffic data estimations extracted from cellular networks [J].IET Intelligent Transport Systems, 2008,2 (3): 179-192.   
[2] 沈激，姜新农，周一．基于手机信令的高速公路拥堵信息自动识别[J]. 中国交通信息化,2015(S1):119-122.(Shen Lian,Jiang Xinnong,Zhou Yi. Automatic identification of freeway congestion information based on mobile signaling [J].Transportation Information Industry,2015 (S1):119-122.)   
[3]Wu Chei, Chen Chihua,Lin Bonyeh,et al. Traffic information estimation methods from handover events[J].Journalof Testing& Evaluation,2016, 44 (1S): 656-664.   
[4]ChangMingfeng,Chen Chihua,Lin Yibing,et al.The frequencyof CFVD speedreport for highwaytraffic[J].Wireless Communications& Mobile Computing,2015,15 (5): 879-888.   
[5]Demissie M G,Correia G HDA,Bento C. Intelligent road traffic status detection system through celllar networks handover information: An exploratory study[J]. Transportation Research,Part C,2013,32(4): 76-88.   
[6]Shen Yun,Dong Honghui,Jia Limin,et al.Amethod of traffic travel status segmentation based on position trajectories [C]// Proc of the 18th IEEE International Conference on Intelligent Transportation Systems.2015: 2877- 2882.   
[7]Chen Chihua,Chang Hsuchia,Su Chunyun,et al. Trafc speed estimation based on normal location updates and call arrivals from cellular networks [J].Simulation Modelling Practice& Theory,2013,35(6): 26-33.   
[8]Chang Hsuchia,Chen Chihua,Lin Bonyeh,et al.Trafc information estimation using periodic location update events [J]. International Journal of Innovative Computing Information & Control Ijicic,2013,9(5): 2031-2041.   
[9]Lai Weikuang,Kuo Tinguan, Chen Chihua. Vehicle speed estimation and forecasting methods based on celllar floating vehicle data [J].Applied Sciences,2016,6(2): 47.   
[10] Zhu Tongyu,Song Zhixin,Wu Dongdong,et al. A novel freeway traffic speed estimation model with massive cellular signaling data[J]. International Journal of Web Services Research,2016,13(1): 69-87.   
[11]刚红润，沈志纲，刘承华，等．一种基于手机信令的高速路车速估计算 法[J].电子世界,2017(17):46-46.(Gang Hongrun,Shen ZhiGang,Liu Chenghua,et al. Analgorithm ofhighway speed estimation based oncellular signaling[J].ElectronicsWorld,2017(17): 46-46.)   
[12] 杨杰，朱邦培，吴宏伟．基于 Storm 的高速公路实时交通指数评估方法 的研究与实现[J].计算机应用研究,2017(9):2707-2713.(Yang Jie,Zhu Bangpei,Wu Hongwei.Research and realization of evaluationmethod for freewayreal-time trafc index based on storm [J].Application Research of Computers,2017 (9): 2707-2713. )