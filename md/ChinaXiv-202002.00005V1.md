# 热色液晶瞬态测量流动换热中努赛尔数的技术研究

罗希凌1,²，饶宇²，梁策²，罗稼昊²

1（上海交大-巴黎高科卓越工程师学院 上海 200240)  
2（上海交通大学叶轮机械研究所 上海 200240)

摘要 热色液晶是一种胆甾相液晶，其具有显著的旋光效应，对于温度的变化具有高度的敏感性，广泛应用于物件表面温度的测量。在流动与换热的实验研究中，通常需要研究整个通道内部表面的换热分布情况。利用瞬态液晶测量通道表面的温度场，进而推导出表面的换热系数分布和努赛尔数，在燃气轮机涡轮叶片冷却的研究中已成趋势。本文建立了基于瞬态液晶实验技术的风洞和测试系统，利用HSV色彩模型对颜色进行描述，经过标定后，得到颜色-温度关系；开展瞬态液晶实验，用半无限大导热理论对瞬态导热过程进行求解，得到了通道内部壁面的努赛尔数分布云图与平均努赛尔数，并与理论计算值进行了对比，两者吻合较好。

关键词 液晶热相；瞬态；努赛尔数；流动换热 分类号TK1

# 1导言

努赛尔数（Nusseltnumber）分布的测量是对流换热实验研究中的基础工作，传统的测量方法需要在研究表面布置有限个测点，通过测定局部换热系数的方法得到整个表面的换热系数分布，进而得出通道内部的努赛尔数分布。对于一些复杂流场（如带扰流及溢流的内流通道、带扰流及变向流的内流通道、带射流的气膜冷却、带跨流的冲击冷却等)，表面温度变化规律十分复杂，只有全面地测量表面温度场，才能为热分析提供准确可靠的数据。另外在许多气动传热基础技术研究中，要求在测量时不能破坏试件的结构及流场的性质，采用非接触式测量技术就显得非常重要。这些都是传统测量方法难以克服的。

热色液晶测温技术是近年来发展起来的新技术，为非接触测温方式，并且可以得到整个研究表面的温度场。近年来发展液晶瞬态测量技术已形成趋势。其基本原理是：当气流流过与之不同温度的试验模型表面时，试验模型表面各点的温度变化与该点的换热速率密切相关，因此，只需准确记录试验件表面各点的温度变化，就可根据传热学理论计算出各点的对流换热系数，进而求解出Nu数。由于该方法不要求换热达到稳定，因而实验时间较短。

本文首先介绍了瞬态液晶测试的实验原理，其次介绍了实验技术以及数据处理，然后给出了测试实例以及与数值计算结果的对比，最后对本次报告进行总结。

# 2瞬态液晶实验原理

# 2.1热色液晶以及图像处理技术

晶体的中间态是指固态和液态之间的过渡态。此时，液晶既能保持晶体固态分子的包括各项异性等在内的物理化学性质，又具有流动的特性。在传热实验中应用的液晶通常指胆甾相液晶（cholesteric liquid crystals)，它的名称来源于一些胆甾醇衍生物所形成的液晶态结构。它具有显著的旋光效应、较强的圆二色性和波长的选择性反射，后者使它在肉眼下即能显现色彩。液晶对温度变化具有高度的敏感性，可以用来测试实验物体表面温度的变化。

热色液晶在温度升高的条件下出现液晶态的温度范围被称为带宽。不同种类的液晶的带宽有很大差别。实验所使用的液晶分为变色范围小于 $1 ^ { \circ } \mathrm { C }$ 的窄带液晶和大于 $5 \mathrm { { ^ circ C } }$ 的宽带液晶。当温度达到液晶的变色范围内时，液晶的分子排列方式发生改变，在光源的照射下呈现出肉眼可见的光。该波长范围的光依次呈现出红、绿、蓝的变化过程。通过高清相机捕捉喷涂有液晶的器件表面颜色的变化，再参照液晶的标定数据，就可求解出元器件表面的温度场。通过对温度的测量间接地可用于测量局部传热系数。

