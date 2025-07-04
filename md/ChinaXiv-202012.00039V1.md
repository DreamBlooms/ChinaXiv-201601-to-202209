# 新疆地区多源降水融合试验

卢新玉¹，刘艳¹，王秀琴¹，刘晶¹，魏鸣²，宋志国³，张迎新}(1.中国气象局乌鲁木齐沙漠气象研究所,新疆 乌鲁木齐830002；2.中国气象局气溶胶-云-降水重点开放实验室,南京信息工程大学,江苏 南京 210044；3.山东省沂水县气象局,山东 沂水 276400)

摘要：利用新疆地区2016年夏季(6—8月)近2000个区域自动站小时降水数据,以最新一代GPM(Global Precipi-tation Measurement Mission,全球降水测量计划)IMERG(Integrated Multi-satelite Retrievals for GPM)卫星降水产品为初始场,运用概率密度匹配与最优插值两步融合校正方法(probability density function-optimal interpolation,PDF-OI),开展干旱区多源降水融合试验。首先,通过将实况观测与卫星反演降水进行概率密度函数(PDF)匹配,从而实现对IMERG降水的偏差订正;然后以偏差订正后的IMERG降水为初估场，实况降水为观测场，通过最优插值(OI)将偏差订正后的IMERG降水量估计值与雨量计实况相结合，最终得到经过两步校正后的新疆地区小时雨量数据。交叉验证结果表明，与雨量计实况和原始卫星降水数据相比，PDF-OI两步校正方法构建的融合降水不仅大大消除了系统误差，而且显著提高了数据精度。

关键词：星-地联合；小时降水；融合；新疆

降水是与大气潜热释放有关的大气活动，降水过程使得地球表面接收的太阳辐射被重新分配到大气层内部，从而驱动大尺度环流[1]。掌握一个特定区域的降水时空分布有助于更好地理解这一区域的生态、环境变化，而这其中最关键的是准确获取整个区域的降水数据。由于降水在不同空间和时间上有很大的差异，获得精确的区域和全球降水信息，往往是一项艰巨的挑战。

当前，获取降水信息的手段主要有3种：台站实况观测2、雷达估测和卫星遥感反演。站点观测具有较高的精度，但台站大多位于低海拔地带，且分布不均，不能有效反映降水的空间变化特征，空间代表性不强；基于气象雷达回波推算的降水数据具有一定区域估测的优点，然而Z-I(反射率-雨强)关系在不同的降水系统、季节、区域都有很大差异，影响了雷达估测降水的准确性，此外，雷达探测易受到地物阻挡、波束效应以及速度模糊等限制而使降水估测精度不高，实际应用中仍然存在较大限制；遥感和地理信息科学的快速发展，为大范围降水同步观测提供了新方法，卫星反演降水产品具有全天候、全球覆盖以及准确反映降水空间分布的独特优势[3-5],使其成为系统了解区域乃至全球降水情况及其变化的重要手段。

