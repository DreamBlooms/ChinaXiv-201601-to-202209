# 我国地基雷达观测月球的现状和研究进展

孙靖，杨嵩²，周峰，丁宗华²，刘磊，曹建峰4，韩松涛4，平劲松"(1.中国科学院国家天文台，北京100101;2.中国电波传播研究所，青岛266107;3.西安电子科技大学，西安710071;4.北京航天飞行控制中心，北京 100094)

摘要：地基雷达天文观测可以提供太阳系天体目标的地形地貌、物理特征、轨道动力等信息。文章聚焦利用地基雷达天文技术开展月球观测的原理方法和科学意义，介绍了基于我国现有深空雷达上行装置、射电望远镜条件、以及非相干散射雷达等系统，初步开展的UHF频段和X频段的地基雷达观测月球试验。通过月球反射回波的信号处理，获得了延迟、多普勒频移等参数，得到了一致的与近表层物质密度相关的月面雷达反射率，并得到了月球的左右旋圆极化率，其反映了与波长同尺度的月球近表层结构。文章积累的数据处理经验将为我国的小行星预警、行星历表等地基雷达天文观测研究提供技术基础。

关键词：地基雷达；月球；雷达反射率；圆极化率中图分类号：P165 文献标识码：A 文章编号：1007-2276-(2004)4-0338-05

# 0引言

雷达可以主动发射电磁波探测和跟踪空间目标，通过对上行发射信号的控制，研究太阳系天体目标的尺寸、形状、旋转周期等特征，是研究太阳系天体的地形地貌、物理特征、轨道动力等信息的最有效技术之一。目前雷达探测技术可分为地基探测、星载探测、就位探测、以及星地联合探测，不同的探测方式有各自不同的特点与优势[1-2]。地基探测是将雷达放置在地球上对太阳系天体进行观测的探测方式，依托地面大口径天线作为发射和接收天线，其观测周期短，较为经济、方便、可重复性高。星载探测是将雷达搭载在卫星上，将卫星发射至太阳系天体的轨道上进行环绕观测的探测方式，探测范围广，精确度较高，但成本较昂贵，探测周期长。就位探测是将雷达搭载在天体巡视器上，利用火箭发射至太阳系天体表面进行实地登陆观测的探测方式，可以高分辨率探测天体次表层地质结构与厚度，精度高，缺陷在于探测区域范围有限。星地联合探测是将雷达收发设备分置于星载、地基两个不同载体平台的探测方式，结合了星载雷达与地基雷达的优势，减少了星载雷达的载荷负重，较为经济，但数据处理算法上更为复杂，会致使分辨率降低。就目前的发展趋势而言，地基雷达以成本低、分辨率高的优势仍将是未来太阳系天体探测的主要手段。

月球是离地球最近的天体，它历来是人类天文活动和空间探测活动的首选目标之一。月球也是地基雷达探测应用最早也是最多的天体，1946年1月美国海军某地面站向月球发射电磁波，在经过不到3秒的时延接收天线收到了来自月球的信号回波，这是人类首次利用地基雷达技术探测太阳系天体收到的回波。雷达探测技术在探测月球过程中具有独特的优势与作用。首先，雷达探测技术不受光照和地球气象条件限制，可用于探测月球两极、月球撞击坑的永久阴影区。其次，运用合成孔径技术，可用于对月球表面的地形测绘、成像。最后，基于雷达电磁波的穿透性与极化特征，通过分析雷达后向散射回波，可反演月球的月壤厚度、介电常数、地质结构等次表层特性，以及探测月球是否存在水冰。但是由于地月运动关系，地基雷达技术只能探测月球朝向地球的一面。

人类运用地基雷达探测技术开展了对月球地形地貌探测、月壤厚度反演、月球水冰探测等研究，取得了丰硕的科学成果。美国引领了地基雷达天文学领域的发展，在基础设施和信号处理方法两方面都有雄厚基础。美国GSSR（Goldstone Solar System Radar）、Arecibo和Green Bank等多个射电天文台站主导了地基雷达对太阳系自然天体的探测，表1中列出了美国主要地基雷达探测系统参数3。与国外相比，我国运用雷达技术对天体的探测还处于起步阶段，“嫦娥三号”搭载的测月雷达（Lunar Penetrating Radar，LPR）是我国首次运用雷达技术探测地球外天体，同时也是人类首次运用雷达技术对地外天体进行实地就位探测。然而我国在地基雷达测月领域目前还处于空白阶段，还没有专门用于对月球和其它太阳系天体进行观测的地基雷达。但国内现有的地基设备，包括深空网雷达系统、云南曲靖非相干散射雷达、以及我国的大口径射电望远镜网等，目前已具备月球探测的地基雷达发射和接收能力。因此通过发展针对地基雷达观测的数据处理方法，可以在现阶段开展月球等天体的地基雷达探测试验和科学研究，这将与通过运载火箭发射卫星进行探测等方式互为补充，必将大大推动我国太阳系天体探测和行星科学研究的发展，也将在近地小行星监测和预警中起着至关重要的作用，同时地基雷达天文技术也可用于保护卫星和监测潜在的危险太空物体。

# 表1美国主要地基雷达探测系统参数

Tab.1 Key-parameters of ground-based radar detection systems in the US   

