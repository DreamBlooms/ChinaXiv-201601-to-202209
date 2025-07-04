# 火星轨道器次表层探测雷达数据处理技术与现状研究

洪天晟1,2,3，苏彦1,2,3，王瑞刚1,2,3，戴舜1,2,3，刘晨迪,2,3，李春来1,2,3（1.中国科学院国家天文台，北京 100012;2.中国科学院月球与深空探测重点实验室，北京100012;3.中国科学院大学，北京100049)

摘要：火星是重要的地外天体探测目标之一，对火星表面进行的探测、研究表明火星表面會经存在液态水，水是生命存在的基础与前提条件，因此在次表层寻找不同形式的水是目前火星探测的重要科学目标之一。近十七年来，欧洲火星快车上搭载的火星次表层和电离层探测先进雷达以及美国火星勘测轨道器上搭载的浅表层雷达开展了对火星次表层的大量探测，由于雷达的工作原理，雷达获取的原始回波数据需要经过距离向、方位向处理、电离层校正等数据处理步骤才能完成成像，从成像数据中提取科学信息，取得了众多科学成果。火星次表层探测雷达的数据处理技术在火星次表层探测上发挥了不可或缺的作用，具有很强的代表性与参考价值。综述目前利用雷达对火星次表层展开的探测与研究，介绍了火星次表层探测雷达数据处理技术，列举了取得的部分科学成果，并展望将要投入使用的火星次表层探测雷达。

关键词：雷达；火星；次表层；距离向处理；方位向处理；电离层校正

中图分类号：TN959.74;P185.3

# 0引言

火星是太阳系中的类地行星之一，相比起同为类地行星的水星、金星，火星在大气、地貌等方面与地球相似度较高，是太阳系内与地球相似度最高的行星。从人类进入航天时代开始，火星就是最重要的地外天体探测目标之一，美苏以及其他国家总计进行了45次火星飞越、绕飞、着陆以及巡视的探测尝试[1]，仅次于'对月球的124次。火星探测的第一次高峰期出现在1960-1975年，在此期间水手4号、6号、7号对火星进行了飞越探测，近距离拍摄火星，为人类提供了火星表面的清晰图像。水手9号首次完成了对火星的绕飞探测，而海盗1号、2号在火星表面完成了软着陆2]，同期苏联也发射了多个探测器进行火星探测[3]。1992年之后火星探测再次迎来高峰，火星快车（Mars Express）、火星勘察轨道器（Mars Reconnaissance

Orbiter,MRO)、火星全球勘测者（Mars Global Survyor,MGS）、凤凰号着陆器、勇气号、机遇号、好奇号火星车等探测器都抵达火星开始探测任务，对火星进行了多波段光学遥感、雷达次表层探测、着陆巡视等多种方式的探测，绘制了火星表面的地貌细节、矿物分布、表面亮温分布，对火星次表层结构进行了研究，在火星上寻找液态水及其存在过的证据。

对火星表面进行的一系列探测结果表明，火星表面曾经有液态水存在，而在火星南极冰盖进行的次表层探测甚至为液态水的存在提供了直接观测证据，欧空局（ESA）火星快车探测器上搭载的MARSIS雷达于2012年至2015年间在火星南极冰盖区域采集到的数据显示，冰盖表面下1.5千米处存在宽度达到20千米的液态水湖[4]。火星上存在不同状态的水这一发现激发了人类寻找火星生命存在痕迹的热情。

在火星搜索各种形态水的存在以及生命痕迹的过程中，一种先进的探测仪器发挥了极大作用，这种设备被称为轨道器次表层探测雷达，与车载次表层探测雷达相比，星载雷达最大的特点是使用了合成孔径技术，通过对图像进行顺轨方向的处理，在离地面数百公里的高度上仍能取得较高的方位向分辨率。轨道器次表层探测雷达的探测深度可达数百米甚至几千米，但其分辨率较低，一般为数十米。目前只有欧空局(ESA)2003年发射的火星快车探测器(MarsExpress）和美国航空航天局（NASA）2005年发射的火星勘测轨道器上搭载了此类仪器，分别简称为MARSIS 和 SHARAD。MARSIS全称 为Mars Advanced Radar for Subsurfaceand Ionosphere Sounding（火星地表和电离层探测先进雷达），SHARAD全称为ShallowSubsurfaceRadar（浅表层雷达）。而在我国“嫦娥”探月工程中大放异彩的车载次表层探测雷达目前还没有随火星车或者着陆器登陆过火星，开展相应的次表层探测。

我国的首次火星探测任务已于2016年正式立项，2020年7月23日于海南文昌发射场由长征5号运载火箭发射，探测器包括轨道器和巡视器[5]，轨道器与巡视器上都搭载了次表层探测雷达。美国Mars 2020任务探测器于2020年7月30日由AtlasV541火箭在卡纳维拉尔角空军基地发射升空，阿联酉的火星探测任务“希望号”探测器于2020年7月20日由H-IIA火箭在种子岛航天中心发射升空，欧洲与俄罗斯的联合火星探测任务ExoMars原定于2020年发射，由于疫情等多种原因推迟至2022年，火星探测又将迎来一次高峰，且Mars 2020任务和ExoMars任务中巡视器都搭载了车载次表层探测雷达。如果各国的探测器都能顺利抵达火星展开探测，则如何处理、分析、解读火星次表层探测雷达的数据将成为火星次表层探测的一大重点、难点。本文综述了国内外利用雷达探测技术进行火星次表层探测的发展成果与技术进展，对于未来更好利用火星探测任务提供的雷达数据有一定意义。

# 1次表层探测雷达对火星探测技术发展

雷达发射的电磁波穿透性强，且不依赖于光照，具有全天候性，在月球的次表层探测中发挥了很大作用，1972年搭载于阿波罗17号的阿波罗月球探测仪、2007年日本SELENE搭载的月球雷达探测仪以及嫦娥3号、4号月球车上搭载的测月雷达都对月球进行了次表层探测，并在澄海、危海与雨海等地都探测到了次表层分层结构，嫦娥3号月球车“玉兔”与嫦娥4号月球车“玉兔2号”都搭载了配置相同的月球穿透雷达（Lunar Penetrating Radar,LPR），工作频段为40-80MHz与 $2 5 0 { \mathrm { - } } 7 5 0 ~ \mathrm { M H z }$ ，最大探测深度超过100米，并拥有优于1米的距离分辨率，进行巡视路线上月球次表层与月壤结构探测[7]。3号雷达在月球雨海的巡视区中展开探测，根据探测结果估计风化层深度为4-6米，并确定约330米深处存在月岩层[8]。嫦娥4号搭载的雷达在月球背面的冯卡门撞击坑获得了远深于3号着陆区的探测深度，并探明了巡视区的三个次表层分层结构：风化层（深度12米）、嵌入岩石的粗糙材料（深度12-24米）以及粗糙与精细物质的交替层（深度24-40米）[9]。火星探测距离远，能量需求大，难度较高，早期的火星探测一直以光学为主，雷达较少被用于火星探测，目前地基雷达观测和轨道器次表层探测雷达探测已被正式用于火星探测，已登陆火星的巡视器上都没有搭载次表层穿透雷达，我国的火星车次表层探测雷达与美国Mars 2020任务巡视器“毅力号”（Perseverance）火星车搭载的RIMFAX中将诞生第一台登陆火星的车载次表层探测雷达。

地基雷达探测是雷达技术应用于火星探测的最初方式，进行观测的设备为位于美国波多黎各的阿雷西博（Arecibo）305米望远镜以及位于美国加利福利亚的金石（goldstone）70米射电望远镜[10][I]。地基雷达观测基于随机长编码延迟-多普勒技术以及干涉延迟-多普勒技术[10]，在火星冲日时对火星表面进行观测，获取了火星表面的高程、反射率、粗糙度等信息，并进行表面物质的介电常数反演。

由于火星的快速自转，入射的电磁波会因多普勒频移发生严重的频率偏移，大大提高探测难度[12]，且地基雷达探测技术无法进行次表层探测。在火星探测进入绕飞与着陆探测阶段后，地基雷达探测更多发挥着陆区选取等辅助功能。

在火星探测确立了在火星次表层寻找不同形态的水的科学目标后，次表层探测的需要推动了次表层探测雷达技术的发展，并逐渐在火星探测器的载荷中占到越来越重要的地位。目前，火星次表层探测雷达已获取了基本覆盖火星全球的探测数据，并识别出一些水冰存在的区域。

# 1.1轨道器次表层探测雷达

次表层探测雷达拥有穿透火星地表，深入火星次表层探测其结构的能力。雷达发射的电磁波能够在一定程度上穿透土壤、冰、岩石等介质，并在两种介电常数不同的介质界面上发生反射、散射和透射，这种特点可以帮助雷达探明探测区域中的地质分层，比如干燥的土壤与冰层的界面，冰川与基岩的分层，孔隙中充满冰或液态水的多孔岩石以及冰盖下液态水的存在等。电磁波在各种介质中并非无损耗传输，电磁波在穿越介质时会由于介质吸收而发生衰减，一种介质对电磁波的吸收能力一般与这种介质的介电常数和电磁波的波长有关，波长越长，频率越低的电磁波在同种介质的中传播，衰减的程度越小，穿透能力也越强，能探测到更深处的地质结构。因此，次表层探测雷达工作频率一般在1MHz-1GHz之间选取，而雷达的带宽决定了分辨率，带宽越小，深度上的分辨率越高。为了实现对次表层进行高精度的雷达探测，并满足探测深度的要求，雷达的工作参数设计受到了很多限制。MARSIS在次表层探测模式下使用的工作频段为 $1 . 3 { - } 5 . 5 \mathrm { M H z }$ ，被划分为4个子频段，每个频段带宽为 $1 \mathrm { M H z }$ 分别为 $1 . 3 – 2 . 3 ~ \mathrm { M H z }$ 、2.5-3.5 MHz、 $3 . 5 { \cdot } 4 . 5 ~ \mathrm { M H z }$ 、 $4 . 5 { - } 5 . 5 ~ \mathrm { M H z }$ ，真空中波长范围从 $5 5 - 2 3 0 \mathrm { ~ m ~ }$ SHARAD使用的工作频段为 $1 5 { - } 2 5 \ \mathrm { M H z }$ ，带宽 $1 0 ~ \mathrm { M H z }$ ，波长范围为 $1 2 { - } 2 0 \mathrm { ~ m ~ }$ 。MARSIS与SHARAD由于工作参数的差异，分辨率、探测深度等性能参数也存在一些区别（见表1）。

表1MARSIS 与 SHARAD 关键性能参数[10-14]  
Table.1 Main performance parameters of MARSIS and SHARAD [10-14   

<html><body><table><tr><td>Parameter</td><td>MARSIS</td><td>SHARAD</td></tr><tr><td>Orbit altitude（km）</td><td>250-900</td><td>250-320</td></tr><tr><td>Antenna length（m)</td><td>40</td><td>10</td></tr><tr><td>Frequency band（MHz)</td><td>1.3-5.5</td><td>15-25</td></tr><tr><td>Bandwidth（MHz)</td><td>1</td><td>10</td></tr><tr><td>Transmitter Power（W）</td><td>1.5-5</td><td>10</td></tr><tr><td>Pulse length（us）</td><td>250</td><td>85</td></tr><tr><td>Pulse repetition frequency（Hz）</td><td>127</td><td>700.28</td></tr><tr><td>Range resolution（m）</td><td>150（vacuum）</td><td>15(vacuum)</td></tr><tr><td>Horizontal resolution in along-track(km)（km)</td><td>5-10</td><td>0.3-1</td></tr><tr><td>Horizontal resolution in cross-track(km) （km)</td><td>10-30</td><td>3-6</td></tr><tr><td>Penetration depth（km)</td><td>5</td><td>1</td></tr></table></body></html>

