# 基于GIS的藏羊生长发育期气象灾害风险评估

韩炳宏²，周秉荣}³，赵恒和²，石明明1³，孙瑛²，牛得草4，傅华4（1．青海省防灾减灾重点实验室,青海西宁810001；2．青海省海南藏族自治州气象局,青海 共和813099;3．青海省气象科学研究所,青海西宁81001；4．兰州大学草地农业生态系统国家重点实验室,甘肃兰州730020）

摘要：以高海拔脆弱生态环境下的藏羊为研究对象,利用1961—2017年逐日气象资料、承灾体脆弱性、孕灾环境敏感性以及社会经济条件等因子,结合灾害理论模型,通过 ArcGIS 空间分析工具,分析评估了该区藏羊生长发育不同时期气象灾害综合风险。结果表明：高海拔脑山地区羔育期和剪毛期风险较高，浅山或川区风险较低；打草期和配种期浅山、川区及河谷地带风险较高，而脑山地区较低。由此可见，地形因素是影响高海拔地区藏羊生长发育期的主导因子。

关键词：藏羊；生长发育；气象灾害；风险评估；青海

气象灾害作为世界上最为严重的自然灾害之一，是由大气反复活动引起的一类灾害，直接或间接地造成大量生命财产损失。据最新研究资料显示，极端气候和水文灾害事件占全部自然灾害事件的$62 \%$ ,与天气相关的事件却高达 $8 5 \%$ ，约 $3 . 5 0 \times 1 0 ^ { 6 }$ 人死于气象水文灾害事件， $2 . 8 0 \times 1 0 ^ { 6 }$ 人却遭其强烈的影响[1。据联合国报道,1947—1980 年全世界总共有 $1 . 2 0 \times 1 0 ^ { 6 }$ 人直接死于气象灾害[2]。我国是全世界受气象灾害影响最为严重的国家之一。在过去几十年间，因暴雨洪涝、台风和雪暴等事件的发生，我国蒙受了大量的生命财产损失。我国主要的气象灾害影响了 $4 . 0 0 \times 1 0 ^ { 6 }$ 人的生存,灾害造成的经济损失大致占国民生产总值的 $1 \% \sim 3 \%$ [3]。近50a来，我国有数百万人遭受气象灾害的影响，直接经济损失高达数千亿美元[3]。全球气候变暖导致极端天气事件发生的频率显著增加，同时亦加剧了气象灾害的风险[4]

藏羊是我国高海拔地区特色的畜牧业生产优势资源之一，特别在高原牧区生产生活中占据极其重要的地位。藏羊肉中含有大量营养和生物活性物质,有较高的营养保健价值[5]。藏羊养殖抗风险能力较差，受到气象灾害侵袭时容易造成较大损失。因此，在气象现代化逐步实施的条件下，努力提高和加强气象灾害的防御、抗灾和应急减灾能力。同时，精准、科学、合理的气象灾害风险评估，对促进藏羊养殖业健康、稳定的发展具有重要意义。目前，国内大量学者主要开展了有关细毛羊与气候条件的关系研究，集中分析了气候条件对细毛羊生长发育的影响[6-9];另外,还开展了细毛羊气候适应性〔10-11]和气象灾害等研究[12]。

近年来，国内外关于藏羊的研究主要集中于藏羊的采食行为、载畜量与草地畜牧平衡、品种改良与选育、瘤胃消化率与排便量以及养殖的气候适宜性区划等方面[13-15]。然而,有关高海拔地区藏羊生长发育不同阶段的气象灾害风险区划与评估的研究尚未报道。王凯等分析了肃南高寒牧区气象灾害性天气对藏羊产业的影响,并提出了应对策略[16]。本文考虑到数据的完整性，采用1961—2017年青海省海南地区26个区域站逐日气象资料，以藏羊为研究对象，从灾害学角度建立量化因子，基于主客观赋权法赋予每种灾害因子权重，从而构建气象灾害风险区划指标体系，实现了藏羊生长发育期不同阶段的气象灾害综合风险区划。以期为相关部门应对极端气象灾害和高寒牧区畜牧业生产建议提供一定的技术支撑。

