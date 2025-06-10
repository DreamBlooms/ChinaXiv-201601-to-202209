# 桂北岩溶区与非岩溶区植物叶片含水率高光谱反演

秦佳双¹，顾大形l\*，倪隆康‘，何文¹，阮杨春²，黄玉清²，王权  
(1.广西喀斯特植物保育与恢复生态学重点实验室，广西壮族自治区中国科学院广西植物研究所，中国广  
西 桂林 541006；2.北部湾环境演变与资源利用教育部重点实验室，广西地表过程与智能模拟重点实验室，南宁师范大学，中国 南宁 530001；3．日本静冈大学农学部，日本 静冈 422-8529)

摘要：叶片水分状况是反映植被生理状况的重要指标，构建高普适性的植物叶片含水率高光谱反演模型对准确评价岩溶和非岩溶植被生态功能具有重要意义。以我国西南典型区域内岩溶区与非岩溶区共17种植物694个样品为研究对象，同步测量叶片含水率和反射光谱，采用单波段、差值型、比值型、归一化型等四类光谱指数模型，对反射光谱及一阶导数光谱进行全波段搜索分析。结果表明：光谱指数 $\mathrm { D } _ { 2 0 4 8 ^ { - } } \mathrm { D } _ { 1 7 3 3 }$ 的建模与验证结果均最好，为岩溶植物叶片含水率的最佳估计光谱指数；对于非岩溶植物，光谱指数 $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$ 和$( \mathrm { D } _ { 2 3 5 6 } \mathrm { - D } _ { 1 8 8 5 } ) / ( \mathrm { D } _ { 2 3 5 6 } \mathrm { + D } _ { 1 8 8 5 } )$ 建模与验证结果均相差很小，均可作为叶片含水率最佳估计模型；该研究结果还表明叶片绒毛对岩溶植物叶片含水率反演光谱指数构建影响不大。总体上，新构建的最优光谱指数对岩溶区与非岩溶区植物叶片含水率的拟合效果优于传统指数，具有较好的普适性，可为精准评估桂北地区植被水分状态提供科学依据。

关键词：岩溶区，叶片含水率，光谱指数，高光谱中图分类号： $Q 9 4 5 . 1 7 + 9$ 文献标识码：A

# Hyperspectral inversion of leaf water content at karst and non-karst areas in Northern Guangxi

QIN Jiashuang1,GU Daxing1\*,NI Longkang1,HE Wen', RUAN Yangchun², HUANG Yuqing², WANG Quan³

(1. Guangxi Key Laboratoryof Plant Conservation and Restoration Ecology in Karst Terrain,Guangxi Institute of Botany,Chinese Academy ofSciences,Guilin 541006,Guangxi, China; 2. Guangxi Zhuang Autonomous Region and Chinese Academy of Sciences,Key Laboratory of Earth Surface Processes and Intelligent Simulation,   
Nanning Normal UniversityNanning 5301,China;3.DepartmentofAgriculture,Shizuoka University,hizuoka 422-8529, Japan)

Abstract: Leaf water content is a key indicator that reflects the physiological conditions of vegetation. It is of great significance to construct a highly universal hyperspectral inversion model of the water content of leaves to accurately evaluate the ecological functions of karst and non-karst vegetation. As a result, developing hyperspectral inversion models of leaf water content for karst and non-karst vegetation respectively is becoming more necessary. In total, 694 samples from 17 plant species were taken at karst and non-karst areas in North Guangxi. Leaf water content and reflectance spectrum ranging from $3 5 0 ~ \mathrm { n m }$ to $2 ~ 5 0 0 ~ \mathrm { { n m } }$ of all leaf samples were measured simultaneously. Four model structures including single-band, difference,ratio,and normalized difference were employed in this study.All possible index models with single waves and couple of two waves based on both reflectance spectrum and first derivative spectrum were related to leaf water content for karst and non-karst vegetation respectively. The results were as follows: The spectral index of $\mathrm { D } _ { 2 0 4 8 ^ { - } } \mathrm { D } _ { 1 7 3 3 }$ had the best modeling and verification result, and was the best index model for estimating leaf water content of karst plants; For non-karst plants, the spectral index of $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$ and $\left( \mathrm { D } _ { 2 3 5 6 } – \mathrm { D } _ { 1 8 8 5 } \right)$ / $\left( \mathrm { D } _ { 2 3 5 6 } + \mathrm { D } _ { 1 8 8 5 } \right)$ had similar results,and both of them could be used as the best estimation index of leaf water content; This results also showed that, for karst plants,the leaf fluff had little effect on the construction of inversion model of leaf water content. Generally, the newly constructed optimal spectral index has a better fitting effect on the leaf water content in karst and non-karst areas than the traditional index,and has a good general applicability， which could provide a scientific basis for the accurate assessment of vegetation water state in North Guangxi.

Key word: karst area, leaf water content, spectral index, hyperspectrum

水是植物生长发育的主要组成部分，是光合作用中的反应原料和代谢溶剂（张峰和周广胜,2018)，其在叶片中的含量对外界土壤和大气环境响应敏感，是植物生理状态和生态系统功能评价的关键参数。对植被叶片含水率的快速精确估算，有助于及时了解植物生理状况、植被干旱胁迫程度、森林潜在火灾风险、生态系统功能评价以及农业灌溉与产量评估等（张佳华等,2010; Asner et al., 2016; Luo et al.,2019)。

与传统的叶片含水率测定方法（烘干法）相比，高光谱遥感技术具有获取信息量大、经济、快速、无损等优点，能够迅速准确地连续监测大范围植被水分含量，已成为研究植被含水率的重要工具（吾木提·艾山江等,2019)。目前已有大量研究基于不同方法针对单一作物（Krishna et al.,2019; Sun et al.,2019; Kovar et al.,2019）或单一经济林木（程志庆等,2016;潘庆梅等,2019）构建了有效的叶片水分含量高光谱反演模型。由于不同植物间叶片结构和化学特征等差异会不可避免地引起叶片水分敏感波段的变化（吴见等,2015)，从而导致现有水分光谱指数具有特异性较强和适用性较差等缺点（杨勇等,2011；刘小军等,2012；梁亮等，2013；朱西存等,2014)。同时，基于单一或少量植物构建的反演模型也无法应用到更大尺度。为提高模型在大尺度（群落或生态系统）上的适用性，针对研究地区开发对区域多种植物具有普适性的光谱指数模型显得十分必要。尤其在植物生物多样性丰富的西南地区，构建具有一定普适性的叶片水分高光谱反演模型，对于提高自然植被功能的遥感评价精度具有重要意义。

我国岩溶区分布广泛（袁道先,2009),其中尤以西南地区的连片分布和发育程度最高（蔡运龙,1996)。西南岩溶区特殊的地质结构导致地表土壤持水能力差（黄甫昭等,2019)，因此尽管我国西南地区年降雨量充沛，但相对于相同气候条件下的非岩溶区域，岩溶区植物叶片多具有革质、蜡质、被有绒毛、叶片较厚等旱生特征（倪隆康等,2019)。同时岩溶区土壤的富钙特征，也影响到植被叶片的化学组成（陈洪松等，2013；魏兴琥等,2017)。岩溶区植物的旱生性和钙生性导致其叶片结构和化学特征与非岩溶区植被差异较大，进而可能影响叶片水分含量的敏感波段。而目前植物叶片含水率高光谱反演研究主要集中在农林等经济作物，对岩溶区与非岩溶区自然植被含水量研究未见报道。因此，本研究目的：(1)探究岩溶区与非岩溶区植被叶片含水率反演模型分别构建的必要性；(2)分析不同生境以及叶表结构等对植被含水率反演的影响；(3)针对研究地区开发对区域多种植物具有普适性的叶片水分高光谱反演模型，以期为区域尺度上监测西南生态脆弱区植被生理状况、生态功能评估等提供科学依据。

