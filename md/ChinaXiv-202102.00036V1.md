# 区域建设用地开发强度格局演化及影响因素分析以陕西省为例

王博}，黄晓军1,23,4，刘萌萌1(1 西北大学城市与环境学院,陕西 西安710127；2 陕西省地表系统与环境承载力重点实验室,陕西 西安710127；3陕西省黄河研究院,陕西 西安710127；4 陕西西安城市生态系统定位观测研究站,陕西 西安710127)

摘要：区域建设用地开发强度是揭示土地利用效率、社会经济发展水平与国土空间开发状态的重要指标，对其变化进行监测与管治是优化国土空间开发格局，实现区域可持续发展的重要手段。构建建设用地开发强度量化模型，以陕西省为例,计算2000—2015年县域建设用地开发强度指数，利用空间自相关分析方法揭示其空间格局和演化特征，并采用最小二乘法(OLS)和地理加权回归(GWR)模型识别建设用地开发强度格局演化的影响因素。结果表明：(1)2000—2015年陕西省建设用地开发强度总体呈现增长态势，内部空间分异显著，高强度区集中在榆林、延安、西安、安康等地，低强度区集中在咸阳、宝鸡、铜川、商洛、渭南、汉中等地。(2)陕西省建设用地开发强度呈现出明显的空间集聚状态，热点区稳定分布在西安市辖区及周边区县，冷点区分布在延安南部、咸阳、铜川、渭南和汉中等部分区域；县域建设用地开发强度逐步提升的同时，区域开发不平衡现象日益突显。(3）固定资产投资、居民消费水平、财政投入力度、耕地资源和地形条件是影响陕西省建设用地开发强度空间分异的主要因素，但在不同县域其影响程度大小具有显著差异，且个别因素的影响具有不稳定性。

关键词：建设用地;开发强度；格局;影响因素；陕西省

# 文章编号：

近年来，中国快速的城镇化发展对建设用地空间形成了巨大需求，全国建设用地面积已从2002年的 $3 0 7 3 0 0 { \mathrm { k m } } ^ { 2 }$ 增长至2016年的 $3 9 0 9 5 1 { \mathrm { k m } } ^ { 2 }$ ，年均增长 $1 . 7 5 \%$ 。在保障国家粮食安全与保护耕地资源前提下，建设用地的高需求致使国土空间开发强度不断加大，对区域水土资源和生态环境的可持续发展带来严峻挑战[1]。与此同时,建设用地开发强度的空间不均衡现象仍十分显著，过度开发与粗放利用并存，同区域的资源环境承载能力严重不匹配。全国"国土资源十三五"规划中明确提出“实行建设用地总量和强度双控行动”，以进一步强化建设用地管理。建设用地开发强度已成为监控地区土地利用水平和调控土地资源配置的重要指标[2-3],加强建设用地开发强度管控是优化国土空间格局，促进其与区域资源环境承载能力相适应，实现区域可持续发展的重要途径。

目前有关建设用地开发强度的研究主要集中在4个方面：（1）土地开发强度评价研究。宏观尺度上，多以建设用地面积占区域土地总面积比重来衡量区域土地利用程度或人类活动强度，并对建设用地开发强度进行相应评价[4-5];微观尺度上，侧重于容积率、建筑密度和建筑高度等指标评估土地开发强度[6-7]。（2）建用地开发强度演变的生态环境效应研究。集中探讨建设用地开发强度变化对碳排

# 干旱区地理

放效率[8]生态系统服务价值[、生态环境容量[]及生物多样性[1I-12]等的作用关系，明确了建设用地开发对生态环境的影响。（3）建设用地开发强度与资源环境承载力的耦合研究。分别构建区域开发强度与水、土、生态等资源环境承载力指标体系[13-15]，采用耦合度模型判别二者之间的协调程度，分析区域可持续发展状态。（4）土地利用空间均衡度研究。通过衡量土地供给能力和土地开发强度之间的强弱关系来判断区域土地利用均衡度[16-19]。总体而言，当前有关建设用地开发强度的研究已取得一定成果，但受多方面因素制约，相关研究还存在一定的局限性。一是由于现行统计数据只能获取城市建设用地面积，因此针对建设用地开发强度评价的研究多以地级市为研究单元，侧重于对城市土地开发强度的测度，而对于县域尺度建设用地开发强度的研究相对较弱；二是缺乏建设用地开发强度的长时间序列评价，即对于建设用地开发强度时空演化特征的研究稍显不足；三是当前多数研究集中在建设用地开发强度与资源、环境、生态等要素的耦合协调性探讨，而对建设用地开发强度的影响因素及其空间异质性缺乏深入系统的分析。

基于此，本文整合土地利用现状遥感监测数据和社会经济统计数据，将建设用地开发强度视为区域土地利用程度及其人口承载密度、经济产出力度的综合反映，以陕西省107个县域单元为研究对象，量化测度2000—2015年陕西省县域建设用地开发强度指数，并利用空间自相关技术揭示其空间格局及演化特征，最后采用普通最小二乘法(OLS)和地理加权回归(GWR)模型识别并分析建设用地开发强度的影响因素。本文可为区域建设用地开发强度空间分异及其影响因素等相关研究提供案例借鉴，在实践上可为陕西省建设用地的有序开发与合理利用提供科学决策依据。

# 研究区概况与数据

# 1.1 研究区概况

陕西省地处我国西北地区，土地面积 $2 0 . 5 8 \times 1 0 ^ { 4 }$ $ { \mathrm { k m } } ^ { 2 }$ ,2016年常住人口 $3 \ 8 1 3 \times 1 0 ^ { 4 }$ 人，全省辖10个地级市和107个县(县级市、市辖区）。根据自然地理特征差异，陕西省可划分为三大区域(图1)，即陕北黄土高原区、中部关中平原区和陕南秦巴山地区。近年来，随着社会经济快速发展，陕西省建设用地

府谷县县域神木县市域黄土高原关中平原 佳县秦巴山地 米脂横山县吴堡县0 50km J 定边县 靖边县 茅洲县绥德县子长县清涧县吴起县 安塞县延川县志丹县 S 延长县甘泉县宜川县富县洛川县黄陵县黄龙县韩城市宜君县白水县长武彬县州区城县 包员县 铜川市澄城县合阳县陇县 寿县淳化县富平县大荔县千阳县麟游县咸阳市泾阳 南华阴市凤翔县乾县礼泉县华县仓区岐山县风 县宝鸡市眉县 兴平市 西安市 蓝田 洛南县凤县 户县长安区商洛市太白县周至县 柞水县 丹凤县略阳县 留坝县 佛坪县宁陕县 洋县 镇安县 山阳县商南县勉县城固县 有泉县强县 汉中县 西乡县 汉阴县 安康市河县镇巴县紫阳县 平利县皋县

规模不断扩大，2002—2016年，全省建设用地面积从 $7 8 3 1 ~ \mathrm { k m } ^ { 2 }$ 增长至 $1 3 7 7 5 { \mathrm { k m } } ^ { 2 }$ ,年均增长 $4 . 7 7 \%$ 。建设用地大规模开发的同时，也呈现出诸多问题，集中体现在建设用地的无序扩张与粗放利用、农村居民点土地空间的闲置化、生态脆弱区的资源环境超载以及过度开发带来的严重水土流失、环境污染等生态问题。如何优化国土空间开发模式，促进建设用地合理利用，实现社会经济与生态环境协调发展已成为当前陕西省面临的重要现实问题。

# 1.2数据来源

本文土地利用数据来源于中国科学院资源环境科学数据中心（http://www.resdc.cn）的4期（2000年、2005年、2010年、2015年)土地利用遥感监测数据。依据其分类系统，建设用地包括城镇用地、农村居民点和其它建设用地。地形坡度数据来源于国家地球系统科学数据共享平台(http://www.geodata.cn)。社会经济数据来源于2001—2016年《陕西区域统计年鉴》、《陕西省统计年鉴》以及各城市统计年鉴。本文以陕西省107个县域空间(县、县级市、市辖区）为研究单元，为便于比较分析，以2015年陕西省行政区划为标准对往年行政区划进行调整并统一。

# 2 研究方法

# 2.1建设用地开发强度模型

建设用地开发强度是一个综合指数，其反映了一定区域内的建设用地利用水平以及人口与社会经济要素的承载强度[20-22]。基于此，本文选取建设用地比重、人口承载强度和经济开发力度来综合表征建设用地开发强度。计算公式如下：

$$
C L D I = \alpha C L P + \beta P C S + \gamma E D I
$$

其中，建设用地比重 $( C L P )$ 反映了区域建设用地开发规模，用建设用地面积除以区域总面积来表示；人口承载强度 $( P C S )$ 反映了区域建设用地的人口承载能力，用总人口除以建设用地面积来表示;经济开发力度 $( E D I )$ 反映了区域建设用地的经济产出能力，用二、三产业产值除以建设用地面积来表示； $\alpha \cdot \beta \cdot \gamma$ 分别为建设用地比重、人口承载强度、经济开发力度的权重。由于 $\ C L P , P C S , E D I$ 均为正向指标，首先采用正向标准化的方法对原始数据进行处理，标准化公式为：

$$
Y _ { i j } = ( X _ { i j } - X _ { j \operatorname* { m i n } } ) / ( X _ { j \operatorname* { m a x } } - X _ { j \operatorname* { m i n } } )
$$

式中： $X _ { i j } \setminus X _ { j m a x } \setminus X _ { j m i n }$ 和 $Y _ { i j }$ 分别为第 $i$ 研究对象第 $j$ 指标的原始值、最大值、最小值和标准化值。然后采用熵值法确定 $\alpha , \beta , \gamma$ 权重值分别为0.54、0.17、0.29，最后综合计算建设用地开发强度数值。

# 2.2 空间自相关

引入空间自相关方法检验县域单元之间建设用地开发强度是否具有显著关联性。空间自相关包括全局自相关和局部自相关，全局自相关常用

Moran'sI指数来描述整个区域某种现象的空间关联和空间差异，取值范围为[-1,1]，当 $- 1 \leqslant j$ Moran's$I { < } 0$ 时，表明空间单元呈负相关；当 $0 <$ Moran's $I { \leqslant } 1$ 时，表明空间单元呈正相关;当Moran's $\scriptstyle { I = 0 }$ 时，表明不相关[23]。局部空间自相关能反映某一空间单元的属性值与邻接空间单元之间的局部关联，识别出聚集发生的具体空间位置[24]，常用Getis-OrdGi\*指数来识别空间对象属性值的高值簇或热点区与低值簇或冷点区。

# 2.3基于OLS与GWR模型的影响因素空间异质性分析

传统线性回归模型(OLS)并没有考虑空间格局要素，只是对所有样本和参数进行整体的回归计算，而地理加权回归(GWR)模型可以对不同区域的影响进行估计，能够反映参数在空间分布的差异性，使得空间位置不同的参数产生变化，结果也更符合实际[25]。地理加权回归模型如下：

$y _ { i } = \beta _ { 0 } { \big ( } u _ { i } , v _ { i } { \big ) } + \beta _ { 1 } { \big ( } u _ { 1 } , u _ { 2 } { \big ) } + \cdots + \beta _ { p } { \big ( } u _ { i } , v _ { i } { \big ) } x _ { p } + \varepsilon _ { i }$ (3)式中： $y _ { i }$ 为因变量; $\beta _ { \mathfrak { o } }$ 为回归模型截距项; $\left( u _ { i } , v _ { i } \right)$ 为第 $i$ 个样本的空间坐标; $\beta _ { _ p } ( u _ { i } , v _ { i } )$ 为第 $p$ 个自变量的系数； $p$ 为自变量个数； $\pmb { \varepsilon } _ { i } ( i = 1 , 2 , \cdots , p )$ 为独立分布的随机误差项。GWR模型中的权重设定为观测点之间距离的函数，带宽在很大程度上会影响模型的精度，确定带宽的方法有赤池信息准则法（AIC）、交叉确认法(CV)等[26],由于AIC方法兼顾了不同模型存在不同自由度的差异，故本文在计算时采取高斯函数确定权重，采用AIC方法确定最优带宽[27]。

建设用地开发强度是对人类社会经济活动过程中土地利用水平与程度的衡量，因此，受到人口、社会、经济、资源等多种因素的共同影响。基于科学性、客观性以及可获取性等原则，本文从经济发

表1建设用地开发强度空间分异影响因素  
Tab.1Influencing factors of spatial differentiation of construction land development intensity   

<html><body><table><tr><td>指标名称</td><td>指标计算</td><td>指标释义</td></tr><tr><td>人均GDP</td><td>GDP/总人口</td><td>经济发展水平</td></tr><tr><td>二、三产比重</td><td>二、三产产值/GDP</td><td>产业结构水平</td></tr><tr><td>非农人口</td><td>通过统计年鉴获取非农业人口数</td><td>用地人口数量</td></tr><tr><td>地均固定资产投资</td><td>固定资产投资总额/建设用地面积</td><td>建设投资强度</td></tr><tr><td>人均社会消费品零售总额</td><td>社会消费品零售总额/总人口</td><td>居民消费水平</td></tr><tr><td>财政支出占GDP比重</td><td>地方财政支出/GDP</td><td>财政投入力度</td></tr><tr><td>人均耕地面积</td><td>常用耕地面积/总人口</td><td>地区资源禀赋</td></tr><tr><td>地形条件</td><td>通过DEM数据提取坡度值</td><td>自然本底条件</td></tr></table></body></html>

# 干吴区地理

展、人口规模、投资消费、资源禀赋、自然条件、政府调控等方面选取影响建设用地开发强度的驱动因素(表1)。土地利用程度和效率与经济发展水平密切相关，故选取人均GDP和二、三产比重来反映地区经济发展水平；非农人口数反映了城市人口对建设空间的需求，是建设用地扩张的动力之一；投资和消费是驱动经济发展的主要力量，经济增长会进一步对建设空间形成需求;耕地是建设用地扩张的主要来源，人均耕地面积反映了地区资源禀赋；地形条件是限制建设用地开发的重要因素，故选取坡度值反映自然本底条件；政府作为土地的管理者，其调控手段影响着建设用地的利用效率和开发强度[28],故选取财政支出占GDP比重来表征政府调控对建设用地开发的影响。

# 3结果与分析

# 3.1陕西省建设用地开发强度格局演化

3.1.1总体格局变化分别计算各县域建设用地比重、人口承载强度和经济开发力度，将结果代人公式(1)计算得出陕西省县域建设用地开发强度，采用自然断点方法将其划分为高强度区、次高强度区、次低强度区和低强度区，进而分析2000—2015年各县域3个维度以及建设用地开发强度空间格局演变特征。

从建设用地比重来看（图2），2000—2015年各县域建设用地比重均发生明显增长，省域平均建设用地比重由 $6 . 6 7 \%$ 上升至 $8 . 8 9 \%$ 。空间分布上则呈现出显著的不均衡态势，建设用地比重高值区主要集中在关中地区，其中，西安市主城区建设用地比重最高，咸阳市辖区次之；陕北和陕南地区建设用地比重则处于相对较低水平。

![](images/259880c6edd46fdf9927522ec175862b35903358296b63b6c5aedbe9ecc8e0e4.jpg)  
Fig.2 Spatial distribution of proportion of construction land in Shaanxi Province from 2Ooo to 2015

![](images/39023bf881bce4c72df09d4787fda72c5a09209a0d6c8491921a86c3bf0ea160.jpg)  
图22000—2015年陕西省建设用地比重空间分布  
图32000—2015年陕西省人口承载强度空间分布  
Fig.3Spatial distribution of population carrying capacity in Shaanxi Province from 2Oo0 to 2015

从人口承载强度来看（图3），2000—2015年各县域人口承载强度均发生明显下降，省域平均人口承载强度由21633人· $\mathrm { k m } ^ { - 2 }$ 减少至14612人· $\mathrm { k m } ^ { - 2 }$ ○陕西省人口承载强度较高地区集中在陕北与陕南，而关中地区则处于较低水平。此外，从2000—2015年，由于县域建设用地规模提升，人口承载强度高值区发生明显减少，其中榆林市、安康市下降最为明显。

从经济开发力度来看(图4)，2000—2015年各县域经济开发力度均发生明显增长，省域平均经济开发力度由 $0 . 6 0 \times 1 0 ^ { 8 }$ 元· $\mathrm { k m } ^ { - 2 }$ 上升至 $4 . 5 9 \times 1 0 ^ { 8 }$ 元· $\mathrm { k m } ^ { - 2 }$ 。县域经济开发力度空间分异显著，经济开发力度较高的区域主要集中在榆林市，延安北部，安康市及西安、咸阳、宝鸡三地市辖区，而关中大部分县域的经济开发力度处于较低水平。此外，从2000一2015年，陕南地区县域经济开发力度高值区明显增多。

从建设用地开发强度来看(图5)，陕西省县域建设用地开发强度呈现出增长态势，省域平均开发强度由2000年的0.086增长到2015年的0.121。从空间分布来看，高强度区主要分布在西安市主城区，榆林市的清涧、子洲、佳县、吴起，延安市的子长、延长、志丹，安康市的旬阳、汉阴、白河、紫阳等县域。低强度区主要分布在榆林市北部、延安市南

![](images/f97be06b8d1a1ca54b5b64f0519b03dcf7ca69184e162ed72068c170f4c9b5bf.jpg)  
Fig.4Spatial distribution of economic development intensity in Shaanxi Province from 2OoO to 2015

![](images/46f3e737e43a721024b65e9d26a0a266d7d5241ccca4853b88279ae1ed60ca99.jpg)  
图42000—2015年陕西省经济开发力度空间分布  
图52000—2015年陕西省建设用地开发强度空间分布

Fig.5Spatial distribution of construction land development intensityin Shaanxi Province from 2Oo0 to 2015

# 干吴区地理

部以及咸阳市、宝鸡市、铜川市、渭南市、汉中市等所辖部分县域。

具体来看，2000年陕西省建设用地开发强度处于低或次低强度的县域共有93个，处于高或次高强度的县域共有14个；2005年低或次低强度县域减少至81个，而高或次高强度县域增长至26个，这一时期县域建设用地开发强度明显提升，其中西安市周边县域及榆林南部、延安北部最为突出；2010—2015年县域开发强度仍在继续增长，但除了榆林、安康部分县域有所变化外，总体格局变化较小，低或次低强度县域个数稳定在80个左右，而高或次高强度县域个数则在27个左右。由此可知，陕西省县域建设用地开发强度总体仍处于较低水平，高开发强度县域所占比例较小。此外，从具体县域单元来看，关中地区城市市辖区开发强度普遍高于所辖县，陕北、陕南地区则不明显，原因可能在于陕北、陕南地区城市市辖区建设用地利用效率较低，其人口承载强度以及经济开发力度甚至低于部分县域，从而导致其建设用地开发强度也低于部分县域

# 3.1.2空间关系变化

# (1)全局空间关系

分别计算4个时段陕西省建设用地开发强度全局Moran'sI指数，结果显示2000年、2005年、2010年和2015年的Moran'sI指数分别为0.636、0.657、0.704和0.710，且均通过显著性检验(Z值大于临界值1.96)，表明陕西省建设用地开发强度呈现显著的空间集聚状态。与此同时，2000—2015年Moran'sI指数逐渐增大，说明空间上的整体集聚特征逐年

增强。

# (2)局部空间关系

分别计算4个年份陕西省建设用地开发强度的Getis-OrdGi\*指数，并采用自然断裂点方法将其划分为冷点区、次冷点区、次热点区、热点区。结果显示（图6)，2000—2015年建设用地开发强度的热点区一直稳定分布在西安市辖区及周边区县，次热点区分布在榆林南部、延安北部以及安康市部分区域，冷点区分布在延安南部、咸阳、铜川、渭南和汉中等部分区域，次冷点区分布在榆林北部、宝鸡和商洛等区域；并且次热点区、冷点区呈现出先增加后减少的趋势，而次冷点区则呈现先减少后增加的趋势，说明区域开发不均衡现象先加剧后有所减缓。总体而言，热冷点格局呈现出陕北、陕南、关中各有一块高值区而低值区连片分布的状态，与建设用地开发强度全局变化及空间异质性态势基本吻合。

# 3.2陕西省建设用地开发强度影响因素的空间异质性分析

3.2.1基于OLS模型的影响因素识别首先采用OLS模型识别2000—2015年陕西省建设用地开发强度的影响因素。结果显示(表2)，模型的校正决定系数均在0.75以上，即模型能解释样本 $7 5 \%$ 以上的变化。其中，地均固定资产投资、人均社会消费品零售总额、财政支出占GDP比重、人均耕地面积及地形起伏度5个变量通过显著性检验（ $( P { < } 0 . 0 5 )$ ，是影响陕西省建设用地开发强度的主要因子。

固定资产投资对建设用地开发强度的影响体现在，单位建设用地面积上投入资金越多，人口、产

![](images/e20af54bf5587b390af00fc470ca02e48772faf5d82fbee60862f322cc589f06.jpg)  
图62000—2015年陕西省建设用地开发强度Getis-OrdGi\*分布

Fig.6Getis-Ord $G i ^ { * }$ spatial distribution of construction land development intensity in Shaanxi Province from 2OOO to 2015业集聚效果越明显，建设用地的人口承载能力以及经济产出效益便得到加强，进而促进建设用地开发强度的提升。但建设用地的承载能力以及产出效益具有上限，当单位建设用地承载人口数以及经济效益达到峰值后，即使再加大投资力度，开发强度难以继续提高。

Tab.2 Regression results and parametersof OLS model   

<html><body><table><tr><td rowspan="2">变量</td><td colspan="2">2000年</td><td colspan="2">2005年</td><td colspan="2">2010年</td><td colspan="2">2015年</td></tr><tr><td>系数</td><td>P值</td><td>系数</td><td>P值</td><td>系数</td><td>P值</td><td>系数</td><td>P值</td></tr><tr><td>人均GDP</td><td>-0.083</td><td>0.097</td><td>-0.008</td><td>0.922</td><td>-0.039</td><td>0.223</td><td>-0.028</td><td>0.590</td></tr><tr><td>二、三产比重</td><td>-0.029</td><td>0.276</td><td>-0.035</td><td>0.235</td><td>-0.023</td><td>0.347</td><td>0.009</td><td>0.764</td></tr><tr><td>非农人口</td><td>0.184</td><td>0.102</td><td>0.134</td><td>0.068</td><td>0.097</td><td>0.066</td><td>0.108</td><td>0.194</td></tr><tr><td>地均固定资产投资</td><td>0.173</td><td>0.000***</td><td>0.232</td><td>0.001**</td><td>0.331</td><td>0.000**</td><td>0.222</td><td>0.000***</td></tr><tr><td>人均社会消费品零售总额</td><td>0.426</td><td>0.000**</td><td>0.440</td><td>0.000**</td><td>0.301</td><td>0.000**</td><td>0.542</td><td>0.000****</td></tr><tr><td>财政支出占GDP比重</td><td>0.384</td><td>0.000***</td><td>0.204</td><td>0.004**</td><td>0.078</td><td>0.040*</td><td>0.103</td><td>0.191</td></tr><tr><td>人均耕地面积</td><td>-0.053</td><td>0.083</td><td>-0.063</td><td>0.037°</td><td>-0.145</td><td>0.034*</td><td>-0.086</td><td>0.093</td></tr><tr><td>地形起伏度</td><td>-0.023</td><td>0.158</td><td>-0.011</td><td>0.416</td><td>-0.063</td><td>0.001**</td><td>-0.041</td><td>0.173</td></tr><tr><td>多重决定系数</td><td colspan="2">0.796</td><td colspan="2">0.841</td><td colspan="2">0.890</td><td colspan="2"></td></tr><tr><td>校正决定系数</td><td colspan="2">0.780</td><td colspan="2">0.828</td><td colspan="2">0.881</td><td colspan="2">0.762</td></tr><tr><td>阿凯克信息准则(AICc)</td><td colspan="2">-346.751</td><td colspan="2">-357.277</td><td colspan="2">-372.764</td><td colspan="2">0.743 -258.445</td></tr></table></body></html>

注：\*\*\*表示 $9 9 . 9 \%$ 显著性水平；\*\*表示 $9 9 \%$ 显著性水平；\*表示 $9 5 \%$ 显著性水平

消费作为驱动经济增长的主要动力之一，对建设用地开发强度也具有重要影响。居民消费能力持续上升且消费结构不断升级，形成对居住、商业、休闲等空间的强烈需求，意味着更多的建设用地被用来承担生产活动，因此极大促进了城市建设用地的开发强度。

地方政府在基础建设、企业改造、社会服务等方面的财政支出都会在一定程度上增加建设用地规模或加大建设用地开发强度，因此，财政投入力度大的地区，其建设用地比重，人口承载强度以及经济开发力度往往越强，建设用地开发强度也越大。

人均耕地面积和地形起伏度与建设用地开发强度呈负相关。耕地是建设用地的主要来源，如果区域耕地资源有限，必然会形成建设用地开发强度的增大;相反，如果区域耕地资源丰富，则容易出现建设用地的无序扩张和低效利用。同样，地形起伏度决定了建设用地的开发条件和利用潜力，进而对建设用地开发强度形成了不同程度的约束作用。

3.2.2基于GWR模型的影响因素空间异质性分析为进一步探讨影响因素的空间分异，在OLS分析基础上引入GWR模型对2000年、2005年、2010年和2015年陕西省建设用地开发强度影响因素的空间分异参数进行估计。结果显示(表3),4个时期的校正决定系数分别为0.815、0.866、0.903、0.773，较OLS模型有所提升；阿凯克信息准则分别为-358.431、-378.439、-387.433、-264.713，较0LS模型更小，表明GWR模型拟合效果更好。结合OLS模型识别出的5个显著影响因素，利用GWR模型对这5个影响因素的回归系数进行空间可视化，得到各解释变量回归系数的空间分布。

表2OLS模型回归结果及参数  
表3GWR模型相关参数  
Tab.3 Related parametersofGWRmodel   

<html><body><table><tr><td>参数</td><td>2000年</td><td>2005年</td><td>2010年</td><td>2015年</td></tr><tr><td>多重决定系数</td><td>0.850</td><td>0.890</td><td>0.920</td><td>0.815</td></tr><tr><td>校正决定系数</td><td>0.815</td><td>0.866</td><td>0.903</td><td>0.773</td></tr><tr><td>阿凯克信息准 则(AICc)</td><td>-358.431</td><td>-378.439</td><td>-387.433</td><td>-264.713</td></tr></table></body></html>

# (1）地均固定资产投资

2000—2015年地均固定资产投资与建设用地开发强度的回归系数先增大后减小，说明固定资产投资对建设用地开发强度的影响先增强后减弱，原因在于基础设施建设水平到达一定高度后，即使再增加固定资产投入，建设用地开发强度也难以大幅提升。从回归系数空间分布来看（图7)，2000—2010年回归系数空间分布变化较小，总体上呈现从陕北至陕南逐步增加的态势；与之相比，2015年变化较大，回归系数低值区由陕北转至关中地区的宝鸡市，而陕北由低值区转变成次高值区，且关中地区的中值区向北延伸，总体上呈现出从西北向东南逐步增加的态势。2010—2015年回归系数空间格局发生变化的原因在于这一时期陕北地区大力开展延安新城建设以及榆(林)横(山)一体化建设，固定资产投资带来了城市扩张以及基础设施的进一步扩建，使得建设用地规模和开发强度都得到增强。

![](images/ff8cc54d6aadacc3a061563d850cc4b1e4d19cc45cde20d045305a163ef6e9bf.jpg)  
干旱区地理  
图72000—2015年地均固定资产投资回归系数空间分布

# (2）人均社会消费品零售总额

居民消费水平与建设用地开发强度呈正相关，且回归系数较高，说明居民消费水平对建设用地开发强度的影响较大。从回归系数空间分布来看(图8)，2000年人均社会消费品零售总额回归系数自西北向东南逐渐增加；2005年回归系数低值区覆盖整个陕北地区，回归系数高值区向南部汉中市、安康市转移，总体上呈现从陕北向陕南递增的趋势；2010年回归系数整体缩小且高值区转移到陕北，陕南由高值区变成中、次低值区；2015年回归系数在陕南与陕北延安形成高、次高值区，而在关中地区形成中值区。总体来看，2000—2015年回归系数在空间分布上没有一致性规律，说明不同年份居民消费水平对建设用地开发强度影响差异显著。

# （3）财政支出占GDP比重

2000—2015年财政支出占GDP比重回归系数呈现减小趋势，表明财政投入对建设用地开发强度的影响有所减弱。从回归系数空间分布来看（图9)，2000—2005年回归系数分布格局未发生显著变化，但陕南回归系数低值区逐渐减少，次低值区逐渐增多；2005—2010年陕北地区发生较大变化，各等级回归系数均有分布，说明陕北地区受财政投入影响差异显著;2010—2015年高值区几乎覆盖整个陕北地区，而陕南低值区进一步减少。总体来看，财政支出占GDP比重的回归系数呈现从北向南递减的态势。结合建设用地开发强度空间分布来看，建设用地开发中高强度区、低强度区与回归系数低值区、次高值区有一定重合，说明建设用地开发中高强度区对于政府财政投人具有低敏感性，而低强度区对于财政投入具有高敏感性。

