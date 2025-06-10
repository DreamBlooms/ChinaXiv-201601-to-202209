# 基于反射率和亮度温度的锡林郭勒积雪深度估算

李慧融

(锡林浩特国家气候观象台，内蒙古 锡林浩特026000)

摘要：积雪是我国西北干旱半干旱区重要的水资源，也是影响全球气候变化的重要因子之一。目前光学影像反射率和雷达亮温数据是积雪遥感领域的主要数据，本文首次结合两类遥感数据估算积雪深度，并比较偏最小二乘法和机器学习算法(人工神经网络、支持向量机和随机森林算法)在积雪深度估算方面的表现。以锡林郭勒盟2012—2015年积雪深度数据为例，基于反射率和亮度温度相结合的积雪深度估算精度优于单个数据源，且随机森林算法表现最好，均方根误差为2.93cm,满足实际应用的需求。研究结果对我国西北地区水资源分布、生态环境评估等研究具有重要意义。

关键词：积雪深度；MODIS；MWRI；机器学习

# 文章编号：

积雪是影响全球气候变化的重要因子之一，它对地气系统辐射平衡的影响早已被世界各国科学家证实。积雪也是我国西北半干旱地区极为重要的水资源，在区域水分平衡中发挥着极为重要的作用，与农牧业生产有着十分密切的关系[]。冬季积雪丰厚可以对农作物和牧草起到保温保的作用，为春季农业生产提供良好的水资源保障[2]。因此,积雪一直是人们气候变化研究的重点内容之一，宏观、科学的评估积雪资源状况对于水资源循环和全球能量交换研究具有重要意义[3-4]。积雪深度作为积雪资源评估中的重要参数之一，如何准确地估算积雪深度，一直是积雪遥感研究中的重要内容[5]

