# 基于IFWA-ABC的云计算资源任务调度算法的研究

陈暄¹，王大伟1，王常亮‘，龙丹²(1．浙江工业职业技术学院，浙江 绍兴 312000;2.浙江大学，杭州 310058)

摘要：针对云计算资源任务调度效率低，资源分配不均的情况，将改进的烟花算法(improve fireworks algorithm)和人工蜂群算法(artificial bee colony)算法进行融合为IFWA-ABC。首先，对云计算资源任务调度进行描述；其次，在FWA初始化中采用混沌反向学习和柯西分布进行优化，对核心烟花和非核心烟花的半径分别进行优化，将FWA中最优个体通过改进的ABC算法进行获得；最后，将IFWA-ABC算法用于云计算任务调度。仿真实验中，通过与FWA、ABC在虚拟机、执行时间、消耗成本、能量消耗指标对比中，IFWA-ABC具有明显的优势能够有效地提高云计算资源分配效率。

关键词：烟花算法；人工蜂群算法；云计算；混沌反向学习 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.04.0213

# Cloud computing task scheduling algorithm based on IFWA-ABC

Chen Xuan1,Wang Dawei1,Wang Changliangl,Long Dan² (1.Zhejiang IndustryPolytechnic Collge,ShaoxingZhejiang 3120o0,China;2.Zhejiang University,Hangzhou310058, China)

Abstract: Due to the low eficiencyof cloud computing resource task scheduling and unevenresource allocation,this paper combinedtheimproved fireworksalgorithmandartificialbeecolonyalgorithminto IFWA-ABC.Firstly,thispaperdescribed thecloudcomputing resource task scheduling.Secondly,itused thechaoticreverse learningand Cauchy distributionto optimize theFWA initialization.Theradiiof thecore fireworks andthenon-corefireworks are optimizedrespectively.The optimalindividuals intheFWAareobtainedbyimprovingtheABCalgorithm.Finaly,theIFWA-ABCalgorithmis used for cloud computing task scheduling.Inthe simulation experiment,IFWA-ABC has obvious advantages compared with FWA and ABC in terms of virtual machine,execution time,consumption cost and Energy consumption index,which can ffectively improve cloud computing resource allocation efficiency.

Key words: fireworks algorithm; artificial bee colony algorithm; cloud computing; chaotic inverse learning

# 0 引言

云计算中的任务资源调度是衡量云计算中的一个重要组成部分，如何能够有效的、合理的分配任务资源之间的关系是云计算中效率能否提高的关键[I]。将智能算法引入到云计算中的资源调度已经成为了目前研究的主流,国内外学者一方面采用单一智能算法用于云计算资源调度,如PSO算法[2.3]、遗传算法[4.5]、蚁群算法[6,7]、人工蜂群算法[8];DAG 调度算法[9],烟花算法[10].另一方面将融合后的智能算法用于云计算资源调度。文献[11]提出了将粒子群算法和蚁群算法进行融合用于云计算资源调度，该算法优点提高了算法精度，提高了调度效率,缺点是缺乏与其他的更多智能算法进行对比的效果;文献[12]提出采用遗传算子生成初始信息素分布,通过双向收敛蚁群算子求出精确解,该算法优点是提高了求解精度和收敛速度，缺点是采用遗传算子的初始化信息素加强了算法的复杂性，提高了算法的求解时间;文献[13]提出对蚁群算法和粒子群算法分别进行改进，利用两种算法自身优势相结合的方式建立一种蚁群粒子群算法,用于云计算资源调度效率，该算法的优点是降低了消耗时间，缺点是降低了算法的精度。

本文以上研究的基础上,针对FWA存在的问题,对种群进行初始化、烟花半径进行改进,并在选择策略中采用ABC进行改进,融合后的IFWA-ABC算法用于云计算资源调度。仿真实验中在负载均衡、执行时间和消耗成本方面与FWA,ABC算法相比具有一定的优越性。

# 1 云计算资源调度任务简述

云计算中的任务调度效率是衡量云计算资源调度效率高低的重要指标,本文从云计算资源任务调度分的虚拟机负载、执行时间、花费成本三个方面进行描述,并用此作为云计算资源任务调度的效果评价依据

# 1.1虚拟机负载

虚拟机负载是云计算任务资源中调度中的重要组成部分，由于云计算中的资源会随着任务进行动态的变化，因此,记录单个虚拟机的相关参数无法反馈整个云计算动态情况。本文采用如下的方式记录虚拟机：

$$
\mathrm { R e } s L o a d ( V M _ { j } ) = [ i d _ { j } , V M _ { j } , l a s t T i m e _ { j } ]
$$