# 1.2轨道器次表层探测雷达原理

在次表层探测中，电磁波从环绕器上安装的天线发射，穿越火星的大气层，其中电离层会对电磁波的幅度与相位产生一定影响，随后电磁波抵达火星表面，一部分电磁波被表面反射、散射，最终被雷达天线接收，还有一部分穿透火星表面进入次表层，穿透介质，在介电常数不同的次表层分层界面处发生反射。假设轨道器轨道高度为H，c为真空中的光速，则在发射电磁波后时延 $t _ { 0 } \mathrm { = } 2 \mathrm { H / c }$ 时将接收到来自星下点火星表面的回波，穿透地表进入次表层的电磁波由于介质的原因，会以小于真空中的速度 $\scriptstyle { \mathrm { v = c / n } }$ 传播（n为介质的折射率），假设两个介电常数不同的分层界面深度为h，则来自这个界面的回波抵达天线的时间为$t _ { 0 } + 2 h / v$ 。由于雷达的波束宽度较宽，覆盖的地表面积较大，表面回波除了星下点表面反射回波还包括星下点外表面散射杂波，表面杂波存在一定时间延迟，可能与星下点次表层回波信号重合，因此星下点次表层回波信号经过介质衰减可能被表面杂波淹没，为了在表面杂波的存在下有效识别次表层回波，必须对回波进行脉冲压缩，且旁瓣必须远低于主瓣，才能实现次表层探测。

![](images/5e8cee9848ed9d88bef6b8ad062af05a09dd54534bbe75978f2b1a22b7093dfc.jpg)

图1（A）星载次表层探测雷达原理示意图5；（B）来自表面与次表层的回波在时间/距离上的分布示意图，强大的表面回波可能会掩盖较弱的次表层回波[13]；（C）考虑到来自星下点外杂波的次表层探测雷达原理示意图[13]。

Fig.1 (A)Operation principle of the space-based subsurface investigation radar[5];(B)Illustration of distribution of surface and subsurface echo in time/range. Strong surface echo masking a weaker subsurface return [13], (C)Operation principle of the space-based subsurface investigation radar in view of off-nadir surface scatters [13].

由于雷达安装在环绕器上，与探测目标的距离至少为轨道高度，按照雷达分辨理论，雷达的方位向分辨率为 $H \cdot \lambda / ( 2 D )$ ，在次表层探测雷达的运行的情境下方位向分辨率将达到数十千米，要提高雷达的方位向分辨率只能通过增大雷达天线的口径，而在太空中这种要求是不切实际的，因此次表层探测雷达都采用了合成孔径技术，将在不同时刻发射、接收的电磁波等效为在同一时刻发射、接收，即合成为一个大孔径天线进行发射和接收。在这种技术的帮助下，合成孔径大小可以视为 $\sqrt { 2 \lambda H }$ ，将其代入方位向分辨率公式,将大大提高方位向分辨率，最优方位向分辨率可以达到 $\sqrt { \lambda \cdot H } / ( 2 \sqrt { 2 } ) ^ { [ 1 4 ] }$ ,因此轨道器次表层探测雷达在数据处理中必须进行方位向处理来实现合成孔径。

电磁波从发射机通过天线发射，穿越电离层，被目标反射再次穿越电离层，最终被雷达接收，这个过程在仿真中可以认为是理想的。实际上，天线和接收通道会对电磁波幅度和相位造成影响，电离层造成的相位失真也严重影响了成像质量，为了保证雷达的成像精度和次表层探测的效果，必须对上述过程造成的幅相失真进行校正。

# 1.3轨道器次表层探测雷达数据处理流程与方法

合成孔径雷达数据处理过程一般可以划分为距离向处理和方位向处理（或多普勒处理），在MARSIS与SHARAD的数据处理流程中，MARSIS较常用的探测模式SS3（subsurface 3,次表层探测3模式）选择在星上完成方位向处理后下传，再在地面完成距离向处理；SHARAD的原始数据在星上完成相关预叠加后，先进行距离向处理，再进行方位向处理。其中还包括对电离层带来影响的校正，使用的方法也有不同。

# 1.3.1距离向处理

合成孔径雷达数据处理中，距离向处理的操作都为脉冲压缩，将接收到的回波信号通过匹配滤波器，将回波信号与发射信号进行相关处理，这种操作能将时间上分散的信号能量集中到一个时间点附近，使得来自地面或次表层界面的回波时间宽度变窄，能量也被压缩到该时间点。MARSIS与SHARAD进行脉冲压缩的操作在细节上有一些不同，MARSIS的脉冲压缩流程为：

1)对回波信号进行一次快速傅里叶变换（FFT），点数为512;2)对作为参考信号的线性调频信号进行傅里叶变换，求得其频谱，再对其进行共轭变换;3)将1）、2）中得到的回波信号频谱与参考信号频谱共轭相乘，进行反傅里叶变换得到脉压结果[15]。

由于天线与收发通道、电离层造成的幅相变化，如果使用理想的线性调频信号作为参考信号，则其与回波信号的相位无法完全匹配，将影响脉冲压缩的效果。因此MARSIS使用的参考信号是由理想线性调频信号与在仪器定标中测得的幅相失真推导得到的，并根据电离层失真对参考信号进一步调整。此外，为了降低脉压后出现的旁瓣，MARSIS使用了汉宁窗（hanning）对参考信号进行加窗处理，加窗可以降低脉压结果的旁瓣，但也会导致主瓣展宽。

SHARAD探测数据下传后通过两种不同的数据处理流程完成距离向脉冲压缩，第一种流程的参考信号基于天线匹配网络定标时测得的信号幅度，测得的定标数据为接收机与发射机温度的函数。使用定标数据得到的参考信号完成脉压后，使用相位梯度自聚焦算法（phase-gradient autofocusing，PGA）进行电离层校正。而第二种流程选择使用线性调频信号频率分量的等幅模型，结果是脉压后旁瓣将出现一种不对称偏置，时延较大的旁瓣幅度较大，选择这种方法是因为其可以在脉压完成后保持两倍的过采样率，有利于在接下来的处理中进行插值。两种处理流程都选择了汉宁窗对数据进行加窗以减小旁瓣。在进行电离层校正方面，第二种流程使用了一种频率决定的相位误差模型，这种模型给出的校正项与总电子含量（TEC）接近线性相关，因此与来自地表和次表层回波信号时延的改变量相关，这种技术适用于探测时太阳天顶角小于 $1 0 0 ^ { \circ }$ 获得的图像。

# 1.3.2方位向处理

