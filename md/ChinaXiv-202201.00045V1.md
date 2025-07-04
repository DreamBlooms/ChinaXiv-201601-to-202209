# 北斗卫星导航系统国际民航标准重点问题研究与指标验证

陈颖1，卢鋆1，刘成1，邵搏²\*，张键²，原彬²1.北京跟踪与通信技术研究所，北京1000942．中国电子科技集团公司第二十研究所，陕西西安710068摘要：为促进全球卫星导航系统（GNSS）在国际航空领域的应用，国际民航组织（ICAO）正在开展面向北斗卫星导航系统（BDS）、GPS、Galileo、GLONASS 的标准与建议措施（SARPs）的研究、验证与升级工作。BDS自2010年启动ICAO 标准化工作以来，历时11年，参加了50余次技术会议，提交了90余份、千余页技术文件，涉及2000余项问题，关闭了189项验证指标。本文重点围绕时间与坐标基准、射频信号特征、空间信号性能等北斗标准国际化推进过程中的重点问题开展论述。北斗时与国际UTC的偏差保持在50ns以内（模1s)，北斗坐标系与ITRF-2014之间的差异不超过3cm；对北斗民用信号落地电平、信号质量、抗干扰能力进行了分析和验证，构建了北斗空间信号畸变模型；最后，明确了北斗在 ICAOSAPRs框架下的服务性能定义和计算方法，并利用系统实际数据验证北斗系统空间信号性能均满足设计指标要求。以上的分析、模型与验证结果表明，北斗系统具有良好的时空兼容与互操作基础，射频信号质量高、抗干扰能力强，相关内容满足指标要求，能够提供面向国际航空领域的高安全高完好性导航服务，已被写入ICAOBDSSARPs中，为我国北斗系统国际化及民航领域推广应用奠定了良好的理论、标准及验证基础。

关键词：北斗卫星导航系统；国际民航标准；时间与坐标基准；射频信号特征；空间信号性能

# Research and Assessment on key issues of ICAO SARPs for BeiDou Navigation Satellite System

CHEN Ying1,LU Jun1,LIU Cheng\*1,SHAO $\mathbf { B o } ^ { 2 }$ , ZHANG Jian²,YUAN Bin² 1. Beijing Institute on Tracking and Telecommunication Technology, Beijing 1Ooo94, China 2.The 2Oth Research Institute of CETC,Xi'an 710068, China

Abstract: To promote the application of Global Navigation Satelite system (GNSS） in the international aviation field, the International Civil Aviation Organization (ICAO) is carrying out the research, verification and upgrading of Standards and Recommended Practices (SARPs） for Beidou Navigation Satelite System (BDS), GPS, Galileo and GLONASS. Since 2010, BDS has started the ICAO standardization work, which has lasted for 1l years. It has participated in more than 50 technical discussions,submitted more than 90 technical documents with more than 1,000 pages,answered more than 2OOO questions,and closed 189 verification indicators. Since BDS

通信作者：邵搏，night_boris83@163.com  
资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

involves a lot of work at the level of ICAO SARPs,this paper focuses on the time and coordinate reference, radio-frequency signal characteristics, signal-in-space performance which are the key indicators in the process of the internationalization of BDS standards。The deviation between BDT and UTC shall be kept within 5Ons (model 1s),and the difference between BDCS and ITRF-2014 shall not exceed 3cm; The ground level, signal quality and anti-interference ability of BDS civil signal are analyzed and verified,and the BDS spatial signal distortion model is constructed; Finally, the service performance definition and calculation method of BDS under the framework of ICAO SARPRs are clarified,and the actual system data are used to verify that the spatial signal performance of BDS meets the design index requirements.The above analysis，model and verification results show that BDS has good space-time compatibility and interoperability foundation,high RF signal quality and strong anti-interference ability, relevant contents meet the index requirements,and can provide high safety and high integrity navigation services for the international aviation field, which has been written into ICAO BDS SARPS,It has laid a good theoretical,standard and verification foundation for the internationalization of BDS and the promotion and application in the field of civil aviation.

Keywords: BDS； ICAO SARPs; time and coordinate reference; radio-frequency signal characteristics; signal-in-space performance

# 1引言

国际民航组织（ICAO）是联合国中负责处理国际民航事务的专门机构，是政府间的国际组织，中国民航局（CAAC）是中国在ICAO的代表。

在ICAO 组织架构中，成员国大会是ICAO 最高权力机构，理事会是向成员国大会负责的常设行政机构，理事会下设的空中航行委员会（ANC）是ICAO 具体负责有关卫星导航服务民航相关事宜的职能机构，ANC下设的导航系统专家组（NSP）具体负责航空导航技术研究和标准制定工作。

NSP 目前正在开展面向北斗卫星导航系统（BDS）、GPS、Galileo、GLONASS的标准与建议措施（SARPs）的研究、验证与升级工作，ICAO SARPs是由ICAO 基于《国际民用航空公约》组织制定的国际民航统一规则，其目的是为了促进国际民用航空事业发展和保证国际航空安全。

2010 年，北斗系统开启了在ICAO的标准化工作。2010年9月，在ICAO第37届大会上，CAAC 正式提交了北斗系统进入ICAO 标准的申请。2011年1月ICAO 第 192次理事会上，ICAO以决议形式同意北斗系统逐步进入国际民航组织标准。CAAC 和中国卫星导航系统管理办公室（CSNO）联合成立了北斗国际民航组织标准化工作团队，全面参与ICAO通信作者：邵搏，night_boris83@163.com资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

SARPs修订工作。截至 2020年11月，先后参加了导航系统专家组工作组会议、验证工作组网络电话会议以及专题技术讨论会议等50次技术讨论，共提交90余份、千余页文件，答复问题 2000 余项，关闭189 项验证指标[1]。

北斗国际民航组织标准化工作团队成功推进BDS全部性能指标完成专家技术验证，标志着 BDS 正式写入ICAO 标准的最核心、最主要工作已经完成，为全面实施中国民航标准国际化战略、推进新时代民航强国建设与北斗系统工业标准制定、“十四五"期间全面推进北斗系统航空应用奠定了坚实基础[2]。

在历时11年的过程中，北斗卫星导航系统国际民航标准研究与制定牵涉内容繁多，本文重点围绕时间与坐标基准、射频信号特征、空间信号性能等北斗标准国际化推进过程中的重点指标，对北斗在ICAO标准中的实现情况进行论述。

# 2时间与坐标基准

# 2.1 时间基准

BDS 的时间基准为北斗时（BDT)。BDT采用国际单位制（SI)秒为基本单位连续累计，不闰秒，起始历元为2006年1月1日协调世界时（UTC)00时00分00秒。BDT通过UTC（NTSC)与国际UTC 建立联系，BDT与国际UTC 的偏差保持在 50 纳秒以内（模1秒）[3]。BDT 的要求已经正式写入ICAO BDS SARPs第3.1.4.4 节[4]。

