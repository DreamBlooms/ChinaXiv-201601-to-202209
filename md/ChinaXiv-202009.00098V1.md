# 基于基因水平多样性的微种群教与学优化算法

王筱薇1，范勤勤1,2′，王维莉1

(1．上海海事大学 物流研究中心，上海 201306;2.上海交通大学大学系统控制与信息处理教育部重点实验室，上海200240)

摘要：种群多样性对微种群教与学优化算法的性能有极大影响。为进一步提高其性能，提出一种基于基因水平多样性的微种群教与学优化算法(MTLBO-GLD)。该算法从基因水平上对种群多样性进行监测；并使用混沌搜索和余弦函数分阶段进行扰动以增加种群多样性。所提算法与8种元启发式算法(4 种微种群算法和4种非微种群算法)在13个测试函数上进行性能比较。实验结果表明，MTLBO-GLD的整体性能要显著好于其他8种所比较的算法。

关键词：教与学优化；微种群；混沌搜索；种群多样性 中图分类号：TP doi:10.19734/j.issn.1001-3695.2020.03.0050

Micro-population teaching-learning-based optimization based on gene level diversity

Wang Xiaowei1, Fan Qinqin1, 2t, Wang Weilil (1.LogisticsResearchCenter,hanghaiMaritimeUniversityhanghai2l3o6,China;2.KeyLaboratoryofSysteControl &InformationProcessing,MinistryofEducationofChina,ShanghaiJiao Tong University,Shanghai 20024,China)

Abstract: The performance of micro-population Teaching-learning-basedoptimization(TLBO)algorithmis mainlydepended on the population diversity.Inorder to further improve its performance,this paper proposed a Micro-populationteachinglearning-based optimization based on gene level diversity(MTLBO-GLD).In the proposed algorithm,the population diversity is monitoredatthegenetic level,and thechaos searchandthecosine functionareusedtoimprovethepopulation diversity indifferent evolutionarystages.The proposedalgorithmiscompared with eight meta-heuristic algorithms (including four micro-population algorithms and four non-micro-populationalgorithms)on13 test functions.The experimental results show thatthe overall performance of the MTLBO-GLD is significantly beter than that of compared algorithms.

Key words:teaching-learning-based optimization; micro population; Chaotic search; population diversity

# 0 引言

传统数学方法在求解各类复杂优化问题时存在诸多不足；因此，各类智能优化算法被不断提出。如，遗传算法(geneticalgorithm，GA)[1]、蚁群算法(ant colony optimization，ACO)[2]、粒子群算法(particle swarm optimization，PSO)[3]、差分进化算法(differential evolution，DE)[4]等。

教与学优化算法(teaching-learning-based optimization，简称 TLBO)是Rao 等人[5.6]于 2011 年提出的一种新型智能优化算法。其原理主要是模拟学生学习的过程，该算法分为两个阶段：a)学生在课堂上听老师上课的学习过程；b)学生课下的自我学习过程。由于TLBO算法实现简单、便于理解，且其控制参数较少，故受到众多学者的重视和研究；并用其解决了许多实际问题。例如机械优化设计[6]、热交换器优化[7]、热电制冷器优化[8]、平面钢框架的设计优化[9]等。

一般来说，TLBO 算法及其他智能优化算法都会使用较大的种群规模来保持种群多样性以提高搜索性能；但在计算资源受限情况下(如内存小)，较大的种群规模会影响算法运行。为解决以上问题，基于微种群的智能优化算法被不断提出。例如，Ren等[10]提出一种小种群的差分进化算法(Differential evolution using smaller population，DESP)。该算法不仅提出一种新的DE变异策略用于提高全局搜索能力，还对扰动强度进行自适应调整。实验表明，与DE 算法相比，

DESP算法可以较快寻到最优解。Salehinejad等[1]提出一种基于向量化随机突变因子的差分进化算法(micro-differentialevolution with vectorized random mutation factor，MDEVM)。该算法将突变因子向量随机化，即给种群中的每个个体随机分配一个差分突变因子 $F$ ，从而增加种群的多样性。实验结果表明，与DE 算法相比，MDEVM算法在搜索过程中能够较好地增强种群的多样性，同时具有较高的勘探能力。Brown等[12]提出一种使用小种群的自适应差分进化算法(adaptivedifferential evolution with a small population, $\mu \mathrm { J } \mathrm { A D E } )$ ；该算法的改进是基于Rcr-JADE 算法[13]。所提算法使用一种新的变异算子以提高小种群的全局搜索能力，并可以加速算法收敛速度。此外， $\mu \mathrm { J } \mathrm { A D E }$ 还使用隔代更新 $\mu c _ { R }$ 和 $\mu _ { F }$ 的方式来实现DE 变异因子 $F$ 和交叉因子 $C R$ 的自适应调整，从而减少在使用小种群时 $F$ 和 $C R$ 值迅速减小的发生。研究表明，尽管$\mu$ JADE算法使用了小种群，但从所选测试函数来看，其表现比一些使用常规种群规模的DE 算法更好。Salehinejad 等[14]提出一种基于反向学习的集成差分进化算法(opposition-based ensemble micro-differential evolution，OEMDE)。该算法不仅使用反向学习生成与当前个体(候选解)相反的个体以提高算法的全局搜索能力；在每一代，各个个体还随机选择一个突变策略以提高种群的多样性。结果表明，与其他MicroDE 算法相比，OEMDE算法具有更好的性能。

虽然众多学者对微种群优化算法进行了研究，但是他们的研究大都基于个体水平的种群多样性。在实际种群进化过程中，如果某个或某几个决策变量过早收敛，那么就会对个体的进化造成极大影响；进而影响整个种群进化。基于文献[15]和[16]的研究，本研究提出一种基于基因水平多样性的微种群教与学优化算法(micro-population teaching-learningbased optimization based on gene level diversity,MTLBO-GLD)在所提算法中，首先利用基因水平检测方法来对微种群算法的种群多样性进行维度检测，然后使用混沌搜索和余弦函数对收敛变量进行分阶段扰动以增强其多样性。最后，将所提算法与其他8种算法在13个测试函数上进行性能比较。实验结果表明，MTLBO-GLD不仅具有较快的收敛速度，还具有较强全局搜索能力。