<html><body><table><tr><td>Transmitter telescope</td><td>Transmitterdiameter /m</td><td>Transmitter frequency /MHz</td><td>Transmitter power</td><td>Receiver telescopes</td></tr><tr><td>Arecibo</td><td>305</td><td>430</td><td>1MW</td><td>Arecibo 305 m</td></tr><tr><td>Goldstone</td><td>70</td><td>2380 8560</td><td>500kW</td><td>Green Bank 100m DSS-13 34m Green Bank 100m</td></tr></table></body></html>

# 1原理方法

雷达对目标的探测和特征信息提取实质上是一个基于雷达发射与接收回波信号的数据处理过程，雷达首先发射一个特定频段和调制形式的电磁波，电磁波到达观测目标后会发生反射现象，部分反射回来的电磁波经由雷达接收，就得到了包含观测目标电磁散射特性的回波信号。通过复杂的回波数据处理，就可以反演出观测目标在特定频段下的电磁散射特性，进而重构目标的形状、结构等特性。因此，雷达可以满足太阳系内天体观测的多种需求，获得目标天体的高分辨率地形分布、介电常数和地质结构等特性。由于目标表面几何结构和物理特性的差异会导致其极化特性不同，因此，雷达发射特定的极化调制信号，通过对接收回波延迟、多普勒和极化等多维度信息的提取和处理，可精确的获得目标的距离、速度、大小形状、几何结构和物理特性等。并且，雷达发射的电磁波具有一定穿透性，可以对天体表层下的结构进行探测。但地基雷达发射信号的衰减快，信号强度与距离的4次方成反比，这就需要雷达具有高信号发射功率和灵敏的接收系统。另外，地基雷达数据处理算法较复杂，需要对被观测天体的相对运动规律有精确的先验知识。

# 1.1回波的时间延迟和距离分辨能力

雷达回波信号的时间延迟反映了雷达波从发射到接收所经历的传输距离，二者关系如下。通过研究回波相对反射信号的延迟，可以得到目标天体的距离，解算天体星历表。

$$
\mathtt { R } = { \mathrm { c t } } / 2
$$

其中，c为电磁波的传播速度，t为电磁波的传输时间延迟。对于球型物体，最靠近雷达的球型顶点返回的时间最短，以此为中心可以形成不同的距离圆环。通过雷达距离径深信息可以

反演目标的半径，距离门信息则表征目标的表面特征。对于宽带雷达来说，目标回波信号的距离分辨能力与发射信号的带宽有关，带宽越大，分辨率越高，距离分辨率的计算公式如下：

$$
\begin{array} { r } { \rho _ { r } = k \frac { c } { 2 B } } \end{array}
$$

其中， $B$ 为雷达发射信号的带宽， $k$ 为距离压缩的时候加窗引起的主瓣展宽系数。由于月球等自然天体尺度较大，对距离向分辨率的要求不高，也可以直接利用发射脉冲信号的宽度来实现不同距离场景的分辨，此时，距离分辨率可通过下式计算：

$$
\rho _ { r } = \frac { c \tau } { 2 }
$$

其中， $\tau$ 为雷达发射信号的脉冲宽度。

# 1.2回波的多普勒频率

当目标天体与地基雷达存在相对运动时，雷达接收到的目标天体回波信号频率将发生偏移，该偏移量称为多普勒频率。回波信号的多普勒频率直接反映了目标天体的径向速度。对于双基地探测体制来说，多普勒频率 $\mathrm { f _ { D } }$ 可根据目标天体相对发射天线的距离变化速度v和目标天体相对接收天线的距离变化速度u计算而得，如公式（4）所示，其中 $\mathbf { f } _ { 0 }$ 表示雷达发射信号的载频。

$$
\begin{array} { r } { \mathrm { f _ { D } } = \mathrm { f _ { 0 } } \left( 1 + \frac { \mathrm { u } } { \mathrm { c } } \right) / \left( 1 - \frac { \mathrm { v } } { \mathrm { c } } \right) } \end{array}
$$

对于月球上不同区域来说，其相对月球转动中心的距离不同，旋转线速度不同，使得其在雷达视线方向的投影速度不同，产生了不同的多普勒频率，而月球雷达方位成像正是利用不同区域多普勒频率的不同方位向的分辨能力。

回波信号的多普勒频谱展宽特性则包含了目标天体的结构与转动等信息，月球回波信号频谱展宽可由理论计算公式粗略估计为：

$$
\mathsf { B } = 4 \pi \mathrm { l } \alpha / \lambda \mathrm { P }
$$

其中l为月地距离，单位为米； $\alpha$ 为波束宽度，单位为弧度； $\lambda$ 为信号波长，单位为米；P为月球自转周期，单位为秒。

# 1.3回波的幅度特性

根据雷达方程，接收到月球反射回波信号的幅度 $\mathrm { P _ { r } }$ 与距离、发射功率、天线增益等因素有关，其中距离的影响最大，雷达方程表示如下：

$$
\mathrm { P _ { r } } = \mathrm { P _ { t } } \mathrm { G _ { t } } \mathrm { A _ { r } } \sigma / ( 4 \pi \mathrm { R } ^ { 2 } ) ^ { 2 }
$$

