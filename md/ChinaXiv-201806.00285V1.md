# FAST工程综合测试微波暗室设计与实现

胡浩‘，张海燕1²，甘恒谦1²，岳友岭1²，黃仕杰¹，宋金友‘(1.中国科学院国家天文台，北京100012；2.中国科学院FAST重点实验室，北京 100012)

# 摘要

通过对尖劈吸波材料的选型和优化设计，建造完成 FAST工程综合测试微波暗室。满足国军标(GJB151B）和民标电磁兼容测试要求，在500MHz以上频段满足天线测试环境要求。可为500米口径球面射电望远镜（FAST）进行电磁兼容及天线性能测试提供所需的电磁环境和测试条件。通过有效消除外来的电磁波和各种内部反射干扰，以获得可靠规范的测试数据。该综合测试微波暗室可满足国标和相关国际标准的电磁兼容测试及天线测试需求，能实现3米法和天线性能测试环境保障。

关键词：综合测试微波暗室，FAST，吸波材料。

中图分类号：TN014 文献标识码：A 文章编号：1672-7673（2018）

# 1简介

国家重大科技基础设施——5O0 米口径球面射电望远镜（Five-hundred-meter Aperture Spherical radio Telescope，FAST）已于 2016年9月建成，正在进行调试和试观测，并已取得初步成果[]。FAST的高灵敏度使得它极易受到来自自身电气和电子设备的电磁干扰，为此望远镜的电磁兼容设计和整改非常重要[2]开展电磁兼容设计和整改的基础，是对干扰设备的电磁兼容特性进行测试和评估[3，而电磁兼容测试离不开微波暗室4。FAST 台址位于贵州省黔南州平塘县大窝幽洼地，地处偏远山区，电波环境非常安静，是开展天文观测的合适地点。望远镜的建设和运行需要开展一系列的电磁兼容测试维护及研究工作。FAST的电磁兼容试验性测试及研究是长期及耗时的工作。同时，为适应开展控制设备（如配电、索驱动、促动器控制及馈源舱内设备都必须管控认证电磁兼容性接入许可）辐射影响检测及FAST 馈源等微波器件标定测试的多功能需求，有效合理利用FAST现场实验室的基础配套，建设多用途综合测试微波暗室非常必要，该微波暗室的建设将对FAST的正常运行提供有效支撑。

# 2方案设计和实现

# 2.1FAST综合测试微波暗室性能指标

FAST 综合测试微波暗室在FAST观测基地2号实验室内，规划建筑面积 $1 2 . 0 \mathrm { m } \times 1 2 . 0 \mathrm { m }$ ，作为多用途微波暗室，需要满足军标GJB151B试验要求；满足民标3米法电磁兼容性试验要求；兼顾小天线测试要求。

电磁兼容微波暗室指标要求[5]：

（1）归一化场地衰减

3m 距离测试时，静区直径为 $2 \mathrm { m }$ ，高度 $2 \mathrm { m }$ 的静区内从 $3 0 \mathrm { M H z }$ 至1GHz 测量的归一化场地衰减与理论值的偏差在±4dB 之内。（2）场地电压驻波比在 $1 \mathrm { G H z } \sim 1 8 \mathrm { G H z }$ 频率范围内，测试距离 $3 \mathrm { m }$ ，测试直径 $2 \mathrm { m }$ ，高度 $2 \mathrm { m }$ 的静区驻波比 ${ \leqslant } 6 . 0 \mathrm { { c } }$ B。（3）场地均匀性在 $1 . 5 \mathrm { m } \times 1 . 5 \mathrm { m }$ 假想垂直面上 $7 5 \%$ 的场强幅值偏差应在 $0 { \mathrm { - } } 6 \mathrm { d B }$ 。（4）背景噪声

在微波暗室内进行测试时，EUT 断电而辅助设备通电，测得的内部电磁环境电平比GJB151A一$9 7 ^ { \textcircled { 2 } }$ 规定的极限值低 6dB或 CISPR 22/CLASS-B 规定的极限值低 10dB。

天线微波暗室指标要求：

(1)微波暗室静区性能  
本微波暗室在满足3m法电磁兼容测试的前提下兼顾天线远场测试，具体要求如下：（500MHz以下不作要求）：500M-1GHz：优于20dB;1-3GHz：优于25dB;3-6GHz：优于35dB;6-10GHz：优于45 dB;$1 0 \mathrm { - } 1 8 ~ \mathrm { H z }$ ：优于50 dB。  
(2)静区交叉极化电平：≤-25dB( $\geqslant$ 1GHz）。  
(3)场幅均匀性：纵向 $\pm 2$ dB、横向±1 dB。

# 2.2、天线测试的吸波布局设计

2.2.1微波暗室技术指标：

$\spadesuit$ 工作频率： $0 . 5 { \sim } 1 8 \mathrm { G H z }$   
$\bullet$ 微波暗室尺寸： $1 1 \mathrm { m } \times 8 \mathrm { m } \times 7 . 2 \mathrm { m }$ （长 $\times$ 宽 $\times$ 高）;$\spadesuit$ 微波暗室最大测试距离： $R = 5 \mathrm { m }$   
$\spadesuit$ 静区尺寸： $1 . 0 \mathrm { m } \times 1 . 0 \mathrm { m } \times 1 . 0 \mathrm { m }$   
$\bullet$ 发射天线增益：

Table 1The launch antenna gain table is adopted.   

<html><body><table><tr><td>频率 (GHz)</td><td>0.7</td><td>1. 0</td><td>3.0</td><td>6.0</td><td>10.0</td><td>18.0</td><td>40.0</td></tr><tr><td>增益 (dBi)</td><td>10</td><td>10</td><td>15</td><td>15</td><td>15</td><td>15</td><td>15</td></tr></table></body></html>

Table 2Microwave darkroom Quiet zone performance.

表2微波暗室静区性能  

<html><body><table><tr><td>频率 (GHz)</td><td>0.5</td><td>1.0</td><td>3.0</td><td>6.0</td><td>10.0</td><td>18.0</td></tr><tr><td>静区反 射电平 (dB)</td><td>≤-20</td><td>≤-25</td><td>≤-35</td><td>≤-45</td><td>≤-50</td><td>≤-50</td></tr></table></body></html>

2.2.2远场测试微波暗室仿真计算：

（1）静区性能计算条件

$\spadesuit$ 工作频率： $0 . 5 { \sim } 1 8 \mathrm { G H z }$   
$\spadesuit$ 微波暗室尺寸（长 $\times$ 宽 $\times$ 高）： $1 1 \mathrm { m } \times 8 \mathrm { m } \times 7 . 2 \mathrm { m }$ $\spadesuit$ 静区尺寸： $1 . 0 \mathrm { m } \times 1 . 0 \mathrm { m } \times 1 . 0$ m；  
$\spadesuit$ 测试距离： $\scriptstyle { \mathrm { R = 5 m } }$   
$\spadesuit$ 微波暗室可测最大天线口径D：

表1采用的发射天线增益表  
表3不同频率下可测最大天线口径  

<html><body><table><tr><td>频率 （GHz）</td><td>0.5</td><td>1. 0</td><td>3.0</td><td>6.0</td><td>10</td><td>18</td></tr><tr><td>天线口 径（m）</td><td>1. 0</td><td>0.86</td><td>0.50</td><td>0.35</td><td>0.27</td><td>0.20</td></tr></table></body></html>

Table 3The maximum antenna aperture can be measured at different frequencies.

（2）静区性能仿真计算

微波暗室静区性能设计，采用国际通用的射线跟踪法进行仿真计算。根据微波暗室的大小、吸波材料的布局、发射接收天线的位置等相关参数代入微波暗室性能仿真计算软件，对微波暗室的性能进行评估。

(a)微波暗室静区中心和主反射区吸波材料高度的确定

通过设定不同的微波暗室静区中心位置和不同高度的吸波材料，进行仿真优化设计，最终确定静区中心到后墙的距离为 $3 . 6 \mathrm { { m } }$ ，高度2.5m；微波暗室的墙面、天花板采用FAH-1600 吸波材料，地面费涅尔区选用 $7 0 0 \mathrm { m m }$ 高的FA-700高性能角锥吸波材料，其它区域选用 $5 0 0 \mathrm { m m }$ 高的FA-500 高性能角锥吸波材料。

(b)微波暗室静区性能的仿真设计结果：

经过反复计算优化，最后确定本微波暗室的静区性能计算结果如下：

表4微波暗室静区性能计算结果  
Table 4Performance calculation results of microwave darkroom.   

<html><body><table><tr><td>频率（GHz）</td><td>0.5</td><td>1.0</td><td>3.0</td><td>6.0</td><td>10</td><td>18</td></tr><tr><td>静区反射 电平(dB)</td><td>-22. 73</td><td>--29.53</td><td>-39.1</td><td>-49.5</td><td>-53.93</td><td>-51.49</td></tr></table></body></html>

2.2.3结构设计

在结构方面，综合测试微波暗室包括3米法微波暗室屏蔽房，另配2个辅助屏蔽室（测量控制室和功放室)，各室形状为矩形，布局图及结构尺寸如图1。综合微波暗室内还包括供电系统、信号滤波器、电源滤波器、尖劈吸波材料、铁氧体、转台及控制系统、天线升降台及控制系统、消防、视频监控等。各屏蔽室共壁，以便减少信号转接板数量与信号电缆长度。

整个六面体的网格框架构成了屏蔽微波暗室主体自支撑结构。主体框架的设计经过了详细、可靠的结构计算，考虑了框架变形控制和结构稳定性问题，并且充分考虑了按8级烈度抗震设防。

![](images/529fe48aed68984695160b60bc834ca45ca4ae0b98c93256f357aa16628f4e88.jpg)  
图1综合测试微波暗室布局

Fig.1Comprehensive test of microwave darkroom layout

# 2.3关键技术及创新点

FAST综合测试微波暗室作为多用途微波暗室。其设计难点是：

电磁兼容性微波暗室试验具有超宽频带。辐射性能测试：军标 $8 0 \mathrm { M H z } { \sim } 4 0 \mathrm { G H z }$ ；民标 30MHz～18GHz。为了满足与开阔场比对的误差要求，电磁兼容性测试对微波暗室的吸波性能相对天线测试的要求低，整个测试频带吸波性能在 $- 1 5 { \sim } - 2 0 \mathrm { d B }$ 就可以；而天线测试频带相对较窄，静区反射电平要求尽量低，对吸波性能要求高，要在-30dB以上，甚至要达到-55dB。

目前，国内外微波暗室用吸波材料主要有两种：(1)电介质材料，即角锥吸波材料；(2)磁性材料，即铁氧体瓦。角锥材料可以从低频（30MHz））到高频（300GHz)，都可以做成高吸收性能（可达-55dB)，但要满足30MHz吸波性能-15dB，其高度约3m；铁氧体瓦在低频（30MHz～1GHz）具有很好的吸波性能，高频性能很差（见图2)，厚度只有6.5mm左右，相对角锥材料厚度，几乎可以忽略不计。在0.8GHz以上频率吸波性能不能满足天线测试的需要，所以几乎没有天线微波暗室采用铁氧体瓦建设微波暗室（500MHz以上）。