# 1 相关算法介绍

# 1.1标准教与学优化算法

标准TLBO算法[56主要包含两个阶段，老师上课的教学过程和学生课余的自学过程。具体算法描述如下。

# 1.1.1教学阶段

在教学阶段，将适应度值最好的个体(设为 $X _ { T } )$ 作为这个阶段的教师；教师希望通过教学过程提高所有学生的平均成绩(设为 $\boldsymbol { X } _ { M } )$ 并尽量靠近他自己的水平。该阶段个体的更新公式如下：

$$
X _ { i , n e w } = X _ { i , \mathrm { o l d } } + r \cdot \left( X _ { T } - T _ { F } \cdot X _ { M } \right)
$$

其中 $X _ { i , n e w }$ 是经过“教”阶段后第 $i$ 个学生的新位置。 $T _ { \mathrm { F } } =$ round $_ { 1 + r a n d ( 0 , 1 ) ) }$ ，为教学因子，取1或2， $\boldsymbol { r }$ 为[0,1]范围内的均匀随机数.若 $X _ { i , n e w }$ 的适应度值优于 $X _ { i , o l d }$ ，则更新个体；否则，不更新。

# 1.1.2学习阶段

在学习阶段中，学习者主要通过课下与同学交流来提高自己的成绩。个体的更新公式如下：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { X _ { p , \mathrm { n e w } } = X _ { p , \mathrm { o l d } } + r \cdot \left( X _ { p } - X _ { l } \right) } & { \mathrm { i f } ~ f \left( X _ { p } \right) < f \left( X _ { l } \right) } \\ { X _ { p , \mathrm { n e w } } = X _ { p , \mathrm { o l d } } + r \cdot \left( X _ { l } - X _ { p } \right) } & { \mathrm { i f } ~ f \left( X _ { l } \right) < f \left( X _ { p } \right) } \end{array} \right. } \end{array}
$$

其中， $p { \neq } l , \ p , l \ \in ( 1 , 2 , . . . , N P )$ ： $f ( X )$ 为适应度函数值。若$X _ { p , \mathrm { n e w } }$ 的适应度值优于 $X _ { p , \mathrm { o l d } }$ ，则更新个体；否则，不更新。1.1.3标准TLBO算法的实现步骤

a）初始化种群，设定维度 $D$ 、种群规模 $N P$ 和最大评价  
次数。b)教学阶段：班级中的每个学员根据式(1)进行更新个  
体，并进行个体选择。c）学习阶段：通过式(2)对个体进行更新，并进行个体选择。d）判定程序是否达到终止条件，若没有达到，则转至步  
驟b)；否则，继续执行。e）输出最优解。

# 1.2混沌映射

混沌现象是非线性动力系统的固有特性，在没有任何一种随机性因子的作用下也能够发生类随机的运动行为，这种运动行为没有周期的特性不具有收敛特征并且对于初始化的取值有很强的依赖性[17]。混沌模型还有一个重要的特征是遍历性，所以用来对个体进行随机次数的扰动使其跳出局部最优[18]。借鉴文献[18]中的混沌扰动策略，本研究将利用Logistics搜索策略来对种群进行基因水平上的扰动，公式如下：

$$
x _ { n e w } = x _ { o l d } \cdot \mu \cdot ( 1 - x _ { o l d } )
$$

其中， $x _ { n e w }$ 是经过混沌映射之后产生的新变量; $\mu$ 为控制参数，取值范围在[0,4]之间，且当 $\scriptstyle { \mu = 4 }$ 时，Logistics 映射是属于完全混沌的状态。

# 1.3余弦扰动

