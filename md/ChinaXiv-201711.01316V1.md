# CN 53-1189/P ISSN 1672-7673

# 一种速度平滑高程的增强定位方法

刘成，李芳(1.北京跟踪与通信技术研究所，北京100094；2.中国科学院物理研究所，北京100190)

摘要：为提高全球导航卫星系统定位精度与连续性，提出结合使用高程坐标分量与速度分量，设计构成一种组合滤波器。利用速度测量值不断对用户高程进行平滑与修正，获得高精度的高程坐标值，并由此对测量方程组形成高程约束条件，进而提高全球导航卫星系统三维定位精度及接收机钟差解算精度。同时，由于滤波器处理后的高程值序列具有较高的精度和良好的平滑性，因此特别适于拟合与外推，从而更好地辅助卫星信号缺失的非完备星座情况，实现连续三维定位。最后，通过全球定位系统实测实验对方法进行了分析，验证了其可行性与实用性。

关键词：增强定位方法；全球导航卫星系统；卫星导航定位；高程约束；非完备情况中图分类号：TN961 文献标识码：A 文章编号：1672-7673(2017)02-0261-07

# 1概述

受卫星星座几何分布图形的影响，卫星导航系统在高程方向上的定位精度一般较差。其单频粗码定位误差一般为几米至十几米，在信号遮挡或定位条件较差时甚至达几十米。并且，作为同一组最小二乘估计解，高程解算值与其他未知数之间是相关的，高程坐标的误差也会影响用户二维平面坐标及接收机钟差的解算精度。因此，高程定位精度欠佳一直是卫星导航系统存在的一大问题。

针对这一问题，学者们进行了大量的研究，希望能够通过其他方法或手段获得比直接定位解算更精确的高程值，以改善高程定位误差较大的问题。同时，这样也能够对测量方程组形成高程约束条件，从而提高二维平面及接收机钟差的解算精度。在我国北斗一代卫星定位系统及文[1-3］中，曾采用数字高程模型(Digital Elevation Model，DEM)与电子地图获得用户大地高。而在中国区域卫星定位系统（China Area Positioning System，CAPS) $\ ^ { [ 4 - 6 ] } \mathrm { I }$ 期中，也曾利用气压测高技术辅助当时尚不完善的卫星星座实现三维定位[]。文[8-9]提出进一步将气压测高技术应用于地面移动通信基站中，将其作为气压校正基准点并利用通信传输链路将相关测量数据传送给附近用户，以修正获得高精度的用户绝对高程值。文[10]根据高程坐标分量与接收机钟差之间存在高相关性的特征，在差分站的基础上模拟和预测接收机钟差，并在定位方程组中添加一个关于接收机钟差变化的辅助方程，以减小垂直精度因子值，提高高程定位精度[10-11]

以上方法虽然能在不同程度上改善高程误差，提高定位精度，但都需要增加额外设施或手段，在增加投入与成本的同时，也加大了定位系统的复杂性。为此，本文提出一种利用卫星导航系统自身定位信息有效提高高程定位精度的方法。通过引入高程方向速度测量值、结合高程定位值，设计组成一个一定长度的滤波器，不断利用最新测量值对用户高程进行实时平滑处理。由于即使当高程方向上的定位误差较大时，高程方向上的速度值也能够具有很高的精度，因此滤波器能够有效获得高精度的用户实时定位高程值，且无需增加任何额外设备。该方法既能用于正常定位，有效提高定位精度，也能用于卫星信号短暂缺失的非完备定位情况，帮助实现三维定位。另外，由于卫星定位星座分布的原因，其高程坐标分量与接收机钟差之间存在着很高的相关性[11]。因此在高程精度得到提高的同时,

其接收机钟差解算精度也能相应提高。最后，通过全球定位系统实测实验对方法进行了分析与验证。  
实验结果表明，该方法效果显著，简单易行，具有很强的实用性。

