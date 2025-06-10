# 明安图观测基地复杂电磁环境和干扰消减措施

# 耿立红 刘东浩 苏仓 李沙 颜毅华 陈志军

（中国科学院太阳活动重点实验室(国家天文台),北京,100101)

摘要：射频干扰（Radio FrequencyInterference,RFI）是射电天文观测设备无法回避的问题。国家天文台（内蒙古）明安图观测基地多台各具特色的射电观测设备、各类电磁辐射源及其传播路径共同组成了其复杂的电磁环境。现有超宽带高分辨太阳射电成像观测设备－明安图射电频谱日像仪，以及即将建设的子午二期工程的太阳行星际监测系统包括米波-十米波射电日像仪、行星际闪烁望远镜和超宽带射电频谱仪等，全部频率覆盖1MHz-15GHz，观测结果用于太阳物理、空间天气监测和预报的关键问题研究，也对电磁环境提出了更高要求。介绍了明安图观测基地的观测设备及其地理环境，给出了方位频率功率谱、立体方向图、时间频率功率谱等展示的RFI初步监测结果，讨论RFI预防、消减及RFI自监测方案。

关键词 太阳物理；空间天气；射电日像仪；子午工程；射频干扰消减中图分类号：P16 文献标识码：A 文章编号：

在射电天文观测方面，有些雄心勃勃的计划，未来要把射电天文观测设备或阵列，放在月球背面，以避开来自地球的越来越严重的射电频率干扰（Radio Frequency Interference，RFI），避开地球大气窗口限制，也避开了地面射电频谱分配资源对射电天文观测业务频谱范围需求不断拓展的限制。2019年1月4日，嫦娥四号着陆器上第一台低频射电频谱仪的三根5米天线已经在月球背面展开，其将取得的观测结果令世人期待。但地基射电天文观测设备则无此幸运。2019年1月9日英国自然杂志同期在线发表的两篇有关快速射电暴的天文学论文，迅速引发了极大的争议：是一种暂时无法解释的自然现象、外星文明的智慧还是地球人的“微波炉"辐射？即使太阳射电辐射信号比其他天体的要强，太阳射电观测设备也同样饱受复杂电磁环境干扰的困扰。RFI是所有灵敏的地面射电天文观测设备必须解决的问题。

# 1 明安图观测基地主要设备及地理环境

中国科学院国家天文台明安图观测基地（东经 $1 1 5 ^ { \circ } 1 5 ^ { \prime }$ ，北纬 $4 2 ^ { \circ } 1 2 ^ { \prime }$ ，海拔 $1 3 6 5 \mathrm { m }$ )，现有超宽带高分辨太阳射电成像观测设备一明安图射电频谱日像仪[1]（Mingantu Spectral Radioheliograph，MUSER-I和MUSER-II)、明安图三频段太阳射电望远镜[2]（Mingantu threebands Solar Telescope,MST）、两台20米口径分米波地平式抛物面天线，试验中的新型数字式甚低频射电成像望远镜阵列[3]（UItra-P)，2019-2022将建设完成子午二期工程的太阳行星际监测系统，包括米波-十米波射电日像仪（Mingantu Spectral Radioheliograph in Meter-DecameterWavelength，MUSER-II）、行星际闪烁望远镜[4]（Interplanetary Scintilation Telescope，IPS）、超宽带射电频谱仪等，表1为现有和待建设备主要参数，频率覆盖 $1 \mathrm { M H z } - 1 5 \mathrm { G H z }$ ，观测结果用于太阳物理、空间天气监测和预报的关键问题研究。一般10MHz以下频段天体射电辐射采用星载设备如WIND卫星上的Waves来观测，地基射电天文望远镜都被地球电离层阻挡在10MHz以上频段。但是伴随着太阳活动性变化，地球电离层和热层参数也表现有相应时间尺度的变化特征[5]。在太阳活动极小期，电离层截止频率可能会降低到5MHz以下，利用UItra-P有可能首次从地面成像观测到10MHz以下宇宙信号。明安图观测基地正在逐步建设成为一个大型的射电天文、特别是太阳射电天文观测基地，观测设备类型多样、300多个各类接收天线分布在约10平方公里范围内的三条旋臂及中心区、超宽频带，以及广阔草原上开放的地理环境、周围较密集的村落，电磁环境复杂。

表1明安图观测基地现有和即将建设的设备主要参数  
Tab.1 Main specifications of present/future instruments at Mingantu Observing Station   

