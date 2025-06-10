# 基于遥感时序特征的地表覆被信息提取

田艳君1，石莹1，帅艳民1.2.3， 杨健，邵聪颖，范连连23， 马红红4.5

(1.辽宁工程技术大学,辽宁 阜新123000；2.中国科学院新疆生态与地理研究所,新疆 乌鲁木齐830011;3.中国科学院中亚生态与环境研究中心,新疆 乌鲁木齐830011；4.石河子大学,新疆 石河子832003;5.新疆农业科学院土壤肥料与农业节水研究所,新疆 乌鲁木齐830091)

摘要：地表覆被作为自然过程和人类活动共同作用的重要地表景观特征，对全球或局地气候、水热循环、物质传输及陆面生态系统多样性等影响深远。利用年内时序遥感影像自动提取不同地表覆被类型的方法，以新疆阜康地区为研究目标，组织2016年植被全生长季的Landsat8OLI地表反射时序影像，研究不同物候期植被冠层的纹理响应信息，考察研究区典型地表覆被类型在3—11月多波段波谱、归一化植被指数(NDVI)及增强型植被指数(EVI)的时序特征,构建提取地表覆被类型的策略规则，形成时序特征匹配方法，将其应用于2018年研究区地表覆被填图的提取。最后，基于高分辨率卫星影像和野外实地调查对随机选取的2500个样点进行对比验证。结果表明：提取结果和验证数据一致性较好，总体精度为 $9 7 . 2 \%$ ,Kappa系数为0.9655，且实地考查结果显示本方法在复播作物识别和有效降低单一时相中“异物同谱"现象上展示潜在优势。

关 键 词：时序遥感数据；植被物候；光谱特征；归一化植被指数；增强型植被指数；地表覆被填图文章编号：

地表覆被逐渐成为气候变化、国情监测、生态评价和可持续发展规划研究中的重要变量。近年来，虽然已有不少关于全球地表覆被数据用于满足生物多样性和农业管理的研究，但是数据适用性仍显不足[1]。不仅全球约 $6 0 \%$ 的农田制图精度仍需提高[2],粮食估产和农情监测对此也有更高精度的需求。虽然地表覆被产品分类精度逐步提升，但地表覆被作为地球表面物质和自然属性的综合体[3],受气候环境等影响，尤其是在地表蒸散严重的干旱区，表现出很强的脆弱性[4],其识别精度尚未满足广大用户日益增长的应用需求。

随着地表分类精度需求的提高和数据的累积，对地数据逐渐从零星到系统的信号采集和组织模式。早期利用单一时相遥感影像进行地表覆被类型的识别方法简便快捷，但就地物信息提取仅做时间维上有限离散甚至孤立的采样，难以捕捉许多自然地表随时间推移或者季节更替的渐进变化特点，潜在缩减了对“同谱异物"正确解译的机会，常常不易满足动态监测精度要求[5]。而加密的时间序列遥感影像则可以有效采集地表覆被随物候或季相变化的节律特点[,为进一步细化地表类别和提高不同地表覆被识别精度提供可能。

