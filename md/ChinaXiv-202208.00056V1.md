# 多种风电场风速预报订正方法的适用性研究与集成应用

徐丽娜¹，申彦波23，冯震，叶虎(1.内蒙古自治区气象服务中心,内蒙古 呼和浩特010051；2.中国气象局公共气象服务中心,北京100081;3.中国气象局风能太阳能资源中心，北京100081)

摘要：以内蒙古中部某风电场为实验风电场,采用随机森林(Randomforest,RF)方法、相似误差订正（Analogue correction of errors,ACE）方法以及概率密度匹配方法（Probability density functionmatching method,PDF)分别对风电场风速预报进行订正及适用性研究。结果表明:3种方法在各季均对中尺度天气预报模式（Weather researchand forecasting model,WRF)风速预报具有不同程度的订正效果，RF方法可以有效改善WRF误差较大的问题，但兼具误差过分放大情况，ACE方法和PDF虽然对较大误差的改善能力不及RF方法，但是能够较好地控制误差过分放大问题。此外，3种方法针对小于 $5 \mathrm { m \cdot s ^ { - 1 } }$ 的小风速段，订正效果不理想，随着风速的增加，订正能力逐渐增强。参照预报模型各自的优势，尝试开展多种预报模型的分风速等级集成应用，可以对不同风速等级下的WRF预报起到较好的改善作用。

关键词：风速预报；随机森林；相似误差订正；概率密度匹配方法；集成预报

# 文章编号：

我国地域辽阔，风能资源丰富，风电装机容量自2010年起跃居世界第一，风电并网消纳难题随之凸显[1]。未来,中国可再生能源将进入大规模、高比例、市场化阶段，进一步引领能源生产和消费革命的主流方向，发挥能源清洁低碳转型的主导作用，为实现“碳达峰、碳中和”目标提供主力支撑，这就对风电并网消纳能力提出了更高的要求[2-4]

中尺度数值预报模式与统计订正方法相结合的短期风速预测作为减轻风电并网压力，提升风电场运行效率的有效手段之一，长期以来一直是国内外专家学者致力研究的课题。其中，统计订正方法也由早期的传统统计订正方法5-7逐渐发展到基于人工智能的机器学习方法[8-12]。张铁军等[13]基于历史资料提出一种可快速更新的风速预报误差订正方法，即利用趋势、方差和均值对风电场风速预报进行订正，取得了较好的订正效果。邓华等[4基于主成分分析（Principal component analysis,PCA）与径向基(Radialbasis function,RBF)神经网络相结合的算法对模式预报风速进行订正，相对均方根误差降低 $20 \% { \sim } 3 0 \%$ ,相对平均绝对误差降低 $1 5 \% { \sim } 2 0 \%$ ，有效减小了中尺度天气预报模式（Weatherresearchandforecastingmodel,WRF)预报误差，改善了短期风速预报精度。张颖超等[15分别采用极限学习机（Extreme learningmachine,ELM）、反向传播（Backpropagation,BP)神经网络、支持向量机(Support vec-tormachine,SVM)算法进行模式预报风速订正得出，ELM算法将预报风速的相对均方根误差和相对平均绝对误差降低了 $20 \% { \sim } 3 0 \%$ ,明显优于BP神经网络和SVM算法。

然而，如何评价模型的订正效果，对于短期风速预测的改进也至关重要。目前衡量模型订正效果的方法普遍采用研究周期内订正风速、模式预报风速与实况风速之间相关系数、误差等的对比，这种评估方式往往忽略了多数统计订正方法对低、高风速段订正能力有限的问题。近地层风场易受复杂下垫面和复杂湍流过程影响，具有显著的波动性和不确定性特征，当风电机组在低风速段 $\left( 2 { \sim } 4 \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 } \right)$ 或高风速段 $\left( \geqslant 2 5 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 } \right)$ 运行时，受阵风的影响，风电机组可能会频繁启停，增加风电机组损耗的同时,也加大了风电场的运行成本[16]。大规模风电机组启停，可能会由于超出电网调节能力而影响电网的有功功率供需平衡和频率稳定。因此，对于风电机组切入、切出风速段的改善能力是衡量订正模型优劣的重要指标。

本文采用随机森林(Randomforest,RF)方法、相似误差订正（Analogue correctionof errors,ACE)方法以及概率密度匹配方法（Probabilitydensity functionmatchingmethod,PDF），分别建立风电场风速预报订正模型，在进行传统检验的同时，划分风电零发、风电低发、风电高发、风电满发及风电切出等风速等级,进行风速分级误差及准确率评判,旨在提出一种更有助于指导风电企业生产运行的检验评估方法；此外，基于不同订正方法的适用性研究，优选合理的订正模型权重，尝试开展多种模型的集成应用，为更有效地改善风电场风速预报性能提供了一种新思路。

# 1资料与方法

# 1.1资料来源