<html><body><table><tr><td>设备名称</td><td>观测目标</td><td>观测模式</td><td>频率范围</td><td>中频带宽</td><td>单元数</td><td>单元形式</td><td>极化</td><td>分布范围</td></tr><tr><td>MUSER-I</td><td>太阳</td><td>综合孔径成像</td><td>0.4~2.0 GHz</td><td>400 MHz</td><td>40</td><td>4.5m抛物面</td><td>双圆</td><td>沿3条</td></tr><tr><td>MUSER-II</td><td>太阳</td><td>综合孔径成像</td><td>2.0~15 GHz</td><td>400 MHz</td><td>60</td><td>2.m抛物面</td><td>双圆</td><td>3.4Km长</td></tr><tr><td>MUSER-III</td><td>太阳</td><td>综合孔径成像</td><td>30~240 MHz</td><td>210 MHz</td><td>180</td><td>对数周期振子</td><td>双圆</td><td>螺旋臂，</td></tr><tr><td>Ultra-P</td><td>巡天</td><td>综合孔径成像</td><td>1~72MHz</td><td>72MHz</td><td>40</td><td>线天线</td><td>双线</td><td>约10km²</td></tr><tr><td>射电频谱仪</td><td>太阳</td><td>频谱</td><td>30MHz~15GHz</td><td>100KHz</td><td>1</td><td>振子阵+抛物面</td><td>双圆</td><td>1</td></tr><tr><td>IPS</td><td>太阳风</td><td>多波束</td><td>327/654MHz</td><td>1-10MHz</td><td>3/主站</td><td>140m*40m抛物柱面</td><td>双线</td><td>150m*200m</td></tr><tr><td>MST</td><td>太阳</td><td>三频点流量</td><td>2801/4542/9084 MHz</td><td>10MHz</td><td>1</td><td>3m抛物面</td><td>双圆</td><td>/</td></tr></table></body></html>

基金项目：国家重大科研装备研制项目（ZDYZ2009-3），中国科学院国家天文台台级调控项目（Y434141V01）资助，收稿日期：20190330，修回日期：作者简介：耿立红，女，高级工程师，博士，研究方向：射电天文技术与方法．Email：genglh@nao.cas.cn

![](images/c6cd13191d1673bb32399abef4887106ebf57627a747e3f5c6b940373c872c47.jpg)  
图1(a)明安图观测基地鸟瞰及(b)环境和观测设备布置 Fig.1 (a)Bird's eye view of Mingantu Observing Station; (b)environmentand observing facilitylocation

见图1(a)，从基地南部的山坡上大致可以看出 MUSER的天线阵沿三条旋臂（ $\mathsf { A } \backslash \mathsf { B } \backslash \mathsf { C }$ 三轴）排布。图1(b)展示了叠加在 google 地图上的观测基地，红点表示 MUSERI至MUSER II及UItra-P 沿旋臂的天线阵列单元，中心黄色矩形框分别表示办公生活区和观测区，黄线箭头引出了这两个区内的观测设备和建筑。观测基地被牧民的草场包围，标号1-5的红圈表示基地周围的五个牧民班组共105户牧民，距离基地中心 $2 { \cdot } 5 \mathrm { k m }$ ，其中3班组离B轴最远端天线仅约300米。观测区内是MUSER-I和MUSER-II室外天线单元密集的三条螺旋臂的中心区域，观测楼内有MUSER室内模拟接收机、数字接收机及监控系统。

子午工程二期的相关设备将在 2019 年开工建设，办公生活区域将向东、南扩展，各设备相对位置见图 2示意图，最下方为MUSER-III的中心振子阵，3面 $1 4 0 \mathrm { m }$ 长 $4 0 \mathrm { m }$ 宽南北向抛物柱面天线东西排列。办公生活区内的科研楼将是包括海量数据存储和处理机房、实验室密集的科研场所，综合楼内主要为生活用电设施。

![](images/1acef63927edd103dce784465be101b97e76f4ad350b3218ff5b79b5f60b1aaa.jpg)  
图2明安图观测基地办公生活区观测设备布置示意 Fig.2observing facilitylocation in office&living areaat Mingantu Observing Station

# 2 明安图观测基地RFI初步监测

在复杂电磁环境下首先要做RFI监测，以制定相应的抗干扰措施，防范、控制和消减干扰，保障射电天文观测设备的正常运行和数据可靠性。图3为明安图观测基地的部分RFI监测结果，横轴为频谱，纵轴为强度，显示了RFI随频谱和方向的变化。其中图 3 (a) $2 0 \mathrm { m }$ 天线在仰角 $3 5 ^ { \circ }$ 方位 $\cdot 4 5 ^ { \circ }$ 时接收的 $4 7 0 \mathrm { M H z } { \sim } 9 6 0 \mathrm { M H z }$ 内RFI情况；图3(b)用MUSER-I $4 . 5 \mathrm { m }$ 天线在 $0 . 4 \mathrm { G H z } { \sim } 2 . 0 \mathrm { G H z }$ 的一次RFI测量， $9 6 0 \mathrm { M H z }$ 附近手机信号是主要干扰源;图3(c)和图3(d)用 $2 0 \mathrm { m }$ 天线在 $6 0 ^ { \circ }$ 仰角 $\pm 3 0 ^ { \circ }$ 两个方位（ $0 ^ { \circ }$ 为正北方向）上监测的 $2 5 0 \mathrm { M H z } { \sim } 2 9 0 \mathrm { M H z } \ \mathrm { R F I }$ 。图4用线天线对 $1 \mathrm { M H z } { \sim } 1 0 0 \mathrm { M H z }$ 内 RFI的长期监测，横轴为时间/日期，纵轴为频谱，强度用彩色表示。