将电磁兼容性测试和天线测试组合在一起，建设微波暗室不是最佳选择。为了满足FAST测试的特殊需要，使用大型空心截锥吸波材料，对截锥吸波材料进行进一步优化设计，特别是高频吸波性能的优化，使其在低频（30MHz），吸波性能达-15dB，达到铁氧体瓦吸波性能；高频（500MHz以上)，吸波性能-30dB以上；即可满足3米法 EMC试验，也可兼顾天线测试需要的新型截锥吸波材料FAH-1600，吸波性能测试结果见图3。从实际测试曲线看：FAS-1600截锥吸波材料的吸波性能达到或超过铁氧体瓦的吸波性能，完全可以满足FAST3米法综合微波暗室的建设需求。

![](images/f35bc4d52fec89977352e98f28fced205141e312389773ace9aa7db50fe59031.jpg)  
图2铁氧体瓦的吸波性能曲线

Fig.2The absorption performance curve of ferrite tiles.

![](images/4490a0b55fd2c9e33a6451555e32e9ea3e1d08282ad190b594d5440853682201.jpg)  
图3FAH-1600吸波材料测试曲线

Fig.3Fah-1600 absorbent material test curve.

综合以上分析，在电磁屏蔽室所有墙面和天花板铺设高度为 $1 6 0 0 \mathrm { m m }$ 的吸波材料，型号FAH-1600角锥吸波材料，地面部分铺设可移动式材料 $1 4 . 4 \mathrm { m } ^ { 2 }$ ，高度 $3 0 0 \mathrm { m m }$ ，型号FA-300高性能角锥吸波材料，用于CISPR16-1-4(2007)③标准对满足场地电压驻波比的测试。可满足FAST综合测试微波暗室性能指标要求。

