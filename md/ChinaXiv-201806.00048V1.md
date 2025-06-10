# 新疆雪线场的建立及空间分布特征

张连成¹，胡列群²，李帅³，侯小刚，郑照军4（1．新疆维吾尔自治区气候中心,新疆 乌鲁木齐830002；2．新疆气象服务中心,新疆 乌鲁木齐830002；3．中国气象局乌鲁木齐沙漠研究所,新疆 乌鲁木齐830002；4．国家卫星气象中心,北京100081)

摘要：以新疆为研究区,利用2015年逐日积雪产品 MOD10A1/MYD10A1数据,通过积雪持续时间比率法提取研究区雪线,并运用克里金插值法建立新疆区域雪线场,在此基础上对研究区雪线空间分布特征进行研究。经分析得出：普通克里格插值法建立的新疆雪线场MAE(平均绝对误差)为 $4 . 4 9 \mathrm { ~ m ~ }$ ,RMSE（均方根误差）为 $4 8 . 9 3 \mathrm { ~ m ~ }$ ,其误差满足本研究的精度需求;从整个研究区分析,雪线高程呈现出北低南高,西高东低的布局,其值在 $3 \ 0 0 0 \sim 5 \ 6 0 0$ m,具有典型的经度地带性和纬度地带性的分布特点,同时雪线场南部分布密集北部稀疏;从局部区域分析,天山山区雪线高程南高北低、东高西低，昆仑山区中间高、两边低,阿尔泰山区西北向东南依次降低;各个区域雪线分布差异较大,其内部分布复杂,雪线高程高低交错。

关键词：雪线场；空间分布；积雪持续时间比率法；新疆

雪线作为冰雪的下界线，其高程值和高程等值线在空间上分布的变化，不仅反映了积雪区的变化特征[1-2],更反映了极地地区、高原及高山气候、环境的变化特征及其基本状态，同时也能够预测人类活动对高山环境自然资源的潜在影响[3-4) C

雪线高度场简称为雪线场，即为雪线高程的等值线，它反映了雪线在空间上的分布情况。前人对雪线场的建立大多集中在青藏高原区域，如王利平等[5]通过间接的手段得到羌塘高原雪线高度,运用克里金空间插值建立了羌塘高原雪线高度场，并对雪线场的分布特征进行了分析;邓育武等[6-8]通过中国冰川编目最新数据资料得到西藏南部、恒河-雅鲁藏布江以及青藏高原的雪线高度，并结合Kriging 插值和GIS技术，生成了一定间隔的西藏南部和青藏高原的雪线分布图，即雪线场，在此基础上得出西藏南部和青藏高原雪线场的分布规律;陈梦蝶[3]通过遥感手段，结合GIS技术建立了青藏高原雪线场。然而，新疆作为全国三大冰雪分布区之一，雪线的空间动态变化对当地的水资源管理、生态建设具有重要的意义。目前只有极少数学者对新疆局部区域的雪线进行了研究，而对整个新疆区域雪线场的建立和空间分布特征的研究较少。

本文以整个新疆为研究区，利用MODIS逐日积雪产品数据，通过积雪持续时间比率法提取2015 年研究区雪线，在此基础上运用克里金插值法建立新疆区域雪线场，同时对研究区雪线空间分布特征进行了分析。对当地的气候演变、水资源利用及灾害分析等领域的研究具有重要的意义。

# 1资料和方法

# 1.1 研究区域

新疆位于亚欧大陆中部( $^ { \prime } 7 3 ^ { \circ } 1 8 ^ { \prime } \sim 9 6 ^ { \circ } 6 9 ^ { \prime } \mathrm { E } , 3 3 ^ { \circ }$ 0$8 6 ^ { \prime } \sim 4 8 ^ { \circ } 5 0 ^ { \prime } \mathrm { N } )$ ,地处中国西北边陲，总面积为1.66$\times 1 0 ^ { 6 } ~ \mathrm { k m } ^ { 2 }$ ,占全国陆地总面积的 $1 / 6 ^ { [ 9 ] }$ 。地形地貌可以概括为“三山夹两盆”：北面是阿尔泰山，南面是昆仑山，天山横亘中部把新疆分为南北两部分，为南疆和北疆。气候上由于远离海洋，四周高山环抱，空气干燥，年平均降水量为 $1 5 0 ~ \mathrm { m m }$ 左右，但各地降水量相差很大。地表水资源量多年平均值为 $7 8 9 \times$ $1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ,仅占全国的 $3 \%$ ,全疆单位面积的产水量居全国倒数第 $3 ^ { [ 1 0 ] }$ ,这对于一个占全国国土面积1/6的省区来说,水资源短缺尤为严重["],然而新疆积雪资源可谓得天独厚，约占全国积雪水资源量的 $1 / \AA$

3[12-13],在干旱缺水的新疆地区,积雪水资源就是绿洲生命线。近年来随着气温的升高，该区域山区的冰雪储量开始减少,雪线高程愈发的不稳定（1] 。

