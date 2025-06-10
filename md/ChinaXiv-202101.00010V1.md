# 基于多光谱和地理加权回归模型的石嘴山城市土壤有机碳空间分布研究

夏子书1²，白一茹¹²，包维斌}²，钟艳霞¹，王幼奇1.2

（1宁夏大学资源环境学院,宁夏 银川750021;2旱区特色资源与环境治理教育部国际合作联合实验室,宁夏 银川 750021)

摘要：城市土壤有机碳(SOC)分布受城市建设、工业发展等人为因素的影响表现出明显的空间差异。为揭示石嘴山市SOC受城市化、工业化等人类活动的影响，分别利用普通克里格法(OK）、多元线性回归克里格法(RK)、遥感反演方法(RS)和遥感-地理加权回归克里格法(RGWRK)预测石嘴山市SOC空间分布。结果表明：石嘴山市SOC含量在 $1 . 3 1 \sim 6 6 . 9 2 ~ \mathrm { g \cdot k g ^ { - 1 } }$ 之间变化，其平均值为$1 7 . 6 1 \ \mathrm { g \cdot k g ^ { - 1 } }$ 。石嘴山市不同功能区SOC含量存在显著差异 $( \boldsymbol { p } < 0 . 0 5 )$ ，具体表现为工业区 $>$ 医疗区>商业区 $>$ 道路 $>$ 住宅区 $>$ 公园>农田 $>$ 科教区;SOC含量变异系数为 $6 6 . 2 7 \%$ ，呈中等程度变异；其最佳拟合模型为高斯模型， $C _ { 0 } / ( C _ { 0 } { + } C )$ 为0.02，属于强空间自相关。SOC与遥感影像波段 $D N$ 值的差值(B1-B7、B3-B7、B4-B7)和地形因子(高程、坡度、起伏度)之间存在着极显著的相关性 $( \boldsymbol { p } < 0 . 0 1 )$ ：通过对4种方法的结果进行对比可知以各波段DN值差值与地形因子为输入量,利用RGWRK预测的SOC精度最高，相比OK精度提高了 $1 0 . 0 5 \%$ ，相比RK精度提高了 $8 . 7 9 \%$ ，相比RS精度提高了$8 . 9 2 \%$ ；研究区SOC含量呈北高南低的趋势，工业区SOC含量是郊区农田SOC含量的1.92倍，表明城区SOC含量有富集的趋势。

关键词：城市土壤有机碳；空间预测；遥感反演；地理加权回归克里格文章编号：

土壤是参与地球与大气碳循环的陆地生态系统的重要组成部分，并对全球环境的稳定起着至关重要的作用[。其中城市土壤是一个巨大的碳库，其碳循环是全球碳循环的重要组成部分。随着工业发展和城市扩张，越来越多的自然和农业用地正逐步变为城市，这将对全球气候的变化和陆地生态系统的稳定产生深远的影响[2]。土壤有机碳(SOC)是土壤质量的核心，是土壤碳与大气 $\mathrm { C O } _ { 2 }$ 快速交换的主要形式[3]。在城市环境背景下，由于土地利用方式的改变和人类频繁的活动，使得城市SOC含量存在较大的空间变异性。因此，城市化进程中SOC含量和动态变化趋势的高效准确分析和预测，为城市土壤的管理、利用，公共卫生和城市环境的维护

提供了科学依据。

遥感技术是可以在短时间内对地面同一地区实现反复观测的一种新兴综合性勘探技术，同时可以获得大量的遥感影像数据，这些遥感影像记录了土壤的某些属性,在土地评价中应用广泛[4]。目前应用于多光谱遥感影像SOC的预测方法主要有多元线性回归[5]、最小二乘回归[等，这些方法在特定的研究区均取得了较好的效果。然而，这些方法忽略了SOC含量与光谱特征之间的空间异质性，即假定SOC含量在不同的空间位置上对光谱特征的影响是不变的。实际上，SOC含量受某一地区土壤类型、气候特征、地形特征等自然因素和城市扩张、煤矿开采、工业发展等人为因素的影响，使其分布具有一定的区域性和空间异质性[7]。近年来,由于地理加权回归(GWR)能够解释自变量和因变量之间的局部关系，因此受到越来越多的关注[8]。GWR是针对目标变量和解释变量之间回归系数的空间非平稳性而专门设计的，它利用局部数据局部地测量这些系数[9],对土壤属性空间分布的预测已取得一些成效，但将多光谱信息和GWR模型相结合预测SOC方面的研究较少，特别是关于西北旱区工业城市SOC的预测较为缺乏。

石嘴山市地处西北干旱半干旱区，生态环境极其脆弱，而其又是依托煤炭资源而发展起来的典型资源型老工业城市。从20世纪开始，国家就大规模开发石嘴山市的煤炭资源，截至2011年石嘴山市有煤、电、钢材、碳化硅、硅铁等高耗能、高污染企业300多家[10],三废排放量大，因此影响了全球气候变化和生态系统的稳定性，使得SOC含量存在较大的空间变异性。为此，本文以宁夏回族自治区石嘴山市城市SOC为研究对象，结合GWR模型与遥感反演方法，利用土壤样点实测数据、数字高程模型(DigitalElevationModel,DEM)数据和Landsat8多光谱数据，通过提取地形因子和波段亮度值(digitalnumber，DN），分析SOC的空间变异规律，并分别采用普通克里格法(OK）、多元线性回归克里格法(RK)、遥感反演方法(RS)和遥感-地理加权回归克里格法(RGWRK)对研究区SOC含量进行预测，确定研究区SOC空间分布最优预测方法，为城市土壤属性预测提供数据支持。

# 1研究区概况与数据来源

# 1.1 研究区概况

石嘴山市位于宁夏回族自治区最北端，地处宁东、蒙西两个国家千亿吨级煤田之间，以黄河为界，东临鄂尔多斯台地，西踞银川平原北部[10],地理坐标界于 $1 0 6 ^ { \circ } 1 6 ^ { \prime } \sim 1 0 6 ^ { \circ } 3 3 ^ { \prime }$ E, $3 8 ^ { \circ } 5 2 ^ { \prime } \sim 3 9 ^ { \circ } 0 5 ^ { \prime } ~ \mathrm { N } .$ 。气候干燥多风，年降水量 $1 8 0 \sim 1 9 0 ~ \mathrm { m m }$ ,蒸发量 $1 7 0 0 \sim$ $2 ~ 5 0 0 ~ \mathrm { m m }$ ，为典型的干旱半干旱气候,年平均气温$8 . 4 \sim 9 . 9 ~ \mathrm { ^ { \circ } C }$ ，年最低平均气温 $- 1 9 . 4 \sim - 2 3 . 2 \mathrm { ~ \textdegree C }$ ，年最高平均气温 $3 2 . 4 \sim 3 6 . 1 ~ \mathrm { ^ { \circ } C }$ 。随着"一带一路"战略的提出，石嘴山市成为宁夏内陆开放型经济试验区建设的核心区之一，但伴随着城市建设、工业、采矿等人为因素的影响，使石嘴山市城市SOC表现出异质性与多样性，从而影响着城市生态环境的稳定性。

# 1.2土壤样本采集及处理

2018年5月在研究样地内，将研究区按不同的土地利用方式划分为8大功能区：道路、公园、工业区、商业区、科教区、住宅区、农田和医疗区，通过手持式全球定位系统(GPS)定位，在石嘴山市范围内按照不同功能区随机选取151个样点，其中114个点用于方程拟合，37个点用于方程验证。取样深度为 $0 \sim 2 0 \ \mathrm { c m }$ 。样本带回实验室风干、研磨，过100目筛后进行SOC含量测定，采用重铬酸钾容量法一外加热法[]。研究区土壤样点分布如图1所示：

# 1.3影像数据及处理

Landsat8多光谱影像被用作土壤光谱信息的

![](images/42848b53c835c7d55f171322bb5bf42fe12fb6c53d70c2be8f0d4a5a710089ec.jpg)  
图1研究区土壤样点分布示意图  
Fig.1Distribution of sampling points in study area

# 干旱区地理

数据源，按照土壤裸露、云量较少、季节相似、影像年份邻近采样时间等原则，选取了2018年4月2日空间分辨率为 $3 0 \mathrm { ~ m ~ } \times 3 0 \mathrm { ~ m ~ }$ 的多光谱影像。通过ENVI5.3对影像进行辐射定标、大气校正等相关处理，使其最大程度地与采样点土壤属性的真实值接近。从遥感影像中所提取的数据为DN值，是传感器接收地物反射的能量转换后的结果。由于太阳高度角和大气条件会不可避免地影响地面辐射，导致地面的电磁波波谱发生畸变，为了消除这些因素的影响，需要对遥感图像进行辐射校正，才能得到反射率的真实值[12]。筛选出与SOC分布相关的波段,分析表层S0C含量与1\~7波段 $D N$ 值及DN值变换形式的相关关系[13.14],建立SOC含量的光谱预测模型。

# 1.4地形数据及处理

从地理空间数据云上下载分辨率为 $3 0 \mathrm { ~ m ~ }$ 的

DEM数据，利用ArcGIS空间分析工具，提取常用的地形因子：高程、坡度、坡向、坡度变率、地形起伏度（图2)，其中坡度变率是微分空间中坡度的坡度，剖面曲率的信息在一定程度上可以反映出来。地形起伏度是指某一特定区域的最高海拔和最低海拔之间的差异，它是一个宏观数据，用来描述区域的地形特征。

# 1.5 研究方法

RK是基于多元线性回归创建SOC与相关解释变量之间的关系，其预测结果由预测模型计算得出，对预测结果进行OK插值即为SOC的最终预测结果。

地理加权回归克里格法(GWRK)代替了RK法中的全局拟合，将其转换成GWR中的局部拟合，然后将插值点的局部适用性残差进行OK插值。为了更加清楚地理解GWRK法，先对GWR模型做以下

![](images/4c154b76b346c81c753a3d8de8c693b1e90f4e5c50e5bdd43ac7589759adbae8.jpg)  
图2研究区地形特征图  
Fig.2Terrain features of the study area

解释：

$$
Y _ { _ { G W R } } ( s _ { 0 } ) = \beta _ { 0 } ( s _ { 0 } ) + \sum _ { i = 1 } ^ { k } \beta _ { i } ( s _ { 0 } ) X _ { k } ( s _ { 0 } )
$$

式中： $Y _ { _ { G W R } } ( s _ { 0 } )$ 为因变量 $Y$ 在点 $s _ { 0 }$ 处的模拟值;$X _ { k } ( s _ { 0 } )$ 为第 $k$ 个自变量在点 $s _ { 0 }$ 处的测量值; $s _ { 0 }$ 为局部估计的系数，用加权最小二乘法求得，是空间位置的函数，其权重矩阵的估计采用高斯函数; $k$ 为自变量数目。

GWRK法是对GWR法的一种深入推广，即用OK法对GWR模型拟合后的残差进行插值，并增加了GWR法拟合的趋势，其表达式为：

$$
Y _ { _ { G W R K } } ( s _ { 0 } ) = \beta _ { 0 } ( s _ { 0 } ) + \sum _ { i = 1 } ^ { k } \beta _ { i } ( s _ { 0 } ) X _ { k } ( s _ { 0 } ) + \varepsilon ( s _ { 0 } )
$$

式中： $\varepsilon \textbf { ( } _ { s _ { 0 } } )$ 为GWR模型在点 $s _ { 0 }$ 处拟合后所得的残差，采用OK法进行插值。

RS是基于实验室对土壤光谱反射特性的研究，在少量地表数据测量中，分析遥感影像采样点光谱特征的变化，建立研究区土壤信息预测模型。大量前人研究表明SOC与光谱反射率存在显著的负相关关系[3，利用这种相关关系建立定量预测模型可以较准确模拟SOC含量。SOC遥感反演的精度受到多种因素影响，包括土壤其他理化性质、地形因素和大气因素等。首先，对实测SOC与利用影像DN值构建的指标进行相关性分析，得到与SOC显著或极显著相关的变量作为解释变量。其次，为避免数据的重复，假设SOC测量值为因变量，各波段DN值为建模样本的自变量，利用SPSS18.0软件，建立SOC含量的数据反演模型。

RGWRK是将多光谱遥感影像与GWRK方法相结合，使用遥感影像DN值与研究区地形因子来共同预测石嘴山市城市SOC含量。

# 1.6精度评价

随机生成的114个用于拟合的点参与所有分析过程，其余37个测试点用于验证空间插值结果和遥感反演结果。用验证点估计值和实测值的平均相对误差(MRE)和均方根误差(RMSE)评价不同方法对预测的准确性[15]

$$
M R E = \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } { \frac { \left| \hat { y } _ { i } - y _ { i } \right| } { y _ { i } } } }
$$

$$
R M S E = \sqrt { \frac { 1 } { n } { \sum _ { i = 1 } ^ { n } } \bigl ( \hat { y } _ { i } - y _ { i } \bigr ) ^ { 2 } }
$$

式中： $\hat { y } _ { i }$ 是在 $i$ 处 SOC含量的估计值， $y _ { i }$ 是在 $i$ 处

SOC含量的实测值， $n$ 为验证点个数，在本文中即$n { = } 3 7$ 。当MRE和RMSE接近于O时，插值精度较高。

以RMSE为指标，比较不同插值方法与参考方法的相对精度提高值 $( R I ) ^ { [ 1 6 ] }$ ,公式如下：

$$
R I = \frac { R M S E _ { \scriptscriptstyle R } - R M S E _ { \scriptscriptstyle K } } { R M S E _ { \scriptscriptstyle R } } \times 1 0 0 \%
$$

式中： $R M S E _ { _ R }$ 为参照方法的RMSE， $R M S E _ { \scriptscriptstyle K }$ 为其余方法的RMSE。

# 1.7数据处理

利用SPSS18.0软件对样本数据进行描述性统计和多元线性回归，并且进行Kolmogorov-Smirnov(K-S)检验，对数据进行OK插值的前提条件是其要符合正态分布[17]。在 $\mathrm { G S } { + } 7 . 0$ 软件中完成数据的半方差分析，在GWR4.0中完成GWR分析，用ArcGIS10.3软件分别对研究区的SOC进行OK插值、RK插值和RGWRK插值。

# 2结果与分析

# 2.1土壤有机碳描述性统计

由表1可知，不同功能区SOC含量大小表现为：工业区 $\mathrm { ( } 2 3 . 4 0 ~ \mathrm { g \cdot k g ^ { - 1 } } \mathrm { ) > }$ 医疗区 $\mathrm { ( 2 1 . 1 8 ~ g \cdot k g ^ { - 1 } ) > }$ 商业区（ $2 0 . 0 2 \ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 } ) >$ 道路 $( 1 9 . 2 9 \mathrm { g } \cdot \mathrm { k g } ^ { - 1 } ) >$ 住宅区( $\mathrm { 1 6 . 7 0 \ : g }$ $\mathrm { k g ^ { - 1 } } ) >$ 公园 $\mathrm { ( 1 3 . 8 7 ~ g \cdot k g ^ { - 1 } ) > }$ 农田( $\mathrm { 1 2 . 1 6 \ g \bullet \mathrm { k g } ^ { - 1 } \Sigma ) } \rangle$ >科教区 $( 1 1 . 1 4 \mathrm { g } \cdot \mathrm { k g } ^ { - 1 } )$ ),其中工业区是农田的1.92倍。不同功能区SOC含量与乌鲁木齐市[18]研究结果接近，但与开封市[9]、南京市[20]有一定的差异;由于各功能区的划分以及土壤的采样密度、计算单位有差异，使得不同城市不同功能区SOC空间分布特征不确定。变异系数的大小表示土壤属性空间变异性的大小，根据CV评价准则2，CV小于 $1 0 \%$ 时变异性较弱，CV大于 $100 \%$ 时变异性较强，位于二者之间的属于中等变异，本研究区各功能区SOC的CV在$3 3 . 9 0 \% \sim 7 6 . 7 5 \%$ 之间变化，均属于中等程度变异，说明在不同功能区SOC分布不均匀。各功能区SOC含量均通过K-S检验 $^ { 2 2 ] } ( p > 0 . 0 5 )$ ,符合正态分布。