其中，P是发射功率， $\mathbf { G } _ { \mathrm { t } }$ 是发射天线的增益， $\textstyle \mathbf { A } _ { \mathrm { r } }$ 是接收天线的有效孔径， $\sigma$ 是雷达波束在月球表面照射区域的雷达截面， $\sigma = \widehat { \sigma } \ A _ { \mathrm { p r o j } }$ ， $\widehat { \pmb { \sigma } }$ 为雷达反射率（radaralbedo）， $\mathsf { A } _ { \mathsf { p r o j } }$ 为发射的电磁波在月球表面的照射面积，R是发射天线到月球的距离。

通过接收天线的实际回波能量，根据上述公式（6），可反推雷达反射率，这与月球表面的物质特性有关。Arecibo天文台的Thompson等人发现在新的月球撞击坑边缘回波明显增强[4]，Schaber等人根据雨海盆地异常低的雷达反射率，研究了盆地内的岩浆流[5]。

介电常数值能够有效的表征绝缘材料或电介质的电性能，月球的介电常数可以直接测月球样本而得，也可以根据雷达反射率推算。由介电常数值可推断该层介质的物理特性，是否存在水冰等重要信息，认识和解释月球地质结构特征。两个参数控制着层状介质的介电常数：物质成分（化学的、矿物的、含水量和物理状态）和物质的密度。因为水冰呈现较低的介电常数值（典型值为3.1)，而岩浆岩的介电常数相对较高（典型值8)。层状介质中存在的大量水冰将导致表面反射率相对于干燥、密实的岩石层较低。而低密度的介质也可以导致这种有效介电常数较小，因此使用互补的数据集对完善的解释至关重要。

# 1.4回波的极化特征

对雷达信号的极化特征进行分析可以更深入的了解月球表面和近表面特性，进一步推测月球是否存在水冰、月表的粗糙度等等。对于圆偏振的连续波，其回波能量在偏振方向上存在一定分布，反射波的偏振情况与波长同尺度的表层结构相关。

传统的地基雷达观测中，雷达通常发射一个左旋或右旋圆极化（Left/RightCircularly

Polarized，LCP/RCP）电磁波。如果信号从理想光滑平面表面反射后，信号的圆极化特性被反转。实际中大多回波既有镜面也有漫反射成份，由于二次反射等，我们也会收到相同极化的信号。通常采用同向旋转量和反向旋转量大小之比来描述极化程度，利用接收的电磁回波极化辐射能量可以算出圆极化率（CircularPolarization Ratio，CPR） $\mu _ { \mathrm { C } } = \sigma _ { \mathrm { S C } } / \sigma _ { 0 \mathrm { C } }$ ，其中“SC”代表回波偏振方向与发射波相同，“OC”代表回波偏振方向与发射波相反， ${ \sigma } _ { \mathrm { S C } }$ 为接收的同向极化回波总能量， $\sigma _ { 0 \mathrm { C } }$ 为接收的反向极化回波总能量。 $\mu _ { \mathrm { c } }$ 是衡量月球表面波长尺度粗糙度的量，即目标天体表面存在的与雷达波长尺度相同的结构（如岩石）， $\mu _ { \mathrm { c } }$ 越大则表面越粗糙。

