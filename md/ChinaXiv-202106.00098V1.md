# 一种K波段接收机的研制

王凯1,2.3，闫浩12.3，马军1,2.3，陈卯蒸1,2.3，曹亮1.2.,3，宁云炜1,2,3，段雪峰1.2.，李健1,2,3, 2,3，项斌斌1,2

(1.中国科学院新疆天文台，新疆乌鲁木齐 830011;2.中国科学院射电天文重点实验室，江苏 南京210008：

3.新疆微波技术重点实验室，新疆乌鲁木齐830011)

摘 要：射电天文是通过接收和处理无线电波以此研究宇宙天体的一门学科，微波接收机则是射电天文观测的核心接收设备。结合中国科学院新疆天文台南山25米射电望远镜现有K波段制冷接收机及未来Q波段毫米波观测需求，本论文提出一种K波段常温接收机研制，该接收机射频工作频率 $2 2 { \cdot } 2 4 . 2 6 1 2$ ，经混频最终输出3.95-6.15GHz的中频信号，主要用于在K波段开展强度校准方法实践及大气不透明度测量。最终采用冷热负载法测试K波段常温接收机噪声温度为402.2K（理论计算为410.6K)，标准噪声源为166.3K也满足设计需求，结合斩波轮校准机械结构，该K波段接收机已经具备开展强度校准及大气不透明度测试功能，相关工作也可为南山25米射电望远镜未来Q波段毫米波观测做技术预研。关键词：接收机；射电天文；K波段；强度校准；不透明度中图分类号：P111.5；文献标识码：A

射电天文学是通过接收电磁波来研究宇宙天体的一门学科[]。由于射电源辐射的信号都极其微弱，需要将微弱的射电信号从背景噪声中提取出来。为此，射电望远镜应运而生，其主要功能是接收并汇聚微弱的电磁波信号至天线焦点处。对于二次反射结构的卡塞格伦天线而言2，副反射面焦点处的微波接收机主要负责将射电望远镜收集到的射电信号经放大、滤波、变频等环节后送入数字终端并进行处理[34]，以满足不同的科学观测需求，如图1所示。

![](images/a9a00a2decdffc3468a0aac440741cddb52f58d407aae46c9697c13292a66539.jpg)  
Fig.1 Signal transmission link

# 1K波段接收机研制需求

# 1.1南山25米射电望远镜

中国科学院新疆天文台南山25米射电望远镜始建于1992年，已配备4台厘米波段高灵敏度制冷接收机系统，分别为L波段、S/X双频、C波段和K波段制冷接收机，主要用于开展脉冲星、活动星系核、分子谱线及甚长基线干涉观测等[5]。其中，最高工作波段为K波段（22-24.2GHz)，如图2所示。经前期改造过后，南山25米天线面板精度已达到 $7 \mathsf { m m }$ 观测需求，拟开展毫米波观测，现正安装调试Q波段（30-50GHz）接收机[6]。

![](images/b8af275f1f3073665c48505f42c7f5e7bde7c4c17ee8eab69fe9f0d68ed2d027.jpg)  
图1信号传输链路  
图2南山25米射电望远镜及K波段制冷接收机  
Fig.2Nanshan 25mtelescopeand K-band cryogenic receiver

\*基金项目：国家自然科学基金资助项目（11903073，11973078，11903077，11603064)；中国科学院“西部之光”人才培养引进计划（2020-XBQNXZ-018)；新疆维吾尔自治区自然科学基金资助项目（2019D01A99)：中国科学院天文台站设备更新及重大仪器设备运行专项经费资助。  
作者简介：王凯，男，硕士，研究方向：接收机技术。Email:wangkai@xao.ac.cn  
通讯作者：闫浩，男，硕士，研究方向：接收机技术。Email:yanhao@xao.ac.cn

# 1.2K波段接收机研制需求

南山25米射电望远镜现有的K波段双极化制冷接收机系统，主要用于单天线观测（分子谱线、活动星系核快速时变观测）和联测（甚长基线干涉观测）研究，该接收机主要由低温制冷单元、常温微波单元和外围辅助单元等组成。由于毫米波观测中射电信号更容易受到水汽及氧气的吸收作用，结合正在安装调试的Q波段制冷接收机的观测需求，毫米波强度校准必须要考虑大气影响。如若在K和Q波段开展精确的强度校准，尤其是在 $2 2 . 3 6 \mathsf { H z }$ 频点上下以及Q波段的高频段开展观测，更需要实时获取不透明度值以修正大气吸收。