对8个功能区SOC含量进行方差分析，结果表明不同功能区SOC存在显著差异 $( p < 0 . 0 5 )$ 。工业区与公园、科教区和农田存在显著差异 $( p < 0 . 0 5 )$ 。科教区与道路存在显著差异 $( p < 0 . 0 5 )$ 。医疗区与科教区和农田显著差异 $( p < 0 . 0 5 )$ 。说明土地利用格局是影响石嘴山市城市SOC空间分布的重要因素，也说明研究区SOC易受交通、城市建设和商业

# 干旱区地理

# 表1 SOC描述统计量

Tab.1 Descriptive statistics of SOC   

<html><body><table><tr><td>功能区</td><td>样点数</td><td>最小值 Min.</td><td>最大值 Max.</td><td>土壤有机碳 SOC</td><td>偏度 Skewness</td><td>峰度 Kurtosis</td><td>变异系数/% CV</td><td>K-S p值</td></tr><tr><td>道路</td><td>16</td><td>6.17</td><td>26.00</td><td>19.29±6.54abc</td><td>-0.55</td><td>-0.92</td><td>33.90</td><td>0.453</td></tr><tr><td>工业区</td><td>25</td><td>5.18</td><td>66.92</td><td>23.40±17.96a</td><td>1.32</td><td>0.73</td><td>76.75</td><td>0.065</td></tr><tr><td>商业区</td><td>6</td><td>4.00</td><td>26.29</td><td>20.02±8.47abcd</td><td>-1.78</td><td>3.12</td><td>42.31</td><td>0.789</td></tr><tr><td>医疗区</td><td>12</td><td>3.65</td><td>33.60</td><td>21.18±9.78ab</td><td>-0.35</td><td>-0.78</td><td>46.18</td><td>0.994</td></tr><tr><td>住宅区</td><td>15</td><td>3.73</td><td>34.24</td><td>16.70±9.43abcd</td><td>0.29</td><td>-0.72</td><td>56.47</td><td>0.996</td></tr><tr><td>公园</td><td>10</td><td>5.60</td><td>25.87</td><td>13.87±6.11bcd</td><td>0.67</td><td>0.56</td><td>44.05</td><td>0.764</td></tr><tr><td>科教区</td><td>14</td><td>1.31</td><td>26.78</td><td>11.14±8.01d</td><td>0.922</td><td>-0.05</td><td>71.90</td><td>0.856</td></tr><tr><td>农田</td><td>16</td><td>3.09</td><td>37.31</td><td>12.16±7.98cd</td><td>2.23</td><td>6.49</td><td>65.63</td><td>0.394</td></tr><tr><td>合计</td><td>114</td><td>1.31</td><td>66.92</td><td>17.61±11.67</td><td>1.67</td><td>4.28</td><td>66.27</td><td>0.068</td></tr></table></body></html>