余弦函数具有比较强的振荡性，且在 $( 0 , \pi / 2$ 区间中值

呈递减趋势。因此，它不仅适用于种群的局部扰动，而且能使算法的进化后期注重局部搜索。根据文献[19]的研究，本文使用该余弦因子来对个体维度进行扰动，式子如下：

$$
x _ { j 1 , G } = 2 \cdot \cos \left( \frac { \pi } { 2 } \cdot \frac { F E S } { M a x F E S } \right) \cdot N ( 0 . 5 , 0 . 2 ) \cdot x _ { j b e s t , G }
$$

其中，MaxFES为设定的最大迭代数； $N$ 表示正态分布函数；FES为当前迭代数。 $x _ { j b e s t , G }$ 为第 $g$ 代中多样性最好的维度;$x _ { j 1 , G }$ 为第 $g$ 代中第 $j 1$ 个维度扰动后更新的值， $j I \in ( 1 , 2 , . . . , D ) .$

# 2 基于基因水平多样性的微种群教与学优化算法

对于微种群算法来说，保证种群多样性十分关键。由于微种群算法的种群规模较小，导致种群多样性会随着环境的选择急剧下降，这对基于种群进化的元启发式算法来讲十分不利。同时，已有研究对于种群多样性的评判大都基于个体水平，如果种群中的个体出现某一维或某几维收敛的情况，就会对整个个体的进化带来显著影响。因此，基于文献[15]和[16]的研究，本研究将对种群进行基因水平上的监测，并分别使用两种不同的方法来提高种群多样性。

# 2.1基因水平多样性监测

基于文献[15]，本文采用方差来监测每个变量的多样性，计算第 $g$ 代个体变量的第 $j$ 个维度均值和标准差公式如下：

$$
m _ { j , G } = \frac { 1 } { N P } \sum _ { i = 1 } ^ { N P } x _ { i , j , G }
$$

$$
s t d _ { j , G } = \sqrt { \frac { 1 } { N P } \sum _ { i = 1 } ^ { N P } \bigl ( x _ { i , j , G } - m _ { j , G } \bigr ) }
$$

一般情况下，若第 $j$ 个维度的多样性比较差，则其 $s t d _ { j , G }$ 值也就较小。从理论上来说，当一个维度的 $s t d _ { j , G }$ 值等于0时，表示该维度的多样性完全散失。正常情况下，元启发式算法在算法的搜索过程中种群多样性是越来越差的。即，每个维度的 $s t d _ { j , G }$ 值都是一个逐渐变小的趋势。因此，所提算法先从基因水平上来判断每个变量的多样性。需要指出的是，考虑到如果每代多样性检测会造成计算资源的浪费，而且也没必要。因此，本研究采取每5代的间隔来进行多样化检测(代数的敏感性分析的实验结果见3.4.2节)。

# 2.2多样性的提高

研究表明 $s t d _ { j , G }$ 的值降为0需要很长的时间[15]，故本研究用 $o j , G$ 来识别种群多样性开始变小的时刻，式子如下：

$$
o _ { j , G } = \left( 1 - \frac { D \cdot F E S } { M a x F E S } \right) \cdot a _ { j , G }
$$

其中

$$
a _ { j , G } = \operatorname* { m a x } \left( \mu _ { j , G } , 1 - \mu _ { j , G } \right)
$$

$$
\mu _ { j , G } = \frac { m _ { j , G } - l o w _ { j , G } } { u p _ { j , G } - m _ { j , G } }
$$

$$
l o w _ { j , G } = \operatorname* { m i n } \left( m _ { j , G } , \mathbf { x } _ { l o w , j } \right)
$$

$$
u p _ { j , G } = \operatorname* { m a x } \left( m _ { j , G } , \mathbf { x } _ { \mathrm { u p } , j } \right)
$$

其中， $x _ { l o w , j }$ 和 $x _ { u p , j }$ 分别表示第 $j$ 维度预设的上下界。

由式(7)可以知道 $o _ { j , G }$ 的值会随着迭代次数的增加慢慢变小。一般情况下，算法种群的多样性也会在迭代过程种慢慢变差，所以本研究用 $o j , G$ 来判断种群各维度的多样性。从式(8)\~(11)可以看出， $a _ { j , G }$ 主要为 $o _ { j , G }$ 提供了一些该维度的信息，以便引导 $o _ { j , G }$ 更好的判断该维度的多样性。

此外，本文给 $o j , G$ 设置了一个下限值。一般而言，在算法进化后期，种群的多样性很小，但考虑到算法在进化后期会强调局部搜索，故不再对种群采取扰动措施，直到算法收敛到最优。在本研究中， $o _ { j , G }$ 的最小值设为 $1 0 ^ { - 5 }$ (敏感性分析的实验结果见3.4.3节)。

如果监测到某个变量的多样性丢失，那么采用以下方法对其进行扰动来提升多样性。其步骤如下：

a)若 $1 0 ^ { - 3 } < s t d _ { j , G } < o _ { j , G }$ ,则利用式(3)对该维度进行混沌扰动;b)若 $o _ { j , G } \leqslant 1 0 ^ { - 3 }$ 且 $s t d _ { j , G } < o _ { j , G }$ ,则利用式(4)对该维度进行余弦扰动。

# 2.3MTLBO-GLD算法的实现步骤

a)初始化：设定微种群规模 $N P$ 、维度 $D$ 、最大评价次数；初始化种群；

b)教学阶段：根据式(1)对个体进行更新，并对个体进行选择;c）学习阶段：根据式(2)对个体进行更新，并对个体进行选择;d)每隔5代根据式(6)对种群中的每个变量进行多样性  
检测操作，并计算出每个维度的标准差，然后根据式(7)计算  
该维度相应的 $o j , G$ 值，将两值进行比较；e）根据步骤d）进行分阶段扰动：若 $1 0 ^ { - 3 } < s t d _ { j , G } < o _ { j , G }$ ，  
则利用式(3)对该维度进行混沌扰动；若 $o _ { j , G } \leqslant 1 0 ^ { - 3 }$ 且 $s t d _ { j , G } <$   
$o _ { j , G }$ ，则利用式(4)对该维度进行余弦扰动;f)完成步骤d)和e）后，对个体进行选择;g）判定算法是否达到设定的终止条件，若结论是肯定，  
则继续执行；否则，转回步骤b）；h)输出结果。

# 3 仿真测试

为测试所提算法性能，本文选取文献[20]中的13个测试函数，并将测试函数的维度设为30。

将所提算法分别与 TLBO[5,6]、DESP[10]、MDEVM[11]、$\mu \mathrm { J } \mathrm { A D E } ^ { [ 1 2 ] }$ 、Rcr-JADE- $\cdot \mathbf { s } 4 ^ { [ 1 3 ] }$ 、FSADE[21]、TLBO-CSWL[22]以及OBL- $\mu \mathrm { T L B O } ^ { [ 2 3 ] }$ 等算法进行对比。针对各种算法的种群规模会在以下部分进行说明。所有算法均在13个测试函数上独立运行30次，所得结果取30次的平均值。同时，为保证所得结论的可靠性，仿真结果采用Friedman[24]，Bonferroni-$\mathrm { D u n n } ^ { [ 2 5 ] }$ ，Holm和Hochberg[26]检验进行统计分析。显著性水平设为 $5 \%$ 。表中最优结果加粗表示。

# 3.1与微种群算法的比较

在这部分中，所提算法跟 MDEVM、DESP、 $\mu \mathrm { J } \mathrm { A D E }$ 及OBL- $\scriptstyle { \mathrm { \cdot } \mathrm { \ " ~ } \mathrm { \ " ~ } \mathrm { \ L B O } 4 }$ 种微种群算法进行比较。所有算法的种群规模均设定为8，最大适应度函数评价次数为300万。对于13个测试函数的求解精度有以下规定，函数 $f _ { 7 }$ 的求解精度为 $1 0 ^ { - 2 }$ 其余12个测试函数的求解精度为 $1 0 ^ { - 8 }$ 若算法在达到设定的终止条件时，所求解还未到达到规定的精度，则表示该算法在此函数上求解失败，结果以“"来表示。仿真结果如表1所示。