立体RFI表示法更能全面有效反映RFI分布，见图 $5 \sim$ 图9。针对太阳观测设备，图5用MUSER-I接收单元IA9 沿太阳轨道作 $0 . 4 \mathrm { G H z } { \sim } 2 . 0 \mathrm { G H z }$ 内左旋圆极化RFI测量（赤经： ${ } _ { - 9 0 ^ { \circ } \sim + 9 0 ^ { \circ } }$ 赤纬： $1 9 . 1 5 ^ { \circ } , 2 0 1 5 . 0 5 . 1 7 \rangle$ ，X轴为频谱，Y轴为赤经坐标，Z轴为相对功率，显示出RFI频谱沿当日太阳轨道分布。同样，图6为MUSER-II 接收单元HA9 $2 . 0 \mathrm { G H z } { \sim } 2 . 8 \mathrm { G H z }$ 内左旋圆极化RFI频谱沿太阳轨道分布。图7显示MUSER-I左、右旋圆极化 RFI频谱的差异。图8为20米天线和MUSER-I接收系统测的 $0 . 4 \mathrm { G H z } { \sim } 0 . 8 \mathrm { G H z }$ 和 $1 . 6 \mathrm { G H z } { \sim } 2 . 0 \mathrm { G H z }$ 左旋圆极化RFI频谱在40度仰角时随方位分布。

![](images/d71f128585109c3ae6e9b73615a38679ff5ff0f2cf11637900c3265234bc5e52.jpg)  
图3(c)  
图3 (d)

![](images/6091a5145816c0ce8ae51199168441f42078351d8ae4e7f6f6567ce3ea7e01bd.jpg)  
图3 明安图观测基地干扰测量. $\mathrm { ( a ) } 4 7 0 \ \mathrm { M H z } \sim 9 6 0 \mathrm { M H z } ( 2 0 \mathrm { m }$ 天线,仰角 $3 5 ^ { \circ }$ 方位角-45°,2010.10.22,葛亮 图);(b) $0 . 4 { \cdot } 2 . 0 \mathrm { G H z }$ (MUSER-I $4 . 5 \mathrm { m }$ 天线,2013.05.24, 王威图);(c) $\mathrm { | 2 5 0 \ M H z } \sim 2 9 0 \mathrm { M H z } ( 2 0 \mathrm { m }$ 天线,仰角 $6 0 ^ { \circ }$ 方位角-30,2014.11.20);(d) $2 5 0 \mathrm { M H z } \sim 2 9 0 \mathrm { M H z } ( 2 0 \mathrm { m }$ 天线,仰角 $6 0 ^ { \circ } .$ 方位角 $3 0 ^ { \circ } , 2 0 1 4 . 1 1 . 2 0 )$ （204号 Fig.3 RFI at Mingantu Observing Station. (a) $4 7 0 ~ \mathrm { M H z } \sim 9 6 0 \mathrm { M H z }$ 0 $2 0 \mathrm { m }$ antenna,EL 35,AZ-45o,2010.10.22，provided by Ge Liang);(b) $0 . 4 \mathrm { G H z } \sim 2 . 0 \mathrm { G H z }$ (MUSER-I $4 . 5 \mathrm { m }$ antenna,2013.05.24,provided by Wang Wei);(c) $2 5 0 ~ \mathrm { M H z } \sim 2 9 0 \mathrm { M H z }$ 0 $2 0 \mathrm { m }$ antenna, EL $6 0 ^ { \circ } , \mathrm { A Z } \cdot 3 0 ^ { \circ }$ ,2014.11.20);(d) $2 5 0 ~ \mathrm { M H z } \sim 2 9 0 \mathrm { M H z }$ 0 $2 0 \mathrm { m }$ antenna, EL $6 0 ^ { \circ }$ AZ $3 0 ^ { \circ }$ ,2014.11.20)   
图4明安图观测基地 $1 \mathrm { M H z } \sim 1 0 0 \mathrm { M H z }$ 干扰监测（2017.06.17～2017.07.06，陈林杰图） Fig.4 RFI in $1 \mathrm { M H z } \sim 1 0 0 \mathrm { M H z }$ at Mingantu Observing Station（2017.06.17\~2017.07.06,provided by Chen Linjie

![](images/47c7bdc8de7dc066304fa4f7fb226e6c072d94afebbb574d05c248e30b0230e5.jpg)  
图5用 MUSER-I 接收单元IA9 沿太阳轨道作 400MHz-2000MHz 左旋圆极化干扰测量（赤经:-90to $_ { + 9 0 }$ ，赤纬：19.15°,2015.05.17）Fig.5 RFIin 400MHz-2000MHz by IA9 of MUSER-Ialong Solar orbit（RA:-90 to $^ { + 9 0 }$ ,Dec:19.15°,2015.05.17)

![](images/9d98d7182d57d4e214e0fb471651aa0b1a657114e206615fa0b28cdb05596ee2.jpg)  
图6用MUSER-II 接收单元HA9 沿太阳轨道作 $2 . 0 \mathrm { G H z } \mathrm { - } 2 . 8 \mathrm { G H z }$ 左旋圆极化干扰测量（赤经:-90to $_ { + 9 0 }$ ，赤纬:19.15°,2015.05.17) Fig.6 RFI in $2 . 0 \mathrm { G H a } \sim 2 . 8 \mathrm { G H z }$ by HA9 of MUSER-IIalong Solar orbit ( $\mathrm { R A } { : } { - } 9 0 ^ { \circ } \sim { + } 9 0 ^ { \circ }$ ,Dec:19.15,2015.05.17)

