# 面向GWAC系统的流星候选体识别算法

徐洋1,2，王竞1,2,³，黄茂海12，魏建彦1,2（1.中国科学院国家天文台空间天文与技术重点实验室，北京100012；2.中国科学院大学，北京100049;3．广西大学物理科学与技术学院广西相对论天体物理重点实验室，南宁530004）

摘要GWAC的超大视场每天可观测到数百个流星体，识别这些流星体可为流星的科学研究提供重要的科学数据。文章针对GWAC这一类超大视场测光巡天系统在流星识别时，遇到的不能有效区分流星与其他移动目标的挑战，设计和实现了一个流星候选体识别算法，该算法主要包含流星轨迹识别和光变曲线形态分析两个部分。识别算法对Mini-GWAC约两个月的图像进行处理，提取10.9万个移动目标轨迹，其中 $90 \%$ 以上属于非流星目标。分析午夜时间段内流星目标高斯拟合曲线的 $\alpha$ 参数，发现大部分单峰流星目标的光变曲线波峰随图像像素位置呈慢速变化趋势。综合流星的单帧特性、光变曲线的单峰结构特征和光变曲线的慢速变化特性进行过滤，最终得到 $4 . 1 \%$ 的高精度流星候选体。经过人工检查确认， $4 . 1 \%$ 的流星候选体中有 $8 5 \% { \sim } 8 7 . 3 \%$ 的目标符合流星的形态及亮度特征。

关键词流星;拉长轨迹识别；光变曲线；形态分析;GWAC中图分类号：TP311.1文献标识码：A文章编号：

# 1．引言

地基广角相机阵（Ground Wide Angle Cameras，简称GWAC，详见第2节）是中法合作天文卫星 SVOM[]的地基相关观测设备，主要科学目标是探测伽玛射线暴、引力波事件等爆发时对应的电磁辐射对应体。除了探测伽玛射线暴等暂现源，GWAC 约 5000平方度的超大视场同时能够探测到大量的移动目标，如流星、近地目标、小行星、彗星、飞机、空间碎片、卫星等。这些移动目标会影响伽玛暴等暂现源的探测效率，识别并过滤这些移动目标对GWAC系统具有重要意义。同时，国际上的许多组织在进行各类移动目标的研究，如国际天文联盟的流星数据中心致力于流星数据的收集和流星特性的研究[2，GWAC系统将会贡献出大量的流星数据。本文主要针对GWAC中的流星目标设计识别算法。

国际上有许多流星研究项目：NASA 资助建立的Cameras for Allsky Meteor Surveillance project（CAMS）项目[包含3个站点共60个录像相机，其目标是系统研究流星雨的特性及来源；日本的 SonotaCo4包含 25个站点共100个录像相机，已经向国际天文联盟的流星数据中心贡献了大量的流星雨数据；欧洲的European viDeo MeteorObservation Network（Edmond）流星数据库[5]汇聚了欧洲多个流星观测网的数据；克罗地亚的 Croatian MeteorNetwork（CMN）[基于廉价的监控相机和普通台式机构建面向科普教育的流星观测系统；加拿大Western 大学的Southem Ontario Meteor Network（SOMN）[7]主要关注厘米级流星体的探测；俄罗斯的天文科学望远镜阵Mini-MegaTORTORA（MMT）[8与GWAC 系统有着类似的科学目标，即探测短时标光学暂现源，MMT包含900平方度浅视场和100平方度的深视场，白光0.1秒曝光极限星等约11V，1.5年累计观测到约9万颗流星。

现有项目使用的流星识别软件如MeteorScan[1]、MetRec[11、UFO Capture[12]、AIM-IT[13]、Gural[14]和Vida[15]等，主要面向流星巡天项目进行设计，其图像的主要特点是：1）极限星等低（约5V星等)，视场中背景恒星的数目少，识别流星时干扰源少；2）帧频快（每秒曝光几十到上百帧)，拍摄的流星体轨迹出现在多帧图像中，每帧图像中包含一段轨迹，通过多段轨迹可计算出流星体的角速度；3）多站点观测，流星巡天项目通常包含少则两个多则几十个观测站点，联合两个及以上站点的观测数据，可以计算出流星体的位置、高度和线速度。流星巡天项目中流星识别的过程为：1）提取多帧图像中的轨迹线段，关联多个轨迹线段为一个目标；2）通过多站点数据，计算目标的位置；3）通过多个轨迹线段的位置计算目标的速度；4）通过目标的高度和速度信息对流星候选体进行过滤。王恩旺[1使用改进的帧差法对图像中拉长轨迹很短的空间运动目标进行检测。

GWAC图像的特点是：1）极限星等高（GWAC为16V星等，Mini-GWAC为12.5V星等)，图像中会有大量的背景恒星及移动目标；2）帧频慢（曝光10秒，读出5秒)，拍摄的流星出现在单帧图像中，通常表现为一段完整的拉长轨迹（见2.2节)，无法计算流星体的速度；3）目前GWAC项目仅有一个观测站点，无法计算流星体的位置和高度。由于GWAC 的图像和图像中流星的轨迹形态与现有流星巡天项目的有着本质的区别，因此现有流星识别软件或算法不能直接应用于GWAC的流星探测。

国际上与GWAC 有着类似科学目标的大视场测光巡天项目有 MMT[8]和Piof the Sky[17]，这两个项目中也没有可借鉴的经验：1）MMT 的曝光时间为0.1秒，其流星识别算法与流星巡天项目的类似；2）Piof the Sky 没有发表流星体识别的相关研究成果。

![](images/3b001907eab6d67e4604ddaa2a195b854e417fae9c39f423404332973cc1c33b.jpg)  
图1Mini-GWAC图像中各种类别的目标，其中上面部分是原始图像，下面部分是相邻图像相减后的结果。(1)为流星候选体；(2\~6)为不同类别的移动目标；(7)为望远镜视场边缘被遮挡后产生的假目标； (8)为流星的尾焰； (9)为热像列

Fig.lAllkindofjectsininGWAC,toppartofmageisoigalimage,ottmpartofmageisesiualimageofaacntiage (1) is meteorcandidate, (2\~6)are movingobjects, (7) is fake object, (8) is wake flame of meteor, (9) is hot column

![](images/e7ded2743d44c368b9a18fcef67847538c6a7bb52877f136d663119652e0bb15.jpg)  
图2典型流星示例，形态上中间宽两端窄，亮度上中间亮两端暗 Fig.2 The centerpart of meteoriswider and brighter than both ends

GWAC 系统的超大视场每天不仅能观测到数百个流星体，同时也能观测到几千个其他类型的移动目标，如流星、飞机、卫星等。如图1所示，为Mini-GWAC（见2.1节）图像中各种不同类别的移动目标，除(1)是流星候选体之外，其他为不同类别的干扰源。与其他移动目标相比，流星轨迹的典型特征为：1）持续时间短，普遍单帧出现；2）其轨迹在形态上中间宽两端窄，在亮度上中间亮两端暗（火流星例外)，如图2所示。

