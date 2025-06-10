# 基于GIS的天山北坡聚落地名文化景观分析

王盼1²，王宏卫1²，杨胜天1,2.3，隋学佳²，刘枝军1,2（1新疆大学资源与环境科学学院,新疆乌鲁木齐830046;2绿洲生态教育部重点实验室,新疆乌鲁木齐830046；3北京师范大学水科学研究院,北京100875）

摘要：通过利用地理信息手段对新疆天山北坡的地名文化景观进行可视化分析,将不同类型的地名进行分类，共分划分出了兵团类、自然类、工（宫)运类、民族类、数字类、姓氏类、直属类、移民类与其他类地名共9种类型。在此基础上，利用GIS技术将点状化的地名进行分类分层和核密度分析,将不同类型的地名集聚和分布状况进行可视化分析，着眼于新疆天山北坡的历史、经济、自然、民族文化等情况，对不同类型的地名集聚和分布状况进行分析，研究发现该区域地名整体较集中地分布在南部天山与北部沙漠盆地之间的几个绿洲城镇集群附近，其余9种类型地名除直属类分布较离散外，其他类型基本都分布在中部绿洲条带线上，呈现出各自历史情况、经济条件、自然特征和包括屯垦、民族、移民以及新疆地域文化特色规律的分布特征。

关键 词：天山北坡；地名文化景观；核密度分析；新疆

# 文章编号：

地名是人们赋予某一特定空间位置上自然或人文地理实体的专有名称，一般会受到自然地理条件、语言文化、政治体制、人口民族等的影响。研究地名文化的景观布局分析，不仅要考虑到地理条件的影响，其间还会涉及到历史学、语言学、民族文化学、人类学等相互交织的影响,通过对一块地域的地名文化分析，可以在一定程度上了解到该地区较长历史阶段内的变迁。国外关于地名方面的研究一直在发生着变化，起步阶段的定性分析方法在传统地名研究中最普遍采用描述、记述等方法研究地名的起源、演变、语源、类型划分、地名群和反映的自然与社会文化现象等[1]。从20 世纪90 年代至今,计算机技术优化传统研究手段与方法在国外地名研究中逐渐应用，积累了定量分析的研究方法。如运用GIS 技术、计算机技术及其他定量分析方法对民族地名、殖民地名等方面的研究，运用定量分析方法的同时也结合传统文化地理来进行研究。 $\mathrm { J E T T } ^ { [ 2 ] }$ 对美国亚利桑那州纳瓦霍锡安峡谷和青利大峡谷地区的地名与环境和人们生活观念的关系进行系统研究。

