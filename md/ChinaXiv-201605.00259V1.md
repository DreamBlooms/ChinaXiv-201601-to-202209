# 基于CHAMP卫星与三维Taylor多项式模型的区域地磁建模研究

蒋勇1,²，姜乙¹，冯彦1,2＊，刘宝嘉¹，傅帅¹，常德1，张鹏飞¹，江涛11南京信息工程大学空间天气研究所，南京2100442 中国科学院空间天气学国家重点实验室，北京100190

摘要利用CHAMP卫星矢量和标量地磁测量数据，通过三维 Taylor多项式模型建立了2010.O年中国及邻近地区在 $3 0 0 ~ \mathrm { k m }$ 高度附近的 $X , Y , Z$ 和 $F$ 分量的三维磁场模型.为了比较验证所建模型，分析了其与Taylor多项式模型（二维模型)不同截断阶数所对应的均方偏差(RMSE)、残差及分布等.结果表明，三维模型每一阶的 RMSE 和残差绝对值的平均值均要比二维模型的小约 $45 \%$ .由于采用了系数完全展开的建模方式，三维模型的系数数量约为二维模型的2倍，三维模型较低的截断阶数可以反映更多的地磁信息.本研究中的5阶三维 Taylor 模型基本可达到8阶Taylor模型的精度.两种模型绘制的地磁场及残差分布有较好的一致性.

关键词地磁模型；三维Taylor多项式模型；CHAMP卫星；均方偏差

doi:10.6038/cjg20150909 中图分类号 P318

收稿日期2015-03-13，2015-07-30 收修定稿

# Regional geomagnetic modelling based on the magnetic data of CHAMP satellite and 3D Taylor polynomial

JIANG Yong1²，JIANG Yi1，FENG Yan1,2\*，LIU Bao-Jia1 , FU Shuai' ，CHANG Del，ZHANG Peng-Fei' ，JIANG Taol 1 Instituteof Space Weather，Nanjing Universityof Information Science and Technology，Nanjing 210044,China 2 State Key Laboratory of Space Weather，Chinese Academy of Sciences，Beijing l0ol9o,China

Abstract The inherent shortcoming of most regional models is the lack of altitude information. In order to overcome this，the objective of this study is to establish the three-dimensional (3D) model of element $X$ ，Y， $Z$ ，and $F$ over Chinese and its adjacent regions in 2Olo.O at the height of about $3 0 0 ~ \mathrm { k m }$ . Based on the vector and scalar geomagnetic measuring data of CHAMP satellite, associated with 3D Taylor polynomial method，we try to create the 3D model over China and calculate the spatial distribution of geomagnetic field region. 3D model not only has the advantages like simple calculation and convenient to use，but also takes into account the height. In addition，the selection of truncation level of 3D model was also discussed. In order to verify the constructed 3D model，a comparison between 3D and Taylor polynomial （2D） model was taken，we analyzed the Root-mean-square error（RMSE）and the residual distributions between 3D and 2D models in different truncation level.

Results showed RMSE and the mean absolute residuals of each level of the 3D model are about $45 \%$ smaller than that of 2D model. The 3D model of degree 5 basically has the same precision as that of 2D model of degree 8 in this study. Geomagnetic distributions and residuals of 3D and 2D models have high consistency. After comparing with 2D model， the 3D model considers the altitude information，so the precision is really improved；the coeficients show that 3D model of low degree can reflect more information and has the similar precision when compared to 2D model of high degree.

KeywordsGeomagnetic model； 3D Taylor polynomial； CHAMP satelite； Root-mean-square error

# 1引言

区域地磁场模型用以反映某个区域的地磁场的时空分布特征.相比于全球地磁场模型（Hurwitzdetal.，1966；IAGA，2003，2005，2010；冯彦等，2014a)，结合高密度的地面实测数据，区域模型能更精确地反映区域内的地磁场分布，如地磁场在特定区域内所呈现的一些变化规律和异常分布.

常用的区域地磁场模型包括Taylor多项式模型、曲面Spline模型（安振昌和徐元芳，1981；安振昌等，1982）、矩谐模型（Alldredge,1981）、Legendre模型、自然正交分量（NOC)模型、球冠谐模型(Haines，1985)等.国内外学者已利用这些区域模型做了很多研究.如，Alldredge（1982）利用矩谐模型研究美国东南部区域磁场.Haines(1985)利用球冠谐模型分析了加拿大区域1960—1983年的磁场变化.Duzgit等(1997)利用矩谐分析研究了欧洲区域的地磁场.Thebault等（2004，2006）（ThebaultandGaya-Piqué，2008)将原有的球冠谐模型进行了改进，并利用改进后的模型研究了法国地区的地磁场（Thebault，2008).国内学者主要针对中国地区开展了一些研究.徐文耀和朱岗昆(1984)利用矩谐分析研究了我国及邻近地区的地磁场.高金田等(2006）运用曲面Spline模型研究了 $1 9 0 0 - 1 9 3 6$ 年中国区域地磁场以及其长期变化的分布.陈斌等(2011)运用球冠谐模型计算2005年中国地区地磁场及其长期变化.

相比于其他的区域模型，Taylor多项式模型由于其计算简单及使用方便，得到了广泛的应用.如安振昌等（199la）利用Taylor多项式模型建立了1950—1980年中国地区主磁场模型.徐元芳等(1992)运用Taylor多项式模型计算了1950—1985年中国地区地磁场长期变化模型.高金田等(2005)利用2003年中国地区的地磁台站数据建立Taylor多项式模型对中国地区的地磁场进行了研究.冯彦等(2010c)利用2000年中国地磁台站和复测点数据，根据Taylor多项式模型计算了2O0O年中国地区地磁场.

尽管存在上述优点，但Taylor模型是二维模型，建模时只考虑了经度与纬度，而忽略了高度因素.地磁场的强度随着高度变化而变化，一般以$2 0 ~ \mathrm { n T / k m }$ 的速率减少(安振昌等，1991b)，因此二维模型所计算的地磁场强度会存一定的误差.针对此问题，柳士俊等(2011)提出了三维Taylor多项式模型，考虑了高度的因素，为区域模型的研究提供了一种新的方法.

在以往的研究中，建立和计算区域地磁场模型所采用的数据大多来自于地磁复测点、台站数据或者利用其他模型所模拟的数据.由于地磁复测点和台站数量有限，且空间分布很不均匀，这将直接影响所建模型的精度.另外由于缺少国界外测点，使得在边界区域上的模拟会出现异常，即边界效应.一般解决边界效应的方法有添加边界外区域的补充点和扩大拟合区范围两种(杨云涛等，2009).补充点的数据通常来自于其他模型，如国际地磁参考场（IGRF）.这种数据本身就存在一定的误差，因此会进一步影响所建立模型的精度.扩大拟合区范围后，虽然在拟合区中心的高精度范围扩大，但拟合区的边界异常仍没得到解决.

对于CHAMP卫星的磁测数据，国内外学者做了大量的研究工作.如Sabaka等(2004)利用CHAMP等卫星数据建立了第四代地磁场模型综合模型CM4.Olsen等(2006)利用CHAMP等卫星数据建立了CHAOS模型系列.Maus等(2007)利用CHAMP卫星数据建立了岩石圈磁场模型(MF)系列.康国发等（2009，2010)基于CHAMP卫星数据建立的POMME-4.2S模型研究了中国及邻近地区的长期变化、长期加速度以及磁异常的分布特征.然而，将CHAMP卫星磁测数据进行中国大陆地区的地磁场研究至今还鲜有报道.

