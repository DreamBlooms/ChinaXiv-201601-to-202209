# 基于改进PSO算法的MAP图标定点选择新方法

程准，陆凯，钱煜，卢震，鲁植雄(南京农业大学 工学院，南京 210031)

摘要：为提高基于MAP 图的控制系统驱动效果，并有效减小控制系统内的存储量，提出了一种基于改进粒子群算法的MAP图中标定点择优选取新方法。以液压机械无级变速传动比控制系统中采用的MAP图为例，将其横坐标的2个变量在其定义域内等分，并采用改进粒子群算法选取等分后每段内的坐标点数量和位置。选取过程采用多目标优化原理结合了随机产生的100个点的实际值与 MAP 图线性插值的平均误差以及选定的标定点数量。为提高算法执行效率，对粒子群算法的迭代准则、惯性权重和学习因子进行了改进。结果表明，改进后的粒子群算法收敛速度快，寻优精度高；仅需较少的标定数据即可制作控制效果较佳的MAP图。

关键词：改进粒子群算法；MAP图；控制系统；液压机械无级变速器中图分类号：0231 doi:10.3969/j.issn.1001-3695.2018.04.0218

# New method of MAP fixed-point selection based on improved PSO algorithm

Cheng Zhun,Lu Kai, Qian Yu, Lu Zhen,Lu Zhixiong (College ofEngineering,Nanjing Agricultural University,Nanjing21oo31,China)

Abstract: Inorderto improve the driving effectof thecontrol systembasedon MAPand reduce the storage capacityof the control system effectively,this paperproposedanew method forselectingthe fixed points inthe MAPbasedonthe improved particle swarm optimization algorithm.Taking the MAPof hydraulic mechanical continuouslyvariable transmissionratio controlystemasanexample,itdividedthe2variablesof theabscissacoodinateinitsdefinitiondomain,anditused the improved particle swarm optimization algorithm to select the number and locationofcoodinate points ineach section after equal division.The selection processwas based onthe principleof multi-objective optimization,whichcombines theactual values of 1OO randomly generated points with the average errorof linear interpolationof MAPandthe numberof selected scalar points.Iordertoimprovetheeficiencyofthealgorithm,itimprovedtheiterativecriteria,theinertia weightand the learning factorof the particle swarmoptimization.Theresults show that theimproved particle swarm optimization algorithm has the advantages offastconvergence speedand highoptimizationaccuracyandthe MAP withbetercontrol eectcan be made with less calibration data.

Key words:improved particle swarmoptimizationalgorithm；MAP；control system;hydraulicmachinerycontinuously variable transmission

# 0 引言

MAP图是电控系统的核心，为控制系统提供控制参数，在工程领域亦可以称为实验数据图表。其通常以二维图表或三维图表的形式存储于控制器（ECU）中[1,2]。通过查表的方法从MAP图中获取控制数据，能够有效地降低ECU的计算量，提高系统效率，减小响应时间并改善控制效果。所以研究MAP

图的构成意义深远。

现阶段关于电控系统MAP 图的研究较少 $\cdot \left[ 3 { \sim } 6 \right]$ 。文献[7]采用BP神经网络建立待标定系统的模型，再通过自适应神经模糊推理系统（ANFIS）进行非线性插值，结果表明可以有效减少MAP图标定实验并同时在很大程度上保证了精度。文献[8]基于镍氢电池荷电状态（SOC）的基本MAP图，采用曲线平移的方法插值获取了较精确的MAP图模型。由于该MAP图的数据量较大，通过分割和压缩处理以提高查表速率并减小存储空间。文献[9]基于大量的实验标定了SCR控制参数MAP图。虽然MAP图很细致，但是增加了标定实验的数量。文献[10]对柴油机的SCR控制系统进行设计与研究，分别对发动机排气流量、原机排放 $\mathsf { N O } _ { x }$ 浓度、循环供油量、排气温度以及 $\mathsf { N O } _ { x }$ 最大转换效率的MAP进行了标定。但是实验标定时，总是在工况取值范围内以固定的步长进行变化。文献[11]基于输出反馈参考模型自适应控制算法来标定离合器接合控制系统的MAP图，虽然能在很大程度上提高系统的效果和性能，但是MAP图的构建过程需要参数整定，并且缺少对MAP图中数据点个数的研究。文献[12]对插入式并联混合配置的能量管理MAP图进行优化标定研究，虽然可以利用查表法获取最佳换挡、最佳转矩分配以及驱动模式，但是缺少MAP图标定数据的精度和个数研究。以上研究虽然都在一定程度上提高了从MAP图中获取控制参数的精度，但是非线性的插值方法增加了一般控制器逻辑实时处理的难度，而且并未从实际出发在本质上减少MAP图中标定点的数量，从而减小ECU中的存储空间。

