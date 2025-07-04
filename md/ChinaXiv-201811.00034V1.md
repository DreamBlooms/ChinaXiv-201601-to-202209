# 疏勒河流域土壤含水率反演

郭晓娟'，周妍妍'，郭建军²，陈冠光'，岳东霞'（1．兰州大学资源环境学院,甘肃 兰州730000;2．中国科学院西北生态环境资源研究院,中国科学院沙漠与沙漠化重点实验室,甘肃 兰州730000)

摘要：土壤含水率是影响干旱区植物生长的重要因素,获取区域尺度土壤含水率数据,能够为干旱半干旱区生态恢复和脆弱生态系统保护提供科学依据。结合MODIS 地表温度和反射率数据及全球陆面数据同化系统（GLDAS)土壤含水率数据,利用表观热惯量法和统计降尺度方法反演疏勒河流域土壤含水率,研究其时空变化及其与植被的相关性,得到以下结论;2016 年整个疏勒河流域年均土壤含水率偏低,且季节变化显著,其均值、离散程度存在7月 $> 1 0$ 月 $> 4$ 月 $> 1 2$ 月的趋势;流域东部土壤含水率整体高于西部;流域土壤含水率空间分布的季节变化显著，其变异系数的空间分布与年均土壤含水率相似;土壤含水率与归一化植被指数 NDVI正相关,但不同区域两者相关程度不同,灌区土壤含水率与植被的相关性最高。

关键词：土壤含水率；反演模型；GLDAS；表观热惯量；NDVI；疏勒河流域

土壤水分是限制植物生长的重要因素，特别是在干旱区[1],对生态系统平衡有着重要的影响。在大尺度区域上进行土壤含水率反演，宏观动态地监测土壤含水率，对于科学把握区域水文、气象特征和发展高效农业等诸多领域都有十分重要的意义[2] C遥感反演大尺度区域土壤含水率比基于单点测量的传统测量方法具有覆盖范围大、更快、成本更低的优势，国内外对其进行了大量研究，其中主要有基于表观热惯量[3]、温度与植被指数[4-6、土壤高光谱特征[7、微波[8]等的反演方法，且不同方法有不同的适用范围。其中，表观热惯量法较适用于裸土或低植被覆盖区域,且分辨率较高,数据获取方便[9-10)是干旱区土壤含水率反演的重要方法。然而，由于遥感只能获取近地表信息，无法穿透深层土壤，因此,仅能反演表层土壤含水率()

表观热惯量法进行土壤含水率反演，需要建立其与实测土壤含水率之间的关系。然而在西北干旱区，地广人稀，大范围土壤含水率测量与监测并不现实。国内外很多学者尝试采用降尺度的方法，通过各种低分辨率的土壤含水率数据集（如先进微波扫描辐射计(AMSR-E)数据、全球陆面数据同化系统(GLDAS)数据等)获取高分辨率土壤含水率，其中统计降尺度方法应用较多[12-13]。很多学者认为GLDAS数据的适用性较好，数据获取年限较广，能够反映土壤含水率的时空变化[14-15] 。

研究表明，干旱半干旱区土壤含水率的时空分布对植物生长具有深刻影响[16]。很多学者对大尺度区域土壤含水率和植被的相关性展开了研究[17-19],并发现浅层土壤含水率与植被具有很强的相关性。尽管如此，但大多数研究主要关注了两者区域全局的相关性，而对高分辨率土壤含水率与植被的局部相关性尚缺乏深入研究。

疏勒河流域系我国西北干旱区内陆河流域，是典型的干旱荒漠气候,降水少，土壤含水率低，严重限制了流域内植物的生长。然而，目前对疏勒河流域土壤含水率遥感反演及其与植被相关性的研究较少。因此，本文利用MODIS和GLDAS数据，以表观热惯量法结合统计降尺度反演疏勒河流域2016年4个月 $0 \sim 1 0 \ \mathrm { c m }$ 空间分辨率为 $1 ~ \mathrm { k m }$ 的土壤含水率，并分析7月土壤含水率与平均NDVI全局和局部的相关性，以期深入认识该区域水资源分布情况，了解干旱区内陆河流域植物生长状态，并为流域水资源合理配置和生态环境保护提供科学依据。

# 1研究区概况及研究方法

# 1.1 研究区概况

疏勒河流域地处河西走廊最西端，地理位置$9 3 ^ { \circ } 2 2 ^ { \prime } \sim 9 8 ^ { \circ } 5 9 ^ { \prime } \mathrm { E }$ $3 8 ^ { \circ } 0 1 ^ { \prime } \sim 4 2 ^ { \circ } 4 7 ^ { \prime } \mathrm { N } \cdot$ （图1），是甘肃省三大内陆河之一，流域面积约 $1 . 2 5 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ ，包括敦煌市、玉门市、肃北县、瓜州县、阿克塞县及青海省天峻县和德令哈的一部分。该流域东西分别与巴丹吉林沙漠和库姆塔格沙漠相连，北部是马鬃山低山、丘陵、戈壁，南部为祁连山，是流域的上游区域。疏勒河流域是典型的干旱荒漠气候,多年平均降水量极低,而蒸发量大[20]，主要以雪冰融水与山区降水补给为主[21]。流域上游山势险峻,存在典型的大陆性冰川和大面积多年冻土；而中、下游地势平坦，绿洲与荒漠并存[22],存在土地沙漠化、盐碱化等生态问题[20]。主要土地利用类型包括裸岩、稀疏草地、草地、草甸、冰川、落叶阔叶灌木、裸土、沼泽和河流,其中裸岩和稀疏草地占30%以上[23]

![](images/118106b002ea06e5ac52872f9390ddbc01998219637f80db722c0fac337ba89a.jpg)  
图1研究区示意图  
Fig.1Sketch map of the Shule River Basin

# 1. 2 数据来源

本文所利用的数据主要是由美国国家航空航天局（https://ladsweb.nascom.nasa.gov）提供的 MO-DIS全球数据产品MOD09A1（全球 $5 0 0 \mathrm { ~ m ~ }$ 地表反射率8d合成)和MOD11A2（全球 $1 ~ \mathrm { k m }$ 地表温度/发射率8d合成），以及GLDAS_NOAH025_M的 $0 \sim$ $1 0 \ \mathrm { c m }$ 的土壤含水率数据。本文拟反演疏勒河流域2016年4个季节的代表月份(1、4、7、10月）的土壤含水率，然而由于1月MODIS数据质量较差，缺失值过多，故选择12月进行研究。在4个月中选取了白天、午夜天气都比较晴朗,MODIS 数据质量较好的8d合成影像（儒略日为97、201、281、345d），行列号为 $\mathrm { h } 2 5 \mathrm { v } 0 4$ 和 $\mathtt { h 2 5 v 0 5 }$ 。GLDAS_NOAH025_M包含4层土壤含水率数据，空间分辨率为 $0 . 2 5 ^ { \circ }$ ，时间分辨率1个月,单位为 $\mathbf { k g } \cdot \mathbf { m } ^ { - 2 }$ ,也可以认为是 $\mathbf { m } \mathbf { m }$ ，指一定厚度土层中水分的厚度。

# 1.3表观热惯量法

本文选用较适合裸露和低植被覆盖区域的表观热惯量（apparentthermalinertia，ATI)法进行反演。该方法最初由Price[3]提出,计算简单,数据易获取,主要原理是依据ATI与土壤含水率之间的正相关关系。计算公式如下[9]：