其中： $i d _ { \ j }$ 表示具有唯一性的虚拟机的编号; $\boldsymbol { V } \boldsymbol { M } _ { \boldsymbol { j } }$ 表示虚拟机自身的性能参数;lastTime表示最后一个任务在虚拟机中的执行时间。显然,当每一个任务 $T _ { i }$ 分配给虚拟机 $\boldsymbol { V } \boldsymbol { M } _ { \boldsymbol { j } }$ 的时候,最终任务执行时间lastTime需要进行修改：

$$
l a s t T i m e _ { j } = l a s t T i m e _ { j } ^ { ' } + t a s k T i m e _ { i j }
$$

$$
t a s k T i m e _ { i j } = \frac { T _ { i \_ t a s k L t e n t h } } { V M _ { j \_ c p u } } + \frac { T _ { i \_ I n p u t F i l e s i z e } } { V M _ { j \_ b w } } + t _ { w a i t }
$$

其中：lastTimej表示到上一次使用 $\boldsymbol { V } \boldsymbol { M } _ { j }$ 所完成时间; $t a s k T i m e _ { i j }$ 表示将任务 $T _ { i }$ 分配到虚拟机 $j$ 上所需要的执行时间如式(3)所示， $T _ { i \_ t a s k L t e n t h }$ 和 $T _ { i \_ I n p u t F i l e s i z e }$ 对应任务 $T _ { i }$ 中的任务长度和相关的输入信息, $V M _ { j _ { - } c p u }$ 和 $V M _ { _ { j _ { - } b w } }$ 分别表示虚拟机的计算能力和通信带宽。

# 1.2执行时间

云计算中的时间花费是衡量云计算资源调度效果的重要组成部分,本文采用 $\nu m T i m e ( V M _ { j } )$ 来表示所有任务的执行,也就是说每个虚拟机实际完成时间就是分配到该虚拟机上的所有任务的时间总和, $\sum _ { i \in V M _ { j } } t a s k T i m e _ { i j }$ 表示任务分配到第 $j$ 个虚拟机$\boldsymbol { V } \boldsymbol { M } _ { \boldsymbol { j } }$ 上的预测执行时间如式(4)表示,因此一个任务 $I$ 的执行时间如式(5)所示。

$$
\nu m T i m e ( V M _ { j } ) = \sum _ { i \in V M _ { j } } t a s k T i m e _ { i j }
$$

$$
\mathrm { R e } s T i m e ( I ) = \sum _ { j = 1 } ^ { m } \nu m T i m e ( V M _ { j } ) \times V M _ { j \_ \mathrm { c o s } t }
$$

# 1.3成本约束

云计算资源任务调度中除了时间之外,还有另外一个重要的衡量因素-任务成本消耗,它是云计算资源任务调度的重要组成部分。每一个任务的总的成本如下：

$$
R e s \mathbf { C o s } t ( I ) = \frac { f i n i s h \mathbf { C o s } t ( I ) - f i n i s h \mathbf { C o s } t _ { \mathrm { m i n } } } { f i n i s h \mathbf { C o s } t _ { \mathrm { m a x } } - f i n i s h \mathbf { C o s } t _ { \mathrm { m i n } } }
$$

其中： $\hslash n i s h { \bf C o s } t _ { \mathrm { m a x } }$ 和 $f i n i s h { \bf C o s } t _ { \mathrm { m i n } }$ 分别代表任务预测中的最大成本和最小成本,也就是部署在虚拟机上的最大时间和最小

时间对应的费用，具体计算公式如下：

$$
f i n i s h { \mathrm { C o s } } t _ { \mathrm { m a x } } = f i n i s h T i m e _ { \operatorname* { m a x } } \times M a x ( V M _ { j _ { - } \mathrm { c o s } t } )
$$

$$
f i n i s h { \bf C o s } t _ { \mathrm { m i n } } = f i n i s h T i m e _ { \mathrm { m i n } } \times M i n ( V M _ { j _ { - } \mathrm { c o s } t } )
$$

# 1.4能量消耗

云计算任务能量消耗关系到云计算资源调度的效果,本文采用 $\nu m E n g e r ( V M _ { j } )$ 来表示所有任务的能量消耗,也就是说每个虚拟机实际能量消耗就是分配到该虚拟机上的所有任务的能量消耗的总和， $\sum _ { i \in V M _ { j } } t a s k e n g e r _ { i j }$ 表示任务分配到第 $j$ 个虚拟机$\boldsymbol { V } \boldsymbol { M } _ { \boldsymbol { j } }$ 上的能量消耗如式(9)表示,一个任务的能量消耗如式(10)所示。

$$
\nu m E n g e r ( V M _ { j } ) = \sum _ { i \in V M _ { j } } t a s k e n g e r _ { i j }
$$

$$
{ \mathrm { R e } } s E n g e r ( I ) = \sum _ { j = 1 } ^ { m } \nu m E n g e r ( V M _ { j } ) \times V M _ { j \_ \mathrm { c o s } t }
$$

因此,衡量任务 $I$ 对应的资源调度的效果的函数如下：

$$
\begin{array} { r } { F ( I ) = w \times \mathrm { R e } s L o a d V M ( I ) + t \times \mathrm { R e } s T i m e ( I ) } \\ { + c \times R e s \mathrm { C o s } t ( I ) + e \times \mathrm { R e } s E n g e r ( I ) } \end{array}
$$

其中： $w , t , c$ 和 $e$ 分别为虚拟机,时间,成本及能量消耗的影响因子,并且都是0\~1的随机数,且 $\boldsymbol { w } + \boldsymbol { t } + \boldsymbol { c } + \boldsymbol { e } = 1$ 。显然,可以通过调节 $\boldsymbol { w } , t , \boldsymbol { c }$ 和 $\mathbf { \Psi } _ { e }$ 四个因子的值来设定虚拟机负载、执行时间,消耗成本及能量消耗在任务资源选择过程中的影响权重，这样既满足了系统对任务执行时间的约束,又满足了用户降低成本的要求。

# 2 FWA算法

Tan和Zhu根据烟花爆炸的形态于2010年提出了烟花算法(fireworksalgorithm,FWA)[14],它具有随机性、局部性和多样性的特点,其主要用于问题的优化。FWA中的每一个烟花作为优化问题中的一个可行解,根据适应度函数计算每一个烟花产生火花数值，适应度值越好的烟花产生对应的火花数目越多，反之，则越少，并且烟花爆炸过程中变异过程保证种群的多样性。FWA主要包括爆炸算子、变异算子和选择策略三个部分组成。

# 2.1爆炸算子

在算法的初始化中，需要对产生的烟花的位置对应的适应度值进行初步的评估,适应度值较好的烟花（一般被成为核心烟花)能够获得更多的资源,并且能够在小范围内产生更多的烟花，具有较强的局部搜索能力,而适应度值较差的烟花（一般成为非核心烟花)只能获得较少的火花,但是具有一定的全局搜索能力。因此,每个烟花的爆炸半径和所产生的火花数目根据种群中的其他烟花的适应度值计算得到。即爆炸半径 $A _ { i }$ 和爆炸火花数目 $S _ { i }$ 的计算如下：