针对目前研究现状，认为基于CHAMP卫星所提供的高精度、高密度的全球地磁标量数据和矢量观测数据进行中国及邻近地区的地磁场三维建模对于研究中国，乃至东亚地区的高精度地磁场形态分布具有重要的理论和应用价值.现拟首先对CHAMP卫星数据进行数据预处理及网格化，得到中国地区卫星地磁网格数据，然后基于不同位置和高度的卫星数据建立中国及邻近地区的三维Taylor多项式模型（三维模型)，分析了4个地磁要素 $( X , Y , Z , F )$ 的分布特点，研究了截断阶数对模型精度的影响，并在拟合值、残差分布，截断阶数与RMSE值等方面与常用的Taylor多项式模型（二维模型)进行比较分析.

# 2 数据与方法

# 2.1 数据

地磁场为一向量场，地球空间任意一点都包含7个地磁场要素，分别为地磁场总强度 $F$ ，北向分量$X$ ,东向分量Y，垂直分量 $Z$ ,水平强度 $H$ ,磁偏角 $D$ 和磁倾角I.CHAMP卫星提供了2001—2010 年的地磁标量数据 $( F )$ 和矢量数据 $( X , Y , Z )$ ，所有数据由德国地球科学研究中心（GFZ）网站（http：//www.gfz-potsdam.de/startseite/）提供.CHAMP卫星于2000年7月15日从俄罗斯的Plesetst卫星发射基地发射至近极轨、环形、高约 $4 5 4 ~ \mathrm { k m }$ 的轨道.卫星搭载的Overhauser磁力计（OVM)测量标量数据，磁通门磁力计(FGM)测量矢量数据（冯彦等，2010a).

由于所测量的矢量数据是在FGM参考坐标系下获取的，因此还需要将数据转换至NEC（北向、东向、垂直)坐标系数据，具体转换过程如下：

$$
B _ { \mathrm { N E C } } = R _ { \mathrm { ( N E C  I T R F ) } } \bullet R _ { \mathrm { ( I T R F  I C R F ) } } \bullet R _ { \mathrm { ( I C R F  A S C ) } }
$$

$$
\bullet R _ { \mathrm { ( A S C \bullet H M ) } } \bullet B _ { \mathrm { F G M } } ,
$$

其中 $R _ { \mathrm { ( A S C \bullet F G M ) } }$ 为将FGM传感器参考系数据转换至卫星光具座(ASC)参考系数据，虽然角度在发射前已经确定，但在卫星运行过程中会不断变化，因此需要进行校正； $R _ { \mathrm { ( I C R F \bullet , A S C ) } }$ 为将基于level-2的卫星姿态数据由ASC参考系数据转换到国际天球参考系(ICRF)数据； $R _ { \mathrm { ( I T R F  I C R F ) } }$ 为将ICRF参考系数据转换到国际地球参考系(ITRF)数据； $R _ { \mathrm { ( N E C * - I T R F ) } }$ 为将ITRF参考系数据转换到NEC参考系数据.

为了尽量减少磁扰，提高模型的精度，本文参考常用的全球模型，如CM4（Sabakaetal，2004），CHAOS3(Olsenetal,2010)等的建模经验，选取夜侧卫星数据，即 $1 8 : 0 0 { \mathrm { - } } 5 : 0 0 \mathrm { L T }$ 期间数据.并从中筛选出 $K \hbar < 2 , | D _ { \mathrm { s t } } | < 2 0 \mathrm { n T }$ 范围内的数据.

本文拟计算并分析2010.0年（2010年1月1日）的中国及邻近区域地磁场分布，研究范围为 $1 8 ^ { \circ } \mathrm { N - }$ $5 4 ^ { \circ } \mathrm { N } , 7 3 ^ { \circ } \mathrm { E } { \mathrm { - } } 1 3 6 ^ { \circ } \mathrm { E } .$ 为了获得均匀且高密度分布的卫星数据，通过试验，发现对于某一时间点前后60天内的卫星数据经归算后可获取较为理想的测点分布，然而由于测点的分布并不均匀，考虑到每个测点在三维建模中的权重应一致，因此对归算后的所有数据进行网格化处理.现选取2010.0年作为研究时间点，将该时间点前后60天内的数据进行归算，以经纬度1为间隔，在每个格点处取其上下左右 $1 ^ { \circ }$ 内所有卫星数据的平均值进行网格化.对剩余较少的缺测格点，则进行分段线性插值.最后得到在中国及邻近地区的卫星网格值，共为2368个数据点.2010年为CHAMP卫星观测末期，卫星轨道高度较初期有所下降，2010.0年所有CHAMP卫星数据的高度约为 $3 0 2 . 5 9 { \sim } 3 1 2 . 8 4 ~ \mathrm { k m } .$

图1为背景网格数据的平面分布图，每个数据格点都均匀分布.图2为网格数据的三维分布，从低纬到高纬地区，数据点高度呈下降趋势.现基于这些网格数据建立三维Taylor模型，

# 2.2Taylor多项式模型

本研究基于二维Taylor多项式模型建立三维

![](images/57529d94c144a6321fc9f574ea20f4ea23391159a9b6f47551e10fc0208e9548.jpg)  
图1CHAMP卫星磁测数据平面网格图Fig.1 Two-dimenson distribution of CHAMPsatellite magnetic grid data

ss .. . .. ...... Po00 3: 1 ： .. ...... : ..·. 0..0..o ......gs .0.. 888838888888 8398\*.0 ... 0.00· 0.008 .. ...... 0 ....... .......... ........ 310 2 / i .·.. .. 00 m .... · . .....·.. . 8 : ....... 88888 .. ....... · 130 . 120 0.. 305 电话 110 50 100 东经/) 4 90 北纬/() 30 80 20

Taylor多项式模型.二维模型表达式如下：

$$
W = \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { i } A _ { i j } ( \varphi - \varphi _ { 0 } ) ^ { i - j } ( \lambda - \lambda _ { 0 } ) ^ { j - 1 } ,
$$

上式中 $W$ 表示任意磁场要素； $N$ 为截断阶数； $\varphi , \lambda$ 为各地磁测点的纬度和经度； $\varphi _ { \mathrm { 0 } } \mathrm { , } \lambda _ { \mathrm { 0 } }$ 为多项式的展开原点， $\varphi _ { \scriptscriptstyle 0 } = 3 6 ^ { \circ } \mathrm { N } , \lambda _ { \scriptscriptstyle 0 } = 1 0 4 . 5 ^ { \circ } \mathrm { E } ; A _ { i j }$ 为相应各分量的模型系数，每个模型有 $N ( N + 1 ) / 2$ 个系数，所有系数通过最小二乘法求取.