卫星遥感具有大范围空间连续探测的优势，但由于其是非直接观测，卫星反演降水的物理原理和算法还存在很多局限性，使得卫星降水产品具有很大不确定性，精度相对较低。因此，在应用之前，有必要进行卫星降水产品的订正。针对卫星降水产品精度较低，许多研究致力于发展卫星降水与地面观测实况的融合方法，其中包括客观统计分析，最优插值技术[7-10],神经网络[11-12],双核平滑[13]和地理差异分析[14]等。其中，国家气象信息中心针对多源降水融合开展了大量研究工作[7-9],由其研制的降水融合产品(CMPA)已通过全国综合气象信息共享平台下发至各级气象部门，在业务及科研中均得到广泛应用[15-19]。然而,CMPA融合降水主要以Climate Predic-tion Center (CPC) Morphing Technique (CMORPH)[20卫星降水产品为初始场，通过对该产品在新疆地区与其他卫星降水产品进行对比评估，结果显示最新一代全球卫星降水产品IMERG在干旱区的新疆比

CMORPH精度更高,尤其在小时尺度[2I]。因此,本研究在CMPA融合降水的研究方法基础上，在新疆地区以IMERG降水为初始场开展多源降水融合试验，以期获得更高质量的新疆地区小时降水融合产品

开展新疆地区卫星降水产品与地面观测实况的融合试验，对准确反映新疆降水分布信息和降水演变过程特征意义深远。通过研制的高时空分辨率格点降水数据集，将有助于推进我们对新疆地区小时强降水特征和发生发展规律的了解，为该地区提高预报准确率、预防气象次生灾害提供数据支撑，同时，为今后研制中亚区域高时空分辨率降水产品奠定技术基础。

# 1数据的获取

# 1.1GPMIMERG卫星降水

GPM(Global Precipitation Measurement Mission,全球降水测量计划是由美国国家航空航天局(NASA)与日本宇宙航空研究开发机构(JAXA)联合开发的全球降水测量系统,是TRMM(TropicalRain-fallMeasuringMission,热带降雨测量任务)的后续卫星降水计划。GPM是由1颗主卫星和10颗小卫星组成的1个卫星群，每3h获得1次全球降水分布数据资料。GPM核心卫星搭载了双频雷达和微波辐射计，其中，双频雷达比TRMM卫星多出一个Ka波段，可探测更为详细的降水微物理信息；微波辐射计比TRMM卫星多了4个高频波段，从而对小雨和降雪更加敏感。与主要观测中、大型降水的TRMM卫星相比，GPM提高了小雨和固态降水的观测能力，而这2种是新疆地区的主要降水类型，因此，对本研究区来说，GPM的观测成果具有重要研究意义。

本研究选取GPM的3级IMERG产品为降水初始场，时空分辨率为 $0 . 5 \mathrm { ~ h ~ } . 0 . 1 ^ { \circ } { \times } 0 . 1 ^ { \circ }$ 。研究中将0.5h降水累加为 $^ { \textrm { 1 h } }$ 与逐小时实况降水匹配，时间段为2016年6—8月。

# 1.2 实况降水

新疆地区近2000个区域自动站逐时降水数据，实况降水（命名为OBS)时间范围与IMERG降水数据一致。实况数据由新疆气象局信息中心整理并通过气候极值检验、单站极值检验和数据一致性检验等质量控制。为保证建模和验证的独立有效性，已剔除新疆地区19个国际交换站。由于新疆区域自动站大部分为翻斗式雨量计，只能测量降雨，在冷季停止观测，故研究选取暖季的6一8月开展研究。图1显示了新疆区域 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ 网格内台站数量分布情况，新疆地区 $0 . 1 ^ { \circ }$ 网格共有18038个，其中1509个为有效格点( $\angle 1 0 \%$ ),即该格点内至少包含1个雨量站。对1509个有效格点进一步细分，包含1个雨量站的有1267个（占 $8 4 \%$ ),2个雨量站及2个以上的分别有199个和43个，绝大部分有效格点都只含1个雨量站。按照10折交叉验证，将有效格点随机分为10组，每次选取9组用于PDF订正和OI融合，剩余的1组作为独立数据集进行偏差订正后以及最终融合产品的精度验证，如此重复10次，使每个台站都独立地进行了校正和检验，以此保证训练样本及验证样本的代表性和客观性。

![](images/50fb7ae217e74ae0d7ec26c4f4f216609ecba3c4ffd46962f89305e63b3a6f33.jpg)  
图1新疆区域 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ 网格台站个数分布示意图  
Fig.1 Distribution of gauge numbers in the $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ lat/lon grid boxes in Xinjiang

# 2 研究方法

# 2.1建立有效格点数据对

对新疆区域1509个有效格点进行卫星数据与地面实况的时空匹配，将落入同一网格的所有实况站点降水取平均与该网格卫星降水形成1个空间匹配数据对，时间上则取对应的同一时次进行匹配，处理过程中需注意卫星降水为世界时，需加 $8 \mathrm { ~ h ~ }$ 与实况降水的北京时对应，将配对好的数据样本作为下一步PDF(probability density function)订正与 OI(optimalinterpolation)融合的数据基础。

# 2.2PDF匹配法误差订正

PDF订正主要是以雨量计观测的实况降水概率密度对卫星降水估计的概率密度进行“标定”，使两者的概率密度值相匹配，从而达到去除卫星降水系统误差的目的[8-10]。具体步骤如下：