SANDRED[3]研究变化着的社区内地名元素的改变状况。GILL[4]深入探讨莫斯科地名革新。HER-$\mathrm { M A N } ^ { [ 5 ] }$ 展示了夏威夷岛上的原地名服从于西方殖民列强和被取代的历史。 $\mathrm { Y E O H } ^ { [ 6 ] }$ 通过对民族独立后的新加坡城市街道命名分析，揭示出国家意识形态对地名文化的影响。POST等[7通过资本、教会和经济发展解释了一战时期新柏林的地名变化。

国内关于地名文化地理方面的研究始于20 世纪80年代，起步阶段的地名研究主要采用描述的方法来对地名文化布局以及其影响因素进行分析。孙东虎[8利用描述的方法对华北平原地区城镇地名历史演变和位置驱动因素进行了分析，并对未来发展趋势进行了预测。宋长栋和王颖[9-10]研究了民族地区或者民族学与地名学研究的关系。司徒尚纪等[11-13]研究了地名文化景观与历史、民族等因素条件的交互影响。进入21世纪，随着GIS技术的发展，越来越多的专家学者将信息技术引入了人文气息十足的地名文化景观,利用新技术让传统研究更加具有生机活力。王彬等[14-15]先后利用GIS技术建立数据库和利用经验正交函数（EOF)对原始资料矩阵作标准化处理。李建华等[16]利用GIS 方法探析了农牧交错带地区多文化交融的中卫县地名文化景观的分布特征以及驱动因素。王法辉和孙百生等[17-18]对广西壮语地名分布和承德地区乡村地名进行可视化展示，分析不同影响因素和地名景观之间的相关性。陈晨等[19]利用核密度估计法(KDE)可视化了北京市地名集聚特征，并各种分类进行了历史方面的分析。

![](images/632d6732aaa201d7cd3e16e545e1074177c459742bdc0f6c7292b7cc32362f26.jpg)  
王盼等：基于GIS的天山北坡聚落地名文化景观分析  
图1天山北坡研究区示意图  
Fig.1Map of the north slope research area of Tianshan Mountains

新疆地理条件复杂多样，境内有山脉、戈壁荒漠、冲积扇绿洲、丰富的矿产资源以及各类型水系和气候带以及我国最长的边境线。同时作为典型的多民族与多文化聚居区，其在地名的分布布局方面也有会有着比较强的地域特征。而目前关于新疆地理的研究多集中于自然地理方面，人文地理尤其是文化地理方面的研究较少，但新疆的历史悠久，且位于亚欧大陆中心和“一带一路”核心区，文化交互融合，有着丰富的历史文化资源，对新疆地区的地名文化开展研究有着十分重要的意义。

# 1研究区概况与数据来源

天山北坡地区有着新疆最大的连片绿洲，同时也是新疆经济最为发达的地区[20]。其内部包含有乌鲁木齐市与昌吉回族自治州全境、伊犁哈萨克自治州奎屯市、塔城地区沙湾县和乌苏市、克拉玛依市区与独山子区以及新疆生产建设兵团第六师五家渠市、第七师、第八师石河子市和第十二师(图1），其内部共有2473个聚落地名。该地区南靠天山主脉，北望准噶尔沙漠盆地,经济生产和人口生活基本集中于天山脚下的冲积扇绿洲平原，

首先收集天山北坡地区2016年更新调整后的共22个县区市矢量化的地、县、乡、村四级行政区划名称。其中，地州市一级地名共3个，县市区一级地名共22个，乡镇和兵团农牧团场一级地名共298个，村和连队一级地名共2150个。聚落地名一般是在长时间内受到当地的自然地理风貌、政治军事变动、民族文化差异以及其他因素造成的，具有一定历史跨度和依据，在一定程度上这些地名能够反映当地长时间以来的自然人文变化[19]。但是研究区内还有一些城市，例如乌鲁木齐、昌吉、克拉玛依、奎屯等，其建成区内部也密集地布局着一些由于城市发展新产生的小区、街道和单位名称，这些地名不属于本次研究的范畴，未在统计之列。

# 2研究方法

阅读借鉴其他有关研究在地名分类方面的成果，确定具有新疆和天山北坡地区特色的地名分类标准；将所获取的研究区地名矢量图层进行转点化处理,利用GIS中的核密度分析（KernelDensity A-nalysis），得到天山北坡地区整体和其余9类地名核密度分布图，进而从空间可视化与量化角度分析天山北坡地区地名文化景观的空间分布特征。

查阅大量有关新疆的历史资料和科研文献，根据该地聚落地名的由来，分析造成不同类型地名文化景观空间分布的形成原因。

# 2.1 密度分析法

利用密度分析方法计算各类地名的密度，可以看出该地区的各类不同地名的整体密集程度。地名密度是指研究区单位面积内聚落地名的数量，公式如下：

$$
D = { \frac { n } { A } }
$$

式中： $D$ 指聚落地名的密度； $n$ 指该类型的聚落地名数量； $A$ 指研究区面积

# 2.2核密度估计法(KDE)

采用基于核密度估计法的空间平滑法分析天山北坡地区地名文化景观特征，丰富了地名文化景观的研究方法。核密度估计法（KDE)充分地体现了地理学的距离衰减规律，距离较近的对象，权重较大。这种方法在分析和显示点数据时极其有用。离散点数据如果直接用图表示，往往难以直观并定量分析其空间趋势。核密度估计法可以得到研究对象密度变化的图示，空间变化是连续的，又有“波峰”和"波谷"强化空间分布模式的显示，可以客观准确地表达地名点的空间分布状况[21]

核密度方程的几何意义为：密度分布在每个 $x _ { i }$ 点中心处最高，向外不断降低，当距离中心达到一定阈值范围(窗口的边缘)处密度为0。网格中心处的核密度为窗口范围内的密度和：

$$
f ( x ) \ = \ { \frac { 1 } { n h ^ { d } } } \sum _ { i = 1 } ^ { n } K { \bigg ( } { \frac { x - x _ { i } } { h } } { \bigg ) }
$$

式中： $K ( \mathbf { \theta } )$ 为核密度方程； $h$ 为阈值; $n$ 为阈值范围内的点数； $d$ 为数据的维数。

例如，当 $d { \bf \Psi } = 2 { \bf \Psi }$ 时,一个常见的核密度方程可以定义为：

$$
f ( x ) = { \frac { 1 } { n h ^ { 2 } \pi } } \sum _ { i = 1 } ^ { n } \left[ 1 - { \frac { ( x - x _ { i } ) ^ { 2 } + ( y - y _ { i } ) ^ { 2 } } { h ^ { 2 } } } \right] ^ { 2 }
$$

式中： $\left( x - x _ { i } \right) ^ { 2 } + \left( y - y _ { i } \right) ^ { 2 }$ 为 $( x _ { i } , y _ { i } )$ 和 $\displaystyle { \big ( } x , y { \big ) }$ 之间的离差。

# 3地名分类分析

根据天山北坡实际情况，本研究将该地区的聚落地名划分为兵团类、自然类、工（宫）运类、民族类、数字类、姓氏类、直属类、移民类与无明显分类的

其他类(表1)。

兵团类：兵团地名具有极强的军事指令性，多出现“师”“团”“农场”、“ $^ { * * }$ 牧场”、“连”等字。这与新疆的实际情况有着极强的关联，建国初期，驻疆部队响应国家号召，就地转业，由战斗性质转变为农业生产性质，以后经过多次建制调整和兵团撤销与重建,依然保留着“ $^ { * * }$ 师”、“ $^ { * * }$ 团”“ $^ { * * }$ 农场”、“ $^ { * * }$ 牧场”、“\*\*连"的番号。而这些番号则作为地名存在于该地区,且一般以数字、自然地理情况、政治宣传为代号，例如“新疆生产建设兵团第十二师”、“130 团”、“芳草湖农场”、“共青团农场”、“7连"等。天山北坡地区集聚了兵团第六师、第七师、第八师、第十一师(建工师)和第十二师共五个师、数十个农牧团场、数百个连队[22]

自然类：该地区地理条件复杂，绿洲内有河流水库,外有高山、沙漠、各种隘口达坂等，在地名命名时，会依据当时当地的地理情况进行命名。例如：七道湾、碱泉村、金沟河村等[23]

工(宫)运类：古代时期,新疆一直是中原王朝关注的重点区域，当地驻军会在驻守区域进行聚落建设和开垦土地，留下了由数字连起来类似于番号且带有“工（宫)”、“运"等特色字眼的地名[24]

