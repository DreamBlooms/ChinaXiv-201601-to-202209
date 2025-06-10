# 基于距离聚类与K-means动态聚类的棉田土壤养分评价研究

范向龙¹²，吕新²，张泽¹²，高攀23，张强12，印彩霞1²，易翔1.2

(1.石河子大学农学院,新疆生产建设兵团绿洲生态农业重点实验室,新疆 石河子832003;2.新疆兵团农业大数据国家地方联合工程研究中心,新疆 石河子832003;3.石河子大学信息科学与技术学院，新疆石河子832003)

摘要：为了解棉田土壤养分状况及确定养分丰缺程度,研究采用主成分结合距离聚类、K-means动态聚类以及土壤养分综合评价方法对新疆棉田土壤进行分析评价。结果表明：(1）在主成分分析中,有效铜、有效锰和碱解氮起主要作用,有效铜含量为 $1 . 8 2 ~ \mathrm { m g \cdot k g ^ { - 1 } }$ ,丰缺评价状况属于高等水平,有效锰含量为 $1 1 . 3 6 ~ \mathrm { { m g } \cdot \mathrm { { k g } ^ { - 1 } } }$ ,属于较低水平,碱解氮含量为 $1 2 2 . 0 7 ~ \mathrm { { m g \cdot k g ^ { - 1 } } }$ ,属于高等水平,土壤速效磷、速效钾、有效锌和有效铁含量较低,土壤养分含量分布不均匀。在距离聚类和K-means动态聚类中,有机质、碱解氮、有效锰含量较低,其余养分含量较高。在距离聚类中，,土壤各类养分可表示为：第I类 $\mathrm { > }$ 第V类 $>$ 第V类 $>$ 第Ⅱ类 $>$ 第Ⅲ类，而在K-means动态聚类中可以表示为：第Ⅲ类 $>$ 第I类 $: >$ 第V类 $: >$ 第Ⅱ类 $\mathrm { > }$ 第IV类。(2)在土壤综合肥力指数评价值中(IFI),1连和16连的等级高;2连、3连、4连、6连、15连、19连和二监区的等级较高;8连、9连、10连、11连、12连、17连、18连和20连在中等水平。5连、7连、一监区和农市站的等级较低。K-means动态聚类比距离聚类分类效果好,可以更加科学合理、准确有效地对土壤养分进行综合评价。

关键词：土壤养分；距离聚类；K-means动态聚类；综合评价值

土壤对作物生长起着决定性的作用，土壤肥力是土壤物理结构及化学性质的综合表现[]。土壤养分是评价土壤肥力的主要指标2，决定着农作物产量的高低[3]。人们经常用土壤养分的均值来代表整个田块的土壤养分状况，按单个养分含量进行施肥，此种施肥模式往往达不到按需施肥的目的，反而降低了肥料的利用效率。因此，综合土壤养分多个指标对其进行分析判别是非常有必要的，既可以客观评价土壤养分肥力状况，又可提高肥料的利用效率，增加经济效益。

戴余波等4运用主成分分析法，将耕地土壤养分分为4个等级，对于肥力较差的土壤制定相应的施肥方案；刘少春等5采用主成分分析对蔗田土壤进行评价，分析发现有机质不仅与土壤的氮、磷有关，还与微量元素铜、锰、锌有着密切的关系，并得出有机质可以作为反映土壤肥力的一个重要综合指标；李世瑶等采用主成分分析将各评价指标的加权和作为灌水质量的综合主成分指标，发现综合主成分能更好的反应灌水质量变异信息；安云娜等[7运用模糊数学和偏相关分析法得出土壤养分的综合指标值，并提出了不同施肥意见及土地改良措施；唐佐芯等8通过主成分与聚类方法分析发现地形、海拔和pH是影响植烟土壤分类的主要环境因素;郑琦等采用模糊综合指数法(FCE）、土壤综合质量指数法(SQI)及内梅罗综合污染指数法（N-PI)分别对棉田土壤进行分析评价，得出SQI评价法比FCE和N-PI评价法效果好。

综上所述，已有研究主要通过主成分或聚类等单一方法对土壤养分进行分析，而运用主成分与聚类方法相结合在土壤养分的研究中较少，主成分分析的特征是对信息贡献影响力综合评价，结合聚类分析法，可以更精准、更加全面真实的反应土壤养分综合状况。因此，本研究对新疆生产建设兵团农二师33团的土壤进行相关分析，通过主成分结合距离聚类以及K-means动态聚类的方法对多个土壤养分指标进行分级判别与评价，建立其更加合理有效的土壤养分评价方法，以期为科学施肥提供指导。

# 研究区概况与方法

# 1.1 研究区概况

新疆生产建设兵团农二师33团 $( 8 7 ^ { \circ } 0 3 ^ { \prime } 3 0 ^ { \prime \prime } \mathrm { E }$ $4 0 ^ { \circ } 4 0 ^ { \prime } 0 0 " { \sim } 4 0 ^ { \circ } 5 3 ^ { \prime } 5 2 " \mathrm { N } )$ 位于塔里木河下游,地处塔克拉玛干大沙漠腹地、东北边缘的孔雀河和西南方向的塔里木河之间["]。研究区日照时间比较长，光热资源丰富，无霜期平均210d,年平均降水量58.6$\mathbf { m } \mathbf { m }$ ,年最大蒸发量为 $2 7 8 8 . 2 \ : \mathrm { m m }$ ,降水少而蒸发大，冬寒夏热，昼夜温差悬殊，属典型的暖温带大陆性干旱气候，对农业的发展有重要的影响，通过多年的发展,已成为南疆棉花生产的重要组成部分[]。

# 1.2数据来源及指标测定

采用2013—2015年的土壤养分数据从新疆生产建设兵团农二师33团获取，每个土壤样品选择五点取样法进行样品采集，试验区土地均匀平整，土壤取样深度为 $0 { \sim } 2 0 ~ \mathrm { c m }$ ，每个采样点采样完成后用

![](images/899f982b55db3dcc49ebba1b6d875c5f0a81627d5c81771c2630fcb7dd5d5521.jpg)  
图1农二师33团位置及采样点分布  
Fig.1 Distribution map of position and sampling points in 33 Mission of Agriculture Division 2

GPS进行定位（图1)。采样指标包括有机质（OM）、碱解氮（AN）、速效磷（AP）、速效钾（AK）、有效铜（ACu）、有效锌（ $\mathrm { { . A Z n } }$ ）、有效锰（AMn）、有效铁（AFe），其中有机质采用重铬酸钾容量法测定（稀释热法），碱解氮采用碱解扩散法测定，速效磷采用碳酸氢钠提取一钼锑抗比色法测定；速效钾采用乙酸铵浸提一火焰光度计法测定；有效铁、锰、铜、锌均采用DTPA浸提一电感耦合等离子体质谱法测定[12]。每个土样测定重复3次，结果取其平均值，最后对其进行等级划分[13-14]

# 1.3 研究方法

1.3.1主成分分析由于土壤原始数据样本比较大，所得到的统计数据信息在一定程度上会出现重叠现象,变量过多会出现数据的复杂性[15]。主成分分析可有效解决以上缺陷，其主要作用是用少量指标来反映大量原始变量的信息[16]

1.3.2距离聚类距离聚类在数据挖掘中属于无监督学习[17],先将数据集划分为很多子集，让同一集合内的数据相似性增高，而不同集合间的数据差异变得更明显[18]。本文采用欧式距离对原始数据进行处理[19],其优点是新增的对象不会涉及两个对象间的任何距离，计算公式：

$$
d ( x , y ) = { \sqrt { \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 } } }
$$

式中： $x , y$ 为数据对象; $n$ 为数据对象的维度; $x _ { i } \setminus y _ { i }$   
为 $x$ 和 $y$ 的第 $i$ 个属性值。

1.3.3K-means聚类K-means聚类属于无监督学习的一种聚类方法[20]。主要针对观测到的数据,根据给定的准则发现具有的共同点，在数据集中寻找“群”。K-means聚类以距离作为数据对象间相似性度量的标准[2I-23],其原理是先从所有数据集中随机选取初始聚类中心，计算剩余数据与聚类中心间的距离，找出离目标数据最近的聚类中心，并将数据对象分配到聚类中心所对应的簇中。然后将每个簇中的数据均值作为新的中心，进行下一次迭代，直到聚类中心不再变化为止[24]，计算公式如下：

$$
d ( \boldsymbol { X } , \boldsymbol { C } _ { i } ) = \sqrt { \sum _ { j = 1 } ^ { m } ( \boldsymbol { X } _ { j } - \boldsymbol { C } _ { i j } ) ^ { 2 } }
$$

式中： $X$ 为数据对象； $C _ { i }$ 为第 $i$ 个聚类中心； $m$ 为数据对象的维度; $X _ { j } \setminus C _ { i j }$ 为 $X$ 和 $C _ { i }$ 的第 $\cdot j$ 个属性值。

1.3.4土壤肥力指数土壤肥力指数是评价土壤肥力常用的方法[25]。土壤肥力指数的计算方法有：直接叠加法、权重加权求和法、综合评价模型等。本文主要采用综合肥力指数评价模型(IFI)[26]。土壤综合肥力指标值(IFI)划分为5个等级，即：低( $\mathrm { I F I } <$ 0.2）、较低 $0 . 2 { \leqslant } \mathrm { I F I } < 0 . 4 \$ ）、中 $( 0 . 4 { \leqslant } \mathrm { I F I } < 0 . 6 )$ ）、较高L $( 0 . 6 { \leqslant } \mathrm { I F I } < 0 . 8 )$ 和高（ $\mathrm { [ F I geqslant 0 . 8 ~ } )$ 。IFI能够全面反映土壤养分状况，取值范围在0\~1之间，越接近1，说明土壤肥力越好[27]。计算公式如下：

$$
\mathrm { { I F I } } = \sum _ { i = 1 } ^ { n } Q _ { i } Y _ { i }
$$

式中： $n$ 为指标个数; $Q _ { i }$ 和 $Y _ { i }$ 分别为第 $i$ 种肥力指标的隶属度和相应的权重。

通过计算8个土壤养分指标的公共因子方差，将公共因子方差进行归一化，结果作为各项肥力指标的权重。通过模糊数学中的隶属度函数法对数据进行了标准化处理,以消除量纲的影响[28]。由于土壤养分因子变化具有连续性，所以在评价指标时可采用连续性的升型隶属度函数[29]

# 2 结果与分析

# 2.1土壤养分主要特性

通常用变异系数 $( C V )$ 来反映土壤养分的空间分布状况,当 $C V { < } 0 . 1$ 时为弱变异， $C V$ 在0.1\~1.0时为中等变异, $C V { > } 1 . 0$ 时为强变异[30-31],土壤养分特性由表1可知，研究区中OM、AN变异系数最低，为0.16,表明AN在土壤中分配较集中，而AZn变异系数最高，为0.61，AZn在土壤中分配比较离散，剩余各养分指标均属于中等变异。

# 2.2土壤养分特征元素的提取

本文主要以8个土壤养分指标为基础数据，通过主成分分析做相关矩阵及贡献率，找出土壤中少量所具备代表性的综合指标，以较少的土壤信息变量为基准，来反映出土壤原来的总体变量信息（表2)。由表2可知，前3个主成分特征值均大于1，累计贡献率为 $8 8 . 6 9 \%$ ,即涵盖了最初8个指标的原始数据信息，表明前3项主成分能够代表最初的8个指标原始数据信息。

由土壤养分主成分旋转后的载荷系数可知（表3)，第一主成分与ACu高度正相关，主成分载荷为0.966，说明第一主成分是ACu的综合反映;第二主成分中，AMn的主成分载荷最高为0.812，说明第二主成分主要反映的是AMn对土壤养分的供给情况；第三主成分中，AN的主成分载荷最高为0.964，表明第三主成分是对AN含量的描述。因为总方差近$8 8 . 6 9 \%$ 的贡献率来自于这3个因素，由此认为ACu、AMn、AN是农二师33团土壤的特征元素。

