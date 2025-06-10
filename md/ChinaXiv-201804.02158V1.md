# 基于适应值模糊灰模型的交互式进化计算\*

郭广颂1，文振华1，何琳琳1，郝国生²

(1．郑州航空工业管理学院 机电工程学院，郑州 450046;2.江苏师范大学 计算机科学与技术学院，江苏 徐州221116 )

摘要：针对交互式进化计算过程的评价不确定性问题，对个体适应值预测方法进行了研究。对于个体精确数适应值类型，提出基于模糊灰模型FGM(1，1)预测模糊适应值的方法，降低噪声对适应值的影响。首先，确定了用户满意度与适应值噪声强度的函数关系，构建了噪声强度衡量指标；然后，建立模糊适应值支集宽度约束下的最小噪声强度线性规划，求取模糊适应值预测参数；最后，通过模糊灰模型时间响应序列输出模糊适应值。采用NSGA-II范式实现进化计算，并设计了新的个体序值比较方法和拥挤测度计算公式。将所提方法应用于烤漆门外观选型问题，并与已有典型方法比较。结果表明，所提方法在推荐个体质量、减轻用户疲劳、提高搜索效率等方面均有优越性。

关键词：适应值；模糊；GM(1,1)模型；交互；进化计算 中图分类号：TP301.4 doi: 10.3969/j.issn.1001-3695.2018.01.0034

# Interactive evolutionary computation base on fuzzy grey model of fitness

Guo Guangsong1,Wen Zhenhual, He Linlin1, Hao Guosheng² (1.Schoolof Mechatronics Engineering,Zhengzhou UniversityofAeronautics,Zhengzhou45o046,China; 2.Collgeof Computer Science & Technology Jiangsu Normal University,Xuzhou Jiangsu 22116,China）

Abstract: Aiming at solving uncertainty problemof interactive evolutionarycomputation,this paper studied the fitnes predictionmethod.Inorder tomore efectivelyreduce noise influenceonftness,tis paperputforwardafuzzyfitess prediction method based on fuzzy grey model $\mathrm { F G M } ( 1 , 1 )$ with precise number fitness.First of all, It determined the relationship between noise intensityand fitness function and proposed noise intensity index.Then,It proposed a linear programming with fuzzy fitness set width under therestrictionofnoise intensity minimum,whichisused tocalculate fuzzyfitnessprediction parameters. Finaly,the time response sequence offuzzygrey modeloutput fuzzyftness.NSGA-IIrealized the evolutionary computation which have anew comparison method ofindividual sequence and their congestion measure calculation formula.The proposed method wasappiedto baked lacquerdoordesignproblemandcompared with existing typicalmethods.The experimentalresults confirmend thatthe proposed algorithmhas advantages in improving optimization qualityand alleviating user fatigue while improving its efficiency in exploration.

Key words: fitness; fuzzy; GM(1,1) model; interactive; evolutionary computation

# 0 引言

交互式进化计算（interactive evolutionary computation,IEC）是一种人-机互动计算的衍生类进化计算方法。其主要特征是用户根据可视化进化过程评价个体适应值，机器完成进化任务。由于交互式进化计算可优化人的兴趣、偏好、经验等隐式性能指标，且算法实现简单、优化效果显著。因此，近年来交互式进化计算不仅广泛应用于图形图像优化领域[11，在助听器设计[2]、音乐创作[3]、机器人控制[4]等方面也获得了成功应用。

交互式进化计算存在的主要问题是：用户评价行为存在认知不确定性、偏好波动和人的疲劳，由此带来的个体适应值噪声会使算法进化方向偏离用户期望，导致进化优化结果与用户偏好差距过大。减少用户操作负担，降低评价不确定性，提高适应值准确性是解决这一问题的主要研究思路。窦润亮等人[5]提出根据用户评价过程中的犹豫度调整适应值策略，降低因偏好波动带来的评价不确定性，但该方法对不满足约束条件个体的删除策略仅局限于初始种群，这会使大量劣势个体参与进化，影响优化质量；孙晓燕等人[基于用户偏好有向图权重更新估计当前种群个体适应值，该方法对交互行为可信度及用户偏好表示的刻画仍有较大提升空间。Ishibuch等人[7]仅要求用户对个体进行两两优劣比较的最少评价，通过逻辑推理对个体排序，该方法虽然明显减轻了用户负担，但由于用户提交信息过少，适应值不确定性仍较大。从降低适应值噪声角度开发相关策略，提高评价准确性是解决上述问题的主要切入点。因为适应值的噪声强度变化与用户兴趣/偏好直接相关，根据噪声强度与用户兴趣/偏好的映射关系可以开发修正适应值的方法，从而降低评价不确定性对进化的不利影响。基于此，本文提出基于适应值模糊灰模型的交互式进化计算（interactiveevolutionarycomputation base on fuzzy grey model of fitness,IEC-FGM)。该方法对精确数适应值建立模糊灰模型FGM（1,1)，通过适应值噪声强度与用户满意度的映射约束模糊灰模型预测参数，将精确数适应值预测为更符合偏好的模糊适应值，达到拟合噪声，提高评价准确性的目的。同时，本文方法采用非被占优解排序遗传算法(non-dominated sorting genetic algorithm，NSGA)的改进型NSGA-II作为算法引擎，基于NSGA-II求解多目标优化问题的优异性能，提升本文算法的优化能力。

本文方法的优点在于：a）提出的模糊适应值预测方法，满足了不同进化阶段噪声强度变化对适应值的影响，提高了评价准确性；b)提出的模糊适应值预测方法可应对3种不同类型噪声对适应值的不良影响，增强了算法的鲁棒性；c）采用模糊灰模型可以不增加用户操作负担即可获得个体模糊适应值，从而大大减少了评价耗时；d）采用NSGA-II作为算法引擎，优化能力更强；e）算法实现简单，基于NSGA-II扩展性较强。

本文的贡献主要体现在如下五个方面：a)统一了噪声类型与噪声强度的定性关系，为隐式指标评价建立了理论依据；b)提出了新的适应值噪声强度衡量指标，确立了新的用户满意度与噪声强度函数关系，为研究交互式进化计算评价不确定性打下基础；c）基于噪声强度，设计了新的模糊适应值参数求解方法，偏好与适应值之间的映射更为合理；d)提出了新的个体模糊适应值构建方法，丰富了交互式进化计算适应值赋值形式；e）提出了NSGA-II新的个体Pareto 序值比较方法和拥挤距离计算公式，进一步提升了算法优化性能。

# 1 相关工作

# 1.1 评价不确定性