由表1可知，MTLBO-GLD算法对于所有测试函数均能在终止条件范围内寻到最优解，且在各个测试函数上的求解结果都显著好于所比较算法，尤其在fi、f、f、f4、f、fio、$f _ { 1 1 }$ 这几个测试函数上寻优性能非常好。其主要原因在于，对于MDEVM、DESP及 $\mu \mathrm { J } \mathrm { A D E }$ 这三个算法来说，虽然DE 算法的全局搜索能力要好于TLBO算法，但所提算法通过从基因水平上对种群进行监测，并采用混沌与余弦函数分阶段来对种群进行扰动。对于OBL $\cdot \mathrm { \textmu { T L B O } }$ 算法来说，虽然该算法使用反向学习来提高其全局搜索能力，但并未从基因水平上对种群多样性进行监测。因此，相较于MDEVM、DESP、$\mu \mathrm { J } \mathrm { A D E }$ 及OBL $\mathrm { \cdot \mu T L B O \ 4 }$ 种微种群算法，所提算法在该函数测试集上的表现更好。

此外，本文还使用非参数统计分析方法来对几种算法所求解的平均值进行深入分析，结果见图1和表2。从图1中可知MTLBO-GLD算法的寻优效率是最高的，比其中表现较好的OBL $\mathtt { \cdot \mu T L B O }$ 算法略胜一筹，更是显著高于其他几个比较算法。另外，从表2也可以看出所提算法的寻优效率要显著优于所比较的几个算法。

综上所述，MTLBO-GLD算法在基因水平上对种群多样性进行监控，能够得到更高的求解精度。

表1微种群算法的实验结果

Tab.1Experimental results of Micro-population algorithms   

<html><body><table><tr><td>函数</td><td></td><td>MDEVM</td><td>DESP</td><td>μJADE</td><td>OBL-μTLBO</td><td>MTLBO-GLD</td></tr><tr><td rowspan="2">fi</td><td>平均值</td><td>2.8E+04</td><td>1.9E+04</td><td>2.2E+04</td><td>2.6E+02</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>3.3E+03</td><td>8.0E+02</td><td>7.8E+02</td><td>8.9E+00</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>3.1E+04</td><td></td><td>3.7E+04</td><td>3.9E+02</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>4.7E+03</td><td>-</td><td>1.2E+03</td><td>1.1E+01</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>准方差</td><td>1.4E+05</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>1.7E+05</td><td>4.3E+02</td><td>0.0E+0</td></tr><tr><td rowspan="2">f4</td><td>标准方</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>2.2+05</td><td>4.3E+02</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>2.3E+06</td><td></td><td>2.1E+05</td><td>1.8E+05</td><td>2.5E+01</td></tr><tr><td>标准方差</td><td>4.0E+05</td><td></td><td>5.5E+04</td><td>4.3E+04</td><td>1.2E+00</td></tr><tr><td rowspan="2">f</td><td>标准方差</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>1.3E+04</td><td>__</td><td>1.2+04</td><td>1.2E+02</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>8.9E+05</td><td></td><td>2.3E+05</td><td>2.1E+03</td><td>2.5E-06</td></tr><tr><td>标准方差</td><td>7.1E+05</td><td></td><td>1.6E+05</td><td>8.1E+02</td><td>1.8E-06</td></tr><tr><td rowspan="2">f</td><td>标准方差</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>1.0E+03</td><td>1.9E+05</td><td>3.4E+03</td></tr><tr><td rowspan="2">f</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>标准方差</td><td></td><td></td><td>1.2E+05</td><td>2.7E+02</td><td>0.0E+00</td></tr><tr><td rowspan="2">f10</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>标准方差</td><td></td><td></td><td>3.8E+04</td><td>3.9E+02</td><td>0.0E+00</td></tr><tr><td rowspan="2">fi</td><td>平均值</td><td>2.6E+04</td><td>3.1E+04</td><td>4.6E+04</td><td>2.8E+02</td><td></td></tr><tr><td>标准方差</td><td>3.1E+03</td><td>1.7E+03</td><td>3.7E+04</td><td></td><td>0.0E+00</td></tr><tr><td rowspan="2">f12</td><td>平均值</td><td>6.6E+04</td><td>1.8E+06</td><td>3.8E+04</td><td>1.3E+01 4.1E+03</td><td>0.0E+00 6.9E-05</td></tr><tr><td>标准方差</td><td>6.5E+04</td><td>0.0E+00</td><td>7.5E+03</td><td>7.8E+02</td><td>1.9E-04</td></tr><tr><td rowspan="2">f13</td><td>平均值</td><td>7.0E+04</td><td></td><td>3.2E+04</td><td>2.5E+05</td><td>1.1E-02</td></tr><tr><td>标准方差</td><td>6.4E+04</td><td></td><td>1.8E+04</td><td>4.8E+05</td><td>1.2E-02</td></tr></table></body></html>

![](images/a93ada48e99eeb956fc8f6d9eb21d09d02e01e46badca1fa4c128171d4ff1a5c.jpg)  
图1Friedman 测试在微种群算法所得排序结果 Fig.1Ranking obtained by Friedman's test for micro-population algorithms 表2Bonferroni-Dunn、Holm 和 Hochberg 在微种群算法上所得 $p$ 值 Tab.2 $P$ -values obtained by Bonferroni-Dunn's,Holm's,and