# 2.3基于距离聚类的土壤养分分类评价

距离聚类分类结果见图2，根据土壤养分含量利用距离聚类将农二师33团划分为5种类型，第I类有16连，与相近的地区土壤养分差异较大；第Ⅱ类有二监区；第Ⅲ类包括5连、12连、农市站和一监区；第V类包括3连和4连；第V类包括1连、2连、6连、7连、8连、9连、10连、11连、15连、17连、18连、19连、20连。

由土壤养分各元素含量比较可知(表4)，AN、AP、AK、AFe含量在各类别间差异比较大，其余各土壤养分含量变化差异不大。OM含量在第I类、第V类和第V类间及第Ⅱ类和第Ⅲ类间差异不显著；AN含量在第Ⅱ类与第V类及第Ⅲ类与第N类间差异不显著;AP含量在第I类和第Ⅱ类及第N类和第

表1土壤养分各指标描述统计分析  
Tab.1 Statistical analysis of soil nutrient indicators   

<html><body><table><tr><td>指标/(mg·kg-1)</td><td>最大值</td><td>最小值</td><td>均值</td><td>极差</td><td>标准差</td><td>变异系数</td></tr><tr><td>OM</td><td>11220</td><td>6310</td><td>9370</td><td>4910</td><td>1510</td><td>0.16</td></tr><tr><td>AN</td><td>158.32</td><td>88.63</td><td>122.07</td><td>69.69</td><td>19.77</td><td>0.16</td></tr><tr><td>AP</td><td>26.39</td><td>10</td><td>20.36</td><td>16.39</td><td>4.44</td><td>0.21</td></tr><tr><td>AK</td><td>192.13</td><td>143.6</td><td>149.77</td><td>48.53</td><td>29.97</td><td>0.20</td></tr><tr><td>AFe</td><td>15.63</td><td>10.79</td><td>9.25</td><td>4.84</td><td>3.29</td><td>0.35</td></tr><tr><td>AMn</td><td>15.18</td><td>3.65</td><td>11.36</td><td>11.53</td><td>3.81</td><td>0.33</td></tr><tr><td>ACu</td><td>2.41</td><td>1.55</td><td>1.82</td><td>0.86</td><td>0.61</td><td>0.33</td></tr><tr><td>AZn</td><td>3.45</td><td>1.97</td><td>1.07</td><td>1.48</td><td>0.651</td><td>0.61</td></tr></table></body></html>

