# 混合蛙跳算法的最优参数研究

孟凯露ä，尚俊娜‘，岳克强b(杭州电子科技大学a.通信工程学院;b．电子信息学院，杭州310018)

摘要：介绍了混合蛙跳算法的最优参数选取过程。在种群总数以及总迭代数给定的情况下，分组数、允许青蛙个体位置改变的最大步长和组内迭代数是影响混合蛙跳算法优化性能的重要参数。不同的参数值选取会对算法的结果产生不同的影响。对混合蛙跳算法中这3个参数的值进行选择，首先进行了参数对算法的影响分析，其次取每个参数的 3个常用值，利用正交试验设计法设计三因素三水平的实验；接着设置相同的环境条件，用CEC2013实参函数测试集验证不同参数组合算法的寻优性能。最后以最优值误差的 Friedman 检测的得分为评价指标，选出最优参数组合(20，5，10)，为后续算法改进及应用打下基础。

关键词：混合蛙跳算法；正交试验；CEC2013评价标准；参数选择 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.05.0304

# Research on optimal parameters of shuffled frog leaping algorithm

Meng Kailua, Shang Junnaa, Yue Keqiangb† (a.CollegeofelecommunicationEngineering,b.ollgeoflectronicformationHangzhouianziUniversityzou 310018, China)

Abstract: This paper introduced theoptimal parameter selection process ofthe hybrid frog leaping algorithm.Given thetotal numberofpopulations andthe totalnumberofiterations,thenumberof groups,the maximum step sizethat alows theindividual positionofthefrogtochange,andthenumberofiterations withinthe groupareimportantparameters thatafecttheoptimization performanceofthehybridfrog leapingalgorithm.Different parameter setings would have diferent effects ontheresults.This article choosed thevalueofthreeparameters inthe shufled frog leaping algorithm.Firstanalyzed theinfluenceofparameters onthealgorithm,andtook thethreecommonlyusedvaluesofeveryparameters andusedorthogonalexperimentaldesign method todesigthe thre-factor and three-level experiment.Then under thesame environmental conditions,thispaper used the CEC2013realparameterfunction testset toverifytheoptimizationperformanceofdifferentparametercombinationalgorithms. Finaly,the article used theFriedman test scoreoftheoptimal value erorastheevaluation index.Andselectedtheoptimal parameter combination (20,5,15),which is the basis for the improvement and application of the algorithm.

Key Words: Shufled frog leapingalgorithm; Orthogonalexperimental; CEC20l3Evaluation standard; Parameterselection

# 0 引言

一般来说，群体智能优化算法中都包含着多个可以自由设定的参数，不同的参数选择会对算法的收敛能力和寻优性能造成一定的影响。因此，对算法中的参数取值进行研究具有十分重要的价值。在算法性能进行比较的时候，需要一个合理、全面的评价标准，对算法解决问题的正确率、效率和有效性等方面进行评价。文献[1]提出了一种动态参数蚁群算法，其建立在Qos(QualityofService)评估模型之上，通过该模型得到适应度函数 $F$ ， $F$ 越小结果越优，并通过改变参数在不同阶段的值来使算法获得更快的收敛效率。文献[2]提出了自适应遗传算法的SVM参数选取方法，根据适应度值自动调整交叉概率和变异概率，减少了遗传算法的收敛时间并且提高了遗传算法的精度，从而确保了SVM参数选择的准确性。

混合蛙跳算法（shufled frog leaping algorithm，SFLA）[3]是一种全新的启发式群体进化算法，由Eusuff和Lansey于2003年提出。其结合了基于模因（meme）进化的模因算法（memeticalgorithm,MA）[4]和基于群体行为的粒子群算法（particle swarmoptimization,PSO）[5]两种群体智能优化算法的优点，且具有多个可以调整的参数，因此具有研究的意义与价值。目前已经有大量学者对SFLA进行了研究，并将其应用到各个学科的研究领域，但至今还没有学者用全面的评价标准对其参数的选择进行研究。不管是对于SFLA自身的性能改进来说还是将其应用到其他研究领域时，对其参数的研究都具有十分重要的价值和意义。