<html><body><table><tr><td colspan="5">Hochberg's procedures for Micro-population algorithms</td></tr><tr><td>MTLBO-GLDvs.</td><td>Z Unadjusted p</td><td>Bonferroni-Dunn p</td><td>Holm p</td><td>Hochberg p</td></tr><tr><td>DESP</td><td>5.77</td><td>8.04E-09 3.22E-08</td><td></td><td>3.22E-083.22E-08</td></tr><tr><td>MDEVM</td><td>4.78 1.79E-06</td><td>7.18E-06</td><td>5.38E-06</td><td>5.38E-06</td></tr><tr><td>μJADE</td><td>3.53 4.08E-04</td><td>1.63E-03</td><td>8.16E-04</td><td>8.16E-04</td></tr><tr><td>OBL-μTLBO</td><td>2.05 4.07E-02</td><td>1.63E-01</td><td>4.07E-02</td><td>4.07E-02</td></tr></table></body></html>

# 3.2与非微种群算法的比较

在这部分中，所提算法跟FSADE、Rcr-JADE-s4、TLBO和TLBO-CSWL这4种非微种群算法的性能进行比较。期望求解精度同3.1部分。四个算法的种群规模设定

依次为50、100、30和40，算法参数设置均与文献[12]一致。结果见表3。

表3所提算法与非微种群算法的结果  
Tab.3Experimental results of the proposed algorithm and non-Micro-population algorithms   

<html><body><table><tr><td rowspan="2">函数</td><td></td><td>FSADE</td><td>Rcr-JADE-s4</td><td>TLBO</td><td>TLBO-CSWL</td><td>MTLBO-GLD</td></tr><tr><td></td><td>(NP=50)</td><td>(NP=100)</td><td>(NP=30)</td><td>(NP=40)</td><td>(NP=8)</td></tr><tr><td rowspan="2">fi</td><td>平均值</td><td>3.5E+04</td><td>2.1E+04</td><td>4.3E+03</td><td>1.9E+03</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>5.3E+02</td><td>4.9E+02</td><td>9.1E+02</td><td>4.2E+01</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>4.5E+04</td><td>3.3E+04</td><td>7.6E+03</td><td>2.8E+03</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>5.7E+02</td><td>7.6E+02</td><td>1.3E+02</td><td>4.6E+01</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>2.6E+06</td><td>6.7E+04</td><td>1.7E+04</td><td>2.9E+03</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>4.8E+05</td><td>3.6E+03</td><td>8.6E+02</td><td>1.6E+02</td><td>0.0E+00</td></tr><tr><td rowspan="2">f4</td><td>平均值</td><td>2.2E+05</td><td>1.0E+05</td><td>7.2E+03</td><td>3.2E+03</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>4.2E+03</td><td>3.5E+04</td><td>1.5E+02</td><td>5.1E+01</td><td>0.0E+00</td></tr><tr><td rowspan="2">fs</td><td>平均值</td><td>2.8E+06</td><td>7.8E+04</td><td></td><td>4.1E+05</td><td>2.5E+01</td></tr><tr><td>标准方差</td><td>6.1E+04</td><td>2.7E+03</td><td>-</td><td>5.8E+04</td><td>1.2E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>1.3E+04</td><td>8.8E+03</td><td>1.7E+03</td><td>1.1E+03</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>4.7E+02</td><td>3.6E+02</td><td>2.2E+02</td><td>2.1E+02</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>标准方差</td><td>1.1E+05</td><td>2.2E+04</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>__</td><td>2.2E+04</td><td>2.5-06</td></tr><tr><td rowspan="2">fs</td><td>方差</td><td>1.8E+04</td><td>7.0E+04</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>__</td><td>4.5+03</td><td>3.4E+03</td></tr><tr><td rowspan="2">f</td><td>方差</td><td>4.9E+04</td><td>9.3E+04</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>__</td><td>7.9E+03</td><td>0.0E+00</td></tr><tr><td rowspan="2">fi0</td><td>平均值</td><td>4.8E+04</td><td>3.1E+04</td><td>2.3E+04</td><td>2.8E+03</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>5.0E+02</td><td>6.4E+02</td><td>1.3E+02</td><td>4.4E+01</td><td>0.0E+00</td></tr><tr><td rowspan="2">fi</td><td>平均值</td><td>3.9E+04</td><td>2.2E+04</td><td>4.1E+03</td><td>2.1E+03</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>3.7E+03</td><td>6.4E+02</td><td>3.9E+02</td><td>5.8E+02</td><td>0.0E+00</td></tr><tr><td rowspan="2">f12</td><td>平均值</td><td>4.0E+04</td><td>1.9E+04</td><td></td><td>5.0E+04</td><td>6.9E-05</td></tr><tr><td>标准方差</td><td>1.0E+03</td><td>5.5E+02</td><td></td><td>2.5E+03</td><td>1.9E-04</td></tr><tr><td rowspan="2">f13</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>方差</td><td>4.1E+04</td><td>2.1E+04</td><td></td><td>3.1E+05</td><td>1.1E-02</td></tr></table></body></html>

从表3中可以看出，MTLBO-GLD算法在13个测试函数上所得结果均好于其他几个非微种群算法。因此，所提算法虽然使用的是较小规模的种群，但它仍然表现出非常好的寻优性能。原因主要有以下两点：首先，所提算法从基因水平上对种群的多样性进行监测，从而可以从种群中提取更多有效信息；其次，采取了分阶段对种群进行扰动，从而可以保持算法种群的多样性。因此，算法的寻优性能得到了很大的提升。

为使实验结论更加可靠，还使用非参数的统计方法来对所有算法的均值进行分析。统计分析结果见图2和表4。由图2可知，与使用常规规模种群的算法相比，MTLBO-GLD的寻优性能排名第一。从表4可以看出，MTLBO-GLD算法的求解性能要显著性好于所比较的所有非微种群算法。

综上所述，所提算法虽然为微种群算法，但其寻优性能并不比常规种群规模的算法差，反而更优。这恰好证明从基因水平上对种群进行监控是一种十分有效的方法。