由于热敏液晶能在不同的温度情况下，呈现出不同波长的可见光，因此温度和色彩之间存在映射关系： $\scriptstyle \mathrm { R G B = } f ( \mathrm { T } )$ 。通过在计算机中求解该映射关系的反函数，进而可以求解出测试件区域的温度分布情况。具体地，将喷涂好液晶的实验件安装到实验通道上并进行密封，通过调整气体的温度和流量使其温度发生变化，进而改变液晶分子的排列方式，反射出不同颜色的可见光，再依据颜色与温度的对应关系求解出实验件表面的温度场。与传统的温度测量方法相比，由于是非接触型测量，热色液晶不会改变流场本身的结构；另一方面，热色液晶对于温度的变化极为敏感，能够定量地测量特定流场的二维温度分布，测量的精度也较高；此外，此方法相对于红外热像价格低廉，且液晶的变色过程是可逆的，在一定时间范围内可以重复使用，具有较强的成本优势。鉴于以上优点，热敏液晶技术被广泛应用于传热测量领域。

彩色空间中，通常有多种方式来表示颜色，便于计算机进行储存和分析。对于常见的RGB色彩空间而言，其是通过红色（Red）、绿色(Green)和蓝色（Blue)三个颜色通道的变化以及相互之间的叠加来呈现广泛的颜色阵列，是运用最广的色彩模式之一。目前RGB颜色模型基于人类对颜色的感知，主要应用于一些电子系统的感知和显示图像。RGB是与设备相关的颜色模型：不同的设备以不同的方式检测或再现给定的RGB值，由于颜色元素（如荧光粉或染料）及其对单个R、G和B水平的响应随着制造商的不同而不同，甚至在同一设备中随时间而异。因此，RGB值不适合作为测试标准。

瞬态液晶实验中常用的颜色模型是HSV 模型。HSV是由A.R.Smith在1978年创立的一种色彩空间，也称六角锥体颜色空间（HexconeModel)。HSV采用三维极坐标系来描述颜色，分别是：灰度（H)、饱和度（S）和明度（V)。由图1可知，灰度沿圆周方向，数值由最小的0增大到最大的360；饱和度沿径向方向，范围为0-1；亮度则沿轴向方向，范围在0到1之间变化。用HSV模型来表示色彩空间显得更加直观，且HSV图像不受光照强度的影响，是瞬态液晶实验的理想颜色格式。在实际操作中，可以利用程序将相机记录下最原始的RGB色彩空间转换为更直观的HSV空间，以提高瞬态液晶实验的精度。

![](images/5e8c330a05113a95321fdbcbd78d4ca561002cfab98ff26bbc0a071009f17614.jpg)  
图1RGB与HSV色彩空间

# 2.2半无限大平板假设

热色液晶测量作为一种非直接接触式的测量方法，在传热实验中主要应用于获取通道端壁的温度值从而得到换热系数的分布情况，具体又分为稳态测温和瞬态测温。本文基于瞬态液晶测温技术，利用液晶随温度产生颜色变化的原理，通过观测测试件表面温度Tw（t）向流体温度阶跃变化过程，进一步求解出通道端壁的强化换热系数。实验时需特别控制液晶完成一次完整的变色过程的时间。

本实验测试件采用的是有机玻璃板（Acrylicplate)，其具有透光性好、美观平整、使用寿命长等优点。瞬态实验基于半无限大平板的一维非稳态导热原理。导热原理图如图2所示：

![](images/9877ec01d46e542d19dd12fed943fadbe6394a72286bf8412142dcbba934f783.jpg)  
图2半无限大平板导热原理

瞬态实验基于傅立叶一维导热方程：

$$
\begin{array} { r } { k \frac { \partial ^ { 2 } T } { \partial z ^ { 2 } } = \rho c \frac { \partial T } { \partial t } } \end{array}
$$

边界条件：

$$
t = 0 , T ( z , 0 ) = T _ { i }
$$

$$
\begin{array} { r } { z = 0 , - k \frac { \partial T } { \partial z } = h ( T _ { r } - T _ { w } ) } \end{array}
$$

