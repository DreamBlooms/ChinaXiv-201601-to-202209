# 天体高分辨率软X射线光谱的实验测量标定

张雨佳²，梁贵云(1.中国科学院光学天文重点实验室（国家天文台），北京100101;2.中国科学院大学，北京100049)

摘要：目前利用实验装置产生的原子数据来分析天体X射线观测光谱是一个全新的研究方法，在解决天文观测难题方面取得了很大的进展。为测量高电荷铁离子的高分辨率软X射线光谱，在国家天文台EBIS-A平台上设计并搭建了一个超高真空平场光谱仪。该谱仪在单缝模式下，使用1200槽/ $\mathrm { ' m m }$ 变间距的衍射光栅，其测量波长范围为 $1 1 . 5 \mathrm { - } 1 9 . 8 \mathrm { n m }$ 。针对谱仪的测量结果，首先对可能测量到的辐射进行理论的预测。根据电子束离子阱的工作原理，基于Chianti数据库对Heidelberg-EBIT极紫外光谱数据（ $\cdot 1 1 . 5 { - } 1 4 . 5 \mathrm { n m }$ 波段）进行分析，首先建立线性回归模型来校准由实验系统引起的线强度峰值位置的偏移，然后通过碰撞辐射模型模拟的不同离化态铁离子的软X射线光谱确定了实验测量中FeVII、FeXIX-XXIII的线辐射，并较好的呈现观测谱。此外，在 $1 3 . 2 9 2 5 \pm 0 . 1 0 1 7 8 \mathrm { n m }$ 处发现了相对FeXXIII跃迁线强度较弱的FeXIX和FeXX的混合线，而观测到的光谱没有分辨出这些弱线。因此，接下来的实验测量可以参考这一预测结果来检验谱仪的性能。

关键词：软X射线光谱；国台EBIS-A；超高真空平场光谱仪；谱线认证中图分类号：P141.5 文献标识码： 文章编号：

# 0引言

软X射线光谱是认识、理解热高能宇宙物理性质的重要观测数据，包含了宇宙中从碳到锌丰富金属元素所有K壳层和大多数L 壳层的跃迁辐射[]，这些跃迁谱线可以诊断高温等离子体的温度、密度、辐射通量、天体活动性，以及元素种类与丰度等。在探索宇宙软X射线方面，Chandra 空间望远镜的低能透射光栅光谱仪（LETGS，6-176A）对DA型白矮星GD 246的观测[2，首次清晰地识别出了高度电离的铁元素谱线，揭示了100-170 A波长范围内一系列FeVI、FeVII和FeVII离子的特征谱线。然而，无论是均匀化学成分模型还是化学分层模型，这些Adamczak等人对大气分析建立的具体模型都未能很好拟合观测到的光谱[3]。这表明模型中还缺少相应的物理机制。正在进行的有针对性的实验室天体物理测量，或许能够解决软X射线天文学在这方面的难题。对此，Behar等人l4证明了精确的原子参考数据对于高分辨率光谱的分析是十分重要的。而实验测量能够产生大量可靠的原子数据，其中包括用于电荷平衡计算的电离和复合截面，以及用于解释X射线形成的线表、激发截面和双电子复合速率等。

电子束离子源/阱（EBIS/T）是很好的软X射线实验室辐射源，对天体高分辨光谱学研究有着重要的贡献[。电子束离子源之所以经常被作为基准，用于检验等离子体的光谱模型，是因为它所产生等离子体的电子密度和温度范围完全与天体等离子体的参数空间一致。自电子束离子源出现以来，世界各国陆续建立了自己的EBIT装置开始实验测量，包括Livermore-EBIT对极紫外光谱的研究[7-9]，Heidelberg-EBIT（FLASH-EBIT）在125-265A波长范围内对Fe VI-XV 的测量和诊断[1以及 Tokyo EBIT-CoBIT在极紫外波段内对高电荷铁离子的电子密度的测量研究[1I-12]等，国内由中科院上海应用物理研究所和复旦大学共同研制的上海EBIT 装置也在高电荷态离子共振辐射机制方面取得重要科学产出，这种基于EBIS/EBIT的光谱测量方法在精度上有了很大的提高，并为天体物理学家的拟合模型提供了新的实验检验数据。在电子束离子源平台上搭建起的超高真空平场光谱仪对不同元素的离化态离子进行实验测量，不仅能为软X射线波段的测量提供谱线数据以做参考、完善线表，还能帮助解释未知辐射源，完善理论模型。

平场光谱仪的变间距衍射光栅能够极好的适用于软X射线的光谱，是多数EBIT设备上常用的光谱测量装置。本文的工作是在实验室设计一个超高真空平场光谱仪，为了使衍射光线保持在光栅所定义的平面上，入射角需要仔细设置为一个特定的默认值。因此，光谱仪的对准和角度设置对于精准对焦光谱和精确确定波长非常重要。此外，安装在国家天文台（简称国台）EBIS-A上的平场光谱仪开始测量高电荷铁离子的软X射线之前，本文在Chianti数据库的基础上利用 SASAL 分析方法处理了Heidelberg-EBIT 极紫外光谱仪的实验数据，通过线性回归模型来分析光谱仪的色散方程，并在 $1 1 . 5 { - } 1 4 . 5 \mathrm { n m }$ 波长范围内使用碰撞辐射模型模拟铁离子的软X射线光谱，认证了谱仪未来在该波段能够观测到的谱线，进一步评估谱仪的光谱诊断能力和对于波长测量精确度的期望。

# 1 谱仪设计

从国台EBIS-A电子束离子源阴极受加热发射出来的电子束，经过0.6T的轴对称磁场聚焦，形成电流高达 $2 0 0 \mathrm { m A }$ 的强电子束，与注入腔室中心的原子气体发生碰撞电离，生成的离子被束缚在长为 $6 0 \mathrm { m m }$ 的离子阱中，离子阱由电子束产生的径向电势和外部漂移管提供的轴向电势所形成，阱内的电子束将俘获的离子逐步电离到更高的电荷态，从而在阱区形成 $6 0 \mathrm { m m } \times 5 0 0 \mu \mathrm { m }$ 的软X射线辐射源，其穿过长 $1 0 \mathrm { m m }$ 、宽 $1 0 0 \mu \mathrm { m }$ 的狭缝，使得光源准直打在衍射光栅中心位置，同时降低CCD的背景辐射。1200槽 $/ \mathrm { m m }$ 变间距衍射光栅将不同能量的光反射到焦平面处的CCD上（型号为PIXIS-XO1024B）。整体结构上，谱仪主要由带狭缝的法兰、六通转接法兰腔室、可移动光栅位置的三维平移台和调节光源入射角度的旋转贯通仪、真空泵以及控制CCD位置的二维调整机构组成，如图1所示。

![](images/48b64b9c407bd290e6e6f4564b4f997cedb9eca9ecf759b09163bdf1d0417d7f.jpg)

图1超高真空平场光谱仪设计图。从左到右依次为三维平移台、狭缝、型号为413-CFX6-C100的六通转接法兰、二维调整机构 和CCD。

由于永磁铁聚焦的电子束直径大约在上百微米量级，其直径限制了成像谱线的分辨，因此在紧邻EBIS-A阱区处设置一个入口狭缝是必要的，能够有效提高谱仪的分辨率。另一方面，狭缝的位置设定也需要满足光栅参数。然而，狭缝的大小会影响探测光谱的分辨率和信噪比[13]，狭缝越小，光谱分辨率越高，但是如果光强度不是很强，CCD 接受的信号就很弱，数据获取效率会极小。而国台EBIS-A的优点在于产生强光源，在电子密度为 $1 0 ^ { 1 2 } \mathrm { c m } ^ { - 3 }$ 、电子能量为几个 $\mathrm { k e V }$ 的情况下，单个铁离子辐射率大约为 $1 0 ^ { - 2 0 } \mathrm { e r g \cdot s ^ { - 1 } \cdot c m ^ { - 2 } \cdot s t e r ^ { - 1 } \cdot H z ^ { - 1 } }$ ，以脉冲模式在束流方向引出离子，再利用法拉第杯进行测量，揭示不同电荷态的离子数在 ${ 1 0 } ^ { 3 }  { \sim } { 1 0 } ^ { 9 }$ ，如 $\boldsymbol { \mathrm { H } } ^ { + }$ 为 ${ 6 } { \times 1 0 } ^ { 9 }$ 、 $\mathrm { F e } ^ { 1 6 + }$ 为 $1 . 9 \times 1 0 ^ { 9 }$ 、 $\mathrm { F e } ^ { 2 6 + }$ 为 $2 . 5 \times 1 0 ^ { 3 }$ ，在阱区离子的数目会更高。例如， $\mathrm { F e } ^ { 2 2 + }$ （204号在 $1 3 . 2 9 0 6 \mathrm { { n m } }$ 处的强辐射线，单位时间、单位频率间隔内垂直穿过长 $1 0 \mathrm { m m }$ 、宽 $1 0 0 \mu \mathrm { m }$ 狭缝的辐射能为 $1 . 2 5 6 6 { \times } 1 0 ^ { - 1 2 } \mathrm { e r g { \cdot } s ^ { - 1 } { \cdot } H z ^ { - 1 } }$ ，每秒打在光栅的光子数为0.0084个。考虑光栅的 $\mathbf { \boldsymbol { X } }$ （20射线反射率和光束反射角，每秒投影到CCD上的光子数为0.0019个。由于国台EBIS-A产生光源的稳定性，一般会连续几天进行实验采集信号，从估算结果来看，10天内CCD可以接收到1666.2549个光子，从而平衡CCD与狭缝的关系。

在软X射线范围内，1200 槽 $/ \mathrm { m m }$ 变间距的衍射光栅（型号为SHIMADZU30-002）可以获得较大的反射率，衍射效率的峰值所对应的波长由凹槽深度决定，光栅X射线的反射率可通过美国劳伦斯伯克利国家实验室（LBNL）材料科学部（MSD）X射线光学中心计算得到[14]（https://henke.lbl.gov/optical_constants/）， $1 0 { - } 2 0 \mathrm { n m }$ 波段范围内其反射率在$8 5 \% - 9 0 \%$ 左右，如图2所示。经像差校正的变间距衍射光栅与阵列式探测器相结合形成的光谱仪，适用于分辨辐射源的软X射线光谱。光栅的空间尺寸为 $5 0 \times 3 0 \times 1 0 \mathrm { m m } ^ { 3 }$ ，表面镀金，入射角为 $8 7 ^ { \circ }$ ，凹槽深度为 $1 5 \mathrm { { n m } }$ ，探测器长度为 $2 5 . 3 \mathrm { m m }$ ，完全能够覆盖 $1 0 2 4 \times 1 0 2 4$ 成像区域的CCD相机，平场聚焦的波长范围为 $5 { - } 2 0 \mathrm { n m }$ 。然而受机械几何约束的影响，谱仪实际能够测量的范围为 $1 1 . 5 \mathrm { - } 1 9 . 8 \mathrm { n m }$ 。

![](images/3d500b70f062178f1c5b72569cdabdebfc7b78d427cd4c3d2d70b6c02c1aa671.jpg)  
Fig.1Desigdrawingfortheutrahighvacuumflatfield spectrometer.Fromleftoightare three-dimensional (3D)traslation platform,slit,6 way crosses flange of model413-CFX6-C10,two-dimensional (2D)adjusting mechanism and CCD.   
$\mathsf { A u / r e s i n ~ d } { = } 0 . 8 3 \mathsf { n m } \ s { = } 0 \mathsf { n m } \ \mathsf { N } { = } 1 2 0 0$ at3deg, $\mathsf { P } { = } 0$   
图2 $1 2 0 0 ~ \mathrm { 1 / m m }$ 光栅X射线的反射率。  
Fig.2X-ray reflectivity of the $1 2 0 0 \ : \mathrm { l / m m }$ grating.

光栅放置在大角度旋转贯通仪的伸长臂一端，旋转贯通仪安装在三维平移台上，由三维平移台将它伸入到六通转接法兰腔室的中心处，通过XYZ 正交三轴可以灵活地调整光栅在腔室内的位置，如图1所示。三维平移台的最小刻度为 $0 . 0 1 \mathrm { m m }$ ，灵敏度是 $0 . 0 0 2 \mathrm { m m }$ ，摆动误差小于 $3 0 "$ ，具有良好的稳定性。大角度旋转贯通仪的精度为0.01度，通过自动化操作旋转贯通仪的读数可以精确测定光栅旋转的角度，使得入射狭缝到光栅中心的距离为 $2 3 7 \mathrm { m m }$ ，掠入射角为 $3 ^ { \circ }$ ，光栅中心到像平面的距离为 $2 3 5 \mathrm { m m }$ ，这是放置光栅的最佳位置。与三维平移台相对的，在六通转接法兰的另一个法兰口接上一个活套三通法兰，顶端安装真空计，侧端安装了一个耐高温玻璃窗用于腔室内的光栅调整监测，可以观察光栅的位置以及准直光束的入射和反射情况。

与光栅相结合的CCD采用普林斯顿型号为PIXIS-XO1024B的无AR涂层X射线探测器（AR涂层装置不能探测小于 $5 0 0 \mathrm { e v }$ 的X射线），其测量范围是 $1 0 \mathrm { e V } { - } 2 0 \mathrm { k e V }$ 。读出模式提供微秒分辨率，采用热电式空气冷却，制冷温度可达203K（ $\mathrm { - 7 0 ^ { \circ } C }$ ），此时暗电流下降到每秒0.0004个电子/pixel，剩下的噪声主要来源于系统读出噪声，选择 $1 0 0 ~ \mathrm { k H z }$ 数字化率读出噪声通常在3.1个电子（rms）左右，极低的噪声指数可允许的曝光时间更长，从而增加光子数的累积。CCD相机安装在一个二维调整机构上，它将CCD基本定位在光栅平场焦平面覆盖的光谱区域，见图1。调整机构的内部增加了轴承以防止卡位，框架的侧边分别安装了两处导向机构，保证在真空负载作用下，光路是沿着指定角度方向的，防止偏转卡涩。二维调整机构框架的顶部和底部分别配有垂直于光路方向和沿光路方向的两根探针，与它们连接的两个正交位移传感器（电子尺）可以分别测量CCD在横向和纵向上移动的相对距离，位移传感器的精度是 $0 . 0 2 \mathrm { m m }$ 。在垂直于光路方向的二维机构框架一边安装一个指针刻度尺作为零点基准，零点基准加上相对距离，就能得到CCD调节后的绝对位置。这样便于在CCD当前位置的基础上进行微调节，使得CCD探测器采集的光子数最大化。

最后，在国台实验室EBIS-A平台上安装搭建完成的超高真空平场光谱仪如图3所示，它的外围大小大约是 $6 8 0 { \times } 6 0 0 { \times } 6 1 0 \mathrm { m m } ^ { 3 }$ ，整个系统在超高真空条件下工作，经烘烤之后其真空度可达到 $1 0 ^ { - 1 0 } \mathrm { m b a r }$ 。

![](images/fb27dbe9e1910e942abac417698bb60452b64e9643ccca2e8cfddc4d0a81e936.jpg)  
图3实验室装置图。  
Fig.3The schematic of experimental setup.

# 2准直调试

实验开始之前，需要对谱仪进行准直调试[15]，保证从国台 EBIS-A 电子束离子源中心辐射出的软X射线能顺利穿过狭缝，使得CCD 相机能够采集到色散后的X射线光子。

准直过程中，使用单色激光器发射出的绿光作为准直调试光源，其光斑大小可调，光斑直径控制在 $3 \mathrm { m m }$ 以下。首先测试光栅是否水平放置，令激光经过一定光路（由两个反射镜组成）入射至EBIS-A电子束离子阱的中心，再透过狭缝衍射出去，利用旋转贯通仪旋转光栅，使得在远处的竖直白板上能够看到与狭缝处于同一水平面的衍射条纹，表明光栅表面与水平面平行，记录下此时的光栅位置和白板上零级条纹的位置。在此基础上转动光栅，使得其表面与入射光形成 $3 ^ { \circ }$ 的夹角，可见经光栅反射的衍射条纹在白板上爬升，同时记录下此时零级条纹的位置，并测量条纹上升的距离H，光路图如图4所示。以光栅水平放置时，白板上的零级条纹为基准点，测量光栅中心到白板的水平距离d。当光栅倾斜了 $3 ^ { \circ }$ ，反射光打在白板上的零级条纹位置可由理论计算出，此时零级条纹到基准点的垂直距离${ \mathrm { h } } { \mathrm { = d } } { \times } { \mathrm { t a n } } 6 ^ { \circ }$ 。其中的角度 $6 ^ { \circ }$ 是由于光栅倾角为 $3 ^ { \circ }$ 导致的反射光与水平面的夹角。

![](images/c4c943d180f5ef906e491e6331ef87ce349a1217a282796461c576f1ee617f2a.jpg)  
图4准直光路图。  
Fig.4Collimating optical path diagram.

通过调节三维平移台XYZ轴改变光栅的位置以及控制旋转贯通仪旋转光栅倾角，得到本次实验准直测量到的垂直距离H在 $1 2 . 8 5 \mathrm { c m }$ 左右，而测量到的光栅中心到白板的水平距离 $\mathrm { d } { = } 1 2 2 . 4 \mathrm { c m }$ ，根据这一测量参数计算出理论 $\scriptstyle \mathtt { h } = 1 2 . 8 6 \mathrm { c m }$ ，由此可见测量到的垂直距离H与理论 $\mathbf { h }$ 相符。

# 3测量结果预测

# 3.1波长定标

利用谱仪测量到光谱数据后，首要的工作是对其色散关系进行定标。即使是在同一装置上的谱仪，重新使用前由于轻微的不稳定因素（例如整个观测系统的振动，调整不确定性，光栅像差和光束参数的调整等），可能导致每次测量到的辐射线强度峰值所在位置与对应的理论谱线位置产生轻微的偏移，因此需要重新对色散关系进行标定。在此，本文先利用德国Heidelberg-EBIT 极紫外波段平场谱仪（ $3 . 2 ^ { \circ }$ ）测量的数据[1进行色散关系标定，该谱仪与本文中为国台实验室设计的谱仪在单个组件的设计细节上有所不同，如表1所示，比如入口狭缝模式，光栅入射角参数，采用的CCD相机不同以及所有组件准直调整方式略微不同，但是它们的构造和工作原理是非常相似的，定标原理也是一致的。

# 表1Heidelberg-EBIT极紫外波段谱仪和国台 EBIS-A超高真空平场光谱仪的基本参数

<html><body><table><tr><td>Entrance slit mode</td><td>26×5/5.5/6 mm aperture slits</td><td>10 mm ×100 μm single-slit</td></tr><tr><td>diffraction grating</td><td>1200 grooves/mm</td><td>1200 grooves/mm</td></tr><tr><td>Incidence angle</td><td>3.2°</td><td>3°</td></tr><tr><td>Grating object distance</td><td>237 mm</td><td>237 mm</td></tr><tr><td>Grating image distance</td><td>235 mm</td><td>235 mm</td></tr><tr><td>CCD</td><td>2048×2048 pixels of 13.5×13.5 μm²</td><td>1024×1024 pixels of 13×13 μm²</td></tr><tr><td>Vacuum</td><td>Below 10 mbar</td><td>Up to 10"1° mbar</td></tr></table></body></html>

首先针对Heidelberg-EBIT极紫外波段平场谱仪测量到的不同离化态铁离子在107-353A波长范围内的光谱数据，进行高斯拟合得到FeVII-XXIV 的辐射线峰值在CCD上所在的精确位置。而对于感兴趣的波长范围，选择Chianti 数据库[7]中 $1 1 . 5 \mathrm { - } 1 4 . 5 \mathrm { n m }$ 波段内同样辐射强度的FeVIII、FeXIX-XXII谱线来拟合，如图5所示。图5得到8个拟合峰对应的像素值。

![](images/1fe8407ccf2cffe786f4a29dc5da734c6717a1ee325f656c0e6d481d26610f6b.jpg)  
图5实验测量的高斯拟合。  
Fig.5 Gaussian fitting of experimental measurements.

尽管定标原理相同，但是本文采用了不同于Heidelberg-EBIT 极紫外波段光谱实验测量中G.Y.Liang 等人使用的定标方法,G.Y.Liang等人通过三次多项式拟合得到波长和像素的色散方程。由于衍射在CCD像平面上的谱线位置，近似弧度极小的弧形切线，可以看作是波长的线性函数，因此光谱仪的色散方程可以用一个线性回归模型来分析。

$$
\lambda { = } a { + } b x
$$

基于Chianti数据库，同样选择该波段范围内对应图5中8个拟合峰的FeVIII、FeXIX-XXII的辐射线作为参考线来训练模型。Chianti数据库是从已发布的原子数据中收集了大量的原子序数从H到 $Z \mathrm { n }$ 元素的离子数据，该数据被认为是目前太阳和恒星天体在波长范围为1-2000A的最准确、最广泛、最完整的用于分析光谱模型的数据。因此，选择Chianti数据库作为本次模型的基线数据。由于复杂的铁离子光谱使得筛选单个的谱线很困难，考虑到其中混合线的影响，定标是存在误差的。在相同的波峰位置处，将不同离化态铁离子的理论波长和对应的像素值带入方程（1）进行拟合，方程（1）表示波长（入）和CCD相机像素（x）的线性关系，得到的回归模型如图6所示，同时获得的模型参数截距 $\mathrm { a } { = } 1 9 . 2 8 4 4 3 2 3$

相关系数 $\mathsf { b { = } { - 6 . 1 9 9 7 8 7 1 8 \times 1 0 } ^ { - 3 } }$

![](images/bbadda296c74d745667d4fde8a70f8c1fd8d8080924e8e278ce66b4be24ac939.jpg)  
Fig.6The dispersion relation of the spectrometer.

通常对回归模型的检验使用判定系数 $\boldsymbol { \mathrm { R } } ^ { 2 [ 1 8 ] }$ 来衡量，它是表示实际观测值和回归方程的拟合程度的一个指标，越接近于1，回归模型拟合效果就越好。检验之后得到方程（1）的$\operatorname { R } ^ { 2 } { = } 0 . 9 9 5 5$ ，说明这个模型对波长定标是适用的，可以用它进行未知数据的预测。图7通过残差图来评估模型计算出的定标结果，由图7可见观测值和拟合值的残差主要分布在1个标准差（σ）范围内或附近，只有一个残差分布在3个标准差之间，对应于图6中FeXXI波长的定标误差。而在正态分布中，3个标准差之内的比率占全部数值的 $9 9 \%$ ，这表明模型的精确度还是相对较高的。因此，由线性回归模型对光谱仪色散关系的标定可以用来校准观测谱。

![](images/319a15540ab531e8b10b7c9dd39e0b0955da8ea0a44ef8352cfcf4ad3f5832cc.jpg)  
图6光谱仪的色散关系。  
图7实验观测值和回归模型拟合值的残差分布。  
Fig.7The residual distribution of experimental observations and regression model fitting Values.

# 3.2软×射线光谱模拟和谱线认证

即便根据谱线波长的一致性来比较归一化后软X射线波段的测量值和谱线的辐射衰减率，也很难识别谱线，因为该波段光谱的复杂性，不是所有谱线都能被认证，一些未确定的弱线混合在更强的发射线中可能会影响波长和强度。而目前的光谱仪仍无法解决这些问题。因此，可以优先估计在 $1 1 . 5 { - } 1 4 . 5 \mathrm { n m }$ 范围内贡献量最大的离化态铁离子，以确定其主要的辐射线，比如 Fe XXII在 $1 3 . 2 9 0 6 \mathrm { { n m } }$ 处 $\mathrm { 1 s ^ { 2 } 2 s 2 p ~ ^ { 1 } P _ { 1 } } \mathrm { - 1 s ^ { 2 } 2 s ^ { 2 } ~ ^ { 1 } S _ { 0 } }$ 的跃迁，Fe XXI在 $1 1 . 7 1 4 4 \mathrm { n m }$ 处 $\mathrm { 2 s 2 p ^ { 2 } ~ ^ { 2 } P _ { 1 / 2 } } \mathrm { - 2 s ^ { 2 } 2 p ~ ^ { 2 } P _ { 1 / 2 } }$ 的跃迁以及在 $1 3 . 5 8 1 2 \mathrm { n m }$ 处 $\mathrm { 2 s 2 p ^ { 2 } ~ ^ { 2 } D _ { 3 / 2 } } \mathrm { - } 2 \mathrm { s } ^ { 2 } 2 \mathrm { p ~ ^ { 2 } P _ { 1 / 2 } }$ 的跃迁，和Fe XXI在 $1 2 . 8 7 5 5 \mathrm { n m }$ 处 $\mathrm { 2 s 2 p ^ { 3 } ~ ^ { 3 } D _ { 1 } } \mathrm { - } 2 \mathrm { s } ^ { 2 } 2 \mathrm { p } ^ { 2 } \ ^ { 3 } \mathrm { P _ { 0 } }$ 的跃迁。在光学薄的情况下，SASAL方法[19可以分析不同的天体物理和实验室等离子体的 $\mathbf { \boldsymbol { X } }$ 射线光谱和它们的电荷态分布。其中，SASAL光谱模拟包中的 ECP_EBIT 模块用于研究单能电子束的电子碰撞等离子体，拟合结果能够很好的反映电子束离子阱的实验光谱测量。ECP_EBIT模块使用碰撞辐射模型来计算不同离化态铁离子的光辐射。由于激发态粒子的布居极少，在计算光谱时，从各个能级粒子布居的相对比例可以看出跃迁能级越高，处于该激发态的粒子越少。当电子温度为几个keV时，处于基态和量子数为2的激发态的粒子数最多，大约为 $\left. 1 - 1 0 ^ { - 3 } \right.$ ，而电子跃迁到量子数为5的激发态或更高的能级，处于该激发态的粒子数在 ${ 1 0 } ^ { - 1 1 }$ 左右，甚至更少。因此模型考虑电子的主激发及其级联，而电子电离和复合过程对能级分布的贡献较小，忽略不计。假设电子碰撞激发和退激发，以及每个离子能级间的自发衰减率是能级布居的主要机制。通过求解方程（2)，可以得到特定的粒子能级布居：

$$
\frac { d N _ { j } ^ { q } } { d t } = \sum _ { i < j } N _ { i } ^ { q } n _ { e } C _ { i  j } + \sum _ { k > j } N _ { k } ^ { q } ( n _ { e } C _ { k  j } + A _ { k  j } ) - N _ { j } ^ { q } \sum _ { i < j } ( n _ { e } C _ { j  i } + A _ { j  i } )
$$

$\boldsymbol { N } _ { j } ^ { q }$ 是电荷为 $\mathsf { q }$ 、能级为 $\mathrm { j }$ 的离子的密度分布， $n _ { e }$ 是电子密度， $C _ { i  j }$ 是从能级i跃迁至能级j的激发率/退激发率，以及 $A _ { k  j }$ 是从能级 $\mathbf { k }$ 跃迁至能级j的自发衰减率。右边的第一项表示从较低能级i到能级j的激发，第二项的第一部分表示从较高能级 $\mathbf { k }$ 到能级j的退激发，其第二部分表示较高能级 $\mathbf { k }$ 到能级j的自发衰减率，第三项则分别是从能级j到较低能级i的退激发和自发衰减率。使用Chianti数据库和准稳态近似计算每个铁离子的激发能级，令$\frac { d N _ { j } ^ { q } } { d t } = 0$ ，可以得到平衡态下的能级分布，进而计算出谱线强度为：

$$
I _ { j  i } ^ { q } = { N } _ { j } ^ { q } A _ { j  i } h \nu _ { j  i }
$$

在实际的谱线测量时，由于谱线展宽使得任何发射谱线或吸收谱线不是单一频率的谱线，都有一定的宽度与轮廓，对于线强度分布在一定频率范围内的谱线可以通过半高全宽(FWHM)为 $0 . 6 \mathring { \mathrm { A } }$ 的高斯曲线来拟合所测量的辐射线轮廓。类似于早期K.Schwarzschild和Milne 为近似地描述恒星大气的物理状态而各自提出的局部热动平衡假设，国台EBIS-A与Heidelberg-EBIT的电子束都是单能的，宏观上它与气体原子碰撞产生的软X射线辐射源处于热力学平衡状态，因而可以确定实验温度。Heidelberg-EBIT 实验的电子能量和电流分别为 $\mathrm { E _ { e } } { = } 5 . 6 4 \mathrm { k e V }$ 、 $\mathrm { I } _ { \mathrm { e } } { = } 3 2 0 \mathrm { m A }$ ，电子密度为 $1 . 0 { \times } 1 0 ^ { 1 2 } \ \mathrm { c m } ^ { - 3 }$ 。根据这些参数，将由碰撞辐射模型计算出来的不同离化态铁离子在 $1 1 . 5 \mathrm { n m } { - } 1 4 . 5 \mathrm { n m }$ 波段内的理论光谱与实验测量光谱进行比较，如图8所示，其中黄色细实线表示模型计算出来的总的模拟光谱。针对图8中各个铁离子的丰度占比，通过图5的高斯拟合得到铁离子拟合峰的辐射能流，去除以由辐射碰撞模型计算的各离子对应辐射线强度，得到铁的各电离态所占的比例如表2所示。

# 表 2不同电离态铁离子的丰度比

Tab.2Abundance ratios of Fe ions in various ionization stage   

<html><body><table><tr><td>Ionic fraction</td><td>Fe VIII/Fe XXIII</td><td>Fe XX/Fe XXIII</td><td>Fe XXI/Fe XXIII</td><td>Fe XXII/Fe XXIII</td></tr><tr><td>Ratio</td><td>0.0211</td><td>0.0789</td><td>0.4218</td><td>0.5505</td></tr></table></body></html>

![](images/75a6707650f8e02ad50df424fc2f01d80ed273242be39f4b705df7879615cbad.jpg)  
图811.5-14.5nm 波长范围内观测谱和理论模拟的比较。  
Fig.8Comparison of observation spectra and theoretical simulation in $1 1 . 5 - 1 4 . 5 \mathrm { n m }$

图8展示了该波段范围内铁离子的不同离化态（FeVIII、FeXIX-XXIII）谱线在实验测量光谱中其峰值所在位置，这与G.Y.Liang 等人在 $1 1 . 5 { - } 1 4 . 5 \mathrm { n m }$ 波段内观测谱的拟合结果是一致的。此外，从图8中可以看到，在峰值处除了贡献量最大的铁离子谱线，还存在其他离化态的铁离子在此处强度较弱的谱线，混合在里面很难分辨出来。对图8中的最高波峰进行高斯拟合发现在 $1 3 . 2 9 2 5 \mathrm { n m }$ 附近，半高全宽为 $0 . 1 0 1 7 8 \mathrm { n m }$ ，除了FeXXIII的强线，还存在相对较弱的FeXIX和FeXX跃迁谱线，而测量到的光谱没有分辨出这些弱线。这表明光谱仪的灵敏度和分辨率对于认证混合线和分析谱线的精细结构是十分重要的。

由于波长定标潜在的误差，图8中的理论谱和观测谱拟合存在一定的偏移。然而峰值强度是一样的，在此基础上仍然可以确定能级跃迁的波长，帮助实验测量光谱的特征谱线认证，如表3所示，谱线认证是通过与已知的辐射线集比较实现的，一些数据库列出了大量的谱线表，但线表的内容有很大不同，不仅罗列的谱线数目不同，来源也不同，其中一些采用理论值，一些采用实验值。目前以美国国家标准与技术研究院（NIST）[20]原子光谱数据观测到的波长数据为参考标准，显示了由实验测量标定的谱线位置，其中Ion一列中的（b1）表示该离子的谱线与另一条谱线混合。

表3实验认证的谱线波长和跃迁  
Tab.3Wavelength and transitions of identified lines by Experiments   

<html><body><table><tr><td rowspan="2">Ion</td><td colspan="2">λ（nm）</td><td colspan="2">Transition</td></tr><tr><td>Measurement</td><td>NIST</td><td>Lower Level</td><td>Upper Level</td></tr><tr><td>Fe VIII</td><td>13.0924</td><td>13.1240</td><td>1s22s²2p3s²3p3d ²D5/2</td><td>1s²2s2p3s²3p4f²F712</td></tr><tr><td>Fe XIX (bl)</td><td>12.0260</td><td>11.9983</td><td>1s22s2p4 3P1</td><td>1s22s2p ³P2</td></tr><tr><td>Fe XX</td><td>11.9020</td><td>11.8697</td><td>1s²2s²2p 4S3/2</td><td>1s2s2p4 4P112</td></tr><tr><td>Fe XX</td><td>12.1500</td><td>12.1858</td><td>1s2s2p³ 4S3/2</td><td>1s2s2p44P3/2</td></tr></table></body></html>

<html><body><table><tr><td>Fe XXI</td><td>12.7700</td><td>12.8755</td><td>1s22s P</td><td>1s²2s D</td></tr><tr><td>Fe XXI</td><td>14.2084</td><td>14.2278</td><td>1s²2s22p² 3P1</td><td>1s22s2p³ 3D1</td></tr><tr><td>Fe XXII</td><td>11.7160</td><td>11.7144</td><td>1s2s2p ²P112</td><td>1s2s2p² ²P1/2</td></tr><tr><td>Fe XXII</td><td>13.6256</td><td>13.5812</td><td>1s2s22p ²P1/2</td><td>1s2s2p² ²D3/2</td></tr><tr><td>Fe XXIII (bl)</td><td>13.2908</td><td>13.2906</td><td>1s²2s²1So</td><td>1s22s2p 'P1</td></tr></table></body></html>

因此，通过分析Heidelberg-EBIT极紫外光谱仪的实验数据，为接下来设计的国台 EBIS-A超高真空平场光谱仪测量不同离化态铁离子的软X射线光谱实验提供模板以作参考，与此同时，对 $1 1 . 5 \mathrm { - } 1 4 . 5 \mathrm { n m }$ 波段内铁离子的跃迁谱线的观测还能检验谱仪的性能。

# 4总结

本文探讨了使用实验测量的方法对于天体高分辨率软X射线光谱的研究，首先设计了一个搭载在国台 EBIS-A上的超高真空平场光谱仪，利用三维平移台和旋转贯通仪放置光栅的灵活性，可以分别采用1200槽 $/ \mathrm { m m }$ 光栅或2400槽 $/ \mathrm { m m }$ 光栅，通过使用三维平移台和旋转贯通仪分别在三维空间和旋转入射角方向上对光栅位置的调整以及二维调整机构对CCD相机位置的调节以适应光栅参数，来测量较重金属元素在不同波段范围辐射的软X射线谱线，比如前者的波长范围为 $5 { - } 2 0 \mathrm { n m }$ ，后者的波长范围为 $1 { - } 7 \mathrm { n m }$ 。而在 $1 1 . 5 \mathrm { - } 1 4 . 5 \mathrm { n m }$ 波段内，根据经光栅衍射的光子分布在CCD像平面上的位置属性，建立线性回归模型校准实验时轻微的扰动因素造成的辐射线强度峰值所在波长位置与理论的偏移，判定系数 ${ \bf R } ^ { 2 }$ 和残差图表明回归模型对波长定标结果的精确度较高，能够实现对观测谱的校准。像Fe之类的金属元素，在软X射线波段它们辐射出的谱线复杂，使用碰撞辐射模型对谱线强度峰值处贡献量最大的离化态铁离子进行计算，可以得到它们的能级分布和谱线强度，然而由于谱线展宽效应，计算结果用 $\mathrm { F W H M = } 0 . 6 \mathring \mathrm { A }$ 的高斯线型拟合。通过比较理论谱计算结果与实验测量光谱，可以看到光谱中强度峰值所在处的谱线并不是单一的离化态铁离子辐射谱，还夹杂着其他强度较弱的谱线，即便在峰值强度相同的情况下能够认证实验测量光谱的谱线，由于光谱仪的分辨率受限，也无法观测到光谱的精细结构。而设计的平场谱仪不仅能在超高真空下探测光子，而且较小的入口狭缝、以及较高的光栅X射线反射率和CCD 相机信噪比，都能有效提高谱仪的分辨率和灵敏度，有望在接下来铁元素软X射线波段光谱的实验测量中观测到混合线，实现对波长的精确标定。

致谢感谢国家自然科学基金天文联合项目的资助No.U1931140，感谢复旦大学杨洋老师对谱仪准直调试的协助。

# 参考文献：

[1] RANDALL K SMITH,NANCY S BRICKHOUSE. Atomic Data Needs for Understanding X-ray   
Astrophysical Plasmas[J]. Advances in Atomic,Molecular,and Optical Physics,2014,63: 271-321. [2] VENNES S,DUPUIS J. Chandra Observations of Hot White Dwarf Stars[C].The High Energy Universe   
at Sharp Focus: Chandra Science,held in conjunction with the113th Annual Meeting of the ASP.ASPConference   
Proceedings. San Francisco: Astronomical Society of the Pacific, 2Oo2: 57-61. [3] ADAMCZAK J,WERNER K,RAUCH T, et al. Chandra grating spectroscopy of three hot white   
dwarfs[J].Astronomy& Astrophysics,2012,546:13. [4] BEHAR EHUD, COTTAM JEAN, KAHN STEVEN M. The Chandra Iron-L X-Ray Line Spectrum of

Capella[J]. The Astrophysical Journal, 2001,548(2): 966-975.

[5] ZSCHORNACK G,KRELLER M,OVSYANNIKOV V P,et al. Compact electron beam ion sources/traps: Review and prospects (invited)[J]. Review of Scientific Instruments, 2Oo8,79(2).

[6] PETER BEIERSDORFER.Laboratory x-ray astrophysics[J]. Annual Reviews,2003,41: 343-90.

[7] BEIERSDORFER P,LOPEZ-URRUTIAJR CRESPO,SPRINGER P,et al. Spectroscopy in the extreme ultraviolet on an electron beam ion trap[J]. Review of Scientific Instruments,1999,7O(1): 276-279.

[8] GRAF A T, BROCKINGTON S, HORTON R,et al. Spectroscopy on magnetically confined plasmas using electron beam ion trap spectrometers[J]. Canadian Journal of Physics,2Oo8,86(1): 307-313.

[9] LEPSONJK,BEIERSDORFERP,GU MF,etal.Laboratory calibration of density-dependent lines in the extreme ultraviolet spectral region:The 17th International Conference on Atomic Processs in Plasmas (ICAPIP)[C]. Review of Scientific Instruments,2012,1438: 136-141.

[10] LIANG G Y,BAUMANN T M,LOPEZ-URRUTIA JR CRESPO,et al. Extreme-Ultraviolet Spectroscopy of Fe VI-Fe XV and its Diagnostic Application for Electron Beam Ion Trap Plasmas[J].The Astrophysical Journal,2009, 696(2): 2275-2289.

[11] NAKAMURA NOBUYUKI, WATANABE ETSUSHI, SAKAUE HIROYUKI A, et al. Intensity Ratio of Density-sensitive Lines inFe Ions Observed with a Well-defined Laboratory Plasma[J].The Astrophysical Journal, 2011,739(1).

[12] SHIMIZU ERINA,ALI SAFDAR,TSUDA TAKASHI,et al. Measurements of density dependent intensity ratios of extreme ultraviolet line emission fromFe X,XI,and XI[J]. Astronomy& Astrophysics,2017, 601.

[13] PEI S X,LIU Y, CUI F P. Experimental study on the effect of slit width on the resolution of grating spectrometer[J]. Experiment Science and Technology,2018,16(5): 47-52.

[14]The Center for X-Ray Optics.X-ray interactions with matter[OL]. [2020-05-29]. https://henke.lbl.gov/optical_constants/.

[15] YANG Y,SHI Z,FEI Z, et al.Configuration and calibration of a flat field grating spectrometer in the wavelength range $7 { - } 6 0 \mathring \mathrm { A }$ with a Manson ultrasoft x-ray source[J]. Physica Scripta, 2O11,144.

[16] LIANG G Y, CRESPO LOPEZ-URRUTIA JR, BAUMANN T M, et al. Experimental investigations of ion charge distributions,effective electron densities,and electron-ion cloud overlap in electron beam ion trap plasma using extreme-ultraviolet spectroscopy[J]. The Astrophysical Journal, 2Oo9,702:838-850.

[17] LANDI E, GRUESBECKJR,LEPRI S T, et al. Charge State Evolution in the Solar Wind.II. Plasma Charge State Composition in the Inner Corona and Accelerating Fast Solar Wind[J].The Astrophysical Journal, 2012, 761(1).

[18] JAMES G,WITTEN D, HASTIE T, et al. An Introduction to Statistical Learning[M/OL]. Springer, 2013: 59-71[2020-06-15]. htps:/link.springer.com/content/pdf/10.1007%2F978-1-4614-7138-7.pdf.

[19] LIANG G Y, Li F,Wang F L,et al. X-Ray and EUV Spectroscopy of Various Astrophysical and Laboratory Plasmas: Colisional,Photoionization and Charge-exchange Plasmas[J].The Astrophysical Journal, 2014, 783(2).

[20] ALEXANDER KRAMIDA,YURI RALCHENKO, JOSEPH READER, et al. NIST Atomic Spectra

# Experimental measurement and calibration of celestial bodies with high resolution soft X-ray radiation

Zhang Yujial2，Liang Guiyun' (1.KeyLaboatoryofpticalsronoatioalstronoicalOseatosisecdeyofiecseiga; 2.University of Chinese Academy of Sciences,Beijing 10oo49,China,Email:gyliang @bao.ac.cn)

Abstract: At present, it is a new research method to analyze the X-ray observation spectra of celestial bodies by using the atomic data which is generated by experimental devices,and great strides has been made in addressing astronomical observational puzzles. In order to measure the high-resolution soft X-ray spectra of highly charged iron ions,A ultra-high vacuum flat field spectrometer was designed and built on the National Astronomical Observatories of the Chinese Academy of Sciences(NAOC) EBIS-A platform. In single-slit mode,the spectrometer uses 1200 grooves/mm varied line-spacing diffraction grating in the wavelength range of $1 1 . 5 \mathrm { - } 1 9 . 8 \mathrm { n m }$ .For the measurement results of the spectrometer, The first step is to make a theoretical prediction of the radiation likely to measure.With the same working principle of the electron beam ion trap, Heidelberg-EBIT ultraviolet spectrometer experiment data based on Chianti database has been analyzed in the spectral region from 11.5 to $1 4 . 5 \mathrm { n m }$ .First,a linear regression model has been established to calibrate the offset of the peak position of line strength caused by the experimental system. Then the soft $\mathrm { \Delta } X$ -ray spectra of Fe ions in various ionization stage simulated by the collision radiation model has identified wavelengths of Fe VIII and Fe XIX-XXIII line radiation in experimental measurement. And the present simulations satisfactorily reproduce the measured spectra. Furthermore, blend lines of Fe XIX and Fe XX, which is weaker than the transition line of Fe XXIII, have been found at $1 3 . 2 9 2 5 \pm 0 . 1 0 1 7 8 \mathrm { n m }$ but the observed spectra has not resolved these weak lines. Therefore,the following experimental measurement can take the predicted results as a reference to test the performance of the spectrometer.

Key words: soft $\mathrm { \Delta X }$ -ray spectra; NAOC EBIS-A；Ultra-high vacuum flat field spectrometer; Line identification