# 1.2 研究资料

本文所使用的资料主要包括： $\textcircled{1}$ 从NASAEarthObserving SystemDataGateway数据中心定制覆盖新疆区域的（编号分别为： ${ } ~ \mathrm { h } 2 3 \mathrm { v } 0 4 , \mathrm { h } 2 3 \mathrm { v } 0 5 , \mathrm { h } 2 4 \mathrm { v } 0 4 .$ $\mathrm { h } 2 4 \mathrm { v } 0 5 \ \mathrm { , h } 2 5 \mathrm { v } 0 4 \ \mathrm { , h } 2 5 \mathrm { v } 0 5 ) 2 0 0 1 \mathrm { - } 2 0 1 5$ 年MODIS逐日积雪产品（MOD10A1、MYD10A1）； $\textcircled{2}$ 从网站“ht-tp://glovis.usgs.gov/”下载 2005、2010、2014、2015年6—8月份新疆区域无云的 $3 0 \mathrm { ~ m ~ }$ Landsat 数据; $\textcircled{3}$ 地震科学数据共享中心下载的分辨率为 $9 0 \mathrm { ~ m ~ }$ 的SRTMDEM数据。

# 1.3 研究方法

1.3.1统计学方法运用统计学方法统计研究区2001一2015年日积雪面积，确定出研究日期范围。为了尽量减少降雪过程对面积统计的影响，本文选用6—8月份相对稳定的冰雪消融期[9,14]，利用2001—2015年MODIS积雪产品数据，统计出研究区日积雪面积,得出每年积雪面积的最小日期，从而得出 $1 5 \mathrm { ~ a ~ }$ 内积雪面积最小的日期范围，此范围则被确定为研究日期。由于新疆区域地缘辽阔，为了更精确的通过积雪持续时间比率法提取新疆区域雪线，本文将研究区分为3个区域分别进行统计，即天山山区、阿尔泰山区和昆仑山区。

1.3.2积雪持续时间比率法本文利用积雪持续时间比率法提取研究区雪线高程，即利用MODIS逐日积雪产品，计算一个像素在研究日期内出现积雪的概率，提取不同概率上的雪线高程，并以 $3 0 \mathrm { ~ m ~ }$ Landsat数据为“真值"进行误差分析，在误差最小时将积雪出现概率作为雪线提取的阈值，通过此阈值提取雪线的方法即为积雪持续时间比率法。本研究以2005、2010 年和 2014年的 $3 0 \mathrm { ~ m ~ }$ Landsat数据为“真值”确定积雪持续时间比率法的阈值，以2015年的 $3 0 \mathrm { ~ m ~ }$ Landsat数据为“真值"对通过此方法提取的雪线进行精度检验，具体做法参照文献[15]。

1.3.3克里格插值法克里格法是建立在地质统计学基础上的一种插值方法，它不仅具有预测表面的功能，而且能够对预测的确定性或准确性提供某种度量[16-17]。该插值法是区域化变量的线性估计，它假设数据变化成正态分布，认为区域化变量 $( Z )$ 的期望值是未知的。插值过程类似于加权滑动平均,权重值的确定来自于空间数据分析[18]

本文运用普通克里格插值法建立新疆区域雪线场,其公式为：

$$
Z ( X _ { 0 } ) ~ = ~ \sum _ { i = 1 } ^ { n } K _ { i } Z ( X _ { i } )
$$

式中： $Z ( X _ { i } ) ( i = 1 , 2 ^ { . . . { n } } )$ 为 $n$ 个样本点的观测值； $Z$ $( X _ { 0 } )$ 为估计值; $K _ { i }$ 为权重,权重由克里格方程组决定：

