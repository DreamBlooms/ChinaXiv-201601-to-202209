# 基于折射原理的混合型花朵授粉算法

崔丽群，张晨，郑宝林，周四宏(辽宁工程技术大学 软件学院，辽宁 葫芦岛 125105)

摘要：针对花朵授粉算法收敛速度慢，寻优精度低的缺陷，提出基于折射原理的混合型花朵授粉算法 (refrHFPA)。算法首先利用和声搜索算法提升算法收敛速度，然后利用折射原理提高种群的多样性，帮助算法跳出局部最优，提升寻优精度。实验利用8个测试函数，对比其他群智能算法，结果表明refrHFPA算法在收敛速度和寻优精度方面均有显著的提高。

关键词：花朵授粉算法；和声搜索算法；折射原理；种群多样性 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.11.0731

# Hybrid flower pollination algorithm based on refraction principle

Cui Liqun, Zhang Chen, Zheng Baolin, Zhou Sihong (School of software Liaoning Technical University,Huludao Liaoning1251o5,China)

Abstract:This paper proposed a hybrid flower polinationalgorithm (refrHFPA)based onrefraction principle for the slow convergencerateofflowerpolinationalgorithmandlowoptimizationaccuracy.Thealgorithmfirstlyused theharmonysearch algorithmto improvetheconvergence speedofthealgorithm,then itused therefraction principle toimprovethediversityof thepopulation,and helpedthealgorithm tojumpoutof thelocal optimaland improved theacuracyofoptimization.Itused eighttestfunctions tocompareother intellgentalgorithms,andtheresultsshowthattherefrHFPAalgorithmhasasignificant improvement in convergence speed and optimization accuracy.

Key words: flower polination algorithm; harmony search algorithm; refraction principle; population diversity

# 0 引言

花朵授粉算法（flower pollinationalgorithm，FPA）[1]是一种新型元启发式智能算法，由英国学者Yang于2012年首次提出。由于FPA算法具有参数较少、实现简单、易与其他算法进行组合优化，且转换概率p可以较好地调节全局搜索与局部搜索之间平衡等优点，目前已在函数优化领域得到了应用。例如，中国学者Zhou 等人[2]应用改进的花朵授粉算法优化无人海底车辆的路径规划；贺圣彦等人[3]将该算法应用到PID参数优化；Abdel-Baset等人[4]利用该算法进行比例优化。但是花朵授粉算法也具有仿生算法的典型缺点，如易陷入局部极值、后期收敛速度慢等问题。为了解决这些问题，文献[5]将FPA与萤火虫算法相结合，在局部搜索部分引入自适应因子并自适应调整转换概率p。文献[6]利用高斯变异对全局搜索进行扰动增强种群的多样性，将Powell法引入局部搜索，以提升其局部搜索能力。文献[7]将差分进化的变异、交叉和选择操作应用到花朵授粉算法帮助算法跳出局部最优，以增强全局搜索能力。FPA算法因提出时间短，迫切需要理论研究及应用领域的扩展。虽然以上文献对FPA算法的寻优能力有一定程度上的改进，但仍存在寻优精度低、后期收敛速度慢等问题。

针对花朵授粉算法速度和精度的问题，本文将折射原理与和声搜索算法引入到花朵授粉算法中，提出基于折射原理的混合型花朵授粉算法（refrHFPA)。该算法将和声搜索算法引入到FPA算法中，以提高原算法的寻优速度；利用折射原理提高原种群多样性，使FPA算法跳出局部最优，以提高算法的收敛精度。

# 1 基础理论

# 1.1花朵授粉算法

花朵授粉算法是一种模拟开花植物授粉进程的智能算法。授粉方式分为非生物自花授粉和生物异花授粉。非生物自花授粉是指花粉的传播不需要生物作为传播者，而是通过风进行传播，这种传播方式范围较小，被视为局部搜索。生物异花授粉是两种开花植物进行授粉，授粉过程是由蜜蜂等传粉者进行传播，该过程因可在大范围内进行传播，被视为全局搜索。全局搜索与局部搜索之间的转换通过转换概率p来进行调节。现实生活中的每一棵显花植物都可以产生数百万甚至更多的花粉配子。为了简化问题，通常假设每棵显花植物只开一朵花，而且每朵花只产生一个花粉配子，这代表每个花粉配子只对应一个解。

根据开花植物的授粉过程，花朵授粉算法具有如下四条规律[1];

a)生物异花授粉是携带花粉的传粉者进行全局搜索，方式符合莱维飞行；

b)非生物自花授粉被视为局部搜索过程；c)花的恒常性被认为是繁殖概率，这种概率与所涉及的两朵花的相似性成正比；d）转换概率 $p \in \left[ 0 , 1 \right]$ ，受物理距离和其他因素的影响，在整个授粉活动中， $\mathfrak { p }$ 值的选取非常重要。

# 1.2折射原理

光的折射是指光从一种介质斜射入另一种介质，它是自然界中存在的一种普遍的自然现象[8]，如图1所示。其中 $\mathbf { \boldsymbol { a } } _ { 1 }$ 为入射角， ${ \bf { \alpha } } _ { \bf { { u } } _ { 2 } }$ 为折射角，O为交界点。光的传播方向在不同介质的交界处发生偏折。

![](images/04d151052717daa6e4d374c87eb411c3df04d440fc13505d65c0374b487c8421.jpg)  
图1光的折射原理

斯涅耳通过实验确立了折射定律，即介质的绝对折射率n为入射角和折射角的正弦比[9]，公式为

$$
n = \sin \alpha _ { 1 } / \sin \alpha _ { 2 }
$$

# 2 改进的花朵授粉算法

# 2.1基于和声搜索算法的花朵授粉算法

