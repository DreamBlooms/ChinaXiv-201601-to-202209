# 利用穷举搜索法准确确定地下热物性参数

吴迪1于明志1,2

(1．山东建筑大学热能工程学院，济南250101;2．可再生能源建筑利用技术教育部重点实验室，济南250101)

摘要利用穷举搜索法结合参数估计方法确定地下岩土热物性参数，通过模拟验证该方法的可靠性，并用于实际工程测量，且与优化方法计算结果进行对比分析。结果表明穷举搜索法可以在搜索区域得到目标函数方差和最小值，基于此得到热物性参数值可靠性较高；而优化方法得到的目标函数方差和为局部区域的极小值，其确定的土壤导热系数可靠性较高，但钻孔内热阻和容积比热计算结果可信度相对较低。

关键词岩土；热物性参数；测量；穷举搜索法中图分类号：TU831 文献标识码：A 文章编号:0253-231X(2017)04-0822-06

# Exhaustive Search Method to Measure the Grouhd Thermal Parameters With High Credibility

WU Di1 YUWZhi1.2 (1.School of Thermal Engineering,Shandong Jianzhu University，Jinan 250lo1,China; 2.Key Laboratoryof Renewable EnergyUtilization Tehgyin Building,Ministryof Education，Jinan 250lo1,China)

Abstract Combine with the parameteréStimation method,the exhaustive search method is used to measure the ground thermal prQperties,which reliability is verified by simulation.The exhaustive 小   
search method is applied for pr@jects,and the ground thermal parameters calculated are compared with those obtained by theptimization method. The result and analysis demonstrate that the exhaustive search method can find the minimum objective function variance within the search domain and obtain soil thermal parameters with high credibility. As comparison,though the optimization method can also find the minimum objective function variance and obtain the ground thermal conductivity with high credibility, the borehole thermal resisfance and volumetric heat capacity determined by it have relative lower credibility. 5

Key wordsground; thermal parameters; measure; exhaustive search method

# 0引言

地源热泵地热换热器[1]利用泵功使循环水在地埋管中循环流动，把地下浅层土壤作为热源，利用其温度随季节变化浮动较小的特点，将循环水作为载热流体可在冬季从其提取热量、夏季从其提取冷量供给用户[2]。地源热泵地埋管的换热能力与土壤的热物性参数有着直接关系，Kavanaugh的研究显示[3]，当地下土壤的导热系数或热扩散率发生 $1 0 \%$ 的偏差时，地下埋管设计长度偏差为 $4 . 5 \% { \sim } 5 . 8 \%$ 从而影响初投资。因此准确确定土壤热物性参数是合理设计埋管孔深和个数的前提[4-5]。

目前，恒热流测试法[6是国际上普遍采用的获取地下土壤热物性参数值的方法，利用该方法结合建立的地埋管与周围土壤传热模型，确定地下土壤的导热系数、容积比热容等热物性参数[7]。常用的传热模型有线热源模型[8、空心柱热源模型[9]、实心柱热源模型[10]等，计算土壤热物性参数值通常采用斜率法[11]和参数估计法[12]。斜率法可以方便地得到土壤导热系数，但不能确定容积比热容[13]；参数估计法可以同时确定导热系数、容积比热以及钻孔内热阻数值，在工程计算中被广泛应用[14-15]。参数估计法通常是利用模型计算得到循环水温度并将其与实验测量结果对比，寻找不同热物性参数组合值条件下两者之间的方差和最小值，方差和取得最小值时所对应的土壤热物性数值即认为是测试得到的准确热物性参数值。

利用传热模型公式结合参数估计法求解热物性参数的过程实际上是求解多元非线性方程的过程，许多数学家致力于利用优化方法更迅速地找到符合要求的解，常用的传统方法主要有牛顿法、弦割法、抛物线法等，但这类方法需要假定初始参数值，且最终结果受初始参数值选定的影响很大。遗传算法、蚁群算法等避免了结果对初始值的强烈依赖性，虽然寻优速度较快，但并未实现真正意义上的全局范围内的搜索，所以很可能将某局部区域的极小值作为全局范围内的最小值输出[16]。本文尝试采用穷举搜索法[17]，在土壤热物性参数值可能的范围内寻找目标函数最小值，实现全局范围内的搜索，进而确定热物性参数，并与优化方法的结果进行对比分析。

# 1地埋管与周围土壤传热模型

恒热流测试法是在现场进行热响应实验，采用恒定功率加热地埋管循环水，循环水在埋管中循环流动并与周围土壤进行换热，根据测量得到埋管进出口位置循环水温度随时间的变化，得到从测试开始到热平衡过程中温度随时间的响应曲线。根据测试得到的数据结合地埋管与周围土壤传热模型进行计算，并利用参数估计法最终得到热物性参数值是目前普遍的热物性参数计算方法。

由于工程中普遍采用的线热源模型计算结果满足准确性要求，且较其他模型计算便捷、适用性强[18]，本文采用线热源模型作为地埋管与地下周围土壤换热的计算模型。将地埋管看做线热源与外界换热需做如下假设[19]：1)地下土壤视为无限大介质；2）地埋管位于钻孔中心位置，并视为一根无限长的线热源；3)钻孔内回填材料及地下周围土壤各向同性，且物性参数维持恒定；4）钻孔内不存在热量累积现象；5）忽略土壤内的水分迁移、不同材质间的接触热阻。

