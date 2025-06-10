# 太阳活动区低色球层亮点幂律分布时变规律的观测分析

李小波1,2,3，杨志良²，张洪起³（1.中国科学院云南天文台，云南 昆明650011；2.北京师范大学天文系，北京100875；3.中国科学院太阳活动重点实验室，北京100012)

摘要：太阳耀斑和微耀斑能量的幂律分布是太阳活动的一个典型特点。调查其统计特征和时变规律，对研究太阳能量的传输和耗散以及高层大气的加热机制有重要意义。研究太阳低层大气中能量释放的统计规律及其演化过程，使用二维区域标记算法，在日出(Hinode)卫星上的太阳光学望远镜(Solar Optical Telescope，SOT)对 NOAA 10930 活动区观测的低色球层Ca II$\mathrm { ~ H ~ } \lambda 3 9 6 8 . 5$ 单色像资料上，分析表征亮点能量分布的频数特征及其变化规律。在时间跨度为$1 2 4 \mathrm { h }$ 、视场为 $2 0 2 ^ { \prime \prime } . 4 \times 8 5 ^ { \prime \prime } . 3$ 的时间序列中，共获得 $2 . 9 9 \times 1 0 ^ { 5 }$ 个亮点，平均每帧图上每平方角分有 $2 4 . 1 5 \pm 6 . 3 4$ 个亮点。主要分析结果如下：(1)亮点尺度 $L = \sqrt { L _ { x } L _ { y } }$ )的瞬时分布基本符合幂律分布并满足自相似性；(2)亮点的产生率及其信噪比随着尺度的增加而减小。海量微小尺度亮点持续的发生可能是加热高层大气的一种稳定而可观的能量来源，例如，尺度小于 $4 ^ { \prime \prime }$ 的亮点产生的光通量在样本总光通量中占的比例达到 $5 3 . 2 3 \%$ ；（3)小尺度亮点的瞬时数密度随着活动区的衰减而降低；(4)亮点集的尺度服从幂律分布，其离散系数 $\sigma ( \zeta )$ 仅为 $4 \%$ 。该实测样本尺度的幂指数 $\gamma$ 为1.97，低噪声样本( $\left. L \leqslant 8 ^ { \prime \prime } \right.$ 的 $\gamma$ 为2.12；（5)但是，在观测时段内， $\gamma$ 并没有收敛。样本集的 $\gamma$ 是一个在观测积累中呈锯齿状变化的过程：在平静时段缓慢升高，在活动瞬间突然降低。 (6)亮点瞬时子集的 $\gamma$ 与其总光通量呈反比。在样本中剔除大尺度 $\left( L > 8 ^ { \prime \prime } \right)$ 个体后，中小尺度亮点仍服从上述规律。太阳活动不仅产生中、大尺度的增亮区域，还对各尺度区间亮点的频数分布产生全局性的影响，引起瞬时 $\gamma$ 的降低。

关键词：幂律分布；亮点；耀斑；太阳色球；区域标记法中图分类号： $\mathrm { P } 1 8 2 . 2 \substack { + 3 }$ · $\mathrm { P } 1 8 2 . 5 \substack { + 2 }$ 文献标识码：A 文章编号：1672-7673(2017)02-0135-15

太阳活动的一个典型统计特征是耀斑能量的幂律分布。在硬 X射线[1-4]、软X射线[5-8]和极紫外[9-10]波段，耀斑和微耀斑的峰值辐射通量、爆发频率、尺度和寿命基本呈幂律分布[11]。幂律分布的

$$
F ( X ) = \alpha X ^ { - \gamma } , ( \alpha > 0 , \gamma > 1 , \ m i n \{ X \} \leqslant X \leqslant m a x \{ X \} \ ) ,
$$

$$
\begin{array} { r } { \log _ { 1 0 } \left[ F ( X ) \right] = \log _ { 1 0 } \alpha - \gamma \log _ { 1 0 } X . } \end{array}
$$

其中， $X$ 为表征耀斑能量的某受测量； $F ( X )$ 为其频数密度。例如，硬X射线耀斑的光子流量 $I ( E )$ 与光子能量 $E$ 的关系符合幂律分布[5]：

$$
I ( E ) = A E ^ { - \gamma } \mathrm { p h o t o n s } \left( \mathrm { c m } ^ { 2 } \mathrm { s \ k e V } \right) ^ { - 1 } .
$$

太阳活动基本满足幂律分布的自相似性，即对于两个容量不同、但 $\gamma$ 相近的耀斑样本，其分布曲线的形状相似。虽然不同活动区的爆发机制、频率和强度有很大差异，但是，个体活动区上亮点的幂律分布和在全日面、长时标数据上对大量太阳活动的统计中得到的幂律分布在图形和机理上基本相似[12-13]，二者都是太阳活动内禀的性质。作为一个无标度的复杂网络，太阳活动总体的幂律分布是大量无标度分布的综合。在无标度复杂网络中，规模迥异但演化机制相同的复杂网络结构常表现出自相似性(分形)。不同规模的能量连锁耗散事件发生的几率与其规模不相关，会形成形状相似、幅度不同的幂律分布。这种现象在实验、空间和模拟的等离子体中普遍存在[14]。因此，各种尺度的活动区产生的活动也在一定程度上具有自相似性。

亮点的幂律分布可能具有与太阳活动的周期性相对独立的性质。虽然在全日面、跨越太阳周的统计中，日冕亮点的分布具有时空的周期性。在空间上，爆发事件频发的区域与强磁场的分布带[15]基本吻合[16]。在时间上，太阳活动的剧烈程度变化有11 年的长周期和若干个短周期[3,17]，还有一定的随机性[18]，这种周期性还造成了地球电离层的周期变化[19]。但是，多项研究表明[3.5,1,20]，耀斑的频数分布不仅基本维持幂律分布，而且其幂指数 $\gamma$ 并没有表现出与太阳周明确的相关性， $\gamma$ 的涨落小于线性回归的不确定性。例如，在文[7]对24 年间(1976\~2000)地球静止轨道环境业务卫星(GeostationaryOperational Environmental Satelites，GOES）观测的5万余个耀斑的统计研究中，太阳周峰年和谷年的软X射线峰值流量分布有很接近的幂指数。这可能意味着，耀斑的幂律分布是一个与太阳活动的剧烈程度相对独立的统计规律，其背后的物理机制并不随太阳周变化。但是，也有统计表明， $\gamma$ 具有周期性，例如，文[4]认为， $\gamma$ 随太阳周变化，在峰年较大，谷年较小。

在使用多个波段对太阳活动的统计结果中，实测频数分布的中段往往与幂律吻合较好；而在能量较低的一端，实测频数往往低于幂律。这种偏差在相当程度上由观测设备的局限性造成。一方面，实测频数受观测设备在背景噪声中识别低能量事件的阈值的限制，降低观测设备的阈值能够大幅度提高所获取的小规模样本的容量。例如，文［1]使用搭载于轨道太阳观测台7号卫星（Orbiting SolarObservatory7,OSO-7)的由加州大学圣地亚哥分校（University of California，San Diego，UCSD)研制的硬X射线探测器对X射线爆发进行统计，该设备的低端阈值约为 $0 . 3 \left( { \mathrm { c m } } ^ { 2 } { \mathrm { s } } \ { \mathrm { k e V } } \right) ^ { - 1 }$ 。在统计结果中，20$ { \mathrm { k e V } }$ 的峰值流量 $A _ { \mathrm { m } }$ 在 $1 { \sim } 1 0 ( \mathrm { ~ c m } ^ { 2 } \mathrm { s } \ \mathrm { k e V } ) ^ { - 1 }$ 的区间是光滑并且符合幂律的；但在 $A _ { \mathrm { { m } } } < 0 . 5 ( \mathrm { \ c m ^ { 2 } s \ k e V } ) ^ { - 1 }$ 段，频数明显低于幂律并形成平台。而文[2]使用了低端阈值比UCSD小一个数量级的X射线探测器，所观测的X射线爆发 $2 0  { \mathrm { k e V } }$ 峰值流量的频数分布在 $0 . 0 1 { \sim } 0 . 1 ( \mathrm { c m } ^ { 2 } \mathrm { s } \ \mathrm { k e V } ) ^ { - 1 }$ 段都是光滑并且符合幂律的。另一方面，对小规模个体的实测频数受观测设备时间和空间分辨率的制约。数量巨大的短时标个体由于其寿命近似或低于时间序列的间隔而被漏检，而尺度小于设备衍射极限的邻近个体又可能被合并，因而无法准确统计其频数。例如，文[21]使用大熊湖的新太阳望远镜(New Solar Telescope，NST)和太阳光学望远镜对光球磁亮点的比较观测研究中，新太阳望远镜（衍射极限为 $7 7 \mathrm { k m }$ )不但可以将太阳光学望远镜（衍射极限为 $1 5 7 ~ \mathrm { k m }$ )所观测到的亮点个体分解为多个更小尺度的亮点。而且，在新太阳望远镜(时间分辨率达 $6 \mathrm { ~ s ~ } ^ { - 1 }$ )的观测样本中， $9 8 . 6 \%$ 的光球亮点的寿命短于太阳光学望远镜的观测间隔时间(120s)，所以不一定能被太阳光学望远镜检测到。对小规模个体有较高漏检率的情况也出现在对低色球层亮点[22]和行星际磁通量绳[23]的观测统计中。