![](images/0bb6d61d6620e4736f345bbe63ef3fdef3dfe4aeb0f7b82e2b8f626a8ae8099e.jpg)  
图7用MUSER-I 接收单元IA9 沿太阳轨道作 $0 . 8 \mathrm { G H z } \mathrm { - } 1 . 2 \mathrm { G H z }$ 左旋和右旋圆极化干扰对比（赤经:-90to $_ { + 9 0 }$ 赤纬：19.15°,2015.05.17) Fig.7 Right and left-hand circular polarization RFI in $0 . 8 \mathrm { G H z } \mathrm { - } 1 . 2 \mathrm { G H z }$ by IA9 of MUSER-I along Solar orbit（R $\mathsf { A } { : - 9 0 } ^ { \circ } \sim { + 9 0 } ^ { \circ }$ ,Dec:19.15,2015.05.17)

![](images/a1b576abf2ecade4a4276bb6dd7ed2f1b7ac4f53d709e70eabf5fb895bcca923.jpg)  
18用 $2 0 \mathrm { m }$ 天线及MUSER-I接收单元测量RFI空间分布： $0 . 4 \mathrm { G H z } { \sim } 0 . 8 \mathrm { G H z }$ 和 $1 . 6 \mathrm { G H z } { \sim } 2 . 0 \mathrm { G H z }$ 频段内RFI随方位变化（EL $4 0 ^ { \circ } , \mathrm { A Z } \pm 9 0 ^ { \circ }$ 步进 $1 ^ { \circ }$ ） Fig.8 RFI distribution in 0.4GHz\~0.8GHz and $1 . 6 \mathrm { G H z } { \sim } 2 . 0 \mathrm { G H z }$ by $2 0 \mathrm { m }$ antenna and MUSER-I receiver（EL $4 0 ^ { \circ } , \mathrm { A Z } \pm 9 0 ^ { \circ }$ step1°)

相比MUSER赤道式座架的阵列天线，地平式 $2 0 \mathrm { m }$ 天线转动范围可以覆盖高于 $1 0 ^ { \circ }$ 仰角的全部天空。用20米天线及MUSER-I 接收单元以太阳为中心进行立体方向图[6]扫描，频率通道 ${ 3 0 } ^ { \# }$ 和 $4 7 ^ { \# }$ 的左、右旋 RFI影响对比，显示同一频率通道接收的左、右旋圆极化信号差异，见图9。RFI 谱通常显示为强度随时间的变化，如W.A.Baan[7]等在研究Westerbork 综合射电望远镜 RFI消减时的观测图，图 5-9 结合观测目标和观测模式反映了RFI频谱的空间分布，长期监测如RFI分布稳定，将对制定RFI消减方案有更好的参考意义。

综上，RFI随频率、极化、指向及时间变化，也随天线高度和方向图、系统性能、观测目标和模式、RFI源相对监测设备的距离和方向等变化，用RFI监测系统测量结果评估对观测系统影响时还需考虑系统差异。

![](images/4c869bc6199f3dad19e059bbf7ed6540ed52180b72a8d6bf15d29a52e24b3422.jpg)  
图9用 $2 0 \mathrm { m }$ 天线及MUSER-I接收单元以太阳为中心进行立体方向图扫描，显示通道30#左右旋（上排）和47#左右旋（下排）RFI分布对比 Fig.9 Cubic radiation pattern centered on the Sun by $2 0 \mathrm { m }$ antenna and MUSER-I receiver,showing RFI distribution differences of $3 0 \#$ and47#,for example

# 3 明安图观测基地的RFI消减措施

在 MUSER 选址时进行了无线电环境测量和电磁干扰分析[8][9]。综合考察北京、河北、新疆、内蒙古多地，以电磁环境为首要条件，结合地形、人口密度、交通和政府支持，选择内蒙古正镶白旗为射电日像仪建设地点；将干扰容限与接收系统灵敏度相联系，采用接收系统噪声底值的1/4为干扰容限，即日像仪所允许最大干扰电平，估计日像仪低频段(MUSER-I)干扰容限（谱密度）为-181dBm/Hz。但随着科技发展和射电天文观测设备灵敏度提升，相对地RFI越来越强，电磁环境难以满足要求。根据RFI在数据流中出现阶段，常用RFI消减方法分为4种[10]，即预防（选址、建造和运行期间采取电磁环境保护、预防和监管措施）、预检测（接收系统通过预检测屏蔽掉已知强RFI）、预相关（对相关前数据基于硬件或软件作实时消减）和后相关（对相关后干涉数据的实时或离线处理)。

# 3.1 电磁宁静区建立及电磁环境保护

![](images/dfb5d98c3f4002d1c633f4a7671314b45d7e424cfa53fc2263d45897b7d1b08c.jpg)  
图10MAT电磁环境保护：a)基地正南移动通讯塔；b)移动塔关闭前（蓝线）后（红线）干扰监测情况；c）连通5个班组的光纤多媒体通讯网络 Fg0.athetddo fiber cable communication network for 5 villages around MAT