目前，估算积雪深度的遥感数据可以分为光学遥感数据和被动微波遥感数据。在光学遥感领域，陈乾[和周咏梅7分别建立了祁连山区和青南高原积雪深度与AVHRR反射率的统计关系。近年来，具有更高空间分辨率和光谱分辨率的MODIS数据也逐渐被用于积雪深度的估算[8]。在被动微波领域，CHANG等9在辐射传输和米氏散射的理论基础上建立了积雪深度与 $1 9 \mathrm { G H z }$ 和 $3 7 \mathrm { G H z }$ 水平极化的亮温差的统计方法。于惠等[10]、卢新玉等[11-12]也采用了类似的研究思路估算了中国地区的积雪深度。蒋玲梅等[13]和王功雪等[14]系统探究了我国FY-3B和FY-3CMWRI微波辐射数据在雪深估算的潜力，取得了较好的估算效果。经过不断的发展与改进，基于亮温的方法逐渐成为了被动微波遥感估算积雪深度应用最广泛的算法之一。

在积雪深度估算领域，光学遥感无法穿透积雪表层获得积雪内部信息，当积雪深度超过一定范围，某些波段的反射率达到饱和，限制了估算精度。与光学遥感相比，被动微波遥感在穿透能力与全天候工作特性方面具有先天性优势，可用于进行全天候的积雪监测[15，更加适用于积雪深度估算，但是其空间分辨率较低，通常在 $2 5 \mathrm { k m }$ 至 $1 0 0 \mathrm { k m }$ ，难以满足局地尺度空间分辨率研究的需求。已有研究综合利用光学遥感数据和被动微波遥感数据进行积雪识别[16-17],然而综合利用两类数据监测积雪深度的研究还未见报道。因此，本文的首要研究目的就是评估光学遥感和被动微波遥感数据结合在积雪深度估算的潜力。

考虑到积雪深度估算的复杂性，简单的线性模型有可能使得估算结果存在很大的不确定性[18]

# 干旱区地理

偏最小二乘法[19-20]可以克服自变量间的共线性，在遥感领域具有重要应用。除此之外，人工神经网络[21]、支持向量机[2]和随机森林算法[23-25]等机器学习算法也吸引了众多遥感学者的关注，其中，神经网络可以处理复杂的映射关系，支持向量机可以将低维数据转到高维空间进行回归，随机森林算法学习过程快、鲁棒性强。因此，本文的第二个研究目的就是比较4种方法积雪深度的估算精度，为北方地区积雪深度遥感估算提供理论参考依据。

# 研究区概况

锡林郭勒盟 $( 1 1 2 ^ { \circ } \sim 1 2 0 ^ { \circ } \mathrm { E } , 4 2 . 5 ^ { \circ } \sim 4 6 . 7 ^ { \circ } \mathrm { N } )$ 位于内蒙古自治区中部，海拔 $9 0 0 \sim 1 ~ 3 0 0 \mathrm { m }$ ,属于温带干旱半干旱大陆性气候，冬季寒冷，夏季较热，年均气温 $1 \sim 2 ~ \mathrm { \textdegree C }$ 。全盟大部分地区积雪时期集中在11月～次年3月份。

# 2数据与方法

# 2.1积雪深度数据

本文积雪深度数据来源于锡盟15个气象站点的实地观测数据，时间覆盖范围为2012一2015年，观测的积雪深度最大值为 $3 7 \ \mathrm { c m }$ 。根据MODIS地物分类图可知，这些气象站点的下垫面均为草地（图1）。

# 2.2MODIS反射率数据

本文下载了MODIS/Terra提供的8d合成反射率数据。该数据最大限度的去除了云的影响，保留了质量较高反射率数据。归一化积雪指数(Normal-izedDifferenceSnowIndex，NDSI)利用积雪在可见光高反射和短波红外较强吸收的特点，常被用于区分积雪与非积雪目标，是积雪遥感领域应用最广的指数之一,[1,26-27],计算公式如下：

![](images/fb9cf91a447284d50c82bb834808f2bb83fdd767f737da1b39f5a15b6a094d7d.jpg)  
图1研究区地理位置及气象站点分布  
Fig.1Location of the study area and distribution of the meteorological stations

$$
N D S I { = } ( R 4 { - } R 5 ) / ( R 4 { - } R 5 )
$$

式中： $R 4$ 和 $R 6$ 分别为MODIS第4波段和第6波段的反射率。

# 2.3FY-3B亮温数据

风云3B(FY-3B)卫星是我国发射的第2代极轨气象卫星，其搭载的微波成像仪(MWRI)提供了5个中心频率 $( 1 0 . 6 5 \setminus 1 8 . 7 \setminus 2 3 . 8 \setminus 3 6 . 5 \setminus 8 9 . 0 ~ \mathrm { G H z } )$ 、2种极化方式(H和V)的亮温数据，总共10个波段[22-23]MWRI数据包含升轨和降轨数据，过境时间分别为14：00和02：00左右，其中，白天升轨数据用于本文的研究。

# 2.4数据处理流程

首先，根据气象观测站点的经纬度提取与积雪深度观测时间对应的MODIS反射率数据和FY-3B亮温数据；其次，计算NDSI，保留NDSI大于0.4的数据；最后，反射率和亮温数据作为回归模型的因变量，积雪深度作为回归模型的自变量。在精度验证阶段，本文采用十字交叉验证方法对模型进行评价。

# 3结果与分析

# 3.1积雪数据概况

基于15个气象观测站点长时间雪深数据，本文总共使用了256个样本数据，其中积雪深度的频率直方图见图2，积雪深度观测值并不服从正态分布，不满足简单线性回归正态分布的要求，这也说明了简单线性回归模型不适用于积雪深度的反演。随着积雪深度的增大，频率降低，大部分积雪深度观测值落在 $1 \sim 2 0 ~ \mathrm { c m }$ 范围内，占总样本个数的 $8 6 \%$ ○

# 3.2反演精度比较

表1汇总了4种回归方法利用光学遥感数据、被动微波遥感数据以及两者合成数据的积雪深度估算精度。偏最小二乘法需要确定主成分的个数，随机森林算法需要事先确定决策树的变量个数，为了避免变量个数对偏最小二乘法和随机森林算法

12 9 %/率 6 3 ITLuuL 0 1 5 9 13 172125293337 积雪深度/cm

# 表1 四类回归算法在不同遥感数据源的积雪深度反演精度（RMSE）

Tab.1 Inversion accuracy of four regression algorithm based on different remote sensing data /cm   

<html><body><table><tr><td rowspan="2">回归算法</td><td colspan="3">遥感数据源</td></tr><tr><td>反射率</td><td>亮温</td><td>反射率+亮温</td></tr><tr><td>偏最小二乘</td><td>8.63</td><td>8.60</td><td>7.12</td></tr><tr><td>人工神经网络</td><td>6.88</td><td>5.53</td><td>3.92</td></tr><tr><td>支持向量机</td><td>7.81</td><td>4.07</td><td>3.31</td></tr><tr><td>随机森林算法</td><td>3.65</td><td>3.12</td><td>2.93</td></tr></table></body></html>

注：RMSE，均方根误差

精度影响，因此表1中的精度为所有可能变量情况下的平均值，这样能够更好地比较不同回归方法以及数据源之间的精度差异。

仅使用反射率数据情况下，随机森林算法取得最好的精度 $( R M S E { = } 3 . 6 5 \mathrm { c m } )$ )，其次为神经网络和支持向量机。仅使用亮温数据情况下，随机森林算法仍然表现最好 $( R M S E { = } 3 . 1 2 ~ \mathrm { c m } )$ ，但与人工神经网络相差不明显。偏最小二乘法的表现始终最差。值得注意的是对于4种方法，使用亮温数据估算积雪深度的精度均高于使用反射率数据，这可能归因于

反射率数据易于饱和。

综合反射率和亮温数据的情况下，表现最好的仍然是随机森林算法，但是3个机器学习算法的精度差异不大，RMSE为 $2 . 9 3 \sim 3 . 9 2 \mathrm { c m }$ ，远远低于偏最小二乘方法 $( R M S E { = } 7 . 1 2 ~ \mathrm { c m } ~ \$ )。偏最小二乘法虽然有很广泛的应用，但结果表明，该方法不适合于积雪深度的估算研究，而机器学习算法能够比较精确地估算积雪深度。

图3为4种回归方法的1:1图，从图3a中可以明显看出偏最小二乘法估算的积雪深度均小于20cm，估算精度较差。人工神经网络的实测值和估算值总体上落在1:1线附近，但是较为分散（图3b）。对支持向量机来说，大部分数据点落在1:1线上，但是由于积雪深度估算的复杂性，有一些点偏离1:1线较远，降低了支持向量机的精度(图3c)。表现最好的回归算法是随机森林算法(图3d)，大体上所有数据点均较为紧凑的落在1:1附近。值得注意的是，对于4种方法来说，估算结果在积雪深度较低的时候出现高估，而在高积雪深度的时候出现低估。

另外，对于随机森林算法来说，仅使用亮温数据与综合数据的精度相差 $0 . 1 9 \mathrm { c m }$ ，也就是说单独使用亮温数据已经可以取得较好的估算精度。通常情况下，被动微波遥感数据的空间分辨率较低，精度高，而光学遥感数据的空间分辨率高。融合两类遥感数据有望获得高空间分辨率和高精度的积雪深度空间分布图。

# 3.3积雪深度空间分布图

本文选取了2016年1月4号锡林郭勒盟地区天气晴朗、云量较少的MODIS影像数据，图4为MO-DIS数据 $5 0 0 \mathrm { m }$ 分辨率的真彩色图，锡盟绝大部分地区被积雪覆盖。从NDSI数据中也可以看出，大部分地区NDSI接近于1(图5)。

40 RMSE=7.12 cm 40 RMSE=3.92 cm 。 40 RMSE=3.31cm .。 40 RMSE=2.93 cm 0 星 8 。 。 8 0 88 880 站 9 0。 888 。 8 。 868 8 算 C 8 to   
10 e8 估 10 。 估 10 。 。 0 估 10 8 8 1 8   
0 0 8 0 0   
0 10203040 0 10203040 0 102030 40 0 10203040 实测雪深/cm 实测雪深/cm 实测雪深/cm 实测雪深/cm (a)偏最小二乘法 (b)人工神经网络 (c)支持向量机 (d)随机森林算法

# 干旱区地理

![](images/c610efa0ad309e7702ea90df3bd706dde83361ee469bfbe9db9bf9ea6c3044b5.jpg)  
图4锡林郭勒盟地区的真彩色合成图Fig.4True color image of Xilin Gol League

图6为融合反射率和亮度温度估算的积雪深度空间分布图（以随机森林算法为例，其他算法的结果未显示）。锡林郭勒盟地区东北部地区(东乌珠穆沁旗和乌拉盖)的降雪量高于西部地区(二连浩特、西苏旗和朱日和），与图6的积雪深度空间分布图一致。最高积雪深度出现在东乌珠穆沁旗地区，最大为 $2 1 \ \mathrm { c m }$ ○

# 4讨论与结论

反射率数据提供了积雪近表面的光学信息，而微波遥感能够穿透积雪内部，即亮度温度可以反映积雪内部的信息。两类数据在积雪深度估算均有重要的应用价值，但是亮度温度的估算精度高于反射率数据(表1)。本文首次尝试结合两类遥感数据用于积雪深度的估算，并以锡林郭勒盟15个气象观测站点的实测数据为例，结果表明综合利用积雪表面和内部信息明显改进了积雪深度估算精度。

![](images/64b6fe132465b50c8bdce92c103f2ea41f4b91450ae27a893ef3ec3529848b8b.jpg)  
图5锡林郭勒盟地区MODIS-NDSI

![](images/f6a1cc625c12675a094b39d57465e62edf4989a08303b3df58bc2f18d72f1f64.jpg)  
Fig.5MODIS-NDSI image of Xilin GolLeague   
图6锡林郭勒盟地区积雪深度空间分布图  
Fig.6Spatial distribution of snow depth of Xilin Gol League

以随机森林算法为代表的机器学习算法在积雪遥感领域的应用越来越广，这些学习算法能够处理积雪深度与反射率和亮度温度之间复杂的非线性关系。机器学习算法（人工神经网络、支持向量机和随机森林)均可以取得较为满意的积雪深度估算精度，尤其随机森林算法的表现最好。尽管偏最小二乘法可以消除变量的共线性，但是在积雪深度估算领域的表现较差，这可能归因于其难以适应复杂的积雪场景。

本文提出的方法综合利用了光学和微波遥感的优势，基于机器学习算法能够获得高精度和高空间分辨率的积雪深度空间分布图，对我国西北地区积雪深度遥感监测研究具有重要意义。

# 参考文献(References)

[1] SALOMONSON VV,APPEL I.Estimating fractional snow cover from MODIS using the normalized difference snow index[J].Remote Sensing of Environment,2003,89(3): 351-360.   
[2] 刘艳.基于MODIS数据的积雪深度反演研究[D].武汉：武汉大 学,2005.[LIU Yan. The study of snow depth derivation from MODIS data[D].Wuhan: Wuhan University,2005.]   
[3]姜康,包刚,乌兰图雅,等.基于MODIS数据的蒙古高原积雪时 空变化研究[J].干旱区地理,2019,42(4):782-789.[JIANG Kang,BAO Gang,WULANTUYA,et al. Spatiotemporal changes of snow cover in Mongolian Plateau based on MODIS data[J].Arid Land Geography,2019,42(4): 782-789.]   
[4] 周远刚,赵锐锋,张丽华,等.博格达峰地区冰川和积雪变化遥 感监测及影响因素分析[J].干旱区地理,2019,42(6):1395- 1403.[ZHOU Yuangang,ZHAO Ruifeng,ZHANG Lihua,et al. Remote sensing monitoring of the change of glacier and snow cover and its influencing factors in Mount Bogda[J].AridLandGeography,2019,42(6): 1395-1403.]   
[5] 李震,邵雨阳,周建民,等.基于MEMLS模型的积雪深度反演方 法[J].遥感学报,2013,17(3): 657-670.[LI Zhen,SHAO Yuyang, ZHOU Jianmin,et al.2O13.Snow-depth retrieval algorithms on MEMLS [J]. Journal of Remote Sensing,17(3): 657-670.]   
[6]陈乾,陈添宇.祁连山区季节性积雪资源的气候分析[J].地理研 究,1991,10(1):24-38.[CHENQian,CHEN Tianyu.Climatical analysis of seasonal snow resources in Qilian MT[J]. Geographical Research,17(3): 657-670.]   
[7]周咏梅,贾生海,刘萍.利用NOAA-AVHRR资料估算积雪参量 [J].气象科学,2001,21(1):117-121. [ZHOU Yongmei,JIA Shenhai, LIU Ping.The method of snowcover parameters estimation using NOAA-AVHRR date[J]. Scientia Meteorologica Sinica,2001, 21(1): 117-121. ]   
[8]孙知文,于鹏珊,夏浪,等.被动微波遥感积雪参数反演方法进 展[J].国土资源遥感,2015,27(1):9-15.[SUN Zhiwen,YUPengshan, XIA Lang. Progress in study of snow parameter inversion by passive microwave remote sensing[J]. Remote Sensing For Land & Resources,2015, 27(1): 9-15.]   
[9]CHANG A TC,FOSTER JL, HALL D K. Nimbus-7 SMMR derived global snow cover parameters[J].Annals of Glaciology,198, (9): 39-44.   
[10] 于惠,张学通,王玮,等.基于AMSR-E数据的青海省雪深遥感 监测模型及其精度评价[J].干旱区研究,2011,28(2):255-261. [YU Hui, ZHANG Xuetong,WANG Wei, et al. Monitoring model and accuracy evaluation of snow depth in Qinghai Province based on AMSR-E data[J].Arid Zone Research,2011, 28(2): 255-261.]   
[11] 卢新玉.基于被动微波遥感的北疆地区积雪深度反演[D].乌鲁 木齐：新疆师范大学,2011.[LU Xinyu.Snow depth retrieval based on the passive microwave remote sensing of northern Xinjiang[D]. Urumqi: Xinjiang Normal University,2011.]   
[12] 卢新玉,王秀琴,谢国辉,等.基于被动微波遥感的积雪深度反 演[J].干旱区资源与环境,2012,12:108-112.[LU Xinyu,WANG Xiuqin,XIE Guohui, et al.Snow depth retrieval based on the passive microwave remote sensing[J]. Journal of Arid Land Resources and Environment, 2012,12: 108-112.]   
[13]蒋玲梅,王培,张立新,等.FY3B-MWRI中国区域雪深反演算法 改进[J].中国科学:地球科学,2014,44(3):531-547.[JIANG Lingmei, WANG Pei, ZHANG Lixin,et al. Improvement of snow depth retrieval for FY3B-MWRI in China[J]. Scientia Sinica(Terrae),2014, 44 (3): 531-547.]   
[14] 王功雪,蒋玲梅,武胜利,等.FY-3B与FY-3C/MWRI交叉定标 及雪深算法应用[J].遥感技术与应用,2017,32(1):49-56. [WANG Gongxue,JIANG Lingmei,WU Shengli,et al. Intercalibrating FY-3B andFY-3C/MWRI for synergistic implementing to snow depth retrieval algorithm[J]. Remote Sensing Technology and Application,2017,32(1): 49-56.]   
[15] 刘宝康,冯蜀青,杜玉娥,等.积雪被动微波遥感研究进展与前 景展望[J].草业科学,2009,26(11):37-43.[LIU Baokang,FENG Shuqing, DU Yu'e, et al. Research progress and prospect of remote sensing with passive microwave from snow[J]. Pratacultural Science,2009,26(11): 37-43.]   
[16] TEDESCO M, MILLER J. Northern hemisphere snow-covered area mapping: Optical versus active and passive microwave data[J]. IEEE Geoscience & Remote Sensing Letters,2007,4(2): 221- 225.   
[17] 邵东航,李弘毅,王建,等.基于多源遥感数据的积雪反照率反 演研究[J].遥感技术与应用,2017,32(1):71-77.[SHAO Donghang,LI Hongyi,WANG Jian,et al.Retrieval of snow albedo based on multi-source remote sensing data[J]. Remote Sensing Technology and Application,2017,32(1): 71-77.]   
[18] 徐倩,刘志辉,房世峰.融雪期积雪深度高光谱反演方法研究 [J].光谱学与光谱分析,2013,33(7):1927-1931.[XU Qian,LIU Zhihui,FANG Shifeng.Retrieval method for estimating snow depth using hyperspectral data in snowmelt period[J]. Spectroscopy and Spectral Analysis,2013,33(7): 1927-1931.]   
[19] 王超,王建明,冯美臣,等.基于多变量统计分析的冬小麦长势 高光谱估算研究[J].光谱学与光谱分析,2018,38(5):1520- 1525.[WANG Chao,WANG Jianming,FENG Meichen,etal.Hyperspectral estimation on growth status of winter wheat by using the multivariate statistical analysis[J]. Spectroscopy and Spectral Analysis,2018,38(5): 1520-1525.]   
[20] SHA Z Y, XIE Y C, TAN X C, et al. Assessing the impacts of human activities and climate variations on grassland productivity by partial least squares structural equation modeling (PLS-SEM)[J]. Journal of Arid Land,2017,9(4): 473-488.   
[21] 侯海艳,侯金亮,黄春林,等.基于人工神经网络和AMSR2多频 微波亮温的北疆地区雪深反演[J].遥感技术与应用,2018,33 (2): 241-251. [HOU Haiyan,HOU Jinliang,HUANG Chunlin,et al.Retrieve snow depth of north of Xinjiang region from ARMS2 data based on artificial neural network technology[J]. Remote Sensing Technology and Application,2018,33(2): 241-251.]   
[22]MOUNTRAKIS G, IM J, OGOLE C.Support vector machines in remote sensing: A review[J]. ISPRS Journal of Photogrammetry and Remote Sensing,2011,66: 247-259.   
[23] ABDEL-RAHMAN E M,AHMED FB, ISMAIL R. Random forest regression and spectral band selection for estimating sugarcane leaf nitrogen concentration using EO-1 Hyperion hyperspectral data[J]. International Journal of Remote Sensing,2013,34(2):712- 728.   
[24]于新洋,赵庚星,常春艳,等.随机森林遥感信息提取研究进展 及应用展望[J].遥感信息,2019,34(2):8-14.[YU Xinyang, ZHAO Gengxing,CHANG Chunyan,et al. Random forest classifier in remote sensing information extraction: A review of applications and future development[J]. Remote Sensing Information, 2019, 34(2): 8-14.]   
[25] 包青岭,丁建丽,王敬哲,等.基于随机森林算法的土壤有机质 含量高光谱检测[J].干旱区地理,2019,42(6):1404-1414. [BAO Qingling, DING Jianli, WANG Jingzhe,et al. Hyperspectral detection of soil organic matter content based on random forest algorithm[J]. Arid Land Geography,2019,42(6): 1404-1414.]   
[26] 李长春,徐轩,包安明,等.基于FY3B-MWRI数据新疆区域积 雪深度反演[J].遥感技术与应用,2018,18(6):1030-1036.[LI Changchun,XU Xuan,BAO An- ming,etal. Thestudyon snow depth retrieval in Xinjiang regionbasedon FY3B-MWRI data[J]. Remote Sensing Technology and Application,2018,18(6): 1030-1036.]   
[27] 岳继博.李长春.齐修东,等.天山雪深反演算法验证与分析[I]l.

# Estimation of snow depth based on reflectance and bright temperature in Xilin Gol League

LI Hui-rong (Xilinhot National Climatological Observatory,Xilinhot O26ooo,Inner Mongolia,China)

Abstract: Snow is an important water resource inarid and semi-arid regions of northwest China,which is also one of the important factors that afecttheglobal climate change.Snow depth is the main parameter of the water resources and its estimation using aremote sensing technique has a vital efect on the assssment of resources and disease of northern China.The reflectance and brightness temperature data were the main data for snow remote sensing.Taking the snow depth data of 2O12—2O15 for Xilin Gol League,Inner Mongolia, China as an example, The MODIS/Terrasatelite reflectance data andFY-3B brightnesstemperature data forthe estimationof snow depth arecombined for the first time in this study.The estimation accuracy for partialleast squares and machine learning (artificial neural network,support vector machine and random forest)are then compared.Whenonly reflectivitydata is used,bestaccuracy isachievedbytherandom forestalgorithm (RMSE=3.65cm),follwed bythe neuralnetwork and support vector machine.The stochastic forest algorithm still performs best (RMSE=3.12 cm) when only the brightness and temperature data are used.However,no obvious diffrence is found with theartificial neural network.Using the partial least squares method exhibits the worst performance among the methods used.For the four methods,the accuracy of estimating snow depth using brightness temperature data is higher than that using reflectivity data,which may be atributed to the fact that reflectivity data is easy to saturate.Comprehensive research shows that the snow depth estimation accuracy based on the combination of reflectance and brightness temperature was beter than that with singledata.The random forest algorithm obtained the best performance,which is able to meet the needs of practical application.However,the accuracyof the three machine learning algorithms is not much different,with RMSE of $2 . 9 3 \substack { - 3 . 9 2 \ \mathrm { c m } }$ ,which is far lower than that of the partial least squares method （ $( R M S E { = } 7 . 1 2 ~ \mathrm { c m }$ ). Although partial least squares method can eliminate the collinearity of variables,its performance in snow depth estimation is poor,which may be atributed to its diffculty in adapting to complex snow scenes. Results of this paper have important significance for the study of water resources distribution and ecological environment assessment in northern China.

Key words: snow depth; MODIS; MWRI; machine learning