（1）由于小时降水具有零降水发生概率大以及更小时空尺度等特点，为保证获得稳定的累积概率密度，以待订正的IMERG降水格点（以下称当前格点)为中心， $4 ^ { \circ } { \times } 4 ^ { \circ }$ 空间范围为空间窗口选取有效格点数据对，同时，针对逐时降水的日变化特征，以当前时间为基准，取当前日期向前20d以及当前时刻向前6个时次为时间窗口，即每个订正时次共取当前格点 $4 ^ { \circ } { \times } 4 ^ { \circ }$ 空间范围内有效格点的120个匹配时次作为订正样本，从而收集得到匹配的地面观测和卫星降水进行PDF订正，详细过程可参考文献[9」。

(2）在上述得到有效格点数据对基础上，选取实况观测和卫星降水均为非缺测的作为有效数据样本，针对每个样本，以到当前时刻、当前格点的时空距离为权重进行最有效样本的筛选，

(3)按同一降水密度等级，分别计算每个当前格点时空匹配的有效数据样本中实况降水与卫星降水的累积概率密度，由此得到实况降水与卫星降水的累积概率密度匹配表，进一步计算当前格点卫星降水值在卫星降水累积概率密度表中所处的密度等级，得到相应的卫星降水概率密度值，同时，计算该卫星降水概率密度值所匹配的地面降水累积概率密度及对应的实况降水量 $( R _ { \mathrm { g } } )$ ,则订正后的卫星降水值即为 $R _ { \mathrm { g } }$ 。

# 2.3最优插值(OI)

最优插值分析以偏差订正后的IMERG降水为初估场，以站点实况降水为真值，每个格点上的最终降水分析值 $A _ { k }$ 由两部分组成，一部分为该点的初估值 $F _ { k }$ ,即卫星反演降水量，另一部分为该格点卫星降水值与实况降水量的偏差，由于大部分网格内都没有实况站点，因此，这个偏差由该格点周围一定范围内 $n$ 个有效格点数据对的偏差加权估计得到，公式如下：

$$
A _ { _ k } = F _ { _ k } + \sum _ { i = 1 } ^ { n } W _ { i } { \big ( } O _ { _ i } - F _ { i } { \big ) }
$$

式中： $k$ 和 $i$ 分别为当前分析格点和周围有效格点；$\textstyle \mathbf { W } _ { i }$ 为有效格点数据对的权重函数，表示 $i$ 点上实况值与初估值的偏差在订正时分配的权重。值得注意的是由于新疆站网稀疏，将分析半径设置为100$\mathrm { k m }$ ，以保证在本区域能搜索到一定数量的有效格点，再以距离由近及远排序，从中选取距离分析格点最近的 $n$ 个有效格点参与最优插值， $n$ 取值为9。权重系数 $\textstyle \mathbf { W } _ { i }$ 由该分析点降水值 $A _ { k }$ 的最小误差方差决定。

假设观测场与初估场均是无偏且观测误差和初估场误差不相关[7I],则式(1)的权重系数 $\textstyle \ W _ { i }$ 可以通过求解下面的线性方程组来得到：

$$
\sum _ { j = 1 } ^ { n } \bigl ( \mu _ { i j } ^ { f } + \mu _ { i j } ^ { o } \lambda _ { i } \lambda _ { j } \bigr )  { W _ { j } } = \mu _ { k i } ^ { f }
$$

式中:i,j均为有效格点,且i=j=1,2,·…,n; μ、$\mu _ { i j } ^ { o }$ 分别表示初估场误差协相关和实况观测误差协相关; $\lambda _ { i } ( \lambda _ { j } ) \lambda _ { i }$ 为 $i$ 点(i点)观测误差标准差 $\sigma _ { i } ^ { o } \big ( \sigma _ { j } ^ { o } \big )$ 和初估场误差标准差 ${ \boldsymbol { \sigma } } _ { i } ^ { f } \left( { \boldsymbol { \sigma } } _ { j } ^ { f } \right)$ 的比率。在OI融合算法中，关键是量化初估场和观测场的误差结构，这就要求式(2)中的 $\mu _ { i j } ^ { f } \setminus \mu _ { i j } ^ { o } \setminus \sigma _ { i } ^ { o }$ 和 $\boldsymbol { \sigma } _ { i } ^ { f }$ 均为已知量。本研究通过对2016年6—8月的样本数据进行统计得到上述参数值。参数统计过程中计算得到的卫星反演降水(IMERG)的均方误差与雨强的散点分布如图2所示，将有效格点中任意2格点卫星估测值与实况值的误差与距离做相关分析，可得到初估场的误差相关曲线(图3)。

上述参数中, $\mu _ { i j } ^ { f }$ 由图3拟合函数式得到,即给定初估场2格点 $i$ 和 $j$ 的距离则通过图3可得到2格点间的误差协相关； $\mu _ { i j } ^ { o }$ 为实况观测误差协相关，前提是每个台站的观测误差只与自身的观测有关，由此可得出， $i , j$ 相同时 $\mu _ { i j } ^ { o }$ 为1,不同时 $\mu _ { i j } ^ { o }$ 为0； $\boldsymbol { \sigma } _ { i } ^ { f }$ 表示初估场误差标准差，可由图2拟合函数通过给定卫星降水值得到，同理 $\boldsymbol { \sigma } _ { i } ^ { o }$ 可通过实况观测的均方误差与雨强的散点分布计算得到。详细计算过程可参考文献[7]。

![](images/36ab60b1edc2388f33e9349d61b5aea8375897ec6c3ac2cb9e06a8788d8fe40b.jpg)  
图2不同雨强下卫星反演降水(IMERG)的均方误差Fig.2Mean square errors of the IMERG under differentrainfall intensities

![](images/0e2c9835fa7bd227a010e3ffa62aa96246313d1db0308bcf988a518fcfd5b588.jpg)  
图3任意2格点误差相关

通过求解式(2)确定权重系数 $\textstyle \ W _ { i }$ ,最后由式(1)得到最终降水分析值 $A _ { k }$ 专

# 2.4检验评估

台站实测数据是最真实的降水监测，本研究按10折交叉验证利用独立站点进行融合降水产品的效果检验，并与原始IMERG小时降水的评估结果进行对比分析。主要选取4个统计指标进行评估，分为两类，第一类相关系数（CorrelationCoefficient,CC)，它反映融合降水与实测降水的一致性程度；第二类绝对平均误差（MeanError,ME）、相对误差（RelativeBias，RB）、均方根误差（RootMeanSquaredError,RMSE），用来描述融合降水对比实况的误差大小。公式如下所示：

$$
\mathrm { C C } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \left( x _ { i } - { \bar { x } } \right) \left( y _ { i } - { \bar { y } } \right) } { \sqrt { \displaystyle \sum _ { i = 1 } ^ { n } \left( x _ { i } - { \bar { x } } \right) ^ { 2 } \sum _ { i = 1 } ^ { n } \left( y _ { i } - { \bar { y } } \right) ^ { 2 } } } }
$$