![](images/156ccb5db60987d90b0c9c3530b40dd09ed76209842c260866471690c6007174.jpg)  
图2Friedman 测试在MTLBO-GLD 和非微种群算法上所得排序结果 Fig.2Ranking obtained by Friedman's test forMTLBO-GLD and non-micro-population algorithms

3.3MTLBO-GLD 与 OBL- $\mu$ TLBO、TLBO-CSWL的比较

为了进一步验证在资源受限情况下的MTLBO-GLD 算法性能，这里本文将对所提算法与前面两部分中表现较好的

OBL- $\mu$ TLBO和TLBO-CSWL进行性能比较。与前面部分不同的是，在本实验中，最大的适应度函数评价次数设为30,000。同时，OBL- $\mu$ TLBO和TLBO-CSWL的种群规模分别设为8和40。所得结果见表5。从表5可以看出MTLBO-GLD算法在 $f 1 \setminus f 2 \setminus f 3 \setminus f 4 \setminus f 5 \setminus f 6 \setminus f 1 0 \setminus f 1 1 \setminus f 1 3$ 上得到的解比TLBO-CSWL算法的解要好很多。而TLBO-CSWL只在f&这个函数上要显著好于所提算法。结果足以表明所提算法的性能是好于TLBO-CSWL算法。对于OBL- $\mathrm { \cdot \textmu T L B O }$ ，两个算法在这些测试函数上得到的平均结果总体上来说差不多，但所提算法在每个测试函数上表现的比OBL- $\mathtt { \cdot \ " { u } T L B O }$ 略胜一筹。因此，MTLBO-GLD不仅具有较快的收敛速度，还能够降低计算成本，同时也展现了较强的全局搜索能力。

本部分还使用非参数统计分析方法来对三种算法的平均值进行分析，其结果见表6。由表6可知MTLBO-GLD算法的整体性能优于 TLBO-CSWL 算法。另外，虽然 MTLBO-GLD、TLBO-CSWL、OBL $\cdot \mathrm { \textmu { T L B O } }$ 的性能在统计学意义上不存在明显的差异，但是从表6中的结果可知，MTLBO-GLD的整体性能仍稍微优于OBL- $\mathrm { \cdot \textmu T L B O }$ 和 TLBO-CSWL 的。

表 4Bonferroni-Dunn、Holm 和 Hochberg在 MTLBO-GLD 和非微种群算法上所得 $p$ 值

<html><body><table><tr><td>MTLBO-GLD vs.</td><td>Z</td><td></td><td>Unadjusted p Bonferroni-Dunn p</td><td>Holm p</td><td>Hochberg p</td></tr><tr><td>FSADE</td><td>5.0854</td><td>3.67E-07</td><td>1.47E-06</td><td>1.47E-06</td><td>1.47E-06</td></tr><tr><td>TLBO</td><td>4.7133</td><td>2.44E-06</td><td>9.75E-06</td><td>7.31E-06</td><td>7.31E-06</td></tr><tr><td>Rcr-JADE-s4</td><td>3.7831</td><td>1.55E-04</td><td>6.20E-04</td><td>3.10E-04 3.10E-04</td><td></td></tr><tr><td>TLBO-CSWL</td><td>2.0225</td><td>4.97E-02</td><td>0.2182</td><td>4.97E-02</td><td>4.97E-02</td></tr><tr><td>TLBO-CSWL</td><td>2.5427</td><td>1.10E-02</td><td>4.40E-02</td><td>1.10E-02 1.10E-02</td><td></td></tr></table></body></html>

表5所有比较算法在30维函数上所得结果

Tab.4 $P$ -values obtained by Bonferroni-Dunn's,Holm's,and Hochberg's procedures for MTLBO-GLD and non-micro-population algorithms   
Tab.5Experimental results of all compared algorithms on 3OD functions   

<html><body><table><tr><td>函数</td><td></td><td>TLBO-CSWL (NP=40)</td><td>OBL-μTLBO (NP=8)</td><td>MTLBO-GLD</td></tr><tr><td rowspan="2">fi</td><td>平均值</td><td>4.0E-223</td><td>0.0E+00</td><td>(NP=8) 0.0E+00</td></tr><tr><td>标准方差</td><td>0.0E+00</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>9.8E-141</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>6.5E-140</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>2.8E-221</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>0.0E+00</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td rowspan="2">f4</td><td>平均值</td><td>5.5E-224</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>0.0E+00</td><td>0.0E+00</td><td></td></tr><tr><td rowspan="2">fs</td><td>平均值</td><td>2.8E+01</td><td>2.8E+01</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>4.1E-01</td><td>2.78E-01</td><td>2.6E+01</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>9.2E-16</td><td>0.0E+00</td><td>3.5E-01 0.0E+00</td></tr><tr><td>标准方差</td><td>1.5E-15</td><td></td><td></td></tr><tr><td rowspan="2">f</td><td>平均值</td><td>0.0E+00</td><td>0.0E+00 4.4E-05</td><td>0.0E+00</td></tr><tr><td>标准方差</td><td>0.0E+00</td><td></td><td>2.5E-04</td></tr><tr><td rowspan="2">f</td><td>平均值</td><td></td><td>3.2E-05</td><td>1.4E-04</td></tr><tr><td>标准方差</td><td>0.0E+00</td><td>6.4E+03</td><td>4.0E+03</td></tr><tr><td rowspan="2">f</td><td></td><td>0.0E+00</td><td>1.3E+03</td><td>1.5E+03</td></tr><tr><td>平均值</td><td>0.0E+00</td><td>0.0E+00</td><td>9.7E-01</td></tr><tr><td rowspan="2">fio</td><td>标准方差</td><td>0.0E+00</td><td>0.0E+00</td><td>2.5E+00</td></tr><tr><td>平均值</td><td>4.9E+03</td><td>2.1E-16</td><td>0.0E+00</td></tr><tr><td rowspan="2">fi</td><td>标准方差</td><td>1.1E+03</td><td>8.5E-16</td><td>0.0E+00</td></tr><tr><td>平均值</td><td>0.0E+00</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td rowspan="2"></td><td>标准方差</td><td>0.0E+00</td><td>0.0E+00</td><td>0.0E+00</td></tr><tr><td>平均值</td><td>3.2E-219</td><td>8.3E-02</td><td>1.9E-04</td></tr><tr><td rowspan="2">f12</td><td>标准方差</td><td>0.0E+00</td><td>9.7E-02</td><td>2.8E-04</td></tr><tr><td>平均值</td><td>2.9E+01</td><td>2.6E+00</td><td>3.1E-03</td></tr><tr><td rowspan="2">f13</td><td></td><td></td><td></td><td></td></tr><tr><td>标准方差</td><td>6.30E-02</td><td>5.3E-01</td><td>6.2E-03</td></tr></table></body></html>

表6所有比较算法的Bonferroni-Dunn、Holm以及Hochberg 检验的 $p$ 值 Tab.6 $P$ -Values obtained by Bonferroni-Dunn's,Holm's,and Hochberg's procedures on experimental results with all comparison algorithms   

<html><body><table><tr><td>MTLBO-GLD vs. Z</td><td>Unadjusted p</td><td>Bonferroni-Dunn p</td><td>Holm p</td><td>Hochberg p</td></tr><tr><td>TLBO-CSWL 1.86</td><td>6.24E-02</td><td>1.25E-01</td><td>1.25E-01</td><td>1.25E-01</td></tr><tr><td>OBL-μTLBO 0.49</td><td>6.24E-01</td><td>1.00E+00</td><td>6.24E-01</td><td>6.24E-01</td></tr></table></body></html>

# 3.4实验分析

# 3.4.1混沌和余弦两种扰动的结果分析

一般而言，算法在前期应偏重于全局搜索，在后期应偏重于局部搜索[27]。在本研究中，所提算法采用混沌搜索和余弦扰动两种方法进行分阶段增强种群多样性。为验证混沌搜索和余弦扰动两种方法的特点，本部分给出两种方法在二维空间中的个体位置变化图。这里以8个粒子为例，粒子迭代60次的位置变化图如图3和4，从图3和4中可以看出，混沌搜索的全局搜索能力要好于余弦函数。

![](images/4cc0893bc6889e0f3d1f29356d019ff32ca49cc92cafd566035eb42acdb5823d.jpg)  
图3混沌搜索

![](images/8a0a9a5fdd67a560180d41bd9df4af0b4b971831578770de7dee36a72aef0bf1.jpg)  
Fig.3 Chaotic search   
图4余弦扰动  
Fig.4Cosine perturbation

# 3.4.2间隔代数值敏感性分析

本部分对间隔的代数值进行敏感性分析。本实验中，种群规模设置为8，最大的适应度函数评价次数设为30.000，MTLBO-GLD 算法独立运行30 次；并选取13个测试函数。间隔代数分别设定为0、5、10、15和20，并使用非参数的统计方法对平均值进行排序分析。各个参数的排序结果如图5所示。由图5可知，当间隔代数值取5时，所提算法的整体性能表现最佳；所以间隔的代数值设为5。

# 3.4.3oj,G值敏感性分析

该部分对 $o j , G$ 的下限值进行敏感性分析，实验设置与3.4.2 相同。 $o _ { j , G }$ 分别设定为 $1 0 ^ { - 1 }$ 、 $1 0 ^ { - 2 }$ 、 $1 0 ^ { - 3 }$ 、 $1 0 ^ { - 4 }$ 和 $1 0 ^ { - 5 }$ ，不同参数下的排序结果见图6。由图6可知，在 $o _ { j , G }$ 的下限设为$1 0 ^ { - 5 }$ 时，所提算法的整体性能最佳。因此，在所提算法中，$o j , G$ 的下限值设为 $1 0 ^ { - 5 }$ 。

![](images/01b33a18446ab19ac4d0d1d6a6a52030d513514004e191332791811da32d1ae7.jpg)  
图5Friedman 测试在不同代数间隔下所得排序结果 Fig.5Ranking obtained by Friedman's test for different iteration intervals

![](images/acc54581f06f3a5df4bb3888b273aa3a70216523c5f26304c815387b2abf5fbf.jpg)  
图6Friedman 测试在oj,G取不同下限值下所得排序结果 Fig.6Ranking obtained byFriedman's test for oj,G under different lower limits

# 4 结束语

为平衡微种群教与学优化算法的全局和局部搜索能力，本文提出一种基于基因水平多样性的微种群教与学(MTLBO-GLD)算法。在该算法中，首先从基因水平上对种群进行监测，以防止某一维或某几维过早收敛而对整个种群搜索带来不利影响；然后使用混沌搜索和余弦函数分阶段实现扰动来实现种群多样性。所提算法跟 $\mu \mathrm { J } \mathrm { A D E }$ 、DESP、MDEVM、OBL $\mathrm { \cdot \textmu T L B O }$ 等微种群算法和FSADE、Rcr-JADE-s4、TLBO、TLBO-CSWL等非微种群算法进行性能比较。实验结果表明MTLBO-GLD算法的整体性能要优于所有比较算法。

# 参考文献：

[1]Goldberg DE.Genetic algorithms in search,optimization,and machine learning,addison-wesley,reading,ma,1989[J].NNSchraudolph and J, 1989,3 (1) .   
[2]Dorigo M,Maniezzo V, Colorni A. The ant system:optimization by a colony of cooperating agents [J].IEEE Trans on Systems,Man，and Cybernetics B,1996,26 (1): 29-41.   
[3]Eberhart R,Kennedy J.A new optimizer using particle swarm theory [C]//MHS'95.Proc of the 6th International Symposium on Micro Machine and Human Science.IEEE,1995:39-43.   
[4]Efren MM,Miranda-Varela ME,RubiDCG.Differential evolution in constrained numerical optimization:an empirical study[J].Information sciences,2010,180 (22):4223-4262.   
[5]Rao R V,Savsani V J,Vakharia D P. Teaching-learning-based optimization:an optimization method for continuous non-linear large scale problems [J].Information Sciences,2012,183(1):1-15.   
[6]Rao R V,Savsani V J,Vakharia D P. Teaching-learning-based optimization:a novel method for constrained mechanical design optimization problems [J].Computer-aided Design,2011,43 (3):303- 315.   
[7]Rao R V,Patel V.Multi-objective optimization of heat exchangers using a modified teaching-learning-based optimization algorithm [J].Applied Mathematical Modeling,2013,37(3):1147-1162.   
[8]Huang Runqing,Xi Lifeng,Li Xinglin,et al.Residual life predictions for ball bearings based on self-organizing map and back propagation applcations to signal processing [J]. IEEE Irans on Signal Processing, 2002,50(2): 345-356.   
[10] Ren Xuan, Chen Zhizhao,Ma Zhen.Differential evolution using smaller population [C]// Proc of the 2th International Conference on Machine Learning and Computing. IEEE,2010: 76-80.   
[11] Salehinejad H,Rahnamayan S,Tizhoosh HR,etal.Micro-diferential evolution with vectorized random mutation factor [Cl// Proc of IEEE Congress on Evolutionary Computation (CEC).IEEE,2014: 2055-2062.   
[12] Brown C,Jin Yaochu,Leach M,et al. $\mu \mathrm { J } \mathrm { A D E }$ :adaptive differential evolution with a small population [J]. Soft Computing,2016,20 (10): 4111-4120.   
[13] Gong Wenyin, Cai Zhihua, Wang Yang. Repairing the crossover rate in adaptive diferential evolution [J].Applied Soft Computing Journal, 2014,15 (2): 149-168.   
[14] Salehinejad H，Rahnamayan S,Tizhoosh H R.Opposition-based ensemble micro-differential evolution [C]// Proc of IEEE Symposium Series on Computational Intellgence (SSCI) . IEEE,2017: 1-8.   
[15] Yang Ming,Li Changhe,Cai Zhihua,et al.Differential evolution with auto-enhanced population diversity[J]. IEEE Trans on Cybernetics,2014, 45 (2): 302.   
[16]Fan Qinqin, Yan Xuefeng.Self-adaptive differential evolution algorithm with discrete mutation control parameters [J].Expert Systems with Applications,2015,42 (3): 1551-1572.   
[17]孟红记，郑鹏，梅国晖，等．基于混沌序列的粒子群优化算法[J]. 控制与决策，2006,21(3):263-266.(Meng Hongji,Zheng Peng,Mei Guohui,et al.Aparticle swarm optimization algorithm based on chaotic sequence [J].Control and Decision,2006,21 (2):263-266.)   
[18]唐娜，张公让，李磊，等．自适应混沌搜索的双粒子群优化算法[J]. 计算机工程与设计，2016,37(9):2421-2428.(Tang Na,Zhang Gongrang,Li Lei, et al.Double particle swarm optimization algorithm of self-adaption and chaos search [J]. Computer Engineering and Design, 2016,37 (9): 2421-2428.)   
[19]黄宝清，李俊兴，宋春宁，等．基于余弦控制因子和多项式变异的鲸 鱼优化算法[J].控制与决策.(2018-11-13)[2020-03-18].http://doi: 10.13195/j.kzyjc.2018.0463.(Huang Baoqing,Li Junxing，Song Chunning,et al.Whale optimization algorithm based on cosine control factor and polynomial mutation [J]. Control and Decision. (2o18-11-13) [200-03-18].htp://doi:10.13195/j. kzyjc.2018.0463.)   
[20] Yao Xin, Liu Yong.Evolutionary programming made faster[J]. IEEE Trans on Evolutionary Computation,1999,3 (2):82-102.   
[21] Sharma H, Shrivastava P,Bansal JC,et al.Fitness based self-adaptive differential evolution [M]// Nature inspired cooperative strategies for optimization (NICsO 2013）. Springer international publishing, 2014: 71-84.   
[22] 柳缔西子，范勤勤，胡志华．基于混沌搜索和权重学习的教与学优 化算法及其应用[J]．智能系统学报,2018,13(05):818-828.(Lin Dixizi,Fan Qinqin,Hu Zhihua.Teaching-learning-based optimization algorithm based on chaotic search and weighted learning and its application [J]. CAAI Trans on Intelligent Systems,2018,13 (05):818- 828.）   
[23]范勤勤，柳缔西子，王筱薇，等．基于反向学习的微种群教与学优化 算法及其应用[J]．郑州大学学报．(2019-12-27）[2020-03-18]. http://doi:10.13705/j.issn.1671-6833.2020.01.020.(Fan Qinqin,Liu Dixizi,Wang Xiaowei,et al.Opposition-based learning teachinglearning-based optimization algorithm with a micro population and its application [J].Journal of Zhenzhou University.(2019-12-27) [2020-03- 18]. http://doi:10.13705/j.issn.1671-6833.2020.01.020.)   
[24] Milton F.The use of ranks to avoid the assumption of normality implicit in the analysis of variance [J].Journal of the American Statistical Association,1937,34 (200):109-109.   
[25] Dunn O J.Multiple comparisons among means [J].Journal of the American Statistical Association,1961,56 (293): 52-64.   
[26] Salvador Garcia,Molina D,Lozano M,et al.A study on the use of nonparametric tests for analyzing the evolutionary algorithms'behaviour: a case study on the CEC'2oo5 Special Session on Real Parameter Optimization [J].Journal of Heuristics,20o9,15 (6):617.   
[27] Fan Qinqin,Yan Xuefeng,Xue Yu.Prior knowledge guided differential evolution [J]. Soft Computing,2017,21 (22): 6841-6858.