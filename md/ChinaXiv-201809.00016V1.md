# 1962一2015年宁夏平均气温和极端气温的变化特征

刘学智ʰ，李王成1,2,3，苏振娟，王帅ʰ，李晨¹，王霞¹

（1．宁夏大学土木与水利工程学院，宁夏 银川750021；2．西北退化生态系统恢复与重建教育部重点实验室,宁夏 银川750021；3．旱区现代农业水资源高效利用教育部工程研究中心,宁夏 银川750021)

摘要：气候环境是生态健康、社会持续发展中不可控因素,而温度是维持气候系统稳定，提供人类宜居环境的重要条件。为明确宁夏地区平均气温与极端气温事件,运用线性倾向、小波分析、相关分析等,对宁夏1962—2015 年平均气温和极端气温事件进行了分析。结果表明：1962年以来宁夏全区、北部、中部干旱带及南部山区以 $0 . 3 8 \mathrm { ~ \textdegree C }$ （20 $\cdot \ ( 1 0 \mathbf { a } ) ^ { \mathrm { ~ - ~ 1 ~ } } \circ \mathbf { 0 } . 4 2 \ \mathbb { C } \cdot \ b { ( 1 0 \mathbf { a } ) } ^ { \mathrm { ~ - ~ 1 ~ } } \circ \mathbf { 0 } . 3 6 \ \mathbb { C } \cdot \ b { ( 1 0 \mathbf { a } ) } ^ { \mathrm { ~ - ~ 1 ~ } } \circ \mathbf { 0 } . 3 8 \ \mathbb { C } \cdot \ b { ( 1 0 \mathbf { a } ) } ^ { \mathrm { ~ - ~ 1 ~ } }$ 速度增温;冷暖气温主要存在 $2 0 \sim 3 2$ a、8\~19a $\cdot 2 \sim 7$ a的周期,主周期 $1 3 \mathrm { ~ a ~ }$ 和 $3 2 \mathrm { ~ a ~ }$ ,分别有8a与 $2 0 \mathrm { ~ a ~ }$ 的次周期;极端低温事件频率、持续时长低于高温事件，低温四季增幅大于高温,且冬季变幅更为突出。平均气温和极端高温的升高会加大宁夏地区的干旱程度,加剧全区气候的不平衡性,极端低温指数的减少会增加农田、森林等的病虫害，使生态系统进一步恶化，应做好相应防御措施。

关键词：气温；周期；变化趋势；极端气候指数；宁夏