(2)式的系数为一下三角矩阵，该系数展开称为经典展开，而更为普遍的方法为进行完整展开（方阵展开)，这样做的优点是可以较低的截断阶数反映出更多的地磁场信息，后文会有所阐述.现基于二维模型，通过添加高度项，并通过系数的完整展开而得到三维Taylor模型，其表达式如下：

$$
W = \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { N } \sum _ { k = 1 } ^ { N } A _ { i j k } ( \varphi - \varphi _ { 0 } ) ^ { i - 1 } ( \lambda - \lambda _ { 0 } ) ^ { j - 1 } ( h - h _ { 0 } ) ^ { k - 1 } ,
$$

上式中 $W$ 表示任意磁场要素， $N$ 为截断阶数; $\varphi , \lambda$ $h$ 为各地磁测点的纬度、经度和高度； ${ \varphi _ { \mathrm { 0 } } \bullet } _ { \mathrm { 0 } } \bullet _ { \mathrm { 0 } } \bullet _ { \mathrm { 0 } }$ 为多项式的展开原点， $\varphi _ { \scriptscriptstyle 0 } = 3 6 ^ { \circ } \mathrm { N } , \lambda _ { \scriptscriptstyle 0 } = 1 0 4 . 5 ^ { \circ } \mathrm { E } , h _ { \scriptscriptstyle 0 } =$ $3 0 2 . 5 9 \sim 3 1 2 . 8 4 ~ \mathrm { k m } ; A _ { i j k }$ 为模型系数，每个模型有$N ^ { 3 }$ 个系数，所有系数通过最小二乘法求取.

# 3结果

# 3.1 截断阶数的选取

Taylor多项式模型为基于数据点的拟合模型，截断阶数的选取非常重要.过低的截断阶数可能会导致区域地磁场短波长信息的丢失，从而使模型无

法展示高精度区域地磁场的时空分布，而过高的截断阶数在增加计算量的同时，还会使结果出现局部畸变.

通常根据如下两条依据以确定合适的截断阶数（安振昌，2001）：

(1)区域地磁场模型的均方偏差要小于IGRF的均方偏差；

(2)随着截断阶数的增加，RMSE逐渐减小，当RMSE趋于稳定时，可确定截断阶数，

RMSE通过下式计算得到：

$$
\mathrm { R M S E } = \sqrt { \frac { \sum ( W _ { \mathrm { m o d } } - W _ { \mathrm { o b s } } ) ^ { 2 } } { n - 1 } } ,
$$

其中， $W _ { \mathrm { m o d } }$ 为任意地磁要素的模型值， $W _ { \mathrm { { o b s } } }$ 为相同地点同一地磁要素的观测值， $n$ 为观测点数量.

现根据式（4)计算各阶三维模型的RMSE值， 结果见表1.

表1三维Taylor多项式模型各截断阶数的RMSE(单位：nT)   
Table 1 The RMSE of each truncation order of 3D Taylor polynomial model (units：nT)   

<html><body><table><tr><td>N</td><td>X</td><td>Y</td><td>Z</td><td>F</td></tr><tr><td>1</td><td>5495</td><td>1453</td><td>10332</td><td>4710</td></tr><tr><td>2</td><td>437.9</td><td>208</td><td>1108.2</td><td>942.1</td></tr><tr><td>3</td><td>39.86</td><td>187.88</td><td>101.29</td><td>69.27</td></tr><tr><td>4</td><td>21.55</td><td>49.51</td><td>60.16</td><td>45.65</td></tr><tr><td>5</td><td>15.72</td><td>15.08</td><td>30.51</td><td>17.53</td></tr><tr><td>6</td><td>10445</td><td>492</td><td>14520</td><td>17917</td></tr><tr><td>7</td><td>13657</td><td>773</td><td>18971</td><td>23353</td></tr><tr><td>8</td><td>17225</td><td>945</td><td>23874</td><td>29406</td></tr><tr><td>9</td><td>18946</td><td>1191</td><td>26371</td><td>32426</td></tr><tr><td>10</td><td>21312</td><td>1285</td><td>29335</td><td>36263</td></tr><tr><td>11</td><td>21824</td><td>1399</td><td>30127</td><td>37230</td></tr></table></body></html>

根据表1，基于CHAMP卫星数据的三维Taylor多项式模型的RMSE值在 $N { \leqslant } 5$ 时， $X , Y$ 、$Z , F$ 分量的RMSE 随 $N$ 的增大而迅速减小，平均下降幅度达到了 $6 5 . 1 8 \%$ ,其中 $X$ 分量由1阶的$5 4 9 5 ~ \mathrm { n T }$ 减小为5阶的 $1 5 . 7 2 ~ \mathrm { n T } , Y$ 分量从1阶的$1 4 5 3 ~ \mathrm { n T }$ 减少为5阶的 $1 5 . 0 8 ~ \mathrm { n T } , Z$ 分量从 $1 0 3 3 2 ~ \mathrm { n T }$ 减少为 $3 0 . 5 1 ~ \mathrm { n T } , F$ 总量由 $4 7 1 0 ~ \mathrm { n T }$ 减小为 $1 7 . 5 3 ~ \mathrm { n T }$ 当 $N { > } 5$ 时，三维模型的RMSE值大幅增加， $X$ 分量为 $1 0 4 4 5 ~ \mathrm { n T } , Y$ 分量为 $^ { 4 9 2 } \mathrm { n T } , Z$ 分量为 $1 4 5 2 0 ~ \mathrm { n T } , \boldsymbol { F }$ 总量为 $1 7 9 1 7 \ \mathrm { n T }$ .这是由于阶数过高而导致的区域异常现象，即“龙格现象”.

根据第一条选取依据，现基于最新发布的IGRF12计算了其与实测点数据的RMSE值(见表2).

表2实测点与IGRF12的RMSE值(单位：nT) Table 2The RMSE values between measuring points and IGRF12(units:nT)   

<html><body><table><tr><td>模型</td><td>X</td><td>Y</td><td>Z</td><td>F</td></tr><tr><td>IGRF12</td><td>4394.12</td><td>595.08</td><td>6175.49</td><td>7595.54</td></tr></table></body></html>

根据表1和表2，当 $2 \leqslant N \leqslant 5$ 时，三维模型的RMSE值小于IGRF12的RMSE值，即满足选取判据(1).综上，三维模型的截断阶数选为5.

# 3.2中国及邻近地区的三维Taylor多项式模型的计算和分析

