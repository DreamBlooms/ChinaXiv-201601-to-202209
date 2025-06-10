# 21世纪开都-孔雀河流域未来气候变化情景预估

李晓菲}²，徐长春¹²，李路²，宋佳²，张喜成1,2（1．新疆大学资源与环境科学学院,新疆乌鲁木齐830046;2．新疆大学资源与环境科学学院绿洲生态教育部重点实验室,新疆乌鲁木齐830046)

摘要：利用 Downscaled CMIP3 and CMIP5 Climate and Hydrology Projections(DCHP)提供的31个CMIP5 降尺度数据和CRU逐月气温、降水格点数据集,通过评估 PLS（偏最小二乘回归）、RR(岭回归)和EE(等权平均)3种多模式集合平均预估模型对历史气候变化的模拟能力,确定最优集合方法,进而预估开都－孔雀河流域21世纪气候变化情景。结果表明： $\textcircled{1}$ 所建立的PLS模型对流域的气温和降水具有较好的模拟能力，尤其对气温的模拟， $r$ 值均达到了0.64以上，明显优于降水 $( 0 . 1 9 \sim 0 . 3 6 )$ ,但存在空间异质性; $\textcircled{2}$ 21世纪开都-孔雀河流域各子区气温呈显著增加趋势，且RCP8.5情景下的增温速率 $\left[ 0 . 5 8 \sim 0 . 6 7 ~ \mathrm { \% } \cdot \left( 1 0 \mathrm { a } \right) ^ { - 1 } \right]$ 是RCP4.5情景下 $\left[ 0 . 2 5 \sim 0 . 3 1 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ) ~ } ^ { - 1 } \right]$ 的2倍以上,21世纪中叶是2种情景产生明显差异的开始。整个流域增温速率由西北山区向东南荒漠区逐渐增大;$\textcircled{3}$ 未来降水在不同排放情景下变化速率的分布状况略有不同,但均呈显著增加趋势,且RCP8.5 情景下的增加速率 $\left[ 1 . 2 2 \% \sim 1 . 5 4 \% \cdot \left( 1 0 \mathrm { { a } } \right) ^ { - 1 } \right] .$ 1总体上高于 $\mathrm { { R C P 4 . 5 [ 0 . 8 0 \% \sim 1 . 3 2 \% \ \cdot \ ( 1 0 a ) \ ^ { - 1 } \ ] } }$ ○

关键词：降尺度；CMIP5；气温；降水；多模式集合；未来气候变化情景；开都-孔雀河流域

当今,全球气候系统变暖毋庸置疑(1]。IPCC 第五次评估报告（AR5)指出，自1880—2012年，全球地表年平均气温升高了 $0 . 8 5 ( 0 . 6 5 \sim 1 . 0 6 ) \mathrm { ^ { \circ } C }$ ,且未来将持续上升[2]，与此同时，一系列极端气候事件也将伴随发生[3]。近 $3 0 \mathrm { ~ a ~ }$ ,我国干旱半干旱区发生了严重的干旱化倾向，已深刻影响到当地的生存环境，导致诸如水资源严重匮乏、生态环境退化和荒漠化等环境问题[4]。开都－孔雀河流域位于我国西北干旱区，是气候变化响应的敏感地区。过去 $2 0 \mathrm { ~ a ~ }$ 流域水资源短缺问题日益突出，严重制约了当地社会经济的健康快速发展，这其中既有人为因素的影响，也有自然因素的制约。未来，全球气候变暖将进一步加速流域水循环,改变水资源时空分配，从而加剧经济社会用水和生态环境用水之间的矛盾。进行水资源预测，开展开都-孔雀河流域未来气候变化情景预估研究是很有必要的。

全球气候模式(GCMs)是现阶段预测未来气候变化的主要途径[5],近年来取得了迅速发展[。由世界气候研究计划（WCRP）推动的CMIP5气候模式未来预估数据采用了新的排放情景，即典型浓度路径（representative concentration pathways,RCPs）,包括RCP2.6、RCP4.5、RCP6.0和RCP8.5四种情景。与早期的CMIP3相比，CMIP5模式在许多方面都进行了改进，表现在模式水平分辨率、物理过程以及参数化等方面[7-8]。在使用GCM 模式模拟区域气候过程中，由于模式的空间分辨率较低且不统一，通常需要使用降尺度技术将大尺度、低分辨率的模式信息转化为小尺度、高分辨的局地气候要素变化信息，从而获得相对高精度的区域气候情景。

随着气候模式的应用与发展，为了提高模式预报的准确率，多模式集合平均（multi-modelensemblemean，MME)方法受到了越来越多国内外学者的关注[9-10]。其中,等权集合(EE)是最常用的一种集合方法。相关研究表明，等权集合结果与观测值相关性更强,且优于大多数单个模式(11-12]。此外,少数学者使用了加权集合平均，通过对相互独立的观测资料赋予不同的权重系数，来获得预报结果。然而，由于气候模式参数化方案等因素的差异，模式权重系数的确定带有无法避免的主观性，因此至今尚无统一的权重系数确定方法。根据前人的研究对比发现，不同权重系数集合平均模拟效果均优于等权集合平均[13-14]。在此基础上,为了消除降尺度过程中诸多不确定性因素，气象学家们开始着眼于将多模式集合思想引人降尺度技术中去，以获得更好的模式回报效果。结果表明，多模式统计降尺度集合（SDMME）在气候要素模拟上取得了较好的效果[15-16],能够有效降低预估时所存在的不确定性[17-18]。但是此方面的研究在中国开展的还相对较少，尤其在西北干旱区对未来气候预估研究目前主要基于单个气候模式的模拟[19-20],尚缺乏集合研究。

因此，本文拟采用3种多模式统计降尺度集合方法，对开都-孔雀河流域气温和降水进行模拟研究，筛选出模拟能力较好的集合方法，进而预估21世纪流域气候变化，以期提供可信度更高的流域未来气候情景预估结果。

# 1资料与方法

# 1.1 研究区概况