# 1研究区概况及研究方法

# 1.1 研究区概况

青海省海南州位于青藏高原东部腹地，东与海东地区和黄南州毗连，西与海西州接壤，南与果洛州为邻，北隔青海湖与海北州相望，属显著的高原大陆性气候。其地理位置为 $9 8 ^ { \circ } 5 5 ^ { \prime } \sim 1 0 5 ^ { \circ } 5 0 ^ { \prime } \mathrm { ~ E ~ }$ ，$3 4 ^ { \circ } 3 8 ^ { \prime } \sim 3 7 ^ { \circ } 1 0 ^ { \prime } \mathrm { N }$ ,东西宽 $2 6 0 ~ \mathrm { k m }$ ,南北长 $2 7 0 ~ \mathrm { k m }$ ，面积为 $4 . 4 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ，占青海省总面积的 $6 . 1 8 \%$ 。境内地形地貌复杂，有草地、荒漠、湿地和湖泊等下垫面;植被类型主要以高寒草甸、高寒草原、高寒湿地、温性草原和荒漠化草原为主;优势牧草以嵩草( $K o -$ bresia myosuroides）线叶嵩草（Kobresia capillifolia）、草地早熟禾（Poa pratensis）、西北针茅（Stipa sarep-tana）、芦苇（Phragmitesaustralis）、芨芨草（Ach-natherumsplendens）、青海固沙草（Orinuskokonori-ca）泡泡刺（Nitrariasphaerocarpa）盐爪爪（Kalidi-um foliatum)为主;土壤类型主要有草甸土、栗钙土、沙壤土和荒漠土[17]（图1)。

# 1.2 研究资料与指标

1.2.1资料来源本文采用 $1 : 2 5 0 \ 0 0 0$ 地理信息基础数据，州、县界数据来源于青海省气象局遥感中心；区域自动站逐日气象资料来自于海南州气象局；DEM（分辨率为 $9 0 \mathrm { ~ m ~ } \times 9 0 \mathrm { ~ m ~ }$ ）、积雪深度和牧草产量栅格数据来自于青海省气象科学研究所;2016 年末羊密度、人均GDP和可利用草场面积数据来源于青海省海南州统计年鉴，

