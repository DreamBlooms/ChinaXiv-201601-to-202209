# 基于改进遥感生态指数模型的锡林郭勒草原生态环境评价

宋美杰}²，罗艳云¹，段利民1（1．内蒙古农业大学水利与土木建筑工程学院,内蒙古 呼和浩特010018;2．河海大学地球科学与工程学院,江苏 南京211100)

摘要：气候变化和人类活动的不断加剧，引发了生态环境质量问题，快速准确的评价区域生态环境的历史和现状,对实现人与自然的可持续协调发展具有重要意义。本文基于遥感技术分别反演出绿度因子、湿度因子、干度因子和热度因子,使用主成分分析法构建了改进遥感生态指数（MRSEI)。利用相关性分析,分析MRSEI的代表性，建立基于MRSEI的锡林郭勒草原生态环境评价模型,对锡林郭勒草原近26a的生态环境进行了总体评价。结果表明：MRSEI可集中4种生态因子信息,能够准确的对生态环境进行评价;锡林郭勒草原从1991—2017年生态环境质量呈现出先好转后恶化的趋势;1991年研究区上游的生态环境质量优于下游,生态环境质量东部优于西部；2004年,研究区整体生态环境质量空间差异较1991年变化较大，上游大多数地区生态环境质量提升,但下游明显降低；至2017年,整个研究区生态环境质量全面降低,仅在锡林河上游两岸与流域的南部和东南部保持良和优良。

关键词：改进遥感生态指数(MRSEI)；主成分分析；生态因子；环境评价；锡林郭勒