和声搜索算法（Harmony search，HS）是由韩国学者Geem等人[10]于2001年提出的启发式优化算法。由文献[10]可知，HS算法由于随机选择音调的作用使其全局搜索能力较强。因此将HS 算法引入FPA算法中，得到基于和声搜索算法的花朵授粉算法（HSFPA)。HSFPA算法通过将HS 算法的最优解作为初始解来提高算法的寻优精度。和声搜索算法具体步骤如下：

a)对HMS（初始解个数）、HMCR（和声记忆库考虑概率）、PAR（和声微调概率）、BW（音调微调带宽）等参数进行设置。

b)算法进行初始化，随机生成HMS个和声，形成和声记忆库。和声记忆库为：

$$
H M = [ \begin{array} { c c c c c } { x _ { 1 } ^ { 1 } } & { x _ { 2 } ^ { 1 } } & { \ldots } & { x _ { n } ^ { 1 } } \\ { { x _ { 1 } } ^ { 2 } } & { { x _ { 2 } } ^ { 2 } } & { \vdots } & { { x _ { n } } ^ { 2 } } \\ { \vdots } & { \vdots } & { \ldots } & { \vdots } \\ { x _ { 1 } ^ { H M S } } & { x _ { 2 } ^ { H M S } } & { \ldots } & { x _ { n } ^ { H M S } } \end{array} ] \begin{array} { c } { { f ( x ^ { 1 } ) } } \\ { { f ( x ^ { 2 } ) } } \\ { { \vdots } } \\ { { f ( x ^ { H M S } ) } } \end{array} ]
$$

c)生成一个新的和声。新和声的每一个音调通过如下三种机理产生：

（a）学习和声记忆库。

(b)若新解第一个变量以HMCR的概率选自和声记忆库，则按照公式（2）对音调进行微调，反之则在变量范围内（和声记忆库外）随机选择一个值作为新解。

$$
x _ { 1 } ^ { \prime } = \left\{ \begin{array} { c c } { { x ^ { \prime } \pm r _ { 1 } \times B W _ { 1 } } } & { { \ddagger \neq r _ { 2 } < P A R } } \\ { { x _ { 1 } } } & { { \ddagger \neq 1 \land \pmb { \mathscr { W } } } } \end{array} \right.
$$

其中： $\mathbf { r } _ { 1 }$ 、r为符合[0,1]均匀分布的随机数。

(c)随机选择音调。(d)将生成的新和声和原有和声记忆库中的最差值进行比较，若优于最差值则对和声记忆库进行更新，反之则不变。（e）判断是否符合迭代结束条件，符合则结束迭代，不符合则重复（c）和（d）直到符合条件。

# 2.2基于折射原理的花朵授粉算法

本文将折射原理引入FPA算法，以增加种群的多样性，

帮助算法跳出局部最优，提高算法的收敛速度和寻优精度。具体过程如图2所示。将空气与其他介质的临界处看为X轴，X 是搜索区域的上下界，取值范围为[a，b]，点 $\mathrm { X _ { b e s t } }$ 是当前迭代的最优解， $X _ { 1 }$ 为 $\mathrm { X _ { b e s t } }$ 正上方的入射光点， $\mathrm { \Delta Y }$ 为点 $X _ { 1 }$ 的折射点， $\mathrm { Y } _ { 1 }$ 则为点 $\mathrm { \Delta Y }$ 在交界处的投影即点 $\mathrm { X } _ { \mathrm { b e s t } }$ 的折射点。将 $\mathrm { O X _ { l } }$ 的距离设为H，OY的距离设为 $\mathrm { H } _ { 1 }$ ，交界点O为中心点（ $\cdot < + 6$ ）/2。

![](images/e78ce3e7d49888ed5e3114a80956d3d42a03d9c3f37ba4b7fc4996c1f132a182.jpg)  
图2折射原理优化FPA算法原理示意

由图2可知：

$$
\sin \alpha _ { 1 } = ( ( a + b ) / 2 - X _ { b e s t } ) / H
$$

$$
\sin \alpha _ { 2 } = ( Y _ { 1 } - ( a + b ) / 2 ) / H _ { 1 }
$$

由式（3）（4）可知,折射率 $\mathfrak { n }$ 可由式（5）表示。

$$
n = \sin \alpha _ { 1 } / \sin \alpha _ { 2 } = \frac { ( ( a + b ) / 2 - X _ { b e s t } ) / H } { ( Y _ { 1 } - ( a + b ) / 2 ) / H _ { 1 } }
$$

设 $\mathrm { H } / \mathrm { H } _ { 1 } { = } \mathrm { f } _ { \mathrm { : } }$ ，可将式（5）改为

$$
Y _ { 1 } = ( a + b ) / 2 + ( ( a + b ) / 2 - X _ { b e s t } ) / ( f n )
$$

算法每进行一次迭代， $\mathrm { X _ { b e s t } }$ 都通过式（6）进行折射，得到折射解 $\mathrm { Y } _ { 1 }$ ，通过判断 $\mathrm { X _ { b e s t } }$ 与 $\mathrm { Y } _ { 1 }$ 的适应度值大小，对当前的全局最优解进行更新。

# 2.3基于折射原理的混合型花朵授粉算法

将HS 算法的最优解作为FPA算法的初始解，可在一定程度上提升算法的收敛精度，但是HS算法的随机性较大，有时会使算法陷入局部最优。因此利用折射原理增强种群的多样性，以利于算法跳出局部最优，提高算法的寻优精度和收敛速度。改进后的算法流程如图3所示。具体实现步骤如下：

a)初始化算法的各参数。包括p，HMCR,PAR等参数。b)求出每个解的适应度值。c)利用HS算法求出当前最优解作为初始值。d)当 $\mathsf { p } { \circ }$ rand（rand为[0,1]均匀分布的随机数）时，按照式（7）对解进行更新，按照式（8）对步长进行更新；反之则按照式（9）对解进行更新，最后进行越界处理。

