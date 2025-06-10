# 全球降雨计划GSMaP与IMERG卫星降雨产品在陕西地区的精度评估

李彦妮¹，黄昌1²，庞国伟1.2.3

（1.陕西省地表系统与环境承载力重点实验室，陕西 西安710127;2.西北大学城市与环境学院地表系统与灾害研究院,陕西 西安710127;3.旱区生态水文与灾害防治国家林业和草原局重点实验室，陕西 西安710127摘要：以中国气象局提供的地面降雨观测资料为参考，利用相关系数、均方根误差和相对偏差，降雨误报率、命中率和关键成功指数等6种不同的统计分析指标，从年、季、月、日4种不同的时间尺度对两种高分辨率卫星降雨产品(IMERG和GSMaP)在陕西省的精度进行了对比和评价，并对二者在监测强降雨过程中的表现进行了对比分析。结果表明：(1）在年尺度上，GSMaP的数据精度高于IMERG。GSMaP和站点观测数据高度相关，而IMERG和站点观测数据中度相关;GSMaP高估了年尺度的降雨，而IMERG低估了年尺度的降雨。(2)在季节尺度上，两种数据均在夏季的精度最高，总体上，IMERG在季节尺度的精度亦高于GSMaP。（3）在月尺度上，两种产品与地面观测数据均呈现较高的相关性，而且均存在一定程度的高估，但IMERG比GSMaP更具有相对较高的精度。（4）在日尺度上，GSMaP的数据精度略高于IMERG。（5）卫星降雨产品的数据精度与降雨量有关，总体表现为雨量小时高估、雨量大时低估。(6)卫星降雨产品数据精度呈现了明显的地域差异，GSMaP对陕西省的降雨总体表现为低估，其中对陕北的低估最为明显;IMERG对关中有轻微高估，对陕北和陕南则存在明显低估。（7)通过对4场次强降雨事件的分析发现，GSMaP对大雨及以上强降雨事件的监测能力比IMERG略强。研究结果可以为该地区的气象水文研究在选择和使用降雨数据资料时提供参考。

关键词：卫星降雨产品；全球降雨观测计划(GPM)；强降雨事件；精度评估

# 文章编号：

