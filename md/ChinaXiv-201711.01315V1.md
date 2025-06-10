# CN 53-1189/P ISSN 1672-7673

# GEO暗弱空间碎片目标搜索策略分析

汤儒峰',²，李语强'，李荣旺1(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京 100049)

摘要：在地球同步轨道特征的基础上，介绍了地球同步轨道空间碎片的运动特征。针对地球同步轨道暗弱空间碎片进行观测的搜索方案，考虑目标的预报误差以及视场的大小，用数学方法分别计算了同心圆搜索与爬楼梯搜索的成功概率，并由计算结果分析了两者的特征，认为在一般情况下，同心圆搜索方案具有更高的搜索效率。

关键词：地球同步轨道空间碎片；光学观测；搜索策略；搜索概率图分类号：P135 文献标识码：A 文章编号：1672-7673(2017)03-0304-06

空间碎片又称为轨道碎片，是指宇宙空间中除了正常工作的飞行器外所有的人造物体，大到报废的卫星整体，小到发动机点火产生的粉末，都属于空间碎片的范畴[1]。从1957年10月4日前苏联第1颗人造卫星入轨，人类进入了航天时代。在过去的半个多世纪里，人类已经进行了4000多次航天发射活动，将6000多个航天器送人了宇宙空间[2」。目前，具有独立发射能力的国家已超过10个，拥有航天资产的国家超过50个，在用的航天器数量近千个。航天活动带来诸多好处的同时也带来了很多负面影响，其中严重的负面影响是空间碎片的不断增加。据统计，地球轨道上可编目的空间物体数量(尺度在 $1 0 \ \mathrm { c m }$ 以上，绝大部分是碎片)从1981年的5000个增长到了2016年4月的17000多个①（图1)，从图1可以看出，这些物体中解体产生的碎片(红色线条)占了很大一部分。

![](images/f37526bff0613946a8e4061508ade48e3420e73b0522dcd1c7065bf515791699.jpg)  
图1空间碎片数量变化  
Fig.1Variation of space debris quantities

$^ *$ 基金项目：国家自然科学天文联合基金（U1631134）；中国科学院青年创新促进会（2014048）资助，收稿日期：2016-07-19；修订日期：2016-08-16作者简介：汤儒峰，男，博士研究生.研究方向：空间目标光电探测.Email：tangrf@ynao.ac.cn通讯作者：李语强，男，副研究员.研究方向：空间目标光电探测与定轨.Email：lyq@ynao.ac.cn

空间碎片绝大部分在地球低轨道(Low EarthOrbit，LEO)上，另外有相当一部分在地球同步轨道（Geostationary Earth Orbit，GEO)上②（如图2）。虽然地球同步轨道碎片的密度远小于低轨的密度，但地球同步轨道没有类似大气阻尼这样的碎片清除机制[3」，导致地球同步轨道的碎片在轨时间长，数目增长快，对人类航天活动具有潜在的危险。地球同步轨道是一种非常珍贵的资源，该区域的空间碎片引起了航天国家的高度关注。

![](images/303008926078d10da2ba7b045834311bf7b21a5bdc40eeb228853b6f5676861c.jpg)  
图2空间碎片密度分布示意图  
Fig.2Distribution of space debris density

（红色：直径大于 $1 \mathrm { m m }$ 的碎片；绿色：直径大于 $1 \mathrm { { c m } }$ 的碎片；蓝色：直径大于 $1 0 \ \mathrm { c m }$ 的碎片)

地球同步轨道高度为 $3 5 7 8 5 ~ \mathrm { k m }$ ，由于雷达的探测信号与 $r ^ { - 4 }$ 成正比[4]，地基雷达一般用于地球低轨道上空间目标的测量，很难实现对地球同步轨道空间碎片的探测。因此，从20 世纪90年代开始，世界上主要的航天大国先后将地面光学设备应用于地球同步轨道空间碎片的观测研究，地球同步轨道空间碎片的光学观测主要包括目标检测与识别、目标的精密定位与轨道确定以及目标的编目处理等。近年来，将空间目标视为非质点，通过测光观测以及多波段观测，研究空间目标的相关物理特性成为主要研究内容之一[5]。为了对目标成功进行测光，需要在望远镜导星镜视场内成功地搜索并捕获目标，因此高效的搜索策略非常重要。