人类生产生活与气候变化密切相关，近百年来全球气候显著变暖，海陆表面平均温度上升了0.85$\mathcal { \mathrm { C } }$ 左右，预计21世纪末全球平均地表气温将升高$1 . 1 \sim 6 . 4 \mathrm { ~ } ^ { \circ } \mathrm { C } ^ { [ 1 - 2 ] }$ 。气候变化带来的干旱、洪涝、雪灾等灾害日益频繁，极端天气现象造成的经济损失和社会不稳定也在加剧[3]。这对农业生产、作物布局和生态环境等具有重大影响[4]。全球尺度上，极端高温事件和低温事件分布呈增加和减少趋势，多数陆地区域的热浪持续时间、发生频率和强度已经增加。Brown 等[5]认为,全球暖夜数显著增加,霜冻日数减少，温度较差显著减少，地区变化速率差异性显著。我国对区域极端气温事件研究取得了重要进展,表明霜冻、结冰、冷夜和冷昼日数显著减少，暖夜、暖昼日数显著增多[6。我国华北、西北、西南、长江及黄河流域等地区极端气温变化与全国相一致[7-9]。王晓娟等[10]认为,西北区域为全国冬季两大极端低温事件中心之一;Deng 等[1认为，西北极端低温、高温呈上升趋势，1986年左右发生突变。宁夏地区干旱少雨、蒸发强烈、下垫面复杂多变，区域内形成了多种气候类型，是极端气候事件频发的地区[12],极端气候事件对宁夏的水资源、生态环境和社会发展造成了重要影响。以往学者虽对宁夏的极端降水事件、极端气温事件以及极端气候阈值等方面进行了研究[13-14],但针对宁夏平均气温变化周期、极端气温的变化特征还需进一步的认识。笔者运用线性倾向、小波分析、M-K检验等方法，分析了宁夏1962—2015年平均气温和极端气温的变化规律，为预测和预防宁夏地区极端事件灾害、指导农业发展、利用自然资源和保护生态环境提供参考依据。

# 研究区概况

宁夏是我国地形地貌较为复杂的地区之一，包含了山脉、高原、平原、丘陵、河谷等。其深居内陆，属大陆性半湿润半干旱气候。雨雪稀少，气候干燥，风大沙多。农业气象灾害频繁发生，对农业造成了极大损失。为进一步明确宁夏气温及其极端事件的变化特征，本文选取1962一2015年宁夏9个气象站逐日最高/最低气温及年平均气温资料，基于R语言的RClimdex计算“世界气象组织”推荐的其中14个极端气温指标，从时间尺度上对气温和极端事件的变化特征及未来趋势进行了分析。

# 2材料与方法

# 2.1 数据来源

利用中国气象网的气温资料，选取宁夏惠农、银川、陶乐、中宁、盐池、海原、同心、固原、西吉9个站点的逐日最高、最低和年平均气温，通过RClimDex重新进行质量控制： $\textcircled{1}$ 最低气温大于最高气温的按缺测值处理; $\textcircled{2}$ 超出均值3倍标准差的记为出界值，根据相邻台站的记录进行人工处理。为了方便进行空间分析,根据中国气象地理区划及宁夏地理区划，结合前人研究将其划分为宁夏引黄灌区、中部干旱带、南部山区。气象站及分区图如图1所示。

# 2.2 研究方法

基于RClimdex软件,通过逐日最高/最低气温、年平均气温计算14个表征温度意义的极端气候指数，按照气候分析通用方法，结合前人划分基础，将表征温度意义的极端气候指数分为4种类型[15（表1)。采用线性倾向率法、距平法、滑动平均法等对气温变化趋势与突变进行了分析;通过Morlet小波分析对气温序列变化的周期进行了分析。

![](images/8a9f5be3b86983e6e6beaa6cb6883759055be0dd78747c58dfd8195d43a65b72.jpg)  
图1研究区站点及气候区划  
Fig.1Distribution of meteorological stations and climatic regionalization in the study area

表1表征温度意义的极端气候指数分类与定义 Tab.1 Classification and definitions of extreme climatic indexes   

<html><body><table><tr><td>类别</td><td>名称(缩写)</td><td>定义</td><td>单位</td></tr><tr><td>绝对指数</td><td>霜冻日数(FDO) 结冰日数(IDO)</td><td>一年日最低气温<0℃的日数 一年日最高气温<0℃的日数</td><td>d d</td></tr><tr><td rowspan="4">相对指数</td><td></td><td>夏日日数（SU25）一年日最高气温>25℃的日数</td><td>d</td></tr><tr><td></td><td>炎热夜数（TR20）一年日最低气温>20℃的夜数</td><td>d</td></tr><tr><td>冷夜/昼日数 (TN/TX10P)</td><td>日最低/高气温<10%分位 值的日数</td><td>d</td></tr><tr><td>暖夜/昼日数 (TN/TX90P)</td><td>日最低/高气温>90%分位 值的日数</td><td>d</td></tr><tr><td rowspan="2">持续性 时间指数</td><td>热持续指数</td><td>连续6日最高气温在90% 分位值日数</td><td>d</td></tr><tr><td>(WSDI) 冷持续指数 (CSDI)</td><td>连续6日最低气温在10% 分位值日数</td><td>d</td></tr><tr><td rowspan="4">平均指数</td><td>作物生长期 (GSL)</td><td>连续6日>5℃的时间跨度</td><td>d</td></tr><tr><td>年/月最高气温</td><td>最高气温年/月平均值</td><td>℃</td></tr><tr><td>平均值(TMAX) 年/月最低气温</td><td>最低气温年/月平均值</td><td>℃</td></tr><tr><td>平均值(TMIN) 气温日较差</td><td></td><td></td></tr><tr><td></td><td>(DTR)</td><td>日最高气温与日最低气温之差℃</td><td></td></tr></table></body></html>

# 3结果与分析

# 3.1 平均气温变化

3.1.1平均气温变化趋势分析平均气温是研究气温变化的基础，对年平均气温分析可以明确地区气温变化的基本趋势。图2为1962—2015年宁夏平均气温年际变化趋势。由原始数据线性回归、标准距平、滑动平均看出，54a来宁夏地区平均气温明显上升。全区平均气温变化率为 $0 . 3 8 \mathrm { ~ \textdegree C }$ ：（10a）-',多年平均气温为 $8 . 1 9 \mathrm { ~ \textdegree C }$ ,其中有24a平均气温高于多年气温均值。1962—1988 年平均气温距平值均为负值，且1967年达到峰值，1995年开始标准距平为正值，平均气温逐年增大，且1998 年达正峰值。宁夏北部、中部、南部均上升，年际气候倾向率分别为 $0 . ~ 4 2 ~ \mathrm { { \sc ~ \mathcal { C } } ~ } \cdot ~ ( ~ 1 0 \mathrm { { a } } ~ ) \mathrm { { \Large ~ \cdot ~ } } 0 . ~ 3 6 ~ \mathrm { { \Large ~ \mathcal { C } } ~ } .$ (10a) $\mathbf { \Sigma } ^ { - 1 } \mathbf { \Sigma } , 0 . 3 8 \ \mathrm { ~ \textcircled ~ { ~ C ~ } ~ } \cdot \mathbf { \Sigma } ( 1 0 \mathbf { a } ) ^ { \mathrm { ~ - 1 ~ } }$ ,多年气温均值分别为$9 . 2 9 \mathrm { ~ \% ~ . 7 . 9 7 ~ \% ~ . 7 . 5 0 ~ \mathrm { ~ ‰ ~ } }$ 。其中，北部有24a的平均气温高于多年气温平均值，中部与南部分别有21a与 $2 2 \mathrm { ~ a ~ }$ 气温高于多年平均值，且1997年之后均大于多年平均值;宁夏北部、中部、南部年际平均气温标准距平值均在1998年达到正峰值，出现年平均最高气温。

12 (a)全区 气二线动平均 12 14(b)北部 气线平均14  
10 10 12 12  
8 8 10 10  
420 6 0.8x-66.78） 6 420 / 642 8 0.x-74260) 8 642  
本  
年 0 0  
-2 -2 -2 -2  
-4 -4 -4 4  
1960 1970 1980 1990 2000 2010 2020 1960 1970 1980 19902000 2010 2020  
年份 年份  
14 (c)中部 气 二线动平均 14 14(d)南部 气二线平均114  
12 12 12 12  
186 186 / / 186 186  
4 y=0.036x-64.09 均值=7.97℃ 4 平 本 4 y=0.038x-67.59均值=7.50℃ 4  
2 R=0.748 幅度=0.36℃·(10a)-1 2 距 年 2 R=0.787 幅度=0.38℃·(10a)-1 2  
0 0 0 0  
-2 -2 -2 -2  
-4 -4 -4 4  
1960 1970 1980 1990 2000 2010 2020 1960 1970 1980 19902000 2010 2020  
年份 年份

3.1.2平均气温周期规律分析本文采用 Morlet复小波来分析宁夏气温时间序列的尺度特征，揭示宁夏气温在不同时间尺度中的变化趋势。如图3a所示，气温冷一暖演变过程中主要有 $2 0 \sim 3 2$ a、8\~$1 9 \mathrm { ~ a ~ } \Omega \sim 7$ a 的不同周期。在 $2 0 \sim 3 2$ a 时间尺度上,该区主要经历了1984年偏暖期向偏冷期过渡及1994 年的回暖;8\~19a时间尺度经历了1970 年前的偏冷期,1970—1982 年的偏暖期，1982—1987 年的偏冷期,1987—1992 年的偏暖期，1992—1997 年的偏冷期及1997年之后的偏冷期；而 $2 \sim 7$ a尺度的变换在1975年之后表现较为稳定，未出现较大的波动。图3b为气温变化周期能量密度在时间域中的分布情况：20～32a的时间尺度周期变化最明显;10a以下时间尺度模值最小,该周期变化不显著;其他时间尺度表现出了周期变化不稳定。方差图3c表明，宁夏气温主要有 $3 2 \mathrm { ~ a ~ } , 1 3$ a和6a的时间尺度。说明 $^ { 3 2 \mathrm { ~ a ~ } , 1 3 }$ a和6a分别对应的时间尺度为第一、二、三主周期。由图3d可以得出：在不同时间尺度下,年平均气温存在平均周期与冷一暖更换的特征,在第二主周期尺度上，气温变化主要存在约8a的次周期，经历了6个冷一暖更迭;32a时间尺度的平均变化期在20a左右，约经历2个周期的冷一暖交替。

# 3.2表征温度意义的极端气候指数变化

3.2.1表征温度意义的极端气候指数年代/际特征

# （1）绝对指数变化

随全球变暖过程的持续，极端气温事件频繁发生，绝对指数对气温系统具有较大影响。如图4和表2所示，霜冻天数（FD0）、结冰天数（ID0)年际变化逐渐减少,倾向率分别为 $- 4 . 4 4 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ~ ) ~ } ^ { - 1 }$ 、$- 3 . 0 3 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ ,54a间,霜冻与结冰天数减少$1 5 \mathrm { ~ d ~ }$ 以上；暖事件夏季天数（SU25）与炎热夜数（TR20）均增加，年际变化斜率分别为 $3 . 3 3 \mathrm { ~ d ~ } \cdot$ (10 $\mathrm { \Delta ) a ) ~ ^ { - 1 } \Omega , 1 . 4 5 ~ d ~ \cdot ~ ( 1 0 a ) ~ ^ { - 1 } }$ 。距平表明FD0 在20世纪70年代呈增加趋势，80年代开始逐渐减少；ID0 在80年代以前呈减少趋势，而进入21世纪具有微弱的增加迹象；SU25表现出了整体增加局部浮动的趋势，而TR20在1962—2015年呈显著增加趋势，导致夜间高温明显。

