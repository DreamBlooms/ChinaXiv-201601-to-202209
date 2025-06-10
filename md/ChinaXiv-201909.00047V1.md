# 吉林省松花江流域景观格局脆弱性变化及其驱动力

孙鸿超，张正祥（东北师范大学地理科学学院，吉林 长春130024)

摘要：本文以吉林省松花江流域为研究区,以1995年、2005年和2015年3期LandsatTM/ETM影像为数据源,对吉林省松花江流域景观格局、生态脆弱度的时空分布和变化特征及驱动力进行研究,结论如下： $\textcircled{1}$ 流域不同时期气候变化存在差异,景观优势类型以耕地和林地为主,城乡用地和草地稳定增长,林地、耕地、水域呈减少趋势。 $\textcircled{2}$ 流域脆弱度以较低脆弱区和中度脆弱区为主,低脆弱区和中度脆弱区主要分布在流域中游和下游较发达地区,高脆弱区主要分布在流域东南地区和下游西北荒漠化及林草地破坏区域。 $\textcircled{3}$ 流域脆弱度总体相对稳定，呈略微上升和两极分化的趋势;脆弱度与人为活动密切相关,与地形有一定相关性,受气候变化影响并不显著，但仍能反映部分问题。

关键词：景观格局；脆弱度；时空分布；驱动力；土地利用；随机森林；松花江流域；吉林

20世纪80年代以来，景观格局受到越来越多的学者关注，成为全球环境问题的关键内容和当前国内外研究的热点之一[1-2]。景观作为多种栖息地斑块的有机结合体，为人类生存提供适宜的环境，具有很强的综合性和鲜明的区域性。景观格局是指不同形状和大小的斑块在空间上的各种排列组合，是景观异质性的具体体现，对生态过程有重要意义[3-4],能够较好地反应区域生态系统的脆弱度[5]。目前，国内外对于景观格局研究多集中于LUCC和景观格局变化[6-8]、生态安全与生态风险等领域[9-1],脆弱度研究并不多见,孙才志等对下辽河平原,张月等对艾比湖，梁二敏等对新疆玛纳斯河流域绿洲进行了景观格局脆弱度分析(12-14],这些研究多是对研究区格网化计算景观指数再进行插值，忽略了景观尺度效应问题，而且研究多为脆弱度的格局分布和空间变化，分析其空间自相关性，很少结合人为和自然因素来考虑景观脆弱度分布格局形成与变化的原因。

景观格局在某种程度上决定着生态与环境的质量，与各生态过程密切相关，对系统稳定性和生物多样性有重大影响[15]。景观脆弱度体现了系统受到外界的干扰和脆弱程度，是评价区域生态的有效指标[16]。河流是人类生存与繁衍的基础,流域生态系统的完好是人类发展和经济运行的重要保证，流域生态的问题也是当前关注的焦点[17]，其景观格局及脆弱度的研究对于流域环境保护及合理开发具有重要意义，松花江是我国重点流域，也是吉林省的母亲河，20a来气候及环境发生显著变化，并引起了草地沙化和盐碱化等问题[18]。本文对1995 年、2005 年和2015年松花江流域吉林省部分的LandsatTM和$\mathrm { E T M } +$ 影像数据进行解译，得到研究区这3个时期的景观分布图，通过建立相应的景观格局指数构造生态脆弱度模型，利用Fragstats、ArcGIS等软件，通过移动窗口法获取1995—2015 年松花江流域（吉林省)景观脆弱度时空分布和变化,并结合人为和自然因素，对驱动力进行研究。研究成果对指导松花江流域景观资源的合理开发和利用，以及生态恢复具有一定的指导作用和应用价值。

# 研究区概况

松花江流域位于 $1 1 9 ^ { \circ } 5 2 ^ { \prime } \sim 1 2 9 ^ { \circ } 3 0 ^ { \prime } \mathrm { E }$ ? $4 1 ^ { \circ } 4 2 ^ { \prime } .$ ）$5 1 ^ { \circ } ~ 3 8 ^ { \prime } \mathrm { N }$ 之间,流域面积 $5 . 5 7 \times 1 0 ^ { 5 } \ \mathrm { k m } ^ { 2 }$ 。其中吉林省松花江流域面积约 $9 . 4 9 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ ,范围见图1。地势的总体趋势呈西北低、东南高。流域西北部属于平原丘陵地貌，海拔在 $1 0 0 \sim 2 0 0 \mathrm { ~ m ~ }$ ，其中北部属于低山丘陵区，南部属于长白山山系，西部为松嫩平原，是松花江流域的主要农业区域,海拔 $5 0 \sim 2 0 0$ m。流域具有明显的大陆性季风气候，冬季严寒漫长，夏秋季降雨集中，春季干燥多风,年内温差较大。流域多年的平均气温在 $4 \mathrm { ~ \textdegree C }$ 左右，平均降水量在$6 7 0 ~ \mathrm { m m }$ 左右，存在明显的空间差异，呈现出由南向北递减的趋势。流域矿产丰富，土地肥沃。虽是黑龙江的支流，但对东北地区的人民生活及农业生产的意义都超过了黑龙江和其他河流，因此，流域的生态研究非常重要，选取吉林省辖区部分作为研究区。

