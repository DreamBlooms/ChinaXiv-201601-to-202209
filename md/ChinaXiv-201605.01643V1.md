# 基于PSD的高精度太阳敏感器电子学系统设计

朱龙飞1²，陈鼎，桑鹏’，李保权'(1.中国科学院复杂航天系统电子信息技术重点实验室，中国科学院空间科学与应用研究中心北京100190;2.中国科学院大学北京100190)

摘要：针对目前国内太阳观测成像仪器稳像系统的需要提出了一种基于位置敏感探测器(PSD)的高精度太阳敏感器电子学系统的设计，有针对性地提出了提高灵敏度的设计方案和降低系统噪声的具体措施。该系统噪声水平低于4nA在工作范围中心区域具备了 $0 . 3 ^ { \prime \prime }$ 的高分辨能力，可以配合偏摆镜结构组成稳像系统服务于夸父和SPORT计划等具有高分辨率成像需求的太阳成像仪器。

关键词：太阳成像；稳像；位置敏感探测器；高精度太阳敏感器中图分类号：TP212 文献标识码：A 文章编号:1000-9787(2015)09-0087-03

# Design of electronics system for high precision sun sensor based on PSD

ZHU Long-fei1²,CHEN Ding’,SANG Peng',LI Bao-quan' (1.Key Laboratory of Electronics and Information Technology for Space Systems,CSSAR, Chinese Academy and Sciences Beijing1oo19o,China; 2.University of Chinese Academy of Sciences,Beijing 10o19o ,China)

Abstract:To meet the needs of image stabilization system of domestic solar observatory imaging instrument，a position sensitive detector(PSD)-based electronics system design for high-precision sun sensor is proposed. Concrete measures are put forward to improve the sensitivityand reduce system noise.At presemt,level of the system noise is lower than 4 nA,and has high resolving power of $0 . 3 { ^ { \prime \prime } }$ in center area of working scope ,can cooperate with tip-tilt mirrr to makeup this system image stabilization system，which serve for Kua Fu and SPORT project and other solar imaging instruments which has high resolution imaging demand.

Key words:solar imaging; image stabilization; position sensitive detector(PSD)；high-precision sun sensor

0引言

随着国内空间科学的发展，一大批高分辨率的太阳成像仪器如极紫外成像仪[]、日冕成像、日球成像、磁场成像等仪器正在展开技术攻关中国科学院也正在开展夸父和SPORT等太阳观测卫星的研制任务。这些仪器的分辨率设计指标均要求达到国际先进水平，但国内卫星平台自身的姿态控制系统难以满足其成像的稳定度指标需求。

国际上成熟的解决方案是使用独立的稳像系统，以确保可以获得高分辨率的太阳观测图像。自前美国主导研制的多颗太阳观测卫星,如SOHO，TRACE,STEREO,SDO等均搭载了独立的高精度稳像系统。独立的稳像系统保证了这些太阳观测卫星的成像精度基本上都已经达到角秒级别[2\~6]。

独立的稳像系统的一个重要组成部分是太阳敏感器，太阳敏感器可以迅速计算出太阳视线与太阳观测成像系统光轴之间的夹角提供给稳像系统，用以对成像光路进行调整提高成像的精度和分辨率。若开发出高精度的太阳敏感器则可以显著提高仪器搭载稳像系统的分辨率与精度。

太阳敏感器的电子学系统设计的质量直接影响稳像系统的分辨率和灵敏度。同时，位置敏感探测器（positionsensitivedetector，PSD)作为一种响应速度快、位置分辨率高、光谱响应范围宽的位置敏感器件其在精太阳敏感器中的应用在国内还是空白。本文提出了一种基于PSD的高精度太阳敏感器电子学系统设计方案，并且有针对性地给出了提高灵敏度的设计方案和降低系统噪声的具体措施，使其能够满足高性能稳像系统原理样机的需求，服务于夸父和SPORT等太阳观测卫星高分辨稳像需要。

# 1位置敏感探测原理

系统的位置敏感探测原理如图1所示 $\mathbfcal { X } \mathrm { - } \boldsymbol { Y }$ 是PSD所在平面经过透镜滤波和聚焦的太阳光，在四象限PSD上形成一个合适大小的光斑，太阳光线垂直于PSD平面入射时,光斑位于PSD正中心,那么，四象限的电流值是相同的;如果太阳入射光路偏离垂直方向则光斑的位置就会发生偏移相应的各个象限的电流就会发生改变。