$$
A _ { i } = \widehat { A } \ast \frac { f ( x _ { i } ) - Y _ { \operatorname* { m i n } } + \varepsilon } { \displaystyle \sum _ { i = 1 } ^ { N } ( f ( x _ { i } ) - Y _ { \operatorname* { m i n } } ) + \varepsilon }
$$

$$
S _ { i } = M \times \frac { y _ { \operatorname* { m a x } } - f ( x _ { i } ) + \varepsilon } { \displaystyle \sum _ { i = 1 } ^ { N } ( y _ { \operatorname* { m a x } } - f ( x _ { i } ) ) + \varepsilon }
$$

其中： $y _ { \mathrm { m i n } } = \operatorname* { m i n } ( f ( x _ { i } ) )$ 和 $y _ { \operatorname* { m a x } } = \operatorname* { m a x } ( f ( x _ { i } ) )$ 分别表示当前种群中的适应度值最小值和最大值。使用 $\hat { A }$ 来调整爆炸半径, $M$ 是一个常数,用来设定火花产生数目的大小, $\boldsymbol { \varepsilon }$ 为一个机器最小参数用来避免零操作。为了降低位置值好的烟花产生数量较少的爆炸火花，需要对火花个数进行限制：

$$
\widehat { S } _ { i } = \left\{ \begin{array} { l l } { r o u n d ( a * M ) , S _ { i } < a M } \\ { r o u n d ( b * M ) , S _ { i } > b M , a < b < 1 } \\ { r o u n d ( S _ { i } ) , o t h e r w i s e } \end{array} \right.
$$

其中： $^ { a , b }$ 为常数，round $( \bullet )$ 为四舍五入的取整函数。

# 2.2变异算子

为了能够增加种群的多样性,使用变异算子来产生变异火花。这种变异火花即高斯变异火花,主要是在种群中随机选择一个烟花个体,并在一定的维度上进行高斯变异操作得到公式如式(15)所示。

$$
\widehat { x } _ { i k } = x _ { i k } \times e
$$

其中, $e$ 为 $N ( 1 , 1 )$ 的高斯变异操作。

# 2.3选择策略

为了能够在当前的种群选择有效的个体传递到下一代中，在经历过以上2个操作之后,算法选择一定数量的个体作为下一代的烟花,其选择的概率为

$$
p ( x _ { i } ) { = } \frac { R ( x _ { i } ) } { \displaystyle \sum _ { x _ { j } \in K } x _ { j } }
$$

$$
R ( x _ { i } ) = \sum _ { x _ { j } \in K } d ( x _ { i } - x _ { j } ) = \sum _ { x _ { j } \in K } \| x _ { i } - x _ { j } \|
$$

其中： $R ( x _ { i } )$ 为当前个体候选者集合除了 $x _ { i }$ 之外所有个体的距离之和。通过以上的方式操作方式后,如果个体密度较高,该个体周围被选择的概率会降低。

# 3 基于IFWA-ABC的云计算资源调度算法

针对FWA算法自身过早收敛,解精度低,容易陷入局部最优的问题,本节对FWA算法在初始化,烟花半径和选择策略方面进行改进,将得到的IFWA-ABC算法并用于云计算资源调度

# 3.1改进的 FWA算法

# 3.1.1混沌反向学习和柯西分布优化初始位置

FWA算法的初始解通常采用随机方式，这种随机处理方法在一定程度上对最优解的产生具有一定的影响，假设两者极端的情况，一种是产生的随机解距离最优解很近的时候，算法的收敛速度就会很快，另一种是产生的随机解距离很远或者反向的时候,导致算法需要消耗更长的时间才能够完成收敛。针对这种问题,本文引入了混沌反向学习概念来初始化解，即在当前解的同时求得反向解,通过对两者的对比，从中选择较好的一个解，这样可以在很大程度上提高算法的执行效率。根据FWA算法中的烟花个体的位置，给出Logistic映射产生混沌状态下的初始值，如式(18)所示，计算其位置的反向解如式(19)所示。式中， $x _ { \operatorname* { m a x } , j }$ 和 $x _ { \mathrm { m i n } , j }$ 是搜索空间中的候选解的最大值和最小值

$$
x _ { i , j } = x _ { \operatorname* { m i n } , j } + \delta _ { i , j } \bullet ( x _ { \operatorname* { m a x } , j } - x _ { \operatorname* { m i n } , j } )
$$

$$
{ x _ { i , j } ^ { * } } = { x _ { \operatorname* { m i n } , j } + x _ { \operatorname* { m a x } , j } - x _ { i , j } }
$$

因此，将反向后的解与原来解组成一个群体,按照适应度值的由高到低进行排列,选择前一半的值作为种群的初始化的解。

在标准的FWA算法中，新一代的烟花个体散落在父代个体周围，产生的解会随着迭代次数的增加而不断的减小，将搜索的范围逐渐搜索到父代个体附近，这样使得算法容易陷入局部最优，而降低求出全局最优解的效率，采用柯西分布生成的随机数能够使得搜索区域更加广泛，因此能够提高算法的全局搜索能力，因此采用如下的密度函数进行计算。

$$
\begin{array} { l } { { f ( x , \gamma ) = \displaystyle \frac { 1 } { \pi } [ \frac { \gamma } { x ^ { 2 } + \gamma ^ { 2 } } ] } } \\ { { s . t . ~ \gamma _ { i t e r } = \displaystyle \frac { ( i t e r _ { \mathrm { m a x } } - i t e r ) ^ { n } } { ( i t e r _ { \mathrm { m a x } } ) ^ { n } } ( \gamma _ { i n i t i a l } - \gamma _ { f i n a l } ) + \gamma _ { f i n a l } } } \end{array}
$$

其中：iter 表示迭代次数， $i t e r _ { \operatorname* { m a x } }$ 表示最大迭代次数, $\gamma _ { i n i t i a l }$ 和Yfinal 分别表示柯西分布中的尺度参数的初始值和最大值。

# 3.1.2设定阀值优化非核心烟花半径

根据FWA算法得知，当烟花在爆炸的时候,会在它的周围一定的区域中产生大量的火花，火花的范围就是烟花的半径,核心烟花是烟花种群中的适应度值最小的烟花个体，而非核心烟花半径如公式(12)所示，很显然这种方式会发现适应度值最小的烟花的半径非常小，几乎接近0,因此浪费了资源。为了避免这种情况的发生,设定最小半径阀值，其表现形式如下：

$$
A _ { i , k } = \left\{ { \begin{array} { l l } { A _ { \operatorname* { m i n } , k } , i f A _ { i , k } < A _ { \operatorname* { m i n } , k } } \\ { A _ { i , k } , o t h e r w i s e } \end{array} } \right.
$$

阈值 $A _ { \operatorname* { m i n } , k }$ 的设定并不是一个固定的值,这是因为算法在迭代过程中会产生的动态的效果，因此采用非线性递减方式。

$$
A _ { j , k } ( t ) = ( A _ { s t a r t } - A _ { e n d } - d _ { \operatorname* { m a x } } ) e ^ { \frac { t } { 1 + d _ { \operatorname* { m a x } } } }
$$

其中：dmax为最大函数评估次数，t为当前函数评估次数，Astanr和 $A _ { e n d }$ 分别表示最初的爆炸半径和最终半径数值。

# 3.1.3权重算子优化核心烟花半径

文献[15]中提到需要对核心烟花的爆炸半径进行一定的调整才能使得算法的性能得到改进，显然这种改进存在的一定问题,其主要表现在来自局部搜索能力的提高,烟花个体之间相互并没有交流,提出的核心烟花半径计算过于简单，仅仅考虑缩放而直接忽略了搜索过程,容易造成算法陷入局部最优。使得算法过早的收敛，导致算法难以跳出多峰值的时候局部最优解的束缚,本文在此基础上采用粒子群算法中的权重算子，其主要目的是利用当前最好烟花位置和历史最优信息，从而避免了陷入局部最优。表达如下：

$$
\hat { X _ { i } } = X _ { b e s t } + c * ( X _ { b e s t } - X _ { i } )
$$

$$
c = \left\{ { \begin{array} { l } { r a n d c ( 0 . 1 , 0 . 5 ) i f r a n d < { \frac { t _ { 1 } } { t _ { 1 } + t _ { 2 } } } } \\ { r a n d c ( 0 . 5 , 1 . 0 ) o t h e r w i s e } \end{array} } \right.
$$

其中： $X _ { b e s t }$ 表示当前位置中最好的烟花位置, $\boldsymbol { \mathbf { \mathit { c } } }$ 为权重因子控制先产生的火花与当前最好烟花位置之间的距离,使得烟花个体具有向种群中最优秀的个体学习的能力从而向群体内历史最优点靠近。 $r a n d c ( x , y )$ 是位置参数 $x$ 和尺度参数为 $y$ 的柯西分布,当位置参数小的时候,有利于进行局部搜索,使用 $t _ { 1 }$ 表示位置参数小的时候柯西分布，当位置参数大的时候,有利于进行全局搜索,使用 $t _ { 2 }$ 表示参数大的柯西分布。

# 3.1.4基于ABC算法选择策略

在FWA算法中,每一次迭代过程中优秀烟花个体都能传递到下一代种群中,FWA算法主要是选择适应度值最小的个体，而剩余个体都采用随机状态,显然,这种挑选的策略存在一定的端,虽然在某次迭代中，按照适应度值小的选择个体,但从全局来看不一定能够保证选中的个体就一定比剩余随机状态的个体要好，同时剩余的个体采用随机的状态,从整体上不利于算法全局最优解的诞生，针对这个情况，本文引入人工蜂群算法(artificialbee colony,ABC算法),ABC算法具有简单易实现、控制参数少、鲁棒性强以及全局搜索能力较强等特点,通过每个人工蜂个体优化作用最终找到最优的个体。在ABC算法中,分为3种个体，分别是雇佣蜂、观察蜂和侦察蜂。每一个雇佣蜂对应一个确定的蜜源(FWA中个体的位置),并在迭代过程中对蜜源的周围位置进行更新,根据蜜源的适应度值采用轮盘的方式雇佣观察蜂进行采蜜，以便获得新的蜜源，当一定搜索次数之后没有新蜜源出现就放弃该蜜源，雇佣蜂变为侦察蜂随机搜索的新蜜源。

a)初始化。统计FWA中的种群中所有个体 $\mathit { s N }$ ，并计算每个个体的适应度值，产生可行解为xij=Xmin.j +rand(0,1)(xmaxj-Xmin.j）(25)其中： $\boldsymbol { x } _ { i } \ ( \ i = 1 , 2 , \cdots S N )$ 为 $D$ 维向量, $j \in \{ 1 , 2 , \cdots D \}$

b)蜜源最优值。在当前的蜜源相关领域中进行搜索，借助DE算法的思想，因此新的蜜源公式为

$$
\dot { \nu _ { i , j } } = x _ { r 1 , j } + \varphi _ { i , j } ( x _ { i , j } - x _ { r 2 , j } ) + \phi _ { i , j } ( x _ { r 3 , j } - x _ { r 4 , j } )
$$

$$
\begin{array} { r } { \dot { \nu _ { i , j } } = x _ { b e s t , j } + \varphi _ { i , j } ( x _ { i , j } - x _ { r 1 , j } ) + \phi _ { i , j } ( x _ { r 2 , j } - x _ { r 3 , j } ) } \end{array}
$$

$$
\nu _ { i , j } = p \bullet \nu _ { i , j } ^ { \cdot } + ( 1 - p ) \bullet \nu _ { i , j } ^ { \cdot }
$$

其中： $j \in \{ 1 , 2 , \cdots D \}$ 为随机选择的目标, $i \in \{ 1 , 2 , \cdots S N \} \ , \ \cdot$ $\varphi _ { i j }$ 和$\phi _ { i , j }$ 分别为 $[ - 1 , 1 ]$ 和[0.5,1]的随机数， $p$ 都是随机选择的整数， $\boldsymbol { x } _ { b e s t , j }$ 是当前全局最优解,显然，借助差分算法的影响式(26)能够有效地保持种群的多样性，式(27)可以提高收敛速度，增强算法的开发能力，为了能够将两者进行有效的结果,采用式(28)来控制新的蜜源位置。

c)雇佣蜂概率。观察蜂选择雇佣蜂概率如式(29)所示。

$$
P _ { i } = { \frac { f i t ( x _ { i } ) } { \displaystyle \sum _ { n = 1 } ^ { S N } f i t ( x _ { n } ) } }
$$

其中： $\mathit { f i t } ( x _ { i } )$ 表示第 $i$ 个解的适应度值对蜜源的丰富程度,当蜜源越丰富，被观察蜂选择的概率就越大。

在ABC算法中,当FWA中个体位置对应的蜜源在迭代过程中没有进行改进,就放弃该蜜源即该烟花个体,并且将该蜜源对应的烟花个体位置放到禁忌表中，同时将该蜜源对应的雇佣蜂转为侦察蜂,并根据式(16)随机产生一个FWA的个体位置代替原有的个体。

# 3.2基于FWA-ABC算法的云计算资源调度

根据融合后的两种算法的优点，结合云计算中资源任务调度步骤如下，流程如图1所示。

a)将云计算任务调度的方案与FWA算法中的烟花位置进行一一对应,找到最佳的烟花位置即为最佳的任务调度方案;