# 1材料与方法

# 1.1研究区域和实验材料

研究地点位于桂北区域的黄冕桉树人工林( $1 0 9 ^ { \circ } 5 3 ^ { \prime }$ E， $2 4 ^ { \circ } 4 8 ^ { \prime } \mathrm { ~ N ) }$ 、桂林植物园常绿阔叶林 $( 1 1 0 ^ { \circ } 1 7 ^ { \prime } \mathrm { \mathrm { E } }$ ， $2 5 ^ { \circ } 0 1 ^ { \prime } \mathrm { N } )$ 和会仙喀斯特灌丛， $( 1 1 0 ^ { \circ } 1 3 ^ { \prime } \mathrm { ~ E ~ }$ ， $2 5 ^ { \circ } 0 6 ^ { \prime } \mathrm { N }$ 等3个生态定位研究站及其周围相似生境，土壤主要是砂页岩发育而成的红壤。该地区属中亚热带季风气候，年平均气温 $1 9 . 2 ^ { \circ } \mathrm { C }$ ，极端最高气温 $4 0 ~ ^ { \circ } \mathrm { C }$ ，极端最低气温 $. 6 ^ { \circ } \mathrm { C }$ ，年均降雨量 $1 8 6 5 . 7 \mathrm { m m }$ ，主要集中在4—8月，无霜期 $3 2 0 \mathrm { d }$ 以上，年日照时间达 $1 6 9 9 \mathrm { h }$ 以上。选择在岩溶区以及非岩溶区分布的主要乔木和灌木植物共17种为研究对象。于2018年11月至 2019 年11月期间每两个月进行一次采样，每种植物选取至少3片成熟健康叶片装入保鲜袋，并立即放入低温采样箱中带回实验室进行测量。样品总量为694个，物种和样品含水率分布信息见表1。

表1不同区域植物种及其叶片含水率概况  
Table 1 General situation of plant species and leaf water content in different regions   

<html><body><table><tr><td rowspan="2">区域 Region</td><td rowspan="2">物种 Species</td><td rowspan="2">叶表是否有 绒毛 Leaf surface villi</td><td rowspan="2">数量 Number</td><td colspan="2">叶片含水率 Leaf water content (%)</td></tr><tr><td>范围 Range</td><td>均值±标准差 Average±Standard</td></tr><tr><td rowspan="10">岩溶区 Karst area</td><td>茶条木Delavaya toxocarpa</td><td>无No</td><td>26</td><td>0.50~0.80</td><td>deviation 0.61±0.08</td></tr><tr><td>花椒 Zanthoxylum armatum</td><td>无No</td><td>59</td><td>0.52~0.75</td><td>0.63±0.05</td></tr><tr><td>火棘Pyracantha fortuneana</td><td>无No</td><td>37</td><td>0.41~0.67</td><td>0.54±0.08</td></tr><tr><td>九龙藤 Bauhinia championii</td><td>无No</td><td>60</td><td>0.38~0.57</td><td>0.46±0.05</td></tr><tr><td>马甲子Paliurus ramosissimus</td><td>无No</td><td>48</td><td>0.35~0.67</td><td>0.56±0.06</td></tr><tr><td>雀梅藤 Sageretia rugosa</td><td>有Yes</td><td>58</td><td>0.30~0.57</td><td>0.44±0.06</td></tr><tr><td>柞木 Xylosma racemosum</td><td>有No</td><td>48</td><td>0.38~0.71</td><td>0.52±0.06</td></tr><tr><td>青冈栎Cyclobalanopsis glauca</td><td>有No</td><td>59</td><td>0.39~0.53</td><td>0.47±0.03</td></tr><tr><td>樟叶槭 Acer coriaceifolium</td><td>有Yes</td><td>48</td><td>0.28~0.63</td><td>0.50±0.06</td></tr><tr><td>粗糠柴Mallotus philippensis</td><td>有Yes</td><td>47</td><td>0.36~0.56</td><td>0.49±0.04</td></tr><tr><td>幸福树 Radermachera sinica</td><td>无No</td><td>30</td><td>0.48~0.72</td><td>0.62±0.06</td></tr><tr><td rowspan="5">非岩溶区 Non-karst area</td><td>尾巨桉</td><td>无No</td><td>82</td><td>0.38~0.76</td><td>0.57±0.08</td></tr><tr><td>Eucalyptus urophllaxE. grandis 黧蒴锥Castanopsis fissa</td><td>无No</td><td>33</td><td>0.48~0.61</td><td>0.51±0.03</td></tr><tr><td>荷木Schima superba</td><td>无No</td><td>33</td><td>0.48~0.65</td><td>0.55±0.04</td></tr><tr><td>枫香Liquidambar formosana</td><td>无No</td><td>12</td><td>0.52~0.75</td><td>0.59±0.06</td></tr><tr><td>锥栗Castanea henryi</td><td>无No</td><td>14</td><td>0.44~0.60</td><td>0.51±0.05</td></tr></table></body></html>

# 1.2叶片光谱与含水率测定

采用美国ASDFieldSpec 4Hi-Res光谱仪（测定波长范围为 $3 5 0 { \sim } 2 5 0 0 \mathrm { n m }$ ，光谱分辨率最高为 $3 \ \mathrm { n m }$ ）自带光源的叶片夹，夹取叶片样本中间部位（避开叶片主脉）测量叶片反射光谱，对同一样本连续测量3条原始光谱并进行平均处理得到该样本的反射率光谱。在测定过程中，每隔 $5 ~ \mathrm { m i n }$ 进行一次标准白板校正。采用上海梅特勒-托利多国际有限公司的天平（型号为AE240-S，称重范围为 $0 { \sim } 3 2 0 ~ \mathrm { g }$ ，分度值为 $0 . 1 ~ \mathrm { m g }$ ）称量叶鲜重和干重；使用电热鼓风干燥箱（型号为DHG-9030，控温范围为 $1 0 { \sim } 2 0 0 \ \mathrm { ~ \textdegree ~ }$ ，恒温波动范围为 $\pm 1 ~ \mathrm { { ^ { \circ } C } }$ ）进行叶片烘干， $1 0 5 \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ }$ 杀青 $3 0 ~ \mathrm { m i n }$ 后，于 $7 0 \ \mathrm { ~ \textdegree C }$ 烘至质量恒定。叶片含水率 $( \% ) =$ （叶片鲜重一叶片干重）／叶片鲜重 $\times 1 0 0$ 。

# 1.3光谱指数结构

