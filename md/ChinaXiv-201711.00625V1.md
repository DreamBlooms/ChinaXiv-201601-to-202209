# 离心泵前置导叶的正交优化设计侯虎灿 张永学\* 李振林　周鑫 王子哲

（中国石油大学（北京）机械与储运工程学院，北京，102249）(Tel:010-89733146/18611131756，Email: zhyx@cup.edu.cn)

摘要：为研究前置导叶各设计参数对离心泵水力性能的影响，对一IS 系列离心泵运用二元理论自编程序完成其前置导叶的水力设计。应用 ${ \cal L } _ { 9 } ( 3 ^ { 4 } )$ 正交表，选取导叶轮毂半径 $\boldsymbol { r }$ ，长宽比 $R _ { \mathrm { l b } }$ ，安放角分布规律 $n$ 及出口边速度环量 $C _ { \mathrm { u } } r$ 为设计参数，对其进行4因素3水平正交设计并得到9组导叶。对加装导叶的离心泵进行全流道数值计算，以扬程和水力效率为考察目标并利用极差分析影响其水力性能的主次因素，得到最佳方案。对最佳方案下导叶进行加工并试验，结果表明：数值模拟与试验结果基本吻合,综合优化后相比于未加装导叶的离心泵，加装导叶时离心泵扬程变化不大，水力效率提高 $1 . 4 3 \%$ ，轴功率减少了 $0 . 8 3 \mathrm { k W }$ 总能耗节能约 $2 . 0 6 \%$ ，同时验证了正交优化方法的可行性及可靠性。

关键词：前置导叶；离心泵；正交优化；水力设计；数值模拟中图分类号：TH311 文献标识码：A

# Optimization Design of Inlet Guide Vane in a Centrifugal Pump Based or Orthogonal Method

HOU Hu-Can ZHANG Yong-XueLI Zhen-Lin ZHOU Xin WANG Zi-Zhe

Mechanical and Transportation Engineering, China University of Petroleum-Beijing,Beijing 102249, China)

