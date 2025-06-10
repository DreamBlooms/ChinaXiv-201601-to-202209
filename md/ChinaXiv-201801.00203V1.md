# DOI: 10.5846/stxb201611152326

王茹琳,李庆,封传红,石朝鹏.基于 MaxEnt 的西藏飞蝗在中国的适生区预测.生态学报,2017,37(24)：8556-8566.WangRLLgrsmodeling.Acta Ecologica Sinica,2017,37(24）:8556-8566.

# 基于MaxEnt的西藏飞蝗在中国的适生区预测

王茹琳1,²，李庆1\*，封传红³，石朝鹏

1四川农业大学农学院，成都611130  
2四川省农村经济综合信息中心，成都610072  
3四川省农业厅植物保护站，成都610041  
4山东省植物保护总站，济南250000

摘要;西藏飞蝗是青藏高原本地特有物种，为青稞和牧草的重要害虫,近年来危害范围有扩大蔓延趋势。研究并明确西藏飞蝗在中国的适生区域,对制定该虫的早期监测、预警及控制措施意义重大。近年来最大熵理论在物种适生研究领域得到广泛应用,基于西藏飞蝗的分布信息和环境变量,采用MaxEnt 生态位模型和ArcGIS 对其在中国的潜在分布区进行预测,用 ROC 曲线检测模型精度、刀切法(jackknife test)筛选主导环境变量及其适宜值。两次模拟的AUC 值分别为0.996 和0.993,预测结果与实际拟合度很高。西藏飞蝗在中国的高适生区主要位于四川的甘孜州,西藏的昌都地区 林芝地区、山南地区及拉萨市,中适生区则以高适生区为中心向外扩散,集中在青藏高原东部地区。海拔、8月份平均雨量、1月份平均雨量、等温性、12—2月份的平均温度是影响西藏飞蝗潜在分布的主要环境变量。 ）

关键词：西藏飞蝗;MaxEnt模型;适生分析;影响因子

# Predicting potential ecological distribution of Locusta migratoria tibetensis in China using MaxEnt ecological niche modeling

WANG Rulin1²,LI Qing1\*，FENG Chuanhong³，SHI Zhaopeng4   
1Collegeof Agronomy,Sichuan Agricultural University，Chengdu 611130,China   
2Sichuan Provincial Rural Economic Information Centre,Chengdu 61oO72,China   
3Plant Protection Station of Sichuan，Chengdu 61Oo41,China   
4Plant Protection Station of Shandong，Ji'nan 25oooo,China

Abstract: Locusta migratorid tibetensis Chen,aunique subspecies inthe Tibetan Plateau,is adestructive pest of highland barley and herbage.The methods of Maximum Entropy have been deployed for some years to addressthe problemof species abundace distributions.TomonitorandcontrolL.migratoria tibetensis，itisnecessary toinvestigatethepotential distribution area of this pest.In thisapproach，ecological niche modeling software MaxEnt（the maximumentropy model）, combined with ArcGIS（Geographic information System），was applied to predict the potential geographic distribution of $L$ ： migratoria tibetensis in China.Bioclimatic dominantfactorsand the appropriateranges oftheirvalues were also investigated. The results showedthattraining data AUC were O.996andO.993 inthe two simulations，which indicatedabeter forecast. The highlysuitablearea for L.migratoria tibetensis wasGanzi in Sichuan Province，and Changdu,Linzhi，Shanan，and Lasaof the Tibet Autonomous Region，whereas the moderatelysuitable area was inthe westof Sichuan，east of Xizang，and north of Yunnan.The important environmental factors affecting the distribution of $L$ ，migratoria tibetensis were altitude, average precipitationin August，average precipitation in January，isothermality，average mean temperature in January， average mean temperature in December，and average mean temperature in February.

Key Words:Locusta migratoria tibetensis;MaxEnt;suitable analysis;environmental factors

全世界约有蝗虫12000 余种,除南极洲外各大洲均有分布。飞蝗(Locutsa migratoria L.)是世界范围内的重要害虫,已知有1个种10个亚种,其中西藏飞蝗（Locusta migratoria tibetensis Chen)为青藏高原特有且分布海拔最高的亚种[1],主要分布在西藏、四川及青海等省区[2],主要以青稞、牧草及杂草为食[3-5]。据史料记载，西藏飞蝗曾在青藏高原多次成灾,蝗灾所到之处庄稼颗粒无收。20 世纪90 年代以来,西藏飞蝗在四川甘孜州和阿坝州,西藏普兰、昌都、阿里及青海玉树等地曾大面积爆发,尤以2003—2006 年该虫发生极为严重,特别是雅鲁藏布江、雅袭江以及金沙江等横断山脉河谷地带,蝗灾的爆发对当地农牧业正常生产造成极大破坏，导致难以估量的经济损失[6]。

预测物种适生分布是生态学的重要研究领域,物种分布模型(species distribution models,SDM)逐渐发展并成为研究物种适生性的一个重要工具[7]。此类模型根据物种已知的“存在"或"不存在"数据,结合相应的环境变量,利用一定的数学理论计算物种在目标地区的分布概率,量化环境变量与物种分布之间的关系,寻找物种分布的限制因子及生境偏好等。目前,物种分布模型的常用领域主要为:预测物种潜在分布区、物种分布与气候关系、濒危及珍贵物种适生性预测和古生物地理研究等方面[8-1],并起到了良好的效果[11]。目前常用的物种分布模型中,最大熵模型 MaxEnt(maximum entropy model)的模拟精度要高于其他模型,加之该软件具有运行时间短、操作简便、运行结果稳定和所需样本量小等特点在业内得到了广泛的认可[12-13],已被应用于多种病虫害适生性的模拟预测,如柑橘黄龙病菌（Candidatus Liberibacter asiaticus）、叶缘焦枯病菌（Xylellafastidiosa）柑橘木虱（Diaphorina citri Kuwayama)和稻水象甲（Lisorhoptrus oryzophilus Kuschel)等[14-7],且模拟的结果与物种实际分布的吻合度高。 1

目前对西藏飞蝗的研究主要集中在生物学特性、环境胁迫、数量性状及遗传特征等方面[28],还未发现对其生态位预测的相关研究报道。本研究基于MaxEnt 模型,研究西藏飞蝗分布与环境变量之间的联系,揭示影响其分布的主导气候因子,分析西藏飞蝗在中国的潜在分布区,旨在为制定合理的防控措施提供重要参考和理论依据。 人