开都-孔雀河流域地处新疆巴音郭楞自治州(简称巴州)境内，包括和静县、和硕县、焉耆县、博湖县、库尔勒市以及尉犁县的部分地区，地形自西北向东南倾斜。该流域深居欧亚大陆腹地，远离海洋，靠近塔克拉玛干大沙漠，是典型的大陆性温带干旱气候,气候特征总体表现为干旱少雨、蒸发能力强、昼夜温差大、日照充足、光热资源丰富等。

# 1.2 数据来源

1.2.1模式资料本文采用的CMIP5 模式资料为经过偏差订正-空间分解技术（bias-correction andspatialdisaggregation，BCSD）降尺度后得到的全球逐月降水和气温数据。此方法能够有效去除全球气候模式在区域尺度上的模拟偏差，在国际上得到了广泛应用。该数据集包括历史模拟试验数据以及未来排放情景下的预估数据，其空间分辨率为 $0 . 5 ^ { \circ } \times$ $0 . 5 ^ { \circ }$ （约 $5 0 ~ \mathrm { k m }$ )。为考虑数据的完整性及其运行试验结果的一致性，本文采用其中的31个模式(表1)“rlilp1"运行结果下的历史模拟数据（1950—2005年）与RCP4.5和RCP8.5两种情景的预估数据（2006—2099年）。该数据可通过“DownscaledCMIP3 and CMIP5 Climate and Hydrology Projections ,DCHP"网页获取,具体细节可参见htps://gdo-dcp.ucllnl.org/downsc-aled_cmip_projections/。

表1基于BCSD降尺度的模式信息  
Tab.1 Information of BCSD-based downscaling models   

<html><body><table><tr><td>编号</td><td>模式名称</td><td>研究机构</td></tr><tr><td>1</td><td>ACCESS1-0</td><td>联邦科学与工业研究组织和气象局（澳 大利亚)</td></tr><tr><td>2</td><td></td><td>ACCESS1-3联邦科学与工业研究组织和气象局（澳</td></tr><tr><td>3</td><td></td><td>大利亚) BCC-CSM1-1中国气象局北京气候中心(中国)</td></tr><tr><td>4</td><td></td><td>BCC-CSM1-1-M 中国气象局北京气候中心(中国)</td></tr><tr><td>5</td><td>BNU-ESM</td><td>北京师范大学全球变化与地球系统科学</td></tr><tr><td>6</td><td>CanESM2</td><td>学院(中国) 加拿大气候模拟与分析中心(加拿大)</td></tr><tr><td>7</td><td>CCSM4</td><td>美国国家大气研究中心(美国)</td></tr><tr><td>8</td><td>CESM1-BGC</td><td>美国国家大气研究中心(美国)</td></tr><tr><td>9</td><td>CESM1-CAM5</td><td>美国国家大气研究中心(美国)</td></tr><tr><td>10</td><td>CMCC-CM</td><td>意大利地中海气候研究中心(意大利)</td></tr><tr><td>11</td><td>CNRM-CM5</td><td>法国气象研究中心(法国)</td></tr><tr><td>12</td><td></td><td>CSIRO-Mk3-6-0 澳大利亚联邦科学与工业研究组织（澳</td></tr><tr><td>13</td><td>FGOALS-g2</td><td>大利亚) 中国科学院大气物理研究所(中国)</td></tr><tr><td>14</td><td>FIO-ESM</td><td>国家海洋局第一海洋研究所(中国)</td></tr><tr><td>15</td><td>GFDL-CM3</td><td>美国地球物理流体动力学实验室(美国)</td></tr><tr><td>16</td><td>GFDL-ESM2G</td><td>美国地球物理流体动力学实验室(美国)</td></tr><tr><td>17</td><td>GFDL-ESM2M</td><td>美国地球物理流体动力学实验室(美国)</td></tr><tr><td>18</td><td>GISS-E2 - R</td><td>美国地球物理流体动力学实验室(美国)</td></tr><tr><td>19</td><td></td><td>HadGEM2-AO 英国气象局,哈德莱中心(英国)</td></tr><tr><td>20</td><td>INMCM4</td><td>俄罗斯数值模拟研究所(俄罗斯)</td></tr><tr><td>21</td><td></td><td>IPSL-CM5A-LR法国 Pierre-Simon Laplace 研究所(法国)</td></tr><tr><td>22</td><td></td><td>IPSL-CM5 A-MR 法国 Pierre-Simon Laplace 研究所（法国）</td></tr><tr><td>23</td><td></td><td>IPSL-CM5B-LR法国 Pierre-Simon Laplace 研究所(法国）</td></tr><tr><td>24</td><td>MIROC5</td><td>大气海洋研究所，国家环境研究所和日本</td></tr><tr><td>25</td><td>MIROC-ESM</td><td>海洋地球科学技术研究所(日本) 大气海洋研究所，国家环境研究所和日本</td></tr><tr><td></td><td></td><td>海洋地球科学技术研究所(日本) 26MIROC-ESM-CHEM大气海洋研究所，国家环境研究所和日本</td></tr><tr><td></td><td></td><td>海洋地球科学技术研究所(日本)</td></tr><tr><td>27</td><td>MPI-ESM-LR</td><td>德国马科斯·普朗克气象研究所(德国)</td></tr><tr><td>28</td><td>MPI-ESM-MR</td><td>德国马科斯·普朗克气象研究所(德国)</td></tr><tr><td>29</td><td>MRI-CGCM3</td><td>日本气象研究所(日本)</td></tr><tr><td>30 31</td><td>NorESM1-M NorESM1-ME</td><td>挪威气候中心(挪威) 挪威气候中心(挪威)</td></tr></table></body></html>

1.2.2观测资料为评估模式资料对流域气温和降水的模拟能力，采用东英吉利大学气候研究所(ClimaticResearchUnit,CRU)2017年9月发布的数据集( $\mathrm { T S \ v { 4 . 0 1 } }$ ,空间分辨率 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ } ,$ 进行资料验证。为便于对比分析，选取的时间跨度与模式历史模拟资料(1950—2005 年)保持一致。CRU仅使用了简单的数学方法对地面观测站和其他辅助性数据源进行整合和插值，重建了一套覆盖完整、高分辨率，且无缺测的月平均地表气候要素数据集。该

# 表2CRU气温、降水数据与同期开都-孔雀河流域5个站点观测数据的相关系数

Tab.2 Correlation coefficients between CRU data and observed data of air temperature and precipitation in theKaidu-Kongqi River Basin   

<html><body><table><tr><td>站点</td><td>巴音布鲁克</td><td>巴伦台</td><td>焉耆</td><td>库尔勒</td><td>铁干里克</td></tr><tr><td>气温</td><td>0.983 *</td><td>0.983 *</td><td>0.995 *</td><td>0.997 *</td><td>0.998 *</td></tr><tr><td>降水</td><td>0.337 *</td><td>0.589 *</td><td>0.557 *</td><td>0.168 *</td><td>0.890 *</td></tr></table></body></html>

注： $*$ 表示通过了置信度为 $9 5 \%$ 的显著性检验。下同。

资料对现有资料均有很大的改进，是一套较为完整的中国百年尺度气候变化数据集，被广泛应用于区域气候变化分析[21]。为评估该数据集在开都－孔雀河流域的适用性，分析了1961—2005年CRU逐月气温、降水数据与同期流域5个站点（巴音布鲁克、巴伦台、焉耆、库尔勒、铁干里克)观测数据之间的相关系数(表2）。可以看出，CRU气温和降水资料与5个站点资料具有很好的相关性，均通过了$9 5 \%$ 的显著性检验，其中气温之间的相关性均在0.983以上，最高达0.998。相对气温而言，降水明显要低，其相关系数均在0.168以上，最高达0.890。以上结果表明，CRU资料在开都-孔雀河流域具有较高的适用性，可用于该流域气候变化分析。

# 1.3 研究方法

开都-孔雀河流域水汽主要来源于湿润的西风环流及北冰洋气流，水汽受天山山脉及多条平行山脉的阻截作用，加之地形走势差异，流域上、中、下游气候特征存在明显差别。上游山区气候特征主要表现为气温相对较低和降水量较大，中游平原丘陵区（主要为开都河、孔雀河和博斯腾湖分布区)地势相对平坦，气温较上游偏高，但降水量明显减少，至下游荒漠区降水则更为匮乏，最低处（位于孔雀河尾闾罗布泊)年降水量不足 $2 5 ~ \mathrm { m m }$ 。考虑到不同区域其气候变化过程与机理存在的差异性以及不同模式的模拟效果因地区的不同而产生差异，本文参照中国 $1 \colon 4 0 0 0 0 0 0$ 数字地貌数据集[22],将整个流域划分为4个子区（sub-basin，SB），分别命名为：SB1、SB2、SB3和SB4（图1）。SB1为流域海拔最高区，地形起伏较大，大部分为山地；SB2和SB3为中海拔区，其中SB2以平原为主要地貌类型，四面环山，地形波动较小，而SB3地形较为多变，多以丘陵和山地为主;SB4位于流域的下游区，地形最为平坦，地貌类型简单，平原覆盖面广。流域海拔总体趋势表现为由西北部向东南部逐渐降低，最高可达4666$\mathrm { ~ m ~ }$ ,最低处仅为 $7 7 0 \mathrm { ~ m ~ }$ 。