研究交互式进化计算评价不确定性主要围绕人的认知规律。目前已提出的犹豫度[5]、可信度[6]、满意度[8]、兴趣度[9]、信任度[10]等认知变量的定量计算方法是认知规律研究的重要成果。但这些计算方法均存在一定的局限性：犹豫度的刻画未考虑时间变化对偏好的影响[5]；针对用户鼠标滚动行为的可信度计算方法不能完全适用于其他类型的浏览行为[；兴趣度和信任度的参数需要根据交互场景事先拟合，应用上存在较大约束[9,10]。

特别地，上述研究只关注单一认知变量，对于各变量的内在联系目前还缺乏统一的研究结果，所以，探讨认知规律变量的内在关系对交互式进化计算评价不确定性研究是十分必要的。

# 1.2适应值估计

以评价不确定性的研究结论为基础，最新采用的适应值估计方法有：熵极大准则[11]、有向图[12]、集合进化[13]等。这些结论为研究交互式进化计算适应值估计提供了丰富的理论依据，但是这些方法受各自研究评价不确定性角度的限制，对交互场景、浏览行为、优化对象等因素不能完全兼顾。由于认知规律的复杂性决定了适应值估计方法的多样性，继续研究适应值估计/修正策略仍是十分必要的。

# 2 适应值噪声分析

不失一般性，考虑优化问题：max $f ( x , t ) = f ( x ( t ) )$ $x \in S \subseteq R ^ { d }$ ， $x$ 是 $d$ 维决策变量，S是其取值范围， $f ( x , t )$ 是被优化的性能指标，且不能用显式函数表示。记第 $t \ ( t { > } 0 )$ 代进化种群 $x ( t )$ 中的第 $k$ 个进化个体为 $x _ { k } ( t )$ ， $k = 1 , 2 , \cdots , N , N$ 为种群规模， $x _ { k } ( t )$ 的适应值为 $f ( x _ { k } ( t ) )$ ， $x _ { k } \left( t \right) \in x ( t )$ 。

在人一机交互环境下，用户的兴趣/偏好主要通过个体适应值表达，且适应值与用户兴趣/偏好呈正向性。同时，用户兴趣/偏好可以用兴趣度/满意度定量刻画，在更广泛的意义上，兴趣度/满意度不仅包含个体适应值，还涵盖了用户的浏览行为（关注时间、点击次数、收藏、保存、打印行为、浏览路径等)。由于主观评价存在不可避免的不确定性，严重影响了评价结果的可信性。不确定性越强，评价结果可信度越低，这给定量刻画用户兴趣/偏好带来很大困难。更重要地，用户兴趣/偏好与主观评价不确定性还存在内在联系，且两者呈非同向性，这给分析用户评价不确定性带来很大挑战。

结合上述，用户评价过程如图1所示。图中用户兴趣与用户偏好是评价过程的主导因素，且两者意义存在交叉。评价结果（适应值）因评价不确定性存在适应值噪声，噪声强度会影响评价的可信性；评价可信性反映了用户的兴趣/偏好，同时用户的兴趣/偏好也影响评价可信性。图中实线箭头表示用户兴趣/偏好与适应值的正向性，虚线箭头表示评价不确定性与评价结果可信性的负向性，双箭头代表用户满意度与噪声强度的映射关系。

![](images/b6be0762d77d8886003206e24bfd80a72727aa253093440a834eae669afbf504.jpg)  
图1用户评价过程

通常情况，人-机交互环境下的评价噪声类型可分为加性噪声、乘性噪声和随机噪声等3种[14]。

1)加性噪声

$$
f ( x _ { k } ( t ) ) = f ^ { * } ( x _ { k } ( t ) ) + I _ { k } \cdot N ( 0 , 1 )
$$

其中： $f ( x _ { k } ( t ) )$ 是用户对个体 $x _ { k } ( t )$ 的评价值， $f ^ { \prime } ( x _ { k } ( t ) )$ 是个体真实适应值， $I _ { k }$ 是评价噪声分布的标准差，代表了个体适应值噪声强度，且评价噪声呈高斯分布。

2）乘性噪声

$$
f ( x _ { k } ( t ) ) = f ^ { * } ( x _ { k } ( t ) ) \cdot ( I _ { k } \cdot N ( 0 , 1 ) )
$$

3）随机噪声