# 2速度平滑高程原理与方法

在车载、船舶定位等应用领域，用户运动状态符合牛顿惯性运动定律，其高程位置的变化一般较为缓慢和平滑。因此，将每个历元的定位过程独立起来、以单点定位解算结果得到的高程值作为最终的输出结果，显然不是最佳选择。实际上，由于即使当高程坐标分量的定位误差较大时，高程速度分量也能够具有很高的精度，因此完全可以将两者结合起来，利用高程解算值获得绝对起始值，利用速度解算值获得准确的高程变化量，从而构成一个组合滤波器，对高程值进行平滑。

这种思想与卫星导航中载波相位平滑伪距测量值的方法[12-13]类似，都是通过对精度欠佳的绝对测量值取均值的方式获得一个较为准确的绝对起始值，并利用高精度的相对测量值获得该绝对起始值的变化量。

# 2.1速度平滑高程滤波器设计

对于用户在最新历元 $n$ 的高程值，可利用之前 $l$ 个高程解算值 $H _ { n - i } ( i = 1 , 2 , \cdots , l )$ 获得其 $l$ 个高程估计值 $\hat { H } _ { n , k } ( k = 1 , 2 , \cdots , l )$ ：

$$
\begin{array}{c} \begin{array} { r l } & { ( \hat { H } _ { n , 1 } = H _ { n - 1 } + v _ { n - 1 } ^ { H } T  } \\ & {  \vphantom { \int } \hat { H } _ { n , 2 } = H _ { n - 2 } + ( v _ { n - 1 } ^ { H } + v _ { n - 2 } ^ { H } ) T  } \\ & {  \vphantom { \int } \ldots  } \\ & {  ( \hat { H } _ { n , l } = H _ { n - l } + ( v _ { n - 1 } ^ { H } + v _ { n - 2 } ^ { H } + \ldots + v _ { n - l } ^ { H } ) T  } \end{array}  ,  \\ & {   \vphantom { \int } \hat { H } _ { n , l } = H _ { n - l } + ( v _ { n - 1 } ^ { H } + v _ { n - 2 } ^ { H } + \ldots + v _ { n - l } ^ { H } ) T  } \end{array}
$$

其中， ${ v _ { n - k } ^ { H } } ( k { = } 1 , 2 , \cdots , l )$ 为高程方向的速度分量； $k$ 代表参与平滑的历元数； $T$ 为定位时间间隔。可根据这一系列估计值以获得最新历元 $n$ 的高程平滑值 ${ \overline { { H } } } _ { n }$ ：

$$
\overline { { H } } _ { n } = \frac { 1 } { l } \sum _ { j = 1 } ^ { l } \hat { H } _ { n , \ j } \ .
$$

若考虑当前历元 $\mathbf { \Omega } _ { n }$ 时，用户实际定位解算结果 $H _ { n }$ ，则可利用上述方法先求得 $\overline { { H } } _ { n - 1 }$ ，并按加权均值方式获得平滑后的高程值：

$$
\overline { { { H } } } _ { n } = \frac { 1 } { l } H _ { n } + \frac { l - 1 } { l } ( \overline { { { H } } } _ { n - 1 } + v _ { n - 1 } ^ { H } T ) .
$$

（3)式即为一般的速度平滑高程滤波器， $\mathbf { \xi } _ { l }$ 为滤波器的长度， $\mathbf { \xi } _ { l }$ 值越大， $\overline { { H } } _ { n }$ 越依赖于速度值， ${ \overline { { H } } } _ { n }$ 也就越平滑。

对于何时开启滤波器分为两种情况：一是等待定位历元数达到滤波器长度 $l$ ，由此获得准确的平滑值 $\overline { { H } } _ { n - 1 }$ ，再根据(3)式开始正常运行滤波器；二是从定位过程一开始即开启滤波器，采用正常定位后的第1个高程解算值 $H _ { 1 }$ 初始化 ${ \overline { { H } } } _ { n }$ 的值：

$$
\begin{array} { r } { \overline { { H } } _ { 1 } = H _ { 1 } \ , } \end{array}
$$

并根据历元数的增加，不断更新 ${ \overline { { H } } } _ { n }$ 的值，直至达到滤波器长度 $l$ 为止。第2种方式能够使滤波器从定位一开始即得到运用，但由于定位初期历元数较少，因此可能会受较大误差值的影响而在初期产生一定的偏差，滤波器需要经过一段时间的运行并达到理想设计长度后，才能逐渐趋于稳定并消除此偏差。

# 2.2滤波器精度分析

由(1)式至(3)式可以看出，速度平滑高程滤波器的误差主要来自两方面：一是各历元实际高程解算值经平均后剩下的误差；二是各历元速度解算值在滤波器长度 $\mathbf { \xi } _ { l }$ 内的累积误差。

由(1)式可得

$$
\overline { { H } } _ { n } = \frac { 1 } { l } \sum _ { i = 1 } ^ { l } H _ { n - i } \ + \frac { T } { l } \big [ \boldsymbol { v } _ { n - 1 } ^ { H } \ + \ \big ( \boldsymbol { v } _ { n - 1 } ^ { H } \ + \boldsymbol { v } _ { n - 2 } ^ { H } \big ) \ + \ \cdots \ + \ \big ( \boldsymbol { v } _ { n - 1 } ^ { H } \ + \boldsymbol { v } _ { n - 2 } ^ { H } \ + \ \cdots \ + \boldsymbol { v } _ { n - l } ^ { H } \big ) \ \big ] \ ,
$$

设每次定位的高程坐标分量均方误差为 $\sigma _ { H }$ ，高程速度分量均方误差为 $\boldsymbol { \sigma } _ { v }$ ，根据误差传播律可得 $\overline { { H } } _ { n }$ 的均方误差 $\sigma _ { \overline { { { H } } } } ^ { [ 1 4 ] }$ ：

$$
\begin{array} { l } { { \displaystyle \sigma _ { \overline { { { H } } } } = \sqrt { \frac { 1 } { l ^ { 2 } } l \sigma _ { _ H } ^ { 2 } } + \sqrt { \frac { T ^ { 2 } } { l ^ { 2 } } \frac { l ( l + 1 ) } { 2 } \sigma _ { _ v } ^ { 2 } } = \sqrt { \frac { 1 } { l } \sigma _ { _ H } ^ { 2 } } + \sqrt { \frac { T ^ { 2 } ( l + 1 ) } { 2 l } \sigma _ { _ v } ^ { 2 } } } } \\ { { \displaystyle ~ \approx \sqrt { \frac { 1 } { l } } \ \sigma _ { _ H } + T \sqrt { \frac { 1 } { 2 } } \ \sigma _ { _ v } } } \end{array} ,
$$

目前全球导航卫星系统的高程速度误差 $\sigma _ { v }$ 一般小于 $0 . 3 \mathrm { m / s }$ ，而接收机定位间隔 $T$ 约为 $0 . 1 \sim 1$ So因此，(6)式右端由速度误差造成的影响很小。故可近似认为滤波器精度为

$$
\sigma _ { \overline { { { H } } } } \approx \frac { 1 } { \sqrt { l } } \ \sigma _ { H } .
$$

通过一个长度为 $\mathbf { \xi } _ { l }$ 的速度平滑高程滤波器，能够将高程坐标分量均方误差减小至原来的约 $1 / \sqrt { l }$ 。

# 3速度平滑高程定位方法

# 3.1正常星座情况下的增强定位方法

当可视卫星多于4颗时，同时存在两类定位算法：后台不断利用正常定位解算得到的高程值 $H _ { n }$ ，通过滤波器得到用户实时高程平滑值 ${ \overline { { H } } } _ { n }$ ；而增强算法则将 ${ \overline { { H } } } _ { n }$ 作为已知量处理，重新对测量方程组进行求解。方法流程如图1。

![](images/eef868216427afcd8d93631d580f1cbc9a893d9a6967dc69a89ff9037154bf21.jpg)  
图1增强算法流程图  
Fig.1Enhancement algorithm flowchart

此时，增强算法实际上相当于减少了一个未知数，对原测量方程形成高程约束条件：

$$
\left\{ \begin{array} { l } { \displaystyle { \sqrt { \left( x _ { i } - x \right) ^ { 2 } + \left( y _ { i } - y \right) ^ { 2 } + \left( z _ { i } - z \right) ^ { 2 } } + c \Delta t = \rho _ { i } ( i = 1 , ~ 2 , ~ \cdots , ~ n ) } } \\ { \displaystyle { \frac { x ^ { 2 } + y ^ { 2 } } { ( a + h ) ^ { 2 } } + \frac { z ^ { 2 } } { ( b + h ) ^ { 2 } } = 1 } } \end{array} \right. .
$$

其中， $n \geqslant 4$ 为观测卫星个数； $x _ { i }$ 、 $y _ { i }$ 和 $z _ { i }$ 为第 $i$ 颗卫星在地心地固坐标系下的坐标; $\rho _ { i }$ 为第 $i$ 颗卫星至用户的伪距观测值； $x , \ y$ 、 $z$ 和 $\varDelta t$ 是待求量，分别为用户接收机位置坐标及接收机钟差； $\textit { a , b }$ 为地球基准椭球的长、短半轴； $h$ 为用户海拔高 ${ \overline { { H } } } _ { n }$ 经简单坐标转换后的大地高。关于(8)式的具体解算方法可见文[15-18]。

# 3.2非完备情况下的辅助定位方法

当可视卫星少于4颗时，称为非完备星座情况。若不依赖其他辅助手段或信息，用户将无法完成正常定位。此时，可利用之前稍早的高程定位值进行外推，以获得非完备情况下的高程预测值，从而将定位解算问题变为二维。

相比于直接对高程定位值进行建模和外推，利用根据滤波器进行平滑后的高程值序列进行外推的主要优势在于：(1)经过滤波器平滑后的高程值更为准确，因此对其进行建模和预测也能够获得更高的精度；（2)由于平滑后得到的高程序列曲线更为明显，因此在对其进行拟合和外推时能够采用更少的先验数据，减小计算量；（3)由于各个历元的高程值经过了足够长度窗口的平滑，所以可以有效避免和克服观测数据突变带来的粗差，抗差性显著提高。