b)初始化FWA算法的初始化参数,ABC算法的参数，设定迭 代次数;

c)按照式(18)\~(20)对FWA算法种群进行初始化;

d)对烟花半径进行分别优化,核心烟花半径按照式(21)(22)进行优化,对非核心烟花半径按照式(23)(24)进行优化;

e)将烟花个体通过ABC算法中的公式(25)-(29)进行处理;

f)当达到最大迭代次数的时候,算法结束,转步骤g),否则转步骤c);

g)得到最优的烟花位置,即得到最优的云计算任务调度方案。

![](images/65341d60098ecdf2ffa7bcc2ae3d77dbfb64b4da4f99d6e74b5a7a2dee59cb00.jpg)  
图1调度流程

# 4 实验仿真

# 4.1算法性能

为了说明本文算法的性能,将IFWA-ABC算法与FWA算法、ABC 算法在3个经典测试函数中进行对比。每一种算法运行200次，比较结果如表1所示

$$
f _ { 1 } ( x ) = \sum _ { 1 } ^ { n } x ^ { 2 }
$$

$$
f _ { 2 } ( \boldsymbol { x } ) = \sum _ { i = 1 } ^ { n } \left( \sum _ { j = 1 } ^ { i } x _ { j } \right) ^ { 2 }
$$