幂律分布不可能向零无限延伸，极小规模的亮点必然有独特的分布规律。如果完全按照幂律分布$\alpha E ^ { - \gamma }$ ，则日面上亮点产生的总能量：

$$
\begin{array} { l } { { \displaystyle \int _ { E \to 0 } ^ { E _ { \mathrm { m a x } } } } { \cal F } ( E ) E \mathrm { d } E = \displaystyle \int _ { E \to 0 } ^ { E _ { \mathrm { m a x } } } \alpha E ^ { 1 - \gamma } \mathrm { d } E } \end{array}
$$

将趋近于无穷[24]，而实际的太阳亮点产生的总能量一定是收敛的，这也是分布函数归一性的要求。这就意味着，亮点完全样本的频数分布曲线必然在低端存在一个拐点，小于该拐点规模的频数低于幂律分布。如果该拐点是尖锐而不是圆滑的，小于该规模的亮点的数目极少，则在统计上可以认为它就是亮点的最小规模。在观测设备的发展过程中，当分辨阈值处于亮点频数分布曲线的幂律段以内时，所获得的样本容量

$$
\int _ { X _ { \operatorname* { m i n } } } ^ { X _ { \operatorname* { m a x } } } F ( X ) \mathrm { d } X = \frac { A X ^ { ( 1 - \gamma ) } } { 1 - \gamma }
$$

会随着阈值的减小而大幅度增加。但是当阈值小于幂律低端拐点时，所能分辨的亮点数密度和相应的亮点辐射总能量会缓慢地向完全样本逼近。

幂律分布表明，太阳大气是一个能量不断输入并耗散的系统。一切太阳活动的根源是在太阳内部生成的磁场[25]。大的磁流管从对流区上浮[26]，把磁能和复杂性带到了光球以上的大气中。大气磁场组成的网络是一个复杂网络[27]。它不仅有规模大、结构复杂、层次多、节点多样化等特点，还具有明显的时空复杂性。一方面，该网络不是封闭的，和大多数真实的网络一样，它具有增长性，不断有新的节点加人。自下而上不断有新的磁能和扰动的输入[28]，产生新的磁场凝聚和爆发，而能量耗尽的节点又逐渐退出。太阳活动的过程，就是网络节点不断新陈代谢、拓扑和动力学性质不断演化的过程。能量从高数量级向低级跃迁[29]而发生耀斑。大的爆发能释放足够多的磁能，暂时清空可供释放的自由能，使得活动区需要一定的时间积蓄能量。这样，耀斑的能量、频率和等待时间的分布都有可能服从幂律分布。另一方面，从复杂网络节点的连接性的角度看，该网络的演化具有择优性，光球上新浮现的磁场(及其所带来的能量和复杂性)倾向于在原有活动区附近出现和聚集[30-31]。复杂网络中的一个新的节点并不是随机与其他 $k$ 个节点发生联系，它有首先与度值较高的节点相连的倾向。这就造成高度值的节点快速增加度值、节点之间度值的差异被放大的结果，逐渐演化成了标度不变的状态，各节点的度值 $k$ 就形成了幂律分布。

太阳活动的幂律分布对研究太阳高层大气的加热机制有重要意义。在色球及以上的太阳大气中，由于磁敏线的稀少，无法直接观测能量释放过程中的磁场空间结构和演化过程，而对亮点的分布特征和时变规律的准确统计为研究大气加热提供了宝贵的信息。文［32]认为，如果 $\gamma$ 超过2，海量微小规模耀斑能够有效地加热日冕；反之，如果 $\gamma$ 小于2，则大耀斑的分布基本决定了总的能量输出。微观上，低层亮点的震荡有可能向上传播磁流体动力学（Magnetohydrodynamics，MHD)波和阿尔文（Alfven）波并发生湍流耗散，进而造成色球和日冕的加热[33-34]。

对于单个太阳活动区而言，由于其能量的有限性，所产生的爆发是否一定遵循幂律分布还不是一个很明确的问题[24,32]。这就需要分析活动区的不同演化阶段爆发活动的分布特征与能量平衡的关系。幂指数的演变机制，尤其是幂指数与熵的关系，以及与外界驱动的关系，对于研究网络如何演化成自组织是重要线索，但目前还没研究得很清楚[35]。值得一提的是，在宁静太阳的范畴中，幂律分布不一定成立。例如，光球亮点的尺度[21,36]和面积[37]均服从对数正态分布。

在前期工作[22]中，使用三维区域标记法对一个太阳活动区的低色球层亮点进行了识别和统计分析。主要结果是：（1)活动区低色球层亮点的尺度、面积和光通量基本服从幂律分布；（2)亮点寿命的频数在中等时标呈幂律分布，在长时标呈指数分布。大规模亮点的等待时间符合指数分布。亮点的产生符合泊松过程的基本特点；(3)海量的小规模亮点有可能向日冕稳定地提供能量；(4)微小规模亮点的实测频数低于幂律分布，这在相当程度上受观测数据的低时间分辨率所造成的低采样率的影响。

前人对于光球磁亮点的精细结构和日冕亮点的统计规律已经积累了相当丰富的观测和理论分析，对色球亮点的震荡[38]也进行了精细的观测，但是，对色球亮点的频数分布规律却只有较为稀少的研究[39]。本文使用低色球层的观测资料，侧重于分析亮点的瞬时分布在时域中的变化和累积，主要研究以下几个问题：（1)在短时标和瞬时观测中，亮点的频数分布遵循什么规律？是否满足无标度性？(2)亮点的瞬时频数分布特征如何随活动区整体的演化而变化？在长时标中，瞬时分布如何累积成为幂律分布？（3)亮点瞬时分布的各参数之间有怎样的相关性？

# 1资料和分析方法

# 1. 1 活动区

