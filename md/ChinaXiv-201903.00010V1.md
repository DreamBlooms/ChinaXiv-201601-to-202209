# 基于动态柯西蜂群算法优化支持向量机的风机叶片故障诊断

王宇鹏1 王致杰¹　刘　琦²　徐莉莉²　王 鸿³　程亚丽（1.上海电机学院电气学院上海 2013062.上海电气风电设备有限公司上海 2002413.山东科技大学电气与自动化工程学院青岛 266590）

![](images/594a80ced134433a28bbdcfaefc739001533a394935fbb7295c7b54ffb047d31.jpg)

王宇鹏男 1992年生，硕士研究生，研究方向为智能电网技术与故障诊断。

摘要：为了提高风力发电机叶片故障的识别率，利用支持向量机建立风力发电机叶片故障和特征参数之间的非线性关系。在蜂群算法中引入一种动态柯西因子，动态调节蜂群寻优过程中的搜索步长，提高蜂群算法的扰动能力，避免蜂群陷入局部搜索，采用这种动态柯西蜂群算法对支持向量机的参数寻优，建立动态柯西蜂群算法优化的支持向量机模型。采集南方某风场风力发电机叶片的四种工况下的特征数据训练此模型并进行故障诊断，诊断结果表明改进后的蜂群算法优化支持向量机模型能够提高风力发电机叶片的故障识别率，具有一定的工程参考意义。

关键词：动态柯西因子蜂群算法 支持向量机风机叶片 故障诊断中图分类号：TM15

# Fault Diagnosis of Wind Turbine Blade Based on Cauchy Artificial Bee Colony Algorithm Optimized Support Vector Machine

![](images/5438d9616c5be4935c283cfcceb85146f9100c2ee5e0b70d03ad5d9204cd4e18.jpg)

王致杰男 1964年生，博士研究生，研究方向为风电机组、电力设备故障诊断。

Wang Yupeng'Wang Zhijie'Liu $\mathcal { Q } i ^ { 2 }$ Xu Lili²Wang Hong³ Cheng Yalil （1.Shanghai Dianji UniversityShanghai201306 China 2. Shanghai Electric Wind Power Equipment Co.LtdShanghai200241 China 3.Shandong Science and Technology UniversityQingdao266590 China ）

Abstract: In order to improve the recognition rate of wind turbine blade fault diagnosis,the nonlinear relationship between fault diagnosis and characteristic parameters of wind turbine blade is established by using support vector machine.In the Cauchy artificial bee colony algorithm,a dynamic Cauchy factor is introduced to dynamically adjust the search step in the optimization process of the colony, to improve the perturbation ability of the colony algorithm,and to avoid the colony into the local search.A dynamic support vector machine model for dynamic Cauchy bee colony optimization is established. The model is trained and diagnosed by four conditions of a wind farm in the south. The results show that the support vector machine model can be improved based on the dynamic Cauchy artificial bee colony algorithm.Wind turbine generator fault recognition rate, with a certain engineering reference significance.

Keywords: Dynamic Cauchy factor, artificial bee colony algorithm, support vector machine,wind turbine,bladefault diagnosis

# 1 引言

随着我国风电装机容量的不断增加，风力发电机的可靠性显得尤为重要，叶片故障在各种故障中占了较高的比例[1]。风机叶片的故障诊断关键在于对叶片故障的识别与分类。支持向量机（SupportVectorMachine，SVM）不仅描述故障与特征间的非线性变化关系，可以解决非线性、高维度的问题，而且诊断速度快，成为电气故障诊断的主要研究方向[2]。文献[3]用谐波小波包分解信号，利用支持向量机（SVM）进行分类，取得了良好的识别效果。在利用SVM进行分类的过程中，模型参数的选择会影响最终分类的结果。

