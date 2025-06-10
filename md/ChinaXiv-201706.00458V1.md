# DOI:10.5846/stxb201604130679

刘华，金鑫，石磊，蒋芮，魏玉梅.基于种间竞争模型的毒杂草入侵空间分布模拟研究.生态学报,2017,37(11);3765-3775.LiuH,JinXec2017,37(11) ：3765-3775.

# 基于种间竞争模型的毒杂草入侵空间分布模拟研究

刘华1\*，金鑫，石 磊，蒋 芮¹，魏玉梅²

1西北民族大学数学与计算机科学学院，兰州730030  
2西北民族大学实验中心，兰州730030

摘要;以天然草场中毒杂草与可食牧草为研究对象,在种间竞争的生态数学模型的基础上引人入侵扩散因素建立毒杂草入侵扩散模型。采用元胞自动机理论将竞争模型扩展到空间网络进行模拟研究,分析毒杂草属的空间分布类型,为毒杂草的控制提供数据支持。研究表明：(1)在入侵扩散作用下,毒杂草与可食牧草的共存平衡点由一个增加为两个,增加了共存的可能性；(2)入侵扩散作用影响了毒杂草种群的空间分布特征,减少了种群空间分布的聚集程度。

关键词：元胞自动机；空间分布；计算机模拟

# Spatial distribution of poisonous weed invasion based on inter-species competition models

LIU Hual\*， JIN Xin’，SHI Lei’， JIANG Rui'，WEI Yumei² 1SchoolofMathematicsand Computer science，Northwest UniversityforNationalities,Lanzhou73oo3o,China 2Experimental Center，Northwest University for Nationalities，Lanzhou 73oo3o,China

Abstract:In thepresent study，a spatial difsion model of poisonous weed invasion byusing inter-species competition model wasdeveloped based on poisonous weeds andedible forage in native pastures.Using thecelular automata theory,the competition model wasextended tothespatial network to simulateand studythe spatial distributionpaternsof poisonous weeds，which will provide data supportingtheir control.Theresults showed that（1）underthe influenceof invasion and diffusion，thecoexistence equilibrium point of the poisonous weedsand theedible grasscould be increased byan increaseof two，which increasedtheposibilityofcoexistence；and（2）the spatial distributionof the weed population was affcted by invasion and diffusion，and the aggregation of the spatial distribution of the population was reduced.

Key Words:cellular automata； space distribution； computer simulation生物入侵是指生物由原分布区域经由自然的或人为的途径扩展到一个新的区域,繁殖并维持下去[1]。近年来，随着全球经济一体化、国内外贸易的迅速发展，世界各地生物入侵现象愈加严重[2]。我国因外来物种人侵造成的损失相当惊人,每年仅几种外来物种造成的经济损失就达到574 亿元人民币[3]。据世界自然保护联盟报道,全球范围内入侵物种对生物多样性的威胁高居前5位，外来生物入侵是导致原生物种衰竭、生物多样性减少的重要原因之一[4]。如今，生物人侵对我国生物多样性的影响越来越突出，在一定程度上威

胁我国生物多样性和生态系统稳定性[4] Q

我国西北地区因其独特的地形条件和地理位置,加之资源过度开发和不合理利用,导致长期以来生物灾害严重、生态环境脆弱,而外来物种入侵加剧了这一矛盾。外来人侵植物可降低土壤的营养水平，这主要是由于竞争、落叶的营养贫乏或难分解，积累盐分改变土壤pH值等造成的[2]。在天然草场中,人侵的毒杂草不仅与可食牧草争夺水、肥料、光照等资源抑制可食牧草的生长、降低可食牧草的产量，而且影响可食牧草的品质,更有甚者,有的杂草本身就是毒草,家畜误食,造成中毒、死亡。原产于中美洲的紫茎泽兰(Eupatoriumodoratum）,约在20世纪50 年代初从中缅、中越边境传入云南南部,至今已占据了四川凉山州1/5 的草场,正以每年约 $3 0 ~ \mathrm { k m }$ 的速度向北、向东扩散蔓延,当地畜牧业遭受了空前打击,每年经济损失达数千万元[3]。因此,牧民都希望草场中的毒杂草越少越好,可食牧草越多越好,而要想控制草场中毒杂草的数量,就首先需要了解毒杂草与可食牧草在草场中的空间分布情况。

本文假设毒杂草与可食牧草存在对环境资源的竞争关系,采用元胞自动机理论对种间竞争模型进行空间模拟。元胞自动机的基本思想就是将系统分解为多个元胞,每个元胞看成一个单元,系统中各个相邻单元之间存在一定的交互相互关系,而每个单元的状态都是整个系统在一些简单的规则作用下不断进化的结果[5-7]

在对种间竞争模型进行模拟的时候,本文引入了空间扩散因素,从而得到了毒杂草入侵的空间分布情况。

# 1毒杂草与可食牧草的种间竞争模型

假设毒杂草与可食牧草种间存在相互作用,同时假设单一物种独自在同一个草场中生存时,数量的演变均遵从 Logistic 规律。于是得到毒杂草与可食牧草的种间竞争模型为[8-10]：

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { \mathrm { d } x } { \mathrm { d } t } = r _ { 1 } x \big ( 1 - \frac { \bigtriangledown x } { N _ { 1 } } - a _ { 1 } \frac { y } { N _ { 2 } } \big ) } \\ { \displaystyle \frac { \mathrm { d } y } { \mathrm { d } t } = r _ { 2 } y \big ( 1 - a _ { 2 } \frac { x } { N _ { 1 } } - \frac { y } { N _ { 2 } } \big ) } \end{array} \right.
$$