# （2）相对指数变化

由图4和表2可知，冷夜/昼(TN10/TX10）日数均显著减少，年际变化斜率分别为－4.29d·(10a）-¹与 $- 2 . 1 1 \mathrm { ~ d ~ } \cdot \mathrm { ~ } ( 1 0 \mathrm { a } ) ^ { \mathrm { ~ } ^ { - 1 } }$ ,变化值在 $2 3 { \mathrm { ~ d ~ } }$ 与11d左右;而暖夜/昼（TN90/TX90）显著增加，斜率为$4 . 5 1 \mathrm { ~ d ~ } \cdot \ : ( 1 0 \mathrm { a } ) ^ { \mathrm { ~ } ^ { - 1 } } \cdot 3 . 1 3 \mathrm { ~ d ~ } \cdot \ : ( 1 0 \mathrm { a } ) ^ { \mathrm { ~ } ^ { - 1 } }$ ,增幅约 $2 4 \mathrm { ~ d ~ }$ 与$1 7 \mathrm { ~ d ~ }$ 。表明宁夏气温偏冷指数减小，而偏暖指数增

![](images/2a94cb5337cb7e60078a5003e5f1842b4404588e6a5216f757e92b483807424c.jpg)  
Fig.3 Wavelet analysis of average annual air temperature in Ningxia during the period from 1962 to 2015

![](images/ee769cef041f5d63e92fd0cedfcb3d473fda77103218ae58ffdd1b7b96767879.jpg)  
图31962—2015年宁夏年平均气温小波分析  
图41962—2015年宁夏表征温度意义的极端气候指数年代距平  
Fig.4Decadal anomalies of extreme climatic indexescharacterizing temperature signification in Ningxia during the period of 1962 -2015

# 表21962—2015年宁夏表征温度意义的极端气候指数年际M-K趋势

Tab.2Interannual M-K trend of extreme climatic indexes characterizing temperature signification in Ningxia during the period of 1962 -2015   

<html><body><table><tr><td>M-K检验</td><td>FD0</td><td>ID0</td><td>SU25</td><td>TR20</td><td>WSDI</td><td>CSDI</td><td>GSL</td></tr><tr><td>Z值</td><td>-5.991</td><td>-2.783</td><td>3.797</td><td>4.529</td><td>0.888</td><td>-4.991</td><td>4.349</td></tr><tr><td>幅度/[d·（10a）-1]</td><td>-0.444</td><td>-0.303</td><td>0.333</td><td>0.145</td><td>0.073</td><td>-0.111</td><td>0.444</td></tr><tr><td>变化趋势</td><td>√</td><td>√</td><td>→</td><td>→</td><td>→</td><td>√</td><td>→</td></tr><tr><td>M-K检验</td><td>TN10</td><td>TN90</td><td>TX10</td><td>TX90</td><td>TDR</td><td>TMAX</td><td>TMIN</td></tr><tr><td>Z值</td><td>-6.990</td><td>6.259</td><td>-4.141</td><td>4.260</td><td>-3.380</td><td>4.618</td><td>7.140</td></tr><tr><td>幅度/[d·（10a）-1]</td><td>-0.429</td><td>0.451</td><td>-0.211</td><td>0.313</td><td>-0.016</td><td>0.030</td><td>0.048</td></tr><tr><td>变化趋势</td><td>←</td><td>→</td><td>←</td><td>→</td><td>√</td><td>→</td><td>→</td></tr><tr><td>置信水平</td><td colspan="7">0.005</td></tr></table></body></html>

增加。由年代距平分析结果可以得出，冷夜与冷昼在年代间均显著下降，但在速率上有变缓趋势，而暖夜TN90p的变化特征则相反；对比这3个指数的变化特征，发现暖昼整体上增加，局部震荡，即在20世纪80 年代与2010—2015年间由增加突变为减少，增加极端气温的不稳定性。

# （3）持续性时间指数变化

作物生长期（GSL）与热持续指数（WSDI）显著上升，幅度分别为 $4 . 4 4 \mathrm { ~ d ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ) ~ } ^ { - 1 }$ 和0.73d·$( \mathrm { 1 0 a } ) ^ { - 1 }$ ,增值为 $2 4 \textrm { d } . 4 \textrm { d }$ 左右,表明升温在一定程度上对作物生产期有促进作用;相反，冷持续指数(CSDI)则在时间尺度内显著减少，年际变化率为$- 1 . 1 1 \mathrm { ~ d ~ } \cdot \mathrm { ~ } ( 1 0 \mathrm { a } ) ^ { \mathrm { ~ } ^ { - 1 } }$ ,相应减少日数为6d左右。即GSL变化强烈,且进入2000 年增加趋势更突出，年代幅度在 $1 0 \mathrm { ~ d ~ }$ 左右，但从2010 年开始减少；而冷暖持续指数(CSDI、WSDI)在年代间有波动变化：CSDI整体减少，但在2000一2009 年其表现出了增加趋势，对GSL产生了内在影响；WSDI则在20世纪 80年代和2010—2015 年局部减少。

# （4）平均值指数变化

年最高气温平均值(TMAX)和年最低气温平均值（TMIN)及日气温差（DTR）更能反映气温极端事件的变化特征。由图4与表2可知，DTR在 $1 1 . 5 3 \sim$ $1 4 . 2 3 ~ \mathrm { ^ { \circ } C }$ 之间波动，1962年开始逐渐减小，年际变化率为 $- 0 . \ 1 6 \ \mathrm { ~ \textcircled ~ { ~ C ~ } ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { { a } ~ ) ~ } ^ { \mathrm { ~ - ~ 1 ~ } }$ ,54a减少了 $0 . 8 6 \mathrm { ~ \textdegree C }$ ：TMAX和TMIN均呈增加趋势，年际气温倾向率分别为 $0 . 3 0 \mathrm { ^ { \circ } C } \cdot ( 1 0 \mathrm { a } ) \mathrm { ^ { \circ } \mathrm { ^ { - 1 } \mathrm { \Omega } } } { } _ { \mathrm { \circ } } 0 . 4 8 \mathrm { ^ { \circ } C } \cdot ( 1 0 \mathrm { a } ) \mathrm { ^ { \circ \mathrm { ^ { - 1 } \mathrm { \Omega } } } }$ ,变化幅度分别为 $1 . 6 2 \mathrm { ~ \textcircled { C } } . 2 . 5 9 \mathrm { ~ \textcircled { C } }$ 左右。DTR在20世纪90年代呈持续减少趋势，但到2000一2009年其表现出了增大的突变情况，到2010年之后有延续前期的减少趋势;TMAX年代变化较为平稳：在80年代之前均保持在 $- 0 . 5 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ，90年代之后开始增加，进入21世纪其维持在 $0 . 7 ~ \mathrm { ^ { 9 } C }$ 左右，预计未来年代际气温会稳中上升;而TMIN则呈近似线性增加，并且增加趋势显著。