$$
\sum _ { i = 1 } ^ { n } K _ { i } C ( x _ { i } , x _ { j } ) - L \ = \ C ( x _ { i } , x _ { 0 } )
$$

$$
\sum _ { i = 1 } ^ { n } K _ { i } \ = \ 1
$$

式中： $C ( x _ { i } , x _ { 0 } )$ 为测站样本点与插值点之间的协方差； $C ( x _ { i } , x _ { j } )$ 为测站样本点之间的协方差; $L$ 为拉格朗日乘子。

1.3.4交叉验证法通过交叉验证的方法对建立的雪线场的精度进行评价(19-20]。具体步骤为：将雪线验证数据加载到ArcGIS中，并转化为矢量点，同时加载新疆区域雪线高程插值图，通过验证矢量点，提取雪线高程插值图上的对应点，此点为栅格点，通过ArcGIS中“栅格转矢量”工具进行转换，在属性表中导出矢量点的高程数据，最后与雪线验证数据进行对比分析。用MAE（平均绝对误差）和RMSE(均方根误差)作为交叉验证法评价精度的两个参数。其公式如下：

$$
M A E \ = \ { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } \ \left| \ T _ { _ { o i } } \ - \ T _ { _ { e i } } \ \right|
$$

$$
R M S E \ = \ \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left( \ T _ { o i } \ - \ T _ { e i } \right) { } ^ { 2 } }
$$

式中， $n$ 为测站数； $T _ { o i }$ 和 $T _ { e i }$ 分别表示第 $i$ 个台站位置上的实际观测值和预测值。

# 2 结果分析

# 2.1研究日期及雪线提取阈值的确定

经统计分析得出新疆三大山区的研究日期：天山山区为每年7月25日至8月24日（第 $2 0 6 \sim 2 3 6$ d)，共计31d;昆仑山区为每年7月22日至8月24日（第 $2 0 3 \sim 2 3 6 \mathrm { ~ d } _ { , }$ ，共计 $3 4 \mathrm { ~ d ~ }$ ;阿尔泰山区为每年8月4日至8月27日（第 $2 1 6 \sim 2 3 9 \mathrm { ~ d ~ }$ )，共计 $2 4 { \mathrm { ~ d ~ } }$ 。在此基础上得出，天山山区以31d数据叠加时的积雪持续时间比率法阈值为 $7 4 . 2 \%$ ，昆仑山区以 $3 4 \mathrm { ~ d ~ }$ 数据叠加时的积雪持续时间比率法阈值为 $7 6 . 5 \%$ ，阿尔泰山区以 $2 4 \mathrm { ~ d ~ }$ 数据叠加时的积雪持续时间比率法阈值为 $8 3 . 3 \%$ 。

# 2.2新疆雪线高度场的建立

以阈值为 $7 4 . 2 \% . 7 6 . 5 \%$ 和 $8 3 . 3 \%$ 分别对2015年天山区域第 $2 0 6 \sim 2 3 6 \mathrm { ~ d ~ }$ 、昆仑山区域第 $2 0 3 \sim 2 3 6$ d以及阿尔泰山区域第 $2 1 6 \sim 2 3 9 \mathrm { ~ d ~ }$ 的叠加数据进行雪线提取，提取的雪线数据转化成点文件并添加经纬度信息，在ArcGIS中调用Sharelt公司的ETgoWi-zard模块来生成 $1 0 ^ { \prime } \times 1 0 ^ { \prime }$ 的格网，运用ArcToolbox工具中的Overlay/Intersect命令提取格网内样点的经纬度和计算雪线高度等属性数据，利用Excel方式打开得到点图层的.dbf属性文件，以ET-Index为主字段进行扩展排序，然后再以字段ET-Index为分类汇总的分类字段计算经度、纬度和雪线高度的算术平均运算，得到的每个网格里只有一个虚拟雪线点分布的数据，如图1和图2所示分别为数据简化前后网格像元内的点。把所得的雪线高程数据分为两部分，一部分作为插值数据，另一部分作为验证数据。通过普通克里格插值法对2015年新疆区域雪线插值点进行空间插值。加载DEM数据，对生成的插值图，以大于等于 $1 5 0 0 \mathrm { ~ m ~ }$ 的高程进行掩膜，在此基础上生成相邻为 $1 0 0 \mathrm { ~ m ~ }$ 的等值线，并对等值线进行曲线圆滑等处理，如图3为等值线圆滑后图像。

