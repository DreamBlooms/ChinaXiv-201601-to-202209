# 基于CloudSat资料分析北疆强降雪天气的云结构特征

王智敏'，冯婉悦²，李圆圆'，储长江³，徐文霞'，陈勇航4（1新疆维吾尔自治区人工影响天气办公室,新疆乌鲁木齐830002；  
2新疆维吾尔自治区气象技术装备保障中心,新疆乌鲁木齐830002;  
3新疆气象局,新疆乌鲁木齐 830002；4 东华大学环境科学与工程学院,上海 201620)

摘要：利用 NASA 发布的 2008—2015 年CloudSat卫星的 2B-CWC-RO、2B-CLDCLASS、2C-SNOW-PROFILE和地面气象站的观测资料，对北疆沿天山及其周边区域内21次强降雪天气降雪前和降雪期间卫星过境时云宏微观特征进行了对比分析。通过将研究区域分为北疆沿天山西部和中部地区进行分析，结果表明：（1）降雪前和降雪期间的云类型以层云、积云、高层云和深对流云为主。（2）降雪前冰粒子等效半径均值分布在 $5 8 . 6 5 \sim 6 7 . 2 9 ~ \mu \mathrm { m }$ 之间，冰粒子数浓度的均值在41.2～76.$5 \mathrm { ~ L ~ } ^ { - 1 }$ 之间,冰水含量的均值在 $2 5 . 4 \sim 1 3 5 . 1 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 之间,雪水含量均值在 $2 8 . 0 \sim 8 8 . 0 \mathrm { ~ m g ~ } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ （204号之间，降雪强度均值在 $0 . 0 8 \sim 0 . 3 6 ~ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ 之间。（3）降雪前冰粒子等效半径、冰粒子数浓度、冰水含量、雪水含量和降雪强度均值分别比降雪期间大 $2 . 9 \% . 6 . 2 \% . 3 4 . 4 \% . 3 6 . 4 \%$ 和 $1 8 . 7 \%$ ，且高值区主要集中在北疆沿天山西部地区。

关键词：CloudSat；强降雪；宏微观物理量；北疆区域文章编号： 1000 -6060(2019)02 -0244 -08(0244\~0251)

开展人工增雪作业以开发利用空中云水资源已成为缓解新疆部分地区淡水资源短缺的一项重要措施，然而长期以来，关于降雪云系的特征变化主要依赖于地面观测站点的人工目测、偶尔小范围的飞机穿云观测以及传统卫星的整层大气的平均观测，缺少对云层内部垂直方向上的云宏微观物理参量的探测，使得人工增雪作业的不确定性增大。

目前有许多学者从天气学角度对北疆的降雪天气过程进行了研究，取得了降雪天气的时空分布、形成机理、天气背景场以及气候特征变化等许多结论[1-5],其中张俊兰等[6]利用长时间序列的北疆51个站点的降水量资料和NCEP再分析资料，将北疆降雪分为三种类型，分别为北疆西部及沿天山型、北疆北部及东部型和北疆西部型及西天山型，并分析了降雪天气的水汽源地和水汽输送路径等。于晓晶等[7]利用WRF中尺度模式中的WSM6、Lin、WDM6和Thompson四种不同的云微物理方案对新疆一次冷锋暴雪过程进行了模拟并对预报结果进行了比较分析。杨莲梅等[8]和刘惠云等[9]利用站点资料和NCEP再分析资料对2010年北疆一次持续性暴雪的大气环流特征和物理量场进行了诊断分析等。

近年来，许多研究人员利用CloudSat卫星资料的产品对不同区域和不同云类的宏微观特征进行了研究[10-18],如陈勇航等[19]利用CloudSat 的 2B-CLDCLASS、2B-CWC-RO 和2B-GEOPROF产品分析了中天山附近的强降雨天气过程中的冰水含量时空分布特征等信息。刘岩等[20]利用CloudSat 和Aqua卫星资料分析了北疆地区一次暴雪天气过程云类型、冰粒子等效半径和低层云高等参数的空间分布情况。陈英英等[21]基于CloudSat 的 2B-GEOPROF产品、探空数据和地面观测数据等分析了一次冻雨天气过程，给出了雨一雪天气转变过程中的温湿度变化以及冻雨形成过程中零度层亮带的演变特征等信息。MARK 等[22]利用CloudSat 资料中的2B-

CLDCLASS和2C-SNOW-PROFILE产品，通过统计分析了全球范围的降雪过程，得出了以浅层积云为主的降雪过程占全球降雪天气过程的 $36 \%$ ,且存在明显不同的海洋与大陆地域特点。SHENG等[23]和MATROSOV 等[24]通过研究发现基于CloudSat上的W 波段毫米波云雷达探测的降雪量产品与地面雪量计和地面S波段雷达所测量的降雪强度和降水信息等的估计值较为一致,2C-SNOW-PROFILE产品可以有效地用于降雪过程分析。

可见针对北疆沿天山及其周边区域降雪天气中云的宏微观物理属性的空间垂直分布的定量研究尚少见。而云的宏微物理属性能显著影响云的结构变化及降雪过程的演变，因此本文应用高分辨率的CloudSat卫星产品等资料，对发生在北疆沿天山地区的21次强降雪天气的云结构特征进行了分析，以期更加深入地认识强降雪的物理机制和更科学地确定人影作业潜力区提供参考依据。

# 数据来源与研究方法

# 1.1 数据来源

CloudSat卫星于2006年由美国宇航局发射上天，是第一颗可以对云层特征进行全球观测的卫星。其上搭载的云廓线雷达（CloudProfilingRadar,CPR），它的频率为94GHz属于W波段的云雷达，它的灵敏度是标准天气雷达的1000倍，采用毫米波段多普勒雷达可以实现由上至下对薄云、浓厚云以及台风云系等不同特征云系的垂直剖面观测，包括云的厚度、云层顶部和云层底部高度、观测云层的形成和演变过程,确定云对气候环境的影响程度；还可以测量云剖面上的液态水和冰水含量以及云的光学特征等，从而确定降雨量等信息。以下为其卫星参数(表1)。

# 1.2 卫星产品