注：土壤有机碳数据为平均值 $\dot { \bf { \varepsilon } } _ { \pm }$ 平均误差，不同功能区不同小写字母表示差异显著 $( p < 0 . 0 5 )$ 0

活动等人类活动影响，且在城市空间分布上存在较大差异。

# 2.2土壤有机碳空间变异特征分析

利用地统计学半方差理论分析SOC含量的空间变异结构。表2显示了4种模型对S0C半变异函数的模拟结果及交叉检验结果，根据各模型交叉验证结果，高斯模型的相关系数平方和 $\left( R ^ { 2 } = 0 . 6 9 4 \right)$ 最大，且回归系数标准误差( $S e = 0 . 6 8 7 \mathrm { ; }$ 和标准误差预测值 $( S e p = 0 . 0 9 7 )$ 在四个模型中最小。因此，该SOC含量的最佳拟合模型为高斯模型。高斯模型中基台值 $\left( C _ { 0 } { + } C \right)$ 为116.10,表示变量的最大变异程度。 $C _ { 0 } / ( C _ { 0 } { + } C )$ 反映了SOC的空间依赖性[23]。一般来说，比值 $< 0 . 2 5$ 时空间变异性表现为强空间相关性，介于 $0 . 2 5 \sim 0 . 7 5$ 时表现为中等强度空间相关性，比值 $> 0 . 7 5$ 时表现为弱空间相关性。变程表明了研究样本区域的相似程度，可作为确定环境因素之间距离的一种度量[24],变程越小,表明 SOC在空间上的相互作用距离越小；反之，变程越大，变量相互依存的空间距离就越大，即变异性越小，本研究SOC的变程为 $2 4 2 4 . 8 7 \mathrm { m }$ 。

# 2.3影像DN值、地形因子与土壤有机碳含量相关性分析

对研究区SOC分别与遥感图像各波段DN值、地形指标进行Pearson相关分析(表3)。由表3可以看出， $B 1 { - } B 7$ 与 $B 2 { - } B 7$ 之间 $D N$ 值的相关系数最高( ${ \bf \Phi } _ { r } = { \bf \Phi } _ { \bf { \Phi } }$ 0.993, $p < 0 . 0 1$ )；其次为 $B 2 { - } B 6$ 与 $B 3 / - B 6 ( r = 0 . 9 7 9$ $p < 0 . 0 1$ ），表明这些波段 $D N$ 值之间的重叠较多。SOC与各波段 $D N$ 值之差存在显著相关关系 $( p <$ 0.01)，其中1、2、3、4、5波段与6、7波段之差与SOC表现出极显著负相关 $( p < 0 . 0 1 )$ ，相关系数达到0.260及以上，其中 $B 4 { - } B 7$ 与SOC相关系数最高。同时，SOC 与高程呈极显著正相关关系 $( r = 0 . 3 2 1 , p <$ 0.01)，表明海拔越高，SOC含量越高。SOC与坡度也呈极显著正相关关系！ $( r = 0 . 3 4 6 , p < 0 . 0 1 )$ ,说明在一定范围内，坡度越大处，有机碳越容易富集。此外，SOC与地表起伏度的相关性也达到了显著正相关水平 $( r = 0 . 3 1 2 , p < 0 . 0 1$ ),反映了地形也会对SOC含量产生影响。

# 2.4土壤有机碳多元线性回归预测模型

逐步回归不仅可以保证与SOC显著相关的自变量进人回归模型，而且可以去除自变量之间的共线性[25]。本研究以遥感影像各波段DN值以及地形因子为自变量，对研究区SOC进行多元线性逐步回归分析，模型1如下：

表2SOC变异模型参数  
Tab.2 Semivariance parameters of SOC   

<html><body><table><tr><td></td><td>模型</td><td>块金值Co</td><td>基台值Co+C</td><td>变程A</td><td>Co/(Co+C)</td><td>决定系数R</td><td>标准误差Se</td><td>标准误差预测值 Sep</td></tr><tr><td rowspan="4">SOC</td><td>线性模型</td><td>95.08</td><td>123.82</td><td>11217.45</td><td>0.77</td><td>0.247</td><td>0.723</td><td>0.124</td></tr><tr><td>球状模型</td><td>43.00</td><td>116.00</td><td>2850.00</td><td>0.37</td><td>0.690</td><td>0.705</td><td>0.125</td></tr><tr><td>指数模型</td><td>54.70</td><td>116.00</td><td>2220.00</td><td>0.47</td><td>0.658</td><td>0.709</td><td>0.129</td></tr><tr><td>高斯模型</td><td>2.10</td><td>116.10</td><td>2424.87</td><td>0.02</td><td>0.694</td><td>0.687</td><td>0.097</td></tr></table></body></html>

Tab.3Correlation between SOC and the difference of DNand terrain factor   

<html><body><table><tr><td></td><td>SOC</td><td>B1-B7</td><td>B2-B6</td><td>B2-B7</td><td>B3-B6</td><td>B3-B7</td><td>B4-B6</td><td>B4-B7</td><td>B5-B6</td><td>高程</td><td>坡度</td><td>起伏度</td></tr><tr><td>SOC</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>B1-B7</td><td>-0.251**</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>B2-B6</td><td>-0.279**</td><td>0.967**</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>B2-B7</td><td>-0.281**</td><td>0.993**</td><td>0.973**</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>B3-B6</td><td>-0.266**</td><td>0.957**</td><td>0.979**</td><td>0.957**</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>B3-B7</td><td>-0.260**</td><td>0.966**</td><td>0.924**</td><td>0.966**</td><td>0.960**</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>B4-B6</td><td>-0.343**</td><td>0.890**</td><td>0.936**</td><td>0.912**</td><td>0.964**</td><td>0.925**</td><td>1</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>B4-B7</td><td>-0.349**</td><td>0.865**</td><td>0.840**</td><td>0.890**</td><td>0.887**</td><td>0.941**</td><td>0.942**</td><td>1</td><td></td><td></td><td></td><td></td></tr><tr><td>B5-B6</td><td>-0.312**</td><td>0.781**</td><td>0.727**</td><td>0.794**</td><td>0.763**</td><td>0.835**</td><td>0.760**</td><td>0.827**</td><td>1</td><td></td><td></td><td></td></tr><tr><td>高程</td><td>0.321**</td><td>-0.114</td><td>-0.136</td><td>-0.125</td><td>-0.138</td><td>-0.123</td><td>-0.184*</td><td>-0.175</td><td>-0.295**</td><td>1</td><td></td><td></td></tr><tr><td>坡度</td><td>0.346**</td><td>-0.145</td><td>-0.170</td><td>-0.154</td><td>-0.163</td><td>-0.139</td><td>-0.182</td><td>-0.154</td><td>-0.257**</td><td>0.736**</td><td>1</td><td></td></tr><tr><td>起伏度</td><td>0.312**</td><td>-0.139</td><td>-0.171</td><td>-0.147</td><td>-0.165</td><td>-0.132</td><td>-0.184</td><td>-0.147</td><td>-0.241**</td><td>0.747**</td><td>0.985**</td><td>1</td></tr></table></body></html>

注：Bi表示Landsat 8影像第i波段DN值,B-B表示第i与第j波段DN值之差；“表示在0.01水平上显著相关，表示在0.05水平上显著相关

$$
S O C = - 0 . 0 1 8 \times ( B 1 - B 7 ) + 0 . 0 4 7 \times ( B 3 - B 7 ) +
$$

$$
1 . 0 8 1 \times S l o p e - 0 . 0 4 0 \times \left( B 4 - B 7 \right) + 6 3 . 9 4 6
$$

式中：SOC为土壤有机碳含量; $B 1 { - } B 7$ 为波段1与波段 $7 D N$ 值差值； $B 3 { - } B 7$ 为波段3与波段 $7 D N$ 值差值； $B 4 { - } B 7$ 为波段4与波段 $7 D N$ 值差值;Slope为研究区坡度。

由模型可知，波段1、3、4和波段7的差值与地形因子坡度是研究区SOC多元线性回归分析的最佳辅助变量。回归模型的决定系数 $R ^ { 2 }$ 相对较低，仅为0.275。之前的研究中也多次出现过类似的结果，如张素梅等在预测农安县SOM分布时，回归方程的决定系数为0.220，刘焕军等26在预测东北典型黑土区田块土壤有机质进行逐步回归拟合时，回归方程的决定系数为0.341。在ArcGIS10.3中对通过多元线性回归模型得到的预测值进行 $O K$ 插值，得到最终预测结果，并进行精度验证。

# 2.5土壤有机碳遥感反演结果分析

利用SPSS软件对SOC含量与各波段 $D N$ 值进行多元线性逐步回归分析，构建得到模型2如下：

$$
S O C = - 0 . 0 2 1 \times { \left( { B 1 - B 7 } \right) } + 0 . 0 5 2 \times { \left( { B 3 - B 7 } \right) } -
$$

$$
0 . 0 4 3 \times { \left( { B 4 - B 7 } \right) } + 7 3 . 8 3 6
$$

式中： $s o c$ 为土壤有机碳含量; $B 1 { - } B 7$ 为波段1与波段 $7 D N$ 值差值； $B 3 { - } B 7$ 为波段3与波段7DN值差值； $B 4 { - } B 7$ 为波段4与波段7DN值差值。

根据模型可知，模型以 $( B 1 - B 7 ) \ 、 ( B 3 - B 7 ) \ 、 ( B 4 -$ $B 7 )$ 作为自变量，反演模型拟合效果较好。逐步回归方法可以消除数据之间的冗余，对于SOC含量的反演而言，用于建模各DN值差值之间存在着重复信息。回归方程的系数检验结果见表4,波段4与波段7的 $D N$ 值差值系数通过了统计学显著性检验 $( p <$ 0.001)，但波段1,3与波段7DN值差值的系数未通过检验， $p$ 值(0.003和0.029)较小，因此，在方程中仍保留了(B3-B7)和(B1-B7)。

表3SOC与DN值差值、地形因子的相关性分析结果  
表4回归方程系数的检验  
Tab.4 Test for coefficients of the regression equation   

<html><body><table><tr><td>系数</td><td>系数值</td><td>标准误差</td><td>t检验</td><td>概率</td></tr><tr><td>常数</td><td>73.836</td><td>12.917</td><td>5.716</td><td>P<0.001</td></tr><tr><td>B4-B7</td><td>-0.043</td><td>0.010</td><td>-4.261</td><td>P<0.001</td></tr><tr><td>B3-B7</td><td>0.052</td><td>0.017</td><td>3.042</td><td>P=0.003</td></tr><tr><td>B1-B7</td><td>-0.021</td><td>0.009</td><td>-2.216</td><td>P=0.029</td></tr></table></body></html>

# 2.6土壤有机碳遥感-地理加权回归克里格插值

GWR是针对目标变量和解释变量之间回归系数的空间非平稳性而专门设计的，它利用局部数据局部测量这些系数。与传统回归方法不同，GWR法在空间上不是全局的(无变化)，而是依赖于不同空间位置的。GWRK是一个混合技术，并且是GWR方法的延续。GWRK是由确定和随机两个部分组

# 干旱区地理

成，这两个部分分别建模。确定性的组成部分是由SOC来建模并且使用可用的相关变量信息来预测目标变量的趋势。随机的组成部分(残差)可以用OK插值，并添加到估计的趋势。残差被认为可能具有一些可以建模的空间相关结构，残差是模型的组成部分，不能够被确定性成分解释，但重要的是要补充，因为它能够帮助解释目标变量在空间上的变化。GWRK方法能够用于估计残差，从而更有效地预测趋势。为了方便比较，应用GWRK模型时，选取相同的波段信息(B1-B7）、（B3-B7）、（B4-B7)和地形因子高程、坡度、起伏度进行建模，通过使用GWR4.0软件来构建GWR模型,并通过MRE、RMSE和RI对其进行精度验证。

# 2.74种不同预测方法下土壤有机碳空间分布特征

采用四种方法分别对SOC含量的空间分布进行OK插值，得出SOC含量的空间分布图。从分布特征看，4种方法预测的SOC含量空间分布具有相似的格局，即研究区北部SOC含量要大于南部，高值区分布在正北和东南部。从制图效果看，OK法得到的图较为粗略，斑块非常零碎，不符合现实中SOC含量空间渐变的特征；RK法和RS法的插值结果体现了SOC含量随着各变量的变化情况，但是也有少部分斑块的边界较为零碎，且RS法预测出的SOC含量比起其他方法偏低；RGWRK法的SOC含量预测图在空间变化上表现为自然、平缓的过渡，有效避免了OK法和RK法图斑边界两侧的破碎程度大、突变明显的缺陷，还反映出SOC含量的空间渐变特征，斑块边界更为光滑，感官上更符合SOC含量的实际分布状况

# 2.8土壤有机碳预测方法精度比较

通过计算37个验证点的MRE、RMSE和RI,检验不同方法的预测精度。从表5中可知，引入地形因子和波段DN值差值的RGWRK法各项精度指标均优于OK法、RK法和RS法。分别以OK法、RK法和RS法作为参照，在预测SOC的精度上分别相对提高了 $1 0 . 0 5 \%$ ） $8 . 7 9 \%$ 和 $8 . 9 2 \%$ ,故RGWRK法是最适合本研究区的最优插值方法。

![](images/e2694c049a44a889960c06a338d70b143dd579aaf29be65ed4d2bbef3d625d6a.jpg)  
图34种方法空间插值结果图  
Fig.3Spatial distribution of $S O C$ by four methods

表5SOC的不同预测方法精度比较  
Tab.5Accuracy assessment of predicted SOC contents by using different methods   

<html><body><table><tr><td>预测方法</td><td>平均相对误差 MRE</td><td>均方根误差 RMSE</td><td>相对提高度/% RI</td><td>相对提高度/% RI</td><td>相对提高度/% RI</td></tr><tr><td>OK</td><td>0.517</td><td>19.694</td><td>一</td><td>一</td><td>1</td></tr><tr><td>RK</td><td>0.505</td><td>19.423</td><td>1.38</td><td>一</td><td>0.14</td></tr><tr><td>RS</td><td>0.507</td><td>19.451</td><td>1.23</td><td>1</td><td>1</td></tr><tr><td>RGWRK</td><td>0.412</td><td>17.715</td><td>10.05</td><td>8.79</td><td>8.92</td></tr></table></body></html>

# 3讨论

通过对石嘴山市城市不同功能区SOC含量特征分析显示，城市SOC含量与人为活动密切相关，石嘴山市表层SOC平均含量为 $1 7 . 6 1 \ \mathrm { g \cdot k g ^ { - 1 } }$ ,属于中等水平,与开封市[19] $( 1 9 . 1 0 \mathrm { g } \cdot \mathrm { k g } ^ { - 1 } )$ ）、南京市[20]（16.29$\mathbf { g } \cdot \mathbf { k } \mathbf { g } ^ { - 1 }$ )等城市含量相近,略高于上海市 $^ { [ 2 8 ] } ( 1 1 . 9 1 \ \mathrm { g }$ $\mathbf { k g } ^ { - 1 } .$ ）、杭州市 $^ { [ 2 9 ] } ( 1 3 . 9 4 ~ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 } )$ )等东部城市，明显低于乌鲁木齐市[18 $^ { 1 } ( 3 3 . 0 5 \ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 } )$ 。罗上华[30]对北京市绿地土壤碳氮的研究表明，城市化与工业化加快了城市土壤碳库的累积。石嘴山市现处于城市化发展时期，人口数量不断增长，道路、城市建筑不断施工，使得石嘴山市城市SOC含量有不同程度的富集。从分布特征看，研究区北部的SOC含量要大于南部，结合采样点的功能区分区可知北部和东南部是石嘴山市工业园区，工业区的SOC含量较高，而南部是农田，其SOC含量较低。研究区SOC呈现不规则分布与其土地利用方式和人类活动有着密切关系，其中工厂排放的“三废"物质成为影响石嘴山市SOC的主要原因之一，同时影响着城市碳循环与生态系统的稳定。与乌鲁木齐市[18]、北京市[30]、南京市[20]、开封市[19]、上海市[28]、杭州市[29]研究结果相一致。