式中， $r _ { 1 } > 0 , r _ { 2 } > 0 , a _ { 1 } > 0 , a _ { 2 } > 0$ ，记x，y分别是可食牧草和毒杂草的数量, $r _ { 1 } , r _ { 2 }$ 分别是它们的固有增长率， $N _ { 1 }$ ， $N _ { 2 }$ 分别是它们的在理想条件下的最大容量。因子 $( 1 - \frac { x } { N _ { 1 } } - a _ { 1 } \frac { y } { N _ { 2 } } )$ ）反映由于可食牧草对环境资源的消耗导致的对它本身增长的阻滞作用和毒杂草对环境资源的消耗对可食牧草产生的影响。这里 $\mathbf { \alpha } _ { a _ { 1 } }$ 的意义是：单位数量的毒杂草（相对 $N _ { 2 }$ 而言)消耗的供养可食牧草的环境资源量为单位数量的可食牧草（相对 $N _ { 1 }$ )消耗的供养自身的环境资源量的 $\boldsymbol { a } _ { 1 }$ 倍。 $a _ { 2 }$ 的意义是：单位数量的可食牧草（相对 $N _ { \scriptscriptstyle 1 }$ 而言)消耗的供养毒杂草的环境资源量为单位数量的毒杂草（相对 $N _ { _ 2 }$ )消耗的供养自身的环境资源量的 $\left| a _ { 2 } \right.$ 倍。模型(1)的4个平衡点为： $\gamma _ { 1 } ( N _ { 1 } , 0 ) \bigotimes _ { \ , p _ { 2 } ( 0 , N _ { 2 } ) } ^ { \ }$ ， $P _ { 3 } \bigg ( \frac { N _ { 1 } ( 1 - a _ { 1 } ) } { 1 - a _ { 1 } a _ { 2 } } , \frac { N _ { 2 } ( 1 - a _ { 2 } ) } { 1 - a _ { 1 } a _ { 2 } } \bigg )$ ， $_ { p _ { 4 } ( 0 , 0 ) }$ ;这4个平衡点的稳定性分析结果见表1[4]（证明过程见附录1）。

表1种群竞争模型的平衡点及稳定性  
Table 1 Equilibrium point and stability of population competition model   

<html><body><table><tr><td colspan="2">平衡点</td><td>稳定条件 Stability condition</td><td>平衡点 Equilibrium point</td><td>稳定条件 Stability condition</td></tr><tr><td colspan="2">Equilibrium point Pi(N,0)</td><td>a<1,a>1</td><td>P(0,N2)</td><td>a>1,a<1</td></tr><tr><td colspan="2">(N(1-a1) N(1-a2)</td><td></td><td></td><td></td></tr></table></body></html>

# 2毒杂草入侵空间扩散模型

毒杂草和可食牧草作为两个物种在单个斑块中将产生竞争,而且毒杂草是外来物种,在生长过程中会从密度高的斑块向密度低的斑块发生迁移,考虑到以上因素建立单个斑块毒杂草入侵空间扩散模型

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { \mathrm { d } \boldsymbol { x } _ { i , j } } { \mathrm { d } t } = r _ { 1 } \boldsymbol { x } _ { i , j } ( 1 - \frac { \boldsymbol { x } _ { i , j } } { N _ { x } } - a _ { 1 } \frac { \boldsymbol { y } _ { i , j } } { N _ { y } } ) } \\ { \displaystyle \frac { \mathrm { d } \boldsymbol { y } _ { i , j } } { \mathrm { d } t } = r _ { 2 } \boldsymbol { y } _ { i , j } ( 1 - a _ { 2 } \frac { \boldsymbol { x } _ { i , j } } { N _ { x } } - \frac { \boldsymbol { y } _ { i , j } } { N _ { y } } ) \ + \mu \big ( \sum \boldsymbol { y } _ { i \pm 1 , j \pm 1 } - \boldsymbol { 4 } \boldsymbol { y } _ { i , j } \big ) } \end{array} \right.
$$