1.2.2研究指标及标准结合前人的研究,通过多年统计资料的比较分析，将藏系羊生长发育期初步划分为羔育期、剪毛期、打草期和配种期4个时段，并总结出藏系羊生长期不同发育阶段的不利气象条件，具体指标见表1;另外，参考《青海省气象灾害标准（DB63/T372-2001)》[18]中的雪灾、寒潮、干旱、连阴雨和大风等级标准(表2～4），该标准也是现阶段青海省各部门广泛应用的一种地方标准。

![](images/e54a594736290f91280ae932d6b28e315fb08068d95683d56ab2c2eba5e31c97.jpg)  
图1研究区基本信息示意图  
Fig.1The basic information of the study area

# 1.3 研究方法

1.3.1灾害理论模型灾害风险度 $( X )$ 是反映灾害发生程度和范围的一种客观定量评估模型，是综合体现致灾因子危险性 $( \boldsymbol { W } )$ 、承灾体脆弱性 $( C )$ 、孕灾环境敏感性 $( M )$ 和防灾减灾能力 $( F ) 4$ 个方面的泛函 $( f )$ ,各因子间的关系通常用表达式 $X = f ( ~ W$ ，

# 表1不同时期影响藏羊生长发育的因素

Tab.1 Factors affecting Tibetan sheep growth in different periods   

<html><body><table><tr><td>生长发育期</td><td>影响阶段</td><td>影响因素</td></tr><tr><td>羔育期</td><td>3月下旬至4月末</td><td>雪灾、大风、寒潮</td></tr><tr><td>剪毛期</td><td>6月上旬至7月末</td><td>平均低温、冰雹</td></tr><tr><td>打草期</td><td>8月下旬至9月上旬</td><td>大风、干旱、连阴雨</td></tr><tr><td>配种期</td><td>9月中旬至10月末</td><td>平均高温、平均低温</td></tr></table></body></html>

Tab.2Standards of snow disasters in pastoral area   
表3牧区寒潮等级标准  

<html><body><table><tr><td>序列</td><td>类型</td><td>牧草掩埋程度/%</td><td>积雪持续日数/d</td><td>积雪面积比/%</td></tr><tr><td rowspan="2">1</td><td>轻灾</td><td>30~40</td><td>≥10</td><td rowspan="2">S≥20</td></tr><tr><td></td><td>41~50</td><td>≥7</td></tr><tr><td rowspan="2">2</td><td>中灾</td><td>41~50</td><td>≥10</td><td rowspan="2">S≥20</td></tr><tr><td></td><td>51~70</td><td>≥7</td></tr><tr><td rowspan="2">3</td><td>重灾</td><td>51~70</td><td>≥10</td><td rowspan="2">S≥40</td></tr><tr><td></td><td>71~90</td><td></td></tr><tr><td rowspan="2">4</td><td>特大灾</td><td></td><td>≥7</td><td rowspan="2">S≥60</td></tr><tr><td></td><td>71~90</td><td>≥10</td></tr><tr><td></td><td></td><td>>90</td><td>≥7</td><td></td></tr></table></body></html>

表2牧区雪灾等级标准  
表4牧区干旱等级标准  

<html><body><table><tr><td>序列</td><td>日最低 气温/℃</td><td>24h降 温/C</td><td>48h降 温/C</td><td>降雪量/mm 偏北风速/(m·s-1)</td></tr><tr><td>1</td><td>≤4.0</td><td>≥8.0</td><td>≥12.0</td><td></td></tr><tr><td>2</td><td>≤4.0</td><td>6.0~7.9</td><td>10.0~11.9</td><td>≥1.0 mm</td></tr><tr><td>3</td><td>≤4.0</td><td>6.0~7.9</td><td>10.0~11.9</td><td>≥12.0m·s-1</td></tr></table></body></html>

Tab.3Standards of cold wave in pastoral area   
Tab.4Standards of drought in pastoral area   

<html><body><table><tr><td>序列</td><td>干旱类型</td><td>干燥度指数(AI)</td></tr><tr><td>1</td><td>无旱</td><td>AI≤1.7</td></tr><tr><td>2</td><td>轻度干旱</td><td>1.7<AI≤3.0</td></tr><tr><td>3</td><td>中度干旱</td><td>3.0<AI≤8.0</td></tr><tr><td>4</td><td>重度干旱</td><td>AI>8.0</td></tr></table></body></html>

$\mathbf { \boldsymbol { C } } , \boldsymbol { M } , \boldsymbol { F } )$ 来表示;然而，由于不同牧区人们的教育文化水平、牧羊经验和贫富差距较大，且政府及相关部门对各地畜牧业生产的支持力度不一致等原因，防灾减灾能力很难量化；故本文采用的气象灾害综合风险指数模型(1如下：

$$
X ~ = ~ W ~ \times ~ C ~ \times ~ M
$$

1.3.2数据处理由于本文涉及的各项指标其计量单位不同，取值范围较大，不仅会影响数据分析结果，也不利于不同量纲指标间的分析比较。因此，为了使得各项指标之间具有可比性，故对各项指标进行归一化处理,公式[19]如下：

$$
T _ { i } = ( X _ { i } - X _ { \operatorname* { m i n } } ) / ( X _ { \operatorname* { m a x } } - X _ { \operatorname* { m i n } } ) \ : , i = 1 \ : , 2 , \cdots , n
$$

式中： $T _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 个标准化因子的原始值; $X _ { \mathrm { m a x } }$ 和 $X _ { \mathrm { m i n } }$ 分别为指标中的最大值和最小值，经归一化的数据$T _ { i }$ 的值域介于[0-1]，其均值为0,均方为1。同时将各指标通过ArcGIS空间分析工具，采用反距离权重(IDW)法进行空间插值，然后将其与海南州县界行政区域相关联。通过灾害风险度模型(1)对各指标进行栅格运算，并利用统计学中的分位数分组法对其进行等级划分。

1.3.3主客观赋权法主观赋权法是根据决策者对各个性能指标的重视程度确定的权重系数，即“专家打分法”;而客观赋权法是通过对“熵”的计算确定权重，就是根据各项指标值的差异，确定各指标的权重[20] 。

# 2 结果与分析

# 2.1 羔育期

高海拔地区影响羔育期的气象灾害主要有雪灾、大风和寒潮，其直接危害羔羊的成活，已成为气象及相关部门服务关注的重点。

2.1.1雪灾风险区划雪灾是指冬春季短时强降雪天气形成的积雪，由于气温过低不能在短时间内消融，制约了牧区畜牧业的发展。其发生不仅会掩埋天然草场，造成畜牧草料供应不足，而且还会形成冰壳刺伤家畜的蹄腕，致使大批家畜因受伤、冻饿而死亡。为此，本文以积雪深度为致灾因子，结合DEM、孕灾环境脆弱性、敏感性、社会经济条件和藏羊密度空间分布（图 $2 \mathrm { a } \sim 2 \mathrm { e }$ )，得出该期雪灾风险区划（图2f）。发现兴海西南部、贵德北部、环湖及贵南局部地区为高风险区，共和盆地外围地区处于中等风险水平，其余各地为低风险区域。

![](images/dc821a9f1180f6785af8b0c1ce603d08123e9be8b976cfa551aea278c0154ec7.jpg)  
图2羔育期雪灾风险区划示意图  
Fig.2Division of sonw disaster risk in lambing period

2.1.2大风风险区划以该期大风日数为致灾因子,并结合DEM、藏羊密度、坡度、坡向分布（图2a,2e和图3a,3b），得出该期大风风险区划（图3c）。结果显示，兴海大部地区为大风高风险区，同德和共和西南部地区居中，其余地区处于低风险区。

2.1.3寒潮风险区划该期以冬春季 $^ { 7 2 \mathrm { ~ h ~ } }$ 日平均气温骤降 $8 \ \mathrm { { ^ \circ C } }$ 或以上，且最低气温降至 $4 \mathrm { { ~ ‰ ~ } }$ 或以下的日数为致灾风险因子，并结合表3中寒潮等级标准，得出该期影响羔羊的寒潮风险区划（图4a）。结果表明，寒潮高风险区主要分布于共和盆地、同德和贵南大部地区，兴海和贵德局部地区为中等风险，其余地区风险较低。

2.1.4羔育期气象灾害综合风险区划该区地理位置特殊，加之海拔较高，早春大风出现的频次较多，考虑到该区寒潮发生的路径和规律，雪灾的危害程度、极端低温、下垫面的脆弱性和敏感性及社会经济条件等因子的影响，从而得出羔育期气象灾害风险综合区划(图4b），结果表明，环青海湖南岸、兴海西部和南部以及同德局部地区气象灾害风险等级较高，共和盆地至龙羊峡一带及贵德和贵南接壤区居中，贵德大部、贵南中西部、兴海中东北部及共和东南部风险较低。

# 2.2 剪毛期

藏羊剪毛期的气象要素主要以低温和冰雹为主。因此,将该时段冰雹日数作为致灾因子，结合DEM、藏羊密度、坡度和坡向分布（图2a,2e;图3a,

![](images/2f5fdb1d18e510621844bc92af9428e9b8453e8f5f8843ba8bbf13862dd87878.jpg)  
Fig.3Division of strong wind disaster risk in lambing period

![](images/190f959c2a9e813c7eaf7bf88f1ee4b73d671c55bb5454524d253db62f6cd428.jpg)  
图3羔育期大风灾害风险区划示意图  
图4羔育期气象灾害风险区划示意图  
Fig.4Division of meteorological disaster risk in lambing period

3b 和图5a)，得出剪毛期平均最低气温和冰雹灾害风险区划（图5b）；同时利用地图栅格代数得出剪毛期气象灾害综合风险区划（图5c）。发现剪毛期气象灾害高风险区主要分布于环青海湖南岸，共和西南部、兴海西北部以及贵南、贵德和同德局部地区处于中等风险水平，其余各地为低风险区。

# 2.3 打草期

影响此时段的气象灾害主要有大风、干旱和连阴雨，其直接影响了饲草料的产量和品质。以该期大风出现的日数、干旱灾害风险指数和连阴雨日数为致灾因子，结合孕灾环境脆弱性、敏感性、可利用草场面积和牧草产量（图2b,2c和图6a,6b），得出该期影响牧事活动的干旱和连阴雨风险区划（图6c和6d)；并利用ArcGIS空间分析工具中的地图栅格代数,将该时段大风、干旱和连阴雨进行栅格运算，从而获得打草期气象灾害综合风险区划（图6e）。结果显示，打草期环青海湖外围地区和共和盆地中部气象灾害风险等级最高，贵南大部、共和西南部和兴海南部地区居中，其余地区灾害风险等级较低。