3.2.2表征温度意义的极端气候指数季节性变化通过年最高/最低气温平均值，来分析极端气温季节性变化。由图5和表3可知，1962—2015年四

![](images/109b18fe052934801065857c0b262319b3fb337a108252baeca57998a3538261.jpg)  
图51962—2015年宁夏表征温度意义的极端气候指数季节性变化趋势Fig.5Seasonal trend of extreme climatic indexes characterizing temperature signification inNingxia during the period of 1962-2015

# 表31962—2015年宁夏表征温度意义的极端气候指数季节变化趋势

Tab.3Seasonal trend of extreme climatic indexes characterizing temperature signification in Ningxia during the periodof1962—2015   

<html><body><table><tr><td rowspan="2">M-K检验</td><td colspan="4">TMAX平均值</td><td colspan="4">TMIN平均值</td></tr><tr><td>春季</td><td>夏季</td><td>秋季</td><td>冬季</td><td>春季</td><td>夏季</td><td>秋季</td><td>冬季</td></tr><tr><td>Z值</td><td>3.514</td><td>3.126</td><td>4.126</td><td>3.470</td><td>5.304</td><td>6.080</td><td>4.648</td><td>5.648</td></tr><tr><td>幅度/[℃·（10a）-1]</td><td>0.034</td><td>0.020</td><td>0.035</td><td>0.049</td><td>0.048</td><td>0.043</td><td>0.041</td><td>0.072</td></tr><tr><td>变化趋势</td><td>→</td><td>→</td><td>→</td><td>→</td><td>→</td><td>→</td><td>→</td><td>→</td></tr><tr><td>置信水平</td><td colspan="6"></td></tr><tr><td></td><td></td><td></td><td></td><td>0.005</td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 表41962—2015年宁夏表征温度意义的极端气候指数季节性年代的距平值