方位向处理是合成孔径雷达技术的关键与难点所在，不同的处理方法需要的处理量也不同。轨道器次表层探测雷达的方位向处理方法与普通合成孔径雷达的方位向处理方法在原理上是相同的，因此轨道器次表层探测雷达数据处理使用的方位向处理算法都是在常见的合成孔径雷达算法的基础上产生的。比较常见的合成孔径雷达方位向处理算法包括CS算法(chirp scaling algorithm)[18]、ωk算法[18]、RD算法（range-doppler algorithm,距离-多普勒算法）[19]、BP算法（back-projection algorithm,后向投影算法）[20]等，如果对数据进行非聚焦成像，则可以选择多普勒波束锐化算法[7]等。

RD算法在上世界70年代末就已经被用于合成孔径雷达成像，至今仍在广泛使用。RD算法的基本实现方法为对雷达回波数据矩阵进行距离向脉冲压缩，然后对数据进行方位向傅里叶变换，将数据转换到方位向频域，并用sinc函数进行距离插值完成距离徙动校正，将距离徙动曲线拉直到与方位向频率轴相平行的方向，最后进行方位向压缩完成成像。这种算法通过距离向与方位向的频域处理，所有操作都在一维频域内进行，简便高效，但由于校正距离徙动所需的插值操作，其对长孔径SAR的处理精度有限，且运算量较大。CS算法避免了插值操作，基于chirp scaling原理，通过相位相乘代替时域插值以完成距离徙动校正，并将所有信号的距离徙动分为补余距离徙动与一致距离徙动，即将距离徙动分解出一致的一部分（一致距离徙动），二者的差为补余距离徙动。CS算法的处理流程首先将数据进行方位向傅里叶变换，进行相位相乘补偿补余距离徙动，然后进行距离向傅里叶变换将数据变换到二维频域，与参考函数进行相位相乘，完成距离压缩、二次距离压缩以及一致距离徙动校正，接下来进行距离向傅里叶逆变换、方位向压缩、方位向傅里叶逆变换，完成成像。还有一种ok算法在处理宽孔径或大斜视角数据上具有独特的优势，这种算法使用二维傅里叶变换将数据变换到二维频域，并乘上参考函数，使参考距离上的目标得到全聚焦，其他目标得到部分聚焦，接下来进行Stolt插值完成其他目标的聚焦，将数据变换回时域完成处理[18]。这些算法有各自的优势与缺陷，适应于不同的雷达成像场景，因此算法的选择需要结合雷达数据的具体情况进行分析。

SHARAD选择了CS算法，将方位向上回波的多普勒频移进行分解，将距离徙动划分为不随距离变化的一致距离徙动与随距离变化的补余距离徙动，在处理过程中分别进行校正。这种算法只需要快速傅里叶变换与复乘就能完成[15]，计算量较小，使用简单。具体的处理流程为：1）计算距离徙动，将每道数据的每个时延位置点相对物理孔径中心的距离进行排列；2）方位压缩，用环绕器的轨道高度，径向速度，切向速度确定每个回波数据的差分相位，校正相位可以表示为整个带宽的频率的函数，但实际操作中使用最大的工作频率（25MHz）可以达到最佳的聚焦效果；3）完成相位校正后，对完成距离徙动校正的“等时延线”进行傅里叶变换，取所得频谱的幅值即为一列雷达图像，使用汉宁窗在方位向上压低旁瓣，在顺轨方向约每 $4 6 0 \mathrm { ~ m ~ }$ （1个度间隔）上有128列图像。如果多普勒频域的单位频宽比一个频率分辨单元更宽，则可以进行多视处理。

MARSIS选择的合成孔径处理算法与SHARAD的CS算法有巨大区别，这种算法被称为多普勒波束锐化，在完成对轨道器垂直方向的运动补偿后进行，可以补偿轨道器除垂直方向外其他方向运动带来的相位。这是一种非聚焦SAR技术，获得的图像方位分辨率较低，但计算量相对较小。处理方法为将一帧（frame）内的所有同频率的回波做叠加处理，对其相位进行调整完成相关性叠加。一“帧”（frame）中包含了在一个合成孔径时间接收到的回波信号，由工作频率/波长以及雷达高度决定。经过叠加的回波信号为一个多普勒滤波器，多普勒滤波器可以在接下来的处理中由地面控制选择前表面反射法或对比法，对孔径中心的多普勒滤波器（第0多普勒滤波器）进行电离层相位校正，校正的结果将在用于更正距离压缩中的参考函数。

![](images/7eeab14775dbdb4b29908d0b63d25b4b7b27cbce84bd3aaf6d53414f77e18a38.jpg)  
图2MARSIS多普勒（方位）向处理与距离向处理流程图[15]。  
Fig.2 MARSIS range processing and doppler processing flow diagram [15].

而我国首次火星探测任务“天问1号”的轨道器次表层探测雷达（MOSIR）在数据处理流程设计的过程中，为实现星上实时成像处理，初步使用了BP算法作为方位向处理的算法，而对于下传的原始数据，在地面采用何种方法进行处理，则需要结合数据的实际情况，选择成像效果最好、距离徙动计算最准确的方法。

# 1.3.3电离层校正

MARSIS次表层探测的工作模式与火星电离层等离子体频率非常接近[6],因此电离层对回波时延以及幅度、相位的影响是不可忽略的。在最初的处理中，研究人员提出了两种校正算法，分别为前表面反射法与对比法，文[17]等文献中更多地使用对比法来完成电离层校正，校正效果见图3。对比法通过对电离层相位误差的泰勒展开式中影响较大的系数进行估计以完成校正，并求得电离层电子总含量（TEC），对回波进行迭代脉压，在每次脉压时对回波信号施加估计的相位误差校正项，估计相位误差使用的参数步长由发射的线性调频信号以及回波信号的调频率决定，直到校正精度满足要求，校正后的回波信号能量集中程度最高，此时根据完成校正所得的泰勒展开式系数可以计算出TEC[2I]。

![](images/0d9fa7292916056b5f98145e9a5279ae73d9ac975f6bbe3310b2300e2b877612.jpg)  
图3未校正电离层失真的MARSIS第 5017轨雷达图像（上图）与使用对比法进行电离层校正后（下图）的图像[17]。  
Fig.3 Radargram for orbit 5Ol7 before(top)and after(bottom) use of the contrast method to correct ionospheric distortion [17].

SHARAD的工作频段较高，而火星电离层的等离子体频率一般为几个MHz数量，频率高于电离层等离子体频率的电磁波在穿越电磁波时都会发生衰减，信号传播时间将出现群延迟。在SHARAD的星上处理过程中，相位梯度自聚焦算法（PGA）用于进行校正电离层带来的相位误差，在MARSIS的后期数据处理中，这种算法也被作为对比法等的补充[22]。这种算法可以同时对电离层以及其他来源造成的相位误差进行估计，具体操作需要选取特显点，即含有较高能量且未经补偿的帧，利用散焦图像中相位误差的冗余信息对相位误差的梯度进行鲁棒估计，一般需要经过圆移（将特显点移至方位中心），加窗，相位梯度估计，最后进行迭代校正，完成整个校正过程。需要注意的是,PGA校正的效果与特显点选择有很大关系，如果选取的特显点帧中，相位误差泰勒展开式中影响较大的系数不稳定，则PGA的校正效果将被削弱。

# 1.4MARSIS&SHARAD成像结果对比

从MARSIS与SHARAD的工作参数以及理论探测能力中，可以看出MARSIS的工作频率低，带宽窄，波长长，且合成孔径处理采用的是非聚焦的多普勒波束锐化算法；SHARAD的工作频率较高，带宽宽，波长短，使用chirp scaling算法进行合成孔径处理。因此，MARSIS的探测深度较深，可以探测到距地表3km的次表层界面，SHARAD接收到的来自相同深度的回波太弱以至于被背景噪声淹没无法探测，但MARSIS的探测精度无论是距离分辨率还是顺轨分辨率还是交轨分辨率都明显弱于SHARAD，尤其是距离分辨率，SHARAD的理论距离分辨率只有MARSIS的十分之一。MARSIS与SHARAD在相同区域的探测图像可以作为互补资料，根据MARSIS探测数据在较大尺度上绘制探测区域的图像，确定有精细探测价值的目标区域，再利用SHARAD的数据对该区域火星地表以下数百米可能存在的次表层结构进行高分辨率的成像。

文[15]对相近区域的MARSIS与SHARAD成像进行了比较，MARSIS第3749轨与SHARAD第2026轨探测区域非常接近，可以比较两部雷达对火星相同区域成像的效果，如图4所示[15]。可以看到SHARAD对距地表回波约7us（约数百米深处)次表层界面成像清晰，能反映出次表层较精细的结构，但探测深度较MARSIS较浅，实际成像质量与理论计算的探测精度相符。

![](images/002380f717e67c163c0556eb7b581087de0818a1aa7c2c23844f08f824256c7e.jpg)  
图4.MARSIS 第3749 轨与 SHARAD 第 2026轨探测区域重合部分图像比较[15]。

Fig.4 Comparison between MARSIS radargram orbit 3749 and SHARAD radargram orbit 2O26 on the same Mars area[15].

# 1.5研究现状

