# 基于AMSFLA的配电网故障定位研究

朱亚伟，孙岩洲，赵来军，韦延方(河南理工大学 电气工程与自动化学院，河南 焦作 454000)

摘要：随着电网的不断发展，其网络架构趋于复杂，电网线路发生故障的概率也随之增加，目前配电网故障指示器作为对线路故障检测的主要工具，仍然具有故障识别率低，易发生误动的缺点。为了解决故障指示器目前存在的问题，针对其现状进行分析，构建了配电网故障定位模型，提出一种基于AMSFLA(自适应变异混合蛙跳算法)的故障指示器定位方法，并结合IEEE33节点配电网模型来进行仿真验证。结果表明该算法能够在故障信号畸变的情况下，准确定位故障区域，为运维工作人员故障排查提供帮助。

关键词：配电网；故障指示器；混合蛙跳算法；故障定位 中图分类号：TP306.3 doi:10.3969/j.issn.1001-3695.2018.03.0241

# Research on fault location using adaptive mutation shufled frog leaping algorithm in distribution network

Zhu Yawei, Sun Yanzhou, Zhao Laijun, Wei Yanfang (SchoolofElectrical Engineering&Automation Henan Polytechnic University,Jiaozuo 4540oo,China)

Abstract:Withdevelopingof power grid,the network structure becomesmorecomplexandthe fault probability increases. Thefaultindicatorbecomesusefultoolindistributionnetwork,butthefaultrecognitionrateisstillow.Inordertosolethe problems existing inthefaultindicator,thispaperconstructedafaultlocation model indistribution network byanalyzingof fault indicator,and presentedafaultindicatorpositioning methodbasedonadaptive mutation shufled frog leapingalgorithm. Usingthesimulationof IEEE33 node distribution network model,theresults show that thealgorithmcanaccurate fault location area when sampled signal is distortion.Sothe algorithmcan provide helpforthe operation and maintenance work.

Key words: distribution network ;fault indicator; shuffled frog leaping algorithm; fault location

# 0 引言

随着社会的飞速发展，人类对于电能的需求越来越大，电网的规模也愈加复杂，当电网中发生故障时，迅速的识别故障并定位故障区域对于保障电网运行稳定，减少电力企业及用户经济损失具有重要意义。目前在配电网中，故障定位的方法有很多包括"S"注入法、中电阻法、行波法、故障指示器法。相对于另外三种方法，基于故障指示器的配电网故障定位技术成熟、成本低，已经在电网中得到广泛应用，但是目前故障指示器的定位效率、精确度及故障率有待于进一步提高改善。

故障指示器是通过安装在配电网的检测装置对线路电流进行实时监测，当检测到故障电流时，就通过通信系统将其指示状态传递给控制中心，从而便于调度运维人员进行故障定位。目前基于故障指示器的配电网故障定位方法主要有：统一矩阵法、概率估计法和人工智能法。

统一矩阵法具有简明直观、速度快的优点，但是由于电网运行环境复杂，会造成故障指示器的精度下降，会发生误动及漏报信号等现象，这就使得故障指示器的可靠性降低[1,2]。基于概率估计的方法在处理故障信息不全的情况下具有一定效果，但是是根据故障信号数量确定的故障概率并不一定正确反映现实故障情况[3]。基于人工智能算法的故障定位能够取得较为满意的结果，但是传统的遗传算法存在求解效率低，收敛速度慢的特点，且采用智能算法时由于算法本身的特性容易造成局部收敛，不利于故障定位[4.5]。

本文根据对现有的智能算法的分析，构建了配电网模型，针对目前传统智能算法收敛速度慢、易陷入局部寻优的缺点，提出了一种基于AMSFLA（自适应混合蛙跳算法）的故障指示器的故障定位算法，并通过仿真来验证所提故障定位算法的效果。

# 1 混合蛙跳算法及改进

混合蛙跳算法（SFLA)，SFLA是2003年提出的一种结合了基因算法和粒子群优化算法的全新进化算法。该算法具有概念简单、易于实现、运行速度快等特点。在故障指示器的故障定位中，通过混合蛙跳算法来进行故障定位，能够有效的解决采用遗传算法等智能算法的时出现的早熟收敛问题，实现对故障信息的快速判断，实现精准故障定位[6-9]。

# 1.1混合蛙跳算法基本原理

