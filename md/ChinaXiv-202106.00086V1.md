# 塔里木河下游生态输水对地表水体面积变化的影响

邹珊1,23.4，吉力力·阿不都外力1,2.3，黄文静1²，段伟利1.2

(1.中国科学院新疆生态与地理研究所,荒漠与绿洲生态国家重点实验室,新疆 乌鲁木齐830011;2.中国科学院大学,北京100049；3.中国科学院中亚生态与环境研究中心,新疆 乌鲁木齐830011;4.根特大学地理系,比利时 根特 9000)

摘要：以河湖为主体的塔里木河下游地表水体的面积受到输水工程的影响,在区域水循环、调节水平衡中扮演着重要角色。基于近20a塔里木河下游Landsat5、Landsat7和Landsat 8影像资料和生态输水数据，综合采用GoogleEarthEngine(GEE)计算平台和多元统计分析方法，对地表水体面积变化及其对生态输水的响应进行了系统分析。结果表明：(1)2000—2019年，塔里木河下游区域的地表水体、季节性水体和永久性水体的面积均呈现波动上升趋势，速率分别为 $1 5 . 5 4 ~ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 、$7 . 1 2 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ 和 $8 . 4 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;塔里木河下游上段(大西海子水库一英苏，不包括大西海子水库）、中段(英苏—阿拉干)和下段(阿拉干一台特玛湖)区域的季节性水体和永久水体面积也均呈现波动增加趋势，其中下段区域的增加速率最大，其值分别为 $5 . 2 3 \ \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ 和 $8 . 2 4 ~ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 } \circ$ (2）生态输水引起的地表水体面积增加主要表现在台特玛湖湖区,2019年台特玛湖湖区的地表永久水体和季节性水体面积分别约为 $2 6 7 . 2 7 ~ \mathrm { k m } ^ { 2 }$ 和 $1 8 8 . 0 0 \mathrm { k m } ^ { 2 }$ ，总体水面积约为 $4 5 5 . 2 7 ~ \mathrm { k m } ^ { 2 }$ ，相比2000年（约 $3 8 . 1 9 \mathrm { k m } ^ { 2 } \mathrm { \Omega }$ 0增加了 $4 1 7 . 0 8 ~ \mathrm { k m } ^ { 2 }$ （约10.92倍)。(3)近20a来，研究区域地表水体面积，尤其是永久水体面积变化与塔里木河下游生态输水量密切相关;2007—2009年输水量下泄水量较少，直接导致研究区域在2009年地表水体和季节性水体的面积均减少到最低点。研究结果有助于全面理解塔里木河下游生态输水对地表水体变化的影响，为区域水生态保护提供科学依据。

关 键词：塔里木河；地表水体；生态输水；时空变化；影响分析；谷歌地球引擎文章编号：

近年来，受全球气候变化和人类活动的双重影响，塔里木河从20世纪50年代开始出现了河道断流、河湖水系肢解、湖泊萎缩及水环境恶化等现象，危及到流域原本脆弱的生态环境，引发了一系列生态环境问题，严重制约了区域经济社会的可持续发展[1-4]。为此,国务院在2001年批复实施了《塔里木河近期综合治理规划》,正式启动了塔里木河流域综合治理工程。截至2019年年底，塔里木河下游输水工程已实施了 $2 0 \textrm { a }$ ，区域地表水体面积得到恢复、地下水埋深得到明显抬升及生态环境出现好转等[5-8]。其中,以河湖为主体的地表水体面积变化受到塔里木河下游输水工程的影响，在参与塔里木河下游水循环、调节水平衡中扮演着重要角色，也是区域人类最易获取的水资源。纵观针对塔里木河下游输水工程影响的研究进展[9-10],目前关于近20 a来塔里木河下游地表水体面积变化及其对生态输水响应的系统研究还比较少。

2010年谷歌推出的GoogleEarthEngine（GEE）云计算平台，整合了多源数据并结合了云平台强大的运算能力，能够快速获取和处理海量遥感影像。目前GEE已被广泛应用于大规模地理空间数据分析，为全球和大尺度流域或区域的资源环境动态监测、时空变化特征解析提供了强大的技术支撑，解决了传统海量遥感影像处理分析的计算复杂、成本

# 干吴区地理

高昂等问题[1I-15],为我们研究塔里木河下游区域地表水体时空变化提供了技术支持。因此，本文选取塔里木河下游区域为研究对象，聚焦以河湖为主体的地表水体面积，采用GEE平台、综合多种统计分析方法，系统解析了近20a塔里木河下游区域地表水体面积的变化特征，并探讨生态输水对地表水体面积的影响，为生态输水后区域水资源的合理利用、生态环境保护等提供科学依据

# 1研究区、数据与方法

# 1.1 研究区概况

塔里木河下游生态输水工程最初是从大西海子水库向下游河道输水，输水量为大西海子水库的下泄水量，因此本文的研究区域为大西海子水库末端(不包括大西海子水库)到台特玛湖的河流周边$1 0 \mathrm { k m }$ 的缓冲区域(图1)。同时，为了准确解析生态输水对地表水体面积时空变化的影响，将研究区分为上段（大西海子水库一英苏，不包括大西海子水库）、中段(英苏一阿拉干)和下段(阿拉干一台特玛湖)3个区域。

![](images/f29ff0cd24571c7709f0f4cf9d6d91274eba32e6a1a3535ec19a86fa110580b6.jpg)  
图1塔里木河下游区域概况  
Fig.1 Overviewof the lowerreaches of TarimRiver

# 1.2主要数据

1.2.1 影像数据本文主要基于GEE云计算平台，通过编程运算获得研究区域2000—2019年所有可利用的Landsat5、Landsat7和Landsat8影像。覆盖本文研究区域的影像有4景，总计影像为2597张，其中Landsat5为759张、Landsat7为1256张和Landsat8为582张。2012年使用的是Landsat7影像数据，2012年前主要使用Landsat5和Landsat7影像数据，2012年后主要使用Landsat7和Landsat8影像数据。

1.2.2生态输水数据截至2019年年底，向塔里木河下游生态输水共20次（表1），总计输水 $8 1 . 6 4 \times$ $1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,其中塔里木河向下游输水 $6 7 . 7 8 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ （约占输水总量的 $8 3 . 0 3 \%$ )，孔雀河输水 $1 3 . 8 6 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ （约占 $1 6 . 9 7 \%$ )。输水量最大的年份为2018年，全部由塔里木河干流向下游输水，达到 $1 2 . 1 5 { \times } 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ;输水量最小的年份为2008年，输水量为0。