降雨代表了地球表层与大气之间至关重要的能量和水分交换，是气象气候相关研究的关键变量[2]。传统的降雨观测方式虽然可以获得小范围较为准确的降雨数据，但是存在空间分布不均匀以及部分地区测站稀少等问题，难以准确反映大尺度降雨的时空分布[3-4]。卫星遥感技术能够克服传统观测方法在时空上的局限性，实现全方位、多时相、大范围的连续降雨观测。1997年，美国发射了热带降雨测量任务[5]（Tropical rainfall measuring mission,TRMM)卫星,其搭载的降雨雷达（Precipitation ra-dar,PR)是全球首个星载测雨雷达，可以进行 $3 5 ^ { \circ } \mathrm { S } \sim$ $3 5 ^ { \circ } \mathrm { N }$ 之间的降雨观测，且能够提供暴雨三维结构，这对精确估计降雨起到了重要作用[,为大尺度水文气象的研究提供了新途径[1-8]。基于TRMM提供的多年降雨观测，结合其他研究和业务卫星提供的降雨产品，形成覆盖范围为 $5 0 ^ { \circ } \mathrm { S } { \sim } 5 0 ^ { \circ } \mathrm { N }$ 的降雨数据，即TRMM多卫星降雨分析产品TMPA（TRMMmulti-satelliteprecipitationanalysis）9」,其空间分辨率为$0 . 2 5 ^ { \circ } \times 0 . 2 5 ^ { \circ [ 1 0 ] }$ 。2014年,由美国航天航空局(Na-tional Aeronautics and Space Administration,NASA)

和日本宇宙航空研究开发机构(Japan Aerospace Ex-plorationAgency，JAXA)联合实施的全球降雨观测计划（Global precipitation measurement,GPM），是TRMM的后续卫星降雨计划[7]。其发射的GPM降雨卫星携带了全球第一个 $\mathrm { { K u / K a } }$ 波段双频测雨雷达(Dual-frequencyprecipitation radar,DPR) "],能够更加精准地监测微量降雨 $\cdot { < } 0 . 0 5 \ \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ )和固态雨雪[12]，自此，多卫星遥感反演降雨正式由TRMM时代跨入了GPM时代[13]。GPM时代广泛应用的两种卫星降雨产品为IMERG（Integrated multi-satellite retrievalsfor GPM)[7]和 GSMaP(Global satellite mapping of pre-cipitation)[8]。与TRMM相比,GPM卫星降雨产品覆盖范围更广（扩展到全球），时空分辨率更高（GS-$\mathrm { M a P : 1 ~ h , 0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ } ; I M E R G : 3 0 ~ m i n , 0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ } ) ^ { [ 1 4 ] } } _ { \mathrm { \Omega } }$

近些年来，国内外已涌现出大批对GPM卫星降雨产品的相关研究。Beria等[15]对IMERGFinal Run和TRMM3B43在印度86个盆地的反演精度进行了对比分析，结果显示，IMERG在整个印度盆地的所有降雨强度上的表现均优于TRMM。Ning等[16]对GPM产品在中国东部地区的误差特征和性能分析中表明，IMERGV04对中国大部分地区的降雨有显著的高估,而GSMap-gaugedVO6对降雨的估测偏差与降雨量有关。陈汉清等在对GPM卫星降雨产品的评估工作中发现,在复杂地形地区和高海拔地区，GPM卫星降雨产品的表现不理想，甚至会出现不可靠的情况，且其精度具有明显的季节差异性。王思梦等[18]、李媛媛等[19]在黑河流域和黄河流域的研究中均发现IMERGV04存在对高海拔地区降雨低估的问题。GPM已应用于流域水文模拟[2]，但是，卫星降雨数据易受多种因素影响，使其数据精度在不同时期、不同地区出现较大差异。因此，在选择降雨资料开展区域性研究之前，对相关卫星降雨产品的精度验证十分重要。

陕西省地跨长江、黄河两大水系，地形气候复杂。万相均等[21]根据1981—2010年的气象站点实测数据，分析了陕西省降雨变化的时空分布，发现陕西省年降雨主要呈现南北差异型的空间分布，表现为陕西南部降雨较多，北部降雨较少。任亮等[22]对陕西秦巴山区TRMM3B42的精度评价结果表明，TRMM数据在年、季、月尺度上有较高的精度，日尺度精度相对较差，降雨事件探测能力表现良好。曾昭昭等23基于地理加权回归(GWR)模型对陕西秦巴山区TRMM3B43数据进行降尺度研究。但是，高分辨率GPM时代的卫星降雨产品在陕西地区的精度还不清楚。理解从TRMM时代到GPM时代卫星降雨产品在空间分辨率及覆盖范围提高的同时，其精度有何变化["],对于进一步促进新型高分辨率卫星降雨产品在陕西地区的应用具有重要意义。

因此，本研究拟对两种GPM时代的卫星降雨产品(IMERG和GSMaP)在陕西地区的精度进行评估和对比，以研究区内地面观测数据作为参考，选取一系列精度评价指标，分别从年、季、月尺度和日尺度对两种卫星降雨产品的精度进行评价；同时，对两种数据在陕北、关中和陕南3个地貌类型区的精度进行横向对比分析；最后，选取典型强降雨事件分析两种数据在监测强降雨事件的表现，

# 1研究区概况

陕西省位于中国内陆腹地，黄河中游，邻接8省，具有承东启西、连接南北的区位之便，介于 $1 0 5 ^ { \circ } 2 9 ^ { \prime } .$ ）$1 1 1 ^ { \circ } 1 5 ^ { \prime } \mathrm { E } , 3 1 ^ { \circ } 4 2 ^ { \prime } { \sim } 3 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { N }$ 之间，由南向北依次横跨北亚热带、暖温带和中温带3个气候带，南北气候差异较大。陕西降雨总体呈现南多北少的规律[24],受季风和地形影响，陕西的降雨季节性变化特征明显，总体表现为夏季多雨而冬季干燥[25]。为研究卫星降雨产品在不同地貌类型区的误差特征，以北山和秦岭为界，将陕西省划分成陕北黄土高原、关中平原和陕南秦巴山地3个地貌区(图1)。

# 2数据与方法

# 2.1降雨数据

本文以中国气象数据网提供的月值数据集和日值数据集作为地面基准数据，17个气象站点的空间分布如图1所示。选取2014年12月一2019年11月的数据作为年尺度分析的数据，其他尺度分析中使用的数据时间跨度均为2016年12月一2017年11月。

本文采用的研究数据为IMERG和GSMaP两种卫星降雨数据。根据处理过程的不同，IMERG分为Early、Late和Final3种产品。Final产品是用月度仪表数据创建的研究级(Level1\~3)数据，其精度优于Early产品和Late产品[26]。本文使用了NASA官网提供的精度较高的IMERGFinal。GSMaP生产了

# 干旱区地理

注：该图基于国家测绘地理信息局标准地图服务网站下载的审图号为GS(2019)3333号的标准地图制作，底图无修改。下同。

![](images/2f2810c6d67c26188204a9fcdc5efb1ce58007f2ab50b09d431245cb5f8f3451.jpg)  
图1陕西省地形及气象站点分布图  
Fig.1 Topography and distribution of meteorological stations in Shaanxi Province

GSMaP_NRT、GSMaP_MVK和GSMaP_Guage3种数据产品,GSMaP_Guage是GSMaP_MVK的继承,是在GSMaP_MVK的基础上经过全球30000多个CPC雨量站点数据校正后获得的1h尺度的高精度产品[27],本文使用了GSMaP_Guage产品,数据来源于JAXA官网。所使用的两种卫星降雨产品的参数见表1。

# 表1两种卫星降雨产品主要特征参数

Tab.1 Important characteristic parameters of the two satellite precipitation products   

<html><body><table><tr><td>卫星降雨 产品</td><td>时间 分辨率/h</td><td>空间 分辨率/()</td><td>覆盖 范围</td><td>数据 来源</td></tr><tr><td>IMERG</td><td>0.5</td><td>0.1</td><td>90°N~90°S</td><td>NASA</td></tr><tr><td>GSMaP</td><td>1.0</td><td>0.1</td><td>60°N~60°S</td><td>JAXA</td></tr></table></body></html>

本文对GPM的两种卫星降雨产品在多个时间尺度上进行误差评估，包括：年、季、月尺度和日尺度。其中，季节尺度的数据是由每3个月的数据累积而成，具体为：12月一翌年2月（冬季）、3—5月（春季）6—8月（夏季）、9—11月（秋季)。每年的降雨数据由12个月(12月一翌年11月）的数据累积

得到。

卫星降雨产品的格点数据表示该格网范围内的单位时间平均降雨量，单位是 $\mathrm { m m \cdot d ^ { - 1 } }$ （日产品）或$\mathbf { m } \mathbf { m } \cdot \mathbf { h } ^ { - 1 }$ （小时产品)；地面站点记录的是点位的单位时间降雨量，单位也是 $\mathrm { m m \cdot d ^ { - 1 } }$ 或 $\mathbf { m } \mathbf { m } \cdot \mathbf { h } ^ { - 1 }$ ,所以两者在单位上可直接匹配。在空间上，针对地面站点的经纬度确定其所对应的格网，由于所用站点较为稀疏，未出现一个格网中同时存在2个或多个站点的情况，故二者之间为一一对应的情况。文中所使用的卫星降雨产品数据与地面观测数据均由数据发布方进行了质量控制，且本文在使用地面数据之前进一步对其进行了检查，保证了数据的质量

# 2.2 研究方法

文章以地面站点数据为基准，对两种卫星降雨产品进行站点检验。为了对两种卫星降雨产品进行精度验证，本文选取相关系数（Correlationcoeffi-cient,CC）、均方根误差（Root mean squared error,RMSE)和相对偏差(Relativebias，BIAS)3个常用指标，利用所有降雨样本对卫星降雨产品性能进行定量评价。在年尺度，基于17个站点，共采用了85组样本；在月尺度，共采用了204组样本；在日尺度，则采用了479组样本计算这3个精度指标。CC可以衡量卫星降雨产品估测值与地面观测值之间的相关程度;BIAS用于衡量卫星降雨产品对于实测降雨值误差的平均趋势；RMSE反映了卫星降雨产品的整体误差水平和精度。其中，CC值越接近于1,其他2个指标的值越接近于0，则说明产品误差越小。各项指标的计算公式如下：

