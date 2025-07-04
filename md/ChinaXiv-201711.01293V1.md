# CN 53-1189/P ISSN 1672-7673

# NVST焦点探测系统

李鹏飞1,²，鞠青华¹，方玉亮1,²，柳光乾1(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京100049)

摘要： $1 \mathrm { ~ m ~ }$ 新真空太阳望远镜在连续观测时，太阳辐射导致的温度变化使其光机结构产生热变形，主要表现为焦点实时变化，产生离焦像差，影响观测数据的质量。为解决这一问题，基于焦点扫描探测算法并结合望远镜的系统结构设计了一个焦点探测系统。首先分析了$1 \mathrm { ~ m ~ }$ 新真空太阳望远镜焦点变化并设计了焦点探测系统的总体结构；然后进行软硬件系统的详细设计和实现，重点对系统的重复精度和焦点探测精度进行测试，表明系统能满足望远镜的焦点探测精度要求；最后给出了焦点探测系统在望远镜上3个月的运行结果：系统能实时监测望远镜的焦点变化，根据焦点的变化量进行调焦，能得到优秀的观测数据。

关键词：焦点探测； $1 \mathrm { m }$ 新真空太阳望远镜；焦点实时变化；重复移动精度中图分类号：P111 文献标识码：A 文章编号：1672-7673(2017)04-0502-09

$1 \mathrm { m }$ 新真空太阳望远镜(New Vacuum Solar Telescope，NVST)是口径为 $1 \mathrm { m }$ 的地平式真空太阳望远镜，主要对太阳进行高分辨成像和光谱观测，自2010年投入使用以来，已取得了大量的太阳高分辨观测数据[1-2]。由于 $1 \mathrm { m }$ 太阳望远镜观测目标是强热源，虽然其光机结构经过特殊设计和处理[3]，但整个系统的稳定性还是受太阳辐射变化的影响，目前主要表现为在连续观测时间内焦点的实时变化，当变化超出系统的焦深时，就会产生离焦像差，从而影响观测数据的质量[4-5」，准确实时地探测 $1 \mathrm { ~ m ~ }$ 太阳望远镜的焦点变化并进行实时调整，将有助于提高望远镜的观测效率和数据质量。

如何实现光学系统的自动调焦已有不少学者进行了研究，文[6]提出了几种测距方法和图像清晰度的评价函数，而大型天文望远镜离焦主要是由于自身光学系统发生改变，这些调焦方法并不适用。文[7]基于图像处理采用搜索焦点的方法在南京大学浦口天文台的 $6 5 ~ \mathrm { c m }$ 望远镜上以恒星为观测目标进行了自动调焦实验。文[8]提出了绝对方差的对焦评价函数，并在怀柔太阳观测基地用搜索焦点的方法以全日面像为目标进行了自动对焦实验。但这两个调焦系统不适用于 $1 \mathrm { m }$ 太阳望远镜，原因主要有两方面：（1) $1 \mathrm { m }$ 太阳望远镜观测目标是局部日面像，其图像清晰度评价函数不适用；（2)这两个调焦系统都是采用移动CCD的方法调节焦点，而 $1 \mathrm { ~ m ~ }$ 太阳望远镜终端成像系统包括多通道高分辨成像系统和多波段光谱仪，因此， $1 \mathrm { m }$ 太阳望远镜调节焦点需要移动主光路中的 $M _ { 3 }$ 成像镜。文[9]采用焦点扫描法，连续采集焦点前后不同扫描位置的局部太阳像，然后计算特定环上的功率谱，并进行多次平均以消除大气影响，最后通过高斯拟合功率谱与扫描位置的关系曲线从而获得焦点位置，文[9]对该方法进行了大量实验，充分论证了方法的稳定性和可靠性。本文的研究工作正是基于此方法开展的，结合 $1 \mathrm { ~ m ~ }$ 太阳望远镜的系统结构，为望远镜研制了焦点实时探测系统。