拟研制K波段常温接收机，期望借助此接收机开展常温和高温负载法、斩波轮法的强度校准方法实践；同时开展K波段大气不透明度测量研究[8.9]，结合大气辐射转移方程，初步拟采用俯仰扫描非线性拟合的方式（sky-dips）获取对应波段在天顶方向的不透明度值，并与现有南山25米射电望远镜K波段制冷接收机的测试数据进行比对，验证测试方案的可行性，希望以此积累短厘米波段至毫米波大气不透明度测量方法及经验，并最终应用于未来的Q波段毫米波观测中。

# 2K波段常温接收机设计

结合研制需求，该接收机主要用于强度校准及大气不透明度测试，对噪声温度的要求相对低于射电观测设备，故没有对接收机进行制冷设计。该K波段常温接收机射频工作带宽为$2 2 \mathrm { - 2 4 . 2 G H z }$ ，采取超外差设计，射频信号经放大、滤波、混频后最终输出为3.95-6.15GHz的中频信号。该K波段接收机主要由馈源网络、噪声源、低噪声放大器、滤波器、混频器、介质本振、中频放大器等器件组成。

# 2.1馈源网络设计

K波段常温接收机最前级为馈源网络，其也是射电信号最先进入接收机的部分。作为整个K波段接收机系统的核心部件，馈源网络主要由波纹喇叭、波纹喇叭过渡段、定向耦合器、圆方转换器、极化器组成。波纹喇叭及过渡段（图3）材料为电解铜，电铸成型，喇叭相位中心距离喇叭口 $1 2 0 \mathrm { m m }$ ，喇叭壁厚为 $2 \mathrm { m m }$ ，喇叭口波纹参数（周期 $3 \mathrm { m m }$ ，槽宽 $2 \mathrm { m m }$ ，齿厚1mm，槽深 $3 . 3 2 \mathrm { m m } ^ { \cdot }$ )，工作频率 $2 2 \mathrm { - 2 4 . 2 G H z }$ ，圆极化轴比1.0dB。波纹喇叭口面选用聚脂薄膜(MYLAR）进行密封，主要用于避免杂物掉入馈源内部以及保持馈源内部干燥功能。该K波段常温接收机选用的密封薄膜MYLAR如图3所示，厚度为 $0 . 2 \mathsf { m m }$ ，差损为0.05dB，噪声约为0.35K。

![](images/dc3daa1d92c51fdd6eb450fe099e32e2f390f2a395ae0a4a9489280e7a994e82.jpg)  
图3波纹喇叭、过渡段和密封薄膜  
Fig.3 Corrugated horn,transition section and olyester film   
图4 定向耦合器、极化器和波同转换器Fig.4 Directional coupler,polarizerand W-C converter

定向耦合器主要用于注入标准噪声信号，利用冷热负载法标定该噪声信号用于二次校准所用；极化器用于将进入波纹喇叭的信号转换为左右旋圆极化信号，输出为标准的WR42接口；波同转换器用于将WR42波导信号转换为同轴信号。上述三个器件如图4所示。

丁山

# 2.2微波链路设计

\*基金项目：国家自然科学基金资助项目（11903073，11973078，11903077，11603064）；中国科学院“西部之光”人才培养引进计划（2020-XBQNXZ-018)；新疆维吾尔自治区自然科学基金资助项目（2019D01A99)；中国科学院天文台站设备更新及重大仪器设备运行专项经费资助。  
作者简介：王凯，男，硕士，研究方向：接收机技术。Email:wangkai@xao.ac.cn  
通讯作者：闫浩，男，硕士，研究方向：接收机技术。Email:yanhao@xao.ac.cn

馈源网络末端输出的同轴信号，经接收机后级微波链路进行放大及下变频处理。微波链路主要由低噪声放大器、射频滤波器、混频器、介质本振、中频滤波器、中频放大器等器件组成。该部分主要功能是将K波段馈源网络接收到的射频信号转换为中频信号。