$$
\mathrm { C C } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( D _ { i } - \bar { D } ) ( W _ { i } - \bar { W } ) } { \displaystyle \sqrt { \sum _ { i = 1 } ^ { n } ( D _ { i } - \bar { D } ) ^ { 2 } } \times \sqrt { \sum _ { i = 1 } ^ { n } ( W _ { i } - \bar { W } ) ^ { 2 } } }
$$

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( W _ { i } - D _ { i } ) ^ { 2 } }
$$

$$
{ \mathrm { B I A S } } = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \left( W _ { i } - D _ { i } \right) } { \displaystyle \sum _ { i = 1 } ^ { n } D _ { i } } } \times 1 0 0 \%
$$

式中： $n$ 为样本数量； $D _ { i }$ 为地面观测降雨 $( \mathbf { \bar { \rho } } _ { \mathrm { m m } } )$ ； $\bar { D }$ 为地面观测降雨平均值 $( \mathrm { m m } )$ ； $\boldsymbol { W } _ { i }$ 为卫星降雨$( \mathbf { m } \mathbf { m } )$ ； $\bar { W }$ 为卫星降雨平均值 $\left( \mathrm { m m } \right)$ ）

分类统计指数可以衡量卫星降雨产品对地面降雨事件发生的监测能力，包括降雨误报率(Falsealarmratio,FAR）、命中率（Probabilityof de-tection,POD）和关键成功指数（Critical success in-dex,CSI)[28],其中,POD和CSI的最优值为1,FAR的最优值为0。各指数的计算公式如下：

$$
\mathrm { F A R } = { \frac { F } { H + F } }
$$

$$
\mathrm { P O D } { = } \frac { H } { H { + } M }
$$

$$
\mathrm { C S I } { = } \frac { H } { H { + } F { + } M }
$$

式中： $F$ 代表实际未发生而卫星观测到强降雨事件（卫星估测值 $\cdot \geqslant$ 阈值，地面观测值 $\leqslant$ 阈值)的次数； $H$ 代表强降雨事件被卫星正确观测到（地面观测值 $\geqslant$ 阈值，卫星估测值 $\geqslant$ 阈值)的次数; $M$ 代表卫星没有观测到而实际发生强降雨事件(地面观测值 $\geqslant$ 阈值，卫星估测值 $\leq$ 阈值)的次数。本研究以 $2 5 \mathrm { m m \cdot d ^ { - 1 } }$ 作为大雨事件的阈值[29-30],利用FAR、POD和CSI3个指标评价和对比两种卫星降雨产品对大雨及以上级别强降雨事件的监测能力。在所选的17个站点中共选取了66组满足大雨阈值条件的样本计算这些精度指标。

# 3结果与分析

# 3.1年尺度精度评估

由基于地面站点数据Kriging插值和基于IMERG、GSMaP得到的陕西省2014年12月—2019年11月期间5a平均的年降雨量空间分布(图2)可知，陕西省的年平均降雨呈现明显的南多北少的分布规律。与由站点观测数据插值得到的结果（图2a)相比，IMERG对年平均降雨量明显低估，而GSMaP对年平均降雨量明显高估。

在年尺度上，2014年12月—2019年11月IMERG和GSMaP两种产品相对于气象站点观测数据的评估指标表明(表2)，GSMaP和站点观测数据高度相关( $\scriptstyle \mathrm { C C = 0 . 8 9 }$ ），而IMERG和站点观测数据中度相关（ $\scriptstyle \mathrm { \backslash C C = 0 . 5 6 ) }$ 。GSMaP对年尺度的降雨有所高估（ $\mathrm { B I A S } { = } 1 3 . 6 0 \%$ ），而IMERG对年尺度的降雨有所低估 $\mathrm { \Delta B I A S { = } { - } 1 1 . 4 1 \% }$ )。综上，两种产品均能较好地反映陕西省的年降雨量，GSMaP优于IMERG。王思梦等[18]在黑河流域的研究中发现IMERG在年尺度上表现为低估地面实测降雨，这与本文结论相背。这可能是由于黑河流域属于干旱区，降雨量较小。而本文发现，卫星降雨产品的数据精度与降雨量有关，总体表现为雨量小时高估、雨量大时低估。因此，对于降雨量较小的黑河流域，IMERG对其降雨量有所低估。

# 3.2季节尺度精度评估

陕西省的降雨季节性变化特征明显，为了进一步分析IMERG和GSMaP的精度是否在季节上存在差异，有必要对卫星降雨数据在季节尺度上进行精度验证[19]。本文分别统计了陕西省在冬季、春季、夏季、秋季的降雨量(图3)，并比较了两种卫星降雨产品与地面观测值的CC、RMSE和BIAS3个评估指标(图4)。

IMERG和GSMaP的拟合优度均在秋季最高，决定系数 $\left( R ^ { 2 } \right)$ 均达到0.9以上，GSMaP在夏季的拟合优

![](images/3811b9febf1572ba636e0e64ad55320793491f7ffe6602a094f429c60b72c3e4.jpg)  
图22014—2019年陕西省年平均降雨量空间分布  
Fig.2 Spatial distribution of annual precipitation in Shaanxi Province from 2O14 to 2019

# 干旱区地理

# 表2两种卫星降雨产品相对于气象站点观测数据的年尺度精度评估指标

Tab.2 Annual scale accuracy evaluation indices of the two satellite precipitation productsrelative to meteorological stationobservation data   

