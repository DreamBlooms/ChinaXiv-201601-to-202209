# 艾比湖流域不同土地覆盖类型土壤养分高光谱反演模型研究

蒋烨林1,2 王让会1,2\*\* 李焱李成彭擎 吴晓全(1．南京信息工程大学应用气象学院南京210044;2.大气环境与装备技术协同创新中心 南京210044)

摘要土壤养分影响着土壤的质量，也影响着植被、农作物等的生长。为快速准确地估测艾比湖流域土壤养分状况，选择艾比湖流域精河县作为研究区，以精河县内不同地表覆盖类型土壤为研究对象，基于实地采集的75个土壤样品的室内ASDFieldSpec3实测光谱数据和3种光谱变换形式，利用 $1 0 \mathrm { n m }$ 间隔重采样进行去噪处理，再结合多元逐步回归法(SMLR)、偏最小二乘法回归法(PLSR)、人工神经网络法(ANN)分别建立土壤养分预测模型，以探索最优模型。结果表明：土壤实测光谱的一阶微分、二阶微分变换形式能显著提高光谱与土壤养分之间的相关性，尤其是一阶微分变换与土壤有机质和全氮的相关性最高分别达0.87和0.91，光谱变换技术能显著增强土壤养分与高光谱之间的敏感度，达到更好的建模效果;SMLR、PLSR和ANN这3种模型都具有良好的预测能力，其中，ANN建立的模型预测效果最好，二阶微分变换的ANN模型对有机质、全氮的预测决定系数 $( R ^ { 2 } )$ 分别为0.886和0.984，均方根误差(RMSE)分别为2.614和0.147,PLSR次之；全氮的预测效果明显优于有机质的预测效果，说明高光谱和全氮之间的敏感性更高。总体来说，光谱二阶微分变换形式的人工神经网络模型可以最精确稳定地完成土壤养分含量的快速预测，能够实现艾比湖流域的土壤养分空间分布状况和动态变化特征的动态监测。

关键词土壤养分 高光谱遥感 多元逐步回归 偏最小二乘法 人工神经网络 艾比湖流域中图分类号：S151.9 文献标识码：A 文章编号:1671-3990(2016)11-1555-10

# Hyper-spectral retrieval of soil nutrient content of various land-cover types in Ebinur Lake Basin

JIANG Yelin1,2,WANG Ranghui12\*,LI Yan',LI Cheng1,PENG Qing', WU Xiaoquan' (1.Schoolof Applied Meteorology,Nanjing UniversityofInformation Scienceand Technology,Nanjing 210044,China; 2.Collaborative Innovation Centeron Atmospheric Environmentand Equipment Technology,Nanjing 210044,China)

AbstractThe soilnutrient affectssoilqualityvegetation type,crops growthandyield.Torapidlyandaccuratelydetermine soil nutrientcontents,an indoorspectraldata(measuredbyASDFieldSpec3)of75soilsamplesofJinghe CountyofEbinur Lake Basin were analyzed. Then the collected data were processed at resampling interval of $1 0 \ \mathrm { n m }$ to suppress noise. Soil nutrient hyper-spectralforecast models wereusedto forecasts soil nutrientcontents in threetransformation conditions.The performance of the models was evaluated based on stepwise multiple linear regresion (SMLR)analysis,partial least squares regression(PLSR)analysisand artificial neural network (ANN)analysis and theoptimal model determined by comparison. Theresultsshowed thatthe transformationoffirst-orderand second-orderdiferential dramatically enhancedcorrelation betweenspectroscopydata andsoil nutrientcontent.Specifically,the first-order differentialof soil spectroscopyhadagood correction with soilnutrientcontent.Thecorrelationcoefficients fororganic materand totalnitrogen wereO.87and0.91, respectively.Inconclusion,spectral transformationtechiqueincreasedthesensitivityofhighspectraldatatosoilnutrient change,anditproducedfarbetter forecastingresults.Althoughall thethree models hadgoodpredictiveability,ANNmodel hadthebest predictiveeffct,followedbyPLSRmodel.TheANNmodelestimationtestbasedonthesecond-orderdiferential of spectroscopy data with independent datasets from different soil samples respectively produced $R ^ { 2 }$ and RMSE values of 0.885and0.984fororganic materand2.614andO.147fortotalnitrogen.Thepredictionefectoftotalnitrogenwasobviously betterthanthatoforganic mater.This indicatedthat thesensitivityofsoilhyper-spectralreflectancetothesoiltotalitrogen content was much bettr.Overall,the ANNmodelbasedon the second-order diferentialofspectroscopydata rapidlyand preciselypredicted soilnutrientscontents.It wasbeneficial for monitoring spatial distributions and dynamicchangesof soil nutrients in Ebinur Lake Basin.

KeywordsSoil nutrient;Hyper-spectrum remote sensing；Stepwise multiple linearregression；Partial leastsquares regression;Artificial neural network;Ebinur Lake Basin

土壤是陆地圈层能生长植物的疏松表层，能够持续、全面地为植物生长提供所需的水、肥、气、热等基本要素[1]。土壤养分是土壤系统的重要组成，影响着土壤的理化性质，是制约植被生长和土地生产能力的关键因素[2]。土壤有机质和全氮含量是植物生长的主要养分，同时也是土壤微生物生命活动的主要能量来源[1]．其含量能直接体现土地的生产能力。因此土壤有机质、全氮含量及其动态平衡是反映土壤健康和土壤质量的重要指标[3]。土壤养分含量的快速精准测定是现代精细农业发展的重要前提[4]。传统土壤养分含量的测定往往通过试验分析获得，试验结果相对精准，但试验分析所需要的经济成本和时间成本较高，不适宜大尺度范围土壤养分的测定[5]。