选取内蒙古中部中节能聚隆风电场为实验风电场。该风电场位于内蒙古兴和县境内，兴和县平均海拔约 $1 5 0 0 \mathrm { ~ m ~ }$ ,以西北气流为主导，常年风速较大，平均风速 $> 1 7 . 0 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 的大风日数[较多，年平均大风日数 $4 5 \mathrm { ~ d } , 2 0 2 0$ 年该风电场测风塔 $7 0 \mathrm { m }$ 高度平均风速为 $9 . 0 \ \mathrm { m \cdot s ^ { - 1 } }$ ,风资源丰富。实验风电场测风塔位置及地形分布见图1。内蒙古属典型的中温带季风气候，具有降水量少而不匀、寒暑变化剧烈等特点。风速季节变化特征明显，表现为春季最大，冬季次之，夏季最小。刘鸿波等"基于台站观测资料和欧洲中期天气预报中心(ECMWF)最高时空分辨率的第五代大气再分析资料(ERA5)，在1979—2018年中国区域 $1 0 \mathrm { m } \cdot 1 0 0 \mathrm { m }$ 高度风速的气候特征及其变化趋势的研究中指出，中国近地层风速呈现出显著的区域性特征，风速大值区主要分布在内蒙古、东北地区西部、新疆北部以及青藏高原西部地区，且上述区域的风速季节差异较大。

实况数据采用2020年1月1日—2020年12月

31日实验风电场测风塔 $7 0 \mathrm { m }$ 高度逐时测风资料，测风塔位于 $1 1 3 ^ { \circ } 1 6 ^ { \prime } 1 2 ^ { \prime \prime } \mathrm { E } , 4 1 ^ { \circ } 0 7 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N } ^ { \prime }$ (图1)。预报数据采用基于WRF的风能专业数值预报模式结合后处理输出的 $7 0 \mathrm { m }$ 高度风速格点预报产品，预报时效为24h,时间分辨率为 $1 \mathrm { h }$ 。该模式主要用于内蒙古风电气象服务，模式中心坐标为 $1 1 2 ^ { \circ } 0 2 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E } , 4 3 ^ { \circ } 4 9 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N }$ 预报区域设置为 $2 7 \mathrm { k m }$ （区域1） $\cdot 9 \mathrm { k m }$ (区域2)的双层嵌套， $9 ~ \mathrm { k m }$ 模式范围为 $9 6 ^ { \circ } 2 7 ^ { \prime } 0 0 ^ { \prime \prime } { \sim } 1 2 7 ^ { \circ } 3 1 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { E }$ $3 7 ^ { \circ } 1 2 ^ { \prime } 0 0 ^ { \prime \prime } { \sim } 5 4 ^ { \circ } 2 8 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N } ,$ ，以 $0 . 5 { \times } 0 . 5$ NCEPGFS资料为初始场和侧边界条件，边界层采用YSU方案，微物理过程方案为WSM6类冰雹方案，长波辐射为RRTM方案，短波辐射方案为Goddard方案，陆面过程采用Noah陆面过程方案，积云参数化方案采用浅对流Kain-Fritsch(newEta)方案，垂直方向为55层，采用地形追随坐标，进行近地不同层次气象要素输出。模式近地sigma层取值与距离测风塔最近预报格点 $( 1 1 3 ^ { \circ } 1 8 ^ { \prime } 3 6 ^ { \prime \prime } \mathrm { E } , 4 1 ^ { \circ } 0 8 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { N } )$ 处的模式输出高度见表1。

选取与测风塔实况数据时间序列一致的测风塔周边4个格点的预报数据，预报格点经纬度依次为：$1 1 3 ^ { \circ } 1 2 ^ { \prime } 0 0 ^ { \prime \prime } \mathrm { E } . 4 1 ^ { \circ } 0 3 ^ { \prime } 0 0 ^ { \prime \prime } \mathrm { N } , 1 1 3 ^ { \circ } 1 8 ^ { \prime } 3 6 ^ { \prime \prime } \mathrm { E } . 4 1 ^ { \circ } 0 3 ^ { \prime } 0 0$ "N,$1 1 3 ^ { \circ } 1 1 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E } . 4 1 ^ { \circ } 0 7 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N } , 1 1 3 ^ { \circ } 1 8 ^ { \prime } 3 6 ^ { \prime \prime } \mathrm { E } . 4 1 ^ { \circ } 0 8 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { N }$ P水平方向采用双线性插值方法插值到测风塔位置，垂直方向采用线性插值方法插值到 $7 0 \mathrm { m }$ 高度。

![](images/4240687b438c2f459745270b63db5666bf960c7dfffde4b2068321c892cedccd.jpg)  
图1实验风电场测风塔位置及地形分布  
Fig.1Wind tower's location and topography distribution of the experimental wind farm

# 1.2 研究方法

考虑研究区风速季节特征明显，因此本文采取按季建模方式,具体为：采取以月份划分季节方式[19],

# 干旱区地理

# 表1模式近地sigma层取值与距离测风塔最近预报格点对应模式输出高度

Tab.1 Value of sigma layer and the model output height of the nearest forecast grid from the wind tower   

<html><body><table><tr><td>近地sigma层取值</td><td>模式输出高度/m</td></tr><tr><td>1.0000</td><td>0.00</td></tr><tr><td>0.9985</td><td>11.32</td></tr><tr><td>0.9970</td><td>22.65</td></tr><tr><td>0.9950</td><td>37.78</td></tr><tr><td>0.9935</td><td>49.14</td></tr><tr><td>0.9928</td><td>54.44</td></tr><tr><td>0.9920</td><td>60.51</td></tr><tr><td>0.9890</td><td>82.29</td></tr><tr><td>0.9850</td><td>113.74</td></tr><tr><td>0.9780</td><td>167.25</td></tr></table></body></html>

即春季3—5月，夏季6—8月，秋季9—11月，冬季12一次年2月，分别建立基于RF方法、ACE方法、PDF的风速预报分季订正模型，各季中前2个月为模型构建期，最后1个月为模型验证期。

1.2.1 随机森林(RF)方法 $\mathrm { R F } ^ { [ 2 0 ] }$ 是通过集成学习的思想将多棵决策树集成的一种算法。RF方法[21]中定义风速预测训练集合 $X _ { i } \longrightarrow Y _ { i }$ 。其中， $X _ { i }$ 为模型构建期第 $i$ 时刻的影响因子 $\left\{ { { I } _ { i 1 } } , { { I } _ { i 2 } } , \cdots , { { I } _ { i n } } \right\}$ 构建的特征向量， $Y _ { _ i }$ 为模型构建期第 $i$ 时刻的实测风速。通过自助法(Bootstrap)重采样技术，完成分类模型构建，建立单棵回归决策树。在单棵决策树构建的基础上，构建整个RF，生成的RF是多元非线性回归分析模型，RF预测值是所有决策树预测值的平均值，其优点在于能够处理具有高维特征的输入样本，可以有效地运行在大数据集上，且具有较好的准确率。