为寻找能准确估算叶片含水率的光谱指数模型，选取四种常用的光谱指数结构进行反演模型构建：单波段、差值型、比值型、归一化型（表2)。此外，一阶导数光谱可以通过分离重叠吸收峰和降低背景噪声有效提高光谱应用精度，因此其对于岩溶区非岩溶区植物叶含水量准确估算有一定的应用潜力。本文基于原始反射光谱及一阶导数光谱按以上四种光谱指数结构，分析所有可能波段组合模型与叶片含水率的关系，进而筛选不同生境下多种典型植物的含水率最优反演模型。

<html><body><table><tr><td colspan="3">Table 2Model structure of spectral index</td></tr><tr><td>指数类型</td><td>原始光谱公式</td><td>一阶导数光谱公式</td></tr><tr><td>Index type</td><td>Raw spectrum formula</td><td>First derivative spectral formula</td></tr><tr><td>单波段</td><td>Ra</td><td>Da</td></tr><tr><td>Single band</td><td></td><td></td></tr><tr><td>差值型</td><td>Ra-Rb</td><td>Da-Db</td></tr><tr><td>Differential 比值型</td><td>Ra/Rb</td><td>Da/Db</td></tr><tr><td>Ratio</td><td></td><td></td></tr><tr><td>归一化型</td><td>(Ra-Rb)/(Ra+Rb)</td><td></td></tr><tr><td>Normalized</td><td></td><td>(Da-Db)/(Da+Db)</td></tr></table></body></html>

注：R为反射光谱，D为一阶导数光谱；a、b代表波长。下同。

Note: R is the reflection spectrum,Dis the first derivative spectrum;a and brepresent the wavelength.The same below.

# 1.4数据处理与分析

相同生境下从每种植物样本数量中随机选择三分之二构成岩溶区/非岩溶区植物建模数据库，用于模型构建，剩余三分之一用于模型验证。岩溶区植物共采集样本数据520组，其中346组数据用于岩溶区模型的构建，剩余的174组数据用于模型检验；非岩溶区植物共采集样本数据174组，其中116组数据用于非岩溶区模型构建，剩余的58组数据用于模型检验。选用决定系数 $( \boldsymbol { R } ^ { 2 }$ ）和均方根误差（RMSE）作为模型的检验指标， $R ^ { 2 }$ 越大，RMSE越小，模型反演精度越高。

# 2结果与分析

# 2.1已知光谱指数在岩溶区与非岩溶区植物叶片含水率中的应用

将文献中基于特定植物提出的估算叶片含水量的部分光谱指数应用于桂北岩溶区和非岩溶区植物叶片含水率估算结果显示（表3)，大部分光谱指数与本数据库叶片含水率拟合效果较差，对岩溶区和非岩溶区的拟合 $\textstyle R ^ { 2 }$ 大于0.5的指数占所有试验指数的比例分别仅为$3 . 3 3 \%$ 和 $1 3 . 3 3 \%$ 。其中指数 $\mathrm { D V I } _ { ( 1 4 4 5 , 2 3 0 5 ) }$ 在岩溶区与非岩溶区均表现最好，拟合 $\textstyle R ^ { 2 }$ 分别达到0.52和0.61。

表2光谱指数模型结构  
表3已知光谱指数与叶片含水率线性拟合精度  
Table 3 Linear fitting accuracy of known spectral index and leaf water content   

<html><body><table><tr><td>计算公式</td><td>文献</td><td>岩溶区 Karst area</td><td>非岩溶区 Non-kars</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">Spectral index</td><td rowspan="2">Formula</td><td colspan="2"></td><td rowspan="2">R² RMSE</td><td rowspan="2"></td><td rowspan="2">R²</td><td rowspan="2">RMSE</td></tr><tr><td></td><td>Cite</td></tr><tr><td>DVI(1218,199)</td><td>R1299-R1218</td><td>Sun et al., 2019</td><td></td><td>0.29</td><td>0.07</td><td>0.47</td><td>0.05</td></tr><tr><td>DVI(1445,2305)</td><td>R2305-R1445</td><td>徐庆等,2018</td><td></td><td>0.52</td><td>0.06</td><td>0.61</td><td>0.04</td></tr><tr><td>DVI(1833,2236)</td><td>D2236-D1833</td><td>徐庆等,2018</td><td></td><td>0.37</td><td>0.07</td><td>0.53</td><td>0.05</td></tr><tr><td>RVI(80.810)</td><td>R810/R680</td><td>刘晓静等,2018</td><td></td><td>0.05</td><td>0.08</td><td>0.04</td><td>0.07</td></tr><tr><td>RVI(760,1650)</td><td>R760/R1650</td><td>刘畅等,2017</td><td></td><td>0.08</td><td>0.08</td><td>0.03</td><td>0.07</td></tr><tr><td>RVI(820,1600)-1</td><td>R820/R1600</td><td></td><td>刘畅等,2017; Zhang & Zhou,2019</td><td>0.09</td><td>0.08</td><td>0.04</td><td>0.07</td></tr><tr><td>RVI(820,1600)02</td><td>R1600/R820</td><td></td><td>杨勇等,2011；朱西存等,2014</td><td>0.08</td><td>0.08</td><td>0.03</td><td>0.07</td></tr><tr><td>RVI(860,1240)</td><td>R860/R1240</td><td></td><td>El-Hendawy et al.,2019; Zhang& Zhou,2019</td><td>0.10</td><td>0.08</td><td>0.03</td><td>0.07</td></tr><tr><td>RVI(900.950)</td><td>R950/R900</td><td></td><td>程志庆等,2016；潘庆梅等,2019</td><td>0.17</td><td>0.08</td><td>0.07</td><td>0.07</td></tr><tr><td>RVI(900,970)-1</td><td>R900/R970</td><td></td><td>刘畅等,2017；张玮等,2019</td><td>0.18</td><td>0.08</td><td>0.03</td><td>0.07</td></tr><tr><td>RVI(900.970)-2</td><td>R970/R900</td><td></td><td>杨勇等,2011；朱西存等,2014</td><td>0.18</td><td>0.08</td><td>0.03</td><td>0.07</td></tr><tr><td>RV(1218,1301)</td><td>R1301/R1218</td><td>Sun et al., 2019</td><td></td><td>0.32</td><td>0.07</td><td>0.47</td><td>0.05</td></tr><tr><td>RVI(1300,1450)</td><td>R1300R1450</td><td>刘畅等,2017；张玮等,2019</td><td></td><td>0.13</td><td>0.08</td><td>0.02</td><td>0.07</td></tr><tr><td>RVI(1445,2305)</td><td>R1445/2305</td><td></td><td>徐庆等,2018</td><td>0.37</td><td>0.07</td><td>0.56</td><td>0.05</td></tr><tr><td>NDVI(531,570)</td><td>(R531-R570)/(R531+R570)</td><td></td><td>胡珍珠等,2016; Sun et al.,2019</td><td>0.08</td><td>0.07</td><td>0.08</td><td>0.07</td></tr><tr><td>NDVI(680.800)</td><td>(R800-R680)/(R800+R680)</td><td></td><td>徐庆等,2018；胡珍珠等,2016</td><td>0.06</td><td>0.08</td><td>0.04</td><td>0.07</td></tr><tr><td>NDVI(680.810) 0</td><td>(R810-R680)/(R810+R680)</td><td></td><td>刘晓静等,2018</td><td>0.06</td><td>0.08</td><td>0.04</td><td>0.07</td></tr><tr><td>NDV 1(705.750)</td><td>(R750-R705)/(R750 + R705)</td><td>Sun et al., 2019</td><td></td><td>0.01</td><td>0.08</td><td>0.07</td><td>0.07</td></tr><tr><td>NDVI(710.750)</td><td>(R750-R710)/(R750+R710)</td><td>Zhang & Zhou, 2019</td><td></td><td>0.01</td><td>0.09</td><td>0.09</td><td>0.07</td></tr><tr><td>4 0 NDVI(820,1600)</td><td>(R820-R1600)/(R820+R1600)</td><td>杨勇等,2011；潘庆梅等,2019</td><td></td><td>0.08</td><td>0.08</td><td>0.04</td><td>0.07</td></tr><tr><td>NDVI(850,1650)</td><td>(R850-R1650)/(R850+R1650)</td><td>徐庆等,2018; Sun et al.,2019</td><td></td><td>0.07</td><td>0.08</td><td>0.05</td><td>0.07</td></tr><tr><td>2 NDVI(858.1640)</td><td>(R858-R1640)/(R858+R1640)</td><td>Zhang & Zhou, 2019</td><td></td><td>0.08</td><td>0.08</td><td>0.04</td><td>0.07</td></tr><tr><td>NDVI(858,2130)</td><td>(R858-R2130)/(R858+R2130)</td><td>Zhang & Zhou, 2019</td><td></td><td>0.04</td><td>0.08</td><td>0.08</td><td>0.07</td></tr><tr><td>11 NDVI(860,1240)</td><td>(R860-R1240)/(R860 +R1240)</td><td>程志庆等,2016；刘畅等,2017</td><td></td><td>0.10</td><td>0.08</td><td>0.03</td><td>0.07</td></tr><tr><td>NDVI(860,1450)</td><td>(R860-R1450)/(R860+R1450)</td><td>潘庆梅等,2019</td><td></td><td>0.13</td><td>0.08</td><td>0.00</td><td>0.07</td></tr><tr><td>NDVI(860,1640)</td><td>(R860-R1640)/(R860+R1640)</td><td>El-Hendawy et al.,2019</td><td></td><td>0.09</td><td>0.08</td><td>0.02</td><td>0.07</td></tr><tr><td>n NDVI(880.970)</td><td>(R970-R880)/(R970+R880)</td><td>El-Hendawy et al.,2019</td><td></td><td>0.15</td><td>0.08</td><td>0.04</td><td>0.07</td></tr><tr><td>h NDVI(1218.1301)</td><td>(R1301-R1218)/(R1301+R1218)</td><td>Sun et al., 2019</td><td></td><td>0.32</td><td>0.07</td><td>0.47</td><td>0.05</td></tr><tr><td>NDVI(1445,2345)</td><td>(R2305-R1445)/(R1445+R2305)</td><td>徐庆等,2018</td><td></td><td>0.38</td><td>0.07</td><td>0.57</td><td>0.05</td></tr><tr><td>NDVI(1649,1722)</td><td>(R1649-R1722)/(R1649+R1722)</td><td>徐庆等,2018</td><td></td><td>0.06</td><td>0.08</td><td>0.27</td><td>0.06</td></tr></table></body></html>