![](images/226ad44f7643e0df1c3fc628c192cd1945feda7f286a9e9708370269c50c6b98.jpg)  
Fig.7Spatial distribution of regression coefficient of per area fixed asset investment from 2Ooo to 2015   
图82000—2015年人均社会消费品零售总额回归系数空间分布  
Fig.8Spatial distribution of regression coefficient of per capita retail sales from 2OoO to 2015

![](images/618fb53fc56cdf289556d1a2c3dd35405054a2958c3eee709796189a668a72b7.jpg)  
王博等：区域建设用地开发强度格局演化及影响因素分析——以陕西省为例  
图92000—2015年财政支出占GDP比重回归系数空间分布

逐渐增大，至2015年又有所下降，表明在建设用地的增量扩张背景下，耕地资源的逐年减少对建设用地开发强度的影响增强，而在建设用地的存量利用效率提升背景下，耕地资源对建设用地开发强度的影响逐渐减弱。从回归系数空间分布来看(图10)，2000年回归系数高值区分布在关中平原，陕北和陕南是低值区；2005年高值区转至宝鸡，形成自东北向西南递增的格局；2010年变化显著，陕北为高值区，陕南为低值区，形成由南向北递增的态势；2015年高值区集中在榆林北部，中、低值区向东南方向蔓延，形成由东南向西北递增的态势。结合建设用地开发强度空间分布来看，回归系数绝对值的高、低区域分别对应建设用地开发强度的高、低区域，