# 1地球同步轨道空间碎片的轨道特征

理想的地球同步轨道是圆形的，具有轨道倾角 $i = { 0 } ^ { \circ }$ ，轨道平运动周期为1d等特征，这样的轨道也称为静止轨道。地球同步轨道高度为 $3 5 7 8 5 ~ \mathrm { k m }$ ，理论半长径为 $4 2 ~ 1 6 4 ~ \mathrm { k m }$ 。事实上，由于多种摄动因素的影响，地球同步轨道上的空间碎片存在东西向和南北向的漂移。地球同步轨道的主要摄动因素为地球的非球形引力摄动、太阳和月亮的引力摄动以及太阳的辐射压力摄动[6]。太阳、月亮的引力摄动造成地球同步轨道目标的轨道角动量有 $5 3 \mathrm { ~ a ~ }$ 左右周期的进动，进动导致轨道倾角存在幅度约为 $1 5 ^ { \circ }$ 的周期变化[7]，如图3。地球同步轨道倾角在26.5a后会由 ${ 0 } ^ { \circ }$ 增加到 $1 5 ^ { \circ }$ ，再过26.5a减小为$0 ^ { \circ }$ 。太阳辐射压力导致一个小的偏心率，从而引起径向半径的变化，在极端情况下，这个变化可以达到 $\pm 7 5 \mathrm { k m }$ 。因此，定义地球同步轨道环带为一个半径为 $4 2 ~ 1 6 4 ~ \mathrm { k m }$ 、厚度为 $1 5 0 \mathrm { k m }$ 、纬度 $\pm 1 5 ^ { \circ }$ 的区域[7]（如图4)。

# 2搜索策略分析与计算结果

对于地球同步轨道上的空间碎片，即使以理想的静止轨道为对象，地球同步轨道环带区域里的空间碎片实际上相对地面测站是运动的。一般的空间碎片观测，每个目标均有对应的轨道根数形式的轨