<html><body><table><tr><td>卫星降雨 产品</td><td>相关系数 (CC)</td><td>均方根误差 (RMSE)/mm</td><td>相对偏差 (BIAS)/%</td></tr><tr><td>IMERG</td><td>0.56</td><td>77.69</td><td>-11.41</td></tr><tr><td>GSMaP</td><td>0.89</td><td>92.65</td><td>13.60</td></tr></table></body></html>

度最低（ $R ^ { 2 } { = } 0 . 3 6 8 1$ ),其他季节的拟合优度均较高，而IMERG在冬季的拟合优度最低（ $R ^ { 2 } { = } 0 . 2 3 3 8 \rangle$ ，在夏季的拟合优度也较低( $R ^ { 2 } { = } 0 . 4 1 1 7 ,$ )。另外，各条拟合曲线与1:1线之间的关系(图3)表明，卫星降雨产品在不同季节相对于观测站降雨量存在高估或低估，两种产品在春季和秋季对降雨均有高估现象，而在冬季和夏季对降雨有高估也有低估，这表明卫星降雨产品的精度可能与降雨量的大小关系密切，降雨强度较小时一般表现为高估，在降雨强度较大时则多为低估。

IMERG和GSMaP在季节尺度上均表现出较高的相关性(图4)，二者与地面观测数据的相关性在秋季最高，均在0.9以上；两种产品的BIAS则均在降雨最少的冬季最大，在夏季最小,这与汪梓彤等[31]在青藏高原对IMERG的多尺度精度评价中得到结论一致，说明两种产品均对夏季降雨的高低估程度较小，而对冬季的高估程度较大，且IMERG在夏季的BIAS为负值，说明IMERG对夏季的降雨有轻微的低估现象，而GSMaP的BIAS值大于O，说明GS-MaP对夏季的降雨有轻微的高估现象；两种产品的RMSE均在春季最大，在冬季最小，说明在冬季，卫星降雨产品数据距实测数据最稳定。两种卫星降

60 (a)冬季 y=0.8504x+12.476 300 (b)春季 y=1.1628x+15.49R²=0.7348 + R²=0.7462·40 .200 1.30 .y=0.3066x+22.815 150 1.0388x+14.00720 R²=0.2338 ·IMERG 100 R²=0.6917 ·IMERG10 ·GSMaP 50 ·GSMaP0 1 -1:1线 0 1:1线10 20 30 40 50 60 50 100 150 200 250观测站降雨量/mm 观测站降雨量/mmS (c)夏季 y=0.4426x+213.04 600R²=0.3681 . P /喜奥 500 (d)秋季 y=1.1017x+8.7495.. ：· 400 R²=0.9352y=0.5363x+163.2R: 1MER 30200100 j-00 SEG0 1:1线 0 -1:1线100 200 300 400 500 100 200 300 400 500观测站降雨量/mm 观测站降雨量/mm

1.2(a) ■IMERG ■GSMaP 14[(b) ■IMERG■GSMaP 40 (c）IMERGGSMaP1.0 264 3080.6 0.4 10 0200.2 2 00.0 0 -10春季夏季秋季冬季 全年 春季夏季秋季冬季 全年 春季夏季秋季 冬季 全年季节 季节 季节

Fig.4Accuracy evaluation indices of the two satelite precipitation products at seasonal scale in Shaanxi Province雨产品数据精度的表现不一，可能与陕西省降雨的时空分布有关，也可能是因为不同季节降雨温度和雷达反射率有不同的变化[32]，使卫星降雨产品的精度表现出明显的季节性差异。

# 3.3月尺度精度评估

IMERG和GSMaP两种卫星降雨产品在月尺度上相对于所有17个气象站点观测数据的评估指标(表3)表明，两种产品的数据和站点观测数据均呈现出较高的相关性。GSMaP的均方根误差相对较大。此外，两种数据的BIAS均大于0,反映了在月尺度上二者对降雨均存在高估。通过绘制的与地面观测数据的散点图(图5)可见，两种产品的估测值均展现了与地面观测值较强的一致性。此外，

# 表3两种卫星降雨产品相对于气象站点观测数据的月尺度精度评估指标

Tab.3 Accuracy evaluation indices of the two satellite precipitation products relative to the observation data of meteorological stations at monthly scale   

<html><body><table><tr><td>卫星降雨产品</td><td>CC</td><td>RMSE/mm</td><td>BIAS/%</td></tr><tr><td>IMERG</td><td>0.95</td><td>2.77</td><td>4.29</td></tr><tr><td>GSMaP</td><td>0.94</td><td>7.41</td><td>11.46</td></tr></table></body></html>

IMERG在降雨量小于 $1 0 0 ~ \mathrm { { m m } }$ 时对降雨主要呈现高估状态，在降雨量大于 $1 0 0 ~ \mathrm { { m m } }$ 时，对降雨主要呈低估状态（图5a)；GSMaP对降雨始终呈现高估状态(图5b)。综上可知，在月尺度上，两种产品与站点观测数据均比较接近，IMERG的表现相对更好。

# 3.4日尺度精度评估

通过雨季(6—9月)IMERG和GSMaP与观测站有效降雨事件（日降雨量 $\mathrm { > } 1 \ \mathrm { m m }$ )的散点图(图6)，结合两种卫星降雨产品的评估指标(表4)可以看出，GSMaP和地面观测数据的相关性更高，且RMSE和BIAS都更小，由此可知，日尺度降雨中GSMaP的数据精度比IMERG的高。两种产品的BIAS均呈现负值，表明在日尺度上二者对地面降雨均有所低估。IMERG和GSMaP均对大于 $4 0 ~ \mathrm { m m }$ 的日降雨量呈现明显的低估。