$$
f ( x _ { k } ( t ) ) = { \left\{ \begin{array} { l l } { f ^ { \prime } ( x _ { k } ( t ) ) \quad 1 - p } \\ { f ( x _ { k } ^ { } \ddots ( t ) ) \quad p } \end{array} \right. }
$$

其中： $p$ 为随机概率， $\boldsymbol { p } \in [ 0 , 1 ]$ ， $x _ { k } ^ { } { ' } ( t )$ 是根据个体 $x _ { k } ( t )$ 随机选择的其他个体。

在评价过程中，这三种噪声类型可以单独出现，也可能同时出现。式 $( 1 ) \sim ( 3 )$ 表达了噪声对评价结果的影响，其中噪声强度直接决定了评价的不确定性。为精确表达噪声的统计意义，噪声强度表示为

$$
I _ { k } = \lambda _ { k } E ( f ( x _ { k } ( t ) ) ) + \varepsilon _ { k }
$$

其中： $E ( \cdot )$ 是与适应值相关的函数， $\lambda _ { k }$ 是参数， $\mathcal { E } _ { k }$ 是常数。

可以看到，噪声强度是关于个体适应值的函数，且随时间变化而改变。适应值类型不同，噪声强度也会不同。噪声强度越大，评价不确定性就越大，评价结果可信性就越低。由于传统的精确数适应值包含信息较少，所以噪声强度刻画较为困难，提取真实适应值难度较大。如果采用区间数、模糊数等不确定数表达适应值可以较好的刻画噪声对评价结果的影响[15]，从而能更客观的表达用户偏好。

评价结果的可信性除受噪声影响外，还与用户兴趣/偏好相关。一般来说，用户常常对于明显感兴趣和明显不感兴趣个体的判别可信度较高，而对于介于二者之间个体的判别可信度较低。同时，用户对特别喜欢和特别不喜欢的个体评价不确定性较小，噪声强度也较小，介于二者之间个体的噪声强度一般较大。基于此，用户满意度与噪声强度之间的关系可以用高斯函数刻画。为方便计算，本文采用直线方程表示成式（5)，其曲线如图2所示。图中 $I ^ { \mathrm { m a x } }$ 是种群中个体适应值噪声强度的最大值， ${ \beta } ^ { \mathrm { m a x } }$ 和 ${ \beta } ^ { \mathrm { m i n } }$ 分别是用户对种群个体的满意度最大值和满意度最小值。

$$
\begin{array} { r } { I _ { k } = \left\{ \begin{array} { l l } { \displaystyle \frac { 2 I ^ { \mathrm { m a x } } } { \beta ^ { \mathrm { m a x } } - \beta ^ { \mathrm { m i n } } } ( \beta _ { k } - \beta ^ { \mathrm { m i n } } ) } & { \displaystyle \beta ^ { \mathrm { m i n } } \leq \beta _ { k } \leq \frac { \beta ^ { \mathrm { m i n } } + \beta ^ { \mathrm { m a x } } } { 2 } } \\ { \displaystyle \frac { - 2 I ^ { \mathrm { m a x } } } { \beta ^ { \mathrm { m a x } } - \beta ^ { \mathrm { m i n } } } ( \beta _ { k } - \beta ^ { \mathrm { m a x } } ) } & { \displaystyle \frac { \beta ^ { \mathrm { m i n } } + \beta ^ { \mathrm { m a x } } } { 2 } \leq \beta _ { k } \leq \beta ^ { \mathrm { m a x } } } \end{array} \right. } \end{array}
$$

求解式（5)，可以得到用户对个体 $x _ { k } ( t )$ 的满意度 $\beta _ { k }$ ：

$$
\beta _ { k } = \left\{ \begin{array} { l l } { \displaystyle \beta ^ { \mathrm { m i n } } + \frac { \beta ^ { \mathrm { m a x } } - \beta ^ { \mathrm { m i n } } } { 2 I ^ { \mathrm { m a x } } } \cdot I _ { k } \quad f ( x _ { k } ( t ) ) \geq \frac { 1 } { N } \sum _ { q = 1 } ^ { N } f ( x _ { q } ( t ) ) } \\ { \displaystyle \beta ^ { \mathrm { m a x } } - \frac { \beta ^ { \mathrm { m a x } } - \beta ^ { \mathrm { m i n } } } { 2 I ^ { \mathrm { m a x } } } \cdot I _ { k } } \end{array} \right.
$$

按式（6）计算 $\beta _ { k }$ ，当个体适应值较大时（大于种群平均适应值)，选取较大的用户满意度；否则选取较小的用户满意度。这种选择符合用户兴趣/偏好与适应值之间的正向性。

再对 $\beta _ { k }$ 进行归一化处理，如下式所示：

$$
\theta _ { k } = \frac { \beta _ { k } - \beta ^ { \mathrm { m i n } } } { \beta ^ { \mathrm { m a x } } - \beta ^ { \mathrm { m i n } } }
$$

式（7）的意义是：如果某一个体的用户满意度是种群中所有个体中最小的，则该个体对应的满意度 $\theta _ { k }$ 值为0；如果某一个体的用户满意度是种群中所有个体中最大的，则该个体的 $\theta _ { k }$ 值为1；对于用户满意度介于两者之间的个体样本有 $\theta _ { k } \in ( 0 , 1 )$ u

![](images/29485e26446ae8a401e06c6c2bb36c2798faec312947ca367adbff46372be2a7.jpg)  
图2满意度与噪声强度关系曲线

# 3 适应值模糊灰模型建模与预测

# 3.1模糊灰模型 FGM(1,1)

灰色系统理论是研究不确定性系统的重要方法[16]。针对灰色系统理论最基本的GM（1,1）模型预测误差偏大的缺陷，曹锐勤提出了映射累加AGO值及模糊参数求输出模糊数预测值的模糊灰模型FGM（1,1）[17]。该模型对于输入为精确数且环境存在不确定的条件下，可以获得一个可能的外插预测区间而得到较充分的预测信息，减少信息不充分下的决策损失。

鉴于交互式进化计算评价不确定性问题符合灰色系统理论适用条件，本节对人-机交互过程中用户提交的个体精确数适应值采用模糊灰模型FGM（1,1）建模，通过求解该模型获得个体模糊适应值，从而降低适应值评价不确定性。为方便计算，本文采用三角形隶属函数表示模糊集合。将用户评价的个体精确数适应值 $f ( x _ { k } ( t ) )$ ， $x _ { k } \left( t \right) \in x ( t )$ 重新记为$F _ { 0 } = ( f _ { 0 } ( x _ { 1 } ( t ) ) , f _ { 0 } ( x _ { 2 } ( t ) ) , \cdots , f _ { 0 } ( x _ { N } ( t ) ) )$ 构成个体适应值原始序列，则 $F _ { 0 }$ 的 1-AGO 序列为 $F _ { 1 } = ( f _ { 1 } ( x _ { 1 } ( t ) ) , f _ { 1 } ( x _ { 2 } ( t ) ) , \cdots , f _ { 1 } ( x _ { N } ( t ) ) )$ ，$F _ { 1 } = \left( \sum _ { k = 1 } ^ { q } f _ { 0 } ( x _ { k } ( t ) \right) , q = 1 , 2 , \cdots N$ 。 $F _ { 0 }$ 的灰模型GM（1,1）为[18]

$$
\frac { d f _ { 1 } ( x _ { k } ( t ) ) } { d k } + a f _ { 1 } ( x _ { k } ( t ) ) = b , k = 1 , 2 , \cdots N
$$

$\frac { d f _ { 1 } ( x _ { k } ( t ) ) } { \dots } \approx \frac { f _ { 1 } ( x _ { k + 1 } ( t ) ) - f _ { 1 } ( x _ { k } ( t ) ) } { \dots } =$ 由于dk 1 所以式（8）也可以写为$f _ { 1 } ( x _ { k + 1 } ( t ) ) - f _ { 1 } ( x _ { k } ( t ) ) = f _ { 0 } ( x _ { k + 1 } ( t ) ) , \forall k \geq 1$ （204号

$$
f _ { 0 } ( x _ { k + 1 } ( t ) ) + a z _ { 1 } ( x _ { k + 1 } ( t ) ) = b , k = 1 , 2 , \cdots N
$$

其中： $z _ { 1 } ( x _ { k + 1 } ( t ) ) = \alpha f _ { 1 } ( x _ { k } ( t ) ) + ( 1 - \alpha ) f _ { 1 } ( x _ { k + 1 } ( t ) )$ ， $\alpha \in [ 0 , 1 ]$ 为权重系数，一般取 $\alpha = 0 . 5 \ : _ { \circ } a$ 为发展系数; $b$ 为灰色作用量， $( a , b ) ^ { T }$ 可以通过最小二乘参数估计。

定义 $\mathbf { 1 } ^ { [ 1 7 ] }$ 记从 $F _ { 0 }$ 预测的模糊适应值原始序列为$\tilde { F } _ { 0 } = ( \tilde { f } _ { 0 } ( x _ { 1 } ( t ) ) , \tilde { f } _ { 0 } ( x _ { 2 } ( t ) ) , \cdots , \tilde { f } _ { 0 } ( x _ { N } ( t ) ) )$ ，则 $\tilde { F } _ { \scriptscriptstyle 0 }$ 的 1-AGO 序列为$\tilde { F _ { 1 } } = ( \tilde { f _ { 1 } } ( x _ { 1 } ( t ) ) , \tilde { f _ { 1 } } ( x _ { 2 } ( t ) ) , \cdots , \tilde { f _ { 1 } } ( x _ { N } ( t ) ) )$ ， $\tilde { F } _ { 0 }$ 的模糊灰模型 $F G M$ （1,1）为

$$
\frac { d \tilde { f } _ { 1 } ( x _ { k } ( t ) ) } { d k } + \tilde { A } \tilde { f } _ { 1 } ( x _ { k } ( t ) ) = \tilde { B } , k = 1 , 2 , \cdots N
$$

或

$$
\tilde { f } _ { 0 } ( x _ { k + 1 } ( t ) ) + \tilde { A } \tilde { z } _ { 1 } ( x _ { k + 1 } ( t ) ) = \tilde { B } , k = 1 , 2 , \cdots N
$$

式(10)中， $\tilde { z } _ { 1 } ( x _ { k + 1 } ( t ) ) = \alpha \tilde { f } _ { 1 } ( x _ { k } ( t ) ) + ( 1 - \alpha ) \tilde { f } _ { 1 } ( x _ { k + 1 } ( t ) ) ) \mathrm { ~ , ~ }$ $\tilde { A }$ 和 $\tilde { B }$ 均为模糊数。 $\tilde { A }$ 的中心值为 $A$ ，支集宽度为 $A _ { 1 }$ ，记$\tilde { \cal A } = ( A , A _ { 1 } )$ 。相似地， $\tilde { B } = ( B , B _ { 1 } )$ ， $A , B , A _ { 1 } , B _ { 1 }$ 称为模糊参数。

通过式（10）可将模糊适应值 $\tilde { f } _ { 0 } ( x _ { k } ( t ) )$ 的隶属函数表示为

$$
\mu ( f _ { 0 } ( x _ { k } ( t ) ) ) = \left\{ \begin{array} { c c } { \displaystyle 1 - \frac { \left| f _ { 0 } ( x _ { k } ( t ) ) - ( B - A \cdot z _ { 1 } ( x _ { k } ( t ) ) ) \right| } { B _ { 1 } - A _ { 1 } \cdot z _ { 1 } ( x _ { k } ( t ) ) } } & { B ^ { L } \leq f _ { 0 } ( x _ { k } ( t ) ) \leq B ^ { U } \neq 0 , } \\ & { \qquad \forall k = 2 , 3 , \cdots , N } \\ { 0 } & { o t h e r w i s e } \end{array} \right.
$$

其中： $B - A \cdot z _ { 1 } ( x _ { k } ( t ) )$ 是 $\tilde { f } _ { 0 } ( x _ { k } ( t ) )$ 的中心值， $B _ { 1 } - A _ { 1 } \cdot z _ { 1 } ( x _ { k } ( t ) )$ 是支集宽度。另外， $z _ { 1 } ( x _ { k } ( t ) ) = \alpha f _ { 1 } ( x _ { k } ( t ) ) + ( 1 - \alpha ) f _ { 1 } ( x _ { k - 1 } ( t ) ) )$ ，$B ^ { L } = B - A \cdot z _ { 1 } ( x _ { k } ( t ) ) - ( B _ { 1 } - A _ { 1 } \cdot z _ { 1 } ( x _ { k } ( t ) ) )$   
$B ^ { U } = B - A \cdot z _ { 1 } ( x _ { k } ( t ) ) + ( B _ { 1 } - A _ { 1 } \cdot z _ { 1 } ( x _ { k } ( t ) ) ) \circ$ （204

式（11）将精确数适应值预测为模糊数适应值，拟合了评价不确定性，偏好信息量更加丰富，偏好表达更加准确。

根据2节用户满意性与噪声强度的关系，针对模糊适应值特点，噪声强度衡量指标定义为

$$
I _ { k } = { \frac { B _ { 1 } - A _ { 1 } \cdot z _ { 1 } ( x _ { k } ( t ) ) } { \left| ( B - A \cdot z _ { 1 } ( x _ { k } ( t ) ) - { \frac { 1 } { N } } \sum _ { j = 1 } ^ { N } ( B - A \cdot z _ { 1 } ( x _ { k } ( t ) ) \right| } }
$$

式（12）的意义是：模糊适应值支集宽度 $B _ { 1 } - A _ { 1 } \cdot z _ { 1 } ( x _ { k } ( t ) )$ 越小，且距离当前种群模糊适应值平均中心值$\frac { 1 } { N } \sum _ { j = 1 } ^ { N } ( B - A \cdot z _ { 1 } ( x _ { k } ( t ) )$ 越远的个体 $x _ { k } ( t )$ ，即为用户特别满意和特别不满意、且评价不确定性小的个体， $I _ { k }$ 值越小，表明该个体的噪声强度较小；对于支集宽度较大，而模糊适应值中心值也距离当前种群模糊适应值平均中心值远的个体而言，实质是此时评价不确定性增大，相应的 $I _ { k }$ 值会增加；类似地，对于模糊适应值支集宽度大，而中心值距离当前种群种群模糊适应值平均中心值相对较近的个体而言， $I _ { k }$ 值亦较大，其噪声强度也较大。因此，上式的刻画噪声强度不仅满足评价不确定性变化规律，同时符合用户偏好。

为了降低适应值噪声强度，建立如下线性规划模型：

$$
\begin{array} { r l } & { M i n { \displaystyle \sum _ { k = 2 } ^ { N } } I _ { k } } \\ & { s t . ( B - A z _ { 1 } ( x _ { k } ( t ) ) ) + \theta _ { k } \cdot ( B _ { 1 } - A _ { 1 } z _ { 1 } ( x _ { k } ( t ) ) ) \geq f _ { 0 } ( x _ { k } ( t ) ) \ k = 2 , 3 , \cdots , N } \\ & { \quad ( B - A z _ { 1 } ( x _ { k } ( t ) ) ) - \theta _ { k } \cdot ( B _ { 1 } - A _ { 1 } z _ { 1 } ( x _ { k } ( t ) ) ) \leq f _ { 0 } ( x _ { k } ( t ) ) \ k = 2 , 3 , \cdots , N } \\ & { \quad A , B , A _ { 1 } , B _ { 1 } \in R , 0 \leq \theta _ { k } \leq 1 } \end{array}
$$

其中： $\theta _ { k }$ 是用户满意度 $\beta _ { k }$ 的归一化值， $\beta _ { k }$ 按式（6）计算，式（6）成立条件中的 $f ( x _ { k } ( t ) )$ 这里替换为 $\tilde { f } _ { 0 } ( x _ { k } ( t ) )$ 的中心值$B - A \cdot z _ { 1 } ( x _ { k } ( t ) )$ 。

式（13)的意义是：为获得种群个体适应值最小噪声强度，约束条件为个体模糊适应值支集下限不大于原精确数适应值，同时个体模糊适应值支集上限不小于原精确数适应值。其中，满意度 $\theta _ { k }$ 影响支集宽度， $\theta _ { k }$ 增大，模糊参数会相应减小。求解上述线性规划模型，可以求出模糊参数 $A , B , A _ { 1 } , B _ { 1 }$ ，进而得到预测的个体模糊适应值 $\tilde { f } ( x _ { k } ( t ) )$ 。

# 3.2模糊适应值预测

定义 $\pmb { 2 } ^ { [ 1 7 ] }$ 模糊灰模型FGM（1,1）的时间响应序列为（取$\tilde { f } _ { 1 } ( x _ { 0 } ( t ) ) = \tilde { f } _ { 0 } ( x _ { 1 } ( t ) ) \mathrm { ~ } .$ ）

$$
\hat { \tilde { f } } _ { 1 } ( x _ { k } ( t ) ) = ( \tilde { f _ { 0 } } ( x _ { 1 } ( t ) ) - \frac { \tilde { B } } { \tilde { A } } ) \cdot e ^ { - \tilde { A } ( k - 1 ) } + \frac { \tilde { B } } { \tilde { A } } \cdot \forall k \geq 2
$$

由于式（14）中各变量均为模糊集，所以式（14）的计算分为 $\hat { \tilde { f } } _ { 1 } ( x _ { k } ( t ) )$ 的支集下限和上限两个问题求解。

记 $\hat { \ b { f } } _ { 1 } ^ { L } ( \ b { x } _ { k } ( t ) )$ 为 $\hat { \tilde { f } } _ { 1 } ( x _ { k } ( t ) )$ 的支集下限，则

$$
\begin{array} { l } { \displaystyle \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) = \Biggl [ f _ { 0 } ( x _ { 1 } ( t ) ) - \frac { B - ( 1 - \alpha ) B _ { 1 } } { A - ( 1 - \alpha ) A _ { 1 } } \Biggr ] \cdot e ^ { - ( A - ( 1 - \alpha ) A _ { 1 } ) ( k - 1 ) } } \\ { \displaystyle + \frac { B - ( 1 - \alpha ) B _ { 1 } } { A - ( 1 - \alpha ) A _ { 1 } } . \forall k \geq 2 } \end{array}
$$

记 $\hat { f } _ { 1 } ^ { U } ( x _ { k } ( t ) )$ 为 $\hat { \tilde { f } } _ { 1 } ( x _ { k } ( t ) )$ 的支集上限，则

$$
\begin{array} { l } { \displaystyle \hat { f } _ { 1 } ^ { U } ( x _ { k } ( t ) ) = \Biggl [ f _ { 0 } ( x _ { 1 } ( t ) ) - \frac { B + ( 1 - \alpha ) B _ { 1 } } { A + ( 1 - \alpha ) A _ { 1 } } \Biggr ] \cdot e ^ { - ( A + ( 1 - \alpha ) A _ { 1 } ) ( k - 1 ) } } \\ { \displaystyle + \frac { B + ( 1 - \alpha ) B _ { 1 } } { A + ( 1 - \alpha ) A _ { 1 } } . \forall k \geq 2 } \end{array}
$$

证明[17]对于任意 $\alpha$ ，考虑 $\tilde { f } _ { 1 } ( x _ { k } ( t ) )$ 的支集下限 $\hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) )$ 州由式（9）有

