# 基于日心坐标系的PDQG-R剖分模型及编码研究

胡雅斯 时蓬段然(中国科学院国家空间科学中心北京 100190)

摘要随着空间数据的海量增长，为了提高数据存取效率和数据可视化效率，需要对数据进行有效的组织和管理.基于现有的二维表面剖分模型，针对过太阳质心的黄道面和子午面，提出一种新的 PDQG-R 格网模型—平面退化四叉树格网，并给出了相应的网格编码方案．以太阳风模型数据为例，给出了具体的组织实例并验证，结果表明该剖分模型不仅解决了日心附近网格过密问题，还可以满足径向分辨率与经(纬）向分辨率不同步的需求，同时还能提供多分辨率层次的数据，有效地支持海量空间数据的组织管理.

关键词 空间剖分,PDQG-R,多分辨率 中图分类号P353,TP391.9

# PDQG-R Subdivision Mode and Encoding in Heliocentric Coordinate System

HU Yasi SHI Peng DUAN Ran (National Space Science Center,Chinese Academy ofSciences,Beijing 100190)

Abstract With the quick increase of space data, in order to meet the higher demand of data visualization and data access eficiency, reasonable data organization and management is needed. Based on the existing 2D subdivision models,for the ecliptic plane and meridian plane which are over the Sun centroid,a new model,PDQG-R (Plane Degradation Quad-Tree Grid), is put forward. Encoding scheme of grids is also given. Taken solar wind data as an example,the model not only resolves the problem that grids near to heliocentric are too dense,but also meets the requirement that resolution in radius is not equal to that in longitude and latitude.Besides,it provides hierarchical multi-resolution data, and can support the organization and management of massve space data effectively.

Key wordsSpace subdivision,PDQG-R,Multi-resolution

# 0 引言

近些年，中国陆续开展了针对太阳、地球、月球的空间探测项目，例如夸父计划、地球空间双星探测计划、高分辨率对地观测系统工程、探月工程等.这些探测项目已经获取或者即将获取到大量空间科学探测数据，如磁层、辐射带和电离层数据等.在科学研究中，除了探测数据，还有一些供科学研究的模型输出数据,例如太阳风数据等.一方面，空间信息量的海量增长并不意味着有效的空间信息必然增长，而无序的空间信息资源甚至可能加剧信息增长与有效应用之间的矛盾.另一方面，如何从当前海量纷繁复杂的数据中找到所需要的数据，是在科学研究中需要首先解决的问题[1].

地理信息系统的发展，特别是数字地球技术的发展，使地球科学研究有了强有力的数据组织和管理手段.面对快速发展的空间科学，如何将空间中海量数据统一组织管理，如何提高数据存取效率和可视化效率，成为当前迫切需要解决的问题之一，具有重要理论研究意义和广泛的应用前景[2-6].

在日地空间，为了研究不同类型的空间数据随着距日心的距离远近的变化，需要对过太阳质心的两种典型切平面(即黄道面、子午面）构建平面网格剖分模型，并且对网格进行编码，利用多细节层次（LODLevelsofdetail)技术，将数据划分成不同的分辨率层次，从而实现巨大圆形平面的数据组织，提高海量数据的存取效率[1].进而为空间数据的组织、管理、分析提供技术支撑[7-13].

点，用经纬格网法会导致距离日心近的地方网格过于密集，距离日心远的地方网格稀疏，当剖分层次增加时，远近格网的大小比例呈不收敛趋势[8]．为了使格网模型有更高的适应性和可扩展性，本文引入退化四叉树思想[25-26],与普通经纬格网结合，取二者之长，形成平面退化四叉树格网模型(PlaneDegenerat-ed Quadtree Grid, PDQG).

对于黄道面和子午面，两个方向上的度量单位不同，一个是距离，一个是角度，由于两种平面都是角度与半径的组合，实质上是一样的.下面以太阳黄道面为例,介绍PDQG格网的剖分方法,拟采用的剖分方法步骤如下.

步骤1将黄道面1分为4,每部分是经度范围是 $0 ^ { \circ } \sim 9 0 ^ { \circ }$ 且半径范围约为1AU (日地平均距离)的 $1 / 4$ 圆面.

步骤2用PDQG格网对每个4分圆面进行递归细分,第1次剖分，即取4分圆面上的3条边的中点,得到3个新点，将4分圆两腰上的2个新点连成一条纬线,再将该纬线的中点与另一新点连成一条径线,形成1个新的子4分圆 (可近似认为是三角形)和2个子四边形，如图1所示．图中实线代表的是第1次剖分结果.

步骤3第2次剖分，是对第1次产生的两种类型子网格的递归细分.对子三角形按第一次剖分的方法进行剖分即可；而对于子四边形剖分，可用普通的四叉树法,取4条边的中点，得到4个新点，将两腰上的中点与圆心用同心圆弧线连接，将两纬线的中点直接连直线，则又得到4个新的子四边形，这样就产生了1个新子三角形和10 (即 $2 + 4 + 4 )$ 个四边形，

# 1剖分模型构建

目前，有三种典型的二维空间剖分模型，分别是经纬度剖分模型[14-16]、正多面体剖分模型[17-19]和Voronoi球面自适应格网模型[20-24].

应用于二维平面的空间物理数据的剖分中，可以排除多面体剖分模型和自适应格网模型.多面体模型的坐标计算相对比较复杂，组织形式与现有的测绘、遥感数据不同，集成起来比较困难[14,18]．自适应剖分模型是单一比例尺的剖分，与多分辨率结合比较困难[21-22,24].

# 1.1 PDQG-R 剖分模型

由于经纬度剖分模型在两极上有变形严重的缺

![](images/f661815fa349ab59e16e822c737ba49aecfea007c5c0477ca501158139fb6158.jpg)  
图14分圆面的 PDQG3次递归剖分 Fig.1Three recursive subdivision of quadrant with PDQG

实现对4分圆面更高分辨率的细分.图1中的点划线代表的是第2次剖分结果

步骤4重复步骤3,直到分辨率满足要求.图1中的虚线代表的是第3次剖分的结果

通过对5次剖分后的网格数量进行统计，对比情况见表1．可归纳为，当剖分层次为 $\boldsymbol { n }$ 时， $1 / 4$ 圆面剖分生成的格网个数即为 $N$ ，满足公式

$$
\begin{array} { c } { N = \left\{ \begin{array} { c } { 1 + 2 ^ { 1 } = 3 , ~ n = 1 ; } \\ { 1 + 2 ^ { 1 } + 2 \times 4 ^ { 1 } + \dots + 2 \times 4 ^ { n - 1 } + } \\ { 2 \times 4 ^ { n } , ~ n > 1 . } \end{array} \right. } \end{array}
$$

即 $N = 1 + 2 ^ { 1 } + \cdot \cdot \cdot + 2 ^ { 2 n - 1 }$ ， $n \geqslant 1$ ,进一步有

$$
N = 1 + \frac { 2 } { 3 } ( 4 ^ { n } - 1 ) , \quad n \geqslant 1 .
$$

普通经纬模型的格网个数为 $N = 4 ^ { n } \ ( n > 0 )$ ，可以计算出PDQG 格网数压缩极限为 $1 / 3$

当用传统经纬格网剖分时，格网数量以 $2 ^ { 2 }$ 速度增长．经过退化之后,PDQG网格数量明显减少，这样既节省了大量的数据存储空间，节省了格网编码也有效地改善了日心处格网过密的缺点，使得格网大小趋于均匀化.

当径向分辨率大于经向分辨率时，PDQG 格网已不能满足需求，为了最大程度保留径向数据的完整性,解决二维度分辨率不一致的问题，可以在PDQG格网的基础上继续在径向独立细分，使得径向的剖分次数大于经向的剖分次数，以满足径向分辨率大于经向分辨率需求.因此，提出径向细分的平面退化四叉树格网 (Plane Degenerated Quadtree Grid-Radius,PDQG-R).

假设径向分辨率是经向的 $2 ^ { 3 }$ 倍,则在PDQG 格 网的基础上继续在径向进行3次细分即可达到分辨

率要求，如图2所示

图2是在3次剖分后的PDQG 格网基础上对某一个PDQG 网格在径向3次细分的示意.图中实线是径向第1次细分，点划线是径向第2次细分，虚线是径向第3 次细分.由此，一个PDQG 网格就变成了8 个子网格,于是生成了PDQG-R 格网.

每一个 PDQG-R 格网都是在对应剖分层次的 PDQG 格网基础上生成的，其中，径向细分的次数应根据实际需求进行相应调整，特别地，当径向细分次数为0时，即是PDQG格网.

# 1.2 PDQG-R格网编码

编码是将每个剖分后的子网格赋予唯一的标识，使网格中的坐标、属性数据和编码形成一一对应的关联关系．为了进行高效的数据索引,PDQG-R 格网的具体编码[15,27-28]规则如下.

(1）首先将1分为4的黄道面按照逆时针编号0, 1,2,3,依次确定了每个4分圆面所在的象限，如图3 所示.

(2)第1次剖分后，对于每一个4分圆面，外侧2个四边形按照逆时针依次编码为2，3，中心三角形编码为0，可以认为是0,1合并形成0,如图4(a)

![](images/4aa8460f479fd80c29c7630a212b9bd1316ffb12d42f4fbee95de5a773379bd4.jpg)  
图2网格径向细分3次示意  
Fig.2Diagram for 3 subdivision of PDQG in radius

表14分圆面剖分后格网数的比较  
Table 1 Comparison for grids’number of quadrant after subdivision   

<html><body><table><tr><td>剖分层次</td><td>经纬模型格网数</td><td>PDQG格网数</td><td>格网数降低比例/(%)</td></tr><tr><td>1</td><td>2²=4</td><td>1+2=3</td><td>25</td></tr><tr><td>2</td><td>24 = 16</td><td>1+2+2×4=11</td><td>31.3</td></tr><tr><td>3</td><td>2 = 64</td><td>1+2+2×4+2×4×4=43</td><td>32.8</td></tr><tr><td>4</td><td>28= 256</td><td>1+2+2×4+2×4×4+2×4×4×4=171</td><td>33.2</td></tr><tr><td>5</td><td>210 = 1024</td><td>1+2+2×4+2×4×4+2×4×4×4+2×4×4×4×4=683</td><td>33.3</td></tr></table></body></html>

(3)第2次剖分后，中心三角形编码与第1次剖分单元的编码方法相同，子四边形编码左下、左上分别为0,1,右下、右上分别为2,3,如图4(b),依此类推.并且，剖分层次每增加1层,编码相应增加1位.

(4)在径向上，每个PDQG 格网都要经过径向3次剖分，1分为8,则任意一个格网可以在其本身编码后加上附加码,用来标识经过径向细分后格网具体位置,如图2中编号为010 的格网是经过PDQG-R 剖分后生成的8个子网格之一．可以在本身编码后用分割线分开，后面的位数标识半径细分位，用二进制码表示，1位代表细分1次，2位代表细分2次，并且每经过一次细分，编码增加一位，剖分的次数越多，所得子网格越小．从圆心往外的编号依次用0，1表示，第1次细分用0,1标识，第2次细分，依次用00，01，10，11表示，第3次细分依次用000，001，010,011，100，101，110，111表示．可以根据编码位数确定径向细分的次数，并且编码是动态的，不但具有遗传性，且能与多分辨率层次很好地结合起来

![](images/34331244ce74ed9d75d0486674de3fd4894f85ebea3d7bcd22a5e4deb15727a9.jpg)  
图3黄道面4分圆面编码 Fig.3Encoding of ecliptic plane

![](images/c04a142e510f253802b6b42d367907e181b97b9e66f64651dd246125eb0e8426.jpg)  
图4PDQG 格网编码.(a)1层PDQG 格网编码,(b)2层PDQG 格网编码  
Fig.4Encoding of PDQG grid.(a) Encoding of 1st PDQG grid, (b) encoding of 2nd PDQG grid

(5)分割线后面的位数标识半径细分位，是二进制码,其余Morton码的每位数字都是不大于3的4进制数，相应的Morton码位数越长，可表示为

$$
\mathrm { M o r t o n } = q _ { 1 } q _ { 2 } \cdot \cdot \cdot q _ { n } q _ { n + 1 } { \stackrel { \_ p } { \_ } } p .
$$

式中， $q _ { 1 }$ 为四分体象限标识位，“—”为分隔符， $p$ 为 PDQG 格网基础上在径向 3次细分后的径向区分标识位.

通过网格编码，网格中的数据与编码对应起来为数据检索、数据组织，后面的数据应用以及数据分析都提供了支持

# 2数据组织实例

下面以太阳风粒子密度数据为例，阐述如何使用 PDQG-R 模型对空间数据进行组织和管理．该数据是由三维太阳风模型 (空间天气学国家重点实验室 SIGMA 研究小组开发的太阳行星际守恒元解元（SIP-CESE）三维太阳风模型）输出的数据[2,29-31].

通过对该太阳风数据的组织，通过可视化展示有助于分析该太阳风模型是否满足预期，为科学研究提供技术支撑

# 2.1 数据分析

所用数据是在极坐标下采样的，3个坐标轴分别是半径、经度、纬度．此太阳风数据具有不规则采样特性，在以太阳为中心的球体采样空间中，纬度范围 $- 9 0 ^ { \circ } { \sim } 9 0 ^ { \circ }$ ，采样55次，经度范围 $0 ^ { \circ } \sim 3 6 0 ^ { \circ }$ ，采样80次，径向采样范围约1AU，采样154次.采样间隔如图5所示.

从图5(a）(b）可以看出，经度间隔集中在 $4 . 5 ^ { \circ }$ 浮动范围很小，可以认为在经度上是等间隔采样的纬度上的间隔是非均匀的，低纬上间隔大，高纬上间隔小，赤道上间隔最小．从半径间隔分布可以看出，离太阳越远，半径间隔越远，且呈线性趋势增长，增长斜率约为 $2 . 8 6 \%$ ，在径向的采样次数远多于经向和纬向上的次数.

根据上述分析可以看出，太阳风数据在经向和纬向的采样次数接近，即经向和纬向分辨率基本同步，而径向采样次数明显较大，这种采样使得太阳风数据在径向分辨率高于经向 (纬向)分辨率，即径向分辨率与经向 (纬向)分辨率不同步时,可用 PDQG-R 格网模型进行数据剖分.

![](images/344bf1b07a189d576e7eb7cae318f73414435ba55d8c7c8e769a08c40a3a49cd.jpg)  
图5采样点经度(a)、纬度(b)和半径(c)间隔分布 Fig.5Longitude (a),latitude (b) and radius (c) interval distributions of sampling data

由于4分圆面数据维度近似是 $2 ^ { 5 } \times 2 ^ { 8 }$ ，即径向采样密度是经向的 $2 ^ { 3 }$ 倍,可采用PDQG-R 格网对该数据进行剖分，在PDQG 格网的基础上继续在径向进行3次细分即可满足分辨率要求.

# 2.2 可视化显示

在日心黄道坐标系下，以太阳风粒子密度数据为例，给出数据可视化实例如下.

图6为原始太阳风绝对密度数据，图7是剖分后的太阳风绝对密度数据，其中LOD代表剖分层次，图7(a)和(b)分别对应LOD为4和5，可以看出原

![](images/3d48fdaa6be7398cf2dc23b08f555e671aea33fdfa5affc668cab3e77006abaa.jpg)  
图6原始太阳风绝对密度数据 (黄道面) Fig.6Original solar wind density data (ecliptic)

![](images/521a0f309b3d17317466878dcd121973e8dd3b1f1d3cb07667c0613669e381ae.jpg)  
图7剖分后太阳风绝对密度数据 (黄道面) Fig.7Solar wind density data after subdivision (ecliptic)

始数据在中心密集，外围稀疏；剖分后整体数据变得均匀，且能完整地表达太阳风的整体特性

由表2可以看出，PDQG-R格网以较少的网格数最完整表达数据的整体特性，数据可用性最高，

# 2.3 数据检索

如果需要获取基于某个特征或者基于某个区域的所有数据，必须浏览所有文件从中提取对应数据这种检索数据的方式费时费力而且很容易遗漏，通过对每个网格进行编码,将网格、属性数据、坐标、时间等信息统一组织起来，可以快速定位所需要的信息.下面以图8编码为32的网格为例，对比普通检索和基于格网编码检索的效率

假设所需要的数据在网格32中，如果用普通的按顺序检索方法查找该数据，则需从文件开始查找，查找次数就是数据所在的行数，数据越靠后，查找次数越大.假设有12320行数据，该数据在12000行则需要查找12000 次；而基于PDQG-R 格网则可以根据多分辨率的网格一层层的定位该数据，首先按顺序查找3次，定位在网格3，然后在网格3中查找3次，定位在网格32，然后在网格32中定位相应的 PDQG-R 网格，然后再按顺序检索，查找次数大幅度减少，检索效率明显提高．也就是说，在传统的查找中，基于数据逐行查找，而基于该数据组织方法则将数据分区、分块网格化，层层递进快速定位，只查找其所在分区,其他分区不进行查找

![](images/4d8f905a958a749678482d8a0efe5b28c1cfcb94846f956dc58647a424b33202.jpg)  
图8基于格网编码的检索示意 (2层PDQG 格网编码) Fig.8Diagram for search based on grid encoding (encoding of 2nd PDQG grid)

通过剖分和编码将海量数据有效组织起来，第一，可以提供多分辨率层次的数据，提高数据检索效率；第二，可以将空间位置与属性数据关联起来；第三，可以有效地减少冗余数据量，提高数据的可用性

# 3结论

在球面剖分上，由于普通经纬格网在两极上经纬线密集,使得两极与赤经上划分的格网大小比例不收敛，从而导致格网绘制效果变形严重.若将其应用到黄道面剖分中，会使日心与外围的网格大小比例过大，为解决此问题，本文引入退化四叉树剖分思想！针对黄道面和子午面两种典型平面，提出了一种新的PDQG-R 格网模型,并针对该格网模型提出相应的编码方案

经试验证明，PDQG-R格网模型不仅能够很好地解决太阳质心附近格网过密的问题,还可以满足径向分辨率与经 (纬)向分辨率同步和不同步两种需求.同时，能提供多种分辨率层次的数据，有效地提高数据检索效率，适用于不规则采样数据的剖分.但是，该模型在径向是等间隔的，如果能够实现径向非等间隔递归剖分，将会更加符合太阳风数据特征

表2剖分后网格个数对比表  
Table 2 Comparison for grids’number after subdivision   

<html><body><table><tr><td>剖分 层次</td><td>原始 数据数</td><td>经纬模型 格网数</td><td>PDQG 格网数</td><td>PDQG-R 格网数</td><td>PDQG-R格网实际 有数据的网格数</td></tr><tr><td>1</td><td>12 320</td><td>16</td><td>12</td><td>96</td><td>96</td></tr><tr><td>2</td><td>12 320</td><td>64</td><td>44</td><td>352</td><td>352</td></tr><tr><td>3</td><td>12 320</td><td>256</td><td>172</td><td>1376</td><td>1120</td></tr><tr><td>4</td><td>12 320</td><td>1024</td><td>684</td><td>5472</td><td>2624</td></tr><tr><td>5</td><td>12 320</td><td>4096</td><td>2732</td><td>21856</td><td>4540</td></tr></table></body></html>

该模型不局限于太阳风数据的剖分，理论上在类似采样空间的数据都可以适用.在剖分的网格中放置不同的数据，即可实现多种空间物理数据的组织管理,在大量空间物理数据组织中，有很好的应用前景

# 参考文献

[1] Hu Y,Meng X, Pan Z. Organization method for solar wind data with LOD technology[J].J. Conv. Inf. Tech., 2013, 8(2):323-329   
[2] Feng Xueshang,Xiang Changqing, Zhong Dingkun. Numerical study of interplanetary solar storms[J].Sci.Sin. Terr.,2013,43(6):912-933.In Chinese (冯学尚,向长青,钟 鼎坤．行星际太阳风暴的数值模拟研究[J]．中国科学：地球科 学,2013,43(6):912-933)   
[3] Wang Hechuang. Research on key technology of the solar wind system simulation [D]. Chengdu: Chengdu University of Technology，20l2.In Chinese（王合闯．太阳风系统仿 真与关键技术研究[D]．成都：成都理工大学,2012)   
[4] Yang Liping.3-dimensional Numerical Study on the Background Solar Wind [D].Beijing: Graduate University of Chinese Academy of Sciences,2O11.In Chinese(杨 利平．背景太阳风的三维数值模拟研究[D].北京：中国科学院 研究生院，2011)   
[5] Ye Zhanyin. Numerical Research about Coronal Mass Ejection [D].Beijing:Graduate University of Chinese Academy of Sciences，20o3．In Chinese（叶占银．日冕物 质抛射的数值研究[D].北京：中国科学院研究生院，2003)   
[6] Zhou Yufen． Three-dimensional Numerical Research of Coronal Mass Ejections [D].Beijing: Graduate University of Chinese Academy of Sciences,20o8.In Chinese （周玉 芬．日冕物质抛射的三维数值模拟研究[D].北京：中国科学院 研究生院，2008)   
[7] Luo H, Chen G X,Du A M.Multipoint observations of Pi2 pulsations and correlation with dynamic processes in the near-Earth magnetotail on March 18,2009[J].Sci. China: Earth Sci.,2014(2):359-371   
[8] Lee C O, Luhmann JG, Odstrcil D,et al. The solar wind at 1 AU during the declining phase of Solar Cycle 23: Comparison of 3D numerical model results with observations [J]. Solar Phys., 2009,254(1):155-183   
[9] Webb D F,Allen JH. Spacecraft and ground anomalies related to the October-November 2003 solar activity [J]. Space Weather, 2004,2(3),doi:10.1029/2004SW000075   
10] Feng Xueshang,Xiang Chagnqing, Zhong Dingkun,et al. Comparative study of Ulysses observation and MHD simulation of the solar wind 3D structure[J]. Chin.Sci. Bull., 2005，50(8):820-826．In Chinese (冯学尚，向长青，钟鼎坤, 等.三维太阳风结构的 Ulysses 观测和 MHD 模拟的比较研 究[J].科学通报,2005,50(8):820-826)   
[11] Xie Yanqiong. Comprehensive Studies on Solar Storm [D]. Beijing:Graduate University of Chinese Academy of Sciences，2007．In Chinese (解妍琼．太阳风暴的综合研究[D]. 北京：中国科学院研究生院，2007)   
[12] Shi Yong,Wei Fengsi，Feng Xueshang， et al.Threedimensional MHD simulation of the solar wind structure observed by Ulysses [J]. Chin. Sci. Bull, 2001(6):511-514. In Chinese (石勇，魏奉思,冯学尚,等.Ulysses 观测的太阳风 结构的三维 MHD 模拟[J].科学通报,2001(6):511-514)   
[13] Wang Chi. MHD simulation on the interaction of the solar wind with the magnetosphere[J]. Chin.J. Space Sci.,2011,31(4):413-428．In Chinese(王赤．太阳风-磁层 相互作用的磁流体力学数值模拟研究[J].空间科学学报，2011, 31(4):413-428)   
[14]Goodchild MF,Yang S.Ahierarchical spatial data structure for global geographic information systems [J]. Graph. Mod. Image Proc., 1992, 54(1):31-44   
[15] Cheng Chengqi. Preliminary studies on geospatial information code model based on global subdivision model[J]. Geogr.Geo-Inf.Sci.,2009,25(4):2-5.In Chinese(程承 旗．基于全球剖分模型的空间信息编码模型初探[J].地理与地 理信息科学,2009,25(4):2-5)   
[16] Li K,Li Q. Study on spatial information encoding based on latitude and longitude subdivision [J].J. Sichuan Norm.Univ.: Nat.Sci., 2010,33(5):694-695. In Chinese (李康荣,李奇．基于经纬度剖分的空间信息编码研究[J]. 四川师范大学学报：自然科学版，2010,33(5):694-695)   
[17] White D,Kimerling A，Sahr K. Comparing area and shape distortion on polyhedral based recursive partitions of sphere[J]. Geogr.Inf. Sci.,1998(12):805-827   
[18] White D, Kimerling A, Overton W. Cartographic and geometric components of a global sampling design for environmental monitoring[J]. Cartogr. Geogr. Inform. Syst., 1992,19(1):5-22   
[19] Sahr K,White D,Kimerling A.Geodesic discrete global grid systems[J]. Cartogr. Geogr. Inf. Sci., 2003, 30(2): 121-134   
[20] Gold C M. Review: Spatial tessellation-concepts and applications of Voronoi diagrams [J]. Intern.J. Geogr.Inf. Syst.,1994, 1(8):237-238   
[21] Ben Jin,Tong Xiaochong,Zhang Heng,et al.A spherical Voronoi algorithm based on hexagonal grid[J]. J.Geom. Sci.Tech.,2006,23(5):1-5.In Chinese (贲进,童晓冲，张 衡，等.基于六边形网格的球面 Voronoi 图生成算法[J]．测绘 科学技术学报,2006,23(5):1-5)   
[22] Han Yinghua,Li Guiqing,Peng Li,et al.Dual Voronoi clustering and remeshing[J].J.Comp.Aid. Des.Comp. Graph.,2009,21(11):1-2．In Chinese (韩英华,李桂清，彭 莉，等.对偶 Voronoi 聚类与重网格化[J].计算机辅助设计与 图形学学报,2009,21(11):1-2)   
[23] Tong Xiaochong. Expression of spherical entities and generation of Voronoi diagram based on truncated Icosahedron DGG[J].Geom.Inf.Sci.Wuhan Univ.,2006, 31(11)：1-2．In Chinese(童晓冲．基于二十面体剖分格网 的球面实体表达与Voronoi 图生成[J].武汉大学学报：信息科 学版,2006,31(11):1-2)   
[24]Zhao Xuesheng.Spherical Voronoi Data Model Based on QTM[M].Beijing:Surveying and Mapping Press,2004. In Chinese(赵学胜．基于QTM 的球面 Voronoi 数据模 型[M].北京：测绘出版社，2004)   
[25]Cui Majun,Zhao Xuesheng.Tessellation and distortion analysis based on spherical DQG[J].Geogr.Geo-Inf. Sci.，2007，23(6):23-25．In Chinese(崔马军，赵学胜．球 面退化四叉树格网的剖分及变形分析[J].地理与地理信息科学, 2007,23(6):23-25)   
[26]Yuan Wen,Zhuang Dafang.Some essential questions in remote sensing science and technology [J].J.Rem.Sens., 2009，13(1):104-111．In Chinese (袁文，庄大方．基于等 角比例投影的球面三角四叉树剖分模型[J]．遥感学报，2009, 13(1):104-111)   
[27] Tong Xiaochong. Expression of spherical entities and generation of Voronoi diagram based on truncated icosahe dron DGG[J].Geom.Inf.Sci.Wuhan Univ.，2007, 36(4):428-435.InChinese(童晓冲.全球多分辨率六边形网 格剖分及地址编码规则[J].测绘学报，2007，36(4):428-435)   
[28]Yu Jieqing,Wu Lixin.Geo-ontology logical structure and development technology for 3D geology modeling[J].Geogr．Geo-Inf.Sci.,2009,25(1):1-2.In Chinese (余接情, 吴立新.球体退化八叉树网格编码与解码研究[J].地理与地理 信息科学，2009,25(1):1-2)   
[29] Feng Xueshang,Xiang Changqing,Zhong Dingkun. The state-of-art of three-dimensional numerical study for corona-interplanetary process of solar storms[J].Sci.Sin. Terr.,2011,41(1):1-28．In Chinese(冯学尚，向长青，钟鼎 坤．太阳风暴的日冕行星际过程三维数值研究进展[J].中国科 学：地球科学，2011,41(1):1-28)   
[30] Xiang Changqing,Feng Xueshang,Fan Quanlin,et al. An observation-based model of solar wind background [J]. Chin．J. Space Sci.,2006,26(3):161-166.In Chinese(向 长青,冯学尚，范全林,等.一个基于观测的太阳风背景模型[J]. 空间科学学报，2006,26(3):161-166)   
[31] Xu Wenyao.Energy budget in the coupling process of the solar wind,magnetosphere and ionosphere[J].Chin.J. Space Sci.,2011,31(1):1-14.In Chinese (徐文耀.太阳风- 磁层-电离层耦合过程中的能量收支[J].空间科学学报，2011, 31(1):1-14)