![](images/6a17e7a9760ca63827b94cda77ddadcdf7c8739c14ed46bf1f9c21bf82d1f12e.jpg)  
图1研究区区位图  
Fig.1Geographical location of the study area

# 2 数据来源与研究方法

# 2.1 数据来源与处理

本研究通过地理空间数据云网站，选取吉林省松花江流域1995年、2005年、2015年时相为6—10月的LandsatTM和ETM $^ +$ 影像数据，每年15景影像图，植被覆盖率较高，影像包含的信息丰富，云覆盖度小，影像清晰容易判读，通过ENVI软件进行几何校正、图像增强等处理，结合野外调查和相关资料进行室内解译，得到3期吉林省松花江流域景观类型分布图。通过矢量化获得流域道路和城市点及水系数据;DEM与气象数据、GDP及人口网格分布数据来自中国科学院资源环境科学数据中心（http：//www.resdc.cn/)

# 2.2 景观指数的选取与脆弱度指数的构建

景观格局脆弱度包含敏感性和适应性两方面。敏感性即在不同时间和空间尺度上系统对于干扰的反应;适应性即景观系统对外界的干扰产生敏感性响应之后，其最终受到干扰后的适应性调整能力[12]。结合前人研究,本文通过景观敏感度指数、景观适应度指数构建景观脆弱度评价模型。

2.2.1景观敏感度指数景观敏感度指数是指景观在受自然环境变化或人为活动干扰时的反应程度，表征发生生态环境问题的难易程度，其变化速率越快,敏感性越强[19]。景观敏感度指数 $( L S I )$ 计算公式为：

$$
L S I = \sum _ { i = 1 } ^ { n } U _ { i } \times V _ { i }
$$

式中： $n$ 为景观类型数目； $i$ 为景观类型； $U _ { i }$ 为景观干 扰度指数； $V _ { i }$ 为景观易损度指数。

# （1）景观干扰度指数 $( U _ { i } )$ （204号

本文采用具有代表性并且与干扰密切相关的景观类型破碎度、分维数倒数和优势度3种指数为基础指标构建景观类型干扰度指数，公式如下：

$$
U _ { i } = a F N _ { i } + b F D _ { i } + c D O _ { i }
$$

式中： $F N _ { i }$ 为破碎度指数，数值越小表明破碎度越小； $F D _ { i }$ 为分维数倒数，其值愈趋近于1，几何形状越简单，表明受干扰越多，反之愈趋近于2,结果越复杂，自然性越强； $D O _ { i }$ 为优势度指数，表明受景观类型控制程度。因此，这3个指标构建出来的干扰度指数能够较好地反映景观受干扰程度。借鉴前人相关的研究成果，将权重分别设定为0.5、0.3和0.2[20] ○

# （2）景观易损度指数( $V _ { i } )$

景观易损度指数表示景观类型与土地利用易损程度的有效结合，借鉴他人研究成果[12],结合专家经验和流域实际情况，将景观类型赋以相对权重，反应各景观类型的易损度：未利用地-7，林地、草地-5，耕地-3，建设用地、水域-1。2.2.2景观适应度指数景观生态脆弱度不仅与敏感性有关,而且与本身的适应性密切相关[21]。系统结构越复杂且分布均匀、多样性和功能越强，则景观生态系统越稳定，对外界干扰的适应能力越强，反之亦然。研究发现斑块丰富度指数(RPR)和物种丰富度存在很好的正相关[22-23];Simpson 多样性指数(SIDI)在生态学中应用广泛，其与物种多样性有着紧密联系;Shannon均匀指数（SHEI)表示不同景观类型分配的均匀程度，其越高表明分配越均匀，系统越稳定。因此，选取这3个能够表达生态意义且符合研究区情况的指数构建适应度指数 $( L A I )$ ：

$$
L A I = R P R \times S I D I \times S H E I
$$

2.2.3景观脆弱度指数结合景观敏感度指数$( L S I )$ 和景观适应度指数 $( L A I )$ ,构建景观脆弱度指数 $( L V I ) ^ { [ 1 2 , 1 4 , 2 4 ] }$ ,其值的大小是流域景观格局生态脆弱情况的定量表达：

$$
L V I = L S I ( 1 - L A I )
$$

# 2.3 驱动力指标定量

2.3.1土地利用动态变化模型本文采用庄大方等[25]提出的土地利用程度综合指数 $( L )$ 作为人类活动对景观格局干扰的明显指标，具体公式如下：

$$
L = 1 0 0 \times \sum _ { i = 1 } ^ { n } \left( A _ { i } \times C _ { i } \right)
$$

式中： $L$ 为栅格单元的土地利用综合程度指数； $A _ { i }$ 为栅格单元第 $\mathbf { \chi } _ { i }$ 级地类分级指数； $C _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 级地类占网格全部地类面积的比重。根据相关文献[25],将土地利用分为4个级别，分别是未利用地-1，林地、草地、水域-2,耕地-3,建设用地-4。