RFI来自系统外部和内部。对于外部RFI，选址和建立电磁宁静区是射电天文观测台站的首要措施。如 FAST工程[1]，2019年《贵州省 500米口径球面射电望远镜电磁波宁静区保护办法》新版公布，以台址为圆心，设置半径5km 区域核心区、 $5 \mathrm { k m } { - } 1 0 \mathrm { k m }$ 环带中间区和 $1 0 \mathrm { k m } \cdot 3 0 \mathrm { k m }$ 环带边远区。经与当地有关部门协商，2007年由内蒙古自治区发文，设立以明安图观测基地为中心半径 $1 0 \mathrm { k m }$ 射电宁静区；2012 年关闭基地正南约 2km远移动通讯塔；2014年为周边5个班组105户牧民安装光纤多媒体通讯网络，牧民们可在家上网、打座机电话、看电视和微信，也维护了牧民和基地友好关系；通过协调避免在宁静区建设新移动基站和500KV高压供电线路经过。随着 5G通讯的到来，宁静区保护内容亦须更新。图10a)b)显示关闭通讯塔后RFI明显改善，图10c)为光纤多媒体通讯网络路线。

# 3.2 电磁兼容及屏蔽

100组 $3 . 4 \mathrm { k m }$ 长光缆连接了MUSER高/低频阵100面天线和观测区中心机房，传输太阳辐射信号和设备监控信号[12]。中心机房聚集了MUSER 高/低频阵监控设备、模拟接收机、大规模高速数据采集相关处理机，有40面天线距中心机房不到 $1 0 0 \mathrm { m }$ ，约80面天线在 $7 0 0 \mathrm { { m } }$ 范围内，图11a)，须考虑机房内设备之间电磁兼容性及对 MUSER 的干扰。图11b)显示了中心机房附近和约 3km距离处1MHz-100MHz的RFI监测对比情况(2018.12.2-2018.12.3，陈林杰图)，两处RFI最大相差约40dB。按用电设备集中程度和功耗，对重点区域进行分级电磁屏蔽是计划采取的重要手段，即采用冷轧钢板、铜网等作主体屏蔽材料，对重点区域六面壳体、门窗、管线进出口进行电磁密封和屏蔽处理，阻断电磁辐射出入，进一步要对辐射强设备采取隔离措施。

![](images/456b790e643813b809d985990520c615b66aa17d6c91a6213eeb97e3f222975c.jpg)  
图11a)观测区附近天线分布；b)RFI监测（实线：观测区，虚线：距观测区 $3 \mathrm { k m }$ ，2018.12.2-2018.12.3，陈林杰图） Fig.11.aantenasdistributionofATcenterarea;b)RFImeasurementsnear(line)centerareaand3kmawayfromcenterea(dotline 2018.12.2-2018.12.3,provided by Chen Linjie)

# 3.3 MUSER宽带抗干扰设计

MUSER采用了多种抗干扰设计[12]。如：用深埋冻土层下光缆进行长距离信号传输减小传输损耗、温度变化及干扰影响；10KV 电力专线在基地附近改从地下走线，沿高压线安装防雷放电间隙和驱鸟装置；7、8月是草原雨季和雷电高发期，全部室外基墩配电箱安装浪涌保护器。观测系统自身稳定性和可靠性是RFI消减基础，对温度敏感器部件采用高精度温控。多数RFI来自天线旁瓣，要求天线方向图旁瓣低于主瓣 14dB以上。

MUSER-I：0.8-1.2GHz频段手机强干扰信号影响系统正常工作，调整备用本振频率后工作在1.0-1.4GHz避开强干扰；前端低噪声放大器加限幅；RFI超过设备安全阈值时自动控制增益，采用模块化信道降低通道间干扰。MUSER-II：前端低噪声放大器加限幅，信道预选滤波器组进行 50dB 以上抑制；前端组件输出端加固定衰减器，防止强干扰时烧毁光发射机；400MHz／80MHz双中频带宽输出兼顾工程、天文和抗干扰需求，可使接收机避免在干扰频段内工作，也可在某些频段更高时间分辨率观测。中频输出端带通滤波器进一步滤除带外噪声。应用LTCC（Low-Temperature Co-fired Ceramics）技术使系统小型化，增加系统可靠性和稳定性。

# 3.4 干扰消减方法研究

判断信号是否为RFI的标准看其在所需观测中是否为无用但可监测的信号，且是否会影响到观测的顺利进行[13]。有些干扰虽不易检测但仍可能影响观测，消减此类干扰要困难许多。