本文从WRF输出要素中筛选出 $7 0 \mathrm { ~ m ~ }$ 风速、70$\mathbf { \rho } _ { \mathrm { m } }$ 气温、 $. 7 0 \mathrm { m }$ 相对湿度、地面气压构建特征向量，建立RF订正模型，实现 $7 0 \mathrm { m }$ 风速订正预报输出。

1.2.2 相似误差订正(ACE)方法ACE方法的主要思想是将根据时间顺序排列的预报变换到相似空间上，以求寻找到与当前预报最相似（用具体的距离来定义)的历史预报，即通过定义合适的距离来度量历史预报和当前预报的相似程度，以期刻画出天气过程的相似度。在相似空间中，根据与当前预报的相似度对历史预报赋予相应权重，再对相似历史预报的观测值进行加权平均，得到订正预报。ACE方法克服了一般基于时间顺序的误差订正方法的不足，可以处理由于天气系统剧烈转变引起的预报误差的快速变化。

选取WRF输出 $7 0 \mathrm { m }$ 风速和地面气压为订正因子，建立 $7 0 \mathrm { m }$ 风速预报ACE模型。通过敏感性试验确定模型参数：时间窗2为 $2 \mathrm { h }$ ，风速权重为1.0，气压权重为0.1，相似预报的样本量( ${ \mathbf { \nabla } } N _ { a }$ )为 $2 5$

1.2.3概率密度匹配方法（PDF）PDF[23-25]的主要思想是通过调整预报值，使其和地面观测的概率密度分布一致，来达到订正预报系统误差的目的。对于测风塔观测风速与WRF预报风速而言，当样本量足够大时，可以分别得到两者稳定的累积概率密度分布。累积概率密度为 $P$ 时，对应的测风塔观测风速与WRF预报风速分别记为 $\mathrm { O B S } ( P ) \ \mathrm { ( m \cdot s ^ { - 1 } ) }$ 与$\mathrm { W R F } ( P ) \left( \mathbf { m } \cdot \mathbf { s } ^ { - 1 } \right)$ ,此时两者具有稳定的差值 $\Delta r ( P )$ $\left( \mathbf { m } { \cdot } \mathbf { s } ^ { - 1 } \right)$ ，计算公式如下：

$$
\Delta r ( P ) = \mathrm { W R F } ( P ) - \mathrm { O B S } ( P )
$$

通过计算各时次测风塔观测风速的累积概率密度以及该概率密度所对应的WRF预报风速和测风塔观测风速，便可求得该时次的差值 $\Delta r \ : ( \mathrm { m } ^ { . } \mathrm { s } ^ { - 1 } )$ ，以此对各时次WRF预报风速进行订正，得到订正值WRF. $\left( \mathbf { m } { \cdot } \mathbf { s } ^ { - 1 } \right)$ ·

$$
\mathrm { W R F _ { \mathrm { c } } } = \mathrm { W R F } - \Delta r
$$

1.2.4检验方法文中采用相关系数 $\textbf { ( } r \textbf { ) }$ 、平均绝对误差 $\left( \mathbf { \sigma } _ { e _ { \mathrm { a } } } \right)$ 、准确率 $( \ f _ { \mathrm { a } } ) ^ { [ 2 6 ] }$ 及平均绝对误差提升率$( C _ { \mathrm { e } } )$ 对订正结果进行检验，计算公式如下：

$$
r = \frac { \displaystyle \sum _ { i = 1 } ^ { N } ( x _ { \mathrm { f } } - \overline { { x _ { \mathrm { f } } } } ) ( x _ { \mathrm { o } } - \overline { { x _ { \mathrm { o } } } } ) } { \displaystyle \sqrt { \sum _ { i = 1 } ^ { N } ( x _ { \mathrm { f } } - \overline { { x _ { \mathrm { f } } } } ) ^ { 2 } } \sqrt { \sum _ { i = 1 } ^ { N } ( x _ { \mathrm { o } } - \overline { { x _ { \mathrm { o } } } } ) ^ { 2 } } }
$$

$$
e _ { \mathrm { a } } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \Bigl | \left( x _ { \mathrm { f } } - x _ { \mathrm { o } } \right) \Bigr | _ { i }
$$

$$
f _ { \mathrm { a } } = \frac { N _ { \mathrm { A } } } { N _ { \mathrm { A } } + N _ { \mathrm { B } } + N _ { \mathrm { C } } }
$$

$$
C _ { \mathrm { e } } = - { \frac { \left( { e _ { \mathrm { a } } } ^ { \prime } - e _ { \mathrm { a } } \right) } { e _ { \mathrm { a } } } } \times 1 0 0 \%
$$

式中： $x _ { \mathrm { f } } \ 、 x _ { \mathrm { o } }$ 分别为预报风速和观测风速 $\left( \mathbf { m } \cdot \mathbf { s } ^ { - 1 } \right)$ $\overline { { x _ { \mathrm { f } } } } \setminus \overline { { x _ { \mathrm { o } } } }$ 分别为预报风速和观测风速的平均值 $\left( \mathbf { m } { \cdot } \mathbf { s } ^ { - 1 } \right)$ $N$ 为统计时段内样本总量； $i$ 为统计时段内样本序号； $N _ { \mathrm { ~ A ~ } } \setminus N _ { \mathrm { ~ B ~ } } \setminus N _ { \mathrm { c } }$ 分别为评价时段内某一风速段的正确预报次数、空报次数和漏报次数; ${ e _ { \mathrm { a } } } ^ { \prime }$ 为订正后预报的平均绝对误差 $\left( \mathbf { m } { \cdot } \mathbf { s } ^ { - 1 } \right)$ $e _ { \mathrm { a } }$ 为原始预报的平均绝对误差 $\left( \mathbf { m } { \cdot } \mathbf { s } ^ { - 1 } \right)$ O