注：OM表示有机质;AN表示碱解氮；AP表示速效磷；AK表示速效钾；AFe表示有效铁;AMn表示有效锰;ACu表示有效铜； $\mathrm { A Z n }$ 表示有效锌。下同。

Tab.2 PCA interpretation of soil nutrients in study area   

<html><body><table><tr><td>主成分数</td><td>特征值</td><td>累计方差贡献率/%</td></tr><tr><td>1</td><td>4.260</td><td>53.252</td></tr><tr><td>2</td><td>1.757</td><td>75.212</td></tr><tr><td>3</td><td>1.078</td><td>88.690</td></tr><tr><td>4</td><td>0.578</td><td>95.914</td></tr><tr><td>5</td><td>0.174</td><td>98.084</td></tr><tr><td>6</td><td>0.117</td><td>99.553</td></tr><tr><td>7</td><td>0.032</td><td>99.956</td></tr><tr><td>8</td><td>0.003</td><td>100.000</td></tr></table></body></html>

表2研究区土壤养分PCA解释主变量  

<html><body><table><tr><td>指标</td><td>PC1</td><td>PC2</td><td>PC3</td></tr><tr><td>OM</td><td>0.693</td><td>0.670</td><td>0.147</td></tr><tr><td>AN</td><td>-0.157</td><td>0.038</td><td>0.964</td></tr><tr><td>AP</td><td>0.319</td><td>0.809</td><td>0.261</td></tr><tr><td>AK</td><td>0.517</td><td>0.719</td><td>0.377</td></tr><tr><td>AFe</td><td>0.593</td><td>0.164</td><td>0.747</td></tr><tr><td>AMn</td><td>-0.220</td><td>0.812</td><td>-0.268</td></tr><tr><td>ACu</td><td>0.966</td><td>0.084</td><td>0.028</td></tr><tr><td>AZn</td><td>0.538</td><td>0.025</td><td>0.700</td></tr></table></body></html>

# 表3研究区土壤养分主成分旋转后的载荷矩阵

V类之间差异不显著，第Ⅲ类与其余各类别间AP含量差异显著;AK含量除了第Ⅲ类与其余各类间差异显著，剩下的各类别间AK含量差异不显著；AFe含量除了第I类、第Ⅱ类和第V类间差异不显著外，其余各类间AFe含量差异显著；AMn含量在第Ⅱ类和第V类及第Ⅲ类和第V类间差异不显著；ACu含量除了第1类与其余各类间差异显著外，剩余各类别间ACu含量差异不显著；AZn含量在第I类和第V类及第Ⅱ类、第Ⅲ类和第V类间差异不显著，其余各类别间差异显著；土壤各类别养分总体状况可以表示为：第I类 $>$ 第V类 $>$ 第V类>第Ⅱ类>

![](images/a2b6b9d7380951eefed68be32e662ce846b15970485727549b4442b9115860c9.jpg)  
图2土壤养分距离分类  
Fig.2 Soil nutrient distance clustering

第Ⅲ类。

# 2.4基于K-means动态聚类的土壤养分分类评价

通过K-means动态聚类方法将农二师33团土壤养分分为5种类型(图3)，第I类包括1连、3连、4连、15连;第Ⅱ类包括7连、8连、9连、10连、11连、17连、18连、19连、20连；第Ⅲ类包括2连、6连、16连；第V类包括5连、12连、一监区和农市站;第V类只有二监区。