传统的卫星辐射计的分析结果在很大程度上忽略了关于云层垂直分布的信息，仅能观测到大气和地表发射和反射的辐射能量。所以传统的卫星数据只能粗略地估计云的位置和垂直范围。而CloudSat卫星上的主动遥感毫米波云雷达则可以探测云层垂直方向上几何剖面中水汽等云层内部的详细信息。本文主要利用CloudSat云雷达的星下像素点为1.4$\mathrm { k m }$ （横道宽度） $\times 1 . 8 ~ \mathrm { k m }$ （沿道宽度），产生的垂直雷达反射率因子的分辨率为 $2 4 0 \mathrm { ~ m ~ }$ 。CloudSat卫星的基本观测数据1B产品为卫星所搭载的W波段云雷达所直接观测得到的数据，2B、2C产品是基于1B数据产品再结合其他卫星产品（MODIS、CALIPSO等)联合反演得到的产品，如表2所示。

表1卫星参数信息  
Tab.1 Parameter information of the satellite   
表2卫星产品信息  

<html><body><table><tr><td>参数</td><td>参数设置</td><td>参数</td><td>参数设置</td></tr><tr><td>正常频率</td><td>94 GHz</td><td>天线长度</td><td>1.95 m</td></tr><tr><td>脉冲宽度</td><td>3.3 μsec</td><td>积分时间</td><td>0.3 sec</td></tr><tr><td>脉冲重复频率</td><td>4 300 Hz</td><td>垂直分辨率</td><td>500m</td></tr><tr><td>最小可探测强度</td><td>-26 dBz</td><td>水平分辨率</td><td>1.4 ×2.5 km</td></tr><tr><td>数据窗</td><td>0~25km</td><td>数据率</td><td>15 kbps</td></tr></table></body></html>

Tab.2Product information of the satellite   

<html><body><table><tr><td>产品编码</td><td>产品名称</td></tr><tr><td>1B-CPR-FL</td><td>雷达后向散射剖面(初级产品)</td></tr><tr><td>1B-CPR</td><td>雷达后向散射剖面</td></tr><tr><td>2B-GEOPROF</td><td>云的几何剖面</td></tr><tr><td>2B-CLDCLASS</td><td>云的分类</td></tr><tr><td>2B-CWC-RO</td><td>云水含量</td></tr><tr><td>ECMWF-AUX</td><td>欧洲中心相对湿度、温度等产品</td></tr><tr><td>2C-SNOW-PROFILE</td><td>降雪产品</td></tr></table></body></html>

# 1.3 个例选取

本文所选的研究区域为位于 $4 1 ^ { \circ } \sim 4 8 ^ { \circ } \mathrm { ~ N ~ } . 7 7 ^ { \circ } \sim$ $8 9 ^ { \circ } \mathrm { ~ E ~ }$ 之间的北疆沿天山及其附近区域。按新疆24h 累计降水量分级标准,北疆地区大雪的降水量为$6 . 1 \sim 1 2 . 0 ~ \mathrm { m m }$ ,大到暴雪为 $9 . 1 \sim 1 8 . 1 \ \mathrm { m m }$ ，暴雪为$1 2 . 1 \sim 2 4 . 0 ~ \mathrm { m m }$ 。首先筛选出 2008—2015 年北疆区域所有 $2 4 \mathrm { ~ h ~ }$ 降水量达到大到暴雪的站点，再参照降雪的具体日期以及站点经纬度筛选出有CloudSat轨道过境的个例作为研究对象。最终选取了21个大到暴雪的个例,代表研究区域内的强降雪天气过程，其中12个为降雪正在发生时卫星过境个例，9个为降雪发生前卫星过境个例，如表3所示。

# 1.4 研究方法

通过处理统计2008—2015年北疆地区20个地面气象观测站的天气现象观测资料、CloudSat卫星数据中的2B-CLDCLASS中的云分类信息、2B-CWC-RO中的冰粒子等效半径（IER）、冰水含量（IWC）、冰粒子数浓度（INC）、和2C-SNOW-PROFIL中的雪水含量(SWC)和降雪强度(SR)产品，分析该区域21次强降雪天气降雪前和降雪过程中的云宏

# 表3强降雪个例

Tab.3 Examples of heavy snows   

<html><body><table><tr><td>序号</td><td>个例时间</td><td>过境气 象站点</td><td>24h降雪 量／mm</td><td>卫星过 境时间</td><td>天气 情况</td></tr><tr><td>1</td><td>2008-02-22</td><td>托里</td><td>11.0</td><td>15 :33</td><td>降雪中</td></tr><tr><td>2</td><td>2009-03-08</td><td>温泉</td><td>22.0</td><td>04:20</td><td>降雪前</td></tr><tr><td>3</td><td>2010-03-15</td><td>托里</td><td>17.0</td><td>15:35</td><td>降雪中</td></tr><tr><td>4</td><td>2010-03-20</td><td>托里</td><td>53.0</td><td>04 :46</td><td>降雪前</td></tr><tr><td>5</td><td>2011-02-10</td><td>温泉</td><td>7.0</td><td>04:50</td><td>降雪前</td></tr><tr><td>6</td><td>2011-03-16</td><td>特克斯</td><td>17.0</td><td>15 :45</td><td>降雪中</td></tr><tr><td>7</td><td>2011-04-03</td><td>托里</td><td>20.0</td><td>15 :34</td><td>降雪前</td></tr><tr><td>8</td><td>2012 -11-29</td><td>昭苏站</td><td>19.0</td><td>15 :50</td><td>降雪前</td></tr><tr><td>9</td><td>2012-12-03</td><td>小渠子</td><td>27.0</td><td>15:25</td><td>降雪前</td></tr><tr><td>10</td><td>2013-11-22</td><td>乌鲁木齐</td><td>56.0</td><td>15 :20</td><td>降雪中</td></tr><tr><td>11</td><td>2014-01 -28</td><td>昭苏</td><td>20.0</td><td>15 :45</td><td>降雪中</td></tr><tr><td>12</td><td>2014-01-30</td><td>托里</td><td>31.0</td><td>15:30</td><td>降雪中</td></tr><tr><td>13</td><td>2014 -02 -24</td><td>呼图壁</td><td>10.0</td><td>15 :25</td><td>降雪中</td></tr><tr><td>14</td><td>2014-12 -07</td><td>精河</td><td>20.0</td><td>15 :40</td><td>降雪前</td></tr><tr><td>15</td><td>2014-11 -09</td><td>昭苏</td><td>79.0</td><td>04 :50</td><td>降雪中</td></tr><tr><td>16</td><td>2014-11 -25</td><td>昭苏</td><td>80.0</td><td>04:50</td><td>降雪中</td></tr><tr><td>17</td><td>2015-03-31</td><td>小渠子</td><td>22.0</td><td>15 :25</td><td>降雪中</td></tr><tr><td>18</td><td>2015-11 -17</td><td>乌苏</td><td>34.0</td><td>15:30</td><td>降雪前</td></tr><tr><td>19</td><td>2015 -11 -22</td><td>昭苏</td><td>19.0</td><td>15:50</td><td>降雪前</td></tr><tr><td>20</td><td>2015-12-10</td><td>精河</td><td>62.0</td><td>15:40</td><td>降雪中</td></tr><tr><td>21</td><td>2015-12-12</td><td>沙湾</td><td>21.0</td><td>15:25</td><td>降雪中</td></tr></table></body></html>

