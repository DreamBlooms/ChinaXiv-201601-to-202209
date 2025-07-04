# 水资源约束下的渭干河流域耕地适宜规模

柯映明1,2，沈占锋12，白洁2,34，李均力2,3,4，常存2,3,4，许泽宇1,2

（1．中国科学院空天信息创新研究院，北京100101；2．中国科学院大学，北京100049；3．中国科学院新疆生态与地理研究所荒漠与绿洲生态国家重点实验室,新疆 乌鲁木齐830011;4．新疆维吾尔自治区遥感与地理信息系统应用重点实验室,新疆 乌鲁木齐830011)

摘要：利用遥感、水文、气象、统计年鉴等数据,基于水量平衡原理建立以生态耗水为主要水资源约束条件的耕地适宜规模模型,以渭干河流域为研究对象,估算1990—2017年4期耕地适宜面积并评价其开发潜力。结果表明： $\textcircled{1}$ 1990—2017年渭干河流域耕地面积持续增加,其转化来源以灌木林、草地为主。 $\textcircled{2}$ 流域水源主要来自地表径流与可利用降水，流域耗水以生态耗水为主。 $\textcircled{3}$ 来水量、作物种植结构与节水灌溉是影响适宜耕地面积估算的主要因素。 $\textcircled{4}$ 1990 年耕地达到相对饱和状态;2000 年耕地水平不稳定,其扩张影响生态环境的平衡;随着作物种植结构调整与节水灌溉普及,2010、2017年实际耕地面积远小于其当年来水量下适宜耕地面积,未来耕地具有较大开发潜力。

关键词：水资源约束；耕地适宜规模；水量平衡；LUCC；生态耗水；渭干河流域

农业作为人类最广泛的土地利用活动之一，对调节气候变化和确保粮食安全起着至关重要的作用[1]。随着土地开发整治政策的发布、水资源利用效率的提高，新疆耕地面积持续增加，其可持续开发在未来我国粮食安全与耕地资源利用中将占据更加突出的地位[2]

