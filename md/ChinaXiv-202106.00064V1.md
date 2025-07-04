# 水资源管理增强下的塔里木河上中游碳储量动态评估

郭靖1,2.3，王光焰4，徐生武4，张广朋1,2.3，苑塏烨1.,2.3，凌红波²，夏依旦·吾买尔江

(1.中国科学院新疆生态与地理研究所荒漠与绿洲生态国家重点实验室,新疆乌鲁木齐830011；2.新疆阿克苏绿洲农田生态系统国家野外科学观测研究站,新疆 阿克苏843017；3.中国科学院大学,北京100049;4.新疆塔里木河流域干流管理局,新疆 库尔勒841000；5.新疆塔里木河流域管理局,新疆 库尔勒832000)

摘要：自2000年实施流域综合治理和2010年推行流域体制改革以来,塔里木河流域水资源管理能力不断增强。然而,水资源管理对流域生态系统固碳能力的提升效果如何，未曾开展评估。以胡杨林集中分布的塔里木河上中游为研究靶区,采用InVEST模型,基于2000年、2010年、2018年土地利用/覆被变化数据，分析了水资源管理增强下流域生态系统碳储量的变化特点。结果表明：(1）2000年、2010年、2018年塔里木河上中游的总碳储量分别为$9 3 . 7 0 \mathrm { T g } \ 、 9 3 . 9 2 \mathrm { T g } \ 、 9 3 . 0 1 \mathrm { T g }$ ，平均碳密度分别为 $6 7 . 6 3 ~ { \mathrm { t } } \cdot { \mathrm { h m } } ^ { - 2 } , 6 7 . 7 8 ~ { \mathrm { t } } \cdot { \mathrm { h m } } ^ { - 2 } , 6 7 . 1 2 ~ { \mathrm { t } } \cdot { \mathrm { h m } } ^ { - 2 }$ ，基本保持稳定。林地是塔里木河上中游的主要碳库、草地次之。(2)2000—2010年碳储量增加 $0 . 2 2 \mathrm { T g }$ ，主要由于大量草地类型 $\left( 6 9 . 3 5 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } \right)$ 转化成耕地类型（ $7 3 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } ,$ )。自2000年塔里木河综合治理实施后,植被恢复使得地表生物量增多,林地、草地碳密度和碳储量增加;2010—2018年碳储量减少 $0 . 9 1 \mathrm { T g }$ ,碳损失途径主要源于大量林地类型( $7 3 . 7 7 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 转化成耕地类型0 $7 3 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } ,$ ),造成草地总碳储量降低。（3）碳储量空间分布具有较强的空间异质性,其特点以塔里木河上中游为条带向四周波动递减。碳储量变化显著区域在空间分布上与土地利用变化区域基本一致。研究可为深入了解干旱区碳循环，提升流域生态系统固碳功能，优化水资源管理提供科学依据。

关键词：InVEST模型；水资源管理；碳储量；土地利用/覆被变化；塔里木河

碳储量是生态系统服务最重要的功能指标之一，与陆地生态系统生产力密切相关,对改善全球气候变化具有重要作用[]。土地利用/覆被变化是全球碳循环不平衡的主要驱动因子[2],并且已经成为全球气候变化和环境变化的研究热点[3]，人类活动也正通过改变土地覆被和利用方式对陆地生态系统碳储量产生巨大影响[4]。因此，及时有效地评估土地利用变化下区域生态系统碳储量的时空变化以及两者之间的关系，对区域碳循环和碳汇/源研究以及缓解气候变化、维持区域可持续发展具有重要意义[5]。传统的碳储量估算研究多采用样地清查法，如根据土壤剖面数据计算土壤碳储量，近年来随着遥感和地理信息系统的快速发展，通过利用