模型(2)中下标 $\ddot { y }$ 表示二维平面上的网格中的第 $i$ 行第 $j$ 列的斑块， $\big ( \sum y _ { i \pm 1 , j \pm 1 } - 4 y _ { i , j } \big )$ 为第 $i j$ 个斑块中毒杂草的邻体对第 $i j$ 个斑块的入侵扩散作用,本模型中元胞自动机设计采用冯诺依曼型,每个元胞的邻体只含上下左右4个邻体,分别为： $N _ { i , j - 1 }$ (左邻体）， $N _ { i , j + 1 }$ （右邻体）， $N _ { i - 1 , j }$ （上邻体）， $N _ { i + 1 , j }$ （下邻体）， $\mu$ 为扩散系数[12]。

2.1具有空间扩散的毒杂草入侵空间扩散模型的稳定性分析讨论模型(2)的稳定性，首先要计算平衡点，令：

$$
\left\{ \begin{array} { l l } { \displaystyle f ( x _ { i , j } , y _ { i , j } ) = r _ { 1 } x _ { i , j } ( 1 - \frac { x _ { i , j } } { N _ { x } } - a _ { 1 } \frac { y _ { i , j } } { N _ { y } } ) = 0 } \\ { \displaystyle g ( x _ { i , j } , y _ { i , j } ) = r _ { 2 } y _ { i , j } ( 1 - a _ { 2 } \frac { x _ { i , j } } { N _ { x } } - \frac { y _ { i , j } } { N _ { y } } ) + \mu \big ( \sum y _ { i \pm 1 , j \pm 1 } - 4 y _ { i , j } \big ) = 0 } \end{array} \right.
$$

则平衡点为：

$$
p _ { 1 } \bigg ( 0 , \frac { \theta _ { 1 } } { 2 } N _ { y } \bigg ) \ ; \ p _ { 2 } \bigg ( 0 , \frac { \theta _ { 2 } } { 2 } N _ { y } \bigg ) \ ; \ P _ { 3 } \bigg ( N _ { x } - \frac { a _ { 1 } N _ { x } } { N _ { y } } \theta _ { 3 } , \theta _ { 3 } \bigg ) \ ; p _ { 4 } \bigg ( N _ { x } - \frac { a _ { 1 } N _ { x } } { N _ { y } } \theta _ { 4 } , \theta _ { 4 } \bigg ) \ \circ
$$

定理：(证明过程见附录2)模型(2)的平衡点 $p _ { 1 } \bigg ( 0 , \frac { \theta _ { 1 } } { 2 } N _ { y } \bigg )$ 稳定的条件为：

$$
\theta _ { 1 } > 1 , a _ { 1 } > \frac { 2 } { \theta _ { 1 } } , a _ { 2 } < 1 ;
$$

平衡点 $p _ { 2 } \bigg ( 0 , \frac { \theta _ { 2 } } { 2 } N _ { y } \bigg )$ 稳定的条件为：

$$
\theta _ { 1 } > 1 , a _ { 1 } > \frac { 2 } { \theta _ { 2 } } , a _ { 2 } < 1 ;
$$

平衡点 $P _ { 3 } \bigg ( N _ { x } - \frac { a _ { 1 } N _ { x } } { N _ { y } } \theta _ { 3 } , \theta _ { 3 } \bigg )$ 稳定的条件为：

$$
a _ { 2 } > 1 , \frac { a _ { 1 } \theta _ { 3 } } { N _ { y } } < 1 , a _ { 1 } a _ { 2 } < \mathrm { m i n } \{ 2 , \frac { N _ { y } ( a _ { 2 } - 1 ) } { 2 \theta _ { 3 } } + 1 \} ;
$$

平衡点 $p _ { 4 } \bigg ( N _ { _ x } - \frac { a _ { 1 } N _ { _ x } } { N _ { _ y } } \theta _ { 4 } , \theta _ { 4 } \bigg )$ 稳定的条件为：

$$
a _ { 2 } \ > \ 1 \ , \frac { a _ { 1 } \theta _ { 4 } } { N _ { y } } \ < \ 1 \ , \ a _ { 1 } a _ { 2 } \ < \ \operatorname * { m i n } \{ 2 , \frac { N _ { y } ( a _ { 2 } \ - \ 1 ) } { 2 \theta _ { 4 } } \ + \ 1 \}
$$

其中：

$$
\theta _ { 1 } = 1 + \sqrt { 1 + \frac { 4 M } { r _ { 2 } N _ { y } } } , \theta _ { 2 } = 1 - \sqrt { 1 + \frac { 4 M } { r _ { 2 } N _ { y } } } ,
$$

$$
\theta _ { 3 } = \frac { \displaystyle ( a _ { 2 } - 1 ) + \sqrt { ( 1 - a _ { 2 } ) ^ { 2 } - \frac { 4 } { r _ { 2 } N _ { y } } ( a _ { 1 } a _ { 2 } - 1 ) M } } { \displaystyle \frac { 2 } { N _ { y } } ( a _ { 1 } a _ { 2 } - 1 ) } ,
$$

$$
\theta _ { 4 } = \frac { \left( a _ { 2 } - 1 \right) - \sqrt { \left( 1 - a _ { 2 } \right) ^ { 2 } - \displaystyle \frac { 4 } { r _ { 2 } N _ { y } } ( a _ { 1 } a _ { 2 } - 1 ) { \cal M } } } { \displaystyle \frac { 2 } { N _ { y } } ( a _ { 1 } a _ { 2 } - 1 ) } ,
$$

扩散项 $\mu \big ( \sum { y _ { i \pm 1 , j \pm 1 } } - 4 y _ { i , j } \big )$ 记为参数 $M$ 。

在以上两个模型中,模型(1)是毒杂草与可食牧草的种间竞争模型,该模型只考虑了当两个种群在同一个自然环境中生存时它们的相互竞争关系。而模型(2)是毒杂草入侵的空间扩散模型,该模型考虑到了毒杂草和可食牧草作为两个物种在单个斑块中将产生竞争,而且毒杂草是外来物种，在生长过程中会从密度高的斑块向密度低的斑块发生迁移这一重要因素。可以说模型(2)是模型(1)的改进。所得到的结果中：没有加入扩散项时,模型(1)的四个平衡点包括零平衡点和毒杂草灭绝的平衡点以及一个共存的非零平衡点;加入扩散项之后,模型的零平衡点和毒杂草灭绝的平衡点消失,而且毒杂草与可食牧草的共存的非零平衡点由一个变为两个。说明在扩散作用下,两种群的可能出现两种稳定情况,而且毒杂草续存的可能性增加。

# 3毒杂草入侵的空间分布模拟

将单一斑块中的毒杂草与可食牧草的相互竞争扩展到空间上，在 $1 0 0 \times 1 0 0$ 的二维网格平面模拟两物种(毒杂草与可食牧草)的种群动态,时间标度 $\mathbf { \chi } _ { t }$ 为单位时间步长。初始时刻可食牧草与毒杂草的数量都是随机的。在二维网格中,网格之间的物种会发生迁移,假定物种在冯诺依曼邻体（即只考虑相邻的每个斑块边的4个斑块)由高密度向低密度发生迁移(也可推广为摩尔邻体即与斑块边和顶点相邻的八个斑块发生迁移)。迁移率为0.25倍的密度差，即 $\mu = 0 . 2 5$ 。

现假定 $r _ { 1 } = 0 . 4 5 , r _ { 2 } = 0 . 4 5 , a _ { 1 } = 0 . 5 , a _ { 2 } = 0 . 7$ ,最大容量 $N _ { \scriptscriptstyle 1 }$ 为40, $N _ { 2 }$ 为60,考虑到毒杂草为外来物种,因此认为该物种在入侵过程中具有扩散过程,而作为本地物种的可食牧草在空间上是没有扩散作用的,通过Matlab 进行编程模拟。图1、图2及图3分别以第40,60,80代可食牧草与毒杂草空间分布情况为例给出空间

![](images/e9a3f9a768654d0085ce392be834dfe33efa07c71823323961dff249cbe92bb6.jpg)  
图1第40代可食牧草与毒杂草空间分布  
Fig.1Spatial distribution of fortieth generations of edible grass and poisonous weeds

![](images/4c970c3ee35b85d44ae7880c61a4c6b5df7a29d928df69162f2f4b824ce20c3a.jpg)  
第60代毒杂草空间分布

![](images/6fa3f7a451b201782c82c6d38876cf13353195ab54779d7990a4b1f111fb1b8b.jpg)  
第60代可食牧草空间分布

Fig.2Spatial distribution of sixtieth generations of edible grass and poisonous weeds分布的模拟结果,其中白色代表生存,黑色代表已灭绝。图4和图5显示：可食牧草生物量大概在18代之后趋于不变,而毒杂草的生物量大概在18代之后在小范围内波动。

![](images/79530eb3834ae19ac3322a626f0dfe0683a992eb740539398490f61c094bb564.jpg)  
图2第60代可食牧草与毒杂草空间分布  
图3第80代可食牧草与毒杂草空间分布  
Fig.3 Spatial distribution of eightieth generations of edible grass and poisonous weeds

# 4毒杂草入侵的空间分布假设检验

David & Moore（1954)法、Iwao(1968,1972） $\stackrel { * } { m } - m$ 回归法、平均拥挤度指标Lloyd，M.（1967)等方法[13-14]是常见的种群的检验空间分布状况的方法,根据上述模拟的数据,利用 Matlab 编写程序,判断在加入扩散项前后毒杂草的空间分布结构。下面以加入扩散项后的第80代种群分布数据为例进行的假设检验。

