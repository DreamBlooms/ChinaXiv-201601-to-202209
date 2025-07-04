# 准噶尔盆地大赖草分布格局及关键因子分析

张林'，张云玲²，马松梅'，张丹³，贺凌云1

(1.石河子大学理学院,兵团绿洲城镇与山盆生态系统重点实验室,干旱区景观生态重点实验室,新疆石河子832000；2.新疆维吾尔自治区草原总站,新疆 乌鲁木齐830049；3.石河子大学生命科学学院，兵团绿洲城镇与山盆生态系统重点实验室，新疆 石河子832000)

摘要：模拟、预测新疆准噶尔盆地沙丘禾草大赖草的生态适宜性及其空间分布特征,以及对未来气候变化的可能响应,指导该濒危植物的保护。研究基于大赖草的24个自然分布点和8个环境因子,利用GIS空间分析和 Max-Ent模型，分析基准气候(1970—2000年)和社会经济路径SSP2下2050时段(2041—2060年)和2070时段（2081—2100年)大赖草的适宜分布范围及分布格局变化，并利用多元环境相似度面和最不相似变量探究影响大赖草分布的关键气候因子。结果表明：(1)基准气候下，大赖草的适宜分布面积占新疆总面积的 $5 . 5 7 \%$ ，主要集中于额尔齐斯河流域附近的低覆盖度草地;(2)与基准气候相比,2050时段和2070时段大赖草的适生区呈显著减少趋势，占比分别为 $0 . 9 9 \%$ 和 $1 . 3 3 \%$ ，适宜生境高度破碎化，适生区的质心向西北方高纬度和高海拔地区迁移;(3）最十月降水量、降水量季节性变化和温度季节性变化是影响准噶尔盆地大赖草适宜分布的关键气候因子。

关键词：大赖草；适宜分布特征；MaxEnt模型；驱动因子；未来气候变化；准噶尔盆地

气候变化对生物多样性和物种空间分布格局有着重要影响[]，不同植物类群应对气候变暖的响应策略不同[2]。研究不同地区物种的适宜分布及其对未来气候变化的可能响应，有助于生物多样性的科学管理与有效保护计划的制定。新疆位于亚欧大陆腹地，具有独特的山脉-盆地-沙漠-绿洲景观和特有的干旱荒漠植物地理分布格局。气候长期干旱化、山体隆升、沙漠形成扩张等原因造成的干旱破碎化景观，进一步加剧了区域的空间环境异质性，这些生态地理驱动力也进一步影响了物种的空间分布特征[3]。因此,研究气候变化与干旱景观破碎化背景下荒漠植物物种的地理分布特征，获取物种空间分布格局等方面的知识，对深入理解和保护干旱区生物多样性十分重要，

大赖草(Leymusracemosus），属于禾本科(Poace-ae)赖草属(Leymus)，分布于中国、哈萨克斯坦、蒙古和俄罗斯等地[4]。在中国，主要分布于新疆准噶尔盆地的流动或半固定沙丘上[5]。大赖草具有耐寒、耐旱、耐盐碱等较强抗性，作为普通小麦的近缘野生植物和沙漠地区的理想牧草[6,是优良的小麦基因改良库[7-8]和植被恢复计划的预选物种[9]。同时，大赖草在干旱荒漠区发挥着防风阻沙和植被恢复等重要的生态与经济作用。近些年，受气候变化、生态环境恶化及人类活动干扰的影响，加之大赖草的种子萌发率低和克隆生长缓慢等原因，该植物目前已处于濒危状态，被列为新疆三级保护植物[10]目前，对大赖草在转基因[]和小麦育种[2]等方面已开展的研究，揭示了该植物种群具有较高的遗传多样性和特殊的种质遗传资源;在大赖草种子萌发[13-14]方面开展的研究,揭示了该植物对荒漠环境的生态适应对策，这些研究对大赖草种群的恢复与重建具有重要意义。然而，大赖草在新疆准噶尔盆地的生态适宜性、空间分布特征，以及对未来气候变化的可能响应鲜见报道，这些科学问题的解决利于深入理解气候变化情景下新疆沙生植物的分布及其对环境的可能响应。

物种分布模型(SpeciesDistribution Model,SDM)是一种基于物种分布数据与环境数据模拟物种生态位的数值模型[15],随着生态位理论与技术的发展，越来越多的统计学方法被广泛的用于描述物种分布模式以及进行建模预测，如广义线性模型（GLMs）、分类回归树分析（CTA）、人工神经网络（ANNs）、随机森林模型（RFs），以及最大熵模型(MaxEnt)。其中，MaxEnt是最常用的物种分布模型之一，在样本量较少( $< 2 0$ )的情况下也能获得较好的模拟效果[1],被广范应用于物种潜在适生生境的预测。

本研究基于MaxEnt模型和GIS空间分析，研究新疆准噶尔盆地大赖草的适宜分布特征，解决以下科学问题：（1）大赖草在新疆的生态适宜性等级与空间分布特征；(2)大赖草的适宜分布对未来气候变化的可能响应；(3）影响大赖草生态适宜性及其分布的关键环境因子。

# 研究区概况与方法

# 1.1 研究区概况

准噶尔盆地是中国第二大内陆盆地，位于中国新疆北部，地处阿尔泰山、天山山脉与准噶尔西部山地之间，地势东高西低，北部略高于南部。北部与南部之间是古尔班通古特沙漠(中国第二大沙漠),沙漠土壤以固定、半固定风沙土占绝对优势[17]。气候属于典型的中温带气候,盆地北部年均温为 $3 { \sim } 5 ~ \mathrm { \% }$ 盆地南部年均温为 $6 { \sim } 1 0 ~ \mathrm { \textdegree C }$ ，水汽主要来自西风气流，四季降水较均匀[18]。准噶尔盆地植物区系在第四纪形成,短命植物和旱生植物种类较丰富[19]

# 1.2数据来源

本研究分布数据来源于中国数字植物标本馆(http://www.cvh.ac.cn/）、植物志（http://zhiwu.cnki.net/）、教学标本资源共享平台(http://mnh.scu.edu$\mathrm { c n / }$ )和中国植物图像库(http://www.plantphoto.cn/），并参考新疆植物志及相关文献资料[8.4,0-21],，共获得59个大赖草的自然分布点。首先,通过GoogleEarth及新疆地名录确定分布点的详细地理坐标；然后根据气候因子的空间分辨率，利用R软件的raster和biomod2包进一步矫正分布点偏差，每个栅格只取1个分布点，最终获得24条大赖草的分布点用于模型模拟(图1a)，基本覆盖了该植物在新疆的自然分布范围和气候范围。同时，本研究对大赖草在额尔齐斯河流域附近的福海县、布尔津县、哈巴河县进行了野外样地样方调查(图1b\~图1e)，包括样方内大赖草株数、高度、盖度等，以及样地的土壤质地、人为干扰类型等，将野外获得10个实测点的大赖草分布信息用以验证模型的模拟结果，

本研究中19个生物气候因子和海拔数据源于世界气候数据库（http://www.worldclim.org）,空间分辨率为 $2 . 5 ^ { \prime }$ 。未来气候选取2050时段（2041—2060年）、2070时段(2081—2100年)MIR0C全球气候模型数据[22]。共享社会经济路径（Shared Socio-eco-nomicPathways,SSPs)是IPCC描述未来在不同社会经济状况假设下新一代的排放情景，包括SSP1（Sus-tainability）、SSP2(Middleof theRoad）、SSP3（Region-al Rivalry）、SSP4（Inequality）和 SSP5（Fossil- fueledDevelopment），本研究选择SSP2代表的温室气体排放中间路径。本研究所用的研究区坡度、坡向数据，是基于海拔数据利用ArcGIS空间分析工具提取获得。

在模型模拟前，为了降低环境因子之间的空间自相关性，利用R软件Hmisc程序包对所选的22个环境因子进行Pearson相关性分析[23]。剔除相关性较高( $( > 8 0 \%$ )的变量，最终保留了6个气候变量和2个地形变量用于模型的模拟，包括平均气温日较差(Bio2）、温度季节性变化(Bio4）、最冷月最低气温（Bio6）、最湿月降水量（Bio13）、最干月降水量（Bio14）、降水量季节性变化（Bio15）、坡度(Slope)和坡向（Aspet）。

# 1.3模型构建与环境因子分析

采用MaxEntversion3.4.1软件模拟大赖草3个时期潜在分布区，随机选择 $7 5 \%$ 的分布数据作为训练集（training data）,剩余 $2 5 \%$ 作为测试集(testingdata)，设置10次重复，其他值为默认值。模型精度依据受试者工作特征曲线(ROC)与横坐标围成的面积，即AUC值来评估，当AUC值 $\geqslant 0 . 8 5$ 时，说明模型精度满足要求[2]。利用自然断点法将物种适生区划分为：非适生区、低度适生区、中度适生区与高度适生区。利用刀切法(Jackknife)分析各环境因子在模型构建时的重要性，利用环境变量贡献率和置换重要性值分析各环境因子对模型模拟的贡献率以及模型对各环境因子的依赖程度[24]。

大赖草喜生于沙地，将土壤质地作为该植物分布的限制性因子，进一步精细化分析基准气候下该植物的适宜分布范围。土壤质地数据来源于世界土壤数据库(HarmonizedWorld SoilDatabase,HWSD）,空间分辨率为 $1 ~ \mathrm { k m }$ 。新疆土地利用数据(2018年)来自于中国科学院资源环境科学数据中心(http:/www.resdc. $\mathrm { c n / }$ ),用于进一步分析适生区的土地覆被情况。

![](images/ade36bc25ac3144c9b0302972ca6623d7fd9726e66e2c5fc3d50daf6b43f295c.jpg)  
注：(a)大赖草分布点与野外实测点分布数据;(b)布尔津县阿库线G217路边种群;(c)单株;(d)单丛;(e)布尔津县窝依莫克镇S232路旁种群。图1大赖草的自然分布点与新疆阿勒泰地区大赖草的野外采样地  
Fig.1Natural distribution point of Leymus racemosus,and the field sample plots of Leymus racemosus in Altay of Xinjiang

# 1.4多元环境相似度面和最不相似变量

以大赖草基准气候的环境变量为参考图层，采用多元环境相似度面（MultivariateEnvironmentalSimilaritySurface,MESS)和最不相似变量(theMostDissimilarVariable,MoD)探究未来时段相比基准气候时段研究区气候变化程度，分析引起适生区分布格局变化的关键气候因子[25]。在命令窗口调用MaxEnt.jar文件中的density.tools.Novel工具,计算基准气候时段与未来时段研究区6个气候因子的相似度(S)，得到多元环境相似度面(MESS);提取多元环境相似度的最小值，得到最不相似变量(MoD)，并利用ArcGIS10.2进行可视化处理。当 $s$ 值为正值时，S值越小表示该区域气候因子的差异越大， $\scriptstyle S =$ 100时，表示没有差异；当 $s { < } 0$ 时，该区域至少有1个气候因子的不相似度超出了参考范围，表明该区域

的环境差异极大[26]

# 2结果与分析

# 2.1基准气候下大赖草的适宜分布及其生态适应性

基准气候下，最大熵模型的AUC值大于0.97,模拟获得大赖草的适宜分布面积占新疆总面积的$5 . 5 7 \%$ (表1)，集中于额尔齐斯河流域、准噶尔盆地

# 表1大赖草的适宜分布区占研究区面积的比例

Tab.1 Proportion of potential distribution areas of Leymus racemosus in the study area   

<html><body><table><tr><td>等级</td><td>基准气候</td><td>基准气候(限制)</td><td>2050时段</td><td>2070时段</td></tr><tr><td>非适宜区</td><td>94.43%</td><td>94.99%</td><td>95.42%</td><td>95.76%</td></tr><tr><td>低度适宜区</td><td>3.86%</td><td>3.44%</td><td>2.97%</td><td>2.79%</td></tr><tr><td>中度适宜区</td><td>1.00%</td><td>0.91%</td><td>1.12%</td><td>0.99%</td></tr><tr><td>高度适宜区</td><td>0.71%</td><td>0.66%</td><td>0.49%</td><td>0.45%</td></tr></table></body></html>

西北部、阿尔泰山南坡、天山北坡与伊犁河谷（图2a)。其中，高度适生区面积仅占研究区面积的$0 . 7 1 \%$ ,集中于额尔齐斯河流域中下游(图 $2 \mathrm { a }$ )，中度适生区面积占研究区面积的 $1 \%$ ,主要分布于额尔齐斯河中下游、额敏河和博格达山西端。基于研究区土壤质地数据对基准气候下大赖草的适宜分布进行了限制性分析，结果显示 $0 . 0 5 \%$ 的适宜分布区被去除(图2b)，主要包括在乌伦古湖、艾比湖以及准噶尔盆地东北部的破碎化适生区。

# 2.2未来气候情景下大赖草的适宜分布

与基准气候相比，2050时段和2070时段大赖草的适生区呈显著减少趋势，减少面积占比分别为$0 . 9 9 \%$ 和 $1 . 3 3 \%$ (表1)。而且，未来气候情景下，大赖草的适宜生境更加破碎化，适生区的质心向西北方向迁移(图2c，图2d)。2050时段，大赖草减少的适宜范围主要是分布于准噶尔盆地中部、东部的低度适生区，以及集中在额尔齐斯河中下游沿岸的中高注：(a)基准气候适宜分布模拟；(b)基准气候限制分析后被去除的适宜分布(c);2050时段适宜分布模拟(d);2070时段适宜分布模拟。

![](images/041a55b75980b659c97c5da79d86d10f9aaa775c18ddb012c6a2bf3383bf3b52.jpg)  
图2最大熵模型下大赖草的适宜分布模拟  
Fig.2 Potential distribution area of Leymus racemosus predicted by MaxEnt model

度适生区(图2c)。2070时段，大赖草的适生区面积进一步减少，适宜分布范围更加破碎化，额尔齐斯河下游的高度适生区进一步缩减，但在额敏河流域和博格达山西端附近的高度适生区呈向西扩张趋势，适宜大赖草分布的高值中心由额尔齐斯河的单中心转变为额尔齐斯河、额敏河以及博格达山西端的多中心。

# 2.3影响大赖草适宜分布的环境驱动因子

MaxEnt模拟结果显示，用于模型模拟的8个因子中，最干月降水量和温度季节性变化对模型的贡献率较大，累积贡献率达 $7 6 . 4 \%$ ;置换重要性结果表明，模型对降水量季节性变化( $7 6 \%$ )和平均气温日较差 $( 1 0 . 5 \%$ )的依赖性更强(表2)。刀切法检验结果表明(图3)：对受试者工作特征、正规则化训练增益和测试增益影响最大的都是最干月降水量，其次是降水量季节性变化和温度季节性变化，而且3个降水因子在正则化训练增益、测试增益及受试者工作特征曲线下面积的贡献均高于3个气温因子。因此，最干月降水量、温度季节性变化和降水量季节

# 表2最大熵模型模拟的基准气候下各环境因子的贡献率及其置换重要性值

Tab.2 Contribution rate and replacement value of each environmental factor in MaxEnt modeling of now   

<html><body><table><tr><td>环境变量</td><td>描述</td><td>贡献率/%</td><td>置换重要性/%</td></tr><tr><td>Bio14</td><td>最干月降水量</td><td>52</td><td>0.5</td></tr><tr><td>Bio4</td><td>温度季节性变化</td><td>24.4</td><td>7.2</td></tr><tr><td>Bio2</td><td>平均气温日较差</td><td>7.8</td><td>10.5</td></tr><tr><td>SLOP</td><td>坡度</td><td>7.5</td><td>1.6</td></tr><tr><td>Bio15</td><td>降水量季节性变化</td><td>5</td><td>76</td></tr><tr><td>ASPE</td><td>坡向</td><td>2.3</td><td>0.7</td></tr><tr><td>Bio13</td><td>最湿月降水量</td><td>1</td><td>3.4</td></tr><tr><td>Bio6</td><td>最冷月最低气温</td><td>0</td><td>0.1</td></tr></table></body></html>

性变化是影响大赖草适宜分布的关键气候因子。

多元环境相似度面显示，未来时段与基准气候相比，研究区绝大部分地区的气候波动较明显。2070时段，气候因子相似度低于0的区域占研究区总面积的 $7 . 0 1 \%$ ，是2050时段的4.22倍，主要集中在准噶尔盆地西南部、塔里木盆地西南部(图4)。大赖草已知分布点区域也表现出较为明显的气候波动，24个分布点在2050时段和2070时段的相似度平均值分别为：3.95、3.29。2050时段和2070时段，大赖草适宜分布区发生变化的区域均将出现较为明显的气候波动，分布减少区域的多元环境相似度值集中于0\~10之间，如准噶尔盆地北部，分布增加区域的多元环境相似度值集中于10\~20，如阿尔泰山和北塔山南坡(图4)。

最不相似变量显示，未来气候情景下最冷月最低气温和降水量季节性变化均将发生显著变化，是造成研究区内 $5 0 \%$ 的区域发生气候波动的主要因子，而降水量季节性变化和最干月降水量是影响大赖草24个分布点发生气候波动的主要因子(图4)。大赖草适宜分布的增加区域和减少区域的最不相似变量不同，增加区域主要是最干月降水量和平均气温日较差，减少区域主要为降水量季节性变化和温度季节性变化(图4)。

# 3讨论

# 3.1大赖草的适宜分布

模型模拟准确可视化了大赖草在新疆的适宜分布范围和生态适宜性等级，主要集中于额尔齐斯河中下游、乌伦古河中下游、额敏河和博格达山西端的草地、旱地和戈壁等附近(图2)。野外调查表明，由于放牧、工程建设等人为活动的干扰，大赖草大多数自然种群存在较为严重的退化。同时，分布于额尔齐斯河中下游和乌伦古河下游的自然种群，如阿勒泰地区布尔津县和阿勒泰市的种群也被揭示具有较高的遗传多样性水平[8]，说明模型识别的高度适生区是大赖草的核心分布区(图3)，对该植物的演化与生态恢复很重要。另外，本研究基于研究区土壤质地数据对模型模拟的适生区进行了限制性分析，进一步过滤了土壤生境不适宜的分布区，如模型识别的与乌伦古湖、艾比湖等叠加的分布区，以及在准噶尔盆地东北边缘的破碎化分布（图2b)，进而显著提升了模型的模拟精度和空间表现力，使模拟结果更接近该植物的实际分布。相关研究也表明，在模型中加入地形、土壤因子、植被指数等非生物因子可显著提升研究区的环境异质性，提升模型模拟的灵敏度和准确性[27]

![](images/668ba3d9e68915c5e245b04514e530b2c5ddd436664a92b5aa09d5af2753320b.jpg)  
图3用于MaxEnt模型预测的8个环境变量的刀切法检验结果  
Fig.3Jackknife test results of eight environmental variables used for MaxEnt model

![](images/da2663d4957f354ffcd638f17ba129737628cb96f182270e81c34056e6e322c8.jpg)  
图4未来时段大赖草的多元环境相似度面(MESS)和最不相似变量分析(MoD) Fig.4 Analysis on multivariate environmental similarity surface (MESS) and the most dissimilar variable (MoD) in future ofLeymus racemosus

结合2018年新疆土地利用数据，本研究进一步明确了大赖草适宜分布区的生境及其生态地理条件，大赖草主要分布于低覆盖度草地(覆盖度在$5 \% { \sim } 2 0 \%$ 的天然草地）、旱地周围和戈壁，土壤类型主要为壤土、沙土和砂质黏壤土。这与野外实地调研相符，10个实测样地的大赖草均分布于荒漠草地,常以优势种或者伴生种出现在群落中[5]。如,调查的分布在阿勒泰地区福海县阿尔达乡的大赖草种群，为沙拐枣-大赖草、铃铛刺-驼绒藜-大赖草、梭梭-大赖草沙质荒漠草地型;阿勒泰市阿克吐木斯克牧场的驼绒藜-大赖草-三芒草的沙质荒漠草地型；阿勒泰地区哈巴河县萨尔塔木乡国道G331路旁的大赖草-蓝刺头-木蓼和大赖草-蒿属的沙质荒漠草地型等。其中，阿勒泰市阿克吐木斯克牧场的种群被模型识别具有分布的高度适宜性，相关研究也表明该种群具有较高的遗传多样性[8]。

# 3.2大赖草对气候变化的可能响应

气候变化对物种的生活习性、空间格局和分布特征有着重要的影响[28]。国内外学者围绕物种的分布预测开展了大量研究，如，未来气候情景下药用植物华中五味子(Schisandra sphenanthera)的高度适宜生境将减少[15];黄山花楸(Sorbusamabilis)在未来时段的适生区呈减少、破碎化的特点，位于中、低海拔的适生区基本消失或适宜度明显降低[29]。气候变暖促使植物分布向高海拔和高纬度地区迁移[30]。这与本研究结果相同，受未来气候变化的影响，大赖草的适生区范围呈显著缩减趋势，适生区质心向高纬度高海拔地区迁移。本研究表明降水因子主要限制了大赖草的适宜分布，各时段降水因子（最干月降水量和降水量季节性变化)的贡献率大于$5 5 \%$ (图5)，大赖草适生范围变化区域的最不相似变量也主要为最干月降水量和降水量季节性变化（图4)。同时，大赖草适生范围内降水因子的数值范围显著收缩，如降水量季节性变化由基准气候的23.218\~142.685到2070时段的 $2 2 . 6 6 5 { \sim } 1 4 0 . 4 1 3$ ，最干月降水量由基准气候的 $0 { \sim } 2 6 ~ \mathrm { m m }$ 到2070时段的$0 { \sim } 2 0 ~ \mathrm { m m }$ 。因而该植物在2070时段的适宜分布范围相比基准气候面积缩减、向西迁移，尤其是高度适生区变化显著。西北地区作为全球同纬度最干旱的地区之一[31],降水因子是该地区旱生植物生长的决定性环境因素。新疆地区在未来50a和100a中，气候变化特点呈现气温升高、降水增加、干燥度升高的特征，在水分不足的区域如荒漠草原和流动或半固定沙丘上,由于蒸发量增加,土壤水分常处于亏缺状态，水分条件将成为牧草生长的关键限制因素。

![](images/c289f9f44d192b690293e0b1f6742cfe8411e9111c80270ab3187a30490a02ab.jpg)  
图5不同时段下气候因子贡献率对比 Fig.5Comparison of contribution rate of climate factors in different periods

物种保护需要考虑物种的目前适宜和新适宜分布范围及其变化趋势。本研究中，最干月降水量和降水量季节性变化是值得关注的关键因子，如大赖草在基准气候下的高度适宜分布区，由于上述水因子的变化2070时段将发生较大的气候波动，将造成大赖草分布于乌伦古河下游与额尔齐斯河中游沿岸的高度适宜区显著缩减，而这些种群对大赖草的可持续保护具有重要的作用与意义。因此，基准气候下大赖草在这些区域的适宜分布区，如河流沿岸阿勒泰市和布尔津县分布的种群，未来气候情景下将发生显著收缩，应给予重点保护。另外，除了气候因子对物种分布范围的影响，其他因子对物种分布的影响也不容忽视，例如物种间的相互作用、物种的迁移能力以及物种或种群对新环境的适应能力等[33]

# 4结论

本研究利用最大熵模型模拟预测了新疆准噶尔盆地大赖草在基准气候、2050时段和2070时段下的适宜分布。结论如下：

(1）大赖草适宜分布主要集中在额尔齐斯河流域，受气候变化的影响，未来时段适生区的范围呈显著减少趋势，适生区质心向高纬度、高海拔方向迁移，降水(最干月降水量、降水量季节性变化)是影响大赖草分布的关键气候因子。

(2)结合野外调查的人为干扰强度与大赖草种群遗传多样性水平的相关研究，确定额尔齐斯河中下游与乌伦古河下游区域是大赖草种群的恢复和自然更新保护的重点区域，本研究的结果利于深入理解新疆地区沙生植物大赖草的分布、演化与保护。

(3）但本研究在建模过程中，未考虑不同物种分布模型方法，以及不同气候模式可能对模型模拟结果带来的不确定性，而且本研究的模拟结果只代表沙生植物大赖草在准噶尔盆地的潜在适宜分布。

# 参考文献(References):

[1] Warren R,Price J,Graham E,et al.The projected effect on insects,vertebrates,and plants of limiting global warming to 1.5 $\mathrm { { ^ \circ C } }$ rather than 2 ℃[J]. Science,2018,360(6390): 791-795.   
[2] Li $\mathrm { \Delta X }$ ,Tian H,Yuan W,etal.Vulnerability of 2O8 endemic or endangered species in China to the effects of climate change[J].Regional Environmental Change,2013,13(4): 843-852.   
[3]Zhao YF,Pan BR, Zhang ML.Phylogeography and conservation genetics of the endangered Tugarinovia mongolica (Asteraceae) from Inner Mongolia,Northwest China[J]. Plos One,2019,14(2): e0211696.   
[4]中国植物志编委.中国植物志[M].北京:科学出版社,1987:16. [Editorial Boardof the Floraof China.Floraof China[M].Beijing: Science Press,1987: 16.]   
[5]中国饲用植物志编辑委员会.中国饲用植物志[M].北京:农业 出版社,1992: 45-47.[Editorial Committee of The Forage Flora of China.Forage Plantsof China[M]. Beijing:Agriculture Press, 1992: 45-47.]   
[6]潘伯荣,尹林克,王烨.三种沙漠牧草的引种比较[J].干旱区研 究,1991,8(2): 8-11.[Pan Borong, Yin Linke,Wang Ye.The adventitious culture of rare endangered plants in Termperate Desert [J]. Arid Zone Research,1991,8(2): 8-11.]   
[7]Ukpong E O, June-Sik K, Masanori O,et al.Efcient anchoring of alien chromosome segments introgressed into bread wheat by new Leymus racemosus genome-based markers[J]. BMC Genetics, 2018, 19(1): 18.   
[8]蔡小霞,吾买尔夏提·塔汉,代培红,等.大赖草种群遗传多样性 的 AFLP分析[J].干旱区资源与环境,2017,31(9):130-134. [Cai Xiaoxia,Wumaierxiati Tahan,Dai Peihong,etal.AFLP analysis on genetic diversityof Leymus racemosus in Xinjiang[J]. Journal of Arid Land Resources and Environment,2017,31(9):130- 134.]   
[9]黄振英,吴鸿.30种新疆沙生植物的结构及其对沙漠环境的适 应[J].植物生态学报,1997,21(6):521-530.[Huang Zhenying, Wu Hong.The structures of 3O species of psammophytes and their adaptation to the sandy desert environment in Xinjiang[J].Acta Phytoecologica Sinica, 1997,21(6): 521-530.]   
[10]尹林克,谭丽霞,王兵.新疆珍稀濒危特有高等植物[M].乌鲁木 齐：新疆科学技术出版社,2006:134-135.[Yin Linke,Tan Lixia,Wang Bing.Rare Endangered Endemic Higger Plants in Xinjiang of China[M]. Urumqi: Xinjiang Science and Technology Press, 2006: 134-135. ]   
[11] 杨瑞武,周永红,郑有良,等.赖草属三个八倍体和两个十二倍 体物种的核型研究[J].草业学报,2004,13(2):99-105.[Yang Ruiwu, Zhou Yonghong, Zheng Youliang,et al. Leymus karyotypes of three octoploid and two dodecaploid species[J].Acta Pratacu Lturae Sinica,2004,13(2): 99-105.]   
[12] 刘宇,周桂玲.大赖草的交配系统及生殖对策[J].中国沙漠, 2010,20(1): 92-96.[Liu Yu, Zhou Guiling. Mating system and reproductive strategy of Leymus racemosus[J]. Journal of Desert Research,2010,30(1): 92-96.]   
[13] 古丽娜儿·阿不来提,周桂玲,王轶,等.不同贮藏条件对大赖草 种子萌发的影响[J].干旱区研究,2014,31(3):502-507.[Gulnar Ablat,Zhou Guiling,Wang Yi,et al.Effectsof diferent storage conditions on germination of Leymus racemosusseeds[J].Arid Zone Research,2014,31(3): 502-507.]

[14]王超,迪利夏提·哈斯木,周桂玲.不同环境因素对大赖草种子

萌发的影响[J].新疆农业大学学报,2011,34(6):469-473. [Wang Chao,Dilixiati Hasimu, Zhou Guiling.Effectsof diferent environmental factors on the seed germination of Leymus racemosus [J]. Journal of Xinjiang Agricultural University,2011,34(6): 469-473.]   
[15]Guo Y,Wei H,Lu C,et al.Predictions of potential geographical distribution and quality of Schisandra sphenanthera under climate change[J]. PeerJ,2016,4(10): e2554.   
[16]Kumar S,Stohlgren TJ. Maxent modeling for predicting suitable habitat for threatened and endangered tree Canacomyrica monticola in New Caledonia[J]. Journal of ecology& the natural environment,2009,1(4): 94-98.   
[17] 钱亦兵,吴兆宁,张立运,等.古尔班通古特沙漠植被与环境的 关系[J].生态学报,2007,27(7):2802-2811.[Qian Yibing,Wu Zhaoning, Zhang Liyun,et al.Vegetation-environment relationships in Gurbantunggut Desert[J].Acta Ecologica Sinica,2Oo7,27(7): 2802-2811.]   
[18]傅伯杰,刘国华,孟庆华.中国西部生态区划及其区域发展对策 [J].干旱区地理,2000,23(4): 289-297.[Fu Bojie,Liu Guohua, Meng Qinghua,etal. Eco-regionalization of West China its regional development countermeasures[J]. Arid Land Geography,2000, 23(4): 289-297.]   
[19] 许鹏.新疆北疆平原荒漠生态特征、问题与对策[J].草叶学报, 1997,6(4): 6-10.[Xu Peng. Ecological characteristics,problems and developmental strategyof plain desert in northern Xijiang[J]. Acta Prataculturae Sinica,1997,6(4): 6-10.]   
[20] 薛晓东,吾买尔夏提·塔汉,代培红,等.新疆阿勒泰地区5个大 赖草种群的表型多样性分析[J].植物资源与环境学报,2016, 25(2): 85-91. [Xue Xiaodong,Wumaierxiati Tahan, Dai Peihong, et al.Analysis on phenotypic diversity of five populations of Leymus racemosus in Altai Region of Xinjiang[J]. Journal of Plant Resources and Environment,2016,25(2): 85-91.]   
[21] 古丽娜儿·阿不来提,周桂玲,阿依吐尔汗·热依木.大赖草(Leymus racemosus)结实格局[J].中国沙漠,2014,34(4):1037-1041. [Gulnar Ablat, ZhouGuiling,Ayturhan Rayim.Fruit-setpatterns of Leymus racemosus[J]. Journal of Desert Research, 2O14, 34(4): 1037-1041.]   
[22] 张文秀,寇一翻,张丽,等.采用生态位模拟预测濒危植物白豆 杉5个时期的适宜分布区[J].生态学杂志,2020,39(2):600- 613.[Zhang Wenxiu,Kou Yixuan, Zhang Li,etal. Suitabledistribution of endangered species Pseudotaxus chienii (Cheng) Cheng (Taxaceae) in five periods using niche modeling[J]. Chinese Journal of Ecology,2020,39(2): 600-613.]   
[23]Parolo G, Rossi G,Ferrarini A. Toward improved species niche modeling: Arnica montana in the Alps as a case study[J]. Journal of Applied Ecology,2008,45(5): 1410-1418.   
[24] 塞依丁·海米提,努尔巴依·阿布都沙力克,李雪萍,等.气候变 化及人类活动对蒙古沙拐枣分布格局的影响[J].干旱区研究, 2018,35(6):1450-1459.[Sayit Hamit,Nurbay Abdushalih,Li Xueping,etal.Efects ofclimatechangeand human activitieson the distribution pattern of Calligonum mongolicum Turcz.[J].Arid Zone Research,2018,35(6): 1450-1459.]   
[25] 张兴旺,李垚,谢艳萍,等.气候变化对黄山花楸潜在地理分布 的影响[J].植物资源与环境学报,2018,27(4):31-41.[Zhang Xingwang,Li Yao,Xie Yanping,etal. Effect of climate change on potential geographical distribution of Sorbus amabilis[J].Journal of Plant Resources and Environment,2018,27(4):31-41.]   
[26]Elith J,Kearney M,Phillips S. The art of modelling range-shifting species[J].Methods in Ecology& Evolution,2010,1(4):330-342.   
[27] 张丹,刘凯军,马松梅,等.高山植物天山花楸的适宜分布及其 环境驱动因子研究[J].生态学报,2022,42(2):1-10.[Zhang Da, Liu Kaijun,Ma Songmei,et al. The suitable distrbution of alpine plant Sorbus tianschanicn and its environmental driving factors[J]. Acta Ecologica Sinica,2022,42(2):1-10.]   
[28]Rosenzweig C,Karoly D,VicareliI M,et al.Attributingphysical and biological impacts to anthropogenic climate change[J].Nature, 2008,453(7193): 353-357.   
[29]Zhang X W,Li Y,XieYP,etal.Effect of climate change on potential geographical distribution of Sorbus amabilis[J].Journal of Plant Resources and Environment,2018,27(4): 31-41.   
[30]Root TL,Price JT,Hall KR,et al.Fingerprints of global warming on wild animals and plants[J].Nature,2003,421(6918): 57-60.   
[31] 刘引鸽.西北干旱灾害影响因子分析[J].灾害学,2003,18(2): 18-22.[Liu Yinge.Analysis on the influencing factors of drought disaster in Northwest China[J]. Journal of Catastrophology,2003, 18(2): 18-22.]   
[32]《气候变化国家评估报告》编写委员会.气候变化国家评估报告 [M].北京:科学出版社,20O7.[Editorial Committee of National Assessment Report on Climate Change.National Assessment Report on Climate Change[M]. Beijing: Science Press,2007.]   
[33]朱耿平,刘国卿，卜文俊,等.生态位模型的基本原理及其在生 物多样性保护中的应用[J].生物多样性,2013,21(1):90-98. [Zhu Gengping,Liu Guoqing,Bu Wenjun,et al.Ecological niche modeling and its applications in biodiversity conservation[J].Biodiversity Science,2013,21(1): 90-98.]

# Distribution pattern and driving mechanisms of the sand plant Leymus racemosus in the Junggar Basin

ZHANG Lin'， ZHANG Yunling²， MA Songmei'， ZHANG Dan³， HE Lingyun' (1. College of Science,Shihezi University, Corps Key Laboratory ofOasis Towns and Mountain Basin Ecosystems,   
KeyLaboratoryofLandscape EcologyinAridRegion,Shihezi 832Ooo,Xinjiang,China;2.General Grassland Station   
of Xinjiang,Urumqi 830049, Xinjiang, China; 2.ColegeofLife Sciences,Shihezi University,Corps KeyLaboratory of Oasis Towns and Mountain Basin Ecosystems,Shihezi 832ooo,Xinjiang, China)

Abstract: Our objective was to simulate and predict ecological suitability, posible suitable distribution range, spatial distribution characteristics,and possble response to future climate change of Leymus racemosus (Lam.) Tzvelev in Xinjiang.The data in this study were based on 24 natural distribution sites and eight environmental factors of Leymus racemosus and were analyzed using GIS spatial analysis and the MaxEnt model.The suitable distribution range and changes in the distribution patern of Leymus racemosus in Xinjiang under the present climate (1970-2000),the 2050 period (2041-2060),and the 2070 period (2081-2100) for the“Middle of the Road” narrative (SSP2） of the shared socioeconomic pathways were analyzed. We used multivariate environmental similarity surface analysis and the most dissimilar variable to explore the key climatic factors. Under the present climate, the suitable distribution area of Leymus racemosus accounts for $5 . 5 7 \%$ of the total area of Xinjiang,mainly concentrated in the low-cover grasslands near the Irtysh River. Compared with the present climate,the suitable habitat of Leymus racemosus will be significantly reduced by $0 . 9 9 \%$ and $1 . 3 3 \%$ in 2050 and 2070,respectively;its suitable habitat willbe highly fragmented,and thecenter of itssuitable habitat will move to the Northwest at higher latitudes and higher elevations.Factors that mainly influencethe suitable distribution of Leymus racemosus in Xinjiang are the precipitation of the driest month, precipitation seasonality $( C _ { \mathrm { v } } )$ ,and the standard deviation of seasonal temperature variation.

Keywords: Leymus racemosus; suitable distribution; MaxEnt model; driving factor； future climate change; Junggar Basin