OK法是目前土壤属性空间插值最具代表性的方法。该方法利用采样点的结构特点，给出了插值结果的估计误差，但没有考虑土壤属性与环境因素的密切联系，且插值精度取决于采样密度等因素，因此在环境复杂的地区适应性较差。基于权函数灵活变化的GWR模型，克服了回归模型中不同空间位置的环境因子权重一致的不足，实现了局部空间信息的捕获，并将OK法对残差信息的充分利用相结合，提高了插值精度。MISHRA等人3将GWR与RK法进行比较，利用一些地形属性、气候数据、土地利用数据和NDVI数据作为解释变量，预测美国中西部7个州的SOC空间分布，他们发现，GWR在捕捉变异性和提高准确性方面略优于RK法。而众多学者研究发现SOC含量和土壤反射率高低有明显关系[32]，本文利用RGWRK法预测的石嘴山城市SOC含量的精度最高，最符合实际情况。因此，利用多光谱遥感影像与GWR模型相结合的方法预测城市SOC是一次有益尝试。同时影响城市SOC含量预测结果准确性的因素很多，如区域差异、土壤水分、气候因素以及遥感影像的空间分辨率等。后续研究应当从多方面考虑影响SOC变化的因素，寻找相关的土壤光谱特征参数，如反射率的数学变换形式、波段组合等，可以提高遥感监测SOC变化的精度。