(1)利用分散指标C对数据进行检验

根据数据计算得：

$$
\bar { x } = \frac { \sum f \times x } { \sum f } = \frac { 2 0 4 5 1 8 . 3 4 } { 1 0 0 0 0 } = 2 0 . 4 5 1 8 3 4
$$

![](images/07e56f5a5d4cd3b7f4dcd1da4f2293aaaa5c4632388b53e7323bcfa1ea537499.jpg)  
图4可食牧草总生物量随时间变化

![](images/2662095e05812b9e8ee11e24f6d5b2752978178a38a50e3346b51b22abeb0c3d.jpg)  
Fig.4The total biomass of edible grass changed with time   
图5毒杂草总生物量随时间变化  
Fig.5The total biomass of poisonous weeds changed with time

$$
S ^ { 2 } = \frac { ~ \displaystyle \sum ~ \left( x _ { i } ~ - ~ \bar { x } \right) ~ ^ { 2 } } { n ~ - ~ 1 } = 1 4 8 . 0 5
$$

又因为

$$
C = { \frac { S ^ { 2 } } { \bar { x } } } = { \frac { \sum { \ ( x _ { i } - \bar { x } ) } ^ { 2 } } { \bar { x } . \left( n - 1 \right) } }
$$

所以

$$
C = { \frac { S ^ { 2 } } { \bar { x } } } = 7 . 2 3 8 9 0 0 8 4
$$