MARSIS与SHARAD运行近20年来，基本实现了对火星全球的覆盖，截至2019年仍在发布数据，研究人员根据其发布的数据，完成数据成像处理后，使用搭载在“火星全球勘探者”号探测器上的火星轨道激光高度计（MOLA）获得的高精度火星表面高程数据（空间分辨率接近1°，绝对精度达到 $1 3 \mathrm { m } ^ { [ 2 3 ] }$ ），建立探测区域火星表面地形模型，仿真雷达接收到的表面杂波，筛除与次表层回波发生混杂的表面杂波[24I[25]。获得次表层回波后，结合周边的地形情况，设计多种方法反演出火星表层、次表层物质的介电常数、衰减系数、次表层界面深度等科学信息，推测火星表层、次表层物质成分，获得了众多高价值的研究成果，以此为依据提出了关于火星的气候、地质、轨道等历史演化的一系列推论。

火星北极高原是MARSIS的首个探测区域，覆盖了火星北极周边直径约600公里的面积，主要成分为水冰与少量尘埃，由三个地质单元组成：北方残余冰盖（NRIC）、北极层状沉积（NPLD）、基底层（the basal unit）。文[26]利用MARSIS早期中心频率为3MHz和5 MHz在第1855轨所得探测数据，获得了从北部平原穿过北极层状沉积边缘进入北极层状沉积区域的雷达图像，雷达图像显示表面反射回波分裂成了两个强反射回波，使用MOLA数据对探测区域表面回波进行仿真，排除了较低的反射回波是由表面杂波导致的可能性，即说明该反射回波来自次表层分层界面。两个反射回波之间的时延以及相对回波强度说明基底上覆物质的介电常数与损耗角正切与纯水冰的介电特性相符，用纯水冰的介电常数（\~3）将时延转换为深度，发现反射体的深度与北极层状沉积高于周围地区的高度大致相等，为 $1 . 8 \mathrm { k m }$ ，说明北极层状沉积下的次表层界面仍与周边地区的平原平齐，没有向下弯曲，证明了非常厚的弹性岩石圈的存在，还表明壳幔温度梯度较低。

![](images/2fc08746dd4d42bedfc5bfbd9ff74b6deb03462ab84469cfe5de1e736ef09210.jpg)  
图5（A）第1855轨MARSIS 探测数据（轨道从周边地区进入NPLD）；（B）使用MOLA数据模拟的MARSIS探测到的表面回波（包括星下点回波以及星下点外的杂波）；（C）沿火星快车（Mars Express）探测器星下点轨迹绘制的MOLA数据地形图[26]。

Fig.5 (A) MARSIS data from orbit 1855 as it crossed the margin of the NPLD and came into the NPLD.(B) Simulated MARSIS data if echoes are only from the surface(nadir and off-nadir clutter). (C) MOLA topography along the ground track(red line) of the Mars Express sub-satellite point[26].

南极高原与北极高原相似，也由三个主要地质单元组成：南方残余冰盖（SRIC）、南极层状沉积（SPLD）、阿詹泰山脊构造（DAF），南方残余冰盖表面覆盖着数米厚的干冰，具有较高的反照率，南极层状沉积的结构与北极层状沉积相似。

文[27]根据MARSIS第2753轨的探测数据，发现星下点在通过南极层状沉积边缘时，也出现了表面回波分裂成两个反射回波的现象，且较低的回波使用水冰的介电常数将时延换算为深度后，次表层分层界面符合南极层状沉积周边地区表面地形的延伸，该界面被认为是南极层状沉积的富冰材料与以岩屑为主要成分的基底的分界，MARSIS在南极层状沉积的大部分区域都探测到了这个界面。从图6中可以看出次表层界面回波的幅度很强，甚至在某些区域（如第2682轨）次表层界面回波强于表面回波，这说明南极层状沉积的成分具有极低的衰减系数，损耗角正切约为 $0 . 0 0 1 { \sim } 0 . 0 0 5$ ，可以由此推测出南极层状沉积中水冰的含尘量在0到$10 \%$ 之间。

![](images/6b3f7765bb6dbff95535aba223eff133cb40b75cac008114c57df61388b5c080.jpg)

图6（A)MARSIS第2753轨探测数据；（B）第2753轨星下点轨迹周围MOLA数据地形图；（C）MARSIS  
第2682轨探测数据；（D）第2682轨星下点轨迹周围MOLA数据地形图；（E）第 2682轨探测数据，MOLA测得表面轮廓（黑色实线）与MARSIS 测得的基底形状（蓝色）[27]。Fig.6 (A) MARSIS data from orbit 2753.(B) MOLA topography along the ground track of orbit 2753.(C)MARSIS data from orbit 2682. (D) MOLA topography along the ground track of orbit 2682.(E) MARSIS data  
from orbit 2682. MOLA surface elevations (black line)and MARSIS measured basal elevations (blue symbols)[27]经过MARSIS对南极层状沉积探测的数据积累，文[27]还运用覆盖整个南极层状沉积的  
MARSIS探测数据与相应的MOLA高分辨率火星表面地形高程数据，MOLA表面高程数据减  
去经过插值的MARSIS测得的基底高程数据，得到对应位置的南极层状沉积的厚度，并绘制  
成厚度分布图（见图7）。

![](images/bb989209abf6e87156af10f963097363d0ae5e06de3bf7e97964bb97d21eef23.jpg)  
图7基于MARSIS 测得数据与MOLA表面高程数据绘制火星南极层状沉积厚度分布图[27]。

Fig.7 Map of the SPLD thicknes,based on MARSIS measurements and MOLA surface topography [27]

MARSIS近年来最重大的发现也来自南极层状沉积，文[28]研究了MARSIS在南极高原地区进行探测获得的数据，探测区域以 $1 9 3 ^ { \circ }$ E，81°S为中心，宽度为 $2 0 0 \mathrm { k m }$ ，大部分地区的基底反射回波都较弱，但在某些区域，基底反射回波十分强烈，甚至强于表面回波（图8)。将次表层回波的强度归一化到表面回波的强度，并绘制成归一化后的基底回波强度区域分布图，分布图显示，在 $1 9 3 ^ { \circ }$ E， $8 1 ^ { \circ }$ S附近存在一个 $2 0 \mathrm { k m }$ 宽的次表层回波异常区域。对异常区域的地质结构进行仿真，得到一组归一化后基底回波能量与基底介电常数关系曲线的包络（图9），并以此为依据计算基底介电常数取值对应的可能性，分析仿真结果得到异常区域基底最可能的介电常数取值大于15，这一结论推出了一个合理解释：该异常区域的层状沉积下可能存在液态水，而水中含有镁、钙、钠等的高氯酸盐是其在低温环境下仍能保持液态的原因。

文[29]使用MARSIS对火星经度 $1 3 0 ^ { \circ } \ \sim 2 4 0 ^ { \circ }$ E赤道地区的探测数据，对梅杜莎槽沟构造进行了研究，梅杜莎槽沟构造可能是火星上最年轻的地表沉积区域之一，面积约为 $2 . 1 \times$ $1 0 ^ { 6 } \mathrm { k m } ^ { 2 }$ 。MARSIS探测到了梅杜莎槽沟沉积物与下方地形构造的次表层界面（图10），探测数据揭示了梅杜莎槽沟构造沉积物的厚度与介电特性，该结果支持之前对梅杜莎槽沟沉积物体积的估计范围（ $( 1 . 4 { \sim } 1 . 9 { \times } 1 0 ^ { 6 } \mathrm { k m } ^ { 3 } )$ 。由探测数据中测得的时延给出梅杜莎槽沟沉积物的介电常数实部为 $2 . 9 \pm 0 . 4$ ，由次表层回波的损耗计算出衰减系数为 $\mathbf { \boldsymbol { \cdot } } 0 . 0 0 4 8 \pm 0 . 0 0 2 4 \mathbf { d B } / \mathbf { m } .$ 。上述结果暗示梅杜莎槽沟沉积物可能为干燥的疏松物质或水冰与高介电常数的其他物质的混合物，如果沉积物为后者，则其中的含尘量将高于南极层状沉积的 $10 \%$ 。

![](images/82969ea910f0fc120ff5b4cb9ee0bb7c28a2ec0f8d623feb169680287dbed7ed.jpg)  
图8MARSIS 第10737轨在南极高原获得的探测数据，可见部分地区基岩回波极其强烈，形成高亮区域[28]。

Fig.8 MARSIS data from orbit 1O737 on the Planum Australe.Strong basal reflections can be seen at some locations, where show as highlight area [28].

![](images/fb90d21d2edf3b10ebfbd53915aa098b381c6a74474e6833c48caad3944fbf7f.jpg)  
图9（左）MARSIS 中心频率4MHz下对异常区域地质分层模型进行仿真的结果，蓝色阴影区域为归一化后基底回波能量与基底介电常数关系的曲线包络，黑色直线为实际探测数据中基底回波能量中值；（右)异常区域内外基底介电常数取值分布[28]。

Fig.9 (Left)Results of the electromagnetic simulation of layers model of the bright reflection area computed at 4 MHz The blue shaded area is the envelope of all curves between normalized basal echo power and basal permitivity,and the black horizontal line is the median normalized basal echo power at $4 \mathrm { M H z }$ from the observations;(Right) Basal permitivity distributions inside (blue) and outside (brown) the bright reflection area[28].

![](images/9ca5d9a562af870efea74de64518780d222b2b1e404c719fd8031d946604d03d.jpg)  
图10（A）MARSIS 第2896轨探测数据；（B）MARSIS 第4011轨探测数据；（C)MARSIS 第3868 轨探测数据；(D)MARSIS第 3824 轨探测数据；(E)MARSIS第4117轨探测数据；(F)MARSIS第3996轨探测数据；以上探测数据均在梅杜莎槽沟构造区域采集[29]。