Abstract: In order to study the influence of inlet guide vane (IGV） parameters on hydraulic performance of centrifugal pump,the hydraulic design of IGV was completed for one IS type centrifugal pump using in-house code based on two dimensional flow theory. The $L _ { 9 } ( 3 ^ { 4 } )$ orthogonal table was implemented to design nine type of IGVs, which contains four factors with three levels of hub radius $r$ , length-width ratio $R _ { \mathrm { l b } }$ ， setting angle distribution $n$ and velocity circulation $C _ { \mathrm { u } } r$ at outlet edge. The whole flow field of centrifugal pump with IGV was numerical simulated at three operating points,and regarding its head and hydraulic efficiency as the evaluation targets and aided by variance analysis,the primary and secondary factors of the researched parameters were acquired and obtained an optimal combination scheme.Then the hydraulic performance experiments for the optimal IGV were carried out and the results show that the numerical results agree well with experimental. Comparing with that without IGV,the head of centrifugal pump with IGV changes not much while the hydraulic efficiency increases obviously by $1 . 4 3 \%$ and the shaft power decrease by $0 . 8 3 \%$ ， saving the total of energy consumption about $2 . 0 6 \%$ ，which meanwhile verifies the feasibility and reliability of the orthogonal optimization method.

Key words: IGV； Centrifugal Pump; Orthogonal Optimization; Hydraulic Design； Numerical Simulation

# 0引言

离心泵广泛应用于各个技术领域，耗能总量巨大，对其进行节能研究有着重大的意义[1]。实际生产由于选型不当、水力设计不合理、实际生产运行条件已严重偏离设计工况要求等原因，多数离心泵在偏离工况运行，运行效率偏低，造成大量能源浪费。实践证明离心泵采用前置导叶预旋调节可有效改善叶轮进口流态，进而改善离心泵及其偏离工况的水力性能。桂绍波[2]对不同预旋角度时前置导叶离心泵进行全流道三维湍流数值模拟，得到的外特性结果与试验数据吻合较好。王海民[3]对不同翼型的前置导叶进行试验研究，表明适当的正预旋调节能够达到

离心泵增效节能的目的。

正交试验设计是研究多因素多水平的一种设计方法，根据正交性挑选试验点并具备“均匀分散，齐整可比”的特性，试验方法高效快速。正交试验法虽在泵设计中得到应用，但还未见前置导叶设计应用的发表成果。戎国平[4指出通过正交试验可以充分分析各因素对泵性能的影响规律并由最经济的途径得到最佳的结果。张金亚[5基于正交设计方法采用数值模拟手段对混输泵进行叶轮优化，使混输泵的水力性能得以明显提高。施卫东对高扬程深井离心泵进行正交试验优化设计，并用极差分析找到影响深井泵性能的主次因素，提出了较优设计方案。

笔者以型谱泵IS150-125-250为试验对象，基于二元流动理论，自编程序完成弯扭空间前置导叶的水力设计，依据正交性指导设计9套前置导叶叶片并全流道数值模拟了加装导叶的离心泵进，探索不同设计参数对泵整体水力性能的影响，提出最佳设计方案。随后加工最佳的前置导叶装置并进行水力性能试验，验证设计方法的可行性及结果的可靠性。

# 1前置导叶二元水力设计

轴面流动有势的二元水力设计方法流程如图1所示，首先确定导叶初始轴面流道轮廓；再运用准正交线法绘制轴面流网并进行轴面速度迭代计算[7];再采用逐点积分法进行叶片骨线绘型并沿周向对叶片骨线进行双面加厚；最后对导叶的进出口边进行多次贝塞尔曲线修圆处理，在Gambit软件构造得到其三维模型8如图2所示。设计中导叶出口边采用等环量设计，而进口边为减小的冲击损失，在设计流量下经预旋调节后的叶轮进口满足无冲击条件。

![](images/3587b9b2abb047a8f13abfdf97dd2b6303a82ecd92d1de004a92a94ff946fad1.jpg)  
图1前置导叶二元流动设计流程图Figl 2D theory design flow chart of inlet guide vane

![](images/cdfde07ba036b5da225ae338c7269a68ecacf6c1c0f5c0299c056f993f7c254e.jpg)

# 2正交设计方案的确定

离心泵前置导叶的正交水力设计优化目的是探求各设计参数对离心泵水力性能的影响。为使设计导叶与其调节的离心泵相匹配，得到的导叶基本设计参数为轮缘直径 $1 5 0 \mathrm { m m }$ ，设计流量 $Q _ { d } 2 0 0 \mathrm { m } ^ { 3 } / \mathrm { h }$ 叶片数6，进口安放角 $9 0 . 0 ^ { \circ }$ 及轴向距离 $2 0 0 \mathrm { m m }$ 。

前置导叶的主要几何结构设计参数有：轮毂半径 $\boldsymbol { r } ^ { \mathrm { ~ } } ( \boldsymbol { r } _ { 1 } )$ ，长宽比 $R _ { \mathrm { l b } } \ ( \mathrm { \it l / ( r _ { 2 } { - } } r _ { 1 } )$ )，叶片安放角沿轴面流线的四次分布规律 $n$ 及出口边的叶片涡 $C _ { \mathrm { u } } r$ 。导叶结构设计参数的选取是否合理直接影响其水力性能，合适的结构参数的选取能够在牺牲很小扬程的情况下改善离心泵偏离工况的水力性能。对每一设计因素取3个水平如表1所示，选用 ${ \cal L } _ { 9 } ( 3 ^ { 4 } )$ 正交表确定的正交试验方案如表2所示。

表1因素水平表Table 1 Orthogonal experiment factors  

<html><body><table><tr><td rowspan="3">水平</td><td colspan="4">因素</td></tr><tr><td>A</td><td>B</td><td>C</td><td>D</td></tr><tr><td>n</td><td>r/mm</td><td>R1b</td><td>Cur/m²/s</td></tr><tr><td>1</td><td>-1.5</td><td>10</td><td>0.8</td><td>0.1</td></tr><tr><td>2</td><td>-1.0</td><td>15</td><td>1.0</td><td>0.2</td></tr><tr><td>3</td><td>0</td><td>20</td><td>1.2</td><td>0.3</td></tr></table></body></html>

表2正交试验方案Table 2 Orthogonal scheme  

<html><body><table><tr><td rowspan="2">编号</td><td colspan="4">代号</td><td rowspan="2">编号</td><td colspan="4"></td></tr><tr><td>A</td><td></td><td></td><td>D</td><td>A</td><td></td><td>代号</td><td>D</td></tr><tr><td>1</td><td>A</td><td>B</td><td>C1</td><td>D1</td><td>6</td><td>A</td><td>B</td><td>C</td><td>D2</td></tr><tr><td>2</td><td>A1</td><td>B2</td><td>C</td><td>D2</td><td>7</td><td>A</td><td>B1</td><td>C</td><td>D2</td></tr><tr><td>3</td><td>A</td><td>B</td><td>C</td><td>D3</td><td>8</td><td>A</td><td>B2</td><td>C1</td><td>D</td></tr><tr><td>4</td><td>A</td><td>B1</td><td>C2</td><td>D</td><td>9</td><td>A</td><td>B</td><td>C2</td><td>D1</td></tr><tr><td>5</td><td>A</td><td>B</td><td>C</td><td>D1</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 3数值模拟与计算方法

在正交方案确定的基础上对每种方案下加装前置导叶的离心泵进行数值计算，并使用 AnsysMeshing进行离心泵网格划分如图3所示。

![](images/3268183a3eefd043db93d0de011e9ccd5834f5a46b79c6e3603a0f5eda8683f5.jpg)  
图2前置导叶三维结构模型 Fig2Geometry model of the designed inlet guide vane   
图3离心泵泵计算域及网格 Fig 3 The computational domains and meshing grid

利用Fluent软件进行全流道流场计算，选用$\operatorname { R N G } k - \varepsilon$ 湍流模型和标准壁面函数，采用MRF模型进行动静部件耦合，采用SIMPLEC算法对压力和速度进行耦合求解。使用PRESTO！格式对压力项进行离散，二阶迎风格式对对流项进行离散，其余各项均采用二阶中心差分格式。进口给定速度边界条件，出口为边界采用自由出流，固体壁面采用无滑移边界条件，动静交界面上采用Interface面进行内部数据传递。

离心泵扬程、轴功率及效率按下式计算：

$$
H = \Delta z + \frac { p _ { 2 } - p _ { 1 } } { \rho g } + \frac { \nu _ { 2 } ^ { 2 } - \nu _ { 1 } ^ { 2 } } { 2 g } P = \frac { 2 \pi n M } { 6 0 } \eta = \frac { \rho g Q H } { P }
$$

式中， $H$ 是扬程， $P$ 是轴功率， $\eta$ 效率， $\Delta z$ 是离心泵进出口位置的高程差； $p _ { I } , \ p _ { 2 }$ ， $\nu _ { I }$ ， $\mathbf { \sigma } _ { \nu _ { 2 } }$ 是离心泵（含进口导叶）进出口位置的静压值和速度值， $M$ 是扭矩值， $n$ 是转速， $\rho$ 是介质的密度。

# 4网格无关性验证

为减少计算负荷并确保计算精度，须对计算网格进行无关性验证如表3所示。无关性过程中选取的三个特征量分别是扬程 $H$ 、水力效率 $\eta _ { h }$ 及额定工况下叶轮进口截面处的平均叶片涡 $C _ { \mathrm { u } } r$ 。综合分析选取网格4作为后续模拟计算的网格数。

Table 3 Evaluation of the Independency of mesh   

<html><body><table><tr><td>Items</td><td>Total grid</td><td>H/H4</td><td>n/n4</td><td>Vur/Vur4</td></tr><tr><td>Mesh 1</td><td>1280144</td><td>0.9993</td><td>1.0008</td><td>0.9993</td></tr><tr><td>Mesh 2</td><td>1469397</td><td>1.0014</td><td>1.0017</td><td>0.9988</td></tr><tr><td>Mesh 3</td><td>1677027</td><td>1.0014</td><td>1.0014</td><td>0.9997</td></tr><tr><td>Mesh 4</td><td>1861551</td><td>1.0000</td><td>1.0000</td><td>1.0000</td></tr><tr><td>Mesh 5</td><td>2077358</td><td>0.9993</td><td>1.0000</td><td>1.0003</td></tr><tr><td>Mesh 6</td><td>2296194</td><td>0.9988</td><td>0.9982</td><td>1.0017</td></tr></table></body></html>

# 5正交设计结果分析

全流道数值计算都是在 $0 ^ { \circ }$ 预旋角下进行的，而$Q _ { d }$ 工况计算得到的9个设计方案的离心泵扬程和水力效率如表4所示。

表3网格无关性评估  
表4额定流量 $\mathcal { Q } _ { d }$ 下数值模拟结果  

<html><body><table><tr><td>编号</td><td>H/m</td><td>n/%</td><td>编号</td><td>H/m</td><td>nh/%</td></tr><tr><td>1</td><td>16.27</td><td>85.65</td><td>6</td><td>16.10</td><td>85.91</td></tr><tr><td>2</td><td>15.89</td><td>85.90</td><td>7</td><td>15.03</td><td>84.41</td></tr><tr><td>3</td><td>15.20</td><td>85.08</td><td>8</td><td>15.42</td><td>85.44</td></tr><tr><td>4</td><td>14.61</td><td>83.40</td><td>9</td><td>16.26</td><td>85.58</td></tr><tr><td>5</td><td>16.22</td><td>85.74</td><td></td><td></td><td></td></tr></table></body></html>

由表4可以看出扬程最高的是1号设计方案，$H { = } 1 6 . 2 7 ~ \mathrm { m }$ ，而水力效率最高的是6号设计方案， $\eta _ { h }$ $= 8 5 . 9 1 \%$ 。为分析各个设计参数对离心泵的性能，并找到主要因素和优化方案，对模拟结果进行极差分析如表5所示。表中 $K _ { \mathrm { i } }$ 为相应水平 $i$ 的模拟结果之和， $M _ { \mathrm { i } }$ 是相应 $i$ 水平结果的平均值， $R$ 为极差。为了直观起见，以因素的水平变化为横坐标，指标平均值为纵坐标的折线图如4所示。

由表5中极差分析可以看出，离心泵前置导叶的主要设计参数对离心泵整体水力性能的影响规律是不同的，各设计参数对 $H$ 影响的主次顺序为DBCA，对 $\eta _ { h }$ 影响的主次顺序为BDCA，可见在离心泵前置导叶的设计中应优先考虑导叶轮廓与导叶出口边的叶片涡。就单个因素而言，因素 $A$ ：对 $H$ 的影响顺序为 $A _ { 1 } A _ { 2 } A _ { 3 }$ ，对 $\eta _ { h }$ 的影响顺序为 $A _ { 1 } A _ { 3 } A _ { 2 }$ ；因素 $B$ ：对 $H$ 的影响顺序为 $B _ { 3 } B _ { 2 } B _ { 1 }$ ，对 $\eta _ { h }$ 的影响顺序为 $B _ { 2 } B _ { 3 } B _ { 1 }$ ；因素 $C$ ：对 $H$ 的影响顺序为 $C _ { 1 } C _ { 2 } C _ { 3 }$ ，对$\eta _ { h }$ 的影响顺序为 $C _ { 1 } C _ { 3 } C _ { 2 }$ ；因素 $D$ ：对 $H$ 的影响顺序为 $D _ { 1 } D _ { 2 } D _ { 3 }$ ，对 $\eta _ { h }$ 的影响顺序为 $D _ { 1 } D _ { 2 } D _ { 3 }$ 。综上分析，提高离心泵的水力效率的同时兼顾扬程得到的最佳组合为 $A _ { 1 } B _ { 2 } C _ { 1 } D _ { 1 }$ 。

![](images/437a46c8af297b8baab95f8e53d6bebe1f44b8ef4f05977d5abf54a46db34e99.jpg)  
图4水力效率、扬程与各因素关系图  
Fig 4Relationship between efficiency/head and parameter:

离心泵加装前置导叶预旋调节可有效改善其偏离工况的水力性能，笔者选取小流量工况 $0 . 8 Q _ { d }$ 和大流量工况 $1 . 2 Q _ { d }$ 进行数值计算得到其扬程和水力效率结果如表6所示，相应的极差分析如表7所示。

由表7中极差分析可以看出，在 $0 . 8 Q _ { d }$ 工况各设计参数对 $H$ 影响的主次顺序为 $D B C A$ ，对 $\eta _ { h }$ 影响的主次顺序为ABDC。综合单个因素的影响结果可得到提高离心泵的水力效率的同时兼顾扬程得到的最佳组合为 $A _ { 3 } B _ { 2 } C _ { 1 } D _ { 1 }$ 。在 $1 . 2 Q _ { d }$ 工况各设计参数对 $H$ 影响的主次顺序为 $D B C A$ ，对 $\eta _ { h }$ 影响的主次顺序为DBCA。综合单个因素的影响结果可得出 $1 . 2 Q _ { d }$ 工况各方案模拟数据到的最佳组合为 $A _ { 1 } B _ { 3 } C _ { 1 } D _ { 1 }$ 。综合分析3中正交试验结果可以得到的最佳组合为$A _ { 1 } B _ { 2 } C _ { 1 } D _ { 1 }$ ，即导叶安放角沿轴面流线的四次分布规律为-1.5，轮毂半径为 $1 5 \ \mathrm { m m }$ ，导叶的长宽比为0.8,导叶出口边的叶片量为 $0 . 1 \mathrm { m } ^ { 2 } / \mathrm { s }$ 。

# 6优化结果分析

基于正交优化设计的参数组合进行水力设计得到导叶几何模型，并数值计算得到相应预旋下离心泵的性能曲线。为验证正交设计结果的可靠性，注塑加工了一套 $0 ^ { \circ }$ 预旋角度的最佳导叶，并对加装最佳导叶时离心泵进行有关效率的外特性试验，试验系统流程及相应导叶管段如图5所示。未加装及加装优化设计导叶的离心泵水力试验及数值计算得到的性能曲线如图6、7所示。

Table 4 Numerical results under the design condition $\mathcal { Q } _ { d }$   
表5模拟结果极差分析Table5 Range analysis of the numerical results  

<html><body><table><tr><td>因素</td><td>A</td><td>B</td><td>C</td><td>D</td><td>因素</td><td>A</td><td>B</td><td>C</td><td>D</td></tr></table></body></html>

表6偏离工况下数值模拟结果  

<html><body><table><tr><td rowspan="7">H/m</td><td>K1</td><td>47.30</td><td>45.91</td><td>47.79</td><td>48.75</td><td rowspan="7"></td><td>K K</td><td>256.63</td><td>253.46</td><td>257.00</td><td>256.97</td></tr><tr><td>K</td><td>46.93</td><td>47.53</td><td>46.76</td><td>47.02</td><td></td><td>255.05</td><td>257.08</td><td>254.88</td><td>256.22</td></tr><tr><td>K</td><td>46.71</td><td>47.56</td><td>46.45</td><td>45.23</td><td>K</td><td>255.43</td><td>256.57</td><td>255.23</td><td>253.92</td></tr><tr><td>M</td><td>15.79</td><td>15.30</td><td>15.93</td><td>16.25</td><td>nn/% M</td><td>85.54</td><td>84.49</td><td>85.67</td><td>85.66</td></tr><tr><td>M2</td><td>15.64</td><td>15.84</td><td>15.59</td><td>15.67</td><td>M2</td><td>85.02</td><td>85.69</td><td>84.96</td><td>85.41</td></tr><tr><td>M3</td><td>15.57</td><td>15.85</td><td>15.48</td><td>15.08</td><td>M</td><td>85.14</td><td>85.52</td><td>85.08</td><td>84.64</td></tr><tr><td>R</td><td>0.22</td><td>0.55</td><td>0.45</td><td>1.17</td><td>R</td><td>0.52</td><td>1.20</td><td>0.71</td><td>1.02</td></tr></table></body></html>

Table 6 Numerical simulation results under the off-design condition   
表 $7 0 . 8 Q _ { d }$ 和 $1 . 2 Q _ { d }$ 工况下极差分析  

<html><body><table><tr><td rowspan="2">方案编号</td><td colspan="2">0.8Qd</td><td colspan="2">1.2Qd</td><td rowspan="2">方案编号</td><td colspan="2">0.8Qd</td><td colspan="2">1.2Qd</td></tr><tr><td>H/m</td><td>/%</td><td>H/m</td><td>n%</td><td>H/m</td><td>1/%</td><td>H/m</td><td>1%</td></tr><tr><td>1</td><td>16.92</td><td>81.86</td><td>13.64</td><td>79.94</td><td>6</td><td>16.81</td><td>82.17</td><td>13.23</td><td>79.26</td></tr><tr><td>2</td><td>16.84</td><td>82.80</td><td>12.91</td><td>78.81</td><td>7</td><td>16.43</td><td>82.52</td><td>11.95</td><td>75.73</td></tr><tr><td>3</td><td>16.40</td><td>82.84</td><td>11.97</td><td>76.45</td><td>8</td><td>16.52</td><td>82.73</td><td>12.25</td><td>77.10</td></tr><tr><td>4</td><td>16.24</td><td>81.28</td><td>10.88</td><td>72.15</td><td>9</td><td>16.98</td><td>82.55</td><td>13.68</td><td>79.91</td></tr><tr><td>5</td><td>16.86</td><td>82.11</td><td>13.51</td><td>79.70</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

Table 7 Range analysis under $\underline { { 0 . 8 Q _ { d } } }$ and 1.2 $\mathcal { Q } _ { d }$ condition   

<html><body><table><tr><td rowspan="2">因 素</td><td colspan="2">A</td><td colspan="2">B</td><td colspan="2"></td><td colspan="2">D</td><td rowspan="2">因</td><td colspan="2">A</td><td colspan="2">B</td><td colspan="2">C</td><td colspan="2">D</td></tr><tr><td>0.8</td><td>1.2</td><td>0.8</td><td>1.2</td><td>0.8</td><td>1.2</td><td>0.8</td><td>1.2</td><td>素 0.8</td><td>1.2</td><td>0.8</td><td>1.2</td><td>0.8</td><td>1.2</td><td>0.8</td><td>1.2</td></tr><tr><td rowspan="7">H</td><td>K 50.16</td><td>38.52</td><td></td><td>49.59</td><td>36.47 50.25</td><td>39.12</td><td>50.76</td><td>40.83</td><td></td><td>247.50</td><td>235.20</td><td>245.66</td><td>227.82</td><td>246.76</td><td>236.30</td><td>246.52</td><td>239.55</td></tr><tr><td>K2 49.91</td><td>37.62</td><td></td><td>50.22</td><td>38.67</td><td>50.06 37.47</td><td>50.08</td><td>38.09</td><td></td><td>245.56</td><td>231.11</td><td>247.64</td><td>235.61</td><td>246.63</td><td>230.87</td><td>247.49</td><td>233.80</td></tr><tr><td>K</td><td>49.93 37.88</td><td></td><td>50.19</td><td>38.88 49.69</td><td>37.43</td><td></td><td>49.16 35.10</td><td></td><td>247.80</td><td></td><td>232.74 247.56</td><td>235.62</td><td>247.47</td><td>231.88</td><td>246.85</td><td>225.70</td></tr><tr><td>M1 16.72</td><td>12.84</td><td></td><td>16.53</td><td>12.16</td><td>16.75 13.04</td><td>16.92</td><td>13.61</td><td>nh %</td><td>82.50</td><td>78.40</td><td>81.89</td><td>75.94</td><td>82.25</td><td>78.77</td><td>82.17</td><td>79.85</td></tr><tr><td>M2 16.64</td><td>12.54</td><td></td><td>16.74</td><td>12.89</td><td>16.69</td><td>12.49</td><td>16.69</td><td>12.70</td><td>81.85</td><td>77.04</td><td>82.55</td><td>78.54</td><td>82.21</td><td>76.96</td><td>82.50</td><td>77.93</td></tr><tr><td>M3 16.64</td><td>12.63</td><td></td><td>16.73</td><td>12.96</td><td>16.56</td><td>12.48</td><td>16.39 11.70</td><td></td><td>82.60</td><td>77.58</td><td>82.52</td><td>78.54</td><td>82.49</td><td>77.29</td><td>82.28</td><td>75.23</td></tr><tr><td>R 0.08</td><td>0.30</td><td></td><td>0.21</td><td>0.80</td><td>0.19</td><td>0.56</td><td>0.53 1.91</td><td></td><td>0.75</td><td>1.36</td><td>0.66</td><td>2.50</td><td>0.28</td><td>1.81</td><td>0.33</td><td>4.62</td></tr></table></body></html>

从图6可的随着流量的增加，加装导叶的离心泵的扬程-流量曲线比未加装导叶时陡峭，随着流量的增加，导叶预旋装置本身带来的水力损失变得明显，导致其扬程下降较快。

图中加装导叶的离心泵效率-流量曲线整体上高于未加装导叶时的效率-流量曲线，说明前置导叶的引入改善了离心泵内流场且使得其高效区拓宽。拟合结果显示，未加装导叶的离心泵的最优工况 $Q _ { \mathrm { o p } }$ 对应的流量为 $1 6 1 . 5 6 \mathrm { { m } } ^ { 3 } / \mathrm { { h } }$ ，效率为 $5 9 . 7 8 \%$ ，扬程为$1 6 . 7 2 \mathrm { ~ m ~ }$ 。同流量下加装导叶的离心泵比未加装导叶时效率提高了 $1 . 4 3 \%$ ，功耗降低了 $0 . 8 3 \mathrm { k W }$ ，节约$6 . 9 0 \%$ ，而扬程下降了 $4 . 8 4 \%$ ，所以总能耗节约$2 . 0 6 \%$ 。且在 $0 . 9 \mathrm { \sim } 1 . 1 Q _ { \mathrm { o p } }$ 范围内，整体效率都有提高且平均值为 $1 . 0 7 \%$ ，此时功率平均节约 $0 . 9 2 \mathrm { k W }$ ，平均功耗节约 $7 . 5 \%$ ，实现了离心泵增效节能的目的。

图7的数值结果显示，在 $Q _ { d }$ 时扬程与水力效率分别为 $1 6 . 1 9 \mathrm { ~ m ~ }$ 与 $8 6 . 9 0 \%$ ，与正交设计9种方案计算结果相比，扬程下降不明显，而水力效率提高近一个百分点。在 $0 . 8 Q _ { d }$ 工况时，其扬程与水力效率分别为 $1 7 . 0 2 \mathrm { m }$ 与 $8 3 . 4 6 \%$ ， $1 . 2 Q _ { d }$ 工况时，其扬程与水力效率分别为 $1 3 . 5 1 \mathrm { ~ m ~ }$ 与 $80 . 7 4 \%$ ，与正交设计9种方案的结果相比均比较理想，验证了正交设计方法的可行性，运用正交设计方法成功的实现了离心泵前置导叶的优化设计。

![](images/82d455bd0e3a78ce7a186bfa6a60e3f2ca52b0520baca0e3ef7a1d4bf560e06a.jpg)  
图5试验系统流程与导叶

![](images/b5d4698691ac3c501db7eb2d9c97e392b74698c6a59f3e9a9f03d246346fc9fb.jpg)  
Fig 5Experimental system flowchart and IGV   
图6离心泵试验性能曲线  
Fig 6 Experimental performance curves of the centrifugal pump without and with IGV

同时容易得到加装导叶的离心泵其扬程-流量曲线较未加装导叶偏低，扬程值平均减少约 $0 . 6 \mathrm { m }$ ；效率-流量曲线在额定流量附近明显偏高，说明前置导叶的引入改善了离心泵的内流场且高效区拓宽。拟合数据显示，在额定工况点离心泵水力效率提高了$1 . 3 5 \%$ ，在 $0 . 8 { \sim } 1 . 2 Q _ { d }$ 流量工况范围内，水力效率平均提高 $1 . 3 2 \%$ ，与试验结果吻合较好，说明了数值模拟方法的可靠性，同时也验证了本文正交水力设计方法的正确性，可见本次正交设计是成功的，达到了预期的目的。

![](images/aba91d03f319d8278a81891e5b0ca9c348897d8a891969e419068d290e273c54.jpg)  
图7离心泵数值性能曲线

Fig 7 Numerical performance curves of the centrifugal pump without andwithIGV

# 7结论

(1）正交试验设计方法可以成功用于离心泵前置导叶的优化设计中并借助于全流道数值计算得到最佳方案组合 $A _ { 1 } B _ { 2 } C _ { 1 } D _ { 1 }$ ，极差详细得到前置导叶轮毂半径与出口边速度环量对设计结果的影响较大。(2）数值计算与水力试验结果基本吻合，说明了数值计算结果的可靠性，同时验证了正交水力设计方法在离心泵前置导叶上的成功应用。(3）相比于未加装导叶的离心泵，加装时扬程变化不大，最优工况下的水力效率提高明显 $1 . 4 3 \%$ ，总能耗节约 $2 . 0 6 \%$ ，实现了离心泵增效节能的目的。

# 参考文献

[1] 袁建平，张改成，陈翔．离心泵运行调节能耗分析[J].排灌机械，2006,24(5)：44\~47.Yuan Jianping， Zhang Gaicheng， Chen Xiang. Operationadjusting methods for energy consumption of centrifugalpump [J].Drainage and Irrigation Machinery,20o6,24(5):  
44\~47. (in Chinese)[2]桂绍波，曹树良，谭磊，等.前置导叶预旋调节离心泵性能的数值预测与试验[J].农业机械学报，2009，  
40(12):101\~106.GuiShaobo,Cao Shuliang,Tanlei,et al.Numerical Simulationand Experiment of Inlet Guide Vane Pre-whirl Regulationfor Centrifugal Pump [J].Transactions of the ChineseSociety forAgricultural Machinery， 2009, 40(12):  
101\~106.[3]王海民，周裁民，黄雄，等.不同翼型前置导叶正预旋对离心泵性能影响[J].农业机械学报，2012，43(11)：  
129\~133.Experiment oI iniet Guiae vane Ior Centriiugal PumpBased on Gottingen Airfoil[J]. Transactions of the ChineseSociety for Agricultural Machinery,2012,43(11): 129\~133.  
[4] 戎国平.正交试验设计及其在泵研究中的应用[J].排灌机  
械，1995，13(1):27\~30.  
RongGuoping.Orthogonal experimental designanditsapplication in pump research [J]. Drainage and IrrigationMachinery,1995,31(1): 27\~30.  
[5] 张金亚，朱宏武，李艳，等.基于正交设计方法的混输泵叶轮优化设计[J].中国石油大学学报：自然科学版,2009,33(6): 105\~110.  
Zhang Jinya, Zhu Hongwu, Li Yan, et al. Optimization design ofmultiphase pump impeller based on orthogonal designmethod [J]. Journal of China University of Petroleum:Edition of Natural Science,2009,33(6): 105\~110.  
[6] 施卫东，周岭，陆伟刚，等.高扬程深井离心泵的正交试验与优化设计[J].江苏大学学报：自然科学版，2011,32(4): 400\~404.  
Shi Weidong, Zhou Ling,Lu Weigang, et al. Orthogonal test andoptimization design of high-head deep-well centrifugalpump [J]. Journal of Jiangsu University: Natural ScienceEdition,2011,32(4): 400\~404.  
[7] 张永学，周鑫，姬忠礼，等．低比转速离心泵的水力设计及性能预测[J]．排灌机械工程学报，2013,31（4)：300\~304.  
Zhang Yongxue,Zhou Xin, Ji Zhongli, et al. Hydraulic designand performance analysis of low specific speed centrifugalpump [J]. Journal of Dranage and Irrigation on MachineryEngineeringt，2013，31（4)：300\~304.  
[8] 周鑫，张永学，姬忠礼，等．低比转速离心泵叶轮的水力设计数值方法[J]．中国石油大学学报（自然科学版)，2011,35 (4): 113\~118.  
ZHOU Xin, ZHANG Yong-xue,JI Zhong-li, et al.Hydraulicdesign of low specific speed centrifugal pump impeller bynumerical method [J]. Journal of China University ofPetroleum，2011，35（4)：113\~118.