基于不同高度的CHAMP卫星网格点，利用5阶三维Taylor多项式模型计算2010.0年的中国及邻近地区地磁场网格值.模型原点为研究区域的中心，即 $\varphi _ { \mathrm { 0 } } = 3 6 ^ { \circ } \mathrm { N } , \lambda _ { \mathrm { 0 } } = 1 0 4 . 5 ^ { \circ } \mathrm { E } .$ 基于所得系数绘制的卫星高度处 $X , Y , Z , F$ 四个要素的三维分布见图3.

根据图 $s , X$ 分量的强度随着纬度的升高而逐渐减小，由 $3 4 1 4 0 . 7 7 ~ { \mathrm { n T } } ( 1 8 ^ { \circ } { \mathrm { N } } , 5 9 ^ { \circ } { \mathrm { E } } )$ 左右减少为$1 4 8 2 3 . 9 8 ~ \mathrm { n T } ( 5 4 ^ { \circ } \mathrm { N } , 7 3 ^ { \circ } \mathrm { E } )$ 左右，等值线走向基本与纬度方向一致.Y分量的分布略为复杂，大致呈 $\pi$ 型分布，强度自西向东逐渐减小，最大值为西北部( $\mathrm { 5 4 ^ { \circ } N }$ $7 3 ^ { \circ } \mathrm { E } )$ 处的 $2 4 4 9 . 2 5 \ \mathrm { n T }$ 左右，最小值在东北部( $\mathrm { \cdot 4 9 ^ { \circ } N }$ $\mathrm { 1 3 5 ^ { \circ } E }$ 处的一 $- 3 5 2 7 . 6 6 ~ \mathrm { n T }$ 左右. $Z$ 分量的等值线走向基本与纬度方向一致，强度随着纬度的升高而增大，由低纬度 $1 2 3 4 9 . 7 0 ~ \mathrm { n T } ( 1 8 ^ { \circ } \mathrm { N } , 1 3 6 ^ { \circ } \mathrm { E } )$ 左右上升到高纬度 $4 9 6 5 7 . 9 9 \ \mathrm { n T } ( 5 4 ^ { \circ } \mathrm { N } , 9 9 ^ { \circ } \mathrm { E } )$ 左右.地磁场 $F$ 总量的分布与 $Z$ 分量类似，强度随着纬度的升高而增大，最大值为 $5 1 8 8 4 . 4 0 ~ \mathrm { n T } ( 5 4 ^ { \circ } \mathrm { N } , 1 0 4 ^ { \circ } \mathrm { E } )$ 左右，最小值为 $3 3 6 4 7 . 1 1 ~ \mathrm { n T } ( 1 8 ^ { \circ } \mathrm { N } , 1 3 6 ^ { \circ } \mathrm { E } )$ 左右.由于采用的是卫星网格数据，因此不存在边界效应.

为了比较验证所建模型，基于相同的CHAMP卫星数据，对所有高度都取平均值，即 $h _ { 0 } { = } 3 0 7 . 6 9 \ \mathrm { k m } .$ 通过输入每个测点在 $h _ { \scriptscriptstyle 0 }$ 处的经纬度及 $X , Y , Z$ 和 $F$ 总量的强度值，利用二维Taylor模型计算并绘制了中国及邻近地区的地磁场分布(未列出).当 $N \geqslant 5$ 时，二维模型的RMSE值逐渐趋于平稳，下降并不明显.考虑到截断阶数越高，计算量越大，且两种模型在相同阶数时反映的信息量不同.通过RMSE值的比较，现认为5阶的三维Taylor模型与8阶的二维Taylor模型都能达到满意的模拟精度，其精度接近（后文有详细阐述).比较发现两种模型所得到的4要素地磁场无论在分布还是强度上均非常相似，故不再将二维模型的图形列出.

![](images/41a064131b6b443f1eb509473b86f3f273676aaeba0cb29931961b8eab7bb70a.jpg)  
图3基于5阶三维Taylor多项式模型的中国及邻近地区地磁分布（高度： $3 0 2 . 5 9 { \sim } 3 1 2 . 8 4 ~ \mathrm { k m } )$ ；单位： $\mathrm { n T }$ Fig.3Geomagnetic distribution of China and its adjacent regions based on 3D Taylor polynomial model withdegree 5(altitude： $3 0 2 . 5 9 { \sim } 3 1 2 . 8 4 ~ \mathrm { k m } )$ ；units：nT

