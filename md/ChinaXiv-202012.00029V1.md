# 玛纳斯河流域绿洲区耕地扩张的CA-Markov模型参数敏感性分析

朱磊¹²，夏鑫鑫²，杨爱民²，靳含1,2(1．新疆农业大学草业与环境科学学院,新疆 乌鲁木齐830052;2．新疆土壤与植物生态过程实验室,新疆 乌鲁木齐830052)

摘要：元胞自动机模型是土地利用变化模拟最有效和常用的方法之一，其模拟精度受元胞大小、时间间隔和邻域结构及大小等参数的影响。以玛纳斯河流域绿洲区耕地为研究对象,基于1975年、1995年、2005年、2010年及2015年土地利用数据构建耕地扩张CA模型,定量分析CA模型的参数敏感性。结果表明：(1)CA模型模拟精度具有时空尺度依赖性,时间间隔越短,精度越高,其中时间间隔为5a的数量精度、位置精度及Kappa精度分别比时间间隔为20a的高 $1 3 . 8 9 \% . 2 . 6 3 \%$ 和 $8 . 4 9 \%$ ;空间尺度上,元胞大小越小,模拟精度越高,元胞大小为 $3 0 \mathrm { m }$ 的Kappa系数值(0.8671)高于 $1 2 0 \mathrm { m }$ 的模拟结果(0.8259)。(2）邻域结构及大小模拟结果表明,摩尔邻域模拟精度优于冯诺依曼邻域;同等邻域下，邻域大小为 $7 { \times } 7$ 模拟精度比 $3 { \times } 3$ 邻域模拟精度高， $7 { \times } 7$ 摩尔邻域是模拟耕地的最优选择。(3)耕地模拟结果表明,2020 年耕地面积较2015年相比减少 $1 4 9 . 2 9 \mathrm { k m } ^ { 2 }$ ,耕地占比已由2015年的 $6 7 . 4 0 \%$ 降至 $6 6 . 1 8 \%$ ，表现出因增长饱和而逐渐减缓的趋势。此研究可为全面了解元胞自动机模型敏感性提供一定的理论基础。

关键词：CA-Markov模型；土地利用变化；参数敏感性；耕地扩张；玛纳斯河流域

土地利用/覆被变化(land use and cover change,LUCC)是人类福祉与自然环境交互的纽带，是全球变化的重要组成部分[1-2]。土地利用变化模拟作为研究LUCC的主要内容之一，其形式已由静态向时空动态模拟转化[3],且逐渐形成了以经验-统计模型、概念机理模型及综合模型为主流的模拟模型[4-6]，如元胞自动机(cellularautomata,CA)模型、多智能体(multi-agent system,MAS)模型&和CLUE-S模型[9]等，上述模型在模拟不同尺度、环境下的土地利用变化中均表现出一定的优势。其中，CA模型是一种时间、空间、状态都离散，空间相互作用和时间因果关系都为局部的网格动力学模型，其实现了“自下而上”模拟复杂系统时空演化的过程，现已成为当前国际上土地利用模拟的常用模型[10]。

元胞大小、时间间隔和邻域结构及大小等是CA模型的重要参数，对LUCC模拟精度产生一定影响，因此，CA模型的参数敏感性研究一直是土地利用变化模拟所重点关注的问题[10]。模拟过程中，元胞大小可以反映数据空间尺度特征，元胞大小的不同会引起邻域等参数的变化，进而产生不同的模拟结果；时间间隔可反映元胞自动机模型迭代步长与现实世界时间的对应关系[；邻域结构及大小共同决定了中心元胞单元的元胞范围及数目[10-12]。然而,现有研究多关注单个参数的敏感性[1-1,3-16],忽视了土地利用变化模拟受多因素影响，不同的参数会对模拟结果造成相应的不确定性，因而，如何较为全面地定量分析多参数的敏感性进而优化模拟方案尚有待开展深入研究。

玛纳斯河流域属天山北坡经济带核心区域，为典型的山地-绿洲-荒漠生态系统(mountain-oasis-desertsystem，MODS)。其中，山地区是绿洲和荒漠的水源和物源，绿洲区广泛分布着大面积农田，荒漠区是绿洲形成与发育的背景环境和基质[17-18]。近年来，随着流域经济的迅速发展及农业的深度开发，流域内绿洲区耕地迅速扩张，天然绿洲大幅减少、人工绿洲显著增加，荒漠化现象加剧及林草地退化等现象频发[19-20]。鉴于此,本文以玛纳斯河流域绿洲区耕地为对象，定量分析元胞大小、时间间隔、邻域结构及大小等参数对CA模型模拟结果精度的敏感性，确定区域CA模型模拟参数的最优组合，模拟2020年玛纳斯河流域耕地分布，为提高基于元胞自动机模型的区域土地利用变化模拟精度提供一定的方法依据。

# A 研究区与研究方法

# 1.1 研究区概况

玛纳斯河流域位于天山北坡、准噶尔盆地南缘，地理坐标为 $8 4 ^ { \circ } 4 2 ^ { \prime } { \sim } 8 6 ^ { \circ } 3 3 ^ { \prime } \mathrm { E } , 4 3 ^ { \circ } 5 0 ^ { \prime } { \sim } 4 5 ^ { \circ } 5 8 ^ { \prime } \mathrm { N }$ 图1),地处干旱区内陆，属典型的温带大陆性气候,年均降水量 $1 0 0 { \sim } 2 0 0 ~ \mathrm { m m }$ ,且时空分布不均匀[21]。流域由南至北依次为山地、绿洲、荒漠，垂直景观带谱完整，东西方向依次分布着塔西河、玛纳斯河、金沟河等水系。行政上主要辖石河子市、玛纳斯县、沙湾县及克拉玛依市、奎屯市、和布克赛尔蒙古自治县和乌苏市部分区域。截止2016年，流域内人口已达$1 . 5 5 \times 1 0 ^ { 6 }$ 人，国民生产总值达 $1 . 3 7 \times 1 0 ^ { 1 1 }$ 元[22]

流域绿洲区是新老绿洲聚集地，其中，沙湾、玛纳斯老绿洲开发历史较长，以石河子为代表的新的农垦绿洲插花分布在两县之中，经过近40a的水土开发，且伴随先进滴灌技术的广泛应用，2015年玛纳斯河流域绿洲耕地面积是1975年的1倍以上[19-20.23],绿洲发展至今，现已成为新疆第四大灌区，在新疆农业生产中有举足轻重的地位[24]。

# 1.2 研究方法

1.2.1数据来源与处理数据包括土地利用数据集、距离数据集、其他要素数据集（含 ${ \geqslant } 1 0 ~ \mathrm { \% }$ 积温、降水量、DEM及坡度等）。

# （1）土地利用数据集

采用的遥感影像数据包括1975年Landsat-MSS影像，1995年、2005年、2010年Landsat-TM影像及2015年Landsat-OLI影像，成像时间均在7—8月，云量少，质量较高。采用1:100000地形图对2015年影像进行几何校正后作为参考图像，采用二次多项式转换方程对其他影像进行纠正，平均位置误差控制在0.5个像元以内，采用双线性内插法将图像重采样至 $3 0 \mathrm { m } { \times } 3 0 \mathrm { m }$ 。结合该地区地形图与土地利用特点，通过人机交互式解译获得玛纳斯河流域绿洲区五期耕地数据。其中，1975年和1995年解译结果分别采用20世纪70年代1:47000黑白航片、90年代彩色航片和地形图进行检验，2005年、2010年及2015年解译结果经野外调查和GoogleEarth历史高空间分辨率影像检验，采用分层随机抽样方法在研究区内随机选取300个样本点进行验证各期解译精度均达到 $8 5 \%$ 以上，满足土地利用变化研究需求。

![](images/f81ab6cd59adc4f5dfe3695f54b1fa10b8a835b74198ef0d5ae30545faaa1159.jpg)  
图1研究区示意及近40a耕地扩张  
Fig.1Location of the study area and nearly 4O years of cultivated land expansion

# (2）距离数据集

根据研究区内道路、水系、村镇及已有耕地等数据，基于ArcGIS平台分别生成距离道路、水系、村镇和已有耕地的栅格图层。

# （3）其他数据集

业 $0 \%$ 积温、降水量数据及DEM数据分别来源于资源环境数据云平台(http://www.resdc.cn/)与地理空间数据云(http://www.gscloud.cn/）,其中， $\mathrm { \ p s i o \ v c }$ 积温、降水量数据空间分辨率为 $1 ~ \mathrm { k m }$ ,DEM数据空间分辨率为 $3 0 \mathrm { m }$ 。上述数据中，距离数据集和其他数据集用于耕地模拟时约束性因子的构建。

1.2.2CA-Markov模型马尔可夫(Markov)模型具有无后效性和稳定性，即在 $_ { t + 1 }$ 时刻的土地利用类型状态仅取决于 $\mathbf { \Phi } _ { t }$ 时刻的状态[25],可由下式表示：

$$
S _ { ( t + 1 ) } = S _ { t } \times P
$$

式中： $S _ { ( t + 1 ) }$ 、 $\boldsymbol { S } _ { t }$ 分别表示 $\mathbf { \Lambda } _ { t + 1 , \mathbf { \Lambda } _ { \setminus } } t$ 时刻研究区土地利用类型状态向量； $P$ 是土地利用状态转移概率矩阵,其表达式及含义详见文献[25]。

元胞自动机模型是一种时间、空间、状态都离散，空间相互作用和时间因果关系都为局部的网格动力学模型[],现已被广泛应用于土地利用变化模拟研究，可用下式表示：

$$
\boldsymbol { S } _ { ( t + 1 ) } = f \left( \boldsymbol { S } _ { t } , \boldsymbol { N } \right)
$$

式中： $s$ 是元胞的状态集合； $\boldsymbol { S } _ { t } \setminus \boldsymbol { S } _ { ( t + 1 ) }$ 分别是 $t \setminus t + 1$ 时刻的系统状态结果； $N$ 是元胞的邻域范围； $f$ 是邻域范围内元胞单元相互作用的状态转移规则函数。

Markov模型着重探索时间尺度上LUCC变化特征与规律，难以预测土地利用的空间格局变化；CA模型关注地块、人群、环境等微观因子间的相互作用机制，但其主要着眼于元胞的局部相互作用，存在一定的局限性[26]。CA-Markov模型将马尔可夫链长时间序列预测的能力与元胞自动机模拟复杂系统空间变化的优势相结合，可实现动态、多情景模拟LUCC的能力，且具有较好的模拟精度[27]

基于IDRISISelva17.0平台，模拟过程中，分别提取1975—1995年、1995—2005年及2005—2010年土地利用转移概率，选取 $\mathrm { \gtrsim } 1 0 ~ \mathrm { \% }$ 积温、DEM、坡度、降水量、距离道路、水系、已有耕地及村庄的距离等空间距离变量作为模拟耕地的约束性因子，分别选取1995年、2005年及2010年水域和建设用地作为模拟的限制性因子，设置不同的元胞大小、时间间隔和邻域结构及大小分别模拟2015年耕地现状，并与2015年实际耕地(R)进行对比分析，进而选取CA模型模拟参数的最优组合对2020年耕地现状进行模拟。

# 1.2.3精度验证

（1）遥感影像分类精度可采用Kappa系数进行验证，计算公式如下：

$$
{ \mathrm { K a p p a } } = { \frac { P _ { \mathrm { { o } } } - P _ { \mathrm { { c } } } } { P _ { \mathrm { { p } } } - P _ { \mathrm { { c } } } } }
$$

式中： $P _ { \mathrm { ~ o ~ } }$ 为正确模拟比例； $P _ { \mathrm { ~ c ~ } }$ 是随机情况下的正确模拟比例； $P _ { \mathrm { { p } } }$ 为理想分类情况下的正确模拟比例。Kappa系数取值范围为[0,1],若Kappa $_ { = 1 }$ ,则两幅图一致;当 $\mathrm { K a p p a } \mathrm { \geqslant } 0 . 7 5$ 时,表明一致性较高;当Kappa≤0.4时，两幅图相差较大。

(2）模拟结果精度运用IDRISISelva17.0平台下CROSSTAB模块及VALIDATE模块对耕地数量变化和空间位置变化的模拟结果进行验证。VALI-DATE模块为IDRISI软件提供的一种改进的Kappa系数验证方法，能够同时兼顾数量和空间位置的验证。

(3）为验证模型模拟结果的合理性，研究基于2005年和2010年土地利用/覆被数据，利用Markov模型得到2005—2010年土地利用/覆被转移面积矩阵、转移概率矩阵，并选取距离道路的距离、距离水系(含河流、水库、湖泊)的距离、距离已有耕地的距离、距离村镇的距离 ${ \mathrm { \Omega } } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega } \mathrm { \Omega }$ 积温数据、降水量数据、DEM及坡度等8个影响因素制作转移适宜性图像集，进而对2015年耕地进行模拟。模型中，设置元胞大小为 $3 0 \mathrm { m }$ ，时间间隔为5a，迭代次数为5，邻域大小及结构为IDRISI17.0软件默认的 $5 { \times } 5$ 冯诺依曼。据上述，得到2015年耕地模拟结果，并与2015年实际耕地进行对比分析。结果表明，模拟结果（即元胞大小为 $3 0 \mathrm { m }$ 的模拟结果、时间间隔为5a的模拟结果)具有较高的可信度，可用于模拟2020年耕地。

# 2结果与分析

# 2.1元胞大小敏感性分析

本文对原始数据进行重采样，得到元胞大小分别为 $3 0 \mathrm { m } { \times } 3 0 \mathrm { m } . 6 0 \mathrm { m } { \times } 6 0 \mathrm { m } . 9 0 \mathrm { m } { \times } 9 0 \mathrm { m }$ 和 $1 2 0 ~ \mathrm { m } \times \$ $1 2 0 \mathrm { ~ m ~ }$ 的栅格数据集。以2005年作为起始年，将2005一2010年土地利用变化数据提取的土地利用转移概率作为转换规则。其中，CA-Markov模型中设置滤波器大小为 $5 { \times } 5$ ，迭代次数均为5，以此在4种空间尺度下对2015年玛纳斯河流域绿洲区耕地进行模拟，得到不同元胞大小下模拟结果(图2)。

![](images/5936a2d08fa7f4ef47c5e964ef5fc8128ede00b2136818b5f75dbd62e86f70cb.jpg)  
图2不同元胞大小下模拟结果  
Fig.2Simulation results under different cell sizes

由表1可以看出，随着元胞大小的增加，数量精度基本保持稳定不变，位置精度则随着元胞大小的增加也随之增加， $3 0 \mathrm { ~ m ~ }$ 的Kappa值高于其他元胞大小的Kappa值。其中不同元胞大小下模拟结果数量精度相差仅为 $0 . 0 2 \%$ 左右，基本处于稳定状态。就位置精度而言，当元胞尺度为 $1 2 0 \mathrm { m }$ 时，其共计包含16个 $3 0 ~ \mathrm { m } { \times } 3 0 ~ \mathrm { m }$ 的元胞，范围覆盖更大，因此，其位置精度也随之增大。元胞大小为 $3 0 \mathrm { ~ m } ( \mathrm { A } _ { 1 } )$ 时的Kappa系数最高，达到0.8671，当元胞大小从 $3 0 \mathrm { m }$ 增加至 $1 2 0 \mathrm { m } ( \mathrm { A } _ { 4 } )$ 时，Kappa系数总计下降 $4 . 1 2 \%$ 。其中,元胞大小由 $3 0 \mathrm { m }$ 增加至 $6 0 \mathrm { m } ( \mathrm { A } _ { 2 } )$ 时,Kappa系数下降 $4 . 2 2 \%$ ,呈现明显的下降趋势，但当元胞大小由$6 0 \mathrm { ~ m ~ }$ 增至 $9 0 { \mathrm { ~ m } } ( { \mathrm { A } } _ { 3 } )$ 及 $1 2 0 \mathrm { m }$ 时，Kappa系数略微表现上升趋势，这是由于在进行CA-Markov模拟时，会

# 表1不同元胞大小下模拟结果精度

Tab.1 Accuracy of simulation results under different cell sizes   

<html><body><table><tr><td rowspan="2">精度</td><td colspan="4">元胞大小/m</td></tr><tr><td>30</td><td>60</td><td>90</td><td>120</td></tr><tr><td>数量精度</td><td>0.8708</td><td>0.8710</td><td>0.8710</td><td>0.8709</td></tr><tr><td>位置精度</td><td>0.9009</td><td>0.9024</td><td>0.9034</td><td>0.9037</td></tr><tr><td>Kappa系数</td><td>0.8671</td><td>0.8249</td><td>0.8257</td><td>0.8259</td></tr></table></body></html>

出现元胞尺寸极限值的问题，即当元胞大小超出某一极限值时,Kappa系数虽相对较大,但其实际模拟结果的精度却不理想[28]

# 2.2时间间隔敏感性分析

将1975—2015年划分为3种不同时间间隔，长期（1975—1995—2015年， $\mathrm { B } _ { 3 } { = } 2 0$ ）、中期（1995—2005—2015年， $\mathbf { B } _ { 2 } { = } 1 0$ )和短期（2005—2010—2015年， $\mathrm { B } _ { 1 } = 5$ ),提取3种时间间隔下土地利用转移概率，分别以1995年、2005年、2010年为初始年，模拟20a $\mathbf { \nabla } _ { \cdot } 1 0 :$ a和5a时间间隔下2015年绿洲区耕地现状$\left( \mathbf { B } _ { 3 } , \mathbf { B } _ { 2 } , \mathbf { B } _ { 1 } \right)$ ，并与2015年实际结果(R)进行比较。其中,CA-Markov模型中设置元胞大小为 $3 0 \mathrm { m } { \times } 3 0 \mathrm { m }$ 滤波器大小为 $5 { \times } 5$ ，迭代次数分别为20、10和5，不同时间间隔模拟结果如图3所示。

