# 基于格网的青海省干旱灾害综合风险评估

韩炳宏}²，周秉荣}，吴让'，赵敏，也国妍²，牛得草，傅华5（1青海省防灾减灾重点实验室,青海 西宁 810001；2 青海省海南州气象局,青海 海南813000;  
3青海省气象科学研究所,青海西宁810001；4 青海省玉树州气象局,青海玉树 815000;  
5草地农业生态系统国家重点实验室 兰州大学草地农业科技学院,甘肃兰州730020)

摘要：干旱灾害风险评估是执行区域性干旱灾害风险管理的重要举措，是有效实施气象防灾减灾工作的非工程性技术措施。随着气象现代化的逐步实施，干旱灾害风险评估技术和精度的重要性越加凸显。为科学、准确地评估青海省区域干旱的监测精度和干旱灾害风险等级，以青海省为例，采用青海省1961—2010年50个气象站潜在蒸散和降水数据，基于气象灾害风险度评估理论和方法,并根据《青海省地方干旱等级划分标准》,通过干旱灾害风险度模型和ArcGIS空间分析相结合的方法，较为系统地分析了青海省干旱灾害风险时空分布特征及其灾害风险等级。结果表明：近50a以来，青海境内主要发生了不同程度的冬春季干旱。从时空分布特征来看，轻、中、重度干旱灾害分布和演化趋势基本一致，干旱灾害易发高发区主要分布于柴达木盆地西北部；环青海湖流域和共和盆地以及东部农业区局地处于中等风险水平，其余地区干旱灾害风险水平较低;从市、县、镇区域单元来看,茫崖、花土沟镇、冷湖及格尔木市干旱灾害风险较高，天峻、都兰、乌兰、共和、兴海、同德、贵南、同仁、化隆、循化及唐古拉等地次之，其余地区干旱灾害风险水平较低，青海境内干旱灾害的发生不仅受降水量影响，还与不同类型的下垫面密切相关。

关键词：青海省；干旱灾害；风险度模型；风险评估中图分类号：X4 文献标识码：A 文章编号

干旱是世界上最为常见和普遍的气象灾害之_[1]。具有发生频次高、持续时间长、影响范围广等特点，在一定程度上严重地制约了农牧业生产、生态环境改善和社会经济发展[2]。据世界气象组织资料显示，全世界约 $70 \%$ 的自然灾害属气象灾害，而干旱灾害约占自然灾害的 $3 5 \%$ 以上[3]。全球每年因干旱灾害造成的经济损失约 $8 \times 1 0 ^ { 8 }$ USD，远远超出了其它自然灾害损失[4-5]。另外,在全球气候变暖的背景下，干旱已逐渐趋于常态化；且随着特大干旱事件发生强度和频率的持续增加，其异常损害程度和范围越加凸显[6] 1

我国西北部位于北半球中纬度地区，地处欧亚大陆腹地，是典型的温带大陆性气候。而且绝大部分地区处于干旱、半干旱气候区，土壤表层干燥，植被稀疏，局地水汽的蒸散量也非常有限。故西北地区的云水资源相对较少，水分自内向外的疏通并不活跃，加之年平均降水量少、气候波动大等特点，该区是我国干旱灾害的易发多发区[7]。另外,西北地区也是全球生态脆弱和气候变化敏感区，气候变暖引起降水非均质性的空间分配格局更加凸显，极端干旱事件发生的频率和强度急剧增加。由此引起了一系列突出的生态环境问题,如：水资源短缺、草地退化和沙化及空气质量不断恶化等[8]。有研究表明,西北气候由暖干不断地向暖湿发生转换[9]，新疆南部和北部冬天湿润指数相对较高，而其它季节相对较低[10]。西北地区东部温度呈线性增加的趋势，而降水和湿润指数呈线性递减趋势，总体表现为暖干化趋势[1]。自1990 年以来,我国西北地区极端干旱事件发生的频率显著增加[12-13] 。有研究显示，自1961—2009年，我国夏季极端干旱事件的发生率均表现为北部大于南部，且西北地区表现更为突出[14]。干旱灾害的发生不仅包含一系列复杂的动态过程和多尺度的物质循环机制，还涉及农气、水文、生态和社会经济等诸多领域，一直以来被认为是科学界的一个重大疑难问题