经交叉验证，插值出的雪线高程MAE（平均绝对误差）为 $4 . 4 9 \mathrm { ~ m ~ }$ ，RMSE（均方根误差）为48.93m,其误差达到本研究的精度需求。

# 2.3雪线高度场的空间分布特征

2.3.1新疆雪线分布的总体特征新疆区域水系流域地形复杂、冰雪较多，雪线高程分布会受到空间地形的影响，由图3可见其分布有以下几个特征：

（1）雪线高程分布总体上是北低南高，从北向南先升高再降低然后再逐步升高，具有纬度地带性特征。从图3可以看出，雪线最低值出现在阿尔泰山区，值为 $3 0 0 0 \mathrm { ~ m ~ }$ ,向南逐渐升高，至西南方向昆仑山区南部达到最大值，约为 $5 6 0 0 \mathrm { ~ m ~ }$ 。雪线高程从北向南升到天山中东段附近( $( 3 9 0 0 \mathrm { ~ m } )$ 开始下降，到伊犁河谷附近降到最小值，下降幅度为 $8 0 0 \mathrm { ~ m ~ }$ ，之后向南持续升高。虽然从北到南雪线高程出现了升高一降低一升高的现象，但由于北部区域最低点与南部最高点之间的差值达到了 $2 6 0 0 \mathrm { ~ m ~ }$ ,而从天山中东段附近到伊犁河谷的差值为 $8 0 0 \mathrm { ~ m ~ }$ ,并且此区域降到的最低值，并未低于整个研究区的最低值，因此，新疆区域雪线高程具有由北向南升高的总体趋势。

![](images/8ff7a4dca5c7999e78df997b679d089144bac0e6e288db11147431a03b720fba.jpg)  
图1数据简化前网格像元内的点  
Fig.1Points within the grid before data reduction

![](images/e52dab21284e78b7d82286133014d7109aa7963e9b2a172bcdaf247d80617097.jpg)  
图2数据简化后网格像元内的点

![](images/1e5209fa12848c649a830bb87500642ede6c1366b7245a174fcbeafb8c8f4abf.jpg)  
Fig.2Points within the grid after data reduction   
图32015年新疆区域圆滑后的雪线等值线示意图Fig.3After the smooth snow line contour mapof xinjiang area in 2015

雪线高程变化梯度的总方向与由纬度影响的热流变化梯度相同，遵循了全球平衡线分布的一般规律，即由北向南升高。这反映了新疆区域影响雪线高程的气温作用远远高于降水作用，说明了高大的昆仑山脉阻碍了印度洋水汽输送到新疆区域，使得新疆南部降水减少，温度较高，雪线高程较高；阿尔泰山脉海拔相对较低，对来自北冰洋的水汽阻碍较少，降水较多;伊犁河谷三面环山，来自大西洋的水汽在此被阻挡，造成此区域降水量丰富，由于这两区域降水相对较多，气温相对较低，使得新疆北部地区雪线高程较低。因此，新疆区域形成了南部雪线高，并逐步向北降低的分布格局。

（2）雪线高程西高东低，分布总趋势是由东北向西南逐渐升高，具有经度地带性分布特征。从图5可以看出，在西南边缘塔什库尔干东南方向雪线高程值达到最高( $\mathrm { ~ 5 ~ 6 0 0 ~ m } )$ ），向东西方向开始逐渐降低，向西至乌恰县最西边，雪线降低变化梯度约为$4 . 8 \ \mathrm { m } \cdot \mathrm { k m } ^ { - 1 }$ ,向东北方向雪线高程依次递减,到尉犁东北方向降至 $4 ~ 0 0 0 ~ \mathrm { ~ m ~ }$ ，雪线降低变化梯度约为$1 . 3 6 \mathrm { ~ m ~ } \cdot \mathrm { k m } ^ { - 1 }$ ,此后雪线分布稀疏,变化缓慢。

（3）雪线场南部分布密集，北部分布稀疏。新疆南部有着巨大的昆仑山脉，地势高，东西范围大，横跨 $2 ~ 0 0 0 ~ \mathrm { k m }$ 以上，在强大的内外力共同作用下形成极为复杂的地表形态，如山谷口、多高山、极高山、断裂带等，再加上各个山峰高低不一，气温降水分布不均匀，以及坡度、坡向等因素的共同影响，致使新疆南部雪线相对密集，变化梯度大，约为 $3 . 3 5 \mathrm { ~ m ~ }$ ·$\mathrm { k m } ^ { - 1 }$ 。新疆北部相对于南部地势较低,变化较缓,降水分布较为均匀，气温变化较平缓等因素共同作用，使得新疆北部雪线分布相对稀疏，变化梯度小，约为 $0 . 6 2 \mathrm { ~ m ~ } \cdot \mathrm { k m } ^ { - 1 }$ ,比新疆南部低5倍多。

2.3.2新疆雪线分布的区域特征由于新疆南北跨度较大，为了更准确的反映新疆雪线变化特征，现将新疆分成3个区域进行研究，即天山山区、昆仑山区和阿尔泰山区。

# （1）天山山区雪线分布的区域特征

从图3可以看出，天山山区雪线总体分布体征为：南高北低，东高西低。从南到北雪线逐渐降低，与整个新疆雪线变化特征一致，具有纬度地带性分布特点。最高点在天山南段乌恰县境内，雪线高程为 $4 \ 6 0 0 \ \mathrm { m }$ ,然后向东北方向递减,最低值 $3 ~ 1 0 0 \mathrm { ~ m ~ }$ ，雪线变化梯度为 $2 \mathrm { ~ m ~ } \cdot \mathrm { ~ k m ~ } ^ { - 1 }$ ；从西向东雪线波动式升高，具有经度地带性的分布特点。最低点出现在伊犁河谷附近，雪线高程为 $3 ~ 1 0 0 \mathrm { ~ m ~ }$ ,向东逐渐递增，升到吐鲁番盆地附近达到最大值，为 $4 ~ 0 0 0 ~ \mathrm { { m } }$ ，雪线变化梯度为 $0 . 9 \mathrm { ~ m ~ } \cdot \mathrm { ~ k m ~ } ^ { - 1 }$ ,之后一段距离雪线变化较为平稳，振幅在 $2 0 0 \sim 4 0 0 \mathrm { ~ m ~ }$ 。

天山南段，深居内陆，受到高大山脉的阻挡，大西洋水汽难以进人，同时该区域面向中国最大的沙漠(塔克拉玛干沙漠)，大气水分较少，空气干燥，两方面的共同作用使得此区域降水较少，气温较高，导致雪线较高。由于伊犁河谷三面环山的地形，使得大量的水汽在此被阻挡，造成此区域降水量丰富，气温较低，且雪线较低。大西洋的水汽越过山脉之后向四周深处逐渐递减，沿着天山中东段方向到达吐鲁番盆地水汽达到最低值，加之此区域气温较高，使得雪线达到最大值。

# （2）昆仑山区雪线分布的区域特征

从图3可以看出，昆仑山区雪线分布总特征为：中间高，两边低。从昆仑山最西边雪线高程为4500$\mathrm { ~ m ~ }$ ，向西雪线高程开始递增，到阿克陶县的中部达到$5 ~ 2 0 0 ~ \mathrm { ~ m ~ }$ ,雪线变化梯度约为 $4 . 6 7 \ \mathrm { m } \cdot \mathrm { k m } ^ { - 1 }$ 。之后雪线高程开始小范围的下降，在阿克陶县的东南方向降到 $4 4 0 0 \mathrm { ~ m ~ }$ ,变化梯度约为 $1 9 . 6 3 \ \mathrm { m } \cdot \mathrm { k m } ^ { - 1 }$ 。此后雪线高程沿着弧形方向逐步升高，在塔什库尔干的东南边界达到此山区雪线高程的最大值，为5600$\mathrm { ~ m ~ }$ ,此阶段雪线的变化梯度约为 $4 . 5 3 \ \mathrm { ~ m ~ } \cdot \mathrm { ~ k m ~ } ^ { - 1 }$ 。继续向西很长的一段距离，雪线高程维持在 $5 4 0 0 ~ \mathrm { m } \sim$ $5 6 0 0 \mathrm { ~ m ~ }$ ,此段位于昆仑山的中部，只有极小一部分区域雪线高程为 $5 ~ 1 0 0 ~ \mathrm { m }$ 。进入东昆仑山，雪线高程自西向东依次降低，降到此山区的最低点（4300m),变化梯度约为 $1 . 4 7 \ \mathrm { m } \cdot \mathrm { k m } ^ { - 1 }$ 。