$$
f _ { 3 } ( x ) = \sum _ { i = 1 } ^ { n } ( x _ { i } ^ { 2 } - 1 0 \mathrm { c o s } ( 2 \pi _ { i } ) + 1 0 )
$$

表1测试结果对比  

<html><body><table><tr><td>维数</td><td>算法</td><td>最优值</td><td>最差值</td></tr><tr><td rowspan="2">f</td><td>IFWA-ABC</td><td>3.78214e-2</td><td>5.38272e-2</td></tr><tr><td>FWA</td><td>4.12712e-2</td><td>7.36234e-2</td></tr><tr><td rowspan="5">f</td><td>ABC</td><td>5.89234e-2</td><td>9.39802e-2</td></tr><tr><td>IFWA-ABC</td><td>0.0023682</td><td>0.0873232</td></tr><tr><td>FWA</td><td>0.0063982</td><td>0.1980327</td></tr><tr><td>ABC</td><td>0.0298217</td><td>0.2739231</td></tr><tr><td>IFWA-ABC</td><td>0.5392873</td><td>2.9837123</td></tr><tr><td rowspan="2">f</td><td>FWA</td><td>1.7309431</td><td>4.2938731</td></tr><tr><td>ABC</td><td>4.983491</td><td>6.3940211</td></tr></table></body></html>