青海省地处青藏高原东北部，由于其地理位置的特殊性。受高空西北气流、高原低值系统、东亚季风环流以及诸多人类活动等因素的影响，其干旱灾害发生的区域性和复杂性非常明显，学者不仅对干旱灾害发生的机理都难以诠释，而且还提出了许多新的科学问题。截止目前，有关青海省干旱灾害形成和发展机理的科学认知并不成熟，而且监控和预警预测的技术方法仍不完善[7]。随着青海省地区社会经济的发展和生态文明建设逐渐依赖于干旱防灾减灾能力的提高，如何及时、有效地预测干旱的发生机理，如何客观、准确地评估干旱灾害的影响程度和范围等一系列科学问题亟需解决。许多学者虽对该区干旱灾害风险评估进行了系统研究[15-17],但由于时间序列短，加之以上研究均基于理论模型插值方法，并未提高区域干旱灾害风险评估精度。为此，本文基于格网尺度的干旱风险指数，较为系统地研究了青海省干旱时空分布格局及其综合风险评估，以期为气象防灾减灾、农牧业气象的规划和气象现代化建设的逐步实施提供一定的理论基础和科学依据。

# 1材料与方法

# 1.1 研究区概况

青海省位于中国西部，地理位置( $8 9 ^ { \circ } 3 5 ^ { \prime }$ \~$1 0 3 ^ { \circ } 0 4 ^ { \prime } \mathrm { E } , 3 1 ^ { \circ } 9 ^ { \prime } \sim 3 9 ^ { \circ } 1 9 ^ { \prime } \mathrm { N } )$ ，行政区域面积 $7 . 2 \times$ $1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ （图1）。地处青藏高原东北部,地形地貌特征复杂，主要以盆地、高山和河谷相间的高原为主。青海畜牧业生产区主要分布于青南地区、环青海湖地区及祁连山等地区。青海属大陆性高原气候，气温日较差大，日照时数长，辐射强，降水地区差异大，降水量由东南部向西北部依次降低。多年平均气温为 $2 . 0 \%$ ,年均降水量 $3 7 3 . 5 \ \mathrm { m m }$ ,年平均降雨日数104d,降雨量主要集中于每年6\~9月份。生长期年平均171d,无霜期年平均86d[17]

# 1.2 资料收集

气象资料，包括研究区1961—2010年青海省

![](images/4f4251cf309fbf611f1a2e1a404ef0f433ac0e3d2e7e04c5fc55c16e9cf3e6cd.jpg)  
图1研究区地势Fig.1Terrain of study area