![](images/b01059f855f857065765d88c6af49c4cf0b33e55eb72ba6f9d4c0a6925f963f9.jpg)  
Fig.9Spatial distributionof regressioncoeficientoftheproportionof fiscal expenditure to GDPfrom2Oo0 to 2015   
（4）人均耕地面积2000—2010年人均耕地面积回归系数绝对值  
图102000—2015年人均耕地面积回归系数空间分布  
Fig.10Spatial distribution of regression coeficient of per capita cultivated land from 2OoO to 2015

# 干吴区地理

体现了人均耕地面积与建设用地开发在一定程度上的对立性，建设用地开发高强度区受耕地资源约束更显著，人均耕地面积减少在迫使建设用地开发强度不断提升。

# （5）地形条件

从各时期回归系数分布来看(图11)，2000年低值区集中在榆林南部和延安北部，高值区集中在榆林北部；2005年的分布格局类似；2010年次高值区显著减少，低值区由陕北地区转移至宝鸡市、汉中市；2015年高值区显著增加，集中分布在商洛和安康部分县域，低值区回归至陕北地区。总体来看，2000—2015年回归系数呈现从西北向东南递增的态势。结合建设用地开发强度空间分布发现，回归系数绝对值小的地区对应陕南建设用地开发高强度区，回归系数绝对值大的地区对应陕北高强度区，说明地形条件对陕北建设用地开发强度的影响大于陕南。原因在于陕南秦巴山地以生态保护为主，开发受到限制，且坡度较高的山地也难以开发建设，而陕北黄土高原地区社会经济活动活跃，但受地形条件影响显著，建设用地多集中在山地沟道等相对平坦地区。