表12000—2019年塔里木河下游生态输水情况  
Tab.1 Amount of ecological water conveyance in the lowerreachesof TarimRiver from2ooo to 2019   

<html><body><table><tr><td rowspan="2">次数</td><td rowspan="2">时间</td><td colspan="3">大西海子水库下泄水量/10m</td></tr><tr><td>孔雀河</td><td>塔里木河</td><td>合计</td></tr><tr><td>1</td><td>2000年5—7月</td><td>9923</td><td>0</td><td>9923</td></tr><tr><td>2</td><td>2000年11—12月</td><td>22655</td><td>0</td><td>22655</td></tr><tr><td>3</td><td>2001年4—11月</td><td>34733</td><td>3490</td><td>38223</td></tr><tr><td>4</td><td>2002年7—11月</td><td>24500</td><td>8629</td><td>33129</td></tr><tr><td>5</td><td>2003年3—11月</td><td>24000</td><td>38509</td><td>62509</td></tr><tr><td>6</td><td>2004年4—6月</td><td>7350</td><td>2857</td><td>10207</td></tr><tr><td>7</td><td>2005年4—11月</td><td>5246</td><td>23026</td><td>28272</td></tr><tr><td>8</td><td>2006年9—11月</td><td>2700</td><td>16944</td><td>19644</td></tr><tr><td>9</td><td>2007年10月</td><td>1410</td><td>0</td><td>1410</td></tr><tr><td>10</td><td>2009年12月</td><td>1066</td><td>0</td><td>1066</td></tr><tr><td>11</td><td>2010年6—11月</td><td>0</td><td>36393</td><td>36393</td></tr><tr><td>12</td><td>2011年1—11月</td><td>0</td><td>85211</td><td>85211</td></tr><tr><td>13</td><td>2012年4—11月</td><td>0</td><td>66716</td><td>66716</td></tr><tr><td>14</td><td>2013年4—11月</td><td>0</td><td>48769</td><td>48769</td></tr><tr><td>15</td><td>2014年6月</td><td>0</td><td>727</td><td>727</td></tr><tr><td>16</td><td>2015年8—11月</td><td>0</td><td>46128</td><td>46128</td></tr><tr><td>17</td><td>2016年8—10月</td><td>0</td><td>67611</td><td>67611</td></tr><tr><td>18</td><td>2017年4—12月</td><td>0</td><td>121461</td><td>121461</td></tr><tr><td>19</td><td>2018年2—11月</td><td>0</td><td>70006</td><td>70006</td></tr><tr><td>20</td><td>2019年8—12月</td><td>5002</td><td>41351</td><td>46353</td></tr></table></body></html>

# 1.3研究方法

1.3.1地表水体提取算法本文首先利用遥感影像数据计算研究区域的归一化植被指数(NDVI)、归一化差异水体指数（ $\operatorname { i n N D V I }$ )和增强植被指数(EVI)，计算公式如下所示：

$$
\mathrm { N D V I } = { \frac { \rho _ { \mathrm { N I R } } - \rho _ { \mathrm { R e d } } } { \rho _ { \mathrm { N I R } } + \rho _ { \mathrm { R e d } } } }
$$

$$
\mathrm { \ m N D W I } = \frac { \rho _ { \mathrm { G r e e n } } - \rho _ { \mathrm { S W I R } } } { \rho _ { \mathrm { G r e e n } } + \rho _ { \mathrm { S W I R } } }
$$

$$
\mathrm { E V I } = 2 . 5 \times \frac { \rho _ { \mathrm { N I R } } - \rho _ { \mathrm { R e d } } } { \rho _ { \mathrm { N I R } } + 6 . 0 \rho _ { \mathrm { R e d } } - 7 . 5 \rho _ { \mathrm { B l u e } } + 1 }
$$

式中： $\rho _ { \mathrm { B l u e } } \mathrm { ~ \setminus ~ } \rho _ { \mathrm { G r e e n } } \mathrm { ~ \setminus ~ } \rho _ { \mathrm { R e d } } \mathrm { ~ \setminus ~ } \rho _ { \mathrm { N I R } }$ 和 $\rho _ { \mathrm { { s w I R } } }$ 分别代表蓝光波段 $( 0 . 4 5 \mathrm { \sim } 0 . 5 2 ~ \mu \mathrm { m } )$ ）、绿光波段 $( 0 . 5 2 { \sim } 0 . 6 0 ~ \mu \mathrm { m } )$ ）红光波段 $( 0 . 6 3 \mathrm { \sim } 0 . 6 9 \ \mu \mathrm { m } )$ ）、近红外光波段 $( 0 . 7 7 \sim$ $0 . 9 0 \mu \mathrm { m }$ )和短波红外波段 $( 1 . 5 5 { \sim } 1 . 7 5 ~ \mu \mathrm { m } )$ ）

当 $\mathrm { \ m N D W I { > } E V I }$ 或 $\mathrm { \ m N D W I { > } N D V I { \Sigma } }$ 时表示影像像素中的植被信号比水信号弱，说明该像素可以被作为水体。同时，利用 $\mathrm { E V I } { < } 0 . 1$ 这一标准来尽可能减少湿地植被信号对湿地水体信号提取的干扰[16]。随后，通过计算每一幅遥感影像水体出现的频率来判定季节性水体和永久水体。对于塔里木河下游的每个Landsat像素，用下述公式计算其1a的水体频率：

$$
F ( y ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N _ { y } } \omega _ { y , i } \times 1 0 0 \%
$$

式中： $F$ 是像素的水体频率计算指数； $y$ 是2000—2019年的年份； $N _ { _ { y } }$ 是第 $y$ 年中该像素的Landsat影像所观测值总数; $\omega _ { y , i }$ 表示该像素的一个观测值是否为水体，其中1表示水体，而0表示非水体。通过计算水体频率，按照 $7 5 \%$ 以上为永久性水体、 $2 5 \% \sim$ 75%为季节性水体和小于25%为非水体的规则[17-18],确定研究区域的非水体(像元值设为0）、季节性水体(值设为1)和永久水体(值设为2)，总的地表水体面积为季节性水体面积和永久水体面积之和。

1.3.2Mann-Kendall检验法本文采用非参数Mann-Kendall趋势检验法（M-K检验法)[19-22]分析地表水体面积的时间变化趋势。该方法对待检验的地表水体面积的时间序列 $\{ T _ { 1 } , T _ { 2 } , \cdots , T _ { n } \}$ ,构造了一个统计变量 $S ^ { [ 2 0 - 2 1 ] }$ ·