# 2.2 坐标基准

BDS 的坐标基准为北斗坐标系（BDCS)，坐标原点位于地球质心，Z 轴指向国际地球自转服务组织（IERS）定义的参考极（IRP）方向，X轴为IERS 定义的参考子午面（IRM）与通过原点且同Z轴正交的赤道面的交线，Y轴与Z、X 轴构成右手直角坐标系[3]。BDCS参考椭球的几何中心与地球质心重合，参考椭球的旋转轴与Z 轴重合，参考椭球定义的基本常数见表1。

表1BDCS参考椭球的基本常数  
Table1 Parameters of BDCS reference ellipsoid   

<html><body><table><tr><td>NO</td><td>Parameters</td><td>Value</td></tr><tr><td>1</td><td>Semi-major axis</td><td>α = 6378137.0 m</td></tr><tr><td>2</td><td>Geocentric gravitational constant</td><td>μ = 3.986004418 × 1014 m³/sec²</td></tr><tr><td>3</td><td>Flattening</td><td>f = 1/298.257222101</td></tr><tr><td>4</td><td>Earth's rotation rate</td><td>Ωe = 7.2921150 × 10-5 rad/sec</td></tr></table></body></html>

BDCS的定义与国际地球参考框架（ITRF）一致，BDCS与ITRF-2014之间的差异不超通信作者：邵搏，night_boris83@163.com资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