针对上述问题，为有效减少MAP图中数据点数量，同时保证控制参数的精度以及ECU的处理速度，本文提出了一种基于改进的粒子群算法的MAP图中标定点择优选择方法。将从MAP图中通过简单的线性插值获取100个随机工况的控制参数值与实际值的平均误差以及MAP图中标定数据点的数量作为2个优化目标，通过多目标优化理论进行分析。为提高优化算法执行效率，对粒子群算法作出优化改进。本文研究以液压机械无级变速控制系统的最优经济性传动比MAP图为例，以期为其他领域的MAP图获取提供一定的理论指导。

# 1 液压机械无级变速器最优经济传动比MAP图的获取

液压机械无级变速器（HMCVT）是一种车辆上用的无级变速器。其经济性传动比MAP图的获取计算公式如下：

$$
\mathrm { ~ m i n ~ } \qquad f ( x ) = \frac { g _ { e } } { \eta _ { c \nu t } }
$$

其中： $g _ { e }$ 为发动机有效燃油消耗率； $\eta _ { _ { c \nu t } }$ 为 HMCVT 的传动效率； $x$ 为三维向量，由发动机转速、扭矩和HMCVT传动比组成。

HMCVT最优经济传动比MAP图由发动机不同转速、转矩以及满足式（1）的HMCVT传动比值绘制完成。某经济传动比MAP图如图1所示。

# 2 改进的粒子群算法

粒子群算法(particle swarmoptimization，PSO)是一种基于仿生学模拟大自然鸟类活动的随机优化算法，其本质是基于群体的进化算法，通过鸟类群体间的交流和个体对历史最佳位置

的记忆来不断迭代寻优[13-17]。其速度更新采用如下公式：

$$
\nu _ { i } ^ { d + 1 } = \omega \nu _ { i } ^ { d } + c _ { 1 } r _ { 1 } ( p _ { i } ^ { d } - x _ { i } ^ { d } ) + c _ { 2 } r _ { 2 } ( p _ { g } ^ { d } - x _ { i } ^ { d } )
$$

其中： $\nu _ { i } ^ { d }$ 为第 $i$ 个粒子第 $d$ 次迭代的飞行速度； $\omega$ 为惯性权重； $c _ { 1 }$ 和 $c _ { 2 }$ 为学习因子； $r _ { \mathrm { 1 } }$ 和 $r _ { 2 }$ 为0\~1之间的随机数； $p _ { i } ^ { d }$ 为第 $i$ 个粒子第 $d$ 次迭代的历史最佳值； $p _ { g } ^ { d }$ 为所有粒子第 $d$ 次迭代的历史最佳值。

![](images/7b5f3f621f5c16a466a49a0109a947c0207887dfea476b65831fcac940054fa2.jpg)  
图1HMCVT经济传动比MAP图

PSO 算法受其算法参数的影响较大，若PSO中的粒子向个体或者群体的历史最佳位置聚拢速度较快，则会形成趋同效应，这使得算法容易早熟。为提高算法收敛速度和寻优精度，采用如下方法对PSO进行改进：