$$
S = \sum _ { i = 1 } ^ { n - 1 } \sum _ { j = i + 1 } ^ { n } \mathrm { s i g n } ( T _ { j } - T _ { i } )
$$

$$
\mathrm { s i g n } ( T _ { j } - T _ { i } ) { = } \left\{ 0 \begin{array} { l l } { { \mathrm { ~ i f ~ } T _ { j } - T _ { i } > 0 } } \\ { { 0 } } & { { \mathrm { i f ~ } T _ { j } - T _ { i } = 0 } } \\ { { - 1 \ \mathrm { i f ~ } T _ { j } - T _ { i } < 0 } } \end{array} \right.
$$

式中： $\mathbf { \Omega } _ { n }$ 为20(2000—2019年）; $\mathrm { s i g n } ( x )$ 为相应的符号函数。基于“待检验地表水体面积无变化趋势”的假设。一般统计量 $s$ 在 $n \geqslant 1 0$ 时服从标准正态分布(均值为0)，方差由如下公式计算：

$$
\sigma ^ { 2 } = \frac { n ( n - 1 ) ( 2 n + 5 ) - \sum t _ { i } ( i ) ( i - 1 ) ( 2 i + 5 ) } { 1 8 }
$$

由此设计的M-K统计量 $( Z )$ 为

$$
Z = \left\{ \begin{array} { l l } { \frac { S - 1 } { \sigma } } & { \ S > 0 } \\ { 0 } & { \ S = 0 } \\ { \frac { S + 1 } { \sigma } } & { \ S < 0 } \end{array} \right.
$$

当 $Z > 0$ 时，表示地表水体面积呈增加趋势；当$Z < 0$ 时，表示地表水体面积呈减少趋势。当 $Z \geqslant$ 1.96时，表示通过 $\alpha = 0 . 0 5$ 的显著性水平检验；当$Z \geqslant 2 . 5 8$ 时,表示通过 $\alpha = 0 . 0 1$ 的显著性水平检验。

1.3.3相关系数分析本文采用皮尔逊(Pearson)相关系数法[23-24]计算2000—2019年塔里木河下游地表水体面积与生态输水量之间的相关性。其计算公式为[23]：

$$
r = \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( X _ { i } - \bar { X } ) ( Y _ { i } + \bar { Y } ) } { \sqrt { \displaystyle \sum _ { i = 1 } ^ { n } ( X _ { i } + \bar { X } ) ^ { 2 } } \sqrt { \displaystyle \sum _ { i = 1 } ^ { n } ( Y _ { i } + \bar { Y } ) ^ { 2 } } }
$$

式中： $\boldsymbol { r }$ 为水体面积与输水量之间的相关系数； $X _ { i }$ 和 $Y _ { _ i }$ 分别为2个变量的年序列； $\bar { X }$ 和 $\bar { Y }$ 为年均值; $n$ 为20(2000—2019年）。 $\boldsymbol { r }$ 处于-1到1之间，正值表示正相关，负值表示负相关，其绝对值越大，相关性越强，越接近于0,相关度越弱。一般认为， $\left| r \right| < 0 . 2$ 时,为相关程度极弱(或不相关); $0 . 2 \leqslant | r | < 0 . 4$ 时，为弱相关; $0 . 4 \leqslant \left| r \right| < 0 . 6$ 时,为中等程度相关； $0 . 6 \leqslant$ $\left| r \right| < 0 . 8$ 时,为强相关； $0 . 8 \leqslant | r | < 1$ 时，为极强相关。

# 2结果与分析

# 2.1地表水体面积时间变化分析

图2和表2显示了2000—2019年塔里木河下游地表水体面积变化的分析结果。2000—2019年塔里木河下游的地表水体面积、季节性水体面积和永久性水体面积均呈现波动上升趋势(其中地表水体面积变化具有显著性上升趋势）, $Z$ 值分别为2.37、1.65 和3.08,上升的速率分别为 $1 5 . 5 4 \mathrm { ~ k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 } \cdot 7 . 1 2$ （20$\mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 和 $8 . 4 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 。20a间地表水体、季节性水体和永久性水体的平均面积分别为 $3 1 2 . 2 1 ~ \mathrm { k m } ^ { 2 }$ $2 4 9 . 0 5 \mathrm { k m } ^ { 2 }$ 和 $6 3 . 1 7 \mathrm { k m } ^ { 2 }$ ,最大面积分别为 $5 2 3 . 9 3 \ \mathrm { k m } ^ { 2 }$ （2018年） $. 4 7 5 . 3 0 \ \mathrm { k m } ^ { 2 } ( 2 0 0 2$ 年)和 $2 1 6 . 4 4 \mathrm { ~ k m } ^ { 2 } ( 2 0 1 7 \$ 年）,最小面积分别为 $4 5 . 8 9 \mathrm { ~ k m } ^ { 2 } ( 2 0 0 9$ 年） $. 4 3 . 3 8 \mathrm { k m } ^ { 2 }$ (2009年）和 $0 . 0 6 \mathrm { k m } ^ { 2 } ( 2 0 0 9$ 年)。塔里木河下游区域(大西海子以下)的地表水体、季节性水体和永久性水体的面积从2000年的 $4 9 . 0 0 \ \mathrm { k m } ^ { 2 } \ 、 4 8 . 9 3 \ \mathrm { k m } ^ { 2 }$ 和

![](images/38e1a160e26ccf85f8825558889aa6bafe48274781abae7b3f2f92957f83201a.jpg)  
图22000—2019年塔里木河下游地表水体面积变化  
Fig.2 Changes of water surface area in the lower reaches of Tarim River from 2Ooo to 2019

表22000—2019年塔里木河下游地表水体面积时间变化趋势  
ab.2Trend of water surface area in the lower reaches of Tarim River from 2ooo to 2019   

<html><body><table><tr><td>区域</td><td>类型</td><td>最大面积/km(年份)</td><td>最小面积/km(年份)</td><td>平均面积/km</td><td>变化速率/km·a-1</td><td>Z值</td></tr><tr><td rowspan="3">整个区域</td><td>季节性水体</td><td>475.30(2002)</td><td>43.38(2009)</td><td>249.05</td><td>7.12</td><td>1.65</td></tr><tr><td>永久水体</td><td>216.44(2017)</td><td>0.06(2000)</td><td>63.17</td><td>8.41</td><td>3.08**</td></tr><tr><td>地表水体</td><td>523.93(2018)</td><td>45.89(2009)</td><td>312.21</td><td>15.54</td><td>2.37*</td></tr><tr><td rowspan="3">上段区域</td><td>季节性水体</td><td>17.18(2018)</td><td>1.47(2008)</td><td>11.21</td><td>0.31</td><td>2.43*</td></tr><tr><td>永久水体</td><td>1.08(2017)</td><td>0.03(2009)</td><td>0.23</td><td>0.01</td><td>0.10</td></tr><tr><td>地表水体</td><td>17.65(2018)</td><td>1.54(2008)</td><td>11.44</td><td>0.31</td><td>2.24*</td></tr><tr><td rowspan="3">中段区域</td><td>季节性水体</td><td>37.77(2017)</td><td>0.20(2008)</td><td>19.10</td><td>1.58</td><td>3.28**</td></tr><tr><td>永久水体</td><td>5.44(2018)</td><td>0(2000,2002,2009,2010)</td><td>0.82</td><td>0.16</td><td>2.90**</td></tr><tr><td>地表水体</td><td>42.50(2018)</td><td>0.21(2008)</td><td>19.92</td><td>1.75</td><td>3.34**</td></tr><tr><td rowspan="3">下段区域</td><td>季节性水体</td><td>443.15(2002)</td><td>29.62(2001)</td><td>218.74</td><td>5.23</td><td>1.59</td></tr><tr><td>永久水体</td><td>212.14(2017)</td><td>0(2000,2001)</td><td>62.12</td><td>8.24</td><td>3.05**</td></tr><tr><td>地表水体</td><td>463.79(2018)</td><td>29.62(2001)</td><td>280.86</td><td>13.48</td><td>2.37*</td></tr></table></body></html>

注： $^ * , * *$ 分别表示在 $5 \% . 1 \%$ 的显著性水平上显著。

$0 . 0 6 \mathrm { k m } ^ { 2 }$ 增加到2019年的 $4 9 8 . 5 4 \ \mathrm { k m } ^ { 2 } \setminus 3 0 0 . 7 6 \ \mathrm { k m } ^ { 2 }$ 和$1 9 7 . 7 8 \mathrm { k m } ^ { 2 }$ 。输水后的第3年(2002年），地表水体面积和季节性水体面积出现了急剧的增加，分别从2001年的 $4 8 . 5 8 ~ \mathrm { k m } ^ { 2 }$ 和 $4 8 . 0 2 \ \mathrm { k m } ^ { 2 }$ 增加到2002年的$4 9 1 . 2 6 ~ \mathrm { k m } ^ { 2 }$ 和 $4 7 5 . 3 0 ~ \mathrm { k m } ^ { 2 }$ 。2002—2006年地表水体面积呈现波动变化，2007一2009年呈现急剧减少，在2009年地表水体和季节性水体的面积均减少到最低点，随后在2010年出现急剧增加，并在2010—2019年呈现缓慢的上升趋势。

塔里木河下游上段的地表水体、季节性水体和永久性水体的面积均呈现波动上升趋势( $Z$ 值分别为2.24、2.43和0.10),上升的速率分别为 $0 . 3 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 、$0 . 3 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 和 $0 . 0 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 。20a间地表水体面积、季节性水体面积和永久性水体面积的平均面积分别为 $1 1 . 4 4 \ \mathrm { k m } ^ { 2 } , 1 1 . 2 1 \ \mathrm { k m } ^ { 2 }$ 和 $0 . 2 3 \ \mathrm { k m } ^ { 2 }$ ,最大面积分别为 $1 7 . 6 5 \ \mathrm { k m } ^ { 2 } ( 2 0 1 8 \$ 年） $1 7 . 1 8 \ \mathrm { k m } ^ { 2 } ( 2 0 1 8$ 年)和$1 . 0 8 \ \mathrm { k m } ^ { 2 } ( 2 0 1 7$ 年）,最小面积分别为 $1 . 5 4 ~ \mathrm { k m } ^ { 2 } ( 2 0 0 8$ 年） $. 1 . 4 7 \ \mathrm { k m } ^ { 2 } ( 2 0 0 8 \$ 年)和 $0 . 0 3 \ \mathrm { k m } ^ { 2 } ( 2 0 0 9 \$ 年)。与整个研究区一样，在2007—2009年呈现急剧减少，在2008年地表水体面积和季节性水体面积均减少到最低点。

塔里木河下游中段和下段区域的地表水体面积、季节性水体面积和永久性水体面积均呈现波动的上升趋势，且除下段区域的季节性水体面积外，其他水体类型面积均呈现显著性增加。20a间中段区域地表水体、季节性水体和永久性水体的面积增加速率分别为 $1 . 7 5 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 } , 1 . 5 8 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ 和 $0 . 1 6 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ ，平均面积分别为 $1 9 . 9 2 \mathrm { k m } ^ { 2 } \setminus 1 9 . 1 0 \mathrm { k m } ^ { 2 }$ 和 $0 . 8 2 \mathrm { k m } ^ { 2 }$ ,最大面积分别为 $4 2 . 5 0 \ \mathrm { k m } ^ { 2 } ( 2 0 1 8 \$ 年） $. 3 7 . 7 7 \ \mathrm { k m } ^ { 2 } ( 2 0 1 7 \$ 年)和 $5 . 4 4 \mathrm { ~ k m } ^ { 2 } ( 2 0 1 8$ 年）,最小面积分别为 $0 . 2 1 \ \mathrm { k m } ^ { 2 }$ （2008年） $0 . 2 0 \ \mathrm { k m } ^ { 2 } ( 2 0 0 8$ 年)和 $0 ~ \mathrm { k m } ^ { 2 } ( 2 0 0 0 , 2 0 0 2$ 2009、2010年）。20a间下段区域地表水体、季节性水体和永久性水体的面积增加速率分别为$1 3 . 4 8 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 } . 5 . 2 3 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 和 $8 . 2 4 ~ \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ ,平均面积分别为 $2 8 0 . 8 6 \ \mathrm { k m } ^ { 2 } \setminus 2 1 8 . 7 4 \ \mathrm { k m } ^ { 2 }$ 和 $6 2 . 1 2 \ \mathrm { k m } ^ { 2 }$ ,最大面积分别为 $4 6 3 . 7 9 \mathrm { k m } ^ { 2 } ( 2 0 1 8 \$ 年） $. 4 4 3 . 1 5 \mathrm { k m } ^ { 2 } ( 2 0 0 2$ 年)和 $2 1 2 . 1 4 \ \mathrm { k m } ^ { 2 } ( 2 0 1 7 \$ 年），最小面积分别为 $2 9 . 6 2 \mathrm { k m } ^ { 2 }$ (2001年） $. 2 9 . 6 2 \ \mathrm { k m } ^ { 2 } ( 2 0 0 1$ 年)和 $0 ~ \mathrm { k m } ^ { 2 } ( 2 0 0 0 \cdot 2 0 0 1$ 年）。与整个研究区一样，中段和下段区域的地表水体面积、季节性水体面积在2007一2009年呈现急剧减少。

# 2.2水体面积空间变化分析

塔里木河下游区域地表水体呈现明显的空间不均匀分布，且随着时间的变化而呈现出不同的状态(图3)。整体上，水体主要分布在研究区域的下段。塔里木河下游区域季节性水体所占的比重相对较大，20a间的平均占比为 $8 3 . 6 0 \%$ ，最大占比为$9 9 . 8 7 \%$ (2000年），最小占比为 $5 7 . 3 1 \%$ (2017年）；永久水体占整个水体表面积比重最大的年份发生在2017年 $( 4 2 . 6 9 \%$ ），随后是2019年 $( 3 9 . 6 7 \%$ )和2018年 $( 3 7 . 0 2 \%$ )。图4显示了塔里木河下游生态输水起始年份2000年和2019年的地表水体面积空间分布，生态输水引起的地表水体面积增加主要表现在台特玛湖湖区（本文计算规定台特玛湖湖区为研究区域中 $3 9 ^ { \circ } 3 9 ^ { \prime } 5 4 ^ { \prime \prime } \mathrm { N }$ 以下部分）。2000年，台特玛湖湖区只存在少量的地表季节性水体，面积约为$3 8 . 1 9 \mathrm { k m } ^ { 2 }$ ;2019年台特玛湖湖区的地表永久水体和季节性水体均呈现显著的增加，面积分别约为

![](images/5f0a76289ad503d5325b3a032f694d50571c80dc6d19ef8002e319b761fa4640.jpg)  
注：饼图代表季节性水体与永久性水体面积占比。  
图32000—2019年塔里木河下游水体空间分布

Fig.3Annual spatial distributions of water surface area in the lower reaches of Tarim River from 2Oo0 to 2019

# 干旱区地理

$2 6 7 . 2 7 \mathrm { k m } ^ { 2 }$ 和 $1 8 8 . 0 0 \mathrm { k m } ^ { 2 }$ ，总体水面积约为 $4 5 5 . 2 7 \mathrm { k m } ^ { 2 }$ 相比2000年增加了 $4 1 7 . 0 8 \mathrm { k m } ^ { 2 }$ （约10.92倍）。

塔里木河下游上段、中段和下段区域的地表水体在过去20a间的平均占比分别为 $3 . 6 6 \% , 6 . 3 8 \%$ 和$8 9 . 9 6 \%$ （图 $5 \mathrm { a }$ )，说明下段区域拥有最大的地表水体面积而上段区域最小，与图3中的空间分布相符。

![](images/d84e8f855d3fbe78e06c7e797ea3428b5d54f6afb64e7af1061ff95913224677.jpg)  
图42000年和2019年塔里木河下游水体的空间分布  
图52000—2019年塔里木河下游不同水体和不同区域的占比Fig.5Ratios of water surface area for different types of surface water and differentregions in the lower reaches of Tarim River from 2ooO to 2019

Fig.4Spatial distributions of water surface area in the lower reaches of Tarim River in 2OoO and 2019

(a)上段、中段、下段区域水体面积占比 (b)上段、中段、下段区域地表水体面积占比上段中段■下段  
20 ■地表水体■季节性水体 川 10 0上段 中段 下段 2000区段 年份(c)上段、中段、下段区域地表永久水体面积占比 (d)上段、中段、下段区域地表季节性水体面积占比上段中段■下段 上段中段下段  
100 100  
40 %/重 860 40  
20 200 0200 2 3 45567 8 2003230 0 1516 0 8 09 2000 123415167 8 。2020 20 20 0 20 20 0 0 20 0 2020 20 20 20 20 20 0 20 0 80 20 0年份 年份

其中，20a间上段、中段和下段区域的地表永久水体的平均占比分别为 $0 . 3 6 \% . 1 . 3 0 \%$ 和 $9 8 . 3 4 \%$ ,季节性水体的平均占比分别为 $4 . 5 0 \% . 7 . 6 7 \%$ 和 $8 7 . 8 3 \%$ ，说明下段区域的永久性水体面积在其总的地表水体面积占比中承担了最大的贡献率。图5b\~d显示了2000一2019年塔里木河下游上段、中段和下段区域的地表水体、永久水体和季节性水体的比重变化。整体上，上段区域的永久水体和季节性水体的比重均呈现减少趋势，永久性水体所占比重从2000年的$100 \%$ 下降到2019年的 $0 . 3 6 \%$ ;相反，下段区域的永久水体和季节性水体的比重均呈现增加趋势，永久性水体所占比重从2000年的 $0 \%$ 上升到2019年的$9 8 . 3 4 \%$ ,主要分布在台特玛湖湖区（约占 $9 9 . 9 8 \%$ ；中段区域的地表永久水体和季节性水体的增长速率较低。台特玛湖湖区水体面积的扩张是下段区域水体面积占比不断增加的主要原因。

# 2.3地表水体面积与输水量的相关性

近20a以来，塔里木河下游的地表水体面积、季节性水体面积和永久性水体面积与生态输水量均呈现正相关性，其相关系数( $\boldsymbol { r }$ 值)分别为0.45(正中等相关）、0.15（正极弱相关)和0.78(正强相关），说明塔里木河下游地表水体面积,尤其是永久水体面积，主要与塔里木河下游输水量相关(图6)。分区域来看，上段、中段和下段区域的地表水体面积与生态输水量均呈现正相关性，其相关系数（ $\boldsymbol { r }$ 值)分别为0.68(正强相关）0.55(正中等相关)和0.42（正中等相关);季节性水体面积与生态输水量也均呈现正相关性，其相关系数( $\boldsymbol { r }$ 值)分别为0.66(正强相关）、0.52(正中等相关)和0.09(正极弱相关);永久水体面积与生态输水量也均呈现正相关性，其相关系数( $r$ 值)分别为0.72(正强相关）0.62(正强相关)和0.78(正强相关)。这些相关性结果说明，整体上，上段区域地表水体面积与生态输水量的相关性较强，而下游区域永久性水体面积受生态输水量的影响相对最大。这主要由于大西海子下泄的水量在先后通过上段和中段区域的河道后才能到达下段区域的台特玛湖湖区，且随着输水量的不断增多，水体面积不断增大。同时，生态输水量在2007—

(a)塔里木河下游地表水体 (b)上段地表水体 (c)中段地表水体 (d)下段地表水体  
80I/雪舞 1628 P0.45 0I/舞 28 p=0.08 . · 0I/ 128 P001: 0I/善舞 128 -0.424 4 .44 C · +0 · 0 . 0 . 0 . .4 4 40 100200300400500 0 4 8 121620 0 10 20 3040 0 100200300400 500水体面积/km² 水体面积/km² 水体面积/km² 水体面积/km²  
(e)塔里木河下游地表永久水体 (f)上段地表永久水体 (g)中段地表永久水体 (h)下段地表永久水体  
goI/鲁舞 1628 4 0.78 g0I/ 201510 5 P0.74 80/舞 1628 4 P00 g0I/善 1628 4 P0.78 .0 输 0 0 04 4 L 40 50 100 150 200 250 0 0.4 0.8 1.2 0 2 4 6 050 100 150 200 250水体面积/km² 水体面积/km² 水体面积/km² 水体面积/km²  
(i)塔里木河下游地表季节性水体 (i)上段地表季节性水体 (k)中段地表季节性水体 ()下段地表季节性水体  
0I/鲁舞 16 r=0.15 16 r=0.66 0I/哦 16 厂 r=0.52 16 r=0.0912 8 P=0.52 . 80I/ m 12 8 P<0.01 . . 12 8 P=0.02 . C 80/舞 12 8 P=0.71+ 量 ·40 8 舞 40 40 · 40. .4 4 4 40 100 200300400 500 0 4 8 12 16 20 0 10 2030 40 50 0 100 200 300 400 500水体面积/km² 水体面积/km² 水体面积/km² 水体面积/km²

# 干吴区地理

2009年处于极低值(其中2008年输水量为0)，直接导致塔里木河下游区域在2009年地表水体面积和季节性水体面积均减少到最低点。

# 3讨论

本文基于近20a塔里木河下游的遥感影像资料和生态输水数据，解析了区域地表水体面积的时空变化特征，探讨了生态输水对地表水体面积的影响，对深入理解塔里木河下游生态输水所带来的生态环境效应具有一定参考意义。塔里木河下游大西海子水库至台特玛湖湖区域的降水稀少、蒸发大，水资源主要是大西海子水库的下泄水量，即塔里木河下游的生态输水量。水资源是干旱区生态环境安全和经济社会可持续发展的首要限制性因子，随着生态输水的不断增加，塔里木河下游地表水体面积的不断扩大，该区域植被生长逐渐得到明显恢复、生态环境得到持续改善67。由于沿途河水损失，使得前几次的生态输水没有到达台特玛湖，故台特玛湖的永久水体和季节性水体面积在前几次输水后没有显著增加;2007—2009年大西海子水库的下泄水量较少，直接导致研究区域的永久水体和季节性水体面积均呈现显著下降，并使得地表水体面积在2009年减少到最低值;在塔里木河下游上段、中段和下段区域中，以河湖为主体的地表水体主要集中在下段区域的台特玛湖湖区，湖区永久水体和季节性水体的增加是塔里木河下游水体面积增大的主要因素。同时，由于研究区域的影像数据可能存在一定的质量缺陷和台特玛湖水体可能受到车尔臣河水量的影响[25-26],本文的研究结果存在一定的不确定性,需要在未来研究中进一步综合考虑其他因素的影响。

# 4结论

通过以上的结果分析及讨论，本文的主要结论如下：

(1）2000一2019年，塔里木河下游的地表水体面积、季节性水体面积和永久性水体面积均呈现波动上升趋势，面积分别从2000年的 $4 9 . 0 0 \mathrm { k m } ^ { 2 } \ 、 4 8 . 9 3 \mathrm { k m } ^ { 2 }$ 和 $0 . 0 6 \mathrm { k m } ^ { 2 }$ 增加到2019年的 $4 9 8 . 5 4 \mathrm { ~ k m } ^ { 2 } \setminus 3 0 0 . 7 6 \mathrm { ~ k m } ^ { 2 }$ 和 $1 9 7 . 7 8 ~ \mathrm { k m } ^ { 2 }$ ;输水后的第3年(2002年），地表水体面积和季节性水体面积出现了急剧增加，分别从

2001年的 $4 8 . 5 8 ~ \mathrm { k m } ^ { 2 }$ 和 $4 8 . 0 2 \ \mathrm { k m } ^ { 2 }$ 增加到2002年的$4 9 1 . 2 6 \mathrm { k m } ^ { 2 }$ 和 $4 7 5 . 3 0 \mathrm { k m } ^ { 2 }$ ;上段(大西海子水库一英苏)区域的地表水体、季节水体和永久性水体的面积均呈现波动上升趋势,增加的速率分别为 $0 . 3 1 \mathrm { ~ k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ 、$0 . 3 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 和 $0 . 0 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ;中段(英苏—阿拉干)区域和下段(阿拉干一台特玛湖)区域的地表水体面积、季节性水体面积和永久性水体面积均呈现波动上升趋势，其中，中段区域地表水体、季节性水体和永久性水体的面积增加速率分别为 $1 . 7 5 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 、$1 . 5 8 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 和 $0 . 1 6 \mathrm { ~ k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ，下段区域地表水体、季节性水体和永久性水体的面积增加速率分别为$1 3 . 4 8 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 } . 5 . 2 3 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ 和 $8 . 2 4 \mathrm { k m } ^ { 2 } { \cdot } \mathrm { a } ^ { - 1 }$ 。

(2)塔里木河下游区域的地表水体呈现出明显的空间不均匀分布，主要分布下段区域；生态输水引起的地表水体面积增加主要表现在台特玛湖湖区L $\langle 3 9 ^ { \circ } 3 9 ^ { \prime } 5 4 ^ { \prime \prime } \mathrm { N }$ 以下部分），2019年台特玛湖湖区的地表永久水体和季节性水体面积分别约为 $2 6 7 . 2 7 \ \mathrm { k m } ^ { 2 }$ 和 $1 8 8 . 0 0 ~ \mathrm { k m } ^ { 2 }$ ，总体水面积约为 $4 5 5 . 2 7 ~ \mathrm { k m } ^ { 2 }$ ,相比2000年（约 $3 8 . 1 9 \ \mathrm { k m } ^ { 2 } \cdot$ 增加了 $4 1 7 . 0 8 ~ \mathrm { k m } ^ { 2 }$ （约10.92倍);近20a以来上段、中段和下段区域的地表永久水体面积的平均占比分别为 $0 . 3 6 \% . 1 . 3 0 \%$ 和 $9 8 . 3 4 \%$ ，季节性水体面积的平均占比分别为 $4 . 5 0 \%$ ） $7 . 6 7 \%$ 和$8 7 . 8 3 \%$ 。

(3）近20a以来塔里木河下游区域的地表水体面积、季节性水体面积和永久性水体面积与生态输水量的相关系数分别为0.45（正中等相关）0.15（正极弱相关)和0.78(正强相关），说明研究区域地表水体面积，尤其是永久水体面积，主要与塔里木河下游输水量相关；其中，中段区域的地表水体面积与生态输水量的相关性较强，而下段区域永久性水体面积受生态输水量的影响相对最大；2007—2009年极低的输水量直接导致研究区域在2009年地表水体和季节性水体的面积均减少到最低点。

# 参考文献(References)

[1]陈亚宁,徐长春,郝兴明,等.新疆塔里木河流域近50a气候变 化及其对径流的影响[J].冰川冻土,2008,30(6):921-929.[Chen Yaning,Xu Changchun,Hao Xingming,et al.Fifty-year climate change and its effect on annual runoff in the Tarim River Basin, China[J].Journal of Glaciology and Geocryology，2Oo8,30(6): 921-929.]   
[2] 陈忠升，陈亚宁,李卫红,等.塔里木河干流径流损耗及其人类 活动影响强度变化[J].地理学报,2011,66(1):89-98.[Chen Zhongsheng,Chen Yaning,Li Weihong,et al. Changes of runoff consumption and its human influence intensity in the mainstream of Tarim River[J]. Acta Geographica Sinica,2011,66(1): 89-98.]   
[3]杨鹏,陈亚宁,李卫红,等.2003—2012年新疆塔里木河径流量 变化与断流分析[J].资源科学,2015,37(3):485-493.[Yang Peng, Chen Yaning,Li Weihong,et al.Analysis of changes in runoff and drying in the Tarim River from 20O3 to 2012[J].Resources Science,2015,37(3): 485-493.]   
[4]王梅霞,张太西,余行杰,等.新疆哈密 2018·7·31特大暴雨山 洪汇水量估算与应用研究[J].干旱区地理,2020,43(4):939- 945.[Wang Meixia,Zhang Taixi,Yu Xingjie,etal. Estimation and application of water-collecting amount during an extreme heavy rainfall induced flash flooding in Hami City on $3 1 ^ { \mathrm { s t } }$ July 2018[J]. Arid Land Geography,2020,43(4): 939-945.]   
[5]陈亚宁,李卫红,陈亚鹏,等.新疆塔里木河下游断流河道输水 与生态恢复[J].生态学报,2007,27(2): 538-545.[Chen Yaning, Li Weihong, Chen Yapeng, et al. Water conveyance in drid-up riverway and ecological restoration in the lower reaches of Tarim River, China[J]. Acta Ecologica Sinica,2007,27(2): 538-545.]   
[6]李丽君,张小清,陈长清,等.近20a塔里木河下游输水对生态 环境的影响[J].干旱区地理,2018,41(2):238-247.[Li Lijun, Zhang Xiaoqing, Chen Changqing,et al. Ecological efects of water conveyance on the lower reaches of Tarim River in recent twenty years[J]. Arid Land Geography,2018,41(2): 238-247.]   
[7]李均力,肖昊,沈占锋,等.2013—2018年塔里木河下游植被动 态变化及其对生态输水的响应[J].干旱区研究,2020,37(4): 985-992.[Li Junli, Xiao Hao,Shen Zhanfeng,et al.Vegetation changes during the 2013—2018 period and its response to ecological water transport in the lower reaches of the Tarim River[J].Arid Zone Research,2020,37(4): 985-992.]   
[8]李卫红,陈永金,陈亚鹏,等.新疆塔里木河下游生态输水对地 下水位和水质的影响[J].资源科学,2006,28(5):157-163.[Li Weihong,Chen Yongjin,ChenYapeng,etal.Eectsofcolgical stream water transfusion on groundwater level and quality in the lower reaches of the Tarim River[J]. Resources Science,2006,28 (5): 157-163.]   
[9]邓铭江,周海鹰,徐海量,等.塔里木河下游生态输水与生态调 度研究[J].中国科学(技术科学),2016,46(8):864-876.[Deng Mingjiang, Zhou Haiying,Xu Hailiang,et al. Research on the ecological operation in the lower reaches of Tarim River based on water conveyance[J]. Scientia Sinica (Technologica),2016,46(8): 864-876.]   
[10] 任强,龙爱华,杨永民,等.近20年塔里木河干流生态环境变化 遥感监测分析[J].水利水电技术,2021,52(3):103-111.[Ren Qiang,Long Aihua, Yang Yongmin, et al. Analysis on remote sensing monitoring of eco-environment variation of main stream basin of Tarim River in recent 2O years[J].Water Resources and Hydropower Engineering,2021,52(3):103-111.]   
[11]Huang W,Duan W,Nover D,et al.An integrated assessment of surface water dynamics in the Irtysh River Basin during 1990- 2019and exploratory factor analyses[J]. Journal of Hydrology, 2021,593: 125905,doi: 10.1016/j.jhydrol.2020.125905.   
[11 在述本引亚销竿 采咸纻△观测片模刑焦成宏为函河

流域生态环境保护与可持续发展提供科技支撑[J].中国科学 院院刊,2020,35(11): 1417-1423.[Che Tao,Li Hongyi, Jin Rui, et al. Integration of remote sensing observations and models supports the regional sustainable development in Heihe River Basin, China[J]. Bulletin of the Chinese Academy of Sciences,2020,35 (11): 1417-1423.]   
[13] 宋春桥,詹鹏飞,马荣华.湖泊水情遥感研究进展[J].湖泊科学, 2020,32(5):1406-1420.Song Chunqiao,ZhanPengfei,MaRonghua.Progress in remote sensing study on lake hydrologic regime [J]. Journal of Lake Sciences,2020,32(5): 1406-1420.]   
[14]Kumar L,Mutanga O.Google Earth Engine applications since inception: Usage,trends,and potential[J]. Remote Sensing,2018,10 (10): 1509.   
[15]Gorelick N,Hancher M,Dixon M,et al.Google Earth Engine: Planetary-scale geospatial analysis for everyone[J]. Remote sensing of Environment,2017,202:18-27.   
[16]Xu B,Li J,Park T,etal. Improving leaf area index retrieval over heterogeneous surface mixed with water[J]. Remote Sensing of Environment,2020,240:111700,doi: 10.1016/j.rse.2020.111700.   
[17] Zou Z, Xiao X,Dong J,et al. Divergent trends of open-surface water body area in the contiguous United States from 1984 to 2016 [J]. Proceedings of the National Academy of Sciences,2018,115 (15): 3810-3815.   
[18]Wang X, Xiao X, Zou Z,et al. Gainers and losers of surface and terrestrial water resources in China during 1989—2O16[J].Nature Communications,2020,11(1): 1-12.   
[19]Mann H B.Nonparametric tests against trend[J]. Econometrica: Journal of the Econometric Society,1945,13(3): 245-259.   
[20] Duan W,He B,Takara K,et al. Changes of precipitation amounts and extremes over Japan between 1901 and 2O12 and their connection to climate indices[J]. Climate Dynamics,2015,45(7): 2273-2292.   
[21]Yue S,Pilon P,Cavadias G.Power of the Mann-Kendall and Spearman's rho tests for detecting monotonic trends in hydrological series[J]. Journal of Hydrology,2002,259(1): 254-271.   
[22]Duan W,Takara K.Impacts of climate and human activities on water resources and quality: Integrated regional assessment[M]. Singapore: Springer, 2020.   
[23]Lawrence I, Lin K.A concordance correlation coefficient to evaluate reproducibility[J]. Biometrics,1989,45(1): 255-268.   
[24] Zou S,Jilili A, Duan W,et al. Human and natural impacts on the water resources in the Syr Darya River Basin, Central Asia[J]. Sustainability,2019,11(11): 3084.   
[25] 艾克热木·阿布拉,朱俏俏,徐海量,等.台特玛湖植被变化特征 [J].新疆大学学报(自然科学版),2019,36(2):182-191.[Aikeremu Abula,Zhu Qiaoqiao,Xu Hailiang et al. Characteristics of vegetation variation in Taitema Lake[J].Journal of Xinjiang University (Natural Science Edition),2019,36(2):182-191.]   
[26] 王晶,杨太保,冀琴,等.1990—2015年喜马拉雅山东段中国和 不丹边境地区冰川变化研究[J].干旱区地理,2019,42(3):542- 550.[Wang Jing,Yang Taibao,Ji Qin,et al. Change of the modern glaciers in the eastern Himalaya near China and Bhutan border area from 1990 to 2015[J].Arid Land Geography,2019,42(3): 542-550.]

# Effects of ecological water conveyance on changes of surface waterareainthelowerreachesof TarimRiver

ZOU Shan $^ { 1 , 2 , 3 , 4 } _ { . }$ ，Jilili Abuduwaili123，HUANG Wenjing1²，DUAN Weili1²   
(1.State KeyLaboratoryofDesertandOasisEcologyXinjiangInstituteofEcologyandGeography,ChineseAcademyofSciences,   
Urumqi830l1,Xijang,China;2.UniversityofChineseAcademyofSciences,Beijing049,China;3.ResearchCterfor Ecologyand Environment of Central Asia,Chinese Academyof Sciences,Urumqi 83ool1,Xinjiang, China; 4.Department of Geography,Ghent University,Ghent 9OOo,Belgium)

Abstract: Water is a key restricting factor of socioeconomic development and eco-environmental protection in the arid inland riverbasins of northwest China.Because of ecological problems causedby climate change and the overexploitation of water resources in the Tarim River Basin (e.g.,river breakup,drying-up of lakes,and degradation of vegetation cover),a national ecological water conveyance project has been oficially implemented in the lower reaches of Tarim River since 2Ooo.So far,the region's ecological environment has improved steadily,and studies have evaluated the impacts (e.g. changes in groundwater level and vegetation cover)of the ecological water conveyance project. However, there are relatively few systematic studies on the changes in the area of surface water in the lower reachesofTarimRiver in the past 2O years.On the basis of the Landsat 5,7,and 8 images and the annual water conveyance quantity,this paper used the Google Earth Engine,the surface water extraction method,and the multiple statistic methods (e.g.,the Mann-Kendalltrend test and the Pearson correlation coeficient) to quantitativelyanalyze the spatiotemporal changes of the surface water and evaluated the impacts of the ecological water conveyance project on the surface water area.The main results are as follows.Firstly,from 2000 to 2019,a fluctuating upward trend was detected in the overallsurface water area,seasonal water area,and permanent water area, with increase rates at $1 5 . 5 4 ~ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ， $7 . 1 2 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ,and $8 . 4 1 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ , respectively. A fluctuating upward trend has also been detected for all three subregions: the upstream region from Daxihaizi Reservoir to Yingsu station, the upstream region from Yingsu station to Alagan station,andthe downstream region from Alagan station to Lake Taitema. Of these,the downstream region had the largest increase rate for both the seasonal water and permanent water areas, with values at $5 . 2 3 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ and $8 . 2 4 ~ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ,respectively. In addition, the increase in surface water area in Lake Taitema was the main factor for the expansion of surface water area in the lower reaches of Tarim River.In 2O19,the permanent surface water area, the seasonal water area,and the total surface water area of Lake Taitema were about $2 6 7 . 2 7 ~ \mathrm { k m } ^ { 2 }$ ， $1 8 8 . 0 0 \ \mathrm { k m } ^ { 2 }$ and $4 5 5 . 2 7 ~ \mathrm { k m } ^ { 2 }$ ,respectively; the total surface water area of Lake Taitema in 2O19 was evaluated to have been increased by $4 1 7 . 0 8 \mathrm { k m } ^ { 2 }$ (about 10.92 times) over that in 2000 (about $3 8 . 1 9 \mathrm { k m } ^ { 2 \cdot }$ ). Finally, in the past 20 years, there is a strong positive correlation between the surface water area (especialy the permanent water area)and the water quantity of the ecological water conveyance project.The water quantity of the ecological water conveyance project was extremely low during 2007—2009, which directly caused the lowest values of the total surface water area and the seasonal surface water area. Results obtained from this studycan contribute to the comprehensive understanding of the impact of ecological water conveyance in the lower reaches of Tarim River and provide a scientific basis for developing regional water ecological protection.

Key words: Tarim River; surface water body； ecological water conveyance;temporal and spatial changes； im-pact analysis; Google Earth Engine