RFI 识别中，因传播路径和距离不同，色散量是区分人类活动产生信号和射电源信号的一个重要判据[10]。较多的RFI探测、识别和消减研究基于统计分析，利用大数据采用机器学习[14]完成RFI探测、识别和消减。射电天文源信息和接收系统噪声都是理想的高斯分布，因此功率探测通常基于高斯模型。高斯分布模型需要两个参数的均值和标准差，均值估计误差将影响标准差估计。未污染的数据样本遵循两个自由度的卡方分布，基于卡方分布的方法只需一个均值来定义信号统计特性。阈值设为递归估计出的均值乘以一个用户定义系数，为使均值不因RFI产生异常，最强信号对称地弃用。设定阈值同时确定了误报率和漏报率。探测强雷达脉冲干扰时，硬件成本可接受情况下以多个连续的功率值超过阈值才触发数据消隐，将大大降低误报率。但是检测连续多个样本是否超过阈值对探测弱雷达脉冲时性能不佳，用在一个时间段内超过阈值的总样本数触发数据消隐更好。专用于探测宇宙曙光和再电离时代的21CMA[15]采用统计法识别和删除非高斯型信号的RFI。并引入可见度函数系数代替可见度函数，进一步压缩快速时变RFI。RFI探测中纳入一些先验知识，将进一步降低RFI对射电天文观测的影响。由于高红移使 HI射电源谱线移到分配给雷达的频段，Allal16]在 Nancay 单天线分米波射电望远镜上采用 FPGA 实时实现基于统计分析的一种雷达脉冲消隐，并用周期平稳特性区分 RFI脉冲和脉冲星脉冲，因为大多数通讯信号都隐藏着周期性。有仿真表明在脉冲星观测中RFI周期平稳探测将优于功率探测器。在设备不同位置插入RFI周期平稳探测器将能够探测不同类型的 RFI。

对大型单射电天线，自适应旁瓣相消是常用的抗干扰方法之一[17]，本质是利用辅助阵列与主天线中干扰信号的相关性和干扰的空间特性获得辅助阵列的最优权矢量，使合成的天线方向图在干扰方向上产生零点达到干扰抑制的目的。Briggs[18]利用独立的RFI参考信号和RFI信号遵循的闭合关系来消除射电频谱仪中的RFI，该参考信号是由参考天线或馈源指向噪声源收到的信号与观测的射电天体辐射信号交叉相关获得。

对干涉仪，相比对最终可见度函数数据进行分析处理，相关技术提供了以更高时间和频率分辨率从干涉仪观测数据中识别和消减RFI的可能性，在RFI识别和消减方法开发和完善阶段以及测试阶段，采用软件相关RFI识别[19]比硬件开发周期短且更具灵活性。由于阵列单元的位置分布，RFI对于射电望远镜阵列影响不一样。对短基线来说问题更严重。但是，由于积分时间增长同时提高了对射电信号和RFI的灵敏度，用单天线进行观测（连续谱或光谱）更易受到干扰的影响[18]。在FASR(frequency agile solar radio-telescope)测试系统上[20]，提出并测试了基于方差分析的功率谱统计切除RFI的方法，从高斯型太阳射电爆发中识别并切除非高斯型 RFI。

根据接收信号的时间频率功率谱、方位频率功率谱和立体方向图的形态可辅助识别干扰，如图5-9 所示，大部分 RFI 限制在一定频率范围内，但存在于整条观测路径，有强度起伏。对少数限制在一定指向范围内和一段频段内，经过长期监测是稳定干扰，可采用空间滤波方式消减。

射电探测是太阳物理和日地空间科学的重要手段，尤其对于太阳爆发过程中的太阳非热粒子加速、发射和传播过程。总是从科学需求的角度研制新的太阳射电望远镜，而无法限制在射电天文业务的保护频率范围。一般认为大多数RFI都很强，但强太阳耀斑爆发时，射电流量密度可能会有 20-30dB 或更大的增量，且耀斑过程中包含着亚秒级脉动准周期性结构以及超精细结构[21]。弱 RFI也可能会和太阳射电辐射信号混淆。如长期的观测研究发现太阳射电爆发常常可分成一系列从长到短不同时标的爆发过程，其中尖峰辐射是最小时间尺度和空间尺度的爆发过程，可以看成是一种元爆发过程，对应于单一的磁场重联和磁能释放。根据太阳射电天文学研究，识别尖峰爆发是对新一代太阳射电望远镜的基本要求[22]。观测小尺度的磁场活动对于理解太阳风暴的元过程以及整体理解太阳风暴很有意义[23]。无论RFI强弱，区分RFI和太阳射电信号很重要也都是难题。

明安图观测基地电磁环境复杂，没有一种RFI消减方法满足所有设备需求，同一设备也可能需多种 RFI消减方法。这方面还有很多工作要做。

# 4 RFI监测

手机通讯是明安图观测基地RFI主要来源，5G 时代的即将来临使电磁环境随之改变。RFI长期监测是 RFI消减的前提。RFI监测一般采用各向同性天线，如GMRT[23]采用四个相同LPDA 组合，架设在 $2 0 \mathrm { m }$ 高塔上监测电磁干扰并判别干扰方向。 $6 5 \mathrm { m }$ 天马射电望远镜2008 年即开始RFI监测用于台址电磁环境评估[24]。WSRT[25]的RFI全向天线频谱监测系统每周7d每天24h无人值守地工作。LORFAR[26]因采用精确探测方法、强滤波和高接收系统线性度以及天线安装接近地面等策略，RFI 影响很小，当然也需考虑数字信号广播和风车的干扰。监测时降低时间和频率分辨率，会使RFI占比近似线性增加。这对RFI监测系统频率、时间、空间分辨率提出了要求。RFI监测系统应以实现观测设备的RFI消减为目标。需考虑实时模式下预检测以及离线模式下从大型望远镜阵列干涉数据中检测RFI[10]。MUSER这类设备是分布在广大区域的传感器阵，精确校准是提供有意义科学图像的关键，校准必须解决天线增益和相位以及大气和电离层扰动问题。如节2图所示，系统复杂、阵列单元间、同单元频率通道间、极化间的差异无疑增加了系统校准和RFI消减难度。除常规RFI监测方法外，我们提出 RFI自监测方案，即利用射电天文观测设备进行RFI监测，辅助采用全向天线和参考天线。