# 2.2岩溶区植物叶片含水率反演

从图1可以看出，岩溶区植物反射光谱在单波段和不同波段组合中对叶片含水率拟合较好的区域并不多。单波段反射光谱拟合中，所有波段拟合 $\textstyle R ^ { 2 }$ 均小于 0.30（图1：a)。不同波段组合的指数模型中，差值型模型表现较好的组合波段较多，主要集中在 $\scriptstyle \mathrm { R a = 1 } 4 7 0 \sim 1 9 2 0$ nm、 $\mathrm { R b } { = } 1 3 8 0 { \sim } 1 8 8 0 \mathrm { n m }$ ， $\mathrm { R a } { = } 2 2 2 0 { \sim } 2 4 0 0 \mathrm { n m } .$ ， $\mathrm { R b } { = } 1 ~ 4 0 0 { \sim } 1 ~ 5 2 0 ~ \mathrm { n m }$ 和 $1 9 7 0 { \sim } 2 1 2 0 \mathrm { n m }$ 区域(图1：b)；比值型和归一化型模型中，表现较好的组合波段相似，主要集中在 $\scriptstyle { \mathrm { R a } = 2 } 2 2 0 \sim$ $2 4 0 0 \mathrm { n m }$ 、 $\mathrm { R b } { = } 1 ~ 4 0 0 { \sim } 1 ~ 5 2 0 ~ \mathrm { n m }$ 和 $1 8 2 0 { \sim } 2 1 2 0 \mathrm { n m }$ 区域（图1：c,d)。

![](images/1ce46983eabf92e1cd7a1941c7b7b7d91711d642b163774e6291f705a5d5290d.jpg)  
图1岩溶植物反射光谱单波段(a)和不同波段组合的差值型 ${ \bf ( b ) }$ 、比值型(c)和归一化型(d)光谱指数对含水率线性拟合的 $R ^ { 2 }$ 分布图

Fig. 1 The $R ^ { 2 }$ profile of linear fiting of spectral index to moisture content of single band (a) and different band combinations differential ${ \bf ( b ) }$ , ratio (c), and normalized $\mathbf { \eta } ( \mathbf { d } )$ of karst plant reflection spectrum

图2为岩溶区植物一阶导数光谱采用不同指数结构对叶片含水率拟合的效果。由图 2可知，对叶片反射光谱进行一阶求导后，单波段反射光谱拟合效果整体提升，其中3个波段的拟合 $R ^ { 2 }$ 均大于0.5（图2：a)，在波段 $1 \ 7 3 0 \ \mathrm { n m }$ 左右拟合效果最好。差值型、比值型和归一化型光谱指数的叶片水分敏感波段组合表现变得较为分散（图2：b-d)，不如原始光谱集中。差值型模型中，拟合效果最好的波段组合主要集中在 $\mathrm { D a } { = } 2 0 0 0 { \sim } 2 1 0 0 \mathrm { n m }$ 、 ${ \mathrm { D b } } { = } 1 ~ 7 0 0 { \sim }$ $1 8 6 0 \mathrm { n m }$ 区域（图2：b)；比值型模型中，拟合效果最好的波段组合主要分布在 $\mathrm { D a } { = } 1 ~ 5 8 0 { \sim }$ $1 ~ 9 0 0 ~ \mathrm { { n m } }$ 、 $\mathrm { D b } { = } 1 ~ 3 0 0 { \sim } 1 ~ 9 0 0 ~ \mathrm { n m }$ 区域（图2：c)；归一化型模型中，拟合效果较好的组合主要在 $\mathrm { D a } { = } 2 ~ 0 0 0 { \sim } 2 ~ 1 2 0 ~ \mathrm { n m }$ 、 $\mathrm { D b } { = } 1 ~ 8 3 0 { \sim } 2 ~ 0 2 0 ~ \mathrm { n m }$ 区域（图2：d)。

注：c,d中空白片段为光谱指数计算值过大，无法拟合。