水资源承载力概念由我国学者于20世纪80年代末提出，继而于90年代初期对水资源合理配置概念进行进一步阐述[3],国外往往以“可持续利用水量”“水资源的生态限度”“水资源自然系统的极限”“水资源紧缺程度指标”等来表述类似含义[4],其本质内涵是在有限水资源条件下人类社会增长的阈值界限，表现在现实生活中即为“以水定田、以水定工农业发展规模、以水定城市规模”的重要理论依据[5]。干旱区水资源是农业生产的重要因素之一，是决定绿洲稳定和发展的关键因子，绿洲的唯水性使得干旱区有水即为绿洲,无水即为沙漠[6-7]。由于气候条件的限制，在有限的水资源制约下只能孕育一定面积的绿洲,为使地区生态、农业等实现和谐稳定、高效、可持续发展,必须“以水定地”[7]。雷志栋等8将绿洲土地资源和水资源利用分为社会经济系统(灌溉地、城乡、道路及工程用地等）与自然生态系统(水面、洼地、林草荒地及绿洲内少量的沙丘戈壁等)两部分，其水资源配置最终体现在二者水量消耗的分配;刘苏峡等 提出流域内生态耗水主要形式是用于土壤蒸发、植被蒸散、地表水面蒸发和潜水蒸发;李卫红等[10]则在“适宜绿洲”的定义基础上提出适宜绿洲规模，以表示理论上能维持的一个相对稳定的最大规模绿洲生态系统的面积。农业灌溉用水是社会经济用水的主体[10],因此,在以自然生态系统中的生态耗水作为水资源约束条件下，核算流域社会经济系统中耕地的适宜发展规模，对实现农业可持续发展有着重要意义。

陈亚宁等[7依据水热平衡原理,建立绿洲适宜规模数学模型，测算塔里木河流域绿洲适宜规模以及耕地适宜面积，得出除和田河流域农业绿洲外，其余绿洲面积均超出水资源承载能力的结论;赵文智等[1]基于净初级生产力(NPP)与蒸腾系数,通过构建植被耗水模型，反演估算得出黑河中游绿洲生态系统消耗的灌溉补充水量;胡顺军等[12]依据水量平衡原理，计算得出渭干河流域绿洲可供蒸发蒸腾的水资源量、适宜的绿洲和耕地面积;张沛等[13]基于已实施的水资源分配方案与近10a的生态输水实践，以水量平衡为依据，探讨塔里木河“九源一干”的可承载最大灌溉面积;李卫红等[10]基于水文、气象等资料，运用水量平衡及水热平衡的方法估算和田河适宜绿洲规模以及适宜绿洲耕地面积。

目前，对适宜耕地规模的计算大多基于水量平衡原理，缺乏从遥感的角度将水量平衡估算所得的适宜耕地面积与遥感手段所获取的耕地历史实际数据进行对比研究与适宜性评价，且在流域可利用水量的计算过程中鲜有考虑因地物种类造成的降水可利用程度。本文基于1990、2000、2010年与2017年4期Landsat TM、OLI数据,实现渭干河流域土地利用信息提取，同时结合相应年份水文气象数据、统计年鉴以及水资源公报等，以水量平衡原理为基础，构建水资源约束下的耕地适宜规模估算模型，从而实现耕地适宜性评估及其开发潜力评价，并从适宜耕地开发方向、农业水利设施建设等角度进行讨论且给出建议。

# 1研究区概况

新疆渭干河流域地处 $8 1 ^ { \circ } 2 0 ^ { \prime } \sim 8 4 ^ { \circ } 4 0 ^ { \prime } \mathrm { ~ E ~ }$ $4 0 ^ { \circ } 0 0 ^ { \prime } \sim 4 2 ^ { \circ } 0 5 ^ { \prime } \mathrm { N }$ ,位于天山南麓,塔里木盆地北部,是一个典型且完整的山前冲洪积扇平原，辖阿克苏地区的库车、沙雅和新和3县[12]，流域面积达$2 . 7 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,农业人口占据较大部分[14]。该地区位于中纬度地区，年均气温 $1 0 . 5 \sim 1 1 . 4 ^ { \circ } \mathrm { C }$ ,年降水量 $5 0 . ~ 5 ~ \sim 6 6 . ~ 5 ~ \mathrm { \ m m }$ ,年均蒸发量达 $2 ~ 0 0 0 . ~ 7 ~ \sim$ $2 ~ 0 9 2 . 0 ~ \mathrm { m m }$ ,区域降水稀少，气候干燥，风沙频繁，蒸发量大，气温日差较大，光热资源丰富，属于典型大陆性暖温带极端干旱气候[15-16] O

流域主要分布有渭干河、库车河、英达里亚河、塔里木河干流以及部分细小支流，是该地区生态、农业、人民生产生活用水的主要来源。根据河流走向，流域以黑孜水库、兰干、阿拉尔为进水口流量监测水文站，英巴扎为出水口流量监测水文站，构成一个相对封闭的水量平衡循环系统。作为干旱区绿洲农业的典型代表，渭干河流域农作物以小麦、棉花、玉米、油菜为主，随着社会经济发展需求的提高，农业种植规模进一步扩大，水资源的短缺问题进一步显现[15],渭干河流域示意图如图1所示。

# 2 数据来源与研究方法

# 2.1 数据来源

本研究主要选取Landsat数据作为遥感解译的数据源，同时采用气象数据、水文数据、统计年鉴等作为耗水量估算的数据基础。根据Landsat数据的云量、质量、时相、条带号等基础信息进行筛选，选取1990、2000、2010年TM与2017年OLI共4个时期的Landsat数据，其中1990 年数据由于影像质量不佳导致数据缺失，因此采用相邻年份数据进行补充，数据空间分辨率为 $3 0 \mathrm { ~ m ~ }$ ,且研究区每一期数据由5景影像覆盖，该部分数据主要用来解译流域各类别地物面积及分布情况。气象数据包括相应4个时期的降水、气温、风速、湿度、日照等数据，数据来自于流域内各观测台站。水文数据包括阿拉尔、英巴扎、黑孜水库、兰干4个水文站点的年径流数据，时间跨度为1990一2017年，该部分数据不仅用于耗水量估算，而且用于地区年河川径流丰、平、枯的评估，该数据来自水文统计年鉴。统计年鉴数据包括研究区的阿克苏地区及其下属3个主要县市（库车县、沙雅县、新和县)的人口统计数据、国民生产总值、农业种植结构数据等，该部分数据用于生产生活、工业等方面的耗水估算，该数据来自相应年份的《新疆统计年鉴》。

![](images/27bb5b39628ead095e0f6b85ea76d7f5458e3d6e2720ae701c227386ebbdf9e9.jpg)  
图1渭干河流域示意图  
Fig.1The sketch map of basin of Ugan River

# 2.2 研究方法

2.2.1土地利用信息提取土地利用变化特征在本文模型中是最重要的因素之一，其中生态耗水、可利用降水量等的估算均以各类地物面积及其变化为基础，且渭干河流域耕地的时空变化特征是评价其适宜规模的重要参考，同时有助于对耕地开发方向等提出建议。

研究区主要分布于渭十河卜游冲积扇平原区及塔里木河干流上游河谷平原区，地下水位较高，土壤在强烈的蒸发作用下盐渍化现象明显[17]。笔者结合干旱区地物特点以及研究需要，根据最新《土地利用现状分类》[18]中的分类体系，将研究区地物分为9类：林地、草地、灌木林、湖泊水库、河流水渠、湿地、耕地、人工地表以及其他地物。利用ENVI5.3以及面向对象分类软件eCongnition，根据不同地物的光谱、纹理等特征,结合 NDVI、NDWI等归一化地物指数，构建土地利用解译规则集，采用自动分类解译与人机交互判读相结合的方法获取1990、2000、2010年和2017年4期研究区土地利用类型图（图2）。通过随机点验证的方式，结合2010年野外实地验证点与高分影像验证点，对4期数据进行精度评定与数据检查，整体解译精度均达到 $90 \%$ 以上。

2.2.2水资源约束下的农业耗水模型构建根据吴炳方等[19]提出的耗水平衡分析方法,以多个数据源为基础分析渭干河流域的水资源供给与消耗过程。生态系统最主要水分来源为降水、径流、土壤水分以及地下水,最主要水分消耗则来自蒸散发[20]笔者基于生态系统的水量平衡原理，从地表径流、地下水、生态耗水、生活用水等角度分析研究区的水资源利用结构；并在确保生态用水的情况下，估算可利用的农业用水量、构建水资源约束下的耕地适宜规模评价体系（图3）。

![](images/28d0b08588a282fc56d79f1f7bbeaeb43d27a550f9d03472e426dde9ea07a934.jpg)  
图21990—2017年4期渭干河流域土地利用状况  
Fig.2Land use maps of the basin of Ugan River in four periods during 1990-2017

根据渭干河流域来水量与耗水量，构建该地区水量平衡方程，从而估算 $1 9 9 0 \ 、 2 0 0 0 \ 、 2 0 1 0 \ 、 2 0 1 7$ 年各年度农业种植业耗水量，水量平衡方程如下。

$$
W _ { \mathrm { f } } = W _ { \mathrm { r } } + W _ { \mathrm { u } } + W _ { \mathrm { p } } - W _ { \mathrm { e } } - W _ { \mathrm { l } } - W _ { \mathrm { s } } - W _ { \mathrm { i } }
$$

式中： $\textstyle \mathbf { W } _ { \mathrm { f } }$ 为计算时段内农业种植业耗水量; $\smash {  { W _ { \mathrm { r } } } }$ 为计算时段内地表径流量； $W _ { \mathrm { u } }$ 为计算时段内不重复的地下水资源量； $W _ { \mathrm { p } }$ 为计算时段内可利用降水量; $\boldsymbol { W } _ { \mathrm { e } }$ 为计算时段内生态耗水量; $W _ { \mathrm { l } }$ 为计算时段内生活用水量； ${  { W _ { \mathrm { s } } } }$ 为计算时段内农业畜牧业用水量； $\textstyle \mathbf { W } _ { \mathrm { i } }$ 为计算时段内工业耗水量,单位均为 $1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 。

地表径流量 $\smash { \mathbf { \mathcal { W } } _ { \mathrm { ~ r ~ } } }$ 与不重复的地下水资源量 $\boldsymbol { \ W _ { \mathrm { u } } }$ 从水文数据以及水资源公报中直接获取，生活用水量 $W _ { \mathrm { l } }$ 、农业畜牧业用水量 ${ \cal W } _ { \mathrm { s } }$ 与工业耗水量 $\mathbb { W } _ { \mathrm { i } }$ 从《新疆统计年鉴》《水资源公报》与《新疆维吾尔自治区行业用水定额》中计算所得。其中，地表径流量统计数值与相关文献[11-16，21-22]所统计的数值差异明显。由于渭干河流域与南部塔里木河干流流域相接,尤其是沙雅县正处于两流域交接地带，两流域耕地交错分布、紧密相连，且统计年鉴中最小统计单元以县为单位，本文在前人对渭干河绿洲区研究的基础上，将研究范围向南延伸到塔里木河干流河谷平原地带。

渭干河流域气候干旱，光热资源充沛，降水稀少,大气湿度低[12],但在水量平衡计算过程中,降水仍然不可忽略。可利用降水量 $W _ { \mathrm { p } }$ 主要采用降水、气温、风速、日照等气象站点数据,通过IDL插值、地形校正所得。相关研究表明，荒漠地区耗水量在数值上与有效降水量基本一致[]。本文将土地利用分类结果中除去人工表面及其他地物的6类作为所在区域可利用降水量分布区，利用对应年份的研究区降水数据与土地利用成果进行叠加计算，获取4期可利用降水量数据。

生态耗水量计算主要集中在林地、灌木林、湿地、湖泊水库、河流水渠、草地6类地物，且计算过程主要分为3大部分，3部分耗水量之和即为渭干河

![](images/e538c1bb4638aa327b4553931cbc83d738bc992ed772333cbe8cac0255950546.jpg)  
图3水资源约束的耕地适宜规模评价体系  
Fig.3The evaluation system of suitable scale of croplands with water resource constraint

流域生态耗水 $\boldsymbol { W } _ { \mathrm { e } }$ 。

首先，林地、灌木林、湿地、草地的生态耗水通过土地利用类型图统计的各地类面积以及对应的维护天然植物生长的最低耗水量进行叠加计算所得，其单位面积需水定额分别为 $3 \ 8 0 0 \ \mathrm { m } ^ { 3 } \cdot \ \mathrm { h m } ^ { - 2 } \cdot 2 \ 0 0 0$ （204号$\mathrm { m ^ { 3 } \cdot h m ^ { - 2 } \Omega \cdot 1 0 \ 7 3 8 \ m ^ { 3 } \cdot \ h m ^ { - 2 } \cdot 2 \ 0 0 0 \ m ^ { 3 } \cdot \ h m ^ { - 2 \ [ 2 3 ] } \Omega }$ 。

其次，湖泊水库生态耗水主要通过水面蒸发的  
形式,且实际蒸散发量的精确计算困难[24]。本文利  
用彭曼公式计算得到基于插值的栅格气象要素集，  
并通过ArcGIS10.5对土地利用图中湖泊水库面积  
与相应的水面蒸发的叠加运算获取1990—2017年  
共4期湖泊水库水面蒸发耗水量，彭曼公式如  
下[25]。

$$
E T _ { \mathrm { 0 } } = \frac { 0 . 4 0 8 \varDelta ( R _ { \mathrm { n } } - G ) + \gamma \frac { 9 0 0 } { T + 2 7 3 } U _ { \mathrm { 2 } } ( e _ { \mathrm { s } } - e _ { \mathrm { a } } ) } { \varDelta + \gamma ( 1 + 0 . 3 4 U _ { \mathrm { 2 } } ) }
$$

式中： ${ E T } _ { 0 }$ 为潜在蒸发量 $( \mathbf { m } \mathbf { m } \cdot \mathbf { d } ^ { - 1 }$ ）； $R _ { \mathrm { n } }$ 为作物表面净辐射 $( \mathrm {  ~ M J ~ } \cdot \mathrm {  ~ m ~ } ^ { - 2 } \cdot \mathrm {  ~ d ~ } ^ { - 1 } )$ ； $G$ 为土壤热通量密度（20 $( \mathbf { M J } \cdot \mathbf { m } ^ { - 2 } \cdot \mathbf { d } ^ { - 1 }$ ）； $T$ 为温度 $( \mathcal { C } ) : U _ { 2 }$ 为风速( $_ { \mathrm { ~ m ~ } } \cdot$ $\mathbf { s } ^ { - 1 } ) : e _ { \mathrm { s } }$ 为饱和水汽压 $( \mathrm { \ k P a } ) ; e _ { \mathrm { a } }$ 为实际水汽压$( \mathrm { \ k P a } ) ; e _ { \mathrm { s } } - e _ { \mathrm { a } }$ 为饱和水汽压差（kPa）； $\Delta$ 为温度 $\mathbf { \chi } _ { t }$ 时饱和水汽压的曲线斜率( $\mathrm { \Delta h P a ~ } \cdot \mathrm { \mathcal { C } ~ } ^ { - 1 }$ )，是温度的函数； $\gamma$ 是干湿常数 $\mathrm { ^ { \prime } k P a \cdot \mathcal { C } ^ { \alpha - 1 } }$ ）。

最后，干旱区河流生态系统的生态需水存在一个保证其流域生态系统稳定性的生态水量临界阀值。在实际生态耗水过程中，耗水量接近该值时，生态系统基本趋于稳定，即维持内陆河河流河道生态系统平衡的水资源总量[26]。根据相关研究[27],在内陆河流，至少要用 $30 \%$ 的水量维系其健康生命的自然水循环过程。因此，对于河流地类的生态耗水，本文由地表径流的 $30 \%$ 计算所得。

为分析流域耕地适宜性，利用农作物种植结构数据与土地利用分布，结合该地区不同灌溉手段下的各作物灌溉定额，以计算所得的农业种植业耗水量为基础，计算不同灌溉保证率下的适宜耕地面积。由于渠道两岸防护林等对渠道渗漏水的消耗利用等因素，在遵循水量平衡原理及水循环规律下，“渠系利用参数"在本研究中不予考虑[12],且忽略膜下滴灌带来的土壤积盐爆发造成的大面积洗盐、压盐所消耗的水资源量的影响[28],不同灌溉保证率下的流域加权平均灌溉定额 $V _ { p }$ 计算公式如下：

$$
\begin{array} { r } { V _ { p } = \sum _ { i } ^ { n } \left[ \left( 1 - k \right) C _ { i p } + k M _ { i p } \right] \times P _ { i } } \end{array}
$$

式中： $p$ 为灌溉保证率; $C _ { i p }$ 为第 $i$ 种作物在灌溉保证率为 $p$ 的情况下的常规灌溉定额； $M _ { i p }$ 为第 $i$ 种作物在灌溉保证率为 $p$ 的情况下的节水灌溉定额; $\boldsymbol { P } _ { i }$ 为第 $i$ 种作物占耕地面积的比例; $k$ 为节水灌溉面积占比。

根据上述水量平衡过程，结合各年份不同灌溉保证率下的流域加权平均灌溉定额，构建水资源约束下的耕地适宜规模估算模型：

$$
S _ { \mathrm { c } } = W _ { \mathrm { f } } / V _ { p }
$$

式中： $S _ { \mathrm { c } }$ 为相对应各条件约束下的适宜耕地面积。

# 3 土地利用变化特征

由图4可知，渭干河流域土地利用类型以林地、灌木林、草地、耕地以及荒漠为主体的其他类型土地为主，湿地、湖泊水库、河流水渠以及人工表面地类面积较小。1990一2017年，湿地、耕地与人工表面呈现持续增加的趋势，灌木林与其他用地呈现持续减少的趋势，林地、草地面积在经过近20a的持续减少后出现不同程度的增加现象，湖泊水库与河流水渠面积则出现大幅波动，具体表现如下：

（1）1990—2017年耕地、湿地与人工表面面积持续增加。其中，耕地、湿地增加幅度较大,1990—2017年增加幅度分别达到 $9 6 . 9 6 \%$ 与 $7 9 . 0 7 \%$ ，且整体趋势均较为平稳，并在2010一2017年出现较大幅度的增加,增加率达到 $30 \%$ 以上。人工表面面积变化幅度较为缓和，1990—2017年增加幅度仅为$3 5 . 7 7 \%$ ,增加幅度呈现先增强后减弱的特点，其中增幅最大的出现在2000一2010 年，达到 $1 8 . 8 9 \%$ 。

(2）林地、灌木林、草地与其他类型均呈现持续减少的趋势，27a期间减少幅度分别为 $1 1 . 6 5 \%$ 、$2 5 . 0 5 \%$ 、25. $70 \%$ 与 $1 . 5 6 \%$ 。其中,林地与草地减少强度在2010年以后得到有效遏制，2010—2017年二者面积减少幅度均为之前年份的 $5 0 \%$ 左右;灌木林减少幅度持续增强,2010—2017 年减少幅度最大达到 $1 2 . 5 8 \%$ ，而其他类型土地减少幅度先减弱后增强，2010—2017年减少幅度最大达到 $1 . 0 9 \%$ 0

（3）湖泊水库与河流水渠面积在27a间出现明显大幅波动，1990—2000年二者面积分别出现小幅减少，减少率分别为 $1 . 3 0 \%$ 与 $1 5 . 0 3 \%$ ,2000—2010 年二者面积则呈现大幅增加,增加率分别为 $6 0 . 1 6 \%$ 与$9 6 . 2 5 \%$ ,而2010一2017年二者面积呈现较大幅度减少,减少幅度分别为 $3 0 . 0 6 \%$ 与 $3 2 . 3 2 \%$ 。

![](images/fb3f0e76ee2ea91c5cb6e0d324238443348f20292def4aeb0aea4c5a4091b12e.jpg)  
Fig.4Statistical map of land use type change in the basin of Ugan River

![](images/5fdcab55dae306395436ea37bfff795d8e27f7749c85bc75c0abdc70936bf7c8.jpg)  
图4渭干河流域土地利用类型变化统计  
图5耕地转入占比变化  
Fig.5Proportion of croplands transferred from other objects

由图5可知，1990—2017年耕地主要由灌木林、草地二者转化而来，其次为林地以及其他用地。在1990—2000 年,灌木林与草地是新增耕地的主要来源，且二者转化比例较为均衡，分别占新增耕地面积的 $4 0 . 8 6 \%$ 与 $5 0 . 5 8 \%$ ,林地转化为耕地的面积占据新增耕地的 $6 . 4 1 \%$ 。2000—2010年，新增耕地主要来源于灌木林,其面积占据新增耕地的 $7 7 . 7 9 \%$ ，草地转化为耕地的力度大幅减弱，林地转化耕地的比例儿乎不变，与此同时，少量以荒漠为主的其他用地开始转化为耕地，该部分面积占据新增耕地面积的 $4 . 1 6 \%$ 。2010年以来，耕地扩张仍旧以灌木林为主，但在林地与以荒漠为主的其他用地上开垦力度逐渐增大，该部分在新增耕地面积占比增加到$1 5 . 4 4 \%$ 与 $5 . 7 5 \%$ ,同时少量水体及人工表面也转化为耕地，占比分别为 $3 . 2 5 \%$ 与 $4 . 0 3 \%$ 。

# 4水资源约束下的耕地适宜规模

基于上述渭干河流域土地利用变化特征，为保护渭干河流域自然生态系统，尤其是确保沙雅县境内胡杨林的来水充分，本文以生态耗水为主要水资源约束条件，对渭干河流域耕地适宜规模及开发潜力进行评估。由表1可知，流域1990一2017年水资源利用特征如下：

# 表11990—2017年渭干河流域水资源利用状况

Tab.1The utilization of water resources in Basin of Ugan River during 1990 -2017   

<html><body><table><tr><td></td><td></td><td>1990年</td><td>2000年</td><td>2010年</td><td>2017年</td></tr><tr><td>来</td><td>地表径流</td><td>44.90</td><td>46.65</td><td>64.77</td><td>45.55</td></tr><tr><td>水</td><td>地下水量</td><td>4.04</td><td>4.20</td><td>5.83</td><td>4.10</td></tr><tr><td>量</td><td>降水</td><td>16.50</td><td>14.54</td><td>22.04</td><td>23.69</td></tr><tr><td>/108m</td><td>合计</td><td>65.44</td><td>65.39</td><td>92.64</td><td>73.34</td></tr><tr><td></td><td>生态</td><td>自然植被</td><td>33.74 32. 63</td><td>29.89</td><td>28.11</td></tr><tr><td>耗水量</td><td>水面蒸发</td><td>2.35</td><td>2.21</td><td>3.58</td><td>2.31</td></tr><tr><td>耗</td><td>河道平衡</td><td>13.47</td><td>13.99</td><td>19.43</td><td>11.77</td></tr><tr><td>水</td><td>合计</td><td>49.56</td><td>48.83</td><td>52.90</td><td>42.19</td></tr><tr><td>量</td><td>其他人民生活耗水</td><td>0.22</td><td>0.31</td><td>0.41</td><td>0.43</td></tr><tr><td></td><td>/10m²耗水量 畜牧业耗水</td><td>0.07</td><td>0.09</td><td>0.06</td><td>0.07</td></tr><tr><td></td><td>工业耗水</td><td>0.00</td><td>0.01</td><td>0.10</td><td>0.27</td></tr><tr><td></td><td>合计</td><td>49.85</td><td>49.24</td><td>53.47</td><td>42.96</td></tr><tr><td>种植业可利用水量/10m</td><td></td><td>15.59</td><td>16.15</td><td>39.17</td><td>30.38</td></tr><tr><td>实际耕地面积/10 hm²</td><td></td><td>2.96</td><td>3.57</td><td>4.41</td><td>5.83</td></tr><tr><td>节水灌溉面积占比/%</td><td></td><td>0</td><td>0.64</td><td>42.95</td><td>75.07</td></tr><tr><td></td><td>小麦</td><td>40.43</td><td>31.47</td><td>18.78</td><td>13.54</td></tr><tr><td></td><td>玉米</td><td>24.87</td><td>12.70</td><td>14.10</td><td>2.78</td></tr><tr><td>农业种植</td><td>棉花</td><td>24.73</td><td>47.45</td><td>61.11</td><td>71.08</td></tr><tr><td>结构/%</td><td>油料</td><td>3.15</td><td>3.73</td><td>0.65</td><td>0.38</td></tr><tr><td></td><td>苜蓿</td><td>2.01</td><td>1.49</td><td>0.18</td><td>0.54</td></tr><tr><td></td><td>其他</td><td>4.81</td><td>3.16</td><td>5.17</td><td>11.67</td></tr><tr><td>加权平均</td><td>p =50%</td><td>344.87</td><td>358.55</td><td>319.69</td><td>289.23</td></tr><tr><td>灌溉定额/mm</td><td>p =75%</td><td>379.52</td><td>395.00</td><td>352.90</td><td>320.09</td></tr><tr><td>适宜耕地</td><td>p=50%</td><td>3.01</td><td>3.00</td><td>8.17</td><td>7.00</td></tr><tr><td>面积/10 hm²</td><td>p=75%</td><td>2.74</td><td>2.73</td><td>7.40</td><td>6.33</td></tr></table></body></html>

注 ${ \bf \sigma } : { \boldsymbol { p } }$ 为灌溉保证率。

（1）渭干河流域主要水源来自地表径流以及可利用降水，其中地表径流占来水量的 $6 0 \%$ 以上，降水约占 $20 \% \sim 3 0 \%$ 。其中，2017年以来新疆发改委结合当地农业发展水平与农民承受能力，对塔里木河流域管理局供水价格进行调整，供水价格增加近1.5倍，使2017年塔里木河干流来水丰富，而实际用水情况表明，渭干河流域地表径流来水组成中塔里木河干流用水量大大降低，仅为其余年份的 $5 0 \%$ 左右。根据国家《水文基本术语和符号标准》以及不同年份来水总量差异，对于渭干河流域，在1990—2017年，1990 年与 2000 年被确定为枯水年份,2010 年为丰水年份,2017 年为偏丰水年份[29]，流域总来水量依次为 $6 5 . 4 4 \times 1 0 ^ { 8 } \mathrm { ~ m ~ } ^ { 3 } . 6 5 . 3 9 \times 1 0 ^ { 8 }$ $\mathrm { m } ^ { 3 } \ 、 9 2 . 6 4 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 和 $7 3 . 3 4 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ 。

（2）除去农业种植业耗水，流域其余部分主要以生态耗水为主，人民生活耗水、畜牧业耗水与工业耗水等占据极小部分。生态耗水中自然植被生态耗水占比超过 $5 5 \%$ ,水面蒸发耗水占 $5 \%$ 左右，河道生态平衡耗水约占 $30 \%$ 。模型建立过程中以生态耗水充分供给为前提条件，对种植业可利用水量进行估算，因此生态耗水量变化会随自然植被类型面积的变化而发生小幅波动，维持河道平衡耗水量的变化会随流域地表径流的增减而随之发生改变。但从整体而言，为确保生态环境得到充分保护，在林地、灌木林、草地、湿地4类自然植被面积不发生剧烈改变的情况下，该模型中生态耗水量的变化强度不会太大。27a来，由于流域地区人口的不断增加以及工业水平的不断提高，人类生活耗水、畜牧业耗水以及工业耗水也相应增多。

（3）种植业可利用水量在枯水年份（1990 年、2000 年)处于较低水平（约 $1 6 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 } .$ ）,在偏丰水年份(2017年)可利用水量为 $3 0 . 3 8 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ,在丰水年份(2010年)可利用水量达到 $3 9 . 1 7 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ，处于较高水平。根据各年度农作物种植结构的不同以及节水灌溉普及度的差异，其加权平均灌溉定额有着较为明显的差异。例如在灌溉保证度为 $5 0 \%$ 的情况下，虽然，1990年与2000年棉花等耗水量较高的作物种植比例比2010 年、2017年低，但是由于灌溉方式落后，灌溉效益较低，其加权平均灌溉定额反而更高。由此可知，水资源约束下的耕地适宜规模估算模型中，来水量的变化、农作物种植结构的差异以及节水灌溉的普及程度是影响适宜耕地面积估算的主要因素。

根据图6，各年度耕地适宜面积与实际面积之差可知，1990 年耕地实际面积与适宜面积相差不大，在灌溉保证率为 $5 0 \%$ 的情况下实际面积略小于适宜面积，表明在该年份耕地面积在保证生态用水充分供给的情况下达到了接近饱和的状态。2000年由于来水量有限,相比较于1990年,其可用于农业种植业的水量仅增加 $0 . 5 6 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ,而在1990 年耕地面积已经达到相对饱和的情况下，其耕地面积依然呈现明显扩张趋势，增长率甚至达到 $20 \%$ 以上，表明耕地总体上已经处于不稳定状态，其面积的扩张已经影响到生态环境的平衡。

![](images/59b3d38bba0c5ea7c9bd6cf6665635fc6f4645d575303639fc7c52e32654e33c.jpg)  
图6耕地适宜规模评价  
Fig.6Evaluation of suitable scale of croplands

随着地区人口数量的不断增加，土地利用程度不断提高,耕地面积持续增加[30],在保证生态用水的情况下，改变农业灌溉方式以及调整农业种植结构成为实现耕地扩张的保障。为提高水资源利用效率，滴灌等能够提高田间水分利用效率，避免深层渗漏，减少棵间蒸发的灌溉模式在新疆农业灌溉上得到广泛运用[31]。2010 年以来,节水灌溉面积占比显著增加，使棉花等高耗水作物种植比例增加，但耕地加权平均灌溉定额仍明显下降，在来水较丰的情况下，2010年与2017年实际耕地面积远小于适宜耕地面积。在灌溉保证率为 $5 0 \%$ 的情况下，2010、2017年可开发耕地面积分别达到 $3 . 7 7 \times 1 0 ^ { 5 } \ \mathrm { h m } ^ { 2 }$ 与$1 . 1 7 \times 1 0 ^ { 5 } ~ \mathrm { h m } ^ { 2 }$ ,在灌溉保证率为 $7 5 \%$ 的情况下，可开发耕地面积分别达到 $2 . 9 9 \times 1 0 ^ { 5 } \ \mathrm { h m } ^ { 2 }$ 与 $5 \times 1 0 ^ { 4 }$ $\mathrm { { h m } } ^ { 2 }$ 。2017年,渭干河灌区南疆农业高效节水增收试点项目启动，通过对高效节水、大中型灌区续建配套与节水改造等措施,进一步提高农业灌溉效率，在一系列措施的实行与引导下，渭干河流域具有较大的耕地开发潜力。

# 5结论

（1）1990—2017年，耕地、湿地与人工表面面  
积持续增加，林地、灌木林、草地与其他用地面积持  
续减少，湖泊水库与河流水渠面积则出现大幅波动。（2）1990—2017年，渭干河流域耕地主要来源

于灌木林、草地的转化，其次为林地与以荒漠为主的其他用地的转化。耕地转入类型由1990—2000 年的草地、灌木林均等分配转变为2000—2017年以灌木林为主、草地为辅，同时林地与其他用地转化为耕地的面积比重逐渐增大，开垦荒漠也逐渐成为耕地扩张的手段之一。

（3）渭干河流域主要水源来自地表径流以及可利用降水，其中地表径流占来水量的 $6 0 \%$ 以上，降水约占 $20 \% \sim 3 0 \%$ 。除去农业种植业耗水，流域其余部分耗水主要以生态耗水为主，人民生活耗水、畜牧业耗水与工业耗水等占据极小部分。生态耗水中自然植被生态耗水占比超过 $5 5 \%$ ,水面蒸发耗水占$5 \%$ 左右，河道生态平衡耗水约占 $30 \%$ 。水资源约束卜的耕地适宜规模估算模型中，来水量的变化、农作物种植结构的差异以及节水灌溉设施的普及程度是影响适宜耕地面积估算的主要因素。

（4）1990年耕地实际面积与其适宜面积相差不大，达到相对饱和状态;2000 年耕地实际面积已经明显超过该年份适宜耕地面积的限制，耕地水平处于不稳定状态，耕地的扩张影响到了生态环境的平衡;随着农业种植结构的调整与节水灌溉普及度的提高，2010年与2017年实际耕地面积均远小于其当年来水量情况下的适宜耕地面积,在灌溉保证率为 $5 0 \%$ 的情况下，可开发的耕地面积分别达到$3 . 7 7 \times 1 0 ^ { 5 } \ \mathrm { h m } ^ { 2 }$ 与 $1 . 1 7 \times 1 0 ^ { 5 } ~ \mathrm { h m } ^ { 2 }$ ,在灌溉保证率为

$7 5 \%$ 的情况下，可开发耕地面积分别达到 $2 . 9 9 \times$ $1 0 ^ { 5 } ~ \mathrm { h m } ^ { 2 }$ 与 $5 \times 1 0 ^ { 4 } ~ \mathrm { h m } ^ { 2 }$ ,渭干河流域耕地开发潜力较大。

# 参考文献（References）：

[1］程维明，高晓雨，马廷,等.基于地貌分区的1990-2015 年中 国耕地时空特征变化分析[J].地理学报，2018，73（9）：1613- 1629.[Cheng Weiming,Gao Xiaoyu,Ma Ting,et al.Spatial-temporal distribution of cropland in China based on geomorphologic re gionalization during 1990-2015[J].Acta Geographica Sinica, 2018,73(9):1613-1629.]

[2］常存,包安明,李均力.塔里木河四源区耕地时空演变的驱动 分析［J].干旱区研究,2016,33（2）:239-245.［Chang Cun， Bao Anming,Li Junli. Spatiotemporal evolution of cultivated land in the headwaters of the Tarim River[J].Arid Zone Research, 2016,33(2):239-245.]

[3］李令跃，甘泓.试论水资源合理配置和承载能力概念与可持续 发展之间的关系［J].水科学进展，2000，11（3）：307-313.［Li Lingyue,Gan Hong.Remark on the relationship between water resources rational allocation,carrying apacity and sustainable development[J].Advances in Water Science,2000,11（3）:307- 313.]

[4]龙腾锐,姜文超,何强.水资源承载力内涵的新认识[J].水利 学报,2004（1）:38-45.［Long Tengrui,Jiang Wenchao,He Qiang.Water resources carrying capacity:New perspectives based on eco-economic analysis and sustainable development[J].Journal of Hydraulic Engineering,2004（1） :38 -45.]