另外需要指出，预测高程辅助非完备定位的效果很大程度上取决于用户所处的运动环境。若用户位于较平坦的地区，高程变化较为缓慢，则预测高程可以在很长一段时间内辅助非完备定位。甚至可以采用对先验高程值序列进行均值或加权均值的处理方法，即能获得良好的定位效果。相反，若用户高程变化较为剧烈，预测高程将难以反映真实高程的变化情况，从而使方法效果受限。

# 4实验与分析

利用中科微电子有限公司研制的CASIC卫星导航接收机模块，以 $1 ~ \mathrm { H z }$ 频率通过串口传输方式输出自定义二进制格式的全球定位系统卫星广播星历及单频、C/A码伪距测量数据。基于该模块及输出编程，并进行实时定位实验与验证。

为更明显地分析和比较滤波器及定位方法在正常星座情况时的性能，在某个具有一定遮挡的已知坐标点上进行长时间的静止测量。首先，直接解算得到用户在该点上全部观测历元的高程坐标值；然后，采用一个长度为100 s的速度平滑高程滤波器对其进行平滑处理，两者结果如图2。

![](images/d11437b69cc8f81fac75292a272ae0215efdfeeb9b7d357cd0a856c5350a538b.jpg)  
图2高程坐标分量对比  
Fig.2Precision comparison of elevations