GWAC系统的流星体识别过程面临的挑战是：在无法依靠速度和高度信息准确区分流星体和其他移动目标的情况下，如何从大量的移动目标中找到流星体。文章将针对GWAC 的系统特性及其图像中流星的轨迹特征设计流星识别算法：1）针对流星的拉长轨迹和单帧特征设计流星轨迹识别算法；2）针对流星轨迹的亮度和形态特征，对流星候选体的形态特征进行分析，以进一步提高流星的准确率。文章在第二部分简要介绍GWAC 系统和分析GWAC系统中移动目标的轨迹特性，第三部分对流星轨迹识别算法和形态分析算法进行详细描述，第四部分简要介绍了算法的实现细节，第五部分对部分移动目标轨迹的形态进行统计分析，最后一部分总结了算法的优缺点，及对下一步工作的展望。

# 2．GWAC系统简介

2.1.GWAC观测系统

![](images/984f4c542cd94c1ab727c65ec0e88135289c49ea45cea0bc325938fa835b4ac3.jpg)  
图3GWAC系统，左边为Mini-GWAC，右边为GWAC Fig.3Image on the left is Mini-GWAC,and on the right is GWAC

GWAC 系统的建设包含两个阶段，分别是一期工程Mini-GWAC实验系统和二期工程GWAC，如图3所示

1）Mini-GWAC 的组成：共包含12台6厘米的宽视场望远镜,每个望远镜配备一台 $3 \mathsf { K } \times 3 \mathsf { K }$ 的CCD 相机,综合视场约 5000平方度，恒星探测极限星等约12.5V（10秒钟、5σ、无月夜)，于2014年10月建成，并于2015年10月正式开始观测。  
2）GWAC 的组成：共包含40台有效口径为18厘米的宽视场望远镜，每个望远镜配备一台 $4 \mathbf { k } \times 4 \mathbf { k }$ 高性能CCD 相机，综合视场约5000平方度，恒星探测极限星等约16.0V（10秒钟、 $5 \sigma$ 、无月夜)。现在已完成部分望远镜的调试，并在进行试观测。

Mini-GWAC 已经积累了大量的观测数据，文章使用 Mini-GWAC的数据进行流星识别算法的研究，并在后

续应用于GWAC。

# 2.2.Mini-GWAC系统移动目标轨迹特性分析

Mini-GWAC图像中的移动目标主要包含3类：飞机、流星和卫星（空间碎片），下面将简要分析这三类目标的特性。

表1飞机、流星和卫星的高度和线速度  
Table1 The height and speed of airplane,meteor and satellite   