Fig.10 (A)MARSIS data from orbit 2896; (B)MARSIS data from orbit 4011; (C)MARSIS data from orbit 3868;(D)MARSIS data from orbit 3824;(E)MARSIS data from orbit 4117;(F)MARSIS data from orbit 3996; these MARSIS orbit tracks were measured in the Medusae Fossae Formation[29].

SHARAD由于其较高的频率和较宽的带宽，穿透深度较浅，但深度分辨率较高，其对南极高原、北极高原以及其他地区可以进行更为精细的探测，获取了一些MARSIS无法探测到的信息。

文[30]利用SHARAD在火星北半球中纬度的德特罗尼鲁斯.门萨地区的叶状山麓冲积平原的超过100轨探测数据，发现星下点在穿过河谷平原经过舌状岩屑坡时出现表面回波分裂为两个时延不同的回波（图11），利用MOLA数据建模仿真结果确定较低的回波不是由表面杂波导致，该回波为次表层界面反射回波。通过时延估计舌状岩屑坡材料的介电常数实部约为3，推测得衰减率为\~2dB/μ sec，与较纯净的水冰或水冰与少量其他物质的混合物相符。

这种舌状岩屑坡（LDAs）不仅出现在北半球中纬度地区，在火星南北半球 $3 0 ^ { \circ }$ ${ \sim } 6 0 ^ { \circ }$ 都有分布。文[31]使用SHARAD在火星南半球中纬度的海勒斯撞击坑东部边缘附近的多组探测数据，绘制了多幅舌状岩屑坡的次表层雷达图像（图12），经过与MOLA模拟仿真数据的对比以及多轨探测数据间的对比，确定了表面以下的反射回波为次表层界面回波，分析图像表明次表层介质十分均一，且大型岩石碎片不是其中的主要组分。测量探测数据中雷达波穿越介质造成的衰减，以及表面回波与次表层回波的关联，测得衰减系数最大为 ${ \sim } 1 0 0 \mathrm { B } / \mathrm { k m }$ 与纯水冰相符，且证明舌状岩屑坡下掩埋的冰川含尘量不可能高于 $10 \%$ 。较弱的衰减率，以及其测得雷达波速与水冰中的雷达波速类似，与MARSIS在极地层状沉积的观测结果相符，这一结果指出舌状岩屑坡内部的主要成分为水冰，印证了舌状岩屑坡下掩埋着冰川这一假设。

![](images/245567d62c460a0db6ceb3456e9fa991fa3317f81bd03e8e8b4a1e1df24a9fe8.jpg)  
图11 SHARAD 在星下点穿过舌状岩屑坡时获得的探测数据[30]。

Fig.11 SHARAD radargram along the ground track of lobate debris aprons [30].

位于火星北半球中纬度的乌托邦低原直径约为 $3 3 0 0 \mathrm { k m }$ ，多见多边形与扇形洼地地貌，研究人员根据对乌托邦低原进行的形貌分析猜测该区域近地表含有大量水冰。文[32]运用SHARAD探测数据，结合MOLA测得的火星表面数字高程模型，利用陡坡估计次表层反射体深度，拟合后估计近次表层物质的介电常数为 $2 . 8 \pm 0 . 8$ ，符合水冰、石质物质以及空气的混合物的介电特性，估计其中水冰含量在 $5 0 \% - 8 5 \%$ 之间，石质材料低于 $30 \%$ ，孔隙空洞则占到了体积的 $1 5 \% - 5 0 \%$ ，而水冰体积达到了 $8 4 0 0 { - } 1 4 3 0 0 \mathrm { k m } ^ { 3 }$ ，乌托邦低原存在水冰的说法得到了雷达探测数据、火星气候模型以及表面形貌分析的支持。

![](images/08d1acf19eb477f2a256098307325c6ed1a496f12d030b59fa9f648fb76946ae.jpg)  
图12（A）MOLA数据仿真得到的表面杂波；（B）SHARAD第6830轨探测数据，白色竖直箭头指出了与表面杂波仿真数据不相符，且在相邻轨道的探测中也证实存在的回波；（C）将原始探测数据进行时延-深度变换后的图像，假设舌状岩屑坡表面下的成分为水冰[31]。

Fig.12 (A)Simulated surface clutters with MOLA data. (B)SHARAD data from orbit 6830, Vertical arrows identify echoes not consistent with surface clutter simulation and also confirmed in adjacent tracks.(C)Radar data converted into depth assuming a water-ice composition [31].

SHARAD在南极高原、北极高原的探测揭示了层状沉积中精细的分层结构，为火星气候变化、水文变化等方面的研究提供了更多线索。文[33]利用SHARAD在南极高原普罗米修斯舌状高原（PrometheiLingula）获取的探测数据，分辨出南极层状沉积厚度可能为米级的几个次表层分层界面（图13），回波时延范围为1.7\~5.3us、4.3\~5.6us、5.6\~7.1us、11.0\~12.9us，用水冰的介电常数实部3.5将时延转换为深度后，各分层界面深度为 $1 3 0 { \sim } 4 2 0 \mathrm { m }$ 、340\~450m、450\~570 m、 $8 9 0 { \sim } 1 0 3 0 \mathrm { ~ m }$ 。文[34]使用SHARAD第5192轨探测数据绘制出北极高原的次表层地层图，雷达图像中能分辨出不同成分的冰、尘埃、沙占比导致的次表层介质分层界面（图14），且能探测到层状沉积下方的基底层，此外，还探测到一些深达数百米的螺旋槽，这些螺旋槽将浅层的反射回波分为数段，同时，对北极高原边缘的基底层露头进行探测证实了格明娜舌状高原（Gemina Lingula）下不存在基底层，此处的北极层状沉积直接坐落在瓦斯蒂塔斯·伯勒里斯平原构造（Vastitas Borealis Formation）上。探测到的基底较为平坦，说明层状沉积的质量负担并没有造成基底的严重挠曲，与MARSIS的探测结果相符，支持存在极厚的弹性岩石圈这一假设。

![](images/914d94c09e5b93501ca9c9ef7b646811523d2f2ac38e73f8a71bf13f3cda08c8.jpg)  
图13SHARAD第 2202轨探测数据局部放大图。图中显示了4个次表层反射体，这4个反射体将不同介质分隔开[33]。  
Fig.13 Enlarged view of SHARAD data from orbit 22O2.4 subsurface reflectors separate diferent dielectric sequences [33].