![](images/7cb31e5fce824ef5926f97fdd9ef1e32ee2ff50c3b318fde09695579bc41a85b.jpg)  
图1太阳光斑在PSD上位移示意图

因此，可以根据电流的变化计算出光斑在四象限PSD上的位置经典的计算方法如式(1）、式(2)所示

$$
X = k \ { \frac { ( \ I _ { 1 } + I _ { 2 } ) \ - ( \ I _ { 3 } + I _ { 4 } ) } { I _ { 1 } + I _ { 2 } + I _ { 3 } + I _ { 4 } } } ,
$$

$$
Y = k \ : \frac { ( I _ { 3 } + I _ { 2 } ) \ : - ( I _ { 1 } + I _ { 4 } ) } { I _ { 1 } + I _ { 2 } + I _ { 3 } + I _ { 4 } } \ : .
$$

其中 $ { J } _ { 1 }  { J } _ { 2 }  { J } _ { 3 }  { J } _ { 4 }$ 为PSD四个相互独立的象限输出的光电流值(以左上角为起始顺时针方向）。 $k$ 值可以通过模拟太阳照射在PSD上进行光斑位移测试得到一个拟合值。因此只要通过合适的电子学系统检测出PSD四个象限输出的电流值大小就可以计算出太阳光斑在PSD的位置进而提供太阳照射角度的信号。

# 2高灵敏度电子学系统设计

传统的PSD信号处理电路大多是模拟式的，由运算放大器实现和差运算由模拟除法器实现除法运算最终得到与位置信号呈比例的电压信号。这种模拟式PSD信号处理器具有处理速度快的优点但却不能通用即由于不同结构PSD的位置公式不同必须匹配不同运算功能的处理器[7]。因此 本文提出了一种通过运放实现信号采集,通过AD实现信号转换的通用型PSD信号处理电路。该电路具有较高的位移探测灵敏度，可以对PSD输出信号进行精确处理和运算实现对太阳偏移角度的精确测量，为稳像系统提供图像偏移误差信号。

其电子学系统设计如图2所示，电子学系统由四部分组成分别是信号获取电路、信号转换电路、数字信号处理电路以及输入输出接口模块。

# 2.1信号获取电路

由于PSD输出的光电流为 $\mu \mathrm { A }$ 级别信号太弱不适合直接采样输出故在信号获取阶段,需采用具有电流/电压转换和放大功能的电路对信号进行放大以保证信号采样

一次电源数据收发接口 信号 信号获取 转换 电子学系统输入 数字输出 信号模块 处理

Fig 2Structure diagram of electronics system输出的准确性。图3为PSD光电流转换和放大电路原理图。

![](images/bd2990eace490712111fd4b0b785497b44d576465d612c45a4e59f487b433033.jpg)  
Fig1Displacement diagram of solar facula on PSD   
图2电子学系统结构图  
图3信号获取电路原理图  
Fig 3Principle diagram of signal acquisition circuit

PSD 四象限输出为 $\mu \mathrm { A }$ 级信号需要分辨精度为nA级别故采用了输入偏置电流为 $1 5 \mathrm { \ p A }$ 的精密跨阻放大器OP497,该放大器输出噪声峰峰值为亚 $\mu \mathrm { V }$ 级将光电流信号转换为电压信号；主放大器采用输出噪声峰峰值为$\mu \mathrm { V }$ 级的微功耗放大器OP491将电压信号进一步放大到便于A/D转换模块采集的范围内。两级放大均采用一片集成4路放大器，以减少PSD四路输出信号的传导误差。

# 2.2信号转换电路

经过计算分析基于PSD的高精度太阳敏感器为了实现1"的测量精度其电子学部分应实现至少6nA的光电流分辨能力 ${ \mathbf { \nabla } } _ { \mathbf { \rho } } 6 { \mathbf { \Omega } } _ { \mathrm { n A } }$ 信号经放大电路后到达A/D转换器时为$0 . 9 4 \mathrm { m V }$ 。

为提高电子学的分辨能力，A/D转换电路部分采用16位的低功耗A/D转换器AD7980单电源2.5V供电参考电压为5V;图4为AD7980在5V参考电压下采样中心值时的输出信号分布直方图，由此可见其输出噪声为$\pm 3 \mathrm { L S B }$ 而电路要求的最低分辨能力根据公式(3)计算得出为12LSB，可见此A/D满足电路系统对于分辨能力的要求

$$
{ \frac { 0 . 9 4 \mathrm { m V } } { 5 \mathrm { V } } } \times 2 ^ { 1 6 } = 1 2 .
$$

# 3噪声抑制措施

# 3.1 稳压电源

在电路初期调试阶段，AD7980的参考电压VR与电路的供电电源VCC是同一路电源，在测试中发现参考电压随着输入增大而变得不稳定 ，输入 $1 6 ~ \mu \mathrm { A }$ 时，参考电压噪声的峰峰值达到 $1 ~ \mathrm { m V }$ ，导致了数字信号转换的精度降低因而采用独立的稳压电源芯片来输出AD7980的参考电压VR。

![](images/44b31bbe664262ab8f322627a09f1b6d65194211667327b4780ff06f56d96cbd.jpg)  
图4AD7980采样输出直方图

本设计选取的稳压源芯片其输出值的 $0 \sim 1 2 \mathrm { H z }$ 峰峰值噪声只有 $8 ~ \mu \mathrm { V }$ ,远远低于VR与VCC共用时的峰峰值$1 \mathrm { m V }$ 。当电路输入电流在 $1 6 \mu \mathrm { A }$ 时 通过公式(4)比较可以得出稳压芯片对于A/D转换的噪声贡献小于0.054(HEX值）远远低于电路分辨能力所要求的12即

$$
\frac { 2 . 5 8 } { 5 } \times 2 ^ { 1 6 } - \frac { 2 . 5 8 } { 5 . 0 0 0 0 0 8 } \times 2 ^ { 1 6 } < 0 . 0 5 4 .
$$

# 3.2 AD7980电磁环境改善

使用高精度稳压源芯片之后导致了较大的噪声干扰，影响了稳压源芯片的输出因而将晶振周围的铜皮和稳压源芯片周围的铜皮隔开，避免了地电平不稳导致的噪声传播。

针对AD7980基准电压输入REF具有的动态输入阻抗进行去耦，为使寄生电感最小最理想的实现方法是将基准电压源的去耦陶瓷电容器正对REF和GND引脚放置并用较宽的低阻抗走线进行连接。同样，AD7980的电源VDD和VIO的去耦电容器，也应尽量靠近AD7980放置并用短而宽的走线连接，以提供低阻抗路径并减小电源线路上的毛刺噪声影响。因而 在电路中将原本摆放在其周围的去耦电容器安装在芯片背面，并通过短而宽的走线或铺铜与管脚相连，从而改善了数字信号转换中的噪声状况。

# 4实验测试

在硬件调试初期，为了验证电路噪声性能和灵敏度，采用电流源直接接入放大模块模拟光电流对电路性能进行仿真测试。采用Keithley6220型精密直流电源作为模拟源进行仿真实验模拟光电流输入由于PSD光电流输出在 $0 \sim$ $2 5 . 8 \mu \mathrm { A }$ 范围内变化故采用电流源的 $2 0 \mu \mathrm { A }$ 量程范围；在该量程范围内电流源的最小调整精度为1nA峰峰值噪声为 $2 \mathrm { n A }$ 。

在测试阶段，首先进行噪声分析。选取 $1 \sim 1 6 \ { , } 2 0$ 1$2 5 \mu \mathrm { A }$ 共18个输入值进行测试。测试结果如图5所示。由数据可知除个别测试值( $8 \ , 1 6 \ 2 5 \mu \mathrm { A } )$ 外系统输出电流数值的峰峰值仅有 $3 . 3 \mathrm { n A }$ 最大的峰峰值出现在输入 $8 ~ \mu \mathrm { A }$ 的时候为 $3 . 8 \mathrm { n A }$ 输入 $1 6 ~ 2 5 \mu \mathrm { A }$ 时峰峰值为 $3 . 7 \mathrm { n A }$ 。

![](images/1322af8529b1817ca7fe179ee64ef54fb2e40c5bf37242308b8a2617e2a901a1.jpg)  
Fig 4Histogram of AD7980 sampling output   
图5输出与输入光电流误差值分布

在随后进行的分辨率测试中，依然选取1～16，20，$2 5 \mu \mathrm { A }$ 共18个输入值进行测试。每个采样值测试时都会加上3nA的跳变,测试电路的分辨能力。结果显示对于各个采样值 $3 \mathrm { n A }$ 的输入跳变都是可以被分辨出来的。其中一个值的测试结果如图6所示。

![](images/3f595b573983fae43c36c5cefaf5a23fb785dec51b8ddadaa4a88d61f81af78b.jpg)  
Fig 5Distrubution of photo current error value between inputs and outputs   
图63nA分辨率测试结果  
Fig6Test result of 3nA resolution

根据PSD的响应曲线可以计算出 $3 \mathrm { n A }$ 的分辨率等价于光斑在PSD中心位置沿坐标轴移动 $0 . 1 6 5 \mu \mathrm { m }$ 可被分辨。光学系统设计中，成像透镜焦距为 $1 0 7 . 6 \mathrm { m m }$ 那么根据公式(5)计算可以得出角分辨率在中心位置可以达到 $0 . 3 "$

$$
1 0 7 . 6 \ \tan { \frac { x } { 3 6 0 0 } } = 0 . 1 6 5 \ \mu \mathrm { m } .
$$

# 5结论

自前通过本文所述的技术手段和噪声抑制措施高精度太阳敏感器的电子学系统配合摆镜结构组成稳像系统，并已经实现了PSD中心位置 $0 . 3 ^ { \prime \prime }$ 的高分辨率电路噪声也降低到最高只有 $3 . 8 \mathrm { n A }$ 能够配合摆镜结构组成稳像系统，并服务于夸父和SPORT工程的太阳成像设备中同时也可以满足其他太阳成像观测仪器的高分辨率需求。

# 参考文献：

[1]Li Baoquan,Zhu Guangwu,Wang Shijin,et al. The solar XEUV imaging telescope [J].Chinese Journal of Geophysics， 2005 48(2):235 -242.   
[2] Delaboundiniere JP Arizner GE Brunaud J et al.EIT extremeultraviolet imaging telescope for the SOHO mission[J].Solar Physics ,1995 162:291 -312.   
[3] Kaiser ML ,Kucera TA Davila JM,etal.The STEREO mission:An introduction[J].Space Sci Rev 2008 ,136:5-16.

固定电位差约 $3 0 0 \mathrm { m V }$ ,对它们之间的电位差进行补偿即可得到本系统测出的钢筋腐蚀程度判定标定。

# 表1腐蚀电位评估钢筋腐蚀状态的标准

Tab 1 Criteria for corrosion potential to evaluate corrosion state of reinforcement   

<html><body><table><tr><td>腐蚀电位/mV</td><td>腐蚀概率</td></tr><tr><td>>-126</td><td><10%</td></tr><tr><td>- 126~ - 276</td><td>不确定</td></tr><tr><td><-276</td><td>> 90%</td></tr><tr><td><-426</td><td>非常严重</td></tr></table></body></html>

注：表中电位水平为采用饱和甘汞作参比电极时的测量值

# 4.2 测试方法与仪器

实验过程中除了通过在混凝土试件中埋设钢筋腐蚀监测探头进行测试外还要使用 $\mathrm { P S } { - } 6$ 型钢筋腐蚀测定仪进行测试，以钢筋腐蚀测定仪测试的结果作为参考。

# 4.3 测试结果与分析

按照上述测试方案进行实验，测试时温度控制在 $2 0 \ \%$ 左右。由于钢筋锈蚀速度比较缓慢因此,每隔5d用本文介绍的方法和钢筋测定仪分别测试一次混凝土试件中钢

表2试件腐蚀电位测试结果  
Tab 2Results of specimens corrosion potential test   

<html><body><table><tr><td>时间(d)</td><td>参比电极测试电位(mV）Ps-6 测试电位(mV)</td></tr><tr><td>0</td><td>-230 -209</td></tr><tr><td>5</td><td>-226 -208</td></tr><tr><td>10</td><td>-240 -219</td></tr><tr><td>15</td><td>-248 -230</td></tr><tr><td>20</td><td>-239 -228</td></tr><tr><td>25</td><td>-251 -241</td></tr><tr><td>30</td><td>-265 -239</td></tr><tr><td>35</td><td>-272 -251</td></tr><tr><td>40</td><td>-284 -267</td></tr><tr><td>45</td><td>-296 -260</td></tr><tr><td>50</td><td>-303 -272</td></tr><tr><td>55</td><td>-341 -278</td></tr><tr><td>60</td><td>-362 -285</td></tr><tr><td>65</td><td>-358 -293</td></tr><tr><td>70</td><td>-376 -308</td></tr></table></body></html>

# (上接第89页)

[4]Handy B N Acton L W ,Kankelborg C C et al.The transition region and coronal exporer[J].Solar Physics,1999,187:229- 260.

[5] Boerner Paul,Edwards Christopher,Lemen James,et al.Initial calibration of the atmospheric imaging assembly(AIA) on the solar dynamics observatory( SDO) [J].Solar Physics ,2012,275: 41-66.

[6]曾超 李锋 徐向东.光电位置传感器 PSD 特性及其应用[J].光学仪器 200224(4/5):82-85.

筋的腐蚀电位。测试结果数据如表2，从测试结果可知，通过埋设钢筋腐蚀监测探头测得的电位值变化与钢筋腐蚀测定仪测得的电位变化趋势基本一致，两种方法测得的电位值相差不大。由于混凝土结构中钢筋的腐蚀速度很缓慢，短时间内钢筋仍处于轻度锈蚀状态。

# 5结论

本文将WSNs技术应用在混凝土钢筋腐蚀度监测中，可以提高混凝土结构中钢筋腐蚀检测的效率，能对大体积混凝土结构建筑进行实时、连续、无线监测，自动采集钢筋腐蚀度的参数,并对采集的数据进行实时处理和存储。工作人员在远程监测中心可以直接查看历史数据和钢筋腐蚀变化曲线且钢筋腐蚀概率在不同水平时，上位机界面将有不同颜色的警示灯闪烁以提醒工作人员实时监测钢筋腐蚀度为评估大型混凝土结构的耐久性提供重要的依据。

# 参考文献：

[1]康旻楠.钢筋混凝土的钢筋腐蚀现状调查与原因探究[J].科技与企业 2013(8):147-148.  
[2]熊传胜 蒋林华,王维春,等.混凝土中钢筋腐蚀实时监测研究现状及展望[J].材料导报 $\mathrm { ~ A ~ } 2 0 1 2 ~ 2 6 ( 6 ) : 1 0 2 - 1 0 3 .$ （2号  
[3] 杨桂新吴瑾吴文操.混凝土结构中钢筋腐蚀监测无线传感器[J].仪器仪表学报200930(6):1153-1155.  
[4]李善仓张克旺.无线传感器网络原理与应用[M].北京：机械工业出版社2008:216-217.  
[5] 高秀利周华新刘建忠.结构混凝土钢筋腐蚀电位原位监测系统研究[J].江苏建筑2011(1)：105-106，  
[6] 李新慧俞阿龙，潘苗.基于CC2530的水产养殖监控系统的设计[J].传感器与微系统 $2 0 1 3 3 2 ( 3 ) : 8 5 - 8 6 .$   
[7] 杨维卫俞阿龙,贾芳芳等.基于WSNs和移动Agent的桥梁健康监测研究[J].传感器与微系统201332(12)：80-81.  
[8] 赵海贤.可调太阳能充电器的设计[J].电源技术应用，2012(9):63-64.  
[9]刘全信.基于 $\mathbf { Z } \mathrm { i g }$ Bee技术的养殖信息监控系统的研究与实现[D].济南:山东科技大学 2012:40-42.

# 作者简介：

王袁(1990-）女江苏淮安人硕士研究生主要研究方向为无线传感器与智能系统。

[7] Gérard Thuillier,Steven Dewitte,Werner Schmutz.Simultaneous measurement of the total solar irradiance and solar diameter by the PICARD mission [J].Advances in Space Research ,2006, 38:1792-1806.

[8]施隆照 ,黄梅珍 杨小玲 等.二维位置敏感探测器及信号处理器[J].传感器技术 2002 21(8)：20-22.

# 作者简介：

朱龙飞(1988-）男陕西汉中人硕士研究生主要从事低噪声小信号电子学系统设计方向的研究。