选取一个爆发现象丰富、演化过程复杂的活动区作为研究样本。NOAA10930活动区位于南半球赤道附近（S05），尺度约为 $9 0 ^ { \prime \prime } \times 1 0 0 ^ { \prime \prime }$ ，其主黑子是一个半径约为 $2 9 ^ { \prime \prime }$ 、处于稳定衰减阶段的负极性黑子。该活动区于2006年12月05日在日面东边初现时是一个 $\beta$ 型活动区，随后，在主黑子的西侧边缘出现了多个磁浮现区，产生了二十余枚小黑子和微黑子。整体的磁场位型也相应地由 $\beta$ 变成了 $\beta - \gamma - \sigma$ 。图1（a)和(b)显示了活动区的形态。在日面期间(05\~18日），AR10930 发生了7个X级和数十个C级和M级爆发。表1列出了它的爆发事件。

![](images/7abd68b6158be9a2eed88ee10acd732af5a1a945879f8aea977e5e70ef434f64.jpg)  
图1NOAA10930活动区在(a)活动和(b)平静时的CaIIH单色像.(c)空心和实心方框分别表示(a)和(b)中亮点尺度的瞬时频数分布  
Fig.1 Ca IIH monograms of NOAA AR1093O in（a）an active and（b）aquiet moment.The unit for coordinates is arcsecond.（c） Instantaneous distributions of BPs'scale $L$ plotted in double-logarithm coordinates.Hollow and solid spades respectively mark samples in panels(a）and（b)

表1NOAA10930的爆发记录a Table1EventsofNOAA AR10930   

<html><body><table><tr><td>8</td><td></td><td></td><td></td><td>1</td><td></td><td>Time</td><td>Observation Ⅱ</td><td>观测时 0</td><td>BFI 60</td><td>08</td><td>0</td><td></td><td></td><td></td></tr><tr><td>S06W91</td><td>S06W86</td><td>S06W73</td><td>S05W61</td><td>S05W47</td><td>S06W35</td><td>S05W21</td><td>S05W08</td><td>S04E05</td><td>S05E18</td><td>S06E31</td><td>S05E46</td><td>S06E58 一</td><td>lon°/lat°</td><td>纬/经度</td></tr><tr><td>β-y-g</td><td>β-y-σ</td><td>β-y-g</td><td>β-y-g</td><td>β-y-σ</td><td>β-y-g</td><td>β-y-g</td><td>β-γ-g</td><td></td><td></td><td>β-y-0</td><td>β-y-g</td><td></td><td>d</td><td></td></tr><tr><td>I</td><td>I</td><td>0</td><td>乙</td><td>4</td><td>乙</td><td></td><td></td><td>0</td><td>0</td><td>→u</td><td></td><td>忆-</td><td>3</td><td></td></tr><tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td></td><td></td><td>Ｉ→→-</td><td>W</td><td>爆发Class</td></tr><tr><td>0</td><td>0</td><td>0</td><td>I</td><td>乙</td><td>I</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>I</td><td>乙</td><td>一 X</td><td></td></tr></table></body></html>

（a）摘自由“活动区监测”发布的“活动区观测摘要”；（b）2006年12月（a）Published by the NOAA/USAF Active Region Summaryand retrieved from the Active Region Monitor（ARM）;（b）2006 December

# 1.2 数据和预处理

使用由宽带滤光器成像仪（BroadbandFilterImager，BFI)获得的 $\mathrm { C a ~ I I ~ H ~ } \lambda 3 9 6 8 . 5$ 波段低色球层单色像时间序列。宽带滤光器成像仪是搭载在“日出”卫星上的太阳光学望远镜的成像系统之一。宽带滤光器成像仪使用时间分辨率为1帧/120秒、像元大小为 $0 ^ { \prime \prime } . 1 0 6 \times 0 ^ { \prime \prime } .$ 106、视场为$2 1 7 ^ { \prime \prime }$ $1 \times 1 0 8 ^ { \prime \prime } . 5$ 的参数对NOAA10930活动区进行了124小时（09日20：02\~14日23：54)的观测。该CaIIH数据中，增亮尺度的跨度达2.5个数量级，包含耀斑、微耀斑和非爆发性的增亮，增亮区域的形状可呈椭圆、弧形或不规则形状，由于研究目的是从统计角度对低色球层增亮进行分析，所以本文中把这些尺度、形状和性质迥异的增亮区域统称为亮点。

日出卫星另有两套成像系统：极紫外成像摄谱仪（Extreme-ultraviolet Imaging Spectrometer,EIS)和X 射线望远镜（X-Ray Telescope，XRT）。在它们采集的图像中也有大量的亮点，蕴含丰富的物理信息。但是，与CaIIH波段相比，一方面，它们的工作波段高度较高，没有相应高度的实测磁场数据；另一方面，极紫外成像摄谱仪和X射线望远镜的像元分辨率 $( \sim 2 ^ { \prime \prime } )$ 比宽带滤光器

成像仪低一个数量级，图像提供的细节信息较少，在CaIIH像中由数十个亮点组成的团簇，在高层大气中仅表现为一个或多个亮点[40]。因此，研究选择在CaIIH单色像上进行亮点的识别和统计，而没有使用极紫外成像摄谱仪和X射线望远镜的数据。

# 1.3 计算方法

开发了一套基于二维区域标记的数据压缩方法，在时间序列中对亮点进行识别和统计。基本步骤如下。

（1)图像预处理。首先，剔除原始数据中成像受干扰的坏图，矫正不准确的像素。然后对图像做投影改正，使用快速傅里叶变换相关跟踪的算法对单色像对齐，并选取观测较为连续的时间段。预处理之后的时间序列包含2597帧图像，视场为 $2 0 2 ^ { \prime \prime } . 4 \times 8 5 ^ { \prime \prime } . 3$ 。

(2)识别亮点。首先，使用根据亮度分布制定的阈值，把二维时间序列中的每个亮点对应的高亮度像素团簇加以标记。由于宽带滤光器成像仪的衍射极限为 $0 ^ { \prime \prime } . 2$ ，使用侵蚀和膨胀的方法过滤像元（ $0 ^ { \prime \prime } . 1 0 6 \times 0 ^ { \prime \prime }$ .106)级的微小亮点，并对亮点区域进行孤立和抛光。然后，测量每个亮点的尺度 $L$ 、面积 $A$ 和光通量 $\phi$ ，并建立数据库。这些受测量表征了亮点的能量，在本文中泛称为规模。其中，考虑到亮点形状的不规则性，研究中对尺度的定义为亮点所占最小矩形面积的平方根( $L = \sqrt { L _ { x } L _ { y } } .$ )，而不是亮点的最大空间展宽(线度)。本文主要以尺度为受测量介绍对亮点幂律分布的分析结果；若无特别说明，下文中的频数分布均指亮点尺度的频数分布。

(3)统计分析。一方面，分析瞬时亮点子集的频数分布特征量在时域中的变化；另一方面，把亮点样本集作为一个整体分析其频数分布。对于每组受测量 $X$ ，首先使用对数分组以获得样本受测量的频数分布 $F ( X )$ 。由于频数分布及其特征量对分组的方案有相当的敏感性，采用不合理的组限会引入随机性并造成幂律分布特征值之间虚假的相关性，在经验公式[41]

$$
N _ { \mathrm { b i n } } = 1 + \log _ { 1 0 } ( n ) / \log _ { 1 0 } ( 2 )
$$

的基础上对样本集和瞬时子集分别确定一个通用的组数 $N _ { \mathrm { b i n } }$ ，用于对受测量的对数 $\log _ { 1 0 } ( X )$ 进行等距分组。然后，使用下式[42]

$$
\gamma = 1 + n \left( \sum _ { i = 1 } ^ { n } \ln { \frac { X _ { i } } { X _ { \operatorname* { m i n } } } } \right) ^ { - 1 }
$$

估算指数 $\gamma$ ，并对频数 $F ( X )$ 使用最小二乘法进行线性回归(2式)以获得系数 $\alpha$ 。为了描述实测频数偏离幂律分布的相对程度，还分别在普通和对数笛卡尔坐标中计算两个离散系数：

$$
\delta ( X ) = \frac { F ( X ) } { \alpha X ^ { - \gamma } } - 1 ,
$$

$$
\zeta ( X ) = \frac { \log _ { 1 0 } [ F ( X ) ] - \log _ { 1 0 } ( \alpha X ^ { - \gamma } ) } { \operatorname* { m a x } \left\{ \log _ { 1 0 } [ F ( X ) ] \right\} - \operatorname* { m i n } \left\{ \log _ { 1 0 } [ F ( X ) ] \right\} } .
$$

对于一个频数分布，使用 $\delta ( X )$ 和 $\zeta ( X )$ 的标准差表征该分布在何种程度上符合幂律分布，称为该分布的离散系数。对于某个已经基本判定为幂律的频数分布，其中某点的 $\delta ( X )$ 和 $\zeta ( X )$ 表征了该点的频数密度 $F ( X )$ 偏离该分布的幂律拟合 $\alpha X ^ { - \gamma }$ 的程度，称之为该点的离散系数。上述4个量在本文中统称为离散系数，均为无量纲的相对量，可以用百分比表示。

# 2 结果

在该时间序列中共获得 $2 . 9 9 \times 1 0 ^ { 5 }$ 个亮点，平均每帧图上每平方角分有 $2 4 . 1 5 \pm 6 . 3 4$ 个亮点。亮点尺度的取值范围是 $0 ^ { \prime \prime } . 2 1 \sim 7 6 ^ { \prime \prime } . 1 1$ 。亮点逐帧总光通量的变化幅度达2个数量级。

2.1活动区亮点能量瞬时分布的幂律特征

亮点的瞬时频数分布基本服从幂律分布。尽管视场中的太阳活动水平有跨多个数量级的剧烈变化，但是每一帧图像中亮点的频数分布相对幂律的离散系数只在很有限的范围内变化。图2（a)中的虚线和点划线分别表示根据亮点尺度的瞬时分布计算的离散系数的分布。虽然离散系数 $\sigma ( \delta )$ （虚线）

的均值达到 $4 8 \%$ ，但是在双对数坐标系中，频数分布与线性回归结果基本符合，离散系数 $\sigma ( \zeta )$ （点划线)的均值为 $1 6 \%$ (表2)。而且， $\sigma ( \delta )$ 和 $\sigma ( \zeta )$ 均呈正态分布（点线）。考虑到逐帧子集的容量较小$( \sim 1 0 ^ { 2 } )$ ，在误差允许的范围内，可以认为亮点的瞬时频数服从幂律分布。