[5]鲍超,方创琳.水资源约束力的内涵、研究意义及战略框架 [J].自然资源学报,2006,21（5）:844-852.[Bao Chao,Fang Chuanglin.On concept,significance and strategic framework for water resources constraint force[J]. Journal of Natural Resources, 2006，21(5):844-852.]

[6]Xu Hailiang,Ye Mao,Li Jimei.The water transfer effects on agricultural development in the lower Tarim River,Xinjiang of China [J].Agricultural Water Management,20O8,95:59 -68.

[7］陈亚宁,陈忠升.干旱区绿洲演变与适宜发展规模研究——以塔里木河流域为例[J].中国生态农业学报,2013,21（1)：134-140.［Chen Yaning,Chen Zhongsheng.Analysis of oasis evolu-tion and suitable development scale for arid regions:A case studyof the Tarim River Basin[J].Chinese Journal of Eco-Agriculture,2013,21(1):134-140.]

[8] 雷志栋,杨汉波，倪广恒,等.干旱区绿洲耗水分析[J].水利水 电技术,2006,37（1）：15-20.［Lei Zhidong,YangHanbo,Ni Guangheng,et al.Analysis on water consumption of oasis in arid area[J].Water Resources and Hydropower Engineering,2006,37 (1):15-20.]

[9］刘苏峡,莫兴国,朱永华,等.基于水量平衡的流域生态耗水量计算—以海河为例[J].自然资源学报，2004，19（5)：662-671.［Liu Suxia,Mo Xingguo,Zhu Yonghua,et al.A new methodfor ecological water consumption calculation and application inHaihe River Basin[J].Journal of Natural Resources,2OO4,19(5):662 -671.]