# 1材料与方法

1.1西藏飞蝗的分布数据与处理

MaxEnt 模型模拟需要物种分布数据和环境数据,分布数据即为“存在”点的经纬度信息。西藏飞蝗的分布数据通过以下方式获得：(1)实地考察,四川境内的采样点多为实地考察获得,调查点主要位于西藏飞蝗高发区的甘孜州和阿坝州,发现西藏飞蝗若虫或成虫即记为“存在”,GPS 记录经纬度。（2)查询物种分布数据库。本研究查询的数据库包括"国际农业与生物科学中心（CABI,http://www.cabi.org/）”数据库、“全球物种多样性信息库（GBIF,htp://www.gbif.org/）”、中国西南地区动物资源数据库(htp://www.swanimal.csdb.cn）、教学标本资源共享平台 $\mathrm { ' h t t p : / / m n h . s c u . e d u . c n / }$ 。（3)检索国内外公开发表的西藏飞蝗相关的期刊论文。数据处理：采用缓冲区分析法对获得的分布点进行校对、筛选,排除空间关联性较大造成的过拟合模拟的影响,由于环境变量空间分辨率为2.5 arc-minutes（约 $4 . 5 ~ \mathrm { k m } ^ { 2 }$ ),故设置缓冲半径为 $1 . 5 \ \mathrm { k m }$ ,当分布点之间距离小于 $3 ~ \mathrm { k m }$ 时,只保留其中一点,共获得分布点47个,通过Google earth 确定每个分布点的经纬度。参照 MaxEnt软件操作手册,将经纬度坐标输人Excel,保存格式为 $*$ .CSV,字段包括物种名称、经度和纬度[29]。由于西藏飞蝗生活在交通不便、气候恶劣的高海拔地区,所获得的分布点很难完全覆盖其实际分布。研究表明,在样本量很小的情况下,MaxEnt 模型较其他模型预测效果更好、准确性更高,更适用于小样本数据的预测。

http ://www.ecologica.cn

# 1.2 预测环境变量

# 1.2.1环境变量数据来源

本研究所用的环境因子均来源于Worldclim气候数据库,数据是以全球的气象记录信息为基础数据,整合插值生成的全球气候栅格数据[30]。利用 ArcGIS 软件提取研究区（西藏、四川、云南、贵州和青海）19 个生物气候因子（具有较强的生物学意义,可反映温度与降水的特点及季节性变化特征）、月平均降水量、月平均最高及最低气温等气候指标数据。另外还选取了海拔数据作为地形因子(表1)。上述数据的空间分辨 2.5arc-minutes（约 $4 . 5 ~ \mathrm { k m } ^ { 2 }$ ）。

表1西藏飞蝗潜在地理分布的评价指标  
Table1Climatic variablesused for predicting potential geographic distributionof Locusta migratoriatibetensis   

<html><body><table><tr><td>变量及描述 Variables and description</td><td>单位 指标意义 Unit</td><td>Significance of variables</td></tr><tr><td>Bio1=年平均气温 Annual Mean Temperature</td><td>℃</td><td>反映平均温度及其变异幅度</td></tr><tr><td>Bio2=平均日较差 Mean Diurnal Range(Mean of monthly（max temp-min temp)</td><td>℃</td><td>反映温差特点</td></tr><tr><td>Bio3=等温性 Isothermality（BIO2/BIO7）（* 100）</td><td>%</td><td>反映温差特点</td></tr><tr><td>Bio4=温度季节性变化标准差 Temperature Seasonality（standard deviation * 100)</td><td>℃</td><td>反映平均温度及其变异幅度</td></tr><tr><td>Bio5=最暖月最高温度 Max Temperature of Warmest Month</td><td>℃</td><td>反映极端温度的影响</td></tr><tr><td>Bio6=最冷月最低温度 Min Temperature of Coldest Month</td><td></td><td>反映极端温度的影响</td></tr><tr><td>Bio7=年均温变化范围 Temperature Annual Range （BIO5-BIO6)</td><td>C</td><td>反映温差特点</td></tr><tr><td>Bio8=最湿季度平均温度 Mean Temperature of Wettest Quarter</td><td></td><td>反映水热是否同步</td></tr><tr><td>Bio9=最干季度平均温度 Mean Temperature of Driest Quarter</td><td>C</td><td>反映水热是否同步</td></tr><tr><td>Bio10=最暖季度平均温度 Mean Temperature of Warmest Quarter</td><td>℃</td><td>反映极端温度的影响</td></tr><tr><td>Biol1=最冷季度平均温度 Mean Temperature of Coldest Quarter</td><td>℃</td><td>反映极端温度的影响</td></tr><tr><td>Bio12=年降水量 Annual Precipitation</td><td>mm</td><td>反映降雨量及季节性分布</td></tr><tr><td>Bio13=最湿月降水量 Precipitation of Wettest Month</td><td>mm</td><td>反映极端水分条件</td></tr><tr><td>Bio14=最干月降水量Precipitation of Driest Month</td><td>mm</td><td>反映极端水分条件</td></tr><tr><td>Bio15=降水量变异系数Precipitation Seasonality（Coefficient of Variation）</td><td>%</td><td>反映降雨量及季节性分布</td></tr><tr><td>Biol6=最湿季度降水量Precipitationof Wettest Quarter</td><td>mm</td><td>反映极端水分条件</td></tr><tr><td>Bio17=最干季度降水量 Precipitation of Driest Quarter</td><td>mm</td><td>反映极端水分条件</td></tr><tr><td>Bio18=最暖季度降水量 Precipitation of Warmest Quarter</td><td>mm</td><td>反映水热是否同步</td></tr><tr><td>Bio19=最冷季度降水量 Precipitation of Coldest Quarter</td><td>mm</td><td>反映水热是否同步</td></tr><tr><td>Alt=海拔高度Altitude</td><td>m</td><td>反映海拔差异</td></tr><tr><td>Tmin=月平均最低温度 Minimum temperature</td><td>℃</td><td>反映平均温度的影响</td></tr><tr><td>Tmax=月平均最高温度 Maximum temperature</td><td>℃</td><td>反映平均温度的影响</td></tr><tr><td>Tmean=月平均温度 Mean temperature</td><td>℃</td><td>反映平均温度的影响</td></tr><tr><td>Prec=月平均降雨量Precipitation</td><td>mm</td><td>反映平均雨量的影响</td></tr></table></body></html>