RS/GIS技术建立模型来评估碳储量空间动态变化已成为了当前主要的发展趋势[6]。有关土地利用变化对碳储量影响的研究，国内外学者已经在不同研究尺度和区域进行了系统的分析。如Andreetta等[7]认为弃耕会造成土壤有机碳储量下降。Gelaw 等[8]发现耕地类型转化为草地类型会使区域碳汇增加。方精云等[9-"]通过森林蓄积量和生物量转换因子法分析对中国1949—1998年森林碳储量进行评估。王淑君等[12]利用回归模型和森林生物量转换因子法计算广州市森林碳储量。此外，在干旱区也存在由于水资源变化使土地利用发生改变,进一步对草地和土壤碳储量造成影响[13-14]。然而，目前大部分研究主要集中在土地利用类型对特定植被碳储量或土壤碳储量的影响5，有关水资源管理增强下土地利用变化与区域生态系统多个碳库碳储量关系的综合性研究成果却极少。

自20世纪50年代以来，由于塔里木河上中游耕地面积的快速扩张，水资源消耗日益加剧，导致下游来水锐减，地下水位明显降低，两岸植被严重衰竭，沙漠化加剧，使其成为中国乃至世界生态退化极为严重的生态脆弱区和敏感区[16]。水资源优化管理是解决干旱区流域水资源短缺和矛盾的重要途径。为协调流域水资源、实现流域生态保护和经济稳定发展，2000年中国政府投资 $1 . 0 7 \times 1 0 ^ { 1 0 }$ 元，对塔里木河流域进行全面管理[17-20]。2010年塔里木河实施管理体制改革，源头区子流域由塔里木流域管理局统一管辖,综合治理效果得到进一步提升[21]。虽然已有学者在塔里木河流域针对土地利用/覆被变化对土壤有机碳储量的影响进行研究[13],但尚未见水资源管理增强下，不同土地利用转化方式引起的生态系统不同碳库碳储量变化的研究。因此，本文分析了2000—2018年塔里木河上中游地区土地利用格局的变化，并利用InVEST模型评估了该区域水资源管理不断增强下土地利用变化所引起的生态系统碳储量的改变，阐明了生态系统碳储量的时空变化格局，以期为深入了解干旱区碳循环，提升流域生态系统固碳能力、优化水资源配置、促进流域可持续发展提供科学依据。

# 1 材料与方法

# 1.1 研究区概况

塔里木河位于塔克拉玛干沙漠北部,地理位置

$3 9 ^ { \circ } 3 0 ^ { \prime } { \sim } 4 3 ^ { \circ } 0 8 ^ { \prime } \mathrm { N }$ . $7 3 ^ { \circ } 1 0 ^ { \prime } { \sim } 9 4 ^ { \circ } 0 5 ^ { \prime } \mathrm { E }$ ，全长 $1 3 2 1 ~ \mathrm { k m }$ ，是中国最长的内陆河(图1)。其中上游为阿拉尔至英巴扎河段，全长 $4 4 7 \mathrm { k m }$ ，中游为英巴扎至恰拉河段，全长 $3 9 8 ~ \mathrm { k m }$ ，下游为恰拉至台特玛湖河段，全长$4 7 6 \mathrm { k m } ^ { [ 2 2 ] }$ 。塔里木河自身不产流，属纯耗散型内陆河，径流主要依靠源流补给，目前只有阿克苏河、和田河和叶尔羌河和开都一孔雀河4条源流汇入其中，形成"四源一干"的格局[23]。研究区属典型的温带干旱大陆性气候,年平均气温 $1 0 . 5 { \sim } 1 1 . 4 \mathrm { ~ \textdegree C }$ ,年潜在蒸发量 $2 0 0 0 { \sim } 2 9 0 0 ~ \mathrm { m m }$ ，而年降水量仅为30\~50$\mathbf { m } \mathbf { m }$ ，干旱指数介于28\~80之间，属极端干旱沙漠气候区[24-25]。河岸植被以胡杨(Populus euphratica）、柽柳(Tamarixchinensis)为主要建群种[26]

# 1.2数据来源及研究方法

1.2.1土地利用数据采用的土地利用/覆被数据为塔里木河内的Landsat-TM影像数据，分辨率为30m，成像时间分别为2000年、2010年与2018年的7—9月，这一时期是流域丰水期，河流、水库等水量较大，自然植被及农作物生长茂盛、地物特征明显。根据《土地利用现状分类》(GB/T21010—2007)将土地利用划分为分耕地、林地、草地、水域、建设用地和未利用土地6个一级土地利用类型;进一步将林地划分为有林地、疏林地、灌木林。土地利用/覆盖图是通过人工解译方法制作而成。在解译之前，先使用GEOSTAR3.0软件对原始多光谱图像进行大气校正和几何校正，然后使用ArcGIS10.4软件对不同年份的遥感影像进行假彩色合成。具有自然植被和耕地的区域是通过目视解译确定。最后，利用Kappa指数方法对解译结果进行精度检验，结合前期108个大样方调查结果与后期实地考察，最终检验结果精度分别为 $8 9 . 6 \% . 9 0 . 2 \% . 8 8 . 9 \%$ 。

![](images/010a043c78b9ee2cfa2321aca732f916c1c70e5ab939cd80be7c3c88ff2dd0c2.jpg)  
图1塔里木河土地利用/覆被分布示意图  
Fig.1Maps showing land use/cover in the mainstream area of the Tarim River

1.2.2碳储量模型 InVEST模型(Integrated Valua-tionofEcosystemServicesandTradeoffs)是由美国斯坦福大学、世界自然基金会和大自然保护协会联合开发的生态系统服务功能评估工具。本文利用InVEST模型的碳储存模块，根据不同土地类型地上、地下、土壤、死亡有机物4种碳库的平均碳密度乘以各土地类型的面积来计算塔里木河上中游生态系统的碳储量。研究区碳总储量由公式(1)和公式(2)计算得出：

$$
C _ { \mathrm { v } } = C _ { \mathrm { a b o v e } } + C _ { \mathrm { b e l o w } } + C _ { \mathrm { d e a d } }
$$

$$
C _ { \mathrm { { t o t } } } = C _ { \mathrm { { v } } } + C _ { \mathrm { { s o i l } } }
$$

式中： $C _ { \mathrm { v } }$ 为植被碳储量(t); $C _ { \mathrm { a b o v e } }$ 为地上生物碳储量(t）； $C _ { \mathrm { b e l o w } }$ 为地下生物碳储量(t); $C _ { \mathrm { d e a d } }$ 为死亡有机碳储量(t)； $C _ { \mathrm { t o t } }$ 为碳总储量(t); $C _ { \mathrm { s o i l } }$ 为土壤有机碳储量(t)。

本研究的总体技术路线为：在InVEST碳模型中输入塔里木河上中游土地利用/覆被类型图和四大碳库参数表，得到研究区地上、地下和死亡有机物碳三者碳储量总和，简称植被碳储量，即 $C _ { \mathrm { v } }$ 。在Arc-GIS10.4软件中运用栅格计算器，将土壤有机碳储量图层（ $( C _ { \mathrm { s o i l } } )$ 加上 $C _ { \mathrm { v } }$ 图层可得到研究区总的碳储量空间分布图,即 $C _ { \mathrm { t o t } }$ 。

1.2.3碳密度数据在 $\mathrm { I n V E S T }$ 模型中需录入不同土地利用类型的碳密度值，研究区各植被类型的碳密度主要来源于相关文献资料和模型数据库[27-30]，碳密度值在选取过程中首选新疆本地的实测数据，其次为邻近区域研究成果，最后为全国数据，并综合考虑塔里木河上中游植被类型，同时参考该区域

2000年、2010年、2018年植被净初级生产力（NPP）数据(MOD17A3HGF),对其进行修正。塔里木河上中游研究区不同土地利用类型碳密度参数如表1所示。此外，本文之所以没有将塔里木河下游列入研究靶区范围，主要原因如下：(1)塔里木河下游整体植被覆盖度与生境质量和上中游相差较大，如果整个干流区的植被都用一个植被平均碳密度，会使模型精确度降低且不能反映各个河段碳储量的真实情况；（2）InVEST模型在塔里木河流域应用很少，碳密度参数缺乏，需借鉴NPP数据进行修正，但MO-DIS影像(MOD17A3HGF)分辨率低( $5 0 0 ~ \mathrm { m } )$ ,在植被稀疏的塔里木河下游，像元内植被所占比重太少，反演效果差。

以往研究表明，虽然土壤有机碳是陆地生态系统中比较重要的碳汇，但由于其固碳速率较慢，在过去几十年中土壤有机碳库并没有发生明显的变化[31],因此在本研究中生态系统碳储存变化过程中不涉及土壤有机碳的变化，主要是变化活跃的植被碳储量引起。本研究中土壤有机碳数据以基于世界土壤数据库(Harmonized World SoilDatabase ver-sion1.1)的中国土壤数据集(http://westdc.westgis.ac.cn/data)为基础，利用土壤有机碳储量和碳密度的空间化表达和计算方法[32]：

$$
\mathrm { S O C D } = \sum _ { i = 1 } ^ { n } ( 1 - \theta _ { i } ) \times P _ { i } \times C _ { i } \times T _ { i } / 1 0 0
$$

式中：SOCD为土壤剖面有机碳密度 $\left( \mathrm { k g } \cdot \mathrm { m } ^ { - 2 } \right)$ ; $\theta _ { i }$ 为第$i$ 层 $> 2 ~ \mathrm { m m }$ 砾石含量（体积 $\%$ ）； $P _ { i }$ 为第 $i$ 层土壤容重$\left( \mathbf { g } \cdot \mathbf { c m } ^ { - 3 } \right)$ ; $C _ { i }$ 为第 $i$ 层土壤有机碳含量 $\left( { \bf g } \cdot { \bf k } { \bf g } ^ { - 1 } \right) ; T _ { i }$ 为第 $i$ 层土层厚度 $( \operatorname { c m } ) ; n$ 为参与计算的土壤层次总数。

表1塔里木河上中游各土地利用类型的碳密度  
Tab.1 Caron density of different land use types in the mainstream area of the Tarim River   

<html><body><table><tr><td rowspan="2">土地利用类型</td><td colspan="9">碳密度/(t·hm2)</td><td rowspan="2">来源文献</td></tr><tr><td></td><td>地上</td><td></td><td></td><td>地下</td><td></td><td></td><td>死亡有机物</td><td></td></tr><tr><td></td><td>2000年</td><td>2010年</td><td>2018年</td><td>2000年</td><td>2010年</td><td>2018年</td><td>2000年</td><td>2010年</td><td>2018年</td><td></td></tr><tr><td>有林地</td><td>0.22</td><td>0.34</td><td>0.31</td><td>0.08</td><td>0.12</td><td>0.11</td><td>0.09</td><td>0.14</td><td>0.13</td><td>[27-30]</td></tr><tr><td>疏林地</td><td>0.18</td><td>0.31</td><td>0.27</td><td>0.06</td><td>0.10</td><td>0.09</td><td>0.07</td><td>0.12</td><td>0.10</td><td>[27-30]</td></tr><tr><td>灌木林</td><td>0.19</td><td>0.32</td><td>0.28</td><td>0.07</td><td>0.12</td><td>0.10</td><td>0.05</td><td>0.08</td><td>0.07</td><td>[27-30]</td></tr><tr><td>草地</td><td>0.17</td><td>0.24</td><td>0.28</td><td>1.05</td><td>1.48</td><td>1.72</td><td>0.23</td><td>0.31</td><td>0.36</td><td>[11,27,29-30]</td></tr><tr><td>耕地</td><td>0.48</td><td>0.60</td><td>0.63</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>[30]</td></tr><tr><td>水域</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>[30]</td></tr><tr><td>建设用地</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>[30]</td></tr><tr><td>未利用地</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>[30]</td></tr></table></body></html>

# 2结果与分析

# 2.1土地利用现状及变化

2.1.1 土地利用现状2000—2018年塔里木河上中游各土地利用类型面积如表2所示。研究区总面积为 $1 3 8 . 5 7 \times 1 0 ^ { 4 } \ : \mathrm { h m } ^ { 2 } , \$ 2000年塔里木河上中游各土地利用类型面积大小为：林地 $\scriptstyle >$ 草地 $>$ 未利用地 $>$ 耕地>水域 $>$ 建设用地；2010年和2018年塔里木河上中游各土地利用类型面积大小为：林地 $>$ 草地 $>$ 耕地 $>$ 未利用地>水域 $>$ 建设用地。研究发现，2000—2018年林地、草地、耕地和未利用地是塔里木河上中游地区的主要地类且占比较高，其中林地、草地、耕地、未利用地年均占比分别为 $3 2 . 9 1 \% . 2 7 . 8 5 \% . 1 7 . 6 8 \%$ 、$1 6 . 7 5 \%$ ，而水域和建设用地占比较少(均不足 $6 \%$ ）。2.1.2土地利用变化随着水资源管理的不断增强，土地利用面积和结构均发生了明显变化。由图2可知，2000—2018年塔里木河上中游地区耕地、水域、建设用地、未利用地均呈增加趋势，其中耕地面积增加了 $1 1 . 6 6 \times 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ ,增幅明显，为 $6 5 . 0 3 \%$ ,未利用地增幅较小，仅为 $1 \%$ ;林地、草地面积呈减少态势,其中草地面积减少了 $9 . 0 9 \times 1 0 ^ { 4 } ~ \mathrm { h m } ^ { 2 }$ 且减少幅度最大，达到 $2 0 . 7 8 \%$ ,林地面积减少了 $5 . 0 6 \times 1 0 ^ { 4 } ~ \mathrm { h m } ^ { 2 }$ 减幅为 $1 0 . 5 0 \%$ 。此外，与2000—2010年相比，2010—2018年耕地面积的增加速率与草地、林地面积的减小速度均明显减缓，表明塔里木河综合治理和流域水资源统一管理实施后塔里木河上中游地区土地利用类型的面积变化较明显。

近20a塔里木河上中游土地利用转移主要发生在耕地、林地、草地和未利用地之间。分析结果表明(表3)：2000—2018年塔里木河上中游地区耕地

# 表22000—2018年塔里木河上中游土地利用面积和比例

Tab.2 Land use area and proportion in the mainstream area of the TarimRiver during 2ooo-2018   

<html><body><table><tr><td rowspan="2">土地利用 类型</td><td colspan="2">2000年</td><td colspan="2">2010年</td><td colspan="2">2018年</td></tr><tr><td>面积 /104 hm²</td><td>比例 1%</td><td>面积 /104 hm²</td><td>比例 1%</td><td>面积 /104hm²</td><td>比例 1%</td></tr><tr><td>耕地</td><td>17.93</td><td>12.94</td><td>25.96</td><td>18.74</td><td>29.59</td><td>21.36</td></tr><tr><td>林地</td><td>48.21</td><td>34.79</td><td>45.43</td><td>32.79</td><td>43.15</td><td>31.14</td></tr><tr><td>草地</td><td>43.75</td><td>31.57</td><td>37.38</td><td>26.98</td><td>34.66</td><td>25.01</td></tr><tr><td>水域</td><td>5.29</td><td>3.82</td><td>5.66</td><td>4.09</td><td>7.11</td><td>5.14</td></tr><tr><td>建设用地</td><td>0.44</td><td>0.31</td><td>0.60</td><td>0.43</td><td>0.87</td><td>0.63</td></tr><tr><td>未利用地</td><td>22.94</td><td>16.55</td><td>23.53</td><td>16.98</td><td>23.17</td><td>16.72</td></tr></table></body></html>

![](images/d751f2377df004710a5794dc9fac4159d7e7e9707450ecb719906cb8e804bf75.jpg)  
图2 2000—2018年塔里木河上中游各土地利用类型面积变化  
Fig.2 Change of land use in the mainstream area of the Tarim River during 20oo-2008

表32000—2018年塔里木河上中游土地利用转移矩阵  
Tab.3Transition matrix of land use in the mainstream area of the Tarim River during 2000-2018 /h1   

<html><body><table><tr><td>时段</td><td>土地利用类型</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>建设用地</td><td>未利用地</td></tr><tr><td>2000—2010年</td><td>耕地</td><td>176896.61</td><td>177.60</td><td>383.39</td><td>48.73</td><td>766.23</td><td>1719.71</td></tr><tr><td></td><td>林地</td><td>27648.10</td><td>449204.76</td><td>2058.00</td><td>667.94</td><td>154.98</td><td>2464.06</td></tr><tr><td></td><td>草地</td><td>54605.15</td><td>3316.68</td><td>368312.73</td><td>7598.88</td><td>597.20</td><td>3475.37</td></tr><tr><td></td><td>水域</td><td>1339.27</td><td>1311.52</td><td>2278.57</td><td>48370.14</td><td>0.00</td><td>79.32</td></tr><tr><td></td><td>建设用地</td><td>7.52</td><td>0.00</td><td>0.00</td><td>0.00</td><td>4300.22</td><td>64.12</td></tr><tr><td></td><td>未利用地</td><td>649.42</td><td>305.54</td><td>767.32</td><td>0.00</td><td>167.28</td><td>227538.47</td></tr><tr><td>2010—2018年</td><td>耕地</td><td>236148.40</td><td>8436.27</td><td>10940.27</td><td>1674.75</td><td>2659.61</td><td>396.42</td></tr><tr><td></td><td>林地</td><td>32228.98</td><td>390551.31</td><td>16857.65</td><td>9479.26</td><td>98.81</td><td>5177.07</td></tr><tr><td></td><td>草地</td><td>21869.35</td><td>21526.50</td><td>312625.53</td><td>7388.01</td><td>285.49</td><td>10240.00</td></tr><tr><td></td><td>水域</td><td>635.14</td><td>2276.26</td><td>2314.57</td><td>51460.21</td><td>0.00</td><td>0.01</td></tr><tr><td></td><td>建设用地</td><td>54.55</td><td>0.00</td><td>181.14</td><td>208.42</td><td>5367.00</td><td>167.28</td></tr><tr><td></td><td>未利用地</td><td>5649.12</td><td>8854.76</td><td>3787.17</td><td>976.56</td><td>318.39</td><td>215738.47</td></tr></table></body></html>

是主要的转入者，草地和林地是主要的转出者。其中，2000—2010年增加的耕地主要来自草地，占$6 4 . 8 1 \%$ ;2010一2018年，耕地面积增加主要来自林地，林地转向耕地的面积占 $5 3 . 3 3 \%$ ,并且该时期未利用地转向耕地的面积也增大 $( 5 6 4 9 . 1 2 \mathrm { h m } ^ { 2 } )$ 。相对于其他地类，耕地是建设用地增加的主要来源，2000—2010年和2010—2018年耕地转向建设用地的面积分别占 $4 5 . 4 6 \% \cdot 7 9 . 1 0 \%$ 。2000—2010年增加的水域面积主要来源是草地，占 $9 1 . 3 8 \%$ ; 2010—2018年水域面积增加主要来自耕地，占 $4 8 . 0 5 \%$ 。未利用地面积增加主要是由草地、林地转化而来，其次是耕地。

综上所述，2000—2018年塔里木河上中游地区，林地、草地呈减小趋势，减小速度为 $0 . 7 4 \times 1 0 ^ { 4 }$ $\mathrm { { h m } } ^ { 2 } { \cdot } \mathrm { { a } } ^ { - 1 }$ ;以沙漠、盐碱地、裸地为代表的未利用地增长幅度较小（增加速度为 $0 . 0 1 \times 1 0 ^ { 4 } \ \mathrm { h m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 } \big )$ ，但在2010—2018年出现减少趋势；此外，2000—2018年由于塔里木河上中游耕地面积扩张迅速,农业发展加快，但大量的生态用地被农业用地占用，“绿色走廊"空间也在缩小。由此可见，塔里木河综合治理和水资源管理体制改革后环境有所改善，但是荒漠化进程仍然强于绿洲化过程，生态环境依然脆弱。

# 2.2生态系统碳储量变化分析

2.2.1 碳储量动态2000年、2010年和2018年塔里木河上中游3个时期的碳储量总量分别为 $9 3 . 7 0 \mathrm { T g }$ 、$9 3 . 9 2 \mathrm { T g } \ 、 9 3 . 0 1 \mathrm { T g }$ ，平均碳密度分别为 $6 7 . 6 3 \ \mathrm { t } \cdot \mathrm { h m } ^ { 2 }$ ）$6 7 . 7 8 ~ \mathrm { t \cdot h m ^ { 2 } } \cdot 6 7 . 1 2 ~ \mathrm { t \cdot h m ^ { - 2 } }$ 。塔里木河上中游总碳储量呈先增长后降低的趋势，土地利用类型面积及其碳密度变化导致生态系统碳储量2000—2010年净增加 $0 . 2 2 \mathrm { T g } , 2 0 1 0 { - - 2 0 1 8 }$ 年净减少 $0 . 9 1 \mathrm { T g }$

从不同土地利用类型碳储量看（图3a），林地是塔里木河上中游的主要碳库,为 $3 1 . 8 8 { \sim } 3 5 . 3 1 \mathrm { T g }$ 占流域生态系统总碳储量的 $3 4 . 2 8 \% { \sim } 3 7 . 6 8 \%$ ,且呈持续下降趋势。草地碳储量仅次于林地，为 $2 4 . 0 3 \sim$ $3 0 . 3 7 \mathrm { T g }$ ，占总碳储量的 $2 5 . 8 4 \% { \sim } 3 2 . 4 1 \%$ ,且呈明显的下降趋势。除水域外，未利用地碳储量最低，建设用地碳密度虽然高于林地，但由于分布面积较小，导致总碳储量最低，为 $0 . 3 5 { \sim } 0 . 6 9 \ \mathrm { T g }$ ，仅占$0 . 3 7 \% { \sim } 0 . 7 4 \%$ 。此外。塔里木河上中游各土地利用类型，除建设用地和水域外,2000—2018年碳密度基本保持稳定(图3b),年均碳密度林地 $\mathrm { ( 7 3 . 7 7 t { \cdot } h m ^ { - 2 } ) > }$ 耕地 $\left( 7 3 \mathrm { ~ t } \cdot \mathrm { h m } ^ { - 2 } \right) >$ 草地 $\left( 6 9 . 3 5 \mathrm { ~ t } \cdot \mathrm { h m } ^ { - 2 } \right) >$ 未利用地中 $6 3 . 5 9 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。

2.2.2碳储量空间分布及其变化塔里木河上中游生态系统碳储量空间分布具有较强的空间异质性，2000年、2010年和2018年碳储量格局基本无较大变化(图4)，总体表现出东高西低、南高北低的趋势，并且呈现出碳储量高值以塔里木河上中游为条带向四周波动递减的空间分布特征。从不同河段来看，塔里木河上中游地区碳储量高值区主要集中在新其满-英巴扎和英巴扎-乌斯满两个河段，年均碳储存量分别为 $2 8 . 1 3 \mathrm { T g } \setminus 2 6 . 9 6 \mathrm { T g }$ ,年均碳密度分别为 $6 7 . 7 9 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } , 7 8 . 3 5 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。这两个河段是林地分布的主要区域，植被覆盖度高且生长状况良好，人类活动干扰程度较小，自然植被保持较好。阿拉尔-新其满是耕地的主要分布区，碳储量次之，年均碳储量和碳密度分别为 $2 2 . 7 4 \mathrm { T g } \cdot 5 7 . 1 2 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。此外，虽然乌斯满-恰拉河段的碳储量最低(年均碳储量为 $1 8 . 0 1 \mathrm { T g }$ ),但是由于该河段是草地的主要分布区,植被覆盖度较高,年均碳密度达到 $7 9 . 4 8 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 。

![](images/7d7d6ea340e854a939070892a5c02d12e748d64d36279b2abf1e115806f31e55.jpg)  
图32000—2018年塔里木河上中游各土地利用类型下碳储量/碳密度变化  
Fig.3 Changes of carbon storage/caron density under diferent land use types in the mainstream area of the Tarim River during 20o0-2018

![](images/995a540825d1de3a833d353539faf2f899a464da9beffa778b4158dc02a38a0a.jpg)  
图42000—2018年塔里木河上中游碳储量空间分布  
Fig.4 Spatial distribution of carbon storage in the mainstream area of the Tarim River during 2000-2018

碳储量变化显著区域在空间分布上与土地利用变化区域基本一致(图5)。2000—2018年塔里木河上中游碳储量空间变化表现为阿拉尔-新其满、新其满-英巴扎南部、新其满-乌斯满北部和乌斯满-恰拉北部碳储量明显增加，新其满-英巴扎北部、英巴扎-恰拉中部以及东部碳储量明显减少;2000—2010年和2000—2018年碳储量变化空间分布基本一致,阿拉尔-新其满西部、新其满-英巴扎南部、英巴扎-恰拉西部碳储量明显增加，阿拉尔-新其满东部、新其满-英巴扎北部、英巴扎-恰拉中部和东部明显减少。2000—2010年阿拉尔-新其满西部、乌斯满-恰拉北部碳储量明显增多，阿拉尔-新其满中部、新其满-英巴扎、英巴扎-乌斯满主要表现为碳储量增加和减少并重。

# 3讨论

研究区2000年、2010年、2018年的平均总碳储量为 $9 3 . 5 4 \mathrm { T g }$ ，平均碳密度仅有 $6 7 . 5 1 \ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ,远低于我国其他区域，如甘肃嘉酒地区的 $3 2 2 . 2 0 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 甘肃白龙江流域的 $1 3 6 . 4 6 \mathrm { ~ t ~ } \cdot \mathrm { h m } ^ { - 2 }$ 、贵州晴隆县的$1 7 3 . 1 0 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 、北京延庆县的 $1 1 5 . 0 4 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ 江西省赣江的 $9 5 . 7 8 \ \mathrm { t \cdot h m } ^ { - 2 [ 3 3 - 3 7 ] }$ 。主要原因是整个塔里木河区年平均降水量小于 $5 0 ~ \mathrm { m m }$ ，蒸发能力大于2300$\mathbf { m } \mathbf { m }$ ,属极端干旱地区，将近一半以上的面积为荒漠和裸地[38],地上生物碳密度和土壤碳密度都显著较低。

从不同土地利用类型分析，2000年、2010年、

![](images/5b9640f077b8a71a14cfaff1ecb6f74c49908767cb68b2e8b147747809cd2ab2.jpg)  
图52000—2018年塔里木河上中游碳储量变化空间分布  
Fig.5Spatial distribution of carbon storage change in the mainstream area of the Tarim River during 2000-2018

2018年林地平均碳密度为 $7 3 . 7 7 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ,显著低于新疆其他地区森林碳密度，如尉犁县有林地平均碳密度为 $1 2 0 . 0 3 \mathrm { ~ t } \cdot \mathrm { h m } ^ { - 2 }$ ,阿尔泰山森林平均碳密度为$2 0 5 . 7 2 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 \left[ 2 8 - 2 9 \right] }$ 。草地的平均碳密度为 $7 3 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ，与尉犁县草地平均碳密度( $6 2 . 6 4 \mathrm { ~ t ~ } \cdot \mathrm { h m } ^ { - 2 }$ )基本相同。本研究还计算了塔里木河上中游 $0 { \sim } 1 0 0 ~ \mathrm { c m }$ 的土壤碳密度，土壤碳密度在碳总密度中的占比较大，最高达到 $9 9 . 1 3 \%$ ,其中草地的平均土壤碳密度为 $6 8 . 6 6 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ，高于徐自为等29估算的新疆尉犁县草地的土壤平均碳密度 $( 6 0 . 6 9 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } )$ )。但与内蒙古草地生态系统相比，该区域 $0 { \sim } 2 0 ~ \mathrm { c m }$ 平均有机碳密度为 $3 6 . 9 0 \ \mathrm { t \cdot h m } ^ { - 2 [ 3 9 ] }$ ,依据草原土壤表层前 $2 0 ~ \mathrm { c m }$ 的土壤中有机碳密度的储量为前 $1 \mathrm { m }$ 的 $4 2 \%$ 这一经验值来计算[40],塔里木河上中游土壤碳密度仍低于其他地区。