# 5 结论

RFI对观测设备的影响与多种因素有关，RFI消减是一项系统性工作。针对性研究RFI消减方法是射电天文研究重要课题。已采取的RFI消减措施保障了MUSER的正常运行，即将开始研制建设的子午二期工程等设备，使频率覆盖范围达1MHz-15GHz，对电磁环境提出更高要求。明安图观测基地多种设备及RFI在极化、时间、频谱和空间上的复杂变化和分布，还包含许多随机和模糊因素，说明了电磁环境的复杂性，电磁宁静区保护、EMC、RFI监测识别评估及消减仍然面临着巨大挑战。组合采用参考天线或参考阵列、全向天线和射电天文观测设备的RFI监测方案将为RFI消减提供更有效的信息。

# 参考文献：

1．颜毅华,张坚,陈志军,等．关于太阳厘米一分米波段频谱日像仪研究进展[].天文研究与技术.2006,3(2):91-98   
Yan Yihua,ZhangJian,Chen Zhijun,etal.Progresson Chinese SolarRadioheliographincm-dm Wavebands[J].Astronomical   
Research & Technology. 2006,3(2): 91-98   
2．耿立红,谭程明,敦金平,等.三频段太阳射电望远镜与空间天气[].天文研究与技术.2018,15(4):381-389   
Geng Lihong,Tan Chengming,DunJinping,etal.Twonew3-bandsolarrdiopolarimetersandspaceweather[].Astronomical   
Reaearch & Technology.2018,15(4):381-389 3.Linjie Chen,AminAminaei,Leonid I. Gurvits,et.al.Antennadesignand implementation forthefuture space Ultra-Long wavelength radio telescope[J].Exp Astron.2018,(45):231-253. htps://doi.0rg/10.1007/s10686-018-9576-3   
4.Yan Yihua,Wang Wei,LiuFei,et.Al.New Interplanetary Scintilltion Aray inChina for Space Weather[].DOI: 10.31401/SunGeo.2018.02.05 ,pp.153-155   
5．刘立波,万卫星,陈一定,等.电离层与太阳活动性关系[J].科学通报.2011,56(7):477-487   
Liu LB,WanWX,ChenYD,etal.Solaractivityeffectsoftheionosphere:Abriefreview.Chinese SciBul,2,6,doi: 10.1007/s11434-010-4226-9   
6．耿立红,刘东浩,陈志军,等.基于立体方向图和十字跟踪扫描法校准天线指向[].电波科学学报.2019,34(2)   
Geng Lihong，Liu Donghao，Chen Zhijun，etal.Antenna pointing calibration basedoncubic radiation patern andcross scan [J]. Chinese Journal of Radio Science. 2019,34(2)   
7．W.A.Baan,P.A.Fridman,R.P.Milenaar. Radio frequency interference mitigationat the westerbork synthesisradio telescope:algorithms,testobservations,and systemimplementation[J].The astronomicaljournel.2004,128(8):933-949 8．陈志军,颜毅华,刘玉英,等.关于中国厘米一分米波频谱日像仪（CSRH）选址与无线电环境监测[].天文研究与技术.2006, 3(2):168-175   
Chen Zhijun,Yan Yihua,LiuYuying,et.al.Site SurveyandRFITestfor CSRH[J].AstronomicalResearch &Technology.2006, 3(2):168-175   
9．王威,陈志军,刘玉英,等.日像仪的电磁干扰分析[I].天文研究与技术.2006,3(2):176-182   
Wang Wei,Chen Zhijun,Liu Yuying,etal.Electromagnetic Interference Analysis for CSRH[J].Astronomical Research & Technol0gy. 2006,3(2):176-182   
10．安涛,陈骁,Mohan Prashanth,等.射电频率干扰的消减[I]．天文学报.2017,58(5):43-1-43-22   
An Tao，Chen Xiao，Mohan Prashanth，etal.Radio frequency interference mitigation[J].ACTA ASTRONOMICA SINICA. 2017,58(5):43-1-43-22   
11．张海燕．中国射电天文频率保护进展[J]．天文学进展.2017,35(4):473-480   
Zhang Haiyan.Protection Progress onRadio AstronomyFrequencies in China[J].ProgressinAstronomy.2017,35(4):473-480 12．耿立红，颜毅华,宋庆辉，等．明安图射电频谱日像仪高频阵模拟接收机研制 [].天文研究与技术.2016,13(2):160-169. Geng Lihong，Yan Yihua，Song Qinghui，etal. MUSER-II Analog Receiver System Designing and Developing[].Astronomical Research & Technology. 2016,13(2):160-169   
13．ITU-R RA.2126 号报告，射电天文学中的射频干扰减缓技术(ITU-R 第 237/7 号课题).2007   
14.JoelAkeret,Chihway Chang,AurelienLucchi,etal.Radio frequencyinterference mitigationusingdeepconvolutional neural networks[J]. rXiv:1609.09077v2. 2017.   
15.Huang Yan，Wu Xiangping，Zheng Qian,etal.Theradio environment of 21 Centimeter Array:RFIdetection and mitigation[J]. RAA. 2016,16(2): 1-10. doi:10.1088/1674-4527/2/036   
16.D.Ait-All,R.Weberaband C.Dumez-Vioua.RFImitigationat NancayObservatory:Impulsive Signal Processing[C].RFI mitigation workshop - RFI2010.2010   
17．黄达,王壮,程翥,等.精确时延补偿的自适应旁瓣相消射电抗干扰方法研究[I].天文研究与技术.2016,13(3):284-292 Huang Da,Wang Zhuang,Cheng Zhu,etal.Mitigationof theradio freqency interferenceusinganadaptive side-lobe cancelltion based on accurate delay compensation[J].Astronomical Research & Technology.2016,13(3): 284-292 18.F.H.Briggs,JFBelland M.J.Kesteven.Removing radio interference fromcontaminated astronomical spectrausing an independent reference signal and closure relations[J].The Astronoical Journal.2ooo,120:3351-3361   
19.Adam Deller. Software correlators as testbeds for RFI algorithms[C]. RFI mitigation workshop-RFI2010.   
20.Xiaoli Wang, Hongya Ge,Gelu M.Nita,et al.Radio frequency interference excision in solar dynamic spectra using variance-based spectral statistics[C].208IEEE International Conferenceon Acoustics,Speechand Signal Processing.2008. DOI: 10.1109/ICASSP.2008.4518445   
21．谭宝林,程俊,谭程明,等.尖峰爆发标度率及对新一代太阳射电望远镜参数的约束[].天文学报.2018,58(4):37-1-37-13 Tan Baolin,Cheng Jun,Tan Chengming,etal.Scaling-lawsofradiospike burstsand theirconstraintsonnew solarradio telescopes[J]. Acta astronomica sinica. 2018,59(40):37-1-37-13   
22．汪景琇,季海生.空间天气驱动源一太阳风暴研究[J]．中国科学-地球科学.2013,43(6):883-911   
Wang Jigxiu,Ji Haisheng.Recent advances in solar storm studies in China. Science China: Earth Sciences2013,43(6): 883-911. doi: 10.1007/s11430-013-4648-8   
23．ShubhenduJoardar，RFI monitoring systemof GMRTandradio interference analysis onvarious radio-stronomy bands, http://www.ursi.org/Proceedings/ProcGA05/pdf/JE-P.3(01224).pdf   
24.Li Bin,SunRongxia,Gou Wei,etal.RFImeasurementsatthe65m Tianma Tlescope[C].RFIworkshop,Yebes,Span,June, 2017   
25．Hans vander Marel,Pieter Doner RFImeasurements atthe WSRT[C].Proceedingsof Science.RFImitigation workshopRFI2010. http://pos. sissa.it   
26.A.R.Ofringa，A.G.deBruyn，S.Zaroubi，etal.The LOFAR radio environment[J].A&A 549,A11(2013):1-15.D0I: 10.1051/0004-6361/201220293