本文第1节根据 $1 \mathrm { m }$ 太阳望远镜的光学系统从理论和实测两方面分析了望远镜焦点位置随温度的变化；第2节根据文[9]中的焦点扫描探测法和 $1 \mathrm { ~ m ~ }$ 太阳望远镜的系统结构，给出了 $1 \mathrm { m }$ 太阳望远镜焦点实时探测系统总体结构，并分析了焦点探测算法对系统参数的具体要求；第3节详细设计了 $1 \mathrm { m }$ 太阳望远镜焦点实时探测系统的硬件和软件系统；第4节测试系统的重复精度和系统性能；第5节对本文研究工作进行了总结和展望。

# 1 $1 \mathrm { m }$ 太阳望远镜焦点变化分析

$1 \mathrm { m }$ 太阳望远镜整体(包括建筑)和主光学系统如图1，望远镜观测时，圆顶完全移开，除望远镜整体直接受太阳照射外，周围环境也随太阳照射而温度升高。为减小对温度的敏感性， $M _ { 1 }$ 与 $M _ { 2 }$ 采用热膨胀系数很小的铟钢连接以控制 $M _ { 1 }$ 与 $M _ { 2 }$ 之间距离的变化，在焦点 $\boldsymbol { F } _ { 1 }$ 的焦面视场光阑处设计了热控系统。

![](images/3ccf45927290b719ec048be4452fda1c8066eade68ebdffe88fcb26521458236.jpg)  
图1 $1 \mathrm { m }$ 太阳望远镜整体与主光路图 Fig.1The overall structure and optical system of NVST

根据文[5]的研究结果，焦点 $F _ { 3 }$ 的位置变化与镜筒温度变化关系近似描述为(1)式：

$$
\Delta F _ { 3 } / \Delta T = \left[ \left( L _ { 1 2 } \beta _ { 2 } + L _ { 2 4 } \right) \alpha _ { 1 } + L _ { 4 3 } \alpha _ { 2 } \right] \beta _ { 3 } ,
$$

其分析结果为： $\Delta F _ { 3 } / \Delta T { = } 2 . 5 7 ~ \mathrm { m m } / \mathrm { ^ q C _ { \circ } }$

$M _ { 3 }$ 镜的位置变化量与焦点 $F _ { 3 }$ 变化量近似是线性关系：

$$
\Delta M _ { 3 } = \Delta F _ { 3 } / \alpha _ { \mathrm { t } }
$$

其中， $\alpha _ { \mathrm { { t } } } = 8 . 6 7$ 是终端光学系统的轴向放大率，因此， $1 \mathrm { m }$ 太阳望远镜焦点调节是通过调整 $M _ { 3 }$ 的位置

实现的， $M _ { 3 }$ 的调节量也同样反应望远镜的焦点变化。由(1)式和(2)式可得调节量与镜筒内温度变化的关系为 $\Delta M _ { 3 } / \Delta T { = } 0 . 3 0 \ \mathrm { m m / ^ { \circ } C }$ 。由此计算 $M _ { 3 }$ 调节量随温度的理论变化值，并实测望远镜打开圆顶开始观测后温度上升较快的2小时内镜筒温度与焦点位置，理论值与实测值如图2。

从理论计算与实测结果看，理论值能大致反应焦点随镜筒内温度的变化趋势，但二者差别较大，实测数据表明，焦点变化速度较理论分析的快，主要是理论分析只考虑了温度因素，而且有一定的简化，实测时，由于无法对真空镜筒内系统各点温度实测，只能以镜筒臂上的温度近似代替。总之， $1 \mathrm { ~ m ~ }$ 太阳望远镜在开始观测的一段时间内，焦点变化较快，需要对焦点做频繁的调整。

![](images/57b49069c867967bfbbfce894fe4b285df8d4712c3930465cfe6882770e098ad.jpg)  
图2 $M _ { 3 }$ 位置理论值与实测结果 Fig.2Ideal value and observational results of $M _ { 3 }$

打开圆顶开始观测以后，望远镜受太阳照射和环境温度的影响，主镜筒内热量累积使望远镜产生离焦。离焦图像与聚焦图像对比( $\lambda = 7 0 5 . 8 ~ \mathrm { { n m } }$ )如图3。

![](images/48f27c96e511eb608257644a7225f736cf602683477c6c42dc7c903f8876b002.jpg)  
图3离焦与聚焦图像对比  
Fig.3Comparison between defocusing image and focusing image