![](images/940230bebace5f7599bd976879e3e3b736b872a4dd2d370da104217df2ad10af.jpg)  
Fig.5Division of meteorological disaster risk in shearing period

![](images/0d19aad25d62ec7f722fcae5200a86d914cbfc82aaacddca4ab7f31796232a0c.jpg)  
图5剪毛期气象灾害风险区划示意图  
图6打草期气象灾害风险区划示意图  
Fig. 6 Division of meteorological disaster risk in grass harvest period

![](images/13b43f6262e832d48ad153da1607948b9baa4dc3903bd86a3f856d6d8ec68efa.jpg)  
韩炳宏等：基于GIS的藏羊生长发育期气象灾害风险评估  
图7配种期气象灾害风险区划示意图  
Fig.7 Division of meteorological disaster risk in copulation period

# 2.4 配种期

藏羊配种的成功率与该时段平均最高和最低气温密切相关，气温过高或过低都会降低配种成功率。因此，在充分考虑地形因素的前提下，结合该时段平均最高和最低气温(图7a和7b)的空间分布特征，得出藏羊配种期气象灾害风险区划（图7c）。结果表明，贵德地区的气象灾害风险较高，共和东部以及贵南局地风险水平居中，而兴海和贵南西南部地区风险较低。

# 3讨论