$$
z  \infty \ , T ( z , 0 ) = T _ { i }
$$

其中,

$T _ { i }$ ：实验件 $\scriptstyle { \mathrm { t } = 0 }$ 时刻的温度;

$T _ { r }$ ：气体来流温度；

$T _ { w }$ ：壁面温度。

经Fourier变换，一维半无限大平板微分方程的解为：

$$
\begin{array} { r } { \frac { T _ { w } - T _ { i } } { T _ { r } - T _ { i } } = 1 - \exp { ( h ^ { 2 } \frac { t } { k \rho c } ) } e r f c ( h \sqrt { \frac { t } { k \rho c } } ) } \end{array}
$$

靶板初始温度 $T _ { i }$ 可以用热电偶测试得到； $T _ { r }$ 是测试过程中流体的温度，由热电偶实时记录并输出到对应的Exce1文件中； $T _ { w }$ 通过根据拍摄到的靶板表面液晶的变化信息，反求解得到。 $k \rho c$ 是靶板的材料特性，分别表征热导率、密度和热容。

在实际测试过程中，由于气体来流的加热存在一定程度的延迟，理想情况下的阶跃难以实现。运用Duhamel齐次化原理，有：

$$
\begin{array} { r } { { \cal T } _ { w } - { \cal T } _ { i } = \sum _ { j = 1 } ^ { N } [ 1 - \exp { ( \frac { h ^ { 2 } \alpha \left( t - t _ { j } \right) } { k ^ { 2 } } ) } e r f c ( \frac { h \sqrt { \alpha \left( t - t _ { j } \right) } } { k } ) ] ( { \cal T } _ { r , j } - { \cal T } _ { r , j - 1 } ) } \end{array}
$$

其中,

$T _ { i }$ ：有机玻璃板的初始温度；  
$\alpha$ ：实验件的热扩散率；  
$h$ ：壁面的对流换热系数;  
t：加热空气的时间。

式6的解是基于半无限大平板导热的假设前提。由该假设前提可知，实验中必须保证被加热的空气热流未击穿靶板，即靶板最深处仍可以被视作 $T _ { i }$ ，热扰动的影响局限在靶板表面时方可采用上述方程的解。因此，为了保证在足够长的时间范围内呈现稳定清晰的液晶变色图像，便于后期的数据处理，测试板需要采用低热扩散率的材料。实验采用的亚克力板热扩散率低，同时具有强度高、透光性好、便于观察等优点，能够较好满足实验条件。具体地，当靶板厚度 $\tau _ { d } = \alpha t / y ^ { 2 } <$ 0.25，满足一维半无限大平板的适用条件。

利用式6可以求解出对流换热系数 $h$ ，进而求出通道端壁的努赛尔数。努塞尔数是表示对流换热强度的无量纲参数，是跨越边界层的对流换热与导热强度的比。依据努赛尔数 $\mathrm { \Delta N u }$ 的定义式：

$$
\begin{array} { r } { N u = \frac { h D } { \lambda } } \end{array}
$$

式中，D是通道入口的水力直径，其计算方式为4倍通道截面面积比通道周长； $\lambda$ 是静止的流体的导热系数，单位为 $\mathrm { W } / ( \mathrm { m } \cdot \mathrm { K } )$ 。

# 2.3液晶的标定实验

开展瞬态液晶实验之前，需要对所使用的液晶进行标定。瞬态实验所采用的是带宽为 $1 ^ { \circ } \mathrm { C }$ 的窄带液晶。为了得到清晰的变色图像，进行液晶标定实验时，要使用专门配套的黑漆作为打底。标定实验如图3所示，选用导热性能极好的光滑紫铜板作为标定板，可以使液晶显色温度与热电偶实际测量温度保持一致。喷涂液晶前，铜板表面要保持光洁，先均匀喷上一层水溶性黑漆，带干燥充分后，将配置好的热色液晶均匀地喷涂在涂有黑漆的铜板表面。标定板液晶喷涂完毕后，需要用电吹风对表面进行质量检验，观察表面噪点数量、液晶变色亮度及液晶变色是否均匀。放置6-8h后，待表面自然风干，即可开始标定实验。

