# DOI: 10.5846/stxb201608121653

王超军,吴锋,赵红蕊,陆胜寒.时间信息熵及其在植被覆盖时空变化遥感检测中的应用.生态学报,2017,37(21)：7359-7367.WangCJ，Wufoadlofagieebased on remote sensing images.Acta Ecologica Sinica,2017,37(21） :7359-7367.

# 时间信息熵及其在植被覆盖时空变化遥感检测中的应用

王超军}，吴 锋2,3,赵红蕊1，\*，陆胜寒1

1清华大学3S中心,清华大学土木工程系地球空间信息研究所，北京100084  
2中国科学院地理科学与资源研究所，北京100101  
3中国科学院农业政策研究中心，北京100101

摘要：基于遥感影像的变化检测是当前的研究热点,可为区域生态环境保育、资源管理与发展规划等提供决策支撑。目前遥感影像的变化检测多基于两个时相,不能充分地反映植被在时间维的连续变化特征。通过引入信息论,提出了利用时间信息熵来综合表征植被长时间序列的变化特征。研究以延河流域为试验区,基于MODIS/NDVI数据,应用时间信息熵方法来计算了2000—2010年该区域的植被覆盖变化信息,厘清了时空变化特征。研究结果表明,近10年延河流域的植被覆盖的变化以增加为主,占流域面积的 $8 0 . 7 \%$ ;植被覆盖明显增加的区域占流域面积 $1 3 . 9 \%$ ,主要分布在流域的东北部和东南部;植被覆盖减少的区域占比 $2 . 4 \%$ ,主要分布在流域的西部和西北部;严重减少的区域占比 $1 . 1 \%$ ,主要分布在流域的中部和西南部,是需要重点的生态恢复与治理区域。时间信息熵方法与回归分析法相比,能够更为客观地表征长时间序列植被覆盖的连续变化强度和变化趋势,可为区域生态环境的保护和管理提供更为科学的理论依据。

关键词：遥感;变化检测;时序数据;时间信息熵;植被覆盖

# Temporal information entropy and its application in the detection of spatiotemporal changes in vegetation coverage based on remote sensing images

WANG Chaojun’，WU Feng2,³， ZHAO Hongrui1 \*， LU Shenghan'   
13SCenter，singaUniersity；Istitutefomatics，DepartmentofCilEgineing，singaUniersty，ejingoin   
2Institute ofGeographicand Natural Resources Research，ChineseAcademyof Sciences，Beijing1Ol01,China   
3Center for Chinese Agricultural Policy，Chinese Academy of Sciences，Beijing 1Oo101,China

Abstract:Change detection based on remote sensing images is ahotresearch topic，which can provide decision support for regional ecologicalconservation,resourcemanagementanddevelopment plannng，etc.However,thecurrent studiesmostly focus on bio-temporal change detection，which cannot adequatelyreflect the continuous change characteristicsin time dimension.Inthis paper,through theintroductionof information theory，weproposeanovelmethodof temporalinformation entropy to characterize the long time change features of vegetation comprehensively.Taking Yanhe watershedas the study area andbasedon Normalized Diference Vegetation Index（NDVI）data，weused this method to calculate the change information of vegetation coveragein Yanhe watershed from 20O to 2O10andidentifieditsspatio-temporal change characteristics.Theresults showed thatthechange level of vegetation coverage in Yanhe watershed was mostly increased in this period,accounted for $8 0 . 7 \%$ of the total area.Obviously increased area accounted for $1 3 . 9 \%$ and mainly distributed in northeast and southeast of the watershed. Vegetation coverage decreased area accounted for $2 . 4 \%$ ，mainly distributed in the western and northwestern；Severely decreased area accounted for $1 . 1 \%$ ，mainly distributed in the central and southwest of the studyarea，where needs strict environmental management.Comparing with theregresionanalysis method，temporal informationentropycanbemoreobjectivelyinreflectingthecontinuouschange intensityand trendof vegetationcoveragein longtimeseries，whichcan provide scientifictheoreticalreferences fortheprotectionand managementofregionalecological environment. N

Key Words:remote sensing；change detection；time series data；temporal information entropy；vegetation coverage