按照气象规定的降雨阈值，将降雨事件按日降雨量分为小雨 $( 0 . 1 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \leqslant$ 降雨量 ${ \bf \cdot } < 1 0 \mathrm { m m } { \bf \cdot } \mathrm { d } ^ { - 1 } ,$ 、中雨1 $1 0 \mathrm { m m \cdot d ^ { - 1 } } \leqslant$ 降雨量 $< 2 5 \mathrm { m m \cdot d } ^ { - 1 }$ 、大雨（ $2 5 \mathrm { m m \cdot d ^ { - 1 } } \leqslant$ 降雨量 $< 5 0 ~ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ）、大雨以上(降雨量 ${ \geqslant } 5 0 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ），以研究不同降雨强度下卫星降雨产品的误差特征。两种产品在4种不同降雨强度下的评估指数

300 300T/PRmm 250 (a)IMERG月尺度 E/雪 mm 250 (b) GSMaP月尺度 \~200 0 200 . .150 . 150 5 y=0.991x+7.9972100 0 8 y=0.9338x+7.0537 R²=0.911 100 R²=0.90150 曲线 50 二-曲线.0 L 上 ⊥ 0 上0 50 100 150 200 250 300 0 100 200 300观测站降雨量/mm 观测站降雨量/mm

120 120(a)IMERG日尺度有效降雨 (b)GSMaP日尺度有效降雨  
80 . 80  
60 60  
40 40  
20 拟合曲线 20 . -拟合曲线\ 1:1线 . . · 1:1线0 0 + 福0 20 40 60 80 100 120 0 20 40 60 80 100 120观测站降雨量/mm 观测站降雨量/mm

# 干旱区地理

# 表4两种卫星降雨产品降雨量观测相对于气象站点观测数据的日尺度精度评估指标

Tab.4 Accuracy evaluation indices of the two satellite precipitation products to the measured data of meteorological stations at daily scale   

<html><body><table><tr><td>卫星降雨产品</td><td>CC</td><td>RMSE/mm</td><td>BIAS/%</td></tr><tr><td>IMERG</td><td>0.50</td><td>3.75</td><td>-27.23</td></tr><tr><td>GSMaP</td><td>0.62</td><td>2.38</td><td>-17.27</td></tr></table></body></html>

(图7)表明，两种产品在小雨、中雨、大雨时相关性都很低，尤其在中雨时两种产品的相关性都最低，在大雨以上降雨时相关性较高；两种产品的RMSE均在小雨时达到最小值，同时其BIAS均大于0,且值最大，说明两种产品均在小雨时对降雨量高估严重，并且GSMaP对降雨量的高估程度比IMERG更大一些，而二者的BIAS在其他情况下均小于0,可以看出两种产品在降雨强度较大时对降雨存在低估，且IMERG的低估程度更大。以上结果表明，在陕西地区，GSMaP对降雨事件和降雨量的捕捉能力比IMERG更好。

# 3.5不同地区精度对比分析

为了量化日尺度下两种卫星降雨产品在陕西省不同地貌区的有效降雨的误差，统计了IMERG和GSMaP两种产品在陕西省内不同分区的评估指数(图8)，分析表明，两种产品在关中地区的相关性均较低，但是在关中地区的RMSE和BIAS均最小。

IMERG轻微高估关中地区的降雨而明显低估陕北和陕南地区的降雨，而 $\mathrm { G S M a P }$ 不同程度地低估了这3个地区的降雨，其中，对陕北地区的降雨低估现象最为严重 $\scriptstyle { \mathrm { : B I A S } } = - 2 7 . 1 6 \%$ )，其次是陕南地区（BI-${ \mathrm { A S } } { = } { - } 1 3 . 9 9 \%$ ），对关中地区的降雨低估程度最轻$\scriptstyle \left( { \mathrm { B I A S } } = - 1 . 4 8 \% \right)$ 。

以上分析表明，在日尺度降雨中，卫星降雨产品数据精度呈现出明显的地域差异，GSMaP对陕西省的降雨量总体表现为低估，尤其是对陕北地区的降雨低估最为明显；IMERG则是对陕北和陕南地区均有较为明显的低估。曾岁康等[14]、王思梦等[18]在四川地区和黑河流域的研究均发现IMERG对高海拔地区降雨表现出低估现象，这与本文研究结果一致。而两种卫星降雨产品在关中地区的表现与其他地区的表现差异较为明显，一方面，这可能是由地域导致的气候地貌等差异导致，另一方面，不同地区站点的数量可能也会造成一定的影响。总体来看，GSMaP的数据精度高于IMERG。

# 3.6强降雨事件观测精度对比分析

为了对比两种卫星降雨产品在监测强降雨事件时的表现力，以陕西省2017年4场暴雨事件（即2017年6月3—5日、7月25—27日、9月23—27日以及9月30日一10月4日)为例，分别使用卫星数据和地面观测数据进行了降雨过程分析。4场暴雨事件的发生地主要集中在陕北和陕南地区，2个地区在