在昆仑山的东部，印度季风从海拔 $5 ~ 0 0 0 ~ \mathrm { ~ m ~ }$ 高空越过青藏高原山地，到达昆仑山地区已经很微弱，仅可在昆仑山北坡形成少量降水，唯有强大的太平洋季风在6一8月间可到达昆仑山东部边缘，带来一定降水，该区域受到该季风的影响由东向西递减，到达昆仑山的中部影响极其微弱；同时，来自大西洋的湿润气团受到高大的帕米尔高原的阻碍，只有极少部分的气团能够翻越，由西向东受到此气团的影响依次减弱，到达昆仑山的中部影响作用甚微；此外，亚洲最干旱的大陆中心位于昆仑山的北坡，属暖温带柴达木荒漠和塔里木荒漠，在大陆气团的持续作用下，引起日气温和年气温的巨大波动。在山的低层，7月平均气温 $2 5 \sim 2 8 \mathrm { ~ \textdegree C }$ ,在1月高于 $- 9 \mathrm { ~ \textdegree C }$ ，然而在山的上部和西藏边界处，7月平均气温低于10$\mathcal { \mathrm { C } }$ ,在冬季则常降至 $- 3 5 \ \mathrm { { ^ circ C } }$ 或更低。从以上分析可以看出，此山系中段降水量少，气温高，空气最为干燥，西部和东部的降水相对较为丰富，气温较低，空气较湿润。最终导致昆仑山区雪线分布总特征为中间高，两边低。

