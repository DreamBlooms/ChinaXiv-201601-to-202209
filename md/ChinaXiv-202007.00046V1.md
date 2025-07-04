# 基于策略改进遗传算法的双星星族光谱拟合

迟焕斌¹，李忠木²，王锋1,3(1.昆明理工大学管理经济学院，云南昆明650093；2．大理大学天文研究所，云南大理671000；3．广州大学天体物理中心，广东广州510006)

摘要：双星星族光谱拟合的实质是在双星星族理论光谱库对应的参数空间进行搜索，通过最小二乘法找到与被拟合观测光谱最相近的理论光谱。快速、准确的拟合是有效利用星族合成方法处理海量星系光谱的难点和关键。为了提高双星星族光谱拟合的速度，针对双星星族光谱拟合计算量巨大、拟合效率不高等问题，本文在双星星族光谱拟合的优化模型基础上,采用策略改进的遗传算法对模型进行求解,并与 BS2fit算法和传统遗传算法进行比较。实验表明，通过改进策略的遗传算法对双星星族光谱拟合的速度平均可提高 $4 3 . 5 \%$ ，一定程度上推动了演化星族合成方法在天文研究中的应用。

关键词：光谱拟合；星系；遗传算法中图分类号：P1-092;TP391 文献标识码：A 文章编号：

# 0引言

双星星族是包含一些共同演化的双星和单星，具有相同初始金属丰度和演化年龄的恒星组合，它是对单星星族的扩展和丰富。基于双星星族模型得到的星团和星系参数结果通常更合理[1]，因此，基于双星星族的研究得到越来越多的关注。