$$
\mathrm { A T I } = { \frac { \left( 1 - A \right) } { \Delta T } }
$$

式中：ATI为表观热惯量,单位： $\mathrm { ~ J ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 } \cdot \mathrm { ~ s ~ } ^ { - 1 / 2 }$ ：$\mathbf { K } ^ { - 1 }$ $A$ 为全(宽)波段反照率; $\Delta T$ 为地表昼夜温差,单位:K。其中, $A$ 根据 Liang(24]针对 MODIS 数据的宽波段反照率公式计算。 $\Delta T$ 根据任皓晨9和陈国茜等[25]的温差校正方法,将 MODIS 地表温度计算的过境时间温差换算为地表昼夜温差。虽然表观热惯量法对 NDVI大于0.35 区域的适用性较低[26]，但综合考虑疏勒河流域属干旱区，裸地以及低植被覆盖区分布广泛，高植被覆盖区较少，研究区7月仍然有 $9 7 . 3 4 \%$ 以上的区域NDVI小于0.35，该方法对整个研究区绝大部分区域的适用性较好，因此采用此方法进行土壤含水率反演。

# 1.4 降尺度方法

GLDAS是一个全球高分辨率陆面同化系统，相比其他模拟产品,其生产的驱动数据更准确[14],模拟结果更合理[27]。该数据在国内外得到广泛的应用，并证明其在一定程度上可以代表实际土壤含水率[13],因此本文利用GLDAS 土壤含水率数据代表疏勒河流域实际土壤含水率。但该数据分辨率太低，无法表现出流域内土壤含水率空间分布的细节情况，不能满足研究需要，因此利用统计降尺度方法将其空间分辨率提高至 $1 ~ \mathrm { k m }$ 。将GLDAS数据裁剪和投影变换后，再重采样至 $2 5 \ \mathrm { k m }$ ，并利用ArcGIS10.3软件中的聚合工具，对应计算每个GLDAS 栅格范围内ATI的平均值，再用GLDAS栅格的中心点对应提取 $2 5 ~ \mathrm { k m }$ 栅格的ATI和GLDAS土壤含水率;为减小土壤含水率的波动，在Excel中，以0.O01ATI步长统计区间内GLDAS土壤含水率的平均值[10,13],并将ATI值和GLDAS 土壤含水率进行拟合，最后利用该拟合关系以及 $1 ~ \mathrm { k m }$ 分辨率的ATI数据反演整个流域的土壤含水率。

# 1.5 降尺度结果精度评价

将反演后的土壤含水率与原GLDAS土壤含水率进行比较分析，主要采用的指标为残差、平均相对误差和均方根误差。

平均相对误差：指GLDAS数据降尺度结果偏离原始数据的大小。

均方根误差：指GLDAS数据降尺度结果与原始数据之间的偏差，其值越小，表示降尺度结果和原始数据之间越接近。

# 1.6 地理加权回归