因此，本文主要对SFLA的最优参数选择展开一系列的实验和分析，从测试问题的选择与设计、实验方法的确定及深入展开和利用SPSS软件进行实验结果的统计分析三方面进行展开，最终选出SFLA的最优参数组合。

# 1 混合蛙跳算法

# 1.1混合蛙跳算法介绍

SFLA的基本思想是：生成 $N$ 只青蛙的初始化种群，并在位置范围内随机初始化每个个体的位置值，将其表示为P={X,X,，XN}。假设解空间的维数为s，则将第i只青蛙表示为 $X _ { i } = [ x _ { i 1 } , x _ { i 2 } , \cdots , x _ { i S } ]$ 。在形成初始化群体之后，将种群内的所有青蛙个体以适应度值为标准从大到小排列，首个具有最优适应度值的青蛙位置记为 $X _ { g }$ ；随后将整个种群分成 $m _ { p }$ 组，其中每组包含 $n _ { p }$ 只青蛙，即 $N = m \times n$ ，假设 $M ^ { k }$ 为第 $k$ 组青蛙个体的集合，则其分配过程如式（1）所示。

$$
M ^ { k } = \{ X _ { k + m ( l - 1 ) } \in P | 1 \leq l \leq n \} , 1 \leq k \leq m
$$

分组完成后，每一组中具有最优适应度值的个体位置记为$X _ { b }$ ，具有最差适应度值的个体位置记为 $X _ { \scriptscriptstyle w }$ 。对每组分别进行局部搜索，最差青蛙个体的更新公式如式（2）所示。