为了比较所建模型的拟合效果，现将部分测点的实测值及其8阶二维模型和5阶三维模型值进行对比(见图4）.

根据图4，两种模型的拟合值与实测值非常接近，图中两条线基本重合，而Y分量则存在一些差异，从与实测值的接近程度及变化趋势看，三维模型拟合值要略好于二维模型拟合值.通过比较，可以发现每个实测点的二维以及三维模型值与对应实测数据的平均误差为 $1 \%$

然而，二维模型是一种平面方法，所有数据点都要求在同一水平高度上.因此二维模型所使用的平均高度 $( 3 0 7 . 6 9 ~ \mathrm { k m } )$ 与本文数据 $( 3 0 2 . 5 9 { \sim } 3 1 2 . 8 4 ~ \mathrm { k m } )$ 相比就会存在士 $5 ~ \mathrm { k m }$ 左右的高度差，由此而产生的误差是不可避免的，并且对于二维模型是无法计算这部分误差的.而三维模型的结果不仅考虑了高度的因素而且能与实测值很好的拟合.因此总体而言，三维模型的拟合效果是令人满意的.

为了进一步地观察两模型的差异，现绘制了两种模型相对于实测值的残差分布图（见图5）.

通过比较发现，两种模型绘制的残差网格图无论在分布以及强度上都很接近.并在各分量的一些正负残差分布位置都较为相似，如 $X$ 分量在塔里木盆地的约 $3 0 ~ \mathrm { n T }$ 的正残差分布和内蒙古中部的约$- 4 0 ~ \mathrm { n T }$ 的负残差分布、Y分量在中国地区东经 ${ 1 1 0 } ^ { \circ }$ 附近约一 $3 3 ~ \mathrm { n T }$ 的负残差分布、 $Z$ 分量在广西南部约一 $7 0 ~ \mathrm { n T }$ 的负残差分布以及 $F$ 总场量在漠河一带约 $4 0 ~ \mathrm { n T }$ 的正残差分布都很相似.

![](images/a57d5c9fa263240273ad4706676e7de3516256eadca1ab17b37bcf574eb04bd7.jpg)  
图4三维模型和二维模型的模拟值与实测值的比较；单位： $\mathrm { n T }$   
'ig.4The comparison among observed values and their modelling values based on 3Dand 2D model；units：1

![](images/cc1e2543f10a5ef46cd5cf9b399948c881fd913d3f2b1a62d3959cabc6912915.jpg)  
图5三维模型(左)和二维模型(右)的残差分布图；(a—d) $X , Y , Z , F ; \left( \mathrm { e } ^ { - } \mathrm { h } \right) \ X , Y , Z , F$ 单位：nTFig.5The residual distribution of 3D model(left）and 2D model(right)；(a—d) $X , Y , Z , F$ ;(e-h) $X , Y , Z , F$ ；units：nT

以上两种分布的比较很难发现明显的区别，为了更为直观地观察两种模型的拟合效果，计算了两模型相对于所有CHAMP卫星网格数据的残差.比较发现两模型的残差在变化幅度上相差不大，但对于 $X$ 分量和 $F$ 总量，三维模型要明显优于二维模型.三维模型的残差整体要小于二维模型，如三维模型 $X$ 分量的平均相对误差为 $0 . 0 5 1 \%$ ，要小于二维模型的 $0 . 0 5 4 \%$ ,三维模型 $F$ 总量的平均相对误差为

$0 . 0 3 1 \%$ ,要小于二维模型的 $0 . 0 4 3 \%$ ，下降了 $0 . 0 1 2 \%$

为了进一步说明两种模型的差异，通过下式计算两种模型 $N$ 为 $1 \sim 1 0$ 时的残差绝对值的平均值变化，

$$
R _ { \mathrm { m } } = \frac { \sum \mid W _ { \mathrm { m o d } } - W _ { \mathrm { o b s } } \mid } { n } ,
$$

上式中 $R _ { \mathrm { m } }$ 为所有点残差绝对值的平均值，其他各变量的意义与(4)式相同.

图6列出了两模型在 $N$ 为 $1 \sim 5$ 时的残差绝对值求平均的结果.根据图6可知，随着 $N$ 的增加，三维模型的平均残差的下降速度要略快于二维模型的，在 $N$ 相同的情况下，三维模型的平均残差要比二维模型平均小 $4 5 . 0 9 \%$ ，这说明了相同阶数三维模型的拟合精度要好于同阶的二维模型.

![](images/043bd6fd0f7cbe77b734e39b19c4edac7a4fec0456acad72268909f9c38a8341.jpg)  
图6三维模型和二维模型的残差绝对值的平均值变化  
Fig.6Mean values variation of absolute residual of elements $X$ ， $Y$ ， $Z$ ， $F$ based on 3D and 2D model；units：n'

下面对于两模型的RMSE进行分析.首先列出了二维模型在 $N$ 为 $_ { 1 \sim 1 1 }$ 时的RMSE变化(见表3).

表3二维Taylor多项式模型各截断阶数的RMSE(单位：nT)Table 3The RMSE of each truncation order of 2D Taylorpolynomial model(units:nT)  

<html><body><table><tr><td>N</td><td>X</td><td>Y</td><td>Z</td><td>F</td></tr><tr><td>1</td><td>5495</td><td>1453</td><td>10332</td><td>4710</td></tr><tr><td>2</td><td>755</td><td>616.3</td><td>1677.2</td><td>976.1</td></tr><tr><td>3</td><td>309.21</td><td>227.27</td><td>302.37</td><td>231.63</td></tr><tr><td>4</td><td>45.28</td><td>69.48</td><td>133.87</td><td>82.7</td></tr><tr><td>5</td><td>29.01</td><td>32.49</td><td>38.94</td><td>31.37</td></tr><tr><td>6</td><td>17.85</td><td>15.43</td><td>32.1</td><td>25.23</td></tr><tr><td>7</td><td>17.23</td><td>13.51</td><td>29.68</td><td>24.86</td></tr><tr><td>8</td><td>16.96</td><td>12</td><td>29.35</td><td>24.61</td></tr><tr><td>9</td><td>16.77</td><td>11. 81</td><td>29.19</td><td>24.55</td></tr><tr><td>10</td><td>16.71</td><td>11.48</td><td>29.06</td><td>24.41</td></tr><tr><td>11</td><td>4843</td><td>243</td><td>6814</td><td>8320</td></tr></table></body></html>

根据表3，基于CHAMP卫星数据的二维Taylor模型在截断阶数 $N { < } 6$ 时， $X , Y , Z , F$ 分量的RMSE随 $N$ 的增大而迅速减小，平均下降幅度达到了 $60 . 6 2 \%$ ,其中 $X$ 分量由1阶的 $5 4 9 5 ~ \mathrm { n T }$ 减小为

6阶的 $1 7 . 8 5 ~ \mathrm { n T } , Y$ 分量从1阶的 $1 4 5 3 ~ \mathrm { n T }$ 减少为6阶的 $1 5 . 4 3 ~ \mathrm { n T } , Z$ 分量从 $1 0 3 3 2 ~ \mathrm { n T }$ 减少为 $3 2 . 1 0 ~ \mathrm { n T } , F$ 总量由 $4 7 1 0 \ \mathrm { n T }$ 减小为 $2 5 , \ 2 3 \ \mathrm { \ n T }$ ；当 $N$ 为 $6 \sim 1 0$ 时，RMSE平均减少幅度为 $2 . 9 6 \%$ ，逐渐趋于平稳；当 $N { > } 1 0$ 时，二维模型也出现了“龙格现象”,RMSE值大幅增加.

为了进一步比较，绘制了两模型当 $N = 1 \sim 1 1$ 时的RMSE变化（见图7).由图7可知，当 $N$ 为 $1 \sim$ 5时，三维模型的RMSE值均小于二维模型，当$N = 5$ 时，三维模型中 $X$ 分量和 $F$ 总量的RMSE值都要远小于8阶二维模型的 $X$ 分量和 $F$ 总量，而 $Z$ 分量与 ${ 7 } \mathrm { \sim } 1 0$ 阶的二维模型值非常接近，三维模型的5阶 $Y$ 分量则略大于8阶的二维模型.综合考虑磁场分布、残差分布以及RMSE的比较，现认为5阶的三维Taylor模型与8阶的二维Taylor模型具有相近的精度，且在 $X$ 分量和 $F$ 总量上三维模型的精度甚至更高.

通过比较发现，三维模型在 $N$ 为 $1 \sim 5$ 时RMSE值比对应的二维模型平均要小 $4 5 . 8 \%$ ，另外根据两种模型的系数个数，认为在基于CHAMP卫星数据以模拟中国地区地磁场的情况下，较低阶的三维模型可反映更多的地磁场信息，其精度相当于高阶的二维模型.

为了进一步观察两模型，并考虑到存在的差异，列出了 $N = 3$ 时两模型的系数，见表4，表5.

![](images/24b86262feae7d1af76954f347684d74e271cf2842f6c17b167e7c106d3ab917.jpg)  
图7二维及三维Taylor多项式模型的RMSE随截断阶数 $N$ 的变化；单位：nT

Fig.7The relationship between RMSE and $N$ of elements $X , Y , Z , F$ in 2D and 3D Taylor polynomial model；units：n]

Table 4The coefficients of 3D Taylor polynomial model while $N$ is3   
表53阶二维Taylor多项式模型系数  