亮点的分布基本满足幂律分布的自相似性。图2(a)用实线绘制了亮点逐帧子集的幂指数 $\gamma ( t )$ 的频数分布。 $\gamma$ 近似呈正态分布，其相对变化幅度 $\{ \sigma [ \gamma ( t ) ] / \overline { { \gamma ( t ) } } = 0 . 2 0 \}$ 远小于瞬时光通量的相对变化幅度 $\{ \sigma [ \phi ( t ) ] / \overline { { \phi ( t ) } } = 2 . 3 8 \}$ 。在双对数坐标系中，这种自相似性表现为逐帧子集频数分布的拟合直线近似平行。例如，图1(a)采集于该区域活动较为剧烈的一个时刻，视场中共有253个亮点。该帧总光通量的 $8 4 \%$ 是由尺度大于 $8 ^ { \prime \prime }$ 的8个大尺度亮点提供的，其中尺度最大达 $5 7 ^ { \prime \prime }$ 。而图1(b)采集于较为宁静的一个时刻，视场中共有47个亮点，尺度最大的仅为 $2 ^ { \prime \prime } . 4$ ，其亮点的总光通量仅为图1(a)中亮点总光通量的 $0 . 8 0 \%$ 。虽然这两个瞬间的活动水平有巨大的差异，但是它们各自都服从幂律分布，而且二者的 $\gamma$ 仅相差约 $7 \% ( { \mathrm { a } } _ { : } 0 . 8 1 4 , { \mathrm { b } } _ { : } 0 . 8 7 6 )$ 。它们的频数分布是两条幅度不同但近似平行的曲线（图1（c））。

![](images/30fd76f14358181c2d61408f76bc9013b34c80dcb8a918007c4550c97d41e999.jpg)  
图2（a）亮点瞬时频数分布特征量的频数分布及其高斯拟合；（b）亮点瞬时容量 $n$ 与瞬时光通量 $\varphi$ 的关系Fig.2（a）Frequency distributions of the power-law index y（solid curves），dispersion coefficients $\sigma ( \delta )$ （dashed curves）,and $\sigma ( \zeta )$ （dash-dotted curves）of $\mathrm { B P s ^ { \prime } }$ instantaneous distributions.Dotted curves mark results of Gaussian fiting;（b）Instantaneous sample capacity $n$ as a function of the logarithm of instantaneous light flux $\phi$

表2亮点样本频数分布的幂律参数  
Table 2Parameters of power-law fitting the observed BP samples   

<html><body><table><tr><td>行</td><td>样本a</td><td>组数Nbin</td><td>受测量b</td><td>log10a</td><td>2</td><td>σ(8)</td><td>σ()</td></tr><tr><td>1</td><td>全时段实测</td><td>80</td><td>尺度L</td><td>3.97</td><td>1. 97</td><td>0.396</td><td>0.040</td></tr><tr><td>2</td><td>样本集</td><td></td><td>面积A</td><td>3.44</td><td>1. 10</td><td>0.375</td><td>0. 069</td></tr><tr><td>3</td><td></td><td></td><td>光通量Φ</td><td>8.59</td><td>1. 00</td><td>0.504</td><td>0.101</td></tr><tr><td>4</td><td>全时段低噪声</td><td>80</td><td>尺度L</td><td>3.92</td><td>2.12</td><td>0.239</td><td>0.058</td></tr><tr><td>5</td><td>样本集</td><td></td><td>面积A</td><td>3.27</td><td>1. 09</td><td>0.525</td><td>0.092</td></tr><tr><td>6號</td><td></td><td></td><td>光通量Φ</td><td>8.23</td><td>0.97</td><td>0. 691</td><td>0.137</td></tr><tr><td>7</td><td>瞬时实测</td><td>20</td><td>尺度L</td><td>0.66 ± 0.11</td><td>0.97 ± 0.19</td><td>0.47 ± 0. 11</td><td>0.16 ± 0. 04</td></tr><tr><td>8</td><td>子集</td><td></td><td>面积A</td><td>0.48 ± 0. 12</td><td>0.55 ± 0.11</td><td>0.47± 0.10</td><td>0.17 ± 0. 04</td></tr><tr><td>9</td><td></td><td></td><td>光通量Φ</td><td>3.25 ± 0. 53</td><td>0.59 ±0.10</td><td>0.46 ± 0. 10</td><td>0.17 ± 0.04</td></tr><tr><td>10</td><td>瞬时低噪声</td><td>20</td><td>尺度L</td><td>0. 65 ± 0. 11</td><td>0.99±0.18</td><td>0.47 ± 0. 11</td><td>0.16 ± 0. 04</td></tr><tr><td>11</td><td>子集</td><td></td><td>面积A</td><td>0.48 ± 0. 12</td><td>0.57 ± 0.10</td><td>0.47 ± 0.10</td><td>0.17 ± 0.04</td></tr><tr><td>12</td><td></td><td></td><td>光通量</td><td>3.30 ±0.52</td><td>0.54 ± 0. 10</td><td>0.47 ± 0.10</td><td>0.18± 0.04</td></tr></table></body></html>

(a）Lines 1-3：observed sample set； lines $_ { 4 - 6 }$ : low-noise sample set； lines 7-9：observed instantaneous subsets；lines 10-12:low-noise instantaneous subsets；（b）Quantities : $\mathrm { B P s ^ { \prime } }$ scale $L$ ，area A，and light flux $\phi$ （204号

# 2.2小尺度亮点产生率的稳定性

微小尺度亮点的发生是持续稳定的。亮点幂律分布的一个重要特征就是频数随着规模的增加而迅速减小，而其产生率的涨落和间歇性都随着规模的增加而增加。对亮点样本按照尺度进行分组后，使用4项指标表征各尺度区间亮点发生的稳定程度：(1)平均数密度 $\stackrel { - } { d }$ ；(2)分组容量在样本容量中的比例 $R _ { \mathrm { n } }$ ；（3)瞬时发生率 $R _ { \mathrm { o c c } }$ ：某尺度区间的亮点在时间序列中出现帧数的比例；（4)信号噪声比 $R _ { \mathrm { S / N } }$ ：某尺度区间亮点的瞬时数密度 $d ( L , \ t )$ 在相邻某短时间区间(1h)内的均值与标准差的比值：

$$
R _ { \mathrm { S N } } ( L , \ t ) = \overline { { { d ( L , \ t ) } } } / \sigma [ d ( L , \ t ) ] , \ t - t _ { b } \ < \ t < t + t _ { b } , \ t _ { b } = 0 . 5 \ h .
$$

$R _ { \mathrm { { s } / N } } ( L , \ t )$ 在观测时段内的集中趋势表征了 $d$ 在短时标变化的剧烈程度。表3(第1\~4行)列出了使用组距为 $2 ^ { \prime \prime }$ 进行等距分组后计算所得的上述4项指标。其中，尺度小于 $4 ^ { \prime \prime }$ 的亮点的瞬时发生率在 $9 9 \%$ 以上，即它们在绝大多数帧的图像中出现；而尺度大于 $8 ^ { \prime \prime }$ 的亮点的瞬时发生率和信噪比都非常低。图3(b)绘制了使用组距为 $0 ^ { \prime \prime } . 5$ 进行等距分组获得的结果。它表明，亮点发生的频繁和稳定程度都随着尺度的增加而迅速减小。图3(a)把这种区别直观地表现了出来：大尺度亮点(符号)的发生是间歇性的，而中小尺度亮点(曲线)的产生较为稳定。基于这些观察，在分析中剔除了产量低、噪声高的个体，把样本中所有尺度不大于 $8 ^ { \prime \prime }$ 的亮点作为一个子样本，以下称为低噪声样本，其容量为实测样本的 $9 9 . 6 4 \%$ 。把含有 $L > 8 ^ { \prime \prime }$ 个体的瞬间称为活动瞬间；把只含有低噪声样本的瞬间称为平静瞬间。

微小规模亮点的总辐射能量是相当可观的。表3的第5行是各尺度区间的亮点产生的光通量占视场中所有亮点的总光通量的比例 $R _ { \Phi }$ 。尺度小于 $4 ^ { \prime \prime }$ 的亮点辐射的总光通量在样本集总光通量中占的比例达到 $5 3 . 2 3 \%$ （表3第5行）。考虑到宽带滤光器成像仪的低时间分辨率，小尺度短时标亮点样本在被识别过程中有相当高的漏检率[22]，微小尺度亮点光通量所占的实际比例有可能高于上述测量值。与此相比，最大一个尺度区间的亮点( $L \geqslant 1 0 ^ { \prime \prime } ,$ )虽然包含了多个M和X级爆发事件，其光通量只占样本总光通量的 $3 1 \%$ 。因此，海量微小规模亮点持续的发生可能是加热高层大气的一种稳定而可观的能量来源。