由于土壤含水率和NDVI都具有显著的空间异质性，两者在空间上并不平稳，而假设数据具有平稳性的全局模型可能无法捕捉两者之间的真实关系，从而使结果的可靠性受到质疑[28]，因此,本文在ArcGIS10.3软件中使用地理加权回归工具对两者的局部相关性进行分析,该方法由Brunsdon 等[29]提出，计算简单，而且能够获取空间上任意待估点的估计系数。其 $R ^ { 2 }$ 和系数绝对值的大小可以代表土壤含水率与NDVI相关关系的强弱，系数正负可以表明两者相关性的正负。

# 2 结果与讨论

# 2.1 反演模型及精度验证

根据表观热惯量法和降尺度的方法建立反演模型，拟合关系见图2。可见，4个月拟合关系的 $R ^ { 2 }$ 均在0.5以上，可以用于反演整个流域的土壤含水率。4个月土壤含水率反演的残差见图3，平均相对误差和均方根误差见表1。

![](images/26210b6d8ed1dc88b4ab5e2d180b23720a7bb01ac1764e2cbfd7faec38ffc3c4.jpg)  
图2ATI和GLDAS 数据拟合关系 Fig.2Fitting relationship between ATI and GLDAS data

表1降尺度数据检验  
Tab.1 Downscaling data test   

<html><body><table><tr><td>月份</td><td>残差>5mm 的栅格 百分比/%</td><td>平均相对 误差/%</td><td>均方根误差 (RMSE)/%</td></tr><tr><td>4</td><td>2.5</td><td>12.98</td><td>2.409</td></tr><tr><td>7</td><td>9</td><td>15.34</td><td>3.081</td></tr><tr><td>10</td><td>6.5</td><td>12.27</td><td>3.161</td></tr><tr><td>12</td><td>1</td><td>10.34</td><td>2.276</td></tr></table></body></html>

从残差图(图3)和残差 $> 5 \ \mathrm { m m }$ 的栅格百分比(表1)看，残差主要集中于 $\pm 5 \ \mathrm { m m }$ 以内,其栅格数均 $> 9 0 \%$ ,说明超出 $5 ~ \mathrm { m m }$ 范围的栅格较少,且基本集中于流域上游雪冰覆盖的区域。根据吴盼等[13]的研究，认为此结果是一个可以接受的范围，反演精度良好，且平均相对误差均在 $20 \%$ 以下，与其他研究者的结论相一致[30-31],均方根误差也在 $2 \sim 4 ~ \mathrm { m m }$ 之间，说明反演值与GLDAS原始土壤含水率虽有偏差，但整体相吻合，可以较好地反映地表土壤含水率。整体来看，雪冰覆盖和水体区域反演误差较大，可能是由于表观热惯量法对雪冰和水体的适用性较差造成的。

![](images/fb68a3e7ebb1c93e86fb36fabf75b3f242709dba1fa866f1ab6fff218d75374d.jpg)  
Fig.3The residual graph of the inverse value and the original GLDAS data

# 2.2疏勒河流域土壤含水率空间分布

本文选定的4个月分别代表疏勒河流域年内4个季节的土壤含水率，因此认为其平均值可以作为年均土壤含水率(图4)。流域年均土壤含水率主要集中在 $1 0 \sim 1 8 ~ \mathrm { \ m m }$ ,其平均值为 $1 4 . 1 1 \ \mathrm { \ m m }$ ,其中$1 5 ~ \mathrm { m m }$ 及以下的区域占 $8 0 . 2 \%$ 。整体来看,流域东部土壤含水率高于西部。其中，疏勒河干流上游区域、当金山附近、灌区和马鬃山附近的部分地区土壤含水率最高，多在 $1 7 \sim 2 5 \ \mathrm { m m }$ ;而党河上游、敦煌阿克塞一带的沙漠戈壁以及瓜州北部的戈壁土壤含水率较低，特别是党河上游的部分地区土壤含水率在$1 1 \sim 1 3 ~ \mathrm { m m }$ 。总体而言，疏勒河流域土壤含水率表现出较大的空间异质性。

# 2.3疏勒河流域土壤含水率时间变化

箱线图（图5)展示了疏勒河流域2016年不同月土壤含水率的数值分布。整体而言，土壤含水率均值存在7月 $> 1 0$ 月 $> 4$ 月 $> 1 2$ 月的趋势( $T$ 检验$P < 0 . 0 1$ );箱体长度也存在同样的趋势，说明7月土壤含水率的分布相对其他季节来说较为离散、异质性高，其次为10月，12月土壤含水率的分布最为集中、异质性低。而年均土壤含水率均值介于4月与10月之间。整体来看，疏勒河流域土壤含水率偏低，这与此区域的气候条件密切相关。疏勒河流域降雨少,蒸发大,中下游地表土壤多石质土、棕漠土、风沙土，保水性差，这就使得土壤水分不能有效储存，从而导致土壤含水率较低。

![](images/518d7883b9ca77ac23c8bb00973604f02272181754d20dbcba8a1faeb592f1e9.jpg)  
图3反演值与原GLDAS数据的残差  
图42016 年疏勒河流域年均土壤含水率分布 Fig.4Distribution of annual average soil moisture content in the Shule River Basin in 2016