50个气象台站月平均气温( $\mathcal { \mathrm { C } }$ ）、月平均最高气温$\big ( \mathrm { ‰ }$ 、月平均最低气温( $\mathcal { C }$ ）、月降水 $\left( { \bf { m m } } \right)$ 、月平均相对湿度 $( \% )$ 、月日照百分率 $( \%$ ）、月平均风速 $( \mathbf { m } \cdot \mathbf { s } ^ { - 1 }$ )等要素资料,气象台站海拔和经纬度资料来源于青海省信息中心。基础地理信息数据和高程（1：250000）等资料来源于青海省气象科学研究所。

# 1.3 干旱等级确定

本文中利用干燥度指数（AritidyIndex)来表征干旱程度，其定义为可能蒸散与降水的比值。为了避免计算式中分母为零的情况，故利用如下公式进行计算。

$$
A I = E T _ { 0 } / ( \cal { P } + 1 )
$$

式中： $E T _ { 0 }$ 为参考作物蒸散系数 $\left( { \mathrm { m m } } \right) , P$ 为月降水 $\mathrm { ( m m ) }$ ）。应用《青海省气象灾害地方标准》土壤水分干旱指标进行回归分析，并结合干燥度在气候类型划分中的标准，确定青海气象干旱类型和干燥度指数范围。

表1青海省干燥度指数  
Tab.1Aridity index in Qinghai Province   

<html><body><table><tr><td>干旱类型</td><td>干燥度指数</td><td>干旱类型</td><td>干燥度指数</td></tr><tr><td>无旱</td><td>AI ≤1.7</td><td>中旱</td><td>3.0<AI≤8.0</td></tr><tr><td>轻旱</td><td>1.7<AI≤3.0</td><td>重旱</td><td>AI>8.0</td></tr></table></body></html>

# 1.4 潜在蒸散估算

潜在蒸散量是指在一定气象条件下水分供应不受限制时，陆面可能达到的最大蒸发量，计算方法诸多,但各有优缺点。本文采用Hargreaves 法（2）和Penman-Monteith方法（3）相结合，前者需要的输入因子有最高气温、最低气温、天文辐射，以上因子栅格资料都可以获取。Penman-Monteith方法需要的输入因子较多，但其最大的优点是计算结果较为准确。二者结合使用，既可以解决栅格资料的缺少，又在一定程度上提高估算准确性。

$$
\begin{array} { c } { E T _ { \scriptscriptstyle h } = 0 . 0 0 1 4 R _ { \scriptscriptstyle { t w f s } } [ ( T _ { \scriptscriptstyle { m a x } } + T _ { \scriptscriptstyle { m i n } } ) / 2 + 1 3 . 1 0 ] \times } \\ { ( T _ { \scriptscriptstyle { m a x } } - T _ { \scriptscriptstyle { m i n } } ) ^ { 0 . 7 } } \end{array}
$$

$$
E T _ { 0 } = \frac { 0 . 4 0 8 \varDelta \left( R _ { n } - G \right) + \gamma \bigg ( \displaystyle \frac { 9 0 0 } { t + 2 7 3 } \bigg ) \mu _ { 2 } \left( e _ { s } - e _ { a } \right) } { \varDelta + \gamma \left( 1 + 0 . 3 4 \mu _ { 2 } \right) }
$$

式中： $R _ { n }$ 为净辐射 $( \mathrm {  ~ M J ~ } \cdot \mathrm {  ~ m ~ } ^ { - 2 } ) : G$ 为土壤热通量$( \mathbf { M } \mathbf { J } \cdot \mathbf { m } ^ { - 2 }$ ; $\gamma$ 为干湿常数( $\mathrm { ^ { \prime } k P a \cdot \mathcal { C } ^ { \alpha - 1 } }$ ）； $\Delta$ 为饱和水汽压曲线斜率 $\mathrm { ^ { \prime } k P a \cdot \mathcal { C } ^ { \alpha - 1 } }$ ）； $T$ 为平均温度 $( \mathrm { ^ { \circ } C } )$ ：$\mu _ { 2 }$ 为 $2 \mathrm { ~ m ~ }$ 高处的风速 $( \mathbf { m } \cdot \mathbf { s } ^ { - 1 }$ ）； $\boldsymbol { e } _ { a _ { } }$ 为实际水汽压（kPa）;e 为平均饱和水汽压（kPa)[18]

利用青海省玉树市隆宝地区微气象观测资料，得到 $E T _ { 0 }$ 和 $E T _ { h }$ 的关系式（图2）。

# 1.5 干旱风险指数确定

干旱风险区划考虑致灾因子的危险性、承灾体的暴露性和脆弱性等多种要素，根据作物减产或者历史干旱灾情统计资料，确定干旱发生的强度或者频率，以及干旱对某种作物的影响程度即承灾体的脆弱性，给出定量的结论。本文中应用干旱出现频数和干燥度变异系数来构建青海省月干旱发生风险指数模型[19]：

$$
D I _ { _ { i j } } = f _ { _ { i j } } \times C V _ { _ { A I } } = { \frac { f _ { _ { i j } } \times S _ { A I } } { \bar { X } _ { A I } } }
$$

式中： $C V _ { A I }$ 是干燥度指数的变异系数，定义为干燥度指数标准偏差 $S _ { A I }$ 和均值 $\bar { X } _ { A I }$ 的比值,表示该级干旱出现的不稳定性 $\mathbf { ; } f _ { i j }$ 为干旱出现次数, $i$ 为月份， $j$ 表示轻、中、重干旱等级。 $C V _ { A I }$ 越高表示出现某级干旱的风险越大，可能性越高；反之，则越低。

# 1.6 数据处理

干旱风险指数采用下式做均一化处理：

$$
T _ { \scriptscriptstyle i j } = \frac { D I _ { \scriptscriptstyle i j } - D I _ { \scriptscriptstyle m i n } } { D I _ { \scriptscriptstyle m a x } - D I _ { \scriptscriptstyle m i n } }
$$

式中： $D I _ { i j }$ 为某一格点值; $D I _ { \mathrm { { \it m i n } } }$ 和 $D I _ { m a x }$ 为数据集中的最小值和最大值。

通过统计学中的分位数分组法[20],初步确定了青海省干旱风险等级划分标准（表2）。

![](images/eb290820c5e68abdfcdf4a14dfc5e20de53bbf3981cc4ac25d1f16123a4a02a3.jpg)  
  
图2潜在蒸散系数 $E T _ { h }$ 与 $E T _ { 0 }$ 的关系 Fig.2Relations between $E T _ { h }$ and $E T _ { 0 }$ of potential evapotranspiration

# 表2青海省干旱风险等级

Tab.2 Classification of drought risk in Qinghai Province   

<html><body><table><tr><td>T值 风险等级</td><td>T≤0.05 极低</td><td>0.05<T≤0.25</td><td>0.25<T≤0.50</td></tr><tr><td>T值</td><td>0.50<T≤0.75</td><td>低 0.75<T≤0.95</td><td>中 T>0.95</td></tr><tr><td>风险等级</td><td></td><td></td><td></td></tr><tr><td></td><td>较高</td><td>高</td><td>极高</td></tr></table></body></html>

# 2结果与分析

# 2.1轻度干旱风险指数时空分布特征

青海省轻度干旱月发生风险指数的时空分布不均匀(图3)。青海省轻度干旱主要发生于冬、春两季。夏秋季节随着降水量的逐渐增加，全省轻度干旱发生的综合风险水平较低;这与当地实际情况相一致。从地形地貌特征来看，冬春季西北部的柴达木盆地发生轻度干旱风险较高，其次为青南高原牧区和东部农业区，而其余地区处于低等风险水平。另外，从各县域单元来看，茫崖地区冬春季轻度干旱风险较高，都兰、乌兰、共和、兴海、贵南、同德以及玉树州次之，其余地区无轻度干旱风险。

# 2.2中度干旱风险指数时空分布特征

青海省境内的中度干旱风险的时空分布特征与轻度干旱基本相近(图4)。虽然中度干旱的影响范围较轻度干旱有所缩减，但中度干旱综合风险高发时段仍分布于冬春季节，而夏秋季风险相对较低。从各地理单元来看，全年中度干旱风险高发区主要集中于西北部柴达木盆地，而东部农业区和玉树州局部地区在冬春季达中等风险水平，其余地区处于风险较低水平。

# 2.3重度干旱风险指数时空分布特征

整体来看，青海省重度干旱风险指数时空分布特征与轻度和中度干旱较为一致(图5）。在冬春季青海省重度干旱风险发生于全省大部地区，而夏秋季重度干旱风险主要发生于西北部的柴达木盆地;从县域单元来看，冬春季重度干旱风险高发区主要分布于茫崖镇、冷湖和格尔木市，而都兰、乌兰、天峻、门源、共和、兴海、贵南、同德、同仁、化隆、唐古拉及治多等地次之，省内其余地区处于风险低发区。

# 3讨论

区域性气象灾害风险评估是执行区域性灾害风险管理的重要举措，是有效实施气象防灾减灾工作的非工程性技术措施[2I]。随着气象现代化的逐步实施，其对气象灾害风险评估技术和精度的依赖性越加增强。为此，本文通过利用干旱灾害风险指数模型，并结合ArGIS空间分析工具，较为系统地研究了青海省月干旱灾害风险区划空间分布特征及其评估。结果表明，由于受复杂地貌特征的影响，青海省干旱灾害风险时空分布错综复杂。其中,轻、中、重度风险区成片交错出现，冬春季干旱风险区从西北部的柴达木盆地一共和盆地一东部农业区局地一带分布，且影响程度和范围逐渐缩小。西部地区干旱灾害风险总体较高，尤其以柴达木盆地西北部最为明显；而青南高原、东南和东北部地区干旱灾害风险相对较低。从地形地势角度来看，干旱风险高发区主要分布于昆仑山西北部、祁连山西南以及巴颜喀拉山东北部,而唐古拉和共和盆地以及东部农业区局地次之，省内其余地区为旱灾低风险区。

从各市、县、镇域单元来看，海西蒙古藏族自治州的茫崖、冷湖、花土沟镇以及格尔木市属干旱高风险区，而都兰、天峻、乌兰、共和、兴海、同德、贵南、同仁、化隆、循化以及唐古拉等地次之，其余地区风险较低。地处西北部柴达木盆地干旱风险指数较高的原因大致有三方面：（1）海陆位置的差异，柴达木盆地深居内陆干旱地区，远离海洋，长期得不到充足的水汽条件。（2）复杂的地形地貌特征，柴达木盆地地处青南高原与祁连山脉间的峡谷地带，四周被高山环绕，有效地阻挡了水汽的输送，致使大量水汽难以到达该区。（3）由于该区正好处于中纬度地区，加之受温带大陆气团的控制和常年盛行偏西风，降水稀少，气候极度干旱,甚至严重时会出现无雨日。另外，本文轻、中、重的干旱灾害风险评估结果时空分布特征与相关研究结果基本一致,如刘义花等[15]对青海省牧草干旱风险区划进行了研究。结果表明,青海省干旱灾害高风险地区主要分布在柴达木盆地东段和祁连山地区，青南高原西南部为中等风险区;其余地区干旱灾害风险较小。颜亮东等[就青海牧区干旱、雪灾灾害损失综合风险进行了较为系统地评估研究，发现青海省境内若同时发生轻度干旱和雪灾时，干旱对农牧业造成的直接经济损失较雪灾大;刘义花等[17以青海境内气象自动站为单位对青海省农业区春小麦干旱灾害风险进行了比较分析。结果表明，青海西北地区整体旱灾风险等级明显高于东南地区。且重旱和特旱主要出现在柴达木盆地西部地区，频率分别达 $1 0 . 7 \%$ 和 $3 4 . 0 \%$ ；而中度干旱主要分布于环湖南部和东部农业区局地，频率达 $1 0 . 0 \%$ 以上;省内其余地区为轻旱,其出现频率为 $1 5 . 0 \%$ 以上。另外,周秉荣等[19]就青海省农牧业气象灾害区划进行了系统研究，指出柴达木盆地属重旱高发区，环青海湖和共和盆地属中旱地区，三江源属无旱区。以上研究结果与本研究基本一致。上述研究均是以县域为单元，基于矢量数据的空间分布特征分析，其结果精度低,空间属性描述差。而本文利用1961—2010 年干旱灾害风险指数格点化资料，对青海省境内近50a干旱灾害风险时空分布特征进行了系统分析，其评估结果精度较高且空间分布层次比较清晰。截止目前，有关青海省干旱灾害风险评估尚未形成较为统一的风险评估模型，为了使评估结果更加贴合实际，科学合理地选取符合当地实际的评价指标和风险度模型显得尤为重要。大多数有关干旱灾害风险评估研究均采用头脑风暴法、事故树法、专家打分法、故障树分析法、特尔斐法、层次分析和情景分析等模糊数学方法[2]，从而使得干旱灾害风险定量化存在不确定性。因此，定量化评估干旱灾害风险的技术方法还有待进一步深入研究。

![](images/7367f74e6c4a3252a051c7a0b27c0d3f776c52aeb7eabd27ee31bc98fb0731fd.jpg)  
图3青海省轻度干旱时空分布  
Fig.3Spatial-temporal distribution of light drought in Qinghai Province

![](images/59af65aaa019489c348142a2c5cae891a12186581a5455d98550ac577bce3ea0.jpg)  
图4青海省中度干旱时空分布  
Fig.4Spatial-temporal distribution of medium droughtin Qinghai Province

![](images/6040de210c2291fd31b265e37b3e1672a56b7aa6eaa9dcff32a7ec575aeac57f.jpg)  
图5青海省重度干旱时空分布  
Fig.5Spatial-temporal distribution of heavy drought in Qinghai Province

# 4结论

通过对近50a青海省干旱灾害风险指数的分析，发现干旱灾害风险空间分布格局与干旱灾损实际情况基本一致，说明本文研究结果可信，能较好地反映整个青海省干旱灾害风险水平。得到以下结论：

(1)由于受自然降水分配格局和季节性的强烈影响，青海省境内干旱灾害风险主要发生在冬春季专 $\left[ 1 1 \sim 3 \right.$ 月份），夏秋季( $4 \sim 1 0$ 月份)干旱灾害风险水平较低。

(2)从空间分布特征来看，青海省轻、中、重度月干旱灾害风险等级分布趋势基本一致。其中，柴达木盆地西北部干旱灾害风险等级最高，共和盆地至东部农业区局部地区冬春季干旱灾害风险等级次之，其余地区处于低风险区。

(3)从市、县域单元来看，茫崖、冷湖、花土沟镇以及格尔木市属干旱高风险区，都兰、天峻、乌兰、共和、兴海、同德、贵南、同仁、化隆、循化以及唐古拉等地次之，其余地区风险较低。

(4)基于格点化资料获取的结果较以往研究在空间上更能直观地反映该区不同月份干旱灾害发生的程度和范围，以期为气象防灾减灾能力和应对极端天气事件提供科学依据。

本文基于格网尺度的干旱灾害风险指数探讨分析了青海省境内的月干旱灾害风险时空分布特征，虽能较好地反映以区域自动站为中心的干旱灾害风险情况，但由于受降水时空不均匀和地形地貌的复杂性，所获结果与整个青海省境内的实际灾损状况仍存在一定差异，不利于该区干旱灾害风险的进一步预警、监测及推广应用。因此，今后若能综合考虑多因素综合方法对社会经济数据进行栅格化表达，将有利于数据的空间匹配以及属性描述，进一步提高评估结果的准确度。

# 参考文献(References)

[1］徐新创,刘成武.干旱风险评估研究综述[J].咸宁学院学报, 2010,30(1O）:5-9.[XU Xinchuang,LIU Chengwu.A view on the risk assessment of drought[J].Journal of Xianning University, 2010,30(10):5-9.]   
[2]杨帅英,郝芳华,宁大同.干旱灾害风险评估的研究进展[J]. 安全与环境学报,2004,4（2）:79-82.[YANG Shuaiying,HAO Fanghua,NING Datong.New advance on drought risk assessment and its propects[J]. Journal of Safety and Environment,2004,4 (2):79 -82.]   
[3] 秦大河，丁一汇，王绍武，等.中国西部环境变化与对策建议 [J].地球科学进展,2002,17（3）:314－319.[QINDahe,DING Yihui,WANG Shaowu,et al. Environmental changes in western China and countermeasures[J].Advances in Earth Science,2002, 17(3) :314 -319.]   
[4] 王伟光，郑国光.应对气候变化报告(2013)一聚焦低碳城镇化 [M].北京：社会科学文献出版社，2013：360-362.［WANG Weiguang，ZHENG Guoguang. Address climate change report (2013）：Focus on low-carbon urbanization［M].Beijing:Social Sciences Academic Press,2013:360-362.]   
[5] WILHITE D A.Drought as a natural hazard:Concepts and defitnitions[M]//WILHITE D A,ed.Drought:A global assessment.London& New York:Routledge,20oO:3-18.   
[6]IPCC.Summary for policymakers[M]//Managing the risks of extreme events and disasters to advance climate change adaptation.A

special report of working groups Iand II of the intergovernmental panel on climate change.Cambridge,UK,and NewYork,NY,USA： Cambridge University Press,2012:1-19.

[7］张强,姚玉璧,李耀辉,等.中国西北地区干旱气象灾害监测预警与减灾技术研究进展及其展望[J].地球科学进展，2015，30(2）:196-213.[ZHANG Qiang,YAO Yubi,LI Yaohui,et al. Re-search progress and prospect on the monitoring and early warningand mitigation technology of meteorological drought disaster innorthwest China[J].Advances in Earth Science,2015,30（2）：196 -213.]

[8］李明星,马柱国.中国气候干湿变化及气候带边界演变：以集成土壤湿度为指标[J].科学通报，2012，57（28／29）：2740-2754.［LI Mingxing,MA Zhuguo.Soil moisture-based study of thevariability of dry-wet climate and climate zones in China[J].Chi-nese Science Bulletin,2012,57(28/29):2740-2754.]

[9]施雅风.中国西北气候由暖干向暖湿转型问题评估［M].北京：气象出版社,2003：17-25.［SHIYafeng.Assessment of cli-matic transformation from warm-wet in northwest China[M].Bei-jing:MeteorologicalPress,2003:17-25.]

[10］姜大膀，苏明峰，魏荣庆，等.新疆气候的干湿变化及其趋势预估[J].大气科学，2009,33（1）：90-98.［JIANGDabang，SUMingfeng,WEIRongqin,etal.Variationand projection of droughtand wet conditions in Xinjiang[J].Chinese Journal of AtmosphericSciences,2009,33（1）:90-98.]

[11］马柱国，符淙斌.中国北方干早区地表湿润状况的趋势分析 [J].气象学报,2001,59(6）:737-746.[MA Zhuguo,FUCongbin.Drought in northern China the status of surface wetting trend analysis[J].Acta Meteorologica Sinica,2001,59（6）: 737- 746.]

[12］马柱国，符淙斌.中国干旱和半干旱带的10 年际演变特征 [J].地球物理学报,2005，48（3）：519-525.［MAZhuguo，FU Congbin.Decadal variations of arid and semi-arid boundary in China[J].Chinese Journal of Geophysics,2005,48(3）:519-525.] [13］马柱国.我国北方干湿演变规律及其与区域增暖的可能联系 [J].地球物理学报,2005,48（5）:1011－1018.［MA Zhuguo. Dry/wet variation and its relationship with regional warming in arid-regions of northern China[J].Chinese Journal of Geophysics, 2005,48(5):1011-1018.]

[14］刘珂，姜大膀.中国夏季和冬季极端干旱年代际变化及成因分析[J].大气科学，2014,38(2）:309-321.[LIUKe,JIANGDa-bang.Interdecadal change and cause analysis of extreme summerand winter droughts over China ［J].Chinese Journal of Atmos-pheric Sciences,2014,38(2）:309-321.]

[15］刘义花，李林，颜亮东,等.基于灾损评估的青海省牧草干旱风 险区划研究[J].冰川冻土，2013,35（3）：681-686.［LIUYihua,LI Lin,YAN Liangdong,etal.Risk division of pasture drought in Qinghai Province based on loss assessment[J].Journal of Glaciology and Geocryology,2013,35（3）:681-686.]

[16］颜亮东，李林，刘义花.青海牧区干旱、雪灾灾害损失综合评估 技术研究[J].冰川冻土,2013,35（3）:662-680.[YAN Liangdong,LILin,LIUYihua.Howto comprehensivelyevaluate the economic loss due to drought and snow disaster in Qinghai pastoral areas[J].Journal of Glaciology and Geocryology,2013,35（3）:662 -680.]

[17］刘义花,李林,苏建军,等.青海省春小麦干旱灾害风险评估与 区划[J].冰川冻土2012,34(6）：1416-1423.[LIUYihua，LI Lin,SU Jianjun,et al.Risk assessment and division of drought disasteron spring wheat in QinghaiProvince[J].Journal of Glaciolo gy and Geocryology,2012,34(6):1416-1423.]

[18］胡琦，董蓓,潘学标,等.1961—2014年中国干湿气候时空变化特征及成因分析[J].农业工程学报，2017，33（6)：124-132.[HUQi,DONG Bei,PAN Xuebiao,et al.Spatiotemporal variationand causes analysis of dry-wet climate over period of 1961—2014in China[J].Transactions of the Chinese Society of AgriculturalEngineering,2017,33(4）:124-132.]

[19］周秉荣，李甫，胡爱军，等.青海省气候资源分析评价与气象灾 害风险区划［M].北京：气象出版社，2016：62-67.[ZHOU Bingrong,LI Fu,HU Aijun,et al.Analysis and evaluation of climate resources and the division of meteorological disaster risk in Qinghai Province[M].Beijing:Meteorological Press,2O16:62- 67.]

[20］韩炳宏，吴让，周秉荣，等.基于格网的青海省雪灾综合风险评 估[J].干旱区研究,2017,34（5）：1035-1041.[HAN Binghong,WU Rang,ZHOU Bingrong,et al.Grid based estimation of snow disaster risk in Qinghai Province[J].Arid Zone Research, 2017,34(5):1035-1041.]

[21］刘小艳，孙娴，杜继稳，等.气象灾害风险评估研究研究进展 [J].江西农业学报,2009,21（8）:123－125.［LIU Xiaoyan, SUNXian,DU Jiwen,et al.Research progress in environment of meteorological disaster risk[J].Acta Agriculture Jiangxi,2009,21 (8):123-125.]

# Grid-based estimation of drought disaster in Qinghai Province

HAN Bing-hong12，ZHOU Bing-rong¹³，WURang’，ZHAOMin4，NIEGuo-yan, NIU De-cao5， FU Hua5 (1Key Laboratory of Disaster Prevention and Mitigation of Qinghai Province,Xining 81oool,Qinghai,China;   
2The Meteorology Station of Hainan Tibetan Autonomous Prefecture,Hainan 8130o0,Qinghai,China ;   
3The Instituteof Meteorological Science,Xining 810o01,Qinghai,China；4The Meteorology Stationof Yushu Tibetan AutonomousPrefecture,Yushu150o,Qinghai,China；5State KeyLaboratoryofGrassand Agro-ecosystem,Collgeof Pastoral Agriculture Science and Technology,Lanzhou University,Lanzhou 73oo2o,Gansu,China)

Abstract：With the gradual implementation of meteorological modernization,the importance of the risk assessment technique as well as its precision about drought disaster is more prominent.While drought isoneof the global meteorological disasters toacertainextent,theagricultural andanimal husbandryproduction,ecological environmentimprovement and social and economic development have been severely restricted.Therisk assessmentof drought disaster is an important measure tocaryouttherisk managementof regionaldrought disaster,anditis the non-engineeringtechnical measure to implementthe work of meteorological disaster preventionand reduction efectively.The risk assessment of drought disaster in Qinghai Province,China,was studied by some scholars,but it was based on vector data of county domain units.Therefore,theresults exaggerated therisk degree and spatial distribution of drought disaster,and theaccuracy of disaster risk assessment was reduced.In order to assess regional drought monitoring accuracyand the risk levels of drought disaster in Qinghai Province scientifically and acurately,this paper used the potential evapotranspiration and precipitationdata from 5O meteorology stations in Qinghai Province during the period from1961 to 201O to systematically analyze the spatial and temporal distributioncharacteristicsand the risk levels based on the theory and methods of meteorological disaster risk estimation.This was also done with the methods of combining the drought disaster risk degree model and ArcGIS spatial analysis,according to the regional drought grading standard of Qinghai Province.The results showed that the winter and spring drought appeared in Qinghai Province with varying degrees in the period.From the spatial and temporal distribution perspective,the distribution and evolution trends of light,mediumand heavydrought were basically identical.Theareas prone to drought disaster or with high incidence of drought disaster were mainly located in the northwest of Qaidam basin,whileQinghai Lake,Gonghe Basin and the eastern agricultural regions were at medium risk level.The rest shared the low levels of droughtdisaster risk；from theviewpointof theadministrationunit,the drought disaster riskswere higher in Mangya,Lenghu,Huatugou Town and Golmud City.The drought disaster risks in the regions including Tianjun,Dulan, Wulan,Gonghe,Xinghai,Tongde,Guinan,Tongren,Hualong,Xunhuaand Tanggula,were inthe medium levels.The restwere with the low levels.Inaddition,influenced bytopographyand geomorphology,the MangyaandLenghuarea were in a dry state throughout the whole year,which were more consistent with the reality.Thus,itcould be seen thatthe occurrence of drought disaster in Qinghai Province was not only related to precipitation,but also related to the underlying surface of different types.

Key words:Qinghai Province；drought disaster； the risk model； the estimation of risk