从各类别土壤养分含量可知(表5），土壤养分含量变化差异比较大的是AP、AK、AFe。OM含量中第V类和第V类差异不显著，第Ⅱ类和第Ⅲ类OM含量差异显著；AN含量各类别间差异不显著；AP含量在第I类和第V类及第Ⅱ类和第Ⅲ类间差异不显著，第Ⅲ类与其余各类别间AP含量差异显著；AK含量在第I类、第Ⅱ类和第V类间含量差异不显著，第Ⅲ类和第IV类与其余各类别间AK含量差异显著;AFe含量在第I类、第Ⅲ类和第V类间差异不显著;AMn含量在第I类和第V类及第Ⅱ类、第I类和第V类间差异不显著； $\mathrm { A G u }$ 含量除了第Ⅲ类与其余各类别间差异显著外，其余各类别间ACu含量差异不显著；AZn含量在第Ⅱ类和第V类间差异不显著。土壤各类别养分总体状况可以表示为：第Ⅲ类>第I类>第V类>第Ⅱ类 $>$ 第V类。

Tab.3 Component load matrix of soil main nutrient afterrotationin the studyarea   
表4各类别土壤养分元素含量比较  
Tab.4 Comparison of soil nutrient elements in each category   

<html><body><table><tr><td>类别</td><td>OM</td><td>AN</td><td>AP</td><td>AK</td><td>AFe</td><td>AMn</td><td>ACu</td><td>AZn</td></tr><tr><td>I</td><td>1.03a</td><td>86.37a</td><td>20.08b</td><td>192.31a</td><td>15.72a</td><td>3.45ab</td><td>2.42a</td><td>3.21a</td></tr><tr><td>Ⅱ</td><td>0.67b</td><td>73.77b</td><td>17.87b</td><td>170.96a</td><td>13.96a</td><td>2.43b</td><td>1.40b</td><td>1.36b</td></tr><tr><td>Ⅲ</td><td>0.76b</td><td>61.38c</td><td>11.18c</td><td>111.26b</td><td>5.91c</td><td>4.57a</td><td>1.79b</td><td>1.66b</td></tr><tr><td>V</td><td>0.98a</td><td>57.85c</td><td>28.68a</td><td>176.75a</td><td>14.5a</td><td>2.88b</td><td>1.86b</td><td>2.68a</td></tr><tr><td>V</td><td>1.02a</td><td>70.18b</td><td>20.89a</td><td>192.43a</td><td>8.88b</td><td>4.44a</td><td>1.60b</td><td>1.77b</td></tr></table></body></html>

注：同列数据不同小写字母表示不同土壤类别间差异显著水平 $( P < 0 . 0 5 )$ 。

![](images/e095ba83f5c8bdf71b8c43d16cacd6c935a901bfd846639c82b4043b74fa0c63.jpg)  
图3K-means动态聚类 Fig.3K-means dynamic clustering

# 2.5土壤肥力权重及隶属度值的确定

通过对8个土壤养分指标进行主成分分析（表

2),经计算得出土壤养分各指标的公因子方差和权  
重(表6)，AFe、AMn和AN的权重高，分别为0.5327、  
0.2196、0.1348，AK、OM和AZn的权重较低，分别为  
0.0722、0.0217、0.0146，AP和ACu的权重最低，为  
0.0003和0.0039。

由土壤各指标隶属度统计可知(表7),OM、AN、AP、AFe和AMn的变异系数在 $0 . 4 0 9 \mathrm { \sim } 0 . 4 9 1$ ;AK和AZn的变异系数0.305和0.371;ACu的变异系数在0.511。各指标的隶属度值总体变异系数较小，因此，研究区8个土壤养分指标可全部作为土壤肥力质量敏感的参评指标。

# 2.6土壤养分状况评价

从土壤的综合肥力指数可以看出(表8)，依据土壤综合肥力指标等级划分，2连、3连、4连、6连、15连、19连和二监区的IFI值在较高水平；8连、9连、10连、11连、12连、17连、18连和20连的IFI值在中等水平;5连、7连、一监区和农市站的IFI值在较低水平。

# 表5各类别土壤养分含量

Tab.5 Soil nutrient content of each category   

<html><body><table><tr><td>类别</td><td>OM</td><td>AN</td><td>AP</td><td>AK</td><td>AFe</td><td>AMn</td><td>ACu</td><td>AZn</td></tr><tr><td>I</td><td>1.03ab</td><td>62.18a</td><td>27.64a</td><td>166.49b</td><td>12.32a</td><td>2.96b</td><td>1.85b</td><td>2.02b</td></tr><tr><td>Ⅱ</td><td>1.00b</td><td>61.75a</td><td>17.96b</td><td>160.62b</td><td>7.67b</td><td>4.54a</td><td>1.63b</td><td>1.55c</td></tr><tr><td>Ⅲ</td><td>1.11a</td><td>71.87a</td><td>19.35b</td><td>192.69a</td><td>12.43a</td><td>4.05a</td><td>2.92a</td><td>3.01a</td></tr><tr><td>V</td><td>0.70c</td><td>63.48a</td><td>10.46c</td><td>110.42c</td><td>6.76b</td><td>4.23a</td><td>1.73b</td><td>1.71ab</td></tr><tr><td>V</td><td>0.65c</td><td>74.43a</td><td>18.36b</td><td>166.33b</td><td>13.5a</td><td>2.58b</td><td>1.34b</td><td>1.37c</td></tr></table></body></html>

# 表6土壤各指标公因子方差及权重

Tab.6 Variance and weight of common factors of soil indexe!   
表7土壤各指标隶属度统计  

<html><body><table><tr><td></td><td>OM</td><td>AN</td><td>AP</td><td>AK</td><td>AFe</td><td>AMn</td><td>ACu</td><td>AZn</td></tr><tr><td>公因子方差</td><td>0.8943</td><td>0.9383</td><td>0.7335</td><td>0.9184</td><td>0.9971</td><td>0.9565</td><td>0.7483</td><td>0.8275</td></tr><tr><td>权重</td><td>0.0217</td><td>0.1348</td><td>0.0003</td><td>0.0722</td><td>0.5327</td><td>0.2196</td><td>0.0039</td><td>0.0146</td></tr></table></body></html>

Tab.7Statistics of membership degree of soil indexes   

<html><body><table><tr><td>指标/(g·kg-1)</td><td>最大值</td><td>最小值</td><td>均值</td><td>标准差</td><td>变异系数</td></tr><tr><td>OM</td><td>0.991</td><td>0.100</td><td>0.648</td><td>0.270</td><td>0.417</td></tr><tr><td>AN</td><td>0.992</td><td>0.098</td><td>0.549</td><td>0.243</td><td>0.442</td></tr><tr><td>AP</td><td>0.994</td><td>0.148</td><td>0.583</td><td>0.238</td><td>0.409</td></tr><tr><td>AK</td><td>0.921</td><td>0.098</td><td>0.619</td><td>0.189</td><td>0.305</td></tr><tr><td>AFe</td><td>0.994</td><td>0.097</td><td>0.472</td><td>0.232</td><td>0.491</td></tr><tr><td>AMn</td><td>0.974</td><td>0.102</td><td>0.549</td><td>0.257</td><td>0.468</td></tr><tr><td>ACu</td><td>0.836</td><td>0.065</td><td>0.328</td><td>0.167</td><td>0.511</td></tr><tr><td>AZn</td><td>0.921</td><td>0.100</td><td>0.366</td><td>0.135</td><td>0.371</td></tr></table></body></html>

# 表8研究区土壤的综合肥力指数

Tab.8 Comprehensive soil fertility index of the study area   