根据文[5]的研究结果，离焦像差小于 $0 . 2 \lambda$ 时，可以忽略对高分辨重建的影响，离焦像差与焦点 $F _ { 3 }$ 的位置变化量的关系为

$$
\omega = \frac { \Delta F _ { 3 } } { 8 \overline { { \lambda } } \left( f / d \right) ^ { 2 } } .
$$

从(3)式可以看出，离焦像差变化率与波长成反比， $1 \mathrm { ~ m ~ }$ 太阳望远镜多通道高分辨成像系统有5个观测通道，最短观测波长为 $\lambda = 3 9 3 . 3 ~ \mathrm { n m }$ ，根据(3)式，该波长对焦点变化最为敏感。根据(1)和(3)式计算 $\lambda = 3 9 3 . 3 ~ \mathrm { n m }$ 时，离焦像差随温度的变化率为 $\Delta \omega / \Delta T { = } 0 . 4 0 3 ~ \lambda / ^ { \circ } \mathrm { C }$ 。

根据文［5］的测量结果，在温度变化较快的时段，1小时内温度变化 $4 . 5 ~ \mathrm { \textdegree C }$ ，即产生近 $1 . 8 \lambda$ 的离焦像差变化，因此，在焦点变化快的时候，1小时内焦点需要调节10次左右，这就要求焦点探测系统能够在6分钟以内完成一次焦点探测和焦点调节。

以上结果表明，虽然 $1 \mathrm { m }$ 太阳望远镜光机系统经过优化设计，但 $F _ { 3 }$ 焦点仍随温度变化。该焦点探测系统研制之前，望远镜都是通过人为判断焦点变化进行调焦，这种方法效率和准确度都不高。因此， $1 \mathrm { ~ m ~ }$ 太阳望远镜焦点实时探测系统是不可或缺的。

# 2总体结构设计