在地基雷达探月中，同时接收来自月球表面的左旋与右旋圆极化回波，获得的CPR是一个重要的观测量，CPR除了与雷达配置（如频率和入射角）有关外，也与月表的坡度、粗糙度、石块大小与丰度、月壤介电常数、厚度、极区潜在的水冰含量等多个参数密切相关。在所有影响雷达回波的参数中，入射角的作用最为显著。一般地，较大的入射角对应着较大的CPR值。月表CPR的均值介于0.4-0.5之间[6-7]。对频谱域的每个点均可计算极化比，结合距离-多普勒矩阵，就有可能根据频谱的位置定位光滑和粗糙区域。图1是Arecibo地基雷达发射、Green Bank $1 0 0 \mathrm { m }$ 射电望远镜（GBT）接收的月球南极雷达圆极化率图[8。探测波长 $7 0 \mathrm { c m }$ 图1中将雷达阴影区的圆极化率设为0，整个区域圆极化率从0.5（黑色）到1.1（白色）不等。由于圆极化率与天体表面的岩石丰度相关，根据图1就能推演出极区的月壤岩石丰度特性。如图中Zucchius、Hausen、Moretus、Schomberger等4个环形山附近出现低圆极化率的圆晕，说明这些地区的喷发物中石块含量较低。

![](images/96d19d4a142ca7f45bc1a298095bffc5063081818ff01c53cce9e69f094bdce8.jpg)  
图1月球南极地区的雷达极化率图  
Fig.1 CPR properties in the south polar region of the Moon

# 1.5月球水冰探测

长期以来，科学家认为月球上没有水，当然也没有水冰。各种手段探测月球的结果似乎也证实了这一点。但是，人们对于月球水冰的探测一直没有停止脚步，其中雷达探测水冰的方式起着重要作用。雷达系统本身发射电磁波，其观测不受太阳照射等因素的影响，因此可以直接探测到两极地区的永久阴影坑，确定其内是否存在潜在的水冰。

水冰挥发物具有全内反射性质（totalinternalreflection），使散射信号中的电磁波保持原来的极化方式，此时CPR的值会升高（可大于1）；而且冰冻挥发物比硅酸盐类岩石的传输损耗要低，相应的电磁波平均反射率更高，后向散射增强，回波能量就更高，即水冰比月表岩石能反射更多的电磁波。而月表硅酸盐类岩石则向所有方向散射电磁波，部分能量不能被地面接收天线所接收。因此，根据二者表面返回的回波极化方式和能量特征的差异性，可以对月壤与水冰进行区分。

1992年，美国康纳尔大学的Stacy等人利用Arecibo天文台S频段雷达波，以125米空间分辨率、双极化方式对月球极地进行观测，通过比较目标区域回波特性与水冰回波特性的异同，来寻找月球大面积的水冰。探测结果没有发现任何一块面积大于1km的区域存在高雷达后向散射截面和高圆极化率，即没有发现月球极地存在大面积分布的水冰[。

虽然，水冰可以引起散射效应，但其它的散射机制（如月表粗糙度、二次反射等）也可解释月球极地圆极化率增加的原因。一些永久阴影区的圆极化率升高了，不排除可能是在永久阴影区存在大量分散的水冰，但也可能是因为表面粗糙度引起的。另外，两极水冰存在的形式可能是分散式的冰-月壤混合物“脏冰”，雷达探测分辨率若是大于“脏冰”的面积将无法辨别水冰的存在，提高雷达分辨率将是未来要解决的问题。所以，后续需要综合分析多维月球探测数据，研究月球是否存在水冰的科学问题。

# 1.6月壤厚度反演

月球次表层包括月壤、碎石、基岩等多个圈层，月壤（LunarRegolith）广义上是指覆盖在月球基岩之上的所有月表面风化的物质，甚至包括直径为几米的岩石。由于月球没有大气，长期裸露的月壤经由太阳风（太阳喷射的高能粒子流）的直接注入，使得月壤内蕴藏着丰富的He资源，He作为可控核聚变能源燃料，它有可能成为解决今后人类长期能源发展需求的重要原料，所以对于月壤厚度的研究具有十分重要的意义。一些学者通过在不同波段以及利用不同探测模式对月球进行观测，进而得到月壤的厚度分布情况，地基雷达技术可以用于反演月球的月壤厚度。利用地基雷达数据，并考虑高分辨率地形数据、月表粗糙度、岩石大小和丰度、月壤介电常数等输入，进行月壤厚度的反演。

Shkuratov等人利用Arecibo天文台70cm波长地基雷达对月球正面观测数据，并结合月球铁和钛分布的光谱数据，获得了世界上第1幅月球正面的月壤厚度分布图。由月壤厚度分布图可知月海地区与高地地区（不考虑月球高地厚度数千米的大月壤）的平均月壤厚度分别为5米和12米[7]。2011年，法文哲等人利用高分辨率的Arecibo地基雷达数据，结合基于向量辐射转移理论的雷达散射模型，得出月海地区月壤度约为5m，高地地区月壤厚度10m以上[9]。

# 1.7月球成像和地形地貌研究

在冷战背景下，美国和前苏联展开了以月球探测为中心的空间竞赛，围绕人类登月着陆点选择问题，月球地貌与地形的研究显得迫切而至关重要。地基雷达探测方式由于自身的优势与当时技术的局限性，成为月球地形测绘的首选方式。采用地基雷达技术开展月球地形测绘主要是在20世纪60、70年代进行的，期间Arecibo的月球雷达成像结果奠定了雷达技术探测月球地形地貌的基础。目前，地基雷达在对月球正面中低纬度地区地形测绘中的应用价值明显降低，但是由于月球两极存在永久阴影区，这些阴影区是可见光波段探测手段无法观测的，而微波波段的观测不受太阳光照和地球气象条件的影响。因此，可以利用地基雷达绘制月球两极的地形，特别是永久阴影区的地形，这是当前利用地基雷达进行月面地形地貌探测的热点。

地基雷达对月球成像是逆合成孔径雷达成像技术在天文探测中的应用，探测原理如图2所示，地基雷达对月球发射电磁信号，利用地球自转、月球自转和月球公转等运动形成的地月相对运动关系，将来自不同观测时刻的回波信号进行相干累积处理，实现方位的高分辨。对接收的回波数据进行距离-多普勒成像处理便可得到月球的雷达图像，而回波信号的相干累积处理依赖于雷达与月球相对运动分量的精确估计与补偿，若能获得雷达与月球相对运动的先验知识，即可直接构造运动补偿分量实现月球的距离-多普勒成像[0]。

![](images/867a478a64bac0694357ab79adfe9f854a81de416eef3bde56a4ac3cfab13247.jpg)  
图2 地基雷达探测月球原理示意图[1]

地基雷达虽然只能探测月球朝向地球一面的图像而不是全月的探测图像，但优势在于较为经济、探测周期短、可重复性高。就目前的发展趋势而言，地基雷达以成本低、分辨率高的优势仍将是未来月球地貌与两极探测的主要手段。地基雷达成像的目标是不断追求更高分辨率的月球地形地貌图像。下图为2008年NASA公布的由Goldstone太阳系雷达获得的迄今为止最高分辨率（20米/像素）的月球南极地形图，这远高于地基光学望远镜的分辨率，甚至比嫦娥一号CCD相机的分辨率（ $1 2 0 \mathrm { m }$ ）还要高。

![](images/d93654e882f9fdc16d988cc7f76a8139a33c24b0a1132fdf36378b5aaf0c885f.jpg)  
Fig.2 Illustration of the principle of detecting lunar features using a ground-based radar   
图3Goldstone太阳系雷达获得的月球南极地形图  
Fig.3 Radar map of lunar south pole using GSSR

# 2观测试验

地基太阳系雷达是一种特大功率的雷达系统，它向太阳系天体发射选定波段的电磁波，电磁波传送到目标天体，然后又被反射离开天体表面，被一个或多个地面接收站所接收。通过对接收信号的特征分析，进行太阳系天体的相关科学研究。我国已建设了较完备的航天测

控、空间目标监视、情报侦察等雷达系统，在云南曲靖建设了我国首套电离层非相干散射雷达（QJISR）。通过发展地基雷达天体探测的数据处理技术，可以在较短时间内实现近地天体的地基雷达探测，尤其是反射面大、回波强的月球探测，弥补其他探测手段的缺陷。

# 2.1基于喀什深空站和昆明40米射电望远镜的连续波信号双基地探月试验

根据地基雷达的发展经验看，深空探测雷达与深空探测网相互独立又相互联系，它们互相共享许多设备，深空雷达的天线可以为深空探测网提供发射和接收服务，而深空探测网的天线也为深空雷达提供接收服务。基于喀什深空雷达站(Ks)和昆明40米射电望远镜台站（Km)，开展了一系列的双基地月球地基雷达天文研究试验，参数如下表2所示。观测时雷达发射天线和距离数千公里的射电望远镜接收天线都指向“嫦娥三号”着陆器位置。“嫦娥三号”着陆地点位于月海盆地北部，主要由月球玄武岩构成。

发射站天线发射X波段连续波，频率为7209.125MHz，并采用左旋圆极化模式，载波频率不随时间变化，发射机功率为200W。射电望远镜天线采用与发射波相同极化的（SC）和相反极化的（OC）两种圆极化方式，同时接收月面反射回波，两位量化回波信号并采集记录。由Ks站18米天线和Km站40米天线的X波段波束宽度决定了共同照射月面面积直径为503公里，远小于月球直径[12]。

# 表2天线性能参数

Tab.2 Performance Characteristics of the Radio Telescopes   

<html><body><table><tr><td>Antenna</td><td>Ks</td><td>Km</td></tr><tr><td>DiameterD，m</td><td>18</td><td>40</td></tr><tr><td>Aperture efficiency n</td><td>0.5</td><td>0.47</td></tr><tr><td>System temperature Tr，K</td><td>一</td><td>96</td></tr><tr><td>Transmitter frequency fo，MHz</td><td>7209.125</td><td>1</td></tr><tr><td>Transmitterpower Pt，W</td><td>200</td><td>一</td></tr></table></body></html>

# 2.2基于曲靖雷达的脉冲信号自发自收探月试验

曲靖非相干散射雷达通过地面向高空发射高功率电磁波，接收电离层电子与离子散射的微弱信号，反演电离层等离子体密度、温度与速度等众多参数[13]。该雷达具有功率大、天线增益高、系统噪声温度低等技术优点，在月球等自然天体目标探测方面也具有重要应用价值（其信号处理和数据反演方法与电离层探测存在显著不同）。

曲靖雷达属于地基脉冲机械扫描雷达，采用抛物面天线与速调管发射机技术，自投入运行以来在电离层探测与空间碎片探测方面均取得了良好的结果。该雷达具有很高的功率孔径积，可发射相位调制后的左旋圆极化波，并接收右旋圆极化波，具体参数详见表3。利用该雷达开展了一系列月球单站探测初步实验，实验时采用程序引导跟踪模式，波束中心始终指向月球中心。由于月球的角直径为该雷达波束宽度的 $4 0 \%$ ，故单个脉冲探测可覆盖整个月球的向地球面。

# 表3曲靖雷达性能参数

Tab.3 Performance Characteristics of the QJlSRRadar   

<html><body><table><tr><td>Antenna</td><td>QJISR</td></tr><tr><td>Diameter D，m</td><td>29</td></tr><tr><td>Transmitter power Pt，MW</td><td>2</td></tr><tr><td>Transmitter frequency fo，MHz</td><td>500</td></tr><tr><td>Gain Gt dB</td><td>41</td></tr><tr><td>Beam width Bw</td><td>1.3</td></tr><tr><td>Pulse duration Tp us</td><td>390</td></tr><tr><td>Pulse repetition Trms</td><td>12</td></tr></table></body></html>

# 3初步结果

# 3.1回波的时间延迟

曲靖非相干散射雷达波束指向月球，发射高功率相位编码脉冲（采用13位巴克码编码方式，脉冲重复周期为 $1 2 \mathrm { m s }$ ，码元宽度为30us），通过对月球回波进行简单的脉冲压缩与相干处理，即可得到月球表面不同时延位置的回波功率。下图4为2020年09月11日02时02分（UTC)接收到的月球散射回波功率-时延剖面，其中“红色”曲线代表曲靖雷达测量结果，“蓝色”曲线代表Arecibo雷达（68cm波长）的测量结果，横坐标为时间轴，以雷达下点处（雷达-月球质心连线在月面上的交点）为起始时刻，并以月球边缘回波为终止时刻（相对起始时刻约为11.667ms），纵坐标代表归一化后的回波功率，可以直观看出两台设备的测量曲线在幅值和趋势上均十分接近。在地基雷达对月球的观测中，雷达波的入射角一般从月球正面中心处的 $0 ^ { \circ }$ 连续地变化到边缘处的 $9 0 ^ { \circ }$ 。月球回波在雷达下点处最强，随着延迟深度的增加迅速衰减，随后缓慢下降。这是因为在雷达下点附近，波束入射角较低，回波主要来自准镜面反射；随着入射角的增加，回波主要来自裸露和埋藏的岩石产生的漫散射。准镜面反射主要受月表斜度、菲涅尔反射系数等因素的影响，且对入射角敏感；漫散射主要受对应波长下月表粗糙度、岩石密度和化学成分等因素的影响，且功率约正比于cos $\varphi$ ， $\varphi$ 为雷达入射角。