# 4结论

（1）2000—2015年陕西省建设用地开发强度呈现总体增长态势，但内部空间分异显著。建设用地开发高强度区分布在西安市主城区；榆林市清涧县、子洲县、佳县、吴起县;延安市子长县、延长县、志丹县;安康市旬阳县、汉阴县、白河县、紫阳县。低强度区主要分布在榆林市北部、延安市南部以及咸阳市、宝鸡市、铜川市、渭南市、汉中市等所辖部分县域。

（2）陕西省建设用地开发强度呈现出明显的空间集聚状态，热点区稳定分布在西安市辖区及周边区县，冷点区分布在延安南部、咸阳、铜川、渭南和汉中等部分区域。2000—2010年冷点区和次热点区均有所增加，县域建设用地开发强度的高、低值集聚均呈现增强态势，区域开发的不均衡特征显著;2015年县域建设用地开发强度进一步提升，同时区域开发不均衡现象有所减缓

（3）固定资产投资、居民消费水平、财政投入力度、耕地资源和地形条件对建设用地开发强度的影响具有时空异质性。地均固定资产投资对于陕南的促进作用大于陕北，人均消费品零售总额在空间上未形成明显规律，财政支出占GDP比重对于陕北的促进作用大于陕南，人均耕地面积与建设用地开发强度呈负相关，地形条件对陕北的限制作用大于陕南。