基于遥感的地物目标检测是评价流域生态环境可持续发展的重要方法,其检测方法多样,检测精度仍有提高空间。土地利用变化、城市发展与生态环境变化等关系到人民生活和人类社会可持续发展的一系列问题,集中起来可归结为地物目标的变化检测问题[1-2]。遥感技术因具有时效性强、覆盖范围广、可重复观测等特点,可以定量监测地表发生变化的位置、过程和幅度[3],而成为变化检测最主要的技术手段。变化检测也是目前遥感应用研究中的热点[45]。遥感影像变化检测是从不同时期的遥感数据中,定量地分析和确定地表变化的特征与过程[6]。近些年来,相关学者相继提出了许多基于遥感影像的变化检测方法,并从不同的角度总结和归类。Singh等[7]根据是否对遥感影像分类将变化检测方法分为直接比较法和分类后比较法;Rensink等[8]根据研究对象层次的不同将变化检测方法分为基于像素级、基于特征级、基于决策级3个层次;Lu 等[9]按照采用数学方法的不同将变化检测技术分为算术运算法、变化法、分类比较法、高级模型法、GIS 集成法、视觉分析法和其他方法等七类。然而,从检测变化的本质策略上可将变化检测方法分为双时相变化检测和时间序列变化检测两大类[1,0]。前者是对两个时相遥感影像的变化检测,常用的方法有影像代数法、主成分分析法、变化矢量分析法、纹理特征分析法、马尔科夫随机场模型法、数据融合法等。如:邓小炼等[1]利用变化矢量分析法检测了华北平原的土地利用覆盖变化,取得了较好的效果;Tsarouchi等[12]人利用主成分分析法对TM 影像进行了变化检测处理和检测结果分析;Brozzone 等[13]将马尔可夫随机场模型法引入到变化检测中,提取了两时相影像中的空间邻域信息,结果显示对噪声起到了很好的抑制作用,优化了检测效果;Camps-Valls等[14]将数据融合法应用到多时相遥感影像的变化检测中,并客观评价了检测结果。

长时序植被覆盖的连续动态变化检测是生态学研究的重要领域和全球变化研究的热点。遥感技术与信息论的发展为时间序列的变化检测奠定了理论与数据基础。随着遥感数据的积累,长时间序列的遥感影像完整地记录了地表的变化过程。然而,目前的研究多为双时相变化检测[15]。通过时间序列变化检测可以充分地挖掘地物在时间维的变化信息,能够更好地反映其时空变化规律[16-17]。时间序列数据在地表覆盖变化的研究中有广泛的应用,其中最为直接的是监测地表植被的变化[18-19]。常用的植被覆盖变化检测方法主要有回归分析法、主成分分析法、傅里叶变换、小波变换等。回归分析法是考虑变量之间统计联系的一种重要方法,目前在植被覆盖的长时序变化趋势研究中应用最为广泛[20-21]。该方法的优点是计算过程简单、清晰,结果直观。但是要求研究对象需满足正态分布,且对遥感影像的噪声、误差规避能力较差[22];此外,该方法也很难客观地反映出长时序植被覆盖的变化强度特征。主成分分析法、傅里叶变换及小波变换类似,是通过对时序遥感数据进行影像变换或数学处理来增强变化信息,然后从变换分量中检测变化信息[23],此类方法可以有效地突出变化信息,能够较好地表达植被覆盖的宏观变化特征,但通过变换处理得到的影像意义不够明确，且对长时序植被覆盖在时间维的具体变化特征难以体现出来[24]。鉴于常用分析方法在长时间序列植被覆盖变化检测中存在的不足,本文通过引入信息论,提出了时间信息熵的概念及计算方法,希望为该领域的研究提供新思维、新方法。

时间信息熵是检测植被覆盖的时序变化特征的有效方法。“熵”最早起源于物理学,用来反映热力学系统的无序程度。1948年,香浓将这一概念引人通信领域并称之为信息熵,它反映了信息源的平均不确定性[25]。如今,信息熵已被广泛应用到生态学、地理学、社会科学等领域[26-27]。信息熵在遥感影像变化检测领域中也有较多的应用,但多是对两个时相变化信息的检测。如;李亮等[28]提出了利用遥感影像的像斑差熵来检测两期地表覆盖变化情况;任晖等[29]提出了土地利用异动熵来提取两期影像的土地利用变化信息,取得了较好的效果,且该方法对所用遥感数据源的配准精度、分辨率等要求较低。本文在已有研究成果的基础上,基于信息论,提出了利用时间信息熵方法来深入挖掘时间序列遥感影像的植被覆盖变化信息,综合、定量化地表征其在时间维的变化规律。并以延河流域为试验区,应用时间信息熵方法来客观反映延河流域长时间序列植被覆盖的时空变化特征，以期为该区域生态环境的保育和治理提供决策支撑。

# 1试验区概况与数据来源

# 1.1 试验区概况

延河流域生态环境问题较为突出，是陕西省生态环境建设的重点区域。延河是黄河的一级支流，发源于榆林市靖边县天赐湾乡，由西北向东南依次流经靖边县、志丹县、安塞区、宝塔区和延长县，最后在延长县南河沟乡凉水岸附近注入黄河，干流总长 $2 8 6 . 9 \mathrm { k m }$ 。延河流域位于陕北黄土高原腹地,地理位置 $3 6 ^ { \circ } 2 3 ^ { \prime }$ 一 $3 7 ^ { \circ } 1 7 ^ { \prime } \mathrm { N }$ ，$1 0 8 ^ { \circ } 4 5 ^ { \prime } \mathrm { - } 1 1 0 ^ { \circ } 2 8 ^ { \prime } \mathrm { E }$ ,流域总面积约 $7 6 8 7 \mathrm { k m } ^ { 2 }$ (图1)。地势起伏较大,海拔范围 $4 7 5 { - } 1 7 8 7 \mathrm { m }$ ,平均海拔 $1 2 1 3 \mathrm { m }$ 。截止2010年底，流域总人口约95万，其中农业人口占$6 1 \%$ ,GDP 总量为382.7亿元[30]。宝塔区是我国著名的红色旅游胜地。安塞区矿产资源丰富，石油产业是其支柱产业。该流域属于典型的暖温带大陆性半干旱季风气候,冬季寒冷干燥,夏季高温多雨。从西北向东南,降水、温度具有明显的梯度变化特征。年降水量少且季节分配不均匀,年均降雨量为 $5 2 0 \mathrm { m m }$ ,年均气温约8.8— $1 0 . 2 \%$ 。该区域的植被覆盖状况从南向北呈现着较为明显的变化[31]。科学、客观地反映其长时间范围植被覆盖的变化情况,可为该区域生态环境的建设和治理提供决策信息。

