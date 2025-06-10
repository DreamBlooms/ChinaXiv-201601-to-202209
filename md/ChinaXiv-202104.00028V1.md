# 基于无人机的胡杨(Populuseuphratica）结构参数获取技术研究

杨雪峰1²，昝梅²，木尼热·买买提1,2

（1.新疆师范大学地理科学与旅游学院,新疆 乌鲁木齐830054;2.新疆维吾尔自治区重点实验室“干旱区湖泊环境与资源实验室”,新疆 乌鲁木齐830054)

摘要：快速准确获取森林结构参数具有重要的科学意义。通过使用大疆精灵 $4 \mathrm { P r o }$ 无人机通过倾斜摄影测量和正射摄影测量方式获取塔里木河下游胡杨林样地的冠层高度模型,提出一种自适应窗口最大值算法来分析处理，获取了研究区胡杨(Populus euphratica)的树高、冠幅和株数等结构参数。最后，使用地面实测数据对以上结构数据进行精度评价。结果表明：(1）自适应窗口最大值算法计算效果优于传统的固定窗口最大值算法。（2）倾斜摄影测量方式获取的树高、冠幅和株数精度均优于正射摄影测量方式。(3）倾斜摄影测量获取的结构数据与实测值比较,树高、冠幅和株数 $R ^ { 2 }$ 分别为0.9002,0.8403和0.9405，均方根误差分别是0.4457、0.6815和4.2500,证明使用消费级无人机可以有效获取单木尺度森林结构参数。

关键词：胡杨；结构参数；自适应窗口最大值算法；无人机；倾斜摄影测量文章编号：

森林在水文、生态、碳循环及气候变化中起着重要作用，森林结构信息如冠层高度、冠幅和株数等数据是森林生物量估算的基础，也是众多陆地碳循环生态模型的重要参数，准确且高效地获取森林结构参数具有重大的科学意义[1-2]。如果采用传统的森林调查方法，对于大面积的区域来说，这些方法费时费力，而且采集成本很高，有些地区往往难以通过实地方法进入和调查，因此很难在较大范围进行使用。遥感技术提供了相对低成本、高效益的方式。极化干涉 $\mathrm { S A R } ^ { [ 3 - 5 ] }$ 、高分辨率光学卫星遥感[6-8]星载Lidar[9-10],多角度卫星遥感[11-12]以及多源遥感[13]等遥感技术已在实践中证明可以用来获取中低分辨率、区域尺度的森林结构参数。但是，如何利用遥感技术获取单木尺度的结构信息依然是一个尚待解决的问题。

机载激光雷达(Aeriallaser scanning,ALS)具有高精度的激光测距设备，加之飞行高度较低，可以获取高密度的地面点云数据，可用来获取单木结构信息[14-16。但是,由于使用航空飞行和LiDAR设备的成本较高，限制了LiDAR技术的广泛使用。

无人机(Unmannedaerialvehicle,UAV)在近些年的快速发展，提供了获取森林结构新的技术手段。无人机可通过普通相机获取地面影像，使用SFM(Structurefrommotion)摄影测量技术进行三维重建获取地面点云[17-18],在计算产生的数字表面模型(Dig-ital surfacemodel,DSM）数字高程模型(Digital eleva-tionmodel,DEM）和冠层高度模型（Canopy heightmodel,CHM)的基础上进行森林结构测量[19-20]。与ALS技术相比较，无人机影像摄影测量方式有较大的成本优势,同时能保持有较高的精度[21],国内外都有积极尝试无人机在植被调查工作中的应用研究[22]。以往研究中使用的无人机多为价格不菲的测绘级固定翼无人机[23-24],固定翼无人机有续航时间长、载荷大、飞行稳定性高等优点，往往搭载高精度量测相机和实时动态差分（Realtimekinematic,RTK)设备，而价格较低的旋翼无人机特别是消费级

# 干吴区地理

无人机，存在着空中姿态不稳定、相机分辨率不高、相机未经定标、机载GPS精度不高等缺陷，但是由于小巧灵活、起降方便等优点，在森林调查等领域具有很大的应用潜力。有关消费级无人机在森林结构方面的研究还比较少，在使用上缺乏相应研究。

另外，在利用高分辨率影像数据进行单木识别或冠幅、树高获取时，尚存在技术和算法上的问题。目前，使用较多的有多尺度分割、分水岭算法、局域最大值和种子点区域增长法等。多尺度分割和分水岭算法通过对影像数据进行分割，确定树冠范围，实现单木识别[25-28]

多尺度分割、分水岭算法针对高分辨率卫星或无人机光学影像使用较为合适，但是当使用DSM或CHM数据时，未能有效利用其中的高度信息。因此，使用CHM数据时，更适合使用局域最大值和种子点区域增长法，在单木识别的同时，可提取树高和树冠信息[29-30]。

使用局域最大值法的关键是选择合适大小窗口，在指定大小的窗口内寻找栅格值最大者(种子点)作为树冠最高点，来代表树木。由于窗口的大小会影响到是否能找到正确的树木种子点，窗口太大容易漏掉一些最大值，太小又产生多余不正确的种子点[31]。解决的方式之一是使用动态窗口来搜索局部最大值点[32],此方法依赖树高-冠幅的相关程度，在相关性差的区域则可能带来较高的误差。

塔里木河胡杨林是新疆地区典型的森林资源，塔里木河下游是重要生态保护和恢复区域，胡杨林结构信息对塔里木河流域森林资源监测、生态保护和恢复具有重要意义。在此区域与胡杨林结构相关的研究主要采用地面调查方法[33-36]。总体来看，以上研究还未能实现大范围胡杨树高、冠幅和株数等结构信息的高效率自动获取。

本文使用消费级旋翼无人机，对塔里木河下游胡杨林进行空中摄影测量，研究有效的无人机测量方法，以及研究如何改进区域最大值法能更有效地进行单木识别，并在此基础上进行树高和冠幅提取。

# 1研究区概况

研究区位于新疆塔里木河下游，处于34团与英苏之间的塔里木河河道区域 $\mathrm { ( 8 8 ^ { \circ } 0 1 ^ { \prime } 0 7 " } { \sim } 8 8 ^ { \circ } 0 1 ^ { \prime } 5 5 ^ { \prime \prime } \mathrm { E }$ $4 0 ^ { \circ } 2 5 ^ { \prime } 5 9 ^ { \prime \prime } { \sim } 4 0 ^ { \circ } 2 6 ^ { \prime } 3 3 ^ { \prime \prime } \mathrm { N } )$ ，面积约 $1 . 1 \ \mathrm { k m } ^ { 2 }$ (图1)。该区域的环境为暖温带大陆性干旱气候，平原地区年均温 $1 0 \ \%$ ,年均降水量约 $5 5 ~ \mathrm { m m }$ ，降水匮乏，植被稀少。在塔里木河河岸附近发育有河岸林，主体为胡杨(Populuseuphratica）,林下基本没有植被覆盖，表层土壤为粉砂土，且盐碱化程度较高。地下水水位较高区域分布有怪柳(Tamarixchinensis)灌丛，黑枸杞（Lyciumruthenicum），芦苇（Phragmites commu-nis）,骆驼刺(Alhagisparsilolia)等。该区域平均海拔 $8 4 0 \mathrm { m }$ ,地形较为平坦。

![](images/228c0fe70376608c1e3f41b2fc9d2b5f1cecc08ba664524b10f795fb3ed62673.jpg)  
图1研究区地理位置  
Fig.1 Geographical location of the study area

由于过去多年塔里木河下游断流，出现了下游胡杨大面积衰败和死亡的现象，从2000年后采取紧急输水措施后，情况有所好转。因长期干旱缺水，研究区内胡杨的生长状态存在明显差别，表现在树冠的完整程度有较大的差异[37]，这与正常生长状态的林地有很大的不同，这种状况给空中、地面测量和后续的数据处理带来了一定的困难。

# 2数据与方法

# 2.1数据来源

2.1.1实测数据2018年7月在研究区进行了实地调查，测量获取了49棵胡杨树高、冠幅、以及25个$1 0 0 \mathrm { m } { \times } 1 0 0 \mathrm { m }$ 采样格网中单木株数统计信息。

选取不同生态型的胡杨进行树高和冠幅量测，方法为：（1）使用激光测距仪的测高功能分别从3个不同方向对树冠最高点进行测量，获取胡杨树高,再取平均值作为实测树高;（2）使用OruxMaps[38]手持机地图软件记录每棵树的坐标，并在地面分辨率为 $0 . 5 \mathrm { ~ m ~ }$ 的WorldView2多光谱影像地图上进行位置标注，方便后期与无人机影像比对；（3）使用长卷尺分别获取相隔 $6 0 ^ { \circ }$ 的3个方向的树木冠幅取平均值。

使用OruxMaps手持机地图软件，以WorldView2影像为参照，实地对每个格网中的胡杨进行株树统计，并在地图软件中进行标记。2.1.2无人机摄影测量数据使用的无人机为中国大疆创新科技有限公司生产的精灵 $4 \mathrm { P r o }$ ,该产品为四旋翼无人机，定位为消费级航拍无人机。

无人机获取地面影像的方法目前主要有2种：正射和倾斜摄影[39-40]。传统的正射方式以垂直角度进行拍摄，而倾斜摄影技术是国际测绘领域近些年发展起来的一项高新技术，它颠覆了以往正射影像只能从垂直角度拍摄的局限，通过同时从1个垂直、4个倾斜等5个不同的角度采集影像。通常在无人机倾斜摄影测量时搭载的是五镜头相机，但小型无人机体积小，搭载能力弱，续航时间短等因素限制了其使用倾斜摄影技术的能力。

精灵 $4 \ : \mathrm { P r o }$ 配备有一个相机，本研究使用精灵4Pro通过多次飞行完成正射和倾斜测量，并通过与实测数据对比分析正射摄影测量和倾斜摄影测量获取的树高和冠幅数据精度。相机的性能和航线的规划直接影响到最终的拍摄效果和后期的数据处理结果。由于使用的大疆精灵 $4 \mathrm { P r o }$ 无人机配备的是单镜头相机，为了获取整个区域的倾斜影像，根据调查区的范围，使用航线规划软件Altizure[41]规划了包括一次垂直和四次倾斜的五次飞行任务。

本次飞行任务未设置地面控制点。具体飞行参数如表1所示。最终得到垂直正射照片421张，倾斜摄影照片2307张。

表1飞行参数Tab.1 Paremeters of fly  

<html><body><table><tr><td colspan="4">飞行参数</td></tr><tr><td>飞行设备</td><td>精灵4Pro</td><td>飞行高度/m</td><td>110</td></tr><tr><td>相机分辨率</td><td>2000万</td><td>地面分辨率/cm</td><td>5</td></tr><tr><td>飞行方式</td><td>1正射 4倾斜</td><td>摄影角度/</td><td>0,45</td></tr><tr><td>航向重叠度/%</td><td>80</td><td>旁向重叠度/%</td><td>75</td></tr></table></body></html>

# 2.2 研究方法

2.2.1技术路线本研究首先采用了传统的地面调查方式获取地面真实数据作为无人机获取数据的参照、然后采用无人机低空摄影测量方式获取地面影像、使用软件方法对数据进行自动处理(图2)。

![](images/6f9fa12de573fbb2e0a96880d4bc4bb612ced0024376de1b7676a07e9e8c2756.jpg)  
Fig.2Technology roadmap

2.2.2无人机数据处理通过PIX4DMapper软件[42],分别对正射和倾斜摄影方式获取的无人机影像进行影像匹配、空三、点云生成等处理步骤，获得

# 干吴区地理

了研究区的加密点云。对加密点云进行分类处理得到地面和植被点云数据，再通过插值和栅格化处理得到DSM和DEM数据，对DSM和DEM计算生成了CHM数据，下图为倾斜摄影测量方式处理结果(图3)。2.2.3结构提取算法（1）种子点识别。由于研究区胡杨树高-冠幅回归方程 $R ^ { 2 }$ 为0.3741,胡杨树高-树冠的线性关系并不十分显著，该线性关系不适宜直接作为动态窗口使用。

因此，本文提出一种“自适应窗口局域最大值算法”。该算法在固定窗口局域最大值算法的基础上，利用树高-树冠大小回归方程预测下限的1.5倍窗口做距离阈值，并结合种子点间高度变化的判断来增加种子点选择的准确性。

具体方法如下：首先根据CHM分辨率，使用较小的固定窗口，利用局域最大值算法产生种子点集合，逐一从中取出种子点作为当前种子点，通过计算当前种子点与其他种子点间最短距离，找出小于距离阈值的种子点进行下一步判断处理，处理的原则是判断2个种子点之间高程数值的起伏变化是否超过指定高度阈值，小于该阈值则认为这2个种子点属于一株树，高度小的种子点将被高度大的种子点合并，否则认为属于不同冠层不进行处理，直到循环完成所有种子点判断和处理。该算法实现了自适应窗口效果(图4)。

最终产生的种子点为单木最高点，种子点数量为单木数量。

(2）冠幅提取。树木种子点确定后，采用区域增长法以种子点所在像元为中心，依次对CHM中种子点像元旁边八方向的邻域像素进行搜索判断，如果邻域像元值在指定的下降坡度范围内就继续增长，直到到达搜索范围边缘，或者下降坡度变化超过指定阈值，所有满足条件的邻域像元构成了单木的树冠范围，最后通过几何计算获得冠幅大小。以上算法均使用Python实现。

# 3结果与分析

# 3.1算法分析

分别用自适应窗口最大值算法和固定窗口最大值算法(分别使用 $1 . 5 \ : \mathrm { m } \setminus 2 . 0 \mathrm { m } \setminus 2 . 5 \mathrm { m }$ 和 $3 . 0 \mathrm { m }$ 固定窗口)处理倾斜摄影方式得到的CHM数据生成胡杨种子点，与25个样地的胡杨株树统计数据进行比较（图5)。固定窗口最大值算法在不同窗口大小下，$R ^ { 2 }$ 值变化范围较大，从 $0 . 7 8 3 4 { \sim } 0 . 8 2 6 1$ ,说明需要根据区域的实际情况，选择合适的窗口大小才能取得较高的精度，而自适应窗口算法的 $R ^ { 2 }$ 最高，为0.8341。由于该算法降低了对窗口大小的依赖性，可以取得更高的精度。

![](images/55d00b29f5ceefacc9c551f82cfd1a878e720e6c624de3291062f97538d11d8e.jpg)  
图3无人机倾斜摄影影像处理结果  
Fig. 3 Processing results of UAV images by oblique photogrammetry

![](images/c13227b6139c378c1b11fffae59192cf07beccc0f2279aa51eaab6ab6f15daa4.jpg)  
图4自适应窗口最大值算法Fig.4 Adaptive window maxima algorithm

# 3.2测量方式分析

3.2.1测量方式对比使用自适应窗口最大值算法分别对无人机正射和倾斜测量获取的CHM数据进行分析处理，得到了胡杨树高、冠幅数据(图6)。

与实际测量值相比，2种测量方式均高估了树高，低估了冠幅。倾斜摄影测量方式获取树高和冠幅的均值、中位数和数据分布更接近实测值，说明倾斜摄影测量比正射摄影测量更准确。

3.2.2结构数据相关分析为了更精确分析获取的树高、冠幅和株数的数据质量，使用决定系数(Coef-ficientof determination, $R ^ { 2 }$ )、平均相对误差(Meanrel-ative error,MRE)和均方根误差(Root mean squarederror，RMSE)等指标与实测数据进行比较。

根据与实测的49株胡杨样本比较可以发现，倾斜摄影测量方式获取的树高与实测值的 $R ^ { 2 }$ 为

![](images/e92861aa032cdb1d1d05e401ea6b34deb4576397bde16e63cbec9a36b449c48a.jpg)  
图5自适应窗口算法与固定窗口算法比较 Fig.5Comparison of adaptive window and fixed windows maxima algorithm

![](images/cb23bf78cdf5c14d954ade1234294c2223a3cd7a08c152e5220cf2235daa24c0.jpg)  
图6正射、倾斜摄影测量值与地面实测值比较 Fig.6 Comparison of data of ortho and oblique photogrammetry with field data

0.9002,RMSE为 $0 . 4 4 5 7 \mathrm { ~ m ~ }$ ,MRE为 $5 . 4 0 0 \%$ （图 $\mathrm { 7 a }$ ；倾斜摄影测量获取的冠幅与剔除冠幅残缺样点后的45株胡杨冠幅实测值的 $R ^ { 2 }$ 为0.8403，RMSE为$0 . 6 8 1 5 \mathrm { ~ m ~ }$ ,MRE为 $8 . 9 2 5 \%$ （图7b）。

使用25个统计样区对倾斜摄影测量提取的单木胡杨进行统计并与实测株数比较，发现单木侦测的精度较高， $R ^ { 2 }$ 为0.9405,RMSE为4.25株，MRE为$6 . 9 2 8 \%$ （图 $\mathrm { 7 c }$ 。

# 3.3误差分析

形成以上结果的原因是由测量、算法、无人机和环境因素共同造成的。

![](images/ba8c6f94f4385246c6050b312e088a9d313482a3cbdcc0a3820126c75a301243.jpg)  
图7倾斜测量参数与地面实测值比较 Fig.7 Comparison of data of oblique photogrammetry and field data

3.3.1测量因素（1)测量的难度不同。由于树高测量的目标比较清楚，即树的最高点，目标明确单一。而冠幅由一系列的边缘点决定，确定的难度较大，胡杨树冠位置的判断较难精确掌握。

3.3.3无人机因素（1）由于大疆精灵 $4 \mathrm { P r o }$ 无人机只配备一个相机，所以要完成倾斜摄影测量必须进行多次飞行。加上精灵 $4 \ : \mathrm { P r o }$ 配备的一块电池只能飞行20多分钟，即使使用备用电池，飞行任务需要在几天内完成，较长的飞行周期会出现不同的太阳光照条件，表现在照片上出现同样物体明暗变化，清晰程度变化相对较大。这些都会影响后面的空三处理。

法判断的问题，从而造成树高和树冠的错误估计。

(2）测量方式的影响。树高的测定使用精度较高的激光测距仪，所以最终结果和实地测量的数据一致性较高，差异相对较小，而使用皮尺量测冠幅取平均值的方法，则易产生人为误差，造成与实测值的一致性低于树高。

（2）大疆精灵 $4 \mathrm { P r o }$ 相机为非专业测量相机，内方位元素未知，会导致一定程度的图像畸变。该型号无人机虽然相机做了升级，但相比较而言相机性能与专业相机有较大的差距。

3.3.2算法因素在重叠树冠区域，算法容易出现 种子点疏漏或被错误合并的情况，还有树冠增长算

3.3.4环境因素（1）由于这里地处沙漠边缘，风沙天气频发，影响了部分影像的质量

(2）研究区土壤为粉沙土，加上盐碱化程度较高，土壤反射率很高，造成在特定角度，会形成强烈的镜面反射，在相应区域的影像上形成亮斑，可能形成错误的点云数据或者点云生成失败。

# 4结论

无人机技术的快速发展，为空间测绘、资源调查等领域的用户提供了更多的技术手段。相对而言，无人机在干旱区森林资源的应用研究比较匮乏，消费级无人机技术在森林资源调查的应用潜力尚不明确，无人机数据处理算法上存在改进的空间。本研究通过对消费级无人机不同摄影测量方式、以及无人机影像不同处理算法获取的胡杨结构参数与实测值进行比较，结果说明：

（1）固定窗口最大值算法需要根据实际情况设置合适窗口大小，方能取得较好效果，而自适应窗口最大值算法降低了对设置窗口大小的限制，获取的结果要优于固定窗口最大值算法，该算法可以更有效提取CHM数据中的胡杨结构参数。

(2）倾斜摄影和正射摄影2种测量方式获得的结果，与实测数据相比，两者均高估了树高，低估了冠幅。倾斜摄影方式获取的数据精度比正射摄影方式更高。

(3）使用自适应窗口最大值算法和倾斜摄影测量数据获取的树高、株数与实测值的决定系数 $R ^ { 2 }$ 均大于0.90,冠幅 $R ^ { 2 }$ 大于0.84,平均相对误差均小于

$9 \%$ 。说明结合这几种技术能够获得高精度的单木尺度森林结构参数。

消费级无人机虽然硬件条件不及测绘级无人机，但如果设置合理的飞行测量方案，采用更先进的算法，使用消费级无人机获取胡杨结构参数是可行的。该方法可以用来代替部分人工地面测量，即保证一定效率，同时有效地降低了调查成本。

未来的研究重点是寻找更有效的基于无人机数据的图像处理算法，进一步提高自动化数据提取的准确性和效率。

# 参考文献(References)

[1]Rdig E,Cuntz M,Rammig A,et al. The importance of forest structure for carbon flux estimates in the Amazon rainforest[J]. Environmental Research Letters,2018,13(5): 054013,doi: 10.1088/1748- 9326/aabc61.   
[2]Houghton R A,HallF,Goetz S J. Importance of biomass in the global carbon cycle[J]. Journal of Geophysical Research: Bio-geoences,2009,114(G2): 1-13.   
[3]( Garestier F,Dubois-Fernandez P C,Guyon D,et al.Forest biophysical parameter estimation using L and P-band polarimetric SAR data[J].IEEE Transactions on Geoscience & Remote Sensing,2009, 47(10): 3379-3388.   
[4]李文梅,李增元,陈尔学,等.层析SAR反演森林垂直结构参数 现状及发展趋势[J].遥感学报,2014,18(4):741-751.[Li Wenmei,Li Zengyuan, Chen Erxue,et al. Status and development of tomographic SAR for forest vertical structural parameters inversion [J]. Journal of Remote Sensing,2014,18(4): 741-751.]   
[5]Lei Y,Siqueira P.Estimation of forest height using spaceborne repeat-pass L-band InSAR correlation magnitude over the US State of Maine[J]. Remote Sensing,2014,6(11):10252-10285.   
[6]崔少伟,范文义,金森,等.基于树影与快鸟图像的单木树高提 取[J].东北林业大学学报,2011,39(2):47-50.[Cui Shaowei, Fan Wenyi,Jin Sen,et al.Extraction of individual tree height using quickbird images based on tree shadow[J]. Journal of Northeast Forestry University,2011,39(2): 47-50.]   
[7]Ke Y, Quackenbush L J.A comparison of three methods for automatic treecrown detection and delineation from high spatial resolution imagery[J]. International Journal of Remote Sensing,2011, 32 (13): 3625-3647.   
[8] Gomes MF,Maillard P.Using spectraland textural features from RapidEye images to estimate age and structural parameters of Cerrado vegetation[J]. International Journal of Remote Sensing, 2015, 36(11-12): 3058-3076.   
[9]Nie S,Wang C, Zeng H,et al.A revised terrain correction method for forest canopy height estimation using ICESat/GLAS data[J]. ISPRS Journal of Photogrammetry and Remote Sensing,2015,108: 183-190.   
[10]吴迪.基于GLAS 和MISR数据的森林冠层高度和地上生物量 遥感估算研究[D].哈尔滨:东北林业大学,2015.[Wu Di.Forest canopy height and aboveground biomass estimation based on GLAS and MISR data[D]. Harbin: Northeast Forestry University,2015.]   
[11]Chopping M,Nolin A,Moisen G G,et al.Forest canopy height from the Multiangle Imaging Spectro-Radiometer assessed with high resolution discrete return lidar[J].Remote Sensing of Environment, 2009,113(10): 2172-2185.   
[12]Chopping M, Crystal S, Feng Zhao,et al. Forest structure and aboveground biomass in the southwestern United States from MODIS and MISR[J]. Remote Sensing of Environment, 2O11,115(11): 2940-2953.   
[13] 胡凯龙,刘清旺,崔希民,等.多源遥感数据支持下的区域性森 林冠层高度估测[J].武汉大学学报:信息科学版,2018,43(2): 289-296,303.[Hu Kailong,Liu Qingwang,Cui Ximing,et al. Regional forest canopy height estimation using multi-source remote sensing data[J]. Geomatics and Information Science of Wuhan University,2018,43(2): 289-296,303.]   
[14]Sherrill KR,Lefsky MA,Bradford JB,etal.Forest structure estimation and pattern exploration from discrete-return lidar in subalpine forests of the central Rockies[J]. Revue Canadienne De Recherche Forestiere,2008,38(8):2081-2096.   
[15] 霍达.基于机载LiDAR反演森林参数的研究——以内蒙古依 根地区为例[D].哈尔滨:东北林业大学,2015.[Huo Da. Study on inversion of forest parameters based on airborne LiDAR[D]. Harbin: Northeast Forestry University,2015.]   
[16]韦雪花.轻小型航空遥感森林几何参数提取研究[D].北京:北 京林业大学,2013.[Wei Xuehua.Research of forestry geometrical parameter extraction with light and small airborne remote sensing system[D]. Beijing: Beijing Forestry University,2013.]   
[17]Iglhaut J, Cabo C,Puliti S,et al. Structure from motion photogrammetry in forestry: A review[J]. Current Forestry Reports,2019,5 (3): 1-14.   
[18] Nex F, Remondino F. UAV for 3D mapping applications: A review [J]. Applied Geo-matics,2014,6(1): 1-15.   
[19]Panagiotidis D,Abdollahnejad A, Surovy P,et al.Determining tree height and crown diameter from high-resolution UAV imagery[J]. International Journal of Remote Sensing,2017,38(8-10): 2392- 2410.   
[20]Mohan M, Silva C A,Klauberg C,et al. Individual tree detection from unmanned aerial vehicle (UAV) derived canopy height model in an open canopy mixed conifer forest[J]. Forests,2O17,8(9): 340-354.   
[21] Cao L, Liu H,Fu X,et al. Comparison of UAV LiDAR and digital aerial photogrammetry point clouds for estimating forest structural attributes insubtropical plantedforests[J].Forests，2019,0(2): 145-160.   
[22]岳健,穆桂金,唐自华,等.基于NDVI的新疆荒漠地区植被覆 盖度遥感估算经验模型研究[J].干旱区地理,2020,43(1):153-

# 干吴区地理

160.[Yue Jian,Mu Guijin,Tang Zihua,et al.Remote sensing estimation modelsfor vegetationcoverage indesertregionsof Xinjiang based on NDVI[J].AridLandGeography,2020,43(1):153-160.]   
[23] Grzn(rova A,Mokro M, Surov P,et al. The crown diameter estimation from fixed wing type of UAV imagery[J]. The International Archives of the Photogrammetry,Remote Sensing and Spatial Information Sciences,2019, XLII-2/W13: 337-341.   
[24] Anders N,Keesstra S,Cammeraat E.The effect offlight altitude to data quality of fixed-wing UAV imagery: Case study in Murcia, Spain[C]//EGU General Assembly Conference Abstracts,2014.   
[25] 李晓靖.基于高分影像的面向对象分类与单木树冠提取研究 [D].北京:北京林业大学,2017.[Li Xiaojing.Study on object oriented classfication and individual tree crown extraction based on high resolution imagery[D]. Beijing:Beijing Forestry University, 2017.]   
[26] 郭昱杉,刘庆生,刘高焕,等.基于标记控制分水岭分割方法的 高分辨率遥感影像单木树冠提取[J].地球信息科学学报,2016, 18(9): 1259-1266.[Guo Yushan,Liu Qingshen, Liu Gaohuan, et al. Individual tree crown extraction of high resolution image based on marker-controlled watershed segmentation method [J]. Journal of Geo-Information Science,2016,18(9): 1259-1266.]   
[27] 冯静静,张晓丽,刘会玲.基于灰度梯度图像分割的单木树冠提 取研究[J].北京林业大学学报,2017,39(3):16-23.[Feng Jingjing, Zhang Xiaoli,Liu Huiling. Single tree crown extraction based on gray gradient image segmentation[J]. Journal of Beijing Forestry University,2017,39(3): 16-23.]   
[28] 何艺,周小成,黄洪宇,等.基于无人机遥感的亚热带森林林分 株数提取[J].遥感技术与应用,2018,33(1):168-176.[He Yi, Zhou Xiaochen, Huang Hongyu,et al. Counting tree number in subtropical forest districts based on UAV remote sensing images [J].Remote Sensing Technology and Application,2018,33(1): 168-176.]   
[29] 杨礼.融合UAV遥感影像与SFM点云的树木识别及参数提取 [D].焦作:河南理工大学,2018.[Yang Li. Tree parameters extraction using UAV remote sensing image and SFM point cloud [D]. Jiaozuo: Henan Polytechnic University,2018.]   
[30] 汪霖,李明阳,方子涵,等.基于无人机数据的人工林森林参数 估测[J].林业资源管理,2019(5):61-67.[Wang Lin,Li Mingyang,Fang Zihan,et al.Plantation forest parameter estimation based on UAV data[J].Forest Resources Management,2019(5): 61-67.]   
[31]Daley N MA, Burnett C N,Wulder M,et al. Comparison of fixedsize andvariablesizedwindowsfortheestimationof re crown position[C]//IEEE International Geoscience & Remote Sensing Symposium. IEEE,1998.   
[32] 李响,甄贞,赵颖慧.基于局域最大值法单木位置探测的适宜模 型研究[J].北京林业大学学报,2015,37(3):27-33.[Li Xiang, Zhen Zhen, Zhao Yinghui.Suitable model of detecting the position of individual tree top based on local maximum method[J]. Journal of Beijing Forestry University,2015,37(3):27-33.]   
[33] 于军,白冠章,梁继业,等.塔里木河上、中、下游胡杨种群高度 结构特征[J].干旱区资源与环境,2012,26(7):103-109.[Yu Jun,Bai Guanzhang,Liang Jiye, et al. The height structure characteristics of Populus euphratica population along Tarim River[J]. Journal of Arid Land Resources and Environment, 2012,26(7): 103-109.]   
[34] 蔡富艳,玉米提·哈力克,艾尔肯·艾白不拉,等.塔里木河下游 阿拉干断面胡杨树高的分布和密度[J].生态环境,2008,17(3): 1086-1090.[Cai Fuyan, Umut Halik,Arkin Abibul,et al.Tree height distribution and density of Populus euphratica forest along the Argan section in the lower reaches of Tarim River[J].Ecology and Environment, 2008,17(3): 1086-1090.]   
[35] 万红梅,李霞,董道瑞,等.塔里木河下游林地树冠QuickBird 影 像信息提取与分析[J].西北植物学报,2011,31(9):1878-1885. [Wan Hongmei,Li Xia,Dong Daorui, et al.Abstraction and analysis of tree-crown of forest land based on QuickBird image in the lower reaches of Tarim River[J].Acta Botanica Boreali-Occidentalia Sinica,2011,31(9): 1878-1885.]   
[36] 李越帅,郑宏伟,罗格平,等.集成U-Net方法的无人机影像胡 杨树冠提取和计数[J].遥感技术与应用,2019,34(5):939-949. [Li Yueshuai, Zheng Hongwei, Luo Geping,et al. Extraction and counting of Populus euphratica crown using UAV images integrated with U-Net method[J]. Remote Sensing Technology and Application,2019,34(5): 939-949.]   
[37] Aishan Tayierjiang,Halik Umut,Florianbetz,et al. Stand structure and height-diameter relationship of a degraded Populus euphratica forest in the lower reaches of the Tarim River,Northwest China[J]. Journal of Arid Land,2015,7(4): 544-554.   
[38] 杨勇长.Oruxmaps 软件在森林资源清查中的应用[J].福建林 业,2014(3): 46-48.[Yang Yongchang. Application of oruxmaps software in forest resources inventory[J].Fujian Forestry,2O14(3): 46- 48.]   
[39] San J, Wanshou J,Wei H, et al. UAV-based oblique photogrammetry for outdoor data acquisition and ofsite visual inspection of transmission line[J]. Remote Sensing,2017,9(3): 278-290.   
[40]Liu Y, Zheng X,Ai G,et al. Generating a high-precision true digital orthophoto map based on UAV images[J]. Isprs International Journal of Geo Information,2018,7(9): 333-338.   
[41]孙春辉,成锡平.基于无人机的实景三维建模在消防中的应用 [J].消防科学与技术,2018,37(4):501-504.[Sun Chunhui, Cheng Xiping.Application of real 3D modeling in firefighting based on UAV[J]. FireScienceandechnolgy,201,37(4):50-504]   
[42] Michal Brach, Chan C W,Pawel Szymanski. Accuracy assessment of different photo-grammetric software for processing data from lowcost UAV platforms in forest conditions[J]. iForest Biogeosciences and Forestry,2019,12: 435-441.

# Structural parameters acquisition technology of Populus euphratica based on UAV

YANG Xuefeng1²， ZAN Mei'²， Munire MAIMAITI12 (1.College of Geography Science and Tourism,Xinjiang Normal University,Urumqi 83oo54,Xinjiang, China; 2.Xinjiang KeyLaboratoryofLakeEnvironmentand Resources inArid Zone,Urumqi 83oo54,Xinjiang,China)

Abstract: Obtaining the structural parameters of forests accurately and quickly is of great scientific significance. The technologies of polarimetric and interferometric synthetic-aperture radar,high-resolution optical satelite remote sensing,spaceborne lidar, and multi-angle satelite remote sensing can effectively obtain forest structure regionally. However, it is chalenging to obtain structural parameterson a single-tree scale using these technologies. The rapid development of unmanned aerial vehicles (UAVs) recently provides a new means to obtain forest structures.The ground images can be obtained using UAV ordinary cameras,and the ground point cloud can be obtained using structure from motion photogrammetry technology for 3D reconstruction，generating digital surface model,digital elevation model (DEM),and canopy height model (CHM).The local maximum algorithm is used to process CHM data. The key to the local maximum algorithm is to select an appropriate window size and find the largest grid value (seed point)in the window as the highest point of the tree crown to represent the tree. However,itis challenging to calculate the window size.One solution is to use the variable window method. In this study,the height and crown diameter of 49 Populus euphratica trees were measured in the lower reaches of the Tarim River, Xinjiang,China. The Populus euphratica were counted in a $2 5 1 ~ \mathrm { h m } ^ { 2 }$ grid,and a DJI Phantom 4 Pro Was used to acquire the image data.The DJI Phantom 4 Pro is a consumer-grade UAV using oblique and ortho photogrammetry,respectively. An adaptive window maxima algorithm was proposed to analyze and process CHM data,obtaining the structural parameters of the Populus euphratica forest in the study area,such as tree height, crown diameter,and number of trees.The structural parameters extracted using oblique and ortho photogrammetry were compared and analyzed with field-measured data.The results and conclusions are (1)the adaptive window maxima algorithm and fixed window maximum algorithm (1.5-，2.0-，2.5-，and $3 . 0 \mathrm { - ~ } \mathrm { m }$ fixed windows, respectively） were used to process CHM data obtained using oblique photogrammetry to generate Populus euphratica seed points. The data are compared with the statistical data of 25 sample plots. The $R ^ { 2 }$ of fixed window values vary widely from 0.7834 to 0.8261,indicating that we should choose an appropriate window size to achieve higher accuracy according to the actual situation of the region. While the $R ^ { 2 }$ of the adaptive window maxima algorithm is the highest (O.8341),it can achieve higher accuracy because the algorithm reduces the window size dependence. (2) The tree height measured using oblique and ortho photogrammetry is overestimated, and the crown diameter is underestimated.The mean,median,and distribution of treeheight and crown diameter obtained using ortho photogrammetry are closerto the field-measured values,indicating that oblique photogrammetry could achieve more accurate results than ortho photogrammetry. (3） The oblique photogrammetry and fieldmeasured data were compared to determine the coefficients $( R ^ { 2 } )$ of tree height, crown diameter, and tree numbers per hectare (0.9002,0.8403,and 0.9405,respectively).The root means squared error was 0.4457,0.6815,and 4.2500,respectively.The results prove that it is effective to use a consumer-grade UAV to obtain forest structure parameters on a single-tree scale using an appropriate measurement method and processing algorithm.

Key words: Populus euphratica; structural parameters； adaptive window maxima algorithm; UAV； obliquephotogrammetry