基上述假设，可列出控制方程，初始条件和边界条件如下：

$$
\begin{array} { c } { { ( r _ { d } < r < \infty , \tau = 0 ) } } \\ { { ( r  \infty , \tau > 0 ) } } \end{array}
$$

其中， $T$ 为 $\tau$ 时刻距离线热源中心 $\boldsymbol { r }$ 处的温度， $^ { \circ } \mathrm { C }$ ; $T _ { 0 }$ 为土壤初始平均温度， $^ { \circ } \mathrm { C }$ $r _ { \mathrm { d } }$ 为钻孔半径, $\mathrm { m }$ ; $q _ { 1 }$ 为埋管每延米换热量， $\mathrm { W } { \cdot } \mathrm { m } ^ { - 1 }$ $\rho _ { \mathrm { s } } c _ { \mathrm { s } }$ 为土壤容积比热容， $\mathrm { J } { \cdot } \mathrm { m } ^ { - 3 } { \cdot } \mathrm { K } ^ { - 1 }$ ; $k$ 为土壤导热系数，$\mathrm { W } { \cdot } ( \mathrm { m } { \cdot } \mathrm { K } ) ^ { - 1 }$ $\tau$ 为时间，s。

循环水平均温度 $T _ { \mathrm { f } }$ 与钻孔壁温 $T _ { \mathrm { w } }$ 的关系式：

$$
T _ { \mathrm { f } } - T _ { \mathrm { w } } = q _ { \mathrm { l } } R _ { 0 }
$$

则循环水进出口平均温度 $T _ { \mathrm { f } }$ 为[20]：

$$
T _ { \mathrm { f } } = T _ { 0 } + q _ { \mathrm { l } } R _ { 0 } + { \frac { q _ { \mathrm { l } } } { 4 \pi k } } E i \left( { \frac { r _ { \mathrm { d } } ^ { 2 } \rho _ { \mathrm { s } } c _ { \mathrm { s } } } { 4 k \tau } } \right)
$$

其中, $R _ { 0 }$ 为钻孔内热阻, $\mathrm { m } { \cdot } \mathrm { K } { \cdot } \mathrm { W } ^ { - 1 }$ ， $E i \mathrm { ( X ) }$ 为指数积分函数。

参数估计法目标函数为地下埋管与周围土壤传热模型计算得到的循环水平均温度与实际测量值之间的方差和[7]：

$$
f = \sum _ { i = 1 } ^ { n } \left( T _ { \mathrm { c a l } , i } - T _ { \mathrm { e x p } , i } \right) ^ { 2 }
$$

其中， $T _ { \mathrm { c a l } , i }$ 为第 $i$ 时刻由传热模型计算得到的地埋管内循环水平均温度， $^ { \circ } \mathrm { C }$ $T _ { \mathrm { e x p } , i }$ 为第 $\mathbf { \chi } _ { i }$ 时刻热响应实验测得的循环水平均温度， $^ { \circ } \mathrm { C }$ ; $N$ 为数据测量组数。