# 2.3亮点频数分布在时域中的变化

小尺度亮点明显地表现出衰减的趋势。从各尺度区间亮点的数密度 $d$ 与时间 $\mathbf { \chi } _ { t }$ 的关系中，得到一个相对增长率 $R _ { \mathrm { g } } = \Delta d ( L , \ t ) / [ d ( L , \ t ) \Delta t ]$ ，它在观测时段内的集中趋势 $\overline { { R _ { \mathrm { g } } } }$ 表征了每单位时间（小时)该组亮点数密度的平均相对增长速率，其数值(表3的第6行)表明，尺度小于 $6 ^ { \prime \prime }$ 的3个尺度区间的亮点都在不同程度地减少。在图3(a)中，这种衰减趋势表现为小于 $8 ^ { \prime \prime }$ 的3个尺度区间数密度的线性拟合(点划直线)的斜率均为负。例如，对比观测的开始和结束，尺度为 $1 ^ { \prime \prime } { \sim } 2 ^ { \prime \prime }$ 的亮点的数密度减小了 $84 \%$ (线性拟合后)。虽然这种衰减可能在一定程度上是由临边昏暗造成的观测效应，但是它与活动区整体上处于衰减、趋于沉寂的趋势相符合。而大尺度亮点(图3(a)中符号)的信噪比过低，难以作为判断总体趋势的有效依据。

表3各尺度亮点的基本统计指标  
Table 3Basic statistical values of BPs grouped by scale   

<html><body><table><tr><td>行</td><td>统计指标a</td><td>L<2"</td><td>2"≤L<4"</td><td>4" ≤L<6"</td><td>6"≤L<8"</td><td>8" ≤L< 10"</td><td>10" ≤ L</td></tr><tr><td>1</td><td>平均数密度d/角分-2</td><td>22.29</td><td>1.31</td><td>0.22</td><td>0.07</td><td>0.03</td><td>0.06</td></tr><tr><td>2</td><td>占样本容量的比例R/%</td><td>92. 16</td><td>5.42</td><td>0.91</td><td>0.29</td><td>0.12</td><td>0.24</td></tr><tr><td>3</td><td>瞬时发生率Roc/%</td><td>100. 00</td><td>99.42</td><td>61. 46</td><td>26.42</td><td>12. 55</td><td>14. 71</td></tr><tr><td>4</td><td>信号噪声比Rs/N</td><td>9. 92</td><td>2. 77</td><td>1.03</td><td>0.56</td><td>0.37</td><td>0.49</td></tr><tr><td>5</td><td>占光通量比例R/%</td><td>35.80</td><td>17. 43</td><td>7.95</td><td>4.71</td><td>3.10</td><td>31.01</td></tr><tr><td>6</td><td>相对增长率R/%</td><td>-0.63</td><td>-0.53</td><td>-0.02</td><td>0.04</td><td>0.16</td><td>0.61</td></tr></table></body></html>

(a）1.Average numerical density $\bar { d } / \mathrm { a r c m i n u t e } ^ { - 2 }$ ；2.share in total sample capacity $R _ { \mathrm { n } } / \%$ ；3.instantaneous occurrence rate $R _ { \mathrm { { o c c } } } / \%$ ；4. signal-to-noise ratio $R _ { \mathrm { { S } / { N } } }$ ；5.share in total light flux $R _ { \Phi } / \%$ ；6.relative growth rate $\overline { { R _ { \mathrm { g } } } } / \%$

15 30 二 8 100数密度d（-）/ 2 +16">L≥8" 2">L≥0" 光通量比例R△32">L≥16" 4 >L≥2 信噪比Rs/N 80■L≥32" 8">L≥4" (z-） 瞬时发生率Rocc 6 %/1 线性拟合 10 %： 尔/P出 60： - 江 + 40l 福 美 价 中 5 40•20xxx A A心 山 M BAB 福 2LM 4 5-2 M A A 丰 0 L 山 0 」0 100 20 40 60 80 100 120 0 2 4 6 8 10时间t/h 尺度 $L / { } ^ { \prime \prime }$ （204号(a) (b)

在统计分布中，活动区的衰减表现为瞬时分布的调幅指数 $\alpha$ 逐渐减小。为了研究瞬时分布的参数是否随活动区的演化而变化的问题，在时域中以小时为单位对亮点的瞬时子集进行了分组。图4（a)和(b)分别绘制了瞬时 $\alpha$ 和 $\gamma$ 在每小时区间的均值(实心方块)和标准差(误差棒)随时间(横轴)的变化。在图4(a)中，调幅指数 $\alpha$ 基本保持随时间降低的趋势，这与瞬时容量(虚线)的降低一致，表征了活动区的衰减。

幂指 $\gamma$ 的变化与大规模亮点的存在有密切关系。图4(b)中，方块表示每小时 $\gamma ( t )$ 的均值；虚线表示瞬时亮点子集的总光通量

$$
\phi ( t ) = \sum _ { i = 1 } ^ { n ( t ) } \phi _ { i }
$$

的时变， $\phi$ 的突然变化主要由少数大尺度亮点造成。比较 $\gamma ( t )$ 和 $\varPhi ( t )$ 的变化可以看出，当活动区较为平静时，瞬时分布的 $\gamma$ 较高；当产生大规模的亮点时， $\gamma$ 便迅速降低。

![](images/2e57d9814b19348a9c635f8f04eac60575e3032b54e38030ae2f01e6a95b277e.jpg)  
图3（a）亮点数密度的时变。曲线/符号表示某小/大尺度区间亮点的瞬时数密度 $\scriptstyle d ( L , t )$ 的对数。直点划线表示 对相应曲线的线性拟合；（b）表征亮点产生情况的4个统计指标与尺度的关系 Fig.3（a）Temporal variations of the logarithm of $\mathrm { B P s ^ { \prime } }$ instantaneous numerical densities $d ( L , \ t )$ as grouped by scale. Those of smalland big BPsare marked with curves and symbols respectively.Straight lines show resultsof linear regression；（b）Four parameters（d, $R _ { \phi }$ ， $R _ { S / N }$ ，and $R _ { \mathrm { o c c } }$ ）that reflect $\mathrm { B P s } ^ { \prime }$ production as functions of $\mathrm { B P s } ^ { \prime }$ scale $L$ （20   
图4亮点瞬时频数分布的特征量(纵轴)在时域(横轴)中的变化。实心方块和误差棒分别表示瞬时(a)调幅系数 $\alpha$ 和(b)幂指数 $\gamma$ 在1小时内的均值和标准差  
Fig.4Temporal variations of the parameters of $\mathrm { B P s ^ { \prime } }$ instantaneous distributions.Filled squares and error bars respectively mark the hourly averages and standard deviations of（a） $\alpha$ and（b) $\gamma$ .Dashed curves indicate the instantaneous（a） sample capacity $n$ and（b）logarithm of total light flux $\phi$ （204号

# 2.4瞬时频数分布系数之间的相关性

为了研究图4中幂律参数时变的成因，分析了表征亮点瞬时分布和太阳活动水平的几个特征量的相关性，并绘制了散点图5。平静和活动瞬间在图中分别用十字和方片标记。图5(a)表明，调幅系数 $\alpha$ （纵轴)与亮点瞬时子集容量 $n$ (横轴)之间有明确的线性关系。正如幂律关系(1)式， $\alpha$ 的时变实质上体现了瞬时容量的变化。图5(b)表明，幂指 $\gamma$ 与瞬时容量 $n$ 之间也有线性关系，当 $n$ ，尤其是小尺度亮点的数目增加时， $\gamma$ 也相应增加。图5(c)表明，幂指 $\gamma$ 与瞬时总光通量 $\phi$ 成反比。当活动剧烈时， $\phi$ 增加而 $\gamma$ 降低；而当活动区较为平静时， $\gamma$ 维持在较高的水平。这与图4(b)表现的二者关系一致。图5(d)表明，幂指 $\gamma$ 与 $\alpha$ 是两个相对独立的参数，它们在平静和活动瞬间都没有表现出可信的相关性。