过3厘米 $( 9 5 \%$ ）[5]。ICAO SARPs 中GPS、Galileo 等采用的WGS-84 坐标系也是基于 ITRF实现的，在航空应用中WGS-84与BDCS之间的差异可以忽略。BDCS的定义以及与ITRF/WGS-84 的差异已经写入ICAO BDS SARPs第3.1.4.5 节以及附件D 第4.1.4.9 节[4]。

# 3射频信号特征

# 3.1 落地电平

按照 ICAO SARPs对落地电平的接收要求，在高于5度仰角和使用3dBi线性圆极化天线条件下，接收到GPS卫星L1C/A信号的落地电平为-158.5dBW至-153dBW6，接收到L5信号的落地电平为-157.9dBW至-150dBW[7];接收到GLONASS卫星L1OF信号的落地电平为-161dBW 至-155.2dBW[，L1OC 信号的落地电平为-158.5dBW 至-155.2dBW，L3OC 信号的落地电平为-158.5dBW 至-155.2dBW[8]；接收到 Galileo 卫星 E1 信号的落地电平为-157.9dBW至-151.45dBW，E5a 信号的落地电平为-155.9dBW至-149.45dBW[9]。

北斗卫星导航系统 B1I、B1C、B2a 空间信号接口控制文件中明确给出了B1I、B1C、B2a 的最低落地电平，未给出最高落地电平的相关信息。从卫星发射功率调节能力、天线在不同离轴角的增益差异、传播距离不同造成的路径损耗差异、大气损耗等方面，对 BDS 在B1I、B1C、B2a上的最高落地电平进行了推算。

BDS在B1I、B1C和B2a频点上的落地电平如表2所示，相关要求已正式写入ICAO BDSSARPs第3.7.3.1.4.8.4节、第3.7.3.1.4.9.4节和第 3.7.3.1.4.10.4 节[4]。

表2BDS在B1I、B1C和B2a频点上的落地电平  
Table 2 B1l、 B1C and B2a ground level of BDS   

<html><body><table><tr><td>Channel</td><td>Satellite Type</td><td>Received</td></tr><tr><td rowspan="2">B1I</td><td>MEO</td><td>-163Dbw~-154.8dBW</td></tr><tr><td>IGSO</td><td>-163dBW~ -156.5dBW</td></tr><tr><td rowspan="2">B1C</td><td>MEO</td><td>-159dBW~-152.5dBW</td></tr><tr><td>IGSO</td><td>-161dBW~-153.5dBW</td></tr><tr><td rowspan="2">B2a</td><td>MEO</td><td>-156dBW~-148.5dBW</td></tr><tr><td>IGSO</td><td>-158dBW~ -150.5dBW</td></tr></table></body></html>

# 3.2 信号质量

依据北斗MEO卫星和IGSO卫星设计要求，从频域特性、相关域特性、调制特性等方面对 MEO卫星和IGSO卫星进行了信号质量评估，评估结果分布如表3和表4所示，测试项均符合指标要求。

表3BDSMEO和IGSO卫星信号质量评估结果 Table 3 Signal quality evaluation of BDS MEO and IGSO satellites

通信作者：邵搏，night_boris83@163.com  
资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

<html><body><table><tr><td>NO</td><td>Item</td><td>Detail</td><td colspan="2">Requirements</td><td>MEO results ）</td><td>IGSO results</td></tr><tr><td>1 2</td><td>Frequency characteristics</td><td>Spectral density with excess radiation power Phase Noise</td><td colspan="2">1）B1±45MHz≤-35dBW/KHz 2）B2±45MHz≤-35dBW/KHz 1）-35dBc/Hz @1Hz 2）-60dBc/Hz @1Hz 3）-80dBc/Hz @1Hz 4）-85dBc/Hz @1Hz 5）-90dBc/Hz @1Hz 6）-95dBc/Hz @1Hz</td><td>1 -85.3dB 2）-88.8 dB 1) -54.07 dB 2) -72.25 dB 3） -83.21 dB 4) -93.82 dB 5) -98.31</td><td>1) -91.03dB 2) -89.16dB 1) -57.13dB 2) -73.45dB 3) -85.69dB 4)</td></tr><tr><td>3</td><td></td><td>In-band spurious Associated</td><td>≤-50dBc</td><td></td><td>dB 6 -117.63 dB -78.26 dBc 1)</td><td>5) -101.67dB 6 -106.21dB -64.38 dBc 1）-0.021</td></tr><tr><td>4</td><td>Correlation characteristics</td><td rowspan="2">losses due to load distortion Zero crossing deviation of S</td><td>1）B1:0.3dB 2）B2:0.6dB</td><td></td><td>-0.105dB 2) 0.014dB 0.086ns</td><td>dB 2) 0.016 dB 0.057ns</td></tr><tr><td>5</td><td>curve Signal component effective power ratio</td><td>≤0.5ns 0.5dB</td><td></td><td>0.045dB</td><td>-0.014dB</td></tr><tr><td>6 7</td><td>Modulation characteristics</td><td>deviation Carrier phase deviation between signal components</td><td>0.1rad</td><td></td><td>0.032rad</td><td>0.045rad</td></tr></table></body></html>

# 3.3 抗干扰能力

抗干扰能力是卫星导航服务的一项重要指标，国际民航组织、航空无线电技术委员会、

通信作者：邵搏，night_boris83@163.com  
资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

美国航空无线电协会以及美国联邦航空局等相关标准文件对抗干扰能力具有规范化要求，关于 GPS 和GLONASS 抗干扰的描述是：在特定的航空电磁干扰环境下，GPS 伪距跟踪精度为$0 . 3 6 \mathrm { m }$ ，GLONASS 伪距跟踪精度为 $0 . 8 \mathrm { m }$ 。在标准化测试框架下，BDSB1C 和B2a信号在有限带宽白噪声容限干扰，连续波容限干扰和脉冲容限干扰等各类型干扰容限下，伪距跟踪精度分别优于0.5米和0.3米(1 sigma)，测试结果如图1和图2所示[10]。该测试结果已经得到了ICAO NSP的认可，相关要求已正式写入ICAOSARPs。