Complex electromagnetic environment and RFl mitigation at Mingantu Observing Station

Geng Lihong，Liu Donghao， Su Cang，Li Sha，Yan Yihua，Chen Zhi jun(Key Laboratory of Solar Activity（National Astronomical Observatory），CAS，Beijing，100101, China)(Received date:20190330）

Abstract: Radio frequency interferences (RFI) and Electromagnetic compatibility (EMC)are common problems toall sensitive radio astronomical telescopes.Mingantu Observing Station of National Astronomical Observatories in Inner Mongolia is the site of the powerful Mingantu Spectral Radioheliograph (MUSER),the solar-dedicated radio imaging observing instrument with total1OO antennas spreading over3 spiral-arms in about 10 square kilometers.A new digital array in lower frequency is under testing.Three big instruments including Meter to 1O-meter Waveband Radioheliograph,Interplanetary Scintilation telescope (IPS),and Super-wide Band Spectrograph in MeridianprojectI under National Infrastructure Program in China will be setup in 2O19-2O22. Observing data from all these radio telescopes will play important roles in solving the key problems of solar physics,space weather and solar activity prediction.The overall working frequency ranges from 1MHz to 15GHz. Allequipment has more than 3OO antennas, complicated structure and function,high rate data processng and mass memory.These put forward higher and stricter demands on protecting electromagnetic environment to reach EMC and from RFI contaminating. RFI mitigation is a systematical work.To distinguish weak and strong RFIs from solarradiation is also a big chalenge.Thecomplex electromagnetic environment,RFI spaceand spectrum distribution surveillance in double-circular polarizations are displayed and analyzed.Some anti-RFI measures and designs are introduced and discussed.RFI influences on observed data are related with many factors including the RFIsources’and the telescopes'.ARFI self-surveillance scheme using the radio telescope itself working together with omni antenna and reference antenna is proposed.

Key words: Solar physics; Space weather; Radioheliograph; Meridian project; RFI mitigation