图5为微波链路具体设计。首先，利用低噪声放大器对射频信号进行放大，由于放大后的射频信号强度仍无法满足混频器 RF 端的输入功率需求，因此在低噪放之后继续添加一个射频放大器以提升增益，并在两个放大器之间添加了10dB 衰减器（控制整体增益及减少两个放大器之间的反射)；其次，在射频放大器之后添加一个工作频率 $2 2 \mathrm { - } 2 4 . 2 \mathrm { G H z }$ 的带通滤波器，滤出需要的射频信号；之后，混频部分选择18.05GHz介质本振作为本振参考信号，与射频输入端的22-24.2GHz信号进行混频，经混频器最终输出为 $3 . 9 5 \mathrm { - } 6 . 1 5 \mathrm { G H z }$ 的中频信号;最后，中频信号再经 $3 . 9 5 \mathrm { - 6 . 1 5 \mathrm { G H z } }$ 带通滤波器和中频放大器处理后完成最终输出。

![](images/69900576e263f5a176e5ef3e1526b2456f64de0062d9649a57593b16ff9ac558.jpg)  
图5微波链路具体设计

# 3K波段常温接收机测试

在实验室分别对K波段接收机各个器件以及接收机整体进行了相关的微波测试，主要测试参数包括天线方向图、增益、回波损耗、噪声系数，以及接收机的带通响应及噪声温度等。

# 3.1馈源网络测试

馈源网络工作频率22-24.2GHz，VSWR≤1.2:1，插入损耗为0.2dB，在22和 $2 3 \mathrm { G H z }$ 的天线方向图如图6所示：

![](images/4ba6e3189b75b25441725e01c48a3f8c9411f554ee25a3118c9f3742c1e859ca.jpg)  
Fig.5Specific design of microwave link   
图6馈源天线方向图  
Fig.6Feed antenna pattern

# 3.2微波链路测试

从简化系统及强度校准需求考虑，暂时不需要双通道观测，故仅搭建了极化器出来后通道1的微波链路,通道2则在波同转换器后添加了匹配。通道1微波链路相关测试如下所示。

# 3.2.1低噪声放大器测试

微波链路核心器件低噪声放大器选用伟奇微波的WQLF220-242-30-LNF（增益30dB，噪声系数3dB），在工作频段22-24.2GHz开展噪声系数、增益以及驻波的测试。噪声系数测试选用安捷伦N8975A噪声系数分析仪，在22.8GHz的测试结果为2.983dB，见图7所示。

![](images/569c1ba5b219b4cd9625c40777d8423ff14477e2195063d934c12a81ad8a9791.jpg)  
图7低噪放噪声系数测试结果 Fig.7Test results of LNA noise coefficient

低噪声放大器增益及驻波测试选用安捷伦安捷伦 E8363C 矢量网络分析仪。在23.1GHz增益的测试结果为28.637dB，在 23.1GHz驻波的测试结果为1.5625，如图8所示。

![](images/1592643a352375d4809e90b640ec07cf35f967cb9d21c3f5d7b2374613e702bf.jpg)

# 3.2.2带通滤波器测试

射频部分 $2 2 \mathrm { - } 2 4 . 2 \mathrm { G H z }$ 带通滤波器选用恒伟微波的HWBPF220242（插损0.7dB,驻波1.4）。在 23.1GHz 插损的测试结果为0.57dB，驻波的测试结果为1.3，如图9所示。

![](images/d2b471d45678b01af9357773de90b965b5f57e85f3b5dcbd4dadebc6dfcafa8e.jpg)  
Fig.8Test results of gain and standing wave of LNA   
图9射频带通滤波器插损及驻波测试结果   
Fig.9Test results of insertion loss and standing wave of RF band-pass filter

# 3.2.3混频器测试

混频器选用MarkiMM1-0424S（转换插损9dB，端口隔离度 ${ \leqslant } \mathrm { - } 3 0$ dB)。在23.1GHz插损的测试结果为8dB，在23.1GHz的LO-RF 隔离度测试结果为-49.9dB，LO-IF 隔离度测试结果为-31.9dB，RF-IF隔离度测试结果为-34.8dB，如图10所示。

![](images/a167f2ea204adc91fadac851e884620581f5179a679214fd22a25869becf5f8b.jpg)  
图8低噪声放大器增益及驻波测试结果  
图10混频器插损及端口隔离度测试结果  
Fig.10Mixer insertion loss and port isolation test results