# 2.4FAST综合测试微波暗室工程实现

FAST综合测试微波暗室工程包括5方面。

（1）微波暗室建设在室内，空间狭小，所有钢材在使用前进行除锈防腐处理，施工过程中同步  
进行防腐补漆。保证工程质量。（2）吸波工程：微波暗室屏蔽体及附属设施安装完成后，屏蔽检测合格，进行墙面及屋顶的尖  
劈吸波材料安装。（3）装饰工程：控制室及功放室屏蔽检测合格后进行室内装修。（4）附属设施：包含消防报警系统、通风空调系统、供配电系统、信号滤波器及接口装置、电  
视监视系统、灯光照明系统、接地系统。（5）配套设备：包含转台、天线塔、升降台。

# 3FAST综合测试微波暗室性能检测

综合测试微波暗室建设完成后，进行微波暗室性能测试，测试结果达到优秀水平，测试情况如下：

![](images/cc3bed733c98b8b16cc35fe4d4e3237be251a34da61e236e176f124c579872fc.jpg)  
图4FAST综合测试微波暗室性能检测

Fig.4 FAST comprehensive test of microwave darkroom performance.

# 3.1归一化场地衰减

按照标准GB9245-2008《信息技术设备的无线电骚扰限值和测量方法》规定的测试方法进行归一化场地衰减的垂直极化和水平极化测量。垂直极化测试结果见图5。