道预报数据。设备根据轨道预报数据以及观测站的位置，生成实时和望远镜匹配的引导数据，引导望远镜指向预报位置，当望远镜到达预报位置后，由于导星镜视场比较大，在视场内能看见许多星，这时只要空间目标是可见的，一般可以依靠观测人员的经验对目标进行人眼识别，或者有一些识别算法[8]。因为在使用预报数据对目标进行跟踪时，目标在视场内相对静止，而其他星是运动的，以此可以对目标进行判断，随后选定目标，对其捕获跟踪[9（即凝视目标），在测光视场内对其进行光度测量等更细致的观测。但是当目标非常暗弱时，在导星镜视场内无法直接看到目标，此时就无法选定目标并进行跟踪以及更细致的光度测量。地球同步轨道空间碎片往往属于十分暗弱的对象，尤其尺寸相对较小的空间碎片，这时难以直接从导星镜视场里找到目标，所以需要对导星镜视场进行搜索。

由于预报误差，目标可能在偏离视场中心的任何一个位置。若假设预报数据的方位角精度（标准偏差）为 $\sigma _ { - } A$ ，高度角精度为 $\boldsymbol { \sigma } _ { - } \boldsymbol { E }$ ，并假设预报数据与目标真实位置的误差大小服从高斯分布。从而真实目标偏离预报位置的距离值也为高斯分布。为了更加直观地分析搜索过程，将预报误差角度转换到目标所在位置的距离值（同样将其他角度值转换为距离值）：

$$
\sigma _ { 1 } = R \sigma _ { - } ~ A ; ~ \sigma _ { 2 } = R \sigma _ { - } E ,
$$

其中， $R$ 为目标与测站的距离值； $\sigma _ { 1 } , \sigma _ { 2 }$ 分别为两个方向上偏离距离的精度经过上式转化，相当于以预报位置为中心，目标真实位置离中心位置的距离，也服从高斯分布。

![](images/bd0068e945dc896220eb57ef4d1e060036bab9ead0a1d254d483b932d802b9e9.jpg)  
图3地球同步轨道目标轨道倾角(i)与升交点赤经(RAAN)的分布关系

![](images/c831d96b56c77608c0767d02b2dfcb21305432d0d9f373fb99350b30f50e2674.jpg)  
Fig.3Distributional relationship between orbital inclination （i）of geosynchronous targets and RAAN   
图4地球同步轨道环带区域 Fig.4Geosynchronous orbital belt

以预报位置为中心原点，忽略径向(即目标距离)误差，建立一个目标真实位置偏离值的二维高斯分布[10]：

$$
p ( x , \ \gamma ) = { \frac { 1 } { 2 \pi \sigma _ { 1 } \sigma _ { 2 } { \sqrt { 1 - \rho ^ { 2 } } } } } \exp \left\{ - { \frac { 1 } { 2 ( 1 - \rho ^ { 2 } ) } } \times \left[ { \frac { ( x - \mu _ { 1 } ) ^ { 2 } } { \sigma _ { 1 } ^ { 2 } } } - 2 \rho { \frac { ( x - \mu _ { 1 } ) \ ( \gamma - \mu _ { 2 } ) } { \sigma _ { 1 } \sigma _ { 2 } } } + { \frac { ( \gamma - \mu _ { 2 } ) ^ { 2 } } { \sigma _ { 2 } ^ { 2 } } } \right] \right\} ,
$$

其中，原点为预报位置； $( x , y )$ 为目标的真实位置； $p ( x , y )$ 为目标在该位置出现的概率； $\sigma _ { 1 } , \sigma _ { 2 }$ 为两个标准差； $\smash { \mu _ { 1 } , \mu _ { 2 } }$ 为两个均值; $\rho$ 为两个随机变量之间的相关系数。现取原点(预报位置)为中心，$\smash { \mu _ { 1 } , \mu _ { 2 } }$ 则均为0，并假设两个方向上的预报误差相互独立，因此相关系数为0。而对于空间碎片，大部分目标尤其是地球同步轨道碎片，由于缺乏足够的观测数据，从而预报精度比较低，此时取$\sigma _ { 1 } = 3 0 0 0 \mathrm { m }$ ， $\sigma _ { 2 } = 3 0 0 0 \mathrm { m }$ ，计算目标真实位置在距离中心原点 $2 0 \mathrm { k m }$ 内出现的概率值如图5、6。

从图5、6可以看出，越靠近预报中心位置，目标出现的概率越高，越远离预报中心，目标出现的概率越低。而没有颜色的区域并不代表目标不会出现，只是选取了圆心为零点，以 $1 ~ \mathrm { k m }$ 为半径的区域进行了高斯分布概率计算(该区域全概率和非常接近1)，圆形以外区域没有计算，目标在此区域外出现的概率非常低。

![](images/7da0316e5eca242ab419e55cd69768ce202dd64394c501723dabc1fdbb2afc78.jpg)  
图5目标位置概率分布(三维图)

![](images/d2b6b3c6296998218889988e382e5439e507afc4626bb25eaac5238cf99fd8b2.jpg)  
图6目标位置概率分布(二维图)Fig.6Target position probability distribution（2-D)