[10］李卫红，黎枫，陈忠升，等.和田河流域平原耗水驱动力与适宜 绿洲规模分析[J].冰川冻土，2011,33（5)：1161-1168.［Li Weihong,Li Feng,Chen Zhongsheng,et al.Analysisof driving force of water consumption in plain and suitable scale of oasis in Hotan River Basin[J].Journal of Glaciology and Geocryology, 2011,33(5):1161-1168.]

[11］赵文智，牛最荣,常学礼，等.基于净初级生产力的荒漠人工绿洲耗水研究［J].中国科学：地球科学，2010,40（10）：1431-1438.［Zhao Wenzhi,Niu Zuirong,Chang Xueli,etal.Water con-sumption inartificial desert oasis based on net primary productivity[J].Scientia Sinica(Terrae）,2010,40（10）:1431-1438.]

[12］胡顺军，宋郁东，田长彦，等.渭干河平原绿洲适宜规模[J].中国科学D辑：地球科学，2006，36（增刊2）：51-57.[HuShunjun,Song Yudong,Tian Changyan,etal.Suitable scale of Ugan riv-er plain oasis[J].Scientia Sinica(Terrae）,2006,36（Suppl.2）：51 -57.]

[13］张沛，陈超群，徐海量，等.塔里木河"九源一干”可承载最大灌溉面积探讨[J].干旱区研究,2017,34（1）：223-231.［ZhangPei,Chen Chaoqun,Xu Hailiang,et al. The bearable largest irriga-tion area in the basins of nine source streams and mainstream ofthe Tarim River[J].Arid Zone Research,2017,34（1）:223-231.]

[14］何珍珍，王宏卫,杨胜天，等.塔里木盆地中北部绿洲生态安全 评价［J].干旱区研究,2018,35（4）:963-970.［He Zhenzhen, WangHongwei,Yang Shengtian,et al.Evaluation on oasis ecological security in the Central-Northwest part of the Tarim Basin[J]. Arid Zone Research,2018,35(4) :963 -970.]

[15］陈大波，杨德刚,唐宏，等.渭干河流域农业水资源消耗强度及 影响因素[J].干旱区地理，2014，37（3）：509-519.ChenDa bo,Yang Degang,Tang Hong,etal.Agricultural water consumption intensity and effecting factors in Ogan River Basin[J].AridLand Geography,2014,37(3）:509-519.]

[16］何珍珍，王宏卫,杨胜天,等.渭干河一库车河绿洲景观生态安 全时空分异及格局优化[J].生态学报，2019，39（15）：1-10 [He Zhenzhen,Wang Hongwei,Yang Shengtian,etal.Spatial-tem poral differentiation and pattern optimization of landscape ecological security in the Ugan-Kuqa river oasis[J].Acta Ecologica Sinica,2019,39(15):1-10.]

[17］乔木，周生斌，卢磊,等.新疆渭干河流域土壤盐渍化时空变化及成因分析[J].地理科学进展，2012，31（7）：904-910.［QiaoMu,Zhou Shengbin,Lu Lei,et al.Causes and spatial-temporalchanges of soil salinization in Weigan River Basin Xinjiang[J].Progress in Geography,2012,31（7) :904-910.]

[18］GB/T21010-2017.中华人民共和国国家标准：土地利用现状 分类［S].北京：中国标准出版社,2017.［GB/T21010-2017. National Standard of the People's Republic of China:Current Land Use Classification[S].Beijing:Standards Press of China,2017.] [19］吴炳方，闫娜娜，蒋礼平，等.流域耗水平衡方法与应用[J].遥 感学报,2011,15(2）:281-297.[Wu Bingfang,Yan Nana,Jiang Liping,et al.A method of water consumption balance and application[J].Journal of Remote Sensing,2011,15(2）:281-297.] [20］郑红星，刘昌明，丰华丽.生态需水的理论内涵探讨[J].水科 学进展,2004,15（5）:626-633.［Zheng Hongxing,Liu Changming,Feng Huali.On concepts of ecological water demand[J]. Advancesin Water Science,2004,15(5）:626-633.]

[21］薛青,张亮.渭干河年径流量还原计算分析[J].水利科技与经 济,2013,19(8）:34-36.[Xue Qing,Zhang Liang.Reducing the calculationofannualrunoff intheWeigan River[J].Water Conservancy Science and Technology and Economy,2013,19（8）:34 -36.]

[22］胡顺军,田长彦,周宏飞,等.渭干河灌区陆面蒸发量估算[J]. 干旱区地理,2000,23（1）:67-71.[Hu Shunjun,Tian Changyan,Zhou Hongfei,et al.Estimation of land evaporation in the Weiganirrigated area,Xinjiang[J].AridLand Geography,2000, 23(1):67 -71.]

[23］王让会，宋郁东，樊自立，等.塔里木流域"四源一干"生态需水 量的估算[J].水土保持学报,2001,15（1）：19－22.[Wang Ranghui,Song Yudong,Fan Zili,et al.Estimation on ecological water demand amount in four sources and one main stream area of Tarim Basin[J].Journal of Soil and Water Conservation,2001,15 (1):19-22.]

[24］姚俊强，杨青，毛炜峰，等.西北干旱区大气水分循环要素变化 研究进展[J].干旱区研究,2018,35（2）：269-276.［YaoJun qiang,Yang Qing,Mao Weiyi,etal.Progress of study on variation ofatmospheric water cycle factors over arid region in Northwest China[J].Arid ZoneResearch,2018,35(2）:269-276.]

[25]Allen R G.Crop evapotranspiration-Guidelines for computing crop water requirements-FAO Irrigation and drainage paper 56［R]. FAO,Rome:1998:87 -210.

[26］陈锐，邓祥征，战金艳，等.流域尺度生态需水的估算模型与应用——以克里雅河流域为例[J].地理研究，2005,24（5）：725-731.［Chen Rui,Deng Xiangzheng,Zhan Jinyan,et al.Estima-tion model and application of the amount of eco-water demand;Acase study on Keriya river basin［J].Geographical Research,2005,24(5):725-731.]

[27］邓铭江,石泉.内陆干旱区水资源管理调控模式[J].地球科学 进展,2014,29（9）:1046-1054.［Deng Mingjiang,Shi Quan. Management and regulation pattern of water resource in inland arid regions[J].Advances in Earth Science,2014,29（9）:1046- 1054.]

[28］王振华，杨培岭，郑旭荣，等.膜下滴灌系统不同应用年限棉田 根区盐分变化及适耕性[J].农业工程学报，2014，30(4)：90- 99.[Wang Zhenhua,Yang Peiling,Zheng Xurong,et al. Soil salinity changes of root zone and arable in cotton field with drip irrigation under mulch for different years[J].Transactions of the Chinese Society of Agricultural Engineering（Transactions of the CSAE),2014,30(4):90-99.]

[29］GB/T50095-2014.中华人民共和国国家标准：水文基本术语和符号标准[S].北京：中国计划出版社，2014.［GB/T50095- 2014.National Standard of the People's Republic of China:Standard for Essential Terminology and Symbol in Hydrology[S].Beijing:China Planning Press,2014.]

[30］孙倩，塔西甫拉提·特依拜,张飞，等.渭干河-库车河三角洲 绿洲土地利用/覆被时空变化遥感研究[J」.生态学报，2012， 32（10）:3252-3265.[Sun Qian,Tashpolat Tiyip,Zhang Fei,et al.Dynamics of land use/cover changes in the Weigan and Kuqa rivers delta oasis based on Remote Sensing[J].Acta Ecologica Sinica,2012,32(10):3252-3265.]

[31］王振华,杨彬林，谢香文，等.灌溉制度对膜下滴灌甜菜产量及 水分利用效率的影响[J].农业工程学报，2019，35（8）：158- 166.［Wang Zhenhua,Yang Binlin,Xie Xiangwen,et al.Effects of different irrigation regimes of drip irrigation under plastic film on sugarbeet yield and water use efficiency[J].Transactions of the Chinese Society of Agricultural Engineering（Transactions of the CSAE),2019,35(8):158-166.]

# Analysis of suitable scale for cultivated land in the Ugan River Basin accounting for water resource constraints

KE Ying-ming $^ { 1 , 2 }$ ，SHENZhan-feng²，BAJe²34，Jun-l34，CHANGCun2，XUZe-yu (1.Aerospace Information Research Institute,Chinese Academy of Sciences,Beijing 10ol01,China; 2. University of Chinese Academy of Sciences,Beijing 100049,China; 3.State Key Laboratory of Desert and Oasis Ecology,Xingjiang Institute of Ecology and Geography, CAS,Urumqi 830011,Xinjiang,China ; 4.Key Laboratory of GIS & RS Application Xinjiang Uygur Autonomous Region,Urumqi 830o11,Xinjiang,China)

Abstract:Based on multi-source data including remote sensing,hydrometeorology,statistical yearbooks,and agricultural irrigation,a suitable scale model for cultivated land under water resources constraints isconstructed based on the principleof water balance.Considering the case of the Ugan River Basin,the suitable scale of cultivated land in 1990,20O0,2010and2017 was estimated,andthe potentialof cultivated land development with ecological water consumption as the main water resource constraint was evaluated.The results show that:（1）From 1990 to 2017, cultivated landarea in the Ugan River Basin continuallyincreased,primarily from theconversion of shrubsand grasslands,followed bythe conversion of land dominated by forestsand desert.Since 20lO,oneof the primaryreasons for the expansionof cultivated land is the gradualtransformation of wasteland intocultivated land.（2）The waterin the Ugan River Basin mainly originates from surface runoffand precipitation.Surface runoff accounts for more than $60 \%$ of the incoming water,whereas precipitation accounts for approximately $20 \% - 3 0 \%$ .With the exception of water consumption byagriculture,the remainderof the water consumption inthe basin is basedon ecological water consumption,of which natural vegetation accounts for more than $5 5 \%$ ,surface water evaporation for approximately $5 \%$ ,and water consumption by the ecological balance of the river for around $30 \%$ .Water consumption by the population of theregion,including for animal husbandry and industrial usage,accounts for avery small portion.（3) In the suitable scale estimation model for cultivated land under constrained water resources,changes of incoming waterquantity,thediferenceofcrop planting structure,and the useof water-saving irigation facilities are the principal factors affecting the estimationofcultivated land area.(4）In199O,cultivated landarea wassimilar to itssuitable areaandreachedarelatively saturated state.In2Ooo,cultivatedland had significantly exceeded the limitof suitable cultivated landarea.Suchunstablelevelsof cultivated land,together with its expansion,affctedtheecological environment balance；with the adjustment of agricultural planting structure and increasing usage of water-saving irigation,the cultivated land area in 2O1Oand2O17 has become much smalerthan thesuitable cultivated land area consideringthe available water supply.Cultivated land in the Ugan River Basin has substantial potential fordevelopment.

Key words:water resources constraints；suitable scale of cultivated land；water balance;LUCC；ecological water consumption；basin of the Ugan River