土壤反射光谱与土壤理化性质之间的密切关系，为土壤组分和属性的遥感研究提供了可能[6-7]。大量的研究围绕土壤反射光谱与土壤有机质、氮素、水分、重金属等进行，并取得了不错的反演效果[8-10]。国内外很多学者都使用近红外光谱对土壤组分反演进行建模。Hummel等l分析了近红外光谱与土壤有机质之间的关系，利用多元逐步线性回归建立有机质预测模型。张娟娟等[12建立了基于不同光谱指数的土壤有机质光谱估算模型。任红艳等[13]综合利用可见光-近红外光谱、近红外/中红外光谱结合偏最小二乘回归分析成功地预测了不同区域的土壤有机碳、全氮的含量。李伟等[[4同时利用偏最小二乘法和人工神经网络法建立了黑土的碱解氮、速效磷、速效钾含量的预测模型，发现人工神经网络法有一个更好的建模效果。

高光谱遥感凭借其高分辨率等优点，能够更好地反演土壤组分特征，更有利于土壤养分的遥感估算。关于高光谱遥感监测土壤的研究，大多借鉴红外光谱遥感技术研究的经验，在原有的遥感光谱模型基础上进行改进。刘华等[15]、王维等[16]、贺军亮等[17]都对不同环境背景下的土壤重金属高光谱特征进行了较为细致的研究，均得到不错的效果。陈东强等[18]基于高光谱技术研究了准噶尔盆地人工林全盐含量，进而了解土地退化程度。李民赞[19]对不同环境背景下的土壤有机质高光谱特征进行了细致的研究。自前高光谱遥感监测土壤组成的常用统计分析方法有多元逐步回归分析[20]、偏最小二乘回归分析[2]、人工神经网络分析[21]。大量研究证明这3种方法在高光谱遥感建模上具有适用性。新疆因其独特的气候特征和地理环境条件，形成了典型的山地-绿洲-荒漠系统[22]。对于这种特殊景观的土壤属性高光谱研究并不多，且多集中于土壤盐渍化层面[7,18,23]，而关于新疆土壤养分的高光谱研究尚不多见。使用目前已有的高光谱经验模型无法精确反演新疆地区的土壤组分和属性状况[2]。本研究以新疆艾比湖流域不同地表覆盖类型的土壤养分为研究对象，通过光谱变换技术进行优化处理，选取多元逐步回归分析(stepwise multiple linear regression,SMLR)、偏最小二乘法分析(partial least squares regression,PLSR)和人工神经网络分析(artificialneuralnetwork,ANN)3种方法进行高光谱模型建立，试图通过分析3种模型的稳定性和准确性，探求艾比湖流域土壤养分高光谱反演的适宜性和可能性，以期得到能反演土壤养分空间分布状况和动态变化特征的最佳模型，为艾比湖流域人工绿洲的稳定、农业发展以及荒漠化治理提供科学依据。

# 1材料与方法

# 1.1 土壤样品采集

本研究以天山北坡艾比湖流域的精河县$( { 8 1 ^ { \circ } 4 6 ^ { \prime } 8 3 ^ { \circ } 5 1 ^ { \prime } \mathrm { E } }$ 5 $4 4 ^ { \circ } 0 2 ^ { \prime } { \sim } 4 5 ^ { \circ } 1 0 ^ { \prime } \mathrm { N } _ { \prime }$ 为试验点。该区属于典型的干旱荒漠型大陆性气候，年均降水仅有 $9 0 . 9 \ \mathrm { m m }$ 而年均蒸发量高达 $1 4 2 3 . 9 \ \mathrm { m m } .$ 。年均气温为 $8 ~ \mathrm { { ^ \circ C } }$ 5多大风天气，是西北沙尘暴重要源区之一。精河县地形复杂，三面环山(婆罗科努山、科古琴山、阿拉套山)，东北面与准噶尔盆地相连接，形成了由南和西南向北倾斜的艾比湖为底中心的盆地，平原多为山前坡积洪积平原，广阔起伏，上面广泛分布着砾质戈壁、风积沙丘和盐碱沼泽，是典型的山地-绿洲-荒漠系统。土壤类型众多，地表覆盖类型复杂，包括灰棕漠土、灰漠土、草甸土、沼泽土、潮土、灌淤土、风沙土和盐土8种土壤类型。于2015年8月，选取梭梭(Haloxylon ammodendron)、芦苇(Phragmitesaustralis)、胡杨(Populuseuphratica)、枸杞(Lyciumbarbarum)棉花(Anemone vitifolia)、沙地桑(Morus alba)、罗布麻(Apocynum venetum)等 15 种不同地表覆盖类型,样地基本信息见表1。样地选取不仅考虑具有代表性的覆盖类型，还考虑了空间分布。本研究的样地选取位于精河县人工绿洲规划区和生态修复区，集中于精河县中部和东北部平原地区，围绕G312 干线，避免过多的人为扰动，大多选取在距离公路超过 $1 ~ \mathrm { k m }$ 处，见图1。在各样地进行土壤剖面调查，每个样地挖取 5个 $1 0 0 ~ \mathrm { c m }$ 深的土壤剖面(重复试验),使用 $1 0 0 ~ \mathrm { c m } ^ { 3 }$ 环刀分5层分层取样，再用小铲子每个样取土 $1 ~ \mathrm { k g }$ ，同时使用手持式GPS仪对每个采样点的经纬度和海拔进行记录。土样经自然风干完全后，研磨、去除砂粒、石块和植物残体，用 $0 . 2 5 \mathrm { \ m m }$ 孔隙的筛子进行筛选。将处理好的土样分为3份，分别用于光谱分析、化学测量和保存备用。

表1试验调查样地的基本信息Table 1Information of the investigated sample plots  

<html><body><table><tr><td>样地编号 Sanupleplot</td><td>经纬度 Latitgdeuand</td><td>海拔 Altude</td><td>土壤类型 Agrotype</td><td>土地利用类型 Land-use type</td><td>地表覆盖类型(主要植物类型) Land cover type (major plants)</td></tr><tr><td>1#</td><td>83019E</td><td>123</td><td>Soonchak</td><td>Pastre and</td><td>Nitraria白刺、梭梭、麻黄、Caragand korshinskii,Ephedra sinica,Calligonum arborescens</td></tr><tr><td>2#</td><td>83°09'E, 44°37'N</td><td>211</td><td>沼泽土 Bog soil</td><td>水域 Water area</td><td>芦苇、盐节木、盐爪爪 Phragmites australis,Halocnemumstrobilaceum, Kalidium</td></tr><tr><td>3#</td><td>83°29'E, 44°33'N</td><td>369</td><td>灰漠土 Gray desert soil</td><td>未利用土地 Unused land</td><td>白刺、梭梭、柽柳、胡杨 Nitraria tangutorum,Haloxylon ammodendron,Tamarix</td></tr><tr><td>4#</td><td>83°41'E, 44°36'N</td><td>330</td><td>潮土 Fluvo-aquic soil</td><td>草地 Pasture land</td><td>hohenackeri,Populuseuphratica 罗布麻、芦苇 Apocynum venetum,Phragmites australis</td></tr><tr><td>5#</td><td>44N</td><td>294</td><td>Aeoli风ady oil</td><td>u用土地</td><td>U无植被ed</td></tr><tr><td>6#</td><td>83012'E</td><td>225</td><td>Gray o棕ert soil</td><td>Culivate and</td><td>Haloxylon梭、io</td></tr><tr><td>7#</td><td>856E</td><td>324</td><td>Grayset soil</td><td>Cultivate ad</td><td>ruthenica,Halogetonglomeratus Lyciumbarbarum</td></tr><tr><td>8#</td><td>8256</td><td>382</td><td>Grat soil</td><td>Foresttand</td><td>Haloxylon梭modendron</td></tr><tr><td>9#</td><td>8257E</td><td>374</td><td>ntropognc-alvialsil</td><td>Fostand</td><td>Populusili Tamarix hohenackeri</td></tr><tr><td>10#</td><td>82°57'E, 44°35'N</td><td>354</td><td>草甸土 Meadow soil</td><td>草地 Pasture land</td><td>沙枣、沙拐枣 Elaeagnus angustifolia,Calligonum arborescens</td></tr><tr><td>11#</td><td>82°45'E, 44°31N</td><td>344</td><td>灌淤土 Anthropogenic-alluvial soil</td><td>耕地 Cultivated land</td><td>沙地桑 Moru salba</td></tr><tr><td>12#</td><td>4244 82°46'E,</td><td>372</td><td>Acoli风dy soil 灌淤土</td><td>u用土地 耕地</td><td>Haloxylon爪tobleu Kalidium foliatum</td></tr><tr><td>13#</td><td>44°31N</td><td>350</td><td>Anthropogenic-alluvial soil Soonchak</td><td>Cultivated land</td><td>棉花 Anemonevitifolia</td></tr><tr><td>14#</td><td>8241 82°38'E,</td><td>330</td><td>灌淤土</td><td>Forest tand 耕地</td><td>Popu小u smonil 枸杞</td></tr><tr><td>15#</td><td>44°33'N</td><td>310</td><td>Anthropogenic-alluvial soil</td><td>Cultivated land</td><td>Lycium barbarum</td></tr></table></body></html>

# 1.2土壤养分含量测定

将各取样点的土壤样品带回实验室，使用恒温105 $\mathrm { { } ^ { \circ } C }$ 干燥箱烘干至恒重，测得容重。将已去除杂质、烘干的土壤溶于蒸馏水中，用pH计测土壤 $\mathrm { p H } _ { \circ }$ 土壤全盐含量的测定使用残渣-烘干质量法[24]，土壤有机质含量的测定采用重铬酸钾容重-外加热法进行测定[24]，全氮含量则选用最常用的凯氏定氮法[24]。表2为不同样点土壤样本的基本性质，包括土壤容重、

![](images/6fc73946fe2388b1f01fd662b877346bb58e60db311e44e770412411c49236bf.jpg)  
图1研究区及采样点示意图 Fig.1Location of the research area and distribution of sample plots

$\mathsf { p H }$ 、总盐等基本参数。

# 1.3土壤光谱采集及预处理

光谱分析采用美国ASD公司生产的FieldSpec3地物光谱仪。光谱仪重采样间隔为 $1 \ \mathrm { n m }$ ，共输出2151个波段。试验采用暗室试验，试验时将土壤均匀放置在盛样皿内，保持土层厚度约为 $2 \ \mathrm { c m }$ 。为减少试验土样每个方向的异质性，测量时分别在盛样皿 $0 ^ { \circ }$ 、 $9 0 ^ { \circ }$ 、 $1 8 0 ^ { \circ }$ 和 $2 7 0 ^ { \circ }$ 方位各采集3条样本线，每个土样都采集12条样本光谱数据，进行算术平均所得值构成曲线则为光谱曲线，同时在每次测试之前光谱仪都需进行白板标定[25]。光谱采集试验选择室内进行而不采用野外实地测量，是因为实测光谱数据容易受外界影响(植被覆盖、土壤水分、大气条件等)，尤其是研究地精河县大风天气频发，扬尘较多，选择室内进行试验可控性强，易获得稳定的光谱数据。

表2研究区各采样点土壤基本性质Table 2Basic properties of soil samples of soil sample plots  

<html><body><table><tr><td>样地编号 Sample plot number</td><td>容重 Bulk density (g·cm-3)</td><td>pH</td><td>总盐 Total salinity (g:kg-1)</td><td>有机质 Organic matter (g·kg-1)</td><td>全氮 Total nitrogen (g:kg-1)</td></tr><tr><td>1#</td><td>1.160±0.028</td><td>8.090±0.355</td><td>2.40±0.324</td><td>4.468±0.114</td><td>0.191±0.090</td></tr><tr><td>2#</td><td>1.519±0.031</td><td>7.730±0.075</td><td>14.78±0.870</td><td>4.252±0.072</td><td>0.114±0.012</td></tr><tr><td>3#</td><td>1.196±0.070</td><td>7.620±0.219</td><td>19.70±0.957</td><td>4.980±0.077</td><td>0.420±0.015</td></tr><tr><td>4#</td><td>1.375±0.024</td><td>8.352±0.089</td><td>27.60±0.843</td><td>3.359±0.153</td><td>0.190±0.011</td></tr><tr><td>5#</td><td>1.543±0.025</td><td>7.534±0.051</td><td>3.52±0.642</td><td>0.402±0.068</td><td>0.190±0.021</td></tr><tr><td>6#</td><td>1.621±0.077</td><td>7.552±0.089</td><td>4.78±0.259</td><td>0.843±0.037</td><td>0.038±0.008</td></tr><tr><td>7#</td><td>1.752±0.070</td><td>7.466±0.078</td><td>7.10±0.442</td><td>2.991±0.137</td><td>0.114±0.016</td></tr><tr><td>8#</td><td>1.604±0.050</td><td>8.202±0.390</td><td>0.88±0.148</td><td>2.294±0.128</td><td>0.114±0.013</td></tr><tr><td>9#</td><td>1.157±0.065</td><td>7.958±0.165</td><td>8.10±0.447</td><td>2.244±0.095</td><td>0.191±0.015</td></tr><tr><td>10#</td><td>1.156±0.056</td><td>7.744±0.151</td><td>17.30±0.949</td><td>3.827±0.168</td><td>0.114±0.010</td></tr><tr><td>11#</td><td>1.407±0.068</td><td>8.428±0.328</td><td>3.08±0.228</td><td>3.763±0.098</td><td>0.190±0.014</td></tr><tr><td>12#</td><td>1.041±0.044</td><td>8.718±0.245</td><td>2.20±0.235</td><td>1.683±0.093</td><td>0.114±0.019</td></tr><tr><td>13#</td><td>1.442±0.067</td><td>8.522±0.286</td><td>3.80±0.265</td><td>4.385±0.186</td><td>0.152±0.004</td></tr><tr><td>14#</td><td>1.805±0.039</td><td>7.796±0.154</td><td>10.34±0.820</td><td>0.457±0.025</td><td>0.114±0.010</td></tr><tr><td>15#</td><td>1.593±0.049</td><td>8.542±0.067</td><td>1.88±0.228</td><td>12.200±0.298</td><td>0.649±0.028</td></tr></table></body></html>

尽管在样本光谱数据采集之前，土壤已经过风干、研磨、过筛等处理，但由于不同土壤类型矿物组成等属性不同导致土壤样品的颗粒大小有细微差别，影响吸光度的大小而干扰光谱信息的分析和提取[26]。为减少光谱测定过程中的误差，往往对土壤原始样本进行去噪、重采样处理。有研究表明，光谱不同形式变化能降低背景、样品粗糙度等因子的干扰[27]。本研究采用 $1 0 \ \mathrm { n m }$ 间隔重采样去噪，重采样后能获取215个波段数组成的光谱曲线，在更加平滑的同时仍能维持原光谱的形状特征。为扩大样本之间的光谱特征差异，更有效分析高光谱特征与土壤有机质、全氮之间的关系，本研究对光谱反射率进行一阶微分、二阶微分变换，有研究表明光谱变换技术能显著提高高光谱反演的稳定性和精确性[28]。

通过对所测土壤光谱反射率及其相关变换形式与土壤养分含量的逐波段相关分析，对光谱数据进行降维处理，除去无效信息。选取相关系数较大波段，作为待建模因变量，避免了模型过于复杂而不能快速达到预测效果。

# 1.4高光谱模型建立和精度验证

# 1.4.1 模型建立

多元逐步回归分析(SMLR)根据方差分析结果选取效果较好的自变量进入方程进行建模，能够将$F$ 值较小的变量剔除，达到较好的建模效果，是自前解决多元线性问题最常用的方法[2]。本研究的SMLR模型是采用SPSS19处理得到的。偏最小二乘法分析(PLSR)模型是目前高光谱反演建模选用较多、效果较好的回归模型，汇集典型相关、主成分和多元线性回归3种分析方法优点[2,21,29]，能够最大程度地提取数据变异信息，特别适合多变量高线性相关的数据分析；所建模型能简化方程，并且保留大量信息，提高运算速度[30]。本研究的PLSR 模型建立是采用Minitab17拟合实现的。BP神经网络是人工神经网络(ANN)中运用最广泛的算法，大量研究证明ANN模型中的BP神经网络算法能够很好地利用光谱特征反演土壤组分[21,29]。ANN模型也需要相关系数法先进行波段筛选，过多的波段会使网络结构复杂，导致计算量大、收敛慢等问题[29]。ANN模型涉及多套方案的比较和筛选，具有同时处理线性和非线性关系的能力[21]。本研究的 ANN 模型建立使用 DPS 7.05。

# 1.4.2 模型精度验证

本研究主要采用决定系数 $( R ^ { 2 } )$ 和均方根误差(RMSE)来进行模型效果验证，回归模型的评价采用方差分析法。 $R ^ { 2 }$ 对自变量和因变量之间关系进行验证，很好地反映模型自身的稳定性， $R ^ { 2 }$ 较大时，模型较稳定；RMSE能够表达拟合数据偏离真实值的程度，是反映模型监测能力的重要指标，当RMSE较小时，模型精度较高，预测能力较强。所以模型的 $R ^ { 2 }$ 越大，RMSE越小，模型的稳定性越好,预测精度也越高[31]。本研究的 $R ^ { 2 }$ 和RMSE 计算以及模型拟合分布图像的绘制均由MicrosoftExcel2007实现。

# 2 结果与分析

# 2.1土壤养分空间分析及与光谱的相关性分析

由表2土样基本性质可知不同地表覆盖类型土壤养分的含量差异较大。2种养分的最大值均出现在 $1 5 \#$ 样地，土壤有机质和全氮含量分别达 $1 2 . 2 0 0 ~ \mathrm { g { \cdot k g } ^ { - 1 } }$ 和 $0 . 6 4 9 \ \mathrm { g { \cdot k g } ^ { - 1 } }$ ；其次是3#样地，而5#、6#和14#样地2种土壤养分含量都相对较低。

经过相关系数法处理得到，土壤有机质和全氮含量与光谱原始反射率、一阶微分和二阶微分之间的相关系数如图2所示。

![](images/25fddeb0d79707280b107d4b3e26d66cd56031d6f156442e9797a056f2df7f3d.jpg)  
图2土壤有机质(a)和全氮(b)含量与光谱反射率及其一阶微分和二阶微分的相关性 Fig.2Correlationbetweensilorganc materontet (a),totaltrogencontet (b)andrigial,firstrderdieretialand second-order differential soil spectroscopy

两种养分和原光谱反射率的负相关都集中在$3 5 0 { \sim } 4 7 0 \mathrm { n m }$ 处，并都在 $1 8 8 0 { \sim } 1 8 9 0 \mathrm { n m }$ / $1 9 8 0 { \sim } 2 0 0 0 \mathrm { n m }$ 和 $2 ~ 1 4 0 { \sim } 2 ~ 2 3 0 ~ \mathrm { \ n m }$ 处有较好的正相关性，全氮的相关性略高于有机质；有机质和全氮与一阶微分光谱变换形式的相关性较高波段集中于 $6 5 0 { \sim } 8 4 0 \ \mathrm { n m }$ 和$8 8 0 { \sim } 9 2 0 ~ \mathrm { n m }$ 处，且两者最好相关性波段都为 $8 9 0 ~ \mathrm { n m }$ 有机质的相关性达0.87，全氮的则高达0.91；两种物质与光谱二阶变换形式相关性较高波段相对分散，其中有机质在 $1 4 1 0 \ \mathrm { n m }$ 处正相关最高达0.81，负相关最高只有0.70出现在 $1 \ 1 2 0 \ \mathrm { n m }$ 处。而全氮则在

$7 7 0 \mathrm { n m }$ 1 $1 \ 0 1 0 \ \mathrm { n m }$ 和 $2 \ : 4 3 0 \ : \mathrm { n m }$ 处呈现较好的正相关，相关性最高达0.78，负相关较好处在 $7 4 0 ~ \mathrm { n m }$ 人 $1 0 3 0 ~ \mathrm { n m }$ 处，相关性0.79。

从图2可明显看出，两种土壤养分与光谱数据相关性基本一致，两种养分实测数据间的相关性也达0.85。有研究表明，土壤有机质含量与全氮含量之间存在密切的关系，水稻土全氮含量可以用有机质含量乘以转换系数0.065获取，干旱地区的转换系数为 $0 . 0 5 { \sim } 0 . 0 6 ^ { [ 3 2 ] }$ 。两种养分相关性略有差异是由于高光谱反演基于各种不同化学键位的吸收，而不同物质组成导致两种养分含量在敏感波段上出现一定的差异性[19]。

# 2.2 多元逐步回归建模

对土壤养分与反射光谱及其变换形式之间进行相关分析，不同变换形式光谱与土壤养分的较大相关系数所对应波段通常作为预测土壤养分的敏感波段，故选取各形式相关系数较大的波段作为自变量，以有机质含量和全氮含量作为因变量进行多元逐步线性回归分析，获得光谱原始反射率、光谱一阶微分及二阶微分的SMLR模型以及SMLR模型所得预测值与养分实测值之间关系如表3所示。光谱反射率的一阶微分和二阶微分变换形式所得到的 $R ^ { 2 }$ 和RMSE均优于光谱原反射率的值，其中二阶微分略优于一阶微分。有机质和全氮二阶微分所建模型的$R ^ { 2 }$ 分别达0.803和0.852,RMSE只有1.361和0.066,能够很好地预测土壤有机质和全氮两种养分状况。一阶微分建模所得 $R ^ { 2 }$ 也能达到0.768和0.835，对应的RMSE也只有1.42和0.064，也能相对较好地预测土壤养分。而光谱原反射率所建模型则相对较差不能得到稳定精确的预测值。比较两种养分的预测情况，全氮的拟合效果优于有机质，高光谱对全氮的敏感性强于有机质。

表3土壤养分多元逐步回归分析结果  
Table 3Test results of stepwise multiple linear regression (SMLR) model for soil nutrient contents   

<html><body><table><tr><td>土壤养分 Soil nutrient</td><td>光谱变换形式 Transform form of spectrum</td><td>多元逐步回归模型 Stepwise multiple linear regression model</td><td>决定系数 Coefficient of determination</td><td>总均方根误差 Root mean square error</td></tr><tr><td>有机质 Organic matter</td><td>光谱反射率 Original soil spectroscopy</td><td>Y=24.193X1880-7.679</td><td>0.486</td><td>2.113</td></tr><tr><td rowspan="6">全氮 Total nitrogen</td><td>光谱反射率一阶微分 First-order differential soil spectroscopy</td><td>Y=28 903.701X890+3.072</td><td>0.768</td><td>1.420</td></tr><tr><td>光谱反射率二阶微分</td><td>Y=-3 554.960X1000+</td><td>0.803</td><td>1.361</td></tr><tr><td>Second-order differential soil spectroscopy 光谱反射率</td><td>74 349.124X1410-0.577</td><td></td><td>0.093</td></tr><tr><td>Original soil spectroscopy 光谱反射率一阶微分</td><td>Y=-0.151-1.053X39+1.517X1990</td><td>0.627</td><td></td></tr><tr><td>First-order differential soil spectroscopy</td><td>Y=0.170+1 611.122X890</td><td>0.835</td><td>0.064</td></tr><tr><td>光谱反射率二阶微分 Second-order differential soil spectroscopy</td><td>Y=0.274-1 492.812X1030- 5 786.504X610+10 819.675X770</td><td>0.852</td><td>0.066</td></tr></table></body></html>

$X _ { N }$ 表示 N\~N+9 (nm)波段的算术平均数。 $X _ { N }$ indicates the arithmetic mean of $N$ to $N { + } 9$ $( \mathrm { n m } )$ waveband.

# 2.3 偏最小二乘法建模

基于PLSR模型土壤养分实测值与预测值的拟合分布如图3。选取建模波段为自变量，以土壤养分为因变量进行PLSR分析，针对光谱原始反射率、一阶和二阶微分变换形式进行建模。反射率一阶微分和二阶微分变换形式所建模型优于原反射光谱所建模型，说明光谱变换技术能显著提高模型的预测精度和稳定性。有机质和全氮的二阶微分建模所得 $R ^ { 2 }$ 分别为0.881和0.956，为3种建模方式中最优,RMSE分别只有2.706和0.045，能达到很好的预测效果。同时，一阶微分建模形式的 $R ^ { 2 }$ 也能达到0.814和0.877，也能得到较好的预测效果，而原光谱建模的预测效果较差，两种土壤养分的预测模型 $R ^ { 2 }$ 分别只有0.490和0.673。基于PLSR模型的光谱一阶微分建模和二阶微分建模都能很好地预测土壤养分值。3种建模方式得到的全氮的精度都优于有机质，说明高光谱遥感对全氮的反演效果强于有机质。

# 2.4 人工神经网络建模

基于BP神经网络分析建立的ANN模型的土壤养分实测值与预测值的拟合分布见图4。选取建模波段作为自变量，以土壤养分值作为因变量进行BP神经网络分析，建立原始光谱、反射率一阶微分和二阶微分变换形式的分析模型。由图4可得二阶微分变换形式建立的模型最优，有机质和全氮二阶微分建模 $R ^ { 2 }$ 分别达0.886和0.984，优于一阶微分建模的0.873和0.968以及原始光谱建模的0.486和0.516,而反射率二阶微分建模的RMSE也分别只有2.614和0.147。说明二阶微分的ANN模型具有很好的预测能力，一阶微分模型也具有较好的预测能力，而原始光谱模型的精度和稳定性相对较差。对比有机质和全氮的3种光谱形式模型，得到与PMLR、PLSR模型类似的结果，仅有机质原始光谱反射率的稳定性强于全氮，其他所有指标均劣于全氮，全氮的高光谱反演效果优于有机质。

# 3 结论与讨论

土壤光谱反射率是土壤特征研究的重要指标之一，是土壤遥感的物理基础，依靠其分辨率高等优点已经得到广泛应用。探讨土壤光谱与土壤养分之间的关系，使用不同数学方法建立模型并选择最优模型，有助于提高土壤养分遥感定量反演和预测的精度。本研究通过对研究区土壤样品的光谱数据进行去噪、重采样等预处理，并对土壤高光谱反射率进行一阶微分和二阶微分形式的变换，对比多元逐步回归分析、偏最小二乘法回归分析以及人工神经网络分析3种方法与土壤养分特征关系的研究，得到以下结论。

![](images/3d9053e4e19180e42585df1d206addc09b85ccc2c30700756abf3065000c97eb.jpg)  
图3土壤有机质 $( \mathbf { a } , \mathbf { b } , \mathbf { c } )$ 和全氮(d,e,f)反射率(a,d)、反射率一阶微分 $( \boldsymbol { \mathbf { b } } , \boldsymbol { \mathbf { e } } )$ 和反射率二阶微分(c,f)与偏最小二乘回归析预测值之间的拟合分布

![](images/0aee61d7a8abaaf080c34a77270940d390b8234cae58d99b32a519f65c7cb2c8.jpg)  
Fig.3Fitigdistrbtionetenoiginal(d),istderderetal(,e)andsecondorderdrential(fofasdil spectroscopyofsoilrgaicmatercontents(a,bcandtotalnitrogenontents(d,e,f)andpredictedvauesbypartialleastsars regression (PLSR) model   
图4土壤有机质 $( \mathbf { a } , \mathbf { b } , \mathbf { c } )$ 和全氮(d,e,f)反射率(a,d)、反射率一阶微分 $( \mathbf { b } , \mathbf { e } )$ 和反射率二阶微分 $( \mathbf { c } , \mathbf { f } )$ 与人工神经网络分析 的预测值之间的拟合分布 Fig.4Fitingistrbuonbetweoginal(d),firstderdereal(b,e)andseondderdereal(cfofeasudol spectroscopyofsoilorganicmatercontents(,b,c)andtotalnitrogencontents (d,e,f)andpredictedvaluesbyartificialneural network(ANN) model

1)在3种模型中，反射率一阶微分和二阶微分能显著提高光谱与土壤养分之间的相关性，所得到的预测效果也均优于原光谱反射率，其中二阶微分的预测效果最佳，能很好地预测研究区的土壤养分状况。一阶微分形式次之，也能较好地预测土壤有机质和全氮含量。说明光谱变换形式能消除实验噪声等误差影响，提高光谱与土壤养分间的敏感性。这与前人研究结果一致，尤其是光谱的二阶微分变换[18]和一阶微分变换[33]在提升光谱和土壤组分之间敏感性上效果明显。

2)3种高光谱模型都能较好地预测艾比湖流域不同土壤覆盖类型的养分状况。但从建模稳定性和精度上而言，ANN模型最优,PLSR模型次之，SMLR模型最差。其中全氮基于ANN 模型的二阶微分模型效果最优，其决定系数达0.984，而均方根误差只有0.147。说明ANN模型在研究区养分预测上具有很好的稳定性和高预测精度。土壤光谱反演是一个复杂的线性和非线性相结合的问题，杨扬等[21通过对三江源地区有机质的高光谱研究也表明，ANN模型更为适合土壤组分监测和土壤质量的监测，但ANN模型是否更为适合其他区域、其他土质、其他土壤组分还有待进一步研究。

3)在3种模型的所有光谱变换形式中，全氮的拟合效果均优于有机质。同一模型中，全氮预测的决定系数更高、总均方根误差更小，说明光谱对全氮的敏感性优于有机质，高光谱对全氮的反演效果更好。

4)土壤有机质和全氮之间相关性较好，达0.85。同时两种养分与光谱数据的相关性也很相似，很多反演波段都很接近甚至一致，因此不同土地覆盖类型土壤养分的光谱反演能否协同预测或采用相同波段进行反演，还有待于进一步研究。

致谢新疆林业科学院宁虎森、罗青红、邹杰3位老师给予本研究帮助，谨表谢意！

# 参考文献 References

[1]黄昌勇．土壤学[M]．北京：中国农业出版社,2000:32-33

Huang C Y. Soil Science[M]. Beijing: China Agriculture Press, 2000: 32-33   
[2] 管延龙，王让会，李成，等．天山北麓土壤有机质高光谱特 征分析[J]．环境科学与技术,2015,38(9):1-6 Guan YL,WangRH,Li C,et al. Study on soil organic matter content from hyper-spectra in the North of Tianshan Mountains[J]. Environmental Science & Technology, 2015, 38(9): 1-6   
[3] 傅华，陈亚明，王彦荣，等．阿拉善主要草地类型土壤有机 碳特征及其影响因素[J]．生态学报,2004,24(3):469-476 Fu H, Chen Y M, Wang YR,et al. Organic carbon content in major grassland types in Alex，Inner Mongolia[J]. Acta Ecologica Sinica,2004,24(3): 469-476   
[4] 武均，蔡立群，齐鹏，等．不同耕作措施下旱作农田土壤团 聚体中有机碳和全氮分布特征[J]．中国生态农业学报, 2015,23(3): 276-284 Wu J,Cai L Q,Qi P,et al. Distribution characteristics of organic carbon and total nitrogen in dry farmland soil aggregates under different tillage methods in the Loess Plateau of central Gansu Province[J].Chinese Journal of Eco-Agriculture,2015,23(3): 276-284 [5]Yang H,Kuang B,Mouazen A M.Quantitative analysis of soil nitrogen and carbon at a farm scale using visible and near infrared spectroscopy coupled with wavelength reduction[J]. European Journal of Soil Science,2012,63(3): 410-420   
[6] Gomez C,Rossel R A V, McBratney AB.Soil organic carbon prediction by hyperspectral remote sensing and field vis-NIR spectroscopy:An Australian case study[J]. Geoderma, 2008, 146(3/4): 403-411   
[7]丁建丽，姚远，王飞．基于三维光谱特征空间的干旱区土 壤盐渍化遥感定量研究[J].土壤学报,2013,50(5):853-861 Ding JL, Yao Y, Wang F. Quantitative remote sensing of soil salinization in arid regions based on three dimensional spectrum Eigen spaces[J].Acta Pedologica Sinica,2013, 50(5): 853-861   
[8] 龚绍琦，王鑫，沈润平，等．滨海盐土重金属含量高光谱遥 感研究[J]．遥感技术与应用,2010,25(2):169-177 Gong SQ,Wang X,Shen RP,et al.Study on heavy metal element content in the coastal saline soil by hyperspectral remotesensing[J]. RemoteSensingTechnologyand Application,2010,25(2): 169-177   
[9] Gozzolino D,Morón A. Potential of near-infrared reflectance spectroscopy and chemometrics to predict soil organic carbon fractions[J]. Soil and Tillage Research,2006,85(1/2): 78-85   
[10]王璐，葡启忠，贾东，等．多光谱数据定量反演土壤营养元 素含量可行性分析[J]．环境科学,2007,28(8):1822-1828 Wang L,Lin Q Z,Jia D,et al. Analysis on possibilities of multi-spectral data for quantitative retrieving soil nutrition element contents[J].Environmental Science，2007,28(8): 1822-1828   
[11] Hummel JW, Sudduth K A,Hollinger S E. Soil moisture and organic matter prediction of surface and subsurface soils using an NIR soil sensor[J]. Computers and Electronics in Agriculture,2001,32(2): 149-165   
[12] 张娟娟，田永超，姚霞，等．基于高光谱的土壤全氮含量估

测[J]．自然资源学报,2011,26(5):881-890 Zhang JJ,Tian Y C,Yao X,et al.Estimating soil total nitrogen content based on hyperspectral analysis technology[J]. Journal of Natural Resources,2011, 26(5): 881-890

[13]任红艳，史学正，庄大方，等．土壤全氮含量与碳氮比的高 光谱反射估测影响因素研究[J]．遥感技术与应用，2012, 27(3): 372-379 Ren H Y, Shi X Z, Zhuang D F,etal. Efects on estimating soil nitrogen content and ratio of carbon to nitrogen using hyperspectral reflectance[J]. Remote Sensing Technology and Application,2012,27(3): 372-379   
[14]李伟，张书慧，张倩，等．近红外光谱法快速测定土壤碱解 氮、速效磷和速效钾含量[J]．农业工程学报，2007，23(1): 55-59 Li W,Zhang S H, Zhang Q，et al. Rapid prediction of available N,P and K content in soil using near-infrared reflectance spectroscopy[J]. Transactions of the CSAE,2007, 23(1): 55-59   
[15]刘华，张利权．崇明东滩盐沼土壤重金属含量的高光谱估 算模型[J]．生态学报,2007,27(8):3427-3434 Liu H, Zhang L Q.A predictive model for the hyperspectral character of saltmarsh soil to its heavy metal content at Chongming Dongtan[J]. Acta Ecologica Sinica, 2007, 27(8): 3427-3434   
[16]王维，沈润平，吉曹翔．基于高光谱的土壤重金属铜的反 演研究[J]．遥感技术与应用,2011,26(3):348-354 Wang W, Shen R P, JiC X. Study on heavy metal Cu based on hyperspectral remote sensing[J]. Remote Sensing Technology and Application,2011,26(3): 348-354   
[17]贺军亮，张淑媛，查勇，等．高光谱遥感反演土壤重金属含 量研究进展[J]．遥感技术与应用,2015,30(3):407-412 He JL, Zhang S Y, Zha Y,et al. Review of retrieving soil heavy metal content by hyperspectral remote sensing[J]. Remote Sensing Technology and Application，2015,30(3): 407-412   
[18] 陈东强，王让会．准噶尔盆地人工林地土壤全盐的高光谱 反演[J].干旱区研究,2013,30(3):444-448 Chen D Q,Wang R H. Total soil salinity in artificial forest in the Junggar basin based on hyperspectrum[J]．Arid Zone Research,2013,30(3): 444-448   
[19]李民赞．光谱分析技术及其应用[M]．北京：科学出版社, 2006 Li M Z. Spectral Analysis Technology and Application[M]. Beijing: Science Press,2006   
[20]李娜，吕建升，Altermann W.光谱分析在植被重金属污染 监测中的应用[J]．光谱学与光谱分析，2010，30(9): 2508-2511 Li N, Lü JS,Altermann W. Hyperspectral remote sensing in monitoringthevegetationheavymetalpolution[J]. Spectroscopy and Spectral Analysis,2010,30(9): 2508-2511   
[21]杨扬，高小红，贾伟，等．三江源区不同土壤类型有机质含 量高光谱反演[J]．遥感技术与应用,2015,30(1):186-198 Yang Y, Gao X H, Jia W, et al. Hyperspectral retrieval of soil

organic matter for different soil types in the three-river headwaters region[J]. Remote Sensing Technology and Application,2015,30(1):186-198

ecosystem: A case study of Beitun oasis[J].Arid Land Geography,2009,32(4): 578-584   
[23] 马诺，杨辽，李均力．焉耆盆地土壤盐渍化的光谱特征分 析[J]．干旱区资源与环境,2008,22(2):114-117 Ma N,Yang L,Li JL. Study on hyperspectral distinction of soil salinity:A case study of Yanqi,Xinjiang Province[J]. Journal of Arid Land Resources and Environment,2008, 22(2): 114-117   
[24]鲍士旦．土壤农化分析[M]．北京：中国农业出版社，1999: 30-34 Bao S D.Soil and Agricultural Chemistry Analysis[M]. Beijing:China Agriculture Press,1999:30-34   
[25]彭杰，周清，张杨珠，等．有机质对土壤光谱特性的影响研 究[J]．土壤学报,2013,50(3):517-524 Peng J, Zhou Q, Zhang Y Z, et al. Effect of soil organic matter on spectral characteristics of soil[J]. Acta Pedologica Sinica, 2013,50(3): 517-524   
[26]张娟娟，田永超，姚霞，等．同时估测土壤全氮、有机质和 速效氮含量的光谱指数研究[J]．土壤学报，2012，49(1): 50-59 ZhangJJ,Tian YC,Yao X,et al.The spectral index for estimating soil OM, TN and an content simultaneously using near-infrared spectroscopy[J].Acta Pedologica Sinica, 2012, 49(1): 50-59   
[27]王淼，解宪丽，周睿，等．基于可见光-近红外漫反射光谱 的红壤有机质预测及其最优波段选择[J]．土壤学报，2011, 48(5): 1083-1089 Wang M, Xie $\texttt { X L }$ ，Zhou R,et al.Determination of soil organic matter in red soils using Vis-NIR diffuse reflectance spectroscopy and selection of optimal spectral bands[J]. Acta Pedologica Sinica,2011,48(5): 1083-1089   
[28] 陈红艳，赵庚星，李希灿，等．基于 DWT-GA-PLS 的士壤 碱解氮含量高光谱估测方法[J]．应用生态学报，2013, 24(11): 3185-3191 Chen H Y, Zhao G X, Li X C, et al. Hyper spectral estimation method for soil alkali hydrolysable nitrogen content based on discrete wavelet transform andgenetic algorithmin combining with partial least squares (DWT-GA-PLS)[J]. Chinese Journal of Applied Ecology,2013,24(11): 3185-3191   
[29] 沈润平，丁国香，魏国栓，等．基于人工神经网络的土壤有 机质含量高光谱反演[J]．土壤学报,2009,46(3):391-397 Shen R P, Ding G X, Wei G S,et al. Retrieval of soil organic matter content from hyper-spectrum based on ANN[J]. Acta Pedologica Sinica,2009,46(3): 391-397   
[30]刘秀英，王力，常庆瑞，等．基于相关分析和偏最小二乘回

归的黄绵土土壤全氮和碱解氮含量的高光谱预测[J].应用 生态学报,2015,26(7):2107-2114 Liu X Y,Wang L,Chang Q R,et al.Prediction of total nitrogen and alkali hydrolysable nitrogen content in loess using hyperspectral data based on correlation analysis and partial least squares regression[J].Chinese Journal of Applied Ecology,2015,26(7): 2107-2114 [31]丁建丽，伍漫春，刘海霞，等．基于综合高光谱指数的区域 土壤盐渍化监测研究[J]．光谱学与光谱分析，2012，32(7): 1918-1923 DingJL，Wu M C,Liu H X，et al.Study on the soil salinization monitoring based on synthetical hyperspectral index[J].Spectroscopy and Spectral Analysis,2012,32(7): 1918-1923

[32]赵云，陈伟，李春鸣，等．东祁连山不同退化程度高寒草甸土壤有机质含量及其与主要养分的关系[J]．草业科学，2009,26(5):20-25Zhao Y, Chen W,Li CM, et al.Content of soil organic matterand its relationships with main nutrients on degraded alpinemeadow in Eastern Qilian Mountains[J].Pratacultural Science,2009,26(5):20-25  
[33]高会，陈红艳，刘慧涛，等．基于高光谱的鲁西北平原土壤有效磷含量快速检测研究[J]．中国生态农业学报，2013,21(6): 752-757Gao H,Chen H Y,Liu HT,et al.Spontaneous determinationof soil available phosphorus using high spectrum in theNorthwest Plain of Shandong Province[J].Chinese Journal ofEco-Agriculture,2013,21(6): 752-757