# 4结论

以宁夏石嘴山市各功能区为研究区，以裸土期Landsat8影像和 $3 0 \mathrm { ~ m ~ }$ 分辨率DEM影像为基础数据，利用地统计方法和RS法对研究区SOC进行预测，得出以下结论：

(1)石嘴山市SOC空间变异系数为 $6 6 . 2 7 \%$ ，呈中等变异水平,SOC含量范围为 $1 . 3 1 \sim 6 6 . 9 2 ~ \mathrm { g \cdot k g } ^ { - 1 }$ ，变化较广，不同功能区SOC含量差异显著，表现为：工业区 $>$ 医疗区 $\cdot >$ 商业区 $>$ 道路 $\cdot >$ 住宅区 $>$ 公园 $>$ 农田>科教区。

(2)根据地形因子与SOC相关性分析可知，地形变化和遥感影像波段信息同时影响着研究区SOC含量的空间分布。相较于纯粹的遥感波段信息，对波段DN值进行数学变换得到的数据与SOC相关性更强。

(3)通过对4种方法的精度进行比较，引入地形因子和波段DN值差值的RGWRK法MRE和RMSE均为最低。分别以OK法、RK法和RS法作为参照，在预测SOC的精度上分别相对提高了 $1 0 . 0 5 \%$ 、$8 . 7 9 \%$ 和 $8 . 9 2 \%$ ,故RGWRK法是最适合本研究区的最优插值方法。