在子区划分的基础上，重点分析降尺度后的31个全球气候模式在等权重与加权重下多模式集合平均结果。采用偏最小二乘回归（partial least squaresregression,PLS）与岭回归（ridgeregression,RR)法来确定各个模式的权重，两者均能有效解决自变量间因存在多重共线性问题而使预测结果不尽人意的情况。其中，偏最小二乘回归分析在建模过程中集中了主成分分析、典型相关分析和线性回归分析等方法的特点,使得信息更加深入、丰富[23]。而岭回归是改良的最小二乘算法，能够处理最小二乘法求解系数向量时所碰到的矩阵无法求逆问题[24]。因此,

![](images/3705b8451b0e3995b0a9b04dd032e82b193db47052fec01f23f218db9ca52e79.jpg)  
图1开都-孔雀河流域高程及子流域划分  
Fig.1The elevation and sub-basin division map of the Kaidu-Kongqi River Basin

(a)气温 +PLS(SB1)+PLS(SB2)+PLS(SB3)+PLS(SB4)0.16 RR(SB1) -RR(SB2) -RR(SB3) -RR(SB4)王牛0.12 丰0.08 + -++二 +HI 一丰+ +干 +‡+  
重 0000 丰+ 丰士 二丰 1 +二 土土‡= + #- 三 二+- 丰+圭 1 += ±+ + =圭-0.08 土 1(b)降水0.160.12 干  
重 00000 销 艹+++ 饰 王+干+ +++- +丰 一丰+ =丰--0.08 上 上 上 上 上 上 上 F 上 上 上 上 上 上 上 J2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32模式编号

这两种方法对于权重的确定具有一定的合理性。

# 2 当前气候情景下多模式集合模拟与评估

# 2.1 模式权重比较

对各子区不同模式模拟结果与观测值进行回归分析，得到不同方法拟合出的各模式权重大小（图2)，权重越大，表明该模式模拟能力越强。由图2可以看出，模式在不同方法及子区下，模拟效果各有不同。由气温模拟的权重（图2a)看，NorESM1-ME的模拟性能最强，其在PLS、RR方法下4个子区的权重平均值分别为0.133和0.130，远超过等权值0.032。MIROC-ESM-CHEM模拟性能最差，两种方法在各个子区的权重均低于等权值。对于降水（图2b），CMCC-CM表现出最强的模拟能力，在PLS及RR方法下4个子区权重均值分别为0.087和0.103，也远远高于等权值。与气温不同的是，模拟性能最差的模式因方法不同而产生差异，PLS及RR方法下的分别为GFDL-ESM2G、NorESM1-ME。