![](images/0e31519a72d02f7b22530b340c50d32f72d67abc7fd1f6b473f4317945217e3e.jpg)  
图5垂直极化归一化场地衰减

Fig.5Vertical polarization normalized site attenuation.

# 3.2场地电压驻波比

指标要求：在 $1 \mathrm { G H z } \sim 1 8 \mathrm { G H z }$ 频率范围内，测试距离3m，测试直径 $2 \mathrm { m }$ ，高度2m的静区驻波比≤6. 0dB。

测试方法：按照CISPR16-1-4：2008-01标准规定，测试距离 $3 \mathrm { m }$ ，测试直径 $1 . 5 \mathrm { m }$ ，高度 2m 的静区场地电压驻波比不大于6dB。要求验收测试发射天线为全向天线，测试接收天线为LPDA天线。

测试结果见图6，满足设计要求 ${ \leqslant } 6 . 0 \mathrm { d B }$ （在 $1 2 . 5 \mathrm { G H z }$ 附近存在两点凸起，是测试设备不匹配所引起）。

![](images/66e9cdfaae4a5930d986800fd40a7b67205f0d8aa404fd7f19213d26048a86e5.jpg)  
图6场地电压驻波比

Fig.6Field voltage standing wave ratio.

# 3.3场地均匀性

按照GB/T17626.3-2006《电磁兼容试验和测量技术射频电磁场辐射抗扰度试验》④要求，在测试转台之上 $0 . 8 \mathrm { m } { \sim } 2 . 3 \mathrm { m }$ 范围 $1 . 5 \mathrm { m } \times 1 . 5 \mathrm { m }$ 的垂直平面内，16个测试点中 $7 5 \%$ （ $\mathrm { \cdot 1 G H z } \mathrm { \sim } 1 8 \mathrm { G H z }$ 频率范围为 4 个端点 $1 0 0 \%$ ）的点场地均匀性在 $0 \mathrm { d B } \mathrm { \sim } \mathrm { + } 6 \mathrm { d B }$ 之间，满足测试要求。测试结果见图7、图8。

![](images/afa19843c03bd8458752b32a5e758a4220946a1b19e99fcc903dfb13141b0b24.jpg)  
图7场地均匀性垂直极化 $7 5 \%$

![](images/58177cf1aa863821924b35b3b674c6bf8d28ac31b7525d9751f18245bd5b29ff.jpg)  
Fig.7The uniformity of the site is $7 5 \%$ vertically polarized.   
图8场地均匀性垂直极化 $1 0 0 \%$

Fig.8The uniformity of the site is $1 0 0 \%$ vertical.

# 3.4背景噪声

在微波暗室内进行测试时，EUT 断电而辅助设备通电，测得的内部电磁环境电平比GJB151A一97规定的极限值低14dB或CISPR 22/CLASS-B规定的极限值低18dB。

# 3.5电磁屏蔽效能检测

测试方法：GB/T12190-2006 电磁屏蔽室屏蔽效能的测量方法。  
测试频点：30MHz、100MHz、345MHz、500MHz、1GHz、2.575GHz、18GHz。  
测试结果见表5。

表5暗室屏蔽效能检测结果  
Table 5Detection results of dark room shielding effectiveness.   

<html><body><table><tr><td>测试频点</td><td>30MHz</td><td>100MHz</td><td>345MHz</td><td>500MHz</td><td>1GHz</td><td>2.575GHz</td><td>18GHz</td></tr><tr><td>屏蔽效能</td><td>108</td><td>119</td><td>125</td><td>125</td><td>106</td><td>114</td><td>101</td></tr></table></body></html>