# 1.2.2影响西藏飞蝗潜在分布关键环境变量的筛选

影响物种分布的环境因子多种多样,包括气候因子、土壤因子、植被分布等,本文中选取了worldclim 提供的24个环境变量构建初始模型。初始模型构建过程中选择 MaxEnt 软件中的刀切法(jackknife test)检验来测定环境变量对模型预测的贡献大小,以此剔除对 MaxEnt 模型预测结果贡献较小的环境变量,对贡献较大的关键限制因子进行 Spearman 相关分析,提高模型模拟的精度,在此基础上重建西藏飞蝗分布的最大熵模型,并对模拟结果进行准确性评价[31]。

刀切法检验使用MaxEnt 软件,Spearman 相关分析使用 Spss 分析软件。

# 1.3MaxEnt模型的操作与结果评价

MaxEnt 模型来源：选用基于最大熵理论的 MaxEnt模型软件来预测西藏飞蝗在中国的适生区分布,该软件可在 MaxEnt 主页（htp://www.cs.princeton.edu/～schapire/maxent/）上免费获取[32],当前最新版本为

3.3.3k版。

MaxEnt模型的使用：将上述1.1中47个西藏飞蝗分布点数据和1.2中的环境因子数据添加到软件中，随机选取 $7 5 \%$ 的西藏飞蝗分布点作为训练集(trainingdata)建立预测模型,剩余 $2 5 \%$ 的西藏飞蝗分布点作为测试集（testdata)验证模型,选择刀切法(jackknife test)测定各变量权重,选择创建环境变量响应曲线,其余参数均选择模型的默认值[33]。

本研究采用受试者工作特征曲线（Receiver Operating Characteristic Curve,ROC 曲线）下面积值,即 AUC值（Area Under Curve，AUC）为判据来评价模型模拟结果。ROC 曲线,又称为感受性曲线,该曲线根据 $\bar { }$ 系列不同的二分类方式,分别以假阳性率(1-特异率)和真阳性率(1-遗漏率)为横纵坐标绘制而成,曲线下面积值即 AUC 值,取值范围为[0,1],AUC 值越接近1表明环境变量与分布模型之间相关性越大,预测结果精度越高[34]。ROC 曲线可使用 Spss分析软件获得,本研究中 MaxEnt 模型可自动生成ROC 曲线,并给出相应的AUC 值。具体评价标准[35-36]见表2。

表2AUC评价标准表  
Table 2The evaluation criterion of AUC   

<html><body><table><tr><td>AUC取值范围 Range of AUC values</td><td>评价标准 Evaluation criterion</td><td>AUC取值范围 评价标准 Range of AUC values Evaluation criterion</td></tr><tr><td>0.5≤AUC<0.6</td><td>失败</td><td>0.8≤AUC<0.9 好</td></tr><tr><td>0.6≤AUC<0.7</td><td>较差</td><td>0.9≤AUC<1.0 极好</td></tr><tr><td>0.7≤AUC<0.8</td><td>一般</td><td></td></tr></table></body></html>

AUC:ROC 曲线下面积值,即 Area Under Curve

# 1.4西藏飞蝗适生等级分区

MaxEnt模型输出结果为西藏飞蝗在世界范围内的存在概率,数据为ASCⅡ格式，首先使用ArcGIS 的ArcToolbox 的格式转换工具,将该数据转为Raster 格式,使该结果可在 ArcGIS 中显示,而后使用“提取分析"功能得到该虫在中国的存在概率分布图[3738]。MaxEnt软件模拟输出的结果值在0—1之间，值越接近1表示物种越可能存在。参考 IPCC报告[39]关于评估可能性的划分方法,结合西藏飞蝗的实际情况,利用“Reclassify”功能,划分分布值等级及相应分布范围,并使用不同颜色表示,划分标准为：存在概率 $< 0 . 0 5$ 为不适生区； $0 . 0 5 \leqslant$ 存在概率 $< 0 . 3 3$ 为低适生区; $0 . 3 3 \leqslant$ 存在概率 $< 0 . 6 6$ 为中适生区;存在概率 ${ \geqslant } 0 . 6 6$ 为高适生区。

# 2研究结果

2.1主导环境因子筛选及模型检验

# 2.1.1影响西藏飞蝗潜在分布主导环境变量筛选

MaxEnt 模型预测过程中需使用物种空间分布点数据和环境变量数据,并不是每个环境变量对物种潜在分布预测都是必需的,因此需要剔除对 MaxEnt 模型预测结果贡献较小的环境变量,筛选得到贡献较大的关键限制因子[40]。本研究参考雷军成等[4-2]方法,利用 MaxEnt 软件本身提供的模块,即刀切法测定变量的重要性,通过比较每个环境变量对模型结果的影响程度来剔除影响较小的变量,最终获得对模型模拟贡献率较大的变量作为主导变量。本研究中,依据 MaxEnt的运算结果,不同环境变量对西藏飞蝗潜在分布的累积贡献率见表3。海拔高度为限制西藏飞蝗分布的主要变量,单因子贡献率达到了 $5 2 \%$ ,其次,8月份平均雨量、1月份平均雨量、等温性、1月份平均温度、12月份平均温度和2月份平均温度对西藏飞蝗潜在分布的累积贡献率为$4 2 . 6 \%$ 。

本研究使用 Spearman 相关系数法计算7个环境因子之间的相关性,以消除共线性对模型建模过程和结果解释的影响,环境因子之间的相关系数绝对值大于 $0 . 8 ^ { [ 4 3 - 4 4 ] }$ ,则认为两者具有很强的相关性。由表4可以看出,7个环境因子两两之间相关系数均未超过0.8,因此本研究选定上述7种环境变量作为影响西藏飞蝗分布的主导变量,在此基础上重建西藏飞蝗在中国的分布的最大熵模型,并进行模拟结果的精度评价,以获得最

优秀的预测模型。

表3影响西藏飞蝗分布的环境变量贡献百分率和累积贡献百分率  
Table3ThecumulatedcontrbutionofachenvironmentalvarabletotepotentialdistrbutionfLocustamigratoriatietesisdefie   

