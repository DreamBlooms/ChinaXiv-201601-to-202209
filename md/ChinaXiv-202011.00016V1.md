# 北斗卫星精密星历插值精度研究

郭忠臣1.2，宋明洋2，鲍雅君2，崔磊³，张可2（1.安徽理工大学 地球与环境学院,安徽 淮南 2320012.宿州学院 环境与测绘工程学院，安徽宿州 $2 3 4 0 0 0 \div 3 .$ 桂林理工大学 测绘地理信息学院，广西 桂林 541006）

摘要选用非滑动式Lagrange插值法和滑动式Lagrange插值法对北斗卫星导航系统（BeidouSatellite Navigation Syetem,BDS）精密星历进行插值，通过大量实验对BDS卫星的插值精度与两种方法及插值阶次的关系进行研究。实验结果表明：(1)分别采用非滑动式和滑动式Lagrange插值时,MEO卫星和IGSO卫星的插值误差随阶次增加近似呈"U"形和"L"形分布，GEO 卫星的插值误差随阶次增加表现出逐渐增大和近似平稳的形式；（2）当插值阶次较低时，两种方法的插值误差均会出现一定的规律性，但GEO卫星插值误差的规律性弱于MEO卫星和IGSO卫星;(3)各颗卫星采用两种方法的最优插值阶次相差均在1以内，且最佳插值阶次下，滑动式Lagrange插值精度较非滑动式可提高 $1 1 . 9 6 \% { \sim } 4 4 . 0 1 \%$ ，GEO卫星插值精度优于MEO卫星和IGSO卫星。

关键词：Lagrange插值法；滑动式；BDS精密星历；误差分布规律；最佳插值阶次中图分类号：P228.4 文献标识码：A 文章编号：

# Research on interpolation accuracy of precise ephemeris of Beidou satellite

GUO Zhongchen1'2, SONG Mingyang², BAO Yajun², CUI Lei³, ZHANG Ke² .SchoolofEarthandEnvironment,Anui UniversityofScienceandTechnologyHuainan,Anhui32oo,China;2.oolol

EnvironmenndurveingEgineing,uzouUiversityzhouAnhi4,Cina;3.Coegeoomaticsndfoio Guilin University of Technology,Guilin Guangxi 541006)

Abstract: The non-sliding Lagrange interpolation method and sliding Lagrange interpolation method are used to interpolate the precise ephemeris of Beidou satelite navigation system (BDS). The relationship between interpolation accuracy and interpolation order of BDS satellite and two methods is studied. The results show that when non-sliding and sliding Lagrange interpolation are used respectively the interpolation errors of MEO and IGSO satellites are approximately U-shaped and L-shaped with the increase of the order，while the interpolation errors of GEO satelites increase gradually and are approximately stable with the increase of the order. When the interpolation order is low,the interpolation errors of the two methods have certain regularity, but the regularity of GEO Satellte interpolation error is weaker than that of MEO satellite and IGSO satelite.The difference of the optimal interpolation order of the two methods for each satelite is within 1,and under the best interpolation order the accuracy of sliding Lagrange interpolation is $1 1 . 9 6 \% \sim 4 4 . 0 1 \%$ higher than that of non-sliding interpolation,and the interpolation accuracy of GEO satellite is better than that of MEO satellite and IGSO satellite.

Keywords: Lagrange interpolation; sliding; BDS precise ephemeris; Error distribution law; optimal interpolation order

# 0引言

2020 年6月23日，北斗卫星导航系统（Beidou Satellite Navigation Syetem,BDS）全球组网完成，标志着我国的北斗卫星导航系统已经正式走向世界并为全球服务。定位功能是卫

基金项目：国家自然科学基金项目（41804029)；教育部产学合作协同育人项目（201802201036；201902164012)；国家级大学生创新创业训练计划项目（202010379058)；安徽省大学生创新创业训练计划项目（201910379140；【201910379141)；宿州学院产学研项目， $( 2 0 2 0 \mathrm { x h x } 0 3 9 )$ 资助。  
作者简介：郭忠臣，男，博士研究生，研究方向：GNSS 测量数据处理。Email：cumt_guozc@163.com  
通讯作者：宋明洋，男，本科生，研究方向：GNSS 测量数据处理。Email：978571890@qq.com

