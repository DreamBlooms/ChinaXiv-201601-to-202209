# GPM卫星降水数据的降尺度研究以陕西省为例

温伯清'，刘戎²，庞国伟¹，张泉1(1.西北大学,陕西 西安710127；2.中国电子科技集团公司第二十研究所,陕西 西安710000)

摘要：以陕西省内2019年33个地面气象观测站点的测量数据为真实值，选取相关系数(CC）、均方根误差（RMSE)以及相对误差(BIAS)等多种统计分析指标对GPM(Global precipitation measure-ment)卫星降水数据进行精度验证，并引入地形因子作为空间参考要素，基于地理加权回归模型(GWR)对GPM降水数据进行降尺度研究。结果表明：（1）在年际尺度上，GPM降水数据与实测降水数据之间有着明显的相关性，相关性较好( $\operatorname { C C = } 0 . 8 9$ ），相对误差则较低(BIAS=-0.45)；(2）在季节尺度上，春、夏两季GPM降水数据的降尺度结果与实测降水数据之间的CC值分别为0.92和0.80，而秋季则为0.93;(3)降尺度降水量结果与高程呈现出明显的负相关性，随着海拔升高，降水相对减少。总体而言，GWR降尺度降水数据在陕西省内有着较好的精度，能够较为准确地反映陕西省内的降水分布。

关键词：GPM；降水；降尺度；地理加权回归模型(GWR)

# 文章编号：

降水不断地影响着全球的水热循环与人类的生产和生活，研究降水对区域水循环以及水资源管理、经济发展以及区域的生态环境治理有着重要意义。目前，由于降水具有高时空变异性,获取降水数据的传统方法即地面气象观测站，难以准确反映降水的时空分布规律。卫星遥感和地理信息技术的快速发展提供了新的降水探测方法，涌现了大量基于卫星遥感的降水观测产品，其中包括美国气象预测中心研发的降水产品（ClimatePrecipitationCenterMORPHingMethod,CMORPH）、使用人工神经网络算法对遥感数据进行估算的高分辨率降水产品PERSIANN(Precipitation estimation from remote-ly sensed information using artificial neural network）、GSMaP[3](（Global satellite mapping of precipitation）以及TRMM[4]（Tropical rainfall measuring mission）等产品，这些降水产品提供了连续的时空降水信息，为研究区域降水以及水文模拟等研究提供了有力的数据支持[5]。 $\mathrm { G P M } ^ { [ 6 ] }$ (Global precipitation measurement)是新一代降水观测卫星，具有更高的时空分辨率，并增强了对微量和固态降水的探测能力[7],更进一步的地提升了卫星降水的探测精度，IMERG(Integratedmulti-satelliteretrievals,IMERG)是GPM的三级产品，为高空间分辨率的水文研究提供了新的数据源。但是在水文研究过程中，GPM降水数据仍然存在限制，粗糙的分辨率难以满足高精度水文研究需求[8-9]。高时空分辨率的降水数据,有助于推进区域降水的时空变异特征研究[10]。因此,对GPM降水数据进行降尺度研究具有重要的现实意义。

空间降尺度方法可以进一步提高数据质量，其中地理加权回归模型（Geographically weighted re-gression,GWR)已广泛应用于地理科学领域[8.1-14] O基于GWR模型进行降水降尺度，可以获取较高空间分辨率的降水数据，使降水估计的空间尺度更精细化，对区域水文、水资源管理有着重要意义。胡实等[15构建实滞GWR模型对GPM降水数据进行降尺度研究，研究表明降尺度后的数据优于原始数据，该方法对研究空间降水精细化具有一定的参考意义;Immerzeel等[16]、Duan等[17]和李净等[18]在低空间分辨率下建立TRMM卫星降水和归一化差异植被指数(Normalized difference vegetation index,NDVI)的指数函数关系，并进行降尺度，结果表明降尺度结果展现出更多的降水细节信息；Jia等引入与降水相关的NDVI和数字高程模型（Digitalelevationmodel,DEM)空间变量，对TRMM3B43数据进行降尺度，对柴达木盆地卫星降水的空间分辨率提升至$1 ~ \mathrm { k m }$ ;以上研究多集中在对TRMM卫星的降尺度分析上。对于GPM卫星降尺度的研究较少，大多主要关注的是GPM卫星数据的适用性研究，金晓龙等[19]基于天山山区数据对GPM适用性进行验证，研究发现GPM能够准确的反映降水分布；董国涛等2在黄河流域对TRMM和GPM数据进行评估，结果表明GPM数据精度优于TRMM;Zhan等[21]基于GWR降尺度对横断山区的GPM数据进行降尺度处理，结果表明GWR降尺度结果比原GPM降水更加准确，但是目前GPM降尺度在其他地区仍然缺乏研究验证。

陕西省地处我国中西部地区，受秦岭和黄土高原阻挡，区域内气候差异显著[22],研究陕西省降水时空格局有着重要意义。因此，本文以陕西省为研究区域，以地面气象观测站点降水数据为真实值，从年的时间尺度和站点的空间尺度上验证GPM降水数据的精度，并采用GWR模型对GPM进行降尺度，与实测降水数据进行对比验证。同时，在年降水量数据降尺度方法的基础上，进一步进行月尺度拓展，获取更高分辨率的GPM月降水数据，并结合DEM数据分析地形对卫星降水产品精度的影响程度。

# 1 研究区、数据与方法

# 1.1 研究区概况

陕西省位于中国西北部的东南段，地处 $1 0 5 ^ { \circ } 2 9 ^ { \prime }$ ，$1 1 1 ^ { \circ } 1 5 ^ { \prime } \mathrm { E } , 3 1 ^ { \circ } 4 2 ^ { \prime } { \sim } 3 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { N }$ ,全省面积 $2 . 0 5 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ 地势南北高、中间低(图1)，北部是陕北黄土高原，中部是关中平原，南部是秦巴山地，且陕西省南北气候差异较大,气候类型的分布从北到南依次为温带亚干旱季风气候、暖温带亚干旱湿润季风气候和亚热带湿润季风气候[23]。年降水量的分布由南向北递减，受到山地影响明显。陕西省主要干旱季节是冬、春季和秋、冬季，雨季是夏、秋季，北部和南部夏季常发生暴雨天气，因此对陕西省降水进行监测研究，具有重要意义。

![](images/439cdbc69ea72b4560f40e863ed8c42af5f594840d78ce76997cca595df97104.jpg)  
图1陕西省地形与气象站点分布  
Fig.1 Terrain and distribution of meteorological stations in Shaanxi Province

# 1.2数据来源

本文使用的GPM数据为GPMVesion04的IMERG月降水产品，数据覆盖全球，空间分辨率 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ P数据记录的是每个月的平均每小时降水量！ $\mathrm { ( m m \cdot h ^ { - 1 } }$ ，数据格式为HDF5。该数据集结合了所有微波传感器、地球同步卫星以及地面站点的月降水信息，数据于NASA(https://pmm.nasa.gov/precipitation-measu-rement-missions)上获取。

本文使用的地面观测资料来源于中国气象数据网(http://data.cma.cn/)的逐日数据集,将其作为真值检验降水数据，时段为2019年1—12月，33个气象站点的空间分布如图1所示。DEM数据来自于黑河计划数据管理中心（http://westdc.westgis.ac.cn）,空间分辨率是 $1 ~ \mathrm { k m }$ ，用于GWR模型降尺度分析。

# 1.3 研究方法

本研究对GPMIMERG降水数据及降尺度后GPMIMERG数据进行检验的评价指标主要包括皮尔逊相关系数（Correlationcoefficient,CC），相对误差（Relativebias,BIAS)和均方根误差(Root meansquareerror,RMSE)。其计算公式如下：

$$
\mathrm { C C } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( x _ { i } - \bar { x } ) ( y _ { i } - \bar { y } ) } { \sqrt { \displaystyle \sum _ { i = 1 } ^ { n } ( { { { x } _ { i } } - \bar { x } } ) ^ { 2 } } \sqrt { \displaystyle \sum _ { i = 1 } ^ { n } ( { { { y } _ { i } } - \bar { y } } ) ^ { 2 } } }
$$

$$
{ \mathrm { B I A S } } = { \frac { { \frac { 1 } { n } } { \underset { i = 0 } { \sum _ { i = 0 } ^ { n } } } ( x _ { i } - y _ { i } ) } { \displaystyle { \sum _ { i = 0 } ^ { n } } y _ { i } } } \times 1 0 0 \%
$$

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 } }
$$

式中： $n$ 为站点个数； $i$ 为降水数据中的第 $i$ 个数据; $x _ { i }$   
为卫星产品的降水估计值； $y _ { i }$ 为地面实测的降水； $\bar { x }$   
为卫星降雨平均值; $\bar { y }$ 为地面降水平均值。

为了进一步对比实测站点降水和GPM降水数据的匹配状况，采用线性判断系数 $R ^ { 2 }$ 来评价GPM降水量与站点观测值的线性拟合优度，计算公式如下：

$$
R ^ { 2 } = \frac { \displaystyle \sum _ { j = 1 } ^ { n } \left( { \hat { Y } } - { \bar { y } } \right) ^ { 2 } } { \displaystyle \sum _ { j = 1 } ^ { n } \left( y _ { j } - { \bar { y } } \right) ^ { 2 } }
$$

式中： $\hat { Y }$ 为线性拟合值; $\bar { y }$ 表示观测平均值; $y _ { j }$ 表示观测值； $n$ 表示对比记录的总数; $R ^ { 2 }$ 越接近于1,表明数据拟合度越好。

1.3.1地理加权回归模型（GWR）GWR模型由Chris等[24提出，是空间数据分析中常用的统计方法之一，基本思想是通过估算研究区内每一给定位置的相关变量与解释变量的参数建立回归模型[1]。以往的研究证明，高程是影响降水分布的重要因素[25],因此，本文引入高程作为降尺度过程中影响降雨的因子，建立GWR模型进行降尺度处理，公式如下：

$$
y _ { i } = \beta _ { 0 i } ( u ) + \beta _ { 1 i } ( u ) x _ { 1 i } + \varepsilon _ { i } ( u )
$$

式中： $y _ { i }$ 是第 $i$ 个点的降水量; $x _ { 1 i }$ 是第 $i$ 个点的DEM值； $\beta _ { i }$ 是相应的系数项; $\boldsymbol { u }$ 是某一个空间坐标; $\ \varepsilon _ { i }$ 是残差； $i { = } 1 , \cdots , n$ ，表示样本点的个数。

1.3.2降尺度方法本文通过GWR模型，对GPM降水数据进行降尺度操作：将DEM数据重采样至与GPM数据相同的分辨率；同时将 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ 分辨率下的GPM数据和DEM数据作为输入要素，构建GWR模型，从回归模型中提取每一个栅格中心点对应的常数项、DEM系数项以及残差；对常数项和系数项进行栅格化，得到 $1 ~ \mathrm { k m }$ 的数据，并运用普通克里金法将残差插值到 $1 ~ \mathrm { k m } { \times } 1 ~ \mathrm { k m }$ 空间分辨率；根据上述公式(5)计算得到空间分辨率为 $1 ~ \mathrm { k m }$ 的GPM降水数据。

# 2结果与分析

# 2.1GPM降水数据精度验证

在进行降尺度研究之前，保证尺度一致性的情况下，利用气象站点的实测降水数据对GPM降水数据进行精度验证。以研究区33个气象站点的年观测数据为自变量，其对应的年尺度的GPM降水数据为因变量，进行线性回归分析，对陕西省的GPM年降水数据进行精度验证(图2)。

注：CC、RMSE、BIAS分别表示相关系数、均方根误差、相对误差。

![](images/58b6351b311e43ffe92009b3268c3069989f78f6517ba8a99c88e31538a1dc0e.jpg)  
图2GPM卫星降水精度验证  
Fig.2 Validation of annual GPM precipitation

图2可知，GPM卫星数据对陕西省的实测年降水数据拟合度较好，具有明显的相关性和一致性$( R ^ { 2 } { = } 0 . 7 8 )$ )。GPM年降水量与实测降水量的相关系数较好( $\operatorname { C C = } 0 . 8 9$ )，但是相关系数只能反映数据之间的联系情况，无法客观表现出实测降水数据和GPM卫星降水数据之间的差异程度，因此进一步通过计算相对误差(BIAS)以及均方根误差(RMSE），发现GPM月降水数据存在一定的低估降水现象1 $\mathrm { B I A S } { = } { - } 0 . 4 5$ ）。

# 2.2站点精度验证

为了进一步验证GPM卫星降水数据的精度，利用陕西省内33个实测降水站点数据与GPM卫星降水数据进行统计分析，对单个站点的结果进行评估，各气象站点的误差统计情况如表1所示。

通过表1分析发现，陕西省大部分站点的GPM

# 表133个气象站点的GPM年降水量数据与实测年降水数据的统计指标

from 33 meteorological stations年降水与实测年降水量的相关系数均较好( $\mathrm { C C > }$ 0.90），说明陕西省内GPM卫星降水数据与地面实测降水数据有着较好的一致性，数据精度整体较好。但是在各气象站点之间的BIAS具有不均匀性，其中榆林、定边、镇巴、留坝、长武、佛坪、宁强、商南和镇坪站点的BIAS ${ < } 0$ ，说明在这些地区的GPM卫星降水数据存在低估降水的现象；其他站点的BI-$\mathrm { A S } { > } 0$ ，说明GPM降水数据存在一定程度的高估降

Tab.1 Statistical indexes of annual GPM precipitation data and measured annual precipitation data   

<html><body><table><tr><td colspan="4">irom33meteorologicalstations</td></tr><tr><td>气象站点</td><td>相关系数(CC）</td><td>均方根误差(RMSE)</td><td>相对误差(BIAS）</td></tr><tr><td>安康</td><td>0.93</td><td>81.17</td><td>20.15</td></tr><tr><td>榆林</td><td>0.96</td><td>47.53</td><td>-6.12</td></tr><tr><td>神木</td><td>0.96</td><td>42.63</td><td>13.36</td></tr><tr><td>吴旗</td><td>0.98</td><td>38.91</td><td>6.59</td></tr><tr><td>横山</td><td>0.96</td><td>37.86</td><td>3.44</td></tr><tr><td>定边</td><td>0.91</td><td>29.23</td><td>-14.13</td></tr><tr><td>绥德</td><td>0.94</td><td>42.40</td><td>33.57</td></tr><tr><td>延长</td><td>0.95</td><td>46.18</td><td>57.21</td></tr><tr><td>靖边</td><td>0.94</td><td>35.73</td><td>25.47</td></tr><tr><td>蒲城</td><td>0.96</td><td>45.61</td><td>18.76</td></tr><tr><td>太白</td><td>0.93</td><td>59.77</td><td>11.99</td></tr><tr><td>华山</td><td>0.88</td><td>51.91</td><td>22.94</td></tr><tr><td>汉中</td><td>0.94</td><td>71.67</td><td>2.53</td></tr><tr><td>镇安</td><td>0.91</td><td>68.32</td><td>9.41</td></tr><tr><td>镇巴</td><td>0.96</td><td>92.08</td><td>-10.12</td></tr><tr><td>长武</td><td>0.94</td><td>50.93</td><td>-4.21</td></tr><tr><td>洛川</td><td>0.82</td><td>50.94</td><td>19.71</td></tr><tr><td>铜川</td><td>0.97</td><td>43.71</td><td>25.02</td></tr><tr><td>宝鸡</td><td>0.97</td><td>54.46</td><td>1.88</td></tr><tr><td>凤翔</td><td>0.96</td><td>51.68</td><td>22.30</td></tr><tr><td>永寿</td><td>0.97</td><td>44.82</td><td>10.68</td></tr><tr><td>武功</td><td>0.92</td><td>52.78</td><td>17.64</td></tr><tr><td>耀县</td><td>0.93</td><td>42.42</td><td>37.10</td></tr><tr><td>留坝</td><td>0.96</td><td>64.94</td><td>-3.31</td></tr><tr><td>略阳</td><td>0.93</td><td>65.61</td><td>14.01</td></tr><tr><td>秦都</td><td>0.96</td><td>53.03</td><td>46.26</td></tr><tr><td>泾河</td><td>0.94</td><td>52.03</td><td>49.91</td></tr><tr><td>佛坪</td><td>0.95</td><td>98.17</td><td>-25.91</td></tr><tr><td>商州</td><td>0.91</td><td>53.03</td><td>6.30</td></tr><tr><td>石泉</td><td>0.91</td><td>91.97</td><td>5.67</td></tr><tr><td>宁强</td><td>0.90</td><td>85.62</td><td>-7.24</td></tr><tr><td>商南</td><td>0.96</td><td>53.69</td><td>-2.46</td></tr><tr><td>镇坪</td><td>0.96</td><td>61.90</td><td>-7.43</td></tr></table></body></html>

水的现象。

由图1中气象站点的地理位置可知，在海拔低的地区相对海拔高的地区误差更小一些。总体而言，气象站点的GPM降水数据与实测降水数据的误差较小，其结果能够满足区域水文应用的需求。基于此，采用GPM降水数据进行降尺度模拟实测降水有一定科学性。

# 2.3GWR降尺度结果与验证

2.3.1年降水数据降尺度结果对GPM年际数据进行降尺度，图3为 $0 . 1 ^ { \circ } \mathrm { G P M }$ 降水数据、 $. 1 \ \mathrm { k m \ G W R }$ 降尺度降水、 $1 \ \mathrm { k m \ G W R }$ 模型预测降水数据以及$1 ~ \mathrm { k m }$ 残差数据。研究发现，经过GWR降尺度计算后，降尺度空间分辨率得到提升，达到 $1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ 分辨率，能够表现出更为细致的空间降水特征；GPM年降水范围为 $3 3 8 . 8 2 { \sim } 1 2 6 0 . 8 4 ~ \mathrm { m m }$ ,经过降尺度后，降水范围有所减少，降水高值依然在南部的秦巴山区，但是GWR降尺度降水数据的可靠性，还需要进一步验证。

![](images/0faf503fb7d617bb83d8ec40575c5343c88e96026e60b8a110bb3bc190410b3c.jpg)  
图3GPM降水、GWR降尺度降水、GWR模型预测降水数据及残差值分布  
Fig.3Distributions of the annual GPM precipitation, GWR downscaling precipitation,predictive precipitation of GWR mode,and the residual

2.3.2年降水降尺度结果验证为了验证降尺度结果精度，利用研究区33个地面气象观测数据站点提取降尺度结果，分别计算均方根误差(RMSE）相关系数(CC)和相对误差(BIAS)3个评价指标，对降尺

# 干旱区地理

度结果进行精度验证，图4为GWR年际降尺度结果与实测降水数据的精度检验。

![](images/e475fd2d41dd3cd323af076f5a9ddb5d5e726af4f40672d1f98eb2d07a2ce04f.jpg)  
图4GPM年降水降尺度精度验证 Fig.4Validation of downscaling results of annual GPM precipitation

与GPM数据相比，GWR年际降尺度结果提高了决定系数（ $\scriptstyle ( R ^ { 2 } = 0 . 8 1$ ），相关系数（ $\scriptstyle \mathrm { C C = 0 . 9 0 } )$ 与均方根误差（ $\mathrm { R M S E } { = } 2 5 2 . 8 2$ )基本保持不变，说明GPM降水数据的系统误差和相关程度并没有随着GWR降尺度过程而降低，仍然保持了原有的精度水平。相对误差（ $\scriptstyle \mathrm { , B I A S = - 0 . 4 5 }$ 略有下降，降尺度结果的准确性得到提高，结果能够较好的反映真实降水，说明在年尺度上，利用地形因子对降水量进行降尺度模拟具有一定的科学性。但是GWR降尺度结果在提升空间分辨率的同时，牺牲掉了一部分的数据精度[26-28],需要进一步在月尺度上进行验证。

2.3.3季节降水降尺度结果与验证陕西省内降水的季节性差异较为明显，为进一步分析不同季节对降尺度结果的影响，本文对GPM卫星降水数据进行了季节尺度上的精度验证。为了保证年际数据的一致性（文章主要研究2019年的降水数据，但2019年的冬季包括了2018年的1月和2月），在本研究中对冬季暂不做考虑。将2019年的降水量按春季（3—5月）、夏季(6—8月）、秋季(9—11月)进行叠加，得到季度降水数据，并对均方根误差（RMSE）、相关系数(CC)和相对误差(BIAS)3个统计量进行比较(表2）。分析发现，秋季的相关性最高( $\operatorname { C C } =$ 0.93），夏季的相关性最低（ $\scriptstyle \mathrm { ~ \sum C C = 0 . 8 0 ~ }$ )；夏季具有最大的均方根误差 $( \mathrm { R M S E } { = } 1 1 5 . 0 6 )$ ）

表2GPM季节降水降尺度结果验证  
Tab.2 Validation of downscaling results of seasonalGPMprecipitation   

<html><body><table><tr><td>气象站点</td><td>相关系数(CC)</td><td>均方根误差(RMSE)</td><td>相对误差(BIAS)</td></tr><tr><td>春</td><td>0.92</td><td>97.78</td><td>0.08</td></tr><tr><td>夏</td><td>0.80</td><td>115.06</td><td>0.316024</td></tr><tr><td>秋</td><td>0.93</td><td>0.00</td><td>0.077821</td></tr></table></body></html>

对比陕西省季节降尺度降水量的空间分布（图5)，发现3个季节的降水量自南向北逐渐减小，并且差异性较为显著，秦岭以南地区降水量明显高于北部黄土高原地区降水量。同时可以看出，降水量最大的区域都集中在秦岭以南地区，夏季降水量最大可达 $6 4 4 . 9 5 ~ \mathrm { m m }$ ,秋季最大降水量为 $5 1 2 . 0 2 ~ \mathrm { m m }$ ，春季最大降水量为 $2 9 0 . 1 8 ~ \mathrm { m m }$ ○

2.3.4月降水降尺度结果与验证在GPM年降水量数据降尺度的基础上，进一步进行降尺度方法的月时间尺度探究。应用比例系数法[29],获取2019年内各月的降尺度降水数据，对陕西省内33个实测降水观测站点2019年逐月进行散点趋势分析(图6)。观察发现， $R ^ { 2 }$ 值大部分介于 $0 . 4 6 { \sim } 0 . 7 6$ 之间， $R ^ { 2 }$ 值越小，表明降水越少，这与已有的降水研究规律相符合[30]。从降尺度结果与实测降水数据线性拟合度

![](images/236d17ff0b0e64235163892ff1232285ca9c7034c0b30614632f4ca8254a5756.jpg)  
图5季节降尺度降水结果的空间分布  
Fig.5Spatial distribution of seasonal downscaling precipitation

C/自 20 (a)1月 / 40 (b)2月 C/ 60 (c)3月   
16 ■   
28 ， y=0.57x+4.16 3020 R01 40 =0.70x+73.40 ■ ■   
40 RMS534 10 Y BMSE=1.93 200 RMAE-122   
■ 1 1 10 20 30 0 10 20 30 0 20 40 60 80   
实测月降水量 $/ \mathrm { m m }$ 实测月降水量 $/ \mathrm { m m }$ （204号 实测月降水量 $/ \mathrm { m m }$   
(d)4月 /鲁 150 (e)5月 / 200 (f)6月 1 ■ 150 -   
100 火 山 y=0.61x+25.45 正 100 1 y=0.81x+19.09 茶 y=0.77x+31.34   
茶 R²=0.73 ■ R²=0.68 100 R²=0.73   
50 ? 专 ■ RMSE=23.99 CC=0.86 50 RMSE=32.65 CC=0.83 GERE 50 T □ RMSE=56.70 CC=0.86   
0 ■ BIAS=0.11 0 BIAS=0.55 0 BIAS=0.09   
50 100 150 200 50 100 150 200 100 200 300   
实测月降水量 $/ \mathrm { m m }$ 实测月降水量 $/ \mathrm { m m }$ （204号 实测月降水量 $/ \mathrm { m m }$ （204号   
（g）7月 (h)8月 (i)9月 ■ ■   
200 L   
■   
150 ■ 150 气 y=0.57x+56.62 y=0.47x+64.44 Y   
10500 10050 R 100 1   
100 200 300 400 100 200 300 50 100 150200 250   
实测月降水量/mm 实测月降水量 $/ \mathrm { m m }$ （204号 实测月降水量 $/ \mathrm { m m }$ （204   
(j)10月 /m 40 (k)11月 C/ 15 (1)12月 □   
150 100 ? □ y=0.84x+27.48 RME-405 R²=0.75 20 1 ■ =0.32x+15.85 RMAE=1.046 CC=0.43 10 5 = 1 ■ BIAS=-0.72 y=0.47x+1.94 R²=0.46 RMSE=2.96 CC=0.67   
50 7 ■   
A 0 L 0 L v   
50 100150 200 250 20 40 60 0 10 20   
实测月降水量/mm 实测月降水量/mm 实测月降水量/mm

来看，线性拟合优度较好的是3一6月，相关系数在0.83以上。从月尺度的相对误差来看，误差与原始GPM低误差基本保持一致，说明与实测降水数据更为接近，且空间分辨率变得更高。此外，影响月降尺度数据精度最主要原因是卫星降水数据的不均匀性,导致了时空尺度的不匹配[31]；二是由于月降尺度结果存在误差。

# 2.4陕西省降水的空间分布

为了分析流域内的卫星降水数据相对于地面观测数据误差的空间分布规律，本文通过对实测年降水数据进行插值[32],得到了年降水的空间分布图（图7a)，分析降尺度前后GPM降水数据在空间分布上的差异。

由图可知，经过GWR空间降尺度后的GPM卫星降水数据在空间分辨率方面有了很大的提高，具有更强的空间分布信息细节刻画能力，降水数据边缘变得平滑，在一定程度上，可以反映出陕西省降水的时空分布规律。实测降水数据、GWR降尺度降水数据以及GPM卫星降水数据具有相似的空间分布特征，降水量从南到北递减，山地降水较多，盆地降水较少[33]。整个流域最大降水区域主要集中在南部山区和中部盆地，北部降水相对稀少。

# 2.5高程对数据精度的影响

陕西省地貌类型复杂，既有高原、山地和平原，高程落差大，考虑到陕西省复杂的地形变化，为了验证地形对降水产品的影响程度，本文结合DEM对降水的空间分布进行分析。

自变量为站点海拔，分别以GWR降尺度年降水数据和绝对误差(BIAS)为因变量，进行回归分析，回归结果如图8。

![](images/271ecf2abbe839a931ac52f185df8299435639227ceb6403524d8b48981291e0.jpg)  
图7陕西省克里金插值年降水量、GPM卫星年降水量以及降尺度年降水量的空间分布

由图可知，DEM与降水呈现负相关，随着海拔的升高，降水相对减少，陕西省降水主要集中在陕南及关中地区，北部黄土高原地区降水相对较少，这与陕西省实际降水情况相符。以高程为因变量，BIAS为自变量做3次多项式回归分析，结果表明随海拔的升高，BIAS先减小后略有增大，随后减少。

![](images/4cfa6bd8c220af0499ba235744d0620468b55e79be69cec15626fb8057fb10b7.jpg)  
Fig.7SpatialdistributionsofKriging interpolation,GPMsateliteanddownscalingannualprecipitationinShaanxiProvince   
图8高程(DEM)与GPM卫星年降水降尺度结果及|BIASI的拟合散点图  
Fig.8Fittings of DEM and annual GPM downscaling precipitation and |BIAS|

# 3结论

基于GPM降水数据和地面实测降雨资料分析验证了GPM数据对陕西省降水过程的探测能力以及精度，并引入DEM对GPM降水数据进行降尺度，得到 $1 ~ \mathrm { k m }$ 降尺度年降水数据，同时对其进行精度验证，研究地形对降尺度结果的影响。研究表明：

（1）GPM卫星降水数据在年和站点的时空尺度上精度较好，在研究区域内有一定的适应性。利用GWR模型对GPM降水数据进行降尺度研究，可以大幅度提高了降水数据的空间分辨率，并且有着更强的空间细节表现能力。

（2）GWR降尺度结果与实测降水数据之间有着较好的相关性，年尺度上 $\operatorname { C C } { = } 0 . 9 0$ ;季节尺度上，春、夏两季GPM降水数据的降尺度结果与实测降水数据之间的CC值分别为0.92和0.80，秋季则为0.93；月尺度上相关性也普遍较高，精度较好，能够满足实际降水研究数据的需求。

（3）但是整体而言，GWR降尺度结果值要高于GPM卫星降水数据值，GWR降尺度模型被验证能够较好的应用于陕西省的GPM降水数据降尺度研究，提高了数据的空间分辨率。本文在构建GWR模型的过程中，选取了容易获取的地形因子，忽略了其他因子，今后研究可以结合其他降尺度方法对产品数据进行进一步的精度提高。研究区内的气象观测站点较多，但是由于获取实测数据的难度较大，只从公开途径，获取了33个观测点的数据，样本数量较少，如果能有较多观测数据的话，效果可能更好。

# 参考文献(References)

[1] Chen C, Zhao S,Duan Z,et al.An improved spatial downscaling procedure for TRMM 3B43 precipitation product using geographi

cally weighted regression[J]. IEEE Journal of Selected Topics in Applied Earth Observations & Remote Sensing,2015,8(9): 4592- 4604.   
[2] 田亚林,李雪梅,李珍,等.1980—2017年天山山区不同降水形 态的时空变化[J].干旱区地理,2020,43(2):308-318.[Tian Yalin,Li Xuemei,Li Zhen,et al. Spatial and temporal variations of different precipitation types in the Tianshan Mountains from 1980 to 2017[J]. Arid Land Geography,2020, 43(2): 308-318.]   
[3]Kubota T, Shige S, Hashizume H,et al. Global precipitation map using satellite-borne microwave radiometers by the GSMaP project: Production and validation[J] IEEE Transactions on Geoscience and Remote Sensing,2007,45(7): 2259-2275.   
[4]Huffman G J,Robert FA,David TB,et al. The TRMM multi-satellite precipitation analysis TMPA: Quasi-global precipitation estimates at fine scales[R]. NTRS-NASA Technical Reports Server,2006.   
[5]张鹏举,江善虎,陈宏新,等.TRMM卫星降水数据在淮河息县 流域径流模拟的适用性[J]水资源研究.2017,6(2):148-155. [Zhang Pengju,Jiang Shanhu,Chen Hongxin,et al. Hydrological simulation capability of TRMM satelite precipitation data in Xixian catchment, Huai River Basin[J]. Journal of Water Resoures Research,2017,6(2): 148-155.]   
[6]Smith EA,Ghassem A,YojiF,et al.International global precipitation measurement (GPM) program and mission: An overview[J]. Measuring Precipitation from Space,2007,28:611-653.   
[7] Hou Arthur Y,Ramesh K K,Steven N,et al. The global precipitation measurement mission[J]. Bulletin of the American Meteorological Society,2013,95(5): 701-722.   
[8] Xu S G,Wu C Y,Li W,et al.A new satellite-based monthly precipitation downscaling algorithm with non-stationary relationship between precipitation and land surface characteristics[J]. Remote Sensing of Environment, 2015,162: 119-140.   
[9]Jia SF,Zhu WB,LuA F,et al.A statistical spatial dowscaling algorithm of TRMM precipitation based on NDVI and DEM in the Qaidam Basin of China[J].Remote Sensing of Environment,2011, 115(12): 3069-3079.   
[10] 刘小婵,张洪岩,赵建军,等.东北地区TRMM数据降尺度的 GWR模型分析[J].地球信息科学学报,2015,17(9):1055-1062. [Liu Xiaochan, Zhang Hongyan, Zhao Jianjun,et al. Spatial downscaling of TRMM precipitation data based on GWR model in northeast China[J]. Journal of Geo-Information Science,2015,17 (9): 1055-1062. ]   
[11]曾业隆,谭伟,王超,等.基于GWR模型的贵州喀斯特山区 TRMM 3B43降水资料降尺度分析[J].干旱气象,2018,36(3): 405-414.[Zeng Yelong,Tan Wei,Wang Chao,et al. Spatial downscaling of TRMM 3B43 precipitation data based on GWR model in Karst Mountainous area of Guizhou Province[J].Journal of Arid Meteorology,2018,36(3): 405-414.]   
[12]曾昭昭,王晓峰,任亮.基于GWR模型的陕西秦巴山区TRMM 降水数据降尺度研究[J].干旱区地理,2017,40(1):26-36. [Zeng Zhaozhao,Wang Xiaofeng,Ren Liang. Spatial downscaling of TRMM rainfall data based on GWR model for Qinling-Daba Mountains in Shaanxi Province[J].Arid Land Geography,2017,40 (1): 26-36.]   
[13]Duan S,Li Z L. Spatial downscaling of MODIS land surface temperatures using geographically weighted regression: Case study in northern China[J].IEEE Transactions on Geoscience & Remote Sensing,2016, 54(11): 6458-6469.   
[14]Chen F R, Yu Li, Qiang L,et al. Spatial downscaling of TRMM 3B43 precipitation considering spatial heterogeneity[J]. International Journal of Remote Sensing,2014,35(9): 3074-3093.   
[15] 胡实,韩建,占车生,等.太行山区遥感卫星反演降雨产品降尺 度研究[J].地理研究,2020,39(7):1680-1690.[Hu Shi,Han Jian, Zhan Chesheng,et al. Spatial downscaling of remotely sensed precipitation in Taihang Mountains[J]. Geographical Research, 2020,39(7): 1680-1690.]   
[16]Immerzeel W W,Rutten M M, Droogers P.Spatial downscaling of TRMM precipitation using vegetative response on the Iberian Peninsula[J]. Remote Sensing of Environment, 2009,113(2): 362-370.   
[17] Duan Z, Bastiaanssen W G M.First results from version 7 TRMM 3B43 precipitation product in combination with a new downscaling-calibration procedure[J]. Remote Sensing of Environment, 2013, 113(131): 1-13.   
[18] 李净,张晓.TRMM降水数据的空间降尺度方法研究[J].地理科 学.2015,35(9): 1164-1169.[Li Jing, Zhang Xiao.Downscaling method of TRMM satelite precipitation data[J]. Scientia Geographica Sinica,2015,35(9): 1164-1169.]   
[19] 金晓龙,邵华,张弛,等.GPM卫星降水数据在天山山区的适用 性分析[J].自然资源学报.2016,31(12): 2074-2085.[Jin Xiaolong, Shao Hua, Zhang Chi,et al. The applicability evaluation of three satelite products in Tianshan Mountains[J]. Journal of Natural Resources,2016,31(12):2074-2085.]   
[20] 董国涛,樊东,杨胜天,等.GPM与TRMM降雨数据在黄河流域 适用性分析[J].水土保持研究,2018,25(3):81-87.[Dong Guotao,Fan Dong,Yang Shengtian,et al.Analysis on the applicability of GPM and TRMM precipitation data in the Yellow River Basin [J]. Research of Soil and Water Conservation,2018,25(3): 81-87.]   
[21]Zhan CS,HanJ,Shi H,etal. Spatial downscaling of GPM annual and monthly precipitation using regression-based algorithms in a mountainousarea[J].Advances in Meteorology，2018,2018: 1506017, doi: 10.1155/2018/1506017.   
[22] 胡胜,曹明明,李婷,等.1957—2011年陕西省降水特征分析及 趋势判断[J].西北大学学报(自然科学版),2014,44(5):825- 828.[Hu Sheng,Cao Mingming,Li Ting,et al.Analysis of precipitation characteristics from 1957 to 2011 and judgement of precipitation trend in Shaanxi Province[J]. Journal of Northwest University (Natural Science Edition),2014,44(5): 825-828.]   
[23] 万相均,任志远,张翀.陕西省气温与降水变化时空分布研究 [J].干旱区资源与环境,2013,27(6):140-147.[Wan Xiangjun,

# 干吴区地理

Ren Zhiyuan,Zhang Chong.Research on spatial-temporal distribution of temperature and precipitation changes in Shaanxi Province [J].Journal of Arid Land Resources and Environment,2013,27 (6): 140-147.] [24]Brunsdon C,Fotheringham A S,Charlton M E.Geographically weighted regression: A method for exploring spatial nonstationarity [J]. Geographical Analysis,1996,28(4): 281-298. [25]Basist A,Bellg G D,Meentemeyer V. Statistical relationships between topography and precipitation paterns[J]. Journal of Climate,   
1994, 7(9): 1305-1315. [26] 魏志明,岳官印,李家,等.GPM与TRMM降水数据在海河流域 的精度对比研究[J].水土保持通报,2017,37(2):171-176.[Wei Zhiming,Yue Guanyin,Li Jia,et al. Comparison study on accuracies of precipitation data using GPM and TRMM product in Haihe River Basin[J].Bulletin of Soil and Water Conservation,2017,37 (2): 171-176.] [27]郭妍.陕西省TRMM降水数据反演精度的时空分布特征研究 [D].杨凌:西北农林科技大学,2017.[Guo Yan.Study on temporal and spatial distribution characteristics of inversion accuracy of TRMM precipitation data in Shaanxi Province[D]. Yangling: Northwest A&F University,2017.] [28]金辉明,徐鹏,何康,等.基于地理加权回归模型的省级TRMM 降水数据降尺度研究[J].浙江水利水电学院学报,2017,29(3):   
29-36.[Jin Huiming,Xu Peng,He Kang,et al. Downscaling research of TRMM precipitation data based on GWR model in Zhejiang Province[J]. Journal of Zhejiang University of Water Resources and Electric Power,2017,29(3): 29-36.]   
[29]稀涛,刘睿,杨华,等.多源遥感数据的降水空间降尺度研究 —以川渝地区为例[J].地球信息科学学报,2015,17(1):108- 117.[Ji Tao,Liu Rui, Yang Hua,et al. Spatial downscaling of precipitation using multi-source remote sensing data:A case study of Sichuan-Chongqing Region[J]. Journal of Geo-information Science, 2015,17(1): 108-117.]   
[30] 徐明,石玉立,王彬.高分辨率青藏高原历史月降水数据重建 [J].地理科学进展,2018,37(7):923-932.[Xu Ming,Shi Yuli, Wang Bin.Reconstruction of high-resolution monthly precipitation data of the Tibetan Plateau[J] Journal of Progress in Geography,2018,37(7): 923-932.]   
[31]陈诚.TRMM3B43遥感降水量产品数据定标与降尺度方法研 究[D].南京:南京大学,2016.[Chen Cheng.Researchon TRMM 3B43 remote sensing precipitation product data calibration and scaling method[D]. Nanjing: Nanjing University,2016.]   
[32]刘世伟,吴锦奎,张文春,等.基于克里金插值估算区域降水量 的抽样方法对比分析——以甘肃省为例[J].冰川冻土，2015, 37(3):650-657.[Liu Shiwei,Wu Jinkui, Zhang Wenchun,et al. Comparison analysis of sampling methods to estimate the regional precipitation based on Kriging interpolation method:A case study in Gansu Province[J]. Journal of Glaciology and Geocryology, 2015,37(3): 650-657.]   
[33]刘闻,曹明明,宋进喜,等.陕西年降水量变化特征及周期分析 [J].干旱区地理,2013,36(5):865-874.[Liu Wen,Cao Mingming,Song Jinxi,et al. Spatio-temporal distribution and temporal periodicity of annual precipitation in Shaanxi Province[J].Arid Land Geography,2013,36(5): 865-874.]

# Downscaling study of GPM satellite precipitation data: A case study of Shaanxi Province

WEN Boqing'，LIU Rong²， PANG Guowei'， ZHANG Quan' (1.Northwest University,Xi'an 710127,Shaanxi,China; 2.The 2Oth Research Institute of China Electronics Technology Group,Xi'an 71Oooo,Shaanxi,China)

Abstract: The downscaling of precipitation based on the geographically weighted regression (GWR) model provides precipitation data with higher spatial resolution, making the spatial scale of precipitation estimation more refined, which is of great importance to regional hydrology and water resources management. Shaanxi Province is located in the central and western region of China,blocked bythe Qinling Mountains and Loess Plateau,and exhibits significant regional climate diferences.Therefore,the evaluation of the spatial and temporal patterns of precipitation in Shaanxi Province is essential. In this study,the Shaanxi Province was selected as the study area and the precipitation data from ground meteorological observation stations as the real values to verify the accuracy of Global precipitation measurement (GPM) precipitation data from the time scale of the year and spatial scale of the stations.The GWR model was used to downscale the GPM and compare and verify it with the measured precipitation data. Simultaneously,basedon the downscaling method of annual precipitation data,the monthly scale was further extended to obtain higher resolution GPM monthly precipitation data and the influence degree of topography on the accuracy of satelite precipitation products was analyzed by combining the digital elevation model (DEM)data. Moreover,te correlation coeffcient (CC),root mean square error (RMSE),and relative error (BIAS)were selected to verify the GPM precipitation data accuracy in the Shaanxi Province.Additionally,the GWR model was used to downscale the GPM precipitation data.DEM data were resampled to the same resolution as GPM data.At the same time, the GPM and DEM data under the resolution of $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ were used as input elements to constructthe GWR model and the constant term,DEM coeficient term,and residual ofeach grid center point were extracted from the regression model.The constant term and coefcient term were rasterized to obtain $1 ~ \mathrm { k m }$ data,and the residual was interpolated to the spatial resolution of $1 ~ \mathrm { k m } \times 1 ~ \mathrm { k m }$ using the ordinary Kriging method. The GPM precipitation data with a spatial resolution of $1 ~ \mathrm { k m }$ was calculated and the results show that: (1)The GPM satelite precipitation data demonstrated a good accuracyon the spatial and temporal scales of annual and station,and exhibited certain adaptability in the study region.The downscaling study of GPM precipitation data using the GWR model could greatly improve the spatial resolution of precipitation data, demonstrating a stronger ability to display spatial details. (2） The GWR downscaling results showed a good correlation between the observed precipitation data, $\scriptstyle \mathrm { C C = 0 . 9 0 }$ at year scale. The GPM precipitation data of spring and summer between downscaling results and the measured rainfall data of CC values were 0.92 and 0.80,respectively at seasonal scale. In the autumn of 0.93,the month scale correlation was also generally higher and showed better accuracy, meting the needs of actual precipitation research data. On the whole,however,the GWR downscaling result was higher than the original precipitation data of GPM.(3)The results of downscaling precipitation showed a significant negative correlation with elevation.As the altitude increased,the precipitation decreased.Therefore,the GWR downscaling model was satisfactorily applied to the downscaling study of GPM precipitation data in the Shanxi Province,which improved the spatial resolution of the data.This study can provide important data for hydrological research and improve the simulation accuracy.

Key words: Global precipitation measurement (GPM)； precipitation; downscaling; geographically weighted regression model (GWR)