在绘制图4(b)和5(c)时，使用的都是低噪声样本， $\gamma$ 是中小尺度个体的幂指数，计算过程（7)式未受大尺度个体的干扰。这说明，它们所揭示的 $\gamma$ 的突降与大尺度个体存在的关系不是一种统计效应。并不是当瞬时子集中加入了极少数大规模个体后，影响了数值计算的结果，从而造成了 $\gamma$ 突然降低的假象。 $\gamma$ 与太阳活动水平之间的关系是中小规模亮点分布的本征性的内在规律，爆发事件对活动区亮点的频数分布有全局性的影响，改变了瞬时分布的模式。

![](images/4b5d82b30a17699912696ca990785aaeacc8347f008032356e76597f284e5db5.jpg)  
图5亮点瞬时频数分布各特征量之间的相关性。活动的瞬间用方片标记，平静的瞬间用十字标记。实线和虚线分别表示对活动瞬间和平静瞬间散点的线性回归  
Fig.5Correlations between the parameters of $\mathrm { B P s } ^ { \prime }$ instantaneous frequency distributions.Active and quiet moments are respectively indicated with spades and crosses.Solid and dashed lines respectively mark linear regressions for active and quiet moments

# 2.5样本集的幂律分布及其累积过程

亮点集的尺度服从幂律分布。图6(a)表示在观测时段内获得的所有亮点尺度的频数分布，虚线是对实测频数的幂律拟合。图6(c)表示实测分布(方片)与幂律(水平中线)的离散系数 $\delta ( L )$ 与尺度的关系。可以看出，在 $L$ 取值范围的中段( $1 . 5 \gtrsim \log _ { 1 0 } L \gtrsim 0 . 7$ ，即 $3 2 ^ { \prime \prime } \gtrsim L \gtrsim 0 ^ { \prime \prime } . 5 \$ )，频数较好地服从幂律分布，二者的离散是随机的。而在 $L$ 取值范围的两端，二者有系统性的偏差。表2的第1行列出了对样本的尺度进行拟合得出的幂律参数和离散系数，其离散系数 $\sigma ( \zeta )$ 仅为 $4 \%$ 。

![](images/26bd6e9e2b75041b11863db7f12daf8f124b28b34f15638bc39983e88db77f8c.jpg)  
图6 （204号 $\left( \mathbf { a } { \sim } \mathbf { b } \right)$ 亮点尺度(a)和光通量(b)的频数分布。虚线和点划线分别是对实测频数的线性和二项式拟 合。 $( { \bf c } \sim { \bf d } )$ 实测频数偏离幂律分布的离散系数δ(纵轴)与亮点规模(横轴)之间的关系 Fig.6 $\mathrm { { ( a - b ) } }$ ）Frequency distributions of $\mathrm { B P s } ^ { \prime }$ （a）scale and（b）light flux. $( \mathrm { c } \mathrm { - d } )$ Coefficients of dispersion $\delta$ as functions of $\mathrm { B P s ^ { \prime } }$ (c）scale and（d） light flux.Dashed lines and spades mark results of linear regressions; crosses and dash-dotted curves mark results of binomial regressions

但是，上述亮点样本的幂律分布并不是稳定的，在为期124小时的观测时间内 $\gamma$ 没有收敛。假设某观测始于该时间序列的起点( $: t _ { 0 } = 2 0 0 6 - 1 2 \mathrm { - } 0 9 \mathrm { T } 2 0 : 0 2 \mathrm { Z } )$ ，终止于时间序列中的某时刻 $t _ { 0 } { + } D$ ，则可以计算从观测时段获得的亮点子样本的幂律参数与观测时长 $D$ 的关系。在图7中，任一时刻的 $\gamma$ （实线)和 $\alpha$ (虚线)描述了在 $t _ { 0 } \sim t _ { 0 } { + } D$ 中累积的亮点样本尺度的幂律分布。图中还绘制了代表视场中太阳活动水平的瞬时总光通量 $\varPhi ( t )$ （点划线)以作为参考。图7(a)和(b)分别使用实测样本和低噪声样本。由图7(a)可知， $\alpha$ 随着样本容量的累积而单调增加。当观测时段很短时（曲线左端）， $\gamma$ 有大幅度的震荡；当活动水平较为平静时， $\gamma$ 逐渐增高；当发生大规模事件时，样本集中被注入了小 $\gamma$ 的瞬时子集，造成累积 $\gamma$ 的急剧降低。在 $D$ 的取值范围内，γ一直处于锯齿状变化之中，没有收敛。可以推测，即便进行更长时标的观测，样本中也会不定期地加入大规模的个体，累积 $\gamma$ 也有可能发生突然的变化。因此，实测样本集的 $\gamma$ 是一个在观测积累中不断变化的过程，基于该样本所得到的 $\gamma$ 值(表2第1\~3行)只有有限的意义，在该活动区的统计结果中也无法判断 $\gamma$ 的长时标走向。

为了减小少量大尺度个体对子样本 $\gamma$ 的影响，使用低噪声样本重复上述计算并绘制了图7（b）。在去除大尺度个体之后， $\gamma$ 虽没有收敛，但其变化幅度随着容量的增加而逐渐减小。可以认为，低噪声样本的 $\gamma$ 值(表2第4\~6行)对观测时段的选取不很敏感，因而有较高的可信度，能较客观地反映亮点的频数分布特征。

在双对数坐标系中，亮点的光通量 $\phi$ 和面积 $A$ 基本服从二项式分布。从实测样本集的光通量的频数分布(图6(b))及其与幂律的离散 $\delta ( \phi )$ （图6(d))可以看出，二者有系统性的偏差。对小容量的瞬时亮点子集而言，该偏差可以忽略，线性(幂律)拟合可以代表其频数分布的主要特征。但此偏差对大容量的样本集来说不能忽略，幂律分布不能准确地表示其分布。对面积和光通量使用二次项拟合

$$
\begin{array} { r } { \log _ { 1 0 } F ( X ) = a _ { 1 } - a _ { 2 } \log _ { 1 0 } X - a _ { 3 } ( \log _ { 1 0 } X ) ^ { 2 } } \end{array}
$$

后(图6(d)中十字），大大减小了此偏差。

![](images/6f8fa6cfdc65dda855d457b86dd1c5ffc64548d7502dd8cbfb9923599f9a7be2.jpg)  
图7累积亮点样本集的频数分布各参数(纵轴)随观测时长(横轴)的变化。图(a)和(b)所统计的分别是实测样本和低噪声样本  
Fig.7Variations of $\alpha$ (dashed curves）and γ（solid curves）of a partial BP sample set accumulated during a hypothetical observation time D.Panels（a）and（b）are plotted respectively with observed and low-noise samples.Dotted curves show the temporal variations of $\log _ { 1 0 } \phi$

# 2.6 误差分析

对于中等规模的亮点，获得的样本比较完整，频数曲线的中段较为光滑，较好地体现了亮点按照尺度呈幂律分布的关系。但是，实测频数分布曲线的两端与幂律分布的偏差较大。这些偏差既有物理本质的因素，也有观测造成的系统误差。研究中的误差主要产生于对亮点的识别过程。

亮点频数分布的右端代表样本中规模较大的级别 $( \gtrsim 1 0 ^ { \prime \prime } )$ )。图6中各分布的右端均有较大的噪声，并与幂律分布有明显的偏差，这可能有3方面的原因。（1)这种偏差有可能是本征性的，规模大的耀斑有可能遵守指数分布而不是幂律分布。受样本容量的限制，在本文的数据基础上尚无法判断这种可能性的真伪。（2)由于单个活动区大规模耀斑的数目非常有限，频数参差不齐，不能获得可信的频数密度。若要获得大耀斑的准确统计规律，需要对大量活动区进行统计，大幅度增加样本容量。但是，由于幂律分布的无标度性，无论样本容量有多大，其中最大规模的个体数目总是很有限的，所以频数分布的最右端也总是较为离散。（3)大耀斑效应。发生大耀斑时，对视场中各种尺度亮点的频数统计都不准确。（a)对于有一部分面积超出视场的大尺度亮点，所测量的内容比实际内容小。这在一定程度上造成了图6中曲线的右端比幂律分布高并突然终止的情况。如果使用全日面观测资料，可以基本消除此类误差。（b)多个临近的亮点区域可能发生粘连并被识别为同一个区域。改进本区域识别算法的难点和目标是使其能够在降低大尺度增亮区域噪声的同时又能保留小尺度区域的精细结构，从而对尺度迥异的亮点进行同等准确的测量。（c)由于所使用的观测数据在爆发区域常出现大面积饱和现象，低估了其光通量，实测亮点光通量的分布规律与面积的分布规律非常相似，并不是真实分布的准确反映。

