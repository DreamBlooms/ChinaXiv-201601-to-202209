# 有机工质离心透平设计与变工况性能研究

宋艳苹1,2 谭鑫1,2 黄典贵1,2

(1.上海理工大学能源与动力工程学院，上海200093;2．上海市动力工程多相流动与传热重点实验室，上海200093)

摘要本文以R123为流动工质，进行离心透平级的一维热力计算，并通过数值模拟分析ORC 离心透平级内流动情况及变工况性能。结果表明：在设计工况下，数值模拟结果与一维设计结果基本一致，功率与效率偏差在 $1 \%$ 以内，符合设计要求。在变工况下，进汽压力在 $0 . 3 3 { \sim } 0 . 8 8 \ \mathrm { M P a }$ 变化时，效率随进汽压力增大先增大后减小，流量和功率随进汽压力增大而增大；背压在 $0 . 1 0 { \sim } 0 . 1 8 ~ \mathrm { M P a }$ 变化，在临界工况下运行，效率和功率随着背压的增大而减小，流量保持不变；初温改变对透平性能影响较小，效率变化范围在 $1 \%$ 以内；转速变化时，流量不变，效率先增大后减小，设计转速下效率最高。

关键词离心透平；数值模拟；变工况

中图分类号：TK14 文献标识码：A 文章编号:0253-231X(2017)08-1665-06

# Design and Research on Off-Design Characteristics of Centrifugal Turbine for ORC

SONG Yan-Ping $^ { 1 , 2 }$ （204 TAN Xin $^ { 1 , 2 }$ （20 HUANG Dian-Gui $^ { 1 , 2 }$ （204号 .SchoolofEnergyandPowerEngineering,Universityof Shanghai for ScienceandTechnology，Shanghai 20o93,China; 2.Shanghai key laboratory of multiphase flowand heat transferof power enginering，Shanghai 2093,China)

AbstractIn this paper, the one-dimensional design of the centrifugal turbine was conducted by using R123 as working fluid. Combining with CFD technology, the aerodynamic performance analysis of the centrifugal turbine stage was carried out both in design and off-design conditions. The results show: in the design condition,the CFD results mostly agree with the one-dimensional design; relative errors of power and efficiency are within 1%,efficiency and power of the turbine satisfy the design requirements.In the of-design conditions，when the inlet pressure increased from 0.33 MPa to 0.88 MPa,the efficiency increased at first,then decreased; massflow and power increased with the increasing of the inlet pressure.When the back pressure increased from O.10 MPa to 0.18 MPa which is smaller than the critical back pressure, effciency and power decrease with the increasing of the back pressure,mass flow maintains constant. The variation of inlet temperature showed less effect on stage performance, the variation of efficiency is within $1 \%$ .When the rotor speed varies,efficiency increases with the increasing of the rotor speed,reaches a maximum value at design speed,and then decreases with any further increase in rotor speed, massfow maintains constant. Key wordscentrifugal turbine; numerical simulation; off-design

# 0前言

在我国，工业余热、太阳热能、地热能等低品位热源蕴藏量大，分布广，低品位热源科学利用对能源开发具有重大的意义。但由于常用的工质水蒸气和理想气体等沸点较高，低温热源进行热功转换效率低。近年来，由于有机工质低沸点的特性，有机朗肯循环（ORC）成为低温热源利用研究的热点。