![](images/f9a726929c9ddb340488b13b407dabb1f751375cf0108037fb2ab53dd35a153f.jpg)  
图1延河流域位置示意图  
Fig.1Location of Yanhe watershed

# 1.2 数据来源

归一化植被指数(NDVI)是本研究的重要数据源,其能够很好地反映地表的植被覆盖情况。NDVI是遥感卫星监测植被应用最为广泛的参数[32]。研究中所采用的 NDVI数据来源于美国 NASA（htps://ladsweb.nascom.nasa.gov/data）的 MODIS 植被指数产品 MOD13Q1,空间分辨率为 $2 5 0 \mathrm { m }$ ,时间分辨率为16d。该数据产品统一采用SIN投影并已进行去云、辐射校正等预处理。研究所选用的时间范围为2000年2月到2010年12月。利用 MODLAND 提供的 MRT（MODIS Reprojection Tols）软件对该数据产品进行格式转换和投影转换,将HDF 格式转换为Tif格式,并将 SIN投影转换为WGS84/Albers Equal Area Conic 投影,重采样方法为最邻近法,重采样分辨率为 $2 5 0 \mathrm { m }$ 。然后利用MVC（MaximumValue Composites）法对各年23期数据进行最大值合成,来进一步消除云、大气和太阳高度角等因素对遥感影像产生的影响[33],得到试验区 2000—2010 年逐年的NDVI年最大值数据。

# 2研究方法

# 2.1 信息熵

信息熵(也称狭义信息熵)的计算方法基于离散型随机变量,其计算公式见式（1)。

$$
H ( X ) = - \sum _ { i = 1 } ^ { n } p ( x _ { i } ) \log _ { 2 } p ( x _ { i } )
$$

式中， $x _ { i }$ 表示随机变量 $X$ 的状态或取值; $p ( \boldsymbol { x } _ { i } )$ 为相应的概率。

连续型随机变量的信息熵不是对上式简单地取极限值,而是以微分熵的形式定义的[34],见式（2）。

$$
H ( X ) = - \int f ( x ) \log _ { 2 } f ( x ) d x
$$

式中， $f ( x )$ 为概率分布函数。

由上面的计算公式可知,求信息熵最关键的是确定概率密度或者具体的概率分布函数。Vasicek 等[35]提出了直接基于观测数据,而无需求概率密度函数或概率分布函数来计算信息熵的估计值,并证明了该估计值依概率收敛到理论值。将式(2)表示为式(3)的形式：

$$
H ( X ) = - \int f ( x ) \log _ { 2 } f ( x ) d x = - \int _ { 0 } ^ { 1 } \log _ { 2 } \left\{ { \frac { d } { d p } } F ^ { - 1 } ( p ) \right\} d p
$$

式中， $\boldsymbol { F } ^ { - 1 } \left( \boldsymbol { p } \right)$ 的微分可由样本点 $x _ { i }$ 处的斜率值来近似表达,见式（4)：

$$
h _ { i } ( m , n ) = { \frac { y _ { i + m } - y _ { i - m } } { 2 m / n } }
$$

式中,yi≤y≤…≤y,是样本点𝑥,…,x按照从小到大的顺序排列得到的。m为正整数,且0<m≤进而,信息熵可以表达为式（5）：

$$
H ( m , n ) = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } \ \log _ { 2 } { \frac { y _ { i + m } - y _ { i - m } } { 2 m / n } }
$$

Ebrahimi等[36]对上式进行了改进,并提出了新的计算方式,见式(6)：

$$
H _ { c } ( m , n ) = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } \ \log _ { 2 } { \frac { y _ { i + m } - y _ { i - m } } { c _ { i } \times m / n } }
$$