# 2.2 模拟结果评估

为评估不同集合平均方法对流域各子区气温和降水的模拟能力，图3给出了1950—2005年气温、降水观测结果与多模式集合结果在流域各子区的距平时间序列。从模拟与观测气温过去50多年变化趋势来看(图3a），开都-孔雀河流域各个子区均呈现出显著增温的特征，这与北疆地区气温变化趋势一致[25]。对比发现,3种集合方法模拟结果增温幅度明显小于观测增温幅度。对比各子区不同集合方法的模拟效果，PLS法能够更好地反映出观测值长期变化趋势及其特征，其模拟结果与观测值相关系数均通过了 $9 5 \%$ 的显著性检验，并且对各子区来说，PLS集合结果与观测相关性 $( 0 . 7 4 \sim 0 . 8 2 )$ 总体上高于RF $\mathfrak { i } ( 0 . 7 3 \sim 0 . 8 2 )$ 和E $\operatorname { E } { \big ( } 0 . 6 4 \sim 0 . 7 8 { \big ) }$ 集合结果（表3）。从4个子区的相关系数及均方根误差来看，PLS模拟能力由流域西北山区到东南荒漠区逐渐增强。而SB3地形多变却仍表现出较好的模拟能力，可能是与降尺度数据分辨率有关，高分辨率模式能够更好地反映高原边缘陡峭的地形特点，消除所存在的高偏差[26],从而提高模拟能力。由此可得，气候模式对温度的模拟能力可能受到地形的影响，越是平坦且类型简单的地区，其模拟效果表现越好。

![](images/a87d9c1515a7f60734da59b0638a1366c7057709aab48bd202274912b8345666.jpg)  
注：距平参考为1986—2005年。下同。  
图3观测与多模式集合结果在开都-孔雀河流域各子区距平时间序列  
Fig.3Temporal seriesof anomaliesof air temperature and precipitation from theobservedresultsandtheCMIP5 MME in sub-basins of the Kaidu-Kongqi River Basin

表3各子区不同集合平均方法模拟值与观测值的对比 Tab.3Compared results between the observed values and the values simulated with different ensemble mean methods in each sub-basin   

<html><body><table><tr><td>气候要素</td><td>子区</td><td>评估指标</td><td>PLS</td><td>RR</td><td>EE</td></tr><tr><td>气温</td><td>SB1</td><td>RMSE</td><td>0.59</td><td>0.60</td><td>0.66</td></tr><tr><td rowspan="9">降水</td><td></td><td>r</td><td>0.74 *</td><td>0.73 *</td><td>0.64*</td></tr><tr><td>SB2</td><td>RMSE</td><td>0.50</td><td>0.50</td><td>0.57</td></tr><tr><td></td><td>r</td><td>0.78 *</td><td>0.78 *</td><td>0.70*</td></tr><tr><td>SB3</td><td>RMSE</td><td>0.42</td><td>0.43</td><td>0.47</td></tr><tr><td></td><td>r</td><td>0.81*</td><td>0.80 *</td><td>0.75 *</td></tr><tr><td>SB4</td><td>RMSE</td><td>0.39</td><td>0.38</td><td>0.43</td></tr><tr><td></td><td>r</td><td>0.82*</td><td>0.82 *</td><td>0.78 *</td></tr><tr><td>SB1</td><td>RMSE</td><td>16.34</td><td>16.49</td><td>17.13</td></tr><tr><td></td><td>r</td><td>0.36 *</td><td>0.32</td><td>0.18</td></tr><tr><td rowspan="4"></td><td>SB2</td><td>RMSE</td><td>20.07</td><td>20.28</td><td>21.00</td></tr><tr><td></td><td>r</td><td>0.24</td><td>0.21</td><td>0.04</td></tr><tr><td>SB3</td><td>RMSE</td><td>23.12</td><td>23.22</td><td>29.10</td></tr><tr><td></td><td></td><td>0.19</td><td>0.19</td><td>-0.01</td></tr><tr><td></td><td>SB4</td><td>RMSE</td><td>24.10</td><td>23.81</td><td>25.05</td></tr><tr><td></td><td></td><td>1</td><td>0.24</td><td>0.28</td><td>0.08</td></tr></table></body></html>

注：PLS为偏最小二乘回归，RR为岭回归，EE为等权平均。

与气温相比，CMIP5多模式集合方法对于流域降水的模拟能力明显要差一些。图3b给出了1950一2005年降水距平百分率的时间变化情况。可以看出，流域降水整体上呈增加趋势，此结论与商沙沙等[27]研究西北干旱区降水变化得出的结论一致。由模拟结果来看，无论是哪一种集合方法，其所展现出的变化幅度明显低于观测结果。尤其明显的是流域的高海拔地区SB1，模拟的最大变化幅度$[ 0 . 5 7 \% \cdot \ ( \mathrm { \Omega } 1 0 \mathrm { { a } } ) ] ^ { - 1 } \mathrm { ] }$ 仅约为观测［3. $9 7 \%$ ：$\left( 1 0 \mathrm { a } \right) ^ { - 1 } \mathbf { \bar { \Psi } }$ 的 $1 / 7$ ,这可能是由于模式对于地形的刻画存在不足造成的。对比3种集合法模拟结果（表3）,在 SB1、SB2与 SB3区,PLS 集合法的模拟效果要优于RR与EE 两种集合方法，其中效果最差的当属EE法，表现最为明显的区域为SB3子区，其模拟值与观测值的相关系数为负相关（-0.01）。从4个子区来看，对于SB1、SB4区域的模拟效果要好于SB2与SB3区。而SB1相较于其他子区表现出了最好的模拟效果，或许与此处四周高山环绕，并受到中高纬度西风环流与极地冷气团的控制，使得该区域降水集中有关。由此可以看出，气候模式对降水的模拟能力也可能会受到地形的影响，与气温不同的是，其并未表现出一定的规律性。