![](images/a83caf1308339c81a8be6900bb254b7228d319c1543a247cdeac29ade9ddf3f3.jpg)  
图3液晶标定实验示意图

标定实验选用铜板背面正中心的7个测温孔，间距为 $2 5 \mathrm { m m }$ ，加热膜紧密地贴在铜板背面，热电偶穿过加热膜插入上述三个测温孔中，并用导热硅胶密封，减小接触热阻，并用胶带固定防止热电偶脱落。实验具体步骤如下：

（1）将喷涂好的标定板安装在实验支架上，连接实验测试电路加热测试，  
观察测试板表面变色是否正常；（2）调节电源功率，使标定板热电偶温度稳定，将此时温度及标定图像记  
录下来，重复此步骤30-50次直至液晶颜色变化结束；（3）根据视频数据与Excel的温度数据绘制标定曲线，在Matlab 程序中实  
现这一过程。程序的基本原理是将 3CCD 相机采集到的 RGB 三种数据转化为  
HSV灰度，以热电偶获取的瞬时温度作为自变量，HSV灰度数据作为因变量可

以得到最终的标定曲线。如图4所示，Hue-T图像在显色温度附近具有明显的灰度变化，在 $3 5 . 2 ^ { \circ } \mathrm { C } \mathrm { - } 3 5 . 7 ^ { \circ } \mathrm { C }$ 附近灰度变化最为明显，因此选定该区域作为标定结果。

![](images/13b03c54cf11fdc18ca8e250fb950088130ef6b72f60b8f62e4c1e870eb97b68.jpg)  
图4液晶标定结果曲线图

瞬态液晶喷涂过厚会造成表面不均匀，影响传热使实验结果与实际不符，液晶过薄达不到变色效果，影响拍照精确度及后续数据处理。因此实验前需根据靶板大小配置液晶用量。根据RAO等人的研究，当液晶厚度为 $1 7 \mu \mathrm { m }$ 时，综合变色效果最佳。实验采用的LCRHallcrest公司生产的SPN-100/R35C1W型瞬态液晶悬浊液浓度为 $10 \%$ ，按照 $1 7 \mu \mathrm { m }$ 的厚度可以计算出所需瞬态液晶的体积。

将取出的液晶和水按1:1等体积混合后加入磁力搅拌器搅拌30-60min后取出，将大颗粒粉碎后的悬浊液加入砂芯漏斗，震荡搅拌，防止液晶沉积堵塞漏斗，一般过滤1-2h 使得悬浊液充分过滤。加入事先准备好的容器。准备喷涂。

将实验测试靶板用酒精擦拭干净吹干后开始液晶喷涂。实验需要用到空气压缩机、液晶喷枪等设备。将增压泵空气压缩至60psi，检查喷头是否可以正常使用。装入液晶，调节喷嘴出气量，使得液晶量喷出量不至于过大出现噪点，不至于过小大颗粒堵住喷头，开始喷涂过程。喷涂过程随时观测是否有大颗粒出现，用电吹风检查靶板表面变色是否均匀。每次加入液晶后都必须重新检查喷头是否堵塞，并将喷出量控制在一个合理的水平。此外，当压力低于30psi 时需重新启动压缩机，否则容易引起喷枪堵塞造成喷涂不均匀。放置1-2h后待液晶自然风干后开始喷涂黑漆。

喷涂黑漆时喷头处薄层黑漆易干，需避免过长时间充气导致喷头堵塞，如果出现严重堵塞需更换清水清洗喷头后方可实验。喷涂时不能集中喷涂一处，容易导致局部过湿损坏液晶层。如果影响液晶变色效果，需将整个靶板重新喷涂，耗材耗时。

整块板喷涂完成后将表面用塑料薄膜密封起来，壁面沾染灰尘，并自然干燥

6小时以上进行正式实验

# 3实验技术和数据处理

# 3.1实验装置