文[9］中的扫描焦点探测法要求在焦点前后位置连续扫描记录多帧图像和每帧图像对应的位置,同时为消除湍流大气的影响，需要连续扫描多组图像进行平均。 $1 \mathrm { ~ m ~ }$ 太阳望远镜多通道高分辨成像系统已投入观测的有 $\mathrm { H } \alpha ( \lambda = 6 5 6 . 3 \ \mathrm { n m } )$ 和TiO( $\lambda = 7 0 5 . 8 ~ \mathrm { { n m } }$ )两个波段，在TiO成像通道进行分光，设计一个同步的成像系统进行图像采集，经后续算法处理后，得到焦点的位置，该位置信息转换为 $M _ { 3 }$ 的调节量后，可以提醒观测人员进行调焦，也可以输送给调焦系统，形成闭环的自动调焦系统。 $1 \mathrm { ~ m ~ }$ 太阳望远镜焦点探测系统的总体结构设计如图4。针对该算法， $1 \mathrm { ~ m ~ }$ 太阳望远镜高分辨率成像系统和光学结构的具体要求和特点，对望远镜焦点探测系统各参数的详细要求如表1。

根据(3)式，离焦像差要求等于 $0 . 2 \lambda$ ， $\lambda = 7 0 5 . 8 ~ \mathrm { { n m } }$ 时，焦点探测系统的焦比 $f / d$ 为25.9， $\Delta F _ { 3 } =$ $7 5 8 ~ { \mu \mathrm { m } }$ ，对应采集图像时的步长要小于 $7 5 8 ~ { \mu \mathrm { m } }$ ，焦点扫描探测算法最后一步是高斯拟合得出焦点位置，为取得较好的拟合效果，扫描范围需要大于 $\pm 2 \lambda$ ，由(3)式计算 $\Delta F _ { _ 3 } = 1 5 . 1 5 \ \mathrm { m m }$ ，因此，扫描范围需要大于 $1 5 ~ \mathrm { m m }$ 。同时，因为要扫描多组进行平均，所以多组之间对应位置点的重复精度也是非常关键的指标。

![](images/b711b70065f1bbce0e7797d251251cb8297f106f903fe7f1835b8484777f3eaa.jpg)  
图4整体结构设计  
Fig.4Overall structure design

# 表1系统对各参数的具体要求

Table 1 The precision requirement of defocus-detect system   

<html><body><table><tr><td>参数名称</td><td>物理意义</td><td>数值</td></tr><tr><td>工作波长/nm</td><td>图像采集系统工作中心波长</td><td>705.8</td></tr><tr><td>视场/'</td><td>图像采集系统的工作视场</td><td>1×1</td></tr><tr><td>焦比</td><td>焦点探测系统的光学系统焦比</td><td>25.9</td></tr><tr><td>每帧图像曝光/ms</td><td>每帧图像的曝光时间</td><td><30</td></tr><tr><td>图像采集频率/Hz</td><td>图像采集的频率</td><td>5</td></tr><tr><td>所需图像组数/组</td><td>一次焦点探测要求的图像组数</td><td>10</td></tr><tr><td>每组图像帧数/帧</td><td>每组图像(完成一次焦点扫描)所需的图像帧数</td><td>50</td></tr><tr><td>位置分辨率/μm</td><td>扫描系统位置分辨率</td><td>1</td></tr><tr><td>位置精度/μm</td><td>扫描系统的位置精度</td><td>5</td></tr><tr><td>扫描步长/μm</td><td>扫描时连续两帧图之间的距离</td><td>758</td></tr><tr><td>步长运动时间/s</td><td>扫描时连续两帧图之间的平台运动时间</td><td>0.2</td></tr><tr><td>扫描步数/步</td><td>每组图像直接扫描点，与每组图像帧数严格一致</td><td>50</td></tr><tr><td>扫描范围/mm</td><td>扫描时，相机在焦点前后运动的距离</td><td>15. 0</td></tr><tr><td>一次焦点时间/min</td><td>完成一次焦点探测所需要的时间</td><td>6</td></tr></table></body></html>

# 3软硬系统设计

# 3.1 硬件系统设计

为了实现图像采集系统的扫描，在调焦成像系统的焦平面安放一个电动位移台，位移台上安装高精度的位置检测系统。平台上安放采集相机，图像采集和平台控制通过一台计算机完成，如图5。

为满足表1的指标要求，相机与位移台的选型和主要参数见表2。系统安装时，位移台的运动方向要与光轴方向保持一致。根据表1和表2，位移台WN230TA100M的最大运动范围是 $1 0 . 0 \ \mathrm { c m }$ ，其位置检测系统的最小分辨率是 $1 ~ { \mu \mathrm { m } }$ ，这相当于位移台的运动方向与光轴方向相差 $1 5 . 4 ^ { \prime }$ 时带来的误差，这就要求位移台的运动方向与光轴方向相差小于 $1 5 . 4 ^ { \prime }$ 。实际系统装调时，在 $1 0 . 0 \ \mathrm { c m }$ 范围移动位移台，用CCD记录穿过光轴中心的激光光斑的质心最大平移，然后折算成位移台的运动方向与光轴方向的夹角，将这一误差调节在 $5 ^ { \prime }$ 以内，完全满足 $1 5 . 4 ^ { \prime }$ 的要求。相机和位移台在焦点前后的位置与其它高分辨成像通道采用齐焦进行定标，保证焦点总能处在系统扫描范围内。

![](images/8dee0866b892bf58e5bac05f0fce16fefdcb8550c45632606bd32e0d59f5fcf8.jpg)  
图5硬件系统结构及工作中的平移台与相机Fig.5Hardware system structure and system at work

表2相机与位移台的主要参数  
Table2Main feature of hardware   

<html><body><table><tr><td colspan="2">相机型号与主要参数</td><td colspan="2">位移台型号与主要参数</td></tr><tr><td>厂家信息</td><td>JAI集团</td><td>厂家信息</td><td>乐创自动化公司</td></tr><tr><td>相机型号</td><td>BM-141GE</td><td>位移台型号</td><td>WN230TA100M</td></tr><tr><td>芯片类型</td><td>CCD</td><td>运动范围</td><td>10 cm</td></tr><tr><td>靶面大小</td><td>1 392 × 1 040 pixels</td><td>编码器分辨率</td><td>1 μm</td></tr><tr><td>像元尺寸</td><td>6.45 μm</td><td>控制电机类型</td><td>步进电机</td></tr><tr><td>AD位数</td><td>8/12位</td><td>电机控制器型号</td><td>MPC08</td></tr><tr><td>读出速度</td><td>30帧/秒</td><td>系统控制模式</td><td>位置式/速度式</td></tr><tr><td>曝光时间范围</td><td>63 μs~33 ms</td><td>零点类型</td><td>光耦</td></tr><tr><td>读出接口</td><td>以太网</td><td>限位开关类型</td><td>机械式接近开关</td></tr></table></body></html>

# 3.2软件系统设计

软件系统主要完成相机控制与数据采集、相机与位移台的同步控制和数据处理并计算焦点位置等功能，软件系统的界面和工作流程分别如图6和图7。软件在WIN7平台上采用 ${ \mathrm { V C } } + +$ 开发，系统采用多线程实现[10]，主要包括3个线程：（1)系统主线程，包括界面和消息响应的实现；（2)图像采集、平移台控制和数据处理线程；（3)图像显示线程。系统完成一次检测焦点需要 $6 ~ \mathrm { m i n }$ 。