a）惯性权重 $\omega$ 自适应变化。惯性权重 $\omega$ 可以影响微粒群算法的局部最优能力和全局最优能力。较大的权重有利于提高算法的全局粗扩搜索能力，而较小的权重会增强算法的局部精确搜索能力。由此可见目标函数每代下降速率较慢时需要大的权重以便于跳出局部最优点，下降速率较快时需要小的权重以便于精确搜索。为使得惯性权重匹配算法迭代情况，基于查表法来设计惯性权重。在某次迭代过程中，若目标函数的下降幅度在 $0 \sim 3 0 \%$ 间，则 $\omega$ 在区间[0.2,0.7]内随机产生；若目标函数的下降幅度在 $30 \% { \sim } 1 0 0 \%$ 间，则 $\omega$ 参考上一次迭代的取值；若目标函数的下降幅度连续5代没有变化，则 $\omega$ 取值为1；若目标函数的下降幅度连续10代没有变化，则 $\omega$ 取值为2。

b）算法搜索的后期由学习因子 $c _ { 1 }$ 和 $c _ { 2 }$ 的不断减小来保证精确的局部搜索需求。学习参数的改进参见文献[18]。c）引入模拟退火算法的概率判断Metropolis准则，该准则如式（3）所示。

$$
P = e ^ { ( - \frac { \Delta E } { T } ) }
$$

其中： $P$ 为接受差解的概率； $\Delta E$ 为前后2代目标函数的差值；

$T$ 为模拟退火算法中的温度参数，其随迭代次数的增加而不断下降。Metropolis 准则的引入使得PSO算法在算法迭代的初期和中期能够有一定的概率接受较差的解，避免了早熟现象，提高了寻找到全局最优解的可能性。

为验证改进PSO算法的效果，采用如下测试函数：

$$
f ( x _ { 1 } , x _ { 2 } ) = \frac { \sin ^ { 2 } \sqrt { x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } } } { [ 1 + 0 . 0 0 1 ( x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } ) ] ^ { 2 } }
$$

该测试函数有唯一最小值0,其所对应的最小值点为 $( 0 , 0 )$ 。粒子群规模为20，算法最大迭代次数为20，测试结果如图2所示。

![](images/dc7e83467b8d18bca7a7abd1083b2b17fa8df439b292c50433752707be15c7dd.jpg)  
图2测试函数迭代进化图

根据图2，本文提出的改进PSO算法在第5代时已经优化得到最小值，并跳出了迭代循环。而标准的PSO算法在第9代陷入局部最小值，并未找到最优解，其找到的解为(-5，8)，对应的值为0.00071。

# 3 择优选定MAP图标定点的方法

以MAP图中标定数据点的位置及数量作为决策变量。为使得决策变量更符合算法编程和实际优化的需求，将MAP图中自变量的2个坐标在其定义域内分为5个等份，并设每个等份中的坐标数量为算法运行中的决策变量。以HMCVT经济传动比MAP图为例，其决策变量如下所示：

$$
X = [ q _ { 1 } , q _ { 2 } , q _ { 3 } , q _ { 4 } , q _ { 5 } , p _ { 1 } , p _ { 2 } , p _ { 3 } , p _ { 4 } , p _ { 5 } ]
$$

其中： $q _ { i }$ 为转速在其定义域内第 $i$ 个等份中被选择坐标点的数量； $p _ { i }$ 为扭矩在其定义域内第 $i$ 个等份中被选择坐标点的数量。

在每个等份内被选择的坐标点数值根据其区间长度按数量进行平分来确定。

优化目标有两个。第一个为随机产生100个不同转速、扭矩值并基于MAP图采用简单的线性插值方法获取的值与实际

值的平均误差，第 $d$ 代第 $i$ 个粒子的目标函数 $f _ { 1 }$ 计算公式如下：

$$
f _ { 1 } ( X _ { i } ^ { d } ) { = } \sum _ { j = 1 } ^ { 1 0 0 } ( 1 { - } \frac { \left| z _ { j } - z _ { j } ^ { \prime } \right| } { z _ { j } } ) { \times } 1 0 0 \%
$$

其中： $X _ { i } ^ { d }$ 为第 $d$ 代第 $i$ 个粒子； $z _ { j }$ 为第 $j$ 个随机工况（转速和扭矩随机产生）的传动比实际值； $\boldsymbol { z } _ { j } ^ { \prime }$ 为第 $j$ 个随机工况采用线性插值方法获得的传动比值。