研究表明，随着海拔高度的不断增加，羔育期和剪毛期气象灾害风险也随之升高，加之该区常年积雪覆盖，故羔羊很难度过这一阶段，此阶段的气象灾害直接影响羔羊的成活率;打草期和配种期气象灾害风险与羔育期和剪毛期相反，这可能与浅山和川区的连阴雨、干旱、高温及降雹格局分布不均有关，且在各地区的分布差异较大。因为这些因子不仅影响饲草料的饲用品质和产量，而且也不利于藏羊的成功配种。来自内蒙古草原牧区的研究表明[1],羔育期雪灾、沙尘暴、寒潮、湿雪等因子对牧事活动有很大负面影响，直接危害羔羊的成活率;剪毛期低温、冷雨和冰雹等恶略天气是限制剪毛的主要因子;打草期的连片干旱和连阴雨天气会影响饲草料的产量和品质，从而间接影响羊正常生长发育；羊配种的成功率与极端高温和极端低温密切相关。王凯等[21]对肃南高寒牧区气象灾害性天气对羊产业的影响进行了分析，指出每年3月中下旬至5月上旬往往是春季雪灾频发期,大雪过后通常伴随着气温低、雪被厚、持续时间长等特点，致使牲畜因吃不上草或在雪地穿行困难，体能消耗过大，出现牲畜饿死或掉膘、羔羊冻伤冻死等现象。虽上述研究在羊不同生长发育阶段选取的大多数气候因子与本研究相同，但由于地域的差异，仍有少数因子与本研究不同。因此,所获结果与本研究相比仍有一定差异。应该指出，本文虽取得的成果，能客观实际反映当地的气象灾害风险基本情况，但这并不意味着所获结果在其他地区也能取得较好的应用。另外,针对当地藏羊生长发育期气象灾害风险预警预测技术和服务仍有一定差距。因此,我们应充分考虑当地的气候、地形地貌、生态环境、水文条件以及经济状况等特征,在后续工作中，有针对性地选取影响藏羊的诱发因子，应用遥感卫星技术获取地形地貌和生态环境因子数据,将现有的气象资料实现格点化,并进一步精细化，才能满足本地化业务应用平台。