混合蛙跳算法的思想是模拟受限池塘中青蛙觅食时的信息共享的仿生优化算法，算法生成初始蛙群后，根据适应值对蛙群进行降序排列，并记录整个蛙群中的最优个体。然后将整个蛙群划分为不同组，记录每个组内最差个体和最优个体，局部搜索策略利用蛙跳更新公式更新最差个体，若更新后个体更优，则取代原最差个体；否则，以整个种群的最优个体取代。更新到局部迭代次数后，蛙群重新混洗进行排序，再次划分组，重复局部搜索策略，直到达到全局迭代次数后算法停止。

混合蛙跳算法一般包括以下四个部分，分别是初始种群的构造、子种群的划分、局部搜索策略和全局的信息交换。以下对于每个具体步骤给出分析。

# 1）初始种群构造

设有P只青蛙，将P只青蛙（ $X _ { 1 } , X _ { 2 } , \cdots , X _ { P }$ ）作为初始种群,种群内的第i只青蛙也就是第i个解用 $X _ { \mathrm { i } } ^ { 1 } , X _ { \mathrm { i } } ^ { 2 } , \cdots , X _ { \mathrm { i } } ^ { 3 }$ 来表示，S是问题的维数。用适应度 $f _ { i }$ 来表示每只青蛙在种群中当前的位置，并按照适应度的大小将青蛙从优至劣排序。

# 2）子种群划分

首先，计算种群内每只青蛙的适应度，按照适应度的大小对种群内的青蛙个体进行降序排列，记录种群内具有最优适应度值的个体为 $X _ { z }$ 。然后把 $\mathrm { ~ \bf ~ P ~ }$ 只青蛙种群划分成m 个子种群,每个子种群内包含的青蛙个数为 $\mathfrak { n }$ ，按照排好的顺序将第1只青蛙放入第1组，第2只青蛙放入第2组，第 $\mathrm { ~ m ~ }$ 只青蛙放入第$\mathbf { m }$ 组，第 $\mathrm { m } { + } 1$ 只放入第1组，以此类推直到分配完毕。在每个种群内，适应度最好的个体记为 $X _ { b }$ ，适应度最差的个体记为$X _ { \scriptscriptstyle { w } }$

# 3）局部搜索策略

局部搜索是混合蛙跳算法中最重要的一步，在进行局部搜索时会对子种群内适应度最差的个体 $X _ { \scriptscriptstyle w }$ 进行更新，更新的策略公式如下：

$$
D _ { i } = r a n d ( ) \cdot ( X _ { b } - X _ { w } )
$$

$$
X _ { \scriptscriptstyle w } = X _ { \scriptscriptstyle w } + D _ { \scriptscriptstyle i }
$$