$$
X _ { i } ^ { { t + 1 } } = X _ { i } ^ { { t } } + L ( X _ { i } ^ { { t } } - g _ { * } )
$$

其中： $\mathbf { X _ { i } ^ { \mathrm { { t + 1 } } } }$ 、 $X _ { \mathrm { i } } ^ { \mathrm { t } }$ 分别是指向量 $\mathrm { \Delta X _ { i } }$ 迭代 $_ { \mathrm { t + l } }$ 次和t次后的解； $g _ { * }$   
代表当前最优解。

$$
L \sim \frac { \lambda \Gamma ( \lambda ) \mathrm { s i n } ( \pi \lambda _ { \binom { 2 } { 2 } } ) } { \pi } \frac { 1 } { s ^ { 1 + \lambda } } , ( s > > s _ { 0 } > 0 )
$$

其中： $\mathrm { ~ L ~ }$ 代表步长； $\Gamma$ （λ）是标准的伽玛函数， $\lambda { = } 1 . 5$ 。

$$
X _ { i } ^ { { t + 1 } } = X _ { i } ^ { { t } } + \varepsilon ( X _ { j } ^ { { t } } - X _ { g } ^ { { t } } )
$$

其中： $\mathrm { X j } ^ { \mathrm { t } }$ 和 ${ \mathrm { X } } { \mathrm { k } } ^ { \mathrm { t } }$ 代表来自相同植物不同花的花粉；ε是[0,1]均匀分布的随机数。

e)求得当前最优解和最优解的适应度值。

f)对当前最优解按照式（6）进行处理，得到折射点 $\mathrm { Y } _ { 1 }$ ，然后对该点的函数值进行判断。若优于当前最优解，则更新全局最优解和最优解的适应度值，反之不变。

g)判断是否满足实验设置的最大迭代次数或固定收敛精度，若满足则输出结果结束算法，否则转至c)。

# 3 仿真实验及结果分析

为了检验refHFPA算法的有效性，利用八个测试函数在MATLAB的环境下进行测试，并将其测试结果与FPA、HSFPA、refrFPA算法进行比较。其中，八个测试函数如下：

(1) $f _ { 1 } ( x ) = \sum _ { i = 1 } ^ { n } { x _ { i } } ^ { 2 }$ ,x ∈[-5.12,5.12],i=1,2,3..,n,该函数的理  
论最优值为0。(2） $f _ { 2 } \left( x \right) = \sum _ { i = 1 } ^ { n } ( \left[ x _ { i } + 0 . 5 \right] ) ^ { 2 } , x _ { i } \in \left[ - 1 0 0 , 1 0 0 \right] , \mathrm { i = 1 } , 2 , 3 . . . , \mathrm { n } ,$   
该函数的理论最优值为0。(3） $f _ { 3 } ( x ) = \sum _ { i = 1 } ^ { n } \left| x _ { i } \sin ( x _ { i } ) + 0 . 1 x _ { i } \right| , x _ { i } \in [ - 1 0 , 1 0 ] , { \mathrm { ~ } } \vec { \chi } _ { \vec { \Sigma } } \vec { \smash { \scriptstyle { \vert \vec { \Sigma } \vec { k } \vert } ^ { 3 } } }$ 数的  
理论最优值为0。(4) $f _ { 4 } ( x ) = \frac { 1 } { 4 0 0 0 } \sum _ { i = 1 } ^ { n } { x _ { i } } ^ { 2 } + 1 - \prod _ { i = 1 } ^ { n } \cos ( \frac { x _ { i } } { \sqrt { i } } ) , x _ { i } \in [ - 6 0 0 , 6 0 0 ] ,$   
$\mathsf { i } { = } 1 , 2 , 3 . . . \mathsf { n } .$ 该函数的理论最优值为0。(5） $f _ { 5 } ( x ) = \sum _ { i = 1 } ^ { n } \left| x _ { i } - { \frac { 1 } { i } } \right| , \quad x _ { i } \in [ - 1 0 , 1 0 ] { \mathrm { ~ } } , { \mathrm { i = 1 } } , 2 , 3 . . . , \mathrm { { n } } , { \mathrm { i } } \dot { \Xi } { \mathrm { ~ � } } \dddot { \ddag } \dddot { \ddag } { \mathrm { ~ } }$   
理论最优值为0。(6） $\mid f _ { 6 } ( x ) = 2 0 + e - 2 0 \exp ( - 0 . 2 \sqrt { \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } } x _ { i } } ^ { 2 } ) - \exp ( \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } } \cos ( 2 \pi x _ { i } ) ) \ ,$

$x _ { _ i } \in [ - 3 2 , 3 2 ] \mathrm { ~ , i = 1 , 2 , 3 \ldots , n , }$ 该函数的理论最优值为0。

(7) $f _ { 7 } \left( x \right) = \prod _ { i = 1 } ^ { n } \left| x _ { i } \right| + \sum _ { i = 1 } ^ { n } \left| x _ { i } \right| , x _ { i } \in \left[ - 1 0 , 1 0 \right] , { \mathrm { i } } { = } 1 , 2 , 3 { \ldots } , { \mathrm { n } } , { \mathrm { i } } \dot { \mathcal { Z } } \left| \overrightarrow { \mathcal { X } } \right| \stackrel { { \mathrm { d } } } { \approx } 0$ 的理论最优值为0。