微观物理量的在垂直方向上的分布特征等信息。根据降雪天气所发生的空间位置和卫星过境站点信息，将研究区域分成了北疆沿西天山型和北疆沿中天山型两类。

# 2结果与分析

# 2.1强降雪过程中云的类型

NASA的研究人员把空间主动和被动传感数据结合起来，根据云的水平和垂直属性、水汽比湿、观测到的向上辐射强度、温度、云低高度等信息发展出一种CloudSat的云分类算法，该算法把云分成层云（St)层积云（Sc）、积云（Cu）、积雨云（Ns）、高积云（Ac）、高层云（As）、深对流(Deep）和高云（High）几类，高云类包括卷云、卷积云和卷层云，积云代表浓积云和晴空积云。

北疆21次降雪天气的云系类型主要有层云、层积云、积云、积雨云、高积云、高层云、深对流和高云8类，其中降雪前主要以大范围高层云、积云、雨层云、层云、高云和深对流云等为主，降雪中主要以积云、高层云，层云，高云和深对流云为主(图1），在降雪前和降雪期间以层云、积云、高层云和深对流云为主(图2)。

# 2.2强降雪过程云的微观物理属性

云和降水的发生和发展过程既受动力、热力条件的影响又受云系内部微物理过程的影响。研究发现，云系中粒子等效半径、粒子种类、水汽含量等的分布和大小变化对云系分布和降水的发生演变具有重要作用[24]。CloudSat 云雷达的云水含量产品(2B-CWC-RO)包含每个云雷达剖面上的云液水和冰水含量，有效半径以及粒子数浓度的反演估计值，其中，基于ECMWF模式中的温度产品对CRR产品进行分类，认为低于 $- 2 0 \ \mathrm { ^ { \circ } C }$ 以上为冰云，温度超过$0 \ \mathrm { { ^ circ C } }$ 的情况被认为是水云， $- 2 0 \sim 0 \ \mathrm { ~ \textdegree C }$ 之间为混合相云。在人工增雪中冰云是主要的作业对象，冰粒子对降水的贡献率占到了 $3 5 \%$ 以上，冰相粒子的发展变化与地面降雪量的大小成正相关[25]。分析降雪天气中的冰粒子等效半径、冰粒子数浓度、冰水含量、雪水含量与降雪强度，对人工增雪作业人员了解作业云系的微物理特征变化至关重要。

2.2.1粒子等效半径粒子尺度是云降水微物理研究过程中最基本的特征值，一般用等效半径来描述粒子大小，本文中利用冰粒子的等效半径来表示强降雪天气过程中的粒子尺度，其计算公式如下，冰

15 深对流层积雨云高 5 高 云云0 据40.02N41.67N 43.32N 44.97N46.62N 48.27N 49.92N81.42E80.82E 80.22E 79.63E79.03E78.43E 77.83E经纬度

15 深对流层积雨云/ 105 云云0 据40.02N41.67N43.32N44.96N46.61N48.26N49.91N85.95E85.35E 84.75E 84.16E 83.56E 82.96E 82.36E经纬度

粒子有效半径 $r _ { e }$ 根据尺寸分布的矩来定义：

$$
r _ { e } = \frac { \displaystyle \int _ { 0 } ^ { \infty } N ( r ) r ^ { 3 } \mathrm { d } r } { \displaystyle \int _ { 0 } ^ { \infty } N ( r ) r ^ { 2 } \mathrm { d } r }
$$

式中： $N ( r )$ 为假定冰晶符合对数正态分布， $r$ 是为冰粒子半径[10] O

基于CloudSat卫星过境时降雪云系中冰粒子等效半径的垂直剖面信息，将21次降雪个例进行分类，根据时间信息分为降雪发生前卫星过境的垂直剖面信息和降雪正在发生时的剖面信息，其中冰粒子等效半径(IER)最大值为 $2 9 6 . 5 ~ { \mu \mathrm { m } }$ ,最小值为$2 8 . 4 ~ \mu \mathrm { m }$ ,在降雪前和降雪中 $I E R$ 大于 $1 2 0 ~ { \mu \mathrm { m } }$ 所占频率为 $5 . 9 0 \%$ ， $6 0 \sim 1 2 0 ~ \mu \mathrm { m }$ 为 $6 4 . 2 9 \%$ ， $0 \sim 6 0 ~ \mu \mathrm { m }$ 为 $3 2 . 4 3 \%$ ,得出降雪天气 $I E R$ 以 $6 0 \sim 1 2 0 ~ \mu \mathrm { m }$ 为主,通过计算分析垂直剖面上的IER的几何平均值分布特征（图3），发现降雪前卫星过境探测到的IER 的几何平均值为 $5 8 . 6 5 \sim 6 7 . 2 9 ~ upmu \mathrm { m }$ ,其中有$6 7 \% > 6 4 ~ \mu \mathrm { m }$ ,降雪正在发生时的IER的几何平均值为 $5 4 . 5 6 \sim 6 6 . 9 5 ~ \mu \mathrm { m }$ ，有 $8 3 \% > 6 1 \ \mu \mathrm { m }$ ,得出降雪前比降雪中 $I E R$ 大 $2 . 9 \%$ 。

北疆西部沿天山型降雪前和降雪中的IER 均值为 $6 7 . 8 ~ \mu \mathrm { m }$ 和 $6 6 . 8 ~ \mu \mathrm { m }$ ,北疆中部沿天山型降雪前和降雪中的IER 均值为 $6 7 . 7 ~ { \mu \mathrm { m } }$ 和 $6 2 . 4 ~ { \mu \mathrm { m } }$ ,北疆西部型比中部型降雪前IER稍大，降雪过程中西部型比中部型大 $7 . 1 \%$ 。这主要可能与降雪前云系对流活动发展旺盛，水汽较为充沛，上升运动相对比较剧烈，降雪前粒子可以在云中生长较长的时间，导致降雪前云系中的粒子半径大于降雪开始后。

2.2.2粒子数浓度粒子数浓度是指单位体积内所包含粒子的数量，通过分析可以获取降水天气的发展演变过程以及判断降水发生可能性等信息。计算公式如下所示[10]：

$$
N _ { _ T } = \frac { N ( r ) } { \sqrt { 2 } \pi \sigma _ { l o g } D } \mathrm { e x p } \bigg [ \frac { - \ln ^ { 2 } \bigg ( \displaystyle \frac { D } { D _ { _ g } } \bigg ) } { 2 \sigma _ { l o g } ^ { 2 } } \bigg ]
$$

式中： $N ( r )$ 为假定的云滴符合对数正态分布， $D$ 是等效半径, $D g$ 是几何平均直径， $\sigma _ { l o g }$ 是宽度参数。

为了了解降雪前和降雪发生过程中云系中粒子数浓度的垂直分布规律，统计出INC最大值为$7 6 8 . 4 \mathrm { ~ L ~ } ^ { - 1 }$ 、最小值为 $0 . 1 \mathrm { ~ L ~ } ^ { - 1 }$ ;通过对比分析得出了降雪前和降雪中INC 大于 $1 3 0 { \mathrm { ~ L } } ^ { - 1 }$ 的比例为 $1 9 . 5 \%$ ，分布在 $5 0 \sim 1 3 0 ~ \mathrm { L } ^ { - 1 }$ 之间的INC 为 $6 1 . 8 \%$ ， $0 \sim 5 0$ ${ \mathrm { L } } ^ { - 1 }$ 之间范围的INC 频率是 $2 0 . 8 9 \%$ ,发现降雪天气的粒子数浓度主要集中在 $5 0 \sim 1 3 0 ~ \mathrm { L } ^ { - 1 }$ 之间。

![](images/a1791b8526e268b77c681855b93b1e77f0ba313dcf5413019427fac62167e93a.jpg)  
图3冰粒子等效半径分类

降雪前卫星过境时云系的INC的几何平均值为 $4 1 . 2 \sim 7 6 . 5 ~ \mathrm { L } ^ { - 1 }$ ,其均值为 $6 0 . 0 \mathrm { ~ L ~ } ^ { - 1 }$ ,降雪正在发生时云系的INC几何平均值为 $2 8 . 1 \sim 7 3 . 0 ~ \mathrm { L } ^ { - 1 }$ ,其均值为 $5 6 . 5 \mathrm { ~ L ~ } ^ { - 1 }$ （图4），最后得出降雪前比降雪中INC大 $6 . 2 \%$ 。这与邓军英[26]得到的北疆降雪天气过程中的冰粒子数浓度平均范围为 $3 0 . \ : 0 \ : \sim 9 7 . \ : 2$ ${ \mathrm { L } } ^ { - 1 }$ ,平均值为 $6 0 . 6 \mathrm { L } ^ { - 1 }$ 的结果较为一致。北疆西部型降雪前和降雪中的INC 均值为 $6 4 . 5 \mathrm { ~ L ~ } ^ { - 1 }$ 和59.6${ \mathrm { ~ L } } ^ { - 1 }$ ,北疆中部型降雪前和降雪中的INC均值为$6 2 . 0 \mathrm { ~ L ~ } ^ { - 1 }$ 和 $5 0 . 2 \mathrm { ~ L ~ } ^ { - 1 }$ ,北疆西部型降雪前和降雪中的INC 比北疆中部型分别大 $4 . 0 \%$ 和 $1 8 . 7 \%$ 。李宝东等[27]利用机载仪器和卫星、雷达等实时观测资料，发现云在发展期云顶高度、云顶温度、有效粒子半径、粒子数浓度和光学厚度等都有增加，而在云的发展中后期有效粒子半径、光学厚度、粒子数浓度和液水路径等会迅速下降

![](images/592fa35dfc675e4442c86f8a102a860447cddaa954b3d8300964b3712f0d3f82.jpg)  
图4冰粒子数浓度分类  
Fig.3Classification of ice effective radius   
Fig.4Classification of ice number concentration

2.2.3冰水含量冰水含量是指单位体积内的水凝物质量，它们的大小对云滴的增长和降水的发展变化都有重要影响。在CloudSat 资料中IWC产品的定义如下：

冰水含量IWC 根据尺寸分布的矩来定义[10]：

$$
I W C = \int _ { 0 } ^ { \infty } \rho _ { i } N \left( D \right) \frac { \pi } { 6 } D ^ { 3 } \mathrm { d } D
$$

式中： $N ( D )$ 为假定的冰晶符合对数正态分布，其中$\rho _ { i }$ 是冰晶的密度。

基于CloudSat资料中 $I W C$ 产品对比分析了降雪前和降雪期间云系中冰水含量的垂直分布规律，其中冰水含量(IWC)最大值为 $7 ~ 0 1 8 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 、最小值为 $1 \mathrm { \ m g } \cdot \mathrm { m } ^ { - 3 }$ 。降雪前和降雪期间大于 $2 0 0 ~ \mathrm { m g }$ ：$\mathrm { ~ m ~ } ^ { - 3 }$ 的 $I W C$ 出现频率为 $1 1 . 9 6 \%$ ， $1 0 0 \sim 2 0 0 ~ \mathrm { \ m g }$ ：$\mathrm { ~ m ~ } ^ { - 3 }$ 所占频率为 $2 5 . 9 7 \%$ ， $5 0 \sim 1 0 0 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ 占比为$2 4 . 3 4 \%$ ，小于 $5 0 \mathrm { \ m g } \cdot \mathrm { \ m } ^ { - 3 }$ 为 $4 4 . 6 0 \%$ ,得出北疆降雪天气的 $I W C$ 主要小于 $5 0 \mathrm { \ m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ 。

通过进一步对比分析得出降雪前和降雪期间的冰水含量的分布特征，如图5所示，降雪前卫星过境时云系的IWC 的几何平均值为 $2 5 . 4 \sim 1 3 5 . 1 ~ \mathrm { m g } ~ \cdot$ ，$\mathrm { ~ m ~ } ^ { - 3 }$ ,其均值为 $5 9 . 0 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ ,降雪正在发生时云系的 $I W C$ 几何平均值 $1 2 . 0 \sim 7 7 . 7 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ ,其均值为$4 3 . 9 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ ,这大于邓军英[26]得到的北疆降雪天气过程中的冰水含量平均值 $3 1 . 1 0 \mathrm { ~ m g ~ } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ 的结果，其可能与样本数不同以及研究区域不同有关，同样降雪前比降雪期间的IWC 大 $3 4 . 4 \%$ 。

![](images/9c11788c13cfa077112c13d886bcdbb452956334d65c8404f2406c3a17e2f8bd.jpg)  
图5冰水含量分类  
Fig.5Classification of ice water content

基于不同区域天气过程分析，发现北疆西部型降雪前和降雪中的 $I W C$ 均值为 $6 2 . \mathrm { ~ 1 ~ } \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ 和$4 8 . 7 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ ,北疆中部型降雪前和降雪中的 $I W C$ 均值为 $4 7 . 9 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ 和 $3 4 . 4 \mathrm { ~ m g ~ } \cdot \mathrm { ~ m ~ } ^ { - } 3$ ,通过统计计算得出北疆西部型降雪前和降雪中的 $I W C$ 比北疆中部型分别大 $2 9 . 6 \%$ 和 $4 1 . 5 \%$ 。这可能与北疆水汽输送以西南和西风路径为主，伊犁河谷、塔额盆地的“喇叭口”地形利于水汽的辐合抬升，利于增强北疆西部型降雪天气过程，也在一定程度上消耗了输送往中天山区域的水汽等原因有关。孙玉稳等[28]利用飞机穿云观测一次低涡气旋天气过程，发现在强云核前部,过冷水较丰富为 $1 6 6 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ 。最终统计 $8 5 \%$ 的个例表明飞机在云内穿行时，云核前部过冷水含量高，得出云系发展初期形成降水之前是飞机增雨雪作业的最佳阶段。

2.2.4雪水含量与降雪强度2C-SNOW-PROFILE产品提供了有关降雪垂直分布的降雪强度、雪粒子尺寸分布参数和雪水含量等信息，产品算法基于CPR云雷达观测的动态雷达反射率因子，使用了一种截断的反射率曲线法(终止于地表以上)来估算垂直方向几何剖面的降雪过程信息，使用最优估计算法计算出了雪的雷达散射特性，雪粒子尺寸分布参数，降雪率和雪水含量等微物理特性信息。主要利用了2C-SNOW-PROFILE数据集中的SnowWaterContent 和 Snowfall Rate 产品。

在云雷达探测范围 $R$ 内单位时间内的降雪强度S表示为：

$$
S ( P ) = \frac { 1 } { \rho _ { l i q } } { \int _ { { D _ { m i n } } } ^ { { D _ { m a x } } } } N ( { D , R } ) { m ( D , R ) } V ( { D , R } ) { \mathrm { d } } { D }
$$

雪水含量计算为

$$
S E C ( R ) = \int _ { { D _ { m i n } } } ^ { D _ { m a x } } N ( D , R ) m ( D , R ) \mathrm { d } D
$$

式中： $D$ 为粒径大小， $m ( D , R )$ 是粒子质量， $V ( D , R )$ 是降速，是液态水的密度， $N ( D , R )$ 为假定的雪粒子的尺度分布为对数正态分布[24]

利用CloudSat资料中的2C-SNOW-PROFILE数据集产品提取出了降雪云系中雪水含量( $( S W C )$ 和降雪强度 $( S R )$ 的垂直分布规律,其中 SWC 最大值为 $5 ~ 2 0 5 . 9 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ ,最小值为 $1 . 7 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ $S R$ 最大值为 $2 3 . 8 ~ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ ,最小值为 $0 . 0 0 2 5 \ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ L通过进一步对比分析降雪前和降雪发生时SWC和$S R$ 数据的分布特征(图6、图7），得出降雪前卫星过境时云系的 SWC 的几何平均值为 $2 8 . 0 \sim 8 8 . 0 ~ \mathrm { m g }$ ：$\mathrm { ~ m ~ } ^ { - 3 }$ ,其均值 $4 5 . 1 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ ,降雪期间云系的 SWC几何平均值为 $1 2 . 5 \sim 6 7 . 3 \mathrm { ~ m g ~ } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ ,其均值38.0$\mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ ,最后得出降雪前比降雪中 $s W C$ 大$1 8 . 7 \%$ 。

基于空间特征分析，发现北疆西部型降雪前和降雪中的 $S W C$ 均值为 $4 7 . 1 \mathrm { ~ m g ~ } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ 和 $4 2 . 7 ~ \mathrm { m g }$ ：$\mathrm { ~ m ~ } ^ { - 3 }$ ,北疆中部型降雪前和降雪中的 SWC 均值为$3 8 . 0 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 和 $2 8 . 7 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ ,北疆西部型降雪前和降雪中的 $S W C$ 比北疆中部型分别大 $2 3 . 9 \%$ 和$4 8 . 8 \%$ 。降雪前云系的 $S R$ 几何平均值为 $0 . 0 8 \sim$ $0 . 3 6 ~ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ ,其均值 $0 . 1 5 \mathrm { ~ m m ~ } \cdot \mathrm { ~ h ~ } ^ { - 1 }$ 。降雪正在发生时云系中 $S R$ 的几何平均值为 $0 . \ 0 3 \sim 0 . \ 2 4$ $\mathbf { m } \mathbf { m } \cdot \mathbf { h } ^ { - 1 }$ ,其均值为 $0 . 1 1 \ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ ,计算得出降雪前 $S R$ 是降雪中 $S R$ 的1.08倍。这与MATROSOV等[24]研究的美国阿拉斯加北部一次降雪天气中 $S R$ 为 $0 \sim 0 . 6 8 \ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ 的结果较为接近。北疆西部型降雪前和降雪中的 $S R$ 均值为 $0 . 1 6 ~ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ 和0.14$\mathbf { m } \mathbf { m } \cdot \mathbf { h } ^ { - 1 }$ ,北疆中部型降雪前和降雪中的 $s W C$ 均值为 $0 . 1 2 \ \mathrm { m m } \cdot \mathrm {  ~ h ~ } ^ { - 1 }$ 和 $0 . 0 6 \ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ ,可见北疆西部型降雪前和降雪中的 $S R$ 比北疆中部型分别大$3 3 . 3 \%$ 和2.3倍。

![](images/aec2752f23195c34bbf93d8c72cfc7032d04bbe034293f6f3727b866fbc768a7.jpg)  
图6雪水含量分类

![](images/a1ef76e930576dc09e3156f90fd9cf685b43ac72cd18a5461077360eb4d887df.jpg)  
Fig.6Classification of snow water content   
图7降雪强度分类  
Fig.7Classification of snow rate

# 3结论

本文针对2008—2015年北疆沿着天山及其周边地区21次强降雪天气过程，分析了降雪过程云系类型和云微物理属性的垂直分布特征，对比分析了不同区域、降雪不同时段卫星过境时云宏微观物理参数的差异，得出了以下结论：（1）21次降雪天气的云系有层云、层积云、积云、积雨云、高积云、高层云、深对流和高云8类，降雪前和降雪期间云系以层云，积云，高层云和深对流云为主。

（2）通过降雪不同时段分析，在降雪前和降雪中冰粒子等效半径IER以 $6 0 \sim 1 2 0 ~ \mu \mathrm { m }$ 为主出现频率为 $6 4 . 2 9 \%$ ,冰粒子数浓度INC主要集中在 $5 0 \sim$ $1 3 0 ~ \mathrm { L } ^ { - 1 }$ 之间占比为 $6 1 . 7 9 \%$ ,冰水含量IWC 主要小于 $5 0 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ 出现频率为 $4 4 . 6 \%$ 0

（3）降雪前的粒子等效半径、粒子数浓度、冰水含量、雪水含量和降雪强度均值均大于降雪期间，其中差别较大的是 $I W C , S R$ 和 $S W C$ ，降雪前分别比降雪中大 $3 4 . 4 \% . 3 6 . 4 \%$ 和 $1 8 . 7 \%$ 。差别较小的是IER、INC降雪前比降雪中大 $2 . 9 \%$ 和 $6 . 2 \%$ 。这主要可能与云系前部对流活动发展旺盛，水汽较为充沛，辐合上升运动相对比较剧烈，导致降雪前冰水含量、水粒子数浓度和雪水含量等较大。

（4）通过不同地理区域分析来看，发现北疆西部沿天山型降雪前和降雪中微物理特征值均大于中部沿天山型降雪天气过程，其中差别最大的是在降雪过程中西部型降雪的SR为中部型的2.3倍，其次IWC和SWC比中部沿天山型分别大41. $5 \%$ 和$4 8 . 8 \%$ 。北疆西部的“喇叭口”地形利于水汽的辐合拾升，有助于增强北疆西部型降雪天气过程，也在一定程度上消耗了输送往中天山区域的水汽。

# 参考文献(References）

[1］李效收.1961—2010 年新疆降雪的变化特征［D].兰州：西北师范大学,2O13.［LI Xiaoshou.Changing characteristics of snow-

fall in Xinjiang from 1961 to 2010[D].Lanzhou:Northwest Normal University,2013.]   
[2]赵俊荣,郭金强.天山北坡中部一次罕见特大暴雪天气成因 [J].干旱气象,2010,28（4）:438-442.[ZHA0 Junrong,GUO Jinqiang.A rare blizzard weather in the middle of the northern slope of the Tianshan Mountains[J]. Joumal of Arid Meteorology, 2010,28(4) :438 -442.]   
[3］张书萍,祝从文.2009 年冬季新疆北部持续性暴雪的环流特征 及其成因分析[J].大气科学,2011,35（5）：833－846. [ZHANG Shuping,ZHU Congwen.Possible causes of circulation anomalies associated with subsequent snowstorms over the north of Xinjiang during winter 2O09[J]. Chinese Journal of Atmospheric Sciences,2011,35(5） :833-846.]   
[4］李如琦,唐冶.2010 年新疆北部暴雪异常的环流和水汽特征分 析[J].高原气象,2015,34(1）:155-162.[LI Ruqi,TANG Ye. Atmospheric circulation and water vapor characteristics of snowstorm anomalies in northern Xinjiang in 2Olo[J].Plateau Meteorology,2015,34(1) :155-162.]   
[5］庄晓翠,李博渊,张林梅,等.新疆阿勒泰地区冬季大到暴雪气 候变化特征［J].干旱区地理,2013,36(6）：1013－1022. [ ZHUANG Xiaocui,LI Boyuan,ZHANG Linhai,etal. Heavy snowstorm characteristics of climatic change in winter in Altay Prefecture,Xinjiang[J].Arid Land Geography,2013,36(6）:1013- 1022.]   
[6］张俊兰,崔彩霞,陈春艳.北疆典型暴雪天气的水汽特征研究 [J].高原气象,2013,32（4）:1115-1125.[ZHANG Junlan, CUI Caixia,CHENG Chunyan.Studyon water vapor characteristc of typical heavy snowstorm case in northern Xinjiang[J].Plateau Meteorology,2013,32（4）,115-1125.]   
[7］于晓晶,于志翔,唐永兰,等.不同云微物理方案对新疆冷锋暴 雪的预报影响分析[J].暴雨灾害,2017,36(1):33－41.[YU Xiaojing,YU Zhixiang,TANG Yonglan,etal. Influence of diferent cloud microphysical schemes on forecasts of a cold-font snowstorm in Xinjiang[J].Torrential Rain and Disasters,2017,36(1） 33- 41.]   
[8］杨莲梅,刘雯.新疆北部持续性暴雪过程成因分析[J].高原气 象,2016,35(2）:507-519.[YANG Lianmei,LIU Wen.Cause analysis of persistent heavy snow processes in the northern Xinjiang [J].Plateau Meteorology,2016,35(2）:507 -519.]   
[9]刘惠云,崔彩霞,李如琦.新疆北部一次持续暴雪天气过程分 析[J].干旱区研究,2011,28(2）:282-287.[LIU Huiyun,CUI Caixia,LI Ruqi. Analysis of a continuous snowstorm weather process in northern Xinjiang[J].Arid Zone Research,2011,28 (2):282 -287.]   
[10］马占山,秦琰.云探测卫星CloudSat[J].气象,2008,34（8）： 104-111.[Ma Zhanshan,Qin Yanyan.Introductions to a new type cloud detecting satellite-Cloudsat[J].Meteorological,2008, 34(8):104 -111. ]   
[11］周毓荃,赵姝慧.CloudSat卫星及其在天气和云观测分析中的 应用[J].南京气象学院学报,2008,31（5）:603-614.[ZHOU Yuquan,ZHAO Shuhui. Cloudsat satelite and its application in weatherand cloud observation[J].Journal of Nanjing Institute of Meteorology,2008,31（5）:603-614.]   
[12］冯建东,武志婷,彭宽军,等.基于CloudSat卫星资料的新疆三 大山区不同类型云高特征研究[J].冰川冻土,2014,36（2）： 310 -317.[FENG Jiandong,WU Zhiting,PENG Kuanjun,et al. Variations in the heights of different clouds over three major mountains in Xinjiang based on Cloudsat observation[J]. Journal of Glaciology and Geocryology,2014,36(2）:310-317.]   
[13］张晓,段克勤,石培宏.基于CloudSat卫星资料分析青藏高原 东部夏季云的垂直结构[J].大气科学,2015,39(6)：1073- 1080.［ZHANG Xiao,DUAN Keqin,SHI Peihong. Cloud vertical profiles from Cloudsat data over the eastern Tibetan Plateau during summer[J]. Chinese Journal of Atmospheric Sciences,2015,39 (6):1073 -1080.]   
[14］钟水新,王东海,张人禾,等.基于CloudSat 资料的冷涡对流云 带垂直结构特征[J].应用气象学报,2011,22（3）:257 －264. [ ZHONG Shuixin,WANG Donghai,ZHANG Renhe,et al. Vertical structure of convective cloud in a cold vortex over northeastern China using Cloudsat data[J].Journal of Applied Meteorological Science,2011,22(3):257 -264.]   
[15］王帅辉,韩志刚,姚志刚,等.基于CloudSat 资料的中国及周边 地区各类云的宏观特征分析[J].气象学报,2011,69（5）:883 -899.[WANG Shuaihui,HAN Zhigang,YAO Zhigang,et al. Analysis of cloud types and macroscopic characteristics over China and its neighborhood based on the Cloudsat data[J].Acta Meteorologica Sinica,2011,69(5）:883-899.]   
[16］邓军英,丁明月，王文彩,等.冰云粒子微物理属性在一次强降 雨过程中的垂直分布［J].干旱区地理,2016,39（3)：590- 599.[DENG Junying,DING Mingyue,WANG Wencai,et al. The vertical distribution of microphysical properties of ice cloud particles in a strong rainfall process[J].Arid Land Geography,2016, 39(3):590 -599.]   
[17］光莹,邓军英,陈勇航,等.层状云微物理属性垂直分布的季节 变化——以新疆地区为例[J].干旱区地理,2017,40（4)： 754-761.[GUANG Ying,DENG Junying,CHEN Yonghang,et al. Seasonal variation of vertical distribution of layered cloud microphysical properties: Taking Xinjiang region as an example[J].Arid Land Geography,2017,40(4) :754 -761.]   
[18］王旭,张嘉伟,马禹,等.天山山脉强降水云宏微观物理属性的 空间分布特征[J].干旱区地理,2016,39(6)：1153-1161. [WANG Xu,ZHANG Jiawei,MA Yu,etal. Spatial distribution characteristics of microscopic physical properties of heavy precipitation in Tianshan Mountains[J].AridLand Geography016,39 (6):1153 -1161.]   
[19］陈勇航,邓军英,张萍,等.中天山附近强降雨过程中云冰水含 量随高度变化特征[J].资源科学,2013,35（3）：655-664. [CHEN Yonghang,DENG Junying,ZHANG Ping,et al. Vertical distribution of ice water content in clouds during heavy rainsaround Tianshan Mountain[J].Resources Science,2013,5（3）: 655 -664.]   
[20］刘岩,马骁骏,李浩,等.基于 CloudSat 和 Aqua 卫星资料的北 疆一次暴雪过程中云的宏微观物理属性[J].沙漠与绿洲气 象,2015,9(2）:9-15.[LIU Yan,MA Xiaojun,LI Hao,et al. Cloud macro and micro physical properties during a snowstorm based on cloudsat and aqua satellite data[J].Desert and Oasis Meteorology,2015,9(2）:9 -15.]   
[21］陈英英,武文辉,唐仁茂,等.利用Cloudsat 卫星资料分析冻雨 天气的云结构［J].气象,2011,37（6）：707-713.［CHEN Yingying,WU Wenhui,TANG Renmao,et al. Analysis on the cloud structure of freezing precipitation using Cloudsat satellte data[J]. Meteorological,2011,37(6） :707 -713.]   
[22]KULIE M S,MILANI L,WOOD N B,et al.A shallow cumuliform snowfall census using spaceborne radar[J]. Journal of Hydrometeorology,2016,17(4）:1261-1279.   
[23]CHEN S,HONG Y,KULIE M,et al. Comparison of snowfall estimates from the NASA CloudSat cloud profiling radar and NOAA/ NSSL multi-radar multi-sensor system[J]. Journal of Hydrology, 2016,541:862-872.   
[24]MATROSOV SY,SHUPE MD,DJALALOVA IV.Snowfall retrievals using millimeter-wavelength cloud radars[J].Journal of Applied Meteorology and Climatology,2008,47(3）:769-777.   
[25］梁军，张胜军，王树雄，等.大连地区一次区域暴雪的特征分析 和数值模拟［J].高原气象，2010，29（3）：744－754.［LIANG Jun,ZHANG Shengjun,et al.Characteristic analysis and numerical simulation of a snowstormin DalianRegion[J].Plateau Meteorology,2010,29(3):744-754.]

[26］邓军英.云卫星在降水云研究中的应用[D].上海：东华大学，

2014.［DENG Junying.Application of Cloudsat in the study of precipitation clouds[D].Shanghai;DongHua University,2014.]   
[27］李宝东，孙玉稳，孙霞，等.河北春季一次飞机人工增雪的综合 分析[J].干旱气象,2014,32（5）:819-829.[LIBaodong,SUN Yuwen,SUNXia,et al.Comprehensive analysisof aircraft artificial precipitation on stratiform clouds in spring over Hebei Province [J].Journal of Arid Meteorology,2014,32(5）:819 -829.]   
[28］孙玉稳，孙霞，刘伟，等.一次雨夹雪降水过程人工增水作业的 综合观测研究[J].气象，2015，41（11）：1341-1355.［SUNYuwen,SUN Xia,LIUWei,et al.Study of integrated observation on aircraft artificial operation during a sleet event[J].Meteorological Monthly,2015,41（11）:1341-1355.]

# Cloud structure characteristics in heavy snowfall days in northern Xinjiang using Cloudsat satellite data

WANG Zhi-min'，FENG Wan-yue²，LI Yuan-yuan’， CHU Chang-jiang³, XU Wen-xia'， CHENG Yong-hang4   
(1Xinjiang WeatherModfiationOffce,Urumqi8o2,injang,China；2eteorologicalndTechicalEquipmentt   
CenterofXinjang UygurAutonomousRegionUrumqi,Xinjan,hina；XinjangeteorologicalBureauUumqi0   
Xinjiang,China；4olgefEironmentalSencendEngineeing,Donghua Universityanghaihanghi6,hna)

Abstract：The CloudSat observational dataset provides an important opportunity to study snowfall,and there have ben numerous investigations making use of CloudSat for snowfal-related research.Based on the data of 2B-CLDCLASS,B-CWC-RVOD and 2C-SNOW-PROFILE and the precipitation data of the ground observation stations,the macro and micro physical properties of the clouds before and duringthe snowfall were comparedand analyzed in 21 heavy snowfallevents in the northern Xinjiang,China.In the paper,the northern Xinjiang was divided into the western and the central region along Tianshan Mountains.Firstly,allthe sites which had precipitation reached to heavy snowstorm in 24 hours were selected in the northern Xinjiang from 2OO8 to 2O15.Then,according to the specificdates ofthesnowfall andthe latitude and longitudeof the sites,those sites which had CloudSat passed their territory were selected as the research object and there were 2l cases obtained.Outofthe21 cases there were l2 cases withthe satellte passing their teritories while the snowfall was occurring,and9 cases with the satellite passing their teritories before snowfall.Thedistributions of microphysical properties,which include ice effctive radius（IER）, ice number concentration（INC）,ice water content（IWC）,snow water content（SWC）and snow rate（SR）,were revealed through analyzing the clouds,cloud types of heavy snowfalland the relationship between cloud microphysical properties and snowfall.Before the heavy snowfalland during the heavy snowfall,the main cloud types were altostratus clouds,cumulus clouds,nimbostratus,stratus clouds,the convective clouds between altostratus cloudsand deep stratus.The maximum of $I E R$ was $2 9 6 . 5 ~ { \mu \mathrm { m } }$ and the minimum was $2 8 . 4 ~ \mu \mathrm { m }$ . The mean of $I E R$ of ice cloud was $6 4 . 1 ~ { \mu \mathrm { m } }$ before the snowfall,and $6 2 . 3 ~ { \mu \mathrm { m } }$ in the snowfall. The $I E R$ before the snowfall was $7 . 1 \%$ larger than that in the snowfall. The largest $I N C$ is $7 6 8 . 4 \mathrm { L } ^ { - 1 }$ ,and the values of geometric mean range of INC were $4 1 . 2 \sim 7 6 . 5 \$ （204号 $\mathrm { ~ L ~ } ^ { - 1 }$ before the snowfall ,and $2 8 . 1 \sim 7 3 . 0 ~ \mathrm { L } ^ { - 1 }$ during the snowfall. The values of geometric mean range of $I W C$ of ice cloud were $2 5 . 4 \sim 1 3 5 . 1 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ before the snowfall ,and $1 2 . 0 \sim 7 7 . 7 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ during the snowfall. The largest $I W C$ was $7 0 1 . 8 ~ \mathrm { m g } \cdot \mathrm { ~ m ~ } ^ { - 3 }$ ,and the smallest $I W C$ was $1 . 0 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ . The mean values of $S W C$ and $S R$ were $2 8 . 0 \sim$ $8 8 . 0 ~ \mathrm { m g } \cdot \mathrm { m } ^ { - 3 }$ and $0 . 0 8 \sim 0 . 3 6 ~ \mathrm { { m m } } \cdot \mathrm { { h } } ^ { - 1 }$ respectively. The mean values of $I E R , I N C , I W C , S W C$ and SR before the snowfall were respectively $2 . 9 \ \% , 6 . 2 \ \% , 3 4 . 4 \ \% , 3 6 . 4 \ \%$ and $1 8 . 7 \ \%$ higher than those during the snowfall. The areas with larger values of the micro physical cloud properties are mainly concentrated in the western part of norther Xinjiang.This study had presented acomprehensive analysis of cloud vertical structures and regional variations before and during the heavy snowfall.The analysis of ice effective radius,ice number concentration,ice water content,snow water content and snow rate also helps understand the artificial snow augmentation.

Key words:Cloudsat； heavy snowfall；macro and micro physical properties ；northern Xinjiang