其中:i表示子种群内第只青蛙， $i = 1 , 2 , \cdots m$ ， $D _ { i }$ 表示青蛙的更新步长， $- D _ { \mathrm { m a x } } \leq D _ { i } \leq D _ { \mathrm { m a x } }$ ，rand(是0和1之间的随机数， $D _ { \mathrm { m a x } }$ 表示了青蛙允许移动的最大步长。种群内的最差解通过式（1）来更新自己的位置。如果更新后位置比更新前的位置更好，则用更新后的解来替换更新前的解，否则用全局最优解$X _ { z }$ 来代替式(2)中的子种群内部最优解 $X _ { b }$ ，重新计算更新后的位置。如果此时更新后的位置仍没有原来 $X _ { \scriptscriptstyle w }$ 的位置好，则随机生成一个解替换原来的最差解。在指定的内部迭代次数内重复进行上述操作完成一轮子种群的局部搜索。

# 4）全局的信息交换

当完成了子种群的内部更新后，将各个子种群合并成一个新的种群，按照适应度进行降序排列，重新执行子种群划分和子种群的局部搜索策略，如此反复直到找到最优解为止。

经典混合蛙跳算法具有原理简单、参数少和全局寻优的优点，但是存在着初始种群不均匀、移动部长适应性较差、局部搜索效率低等问题，本节对经典混合蛙跳算法引入自适应变异因子，提出一种自适应混合蛙跳算法用于解决存在的问题。

# 1.2自适应变异混合蛙跳算法

混合蛙跳算法虽然结合了基因算法和粒子群算法的特点，克服了传统仿生算法的一些不足，但是仍然存在搜索速度缓慢、无法保证算法收敛的问题。本文通过在经典混合蛙跳算法的局部搜索中加入自适应局部搜索因子和levy变异因子，使得算法能够有效的克服经典蛙跳算法易陷入局部寻优的问题[10\~12]，同时克服了遗传算法和蚁群算法易早熟收敛的问题。本文算法相对于粒子群算法提高了精度，改善了易发散的缺点，解决了免疫算法和人工鱼群算法容易失真以及收敛速度慢的问题；相对于模拟退火算法兼顾了局部和全局寻优。自适应变异因子的引入相对于其他仿生算法进一步提高仿生算法的寻优速度和搜索性能。

# 1）自适应局部搜索因子

经典混合蛙跳算法应用于故障定位能够实现故障信息的快速判断，但是配电网故障定位往往需要实时性和准确性，仅提高局部搜索效率不足以应对发生多点故障的情况，由于系统较复杂，采用经典混合蛙跳算法往往会陷入局部寻优，不能够及时发现配电网中存在的所有故障信息。为此借鉴文献[5],在算法的局部搜索策略中引入自适应局部搜索因子@，来协调算法的全局和局部搜索能力，使得算法能够快速发现配电网中全部故障点，实现精准故障定位。具体的方式是将式（1）更新为式(3)，

$$
D _ { i } = \infty D _ { i } ^ { ' } + r a n d ( ) \cdot ( X _ { { b } } - X _ { { w } } )
$$

其中： ${ \bf \omega } _ { \infty }$ 为惯性权重， $D _ { i } ^ { ' }$ 为前一个最差青蛙的移动步长。

在此处引入惯性权重 ${ \bf \omega } _ { \infty }$ ，利用线性递减调整 ${ \bf \omega } _ { \infty }$ ，能够当处于局部最优解附近时，避免陷入早熟，当处于全局最优解附近时，能够更加精确的进行搜索，提高算法收敛速度。在混合蛙跳算法中，进行自适应局部搜索时，随着全局迭代次数由大变小，首先应使 ${ \boldsymbol \omega }$ 处于较大值，有利于进行全局搜索，当接近最优解时，减小 $\boldsymbol { \mathfrak { o } }$ 的值，按式（4）来调整 ${ \boldsymbol \omega }$ 的值。

$$
\mathrm { \omega \omega \omega _ { \mathrm { m i n } } } + \mathrm { ( \omega \omega \omega _ { \mathrm { m a x } } } - \mathrm { \omega \omega \omega _ { \mathrm { m i n } } } ) \times \frac { G _ { \mathrm { m a x } } - c } { G _ { \mathrm { m a x } } }
$$

其中： $ { \omega _ { \mathrm { m i n } } } \cdot  { \omega _ { \mathrm { m a x } } }$ 分别表示惯性权重的最小值和最大值， $G _ { \mathrm { m a x } }$ 表示子种群间最大混合迭代次数的最大值， $c$ 表示当前子种群的总迭代次数。

# 2）Levy 变异因子

为了保障配电网故障定位时的局部寻优速度和准确度，在算法中引入基于Levy分布的Levy变异因子，Levy变异因子相比于高斯变异算子和柯西变异算子具有更好的变异步长，能够产生更强的扰动，Levy变异因子的引入能够大大增强算法的全局寻优能力，同时能够更好的跳出局部最优，避免算法出现早熟。Levy变异因子的引入，在自适应因子的基础上使算法应用于复杂配电网中的全局寻优能力增强，同时在故障信息出现畸变时仍能够准确的实现故障定位。具体的做法是将式（3）加入Levy变异算子更新为式（5)，

$$
D _ { i } = \Big [ \Theta D _ { i } ^ { ' } + r a n d ( ) \cdot ( X _ { \boldsymbol { b } } - X _ { \boldsymbol { w } } ) \Big ] \times L _ { j } ( t )
$$

$L _ { j } ( t )$ 为服从Levy 分布的随机数。

引入自适应变异因子后，混合蛙跳算法的局部更新策略如下：

$$
\begin{array} { l } { { D _ { i } = \Big [ \omega D _ { i } ^ { ' } + r a n d ( ) \cdot ( X _ { b } - X _ { w } ) \Big ] \times L _ { j } ( t ) ~ } } \\ { { \nonumber } } \\ { { X _ { w } = X _ { w } + D _ { i } } } \end{array}
$$

3）自适应变异混合蛙跳算法流程

针对经典混合蛙跳算法引入自适应变异算子后，对算法的编码，种群划分环节都不产生影响，只针对局部搜索策略进行更新，极大的改善了传统算法的迭代速度和全局寻优精度。自适应变异混合蛙跳算法的流程如图1所示。

![](images/37035c2bff8f10c5a9b66a177a8770f04437e7cd2869d8f659a4f20dfd7deb87.jpg)  
图1自适应变异混合蛙跳算法流程

# 2 基于AMSFLA的配电网故障指示器定位原理

基于AMSFLA的配电网故障指示器定位基本操作主要包括编码、评价函数构造、自适应混合蛙跳操作等。当进行配电网故障定位时，以开关(包括进线断路器、分段开关、联络开关)为节点，两相邻开关之间的配电部分为一个独立设备，每个节点配备一个故障指示器，通过故障指示器采集各节点的故障状态信息，经通信将故障信息传递给调度运行系统，从而判断配电网故障区间，为配电网故障寻址定位提供帮助[13:14]。

# 2.1编码问题

混合蛙跳算法是对状态信息组成的数字串进行处理，因此需要对故障指示器的状态信息进行二进制编码，配电网故障定位时，故障指示器检测到故障电流的有无和设备故障的有无都可用0-1进行编码，故障指示器有故障电流通过和设备故障状态用1表示，故障指示器没有检测到故障电流和设备正常状态用0表示。

# 2.2故障定位数学模型

1）评价函数构造

当配电网发生故障时，FI检测到故障电流，发出0或1的离散信号，针对故障指示器发出的信号来进行配电网故障定位的算法实际上就是一种全局寻优问题，为此，需要建立合适的评价函数来计算其适应度。本文所采用的评价函数如式（8)所示。

$$
F _ { i } = \sum _ { i = 1 } ^ { N } \bigl | I _ { j } - I _ { j } ^ { * } ( B _ { N } ) \bigr | - \omega \times \sum _ { i = 1 } ^ { N } \bigl | x ( i ) \bigr |
$$

其中： $F _ { i }$ 为第i个解的适应度， $I _ { { \sb j } }$ 为第j条线路的故障电流越限信号，取值为1时表示FI检测到故障电流，为0时表示没有检测到， $I _ { j } ^ { * } ( B _ { N } )$ 为第j条线路的故障电流越限信号的期望值函数， $\mathbf { N }$ 为配电网中所装设的故障指示器数量， ${ \bf \omega } _ { \odot }$ 为检测到故障电流的FI总数的权重， $x ( i )$ 为第i个故障指示器的工作状态，取值为1表示设备故障状态，取值为0表示设备正常状态，加入 $\mathfrak { \omega } \times \sum _ { i = 1 } ^ { N } \Bigl | x ( i ) \Bigr |$ 这一项是为了避免故障指示器发生故障时产生误判现象。

2）线路状态函数构造

线路状态函数用来确定确定配电网的状态信息，假设线路中有N个节点开关，将配电网划分为N个部分，每个部分的状态由其下游的故障指示器状态来决定，线路状态函数由下式表示：

$$
I _ { j } ^ { * } ( B _ { N } ) = \prod _ { i } x ( i )
$$

其中：II 表示逻辑或。

以十节点的单电源辐射状配电网为例来介绍线路故障函数的构造方法，如图2所示为一个十节点单电源辐射状配电网。1节点为断路器，2-10节点为分段开关，B1-10为10段配电线路，每个线路在节点后都装设有故障指示器，表1为各线路与所对应的故障指示器状态表。依据表中所列出的线路与设备对应状态，可以得到如下线路状态函数：

![](images/2715d5a1d8038bc82744b63bdb7d50a957dd49dd3f756f731316b4b63b0b49fb.jpg)  
图210节点单电源辐射状配电网结构简图

表1线路与其对应的故障指示器状态  

<html><body><table><tr><td>线路BN</td><td>B1</td><td>B2</td><td>B3</td><td>B4</td><td>B5</td><td>B6</td><td>B7</td><td>B8</td><td>B9</td><td>B10</td></tr><tr><td>FI状态</td><td>x(1)</td><td>x(2)</td><td>x(3)</td><td>x(4)</td><td>x(5)</td><td>x(6)</td><td>x(7)</td><td>x(8)</td><td>x(9)</td><td>x(10)</td></tr></table></body></html>

依次类推可以得到各个线路的状态函数，对应的故障指示器状态信息用1或0表示。

当完成了故障信息的确定就可以进行自适应变异混合蛙跳操作，根据最优解来确定故障点所在位置。

# 3 算例分析

本文以实际IEEE33节点配电系统为例，如图3所示，采用MATLAB编写自适应变异混合蛙跳算法程序对配电网故障信息进行计算，验证所提出的算法的应用可行性。

![](images/d84e1b9c0d889b1f4917d99e7e9ad57b018d620273ecb961ea0eeec84bbd267c.jpg)  
图3IEEE33节点结构简图

分别针对单点故障和多点故障进行测试，测试结果见表2。根据上表的测试结果可以看出，假设输入1故障区段为5，输入2的故障区段为5和25，输入3的故障区段为6、21和31，经自适应变异混合蛙跳操作后能够准确定位故障区段，对比输入1和输入4、输入2和输入5、输入3和输入6，可以发现，当出现故障信息畸变时，采用AMSFLA仍能够准确定位出故障区段，测试结果表明当配电网发生故障时，采用AMSFLA进行故障信息信息处理，能够为检修人员提供准确依据。

表2IEEE33节点故障测试结果  

<html><body><table><tr><td>端子</td><td>测试结果</td></tr><tr><td>输入1</td><td>111110000000000000000000000000000</td></tr><tr><td>输出1</td><td>000010000000000000000000000000000</td></tr><tr><td>输入2</td><td>111110000000000000000011100000000</td></tr></table></body></html>

<html><body><table><tr><td>输出2</td><td>000010000000000000000000100000000</td></tr><tr><td>输入3</td><td>111111000000000000111000011111100</td></tr><tr><td>输出3</td><td>000001000000000000001000000000100</td></tr><tr><td>输入4</td><td>111010000000000010000000000000000</td></tr><tr><td>输出4</td><td>000010000000000000000000000000000</td></tr><tr><td>输入5</td><td>101110000000010000000011100000000</td></tr><tr><td>输出5</td><td>000010000000000000000000100000000</td></tr><tr><td>输入6</td><td>111011000001000000111000011101100</td></tr><tr><td>输出6</td><td>000001000000000000001000000000100</td></tr></table></body></html>

为了验证所提自适应变异混合应用于配电网故障指示器故障定位的性能，使用MATLAB编写经典混合蛙跳算法、自适应遗传算法和自适应粒子群算法程序，以输入1为例来进行算法性能验证，将四种算法分别运行50次，可得到如表3所示

的结果。

表3算法性能测试  

<html><body><table><tr><td>算法</td><td>平均迭代次数</td><td>平均时间/ms</td></tr><tr><td>AMSFLA</td><td>32.50</td><td>3.57</td></tr><tr><td>SFLA</td><td>55.13</td><td>5.10</td></tr><tr><td>AGA</td><td>100.46</td><td>8.20</td></tr><tr><td>AMPSO</td><td>63.20</td><td>6.52</td></tr></table></body></html>

通过对表3进行对比可得，AMSFLA相对于AGA和AMPSO来说，迭代速度快，性能更好，对比AMSFLA和SFLA可得，在引入自适应变异算子之后，能够有效打的改善经典混合蛙跳算法中存在的易早熟问题，大大提高算法的全局寻优能力[15,16]。

# 4 结束语

本文在对经典混合蛙跳算法进行分析的基础上，针对算法中存在的易陷入局部寻优的缺点进行改进，引入惯性权重因子和Levy变异算子，将AMSFLA应用于配电网故障指示器故障定位上，并通过IEEE33节点系统进行算法性能验证，结果表明，在SFLA中引入自适应变异算子，能够提高算法的收敛速度，避免早熟，并且该算法应用于基于FI的故障定位时能够对单点和多点的故障区间进行有效定位，同时FI发生故障，故障信息产生畸变时，依然能够准确定位故障区段，为运行检修人员提供可靠的判断依据。

# 参考文献：

[1]黄佳乐，杨冠鲁．配电网故障区间定位的改进矩阵算法[J].电力系统 保护与控制,2014,42(11):41-45.(Huang Jiale,Yang Guanlu.Modified matrix algorithm for fault section location of distribution network [J]. Power System Protection and Control,2014,42(11):41-45.)

[2] 宋晓燕，孙岩洲，宋紫嫣，等．基于零序 PT二次侧注入信号的配电网 电容电流测量新方法[J]．电力系统保护与控制，2014,42(19):134-138. (Song Xiaoyan，Sun Yanzhou,Song Ziyan,et al.A new method of distribution network capacitive current measurement based on injecting signals into the secondary side of the zero sequence PT[J]. Power System Protection and Control,2014,42(19): 134-138.)

[3]郑国华，黄朵，张伟，等．基于最大概率的故障指示器故障判定方法 [J]．电力系统保护与控制，2017，45(16):105-110.(Zheng Guohua, Huang Duo,Zhang Wei,et al.A fault diagnosis method of fault indicator based on the Worst principle [J].Power System Protection and Control, 2017,45 (16): 105-110.)

[4]刘鹏程，李新利．基于多种群遗传算法的含分布式电源的配电网故障 区段定位算法[J].电力系统保护与控制，2016，44(2)：36-41.(Liu Pengcheng，Li Xinli．Fault section location of distribution network containing distributed generation based on the multiple-population genetic algorithm [J].Power System Protection and Control,2016,44(2): 36-41.)

[5]段大伟，周晓宇．基于混合算法的配电网故障定位[J].黑龙江科学， 2011,2(4): 30-32.(Duan Dawei, Zhou Xiaoyu.Distribution network fault locating based on hybrid algorithm [J].Heilongjiang Science,2O11,2 (4): 30-32.)

[6]郑云水，岳小雪，林俊亭．带有高斯变异的混合蛙跳蝙蝠算法[J].计 算机应用研究,2015,32(12):3629-3633.(Zheng Yunshui,Yue Xiaoxue, Lin Junting. Shuffled frog leaping and bat algorithm with Gauss mutation [J].Application Research of Computers,2015,32(12): 3629-3633.)

[7]潘桂彬，刘国栋，张世龙．改进的混合蛙跳移动机器人路径规划算法 [J].计算机应用研究，2014，31(12):3564-3567．(Pan Jiabin,Liu Guodong,Zhang Shilong.Improved path planning algorithm of shuffled frogleaping for mobile robot [J].Application Research of Computers, 2014,31(12): 3564-3567.)

[8]张勇．混合蛙跳算法的改进与应用研究[D].赣州：江西理工大学, 2016.(Zhang Yong.Application research and improvement on shuffled frog leaping algorithm [D].Ganzhou: Jiangxi University of Science & Technology,2016.)

[9]刘悦婷．带有选择和自适应变异机制的混合蛙跳算法[J].计算机工程， 2012,38 (23): 206-210.(Liu Yueting. Shuffled frog leaping algorithm with selection and adaptive mutation mechanism [J]. Computer Engineering, 2012,38 (23):206-210.)

[10]费腾，张立毅，陈雷．混合Levy 变异与混沌变异的改进人工鱼群算法 [J]．计算机工程,2016,42(7):146-151.(Fei Teng,Zhang Liyi,Chen Lei. Improved artificial fish swarm algorithm mixing levy mutation and chaotic mutation [J].Computer Engineering,2016,42(7):146-151.)

[11]王建玺，王刘涛，李小红.Levy 变异ABC 算法优化二阶Volterra 核的 鲁棒人脸识别[J].计算机应用研究，2015，32(2):619-622.(Wang Jianxi,Wang Liutao,Li Xiaohong.Robust face recognition based on the second order Volterra kernal optimized by ABC algorithm with Levy mutations [J]. Application Research of Compu-ters，2015，32 (2): 619-622.)

[12]张友华．混合蛙跳算法的改进及其应用研究[D]．兰州：甘肃农业大学， 2013.(Zhang Youhua. Improvement on shuffled frog leaping algorithm and itsapplication research [D].Lanzhou:Gansu Agricultural University, 2013.)

[13]康朝海，李鹏娜，张永丰，等．基于混合蛙跳粒子群算法的 TSP问题求 解[J]．吉林大学学报,2017,35(5): 498-506.(Kang Chaohai,LiPengna, Zhang Yongfeng，et al.Solving travelling salesman problem based on shuffled frog leaping algorithm and particle swarm optimization algorithm [J].Journal of Jilin University,2017,35(5): 498-506.

[14]陈超．自适应遗传算法的改进研究及其应用研究[D].广州：华南理工大 学，2011.(Chen Chao．Improvement and application Research onimproved adaptive genetic algorithm [D]. Guangzhou: South ChinaUniversity of Technology,2011.)

[15]张国强，彭晓明．自适应遗传算法的改进与应用[J].舰船电子工程， 2010 (1): 83-84,159.(Zhang Guoqiang,Peng Xiaoming. Improvement and application of an improved adaptive genetic algorithm [J]. Ship Electronic Engineering,2010 (1): 83-84,159.)

[16]邬月春．基于自适应变异粒子群算法的物流配送路径优化[J].兰州交 通大学学报,2012,31(1):114-117.(Wu Yuechun. Study on optimization oflogistics distribution route based on AMPSO[J].Journal of Lanzhou University,2012,31(1): 114-117.)