各频数分布曲线的左端代表尺度小、时标短的亮点，它们的频数密度比幂律拟合值都明显偏低，且二者的差异随着规模的减小而增加，如图6(c)和(d)。例如，实测样本中最小尺度的亮点 $( \sim 0 ^ { \prime \prime } . 2 4 )$ 的频数只有幂律拟合值的 $2 2 \%$ 。这主要由采样过程中的误差造成。首先，该时间序列的低时间分辨率导致了低采样率。由于该时间序列的间隔时间（120 s)较长，对海量小尺度、短时标个体有较高的漏检率[22]。其次，大耀斑效应也影响了对亮点的统计。散点图2(b)表示瞬时容量 $n$ 与瞬时光通量 $\phi$ 的关系。活动瞬间(方片)并不遵守在宁静瞬间(十字)表现的线性关系(虚线)，其瞬时容量偏小，这可能因为大耀斑的发生掩盖了临近的小尺度亮点。该误差对2.3\~2.5节中的分析也可能有一定影响。

# 3结论与展望

# 3.1结论

本文使用二维区域识别算法，在太阳光学望远镜对 NOAA10930 所观测的Ca ⅡIH时间序列中，获得了一个容量为 $2 . 9 9 \times 1 0 ^ { 5 }$ 的低色球层亮点样本，分析了其瞬时频数分布的基本特征、时变规律和累积样本分布。主要结果如下：

(1)亮点的尺度服从幂律分布。样本尺度的实测频数与幂律的离散系数 $\sigma ( \zeta )$ 仅为 $4 \%$ 。亮点的瞬时分布也基本符合幂律分布并满足自相似性;

(2)该实测样本尺度的 $\gamma$ 为1.97，剔除大耀斑之后的低噪声样本的 $\gamma$ 为2.12;

(3)在跨度为124小时的观测时间内，样本集的 $\gamma$ 并没有收敛。 $\gamma$ 是一个在观测积累中呈锯齿状变化的过程：在平静时段缓慢升高，在活动瞬间突然降低；

(4)累积 $\gamma$ 如此变化的原因是亮点瞬时分布的幂指 $\gamma ( t )$ 与瞬时子集的总光通量 $\varPhi ( t )$ 呈反比。在样本中剔除大尺度( $\left( L > 8 ^ { \prime \prime } \right)$ )个体后，仅含有中、小尺度亮点的低噪声样本仍服从上述规律。太阳活动不仅产生中、大尺度的增亮区域，还对亮点的频数分布产生全局性的影响，引起瞬时 $\gamma$ 的降低;

(5)小尺度亮点的瞬时数密度及调幅指数 $\alpha$ 随着活动区的衰减而降低;

(6)亮点的产生率及其信噪比随着尺度的增加而减小。海量微小规模亮点持续的发生可能是加热高层大气的一种稳定而可观的能量来源，例如，尺度小于 $4 ^ { \prime \prime }$ 的亮点产生的光通量在样本总光通量中占的比例达到了 $5 3 . 2 3 \%$ 。

# 3.2展望

以下工作将有助于进一步揭示亮点分布特征的统计规律和形成机制。

(1)使用高时、空分辨率数据对小规模亮点的分布规律进行准确统计。历史上对亮点幂律分布的观测统计中，频数分布在低端的拐点往往由观测手段的阈值造成，并不是物理实质的反映。本文中，微小规模亮点的实测频数的确小于幂律分布，但是由于对小规模亮点获取的信息很不完全，无法对微小亮点频数与幂律的本征性偏离进行判断，也难以进一步估算其在大气加热中的贡献。只有使用高时间分辨率和衍射极限更小的观测设备，方能更准确地获得小规模亮点的分布规律，进一步了解微小规模能量释放在日冕加热中的作用。

(2)对低层亮点和磁场凝聚的空间分布进行比较。活动区的浮现、爆发和衰减，实质上是磁场结构和能量上传和扩散的过程。而宁静区没有大尺度磁场凝聚的产生和消失。结合光球磁场资料中磁场凝聚的形成和衰减过程，分析活动区不同演化阶段以及宁静区亮点的分布特征和演化方式，可以深入对磁场演化和能量传输过程的理解。

(3)对低层大气中各波段亮点的分布规律进行比对研究。目前对高层大气中活动能量幂律分布的研究已经覆盖了较宽广的波段和时标[1]，但是对低层大气中的亮点，尤其是色球层和过渡区亮点，所掌握的宏观分布规律还很有限。而光球亮点是具有特征尺度的[21,37]，并不满足无标度条件。对低层大气亮点分布规律的多波段比对研究，有助于了解能量释放机制随高度的变化。例如，亮点服从幂律分布的最低层次是什么？为什么能量的分布规律在该高度发生了变化？

(4)使用全日面、长时标的数据分析亮点分布规律随太阳活动水平的变化。本文仅在一个衰减的活动区狭窄的时空范围内，对亮点幂律分布随太阳活动的时变进行了有限的分析。在全日面、跨太阳周的范围内对亮点进行统计，一方面可以研究活动区的磁场演化影响日面上亮点空间分布的动态过程，另一方面可以研究幂律分布特征随太阳周的长时标变化规律。

致谢：谨以此文缅怀杨志良教授(1965\~2016)。“日出”卫星是由日本ISAS/JAXA主持，日本国家天文台、美国宇航局、英国STFC协作完成，并和欧洲空间局、挪威NSC共同操作的太阳观测设备。本研究使用了IDL语言、SSW软件包、ADS文献库和Kubuntu操作系统。

# 参考文献：