# 4位移台和焦点探测系统性能测试

# 4.1位移台性能测试

位移台性能测试主要测试位移台的重复移动精度是否满足要求。平台移动有两种工作模式：位置模式和速度模式，位置工作模式是给位移台一个指定的扫描起点和步进距，等位移台完成一步运动后保存平台的位置并采集一帧图像；速度模式是给位移台一个恒定的运动速度，移动过程中连续采集图像并记录平台的位置。为平滑大气的影响，需要连续采集多组图像进行平均，因此，组与组之间的位置精度需要满足算法要求，即平台的重复移动精度。测试结果如图8。

![](images/b27606883595c8401862283e6849e06919a6ced522834cb27b8d5175f7a8de0d.jpg)  
图6软件界面

测试时需满足连续两帧之间的位置差小于$\Delta F ( 7 5 7 ~ \mu \mathrm { m } )$ ，因此，对位置模式进行测试时，步长设定为 $3 0 0 ~ { \mu \mathrm { m } }$ ，扫描一次采集50个点的位置数据，来回扫描10次，对应每个位置都采集了10个数据，然后计算10个位置数据均方根值，得到一个点的位置重复精度，逐个计算50个点位置均方根值，如图8（a）。50个点的位置均方根值中，最大为 $3 . 0 3 ~ \mu \mathrm { m }$ ，最小为 $0 . 7 8 \mu \mathrm { m }$ ，其重复移动精度满足系统精度要求。对速度模式进行测试时，位移台移动速度为 $2 5 0 0 ~ \mu \mathrm { m / s }$ ，每组同样采集50个点的位置数据，来回扫描10次，然后计算50个点的位置均方根值，如图8(b)。50个点的位置均方根值中，最大为8.24$\mu \mathrm { m }$ ，最小为 $5 . 7 2 ~ \mu \mathrm { m }$ 。通过比较可以看出，速度模式下位置数据的均方根值较位置模式下的均方根值大，因此，位移台工作在位置模式的重复移动精度较工作在速度模式的重复移动精度高，系统更稳定。

# 4.2焦点探测系统测试

焦点探测系统实验主要测试整个系统对焦点的探测精度，包括位移台、CCD采集系统、图像处理、焦点探测算法的一个综合测试。实验过程如下：

![](images/d6d15963b28f1e1cefdf441b998f726239ea3b55def0ceaff08be141f97c436c.jpg)  
Fig.6Software Interface   
图7图像采集与处理线程 Fig.7Image acquiring and processing thread

(1)将 $1 \mathrm { m }$ 太阳望远镜对准日面上的任意观测区域，采集调焦系统中CCD的平场和暗场;(2)通过 $1 \mathrm { m }$ 太阳望远镜的 $M _ { 3 }$ 调焦系统，人为随机调节 $M _ { 3 }$ 位置，即改变望远镜的焦点，同时记录 $M _ { 3 }$ 调节量，并根据(2)式转换为焦点探测系统中的焦点变化量;(3)打开焦点探测系统，测量并记录一次焦点变化量；(4)反复进行(2)和(3)操作，多次测量;(5)计算多次测量中焦点实测变化量与给定变化量的偏差，并统计均方根值。图9 是进行47次实验得到的焦点探测偏差分布图，均方根值是 $4 9 0 ~ { \mu \mathrm { m } }$ 。