# 2 穷举搜索法

穷举搜索法是将土壤热物性参数可能取值范围内的不同数值组合带入到式(3）中，得到循环水温度随时间变化的计算值，然后利用式（4）计算循环水温度计算值与测量值之间的方差和，从中寻找方差和最小值 $f _ { \mathrm { m i n } }$ ，此时对应的土壤热物性参数值即认为是所需测量的结果。

穷举搜索法将热物性参数的可能取值全部考虑在内，并逐一进行目标函数方差和的计算，比较得到方差和最小值。穷举搜索法与优化方法相比，它可得到目标函数最小值，而不是某局部区域的极小值，因而可以得到最接近实际的热物性参数值；穷举搜索法不存在对算法初始搜索值变化的影响与依赖。由于穷举搜索法在全局范围内进行计算分析与比较，所以运算时间较优化方法长。

# 3验证与分析

为了验证穷举搜索法计算结果的准确性，预先设定钻孔半径 $r _ { \mathrm { d } }$ 、每延米换热量 $q _ { \mathrm { l } }$ 、土壤导热系数$k$ 、钻孔内热阻 $R _ { 0 }$ 、土壤容积比热 $\rho _ { \mathrm { s } } c _ { \mathrm { s } }$ 等参数值,并用以计算循环水温度值作为模拟的测量结果，然后利用穷举搜索法确定土壤热物性参数，将设定值与运算值进行对比分析。采用两组参数设定值（见表1）分别进行验证。考虑到可能的土壤热物性参数值范围，本文选择的各参数搜索范围[21]为：0.5$\mathrm { W } { \cdot } \mathrm { m } ^ { - 1 } { \cdot } \mathrm { K } ^ { - 1 } < k < 5 . 0$ W $\cdot _ { \mathrm { m } } \mathrm { - } 1 . \mathrm { K } ^ { - 1 }$ ： $0 . 0 1 \ \mathrm { m } { \cdot } \mathrm { K } { \cdot } \mathrm { W } ^ { - 1 } <$ $R _ { 0 } ~ < ~ 0 . 3 ~ \mathrm { m { \cdot K } { \cdot W } ^ { - 1 } }$ ; $1 . 0 { \times } 1 0 ^ { 6 } \mathrm { J } { \cdot } \mathrm { m } ^ { - 3 } { \cdot } \mathrm { K } ^ { - 1 } < \rho _ { \mathrm { s } } c _ { \mathrm { s } } <$ $6 . 0 { \times } 1 0 ^ { 6 } \ \mathrm { J } { \cdot } \mathrm { m } ^ { - 3 } { \cdot } \mathrm { K } ^ { - 1 }$ 。利用穷举搜索法的计算结果见表2。

作为对比，同时采用优化方法寻找目标函数最优解，寻优方法采用目前广泛使用的遗传算法[22-23]。遗传算法通过“种群”的变异、交叉、选择，进行非确定性方式寻优，最终选定全局范围内所涉及“种群”的某一最优点。为保证遗传算法计算结果的准确性，同时考虑节省运行时间，设置遗传算法“遗传代数”为5000代，每代“种群”包含50个个体，优化方法计算得到的结果见表3。为进一步验证两种计算方法结果的可信度，将模拟测试温度曲线与两种方法得到的计算温度曲线进行了对比，见图 $1 { \sim } 2$ 。

由表2和表3可知，穷举搜索法得到每组方差和为0，即可以寻找到目标函数最小值，其对应的各参数值与设定值之间的相对误差也均为0，说明利用穷举搜索法可以准确地找到热物性参数值。而在模拟验证的两组数据中，优化方法得到的结果与设定值之间存在一定误差，其中得到的导热系数相对误差较小，钻孔内热阻相对误差较大，可达到 $1 3 \%$ =而容积比热的相对误差最大，最高可超过 $3 5 \%$ ，显然优化方法得到的导热系数准确度较高，但得到的钻孔内热阻和容积比热容则可信度相对较差。且优化方法得到的目标函数方差和大于穷举搜索法得到的方差和，这表明优化方法寻找到了局部区域内的热物性参数极小值而不是全局内的最小值如图 $1 { \sim } 2$ 所示，两种方法的计算温度曲线对模拟测试温度曲线拟合均非常好，由此可见，计算温度曲线和测试温度曲线拟合良好并不一定表明计算结果一定可靠。

表2穷举搜索法得到的土壤热物性参数  

<html><body><table><tr><td>参数</td><td>rd/m</td><td>q/W·m-1</td><td>k/W:m-1.K-1 Ro/m·K·W-1</td><td></td><td>psCs/106Jm-3.K-1</td></tr><tr><td>第一组</td><td>0.075</td><td>55</td><td></td><td>0.100</td><td>2.30</td></tr><tr><td>第二组</td><td>0.075</td><td>75</td><td>2.60</td><td>0.080</td><td>3.50</td></tr></table></body></html>

Table 2 Soil thermal parameters obtained by exhaustive search method   
表3优化方法得到的土壤热物性参数  

<html><body><table><tr><td>设定参数组别</td><td>计算项目</td><td>XK-1</td><td>Ro/mK·W-1</td><td>psCs/10Jm-3.K-1</td><td>fmin/K2</td></tr><tr><td rowspan="2">第一组</td><td>计算参数值</td><td>1.80</td><td>0.100</td><td>2.30</td><td rowspan="2">0</td></tr><tr><td>相对误差/%</td><td>0</td><td>0</td><td>0</td></tr><tr><td rowspan="2">第二组</td><td>计算参数值</td><td>2.60</td><td>0.080</td><td>3.50</td><td rowspan="2">0</td></tr><tr><td>相对误差/%</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

表1设定参数Table 1 Preset parameters  
Table 3 Soil thermal parameters obtained byoptimization method   

<html><body><table><tr><td>设定参数组别</td><td>计算项目</td><td>k/W·m-1.K-1</td><td>Ro/mKW-1</td><td>psCs/10J·m-3.K-1</td><td>fmin/K2</td></tr><tr><td rowspan="2">第一组</td><td>计算参数值</td><td>1.80</td><td>0.113</td><td>3.11</td><td rowspan="2">0.035</td></tr><tr><td>相对误差/%</td><td>0</td><td>13.00</td><td>35.22</td></tr><tr><td rowspan="2">第二组</td><td>计算参数值</td><td>2.61</td><td>0.080</td><td>3.48</td><td rowspan="2">0.056</td></tr><tr><td>相对误差/%</td><td></td><td>0</td><td>0.57</td></tr></table></body></html>

![](images/35e76b749db2c707c83b82f70c8ada915f5fab3949d749bdb67815c5b4f99f92.jpg)  
图1循环水温度随时间变化曲线 (第一组)  
Fig.1 Circulating water temperature variation vs.time (the first group)

![](images/0d66e2c3bafa70aaaa580fdcfa7b361de00aadbf51b63a537be15161177a102e.jpg)  
Fig.2 Circulating water temperature variation vs.time (the second group)

穷举搜索法可以得到确定的热物性参数值，且方差和最小，计算温度曲线对模拟测试温度曲线拟合非常好，显然穷举搜索法得到的热物性参数值与优化方法得到的结果相比具有更高的可信度。优化方法寻找到的通常是局部区域极小值而不一定是全局区域最小值，其原因在于遗传算法变异、交叉过程中没有得到的“个体”并未参与计算、比较，所以优化方法并未实现真正意义上的全局范围搜索寻优。，

# 44程应用

利用穷举搜索法分别对山东省烟台市 (工程 1)和北省清河县 (工程2)的两个工程项目进行了地下土壤热物性参数测量计算。现场测试得到的进出□循环水温度随时间的变化见图 $3 { \sim } 4$ 中的测试温度曲线。另外，本文还采用优化方法对地下土壤热物性参数进行了计算，两种方法得到的结果见表4，两种方法利用土壤热物性参数计算得到的循环水温度见图 $3 { \sim } 4$ 中的计算温度曲线。

穷举搜索法与优化方法均得到了较为接近的导热系数值，钻孔内热阻值存在一定偏差，而容积比热的差距较大。虽然两种方法得到的循环水计算温度曲线与实际测试温度曲线均拟合较好，但两个工程中穷举搜索法得到方差和最小值比优化方法得到的方差和极小值均要小，显然穷举搜索法得到的热物性参数值具有更高的可信性。

![](images/5adc4273174517810c54cfe68f9081fbb60876cf5266209dde881056cc8237e6.jpg)  
图2循环水温度随时间变化曲线 (第二组)  
图3循环水温度随时间变化曲线 (工程1)  
g.3 Curve of circulating water temperature changes with time (The first projecl

![](images/e3312867c07afd32c95d8f5d8d89254a7cb231d384f9c75fd36510af0f71e93a.jpg)  
图4循环水温度随时间变化曲线 (工程 2) Fig.4 Circulating water temperature vs.time (The second project)

表4穷举搜索法与优化方法得到的土壤热物性参数  

<html><body><table><tr><td colspan="6">labie4 30n thermal properties obtainec Oy</td></tr><tr><td rowspan="2"></td><td>计算方法</td><td>k/W·m-1.K-1</td><td>Ro/m·KW</td><td>psCs/10Jm-3.K-1</td><td>fmin/K2</td></tr><tr><td>穷举搜索法</td><td>1.73</td><td>0. 1</td><td>3.44</td><td>1.430</td></tr><tr><td rowspan="2">工程1</td><td>优化方法</td><td>1.79</td><td>0.110</td><td>1.47</td><td>4.326</td></tr><tr><td>穷举搜索法</td><td>1.35</td><td>0.235</td><td>2.63</td><td>1.450</td></tr><tr><td>工程2</td><td>优化方法</td><td>1.34</td><td>0.280</td><td>5.66</td><td>1.562</td></tr></table></body></html>

# 5结论

本文提出运用穷举搜索法寻找目标函数最小值，进而确定土壤热物性参数值，并与优化方法计算结果进行对比分析，通过上述分析得到结论：

1)通过验证分析，穷举搜索法可以得到目标函数最小值，进而确定准确的热物性参数值，其得到的计算温度曲线对模拟测试温度曲线拟合较好，计算结果具有较高的可信性。优化方法得到的土壤导热系数较为接近预设值，但得到的钻孔内热阻及容积比热与预设值存在一定误差，目标函数方差和较穷举搜索法得到的方差和大。 +t

2)分别采用穷举搜索法和优化方法对实际工程的地下土壤热物性参数进行计算，结果表明穷举搜索法较优化方法得到的地下土壤热物性参数值更为可信。