$C$ 的概率为 $9 5 \%$ 的置信区间为

$$
1 \ \pm 2 { \sqrt { \cfrac { 2 n } { \left( n \ - \ 1 \right) ^ { 2 } } } } = 1 \ \pm 2 { \sqrt { \cfrac { 2 0 0 0 } { 9 9 9 8 0 0 0 1 } } } = 1 \ \pm 0 . 0 2 8 2 8 7
$$

$$
7 . 2 3 8 9 0 0 8 4 \ > \ 1 . 0 2 8 2 8 7 , 7 . 2 3 8 9 0 0 8 4 \ > \ 0 . 9 7 1 7 1 2 9
$$

显然 $C$ 落入区间外，故模拟数据属于聚集型分布。

(2)利用David&Moore(1954)方法对数据进行检验

首先假设模拟数据属于随机分布，则有

$$
\chi _ { _ { 0 . 9 7 5 } } ^ { 2 } < \chi ^ { 2 } < \chi _ { _ { 0 . 0 2 5 } } ^ { 2 }
$$

由上可知

$$
I = { \frac { S ^ { 2 } } { \bar { x } } } = C = 7 . 2 3 8 9 0 0 8 4
$$

求得

$$
\chi ^ { 2 } = I ( n - 1 ) = 7 . 2 3 8 9 0 0 8 4 \times 9 9 9 9 = 7 2 3 8 1 . 7 6 9 5
$$

取自由度

$$
i = 1 0 0 0 0 - 1 = 9 9 9 9
$$

经计算得：

$$
\begin{array} { c } { { \chi _ { _ { 0 . 9 7 5 } } ^ { 2 } = 9 7 2 3 . 7 3 2 2 3 7 } } \\ { { \chi _ { _ { 0 . 0 2 5 } } ^ { 2 } = 1 0 2 7 8 . 0 5 6 3 2 } } \end{array}
$$

所以

$$
\chi ^ { 2 } ~ > \chi _ { _ { 0 . 0 2 5 } } ^ { 2 } ~ , \chi ^ { 2 } ~ > \chi _ { _ { 0 . 9 7 5 } } ^ { 2 }
$$

显然不接受假设，所以模拟数据属于聚集型分布。

http://www.ecologica.cn

(3)利用平均拥挤度指标Lloyd，M.（1967)对数据进行检验

平均拥挤度指标参数m=j=1 $\ddot { \bar { m } } = \frac { \displaystyle \sum _ { j = 1 } ^ { n } x _ { j } ( x _ { j } - 1 ) } { \displaystyle \sum _ { j } ^ { n } x _ { j } }$ ,判断相应数据的邻居个数。根据模拟数据求得 $\stackrel { * } { m } = \frac { 5 4 5 8 5 9 . 4 9 } { 2 0 4 5 1 8 . 3 4 } =$

26.69，即平均每个元素有23.8569个邻居。因为 $m = \bar { x } = 2 0 . 4 5 2$ ,得 $\frac { \stackrel { * } { m } } { m } = 1 . 3 0 5 0 0 6 8 5 > 1$ ,所以模拟数据属于聚集型分布。

（4)利用Iwao（1968，1972） $\stackrel { * } { m } - m$ 回归法对数据进行检验

根据Iwao 的发现 $\stackrel { * } { m } = \alpha + \beta m$ ，因为研究的是个体分布,所以分布基本成分是单个个体,即 $\alpha = 0$ ，由前文可知 $\stackrel { * } { m } = 2 6 . 6 9$ ， $m = \bar { x } = 2 0 . 4 5 2$ ，,所以可得 $\beta \approx 1 . 3 0 5 0 0 6 8 5 \mathrm { ~ > ~ } 1$ ,很容易判断模拟数据属于聚集型分布。

(5)计算Morisita'sindex对数据进行检验

由公式 $I _ { d } = n \left[ \frac { \sum { x ^ { 2 } - \sum { x } } } { \left( \sum { x } \right) ^ { 2 } - \sum { x } } \right]$ ,求得 $I _ { d } = 1 . 3 0 5 0 0 6 8 5$ ,自由度 $n - 1 = 9 9 9 9$ ,由上可得：

计算临界点

Uniform index

Clumped index

所以

$$
I _ { d } \geqslant M _ { c } > 1
$$

计算 Standardized Morisita index

$$
I _ { \mathrm { P } } = 0 . 5 + 0 . 5 \biggl ( { \frac { I _ { d } - M _ { c } } { n - M _ { c } } } \biggr ) = 0 . 5 0 0 0 1 5 3 5
$$

因为 $I _ { \mathrm { P } } = 0 . 5 0 0 0 1 5 3 5$ ，得 $I _ { p } > 0$ ,所以模拟数据属于聚集分布型。