![](images/bb3218294e4f08dc3aefb72888b0b27cdecdd5ac20cab6b078272754e478f8be.jpg)  
Fig.8The experimental results of repeat precision

![](images/f5aaa742cdb0c575d17ee893b903796e5c078ac80c872f4fa1465bc226e666d4.jpg)  
图8重复移动精度测试结果  
图9焦点探测偏差 Fig.9Error of defocus-detect system

从焦深角度看，当离焦距离处在焦深内时系统成像是清晰的，而焦点探测的均方根值小于半焦深时则认为是可信的。 $1 \mathrm { m }$ 太阳望远镜的焦深计算公式如下：

$$
\delta = \pm 2 \stackrel { \_ } { \lambda } \left( f / d \right) { } ^ { 2 } .
$$

把系统的焦比 $f / d = 2 5 . 9$ 和波长 $\overline { { \lambda } } = 7 0 5 . 8 ~ \mathrm { { n m } }$ 代入(4)式得到半焦深为 $9 4 7 ~ { \mu \mathrm { m } }$ ，焦点探测系统偏差的均方根值为 $4 9 0 ~ { \mu \mathrm { m } }$ ，因此从焦深角度，该调焦精度能够满足要求。

从天文高分辨统计重建的角度看，探测精度应小于 $0 . 2 \lambda$ 。把 $f / d = 2 5 . 9$ 和 $\overline { { \lambda } } = 7 0 5 . 8 ~ \mathrm { { n m } }$ ， $\Delta F _ { 3 } =$ $4 9 0 ~ \mu \mathrm { m }$ 代入(3)式得到焦点探测偏差带来的离焦像差为 $0 . 1 2 8 \lambda$ ，因此从天文高分辨统计重建的角度来看也是可行的。

根据对系统的探测精度和时间性能的测试，系统能有效探测 $1 \mathrm { m }$ 太阳望远镜的焦点变化，系统于2016年8月份投入 $1 \mathrm { m }$ 太阳望远镜的常规观测中使用，使用调焦系统的观测数据可参考 $1 \mathrm { m }$ 太阳望远镜的数据网站。系统投入使用后，还可以有效监测 $1 \mathrm { ~ m ~ }$ 太阳望远镜的焦点变化情况，图10是 $1 \mathrm { ~ m ~ }$ 太阳望远镜在4天中的焦点调节( $M _ { 3 }$ 位置变化)情况，从图10调焦量随时间的变化可以看出，在望远镜对准太阳后，焦点变化较快，需要不断调焦，开始观测后两个小时左右，焦点变化趋于稳定，在中午

11：00到13：00，焦点变化在一个方向达到最大，随后往反方向变化，但变化相对于刚开机观测时缓慢，也需要不断调焦，这是由于太阳高度引起的辐射变化也是造成望远镜光机系统温度变化的原因之一。

![](images/a184f5d51ba94020e3887a4ff1edefd28e4ed322c5d6e60596d8b3cfc94875fb.jpg)  
图10焦点探测系统检测到的焦点变化  
Fig.10Focus variation detected by defocus-detect system

# 5总结

本文针对 $1 \mathrm { m }$ 太阳望远镜在观测过程中焦点实时变化的问题，根据文[9]提出的焦点探测方法并结合 $1 \mathrm { m }$ 太阳望远镜的光机结构，设计了焦点探测系统。系统经过测试并已经投入使用，3个月运行结果表明：系统能准确地探测 $1 \mathrm { m }$ 太阳望远镜的焦点变化，并提供给观测人员焦点调焦量，提高了望远镜的观测效率和数据质量。下一步工作需要改造 $1 \mathrm { m }$ 太阳望远镜的焦点调节部分，与焦点探测系统形成闭环控制，进一步提高望远镜的工作效率。

# 参考文献：