D.Karaboga提出了人工蜂群算法（ArtificialBee Colony，ABC）[4]，该算法不仅参数少，而且全局搜索能力强，因此在多种寻优问题上被广泛研究和应用[5]。文献[6]进行了人工蜂群算法ABC 优化支持向量机的电气故障诊断方法研究，解决SVM参数优化难题，提高了电气故障诊断的可靠性。本文提出一种动态柯西人工蜂群算法（DynamicCauchyArtificialBeeColony，DCABC)，优化支持向量机，利用DCABC-SVM对风机叶片故障进行故障诊断，通过实验验证了这种方法的可行性。

# 2 支持向量机理论

给定样本集 $T = \{ x _ { i } , y _ { i } | i = 1 , 2 , \cdots , m \}$ ，其中 $\mathbf { \mathfrak { x } } _ { i } \in R ^ { n }$ 表示输入矢量； $y _ { i } \in \{ + 1 , - 1 \}$ 表示对应的期望输出矢量； $\mathbf { \nabla } _ { m }$ 为样本数。通过非线性的映射函数，将输入的数据映射到高维线性空间，在高维特种空间中构造最优分类超平面

$$
f ( x ) = w \varphi ( x ) + b = 0
$$

式中， ${ \bf \nabla } _ { \pmb { \mu } } \psi$ 为权值矢量； $b$ 为阈值。

此时 $\vert f ( x ) \vert = 1$ ，样本离分类面最近，分类间隔最大且训练误差为零，要求分类间隔 $2 / | | _ { W } | |$ 最大,即 $\left\| \boldsymbol { w } \right\| ^ { 2 }$ 最小。分类面要对所有样本正确分类，故有约束条件

$$
y _ { i } [ w \varphi ( x ) + b ] \geqslant 1 \quad i = 1 , 2 , \cdots , l
$$

对于线性不可分的样本的情况，在约束条件中引入 $\xi _ { i }$ 来解决误差问题[7]；当 $0 \leqslant \xi _ { i } \leqslant 1$ 时，样本点正确分类； $\xi _ { i } \geqslant 1$ 时，样本点将被错分。为解决此问题，在最小化的目标函数中加入惩罚项 $C \sum _ { i = 1 } ^ { l } \xi _ { i }$ ，

此时的优化问题变为