$$
\begin{array} { r l r } & { } & { \frac { d \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) } { d k } = [ B - ( 1 - \alpha ) B _ { 1 } ] - [ A - ( 1 - \alpha ) A _ { 1 } ] \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) } \\ & { } & { \cdot \cdot \displaystyle \int _ { [ B - ( 1 - \alpha ) B _ { 1 } ] - [ A - ( 1 - \alpha ) A _ { 1 } ] \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) } d \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) = \int 1 d k } \end{array}
$$

$$
Z = [ B - ( 1 - \alpha ) B _ { 1 } ] - [ A - ( 1 - \alpha ) A _ { 1 } ] \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) )
$$

$$
\begin{array} { l l } { \displaystyle } & { \displaystyle \Rightarrow - [ A - ( 1 - \alpha ) A _ { \mathrm { 1 } } ] d \hat { f } _ { \mathrm { 1 } } ^ { L } ( x _ { k } ( t ) ) = d Z } \\ { \displaystyle } & { \displaystyle \cdot \int \frac { 1 } { [ B - ( 1 - \alpha ) B _ { \mathrm { 1 } } ] - [ A - ( 1 - \alpha ) A _ { \mathrm { 1 } } ] \hat { f } _ { \mathrm { 1 } } ^ { L } ( x _ { k } ( t ) ) } d \hat { f } _ { \mathrm { 1 } } ^ { L } ( x _ { k } ( t ) ) } \\ { \displaystyle } & { \displaystyle = \int \frac { 1 } { Z } \cdot \frac { - 1 } { A - ( 1 - \alpha ) A _ { \mathrm { 1 } } } d Z = \int 1 d k } \end{array}
$$