<html><body><table><tr><td>环境变量 Environmental variables</td><td>贡献百分率 Percent contribution/%</td><td>累积贡献百分率 Accumulated percent contribution/%</td></tr><tr><td>海拔(Altitude，Alt)</td><td>52</td><td>52</td></tr><tr><td>8月份平均雨量(Average precipitation in August，Prec8)</td><td>17.3</td><td>69.3</td></tr><tr><td>1月份平均雨量(Average precipitation in January，Prec1)</td><td>5.9</td><td>74.2</td></tr><tr><td>等温性（Isothermality，Bio3）</td><td>13</td><td>87.2</td></tr><tr><td>1月份平均温度(Average mean temperature in January，Tmean1)</td><td>3.4</td><td>90.6</td></tr><tr><td>12月份平均温度(Average mean temperature in December，Tmean12)</td><td>2.5</td><td>93.1</td></tr><tr><td>2月份平均温度(Average mean temperature in February，Tmean2)</td><td>1.5</td><td>94.6</td></tr></table></body></html>

累积贡献百分率为贡献百分率之和

byMaxEnt   
表4环境因子之间的 Spearman 相关系数  
Table 4Pair-wise Spearman's correlation coefficients of environmental variables   

<html><body><table><tr><td>环境因子</td><td>Alt</td><td>Bio3</td><td>Prec1 Prec8</td><td>Tmean1</td><td>Tmean2</td></tr><tr><td>Bio3</td><td>0.215 *</td><td></td><td></td><td></td><td></td></tr><tr><td>Prec1</td><td>0.134 *</td><td>0.431*</td><td></td><td></td><td></td></tr><tr><td>Prec8</td><td>0.15 *</td><td>0.612 *</td><td>0.36 *</td><td></td><td></td></tr><tr><td>Tmean1</td><td>0.017</td><td>0.196 *</td><td>0.115 * 0.155 *</td><td></td><td></td></tr><tr><td>Tmean2</td><td>0.072 *</td><td>0.262 *</td><td>0.142 * 0.192 *</td><td>0.287 *</td><td></td></tr><tr><td>Tmean12</td><td>0.049</td><td>0.28 *</td><td>0.158* 0.196 *</td><td>0.323 *</td><td>0.023</td></tr></table></body></html>

Alt:海拔,Altitude;Bio：等温性,Isothermalty;Prel:1月份平均雨量,AveragepreciptationinJanuary;Prec88月份平均雨量,verage preciptationinAugust;meanl;1月份平均温度,AveragemeantemperatureinJanuary;mean2:2月份平均温度,Averagemeantemperature in February;Tmean12:12月份平均温度,Average mean temperature in December; $^ *$ 表示在 $\alpha = 0 . 0 5$ 水平上显著相关

# 2.1.2ROC曲线和AUC值对模型准确性检验

图1是 MaxEnt 模型模拟输出的ROC曲线图,图中表明基于所有环境变量和主导环境变量构建的西藏飞蝗在中国的地理分布模型的AUC 值分别为0.996 和0.993,依据表1的AUC 值评价标准表,本次构建模型的预测准确性达到“极好"的标准,说明此结果可用于研究西藏飞蝗的适生区划。

![](images/166d4828c0b40d72102a98a0a87fcf36e0f00f9116c07b31560787286de46cde.jpg)  
图1模型适用性检验AUC值  
Fig.1AUC value of test on applicability of the MaxEnt model

A代表基于所有环境变量计算的ROC曲线，B代表基于主导环境变量ROC曲线

# 2.2 西藏飞蝗在中国的地理分布的预测