2.3.2气候要素变化趋势分析本文采用 Sen 趋势度法对流域1995—2005 年、2005—2015 年两个时间段的温度及降水进行变化趋势计算，是计算序列的中值，它可以很好地减少噪声的干扰，其公式如下：

$$
\beta = \mathrm { M e d i a n } \left( { \frac { x _ { j } - x _ { i } } { j - i } } \right) , \forall j > i
$$

式中：Median为中位数函数; $x _ { j }$ 和 $x _ { i }$ 属于待分析趋势的序列数据，表示不同年份的气温或者降水 $\cdot j$ 和 $i$ 代表对应的时间即年份；使用 $\beta$ 来判断温度和降水量在某一时间段内的升降水平，当其大于0时，呈上升趋势，反之呈下降趋势。

2.3.3其他因子选取与定量处理在考虑土地利用程度和气候因素同时，本文还选取了3期对应时间段的GDP和人口分布数据进行重采样，与其他数据分辨率保持一致。通过数字高程模型（DEM)提取流域坡度、坡向，通过ArcGIS计算每个栅格点距城市、道路、河流的距离，生成距离分布图，限于篇幅以2005年部分数据为例，如图2。

# 2.4 随机森林分析

随机森林是一种基于决策树的机器学习算法，每一棵树都是基于Bootstrap样本构建的，然后对多棵树的预测结果进行组合。每个分类树使用2/3的数据来训练随机森林,其余1/3的OOB（out of bag)样本被保留，用以进行模型验证。随机森林通过对指定变量组进行随机而其他变量保持不变，比较由此导致的OOBerror变化来对变量的重要性进行生成。

# 2.5 数据处理

景观脆弱指数和土地利用程度分布图都是用Fragstats和ArcGIS10.2选取99移动窗口计算得出，解决分析尺度问题。为了方便气候变化与景观脆弱度变化进行对比分析，通过python获得研究区1995—2005年与2005—2015年两个时间段的气候变化趋势栅格分布图。对上述所选取驱动力因子栅格图通过ArcGIS导出为ASCII格式，通过R进行相关系数计算并完成随机森林建模及精度检验，获得驱动力的相对重要性。

# 3 结果分析

# 3.1 景观类型变化特征

利用RS和GIS技术，对流域1995年、2005年和2015年6种景观类型进行了解译，得到3期景观分布（图3），通过叠置分析得到两个阶段的景观类型转移矩阵。从表1可以看出，1995—2005年流域整体景观分布比较稳定，主要以耕地和林地为主，但两者随着时间推移都出现大幅减少，城乡用地明显增加，水域面积有所减少。其中，耕地主要转化为城乡用地和林地，说明这10a内随着经济的发展，城镇化比较明显，同时部分地区开展了退耕还林政策，但是整体来看，林地人为破坏加剧，主要表现在林地转化为耕地和草地，说明毁林造田，乱砍乱伐现象的存在。水域面积减少主要转化为耕地、林地和城乡用地，说明人为干扰的情况下出现了水土流失的问题。

从表2可以看出，2005—2015年的变化趋势和前10a大体相似，城镇化现象更为明显，水域和林

![](images/d9f9c4c1b40c802f6badfc6edafebfde400a37effb081952451acf9811b97369.jpg)  
Fig.2Distribution of the driving factors affecting landscape pattern vulnerability in 2005

![](images/e9f56f5e3d4f09f81d23f957763b97b1c359832c1dce7d3520436ba658c2cccd.jpg)  
图22005年景观格局脆弱度驱动因子分布  
图31995—2015 年吉林省松花江流域景观类型分布

Fig.3Distribution of the landscape types in the Songhua River Basin in Jilin during the period of 1995-2015 地转化为未利用地明显增加，说明这一时间段内流域 受气候变化影响，水土流失和荒漠化现象有所体现