随着气候变化和人类活动的不断增强，生态环境问题严重威胁到区域生态安全和经济社会的可持续发展[1]。准确地评价区域生态环境历史和现状,有利于决策者认识区域生态环境状况，进而采取积极的措施,以实现人与自然的可持续协调发展[2]。以往生态环境状况多以单一生态因子为变量来进行评价，如植被指数[3-4]、地表温度[5]、干旱指数[6]等。如何进行区域尺度的多因素综合的生态环境动态监测，是目前生态环境定量评价中需要解决的问题。2013年，徐涵秋[提出，利用完全基于遥感技术获取生态指标的方法对生态环境进行监测与评价。该方法降低了生态指标提取的难度和在实际应用中的主观性，达到对区域生态环境状况进行定量评价、可视化评价结果的目的;但以往学者[7-9]多是以主成分分析中的第一主成分或全部主成分构建生态指数，考虑到仅用第一主成分，造成信息利用不充分，而第四主成分绝大部分为噪声信息，因此，需对遥感生态指数模型加以改进。改进后的生态指数模型在剔除噪声信息的同时，充分综合了影像有效信息，更加具有代表性。锡林郭勒草原区植被低矮、稀疏，群落生产力低，气候干旱，自然环境复杂，成为气候变化的异常敏感区域[10],已被联合国教科文组织认定的国际生物圈保护区(1]。众多学者也从降水、气候变化、草场退化、草场利用现状等方面进行了相关研究。本研究基于遥感技术反演绿度因子、湿度因子、干度因子和热度因子4个生态因子，采用主成分分析法构建改进遥感生态环境指数（MRSEI），利用相关性分析分析MRSEI的代表性，建立基于MR-SEI的锡林郭勒草原生态环境评价模型，对锡林郭勒草原近26a的生态环境进行总体评价，为草原生态环境的快速动态定量评价提供新的思路，为准确制定生态环境治理方案，保护北部边疆生态环境脆弱区提供科学依据。

# 1研究区概况与数据预处理

# 1.1 研究区概况

本研究以锡林河流域为研究区，该区位于内蒙古自治区锡林郭勒盟境内，属欧亚大陆大草原地带。面积约 $1 0 \ 0 0 0 \ \mathrm { k m } ^ { 2 }$ ,地理坐标为 $4 3 ^ { \circ } 2 4 ^ { \prime } \sim 4 4 ^ { \circ } 3 9 ^ { \prime } \mathrm { N }$ $1 1 5 ^ { \circ } 2 5 ^ { \prime } \sim 1 1 7 ^ { \circ } 1 5 ^ { \prime } \mathrm { E }$ 。植被从上游的草甸草原、羊草草原向下游依次过渡为大针茅草原和克氏针茅草原。研究区海拔 $9 0 0 \sim 1 ~ 6 5 0 ~ \mathrm { ~ m ~ }$ ,地势由东南向西北逐渐降低，周边低丘环绕，地势比较平坦，地面坡降约 $1 \%$ 。按地貌成因类型和特征划分，该区可分为构造剥蚀型和堆积地型(12]。在中国气候区划上,锡林河流域属温带半干旱气候，气温的年较差和日较差都较大，冬季严寒漫长，夏季温和短促，具明显的大陆性气候特征[13]。降水主要集中在7、8、9月,降水量直接影响植被的生长状况(14)

# 1.2数据源与数据预处理

锡林河流域属于典型草原区，植被的生长易受降水影响，选择降水量正常的1991年、2004 年和2017 年为代表年份(15-16]。遥感数据下载自地理空间数据云，分别为1991年8月11日和2004年8月14日的Landsat5－TM影像及2017年7月17日的Landsat8-OLI和TIRS影像，所获取的遥感影像云量少，质量较高。影像预处理采用ENVI5.3平台，首先，对可见光波段与热红外波段进行辐射定标，将原始像元亮度值转化为辐射亮度值，然后利用FLAASH大气校正工具对其进行校正，得到真实的地表反射率。由于研究区需要2景影像才能完全覆盖，因此，大气校正后对影像的多光谱波段与热红外波段分别进行镶嵌和裁剪。最后，以2004年影像为基准影像，分别对1991年与2017年影像进行配准，RMS(均方根误差)控制在0.5个像元以内。

# 2改进遥感生态指数(MRSEI)的构建

# 2.1 生态因子的计算

生态系统巨大而复杂，各组成成分既相互独立又相互关联。单一的生态因子无法准确的对生态环境进行客观的评价与全面的反映。因此，从多个生态因子的综合作用进行区域生态环境评价尤为重要。本研究选取了能够表征生态环境状况的绿度因子、湿度因子、干度因子、热度因子4个生态因子作为生态环境评价指标。

植被是指示区域生态环境质量最敏感的因子，在植被遥感监测中，归一化植被指数(NDVI)的应用最为广泛[17]。NDVI经比值处理,增强了对植被的响应能力，是植物生长状况及植被覆盖的最佳指示因子，因此，以NDVI代表绿度因子。湿度因子(WET)可以较好地反映地表植被、水体和土壤的湿度状况,与土壤退化等生态环境变化密切相关[2]基于TM影像WET的计算公式参见文献[18]，基于OLI影像的WET计算公式参见文献[19]。干度因子（NDSI）由裸土指数（SI）和建筑指数（IBI）合成[17,20-21]。热度因子（LST）用地表温度来表示[21-24] 。

构建出的生态因子由于量纲不同，取值范围差异较大，因此，根据下式对各因子进行标准化，将因子值统一到[0，1]之间。

$$
N I = \big ( I - I _ { \mathrm { m i n } } \big ) / \big ( I _ { \mathrm { m a x } } - I _ { \mathrm { m i n } } \big )
$$

式中： $N I$ 为标准化后的指标值； $I$ 为各生态因子对应的指标值; $I _ { \mathrm { m a x } }$ 为该指标的最大值； $I _ { \mathrm { m i n } }$ 为该指标的最小值。

# 2.2 主成分分析

主成分分析是一种除去波段之间多余信息，将多波段的图像信息压缩到比原波段更有效的少数几个相互独立波段的转换方法。想要以单一的指数反映生态环境质量，需要给构建遥感生态指数的每个因子赋予不同的权值，主观经验赋权值的方法，容易造成结果的偏差。利用主成分分析方法，根据不同因子对主成分的贡献率，可自动、客观地确定权值。

# 2.3 MRSEI的构建

由表1可见，主成分分析的前3个主成分包含了影像较为完整的信息，因此以 $P C _ { 1 } \lnot P C _ { 2 }$ 和 $P C _ { 3 }$ 的贡献率为权重，构建MRSEI。

$$
\mathrm { M R S E I } = \sum _ { i = 1 } ^ { 3 } \omega _ { i } P C _ { i }
$$

式中： $\omega _ { i }$ 为第 $i$ 主成分的贡献率； $P C _ { i }$ 为第 $i$ 主成分。

根据标准化公式，将MRESI指数标准化到[0，1]范围内，MRSEI越接近于1代表生态环境越好。为更好的呈现MRSEI所体现的生态效应，将数值由小到大，以0.2为间隔，将生态环境分为差、较差、中等、良、优等5个生态等级，并统计1991年、2004年和2017年各等级相对应的面积。

# 2.4MRSEI代表性验证及模型构建

MRSEI能否代表各生态因子，可以通过MRSEI和各生态因子之间的相关性来进行分析。从各生态因子与MRSEI的相关系数以及各生态因子之间的相关系数的计算结果(表2)可以看出，各年份内，各生态因子之间的相关系数绝对值范围为0.56\~0.87，而MRSEI与各生态因子均有较高的相关性，相关系数的绝对值均在0.80以上。MRSEI与各生态因子的平均相关度在1991年、2004年和2017年分别为0.92、0.93和0.86。由此可以得出，MRSEI除了能集中各因子的信息外，相比单一生态因子更具有生态环境质量代表性。

Tab.1 Results of principal component analysis   
表2MRSEI与各指标的相关性  

<html><body><table><tr><td>年份</td><td>生态因子</td><td>PC1</td><td>PC2</td><td>PC3</td><td>PC4</td></tr><tr><td>1991</td><td>NDVI</td><td>0.52</td><td>0.54</td><td>0.60</td><td>0.27</td></tr><tr><td rowspan="12">2004</td><td>WET</td><td>0.55</td><td>0.16</td><td>-0.76</td><td>0.31</td></tr><tr><td>NDSI</td><td>-0.50</td><td>0.04</td><td>0.00</td><td>0.87</td></tr><tr><td>LST</td><td>-0.43</td><td>0.82</td><td>-0.25</td><td>-0.28</td></tr><tr><td>特征值</td><td>0.12</td><td>0.01</td><td>0.01</td><td>0.00</td></tr><tr><td>贡献率/%</td><td>86.00</td><td>7.00</td><td>7.00</td><td>0.00</td></tr><tr><td>NDVI</td><td>0.61</td><td>0.61</td><td>0.47</td><td>0.17</td></tr><tr><td>WET</td><td>0.54</td><td>-0.58</td><td>-0.16</td><td>0.59</td></tr><tr><td rowspan="11">2017</td><td>NDSI</td><td></td><td></td><td></td><td></td></tr><tr><td>LST</td><td>-0.45</td><td>-0.26</td><td>0.77</td><td>0.37</td></tr><tr><td>特征值</td><td>-0.37</td><td>0.47</td><td>-0.39</td><td>0.70</td></tr><tr><td>贡献率/%</td><td>0.14</td><td>0.01</td><td>0.01</td><td>0.00</td></tr><tr><td>NDVI</td><td>88.00</td><td>6.00</td><td>6.00</td><td>0.00</td></tr><tr><td>WET</td><td>0.50</td><td>0.86</td><td>-0.04</td><td>-0.08</td></tr><tr><td>NDSI</td><td>0.43</td><td>-0.28</td><td>0.55</td><td>-0.66</td></tr><tr><td>LST</td><td>-0.64</td><td>0.30</td><td>-0.17</td><td>-0.69</td></tr><tr><td></td><td>-0.40</td><td>0.29</td><td>0.82</td><td>0.29</td></tr><tr><td>特征值</td><td>0.08</td><td>0.01</td><td>0.01</td><td>0.00</td></tr><tr><td>贡献率/%</td><td>80.00</td><td>10.00</td><td>10.00</td><td>0.00</td></tr></table></body></html>

表1主成分分析结果  
Tab.2 Correlation between MRSEI and indicators   

<html><body><table><tr><td>年份</td><td>指标</td><td>NDVI</td><td>WET</td><td>NDSI</td><td>LST</td><td>MRSEI</td></tr><tr><td rowspan="5">1991</td><td>NDVI</td><td>1.00</td><td>0.82</td><td>-0.85</td><td>-0.69</td><td>0.93</td></tr><tr><td>WET</td><td>0.82</td><td>1.00</td><td>-0.87</td><td>-0.74</td><td>0.94</td></tr><tr><td>NDSI</td><td>-0.85</td><td>-0.87</td><td>1.00</td><td>0.80</td><td>-0.95</td></tr><tr><td>LST</td><td>-0.69</td><td>-0.74</td><td>0.80</td><td>1.00</td><td>-0.85</td></tr><tr><td>平均相关度</td><td>0.79</td><td>0.81</td><td>0.84</td><td>0.75</td><td>0.92</td></tr><tr><td rowspan="6">2004</td><td>NDVI</td><td>1.00</td><td>0.85</td><td>-0.87</td><td>-0.80</td><td>0.96</td></tr><tr><td>WET</td><td>0.85</td><td>1.00</td><td>-0.84</td><td>-0.85</td><td>0.94</td></tr><tr><td>NDSI</td><td>-0.87</td><td>-0.84</td><td>1.00</td><td>0.77</td><td>-0.93</td></tr><tr><td>LST</td><td>-0.80</td><td>-0.85</td><td>0.77</td><td>1.00</td><td>-0.89</td></tr><tr><td>平均相关度</td><td>0.84</td><td>0.85</td><td>0.83</td><td>0.81</td><td>0.93</td></tr><tr><td>NDVI</td><td>1.00</td><td>0.60</td><td>-0.69</td><td>-0.56</td><td>0.83</td></tr><tr><td rowspan="5"></td><td>WET</td><td>0.60</td><td>1.00</td><td>-0.82</td><td>-0.59</td><td>0.86</td></tr><tr><td>NDSI</td><td>-0.69</td><td>-0.82</td><td>1.00</td><td>0.74</td><td>-0.95</td></tr><tr><td>LST</td><td>-0.56</td><td>-0.59</td><td>0.74</td><td>1.00</td><td>-0.81</td></tr><tr><td></td><td></td><td></td><td>0.75</td><td>0.63</td><td>0.86</td></tr><tr><td>平均相关度</td><td>0.62</td><td>0.67</td><td></td><td></td><td></td></tr></table></body></html>

注：平均相关度是以某一指标与其他指标相关系数的绝对值来计算。

对各年份的4个生态因子和MRESI专题反演图进行贯穿全影像采样方法，随机采集样点20000个。以生态指数MRSEI为因变量，生态因子NDVI、WET、NDSI、LST为自变量,采用逐步回归分析[25],建立的锡林郭勒草原生态指数模型如下：

$\mathrm { M R E S I _ { 1 9 9 1 } } = 0 . \ 3 0 2 \ 2 \mathrm { N D V I } + 0 . \ 2 6 1 \ 8 \mathrm { W E T } - 0 . \ 2 5 0 \ 0$   
$\mathrm { N D S I } - 0 . 1 8 6 ~ 0 \mathrm { L S T } + 0 . 4 3 6 ~ 0$   
（204号 $\mathrm { M R E S I } _ { 2 0 0 4 } = 0 . \ 3 4 3 \ 9 \mathrm { N D V I } + 0 . \ 2 5 8 \ 0 \mathrm { W E T } - 0 . \ 2 2$ 248  
$\mathrm { N D S I } - 0 . 1 8 3 \ 6 \mathrm { L S T } + 0 . 3 9 8 \ 1$   
$\mathrm { M R E S I _ { 2 0 1 7 } } = 0 . \ 2 6 0 \ \mathrm { 8 N D V I } + 0 . \ 2 2 4 \ \mathrm { 8 W E T } - 0 . \ 3 3 3 \ 3$   
$\mathrm { N D S I } - 0 . 2 1 1 1 \mathrm { L S T } + 0 . 5 1 4 3$

从1991年、2004 年和2017年的回归模型可分析出，在逐步回归过程中4个生态因子均未被剔除，说明NDVI、WET、NDSI和LST都是锡林郭勒草原生态的关键指标；由各因子回归系数的正负可知，ND-VI和WET的系数为正值，说明对生态起积极作用，NDSI和LST为负值，说明对生态起消极作用。

# 3结果与分析

# 3.1生态因子贡献状况分析

各生态因子与MRSEI的关系可采用三维特征空间进行展示分析。分别将各年份对生态环境起积极影响的NDVI、WET和对生态环境起消极影响的NDSI、LST与MRSEI的采样点投影到三维空间。从图1可以看出，MRSEI的高值区聚集在湿度高、植被覆盖条件较好的区域，而MRSEI的低值区聚集在地表裸露且温度较高的区域。

依据各因子的回归系数大小作为评判其对生态指数的贡献度，NDVI的回归系数在3个年份均大于0.26，反映NDVI对生态的贡献度较高;LST的回归系数为 $0 . \ 1 8 \sim 0 . 2 1$ ，说明LST对生态的贡献度较低。NDVI的相关系数绝对值，随时间的推移越来越小，说明绿度因子对生态质量的正向贡献度在降低；而NDSI的相关系数绝对值逐渐增加，尤其是2017年NDSI对生态质量的负向贡献度超过了ND-VI的正向贡献度，从2017年的遥感影像上也可看出，裸土面积较1991年和2004 年明显增加，印证了NDSI的负向影响在增大。4个生态因子中LST的贡献度最低，说明热度因子对生态环境质量的影响不及其他3个因子强。

# 3.2 生态环境总体评价

1991年,锡林郭勒草原的MRSEI平均值为0.41;  
2004年，MRSEI平均值为0.44，较1991年上升了

![](images/1269a6ce070449ae5a01499836d3cc43664b83eb705ad6f04e5141ac650eff7d.jpg)  
图1MRSEI与生态因子的三维散点图  
Fig.1Three-dimensional scatter diagram of MRSEI and ecological factors

$7 . 3 2 \%$ ,可以看出1991—2004 年锡林郭勒草原生态环境有好转；2017年，MRSEI平均值为0.27，MRESI均值下降 $3 8 . 6 4 \%$ ,2004—2017年锡林郭勒草原生态环境明显恶化。总的来说，2004年锡林河流域的生态环境质量最好，从1991—2017年锡林郭勒草原生态环境质量呈现先好转后恶化的趋势。

从表3可以看出，1991年研究区超过 $5 0 \%$ 的地区生态环境质量处于差和较差水平；1991—2004年,研究区生态环境质量明显好转,2004年中等和良等级的区域分别占 $3 7 . 0 0 \%$ 和 $1 7 . 7 3 \%$ ，较1991年分别增加了 $8 . 0 8 \%$ 和 $6 . 5 1 \%$ ；但是，2004—2017年，研究区生态环境质量急剧恶化，2017年差和较差等级的区域分别占 $3 5 . 4 0 \%$ 和 $5 3 . 2 1 \%$ ，较2004年增加了 $2 0 . 9 3 \%$ 和 $2 5 . 0 0 \%$ 。

表3锡林郭勒草原不同时期生态等级面积及比例Tab.3The areas and proportions of the steppes withdifferent levels in Xilin Gol in different periods  

<html><body><table><tr><td>MRSEI</td><td>1991年</td><td>2004年</td><td>2017年</td></tr><tr><td>等级</td><td>面积/km² 比例/%</td><td>面积/km² 比例/%</td><td>面积/km² 比例/%</td></tr><tr><td>差</td><td>1 053.00 9.75</td><td>1 562.76 14.47</td><td>3 823.20 35.40</td></tr><tr><td>较差</td><td>5 070.60 46.95</td><td>3046.68 28.21</td><td>5 746.68 53.21</td></tr><tr><td>中等</td><td>3123.36 28.92</td><td>3 996.00 37.00</td><td>799.20 7.40</td></tr><tr><td>良</td><td>1 211.76 11.22</td><td>1 914.84 17.73</td><td>207.36</td></tr><tr><td>优</td><td>341.28 3.16</td><td>279.72 2.59</td><td>223.56 2.07</td></tr><tr><td>合计10800.00</td><td>100.00</td><td>10 800.00 100.00</td><td>10 800.00 100.00</td></tr></table></body></html>

![](images/c7c7c53bad8305207ae35829d15789d07bf094b1e61b0260a6e32768a3170fe7.jpg)  
宋美杰等：基于改进遥感生态指数模型的锡林郭勒草原生态环境评价  
图2 MRSEI等级空间分布  
Fig.2Spatial distribution of MRSEI levels

由图2可以看出，1991年研究区MRSEI等级从上游至下游逐渐降低，自东向西逐渐降低，该结果表明上游的生态环境质量优于下游,研究区生态环境质量东部优于西部，这样的空间分布特点与当地的气候条件和植被分布相呼应，降水自西向东增加，温度自东向西增加，植被分布上游优于下游;2004年，MRSEI等级依然保持自上游至下游逐渐降低，但研究区整体MRSEI等级空间差异较1991年变化较大，上游大多数地区MRSEI等级升高，但下游明显降低；至2017年，整个研究区MR-SEI等级全面降低为差和较差，仅在锡林河上游两岸和研究区的南部与东南部保持在良和优良等级。

# 4结论与讨论

锡林郭勒草原是我国北方地区的一道绿色屏障，对维持整个华北地区的生态环境安全起着极其重要的作用。本文得出的2004年的生态环境状况相较于1991年有所好转,该结论与马梅等[26]得出的2000—2005 年草场退化状况发生好转相吻合，同时也证明了MRSEI的正确性。通过MRSEI对该地区进行研究得出如下结论：

（1）本研究所选用的绿度因子、湿度因子、干度因子、热度因子4个生态因子对草原流域的生态环境评价具有代表性。基于遥感技术获取的生态因子构建生态指数，通过主成分分析来确定各个因子的权重，在剔除噪声信息的同时最大限度地保留单一因子的有效信息，使生态环境评价更快捷客观。MRSEI的高值区聚集在湿度高、植被覆盖条件较好的区域，而MRSEI的低值区聚集在地表裸露且温度较高的区域。

（2）锡林郭勒草原近26a的生态环境质量呈现先好转后恶化的趋势。1991—2004年，研究区生态环境质量明显好转，2004年中等和良等级的区域分别占 $3 7 . 0 0 \%$ 和 $1 7 . 7 3 \%$ ，但是，2004—2017年，研究区生态环境质量急剧恶化，2017年差和较差等级的区域分别占 $3 5 . 4 0 \%$ 和 $5 3 . 2 1 \%$ 。

（3）1991年研究区上游的生态环境质量优于下游，锡林河流域生态环境质量东部优于西部;2004年，研究区整体MRSEI等级空间差异较1991年变化较大，上游大多数地区MRSEI等级升高，但下游明显降低；至2017年，研究区MRSEI等级全面降低为差和较差，仅在锡林河上游两岸和研究区的南部与东南部保持在良和优良等级。

采用MRSEI模型对锡林郭勒草原进行生态环境评价，提高了人们对草原流域生态环境定量评价的认识，为预测未来生态环境的变化趋势奠定了基础，对于改善我国北部边疆生态脆弱区的生态环境具有深远的意义。

# 参考文献(References）:

[1]张静.准噶尔盆地表生生态环境演化及驱动力分析〔D].西 安：长安大学,2016.［ZhangJing.TheEvolutionofEcological En vironment and Driving Forces of the Junggar Basin[D].Xi'an: Chang'an University,2016.]