综合地物时序光谱特征或植被指数信息提取地表覆被正在逐渐被越来越多的学者关注。如利用多时相Landsat8OLI数据深度挖掘地物的光谱特征及归一化植被指数(Normalizeddifferencevegeta-tionindex，NDVI)的时序信息，选取某些关键时相构建不同作物的决策树模型,提取作物种植结构信息[7-9]。胡勇等[根据训练样本和参考影像光谱特征将其在时间维进行扩展以提高分类精度。王颖洁等[]基于Landsat等中分辨率遥感数据定量提取地物光谱和时序特征，同时应用各种分类器及多源算法，将地物分为裸地、耕地、林地等基础类别，生产连续地表覆被填图。但植被物候信息在中高分辨率地表覆被提取中的应用仍很缺乏，尤其在农情管理、智能农业或精准农业监测等领域尚需更为精细的农作物类别填图。因此，如何利用时间序列遥感影像定量描述农作物的物候变化规律，表征不同地表覆被的特点，提高地表覆被精度具有重要意义。

综上所述，时间序列方法在多种地物分类尤其是农作物类别提取中有待进一步加强。本文基于作物生长季时序的中分辨率地表反射数据，提取典型地物多波段波谱和NDVI及增强型植被指数(En-hancedvegetationindex，EVI)的时序特征，建立特征规则提取实验区作物类别信息。

# 1材料与方法

# 1.1 研究区概况

本文选取西部绿洲城市[12-13]阜康地区( $8 7 ^ { \circ } 5 3 ^ { \prime } \sim$ $8 8 ^ { \circ } 4 ^ { \prime } \mathrm { E }$ $4 4 ^ { \circ } 1 5 ^ { \prime } { \sim } 4 4 ^ { \circ } 2 2 ^ { \prime } \mathrm { N }$ ，图1)为研究区，其位于新疆维吾尔自治区昌吉回族自治州，地处天山东段北麓、准噶尔盆地的南缘，中部为由天山融雪河流冲积而成的平原，是绿洲农业的集中分布区，具有多样的作物类型。新疆阜康地区属于典型的温带大陆性干旱气候，水资源匮乏，蒸发强烈，主要灌溉水源是天山冰雪融水与细小河流，对精准农业的需求更为迫切，因此对该区域地表覆被类型的提取，尤其是农作物信息的准确提取变得尤为重要。

![](images/3ee0cad6e85a103481671d0c352d12a00f4b925724157f6dd625473162e35ee9.jpg)  
Fig.1 True color images and geographical location of the study area

# 1.2 研究方法

1.2.1 时序特征匹配不同地表覆被(尤其是农作物)生育周期内的地表反射波谱及植被指数各具特色，特征明显。如图2为不同类型植被生长发育特征随时序典型分异情况。一些秋末初冬播种的作物，如小麦，在春季进入发育旺盛时期，到夏初就发育成熟进入收割期;而春播作物出苗就已5、6月份，经过各具特色的发育过程，到夏末或秋季结束生长进入收割期，如玉米、棉花等作物;此外城市绿化、乡村绿植、防护林或防风带等也各有其独特的生长发育和休眠特征。结合植被物候期及纹理特征选取典型地表覆被样本点，提取不同植被在波谱空间全生育期内绿起、成熟/丰叶、凋零/收割多波段波谱和植被因子的渐进变化特征，组成特征向量$\boldsymbol { x } _ { _ { v _ { - } i } } = ( x _ { _ { 1 } } , x _ { _ { 2 } } , \cdots , x _ { _ n } )$ ,其中 $v \_ i$ 表示第 $i$ 种植被; $x _ { j } ( j =$ ${ 1 , 2 , \cdots , n } )$ 表示所提取的 $n$ 维时序特征，用来定量表征植被 $\ v _ { - } i$ 在不同生育期的典型特征值。

![](images/06fd3ee5cc41ec06b724ff7fbdecb904b9702580811966ce9ca290279ae3c539.jpg)  
图1研究区真彩色影像及地理位置  
图2典型植被的时间序列特征图 Fig.2Illustration of temporal features implied in typical vegetation

以欧氏距离[4和最近邻原则为主判别待识别像元 $\nu _ { - } p$ 的精细类别归属。首先依据公式(1)估算$\nu _ { -  { p } }$ 的时序特征向量 $( y _ { 1 } , y _ { 2 } , \cdots , y _ { n } )$ 与 $m$ 个先验特征样本 $( x _ { 1 } , x _ { 2 } , \cdots , x _ { m } )$ 的特征距离 $( D _ { { } _ { p _ { - } 1 } } , D _ { { } _ { p _ { - } 2 } } , \cdots , D _ { { } _ { p _ { - } m } } )$ ,再根据最近邻原则进行类别匹配，获得最大似然的精细类别。

$$
D _ { j k } = \sqrt { \sum _ { i = 1 } ^ { n } ( x _ { k i } - y _ { j i } ) ^ { 2 } }
$$

式中： $D _ { j k }$ 指特征距离,其中 $k = 1 , 2 , \cdots , m , j \in [ 1 , + \infty )$ $\boldsymbol { x } _ { k i }$ 指训练样本时间序列的特征值; $y _ { j i }$ 指待分类样本的时间序列特征值。

1.2.2技术流程图3所示为主要技术流程。首先对Landsat8OLI数据进行预处理(模块A），为有效提取地表覆被纹理、波谱特征服务；融合物候信息，构建典型地表覆被的先验特征向量(模块B)，为自动识别建立规则；再将其应用到待识别影像序列，自动进行特征匹配，获取最似然的精细地物类别(模块C);最后与验证数据进行对比与精度分析(模块D)。

# 1.3数据来源

1.3.1物候数据新疆阜康地区地表观测农作物生长发育的物候期(旬/月)见表1。该地区典型地表覆被在生长发育过程中，会呈现不同的特征。如小麦播种早期不覆膜，9月中下旬播种，翌年6月中下旬成熟;而棉花和玉米播种早期均覆膜,棉花每年4月播种，11月中旬收割结束，玉米每年4月播种，9月底收割，其收获期间绿叶仍可能存在；水稻在分蘖拔节期需灌入大量的水；油葵生育期较短，持续120d左右，其在4月末播种。

![](images/744a98b05023db4d78d619938f607c71fdf55c3bfff97e99e725fa8d11a8f181.jpg)  
图3信息处理流程  
Fig.3Flow chart of information process

表1新疆阜康地区农作物物候期  
Tab.1Phenological period of crops in Fukang City, Xinjiang   

<html><body><table><tr><td>农作物生育期</td><td>播种—分蘖</td><td>分蘖一返青</td><td>返青一拔节</td><td>拔节一抽穗</td><td></td><td>抽穗一成熟</td></tr><tr><td>小麦</td><td>下/9—上/11</td><td>上/11—下/3</td><td>下/3—中/4</td><td></td><td>中/4—中/5</td><td>中/5-下/6</td></tr><tr><td>农作物生育期</td><td>播种一出苗</td><td>出苗一拔节</td><td>拔节一抽穗</td><td></td><td>抽穗一乳熟</td><td>乳熟一成熟</td></tr><tr><td>玉米</td><td>下/4—中/5</td><td>中/5—下/6</td><td>下/6-下/7</td><td></td><td>下/7—中/8</td><td>中/8—中/9</td></tr><tr><td>农作物生育期</td><td>播种一出苗</td><td>出苗一现蕾</td><td>现蕾一开花</td><td></td><td>开花一吐絮</td><td>吐絮以后</td></tr><tr><td>棉花</td><td>下/4—中/5</td><td>中/5—中/6</td><td>中/6—下/7</td><td></td><td>下/7—下/9</td><td>下/9—上/11</td></tr><tr><td>农作物生育期</td><td>播种一分蘖</td><td>分蘖一拔节</td><td>拔节一抽穗</td><td></td><td>抽穗一灌浆</td><td>灌浆一成熟</td></tr><tr><td>水稻</td><td>下/4—中/5</td><td>中/5—下/6</td><td>下/6—上/8</td><td></td><td>上/8-上/9</td><td>上/9—下/10</td></tr><tr><td>农作物生育期</td><td>播种一出苗</td><td>出苗一现蕾</td><td>现蕾一开花</td><td></td><td>开花一成熟</td><td></td></tr><tr><td>油葵</td><td>下/4—中/5</td><td>中/5-上/6</td><td>上/6—下/7</td><td></td><td>下/7—下/8</td><td></td></tr></table></body></html>

注：下/9等表示农作物生长发育的物候期(旬/月）。

1.3.2验证数据本文选取覆盖研究区的高分辨率开放遥感影像(谷歌地图GoogleEarth)和野外实地调查数据作为验证数据。随机选取2500个样本点，包括小麦、玉米、油葵、水稻、棉花、葡萄、居民地、草地、裸土和复播10类地物，利用谷歌地图对其进行验证，同时以2019年5月18日野外实地调查的葡萄、水稻、小麦和油葵作为辅助数据来进行验证。

1.3.3影像数据及预处理本文所采用的遥感影像数据来源于美国地质调查局(https://earthexplorer.usgs.gov/)所发布的已做过地理定标、大气校正的地表反射率数据产品[15-16],可有效反应地表波谱响应信息。经对比筛选，选取2016年(14个时相）和2018年(12个时相)云量较少，植被生长季时相较多的Landsat8OLI数据。其中，2016年的14个时相作为提取波谱及植被指数特征的数据，2018年的12个时相数据作为地表覆被分类数据。

为满足实验需求，对研究区遥感数据进行了预处理操作。将遥感影像进行4、3、2波段的融合形成真彩色图像，并对阜康地区农业集中分布研究区进行裁剪操作，图1a为阜康市真彩色图像，图1b为所裁剪的研究区真彩色图像。再进行研究区时相数据间的配准校验，保证不同时期获取的影像精确配准。最后，对地面观测农作物物候期与遥感影像数据采集日期归一化整合处理。此外，准备调查GoogleEarth在该地区清晰影像和整理实地调查记录，为分类验证做准备。

# 2 结果与分析

# 2.1时间序列多波段波谱特征分析

不同地表覆被的反射波谱在不同季相，尤其是植被，天然拥有各具特色的生长发育周期，大都差异鲜明。根据阜康农作物产业结构年鉴数据和新疆阜康地区农作物物候期可知研究区的农作物主要有小麦、油葵、玉米、水稻、葡萄和棉花等。图4为阜康地区8种典型覆被类型样本点2016年Landsat8OLI中16个时相多光谱时序变化曲线。总体上，可见光波段包括蓝波段 ${ \mathrm { B } } 2 { \left( 0 . 4 5 { \sim } 0 . 5 1 ~ { \mu } { \mathrm { m } } \right) }$ ，绿波段${ \mathrm { B } } 3 \left( 0 . 5 3 { \sim } 0 . 5 9 \ { \mu \mathrm { m } } \right)$ 和红波段 ${ \mathrm { B } } 4 ( 0 . 6 4 { \sim } 0 . 6 7 \ { \mu } { \mathrm { m } } )$ 在未有植被覆盖时,呈现裸土特性（图 $4 \mathrm { h }$ )。一旦作物出苗或其他植被返青，可见光波段会明显被抑制，且绿波段反射率比其他可见光的反射率高，如4、5月小麦(图4a)，7、8月的油葵(图4b)和玉米(图4c)等;而近红外波段B ${ \displaystyle { ; 5 ( 0 . 8 5 { \sim } 0 . 8 8 \ \mu \mathrm { m } ) } }$ 随植被出苗拔节等生长变化其冠层绿色叶片增加，近红外波段反射率变化明显，且在植被生长期，相比其他波段反射率值较高，如6、7月的玉米(图4c)及8、9月的棉花(图4f)等;短波红外 $1 \mathrm { B } 6 ( 1 . 5 7 { \sim } 1 . 6 5 ~ \mu \mathrm { m } )$ 对水具有强吸收性,故在植被生长期其反射率较低,非植被生长期反射率较高，说明土壤含水较少，地表较为干旱(图4h)。且比其他地物，水稻受灌水影响，其各个波段的反射率较低(图4d)。

# 2.2时间序列NDVI特征分析

研究表明NDVI具有捕获植被生长状况的能力。不同植被的内在组织结构、色素含量和冠层组分比例在生长发育过程中不断变化，红光和近红外波段对此响应相对敏感。NDVI定义中[见公式(2)]近红外和红光2个波段差值旨在放大植被响应信号，并通过归一化增强不同情况下取值的定量可比性,是探讨植被特征的有效因子[17]

$$
\mathrm { N D V I } = { \frac { \rho _ { \mathrm { N I R } } - \rho _ { \mathrm { R E D } } } { \rho _ { \mathrm { N I R } } + \rho _ { \mathrm { R E D } } } }
$$

式中： $\rho _ { \mathrm { R E D } }$ 和 $\rho _ { \mathrm { { N R } } }$ 分别指红波段和近红外波段的地表反射率。时间序列的NDVI可以在同一作物生育期内进行多次采样，潜在勾勒出不同作物生长发育进展，丰富分类信息，降低"异物同谱"几率，以提高准确提取精度。一般情况下，随着植被的快速生长，叶面积持续增加，卫星观测的视场内信号增强，而红光和近红外波段在光谱空间对绿色生长变化的联动反映，使不同地表覆被展现出不同的波谱特征，综合分析图5a可以得到：

（1）小麦4月中旬拔节期前后，干物质积累快生长旺盛，NDVI曲线迅速上升直至5月中下旬抽穗期，NDVI值达到峰值(约0.8)，保持约2周的饱和状态，随着小麦灌浆成熟逐渐降低，进入7月中旬收割期。若复播后期呈现种植作物生育期的特征(见复播曲线）,若无复播NDVI向裸土特征逼近，取值约为0.1。

(2）油葵7月开花，NDVI值达到峰值(约0.7)，8月下旬油葵成熟收割，NDVI值基本保持在0.1左右。

(3）玉米和油葵的生育规律较为相似，但玉米6月下旬处于拔节期，其NDVI值达到峰值(约0.8），且玉米7月中旬到8月上旬处于抽雄期，玉米的雄花呈淡黄色穗状，NDVI值会呈现低谷，NDVI值由0.87下降至0.83，又上升到 $0 . 8 6$ O

![](images/28e860597d40e017e06e69716777c776378ff8c9dfe8b93b7eed217aaeb5a607.jpg)  
干旱区地理  
31表示海岸波段;B2表示蓝波段;B3表示绿波段;B4表示红波段;B5表示近红外波段;B6表示短波红外1;B7表示短  
图4阜康典型地物的多光谱时序变化  
Fig.4Dynamic changes of multispectral over typical land covers of Fukang City

![](images/633b1c49bfa4d45deb509aa977585f55245e1f4e25a9fea626cc3bd24e3343a0.jpg)  
图5阜康典型地物的NDVI、EVI时序变化  
Fig.5Dynamic changes of NDVIand EVI over typical land covers of Fukang City

(4）水稻5月中旬，处于分蘖拔节期，需向稻田中灌入大量的水，此时NDVI值达到低谷，4月上旬NDVI值为0.18,灌水后，5月中旬NDVI值下降至0.08,5月下旬NDVI值又上升到0.18。（5）棉花9月处于吐絮期，其NDVI值基本维持为0.8左右，而此时其他作物逐渐收割，NDVI曲线呈现下降趋势。(6)葡萄是多年生果树，4月温度上升后生长发育，到6月下旬NDVI达到峰值(约0.7)，随时间推移开始结果实，由于葡萄果实呈现紫色，NDVI下降至0.6左右，大约需35\~50d果实成熟，期间其他幼果也逐渐成熟，持续到10月，待果实摘掉后，仍有绿叶存在NDVI曲线呈现上升的趋势，10月到11月进入休眠期其呈下降趋势。（7）裸土的NDVI值一般较低，基本保持在0.1左右，其NDVI值一般不随着时间推移而改变。（8）草地在温度适宜时，进行生长，5月中旬到10月上旬，其NDVI值维持在0.2\~0.3之间。（9）居民地[包括建筑物，以及与居住相关的其他生活设施(如道路、园林绿化等），经过考察得知建筑设施周围存在树木、人工绿化等植被，一般以居民地为主,植被较少，其NDVI值为0.2左右，与草地的时序NDVI曲线较为相似。

# 2.3时间序列EVI特征分析

因NDVI高端取值时存在饱和现象，考虑EVI[见公式(3）辅助分析，在一定程度上克服NDVI高端取值的饱和现象，增大稠密绿叶植被间的差异性,提高丰叶期不同植被识别的敏感性[19]

$$
\mathrm { E V I } = \frac { 2 . 5 \times ( \rho _ { \mathrm { N I R } } - \rho _ { \mathrm { R E D } } ) } { \rho _ { \mathrm { N I R } } + 6 . 0 \rho _ { \mathrm { R E D } } - 7 . 5 \rho _ { \mathrm { B L U E } } + 1 }
$$

式中： $\rho _ { \mathrm { { B L U E } } }$ 指蓝波段的地表反射率。如图5b所示为研究区典型地物时序EVI曲线，可以得出：5月中旬到5月末，小麦的NDVI值变化较小而EVI值在增加，玉米在抽雄期NDVI值和EVI值从7月中旬至7月下旬逐渐下降，7月下旬到8月上旬逐渐上升，但EVI值的变化幅度较大；水稻在分蘖拔节期需向稻田中灌入大量的水，故其NDVI值和EVI值4月上旬到5月中旬逐渐下降，而5月中旬到5月下旬逐渐上升，且EVI值的变化幅度较大;油葵、葡萄、棉花的EVI值每个时间节点均呈现一定变化的趋势；草地和居民地的时序NDVI曲线特征较为相似，而时序EVI曲线较为不同，可说明2种地物的差异性；裸土的时序EVI曲线变化较为平缓，

# 3讨论

# 3.1方法应用

根据上述基于时序光谱及植被指数特征构建的方法自动识别地表覆被情况。综合分析时间序列NDVI曲线和时间序列EVI曲线的变化可以得知，NDVI曲线和EVI曲线趋势相同，其中NDVI值经过归一化处理，具有定量可比性，选用时间序列NDVI值对地表覆被信息进行提取，EVI值作为辅助信息。本文将已提取的2016年时间序列地表覆被的NDVI值作为匹配模板，将2018年时间序列地表覆被的NDVI值作为待分类样本。基于典型样本建立的匹配模板与2018年12个有效时相进行特征匹配，根据欧氏距离和最近邻原则判定2018年NDVI影像的每个像元对应的类别，完成2018年阜康研究区的地表精细类别填图(图6c)。如图6c所示可知，

# 干辛区地理

![](images/1d24c87cf1f051165809851f35a4b895bb37cf9ecea1faec9e55ca2677bab079.jpg)  
图62018年阜康研究区的地表覆被分类  
Fig.6Land covers classification ofFukang in 2018

该研究区的主要农作物主要包括小麦、油葵、玉米、水稻、葡萄和棉花，其中玉米种植面积较多，零星分布棉花和水稻的种植面积均较小，葡萄主要集中分布在西北部地区。东北部地区的圆形地块是由于干旱区农业灌溉技术管理模式的田块。此外，草地和裸土相间分布，居民地包括建筑物、道路、园林绿化等。

# 3.2地表覆被验证

因本区域精细到作物种类的高分辨率地表覆被填图未有开放产品可做横向对比验证，我们采取空间采样的考察验证。以谷歌地图和新疆生态与地理研究所提供的野外实地考察照片对2018年地表覆被分类结果进行验证。在2018年地表覆被填图上随机选取100个 $1 5 0 ~ \mathrm { m } { \times } 1 5 0 ~ \mathrm { m }$ 的验证样本区域，参考谷歌地图地表覆被数据和野外实地考察照片对其进行人工目视验证，本文实地调查验证的作物包括水稻和葡萄(图6a、图6b)，由于这2种多年生作物在2018年和2019年种植区域基本保持不变，而其他农作物可能轮作而使种植区域变化，因此可以利用包含经纬度信息的实地考查作物信息进行分类精度验证。综合以上验证信息，采用混淆矩阵对其进行精度评价，根据选定的验证样本统计每种地物的像元个数，计算混淆矩阵，其分类总体精度达到 $9 7 . 2 \%$ ,Kappa系数达0.9655，计算得到各类别的生产精度和用户精度见表2。综合分析表2可以得到：本文所构建的提取地表覆被类别的规则在一定程度上降低“异物同谱”概率，提高了对地物的识别精度。其中小麦的时间序列曲线特征明显，其物候期与其他作物差异较大，故其分类精度较高；水稻和玉米虽在5月中旬存在较大差异，但其他时相特征规律较为相似，葡萄和棉花时序特征变化趋势较为相近，且由于各种作物长势的区别，每块农田受降雨、温度等影响，使得在一定程度上造成误分;裸土、草地和居民地三者曲线变化趋势较为相似，故在一定程度上造成了误分;复播和其他地物时序特征有较大差异，故其提取精度较高。

表22018年阜康研究区的地表覆被填图混淆矩阵  
Tab.2 Confusion matrix of surface cover mapping in Fukang research area in 2018   

<html><body><table><tr><td colspan="10">地表真实值</td></tr><tr><td></td><td>小麦</td><td>油葵</td><td>玉米</td><td>水稻</td><td>葡萄</td><td>棉花</td><td>裸土</td><td>草地</td><td>居民地</td><td>复播</td><td>总数</td><td>用户精度/%</td></tr><tr><td>分类结果 小麦</td><td>170</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>170</td><td>100.00</td></tr><tr><td>油葵</td><td>0</td><td>298</td><td>7</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>306</td><td>97.39</td></tr><tr><td>玉米</td><td>0</td><td>9</td><td>660</td><td>4</td><td>4</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>678</td><td>97.35</td></tr><tr><td>水稻</td><td>0</td><td>0</td><td>4</td><td>39</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>43</td><td>90.70</td></tr><tr><td>葡萄</td><td>0</td><td>0</td><td>3</td><td>1</td><td>175</td><td>2</td><td>0</td><td>0</td><td>0</td><td>0</td><td>181</td><td>96.69</td></tr><tr><td>棉花</td><td>0</td><td>0</td><td>2</td><td>0</td><td>2</td><td>45</td><td>0</td><td>0</td><td>0</td><td>0</td><td>49</td><td>91.84</td></tr><tr><td>裸土</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>265</td><td>7</td><td>3</td><td>0</td><td>275</td><td>96.36</td></tr><tr><td>草地</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>7</td><td>677</td><td>2</td><td>0</td><td>686</td><td>98.69</td></tr><tr><td>居民地</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>5</td><td>5</td><td>93</td><td>0</td><td>103</td><td>90.29</td></tr><tr><td>复播</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>8</td><td>9</td><td>88.89</td></tr><tr><td>总数</td><td>171</td><td>307</td><td>676</td><td>44</td><td>182</td><td>48</td><td>277</td><td>689</td><td>98</td><td>8</td><td>总体精度=97.2%</td><td></td></tr><tr><td>生产者精度/%</td><td>99.41</td><td>97.07</td><td>97.63</td><td>88.64</td><td>96.15</td><td>93.75</td><td>95.67</td><td>98.26</td><td>94.90</td><td>100</td><td>Kappa系数=0.9655</td><td></td></tr></table></body></html>

# 4结论

本文基于Landsat8OLI影像的时序特征，构建信息提取方法对地表覆被信息进行提取。首先根据地物的纹理特征和阜康地区植被的物候信息选择典型地物样点，分析地表覆被时序波谱、NDVI和EVI特征，建立典型地物时序特征向量。根据特征向量匹配和最近邻原则自动确定像元的地表覆被类别，完成地表覆被分类图。最后，通过新疆生态与地理研究所野外实地考察和高分辨率卫星影像对随机选取的2500个样点数据建立混淆矩阵对其进行精度评价，其总体分类精度为 $9 7 . 2 \%$ ,Kappa系数达0.9655，信息捕获较为准确，分类效果良好。主要结论如下：

（1）Landsat时序光谱特征可较好的反映新疆阜康地区农作物的季相节律性和物候变化规律尤其捕获农作物在不同生育期的特征，为地物识别提供多维资料，且对复播作物的识别，潜在提供了提高识别精度的途径，降低“异物同谱”出现的概率，增加地物间的可分离性。

(2）新疆阜康地区是典型的绿洲农业，本文通过遥感影像时序特征匹配的自动识别方法，为及时更新农作物种植结构提供基础积累，对探索农田水循环及节水灌溉措施具有显示意义。

（3）本文通过时序特征匹配原则对有限范围典型地表覆被识别进行探讨，在时序遥感影像因云或气溶胶而缺失时，仍需继续加强方法研究，推演更多典型植被种类的时序特征，为在更广泛的区域推广方法打基础。

# 参考文献(References)

[1]宫鹏,张伟,俞乐,等.全球地表覆盖制图研究新范式[J].遥感学 报,2016,20(5): 1002-1016.[Gong Peng, Zhang Wei,Yu Le,et al. New research paradigm for global land cover mapping[J]. Journal of Remote Sensing,2016,20(5): 1002-1016.]   
[2] YuL,WangJ,Clinton N,et al.FROM-GC:3O m global cropland extent derived through multisource data integration[J]. International Journal ofDigital Earth,2013,6(6):521-533.   
[3] 陈军,陈晋,宫鹏,等.全球地表覆盖高分辨率遥感制图[J].地理 信息世界,2011,9(2):12-14.[Chen Jun,ChenJin,Gong Peng,et al. High resolution remote sensing mapping for global land cover[J]. Geomatics World,2011,9(2): 12-14.]   
[4]高瑜莲,柳锦宝,柳维扬,等.近14a新疆南疆绿洲地区地表蒸 散与干旱的时空变化特征研究[J].干旱区地理,2019,42(4):

# 干吴区地理

830-837.[Gao Yulian,Liu Jinbao,Liu Weiyang,et al. Spatio-temporal variation characteristics of surface evapotranspiration and drought at the oasis area of the southern Xinjiang in recent 14 years[J]. Arid Land Geography,2019, 42(4): 830-837.]   
[5]王文静,张霞,赵银娣,等.综合多特征的Landsat 8时序遥感图 像棉花分类方法[J].遥感学报,2017,21(1):115-124.[Wang Wenjing, Zhang Xia, Zhao Yindi,et al. Cotton extraction method of integrated multi-features based on multi-temporal Landsat 8 images[J]. Journal of Remote Sensing,2017,21(1): 115-124.]   
[6]Shuai Y M,Schaaf C,Zhang X Y,et al.Daily MODIS 50 m reflectance anisotropy direct broadcast (DB) products for monitoring vegetation phenology dynamics[J]. International Journal of Remote Sensing,2013,34(16): 5997-6016.   
[7]白燕英,高聚林,张宝林.基于Landsat 8影像时间序列NDVI的 作物种植结构提取[J].干旱区地理,2019,42(4):893-901.[Bai Yanying,Gao Julin,Zhang Baolin．Extraction of crop planting structure based on time-series NDVI of Landsat 8 images[J].Arid Land Geography,2019,42(4): 893-901.]   
[8]刘吉凯,钟仕全,梁文海.基于多时相Landsat 8OLI影像的作物 种植结构提取[J].遥感技术与应用,2015,30(4):775-783.[Liu Jikai, Zhong Shiquan,Liang Wenhai. Extraction on crops planting structure basedon multi-temporal Landsat 8 OLI images[J].Remote Sensing Technology and Application,2015,30(4): 775-783.]   
[9]熊元康,张清凌.基于NDVI时间序列影像的天山北坡经济带 农业种植结构提取[J].干旱区地理,2019,42(5):1105-1114. [Xiong Yuankang, Zhang Qingling. Cropping structure extraction with NDVI time-series images in the northern Tianshan economic belt[J].Arid Land Geography,2019,42(5): 1105-1114.]   
[10] 胡勇,刘良云,Caccetta Peter,等.光谱特征扩展的时间序列 Landsat数据地表覆盖分类[J].遥感学报,2015,19(4):648-656. [Hu Yong,Liu Liangyun,Caccetta Peter,et al. Extraction for land cover based on time series Landsat data of spectral characteristics [J]. Journal of Remote Sensing,2015,19(4): 648-656.]   
[11] 王颖洁,刘良云,王志慧.基于时序Landsat数据的三江平原植 被地表类型变化遥感探测研究[J].遥感技术与应用,2015,30 (5): 959-968.[Wang Yingjie,Liu Liangyun,Wang Zhihui. Land cover mapping based on Landsat time-series stacks in Sanjiang Plain[J]. Remote Sensing Technology and Application,2015,30(5): 959-968.]   
[12] 贺可,吴世新,杨怡,等.近40a新疆土地利用及其绿洲动态变 化[J].干旱区地理,2018,41(6):1333-1340.[He Ke,Wu Shixin, Yang Yi,et al.Dynamic changes of land use and oasis in Xinjiang in the last 40 years[J]. Arid Land Geography,2018,41(6): 1333-1340.]   
[13]王一航,夏沛,刘志锋,等.中国绿洲城市土地利用/覆盖变化研 究进展[J].干旱区地理,2019,42(2):341-353.[Wang Yihang, Xia Pei, Liu Zhifeng,et al. Research progress of urban land use/ cover change in the oasis cities of China[J].Arid Land Geography, 2019,42(2): 341-353.]   
[14] 汪小钦,邱鹏勋,李娅丽,等.基于时序Landsat遥感数据的新疆 开孔河流域农作物类型识别[J].农业工程学报,2019,35(16): 180-188.[Wang Xiaoqin, Qiu Pengxun,Li Yali,et al. Crop identification in Kaikong River Basin of Xinjiang based on time series Landsat remote sensing images[J]. Transactions of the Chinese Society of Agricultural Engineering,2019,35(16): 180-188.]   
[15]Roy DP,Wulder MA,Loveland T R,et al. Landsat 8: Science and product vision for terrestrial global change research[J]. Remote Sensing of Environment,2014,145: 154-172.   
[16] Masek JG,Vermote E F,Saleouset N E,et al.A Landsat surface reflectance dataset for north America,1990—200o[J]. Geoscience and Remote Sensing Letters,2006,3(1): 68-72.   
[17]刘焕军,康苒,Susan Ustin,等.基于时间序列高光谱遥感影像 的田块尺度作物产量预测[J].光谱学与光谱分析,2016,36(8): 2585-2589.[Liu Huanjun, Kang Ran, Susan Ustin,et al. Study on the prediction of cotton yield within field scale with time series hyperspectral imagery[J]. Spectroscopy and Spectral Analysis,2016, 36(8): 2585-2589.]   
[18] 杨存建,周成虎.TM影像的居民地信息提取方法研究[J].遥感 学报,2000(2):146-150,166.[Yang Cunjian,Zhou Chenghu. Extracting residential on the TM imagery[J]. Journal of Remote Sensing,2000(2): 146-150,166.]   
[19]白燕英,高聚林,张宝林.基于NDVI与EVI的作物长势监测研 究[J].农业机械学报,2019,50(9):153-161.[Bai Yanying,Gao Julin,Zhang Baolin. Monitoring of crops growth based on NDVI and EVI[J]. Transactions of the Chinese Society for Agricultural Machinery,2019,50(9): 153-161.]

# Land cover information retrieval from temporal features based remote sensing images

TIAN Yanjun'，SHI Ying'， SHUAI Yanmin1,23, YANG Jian',SHAO Congying'， FAN Lianlian2³， MA Honghong4,5

（1.Liaoning Technical University,Fuxin123ooo,Liaoning,China；2.Xinjiang Instituteof Ecologyand Geography, ChineseAcademyofciences,Urumqi830ol1,Xinjiang,China;3.ResearchCenterforEcologandEnvironmentofCentralAsia, Chinese Academyof Sciences,Urumqi 83oo11,Xinjiang,China;4.College of Agriculture,Shihezi University, Shihezi 832OO3,Xinjiang,China;5.Institute of Soil,Fertilizerand Agricultural Water Conservation, Xinjiang Academy of Agricultural Sciences,Urumqi 83Oo91,Xinjiang,China)

Abstract: Surface land cover is a special landscape feature modeled by natural and anthropogenic activities, significantly influencing global or local climate,hydrothermal circulation,material transport,and diversityof terrestrial ecosystem communities.Although numerous global or regional land cover datasets have been published, challenges exist in the retrieval of detailed surface cover information,especiallyon the automatic identification of crop types.Furthermore,the clasificationaccuracyof land-use and land cover maps needs improvement,specifically on crops in the agricultural management community. Using temporal Landsat 8 OLI multispectral images,we analyzed the spectral features of several dominant land cover types from temporal remote sensing images,with a specific emphasis on the unique phenological rhythm of individual plants and investigated the automatic retrieval of land cover types. We organized temporal Landsat 8 OLI surface reflectance data covering Fukang City of Xinjiang, China in the 2016 vegetation growth season. According to the Fukang statistical yearbook,prior knowledge of crop phenology,and the visible texture transition of vegetation in the growing season, we systematically selected the training samples of typical surface covers. We investigated the spectrum,the normalized difference vegetation index,and the enhanced vegetation index temporal curves of 10 typical ground objects,such as agriculture fields of wheat,corn,and cotton,to extract the feature vectors modulated by the growth phase of each crop type.The Euclidean distance was calculated to measure the similarity between unknown surface targets and apriori templates built-upusing the above feature vectors and assigned the land cover type according to the K-nearest neighbor rule.As acase study, we applied this approach to the land cover identification ofFukang using the time series of Landsat spectral data in 2018.We validated the retrieval accuracy using 2500 ground samples randomly collected fromthe land cover map of the investigated area,followed by the manual interpretation of the land cover types using the high-resolution images of 2018 and our field surveys.The results corelate well with the overall accuracy of $9 7 . 2 \%$ and the Kappa coefficient of 0.9655.Specifically, combined with the field investigation results,the method provides multi-dimensional data for ground object identification and potentially outlines the growth and development progress of diferent crops,enriches classification information,effectively reduces the phenomenon of foreign maters with the same spectrum ina singletime phase,and has potential advantages in improving the identification accuracyof re-plant fields.The time series spectral information captured bythis research well reflects the seasonal rhythm and phenological change law ofcrops in theFukang region of Xinjiang and provides a novel technical method for the needs of agricultural monitoring.

Keywords:time series remote sensingdata;phenologyofvegetation；spectral characteristics；normalized difference vegetation index; enhanced vegetation index; surface cover mapping