<html><body><table><tr><td>区域</td><td>IFI</td><td>等级</td><td>区域</td><td>IFI</td><td>等级</td><td>区域</td><td>IFI</td><td>等级</td></tr><tr><td>1连</td><td>1.596</td><td>高</td><td>8连</td><td>0.473</td><td>中等</td><td>17连</td><td>0.533</td><td>中等</td></tr><tr><td>2连</td><td>0.628</td><td>较高</td><td>9连</td><td>0.483</td><td>中等</td><td>18连</td><td>0.591</td><td>中等</td></tr><tr><td>3连</td><td>0.733</td><td>较高</td><td>10连</td><td>0.513</td><td>中等</td><td>19连</td><td>0.618</td><td>较高</td></tr><tr><td>4连</td><td>0.704</td><td>较高</td><td>11连</td><td>0.513</td><td>中等</td><td>20连</td><td>0.552</td><td>中等</td></tr><tr><td>5连</td><td>0.225</td><td>较低</td><td>12连</td><td>0.451</td><td>中等</td><td>一监区</td><td>0.383</td><td>较低</td></tr><tr><td>6连</td><td>0.634</td><td>较高</td><td>15连</td><td>0.705</td><td>较高</td><td>二监区</td><td>0.765</td><td>较高</td></tr><tr><td>7连</td><td>0.356</td><td>较低</td><td>16连</td><td>0.922</td><td>高</td><td>农市站</td><td>0.292</td><td>较低</td></tr></table></body></html>

通过距离聚类及K-means动态聚类对新疆生产建设兵团农二师33团棉田土壤进行分类评价，不同的分类方法根据其距离中心及分类原理将土壤养分为5类，距离聚类和K-means动态聚类中第I类与第Ⅲ类土壤养分含量整体高于其他几类,但是距离聚类中的第Ⅲ类与K-means动态聚类中的第V类土壤养分含量相近，这是由于不同分类方法中各土壤养分之间以及养分离聚类中心点是不同的，导致其分类结果出现偏差。通过土壤肥力权重及隶属度值的计算，发现农二师33团土壤养分差异比较大，一方面可能因为新疆棉区主要分布在盆地周围，降水较少，并且土质疏松，土壤理化性质较差，导致土壤养分容易流失，另一方面可能与当地有机肥的施入有关。通过土壤肥力综合指数(IFI)进行等级划分，分析得出农二师33团各地区处于中等和高等水平的所占比例最大，处于低等水平所占比例少，说明土壤肥力高，适合农作物生长。将距离聚类和K-means动态聚类的分类结果与土壤肥力综合指数等级划分结果相比，分析发现K-means动态聚类的分类结果更加接近土壤肥力综合指数的分类结果，因此，K-means动态聚类在土壤养分的分类方法上其效果更好，后期可直接用主成分结合Kmeans动态聚类对土壤养分进行分析评价。

# 3讨论

# 3.1土壤养分机理分析

土壤养分是反映土壤肥力高低的关键指标之一,直接影响着作物的生长发育及产量的高低[32-34]，土壤养分的评价可以为土地合理使用、农作物种植、农田施肥、土壤污染、科学治理等提供建议。土壤养分是一个动态变化的过程。本文通过主成分分析得出农二师33团土壤养分主要以AN、ACu和AMn为主，其他元素含量较低，这与田立文等35的研究不一致，主要由于农二师33团农民种植过程中不施用微量元素肥料，并且长期用苦咸水来灌溉棉田，苦咸水中含有少量微量元素，以磷肥最为突出，但这与土壤中微量元素含量变化是否有关，有待进一步研究。新疆种植区域以盐碱地为主，微量元素随土壤pH的升高而减小，有效性也随之降低，土壤中微量元素的有效性大部分存在于矿物晶格中，不能被植物吸收利用。土壤养分全量仅能看储量指标，不能反映其有效性，微量元素的供给不足除了有可能是因微量元素的全量低之外，还有一种可能是土壤中微量元素有效性低。因此，合理调控当地土壤中微量元素的植物有效性是实现有效管理的关键，并且微量元素在土壤中的有效性与土壤-植物的相互作用紧密相关。