# 参考文献(References)

[1] 赵明松,李德成,张甘霖,等.1980-2010年安徽省土壤有机碳 密度及储量时空变化分析[J].地理研究,2018,37(11):84-95. [ZHAO Mingsong,LI Decheng,ZHANG Ganlin, et al. Spatial-temporal change of soil organic carbon density and storage in Anhui Province from 1980 to 2010[J]. Geographical Research,2018,37 (11): 84-95.]   
[2] XIE R,WU XIUQIN.Effects of grazing intensity on soil organic carbon of rangelands in Xilin Gol League,Inner Mongolia,China [J].Acta Geographica Sinica,2016,26(11): 1550-1560.   
[3] 徐丽，于贵瑞,何念鹏.1980s-2010s中国陆地生态系统土壤碳 储量的变化[J].地理学报,2018,73(11):102-119.[XULi,YU

# 干旱区地理

Guirui,HE Nianpeng.Changes of soil organic carbon storage in Chinese terrestrial ecosystems from the 198Os to the $2 0 1 0 \mathrm { s } [ \mathrm { J } ]$ . Acta Geographica Sinica,2018,73(11): 102-119.]   
[4]张晓东,刘湘南,赵志鹏,等.农牧交错区生态环境质量遥感动 态监测——以宁夏盐池为例[J].干旱区地理,2017,40(5): 1070-1078.[ZHANG Xiaodong, LIU Xiangnan,ZHAO Zhipeng, et al.Dynamic monitoring of ecology and environment in the agro一 pastral ecotone based on remote sensing: A case of Yanchi County inNingxiaHuiAutonomousRegion[J].AridLand Geography, 2017,40(5): 1070-1078.]   
[5]赵锐锋,张丽华,赵海莉.黑河中游湿地土壤有机碳分布特征及 其影响因素[J].地理科学,2013,33(3):363-370.[ZHAO Ruifeng, ZHANG Lihua, ZHAO Haili.Distribution of soil organic carbon of wetlands in the middle reaches of the Heihe River and its influencing factors[J]. Scientia Geographica Sinica,2O13,33(3): 363-370.]   
[6]杨爱霞,丁建丽.新疆艾比湖湿地土壤有机碳含量的光谱测定 方法对比[J].农业工程学报,2015,31(18):162-168.[YANG Aixia,DING Jianli. Comparative assessment of two methods for estimation of soil organic carbon content by Vis-NIR spectra in Xinjiang Ebinur Lake Wetland[J]. Transactions of the Chinese Society of Agricultural Engineering,2015,31(18): 162-168.]   
[7]任广琦,贾小旭,贾玉华,等.黄土高原南北样带土壤有机碳空 间变异及其影响因素[J].干旱区研究,2018,35(3):524-531. [REN Guangqi, JIA Xiaoxu, JIA Yuhua, et al. Spatial variation of soil organic carbon content and its driving factors along southnorth transect in the Loess Plateau of China[J].Arid Zone Research,2018,35(3): 524-531.]   
[8]SONG XD,B.D.J.,Liu F,et al. Mapping Soil Organic Carbon Content by Geographically Weighted Regression. Geoderma,2016, 261: 11-22.   
[9]Ye H, HUANG W,HUANG S,et al Effects of DiferentSampling Densities on Geographically Weighted Regression Kriging for Predicting Soil Organic Carbon.Spatial Statistics,2017,20: 76-91.   
[10] 樊新刚,米文宝,马振宁,等.宁夏石嘴山河滨工业园区表层土 壤重金属污染的时空特征[J].环境科学,2013,34(5):1887- 1894.[FAN Xingang,MI Wenbao,MA Zhenning,etal.Spatial and temporal characteristics of heavy metal concentration of surface soil in hebin industrial park in Shizuishan Northwest China [J]. Environmental Science,2013,34(5): 1887-1894.]   
[11]鲍士旦.土壤农化分析[M].北京:中国农业出版社,2007,[BAO Shidan.Soil agricultural chemistry analysis[M]. Beijing: China Agricultural Press,2007.]   
[12] 许宝泉,梁长利,蔡定建,等.祖历河流域自然草地生产力遥感 反演[J].干旱区研究,2014,31(6): 1147-1152.[XU Baoquan,LIANG Changli,CAI Dingjian,et al. Inversion of natural grassland productivity from remote sensor imagery in Zulihe River Basin[J]. Arid Zone Research,2014,31(6): 1147-1152.]   
[13] 周倩倩,丁建丽,唐梦迎,等.干旱区典型绿洲土壤有机质的反 演及影响因素研究[J].土壤学报,2018,55(2):313-324.[ZHOU Qianqian,DING Jianli,TANG Mengying,YANG Bin. Inversion of soil organic matter content in oasis typical of arid area and its influencing factors[J].Acta Pedologica Sinica,2018,55(2): 313- 324.]   
[14] 刘焕军,潘越,窦欣,等.黑土区田块尺度土壤有机质含量遥感 反演模型[J].农业工程学报,2018,34(1):127-133.[LIU Huanjun,PAN Yue,DOU Xin,et al. Soil organic matter content inversion model with remote sensing image in field scale of blacksoil Area[J]. Transactions of the Chinese Society of Agricultural Engineering,2018,34(1): 127-133.]   
[15] ZENG C, YANG L, ZHU A X,et al. Mapping soil organic matter concentration at diffrent scales using a mixed geographically weighted regression method. Geoderma,2016,281(281): 69-82.   
[16] 陈实,高超,徐斌,等.新疆石河子农区土壤含盐量定量反演及 其空间格局分析[J].地理研究,2014,33(11):2135-2144. [CHEN Shi, GAO Chao,XU Bin, et al. Quantitative inversion of soil salinity and analysis of its spatial pattern in agricultural area in Shihezi of Xinjiang[J]. Geographical Research,2014,33(11): 2135-2144. ]   
[17]王幼奇,白一茹,赵云鹏.宁夏砂田小尺度土壤性质空间变异特 征与肥力评价[J].中国农业科学,2016,49(23):4566-4575. [WANG Youqi, BAI Yiru, ZHAO Yunpeng. Assessment of soil fertility and its spatial variability based on small scale in the gravel mulched field of Ningxia[J]. Scientia Agricultura Sinica,2016,49 (23): 4566-4575.]   
[18] 张小萌,李艳红,王盼盼.乌鲁木齐城市土壤有机碳空间变异研 究[J].干旱区资源与环境,2016,30(2):117-121.[ZHANG Xiaomeng,LI Yanhong,WANG Panpan.Analysis of spatial variability of soil organic carbon in Urumqi[J]. Journal of Arid Land Resources and Environment, 2016,30(2): 117-121.]   
[19]孙艳丽,马建华,李灿.开封市不同功能区城市土壤有机碳含量 与密度分析[J].地理科学,2010,20(1):124-128.[SUN Yanli, MA Jianhua,LI Can. Contents and densities of soil organic Ccarboninurbansoil in diferent function districtsof Kaifeng[J]. Journal of Geographical Sciences,2010,20(1): 124-128.]   
[20]何跃,张甘霖.城市土壤有机碳和黑碳的含量特征与来源分析 [J].土壤通报,2006,43(2):177-182.[HE Yue,ZHANG Ganlin. Concentration and sources of organic Carbon and black carbon of urban soils in Nanjing[J].Acta Pedologica Sinica,2006,43(2): 177-182.]   
[21]ZHANG S,HUANG Y,SHEN C,et al. Spatial prediction of soil organic matter using terrain indices and categorical variables as auxiliary information. geoderma,2012,171-172(2): 35-43.   
[22]JUSTEL A,PENA D, ZAMAR R,A multivariate kolmogorovsmirnov test of goodness of fit[J].Statistics&ProbabilityLeters, 1997, 35(3): 251-259.   
[23] 刘迁迁,苏里坦,刘广明,等.伊犁河谷察南灌区土壤盐分空间 变异研究[J].干旱区研究,2017,34(5): 980-985.[LIU Qianqian, SU Litan,LIU Guangming,et al.Spatial variation of soil salinity in the chanan irrigated area in the ili River Valley[J]. Arid Zone Research,2017,34(5): 980-985.]   
[24]Cambardella,C.A., T.B. Moorman,J.M. Novak,et al. Field-scale Variability of Soil Properties in Central Iowa Soils.Soil science Society of America Journal,1994,58(5): 1501-1511.   
[25] 王涛,喻彩丽,姚娜,等.MLR和PLSR的沙壤土盐分含量光谱 检测比研空干旱区18416)：105_13m