$$
\begin{array}{c} \begin{array} { l } { \displaystyle \left\{ \operatorname* { m i n } _ { \mathbf { \phi } } \psi _ { \left( w \right) } = \frac { 1 } { 2 } \Big \| w \Big \| ^ { 2 } + C \sum _ { i = 1 } ^ { l } \xi _ { i } \quad \right.} & { i = 1 , 2 , 3 , \cdots , l } \\ { \mathrm { s . t . } \quad y _ { i } = [ ( w x _ { i } + b ) ] \geqslant 1 - \xi _ { i } } \end{array}   \end{array}
$$

式中， $\xi _ { i }$ 为松弛变量； $C$ 为惩罚因子。

引入核函数 $K ( x _ { i } , x _ { j } ) { = } \varphi ( x _ { i } ) \varphi ( y _ { i } )$ ， $K ( x _ { i } , y _ { i } )$ 满足Mercer条件[8]，本文中选择径项基核函数（RBF）：$K ( x _ { i } , y _ { i } ) = \exp ( - \vert \vert x _ { i } , y _ { i } \vert \vert ^ { 2 } / 2 \sigma ^ { 2 } )$ 为本文中的核函数。并引入Lagrangian乘子 $a _ { i }$ ，上述问题转化为二次规划的优化问题

$$
\left\{ \begin{array} { l l } { \displaystyle { \operatorname* { m a x } L ( a ) = \sum _ { i = 1 } ^ { m } a _ { i } - \frac { 1 } { 2 } \sum _ { i , j = 1 } ^ { m } a _ { i } a _ { j } y _ { i } y _ { j } K ( x _ { i } , y _ { i } ) } } \\ { \mathrm { s . t . } \quad \displaystyle { \sum _ { i = 1 } ^ { m } a _ { i } y _ { i } = 0 \geqslant 0 \quad i = 1 , 2 , 3 , \cdots , l } } \end{array} \right.
$$

$a _ { i } > 0$ 对应的点成为支持向量机，通常支持向量的数目要小于训练样本的个数，通过解式（5）来获得分类决策函数

$$
f ( x ) = \mathrm { s g n } \left( \sum _ { i , j = 1 } ^ { m } a _ { i } a _ { j } K ( x _ { i } , y _ { i } ) + b \right)
$$

在建模中，惩罚参数 $C$ 和核函数参数γ的选择影响 SVM诊断的效果[9]。 $C$ 值起调节样本误分率与学习机复杂性的作用；核函数参数 $\gamma$ 主要影响样本数据在高维空间中分布的复杂程度，本文将采用改进的蜂群搜索算法对 $C$ 和γ寻优，从而得出实际情况中分类模型最优值。

# 3 动态柯西蜂群算法

# 3.1 基本蜂群算法

人工蜂群算法ABC模拟实际蜜蜂采蜜行为，包含：引领蜂（leaders）、跟随蜂（followers）和侦查蜂（scouts）[10]。初始化时食物源个数与采蜜蜂的个数相等，食物源的位置代表问题的优化解，随机产生一个初始种群，在适应度值较优的一半个体周围进行搜索，采用竞争方式选择并保留较优个体；然后跟随蜂搜索，采用轮盘赌的选择策略选择较优的个体，并在其周围进行贪婪搜索产生另一半个体；最后侦查蜂搜索，如某个食物源被放弃，则产生侦查蜂，寻找新的食物源。

假设蜜源总数为 $N$ ，随机产生蜜源的初始位置为

$$
X _ { i j } = X _ { \mathit { j } \operatorname* { m i n } } + \operatorname { r a n d } ( 0 , 1 ) ( X _ { \mathit { j } \operatorname* { m a x } } - X _ { \mathit { j } \operatorname* { m i n } } )
$$

式中， $X _ { j \mathrm { m a x } }$ 为蜂群搜索范围的上边界； $X _ { j \mathrm { m i n } }$ 为蜂群搜索范围的下边界；rand(O,1)为[0,1]之间随机数。

按式（7）引领蜂随机选取食物源进行交叉搜索，对食物源进行更新产生一个新解，在计算新解的适应度值时，利用贪婪准则对新解和最优解进行选择。

$$
\nu _ { _ { i j } } = x _ { _ { i j } } + \varphi _ { _ { i j } } ( x _ { _ { i j } } - x _ { _ { k j } } )
$$

式中， $k { \in } \{ 1 , 2 , \cdots , N / 2 \}$ ， $j { \in } \{ 1 , 2 , \cdots , n \}$ ，且 $k \neq i$ ， $\varphi _ { i j }$ 为[-1,1]之间的随机数。

跟随蜂以概率 ${ \mathbf { } } _ { P _ { i } }$ 并根据轮盘赌的选择方法选择蜜源采蜜，由式（9）计算其邻域搜索得到的对应适应值，利用贪婪准则对新解和最优解进行选择。

$$
P _ { i } = f _ { \mathrm { i t i } } { \Bigg / } \sum _ { i = 1 } ^ { N } f _ { \mathrm { i t i } }
$$

式中， $f _ { \mathrm { i t i } }$ 为 $X _ { i }$ 的适度函数值。

$$
f _ { \mathrm { i t i } } = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 1 + f _ { i } } \qquad } & { f _ { i } \geqslant 0 } \\ { \displaystyle 1 + a b s ( f _ { i } ) \qquad } & { f _ { i } < 0 } \end{array} \right.
$$

式中， $f _ { i }$ 为第 $i$ 个解的目标函数值。