<html><body><table><tr><td>coeff</td><td>X</td><td>Y</td><td>Z</td><td>F</td><td>coeff</td><td>X</td><td>Y</td><td>Z</td><td>F</td></tr><tr><td>A111</td><td>2.6356×104</td><td>-1. 1184×10</td><td>3.6920×104</td><td>4.5378×104</td><td>A223</td><td>4.0196×10-2</td><td>9.2792×10-3</td><td>-2.2684×10-2</td><td>-1.8737×10-2</td></tr><tr><td>A112</td><td>1. 8244×100</td><td>2.8360×101</td><td>-3.0513×101</td><td>-4.7863×101</td><td>A231</td><td>9.7056×10-2</td><td>—1.4293×10-2</td><td>-5.9247×10-2</td><td>-1.7627×10-2</td></tr><tr><td>A113</td><td>9.3890 ×100</td><td>2.5699×101</td><td>-5.4618×100</td><td>-5.7399×10°</td><td>A232</td><td>-2.3759×10-3</td><td>-3.7049×10-2</td><td>—2.5003×10-2</td><td>—2.7506×10-2</td></tr><tr><td>A121</td><td>8.5038×10°</td><td>-7.7084×101</td><td>-5.8756×101</td><td>－4.0083×101</td><td>A233</td><td>1.2984×10-3</td><td>—1.1612×10-3</td><td>4.2343×10-4</td><td>7. 4171×10-4</td></tr><tr><td>A122</td><td>-2.4694×10-1</td><td>5.7523×10-1—1.1463×100</td><td></td><td>-7.0559×10-1</td><td>A311</td><td>-5.0897×100</td><td>2.0020×10°</td><td>-1.4831×101</td><td>-3.1636×100</td></tr><tr><td>A123</td><td>2.9190×10-1</td><td>-1.9139×100</td><td>7.8564×10-1</td><td>4.7338×10-1</td><td>A312</td><td>-1.1852×100</td><td>-6.4037×10-3</td><td>7.7148×10-1</td><td>1. 8777 ×100</td></tr><tr><td>A131</td><td>-8.4217×10-1</td><td>1.1318×10-1—3.4192×100</td><td></td><td>-3.1678×100</td><td>A313</td><td>-6.4995×10-4</td><td>-3.3960×10-3</td><td>2.3336×10-2</td><td>3.8016×10-2</td></tr><tr><td>A132</td><td>9.0272×10-4</td><td>-1.4263×10-1</td><td>2.8775×10-2</td><td>1.3662×10-2</td><td>A321</td><td>—1.5394×10-2</td><td>3.6781×10-3</td><td>1.0011×10-1</td><td>4.6874×10-2</td></tr><tr><td>A133</td><td>-4.9521×10-3</td><td>—8.6342×10-²—6.7235×10-2</td><td></td><td>—7.8745×10-2</td><td>A322</td><td>1.5478×10-²</td><td>2.6794×10-3</td><td>-1.2601×10-3</td><td>-2.4206×10-3</td></tr><tr><td>A211</td><td>-5.6348×10²</td><td>-3.2395×10-1</td><td>9.8169×10²</td><td>4.6313×10²</td><td>A323</td><td>3.4452×10-4</td><td>3.2986×10-4</td><td>-3.5591×10-4</td><td>-3.8670×10-4</td></tr><tr><td>A212</td><td>4.0267×10°</td><td>9.9163×100</td><td>-8.5600×10-1</td><td>7.5899×10-1</td><td>A331</td><td>5.2130×10-4</td><td>3.3949×10-3</td><td>1.2816×10-3</td><td>-5.9806×10-4</td></tr><tr><td>A213</td><td>2.7306×100</td><td>1. 1916×10-1</td><td>1.7439×100</td><td>4.1502×100</td><td>A332</td><td>5.0862×10-4</td><td>2.3039×10-4</td><td>-5.6094×10-4</td><td>-1.7193×10-5</td></tr><tr><td>A221</td><td>2.0462×100</td><td>—2.9027×10°</td><td>1.4973×10-1</td><td>5.4465×10-1</td><td>A333</td><td>-8.4805×10-6</td><td>-3.1064×10-5</td><td>-4.6306×10-6</td><td>5.6562×10-6</td></tr><tr><td>A222</td><td>4.7735×10-2</td><td>-6.4648×10-1</td><td>2.2293×10-1</td><td>9.0850×10-2</td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

表43阶三维Taylor多项式模型系数  
Table 5The coefficients of 2D Taylor polynomial model while $N$ is3   

<html><body><table><tr><td>coeff</td><td>X</td><td>Y</td><td>Z</td><td>F</td><td>coeff</td><td>X</td><td>Y</td><td>Z</td><td>F</td></tr><tr><td>A11</td><td>2. 6334×104</td><td>-1.1095×103</td><td>3.6768×104</td><td>4.5286×104</td><td>A21</td><td>-5.3071×100</td><td>1.0536×10</td><td>-1.3394×101</td><td>-2.3098×10°</td></tr><tr><td>A12</td><td>5.0955×102</td><td>-3.9682×10-1</td><td>9.5088×10²</td><td>4.2726×102</td><td>A22</td><td>1.8126 ×10°</td><td>2.8480×10°</td><td>2.4282×10-1</td><td>6.2468×10-1</td></tr><tr><td>A13</td><td>6. 7776×100</td><td>-7.1202×101</td><td>-4.8903×101</td><td>-3.4906×101</td><td>A23</td><td>-7.6290×10-1</td><td>1.0246×10-1</td><td>3.0339×100</td><td>2.9828×100</td></tr></table></body></html>

由表4和表5可知，两种模型在第一项系数上非常接近，而且在数值上比其他项系数大2到3个数量级，因此两种模型在拟合结果以及分布都非常接近.相比于二维模型，三维模型的系数个数约为二维模型的4倍，地磁模型的系数能反映地磁场强度等信息，如IGRF模型中各阶系数能反映偶极子场和各阶非偶极子场的强度信息，当 $N { > } 1 3$ ，认为球谐模型的系数即反映了不同波长所对应的岩石圈磁场的强度信息.Taylor多项式模型的各阶系数从地球物理的角度而言，应包含了区域地磁场不同尺度的强度信息，但由于其为区域模型，并不具备正交性，因此是很难从功率谱的角度定量地分析不同尺度的区域地磁场与不同阶系数的关系，故三维模型具备更多系数的具体含义，也是以后工作中需要考虑的问题.

# 4 结论与讨论

本文基于CHAMP卫星的网格数据运用三维Taylor多项式模型计算并绘制了2010.0年中国及邻近地区的地磁场分布，并通过对比，分析了两种模型的残差分布、截断阶数与RMSE等.结果显示 5阶的三维Taylor模型与8阶的二维Taylor模型具有相近的精度.通过比较两种模型的拟合值、残差分布，截断阶数与RMSE值等，显示三维模型都要优于同阶的二维模型，并认为较低阶的三维模型可以得到与高阶二维模型相近，甚至更好的拟合效果，并得出以下结论：