可以看出，经速度平滑后得到的高程更加平滑、稳定，与真实高程值更为吻合。在此基础上按图1流程进行增强定位方法解算，并与原定位结果比较，结果如图3。

统计图3(a)中的误差可知，增强算法将原始二维定位误差减小了约 $30 \%$ ，具有显著的效果；而图3(b)中的接收机钟差值序列也更为平滑，符合实际规律，说明由于高程坐标分量与接收机钟差之间的高相关性，更准确的高程确实能够带来更准确的接收机钟差值，从而能够帮助提高接收机的授时精度。

![](images/6c8eef989e71292a3700371ff096fe6d2f5fcf29a07eff9507aeb31af6e6a28d.jpg)  
图3增强算法定位解算结果对比。（a）二维定位结果对比；（b）接收机钟差解算结果对比 Fig.3The positioning results of enhanced algorithm and original method.（a）Comparison for 2D positioning results；（b）Comparison for the clock error of the GPS receiver

# 5结论

受星座分布几何图形的影响与制约，高程定位精度一直是全球导航卫星系统的一大短板。为此,曾提出使用电子地图匹配、气压测高、基准站差分修正等多种手段以获得更准确的高程值，从而提高全球导航卫星系统高程及三维定位精度。然而，这些方法通常需在用户或定位基准端配备额外的硬件设施，在加大成本的同时也增加了系统的复杂性。并且，由于电子地图及气压测高技术一般只能将用户高程定位精度提高至 $1 \mathrm { m }$ 左右，因此仅能应用于单频、粗码等一般民用领域。而当采用差分、多频或载波相位等高精度定位手段后，全球导航卫星系统高程定位精度本身已优于 $1 \mathrm { ~ m ~ }$ ，此时上述方法将难以继续起到提升作用。