# 3.2.4中频放大器测试

经混频后所选用的中频放大器为MITEQ AFS3-04000800-20-10P-4（增益 30dB，噪声系数3dB)。在5.1GHz增益的测试结果为29.532dB，回波损耗的测试结果为13.656dB，如图11所示。

\*基金项目：国家自然科学基金资助项目（11903073，11973078，11903077，11603064）；中国科学院“西部之光”人才培养引进计划（2020-XBQNXZ-018)；新疆维吾尔自治区自然科学基金资助项目（2019D01A99)；中国科学院天文台站设备更新及重大仪器设备运行专项经费资助。  
作者简介：王凯，男，硕士，研究方向：接收机技术。Email:wangkai@xao.ac.cn  
通讯作者：闫浩，男，硕士，研究方向：接收机技术。Email:yanhao@xao.ac.cn

![](images/80dcf3129c1ce9bbe548e5fe1c7b2a735850d4587fc4243e0634585415b3ddf0.jpg)  
图11中频放大器增益及回波损耗测试结果

Fig.11 IF amplifier gain and return loss test results

# 3.2.5噪声温度测试

由于接收机系统的噪声温度主要取决于接收机前端无源器件的插损和有源器件的噪声和增益，在整个系统链路中插损L计算如式1所示，其中Pi为输入功率， $\mathsf { P o }$ 为输出功率。

$$
L ( d B ) = I O \log _ { I 0 } ( \frac { P _ { i } } { P _ { o } } )
$$

增益GA计算如式2所示：

$$
G _ { _ A } = { \frac { l } { L } } = { \frac { P _ { o } } { P _ { i } } }
$$

由此可以计算出无源器件的增益，如式3所示：

$$
G _ { _ A } = \frac { l } { l \theta ^ { \frac { L ( d B ) } { l \theta } } }
$$

级联系统的噪声温度计算如式4所示：

$$
T _ { e } = T _ { e 1 } + \frac { T _ { e 2 } } { G _ { A 1 } } + \frac { T _ { e 2 } } { G _ { A 1 } G _ { A 2 } } + \dots
$$

总增益为各部分增益的叠加，如式5所示：

$$
G ( d B ) = G _ { _ { A 1 } } + G _ { _ { A 2 } } + G _ { _ { A 3 } } + \ldots
$$

根据噪声级联的方式对K波段接收机的噪声温度进行理论计算[10]，计算结果为410.6K。K波段接收机噪声温度Trec计算如式6所示，式中Tamb和Vamb分别是常温黑体温度及接收机对应的功率输出，Tcold和Vcold分别是低温黑体温度及接收机对应的功率输出，其中接收机中频输出功率值由安捷伦N1914A功率计和E9300A功率探头（DC-18GHz）获取。

$$
T _ { r e c } = \frac { T _ { a m b } - \frac { V _ { a m b } } { V _ { c o l d } } T _ { c o l d } } { \frac { V _ { a m b } } { V _ { c o l d } } - 1 }
$$

K波段接收机定向耦合器耦合标准噪声用于二次校准，噪声源选用NOISEWAVE 的$\mathrm { N W 2 0 G 2 5 { - } 3 5 W }$ 。在低温黑体负载（冷负载）覆盖在接收机馈源口面时开启或者关闭噪声源，再结合冷热负载法，标准噪声Tcal计算如式7所示，式中 $\mathrm { V _ { C a l } }$ 为冷负载下开启噪声源时接收机对应的功率输出。

$$
T _ { c a l } = \frac { V _ { c a l } - V _ { c o l d } } { V _ { a m b } - V _ { c o l d } } \cdot \left( T _ { a m b } - T _ { c o l d } \right)
$$

之后，使用经典的冷热负载法对K波段接收机进行噪声温度Trec测试及标准噪声Tcal的标定，测试数据及结果见表1。其中，Trec_average为402.18K，Tcal_average为166.32K。

表1K波段接收机噪声温度及标准噪声测算  
Table 1 Noise temperature and standard noise calculation of K-band receiver   