[WANG Tao,YU Caili,YAO Na,et al.A comparison of the salt content in sandy soil between the MLR model and PLSR model[J]. Arid Land Geography,2018,41(6): 1295-1302.]   
[26]张新乐,窦欣,谢雅慧，等.引入时相信息的耕地土壤有机质遥 感反演模型[J].农业工程学报,2018,34(4):143-150.[ZHANG Xinle,DOU Xin,XIE Yahui,et al. Remote sensing inversion model of soil organic matter in farmland by introducing temporal information[J].Transactions of the Chinese Society of Agricultural Engineering,2018,34(4): 143-150.]   
[27]王秋兵,段迎秋,魏忠义,等.沈阳市城市土壤有机碳空间变异 特征研究[J].土壤通报,2009,40(2): 252-257.[WANG Qiubing, DUAN Yingqiu,WEI Zhongyi,et al. Spatial varibility of urban soil organic carbon in Shenyang City[J].Acta Pedologica Sinica, 2009,40(2): 252-257.]   
[28]柳云龙,章立佳,施振香,等.上海城市样带土壤有机碳空间变 异性研究[J].长江流域资源与环境,2011,20(12):1488-1494. [LIUYunlong,HANG Lijia,SHI Zhenxiang,et al.Research on spatial variability of soil organic carbon content in the urban-transect of Shanghai[J].Resources and Environment in the Yangtze

Basin,2011,20(12): 1488-1494.]