# 5讨论

以往关于建设用地开发强度的研究大多采用区域建设用地面积占区域总面积的比重来表示，这一计算方法只考虑了土地利用的功能和建设用地的规模，而忽视了建设用地作为人类生产活动承载空间的综合性及其利用效率与承载能力的差异。

![](images/67681d2f43e9c2aafe4ce9dcff4523ec3db30f9a8d7a0c371d788e6916512dcf.jpg)  
图112000—2015年地形条件回归系数空间分布  
Fig.11 Spatial distribution of regression coefficient of terrain condition from 2OoO to 2015

本文将建设用地开发强度视为区域土地利用程度及其人口承载强度、经济产出力度的综合指数，可实现从规模、效率和承载能力对建设用地开发强度进行综合评价。基于多时段的土地利用遥感监测数据，分析陕西省县域建设用地开发强度时空演化特征，不仅实现了区域建设用地开发强度的长时间序列评价，同时也是对国土空间开发的动态监测与人类活动强度格局识别的有效手段。基于OLS和GWR模型的影响因素空间异质性分析指出了人口、社会、经济、资源、环境等因素对于建设用地开发强度作用程度的空间差异，对深人探析不同区域建设用地开发强度的驱动和约束因子，制定具有针对性的国土空间开发策略，合理引导区域开发建设活动具有重要意义。