<html><body><table><tr><td>Tamb (K)</td><td>Vamb (uw)</td><td>Tcold (K)</td><td>Vcold (uw)</td><td>Vcal (uw)</td><td>Trec (K)</td><td>Tcal (K)</td></tr><tr><td>298.79</td><td>7.879</td><td>77.3</td><td>5.398</td><td>7.328</td><td>404.6</td><td>172.3</td></tr><tr><td>298.62</td><td>7.893</td><td>76.8</td><td>5.409</td><td>7.287</td><td>406.2</td><td>167.7</td></tr><tr><td>298.44</td><td>7.946</td><td>76.1</td><td>5.406</td><td>7.216</td><td>397.1</td><td>158.4</td></tr><tr><td>298.13</td><td>7.863</td><td>76.6</td><td>5.388</td><td>7.308</td><td>405.7</td><td>171.9</td></tr><tr><td>298.26</td><td>7.812</td><td>76.9</td><td>5.326</td><td>7.137</td><td>397.3</td><td>161.3</td></tr></table></body></html>

结合具备常温黑体斩波功能及0-90度仰角可调的强度校准机械结构，该K波段常温接收机已可以开展斩波轮法强度校准测试及大气不透明度测量，如图12所示。

![](images/869678ac78a7a84b1557086fe5aec555cfe26190859ed245dd561366d8ea90dc.jpg)  
图12K波段接收机强度校准测试平台

# 3.2.6K波段大气不透明度测试

结合研制完成的K波段常温接收机及其俯仰可调机械结构，在南山站分别选取90、80、70、60、50、45、40、30、25、20、15、10、5度十三个仰角进行总功率采集，之后采用非线性拟合方式，初步得到在 $2 2 \mathrm { - 2 4 . 2 \ G H z }$ 频段内天顶方向上的实时不透明度值为0.12655，拟合曲线如图13所示。

![](images/dc4892908237a5608a57fcabcc2c623624534acaaf2f970ad4c12f9e43784d9f.jpg)  
Fig.12 K-band receiver calibration test platform   
图13不透明度拟合曲线  
Fig.13 Atmospheric opacity fitting curves.

# 4结论

本文结合射电天文微波接收机及其强度校准相关需求，提出一种K波段常温接收机设计，该接收机射频工作频率 $2 2 \mathrm { - 2 4 . 2 G H z }$ ，经混频最终输出 $3 . 9 5 \mathrm { - 6 . 1 5 \mathrm { G H z } }$ 的中频信号，主要用于在K波段开展强度校准方法实践及大气不透明度测量。最终采用冷热负载法测试K波段常温接收机噪声温度为402.2K（理论计算为410.6K)，标准噪声源为166.3K也满足设计需求，接收机最终中频输出频谱动态范围约30dB，功率幅度约为-50dBm，结合斩波轮校准机械结构，该K波段接收机已经具备开展强度校准及大气不透明度测试功能（初步测试对应波段天顶方向不透明度值约为0.126)，相关工作也可为南山25米射电望远镜未来Q波段毫米波观测做技术预研。