第二个优化目标为MAP图中标定数据点的数量，第 $d$ 代第 $i$ 个粒子的目标函数 $f _ { 2 }$ 计算公式如下：

$$
f _ { 2 } ( X _ { i } ^ { d } ) { = } \sum _ { j = 1 } ^ { 5 } ( p _ { j } + q _ { j } )
$$

由于优化过程涉及到两个不同数量级的目标函数，采用分配权重系数的方法对该多目标优化问题进行处理。

# 4 实验结果与分析

采用本文提出的改进PSO 算法对HMCVT经济传动比MAP图中的标定数据点进行择优选取。粒子群规模设置为50，最大迭代次数为200。寻优迭代进化结果如图3所示。

![](images/411e5810c65bc1a769fb704a709368bd21e6873587186b43997bd4d74790b267.jpg)  
图3MAP图标定点择优选取进化图

转速和扭矩在其各自每个等份内坐标点的数量如表1所示。

表1MAP图中每个等份内坐标点的数量  

<html><body><table><tr><td>q1</td><td>q2</td><td>q3</td><td>q4</td><td>q5</td><td>p1</td><td>p2</td><td>p3</td><td>p4</td><td>p5</td></tr><tr><td>2</td><td>2</td><td>20</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>9</td></tr></table></body></html>

择优选取标定点绘制的MAP图如图4所示。

![](images/3d24dab27aedd047e35e21d157e8be0bdca1561cc16c50e293b26f90b653d51a.jpg)  
图4标定点择优选取后的MAP图

采用简单的线性插值方法基于图4获取100个随机工况的传动比值，其与实际传动比值的平均误差仅为 $3 . 7 \%$ ，该MAP图中转速和扭矩选择的坐标数量分为28和17个，总标定点数为原图1中的 $1 5 . 9 \ \%$ 。

# 5 结束语

a）本文提出的惯性权重系数自适应改进方法有效提高了PSO算法的收敛速度和寻优精度，该方法将惯性权重系数与算法目标函数下降幅度结合起来，通过查表的方法动态确定每代的惯性权重值，结果表明仅用5次迭代即实现对测试函数最小值的寻优分析。

b）本文提出的基于进化算法的MAP图中标定数据点择优选取方法能高效的减小MAP图中的数据量，以HMCVT经济传动比MAP图为例，优化后数据总量为原先的 $1 5 . 9 \ \%$ ，能够在很大程度上减小ECU中的存储量。并且采用的查表方法为最简单的线性插值法，有利于ECU的处理和计算，本例中MAP图的平均误差仅为 $3 . 7 \%$ 。

# 参考文献：

[1]张志超.高压共轨柴油机控制 MAP体系研究[D].昆明：昆明理工大 学,2015.(Zhang Zhichao.Study on control MAP system of high pressure common Rail diesel engine [D]. Kunming: Kunming University of Science and Technology,2015.)   
[2]沈晓勇．基于MAP图的双集成车用驱动电机系统研究[D].大连：大 连理工大学,2O12.(Sheng Xiaoyong. Study on double integrated vehicle drive motor system based on MAP [D].Dalian:Dalian University of Technology,2012.)   
[3]黄贵芬，陈虹，胡云峰．基于模型和MAP图的汽油发动机气路控制[J]. 系统科学与数学,2011,31(12):1592-1601.(Huang Guifen,Chen Hong, Hu Yunfeng.Model and MAP based gasoline engine airpath control [J]. Journal of Systems Science and Mathematical Sciences,2O11,31 (12): 1592-1601.)   
[4]周广猛，刘瑞林，周平，等．基于多项式回归模型的高压共轨柴油机的

标定[J]．汽车工程，2012，34(4):301-305.(Zhou Guangmeng，Liu

Ruilin,Zhou Ping,et al. The calibration of high-pressure common-rail diesel engine based on polynomial regression model [J]．Automotive Engineering,2012,34(4):301-305.)

[5]王天利，于瀛霄，张大明.基于MAP图的微型电动汽车驱动电机匹配 研究[J].农业装备与车辆工程，2013,51(7):17-20.(Wang Tianli，Yu Yingxiao,Zhang Daming.Study on matching of driving motor for miniature electric vehicle based on the MAP diagram [J].Agricultural Equipment& Vehicle Engineering,2013,51(7):17-20.)