民族类：新疆尤其是天山北坡一带，自古以来就是多民族聚居区，有维吾尔族、哈萨克族、回族、塔塔尔族等，他们在他们聚居的地方，会有着自己民族语言的地名，后来经过音译为汉语后，依然保留着自己的民族特色[25] 。

数字类：在古代，新疆人口较少，居住零散，在该地区命名上就直接采用了当地的地理特征进行命名。例如,在乌鲁木齐北部约 $3 0 ~ \mathrm { k m }$ 处，清末民初有杨、冯、杜等5户人家，为种地从老龙河引出一条水渠，人称“五家渠”，一直采用到现在。

姓氏类：这个主要是由居住于当地居民的主要姓氏或最早居住于该地的人口姓氏来进行命名。

移民类：新疆地广人稀，自古以来就是内地屯田移民的重点地区，有些地名就以移民的来源地命名，例如：“肃州户村”、“湖南村”、“河南村”等。

直属类：由于该地区南侧为天山山脉，北侧为古尔班通布特沙漠，大多人迹罕至，没有居民点，一般为县区市或者乡政府直属，没有自己特定的地名。

其他类：其余的没有明显统一特征的地名归类为其他类地名。

# 表1各类型地名分类统计

Tab.1Classification and statistics of various types of geographical names   
表2各类地名总占比以及密度  