基于不同时间间隔的模拟结果与2015年实际土地利用现状之间存在一定的差异(表2、图3）。20a耕地模拟结果 $\left( \mathbf { B } _ { 3 } \right)$ 与2015年耕地真实结果(R)相差最大，达到 $2 9 8 7 . 0 6 \mathrm { k m } ^ { 2 } ; 5$ a耕地模拟结果( $\left( \mathbf { B } _ { 1 } \right)$ （204最接近于真实结果，两者仅相差 $1 3 0 2 . 9 3 \mathrm { k m } ^ { 2 } ;$ ：10a耕地模拟结果 $\left( \mathbf { B } _ { 2 } \right)$ 与真实值相差 $1 4 6 8 . 4 1 ~ \mathrm { k m } ^ { 2 }$ 。结果表明，随着时间间隔的缩短，模拟精度不断增加，模拟结果更加趋向于真实化。

表2表明，随着时间间隔的增加，数量精度、位置精度及Kappa系数均随之下降，时间间隔为5a的

![](images/c2288011787ea7c8d0df23d2002461d5cc278d1b9629acab2c78891d89908436.jpg)  
图3不同时间间隔下模拟结果

# 表2不同时间间隔下模拟结果精度

Tab.2 Accuracy of simulation results at different time intervals   

<html><body><table><tr><td rowspan="2">精度</td><td colspan="3">时间间隔/a</td></tr><tr><td>5</td><td>10</td><td>20</td></tr><tr><td>数量精度</td><td>0.8708</td><td>0.8529</td><td>0.7319</td></tr><tr><td>位置精度</td><td>0.9009</td><td>0.8897</td><td>0.8746</td></tr><tr><td>Kappa系数</td><td>0.8671</td><td>0.8422</td><td>0.7822</td></tr></table></body></html>

模拟结果优于10a、20a模拟结果。

# 2.3邻域结构及大小敏感性分析

摩尔邻域和冯诺依曼邻域是元胞自动机模拟土地利用变化常见的两种邻域结构。其中，在标准摩尔邻域中，一个中心元胞共有8个相邻元胞，而在标准冯诺依曼邻域中，中心元胞只有4个相邻元胞。CA-Markov模型中设置元胞大小为 $3 0 \mathrm { m } { \times } 3 0 \mathrm { m }$ ，模拟初始年为2010年，迭代次数均为5，滤波器分别自定义选取 $3 \times 3 、 5 \times 5 、 7 \times 7$ 摩尔邻域及冯诺依曼邻域，依照上述参数对2015年绿洲区耕地进行模拟，不同邻域及大小模拟结果见图4、图5。

由不同大小下摩尔邻域和冯诺依曼邻域的模拟结果(表3)可以看出，模拟结果的数量精度保持不变，这是由于分辨率( $\left( 3 0 ~ \mathrm { m } \right)$ )均保持一致，且模拟结果中耕地的像元个数均为 $7 . 2 3 \times 1 0 ^ { 6 }$ 个左右，像元个数相差较小，因而其数量精度保持稳定。两种邻

![](images/2a6a5637f2b413a67289cbabb6ca09c02e4fd3b88b5446930ee630bd35cdec62.jpg)  
图4不同邻域大小下摩尔邻域模拟结果

![](images/6d1904ec766698dea5fe3a05501a1e6701cf1b1ffbbf6d4632b2ee362076518e.jpg)  
Fig.3Simulation results at different time intervals   
Fig.4Moore neighborhood simulation results for different neighborhood sizes   
图5不同邻域大小下冯诺依曼邻域模拟结果 Fig.5Von Neumann neighborhood simulation results under different neighborhood sizes

# 表3不同邻域及大小下模拟结果精度

Tab.3 Simulation results with different neighborhood and size accuracy   

<html><body><table><tr><td rowspan="2">精度</td><td colspan="3">冯诺依曼邻域</td><td colspan="3">摩尔邻域</td></tr><tr><td>3x3</td><td>5×5</td><td>7×7</td><td>3x3</td><td>5×5</td><td>7×7</td></tr><tr><td>数量精度</td><td>0.8708</td><td>0.8708</td><td>0.8708</td><td>0.8708</td><td>0.8708</td><td>0.8708</td></tr><tr><td>位置精度</td><td>0.8990</td><td>0.9009</td><td>0.9023</td><td>0.8994</td><td>0.9030</td><td>0.9042</td></tr><tr><td>Kappa系数0.8660</td><td></td><td>0.8671</td><td>0.8679</td><td>0.8662</td><td>0.8683</td><td>0.8690</td></tr></table></body></html>

域下的位置精度和Kappa系数均随着邻域大小的增加而增加。相同邻域大小下，摩尔邻域的位置精度分别比采用冯诺依曼邻域模拟精度分别高 $0 . 0 4 \%$ 、$0 . 2 1 \%$ 和 $0 . 1 9 \%$ ,摩尔邻域Kappa系数分别比冯诺依曼Kappa系数大 $0 . 0 2 \% . 0 . 1 2 \%$ 和 $0 . 1 1 \%$ $7 { \times } 7$ 的摩尔邻域是模拟区域耕地扩张的最优组合。

# 2.4最优参数下的绿洲区耕地预测

据上述分析可知，元胞大小为 $3 0 ~ \mathrm { m } { \times } 3 0 ~ \mathrm { m }$ 时间间隔为 $5 \textrm { a }$ 邻域结构及大小为摩尔邻域 $7 { \times } 7$ 的参数是模拟玛纳斯河流域绿洲区耕地的最优参数组合，且模拟达到了较好的效果，模拟方法及过程具有较高的可信度。结合以上参数，对2020年玛纳斯河流域绿洲区耕地进行模拟(图6)。

由图7可知，1975—2015年耕地表现为持续增加的趋势，占比由研究初期(1975年)的 $3 5 . 9 3 \%$ 增至研究末期（2015年）的 $6 7 . 4 0 \%$ ，累计涨幅达到$3 0 . 4 7 \%$ ,年均增幅为 $0 . 7 9 \%$ 。这是由于自1975年以来，流域水土开发逐渐加剧，大量未利用地被开垦，且伴随着先进滴灌技术的广泛应用，耕地扩张趋势

![](images/024d0ef31e770803ff20888c116e5b0467eb5e81cd4bd16e30aad073df21d18a.jpg)  
图62020年玛纳斯河流域绿洲区耕地模拟结果 Fig.6Cultivated land in Manas River Basin oasis region simulation result in 2020   
图71975—2020年玛纳斯河流域绿洲区耕地占绿洲区面积比  
Fig.7The area ratio of cultivated land to oasis area in the oasis area of Manas River Basin from 1975 to 2020

80%/ ： 区发设及8及：601地 1：40 制 13 B注 ： ：：：20 电 福 ： 1 电聘 ： ：： 三： ： ：： ：0 盟 ：： 注1975 1995 2005 2010 2015 2020年份

更为显著。由于加入了约束性因子及限制性因子，模拟目标年(2020年)的耕地占比略降至 $6 6 . 1 8 \%$ ，呈现出因增长饱和而逐渐减缓的趋势。

# 3讨论

元胞自动机模型对空间尺度、时间尺度、邻域结构及大小等均具有敏感性，多因素共同作用对模型的精准预测造成了一定程度的影响[10-12.28]

（1）通常情况下，多数模拟结果精度均随元胞大小的增加而下降[10,3,28-29],即元胞大小越精细,模拟结果越高;反之，,模拟结果精度则较低[]。但也存在不同的研究结果，如吴浩等[12]采用正交试验的设计，系统地分析了元胞自动机模型各尺度之间的关系以及尺度组合对模拟结果的影响，结果表明，元胞大小为 $6 0 \mathrm { ~ m ~ }$ 的模拟结果优于元胞大小 $3 0 \mathrm { ~ m ~ }$ ○这是源于其针对不同的元胞大小采用了不同的转换规则、邻域结构及大小，由于CA模型模拟精度受多因素的共同制约，因此，这可能是与本文结果有所差异的原因所在。

（2）时间间隔作为CA-Markov模型模拟土地利用变化的重要参数，与元胞大小、邻域结构及大小一起作用于CA-Markov模型,影响着模型的模拟精度。本研究分别选取 $2 0 \mathrm { a } , 1 0$ a和5a三种时间间隔模拟玛纳斯河流域绿洲区耕地现状，结果表明，时间间隔为5a的模拟结果优于 $1 0 \mathrm { ~ a ~ }$ 和 $2 0 \textrm { a }$ ，且模拟精度随着时间间隔的增加而降低，这与Sinha及Sa-mat等[14.30]研究结果一致。但王羊等[28]的研究结果却与本文结果不同，其选择深圳市龙华镇作为研究区，以1990年土地利用驱动力变量为初始条件，分别以5a和10a为时间间隔模拟1995年与2000年，结果表明模拟时间跨度越长，精度越高。导致结果出现差异的原因可能是政策因素所致，龙华镇的城市化过程主要发生在1990—2000年，于2000年基本达到稳定，在1990—1995年(即5a时间间隔)模拟过程中，模拟的建设用地与实际建设用地虽在数量上大致相等，但在空间分布上略有差异，导致模拟误差较大；而在1990一2000年(即10a时间间隔）的模拟过程中，由于城市化过程已基本完成，因此在空间分布上误差较小，进而模拟精度得到大幅提高。而近40a玛纳斯河流域耕地在不同时段内变化程度均有所差异，其中，1975一1995年期间，流域水土开发程度急剧下降,耕地扩张较为缓慢[31],导致20a模拟结果精度最低；1995—2005年，流域开始有计划地开发水资源，农田灌溉以集约、内涵挖潜为主,裸地大量开垦,大量弃耕地得到收复,耕地表现为持续缓慢扩增[32]，因此，10a模拟结果精度优于20a模拟结果；2005—2010年，流域开荒力度加大，且随着“三生用地"保护性政策的实施，生产生活用地(耕地和建设用地)转入量快速增加[33],耕地增速加快，从而导致5a模拟结果优于其他。耕地的变化受到经济、社会、人口、地理和政策诸多因素的影响，存在着不确定性和复杂性，因此模拟时间间隔的确定应考虑区域发展的历程和政策等相关因素。

（3）邻域结构及大小是CA-Markov模型模拟土地利用变化的重要参数之一，本文分别选取常见的摩尔邻域和冯诺依曼邻域及不同的邻域大小( $3 { \times } 3$ 、$5 { \times } 5 . 7 { \times } 7 .$ )定量分析CA模型对其的敏感性。结果表明： $7 { \times } 7$ 摩尔邻域是模拟土地利用变化时最优的邻域大小及结构。张亦汉和 $\mathrm { P a n }$ 等[10.34]的研究结果也证实了摩尔邻域模拟精度优于冯诺依曼邻域，这是由于在同一空间尺度下，摩尔邻域中角点(左上、左下、右上、右下)对中心元胞的影响高于冯诺依曼邻域(上、下、左、右)，而 $5 { \times } 5$ 冯诺依曼邻域包含摩尔邻域所有元胞(含左上、左下、右上、右下)。模拟精度会随着邻域角点的增加而增加，相同邻域结构下，随着邻域半径的增加，中心元胞的影响力增大，对模拟结果精度的提高起到了一定的促进作用[35]

本研究尚存在一定的不足： $\textcircled{1}$ 邻域结构仅选取了规则邻域(摩尔邻域及冯诺依曼邻域），未考虑不规则邻域对模型模拟精度有何影响，国外已有学者针对不规则邻域进行探索[3，取得了较好的模拟结果。 $\textcircled{2}$ CA-Markov模型的模拟精度一方面受到模型本身参数的影响，另一方面来源于数据源误差[35]。本文重在探究CA-Markov模型的参数敏感性特征，考虑到数据来源的一致性和完整性，仅选取了Landsat系列影像作为基础数据，较为全面地对模型参数敏感性进行了定量分析。然而，不同数据源的时间、空间分辨率等差异导致的模拟误差将会通过CA模拟过程传递。在进行土地利用变化模拟时，可通过对比选取不同的遥感数据源的"最佳尺度”[37]，进而提高模拟精度。因此，未来的研究有必要深入探讨多源数据与模型参数对土地利用变化模拟精度的影响机制。 $\textcircled{3}$ 水资源是制约干旱区耕地扩张的重要因素，其包含地表水(河流、湖泊、水库等)和地下水。研究初期(1975一1990年),流域内修建了蘑菇湖、大泉沟、夹河子等大、中、小水库20多座,农业灌溉以地表水为主，灌溉方式主要为畦灌沟灌；1990—1998年灌溉方式发展为渠库井结合灌溉，水库、灌渠的共同作用保障了耕地的持续灌溉；1998年后，流域高效节水灌溉(膜下滴灌)技术大面积广泛推广并应用,使得流域实现了省水、省劳力、省肥料，作物增产达 $10 \% { \sim } 2 0 \%$ 左右38。随着人口数量的不断增加,流域经济得到较快发展,地表水已难以满足工农业生产及城市生活，继而流域内大量广泛布井并开采地下水用以弥补,由于井眼数量难以统计,地下水开采量难以获取,取水量不尽相同,进而较难量化。故此,文章将地表水作为影响因素对耕地扩张进行模拟分析。此外，土地利用/覆被变化存在一定的不确定性及复杂性，需综合考虑自然、社会、经济及人文因素对LUCC产生的影响，故而在今后的研究中，可针对上述问题进行深人研究，以期达到更高的模拟精度,更好地揭示CA-Markov模型的敏感性规律。

# 4结论

（1）CA模型模拟精度具有时空尺度依赖性。就时间尺度而言，模型模拟的时间间隔越短，精度越高；空间尺度上，元胞空间分辨率越高，模型的模拟精度越高。基于5a时间间隔、元胞大小为 $3 0 \mathrm { ~ m ~ }$ 的模拟结果更接近于实际情况，

(2）邻域结构及大小模拟结果表明，冯诺依曼邻域和摩尔邻域的位置精度和Kappa系数均随着邻域大小的增加而上升。其他条件相同的情况下，摩尔邻域模拟结果的位置精度和Kappa系数均比冯诺依曼邻域略高， $7 { \times } 7$ 摩尔邻域是模拟区域耕地的最优选择。

（3）玛纳斯河流域绿洲区2020年耕地模拟结果表明，相比2015年耕地面积，2020年耕地面积略微下降,5a间共计减少 $1 4 9 . 2 9 \ \mathrm { k m } ^ { 2 }$ ，年均减幅29.86$\mathrm { k m } ^ { 2 }$ ，耕地面积呈现因增长饱和而逐渐减缓的趋势。耕地是干旱区人类生存的重要基础，应努力实现耕地内部利用优化与外部适度控制并举之策，促进绿洲人地关系的和谐发展。

# 参考文献(References)：

[1]Foley J,Defries R,Asner G,et al. Global consequences of landuse [J]. Science,2005,309: 570-574.   
[2]刘纪远,宁佳,匡文慧,等.2010—2015年中国土地利用变化的 时空格局与新特征[J].地理学报,2018,73(5):789-802.[Liu Jiyuan,Ning Jia,Kuang Wenhui,et al. Spatio- temporal patterns and characteristics of land-use change in China during 2O10-2015 [J].Acta Geographica Sinica,2018,73(5): 789-802.]   
[3]王宇航,于强,岳德鹏,等.基于BRT_DC_Pd模型的土地利用模 拟研究[J].农业机械学报,2018,49(3):225-234.[Wang Yuhang,Yu Qiang,Yue Depeng,et al. Simulation of land use based on BRT_DC_Pdmodel[J].Transactions of the Chinese Society for Agricultural Machinery,2018,49(3): 225-34.]   
[4]刘纪远,邓祥征.LUCC时空过程研究的方法进展[J].科学通报, 2009,54(21): 3251-3258.[Liu Jiyuan,Deng Xiangzheng.Progress of the research methodologies on the temporal and spatial process of LUCC[J]. Chinese Science Bulletin,2009,54(21): 3251-3258.]   
[5]崔学刚,方创琳,李君,等.城镇化与生态环境耦合动态模拟模 型进展研究[J].地理科学进展,2019,38(1):111-125.[Cui Xuegang,Fang Chuanglin,Li Jun,et al. Progress in dynamic simulation modeling of urbanization and ecological environment coupling [J]. Progress in Geography,2019,38(1): 111-125.]   
[6]Martellozzo F,Amato F, Murgante B,et al. Modelling the impact of urban growth on agriculture and natural land in Italy to 2030[J]. Applied Geography,2018,91: 156-167.   
[7]田义超,梁铭忠.黄土台塬区土地利用/覆被变化定量研究 以陕西省咸阳台塬区为例[J].干旱区研究,2013,30(3):563- 569.[Tian Yichao,Liang Mingzhong.Land use/cover change in Loess tableland areas: A case study in the Loess tableland areas in Xianyang,Shaanxi Province[J].Arid Zone Research,2O13,30 (3): 563-569.]   
[8] 马冰滢,黄姣,李双成.基于生态-经济权衡的京津冀城市群土 地利用优化配置[J].地理科学进展,2019,38(1):26-37.[Ma Bingying,Huang Jiao,Li Shuangcheng. Optimal allocation of land use types in the Beijing-Tianjin-Hebei urban agglomeration based on ecologicaladecoomicnefits tadeofs[J].Progesso raphy,2019,38(1): 26-37.]   
[9]赵旭,汤峰,张蓬涛,等.基于CLUS-S模型的县域生产-生活- 生态空间冲突模拟及特征分析[J].生态学报,2019,39(16): 5897-5908.[Zhao Xu, Tang Feng, Zhang Pengtao,et al. Dynamic simulation and characteristic analysis of county production-livingecological conflicts based on CLUE-S model[J]. ActaEcologica Sinica,2019,39(16): 5897-5908.]   
[10] 张亦汉,乔纪刚,刘婉华,等.城市扩张CA模型的参数敏感性 分析[J].遥感学报,2018,22(6): 1051-1059.[Zhang Yihan, QiaoJigang,Liu Wanhua,et al.Parameter sensitivity analysis of urban cellular automata model[J]. Journal of Remote Sensing,2018,22 (6): 1051-1059.]   
[11] 柯新利,邓祥征,何书金.地理元胞自动机模型的尺度敏感性及 原因[J].地理研究,2010,29(5):863-872.[Ke Xinli,Deng Xiangzheng,He Shujin. Scale sensitivity and its causality for geo-cellular automata modelling[J]. Geographical Research,2010,29(5): 863-872.]   
[12] 吴浩,周璐,史文中,等.基于正交试验设计的土地利用变化元 胞自动机模拟过程的尺度敏感性分析[J].地理科学,2013,33 (10):1252-1258.[Wu Hao,Zhou Lu, Shi Wenzhong,et al. Scalesensitive of cellular automata model for the simulation of land use change based on orthogonal experiment[J]. Scientia Geographical Sinica,2013,3(10): 1252-1258.]   
[13]Menard A,Marceau D J. Exploration of spatial scale sensitivity in geographic cellular automata[J].Environment and Planning B: Planning & Design,2005,32: 693-714.   
[14] Sinha P. Markov land cover change modeling using pairs of timeseries satellite images[J]. Photogrammetric Engineering & Remote Sensing,2015,79: 1037-1051.   
[15]Parsa V A,Salehi E. Spatio-temporal analysis and simulation pattern of land use/cover changes,casestudy: Naghadeh,Iran[J]. Journal of Urban Management,2016,5: 43-51.   
[16]Chen H,Jr RG P.Diagnostic tools to evaluate a spatial land change projection along a gradient of an explanatory variable[J]. Landscape Ecology,2010,25(9): 1319-1331.   
[17] 张军民,张建龙,马玉香.玛纳斯河流域绿洲生态耦合的理论、 方法及机制研究[J].干旱区资源与环境,2007,21(6):7-11. [Zhang Junmin, Zhang Jianlong, Ma Yuxiang.Study on the theory, methodand mechanism of ecologic coupling of Manas River Basin oasis [J]. Journal of Arid Land Resources and Environment,2007,21 (6): 7-11.]   
[18]张凤华.干旱区绿洲、山地、荒漠系统耦合效应及其功能定位 以玛纳斯河流域为例[J].干旱区资源与环境,2011,25(5): 52-56.[Zhang Fenghua.The coupled ecology effect and the function position for oasis-mountain-desert system in arid land: A case of Manas River valley[J]. Journal of Arid Land Resources and Environment,2011,25(5): 52-56.]   
[19]黄犁,徐丽萍.玛纳斯河流域绿洲时空演变及其景观格局变化 [J].干旱区研究,2019,36(5):1261-1269.[Huang Li,Xu Liping. Spatiotemporal evolution of the oasis and change of landscape pattern in the Manas River basin[J].Arid Zone Research,2019,36 (5): 1261-1269.]   
[20]贺可,吴世新,周宏飞,等.玛纳斯河流域两种典型土地利用变 化分析[J].干旱区研究,2018,35(4):954-962.[He Ke,Wu Shixin,Zhou Hongfei,etal.Twotypicallanduse modelsinthe Manas River Basin [J]. Arid Zone Research, 2018,35(4): 954-962.]   
[21] 阿依努·吐逊,张青青,徐海量,等.近57a玛纳斯河流域土地利 用/覆被变化[J].干旱区研究,2019,36(3):599-605.[Ayinu Tuxun,Zhang Qingqing,Xu Hailiang,et al. Characteristicsof land use/cover change in Manas River Basin in recent 57 years[J]. Arid Zone Research,2019,36(3): 599-605.]   
[22] 王丽春,焦黎,来风兵,等.基于遥感生态指数的新疆玛纳斯湖 湿地生态变化评价[J].生态学报,2019,39(8):2963-2972. [Wang Lichun,JiaoLi,LaiFengbing,etal.Evaluation of ecological changes based on a remote sensing ecological index in a Manas Lake wetland, Xinjiang[J].Acta Ecologica Sinica,2019,39(8): 2963-2972.]   
[23] 李建军,罗格平,丁建丽,等.近50a人工灌排技术进步对玛纳 斯河流域耕地格局变化的影响[J].自然资源学报,2016,31(4): 570-582.[Li Jianjun,Luo Geping,Ding Jianli,etal.Efectof progress in artificial irrigation and drainage technology on the change of cultivated land pattern in the past 5O years in Manas River watershed[J]. Journal of Natural Resources,2O16,31(4): 570-582.]   
[24] 张青青,徐海量,樊自立,等.基于玛纳斯河流域生态问题的生 态安全评价[J].干旱区地理,2012,35(3): 479-486.[Zhang Qingqing,Xu Hailiang,Fan Zili, etal.Eco-security assessmentbased on ecological problems of Manas River Basin[J]. Arid Land Geography,2012,35(3): 479-486.]   
[25]解修平,周杰.土地利用变化预测研究——以西安地区为例[J] 干旱区研究,2008,25(1): 125-130.[Xie Xiuping, Zhou Jie. Study on prediction of land use/cover change: A case study in the Xi'an Region[J]. Arid Zone Research,2008,25(1): 125-130.]   
[26] 吴晶晶,田永中,许文轩,等.基于CA-Markov模型的乌江下游 地区土地利用变化情景分析[J].水土保持研究,2017,24(4): 133-139.[Wu Jingjing,Tian Yongzhong,Xu Wenxuan,et al. Scenarioanalysis of land usechange in the lower reaches of Wujiang River based on CA-Markov modle[J]. Research of Soil and Water Conservation,2017,24(4): 133-139.]   
[27] Memarian H, Balasundram S K, Talib JB,et al. Validation of CAMarkov for simulation of land use and cover change in the Langat Basin,Malaysia[J]. Journal of Geographic Information System, 2012, 4: 542-554.   
[28] 王羊.高阳.赵琳.等.元胞自动机模型的尺度敏感性分析II.北

京大学学报(自然科学版),2011,47(4):750-758.[Wang Yang, Gao Yang, Zhao Lin,et al. Scalesensitive analysis of celllar automata model[J].Acta Scientiarum Naturalium Universitatis Pekinensis,2011,47(4): 750-758.]   
[29] 赵冠伟,陈颖彪,陈健飞,等.CA-Markov模型的空间尺度敏感 性研究[J].地理科学,2011,31(8):897-902.[Zhao Guanwei, Chen Yingbiao,Chen Jianfei, et al. Spatialscale sensitivity of CAMarkov model[J]. Scientia Geographica Sinica,2011,31(8): 897- 902.]   
[30]Samat N, Hasni R,Elhadary A E. Modelling land use changes at the Peri- Urban areas using geo- graphic information systems and celular automata model[J]. Journalof Sustainable Development. 2011, 4: 72-84.   
[31] 程维明,周成虎,李建新.天山北麓经济发展与绿洲扩张[J],地 理学报,2002,57(5): 561-568.[Cheng Weiming, Zhou Chenghu, Li Jianxin. Economicdevelopment and oasis growth at the Northern foot of the Tianshan Mountains[J].Acta Geographica Sinica, 2002,57(5): 561-568.]   
[32] 王渊刚,罗格平,冯异星,等.近50a玛纳斯河流域土地利用/覆 被变化对碳储量的影响[J].自然资源学报,2013,28(6): 994- 1006.[Wang Yuangang, Luo Geping,Feng Yixing, et al. Efects of land use/land cover change on carbon storage in Manas River watershed over the past 5O years[J]. Journal of Natural Resources, 2013,28(6): 994-1006.]   
[33] 李菊荣,王延华,唐湘玲,等.新疆玛纳斯河流域土地利用变化 特征及影响因素研究[J].土壤通报,2018,49(1):61-68.[Li Jurong,Wang Yanhua,Tang Xiangling,etal. Thespatial- temporal characteristics of land use change in Manas River Basin and influencing factors[J]. Chinese Journal of Soil Science,2O18,49(1): 61- 68.]   
[34]Pan Y,Andreas R,Yu ZR,et al.The impact of variation in scale on the behavior of a cellular automata used for land use change modeling[J].Computer, Environment and Urban Systems,2010, 34: 400-408.   
[35] 黎夏,叶嘉安,刘涛,等.元胞自动机在城市模拟中的误差传递 与不确定性的特征分析[J].地理研究,2007,26(3):443-451. [Li Xia,Ye Jia'an,Liu Tao, et al.Analysis of error propagation and uncertainties in urban celular automata[J].Geographical Research,2007,26(3): 443-451.]   
[36]Khila RD,Edwin C T. Characterization of neighborhood sensitivity of an irregular cellular automata model of urban growth[J]. International Journal of Geographical Information Science,2015,29: 475-497.   
[37] 王亚琴,王正兴,刁慧娟.多源遥感数据在土地覆盖变化检测中 的应用[J].地理研究,2014,33(6):1085-1096.[Wang Yaqin, Wang Zhengxing,Diao Huijuan.Application of multiple satellite data to land cover change detection[J]. Geographical Research, 2014,33(6): 1085-1096.]   
[38] 张青青,徐海量,樊自立,等.北疆玛纳斯河流域人工绿洲演变

过程及其特点[J].冰川冻土,2012,34(1):72-80.[Zhang Qingqing,Xu Hailiang,Fan Zili, etal.Artificial oasis evolution and its

# Expansion of cultivated land in the oasis area of the Manas River Basin sensitivity analysis of CA-Markov model parameters

ZHU Lei1²， XIA Xin-xin1²， YANG Ai-min1²， JIN Han1² (1. College ofGrassland and Environment Sciences, Xinjiang Agricultural University, Urumqi 83oo52, Xijiang, China;2.XinjiangKey LaboratoryofSoil andPlant EcologicalProceses,Urumqi 830052,Xinjiang,China)

Abstract:The cellular automaton model is one of the most effective and common methods for land-use change simulation.The accuracy of the simulation is affcted by parameters such ascell size,time interval,and neighborhood structure and size.Follwing the land use data of the Oasis of Manas River Basin in 1975,1995, 2005,2010,and 2O15,this study constructed a cultivated land expansion CA model to analyze the parameter sensitivity of the CA model in the methodofquantitative analysis.Theresults showed that (1)the simulation accuracy of the CA model depends on a spatial and temporal scale.The shorterthe time interval,the higher the accuracy. The quantitative accuracy，position accuracy,and Kappa accuracy of a $5 -$ year interval are $1 3 . 8 9 \%$ ， $2 . 6 3 \%$ ,and $8 . 4 9 \%$ higher than those of a 2O-year interval. At the spatial scale,the smaller the cell size,the higher the simulation accuracy will be. The Kappa coefficient value(O.8671) of a cell size of $3 0 \mathrm { ~ m ~ }$ is higher than the simulation result of 120 m (0.8259).(2)The simulation results of neighborhood structure and size showed that the Moore neighborhood accuracy is better than Von Neumann’s. Under the same neighborhood,the neighborhood accuracy with 7 $\times 7$ size is higher than that of the $3 \times 3$ size.The 7 $\times$ 7 Moore neighborhood is the best choice for simulating cultivated land.(3)Thesimulationresultsof cultivated land manifested that thecultivated land decreased $1 4 9 . 2 9 ~ \mathrm { k m } ^ { 2 }$ in 2020 compared with the area in 2O15. The proportion of cultivated land decreased from $6 7 . 4 0 \%$ in 2015 to $6 6 . 1 8 \%$ in 2020,which presented a gradual slow down due to growth saturation. This study can help provide atheoretical basis fora comprehensive understanding ofthe sensitivityof thecellular automaton model.

Keywords:CA-Markov model; land-use change；parametric sensitivity；cultivated land expansion； Manas River Basin