0.60   
0.30 Wwwwwwwwww   
0.15   
0.00   
1,555.0 1, 559.6 1, 564. 1 1, 568. 7 1, 573. 2 1, 577. 8 1, 582.3 1, 586.9 1, 591. 4 1, 596   
Pulse Interference Frequency (MHz)

![](images/d3a6a458d8bf0c87e844367ed3ffee77094d4c5deddd34dbd002b11dff3e57a2.jpg)  
图1BDSB1C信号跟踪误差  
图2BDSB2a信号跟踪误差

# 3.4 空间信号畸变模型

导航卫星信号由于各种非预期原因，可能产生一定畸变。这种畸变对差分用户可能带来潜在威胁，一般通过信号质量监测手段进行监测。为评估信号质量监测手段的有效性，需要通信作者：邵搏，night_boris83@163.com资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

对信号畸变进行有限的建模描述，明确信号质量监测所需要针对的具体畸变特点和畸变程度。目前国际民航标准里对GPS、GLONASS 导航信号的畸变采用TM-A、TM-B、TM-C模型描述[6]。

针对B1C 和B2a信号特性，结合北斗卫星实际状态，对北斗信号畸变模型威胁空间参数（即△、σ、fd参数）基于三个原则进行分析：1）如果参数值已经超过卫星的物理可实现性，则不作为威胁空间的参数范围；2）如果参数值导致的测距误差过大，容易被检测到，则不作为威胁空间的参数范围;3)如果参数值导致的监测站与用户机之间的差分误差较小，不影响系统服务性能，则不作为威胁空间的参数范围。

考虑监测接收机、用户接收机有严格的设计约束，通过有限范围的遍历进行分析畸变导致的最大差分误差[1]。BDS 星上测距偏差在 TM-A 模型下与参数 $\Delta$ 的变化关系和在 TM-B模型下与参数 fd的变化关系分别如图3 和图4所示，TM-C 模型的参数范围为 TM-A、TM-B的组合。

![](images/6288052ff3d0b12db497216969dc29ffe0e21e5b074ac75265ad2217be6d9b9e.jpg)  
图3TM-A模型BDS星上测距偏差与参数 $\Delta$ 的变化关系(左：B1C，右：B2a)

![](images/022f8e28f0eec4647b9fe066a529755c513b3cd2e837baf9c8dca7d598cb7fd9.jpg)  
图4TM-B模型BDS星上测距偏差与参数 fd的变化关系（左：B1C，右：B2a)

BDS B1C 和B2a信号在TM-A、TM-B、TM-C畸变模型下威胁空间参数范围如表 4所示，BDS 的畸变模型已正式写入ICAO SARPs 附件D 第8章[]

表 4BDS空间信号畸变模型威胁空间参数范围  
Table 3Threat Space for BDS B1C and B2a signals   

<html><body><table><tr><td>Signal</td><td>TM-A</td><td>TM-B</td><td>TM-C</td></tr><tr><td>BDS B1C</td><td>-0.05≤△≤0.05</td><td>0.1≤σ≤20（Mnepers/s）</td><td>-0.05≤△≤0.05（chip)</td></tr><tr><td></td><td>（chip）</td><td>1.5≤fd≤18 (MHz)</td><td>0.1≤σ≤20（Mnepers/s）</td></tr></table></body></html>

通信作者：邵搏，night_boris83@163.com资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

<html><body><table><tr><td rowspan="2">BDS B2a</td><td rowspan="2">-0.5≤△≤0.5 （chip）</td><td rowspan="2">0.1≤σ≤18（Mnepers/s） 4≤fd≤18 (MHz)</td><td>1.5≤fd≤18 (MHz) -0.5≤△≤0.5（chip)</td></tr><tr><td>0.1≤σ≤18（Mnepers/s） 4≤fd≤18 (MHz)</td></tr></table></body></html>

# 4北斗空间信号性能

北斗卫星导航系统空间信号性能设计指标分为四类。一，精度：包含全球平均水平/垂直精度指标和最坏点水平/垂直精度指标；二，完好性：包含单星完好性和星座完好性,用以表征系统单星或多星同时出现服务故障的概率；三，连续性：表征一个"健康"状态的公开服务空间信号能在规定时间段内不发生非计划中断而持续工作的概率；四，可用性：表征北斗星座中规定轨道位置上的卫星提供"健康"状态的空间信号的概率。

上述性能指标均已正式写入ICAO SARPs标准，本文基于2019年7月1日至7月30日中国境内监测接收机接收的数据，对北斗全球卫星导航系统空间信号性能指标实现情况进行验证。