![](images/4ba2b5df8d6d0e5bab9cd665dbb9a5f595d54dfde7ebd0df72169a8a18cd162b.jpg)  
图5疏勒河流域土壤含水率箱线图 Fig.5Box plots of soil moisture content in the Shule River Basin

图6显示疏勒河流域2016年4个月的土壤含水率空间分布。在敦煌阿克塞附近沙漠戈壁、党河上游部分地区全年土壤含水率均较低，在马鬃山及上游地区冰川附近每个月都有较高的土壤含水率。

而流域内土壤含水率季节变化也十分明显。疏勒河干流上游山区和三大灌区的年内变化最为明显，这些区域在植物生长旺季(7月）的土壤含水率最高，明显区别于附近地区；在4月、10月土壤含水率稍降，与附近地区差异不如7月明显;12月灌区土壤含水率处于全年最低水平。全流域7月土壤含水率的空间异质性最大，4月、10月次之，12月的空间异质性最小。流域内7月仅有 $3 8 . 9 4 \%$ 的区域土壤含水率处于 $1 5 ~ \mathrm { m m }$ 以下，而12月 $9 8 . 7 8 \%$ 的区域都处于 $1 5 ~ \mathrm { m m }$ 以下，只有零星区域高于 $1 5 \ \mathrm { m m }$ ，两者间的差异显著。

本文逐栅格计算疏勒河流域4个月土壤含水率的变异系数(图7）。变异系数越大，说明土壤含水率变化越剧烈，变异系数越小，说明土壤含水率越稳定，且通常认为变异系数 $\leqslant 0 . 1$ 为弱变异性， $0 . 1 <$ 变异系数 $\leqslant 1$ 为中等变异,变异系数 $> 1$ 为强变异性[32]。可见,全流域变异系数介于 $0 \sim 0 . 9 6 9$ 之间，土壤含水率波动幅度具有明显的区域差异,且与年均土壤含水率的空间分布格局相似，全流域土壤含水率没有强变异。流域内土壤含水率变异最大的区域位于玉门和瓜州灌区以及马鬃山附近，敦煌灌区和疏勒河干流上游大部分地区变异性稍减弱，但均属于中等变异。而在敦煌、阿克塞及党河上游大部分地区其土壤含水率最为稳定，变异性最低，属于弱变异性。土壤含水率中等变异的区域占流域总面积的 $6 1 . 4 4 \%$ ，流域土壤含水率的季节变化明显。

![](images/213f8bf686307141ba1dd09336ecf85dd814c748c7f51e446f5308b09eba6813.jpg)  
图62016年疏勒河流域土壤含水率分布  
Fig.6Distribution of soil moisture content in the Shule River Basin in 2016

![](images/a67aef701b4188348640ea093e99d33dd1361bafc17909bc14c71848610a5fdb.jpg)  
图7疏勒河流域土壤含水率变异系数 Fig.7Variation coefficient of soil moisture content in the Shule River Basin

降水、气温、蒸发以及人类活动的季节性变化和空间分布的不均匀，导致流域土壤含水率在时间和空间上具有显著的差异

在干旱区，降水强烈影响着土壤含水率的动态变化[33]。疏勒河流域降水量由东南向西北递减,山区比平原区降水量多[34],因此,流域上游山区大部分地区的土壤含水率较高，而中下游大部分地区土壤含水率相对较低，但灌区受人类活动影响，土壤含水率较高。流域内春季降水少而稳定，汛期相对较多,冬季甚少的季节性变化特征[34],加之气温变化导致的融雪量季节变化，使得流域内12月份水源补给过少，土壤含水率处于全年最低水平，4月、10月较高，而7月降水和融雪都大大增加,使得土壤含水率较高，尤其是在上游地区增加显著。党河上游$3 ~ 2 0 0 \sim 4 ~ 0 0 0 ~ \mathrm { m }$ 高程的区域，顶部无冰雪覆盖，气温也相对较低，多荒漠植被，且植被稀疏，基本为裸土，

土壤含水率较低。

从上游到中、下游，气温逐渐升高，蒸散发加强，土壤含水率逐渐下降。尤其是在敦煌阿克塞一带，多荒漠戈壁，且与库姆塔格沙漠相连，土壤多沙质土，植被稀疏，下垫面裸露，且降水量低，温度较高[35]，导致蒸发强烈,使得此区域土壤含水率最低。

人类活动对疏勒河流域土壤含水率的时空分布有巨大的影响。尤其是在敦煌、瓜州、玉门三大灌区，由于人类活动密集，农业灌溉频繁，人工林地较多，使得该区域土壤含水率明显高于附近地区，且年内变化明显。4月由于春种开始，农田灌溉增加，使得三大灌区土壤含水率也明显增加。7月是作物生长关键期，农田灌溉量大大增加，使得灌区土壤含水率明显高于附近区域。10月作物收割后，人工灌溉有所下降，因此灌区土壤含水率下降。12月植被处于非生长期，灌区的土壤含水率与周围地区相比，差异减小。

# 2.4土壤含水率与植被的相关性分析

如表2所示，土壤含水率和 NDVI存在全局正相关关系（ $\cdot P < 0 . 0 1 \cdot$ ，而土壤含水率与 $\mathrm { \Delta N D V I } > 0$ 区域( $\mathrm { \Delta N D V I } \leqslant 0$ 的水体、积雪、岩石或裸土等无植被覆盖区域剔除)的相关性有所增强，进一步说明土壤含水率与植被的正相关关系。从全局的Pearson相关系数来看，土壤含水率与植被有显著的正相关性，土壤含水率越高的地方，植物生长越好，反之亦然。由其线性回归关系式可以发现，在 $0 \sim 1 0 \ \mathrm { c m }$ 土层,当土壤含水率低于 $8 . 1 7 ~ \mathrm { m m }$ 时， $\mathrm { \Delta N D V I } < 0$ ,在疏勒河流域，当土壤含水率低于 $8 . 1 7 \ \mathrm { m m }$ 时，流域内的植物可能无法生长[19] O

利用地理加权回归方法对两者的局部相关性做进一步分析。地理加权回归显示其 $R ^ { 2 }$ 达到0.837，说明土壤含水率与NDVI具有极大的相关性。相比全局普通最小二乘法得到的结果，其相关性和残差平方和均得到极大提升（表2），说明地理加权回归模型的效果更优于全局普通最小二乘法。

将地理加权回归结果中的局部 $R ^ { 2 }$ 栅格化。结

表2土壤含水率和NDVI回归参数  
Tab.2Regression parameters of NDVI and soil moisture content   

<html><body><table><tr><td></td><td>Pearson 相关系数</td><td>R²</td><td>残差平方和</td><td>回归关系式</td></tr><tr><td>全局回归</td><td>0.484</td><td>0.235</td><td>671. 494</td><td>1</td></tr><tr><td>NDVI>0部分的全局回归</td><td>0.522</td><td>0.273</td><td>630.765</td><td>NDVI=0.012×土壤含水率-0.098</td></tr><tr><td>地理加权回归</td><td></td><td>0.837</td><td>125.410 812</td><td>一</td></tr></table></body></html>

![](images/9cac2a7d8e48efe10675eade31413c9288134572c9bdc7cd78be7c7d17cabef8.jpg)  
郭晓娟等：疏勒河流域土壤含水率反演  
图8土壤含水率和NDVI地理加权回归局部 $R ^ { 2 }$ 和回归系数

注： $R ^ { 2 }$ 在 $0 \sim 0 . 1$ 之间可以认为两者基本没有相关性,在0.1\~0.3之间具有弱相关关系，在 $0 . 3 \sim 0 . 5$ 之间具有中等相关关系，在 $0 . 5 \sim 0 . 8$ 之间具有强相关关系，0.8以上具有极强的相关关系[36]。

Fig.8Local $\boldsymbol { \mathrm { R } } ^ { 2 }$ and regression coefficient of geographically weighted regression of soil moisture content and NDVI果如图8a所示，在玉门、瓜州、敦煌三大灌区，土壤含水率和NDVI强相关，部分地区甚至极强相关；在党河上游部分区域，土壤含水率和NDVI中等相关，部分区域强相关；在马鬃山附近，土壤含水率和NDVI达中等相关以上;疏勒河干流上游大部分区域土壤含水率和NDVI相关性极弱，这主要是由于此区域位于整个流域的高海拔区域,7月气温升高，雪冰融水增加，降水也同样增加，使得其水热条件发生复杂变化，共同影响植物的生长，因此此处两者相关性弱。

图8b为土壤含水率和NDVI地理加权回归系数栅格化图。在流域中下游的灌区系数为正值，基本在0.03以上，在党河上游部分地区系数为正，但相对灌区较小，在 $0 . 0 1 \sim 0 . 0 3$ ，说明在这些区域较高的土壤含水率使得NDVI较高。主要是由于灌区人类活动密集，对农田和人工林的灌溉，促进了植物生长，从而使得土壤含水率大于周边区域,NDVI也高于流域内其他区域。

通过统计发现，在系数为负的区域， $7 7 . 8 6 \%$ 的区域 $R ^ { 2 } < 0 . 1$ ,说明这些区域中，土壤含水率与植被的空间相关性并不是很好，在分析时可以忽略。而在疏勒河干流上游、敦煌阿克塞附近沙漠、瓜州玉门灌区北部和马鬃山附近部分地区的土壤含水率与NDVI的系数为负，但 $R ^ { 2 } > 0 . 1$ 。这可能是由于本文分析的是浅层土壤含水率与植被的关系，而部分区域的植被主要依靠深层土壤水分[37],或者其他环境因子(如降水、气温等)对植被的影响更大，所以出现了浅层土壤含水率低，而植被相对较好的情况；也可能有的区域水分亏缺较严重，植物生长耗水不能够被降水及时补充，长势越好的区域其土壤含水率也就越低[37]；而流域北部可能由于人类活动较密集（如工矿开采等），对植被的破坏较大，使得浅层土壤含水率高而NDVI过低。

# 3结论

2016 年整个疏勒河流域年均土壤含水率集中在 $1 0 \sim 1 8 ~ \mathrm { m m }$ ,其平均值为 $1 4 . 1 1 \ \mathrm { m m }$ ,整体偏低；流域2016年4个月的土壤含水率变化显著，其均值、离散程度存在7月 $> 1 0$ 月 $> 4$ 月 $> 1 2$ 月的趋势；流域东部土壤含水率整体上高于西部,其中疏勒河上游、三大灌区以及马鬃山附近土壤含水率最高，党河上游和敦煌阿克塞一带的沙漠戈壁土壤含水率最低；流域土壤含水率空间分布格局季节变化显著，其变异系数的空间分布与年均土壤含水率相似;浅层土壤含水率与 NDVI存在正相关性,但不同区域土壤含水率与NDVI的相关程度不同，灌区两者相关性最高，疏勒河干流上游两者相关性不显著，党河上游两者存在强相关。

由于研究区内没有大量的实测数据以供检验，本文仅以GLDAS土壤含水率代替实测值进行反演;且由于MODIS数据质量问题，本文采用的是1个月中1期8d合成影像与月尺度的GLDAS数据进行降尺度，存在一定误差。流域内土壤含水平相值恢怕大性区域左并时驱动四系处有付近步的研究。

参考文献（References）:   
[1］马晓东,李卫红,朱成刚,等.塔里木河下游土壤水分与植被时 空变化特征[J].生态学报,2010,30（15）:4035-4045.[Ma Xiaodong,Li Weihong,Zhu Chenggang,etal.Spatio-tempora variation in soil moisture and vegetation along the lower reaches of Tarim River，China[J].Acta Ecologica Sinica,2010,30（15）： 4 035 -4 045.]   
[2]裴浩,范一大，乌日娜.利用气象卫星遥感监测土壤含水量 [J].干旱区资源与环境,1999,13（1）:73－76.[Pei Hao,Fan Yida,Wu Rina.Sense remotely soil moisture through meteorological satelite[J]. Journal of Arid Land Resourcesand Environment, 1999,13(1) :73 - 76. ]   
[3]Price JC.On the analysis of thermal infrared imagery:The limited utility of apparent inertia[J].Remote Sensing of Environment, 1985,18(1) :59 - 73.   
[4]Sandholt I,Rasmussen K,Andersen J.A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J]. Remote Sensing of Environment,2002, 79(2) :213 -224.   
[5]林巧,王鹏新,张树誉,等.不同时间尺度条件植被温度指数干 旱监测方法的适用性分析[J].干旱区研究,2016,33（1）： 186 -192.[Lin Qiao,Wang Pengxin,Zhang Shuyu,et al.Applicability of vegetation temperature index fordrought monitoring at the time scales[J].Arid Zone Research,2016,33(1) :186-192.]   
[6]Jackson R D,Idso S B. Canopy temperature as a crop water stress indicator[J].Water Resource Research,1981,17（4）:1 133 - 1138.   
[7］姚艳敏,魏娜,唐鹏钦,等.黑土土壤水分高光谱特征及反演模 型[J].农业工程学报，2011,27（8）:95-100.[Yao Yanmin, Wei Na,Tang Pengqin,etal.Typer-spectral characteristicsand modeling of black soil moisture content[J].Transactions of the Chinese Society of Agricultural Engineering,2011,27（8）:95- 100.]   
[8]魏宝成,银山,贾旭,等.蒙古高原植物生长期土壤水分时空变 化特征［J].干旱区研究,2016,33（3）：467－475.［Wei Baocheng,Yin Shan,Jia Xu,et al.Spatiotemporal variation of soil moisture content in the Mongolia Plateau in plant growing season [J].Arid Zone Research,2016,33(3）:467 -475.]   
[9]任皓晨.石羊河流域土壤含水量的遥感反演及在旱情监测中 的应用〔D].兰州：西北师范大学,2009.［Ren Haochen.The Study on Retrieving Soil Moisture by Remote Sensing in Shiyang RiverBasin and the Application of Soil Moisture in Drought Monitoring[D].Lanzhou:Northwest Normal University,2009.]   
[10］王凯霖,金晓媚,郭任宏,等.柴达木盆地土壤湿度的遥感反演 及对蒸散发的影响[J].现代地质,2016,30（4）：834－841. [Wang Kailin,Jin Xiaomei,Guo Renhong,etal.Soil moisture retrieval from remote sensing and its impact on evapotranspiration in Qaidam Basin[J].Geoscience,2016,30(4）:834 -841.]   
[11]Gao X,Zhao X,Brocca L,et al. Upscaling of soil moisture content from surface to profile:Multi-station testing of observation operators [J].Hydrology & Earth System Sciences Discussions,2O17,617： 1-28.   
[12]曹永攀,晋锐,韩旭军,等.基于 MODIS 和AEMSR-E 遥感数据 的土壤水分降尺度研究[J].遥感技术与应用,2011,26（5）： 590 -597.[Cao Yongpan,Jin Rui,Han Xujun,et al.A downscaling method for AMSR-Esoil moisture using MODIS derived dryness index[J].Remote Sensing Technology and Application, 2011,26(5):590 -597.]   
[13］吴盼,冯雨晴,梁四海,等.基于GLDAS 与TVDI降尺度反演土 壤含水量[J].北京师范大学学报（自然科学版）,2016,52 (3）:265-27O.[Wu Pan,Feng Yuqing,Liang Sihai,et al. Estimating soil moisture-based on TVDI and GLDAS using down scaling method[J].Journal of Beijing Normal University（Natural Science）,2016,52(3) :265 -270.]   
[14]Rodell M,HouserPR,Jambor U,et al.The global land data assimilation system[J].Bulletin of the American Meteorological Society, 2004,85(3) :381 -394.   
[15]程善俊,黄建平,季明霞,等.中国华北暖季土壤湿度的变化特 征[J].干旱气象,2015,33（5）:723－731.[Cheng Shanjun, Huang Jianping,Ji Mingxia,etal.Variation feature of soil moisture in warm seasonover North China[J].Journalof Arid Meteorology, 2015,33(5) 723 -731. ]   
[16]Rodriguez-Iturbe I. Ecohydrology:A hydrologic perspective of climate-soil-vegetation dynamics[J].Water Resources Research, 2000,36(1) :3 -9.   
[17］陈云浩,李晓兵,李霞,等.不同地表覆盖条件下区域水分盈亏 的遥感分析—以中国北方为例[J].地球科学进展,2002,17 (2）:283-288.[Chen Yunhao,Li Xiaobing,Li Xia,et al.Remote sensing model for monitoring regional water stress concerning landcover condition:A case study over North China[J].Advance in Earth Sciences,2002,17(2):283 -288.]   
[18］赵琛.黑河上游土壤水分时空变异性及其估算研究[D].兰 州：兰州大学,2015.[Zhao Chen.The Spatial-Temporal Variability of Soil Moisture in the Upstream of the Heihe River Watershed, China[D].Lanzhou:Lanzhou University,2015.]   
[19］白晓,王忠富,杨礼箫.黑河上游土壤水分与遥感环境因子相 关性分析[J].遥感信息,2016,31(6）:121-127.[Bai Xiao, Wang Zhongfu,Yang Lixiao.Correlation analysis between soil moisture and environmental factors by remote sensing in upper reach of Heihe River Watershed[J].Remote Sensing Information,2016,31 (6):121 -127.]   
[20]巩杰,钱彩云,钱大文.1977—2013 年疏勒河中下游土地利用 变化与环境响应[J].干旱区研究,2017,34（4)：775－781. [Gong Jie,Qian Caiyun,Qian Dawen.Land use change and response of environment in the middle-lower reaches of the Shule

River Basin during the period of 1977-2013[J].Arid Zone Research,2017,34(4):775-781.]

[21]高前兆.河西内陆河流域的水循环特征[J].干旱气象，2003， 21(3）:21-28.[Gao Qianzhao.The features of water cycle in inland river basins in Hexi region[J].Arid Meteorology,2O03,21 (3):21-28.]

[22]李曼，丁永建,杨建平，等.疏勒河径流量与绿洲面积、农业产值及生态效益的关系[J].中国沙漠，2015，35（2）：514-520.[Li Man,Ding Yongjian,Yang Jianping,etal.The impact of runoffon the oasis area,agro-output value and ecological benefits in theShule River Basin[J].Journal of Desert Research,2O15,35（2）：514 -520.]

[23]Chang Y,Ding Y,Zhao Q,et al.Remote estimation of terrestrial evapotranspiration by Landsat 5 TM and the SEBAL model in cold and high-altitude regions:A case study of the upper reach of the Shule River Basin,China[J].Hydrological Processes,2017,31 (3):514-524.

[24]Liang S.Narrowband to broadband conversions of land surface albedo I.Algorithms[J].Remote Sensing of Environment,2001,76 (2):213-238.

[25]陈国茜，周秉荣，颜亮东，等.大气校正与温差订正对表观热惯 量法监测干旱的影响分析[C]//2012年青海省科学技术协会 年会论文集.北京：中国科学技术出版社,2012：163-170. [Chen Guoqian,Zhou Bingrong,Yan Liang Dong,et al.The influence of atmospheric correction and temperature correction on the monitoring of drought by the apparent thermal inertia method [C]//Annual Conference Proceedings of Qinghai Province Science and Technology Association in 2O12.Beijing:China Science and Technology Press,2012:163-170.]

[26]吴黎，张有智，解文欢，等.改进的表观热惯量法反演土壤含水 量[J].国土资源遥感,2013,25（1）：44-49.[WuLi,Zhang Youzhi,Xie Wenhuan,et al.The inversion of soil water content by the improved apparent thermal inertia[J].Remote Sensing for Land and Resources,2013,25(1) :44-49.]

[27]程善俊，管晓丹，黄建平.利用GLDAS资料分析黄土高原半干 旱区土壤湿度对气候变化的响应[J].干旱气象，2013，31（4)： 641-649.[Cheng Shanjun,Guan Xiaodan,Huang Jianping.Analysis of response of soil moisture to climate change in semi-arid Loess Plateau in China based on GLDAS data[J].Journal of Arid Meteorology,2013,31(4） :641-649.]

[28]Georganos S,Abdi A M,Tenenbaum DE,et al.Examining the NDVI-rainfall relationship in the semi-arid sahel using geographically weighted regression[J].Journal of Arid Environments,2O17,146：

64 -74.   
[29]Brunsdon C,Fotheringham S,Charlton M. Geographically weighted regression-modelling spatial non-stationarity[J]. Journal of the Royal Statistical Society,1998,47(3）:431-443.   
[30]郭茜,李国春.用表观热惯量法计算土壤含水量探讨[J].中国 农业气象,2005,26(4）:215-219.[Guo Qian,Li Guochun.Monitoring of soil moisture by apparent thermal inertia method[J]. Chinese Journal of Agrometeorology,2005,26(4）:215-219.]   
[31］邸兰杰.基于TVDI和ATI模型河北省土壤湿度遥感反演 [D].石家庄：河北师范大学,2014.［DiLanjie.The Remote Sensing of Soil Moisture Based on ATIand TVDI Model in Hebei Province[D].Shijiazhuang: Hebei Normal University,2014.]   
[32］刘普幸,张克新,霍华丽,等.疏勒河中下游绿洲胡杨林土壤水 盐的空间变化特征与成因[J].自然资源学报,2012,27（6)： 942-952.[Liu Puxing,Zhang Kexin,Huo Huali,et al. Characteristics and causes of the spatial variations of soil water and salt content under Populus euphratica Oliv.in the middleand lower reaches of the Shule River Basin[J].Journal of Natural Resources, 2012,27(6) :942 -952.]   
[33］常昌明,牛建明,王海,等.小针茅荒漠草原土壤水分动态及其 对降雨的响应[J].干旱区研究,2016,33（2)：260－265. [Chang Changming,Niu Jianming，Wang Hai,et al.Dynamic change of soil moisture and its response to rainfall in a Stipa klemenzii steppe[J].Arid Zone Research,2016,33(2）:260-265.]   
[34］张丽.疏勒河流域降水分布规律及变化趋势分析[J].甘肃水 利水电技术,2015,51（7）：1-4.［ZhangLi.Distribution and trend analysis of precipitation in the Shule River Basin[J].Gansu Water Resourcesand Hydropower Technology,2015,51（7）: 1-4.]   
[35］赵慧.河西地区干湿变化特征分析及干旱年预测[D].兰州： 兰州大学,2015.[Zhao Hui.Analysis of Dry/Wet Variation Characteristicsand Prediction for Years of Drought in Hexi Region [D].Lanzhou;Lanzhou University,2015.]   
[36］赵跃环.鄂尔多斯盆地植被覆盖与土壤湿度反演研究[D].北 京：中国地质大学,2015.[Zhao Yuehuan.Research on Vegetation Cover and Soil Moisture Inversion in Ordos Basin[D].Beijing:China University of Geosciences,2015.]   
[37］方楷,宋乃平,魏乐,等.荒漠草原不同地形条件下土壤水分和 地上生物量的时空分异[J].干旱区研究,2012,29（4)：641- 647.[Fang Kai,Song Naiping,Wei Le,et al.Spatiotemporal distribution of soil moisture content and aboveground biomass under different terrains in desert steppe[J].Arid Zone Research,2012,29 (4) :641 -647.]

# Inversion of Soil Moisture Content in the Shule River Basin

GUO Xiao-juan’，ZHOU Yan-yan¹， GUO Jian-jun²， CHEN Guan-guang'， YUE Dong-xia' (1.College of Earth and Environmental Sciences，Lanzhou University，Lanzhou 73oooo，Gansu,China; 2.Key Laboratory of Desert and Desertification，Northwest Institute of Eco-environment and Resources, Chinese Academy of Sciences,Lanzhou 73oooo,Gansu,China)

Abstract：Soil moisture is an important factor affecting vegetation growth inarid regions.Obtaining soil moisture data at aregional scale can providea scientificbasis for ecological regeneration and conservation offragile ecosystem in aridandsemiarid regions.In this paper，the Apparent Thermal Inertia method and statistical downscaling method were used to obtain the data of soil moisture content at $0 - 1 0 \ \mathrm { c m }$ depth in the Shule River Basin in April, July,October and December 2O16 with a1km resolution based on the Moderate Resolution Imaging Spectroradiometer（MODIS） surface temperature and reflectance data and Global Land Data Asimilation System（GLDAS） soil moisturedata.The purposes of the study were to lucubrate the spatiotemporal change of soil moisture content and the correlation between local soil moisture content and vegetation by geographically weighted regression analysis. The results showed that the average annual soil moisture in the Shule River Basin varied in a range of $1 0 - 1 8 ~ \mathrm { m m }$ （204号 with an average of $1 4 . 1 1 \ \mathrm { m m }$ in 2016. Soil moisture content in the Shule River Basin changed significantly in 2016,and the average and discrete degree of soil moisture content was in an order of July $>$ October $>$ April > December.The soil moisture content in the eastof the Shule River Basin was higher than that in the west.Soil moisturecontent was the highest in the upper reaches of the Shule River，three main irrigation areas and near the MaZong Mountain in the north ofthebasin,but it was the lowestin the Kumtag Desert and Gobi near Aksai-Dunhuang and theupper reaches of the Danghe River.The seasonal variation of spatial distribution patern of soil moisture content inthe basin was significant,and the spatial distribution of variationcoeffcient was similarto thatof average anual soil moisture content.There was a positive correlation between the soil moisture contentand the Normalized Diference Vegetation Index（NDVI），butthe correlation was different from differentregions.It was the highest in the irrigation areas.

Key Words:soil moisture content； inversion model; GLDAS；ATI； NDVI； Shule River Basin