Tab.4Anomalies of extreme climatic indexes characterizing temperature signification in Ningxia during the period of 1962—2015   

<html><body><table><tr><td rowspan="2">时段</td><td colspan="4">TMAX平均值</td><td colspan="4">TMIN平均值</td></tr><tr><td>春季</td><td>夏季</td><td>秋季</td><td>冬季</td><td>春季</td><td>夏季</td><td>秋季</td><td>冬季</td></tr><tr><td>1962 -1969 年</td><td>-0.158</td><td>-0.245</td><td>-0.795</td><td>-0.908</td><td>-0.561</td><td>- 0.941</td><td>-0.736</td><td>-1.604</td></tr><tr><td>1970s</td><td>-0.581</td><td>-0.333</td><td>-0.485</td><td>-0.436</td><td>-0.879</td><td>-0.5</td><td>-0.629</td><td>-1.083</td></tr><tr><td>1980s</td><td>-0.656</td><td>-0.467</td><td>-0.282</td><td>-0.499</td><td>-0.489</td><td>-0.29</td><td>-0.269</td><td>-0.218</td></tr><tr><td>1990s</td><td>-0.234</td><td>-0.05</td><td>0.688</td><td>0.688</td><td>0.361</td><td>0.106</td><td>0.139</td><td>0.773</td></tr><tr><td>2000-2009 年</td><td>1.082</td><td>0.662</td><td>0.372</td><td>0.637</td><td>0.894</td><td>0.747</td><td>0.57</td><td>1.048</td></tr><tr><td>2010-2015年</td><td>0.905</td><td>0.68</td><td>0.611</td><td>0.576</td><td>0.955</td><td>1. 129</td><td>1.264</td><td>1.304</td></tr></table></body></html>