# 4.1 精度

北斗全球卫星导航系统全球平均水平精度指标 $6 . 0 \mathrm { m }$ ，全球平均垂直精度指标 $1 0 . 0 \mathrm { m }$ 最坏点位置水平精度指标 $1 2 . 0 \mathrm { m }$ ，最坏点垂直精度指标 $2 2 . 0 \mathrm { m }$ 。依据 GPS SPS 性能标准中全球平均和最坏位置处的位置误差计算方法，结合北斗系统的实际情况，北斗B1C、B2a频点公开服务位置误差确定步骤如下：

1）确定星座情况：

a.全星座24颗北斗三号MEO卫星+3IGSO;

b.任意缺失两颗卫星情况：（在一个回归周期内任意时刻出现2颗卫星故障的概率极低),鉴于北斗三号24颗MEO卫星均匀分布在3个轨道面，各个轨道面夹角为 $1 2 0 ^ { \circ }$ 故考虑缺失的这两颗卫星在任意一个轨道面和分别位于某两个轨道面上即可；另外由于卫星轨道是对称的（近圆轨道)，综合以上情况，给出以下几种缺失两颗卫星的星座情况：缺失 MEO-07/MEO-08，缺失 MEO-07/MEO-09，缺失 MEO-07/MEO-15，缺失MEO-08/MEO-01,缺失MEO-08/MEO-02,缺失MEO-08/MEO-15,缺失MEO-08/MEO-03,缺失 MEO-08/MEO-04;

2）计算条件：截止高度角 $5 ^ { \circ }$ ，数据采样点： $5 ^ { \circ } \times 5 ^ { \circ }$ 格网点，计算间隔：5分钟，计算周

通信作者：邵搏，night_boris83@163.com  
资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

期： $7 { \times } 2 4$ 小时；

3）在1）和2）的前提条件下，计算全球区域内一个周期内各个格网点的HDOP（水平精度因子，Horizontal Dilutionof precision）和 VDOP（垂直精度因子，Vertical Dilution ofprecision);

4）按照置信度为 $9 5 \%$ 统计一个周期内所有格网点的HDOP和VDOP值;

5）求取所有格网点的均值和最大值（最差值);

6）按照以下公式可获得全球平均和最差点处位置误差：

$$
\begin{array} { l } { S P P ( H ) = U E R E \times H D O P } \\ { S P P ( V ) = U E R E \times V D O P } \end{array}
$$

一个周期内所有格网点的HDOP、VDOP均值和最差值统计情况如下表所示：

表5DOP统计值（ $9 5 \%$ ） Table 5 Statistics $( 9 5 \% )$ of DOP   

<html><body><table><tr><td></td><td>Mean of HDOP</td><td>Mean of VDOP</td><td>Maximum of HDOP</td><td>Maximum of VDOP</td></tr><tr><td>24MEO+3IGSO</td><td>1.14</td><td>1.92</td><td>1.41</td><td>2.35</td></tr><tr><td>2 satellites invalid</td><td>1.5</td><td>2.5</td><td>2.2</td><td>4.3</td></tr></table></body></html>

取UERE（用户等效距离误差，User Equivalent Range Error）为 SISRE（空间信号距离误差，Signal in Space Range Error）与UEE（用户设备误差，User Equipment Error）的平方和，SISRE 取为任意龄期值 $4 . 6 \mathrm { m }$ ，UEE取 $2 . 0 \mathrm { m }$ ，进行最坏点位置和全球平均的定位精度计算如下：

$$
U E R E = ~ ( ( 4 . 6 \times 4 . 6 ) + ~ ( 2 . 0 \times 2 . 0 ) ) ~ ^ { I / 2 } \mathrm { = } 5 . 0 m
$$

$$
S P P ( H ) _ { W O R S T } { = } 5 . O { \times } 2 . 2 { = } I I . O m
$$

$$
S P P ( V ) _ { W O R S T } { = } 5 . 0 { \times } 4 . 3 { = } 2 I . 5 m
$$

$$
S P P ( H ) _ { A V E } { = } 5 . O { \times } I . I 4 { = } 5 . 7 m
$$

$$
S P P ( V ) _ { A V E } { = } 5 . 0 { \times } I . 9 2 { = } 9 . 6 m
$$

全球平均水平精度为 $5 . 7 \mathrm { m }$ ，全球平均垂直精度为 $9 . 6 \mathrm { m }$ ；最坏点位置水平精度为 $1 1 . 0 \mathrm { m }$ 最坏点垂直精度为 $2 1 . 5 0 \mathrm { m }$ ，能够满足空间信号精度指标要求。

# 4.2 完好性