# 参考文献

[1]刁乃仁,方肇洪.地埋管地源热泵技术[M].北京：高等教育 出版社，2006:15-38 DIAO Nairen,FANG Zhaohong.Ground-Coupled Heat Pump Technology [M].Beijing:Higher Education Press, 2006:15-38   
[2]Luo J,RohnJ,BayerM,et al.Heating and Cooling Performance Analysis of a Ground Source Heat Pump System in Southern Germany [J].Geothermics,2015,53:57-66   
[3] Kavanaugh S P.Field Tests for Ground Thermal Properties-methods and Impact on Ground-source Heat Pump Design [J].ASHRAE Transactions,2000,106:851   
[4]王沣浩，颜亮,冯琛琛,等.地源热泵岩土导热系数测试影响 因素分析[J].制冷学报，2012,33(4)：16-22 WANG Fenghao，YAN Liang，FENG Chenchen，et al. Analysis of Influencing Factors on Soil Thermal Conductivity Test in Ground Source Heat Pump [J].Journal of Refrigeration, 2012, 33(4): 16-22   
[5] 胡平放，孙启明，雷飞，等.岩土热物性测试若干问题探讨 [J].制冷与空调,2012,12(4)：109-111 HU Pingfang,SUN Qiming,LEI Fei,et al. Discussion on Some Problems of Rock-Soil Thermal Properties Test [J]. Refrigeration and Air-Conditioning,2012,12(3):109-111   
[6] IGSHPA (International Ground Source Heat Pump Association).Closed-Loop/Geothermal Heat Pump Systems - Design and Installation Standards (2007 Edition） [M]. USA:Oklahoma State University, 2007   
[7]Austin W A.Development of an in Situ System for Measuring Ground Thermal Properties [D].Oklahoma State University,1998   
[8] Ingersoll L R,Plass HJ.Theory of the Ground Pipe Heat Source for the Heat Pump [J].ASHVE transactions,1948, 47(7):339-348   
[9]CarslawHS,Jaeger JC,FeshbachH.Conduction of Heat in Solids [J].Physics Today,1962,15:74   
[10]于晓菲,于明志,张磊,等.基于实心圆柱面热源模型的岩土 热物性测试方法[J].化工学报，2012,63(S1)：84-87 YU Xiaofei,YU Mingzhi, ZHANG Lei,et al. Ground Thermal Properties Measurement Method Based on Solid Cylindrical Heat Source Model[J].CIESC Journal,2012, 63(S1): 84-87   
[11]Alonso-Sanchez T,Rey-Ronco MA,Carnero-Rodriguez F J,et al. Determining Ground Thermal Properties Using Logs and Thermal Drill Cutting Analysis.First Relation

ship with Thermal Response Test in Principality of Asturias,Spain[J].Applied Thermal Engineering,2012,37: 226-234 [12]Pieter E.System Identification:Parameter and State Estimation [M].New York:Wiley-Interscience,1974:104-230 [13]赵飞.现场岩土热响应测试及数据处理分析方法研究[D]. 西安：西安建筑科技大学，2013 ZHAO Fei. In-suit Soil Thermal Response Test and its Data Processing Methods Studies [D].Xi'an:Xi'an University of Architecture and Technology, 2013 [14]LamarcheL,KajlS,BeauchampB.AReview ofMethods to Evaluate Borehole Thermal Resistances in Geothermal Heat-pump Systems [J].Geothermics,2010,39(2):187- 200 [15]LiM,Lai ACK.Parameter Estimation ofIn-situ Thermal Response Tests for Borehole Ground Heat Exchangers [J]. International Journal of Heat and Mass Transfer,2012, 55(9): 2615-2624 [16]Rose K,Gurewitz E,Fox G C.Constrained Clustering as an Optimization Method [J].Pattern Analysis and Machine Intelligence,IEEE Transactions on，1993,15(8): 785-794 [17]Engle JA,Legault K R,Rosati JD.Sediment Budget Formulation Via Exhaustive Search Method [J].Coastal Engineering Proceedings,2012,1(33):121-123 [18]Luo J,RohnJ,XiangW,et al.AReview ofGroundI

tigations for Ground SourceHeat Pump(GSHP)Systems [J].Energy and Buildings,2016,117:160-175   
[19] Spitler J D,Gehlin S E A.Thermal Response Testing for Ground Source Heat Pump Systems—An Historical Review [J].Renewable and Sustainable Energy Reviews, 2015,50:1125-1137   
[20] Roth P,Georgiev A,Busso A,et al. First in Situ Determination of Ground and Borehole Thermal Properties in Latin America [J].Renewable energy, 2004,29(12):1947- 1963   
[21]肖衡林，吴雪洁，周锦华．岩土材料导热系数计算研究[J]. 路基工程，2007(3):54-56 XIAO Henglin,WU Xuejie,ZHOU Jinhua. Study on the Calculation of Thermal Conductivity ofRock and Soil Material [J].Subgrade Engineering,2007(3):54-56   
[22]金芬.遗传算法在函数优化中的应用研究[D].苏州:苏州大 学,2008 JIN Fen，Application Research of Genetic Algorithm in FunctionQptimization [D]. Suzhou: Soochow University, 1   
[23葛继科,邱玉辉,吴春明，等.遗传算法研究综述[J].计算机 应用研究,2008,25(10):2911-2916 GE Jike,QIU Yuhui,WU Chunming,et al. Summary of Genetic Algorithms Research[J].Application Research of Computers,2008,25(10):2911-2916