# 4结论与建议

（1）羔育期气象灾害风险高发区主要分布在海南北部的共和、西南部兴海及南部同德脑山地区，浅山或川区风险水平较低。可见，脑山地区的羔羊对气象致灾因子(雪灾、大风和寒潮)的敏感性较浅山或川区高。

（2）藏羊剪毛期气象灾害风险高发区主要位于共和地区，其余县区风险较低。主要是该区受青海湖及其周边湿地的显著影响，因为青海湖及其周边湿地向大气中输送的水汽量较其他地区多，从而导致降雹格局极不均匀。

（3）打草期气象灾害风险高发区主要以共和盆地和黄河谷地为主，浅山或川区居中，而脑山区较低。气象干旱、大风和连阴雨天气过程,不仅影响该区饲草料的产量和及时储备，也降低了饲草料的营养品质。

（4）藏羊配种期气象灾害风险高发区位于贵德地区，共和、同德地区居中，兴海和贵南西南部较低。配种期气温过高或过低都会显著影响藏羊配种的成功率。

由于藏羊不同生长发育期的致灾因子类型不同。因此，建议政府及相关部门能及时、准确提供优质的决策气象服务产品，同时牧民也要密切关注当地的天气预报，为当地社会经济和畜牧业健康发展创造有利条件。

# 参考文献（References）：