[1」 Datowe 1 A-lays  ue eneigy lange $1 0 { - } 1 0 0 \ \mathrm { k e V }$ [J].Solar Physics，1974,39(1):155-174.   
[2] Lin R P，Schwartz R A，Kane SR,et al. Solar hard X-ray microflares [J].The Astrophysical Journal，1984，283(1) : 421-425.   
[3] Dennis BR.Solar hard X-ray bursts [J]. Solar Physics，1985，100(1）:465-490.   
[4] Bai T.Variability of the occurrence frequency of solar flares as a function of peak hard X-ray rate [J]. The Astrophysical Journal，1993，404:805-809.   
[5] Crosby N B，Aschwanden M J,Dennis B R. Frequency distributions and correlations of solar Xray flare parameters [J]. Solar Physics，1993，143(2）:275-299.   
[6] Shimojo M，Shibata K. Occurrence rate of microflares in an X-ray bright point within an active region ［J]. The Astrophysical Journal，1999,516(2）: 934-938.   
[7] Veronig A，Temmer M，Hanslmeier A，et al. Temporal aspects and frequency distributions of solar soft X-ray flares [J]. Astronomy & Astrophysics，2002，382(3）:1070-1080.   
[8] Su Y，Gan W Q，Li Y P. A statistical study of Rhessi flares [J]. Solar Physics，2006，238 (1): 61-72.   
[9] McIntosh S W，Gurman JB. Nine years of EUV bright points [J]. Solar Physics，2005，228 (1):285-299.   
[10]Alipour N,Safari H. Statistical properties of solar coronal bright points [J].The Astrophysical Journal，2015，807(2): 175-183.   
[11] Aschwanden M J，Crosby N B，Dimitropoulou M，et al. 25 years of self-organized criticality: solar and astrophysics [J]. Space Science Reviews，2016，198(1） :47-166.   
[12] Wheatland M S，Sturrock P A.Avalanche models of solar flares and the distribution of active regions [J]. The Astrophysical Journal，1996,471(2）:1044-1048.   
[13]Wheatland M S.Flare frequency-size distributions for individual active regions [J].The Astrophysical Journal,2000，532(2）：1209-1214.   
[14] Perone D,Dendy R O,Furno I,et al. Nonclasscal transport and particle-field coupling:from laboratory plasmas to the solar wind [J]. Space Science Reviews，2013，178(2）: 233-270.   
[15] Hale G E. Solar magnetism [J]. Nature，1935，136(3444）: 703-705.   
[16] McIntosh S W，Wang X，Leamon R J，et al. Deciphering solar magnetic activity I:on the relationship between the sunspot cycle and the evolution of small magnetic features [J].The Astrophysical Journal，2014，792(2）：12-30.   
[17]Rieger E，Kanbach G，Reppin C，et al. A 154-day periodicity in the occurrence of hard solar flares？［J]. Nature，1984，312:623-625.   
［18］赵明宇，陈军权，刘煜，等．太阳活动峰年和谷年期间黑子群与耀斑的统计分析［J]．中国 科学：物理学 力学 天文学，2014，44(1)：109-120. Zhao Mingyu，Chen Junquan，Liu Yu，et al. Statistical analysis of sunspot groups and flares for solar maximum and minimum [J].Scientia Sinica:Physica Mechanica Astronomica，2014,44 (1):109-120.   
[19］牛俊，方涵先，翁利斌．太阳活动与热层大气密度的相关性研究［J].空间科学学报， 2014,34(1) : 73-80. Niu Jun，Fang Hanxian，Weng Libin. Correlation between solar activity and thermospheric density [J]. Chinese Journal of Space Science，2014，34(1） : 73-80.   
[20]Lu E T,Hamilton R J.Avalanches and the distribution of solar flares [J]. The Astrophysical Journal Letters，1991，380(2）:L89-L92. bright points observed with the new solar telescope [J]. The Astrophysical Journal Letters, 2010,725(1) : L101-L105.   
[22] 李小波，杨志良，张洪起．基于三维区域标记对太阳活动区低色球层亮点的统计分析 [J]．北京师范大学学报（理），2016，52(5)：542-549. Li Xiaobo，Yang Zhiliang， Zhang Hongqi. Distribution of low-chromospheric brightpoints in a solar active region as observed by region-labeling ［J]. Journal of Beijing Normal University (Natural Science），2016,52(5） : 542-549.   
[23] 冯恒强，曹行健.行星际磁通量绳尺度的幂律谱分布［J].天文研究与技术——国家天文 台台刊，2010，7(1)：1-7. Feng Hengqiang，Cao Xingjian. Power-law distribution of scale lengths of interplanetary magnetic flux ropes [J].Astronomical Research & Technology一 -Publications of National Astronomical Observatories of China，2010,7(1）:1-7.   
[24] Wheatland M S.Evidence for departure from a power-law flare size distribution for a smal solar active region [J]. The Astrophysical Journal，2010，710(2）:1324-1334.   
[25] Parker E N. The sun: the ultimate challenge to astrophysics [J].Advances in Space Research, 1998，21(1-2): 267-274.   
[26] Ilnidis S，Zhao J，Kosovichev A. Detection of emerging sunspot regions in the solar interior [J]. Science，2011，333(6045）: 993-996.   
[27] Bak P，Tang C，Wiesenfeld K. Self-organized criticality: an explanation of the 1/f noise [J]. Physical Review Letters，1987,59(4): 381-384.   
[28] Albert R，Barabási A L. Statistical mechanics of complex networks [J]. Reviews of Modern Physics，2002，74(1) : 47-97.   
[29] Daly E，Porporato A.Efect of different jump distributions on the dynamics of jump processes [J].Physical Review E,2010,81(6): 061133-1-061133-10.   
[30] Zirin H. The magnetic structure of plagues [C]// Athay R G. Chromospheric fine structure, volume 56 of IAU Symposium.Boston：Reidel，1974：161-175.   
[31] Li X B，Yang Z L，Zhang H.Formation of pores associated with the inflow of moving magnetic features [J]. The Astrophysical Journal，2015，807(2） : 160-174.   
[32] Hudson H S.Solar flares，microflares，nanoflares，and coronal heating [J]. Solar Physics, 1991，133(2):357-369.   
[33] Tu C Y，Marsch E. MHD structures，waves and turbulence in the solar wind: Observations and theories [J]. Space Science Reviews，1995，73(1）: 1-210.   
[34] Suzuki T K， Inutsuka S I. Solar winds driven by nonlinear low-frequency Alfven waves from the photosphere:Parametric study for fast/slow winds and disappearance of solar winds [J]. Journal of Geophysical Research，2006，111(A6): 06101.   
[35] 方锦清，汪小帆，郑志刚，等.一门崭新的交叉科学：网络科学（上）［J].物理学进展， 2007，27(3) :239-343. Fang Jinqing，Wang Xiaofan， Zheng Zhigang，et al. New interdisciplinary science: networks science [J]. Progress in Physics，2007，27(3）: 239-343.   
[36] 刘艳霄，杨云飞，林隽．太阳光球磁亮点的识别算法［J]．天文研究与技术，2014，11 (2): 145-150. Liu Yanxiao，Yang Yunfei,Lin Jun. A region-growth algorithm to recognize magnetic bright spots in the solar photosphere [J]. Astronomical Research & Technology，2014，11(2）:145-150.   
[37]Crockett P J,Mathioudakis M,Jess D B，et al. The area distribution of solar magnetic bright points[J]. The Astrophysical Journal Letters，2010,722(2）: 188-193.   
[38] Kalkofen W. Oscillations in chromospheric network bright points [J].The Astrophysics Journal, 1997，486(2) :L145-L148.   
[39] Bocchialini K，Vial JC,Einaudi G.Statistical analysis of a bright point observed simultaneously in two chromospheric and transition region lines by SUMER［C]// Wilson A，Fifth SOHO workshop:The corona and solar wind near minimum activity，1997，404:211-215.   
[40] Pérez-Suárez D,Maclean R C,Doyle JG,et al. The structure and dynamics of a bright point as seen with Hinode，SoHO and TRACE[J]. Astronomy & Astrophysics，2008,492(2): 575-583.   
[41] 卢小广.统计学教程［M].北京：清华大学出版社，2005：33-36.   
[42] Newman M E J. Power laws，Pareto distributions and Zipf's law [J]. Contemporary Physics, 2005，46(5):323-351.

# Temporal Variations of the Power-Law Distribution of Low-Chromospheric Bright Points in a Solar Active Region

Li Xiaobo $^ { 1 , 2 , 3 }$ ，Yang Zhiliang²， Zhang Hongqi3 (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 650011, China;   
2.Department of Astronomy，Beijing Normal University，Beijing 10o875，China，Email: zlyang@bnu.edu.cn;   
aboratoryof SolarActivity，National Astronomical Observatories，Chinese Academyof Sciences，Beijing1Oool2,China)

Abstract:The power-law distribution of the energy of flares and microflares is an important character of solar activities.Investigating its attributes and temporal variations helps to studythe transmissionof energyand the heating of the solar corona. In this observation，we study the temporal variations of the frequency distribution of low-chromospheric bright points（BPs），and probe the patern of energy release in low solar atmospheres.We utilize Ca II H X3968.5 monograms of NOAA AR 10930 acquired by Hinode/SOT and recognize BPs with a two-dimensional region-labeling algorithm.On the time sequence with a time span of $1 2 4 \mathrm { { h } }$ and a field-of-view of $2 0 2 ^ { \prime \prime }$ $4 \times 8 5 ^ { \prime \prime }$ .3,a sample of $2 . 9 9 \times 1 0 ^ { 5 }$ BPs is identified，with a numerical density of $2 4 . 1 5 \pm 6 . 3 4$ per square arcminute. The main results are summarized as folows:（1）The instantaneous frequency distribution of BP's scale ( $L = \sqrt { L _ { x } L _ { y } } ,$ ） virtually observes the power-law and self-similarity.（2）The value and signal-to-noise ratio of BP's production decrease with the increase of $\mathrm { B P ^ { \prime } }$ s scale. Numerous smallscale BPs could be a valid source of energy for the heating of upper atmosphere.For instance，BPs with a scale smaller than $4 ^ { \prime \prime }$ share approximately $5 3 . 2 3 \%$ of the sample's total light flux budget.(3） As the active region decays，the numerical density of small-scale BPs also decreases.（4）The distribution of the sample set's scale observes the power-law，with a dispersion index $\sigma ( \zeta )$ of $4 \%$ . The power-law index $\gamma$ of the observed and low-noise ( $L \leqslant 8 ^ { \prime \prime }$ ）samples are respectively 1.97 and 2.12.（5）However，within the observation time，the overall power-law index $\gamma$ does not converge. The relationship between the power-law index and the time-span of observation is serrated:in quiet times $\gamma$ gradually increases，while in active moments $\gamma$ decreases sharply. （6）The instantaneous $\gamma$ is reversely proportional to the instantaneous total light flux. Even after filtering largescale BPs $( L > 8 ^ { \prime \prime } )$ ），the low-noise sample，which contains only middle- and small-scale BPs，still shows such correlation.Thisquashes our initial suspicion that the numerical calculation of y is rigged by the injection of few large BPs into the sample pool；the observed relationship between large events and the dropping of y is intrinsic.Solar activities not only produces middle and large scale BPs，but also changes theentire pattrn of BP's distribution and hence lowers $\gamma$ ：

Key Words:Power-law distribution；Bright point；Solar flare；Solar chromosphere；Region labelling method