$$
\begin{array} { r l } & { \because [ B - ( 1 - \alpha ) B _ { 1 } ] - [ A - ( 1 - \alpha ) A _ { 1 } ] \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) = Z = e ^ { - [ A - ( 1 - \alpha ) A _ { 1 } ] k + C } } \\ & { \therefore \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) = \displaystyle \frac { B - ( 1 - \alpha ) B _ { 1 } } { A - ( 1 - \alpha ) A _ { 1 } } - \frac { 1 } { A - ( 1 - \alpha ) A _ { 1 } } e ^ { - [ A - ( 1 - \alpha ) A _ { 1 } ] k + C } \quad ( \ast ) } \end{array}
$$

由于 $f _ { 1 } ( x _ { 1 } ( t ) ) = f _ { 0 } ( x _ { 1 } ( t ) )$

$$
\Rightarrow f _ { 1 } ( x _ { 1 } ( t ) ) = \frac { B - ( 1 - \alpha ) B _ { 1 } } { A - ( 1 - \alpha ) A _ { 1 } } - \frac { 1 } { A - ( 1 - \alpha ) A _ { 1 } } e ^ { - [ A - ( 1 - \alpha ) A _ { 1 } ] + C } = f _ { 0 } ( x _ { 1 } ( t ) )
$$

$$
\begin{array} { r l } & { \Rightarrow C = [ A - ( 1 - \alpha ) A _ { 1 } ] } \\ & { + \ln \left\{ - [ A - ( 1 - \alpha ) A _ { 1 } ] \cdot f _ { 0 } ( x _ { 1 } ( t ) ) + [ B - ( 1 - \alpha ) B _ { 1 } ] \right\} } \end{array}
$$

将 $C$ 代入式 $( ^ { * } )$ ，可得式（15）

同理，可得式（16)。证毕。

由定义2，得到FGM（1,1）的还原值

$$
\hat { \tilde { f } } _ { 0 } ( x _ { k } ( t ) ) = \hat { \tilde { f } } _ { 1 } ( x _ { k } ( t ) ) - \hat { \tilde { f } } _ { 1 } ( x _ { k - 1 } ( t ) ) . \forall k \geq 2
$$

根据式（15）（16)，可求模糊适应值 $\tilde { f } _ { 0 } ( x _ { k } ( t ) )$ 的支集下限和上限还原值为

$$
\hat { f } _ { 0 } ^ { L } ( x _ { k } ( t ) ) = \hat { f } _ { 1 } ^ { L } ( x _ { k } ( t ) ) - \hat { f } _ { 1 } ^ { L } ( x _ { k - 1 } ( t ) ) . \forall k \geq 2
$$

$$
\hat { f } _ { 0 } ^ { U } ( x _ { k } ( t ) ) = \hat { f } _ { 1 } ^ { U } ( x _ { k } ( t ) ) - \hat { f } _ { 1 } ^ { U } ( x _ { k - 1 } ( t ) ) . \forall k \ge 2
$$

$\tilde { f } _ { 0 } ( x _ { k } ( t ) )$ 的中心值为 $\hat { f } _ { 0 } ( x _ { k } ( t ) )$

$$
\begin{array} { r } { \hat { f } _ { 0 } ( x _ { k } ( t ) ) = \hat { f } _ { 1 } ( x _ { k } ( t ) ) - \hat { f } _ { 1 } ( x _ { k - 1 } ( t ) ) . \forall k \ge 2 } \end{array}
$$

其中： $\hat { f } _ { 1 } ( x _ { k } ( t ) ) = ( f _ { 1 } ( x _ { 0 } ( t ) ) - \frac { B } { A } ) e ^ { - A ( k - 1 ) } + \frac { B } { A } \circ$

最后，个体 $x _ { k } ( t )$ 的预测模糊适应值与原精确数适应值的相对误差为

$$
\Delta ( k ) = \frac { \Big | \hat { f } _ { 0 } ( x _ { k } ( t ) ) - f _ { 0 } ( x _ { k } ( t ) ) \Big | } { f _ { 0 } ( x _ { k } ( t ) ) } \cdot 1 0 0 \%
$$

平均相对误差为

$$
\Delta = \frac { \displaystyle \sum _ { k = 2 } ^ { N } \Delta ( k ) } { N - 1 }
$$

# 4 算法设计