[1]Zhong SB,Fang Z X,Zhu M,etal.A geo-ontology-based approach to decision-making in emergency management of meteorological disasters[J].Natural Hazards,2017,89(2）:531 -554.   
[2] 杨淑萍，赵光平，马力文，等.气候变暖对宁夏气候和极端天气 事件的影响及防御对策[J].中国沙漠，2007，27（6)：1072- 1 076.[Yang Shuping,Zhao Guangping,Ma Liwen,et al. Climate change and extreme weather events in Ningxia on global warming background and meteorological disaster preventing countermeasures [J].Journal of Desert Research,2007,27(6):1 072-1 076.]   
[3] Liu T,Yan TC.Main meteorological disasters in China and their economic losses[J]. Journal of Natural Disasters,2011,2O（2）: 90-95.   
[4] SunJ,Zhao S.The impacts of multiscale weather systems on freezing rain and snowstorms over southern China[J].Weather& Forecasting,2010,25(2):388-407.   
[5] 靳义超，闫忠心，李升升.我国藏羊资源研究利用现状与展望 [C]//中国畜牧兽医医学会信息技术分会2014年学术研讨 会,2014.[Jin Yichao,Yan Zhongxin,Li Shengsheng.The utilization status and prospect of Tibetan sheep resources research in China[C]//China Animal Husbandry and Veterinary Medical Association Information Technology Branch 2O14 Academic Seminar, 2014.]   
[6]范德芹,赵学胜,郑周涛.内蒙古羊草草原物候及其对气候变 化的响应[J].地理与地理信息科学,2016,32(6):81-86. [Fan Deqin,Zhao Xuesheng,Zheng Zhoutao.Phenology of Leymus chinensis steppe in Inner Mongoliaand itsresponse to climate changes[J].Geography and Geo-Information Science,2016,32 (6):81-86.]   
[7]那木斯来.2016年内蒙古鄂温克族自治旗接羔保育期气候评 述[J].畜牧与饲料科学,2016,37(9）:97-98.[Namusilai.The climate review of the lamb conservation period of Ewenki Autonomous Banner of Inner Mongolia in 2O16[J].Animal Husbandry and Feed Science,2016,37(9) :97 -98.]   
[8］李桂英.高寒牧区气候与营养因素对细毛羊体重影响的研究 [J].畜牧兽医杂志,2012,31（1）:27-30.[Li Guiying.Study on the effects of alpine-arctic pastoral zone climate and nutritional factors on fine wool sheep body weight[J]. Journal of Animal Science and Veterinary Medicine,2012,31(1）:27-30.]   
[9]张利平,宫旭胤,张明贤,等.肃南牧区家庭牧场甘肃高山细毛 羊生产现状研究分析[J].草食家畜,2014（3）:1-6.[Zhang Liping,Gong Xuyin,Zhang Mingxian,et al. The production status analysis of Gansu fine-wool sheep in family ranch of Sunan pastoral area[J]. Grass-Feeding Livestock,2014(3）:1-6.]   
[10］祁全青,李光梅,党海森,等.甘肃高山细毛羊在环青海湖地区 的适应性观察试验[J].草食家畜,2008（4）:27－29.[Qi Quanqing,Li Guangmei,Dang Haisen,et al. Gansu areas around Qinghai lake in the mountains of fine wool adaptation test[J]. Grass-Feeding Livestock,2008(4）:27-29.]   
[11］哈斯塔木嘎,格日乐.基于GIS 的内蒙古细毛羊放牧期气象灾 害风险区划[J].灾害学,2017,32（4）:90-93.[Hasitamuga, Gerile.GIS based risk zoning of meteorological disaster in grazing period of fine wool sheep[J]. Journal of Catastrophology,2017,32 (4):90-93.]   
[12］刘继刚.高寒地区引进体大高产澳血细毛种羊适应性观察 [J].畜牧兽医杂志,2014,33（5）：9-10,14.[LiuJigang.Adaptive observation of the large high-yield Australian blood breeding sheep from cold areas[J].Journal of Animal Science and Veterinary Medicine,2014,33（5）:9-10,14.]   
[13]吴铁成,吴建平,赵生国,等.甘南玛曲不同年龄欧拉型藏羊放 牧采食量季节动态研究[J].草地学报,2016,24（6）：317- 321.[Wu Tiecheng,Wu Jianping,Zhao Shengguo,et al. Seasonal dynamics research on grazing intake of Oula Tibetan sheep at different ages in Gansu Maqu[J].Acta Agrestia Sinica,2016,24 (6):317-321.]   
[14］淡瑞芳,张海涛,龙瑞军,等.藏系绵羊瘤胃细菌数量及其放牧 地牧草养分随季节变化的研究[J].草业学报,2009,18（1)： 100-104.[Dan Ruifang,Zhang Haitao,Long Ruijun,et al. Seasonal shift of rumen bacteria quantity of grazing Tibetan sheep and forage nutrition by grazing sheep[J]. Acta Prataculturae Sinica, 2009,18（1):100 －104.]   
[15］郭强,殷国梅,赵和平,等.放牧绵羊牧食行为及采食量研究 [J].中国草地学报,2011,33（4）:95-98.[Guo Qiang,Yin Guomei,Zhao Heping,et al. Study on grazing behavior and feed intake of grazing sheep[J]. Chinese Journal of Grassland,2011,33 (4) :95 -98.]

[16]王凯,乔红梅,海菊花.肃南高寒牧区气象灾害性天气对羊产 业的影响分析及应对策略[J].甘肃畜牧兽医,2015,45（4）： 32-33.[Wang Kai,Qiao Hongmei,Hai Juhua.Analysis of the influence of meteorological disasters on sheep industry and its countermeasures[J].Gansu Animal and Veterinary Sciences,2015,45 (4):32 -33.]

[17」韩炳宏，周秉荣，吴让，等.青海南部高寒草地土壤冻融交替期水热特征分析[J].气象科技，2018，46（2）：361-368.［HanBinghong,Zhou Bingrong,Wu Rang,etal.Characteristics of hydrothermal factors in soil freezing and thawing alternation over south-ern alpine grasslands in Qinghai Province[J].Meteorological Sci-ence and Technology,2018,46(2） :361-368.]

[18]周秉荣，李甫，胡爱军，等.青海省气候资源分析评价与气象灾 害风险区划[M].北京：气象出版社,2016:62-67.[Zhou Bing rong,Li Fu,Hu Aijun,et al.Analysisand Evaluation of Climate Resources and the Division of Meteorological Disaster Risk in QinghaiProvince[M].Beijing:Meteorological Press,2O16:62-

# 67.]

[19]韩炳宏，吴让，周秉荣,等.基于格网的青海省雪灾综合风险评 估[J].干旱区研究,2017,34(5）:1035-1041.[Han Binghong,Wu Rang,Zhou Bingrong,et al.Grid-based estimation of snow disaster risk in Qinghai Province[J].Arid Zone Research, 2017,34(5) :1035 -1041.]   
[20]洪峰，曾智勇，周婉婷,等.基于主观赋权法的控制系统优化研 究[J].制造业自动化,2015,37（8）:20-22.[Hong Feng,Zeng Zhiyong,Zhou Wanting,et al.Optimization of control system based on the subjective weighting method[J].Manufacturing Automation,2015,37(8):20-22.]   
[21］王凯,乔红梅,海菊花.肃南高寒牧区气象灾害性天气对羊产 业的影响分析及应对策略[J].甘肃畜牧兽医，2015,45（4）： 32-33.[Wang Kai,Qiao Hongmei,Hai Juhua.The effects analysis on the sheep industry of Sunan alpine pastoral areas harazd weather and its countermeasures[J].Gansu Animal and Veterinary Sciences,2015,45(4) :32-33.]

# GIS-based Estimation of Meteorological Disaster Risk During Tibetan Sheep Growth

HAN Bing-hong $^ { 1 , 2 }$ ，ZHOU Bing-rong1,3 ZHAO Heng-he²， SHI Ming-mingt1,3SUN Ying²， NIU De-cao4, FU Hua4

(1.Qinghai Province Key Laboratory of Disaster Prevention and Mitigation,Xining 810oo1,Qinghai,China; 2. Meteorology Bureau of Hainan Tibetan Autonomous Prefecture,Gonghe 813099 ,Qinghai,China; 3.Qinghai Province Institute of Meteorology,Xining 810oo1,Qinghai,China ; 4.State KeyLaboratoryofGrassand Agro-ecosystem,Collegeof Pastoral Agriculture Scienceand Technology,Lanzhou University,Lanzhou 73002O,Gansu,China)

Abstract：Tibetan sheep in alpine fragile ecological environment was researched using thedaily meteorological dataduring theperiodof1961-2O17,andthe vulnerabilityof the sheep,environmental sensitivityand socialandeconomicconditions wereanalyzed.The theory model of disaster,meteorological disaster risk estimationand ArcGIS spatial analysis were applied to lucubrate and estimate the sheep growth in different periods.The results showed that the risk in the alpine zone was higher in lambing and shearing periods but lower in the hilsandonthe gentle slope. In copulationand grassharvest periods,therisk was higherinthehilsand valleysandonthegentle slopebut lower in the nalpine zone.Thus itcan be seenthat terrain is adominant factorafecting Tibetan sheep growth in the alpine zone.

Key words:Tibetan sheep； sheep growth ；meteorological disaster； risk assessment； Qinghai Province