从表1中发现IFWA-ABC的性能相比FWA算法具有显著的提高,说明本文的算法效果较好。

# 4.2 云计算任务调度

为了说明IFWA-ABC 算法在云计算中资源调度的效果,将IFWA-ABC算法与FWA、ABC 算法在虚拟机负载均衡、消耗时间和成本花费进行对比。硬件环境选CPU为酷睿i3,内存为4GDDR,硬盘容量为1000G软件环境为Linux操作系统,采用Cloudsim模拟云计算环境。选取三种不同的任务集合，分别为Task1[100,1000],Task2[1000,10000]和Task3[10000,100000],资源数目为500。FWA算法,ABC算法的相关参数以文献[8],文献[10]为主,IFWA-ABC 算法中的相关参数设置如下: $\gamma _ { i n i t i a l }$ 和 $\gamma _ { \mathit { f i n a l } }$ 分别10和50, $d _ { \operatorname* { m a x } }$ 为100, $A _ { s t a r t }$ 和 $A _ { e n d }$ 分别为2.5和 $1 0 , \varphi _ { i j }$ 和 $\phi _ { i , j }$ 分别为0.5和1, $p$ 为0.5。

# 4.3负载均衡对比

本文将三种任务集合在10个资源点中（24号 $\{ \mathrm { s } 1 , \mathrm { s } 2 , \mathrm { s } 3 , \mathrm { s } 4 , \mathrm { s } 5 , \mathrm { s } 6 , \mathrm { s } 7 , \mathrm { s } 8 , \mathrm { s } 9 , \mathrm { s } 1 0 \} , \mathrm { s } 1$ 到s10处理任务为分别为50,100,150,200,250,300,350,400,450和500,三种任务集合状态下的三种算法的对比效果如图2-4所示,每个云计算的资源处理点的能力不同，因此负载都不相同,从图2-4中发现,当任务数量较小的时候，三种算法的负载均衡都差不多，当任务的数量逐渐增大的时候,IFWA-ABC算法的负载均衡，而FWA和ABC算法的负载产生的数值不同，这说明IFWA-ABC算法在云计算资源分配效果明显,负载稳定。