（3）阿尔泰山区雪线分布的区域特征

本文对阿尔泰山区的研究，仅限于新疆范围内，此段属于阿尔泰山中段南坡，呈西北至东南走向。从图3可以看出，雪线分布总特征为西北向东南依次降低。坐落在新疆区域的阿尔泰山区，雪线高程在 $3 \ 0 0 0 \sim 3 \ 3 0 0 \ \mathrm { m }$ ,雪线起伏不大，变化梯度仅为0.$7 7 ~ \mathrm { m } \cdot \mathrm { k m } ^ { - 1 }$ ,变化较为平缓。阿尔泰山处于湿润的西风气流迎风面，到达新疆境内，由西北到东南依次减弱，降水也沿此方向逐渐减少，气温逐渐升高。最终使得此区域雪线高程的总特征显现为西北高，东南低。

# 3结论

本文以新疆为研究区，利用2015年逐日积雪产品MOD10A1/MYD10A1数据,通过积雪持续时间比率法提取研究区雪线，并运用克里金插值法建立新疆区域雪线场，在此基础上对研究区雪线空间分布特征进行分析。结果如下：

（1）通过交叉验证得出：普通克里格插值法建立的新疆雪线场MAE（平均绝对误差）为 $4 . 4 9 \mathrm { ~ m ~ }$ ，RMSE（均方根误差）为 $4 8 . 9 3 \mathrm { ~ m ~ }$ ,其误差满足本研究的精度需求。

（2）从整个研究区分析得出：雪线高程呈现出北低南高，西高东低的格局，其值在 $3 \ 0 0 0 \sim 5 \ 6 0 0$ m,具有典型纬度地带性和经度地带性的分布特点；同时，雪线场南部分布密集北部稀疏。

（3）从局部区域分析得出：天山山区雪线高程南高北低，东高西低；昆仑山区中间高，两边低；阿尔泰山区从西北向东南依次降低。

（4）各个区域雪线分布差异较大，其内部分布复杂，雪线高程高低交错，

# 参考文献（References）：

[1]蒋复初,吴锡浩,王书兵,等.中国大陆森林线空间分布特征及 其与多年冻土线、气候雪线的关系[J].地质力学学报，2004， 10（4）:289-298.[Jiang Fuchu,Wu Xihao,Wang Shubin,et al. Features of space distribution of the forest line and relations between the forest line and climatic limit of permafrost and climatic snowline in china[J].Journal of Geomechanics,2OO4,1O(4）:289 -298.]

[2]庄小翠,周鸿奎,王磊,等.新疆北部牧区雪灾评估指标及其成 因分析[J].干旱区研究,2015,32（5）：1000-1006.［Zhuang Xiaocui,Zhou Hongkui,WangLei,et al.Evaluation and cause study on the snow disasters in pastoral areas of northern Xinjiang [J].Arid ZoneResearch,2015,32(5):1 000-1006.]