NSGA-II是一种有效解决多目标优化问题的进化优化算法[19]。该算法的特点是：a)采用基于分等级的快速非支配排序方法，算法的复杂度大大降低；b）采用拥挤距离比较准则，适应值共享策略不需要指定共享半径，并且其作为排序后同级间的比较准则，有利于保持种群多样性和分布均匀；c）引入精英保留策略，子代种群和父代种群共同竞争产生下一代种群，增大了种群规模，有利于提高种群整体进化水平。

由于交互式进化计算要求进化代数不能太多，用户评价个体数目不能太大。相比于传统GA只有选择、交叉和变异3种遗传操作，NSGA-II的求解能力更强。所以，采用NSGA-II可以充分利用其能扩大种群规模、保持种群多样性和分布均匀等特点，高效实现算法进化，挖掘潜在的偏好解。基于此，采用NSGA-II具有更强的合理性。

采用NSGA-II范式求解基于个体适应值模糊灰模型的交互式进化优化问题，需解决如下三个主要问题：

a）个体Pareto序值。记任意个体 $x _ { i } ( t )$ 和 $x _ { j } ( t )$ ，$i , j \in \{ 1 , 2 , \cdots N \}$ ，若其满意度 $\beta _ { i } \geq \beta _ { j }$ ，则个体 Pareto 序值$\operatorname { r a n k } ( x _ { i } ( t ) ) \geq \operatorname { r a n k } ( x _ { j } ( t ) )$ 。

b)拥挤测度。鉴于拥挤测度主要用于选择具有相同序值的优化解，因此，这里仅考虑相同序值优化解的拥挤测度。对于具有相同序值的优化解 $x _ { i } ( t )$ 和 $x _ { j } ( t )$ ，其模糊适应值分别为$\tilde { f } ( x _ { i } ( t ) )$ 和 $\tilde { f } ( x _ { j } ( t ) )$ ，它们的交区间为支集的交集，记为$\overleftrightarrow { f } ( x _ { i } ( t ) ) \bigcap \overleftrightarrow { f } ( x _ { j } ( t ) )$ ，其宽度为 $w ( \ddot { f } ( x _ { i } ( t ) ) \bigcap \ddot { f } ( x _ { j } ( t ) ) )$ ，那么， $x _ { i } ( t )$ 和$x _ { j } ( t )$ 的重叠度可以表示为

$$
\gamma ( x _ { i } ( t ) , x _ { j } ( t ) ) = w ( \overleftrightarrow { f } ( x _ { i } ( t ) ) \bigcap \overleftrightarrow { f } ( x _ { j } ( t ) ) )
$$

如果 $\tilde { f } ( x _ { i } ( t ) )$ 和 $\tilde { f } ( x _ { j } ( t ) )$ 的支集不相交，则

$$
\gamma ( x _ { i } ( t ) , x _ { j } ( t ) ) = 0 \ : _ { \circ }
$$

记 $\overleftrightarrow { f } ( x _ { i } ( t ) )$ 的中点为 $m ( \ddot { f } ( x _ { i } ( t ) ) )$ ，则 $x _ { i } ( t )$ 和 $x _ { j } ( t )$ 的距离可以表示为

$$
D ( x _ { i } ( t ) , x _ { j } ( t ) ) { = } \frac { | m ( \stackrel {  } { f } ( x _ { i } ( t ) ) ) - m ( \stackrel {  } { f } ( x _ { j } ( t ) ) ) | } { \gamma ( x _ { i } ( t ) , x _ { j } ( t ) ) + 1 }
$$

现考虑某一序值的个体 $x _ { i } ( t )$ ，假设按式（22)得到的与 $x _ { i } ( t )$ 距离最近的两个具有相同序值的个体分别为 $x _ { j } ( t )$ 和 $x _ { k } ( t )$ 。容易理解， $D ( x _ { i } ( t ) , x _ { j } ( t ) )$ 和 $D ( x _ { i } ( t ) , x _ { k } ( t ) )$ 越大，说明 $x _ { i } ( t )$ 的拥挤程度越小；反之，说明 $x _ { i } ( t )$ 的拥挤程度越大。鉴于此， $x _ { i } ( t )$ 的拥挤测度可以表示为

$$
C ( x _ { i } ( t ) ) = \frac { D ( ( x _ { i } ( t ) , x _ { j } ( t ) ) + D ( ( x _ { i } ( t ) , x _ { k } ( t ) ) } { 2 }
$$

c）临时种群个体适应值估计。由于NSGA-II 需要将新生成的临时种群与原种群合并后对个体排序，所以，本文采用文献[20]的方法根据与原种群个体的相似性估计临时种群个体适应值。

本文算法的步骤如下：

a)初始化规模为 $N$ 的种群 $P ( 0 )$ ；取进化代数 $t = 0$ ·

b)用户评价个体，并判断是否满足终止准则，若是，转步骤g);

c)根据2节的方法对适应值序列建立模糊灰模型，预测个体模糊适应值 $\tilde { f } ( x _ { k } ( t ) )$

d)实施交叉、变异操作生成相同种群规模的临时种群 $Q ( t )$ · e)合并种群 $P ( t )$ 和 $Q ( t )$ ，记为 $R ( t )$

f)采用本节给出的进化个体排序方法，选取 $R ( t )$ 中前 $N$ 个个体，构成种群 $P ( t + 1 )$ ，令 $t = t + 1$ ，转步骤b);

g)停止进化，输出优化结果。

# 5 实例验证

# 5.1染色体编码

烤漆门是室内建筑重要组成部分，其外观设计对室内装修效果有重要影响。由于烤漆门造型、色彩类型多样，且要求与室内装饰风格协调，所以用户对烤漆门的审美标准不尽相同，烤漆门外观选择体现出强烈的个性化特点。评价结果具有很强的不确定性，难以准确定量计算。这是一类典型的传统进化优化方法无法解决、但适合交互式进化求解的隐式指标优化问题。鉴于此，本文以烤漆门外观为优化对象，基于NSGA-II算法开发烤漆门外观选型交互式进化优化平台，验证本文算法的有效性。

为实现进化优化，将烤漆门外观做为进化个体。结合市场调查，烤漆门外观属性共有门套线、门型和门色三个。其中，门套线的属性值有直角、工字型和门楼等三类共16种；门型属性值包括经典系列、面包系列、韩日拉伸系列、深拉伸系列、反凸系列和卡通系列等六类共1024种；门色属性值共有黄枫等32种烤漆色系。门套线属性值在[0,15]内取整数，用4位二进制编码表示，其中0000代表直角类型，0001为工字型类型，其余为门楼类型。门型的属性值在烤漆门三种属性中最多。首先，在[0,1023]内划分六个区间分别代表门型类型：[0,170]代表经典系列、[171-341]代表面包系列、[342-512]代表韩日拉伸系列、[513-683]代表深拉伸系列、[684-854]代表反凸系列、[855-1023]代表卡通系列，然后，在各区间内取整数值转换为10位二进制编码对应相应种类门型。门色属性值在[0,31]内取整数，用5位二进制编码表示，对应32种烤漆色系。个体染色体长度为19，搜索空间包含 $2 ^ { 4 } \times 2 ^ { 1 0 } \times 2 ^ { 5 } = 5 2 4 2 8 8$ 个候选解。图3表示了染色体编码过程，其中 $x _ { i 1 } , x _ { i 2 } , x _ { i 3 }$ 表示个体 $x _ { i } ( t )$ 的3个属性,$l _ { 1 } ^ { 1 } , l _ { 2 } ^ { 1 } , \cdots l _ { 4 } ^ { 1 } ; l _ { 1 } ^ { 2 } , l _ { 2 } ^ { 2 } , \cdots l _ { 1 0 } ^ { 2 } , l _ { 1 } ^ { 3 } , l _ { 2 } ^ { 3 } , \cdots l _ { 5 } ^ { 3 }$ 表示各属性的属性值。所示个体的属性值为（0,352,11)，其染色体为0000010110000001010，对应的烤漆门外观是“直角/LC-203（韩日拉伸系列）/泰柚”。烤漆门样本以.bmp 格式储存在根目录下的数据库中。