根据7个主导环境变量与西藏飞蝗的分布数据构建的最大熵模型模拟结果，按照高适生区、中适生区、低适生区和不适生区4个等级标准划分，最终获得西藏飞蝗在中国的适生区划图(图2）。预测结果显示，西藏飞蝗在当代气候条件下预测的适生区范围为 $8 8 . 7 9 ^ { \circ }$ 一$1 1 3 . 5 7 ^ { \circ } \mathrm { E } , 2 1 . 5 2 ^ { \circ } - 3 8 . 3 3 ^ { \circ } \mathrm { N } .$ 。其中高适生区主要位于四川和西藏两省区，包括四川的甘孜州，西藏的昌都地区、林芝地区、山南地区和拉萨市。中适生区沿高适生区周围分布，主要集中青藏高原东部地区，包括四川西部、西藏东部、云南北部等地。

西藏飞蝗当代适生区总面积为 $1 7 0 . 5 5 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ ，占中国国土面积的 $1 7 . 7 7 \%$ 。其中，高、中、低适生区面积分别为 $2 2 . 5 1 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ） $6 3 . 0 4 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ 和 $8 5 . 0 1 \times 1 0 ^ { 4 }$ $ { \mathrm { k m } } ^ { 2 }$ ,分别占总适生区面积的 $1 3 . 2 \%$ ） $3 6 . 9 6 \%$ 和 $4 9 . 8 4 \%$ 。四川和西藏高适生区面积最大,分别为 $1 0 . 1 9 \times 1 0 ^ { 4 }$ $\mathrm { k m } ^ { 2 }$ 和 $1 1 . 0 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ （表5）。

![](images/17b5b337f9a9b69478b6bc258248688c85f7e79e5680c0de291a3ac74a34ee8a.jpg)  
图2基于MaxEnt模型预测的西藏飞蝗在中国的适生分析图 Fig. 2 Potential suitabledistributionof Locusta migratoria tibetensis in China based on MaxEnt model

# 2.3西藏飞蝗地理分布与环境变量之间的关系

# 2.3.1刀切法检验结果

刀切法检验结果可反映不同环境变量对于分布增益的贡献大小，该方法分别计算“仅此变量”、“除此变量”和“所有变量”模拟时的训练得分情况，判定标准为：“仅此变量"时得分较高，说明该因子具有较高的预测能力，对物种分布贡献较大；“除此变量”时模型训练得分能力降低较多，说明该变量具有较多的独特信息，对物种分布较为重要。图3为使用MaxEnt软件自带的刀切法分析各环境变量对西藏飞蝗分布重要性的结果图，由图中可见海拔(Alt)是影响西藏飞蝗分布的关键环境变量，其训练增益超过2.5;等温性(Bio3)也是较为重要的环境变量,其单独训练得分超过1.5;另外5种主导变量的重要性排序为2月份平均温度（Tmean2） $> 1$ 月份平均温度（Ttmeanl) $> 1 \bar { 2 }$ 月份平均温度(Tmean12) $^ { > 1 }$ 月份平均雨量 $ { \left( \mathrm { P r e c } 1 \right) } > 8$ 月份平均雨量（Prec8）,这5 种环境变量的训练得分也均超过1.0。

![](images/a8a177372c7b3f62c29b5f1aefe4bd56390300a8d6caf183fc01b6b1f9c66d07.jpg)  
图3环境变量对西藏飞蝗分布的重要性(jackknife)Fig.3Importance ofenvironmental variablesto Locustamigratoriatibetensisbyjackknifeanalysis

# 2.3.2 环境变量对MaxEnt模型预测的影响

图4是MaxEnt模型绘制的主导环境变量与分布概率之间的反馈曲线,该图可反映不同阈值下环境变量的取值范围。参照1.4中的分级方法,本文以0.33为阈来划分适合西藏飞蝗分布的环境变量的范围。结果显示,海拔的适宜范围为 $2 8 7 0 { \mathrm { - } } 5 1 8 8 { \mathrm { ~ m } }$ ,最适高度为 $3 9 4 1 \mathrm { ~ m ~ }$ ,海拔2870- $3 9 4 1 \mathrm { ~ m ~ }$ 时,分布概率随海拔升高而增加，3941— $5 1 8 8 \mathrm { ~ m ~ }$ 时,随海拔升高而降低。等温性的适宜值为38.5—47.2,最适值为42.9,在38.5—42.9,随等温性上升分布概率增大,在42.9—47.2时,随等温性升高分布概率降低。1、2、12月份平均温度和8月份平均雨量与分布概率之间的反馈曲线的变化趋势与上述2种变量类似,只是在变化幅度及取值范围存在差异,具体见表6。在适宜范围内,各主导环境变量的变化对西藏飞蝗的存在概率均有一定的影响,而取值在适宜范围之外时对该虫分布影响的概率逐渐减小。

Table 5Predicted areas for Locusta migratoria tibetensis under current climatic condition   

<html><body><table><tr><td rowspan="2">省份</td><td colspan="2">不适生区 No suitable area</td><td colspan="2">低适生区 Lowly suitable area</td><td colspan="2">中适生区 Moderately suitable area</td><td colspan="2">高适生区 Highly suitable area</td></tr><tr><td>预测面积/ ×104 km² Predicted area</td><td>占该省 面积比例/% Account for th prear iht province</td><td>预测面积/ ×104 km² Predicted area</td><td>占该省 面积比例/% Account for th rear iht province</td><td>预测面积/ ×104 km² Predicted area</td><td>占该省 面积比例/% Account for th preartihlt province</td><td>预测面积/ ×104km² Predicted area</td><td>占该省 面积比例/% Account for th prpeaih province</td></tr><tr><td>四川</td><td>6.15</td><td>13.51</td><td>11.03</td><td>24.23</td><td>18.14</td><td>39.86</td><td>10.19</td><td>22.40</td></tr><tr><td>西藏</td><td>30.92</td><td>31.45</td><td>25.12</td><td>25.55</td><td>31.22</td><td>31.76</td><td>11.05</td><td>11.24</td></tr><tr><td>云南</td><td>5.33</td><td>15.57</td><td>19.41</td><td>56.73</td><td>8.22</td><td>24.03</td><td>1.26</td><td>3.67</td></tr><tr><td>贵州</td><td>9.78</td><td>61.35</td><td>5.50</td><td>34.51</td><td>0.66</td><td>4.14</td><td>0.00</td><td>0.00</td></tr><tr><td>青海</td><td>42.58</td><td>59.70</td><td>23.94</td><td>33.57</td><td>4.80</td><td>6.73</td><td>0.01</td><td>0.01</td></tr></table></body></html>

![](images/f48fa30a9bd79ffc026a9344b0f86aa0f9c7ed0cba3578a1e2075e314f8a252a.jpg)  
图4MaxEnt模型中研究物种对各环境变量的反馈曲线  
Fig.4Response of curves of environmental variables in MaxEnt models

表5西藏飞蝗在当代气候条件下的适生区面积预测  
表6西藏飞蝗潜在分布对应的环境变量适宜范围表  

<html><body><table><tr><td>环境变量 Environmental variables</td><td>适宜范围 Suitable range</td><td>最适值 Optimum value</td></tr><tr><td>海拔 Altitude</td><td>2870—5188</td><td>3941</td></tr><tr><td>等温性 Isothermality</td><td>38.5—47.2</td><td>42.9</td></tr><tr><td>1月份平均雨量 Average precipitation in January</td><td>0-9.35</td><td>3.56</td></tr><tr><td>8月份平均雨量 Average precipitation in August</td><td>79.7-296</td><td>98.2</td></tr><tr><td>1月份平均温度 Average mean temperature in January</td><td>-13.3-6.73</td><td>-3.1</td></tr><tr><td>12月份平均温度 Average mean temperature in December</td><td>-12.12-7.13</td><td>-2.13</td></tr><tr><td>2月份平均温度 Average mean temperature in February</td><td>-11.18-8.78</td><td>-1.51</td></tr></table></body></html>

# 3讨论

研究表明[45],环境变量的选择会对生态位模型的预测结果造成一定的影响。应用 MaxEnt模型预测物种地理分布的很多研究,采用世界气候数据库(htp://www.worldclim.org）的 Bioclim 数据集中的19 个生物气候因子作为全部或主要环境变量。19个环境变量是以温度和雨量为基础数据,根据不同需求计算演生而来，因此这些变量之间存在不可避免的自相关及多重线性重复等问题[4-47]。研究业已证实,这些高度相关的变量在模型预测过程中会引入冗余信息,影响预测结果。在建模过程中,为避免上述问题,应首先对环境变量进行相关分析和有效筛选。本研究中,参考孙敬松等[48-50]方法,以各因子对物种分布的贡献率来评价变量的重要性,有效剔除了贡献率较小的环境变量并对筛选的变量进行了相关性分析,获得了7种主导环境变量并对模型进行重建,减少了冗余信息对模拟结果的影响,提高了预测结果的准确性。

目前对模型精度评价应用最广泛的方法为ROC 曲线法（即 AUC 法）[51],由于AUC 不受诊断阈值的影响,并可提供所有阈值范围上的性能评价结果,因此目前被公认为生态位模型评价领域的最佳评价指标。AUC 的取值范围在0.5—1,值越接近于1模型精度越高。本研究中基于主导环境变量的模拟的训练集AUC平均值为0.993（非常接近1),预测结果达到"极好”水平,说明此次模型预测的地理分布与西藏飞蝗实际分布拟合度较高。另外，本研究利用地理信息系统软件ArcGIS对MaxEnt输出的栅格文件进行后期处理，使目标物种的分布数据与环境变量数据在栅格单元上相对应,有效的降低了系统误差,进一步提高了数据的准确性。

本研究预测结果显示,西藏飞蝗在中国的适生范围为 $8 8 . 7 9 ^ { \circ } - 1 1 3 . 5 7 ^ { \circ } \mathrm { E } , 2 1 . 5 2 ^ { \circ } - 3 8 . 3 3 ^ { \circ } \mathrm { N }$ ，总面积达$1 7 0 . 5 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。其中高适生区主要位于四川和西藏两省区，中适生区则主要集中青藏高原东部地区,包括四川西部、西藏东部、云南北部等地。上述区域地理上包含了四川的多数草原(若尔盖草原、红原草原、塔公草原、龙灯草原和毛垭草原等)以及西藏雅鲁藏布江及雅袭江河谷。李庆等[3]研究发现,西藏飞蝗在草地环境下产卵块数最多、草地环境更适合其生活,西藏飞蝗可对草地造成严重危害。因此西藏飞蝗在上述地区的危险系数极高,有关部门应引起高度重视,严防西藏飞蝗聚集成灾。封传红等[52]建立了有效积温与地理位置的模型,获得了西藏飞蝗的潜在分布面积,结果表明,1998 年西藏飞蝗分布面积最大,为 $1 4 . 3 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。本文中高适生区面积为 $2 2 . 5 1 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,中适生区面积则达 $6 3 . 0 4 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,与封传红的研究结果相差较大,这可能是因为使用的模型及变量不同所导致。

物种-环境关系是研究物种生态学需求和空间分布的重要方面,本研究分析了西藏飞蝗存在概率与主导环境变量之间的关系,获得了相关的反馈曲线。结果表明,西藏飞蝗的存在概率随着主导环境变量(海拔、等温性、1月份及8月份平均雨量、1月份2月份及12月份平均温度)的变化而改变。7个主导变量中,海拔和等温性是影响该虫分布最为重要的环境变量,表明西藏飞蝗扩散和繁殖过程中，一方面受当地海拔范围的制约,另一方面也受当地等温性的影响。本研究中西藏飞蝗适宜的海拔范围为 $2 8 7 0 { \mathrm { - } } 5 1 8 8 { \mathrm { m } }$ ,最适为 $3 9 4 1 \mathrm { ~ m ~ }$ 。目前已知西藏飞蝗的分布范围仅限于青藏高原地区,王思忠等[53]虽曾在四川雅安（海拔 $5 6 0 \mathrm { ~ m ~ }$ 左右)室内成功饲养繁殖,但死亡率高,且众多研究证明至今未发现该虫在低海拔地区分布,这与本实验的结果相吻合。等温性反映了温度变化的迟早及幅度,如当年气温转变迟缓,则利于西藏飞蝗的胚胎发育,西藏飞蝗存在概率较高的等温性指标在42.9左右,这表明该虫在温差较大情况下存在概率较高,这与上述的研究结果相近。李庆等研究了西藏飞蝗各发育阶段的耐寒性,结果表明卵期的过冷却点为 $- 2 2 . 0 2 9 \mathrm { C } \ , 4$ 龄蝗螨的过冷却点为$- 6 . 4 6 ^ { \circ } \mathrm { C }$ ,西藏飞蝗以卵越冬。西藏飞蝗蝗卵越冬期长达 $2 0 0 \textup { d }$ ,冬季低温会影响其胚胎发育及孵化率。封传红等[54]研究发现,温度为限制西藏飞蝗分布的主要限制因子,夏季高温不是限制因素,冬季低温可影响西藏飞蝗的安全越冬，这些都说明冬季低温对蝗卵的越冬至关重要，本研究认为西藏飞蝗的存在概率与越冬期12月及次年1、2月平均温度有关,在较低的温度条件下,该虫仍有较高的存在概率,但过低的温度将导致其存在概率下降;8月份平均雨量也是影响西藏飞蝗分布的重要因素,最适值为 $9 8 . 2 \ \mathrm { m m }$ 。研究发现,西藏飞蝗与飞蝗其他亚种类似,主要栖居在较低湿的禾本科杂草地带,该虫一般在8月开始交配、产卵,适宜的湿度有利于该虫顺利的完成这些生命活动。此处需要注意,物种存在概率对环境变量的反馈曲线反映的是单一环境变量的作用,但昆虫的生命活动受到各种环境变量(包括气候因子、寄主条件、天敌种类、植被条件等)的综合影响,因此此结果可作为判断西藏飞蝗与环境变量之间关系的参考,但不能完全准确解释二者之间的关系。