单星完好性风险指任意单颗卫星出现主要服务故障的概率，设计指标为300 秒内用户接收机天线没有收到告警信息的概率，不应超过 $\mathrm { 1 { \times } } \mathrm { 1 0 ^ { - 5 } }$ 每小时；星座完好性风险指两颗或多颗卫星同时出现主要服务故障的概率，设计指标为300秒内用户接收机天线没有收到告警信息的概率，不应超过 $\boldsymbol { 1 \times } \boldsymbol { 1 0 } ^ { - 7 }$ 每小时。

通信作者：邵搏，night_boris83@163.com资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

测试使用数据为7月1日至7月30日中国境内监测接收机接收的B-CNAV1和B-CNAV2导航电文中的 SISA（空间信号精度指数）参数，中国境内监测接收机接收的B-CNAV1和B-CNAV2导航电文参数，包括卫星星历、钟差、HS（卫星健康状态）、DIF（电文完好性标识）、SIF（信号完好性标识）和AIF（系统告警标识）参数。完好性分析步骤如下：

(1）利用广播星历(含钟差)和精密星历(含钟差)，计算得到每颗健康卫星的径向、切向、法向和钟误差;

（2）计算每颗卫星瞬时SISRE，计算方法如下：

$$
S I S R E = \sqrt { ( \beta \times R - c \times T ) ^ { 2 } + \frac { 1 } { \alpha } ( A ^ { 2 } + C ^ { 2 } ) }
$$

其中， $R$ 表示径向误差， $c$ 表示法向误差， $A$ 表示切向误差， $T$ 表示卫星钟偏差， $\boldsymbol { \mathbf { \mathit { c } } }$ 为光速，$\beta$ 为比例因子（IGSO取0.99，MEO取0.98）， $\alpha$ 为比例因子（IGSO 取127，MEO 取54）。

（3）对于BIC/B2a频点计算SISA，SISA值由B1C 信号导航电文B-CNAV1或 B2a信号导航电文B-CNAV2中播发的 $S I S A I _ { o e }$ （卫星轨道切向和法向精度）和 $S I S A I _ { o c b }$ （卫星径向和卫星钟差精度）、 $S I S A I _ { o c I }$ （卫星钟频偏精度指数）、 $S I S A I _ { o c 2 }$ （卫星钟频漂精度指数）参数综合计算。具体计算方法如下：

： $S I S A _ { o e }$ 取导航电文中 $S I S A I _ { o e }$ 对应等级"N"的上限值， $S I S _ { o c b }$ 取导航电文中 $S I S A I _ { o c b }$ 对应等级"N"的上限值， $S I S A _ { o c I }$ 与 $S I S A _ { o c 2 }$ 的等级转换算法见以下公式：

$$
S I S A _ { o c 1 } = 2 ^ { - ( S I S A I _ { o c 1 } + 1 4 ) }
$$

$$
S I S A _ { o c 2 } = 2 ^ { - ( S I S A I _ { o c 2 } + 2 8 ) }
$$

$S I S A _ { o c }$ 计算方法见以下公式：

$$
S I S A _ { o c } = S I S A _ { o c b } + S I S A _ { o c 1 } \left( t - t _ { o p } \right) , \quad t - t _ { o p } \leq 9 3 6 0 0 s
$$

$$
S I S A _ { o c } = S I S A _ { o c b } + S I S A _ { o c 1 } \left( t - t _ { o p } \right) + S I S A _ { o c 2 } \left( t - t _ { o p } - 9 3 6 0 0 \right) ^ { 2 } , \quad t - t _ { o p } > 9 3 6 0 0 s
$$

SISA计算方法见以下公式：

$$
S I S A = \sqrt { \left( S I S A _ { o e } \times \sin 1 4 ^ { \circ } \right) ^ { 2 } + S I S { A _ { \mathrm { o c } } } ^ { 2 } }
$$

（4）将各卫星SISRE值与4.42倍SISA限值比较，判断是否超过限值；

（5）统计单星SISRE 超过限值的概率作为单星完好性风险；统计由于共同原因引起的两颗及以上卫星SISRE超过限值的概率作为星座完好性风险。

通信作者：邵搏，night_boris83@163.com资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

部分卫星4.42倍SISA限值与SISRE对比关系如图5和图6所示，图中红色曲线为4.42倍的SISA，蓝色曲线为SISRE。未有单星 SISIRE超过限值的现象发生，可以满足 $\mathrm { { 1 { \times } } \mathrm { { 1 0 } ^ { - 5 } } }$ 每小时星座完好性风险指标要求；未有两颗或两颗以上卫星 SISRE 由于共同原因超过限值的现象发生，可以满足 $\boldsymbol { 1 \times } \boldsymbol { 1 0 } ^ { - 7 }$ 每小时星座完好性风险指标要求。

![](images/07463481d4403e9e2afb3cf1d40b8ed0fd64e3886c339eccebdeb09d78cfc138.jpg)  
图5北斗28号星4.42倍SISA限值与SISRE对比关系

![](images/56c97e6b4d6a1ae1bc38e9b1b30fdc871a2d55f4c619693826775e2f2cb87590.jpg)  
图6北斗38号星4.42倍SISA限值与SISRE对比关系

# 4.3 连续性

空间信号连续性是指一个“健康"状态的公开服务空间信号能在规定时间段内不发生非计划中断而持续工作的概率。北斗IGSO 和MEO卫星在B1C 和B2a 频点上空间信号连续性指标为优于0.998 每小时。

通信作者：邵搏，night_boris83@163.com  
资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）。

测试使用数据为7月1日至7月30日中国境内监测接收机接收的B-CNAV1和B-CNAV2导航电文。空间信号连续性分析步骤如下：

（1）对于任意时刻t（固定步长 $\leq 1 0 \ \mathrm { m i n }$ )，用导航电文的判断卫星信号是否健康（可用），标识为：H_flag，H_flag $_ { ; = 0 }$ 表示信号可用。