当蜜源 $X _ { i }$ 连续经过lim次循环搜寻仍没有变化，则放弃此蜜源，采蜜蜂变成侦查蜂，通过式(6）随机产新的蜜源代替原蜜源进行下一次计算。

# 3.2对蜂群搜索步长的动态调整

由于搜索步长的随机性，跟随蜂在选中的蜜源邻域内搜索时，在初始阶段不一定可以保证搜索的全局性，在随后的搜索过程中也可能陷入局部搜索，不能保证算法的整体性能。因此，在蜂群寻优过程中，期望其在初始阶段扩大搜索范围，在最优解附近缩小搜索范围。文献[11]对搜索步长做出线性调整，减少了随机步长，但在最优解附近也陷入局部搜索。本文引入一种动态因子 $w$ ，调整后的为

$$
w = w _ { \mathrm { m i n } } + \big ( w _ { \mathrm { m a x } } - w _ { \mathrm { m i n } } \big ) \mathrm { e } ^ { - t }
$$

$$
t = f _ { i } { \Bigg / } \sum _ { i = 1 } ^ { n } f _ { i }
$$

式中， $w _ { \mathrm { m i n } }$ 为最小惯性权值； $w _ { \mathrm { m a x } }$ 为最大惯性权值；  
$f _ { i }$ 为每次适应度值。

引领蜂和跟随蜂的位置更新公式就变为

$$
\nu _ { _ { i j } } = x _ { _ { i j } } + w ( x _ { _ { i j } } - x _ { _ { k j } } )
$$

由式（10）可知，在初始阶段 $\mathbf { \xi } _ { t }$ 较小， $w$ 值较大，通过扩大动态因子扩大了蜂群的搜索范围，算法能够跳出局部搜索，保证解的多样性并避免错过最优解；在蜂群搜索的后期阶段， $t$ 较大的 $w$ 值较小，缩小了动态因子，加强引领蜂在最优解附近进行局部搜索的能力，这样就提高了算法的动态搜索性能。

# 3.3引入柯西因子

蜂群开采同一个蜜源的次数达到开采极限时，引领蜂变为侦查蜂随机产生一个新解，随机性强，扰动性较差[12]。本文将柯西分布引入侦查蜂的搜索公式中来提高算法的扰动能力，帮助蜂群跳出局部搜索。柯西分布（Cauchy）概率密度函数为

$$
f ( x ) = \frac { 1 } { \pi } \frac { t } { t + x ^ { 2 } } \qquad - \infty < x < + \infty
$$

由式（13）可知，当 $t$ 的取值为1时， $f ( x )$ 就是标准柯西分布Cauthy(0,1)，此柯西随机变量生成的函数为 $\beta = \tan [ ( \alpha - 1 / 2 ) \pi ]$ ，其中 $\alpha$ 是[0,1]上的随机变量。

图1中，分别给出了标准正态分布与标准柯西分布的概率密度函数，可知柯西分布两侧趋于零的速度要比标准正态分布的速度慢，可以避免算法陷入早熟，更容易跳出局部极值；标准柯西分布的峰值比标准正态分布的峰值要小，可以提高扰动能力。

![](images/6d7adc630da779bb329b5135e79322535e95a191405714b0218f533fde0bda41.jpg)  
图1标准正态分布与柯西分布  
Fig.1Standard normal distribution and Cauchy distribution 侦查蜂的搜索公式变为

$$
X _ { i j } = X _ { j \operatorname* { m i n } } + \operatorname { C a u c h y } ( 0 , 1 ) ( X _ { j \operatorname* { m a x } } - X _ { j \operatorname* { m i n } } )
$$

# 3.4动态柯西蜂群算法性能分析

为了测试柯西动态蜂群算法的性能，本文选取4种基准测试函数Rastrigin，Sphere，Ackley,Griewank，对动态柯西蜂群算法与标准的蜂群算法

进行比较测试。这四种函数的数学模型及变量的取值如下。

（1）Rastrigin函数

$$
f ( x ) = \sum _ { i = 1 } ^ { n } [ x _ { i } ^ { 2 } - 1 0 \cos { ( 2 \pi x _ { i } ) } + 1 0 ]
$$

式中， $x _ { i } \in [ - 5 . 1 2 , 5 . 1 2 ]$ ， $i = 1 , 2$ ， $x _ { i }$ 在(0,0)处取得最小值0。

(2）Sphere 函数

$$
f ( x ) = \sum _ { i = 1 } ^ { n } x _ { i } ^ { 2 }
$$

式中， $x _ { i } \in [ - 5 . 1 2 , 5 . 1 2 ]$ ， $i = 1 , 2$ ， $x _ { i }$ 在(0,0)处取得最小值 $0$ 。

(3）Ackley函数

$$
f ( \boldsymbol { x } ) = \mathrm { e } + 2 0 - 2 0 \mathrm { e } ^ { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \cos { ( 2 \pi x _ { i } ) } } - 2 0 \mathrm { e } ^ { - \frac { 1 } { 5 } \sqrt { \frac { 1 } { n } x _ { i } ^ { 2 } } }
$$

式中， $x _ { i } \in [ - 1 0 , 1 0 ]$ ， $i = 1 , 2$ ， $x _ { i }$ 在(0,0)处取得最小值0。

(4）Griewank 函数

$$
f ( x ) = 1 + \sum _ { i = 1 } ^ { n } { \frac { x _ { i } ^ { 2 } } { 4 0 0 0 } } - \prod _ { i = 1 } ^ { n } \cos \left( { \frac { x _ { i } } { \sqrt { i } } } \right)
$$

式中， $x _ { i } \in [ - 6 0 0 , 6 0 0 ]$ ， $i = 1 , 2$ ， $x _ { i }$ 在(0,0)处取得最小值0。

本文中仿真实验参数的设定：蜜源总数为50，迭代次数为200次，开采极限为15，最大惯性权值为2.0，最小惯性权值为0.4，每组实验独立运行50次。仿真曲线如图2～图5所示。

![](images/0c1b52cda6f912bcbc8fb4e68e4de43b65688f959f16920b767d255181ee145d.jpg)  
图2两种算法在Rastrigin 测试函数上仿真曲线 Fig.2Two algorithms simulate the curve on the Rastrigin test function

![](images/f88c597902af5da4aff814f28f197e086634cab2a6a13a101b49ac60eeaf528c.jpg)  
图3两种算法在Sphere 测试函数上的仿真曲线

![](images/9b4ba3572803a77c134b3bc397c1db0046f2cd288caf59736664d190802e6168.jpg)  
Fig.3Simulation of two algorithms on Sphere test function   
图4两种算法在Ackley 测试函数上的仿真曲线

![](images/f2893bda85d2eccfba0cbf6a7296a65698195d40638440f95a67e95b5e3d91bb.jpg)  
Tab.4Simulation of two algorithms on Ackley test function   
图5两种算法在Griewank 测试函数上仿真曲线 Fig.5Two algorithms simulate the curve on the Griewank test function

由图2～图5和表1可以看出，经过四种测试函数的运算，通过DCABC算法运算得到的最优值和平均值都比经ABC算法得到的结果小，而且收敛时间更短。因此DCABC的寻优效果更好，更有利于提高对SVM参数惩罚参数 $C$ 和核函数参数γ的寻优效率。

Tab.1 Results ofABC and DCABC algorithm in the test function simulation   

<html><body><table><tr><td rowspan="2">测试函数</td><td colspan="3">DCABC</td><td colspan="3">ABC</td></tr><tr><td>最优值</td><td>平均值</td><td>收敛时间/s</td><td>最优值</td><td>平均值</td><td>收敛时间/s</td></tr><tr><td>Rastrigin</td><td>0</td><td>0.008 1</td><td>4.231 4</td><td>0.000 4</td><td>0.0091</td><td>5.523 1</td></tr><tr><td>Sphere</td><td>5.001 2×10-7</td><td>0.053 2</td><td>4.136 9</td><td>2.256 4×106</td><td>0.062 3</td><td>5.813 7</td></tr><tr><td>Ackley</td><td>1.846 5 × 10-12</td><td>0.002 75</td><td>5.196 4</td><td>1.156 4× 10-1</td><td>0.0052</td><td>6.315 9</td></tr><tr><td>Griewank</td><td>0</td><td>2.584 1 × 10-5</td><td>5.169 8</td><td>0.000 4</td><td>4.621 4 × 10-5</td><td>6.412 8</td></tr></table></body></html>

# 4 DCABC算法优化SVM参数对风机叶 片故障诊断

# 4.1利用DCABC算法对SVM参数寻优

具体步骤如下：

（1）算法初始化。设置开采极限lim、最大迭代次数 $N$ ，需优化惩罚参数 $C$ 和核函数参数γ，故维数 $D = 2$ 。随机产生初始解，将 $C$ 和γ初值写入SVM模型，并对训练样本进行训练分类，准确率为DCABC的适度值，记录好初始解并算出每个解对应的适应度值。

(2）根据式 (12)，引领蜂随机搜索新的蜜源并计算其适度值，如果搜索到的新的适度值较初始解产生的适度值好，则用新解代替初始解；否则当前解仍为初始解。(3）计算所有的解对应的适度值，运用式（8)计算对应的概率值。(4）跟随蜂跟随对应的引领蜂并依据轮盘赌选择策略进行采蜜，再由式（12）搜索新解并计算其对应的适度值，若较历史最优值更好，则用新解代替初始解；否则当前解仍为最优解。(5）若蜜源适度值经过多次迭代后仍然没有达到最优，引领蜂变为侦查蜂并依据式（14）搜索新解。(6）算法进行一次运算后记录当前为止最优解。（7）若迭代次数达到最大或者满足误差条件，则将目前为止的最优解输出，蜂群寻优完成，否则回到步骤 (2)，再次进行寻优运算。

# 4.2利用DCABC-SVM对风力发电机叶片故障诊断

采集样本特征数据，进行归一化处理后，初始化DCABC 算法参数，利用DCABC算法对 $C$ 和y寻优得到最优的参数，再利用样本数据并结合寻优参数训练SVM模型，最后利用实验样本数据对模型进行诊断检验，诊断流程如图6所示。

![](images/a22628df1f0597f6c7c7a9b240c9114ce1682d98372831d856eeaa67eb5cfdd2.jpg)  
图6利用DCABC-SVM对风机叶片故障诊断流程 Fig.6The process ofusing DCABC-SVM wind turbines blades fault diagnosis

# 5 实验分析

# 5.1实验数据的选取和量化

本实验选取南方某临海风电场中运行的1.25MW风力发电机作为试验平台，风机叶片出现故障时，叶片前缘和后缘的温度、湿度、光亮度和音量都会发生不同程度的变化，测量并记录这些数据，去除噪声后提取特征值，并将它们归一化处理，形成数据集，其中每个状态数据集分配见表2，部分测试样本的特征参数见表3，作为支持向量机模型的输入，通过识别正常状态与叶片蒙皮开裂、前缘开裂和后缘开裂下不同的特征进行故障识别与诊断。

表1ABC与DCABC算法在测试函数上仿真的统计结果  
表2风机叶片实验样本数量表  
Tab.2Size table of wind turbines blades experimental sample   

<html><body><table><tr><td></td><td>正常</td><td>前缘开裂</td><td>后缘开裂</td><td>蒙皮开裂</td></tr><tr><td>训练样本</td><td>60</td><td>40</td><td>40</td><td>40</td></tr><tr><td>实验样本</td><td>25</td><td>20</td><td>20</td><td>20</td></tr><tr><td>总数据</td><td>85</td><td>60</td><td>60</td><td>60</td></tr></table></body></html>

Tab.3Training samples of the part of wind turbines blades   

<html><body><table><tr><td>故障类型</td><td>前缘温度xi</td><td>后缘温度x2</td><td>前缘湿度x</td><td>后缘湿度x4</td><td>前缘光亮度 xs</td><td>后缘光亮度x6</td><td>前缘音量x7</td><td>后缘音量xg</td></tr><tr><td rowspan="3">正常</td><td>0.75</td><td>0.84</td><td>2.03</td><td>2.12</td><td>0.51</td><td>0.53</td><td>0.87</td><td>0.84</td></tr><tr><td>0.67</td><td>0.94</td><td>2.04</td><td>2.24</td><td>0.61</td><td>0.58</td><td>0.78</td><td>0.91</td></tr><tr><td>0.45</td><td>1.06</td><td>0.48</td><td>0.45</td><td>1.04</td><td>1.05</td><td>2.73</td><td>2.58</td></tr><tr><td>蒙皮 开裂</td><td>0.52</td><td>1.06</td><td>0.59</td><td>0.52</td><td>1.05</td><td>1.04</td><td>2.75</td><td>2.55</td></tr><tr><td>前缘</td><td>1.72</td><td>0.99</td><td>1.89</td><td>0.88</td><td>2.43</td><td>1.65</td><td>2.98</td><td>1.14</td></tr><tr><td>开裂</td><td>1.66</td><td>1.05</td><td>1.83</td><td>1.08</td><td>2.27</td><td>1.62</td><td>2.92</td><td>1.16</td></tr><tr><td>后缘</td><td>0.92</td><td>1.80</td><td>1.19</td><td>1.97</td><td>1.66</td><td>2.36</td><td>1.06</td><td>2.68</td></tr><tr><td>开裂</td><td>1.04</td><td>1.76</td><td>1.08</td><td>1.87</td><td>1.52</td><td>2.25</td><td>1.09</td><td>2.88</td></tr></table></body></html>

# 5.2风机叶片样本的训练和诊断

使用训练样本对支持向量机训练后，将测试样本输入到训练好的支持向量机中进行验证。正常代码为1，蒙皮开裂故障代码为2，前缘开裂故障代码为3，后缘故障代码为4，分别利用ABC算法与DCABC算法优化的SVM对风机叶片进行故障诊断，诊断分别结果如图7和图8所示。

![](images/6cb2909eed9aefa9754e127b7e13dfcf306fcec9cd0c0f7908b14b1144e68d6c.jpg)  
图7基于ABC优化的SVM对风机叶片诊断结果 Fig.7Diagnosis results of wind turbines blades based on ABC optimized SVM

![](images/a7951a0110373131ecdf0009a89d9d6bed0d34b252723dcd8ffc0dd83c1bab7d.jpg)  
图8基于DCABC优化的SVM对风机叶片诊断结果 Fig.8Diagnosis results of wind turbines blades based on DCABC optimized SVM

两种方法诊断结果见表4，相对于ABC-SVM,DCABC-SVM的故障诊断率提高了 $2 . 3 6 \%$ ，主要是由于采用DCABC算法寻优过程中避免了算法陷入局部搜索，调高了算法的扰动能力，找到了更优的参数，构建了更加准确的SVM故障识别模型，而且缩短了训练时间，减少了支持向量机的数量，加快了分类的速度，对比结果表明了本文提出的DCABC-SVM故障诊断模型更具备有效性。

表3风机叶片部分训练样本  
表4两种方法诊断结果统计表  
Tab.4 Statistical tables of two methods of diagnosis   

<html><body><table><tr><td>方法</td><td>C</td><td>Y</td><td>训练时间/s</td><td>准确率(%)</td></tr><tr><td>ABC-SVM</td><td>13.254</td><td>0.231</td><td>50.40</td><td>95.29</td></tr><tr><td>DCABC-SVM</td><td>11.241</td><td>0.104</td><td>37.54</td><td>97.65</td></tr></table></body></html>

# 6 结论

本文提出一种基于DCABC-SVM的风机叶片故障诊断的方法。在ABC算法中引入动态因子在算法初期扩大搜索范围，接近最优解附近时缩小搜索范围；并引入柯西算子提高算法的扰动能力，帮助蜂群跳出局部搜索，提高了蜂群寻优效率。利用这种DCABC算法对SVM的惩罚因子 $C$ 和核函数参数γ寻优得到最优参数，采集风力发电机叶片特征参数得到训练样本，训练后得到SVM模型。利用测试样本对DCABC-SVM进行验证后表明，诊断结果较传统的ABC-SVM提高了诊断的准确率，具有一定的工程意义。

# 参考文献

[1] 于占龙．风力发电机状态监测与故障诊断技术综述[J]．工程技术：文摘版，2016，16(10)：297-297.Yu Zhanlong.A review of condition monitoring

and fault diagnosis techniques for wind turbine [J]. Engineering Technology: Digest, 2016,16(10): 297- 297.   
[2] 薛浩然，张珂珩，李斌，等．基于布谷鸟算法和 支持向量机的变压器故障诊断[J]．电力系统保护 与控制，2015(8)：8-13. Xue Haoran,Zhang Keheng,Li Bin,et al. Transformer fault diagnosis based on cuckoo algorithm and support vector machine[J]. Power System Protection and Control, 2015(8): 8-13.   
[3] 饶金根．基于谐波小波和支持向量机的风电叶片 损伤识别研究[D]．兰州：兰州交通大学，2014.   
[4] Karaboga D,Basturk B.A powerful and efficient algorithm for numerical function optimization: artificial bee colony(ABC)algorithm[J]. Journal of Global Optimization,2007, 39(3): 459-471.   
[5] Hu W, Yu Y, Zhang S.A hybrid artificial bee colony algorithm forparameter identification of uncertain fractional-order chaotic systems[J]. Nonlinear Dynamics,2015,82(3): 1-16.   
[6] 吴国诚，范良忠．人工蜂群优化支持向量机的电 气故障诊断方法研究[J]．电网与清洁能源，2016, 32(7): 87-91. Wu Guocheng,Fan Liangzhong. Study on electrical fault diagnosis of artificial bee colony optimization support vector machine[J]. Power System and Clean Energy,2016,32(7): 87-91.   
[7] 叶东毅，陈昭炯．最小属性约简问题的一个有效的 组合人工蜂群算法[J]．电子学报，2015，43(5)： 1014-1020. Ye Dongyi, Chen Zhaojiong. An effective combination of artificial bee colony algorithm for minimal attribute reduction[J].Acta Electronica Sinica,2015,43(5):1014-1020.   
[8] 许建华，张学工．经典线性算法的非线性核形式 [J]．控制与决策，2006，21(1)：1-6. Xu Jianhua, Zhang Xuegong. Nonlinear kernel form of classical linear algorithm[J]. Control & Decision, 2006, 21(1): 1-6.   
[9] 顾桂梅，胡让，李远远．果蝇优化算法融合SVM 的风机叶片损伤识别研究[J]．自动化仪表，2016, 37(2): 9-12. Gu Guimei, Hu Rang,Li Yuanyuan.Description of damage identification of blower vane based on drosophila optimization algorithm combined with SVM[J]. Process Automation Instrumentation, 2016, 37 (2): 9-12.   
[10] 肖剑，周建中，张孝远，等．基于Levy-ABC 优化 SVM的水电机组故障诊断方法[J]．振动、测试与 诊断，2013，33(5)：839-844. Xiao Jian, Zhou Jianzhong, Zhang Xiaoyuan, et al.A fault diagnosis method based on Levy-ABC SVM for hydroelectric units[J]. Journal of Vibration, Testing and Diagnosis, 2013,33(5): 839-844.   
[11] 张银雪，田学民，曹玉苹．改进搜索策略的人工 蜂群算法[J]．计算机应用，2012，32(12)：3326- 3330. Zhang Yinxue, Tian Xuemin, Cao Yuping. Artificial bee colony algorithm with improved search strategy [J]. Journal of Computer Applications,2012,32(12): 3326-3330.   
[12]张鑫，陈国初，公维祥，等．自适应柯西蜂群及其 收敛性分析[J]．计算机系统应用，2015，24(12)： 118-124. Zhang Xin, Chen Guochu, Gong Weixiang. An adaptive cauchy bee colony and its convergence analysis[J]. Computer Systems & Applications,2015, 24(12): 118-124.