# 取向硅钢低温加热工艺中渗氮工序的实验与数值模拟研究

曾贵民¹ 罗海文1 李军²龚坚 黎先浩 王现辉3

1北京科技大学冶金与生态工程学院北京10083  
2 安泰科技股份有限公司功能材料事业部北京100081  
3首钢股份公司迁安钢铁公司迁安064404

摘要通过在实验室模拟取向硅钢的渗氮生产工序，实测了不同渗氮时间下的渗氮量，并通过 EPMA、FESEM等观察了渗氮后氧化层的变化、N 在硅钢带厚度方向的浓度梯度。根据实测的组织形貌和渗氮动力学特点，首次建立了针对取向硅钢的渗氮动力学模型，并成功地进行了数值模拟计算。研究结果表明：(1）取向硅钢带的平均N含量在渗氮初期增加缓慢，之后逐渐加快，直至90s时渗氮速率达到最大值之后保持恒定；在 $7 5 0 \ \mathrm { ^ { \circ } C }$ 渗氮 $2 ~ \mathrm { m i n }$ 时间内，在近表面 $0 . 0 4 ~ \mathrm { m m }$ 范围内存在显著的N浓度梯度；(2）脱碳退火后，取向硅钢的氧化层主要为层状氧化物，渗氮时氧化层被 $\mathrm { H } _ { 2 }$ 还原，层状氧化物转变为球状，氧化层的变化对渗氮动力学影响恒定；(3）分析了N 由气相穿过表面氧化层至铁基体的传质系数所遵循的可能模型，发现只有当传质系数遵循氧化层还原动力学模型时，即Avrami函数模型 $\mathrm { \dot { \bar { \mathbf { \rho } } } = 1 - \exp \left( - k t ^ { n } \right) }$ ，计算结果才能与实测的渗氮动力学特征高度吻合。

关键词 取向硅钢，数值模拟，渗氮，动力学，扩散

中图分类号TG142

文章编号 0412-1961(2017)00-0000-00

# Experimental Studies and Numerical Simulation on the Nitriding Process of Grain-Oriented Silicon Steel

ZENG Guimin ', LUO Haiwen ¹ LI Jun ², GONG Jian ³,LI Xianhao ³,WANG Xianhui ³ 1Schoolofmetallurgicalandecologicalengineering,UniversityofScienceandTechnologyBeijing,Beijingl08,China 2Functional Materials Branch,Advanced Technology and Materials Co.Ltd.,Beijing 10oo81,China 3 Qian'an Steel Corp.,Shougang Co.Ltd.,Qian'an O630oo,China Correspondent: LUO Haiwen, professor, Tel: (010)62332911, E-mail: luohaiwen $@$ ustb.edu.cn Manuscript received 2016-10-18，in revised form 2017-01-12

ABSTRACT Grain-oriented silicon steel (GOSS) is an important functional material used as lamination cores in various transformers. Its magnetic properties are strongly dependent on the sharpness of Goss texture, which is developed during the secondary recrystallization annealing of product.In order to save energyand reduce cut-down operation costs,Nippon steel first lowered the slab-reheating temperature from $1 3 5 0 { \sim } 1 4 0 0 \ ^ { \circ } \mathrm { C }$ to 1150 $^ { \mathrm { o } } \mathrm { C }$ and adopted the nitriding process to form nitride inhibitors before recrystallization annealing in 197Os. In this new process,nitriding is the critical process because itcontrols the size,distributionand volume fraction of nitride precipitates，which then determines the subsequent development of Goss texture.Although it is of great importance for good quality control of industrial GOSS product,unfortunately，a quantitative mathematic modeling on nitriding kinetics is stillin lack.In this work,nitriding kinetics were both measured experimentally and simulated by modeling.The N contents after various nitriding periods and N concentration gradient across thickness were both measured. It has been found that the $\mathbf { N }$ content increases slowly at the beginning of $6 0 ~ \mathrm { s }$ and then much more rapidly during nitriding. There exists a sharp $\mathbf { N }$ concentration gradient within the depth of 0.03 mm to the steel sheet surface,which diminishes after about $0 . 0 4 ~ \mathrm { { m m } }$ depth.With the different assumptions on N-transfer coeffcient from gas to the steel matrix,the first mathematic modeling on nitriding kinetics of GOSs has been successfully established and solved numerically.The simulation results suggest that only when the N-transfer coefficient, $f ,$ changes with time following the Avrami function, $f = 1 - \exp { \left( - \mathrm { k t } ^ { \mathrm { n } } \right) }$ ， the calculated nitriding kinetics are consistent with the measurements. Such an Avrami-type dependence results from the reduction kinetics of oxide layer on the surfaceof silicon steel sheet during nitriding, in which both plate-like and spherical oxides were observed at the beginning but most of them became spherical after nitriding.

KEY WORDS grain-oriented silicon steel, numerical simulation, nitriding,kinetics, diffusion

冷轧取向硅钢大量用于制造各类变压器的铁芯，它的磁性能决定了电能的输送和转换效率，因此对节能降耗有直接影响[。取向硅钢的磁性能与其二次再结晶退火过程中形成的 $( 1 1 0 ) { < } 0 0 1 >$ Goss织构有很大关系，只有形成位向正确的Goss 晶粒才能获得高磁感、低铁损的取向硅钢。众所周知，取向硅钢中抑制剂的类型、尺寸与体积分数对控制再结晶退火过程中形成位向准确的Goss 织构非常重要，不同的取向硅钢生产工艺采用了不同类型的抑制剂体系且获得方式也有所不同[1,2]。自1934 年Goss3]发明普通取向硅钢生产技术以来，传统的取向硅钢生产工艺以高的板坏加热温度(超过 $1 3 5 0 ~ \mathrm { ~ } ^ { \circ } \mathrm { C }$ )和钢材内生的MnS、AIN抑制剂为特征，该工艺能耗高、成材率低。为了大幅度降低能源消耗和提高生产率，目前多数大钢铁企业应用的低温板坏加热工艺，将板坏加热温度显著降低到 $1 1 5 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ，并通过冷轧板的渗氮处理与硅钢中的Al、Si形成(Al,Si)N等抑制剂，也即抑制剂由内生的MnS、AIN变为通过渗氮获得的各类氮化物。由于该方法可以大幅度地降低生产难度和生产成本，显著提高了生产效率和成材率[4.5]。新日铁八幡厂首先开发和应用该工艺后，其后在浦项、宝山等大型钢铁企业也都开发了类似的工艺技术并得到广泛应用。这种低温加热工艺区别于传统高温工艺的关键特征就是引入了渗氮，即通过渗氮获得(Al、SiN 抑制剂来代替高温工艺下获得的MnS、AIN抑制剂。渗氮工序中取向硅钢薄带渗入氮量的多少和分布，直接决定了所形成氮化物抑制剂的分布、数量与分数，从而影响了后续高温退火过程中Goss 织构晶粒的演变和取向，也就决定了最终的磁性能[6-9]。因此，取向硅钢工业生产时对渗氮工序所要达到的渗氮目标值要求很严格，其允许的波动窗口很窄，需要进行严格的工艺控制才能稳定达到目标值。而渗氮工艺中，渗氮温度、渗氮气氛和硅钢带的表面状态、厚度和成分等诸多因素均影响渗入的氮量与分布，但是目前还没有一个物理基数学模型来定量描述上述各因素对渗氮动力学的影响[10-12]。

因此，根据实测的渗氮动力学和渗氮过程中的硅钢表面氧化层的组织演变，本工作首次建立了可定量计算上述各因素对渗氮动力学影响的数学模型。该模型将有助于优化取向硅钢工业生产中的渗氮工艺参数，提高对渗入氮量的控制精度，从而获得更为稳定的产品磁性能。

# 1 实验方法

取向硅钢样品为实验室制备，通过 $5 0 \mathrm { k g }$ 感应炉冶炼获得化学成分为 $\mathrm { F e } { - 3 . 3 \% } \mathrm { S i } { - 0 . 0 0 8 9 \% } \mathrm { N } ($ 质量分数)的钢锭，将铸锭锻造成宽 $1 1 0 \mathrm { m m }$ 、厚度 $3 5 ~ \mathrm { m m }$ 的板坏，锻造开始温度为 $1 1 0 0 \mathrm { ~ \textdegree ~ }$ ，终锻温度为 $8 0 0  { \mathrm { ~ \textrm ~ { ~ ~ } ~ } }  { \mathrm { C } } \circ 3 5  { \mathrm { m m } }$ 厚度板坏加热至 $1 1 5 0 ~ \mathrm { ~ \textdegree ~ }$ 并保温 $3 0 \mathrm { m i n }$ 以上后，在 $1 1 0 0 \mathrm { ~ \textdegree ~ }$ 开轧，经过3\~5道次热轧至终轧厚度 $2 . 3 ~ \mathrm { m m }$ 左右，终轧温度要保证高于 $9 0 0 \mathrm { ~ \textdegree ~ }$ ；然后热轧钢带进行冷轧，冷轧前钢带在 $1 0 0 { \sim } 2 0 0 \ \mathrm { ~ } ^ { \circ } \mathrm { C }$ 温度预热，采用一次大压下率冷轧法，经5\~7道冷轧至 $0 . 3 0 \mathrm { m m }$ 厚，冷轧过程中进行3次 $1 0 0 { \sim } 2 0 0 \ \mathrm { ~ \textdegree ~ }$ 时效处理。在渗氮前先进行氧化脱碳处理，脱碳温度为 $8 5 0 \mathrm { ~ \textdegree C }$ ， $7 5 \% \mathrm { H } _ { 2 } \substack { + 2 5 \% N _ { 2 } ( }$ (体积分数，下同)混合气体通过水温 $7 0 \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ }$ 的水浴，以将水蒸气带入炉膛进行脱碳，脱碳时间 $3 \mathrm { m i n }$ ；随后脱碳薄板在温度 $7 5 0 \ \mathrm { { ^ \circ C } }$ 和 $1 5 \% \mathrm { N H } _ { 3 }$ 和 $8 5 \% \mathrm { H } _ { 2 } \mathrm { + } \mathrm { N } _ { 2 }$ (其中 $\mathbf { H } _ { 2 } { : } \mathbf { N } _ { 2 } { = } 3 { : } 1 \$ 的气氛下进行渗氮实验，渗氮总时间为 $1 2 0 \mathrm { s } _ { \circ }$ 在 $6 0 { \sim } 1 2 0 ~ \mathrm { s }$ 时间内，每隔10s取出一片样品(样品尺寸为 $1 0 0 \mathrm { m m } { \times } 3 0 \mathrm { m m } )$ ，按照GB/T20124-2006规定的惰性气体熔融热导法，测定渗氮不同时间后样品的N含量。将渗氮实验获得的的样品横截面(厚度方向)按照标准程序经过磨光和抛光，不经侵蚀直接在 FEIQuanta450 场发射扫描电镜(SEM)和 Oxford X-Max SN:54705 能谱仪(EDS)下观测氧化层形貌，并通过

EPMA-1720H 电子探针(EPMA)对表面渗氮层的成分变化进行分析。渗氮动力学的模拟采用软件ThermoCalc $2 0 1 5 \mathrm { a } ^ { [ 1 3 ] }$ (包括 TC 热力学计算模块和DICTRA动力学计算模块)，使用的热力学和动力学数据库分别为TCFe8和MOBFe3。

# 2 实验结果

# 2.1不同渗氮时间的渗氮量

渗氮过程中，在 $6 0 { \sim } 1 2 0 ~ \mathrm { s }$ 中，每隔10s所测得的样品 $\mathbf { N }$ 浓度如图1所示。从图中可知，渗氮 $6 0 \mathrm { ~ s ~ }$ 时，N含量由初始的 $0 . 0 0 8 9 \%$ 增加到 $0 . 0 1 5 \%$ (质量分数，下同)，增N平均速度约为 $1 0 ^ { ^ { - 6 } } \ \mathrm { s } ^ { - 1 }$ ；而在 $9 0 \mathrm { ~ s ~ }$ 时，N含量增加到 $0 . 0 2 1 \%$ ，增N平均速率略有增加，约为 $2 \times 1 0 ^ { - 6 } \ \mathrm { s ^ { - 1 } }$ ；至 $1 2 0 \mathrm { ~ s ~ }$ 时N含量增加到 $0 . 0 3 5 \%$ ，增 $\mathbf { N }$ 平均速率增加到 $4 . 7 \times 1 0 ^ { - 6 } \ \mathrm { s } ^ { - 1 }$ 。因此，渗氮动力学随着渗氮时间的延长呈现出一种不断加速直至恒定的趋势。

![](images/6898ae8f8443e1cf92c344496f76d4110926843ecbf8292743f420fa0f8145af.jpg)  
图 $1 7 5 0 \ \mathrm { ^ { \circ } C }$ 渗氮时取向硅钢薄带的实测渗N量与渗氮时间的关系

Fig.1 Measured N contents of grain-oriented silicon steel sheet after nitriding for various periods at $7 5 0 \ \mathrm { { ^ \circ C } }$

图2为取向硅钢薄带横截面沿着厚度方向EPMA线扫描的结果。从图中可以看出，脱碳退火后，基体中的N浓度在一恒定值附近波动，无浓度梯度；而在渗氮120s后，在硅钢带表面层N浓度呈现一个显著的浓度梯度，越靠近钢带中心处N浓度下降越缓，至距离表面约 $0 . 0 4 \mathrm { m m }$ 时， $\mathbf { N }$ 浓度降低至基体初始N浓度左右而不再变化。

![](images/55749c5fdd29557e2035e7f0870ae29d3449e7b0a72e1123794598e1ad9557af.jpg)  
图2渗氮不同时间硅钢薄带厚度方向N含量变化的EMPA线扫描结果

Fig.2 EPMA line analysis of Nconcentration gradients across the thickness of steel sheet before and after nitriding

# 2.2硅钢带脱碳退火后氧化层形貌

图3为经过脱碳退火和渗氮120s硅钢带横截面积的组织及EDS分析结果。脱碳退火后在硅钢带表面形成以 $2 { \sim } 3 ~ \mu \mathrm { m }$ 厚的氧化层，表面处以球状形貌为主，而靠近基体内部以层状形貌为主(图3a)。当渗氮 120s时，在氧化层与基体界面处靠近基体侧的氧化物形貌从层状逐渐演变为球状(图3b)。通过EDS 分析，可知该片层状和球状氧化物应为Fe、Si的氧化物(图3c和d)。关于取向硅钢带脱碳退火过程有过许多深入的研究，一般认为氧化膜的形成主要是由于Si和O的亲和力强于Fe 而优先氧化形成的。如王若平等[4研究了不同气氛下的渗氮过程，运用辉光光谱仪测得该氧化膜主要由 $\mathrm { F e O } { + } \mathrm { S i O } _ { 2 }$ 构成，并且在渗氮后氧化膜厚度减少 $20 \%$ ；Toda 等[15]研究了钢带表面和亚表面的氧化层结构，认为其由外向内分别由 $\mathrm { F e S i O _ { 4 } }$ 球状和片状 $\mathrm { S i O } _ { 2 }$ 颗粒构成；宋惠军等[1的研究表明，脱碳退火后的氧化膜主要由FeO 和 $\mathrm { S i O } _ { 2 }$ 组成，并且对渗氮起阻碍作用；严国春等[17的研究表明，脱碳后的氧化物主要由FeO 和 $\mathrm { S i O } _ { 2 }$ 组成，但是他们发现氧化层对取向硅钢N 含量的增加有着明显的促进作用；Jung 等[18]使用透射电镜(TEM)详细研究了取向硅钢脱碳退火后形成的氧化层，确定了该氧化层中氧化物主要为 $\mathrm { S i O } _ { 2 }$ 和 $\mathrm { F e } _ { 2 } \mathrm { S i O } _ { 4 }$ ，且形貌、分布和成分皆与本实验结果一致，他们的实验结果更为让人信服，因此推测图3中的氧化层中也是以 $\mathrm { S i O } _ { 2 }$ 和 $\mathrm { F e } _ { 2 } \mathrm { S i O } _ { 4 }$ 为主的氧化物。从图1可知，在0\~90s内N含量增加缓慢，随后增加速度逐渐增大，而在渗氮后期有部分氧化物由片层状转变为球状，同时氧化层还由于失氧而变得疏松，呈海绵铁状，这和低碳钢热轧钢板的氧化层在氢气中被还原的现象和机理一致[19-21]，因此推测脱碳退火后，所形成较致密的层状形貌的氧化物对渗氮有阻碍作用，而随着时间延长，氧化层被氢气还原变为疏松的海绵铁后，渗氮速率大幅加快。

![](images/9147c2de392f17f91e127ac65175bed6355d452fd1d9d3c848826b102a99bb46.jpg)  
图3冷轧取向硅钢薄带脱碳退火和渗氮后显微组织及EDS分析结果 Fig.3 Microstructures (a,b) and EDS analyses (c, d) on the surface of cold rolled grain oriented silicon steel sheet after both decarburization and nitriding

(a) after decarburization at $8 5 0 \ \mathrm { { ^ \circ C } }$ in the atmosphere of $7 5 \% \mathrm { H } _ { 2 } \substack { + 2 5 \% \mathrm { N } _ { 2 } }$ with the dew point of $7 0 \ \mathrm { ~ \textdegree C }$ for 3 min   
(b) after nitriding at $7 5 0 \ \mathrm { { ^ \circ C } }$ in the atmosphere of $1 5 \% \mathrm { N H } _ { 3 } { + } 8 5 \%$ （204号 $\mathrm { ( H } _ { 2 } \mathrm { + } \mathrm { N } _ { 2 } \mathrm { ) }$ for $1 2 0 \mathrm { s }$ （20   
(c) EDS analysis of inclusion in circle of Fig.3a   
(d) EDS analysis of inclusion in circle of Fig.3b

# 3数学模型的建立

# 3.1渗氮的原理

取向硅钢在脱碳退火后进行气体渗氮处理，气氛一般采取 $\mathrm { N H } _ { 3 } { + } \mathrm { H } _ { 2 } { + } \mathrm { N } _ { 2 }$ ，其渗氮过程可以分为3个过程：

$( 1 ) \mathrm { N H } _ { 3 }$ 从气氛中扩散到硅钢带表面； $( 2 ) \mathrm { N H } _ { 3 }$ 在硅钢带表面分解， $\mathrm { N H } _ { 3 } = \left[ \mathrm { N } \right] + 3 / 2 \mathrm { H } _ { 2 }$ ； (3)活性[N]原子越过硅钢带表面氧化层的阻碍至氧化层与基体的界面，然后再向硅钢带内部扩散。如示意图图4所示。可见在硅钢带表面分解所提供的N原子与接触硅钢带的表面和分解时间均有关系，所以在垂直于界面的方向上，气氛和硅钢带表面存在一定的浓度梯度， $\mathbf { N }$ 的传输通量 $J _ { N }$ 为[22]

$$
\mathsf { J } _ { \mathrm { N } } = f _ { 1 } \cdot ( \mathsf { c } _ { \mathrm { N } } ^ { \mathbf { g } } - \mathsf { c } _ { \mathrm { N } } ^ { s \mathbf { u r f } } )
$$

式中， $f _ { 1 }$ 为气相传质系数，与气体流动、温度等相关，单位为 $\mathrm { m / s }$ ; $\mathbf { c } _ { \mathrm { N } } ^ { s \mathrm { u r f } }$ 为钢表面N浓度，单位为 $\mathrm { m o l } / \mathrm { m } ^ { 3 }$ $\mathbf { c } _ { \mathrm { N } } ^ { \mathbf { g } }$ 为气氛中的 $\mathbf { N }$ 浓度，其单位为 $\mathrm { m o l } / \mathrm { m } ^ { 3 }$ ，由 $\mathrm { N H } _ { 3 }$ 的分解反应决定，可以通过下式计算[22]：

$$
\mathrm { c _ { N } ^ { g } = P _ { N H 3 } / ( P _ { H 2 } } ^ { 3 / 2 } ) \cdot C _ { 0 } \cdot \exp \left[ - \mathrm { Q _ { 2 } / ( R T ) } \right]
$$

式中，分解反应系数 $\mathrm { \Delta C _ { 0 } }$ 为 $1 . 1 { \times } 1 0 ^ { 8 } \ \mathrm { a t m } ^ { 1 / 2 } { \cdot } \mathrm { m o l } / \mathrm { m } ^ { 3 }$ ；分解反应激活能 $\mathrm { Q } _ { 2 }$ 为 $7 4 5 5 0 \mathrm { ~ J / m o l }$ ; $\mathrm { P _ { N H 3 } }$ 和 $\mathrm { \bf P } _ { \mathrm { H } 2 }$ 分别为$\mathrm { N H } _ { 3 }$ 和 $\mathrm { H } _ { 2 }$ 在气氛中的分压；R为气体常数 $8 . 3 1 4 ~ \mathrm { J / m o l { \cdot } K }$ ；T为热力学温度， $\mathrm { ~ K ~ }$ 。

当表面处的活性[N]越过氧化层扩散至界面处，再扩散渗入硅钢带内部时，其扩散规律服从 Fick 第二定律[23]：

$$
\frac { \partial \mathbf { c } } { \partial \mathbf { t } } = \mathbf { D } \frac { \partial ^ { 2 } \mathbf { c } } { \partial \mathbf { x } ^ { 2 } }
$$

式中， $\boldsymbol { c }$ 为N的浓度； $x$ 为扩散距离; $t$ 为时间； $D$ 为扩散系数，当 $D$ 为不随浓度变化的常数时上式才能通过积分求解。在 TheromoCalc 软件中的DICTRA动力学计算模块中，引入了针对各组分的化学位梯度的迁移率 $M$ 这一概念，并将铁基材料中的各组分的原子迁移率及其与温度、浓度等的关系被归纳入MOBFe3数据库中，在通过DICTRA进行扩散计算时，实际上采用的是原子迁移率 $M$ 进行计算，且迁移率与扩散系数之间存在着如下换算关系[13,23]：

$$
\scriptstyle \mathrm { D = M } \mathrm { R T } ( 1 + \mathrm { d } \ln f _ { c } / \mathrm { d } \ln c )
$$

上式中的 $f _ { c }$ 为活度系数，在稀溶液或者理想溶液时上式可简化为D $\scriptstyle \mathbf { \alpha } = \mathbf { M }$ RT，在 $7 5 0 \ \mathrm { { ^ \circ C } }$ 时，通过DICTRA计算得到铁素体中氮的扩散系数 $\mathrm { D _ { N } { = } 8 . 0 3 { \times } 1 0 ^ { - 1 1 } { \ m } ^ { 2 } / s }$ ；迁移率 ${ \bf M } _ { \mathrm { N } } { = } 9 . 4 4 \times { 1 0 } ^ { - 1 5 } { \ m } ^ { 2 } { \mathrm { m o l } } { s } ^ { - 1 } { J } ^ { - 1 } { }$ ;

在稳态扩散时，穿过各界面的氮通量应该相同，即有如下界面条件存在：

$$
\begin{array} { r } { J _ { N } = f _ { 1 } \cdot \left( \mathbf { c } _ { \mathrm { N } } ^ { \mathrm { g } } - \mathbf { c } _ { \mathrm { N } } ^ { \mathrm { s u r f } } \right) = f _ { 2 } \cdot \left( \mathbf { c } _ { \mathrm { N } } ^ { \mathrm { s u r f } } - \mathbf { c } _ { \mathrm { N } } ^ { \mathrm { i n t e r f } } \right) = - \mathrm { D } \frac { \partial \mathbf { c } } { \partial \mathbf { x } } \Big \vert _ { \mathbf { x } = 0 } } \end{array}
$$

式中， $\mathbf { c } _ { \mathrm { N } } ^ { \mathrm { i n t e r f } }$ 是氧化层与基体界面处的N 浓度； $f _ { 2 }$ 是由钢带表面至氧化层与基体界面处的传质系数，与氧化层致密度和厚度、氧化物的尺寸和形貌等相关。由于取向硅钢渗氮通常都是固定成分的硅钢在一定的气氛和温度下进行的，在这样的条件下，为了便于计算，可以将上述边界条件简化为：

$$
\left. - \mathrm { D } \frac { \partial \mathrm { c } } { \partial \mathrm { x } } \right| _ { \mathrm { x } = 0 } = f \cdot \left( \mathrm { c } _ { \mathrm { N } } ^ { \mathrm { g } } - \mathrm { c } _ { \mathrm { N } } ^ { \mathrm { i n t e r f } } \right)
$$

式中， $f$ 为图4中 $\mathbf { N }$ 由气相穿过氧化层至界面处的综合传质系数，是 $f _ { I } , f _ { 2 }$ 两者的综合，与表面氧化层的状态密切相关。

另外，由于硅钢带在气氛中N由两个表面对称向内渗氮，所以在硅钢带中心无浓度梯度，即有如下界面条件成立：

$$
- { \frac { \partial \mathbf { c } } { \partial \mathbf { x } } } { \bigg | } _ { \mathbf { x } = \mathbf { M i d d l e } } = 0
$$

式中， $x =$ Middle表示硅钢带中心，即硅钢带的一半厚度处。

![](images/da07e094d8c0c6096991369d40ad002c49cb65a0bea17d957fff370b630d4cb8.jpg)  
图4界面反应控制的渗氮过程示意图

Fig.4 Schematic of surface reaction determined nitriding process $\cdot { c _ { \mathrm { N } } } ^ { \mathrm { g } } .$ $c _ { \mathrm { N } } ^ { \mathrm { { \scriptsize ~ s u r f } } }$ and $c _ { \mathrm { N } } ^ { \mathrm { \scriptsize ~ { ~ 1 n t e r f } } }$ are the N concentrations in gas,on the surface of stel sheet and at the interface of oxide layer and steel matrix respectively)

式(6)中的综合传质系数 $f$ 既包括了气氛和温度的影响，也包含了氧化层对渗氮的影响。渗氮时，由于$\mathrm { H } _ { 2 }$ 对氧化层的还原，导致氧化层不断发生变化(图3)，因此 $f$ 是动态变化的，需要确定的函数模型进行描述。基于不同的物理机制假设，可用多种模型计算该系数。如Rozendaal等24在研究N浓度的分布过程中认为， $f$ 主要是由渗氮气氛和温度决定的一个系数，即将其定义为 $f = f _ { 0 } \cdot \mathrm { P _ { H _ { 2 } } } \cdot \exp { \left( - \mathrm { Q } / ( \mathrm { R T } ) \right) }$ ，其中 $f _ { 0 }$ 为常数；Nakada等[25]计算固态渗氮过程中N 在奥氏体不锈钢中的扩散时，认为 $f$ 是一个常数；Pineau 等[26]根据溶质渗透理论模型，认为传质系数 $f$ 非常数，而随着时间按 Higbie 模型变化，即 $f = 2 \sqrt [ n ] { \mathrm { D _ { N } / ( \pi t ) } } ( \mathrm { D _ { N } }$ 为N 的扩散系数)。为了找到适合取向硅钢渗氮的关系式，本工作首先通过DICTRA来验证上述2种模型是否适合硅钢的渗氮过程；并提出了新的传质系数 $f$ 的函数模型，进而定义界面条件并结合Fick第二定律来计算不同时间下取向硅钢的渗氮量，并将计算结果与实验数据进行对比以验证该模型。

# 3.2模型的验证

# 3.2.1传质系数f为常数的情况

根据Rozendaal等[24]和 Nakada等[25]的研究，当渗氮温度和 $\mathrm { P _ { H } } _ { 2 }$ 分压确定之后，认为 $f$ 为常数，据此可以计算出不同 $f$ 时，渗入的N含量与渗氮时间的关系，如图5所示。从图中可见，当 $f$ 为常数时，所计算出的硅钢带中渗氮后的平均N含量与渗氮时间呈线性关系，并且随着 $f$ 的增加，渗氮量也增加，这与图1所示的渗氮动力学特征不吻合。

![](images/dfe083663b8c7a421545b5c44d93afc3794720784bee1967904b8cb4a6a640e2.jpg)  
图5N传质系数 $f$ 为常数时计算出的渗氮动力学曲线 Fig.5 Calculated nitriding kinetics by assuming the N-transfer coefficient $f$ as a constant

# 3.2.2 $f = \mathsf { a } / \sqrt [ \mathrm { t } ] { \mathsf { t } }$ 的情况

假设渗氮过程的 $f$ 符合 Higbie 模型[26]，即 $f = \mathsf { a } / \sqrt [ \mathsf { t } ]$ 其中a和 ${ \bf n } _ { 1 }$ 为常数)。通过给定不同数值的a和$\mathbf { n } _ { 1 }$ ，根据式(3)、(6)和(7)，利用 DICTRA 可计算出不同时间下的渗氮量，如图6所示。由此可以看出，根据该界面条件计算出的渗氮速度在开始时最大，之后随着时间不断减小，而这与图1所测的渗氮动力学特征不吻合，所以该模型定义的 $f$ 也是不适合的。

![](images/f52249c788d3722bd1aba509fca38f783f3318e751eff514d33343c234a57ee6.jpg)  
图6 $f = \mathbf { a } / { \sqrt [ n ] { \mathbf { t } } }$ 时计算得到的渗氮动力学曲线

Fig.6 Calculated nitriding kinetics by assuming $f = \mathbf { a } / \sqrt [ n ] { \mathbf { t } }$ （ $\dot { a }$ and $n _ { l } -$ constants, $t$ -nitriding time)

综上所述，传质系数为常数或者为Higbie模型时，都无法反映渗氮初期较慢而后期加快的动力学特征，因此需要重新建立传质系数模型来作为边界条件来模拟计算取向硅钢的渗氮过程。

# 3.3建立新模型

从图3可知，在硅钢带脱碳退火后，在硅钢带表面形成了一层氧化层，内有片层状氧化物，而在渗氮初期其渗氮速度较慢，因此认为脱碳退火形成的致密程度高的层状氧化物阻碍了N原子向硅钢带内部的扩散，所以渗入的 N 含量增加比较缓慢；同时由于渗氮气氛中有一定比例的 $\mathrm { H } _ { 2 }$ ，随着渗氮的进行，表面氧化层也被不断还原，片层状氧化物逐渐变成球状，且氧化层由于失氧而变得疏松，对渗氮的阻碍作用逐渐降低直至消失，因此渗氮速度逐渐增加直至因氧化层的阻碍作用完全消失而变得恒定，这与图1的渗氮实验数据相吻合。从上面的分析知道，传质系数 $f$ 是由硅钢带表面氧化层的还原程度所决定，也即硅钢氧化层的还原动力学决定了 $f$ 的变化。Guan 等[9]计算 $\mathrm { H } _ { 2 }$ 低温还原氧化层时，采用Avrami 方程 $f = 1 -$ exp $( - k t ^ { n } )$ 来描述氧化层的还原程度，其计算结果与实测结果吻合较好。因此，可以将气氛到界面的传质过程中的传质系数 $f$ 也同样定义为时间的 Avrami函数如下：

式中，A、k和 $\mathbf { n }$ 均为常数， $\mathbf { t } = 0$ 时， $f = 0$ ，即此时认为初始时刻的氧化层是对氮扩散是绝缘的；而 $t = \infty$ 时， $f$ $\scriptstyle = A$ ，也即在长时间渗氮时，氧化层因为被完全还原，所以对氮扩散是透明的即完全没有阻碍作用，也就是此时 $f$ 不再受氧化层的影响而完全由气氛和温度决定，这时式(8)就退化为 $f$ 为常数情形，此时渗氮量随时间呈现图5所示的线性增加关系。在图1所示的实测渗氮 $\mathbf { N }$ 含量数据中，当渗氮时间超过90s后，渗氮速度加快且近似呈直线关系，此时，可认为氧化层的作用已经不明显了，主要由气相至钢带表面的渗氮过程决定传质系数，即此时的 $f$ 应该是图5所示的为常数的情况，因此可按照 $f$ 为常数模型对图1中90s后的渗氮数据进行直线拟合，得出的 $f$ 可认为近似等于A值，如图5所示，经计算 $\mathrm { A } { = } 6 . 7 8 { \times } 1 0 ^ { - 1 3 }$ mol/s。

# 3.4新模型计算结果与讨论

# 3.4.1渗氮过程中的硅钢带平均N含量的变化

图7给出了 $f$ 随时间变化的Avrami函数关系，不同于Higbie 模型和常数模型，在初始阶段， $f$ 随时间的增大变化缓慢，但随后快速增加，与图1硅钢中N平均含量的增加趋势吻合，根据式(8)所定义的 $f$ 的函数模型以及式(3)、(6)和(7)，即可通过 DICTRA 软件对渗氮过程进行建模计算，得到在任一时刻钢带厚度方向的N浓度分布，并对此取积分平均值即可求出渗入钢带的平均N含量。计算得到的平均N含量如图8所示。如上所述，式(8)中系数 $A$ 可以通过长时间的渗氮数据确定，而 $\mathbf { n }$ 和 $\mathbf { k }$ 值未知，两者的增加均会导致渗氮量也相应增加，但其中 $\mathfrak { n }$ 的影响更显著，如图8中所示的1、2和3条线的计算结果所示。 $\mathfrak { n }$ 的取值范围与氧化层的还原机制相关，如Guan等[19在 $\mathrm { H } _ { 2 }$ 低温还原热轧钢板氧化层的研究中，将 $\mathbf { n }$ 值根据气固反应机制分为3类： $0 . 5 4 { \leq } n { \leq } 0 . 6 2$ 时扩散为控制性环节； $1 . 0 7 { \leq } \mathrm { n } { \leq } 1 . 2 4$ 时相边界反应为控制环节； $2 { \leq } \mathrm { n } { \leq } 3$ 时形核为控制环节。而Pineau 等[26在不同温度下 $\mathrm { H } _ { 2 }$ 还原氧化铁的实验研究结果表明，在温度 $T { < } 4 2 0 \ \mathrm { ~ } ^ { \circ } \mathrm { C }$ 时为形核为控制性环节，温度 $\scriptstyle { T > 4 2 0 ^ { \circ } \mathrm { C } }$ 时相边界反应为控制性环节。根据硅钢的渗氮反应条件，硅钢氧化层的还原应该是相边界反应为控制环节，故根据Guan 等[19的研究，该机制所对应 $n$ 的范围为 $1 . 0 7 { \leq } n { \leq } 1 . 2 4$ ，可取上限 $n$ 为1.24，此时本模型就只剩下一个待定系数 $k$ 。可将计算结果与图1中的实测数据进行逼近优化后确定 $k$ ，最后确定 $k$ 为 $2 . 8 2 \times 1 0 ^ { - 3 }$ ，此时计算结果(图8中曲线1)和实验数据吻合非常好，相关系数为0.99。由图8中曲线1可知，渗氮 $6 0 ~ \mathrm { s }$ 以内，硅钢带平均 $\mathbf { N }$ 含量增加缓慢； $6 0 { \sim } 9 0 \ \mathrm { s }$ 期间， $\mathbf { N }$ 含量快速增加且渗氮速率也在变大，直至 $9 0 \mathrm { ~ s ~ }$ 左右时渗氮速率增至最大，之后N含量以恒定速率增加。这些均与实测的渗氮动力学特征高度吻合。本实验结果和计算结果也与 Liao 等[2的研究结果一致，他们研究了不同渗氮时间后硅钢薄带中平均 $\mathbf { N }$ 含量的变化，也发现N含量在渗氮初期增加缓慢，之后渗氮速度逐渐增大。

![](images/a8effbc85fb75300427761dd21a16928e7ddb59153c272d32058f3dec52fc2ca.jpg)  
图7渗氮时 $f$ 与时间的不同函数关系Fig.7 Possible dependences of $f$ on time duringnitriding, as described byf=constant,（204 and$\mathrm { e x p } ( - \mathrm { k t ^ { n } } ) ]$ respectively $( a , n _ { 1 }$ ， $k ,$ A and $n$ areconstants)  
图8根据 $f = \mathrm { A } [ 1 - \mathrm { e x p } ( - \mathrm { k t } ^ { \mathrm { n } } ) ]$ 模型计算出 的渗氮动力学曲线与实验结果的对比 Fig.8Comparison ofthe measuredand calculated N contents during nitriding, the latter assumes the $f = \mathrm { A } [ 1 - \mathrm { e x p } ( - \mathrm { k t ^ { n } } ) ]$ 0 $\left[ k , \right.$ A and $n$ are constants)

![](images/da31416b3dd451d9bcf0c02141d83b877909d091163dd2e7840f2213efec712f.jpg)  
图9 计算得到的渗氮后硅钢薄带中N浓度梯度与通过EPMA 实测得到N浓度梯度的对比 Fig.9 Comparison of calculated N concentration gradient and the measured one by EPMA across the thickness direction of silicon steel sheet after nitriding

# $3 . 4 . 2 \ : \mathrm { N }$ 浓度分布曲线

上述模型同样可以计算出在渗氮不同时刻的N浓度分布，所得到的厚度方向 $\mathbf { N }$ 浓度分布如图9所示，并与 EPMA所测结果相比较。从图中的计算结果可知,N浓度在距离表面 $3 0 \mu \mathrm { m }$ 范围内急剧下降，而 $4 0 \mu \mathrm { m }$ 后N浓度变化减缓，这和EPMA的实测结果非常接近；而且计算与实测的N的扩散距离相近，在近表面$3 0 \mu \mathrm { m }$ 内 N 浓度下降的速率也相似。这说明本模型计算基本再现了实际渗氮的N浓度梯度特征。需要注意的是计算和实测的N含量差别较大，这是因为一是由于样品很容易被空气的 $\mathbf { N } _ { 2 }$ 污染，二是由于EPMA并不能准确测出在钢带某一厚度位置的N含量，而是以该位置为中心电子束所激发区域的 $\mathbf { N }$ 含量；其三是N作为轻元素，尤其在低含量时测量误差较大。事实上，计算得到的N浓度梯度应该更接近实际值，因为根据N浓度梯度积分平均得到的平均N含量与化学分析检测得到的N含量是一致的。虽然 EPMA关于N含量的测量基本上是一个定性结果，但是其揭示出的N浓度梯度特征则相对可靠，如渗氮深度、在厚度方向的N浓度梯度等，而在这些方面，模型计算出的N浓度梯度与EPMA的测量结果基本是一致的。

0.16 0.92   
% /  nr rlile es p 0.14 0.12 EPlMAame urutent 0.90% 0.86 0.10 0.84 0.08 0.82 0.06 0.80   
ceeeeegea 0.02 0.78 0.74 0.00 . 0.72 0.00 0.02 0.04 0.06 0.08 0.10 0.12 0.14 0.16 Interface Distance to the interface /mm

综上所述，依据从气相至氧化层/铁基体界面间的传质系数符合Avrami 函数模型的假设，所建立的渗氮定量模型可以很好地解释渗氮过程中的动力学特点和N浓度梯度特征，因此本模型的假设是合理的。

# 4结论

(1)取向硅钢在 $7 5 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 渗氮温度， $1 5 \% \mathrm { N H } _ { 3 }$ 、 $8 5 \% \mathrm { H } _ { 2 }$ 和 ${ \bf N } _ { 2 }$ $( \mathrm { H } _ { 2 } { : } \mathrm { N } _ { 2 } { = } 3 { : } 1 )$ 渗氮气氛下，渗氮初期渗氮速度较小，随后逐渐增加直至恒定；渗氮 $1 2 0 \mathrm { { s } }$ 后，在近表面 $3 0 \mu \mathrm { m }$ 范围内存在显著的N浓度梯度。

(2)取向硅钢经过脱碳退火后，表面形成致密氧化层，该氧化层主要为含Fe和 Si的氧化物组成，氧化物多为层状；渗氮一定时间后，由于气氛中 $\mathrm { H } _ { 2 }$ 的还原，氧化物形貌由层状转变为球状。渗氮初期的氧化层对渗氮有阻碍作用导致渗氮速度较慢，但随着氧化层被逐渐还原而变疏松，其阻碍作用逐步消失，因此渗氮速度不断加快直至变为常数。

(3)由气氛至氧化层和基体之间界面的氮的传质系数 $f$ 为常数或者符合Higbie 模型时，计算得到的渗氮动力学均与实测数据不吻合；由于氧化层在渗氮时被气氛中 $\mathrm { H } _ { 2 }$ 还原，其还原动力学满足Avrami模型，因此提出 $f$ 也符合同样的模型，即 $f = \mathrm { A } [ 1 - \mathrm { e x p } ( - \mathrm { k t ^ { n } } ) ]$ 。据此计算得到的渗氮动力学与实测值非常吻合，且计算得到的厚度方向N浓度梯度特征也与实测值基本吻合。

# 参考文献

[1]He Z Z, Zhao Y,Luo HW. Electrical Steel. Beijing: Metallurgical Industry Press,2012: 1 (何忠治，赵 宇,罗海文．电工钢．北京：冶金工业出版社,2012:1) [2] UshigamiY,izokamiYFujikura M,etal.Recentdevelopmentoflow-lossgrain-orientedsiliconsteel[J].J.Magn.agn. Mater.,2003,254-255: 307 [3] Goss NP. Electrical sheet and method and apparatus forits manufacture and test [P]. US,1965559,1934 [4] Li J,Sun Y,ZhaoY.Developmentoflowtemperature slabreheating techniqueforgrain-oriented silicon steel[J].IroSeel,   
2007,42(10): 72 (李 军，孙 颖，赵宇．取向硅钢低温铸坏加热技术的研发进展[J]．钢铁,2007,42(10):72) [5] Kumano T,HarataniT,FujiiN.Effectofnitridingongrainorientediicosteelbearingaluminum[J].IIInt,25,45:95 [6] Lee SC,HanCH,WooJS,etal. Hotrollng annealing;coldrollng decarbonization;controllingconcentration[P].US,   
6451128,2002 [7] TakahashiN,HaraseJ.Recentdevelopmentof technologyof graiorientedsiiconsteelC].MaterSci.Forum,199604:143 [8] Kubota T,Fujikura M, Ushigami Y.Recent progressand future trendongrain-oriented siliconstel[J].JMagn Magn Mater,   
2000,215: 69 [9]Lobanov ML. Nitriding of Fe- $3 \%$ Si alloy [J]. Steel Trans,2015,45(2): 94 [10] Morawiec A. On abnormal growth of Goss grains in grain-oriented silicon steel. Scr.Mater.,2011,64: 466 [1]KumanoTOhataY,FujiiN,etal.Effectofitridingongrainorientedsiliconstelbearingaluminum(thsecondstudy)[J]. J. Magn.Magn.Mater.,2006,304: e602 [12]AbbruzeseG,CampopianoA.AgeneraltheoryofsecondaryrecrystalizationingrainorientedFe-Si:Metalurgical parameters controlling the microstructural evolution [J].J.Magn.Magn.Mater.,1994,133:123 [13] Thermocalc: Thermo-calc software TCFE8 steel/Fe-database.version 2015b: 2015,www.thermocalc.com [14]Wang RP,LiuJ,MaoJH.Influenceof nitriding modesandammoniaonnitrogencontentoforiented siliconstel[J].Heat Treat Met,2009,34(10): 69 (王若平，刘 静，毛炯辉．渗氮方式及氨气对取向硅钢氮含量的影响 [J]，金属热处理,2009,34(10):69) [15] Toda H, Sato K,Komatsubara M. Characterization of internal oxide layers in $3 \% \mathrm { S i }$ grain-oriented steel by electrochemical methods [J]. Jmater eng perform,1997,6: 722 [16]SongHJ,YangP,MaoWM.Nitridingbehavioruring nitriding treatmentofelectricalstel[J].HeatTreatMet,2237:38 (宋惠军，杨 平，毛卫民．电工钢渗氮的氮行为[J]．金属热处理，2012,37:38) [17]YanGC,HeCX,MengL,etal.Structureofsurfaceoxidelayerand efectonnitridingof grain-oriented silico ste[J]. Mater Eng. 2015,43: 89 (严国春，何承绪，孟力，马光，吴细毛．取向硅钢表面氧化层的结构及其对渗氮的影响 [J]．材料工程,2015,43:89   
[18]Jung S,Kwon MS,ParkJ,etal.ATEMstudyofoxidelayers formedduring decarburizationannealingofelectrical stee[J]. ISIJ Int.,2011,51: 1163   
[19]GuanC,LiJ,TanN,etal.Reductioofoxidescaleonhot-roledsteelbyhydrogenatlowtemperature[J].It.JHydrogen Energy,2014,39:15116   
[20]HudsonMR.Nonacidicdescaling ofhotband.iiReductionofscaleby hydrogenorcarbon[J].MetFinish,1985,83:59   
[21]HudsonMR.Nonacidic descaling of hotband: reductionof scale by hydrogen orcarbon[J].MetFinish 1985,83:73   
[2]SprogeL,AgrenJ.Experimentalandtheoretical studiesofgasonsumptioninthegascarburizing process[J].J.HeatTreat. 1988, 6:9   
[23]Hillert M.translatedbyLaiHY,LiuGX.Diffusioninalloysandthermodynamics[M]Beijing:MetallrgyIndustrye, 1984: 6 (Hillert M.著，赖和怡，刘国勋译．合金扩散和热力学 [M]．北京：冶金工业出版社,1984:6)   
[24]RozendalHCF,MitemeijerEJ,ColijnPF,etal.Tedevelopmentofitrogenconcentrationprofilesonnitridngion[J]. Metall. Trans.,1983,14A: 395   
[25]NakadaN,TsuboiK,nomotoT,etal.Thermodynamicsand kineticsofsolution nitriding[J].Calphad,2014,47:168   
[26] Pineau A, Kanari N, Gaballah I. Kinetics of reduction of iron oxides by $\mathrm { H } _ { 2 }$ : Part I: Low temperature reduction of hematite [J]. Thermochim. Acta,2006,447: 89   
[27]Liao CC,HouCK.Effectofnitridingtieonsecondaryecrystallzationbhaviorsandmagnetic propertiesof gain-oriented electrical steel[J].J.Magn.Magn.Mater,2010,322: 434