<html><body><table><tr><td>最低高度(km)</td><td></td><td>最高高度(km)</td><td>最小线速度(km/s)</td><td>最大线速度(km/s)</td></tr><tr><td>飞机</td><td>6</td><td>12.6</td><td>0.08</td><td>0.3</td></tr><tr><td>流星</td><td>80</td><td>120</td><td>11</td><td>72</td></tr><tr><td>卫星</td><td>200</td><td>36000</td><td>3</td><td>7.78</td></tr></table></body></html>

1) 高度和速度特性

如表1所示，飞机、流星和卫星三类移动目标的高度和速度区间有着明显的差异，计算出高度或速度中的一项参数，即可区分移动目标的类别。GWAC系统目前为单站点观测，无法计算移动目标的高度或速度，因此无法利用高度或速度特性对移动目标进行区分。

# 2) 时间特性

MMT与Mini-GWAC使用相同型号的镜头，其在1.5年中累计观测到约9万颗流星，这些流星持续时间为0.1秒到2.5秒[9]。照此估算，流星在 Mini-GWAC 的图像（10 秒曝光5秒读出）中只能单帧出现。飞机、卫星等移动目标在飞出图像边缘前会持续存在，因此可以在多帧中连续出现。

# 3) 轨迹长度特性

图4所示为对表1中三类典型移动目标在Mini-GWAC单帧10秒曝光图像中轨迹长度的估算。可见在不同速度和高度时，这三类移动目标在图像中的轨迹长度存在交集，因此无法直接通过轨迹长度对这三类移动目标进行区分。

![](images/ff777b9874c060ae4822e8cf73ee07437fbf30cf3fdfd273b870e041e4ae29be.jpg)  
图4Mini-GWAC的一帧10秒曝光图像中，流星、飞机和卫星的轨迹长度估算，其中流星的长度按0.5秒持续时间估算，飞机和卫星的长度按10秒持续时间估算左图为流星与飞机的轨迹长度对比，右图为流星和卫星的轨迹长度对比Fig.4 The estimation of track length of airplane, meteor and satellite ina10 seconds exposure image of Mini-GWAC,the left picture shows the track length comparison of the meteor and the plane,and the right picture shows thetrack length comparison of the meteor and the satellite

# 4) 轨迹形态特性

Subasinghe[18l对CAMS 双站点观测的891颗流星进行了光变曲线和形状分析：1）光变曲线分析：光变曲线的形状有 $67 \%$ 的单峰目标，包括 $14 \%$ 的早峰类型， $42 \%$ 的对称类型， $1 1 \%$ 的晚峰类型；2）形状分析：单帧图像(110 帧/秒）中流星为类彗星状。流星在Mini-GWAC 图像中单帧出现，其轨迹也包含光变曲线和形状信息：1)

光变曲线：从Mini-GWAC 的图像中能够得到流星随位置变化的光变曲线，后文将会进行详细介绍；2）形状特征：Mini-GWAC 图像中流星的轨迹中间粗两端逐渐变细，其宽度仅为几个像素到十几个像素，采样不足，容易受噪声的影响，因此本文不对流星的形状进行分析。

# 3．流星候选体识别算法

# 3.1．流星轨迹识别

算法对时空连续的多张FITS图像 $I ( k )$ 进行处理，整体流程如图5所示，下面将着重对几个关键的步骤进行介绍。

![](images/a95154330da193777c53383639c816c65d4f70a578e70ecde92f5f7532bea525.jpg)  
图5流星轨迹识别算法的流程图 Fig.5 The flow chart of meteor track recognition method

1) 图像预处理

连续的两帧图像拍摄时间相隔15秒，图像之间 seeing 等环境因素的变化非常微弱，可直接对连续两幅图像进行相减操作：

对相邻的两幅图像相减，避免了天文数据处理流程中对暗场和本底的操作，同时也不用对图像进行去背景的操作。原始图像相邻素点之间是有关联的，且相邻图像之间有细微的局部噪声起伏（如热噪声、大气扰动等），为了降低环境因素对关键信息的影响，可对相减后的图像 $S ( k )$ 进行白化处理。 $S ( k )$ 的协方差矩阵为 $\pmb { R } ( \pmb { k } )$ ，白化处理可表示为：

$$
W ( k ) { = } R ( k ) ^ { { - } I / 2 } S ( k )
$$

相减后图像 $S ( k )$ 主要包含3部分内容：背景（像素值接近零）；残差信号（局部信号起伏）；真实信号（星变亮，移动目标等）。图像二值化过程包括：

1）对 $W ( k )$ 使用 $3 \sigma$ 原则去掉背景信息，计算均值 $E$ 和标准差 $D$

2）初始化阈值设为 $\scriptstyle { T = E + 2 D }$ ，使用阈值 $T$ 对 $S ( k )$ 进行二值化操作得到二值化图像 $B ( k )$