[2]宋慧敏，薛亮.基于遥感生态指数模型的渭南市生态环境质量动态监测与分析[J].应用生态学报，2016，27（12）：3913-3 919.[Song Huimin,Xue Liang.Dynamic monitoring and analysisof ecological environment in Weinan City,Northwest China basedon RSEI model[J]. Chinese Journal of Applied Ecology,2016,27（12):3 913 -3 919.]

[3]Yuan Fei,Bauer M E.Comparison of impervious surface area and normalized difference vegetation index as indicators of surface urban heat island effects in Landsat imagery[J]. Remote Sensing of Environment,2007,106(3）:375-386.   
[4]Wright C K,De Beurs K M,Henebry G M.Combined analysis of land cover change and NDVI trends in the Northern Eurasian grain belt[J].Frontiers of Earth Science,2012,6(2）:177 -187.   
[5]Imhoff ML,Zhang P,Wolfe R E,et al. Remote sensing of the urban heat island efect across biomes in the continental USA[J]. Remote Sensing of Environment,2010,114(3）:504 -513.   
[6]Sandholt I,Rasmussen K,Andersen J.A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J].Remote Sensing of Environment,2002, 79(2-3) :213 -224.   
[7]徐涵秋.城市遥感生态指数的创建及其应用[J].生态学报, 2013,33(24):7 853-7 862.[Xu Hanqiu.A remote sensing urban ecological index and its a pplication[J].Acta Ecologica Sinica,2013,33(24) :7 853-7 862.]   
[8]李粉玲,常庆瑞,申健,等.黄土高原沟壑区生态环境状况遥感 动态监测—以陕西省富县为例[J].应用生态学报,2015,26 (12）:3 811-3 817.[Li Fenling,Chang Qingrui,Shen Jian,et al.Dynamic monitoring of ecological environment in loess hilly and gully region of Loess Plateau based on remote sensing :A case study on Fuxian County in Shaanxi Province,Northwest China[J]. Chinese Journal of Applied Ecology,2015,26(12）:3 811-3 817.]   
[9］王士远,张学霞,朱彤,等.长白山自然保护区生态环境质量的 遥感评价[J].地理科学进展,2016,35（10）：1269－1 278. [Wang Shiyuan,Zhang Xuexia,Zhu Tong,et al.Assessment of ecological environment quality in the Changbai Mountain Nature Reserve based on remote sensing technology[J].Progress in Geography,2016,35(10) :1 269 -1 278.]   
[10］韩芳.气候变化对内蒙古荒漠草原生态系统的影响[D].呼和 浩特：内蒙古大学,2013.［Han Fang.Impact of Climate Change on Desert Steppe Ecosystem in Inner Mongolia[D].Hohhot: Inner Mongolia University,2013.]   
[11］李传新.基于遥感的锡林河流域草地退化及影响因素分析 [D].北京：中国地质大学,2016.［Li Chuanxin.Analysis of Grassland Degradation and Influencing Factors Based on Remote Sensing[D].Beijing:China University of Geosciences,2016.]   
[12］李玮.变化环境下锡林河流域地表水与地下水耦合模拟[D]. 呼和浩特：内蒙古农业大学,2018.[Li Wei.Integrated Simulation of Surface Water and Groundwater in Xilin River Basin in Changing Environments[D].Hohhot: Inner Mongolia Agricultural University,2018.]   
[13］柳艺博,居为民,朱高龙,等.蒙古不同类型草地叶面积指数遥 感估算[J].生态学报,2011,31（18）：5159-5170.［Liu Yibo, Ju Weimin,Zhu Gaolong,et al. Retrievalof leaf area index for different grassands in Inner Mongolia prairie using remote sensing data[J].Acta Ecologica Sinica,2011,31(18):5 159- 5170.]   
[14］洪立国.锡林河流域草原利用现状与保护对策研究[D].呼和 浩特：内蒙古大学,2009.[Hong Liguo.Study on Utilization Status and Protection Countermeasures of Grassland in Xilin River Basin[D].Hohhot:Inner Mongolia University,2009.]   
[15］贺俊杰.锡林浩特市 50 年降水量变化特征分析[J].中国农学 通报,2012,28（29）:271-278.[He Junjie.Precipitation variation characteristics of Xilinhot City for5O years[J].China Agricultural Science Bulletin,2012,28（29）:271-278.]   
[16］锡林浩特市人民政府.锡市概况［EB/OL].htp://www.xilinhaote.gov.cn/zjcymz/xsgk/,2018-10-22.[Xilinhot people's government.Overview of Xilnhot[EB/OL].http://www.xilinhaote. gov.cn/zjcymz/xsgk/,2018-10 - 22.]   
[17］武正丽.2000—2012 年祁连山植被覆盖变化及其对气候的响 应研究[D].兰州：西北师范大学,2014.[Wu Zhengli.The Research of the Vegetation Change and the Sensitivity between NDVI and Climatic Factors in Qilian Mountains from 20oO to 2012[D]. Lanzhou:Northwest Normal University,2014.]   
[18]Crist EP.A TM tasseled cap equivalent transformation for reflectance factor data[J].Remote Sensing of Environment,1985,17 (3) :301-306.   
[19]Baig MHA,ZhangL,Shuai T,et al.Derivationof ataselled cap transformation based on Landsat 8 at-satelite reflectance[J]. Remote Sensing Letters,2014,5(5） :423 -431.   
[20] Rikimaru A,Roy P S,Miyatake S. Tropical forest cover density mapping[J].Tropical Ecology,2002,43（1） :39 -47.   
[21］吴国训,阮宏华,李显风,等.基于 MODIS 反演的 2000—2011 年江西省植被叶面积指数时空变化特征[J].南京林业大学学 报（自然科学版）,2013,37（1）:11-17.[Wu Guoxun,Ruan Honghua,Li Xianfeng,etal. Spatial-temporal variationsof leaf area index（LAI）in Jiangxi Province during 200O－201l based on MODIS data[J].Journal of Nanjing Forestry University（Natural Science Edition）,2013,37(1） :11-17.]   
[22］邸苏闯,吴文勇,刘洪禄,等.城市绿量的遥感估算与热岛效应 的相关分析——以北京市五环区域为例[J].地球信息科学学 报,2012,14（4）:481-489.[Di Suchuang,Wu Wenyong,Liu Honglu,et al. The correlationship between urban greenness and heat island effect with RS technology:A case study within 5th ring road in Beijing[J].Journal of Geo-Information Science,2012,14 (4) :481 -489.]   
[23]Sobrino JA,Jiménez-Munoz JC,Paolini L.Land surface temperature retrieval from LANDSAT TM 5[J]. Remote Sensing of Environment,2004,90(4） :434 -440.   
[24]Yu Xiaolei,Guo Xulin,Wu Zhaocong.Land surface temperature retrieval from Landsat 8 TIRS: Comparison between radiative transfer equation-based method,split window algorithm and single channel

method[J].Remote Sensing,2014,6(10):9 829-9 852.

[25]张浩，杜培军，罗洁琼,等.基于遥感生态指数的南京市生态变 化分析[J].地理空间信息,2017,15(2）：58-62.[Zhang Hao, Du Peijun,Luo Jieqiong,et al.Ecological change analysis of NanJing City based on remote sensing ecological index[J].Geospatial Information,2017,15(2):58-62.]

[26］马梅,张圣微，魏宝成.锡林郭勒草原近30 年草地退化的变化特征及其驱动因素分析[J].中国草地学报，2017,39（4)：86-93.[Ma Mei,Zhang Shengwei,Wei Baocheng.Temporal and spa-tial pattern of grassland degradation and its determinants for recent30 years in Xilingol[J].Chinese Journal of Grassland,2017,39(4):86-93.]

# Evaluation of Ecological Environment in the Xilin Gol Steppe Based on Modified Remote Sensing Ecological Index Model

SONG Mei-jie $^ { 1 , 2 }$ ，LUO Yan-yun¹，DUAN Li-minl (1. College of Water Conservancyand Civil Enginering,Inner Mongolia Agricultural University,Hohhot 010018, Inner Mongolia,China; 2.Schoolof Earth Sciencesand Engineering,Hohai University,Nanjing21loo,Jiangsu,China)

Abstract：Climate change and human activities continue to intensify and cause some ecological and environment qualityproblems.It is important to the sustainableand coordinated development of human and nature to quickly and accurately evaluate the historical and current situationof regional ecological environment.In this paper,four indicators including greenness,wetness,dryness and heat were retrieved using the remote sensing RS techniques.Principal component analysis（PCA）was used to construct the modified remote sensing ecological index（MRSEI）,and the representativeness of MRSEI was analyzed by correlation analysis.Based on MRSEI,the ecological environment evaluation model was developed for the XilinGol Steppe,and theoverall evaluation of the ecological environment in the XilinGol Steppe in recent 26 years was conducted.The results showed that MRSEI could be used to collect the information of various ecological factors and evaluate the ecological environment accurately.From1991 to 2017,the ecological environment qualityinthe Xilin Gol Steppe was improved at first andthen degenerated.In 1991,the environmental qualityintheupstream wasbetterthan thatinthedownstream,and it was beterintheeastern part than thatin the western part.In 2O04,the spatial diferenceof theoverall ecological environmental qualityin the study area was obviously changed compared with that in 1991.The ecological environment quality in the upstream was improved but obviously decreased in the downstream.By 2O17,theecological environment quality in the whole study area wasroundly reduced,and agood ecological environment was remained onlyalong the upper banks of the Xilin River and the southern and the southeast parts of the drainage basin.

Key words:modified remote sensing ecological index(MRSEI）；principal component analysis；ecological factor; environment evaluation；Xilin Gol