(1)相较于其他二维模型，如二维Taylor多项式模型、曲面Spline等，三维Taylor 模型考虑了高度因素，在中国及邻近地区，海拔高度为一 $4 \sim 8 ~ \mathrm { k m }$ 左右，而地磁场一般随高度呈 $2 0 ~ \mathrm { n T / k m }$ 左右的速率衰减，因此三维Taylor模型相较于二维模型有了本质的提高.本研究使用了高精度、高密度的CHAMP卫星的标量和矢量数据，基于此建立的中国地区三维模型，相较于IGRF11、甚至球冠谐模型，不仅计算方便，而且精度相当甚至更高.

(2)三维Taylor多项式模型为完整展开的拟合模型，其系数数量为相同截断阶数下的二维模型的$\frac { 2 N ^ { 2 } } { N + 1 }$ 倍，约为 $2 N$ 倍，因此认为三维模型在较低的截断阶数下可以反映出更多的地磁场信息.然而由于系数数量随截断阶数的增加呈现指数式上升，因此三维模型也较易出现“龙格现象”.

(3)本研究显示了较低阶数的三维模型，其RMSE与较高阶数的二维模型接近，通过比较两种模型不同截断阶数对应的RMSE值、以及磁场和残差分布，认为三维模型每一阶的RMSE和残差绝对值的平均值均要比二维模型的小约 $45 \%$

通过计算还发现二维模型的边界畸变很大，而三维模型的边界效应相对较小.原因在于，在完整展开的三维模型中，我们取的截断阶数为 $N$ 不是很大，“龙格现象”尚未得以发展（柳士俊等，2011）.

二维Taylor模型只考虑了经度与纬度，忽略了高度的因素.因此二维模型由于本身的限制，所计算的地磁场强度会存在一定的误差.针对上述缺点，结果显示三维模型可以更准确地描述地磁场的空间分布.之所以采用完整展开，是因为可在较少的截断阶数计算出更多的系数，从而提高效率.

由于缺乏2010.0年的地面实测数据，因此研究只展示了卫星高度处的地磁场分布，今后若可获取地面及海洋地区，甚至航磁数据，可尝试从不同高度联合建立三维Taylor多项式模型，该模型的空间适用范围为地面至卫星高度，因此适合进行空间磁场的应用研究.若结合 TO4（Tsyganenko and Sitnov，2005）、CM4等模型，可进一步模拟区域外源场以及岩石圈磁场的形态分布（冯彦等，2010b；2014b).综上所述，三维Taylor模型具有计算简单、使用方便、且具有相当的模拟精度，适于进行区域三维地磁场的研究.

致谢感谢空间天气学国家重点实验室开放课题以及德国地球科学研究中心对本文提供的帮助

# References

Alldredge L R.1981. Rectangular Harmonic analysis applied to the Geomagnetic field.J.Geophys.Res.，86(B4)：3021-3026.   
Alldredge L R. 1982.Geomagnetic local and regional Harmonic analyses.J.Geophys.Res.，87(B3)：1921-1926.   
An Z C，Xu Y F，1981.Methods of computation of geomagnetic field at greater altitude in a local region.Chinese Journal of Space Science.(in Chinese)，1(1)：68-73.   
An ZC，Xu YF，Xia G H，et al.1982.Mathematical method to express the distribution of geomagnetic field and its secular variation in a local area.Acta Geophysica Sinica (in Chinese)， 25(S):711-717.   
An ZC，Xu YF，Wang YH.199la.Derivation and analysis of the main geomagnetic field models in China for 1950—198o.Acta Geophysica Sinica (in Chinese)，34(5)：585-593.   
AnZC，WangYH，Xu YF.1991b.Calculations and analyses of 14-∠5.   
An Z C. 2ool. Analyses and discussions of the geomagnetic field polynomial models. Chinese J.Geophys.(in Chinese)，44(S)： 45-50，doi:10.3321/j.issn:0001-5733.2001.z1.007.   
Chen B,Gu Z W，Gao JT，et al. 2o11. Analyses of geomagnetic field and its secular variation over China for 2Oo5.O epoch using Spherical Cap Harmonic method.Chinese J.Geophys.(in Chinese)， 54(3)：771-779. doi:10.3969/j.issn.0001-5733.2011.03.017.   
Duzgit Z，Baydemir N，Malin S R C. 1997. Rectangular polynomial analysis of the regional geomagnetic field. Geophys. J. Int., 128(3): 737-743.   
Feng Y，An Z C，Sun H，et al. 2010a.Geomagnetic survey satellites.Progress in Geophysics (in Chinese)，25(6)：1947- 1958.doi:10.3969 /j.issn.1004-2903.2010.06.009.   
Feng Y，An Z C，Sun H，et al． 20l0b. Analysis of variation in geomagnetic field of Chinese mainland based on comprehensive model CM4.Acta Physica Sinica (in Chinese)，59(12)：8941- 8953.   
Feng Y，Pan JJ，An Z C,et al. 201Oc. Calculation and analysis of geomagnetic field horizontal gradients in China. Chinese $J$ ： Geophys.（in Chinese)，53(12)：2899-2906．doi:10.3969/j. issn. 0001-5733.2010.12.013.   
Feng Y，Jiang Y，Sun H，et al. 2Ol4a. A study on variations of non-dipole magnetic field over Chinese mainland during 2000 BC to 1990 AD. Science China （Earth Sciences），57（6）:1229- 1244.doi:10.1007/s11430-013-4674-6.   
Feng Y,Sun H，An ZC，et al. 2Ol4b. A study on lithospheric field based on geomagnetic model with high precision and power spectrum. Progress in Geophysics (in Chinese)，29(2): 478- 487.doi:10.6038/pg20140202.   
Gao J T，An Z C，Gu Z W，et al.2005.Selections of the geomagnetic normal field and calculations of the geomagnetic anomalous field. Chinese J.Geophys.(in Chinese)，48(1)：56- 62，doi:10.3321/j.issn:0001-5733.2005.01.010.   
Gao JT，An ZC，Gu Z W，et al.2006．Distributions of the geomagnetic field and its secular variations expressed by the surface Spline method in China （a part） for 19o0—1936. ChineseJ.Geophys.（in Chinese），49(2）：398-407，doi：10. 3321/j.issn:0001-5733.2006.02.013.   
Haines G V. 1985. Spherical cap harmonic analysis of geomagnetic secular variation over Canada 1960-1983. J. Geophys.Res.，90 (B14)：12563-12574.   
Hurwitzd L，Knapp D G，Nelson JH，et al. 1966.Mathematical Model of the Geomagnetic Field for l965.J.Geophys. Res., 71(9): 2373-2383.   
IAGA，Working Group V-MOD.2O03．The 9th Generation International Geomagnetic Reference Field. Physics of the Earth and Planetary Interiors，140(4):253-254.   
IAGA，Working Group V-MOD.2005． The 10th Generation International Geomagnetic Reference Field. Physics of the 183(3)：1216—1230.   
Kang G F,Gao G M,Bai C H，et al. 2009.Characteristics of the secular variation and secular acceleration distributions of the main geomagnetic field for the CHAMP satelite. Chinese $J$ ： Geophys.（in Chinese），52（8)：1976-1984，doi:10.3969/j. issn. 0001-5733. 2009.08.004.   
KangGF，Gao G M，BaiCH，et al.20lo.Distribution of the magnetic anomaly of the CHAMP satellite in China and adjacent areas.ChineseJ．Geophys.（in Chinese），53（4)：895-903， doi:10.3969/j.issn.0001-5733. 2010.04.014.   
Liu SJ,Zhou XG,Sun H,et al. 2011. The three dimension Taylor polynomial method for the calculation of regional geomagnetic field model. Progress in Geophysics (in Chinese)，26(4)：1165- 1174.doi:10.3969/j.issn.1004-2903.2011.04.005.   
Maus S,Luhr H，Rother M，et al.2OO7．Fifth-generation lithospheric magnetic field model from CHAMP satelite measurements. Geochem. Geophys.Geosyst.，8(5)． doi:10.1029/2006GC001521.   
Olsen N，Luhr H,Sabaka T J,et al. 2006.CHAOS-a model of the Earth's magnetic field derived from CHAMP,Orsted，and SACC magnetic satelite data. Geophys. J. Int.，166(1)： 67-75.   
Olsen N，Mandea M，Sabaka T J，et al. 2010．The CHAOS-3 geomagnetic field model and candidates for the 1lth generation IGRF.Earth Planets and Space，62(10):719-727.   
Sabaka T J，Olsen N，Purucker M E. 2OO4．Extending comprehensive models of the Earth's magnetic field with Orsted and CHAMP data.Geophys.J. Int.，159(2)：521-547.   
Thébault E，Schott JJ，Mandea M，et al. 2004.A new proposal for spherical cap harmonic modelling.Geoph ys.J.Int.，159（1）： 83-103.doi:10.1111/j.1365-246X.2004.02361.x.   
Thébault E，Schott J J，Mandea M. 2O06.Revised spherical cap harmonic analysis（R-SCHA）：Validation and properties.J. Geophys.Res.，111(B1)：B01102，doi:10.1029/2005JB003836.   
Thébault E，Gaya-Piqué L. 2oo8.Applied comparisons between SCHA and R-SCHA regional modeling techniques. Geochem. Geophys.Geosyst.，9(7):Q07005，doi:10.1029/2008GC001953.   
Thebault E. 2008. A proposal for regional modeling at the Earth's surface.R-SCHA2D.Geophys.J. Int.，174（1)：118-134. doi:10.1111/j.1365-246X.2008.03823.x.   
Tsyganenko N A，Sitnov MI. 2005. Modeling the dynamics of the inner magnetosphere during Strong geomagnetic storms. J. Geophys.Res.，110(A3)：A03208.doi:10.1029/2004JA010798.   
Xu W Y，Tschu K K. 1984. A study of the RHA for the geomagnetic field of China and neighbouring region. Acta Geophysica Sinica (in Chinese)，27(6)：511-522.   
Xu Y F,Wang Y H,An Z C. 1992. An analysis and the models of the geomagnetic secular variation in China for 1950—1985.Acta Geophysica Sinica (in Chinese)，35(6)：740-747.   
Yang Y T，Shi Z Y,Guan Z Z，et al. 20o9. A method of improving regional geomagnetic field model boundary effect. Progress in Geophysics.（in Chinese)，24(2):468-474，doi：10.3969/j.   
issn.1004-2903.2009.02.013.