![](images/a9543df534169fbb11fa57cee1bccd19bab625da822f5d8caf8be5435bac189d.jpg)  
图2 岩溶植物一阶导数光谱单波段(a)和不同波段组合的差值型 ${ \bf ( b ) }$ 、比值型(c)和归一化型(d)光谱指数对含水率线性拟合的 $\textstyle R ^ { 2 }$ 分布图

Note: The calculated value of spectral index is too large to fit in the blank of a and b.

Fig. 2 The $R ^ { 2 }$ profile of linear fittng of first derivative spectrum to moisture content of single band (a)and different band combinations differential ${ \bf ( b ) }$ ,ratio (c),and normalized (d) of karst plant reflection spectrum

基于各指数结构对岩溶植物叶片含水率拟合的最优指数以及验证结果如表4所示， $\mathbf { R } _ { 7 3 5 }$ 在所有模型中的建模和验证结果均最差， $\mathrm { D } _ { 2 0 4 8 ^ { - } } \mathrm { D } _ { 1 7 3 3 }$ 最好。基于一阶导数光谱构建的单波段、比值型和差值型模型的拟合效果均比基于反射光谱的拟合效果好，其中单波段模型的拟合效果提升最为明显。

表4岩溶区植物光谱指数模型建模和验证结果  
Table 4 Modeling and verification of plant spectral index model in karst area.   

<html><body><table><tr><td rowspan="2">指数变量 Index variable</td><td rowspan="2">模型 Model</td><td colspan="2">建模结果</td><td colspan="2">验证结果 Verification (n=174)</td></tr><tr><td>Model (n=346) R²</td><td>RMSE</td><td>R²</td><td>RMSE</td></tr><tr><td>R735</td><td>y=0.901 6x+0.174 7</td><td>0.28**</td><td>0.07</td><td>0.29**</td><td>0.07</td></tr><tr><td>R2260-R1441</td><td>y= 6.533 5x+0.559 6</td><td>0.62**</td><td>0.05</td><td>0.63**</td><td>0.05</td></tr><tr><td>R2249/R1437</td><td>y= 1.101 4x-0.593 0</td><td>0.61**</td><td>0.05</td><td>0.64**</td><td>0.05</td></tr><tr><td>(R2249-R1437)/(R2249+R1437)</td><td>y= 2.239 6x+0.510 4</td><td>0.61**</td><td>0.05</td><td>0.64**</td><td>0.05</td></tr><tr><td>D1733</td><td>y= -377.847 4x+0.407 3</td><td>0.57**</td><td>0.06</td><td>0.53**</td><td>0.06</td></tr><tr><td>D2048-D1733</td><td>y= 299.415 5x+0.289 8</td><td>0.68**</td><td>0.05</td><td>0.67**</td><td>0.05</td></tr><tr><td>D1732/D1714</td><td>y= 0.204 5x+0.388 5</td><td>0.62**</td><td>0.05</td><td>0.52**</td><td>0.06</td></tr><tr><td>(D2355-D1884)/(D2355+D1884)</td><td>y= 2.077 4x+2.352 8</td><td>0.60**</td><td>0.06</td><td>0.58**</td><td>0.05</td></tr></table></body></html>

注： $^ { * * }$ 表示 $P { < } 0 . 0 1$ 。下同。   
Note:\*\* indicates $P { < } 0 . 0 1$ .The same below.

# 2.3非岩溶区植物叶片含水率反演

从图3可以看出，非岩溶区植物反射光谱在单波段和不同波段组合中对叶片含水率拟合较好的区域很少。反射光谱的单波段指数拟合效果整体很差（ $( R ^ { 2 } { < } 0 . 1 4 )$ ，在 $1 3 0 0 \mathrm { n m }$ 左右波段拟合最好，最大 $\textstyle R ^ { 2 }$ 也仅为0.13（图3：a)。不同波段组合模型的叶片水分敏感波段分布较为相似（图3：b-d)，都主要集中在 $\mathrm { R a } { = } 1 ~ 4 0 0 { \sim } 1 ~ 8 5 0 ~ \mathrm { n m }$ 、 $\mathrm { R b } { = } 1 3 2 0 { \sim } 1 4 2 0 \mathrm { n m }$ 区域，以及$\mathrm { R a } = 1 ~ 8 5 0 { \sim } 2 ~ 5 0 0 \mathrm { n m }$ 、 $\mathrm { R b } { = } 1 3 9 0 { \sim } 1 5 2 0 \mathrm { n m }$ 和 $\mathrm { R b } { = } 1 ~ 8 0 0 { \sim } 1 ~ 9 2 0 ~ \mathrm { n m }$ 区域内的波段组合。

![](images/cf595aba8aab9df1bdc79d54ae62c99c378a9b3788bc76adaf0bcabfc73ac0d5.jpg)  
图3 非岩溶植物反射光谱单波段(a)和不同波段组合的差值型 ${ \bf ( b ) }$ 、比值型(c)和归一化型(d)光谱指数对含水率线性拟合的 $R ^ { 2 }$ 分布图

Fig. 3 The $R ^ { 2 }$ profile of linear fiting of spectral index to moisture content of single band (a) and different band combinations differential ${ \bf ( b ) }$ , ratio (c),and normalized (d) of non-karst plant reflection spectrum

图4为基于非岩溶区植物一阶导数光谱使用不同结构指数对叶片含水率拟合的效果。对叶片反射光谱进行一阶导数处理后，单波段指数拟合效果整体提升，有3个波段对叶片含水率拟合的 $R ^ { 2 }$ 大于0.5，在 $2 \ 3 5 0 \ \mathrm { n m }$ 波段拟合效果最好（图4：a)。基于一阶光谱的差值型、比值型和归一化型模型的敏感波段组合表现的较为分散（图4：b-d)，不如原始光谱拟合时集中。差值型模型中，拟合效果最好的波段组合主要在 $\mathrm { D a } { = } 1 7 0 0 { \sim } 1 8 5 0 \mathrm { n m }$ 、Db=1 600\~1 720nm 区域（图4：b)；比值型和归一化型模型中，拟合效果较好的波段组合主要在 $\mathrm { D a } { = } 2 ~ 3 0 0 { \sim }$ $2 4 6 0 \mathrm { n m }$ 、 $\mathrm { D b } { = } 1 ~ 8 3 0 { \sim } 1 ~ 9 0 0 \mathrm { n m }$ 区域（图4：c,d)。

![](images/ff4254073f5cd97a907f10aa991774fd7ffec22bac86044e807b566841b7a555.jpg)  
图4 非岩溶植物一阶导数光谱单波段(a)和不同波段组合的差值型 ${ \bf ( b ) }$ 、比值型(c)和归一化型(d)光谱指数对含水率线性拟合的 $R ^ { 2 }$ 分布图

Fig. 4 The $R ^ { 2 }$ profile of linear fittng of first derivative spectrum to moisture content of single band (a) and different band combinations differential ${ \bf ( b ) }$ ,ratio (c),and normalized (d) of non-karst plant reflection spectrum