# 5.2系统操作界面及参数设置

本系统采用VisualBasic6.0编程实现。系统运行时首先初始化，进化代设置为0，然后，用户设定遗传参数。系统随机从素材库中读入烤漆门结构模型，利用OpenGL完成模型的贴图和显示，得到一个完整的烤漆门个体（样本)。重复该过程生成初始种群，种群规模 $N { = } 8$ 。个体下方的滑动条供用户采用精确数打分评价使用，打分范围为1-100。用户提交评价结果后，系统在后台按设计算法运算，每代进化结束后系统为用户推荐新的个体。重复这一过程至用户满意。算法采用3种进化终止条件：进化至最大进化代数T、系统收敛（相同个体占种群 $7 5 \%$ 及以上）、用户对优化结果满意。当任意终止条件满足时，系统结束进化。系统人-机交互界面如图4所示。

本系统的测试实验对象是理性单用户，选择4名在校大学生，并标记为用户1-4。为验证本文方法的有效性，以模糊适应值交互式遗传算法(Interactive Genetic Algorithm with IndividualsfuzzyFitness，IGA-IFF)和区间适应值交互式遗传算法(Interactive Genetic Algorithm with Individuals Interval Fitness,IGA-IIF）为比较对象[15]。分别基于上述三种算法开发相应测试系统，设置相同的遗传操作：规模为2的联赛选择、单点交叉和单点变异。交叉和变异概率 $p _ { c } = 0 . 6 , p _ { m } = 0 . 0 1$ ，最大进化代数 $\scriptstyle { \cal T } = 2 0$ 。

![](images/9172139c321e5fdbe9c23dc740f89b0627d1b88e333ea52497ebe43f94aec12b.jpg)  
图3染色体编码过程

![](images/c64f5a0d78be240493e71678bfbbfbd78b0c41142399b39639b9688adec06f97.jpg)  
图4人-机交互界面

# 5.3 实验结果与分析

算法性能比较测试分为2个项目进行：以烤漆门外观符合“典雅”标准的非固定解优化测试（项目1）和以图3所示个体（0.352，11）为优化目标的固定解优化测试（项目2)，验证所提方法在减轻用户疲劳、搜索效率、优化质量和实际应用等方面的有效性。

非固定解优化测试项目的目的是测试算法对个性偏好目标的搜索能力。要求4位用户根据“典雅”风格标准，采用本文算法在最大进化代数 $\scriptstyle { \cal T } = 2 0$ 内不限耗时各运行1次。该项目的测试指标包括：个体模糊适应值、适应值相对误差、用户满意度等。

首先，验证模糊适应值对优化效果的影响，这通过本文提出的适应值模糊灰模型能否顺利建模，以及种群的进化是否符合用户认知规律反映。为此，记录4名不同用户的模糊适应值变化情况。由于不同用户实验中进化结束的代数不同，因此，仅取前10代进化数据进行分析。实验结果如图5所示，图中横坐标为进化代数，纵坐标为模糊适应值参数均值。统计各用户优化结果的平均相对误差，结果如图6所示，图中横坐标为进化代数，纵坐标为根据式（20）计算的模糊适应值平均相对误差。

由图5(a),(b)(c)可知，4位用户模糊适应值的中心值和支集上限下限都逐渐增加，这表明，通过模糊灰模型得到的模糊适应值反映了用户偏好，进化方向符合认知规律。从图5(d)可知，4位用户模糊适应值支集宽度变化虽然有波动，但整体趋势仍逐渐减小，表明评价不确定性逐渐减弱。另外，从图5还可知，4位用户的适应值差异并不明显。这表明，对于优化目标符合“典雅”这一个性优化要求，本文算法获得的优化解对不同的用户具有高度的一致性，算法表现出良好的个性偏好目标搜索能力。由图6可知，4位用户的适应值平均相对误差随进化逐渐减小，表明适应值模糊灰模型预测精度逐渐提高，适应值可信性逐渐增大，优化质量不断提高。

然后，验证噪声强度对进化优化的影响。为此，记录实验过程中用户满意度的变化。结果如图7所示，图中横坐标表示进化代数，纵坐标表示个体满意度均值。由图7可知，用户满意度随进化逐渐增加，在进化初期普遍较低，从第6代开始，满意度值趋近平缓。结合图5(d)进行分析，支集宽度减小同时满意度增加，意味着适应值噪声强度逐渐降低，并且在进化末期4位用户的噪声强度逐渐相同。满意度的递增变化与用户的认知变化趋势是完全吻合的。上述实验结果与分析表明，本文提出的适应值模糊灰建模方法是完全可行的。

![](images/93b74b5c48106f4362bf80380c76fcc2887875f933f032f15856331c0899b33d.jpg)  
图5用户模糊适应值参数变化

![](images/87b30bdcd1110e04d6be6635338e1385c5f24b0df5d4d0772c7b99463b97d757.jpg)  
图6适应值平均相对误差

![](images/c641197f41b4108f838f26796fa8aa9da473e28652caf11950fe02a8ef012478.jpg)  
图7用户满意度

项目1结束一周后，进行固定解优化测试。固定解优化测试的目的是测试算法对共性偏好目标的搜索能力。该项目要求4名用户在最大进化代数内不限耗时，分别用本文算法和比较算法各运行10次，总计120人次进化优化。统计进化代数、评价耗时、搜索效率（搜索效率 $\ c =$ 评价的互异个体数/总评价个体数）等性能指标，箱形图如图8所示。此外，还记录一定时间内，用户找到满意解的实验次数与总的实验次数的比，实验结果如表1所示。然后统计三种算法在不同时间内找到互异个体数目的比例，如表2所示。最后，采用Mann-WhitneyU方法，对实验数据进行非参数检验。取显著性水平为0.05，渐进显著性水平如表3所示。

由图8和表1,2.3可知，本文方法与对比方法的渐进显著性水平均小于0.05，说明本文方法与对比方法存在显著差异，本文方法优于对比方法。具体表现为：

a）在进化代数方面，与对比方法相比，本文方法的进化代数最少，用户负担最小。原因在于本文通过用户满意度约束适应值噪声强度，最大限度抑制了噪声对适应值的影响，获得的模糊适应值更符合用户偏好，所以，算法收敛最快。

b）在用户评价耗时方面，与对比方法相比，本文方法需要的评价时间最短。原因在于本文算法的适应值评价仅按精确数赋值，而IGA-IFF需要进行模糊中点值和语气算子选择两步操作，IGA-IIF也需要评价区间适应值上限和下限两步操作，这不仅增加了用户工作量，评价耗时也相应增加。