![](images/95fef751db2dd76c7dd625e11d3ccf65fea8bdc379177db3daf0e439adf384cd.jpg)  
图4曲靖非相干散射雷达月球回波功率-时延剖面测量结果

# 3.2回波的多普勒频率

2019 年至今，基于我国深空站和射电望远镜，开展了一系列的连续波信号双基地探月试验。在2019年04月26日02时30分（UTC）开始的一小时观测中，实际回波信号的多普勒（如图5所示）与公式（4）估计得到的多普勒理论值基本一致，约 $1 5 \mathrm { H z }$ 的残余差异来源于月球历表的使用和计算。回波信号多普勒的标准偏差约 $7 \mathrm { H z }$ ，测速精度与上下站双基地的时频系统有关系。另外，回波反射信号的频谱展宽约 $3 5 \mathrm { H z }$ ，与公式（5）估计得到的理论频谱展宽值一致。

![](images/ac7acfe36fa7ce038c12fe0a9d9c58ba6dd1c0f339555e909cd279c707c666eb.jpg)  
Fig.4 Lag profile of lunar echo power by Qujing ISR radar   
图5SC和0C月球回波多普勒的理论值和观测值差异

Fig.5 Difference between measured and calculated Doppler frequency shifts for SC and OC echoes.

利用月球星历补偿月球相对雷达的平动带来的影响后，我们得到了曲靖雷达探测的月球不同时延处的回波频谱。结合雷达的脉冲长度和月球延迟深度，我们将回波分为24个区间，对各个区间分别求出信号的频谱，结果可见图6。该图从上至下依次展示连续6个区间的频谱，且用不同颜色表示，横坐标代表信号频率，纵坐标代表功率谱强度。由图可知，第1区间（图6第一行蓝线）功率谱的幅值最强，随后依次减弱，这与回波功率随时延的衰减规律有关（见图4)。各区间的频谱具有相同的分布特征：均存在中心频率为-590.5Hz、3dB带宽约为5.91kHz的主特征，对应的相干时间为169.2us；另外，在主特征附近，存在频带过渡更为平缓的副特征，其3dB带宽约为18.2kHz,对应的相干时间为54.95us,这在第1区间的频谱中尤为明显；最后，随着延迟深度的增加，频谱的两个弱特征逐渐显现（可见图6第4行），其中心频率分别为-17.33kHz与16.14kHz，3dB带宽为2.64kHz，对应相干时间378.8us。频谱中心与零频有略微偏移，初步分析认为是对平动速度的补偿时存在一定的误差所致（本次实验中约 $1 7 7 \mathrm { m / s } )$ 。月球回波频谱包含了一定的地形特征（如月面的平均斜度等信息），后续将进一步对其验证和分析。