综合气温和降水来看，降水3种集合方法的回报效果相比于气温较弱，这种现象在以往的全球气候模式模拟中也普遍存在(28]。对于整个流域而言,PLS 预估结果整体上与CRU数据相吻合，在气温和降水中均表现出更好的模拟能力，其能更有效地减少模式回报误差，且更好地克服模式对地形刻画不足的问题，进而提高预估效果。

# 321世纪开都-孔雀河流域气候预估

# 3.1RCP情景下气温、降水年变化

在31个气候模式中，利用PLS集合方法模拟1950—2099 年开都－孔雀河流域各子区平均气温和降水，得到未来（2006—2099年）相对于1986—2005年的距平时间序列（图4）。可以看出，在不同排放情景下，流域各子区的气温均呈显著上升趋势（通过置信度为 $9 5 \%$ 的显著性检验），且其变化幅度因排放情景、地区的不同而有所差异。

由图4a 可知,在2006—2099 年，高端浓度路径（RCP8.5）下整个流域的增温速率达 $0 . 5 8 \sim 0 . 6 7$ $\mathrm { { ~ \mathcal { C } ~ } } \cdot \mathrm { ~ ( ~ 1 0 a ) ~ } ^ { - 1 }$ ，而中低端浓度路径下（RCP4.5）的增温速率仅为 $0 . 2 5 \sim 0 . 3 1 \ \mathrm { \% } \cdot ( 1 0 \mathrm { a } ) \ ^ { - 1 }$ ,RCP8.5情景下的增温速率为RCP4.5情景的2倍以上，此结论与赵天保等[29]研究得出的干旱半干旱区变暖趋势相一致。在21世纪早期，两种排放情景下的气温距平差异不大，但随着时间推移，两种情景下的差异逐渐增大。RCP4.5 情景下的增温在21世纪中叶以后趋于稳定，而RCP8.5情景下的增温持续保持一个线性增加趋势。从4个子区的增温速率来看，从西北山区的SB1区到东南荒漠区的SB4区，增温速率越来越大，表现为平原区增温明显高于山区。从增温幅度来看，RCP4.5情景下4个子区的增温均在$3 \mathrm { ~ } \mathrm { { ^ circ C } }$ 以内变化，而RCP8.5情景下则达到了 $6 \mathrm { ~ \textdegree C }$ 。这与全国[30]（RCP4.5 情景下2006—2099 年增温在$0 \sim 3 \mathrm { ~ } \mathrm { \textdegree C }$ ,RCP8.5 情景下2006—2099 年增温在 $0 \sim$ $6 ~ \mathrm { { ^ circ C } }$ )气温的预估结果相吻合。总的来看，开都-孔雀河流域与全国及干旱区未来的气温变化情况基本相似，均表现出高排放情景下的增温速率高于低排放情景。

对于降水变化，图4b给出了不同情景下的降水距平百分率。相对于1986—2005年，21世纪流域各子区的降水变化总体呈增加趋势（通过置信度为$9 5 \%$ 的显著性检验），此结论与杨绚等[31利用30 个CMIP5模式集合预估未来全国降水得出的西北地区降水变化趋势一致。相比于气温，年降水的未来变化区域差异大。RCP4.5情景下,SB1和SB4区增加速率较大，分别为 $1 . 2 9 \% \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 }$ 和 $1 . 3 2 \%$ ：（10a）-1，而位于中部的 SB2和SB3 相对较低，两者均在 $1 . 0 0 \% \cdot ( 1 0 \mathrm { { a } ) \Sigma ^ { - 1 } }$ 以下。RCP8.5情景下,总体表现为西北山区降水增加速率略大于东南平原区。对比不同排放情景，除了SB4子区以外，其他子区在RCP8.5情景下的增加速率均大于RCP4.5情景。此结论与程雪蓉等[32]的研究结果略有不同,其利用7个CMIP5模式预估全国7个区域未来降水变化情况，得出西北西部地区RCP8.5情景下的降水增加趋势高于RCP4.5情景。产生此类差异或许与模式对地形的描述存在误差有关。RCP8.5情景下整个流域的增加速率达到 $1 . 2 2 \% \sim 1 . 5 4 \% \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 而RCP4.5情景下的增加速率偏低，为 $0 . 8 0 \%$ \~$1 . 3 2 \% \cdot ( 1 0 \mathrm { { a } ) \ ^ { - 1 } } .$ #

![](images/1a44f63f7f8443493a05cf8d4d04137cb4a7815c37948623f7e672ff81c3708f.jpg)  
图4不同排放情景下21世纪开都-孔雀河流域各子区的气温、降水变化 Fig.4Change of air temperature and precipitation in sub-basins of the Kaidu-Kongqi River Basin under different discharge conditions in the 21st century

综合而言，在不同排放情景下，开都-孔雀河流域未来的气温和降水均呈增加趋势，总体表现出高端浓度路径下的增加速率更快的特征。所不同的是，气温呈现出明显的持续增加趋势，而降水则表现为缓慢的上下波动增加。

# 3.2RCP情景下气温、降水月变化

图5给出了历史时期（1986—2005年）流域各子区的月平均气温和降水变化的箱式图，其中包含上四分位数、中位数、平均值以及下四分位数。除此之外，图5还显示了RCP4.5与RCP8.5情景下多年月平均气温和降水量。通过对比发现，两种排放情景下的气温均值在每个月中均呈现出上升趋势（相对于历史时期），且在7一9月增加幅度最大,其中RCP8.5的均值大于RCP4.5（图5a），此变化趋势与年变化相同。从降水变化结果来看（图5b），不同的子区，月平均降水量呈现出与历史时期相一致的变化趋势，且在6一8月降水量达到最高。然而，未来两种排放情景下的月平均降水量变化呈现出波动的状态（相对于历史时期），特别在降水量最多的6月，除 SB4子区外，其他子区月平均降水量略低于基准期。同时，RCP8.5下的降水量并非一直高于RCP4.5，这种情况主要出现在西北山区SB1区，其中以1月、2月、9月和10月尤为明显。在年变化中也产生了类似情况，不过所发生的地区不同。