使用不同结构的光谱指数对非岩溶植物叶片含水率进行全波段搜索得到的最优指数模型以及验证结果显示（表5）， ${ \bf R } _ { 1 3 2 0 }$ 的建模和验证结果均最差， $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$ 最好，$( \mathrm { D } _ { 2 3 5 6 } \mathrm { - D } _ { 1 8 8 5 } ) / ( \mathrm { D } _ { 2 3 5 6 } \mathrm { + D } _ { 1 8 8 5 } )$ 与 $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$ 的结果比较接近。基于一阶导数光谱构建的单波段、比值型和归一化型模型均比基于反射光谱构建的拟合效果好，其中单波段模型拟合效果提升最为明显。

表5非岩溶植物光谱指数模型建模和验证结果  
Table 5 Modeling and verification of plant spectral index model in non-karst area   

<html><body><table><tr><td rowspan="2">指数变量 Index variable</td><td rowspan="2">模型 Model</td><td colspan="2">建模结果 Model (n=116)</td><td colspan="2">验证结果 Verification (n=58)</td></tr><tr><td>R²</td><td>RMSE</td><td>R²</td><td>RMSE</td></tr><tr><td>R1320</td><td>y=-0.882 5x+0.932 1</td><td>0.13**</td><td>0.07</td><td>0.03**</td><td>0.06</td></tr><tr><td>R2249-R1436</td><td>y= 7.078 8x+0.527 2</td><td>0.72**</td><td>0.04</td><td>0.69**</td><td>0.04</td></tr><tr><td>R2249/R1436</td><td>y= 1.137 6x-0.611 0</td><td>0.72**</td><td>0.04</td><td>0.68**</td><td>0.04</td></tr><tr><td>(R2248-R1436)/(R2248+R1436)</td><td>y= 2.353 1x+0.522 5</td><td>0.71**</td><td>0.04</td><td>0.66**</td><td>0.04</td></tr><tr><td>D2358</td><td>y= -684.766 5x+ 0.324 6</td><td>0.57**</td><td>0.05</td><td>0.53**</td><td>0.04</td></tr><tr><td>D1836-D1700</td><td>y= -332.446 9x+0.557 2</td><td>0.70**</td><td>0.04</td><td>0.61**</td><td>0.04</td></tr><tr><td>D2356/D1885</td><td>y= 3.933 1x+0.320 2</td><td>0.76**</td><td>0.04</td><td>0.64**</td><td>0.04</td></tr><tr><td>(D2356-D1885)/(D2356+D1885)</td><td>y= 2.208 4x+2.515 5</td><td>0.75**</td><td>0.04</td><td>0.64**</td><td>0.04</td></tr></table></body></html>

# 2.4岩溶区毛叶和亮叶叶片含水率反演

采用相同方法对岩溶区毛叶和亮叶植物叶片含水率分别进行全波段搜索得到的最优光谱指数如表6所示。毛叶含水率的最优拟合指数的拟合效果小于亮叶。对岩溶区亮叶和毛叶植物分别进行模型构建后，其拟合效果较岩溶区植物总体建模的拟合效果没有得到明显提升。

# 表6岩溶区毛叶和亮叶植物光谱指数模型建模和验证结果

Table 6 Modeling and verification of plant spectral index model of hairy and bright leaf in karst

<html><body><table><tr><td colspan="8">area</td></tr><tr><td>叶上表皮类型</td><td></td><td></td><td colspan="2">建模结果Model</td><td colspan="2">验证结果Verification</td></tr><tr><td>Leaf surface type</td><td>指数变量Indexvariable</td><td>模型Model</td><td>R²</td><td>RMSE</td><td>R²</td><td>RMSE</td></tr><tr><td>毛叶和亮叶</td><td>D2048-D1733</td><td>Y=299.42x+0.29</td><td>0.68**</td><td>0.05</td><td>0.67**</td><td>0.05</td></tr><tr><td>Hairy and bright leaf</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>亮叶</td><td>D2051-D1734</td><td>Y=300.21x+0.29</td><td>0.69**</td><td>0.05</td><td>0.65**</td><td>0.05</td></tr><tr><td>Bright leaf</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>毛叶</td><td>(D2292-D1771)/ (D2292+D1771)</td><td>Y=-0.23x+0.54</td><td>0.51**</td><td>0.05</td><td>0.36**</td><td>0.04</td></tr><tr><td>Hairy leaf</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 2.5岩溶区和非岩溶区植物叶片含水率最优反演模型的检验

为了检验模型的稳定性和精准性，分别对岩溶区和非岩溶区植物所有样本叶片含水率的测量值与基于最优模型的预测值进行比较（图5)。结果表明，基于最优模型的预测值和实测值之间在岩溶区和非岩溶区均具有极显著的线性相关性（ ${ \cdot } P { < } 0 . 0 0 1 \$ )，说明基于 $\mathrm { D } _ { 2 0 4 8 ^ { - } } \mathrm { D } _ { 1 7 3 3 }$ 和 $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$ 分别建立的岩溶区和非岩溶区植物叶片含水率模型均具有较好的稳定性和反演能力。

![](images/8d0ae7aad69530811322c4f99f45821b9990d7c886582ee8a05e3f83ee0b0ffe.jpg)  
图5基于光谱指数 $\mathrm { D } _ { 2 0 4 8 ^ { - } } \mathrm { D } _ { 1 7 3 3 }$ 和 $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$ 的岩溶区和非岩溶区植物叶片含水率预测值与实测值比较  
Fig. 5 Comparison of estimated with measured leaf water content at karst and non-karst areas based on the spectral indices $\mathrm { D } _ { 2 0 4 8 ^ { - } } \mathrm { D } _ { 1 7 3 3 }$ and $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$

# 3讨论与结论

基于特定数据库构建的叶片含水率光谱模型一般具有一定的适用局限，即在其他数据库中的反演效果不够理想。本文结果也证明文献中已有的叶片水分反演光谱指数在本研究区域植物中的应用效果均不佳，且岩溶区与非岩溶区植物叶片含水率与光谱指数拟合的最佳波段并不相同，说明有必要针对岩溶区和非岩溶区分别建立植物叶片含水率反演模型。处于不同生境条件下的植被，在环境的影响下植物叶性状（结构性状和化学性状）会发生改变来适应环境（盘远方等,2018)，因此其目标敏感光谱信息也会发生相应的改变。本研究中，不同结构的光谱指数对非岩溶区植物的拟合效果整体比岩溶区植物的拟合效果要好，最优叶片水分反演光谱指数分别为 ${ \mathrm { D } _ { 2 3 5 6 } } / { \mathrm { D } _ { 1 8 8 5 } } ( R ^ { 2 } { = } 0 . 7 6 )$ 和 $\mathrm { D } _ { 2 0 4 8 }  – \mathrm { D } _ { 1 7 3 3 } ( R ^ { 2 } { = } 0 . 6 8 )$ 。一方面可能是与岩溶区植物干湿季节间叶片结构和组分的强烈动态变化有关（葛昊等，2012；吴见，2015；刘玉冰等，2016;Sun etal.,2019）。相对于非岩溶区而言，岩溶区土壤持水能力差，使岩溶区植被易受到干旱胁迫，且旱季时干旱胁迫更为明显，从而导致植物水分状态的季节差异较大。另一方面也可能由于岩溶区植物个体间叶片结构差异较大所致。裸露型岩溶区特殊的地质结构阻断了土壤斑块之间的水分和养分关联，生境岛屿化严重（陈洪松等，2013），从而导致植物个体间生长差异较大。这与潘庆梅等（2019）与胡珍珠等（2016）得出的不同区域核桃叶片含水率敏感波段存在差异的研究结果相似。但通过对岩溶区毛叶和亮叶叶片含水率的分类反演结果显示，分类反演后亮叶植物的最优光谱指数拟合效果提升不明显，而毛叶植物拟合效果反而明显降低，说明叶片绒毛对水分反演影响不明显，这可能是由于本研究中毛叶植物的绒毛均在叶片背面，并且部分植物在叶片成熟后绒毛有逐渐褪去的趋势。