≤i≤mm其中,ci={2,m+1≤i≤n-m -m =y,i≤mYi+m=yn,i≥n-mn-i1+ ,n-m+1≤ i Tm

式中： $y _ { 1 } \leqslant y _ { 2 } \leqslant \cdots \leqslant y _ { n }$ ，是样本点 $x _ { 1 } , \cdots , x _ { n }$ 按照从小到大的顺序排列得到的。 $m$ 为正整数,且 $0 < m \leqslant { \frac { n } { 2 } }$ 。同时,证明了该方法依概率收敛到理论值 $H ( X )$ ,并且与式(5)相比有较小的偏差和均方根误差[37]。

# 2.2 时间信息熵

在借鉴信息熵概念的基础上,并结合遥感数据源的特点,本文提出了新的概念和方法,即时间信息熵、时间序列信息熵来充分挖掘植被覆盖在时间维的变化特征,表征其在某一时期的变化强度和变化趋势信息。

时间信息熵(temporal information entropy）以公式(6)为基础,用来反映植被覆盖在时间维的变化强度特征。应用时应考虑不同数据源的特点,以本研究中使用的 NDVI为例,其具体计算如式（7）：

$$
\begin{array} { l } { \displaystyle { \begin{array} { l } { \displaystyle { H = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \log _ { 2 } \Biggl ( \frac { \gamma _ { i + m } - \gamma _ { i - m } } { c _ { i } \times m \times \Delta / n } \Biggr ) } } \\ { \displaystyle { \left[ 1 + \frac { i - 1 } { m } , 1 \leqslant i \leqslant m \right. } } \\ { \displaystyle { c _ { i } = \left\{ 2 , m + 1 \leqslant i \leqslant n - m \right. \qquad } ; \qquad \left. \begin{array} { l } { \displaystyle { \mathcal { Y } _ { i - m } = \gamma _ { 1 } , i \leqslant m } } \\ { \displaystyle { \mathcal { Y } _ { i + m } = y _ { n } , i \geqslant n - m } } \end{array} \right. } } \end{array} }  \end{array}
$$

式中， $y _ { 1 } \leqslant y _ { 2 } \leqslant \cdots \leqslant y _ { n }$ ,是样本点 $x _ { 1 } , \cdots , x _ { n }$ 按照从小到大的顺序排列得到后得到的( $x _ { i }$ 即表示像元第 $i$ 年的NDVI值）。

下面对计算公式中的参数进行说明：

$\mathbf { \nabla } _ { m }$ 是“时间频率”因子,通过选取不同的 $\mathbf { \nabla } _ { m }$ 值( $m$ 为不超过 $n / 2$ 的正整数)可以反映研究对象在不同时间尺度上的变化特征。以本研究为例,由于试验区的植被覆盖情况是用每年 NDVI数据的最大值来反映的,故研究对象变化的时间尺度为年,计算时取 $m = 1$ ：

$\Delta$ 是"缩放系数”,表示对不同数据源进行标准化处理,使得时间信息熵的计算结果具有可比性（一般 $\Delta$ 值可以取为基础变化单位；以本文采用的NDVI数据为例， $\Delta$ 即由时序NDVI数据统计得到的基础变化单位$\Delta = 0 . 0 2$ 。

通过时间信息熵可以反映某一时段内植被覆盖在时间维的变化强度情况： $H$ 值越大反映出这一段时间内其变化强度越大,反之则表示变化强度越小。分析时间信息熵的计算方法,由于计算时对遥感观测数据进行了排序处理,结果只能反映出植被覆盖的变化强度信息,而无法体现出其在时间维的变化趋势信息。基于此，本文提出了时间序列信息熵(time-series information entropy)来反映植被覆盖在某一时间范围内的变化趋势信息。以研究中所用的 NDVI数据为例,具体的计算见式（8）：

$$
\begin{array} { c } { { H ^ { \prime } = \displaystyle \frac { 1 } { n } s g n \big ( x _ { i + m } - x _ { i - m } \big ) \sum _ { i = 1 } ^ { n } \log _ { 2 } \bigl ( \displaystyle \frac { \big | x _ { i + m } - x _ { i - m } \big | } { c _ { i } \times m \times \Delta / n } \bigr ) } } \\ { { { } } } \\ { { D V I \big \{ \not { \boxplus } \ ; s g n \stackrel { { \mathrm { \scriptsize ~ = ~ - ~ } } } { \not { \exists } \in } \Longrightarrow \stackrel { \not { \emptyset } \not { \emptyset } \not { \emptyset } \not { \emptyset } \not { \emptyset } } { \overbrace { { \forall } \not { \nabla } \not { \cdot } \var { \nabla } } } ^ { \pm } \not { \emptyset } \not { \emptyset } \not { \emptyset } , s g n ( \theta ) = \left\{ 0 , \theta = 0 \right. } }  \\ { { { } } } \\ { { { } } } \end{array}
$$

(式中， $x _ { i }$ 表示像元第 $i$ 年的N ;其他参数含义同上。

$H ^ { \prime }$ 值为正表示在某一时段内植被覆盖的变化呈增加趋势;反之则表示植被覆盖呈减少趋势。 $H ^ { \prime }$ 绝对值越大,表明增加(或减少)的趋势越明显。

利用上述时间信息熵、时间序列信息熵可以挖掘植被覆盖在时间维的变化特征,定量、客观地反映出长时序植被覆盖的变化强度和变化趋势信息。同时,在计算得到上述熵值的基础上,对其直方图进行分割,进而得到植被覆盖的变化等级分布图,可为区域生态环境的保育和治理提供更为方便、宏观的参考。

# 2.3线性回归分析法

目前的研究中多采用线性回归分析法来反映区域长时间序列植被覆盖的变化情况[21-22],本研究将新建立的时间信息熵及时间序列信息熵的结果与线性回归分析方法对比,以分析新方法的优势。

线性回归分析法以线性拟合得到的斜率值(slope)表达植被覆盖的变化强度和变化趋势。具体而言,斜率的绝对值越大,表示植被的变化强度越大,反之则变化强度越小;斜率值为正,表示植被覆盖呈增加趋势,反之则呈减少趋势。其计算方法见式（9）：

$$
{ \mathrm { s l o p e } } = { \frac { n \times { \Big ( } \displaystyle \sum _ { i = 1 } ^ { n } i \times { \mathrm { N D V I } } _ { i } { \Big ) } - { \Big ( } \displaystyle \sum _ { i = 1 } ^ { n } i { \Big ) } { \Big ( } \displaystyle \sum _ { i = 1 } ^ { n } { \mathrm { N D V I } } _ { i } { \Big ) } } { n \times \displaystyle \sum _ { i = 1 } ^ { n } i ^ { 2 } - { \Big ( } \displaystyle \sum _ { i = 1 } ^ { n } i { \Big ) } ^ { 2 } } }
$$

式中， $n$ 为监测年数; $\mathrm { N D V I } _ { i }$ 为任意像元第 $i$ 年的NDVI值。

2.4时间信息熵方法的验证比较

为验证本研究所提新方法的科学性和有效性,本文选取延河流域为试验区,将此方法与目前长时序植被覆盖变化检测中最常用的线性回归分析法进行比较。长时间序列植被覆盖的变化情况与区域的生态环境等密切相关。随着人类活动、气候变化等综合因素的影响,区域植被覆盖的变化情况越来越复杂;不仅有变化趋势比较明显的区域,还有变化趋势虽然不显著但在时间维的变化波动性较大的区域。对于长时间序列植被覆盖的变化检测而言,其重点内容是客观、科学地反映出研究区某段时间内的变化强度和变化趋势特征,进而为区域的生态环境建设和管理提供辅助决策信息。基于此,本文将以长时间序列植被覆盖的变化强度和变化趋势检测为标准,选取代表性样本点(表1、图6),来综合对比回归分析法与本文提出算法的计算结果,验证和说明时间信息熵方法的客观性和科学性（详细的内容见3.3节）。

http://www.ecologica.cn

表1代表性样本点的实际数据  
Table 1 Data of representative sample points   

<html><body><table><tr><td>年份 Year</td><td>样本点1观测值 Sample1</td><td>样本点2观测值 Sample2</td><td>样本点3观测值 Sample3</td><td>样本点4观测值 Sample4</td></tr><tr><td>2000</td><td>0.8269</td><td>0.3862</td><td>0.4734</td><td>0.4835</td></tr><tr><td>2001</td><td>0.8335</td><td>0.4126</td><td>0.4276</td><td>0.5009</td></tr><tr><td>2002</td><td>0.8369</td><td>0.5188</td><td>0.4154</td><td>0.5556</td></tr><tr><td>2003</td><td>0.8423</td><td>0.4157</td><td>0.4111</td><td>0.5112</td></tr><tr><td>2004</td><td>0.8436</td><td>0.5169</td><td>0.4246</td><td>0.5196</td></tr><tr><td>2005</td><td>0.8412</td><td>0.5072</td><td>0.4382</td><td>0.4825</td></tr><tr><td>2006</td><td>0.8387</td><td>0.5065</td><td>0.3373</td><td>0.5623</td></tr><tr><td>2007</td><td>0.8395</td><td>0.6021</td><td>0.3415</td><td>0.5015</td></tr><tr><td>2008</td><td>0.8426</td><td>0.5687</td><td>0.359</td><td>0.3969</td></tr><tr><td>2009</td><td>0.8433</td><td>0.6798</td><td>0.2956</td><td>0.5551</td></tr><tr><td>2010</td><td>0.8516</td><td>0.5907</td><td>0.3154</td><td>0.5643</td></tr></table></body></html>

# 3研究结果与讨论

# 3.1线性回归分析法的结果

利用线性回归分析法计算得到 2000—2010 年延河流域植被覆盖的变化情况。结果发现,此时间范围内研究区的植被覆盖总体呈上升趋势(图2)。流域北部和东南部植被覆盖的上升趋势较大,西南部的上升趋势较小。植被覆盖呈下降趋势的区域主要分布在流域的中部、西北部,且中部植被的下降趋势较大。

利用线性回归分析法的判定系数 $R ^ { 2 }$ 来检验所得斜率值的可信程度。计算结果发现,判定系数较大的区域主要分布在延河流域的北部、东南部,表明这些区域 NDVI回归分析斜率值有较高的可信度（图3）。判定系数较小的区域主要分布在流域的中部、西南部、西北部,表明这些区域的计算结果可信度较低,并不能客观地反映植被覆盖的变化情况。

![](images/ae67d684aa1a7dfd83d1910eb0ed9499d8f7de50401105fd59e9b42301c3b4a2.jpg)  
图2延河流域NDVI回归分析斜率值分布图Fig.2Distribution of slope values in Yanhe watershed

![](images/e1fccc28a9b19072bb64b08544d644f9864fe01b67dc6cf998ac452bce88b383.jpg)  
图3延河流域NDVI回归分析判定系数分布图  
Fig.3Distribution of determination coefficient in Yanhe watershed

# 3.2时间信息熵方法的结果

利用时间信息熵方法,计算得到 2000—2010年延河流域植被覆盖的时间信息熵、时间序列信息熵的分布情况，分别见图4、图5。

结果表明,此时间范围内流域的植被覆盖总体变化强度较大（图4)。延河流域的土地利用类型多为耕地、草地[30],近十年来由于“退耕还林、还草"等政策的实施,该区域的植被覆盖整体变化较大。而流域的南

部和西南部为林地,此时间范围内植被变化强度较弱,故其时间信息熵值也较小。本文研究结果与延河流域的实际情况相符合。

![](images/a7b7342198616e1cf4c2b83965b68e43b7f0317913d453d9f8a1da6c782ce7eb.jpg)  
图4延河流域植被覆盖的时间信息熵分布图

![](images/23d5cc0b58a42e79c684ff2360b3fbbffd5ad4e61a753de0d4475d5447f8a79a.jpg)  
图5延河流域植被覆盖的时间序列信息熵分布图Fig.5 Distribution of time-series information entropy in Yanhewatershed

研究表明,2000—2010年间植被覆盖呈增加趋势的区域主要分布在流域的北部、东北部和东南部,反映出这些区域的植被覆盖情况变好(图5)。而流域的中部、西北部和西南部的植被覆盖主要呈减少趋势,需要重视此类区域植被覆盖的保育工作,避免进一步恶化。

# 3.3 算法对比

以长时间序列植被覆盖的变化强度和变化趋势检测为标准，来综合对比回归分析法与本文提出算法的计算结果，验证和说明时间信息熵方法的客观性和科学性。研究依据延河流域植被覆盖的斜率值和判定系数的分布情况，分别从变化趋势平缓、上升和下降区域中，选取4个代表性样本点的NDVI数据（图6）。

对于上述样本点的实际数据(表1），分别利用线性回归分析法和本文提出的时间信息熵方法计算，所得结果如表2所示。

对于前3个样本点的实际数据，可以容易地看出，2000—2010 年间样本点1的NDVI数据变化非常平稳，样本点2增加的趋势明显，样本点3减少的趋势显著。

![](images/a2fec13049395d212c1c9fbb52dc35bbcecab1ec574cbced670c8fb4c7db6e44.jpg)  
Fig.4 Distribution of temporal information entropy in Yanhe watershed   
图6代表性观测点位置示意图  
Fig.6Location of typical observation points

相应的,从表2中,我们可以得到：由回归分析法得到的斜率值其判定系数较大。故利用线性回归分析法得到的斜率值有较高的可信度,能够反映出这段时间内的植被覆盖变化特征。同样的,本文提出的时间序列信息熵也反映出这些变化趋势：时间序列信息熵的绝对值越大,表示变化趋势越明显,且时间序列信息熵为正,表示植被覆盖呈增加趋势;反之，表示呈减少趋势。

对于样本点1、4,由回归分析法得到的斜率值相同,但其变化的波动性却有着很大的差别。对于植被覆盖的此种变化情况,线性回归分析法难以客观地反映出时间维的变化特征。以样本点4数据为例,利用该方法得到的斜率值的判定系数非常小（0.106）,也说明其可信度极小,不能客观地表征植被的变化特征。随着人类活动的加剧、气候变化等综合因素的影响,导致区域植被覆盖的变化波动较大、变化日趋复杂。以延河流域为例,统计图3中所示的判定系数分布情况，可知其中 $4 6 . 9 \%$ 的区域由回归分析法得到的斜率值其判定系数较小（小于0.65）,故利用回归分析法得到的斜率值难以客观地反映出此类区域的植被覆盖的变化规律。利用本文提出的时间信息熵方法能够很好地表征出此类变化特点：样本点4的时间信息熵值大,反映出这段时间内 NDVI变化的波动性较大;而样本点1的时间信息熵值只有0.3557,表明其变化的波动性非常小。综上,我们能够得到：本文提出的时间信息熵能够客观表征植被覆盖变化的波动性特征。

表2计算结果比较  
Table 2 Comparison of the results   

<html><body><table><tr><td>算法 Method</td><td>样本点1计算值 Results of sample1</td><td>样本点2计算值 Results of sample2</td><td>样本点3计算值 Results of sample3</td><td>样本点4计算值</td></tr><tr><td>斜率值 Slope values</td><td>0.0015</td><td>0.0237</td><td>-0.0156</td><td>Results of sample4 0.0015</td></tr><tr><td>判定系数 Determination coefficient</td><td>0.6558</td><td>0.7673</td><td>0.8015</td><td>0.0106</td></tr><tr><td>时间信息熵 Temporal information entropy</td><td>0.3557</td><td>3.7075</td><td>3.0973</td><td>2.5343</td></tr><tr><td>时间序列信息matonentroy</td><td>0.8204</td><td>2.0994</td><td>-1.5576</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>1.3599</td></tr></table></body></html>

综合以上分析,虽然线性回归分析法可以简单、直观地反映 2000—2010 年延河流域植被覆盖的变化情况。然而,由于该方法的前提假设是植被在一段时间范围内呈线性变化特点,对于植被变化波动较大的区域，线性回归分析法却很难客观、科学地表征这段时间内植被覆盖的变化特征。而本文提出的时间信息熵方法表征长时间序列植被覆盖变化信息有着独特的优势,能够客观地反映出研究区植被覆盖的变化强度和变化趋势特征。

更进一步的,通过对熵值分布的直方图进行分割,得到植被覆盖变化等级分布图,可为区域生态环境的保护和治理提供更为方便、宏观的参考。以延河流域为例，对反映植被覆盖变化强度信息的时间信息熵值分布图进行图像分割得到阈值 $\mathrm { A } = 1 . 6 8$ (来确定基本不变的区域);对反映植被覆盖变化趋势信息的时间序列信息熵进行分割得到阈值 $\mathrm { B } = 1 . 9 6$ （判定增加的程度是否明显） $\mathrm { \cdot } \mathrm { C } = - 0 . 7 3$ (判定减少的程度是否严重)来进一步反映研究区植被覆盖的变化等级。综合以上的内容,2000—2010 年延河流域植被覆盖变化情况可分为以下五种等级。

时间序列的遥感检测信息反映近10年流域生态环境偏好（图7）。统计结果表明，可以得到2000—2010年延河流域植被覆盖的变化等级以增加为主，占流域面积的 $8 0 . 7 \%$ ;明显增加的区域占流域面积 $1 3 . 9 \%$ ,主要分布在流域的东北部和东南部;植被覆盖减少的区域占比 $2 . 4 \%$ ，主要分布在流域的西部和西北部;严重减少的区域占比 $1 . 1 \%$ ，主要分布在流域的中部和西南部，是需要重点的生态恢复与治理区域;基本不变的区域占流域面积的 $1 . 9 \%$ o

# 4结论

本文利用时间信息熵方法计算了2000—2010年延河流域的植被覆盖变化信息，厘清了其时空变化特征。研究表明，延河流域的植被覆盖情况总体得到改善，反

![](images/08072f4492bc70ea43dafa9c42896cbceda7a539b8afda0f9afdd7a2d2e67c5a.jpg)  
图7延河流域植被覆盖变化等级分布图  
Fig.7Distribution ofvegetation change levels in Yanhe watershed

映出该区域的“退耕还林、还草"政策得到了有效实施,与延河流域的实际情况相符合。然而,流域的中部、西部的植被覆盖呈现恶化趋势,应重视此类区域植被覆盖的保育工作,加强生态环境的修复和治理力度。

本文提出的时间信息熵方法与回归分析法相比,能够更加客观地表征长时间序列植被覆盖的变化强度和变化趋势信息,可为区域生态环境的保护和管理提供更为科学的决策参考。研究成果可为长时间序列遥感影

像的植被覆盖变化检测提供新方法、新思路。研究旨在揭示某一时间范围内区域植被覆盖的整体变化特征，尚未涉及其中的“突变"问题,未来研究需要利用时间信息熵方法，以期揭示植被覆盖时空变化的影响机制。

# 参考文献（References）：

[1］周启鸣.多时相遥感影像变化检测综述.地理信息世界，2011，9(2)：28-33.  
[2] KenedyRE,TownsendPA，GrossJE，CohenWB，BolstadP，WangYQ，AdamsP.Remotesensingchangedetectiontolsfornaturalresourceersesadsdesofsaesotegot(7)：1382-1396.  
[3] 陈鑫镖.遥感影像变化检测技术发展综述.测绘与空间地理信息，2012，35(9)：38-41.  
[4] 冯文卿，张永军.利用多尺度融合进行面向对象的遥感影像变化检测.测绘学报，2015，44（10)：1142-1151.  
[5] 佃袁勇，方圣辉，姚崇怀.多尺度分割的高分辨率遥感影像变化检测.遥感学报，2016，20(1)：129-137.  
[6] Wilis K S.Remotesensing changedetection for ecological monitoring in United Statesprotectedareas.Biological Conse ation，2015，182:233-242.  
[7] SinghA.Revieartcledigitalchangedtetiochnquesusingemotelysnseddata.nteatioalJoualofRemoteSensing，989（6)：989-1003.  
[8] Rensink R A. Change detection. Annual Review of Psychology，2002,53：245-277.  
[9] AuthorDLC，MauselP,BrondizioE，MoranE.Changedetectiontechniques.IntermationalJouralofRemoteSensing，2O04，25（12）：2365-2401.  
[10] 殷守敬，吴传庆，王桥，马万栋，朱利，姚延娟，王雪蕾，吴迪.多时相遥感影像变化检测方法研究进展综述.光谱学与光谱分析，2013，33(12): 3339-3342.  
[11] 邓小炼.基于变化矢量分析的土地利用变化检测方法研究[D].北京：中国科学院研究生院(遥感应用研究所），2006.  
[12] Tsarouchi GM,Buytaert WMonitoringlandusechangesin theUperGangaBasin,IdiabyusingRemoteSensingandGStechiquesonandsat5 TM data//EGU General Assembly Conference Abstracts.Vienna，Austria:EGU,2013.  
[13] BruzoneL,rietFutoaticalisftdreeafoupeaeetetioEasactosoGecdeSensing，2000,38（3)：1171-1182.  
[14] Camps-VallGeChoaL,oarJj-areJ,artRaM.Keeasedframeorkforuliteporalduoeremotesensingdataclasificationandchangedetectio.IEEETransactiosonGeosienceandRemote Sesing,O08,46（)：835.  
[15] 马云飞，李宏.遥感变化检测技术方法综述.测绘与空间地理信息，2014，37(1)：132-134.  
[16] deJongR,VerbeltJenME,eunSredgsioblngdronrbtioofotrstterm change. Global Change Biology，2012，18(2）:642-655.  
[17] Jamali SJsoklurdJaqstJetectigngsingeatiotredssingtiesrissgmetatioeotesingfEnvironment，2015，156：182-195.  
[18] 张墨谦.遥感时间序列数据的特征挖掘：在生态学中的应用[D]．上海：复旦大学，2014：1-108.  
[19] DescleB,Bgertosetistalbddotegnt/1-11.  
[20] 宋富强，邢开雄，刘阳，刘志超，康慕谊.基于 MODIS/NDVI的陕北地区植被动态监测与评价.生态学报，2011,31（2）：354-363.  
[21] PuRL,GongP,TianY,MiaX，CaruthersRI，AndersonGL.UsingclasificationandNDVIdierencingmethdsformoitorigsparevegetationcoverage：acasestudyofsaltcedarinNevada，USA.InterationalJoualofRemoteSensing，2O08,29(14)：3987-4011.  
[22] 蔡博峰，于嵘.基于遥感的植被长时序趋势特征研究进展及评价.遥感学报，2009，13(6)：1170-1186.  
[23] 张家琦.遥感影像变化检测方法及应用研究［D].北京：中国地质大学(北京），2015.  
[24] EvansJP,GekenRClasifingrangeandveoteadcoveageusingaFourieropontbaseilaritymeasure.RemosingofEnvironment，2006，105(1）：1-8.  
[25] Shannon C E.A mathematical theory of communication.BellSystem Technical Journal，1948,27(3）：379-423.  
[26] ZhangY，YangZF,Li W.Analysesofurbanecosystembasedoninformationentropy.EcologicalModeling，2006,197(1/2）:1-12.  
[27] BrusteinR，MedvedAJM.Howblackholesbu：entanglemententropyevolutionforanevaporatingblackhole.PhysicalReviewD,015，91(8) :084062.  
[28] 李亮，舒宁，李雪.基于像斑差熵的遥感影像变化检测.遥感信息，2011,26(4)：38-41.  
[29]任晖.生态环境健康评价及关键参数定量遥感反演方法研究[D].北京：清华大学，2013：1-69.  
[30] 娄和震，杨胜天，周秋文，罗娅，侯立鹏.延河流域 200-2010年土地利用/覆盖变化及驱动力分析.干旱区资源与环境，2014，28（4)：15-21.  
[31] 王志杰.延河流域植被与侵蚀产沙特征研究[D].北京：中国科学院研究生院(教育部水土保持与生态环境研究中心),2014：1-141.  
[32] Jiang ZY，HueteAR,DidanK，MiuraT.Developmentofato-bandnhancedvegetationindexwithoutablueband.RemoteSensingofEnvironment，2008，112（10）：3833-3845.  
[33] FunkCC,BroMEItra-ssoalDangeprojectiosinaridfricaoteSesigofEvioent,,）：4-56.  
[34] 曲炜，朱诗兵.信息论基础及应用.北京：清华大学出版社，2005.  
[35] VasicekO.Atestfornormalitybasedonsampleentropy.Journalof theRoyalStatistical Society.SeriesB,976,38(1)：54-59.  
[36] EbrahimiN,PflughoeftK,SofiES.Twomeasuresofsampleentropy.Statistics&ProbabilityLetters，1994,2O(3）：25-34.  
[37] 张继国.降水时空分布的信息熵研究[D].南京：河海大学，2004：1-126.