# 2结果与分析

# 2.1模型适用性评估

2.1.1全风速误差检验采取分季节检验方式，进行全风速误差检验。研究期内，即2020年1月1日—2020年12月31日，样本总数为8254,有效样本率为 $9 4 . 2 \%$ 。模型验证期各季的样本量为春季624、夏季720、秋季720、冬季744，各季有效样本率为春季$8 4 \%$ 、夏季 $9 7 \%$ 、秋季 $9 7 \%$ 、冬季 $100 \%$ O

从模型验证期的检验结果来看，3种方法在各季对订正前WRF风速预报具有不同程度的订正效果。以秋季的订正结果(图2)为例，可见RF方法可以有效改善WRF误差较大的问题，但同时也会带来将误差过分放大的情况，这可能是RF方法进行回归时不能够做出超越训练集数据范围的预测，导致对某些特定噪声的数据进行建模时出现过度拟合。而ACE方法和PDF虽然对较大误差的改善不及RF方法，但其较好地控制了误差过分放大的问题,尤其是PDF,模型的负回报几率明显小于其他两种方法。各季订正前后的相关系数(表2)均通过了0.01的置信度检验，RF方法订正后相关系数较订正前略有下降，这可能是由于RF在解决回归问题时，不能给出一个连续的输出，导致了相关系数的下降，而ACE方法和PDF订正后相关系数较订正前有所提升。ACE方法订正后的平均绝对误差(表2)小于RF方法和PDF,而春、秋两季PDF的订正效果好于RF方法，夏、冬两季RF方法的订正效果好于PDF。这可能与实验风电场模型构建期实测风速的概率密度分布特征有关。春、秋两季，实验风电场实测风速分布范围更广，模型模拟出的累计概率密度分布与实际较为吻合，夏、冬两季，实验风电场实测风速分布范围相对集中，模型模拟出的累计概率密度分布与实际存在一定偏差，从而导致春、秋两季的订正效果好于夏、冬两季。全年来看，RF方法的平均绝对误差提升率为 $6 . 7 \% \sim 3 6 . 7 \%$ ，ACE方法的平均绝对误差提升率为 $1 1 . 1 \% { \sim } 3 4 . 7 \%$ ,PDF的平均绝对误差提升率为 $3 . 7 \% { \sim } 2 0 . 6 \%$ ,在预报误差较小的夏季,3种方法的平均绝对误差提升率均较低，在预报误差较大的冬季，3种方法对平均绝对误差也均有较大程度的提升。