农业灌溉经济一直是塔里木河重要的经济来源。建国初期至20世纪90年代，农业生产的发展主要依靠扩大耕地面积。2000年以后，随着粮食和棉花价格快速上升，在经济的驱动下，掀起了以家庭农场为主的开垦热潮，因此上中游大量的林草地和未利用地被开垦为耕地，造成耕地面积急剧增加[41]。此外,2000年开始的塔里木河综合治理工程和2010年实施的水资源管理体制改革引起干流区水量的重新分配[2],使得土地利用/覆被类型发生重大变化。可见，人口增长和经济发展因素以及水资源的再分配是塔里木河土地类型变化的最直接驱动力[42]

从碳储量的变化来看，水资源管理不断增强的近 $2 0 \mathrm { a }$ ,塔里木河上中游土地利用转移主要发生在耕地、林地、草地和未利用地之间。其中2000—

2010年碳储量增长的主要原因如下：首先，耕地面积的增加，增加的耕地主要来自草地（占 $6 4 . 8 1 \%$ ，使得大量碳密度较低的草地类型（ $\left( 6 9 . 3 5 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } \right)$ 转化成碳密度较高的耕地类型( $7 3 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } ,$ ，还有部分以沙漠、盐碱地、裸地为代表的未利用地 $( 6 3 . 5 9 \mathrm { ~ t ~ }$ ：$\mathrm { h m } ^ { - 2 }$ )也被开垦为耕地;其次，自2000年开始实施塔里木河综合治理，塔里木河上中游地下水位抬升 $2 \sim$ $4 \mathrm { m }$ ,对植被恢复起到了积极作用，生态环境出现了明显的好转[17],导致生物量的增加,使得林地、草地的碳密度和碳储量增加。2010—2018年碳储量损失的途径主要是林地面积的减少，增加的耕地面积中 $5 3 . 3 3 \%$ 来自林地，使得大量碳密度较高的林地类型 $( 7 3 . 7 7 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ )转化成碳密度较低的耕地类型（73$\mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ )。此外，草地向荒漠转化、过度放牧以及草地资源的不合理利用等因素，导致草地面积减少迅速，使得草地总碳储量也在减少，这与新疆其他地区草地碳储量下降的研究结果[4相吻合。

由于InVEST模型的碳模块对碳循环过程进行了简化，它主要是利用动态的每种土地利用类型碳密度估算碳储量，这在一定程度上会降低估算的精确度。本文利用2000年、2010年和2018年三期影像进行解译，时间间隔约 $1 0 \mathrm { a }$ ，影像解译的误差可能会大于后续的模型估计的误差，出现不同土地类型碳密度差异化小，这在一定程度上也会降低估算精度。在未来的研究中，应通过高分辨影像提高对土地利用/覆被数据的解译精度。同时加强野外调查，通过收集大量实测数据获取动态碳密度，并对评估结果进行验证，从而提高碳储量估算精度。

# 4结论

（1）2000年、2010年、2018年塔里木河上中游的总碳储量分别为 $9 3 . 7 0 \mathrm { T g } \ . 9 3 . 9 2 \mathrm { T g } \ . 9 3 . 0 1 \mathrm { T g } \ L _ { \odot }$ 。林地是塔里木河上中游的主要碳库、草地次之。2000—2010年碳储量增加主要由于大量碳密度较低的草地类型 $\left( 6 9 . 3 5 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } \right)$ 转化成碳密度较高的耕地类型 $( 7 3 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } ,$ )。此外，塔里木河综合治理实施也使地表生物量增多，导致林地、草地的碳密度和碳储量增加；2010一2018年碳储量减少，碳损失途径主要源于大量碳密度较高的林地类型 $( 7 3 . 7 7 \mathrm { ~ t ~ }$ ·$\mathrm { h m } ^ { - 2 } .$ 转化成碳密度较低的耕地类型 $( 7 3 \mathrm { ~ t } \cdot \mathrm { h m } ^ { - 2 } )$ 。同时草地向荒漠转化以及过度放牧使得草地面积迅速减小，导致草地总碳储量降低。

(2)塔里木河上中游生态系统碳储量空间分布具有较强的空间异质性，2000年、2010年、2018年碳储量格局基本无较大变化，总体呈现出碳储量高值以塔里木河上中游为条带向四周波动递减的空间分布特征。碳储量变化显著区域在空间分布上与土地利用变化区域基本一致。在不同河段，储量高值区主要集中在新其满-英巴扎和英巴扎-乌斯满两个河段，2000—2018年平均碳储存量分别为$2 8 . 1 3 \mathrm { T g } \setminus 2 6 . 9 6 \mathrm { T g }$

（3）为提升塔里木河上中游生态系统固碳功能，首先应控制上中游地区水资源无节制、掠夺式地开发利用，改变现状开发格局和用水规模，优化水资源配置，改善植被生境条件，提高生态系统的质量和稳定性;其次继续推进生态建设工程，通过扩大林地、草地面积来提高流域生态系统固碳能力，同时对塔里木河上中游周边碳密度较高的林地、草地重点保护,严格控制耕地开垦。

# 参考文献(References)：

[1]He Chunyang, Zhang Da,Huang Qingxu, et al. Assessing the po tential impacts of urban expansion on regional carbon storage by linking the LUSD-urban and InVEST models[J]. Environmental Modelling & Software,2016,75: 44-58.   
[2] 王渊刚,罗格平,赵树斌,等.新疆耕地变化对区域碳平衡的影 响[J].地理学报,2014,69(1):110-120.[Wang Yuangang,Luo Geping,Zhao Shubin,et al. Effects of arable land change on regional carbon balance in Xinjiang[J].Acta Geographica Sinica, 2014,69(1): 110-120.]   
[3] Sterling S M,Ducharne Agnes,Polcher J.The impact of global land-cover change on the terrestrial water cycle[J].Nature Climate Change,2012,3(4): 385-390.   
[4] VitousekPM,Mooney HA,LubchencoJ,etal.Human domination of earth's ecosystems[J]. Science,1997,277(5325): 494-499.   
[5] 高扬，何念鹏,汪亚峰.生态系统固碳特征及其研究进展[J].自 然资源学报,2013,28(7):1264-1274.[Gao Yang,He Nianpeng, Wang Yafeng. Characteristics of carbon sequestration by ecosystem and progress in its research[J]. Journal of Natural Resources, 2013,28(7): 1264-1274.]   
[6] 张云倩,张晓祥,陈振杰,等.基于InVEST模型的江苏海岸带生 态系统碳储量时空变化研究[J].水土保持研究,2016,23(3): 100-105.[Zhang Yunqian, Zhang Xiaoxiang, Chen Zhenjie,et al. Research on the spatiotemporal variation of carbon storage in coastal zone ecosystem of Jiangsu based on InVEST Model[J].Research of Soil and Water Conservation,2016,23(3):100-105.] [7]Andreetta A,Huertas A D,Loti M,et al.Land use changes affecting soil organic carbon storage along a mangrove swamp rice chronosequence in the Cacheu and Oio regions (northern Guinea-Bissau)[J].Agriculture,Ecosystems and Environment，2016,216:   
314-321. [8]Gelaw A M,Singh BR,Lal R .Soil organic carbon and total nitrogen stocks under diferent land uses in a semi-arid watershed in Tigray,Northern Ethiopia[J].Agriculture,Ecosystemsand Environment,2014,188:256-263. [9]方精云,郭兆迪,朴世龙,等.1981—2000年中国陆地植被碳汇 的估算[J].中国科学(D辑:地球科学),2007,37(6):804-812. [Fang Jingyun, Guo Zhaodi,Piao Shilong,et al. Assessment of China terrestrial vegetation carbon sinks in 1981-2000[J]. Science in China(Series D),2007,37(6): 804-812.] [10]方精云,刘国华,徐嵩龄.我国森林植被的生物量和净生产量 [J].生态学报,1996,16(5): 497-508.[Fang Jingyun,Liu Guohua, Xu Songling. Biomass and net production of porest vegetation in China[J].Acta Ecologica Sinica,1996,16(5): 497-508.] [11]朴世龙,方精云,贺金生,等.中国草地植被生物量及其空间分 布格局[J].植物生态学报,2004,28(4):491-498.[Piao Shilong, Fang Jingyun,He Jinjie,et al.Spatial distribution of grassland biomass in China[J]. Acta Phytoecologica Sinica,2004,28(4):491-   
498.] [12]王淑君,管东生,黎夏,等.广州森林碳储量时空演变及异质性 分析[J].环境科学学报,2008,28(4):778-785.[Wang Shujun, Guan Dongsheng,Li Xia,et al. The spatial-temporal evolution and heterogeneityanalysisof forest carbon storage in Guangzhou, China[J].Acta Scientiae Circumstantiae,2008,28(4): 778-785.] [13] 杨玉海,陈亚宁,李卫红,等.塔里木河干流土地利用/覆被变化 对土壤有机碳储量的影响[J].中国环境科学,2016,36(9):   
2784-2790.[Yang Yuhai, Chen Yaning,Li Weihong,etal.Effects of land use/cover change on soil organic carbon storage in the mainstream of Tarim River[J]. China Environmental Science,   
2016,36(9): 2784-2790.] [14]尚二萍,张红旗.1980s—2010s新疆伊犁河谷草地碳存储动态 评估[J].资源科学,2016,38(7):1229-1238.[Shang Erping, Zhang Hongqi. Dynamic assessment of the carbon stock of different grassland types in the Yili Valley from 198Os to2010s[J].Resources Science,2016,38(7): 1229-1238.] [15]Bae J, Ryu Y. Land use and land cover changes explain spatial and temporal variations of the soil organic carbon stocks in a constructed urban park[J]. Landscape & Urban Planning,2015,136 (136): 57-67. [16] 邓铭江,周海鹰,徐海量,等.塔里木河干流上中游丰枯情景下 生态水调控研究[J].干旱区研究,2017,34(5):959-966.[Deng Mingjiang, Zhou Haiying, Xu Hailiang,et al.Regulation of ecological water volume under high-or low-flow in the mainstream area of the Tarim River[J].Arid Zone Research,2017,34(5): 959-966.] [17] 黄运梅,徐海量,张广朋,等.基于年轮信息的单株胡杨(Populus euphratica)树干年新增生物量估算方法[J].干旱区研究,   
2018,35(4): 905-911.[uang Yunmei,XuHailiangZhang Guang peng,et al.Estimation of annual biomass of individual Populus euphratica based on tree-ring data[J]. Arid Zone Research,2018,35 (4): 905-911.] [18] 陈亚宁,崔旺诚,李卫红,等.塔里木河的水资源利用与生态保 护[J].地理学报,2003,58(2):215-22.[Chen Yaning,Cui Wangcheng,Li Weihong, et al.The influence of groundwater on vegetation in the lower reaches of Tarim River,China[J].Acta Geographica Sinica,2003,58(2): 215-222.] [19] 徐海量,陈亚宁,杨戈.塔里木河下游生态输水对植被和地下水 位的影响[J].环境科学,2003,24(4):18-22.[Xu Hailiang,Chen Yaning,Yang Ge.Effct of translating water on vegetation at the lower reaches of Tarim River[J]. Chinese Journal of Environmental Science,2003,24(4): 18-22.] [20] 徐海量,陈亚宁,李卫红.塔里木河下游生态输水后地下水的响 应研究[J].环境科学研究,2003,16(2):19-22,38.[Xu Hailiang, Chen Yaning,Li Weihong.Study on response of groundwater after ecological water transport at the lower reaches of the Tarim River [JJ.Research of Environmental Sciences,2003,16(2): 19-22,38.] [21] 熊宇斐,张广朋,陈超群,等.基于水量变化的塔里木河统一管 理成效评价[J].自然资源学报,2016,31(11):1806-1816. [Xiong Yufei, Zhang Guangpeng, Chen Chaoqun,et al.Effectiveness evaluation of the unified management based on water change in Tarim River Basin[J].Journalof Natural Resources,2016,1 (11): 1806-1816.] [22] Chen Yaning, Takeuchi K, Xu Changchun,et al. Regional climate change and its effectson river runoffin the Tarim Basin, China[J]. Hydrological Processes,2006,20(10): 2207-2216. [23] 徐海量,叶茂,宋郁东,等.塔里木河流域水资源变化的特点与 趋势[J].地理学报,2005,60(3): 487-494.[Xu Hailiang, Ye Mao, Song Yudong,et al. The dynamic variation of water resources and its tendency in Tarim River Basin[J].Acta Geographica Sinica,   
2005, 60(3): 487-494.] [24] 叶茂,徐海量,宋郁东,等.塔里木河流域水资源利用面临的主 要问题[J].干旱区研究,2006,23(3):388-392.[Ye Mao,Xu Hailiang, Song Yudong, et al. Some problems and challenges about wateresources utiizationinthe Tarim RiverBasin[J].Arid ZoneResearch,2006,23(3): 388-392.] [25] 张广朋,徐海量,杜清,等.塔里木河流域降水量的非线性时空 变化对比研究及预测[J].水资源与水工程学报,2015,26(2):   
58-63.[Zhang Guangpeng,Xu Hailiang,Du Qing,et al. Comparative study and prediction of nonlinear temporal and spatial variation of precipitation in Tarim River Basin[J]. Journal of Water Resources and Water Engineering, 2015,26(2): 58-63.] [26] 白元,徐海量,凌红波,等.塔里木河干流区天然植被的空间分 布及生态需水[J].中国沙漠,2014,34(5):1410-1416.[Bai Yuan, Xu Hailiang,Ling Hongbo,et al.Spatial distribution characteristics and ecological water requirement of natural vegetation along

the mainstream of the Tarim River[J]. Journal of Desert Research,

2014,34(5): 1410-1416.]   
[27] Talls H T,Rickets T,Guerry A D,et al. In VEST 2.6.0 user' s guide.Stanford CA:The Natural Capital Project,2013,24-29: 233-250.   
[28] 郑拴丽,许文强,杨辽,等.新疆阿尔泰山森林生态系统碳密度 与碳储量估算[J].自然资源学报,2016,31(9):1553-1563. [Zheng Shuanli,Xu Wenqiang,Yang Liao,et al.Carbon density and storage of forest ecosystem in Altay Mountains,Xinjiang[J] Journal of Natural Resources,2016,31(9): 1553-1563.]   
[29] 徐自为,张智杰.基于土地利用变更调查的2010—2016年新疆 尉犁县生态系统碳储量时空变化[J].环境科学研究,2018,31 (11):1909-1917.[Xu Ziwei, Zhang Zhijie. Spatiotemporal variation of carbon storage in Yuli County during 2010-2016[J]. Research of Environmental Sciences,2018,31(11): 1909-1917.]   
[30]包玉斌.基于InVEST模型的陕北黄土高原生态服务功能时空 变化研究[D].西安:西北大学,2015.[Bao Yubin.Temporal and Spatial Change of Ecological Services on Loess Plateau of Shaanxi by InVEST model[D]. Xi'an: Northwest University,2015.]   
[31] 方精云,杨元合,马文红,等.中国草地生态系统碳库及其变化 [J].中国科学(生命科学),2010,40(7): 566-576.[Fang Jingyun, Yang Yuanhe,Ma Wenhong,et al.Ecosystem carbon stocks and their changes in China’s grasslands[J]. Scientia Sinica Vitae(Life Sciences),2010,40(7): 566-576.]   
[32] 于东升,史学正,孙维侠,等.基于1:100万土壤数据库的中国 土壤有机碳密度及储量研究[J].应用生态学报,2005,16(12): 2279-2283.[Yu Dongsheng,Shi Xuezheng,Sun Weixia,et al.Estimation of China soil organic carbon storage and density based on 1: 100000O soil database[J]. Chinese Journal of Applied Ecology, 2005,16(12): 2279-2283.]   
[33] 李真.干旱内陆河流域生态系统服务空间权衡与协同研究[D]. 兰州：西北师范大学,2017.[Li Zhen.The Dynamic Analysis on Trade-off sand Synergies of Ecosystem Services in the Arid Inland River Basin[D].Lanzhou: Northwest Normal University,2017.]   
[34] 张影,谢余初,齐姗姗,等.基于InVEST模型的甘肃白龙江流域 生态系统碳储量及空间格局特征[J].资源科学,2016,38(8): 1585-1593.[Zhang Ying,Xie Yuchu, Qi Shanshan,et al. Carbon storage and spatial distribution characteristics on the Bailongjiang watershed in Gansu based on InVEST model[J].Resources Science,2016,38(8): 1585-1593.]   
[35] 张斯屿,白晓永,王世杰,等.基于InVEST模型的典型石漠化地 区生态系统服务评估——以晴隆县为例[J].地球环境学报, 2014,5(5): 328-338.[Zhang Siyu, Bai Xiaoyong,Wang Shijie, et al.Ecosystem services evaluation of typical rocky desertification areas based on InVEST model: A case study at Qinglong County, Guizhou Province[J].Journal of Earth Environment,2O14,5(5): 328-338.]   
[36]李敏.基于InVEST模型的生态系统服务功能评价研究[D].北 京:北京林业大学,2016.[Li Min.Ecosystem Services Evaluation Based on InVEST Model: ACase study of Yanqing,Beijing[D]. Beijing: Beijing Forestry University,2016.]   
[37] 贾芳芳.基于InVEST模型的赣江流域生态系统服务功能评估 [D].北京:中国地质大学,2014.[Jia Fangfang.InVEST Model Based Ecosystem Services Evaluation with case case study on Ganjiang River Basin[D]. Beijing: China University of Geosciences, 2014.]   
[38] 白元,徐海量,凌红波,等.塔里木河干流区土地利用与生态系 统服务价值的变化[J].中国沙漠,2013,33(6):1912-1920.[Bai Yuan,Xu Hailiang,Ling Hongbo,et al. Analysis on land use changes and ecosystem services value in the area along the Tarim River[J]. Journal of Desert Research,2013,33(6): 1912-1920.]   
[39] 戴尔阜,翟瑞雪,葛全胜,等.1980s—2010s 内蒙古草地表层土 壤有机碳储量及其变化[J].地理学报,2014,69(11):1651-1660. [Dai Erfu, Zhai Ruixue,Ge Quansheng, et al. Topsoil organic carbon storage and its changes in Inner Mongolia grassland from the 1980s to 2010s[J].Acta Geographica Sinica,2014,69(11): 1651-1660.]   
[40] 方岳,刘华,白志强,等.新疆喀纳斯保护区森林碳储量及碳密 度研究[J].南京林业大学学报(自然科学版),2014,38(6):17-22. [Fang Yue,Liu Hua,Bai Zhiqiang,et al. Spatial patern of carbon storage and carbon density in forest vegetation of the Kanas National Natural Reserve[J]. Journal of Nanjing Forestry University (Natural Sciences Edition),2014,38(6): 17-22.]   
[41] 赵锐锋,陈亚宁,李卫红,等.塔里木河干流区土地覆被变化与 景观格局分析[J].地理学报,2009,64(1): 95-106.[Zhao Ruifeng, Chen Yaning,Li Weihong,et al.Land cover change and landscape pattern in the mainstream of the Tarim River[J]. Acta Geographica Sinica,2009,64(1): 95-106.]   
[42] 孙美琴,赵成义,施枫芝,等.近20a塔里木河干流区土地利用 变化特征[J].干旱区研究,2013,30(1):16-21.[Sun Meiqin, Zhao Chengyi, Shi Fengzhi,et al.Analysis on land use change in the mainstream area of the Tarim River in recent 2O years[J]. Arid Zone Research,2013,30(1): 16-21.]

# Dynamic assessment of Tarim River carbon storage under enhanced water resources management

GUO Jing12，WANG Guangyan'， XU Shengwu', ZHANG Guangpeng123, YUAN Kaiyel23，LING Hongbo12， Xiayidan Wumaierjiang§ (1.State KeyLaboratoryof Desert andOasis Ecology,Xinjiang Instituteof Ecologyand Geography,Chinese Academy of Sciences,Urumqi 830o11,Xinjiang, China; 2.Akesu National Station of Observation and Research for Oasis Agroecosystem,Akesu843017,Xinjiang,China;3.UniversityofChinese AcademyofSciences,Beijing1049,China;   
4.Management Bureau of the Main Stream of Xinjiang Tarim River Basin, Korla 841OOo, Xinjiang, China;   
5. Xinjiang Tarim River Basin Management Bureau, Korla 832OOo, Xinjiang, China)

Abstract: Since the implementation of comprehensive governance in 2Ool and unified management in 2011,the water resources management capacity of the Tarim River Basin has been continuously enhanced.However, the effectiveness of water resources management at improving the carbon storage capacity of watershed ecosystems has not been evaluated.Therefore,based on land use/cover change data from 2000,2010,and 2018,this paper used the InVEST model to analyze the change characteristics of the carbon storage of watershed ecosystems under enhanced water resources management in the upper and middle reaches of the Tarim River where Populus euphratica forest is concentrated.In 20o0,2010,and 2018,the total carbon storage in the upper and middle reaches of the Tarim River was 93.70,93.92,and 93.01 Tg,respectively,and the average carbon density was 67.63, 67.78, and $6 7 . 1 2 \ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 }$ ， respectively. Woodland was the primary carbon pool in the upper and middle reaches of the Tarim River Basin,followed by grassland.From 2000 to 2010,the carbon storage in the study area increased by $0 . 2 2 ~ \mathrm { T g }$ ，primarily due to the conversion of a large number of grassland types ( $6 9 . 3 5 \ \mathrm { t \cdot h m ^ { \cdot 2 } }$ into arable land types( $( 7 3 \ \mathrm { t } \cdot \mathrm { h m ^ { - 2 } }$ ). After the implementation of comprehensive management of the Tarim River in 2001,vegetation restoration led to an increase in the surface biomass,carbon density,and carbon storage of woodland and grassland. From 2010 to 2018,carbon storage decreased by $0 . 9 1 \mathrm { T g }$ ,and the carbon loss pathways primarily originated from the conversion of a large number of woodland types $( 7 3 . 7 7 \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } )$ to arable land types $( 7 3 ~ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } )$ . Simultaneously,the total carbon storage of grassland decreased. The spatial distribution of carbon storage inthe studyarea had a strong spatial heterogeneity,and itscharacteristics gradualydecreased around the upper and middle reaches of the Tarim River. The areas with significant changes in carbon storage were consistent with the spatial distribution of land use changes.This research provides a scientific basis for an indepth understanding of the carbon cycle and climate change in the study area,informing the improvement of the carbon storage capacity of the watershed ecosystem, optimizing the allocation of water resources,and promoting the sustainable development of river basins.

Keywords: InVEST model; water resources management; carbon storage； land use/cover change; Tarim River