c）在搜索效率方面，三种算法均在10分钟内完成进化，但本文方法的搜索效率显著高于对比算法。同时，从需要的进化代数和用户找到满意解需要的时间等指标上明显看出，本文方法找到用户满意解的速度也最快。原因在于，本文方法通过模糊灰模型预测得到的模糊适应值更符合用户偏好，算法搜索能力更强，搜索到的互异个体也最多。所以本文算法在相对最少的进化代数下，获得了最高的搜索效率。另外的原因则是本文算法的核心是NSGA-II，对比算法核心均为传统遗传算法（GA)，由于NSGA-II性能优于GA，所以本文算法性能也优于对比算法。

上述实验结果与分析表明，本文方法对个体只需评价精确数值即可获得模糊适应值，且本文方法能够以最少的进化代数和用户评价耗时找到最多的互异个体，从而在减轻用户疲劳的同时，提高了算法对共性偏好目标的搜索能力。

![](images/028d5c0c1baab07005fa3b52f691a1e286621ac79c90c2d6f96c8fa652b5d2ba.jpg)  
图8算法性能指标

表1用户找到满意解的实验次数与总实验次数的比 $( \% )$ ）  

<html><body><table><tr><td>算法</td><td>5分钟</td><td>8分钟</td><td>10分钟</td></tr><tr><td>本章方法</td><td>70</td><td>100</td><td>100</td></tr><tr><td>IGA-IFF</td><td>40</td><td>80</td><td>100</td></tr><tr><td>IGA-IIF</td><td>30</td><td>70</td><td>100</td></tr></table></body></html>

表2算法不同时间内找到互异个体数目比例 $( \% )$   

<html><body><table><tr><td>算法</td><td>5分钟</td><td>8分钟</td><td>10分钟</td></tr><tr><td>本文算法</td><td>30</td><td>60</td><td>80</td></tr><tr><td>IGA-IFF</td><td>20</td><td>50</td><td>70</td></tr><tr><td>IGA-IIF</td><td>15</td><td>40</td><td>50</td></tr></table></body></html>

表3独立样本的Mann-WhitneyU测试结果  

<html><body><table><tr><td>算法配对</td><td>进化代数</td><td>用户评价耗时</td><td>搜索效率</td></tr><tr><td>本文算法 vs.IGA-IFF</td><td>0.028</td><td>0.034</td><td>0.022</td></tr><tr><td>本文算法 vs.IGA-IIF</td><td>0.013</td><td>0.015</td><td>0.007</td></tr></table></body></html>

# 6 结束语

本文提出基于适应值模糊灰模型的交互式进化优化方法。该方法首先分析了用户评价的不确定性过程，建立了适应值噪声强度与用户满意度的映射关系，基于用户满意度约束噪声强度。然后，通过模糊灰模型FGM（1,1）预测个体模糊适应值，达到降低适应值噪声提高算法优化质量的目的。最后，以NSGA-II为引擎实现算法。

实验结果表明，通过噪声强度计算相关参数，并预测模糊适应值，能够体现决策者偏好的同时，大大降低了噪声对适应值的影响，是解决复杂隐式指标优化问题的有效途径。本文以烤漆门外观选型为对象开发系统，但基于算法的普适性，对于其他复杂隐式指标优化问题，本文方法仍然适用。

需要指出的是，交互式进化计算个体适应值也可以采用其他形式表示，如偏好多元组或偏好集合，基于此得到的适应值预测模型，与本文有很大区别；此外，设计合适的进化策略，也将有利于提高Pareto优化解的性能。这是需要进一步研究的问题。

# 参考文献：

[1]Makiwan D, Yoshida K,Koppen M.Interactive evolutionary computation of color palette design enhanced by impression words [C]// Proc of International Conference on Platform Technology and Service,Busan,2017: 1-6.   
[2]Liang Ruiyu,Guo Ruxue,Xi Ji,et al.Self-fitting algorithm for digital hearing aid based on interactive evolutionary computation and expert system [J].Applied Sciences,2017,7 (22): 1-19.   
[3]Fukumoto M.A proposal for continuous evaluation-based interactive evolutionary computation [C]// Proc of the 48th ISCIE International Symposium on Stochastic Systems Theory and Its Applications.2016:211- 215.   
[4]Manfre A,Augello A,Pilato G,et al. Exploiting interactive genetic algorithms for creative humanoid dancing [J].Biologically Inspired Cognitive Architectures,2016,17: 12-21.   
[5]窦润亮，郭均鹏，田祥龙，等．面向客户个性化需求的交互式遗传算法 [J]．管理科学学报,2016,19(1):24-34.   
[6]孙晓燕，朱利霞，陈杨．基于可能性条件偏好网络的交互式遗传算法及 其应用[J]．郑州大学学报：工学版,2017,38(6):1-5.   
[7]Ishibuchi H,Sudo T,Nojima Y. Interactive evolutionary computation with minimum itness evaluation requirement and oline algorithm design [J]. SpringerPlus,2016,5,192:1-19.   
[8]潘涛涛，朱珂，吴毅涛．基于满意区间的协同过滤推荐算法[J].计算 机应用研究,2017,34(8):2282-2286.   
[9]毛宜钰，刘建勋，胡蓉，等．基于Logistic 函数和用户聚类的协同过滤 算法[J].浙江大学学报：工学版,2017,51(6):1252-1258.   
[10]王占，林岩．基于信任与用户兴趣变化的协同过滤方法研究[J].情报 学报,2017,36(2):197-205.   
[11]郭广颂，陈良骥.基于熵极大准则的非用户赋适应值交互式遗传算法 [J].电子学报,2017,12(12):2997-3004.   
[12]孙晓燕，陆宜娜，巩敦卫，等.基于CP-nets 的偏好感知交互式遗传算 法及其个性化搜索 [J]．控制与决策,2015,30(7):1153-1161.   
[13]巩敦卫，陈健．基于精英集选择进化个体的交互式遗传算法[J].电子 学报，2014,42(8):1538-1544.   
[14] Chao Qian,Yang Yu,Ke Tang,et al.On the Effectiveness of Sampling for Evolutionary Optimization in Noisy Environments [J]，Evolutionary Computation, 2017.   
[15]孙晓燕，陈姗姗，巩敦卫，等．基于区间适应值交互式遗传算法的加权 多输出高斯过程代理模型[J]，自动化学报,2014,40(2):172-184.   
[16]吴利丰，高晓辉，付斌，等．灰色GM(1,1）模型研究综述[J].数学的 实践与认识,2017,47(15):227-233.   
[17] Tsaur Rueychyn.Forecasting analysis by fuzzy grey model GM(1,1) [J] Journal of the Chinese Institute of Industrial Engineers,2006,23 (5): 415- 422.   
[18]刘思峰，党耀国，方志耕，等．灰色系统理论及其应用[M].北京：科 学出版社,2010:146-153.   
[19]DebK,PratapA,AgarwalS,etal.A fastandelitist multiobjective genetic algorthm: NSGA-II [J]. IEEE Trans on Evolutionary Computation, 2002, 2 (6): 182-197.   
[20]郭广颂，陈良骥，文振华，等．基于进化个体模糊适应值估计的交互式 遗传算法[J].控制与决策 (已录用).