农二师33团氮肥含量多，磷钾肥含量少，由于当地灌溉主要选用滴灌技术，不同滴灌时段下的土壤养分变异不同，差异比较大，这与袁宇尧等[3研究结果基本一致，当地施氮肥以提高棉花产量，氮肥过量棉花无法全部吸收，常年在土壤中积累，与张丹等7的研究结果不同，滴灌所带入土壤中的氮以硝态氮为主，滴灌棉田属于落干晒田，利于土壤通气性，促进作物生长。土壤氮一部分被作物所吸收，另一部分被微生物所吸收同化。碱性土壤能增加含磷化合物溶解度，导致土壤磷的有效性降低，频繁的干湿交替以及高温，会导致钾的释放。有机质与土壤微生物密切相关，含水量或温度过高会限制微生物的活动，影响有机质的分解和转化，有机质在土壤中的分解与转化比较复杂，其来源由动植物残体的数量和类型决定。当地灌水比较多，但每年将秸秆归还大田中，土壤有机碳与活性有机碳含量会明显增高，所以有机质含量总体不是很低。土壤养分丰缺与长期连作、合理灌溉施肥、膜下滴灌技术等有着密切的关系。所以在今后土壤养分供给中，应因地制宜合理施肥，保证土壤养分的协调供应。

# 3.2距离聚类与K-means动态聚类可行性分析比较

距离聚类与K-means动态聚类将土壤养分各划分为5类，在距离聚类中，第I类土壤养分含量整体高于其他几类，而在K-means动态聚类中，第Ⅲ类土壤养分含量整体要高于其他类，各土壤养分之间以及养分离聚类中心点是不同的，导致其分类结果不同。通过土壤肥力权重及隶属度值的确定，发现农二师33团土壤养分差异比较明显，但土壤养分各元素分布比较集中，这与陈彦[38的研究结果相同，新疆地域辽阔，土壤本身属性差异与不同棉区的成土母质有关，产棉区由于不同区域、气候、温度、地形等环境差异，在空间位置上比较分散，而且新疆以滴灌为主，所以使得土壤养分变异更加分散，不管是在水平方向还是垂直方向都会出现。

土壤肥力综合指数(IFI)能更加全面反映土壤养分状况，在其等级划分中，中等和高等水平所占比例最大，低等水平所占比例少，则表明研究区土壤肥力较好。距离聚类的分类结果与土壤养分综合评价值的分类结果差异比较大，而K-means动态聚类与土壤养分综合评价值的分类结果比较接近，因此，K-means动态聚类对土壤分类效果更好，这与孙亚洲[39的研究结果一致，距离聚类是对原始数据进行优化分析，是根据各个养分指标间的空间距离而产生的聚类，其对数据挖掘比较浅，而K-means动态聚类则是对预处理后的数据进一步挖掘分析，是土壤养分各指标对其聚类中心点之间的相似度所产生的聚类，其结果更能反应土壤的真实情况

# 4结论

通过对新疆生产建设兵团第二师33团棉田土壤养分进行主成分分析研究，筛选出具有代表性的土壤养分综合指标，通过不同聚类算法以及土壤养分综合评价值对该区域棉田土壤养分进行分析评价，主要得出以下结论：

（1）通过主成分分析得出，基于主成分分析方法，研究区棉田土壤有效铜、有效锰和碱解氮起主要作用，土壤速效磷、速效钾、有效锌和有效铁含量较低，土壤养分含量分布整体表现不均匀。

(2）采用距离聚类与K-means动态聚类方法将研究区棉田土壤养分分为5种类型，不同分类方法对土壤养分等级划分结果也不同。在距离聚类中各类别土壤养分类型划分情况为：第I类 $\mathrm { > }$ 第V类>第V类 $\mathrm { > }$ 第Ⅱ类 $>$ 第Ⅲ类，而在K-means动态聚类中土壤养分等级表现为：第Ⅲ类 $>$ 第I类 $\mathrm { > }$ 第V类 $>$ 第Ⅱ类 $\mathrm { > }$ 第V类。

(3）通过土壤养分综合评价值IFI划分肥力等级的方法可知，该棉区土壤综合肥力指数等级处于中等及较高水平，土壤肥力状况良好。土壤养分综合评价值的分类结果与距离聚类的分类结果差异比较大，而与K-means动态聚类分类结果相近，因此，K-means动态聚类比距离聚类分类效果好。

# 参考文献(References):

[1]陈玉芹,胡永亮,张丽萍,等.基于主成分和聚类分析的德宏橡 胶林土壤肥力评价[J].热带作物学报,2019,40(8):1461-1467. [Chen Yuqin,Hu Yongliang,Zhang Liping,et al. Evaluation of soil fertility of rubber plantation in Dehong based on principal component and cluster analysis[J].Chinese Journal of Tropical Crops,2019,40(8): 1461-1467.]   
[2] 任艳芳,何俊瑜,张艳超,等.贵州省开阳茶园土壤养分状况与 肥力质量评价[J].土壤,2016,48(4):668-674.[Ren Yanfang,He Junyu, Zhang Yanchao,et al. Soil nutrient status and comprehensive evaluation of quality of soil fertility of tea garden in Kaiyang of Guizhou Province[J]. Soils,2016,48(4): 668-674.]   
[3]赵月玲,林玉玲,曹丽英,等.基于主成分分析和聚类分析的土 壤养分特性研究[J].华南农业大学学报,2013,34(4):484-488. [Zhao Yueling,Lin Yuling,Cao Liying,et al.A study of soil nutrients characteristics based on principal component and cluster analysis[J]. Journal of South China Agricultural University,2013, 34(4): 484-488.]   
[4]戴余波,张丽萍,李国明,等.热带作物耕地土壤养分分析及肥 力评价[J].现代农业科技,2017,52(18):155-157.[Dai Yubo, Zhang Liping,Li Guoming,et al. Soil nutrient analysis and soil fertility evaluation of tropical crop land[J]. Modern Agricultural Science and Technology,2017,52(18): 155-157.]   
[5]刘少春,张跃彬,郭家文,等.基于养分丰缺分级的蔗田土壤肥 力主成分综合分析[J].西南农业学报,2016,29(3):611-617. [Liu Shaochun, Zhang Yuebin,Guo Jiawen,et al.Comprehensive analysis of main components of soil fertility of sugarcane field based on soil nutrient grades[J]. Southwest China Journal of Agricultural Sciences,2016,29(3): 611-617.] [6]李世瑶,蔡焕杰,陈新明.基于主成分分析的畦灌质量评价[J]. 农业工程学报,2013,29(24):86-93.[Li Shiyao,Cai Huanjie, Chen Xinming.Evaluation of border irrigation performance based on principal component analyses[J]. Transactions of the Chinese Society of Agricultural Engineering,2013,29(24): 86-93.] [7]安云娜,黄义雄,官紫玲.福建东山岛土壤养分综合评价[J].安 徽农业科学,2007,35(13): 3926-3927.[An Yunna, Huang Yixiong,Guan Ziling.Comprehensive valuation on soil nutrient in Dongshan island of Fujian[J]. Journal of Anhui Agricultural Sciences,2007,35(13): 3926-3927.] [8]唐佐芯,李天壁,陈泽斌,等.基于主成分分析和聚类分析的红 河州植烟土壤特性研究[J].西南农业学报,2019,32(7):1607-   
1613.[Tang Zuoxin,Li Tianbi,Chen Zebin,etal. Study of Honghe tobacco-planting soil nutrients characteristics based on principal component and cluster analysis[J]. Southwest China Journal of Agricultural Sciences,2019,32(7): 1607-1613.] [9]郑琦,王海江,董天宇,等.基于不同评价方法的绿洲棉田土壤 质量综合评价[J].灌溉排水学报,2019,38(3):90-98.[Zheng Qi,Wang Haijiang,Dong Tianyu,et al. Evaluating soil quality of the cotton fields in Oasis of Xinjiang using different methods[J]. Journal of Irrigation and Drainage,2019,38(3): 90-98.] [10] 胡俊建.守护沙漠绿洲——新疆兵团第二师三十三团生态文明 建设纪实[J].中国农垦,2018,63(4):51-52.[Hu Junjian.Guarding the desert and oasis: The record of ecological civilization constructionof the 33rd regiment of the second division of Xinjiang Production and Construction Corps[J]. China Agricultural Reclamation,2018,63(4): 51-52.] [11] 古丽努尔·沙布尔哈孜,尹林克,热合木都拉·阿地拉,等.塔里 木河中下游退耕还林还草综合生态效益评价——以新疆生产 建设兵团农二师33 团为例[J].干旱区研究,2004,21(2):161-   
165.[Gulnur Sabirhazi, Yin Linke,Rahmuttula Adil, et al. Evaluation on the compositive ecological benefits of withdrawing from farming to afforesting and grass planting in the middle and lower reaches of the Tarim River: A case study in 33rd regiment,second division,Xinjiang Group Company of Production and Construction [J]. Arid Zone Research,2004,21(2): 161-165.] [12]鲍士旦.土壤农化分析[M].北京.中国农业出版社,2016.[Bao Shidan. Soil Agrochemical Analysis[M]. Beijing: China Agricultural Press,2016.] [13 杨晓武.定边县板凳滩土壤系统分类与土壤肥力评价研究[D]. 杨凌：西北农林科技大学,2012.[Yang Xiaowu.Soil Taxonomy and Fertility Evaluation of Bandeng Bottomland in Dingbian Country[D].Yangling: Northwest A&FUniversity,2012.] [14] 张珊珊,毛云玲,冯志伟,等.云南松林下干巴菌生长土壤有效 态微量元素特征及其影响因素[J].东北林业大学学报,2021,   
49(3):108-112,125.[Zhang Shanshan,Mao Yunling,Feng Zhiwei, et al.Available microelement characteristics of soil and its influential factors for the growth of Thelephora ganbajun under Pinus yunnanensis forest[J].Journal of Northeast Forestry University,2021,49(3): 108-112,125.]   
[15] 桑慧茹,王丽学,陈韶明,等.基于主成分分析的RBF神经网络 在需水预测中的应用[J].水电能源科学,2017,35(7):58-61. [Sang Huiru,Wang Lixue,Chen Shaoming,et al.Water demand forecast modelof RBF neutral networks basedonprinciple component analysis[J]. Hydropower Energy Science,2017,35(7): 58- 61.]   
[16] 李良厚,李吉跃.聚类分析在立地分类与土壤肥力评价中的应 用[C]//第三届教育技术与培训国际会议论文集(第5卷),湖北 工业大学,智能信息技术应用学会,2010:484-487.[Li Lianghou,Li Jiyue.Application of Clustering Analysis in Classifying Site Type and Evaluating Soil Fertility[Cl/ Proceedings of 2010 Third International Conference on Education Technologyand Training(Volume 5),Hubei University of Technology,Intelligent Information Technology Application Association,2010: 484-487.]   
[17] 杨俊闯,赵超.K-Means聚类算法研究综述[J].计算机工程与应 用,2019,55(23): 7-14,63.[Yang Junchuang,Zhao Chao.Survey on K- means clustering algorithm[J]. Computer Engineering and Applications,2019,55(23): 7-14, 63.]   
[18] 刘雪娇.数据挖掘中的动态聚类及增量研究[D].哈尔滨:哈尔 滨理工大学,2015.[Liu Xuejiao.Research on Dynamic Clustering and Incremental in Data Mining[D]. Harbin: Harbin Univesity of Science and Technology,2015.]   
[19] 陈迎丽,何钰,龚会琴,等.基于欧式距离法或因子化法的近红 外光谱技术对牛肉掺假鉴定的研究[J].食品研究与开发, 2019,40(15): 141-146.[Chen Yingli, He Yu, Gong Huiqin,et al. Studyon identificationof beef adulteration bynear infrared spectroscopy based on euclidean distance method or factorization method[J].Food Research and Development,2019,40(15):141-146.]   
[20]Saro,Kavita. Review: Study on simple k- mean and modified kmean clustering technique[J]. International Journal of Computer Science Engineering and Technology,2016,6(7): 279-281.   
[21]Anil K J,Data clustering: 5O years beyond $\mathbf { k }$ -means[J]. Pattern Recognition Letters,2010,31(8): 651-666.   
[22]Hung C H, Chiou HM, Yang W N. Candidate groups search for Kharmonic means data clustering[J].Applied Mathematical Modelling, 2013,37(24): 10123-10128.   
[23] 唐东凯,王红梅,胡明,等.优化初始聚类中心的改进 K-means 算法[J].小型微型计算机系统,2018,39(8):1819-1823.[Tang Dongkai,Wang Hongmei,Hu Ming,etal. Optimizing initial cluster center of improved K-means algorithm[J].Journal of Chinese Computer Systems,2018,39(8): 1819-1823.]   
[24] 杨俊闯,赵超.K-Means聚类算法研究综述[J].计算机工程与应 用,2019,55(23): 7-14,63.[Yang Junchao,Zhao Chao. Survey on K-means clustering algorithm[J]. Computer Engineering and Applications,2019,55(23): 7-14, 63.]   
[25] 付亚丽,李宏光,付国润,等.红河植烟土壤中微量元素含量分 析[J].云南农业大学学报（自然科学版),2012,27(1):73-79. [Fu Yali,Li Hongguang,Fu Guorun,etal.Analysis of soil trace elements in Honghe tobacco-growing area[J]. Journal of Yunnan Agricultural University(Natural Science),2012,27(1): 73-79.]   
[26] 胡玲,周丽娟,王娟,等.云南烟区植烟土壤养分状况综合评价 [J].河南农业科学,2014,43(7):52-59.[Hu Ling, Zhou Lijuan, Wang Juan,et al. Comprehensive evaluation of soil fertility in tobacco-growing areas in Yunnan Province[J]. Journal of Henan Agricultural Sciences,2014,43(7): 52-59.]   
[27]陈江华.中国植烟土壤及烟草养分综合管理[M].北京:科学出 版社,2008.[Chen Jianghua.Integrated Management of Tobacco Soil and Tobacco Nutrients in China[M]. Beijing: Science Press, 2008.]   
[28]徐建华.计量地理学[M].第一版.北京:高等教育出版,2006: 81-83.[Xu Jianhua.Quantitative Geography[M].First Edition. Beijing: Higher Education Press,2006: 81-83.]   
[29] 陈留美,桂林国,吕家珑,等.应用主成分分析和聚类分析评价 不同施肥处理条件下新垦淡灰钙土土壤肥力质量[J].土壤, 2008,40(6): 971- 975.[Chen Liumei, Gui Linguo,Lyu Jialong, et al.Evaluation on soil fertility quality of newly cultivated light sierozem under different fertilization with methods of principal component and cluster analyses[J]. Soils,2008,40(6): 971-975.]   
[30]白由路,金继运,杨俐苹,等.农田土壤养分变异与施肥推荐[J]. 植物营养与肥料学报,2001,7(2):129-133.[Bai Youlu,Jin Jiyun,Yang Liping,et al.Variability of soil nutrients in field and fertilizer recommendation[J]. Journal of Plant Nutrition and Fertilizers,2001,7(2): 129-133.]   
[31] 刘继明,宋启亮,李芝茹,等.大兴安岭白桦低质林生态功能评 价指标的灰色关联聚类分析[J].东北林业大学学报,2012,40 (8): 112-115.[Liu Jiming,Song Qiliang,LI Zhiru,et al. Grey relation clustering analysis of evaluation indices of ecological functions of low-quality birch forests in greater Xing'an mountains afterreconstruction by different transformation methods[J]. Journal of Northeast Forestry University,2012,40(8): 112-115.]   
[32] 张新要,李天福,蒲文宣.不同有机质含量土壤饼肥用量对烤烟 产量及品质的影响[J].耕作与栽培,2015,35(5):24-26.[Zhang Xinyao,Li Tianfu,Pu Wenxuan.Effects of different cake fertilizer amount on yield and quality of flue-cured tobacco in soil of differ

I vigan ai uuitslJJ Iag auu uiuvauun,viJ, (5): 24-26.]   
[33] 许自成,王林,王金平.湖南烤烟化学成分与土壤有机质含量的 关系[J].生态学杂志,2006,25(10):1186-1190.[Xu Zicheng, Wang Lin, Wang Jinping.Relationships between chemical components of flue-cured tobacco leaf and soil organic matter content in Hunan Province of China Chinese Journal of Ecology[J] Chinese Journal of Ecology,2006,25(10): 1186-1190.]   
[34] 黄安,杨联安,杜挺,等.基于主成分分析的土壤养分综合评价 [J].干旱区研究,2014,31(5): 819-825.[Hang An, Yang Lian'an, Du Ting,et al. Comprehensive assessment of soil nutrients based on PCA[J]. Arid Zone Research,2014,31(5): 819-825.]   
[35] 田立文,祁永春,戴路,等.新疆南疆耕地土壤养分含量及其分 布特征评价—以阿克苏地区为例[J].核农学报,2019,34(1): 214-223.[Tian Liwen,Qi Yongchun,Dai Lu,et al.Evaluation of soil nutrient content and its distribution of cultivated land in south of Xinjiang: Taking Aksu Prefecture as an example[J]. Journal of Nuclear Agricultural Sciences,2019,34(1): 214-223.]   
[36] 袁宇尧,李颖德,任宇强,等.新疆阿拉尔垦区密植枣园土壤养 分含量调查与分析[J].塔里木大学学报,2016,28(3):1-6.[Yuan Yuyao,Li Yingde,Ren Yuqiang,et al. Survey and analysis of the soil nutrient in close planting jujube gardens in Alar area[J]. Journal of Tarim University,2016,28(3): 1-6.]   
[37] 张丹,罗格平,许文强,等.新疆耕地土壤养分时空变化[J].干旱 区地理,2008,31(2): 254-263.[Zhang Dan,Luo Geping,Xu Wenqiang,et al. Spatial-temporal change of soil nutrients of cultivated land in Xinjiang[J].Arid Land Geography,2008,31(2): 254-263.]   
[38] 陈彦.绿洲农田土壤养分时空变异及精确分区管理研究[D].石 河子：石河子大学,2008.[Chen Yan.Study on Spatio-temporal Variability and Definition of Management Zones of Soil Nutrients in Oasis field[D]. Shihezi: Shihezi University,2008.]   
[39] 孙亚洲.基于分类距离的土壤系统分类土族单元划分研究- 以河南省境内分布的主要土壤为例[D].郑州:郑州大学,2017. [Sun Yazhou. Classification of Soil Family based on Chinese Soil Taxonomy by Using Soil Taxonomic Distance: A Case Study of Soil in Henan province[D]. Zhengzhou: Zhengzhou University,2017.]

# Soil nutrient evaluation of cotton field based on distance clustering and K-means dynamic clustering

FAN Xianglong1²， LYU Xin1²， ZHANG Ze1²,， GAO Pan23, ZHANG Qiang¹2， YIN Caixial²， YI Xiang12   
(1. Key Laboratory of Oasis Eco-Agriculture,Xinjiang Production and Construction Group,Agriculture College of   
Shihezi Universit,Shihezi 832Oo3,Xinjiang,China;2.National and Local Joint Engineering Research Centerfor   
Agricultural Big Data of Xinjiang Production and Construction Corps,Shihezi 832Oo3,Xinjiang; 3.School of Information Science and Technology,Shihezi University,Shihezi 832OO3,China)

Abstract: This study used principal component analysis combined with distance clustering, K-means dynamic clustering,and comprehensive soil nutrient evaluation methods to analyze and evaluate the soil nutrient status of coton field soil in Xinjiang， China.The resultsshowed that the available copper,manganese，and alkali hydrolyzable nitrogen played a major role principal component analysis: The available copper content was high （2号 $( 1 . 8 2 ~ \mathrm { m g \cdot k g ^ { - 1 } } )$ ; the available manganese content was low $( 1 1 . 3 6 ~ \mathrm { m g \cdot k g ^ { - 1 } } )$ ; and the alkali hydrolyzable nitrogen content was $1 2 2 . 0 7 ~ \mathrm { m g \cdot k g ^ { - 1 } }$ . The available phosphorus,potassium, zinc and iron contents were low. Thus, the distribution of soil nutrients was uneven.In the distance clustering and K-means dynamic clustering,the organic mater,available nitrogen,and available manganese contents were lower, whereas the other nutrient contents were higher.In the distance cluster, the soil nutrients could be expressed as: class $\mathrm { ~ I ~ } >$ class $\mathrm { v } >$ class $\mathrm { I V } >$ class $\mathrm { I I } >$ class IIl, whereas the soil nutrients could be expressed in the K-means dynamic cluster as: class $\mathrm { I I I } >$ class $\mathrm { I } >$ class $\mathrm { v } >$ class $\mathrm { I I } >$ class IV. In the comprehensive evaluation of soil nutrients (IFI), the grades of 1 and 16 are higher.The second company,third company,fourth company,sixth company,15th company,19th company,and the second prison area had higher levels,whereas the8th,9th,10th,11th,12th,17th,18thand 20th companies were in the middle level.The grades of companies 5,7,and 1 supervision district and agricultural city station were lower.Thus,K-meansdynamic clustering is beter than distanceclustering,as itcanbe more scientific,reasonable, accurate,and effective for the comprehensive evaluation of soil nutrients.

Keywords: soil nutrients; distance clustering; K-means dynamic clustering; comprehensive evaluation value