![](images/a274a2bce92581aa6fc2a612192b49546478483cbb3a11a80bcbece5114107ca.jpg)  
图2三种算法Task1中的负载均衡对比

![](images/54d45beffd741d5d56d08bd459a2d54853cc3e4f69f02239989f44a68de3ef30.jpg)  
图3三种算法Task2中的负载均衡对比

![](images/73afa242d308d47c34cd9b2c9d2f078aa4daa09aa1a1e2c67a6f0b1724393b64.jpg)  
图4三种算法Task3中的负载均衡对比

# 4.4执行时间对比

图5\~7显示了三种任务集合下的执行时间对比情况，从图中可以发现,三种算法的执行时间都随着任务数量的增加具有不同程度的增加,当任务数量较小的时候,三种算法的执行时间相差不大，当任务数量较大的时候，三种算法执行时间之间的相差明显，IFWA-ABC算法的执行时间明显优于FWA、ABC算法，这说明IFWA-ABC算法能够适应云计算下任务资源调度。

![](images/f24efaa90db1b7098213ac271a9bf61bf4f6bc2b1c52ba5ae47ed8db9f03b266.jpg)

![](images/6b83eebc8b72da5c785f4e8ea1887c61179bdc471a3e0b5d1cd0074705ee1d99.jpg)  
图5三种算法Task1中的执行时间对比

![](images/e70d34e751ab8a5d11f8c71d2cadf2425710875aada37879f0f75e572d765d06.jpg)  
图6三种算法Task2中的执行时间对比

# 4.5 消耗成本对比

图8\~10显示了三种任务集合下的消耗成本的对比情况，从图中可以发现,三种算法的消耗成本都伴随着任务数量的增多而变大,当任务数量较小的时候,三种算法消耗成本的曲线都在平缓的增长,当任务数量逐渐增大的时候,三种算法的消耗成本的曲线都在不同程度的增加,且IFWA-ABC的曲线增长幅度平缓,而FWA和 ABC算法幅度较大,这说明IFWA-ABC相比于FWA,ABC算法在消耗成本方面具有较大的优势,能够适应。

![](images/cbb5d586df2cef6c0e18323ce40f963695d89e3e88ba194e6507a712b78c8c83.jpg)  
图7三种算法Task3中的执行时间对比

![](images/3f1411f985aa1fdc9663560757b5bd8b2ea8c8cebf4c7d04be614c5a0949f8b8.jpg)  
图8三种算法Task1中的消耗成本对比

![](images/bf0197c912787e096d6aec97b8b9c5e63a05dc1920c53cec301acc3d66f8a978.jpg)  
图10三种算法Task3中的消耗成本对比

# 4.6 能量消耗对比

图11\~13显示了三种任务集合下的能量消耗对比的结果,在任务数量较小的时候，相互之间的能量消耗差别并不是很大，但总体上IFWA-ABC算法占据一定的优势，当任务数量逐渐增大的时候,IFWA-ABC相比于FWA和ABC算法具有明显的优势，这说明了IFWA-ABC算法能够有效的降低能量消耗

![](images/8f9fbfbe55e679cc4dbe13c985611c8c0829f2d4edbb637f56bc03f115a31a7e.jpg)  
图11三种算法在 Task1中的能量消耗对比