![](images/585ffeac70c31d00228a450b415499dca3eaf4ebe9e79dca057c5d6556fa4af3.jpg)  
图6曲靖非相干散射雷达24个月球延迟深度位置回波功率谱

Fig.6 Power spectral density of Lunar echoes from 24 lag-depth positions by QJISR radar

# 3.3回波的幅度特性和雷达反射率

通过 $\mathrm { K m }$ 接收天线的回波能量，根据公式（6)，基于喀什深空站和昆明40米射电望远镜的连续波信号双基地探月试验获得的雷达反射率 $\hat { \sigma } _ { O C } = 0 . 0 6$ ，此处考虑10秒积分时间内，$S N R _ { O C } = 1 2 1 0 0 0$ 。该雷达反射率值反映的是以“嫦娥三号”着陆器位置为中心、直径503公里月面照射面积的雷达反射率平均值。

利用距离-多普勒成像技术，实现了基于曲靖雷达月面不同位置雷达反射率的提取。根据时延分辨率(30us)和相干积累时间(90s)计算得到最小平面分辨单元尺寸为 $4 . 5 \times 3 . 7 \mathrm { k m }$ 。对各单元雷达反射率进行统计，得到图7中的分布结果。计算可得月壤雷达反射率的平均值为0.066，对应的介电常数约为2.8，这与美国Arecibo射电望远镜（68cm波长）探测结果相近[14]。需要说明的是，因为在实验时未对雷达进行精细标校，以上结果可能存在较大的偏差，后续将对雷达系统参数等进行标校。

![](images/7568e7dcd62e9fb6a63c06c670347d2159cc05a84cfb59e2b6b8535678ff8d67.jpg)  
图7曲靖非相干散射雷达月球探测雷达反射率统计分布