![](images/bcb943b71cccffac334aa455b39ff010a880d29d9c946e3b029c61ff52ed0907.jpg)  
图5RCP情景下多模式集合方法模拟开都-孔雀河流域各子区的气温、降水预估结果 Fig.5Projected results of air temperature and precipitation in sub-basins of the Kaidu-Kongqi River Basin under the RCP scenario in the 21st century

# 4结论与讨论

本文基于BCSD 降尺度的CMIP5 模式数据与CRU观测资料,采用PLS、RR和EE3种多模式集合方法，对开都-孔雀河流域历史时期的气候变化进行了评估，确定了最优集合方法，并将其应用到未来RCP情景下流域气候变化预估。主要研究结论如下：

（1）对比多模式集合平均模拟效果，PLS方法具有较高的模拟能力，能够很好地再现1950一2005年开都-孔雀河流域的气候变化特征，尤其对气温的模拟， $r$ 值均达到了0.64，明显优于降水（0.19\~0.36)，说明气温的预估结果具有更高的可信度。综合整个流域来看，东南平原区SB4的气温模拟效果最好，其均方根误差值均小于其他子区，表明模式能够较好地模拟出地势相对平坦且地貌类型简单的区域的气温变化，而模式对降水的模拟并没有表现出一定的规律性。

（2）相对于基准期（1986—2005年），2006—2099年开都-孔雀河流域在不同RCP情景下的气温均显著升高，且RCP8.5情景下的增温速率（204 $\left[ 0 . 5 8 \sim 0 . 6 7 \ \mathrm { ~ \% ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } \ \right]$ 是RCP4.5情景下$\left[ 0 . 2 5 \sim 0 . 3 1 \ \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ~ ) ~ } ^ { \mathrm { ~ - ~ 1 ~ } } \right]$ 的2倍多。21世纪中期以后，RCP4.5排放情景下的气温趋于稳定，而RCP8.5情景下的增温更为明显。从整个流域来看，增温速率由西北向东南逐渐增大，总体表现为平原区高于山区。对于多年月平均气温变化，RCP8.5情景下各月平均气温均高于RCP4.5情景,这与年平均气温变化结果相一致。