[3]陈梦蝶.青藏高原地区雪线时空变化动态研究[D].兰州：兰州大学,2014.[ Chen Mengdie.Spatio-temporal Change Dynam-ic of Snowline on Tibetan Plateau[D].Lanzhou;Lanzhou universi-ty,2014.]

[4]肖清华,张旺生,张伟,等.祁连山地区更新世以来冰期雪线变 化研究[J]．干旱区研究,2008,25（3）:426-432.[Xiao Qinghua,Zhang Wangsheng,Zhang Wei,et al. Study on snow line and climate change during different ice ages in the Qilian Mountains since pleistocene[J].Arid Zone Research,2008,25（3）:426- 432.]   
〔5］王利平,谢自楚,丁亮福,等.基于GIS 的羌塘高原冰川系统雪 线场的建立及其空间分布特征[J].干旱区地理,2010,33（5）： 692-702.[Wang liping,Xie zichu,Ding liangfu,et al.Establishing the field of equilibrium line altitude of the glacier system in the Chiangtang Plateau based on geographic information system and its distribution characteristics[J].Arid Land Geography,2010,33 (5) :692 -702.]   
[6]邓育武,谢自楚,秦建新,等.恒河-雅鲁藏布江流域雪线场的 建立及其环境意义[J].冰川冻土,2006,28(6）:865－872. [Deng Yuwu,Xie Zichu,Qin Jianxin,etal.The field of equilibrium line altitude in the Ganga-Yarlung Zangbo rivers system: Establishment and its environmental significance[J]. Journal of Glaciology and Geocryology,2006,28(6）:865-872.]   
[7］邓育武,谢自楚,李玲玲.基于GIS 的西藏南部雪线场的建立 及其空间分布特征[J].云南地理环境研究,2006,18（3）：10- 14.[Deng Yuwu,XIE Zichu,Li Lingling. Creating the distribution field of equilibrium line altitude based on GIS in the southern of Tibet and analyzing its distribution characters[J].Yun Nan Geographic Environment Research,2006,18(3）:10-14.]   
[8］王艺霖,王太保.青藏高原现代雪线及其影响因素分析[D]. 兰州：兰州大学,201O．[Wang Yilin,Wang Taibao.Analyses of modern snowline and its influential factors in the Tibet〔D]. Lanzhou:Lanzhou university,2010.]   
[9］张杰,韩涛,王建.祁连山区1997-2004 年积雪面积和雪线高 度变化分析[J].冰川冻土,2005,37（5）:649-654．〔Zhang Jie,Han Tao,Wang Jian. Changes of Snow-cover Area and Snowline Altitude in the Qilian Mountains,1997-2004[J]. Journal of Glaciology and Geocryology,2005,37（5）:649 -654.]   
[10]赵明洋,别强,何磊,等.基于去云处理的祁连山积雪覆盖遥感 监测研究［J].干旱区地理,2014,37（2）：325-332.〔Zhao Mingyang,Bie Qiang,He Lei,et al.Estimating snow cover accuracy from MODIS and AMSR-E with cloud removal methodology in Qilian Mountains[J].Arid Land Geography,2014,37(2）:325- 332.]   
[11］施雅风.中国冰川概论［M].北京：科学出版社,1988.[Shi Yafeng.Introduction of Chinese Glacier【M].Beijing:Science press,1988.]   
〔12］李光辉,王成,习晓环,等.机载 LiDAR 和高光谱数据融合提取 提取冰川雪线[J].国土资源遥感,2013,25（3）：79－84.［Li Guanghui,Wang Cheng,Xi Xiaofeng,et al.Extraction of glacier snowline based on airborne LiDAR and hyperspectral data fusion [J].Remote Sensing for Land and Resources,2013,25(3）:79 - 84.]

[13]努尔比亚·吐尼牙孜，布祖热·买买提明，张云惠.南疆西部降雪时空分布特征及其突变分析[J].干旱区研究，2016，33(5）:934-942.[Nurbiye Tunyaz,Buzuhra Mamat,ZhangYun-hui.Spatiotemporal Distribution and Abrupt Change of Snowfall inthe West of South Xinjiang[J]．Arid Zone Research,2016,33(5):934 -942.]

[14]李光辉，王成，习晓环，等.机载LiDAR和高光谱数据融合提取 冰川雪线[J].国土资源遥感,2013,29(3）：79-84．［LiGuanghui,Wang Cheng,Xi Xiaohuan,et al.Extraction of glacier snowline based on airbourne LiDAR and hypersdectral data fusion[J]. Remote SensingForLand&Resources,2013,29(3）:79-84.] [15]张连成，胡列群，李帅，等.基于遥感影像的雪线提取方法对比 分析—以天山中东段为例[J].干旱区地理，2015，38（4）：788 -796.[Zhang Liancheng,Hu Liequn,Li Shuai,et al.Comparison of snow line elevation extraction method based on remote sensing image:A case of north slope of Tianshan Mountains[J].Arid Land Geography,2015,38(4）:788-796.]

[16]汤国安，杨昕.地理信息系统空间分析实验教程[M].北京：科学出版社,2O12.［Tang Guoan,Yang Xin.Geographic InformationSystem Spatial Analysis Experiment Rutorial[M].Beijing:SciencePress,2012.]

[17]牟乃夏，刘文宝，王海银,等.地理信息系统教程[M].北京：测绘出版社,2O13.［Mou Naixia,Liu Wenbao,Wang Haiyin,et al.Geographic information system course[M]. Beijing:Science press,2012.]  
[18]石朋,芮孝芳.降雨空间插值方法的比较与改进[J].河海大学学报（自然科学版）,2005，33（4）:361-365.[ShiPeng,RuiXiaofang.Comparison and improvement of spatial rainfall interpola-tion methods[J].Journal of Hohai University(Natural Sciences）,2005，33(4) :361-365.]  
[19]何龚,傅德平，赵志敏,等.基于GIS 的新疆降水空间插值方法分析[J].水土保持研究,2008,15（6）：35-37.［HeGong，FuDeping,Zhao Zhimin,et al.Analysis of spatial Interpolation meth-ods to precipitation based on GIS in Xinjiang[J].Research of Soiland Water Conservation,2008,15(6):35-37.]  
[20]彭彬，周艳莲，高苹,等.气温插值中不同空间插值方法的适用性分析—以江苏省为例[J].地球信息科学学报,2011,13（4)：539 -548.[Peng Bin,Zhou Yanlian,Gao Ping,et al. Suitabilityassessment of different interpolation methods in the griddingprocess of station collected air temperature:A case study in JiangsuProvince,China[J]. Journal of Geo -information Science,2011,13(4) :539 -548.]

# Based on GIS the establishment of the Xinjiang snowline and its distribution characteristics research

ZHANG Liancheng1,HU Liequn2,LI Shuai3,HOU Xiaogang1,ZHENG Zhaojun4

(1 Xinjiang Uygur Autonomous Region Climate Center,Urumqi 83ooO2,Xinjiang,China; 2 Xinjiang Uygur Autonomous Region Meteorological Service Centre,Urumqi 830o02,Xinjiang,China; 3 Urumqi Desert Institute of CMA,Urumqi 830002,Xinjiang; 4 The National Meteorological Satellite Meteorological Center,Beijing 1Ooo81,China)

Abstract:This paper taking xinjiang as the study area，Using daily snow products MOD10A1/ MYD10Al data in 2015，Throughthe snow duration ratio method to extractthe snow line,and using kriging interpolation method to establish the xinjiang Snowline field,On the basis tothe snowline spatial distribution characteristics studied.Bythe analysis: Ordinary kriging interpolation method to establish the xinjiang snowline field MAE is $4 . 4 9 \mathrm { ~ m ~ }$ ，RMSE is $4 8 . 9 3 \mathrm { ~ m ~ }$ ，The error can satisfy the requirements of this study accuracy；From the analysis in the study area,snowlineelevations：the north area is lower than thesouth area,the west area is higher than theeast，value in 3000- $5 6 0 0 \mathrm { m }$ ，as the typical zonal longitude and latitude zonal distribution characteristics，and snowline field distribution in southern densely populated northern sparse；From the local area analysis，Snowline of Tianshan mountains: the north is lowerthan the south area,theeast is higherthan the west area.Snowline of Kunlun mountains:High middle andlowon both sides the westarea is higher than theeast.Snowlineof Altay mountains：Northwest to southeast in turnreduce.The snow line distributiondiference is bigger,its internal distribution iscomplex,snow line elevation height.

Key words:Xinjiang;Snowline field;GIS;Snow duration ratio method