![](images/9902a088c80336bfc2d5b87586e13455088e99495315e80789f6beb0e4eb0029.jpg)  
图12三种算法在Task2中的能量消耗对比

![](images/b668c3c51c8bc867d80074b725e7a1a9fab5a239fb048c1701b0110ca811829e.jpg)  
图9三种算法Task2中的消耗成本对比  
图13三种算法在Task3种的能量消耗对比

# 5 结束语

针对云计算任务资源的问题,本文将FWA算法用于任务调 度,并对FWA算法自身进行了改进,将ABC算法与之进行融合

形成IFWA-ABC,,仿真实验从均衡负载、执行时间、消耗成本和能量消耗等方面说明了IFWA-ABC算法具有良好的效果，能够适应云计算下任务调度。

# 参考文献：

[1]张建勋，古志民，郑超．云计算研究进展综述[J].计算机应用研究, 2010,27(2): 429-433.(Zhang Jianxun,Gu Zhimin,Zheng Chao.Survey of research progress on cloud computing [J]．Application Research of Computers,2010,27(2): 429-433.)   
[2] Masdari M,Salehi F, Jalal M,et al.A survey of pso-based scheduling algorithms in cloud computing [J]. Journal of Network and Systems Management,2017,Vol.25,No.1,pp:122-158   
[3]Kumar N,Patel P.Resource management using ANN-PSO techniques in cloud environment [C]//Proc of International Congress on Information and Commuication Technology.2016: 419-428   
[4]Shahdi-Pashaki S，Teymourian E,Tavakkkoli Moghaddam R.New approach based on group technology for the consolidation problem in cloudcomputing-mathematical model andgeneticalgorithm[J]. ComputationalandAppliedMathematics，2016,DOI: 10. 1007/s40314-016-0362-4   
[5]Aziza H,Krichen S.Bi-objective decision support systemfor task-scheduling based on genetic algorithm in cloud computing [J]. Computing,2018,100 (2): 65-91.   
[6]Ragmani A,Omri A E,Abghour N,et al.A performed load balancing algorithm for public Cloud computing using ant colony optimization [Cl// Proc of the 2nd International Conference on Cloud Computing Tehnologies and Application. 2016: 7847703   
[7]Satapathy.A basic simulation of ACO algorithm under cloud computing for fault tolerant [C]/ Proc of International Conference on Data Engineering and Communication Technology. 2017: 465-472.   
[8]杨海军.云计算环境下人工蜂群作业调度算法设计[J].数学的实践与

认识，2012,42(10):115-120.(Yang Haijun.A job scheduling algorithm

based on artificial bee colony in cloud computing [J].athematics in Practice and Theory,2012,42(10): 115-120.)   
[9] 徐健锐，朱会娟．云计算环境中面向 DAG 任务的多目标调度算法 [J/OL].计算机应用研究，2019，36（1）．[2018-01-10].http://www. arocmag.com/article/02-2019-01-023.html.(Xu Jianrui,Zhu Huijuan. Multi-objective scheduling algorithm of DAG tasks in cloud computing [J]. pplication Research of Computer,2019,36(1).[2018-01-10]. htp://www. arocmag.com/article/02-2019-01-023. html. )   
[10]黄伟建，郭芳．基于烟花算法的云计算多目标任务调度[J].计算机应 用研究，2017，34(6):1718-1720.(Huang Jinwei，Guo Fang. Multi-objective task scheduling based on fireworks algorithm in cloud computing [J].pplication Research of Computers，2017，34 (6): 1718-1720.)   
[11] Chen X.Task Scheduling of cloud computing using integrated particle swarm algorithm and ant colony algorithm [J]. Cluster Computing,DOI: 10.1007/s10586-017-1479-y, 2017   
[12]赵俊普，殷进勇，金同标，等．遗传蚁群算法在云计算资源调度中的应 用[J]．计算机工程与设计,2017(3):693-697.(Zhao Junpu,Yin Jinyong, Jin Tong biao,et al.Application of genetic ant colony algorithm in cloud computing resource sheduling [J]. Computer Engineering and Design, 2017, 38 (3): 693-697.)   
[13]萨日娜．基于蚁群粒子群优化算法的云计算资源调度方案[J].吉林大 学学报：理学版，2017,55(6):1518-1522.(Sa Rina.Cloud computing resource scheduling scheme based on ant colony particle swarm optimization algorithm [J].Journal of Jilin University: Sci Ed,2O17,55 (6): 1518-1522.)   
[14] Tan Y, Zhu Y. Fireworks algorithm for optimizaion [C].Berlin: Springer, 2010:355-364   
[15] Zheng S,Janecek A,Li J,et al.Dynamic search in fireworks algorithm [C]// Evolutionary Computation. 2014: 3222-3229.