（3）未来流域各子区的降水量将有所增加，且RCP8.5情景下的增加速率 $[ \ : 1 . 2 2 \% \ : \sim \ : 1 . \ : 5 4 \%$ ：（10a）-]总体上高于 $\mathrm { R C P 4 . 5 } [ 0 . 8 0 \% \sim 1 . 3 2 \%$ ：（10a）-']。RCP4.5情景下，西北部山区 SB1及东南部荒漠区SB4降水增加速率略高于中部地区。而RCP8.5情景下，表现为西北山区降水增加速率大于东南平原区。相对于基准期（1986—2005 年），多年月平均降水量却表现出因地区和排放情景的不同而上下波动的状态。

本研究尽管使用了相比于以往的全球气候模式具有一定改进的CMIP5耦合模式,但对于开都－孔雀河流域气候的模拟仍然存在不确定性，尤其表现在降水的模拟上。此外，本研究虽对比分析了3种多模式集合平均方法的模拟效果，但对权重的分配尚无最佳确定方法，仍需要进一步的研究，这也是目前研究者们探讨的热点问题[33-34],因此,在后续的研究中值得加入更多的权重确定方法以提高其精度。与此同时，本文主要采用的是多模式统计降尺度集合方法，而目前基于动力降尺度的区域气候情景预估也已成为学者们关注的重点[35-36],未来可在此方面开展深入研究，以得到更可靠的预估结果。

# 参考文献（References）:

[1]秦大河,Stocke T.IPCC 第五次评估报告第一工作组报告的亮 点结论[J].气候变化研究进展,2014，10(1)：1-6.[QinDahe,Stocker T.Highlights of the IPCC working group Ififth assessment report[J].Advances in Climate Change,2014,1O（1）:1- 6.]   
[2] IPCC.Climate Change 2013:The Physical Science Basis.Contribution ofWorking GroupIto the Fifth Assessment Report of the Intergovernmental Panel on Climate Change[M].Cambridge:Cambridge University Press,2013.   
[3]IPCC,2O12:Managing the Risks of Extreme Events and Disasters to Advance Climate Change Adaptation.A Special Report of Working Groups I and I of the Intergovernmental Panel on Climate Change[M].Cambridge:Cambridge University Press,2012.   
[4] 符淙斌，马柱国.全球变化与区域干旱化[J].大气科学，2008， 32（4）:752-76O.[Fu Congbin,Ma Zhuguo.Global change and regional aridification[J].Chinese Journal of Atmospheric Sciences,2008,32(4):752-760.]   
[5] 成爱芳,冯起，张健恺，等.未来气候情景下气候变化响应过程 研究综述[J].地理科学,2015,35（1）:84-90.[Cheng Aifang, Feng Qi,Zhang Jiankai,et al.A review of climate change scenario for impacts process study[J].Scientia Geographica Sinica,2015, 35(1):84 -90.]   
[6]吴迪,严登华.SRES 情景下多模式集合对淮河流域未来气候 变化的预估[J].湖泊科学,2013,25（4）:565-575.[Wu Di, Yan Denghua.Projections of future climate change over Huaihe River basin by multimodel ensembles under SRES scenarios[J] Journal of Lake Science,2013,25(4）:565-575.]   
[7]Guo Yan,Dong Wenjie,Ren Fumin,et al. Surface air temperature simulations over China with CMIP5 and CMIP3[J].Advances in Climate Change Research,2013,4(3）:145-152.   
[8]Taylor KE,Stouffer R J,Gerald A M.An overview of CMIP5 and the experiment design[J].Bulletin of the American Meteorological Society,2012,93(4） :485-498.   
[9]Qu X,Huang G,Zhou W. Consistent responses of East Asian summer mean rainfallto global warming in CMIP5 simulations[J]. Theoretical & Applied Climatology,2014,117(1-2）:123-131.   
[10]Moon S,Ha K J.Temperature and precipitation in the context of the annual cycle over Asia; Model evaluation and future change [J].Asia-Pacific Journal of Atmospheric Sciences,2017,53（2）： 229 -242.   
[11]Chen H P.Projected change in extreme rainfall events in China by the end of the 21st century using CMIP5 models[J].Science Bulletin,2013,58(12):1 462-1 472.   
[12］陶纯苇,姜超,孙建新.CMIP5 多模式集合对东北三省未来气 候变化的预估研究[J].地球物理学报,2016,59（10）：3 580- 3 591.[Tao Chunwei,Jiang Chao,Sun Jianxin.Projectionoffuture changes in climate in Northeast China using a CMIP5 multi-model ensemble[J]. Chinese Journal of Geophysics,2016,59（10）: 3 580 -3 591.]   
〔13）苏琪骅.基于CMIP5 模式在中国地区温度与降水的模拟评估 及集合预报方法研究[D].合肥：中国科学技术大学,2017. [Su Qihua.Evaluation and Ensemble Forecast of the Surface Air Temperature and Precipitation in China Based on CMIP5 MultiModels[D].Hefei: Universityof Scienceand Technology of China, 2017.   
[14］智协飞,赵欢,朱寿鹏,等.基于CMIP5 多模式回报资料的地面 气温超级集合研究[J].大气科学学报,2016,39(1)：64-71. [ Zhi Xiefei,Zhao Huan,Zhu Shoupeng,et al. Superensemble hindcast of surface air temperature using CMIP5 Multi-Model data[J]. Transactions of Atmospheric Sciences,2016,39（1）:64-71.]   
[15]Zhu C,Park C K,Lee W S,etal.Statistical downscaling for MultiModel ensemble prediction of summer monsoon rainfall in the AsiaPacific region using geopotential height field[J].Advances in Atmospheric Sciences,2008,25(5）:867-884.   
[16]周莉,兰明才,蔡荣辉,等.21世纪前期长江中下游流域极端降 水预估及不确定性分析[J].气象学报,2018,76(1)：47-61. [Zhou Li,Lan Mingcai,Cai Ronghui,et al.Projection and uncertainties of extreme precipitation over the Yangtze River valley in the early 21st century[J]. Acta Meteorologica Sinica,2018,76 (1) :47 -61.]   
[17]Semenov M A,Stratonovitch P.Use of multi-model ensembles from global climate models for assessment of climate change impacts [J]. Climate Research,2010,41(1） :1-14.   
[18］陈鹏翔,江志红,彭冬梅.基于BP-CCA 统计降尺度的中亚春季 降水的多模式集合模拟与预估[J].气象学报,2017,75（2）： 236 -247.[Chen Pengxiang,Jiang Zhihong,Peng Dongmei. Multimodel statistical downscaling of spring precipitation simulation and projection in Central Asia based on canonical correlation analysis [J].Acta Meteorologica,2017,75(2）:236-247.]   
〔19］吴晶,罗毅,李佳,等.CMIP5 模式对中国西北干旱区模拟能力 评价[J].干旱区地理,2014,37（3）:499-508.[Wu Jing,Luo Yi,Li Jia,et al.Evaluation of CMIP5 model's simulation ability in the Northwestaridareas ofChina[J].AridLand Geography,2014, 37(3) :499 -508.]   
[20］祁晓凡,李文鹏,李海涛,等.基于CMIP5 模式的干旱内陆河流 域未来气候变化预估[J].干旱区地理,2017,40(5):987-996. [Qi Xiaofan,Li Wenpeng,LiHaitao,etal.Futureclimatehange prediction of arid inland river basin based on CMIP5 model[J].Arid Land Geography,2017,40(5）:987-996.]   
[21］黄秋霞,赵勇,何清.基于CRU资料的中亚地区气候特征[J]. 干旱区研究,2013,30（3）:396-403.[Huang Qiuxia,Zhao Yong,He Qing. Climatic characteristics in Central Asia based on CRU data[J].Arid Zone Research,2013,30(3） :396 -403.]   
[22]周成虎,程维明.中国1:400 万数字地貌数据集.http://westde.westgis.ac.cn,2014.[Zhou Chenghu,Cheng Weiming.1: 4 000 00 Digital Geomorphology Database in China.http://westdc. westgis.ac.cn,2014.]   
[23]Geladi P,Kowalski B R.Partial least-squares regression: A tutorial [J].Analytica Chimica Acta,1985,185(86）:1 -17.   
[24]Hoerl A,Kennard R. Ridge regression; Biased estimation for nonorthogonal problems[J].Technometrics,2000,42（1）:80-86.   
[25］谭娇,丁建丽,张钧永,等.1961—2014 年新疆北部地区气温时 空变化特征[J].干旱区研究,2018,35(5)：1181-1191.[Tan Jiao,Ding Jianli,Zhang Junyong,et al.Spatiotemporal variation of temperature in North Xinjiang during the period of 1961- 2014 [J].Arid Zone Research,2018,35(5）:1 181-1 191.]   
[26］张艳武,张莉,徐影.CMIP5 模式对中国地区气温模拟能力评 估与预估〔J].气候变化研究进展,2016,12（1)：10 －19. [Zhang Yanwu,Zhang Li,Xu Ying. Simulations and projections of the surface air temperature in China by CMIP5 models[J].Advances in Climate Change,2016,12(1):10 -19.]   
[27］商沙沙，廉丽妹,马婷,等.近54a中国西北地区气温和降水的 时空变化特征[J].干旱区研究,2018,35（1):68－76.[Shang Shasha,Lian Lishu,Ma Ting,et al.The temporal and spatial characteristics of temperature and precipitation in Northwestern China in recent 54 years[J].Arid Zone Research,2018,35(1):68 -76.]   
[28]Aloysius NR,Sheffield J,Saiers JE,etal.Evaluation of historical and future simulations of precipitation and temperature in central Africa from CMIP5 climate models[J]. Journal of Geophysical Research Atmospheres,2016,121(1):130-152.   
[29］赵天保,陈亮,马柱国.CMIP5 多模式对全球典型干旱半干旱 区气候变化的模拟与预估[J].科学通报,2014,59(12)：1148 -1 163.[Zhao Tianbao,Chen Liang,Ma Zhuguo.Simulation of historical and projected climate change in arid and semiarid areas by CMIP5 models[J]. Chinese Science Bulletin,2014,59（12）： 1 148 -1 163.]   
[30］吴佳,周波涛,徐影.中国平均降水和极端降水对气候变暖的 响应:CMIP5 模式模拟评估和预估[J].地球物理学报,2015， 58（9）:3 O48-3060.[Wu Jia,Zhou Botao,Xu Ying.Response of precipitation and its extremes over China to warming:CMIP5 simulation and projection[J].Chinese Journal of Geophysics,2015,58 (9):3 048-3 060.]   
[31］杨绚,李栋梁,汤绪.基于CMIP5 多模式集合资料的中国气温 和降水预估及概率分析[J].中国沙漠,2014,34（3）：795- 804.[Yang Xuan,Li Dongliang,Tang Xu.Probabilityassessment

of temperature and precipitation over china by CMIP5 multi-model ensemble[J].Journal of Desert Research,2014,34（3）:795- 804.]

[32]程雪蓉，任立良，杨肖丽，等.CMIP5多模式对中国及各分区气温和降水时空特征的预估[J].水文,2016,36（4)：37－43.[Cheng Xuerong,RenLiliang,Yang Xiaoli,etal.A CMIP5 Multi-model estimation of spatio-temporal characteristics of temperature,precipitation in regions of China[J].Hydrology,2016,36（4）:37-43.]

[33］郯俊岭,江志红,马婷婷.基于贝叶斯模型的中国未来气温变 化预估及不确定性分析[J].气象学报，2016，74（4）：583- 597.[Tan Junling,Jiang Zhihong,Ma Tingting.Projections of future surface air temperature change and uncertainty over China based on the Bayesian model averaging[J].Acta Meteorologica

Sinica,2016,74(4):583-597.]

[34]张学珍，李侠祥，徐新创，等.基于模式优选的21世纪中国气 候变化情景集合预估[J].地理学报，2017，72（9)：1555- 1 568.[Zhang Xuezhen,Li Xiaxiang,Xu Xinchuang,et al.Ensemble projection of climate change scenarios of China in the 21st century based on the preferred climate models[J].Acta Geographica Sinica,2017,72(9):1 555-1 568.]   
[35]Guo D,Wang H.Comparison of a very-fine-resolution GCM with RCM dynamical downscaling in simulating climate in China[J]. Advances in Atmospheric Sciences,2016,33(5） :559-570.   
[36]Dai A,Rasmussen R M,Ikeda K,et al.A new approach to construct representative future forcing data for dynamic downscaling [J].Climate Dynamics,2017:1-9.

# Projection of Future Climate Change in the Kaidu-Kongqi River Basin in the 21st Century

LI Xiao-fei1,²， XU Chang-chun1²，LI Lu1,2， SONG Jia1,²， ZHANG Xi-cheng1,2 (1. College of Resources and Environmental Sciences,Xinjiang University,Urumqi 830o46,Xinjiang,China; 2.Key Laboratory of Oasis Ecology under Ministry of Education,Collge of Resources and Environmental Sciences,Urumqi 830046,Xinjiang,China)

Abstract:Climate change assessments onboth global and regional scales rely stronglyon the global climate models（GCMs）which are dominantly provided by the Coupled Model Inter Comparison Project Phase 5（CMIP5). Based on the grid datasets of monthly air temperature and precipitation from CRU（Climate Research Unit）and 31 CMIP5 GCMS data from the Downscaled CMIP3 and CMIP5 Climate and Hydrology Projections（DCHP）,in this paper the performance of three Multi-Model Ensemble Mean methods（PLS,RR and EE）in simulating the historical climate change processes was evaluated,and the optimal ensemble method was determined and estimated for predictingthe future climate change in the Kaidu-Konqi River Basin in the 21stcentury.The results indicated that: （204号 $\textcircled{1}$ The performance of the established Partial Least Squares （PLS）model was the best in simulating air temperature and precipitation in the study area.The $r$ values of simulated temperature were all higher than O.64,they were obviously better than those ofsimulated precipitation（O.19-0.36).However,there was aspatial heterogeneity in both temperature and precipitation simulations ; $\textcircled{2}$ In the 21st century,the air temperature in the 4 sub-basins of KaiduKongqi River Basin would be in a significant increase trend.The increase rates of air temperature[0.58- $0 . 6 7 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ 1 0 a ~ ) ~ } ^ { - 1 } \mathrm { ~ ] ~ }$ under the RCP8.5 scenario would be doubled compared with those under RCP4.5 scenario $\left[ 0 . 2 5 - 0 . 3 1 \mathrm { ~ \textdegree ~ } \cdot \mathrm { ~ ( ~ } 1 0 \mathrm { a ) ~ } ^ { - 1 } \right]$ .The significant difference between the two scenarios would begin from the mid-21 st century.Fromthe perspective of entire watershed,the warming rate increased gradualy from the mountainous area in the northwest to the desert in the southeast ; $\textcircled{3}$ The distribution of change rates of precipitation was slightly diferent under diferent discharge scenarios,but both of them would be in a significant increase trend.The increase rate under RCP8.5 scenario $\left[ 1 . 2 2 \% - 1 . 5 4 \% \cdot \left( 1 0 \mathrm { { a } } \right) ^ { - 1 } \right]$ would be holistically higher than that under RCP4.5 scenario （20 $\left[ 0 . 8 0 \% - 1 . 3 2 \% \cdot \left( 1 0 \mathrm { { a } } \right) ^ { - 1 } \right]$

Key words:downscale；CMIP5；air temperature；precipitation；Multi-Model Ensemble； future climate change; Kaidu-Kongqi River Basin