# 附中文参考文献

安振昌，徐元芳．1981．局部地区高空磁场的计算方法．空间科学学报，1(1)：68-73.  
安振昌，徐元芳，夏国辉等．1982．表示局部地区地磁场及其长期变化分布的数学方法．地球物理学报，25(增刊)：711-717.  
安振昌，徐元芳，王月华．1991a. $1 9 5 0 \sim 1 9 8 0$ 年中国地区主磁场模型的建立及分析．地球物理学报，34(5)：585-593.  
安振昌，王月华，徐元芳．1991b.中国及邻近地区地磁垂直梯度的计算与研究．空间科学学报，11（1)：14-23.  
安振昌．2001.地磁场多项式模型的分析与讨论．地球物理学报，44（增刊)：45-50，doi：10.3321/j.issn:0001-5733.2001.zl.007.  
陈斌，顾左文．高金田等．2011．2005.0年代中国地区地磁场及其长期变化球冠谐和分析．地球物理学报，54（3)：771-779，doi：10.3969/j.issn.0001-5733.2011.03.017.  
冯彦，安振昌，孙涵等．2010a.地磁测量卫星.地球物理学进展，25(6)：1947-1958，doi:10.3969/j.issn.1004-2903.2010.06.009.  
冯彦，安振昌，孙涵等．2010b.利用地磁场综合模型CM4分析中国大陆地区地磁场变化．物理学报，59(12)：8941-8953.  
冯彦，潘剑君，安振昌等.2010c.中国地区地磁场水平梯度的计算与分析．地球物理学报，53（12)：2899-2906，doi：10.3969/j.issn.0001-5733.2010.12.013.  
冯彦，孙，安振昌等．2014b.基于高精度地磁模型与功率谱技术的岩石圈磁场研究．地球物理学进展，29（2)：478-487，doi：10.6038/pg20140202.  
高金田，安振昌，顾左文等．2005．地磁正常场的选取与地磁异常场的计算．地球物理学报，48(1)：56-62，doi：10.3321/j.issn：0001-5733.2005.01.010.  
高金田，安振昌，顾左文等．2006．用曲面SPLINE方法表示1900—1936年中国(部分地区)地磁场及其长期变化的分布.地球物理学报，49（2)：398-407，doi：10.3321/j.issn：0001-5733.2006.02.013.  
康国发，高国明，白春华等．2009．CHAMP卫星主磁场长期变化和长期加速度的分布特征．地球物理学报，52（8)：1976-1984，doi：10.3969/j.issn.0001-5733.2009.08.004.  
康国发，高国明，白春华等．2010．中国及邻近地区CHAMP卫星磁异常的分布特征．地球物理学报，53（4)：895-903，doi：10.3969/j.issn.0001-5733.2010.04.014.  
柳士俊，周小刚，孙涵等．2011．用于区域地磁场模型计算的三维Taylor多项式方法．地球物理学进展，26(4)：1165-1174，doi：10.3969/j.issn.1004-2903.2011.04.005.  
徐文耀，朱岗昆．1984．我国及邻近地区地磁场的矩谐分析．地球物理学报，27(6)：511-522.  
徐元芳，王月华，安振昌．1992．1950—1985年中国地磁长期变化的模型和分析．地球物理学报，35(6)：740-747.  
杨云涛，石志勇，关贞珍等．2009．一种改善区域地磁场模型边界效应的方法．地球物理学进展，24(2)：468-474，doi：10.3969/j.issn.1004-2903.2009.02.013.

(本文编辑胡素芳)