尽管 MaxEnt模型预测具有操作简便、样本需求量小和预测精度高等优势,但同其他生态位预测模型类似不可避免的存在一定的局限性。（1)用MaxEnt模型进行预测时所涉及的环境变量除海拔外,其余变量均为气候变量,19个生物气候变量为西藏飞蝗实际分布地的气候极值,即最大值和最小值,因而,MaxEnt模型所显示的是物种分布的最大可能性,无法准备表达物种在现实分布的主要地区。上述预测结果更侧重于理解和展现西藏飞蝗潜在地理分布以及揭示适于该物种分布的气候特征。（2)基础生态位是一种理想生态位,指某一物种在理想的生存条件而不存在其他物种竞争时所占据的最大生态位,该理论只需考虑非生物因素的影响[55]。MaxEnt模型对适生区的预测就是基于物种对基础生态位的需求,但在实际的生存环境中,生物因子(如物种之间的相互作用、植被类型、地貌特征、物种自身扩散能力和土壤类型等)同样会对预测物种的潜在分布产生重要影响[56]。例如,李庆等[3]研究了植被及土壤对西藏飞蝗产卵及分布的影响,结果表明,植被类型、土壤含盐量、含水量和PH值能显著影响西藏飞蝗的产卵及分布。基于上述原因,可以推测,MaxEnt 模型预测的生态位比西藏飞蝗所占据的实际生态位要宽。对此,在下一步工作中,除考虑气候因素影响外,还应注重考量物种间相互作用等生物因子的可信表达,以改善模型的预测效果。（3)过去30年来,随着温室气体的不断排放和保持,全球气候正异常变暖,而气候变化会引起物种生长及分布格局的变化[57-59]。本研究中所使用的环境变量来源于世界气候数据库 worldclim,时间跨度为1950—2000s,缺失了近期10 多年的气候数据。因此,在以后的工作中,应充实缺失的数据,使预测结果更为准备可靠。