<html><body><table><tr><td>地名类型及占比</td><td>主要用字</td><td>示例</td></tr><tr><td>兵团类(37.40%）</td><td>师、团、农场、牧场、连</td><td>第八师、130团、221团、新湖农场、六运湖农场、北塔山牧场、7连、畜牧连、园林连</td></tr><tr><td>工(宫)运类(3.19%）工、宫、运</td><td></td><td>二工、头工、皇宫、西五工、下三工、三工庙、三宫店、八运、九运、西八运、五运南</td></tr><tr><td>数字类(2.30%）</td><td>户、里、分、份、家、棵、个</td><td>十户村、三个泉子、二十里店、十户窑、八分地村、十坪口村、七户地、十二份村、三 棵树</td></tr><tr><td>自然类(29.76%）</td><td>风、达坂、碱、岔、塔、场、地</td><td>湾、沟、渠、泉、湖、坡、河、梁、石、七道湾、五家渠、山丹湖、河沿、仓房沟、树窝子、大草滩、乱山子、黄土梁、西沙坝、 洞、沙、滩、崖、树、水、山、坝、窝、西阴沟、钻洞子渠、闸滩村、榆树沟、羊头泉子、盐池村、鸭洼坑村、新桥湾、泄水渠 村、小海子村、下野地、小拐、下大草滩、西树窝子、苇湖村、天山村、水西沟、双河、 上沙河</td></tr><tr><td>姓氏类(5.13%）</td><td>黄、方、陈、周、孙、沈、包、邓、党庄、罗家庄子、周家塘、杨家道、吴家梁、潘家台子、马家槽子</td><td>王、李、张、葛、何、丁、曹、郭、胡、王家渠、葛家沟、张家庄、李家坪、陈麻子、胡家海子、邓家湖、曹家沟、杨李庄、徐家</td></tr><tr><td>民族类(5.78%）</td><td></td><td>萨、努、阿、托、博、勒、乌、柯、喀、霍霍斯阿尔克村、博尔通古村、克孜勒阿根村、喀拉巴斯陶村、乌兰祖胡村</td></tr><tr><td>移民类(0.68%)</td><td></td><td>凉州、湖南、广东、陕西、肃州、河南凉州户、湖南村、广东庄子、陕西工、肃州户、河南庄</td></tr><tr><td>直属类(4.21%）</td><td>直属</td><td>沙湾县直属、博尔通古乡直属、柳毛湾镇直属、奇台县直属</td></tr><tr><td>其他类(13.30%）</td><td>丰、团结、向阳、和平、青年、昌德</td><td>联丰村、团结村、向阳街道、和平新村、青年村、昌德村</td></tr></table></body></html>

Tab.2Total proportion and density of all kinds of place names   

<html><body><table><tr><td>地名类型</td><td>全部</td><td>兵团类</td><td>自然类</td><td>工(宫)运类</td><td>民族类</td><td>数字类</td><td>姓氏类</td><td>移民类</td><td>直属类</td><td>其他类</td></tr><tr><td>占比／%</td><td>100.00</td><td>37.40</td><td>29.76</td><td>3.19</td><td>5.78</td><td>2.30</td><td>5.13</td><td>0.68</td><td>4.21</td><td>13.30</td></tr><tr><td>地区密度个／10²km²</td><td>2.049</td><td>0.766</td><td>0.609</td><td>0.065</td><td>0.118</td><td>0.047</td><td>0.105</td><td>0.014</td><td>0.086</td><td>0.273</td></tr></table></body></html>

# 4总体与各类地名景观核密度空间分布特征及其成因分析

# 4.1地名分布总体特征及其成因

从表2可以得知，天山北坡地区地名整体布局稀疏,每 $1 0 0 \ \mathrm { k m } ^ { 2 }$ 内仅有2.049个聚落地名，兵团类、自然类和其他类地名占比较大，其余6类地名数量和比例都较小。图2显示聚落地名主要分布在山前冲积扇平原绿洲地区，北部古尔班通古特沙漠地区地名分布零散稀疏，仅有少量地名分布，南部天山山地地名分布同样也较为稀疏零散，其核密度均为0.04以下，为最低值分布区域;且以乌鲁木齐—昌吉一阜康一带为分布核心区，地名分布最为密集，最高处达到 $0 . 1 6 \sim 0 . 1 9$ 之间；在玛纳斯河流域上游石河子市区、沙湾县城和玛纳斯县城一带以及下游垦区出现 $0 . 1 2 \sim 0 . 1 5$ 的次高值;在乌苏市四棵树镇附近、沿奎屯河干线一带、玛纳斯河流域以及奇台县城一带出现 $0 . 0 9 \sim 0 . 1 1$ 的较高值;除这些区域外的冲积扇平原绿洲地名核密度基本都在 $0 . 0 5 \sim 0 . 0 8$ 之间，呈现出较为均匀分布的态势。

由于乌一昌一阜一带是天山北坡地区乃至全新疆经济最为发达，人口和二三产业布局最为密集的区域,所以地名在此最为密集;玛纳斯河是整个北疆年径流量最大的一条河流，且该流域聚集了石河子市、玛纳斯和沙湾县城,作为一个初有规模的城镇圈，足够有能力和需求来供养起较多的人口和产业，因此在玛纳斯河流域一带会出现次于乌一昌一阜一带较高的地名密度;同样由于受到奎屯河、四棵树河较大年径流量的供给和昌吉东部地区人口经济核心一奇台县城的带动，在奎屯河、四棵树河沿线和奇台县城一带形成了地名分布密度较高区域。

![](images/a2847b63743d5eece5aae5a575e37dca6058cf9c7cd9df9a23b8e84dbddfe64e.jpg)  
图2研究区地名景观核密度分布  
Fig.2Distribution of land name landscape kernel density in the study area

# 4.2各类地名分布特征及其成因

4.2.1兵团类地名分布特征及其成因兵团类地名基本与其规模较大的农业垦区相叠加吻合，大部分位于该地区西部绿洲下游地区，密度核心区很难与主要交通线保持耦合（图3a）。在0.021\~

0.093之间的地名密度较高区域自西向东分别为第七师车排子垦区、奎屯垦区，第八师下野地垦区、莫索湾垦区、石河子垦区，第十二师三坪垦区、乌鲁木齐垦区，第六师芳新垦区、五家渠垦区、奇台总场。

兵团垦区大部分位于天山北坡西部地区，因此在西部地区会呈现出几个较高密度地名的分布区域。这个情况与兵团的历史情况有关，兵团在新疆是以天山北坡中西部的石河子为中心进行屯垦戍边，发展至今，天山北坡地区西部地区布局有第七师、第八师、第十二师和第六师的大部分，东部地区仅有第六师的奇台总场，因此在兵团地名的分布上，基本呈现西部多且密集，东部少且稀疏的态势。在当地，兵团属于后来者，所占据的皆是当地居民经过长时间生产生活后来不及或放弃垦种的土地，一般位于内流河下游区域且远离当地经过长时间形成的主要交通带。

![](images/d80ba7ac5322021743bf3421fb1165b0bacff99e1b4c2b4c1b82a8f9d40e3731.jpg)  
4.2.2自然类地名分布特征及其成因自然类地名大部分分布在该地区天山山前冲积扇和较大河流  
图3各类地名景观核密度分布  
Fig.3Kernel density distribution of various geographical names

流域沿线,其中以乌一昌一阜一带和玛纳斯河流域一带为 $0 . 0 3 4 \sim 0 . 1 0 1$ 的高密度核心区;以奎屯河流域一带、玛纳斯河山间上游区域、乌鲁木齐河上游区域和吉木萨尔县与奇台县山前冲积扇为 $0 . 0 1 8 \sim$ 0.058的次高密度核心区；以 $0 . 0 0 6 \sim 0 . 0 1 7$ 的次低值密度区则漫布于该地区的连片冲积扇区域；另外在南部、西北部和东北部也有零散分布（图3b）。

自然类的地名大部分分布在山前冲积扇和较大河流流域沿线，这与当地的实际自然地理情况有关，山前冲积扇和河流沿线自然地理状况和地形地貌较为复杂，坡度和海拔降幅较大,其地名会更倾向于以自然地理实体命名，例如：湖西村位于沙湾县蘑菇湖以西 $3 ~ \mathrm { k m }$ 处，则以蘑菇湖水库为命名对象;沿着沙湾县金沟河自上游到下游分布有头道河子、二道河子、三道河子、四道河子与五道河子，自然类地名的空间布局基本与当地自然地理状况吻合。

4.2.3工(宫)运类地名分布特征及其成因工(宫)运类地名基本沿着山前冲积扇区域的主要交通线布局,其中以乌一昌一阜一带、石河子—玛纳斯一带为 $0 . 0 0 6 \sim 0 . 0 3 1$ 的高密度分布区,以沙湾一乌苏一带和奇台一吉木萨尔一带为 $0 . 0 0 2 \sim 0 . 0 1 1$ 的次高密度分布区。横向分布较为密集，高密度区呈现珍珠链状沿山前冲积扇的交通线分布（图3c）。

工(宫)运类地名高密度区沿着山前冲积扇区域的主要交通线布局，这与当地的历史情况有关。清乾隆中期，新疆驻军受清廷命令，在东自木垒县，西到乌苏一带，筑城建堡，屯田储粮，当时这片王地为"皇工"屯田之所在,按顺序为“头工”、“二工”等等，后来由于历史流传，由“工”演变出“宫”，出现“皇宫镇”等的地名称呼;光绪初年,左宗棠来新疆平叛阿古柏，在现今阜康市九运街道一带屯过兵，西征军基本上为湘军,按湖南方言，将士们将“营”说成了“运”的音，当地老百姓也跟着称呼，久而久之形成固定的地名，即五运、六运、七运、八运、九运、十运为序列的村名。清朝时期，对河流水资源利用率不高再加上当时的人口稀疏，没有足够的需求大量开垦土地，可供人类生产生活的绿洲规模较现在小的很多，一般位于山前地区，那么地名布局也会沿着当时的有着交通线的山前地区进行布局。

4.2.4民族类地名分布特征及其成因民族类地名在该地区山前冲积扇和山区都有核密度为0.003\~0.007较稀疏的分布，但范围较广;在乌苏市古尔图一四棵树河流域、沙湾县金沟一巴音沟河上游区域和奇台县与木垒哈萨克自治县一带有着 $0 . 0 0 8 \sim$ 0.062之间的高值分布，分布范围不大，较为集聚（图3d）。

民族类地名与少数民族聚居有关，天山北坡地区有着包括哈萨克族、回族、维吾尔族、蒙古族等的少数民族分布，一般以牧业为主要产业，主要分布在山前冲积扇上端，紧靠山区，利于夏秋游牧和春冬定牧；而尤其在乌苏市古尔图一四棵树河流域的古尔图镇、吉尔格勒特郭楞蒙古族乡、塔布勒合特蒙古自治乡、沙湾县金沟一巴音沟河流域的博尔通古乡、牛圈子牧场、博尔通古牧场、奇台县坎儿孜乡、五马场哈萨克族乡和木垒哈萨克族自治县等少数民族聚居的县乡是民族类地名核密度的高值区。

4.2.5数字类地名分布特征及其成因数字类地名核密度高值分布在乌鲁木齐一昌吉一带最为密集，其整体基本上保持着沿天山山脉冲积扇呈横向分布，但在一定程度上与主要交通带保持着一定的距离（图3e），最高值为0.013，说明整体保持在较低的密度水平。

其成因与数字类命名条件有关，古代西北地区尤其是新疆地区，地广人稀，人口大部分都集聚在具有较好水资源条件和交通条件的山前冲积扇平原绿洲，在明清和近代时期，随着人口的增加和移民屯垦，开始在冲积扇平原绿洲下游地区和稍远离交通干线的地区进行屯垦生产，就以刚开始居住于当地的户数或者当地具有数量特征的地理情况为地名，例如：“五家渠”“十三户”“三个泉子”“三棵树”等。

4.2.6姓氏类地名分布特征及其成因姓氏类地名最密集的区域为沙湾县老沙湾镇以及玛纳斯县城附近，核密度范围基本保持在 $0 . 0 1 9 \sim 0 . 0 4 6$ 之间，其余几个次密集区分别位于乌苏市、沙湾县、石河子市、阜康市等几个县市城镇区域附近以及乌鲁木齐市北郊,核密度范围在 $0 . 0 0 9 \sim 0 . 0 1 8$ 之间,另外在吉木萨尔县城、木垒哈萨克自治县城和乌鲁木齐市达坂城区附近也有着 $0 . 0 0 3 \sim 0 . 0 0 8$ 的较高密度分布区(图3f)。

姓氏类的地名分布代表着该地由某一姓氏占据主要地位，一般是由最早居住于该地的居民姓氏或者由该地姓氏比例中较大或者最大的姓氏来进行命名。主要是汉族居民，大部分形成较早，一般位于水土条件和交通经济较好的地区，这样的区域也有利于城镇的产生，所以姓氏类的地名一般距离当地的市镇较近，布局在市镇周围。

4.2.7移民类地名分布特征及其成因移民类地名主要集中分布在乌鲁木齐一昌吉一带与石河子—玛纳斯一带，核密度范围为 $0 . 0 0 4 \sim 0 . 0 0 7$ ,另外在主要交通带附近也有零散分布（图 $3 \mathrm { g }$ ）。

移民类地名的形成通常是因为最早聚居此地的移民来自同一迁出地而得名，这与当时的历史情况有关系，自清乾隆时期至抗日战争期间的多次战乱使得内地居民形成了新疆移民潮，其中也主要以甘肃、陕西为主要迁出地，移民类地名中来自甘肃和陕西的地名超过了 $5 0 \%$ ,例如：“凉州户”、“肃州户”、“陕西工”、“渭户”等。另外还有不少来自河南、湖南、广东、青海的地名，如：“河南庄”、“广东户”、“湖南村”、“青海村”等。

移民地名现象体现了移民以祖籍地地缘关系进行组合的社会结构特点。天山北麓移民社会形成过程中，清政府与民国政府都曾招募和组织进行移民，许多移民来自同一地区，集中行动，到达新疆后又被集中安置。这样就形成了来自不同地区的移民地名有着自己的空间集聚特征，来自甘肃的移民地名基本都分布在中部偏西即乌鲁木齐以西地区，来自广东、湖南、河南的移民地名则主要分布在乌鲁木齐周边，来自陕西、青海的移民地名则分布较为零散，东部和乌鲁木齐周边都有分布。

4.2.8直属类地名分布特征及其成因直属类地名全区分布都较为零散，仅在昌吉市的天山山区形成了一个 $0 . 0 0 7 \sim 0 . 0 1 2$ 的密度高值区（图3h）。

直属类地名是西北地区尤其是新疆地区的一个地名特色，由于中部为适宜生产生活的绿洲,南边有天山，北部有沙漠，都是人迹罕至的地方。没有或者很难有人在此长期集聚，难以产生地名，因此一直是县乡两级政府的直属地。

4.2.9其他类地名分布特征及其成因其他类地名也基本上遍布整个地区，乌鲁木齐一昌吉一呼图壁一玛纳斯一石河子一带形成了0.020以上的较高密度区，其中尤以昌吉一带形成了 $0 . 0 5 2 \sim 0 . 1 6 0$ 的高密度分布区（图3i）。

其他类的地名分布布局就没有太多的分类规律可循，人口较多经济发达的区域地名较为密集，这样难以归类的其他类地名也较多一点。乌鲁木齐一昌吉一呼图壁一玛纳斯一石河子一带就是天山北坡地区的人口较多经济较发达的核心区域，因此其他类地名也在此呈现集聚特征。

# 5结论与讨论

通过对新疆天山北坡地区聚落地名进行分析，基本反映出了具有新疆地域特色的聚落地名文化景观分布与其历史政治、自然、经济人文、民族文化等的关联，充分体现了作为多元文化交融区的新疆在地名文化上的多样性。

天山北坡地区地名景观一般以社会经济人文各类型为主，自然类地名比例较低，各类聚落地名文化景观布局有着各自的特点。兵团类地名主要分布在西部即乌鲁木齐以西地区，位于绿洲下游且远离主要交通带，这与历史条件对兵团屯垦的限制基本对应。自然类地名大部分位于冲积扇上游和较大河流流域沿线，这与冲积扇上游和河流干流附近自然地理类型变化多样有关。工(宫)运类地名的布局与绿洲的历史开发条件有关，一般沿冲积扇中上游的主要交通带分布。本地区位于北疆，少数民族以山区或者山前游牧民族为主，其地名分布也基本与民族分布构成保持一致。数字类地名一般是由开发初期的自然与人文景观来命名，一般位于绿洲下游地区且稍远离交通干线。姓氏类地名由于形成较早，一般位于水土条件和经济交通较好的城镇附近。移民类地名一般有同乡集聚的特点，来自同一地区的移民一般集聚在一起，地名来源自甘肃、河南、广东、陕西等省区的都有着自己较为密集地居住区。由于新疆有着很多难以利用的土地，这些土地上人迹罕至，难以产生人为地名，一般由当地基层人民政府直属。其他类地名没有特别明显统一的特点，几乎全区都有分布，在经济较为发达的乌昌地区较为密集。

通过对新疆天山北坡地区各类地名景观布局的分析，可以反映出较长历史时间段内新疆尤其北疆地区的社会经济历史与自然状况，能够在一定程度上印证新疆自古以来就是中国的一部分。

本研究只分析了占新疆总面积 $7 . 2 \%$ 的天山北坡的地名文化景观，研究的区域面积较小且地域单一，同时作为新疆最大特色的民族地名文化并未得到较为深入的研究。例如，南疆四地州的维吾尔族语言文化区、以哈萨克族和蒙古族为代表的游牧民族语言文化区等，因其地名的汉语表达基本为音译，读音不仅冗长而且难以看出其发音之外本身的自然文化含义，例如，喀什地区莎车县拍克其乡下属的“库木艾日克"维吾尔语意译为“沙漠中的水渠”，博尔塔拉蒙古自治州博乐市下属的“乌图布拉格”蒙古语意译为“长长的泉水”[26]。希望能够在以后的研究中能够突破这一问题，建立少数民族聚居地地名意译数据库，在这个意译数据库的基础上，再根据当地的历史、自然、民族文化等等情况深一步研究民族地名的类型、分布状况，为深入研究新疆地名文化做好准备。

# 参考文献(References)

[1]KEARNS A,BERG L D .Proclaiming place;Towards a geography of place name pronunciation[J].Social & Cultural Geography, 2002,3(3):283-302.   
[2]JETT S C.Place-naming,environment,and perception among the Canyon de Chelly Navajo of Arizona[J].Professional Geographer, 1997,49(4) :481 -493.   
[3]SANDRED K I. English stead-a changeable place-name element in a changing community[J].Studia Neophilologica,2Oo1,73（2）： 164 -170.   
[4]GILL G.Changing symbols:The renovation of Moscow place names [J].Russian Review,2010,64(3）:480 -503.   
[5]HERMAN R D K.The Aloha State:Place names and the anti-conquest of Hawaii[J]. Annals of the Association of American Geographers,2015,89(1) :76 -102.   
[6]YEOH B S A. Street-naming and nation-building: Toponymic inscriptions of nationhood in Singapore[J].Area,2015,28(3）:298 -307.   
[7]POST C W,ALDERMAN D H.“Wiping New Berlin off the map”: Political economy and the de-Germanisation of the toponymic landscape in First World War USA[J].Area,2014,46(1):83 -91.   
[8］孙冬虎.华北平原城镇地名群的发展及其地理分布特征[J]. 地理研究,1990,9（3）:49-56.［SUN Donghu.Development and geographical distribution of the colony of town names in the North China Plain[J].Geographical Research,1990,9(3）:49 -56.]   
[9］王颖.乌鲁木齐地区地名与地理要素的关系[J].新疆大学学 报（自然科学版）,1985,（2）:40-44.[WANG Ying.A primary research on the relationships between the geographic names of Urumqi and its geographic elements[J]. Journal of Xinjiang University （Natural Science Edition）,1985,（2）:40 -44.]   
[10］宋长栋.地名学与民族学研究[J].中山大学学报（哲学社会科 学版）,1987,（3）:66-75.[SONG Changdong.Toponymy and ethnology research[J].Journal of Sun Yatsen University Social Science Edition,1987,(3）:66-75.]   
[11］司徒尚纪.广东地名的历史地理研究[J].中国历史地理论丛， 1992,（1）:21-55.[SITU Shangji.A historical geography study on toponomy in Guangdong Province[J]. Journal of Chinese Historical Geography,1992,（1）:21-55.]   
[12］张力仁.地名与河西的民族分布[J].中国历史地理论丛， 1998,(1）:207-214.［ZHANG Liren.Place names and ethnic distribution in Hexi[J].Journal of Chinese Historical Geography, 1998,(1) :207 -214.]   
[13］阚耀平.近代天山北麓人口迁移形成的地名景观[J].干旱区 地理,2005,28（6）:869-873.[KAN Yaoping.The placename landscape formed by immigration in the northern piedmont of the Tianshan Mountains in the modern times[J].Arid Land Geography,2005,28(6):869 -873.]   
[14］王彬,司徒尚纪.基于GIS 的广东地名景观分析[J].地理研 究,2007,26(2）:238-248.[WANG Bin,SITU Shangji. Analysis of spatial characteristics of place names landscape based on GIS technology in Guangdong Province[J].Geographical Research, 2007,26(2):238 -248.]   
[15］王彬,岳辉.GIS 支持的广东地名景观EOF 模型分析[J].地理 科学,2007,27（2）:281-288.[WANG Bin,YUE Hui.EOF model analysis of place names landscape in Guangdong Province on GIS[J].Scientia Geographica Sinica,2007,27(2）:281-287.]   
[16］李建华,米文宝,冯翠月,等.基于GIS 的宁夏中卫县地名文化 景观分析[J].人文地理,2011,26（1）：100－104.［LI Jianhua, MI Wenbao,FENG Cuiyue,et al．An analysis on toponym cultural landscape based on gis application in Zhongwei County,Ningxia Municipality[J].Human Geography,2011,26(1）:100-104.]   
[17］王法辉,王冠雄,李小娟.广西壮语地名分布与演化的GIS 分 析[J].地理研究,2013,32（3）：487－496.[WANG Fahui, WANG Guanxiong,LI Xiaojuan. GIS-based spatial analysisof Zhuang place names in Guangxi,China[J].Geographical Research,2013,32(3):487-496.]   
[18］孙百生,郭翠恩,杨依天,等.基于GIS 的承德乡村地名文化景 观空间分布特征[J].地理科学,2017,37（2）:244－251.[SUN Baisheng,GUO Cuien,YANG Yitian,et al. Spatial distribution characteristics of rural place-name cultural landscape based on GIS approach in Chengde[J].Scientia Geographica Sinica,2017,37 (2) :244 -251.]   
[19］陈晨,修春亮,陈伟,等.基于GIS 的北京地名文化景观空间分 布特征及其成因[J].地理科学,2014,34（4）：420－429. [CHEN Chen,XIU Chunliang,CHEN Wei,et al.Spatial distribution characteristics of place names landscape based on GIS approach in Beijing and itsreasons for the formation[J].Scientia Geographica Sinica,2014,34(4） :420 -429.]   
[20］石天戈,张小雷,杜宏茹,等.天山北坡经济带固定资产投资特 征及其对城镇集聚的影响[J].干旱区地理,2013,36（1）：176 -185.[SHI Tiange,ZHANG Xiaolei,DU Hongru,et al. Characteristics of fixed asset investment and influence to urban agglomeration in the economic belt on the northern slope of Tianshan Mountains[J].Arid Land Geography,201336(1):176-185.]   
[21］王法辉.基于GIS 的数量方法与应用[M].北京:商务印书馆, 2011,47 - 70.[WANG Fahui. Quantity method and application base on GIS[M]. Beijing:Commercial Press,2011,47-70.]   
[22］《新疆生产建设兵团的历史与发展》白皮书[R].北京：中华人 民共和国国务院新闻办公室,2014.[White paper on the history and development of the Xinjiang production and construction corps [R].Beijing:The State Council Information Office of the People's Republic of China,2014.]   
[23］徐金发,杨政,张洁.天山北坡自然地理特征对河流产汇流影 响的研究[J].新疆大学学报（自然科学版),1994,11（3）:92 -98，103.[XU Jinfa,YANG Zheng,ZHANG Jie.On the effect of natural geographic characteristics of the northern slope in Tianshan Mountains on the productivity and confluence of water[J]. Journal of Xinjiang University(Natural Science Edition）,1994,11(3）:92 -98,103.]   
[24］阎东凯.地名文化与边疆移民社会形态——以清至民国时期 天山北麓地区为核心[J]．中国历史地理论丛,2015,30（4)： 139 -147.[YAN Dongkai.Place name culture and forms of frontier migrants societies:Taking the northern foot of Tianshan from

the Qing dynasty to the period of the republic of China as an example[J]. Journal of Chinese Historical Geography,2015,30（4）： 139 -147.]

[25］刘爽,冯解忧.新疆民族人口空间分布的测量与分析一—基于“五普”、“六普”数据[J].南方人口，2014，29（6)：33-41.[LIU Shuang,FENG Jieyou.The spatial distribution measurementof the ethnic population in Xinjiang:An analysis of the fifth and

sixth national population census［J].South China Population, 2014,29(6) :33 -41.] [26］牛汝辰，程锦，牛劲梅，等.新疆地名音转溯源规律研究[J].测 绘科学,2015,40(2）:48-51,114.[NIURuchen,CHENG Jin, NIU Jinmei,et al.Research on pattern of pronunciation transformation of place names in Xinjiang[J].Science of Surveying and Mapping,2015,40(2) :48-51,114.]

# GIS-based analysis of cultural landscapes for settlement names on the northern slope of the Tianshan Mountains

WANG Pan $^ { 1 , 2 }$ ，WANG Hong-wei1,²，YANG Sheng-tian1,2.3， SUI Xue-jia $^ { 1 , 2 }$ LIU Zhi-jun1,2 (1School of Resources & Environmental Science， Xinjiang University，Urumqi 830046,Xinjiang，China 2Key Laboratory of Oasis Ecology of Ministry of Education，Urumqi 830046,Xinjiang，China 3Collge of Water Sciences，Beijing Normal University，Beijing 10o875,China)

Abstract：Through theuse of geographical information methods to visualize the cultural landscape for geographical names onthe northern slope of the Tianshan Mountains in Xinjiang，China，diferent types of geographical names were clasifiedand nine types were categorized.Based on these results,GIS technology was used to classifythe punctuated geographical namesandanalyze their kernel densities.Theagglomeration and distributionof diffrent typesof geographical names were visualyanalyzed，focusing on the history，economy，nature，and the north slope of the Tianshan Mountains in Xinjiang.Forthecaseof ethnic cultures，the agglomeration and distribution of diffrent types of place names were analyzed.These namesgenerally reflect therelationships between the distribution of cultural landscapesandthe geographicalfeaturesof Xinjiangandits historicaland political，natural，economic,culturalattributes as well asethnic cultures；these namesfully embodythecultural diversityof Xinjiang as a culturally diverse region.The cultural landscape pattrn of various setlements on the northern slope of the Tianshan Mountains has its own uniquecharacteristics.The names of Xinjiang Production and Construction Corps are mainly distributed in the western part of Urumqi，which is located in the lowerreachesof theOasisand isatadistancefrom the main trafc belt.This relationship is basicallyconsistent with therestrictions imposed by historical conditions on troop relocations.Most of the natural names arelocated in the upper partof the alluvial fanand along thelarger river basin and are related to the variations of natural geography around the aluvial fan both upstreamand along the mainstreamof theriver.Thepattern of Gong,Yun geographical namesis relatedto theconditionsof historical development atthe oasisand is generallydistributed along the main traffc belt inthe upperand middle partsofthe aluvialfan.This region is located in northern Xinjiang and ethnic minorities are mainly represented by mountainous or piedmont nomadic people.The distribution of geographical names is generallthe same as the ethnic distribution.Digital place names aregenerall named afterthe natural and human landscapes in their early stages of development.Theyare generally locatedinthe downstream areas of the Oasis andaresomewhat distant from the main lineof trafic.Thegeographical names occurrd earlier and are generally locatednear towns with good waterand soil conditions and also with economic transportation.The immigration place names generall have the same characteristics as those of the same county; immigration from the same area generally involves people gathering together.These place names originated from Gansu，Henan，Guangdong，and Shaanxi Provinces and these areas have their own densely populated residential areas. Becausetherearelarge landareas thatare dificult touse in Xinjiang,these landsarerarely visited bypeople and it isdifcult to generate artificial names，which areusually directlysubordinate tothe local grasroots people's governments.Other name types do not exhibit the clear characteristicsof unity.Almost allregions are represented and are denser inthe Wulumuqi-Shihezi region where the economy is more developed.The study of geographical names is acrucial scientificresearch efortanda special research direction incultural geography.Itis hoped that infuture studies，we will continue to deepen the study of Xinjiang's geographical names in multicultural ethnic areas.

Key words:Xinjiang；Tianshan north slope；place-naming cultural landscape；kernel density estimation