![](images/2b084dbd2c849cb257e05d7fd7dfaf20d5208772101d38ff3b33406fb2ae2847.jpg)  
图14SHARAD第 5192轨探测数据，已经过时延-深度转换，使用的次表层介质介电常数为 $3 ^ { [ 3 4 ] }$ 。 Fig.14 SHARAD data from orbit 5192. Range time delay has been converted into depth by assigning real permittivity of 3 below the detected ground surface[341.

# 2国内外未来火星探测雷达载荷

2020年，中国、美国、阿联酋以及一些民营航天企业都已发射探测器开始火星探测任务，而欧洲原定于2020年发射的火星探测器由于疫情等原因推迟到2022年的火星探测窗口。我国、美国的探测器都携带了由巡视器搭载的次表层探测雷达，此外我国的轨道器上也搭载了次表层探测雷达。NASA的MARS2020任务巡视器“毅力号”搭载的雷达为火星次表层实验雷达成像仪（The Radar Imager for Mars subsurface eXperiment），简称为RIMFAX；欧空局ExoMars2022计划的"罗莎琳德.富兰克林"号火星车搭载的雷达实验代号“火星水冰与地下沉积物探测”（Water Ice and Subsurface Deposit Observations on Mars），简称为WISDOM。

# 2.1国外雷达载荷

RIMFAX主要目标为对火星次表层进行成像，获取火星地表下的地质特征，并提供关于次表层成分的信息，探地雷达获取的剖面图像能够揭示层积岩过去暴露在火星表面上的历史，比如撞击、风蚀、河流冲积痕迹等等[35]。

RIMFAX的天线安装在巡视器的尾部偏下的地方，其天线为超宽带蝴蝶结形缝隙天线，使用时将在接收模式与发射模式间来回切换。RIMFAX的工作频段介于SHARAD、MARSIS与欧空局WISDOM之间， $1 5 0 { - } 1 2 0 0 ~ \mathrm { M H z }$ ，采用门限调频连续波（Gated-FMCW）,进行一次全频段扫描需要的时间为 $\mathrm { 1 - 2 0 ~ m s }$ ，具体由其工作模式决定，且工作频段被分为3个单独的扫描频段： $1 5 0 { - } 3 0 0 ~ \mathrm { M H z }$ 、300-600MHz和600-1200MHz。RIMFAX对次表层地貌进行成像的深度超过10米，垂直空间分辨率（距离向分辨率）优于30厘米，沿火星车行进路线每10厘米进行一次水平采样（方位向分辨率）[35]。

由于同时接收来自地表与更深的次表层回波是不可能的，RIMFAX划分了3种工作模式：表面模式、浅层模式和深层模式。3种工作模式的主要区别在于接收机的动态范围窗，表面模式下天线自身反射以及火星表面反射回波在窗内，浅层模式去除了天线自身反射，动态范围窗将表面反射以及浅层反射包括在内，深层模式将天线自身反射、表面反射、浅层反射的回波都置于动态范围窗之外[36]。

RIMFAX在2015年4月、2016年4月分别进行了两次地面验证实验，地点都在挪威斯瓦尔巴特群岛，该区域为冷温复合冰川，表面温度低，部分冰川底部存在较为温暖的分层。2015年数据应用了布莱克曼-哈里斯窗函数，进行补零处理,经傅里叶反变换后得到成像(图15)，而2016年在此基础上还进行了去背景处理（图16）。

![](images/fe6813de9d46be5d04b53900e0803c600e3f087766889ad58dbac01bbaf10bc8.jpg)  
图15（A）2015年RIMFAX外场试验所得120米剖面图；（B）A图中双曲线结构放大后[35]。 Fig.15 (A) The figure shows a $1 2 0 \mathrm { m }$ long radar profile from 2O15 RIMFAX field test.(B) The figure gives a Zoomed in version of Fig. 14A[35].

![](images/e3405a337abf7e3c3b3b8a6d50e9b37089f99e6ac3f20ce683c27070aa827902.jpg)  
图162016年RIMFAX外场试验所得剖面图（表面模式）；长度约为 $4 0 \mathrm { m }$ ，表面以下深度约为 $1 . 5 \mathrm { m } ^ { [ 3 6 ] }$ 。 Fig.16 Radar profile using the Surface Model from 2O16 RIMFAX field test.The length of the profile is around 40 meters and the depth scale is about 1.5 meters below the surface reflection [36l. 欧空局ExoMars 2022计划"罗莎琳德.富兰克林"号火星车搭载的WISDOM雷达科学目标

为研究三维地质结构以及演化历史，探测水在次表层的分布以及存在状态[37]。雷达将与火星车上装备的钻头进行配合，雷达可以沿火星车行驶轨迹在钻探前获取次表层信息。其探测深度约3米，垂直向的空间分辨率可达厘米级。WISDOM可以进行全极化测量，将提供关于三维地质结构、地层学以及近地表的次表层演化历史的关键信息，还能为钻头钻探提供位置信息，避免钻头损坏。

WISDOM是一种特高频步进频率雷达，频段 $5 0 0 ~ \mathrm { M H z } \mathrm { - } 3 ~ \mathrm { G H z }$ ，带宽 $2 . 5 \ : \mathrm { G H z }$ ，其通过天线发射大量连续波信号，每个连续波对应一个频率，持续时间为一个步长 $\Delta t$ ，取值 $2 0 0 \mathrm { u s } ^ { [ 3 7 ] }$ 。系统的带宽由发射频率的数量 $N _ { f r e q }$ 以及发射频率间的间隔决定，WISDOM的 $N _ { f r e q }$ 标称值为1001， $N _ { f r e q }$ 决定了WISDOM的距离分辨率，而频率间隔则决定了雷达的最大模糊距离[38]。接收到数据后，将对数据进行希尔伯特变换（使信号出现 $9 0 ^ { \circ }$ 相移，由于希尔伯特变换只适用于单频率信号，而步进频率信号每个时刻只发射一种频率的脉冲，因此适用希尔伯特变换)，反演出被雷达覆盖环境的复传递函数，再进行反傅里叶变换将信号转变回时间域。此外，还将对回波信号施加不同的频域窗函数以减小距离向的旁瓣，进行滤波以提高信号的信噪比（图17）。

![](images/ebb68e038a4ff36cf62d055754b4fffd73bbd55934e62b61be5b3bd5e43958f0.jpg)  
图17从左到右顺序：频率域测得信号；加窗、滤波减小旁瓣、提高信噪比后的信号；(IFFT后)时间域合成响应；时间域合成响应（分贝表示）[38]。

Fig.17From left to right: (a)Measured signal in the frequencydomain. (b)Signal in the frequencydomain after windowing and filtering to reduce side lobes and enhance the SNR.(c)Synthetic response in the time domain (after FFT) linear scale.(d) Synthetic response in the time domain in decibels [38].

随着巡视器行进，雷达接收到的数据经过处理后可以得到次表层地质结构的二维剖面图，此时的数据产品只提供来自各反射体回波的时延。经过对巡视器行进路线的进一步探测，并使用一个金属盘（完美已知目标）进行定标，WISDOM可以获得理想情况下的表面回波幅度，并估计出表层的介电常数，确定表层的厚度。

WISDOM进行了大量的外场地面验证实验，选择地区以干燥或寒冷环境为主，包括智利阿塔卡马沙漠，意大利埃特纳火山，阿尔卑斯山脉冰川以及澳大利亚达赫施泰因冰穴。在多种环境下进行实验采集到的数据都证明WISDOM有能力分辨浅层精细地质结构，为研究地理、地质演化历史提供线索（图18）。以在阿塔卡马沙漠某处被掩埋的河床露头进行的实验数据为例，WISDOM成功探测到河床底部以下约 $5 0 \mathrm { c m }$ 处的沉积物分层[37]。

![](images/1064eda257c65fb117f954a045820e0fcced871466f3f774a6333d58c585aea7.jpg)  
图18阿塔卡马沙漠外场实验WISDOM雷达图像，显示表面下约 $5 0 \mathrm { c m }$ 深处为河床底部沉积物的界面，被掩盖的河床深约 $5 0 \mathrm { c m }$ ，宽约 $7 \mathrm { m } ^ { [ 3 7 ] }$ 。

Fig.18 WISDOM field test radargrams that reveal asmall50-cm-deepand7-m-wide dried channel bed in the

Atacama Desert (Chile) at about 30m from the left [37].

在2010年10月意大利埃特纳火山进行的外场验证实验开始前实验场地出现降水，造成实验场中火成碎屑沉积物含水量较高，但这并没有严重影响到WISDOM发挥其探测能力。WISDOM测得回波数据绘制的剖面图中清晰显示出次表层界面的形状，剖面图显示的最大深度为 $3 \mathrm { ~ m ~ }$ ，探测间隔为 $1 0 ~ \mathrm { c m } ^ { [ 3 9 ] }$ 。由于WISDOM天线的方向图具有方向性，可进行两种同极化探测的配置有助于WISDOM绘制出地表下界面的三维形状，确定其所在位置范围，埃特纳火山以及达赫施泰因冰穴等地的实验数据处理后的产品都证明了这一点（图19）[37]。

![](images/1d96f8d466308955a6c908d5e61f172889058f0f0f8922725b950b34440f5003.jpg)  
图19 达赫施泰因冰穴实验数据进行三维重建得到的基岩3D 形状，基岩覆盖在约 $1 . 5 \mathrm { m }$ 厚的冰层下[37]。Fig.19 3D reconstruction of bedrock beneath a $1 . 5 – \mathrm { m }$ -thick ice layer (ice caves in Dachstein) [37].

# 2.2国内雷达载荷

2020年7月23日发射的我国火星探测计划“天问一号”极具挑战性地将巡视器与环绕器一起送往火星，巡视器上搭载了中国科学院电子所研制的火星车次表层探测雷达，环绕器上搭载了中国电子科技集团第三十八研究所研制的环绕器次表层探测雷达。两部雷达都采用了双频双极化的配置，同时拥有较深的探测深度与较高的精度，双极化探测能力则可能在火星次表层水冰探测方面开拓出一条新的道路。

# 2.2.1火星车次表层探测雷达

火星车次表层探测雷达（Rover Subsurface Penetrating Radar,RoSPR）用于进行火星巡视区地表、次表层的超宽带全极化探测，发射信号为线性调频信号[40]，高频模式下进行全极化探测。低频通道中心频率 $5 5 ~ \mathrm { M H z }$ ，带宽 $8 0 ~ \mathrm { M H z }$ ，脉宽为 $1 4 5 ~ \mathrm { u s }$ ，脉冲重复周期为 $5 ~ \mathrm { m s }$ 高频通道中心频率为 ${ 1 3 0 0 } \mathrm { M H z }$ ，带宽 $1 7 0 0 \mathrm { M H z }$ ，脉宽为 $4 \mathrm { m s }$ ，脉冲重复周期为 $5 \mathrm { m s }$ 。以雷达工作参数推算，在低频模式下，最大探测深度为 $1 1 2 5 \mathrm { ~ m ~ }$ （介电常数 $\varepsilon \ = 4$ ），厚度分辨率为 $0 . 9 4 \mathrm { m }$ （介电常数 $\varepsilon \ { = } 4$ ）；在高频模式下，最大探测深度为 $3 0 \mathrm { m }$ （介电常数 $\varepsilon \ = 4 ,$ ，厚度分辨率为 $4 . 4 \mathrm { c m }$ 。

低频模式使用的天线为两组单极子天线，安装在火星车顶板下方。高频模式使用的天线为Vivaldi 天线，安装在火星车前侧板上，且两组天线极化方式为相互正交[40]。高频、低频天线都是接收天线、发射天线分开，且高频天线每一组天线由两个天线单元组成，两个发射天线单元互相正交，分别定义为H极化发射天线与V极化发射天线；接收天线同样两个单元互相正交安装，定义为H极化接收天线与V极化接收天线。因此，火星车雷达在高频次表层探测中将以这种形式进行全极化探测，两个发射天线依次交替发射正交极化的电磁波，两个接收天线也选通接收相应极化方式的回波，可构成HH,HV,VH,VV的全极化探测（图20）。而低频通道的天线极化方式为HH，无法进行极化探测。

火星车次表层探测雷达进行了多项验证试验以验证其工作性能，并研究数据处理方法。实验室内场试验设置了一个长 $7 \mathrm { m }$ 宽 $3 \mathrm { m }$ ，深 $2 . 5 \mathrm { m }$ 的试验池，其中装满了人造火山灰（介电常数 $\varepsilon = 2 . 9 4 \pm 0 . 5 6 )$ ，并在深度不足 $0 . 5 \mathrm { m }$ 处埋设了金属管、塑料管、石块等物体（图21）。由于场地限制，该试验只使用高频探测模式，试验数据去除了车身造成的多次反射，并进行了去背景操作，数据处理结果中可识别出金属管、塑料管与池底的回波（图22）[41]。火星车次表层探测雷达在2018年、2019年前往陕北榆林黄土、祁连山老虎沟冰川、内蒙古乌兰哈达火山地质公园等地进行外场验证试验，测试其高频、低频模式对多种分层结构的探测性能。与安装在“玉兔"系列月球车上的探月雷达相比，火星车次表层探测雷达不再使用脉冲信号，而改为线性调频信号，这也使得火星车次表层探测雷达的数据处理流程与探月雷达有所不同。