参考文献  
[1］王娜．新疆奇台110 米射电望远镜［J]．中国科学:物理学力学天文学,2014, 44(8) : 783-794.Wang N. Xinjiang Qitai 110 m radio telescope[J].Sci Sin-Phys Mech Astron,2014,44(8) :783-794.  
[2]项斌斌,王从思,王伟,等.基于机电耦合的反射面天线副面位置调整方法[J].系统工程与电子技术,2018,40(03):489-497.Xiang B B, Wang C S,Wang W，et al. Adjustment method of subreflector positionof reflector antennas based on electromechanical couple theory[J]. Systemsengineering and electronic technology， 2018， 40(03) :489-497.  
[3]陈卯蒸,刘奇,马军,等.大口径射电望远镜超宽带接收机技术发展[J].中国科学:物理学力学天文学,2017,47(05):35-47.Chen M Z,LIU Q, Ma J，et al. Ultra-wideband receiver technology developmentfor radio astronomical large aperture tele-scope[J]. Sci Sin-Phys Mech Astron,2017,47(05) :35-47.  
[4]马军,裴鑫,王娜，等.QTT 超宽带多波束信号接收与处理系统［J].中国科学:物理学力学天文学,2019,49(09) :6-18.Ma J,Pei X, Wang N, et al. Ultra wideband and multi-beam signal receiving andprocessing system of QTT[J]. Sci Sin-Phys Mech Astron， 2019,49(09):6-18.  
[5] 陈勇,孙正文,闫浩,等.新疆天文台26米望远镜L波段接收机线-圆偏振的转换[J].天文研究与技术,2019,16(03):262-267.Chen Y， Sun Z W， Yan H, et al. Conversion of Line Polarization to CircularPolarization in L Band Receiver of 26m Telescope in Xinjiang AstronomicalObservatory[J]． ASTRONOMICAL RESEARCH AND TECHNOLOGY， 2019,16(03) :262-267.  
[6]陈卯蒸,马军，覃律,等.Q波段脊过渡正交模耦合器设计[J]．电子科技大学学报，2018,47(2): 178-182.Chen M Z, Ma J，Qin L，et al. Design of a $\mathsf { Q }$ Band Orthomode Transduer Based onthe Ridged Waveguide Connection[J]. Journal of University of Electronic Scienceand technology of China， 2018，47(2)：178-182.  
[7]王凯，陈卯蒸，马军，等.射电天文毫米波接收机强度校准［J].天文学报，2018, 59(5) :1-14.Wang K,Chen M Z，Ma J，et al. The Amplitude Calibration of Radio AstronomyMillimeter Wave Receiver[J]. ACTA ASTRONOMICA SINICA， 2018,59(5) :1-14.  
[8]杨戟，曹逸庭，黄树频.在97.8GHz 处测量地球大气的不透明度［J].天文学报,1998(03) :333-336.Yang J, Cao Y T， Huang S F. Measurement of the opacity of the earth' s atmosphereat 97.8 GHz[J]. ACTA AS-TRONOMICA SINICA， 1998(03) :333-336.  
[9]周明峰，姚骑均,李升，等.羊八井 460 GHz 大气不透明度的测量［J].天文学报,2011,52(01) :62-72.Zhou M F,Yao Q J,Li S,et al. Measurement of 460 GHz atmospheric opacity inYangbajing[J]. ACTA AS-TRONOMICA SINICA， 2011,52(01) :62-72.

[10]王凯,闫浩,段雪峰,等.K波段常温接收机噪声注入定标方法分析研究[J].天文研究与技术,2020,17(04) :439-445.Wang K， Yan H, Duan X F, et al. Analysis and Research on Noise InjectionCalibration Method of K-band Ambient Temperature Receiver[J]. ASTRONOMICALRESEARCH AND TECHNOLOGY， 2020,17(04) :439-445.

Development of a K-band Receiver WANG Kai1.2.3,YAN Hao123，MA Jun1.23,，CHEN Maozheng1.2.3，CAOLiang1,23，NING Yunwei1.2.3,DUAN Xuefeng1,2.3,LI Jian1.2.3， XIANG Binbin1.2 (1．Xinjiang Astronomical observatory,Chinese AcademyofSciences,Xinjiang, Urumqi,830011,China;2.Key Laboratory of Radio Astronomy, Chinese Academy of Sciences, Nanjing 21oo08,China;3. Xinjiang Key Laboratory of Microwave Technology, Urumqi 830011, China)

Abstract : Radio astronomy is a subject of studying cosmic objects by receiving and processing radio waves. Microwave receiver is the core receiving equipment of radio astronomy observation.Considering the present K-bandcryogenic receiverand future Q-band milimeter-wave observation requirementsof the Nanshan 25-meter radio telescopeat the Xinjiang Astronomical Observatory of the Chinese Academy of Sciences，this paper presents a design of a K-band room temperature receiver.The receiver works at 22-24.2 GHz and eventuall outputs 3.95-6.15 GHz IF signal through mixing.It is mainly used for amplitudecalibration method practice and atmospheric opacity measurement in K-band.Finall，the noise temperature of K-band room temperature receiver is 402.2K (theoretical calculation is 410.6K)，and the standard noise source is 166.3K. Combining with the mechanical structure of chopper wheel calibration,the K-band receiver has the functions of amplitude calibration and atmospheric opacity measurement,and this work can pre-research on technology for Q-band millimeter-wave observations of Nanshan $2 5 m$ radio telescope forthe future.

Key words: Receiver; Radio astronomy; K-band; Amplitude calibration; Opacity