实际上，类似于载波相位平滑伪距的方法，卫星定位中高精度的相对测量值总是能够对绝对测量值进行修正，提高其测量精度。基于这一思想，本文提出结合使用高程坐标分量与速度分量，利用高精度的速度解算值对高程定位值进行平滑与修正。由此设计的组合滤波器简单规范，易于实现，且无需增加任何额外设备。通过一段不长时间的平滑过程，既能获得高精度的高程坐标，具有很强的工程实用性。并且，由于当高程分量精度提高时，其速度分量亦能具有相对更高的精度，因此方法能够适用于各种精度需求的应用领域。

实测实验与分析证明，该方法能够显著提高全球导航卫星系统高程及三维定位精度。同时，由于滤波器处理后的高程值序列具有很高的精度与良好的曲线平滑性，因此适于拟合与外推，从而辅助卫星信号缺失的非完备情况实现三维定位。由于卫星定位高程坐标分量与接收机钟差之间存在很高的相关性，在高程精度得到提高的同时，接收机钟差解算精度也能相应提高，从而获得更高的授时精度。因此，该方法能够在多方面对全球导航卫星系统进行增强与辅助，具有良好的实用效果和应用价值。

# 参考文献：

[1] Ptasinski P，Cecelja F，Balachandran W. Altitude aiding for GPS systems using elevation map datasets [J]. Journal of Navigation，2002，55(3）: 451-462.   
[2] French R L. Map matching origins,，approaches and applications [C]// Proceedings of the Land Vehicle Navigation. 1989:91-116.   
[3] Zavoli W B,Honey S K. Map matching augmented dead reckoning [C]// Vehicular Technology Conference. 1986:359-362.   
[4] 艾国祥，施浒立，吴海涛，等.基于通信卫星的定位系统原理［J].中国科学G辑：物理学 力学天文学，2008，38(12)：1615-1633.   
[5] Ai Guoxiang，Shi Huli，Wu Haitao，et al.The principle of the positioning system based on communication satelites [J]. Science in China Series G: Physics，Mechanics and Astronomy, 2009，52(3): 472-488.   
[6] Ai Guoxiang，Shi Huli，Wu Haitao,et al. A positioning system based on communication satelites and the Chinese Area Positioning System（CAPS）[J].Chinese Journal of Astronomy and Astrophysics，2008，8(6) :611-630.   
[7] Ai Guoxiang，Sheng Peixuan，Du Jinlin，et al.Barometric altimetry system as virtual constellation applied in CAPS [J]. Science in China Series G:Physics，Mechanics and Astronomy，2009, 52(3) : 376-383.   
[8] 张丽荣，施浒立，邓中亮，等．基于基准站的气压相对测量求得精确高程的方法：中国， 201110082773.5［P].［2016-05-20].   
[9] 杜晓辉，裴军，张丽荣，等.基于地面移动通信基站的差分气压测高方法［J］.北京航空航 天大学学报，2013，39(1)：83-88. Du Xiaohui，Pei Jun，Zhang Lirong，et al.Diferential barometric altimetry method based on mobile phone base stations [J]. Journal of Beijing University of Aeronautics and Astronautics, 2013，39(1) : 83-88.   
[10] Misra P,Pratt M，Burke B，et al.Adaptive modeling of receiver clock for meter-level DGPS vertical positioning ［C]// Proceedings of the 8th International Technical Meeting of the Satellite Division of The Institute of Navigation.1995：1127-1135.   
[11] 谢钢.GPS原理与接收机设计［M]．北京：电子工业出版社，2009.   
[12] Hatch R. The synergism of GPS code and carrier measurements [C]// Proceedings of the Third International Geodetic Symposium on Satelite Doppler Positioning.1982.   
[13] Misra P，Enge P.Global Positioning System-signals，measurements，and performance [M]. Lincoln，MA : Ganga-Jamuna Press，2001.   
[14] 武汉大学测绘学院测量平差学科组.误差理论与测量平差基础［M].武汉：武汉大学出 版社，2003.   
[15] 孔祥元，郭际明，刘宗泉，等.大地测量学基础［M].武汉：武汉大学出版社，2010.   
[16] 乔仰文，辛久志，王晓辉，等.GPS高程转换的若干问题的研究［J]．测绘通报，1999 (11): 17-19. Qiao Yangwen，Xin Jiuzhi，Wang Xiaohui，et al.A study on some problems of GPS height transformation [J]. Bulletin of Surveying and Mapping，1999(11） : 17-19.   
[17] 施浒立，孙希延，李志刚.转发式卫星导航原理［M]．北京：科学出版社，2009.   
[18] Shi Huli，Pei Jun.The solutions of navigation observation equations for CAPS［J]. Science in China Series G：Physics，Mechanics and Astronomy，2009，52(3）:434-444.

# An Enhanced Satellite Positioning Algorithm Based on Height Smoothing with Speed

Liu Cheng'， Li Fang² (1.Beijing Instituteof Trackingand Telecommunication Technology，Beijing10o94，China，Email:liucheng@beidou.gov.cn; 2.Institute of Physics，Chinese Academy of Sciences，Beijing 10019o,China)

Abstract:In order to improve the accuracyand continuity of satelite positioning，a combined filter is proposed to be designed and constituted by using a combination of height coordinate component and velocity component in this paper.User height is continually smoothed and revised to obtain a height coordinate of high precision，and thus forming a height constraint of measurement equations.And then，the accuracy of 3D positioning and receiver clock solution results could also be improved.Meanwhile，due to the high precision andfavorable smooth texture of the height values after filter processing，they are especially suitable for fitting and extrapolation，and could help to asist the incomplete situation while the signal of GPS is lostand realize continuous 3D positioning.At last，feasibility andavailabilityof the method areanalyzedand verified by GPS positioning experiment.

Key Words:Enhanced Satellte Positioning Algorithm；Global Navigation Satellte System；Satellte navigation and positioning；Height constraint； Incomplete constellation