FDO 0.74TDR 0.41 0.46TX10 0.52 0.7IDO 0.66 0 0.41 0.62CSDI 0.6 0.65 0 0.28 0.62 Corr  
TMIN -0.49-0.61 0.68 -0.43 -0.87 -0.92 1.00.5GSL 0.72 0 -0.31 -0.49 0 -0.75 -0.60  
TN90 0.6 0.71 0 -0.27 -0.51 0 -0.63 -0.61 -0.5-1.0  
TMAX 0.63 0.63 0.8 -0.5 -0.76 -0.8 0 -0.66 0.67TX90 0.89 0.6 0.63 0.73 0 -0.58 -0.5 0 0.63 0.51SU25 0.73 0.79 0.6 0.51 0.58 0 -0.33 -0.64 0.28 -0.5 -0.41  
TR20 0.5 0.52 0.52 0.56 0.49 0.63 0 0 0.45 -0.29 -0.48 0.55  
WSDI 0.33 0.37 0.72 0.6 0.35 0.36 0.49 0 -0.47 -0.37 0 -0.4 -0.32TTR0 S535 06XL XAAL 300 N sS G NI W CSSS OCI OIXL JIP IOD OINL

temperature signification

季平均最高/最低气温均增加。TMAX四季变幅由小到大为：夏季 $\left[ 0 . 2 \mathrm {  ~ \vec { C } ~ } \cdot \left( \mathrm {  ~ 1 0 a ~ } \right) \mathrm {  ~ \Gamma ~ } \right] .$ 、春季[0.34$\mathrm { ~ \textit ~ { ~ C ~ } ~ } \cdot \mathrm { ~ } ( \mathrm { ~ } 1 0 \mathrm { a ~ } ) \mathrm { ~ } ^ { - 1 }$ }、秋季 $\left[ 0 . 3 5 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } \right]$ 、冬季$\left[ 0 . 4 9 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } \right]$ ,其中春季和秋季变幅相近,而冬季的变幅更为突出。TMIN变化幅度由小到大为：秋季 $\left[ 0 . 4 1 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ) ~ } ^ { - 1 } \right]$ 、夏季 $\textstyle { \left[ 0 . 4 3 \ ^ { \circ } \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ } \right. }$ ：$\left( 1 0 \mathrm { a } \right) ^ { - 1 } \bigg ]$ 、春季 $\left[ 0 . 4 8 \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } \right]$ 、冬季[0.72$\mathrm { { ^ { q } C } \cdot ( 1 0 a ) ^ { - 1 } ] }$ ,表现出了冬季大幅增温。从相应季节变化阈值可见，TMIN四季增温幅度均大于

TMAX，且两者冬季变化更明显，这也是年值均增加的主要原因。

为进一步明确表征温度意义的极端气候指数季节性的年代变化趋势，计算了年代距平值，如表4所示：TMAX春季距平在20世纪90年代前持续减小，而后逐渐增加，在2000一2009 年达到最大值；夏季距平变化与春季基本一致，20世纪90年代至2000年表现出了较大的突变性;秋季呈明显的线性上升，在 2000一2009 年突然下降,之后又回升;冬季指数变化趋势基本与秋季相同，在整个时间轴上表现为缓慢上升。最低气温年代变化：年内四季变化均增加。值得注意的是秋季最低气温平均值存在一定波动，但整体呈增加的趋势。对比TMAX与TMNIN的季节性年代变化，可以发现在20世纪末21世纪初，两者表现出了相反趋势。这与21世纪全球变暖更明显的结论较为相符。

3.2.3表征温度意义的极端气候指数相关性采用R语言Spearman 相关分析法，对宁夏近54a表征温度意义的极端气候指数的相关性进行了分析（图6）。结果表明：极端气温指标GSL、WSDI、TR20、SU25、TX90、TN90及TMAX、TMIN之间均呈显著正相关,TX90和TMAX相关性最高，达到0.89;CSDI、ID0、DTR、FDO及TX10、TN10与前者的相关性，除DTR与SU25、TX90、TMAX具有微相关外，其余均呈负相关，且TN10与TMIN达到了极负相关（-0.92）;CSDI、ID0、DTR、FD0及TX10、TN10间的相关性除DTR与ID0、TX10有弱负相关，其余均呈正相关。DTR、CSDI与GSL、WSDI、TR20、SU25、TX90、TN90及TMIN均不相关，今后宁夏极端指数研究的DTR和CSDI不应作为重点。

# 4结论与讨论

（1）1962—2015年宁夏地区多年平均气温呈上升趋势。宁夏全区、北部灌区、中部干旱带和南部山区分别以 $0 . 3 8 \mathrm { ^ { \circ } C } \cdot ( 1 0 \mathrm { a } )  { ^ { - 1 } }  { , } 0 . 4 2 \mathrm { ^ { \circ } C } \cdot ( 1 0 \mathrm { a } )  { ^ { - 1 } }$ ，$0 . 3 6 \mathrm { ^ { \circ } C \cdot ( 1 0 a ) \ ^ { - 1 } \circ . 3 8 \mathrm { ^ { \circ } C \cdot ( 1 0 a ) \ ^ { - 1 } } }$ 的速度增温,且近20a增温效果更为明显。