在确定目标的位置范围以及分布概率后，为了成功地搜索到目标，需要在该范围内对目标进行搜索，一般采取的搜索方案主要是同心圆搜索(如图7)和爬楼梯搜索(如图8）。

![](images/9247fc4200ffc596cf178bf6e5c9bd168ee1200100df85e180279fcace98025c.jpg)  
Fig.5Target position probability distribution(3-D)   
Fig.7Searching as concentric circles

![](images/8041852faaf0c76e11a654b663226706015b58a375d69189ead7f588f3abe0e1.jpg)  
图7同心圆搜索  
图8爬楼梯搜索 Fig.8Searching as “climbing up'

在搜索过程中，考虑使用测光小视场在图6的范围区域内进行搜索，考虑测光视场的大小，并且通过(1)式的计算，取值视场的覆盖范围是半径为 $1 0 0 0 \mathrm { m }$ 的区域。从而为了找到目标，需要用该较小的视场对目标区域范围进行细致的搜索，在搜索的同时适当加长曝光时间。

图7即是同心圆搜索，该方案从搜索区域中心位置开始，以同心圆的轨迹一次次向区域边缘搜索，图中每一个点代表一次搜索，一个点即是该次搜索的圆心位置，覆盖半径为 $\mathrm { ~ 1 ~ 0 0 0 ~ m ~ }$ ，图中红线代表搜索轨迹，顺序是逆时针方向。在计算过程中，已经保证在每次搜索区域不重叠。对于第 $n$ 次搜索，搜索覆盖范围可以表示为

$$
( x - x _ { n } ) ^ { 2 } + ( y - y _ { n } ) ^ { 2 } \leqslant R ^ { 2 } ,
$$

其中， $( x _ { n } , y _ { n } )$ 为该次搜索的圆心坐标； $R$ 为搜索半径(取值 $1 0 0 0 \mathrm { m }$ ）。

搜索成功的概率 $P$ 就是该圆形区域覆盖真实目标的概率，结合图5可知，通过在圆形区域上对(2)式表示的 $p ( x , y )$ 进行曲面积分，得到该次搜索覆盖目标的概率值：

$$
P = \oiint _ { P } \left( x , \ y \right) \mathrm { d } x \mathrm { d } y \ ,
$$

积分区域： $( x - x _ { n } ) ^ { 2 } + ( y - y _ { n } ) ^ { 2 } \leqslant R ^ { 2 } .$

对于图7中的搜索，从圆心开始，沿着红线，以逆时针方向进行同心圆搜索，对每次搜索进行积分计算，得到单步搜索成功的概率值，可以得到如图9的结果。从图9可以看到，每步的搜索概率呈阶梯状递减，这是因为圆心在同一圈上的搜索区域对应的概率是一样的，随着同心圆搜索的进行，同心圆半径增大，处在同一圆上的搜索区域的概率降低。在图9中，大约在第100步搜索时，单步搜索概率就非常接近0，后面的搜索概率都非常低，第100步的位置距离中心原点 $1 2 0 0 0 \mathrm { ~ m ~ }$ ，即说明 $1 2 0 0 0 \mathrm { ~ m ~ }$ 半径范围以外的概率已经非常低。将每单次搜索成功的概率累积，就可以得到图10中虚线代表的累积搜索成功概率，虚线表示随着搜索步数的增加，成功搜索到目标的概率也在增加。结合图9与图10可以看出，大约在第100 步搜索后，单步搜索概率非常接近于0，累积概率增幅几乎可以忽略。

![](images/beeff7ba6c58679f0a5953feb720aa998d3c570b773b0af0a395d8ac9fc03704.jpg)  
图9每步搜索成功的概率

![](images/0a834b9e45d85e82004ff7e675ec81f0e60d377ecb1cc4f1dc9fadeeeea2d27d.jpg)  
图10累积搜索成功的概率  
Fig.10Sum of successful search probability

爬楼梯搜索如图8，以红色圆圈标出起始点，红色线代表搜索路径，蓝色点代表搜索区域，同前面一样，图中每个点是一个圆心位置，代表一个半径为 $1 0 0 0 \mathrm { m }$ 的圆形区域。以同样的方式，在每个点代表的搜索区域进行积分运算，按顺序计算每个搜索区域的成功概率如图11。

图11每次搜索成功的概率随着搜索步数变化，结合图8中的搜索路径可知，搜索区域与中心原点的距离值从小到大反复变化，从而造成了图11中概率值的变化。同样，将每步的搜索概率一步步累积，从而得到图10中的红色实线，该线表示随着搜索步数的增加，成功搜索到目标的概率也在增加。

从图10可以看出，两种方案虽然搜索了同样的步数，但两方案的累积搜索概率差别较大，两种方案同样一共搜索了271步。蓝色虚线表示的

![](images/e451d8630344310f3b0ed0c71498f0e6ff7441f046ffc62cec7848b14d20a67f.jpg)  
Fig.9Successful search probability of each step   
图11每步搜索成功概率 Fig.11Successful search probability of each step

同心圆方案在大部分搜索步数时保持着更高的搜索成功概率，并且此方法可以很快达到概率峰值，也就是搜索效率比较高，该方案在第94 步累积概率值为0.7340，随后在129 步达到概率峰值0.7348。

爬楼梯搜索方案初始的步数概率很低，随后很快升高，最终在第178步，爬楼梯搜索成功概率刚好等于同心圆搜索概率(0.7348），随后该方法在第219步累积概率达到0.7844，最终爬楼梯方法在第 250步达到概率峰值0.7854。

由以上分析可知，同心圆搜索方法搜索效率更高，可以在较少的步数之内达到较高的搜索成功概率。

# 3结论与展望

不考虑预报精度在方位角与高度角差异的情况下，采取同心圆搜索方案比较高效，由文中的计算可知，该方案在第94步达到较高的累积概率，而往后的搜索步数效率非常低，可以考虑开始新的一轮搜素。实际搜索中，在大致知道预报误差的情况下，可以根据文中方法估算最适合搜索的区域，从而提高搜索效率。而当预报误差精度不一致时，通过合理地选取起始搜索点，应该可以提高爬楼梯搜索的效率，甚至可以使得此方法更加优秀。

# 参考文献：

[1] 吴连大.人造卫星与空间碎片的轨道和探测［M].北京：中国科学技术出版社，2011.  
[2] 林来兴.空间碎片现状与清理［J].航天器工程，2012，21(3)：1-10.Lin Laixing. Status and removal of space debris [J]. Spacecraft Engineering,2012,21(3）: 1-10.  
[3] 李铸洋，张超，梅雨庭，等.GEO空间碎片轨道变化分析［J].北京测绘，2013(6)： $4 \substack { - 6 + 1 0 }$ ：Li Zhuyang，Zhang Chao，Mei Yuting，et al. Analysis on evolution of GEO space debris[J].Beijing Surveying and Mapping，2013(6) : $4 { - } 6 { + } 1 0$ ，  
[4] 叶叔华，黄城．天文地球动力学［M].济南：山东科学技术出版社，2000.  
[5] 庄诚，隋成华，唐轶峻.GEO空间碎片光度测量标定方法的研究［J]．天文研究与技术—国家天文台台刊，2011，8(4)：343-346.Zhuang Cheng，Sui Chenghua，Tang Yijun. Research of photometric calibration of Geosynchronous-Orbit（GEO） space debris ［J].Astronomical Research & Technology——Publications of NationalAstronomical Observatories of China，2011，8(4）：343-346.  
[6] 李恒年.地球静止卫星轨道与共位控制技术［M].北京：国防工业出版社，2010.  
[7] Schildknecht T. Optical surveys for space debris [J]. The Astronomy and Astrophysics Review,2007，14(1) : 41-111.  
[8] 孙荣煜.空间碎片光学观测中若干问题研究［D].北京：中国科学院大学，2015.  
[9] 卢晓猛.基于天文观测方法的空间碎片数据获取与分析系统［D].北京：中国科学院大学,2013.  
[10] 李贤平.概率论基础［M].北京：高等教育出版社，2010.

# The Strategic Analysis for Searching Faint Space Debris in the GEO Region

Tang Rufeng1,2²,Li Yuqiang'，Li Rongwang' (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 65oo11,China，Email：tangrf@ynao.ac.cn； 2.University of Chinese Academy of Sciences，Beijing1OoO49，China)

Abstract: The geosynchronous region is one of the most valuable space environment for application which makes itof great significance to monitor the space debris by optical observation.On the basis of the special dynamical characteristics of geosynchronous orbits，the motion features of GEO space debris were introduced in this paper.Concerning the prediction error of the space target and size of field of view，the success probabilities of“concentric circles search”and“climb stairs search”were calculated.Based on the calculated results，the strengths and weakneses of each search strategy were analyzed. According to the analysis，the “ concentric circles search” is more efficient in most cases.

Key words: GEO space debris； Optical observation；Search strategy； Search probability