[1] Liu Zhong，Xu Jun，Gu Bozhong，et al. New vacuum solar telescope and observations with highresolution [J].Research in Astronomy and Astrophysics，2014，14(6）:705-718.  
[2] Xu Zhi，Jin Zhenyu，Xu Fangyu，et al. Primary observations of solar filaments using the multi-channel imaging system of the New Vacuum Solar Telescope [C］// Proceedings of theInternational Astronomical Union.2013：117-120.  
[3] 顾伯忠，左恒.云南天文台 $1 \mathrm { ~ m ~ }$ 红外太阳望远镜的主镜热力学分析［J］．天文研究与技术国家天文台台刊，2008，5(1）：83-90.Gu Bozhong，Zuo Heng.The thermal analysis of the primary mirror of 1m infrared solar telescopeat Yunnan Observatory ［J].Astronomical Research & Technology——Publications of NationalAstronomical Observatories of China，2008，5（1） :83-90.  
[4] 向永源，刘忠，金振宇，等.高分辨率太阳图像重建方法［J].天文学进展，2016，34（1)：94-110.Xiang Yongyuan，Liu Zhong， Jin Zhenyu，et al. High resolution solar image reconstruction [J].Progress in Astronomy，2016，34(1） : 94-110.  
[5] 方玉亮，金振宇，刘忠，等.一米新真空太阳望远镜离焦对高分辨太阳观测图像重建的影响［J].天文研究与技术，2015，12(2)：183-188.Fang Yuliang，Jin Zhenyu，Liu Zhong，et al.A study of influences of defocus aberrations onhigh-resolution image reconstruction for data from the new vacuum solar telescope of the YNAO[J]．Astronomical Research & Technology，2015，12(2）：183-188.  
[6] 梁翠萍，李清安，乔彦峰，等．简析光学系统的自动调焦方法［J]．电光与控制，2006，13(6) : 93-96.Liang Cuiping，Li Qingan， Qiao Yanfeng，et al. On auto-focusing technology of optical system[J].Electronics Optical & Control，2006，13（6):93-96.  
[7] 李晓燕，朱庆生．一种基于图像清晰度评价的天文望远镜自动调焦系统［J].天文研究与技术——国家天文台台刊，2008，5(3)：294-298.Li Xiaoyan， Zhu Qingsheng. An automatic focusing system of astronomical telescope based onimage definition evaluation［J].Astronomical Research & Technology———PublicationsofNational Astronomical Observatories of China，2008，5(3）:294-298.  
[8] 郭晶晶.太阳望远镜的高精度自动导行和自动调焦方法的研究［D].昆明：昆明理工大学，2015.  
[9] 方玉亮.NVST焦点探测［D].昆明：中国科学院云南天文台，2014.  
[10] 张宏，黄小诚. ${ \mathrm { V C } } + +$ 语言多线程编程及其实现［J].科技信息，2008(7)：64-65.Zhang Hong，Huang Xiaocheng. Multithread programming in ${ \mathrm { V C } } + +$ [J].Science & TechnologyInformation，2008(7） : 64-65.

# NVST Defocus-Detect System

Li Pengfei $^ { 1 , 2 }$ ，Ju Qinghua’,Fang Yuliang $^ { 1 , 2 }$ ，Liu Guangqian1 (1.Yunnan Observatories，Chinese Academic of Sciences，Kunming 650o11,China,Email:lpf@ynao.ac.cn; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China)

Abstract：During the continuous observation in 1-meter New Vacuum Solar Telescope，the solar radiation changes the temperature of the telescope surface，resulting in the thermal deformation on the optical and mechanical structure of the telescope.This results in real-time variation of the telescope focus，which produces thedefocus aberration inthe observation data.Thus it is of importance for theobservationto detect and correct the defocus.This paper describes the design and implementation of a defocus-detect system，based on the optical and mechanical structure of this telescope，and the scanning defocus-detect algorithm is used.Firstly, thevariation of defocus causing by temperature change is analyzed and the overalldesign of the defocus-detect system is given.Then the detailed design and implementation of its hardware and software system is described, subsequentlythe test results of the repeat position precision and detect error show that this defocus-detect system meets the requirement of the observation.At the last part of this paper，the performance of this system on the telescope with 3-months continuous observation is displayed.And it shows that this system can detect and correct the real-time variation of the telescope defocus，and has a positive influence on thequality of the observation data.

Key words: Focus detect; 1-meter New Vacuum Solar Telescope; Real-time variation of the telescope focus ; Repeat precision