结合距离-多普勒矩阵，对频谱域的每个点均计算雷达反射率，下图8展示了第谷环形山区域 $\boldsymbol { 1 0 } ^ { \circ } \times \boldsymbol { 1 0 } ^ { \circ }$ 的雷达反射率图，可以看出该区域反射率最高可达近0.6，明显高于月面平均值（0.066)。但因为目前月球成像时存在南北半球模糊问题以及实验时距离向和方位向分辨率都较差等原因，尚无法识别出环形山的轮廓等地理信息。未来升级至铷钟系统以及选取码宽更短的码型后（如5us)，有望极大提高成像质量。

![](images/a20be2222f2529d478fd3bd654d0323358e4821fe530dce7ddf358843659795d.jpg)  
Fig.7 Statistics distribution of lunar radar albedo measurements by QJISR radar   
图8第谷环形山 ${ 1 0 } ^ { \circ } \times { 1 0 } ^ { \circ }$ 区域的雷达反射率图，  
Fig.8 Albedo map of Tycho crater ${ 1 0 } ^ { \circ } \times { 1 0 } ^ { \circ }$ region.

# 3.4回波的极化特性和圆极化率

在喀什深空站和昆明40米射电望远镜的连续波信号双基地探月试验中， $\mathrm { K m }$ 站获得的圆极化率 $\mu _ { C } = 0 . 4 4$ ，如图9所示。“嫦娥三号”着陆器所在的虹湾地区作为月表上最为平坦的地区之一，具有独特的地理位置与地质环境，一直以来都是月球科学问题研究的热点地区之一。后续通过对虹湾地区高分辨率、多波段观测数据进行地质解译，将会有助于对虹湾地区及其与雨海关系的了解。

![](images/70fdaddf3d6a233a7e9d0046bd12df44c72530f47395e98827b8f2ab723c40c1.jpg)  
图9Km站同时收到的月球化OC(红实线)回波和同极化SC(蓝虚线）回波能量谱

Fig.9 Opposite(OC)(red solid line)and same circular polarizations (SC)(blue dashed line)echo power spectra from the Moon obtained at station Km.

# 3.5月球成像

利用距离-多普勒成像技术，并通过坐标系转换后我们得到了直角坐标系下（设自转轴为z轴，赤道轴为y轴， $\mathbf { x }$ 轴与y、z两轴满足右手定则）月球近地球面不同位置的散射功率，最后在行星表面坐标系下进行绘制，结果在图10中展示。横轴代表月球的经度（自西向东，范围为 $- 9 0 ^ { \circ } { \sim } 9 0 ^ { \circ } )$ ，纵轴代表月球的纬度（自南向北，范围为 $- 7 0 ^ { \circ } { \sim } 7 0 ^ { \circ }$ )。由于距离分辨率较低，视赤道附近（图中“黑色”条纹）成像模糊。可见图像关于视赤道基本对称，这是因为雷达波束覆盖整个月球近地球面，在成像时存在南北半球模糊问题，即无法区分南、北半球的回波。通过与月面第谷环形山（Tycho，位于南半球，坐标为 $4 3 . 3 1 ^ { \circ } \mathrm { E } 1 1 . 3 6 ^ { \circ } \mathrm { W } )$ 位置对比（在图中用红色圆圈标记)，发现两者基本重合，初步验证了曲靖非相干散射雷达对月球成像的有效性。

![](images/8e6f1d332b73aba5ea958ab66b5bb2f18ca77253e169dcc3ebf6e933a041d1b4.jpg)  
图10曲靖非相干散射雷达月球成像结果 Fig.10 Lunar mapping of QJISR radar

# 4结论和展望

雷达探测实时性强、测量信息丰富，可以主动地、全天候、全天时地对空间目标进行探测。以离地球最近的天体——月球着手，研究了地基雷达天体探测的数据处理方法，并利用中国目前现有的上行雷达装备和射电望远镜站网，成功地接收了月球反射的雷达信号。所得到的结果证实了利用射电天文望远镜和深空雷达组成的双基地雷达探测模式对月球观测的可能性和有效性。结果分析表明，回波光谱的信噪比和多普勒展宽值与先验估计值一致。我们得到了圆极化率 $\mu _ { \mathrm { c } }$ 为0.44，得到MareImbrium月球区域的雷达反射率 ${ \widehat { \sigma } } _ { 0 \mathrm { C } }$ 为0.06。首次从曲靖非相干散射雷达月球散射回波中获取了月球回波功率-时延分布图，分析了回波基本特征。利用距离-多普勒成像技术，初步提取了月球不同区域的雷达反射率，初步统计可知月表的平均雷达反射率为0.066，初步得到了月球二维像，利用月球第谷环形山的位置侧面验证了月球成像方法的有效性。研究结果既可为我国现有的月球探测数据提供验证，也可以为建立月球基地的选址提供重要参考。

我国目前广泛分布不同频段的窄带跟踪、宽带成像测量雷达，射电望远镜也具备高灵敏度的多频段接收能力，尤其是中国“天眼”FAST（Five-hundred-meter Aperture Spherical radioTelescope）具备3GHz以下的雷达回波信号接收能力，后续将进一步拓展雷达上行与射电望远镜的多波段联合探测，以及数据处理等技术研究。