当前，全国各地正在大力开展国土空间规划编制工作，而资源环境承载力评价和国土空间开发适宜性评价是国土空间规划的基础。本文研究内容和结论对科学认知国土空间开发状态、开展“双评价”和国土空间规划以及优化国土空间开发格局具有一定参考意义。结合本文研究结果,未来陕西省建设用地管控可从如下两方面开展：(1)强化对高强度开发县域建设用地的管控，合理确定城市增长边界，严格控制新增建设用地数量，加大存量土地的利用和开发，避免开发强度扩大而导致资源环境承载力失衡。(2)对于开发强度较低的县域，加大固定资产投资及财政支出来实现人口及产业的集聚，通过产业扶持、人才引进政策推动中小城镇经济发展；与此同时，应避免盲目扩张，合理划定生态保护红线，在确保生态环境质量的前提下推进城镇化建设。

本文研究仍有待于进一步完善和深化。例如，地方政府的土地开发与管理政策往往对地区建设用地开发具有重要的影响，但这一指标难以直接量化，只能通过固定资产投资、财政支出等替代性指标进行表示，对此，作者在下一步研究中将进一步完善。

# 参考文献(References)

[1]吕晓,黄贤金.建设用地扩张的研究进展及展望[J].地理与地理 信息科学,2013(6):55-62.[LYU Xiao,HUANG Xianjin. Research progress and prospect of construction land expansion[J]. Geography and Geo-Information Science,2013,(6):55-62.]