![](images/6da376dd86800186971ae2ed5f081dd0deb742b3e8c2536a0a39130f9e8b3efa.jpg)  
图20高频、低频天线安装示意图  
Fig.2O The location of high frequency and low frequency antenna installtion of RBMSPR.

![](images/f9e760108da959e1f7473ef8919d5361c1412263a51ffdcf43e9c2885a4fa535.jpg)  
图21 填满人造火山灰的试验池[41]。

![](images/693a5807be6048b4b8aabc0e8ebc9d740bab432a973f9eb4282ed2754e31b342.jpg)  
Fig.21 the test pool filled with artificial volcanic ash[41].   
图22 火星车在试验池顶部从北向南移动获得的剖面图[41]。

Fig.22 profile obtained when the rover on the pool top moving from the north to the south[41l.

# 2.2.2环绕器次表层探测雷达

我国搭载在“天问1号”环绕器上的轨道器次表层探测雷达全称为火星环绕器次表层探测雷达（Mars Orbiter Subsurface Investigation Radar，MOSIR）。MOSIR与MARSIS、SHARAD有很多相似的地方，也存在很大差异。MOSIR采用了双极化探测，这种探测方式可以通过计算不同极化方式回波的斯托克斯参量，探测水冰的存在，还可能提供关于火星冰盖内部性质等的线索，这是单极化雷达无法做到的。其工作模式分为甚低频探测模式、低频探测模式、高频探测模式以及测高模式，发射信号都为线性调频信号，各工作模式中心频率、带宽、脉宽、接收时窗、脉冲重复频率、回波叠加数以及采样率等参数不同，见表2所示。与MARSIS、SHARAD相似的是，该雷达也使用了合成孔径技术以提高方位向分辨率。

# 表2三种模式对应工作参数以及性能参数

Table.2 Performance parameters and operating parameters of 3 modes of MOSIR.

<html><body><table><tr><td></td><td>High Frequency Subsurface Sounding mode</td><td>Low Frequency Subsurface Sounding mode</td><td>Altitude Detection mode</td></tr><tr><td>Pulse length(us)</td><td>60</td><td>70(LF）/120（HF)</td><td>120</td></tr></table></body></html>

<html><body><table><tr><td>Data window duration(us)</td><td>95</td><td>120（LF）/170（HF)</td><td>170</td></tr><tr><td>Center frequency (MHz)</td><td>40</td><td>12.5/17.5</td><td>40</td></tr><tr><td>Frequency band (MHz)</td><td>20</td><td>5</td><td>20</td></tr><tr><td>Sampling rate (MHz)</td><td>24</td><td>6</td><td>24</td></tr><tr><td>Pulse repetition frequency</td><td>810</td><td>741</td><td>1000</td></tr><tr><td>(h=265km,Hz) Free-space range resolution</td><td></td><td></td><td></td></tr><tr><td>(m)</td><td>12</td><td>48</td><td></td></tr><tr><td>Horizontal resolution in</td><td>0.5-0.87</td><td>0.75-1.9</td><td></td></tr><tr><td>along-track(km)</td><td></td><td></td><td></td></tr><tr><td>Horizontal resolution in</td><td>5-9</td><td>10-21</td><td></td></tr><tr><td>cross-track(km)</td><td>1.8</td><td></td><td></td></tr></table></body></html>

557 MOSIR的下传数据给数据处理提供了很大空间，既可以将原始数据下传在地面完成脉  
558 压、聚焦等处理，也可以在星上完成成像后下传。以原始下传数据为例，原始数据下传且完  
559 成解包、解压缩、分类后，根据雷达地面大回路数据以及地面定标数据确定收发通道、天线  
560 匹配滤波系数，根据高频与低频模式原始回波数据按照文[20]给出的方法计算出低频、高频  
561 相应的电离层补偿系数，点乘加窗后的标准脉压系数，获得用于脉冲压缩的参考函数，一次  
562 性完成脉压、收发通道补偿、天线响应补偿、电离层补偿。完成脉压后，按照目前设计的数  
563 据处理方法，初步选择使用BP算法完成聚焦成像处理。BP算法实现难度较低，但运算量较  
564 其他合成孔径处理算法（如CS算法等）较大，其原理是将雷达回波数据投影到成像区域的  
565 每个像素点，每个像素值通过计算相应的时延来成像，具体实现方法为在每个FR处计算环  
566 绕器的位置坐标，并计算 $2 1 \times 3 0 0$ 个聚焦点与天线的距离，以距离单元（高频模式下为 $6 . 2 5 \mathrm { m } \mathrm { \ddot { \Omega } }$ ）  
567 为单位划分每个聚焦点对应的脉压后数据，以波长（高频为 $7 . 5 \mathrm { m }$ ，即光速/中心频率）为单  
568 位划分每个聚焦点对应的相位信息，进行复乘、多普勒窗函数处理后进行累加处理，完成成  
569 像。

MOSIR除了利用高频、低频原始数据获得对应的电离层校正系数，还可以利用两种数据星下点回波间的时间差计算出对应的电子浓度总含量TEC，这也是MOSIR的重要数据产品之一。

2019年，MOSIR在内蒙古磴口县进行了地面验证试验，该实验使用热气球悬挂环绕器模型以及安装在模型上的次表层探测雷达进行自由飘飞行试验以及系留飞行试验，系留飞行试验主要进行天线隔离度以及天线增益定标，自由飘飞试验使用测高模式、高频模式、低频模式进行测量，验证测高模式测高精度，经地形矫正、时间校正后测高精度满足10m的设计指标要求。高频模式与低频模式数据用于数据压缩质量验证以及数据处理流程验证，结果满足压缩质量要求，数据处理方法与流程有效。

# 3总结与展望

由于雷达在较低的频段具有穿透能力，且其不受光照限制，可以对大体不受光照的一面或永久阴影区进行探测，在对月球、行星以及小行星的探测上都有较大的应用价值，其穿透能力能用于探测星球的次表层结构、地表以下水冰的存在以及小行星的内部结构等，对行星探测研究目标天体的地质、气候、水文演化变迁历史具有重大意义，且雷达可具备的多极化探测能力使其在水冰以及干冰探测上具有独特的优势。但由于雷达通过发射电磁波，接收物体反射回来的电磁波以进行探测，本身的性质决定其需要通过一系列的数据处理才能反映实际探测到的物理量，且进行轨道次表层雷达探测的电磁波还会受到行星电离层的影响，降低雷达的探测精度。搭载在轨道器上进行次表层探测的雷达一般采用合成孔径雷达技术，需要经过距离向和方位向处理才能将回波转化为可读的图像，而方位向处理方法众多，从合成孔径雷达技术起步至今，已出现chirp scaling算法、波束锐化算法、ok算法、RD（距离-多普勒）算法等方法，目前chirp scaling算法与波束锐化算法被应用于SHARAD与MARSIS的数据处理上，而相位梯度自聚焦算法以及对比法用于电离层校正。

MARSIS与SHARAD是目前已在火星轨道上工作的两部次表层探测雷达，除了通过数据处理对回波进行成像，在后期的研究中，需要使用MOLA探测获得的火星表面数字高程模型对火星表面进行建模，用于火星表面杂波的仿真；使用多种方法估计火星表面以及次表层物质的介电常数、损耗角正切等数据，以此为依据推测地表之下的物质成分、水冰的含尘量等科学信息。

美国于2020年7月30日开始火星探测任务，其巡视器携带一台雷达。我国首次火星探测任务在2020年7月23日发射成功，包括环绕器与巡视器，各搭载一部雷达。我国的环绕器次表层探测雷达拥有双频、双极化探测的能力，虽然是我国首次将此类雷达应用于行星探测，但有MARSIS与SHARAD多年数据处理的技术沉淀以及其对火星大部分地区的高质量探测，我国轨道器次表层探测雷达具有在MARSIS与SHARAD的基础上取得更多成就的潜力。MARSIS与SHARAD对火星的探测覆盖广，成果多，如何在前人已取得如此成就的基础上更进一步是我国雷达研究值得思考的一点。巡视器雷达虽然更改了体制，但拥有“玉兔”1号、2号的技术经验，以及月球车雷达的优秀表现，我们应该对火星巡视器雷达抱有信心。相信我国首次火星探测任务搭载的两部雷达能给我们带回更多关于火星次表层结构、水冰等的科学信息，在行星科学的研究上发挥至关重要的作用。