本课题瞬态液晶实验装置如图5所示。空气在漩涡式气泵的抽吸作用下，从圆弧形集流器入口处吸入通道内部，而后发展均匀并流经涡街流量计，从而确定实验通道内部的实际流量。在进入实验段通道前，空气流经由实验室自主设计的丝网加热器，从而使空气的温度达到合适的值，再由一个渐缩的通道进入实验段。实验段入口处布置有3个测压孔和3个测温孔，出口处布置有9个测压孔和9个测温孔，分别测试入口段和出口段通道内部气流的实时温度，并通过数据采集卡输入计算机。为保证气流的均匀性，空气流出实验件后布置有均匀转折段和一个体积为0.125立方米的稳压箱，最终气体从风机处排出。

![](images/fb9dca5096084fe952300e90398e6b6599710d1f841fe46677c3d5e75445e9f1.jpg)  
图5实验装置示意图

# 3.2实验过程

一个典型的瞬态实验过程如下：

（1）实验前做好准备工作，搭建实验台，并将喷涂有黑漆和液晶的实验段  
安装在实验台上，布置好热电偶和压力扫描阀，做好密封；（2）实验过程需全程保持黑暗状态，可用带有反光材料的黑布将实验段盖  
住。关紧门窗防止对流扰动，使实验段保持室温；（3）在实验段通道前后两侧上方各布置一个LED灯管作为光源，对照相机  
实时拍摄的图像，调节灯管位置，消除反光的影响；（4）开启风机，对照涡街流量计调节合适的入口流量，开始实验;（5）打开LabVIEW程序，开启数据采集器；同时调节相机白平衡及频率等  
参数，同步进行视频记录；打开实验室自主设计的丝网加热器，对气体进行加热；

（6）当实验件被加热，相机记录下热色液晶的变色过程，并将数据储存为avi格式;（7）当通道壁面的热色液晶变色完全发展，关闭丝网加热器、相机以及数据采集器;（8）数据处理：将LabVIEW导出的数据整理到Excel表中，利用Matlab 程序处理视频数据，输出为针肋通道的努赛尔数分布云图，记录下此时的平均 Nu数。

# 3.3数据处理

本研究采用Matlab软件进行数据处理，首先将CCD摄像机拍摄的记录颜色变化的图像信息送到计算机内，根据加热指示信号和最大测试时间截取有用的片段。PAL制DV 格式每秒存储25帧图像，根据帧数确定每一帧图像距零时刻的时间。之后将每一帧图像处理成反映颜色分布的图片并将其以HSV模型描述，提取每一显色点的色度Hue值。利用色度-温度关系，将图片转换为温度分布。对每一帧图像都进行相同的处理，即得到研究表面每一显色点的壁温Tw 和达到这一壁温所经历的时间t。根据数采系统记录的气流温度的变化规律，可以得到自零时刻到每一点显色时的气流温度变化曲线Tr(t)。结合实验模型的物性参数p、c、λ和实验件的初始温度Ti，即可由式(6)求解换热系数h。如果研究表面每个点都发生过显色过程，就可得到整个表面的换热系数分布，进而求解出Nu数分布。

# 4测试实例介绍

图6为当 $\scriptstyle \mathrm { R e = } 6 0 0 0 0$ 时瞬态液晶实验端壁Nu数分布云图和CFD计算的 Nu数分布云图。通过对比可知，两者展向中心区域的换热分布较为类似，在针肋的前缘形成了强换热区，且实验结果明显大于计算结果。第一排针肋处的流动未充分发展，马蹄涡的位置向通道底部偏置，到第二排及以后开始进入充分发展区域，数值计算和实验结果的拟合较好。在第二排针肋受到气流冲击的部分形成了较大的换热区，而后在后方和第三排针肋的前方由于气体的展向流速较低，致使换热较为平缓。后面两排情况类似。从展向结果来看，无论是实验结果还是计算结果均在通道的底部呈现了较低的换热趋势，该区域流体的低速流动较为明显。