采取以上方法,通过计算机模拟数据并对所有80代数据进行检验,得到的结果如下所示,其中字母“U”代表均匀分布,字母"A”代表聚集分布。充分说明毒杂草入侵可食牧草时,以较强的竞争能力,空间分布型从开始的均匀分布逐渐演变成最终的聚集分布。

表2加入扩散项前毒杂草空间分布结构(1到80代均为A)  
Table 2The spatial distribution structure of the poisonous weeds without diffusion（1th to 8Oth generations are A   

<html><body><table><tr><td>代数Generations</td><td>1</td><td></td><td>20</td><td>…</td><td>30</td><td>…</td><td>40</td><td></td><td>50</td><td>60</td><td>…</td><td>70</td><td></td><td>80</td></tr><tr><td>平均拥挤度指数 Average congestion index</td><td>A</td><td>：</td><td>A</td><td>：</td><td>A</td><td>：</td><td></td><td>A</td><td>：</td><td>A</td><td>…</td><td>A</td><td></td><td>A</td></tr><tr><td>David& Moore方法David& Moore method</td><td>A</td><td>：</td><td>A</td><td>：</td><td>A</td><td></td><td>：</td><td>A</td><td>：</td><td>A</td><td></td><td>A</td><td></td><td>A</td></tr><tr><td>Morisita's指数法 Morisita's index</td><td>A</td><td>：</td><td>A</td><td>…</td><td>A</td><td></td><td>：</td><td>A</td><td>：</td><td>A</td><td>：</td><td>A</td><td></td><td>A</td></tr></table></body></html>

由表2可以看出,在加入扩散项之前,即扩散系数为0时,毒杂草在第1代到第80代一直为聚集分布。

由表3可以看出,在加入扩散项之后,且扩散系数取0.25时,毒杂草在第1代至第24代时为均匀分布，从第 25代以后开始变为聚集分布。

计算1至80代加入扩散项的植物入侵模型的空间分布相关参数,毒杂草从第1代开始到第24代为均匀分布,从第25代开始其空间分布已经由均匀分布向聚集分布发生转变,此后一直是聚集分布。综合两个表可以发现,外来植物物种的入侵及空间扩散可以影响植物物种的空间分布的格局,减少了种群空间分布的聚集程度。

表3加入扩散项后毒杂草空间分布结构(1到24代为U,25代以后为A)  
Table3TespatiadstrbtiostructureofteosoousdsithdiusiothtogeneatioseUfterethgeatioreA）  

<html><body><table><tr><td>代数Generations</td><td>1</td><td></td><td>10</td><td>：</td><td>20</td><td>21</td><td>22</td><td>23</td><td>24</td><td>25</td><td>26</td><td>27</td><td>28</td><td>…</td></tr><tr><td>平均拥挤度指数 Average congestion index</td><td>U</td><td>：</td><td>U</td><td>：</td><td>U</td><td>U</td><td>U</td><td>U</td><td>A</td><td>A</td><td>A</td><td>A</td><td>：</td><td>A</td></tr><tr><td>David&Moore方法David&Moore method</td><td>U</td><td>：</td><td>U</td><td>：</td><td>U</td><td>U</td><td>U</td><td>U</td><td>A</td><td>A</td><td>A</td><td>A</td><td>：</td><td>A</td></tr><tr><td>Morisita's指数法 Morisita's index</td><td>U</td><td>：</td><td>U</td><td>：</td><td>U</td><td>U</td><td>U</td><td>U</td><td>A</td><td>A</td><td>A</td><td>A</td><td></td><td>A</td></tr></table></body></html>

在通过 Matlab 进行编程模拟的过程中,我们观察到:当扩散系数、固有增长率、可食牧草与毒杂草的生存能力等因素变化时,毒杂草与可食牧草的空间分布发生显著的变化,同时,毒杂草与可食牧草的总数量随时间的变化也很明显。当取扩散系数为0, $r _ { 1 } = 0 . 4 5$ ， $r _ { 2 } = 0 . 4 5$ ， $\textstyle { a _ { 1 } = 0 . 5 }$ ， $a _ { 2 } = 0 . 7$ 时,由于没有受到扩散因素的影响,毒杂草从第1代开始到第80代都是聚集分布;当取扩散系数为0.1,其余参数不变时,由于受到扩散因素的影响,可食牧草与毒杂草的分布结构发生了变化,毒杂草在第1代至第14代时为均匀分布,从第15代以后变为聚集分布;当取扩散系数增加到0.2时,毒杂草从第一代至第80代全部为聚集分布;当再取扩散系数为0.25时,可食牧草在第1至24代为均匀分布,从第25代开始为聚集分布;而当取扩散系数继续增加到0.3时，由于扩散系数过大,且可食牧草与毒杂草竞争激烈,可食牧草在很短的时间内灭绝,而毒杂草在第1至9代为均匀分布,从第10代以后为聚集分布;当扩散系数达到0.4,由于扩散系数太大,可食牧草很快就灭绝了,而毒杂草在第1代时为均匀分布，从第2代开始便属于聚集分布。