[29] 章明奎,周翠.杭州市城市土壤有机碳的积累和特性[J].土壤通 报,2006,37(1):19-21.[ZHANG Mingkui, ZHOU Cui.Characterization of organic matter accumulated in urban soils in the Hangzhou City[J].Acta Pedologica Sinica,2006,37(1): 19-21.] [30] 罗上华,毛齐正,马克明.北京城市绿地表层土壤碳氮分布特征 [J].生态学报,2014,34(20):6011-6019.[LUO Shanghua,MAO Qizheng,MA Keming. Spatial distribution of soil carbon and nitrogen in urban greenspace of Beijing[J]. Acta Ecologica Sinica,   
2014,34(20): 6011-6019.] [31]Mishra,U.,R.Lal,D.S.Liu, et al.Predicting the spatial variation of the soil organic carbon pool at a regional scale. Soil Science Society of America Journal,2010,74(3): 906-914. [32]刘焕军,张柏,刘殿伟,等.基于反射率模拟模型的黑土有机质 含量估测[J].光谱学与光谱分析,2008,28(12):2947-2950. [LIU Huanjun,ZHANG Bai,LIU Dianwei,et al. Black soil organic matter content prediction based on reflectance simulation models[J]. Spectrosocopy and Spectral Analysis,2008,28(12): 2947-   
2950.]

# Spatial distribution of soil organic carbon in Shizuishan based on multispectral and geographically weighted regression model

XIA Zi-shul², BAI Yi-rul²， BAO Wei-bin1²， ZHONG Yan-xia’， WANG You-qi',2 (1Collegeoforcndnviront,ngiaUnversitycan,ngia,ia;2Aridceistic Resources and Environmental Governance Department ofEducation International Cooperation Joint Laboratory, Yinchuan 75oo21,Ningxia,China)

Abstract: The distribution of soil organic carbon (SOC)in urban areas is influenced by human factors such as urban constructionand industrialization,and thus shows obvious spatial differences.To reveal the impactof human activities suchas urbanizationand industrializationon SOC in Shizuishan City,the spatial distributionofSOC in Shizuishan was predicted using ordinary Kriging (OK), multiple linear regression Kriging (RK),remote sensing inversion (RS),and remote sensing-geographically weighted regression Kriging (RGWRK). The SOC content changed from $1 . 3 1 ~ \mathrm { g / k g }$ to $6 6 . 9 2 ~ \mathrm { g \cdot k g ^ { - 1 } }$ , with an average of $1 7 . 6 1 ~ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 }$ ，There were significant differences in SOC content among different functional areas in Shizuishan $( p < 0 . 0 5 )$ .Specifically,the performance in decreasing order was,industrial areas,medical areas,commercial areas,roads,residential areas,parks,farmlands,scientificandeducational areas. The coefficient of variation of SOC content was $6 6 . 2 7 \%$ and there was moderate variation. The best fitting model was the Gauss model,and $\mathrm { C _ { 0 } / ( C _ { 0 } + C ) }$ was O.O2,indicatingstrong spatial autocorrelation. There was a significant correlation $( p < 0 . 0 1 )$ between SOC and differences of $D N$ values in different bands of RS images (B1-B7, B3- $B 7$ ，and $B 4 { - } B 7$ ） and topographic factors (elevation,slope,and relief amplitude). Comparing the results of the four methods demonstrated that SOC predicted by RGWRK was the most accurate,being $1 0 . 0 5 \%$ higher than that of OK, $8 . 7 9 \%$ higher than that of RK,and $8 . 9 2 \%$ higher than that of RS.SOC content in the northern part of Shizuishan was higherthan the southern part.The SOC content in industrial areas was1.92 times higher than farmlands,indicating that the SOC content in the urban area was enriched.

Key words: soil organic carbon; spatial prediction; remote sensing inversion; geographically weighted regression Kriging