光谱拟合是获得星系物理信息的重要方法2。随着各种巡天项目的开展和天文信息技术的发展，人们获得了越来越多的高质量光谱数据，为天体光谱拟合创造了条件，有效地推动了光谱拟合的发展。光谱拟合近年来取得了一系列成果，如文献[2]成功地用贝叶斯方法对单星星族光谱拟合估计出星系参数信息。文献[3]基于贝叶斯证据用贝叶斯模型选择的方法分析了双星星族和单星星族模型，发现双星星族模型比其它没有考虑双星相互作用的模型的光谱拟合效果好很多。文献[4]和[5]对早期星系紫外到可见波段的光谱拟合发现双星星族模型对球状星团蓝离散星观测结果有很好的解释。文献[6」Han,Z.(2007)首次通过双星星族光谱拟合发现它能很好地解释早型星系的紫外反转现象。

由于双星星族演化比传统单星星族更复杂，考虑的物理输入也更多，其对应的理论光谱库很大，一定拟合精度要求下的光谱采样率也更高，所以双星星族光谱拟合需要进行海量的计算。能否快速高效地进行双星星族光谱拟合直接影响着星族演化合成方法的应用。因此，探索基于双星星族模型的快速有效的光谱拟合方法显得十分重要。

为了解决双星星族光谱拟合速度不能满足星系演化等研究需求的问题，加快星族演化合成方法在天文研究中的推广和运用，本文基于管理策略进行了一个尝试。我们将光谱拟合转化为一类最优化问题，以最小化理论光谱和观测光谱之间的均方误差为优化目标，建立最优化模型，提出改进策略的遗传算法对模型求解，并与 BS2fit 算法[和传统遗传算法对比以验证算法的有效性。

# 1双星星族模型介绍

双星星族模型的一个主要目标是构建高精度且完备的双星星族理论光谱库。双星星族的理论光谱构建包括两个部分：模型输入参数的假设和理论光谱的计算。

如文献[1]所述,双星星族模型采用 Hurley[的快速恒星演化程序代替恒星演化轨迹，采用 BaseL3.1恒星光谱库和Chapbrier 初始质量函数，并假设每个双星的主星和次星质量比q服从0-1的均匀分布[9]。恒星形成率假设为 $\Psi ^ { ( t ) } = \Psi ^ { ( 0 ) } \cdot \mathrm { e } ^ { \mathbf { - t } / \tau ^ { [ 8 ] } }$ 的形式， $t$ 和τ分别表示星系的年龄和恒星形成的持续时标。

利用演化星族合成方法，在初始质量函数和恒星形成率已知的情况下可以计算星系中不同时刻形成的恒星数。然后，借助Hurley 的快速恒星演化程序来进行恒星演化计算。最后通过BaSeL3.1恒星样本库将恒星的演化参数转换为光谱能量分布。在完成恒星演化计算后将所包含的单颗恒星的光谱进行合成，就可以计算年龄为 $t$ 的星族在波长λ的光谱流量 $f _ { \lambda 0 }$ 。每个星族光谱流量由三个参数决定：金属丰度Z，年老星族年龄 $t _ { 1 }$ ，和年轻星族年龄 $\cdot t _ { 2 }$ 。考虑恒星速度弥散 $\wp _ { * }$ 的影响,尘埃消光（采用Calzetti等人在2000 年提出的消光理论8）,红移，银河系消光等因素，双星星族合成中在波长入处观测的光谱流量可表达为：

$$
f _ { \lambda } = [ f _ { \lambda 0 } ( z , t _ { 1 } , t _ { 2 } ) \otimes G ( v _ { \ast } , \sigma _ { \ast } ) ] p ( \tau _ { \lambda } ) r ( A _ { \lambda } ) \# ( 1 )
$$

其中， $f _ { \lambda 0 }$ 为由三个参数 $( Z , \ t _ { 1 } , \ t _ { 2 } )$ 决定星族的光谱流量, $\mathrm { G } \left( \boldsymbol { v } _ { \ast } , \boldsymbol { \sigma } _ { \ast } \right)$ 是平均值和标准偏差分别为 $v _ { * }$ 和 $\sigma _ { * }$ 一个高斯分布, $\mathrm { p } ( \tau _ { \lambda } )$ 是通过尘埃消光为 $\tau _ { \lambda }$ 的尘埃的能量百分比， $\mathrm { ~ r ~ } ( A _ { \lambda } )$ 是通过银河系消光 $A _ { \lambda }$ 后的能量比， $\otimes$ 为卷积算子。

为了简化双星星族的理论光谱库，本文将 $v _ { * } , \sigma _ { * }$ ， $\tau _ { \lambda } , A _ { \lambda }$ 的取值均设为0,仅考虑 Z, $t _ { 1 }$ ， $t _ { 2 }$ 。然而这并不影响实验目的，同样可以对比分析出所提出的该进遗传算法在光谱拟合中的表现，因为我们所采取的对比实验也是基于同样的简化的双星星族理论光谱库。

# 2基于策略改进遗传算法的双星星族光谱拟合

# 2.1双星星族光谱拟合模型

光谱拟合的目的是为了获得星系星团的物理参数信息。如上一节所述，在双星星族模型中光谱是由 $z , t _ { 1 } , t _ { 2 } , \ v _ { * } , \sigma _ { * } , \ \tau _ { \lambda } , A _ { \lambda }$ 和星族恒星质量8个参数共同决定的。其中，星系的恒星质量可由 Thomas 等(2005)[10]的拟合公式计算：

$$
\log \left( M _ { * } / M _ { \odot } \right) = 0 . 6 3 + 4 . 5 2 \log \left( \sigma _ { 0 } / \left( \mathrm { k m s ^ { - 1 } } \right) \right)
$$

式中的 $M _ { * }$ 为星系的恒星质量， $\sigma _ { 0 }$ 是恒星的速度弥散。其它参数可通过光谱拟合，即将星族的理论光谱与观测光谱进行比对从而给出星族组成的定量信息。具体任务是从理论光谱库中找到最接近观察光谱的理论光谱。在光谱拟合中，通过将观测光谱与理论光谱进行比对，并最小化理论光谱与观测光谱数据之间的差异以确定拟合最优的理论光谱，进而推断出恒星组成的主要参数。

双星星族理论光谱库有稠密的参数网格：恒星金属丰度(Z)取值为 $0 . 0 0 0 3 \widetilde { \mathrm { ~ 0 . ~ 0 3 ~ } }$ ，当 $Z <$ 0.001 时其参数间隔为0.0001,金属丰度较高时 $( 2 { \it \Delta } ) 0 . 0 0 1 { \it \Delta }$ 参数间隔设为0.001。星族群的年老星族年龄 $( t _ { 1 } )$ 在 $0 \textsuperscript { \sim } 1 5 \mathrm { G y r }$ 范围内,其间隔设为 $0 . 1 \mathrm { G y r }$ ;年轻星族年龄 $( t _ { 2 } )$ 从 $t _ { 1 }$ 递减到0Gyr，其间隔设为 $0 . 1 \mathrm { G y r }$ 。恒星速度弥散 $\sigma _ { \ast }$ 参数以步长为 $1 0 \mathrm { k m ~ s } ^ { - 1 }$ 从0到 $3 5 0 \mathrm { k m }$ $\mathrm { ~ s ~ } ^ { - 1 }$ 改变;尘埃消光 $( \tau _ { \lambda } )$ 取值是时间隔为0.01的0至0.5区间。因此，双星星族理论光谱库包含巨大参数空间，光谱拟合包含天然的海量计算，对此建立拟合模型如下。

记观察光谱为 $f _ { \mathrm { o b } \lambda }$ ，双星星族合成理论光谱为 $f _ { \mathrm { t h } \lambda }$ ，则光谱拟合契合度的可由

$$
\chi ^ { 2 } = \Sigma [ ( f _ { \mathrm { o b } \lambda } - f _ { \mathrm { t h } \lambda } ) ^ { 2 } \omega _ { \lambda } ] \# ( 3 ) 
$$

刻画。其中 $\omega _ { \lambda }$ 是波长 $\lambda$ 的权重参数。最佳拟合结果对应于 $\operatorname* { m i n } \left( \chi ^ { 2 } \right)$ 。在大多数情况下, $\omega _ { \lambda }$ 使用观测误差 $E _ { \mathrm { o } } ^ { 2 } \lambda$ 表示：

$$
\omega _ { \lambda } = 1 / E _ { \mathrm { o } \lambda } ^ { 2 } \# \left( 4 \right)
$$

$\omega _ { \lambda }$ 也可以根据特殊要求赋予某个阈值。星族光谱拟合的实质是在理论光谱库对应的参数空间进行搜索，找到与被拟合的观察光谱 $\chi ^ { 2 }$ 最小值所对应的理论光谱。当 $\chi ^ { 2 }$ 最小时,双星星族合成光谱拟合模型满足物理约束： $0 \langle \omega _ { i } \langle 1$ ，其本质是一个最优化问题，可形式化为：

$$
\left\{ \begin{array} { l l } { \operatorname* { m i n } } & { \chi ^ { 2 } } \\ { \mathrm { s . t . } } & { w _ { i } > 0 } \\ & { \sum w _ { i } = 1 } \end{array} \right.
$$

其中， (3)式为目标函数。

# 2.2双星星族光谱拟合算法

遗传算法[1（GA，Genetic Algorithm）是模拟自然界生物遗传进化行为，提出选择、交叉和变异算子，通过对求解问题空间的多点并行迭代搜索能快速有效的收敛至全局最优解的一类仿生启发式算法。遗传算法是一种基于种群的搜索算法，其个体代表了可能解的一个样本。随着搜索的迭代进行，个体通过分享和交换他们之间的信息来产生更好的后代。传统的遗传算法（CGA，Conventional Genetic Algorithm）包含选择、交叉和突变等至关重要的操作。他们可以选择获胜的个体，维持种群的多样性，并在种群内的个体之间交换信息。

然而，传统改进策略遗传算法在局部搜索能力上表现较差，且对初值非常敏感。对GA算法运行机制分析后，受粒子群算法惯性自适应的启发，同时为克服该不足，本文在传统遗传算法改进策略的基础上设计了一种自适应遗传算法（SGA，Self-adaptive GeneticAlgorithm），来求解双星星族光谱拟合问题。传统遗传算法（CGA）采用固定交叉概率（PC,Probabilityof Cross）和固定突变概率（PM，Probabilityof Mutation）。这使得算法按照既定的规则进行，从而导致遗传变异不够灵活。基于特定的进化遗传使得算法的性能如收敛速度和全局优化能力对进化参数的选择很敏感。如果个体的适应度值大于总体的平均适应度值，则分配的交叉概率和变异概率应该较小。此外，对适应度值越大的个体，表示该个体越接近目标解，因此，应赋予其较小的交叉和变异概率，以保护其信息不被遗传给下一代。与之相反，对适应值较小的个体则应伺机引入扰动因子增强其变异能力，个体应被赋予较大的交叉和突变概率，以增加其变异概率。于是，适应度值越小的个体变异的机会越大。为了减少进化参数选择的依赖性，提高算法的收敛速度和全局优化能力，SGA改进如下：

1) 自适应PC更新：

$$
\left\{ \begin{array} { l l } { p _ { \mathrm { c } } = \bigg \{ C _ { 2 } \Big ( 1 - \frac { \left( 1 - \gamma _ { \mathrm { C A } } \right) ^ { w } \left( f _ { c } - f _ { \mathrm { o v s } } \right) } { f _ { \mathrm { m a x } } - f _ { \mathrm { a v s } } } \Big ) ; } & { f _ { \mathrm { c } } > f _ { \mathrm { a v g } } } \\ { C _ { 2 } ; } & { f _ { \mathrm { c } } \leqslant f _ { \mathrm { a v g } } } \\ { w = \big ( \frac { 2 } { \mathrm { i t e r a t i o n } } \big ) ^ { 0 . 3 } } \end{array} \right.
$$

2) 自适应PM更新：

$$
p _ { \mathrm { m } } = \left\{ { \begin{array} { l } { M _ { \mathrm { 2 } } \left( 1 - { \frac { \left( 1 - \gamma _ { \mathrm { G A } } \right) ^ { n } \left( f _ { \mathrm { m a x } } - f _ { \mathrm { m } } \right) } { f _ { \mathrm { m a x } } - f _ { \mathrm { a v g } } } } \right) ; \quad f _ { \mathrm { m } } > f _ { \mathrm { a v g } } } \\ { M _ { \mathrm { 2 } } ; \quad f _ { \mathrm { m } } \leqslant f _ { \mathrm { a v g } } } \end{array} } \right.
$$

其中，iteration为当前迭代次数， $f _ { \mathrm { a v g } }$ 为种群的平均适应值， $f _ { c }$ 为选择交叉操作的个体适应值， $f _ { \mathrm { m } }$ 为选择变异操作的个体适应值，fmax为最大适应值， $\gamma _ { \mathrm { G A } }$ 为随机参数，据经验取$\gamma _ { \mathrm { G A } } = 0 . 5$ 。

3）干扰因子主要目的是增强算法对搜索空间的探索能力。为此，引入了如下扰动因子（DO，Disruption Operator）:

$$
D _ { o p } = \left\{ \begin{array} { c c } { { D i s _ { i , j } \times \delta ( - 2 , 2 ) } } & { { \mathrm { ~ i f ~ } \qquad \mathrm { D i s _ { ~ i , b e s t } \geq 1 ~ } } } \\ { { 1 + D i s _ { i , \mathrm { b e s t } } \times \delta \biggl ( \frac { - 1 0 ^ { - 4 } } { 2 } , \frac { 1 0 ^ { - 4 } } { 2 } \biggr ) } } & { { \mathrm { ~ o t h e r w i s e } } } \end{array} \right.
$$

其中：8是 $( - 2 , 2 )$ 之间的随机数，Dis $_ { i , j }$ 是第i个染色体和领域第j个染色体的汉明距离。 $D i s _ { i , \mathrm { b e s t } }$ 是当前最优染色体和第i个染色体的汉明距离。

![](images/32118a45a60b54f1d087b5e34c855aa075f1918ef95b341954fedb220659774c.jpg)  
图1SGA 流程图  
Fig.1 SGA flow chart

SGA算法具体流程如图1所示，主要包括以下步骤：

步骤一：光谱数据预处理,包括剔除发射线、归一化和红移处理;步骤二：问题编码与种群初始化;步骤三：按目标函数计算适应值并保留当前最优种群。决定种群的大小包括染色体长  
度和个数等，依策略初始化种群，设定进化终止条件；步骤四：判断是否达到收敛条件或停止条件，如果满足则输出搜索结果，否则进行迭  
代进化；步骤五：选择算子：根据适应度值随机选择一组较好的个体;步骤六：按（5）式更新交叉概率；步骤七：交叉算子：从集合中随机选择两染色体交换一个或多个位，根据交叉概率产生  
两个新的个体，按（7）式添加扰动；步骤八：按（6）式更新变异算子：从集合中随机选择一个染色体，并根据突变概率改  
变一个或多个位以产生一个新的染色体；步骤九：返回步骤四进行终止判断，循环以上步骤，直到终止条件。

# 3实验与分析

# 3.1改进策略的遗传算法实验

为了验证SGA在双星星族光谱拟合中的寻优效率，本文选取了CGA和文献[1]的BS2fit算法作为对比。实验代码采用Python3.6开发，操作系统为ubuntu18.0464bit，内存容量为8GB，CPU型号为i7-4790,主频 $3 . 6 0 \mathrm { G H z }$ 。实验的理论光谱数据使用基于Chapbrier初始函数的双星星族理论光谱库进行拟合'。观测光谱数据选自99个本地星系的紫外-可见波段的光谱数据，可以在互联网上下载。

这些数据的特点是覆盖从紫外到可见光波段的波长，范围很广。此外，由于双星对紫外光谱有明显的影响，这些数据也是探索双星演化对光谱拟合影响的理想数据。每条观察光谱采样点数是 $N _ { \lambda } { = } 3 8 7 1$ ，以5500A为归一化因子，对光谱进行预处理。SGA算法参数设置为：交叉概率上限 $C 2 { = } 1$ ，变异概率上限 $\mathrm { M } 2 { = } 1$ ，随机参数 $\gamma _ { \mathrm { G A } } = 0 . 5$ ，个体编码长度 $\mathrm { n { = } 2 0 }$ ，种群规模$\mathrm { P o p { = } 1 0 0 }$ 。耗时指标取每个算法重复20次的平均值。

实验首先从观测光谱数据中随机选取一条（NGC1399星系)作为实验数据参考文献[12]进行数据预处理；然后将观察光谱进行坏点、发射线、天光线等屏蔽得到编号为spec-0266-51630-0010的光谱数据；接着，借鉴相关研究[13]，采用 $\chi ^ { 2 } / \mathrm { N } _ { \lambda }$ 作为评价标准，当$\chi ^ { 2 } / \mathrm { N } _ { \lambda } \ < 1$ 时，认为理论光谱与观测光谱拟合良好，星族合成参数估计准确，拟合结果可以接受。拟合迭代过程如图2左所示。算法在种群迭代20次后收敛，对应的适应值 $\chi ^ { 2 } = 1 3 0 8$ ，拟合精确度为 $\chi ^ { 2 } / \Nu _ { \lambda } { = } 0 . 3 4 3 3$ ，理论光谱与观测光谱拟合良好，如图2右所示。其中灰色曲线代表实际观察的光谱，红色曲线代表所拟合得的最优理论光谱。

![](images/66a29810da02233949b1819639fddb0ef143ef7d93578222f9d9ab552a4fa618.jpg)  
图2SGA拟合迭代过程

Fig.2 SGA fit

# 3.2与传统遗传算法（CGA）的比较

![](images/dcb00bdab44b547adb6998d51692c46497d9070a123417d57316b403410d22d3.jpg)  
图3CGA拟合迭代过程

![](images/e67f4660f1ec757c0047d571af65e889a60b808f349ca17b6c9a29854c5e6b18.jpg)  
图4BS2fit拟合遍历过程

Fig.3 CGA fit

Fig.4 BS2fit fit

CGA算法参数：交叉概率 $\mathrm { P C } { = } 0 . 8 ;$ 变异概率 $\mathrm { P M } { = } 0 . 1$ ，染色体长度为20， $\mathrm { P o p { = } 1 0 0 }$ 。对测试光谱用CGA算法在双星星族理论光谱库上进行拟合结果如图3所示。CGA算法中，种群迭代16次后陷入局部最优，迭代(iteration)15次后开始收敛，寻到拟合度最优的理论光谱。实验迭代20次平均耗时3201.3s 比BS2fit 算法略为占优，速度提高了 $1 9 . 2 \%$ 。与CGA算法相比，SGA在迭代20次后收敛，能有效跳出局部最优陷阱，收敛速度显著改善，实验 20 次平均耗时为1304.4s，速度提高了 $1 9 . 1 \%$ 。

# 3.3与BS2fit算法的比较

BS2fit算法采用文献[1]所述的BS2fit算法python实现，拟合遍历过程如图4所示，横轴表示遍历计算的次数，纵轴表示每次计算得到的卡方统计量的数值。由于是全网格搜索，双星星族模型的理论库覆盖波段长、演化参数网格稠密（模型光谱库覆盖金属丰度Z从0.0003到0.03,精度为0.0001;t1、t2范围从0到15Gyr，精度为 $0 . 1 \mathrm { G y r } )$ 等导致样本参数空间巨大。虽然我们将模型参数做了简化处理，但是要完成一条观测光谱的拟合也需要逐一进行海量对比，能寻到拟合度最优的理论光谱。实验20次平均耗时为3954.2s。与BS2fit算法相比，SGA算法具有更强的全局搜索能力，对理论光谱搜索效率更高，收敛速度显著改善，20次平均耗时减少了 $6 7 . 2 \%$ 。

如上，三种算法均能找到最小 $\cdot \chi ^ { 2 }$ 对应的理论光谱，按照理论光谱的参数网格设置，反演得到表1中给出的拟合参数。

表1：NGC1399星系bsSP-fitted拟合参数  
Tab.1 bsSP-fitted Parameters of NGC1399 Galaxies   

<html><body><table><tr><td>星系参数</td><td>Z(金属丰度)</td><td>t1年老星族年龄</td><td>t2年轻星族年龄</td></tr><tr><td>本文拟合值</td><td>0.0250</td><td>6.30</td><td>6.30</td></tr><tr><td>文献[4] bsSP-fitted 拟合值</td><td>0.030± 0.00</td><td>13.50 ± 0.00</td><td>12.27 ± 0.81</td></tr></table></body></html>

分析产生误差的原因是我们对实验模型进行了简化，一是理论光谱库只考虑（Z, $\mathbf { \Psi } _ { t _ { 1 } , \ t _ { 2 } } )$ 而没有考虑 $v _ { * } , \sigma _ { * }$ ， $\tau _ { \lambda } , A _ { \lambda }$ 等参数的影响；二是没有考虑观测光谱的误差，没有对观测光谱的不确定性进行处理，即是信噪比（S/N）取值很大的理想情况。文中得到的金属丰度比文献[4]的拟合值小0.005。这也符合我们的预期，原因是模型输入的不确定性通常会导致金属丰度估计值偏低[4]。星族年龄 $( t _ { 1 } , \ t _ { 2 } )$ 的拟合值比文献[4]的值低 $5 0 \%$ 的主要原因是简化的模型没有考虑速度弥散从而导致星族年龄被低估。该拟合结果也体现了“年龄-金属丰度简并效应”。

综上，增加自适应策略的改进遗传算法在拟合速度上较传统遗传算法和BS2fit算法平均提高了 $4 3 . 5 \%$ ，拟合结果符合预期。

# 4总结与讨论

采用自适应策略改进的遗传算法对双星星族光谱拟合，结果表明：（1）采用群智能算法（SIA）解决双星光谱拟合问题是可行的。（2）改进策略遗传算法和传统遗传算法、BS2fit算法相比在双星星族光谱拟合中能将计算速度分别提升 $1 9 . 1 \%$ 和 $6 7 . 2 \%$ ，对双星星族光谱拟合速度平均可提高 $4 3 . 5 \%$ ，提升效果明显。改进策略的遗传算法在传统遗传算法的基础上,发挥遗传算法全局搜索能力强、相较于传统遗传算法收敛速度快。此外,改进策略的遗传算法在搜索时更智能，能有效跳出局部最优陷阱，提高遗传算法全局搜索能力，避免算法早熟，相对于BS2fit算法的全网格搜索 SGA算法对搜索空间做了取舍所以效率更高。虽然改进策略遗传算法在双星星族拟合上提升了速度，但是还有很大提升空间。一方面，编码方式对算法探索能力和收敛性也有影响，改进算法编码如利用量子编码等也值得探索，另一方面，群智能算法发展日新月异，探索更有效的搜索策略，如探索和强化学习Q-learning 等融合也很有必要。考虑到遗传算法易于并行实现，下一步可探索并行策略下的改进策略遗传算法对光谱拟合速度的改善。

# 参考文献：

[1]Li Z,Zhang L,Liu J，et al.Integrated spectral energy distributions of binary star composite stellar populations[J]．Monthly Notices of the Royal Astronomical Society，2012，424(2):874-883. [2]HanY，Han Z.BayeSED:AGENERAL APPROACHTOFITTING THE SPECTRALENERGY DISTRIBUTIONOFGALAXIES[J]．Astrophysical Journal Supplement Series，2014，215(1). [3] HanY，Han Z．A Comprehensive Bayesian Discriminationof the Simple Stellar Population Model，Star Formation History，and Dust Atenuation Law in the Spectral Energy Distribution Modelingof Galaxies[J].The Astrophysical

Journal Supplement Series，2018,240(1).   
[4] Li,Zhongmu，et al.Potential Importance of Binary Evolution in UV-Optical Spectral Fiting of Early-Type Galaxies." Astrophysical Journal 776.1(2013):37.   
[5] ZhangF，LiL，Han Z，etal.Yunnan-IImodels for Evolutionary population synthesis[J]．Monthly Notices of the Royal Astronomical Society(4):3390-3408.   
[6] Han Z,PodsiadlowskiP,LynasgrayAE,etal.Abinary model fortheUV-upturnof elliptical galaxies[J].Monthly Notices of the Royal Astronomical Society，2007，380(3):1098-1118.   
[7] HurleyJR,Tout CA,Pols OR,etal.Evolutionof binary stars and the effectof tides onbinary populations[J]. Monthly Notices of the Royal Astronomical Society，2002，329(4):897-928.   
[8] Calzetti D，Armus L，Bohlin RC，etal.The Dust Content and Opacityof Actively Star-Forming Galaxies[J]. Astrophysical Journal，1999,533(2) :682.   
[9] Chabrier G.The Galactic Disk Mass Function:Reconciliation of the Hubble Space Telescope and Nearby Determinations[J]．The Astrophysical Journal，2003，586(2).   
[10]Thomas D,MarastonC,BenderR,etal.The EpochsofEarly-TypeGalaxyFormationasaFunctionof Environent[J]. The Astrophysical Journal，2005，621(2):673-694.   
[11] David E.Goldberg.Genetic Algorithm in Search,Optimization and Machine Learning[J].addison wesley，1989, xiii(7):2104-2116.   
[12]张茜，张健楠，赵永恒．基于聚类的星系光谱分析．天文研究与技术，2020，17(2)：233-243. Zhang Xi，Zhang Jiannan,Zhao Yongheng.Spectral Classification of Galaxies Based on Clustering Analysis.   
Astronomical Research and Technology，2020，17(2)：233-243.   
[13]韩金姝.基于遗传算法的星族合成参数估计[J].天文学报,2015,56(02)：93-101. Han Jinshu.Parameter Estimationof StellarPopulation Synthesis Using Genetic Algorithm[J].Astronomy Letters, 2015,56(02) :93-101.

# Binary-Star Spectral Fitting Based on Strategy Improved Genetic Algorithm

Chi Huanbin1, Li Zhongmu²，Wang Feng1,3,

(1. School of Management and Economics，Kunming University of Science and Technology，Kunming 650500 ，China;2 .Dali University, Institute of Astronomy, Dali 671000, Yunnan ;3 .Center for Astrophysics ,Guangzhou University ,Guangzhou 510006, China)

Abstract: The essence of the binary-star spectral fiting is to search the parameter space corresponding to the comparison of observed and theoretical spectra, via techniques such as least square. Rapid and accurate fiting of spectra is very important for studying a huge number of galaxies.Because it is not easy to deal with such problems as spectral fiting contains huge amounts of calculation and the eficiency of fitting is not high. The strategic improved genetic algorithm is used for binary-star spectral fiting by this paper,and the comparison to BS2fit algorithm and traditional genetic algorithm is also shown.The experimental results show that the improved genetic algorithm can increase the spectral fiting speed by $4 3 . 5 \%$ on average, which can possibly promote the application of stellar population synthesis method in astronomical researches obviously.

Keywords: Spectral fitting; Galaxies; Improved Genetic Algorithm