从以上的模拟过程中我们观察到：当扩散系数从0逐渐增大至0.4的过程中,可食牧草的灭绝速度越来越快。同时,毒杂草在受到扩散因素影响的时候,其均匀分布保持的时间长度也有很大变化,当扩散因素从0增加到0.25时,毒杂草均匀分布保持的时间逐渐变长,而当扩散因素从0.25增加到0.4时,毒杂草均匀分布保持的时间逐渐变短。

# 5结果讨论

本文的模拟过程以及结果充分表明,在生存条件受到制约时,种群的发展与其生存能力的大小密切相关，两种或者两种以上的不同种群所需的生存资源大概相同时,在同样的环境下,生存能力强的种群肯定能赢得种群竞争的胜利[14]。就如同一片草场中的牧草和毒杂草,它们的生存资源基本相同,毒杂草的生存能力强,最后牧草将会被毒杂草淘汰。利用David& Moore（1954)方法、Iwao（1968,1972） $\stackrel { * } { m } - m$ 回归法、平均拥挤度指标 Lloyd,M.(1967)等方法对毒杂草的空间分布做假设检验,证明了毒杂草的入侵影响了草原生态分布,毒杂草的空间分布型也由最初的均匀分布演变成聚集分布。

本文在假设参数时,认为毒杂草的生存能力略大于牧草,故在模拟中参数取值只考虑这一类情况。由于数据是模拟出来的,可能并不能很贴切的描述实际的情况,但这也可以从一个方面来了解研究毒杂草空间分布,进而进行有关的毒杂草问题的处理。本文元胞自动机的规则是自己设定的,并且采用的是四邻域,这个是可以使用八邻域、二十四邻域,得到进一步推广延伸,也就是说本文使用的元胞自动机为冯诺依曼型,可推广为摩尔型以及扩展摩尔型[15-19]。

# 参考文献（References）：

[1]AndersonR,MaR,JoyseyK,MisonD,onwaGR,CartwellR,opsonHVionB.Theivasiopersistenceadedfinfectiousdiseasialdplantoutioopcalsactioofholietyfoolocal，1986,314(1167): 533-570.  
[2］安志兰，郭笃发，褚栋，刘国霞，范仲学.生物入侵对我国生态环境的影响及其控制策略.山东农业科学,2007，（1)：87-91.

http ://www.ecologica.cn