（8） $f _ { 8 } ( x ) = \sum _ { i = 1 } ^ { n } ( 1 0 ^ { 6 } ) ^ { \frac { i - 1 } { n - 1 } } x _ { i } ^ { 2 } , x _ { i } \in \left[ - 1 0 0 , 1 0 0 \right] , \mathrm { i = 1 } , 2 , 3 . . . , \mathrm { n } ,$ 该函数的理论最优值为0。

![](images/f707754780d1db740b15106c7bc0a879533801a8bcc7a5a6e6db2f19d6cd921b.jpg)  
图3refrHFPA算法流程

# 3.1参数f的分析与选取

参数f的取值直接影响折射解在X轴上的位置，取f在预估范围[0,1]内，对单峰函数 $f _ { 1 }$ 和 $f _ { 2 }$ 、多峰函数 $f _ { 4 }$ 和 $f _ { 6 }$ 独立运行20次。判断f取何值时可以有效帮助算法跳出局部最优。本实验设置种群数为20，最大迭代次数为300，refrHFPA算法参数中 $\mathrm { \bf p } { = } 0 . 2 ^ { [ 1 1 ] }$ ， $\lambda { = } 1 . 5$ ， $\mathrm { H M C R } { = } 0 . 9 5$ ，PAR $_ { : = 0 . 3 }$ ， $\mathrm { B W } { = } 0 . 0 1$ ， $\scriptstyle \mathtt { n } = 2 ^ { [ 8 ] }$ 。实验结果如表1所示。

表1f取不同值时refrHFPA算法的性能分析  

<html><body><table><tr><td>函数</td><td>维数</td><td>f</td><td>最优值</td><td>平均值</td><td>最差值</td></tr><tr><td rowspan="6">f</td><td rowspan="6">30</td><td>0.2</td><td>2.492e-01</td><td>5.4612e-01</td><td>9.545e-01</td></tr><tr><td>0.4</td><td>1.675e-01</td><td>7.1101e-01</td><td>1.2157</td></tr><tr><td>0.6</td><td>3.5e-03</td><td>2.3523e-02</td><td>1.315e-01</td></tr><tr><td>0.8</td><td>6.1e-04</td><td>3.7303e-03</td><td>8.6e-03</td></tr><tr><td>1</td><td>6.62e-04</td><td>1.6072e-03</td><td>3.1e-03</td></tr><tr><td>0.2</td><td>1.6512e+02</td><td>2.7669e+02</td><td>3.6554e+02</td></tr><tr><td>30</td><td>0.4</td><td>1.0628e+02</td><td>3.0286e+02</td><td>7.2461e+02</td></tr><tr><td rowspan="6">f</td><td></td><td>0.6 8.3564</td><td>1.5407e+01</td><td></td><td>2.4545e+01</td></tr><tr><td></td><td>0.8</td><td>3.0175</td><td>8.2552</td><td>4.5821e+01</td></tr><tr><td></td><td>1</td><td>2.8153</td><td>4.9436</td><td>7.2475</td></tr><tr><td></td><td>0.2</td><td>2.4283</td><td>3.82006</td><td>5.0583</td></tr><tr><td></td><td>0.4</td><td>1.7756</td><td>3.71579</td><td>6.7429</td></tr><tr><td>30</td><td>0.6</td><td>1.0333</td><td>1.06872</td><td>1.1426</td></tr><tr><td rowspan="6">f</td><td></td><td>0.8</td><td>3.353e-01</td><td>8.3804e-01</td><td>1.0272</td></tr><tr><td></td><td>1</td><td>2.949e-01</td><td>7.7102e-01</td><td>1.0487</td></tr><tr><td></td><td>0.2</td><td>5.2427</td><td>6.94923</td><td>1.0569e+01</td></tr><tr><td>30</td><td>0.4</td><td>4.4971</td><td>7.02611</td><td>1.1209e+01</td></tr><tr><td></td><td>0.6</td><td>8.233e-01</td><td>2.49892</td><td>4.2241</td></tr><tr><td></td><td>0.8</td><td>3.862e-01</td><td>9.3248e-01</td><td>1.6789</td></tr><tr><td></td><td>1</td><td></td><td>1.898e-01</td><td>5.7248e-01</td><td>1.253</td></tr></table></body></html>

由表1可以看出，参数f取值[0.6,1]相比[0,0.4]寻优结果有1\~3个数量级的提高。为了进一步确定参数f取值对算法寻优结果的影响，实验采用 $f _ { 1 }$ 与 $f _ { 4 }$ ，收敛情况如图4所示。

![](images/a3e9003d8aac929bd25feb6dc1e275754e9f988e466f4e2dcc4bc46d3e197b72.jpg)  
图4不同f取值测试函数的收敛曲线