0.[(a) ■IMERG ■IMERG 100 (c) ■IMERG8 ■GSMaP FT/HRRM ■GSMaP %/SAII 50 0 一 ■GSMaP0.30.2 -500.10.0 -100小雨 中雨__大雨大雨以上 小雨中雨大雨 大雨以上 小雨 中雨大雨大雨以上雨强 雨强 雨强

Fig.7Accuracy evaluation indices of the two satelite precipitation products at daily scale in Shaanxi Provin

![](images/7aee149abd15662f02727d8df97c01b03c05a446549ea5d6a35ccae9d371a80b.jpg)  
图7两种卫星降雨产品在陕西省内日尺度的精度评估指标  
图8两种卫星降雨产品在陕西省内不同地区的精度评估指标

Fig.8Accuracy evaluation indices oftwo kinds ofsatelite precipitation products in different areas of Shaanxi Province所统计的暴雨事件期间平均日降雨量均达到 $6 0 \mathrm { m m }$ 以上。IMERG统计的平均日降雨量为 $2 4 ~ \mathrm { m m }$ ,GS-Map统计的平均日降雨量为 $3 7 ~ \mathrm { m m }$ ,两种产品均对降雨量有所低估。图9为4场强降雨事件逐3小时降雨变化过程,其中横坐标均表示第 $n ( n { = } 0 , 1 , 2 , \cdots$ 24)个时间点，每次暴雨事件的起始统计时间为凌晨02:00，每隔 $3 \mathrm { { h } }$ 记为1个时间点，站点观测的降雨量数据是由日降雨量除以24得到的平均降雨量。IMERG和GSMaP对暴雨事件过程的描述比较一致，暴雨事件出现峰值节点的时间也基本相同，说明两种产品都可以较好地反映暴雨期间不同强弱的降雨阶段，相对于日降雨观测数据展现了更多的降雨日内波动细节，这对于开展更细时间尺度的降雨水文过程研究具有重要意义。不过两种产品对降雨量的捕捉仍有差异，尤其是在峰值处，二者的估计量相差最大。

为了比较两种产品对强降雨事件的总体捕捉能力，以 $2 5 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 为阀值，选择日降雨量在阈值以上的所有降雨事件，计算POD、FAR和CSI（表5）。结果表明，IMERG和GSMaP均在陕北地区表现出了低命中率(POD)和低关键成功指数(CSI)的情况，并且GSMaP在陕北的误报率(FAR)也最大，而IMERG在关中的误报率最大。另外，IMERG和GSMaP均在关中地区表现出高命中率，GSMaP的命中率在关中地区达到了0.80，误报率也最低，只有0.20，并且在关中地区的关键成功指数也最大，达到了0.67;IMERG在关中地区的误报率最小，为0.33,在陕南的关键成功指数最大，为0.54。据此推断，在不同地

![](images/d564f72b87e640f4618685a97454a9490b19707b5ff84ccf5c03a49231c89c35.jpg)  
图9暴雨期间降雨量变化过程  
Fig.9Variation process of precipitation during rainstorm

# 表5大雨及以上级别强降雨事件中两种卫星降雨产品在各地区的精度评价指标

Tab.5Accuracy evaluation indices of the two satelite precipitation products in each region inheavyandabove heavyrainfall events   

<html><body><table><tr><td>区域</td><td>卫星降雨产品</td><td>命中率(POD)</td><td>误报率(FAR)</td><td>关键成功指数(CSI)</td></tr><tr><td rowspan="2">陕北</td><td>IMERG</td><td>0.36</td><td>0.29</td><td>0.31</td></tr><tr><td>GSMaP</td><td>0.55</td><td>0.54</td><td>0.33</td></tr><tr><td rowspan="2">关中</td><td>IMERG</td><td>0.67</td><td>0.33</td><td>0.50</td></tr><tr><td>GSMaP</td><td>0.80</td><td>0.20</td><td>0.67</td></tr><tr><td rowspan="2">陕南</td><td>IMERG</td><td>0.64</td><td>0.22</td><td>0.54</td></tr><tr><td>GSMaP</td><td>0.72</td><td>0.35</td><td>0.52</td></tr></table></body></html>

貌区卫星降雨产品数据的精度有明显的差异性，IMERG和GSMaP均在关中的表现更好。

总体来看，IMERG和GSMaP在陕北对大雨及以上强降雨事件的监测情况最差，对关中地区的监测情况最好，并且GSMaP对大雨及以上强降雨事件的监测能力比IMERG强。

# 4结论

本文使用中国气象数据网获取的时间跨度为2014年12月一2019年11月的月值数据集和日值数据集作为地面基准数据，利用多种评价指标分别对IMERG和GSMaP两种卫星降雨产品在年、季、月尺度和日尺度上进行精度评价，并对陕北、关中和陕南3个区域进行区域差异性分析，得到如下结论：

（1）在年尺度上，GSMaP相较于IMERG表现出更高的精度。GSMaP总体表现为高估，而IMERG总体表现为低估。

（2）在季节尺度上，IMERG和GSMaP的估计精度在夏季更高。GSMaP在不同季节与地面观测站数据的相关性都比IMERG略高，但RMSE和BIAS偏大，反映其估计的降雨量与站点降雨量的趋势具有一致性，但波动性较大。

（3）在月尺度上，IMERG和GSMaP与观测数据的相关度都很高，且表现出一定程度的高估；年尺度和月尺度上，IMERG均比GSMaP对降雨量的估计更好。

（4）在日尺度降雨中，GSMaP的数据精度高于IMERG，但其数据精度均呈现出明显的地域差异，GSMaP对陕北地区的降雨呈明显低估，IMERG对陕北和陕南地区的低估程度都比较严重。

（5）对不同降雨强度下卫星降雨产品的误差特征的研究发现，卫星降雨产品的数据精度与降雨量有关。卫星降雨产品在降雨强度较小时一般表现为高估，在降雨强度较大时则多为低估。

(6）在陕西地区，GSMaP对降雨事件和降雨量的捕捉能力比IMERG好，IMERG和GSMaP对大雨及以上强降雨事件的监测能力在陕北地区最差，对关中和陕南地区的监测情况相对较好。

（7）通过在不同尺度对两种卫星降雨产品的精度进行对比和评价发现，IMERG和GSMaP均对陕北黄土高原区和陕南秦巴山地区的降雨量存在明显的低估，在对陕北地区强降雨事件的估计精度

不高。

卫星降雨产品在不同的地区呈现明显的精度差异，其精度受到气候、地形、传感器、降雨强度等因素的影响[33]。将来可以引入地形、气候等因素来对产品进行算法的改进和误差的订正[15]。本研究的结果可以为陕西省的气象水文研究在选择和使用降雨数据资料时提供参考。

# 参考文献(References)

[1]Skofronick-Jackson G,Kirschbaum D,Petersen W,et al.The global precipitation measurement (GPM) mission's scientific achievements and societal contributions:Reviewing four years of advanced rain and snow observations[J]. Quarterly Journal of the Royal Meteorological Society,2018,144(51): 27-48.   
[2]Shawky M, Moussa A, Hassan Q K,et al. Performance assessment of sub-daily and daily precipitation estimates derived from GPM and GSMaP productsover an arid environment[J].Remote Sensing, 2019,11(23): 2840, doi: 10.3390/rs11232840.   
[3]Kidd C.Satelite rainfall climatology:A review[J].International Journal of Climatology,2001,21(9): 1041-1066.   
[4]Testik F Y,Gebremichael M.Rainfall: State of the science[M]. United States: American Geophysical Union,2010:127-158.   
[5]Liu Z, Ostrenga D,Teng W,et al. Tropical rainfal measuring mission (TRMM) precipitation data and services for research and applications[J].Bulletin of the American Meteorological Society, 2012,93(9): 1317-1325.   
[6]Chen S,Hong Y,Cao Q,et al. Similarity and difference of the two successive V6 and V7 TRMM multisatelite precipitation analysis performance over China[J].Journal of Geophysical Research, 2013,118(23): 13060-13074.   
[7]唐国强,龙笛,万玮,等.全球水遥感技术及其应用研究的综述 与展望[J].中国科学:技术科学,2015,45(10):1013-1023. [Tang Guoqiang,Long Di,Wan Wei,et al.An overview and outlook of global water remote sensing technology and applications[J]. Scientia Sinica Technologica,2015,45(10):1013-1023.]   
[8]Tian Y,Peters-Lidard C D,Adler RF,et al. Evaluation of GSMaP precipitation estimates over the contiguous United States[J]. Journal of Hydrometeorology,2010,11(2): 566-574.   
[9]陈洪滨,尹红刚,何文英.星载主动微波遥感云和降水技术与应 用[M].北京:科学出版社,2020:30-31.[Chen Hongbin,Yin Honggang,He Wenying.Technology and application of satellite borne active microwave remote sensing of cloud and precipitation [M]. Beijing: Science Press,2020: 30-31.]   
[10] 李政,吴静,李纯斌,等.TRMM降水产品在中国草地的适用性 研究[J].中国草地学报,2020,42(6):75-81.[Li Zheng,Wu Jing, Li Chunbin,et al.Applicability study of TRMM precipitation products to China grassland[J]. Chinese Journal of Grassland,2020,42 (6): 75-81.]   
[11] Prakash S, Mitra A K,Pai D S,et al.From TRMM to GPM: How well can heavy rainfall be detected from space?[J].Advances in Water Resources,2016,88:1-7.   
[12]Guo H, Chen S, Bao A,et al. Early assessment of integrated multisatellite retrievals for global precipitation measurement over China [J].Atmospheric Research,2016,176-177: 121-133.   
[13] Hou A Y,KakarR K,Neeck S,et al. The global precipitation measurement mission[J]. Bulltin of the American Meteorological Society,2014,95(5): 701-722.   
[14]曾岁康,雍斌.全球降雨计划IMERG和GSMaP反演降雨在四川 地区的精度评估[J].地理学报,2019,74(7):1305-1318.[Zeng Suikang, Yong Bin.Evaluation of the GPM-based IMERG and GSMaP precipitation estimates over the Sichuan region[J]. Acta Geographica Sinica,2019,74(7): 1305-1318.]   
[15] Beria H,Nanda T, Bisht D S,etal. Does the GPM mission improve the systematic error component in satellite rainfall estimates over TRMM? An evaluation at a pan-India scale[J]. Hydrologyand Earth System Sciences Discussions,2017,21(12): 6117-6134.   
[16] Ning S, Song F,Parmeshwar U, et al. Error analysis and evaluation of the latest GSMap and IMERG precipitation products over eastern China[J]. Advances in Meteorology,2017(11): 1-16.   
[17]陈汉清,鹿德凯,周泽慧,等.GPM降雨产品评估研究综述[J] 水资源保护,2019,35(1):27-34.[Chen Hanqing,Lu Dekai, Zhou Zehui, et al. An overview of assessments on global precipitation measurement (GPM) precipitation products[J]. Water Resources Protection,2019,35(1): 27-34.]   
[18] 王思梦,王大钊,黄昌.GPM卫星降雨数据在黑河流域的适用 性评价[J].自然资源学报,2018,33(10):1847-1860.[Wang Simeng,Wang Dazhao,Huang Chang. Evaluating the applicability of GPM satelite precipitation data in Heihe River Basin[J]. Journal of Natural Resources,2018,33(10): 1847-1860.]   
[19] 李媛媛,宁少尉,丁伟,等.最新GPM降雨数据在黄河流域的精 度评估[J].国土资源遥感,2019,31(1):164-170.[Li Yuanyuan, Ning Shaowei,Ding Wei, et al. The evaluation of latest GPM-Era precipitation data in Yellow River Basin[J]. Remote Sensing for Land & Resources,2019,31(1): 164-170.]   
[20] 冯克鹏,洪阳,田军仓,等.多源降水数据的小流域水文模拟效 用评估[J].干旱区地理,2020,43(5):179-1191.[Feng Kepeng, Hong Yang,Tian Juncang,et al. Evaluating runoff simulation of multi-source precipitation data in small watersheds[J]. Arid Land Geography,2020,43(5): 1179-1191.]   
[21] 万相均,任志远,张.陕西省气温与降雨变化时空分布研究 [J].干旱区资源与环境,2013,27(6):140-147.[Wan Xiangjun, Ren Zhiyuan, Zhang Chong. Research on spatial-temporal distribution of temperature and precipitation changes in Shaanxi[J]. Journal of Arid Land Resources and Environment,2013,27(6): 140- 147.]   
[22] 任亮,王晓峰,曾昭昭.陕西秦巴山区TRMM 3B42卫星降水数 据精度评价[J].陕西师范大学学报(自然科学版),2017,45(1): 87-97. [Ren Liang, Wang Xiaofeng, Zeng Zhaozhao. The accuaracy evaluation of TRMM 3B42 precipitation data in Shaanxi Qinling-Daba Mountains[J]. Journal of Shaanxi Normal University (Natural Science Edition),2017,45(1): 87-97.]   
[23]曾昭昭,王晓峰,任亮.基于GWR模型的陕西秦巴山区TRMM 降水数据降尺度研究[J].干旱区地理,2017,40(1):26-36. [Zeng Zhaozhao,Wang Xiaofeng,Ren Liang. Spatial downscaling of TRMM rainfall data based on GWR model for Qinling-Daba Mountains in Shaanxi Province[J].Arid Land Geography,2O17,40(1): 26-36.]   
[24]刘政鸿.陕西省近50年来降雨量时空变化特征分析[J].水土保 持研究,2015,22(2):107-112.[Liu Zhenghong.Analysis of spatiotemporal variation characteristics of precipitation in the past five decades in Shaanxi Province[J]. Research of Soil and Water Conservation,2015,22(2): 107-112.]   
[25] 黄少妮,许新田,王丹.陕西降雨季节及季节内振荡的气候特征 [J].干旱气象,2014,32(1):46-51.[Huang Shaoni,Xu Xintian, Wang Dan. Climatological feature of seasonal and intraseasonal os cillation of rainfall in Shaanxi[J].Journal of Arid Meteorology, 2014, 32(1): 46-51. ]   
[26]Sungmin O,Foelsche U, Kirchengast G,et al.Evaluation of GPM IMERG early,late,and final rainfall estimates using WegenerNet gauge data in southeastern Austria[J]. Hydrology & Earth System Sciences Discussions,2017, 21: 6559-6572.   
[27] XieP,Akiyo Y, Chen M,etal. A gauge-based analysis ofdaily precipitation over East Asia[J]. Journal of Hydrometeorology,2007,8 (3): 607-626.   
[28]胡庆芳,杨大文,王银堂,等.赣江流域高分辨率卫星降雨数据 的精度特征与时空变化规律[J].中国科学:技术科学,2013,43 (4): 447-459.[Hu Qingfang,Yang Dawen,Wang Yintang, et al. Precision characteristics and temporal and spatial variation of highresolutionsateliterainfalldata in Ganjiang River Basin[J]. Scientia Sinica Technologica,2013,43(4): 447-459.]   
[29] 高玥,徐慧,刘国.GSMaP遥感降雨产品对典型极端降雨事件 监测能力评估[J].遥感技术与应用,2019,34(5):1121-1132. [Gao Yue,Xu Hui,Liu Guo. Evaluation of the GSMaP estimates on monitoring extreme precipitation events[J]. Remote Sensing Technology and Application,2019,34(5): 1121-1132.]   
[30] Tian YD,Peters-Lidard C D,Eylander JB,etal.Component analysis of errors in satellite-based precipitation estimates[J]. Journal of Geophysical Research,2009,114(D24): D011949,doi: 10.1029/ 2009JD011949.   
[31] 汪梓彤,李石宝,张志友.GPM近实时降水产品在青藏高原的 多尺度精度评价[J].人民黄河,2021,43(4):43-49,116.[Wang Zitong,Li Shibao, Zhang Zhiyou. Multi-scale accuracy evaluation of GPM precipitation products over the Qinghai-Tibet Plateau[J]. Yellow River,2021,43(4): 43-49,116.]   
[32] 李相虎,张奇,邵敏.基于TRMM数据的鄱阳湖流域降雨时空 分布特征及其精度评价[J].地理科学进展,2012,31(9):1164- 1170.[Li Xianghu, Zhang Qi, Shao Min. Spatio-temporal distribution of precipitation in Poyang Lake Basin based on TRMM data

# Accuracy assessment of GSMaP and IMERG satellite precipitation products in Shaanxi Province

LI Yanni'， HUANG Chang12， PANG Guowei1,2,3

(1.Shaanxi KeyLaboratoryof Earth Surface Systemand Environmental Capacity,Xi'an71Ol27,Shaanxi,China;   
2.InstituteofEarthSurface SystemandHazards,NorthwestUniversityXi'an7Ol27,haanxi,China;3.Laboratoyofon   
Ecological HydrologyandDisasterPreventioninAridRegions,StateForestryandGrasslandAdministration,Xi'an70127, Shaanxi, China)

Abstract: The Global Precipitation Measurement (GPM) mission is an international network of satellites that provide next-generation global observations of rain and snow. GPM was initiated by NASA and JAXA as a global successor to the Tropical Rainfall Measurement Mission (TRMM).In the GPMera, IMERG and GSMaP are two main satelite-based precipitation products. Compared with TRMM, GPM has wider coverage and higher spatiotemporal resolution.Understanding the accuracy and reliability of these products is important to further promote the application of new high-resolution satelite precipitationproducts.Therefore,this study intends to evaluateand compare the accuracy of IMERG and GSMaP in Shaanxi Province, China.In this paper,with surface precipitation observation datasets acquired from the China Meteorological Data Network used as reference,six evaluation indices,namely,correlation coefcient,root mean squared error,relative bias,false alarm ratio,probabilityof detection,and critical success index,were employed to evaluate and compare their accuracy at different temporal scales. Their performance in monitoring heavy rainfall events was also analyzed. Results show the folowing: (1) At an annual scale,the accuracy of GSMaP is higher than that of IMERG. GSMaP is highly correlated with the ground observation, while IMERG is moderately correlated with the ground observation. GSMaP overestimates the precipitation at an annual scale, whereas IMERG underestimates the precipitation. (2)At the seasonal scale, both data have the highest accuracy during summer. Overal, IMERG has a higher data accuracy than GSMaP. (3) At a monthly scale,the two products show a high correlation with the ground observation,but a certain degree of overestimation is observed. IMERG has a relatively higher accuracy than GSMaP.(4)At a daily scale,the accuracy of GSMaP is higher than that ofIMERG.(5)The accuracy of satelite precipitation products is related to total precipitation volume，which is generally overestimated when the precipitation volume is small and underestimated when the volume is large. (6) The accuracy of satelite precipitation product data shows obvious regional differences.GSMaP underestimates the precipitation in Shaanxi Provinceas a whole,especially in northern Shaanxi.IMERG slightly overestimates the precipitation in Guanzhong,but significantly underestimates the precipitation in northern and southern Shaanxi. （7)An analysis of four heavy precipitation events shows that the monitoring capability for heavy precipitation events of GSMap is slightly stronger than that of IMERG.This study is expected to provide a reference for the selection and application of precipitation data in meteorological and hydrological studies in this area.

Key words: satelite precipitation products； global precipitation observation plan (GPM)； heavy precipitation events；accuracy assessment