［3」宋晓丰，叶桂峰.我国外来生物入侵的现状、危害及防治研究.生物学通报，2008，43（7）：24-26.  
［4］林培群，余雪标.生物入侵的现状及其危害与防治.华南热带农业大学学报，2006，12（2）：61-65.  
[5］刘华，刘志广，高猛，张丰盘，李自珍.有色环境噪音下空间种群的一致性与灭绝.兰州大学学报：自然科学版,2008，44(4)：99-102.  
［6］潘士虎.用元胞自动机模型模拟教学楼疏散过程[D].桂林：广西师范大学，2010.  
［7］吕凯.元胞自动机的研究及模型的建立［D].哈尔滨：哈尔滨理工大学，2007.  
[8］刘华，刘志广，苏敏，李自珍.聚集效应对宿主—寄生物种群模型动态行为的影响.山东大学学报；理学版,2008,43（8)：31-34,37-37.  
[9] 付军，朱宏.两种群相互作用模型的定性分析及应用.吉林师范大学学报：自然科学版，2006,27（3）：7-8.  
[10] 杨正清.两种群相互作用模型的全局渐近稳定性.生物数学学报，1994，（3)：33-36.  
[11] 姜启源，谢金星，叶俊.数学模型(第四版).北京：高等教育出版社，2011：223-246.  
[12]MatisJengsgsreadofologicalppulatiosusingtochasticoparntalodelsitirtataticaloc1995，126(2) : 215-247.  
[13］王德好.毒麦空间分布型及其抽样面积的研究.杂草科学，1990，（4)：28-30.  
[14］郭树江，杨自辉，王多泽,李得禄，李爱德，詹科杰，王强强.民勤绿洲一荒漠过渡带植物物种多样性及其优势种群空间分布格局研究.  
水土保持研究，2011，18(3)：92-96.  
[15］贾斌，高自友，李克平，李新刚.基于元胞自动机的交通系统建模与模拟.北京：科学出版社，2007：9-18.  
[16] 刘永欣.基于元胞自动机的交通流研究[D].成都：西南交通大学，2003：9-27. .  
[17］李群，雷永林，侯洪涛，朱一凡.仿真模型设计与执行.北京：电子工业出版社，2010：355-362.  
[18] GustafsonL，SteadM.Bringingconsistencytosimulationofpopulationmodels-Pssonsimulationasabridgebetweemicroadmacosimulation.Mathematical Biosciences，2007，209(2）：361-385.  
[19]EngenStohastcowhndeictoisatialometricoaopulatoodlwigatodoeatediseathaticalBiosciences，2007，209（1）：240-255.

附录1证明：1)对 $p _ { 1 } ( N _ { 1 } , 0 )$ 进行平移变换 $\left\{ { \begin{array} { l } { n _ { 1 } = x - N _ { 1 } } \\ { n _ { 2 } = y } \end{array} } \right.$ 代人模型(1)得：

$$
\begin{array} { l } { \displaystyle { \left\{ \frac { \mathrm { d } n _ { 1 } } { \mathrm { d } t } = - r _ { 1 } n _ { 1 } - \frac { r _ { 1 } a _ { 1 } N _ { 1 } } { N _ { 2 } } n _ { 2 } - \frac { r _ { 1 } } { N _ { 1 } } n _ { 1 } ^ { 2 } - \frac { r _ { 1 } a _ { 1 } } { N _ { 2 } } n _ { 1 } n _ { 2 } \right. } } \\ { \displaystyle { \left\{ \frac { \mathrm { d } n _ { 2 } } { \mathrm { d } t } = r _ { 2 } \left( 1 - a _ { 2 } \right) n _ { 2 } - \frac { r _ { 1 } a _ { 2 } } { N _ { 1 } } n _ { 1 } n _ { 2 } - \frac { r _ { 2 } } { N _ { 2 } } n _ { 2 } ^ { 2 } \right. } } \end{array}
$$

取得线性近似系统为：

$$
\left\{ \begin{array} { l l } { \displaystyle \mathrm { d } n _ { 1 } } \\ { \displaystyle \mathrm { d } t = - r _ { 1 } n _ { 1 } - \frac { r _ { 1 } a _ { 1 } N _ { 1 } } { N _ { 2 } } n _ { 2 } } \\ { \displaystyle } \\ { \displaystyle \mathrm { d } n _ { 2 } } \\ { \displaystyle \mathrm { d } t } \end{array} \right.
$$

其特征方程为： $\left. \begin{array} { c } { \displaystyle { - \frac { r _ { 1 } a _ { 1 } N _ { 1 } } { N _ { 2 } } } } \\ { \lambda - r _ { 2 } ( 1 - a _ { 2 } ) } \end{array} \right| = 0$ ,解得： $\left\{ \begin{array} { l l } { \lambda _ { 1 } = - r _ { 1 } } \\ { \qquad } \\ { \lambda _ { 2 } = r _ { 2 } ( 1 - a _ { 2 } ) } \end{array} \right.$

当α<1,α>1时,特征根有负实部， $p _ { 1 } ( N _ { 1 } , 0 )$ 稳定,否则不稳定（其中 $a _ { 1 } < 1$ 是根据相轨线分析的结果添加的[],这也与生态背景相符合,当 $\boldsymbol { a } _ { 1 } \ < \ 1$ 时,毒杂草的竞争力弱于可食牧草,从而灭绝）。

2)同理可得[1],当 $a _ { 1 } > 1 , a _ { 2 } < 1$ 时， $p _ { 2 } ( 0 , N _ { 2 } )$ 稳定,否则不稳定。

3)对 $p _ { 3 } \bigg ( \frac { N _ { 1 } ( 1 - a _ { 1 } ) } { 1 - a _ { 1 } a _ { 2 } } , \frac { N _ { 2 } ( 1 - a _ { 2 } ) } { 1 - a _ { 1 } a _ { 2 } } \bigg )$ 进行平移变换 $\left\{ \begin{array} { l } { \displaystyle n _ { 1 } = x - \frac { N _ { 1 } ( 1 - a _ { 1 } ) } { 1 - a _ { 1 } a _ { 2 } } } \\ { \displaystyle n _ { 2 } = y - \frac { N _ { 2 } ( 1 - a _ { 2 } ) } { 1 - a _ { 1 } a _ { 2 } } } \end{array} \right.$ ,代入模型(1)得：

$$
\begin{array} { l } { { \displaystyle { \left[ \frac { \mathrm { d } n _ { 1 } } { \mathrm { d } t } = \frac { r _ { 1 } ( a _ { 1 } - 1 ) } { 1 - a _ { 1 } a _ { 2 } } n _ { 1 } - \frac { r _ { 1 } a _ { 1 } N _ { 1 } ( 1 - a _ { 1 } ) } { N _ { 2 } ( 1 - a _ { 1 } a _ { 2 } ) } n _ { 2 } - \frac { r _ { 1 } } { N _ { 1 } } n _ { 1 } ^ { 2 } - \frac { r _ { 1 } a _ { 1 } } { N _ { 2 } } n _ { 1 } n _ { 2 } \right. } } } \\ { { \displaystyle { \left[ \frac { \mathrm { d } n _ { 2 } } { \mathrm { d } t } = - \frac { r _ { 2 } a _ { 2 } N _ { 2 } ( 1 - a _ { 2 } ) } { N _ { 1 } ( 1 - a _ { 1 } a _ { 2 } ) } n _ { 1 } + \frac { r _ { 2 } ( a _ { 2 } - 1 ) } { 1 - a _ { 1 } a _ { 2 } } n _ { 2 } - \frac { r _ { 2 } } { N _ { 2 } } n _ { 2 } ^ { 2 } - \frac { r _ { 2 } a _ { 2 } } { N _ { 1 } } n _ { 1 } n _ { 2 } \right. } } } \end{array}
$$