组合波段与单波段指数相比，其增加了信息的负载量，同时降低了外界因素的影响，实现了光谱差异信息的放大，因此组合波段模型一般比单波段模型具有较高的反演精度（李珺和宋文龙,2016；徐道青等,2017;Corte etal.,2017）。本研究中，与波段组合相比，单波段指数与叶片含水率拟合效果均最差，说明波段组合能更准确地反映目标敏感光谱的信息，体现了植被指数的优点。反射光谱的一阶导数有利于消除测量过程中产生的噪音等对叶片反射光谱信息造成的干扰，能更好地反映植被光谱的特征，有利于植被信息的反演(Damson et al,1992;Yietal.,2013；林毅等,2015）。其中，单波段光谱指数的表现在一阶导数处理后拟合效果提升尤为明显。不同波段组合中，基于反射光谱拟合较好的波段组合区域比基于一阶光谱的更为连续和集中，但精度略差。由此，说明一阶导数光谱能较好地消除相邻光谱信息的干扰，可以有效提高光谱的应用精度。

综上， $\mathrm { D } _ { 2 0 4 8 ^ { - } } \mathrm { D } _ { 1 7 3 3 }$ 为岩溶植物叶片含水率的最佳反演光谱指数， $\mathrm { D } _ { 2 3 5 6 } / \mathrm { D } _ { 1 8 8 5 }$ 和$( \mathrm { D } _ { 2 3 5 6 } \mathrm { - D } _ { 1 8 8 5 } ) / ( \mathrm { D } _ { 2 3 5 6 } \mathrm { + D } _ { 1 8 8 5 } )$ 均可作为非岩溶植物叶片含水率的最佳反演光谱指数。本研究中，岩溶区植物叶片绒毛对水分反演影响不明显，但蜡质晶体等叶表结构是否为影响岩溶植物水分反演的重要因素有待进一步研究。

参考文献：   
ASNER GP, BRODRICK PG, ANDERSON CB, et al., 2016. Progressive forest canopy water loss during the 2012-2015 California drought[J]. Proc Natl Acad Sci USA,113(2): E249-E255.   
CAI YL,1996. Ecological reconstruction in poverty-stricken areas of karst stone mountains in southwest China[J].Adv Earth Sci,11(6):84-88.[蔡运龙，1996．中国西南岩溶石山贫困 地区的生态重建[J]．地球科学进展，11(6)：84-88.]   
CHEN HS,NIE YP, WANG KL，2013. Spatial-temporal heterogeneity of water and plant adaptation mechanisms in karsts regions: A review[J]. Acts Ecol Sin, 33(2): 317-326. [陈洪 松，聂云鹏，王克林，2013．岩溶山区水分时空异质性及植物适应机理研究进展[J]．生 态学报，33(2)：317-326.]   
CHENG ZQ, ZHANG JS,MENG P, et al.,2016. Estimation model of poplar equivalent water thickness based on hyperspectral information[J]. For Res,29(6): 826-833.[程志庆，张劲松, 孟平，等，2016．基于高光谱信息的 107 杨叶片等效水厚度估算模型的研究[J]．林业 科学研究，29(6)：826-833.]   
CORTI M, GALLINA PM, CAVALLI D, et al., 2017. Hyperspectral imaging of spinach canopy under combined water and nitrogen stress to estimate biomass, water, and nitrogen content[J]. Biosyst Eng,158: 38-50.   
DANSON FM, STEVEN MD,MALTHUS TJ,et al.，1992, High spectral resolution data for determining leaf water content[J]. Int J Remote Sens,13(3): 461-470.   
EL-HENDAWY SE, AL-SUHAIBANI NA., ELSAYED S, et al., 2019. Potential of the existing and novel spectral reflectance indices for estimating the leaf water status and grain yield of spring wheat exposed to different irrigation rates[J]. Agric Water Manag, 217: 356-373.   
GE H,LU S, ZHAO YS,2O12. Effects of leaf hair on leaf reflectance and hyperspectral vegetation indices[J].Spectrosc Spectr Anal,32(2):439-444.[葛昊，卢珊，赵云升，2012．叶片茸毛 对叶片反射光谱及高光谱植被指数的影响研究[J]．光谱学与光谱分析，32(2)：439-444.]   
HU ZZ, PAN CD, PAN X, et al., 2016. Estimation models for water content of walnut leaves based on spectral moisture index[J]. Sci Silv Sin, 52(12):39-49.[胡珍珠，潘存德，潘鑫, 等，2016.基于光谱水分指数的核桃叶片含水量估算模型[J]．林业科学，52(12)：39-49.]   
HUANG FZ, LI DX, WANG B, et al., 2019. Foliar stable carbon isotope composition and water use efficiency of plant in the karst seasonal rain forestJ]. Chin J Appl Ecol,30(6): 1833-1839. [黄甫昭，李冬兴，王斌，等，2019．喀斯特季节性雨林植物叶片碳同位素组成及水分 利用效率[J]．应用生态学报，30(6)：1833-1839.]   
KOVAR M, BRESTIC M， SYTAR O,et al.， 2019,Evaluation of hyperspectral reflectance parameters to assess the leaf water content in soybean[J]. Water, 11(3): 443.   
KRISHNA G, SAHOO RN, SINGH P, et al.,2019. Comparison of various modelling approaches for water deficit stress monitoring in rice crop through hyperspectral remote sensing[J]. Agric Water Manag, 213: 231-244.   
LI J, SONG WL, 2016. Water content model for strawberry leaves with spectral signature[J]. J NE For Univ,44(1):72-74.[李珺，宋文龙，2016．基于光谱反射特征的草莓叶片含水率模型 [J]．东北林业大学学报，44(1)：72-74.]   
LIANG L, ZHANG LP, LIN H, et al., 2013. Estimating canopy leaf water content in wheat based on derivative spectra[J]. Sci Agric Sin,46(1): 18-29.[梁亮，张连蓬，林卉，等，2013．基 于导数光谱的小麦冠层叶片含水量反演[J]．中国农业科学，46(1)：18-29.]   
LIN Y, LI Q, WANG HB, et al., 2015. Research summary of vegetation water content inversion with hyperspectral technology[J]. Chin Agric Sci Bull, 31(3): 167-172.[林毅,李倩,王宏博, 等，2015．高光谱反演植被水分含量研究综述[J]．中国农学通报，31(3)：167-172.]   
LIU C, SUN PS, LIU SR, 2017. A comparison of spectral reflectance indices in response to water: A case study of Quercus aliena var. acuteserrata[J]. Chin J Plant Ecol, 41(8): 850-861. [刘畅, 孙鹏森，刘世荣，2017．水分敏感的反射光谱指数比较研究——以锐齿槲栎为例[J]．植 物生态学报，41(8)：850-861.]   
LIU XJ, CHEN GQ, WANG L, et al., 2018. Monitoring leaf relative water content of winter wheat based on hyperspectral index at different growth stages[J]. J Tritic Crops, 38(7): 854-862.[刘 晓静，陈国庆，王良，等，2018.不同生育时期冬小麦叶片相对含水量高光谱监测[J].麦 类作物学报，38(7)：854-862.]   
LIU XJ, TIAN YC, YAO X, et al., 2012. Monitoring leaf water content based on hyperspectra in rice[J].Sci Agric Sin,45(3):435-442.[刘小军，田永超，姚霞，等，2012．基于高光谱的 水稻叶片含水量监测研究[J]．中国农业科学，45(3)：435-442.]   
LIU YB,LI XR,LI MM, et al., 2016. Leaf (or assimilation branch) epidermal micromorphology of desert plant in arid and semiarid areas of China[J]. Chin JPlant Ecol, 4O(11): 1189-1207. [刘玉冰，李新荣，李蒙蒙，等，2016．中国干旱半干旱区荒漠植物叶片(或同化枝)表皮 微形态特征[J]．植物生态学报，40(11)：1189-1207.]   
LUO KW, QUAN XW, HE BB, et al., 2019. Effects of live fuel moisture content on wildfire occurrence in fire-prone regions over southwest China[J]. Forest, 1O(1O): 887.   
NI LK, GU DX, HE W, et al.,2019. Research advances in plant ecological adaptability in karst area[J].ChinJEcol,38(7): 2210-2217.[倪隆康，顾大形，何文，等，2019．岩溶区植物 生态适应性研究进展[J]．生态学杂志，38(7)：2210-2217.]   
PAN QM, ZHANG JS, MENG P, et al., 2019. Hyperspectral estimation of water content in walnut leaves in hilly areas of north China[J].JNE For Univ,47(7): 68-74.[潘庆梅，张劲松，孟平, 等,2019.华北低山丘陵区核桃叶片水分含量的高光谱估算[J]．东北林业大学学报,47(7): 68-74.]   
PAN YF, CHEN XB，JIANG Y,et al.， 2O18. Changes in leaf functional traits and soil environmental factors in response to slope gradient in karst hills of Guilin[J]. Acta Ecol Sin, 38(5):1581-1589.[盘远方，陈兴彬，姜勇，等，2018．桂林岩溶石山灌丛植物叶功能性 状和土壤因子对坡向的响应[J]．生态学报，38(5)：1581-1589.]   
SUN H, FENG MC, XIAO LJ, et al., 2019. Assessment of plant water status in winter wheat (Triticum aestivum L.) based on canopy spectral indices[J]. PLoS ONE,14(6): e0216890.   
UMUT H, MAMAT S, MA CY, 2019. Hyperspectral estimation of wheat leaf water content using fractional differentials and successive projection algorithm-back propagation neural network[J].Laser Optoel Prog,56(15):251-259.[吾木提·艾山江，买买提·沙吾提，马春 玥，2019．基于分数阶微分和连续投影算法-反向传播神经网络的小麦叶片含水量高光 谱估算[J]．激光与光电子学进展，56(15)：251-259.]   
WEI XH,LEI L,LIU SJ,et al.， 2O17． Analysis on the absorbing, transfer, restoration and adaptation mechanism of calcium in different peak forest plants in northern Guangdong Province,China[J].Carsol Sin,36(3):368-376.[魏兴琥，雷俐，刘淑娟，等，2017．粤北 岩溶峰林植物钙吸收、转运、返还能力及适应性分析[J]．中国岩溶，36(3)：368-376.]   
WU J, CHEN TS, PAN LX, 2015. Spectrum variance analysis of tree leaves under the condition of different leaf water content[J]. Spectrosc Spectr Anal,35(7): 1961-1966.[吴见，陈泰生，潘 立新，2015．不同含水量条件下树种叶片光谱差异分析[J]．光谱学与光谱分析,35(7): 1701-1700. 』   
XU DQ,LIU XL, WANG W, et al.,2017. Hyper-spectral characteristics and estimation model of leaf chlorophyll content in cotton under waterlogging stress[J]. Chin J Appl Ecol, 28(10): 3289-3296.[徐道青，刘小玲，王维，等，2017．淹水胁迫下棉花叶片高光谱特征及叶绿 素含量估算模型[J]．应用生态学报，28(10)：3289-3296.]   
XU Q, MA Y, JIANG Q, et al.,2018. Estimation of rice leaf water content based on hyperspectral remote sensing[J].Remote Sens Inform,33(5):1-8.[徐庆，马驿，蒋琦，等，2018．水稻 叶片含水量的高光谱遥感估算[J]．遥感信息，33(5)：1-8.]   
YANG Y, ZHANG DQ, LI S, et al., 2O11. Model for citrus leaves water content based on spectral signature[J].Chin Agric Sci Bull,27(2):180-184.[杨勇，张冬强，李硕，等，2011．基于 光谱反射特征的柑橘叶片含水率模型[J]．中国农学通报，27(2)：180-184.]   
YI Q,BAO A,WANG Q, et al., 2013. Estimation of leaf water content in cotton by means of hyperspectral indices[J]. Comput Electron Agric, 90: 144-151.   
YUAN DX,2OO9. Challenges and opportunities for karst research of our country under new situation[J].Carsol Sin,28(4):329-331.[袁道先，2009．新形势下我国岩溶研究面临的机 遇和挑战[J]．中国岩溶，28(4)：329-331.]   
ZHANG F, ZHOU G, 2019. Estimation of vegetation water content using hyperspectral vegetation indices: a comparison of crop water indicators in response to water stress treatments for summer maize[J]. BMC Ecol,19:18.   
ZHANG F, ZHOU GS, 2018. Research progress on monitoring vegetation water content by using hyperspectral remote sensing[J].Chin JPlant Ecol, 42(5): 517-525.[张峰，周广胜，2018.植 被含水量高光谱遥感监测研究进展[J]．植物生态学报，42(5)：517-525.]   
ZHANG JH,LI L, YAO FM, 2010. Progress in retrieving vegetation water content under different vegetation coverage condition based on remote sensing spectral information[J]. Spectrosc Spectr Anal,30(6):1638-1642.[张佳华，李莉，姚凤梅，2010．遥感光谱信息提取不同 覆盖下植被水分信号的研究进展[J]．光谱学与光谱分析，30(6)：1638-1642.]   
ZHANG W, WANG XM，PAN QM，et al.， 2O19. Spectral reflectance characteristicsof Phyllostachys violascens canopy leaves in response to water change[J]. For Res, 32(3): 73-79. [张玮，王鑫梅，潘庆梅，等，2019．雷竹冠层叶片反射光谱特征及其对叶片水分变化 的响应[J]．林业科学研究，32(3)：73-79.]   
ZHU CX, JIANG YM, ZHAO GX, et al.， 2014. Hyperspectral estimating leaf water contents based on spectral index in apple[J]. Chin Agric Sci Bull,30(4): 120-126.[朱西存，姜远茂, 赵庚星，等，2014．基于光谱指数的苹果叶片水分含量估算模型研究[J]．中国农学通 报，30(4):120-126.]