（2）在任意时刻t，用北斗用户通知（BDSUserNotice）判断是否提前48小时发出卫星计划中断的通知，标识为：BDUN_flag，BDUN_flag $^ { = 1 }$ 表示已经发出了及时通知。

（3）在任意时刻t，任意健康卫星在没有发出中断通知而变为不健康状态用下列函数表示：

$$
F _ { C O N } ( S V _ { h } , t _ { i } ) = \left\{ \begin{array} { l l } { { 1 , } } & { { ( H _ { \mathrm { ~ - ~ } } f l a g ( S V _ { h } , t _ { i } ) = 1 ) ) \& ( B D U N _ { \mathrm { - ~ } } f l a g ( t _ { i } ) = 0 ) } } \\ { { 0 , } } & { { \qquad \quad \sharp \sharp / \sharp } } \end{array} \right.
$$

（4）对于任意卫星以固定步长（ $\mathrm { \ t _ { h o u r } { \leq } 1 }$ 小时）在每小时连续性丧失的函数表示为（该一小时的起始时刻卫星健康，但未提前 48小时收到中断通知而卫星变为了不健康状态)：

$$
F _ { C O N _ { - } h o u r } ( S V _ { h } , t _ { h o u r } ) = \left\{ \begin{array} { l l } { 1 , } & { ( H _ { - } f l a g ( S V _ { h } , t _ { h o u r } ) = 0 ) ) \& ( \exists t _ { i } \in ( t _ { h o u r } , t _ { h o u r } + 1 ) , F _ { C o N } ( S V _ { h } , t _ { i } ) = 1 ) } \\ { 0 , } & { \qquad \mathrm { i f : } t | | _ { \infty } ^ { n } } \end{array} \right.
$$

（5）星座中所有卫星一年的空间信号平均连续性为没有发生连续性丧失的一小时间隔数与总的小时间隔数的比值。

$$
P _ { C O N } = \frac { \displaystyle \sum _ { S V _ { h } } t _ { h o u r } ( 1 - F _ { C O N \_ h o u r } ( S V _ { h } , t _ { h o u r } ) ) } { N _ { h o u r s } \cdot N _ { S V } } ,
$$

其中， $\mathbf { N } _ { \mathrm { S V } }$ 一星座中的卫星数（北斗基础星座27颗)， $\mathbf { N } _ { \mathrm { h o u r s } }$ 一总的小时间隔数（不同于一年的总小时数，该值是滑动产生的)。

北斗卫星空间信号连续性结果如图7所示，北斗IGSO卫星在B1C和B2a频点上空间信号连续性的平均值为0.9982每小时，北斗MEO卫星在B1C和B2a频点上空间信号连续性的平均值为0.9983每小时，测试结果能够满足设计指标要求。

![](images/97111c0bae73d7b3274d3e3617d454f13a2b61355806f4cbb0acebf0de754ad0.jpg)  
图7北斗卫星空间信号连续性测试结果

# 4.4 可用性

空间信号可用性是指北斗星座中规定轨道位置上的卫星提供“健康"状态的空间信号的概率。可用性计算包含计划中断和非计划中断。北斗IGSO 和MEO卫星在B1C 和B2a 频点上空间信号可用性指标为优于0.98。

测试使用数据为7月1日至7月30日中国境内监测接收机接收的B-CNAV1和B-CNAV2导航电文。空间信号可用性分析步骤如下：

（1）对于任意时刻t（固定步长 $\leq 1 0 \ \mathrm { m i n }$ )，用导航电文的判断卫星信号是否健康（可用），标识为：H_flag，H_flag $_ { = 0 }$ 表示信号可用。