$$
\begin{array} { c } { { D = r \cdot ( X _ { \mathit { b } } - X _ { \mathit { w } } ) , } } \\ { { \displaystyle \Big \lbrace X _ { \mathit { w } } ^ { ' } = X _ { \mathit { w } } + D , - D _ { \mathrm { m a x } } \leq D \leq D _ { \mathrm { m a x } } } } \end{array}
$$

其中： $\boldsymbol { r }$ 表示[0,1]的随机数， $S _ { \mathrm { m a x } }$ 表示允许青蛙个体位置改变的最大步长。经过一次迭代后，如果满足 $f ( x _ { \boldsymbol { w } } ^ { \prime } ) < f ( x _ { \boldsymbol { w } } )$ ，则保留该位置值，更新该组中最差的青蛙个体；否则，用 $X _ { g }$ 替代 $X _ { b }$ ，进行式（2）的搜索过程；如果上述操作都没有使青蛙个体更新到更优的位置，则随机更新一个个体来替换 $X _ { \scriptscriptstyle w }$ 。将上述局部搜索过程重复 $L _ { \mathrm { m a x } }$ 次，完成后将所有青蛙个体重新混合并按式(1)分组，继续进行式（2）的局部搜索操作，如此重复直到结果满足收敛条件的要求或者迭代次数达到最大迭代次数值Gmax 。

SFLA 作为一种新兴的群智能优化算法，概念简单，易于实现，在工程设计和学科研究等众多领域获得了成功的应用。

# 1.2参数对算法的影响分析

由上述混合蛙跳算法介绍可知，在青蛙总数 $N$ 和种群迭代次数 $G _ { \mathrm { m a x } }$ 给定的情况下，影响混合蛙跳算法的参数主要有分组数 $m _ { p }$ （由于青蛙总数为 $N$ 一致，故不再考虑每组青蛙数 $n _ { { } _ { p } }$ ），允许青蛙个体位置改变的最大步长 $S _ { \mathrm { m a x } }$ 和组内迭代数 $L _ { \mathrm { m a x } }$ 。下面从理论上分别分析三者对算法性能的影响。

首先分析分组数 $m _ { p }$ ，如果 $m _ { p }$ 偏小，会导致子种群内部信息交换不全面，无法很好的进行局部搜索；如果 $m _ { p }$ 偏大，会使算法容易陷入局部最优。其次是允许青蛙个体位置改变的最大步长 $S _ { \mathrm { m a x } }$ ，该参数是控制算法全局搜索能力的关键因素，如果$S _ { \mathrm { m a x } }$ 偏小，会减弱算法的全局搜索能力，使算法容易陷入局部最优；如果 $S _ { \mathrm { m a x } }$ 偏大，会导致算法跳过真正的全局最优解。最后是组内迭代数 $L _ { \mathrm { m a x } }$ ，该参数的选取与 $m _ { p }$ 类似,如果 $L _ { \mathrm { m a x } }$ 偏小，会使子种群内的青蛙频繁跳跃，导致个体信息交换不够全面;如果 $L _ { \mathrm { m a x } }$ 偏大，会使子种群陷入局部最优。

# 2 测试问题的选择与设计

# 2.1测试问题

近些年来，大量的群体智能优化算法如蚁群算法[、粒子群算法、布谷鸟搜索算法[、蝙蝠算法[8等广泛应用于工程设计和学科领域[9-I的实参函数优化问题中，大大提高了解决这些问题的效率。但在这些研究中，不同的学者一般会选择不同的测试函数集，如Ackley函数、Griewank函数、Rastrigin函数、Rosenbrock函数、Quadric 函数、Shubert函数等等，没有选取一个统一、全面的评价标准，这是目前存在的一个较为严重的问题。只采用部分测试函数会对算法的研究与分析造成一定的影响；并且在不同的研究分析中，设置的环境条件不尽相同，也对结果之间的比较造成了较大的影响，不利于后续工作的展开。

针对上述情况，Suganthan 等人提出了一系列的标准化测试函数集，其中包含单峰函数、多峰函数以及复杂函数，不再只局限于部分函数集，能够全面的测试与分析一个算法的性能。由于本文SFLA的测试主要针对的是单目标实参函数优化问题，因此选用CEC2013评价标准[12]。

# 2.2 CEC2013评价标准

CEC2013实参测试函数集是Suganthan等人在2013年提出的，该集合改进了CEC2005提出的组合函数，并且加入了新的测试函数，使整体更为全面合理。该集合中共包含了28个测试函数，其中5个为单峰函数（unimodal functions），15个为基本多峰函数（basicmultimodalfunctions)，8个为复杂函数（compositionfunctions），不同类型的测试函数可以更全面地对算法性能进行测试与分析。以上测试函数的详细内容介绍如表1所示。

# 2.3实验环境设置及评价指标

由上述分析可知，环境条件设置不相同会影响算法的性能，从而对后续的比较造成较大的影响，不同情况下算法的性能一般无法进行比较。因此将该算法的所有实验环境进行统一的设定，即对其进行标准化。其中种群规模设为300；维度设为20维；独立运行次数设为100 次；搜索范围是函数域[-100,100]，包含所有函数的最优值；算法终止条件是达到最大迭代次数或收敛到的最小适应值小于 $1 0 ^ { - 6 }$ ，当小于 $1 0 ^ { - 6 }$ 时，将最小适应值设为0；算法评价指标为平均值误差，即最小适应值与理论最优值的差，具体设置如表2所示。

表1CEC201328个测试函数  

<html><body><table><tr><td></td><td>No.</td><td>Functions</td><td>f=f(x）</td></tr><tr><td></td><td>1</td><td>Sphere Function</td><td>-1400</td></tr><tr><td>Unimodal</td><td>2</td><td>Rotated High Conditioned Elliptic Function</td><td>-1300</td></tr><tr><td>Functions</td><td>3</td><td>Rotated Bent Cigar Function</td><td>-1200</td></tr><tr><td></td><td>4</td><td>Rotated Discus Function</td><td>-1100</td></tr><tr><td></td><td>5</td><td>Different Powers Function</td><td>-1000</td></tr><tr><td></td><td>6</td><td>Rotated Rosenbrock's Function</td><td>-900</td></tr><tr><td>Basic</td><td>7</td><td>Rotated Schaffers F7 Function</td><td>-800</td></tr><tr><td>Multimodal</td><td>8</td><td>Rotated Ackley's Function</td><td>-700</td></tr><tr><td>Functions</td><td>9</td><td>Rotated Weierstrass Function</td><td>-600</td></tr><tr><td></td><td>10</td><td>Rotated Griewank's Function</td><td>-500</td></tr><tr><td></td><td>11</td><td>Rastrigin's Function</td><td>-400</td></tr><tr><td></td><td>12</td><td>Rotated Rastrigin's Function</td><td>-300</td></tr><tr><td></td><td>13</td><td>Non-Continuous Rotated Rastrigin's Function</td><td>-200</td></tr><tr><td></td><td>14</td><td>Schwefel's Function</td><td>-100</td></tr><tr><td></td><td>15</td><td>Rotated Schwefel's Function</td><td>100</td></tr><tr><td></td><td>16</td><td>Rotated Katsuura Function</td><td>200</td></tr><tr><td></td><td>17</td><td>Lunacek Bi_Rastrigin Function</td><td>300</td></tr><tr><td></td><td>18</td><td>Rotated Lunacek Bi_Rastrigin Function</td><td>400</td></tr><tr><td></td><td>19</td><td>Expanded Griewank's plusRosenbrock'sFunction</td><td>500</td></tr><tr><td></td><td>20</td><td>Expanded Scaffer's F6 Function</td><td>600</td></tr><tr><td></td><td>21</td><td>Composition Function 1 (n=5,Rotated)</td><td>700</td></tr><tr><td></td><td>22</td><td>Composition Function 2 (n=3,Unrotated)</td><td>800</td></tr><tr><td></td><td>23</td><td>Composition Function 3 (n=3,Rotated)</td><td>900</td></tr><tr><td>Composition</td><td>24</td><td>Composition Function 4 (n=3,Rotated)</td><td>1000</td></tr><tr><td>Functions</td><td>25</td><td>Composition Function 5 (n=3,Rotated)</td><td>1100</td></tr><tr><td></td><td>26</td><td>Composition Function 6(n=5,Rotated)</td><td>1200</td></tr><tr><td></td><td>27</td><td>Composition Function 7(n=5,Rotated)</td><td>1300</td></tr><tr><td>28</td><td></td><td>Composition Function 8(n=5,Rotated)</td><td>1400</td></tr><tr><td></td><td>Search Range: [-100,100]D</td><td></td><td></td></tr></table></body></html>

表2实验设置及评价指标  

<html><body><table><tr><td>种群规模</td><td>300</td></tr><tr><td>维度</td><td>20</td></tr><tr><td>独立运行次数</td><td>100</td></tr><tr><td>搜索域</td><td>[-100,100]</td></tr><tr><td>算法评价指标</td><td>f(x)-f(x)</td></tr></table></body></html>

# 3混合蛙跳算法参数选择

# 3.1正交试验设计法介绍

正交试验设计（orthogonal experimental design）[13]是用来研究多因素多水平的设计方法。其根据正交性从全面试验中选出"均匀分散，齐整可比"的点进行试验，并从中挑选出最优因素水平组合。由于其具有高效、快速、经济等优点，已经在很

多领域中得到了广泛的应用。

正交表是一组完整规则的设计表格，可以减少试验的次数，提高测试的效率。比方对于一个三因素三水平的实验来说，共需要进行 $3 ^ { 3 } = 2 7$ 种组合的全面实验，但是如果利用正交表，只需要进行9次实验就能反映出全面实验的情况。

正交试验设计法具有优秀的实验设计能力，已经广泛应用到医药、化工、生物、电子、军事等各个领域，并取得了显著的价值。其提出设计了多参数多水平的实验，有效地解决了通过实验或是经验来确定智能优化算法参数的问题。

# 3.2正交试验法选择SFLA最优参数

上述1.2节中分析了参数对算法的影响，由此可以得出允许青蛙个体位置改变的最大步长 $S _ { \mathrm { m a x } }$ 主要影响算法的全局搜索能力，分组数 $m _ { p }$ 和组内迭代数 $L _ { \mathrm { m a x } }$ 主要影响算法的局部搜索能力，这三个参数过大或者过小都会降低算法的收敛性能，故应该选取合适的中间值。合适的 $S _ { \mathrm { m a x } }$ 会增强算法的全局搜索能力，使算法在搜索空间内搜索更多的可能解，收敛到更优的解；合适的 $m _ { p }$ 和 $L _ { \mathrm { m a x } }$ 会增强算法的局部搜索能力，减少算法陷入局部最优的可能，收敛到更优的解。

本小节通过正交设计法对 SFLA 的参数进行选择，并将CEC2013实际测试函数作为评价标准，具体操作步骤如下：

a）明确实验目的和评价指标。本文实验的目的是找出混合蛙跳算法在CEC2013实际问题测试函数下的最优参数组合，实验的评价指标为28个测试函数最优值误差的Friedman检测的Ranking得分，其得分越小，表明该参数组合越优。

b)选择影响因素并确定因素水平。影响混合蛙跳算法的参数主要有分组数mp，允许青蛙个体位置改变的最大步长 Smax和组内迭代数 $L _ { \mathrm { m a x } }$ ，将这3个主要参数作为正交试验设计的3个因素，并根据常用的SFLA参数设置，将每个因素分成3个不同的水平进行测试。SFLA正交试验因素水平表如表3所示。

表3基本 SFLA因素水平表  

<html><body><table><tr><td rowspan="2">水平</td><td colspan="3">因素</td></tr><tr><td>A分组数</td><td>B最大步长</td><td>C 组内迭代数</td></tr><tr><td>1</td><td>10</td><td>1</td><td>10</td></tr><tr><td>2</td><td>20</td><td>3</td><td>30</td></tr><tr><td>3</td><td>30</td><td>5</td><td>50</td></tr></table></body></html>

c)选择正交试验设计表。由于传统正交表的选择繁琐复杂，需要查询大量相关资料，效率低下。而SPSS是一款用于统计学分析运算、数据挖掘、预测分析和决策支持任务的软件，因此本文运用SPSS20.0进行正交试验表的设计以及对结果的分析，工作效率得到了有效的提高。利用SPSS软件设计的三因素三水平正交实验表如表4所示。

表4三因素三水平正交表  

<html><body><table><tr><td rowspan="2">实验号</td><td colspan="3">列号</td></tr><tr><td>1</td><td>2</td><td>3</td></tr><tr><td>1</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2</td><td>3</td><td>3</td><td>3</td></tr><tr><td>3</td><td>3</td><td>1</td><td>2</td></tr><tr><td>4</td><td>1</td><td>3</td><td>2</td></tr><tr><td>5</td><td>2</td><td>3</td><td>1</td></tr><tr><td>6</td><td>1</td><td>1</td><td>1</td></tr><tr><td>7</td><td>2</td><td>1</td><td>3</td></tr><tr><td>8</td><td>3</td><td>2</td><td>1</td></tr><tr><td>9</td><td>1</td><td>2</td><td>3</td></tr></table></body></html>

d)制定实验方案并实验。本文制定的9种实验方案不考虑各因素间的交互作用。根据表3和4得到正交试验设计的试验方案，如表5所示。本文按照表5中不同参数组合的实验方案进行实验，运行环境参数设置同2.3节的情况，最大迭代次数$G _ { \mathrm { m a x } }$ 为500。评价标准为CEC2013中28个测试函数Friedman检验的Ranking得分，因为评价指标是平均值误差，误差越小代表寻优性能越好，因此Ranking得分越小的组合代表性能越优。

表5实验方案与结果  

<html><body><table><tr><td>实验号</td><td>mp</td><td>Dmax</td><td>Ne</td><td>Rankings</td></tr><tr><td>1</td><td>20</td><td>3</td><td>30</td><td>4.40</td></tr><tr><td>2</td><td>30</td><td>5</td><td>50</td><td>5.20</td></tr><tr><td>3</td><td>30</td><td>1</td><td>30</td><td>7.40</td></tr><tr><td>4</td><td>10</td><td>5</td><td>30</td><td>3.40</td></tr><tr><td>5</td><td>20</td><td>5</td><td>10</td><td>3.20</td></tr><tr><td>6</td><td>10</td><td>1</td><td>10</td><td>7.20</td></tr><tr><td>7</td><td>20</td><td>1</td><td>50</td><td>6.20</td></tr><tr><td>8</td><td>30</td><td>3</td><td>10</td><td>4.00</td></tr><tr><td>9</td><td>10</td><td>3</td><td>50</td><td>4.00</td></tr></table></body></html>

e）实验结果分析。相比全面实验来说，正交试验设计法的次数较少，因此可以得出对数据进行处理至关重要。直观分析法、方差分析法是正交试验的两种常用分析方法。前者别名为极差分析法，根据极差值可以确定因素的主次地位；后者可以定量分析各因素对实验结果的影响程度。本文首先用直观分析法确定各因素的影响程度，得出一组较优组合；然后利用SPSS做精细的方差分析，寻找各因素的影响大小，以验证直观分析法的正确性，分析结果如表6\~8所示。

表6是单因素影响表，其中R代表极差值，其值的大小用来说明对结果的影响程度，值越大代表影响程度越大。从表中可以看出， $D _ { \mathrm { m a x } }$ 的 $\mathrm { ~ \tt ~ R ~ }$ 值为9， $m _ { p }$ 的R值为2.80， $L _ { \mathrm { m a x } }$ 的R值为1，故 $D _ { \mathrm { m a x } }$ 对结果的影响最大，三个因素对结果影响程度从大到小依次是： $D _ { \operatorname* { m a x } } > m _ { p } > L _ { \operatorname* { m a x } }$ 。并且得出了初步最优组合为A2B3C1。

表6单因素结果分析表  

<html><body><table><tr><td>结果</td><td>mp</td><td>Dmax</td><td>Lmax</td></tr><tr><td>k1</td><td>14.60</td><td>20.8</td><td>14.4</td></tr><tr><td>k2</td><td>13.80</td><td>12.4</td><td>15.2</td></tr><tr><td>k3</td><td>16.60</td><td>11.8</td><td>15.4</td></tr><tr><td>极差R</td><td>2.80</td><td>9</td><td>1</td></tr><tr><td>优水平</td><td>A2</td><td>B3</td><td>C1</td></tr><tr><td>优组合</td><td></td><td>A2B3C1</td><td></td></tr></table></body></html>

表7主体间效应的检验  

<html><body><table><tr><td colspan="6">因变量：Ranking</td></tr><tr><td>源</td><td>II 型平方和</td><td>df</td><td>均方</td><td>F</td><td>Sig.</td></tr><tr><td>校正模型</td><td>18.453a</td><td>6</td><td>3.076</td><td>3.443</td><td>.242</td></tr><tr><td>截距</td><td>225.000</td><td>1</td><td>225.000</td><td>251.886</td><td>.004</td></tr><tr><td>A</td><td>1.387</td><td>2</td><td>.693</td><td>.776</td><td>.563</td></tr><tr><td>B</td><td>16.880</td><td>2</td><td>8.440</td><td>9.448</td><td>.096</td></tr><tr><td>C</td><td>.187</td><td>2</td><td>.093</td><td>.104</td><td>.905</td></tr><tr><td>误差</td><td>1.787</td><td>2</td><td>.893</td><td></td><td></td></tr><tr><td>总计</td><td>245.240</td><td>9</td><td></td><td></td><td></td></tr></table></body></html>

<html><body><table><tr><td colspan="4">校正的总计 20.240 8 a.R方=.912（调整R方=.647)</td></tr><tr><td colspan="4">表8 估算边际均值</td></tr><tr><td></td><td>(a)A分组数</td><td></td><td>95%置信区间</td></tr><tr><td>A分组数</td><td>均值</td><td>标准误差</td><td>下限 上限</td></tr><tr><td>10</td><td>4.867</td><td>0.546 2.519</td><td>7.215</td></tr><tr><td>20</td><td>4.600</td><td>0.546 2.252</td><td>6.948</td></tr><tr><td>30</td><td>5.533 0.546</td><td>3.185</td><td>7.881</td></tr><tr><td colspan="4">（b）B最大步长</td></tr><tr><td rowspan="2">B 最大步长</td><td rowspan="2">均值 标准误差</td><td>95%置信区间</td><td></td></tr><tr><td>下限</td><td>上限</td></tr><tr><td>1</td><td>6.933</td><td>0.546</td><td>4.585 9.281</td></tr><tr><td>3</td><td>4.133</td><td>0.546 1.785</td><td>6.481</td></tr><tr><td>5</td><td>3.933</td><td>0.546 1.585</td><td>6.281</td></tr><tr><td colspan="4">(c)C组内迭代数</td></tr><tr><td>C组内迭代数</td><td>均值</td><td>标准误差</td><td>95%置信区间 上限</td></tr><tr><td>10</td><td>4.800 0.546</td><td>下限 2.452</td><td>7.148</td></tr><tr><td>30</td><td>5.067</td><td>0.546 2.719</td><td>7.415</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>50</td><td>5.133</td><td>0.546 2.785</td><td>7.481</td></tr></table></body></html>

表7和8分别是主体间效应的检验和三个因素的估算边际均值。其中F的值可以反映出各个因素对结果的影响程度，其值越大，影响程度越大；Sig.是因素的显著性，显著性越大，表示对结果的影响程度也越大。故可以得出混合蛙跳算法的参数影响排名从大到小为： $D _ { \mathrm { m a x } } > m _ { p } > L _ { \mathrm { m a x } }$ ，与表6根据极差R得出的排名一致。本文的目的是求最优的适应度函数值，即Ranking值越小，代表越优，故从表8中可以得出每个因素的最佳水平为：A分组数是20 组，B最大步长为5，C组内迭代数为10次。最终得出混合蛙跳算法的最优参数组合如表9所示。

通过上述实验结果可得，选择合适的参数可以增强算法的全局搜索能力和局部搜索能力，使其更快地收敛到更优的解，也验证了理论分析的正确性。同时也为其他不同类问题的参数选择提供了思路，首先应该明确需要选择的参数，并选取参数的常用值；其次应该选取一个全面、合理的评价标准；最后利用该评价标准对参数的不同组合进行检验，选取其中最优的组合。

表9混合蛙跳算法的最优参数组合  

<html><body><table><tr><td>mp</td><td>Dmax</td><td>Lmax</td></tr><tr><td>20</td><td>5</td><td>10</td></tr></table></body></html>

# 4 结束语

应用群体智能优化算法时常常涉及参数值的设定问题，蛙跳算法也是如此。较优的参数组合会使算法更快地收敛到更优的解，然后快速地求解相应的应用问题。本文中首先介绍了经典的CEC2013实参测试函数集，并将其作为评价标准；接着统计了蛙跳算法常用的参数组合，并在正交试验设计法设计的组合中找出最优参数组合，为该算法的改进以及应用到其他领域似灯尘础。

参考文献：   
[1]张严凯，周井泉，李强．基于动态参数蚁群算法的云制造服务组合[J]. 计算机技术与发展,2018,28(1):127-130.(Zhang Yankai,Zhou Jingquan, Li Qiang. Cloud manufacturing service composition based on dynamic parametersant colonyalgorithm [J]. Computer Technologyand Development,2018,28(1): 127-130.   
[2]刘胜，李妍妍．自适应GA-SVM参数选择算法研究[J].哈尔滨工程大 学学报,2007(4):398-402. (Liu Sheng,Li Yanyan.Parameter selection algorithm for support vector machines based on adaptive genetic algorithm [J].Journal of Harbin Engineering University,2007(04):398-402.)   
[3]Eusuff M,Lansey K,Pasha F. Shuffled frog_leaping algorithm: a memetic meta_heuristic for discrete optimization [J]. Engineering Optimization, 2005,38 (3): 129-154.   
[4] 刘翱，冯晓毅，邓旭东，等．求解 N-车探险问题的 Memetic 烟花算法 [J].控制与决策,2017,32(9):1-9.(LiuAo,Feng Xiaoyi,Deng Xudong,et al.A memetic fireworksalgorithm forsolving N-vehicleexploration problem[J]. Control and Decision,2017,32 (9): 1-9.   
[5]董丽凤，陈阳，巫光福．动态学习混沌映射的粒子群算法[J/OL].计 算机应用研究,2019,36(5):1-7. (Dong Lifeng,Chen Yang,Wu Guangfu. Chaotic mapping particle swarm optimization algorithm based on variable learning factors[J].Application ResearchofComputers,2019,36(5):1-7.)   
[6]王超，朱明，王敏．基于管制员认知负荷和改进蚁群算法的扇区动态通 行能力评估[J].计算机应用,2018,38(1):277-283.(WangChao,Zhu Ming,Wang Min. Evaluation of sector dynamic traffic capacity based on controller’scognitive loadandimprovedantcolonyalgorithm[J].Joural of Computer Applications,2018,38 (1): 277-283.)   
[7]Yang Xinshe,Suash D.Cuckoo search via levy flights [C]// Proc of World Congresson Nature& Biologically Inspired Computing.India:IEEE Publications,2009: 210-214.   
[8]Yang Xin She.A new meta-heuristic bat-inspired algorithm [J].Nature Inspired Cooperative Strategies for Optimization,2010,284: 65-74.   
[9]RahimiA,BavafaF,Aghababaei S,et al.The online parameter identification of chaotic behaviour in permanent magnet synchronous motor by selfadaptive learning bat-inspired algorithm [J].Int Jof Electrical Power & Energy Systems,2016,78 (6): 285-291.   
[10] Wang Gai Ge,Chu HC E,Mirjalili S.Three-dimensional path planning for UCAV using an improved bat algorithm[J].Aerospace Science & Technology,2016,49 (2): 231-238.   
[11]陈志敏，田梦楚，吴盘龙，等．基于蝙蝠算法的粒子滤波法研究[J]. 物理学报,2017,66(5): 47-56.(Chen Zhiming,Tian Mengchu,Wu Panlong,

etal.Intelligent particle filter based on bat algorithm[J].Acta Phys.Sin, 2017,66 (5):47-56.)

[12] LiangJJ,QuBY, SuganthanPN,et al.Problem definitions and evaluation criteria for the CEC 2O13 special session and competition on real-parameter optimization [R]. Computational Intelligence Laboratory, Zhengzhou University，Zhengzhou Chinaand"TechnicalReport”，Nanyang

Technological University, Singapore,2013.

[13]吴浩扬，常炳国，朱长纯．遗传算法的一种特例—一正交试验设计法[J]．软件学报,2001,12(1):148-153.(Wu Haoyang,Chang Bingguo,ZhuChangchun.A special case of genetic algorithm: orthogonal experimentaldesign method[J]. Journal of Software,2001,12(1): 148-153.