历插值精度进行研究，对BDS 精密星历插值的研究相对较少。与GPS卫星星座不同，BDS包含地球同步静止轨道卫星（Geostationary Earth Orbit，GEO）、倾斜地球同步轨道卫星（Inclined Geosynchronous Satellite Orbit,IGSO）和中圆地球轨道卫星（Medium Earth Orbit,MEO）三种轨道类型，各类卫星受插值方法和插值阶次的影响也有所区别，截止到目前，各轨道卫星分布情况见表1。当前文献中，多是研究插值方法的精度，并未对三类卫星的插值精度情况进行分析，而且多选用1颗或3颗（每类卫星1颗）卫星对算法进行实验，数据量较少，对结论的支持相对单薄[8-10]。

本文在此前研究的基础上，选用滑动式Lagrange 插值法和非滑动式Lagrange 插值法对BDS 三类卫星插值精度进行研究，首先对三类卫星插值精度与插值方法及插值阶次的关系进行研究，分析三类卫星的插值精度以及随插值阶次变化的情况；其次，对低阶次插值情况下，插值误差的统计规律进行分析；最后，对各颗实验卫星在两种方法下的最佳插值阶次进行统计，并对最佳插值阶次下，两种方法的插值精度及三类卫星的最佳插值结果进行对比。由于篇幅限制及考虑部分卫星的数据质量，文中选取PRN号在C01\~C37之间的32颗卫星数据进行实验，加粗编号为选择的实验卫星。

# 表1BDS三类轨道卫星分布情况（加粗：本文实验卫星）

<html><body><table><tr><td colspan="2">Tab.1 Distribution of three kinds of orbits of BDS satellites (bold: experimental satellites in this</td></tr><tr><td></td><td>paper)</td></tr><tr><td>轨道类型</td><td>PRN</td></tr><tr><td>GEO IGSO</td><td>C01、C02、C03、C04、C05、C18、C59、C60、C61</td></tr><tr><td></td><td>C06、C07、C08、C09、C10、C13、C16、C31、C38、C39、C40、C56 C11、C12、C14、C19、C20、C21、C22、C23、C24、C25、C26、C27、C28、C29、C30、C32、C33、C34、</td></tr><tr><td>MEO</td><td>C35、C36、C37、C41、C42、 C43、 C44、 C45、 C46、C57、C58</td></tr></table></body></html>

# 1算法原理

# 1.1 Lagrange 插值法