（2）空间信号平均可用性用下式计算：

$$
A _ { p e r - s a t } = \frac { \displaystyle \sum _ { S V _ { H } } \sum _ { t } ( 1 - H _ { - } f l a g \left( S V _ { h } , t \right) ) } { N _ { t } \cdot N _ { s V } }
$$

其中，Nsv—星座中的卫星数（北斗基础星座 27颗)， $\mathbf { N } _ { \mathrm { t } }$ 一统计总数。

北斗卫星空间信号可用性结果如图8所示，北斗IGSO卫星在B1C 和B2a频点上空间信号可用性的平均值为0.9958，北斗MEO卫星在B1C 和B2a频点上空间信号可用性的平均值为0.9954，测试结果能够满足设计指标要求。

![](images/3ad967344713c16e509790508489a109e88c9e7a7b45a846bd974b3f11c3b973.jpg)  
图8北斗卫星空间信号可用性测试结果

# 5总结

自 2010 年起，北斗系统国际标准化工作已经持续开展了十余年的推进工作，北斗卫星导航系统在国际民航标准层面涉及的工作很多，本文重点围绕时间与坐标基准、射频信号特征、空间信号性能等北斗标准国际化推进过程中的重点指标开展论述。目前，北斗时与国际UTC 的偏差保持在 50ns 以内（模1s)，北斗坐标系与ITRF-2014之间的差异不超过 3cm;北斗民用信号落地电平、信号质量、抗干扰能力的评估结果及空间信号畸变模型符合设计指标；依据北斗在ICAO SAPRs框架下的服务性能定义和计算方法，利用系统实际数据验证北斗系统空间信号性能均满足设计指标要求。上述分析、模型及验证结果等多项内容已正式写入ICAOSARPs，北斗卫星导航系统自 2018年开始，已经连续运行3年，服务性能稳定，各项性能指标均与写入ICAO SARPs的指标要求保持一致，对我国北斗系统国际化、北斗系统标准国际化及民航领域推广具有重要推动作用。后续，北斗国际标准化组织将持续完善北斗在ICAO 层面的验证工作，并进一步推进北斗在航空工业组织层面的验证工作，助力北斗"走出去"战略的顺利实施。

# 参考文献

[1]中国民用航空局．北斗国际民航组织标准完成全部技术验证取得重大突破. https://i.carnoc.com/detail/548451   
[2]新华社．北斗国际民航组织标准完成全部技术验证取得重大突破. http://www.xinhuanet.com/tech/2020-11/17/c_1126751813.htm   
[3]中国卫星导航系统管理办公室．北斗卫星导航系统空间信号接口控制文件公开服务信号 通信作者：邵搏，night_boris83@163.com   
资助信息：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省自然 科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产 业发展资金项目（项目编号20201121）。 B1C（1.0版）.2017年12月.   
[4] Qin Zhi, Wang Zhipeng,Li Xiao,Liu Yuan. BDS SARPs V1.5. Navigation Systems Panel Joint Working Groups Sixth Meeting (Virtual Meeting), 8-18 June, 2020.   
[5] Qin Zhi, Zhou Shanshi, Wang Zhipeng. Diference between BDS terrestrial reference frame BDCS and ITRF2O14. Navigation Systems Panel Joint Working Groups Fifth Meeting,Montréal, 15-24 October, 2019.   
[6] ICAO. International Standards and Recommended Practices Annex 1O Aeronautical Telecommunications Volume I. July 2018.   
[7] Ken Alexander, Tim Cashin, Barbara Clark, Karl Kovach, JPFernow,and Todd Walter. Update to Annex 10 Changes for the GPS L5 Signals. Navigation Systems Panel Joint Working Groups Sixth Meeting(Virtual Meeting), 8-18 June, 2020.   
[8] VWG Rapporteur. Proposed amendments to Annex 10, Volume I: Global Navigation Satellite System (GLONASS) provisions. Navigation Systems Panel Joint Working Groups Sixth Meeting (Virtual Meeting), 8-18 June,2020.   
[9] Eric Chatre,Natalia Castrillo. Galileo Open Service Draft SARPs. Navigation Systems Panel Joint Working Groups Sixth Meeting(Virtual Meeting),8-18 June,2020.   
[10] Qin Zhi, Wang Pengfei, Lei Chengqian, etc. Interference Mask and Anti-Interference Testing for BDS B1C and B2a signals. Navigation Systems Panel Joint Working Groups Fifth Meeting, Montréal, 15-24 October, 2019.   
[11] Qin Zhi, Cui Xiaowei, Shao Bo, Ding Qun. BDS EWF SARPs. Navigation Systems Panel Joint Working Groups Sixth Meeting (Virtual Meeting), 8-18 June, 2020.