[2]王宏亮,郝晋珉,高艺宁.基于AHP-TOPSIS模型的建设用地利 用强度评价及灰色关联分析:以内蒙古为例[J].北京师范大学 学报（自然科学版),2018,54(3): 277-283.[WANG Hongliang, HAO Jinmin, GAO Yiling.Evaluation and correlation analysis of construction land use intensity in Inner Mongolia by AHP-TOPS [J]. Journal of Beijing Normal University (Natural Science),2018,   
54(3): 277-283.] [3]刘冬荣,彭佳捷,吕焕哲,等.区域建设用地开发强度时空格局 分析——以湖南省为例[J].中国国土资源经济,2016,29(7):   
53-59.[LIU Dongrong,PENG Jiajie,LYU Huanzhe,et al. Analysis of spatio-temporal layout with regard to development intensity of regional land for construction purposes: Taking Hunan as an example[J]. Natural Resource Economics of China,2016,29(7): 53-   
59.] [4]HUANG X, HUANG X J,LIU M M,et al. Spatial-temporal dynam ics and driving forces of land development intensity in the western China from 2000 to 2015[J]. Chinese Geographical Science,2020,   
30(1): 16-29. [5]赵亚莉,刘友兆.城市土地开发强度差异及影响因素研究- 基于222个地级及以上城市面板数据[J].资源科学,2013,35 (2): 380-387. [ZHAOYali,LIU Youzhao.Diffdence andinfluencing factors of urban land development intensity across 222 cities in China[J]. Resources Science,2013,35(2): 380-387.] [6]张鹏,张栩嘉,刘勇,等.基于土地开发强度的长春市城市空间 效率分异研究[J].地理科学,2018,38(6):895-902.[ZHANG Peng,ZHANG Xujia,LIU Yong,et al. Diversity of urban spatial efficiency based on the land development intensity in Changchun City[J]. Scientia Geographica Sinica,2018,38(6): 895-902.] [7]王忠诚,李金莲.中心城区土地开发强度研究[J].江苏城市规 划,2008,(12): 17-21.[WANG Zhongcheng,LI Jinlian. Study on the intensity of land development inthe central city[J]. Jiangsu Urban Planning,2008,(12): 17-21.] [8]张苗,甘臣林,陈银蓉,等.中国城市建设用地开发强度的碳排 放效率分析与低碳优化[J].资源科学,2016,38(2):265-275. [ZHANG Miao,GAN Chenlin, CHEN Yinrong. Carbon emission efficiency and optimization of low carbon for construction land development intensity in China according to provincial panel data[J]. Resources Science, 2016,38(2): 265-275.] [9]XU Y,TANG H, WANG B,et al. Effects of land-use intensity on ecosystem services and human well-being: A case study in Huailai County，China[J].Environmental Earth Sciences,2016,75(5):   
416.1-416.11. [10]王昊宇.新疆建设用地开发强度与生态环境容量匹配度评价研 究[D].乌鲁木齐：新疆农业大学,2016.[WANG Haoyu. The study on evaluation of matching degree between construction land development strength and ecological environment capacity in Xinjiang[D]. Urumqi: Xinjiang Agricultural University,2016.] [11]VACKAR D, ORLITOVA E. Spatial relationship between human population density,land use intensity and biodiversity in the Czech Republic[J].Landscape Ecology,2012,27(9): 1279-1290.

# 干吴区地理