[6]Langouet H,Metivier L，Sinoquet D,et al.Engine calibration: multi-objective constrained optimization of engine MAPs [J].Optimization and Engineering,2011,12(3): 407-424.

[7]韩强，杨福源，张京永，等．用于标定和优化的高压共轨柴油机建模 [J].清华大学学报：自然科学版，2004,44(11):1524-1527,1535.(Han Qiang,Yang Fuyuan,Zhang Jingyong,et al.High pressure common rail diesel engine modeling for calibration and optimization [J]. Journal of Tsinghua University(Science and Technology），2004，44(11): 1524-1527.)

[8]胡志坤，王文祥，林勇，等．基于4维MAP图的镍氢电池 SOC估计方法[J]．电机与控制学报，2012，16(2):83-89.(Hu Zhikun，WangWenxiang,Lin Yong,etal.Four-dimensional Map basedNi-MHbattery’sSOC estimation method [J]. Electric Machines and Control,2012,16 (2):83-89.)

[9]邓成林，罗云威，李浩，等．柴油机Urea-SCR系统标定试验研究[J]. 汽车工程,2013,35(1):32-36,77.(Deng Chenglin,Luo Yunwei,Li Hao, et al.An experimental study on the calibration of Urea-SCR system in diesel engine [J]. Automotive Engineering,2013,35 (1): 32-36,77.)

[10]胡杰，王立辉，王天田．柴油机Urea-SCR控制系统设计与试验[J].农 业机械学报,2016,47(2):349-356.(Hu Jie,Wang Lihui,Wang Tiantian. Design and test of Urea-SCR control system for diesel engine [J]. Transactions of the Chinese Society for Agricultural Machinery,2O16,47 (2):349-356.)

[11] HuangWei，Wong Pak Kin，Zhao Jing，et al.Output-feedback model-reference adaptive calibration for map-based anti-jerk control of electromechanical automotive clutches [J]. International Journal of Adaptive Control and Signal Processing,2018,32 (2):265-285.

[12] SchoriM,Boehme,TJ,FrankB,et al.Optimal calibration of map-based energy management for plug-In parallel hybrid configurations:a hybrid optimal control approach [J].IEEE Trans on Vehicular Technology, 2015, 64 (9): 3897-3907.

[13] Wang Dongshu, Tan Dapei,Liu Lei.Particle swarm optimization algorithm: an overview [J]. Soft Computing,2018,22 (2):387-408.

[14] Wu Qinghua,Song Tao,Liu Hanmin,et al.Particle swarm optimization algorithm based on parameter improvements [J]. Journal of Computational Methods in Sciences & Engineering,2017,17(3): 557-568.

[15] Zhang Geng,Li Yangmin,Shi Yuhui.Distributed learning particle swarm optimizer for global optimization of multimodal problems [J].Frontiers of

Computer Science,2018,12(1):122-134.

[16]谢国民，刘叶，付华，等．基于PSO-GSA 优化的井下加权质心人员定 位算法[J].计算机应用研究,2017,34(3):710-713.(Xie Gu0min,Liu Ye,Fu Hua,et al.Improved downhole weighted centroid localization algorithm based on PSO-GSA [J].Application Research of Computers, 2017,34 (3): 710-713.)

[17]张勇，陈玲，徐小龙，等．基于PSO-GA混合算法时间优化的旅行商问题研究[J]．计算机应用研究，2015,32(12):3613-3617.(Zhang Yong,

ChenLing,Xu Xiaolong,et al.Research on time optimal TSP based on hybrid PSO-GA [J].Application Research of Computers,2015,32 (12): 3613-3617.)

[18]程准，鲁植雄，唐迪，等．基于改进PSO算法的拖拉机驱动防滑PID控 制策略[J].计算机应用研究，2017,34（1):83-86.(Cheng Zhun，Lu Zhixiong,TangDi,et al.PID control strategy of tractor driving anti slip control based on improved PSO algorithm [J].Application Research of Computers,2017,34(1): 83-86.)