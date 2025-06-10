# 陕西省退耕还林工程对植被恢复的效应基于PCSE修正的面板数据模型

成佩昆1,²，胡守庚1,²，孙涛³，陈海滨³(1．中国地质大学(武汉)公共管理学院,湖北武汉430074;2．国土资源部法律评价工程重点实验室,湖北武汉430074；3．西北农林科技大学经济管理学院,陕西杨凌712100)

摘要：基于1998—2013 年的 $\mathrm { s P o T _ { \mathrm { v E G } } }$ NDVI数据,利用像元二分法和面板校正标准误(PCSE)估计方法,分析陕西省植被覆盖时空变化特征以及退耕还林工程、降雨水平等自然、社会经济因素对植被覆盖变化的相对贡献,探究退耕还林工程对植被恢复的驱动效应。结果表明： $\textcircled{1}$ 陕西省植被覆盖总体呈增加趋势，1998—2013年年均归一化植被指数(NDVI)值增长 $0 . 9 8 \%$ ，且在退耕还林工程实施阶段(1998—2009年），植被恢复效果更为明显。 $\textcircled{2}$ 陕西省植被恢复效果空间分异显著，16a间，各地区NDVI值上升幅度不同， $4 0 . 6 1 \%$ 的区域提升约 $0 . 1 , 2 9 . 0 5 \%$ 的区域提升约 $0 . 2 , 2 3 . 6 9 \%$ 的区域提升0.25以上。其中,位于陕北退耕还林区的延安市植被恢复效果最为明显,NDVI年增长约为 $1 . 1 2 \%$ 。 $\textcircled{3}$ 退耕还林工程对植被恢复影响显著,退耕还林面积占土地总面积每提升 $1 \%$ 将使NDVI值增加 $1 . 9 7 \%$ ,相当于降水量增加了 $4 . 2 9 \%$ ,这对于降水量少且不均的陕西省生态环境建设具有重要参考意义。

关键词：退耕还林工程；植被恢复；NDVI；面板校正标准误(PCSE)；陕西

当前，中国生态文明建设正处于快速推进的重要时期，如何有效解决由以往不尽合理的经济发展模式而导致的土地沙化、水土流失等生态环境问题已经成为学术界及各级政府部门关注的重点。植被作为生态系统的主体部分[1-3],是指示生态环境变迁的重要指标[1,4-5]。植被恢复是生态系统恢复的首要工作[6。退耕还林工程作为我国乃至世界上规模最大的生态修复和生态补偿工程，是应对环境变化和人类活动干扰的重要措施之一。随着工程的深入推进,西部退耕区植被覆盖度显著提高[7-8]。如何从区域尺度定量分析植被恢复进度，揭示退耕还林工程对植被恢复的相对贡献，对指导工程顺利实施以及为深化生态文明体制改革提供决策参考具有重要现实意义。

植被覆盖及其变化是区域生态环境变化的重要指标[9,是自然、人文等因素共同作用的结果,尤其是在人类活动影响日趋强烈的今天，植被覆盖变化更能深切反映人类活动的进程。近年来，随着地理信息科学的发展与成熟，遥感技术已成为获取植被覆盖相关数据的主流方式。归一化植被指数（ND-

VI)是目前广泛应用于反映植被状况的指标，它与植被覆盖度、生长状况、生物量和叶面积指数密切相关[10-11],能够在较大时空尺度上反映区域植被覆盖信息[12]。学者们从国家及区域尺度出发[13-15],利用NDVI对植被覆盖时空变化特征及其与人类活动和气候变化的相关关系等开展了大量研究[16-19],并取得了较为丰富的成果和可资借鉴的经验。与此同时，部分学者重点关注了退耕区的植被覆盖变化情况,信忠保等[20指出，自退耕还林政策大规模实施以来,黄土高原植被覆盖度显著提高;张清雨等[21]分析了内蒙古不同生态区内NDVI时空变化，指出人类活动对NDVI的影响程度逐渐增强。类似研究很多，结果均表明植被覆盖的时空变化与退耕还林工程的实施密切相关。然而，上述研究多从定性角度描述退耕区植被变化情况，从定量角度评估退耕还林工程对植被恢复相对贡献的研究较少，不利于准确评估退耕还林工程所取得的实效。

陕西省是我国水土流失最为严重的省份之一，省内地貌状况复杂，南北空间差异大，植被覆盖度低,整体生态环境相对脆弱[22]。陕北地区在 20 世纪末和21世纪初频繁发生极端恶劣天气，生态失调等环境问题尤为突出。鉴于此，为有效治理和解决严重的生态环境恶化和水土流失问题，陕西省于1999 年率先实施退耕还林工程，历经十几年，植被覆盖度显著提高,林草地面积占比不断增加,生态环境明显好转。因此，有效揭示退耕还林工程对植被恢复的驱动作用，对于推进陕西省生态文明建设具有重要的意义。

本文基于RS 和GIS 技术，利用 $\mathrm { \Delta S P O T _ { \mathrm { { v E G } } } }$ NDVI数据，提取陕西省1998—2013年地表植被覆盖变化的时空信息，分析研究区植被覆盖的年际变化和区域差异特征，并通过PCSE估计方法定量分析退耕还林工程、降雨水平、人地关系、经济发展水平、农耕强度等自然、社会经济因素对植被覆盖变化的相对贡献，进而探讨退耕还林工程对植被恢复效果的驱动效应，以期为客观评价陕西省退耕还林工程的生态效益提供科学依据，为西部地区深入开展生态文明建设提供决策参考。

# 1 研究区概况

陕西省位于我国西北内陆（ $( 3 1 ^ { \circ } 4 2 ^ { \prime } \sim 3 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { N }$ $1 0 5 ^ { \circ } 2 9 ^ { \prime } \sim 1 1 1 ^ { \circ } 1 5 ^ { \prime } \mathrm { E } { } )$ ，平均海拔 $1 \ 1 2 7 \ \mathrm { m }$ ,地形呈狭长状，按照地貌可划分为黄土高原区、秦岭山地区、关中平原区等,其中，黄土高原区占全省面积最大,占比达 $40 \%$ 以上。全省地跨北亚热带、暖温带和中温带3个气候带，南北气候差异显著，气温由南向北逐渐降低，年平均气温在 $7 \sim 1 6 ~ \mathrm { { ^ circ C } }$ 。年降水量北少南多，年际降水量差异较大，且降水各季分配不均衡，多集中在每年的7一8月。陕西省水土流失严重，是国家退耕还林工程重点建设省份之一。1999年起,陕西省启动并实施了退耕还林工程。根据陕西省林业勘查设计院提供的退耕还林区图（图1），陕西省退耕还林区包括陕北退耕还林区和陕南退耕还林区，分别位于陕北黄土高原丘陵的沟壑区、渭北塬区和陕南低山丘陵区。陕西省退耕还林区以草地和耕地为主，分别占退耕还林总面积的 $4 5 . 9 \%$ 和$4 4 . 1 \%$ ；林地面积占退耕还林总面积的 $9 . 0 \%$ ；水域、城乡、工矿、居民用地和未利用地所占比例不及$1 \%$ [23]。自退耕还林工程实施以来,生态建设取得了明显成效，十多年来累计完成退耕还林计划任务$2 . 4 4 \times 1 0 ^ { 6 } ~ \mathrm { h m } ^ { 2 }$ ,其中退耕地还林 $1 . 0 2 \times 1 0 ^ { 6 } ~ \mathrm { h m } ^ { 2 }$ ，国家累计投入补助资金 $2 . 7 9 \times 1 0 ^ { 1 0 }$ 元。

![](images/a07038982a154e38966a82914eb7a7b9a0faf754be199d439bd28e2cb54c9b05.jpg)  
图1陕西省退耕还林区示意图  
Fig.1Schematic map of the areas where the Grain for Green Project is implemented in Shaanxi Province

# 2 数据与研究方法

# 2.1 数据来源与数据预处理

收集了1998—2013年陕西省10个主要行政区（市/区）16a的数据，所构成的面板数据总计有960个观测值。

2.1.1数据数据来源于 $\mathrm { s P o T _ { \mathrm { v E G } } }$ NDVI数据产品（Flemish Institute for Technological Research，Vi-to，Belgium），该数据从1998年4月开始提供，时间精度10d,空间精度 $1 ~ \mathrm { k m }$ 。回顾以往国内及陕西省的相关研究，8月是陕西省植物生长最茂盛的时间点,NDVI值处于全年最高水平[24]。因此,研究使用ENVI5.1软件进行格式转换，提取出1998—2013年每年8月底的波段影像图。由于原始影像已经过辐射校正和大气校正等预处理，故可直接利用BandMath工具对遥感影像图做格式转换,将其原始数据格式 $( 0 \sim 2 5 5 )$ 转换为研究需要的 NDVI值（取值范围[-1,1]）[25],计算公式为： $\mathrm { N D V I } = \mathrm { D N } \times 0 . \ 0 0 4 \ - 0 . \ 1$ ,其中，NDVI值大于零表示覆盖地物是绿色植被，且值越大表明绿色植被数量越多，覆盖度越高；值越接近于零表明绿色植被覆盖度越低；若NDVI值为负值则表示地表覆盖物是非植被地物，例如裸露地表（岩石、沙土）、水域、雪、冰或者云覆盖等。

2.1.2陕西省10个地级市的统计数据降水量数据来源于国家气象科学数据共享服务平台；GDP、CPI数据来源于《陕西统计年鉴》；人口数收集于国家统计局;耕地面积、土地面积收集于陕西林业局;退耕还林面积收集于国家林业局退耕还林（草）工程管理办公室数据共享平台。

# 2.2 研究方法

2.2.1 植被覆盖度提取方法 植被指数(VI)是从遥感影像中抽象出来的对地表植被活动简单、有效和经验的量度，它能够反映地表植物生长状况、覆盖情况、生物量、叶面积指数、光合作用强度等生物物理特征。大量研究表明，植被指数与植被覆盖度之间存在显著的相关关系，用它来计算植被覆盖度是合适的(13,16]。其中,归一化植被指数（NDVI)对植被的生物物理特征十分敏感，且在时效、尺度方面都具有显著优势，通常被用来进行区域尺度的植被分类和植被覆盖度研究[26-27]

研究采用像元二分模型建立NDVI与植被覆盖度二者之间的转换关系,提取植被覆盖度信息[28]像元二分模型基于混合像元分解理论，将影像数据中的绿色植被和裸土信息进行线性分解，进而分离得到像元中的植被丰度信息，反演植被覆盖度。该方法能够在较大程度上消除土壤等背景因素的影响，且对影像辐射校正影响不敏感，计算简便，已被广泛应用于计算植被覆盖度，并取得了较为理想的结果[18,23,29] 。

模型假设每个像元的NDVI值由绿色植被所贡献的信息与裸土部分所贡献的信息合成，NDVI值计算公式如下：

$$
{ \mathrm { N D V I } } = { \mathrm { N D V I } } _ { \mathrm { v e g } } f _ { c } + { \mathrm { N D V I } } _ { \mathrm { s o i l } } \left( 1 - f _ { c } \right)
$$

式中： $\mathrm { \Delta N D V I _ { v e g } }$ 为纯植被像元的 NDVI值; $\mathrm { \Delta N D V I _ { s o i l } }$ 为纯裸地像元的NDVI值; $f _ { c }$ 为植被覆盖度。根据公式(1)， $\boldsymbol { { f } } _ { c }$ 的计算公式如下：

$$
f _ { c } = \left( \mathrm { { N D V I - N D V I } _ { \mathrm { s o i l } } } \right) / ( \mathrm { { N D V I } _ { \mathrm { v e g } } - \mathrm { { N D V I } _ { \mathrm { s o i l } } } ) }
$$

理论上, $\mathrm { \Delta N D V I _ { v e g } }$ 趋于 $1 , \mathrm { { N D V I } _ { \mathrm { { s o i l } } } }$ 趋于0。但受环境等因素的影响， $\mathrm { \Delta N D V I _ { v e g } }$ 和 $\mathrm { \Delta N D V I _ { s o i l } }$ 存在一定的变异。目前不同研究对 $\mathrm { \Delta N D V I _ { v e g } }$ 和 $\mathrm { \Delta N D V I _ { s o i l } }$ 的取值方法有较大差异，研究结合多数学者的取值经验，将各植被类型的NDVIg和 NDVIsoi取为定值计算f[16,18]实际计算过程中，分别用生长季内NDVI最大值和最小值代替 $\mathrm { \Delta N D V I _ { v e g } }$ 和 $\mathrm { \Delta N D V I _ { s o i l } }$ ，则植被覆盖度公式如下：

$$
f _ { c } = \mathrm { ( \Delta N D V I - N D V I _ { \mathrm { m i n } } ) } / ( \mathrm { \Delta N D V I _ { \mathrm { m a x } } - N D V I _ { \mathrm { m i n } } ) }
$$

该方法已在其他地区广泛应用，并且精度较高。如陈效逑等[30]用此方法估算内蒙古地区典型草原植被覆盖度，并对估算值与观测值进行拟合，拟合系数接近于1,表明估算结果可信;李苗苗等[31]采用此方法对密云水库上流进行了植被覆盖度提取，并与实测值进行相关分析，相关系数达$9 9 \%$ ,认为估算结果可靠性较高，可适用于大面积估算。

2.2.2面板数据模型与方法研究拟选用面板数据回归模型来直观展现退耕还林工程对植被恢复的影响。使用面板数据，可以克服时间序列分析受多重共线性的困扰，有利于观察个体差异，增加多变性，减少共线性，提高自由度和有效性，减少偏差。回归模型可以清晰地观察因变量关于另一个（些)自变量的具体依赖关系。

为了避免遗漏重要变量造成虚假回归，在把退耕还林工程作为影响植被恢复的主要自变量外，还选取降雨水平、人地关系、经济发展水平、农耕强度作为自变量对植被恢复进行整体分析。将植被覆盖水平作为因变量，并设立随机扰动项 $\mu$ 。为确保估计结果的有效性，对回归方程进行对数化处理，并利用Stata12.0对面板模型进行Hausman检验，得 $P$ 值小于0.05显著性水平，故拒绝建立随机效应模型原假设，选择建立个体固定效应模型。模型设置如下[13]：

$$
\mathrm { l n N D V I } _ { i t } = \beta _ { 0 } + \beta _ { 1 } \mathrm { l n p r e c } _ { i t } + \beta _ { 2 } \mathrm { l n p o p } _ { i t } + \beta _ { 3 } \mathrm { l n g d p } _ { i t } +
$$

$$
\beta _ { 4 } \mathrm { f a r m } _ { i t } + \beta _ { 5 } \mathrm { R G P F } _ { i t } + \mu _ { i t }
$$

考虑到面板数据可能存在同步相关、面板数据异方差、序列相关等问题，在进行面板数据回归分析过程中，选取面板矫正标准误(PCSE)估计方法对固定效应模型进行修正，以加强回归结果的有效性和稳健性。PCSE方法在保留最小二乘法（OLS）估计参数的基础上将残差项代入对角矩阵，对其标准差进行修正，能够更加准确地对面板数据进行回归估计。

变量解释及描述性统计(表1)如下：

表1变量定义与基本统计  
Tab.1 Variabledefinitionsandbasicstatistics   

<html><body><table><tr><td>变量</td><td>变量描述</td><td>均值 标准差</td><td>期望</td></tr><tr><td>lnNDVIu</td><td>对数变换的 NDVI均值</td><td>-0.6354 0.3690</td><td>na</td></tr><tr><td>lnprecit</td><td>对数变换的年降水量</td><td>6.3880 0.305 3</td><td>+</td></tr><tr><td>lnpopit</td><td>对数变换的人口密度=人 □总数/土地面积</td><td>5.2556 0.739 4</td><td></td></tr><tr><td>lngdpit</td><td>对数变换的经济发展水 平=GDP/土地面积</td><td>-4.6538 1.065 3</td><td></td></tr><tr><td>farmit</td><td>农耕强度=耕地面积/土 地总面积</td><td>0.1893 0.1213</td><td></td></tr><tr><td>RGPFit</td><td>退耕强度=累计退耕还林 面积/土地总面积</td><td>0.04070.027 4</td><td>+</td></tr></table></body></html>

注：GDP经CPI调整（以1997年为基准）；“ $^ +$ ”代表回归系数期望为正，“-”代表回归系数期望为负。

（1）植被覆盖水平，用NDVI来表征。为分析退耕还林工程对植被恢复的驱动效应，将NDVI设为因变量。

(2）降雨水平，用年降水量（prec)来表征。降水量对植物生长的积极影响在相关研究中已被充分证实，一般情况下，降水量越多的地区植被覆盖水平越高，两者成正向关系。

（3）人地关系，用单位面积人口数量即人口密度(pop)来表征。其反映人口数量与土地资源之间的关系。一般情况下，人口密度越高，土地需求和利用程度越高，植被覆盖水平越低。

（4）经济发展水平。为消除地区面积对生产总值的影响，选用单位土地面积的GDP（gdp）作为地区经济发展水平的表征指标。一般情况下，经济发展水平越高，对土地的利用程度越高，植被覆盖水平越低。同时，为消除价格波动的影响，将各市的名义国民生产总值指数折算成1997年不变价的实际人均 GDP。

（5）农耕强度，用单位土地面积的耕地面积(farm)来表征。其反映土地总面积与耕地面积的数量关系，一般情况下，农耕强度与植被覆盖水平成负向关系。

（6）退耕还林工程。1999 年陕西省开始施行退耕还林工程，直至2009年第一轮退耕还林工程阶段性结束。为量化这一研究对象，模型选用单位土地面积的退耕还林面积（RGPF)作为研究指标。退耕还林工程是在减少耕地面积的基础上，人为干预植物生长的生态工程，因此，预期退耕还林工程与植被覆盖水平成正向关系。