（2）冷一暖气温演变的长短周期有 $2 0 \sim 3 2$ a、$8 \sim 1 9$ a $\cdot ^ { 2 } \sim 7$ a年； $2 0 \sim 3 2$ a周期变化最显著，10a以下周期特征较平稳；主周期 $1 3 \mathrm { ~ a ~ }$ 和 $3 2 \mathrm { ~ a ~ }$ 分别存在着8a与20a的次周期。

(3）表征温度意义的极端气候指数变化特征表明，1962—2015年极端气温冷指标和日较差呈下降趋势，极端暖指标均呈上升趋势。极端高温事件发生频率、增幅明显高于极端低温事件；低温事件四季增温幅度大于高温，且两者冬季的增幅更为突出。

影响气温变化的因素很多，且不同区域差异较大。就宁夏地区而言，气候分异的原因可能是地形因素造成的：宁夏北部多处于河套平原，中部干旱带降雨稀少、蒸发强烈，南部山区多为黄土丘陵区。有学者认为大气动力是中纬度地区气候变化的主要驱动力[16]。如西伯利亚西、北部春季的冷夜日数减少与偏北气流减少有关，南部暖昼日数增加与西南气流增多有关[17]。You 等[18]认为,夏季气旋在亚洲大陆的蒙古和贝加尔湖的加强，削弱了来自中国北部的西风急流，使宁夏持续干旱天数上升。另外，低气温的持续走低可能与AO 有关。关学峰等[19]指出，1990年之前AO指数呈增长态势，而后呈显著下降趋势;除此之外，可能与海拔、太阳黑子、月亮潮汐、中纬度西风和北大西洋涛动等有关。

# 参考文献（References）：

[1] Meehl G A,Tebaldi C.More intense,more frequent,and longer lasting heat waves in the 21st century[J].Science,20O4,305:994 -997.   
[2] IPCC.Climate change 2013:Managing the Risks of Extreme Events and Disaster to Advance Climate Change Adaptation[M].Cambridge :Cambridge University Press,2013.   
[3]陈建宇,赵景波.1960—2014 年内蒙古极端天气事件趋势分析 [J].干旱区研究,2017,34（5）:997-1009.[Chen Jianyu, Zhao Jingbo.Trends of extreme weather events in Inner Mongolia during the period of 1960 -2014[J].Arid Zone Research,2017, 34(5):997 -1009.]   
[4]Houghton JT,Ding Y,Griggs D J,et al. Climate Change 2001:The Scientific Basic[M].Cambridge: Cambridge University Press, 2001:156 -159.   
[5]Brown S J,Caesar J,Ferro C A T.Global changes in extreme daily temperature since 1950[J]. Journal of Geophysical Research-Atmospheres,2008,113（D5）:1 -11.   
[6]任国玉,封国林,严中伟.中国极端气候变化观测研究回顾与 展望[J].气候与环境研究,2010,15（4）:337-353.[Ren Guoyu,Feng Guolin,Yan Zhongwei. Progresses in observation studies of climate extremes an d changes in main land China[J]. Climatic and Environment al Research,2010,15(4）:337 -353.]   
[7］李佳秀.西北干旱区极端气候事件的变化特征与时空分布规 律[D].乌鲁木齐：新疆大学,2015.［Li Jiaxiu.Variation and Temporal and Spatial Distribution of Extreme Climate Events in the Arid Area of Northwest China[D]. Urumqi: Xinjiang University, 2015]   
[8］刘琳,徐宗学.西南5省市极端气候指数时空分布规律研究 [J].长江流域资源与环境,2014,23（2）:294-301.[Liu Lin, Xu Zongxue. Spationtemporal distribution of extreme climate indices in the five Southwestern Provinces of China[J].Resources and Environment in the Yangtze Basin,2014,23(2）:294-301.]   
[9］吴灿,赵景波,王格慧.黄河流域表征温度意义的极端气候指 数的气候演变特征分析[J].中国农业气象,2015,36(5）：525 -535.[Wu Can,Zhao Jingbo,Wang Gehui.Characteristic analysis of the climatic revolution in the Yellow River extreme temperature index[J]. Chinese Journal of Agrometeorology,2015,36（5）: 525 -535.]   
[10］王晓娟,沈柏竹,龚志强,等.中国冬季区域性极端低温事件分 类及其与气候指数极端性的联系〔J].物理学报,2013,62 （22）:438-448.[ Wang Xiaojuan,Shen Baizhu,Gong Zhiqiang, et al.The classifcationof winterregional extremelowtemperature events in China and their corresponding relationship to climatic indices extreme anomaly[J].Acta Physica Sinica,2O13,62（22）): 438 -448. ]   
[11]Deng H J,Chen Y N,Shi X,et al. Dynamics of temperature and precipitation extremes and their spatial variation in the arid region of Northwest China[J].Atmospheric Research,2014,138:346- 355.]   
[12］薛红喜,孟丹,吴东丽,等.1959—2009 年宁夏极端温度阈值变 化及其与AO指数相关分析[J].地理科学,2012,32（3）:380 -385.[Xue Hongxi,Meng Dan,Wu Dongli,et al.Extreme temperature threshold changes and its association with AO index in Ningxia Hui Autonomous Region of China in 1959-2009[J].Scientia Geographica Sinica,2012,32(3）:380-385]   
[13］孔祥伟,陶健红.近51a甘肃夏季气温和降水极端事件变化 [J].干旱区研究,2012,29(6）:965-971.[Kong Xiangwei,Tao Jianhong. Change of extreme temperature and precipitation events in Gansu Province in summer in recent 51 years[J].Arid Zone Research,2012,29(6) :965-971.]

[14]杨建玲，冯建民，闫军，等.宁夏高温气候特征及其大气环流异常分析[J].中国沙漠，2012，32(5）：1417-1425.[YangJianlin,Feng Jianming,Yan Jun,et al.Ningxia high-temperature cli-matic characteristics and analysis of abnormal atmospheric circula-tion[J].Journal of Desert Research,2012,32（5）:1 417-1 425.]

[15]杨晓静，徐宗学，左德鹏，等.云南省1958一2013年极端气温时空变化特征分析[J].长江流域资源与环境，2016，25（3）：524-536.[Yang Xiaojing,Xu Zongxue,Zuo Depeng,et al. Spati-otemporal characteristics of extreme air temperature in YunnanProvince during 1958-2O13[J].Resources and Environment inthe Yangtze Basin,2016,25(3) :524-536.]

[16]龚道溢，韩晖.华北农牧交错带夏季极端气候的趋势分析[J]. 地理学报,2004,59(2）:230-238.[Gong Daoyi,HanHui.Study onthe trend of extreme weather in the summer of Beijing and China[J].Acta Geographica Sinica,2004,59(2）:230-238]

[17]Fernandez-Montes S,Rodrigo F S,Seubert S,etal.Spring and summer extreme temperatures in Iberia during last century in relation to circulation types[J].Atmospheric Research,2013,127:154- 177.   
[18]YouQL,Kang SC,AguilarE,et al.Changes in daily climate extremes in China and their connection to the large scale atmospheric circulation during 1961 -2003[J].Climate Dynamics,2011,36 (11/12):2 399 -2 417.   
[19]关学锋,孙卫国,李敏姣,等.1965—2012 年新疆北部地区气候 变化及其对北极涛动的响应[J].干旱区研究，2016，33（4）：26 - 28.[Guan Xuefeng,Sun Weiguo,Li Minjiao,et al.Climate change in North Xinjiang and its response to Arctic Oscillation during the period of 196-2012[J].Arid Zone Research,2016,33 (4):26-28.]

# Change of Mean Temperature and Extreme Temperature in Ningxia during the Period of 1962—2015

LIU Xue-zhi $^ { 1 }$ ， LI Wang-cheng $^ { 1 , 2 , 3 }$ ， SU Zhen-juan1，WANG Shuai，LI Chen’，WANG Xia’ (1. School of Civil and Hydraulic Engineering,Ningxia University,Yinchuan 75oo21,Ningxia,China; 2.KeyLaboratory of Degenerated Ecosystem Restoration and Reconstruction in Northwest China of Ministry of Education,Yinchuan 750021,Ningxia,China； 3.Effcient Utilization of Water Resources in Modern Agriculture in Arid Area,Ministry of Education, Yinchuan 750021,Ningxia,China)

Abstract：Climate environment isoneofthemost volatilefactors in ecological healthand sustainable social development.Temperature is important for maintaining the stabilityof climate systemand providing a livable environment for human beings.In this study,the linear temperature trend,wavelet analysis and correlationanalysis were used to analyzethe change of average temperature and extreme temperature events in Ningxia during the period from 1962 to 2015.The results showed thatthe values of average temperature in whole Ningxia,the northernand central arid zones and the southern mountainous regions since 1962 were $0 . 3 8 ~ \mathrm { ^ { \circ } C \cdot ( 1 0 a ) ~ ^ { - 1 } , 0 . 4 2 ~ ^ { \circ } C \cdot ( 1 0 a ) ~ ^ { - 1 } , 0 . 3 6 ~ ^ { \circ } C } ~ \cdot$ （204 $( 1 0 \mathrm { a } ) ^ { - 1 }$ and $0 . 3 8 ^ { \circ } \mathrm { C } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 }$ respectively. There were the $2 0 - 3 2 \mathrm { ~ a } , 8 - 1 9$ a and 2 -7 a periods of temperature fluctuation,and also the8a and 2Oa sub-periods in the13 aand 32 a main periods,respectively.The ocurring frequencyof extremely low temperature was lower thanthatof extremely high temperature,thedurationof the former was shorter than thatof the latter,the seasonal increase of low temperature was higher than thatof high temperature, and the temperature fluctuation was the most significant in winter.Thedrought degree in Ningxia became more serious due to the increase of both average temperature and extremely high temperature,and the plant diseases and insect pests were increased because of the unbalanced climate change and the reduction of extremely low temperature, thus the ecosystems were further degenerated,so it is necessary to take some improvement measures.

Key words: temperature;period;change trend ; extreme climate index； Ningxia