$$
B ( \pmb { k } ) = \left\{ \begin{array} { l l } { 2 5 5 , \ W ( \pmb { k } ) \geq T } \\ { 0 \ \mathrm { ~ , ~ } \ W ( \pmb { k } ) < T } \end{array} \right.
$$

3）如果公式(5)中霍夫变换操作没有得到线段集，且 $r { > } I O O$ ，则开始动态调整阈值 $T$

$$
T { = } E { + } 2 D { - } N ^ { * } 5 ( N \not \to \not \cup \bar { \mathbb { E } } \not \equiv \not \mathcal { X } )
$$

循环每次将 $T$ 的值减5，然后对图像进行二值化和线段提取操作。如果 $\scriptstyle \mathrm { \mathrm { T } } < 1 0 0$ 或者公式(5)找到线段集，则停止循环过程。

# 2) 移动目标轨迹识别

文章选用概率霍夫变换（progressive probabilistic hough transform，PPHT）[19]来对二值化图像进行线段探测。相比霍夫变换，概率霍夫变换计算速度快，且能直接算出线段的两个端点坐标。概率霍夫变换后，得到候选线段集：

$$
\scriptstyle { L ( k ) = P P H T ( B ( k ) ) }
$$

流星在 Mini-GWAC 图像中的轨迹宽度约几个像素到十几个像素。因此霍夫变换后，一个流星轨迹有可能被识别为多条线段。为去除冗余线段，文章对候选线段集 $L ( k )$ 进行融合，将相邻的多条线段合并为一条线段。文章综合采用线段中心距离、线段斜率和图像中心到线段的距离三个参数来判断线段的相似性，对这三个参数小于指定数值的线段合并为一条线段 $L _ { \theta }$ ， $L _ { \theta }$ 代表一个移动目标候选体 $\scriptstyle { O _ { \theta } }$ ，对线段集 $L ( k )$ 合并后得到移动目标候选集$O ( k )$ 。

# 3) 多帧过滤

Mini-GWAC图像中不仅包含流星，还包含其他的移动目标（如飞机、卫星等）。流星与其他移动目标的区别是：流星仅在单帧图像中出现（流星的持续时间为 $0 . 1 { \sim } 2 . 5$ 秒，Mini-GWAC单帧图像曝光时间10秒，读出时间5秒），而其他移动目标可能会在多帧图像中出现。因此，对合并后的移动目标候选集 $o ( k )$ 进行前后帧关联，可以过滤一部分非流星目标。

# 3.2.流星光变曲线形态分析

移动目标光变曲线从形态上可分为无峰目标、单峰目标和多峰目标三类，如图6所示。Subasinghe[18分析的流星样本中有 $67 \%$ 的流星是单峰目标，且其主要针对单峰目标进行光变曲线的形态分析。因此文章尝试对单峰目标的形态进行分析，以期进一步过滤非流星目标。由于流星在Mini-GWAC图像中主要为单帧出现，无法得到流星随时间变化的光变曲线，但是可以通过流星在图像上的拉长轨迹得到流星随图像像素位置变化的光变曲线，后文简称光变曲线。下面将简要介绍光变曲线的提取及单峰目标形态分析的关键步骤。

![](images/e141d472d54cfed48c50c0e0d42911bbb8d346b4f9b8a1b33c0c4d5002408d17.jpg)  
图6三类移动目标，左图为无峰目标，中图为单峰目标，右图为多峰目标 Fig.6 Three kinds of moving objects,left is no-peak object,center is single-peak object, right is multi-peak object

# 1) 光变曲线的提取

线段 $L _ { \theta }$ 与原始图像X轴的夹角为 $\scriptstyle \theta _ { \theta }$ ，对 $S ( k )$ 顺时针旋转 $\theta _ { \theta }$ ，使目标长轴在图像中处于水平位置，对目标进行矩形区域裁图得到如图6所示的窗口图 $S u b _ { \theta }$ 。对 $S u b _ { \theta }$ 沿图像 $\mathrm { \Delta Y }$ 轴方向对 $\mathrm { \Delta } \mathrm { X }$ 轴方向的流量强度进行求和，得到目标亮度随 $\boldsymbol { x }$ 的变化曲线：

$$
\begin{array} { r } { F l u x _ { x } = \sum _ { y } S u b _ { 0 } ( x , y ) } \end{array}
$$

# 2）峰值计算及多峰目标过滤

峰值计算过程参考 SExtractor[20中的多颗相邻恒星目标的解析过程。对光变曲线 $F l u x _ { x }$ 取与X轴平行的直线$\scriptstyle { \mathbf { y } = Y _ { \theta } }$ ， $\scriptstyle \mathbf { Y } _ { \pmb { \theta } }$ 从光变曲线 $F l u x _ { \theta }$ 的最大值开始，依次以 Stepy递减，直到最小值。每次递减后计算直线与光变曲线的交叉部分，交叉部分的个数即为峰值个数peakNum。如果峰值个数peakNum等于0，则代表该目标为无峰目标；如果峰值个数peakNum等于1，则代表该目标为单峰目标；如果峰值个数peakNum大于1，则代表该目标为多峰目标。

# 3) 光变曲线形态分析

文章采用高斯函数拟合的方式对光变曲线进行形状的量化，多个高斯函数叠加能更准确的描述目标的光变曲线，这里至多使用两个高斯函数对光变曲线进行拟合。光变曲线拟合函数如下：

$$
\begin{array} { r } { F l u x ( k ) = \sum _ { i = 0 } ^ { N } A _ { i } * e ^ { - \left( \frac { x - x _ { 0 i } } { \alpha _ { i } } \right) ^ { 2 } } , N = [ 1 , 2 ] } \end{array}
$$

用拟合后高斯函数的参数 $( A _ { i } , \pmb { x _ { 0 i } }$ 和 $\pmb { \alpha } _ { i }$ 分别代表第 $\mathrm { ~ i ~ }$ 个拟合曲线的高度、中值和峰值锐度）作为对目标光变曲线形态的量化参数。文章将在第5节对目标的光变曲线形态进行详细分析与讨论。

# 4．程序实现

文章使用 Python 和OpenCV对算法进行实现，在i7 4770k CPU上测试，每幅图像的处理时间不超过1秒，满足GWAC系统的实时探测的需求。算法实现的关键信息如下：

1）异常图像过滤：Mini-GWAC的单图像视场覆盖天区范围大，易受环境因素的影响。文章通过相邻图像相减后残差的方差和有效像素百分比这两个参数对图像进行过滤。

2）霍夫变换参数选择：移动目标轨迹经过二值化之后，有可能会形成多个线段。通过分析Mini-GWAC 图像中流星的特征，选取概率霍夫变换测参数为 $\scriptstyle \rho = 1$ 像素， $\scriptstyle { \Theta = 1 }$ 度，组成轨迹的子线段最小长度为10 像素，子线段间最大间隔为5像素，轨迹的最短长度为50像素。3）线段融合参数选择：对图像中多条线段，如果中心距离小于50，且线段斜率差小于5，且线段与图像中心的距离差小于150，则这些线段合并为一条线段。4）相邻帧线段集栈构造：对连续多帧图像产生的线段集 $L ( k )$ 缓存在一个堆栈中，用来过滤多帧出现的移动目标。对相邻的两个线段集，对一个线段集中的所有线段都与另一个线段集中的线段进行比较，如果两个线段的斜率之差绝对值小于5，则认为这两个线段是同一个目标的线段，即该目标是多帧出现的移动目标。5）峰值数量peakNum 的计算：首先对流量曲线进行中值滤波，滤波器的 kermelSize 选取目标长度的 $10 \%$ 。峰值计算过程 $S t e p _ { y } { = } F l u x _ { m a x } / { 1 0 }$ 。为过滤噪声带来的毛刺，限定相邻两个峰值的最大值之差应大于 $S t e p _ { y }$ 。6）光变曲线归一化：将光变曲线的长度和高度（亮度）都归一化到[0,1]之间。对于所有光变曲线，记最大长度为 $L _ { m a x }$ ，记最大高度为 $H _ { m a x }$ ；将所有光变曲线等比放大到长度为 $L _ { m a x }$ ；对所有光变曲线的长度除以 $L _ { m a x }$ ，完成长度归一化；对所有光变曲线的高度除以 $H _ { m a x }$ ，完成高度的归一化。7）拟合参数融合：对于单峰目标的拟合，有些目标 $\scriptstyle { O _ { I } }$ 使用一个高斯函数能有效拟合，有些目标 $O _ { 2 }$ 需要两个高斯函数才能有效拟合。对于 $\scriptstyle { O _ { I } }$ ，算法直接使用拟合的三个参数（A、 $\scriptstyle \mathbf { \lambda } _ { x _ { \theta } }$ 和 $\pmb { \alpha }$ ）描述其形态。对于 $O _ { 2 }$ ，算法将两个高斯函数的参数进行融合，以更准确地描述流星曲线的形态：对两个 $A$ 取最大值，对两个 $\scriptstyle \left| { \pmb x } _ { \pmb \theta } \right|$ 取均值，对两个 $\pmb { \alpha }$ 取最小值。

# 5．光变曲线形态特征分析

# 5.1.数据统计

文章对Mini-GWAC的131万幅图像（约两个月的数据量）进行分析处理，结果中各类目标的统计如表2所示：

1）样本选择：这里选择单像素（均值）信噪比大于等于5o的移动目标，总数约10.9万个。  
2） 按是否多帧出现统计：包含1.2万个单帧出现的目标和9.7万个多帧出现的目标。  
3）按光变曲线峰值个数统计：包含约2.5万个单峰目标、1.3万个多峰目标和7.1万个无峰目标。  
4）流星候选体：按照Mini-GWAC 系统中流星的单帧出现特性对移动目标进行统计，流星候选体约占总数  
的 $1 0 . 7 \%$ 。如果通过光变曲线的单峰特性进一步过滤，则流星候选体的数据量可降低到 $5 . 8 \%$ 。

表2Mini-GWAC不同类别的移动目标数量统计  
Table2 Statistic of different categories of moving objects in Mini-GWAC   

<html><body><table><tr><td>统计量</td><td>数量（个)</td><td>所占百分比</td></tr><tr><td>移动目标总数</td><td>108764</td><td>100%</td></tr><tr><td>单帧出现数量</td><td>11613</td><td>10.7%</td></tr><tr><td>多帧出现数量</td><td>97151</td><td>89.3%</td></tr><tr><td>单峰目标数量</td><td>24777</td><td>22.8%</td></tr><tr><td>多峰目标数量</td><td>13011</td><td>12.0%</td></tr><tr><td>无峰目标数量</td><td>70976</td><td>65.2%</td></tr><tr><td>单帧出现单峰目标数量</td><td>6275</td><td>5.8%</td></tr><tr><td>单帧出现单峰峰值参数α大于0.2的目标数量</td><td>5583</td><td>5.1%</td></tr><tr><td>单帧出现单峰峰值参数α大于0.2</td><td>4453</td><td></td></tr><tr><td>且拟合度R2大于0.7的目标数量</td><td></td><td>4.1%</td></tr></table></body></html>

为量化光变曲线的拟合精度，文章采用R-Square(R2)进行评估。表2中的 6275 个单帧出现单峰目标光变曲线高斯拟合结果R2的直方图如图7所示。其中有 $4 1 . 2 \%$ 的目标R2大于0.9；有 $8 1 . 8 \%$ 的目标R2大于0.7。由于数据处理时存在噪声的干扰，所以选择较低的R2值(0.7)来过滤拟合结果。

![](images/0f0c5ac4114471602c5ea169a20303bc7aa54993dfccb850ec0bef92d12bd62c.jpg)  
图7单帧出现单峰目标（6275个）光变曲线高斯拟合度R2直方图 Fig.7 The histogram of R2 of 6275 single-peak objects appeared in one frame

# 5.2.光变曲线形态分析

高斯拟合参数 $\alpha$ 代表移动目标光变曲线的波峰宽度： $\alpha$ 值越小，波峰越窄； $\pmb { \alpha }$ 值越大，波峰越宽。文章将基于 $\alpha$ 对单帧出现单峰目标的光变曲线进行统计分析。为了找到能在光变曲线形态上区分不同移动目标的参数，文章选择3个样本集，并对这3个样本集的波峰宽度值 $\alpha$ 进行直方图统计分析，这3个样本集分别是：

1）单帧出现单峰目标样本集，简称样本集1：其中大部分为流星，且包含少量的多帧未匹配成功的空间碎片、卫星、飞机等长时间持续存在的移动目标。其波峰宽度值 $\alpha$ 分布如图8。  
2）傍晚或黎明期间的单帧出现单峰目标样本集，简称样本集2：从1）中选择晚上9点之前和凌晨4点之后出现的目标，其中的目标类别与1）基本相同。其波峰宽度值 $\pmb { \alpha }$ 分布如图9所示。  
3）午夜期间的单帧出现单峰目标样本集，简称样本集3：从1）中选择晚上10 点到凌晨2点之间出现的目标，该时间段的天空处于地球的阴影区，除了自发光的目标（如流星、飞机等），很难观测到其他依靠反射太阳光才能看到的目标（如空间碎片、卫星等）；飞机等自发光的目标受限于速度，多为多帧出现，单帧出现的概率非常低；因此该样本集中的目标主要为流星，其波峰宽度值 $\alpha$ 分布如图10。

![](images/4ef8c6943e8fe73e91f73e60a0ac173a1b0eca25d21b5877928b7c27c8937b06.jpg)  
图8单帧出现单峰目标（6275个） $\mathfrak { a }$ 参数的直方图

![](images/e3ace58165aea15882890c17d95d4908674f55d8dd49dc2ef05ccc0494d74d65.jpg)  
Fig.8 The histogram of $\mathfrak { a }$ parameter of 6275 single-peak objects appeared in one frame   
图9晚上9点之前和凌晨4点之后，单帧出现单峰目标（2962个） $\mathfrak { a }$ 参数的直方图 Fig.9Before $9 \mathrm { p . m }$ .and after 4 a.m,the histogram of $\mathfrak { a }$ parameter of 2962 single-peak objects appeared in one frame

![](images/079170827aca043893fd50d75c58031b96a72979fef38f03785a57e663a356bc.jpg)  
图10晚上10点到凌晨2点之间，单帧出现单峰目标（1306个） $\mathbf {  { a } }$ 参数的直方图 Fig.10 Between $1 0 { \mathrm { p . m } } .$ and $2 \ \mathrm { a . m }$ ,the histogram of $\mathfrak { a }$ parameter of 1306 single-peak objects appeared in one frame

对这3个样本集 $\alpha$ 参数的直方图分布曲线分析如下：

1）分析图8：样本集1的分布曲线有两个峰值。这两个峰值代表两类目标：一类是亮度随图像像素位置快速变化的目标，简称亮度快速变化目标，其 $\alpha$ 参数小于0.2，占比 $10 \%$ ；一类是亮度随图像像素位置慢速变化的目标，简称亮度慢速变化目标，其 $\pmb { \alpha }$ 参数大于0.2，占比 $90 \%$ 。  
2）分析图9：样本集2的分布曲线在整体上与样本集1基本一致，但样本集2中的快速变化目标的比例比样本集1高。  
3）分析图10：与样本集1和样本集2相比，样本集3的分布曲线在两端的比例偏少，其在左边的快速变化部分也有一个很小的峰值，表明其中快速变化目标所占的比例非常少。样本集3中的移动目标主要为流星，因此流星中快速变化的个体非常少。

综合分析图8、图9和图10,发现大部分单峰值流星为亮度慢速变化的目标，依此条件对样本集1进行过滤，可以得到5583的流星候选体，约占所有移动目标的 $5 . 1 \%$ 。同时采用R2大于0.7的条件过滤后得到 $4 4 5 3 ( 4 . 1 \% )$ （20个目标，如表2所示。人工对这4453个目标进行检查，确认其中有3785个目标符合流星的形态及亮度特征，占比 $8 5 \%$ ；有104个目标处于图像边缘，图像中仅包含目标的部分轨迹，这些部分轨迹也符合流星的形态及亮度特征，占比 $2 . 3 \%$ ；剩下564个为低信噪比目标、天气原因导致的假目标、与流星形态类似的天体目标等，占比$1 2 . 7 \%$ 。因此算法的综合识别精度为 $8 5 \% { \sim } 8 7 . 3 \%$ 。

# 6．总结与展望

GWAC 的超大视场中每天会探测到大量的流星，有效的识别出这些流星能为世界流星研究提供大量的有效数据。目前在GWAC这一类超大视场测光巡天系统中进行流星识别，遇到的最大挑战是没有充足的信息来有效区分流星与其他移动目标。为了尽可能准确的识别出流星，文章设计和实现了一个面向GWAC这类系统的流星轨迹识别算法，同时对得到的流星候选体进行了光变曲线形态分析，结果总结如下：

1）识别算法对Mini-GWAC约两个月的历史图像进行处理，从中筛选出单像素信噪比大于 $5 \sigma$ 的移动目标约10.9万个；  
2）通过流星在Mini-GWAC 图像中的单帧出现特性，可过滤 $8 9 . 3 \%$ 的移动目标，剩余 $1 0 . 7 \%$ 的候选目标;  
3）大部分流星的光变曲线为单峰结构（见3.2小节），该特性可进一步过滤候选目标，剩余 $5 . 8 \%$ 的流星候选体;  
4）通过分析3个样本集光变曲线的 $\pmb { \alpha }$ 参数直方图，发现大部分流星为亮度慢速变化的目标。使用该特性和光变曲线拟合度R2进一步对候选目标进行筛选，最终得到 $4 . 1 \%$ 的流星候选体。  
5）人工对 $4 . 1 \%$ 的流星候选体进行检查，确认其中有 $8 5 \% { \sim } 8 7 . 3 \%$ 的目标符合流星的形态及亮度特征。

文章中筛选流星使用了光变曲线单峰结构和亮度慢速变化这两个特性，这两个特征仅能包含大部分流星，而漏掉一些流星（如光变曲线有多个峰值的流星）。但是通过这两个特征的过滤，最终得到的 $4 . 1 \%$ 流星候选体具有更高的准确度。

通过分析单峰目标的实际图像，我们发现一些移动目标（卫星、飞机等）的形状和光变曲线形态与流星非常相似，如果这些目标出现在图像边缘，有很大概率仅单帧出现，本文算法很难过滤这类非流星目标。论文下一步将会围绕三个方面对算法进行改进：1）增加对移动目标的形态分析方法，如对移动目标的形状进行分析，找到多个可量化的形态描述参数，以期进一步提升流星的识别数量和识别精度;2)GWAC 正在计划建设第二个站点，两个站点协同观测，可计算移动目标的高度信息，通过高度信息可过滤飞机和卫星等移动目标；3）GWAC 正在研制快帧频CMOS相机，图像曝光时间可达到0.1秒，将极大的增加移动目标的时间分辨率，可计算移动目标的速度信息。算法中加入高度和速度信息后，能更准确的区分流星与其他移动目标。

参考文献   
[1] B Cordier, Jianyan Wei, JL Atteia, S Basa. The SVOM gamma-ray burst mission.Physics, 2015,   
arXiv:1512.03323.   
[2] Jopek,Tadeusz Jan; Kauchova, Zuzana.IAU Meteor Data Center-the shower database: A status report. Planetary and Space Science, 2017,143(3-6).   
[3] JenniskensP, GuralPS,DynnesonL,etc. CAMS: Cameras for Alsky Meteor Surveillance to establish minor meteor showers.Icarus,2011,216(1):40-61.   
[4] SonotaCo.A meteor shower catalog based on video observations in 2O07-2O08.Journal of the International Meteor Organization, 2009, 37(2):55-62.   
[5] KornosLeonard,KoukalJakub,PifflRoman,TothJuraj. Database of meteoroid orbits from several European video networks.Proceedings of the International Meteor Conference, 2O13: 21-25.   
[6] AndreicZeljko,SegonDamir.The First Year of Croatian Meteor Network. Proceedings of the International Meteor Conference,2010:16-23.   
[7]BrownP, WerykRJ, KohutS,EdwardsWN, KrzeminskiZ. Development of an Al-ky Video Meteor Network in Southern Ontario: Canada The ASGARD System. Journal of the International Meteor Organization, 2010, 38(1):25-30.   
[8] Karpov, S.; Beskin, G.; Biryukov,A.; Bondar, S. Mini-MegaTORTORA Wide-Field Monitoring System with Subsecond Temporal Resolution: Observation of Transient Events. Stars: From Collapse to Collapse,Proceedings of a conference held at Special Astrophysical Observatory, 2O17:526.   
[9] Karpov S, Orekhova N,Beskin G,etc. Meteor observations with Mini-Mega TORTORA wide-field monitoring system. IV Workshop on Robotic Autonomous Observatories, 2016: 97-98.   
[10]Gural Peter. MeteorScan Documentation and User's Guide.1999.   
[11]Molau S,Gural Peter. A review of video meteor detection and analysis software.Journal of the IMO,2005,33: 15-20.   
[12]SonotaCo. UFOCaptureV2 user's manual.http:/sonotaco.com/soft/UFO2/help/english/index.html .   
[13]Gural Peter, Jenniskens P, Varros G. Results from the AIM-IT meteor Tracking System. Earth, Moon and Planets, 2004, 94 (1-4):541-552.   
[14]GuralPeter.A fast meteor detection algorithm. nternational Meteor Conference, 2016: 96-104.   
[15]VidaD, ZubovicD,SegonD, etc. Open-source meteor detection software for low-cost single-board computers. International Meteor Conference, 2016: 307-318.   
[16]王恩旺，王恩达．改进的帧差法在空间运动目标检测中的应用[J].天文研究与技术,2016,13(3):333-339. [17]MankiewiczL, BatschT, Castro-TiradoA.Pi of the Sky full system and the new telescope. II Workshop on Robotic Autonomous Observatories, 2014, 45:7-11.   
[18]SubasingheDilini, Campbell-BrownMargaret D,StokanEdward. Physical characteristics of faint meteors by light curve and high-resolution observations,and the implications for parent bodies.Monthly Notices of the Royal Astronomical Society, 2016, 457(2): 1289-1298.   
[19]JMatas, CGalambos,JKitler. Robust detection of lines using the progressive probabilistic hough transform. Computer Vision & Image Understanding, 2000,78(1): 119-137.   
[20]BertinE,ArnoutsS.SExtractor: Software for source extraction.Astronomy and Astrophysics Supplement.1996, 117:393-404.

# An algorithm of selection of meteor candidates in GWAC system

# Xu Yang1,2, Wang Jing1,2.3, Huang Maohai1,2, Wei Jianyan1.2

(1.Key Laboratory of Space Astronomy and Technology, National Astronomical Observatories,Chinese Academy of Sciences,Beijing 1Ooo12,China; 2.University of Chinese Academy of Sciences,Beijing 10oo49,China; 3.Guangxi Key Laboratory for Relativistic Astrophysics,School of Physical Science and Technology, Guangxi University,Nanning 53oo04,Peoples Republic of China)

Abstract: With its large field of view,GWAC can record hundreds of meteors every day.These meteors are valuabletreasures for some meteor research groups.It is terefore very important to accurately findallof these meteors. To address the challenge of precisely distinguishing meteors from other elongated objects in a GWAC-like sky survey system, we design and implement a meteor candidate recognition algorithm, including the recognizing and morphology analysis of the light curves of the meteor candidates.After processng the images of Mini-GWAC taken in two months, we detect 109,00o elongated objects in which more than 90 percent of objects are not meteor. By analyzing $\mathfrak { a }$ parameter of gaussian fiting curve of meteor target in midnight,we found that the wave crestof most single-peak meteor target changes slowly with the position of image pixel.Among the elongated objects,about $4 . 1 \%$ objects are identified as meteors with highconfidence,after the filtersbased upon an existence ina single frame,a single peak in the light curves, and a slow variation of the light curves.After manual examination, $8 5 \% { \sim } 8 7 . 3 \%$ of the $4 . 1 \%$ candidates were consistent with the shape and brightness of the meteor.

Key Words: meteor;elongated track recognition; light curve; morphology analysis;GWAC;