Lagrange 插值法可根据已知数据插值出节点内任意位置的数据，若有一系列已知节点$x _ { 0 } , x _ { 1 } , . . . , x _ { n }$ 及其对应的数值 $y _ { 0 } , y _ { 1 } , . . . , y _ { n }$ ，则Lagrange 插值多项式可表示为[3.111.

$$
L _ { n } ( x ) = \sum _ { k = 0 } ^ { n } y _ { k } ( \prod _ { i = 0 } ^ { n } { \frac { ( x - x _ { i } ) } { ( x _ { k } - x _ { i } ) } } ) = \sum _ { k = 0 } ^ { n } y { \frac { ( x - x _ { 0 } ) \dots ( x - x _ { k - 1 } ) ( x - x _ { k + 1 } ) \dots ( x - x _ { n } ) } { ( x _ { k } - x _ { 0 } ) \dots ( x _ { k } - x _ { k - 1 } ) ( x _ { k } - x _ { k + 1 } ) \dots ( x _ { k } - x _ { n } ) } }
$$

卫星的位置信息中包含 $\mathrm { \Delta } \mathrm { X }$ 、Y、 $z$ 三个坐标分量，则其在 $t$ 时刻三个坐标分量的插值多项式可表示为：

$$
\begin{array} { l } { \left\{ X ( t ) = \displaystyle \sum _ { k = 0 } ^ { n } X _ { k } \frac { \left( ( t - t _ { 0 } ) \ldots ( t - t _ { k - 1 } ) \right) \left( t - t _ { k + 1 } \right) \ldots \left( t - t _ { n } \right) } { \left( t _ { k } - t _ { 0 } \right) \ldots \left( t _ { k } - t _ { k - 1 } \right) \left( t _ { k } - t _ { k + 1 } \right) \ldots \left( t _ { k } - x _ { n } \right) } \right. } \\ { \left. \begin{array} { r l } { Y ( t ) = \displaystyle \sum _ { k = 0 } ^ { n } Y _ { k } \frac { \left( ( t - t _ { 0 } ) \ldots ( t - t _ { k - 1 } ) \right) \left( t - t _ { k + 1 } \right) \ldots ( t - t _ { n } ) } { \left( t _ { k } - t _ { 0 } \right) \ldots \left( t _ { k } - t _ { k - 1 } \right) \left( t _ { k } - t _ { k + 1 } \right) \ldots \left( t _ { k } - x _ { n } \right) } } & { { } } \\ { Z ( t ) = \displaystyle \sum _ { k = 0 } ^ { n } Z _ { k } \frac { \left( ( t - t _ { 0 } ) \ldots ( t - t _ { k - 1 } ) \right) \left( t - t _ { k + 1 } \right) \ldots ( t - t _ { n } ) } { \left( t _ { k } - t _ { 0 } \right) \ldots \left( t _ { k } - t _ { k - 1 } \right) \left( t _ { k } - t _ { k + 1 } \right) \ldots \left( t _ { k } - x _ { n } \right) } } & { { } } \end{array} \right. } \end{array}
$$

式中： $( X ( t ) , \ Y ( t ) , \ Z ( t ) )$ 为 $t$ 时刻卫星插值位置， $t _ { k } ( k = 0 , 1 , . . . , n )$ 为样本点历元， $( X ( k )$ $Y ( k ) , Z ( k ) , $ ）为 $t _ { k }$ 时刻卫星位置。

# 1.2滑动式Lagrange插值策略

滑动式Lagrange 插值法是在传统插值方法的基础上将插值区间视为一个可滑动的“窗□”，在插值过程中令插值区间随待插值点不断移动，使待插值点时刻位于插值区间中心位置[1-12]。传统插值方法在应用中易出现龙格现象，即插值区间端点附近插值结果容易出现震荡而导致插值精度较低，滑动式算法仅对插值区间中心位置进行插值，能够避免龙格现象对插值精度的影响，进而提高插值精度，但其计算量较非滑动式算法大，在实际应用过程中，可综合考虑插值精度和效率，将滑动式与非滑动式两种方式组合使用。

# 2 实验分析

本文采用2020年5月30日IGS发布的历元间隔为5min的精密星历作为原始数据，并对原始数据进行分析。依据表1，提取32颗卫星的精密星历，其中每颗卫星包含 288个三维坐标位置，为了对两种方法的插值精度及插值阶次进行研究，提取该天内以 $1 0 \ \mathrm { m i n }$ 为时间间隔的坐标作为已知数据，对其余已知时刻的坐标进行插值，并与精密星历进行对比，采用均方根误差（RMS）作为精度评价指标。鉴于实验卫星数目较多，且三维坐标的每个方向插值均有误差，同时由于篇幅限制，后面所提到的RMS均表示卫星位置综合插值误差，不再对各单独方向的RMS 进行统计分析。

# 2.1三类卫星插值精度与插值方法及插值阶次关系研究

为研究非滑动式及滑动式Lagrange 插值法中插值阶次对插值精度的影响情况，分别统计了阶次在4\~20阶时的插值精度，结果见图1和图2。为了体现三类卫星在不同插值情况下的精度量级，三类卫星各选取两颗卫星的插值精度统计结果列于表2和表3。

![](images/f2fb194df35b194fa99f0cbde4c53c14ba4560dd64154ebf8d4a1755a518f19a.jpg)  
图1不同插值阶次下非滑动式Lagrange 插值法精度统计

![](images/f7e73098a5d55501b166bc45c320b28399d3dac68f22f6dc3d74feacd18fcdb9.jpg)  
Fig.l Accuracy statistics of non-sliding Lagrange interpolation with different interpolation orders   
图2不同插值阶次下滑动式Lagrange 插值法精度统计  
Fig.2Accuracy statistics of sliding Lagrange interpolation with different interpolation orders

表2不同插值阶次下非滑动式Lagrange插值法精度统计（单位： $\mathrm { m m }$ ）） Tab.2 Accuracy statistics of non-sliding Lagrange interpolation with different interpolation orders (unit:mm)   

<html><body><table><tr><td colspan="8">PRN</td></tr><tr><td>order</td><td>C01</td><td>C05</td><td>C06</td><td>C11</td><td>C13</td><td>C37</td></tr><tr><td>4</td><td>3.62</td><td>3.69</td><td>545.75</td><td>2433.90</td><td>600.65</td><td>2286.33</td></tr><tr><td>5</td><td>3.64</td><td>3.37</td><td>31.17</td><td>194.27</td><td>34.47</td><td>181.68</td></tr><tr><td>6</td><td>4.17</td><td>3.96</td><td>4.88</td><td>17.44</td><td>5.03</td><td>16.65</td></tr><tr><td>7</td><td>4.64</td><td>4.49</td><td>5.02</td><td>5.66</td><td>4.92</td><td>4.89</td></tr><tr><td>8</td><td>5.26</td><td>5.64</td><td>6.37</td><td>6.85</td><td>6.96</td><td>6.55</td></tr><tr><td>9</td><td>7.44</td><td>7.20</td><td>8.62</td><td>9.52</td><td>8.41</td><td>9.17</td></tr><tr><td>10</td><td>10.33</td><td>10.77</td><td>11.59</td><td>13.55</td><td>13.95</td><td>13.69</td></tr><tr><td>11</td><td>17.56</td><td>16.24</td><td>19.26</td><td>20.38</td><td>20.04</td><td>21.71</td></tr><tr><td>12</td><td>27.13</td><td>21.73</td><td>26.03</td><td>34.19</td><td>30.66</td><td>30.57</td></tr><tr><td>13</td><td>46.97</td><td>44.82</td><td>43.79</td><td>52.90</td><td>55.65</td><td>57.64</td></tr><tr><td>14</td><td>77.53</td><td>71.10</td><td>88.98</td><td>95.38</td><td>88.43</td><td>93.39</td></tr></table></body></html>

<html><body><table><tr><td>15</td><td>110.31</td><td>112.19</td><td>131.66</td><td>154.89</td><td>157.16</td><td>154.92</td></tr><tr><td>16</td><td>245.98</td><td>219.40</td><td>200.47</td><td>260.19</td><td>241.98</td><td>279.74</td></tr><tr><td>17</td><td>372.39</td><td>358.34</td><td>386.48</td><td>436.19</td><td>437.17</td><td>319.00</td></tr><tr><td>18</td><td>650.75</td><td>410.16</td><td>673.16</td><td>752.16</td><td>931.41</td><td>688.82</td></tr><tr><td>19</td><td>994.99</td><td>956.14</td><td>1174.84</td><td>1488.41</td><td>1349.69</td><td>1409.19</td></tr><tr><td>20</td><td>2222.60</td><td>2204.32</td><td>2199.37</td><td>2747.37</td><td>2241.59</td><td>2342.38</td></tr></table></body></html>

表3不同插值阶次下滑动式Lagrange插值法精度统计（单位： $\mathbf { m m } \mathrm { . }$ ） Tab.3 Accuracy statistics of sliding Lagrange interpolation with different interpolation orders (unit:mm)   

<html><body><table><tr><td>PRN order</td><td>C01</td><td>C05</td><td>C06</td><td>C11</td><td>C13</td><td>C37</td></tr><tr><td>4</td><td>3.02</td><td>3.12</td><td>303.99</td><td>1356.25</td><td>334.67</td><td>1274.26</td></tr><tr><td>5</td><td>2.97</td><td>2.97</td><td>11.31</td><td>68.50</td><td>12.44</td><td>64.45</td></tr><tr><td>6</td><td>3.00</td><td>3.03</td><td>3.49</td><td>5.32</td><td>3.15</td><td>5.16</td></tr><tr><td>7</td><td>3.01</td><td>3.01</td><td>3.42</td><td>3.26</td><td>3.05</td><td>3.21</td></tr><tr><td>8</td><td>3.03</td><td>3.05</td><td>3.48</td><td>3.35</td><td>3.10</td><td>3.25</td></tr><tr><td>9</td><td>3.03</td><td>3.03</td><td>3.44</td><td>3.31</td><td>3.07</td><td>3.23</td></tr><tr><td>10</td><td>3.04</td><td>3.06</td><td>3.49</td><td>3.36</td><td>3.12</td><td>3.27</td></tr><tr><td>11</td><td>3.05</td><td>3.05</td><td>3.46</td><td>3.33</td><td>3.09</td><td>3.25</td></tr><tr><td>12</td><td>3.06</td><td>3.07</td><td>3.50</td><td>3.36</td><td>3.13</td><td>3.28</td></tr><tr><td>13</td><td>3.06</td><td>3.06</td><td>3.47</td><td>3.34</td><td>3.11</td><td>3.27</td></tr><tr><td>14</td><td>3.07</td><td>3.08</td><td>3.51</td><td>3.37</td><td>3.14</td><td>3.29</td></tr><tr><td>15</td><td>3.07</td><td>3.07</td><td>3.48</td><td>3.35</td><td>3.12</td><td>3.28</td></tr><tr><td>16</td><td>3.08</td><td>3.09</td><td>3.51</td><td>3.38</td><td>3.15</td><td>3.29</td></tr><tr><td>17</td><td>3.08</td><td>3.08</td><td>3.49</td><td>3.36</td><td>3.14</td><td>3.29</td></tr><tr><td>18</td><td>3.09</td><td>3.10</td><td>3.52</td><td>3.38</td><td>3.16</td><td>3.30</td></tr><tr><td>19</td><td>3.09</td><td>3.09</td><td>3.50</td><td>3.36</td><td>3.15</td><td>3.30</td></tr><tr><td>20</td><td>3.09</td><td>3.10</td><td>3.52</td><td>3.39</td><td>3.16</td><td>3.31</td></tr></table></body></html>

通过分析可知：

（1）对32颗卫星在各阶次下采用两种方法插值的结果对比，发现采用滑动式Lagrange插值法进行插值所获插值结果精度均高于同阶次非滑动式Lagrange插值法。当阶次为4时，两种方法插值误差统计的RMS均比较大，对所有卫星插值结果进行统计可知，非滑动式和滑动式Lagrange 插值结果统计RMS 的平均值分别为 $1 6 2 9 . 4 7 \mathrm { m m }$ 及 $9 0 8 . 1 3 \mathrm { { m m } }$ ，滑动式精度较非滑动式精度提高 $7 9 . 4 3 \%$ 。对其余阶次进行统计，滑动式较非滑动式插值精度均有提高，尤其是MEO卫星和IGSO卫星，提高幅度大都在 $5 0 \%$ 以上。

(2)GEO卫星受插值方法和插值阶次的影响远小于MEO卫星和IGSO卫星。对于GEO卫星，采用非滑动式Lagrange 插值时，当插值阶次较低时，RMS 基本都在 $4 \mathrm { m m }$ 以内，随着阶次增加，误差呈逐渐增大的趋势变化，当阶次为20时，GEO、MEO 和IGSO三类卫星的RMS均值分别为 $1 9 7 2 . 6 6 \mathrm { m m }$ 、 $2 0 5 0 . 7 1 \mathrm { m m }$ 和 $1 9 3 5 . 6 6 \mathrm { { m m } }$ ，MEO卫星和IGSO卫星的统计误差随阶次增加均呈"U"字形；采用滑动式Lagrange 插值时，GEO 卫星的RMS 随阶次的增加几乎不变，MEO卫星和 IGSO卫星在4\~5 阶时RMS 较大，随阶次增加，RMS 变化幅度较小。另外，对GEO卫星的最佳插值阶次统计发现，最佳插值阶次的精度较4阶插值结果仅提高 $4 \%$ 左右（约 $0 . 1 \mathrm { m m }$ ）。

（3）非滑动式Lagrange 插值法受插值阶次的影响明显大于滑动式Lagrange 插值法。整体上看，使用非滑动式Lagrange 插值时，插值误差随阶次的增加近似呈现出"U"字形，即插值阶次较低或者较高时，误差均比较大，插值阶次在7\~9 附近时，误差较小；使用滑动式Lagrange 插值时，插值误差在阶次为4和5的时候，误差比较大，随着阶次的增加，误差变化基本趋于稳定。

为研究插值误差的变化规律，对各个时刻的插值误差进行分析，顾及篇幅限制，三类卫星各选一颗进行分析（C01、C06、C11），图3\~图5分别给出了三颗卫星不同情况下各个插值时刻的误差分布情况，图中Z轴表示在某一插值历元下，卫星位置的综合插值误差。

![](images/b1cb2af823385103c4765dd362c9c895cba960088b16808675820d95d3d74c57.jpg)  
Fig.3 Interpolation error distribution of PRN CO1 under different interpolation orders

![](images/02f6d9d1dafb9b5ad4f1c3827d41ced16e490690f77bf5b73f6b096f877bdb9d.jpg)  
图3不同插值阶次下C01卫星插值误差分布情况  
图4不同插值阶次下C06卫星插值误差分布情况

![](images/795d085f5d6f5d3c36de3b1ac5b362fbd9f8934c712bc78dab8c8604b1940b42.jpg)  
Fig.4 Interpolation error distribution of PRN CO6 under different interpolation orders   
图5不同插值阶次下C11卫星插值误差分布情况  
Fig.5 Interpolation error distribution of PRN C11 under different interpolation orders

由图可知：采用非滑动式Lagrange 插值时，当插值阶次增加到10阶以上时，插值过程中会存在部分插值时刻误差异常的情况，随着阶次增加，异常值出现的频率相对变少，但数值却逐渐变大。对异常值进行分析，发现大多出现在插值区间两端，即异常值的出现主要是受到了“龙格”现象的影响。滑动式Lagrange 插值时可保证插值时刻位于区间中心，能有效避免“龙格”现象，故其出现异常值的概率较小，如图所示，随着插值阶次的增加，滑动式Lagrange插值结果未发现异常值，误差变化均比较平缓。

通过分析各阶次插值误差变化规律发现，插值误差随着插值历元的增加呈现出一定的周期性，并且当插值阶次较小时，规律性表现较为明显，对各颗卫星三个方向的误差作功率谱分析可知，低阶插值误差的周期性与其精密星历的周期性一致。这是因为插值阶次较小时，插值所使用的原始数据较少，各时刻的插值结果受原始数据规律的影响会比较大，随着插值阶次的增加，各时刻的插值结果受到较多数据的作用，规律性反而不会表现的那么强烈，这也解释了图中为何随着插值阶次的增加，周期性反而未表现出来。另外，GEO卫星插值误差的周期性并不明显，这也说明了GEO卫星的插值精度优于MEO卫星和IGSO卫星。

# 2.2两种方法最佳插值阶次精度对比

同阶次插值情况下，非滑动式Lagrange 插值法效率较滑动式Lagrange 插值法高，但插值精度相对较低，为研究对比两种方法的最佳插值精度，提取各颗实验卫星的最佳插值阶次，统计结果见表4。在两种方法各自的最佳插值阶次下，对各颗卫星的插值结果进行统计，并以RMS作为精度评价指标，统计结果见图6。

# 表4非滑动式和滑动式Lagrange插值法最佳插值阶次

Tab.4 The best interpolation order of the non-sliding and sliding Lagrange interpolation methods

<html><body><table><tr><td>PRN</td><td>C01</td><td>C02</td><td>C03</td><td>C04</td><td>C05</td><td>C06</td><td>C07</td><td>C08</td><td>C09</td><td>C10</td><td>C11</td></tr><tr><td>Non-sliding</td><td>4</td><td>5</td><td>4</td><td>4</td><td>5</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>7</td></tr><tr><td>sliding</td><td>5</td><td>5</td><td>5</td><td>5</td><td>5</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td></tr><tr><td>PRN</td><td>C12</td><td>C13</td><td>C14</td><td>C19</td><td>C20</td><td>C21</td><td>C22</td><td>C23</td><td>C24</td><td>C25</td><td>C26</td></tr><tr><td>Non-sliding</td><td>7</td><td>6</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td></tr><tr><td>sliding</td><td>8</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td></tr><tr><td>PRN</td><td>C27</td><td>C28</td><td>C29</td><td>C30</td><td>C32</td><td>C33</td><td>C34</td><td>C35</td><td>C36</td><td>C37</td><td></td></tr><tr><td>Non-sliding</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td>7</td><td></td></tr><tr><td>sliding</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>6</td><td>7</td><td>6</td><td>6</td><td>6</td><td></td></tr></table></body></html>

![](images/30bdb0fe0755c54d590afd24ae1326eb7029fedc33b2237e0b1cf39ea0c29380.jpg)  
图6非滑动式和滑动式Lagrange 插值法最佳阶次插值精度统计

Fig.6 Statistics of the bestorder interpolationaccuracyofthe non-slidingand sliding Lagrange interpolation methods

由表4可知,各颗卫星采用非滑动式和滑动式Lagrange 插值法的最佳插值阶次均在 4\~8阶之间，两种方法的最佳插值阶次相差均在1以内，其中， $1 2 . 5 \%$ 的卫星非滑动式算法插值阶次较低， $5 9 . 4 \%$ 的卫星滑动式算法插值阶次较低， $2 8 . 1 \%$ 的插值阶次相等。三类卫星中，GEO 卫星的最佳插值阶次主要为4阶和5阶，低于IGSO卫星的6阶，MEO卫星的最佳插值阶次相对最高，主要为6\~7阶，个别情况下为8阶。

由图10 可知，各颗卫星采用最佳插值阶次插值时，滑动式Lagrange 插值精度还是均高于非滑动式Lagrange 插值，滑动式Lagrange 插值精度较非滑动式可提高 $1 1 . 9 6 \%$ 至 $4 4 . 0 1 \%$ 。另外，GEO卫星在插值阶次更小的情况下，插值精度同样优于MEO卫星和 IGSO卫星，也说明GEO卫星的轨道数据更为稳定，MEO卫星和IGSO卫星的插值精度相似。

# 3结语

本文采用滑动式Lagrange 插值法和非滑动式Lagrange插值法对北斗卫星导航系统的三类卫星的精密星历进行插值，对两种方法及三类卫星的插值精度进行研究。以三维方式较为形象的显示了两种插值方式下，三类卫星插值精度与插值阶次的关系，同时对相同阶次下，各类卫星的插值精度进行了统计分析。当插值阶次较低时，卫星的插值精度受原始精密星历的影响较大，会呈现出同样的规律性，其中，GEO卫星受到的影响低于MEO卫星和 IGSO卫星，随着插值阶次的增加，误差的规律性表现会逐渐变弱。三类卫星采用两种方法插值时的最佳插值阶次相差均在1以内，使用最佳插值阶次插值时，滑动式Lagrange 插值精度较非滑动式可提高 $1 1 . 9 6 \% { \sim } 4 4 . 0 1 \%$ 。总的来说，三类卫星中，GEO卫星在相同插值阶次及最佳插值阶次下插值精度均优于MEO卫星和IGSO卫星，且GEO卫星的最佳插值阶次也较低；两种方法中，滑动式Lagrange插值精度优于非滑动式。在实际使用时，若数据量较多，滑动式Lagrange插值法的计算量会明显增大，可在综合考虑插值精度和插值效率的情况下，将两种方法组合使用。

# 参考文献：

[1] 陈强强,陈志平,李芳.广义延拓法在GPS 精密星历内插和外推中的应用[J].天文研究与技术,2018,15(01):52-58.CHEN Qiangqiang,CHENZhiping,LIFang.Applicationofgeneralizedcontinuationmethod in interpolationand extrapolationofGPS precise ephemeris[J].Astronomical Research& Technology,2O18,15(O1):52-58.  
[2] 李振昌,李仲勤.滑动式Lagrange 插值法在北斗卫星精密星历内插中的应用[J].全球定位系统,2018,43(03):21-25.LI Zhenchang,LIZhongqin.ApplicationoflagrangeiterpolationmethodinBeDousatelitepreciseephemeris interpoltion[J].GNSS World of China,2018,43(03):21-25.  
[3] 李振昌,李仲勤,寇瑞雄.非滑动式与滑动式拉格朗日插值法在 BDS 精密星历内插中的比较分析[J.天文研究与技术,2019,16(01):54-60.LI Zhenchang,LI Zhongqin,KOURuixiong.Comparisonandanalysisofnon-slidingand sliding lagrange interpolationinBDSprecision ephemeris interpolation[J]. Astronomical Research & Technology,2O19,16(O1):54-60.  
[4] 王建敏,李亚博,祝会忠,等.BDS卫星位置插值方法研究及精度分析[J].测绘科学,2017,42(12):25-31.WANGJianmin,abo,ZUHuzhong,etalResearchoniterpolationmethdadprecisioaalysisofDSsateliteoitio[J].Science of Surveying and Mapping,2017,42(12):25-31.  
[5]吴传龙,宋世泽,王鼎蔚.三次样条在北斗卫星轨道插值中的应用[J].全球定位系统,2017,42(01):108-110.WUChuanlong,SONG Shize,WANGDingwei.Theapplicationofcubicsplineiterpolationfortheleosatelite[J].GN WorldfChina,2017,42(01):108-110.  
[6] 王兴,高井祥,王坚，等.利用滑动式切比雪夫多项式拟合卫星精密坐标与钟差[J].测绘通报,2015(5):6-8+16.WANGXin,GAOJingxiang,WANGJian,etal.UsingsleekChebyshevpolomialtofittheprecisesatelitecoordinateadclockerror[J]. Bulletin of Surveying and Mapping,2O15(5):6-8+16.  
[7]高明超,徐泮林,谷彦斐.IGS 精密星历内插方法研究[J].测绘与空间地理信息,2020,43(08):110-112+115.GAO Mingchao,XUPanlin,GU Yanfei.Researchontheinterpolation methodof preciseephemeris[J].Geomatics& SpatialInformation Technology, 2020,43(08):110-112+115.  
[8]从建锋,刘智敏，刘盼,郭金运.基于非滑动式与滑动式BDS 精密星历内插及其精度分析[J].测绘工程,2019,28(06):22-29.

CONG Jianfeng,LIU Zhimin,GUO Jinyun.Non-slidingand sliding BDSprecision ephemeris interpolationand itsacuracy analysis[J].Engineering of Surveying and Mapping,2O19,28(06):22-29.

[9] 汪威,陈明剑,闫建巧,等.北斗三类卫星精密星历内插方法分析比较[J].全球定位系统,2016.41(02):60-65. WANGWei,CHENMingjian,YANJianqiao,etal.ThreeKindsofCompassSatelitePreciseEphemerisInterpolationMethod Analysis Comparative[J]. GNSS World of China,2016,41(O2):60-65.

[10]王尔申,赵珩,曲萍萍,等.基于拉格朗日插值法的卫星导航空间信号精度评估算法[J.沈阳航空航天大学学报,2019,36(04):43-48.

WANGErshen,ZHAOHeng,QUPingping,etal.Alagrangianinterpolationmethod-basedsatelitenavigationsignalin-space accuracy evaluation algorithm[J]. Journal of Shenyang Aerospace University,2O19,36(O4):43-48.

[11] 郭忠臣.利用滑动式Lagrange 插值方法拟合卫星精密星历[J].宿州学院学报,2017,32(07):106-108.GUO Zhongchen.Fitingsatelitepreciseephemeris bysliding Lagrangeinterpolation method[J].Journalof Suzhou University2017,32(07):106-108.

[12]雷雨,赵丹宁,高玉平.基于滑动式Lagrange 插值方法的GPS 精密星历内插分析[J].测绘工程,2013,22(02):34-36 LEIYu,ZHAODanning,GAO Yuping.Analysisof interpolation forGPS preciseephemeris using sleek Lagrange interpolation[J] Engineering of Surveying and Mapping,2013,22(02):34-36.