[12]MACCHI L, GRAU HR, ZELAYA PV, et al. Trade-offs between land use intensity and avian biodiversity in the dry Chaco of Argentina: A tale of two gradients[J]. Agriculture Ecosystems & Environment,2013,174(174): 11-20.   
[13] 刘艳军,刘静,何翠,等.中国区域开发强度与资源环境水平的 耦合关系演化[J].地理研究,2013,32(3):507-517.[LIU Yanjun,LIU Jing,HE Cui,etal.Evolution of the coupling relationship between regional development strength and resource environment level in China[J]. Geographical Research,2013,32(3): 507-517.]   
[14] 沈春竹,谭琦川,王丹阳,等.基于资源环境承载力与开发建设 适宜性的国土开发强度研究——以江苏省为例[J].长江流域 资源与环境,2019,28(6):1276-1286.[SHEN Chunzhu,TAN Qichuan, WANG Danyang, et al.Research on land development intensity based on carrying capacity of resources and environment and suitability of development and construction: Acase studyof Jiangsu[J. Resources and Environment in the Yangtze Basin,2019,28 (6): 1276-1286.]   
[15] 卫思夷,居祥,荀文会.区域国土开发强度与资源环境承载力时 空耦合关系研究——以沈阳经济区为例[J].中国土地科学, 2018,32(7): 58-65.[WEI Siyi,JU Xiang,XUN Wenhui. Spatialtemporal coupling relationship between land development intensity and carrying capacity of regional resources and environment: A case study in Shenyang economic region[J]. China Land Science, 2018, 32(7): 58-65.]   
[16]卞凤鸣,刘彦彤,赵玲.吉林省土地利用空间均衡度评价研究 [J].中国土地科学,2015,29(12):74-80.[BIAN Fengming,LIU Yantong, ZHAO Ling. The spatial balance degree evaluation on land use in Jilin Province[J]. China Land Science,2015,29(12): 74-80.]   
[17]王全喜,孙鹏举,刘学录,等.甘肃省土地利用空间协调度时空 分异及态势分析[J].干旱区地理,2020,43(1):271-279. [WANG Quanxi, SUN Pengju, LIU Xuelu,et, al. Spatial-temporal differentiation and situation of spatial coordinationdegree on land use in Gansu Province[J].Arid Land Geography,202O,43(1): 271- 279.]   
[18]张竞珂,陈逸,黄贤金.长江经济带土地开发均衡度及限度 评价研究[J].长江流域资源与环境,2017,26(12):1945-1953. [ZHANG Jingke, CHEN Yi, HUANG Xianjin. Assessment of the equilibrium degree and limitation degree of Yangtze River economic belt's land development[J]. Resources and Environment in the Yangtze Basin,2017,26(12): 1945-1953.]   
[19] 谭术魁,刘琦,李雅楠.中国土地利用空间均衡度时空特征分析 [J].中国土地科学,2017,31(11): 40-46.[TAN Shukui,LIU Qi, LI Yanan. Spatial-temporal characteristics of spatial balance degrees on land use in China[J]. China Land Science,2O17,31(11): 40-46.]   
[20] 刘艳军,于会胜,刘德刚,等.东北地区建设用地开发强度格局 演变的空间分异机制[J].地理学报,2018,73(5):818-831.[LIU Yanjun,YU Huisheng,LIU Degang,et al. Spatial differentiation mechanismsof tepaernevolutionofconstructionlanddevelopment intensity in northeast China[J].Acta Geographica Sinica,   
2018, 73(5): 818-831.] [21] 杨清可,段学军,李平星,等.江苏省土地开发度与利用效益的 空间特征及协调分析[J].地理科学,2017,37(11):1696-1704. [YANG Qingke,DUAN Xuejun,LIPingxing,etal.Thepatialpatternand coordination analysis between degree of land development and use benefit in Jiangsu[J]. Scientia Geographica Sinica,   
2017,37(11): 1696-1704.] [22] 陈逸,黄贤金,陈志刚,等.中国各省域建设用地开发空间均衡 度评价研究[J].地理科学,2012,32(12):1424-1429.[CHEN Yi, HUANG Xianjin, CHEN Zhigang,et al. Thespatial balance degree evaluation of construction land in China[J]. Scientia Geographica Sinica,2012,32(12): 1424-1429.] [23] 王晶,肖海峰.耕地生态安全视域下棉花生产布局优化问题研 究———以新疆为例[J].干旱区地理,2018,41(4):833-843. [WANG Jing,XIAO Haifeng.Optimization of the distribution of cotton production in Xinjiang under the view of cultivated land ecological security[J].Arid Land Geography,2018,41(4): 833-   
843.] [24] 金贵,邓祥征,陈冬冬,等.黄淮海平原农地流转空间分布与格 局特征[J].资源科学,2016,38(8):1515-1524.[JIN Gui,DENG Xiangzheng,CHEN Dongdong,et al. Trends and spatial patterns of land conversions in the north China Plain[J].Resources Science,2016,38(8): 1515-1524.] [25] 许紫峻,汪溪远,师庆东,等.基于空间统计理论的新疆各地州 经济林营养物质积累空间关系特征分析及应用[J].干旱区地 理,2017,40(6): 1227-1234.[XU Zijun, WANG Xiyuan,SHI Qingdong,et al.Analysis and application of spatial relationship of nutrient accumulation ineconomic forests in Xinjiang based on spatial statistical theory[J].Arid Land Geography,2017,40(6): 1227-   
1234.] [26] 王茜茜,申晓燕,徐建斌,等.环渤海地区客货运量及其影响因 子的空间相关性分析[J].经济地理,2018,38(2):133-139. [WANG Xixi,SHEN Xiaoyan,XU Jianbin,et al. Spatial correlation analysis of the influencing factors and the relationship between passenger volume and cargo volume in the Bohai Rim[J]. Economic Geography,2018,38(2): 133-139.] [27]曹小曙,徐建斌.中国省际边界区县域经济格局及影响因素的 空间异质性[J].地理学报,2018,73(6): 81-91.[CAO Xiaoshu, XU Jianbin.Spatial heterogeneity analysis of regional economic development and driving factors in China's provincial border counties[J]. Acta Geographica Sinica,2018,73(6): 81-91.] [28] 王宏亮.城镇化背景下建设用地利用强度研究[D].北京:中国 农业大学,2O17.[WANG Hongliang.Research on construction land use intensity in urbanization: A case study in Inner Mongolia [D]. Beijing: China Agricultural University,2017.]

# Pattern evolution and influencing factors of regional construction land development intensity: A case of Shaanxi Province

WANG Bo'，HUANG Xiao-jun1,2.34，LIU Meng-meng1   
(1CollegeofUbanndEnvironmentalSiences,NrthwestUnversityXi'an,ani,na;2aniKey   
LaboratoryofEarthSurfaceSystemandEnvironmentalCarryingCapacity,Xi'an70l27,haanxi，China;3ani Yellow River Research Institute,Xi'an710l27,Shaanxi,China;4Shaanxi Xi'an UrbanForest Ecosystem Research Station,Xi'an 710127,Shaanxi,China)

Abstract:The development intensityof regional construction land isan important index to revealthe levelof land use,the development of social economy,and the evolution of land spatial pattern.Monitoring and controllng the construction land development intensitycanoptimize the patern of land spatial development and realize regional sustainable development.Shaanxi Province is located in thenorthwest of China,which can be divided into three regions according to its natural geographical characteristics: Loess Plateau,Guanzhong Plain,and Qinling-Daba mountain area.In recent years,there are many problems in the development and utilization of land resources in Shaanxi Province,such as the disordered expansion and extensive utilization ofconstruction land,the idling of rural residential land,theoverload ofresources and environment in ecologically fragileareas,andtheserious soil erosion and environmental polltion caused by overdevelopment.Therefore,this paper scientifically evaluates pattern evolutionand influencing factors of construction land development intensity in counties of Shaanxi Provine.Atthe same time,it efectively discriminates the overdevelopment zone and underdevelopment zone inthe city.Both of them will have important practical significance for the orderly development and rational utilizationof regional construction land.First,based on the land use remote sensing monitoring dataand socio-economic statistical data, this paper selects the proportion of construction land (CLP)，population carrying capacity ( $P C S$ )，and economic development intensity (EDl) to calculate the construction land development intensity of counties in Shaanxi Provincefrom 2OOO to 2O15.A spatialautocorrelation method is then used to reveal its spatial pattrnand evolution characteristics.Finally,OLSand GWRmodelsare used to identifythe influencingfactors of the pattern evolutionof construction land development intensity.The results are shown as follows: (1)From 20oO to 2015,the construction landdevelopment intensity in Shaanxi Province showedan overall growth trend,but the internal space was significantlydifferent.High-intensityareas were concentrated inthecountiesof Yulin,Yan'an,Xi'an,and Ankang, whilelow-intensityareasareconcentrated inthecountiesofXianyang,Baoji,Tongchuan,Shangluo,Weinan,and Hanzhong.(2)The construction land development intensity shows obvious spatial agglomeration state.Hot spots are stably distributed in Xi’anand surounding counties,while cold spotsare distributed in southern Yan’an, Xianyang,Tongchuan, Weinan,and Hanzhong.The imbalance of regional development is becoming more and more prominent as the construction land development intensity is gradually increasing.(3） Fixed asset investment, household consumption level,financial input,cultivated land resources and topographical conditions arethe main factors affecting the spatial diffrentiationofconstructionland developmentintensity in ShaanxiProvince.However, thedegreeof impact varies significantlyin diffrent counties，and theimpact of individual factors exhibits instability.Inadition,the innovationof this paper lies in the following:(1）With the helpofremote sensing monitoring data of land use to carry out the long-term evaluation of construction land development intensity of counties,we makeup for the deficiency of meso scale research;(2)From the perspective of factors affecting development intensity, OLS and GWR models are used to analyze the spatial heterogeneity of influencing factors, which enriches the research method.

Key Words: construction land; development intensity; pattrn; influencing factors; Shaanxi Province