Tab.1The transfer matrix of landscape types from 1995 to 20(   
表22005—2015年景观类型转移矩阵  

<html><body><table><tr><td>类型</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>城乡用地</td><td>未利用土地</td><td>合计</td></tr><tr><td>耕地</td><td>43 416.92</td><td>41.45</td><td>7.80</td><td>13.05</td><td>141. 00</td><td>1. 19</td><td>43 621.41</td></tr><tr><td>林地</td><td>122.78</td><td>42 801.20</td><td>48.72</td><td>3.43</td><td>25.79</td><td>1.65</td><td>43 003.57</td></tr><tr><td>草地</td><td>4.58</td><td>2.18</td><td>1 225.22</td><td>0.91</td><td>6.49</td><td>4.92</td><td>1 244.30</td></tr><tr><td>水域</td><td>23.96</td><td>10.82</td><td>1. 22</td><td>1 989.50</td><td>5.89</td><td>0.26</td><td>2 031.65</td></tr><tr><td>城乡用地</td><td>0.57</td><td>1.15</td><td>0.12</td><td>0.03</td><td>4 338.24</td><td>0</td><td>4 340.11</td></tr><tr><td>未利用土地</td><td>8.70</td><td>1.83</td><td>17.03</td><td>0</td><td>0.50</td><td>727.71</td><td>755.77</td></tr><tr><td>合计</td><td>43 577.51</td><td>42 858.63</td><td>1 300.11</td><td>2 006.92</td><td>4 517.91</td><td>735.73</td><td>94 996.81</td></tr></table></body></html>

表11995—2005年景观类型转移矩阵  

<html><body><table><tr><td>类型</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>城乡用地</td><td>未利用土地</td><td>合计</td></tr><tr><td>耕地</td><td>43 271.81</td><td>24.72</td><td>1.33</td><td>8.35</td><td>269.05</td><td>2.25</td><td>43 577.51</td></tr><tr><td>林地</td><td>84.69</td><td>42 652. 43</td><td>75.48</td><td>3.23</td><td>34.99</td><td>7.81</td><td>42 858.63</td></tr><tr><td>草地</td><td>6.10</td><td>2.83</td><td>1 280.19</td><td>2.85</td><td>8.09</td><td>0.05</td><td>1 300.11</td></tr><tr><td>水域</td><td>29.60</td><td>2.13</td><td>2.84</td><td>1 955.97</td><td>3.82</td><td>12.56</td><td>2 006.92</td></tr><tr><td>城乡用地</td><td>0.25</td><td>0.48</td><td>0.03</td><td>0</td><td>4 517.15</td><td>0</td><td>4 517.91</td></tr><tr><td>未利用土地</td><td>4.44</td><td>0.16</td><td>0.11</td><td>0.03</td><td>0.05</td><td>730.94</td><td>735.73</td></tr><tr><td>合计</td><td>43 396.89</td><td>42 682.75</td><td>1 359.98</td><td>1 970.43</td><td>4 833.15</td><td>753.61</td><td>94 996.81</td></tr></table></body></html>

# 3.2 流域气候要素变化

利用python和GIS技术，计算1995—2005年及2005一2015年两个时间段的气候要素变化趋势（图4)。从图4可以明显看出，不同地区气候要素变化具有一定差异，且两个时间段内同一气候要素变化同样具有较大差异性。前 $1 0 \mathrm { ~ a ~ }$ ，流域东南部相对来说增温明显，后十年中部增温比较明显。前10a内，流域西南和西北两个地区雨水持续增加，东南部有干旱趋势，后 $1 0 \mathrm { ~ a ~ }$ 内，流域西南地区雨水依旧增加，东南角的降水开始增多，相对以前，干旱趋势有所改观，但东部依然有部分地区呈现出干旱趋势。将对应年份气温及降水分布图与景观脆弱指数图进行相关分析(表3），各期脆弱指数与气候值相关系数绝对值均不足0.4，相关系数较低，且变动相对较大，其原因是气候对景观变化为长期影响，因此更应结合气候变化趋势图来看，东部林地分散的高脆弱区发生在温度升高和降水减少的地区，西北低脆弱区分布与温度降低、降水较高地区分布一致，说明干旱事件会对景观脆弱度分布有一定影响。

# 3.3景观格局脆弱度及土地利用程度的时空分布

利用ArcGIS及移动窗口法获得3个时期脆弱度分布(图5)与土地利用程度(图6)。本文根据相关文献并结合松花江流域自然地理状况，将研究区分为5个等级，分别为低脆弱区( $L V I { \leqslant } 0 . 0 5 )$ ），较低脆弱区（ $0 . \ 0 5 < L V I \leqslant 0 . \ 1 2 \ \rangle$ ，中度脆弱区( $\ : 0 . 1 2 < \$ $L V I { \leqslant } 0 . 2 0$ ），较高脆弱区( $0 . 2 0 < L V I { \leqslant } 0 . 2 8 \$ ，高脆弱区( $L V I > 0 . 2 8 )$ ，并对不同时期5个分区占总区域的百分比进行了统计。

Tab.2The transfer matrix of landscape types from 2oo5 to 2015   
表3脆弱度与驱动力相关系数 Tab.3Correlation coefficients between ecological vulnerability level and driving factors   

<html><body><table><tr><td>LVI</td><td>坡度</td><td>坡向</td><td>DEM</td><td>利用度</td><td>温度</td><td>降水</td><td>人口</td><td>GDP</td><td>城市</td><td>水系</td><td>道路</td></tr><tr><td>LVI(1995年)</td><td>0.158 *</td><td>0.021 *</td><td>0.413 *</td><td>-0.621 *</td><td>-0.340 *</td><td>0.389 *</td><td>-0.330 *</td><td>-0.237 *</td><td>0.166 *</td><td>0.014 *</td><td>0.097 *</td></tr><tr><td>LVI(2005年)</td><td>0.161 *</td><td>0.022 *</td><td>0.416 *</td><td>-0.622 *</td><td>-0.323 *</td><td>0.342 *</td><td>-0.427 *</td><td>-0.221 *</td><td>0.178 *</td><td>0.012 *</td><td>0.098 *</td></tr><tr><td>LVI(2015年)</td><td>0.159 *</td><td>0.021 *</td><td>0.418 *</td><td>-0.627 *</td><td>-0.351 *</td><td>0.298 *</td><td>-0.278 *</td><td>-0.282 *</td><td>0.187 *</td><td>0.013 *</td><td>0.102 *</td></tr></table></body></html>

注： $L V I$ 表示景观脆弱度指数； $*$ 表示在 $P < 0 . 0 1$ 水平(双侧)上显著相关。

![](images/3cddcd81f71cab6dc855d4c0333d8fba8060afdd0e18e4cb75db9879657503f7.jpg)  
图4流域气候变化趋势分布

![](images/bac47fa1b699a29abbd1324fa1f7fc582e5877d8b2d823926712c9bd981e13f7.jpg)  
Fig.4Climate change in the study area   
图51995—2015 年吉林省松花江流域景观生态脆弱度分布

Fig.5DistributionofecologicalvulnerabilitylevelofthelandscapesintheSonghuaRiverBasininJilinin1995,2O05andC

![](images/244dbd8b98ef0b1015f0eeadb71e00174ddac0c2ce90d08094fef3bb66f45681.jpg)  
图61995—2015年吉林省松花江流域土地利用度分布  
Fig.6Distribution of land use level in the Songhua River Basin in Jilin in 1995,2Oo5 and 2015

从空间分布的角度来看，松花江流域西北部脆弱度较低，中部主要为中度脆弱，高脆弱地区主要分布于西北边缘地区和东部地区。城乡用地和耕地与其他类型相比较为有序，所以脆弱度较低；中部和东部以林地为主，脆弱度适中；东部地区林地和草地、耕地交错分布，整体比较破碎，所以呈现出了高脆弱度；西北和中部地区存在部分难以利用的盐碱地和沼泽，呈现出局部高脆弱度。结合图5和图6可以看出空间分布的相关性。同时，结合图1也体现出脆弱度的分布与流域地形有一定的一致性。

从表4可以看出，1995—2015年研究区的脆弱度整体来说相对比较稳定，但是极低脆弱度和极高脆弱度的比例都逐年增加，中等和较低脆弱度比例下降，呈现出两极分化的趋势。

# 表4脆弱分区各年所占比例及其变化情况

Tab.4Proportions and change of the subareas with   

<html><body><table><tr><td colspan="5">different ecological vulnerabilitylevels</td></tr><tr><td>年份</td><td>低脆弱区</td><td>较低 脆弱区</td><td>中度 脆弱区</td><td>较高 高脆弱区 脆弱区</td></tr><tr><td>1995</td><td>1.03</td><td>34.91</td><td>55.03</td><td>8.71 0.33</td></tr><tr><td>2005</td><td>1.06</td><td>34.85</td><td>54.87</td><td>8.89 0.33</td></tr><tr><td>2015</td><td>1. 15</td><td>34.78</td><td>54.63</td><td>9.10 0.34</td></tr></table></body></html>

表5随机森林效果评价  
Tab.5Evaluation of the effects of random forest models   

<html><body><table><tr><td>年份</td><td>MSE</td><td>RMSE</td><td>R²</td><td>准确率</td></tr><tr><td>1995</td><td>0.085</td><td>0.292</td><td>0. 793</td><td>79.28</td></tr><tr><td>2005</td><td>0.088</td><td>0.297</td><td>0.788</td><td>78.83</td></tr><tr><td>2015</td><td>0.089</td><td>0.298</td><td>0.787</td><td>78. 74</td></tr></table></body></html>

注：MSE表示均方差，RMSE表示标准差， $R ^ { 2 }$ 表示决定系数。

# 3.4模型评价及驱动力分析

3期景观脆弱度分布与土地利用综合指数相关系数绝对值均大于0.6,且与人口和GDP也存在相对较强关系，表明景观脆弱度受人为活动影响明显，同时气候因素及其与河流远近对脆弱度的分布有一定的影响，与城市、道路及坡度坡向相关性较低（表3）。单纯的相关不能代表因果，为了更好地揭示驱动机制,对因子进行随机森林建模,表5中MSE及RMSE均较低, $R ^ { 2 }$ 及准确率相对较高,模拟效果较为理想，能够达到进一步研究的要求。从图7可以看出3期驱动因子相对重要性的变化,土地利用及DEM 的重要性与相关分析中一致,均占有很大比例，气候因素及GDP和人口都占有一定比例，且在不同时期起到的作用略有差别。河流也有一定的作用，且在各个时期相对稳定，与城市及道路的距离，坡度、坡向这4个因子在3段时期相对作用均较小，而且驱动力随着时间变化整体作用相对较稳定，但GDP和人口的作用相对气候因素有上提趋势。综上说明，以土地利用程度为主导因素，结合人口和GDP可以很好地作为人为因素来分析，将这些驱动力的作用及分布结合脆弱度分布状况来看，流域景观在人为干预的作用下,随着土地利用程度的增加,建设用地向四周扩展，连接成片，增加景观连通性，各类景观分布也更加均匀，结构更加有序，斑块边界及形状也更加规则，降低了整个流域的破碎度，提高了景观稳定性及抗干扰能力，景观资源会在土地利用程度高的地区得到更加有效的使用和整理，因此这些区域脆弱度较低。从脆弱度变化可以看出，流域整体脆弱度变化不大，下降区域主要分布于流域土地利用程度较为发达地区，该区域土地利用程度呈微弱增加趋势，城镇化进程明显，气候条件较为稳定，景观利用愈发合理;上升区主要分布于流域东部林草地，此区域人口及经济发展水平均较低，由于人为管理强度较小，在遭受干旱迹象干扰和人为破坏情况下，土地利用程度进一步降低,因此脆弱度上升，导致了流域景观脆弱度又呈现出略微两极化的现象。

![](images/93454f34358c3d3afb2ffc832eb9b7e862bca8deef70260d8a0daf1725c62a6b.jpg)  
图71995—2015年流域景观脆弱度驱动力相对重要性  
Fig.7Relativeimportanceof driving factorsonlandscapevulnerabilitylevel inthedrainage basin in1995,2Oo5and2015

# 4结论与讨论

（1）吉林省松花江流域景观类型主要以耕地和林地为主，整体来说景观分布比较稳定，但随着城市化的推进，各时间段内不同景观类型之间存在复杂的交汇，城市化持续上升，耕地和林地迅速减少，且流域东部林地破碎愈发严重，中游水域也呈现逐年减少的趋势，暴露出荒漠化及水土流失问题。

(2）低脆弱地区主要位于流域西北和中部发达城市，这些地区人为活动较频繁，土地使用更加有序，流域中部由于升温和略微的干旱，水土有所流失，脆弱度略微增加，东部林地遭到破坏，斑块破损严重,高脆弱度部分逐渐增加。西北部分地区的未利用土地长期难以利用，一直处于高脆弱状态。整个流域脆弱度分布随着时间变化有两极分化趋势，西北地区低脆弱度稳定性持续升高，东部林地脆弱度愈发升高。

（3）松花江流域脆弱度分布与变化受人类活动（土地利用、人口及GDP)影响显著，其中土地利用程度是主导因素。整体来讲，土地利用程度越高，斑块破碎度越低，连通性越强，对土地利用程度低的地区来说景观资源利用越合理，抗干扰能力越强，系统越稳定；脆弱度分布与地形有一定的相关性；流域不同时间段气候变化趋势有所差异，整体来看，脆弱度变化与气候变化有一定相关性，如局部地区的干旱干扰，导致景观类型改变及斑块破碎，因此脆弱度也有所升高;脆弱度与距河流距离有一定关系，其作用在不同时间段相对稳定；与城市及道路距离、坡度及坡向等关系不大。

（4）对于流域景观脆弱度的改善应考虑：适当开发西北高脆弱的未利用地，增加其利用;保护中游的水域，加大生态项目投入，加修水库，保护其枢纽功能;保护东部的林草地，开展植树造林项目，增加其景观连通性，减少破碎化。

本文以吉林省松花江流域为研究区，选取相关景观指数构建景观脆弱度，结合人为、地形及气象等数据，通过随机森林等方法分析了景观格局和脆弱度时空分布及驱动机制，外界驱动力的作用使景观结构随着土地利用模式的变化而变化，进而影响流域的生态服务价值和景观脆弱度，即使在人为干扰最小的情况下，景观功能也可能因气候和天气条件的变化而发生改变。景观功能的变化影响着生态系统内的能量流动和养分循环，生态脆弱度也随之发生变化。根据上述分析和实地调查结果,笔者认为，在过去的20a中，研究区的景观格局脆弱度受到了自然和人为因素的双重影响，其中人为因素是景观脆弱度较强的驱动力，且作用有上升趋势，表明保护景观生态，人类的干预并不是一个绝对消极的因素[26],科学合理的人类保护措施可以使景观格局更加有序,斑块形状更加规则[27],资源使用更加合理,景观分布更加均匀，更有利于景观生态系统的健康发展。因此，有必要在自然继承的基础上，辅以适当的人工干预，提高对景观格局变化和脆弱度的适应性。

受研究者经验和知识水平等因素限制，权重的赋值更多的是反映景观类型相对易损程度，如何采用更好的表达方法有待完善。还应进一步加强景观指数的生态学意义解释，驱动力对景观脆弱度的影响也具有阶段性和区域性特征，建立更完善的基于生态过程机理的景观脆弱度及更完整时间序列的驱动力研究是今后努力的方向。

# 参考文献（References）:

[1]陈利顶,李秀珍,傅伯杰,等.中国景观生态学发展历程与未来 研究重点[J].生态学报,2014,1（12）:3129-3141.[ChenLiding,Li Xiuzhen,Fu Bojie,et al.Development history and future research priorities of landscape ecology in China[J].Acta Ecological Sinica,2014,34(12):3 129 -3 141.]   
[2]Smiraglia D,Ceccarelli T,Bajocco S,et al. Unraveling landscape complexity: Land use/land cover changes and landscape pattern dynamics（1954-2008）incontrasting peri-urban and agro-forest regions of Northern Italy[J].Environmental Management,2015,56 (4):916-932.   
[3]陈颐,林毅伟,朱志鹏,等.基于RS 和GIS 的莆田市土地利用 景观格局变化分析[J].西北林学院学报,2017,32（1)：279- 286.[Chen Yi,Lin Yiwei,Zhu Zhipeng,et al. Changes of land use and landscape pattern in Putian based on RS and GIS[J]. Journal of Northwest Forestry University,2017,32(1):279-286.]   
[4]王根绪,郭晓寅,程国栋.黄河源区景观格局与生态功能的动 态变化[J].生态学报,2002,22（10）：1 587-1598.[Wang Genxu,Guo Xiaoyin,Cheng Guodong.Dynamic variations of landscape pattern and the landscape ecological functions in the source area of the Yellow River[J].Acta Ecological Sinica,2002,22 (10):1 587 -1598.]   
[5]Fu B,Liang D,Lu N. Landscape ecology: Coupling of pattern, process,and scale[J].Chinese Geographical Science,2011,21 (4):385-391.   
[6]巩杰,钱彩云,钱大文.1977—2013 年疏勒河中下游土地利用 变化与环境响应[J].干旱区研究,2017,34（4)：775-781. [Gong Jie,Qian Caiyun,Qian Dawen. Land use change and response of environment in the middle-lower reaches of the Shule River basin during the period of 1977-2013[J].Arid Zone Research,2017,34(4) :775-781.]   
[7」杜金龙,朱记伟,解建仓,等.近25a关中地区土地利用及其景 观格局变化[J].干旱区研究,2018,5（1）：217-226.［DuJinlong,Zhu Jiwei,Xie Jiancang,et al. Changes of land use and landscape pattern in the Guanzhong Area in recent 25 years[J].Arid Zone Research,2018,5(1) :217 - 226.] [8]刘亚文,阿不都沙拉木·加拉力丁,阿拉努尔·艾尼娃尔,等.   
1989—2016年吐鲁番高昌区绿洲时空格局变化及其驱动因素 [J].干旱区研究,2018,35(4）:945-953.[Liu Yawen,Abdushalam Jalaliding,Alanuer Aniwaer,et al. Spatiotemporal change of the oasis in Gaochang,Turpan and its driving factors during the period of 1989-2016[J]. Arid Zone Research,2018,35(4） :945-   
953.] [9]喻锋,李晓兵,王宏,等.皇甫川流域土地利用变化与生态安全 评价[J].地理学报,2006,61(6）:87-95.[Yu Feng,Li Xiaobing,Wang Hong,et al.Land use change and eco-security assessment of Huangfuchuan Watershed[J].Acta Geographica Sinica,   
2006,61(6) :87 -95.] [10]杜军,杨青华.基于土地利用变化和空间统计学的区域生态风 险分析—以武汉市为例[J].国土资源遥感，2010,22（2）：   
102 -106.[Du Jun,Yang Qinghua.An analysis of regional ecolog ical risk based on land use change and spatial statistics:A case study in Wuhan,Hubei Province[J].Remote Sensing for Land & Resources,2010,22(2）:102-106.] [11]Mo W,Wang Y,Zhang Y,et al. Impacts of road network expansion on landscape ecological risk in a megacity,China:A case study of Beijing[J].Science of the TotalEnvironment,2017,574:1000   
1 011. [12］孙才志,闫晓露,钟敬秋.下辽河平原景观格局脆弱度及空间 关联格局[J].生态学报,2014,34（2）:247-257.[Sun Caizhi, Yan Xiaolu,Zhong Jingqiu.Evaluation of the landscape patterns vulnerability and analysis of spatial correlation patterns in the lower reaches of Liaohe River Plain[J].Acta Ecologica Sinica,2014,34 (2):247 -257.) [13］张月,张飞,王娟,等.干旱区艾比湖流域典型区域景观格局脆 弱度时空格局变化研究[J].灾害学,2016,31（3）：222-229. [Zhang Yue,Zhang Fei,Wang Juan,et al.Evaluation of the landscape patterns vulnerability and analysis of spatial-temporal patterns in the typical region of the Ebinur Lake[J].Journal of Catastrophology,2016,31（3）:222-229.] [14］梁二敏,张军民,杨卫红.新疆玛纳斯河流域绿洲景观生态脆 弱度时空分异[J].干旱区研究,2017,34（4）：950-957.[Liang Ermin,Zhang Junmin,Yang Weihong. Spatiotemporal variation of landscape ecological vulnerability in oasis in the Manas River Basin,Xinjiang[J].Arid Zone Research,2017,34（4）: 950 -   
957.] [15]Turmer M G,Romme W H,Gardner R H,et al.A revised concept of landscape equilibrium:Disturbance and stability on scaled landscapes[J].Landscape Ecology，1993,8(3）:213 -227. [16］徐燕,孙小银,张大智，等.1980—2015 年南四湖流域景观格 局及其脆弱度[J].应用生态学报,2018,29（2）：635-642. [ Xu Yan,Sun Xiaoyin,Zhang Dazhi,et al. Landscape pattern and its vulnerability of Nansihu Lake basin during 198O-2015[J]. Chinese Jourmal of Appied Ecology,2018,29(2）:635-642.] [17]郭维东,王丽,高宇,等.辽河中下游水文生态完整性模糊综合 评价[J].长江科学院院报,2013,30（5）：13－16.[Guo Weidong,Wang Li,Gao Yu,et al. Fuzzy comprehensive assessment of hydroecological integrity for middleand lower reaches of Liaohe River[J]. Journal of Yangtze River Scientific Research Institute,

2013,30(5):13 -16.] [18］汪雪格,胡俊,吕军,等.松花江流域1956—2014 年径流量变 化特征分析[J].中国水土保持,2017（10）:61-65.[Wang Xuege,Hu Jun,Lu Jun,et al.Variation characteristics of annual run off in the Songhua River Basin from1956 to 2014[J].Soil and Water Conservation in China,2017(10）:61-65.] [19]欧阳志云，王效科.中国生态环境敏感性及其区域差异规律研 究[J].生态学报,2000,20（1）:9-12.[Ouyang Zhiyun,Wang Xiaoke.China's eco-environmental sensitivity and its spatial heterogeneity[J].ActaEcologica Sinica,2000,20(1）:9-12.] [20］游巍斌,何东进,巫丽芸,等.武夷山风景名胜区景观生态安全 度时空分异规律[J].生态学报，2011,31（21):6317-6 327. [YouWeibin,He Dongjin,Wu Liyun,et al. Temporal-spatial differentiation and its change in the landscape ecological security of Wuyishan Scenery District[J].Acta Ecologica Sinica,2011,31 (21):6 317 -6 327.] [21]李克让，曹明奎,於刑,等.中国自然生态系统对气候变化的脆 弱性评估[J].地理研究,2005，24(5）:653-663.[Li Kerang, Cao Mingkui,Yu Li,etal.Assessmentof vulnerability of natural ecosystems in China under the changing climate[J].Geographical Research,2005,24(5）:653-663.] [22]Soler L D S,Verburg P H.Combining remote sensing and household level data for regional scale analysis of land cover change in the Brazilian Amazon[J].Regional Environmental Change,2010,   
10(4):371 -386.   
[23]刘吉平，董春月，盛连喜，等.1955—2010 年小三江平原沼泽湿 地景观格局变化及其对人为干扰的响应[J].地理科学，2016， 36(6）:879 -887.[Liu Jiping,Dong Chunyue,Sheng Lianxi,et al.Landscape pattern change of the marsh and its response to human disturbance in the Small Sanjiang Plain,1955-2010[J]. Scientia Geographica Sinica,2016,36(6）:879-887.]   
[24]梁佳欣,李新举.南四湖湿地景观格局脆弱度的时空分异特征 [J].应用生态学报,2018,29（2）:626-634.[LiangJiaxin，Li Xinju.Characteristics of temporal-spatial differentiation in landscape pattern vulnerability in Nansihu Lake Wetland,China[J]. Chinese Journal of Applied Ecology,2018,29(2）:626-634.]   
[25]庄大方，刘纪远.中国土地利用程度的区域分异模型研究[J]. 自然资源学报,1997,12（2）：105-111.［ZhuangDafang,Liu Jiyuan.Study on the model of regional differentiation of land use degree in China[J].Acta Ecologica Sinica,1997,12（2）:105- 111.]   
[26]Zang Z,Zou X,Zuo P,et al.Impact of landscape patterns on ecological vulnerability and ecosystem service values:An empirical analysis of Yancheng Nature Reserve in China[J].Ecological Indicators,2017,72:142-152.   
[27］李继红，胡庆磊.基于生态干扰度的宝清县湿地景观动态分析 [J].西北林学院学报，2013，28（5）：154-159,194.［LiJihong,Hu Qinglei.Dynamic appraisals of landscape pattern in Baoqing County wetland based on eco-disturbance degree[J]. Journal of Northwest Forestry University,2013,28(5）:154-159,194.]

# Change of Landscape Pattern Vulnerability in the Songhua River Basin in Jilin Province and Its Driving Forces

SUN Hong-chao， ZHANG Zheng-xiang (School ofGeographical Science,Northeast Normal University,Changchun 130024,Jilin,China)

Abstract：The Songhua River Basin in Jilin Province was taken as the study area,and the three Landsat TM/ETM images in 1995,2005 and 2O15 were used as thedata sources.The landscape patern,spatiotemporal distribution of ecological vulnerability and its driving forces were studied.The main conclusions were as follws : $\textcircled{1}$ Climate change inthe drainage basin was diferent from diferent periods.Thedominant landscapes werecultivated land and woodland,theareasofurbanandrurallandand grassland weresteadilyenlarged,buttheareasof woodland,cultivated land and waters were in a reduction trend. $\textcircled{2}$ The areas with low and moderate ecological vulnerability were dominant inthe middleand lower reaches of the drainage basin,and theareas with high ecological vulnerability were mainly distributed inthesoutheastof the basin,northwest desertified land inthe lowerreaches,woodlandandgrassland. $\textcircled{3}$ Ecological vulnerability of the drainage basin was relatively stable and in slight increase and polarization trends.The distributionofecological vulnerabilitywas closely relatedtothe humanactivities,and it was relatedto thetopographical conditions to some extent.The efect of climate change was not significant,which,however,could still reflect some ecological problems.

Key words:landscape pattrn；vulnerability；spatiotemporal distribution；driving factor；land use；random forest models；Songhua River Basin； Jilin