# 4参考文献

[1]侯建文，张晓岚，王燕，等．火星探测征程[M].Zhong guo yu hang chu ban she,2013.

[2]于登云，孙泽洲，孟林智,etal.火星探测发展历程与未来展望[J].深空探测学报,2016(2):108-113.   
[3]PerminovVG.ThedifcultroadtoMars:abriefhistoryofMarsexplorationintheSovietUnionM].NationalAeronauticsandSpace Administration Headquarters,1999.   
[4]Diez A.Liquid water on Mars[J]. Science,2018,361(6401): 448-449.   
[5]肖媛，苏彦，戴舜，等．雷达对火星次表层的探测与研究现状[J].2017.   
[6]丁春雨，封剑青，郑磊，等．雷达探测技术在探月中的应用[J].ASTRONOMICAL RESEARCH AND TECHNOLOGY,2015, 12(2).   
[7]LiC,XingS,LauroSE,etal.PitfallinGPdatainterpretation:FalsereflectorsetectedinLunarradarcrossctionsby Chang'e-3[J]. IEEE Transactions on Geoscience and Remote Sensing,2017,56(3):1325-1335.   
[8]SuY,FangGYFengJQetal.Dataprocessgandiitialresultsofhang'e-3arpenetratigrdar[J].Reseachinstro and Astrophysics,2014,14(12): 1623.   
[9]LiC,SuYPetieliE,tal.Theoon’fridesallsubsufacestructureuveiledbyChngE-4LunarPenetratigRdar[J] Science advances,2020, 6(9): eaay6898.   
[10] 郑磊，苏彦，郑永春，等．地基雷达技术及其在太阳系天体探测中的应用[J].天文学进展,2009,27(4):373-382.   
[11] Harmon JK, Slade MA,Hudson R S.Mars radar scatering: Arecibo/Goldstone results at 12.6-and $3 . 5 – \mathrm { c m }$ wavelengths[J]. Icarus, 1992,98(2): 240-253.   
[12] MuhlemanDO,ButlerBJ,GrossmanAW,etal.Radarimagesof Mars[J].Science,1991,253(5027):1508-1513.   
[13]CrociR,SeuR,FlaminiE,etal.TheSHAllowRADar(SHARAD)onboardtheNASAMROmission[J].ProceedingsoftheIEE, 2011, 99(5): 794-807.   
[14]FoisF,CrociR,SuR,etalPerformanceresultsoftheSARADinstrumentCOIEInteratioalGeoscienceandRemote Sensing Symposium. IEEE,2007: 119-124.   
[15]FoisF,MecozziR,Iorio,etal.ComparisonbetweenMARS&HARADresults[C/O7IEEEIntermationalGeoscieceand Remote Sensing Symposium. IEEE,2007: 2134-2139.   
[16]JordaR,diGauttarseprssoderstruntJ]aetardSaceiee) 1975-1986.   
[17]OroseiR,JordanRL,MorganDD,etal.Mars AdvancedRadarfor Subsurface and Ionospheric Sounding(MARSIS)afternine years of operation: A summary[J]. Planetary and Space Science,2015,112: 98-114.   
[18]Cumming IG,WongFH,洪文．合成孔径雷达成像—算法与实现[M].2007.   
[19]mithAM.Aaroachtange-DopplerAproceing[J].Iteaioaloualofemotesng,991(2)21 [20]范明意，吕鹏．环绕器次表层探测雷达实时处理技术[J].深空探测学报,2019,5(5):478-482.   
[21]Cartaci,AmataE,CiccetiA,etal.MarsoospretotalctronotentaalysisfroMASsuburfacedata[J].Iarus 2013,223(1):423-437.   
[22]Restano,SeuR,icardiG.Apasgradientutofocsalgoritforthrcoveryfmarsissubsurfcedata[J].EEEGoied Remote Sensing Letters,2016,13(6): 806-810. [23]SmithDE,ZuberMT,olomoSC,etal.TeglobaltopographyofMarsandimplicationsforsurfaceevolutionJ].Sciece999, 284(5419): 1495-1503   
[24]NouvelJF,HeriqueA,KofmanW,etal.Marsisrdarsignalsimulation[CGAS.IEEIteatioalGeociencead Remote Sensing Symposium. Proceedings (IEEE Cat.No. 03CH37477). IEEE,2003,4: 2756-2758.   
[25]llyusinYAOroseiR,WitassOeta.CU:AstticaprtureraarutersiulatorforaetaryeplortioJ]o Science,2017,52(9): 1200-1213.   
[26]PicardiG,PlautJJ,cariD,etal.Radarsondingsoftheubsurfaceofars[J].sience,O0(576):998 [27]PlautJ,cardiG,faeiiiA,etal.Subsurfacedarsoundingof hesouthpolarlaereddepositsofMars[J].siee,20, 316(5821): 92-95.   
[28]OroseiR,LuroSEetieliE,etal.Radarevidenceofsublaciallqdwateroars[J].Since,21,664):9493. [29]Waters,CapbellCarterLetadaoudingofteedsaeFosseFoatioa:qatoraceodosity deposits?[J]. Science,2007,318(5853):1125-1128.   
[30]PlautJJ,SafaeiniliA,HoltJW,etal.Radarevidenceforiceinobatedebrisapronsintheid-northerlatitudesofMars[J]. Geophysical research letters,2009,36(2).   
[31]HoltW,faeiliA,autJJetaRdarsoundigevdeneforriedgaciersintesouthed-latitudesofasJ].iec 2008,322(5905): 1235-1238.   
[32]StuurmanCM,OsinskiGR,HoltJW,etal.SHARADdetectionandcharacterzationofsubsurface watericedepositsinUtopia Planitia,Mars[J]. Geophysical ResearchLeters,2016,43(18): 9484-9491.   
[33]SeuR,bttlatrootrdeits[J].i4) 1715-1718.   
[34]PhilipRJuberrekarS,etalarsorthardeposits:Stratiage,dgeodacalresoseJ]ice 2008,320(5880): 1182-1185.   
[35]HamranSE,BergerT,Brovo S,etal.RMFAX:AGPRfortheMars220rovermission[C2158th Interational Workshopon Advanced Ground Penetrating Radar (IWAGPR). IEEE,2015: 1-4.   
[36]HamranSE,AmundsenHEF,AsakL,etal.TheRIMFAXGPRInstrumentDevelopmentforteMars202RoverMision/rd International Workshop on Instrumentation for Planetary Mission.2O16,1980.   
[37]Ciarleti V,Clifford S,PlettemeierD,etal.The WSDOMradar:unveilingthesubsurface beneaththeExoMars Rovernd identifying thebestlocations fordrillng[J].Astrobiology,2017,17(6-7):565-584.   
[38]CiarletiVCobelC,PlettemeerD,etalWDOGPRdesignedforshallowandhighresolutionsoundingoftheMartian subsurface[J]. Proceedings of the IEEE,2011,99(5): 824-836.   
[39]Ciarleti VCiffrdS,VieaAJ,ealResultsfrotefistfiedtestsof tewsdgr(8exomars mision)CdLar and Planetary Science Conference. 2011,42: 2613.pdf.   
[40] ZhouB,ShenSX,JiYC,etal.ThesubsurfacepenetratingradarontheroverofChina’sMars2O20missionC//1616th International Conference on Ground Penetrating Radar(GPR). IEEE,2016: 1-4.

# Overview of Mars Orbiter Subsurface Investigation Radar Data Processing Technology and Research Using Radar

Iong Tiansheng,23,SuYan123,，WangRuigang,23,DaiShun1,3,LiuChendi123,LiChuai23 (1．National Astronomical Observatories，Chinese Academy of Sciences，Beijing 10ool2，China;

KeyLaboratoryofLunaand Deep-SpaceExploration,National AstronomicalObservatories,Chinese AcademyofSciences，eijing

100012，China; 3．University of Chinese Academy of Sciences，Beijing 1Ooo49，China)

Abstract: Mars is one of the most important targets of extraterrestrial exploration. Investigation and research on mars surface indicate that liquid water once existed on the mars surface,and water is basis and precondition of life. Therefore,one of today's mars exploration scientific objectives is searching for water both solid and liquid in mars subsurface.For the last 17 years ，the Mars Advanced Radar for Subsurface and Ionosphere Sounding (MARSIS) on ESA's Mars Express ，and the Shallow Subsurface Radar(SHARAD) on NASA' s Mars Reconnaissance Orbiter has probed the mars subsurface at a global scale. Because of operating principle of radar, raw data of subsurface investigation radar should be processed in range and azimuth and correct ionospheric distortion in order to generate radargram. Many scientific achievements have been made in extracting scientific information from radargram. Data processing technology played a indispensable role in mars subsurface investigation,which shows great representativeness and reference value.We described the investigation and research about Martian subsurface with radar in this overview, introduced data processing technology using in Mars subsurface investigation, and presented part of findings of MARSIS and SHARAD.We also introduced several future Martian subsurface radars in this paper. Key words: Radar; Mars; Subsurface; range process; azimuth process; ionospheric distortion correction.