2.1.2分风速区间误差检验由于各季模型验证期强风样本数量有限，因此进行风速区间误差检验时采用全季检验方式，即将各季模型验证期的样本合并，按照实测风速区间进行分级误差检验。首先根据典型风电机组的功率曲线，按照风机出力情况将测风塔实测风速划分为[0,3）、[3,8）、[8,12）、[12,25）、 $[ 2 5 , + \infty ) 5$ 个等级，分别对应风电零发、风电低发、风电高发、风电满发及风电切出。为了更为详细地掌握不同方法的误差订正能力，同时考虑到$\geqslant 2 5 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 的样本数量太少，难以获得具有统计意义的分析结果，因此,进一步将上述风速等级细化调整为[0,3）、[3,5）、[5,8）、[8,12）、[12,16)、[16,20） $[ 2 0 , + \infty ) 7$ 个风速区间。全年模型验证期各风速区间的样本数量见表3。

图3为不同方法对不同区间风速的订正效果对比。可见,实测风速在 $5 \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 以下时,WRF的预报误差较小（小于 $2 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ ),3种订正方法均具有负回报；当风速 $\mathrm { > } 5 \mathrm { ~ m \cdot s ^ { - 1 } }$ 时，随着风速的增加，WRF预报误差随之增大，此时，3种订正方法开始产生正回报，且随风速的增加，RF方法的平均绝对误差提升率较为稳定，ACE方法的平均绝对误差提升率略有下降，这可能是高风速区间的历史样本数量有限造成的。针对ACE方法而言，只有历史上相似状态提供的信息才能有效订正当前的预报误差，不相似的状态可能会提供错误的订正信息[27],而RF方法在训练过程中则具有较强的抗干扰能力，对于不平衡的数据集来说，可以平衡数据集的误差，从而可以较好地维持其准确度。PDF的平均绝对误差提升率则有所上升，这与高风速模式预报表现为稳定的负偏差有关。针对不同风速区间，3种订正方法的订正能力不尽相同，当风速 $< 5 ~ \mathrm { m \cdot s ^ { - 1 } }$ 时,PDF明显优于RF、ACE方法，当 $5 \ \mathrm { m \cdot s ^ { - 1 } } \mathrm { \leqslant }$ 风速 $< 1 6 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 时，RF、ACE方法优于PDF，当风速 $\geqslant 1 6 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 时，ACE方法的订正能力开始下降，PDF的订正能力有所提升。从实测风速与WRF预报风速的概率密度分布（图4)上可以看到，实测风速与WRF预报风速均具有明显的非正态分布特征，WRF可预报风速在 $0 { \sim } 2 0 \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 之间，对低风速区间风速预报概率偏低，高风速区间风速预报能力明显不足。由于PDF适用于误差大小对数据本身的数值范围具有较强依懒性的产品订正[24]，而如图4所示，研究期内WRF预报普遍存在小风天气预报偏大，大风天气预报偏小的特点，当风速 $< 5 ~ \mathrm { m \cdot s ^ { - 1 } }$ 与风速 $\geqslant 1 6 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 时,研究期内WRF的系统性偏差特征总体较为一致，即当风速<

干辛区地理

![](images/d296d0e29e0f3f2f7ae3dc384ccdb2a1f54e99e2b6f60020a61fbb9fbef06b19.jpg)  
注：RF为随机森林;ACE为相似误差订正;PDF为概率密度匹配方法。下同。  
图2秋季模型验证期风速预报的订正结果  
Fig.2 Correction results of wind speed forecast during model validation period in autumn

Tab.2 Average absolute error and average absolute error promotion rate after correction   

<html><body><table><tr><td rowspan="3">季节</td><td colspan="4">相关系数</td><td colspan="4">平均绝对误差/m·s-1</td><td rowspan="2" colspan="3">平均绝对误差提升率/%</td></tr><tr><td rowspan="2">订正前</td><td colspan="3">订正后</td><td rowspan="2">订正前</td><td colspan="3">订正后</td></tr><tr><td>RF</td><td>ACE</td><td>PDF</td><td>RF</td><td>ACE</td><td>PDF</td><td></td><td>ACE</td></tr><tr><td>春季</td><td>0.72</td><td>0.69</td><td>0.75</td><td>0.72</td><td>3.0</td><td>2.8</td><td>2.5</td><td>2.7</td><td>RF 6.7</td><td>16.7</td><td>10.0</td></tr><tr><td>夏季</td><td>0.43</td><td>0.40</td><td>0.40</td><td>0.43</td><td>2.7</td><td>2.5</td><td>2.4</td><td>2.6</td><td>7.4</td><td>11.1</td><td>3.7</td></tr><tr><td>秋季</td><td>0.75</td><td>0.68</td><td>0.76</td><td>0.74</td><td>3.4</td><td>2.8</td><td>2.6</td><td>2.7</td><td>17.6</td><td>23.5</td><td>20.6</td></tr><tr><td>冬季</td><td>0.65</td><td>0.64</td><td>0.65</td><td>0.66</td><td>4.9</td><td>3.1</td><td>3.2</td><td>3.9</td><td>36.7</td><td>34.7</td><td>20.4</td></tr></table></body></html>

注：RF为随机森林；ACE为相似误差订正;PDF为概率密度匹配方法。下同。

# 表3全年模型验证期各风速区间的样本数量

表2订正后的平均绝对误差及平均绝对误差提升率  
Tab.3Sample numbers in each wind speed domain during the model validation periods of the whole year   

<html><body><table><tr><td>风速区间/m·s-1</td><td>样本数量</td></tr><tr><td>[0,3)</td><td>206</td></tr><tr><td>[3,5)</td><td>317</td></tr><tr><td>[5,8)</td><td>748</td></tr><tr><td>[8,12)</td><td>888</td></tr><tr><td>[12,16)</td><td>392</td></tr><tr><td>[16,20)</td><td>187</td></tr><tr><td>[20,+∞)</td><td>70</td></tr></table></body></html>

$5 \mathrm { m \cdot s ^ { - 1 } }$ 时，尤其是[0,3)风速区间下，WRF存在明显的正系统性偏差特征，平均为 $1 . 5 \ \mathrm { m \cdot s ^ { - 1 } }$ ；当风速 $\geqslant 1 6$ $\mathbf { m \cdot s } ^ { - 1 }$ 时，WRF存在明显的负系统性偏差特征，平均为 $- 8 . 7 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 。因此PDF在[0,5）、 $[ 1 6 , + \infty )$ 风速区间下相对于RF、ACE方法表现出较强的订正能力，而当 $5 \mathrm { m \cdot s ^ { - 1 } } \leqslant$ 风速 ${ < } 1 6 \mathrm { \ m } { \cdot } \mathrm { s } ^ { - 1 }$ 时，WRF的正负偏差不确定，导致PDF的订正能力有限。

2.1.3分风速区间准确率检验分风速区间准确率检验同样采取全季检验方式。从不同风速区间预报准确率(图5)来看，当风速 $< 5 ~ \mathrm { m \cdot s ^ { - 1 } }$ 时，3种订正方法的准确率均不及原始WRF预报，当风速 $\geqslant 5 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 时，3种订正方法的准确率均较原始WRF预报有不同程度的提升，尤其当风速 $\geqslant 8 \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ ,订正后风速预报的准确率得到明显改善，当风速 $\geqslant 2 0 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 时，PDF的准确率最佳。

# 2.2多模型集成应用

2.2.1分季节集成集合预报和集成预报是天气预报技术的发展方向，集成预报可以通过一种数学模型将多种相互独立的单模型预报结果或参数进行整合分析，最终得到最理想的预报结果[28]。常用的集成预报方法有权重集成、回归集成、概率集成及判别集成等[29]

参照各季的平均误差提升率对3种方法进行分季节加权集成,集成预报(Integrating forecast,IF)的

![](images/8af869058c1493d95c05bd36a10e7ecf7744bfdb6693ff4b616ffc8abdd22680.jpg)  
注：WRF为中尺度天气预报模式。下同。图3不同风速区间的订正结果对比  
Fig.3Comparison of correction results in different wind speed domains

# 干旱区地理

![](images/125d2e7f7ce47d69b03751bdf4bd83232920898288f5658f06339a4eced5a7f7.jpg)  
图4实测风速与WRF预报风速的概率密度分布 Fig.4Probability density distribution of measured wind speed and wind speed forecast ofWRF

相关系数及平均绝对误差均略高于或持平于最优成员(表4)。可见，分季节对3种订正方法进行加权集成可以发挥集成成员各自的优势，从整体上改善预报性能，但是从集成前后的风速时序图(图6)上可以看到，分季节集成后并不能有效改善WRF预报在[0,3)低风速较实况偏大的情况

2.2.2分风速区间集成考虑到WRF预报与3种订正模型在不同风速区间下各自的优势，利用全年验证期样本，在实测风速等级判别的前提下，将原始WRF预报、RF订正预报、ACE订正预报和PDF订正预报作为4个成员进行集成，不同风速区间下各成员权重及检验结果见表5。

集成后按季进行检验：各季相关系数依次为$0 . 8 0 \ 、 0 . 6 0 、 0 . 8 1 、 0 . 7 4$ ，平均绝对误差依次为 $2 . 2 \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 、$2 . 1 \mathrm { m ^ { * } s ^ { - 1 } } , 2 . 3 \mathrm { m ^ { * } s ^ { - 1 } } , 3 . 0 \mathrm { m ^ { * } s ^ { - 1 } }$ ,优于分季节的集成方法。图7为分风速区间集成后不同区间预报风速的平均绝对误差和准确率与WRF预报之间的对比，可见，考虑风速区间的集成方法对不同风速区间下的WRF预报均具有较好的改善作用。值得指出的是，在[0,5)风速区间下，集成后空报次数由649次降至261次，由于空报次数的减小，使得分风速区间集成后的预报准确率得以有效提升，从而优于分季节集成方式。

# 3结论

（1）RF、ACE方法以及PDF对WRF风速预报均具有不同程度的订正效果，RF方法在有效改善WRF误差较大问题的同时会带来将误差过分放大的情况，ACE方法和PDF虽然能够较好地控制误差

![](images/3cc1a6d208827d2e2da9475242a93dd52096185db7018e904ed81b8c7e9f0826.jpg)  
图5不同风速区间预报准确率对比  
Fig.5Comparison of the forecast accuracy in different wind speed domains

表4分季节集成成员权重与集成后的相关系数、平均绝对误差  
Tab.4Weight of seasonal integrated member and the results after integratior   

<html><body><table><tr><td rowspan="2">季节</td><td colspan="3">集成权重</td><td colspan="2">相关系数</td><td colspan="2">平均绝对误差/m·s-1</td></tr><tr><td>RF</td><td>ACE</td><td>PDF</td><td>集成前最优</td><td>集成后</td><td>集成前最优</td><td>集成后</td></tr><tr><td>春季</td><td>0.30</td><td>0.40</td><td>0.30</td><td>0.75</td><td>0.76</td><td>2.5</td><td>2.4</td></tr><tr><td>夏季</td><td>0.30</td><td>0.40</td><td>0.30</td><td>0.43</td><td>0.46</td><td>2.4</td><td>2.3</td></tr><tr><td>秋季</td><td>0.33</td><td>0.34</td><td>0.33</td><td>0.75</td><td>0.76</td><td>2.6</td><td>2.5</td></tr><tr><td>冬季</td><td>0.40</td><td>0.40</td><td>0.20</td><td>0.66</td><td>0.66</td><td>3.1</td><td>3.1</td></tr></table></body></html>

![](images/3fe044411b14fdb5031327431918c8b8c9c47b30b9c5920368dba9a1e4d439ac.jpg)  
徐丽娜等：多种风电场风速预报订正方法的适用性研究与集成应用  
图6分季节集成前后风速时序变化

# 表5分风速区间集成成员权重与集成后的相关系数、平均绝对误差

Tab.5 Weight of wind speed domain integrated member and the resultsafter integration   

<html><body><table><tr><td rowspan="2">风速区间/m·s-1</td><td colspan="4">集成权重</td></tr><tr><td>WRF</td><td>RF</td><td>ACE</td><td>PDF</td></tr><tr><td>[0,5)</td><td>1.0</td><td>0.0</td><td>0.0</td><td>0.0</td></tr><tr><td>[5,16)</td><td>0.1</td><td>0.3</td><td>0.4</td><td>0.2</td></tr><tr><td>[16,+∞）</td><td>0.0</td><td>0.4</td><td>0.3</td><td>0.3</td></tr></table></body></html>

注：WRF为中尺度天气预报模式。下同。

过分放大问题，但是对较大误差的改善能力不及RF方法。

(2）当风速 $< 5 ~ \mathrm { m \cdot s ^ { - 1 } }$ 时，原始WRF预报与PDF优于RF、ACE方法，当风速 ${ \geqslant } 5 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 时，3种订正方法均表现出较好的订正能力： $5 \mathrm { m \cdot s ^ { - 1 } } \mathrm { \leqslant } ,$ 风速 ${ < } 1 6 \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 时,RF方法和ACE方法优于PDF;当风速 ${ \geqslant } 1 6 \ \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 时，ACE方法的订正能力开始下降，PDF的订正能力有所提升。

（3）分风速区间的集成方法优于分季节集成方法，其对不同风速区间下的WRF预报具有较好的改善效果。

本文通过按季构建WRF风速预报的RF、ACE方法及PDF订正模型，进行了3种订正方法在不同季节、风速区间的检验评估，发现订正后平均绝对误差和准确率均得以有效改善，且针对WRF预报的高值风速预报能力不足问题也具有一定的改善作用。但3种方法的订正能力随季节、风速区间的不同明显不同，因此如何发挥预报模型各自的优势，是集成应用过程中需要解决的关键技术问题。本

![](images/445a93f8f640fa995278860cde9e97fec79d329d9a0758b71c69fd0f72b022a4.jpg)  
Fig.6Temporal variation of wind speed before and after seasonal integration   
注：IF为分风速等级集成预报。  
图7分风速区间集成后的平均绝对误差和准确率  
Fig.7 Average absolute error and accuracy after integration considering the wind speed domain

# 干吴区地理

文提出在风速预报区间判别的前提下，进行多种预报模型的加权集成，可以较为有效地改善模型的订正能力。不足的是，本次研究的研究期仅为1a，后续将继续深入展开研究，为风速预报的最优订正提供更为可靠的研究基础。

# 参考文献(References)

[1]易跃春.中国可再生能源发展报告2019[R].北京:水电水利规 划设计总院,2O2O.[Yi Yuechun.China renewable energy development report 2O19[R]. Beijing: China Renewable Energy Engineering Institute, 2020.]   
[2]Xu JZ, He D X, Zhao X L. Status and prospects of Chinese wind energy[J]. Energy,2010,35(11): 4439-4444.   
[3]Feng Y,Lin HY,Ho SL, et al. Overview of wind power generation in China: Status and development[J]. Renewable and Sustainable Energy Reviews,2015,50: 847-858.   
[4]顾洪宾.中国可再生能源发展报告 2020[R].北京:水电水利规 划设计总院,2O21.[Gu Hongbin.China renewable energy development report 2O20[R]. Beijing: China Renewable Energy Engineering Institute, 2021.]   
[5]程兴宏,陶树旺,魏磊,等.基于WRF模式和自适应最小二乘回 归法的风能预报试验研究[J].高原气象,2012,31(5):1461- 1469.[Cheng Xinghong,Tao Shuwang,Wei Lei,et al. Short-term wind power forecasting experiment based on WRF model and adapting partial least square regression method[J]. Plateau Meteorology,2012,31(5): 1461-1469.]   
[6]石岚,徐丽娜,郝玉珠.多模式风速融合预报应用研究[J].高原 气象,2017,36(4):1022-1028.[Shi Lan,Xu Lina, Hao Yuzhu. Application research on the multi-model fusion forecast of wind speed [J].Plateau Meteorology,2017,36(4): 1022-1028.]   
[7]石岚,徐丽娜,郝玉珠.基于风速高相关分区的风电场风速预报 订正[J].应用气象学报,2016,27(4):506-512.[Shi Lan,Xu Li' na,Hao Yuzhu.The correction of forecast wind speed in a wind farm based on partitioning of the high correlation of wind speed[J]. Journal of Applied Meteorological Science,2016,27(4):506- 512.]   
[8]Wang JJ,Wang YF,LiY N.A novel hybrid strategy using threephase feature extraction and a weighted regularized extreme learning machine for multi-step ahead wind speed prediction[J]. Energies,2018,11(2): 321,doi: 10.3390/en11020321.   
[9]肖建辉.基于机器学习的风电场短期风速预测混合模型研究 [D].上海:东华大学,2020.[Xiao Jianhui.Research on hybrid model of wind farm short-term wind speed prediction based on machine learning[D]. Shanghai: Donghua University,2020.]   
[10] 李慧,陈湘萍.基于相空间重构和长短期记忆网络的风电预测 [J].新型工业化,2020,10(3):1-6.[Li Hui,Chen Xiangping. Wind power prediction based on phase space reconstruction and long sort-term memory networks[J]. The Journal of New Industrial

ization,2020,10(3): 1-6.]

[11] 王丹,高红燕,杨艳超,等.基于最优训练期的PP与MOS 的风 电功率趋势预报对比[J].干旱区地理,2021,44(3):819-829. [Wang Dan,Gao Hongyan,Yang Yanchao,et al.Comparative study of wind power trend forecast by using methods of PP and MOS with optimal training period[J]. Arid Land Geography,2021, 44(3): 819-829.]   
[12]Ren Y, Suganthan PN,Srikanth N.A novel empirical mode decomposition with support vector regression for wind speed forecasting[J]. IEEE Transactions on Neural Networks and Learning Systems,2016,27(8): 1793-1798.   
[13] 张铁军,颜鹏程,李照荣,等.基于短期历史资料的风能预报中 风速误差循环订正新方法[J].干旱气象,2017,35(6):1042- 1052.[Zhang Tiejun,Yan Pengcheng,Li Zhaorong,etal.A new cycle correction method for wind speed error in wind energy forecast based on short-term historical data[J]. Journal of Arid Meteorology,2017,35(6): 1042-1052.]   
[14] 邓华,张颖超,顾荣,等.基于PCA-RBF的风电场短期风速订正 方法研究[J].气象科技,2018,46(1):10-15.[Deng Hua, Zhang Yingchao,Gu Rong,et al. Correction method of short-term wind speed in wind farm research based on PCA and RBF neural network[J]. Meteorological Science and Technology,2018,46(1):10- 15.]   
[15] 张颖超,肖寅,邓华.基于ELM的风电场短期风速订正技术研 究[J].气象,2016,42(4): 466-471. [Zhang Yingchao,Xiao Ying, Deng Hua.Modification technology research of short-term wind speed in wind farm based on ELM method[J]. Meteorological Monthly,2016,42(4): 466-471.]   
[16] 杨培宏,胡庆林,胡忠林,等.风能特性对风电场电能输出预测 研究[J].计算机仿真,2016,33(12):122-127.[Yang Peihong,Hu Qinglin,Hu Zhonglin,et al.The predictive studyof wind energy characteristics for the power energy production of the wind farm [J]. Computer Simulation,2016,33(12): 122-127.]   
[17]中华人民共和国国家质量监督检验检疫总局,中国国家标准化 管理委员会.地面气象观测规范自动观测(GB/T 35237-2017) [S].北京:中国标准出版社,2017.[General Administration of Quality Supervision,Inspection and Quarantine of the People’s Republic of China,Standardization Administration of China.Specification for surface meteorological obversation: Automatic observation(GB/T 35237-2017)[S]. Beijing: China Standards Press,2017.]   
[18] 刘鸿波,董理,严若婧,等.ERA5再分析资料对中国大陆区域 近地层风速气候特征及变化趋势再现能力的评估[J].气候与 环境研究,2021,26(3):299-311.[Liu Hongbo,Dong Li,Yan Ruojing,et al. Evaluation of near-surface wind speed climatology and long-term trend over China’s mainland region based on ERA5 reanalysis[J]. Climatic and Environmental Research,2O21,26(3): 299-311.]   
[19] 刑丽珠,张方敏,黄进,等.1961—2018年内蒙古6级及以上大 风日数时空变化特征[J].干旱区地理,2021,44(5):1290-1298. [Xing Lizhu, Zhang Fangmin,Huang Jin, et al. Spatial and temporal changes of high wind days over category 6 and above in Inner Mongolia from 1961 to 2018[J].Arid Land Geography,2021,44 (5): 1290-1298.]   
[20]Lin YJ,Kruger U, Zhang JP,et al. Seasonal analysis and prediction of wind energy using random forests and arx model structures [J].IEEE Transactions on Control Systems Technology,2O15,23 (5):1994-2002.   
[21]孙全德,焦瑞莉,夏江江,等.基于机器学习的数值天气预报风 速订正研究[J].气象,2019,45(3):426-436.[Sun Quande,Jiao Ruili,Xia Jiangjiang,et al.Adjusting wind speed prediction of numerical weather forecast model based machine learning methods [J]. Meteorological Monthly,2019,45(3): 426-436.]   
[22] 徐晶晶,胡非,肖子牛,等.风能模式预报的相似误差订正[J].应 用气象学报,2013,24(6):731-740.[Xu Jingjing,Hu Fei, Xiao Ziniu,et al.Analog bias correction of numerical model on wind power prediction[J].Journal of Applied Meteorological Science, 2013,24(6): 731-740.]   
[23]钱磊,邱学兴,郑淋淋.基于概率密度匹配方法的WRF模式阵 风风速误差订正[J].气象科技,2019,47(6):916-926.[Qian Lei, Qiu Xuexing,Zheng Linlin.Error correction of WRF model gust speed based on probability density function matching method[J]. Meteorological Science and Technology,2019,47(6): 916-926.]   
[24]WangWQ,XiePP.A multiplatform-merged (MPM) SST analysis [J]. Journal of Climate,2007,20(9): 1662-1679.   
[25] 徐丽娜,申彦波,李忠,等.基于概率密度匹配方法的FY-4A地 表入射太阳辐射订正[J].高原气象,2021,40(4):932-942.[Xu Li'na, Shen Yanbo,Li Zhong,et al. Correction of FY-4A surface solar irradiance based on probability density function matching method[J].Plateau Meteorology,2021,40(4): 932-942.]   
[26]中国气象局.风电场风速预报准确率评判方法(QX/T 243- 2014)[S].北京:气象出版社,2014.[China Meteorological Administration. Evaluation of wind speed forecast accuracy in wind farm (GB/T 243-2014)[S]. Beijing: China Meteorological Press,2014.]   
[27] 任宏利,丑纪范.统计-动力相结合的相似误差订正方法[J].气 象学报,2005,63(6): 988-992.[Ren Hongli, Chou Jifan.Analogue correction method of errors by combining both statistical and dynamical methods together[J]. Acta Meteorologica Sinica, 2005,63(6): 988-992.]   
[28]疏杏胜,王子茹,李福威,等.基于机器学习模型的短期降雨多 模式集成预报[J].南水北调与水利科技,2020,18(1):42-50. [Shu Xingsheng,Wang Ziru,Li Fuwei,et al. Short-term rainfall multi-mode integrated forecasting based on machine learning models[J].South-to-NorthWater Transfers and Water Science& Technology,2020,18(1): 42-50.]   
[29]熊聪聪,潘璇,赵奇,等.多模式集成的RBF神经网络天气预报 [J].天津科技大学学报,2014,29(1):75-78.[Xiong Congcong, Pan Xuan,Zhao Qi,et al.RBF neural network for weather forecast based on multi-model integration[J].Journal of Tianjin University of Science & Technology,2014,29(1): 75-78.]

# Applicability research and integrated application of various correction methods for wind speed forecast in a wind farm

XU Li'na'，SHEN Yanbo²³，FENG Zhen'， YE Hu' （1.InnerMongoliaServiceCenterofMeteorology,HohhotOOo51,InnerMongolia,China;2.PublicMeteorologicalServiceCenter of China Meteorological Administration,Beijing 1o81,China；3.Windand Solar Energy Resources Centerof China Meteorological Administration,Beijing 1Ooo81, China)

Abstract: The method used for evaluating the correction effct of a model is very important for improving the short-term wind speed forecast.At present, the comparison of the correlation coeffcient and eror between the corrected and forecasted wind speeds in the research period is generally adopted.This evaluation method often ignores the limited correction abilityof most statisticalcorrection methods in low and high wind speed sections. Taking a wind farm in central Inner Mongolia, China as the experimental site,this studyuses the three methods of random forest (RF),analog correction of erors (ACE),and probability density function matching method (PDF） to correct the wind speed forecast in the experimental wind farm.A correlation coeficient and error analysis of the whole research period is performed.Wind speed is classified intocut-in wind speed,low, high,and full generating wind speeds,and cut-out wind speed.The applicability study of the three models in each grade is then conducted.The results show that the three methods have different degrees of correction effects on the weather research forecast (WRF) of wind speed in each season. The average absolute errr promotion rates in sequence are $6 . 7 \% - 3 6 . 7 \%$ ， $1 1 . 1 \% - 3 4 . 7 \%$ ,and $3 . 7 \% - 2 0 . 6 \%$ after correction via the RF, ACE,and PDF methods, respectively, in the model validation period.The RF method can effectively improve the large error problem of the WRF,but it also has the error overamplification problem.Although the ACE and PDF methods have less ability for improving the large error compared with the RF method，they can better control the error overamplification problem. For the small wind speed section of less than $5 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ ，the correction effect of the three methods is not ideal.The original WRF forecast and PDF method are better than the RFand ACE methods. With the wind speed increase,the WRF forecast eror significantly increases,and the correction ability of the three methods gradually increases.The RF and ACE methods are better than the PDF methods in the wind speed level of [5,16).The corrction ability of the ACE method begins to decline,，whereas that of thePDF method begins to improve in the wind speed level of $[ 1 6 , + \infty )$ . According to the respective advantages of the forecast models，the integrated application of various forecast models considering the wind speed forecast level is attempted to improve the WRF forecast under different wind speed levels.

Key words:wind speed forecast;；random forest；analogue correction of errors；probability density function matching method; integrating forecast