![](images/6bb2636c45c8126b091a2d38a09d513b2e3f5d3c25b64f0a4f8050f19eaeace6.jpg)  
图 $6 ~ \mathrm { R e } { = } 6 0 0 0 0$ 通道端壁实验和数值模拟Nu数云图

图7为四个雷诺数：21000、39000、48000、60000下实验和数值计算的目标区域平均 $\mathrm { \Delta N u }$ 数。由图可知计算值与实验值吻合较好，两者误差最大不超过 $12 . 7 \%$ 0

![](images/258ea123a7163729b1ad512f6f915ada49995e00bb068307e118ef097a92fbd6.jpg)  
图7瞬态实验和数值计算 $\mathrm { \Delta N u }$ 数对比

# 5结语

热色液晶测温可方便地测量被研究对象表面的温度场，并且为非接触测量方法，对试件结构和流场性质没有影响。使用液晶测温和瞬态实验技术进行了端壁的 $\mathrm { \Delta N u }$ 数的测量并与理论值进行了对比，测量结果与理论解相吻合。测试方法准确、可靠。

基于液晶测温和瞬态实验技术的努赛尔数测试方法测量时间短，实验效率高，在同样工况下，对气源和加热设备要求较稳态实验低，是进行换热系数测量的有效方式。

# 参考文献

[1]Hallrest Inc.Handbook of thermochromic liquid crystal technology [M]. Glen-view,Illinois: Hallcrest Inc Pres,1991.   
[2]Rao Y, Zang S S. Calibration and the measurement uncertainty of wide-band liq-uid crystal thermography[J]. Meas Sci Techn, 2010,21(1): 15105-15112.   
[3]Ireland PT, Neely A J, Gillespie D, et al. Turbulent heat transfer measurement u-sing liquid crystal [J]. Int JHeat Fluid Flow, 1999, 20(4):355-367.   
[4] 许亚敏，饶宇．液晶热像测量精度分析及其在湍流传热研究中的应用[J]．上海交通大学学 报,2013,47(8):1185-1190.   
[5]Wagner G, Kotulla M,Ott P, et al. The transient liquid crystal technique: influe-nce of surface curvature and finite wall thickness[J]. Journal of Turbomachinery,20o5,127(1): 175-182.   
[6]王良御，廖松生．液晶化学[M]．科学出版社,1988.   
[7]J.W. Goodby,P.J. Collings,T.Kato,C.Tschierske, H.F. Gleeso n, and P.Ray-nes.Handbook of Liquid Crystals: 8 Volume Set, Second Edition 2014 Wiley VCH Verlag GmbH& Co.KGaA （通讯作者：罗希凌，E-mail:liberty@sjtu.edu.cn）

# Research on transient measurement of Nusselt number distribution with liquid crystal technique

LUO Xiling1,², RAO $\mathrm { Y u } ^ { 2 }$ ,LIANG $\mathrm { C e } ^ { 2 }$ , LUO Jiahao²

1 (SJTU-ParisTech Elite Institute of Technology, Shanghai Jiao Tong University, Shanghai 200240, China) 2 (Institute of Turbomachinery, Shanghai Jiao Tong University, Shanghai 200240, China)

Abstract: Thermochromic liquid crystal belongs to cholesteric liquid crystal, which has significant optical rotation efect and high sensitivity to temperature changes. It is widely used for measuring the surface temperature of objects. In the experimental research of flow and heat transfer, it is very necessary to study the heat transfer distribution on the inner surface of the channel.The temperature field on the surface of the channel is measured by the transient liquid crystal,and then the surface heat transfer coefficient as well as Nusselt number are deduced, which has become a trend in the research of gas turbine blade cooling.This paper establishes a test system based on transient liquid crystal experimental technology.The color is described using the HSV color model,and the colortemperature relationship is obtained after calibration.The heat conduction process is solved,and the Nusselt number distribution diagram as well as the average Nusselt number of the inner wall surface ofthe channel are obtained. Comparing the experiment results with the theoretical calculation values, the two are in good agreement.

Key words: liquid crystal thermography, transient, Nusselt number, flow and heat transfer