# 3.6微波暗室静区性能

测试方法：按照GJB6780-2009 微波暗室性能测试方法。  
测试频点：500MHz、2GHz、5GHz、10GHz、18GHz。

本微波暗室在满足3m法电磁兼容测试的前提下兼顾天线远场测试，实测数据满足设计要求，测试结果如下：

(a)静区性能（500MHz以下不作要求）：500M-1GHz：优于20.6dB;1-3 GHz：优于25.5dB;3-6GHz：优于35.7dB;6-10GHz：优于 50.8 dB;$1 0 \mathrm { - } 1 8 ~ \mathrm { H z }$ ：优于50.9 dB。  
(b)静区交叉极化电平：≤-29dB( $\geqslant$ 1GHz）。  
(c)场幅均匀性：纵向±1.76dB、横向±0.89dB。

# 4结论

FAST 综合测试微波暗室通过尖劈吸波材料的优化设计，选用1600mm高（FAH-1600）大型空心截锥吸波材料铺设所有墙面及天花板，地面部分铺设可移动式高性能复合型角锥吸波材料：高度$3 0 0 \mathrm { m m / 5 0 0 m m / 7 0 0 m m } ,$ 型号FA-300/FA-500/FA-700，在有限的室内空间实现了集电磁兼容测试微波暗室和天线测试微波暗室于一体，满足FAST望远镜特殊的测试需求。微波暗室各屏蔽室共壁，减少信号转接板数量与信号电缆长度，通过合理的布局和严格的施工过程管控，FAST综合测试微波暗室性能通过测试，性能指标达到优秀水平。本综合测试微波暗室内配备的测试平台、仪器设备包括了电磁兼容测试系统和天线测试系统，主要设备采购国外进口，部分器件共用，在8GHz以下频率范围均满足相关标准的测试要求.

# 参考文献

[1]Nan R D，Li D， Jin C J，et al. The Five-Hundred Aperture Spherical Radio Telescope (FAST) Project[J]. International Journal of Modern Physics D, 2011, 20 (6) :989-1024.

[2]Deboer D R, Cruz-Pol S L， Davis M M, et al. Radio frequencies: policy and management[J]． IEEE Transactions on Geoscience & Remote Sensing， 2013， 51(10):4918-4927.

[3]黄仕杰,张海燕，甘恒谦,等.FAST访客电子设备电磁干扰分析[J]．天文研究与技术，2017,14(2) :268-274.

Huang Shijie， Zhang Haiyan， Gan Hengqian，et al. A study of evaluation on radio interference of FAST visitor’ s electronic devices[J]. Astronomical Research & Technology, 2017， 14(2) :268-274.

[4]杨文麟，雷炳新,苏洋.电波暗室综述[J].微波学报,2012(S3)：431-433.

Yang Wenlin，Lei Bingxin， Su Yang. Summary of anechoic chamber[J]. Journal of Microwaves,2012(S3): 431-433..

[5]李莹莹，闻映红.电波暗室的分类及半电波暗室的性能评价指标[J].安全与电磁兼容，2005(S1) :5-7.

Li Yingying,Wen Yinghong.Classification of anechoic chamber and technical requirements for semi-anechoic chamber[J].Safety & EMC， 2005(S1) :5-7.

# FAST Engineering Comprehensive test Microwave Darkroom Design and Implementation

HuHao1, Zhang Haiyan12,Gan Hengqian1,2, Yue youling1,2, HuangShijie1, Song Jinyou1 (1.National Astronomical Observatories, Chinese Academy of Sciences,Beijing 100012,China;2.CASKey Laboratory of FAST,National Astronomical Observatories, Chinese Academy of Sciences,Beijing 1oool2, China.Email: huhao@nao.cas.cn)

# Abstract

Through the selection and optimization design of the wedge absorbing material, the FAST engineering comprehensive test microwave darkroom is completed.Meet the requirements of (GJB151B） and civil standard electromagnetic compatibility test,and meet the requirements of the antenna test environment in the frequency band above 5OoMHz.The electromagnetic environment and test conditions are provided for the electromagnetic compatibility and antenna performance test of the Five-hundred-meter Aperture Spherical radio Telescope (FAST).Through effective elimination of external electromagnetic wave and various internal reflection interference,to obtain reliable and standardized test data.Thecomprehensive test microwave darkroom can meet the requirements of electromagnetic compatibility test and antenna testing of national standard and relevant international standards,and can realize the three meter method and the antenna performance test environment protection.

Key words: comprehensive test microwave darkroom, FAST, absorbing material.