透平是ORC热功转换的关键设备，是系统安全高效运行的保证。有机工质分子量大，沸点低，体积变化大，声速小等不同于理想气体的特殊热物性，使透平内流动也更为复杂，因此关于ORC透平的研究显得愈加重要。刘广彬[1采用R123作为循环工质，以涡旋膨胀机作为能量回收机械，建立了小型低温余热发电试验系统，分析了相同热源不同流量的两种工况下，膨胀机转速对系统性能的影响。Wang

W，Wu Y T[2,3]研究单螺杆膨胀机用于余热回收发电，最低可利用余热温度可低至 $8 0 ^ { \circ } \mathrm { C }$ 。薄泽民[4]设计了 $1 5 0 ~ \mathrm { k W }$ 向心透平，采用NUMECA软件进行数值模拟，并分析了其变工况性能。李艳[5.6]设计了高膨胀比有机工质向心透平，进行了数值模拟和实验。意大利米兰理工大学的G.Persico，M.pini等[7]研究了离心透平流动规律及应用范围，对离心透平叶栅的气动性能进行了数值模拟研究。

本课题组李银各[8以完全气体为工质，研究了一维级效率的影响因素，为离心透平的设计提供了依据。谭鑫[9]对以完全气体为工质的离心透平进行了气动设计和优化，并采用数值模拟方法，对所设计的离心透平级进行设计工况及变工况三维稳态流场分析。黄典贵、谭鑫[10]设计了一种新型的离心透平，结构如图1所示。气流从内部环形径向进汽，膨胀做功后沿外径径向流出，通流截面沿着流向膨胀过程逐渐增大。

征，借鉴轴流和向心透平气动设计方法[11,12]，建立流动损失模型，以轮周效率最大为目标，热物性参数从实际气体物性软件REFPROP9.0调用，编写一维热力设计程序。本文以某太阳能热源有机朗肯循环向心透平热力参数见表1，以R123为流动工质，根据编制的一维热力计算程序，设计离心透平，以轮周效率最大为目标，采用筛选法，确定设计几何参数。如表2所示。

Table 1 The parameters of the centrifugal turbine   
表2离心透平的主要几何参数  

<html><body><table><tr><td>热力参数</td><td>设计值</td></tr><tr><td>进口总温To/K</td><td>373.23</td></tr><tr><td>进口总压P/MPa</td><td>0.78564</td></tr><tr><td>出口背压P2/MPa</td><td>0.11</td></tr><tr><td>设计转速n/r·min-1</td><td>10000</td></tr><tr><td>质量流量G/kg·s-1</td><td>12.4</td></tr><tr><td>透平功率W/kW</td><td>300</td></tr><tr><td>轮周效率/%</td><td>84</td></tr></table></body></html>

量 m

表1离心透平热力参数  
Table 2 The centrifugal turbine geometry   

<html><body><table><tr><td>热力参数</td><td>设计值</td></tr><tr><td>静叶入口直径Di/mm</td><td>278</td></tr><tr><td>静叶出口直径D2/mm</td><td>310</td></tr><tr><td>动叶入口直径D3/mm</td><td>314</td></tr><tr><td>动叶出口直径D4/mm</td><td>346</td></tr><tr><td>叶高H/mm</td><td>21.7</td></tr><tr><td>进口气流角α/()</td><td>12</td></tr></table></body></html>

# 2离心透平的数值模拟

有机朗肯循环采用该离心透平与传统的向心透平相比有两点优势：1、有机工质在膨胀时，相对于理想气体比容变化大(该设计几何与气动相匹配，叶高变化小)；2、有机工质分子量大，声速低，容易形成超音速流动，引起激波和气流偏转。而离心透平可采用多级设计，各级焓降合理分配，避免在马赫数过高的工况下运行。同时多级可利用余速和重热，提高整机热效率。本文以R123作为流动工质，对大膨胀比离心透平进行气动设计，并数值模拟研究其流动特性及变工况性能。

# 1离心透平气动设计

根据ORC离心透平的工质特性和透平流动特

根据离心透平的一维热力设计参数，采用Ansys-Workbench工作平台系列软件，分别对动静叶进行叶型初步造型设计、叶型参数化、叶栅流道网格划分、数值模拟计算，在初步模拟的结果基础上采用梯度算法对叶型进行优化，循环数值模拟计算之至功率与效率达到设计要求，然后进行变工况性能分析。具体流程如图2所示。

# 2.1 叶片造型

离心透平通流截面和工质比容沿流向方向同时增大，因此叶片可采用等叶高直叶片，但由于环列叶栅流道是渐扩的，叶型无法采用传统的轴流叶型，设计满足离心透平特性的气动翼型是一个重要的工作。本文在 Ansys 软件中 BladeGen 模块中设计叶型。以静叶为例予以简要说明：叶片为等叶高直叶片，根据表2确定叶片的进口径向位置与叶高确定叶型子午面。叶片截面由前缘、尾缘、叶盆和叶背四条曲线组成，前缘和后缘采用圆弧，叶背、叶盆则由中弧线叠加厚度的方法来构造。如图3所示，中弧线是采用3次Bezier曲线来表示，四个点代表不同径向位置的中弧线与切向的夹角，横坐标代表的是径向相对位置，纵坐标表示相应的几何角，通过改变中间2个控制点的坐标可改变中弧线形状。沿中弧线的厚度分布也采用3次Bezier曲线来表达，如图4所示，前缘和尾缘厚度为圆弧直径，经过经验值确定，通过改变中间2个控制点的坐标来得到中弧线不同径向相对位置的厚度值。最终由样条曲线光滑连接生成叶盆、叶背曲线。同理生成动叶叶型，图5所示为动静叶三维几何结构图。

![](images/c42ec6986eba6f4f271cd6e87124511a2e22aa0c8165a890439da00895a644f7.jpg)  
图2离心透平的叶型设计和优化流程图Fig.2 Numerical simulation of centrifugal turbine

![](images/acb692b45f629d81c50bb002d31c00a936fda54f4a84627c47a73c51626855a8.jpg)  
图3中弧线切线角分布  
Fig.3 Mean line tangential angular distribution of radial chord

# 2.2网格划分与边界条件的设置

根据叶栅的流动特性，在数值模拟时选取单个流道为研究对象简化计算，周期性边界条件，近壁面为无滑移固体壁面，网格采用ANSYS-TurboGrid生成结构网格。湍流模型选择 $k { - } \varepsilon$ 双方程模型，标准壁面函数。工质物性选用实际气体立方型S-R-K状态方程计算，进口边界条件给定总温和总压，出口边界给定静压，设计转速为 $1 0 0 0 0 ~ \mathrm { r / m i n }$ 。

![](images/a3f54b79fe02be7041fa0107d70a22a0fc6477f52d59de98d1a7726aef89a750.jpg)  
图4叶片厚度分布

![](images/d8a03e38136f8734fe506e6f5f2fb0c3afe75bc5ea4a4b8d808fff677df5b9ff.jpg)  
Fig.4 Thickness distribution of radial chord   
图5叶片几何模型  
Fig.5 3-D model of stator and rotor

# 2.3数值模拟结果

根据数值模拟结果是否达到设计效率及功率，采用梯度优化算法，通过调整叶片的中弧线切线角和叶片厚度沿径向分布，优化叶型，数值模拟重复计算直至达到设计要求。

表3给出了所设计的离心透平一维设计与CFD数值模拟的结果，在设计工况下，热力计算和数值模拟结果误差在 $1 \%$ 以内，功率和效率达到设计要求，符合预期。

表3设计值与模拟结果误差表  
Table 3 The contrast of design value and CFD value   

<html><body><table><tr><td>变量</td><td>设计值</td><td>模拟值</td></tr><tr><td>G/kg·s-1</td><td>12.4</td><td>12.55</td></tr><tr><td>W/kW</td><td>344</td><td>343</td></tr><tr><td></td><td>0.6</td><td>0.62</td></tr><tr><td>Xa</td><td>0.63</td><td>0.6</td></tr><tr><td>n/%</td><td>84</td><td>83</td></tr></table></body></html>

图5所示，级的动静叶片均为等叶高直叶片，因此在展向上流动特征相同。采用在展向位置流动特征相同。图 $6 { \sim } 8$ 分别为展向为 $5 0 \%$ 叶高处的流线图和涡黏性、压力云图。

![](images/5f4bbb0cf01af3d093560c788ace30924dd327cc725dd2c890dee593a33760e5.jpg)  
图6叶高 $5 0 \%$ 处流线分布图

Eddy Viscosity 3.9e-003 3.6e-003 3.3e-003 2.9e-003 2.6e-003 2.3e-003 2.0e-003 D 1.6e-003 1.3e-003 9.8e-004 6.6e-004 3.3e-004 2.0e-004   
Pa-s

缩放形式，在动叶内为超音速流动。图7为涡黏性云图，在静叶出口涡黏性有少许增大。图8为压力云图，在整个流道内顺压流动。

# 3变工况性能预测

# 3.1进汽压力变化对性能的影响 (背压不变)

透平热源的变化会引起蒸发压力变化，当进汽压力增大时，膨胀比增大，级的焓降增大。在设计转速和背压下，研究进汽压力变化对级的性能的影响，进汽压力 $0 . 3 3 { \sim } 0 . 8 8 ~ \mathrm { M P a }$ ，间隔选取 $0 . 1 1 \ \mathrm { M P a }$ 。效率、流量及功率随进气压力变化规律如图9、10所示，进汽压力增大理想焓降增大，效率随进汽压力增大先增大后减小，进汽压力为 $0 . 6 6 ~ \mathrm { M P a }$ ，即焓降$3 0 \ \mathrm { k J / k g }$ 时效率最高。在进汽压力变化时，喷嘴达到临界工况，流量随着进汽压力增大线性增大，输出功率随着进汽压力压增大而增大。

![](images/e183236bf4b36917bbe47ea6e4b2dd54f5cb6d877852594a9dfa052309417789.jpg)  
Fig.6 The streamline distribution at $5 0 \%$ span   
图9效率随进汽压力的变化曲线 Fig.9 Efficiency of vs.inlet pressure

![](images/4ac5ee0fb9ec0e50b926e30ef2c3596b1cfe532fd3899383412e69ea338bbed7.jpg)  
图7叶高 $5 0 \%$ 涡黏性云图  
Fig.7 The Eddy Viscosity distribution at $5 0 \%$ span   
图8叶高 $5 0 \%$ 压力云图  
Fig.8 The pressure distribution at $5 0 \%$ span

图6为叶栅 $5 0 \%$ 叶高处的流线图，由图可知，流道通畅，在静叶尾缘有流动尾迹，但没有流动分离产生。因透平设计压比在0.14，整级焓降较大，动叶为

# 3.2进汽温度变化对性能的影响(进汽压力、背压 均不变)

热源的温度变化会引起进汽温度发生变化，当进汽温度发生变化时，级的焓降、效率、轴功也会相应发生变化。进汽压力为设计压力，当进汽温度从$3 7 3 \mathrm { ~ K ~ }$ 增加到408K时，间隔选取5K，工质由饱和进汽逐渐到过热的过程，研究进汽温度变化对透平性能的影响。结果如图11、12所示，

随着进汽温度的增加，效率逐渐下降，但是变化小于 $1 \%$ 。随着进汽温度增加，级理想焓降增大，在进汽压力和背压不变的情况，比容增大，质量流量减小，但由于焓降增大，效率基本不变，输出总功率仍然增大。因此可认为，离心透平与轴流和向心透平热力特性相同，进汽温度变化对运行经济性影响较小。

![](images/62054d7d0f26bd70746b3001728d45e91dcd43a0446f5ee05888f275f3c14089.jpg)  
图10功率和流量随进汽压力变化曲线

![](images/3fc7546df4ad576af03fcf540551174d90ed08f8346e6779225d20318ec89421.jpg)  
Fig.1O Output power and mass flow rate of inlet pressure

![](images/49ec2804e04056fc4c5f1adabf1b6c06734da3d204c0ef3e860129d641810a01.jpg)  
图11效率随进汽温度的变化曲线 Fig.11 Efficiency of vs.inlet temperature   
图12功率与流量随进汽温度的变化曲线 Fig.12Output power and mass flow rate of vs. inlet temperature

# 3.3背压变化对性能的影响 (进汽温度、压力不变)

透平出口背压为冷凝温度对应的饱和压力。当环境水温随季节发生变化、循环水泵的变工况运行等均会引起冷凝温度发生改变，进而使透平出口背压偏离设计值。原设计背压 $0 . 1 1 \mathrm { M P a }$ 对应的冷凝温度为 $3 0 ^ { \circ } \mathrm { C }$ 。当冷凝温度从 $2 7 ^ { \circ } \mathrm { C }$ 到 $4 5 ^ { \circ } \mathrm { C }$ 变化时，背压从 $0 . 1 0 1 2 3 5 \mathrm { M P a }$ 升高到 $\mathrm { 0 . 1 8 2 2 M P a }$ ，背压变化对透平性能的影响如图13、14所示，效率随着背压升高先增大后减小，在背压为 $0 . 1 3 4 ~ \mathrm { M P a }$ (冷凝温度为

$3 5 ^ { \circ } \mathrm { C } )$ ）时，即焓降为 $3 0 \mathrm { k J / k g }$ 时，效率最高。由于在该背压变化范围内，均在临界工况下运行，所以流量保持不变，但随着冷凝温度的升高，背压升高，理想焓降减小，输出总功率减小。

![](images/9f8067602afe10773309a1555d80596f122c98dffa8537d773e50ef49f0d493b.jpg)  
图13效率随背压的变化曲线Fig.13 Efficiency of vs.exhaust back pressure

![](images/6896108f232b423f057b080afb8f2efc16ac6e056f86cb25368f988de93b2152.jpg)  
图14功率与流量随背压的变化曲线 Fig.14 Output power and mass flow rate of vs.exhaust back pressure

![](images/b433c56e1b5acc9648607b7422999c990ebbdf033158e0c3e14eff9d3a4f42fa.jpg)  
图15效率随转速的变化曲线 Fig.15 Efficiency ofvs.rotation speed

# 3.4转速的变化对性能的影响 (设计参数)

在透平运行时，会发生转速偏离设计转速的工况，因此透平要求在一定转速波动范围内，维持良好的性能。在设计热力参数下，对转速在 $6 0 0 0 { \sim } 1 5 0 0 0$ $\mathrm { { r / m i n } }$ 范围内变化进行了数值模拟，效率随着转速变化先增大后减小，在设计转速变动 $2 5 \%$ 的变动范围内，效率均在 $8 0 \%$ 以上，规律如图15、16所示。在热力参数保持不变，转速改变，质量流量保持不变,输出总功率随着效率先增大后减小。

![](images/4cd9bb7bce6b69584cad3c8a58feb6bfe6cf391d93eb4d2d2bd612263dbdf346.jpg)  
图16功率与流量随转速的变化曲线 Fig.l6 Output power and mass flow rate of vs.rotation speed

# 4结论

本文以有机工质R123为流动工质，借鉴轴流透平气动设计方法，设计了应用于低温热源利用的离心透平，用商业通用软件CFX对所设计的离心透平整级性能进行数值模拟和变工况性能研究。

研究表明：

1)在设计工况下，流道通畅，顺压流动，无流动分离，效率和功率达到设计要求。

2)在变工况条件下，当进汽压力增大，焓降随之增大时，效率先增大后减小，膨胀比在 $5 { \sim } 6$ 之间，也即焓降在 $3 0 \mathrm { k J / k g }$ 左右,效率最高。随着进汽压力增大，流量增大，输出功率增大；冷凝温度在 $2 7 { \sim } 4 5 ^ { \circ } \mathrm { C }$ 范围变化时，也即背压在 $0 . 1 0 { \sim } 0 . 1 8 \mathrm { M P a }$ 变化时，级在临界工况下工作，随着背压增大，流量不变，效率先增大后减小，效率仍在焓降为 $3 0 \mathrm { k J / k g }$ 时为最佳,输出功率随着背压的增大而减小。