# 参考文献（References）:

[1］陈永林.飞蝗新亚种—西藏飞蝗 Locusta migratoria tibetensis subsp.n.昆虫学报，1963,12(4)：463-475.  
[2］朱昱翰，李庆，杨刚，白马吞珠,匡健康，蒋春先，王海建，杨群芳.低温和光周期对西藏飞蝗体内物质的影响.应用生态学报,2016,27(2):629-633.  
[3］李庆，廖志昌，杨刚，封传红，杨群芳，罗怀海，蒋春先，王海建．植被及土壤对西藏飞蝗产卵的影响.中国农业科学,2012，45（4)：656-665.  
[4］陈永林.蝗虫和蝗灾.生物学通报，1991，26(11)：9-12.  
[5］李庆，吴蕾，杨刚，匡健康,封传红，罗怀海，杨群芳,蒋春先，王海建.温度和紫外辐射胁迫对西藏飞蝗抗氧化系统的影响.生态学报，2012，32(10):3189-3197.  
[6］王翠玲，姚小波，覃荣，席永士，王保海，王文峰，扎罗，王考昌.西藏飞蝗的发生规律与综合防治技术探讨.西藏农业科技，2008，30(4):34-40.  
[7］许仲林，彭焕华，彭守璋.物种分布模型的发展及评价方法.生态学报，2015，35(2）：557-567.  
[8］朱耿平，刘国卿，卜文俊，高玉葆.生态位模型的基本原理及其在生物多样性保护中的应用.生物多样性，2013,21（1）：90-98.  
[9］张琳娜，樊隽轩，Melchin MJ，陈清，Wu SY,GoldmanD,MitchellC M,ShetsHD.物种分布模型在古生物学研究中的应用.古生物学报，2013,52(2) : 146-160.  
[10］吴庆明，王磊，朱瑞萍，杨宇博，金洪阳，邹红菲.基于MAXENT 模型的丹顶鹤营巢生境适宜性分析——以扎龙保护区为例.生态学报，2016，36(12) : 3758-3764.  
[1]AnersonR，RazaA.efectofteetentofthesudyegiooGSodelsofspeciesgeogahicdisributiosadstiatesofceevolution：preliminarytestswithmontanerodents（genusNephelomys）inVenezuelaJoualofiogeogaphy，Oo,37（7）：78-1393.  
[12] 张路.MAXENT最大熵模型在预测物种潜在分布范围方面的应用.生物学通报，2015，50(11）：9-12.  
[13] 李国庆，刘长成，刘玉国，杨军，张新时，郭柯.物种分布模型理论研究进展.生态学报，2013，33（16)：4827-4835.  
[14］Narouei-Khandan HA,Halbert SE,Worner SP,van Bruggen A $\mathrm { ~ H ~ C ~ }$ .Global climate suitability of citrus huanglongbing and its vector,the Asiancitrus psylldusingtooeatiesesdistrbuionodelingappoacs，ipsishUEuroanJualofanttolog2016,144(3):655-670.  
[15]DeMeyerobertsonM,MansellW,EkesiS，urutaK,MwakWVaysieresJF,PetersoATEcologicalnichedotetilgeographicdistroofiitfds（ipte）lioala：35-48.  
[16]Herndez-BazF,RomoH,GonzlezJM,deJesusM,HerndezM,GmezPastranaRMaximumentropyniche-basedmodeling（axent）ofpotentialgeogaicaldistributionoforeuralbicosta（Lepidoptera：Erebidae：Cteuchna）inexicoFlridaEntomologist，O99（）：376-380.  
[17]GillaneaoFfrcadobebiatiailitoasetwoelsooutUdoutClfldGeography，2016，76：14-21.  
[18]Bss,DbaoistiG,Zina，ussDdlghtohtsateaepotetialirtioXllfastidiosa in the Mediterranean basin.Biological Invasions,2016,18(6）：1759-1768.  
[19］齐国君，高燕，黄德超，吕利华.基于 MAXENT的稻水象甲在中国的入侵扩散动态及适生性分析.植物保护学报，2012，39（2)129-136.  
[20］杨会枫，郑江华，吴秀兰，穆晨，林俊，许仲林.基于MaxEnt 模型的西伯利亚蝗虫在新疆潜在分布预测研究.新疆农业科学，2016，53(1): 43-50.  
［21］李宗亮，于向鹏，陆晨晨，金海如.基于物种预测分布模型对桔小实蝇在全球适生区的评估.浙江师范大学学报：自然科学版，2011，34(2):207-210.  
[22］冯益明，刘洪霞.基于 Maxent 与GIS 的锈色棕榈象在中国潜在的适生性分析.华中农业大学学报，2010,29(5)： 552-556.  
[23] 董丹丹，刘崇怀，樊秀彩，孙海生，张国海，王忠跃.葡萄根瘤蚜在中国的风险性分析.植物检疫，2011,25(1)：21-26.  
[24] 赵文娟，陈林，丁克坚，段霞瑜，周益林.利用MAXENT预测玉米霜霉病在中国的适生区，植物保护，2009，35（2）：32-38.  
[25] 曹学仁，陈林，周益林，段霞瑜.基于 MaxEnt 的麦瘟病在全球及中国的潜在分布区预测.植物保护，2011，37（3）：80-83.  
[26] 韩阳阳，王焱，项杨，叶建仁.基于Maxent 生态位模型的松材线虫在中国的适生区预测分析.南京林业大学学报：自然科学版，2015，39(1) : 6-10.  
[27］曾辉，黄冠胜，林伟，梁忆冰，李志红.利用MaxEnt预测橡胶南美叶疫病菌在全球的潜在地理分布.植物保护，2008，34（3）：88-92.  
[28] 杨群芳，廖志昌，李庆，杨刚，封传红，蒋春先.西藏飞蝗食性及其防治指标.植物保护学报，2008，35（5）：399-404.  
[29］叶永昌，周广胜，殷晓洁.1961-2010年内蒙古草原植被分布和生产力变化——基于MaxEnt模型和综合模型的模拟分析.生态学报，2016,36(15): 4718-4728.  
[30］柳晓燕，李俊生，赵彩云，全占军，赵相健，宫璐.基于MAXENT模型和 ArcGIS 预测豚草在中国的潜在适生区.植物保护学报，2016,43(6):1041-1048  
[31]PhilidchelioftConference on Machine Learning. New York: ACM Press， 2004.  
[32］朱耿平，刘晨,李敏，刘强.基于 Maxent和GARP 模型的日本双棘长蠹在中国的潜在地理分布分析.昆虫学报，2014,57（5)：581-586.  
[33］赵晶晶，高丹，冯纪年.基于 MaxEnt模型的葡萄根瘤蚜在中国的适生性分析.西北农林科技大学学报：自然科学版，2015，43（(1)：99-104，112-112.  
[34］王运生，谢丙炎，万方浩，肖启明，戴良英.R0C 曲线分析在评价入侵物种分布模型中的应用.生物多样性，207，15(4)：365-372.  
[35］王雷宏，杨俊仙，徐小牛.基于 MaxEnt 分析金钱松适生的生物气候特征.林业科学,2015,51(1)：127-131.  
[36］赵力，朱耿平,李敏，刘强.入侵害虫西部喙缘蝽和红肩美姬缘蝽在中国的潜在分布.天津师范大学学报：自然科学版，2015，35（1)：75-78. ?  
[37]ElithJ,GraaHCdersoR,keSsanA,jasRJ,HueF,eathwckJR,eaA,L,G,LoiselleBA,ManionG,Moritz C,Nakamura M,NakzawaY，OvertoJ,PetersonAT,hilipsSJ,RchardsnK,Scachet-eraR,SchapireRE，SobernJ，WiliamsS，WiszMS,ZimmermannNE，AraujM.Novelmethodsimprovepredictionofspecies’disributiofrooccurrence data.Ecography,2006，29(2）: 129-151.  
[38]应凌霄，刘哗，陈绍田,沈泽昊.气候变化情景下基于最大熵模型的中国西南地区清香木潜在分布格局模拟.生物多样性,2016,24（4)：453- 461.  
[39]段居琦，周广胜.中国水稻潜在分布及其气候特征.生态学报,2011,31（22）：6659-6668.  
[40] 邢丁亮，郝占庆.最大熵原理及其在生态学研究中的应用.生物多样性，2011，19(3)：295-302.  
[41］雷军成，徐海根，吴军，关庆伟.基于IPCC AR5的我国常绿阔叶林潜在适宜生境变化分析.生态与农村环境学报，2015,31（1)：69-76.  
[42］殷晓洁，周广胜，隋兴华，何奇瑾，李荣平.蒙古栎地理分布的主导气候因子及其阈值.生态学报，2013，33（1)：103-109.  
[43]LemkeD,HuleEroJA，adessWDisributioodellngofJapaseoneyuckle（Loicerajpoica）vasioninebedplateau and mountain region，USA.Forest Ecology and Management，2011,262(2）：139-149.  
[4]YagXQushwahaSPS,SaranS，XuJC,RoyP.Maxentmodelingforpredictigtepotentialditributionofmedicinalplantusticaadhatoda,L.in Lesser Himalayan foothills.Ecological Engineering,2013,51(1)：83-87.[45］陈新美，雷渊才，张雄清，贾宏炎.样本量对 MaxEnt 模型预测物种分布精度和稳定性的影响.林业科学,2012，48（1)：53-59.  
[46］朱耿平，刘强，高玉葆.提高生态位模型转移能力来模拟入侵物种的潜在分布.生物多样性，2014，22（2）：223-230.  
[47］王运生，谢丙炎，万方浩，肖启明，戴良英.应用生态位模型研究外来入侵物种生态位漂移.生态学报，2008，28(10)：4974-4981.  
[48］孙敬松，周广胜.利用最大熵法（MaxEnt)模拟中国冬小麦分布区的年代际动态变化.中国农业气象，2012，33(4)：481-487.  
[49］常志隆，周益林，赵遵田，段霞瑜.基于 MaxEnt 模型的小麦印度腥黑穗病在中国的适生性分析.植物保护，2010，36(3）：110-112,129- 129.  
[50]何奇瑾，周广胜.我国夏玉米潜在种植分布区的气候适宜性研究.地理学报，2011,66(11)：1443-1450.  
［51］宋花玲.ROC 曲线的评价研究及应用[D]．上海：第二军医大学，2006.  
[52］封传红，单绪南，郭聪，罗林明.1961-2005 年西藏飞蝗潜在分布的变化.昆虫学报，2011,54(6)：694-700.  
［53］王思忠.西藏飞蝗生物学特性及耐寒性研究[D].雅安：四川农业大学，2006.  
[54］封传红，王思忠，蒋凡，杨刚，游超，李庆，张敏，罗林明.温度对四川省甘孜州西藏飞蝗分布的影响.植物保护,200,34（1)：67-71.  
[55] 蔡静芸，张明明，粟海军，张海波.生态位模型在物种生境选择中的应用研究.经济动物学报，2014，18(1)：47-52.  
[56］乔慧捷，胡军华，黄继红.生态位模型的理论基础、发展方向与挑战.中国科学：生命科学，2013，43(11)：915-927.  
[57］霍治国,李茂松，王丽，温泉沛，肖晶晶，黄大鹏，王春艳.气候变暖对中国农作物病虫害的影响.中国农业科学，2012，45（10)：1926-1934.  
[58］陈瑜，马春森.气候变暖对昆虫影响研究进展.生态学报，2010，30（8)：2159-2172.  
[59］徐小锋，田汉勤，万师强.气候变暖对陆地生态系统碳循环的影响.植物生态学报，2007,31(2)：175-188.