$$
\mathrm { M E } = { \frac { 1 } { n } } \sum \left( x _ { i } - y _ { i } \right)
$$

$$
{ \mathrm { R B } } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \left( x _ { i } - y _ { i } \right) } { \displaystyle \sum _ { i = 1 } ^ { n } y _ { i } } } \times 1 0 0 \%
$$

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } } \Bigl ( x _ { i } - y _ { i } \Bigr ) ^ { 2 } }
$$

式中：CC为相关系数;ME为绝对误差;RB为相对误差;RMSE为均方根误差, ${ \bar { x } } = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } x _ { i }$ ， $\bar { y } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } y _ { i } \mathrm { ~ , ~ } n$ 为样本容量; $x _ { i } \ , \ y _ { i }$ 分别为降水估测值和气象站观测值。

# 3结果分析

# 3.1PDF匹配对原始IMERG降水的改进

通过与实况降水概率密度匹配，对原始IMERG卫星降水进行偏差订正。图4显示交叉验证后的实况（OBS）、原始IMERG、以及偏差订正后的降水（命名为pdf_CRT)3种降水数据的概率密度分布，注意由于小时降水中0值降水占绝大多数比例，因此，图4从大于 $0 \mathrm { m m }$ 降水开始统计。图4中反映出原始

![](images/9578f0006c5834626fb5407a9b42a728b87850e192794a37f336d74a5d02a25b.jpg)  
Fig.3Error correlation for the bias-corrected IMERG as a function of separation between two grid boxes   
图42016年夏季新疆地区实况（OBS）订正前(IMERG）、订正后(pdf_CRT)小时降水概率密度分布对比Fig.4Comparison of the PDFs of hourly precipitation amongOBS,original IMERG,and bias-correctedIMERG in summer 2016 over Xinjiang

IMERG降水在大多数情况下的概率分布均远远高于实况，只在降水量较大时 $\left( > 2 \mathrm { m m } \cdot \mathrm { h } ^ { - 1 } \right)$ 低于实况降水，而经过概率密度匹配订正后的pdf_CRT，在各个降水等级的概率密度值都明显与实况更为接近，具体表现为在原始IMERG的PDF偏大时减小其概率密度值，而在原始IMERG的PDF偏小时增大其概率密度值，体现了PDF订正方法中实况降水概率分布对卫星降水的调节作用。表1的定量评估结果也显示，PDF订正后相对误差由订正前的 $4 8 . 4 1 \%$ 减小到$2 3 . 7 7 \%$ ,降幅达 $5 0 \%$ 。表1还显示出PDF订正后相关系数比订正前略有下降(下降0.006)，表明PDF订正方法主要起到了降低卫星降水系统偏差的作用；进一步给出订正后降水数据的偏差随时间变化的曲线（图 $5 \mathrm { b } \sim 5 \mathrm { d } \AA .$ ），图中显示pdf_CRT降水的ME与RB在各个时段都比原始IMERG降水显著降低，系

# 表12016年6—8月3种降水产品交叉验证结果

Tab.1 Results of cross-validation of three precipitation products from June to August 2016   

<html><body><table><tr><td></td><td>相关 系数</td><td>平均误差 /(mm·h-1)</td><td>相对误差 1%</td><td>均方根误差 /(mm·h-1)</td></tr><tr><td>IMERG</td><td>0.288</td><td>0.15</td><td>48.41</td><td>1.20</td></tr><tr><td>pdf_CRT</td><td>0.282</td><td>0.08</td><td>23.77</td><td>1.24</td></tr><tr><td>pdf-oi_CRT</td><td>0.379</td><td>0.07</td><td>21.43</td><td>1.18</td></tr></table></body></html>

![](images/496bd40e15e4a1e8265b2215b62dd44bdab5ac837e193d17546025272f541ada.jpg)  
图52016年6—8月独立检验统计值的时间变化

Fig.5Time series of(a)CC,(b)ME,(c)RBand(d)RMSEbetween the gauge-based analysis andthe IMERG,pdf_CRT, and pdf-oi_CRT precipitation over Xinjiang from June to August 2016

统偏差更接近0。

# 3.2OI的改进效果

由表1可知，在各项指标中，经过2步校正的降水产品(命名为pdf-oi_CRT)都表现最优，与原始IMERG相比，相关系数提高 $3 1 . 6 \%$ ,绝对平均误差下降 $5 3 . 3 \%$ ,相对误差下降 $5 5 . 7 \%$ ,均反映出大幅改进效果。由图5可知，3种降水产品各种评估指标的时间变化曲线，直观地反映出pdf-oi_CRT降水质量在绝大部分时间点均比原始IMERG降水有很大提高。如CC从订正前的 $0 . 0 6 \sim 0 . 5 6$ 提高到PDF-OI订正后的 $0 . 0 6 \sim 0 . 6 6$ ;ME和RB分别由订正前的 $- 0 . 1 9 \sim$ $0 . 4 2 ~ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ 和 $- 2 7 . 1 4 \% \sim 6 5 8 . 2 2 \%$ 下降到 $- 0 . 1 4 \sim$ $0 . 2 7 \ \mathrm { m m ^ { \bullet } h ^ { - 1 } }$ 和 $- 2 3 . 0 6 \% \sim 4 1 3 . 2 \%$ ）

以上分析均是基于单个统计指标的对比评估，图6给出了各种降水产品与实况的泰勒图，泰勒图[22]以图形化的方式提供了1种针对模式(或估测)精度进行综合评价的方法。通过模式产品之间的相关系数、均方根误差和标准差来量化它们之间的相似性，离实况(字母A)距离越近则表明一致性越好。泰勒图对评估多个复杂模型或测量许多不同模型的整体性能方面特别有用。从图6可以看出，结果分布较一致，离实况最近的均是pdf-oi_CRT（字母D），表明pdf-oi_CRT降水的评估结果最好。进一步分析如图6a所示，在整个研究时段内实况降水的标准差（黑色虚线）为 $1 . 1 6 \ \mathrm { m m }$ ，而IMERG、pdf_CRT和pdf-oi_CRT分别为 $0 . 7 4 , 0 . 8 6$ 和0.92$\mathbf { m } \mathbf { m }$ ，这意味着pdf-oi_CRT降水的标准差最接近实况。同时，pdf-oi_CRT与实况降水的CC最高(0.39)，而RMSE(绿色虚线)均低于其他2种产品同样的结果也可以从各月的泰勒图得到反映（图$6 \mathrm { b } \sim 6 \mathrm { d } \AA .$ 。

![](images/982ba9f2e51a2df1e65355e9fa8b1fb554e889058743220da6e87cef21de8f88.jpg)  
注：A表示实况降水,B表示IMERG,C表示pdf_CRT,D表示pdf-oi_CRT。  
图63种降水产品2016年整个研究时段以及6—8月的泰勒图  
Fig.6Taylor diagrams of the three precipitation products for the whole period and each month from June to August 2016 over Xinjiang

# 3.3降水个例分析

2016年7月31日至8月1日新疆地区自西向东出现了大范围降水，其中伊犁地区"7·31"暴雨最为显著，此次大降水天气过程由7月31日17:00开始至8月1日17:00结束，雨强在8月1日02:00左右达到最强。图 $7 a \sim 7 d$ 分别给出了8月1日03:00（北京时）的地面自动气象站观测、IMERG卫星降水、pdf_CRT订正降水以及pdf-oi_CRT融合降水分布。从图7可看出，实况降水此时主要集中于伊犁、博州、塔城地区，而大值中心在伊犁地区；图7bIMERG卫星反演降水显示降水区域远远大于实况分布，且降水大值中心比实况偏北位于塔城地区托里县一带，此外,阿勒泰、阿克苏以及喀什地区均有大面积降水，而实况站点显示该区域仅有少量台站出现降水，这反映出卫星反演降水普遍存在的高值低估、低值高估的现象；图7c是经过概率密度匹配订正后得到的格点降水pdf-CRT,可以看出，由PDF偏差订正后，原始卫星降水的虚报和高估现象得到显著改善，且降水大值中心也下移至与实况一致的伊犁地区，然而不足之处是pdf-CRT降水过滤掉了许多实况站发生降水的区域，尤其在伊犁、博州西部地区;图7d为概率密度匹配与最优插值两步校正最终得到的pdf-oi_CRT融合降水，该图显示原始IMERG降水在PDF偏差校正基础上再融合实况降水，不仅修正了图7c中PDF处理后被错误过滤的有降水区域，而且确保了在有实况站点的区域与实况保持一致，在无实况观测区域保留卫星反演降水分布，有效结合了2种观测方式的优点。

# 3.4同类融合降水产品对比

本研究是建立在文献[8-12]的方法基础上，不同之处在于，本研究选取在新疆地区精度更高的GPMIMERG卫星降水产品作为初始场，且在算法处理过程中根据新疆地区降水特点进行了本地化处理，因此，有必要将得到的pdf-oi_CRT融合降水与国家气象信息中心研发的全国范围降水融合产品CMPA进行比较。需要指出的是，由于缺乏独立验证数据集，无法将pdf-oi_CRT产品与CMPA产品进行全面的对比评估，本研究通过将两者在空间分布上进行对比，分析评估两者的差异。同样以“7·31"暴雨过程为例，图8给出融合降水CMPA(图8e)及其初始场CMORPH(图8d)同期降水空间分布，与本文初始场IMERG（图8b)以及融合降水pdf-oi_CRT（图8c)进行对比。图8d显示CMORPH卫星数据对比实况观测，其降水范围显示出明显的高估现象，尤其在新疆北部的阿勒泰、塔城以及新疆南部的喀什、和田地区，其融合产品CMPA在新疆北部地区有了很大改进，而在新疆南部地区仍存在大量高估区域，而图8c融合降水pdf-oi_CRT则在2个区域都做出了很好地处理，与实况降水空间分布较为一致。由伊犁河谷降水中心来看，CMPA也比实况明显偏大，由于CMORPH卫星降水在新疆地区存在明显的高估[20],因此，本研究基于IMERG的融合试验有望得到更为准确的区域降水量。

![](images/0faa9c5d7095853940603d60930815f7cc0411a736bc3e15a94f6fac2c78132a.jpg)  
图72016年8月1日03：00新疆地区雨强分布  
Fig.7Hourly precipitation at 03:00( $\mathrm { \ U T C } { + } 8 )$ 1 August 2016 over Xinjiang

![](images/d93f8b18da114946968d3893de2acd9675483e64b01c09133c40afed7917dd49.jpg)  
图82016年8月1日03:00新疆地区雨强分布对比  
Fig.8 Comparison of the hourly precipitation at 03:00 ( $\mathrm { \ U T C } { + } 8 )$ 1 August 2016 over Xinjiang

# 4结论

（1）概率密度匹配法(PDF)对原始IMERG的系统误差有很好的订正效果，使原始卫星降水产品的绝对平均误差与相对误差均明显减小。

（2）交叉验证结果显示，在IMERG降水产品系统误差经PDF订正后显著降低的基础上，进一步利用OI方法与实况降水融合，使最终得到的格点降水数据集质量进一步提高。

（3）研究体现了PDF-OI方法应用于IMERG卫星降水产品的有效性，且融合产品的降水量与CMPA融合降水相比与实况更为一致。

参考文献(References):   
[1]Ebert E,Janowiak J, Kidd C.2007: Comparison of near real time precipitation estimates from satellite observations and numerical models[J].Bulletin of the American Meteorological Society,2007, 88: 47-64.   
[2]秦贺,陈春艳,阿不力米提江·阿布力克木,等.新疆暖季短时强 降水特征[J].干旱区研究,2019,36(6):1440-1449.[Qin He, Chen Chunyan,Ablimitijan Ablikim,et al.Characteristics of shortduration heavy rainfall in warm season in Xinjiang[J].Arid Zone Research,2019,36(6): 1440-1449.]   
[3]刘元波,傅巧妮,宋平,等.卫星遥感反演降水研究综述[J].地球 科学进展,2011,26(11):1162-1172.[Liu Yuanbo,Fu Qiaon, Song Ping,et al. Satellite retrieval of precipitation: An overview [J]. Advances in Earth Science,2011,26(11): 1162-1172.]   
[4]穆振侠,姜卉芳,刘丰.基于 TRMM/TMI与实测站点的降水垂 直分布差异性探讨[J].干旱区研究,2010,27(4):515-521.[Mu Zhenxia,Jiang Huifang,Liu Feng.Discussion on difference of vertical distribution pattern of precipitation based on TRMM/TMI and observed data[J].Arid Zone Research,2010,27(4): 515 -521.]   
[5]王玉丹,陈浩,刘璨然,等.ITPCAS 和CMORPH两种遥感降水 产品在陕西地区的适用性研究[J].干旱区研究,2018,35(3): 579-588.[Wang Yudan,Chen Hao,Liu Canran,et al.Applicability of ITPCAS and CMORPH precipitation datasets over Shaanxi Province[J].Arid Zone Research,2018,35(3): 579-588.]   
[6]FaridIshak Boushaki, Kuolin Hsu, Soroosh Sorooshian,et al. Bias adjustment of satelite precipitation estimation using ground-based measurement:A case study evaluation over the southwestern United States[J]. Journal of Hydrometeorology,2009,10:1231-1242.   
[7]潘肠,沈艳,宇婧婧,等.基于最优插值方法分析的中国区域地 面观测与卫星反演逐时降水融合试验[J].气象学报,2012,70 (6): 1381-1389.[Pan Yang,Shen Yan, Yu Jingjing,etal.Analysis of the combined gauge-satellite hourly precipitation over China based onthe OI technique[J].Acta Meteorologica Sinica,2012,70(6): 1381-1389.]   
[8]宇婧婧,沈艳,潘肠,等.概率密度匹配法对中国区域卫星降水 资料的改进[J].应用气象学报,2013,24(5):544-553.[Yu Jingjing,Shen Yan,Pan Yang,etal. Improvement of satelitebased precipitation estimates over China based on probability density function matching method[J]. Journal of Applied Meteorological Science,2013,24(5): 544-553.]   
[9]Shen Y, Zhao P,Pan Y,et al.A high spatiotemporal gauge-satellite merged precipitation analysis over China[J]. Journal of Geophysical Research,2014,119:3063-3075.   
[10]Xie PP, Xiong A Y.A conceptual model for constructing high-resolution gauge-satelite merged precipitation analyses[J]. Journal of Geophysical Research,2011,116, D21106.   
[11]卢新玉,魏鸣,王秀琴.TRMM月降水量产品在新疆地区的订 正[J].应用气象学报,2017,28(3):379-384.[Lu Xinyu,Wei Ming,Wang Xiuqin. Correction of TRMM monthly precipitation data from 1998 to 2013 in Xinjiang[J].Journal of Applied Meteoro logical Science,2017,28(3): 379-384.]   
[12] 李慧,杨涛,何祺胜,等.新疆天山山区TRMM卫星降水数据的 复合校正方法[J].干旱区研究,2017,34(3):585-590.[Li Hui, Yang Tao,He Qisheng，et al. Composite correction method of TRMM satelite precipitation data in the Tianshan Mountains,Xinjiang[J]. Arid Zone Research,2017,34(3): 585-590.]   
[13]Li M, ShaoQ X.An improved statistical approach to merge satelliterainfall estimatesandraingaugedata[J]. JournalofHydrology, 2010,385: 51-64.   
[14]Baik Jongjin,Park Jongmin,Ryu Dongryeol. Geospatial blending to improve spatial mapping of precipitation with high spatial resolution by merging satelite-based and ground-based data[J]. Hydrological Processes,2016,30: 2789-2803.   
[15]张蒙蒙,江志红.我国高分辨率降水融合资料的适用性评估[J]. 气候与环境研究,2013,18(4):461-471.[Zhang Mengmeng,Jiang Zhihong. Anlyses of high-resolution merged precipitation productsover China[J]. Climatic and Environmental Research,2013, 18 (4): 461-471. ]   
[16] 周璇,罗亚丽,郭学良.CMORPH卫星-地面自动站融合降水数 据在中国南方短时强降水分析中的应用[J].热带气象学报, 2015,31(3): 333-344.[Zhou Xuan,Luo Yali, Guo Xueliang. Application of a CMORPH-AWS merged hourly gridded precipitation product in analyzing characteristics of short-duration heavy rainfall over Southern China[J]. Journal of Tropical Meteorology,2015,31 (3): 333-344.]   
[17]吴薇,杜冰,黄晓龙,等.四川区域融合降水产品的质量评估[J]. 高原山地气象研究,2019,39(2):76-81.[Wu Wei,Du Bing, Huang Xiaolong,et al.Quality evaluation of regional integrated precipitation products in Sichuan Province[J]. Plateau and Mountain Meteorology Research,2019,39(2): 76-81.]   
[18] 王皓,罗静,叶金印,等.CMORPH融合降水产品与地面观测雨 量资料估算淮河流域面雨量对比分析[J].河海大学学报(自然 科学版),2014,42(3):189-194.[Wang Hao,Luo Jing,Ye Jinyin, et al. Comparative analysis of area rainfall in Huaihe River Basin estimated by CMORPH-Gauge merged data and observed rain gauge data[J].Journalof Hohai University (Natural SciencesEdition), 2014, 42(3): 189-194.]   
[19] 陈圆圆,宋晓东,黄敬峰,等.基于地面站点观测降水资料的中 国区域日降水融合产品精度评价[J].自然资源学报,2016,31 (6): 1004-1014.[Chen Yuanyuan, Song Xiaodong, Huang Jingfeng, et al.Evaluation of the high-resolution daily merged precipitation product over China based on in situ observations[J].Journal of Natural Resources,2016,31(6): 1004-1014.]   
[20]Joyce R, Janowiak J,Arkin P,et al. CMORPH: A method that produces global precipitation estimates from passive microwave and infrared data at high spatial and temporal resolution[J]. Journal of Hydrometeorology,2004,5(3): 487-503.

[21]Lu X,Tang G,Wei M,et al. Evaluation of multi-satellite precipitation products in Xinjiang,China[J]. International Journal of Remote Sensing,2018,39(21): 7437-7462.

[22] Taylor K. Summarizing multiple aspects of model performance in a single diagram[J]. Journal of Geophysical Research,2OO1,106: 7183-7192.

# Multisource precipitation data merging experiment in Xinjiang

LU Xin-yu'， LIU Yan'， WANG Xiu-qin'， LIU Jing'， WEI Ming²,SONG Zhi-guo², ZHANG Ying-xin'

(1.InstituteofDesertMeteorology,China MeteorologicalAdministration,Urumqi83oo02,Xinjiang,China; 2.Key Laboratory for Aerosol-Cloud-Precipitation of China Meteorological Administration, Nanjing University of Information Science and Technology,Nanjing 21oo44,Jiangsu, China; 3.Yishui meteorological bureau of Shandong,Linyi 27640o,Shandong, China)

Abstract:Precipitation is a fundamental component of the Earth's water cycle.Recognizing the temporal and spatial distributionsof precipitation in a specific area is helpful to better understand theecological and environmentalchanges inthis area,andthe most importantof theseis toaccuratelyobtain the precipitation data for the entire area.Therefore,developing high spatiotemporal resolution and high-quality precipitation data is an urgent need as he development of modern meteorological services.In this paper,the study on a fusion method based on two-source precipitation,that is,satelite precipitation data and groundobservation,iscariedout inthe Xinjiang area with sparse stations in China,which can be of great significance to accurately reflect the precipitation distribution information and the characteristics of precipitation evolution process in this area.

Using hourly precipitation data in summer (June-August) 2016 of about 2OOO automatic weather stations (AWS) over Xinjiang and using the latest generation of GPM IMERG satelite precipitation data as the first guess,a twostep strategy based on the probability density function (PDF） matching and optimal interpolation(OI) technique (PDF-OI) was conducted toa studyon fusion methods of precipitation in arid regions.First,the bias of the IMERG precipitation is corrected by matching thePDFof theobservation with thesatelite data.Then,the bias-corrected IMERG precipitation (pdf_CRT) is used as the initial estimation fieldand the observation field (OBS)as the truthvalue; the combination of the pdf $\mathbf { \bar { \Big { - } } }$ CRT and OBS through the OI method is carried out to finally obtain hourly areal precipitation data (pdf-oi_CRT) in Xinjiang.The cross-validation results show that,compared with the OBS and the satelite precipitation,the PDF-OI fusion method notonly greatly eliminates the bias but also significantly improves the accuracy of the original satellite precipitation data.

In this study,a useful exploration is made in developing a grid precipitation data set in Xinjiang,which is locatedina middle-to high-latitudearid area.Theresults show thatthe studyonthe multisource precipitation fusion method helps develop grid precipitation data set.The high temporaland spatial resolution grid precipitation data set will help us understand the characteristics and occurrence and development regularityof hourly heavy precipitation in the Xinjiang area.Furthermore,it willalso provide data support for improving the accuracyof forecast and preventingsecondary meteorological disasters and the technical foundation fordeveloping high spatial and temporal resolution precipitation products in the Central Asian region.

Keywords: satellite-gauge merging; hourly precipitation; fusion; Xinjiang