# 3结果与分析

# 3.1植被覆盖年际变化特征

3.1.1NDVI值年际发展趋势提取1998—2013年陕西省历年的NDVI平均值来表示NDVI的年际变化特征(图2a）。由图2a可知，研究期内陕西省NDVI值总体呈现上升趋势,而年际间的NDVI指数存在波动，一定程度上是受降水量等自然条件的影响。其中，2000年的植被覆盖在研究区间内最低，NDVI年平均值为0.439；2012年的植被覆盖在研究期内最高，NDVI年平均值为0.601;整体来看，陕西省NDVI年平均值增长速率为 $0 . 9 5 \%$ ,表明陕西省在1998—2013年NDVI值不断增加，植被恢复取得了阶段性进展。

3.1.2植被覆盖度变化利用NDVI数据分别计算出1998—2013 年陕西省10个市的植被覆盖度（图2）。由图2可知，虽然各市的植被覆盖度年际间出现波动，但整体仍呈上升趋势。其中，位于陕北退耕还林区的延安市和陕南退耕还林区的安康市植被覆盖度的增加尤为显著。延安市1998年的植被覆盖度为 $3 9 . 7 9 \%$ ，至2013年已增长为 $5 5 . 1 8 \%$ ；安康市的植被覆盖度由1998 年的 $7 4 . 0 7 \%$ 增长至2013年的 $8 4 . 2 3 \%$ 。值得注意的是,延安市地处陕北地区，自然条件相比其他区域并不占优，但相比其他地级市，延安市植被覆盖度增长最快，年增长速率为 $1 . 1 2 \%$ 。与此同时，通过统计数据可得，延安市在1998—2013年累计退耕还林面积占全省的$2 3 . 9 5 \%$ ，这被视为其植被覆盖度增加的主要原因，也在一定程度上表明了退耕还林工程对植被覆盖增加存在积极影响。为进一步验证退耕还林工程对植被覆盖变化影响的显著性，引入统计模型对其进行深入分析。

# 3.2植被覆盖区域差异特征

通过对 1998 年、2009 年与 2013 年的 $\mathrm { s P o T _ { \mathrm { v E G } } }$ NDVI数据进行叠加计算，可得到年份间的NDVI差值图（图3）。由图3c可知，1998—2013年除关中地区外，全省大面积地区植被覆盖都得到了显著提升。相较于1998年，2013年陕西省仅 $5 . 9 3 \%$ 区域的NDVI值轻微缩减，且缩减幅度小于0.2;而绝大部分区域的NDVI值都得到提升，其中， $4 0 . 6 1 \%$ 区域的NDVI值提升了约 $0 . 1 , 2 9 . 0 5 \%$ 区域的NDVI值提升了约 $0 . 2 , 2 3 . 6 9 \%$ 区域的NDVI指数提升了0.25以上。

![](images/5db8ae5b8678320914da6e69a1eac4a6b28598afd5c6b3ddd019bfed746152d4.jpg)  
图21998—2013年陕西省NDVI和植被覆盖度的逐年变化  
Fig.2Annual changes of NDVI and vegetation coverage in Shaanxi Province from 1998 to 2013

陕西省退耕还林工程于2009年开始进入验收与维护阶段(新一期的退耕还林工程不在研究区间内，故暂不研究），1998—2009 年及2009—2013 年的陕西省NDVI值变化(图3a与图3b)响应了这一人为要素的变化。NDVI差值显示，1998—2009 年陕西省大部分区域 NDVI指数都得到较大幅度提升，而2009—2013年只有小部分区域 NDVI值发生明显变化，多数区域基本维持稳定状态。经统计分析可知,1998—2009 年，仅西安、宝鸡、渭南、汉中 4市中的少数区域NDVI值略微缩减，省内其他区域的 NDVI值均得到不同程度的增加;2009—2013 年，西安、铜川、宝鸡3市的NDVI值普遍降低,其他区域基本持平。这显然表明1998—2009年植被状况改善更为显著。

综上所述，1998一2013年省内绝大部分市区NDVI值呈现上升趋势，且不同阶段呈现出不同的变化特征。在1998—2009年退耕还林工程进行期间，研究区内绝大部分区域NDVI值呈一致性增加趋势，植被恢复效果显著,从侧面反映出退耕还林工程的实施对于陕西省的植被恢复有着积极的作用。相比之下，2009年退耕还林工程进入验收与维护阶段后，各区域NDVI值变化增减不一，陕北地区植被覆盖基本不变，陕南地区植被覆盖略微增加，关中地区各市植被覆盖普遍缩减。

无论从全域还是各市区的植被覆盖时空变化来看，陕西省植被覆盖水平均呈现改善趋势，但是，仍然不能完全确信这一改善是由退耕还林工程实施推动的，也有可能是其他自然或社会经济因素导致了以上观察结果。鉴于此，笔者通过回归模型来定量分析退耕还林工程实施对植被恢复的驱动效应。

# 3.3退耕还林工程对植被恢复的驱动效应

利用1998—2013年陕西省10个市级行政区的16a数据，构建面板数据模型来重点探讨退耕还林工程实施与陕西省植被覆盖变化的相关关系，将选取的6个因素值导人市级研究单元，实现因素的定量化和空间化，得到其空间分布图（图4）。

为了消除面板数据存在的同期相关和截面异方差问题，选取PCSE估计方法对固定效应模型进行修正，以加强回归结果的有效性和稳健性，更充分地反映NDVI与各个可能的影响因素之间的关系。回归结果如表2所示。

![](images/bdce174d20a8d788e69e95d5d8b564dec46c53548b3634e732ecdccef12034ba.jpg)  
Fig.3Difference of values of NDVI in Shaanxi Province in typical years

![](images/9a71c3c97f56b435920a8fe192276f9e7edf181289347383416c19ca801fa6cf.jpg)  
图3典型年份陕西省NDVI差值  
注：本文共使用了1998—2013年16 a的数据，考虑到篇幅限制,图中仅选取2013年各地市因素数据进行空间可视化展示。  
图4陕西省植被恢复驱动因素定量化空间分布  
Fig.4Quantitative spatial distribution of driving factors for vegetation regeneration in Shaanxi Province

从表2可知，拟合优度 $R ^ { 2 } = 0 . 7 5 1 \ 5$ ,说明模型整体拟合效果较好，模型设定有效。从各变量对应

$P$ 值可知,在0.01检验水平下,降水量、人口密度、退耕强度、地均GDP、农耕强度变量对于陕西省的NDVI均值有着显著影响( $\textstyle P < 0 . 0 1 { \dot { } }$ ），除人口密度外各指标影响方向均与预期假设相符。

降水量、农耕强度、地均GDP、人口密度4个变量对植被覆盖水平的影响各不相同。从回归结果来看，降水量每增加1个百分点，可使NDVI值增加0.46个百分点。植物生长受降水量影响较大，异常的旱涝天气都会严重影响植物生长情况，生态脆弱的区域对降水量变化更敏感。农耕强度每增加1个百分点，NDVI值将下降2.74个百分点，影响程度居所有变量之首。粗放式的农耕方式严重危害到陕西省的生态环境，改善陕西省生态环境亟需在满足粮食产量需求的前提下，减少不适宜耕作的农耕地并重建生态系统。经济发展水平每提升1个百分点，NDVI值将下降0.0758个百分点。经济增长带来的是资源需求的增多和环境压力的加大，因此，在保证经济正常发展的前提下需尽可能减小其对生态环境的影响，实现可持续发展。与预期不同的是，人口密度的增加对NDVI值有着正面的影响。这一方向与预期的偏差在一定程度上是陕西省城镇化率的快速提升导致的[32]。近年来,陕西省城镇化步伐不断加快，1998一2010年，城镇人口比重整体呈增长趋势，由 $2 1 . 8 0 \%$ 增加到 $5 0 . 0 2 \%$ 。城镇化程度越高，人口越集中,非城镇区域的环境压力随之降低[33]

表2PCSE估计方法面板数据回归结果Tab.2Regression results of PCSE  

<html><body><table><tr><td>自变量</td><td>参数估计值</td><td>标准差</td><td>P值</td></tr><tr><td>lnpreCit</td><td>0.459 4</td><td>0.0919</td><td>0.000***</td></tr><tr><td>lnpopit</td><td>0.5131</td><td>0.030 5</td><td>0.000***</td></tr><tr><td>lngdpit</td><td>-0.075 8</td><td>0.014 6</td><td>0.000***</td></tr><tr><td>farmit</td><td>-2.743 6</td><td>0.1891</td><td>0.000***</td></tr><tr><td>RGPFit</td><td>1.972 5</td><td>0.707 1</td><td>0.005***</td></tr><tr><td></td><td>-0.405 6</td><td>0.248 2</td><td>0.000***</td></tr><tr><td>调整后的R</td><td>0.7515</td><td></td><td></td></tr></table></body></html>

注： $*$ 表示 $P < 0 . 1 0$ ， $* *$ 表示 $\textstyle P < 0 . 0 5$ ， $* * *$ 表示 $P < 0 . 0 1$ □

值得注意的是，退耕还林工程的实施对陕西省植被恢复具有明显正面效应。由表2可以看出，退耕还林面积占总面积的比值每提升1个百分点，预计可使NDVI值增加1.97个百分点，换算成降水量来看，提升陕西省退耕还林面积占总面积比值1个百分点，相当于陕西省的降水量增加了4.29个百分点。这一结果对降水量偏少的西部地区具有重要意义。退耕还林工程的实施可增加植被覆盖度，提升生态系统的抵御能力，减小旱涝等气象灾害对植被造成的负面影响。1999—2013年，陕西省累计完成退耕还林 $2 . 4 1 \times 1 0 ^ { 6 } ~ \mathrm { h m } ^ { 2 }$ ,其中退耕地还林 $1 . 0 2 \times$ $1 0 ^ { 6 } \ \mathrm { h m } ^ { 2 }$ ,荒山造林 $1 . 2 6 \times 1 0 ^ { 6 } ~ \mathrm { h m } ^ { 2 }$ ,封山育林 $1 . 2 9 \times$ $1 0 ^ { 5 } ~ \mathrm { h m } ^ { 2 }$ 。退耕还林工程退出坡地及其他不适宜耕种的耕地，栽种更适合生长的林草,减少了耕地面积，对植被恢复有着积极影响。除上述影响外，退耕还林工程还改变了农村的生产、生活经营方式，进而改善了农村生态环境。随着退耕还林工程的逐步推进，农村大量劳动力从粮食生产中解放出来，从事种植业、养殖业、设施农业等劳务经济活动，改变了农村的现有产业结构;随之而来的是退耕农户收入的增长以及生活方式的改变，使得农村户用沼气得到迅速发展，煤、太阳能、天然气等逐渐取代烧柴，环境压力得到释放。从长远角度来看，退耕还林工程在改善生态环境的同时，更增强了全社会的生态保护意识，是生态环境持续改善的根本保障。

# 4结论

（1）从NDVI时序变化结果来看，1998—2013年陕西省植被覆盖水平总体呈上升趋势，NDVI值年平均增长速率为 $0 . 9 5 \%$ ,植被恢复效果明显。通过对比特定年份间的NDVI差值，可以看出，相比2009—2013年，1998—2009 年（即陕西省全面实施退耕还林工程期间)研究区NDVI值提升尤为显著。

（2）从植被覆盖度空间分布情况来看，陕西省植被覆盖水平整体上由南向北递减、空间分异特征显著。16a间,省域内NDVI值有不同程度的上升，$4 0 . 6 1 \%$ 的区域提升约 $0 . 1 , 2 9 . 0 5 \%$ 的区域提升约$0 . 2 , 2 3 . 6 9 \%$ 的区域提升0.25以上。分析表明在市域尺度上植被覆盖的增加与退耕还林工程相关性明显，植被恢复效果最好的两个市（区）分别为延安市（陕北退耕还林区）、安康市（陕南退耕还林区），其中延安市的植被覆盖水平增幅最大，年增长率达$1 . 1 2 \%$ 。

（3）退耕还林工程的实施对陕西省植被恢复具有明显的积极效应。通过统计陕西省1999—2009年累计退耕还林面积，并引入降雨水平、人地关系、经济发展水平、农耕强度等自然、社会经济因素变量，与对应地区8月的NDVI平均值进行回归分析。结果显示，退耕还林面积占总面积的比值每提升1个百分点，预计可使NDVI值增加1.97个百分点。这一定量分析进一步验证了时间动态分析的结果，说明退耕还林工程对陕西省植被恢复的影响是积极且显著的。

需要指出的是，植物生长是多种因素综合作用的结果，除所列举的因素外，不同区域的土壤状况、地形地貌、政策条件、产业结构等因素对该区域植被覆盖变化同样起着关键作用。以榆林、延安两市为例，二者同属陕北地区，但榆林地理位置更为偏北,且二者产业结构不尽相同,虽然榆林累计退耕还林面积在全省范围内仅次于延安，但其植被恢复效果相比延安市差距较大。鉴于此，后续研究应考虑加入地形地貌、产业结构等相关因素。与此同时，本文使用了遥感数据分析植被恢复状况，受遥感数据分辨率限制，解译精度受到一定影响。在今后的研究中,若采用更高空间分辨率的遥感影像，将可以更加准确、客观地评价植被恢复动态，进一步深入分析植被恢复过程中出现的问题。值得注意的是，陕西省地域差异大，各地自然环境、经济结构不尽相同，时空特征所展现出的是全省及省内不同市区植被覆盖情况对退耕还林工程的响应。这表明，从大尺度研究单元上可区分出植被覆盖变化过程中生态工程的信号。但随着生态文明建设的深入推进，对具体微观尺度(如样带、县域、镇域等)植被恢复建设工作进行科学合理的指导显得尤为迫切，因此，今后仍需要在微观尺度上对相关问题进行深入探讨。

# 参考文献（References）：

[1]Parmesan C,Yohe G.A globally coherent fingerprint of climate change impactsacross natural systems[J].Nature，2OO3，421 (6 918) :37 -42.   
[2] Hilker T,Lyapustin AI,HallFG,et al. On the measurability of change in Amazon vegetation from MODIS[J].Remote Sensing of Environment,2015,166:233-242.   
[3] 朴世龙,方精云.1982—1999 年我国陆地植被活动对气候变化 响应的季节差异[J].地理学报,2003,58（1)：119-125.［Piao Shilong,Fang Jingyun. Seasonal changes in vegetation activity in response to climate changes in China between 1982 and 1999[J]. Acta Geographica Sinica,2003,58(1）:119-125.]   
[4] PengJ,Liu Z,Liu Y,etal. Trend analysis of vegetation dynamics in Qinghai-Tibet Plateau using hurst exponent[J].Ecological Indicators,2012,14(1):28-39.   
[5] Lamchin M,Park T,Lee JY,et al.Monitoring of vegetation dynamics in the Mongolia using MODIS NDVIs and their relationship to rainfall by natural zone[J]. Journal of the Indian Society of Remote Sensing,2015,43(2):325-337.   
[6] 程冬兵,蔡崇法，孙艳艳.植被恢复研究综述[J].亚热带水土 保持,2006,18（2）:24-26.[Cheng Dongbing,Cai Chongfa,Sun Yanyan.A review of vegetation restoration[J].Subtropical Soil and Water Conservation,2006,18(2）:24-26.]   
[7]Zhou D,Zhao S,Zhu C.The Grain for Green Project induced land cover change in the Loess Plateau：A case study with Ansai Coun

ty,Shanxi Province,China[J].Ecological Indicators,2012,23

(4) :88 -94.   
[8］李登科.陕北吴起县退耕还林(草)成效的遥感监测分析[J]. 中国沙漠,2009,29（1）:125-130.[Li Dengke.Remote sensing analysison effect of tillage reverting to woodland or grassland in Wuqi,Shaanxi Province[J]. Journal of Desert Research,2009,29 (1):125 -130.]   
[9]Dai S P,Zhang B,Wang HJ,et al.Vegetation cover change and the driving factors over Northwest China[J]. Journal of Arid Land, 2011,3(1) :25 -33.   
[10]Prince S D.A model of regional primary production for use with coarse resolution satelite data[J]. International Journal of Remote Sensing,1991,12(6) :1 313-1 330.   
[11]Carlson TN,Ripley D A.On the relation between NDVI,fractional vegetation cover,and leaf area index[J].Remote Sensing of Environment,1997,62(3）:241-252.   
[12]Scanlon TM,Albertson JD,Caylor K K,et al. Determining land surface fractional cover from NDVI and rainfall time series for a savanna ecosystem[J].Remote Sensing of Environment,2002,82 (2) :376 -388.   
[13］范建忠,李登科，董金芳.陕西省重点生态建设工程区植被恢 复状况遥感监测[J].农业工程学报,2012,28（7）:228－234. [Fan Jianzhong,Li Dengke,Dong Jinfang.Remote sensing analysis of vegetation restoration in key ecological construction areas of Shaanxi Province[J].Transactions of the Chinese Society of Agricultural Engineering,2012,28（7）:228-234.]   
[14］郭继凯,吴秀芹,董贵华,等.基于 MODIS/NDVI的塔里木河流 域植被覆盖变化驱动因素相对作用分析〔J].干旱区研究, 2017,34(3）:621-629.[Guo Jikai,Wu Xiuqin,Dong Guihua,et al. Vegetation coverage change and relative efects of driving factors based on MODIS/NDVI in the Tarim River Basin[J].Arid Zone Research,2017,34(3）:621-629.]   
[15］崔林丽,史军,肖风劲,等.中国东部 NDVI的变化趋势及其与 气候因子的相关分析[J].资源科学,2010,32（1):124－131. [Cui Linli,Shi Jun,Xiao Fengjing,etal.Variation trends in vegetation NDVIand its correlation with climatic factors in Eastern China[J]. Resources Science,2010,32(1) :124-131.]   
[16］穆少杰,李建龙,陈奕兆,等.2001—2010 年内蒙古植被覆盖度 时空变化特征[J].地理学报,2012,67(9）：1255-1268.[Mu Shaojie,Li Jianlong,Chen Yizhao,etal. Spatial differences of variations of vegetation coverage in Inner Mongolia during 2Oo1- 2010 [J].Acta Geographica Sinica,2012,67(9):1 255-1 268.]   
[17］白建军,白江涛,王磊.2000—2010 年陕北地区植被 NDVI时 空变化及其与区域气候的关系[J].地理科学,2014,34（7)： 882 -888.[Bai Jianjun,Bai Jiangtao,Wang Lei.Spatio-temporal change of vegetation NDVI and its relations with regional climate in Northern Shaanxi Province in 20oO-201O[J].Scientia Geographica Sinica,2014,34(7) :882 -888.]   
[18］刘雪梅,高小红，马元仓.2002—2015年青海省不同气候区植 被覆盖时空变化[J].干旱区研究,2017,34(6):1345-1352.

[Liu Xuemei,Gao Xiaohong,Ma Yuancang.Spatio-temporal evolution of vegetation coverage in Qinghai Province,China during the periods from 2002 to 2015[J].Arid Zone Research,2017,34（6）： 1 345 -1 352.]

[19］王涛,杨梅焕.榆林地区植被指数动态变化及其对气候和人类活动的响应[J].干旱区研究，2017，34（5）：1133-1140.[Wang Tao,Yang Meihuan.Dynamic change of NDVI and itsre-sponse to climate change and human activities in Yulin,ShaanxiProvince,China[J].Arid Zone Research,2017,34（5）:1 133-1 140.]

[20]信忠保，许炯心，郑伟.气候变化和人类活动对黄土高原植被 覆盖变化的影响[J].中国科学D辑：地球科学，2007，37 (11）:1 504-1 514.［Xin Zhongbao,Xu Jiongxin,Zheng Wei. Response of vegetation cover change to climate change and human activities in LoessPlateau[J].Scientia Sinica(Terrae）,2O07,37 (11):1 504 -1514.]

[21]张清雨,赵东升，吴绍洪，等.基于生态分区的内蒙古地区植被 覆盖变化及其影响因素研究[J].地理科学,2013,33（5）： 594-601.[Zhang Qingyu,Zhao Dongsheng,Wu Shaohong,et al. Research on vegetation changes and influence factors based on ecogeographical regions of Inner Mongolia[J].Scientia Geographica Sinica,2013,33（5):594-601.]

[22]Wang F,Mu X,Li R,et al. Co-evolution of soil and water conservation policy and human-environment linkages in the Yellow River Basin since 1949[J].Science of the Total Environment,2015, 508:166 -177.

[23]范建忠，李登科，周辉.陕西省退耕还林工程区植被覆盖度的变化分析[J].干旱地区农业研究，2013，31（4）：207-213.[Fan Jianzhong,Li Dengke,Zhou Hui.Variation of fractional vege-tation coverage in returning cropland to woodland project zones inShaanxi Province[J].Agricultural Research in the Arid Areas,2013,31(4):207-213.]

[24]秦超，李君轶，陈宏飞，等.陕西省植被覆盖时空演变特征及其与气候因子的关系[J].中国农业气象，2015，36（1）：108-114.[Qin Chao,Li Junyi,Chen Hongfei,et al.Temporal and spa-tial evolution of vegetation cover and its relationship with climatefactors in ShaanxiProvince[J].Chinese Journal of Agrometeorolo-gy,2015,36(1) :108-114.]

[25]Li J,Liu Y,Cao M,et al. Space-time characteristics of vegetation cover and distribution:Case of the Henan Province in China[J]. Sustainability,2015,7(9):11 967-11 979.

[26]杨雪梅,杨太保,刘海猛,等.气候变暖背景下近30 a北半球植 被变化研究综述[J].干旱区研究,2016,33（2）：379-391. [Yang Xuemei,Yang Taibao,Liu Haimeng,et al. Vegetation variation in the North hemisphere under climate warming in the last 30 years[J].Arid Zone Research,2016,33(2）:379 -391.]   
[27］韩辉邦,马明国,马守存,等.近30 a青海省植被变化及其气候 驱动因子分析[J].干旱区研究,2017,34（5)：1164-1174. [Han Huibang,Ma Mingguo,Ma Shoucun,et al.Vegetation change and its driving climatic factors in Qinghai Province in recent 30 years[J].Arid Zone Research,2017,34(5）:1 164-1 174.]   
[28]Gutman G,Ignatov A.The derivation of the green vegetation fraction from NOAA/AVHRR data for use in numerical weather prediction models[J]. International Journal of Remote Sensing,1998, 19(8):1 533 -1 543.   
[29］吴云,曾源,赵炎,等.基于MODIS 数据的海河流域植被覆盖 度估算及动态变化分析[J].资源科学,2010,32（7)：1417- 1 424.[Wu Yun,Zeng Yuan,Zhao Yan,et al. Monitoring and dynamic analysis of fractional vegetation cover in the Hai River Basin based on MODIS data[J]. Resources Science,201,32（7）：: 1 417 -1 424.]   
[30］陈效逑,王恒.1982—2003 年内蒙古植被带和植被覆盖度的时 空变化[J].地理学报,2009,64（1）:84－94.[Chen Xiaoqiu, Wang Heng.Spatial and temporal variations of vegetation belts and vegetation cover degrees in Inner Mongolia from 1982 to 2003[J]. Acta Geographica Sinica,2009,64(1) :84- 94.]   
[31］李苗苗,吴炳方,颜长珍,等.密云水库上游植被覆盖度的遥感 估算[J].资源科学,2004,26(4）:153-159.[Li Miaomiao,Wu Bingfang,Yan Changzhen,et al.Estimation of vegetation fraction in the upper basin of Miyun Reservoir by remote sensing[J].Resources Science,2004,26(4） :153-159.]   
[32]付云鹏,马树才，宋琪.人口规模、结构对环境的影响效应- 基于中国省际面板数据的实证研究[J].生态经济,2015,31 (3）:14-18.[Fu Yunpeng,Ma Shucai,Song Qi.Examining the impact of demographic factors on regional environment:An empirical study based on Chinese provincial panel data[J].Ecological Economy,2015,31(3) :14-18.]   
[33］马孝先.中国城镇化的关键影响因素及其效应分析[J].中国 人口·资源与环境,2014,24（12）:117-124.[Ma Xiaoxian.Analysis on the key influence factors of urbanization and its effects in China[J].China Population,Resources and Environment,2014,24 (12) :117 -124.]

# Effect of Grain for Green Project on Vegetation Regeneration in Shaanxi Province :Based on PCSE Panel Data Model

CHENG Pei-kun1²， HU Shou-gengl²， SUN Tao³， CHEN Hai-bin’ (1．School of Public Administration，China University of Geosciences,Wuhan 43oo74,Hubei,China;   
2.Key Laboratory of Legal Asessment Project,Ministry of Land and Resources,Wuhan 430074,Hubei,China;   
3.College of Economics and Management，Northwest A&F University,Yangling 7121o0,Shaanxi,China)

Abstract：In this paper,the temporal and spatial variations of vegetation cover in Shaanxi Province were analyzed.The purposes of this study were to explore the driving effect of the Grain for Green Projecton vegetation regeneration,and the relative contributions of some natural andsocio-economic factors（such as the Grain for Green Project and rainfall level） to vegetation cover change were estimated based on the $\operatorname { s P O T } _ { \operatorname { v E G } }$ NDVI data during the period from 1998 to 2013 by using the pixel dichotomy method and the Panel Corrected Standard Errors（PCSE). Theresult showed that the vegetation coverage in Shaanxi Province was holistically improved,the annual average NDVI value was increased by $0 . 9 8 \%$ from 1998 to 2O13,and the effect of vegetation regeneration was obvious by implementing the Grain for Green Project from1998 to 2O09.The spatial differenceof vegetationregenerationeffect inthe province was significant.During the16 years,the NDVI in the province increased with different rates,it was increased by 0.1 in $4 0 . 6 1 \%$ area,by 0.2 in $2 9 . 0 5 \%$ area,and by 0.25 in $2 3 . 6 9 \%$ area.In which the most evident effect of the project on vegetation regeneration occurred in Yan'an City located in north Shaanxi Province, where the NDVI was increased by $1 . 1 2 \%$ . The NDVI was increased by $1 . 9 7 \%$ if the Grain for Green Project was implemented in $1 \%$ area of the total,which was equivalent to increasing $4 . 2 9 \%$ precipitation. The results of this study are of great significance for reconstructing the ecological environment in the study area.

Key words: Grain for Green Project；vegetation regeneration；NDVI；PCSE；Shaanxi Province