3)进汽温度改变对气动性能的影响较小，效率变化范围在 $1 \%$ 之内，功率随着进汽温度的增大而增加；转速改变时，在设计点效率最高，转速改变对流量没有影响。

# 参考文献

[1]刘广彬，赵远扬，李连生，等.小型低温余热发电系统膨胀机输出特性试验研究[J].西安交通大学学报,2009,43(11):100-103LIUGuangbin,ZHAO Yuanyang,LILiansheng,et al.Ex-

permment on Outpu anuer Small Power Generation System With Low-temperature Waste Heat [J]. Journal of Xi'an JiaoTong University, 2009,43(11):100-103 [2] Wang W,Wu Y T,Ma C F,et al.Preliminary Experimental Study of Single Screw Expander Prototype [J]. Applied Thermal Engineering,2011,31(17): 3684-3688 [3] He W,Wu Y T,Peng Y H,et al.Influence of Intake Pressure on the Performance of Single Screw Expander Working with Compressed Air [J].Applied Thermal Engineering,2013,51(1/2):662-669 [4]薄泽民.有机物工质发电系统向心透平性能研究[D].上海： 上海交通大学，2014 BO Zemin.Performance Analysis of Radial Turbine for Organic Rankine Cycle Power System [D]. Shanghai: Shanghai Jiao Tong University, 2014   
[5]李艳,连红奎，顾春伟．有机朗肯循环系统及其透平设计研 究[J].工程热物理学报,2010,31(12):2014-2018 LI Yan,LIAN Hongkui, GU Chunwei. Design and Study of Organic Rankine Cycle (ORC)and Turbine for ORC [J].Journal of Engineering Thermophysics,2010,31(12): 2014-2018 [6] 李艳，顾春伟．高膨胀比有机工质向心透平气动优化研究 [J].工程热物理学报,2013,34(7)：1239-1242 LI Yan,GU Chunwei.Aerodynamic Optimization Study for a Radial-Inflow Organic Turbine with High Expansion Ratio [J]. Journal of Engineering Thermophysics,2013, 34(7):1239-1242 [7] Persico G,Pini M, Dossena V,et al.Aerodynamic Design and Analysis of Centrifugal Turbine Cascades [C]//ASME Turbo Expo 2013: Turbine Technical Conference and Exposition.American Society of Mechanical Engineers, 2013:V06CT40A019   
[8] 李银各，谭鑫，林显巧，等．离心式透平的热力设计与分析 [J].工程热物理学报，2015,36(10)：2103-2109 LI Yinge, TAN Xin, LIN Xianqiao,et al. Thermal Design and Analysis of the Centrifugal Turbine [J]. Journal of Engineering Thermophysics,2015,36(10):2103-2109 [9]谭鑫，李银各，林显巧，等.离心式透平的变工况特性研究 [J].工程热物理学报，2016,37(6):1201-1207 TAN Xin, LI Yinge, LIN Xianqiao, et al. Research on OffDesign Characteristic of Centrifugal Turbine [J]. Journal of Engineering Thermophysics,2016,37(6):1201-1207.   
10]黄典贵，谭鑫，李银各．径向离心透平，中国，CN104863 643A [P]. 2015-08-26 HUANG Diangui, TAN Xin,LI Yinge,The Centrifugal Turbine. China, CN104863643A [P]. 2015-08-26   
11]舒士甄．叶轮机械原理[M].北京：清华大学出版社，1991: 172-175 SHU ShiZhen.Turbomachinery Principle [M]. Beijing: Tsinghua University Press,1991:172-175   
12]岳松,张奥,张燕平,等.中高温太阳能有机朗肯循环系统向 心透平气动设计研究[J].机械工程学报,2015,51(4)：155- 160 YUE Song, ZHANG Ao, ZHANG Yanping, et al. Aerodynamic Design Study of Radial Inflow Turbine Used in Middle-high Temperature Solar Organic Rankine Cycle System [J]. Journal of Mechanical Engineering 2015, 51(4): 155-160