由图4可见，f值在[0.8,1内时收敛速度更快，因此将f按照式（10）进行取值，初始值设为0.8。

$$
f = 0 . 8 + 0 . 2 \times r a n d ( )
$$

# 3.2测试方案

本文共设计五种仿真实验方案：第一种是固定种群数量及迭代次数，通过八种测试函数测试FPA、HSFPA、refrFPA 及refrHFPA算法在低维环境下的寻优能力；第二种是设定一个高维的实验环境，判断refrHFPA算法在高维环境下是否可以得到较好的收敛精度；第三种是固定收敛精度，对比这四种算法的最小收敛次数、平均收敛次数和收敛率；第四种是refrHFPA算法在不同维度下，判断其是否具有较低的时间复杂度；第五种是将refrHFPA算法与近两年改进后的FPA算法进行对比，验证本文算法的可行性。

本文设置的实验参数如下：

FPA算法中转换概率 $\scriptstyle \mathtt { p } = 0 . 8 ^ { [ 1 ] }$ ， $\lambda { = } 1 . 5$ 。

HSFPA 算法中 $\scriptstyle \mathtt { p } = 0 . 8 ^ { [ 1 ] }$ ， $\lambda { = } 1 . 5$ ， $\mathrm { H M C R } { = } 0 . 9$ ，PAR $_ { = 0 . 3 }$ ，$\mathrm { B W } { = } 0 . 1$ 。refrFPA 算法中 $\mathsf { p } { = } 0 . 2 ^ { [ 1 1 ] }$ ， $\lambda { = } 1 . 5$ ， $\scriptstyle \mathtt { n } = 2 ^ { [ 8 ] }$ ， $\mathrm { f } { = } 0 . 8$ ，。refrHFPA算法参数设置与小节3.1相同。

# 3.2.1固定迭代次数性能分析

1）低维下的性能分析

本文实验方案设置种群数为20，迭代次数为1000， $f _ { 3 }$ 维数为10，其余函数维数为30。每种算法对每个测试函数均独立运行50次，计算其最优值、最差值、平均值和寻优成功率。其中寻优成功的标准是实际最优值与理论最优值的差值小于0.001。实验结果如表2所示。

表2refrHFPA算法在低维上的性能分析  

<html><body><table><tr><td>函数</td><td>算法</td><td>平均值</td><td>最差值</td><td>最优值</td><td>成功率</td></tr><tr><td rowspan="4">f</td><td>FPA</td><td>2.74751</td><td>4.483</td><td>1.5283</td><td>0</td></tr><tr><td>HSFPA</td><td>0.06378</td><td>0.13458</td><td>0.01626</td><td>0</td></tr><tr><td>refrFPA</td><td>1.8486e-08</td><td>4.4378e-08</td><td>3.426e-09</td><td>100%</td></tr><tr><td>refrHFPA</td><td>9.4645e-12</td><td>1.6008e-10</td><td>7.5141e-15</td><td>100%</td></tr><tr><td rowspan="4">f</td><td>FPA</td><td>1.2752e+03</td><td>3.3109e+03</td><td>1.0687e+02</td><td>0</td></tr><tr><td> HSFPA</td><td>2.97996-041</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>4.754e-01</td><td>1.17231e-04</td><td>92.8%</td></tr><tr><td>refrHFPA</td><td>2.7042e-05</td><td>1.3952e-04</td><td>2.5498e-06</td><td>100%</td></tr><tr><td rowspan="4">f</td><td>FPA</td><td>1.48352</td><td>2.429</td><td>5.389e-01</td><td>0</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>reSFPA</td><td>5.8429-03</td><td>3.62-02</td><td>1.9e-03</td><td>００</td></tr><tr><td>refrHFPA</td><td>9.1811e-09</td><td>8.6994e-08</td><td>3.3573e-10</td><td>100%</td></tr><tr><td rowspan="4">f4</td><td>FPA</td><td>1.4417e+01</td><td>1.1886e+02</td><td>4.77</td><td>0</td></tr><tr><td>reSFPA</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>5.37203</td><td>4.9232</td><td>4.1.10506</td><td>50%</td></tr><tr><td>refrHFPA</td><td>1.4265e-10</td><td>5.89e-09</td><td>5.9064e-14</td><td>100%</td></tr><tr><td rowspan="4">f</td><td>FPA</td><td>1.3112e+01</td><td>1.8652e+01</td><td>9.1526</td><td>0</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td> HSFPA</td><td>2.016703</td><td>1.403</td><td>1.6329</td><td>００</td></tr><tr><td>refrHFPA</td><td>5.1908e-04</td><td>9.3451e-04</td><td>2.6926e-04</td><td>100%</td></tr><tr><td rowspan="4">f</td><td>FPA</td><td>5.81155</td><td>7.9429</td><td>2.8798</td><td>0</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>reSFPA</td><td>7.951602</td><td>7.4.4601</td><td>8.2.03604</td><td>01%</td></tr><tr><td>refrHFPA</td><td>2.4028e-05</td><td>4.0876e-05</td><td>1.8607e-05</td><td></td></tr><tr><td rowspan="4">f</td><td>FPA</td><td>1.4951e+1</td><td>2.2939e+1</td><td>9.4265</td><td>100% 0</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>HSFPA</td><td>7.5146-95</td><td>1.2.631104</td><td>2.712e-01</td><td>10%</td></tr><tr><td>refrHFPA</td><td>1.248e-07</td><td>1.5261e-06</td><td>4.3813e-09</td><td>100%</td></tr><tr><td rowspan="4">f</td><td>FPA</td><td>1.0406e+05</td><td>2.8598e+05</td><td>3.392e+04</td><td>0</td></tr><tr><td> HSFPA</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>4.7374e-04</td><td>7.23670404</td><td>1.93604304</td><td>００</td></tr><tr><td>refrHFPA</td><td>2.6904e-07</td><td>2.9884e-06</td><td>9.7789e-11</td><td>100%</td></tr></table></body></html>

从表2可以看出，针对本文选取的测试函数，refrHFPA算法的最优值、最差值及平均值均优于FPA、HSFPA和refrFPA算法；除 $f _ { 6 }$ 外，HSFPA 较于FPA算法，寻优结果均有1\~2个数量级的提高；除 $f _ { 3 }$ 外，对于不同的测试函数refrFPA算法较于原算法均有4\~8个数量级的提高。此外，refrHFPA算法对于这八种测试函数的寻优率达到 $100 \%$ ，并且最优值、最差值和平均值也远高于其他三种算法。为了更直观地比较refrHFPA算法与其他三种算法寻优能力，本文对于八个测试函数的收敛情况如图5所示。

![](images/2538cfe6b5454f4d3dddba8832429461221614dc7bf43129ab6c8b8dd15d0704.jpg)  
图5四种算法对于测试函数的收敛曲线

从图5可以看出，HSFPA算法在对测试函数 $f _ { 5 } - f _ { 7 }$ 进行测试时陷入局部最优，但refrHFPA算法却能很好地跳出局部最优，说明引入折射定理可以有效的增加种群多样性，帮助算法跳出局部最优，提升算法的收敛速度和寻优精度。

# 2）高维下的性能分析

目前处理的很多数据多为高维数据，如多媒体图形图像和视频数据等，本文算法在高维环境下进行实验。维数设为100，迭代次数设为4000，其余参数不变。对于每个测试函数，将原花朵授粉算法与本文提出的花朵授粉算法均独立实验50次，若实际最优值与理论最优值的差值小于0.001时代表寻优成功。实验结果如表3所示。

表3refrHFPA算法在高维上的性能分析  

<html><body><table><tr><td>函数</td><td>维数</td><td>算法</td><td>平均值</td><td>最差值</td><td>最优值</td><td>成功率</td></tr><tr><td rowspan="2">f</td><td>100</td><td>FPA</td><td>5.4706e+03</td><td>9.8813e+03</td><td>2.8358e+03</td><td>0</td></tr><tr><td></td><td>refrHFPA</td><td>1.5171e-07</td><td>3.586e-07</td><td>4.5143e-08</td><td>100%</td></tr><tr><td rowspan="2">f4</td><td rowspan="2">100</td><td>FPA</td><td>5.1105e+01</td><td>8.8088e+01</td><td>3.1268e+01</td><td>0</td></tr><tr><td>refrHFPA</td><td>2.5373e-13</td><td>3.6189e-12</td><td>3.3307e-16</td><td>100%</td></tr><tr><td rowspan="2">f</td><td rowspan="2">100</td><td>FPA</td><td>5.6286</td><td>9.3972</td><td>2.8912</td><td>0</td></tr><tr><td>refrHFPA</td><td>1.8174e-05</td><td>1.8273e-05</td><td>1.8172e-05</td><td>100%</td></tr><tr><td rowspan="2">f</td><td rowspan="2">100</td><td>FPA</td><td>4.7518e+07</td><td>8.7437e+07</td><td>1.9636e+07</td><td>0</td></tr><tr><td>refrHFPA</td><td>5.6762e-06</td><td>1.9884e-04</td><td>7.2084e-12</td><td>100%</td></tr></table></body></html>

表3表明，在高维环境下refrHFPA与FPA算法相比，在寻优精度上有5\~15个数量级的提高。因此refrHFPA算法可以跳出局部最优，不易随着维数的增加而陷入“维灾难”。

# 3.2.2固定收敛精度性能分析

收敛率是寻优成功的次数占实验总次数的百分比。为了验证refrHFPA算法的收敛性，在固定精度的前提下，对每个测试函数独立运行50次，将其最小收敛代数、平均收敛代数、收敛率与FPA、HSFPA、refrFPA算法相比较。实验中四种算法的种群数均为20，维数设定为10，最大迭代次数为2500。实验结果如表4所示。

表4四种算法在固定收敛精度下的性能分析  

<html><body><table><tr><td>函数</td><td>维数</td><td>固定精度</td><td>算法</td><td>最小收敛代数 平均收敛代数</td><td></td><td>收敛率</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-05</td><td>FPA</td><td>961</td><td>1225.58</td><td>100%</td></tr><tr><td>HSFPA</td><td>582</td><td>685.97</td><td>100%</td></tr><tr><td>refrFPA</td><td>224</td><td>290.43</td><td>100%</td></tr><tr><td>refrHFPA</td><td>161</td><td>216.18</td><td>100%</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-07</td><td>FPA</td><td>1760</td><td>2059.17</td><td>82%</td></tr><tr><td>HSFPA</td><td>1076</td><td>1182.36</td><td>100%</td></tr><tr><td>refrFPA</td><td>633</td><td>666.14</td><td>100%</td></tr><tr><td>refrHFPA</td><td>558</td><td>601.08</td><td>100%</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-03</td><td>FPA</td><td>fail</td><td>fail</td><td>0</td></tr><tr><td>HSFPA</td><td>927</td><td>1193.71</td><td>100%</td></tr><tr><td>refrFPA</td><td>fail</td><td>fail</td><td>0</td></tr><tr><td>refrHFPA</td><td>325</td><td>397.36</td><td>100%</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-07</td><td>FPA</td><td>fail</td><td>fail</td><td>0</td></tr><tr><td>HSFPA</td><td>fail</td><td>fail</td><td>0</td></tr><tr><td>refrFPA</td><td>fail</td><td>fail</td><td>0</td></tr><tr><td>refrHFPA</td><td>202</td><td>594.38</td><td>100%</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-03</td><td>FPA</td><td>1076</td><td>1165.2</td><td>100%</td></tr><tr><td>HSFPA</td><td>872</td><td>959.79</td><td>100%</td></tr><tr><td>refrFPA</td><td>437</td><td>455.43</td><td>100%</td></tr><tr><td>refrHFPA</td><td>304</td><td>356.72</td><td>100%</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-03</td><td>FPA</td><td>1542</td><td>2056.3</td><td>86%</td></tr><tr><td>HSFPA</td><td>910</td><td>1045.07</td><td>100%</td></tr><tr><td>refrFPA</td><td>500</td><td>730.29</td><td>100%</td></tr><tr><td>refrHFPA</td><td>240</td><td>441.2</td><td>100%</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-03</td><td>FPA</td><td>1856</td><td>2115.23</td><td>62%</td></tr><tr><td>HSFPA</td><td>844</td><td>929.43</td><td>100%</td></tr><tr><td>refrFPA</td><td>258</td><td>344.36</td><td>100%</td></tr><tr><td>refrHFPA</td><td>209</td><td>294.96</td><td>100%</td></tr><tr><td rowspan="4">f</td><td rowspan="4">10</td><td rowspan="4">1.0e-07</td><td>FPA</td><td>2271</td><td>2479.1</td><td>20%</td></tr><tr><td>HSFPA</td><td>1486</td><td>1611.21</td><td>100%</td></tr><tr><td>refrFPA</td><td>465</td><td>606</td><td>100%</td></tr><tr><td>refrHFPA</td><td>450</td><td>582.6</td><td>100%</td></tr></table></body></html>

从表4可以看出，对于这八个测试函数，HSFPA、refrFPA与refrHFPA算法无论是最小收敛代数还是平均收敛代数均优于原算法。由此可见HS算法与折射定理的引进对于FPA算法均是有效的。此外，refrHFPA算法的最小收敛代数和平均收敛代数在四种算法中最小，且收敛率均为 $100 \%$ 。因此refrHFPA算法的收敛性要优于其他三种算法，并具有有效性。

# 3.2.3refrHFPA算法的时间复杂度分析

本文将refrHFPA与FPA算法在相同环境下，通过运行时间来观察本文算法是否满足时间复杂度较低的要求。实验中种群数量设置为10，迭代次数为300，维数分别设为10、100、200，每种算法对于每种测试函数均独立运行20次。refrHFPA与 FPA算法在不同维度下的最小运行时间与平均运行时间如表5所示。

表5refrHFPA算法时间复杂度分析  

<html><body><table><tr><td>函数</td><td>维数</td><td>算法</td><td>最优值</td><td>平均值</td></tr><tr><td rowspan="5">f</td><td>10</td><td>FPA</td><td>0.302</td><td>0.31624</td></tr><tr><td></td><td>refrHFPA</td><td>0.902</td><td>0.94136</td></tr><tr><td>100</td><td>FPA</td><td>0.603</td><td>0.62993</td></tr><tr><td></td><td>refrHFPA</td><td>1.662</td><td>1.70079</td></tr><tr><td>200</td><td>FPA refrHFPA</td><td>0.929</td><td>0.966</td></tr><tr><td rowspan="5">f4</td><td>10</td><td>FPA</td><td>2.453 0.339</td><td>2.53729 0.3765</td></tr><tr><td></td><td>refrHFPA</td><td>0.903</td><td>1.30135</td></tr><tr><td>100</td><td>FPA</td><td>0.703</td><td>0.74143</td></tr><tr><td></td><td>refrHFPA</td><td>1.662</td><td>2.7271</td></tr><tr><td></td><td>FPA</td><td>1.081</td><td>1.12068</td></tr><tr><td rowspan="5">f</td><td>200</td><td>refrHFPA</td><td>2.453</td><td>4.18715</td></tr><tr><td>10</td><td>FPA refrHFPA</td><td>0.34</td><td>0.35907</td></tr><tr><td>100</td><td>FPA</td><td>1.238 0.698</td><td>1.35307 0.73064</td></tr><tr><td></td><td>refrHFPA</td><td>2.458</td><td>2.60107</td></tr><tr><td></td><td>FPA</td><td>1.079</td><td>1.15293</td></tr><tr><td rowspan="5">f</td><td>200</td><td>refrHFPA</td><td>3.838</td><td>4.02456</td></tr><tr><td>10</td><td>FPA</td><td>0.311</td><td>0.32585</td></tr><tr><td></td><td>refrHFPA</td><td>1.041</td><td>1.15021</td></tr><tr><td>100</td><td>FPA</td><td>0.652</td><td>0.68729</td></tr><tr><td></td><td>refrHFPA</td><td>2.15</td><td>2.41129</td></tr><tr><td rowspan="2"></td><td>200</td><td>FPA</td><td>1.005</td><td>1.0425</td></tr><tr><td></td><td>refrHFPA</td><td>3.245</td><td>3.4529</td></tr></table></body></html>

从表5可以看出，refrHFPA与FPA算法相比运行时间略长，但refrHFPA算法无论在低维还是高维环境下的寻优精度都远高于FPA算法，而且refrHFPA算法的最小运行时间与平均运行时间仍然较短，所以可以看出refrHFPA算法是可行的。

# 3.2.4改进智能算法比较实验

本文将refrHFPA算法与文献[6,7]相比较，测试函数为文献中的部分函数。本实验方案的参数设置与参考文献相同，GMPFPA和DEFPA算法的实验数据均来自于参考文献，结果如表6和7所示。

表6refrHFPA算法与GMPFPA算法优化性能对比  

<html><body><table><tr><td>函数</td><td>维数</td><td>算法</td><td>平均值</td><td>最差值</td><td>最优值</td></tr><tr><td rowspan="2">f</td><td rowspan="2">30</td><td>GMPFPA</td><td>1.4323e-18</td><td>1.5429e-17</td><td>1.0003e-30</td></tr><tr><td>refrHSFPA</td><td>7.5053e-30</td><td>4.2212e-29</td><td>3.4197e-33</td></tr><tr><td rowspan="2">f</td><td rowspan="2">30</td><td>GMPFPA</td><td>1.1166e-13</td><td>1.3006e-12</td><td>7.886e-13</td></tr><tr><td>refrHSFPA</td><td>2.7426e-17</td><td>1.6592e-16</td><td>2.2627e-18</td></tr><tr><td rowspan="2">f</td><td rowspan="2">30</td><td>GMPFPA</td><td>1.3881e-10</td><td>1.467e-09</td><td>4.4409e-15</td></tr><tr><td>refrHSFPA</td><td>5.7731e-15</td><td>1.0658e-14</td><td>3.5527e-15</td></tr><tr><td rowspan="2">f</td><td rowspan="2">30</td><td>GMPFPA</td><td>1.5011e-16</td><td>2.3621e-15</td><td>2.7323e-21</td></tr><tr><td>refrHSFPA</td><td>6.0552e-19</td><td>2.7656e-18</td><td>2.2322e-20</td></tr></table></body></html>

表7refrHFPA算法与DEFPA算法优化性能对比  

<html><body><table><tr><td>函数</td><td>维数</td><td>算法</td><td>平均值</td><td>最差值</td><td>最优值</td></tr><tr><td rowspan="2">f</td><td rowspan="2">30</td><td>DEFPA</td><td>2.6347e-17</td><td>1.0206e-16</td><td>7.4022e-18</td></tr><tr><td>refrHSFPA</td><td>1.8415e-32</td><td>6.587e-31</td><td>1.0809e-34</td></tr><tr><td rowspan="2">f4</td><td rowspan="2">30</td><td>DEFPA</td><td>5.0093e-15</td><td>1.4322e-14</td><td>9.992e-16</td></tr><tr><td>refrHSFPA</td><td>0</td><td>0</td><td>0</td></tr><tr><td rowspan="2">f</td><td rowspan="2">30</td><td>DEFPA</td><td>3.359e-08</td><td>6.9112e-08</td><td>1.4435e-08</td></tr><tr><td>refrHSFPA</td><td>7.9935e-15</td><td>2.1316e-14</td><td>3.5527e-15</td></tr><tr><td rowspan="2">f</td><td rowspan="2">30</td><td>DEFPA</td><td>9.2161e-31</td><td>2.2095e-30</td><td>3.66e-31</td></tr><tr><td>refrHSFPA</td><td>4.6329e-19</td><td>1.8917e-18</td><td>1.5876e-20</td></tr></table></body></html>

由表6可以看出，refrHFPA算法相较于GMPFPA算法，单峰函数有12个数量级的提高，多峰函数有3\~5个数量级的提高。由表7可以看出，除 $f _ { 7 }$ 外，refrHFPA算法较于DEFPA算法，在寻优结果上均有6\~16个数量级的提高。因此，在实验条件相同的情况下，无论是单峰函数还是多峰函数，refrHFPA算法寻优结果优于参考文献[6,7]算法。

# 4 结束语

花朵授粉算法作为新型群智能算法，也与其他智能算法一样存在收敛速度慢、寻优精度低的缺点。针对这些不足，本文将 HS 算法引入花朵授粉算法，将其最优解作为算法迭代的初始解，以提高初始解的质量。利用折射定理对当前最优解进行折射，以提升算法的全局搜索能力，提高寻优精度。实验结果表明，本文算法与原算法和其他改进算法相比，收敛速度较快、最优解质量较高，具有一定的可行性和有效性。以后，将在花朵授粉算法的参数值设置、推广算法应用领域等方面做进一步研究。

# 参考文献：

[1]Yang Xinshe.Flower pollination algorithm for global optimization [C]// Proc of International Conference on Unconventional Computation and

Natural Computation.2012:240-249.   
[2]Zhou Yongquan,Wang Rui.An improved flower pollination algorithm for optimal unmanned undersea vehicle path planning problem [J]. International Journal of Pattern Recognition and Artificial Intelligence,2016,30 (4): 1659010.   
[3]贺圣彦，曹中清，余胜威．基于花授粉算法的 PID 参数优化[J].计算 机工程与应用,2016,52(17):59-62.   
[4]Abdel-Baset M, Hezam IM.An improved flower pollination algorithm for ratios optimization problems [M]//Applied Mathematics and Information Sciences Letters.2015: 83-91.   
[5]卞京红，贺兴时，杨新社．基于萤火虫算法的自适应花授粉优化算法 [J].计算机工程与应用,2016,52(21):162-167.   
[6]肖辉辉，万常选，段艳明，等．融合高斯变异和PoWell法的花朵授粉优 化算法[J].计算机科学与探索,2017,11(3):478-490.   
[7]肖辉辉，万常选，段艳明．一种改进的新型元启发式花朵授粉算法[J] 计算机应用研究,2016,33(1):126-131.   
[8] 邵鹏，吴志健，周炫余，等．基于折射原理反向学习模型的改进粒子群 算法[J]．电子学报,2015,43(11):2137-2144.   
[9]Griffiths,David J. Introduction to Electrodynamics [M].[S.1.] :PrentIce Hall,1998. 386-389.   
[10] Geem Z W,Kim JH,Loganathan G V.A new heuristic optimization algorithm: harmony search [J]. Simulation,2001,76(2):60-68.   
[11] Draa A.On the performances of the flower polination algorithm-qualitative and quantitative analyses [J].Elsevier Science Publishers B.V.,2O15,34 (C): 349-371.   
[12]曲良东，何登旭，黄勇．自适应改进和声——单纯形进化算法研究[J]. 计算机应用研究,2013,30(3):676-678.   
[13] Zhao S Z,Suganthan P N,Pan QK,et al.Dynamic multi-swarm particle swarm optimizer with harmony search[J].Expert Systems with Applications, 2011,38 (4): 3735-3742.   
[14]He X,Yang Xinshe,Karamanoglu M,et al.Global convergence analysis of the flower polination algorithm:a discrete-time markov chain approach [J]. Procedia Computer Science,2017,108:1354-1363.   
[15] Zaem D,Mezioud C,Draa A.On the efficiency of the binary flower pollination algorithm:application on the antenna positioning problem [J]. Applied Soft Computing,2016,47 (C): 395-414.