我国目前还没有专门用于对太阳系天体进行观测的地基雷达设备，鉴于我国月球探测的现状和发展、正在执行的火星探测任务、以及未来的小行星预警计划等，有待建设一套地基雷达观测系统，不局限于探测单一类型的天体，可以对多个太阳系天体进行探测。整套系统的建设、运行费用相对于昂贵的航天项目来说是很经济的，具有巨大的灵活性与经济性优势。地基雷达探测可作为未来的发展方向，不仅应用于天文研究和国家重大需求等方面，也将大力推进我国未来深空探测以及行星科学研究的发展。

# The status of Earth-based radar astronomical

# observations of the Moon in China

Jing SUN'， Song YANG²， Feng ZHOU²， Zonghua DING²，Lei LIU,Jianfeng $\mathsf { C A O } ^ { 4 }$ ，Songtao HAN4， Jinsong PING1

(1.National Astronomical Observatory,Chinese Academy of Sciences,Beijing 1OolO1, China;

2.China Research Institute of Radio-wave Propagation, Qingdao 2661O7, China;

3.Xidian University, Xi'an 710071,China;

4.Beijing Aerospace Control Center, Beijing 10oo94, China)

Abstract:Earth-based radar astronomical observations provide information on surface characteristics，orbits，and rotations for a wide variety of solar system objects.Based on compound radio telescopes,in cooperation with the Chinese radar transmittrs,we present the current ground radar astronomical observations of the moon. The time delay and spectrum of the reflected radio signals were measured. Radar albedo of the observed region was determined with X band and UHF band,respectively. The power ratios of the reflected signals with left- and right-hand circular polarizations was also determined, allowing us to study the radar reflectivity and near-surface wavelength-scale roughness of the moon. The lunar mapping with QJISR radar confirms the prospect of the Earth-based radar astronomical technique. Future developments on radar astronomy are also discussed in the paper.

Key words:Earth-based radar; Moon; Radar albedo; Circular polarization ratio

# 参考文献： 献：

[1］王瑞刚，苏彦，洪天晟，戴舜，刘晨迪.表层穿透雷达在月球和深空探测中的应用[J].天文研究与技术，2020,Vol. 17, No. 4,492-512.   
WANG Ruigang,SU Yan, HONG Tiansheng,DAI Shun,LIUChendi.AReviewof Applicationof Surface Penetrating Radar in the Moon and Deep-space Exploration[J].Astronomical Research and Technolog,2O20,Vol.17,No.4,492-512. [2]丁春雨，封剑青，郑磊，戴舜，邢树果，肖媛，苏彦．雷达探测技术在探月中的应用[J].天文研究与技术,2015, 12(2): 228-242.   
DING Chunyu,FENG Jianqing, ZHENG Lei,DAI Shun, XING Shuguo, XIAO Yuan,SU Yan. A Review of Applications of Radar-Detection Techniques in Lunar Explorations.Astronomical Research and Technolog,2O15,12(2): 228-242. [3]郑磊.地基雷达对月成像数据处理方法研究[D].北京：中国科学院国家天文台,2011.   
ZHENG Lei. The research on Data Processing of Ground-based Radar Mapping of Lunar Surface[D]. National Astronomical Observatories,2011.   
[4] Thompson TW. Atlas of lunar radar maps at 70-cm wavelength [J].The Moon,1974,10(1): 51-85.   
[5]Schaber G G,Thompson TW,Zisk SH.Lava flows in Mare Imbrium: an evaluation of anomalously low Earth-based radar reflectivity [J]. The Moon,1975,13(4): 395-423.   
[6] Stacy NJS,CampbellDB,FordPG.Arecibo Radar Mapping of the Lunar Poles: ASearch for Ice Deposits[J]. Science, 1997, 276(6): 148-152.   
[7]ShkuratovYG,BondarenkoNV.Regolith layer thicknessmapping of the Moonbyradar andoptical data[J].Icarus, 2001,149(2):329-338.   
[8]Campbell BA, Campbell DB.Regolith properties in the south polar region of the Moon from 70-cmradar polarimetry [J]. Icarus,2006,180(1): 1-7.   
[9]Fa W,Wieczorek MA.Regolith thickness over the lunar nearside: results from Earth-based $7 0 \mathrm { c m }$ Arecibo radar observations [J]. Icarus,2012,218(2): 771-787.   
[10]Lei Liu, Zuobang Zhou,Feng Zhou,Xiaoran Shi.A New 3-DGeometry Reconstruction Method of Space Target Utilizing the Scatterer Energy Accumulation of ISAR Image Sequence [J]. IEEE Transactions on Geoscience and Remote Sensing,2020,58(12),8345-8357.   
[11]Bruce A.Campbell. Focused 70-cm wavelength radar maping of the Moon [J]. IEEEtransactions on Geoscience and remote sensing,2007,45(12): 4032-4042.   
[12]Jing Sun,Jinsong Ping,Yuri Bondarenko,DmitryMarshalov,Fengchun Shu,Jianfeng Cao,Songtao Han,Lue Chen, Wen Chen.Promoting Earth-Based Radar Astronomical Observations of the Moon.Sensors,2020,20,1874.   
[13]Ding Zonghua, Wu Jian, Xu Bin, Xu Zhengwen,Dai Liandong.The Qujing incoherent scatterradar:system description andprelminarymeasurements.Earth,Planets and Space,2018,70-87,htps:/doi.org/10.1186/s40623-018-0859-8. [14]T.Hagfors. Remote probing of the moon by infrared and microwave emisions and byradar[J]. Radio Science,1970, 5(2): 189-227.