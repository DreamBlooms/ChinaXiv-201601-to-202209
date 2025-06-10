DOI:10.13930/j.cnki.cjea.170112

郑雯，明金，杨孟克，周四维，汪善勤，基于波段深度分析和BP神经网络的水稻色素含量高光谱估算[J].中国生态农业 学报,2017,25(8):1224-1235 Zheng W,Ming J,Yang MK,Zhou SW, Wang SQ.Hyperspectral estimationofrice pigmentcontent based onband depth analysis and BP neural network[J]. Chinese Journal of Eco-Agriculture,2017,25(8): 1224-1235

# 基于波段深度分析和BP神经网络的水稻色素含量高光谱估算

郑雯¹，明金¹，杨孟克¹，周四维¹，汪善勤1,2\*\*(1．华中农业大学资源与环境学院武汉430070;2.农业部长江中下游耕地保育重点实验室武汉430070)

摘要：该文以水稻田间氮肥水平试验为基础，采用单变量的线性和非线性回归方法，建立基于植被指数的水稻色素含量高光谱估算模型。各植被指数对色素含量的估计能力分析结果显示，植被指数在色素含量较大时存在饱和问题，为此尝试将波段深度分析(BDA)与BP神经网络结合，以提高利用高光谱技术对水稻叶片色素含量的估算精度。基于连续统去除处理的水稻冠层高光谱数据 $( 4 0 0 { \sim } 7 5 0 ~ \mathrm { n m } )$ ，选取波段深度(BD)、波段深度比(BDR)、归一化波段深度(NBDI)和归一化面积波段指数(BNA)4 种波段指数，在此基础上进行主成分分析(PCA)实现降维，然后采用反向传播(BP)神经网络方法对水稻叶片色素含量进行高光谱反演，探讨 BDA与 BP神经网络结合解决植被指数饱和问题的可能性和有效性。结果表明，波段深度分析突出了光谱吸收特征差异，挖掘了更多的潜在信息，使得光谱曲线的差异性得到增强。BD与BP结合的估算模型对水稻叶片中的类胡萝卜素含量估算精度最高 $( R ^ { 2 } { = } 0 . 6 1$ ， $\mathrm { R M S E P = 0 . 1 2 8 \ m g \cdot g ^ { - 1 } } ,$ ,BNA与BP结合的估算模型对水稻叶片中的叶绿素含量估算精度最高 $( R ^ { 2 } { = } 0 . 7 3$ ， $\mathrm { R M S E P = 0 . 3 4 3 m g \cdot g ^ { - 1 } } ,$ 。对比分析BDA与BP结合的模型和植被指数最佳回归模型的精度，发现波段深度分析建立的BP神经网络模型能较好地解决饱和问题，提高水稻叶片色素含量的估算精度。

关键词：高光谱；水稻；色素；植被指数；波段深度分析；主成分分析；反向传播神经网络中图分类号：S127 文献标识码：A 文章编号:1671-3990(2017)08-1224-12

# Hyperspectral estimation of rice pigment content based on band depth analysis and BP neural network\*

ZHENG Wen1,MING Jin',YANG Mengke,ZHOU Siwei, WANG Shanqinl,2\*\* (1.CollegeofResourcesandEnvironment,HuazhongAgriculturalUniversityWuhan430o,China;2.KeyLaboratoryofArable Land Conservation in Middle and Lower Reaches of Yangtze River,Ministry of Agriculture,Wuhan 430070,China)

Abstract:The estimation accuracyof plantpigmentcontentislow under higher pigment content since conventional vegetation indices tend tobe less sensitiveto the variance ofpigmentcontent.In orderto improve estimation accuracyofricecarotenoid andchlorophyllcontents with canopyreflectance during all growth stage,weexplore the feasibiltyand effectivenessofcombiningthebanddepthanalysis (BDA)andbackpropagation(BP)neuralnetworktosolvetheproblemofvegetationindexsaturation.

With canopy hyperspectral data $( 4 0 0 - 7 5 0 ~ \mathrm { n m }$ ), four band indices — band depth (BD),band depth ratio (BDR),normalized band depth index (NBDI) and band depth normalized to band area (BNA)—werecalculated via continuum removal procesing. Principal component analysis (PCA)wasused toreduce the dimensions of hyperspectral data,anddetermined10 principle components,which were introduced into BPneutral network as input variables.Inthe study,canopyhyperspectralreflectance and pigmentcontent measurements were conducted in Meichuan TownofHubei Province,China.Eight treatments of nitrogen fertilization (0,45,82.5,127.5,165,210,247.5 and $2 9 2 . 5 \mathrm { k g } { \cdot } \mathrm { h m } ^ { - 2 } .$ ） were applied to generate various indices of vegetation and pigmentcontent.Linearandnonlinearregression models wereused toquantitativelyanalyze the vegetation indices and measured pigment content. In addition, coeficient of determination $( R ^ { 2 } )$ and root mean square error (RMSE) were used to evaluate themodels.Allthehyperspectral indices werecomparativelyanalyzed.Asaresult,BDAshowedthediferences inspectralbsorptioncharacteristicsandrevealed morepotential information toenhance spectral diference.Theestimation modelcombinedband index BD and BP had the highest estimation accuracy for carotenoid content in rice leaves, with $R ^ { 2 } = 0 . 6 1$ and $\mathrm { R M S E } = 0 . 1 2 8 \mathrm { \ m g cdot g ^ { - 1 } }$ whilethe estimation model combined band index BNAandBPhadthe highest estimation acuracyforchlorophyllcontent in rice leaves, with $R ^ { 2 } = 0 . 7 3$ and $\mathrm { R M S E } = 0 . 3 4 3 ~ \mathrm { m g { \cdot g } ^ { - 1 } }$ .Further comparison between BDA & BP models with the best regression modelfor vegetationindex indicatedthatBPneutral network modelbasedonBDA providedabetersolutionto saturation problem and a higher estimation precision of rice leaf pigment content.

Keywors: Hyperspectral; Rice; Pigment; Vegetation index;Banddepth analysis; Principalcomponent analysis; Backpropagation neural network

色素含量是描述作物生理状态的重要指标之一，其变化可用于评估作物的光合能力和初级生产力。实时快速地获取色素含量信息成为监测水稻(Oryzasativa)生长、发育和产量的一种有效方法。传统的作物叶片色素含量测定常采用实验室理化分析方法，费时、繁琐并具有破坏性。近年来，高光谱技术以其波段连续性强、波谱分辨率高、光谱信息量大等优势为快速、高效、无损检测作物叶片色素含量提供了一种有效途径[1-2]。因此，研究高光谱技术定量估算作物色素含量具有重要的实践意义。

在可见光范围内，植被冠层反射光谱主要受叶片色素含量的影响；而在近红外范围叶片组织结构、生物量、蛋白质、水分等起主要作用。大量研究表明，可以用植被的冠层反射光谱来估算色素含量[3]。作物叶片中的色素主要包括叶绿素(叶绿素a、叶绿素 b)和类胡萝卜素(胡萝卜素和叶黄素)，其中叶绿素是吸收光能的主要物质，直接影响光合作用的光能利用。研究发现叶绿素a和叶绿素b的吸收峰波段分别为 $6 6 5 ~ \mathrm { { n m } }$ 和 $6 4 3 ~ \mathrm { { n m } }$ ，类胡萝卜素的吸收峰所处的波段与叶绿素相重叠，单独估计不同色素含量存在一定的难度。文献报道通过建立遥感原始波段或植被指数与生化组分含量之间的多元统计回归模型，能较准确地估测植物叶片生化组分含量。王福民等[2通过所有光谱波段的两两组合，建立归一化比值色素与叶绿素、类胡萝卜素的统计模型，得到最佳归一化色素指数。Sims等4通过寻找新的光谱指数来预测叶片色素，但选取的特征光谱及参数因不同作物或不同试验、不同叶片结构而有明显差异。最明显的问题在于，当叶片色素含量较高时，常规植被指数将趋于饱和水平，估算色素含量的精度大大降低[5]。Lichtenthaler等[6指出NDVI对偏高叶绿素浓度不敏感，原因在于NDVI对叶绿素吸收带的高度敏感性，较低的叶绿素含量就能使得叶片对光吸收达到饱和状态。

针对上述问题,Gitelson等[7-8]提出红边位置 $7 0 0 \mathrm { n m }$ 处反射率比植被指数对叶绿素的吸收特征更加敏感。但是，当叶片叶绿素含量改变时，对应的吸收波段、红边位置与红边面积也随之改变[9]。连续统去除法可以矫正由于波段依赖而引起的波段反射率极值点的漂移，将波段极值点调整到其真正的波段位置[10]。在此基础上，对使用连续统去除之后的光谱进行波段深度分析，增强吸收特征及减少无关的信息冗余[1]。Mutanga 等[12]对实验室可控条件下的草地冠层光谱进行波段深度分析，并与逐步多元线性回归结合估算草地地上生物量。Kokaly等[13]运用波段深度分析方法能够很好地估算干枯落叶的生理生化含量。Chen等[14]将波段深度分析与PLS结合来估算高覆盖草地的地上生物量。

目前在植被冠层光谱定量分析中常采用线性方法，如逐步多元回归和PLS等。但是，由于受天气、作物品种、土壤背景、试验条件等众多因素的影响，冠层光谱与植物叶片组分含量之间的关系是非线性的，现有方法很难拟合这种多因素影响下的非线性关系。人工神经网络因具有极强的非线性处理、自组织调整、自适应学习的能力而得到广泛应用。本文以提高水稻全生育期的冠层光谱估计类胡萝下素和叶绿素的精度为主要目的，采用波段深度分析(BDA)计算波段深度指数，然后通过主成分分析(PCA)对波段深度指数进行降维，建立BP神经网络模型预测水稻叶片的色素含量，并探讨BDA与BP神经网络结合解决植被指数饱和问题的可能性和有效性。

# 1材料与方法

# 1.1 试验材料

试验田位于湖北省武穴市梅川镇 $( 3 0 ^ { \circ } 0 6 \mathrm { ^ { \circ } N }$ $1 1 5 ^ { \circ } 3 5 ^ { \prime } \mathrm { E } )$ ，土壤类型为水稻土， $0 { \sim } 2 0 \ \mathrm { c m }$ 耕层土壤$\mathrm { p H } 5 . 7 0$ ，有机质 $3 7 . 3 5 ~ \mathrm { g } { \cdot } \mathrm { k g } ^ { - 1 }$ ，全氮 $1 . 6 0 ~ \mathrm { g { \cdot k g } ^ { - 1 } }$ ，速效磷 $5 . 8 3 ~ \mathrm { m g ^ { . } k g ^ { - 1 } }$ ，速效钾 $9 1 . 6 7 ~ \mathrm { { m g } \cdot \mathrm { { k g } ^ { - 1 } } }$ 。供试水稻品种为深两优 ${ 5 8 1 4 } ^ { \prime }$ ，属杂交粘稻，全生育期约 $1 3 8 \mathrm { d }$ 株型适中，叶片挺直。

# 1.2 试验设计与方法

试验田内共设置24个小区，氮肥处理设0$\mathrm { k g } { \cdot } \mathrm { h m } ^ { - 2 }$ 、 $4 5 \mathrm { k g } { \cdot } \mathrm { h m } ^ { - 2 }$ 、 $8 2 . 5 \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ 、 $1 2 7 . 5 \mathrm { k g } { \cdot } \mathrm { h m } ^ { - 2 }$ 、$1 6 5 ~ \mathrm { \ k g } { \cdot } \mathrm { h m } ^ { - 2 }$ 、 $2 1 0 ~ \mathrm { \ k g { \cdot h m } } ^ { - 2 }$ 、 $2 4 7 . 5 ~ \mathrm { \ k g } { \cdot } \mathrm { h m } ^ { - 2 }$ 、292.5$ { \mathrm { k g } } { \cdot }  { \mathrm { h m } } ^ { - 2 } \ 8$ 个水平，分别用 N0、N3、N5.5、N8.5、N11、N14、N16.5和N19.5表示。各处理3次重复，随机区组排列。每个小区面积 $2 0 . 0 \mathrm { m } ^ { 2 }$ 。磷、钾肥按 $\mathrm { P } _ { 2 } \mathrm { O } _ { 5 } 7 5$ $\mathrm { k g } { \cdot } \mathrm { h m } ^ { - 2 }$ / $\mathrm { K } _ { 2 } \mathrm { O } 7 5 \mathrm { k g } { \cdot } \mathrm { h m } ^ { - 2 }$ 施入。氮肥为尿素(含 $\ N 4 6 \%$ ），磷肥用过磷酸钙(含 $\mathrm { P } _ { 2 } \mathrm { O } _ { 5 } 1 2 \% )$ ，钾肥为氯化钾(含$\mathrm { K } _ { 2 } \mathrm { O } 6 0 \%$ ，所有肥料做基肥一次性施入。种植密度为255000株 $\cdot \mathrm { h m } ^ { - 2 }$ ，2015年5月25日播种，6月28日移栽，10月9日成熟。

# 1.3 测量项目与方法

# 1.3.1 水稻冠层高光谱反射率的测定

分别于2015年水稻分蘖期(7月10日)、拔节期(7月27日)、孕穗期(8月12日)、抽穗期(8月27日)和灌浆期(9月12日)，在相应时期内选择晴朗无云、无风天气，每个小区选取5个有代表性观测点。在每个观测日的10:00—14:00，使用FieldSpec Pro$\mathrm { F R } ^ { \mathrm { T M } }$ 光谱仪(美国 Analytical Spectral Devices 公司生产)测量冠层光谱反射率。该光谱仪视场角为 $2 5 ^ { \circ }$ ，波谱范围 $3 5 0 { \sim } 2 ~ 5 0 0 ~ \mathrm { n m }$ ，其中 $3 5 0 { \sim } 1 ~ 0 0 0 ~ \mathrm { n m }$ 区间光谱分辨率为 $3 \quad \mathrm { n m }$ ，采样间隔为 $1 . 4 \mathrm { n m }$ ；在$1 ~ 0 0 0 { \sim } 2 ~ 5 0 0 ~ \mathrm { n m }$ 区间光谱分辨率为 $1 0 \mathrm { n m }$ ，采样间隔为 $2 \ \mathrm { n m } _ { \cdot }$ 。各小区在测量前均进行标准白板校正，测量时仪器探头垂直朝下，距离水稻冠层高度约 $1 . 0 \mathrm { m } _ { \circ }$ 各观测点重复观测5次，取25条光谱的算术平均值作为相应小区冠层光谱结果，5个物候期24个小区共采集120条有效冠层光谱数据。图1表示孕穗期不同氮素水平下的水稻冠层光谱反射率变化趋势，其他关键物候期呈现相同规律。

![](images/be0a85ce07f061a657351f51385f7ec3e0e0c4f87de0e2d713d6a3f8c53ea283.jpg)  
图1不同氮素水平下水稻孕穗期冠层光谱反射率 Fig.1Canopy spectral reflectance of rice at booting stage underdifferentnitrogen applications

# 1.3.2 水稻叶片叶绿素及类胡萝下素的测定

采用混合液(丙酮：无水乙醇 $\vdots = 1 : 1$ )提取法测定水稻叶片叶绿素 $( \mathsf { a } + \mathsf { b } )$ 和类胡萝卜素含量，每个小区对应测光谱的冠层，与冠层光谱测量同步。选取有代表性植株4株，从采样的水稻植株上等数量选取上中下完全展开叶，剪碎，混均匀后获取 $ { 0 . 2 0 0 \mathrm { ~ g ~ } }$ 加混合液 $5 0 ~ \mathrm { m L }$ ，于室温下遮光静置 $2 4 \mathrm { ~ h ~ }$ 左右至样品完全发白，用分光光度计测定叶绿素、类胡萝卜素含量[15]。

# 1.4 数据处理与分析

# 1.4.1 数据预处理

进行色素含量估算时，仅选用信噪比较高的$4 0 0 { \sim } 1 ~ 3 5 0 ~ \mathrm { \ n m }$ 作为有效分析数据。为消除噪声，采用Savitzky-Golay 卷积平滑法进行光谱去噪，移动窗口宽度为15，多项式次数为2。将测得的色素含量与对应的冠层高光谱组成原始数据集，随机分成两组，第1组包含80个用于建模的样本数据，第2组包含40个样本数据用于模型验证。

# 1.4.2 波段深度分析(BDA)

作物叶片的色素含量主要与可见光波段紧密相关，因此深度分析主要处理 $4 0 0 { \sim } 7 5 0 ~ \mathrm { n m }$ 的光谱数据，此波段包含了色素强吸收的蓝、红光区及“红边"波段范围。首先，对光谱数据进行连续统去除变换，校正由于波段依赖而引起的波段反射率极值点的偏移，有效增强吸收特征，增大各光谱曲线之间的差异[10]。“连续统线"定义为连接局部原始光谱反射率峰值点之间的线段(图2)。将反射率曲线上每个波长的光谱反射率 $( R )$ 除以相应波长处连续统线上的值 $( R _ { \mathrm { c } } )$ 可以得到连续统去除光谱 $( R ) _ { \circ }$

![](images/db6d095876919f845f3ca714f783a8c329b121ad70c497f4d251799036cbdb1d.jpg)  
图2 $\mathbf { 4 0 0 { \sim } 7 5 0 \ n m }$ 连续统去除变换光谱曲线Fig.2 Continuum removed reflectance spectra from400 to $7 5 0 ~ \mathrm { n m }$   
图3估计水稻色素含量的BP神经网络模型 Fig.3BP neural network model of estimating pigment content in rice

然后，对连续统去除变换光谱按照表1中的公式计算得到波段深度(band depth，BD)、波段深度比(banddepth ratio，BDR)、归一化波段深度指数(normalized band depth index,NBDI)、归一化面积波段深度(band depth normalized to band area，BNA),结果能够进一步反映色素的吸收特征。

表1吸收特征光谱变换的波段深度分析公式Table1Band depth analysis formulas of absorption featuretransform spectrum  

<html><body><table><tr><td>特征指数 Characteristicindex</td><td>表达式 Expression</td></tr><tr><td>波段深度 Band depth (BD)</td><td>1-R'</td></tr><tr><td>波段深度比</td><td>BDR=BD/BDmax</td></tr><tr><td>Band depth ratio (BDR) 归一化波段深度指数</td><td>NBDI=(BD-BDmax)/(BD+BDmax)</td></tr><tr><td>Normalized band depth index (NBDI) 归一化面积波段深度</td><td></td></tr><tr><td>Band depth normalized to band area (BNA)</td><td>BNA=BD/BDarea</td></tr></table></body></html>

# 1.4.3 建模方法

主成分分析(PCA)是一种通过降维技术把多个变量化为少数几个主成分的多元统计方法。本文采用PCA分别对原始波段 $( R )$ 、波段深度(BD)、波段深度比(BDR)、归一化波段深度指数(NBDI)、归一化面积波段深度(BNA)提取主成分，为了后续构建BP神经网络的一致性，各取前10个主成分，对应的累积贡献率分别为 $9 9 . 4 9 \%$ 、 $9 9 . 8 5 \%$ /$9 9 . 5 5 \%$ 、 $9 0 . 4 6 \%$ 和 $9 9 . 9 7 \text{‰}$ ，经过PCA处理后，将光谱维数从351减少到10，既实现了高光谱数据的降维处理，又保留了原光谱数据绝大部分的特征信息。然后将主成分代入BP神经网络模型进行训练。

BP神经网络模型是一种由输入层、隐含层和输出层组成的前向网络，学习过程由信号的正向传播与误差的反向传播两个过程组成。正向传播时，输入的样本以S型传递函数从输入层经各神经元按层处理，通过隐含层再传向输出层。如果输出层的实际输出与期望输出不符，则转入误差反向传播即将输出误差以某种形式通过隐含层向输入层反传，并将误差分摊给各层所有单元，进行权值修正，从而使误差信号趋于最小，满足预先设定的限差要求[16]。

以10个主成分作为BP神经网络的输入矢量，隐含层节点数直接影响网络的非线性预测性能，采用“试错法"确定隐含层节点数，即尝试不同值的对比，获得最佳节点数，类胡萝下素和叶绿素对应模型的隐含层节点数分别为10、11。1个输出层为水稻叶片色素含量。网络训练的迭代次数为10000，训练目标参数为0.001，学习误差为0.01。训练函数用L-M 优化算法函数 Trainlm(图3)。

# 1.4.4 色素光谱参数计算

参照已有的色素光谱参数计算方法，选择常用的、认可度较高且与本研究相关的17个色素光谱指数(表2)，分别进行了线性和非线性模型拟合，挑选色素最佳估计模型。

采用拟合决定系数 $( R ^ { 2 } )$ 、拟合均方根误差(RMSEC)评价模型的建模精度；估计决定系数 $( R ^ { 2 } )$ /估计均方根误差(RMSEP)和相对分析误差(RPD)评价模型的验证精度。 $R ^ { 2 }$ 反映模型建立和验证的稳定性, $R ^ { 2 }$ 越接近于1，说明模型的稳定性越好、拟合程度越高。RMSE和RPD用来评价模型的误差和估计精度，RMSE值越小说明模型估算能力越好，RPD值大于1.4时说明模型可用，大于 2.0 时模型非常优异[17]。数据处理在Matlab2010b中编程实现。

隐含层 输出层 输人 Hidden layer Output layer Input 输出 权值 权值 Output 10个主成分 Weight 激活函数： Weight 激活函数： Ten principal components S型 线性 水稻叶片色素含量   
(原始波段、波段深度指数的主成分变化。 Activate Activate Rice leaf pigment   
Principal component change of the original function: function: content bandand band depth index) 阈值 tansing 阈值 purelin Threshold Threshold

表2常用估算水 稻叶片色素含量的高光谱参数  
Table 2Hyperspectral indices for estimating leaf pigment content of rice   

<html><body><table><tr><td>光谱参数 Spectral parameter</td><td>计算公式 Algorithm formula</td><td>参考文献 Reference</td></tr><tr><td>色素比值指数-1 Pigment specific simple ratio-1(GM1)</td><td>R750/R550</td><td></td></tr><tr><td>色素比值指数-2 Pigment specific simple ratio-2 (GM2)</td><td>R750/R700</td><td>[18]</td></tr><tr><td>色素比值指数-3 Pigment specific simple ratio-3 (PSSRa)</td><td>R800/R680</td><td>[19]</td></tr><tr><td>色素比值指数-4 Pigment specific simple ratio-4 (PSSRb)</td><td>Rg00/R635</td><td></td></tr><tr><td>卡特指数-1 Carter index-1 (CTR1)</td><td>R695/R420</td><td>[20]</td></tr><tr><td>卡特指数-2 Carter index-2(CTR2)</td><td>R695/R760</td><td></td></tr><tr><td>比值植被指数-1 Ratio vegetation index-1 (RVI1)</td><td>R810/R560</td><td>[21]</td></tr><tr><td>比值植被指数-2 Ratio vegetation index-2 (RVI2)</td><td>R800/R550</td><td>[22]</td></tr><tr><td>归一化色素差异指数-1</td><td>(R800-R680)/(R800+R680)</td><td>[19]</td></tr><tr><td>Petspefi nalizdifferenc-1 (PSSNRa) Pigment specific normalized difference-2 (PSSNRb)</td><td>(R800-R635)/(R800+R635)</td><td></td></tr><tr><td>修正叶绿素吸收指数 Modified chlorophyll absorption ratio index (MCARI)</td><td>[(R700-R670)-0.2(R700-R550)]×(R700/R670)</td><td>[23]</td></tr><tr><td>光化学植被指数 Photochemical reflectance index (PRI)</td><td>(R531-R570)/(R531+R570)</td><td>[24]</td></tr><tr><td>植被衰老反射率指数 Plant senescence reflectance index (PSRI)</td><td>(R680-R500)/R750</td><td>[25]</td></tr><tr><td>转换叶绿素吸收反射指数</td><td>3[(R700-R670)-0.2(R700-R550)(R700/R670)]</td><td>[23]</td></tr><tr><td>Transformed chlorophyll absorption ratio index (TCARI) 绿波段归一化植被指数 Greenness normalized index (GNDVI)</td><td>(R780-R550)/(R780+R550)</td><td></td></tr><tr><td>综合叶绿素光谱指数</td><td>[(R700－R670)-0.2(R700－R550)]×(R700/R670)</td><td>[26]</td></tr><tr><td>Combined optical index (MCARI/OSAVI)</td><td>1.16(R800 －R670)/(R800 + R670+0.16)</td><td>[23]</td></tr><tr><td>结构不敏感色素指数 Structure insensitive pigment index (SIPI)</td><td>(R800-R445)/(R800-R680)</td><td>[27]</td></tr></table></body></html>

R为不同波长下光谱反射率。 $R$ is the reflectance of different wavelength.

均方根误差(root mean square error):

$$
\mathrm { R M S E } = \sqrt { \frac { \sum _ { i = 1 } ^ { n } ( y _ { i } - \widehat { y } _ { \mathrm { t } } ) ^ { 2 } } { n } }
$$

相对分析误差(relative percent deviation):

$$
\mathrm { R P D } = { \frac { \sqrt { \frac { \sum ( y _ { i } - { \overline { { y } } } ) ^ { 2 } } { n } } } { \mathrm { R M S E } } }
$$

式中： $y _ { i }$ 代表实测值， $\widehat { y } _ { \mathrm { t } }$ 代表预测值， $\overline { { y } }$ 代表实测值的均值， $n$ 为样本数。

# 2 结果与分析

# 2.1类胡萝卜素、叶绿素的含量统计

建模集类胡萝 $\boldsymbol { \mathsf { h } }$ 素含量均值和标准差分别为$0 . 7 2 ~ \mathrm { m g ^ { . } g ^ { - 1 } }$ 和 $0 . 2 4 ~ \mathrm { m g ^ { . } g ^ { - 1 } }$ ；验证集类胡萝 $\boldsymbol { \mathsf { h } }$ 素含量均值和标准差分别为 $0 . 7 1 ~ \mathrm { m g ^ { . } g ^ { - 1 } }$ 和 $0 . 1 9 ~ \mathrm { m g { \cdot g } ^ { - 1 } }$ (表3)。建模集叶绿素含量均值和标准差分别为 $2 . 1 6 \ \mathrm { \ m g { \cdot g } ^ { - 1 } }$ 和 $0 . 7 9 \ \mathrm { \ m g { \cdot g } ^ { - 1 } }$ ；验证集叶绿素含量均值和标准差分别为 $2 . 2 1 \ \mathrm { m g { \cdot g } ^ { - 1 } }$ 和 $0 . 6 6 \mathrm { m g { \cdot g } ^ { - 1 } }$ (表3)。试验所划分的建模集和验证集样本均值差异较小，标准差较低，两者具有很好的相似性，说明样本的划分满足模型的构建和检验需要。

对各生育期不同施肥水平下的水稻叶片类胡萝卜素和叶绿素含量进行单因素方差分析，结果表明水稻分蘖期到拔节期，不同施肥水平处理下，叶片类胡萝卜素含量差异不显著；孕穗后叶片类胡萝卜素开始有显著性差异。水稻各生育期，不同施氮处理下的叶片叶绿素含量差异显著。同时类胡萝卜素和叶绿素含量的总体变化趋势一致，即分蘖期到孕穗期含量逐渐增加，到抽穗期有明显减少的过程，灌浆期的色素含量明显低于其他各期(图4)。水稻分蘖期到孕穗期，叶片中的类胡萝卜素和叶绿素含量逐渐增加，孕穗前水稻植株处于营养生长阶段，叶片还在继续发育，类胡萝卜素和叶绿素含量不断增加。水稻孕穗期到灌浆期，叶片中的类胡萝卜素和叶绿素含量逐渐减少，反映出水稻抽穗初期，叶片内的营养物质向穗部转移，类胡萝下素和叶绿素的合成减弱。而在灌浆时期，叶片慢慢衰老变黄，叶片作为光合器官的作用进一步削弱，合成的类胡萝卜素和叶绿素越来减少。

<html><body><table><tr><td>色素 Pigment</td><td>数据集 Data set</td><td>样本数 Number of samples</td><td>均值+标准差 Mean±SD (mg:g-1)</td><td>方差 Variance</td><td>变异系数 Coefficient of variation (%)</td></tr><tr><td>类胡萝卜素 Carotenoid</td><td>全集All</td><td>120</td><td>0.72±0.23</td><td>0.05</td><td>32</td></tr><tr><td rowspan="3">叶绿素</td><td>建模集 Calibration</td><td>80</td><td>0.72±0.24</td><td>0.06</td><td>33</td></tr><tr><td>验证集Validation</td><td>40</td><td>0.71±0.19</td><td>0.04</td><td>27</td></tr><tr><td>全集All</td><td>120</td><td>2.18±0.75</td><td>0.56</td><td>34</td></tr><tr><td rowspan="2">Chlorophyll</td><td>建模集 Calibration</td><td>80</td><td>2.16±0.79</td><td>0.62</td><td>37</td></tr><tr><td>验证集Validation</td><td>40</td><td>2.21±0.66</td><td>0.44</td><td>30</td></tr></table></body></html>

1.4 □0 kg·hm-2 45 kg:hm-² 4.5 a 82.5kg.hm-2 127.5 kg:hm-²   
1.2 □165kg:hm-² Q210kg·hm- 828 2 247.5kg.hm2292.5kg.hm-2   
0.8 baa 品 喜古   
0.6 CI +   
0.4   
0.2 1 1 分蘖期 拔节期 孕穗期 抽穗期 灌浆期 分蘖期 拔节期 孕穗期 抽穗期 灌浆期 Tillering Jointing Booting Heading Filling Tillering Jointing Booting Heading Filling 生育期 Growth stage

# 2.2各光谱指数反演模型的比较分析

# 2.2.1 光谱指数与色素含量相关性分析

分析色素含量与光谱参数的相关性发现，在全生育期，所有光谱参数均与叶片类胡萝卜素和叶绿素含量之间存在显著相关关系，一些与红边相关的光谱参数，如CTR2、PSSNRb等均与叶片类胡萝卜素和叶绿素含量达到较好的相关性(0.7以上)。CTR2与类胡萝卜素呈现显著的负相关，相关系数达-0.77。PRI与叶绿素的含量相关性最大，相关系数达0.8以上(表4)。叶片光化学指数PRI的定义为 $5 3 1 ~ \mathrm { n m }$ 和 $5 7 0 \mathrm { n m }$ 处反射率的归一化植被指数，这两个波段位置的反射率受到叶黄素循环的影响并和叶片的光能利用率密切相关[28]。Filella等[29]指出叶片叶绿素含量和叶黄素含量之间有显著的相关性，叶绿素含量可以间接反映叶黄素的变化。而且植被光能利用率与叶绿素进行光合作用的能力息息相关，因而能够很好地估算叶绿素含量。

表3水稻样本叶片色素含量的统计特征 Table 3 Statistical characteristics of pigment content of leaves of rice samples   
表4高光谱特征参数与水稻叶片色素含量之间的相关系数分析 $\scriptstyle ( n = 1 2 0 )$   
ile 4Correlation analysis between pigment centent and hyperspectral indices of rice leaves $\scriptstyle ( n = 1 2 0$   

<html><body><table><tr><td>参数 Parameter</td><td>GM1</td><td>GM2</td><td>PSSRa</td><td>PSSRb</td><td>CTR1</td><td>CTR2</td><td>RVI1</td><td>RVI2</td><td>PSSNRa</td></tr><tr><td>叶绿素 Chlorophyll</td><td>0.60**</td><td>0.65**</td><td>0.61**</td><td>0.62**</td><td>-0.74**</td><td>-0.75**</td><td>0.60**</td><td>0.59**</td><td>0.67**</td></tr><tr><td>类胡萝卜素 Carotenoid</td><td>0.69**</td><td>0.71**</td><td>0.67**</td><td>0.68**</td><td>-0.55**</td><td>-0.77**</td><td>0.68**</td><td>0.67**</td><td>0.74**</td></tr><tr><td>参数 Parameter</td><td>PSSNRb</td><td>MCARI</td><td>PRI</td><td>PSRI</td><td>TCARI</td><td>GNDVI</td><td>MCARI/OSAVI</td><td>SIPI</td><td></td></tr><tr><td>叶绿素 Chlorophyll</td><td>0.72**</td><td>-0.44**</td><td>0.83**</td><td>-0.77**</td><td>-0.55**</td><td>0.65**</td><td>-0.63**</td><td>-0.78**</td><td></td></tr><tr><td>类胡萝卜素 Carotenoid</td><td>0.75**</td><td>-0.26*</td><td>0.75**</td><td>-0.65**</td><td>-0.42**</td><td>0.73**</td><td>-0.47**</td><td>-0.67**</td><td></td></tr></table></body></html>

各参数的意义见表2;\*、\*\*分别表示在0.05和0.01水平差异显著。Meanings of parameters are shown inthe Table 2.\* and $* *$ show significant correlation at 0.05 and 0.01 levels,respectively.

# 2.2.2 光谱指数对色素含量估计能力

# 应用17种有代表性的光谱参数，在以拟合 $R ^ { 2 }$ 最

大的优选原则基础上，构造对类胡萝下素和叶绿素的最佳预测模型，用来与BDA和BP神经网络结合建

http://www.ecoagri.ac.cn

立的水稻叶片色素含量估算模型进行精度比较(表5,表6)。结果表明类胡萝下素含量的光谱指数模型拟合度较好， $R ^ { 2 }$ 均在0.6附近,RMSE均相对较小，而模型验证结果可行度差 $( R ^ { 2 } { < } 0 . 5 0$ ， ${ \mathrm { R P D } } { < } 1 . 4$ )。叶绿素光谱指数模型中,PRI、PSRI和SIPI拟合度和验证精度均较高 $( R ^ { 2 } { > } 0 . 6 0$ ， ${ \mathrm { R P D } } { \scriptstyle > } 1 . 4 ,$ ，可以用来估算叶绿素含量。其余光谱指数建模结果不理想，模型的验证集精度不高,RMSEP较大,RPD较小。上述结果说明色素光谱指数模型不能很好地估算水稻叶片类胡萝卜素含量，而植被指数如PRI、PSRI和SIPI使用了与叶绿素作用相关的蓝红光吸收和绿峰相对反射的波段，可以较好地估算叶片叶绿素含量。

表5水稻叶片类胡萝卜素含量(Cars)与高光谱参数的线性与非线性回归模型 Table5Comparison of linear Vs non-linear spectral index regresson models of rice leaf carotenoid content (Cars)   

<html><body><table><tr><td rowspan="2">光谱参数 Speatralpa-</td><td colspan="3">建模集 Calibration</td><td colspan="3">验证集Validation</td></tr><tr><td>模型Model</td><td>R²</td><td>RMSEC (mg:g-1)</td><td>R²</td><td>RMSEP (mg:g-1)</td><td>RPD</td></tr><tr><td>GM1</td><td>Cars=0.2GM1-0.06</td><td>0.63</td><td>0.126</td><td>0.43</td><td>0.208</td><td>1.30</td></tr><tr><td>GM2</td><td>Cars=0.16GM2+0.07</td><td>0.71</td><td>0.112</td><td>0.44</td><td>0.206</td><td>1.32</td></tr><tr><td>PSSRa</td><td>Cars=0.03PSSRa+0.3</td><td>0.64</td><td>0.125</td><td>0.46</td><td>0.202</td><td>1.34</td></tr><tr><td>PSSRb</td><td>Cars=0.05PSSRb+0.24</td><td>0.68</td><td>0.118</td><td>0.46</td><td>0.202</td><td>1.34</td></tr><tr><td>CTR1</td><td>Cars=-0.02CTR12+0.13CTR1+0.65</td><td>0.53</td><td>0.143</td><td>0.20</td><td>0.244</td><td>1.11</td></tr><tr><td>CTR2</td><td>Cars=1.1e-3.6CTR2</td><td>0.62</td><td>0.145</td><td>0.48</td><td>0.152</td><td>1.38</td></tr><tr><td>RVI1</td><td>Cars=-0.01S RVI²+0.14RVI</td><td>0.64</td><td>0.124</td><td>0.43</td><td>0.208</td><td>1.30</td></tr><tr><td>RVI2</td><td>Cars=-0.01RVI2+0.16 RVI+0.02</td><td>0.63</td><td>0.126</td><td>0.42</td><td>0.210</td><td>1.29</td></tr><tr><td>PSSNRa</td><td>Cars=3.5PSSNRa²-3.9PSSNRa+1.4</td><td>0.65</td><td>0.123</td><td>0.49</td><td>0.200</td><td>1.36</td></tr><tr><td>PSSNRb</td><td>Cars=1.3PSSNRb²-0.4PSSNRb+0.15</td><td>0.70</td><td>0.114</td><td>0.47</td><td>0.203</td><td>1.34</td></tr><tr><td>MCARI</td><td>Cars=-27MCARI2+7.3MCARI+0.32</td><td>0.42</td><td>0.158</td><td>0.06</td><td>0.268</td><td>1.01</td></tr><tr><td>PRI</td><td>Cars=-3.34PRI2+5.3PRI+0.78</td><td>0.73</td><td>0.108</td><td>0.38</td><td>0.217</td><td>1.25</td></tr><tr><td>PSRI</td><td>Cars=80PSRI2-11PSRI+0.66</td><td>0.60</td><td>0.131</td><td>0.33</td><td>0.227</td><td>1.20</td></tr><tr><td>TCARI</td><td>Cars=-22.7TCARI2+5.65TCARI+0.43</td><td>0.41</td><td>0.160</td><td>0.03</td><td>0.272</td><td>1.00</td></tr><tr><td>GNDVI</td><td>Cars=-0.37GNDVI2+GNDVI-0.2</td><td>0.64</td><td>0.125</td><td>0.41</td><td>0.211</td><td>1.28</td></tr><tr><td>MCARI/OSAVI</td><td>Cars=-6.4 MCARI/OSAVI2+</td><td>0.45</td><td>0.154</td><td>0.09</td><td>0.262</td><td>1.04</td></tr><tr><td>SIPI</td><td>1.74MCARI/OSAVI+0.7 Cars=28SIPI²-64SIPI+37</td><td>0.68</td><td>0.118</td><td>0.37</td><td>0.220</td><td>1.23</td></tr></table></body></html>

各参数的意义见表2。Meanings of parameters are shown in the Table 2.

表6水稻叶片总叶绿素含量(ChI)与高光谱参数的线性与非线性回归模型 6Comparison of linear Vs non-linear spectral index regresson models of rice leaves chlorophyll content (Chl   

<html><body><table><tr><td rowspan="2">光谱参数 Spetral pa-</td><td colspan="3">建模集 Calibration</td><td colspan="3">验证集Validation</td></tr><tr><td>模型 Model</td><td>R²</td><td>RMSEC (mg:g-1)</td><td>R²</td><td>RMSEP (mg:g-1)</td><td>RPD</td></tr><tr><td>GM1</td><td>Chl=-0.04 GM12+0.7GM1-0.6</td><td>0.56</td><td>0.477</td><td>0.20</td><td>0.704</td><td>1.08</td></tr><tr><td>GM2</td><td>Chl=-0.03GM22+0.6GM2-0.2</td><td>0.65</td><td>0.423</td><td>0.32</td><td>0.641</td><td>1.19</td></tr><tr><td>PSSRa</td><td>Chl=0.09PSSRa+0.8</td><td>0.56</td><td>0.475</td><td>0.20</td><td>0.712</td><td>1.07</td></tr><tr><td>PSSRb</td><td>Chl=0.2PSSRb+0.5</td><td>0.61</td><td>0.450</td><td>0.25</td><td>0.684</td><td>1.12</td></tr><tr><td>CTR1</td><td>Chl=-0.11CTR12+0.5CTR1+2</td><td>0.60</td><td>0.453</td><td>0.61</td><td>0.483</td><td>1.58</td></tr><tr><td>CTR2</td><td>Chl=4CTR22-8CTR2+3</td><td>0.67</td><td>0.413</td><td>0.35</td><td>0.619</td><td>1.23</td></tr><tr><td>RVI1</td><td>Chl=-0.02RVI2+0.5RVI-0.2</td><td>0.57</td><td>0.473</td><td>0.20</td><td>0.705</td><td>1.08</td></tr><tr><td>RVI2</td><td>Chl=-0.03RVI2+0.6RVI-0.3</td><td>0.55</td><td>0.480</td><td>0.19</td><td>0.709</td><td>1.08</td></tr><tr><td>PSSNRa</td><td>Chl=10PSSNRa²-10PSSNRa+3</td><td>0.60</td><td>0.453</td><td>0.22</td><td>0.698</td><td>1.09</td></tr><tr><td>PSSNRb</td><td>Chl=1.7PSSNRb²+2.8PSSNRb-1.3</td><td>0.65</td><td>0.427</td><td>0.30</td><td>0.645</td><td>1.18</td></tr><tr><td>MCARI</td><td>Chl=-81MCARI²+21MCARI+1</td><td>0.41</td><td>0.551</td><td>0.18</td><td>0.708</td><td>1.08</td></tr><tr><td>PRI</td><td>Chl=-80PRI²+16PRI+2.4</td><td>0.75</td><td>0.363</td><td>0.63</td><td>0.464</td><td>1.64</td></tr><tr><td>PSRI</td><td>Chl=285PSRI2-40PSRI+2</td><td>0.63</td><td>0.438</td><td>0.69</td><td>0.443</td><td>1.72</td></tr><tr><td>TCARI</td><td>Chl=-72TCARI2+17TCARI+1.4</td><td>0.45</td><td>0.535</td><td>0.31</td><td>0.680</td><td>1.12</td></tr><tr><td>GNDVI</td><td>Chl=-GNDVI²+7GNDVI-2</td><td>0.56</td><td>0.475</td><td>0.22</td><td>0.686</td><td>1.11</td></tr><tr><td>MCARI/OSAVI</td><td>Chl=-23.6MCARI/OSAVI²+6.5</td><td>0.50</td><td>0.507</td><td>0.44</td><td>0.626</td><td>1.22</td></tr><tr><td>SIPI</td><td>MCARI/OSAVI+2 Chl=225 692e-11.4SIPI</td><td>0.69</td><td>0.400</td><td>0.63</td><td>0.470</td><td>1.62</td></tr></table></body></html>

各参数的意义见表 2。Meanings of parameters are shown in the Table 2.

# 2.2.3各光谱指数对不同色素含量样本的饱和现象分析

图5显示了类胡萝 $\boldsymbol { \mathsf { h } }$ 含量与估算精度较高的CTR2、PSSNRa、PSSNRb的散点关系以及叶绿素含量与估算精度高的PRI、PSRI、SIPI的散点关系。当类胡萝卜素含量大于 $0 . 8 \mathrm { m g { \cdot g } ^ { - 1 } }$ 时,CTR2、PSSNRa、PSSNRb与类胡萝卜素含量的散点分布呈现随机性;当叶绿素含量大于 $2 \mathrm { m g } { \cdot } \mathrm { g } ^ { - 1 }$ 时,PRI、PSRI、SIPI与叶绿素含量的散点分布也呈现不规律变化，即色素含量增加到一定程度，高光谱参数不能有规律地反映叶绿素含量的变化，表现出上下浮动的平稳性。通过散点图确定变化的拐点，将类胡萝下素含量分为2个子集(子集I：类胡萝卜素含量小于 $0 . 8 ~ \mathrm { m g { \cdot g } ^ { - 1 } }$ ，为中低含量样本集；子集Ⅱ：类胡萝 $\curlywedge$ 素含量大于 $0 . 8 ~ \mathrm { m g { \cdot g } ^ { - 1 } }$ ，为高含量样本集)，叶绿素含量分为2个子集(子集I：叶绿素含量小于 $2 ~ \mathrm { m g { \cdot g } ^ { - 1 } }$ ，为中低含量样本集；子集Ⅱ：叶绿素含量大于 $2 \mathrm { m g } { \cdot } \mathrm { g } ^ { - 1 }$ ，为高含量样本集)。然后在子集中随机选取40个样本，分别进行类胡萝卜素含量、叶绿素含量的预测，并以预测结果的RMSE作为评价指标。若光谱指数对色素含量不同的样本具有良好的预测能力，则各子集的RMSE应趋于一致。

![](images/3c5420fbb9bf23958cff24f6eca075fa24cc5b19f3b6e2b7a9fb181ec0165e4b.jpg)  
图5水稻叶片类胡萝卜素含量、叶绿素含量与高光谱参数的散点关系变化图 Fig.5Relationships between spectral parameters and carotenoid content and chlorophyllcontent of rice leaves 各参数的意义见表 $2 _ { \circ }$ Meanings of parameters are shown in the Table 2.

根据CTR2、PSSNRa、PSSNRb估算类胡萝卜素含量并利用PRI、PSRI、SIPI估算叶绿素含量预测结果的 RMSE 值可知(表 7)，当色素含量高时，RMSE值越大，对高含量样本预测精度相对较低，存在饱和现象。其中与类胡萝下素相关系数最好的CTR2和与叶绿素相关系数最好的PRI对不同样本含量预测精度均高于其他指数。

# 2.3BDA与BP结合的色素含量估算

表8显示BDA与BP结合在建模和验证时均较大程度地提高了水稻叶片色素含量估算精度，能较好地克服饱和问题。对于类胡萝卜素的预测，BD、BDR、BNA的验证效果所得到的 $R ^ { 2 }$ 、RPD均高于原始波段 $R$ 的验证效果，RMSE则低于原始波段 $R$ 验证的对应值(图6，图7)，说明BDA的反演精度要优于原始波段 $R$ ，能够更好地挖掘与色素关系密切的信息。BD与BP结合的模型建模集 $R ^ { 2 }$ 最大，验证集$R ^ { 2 }$ 为0.61，虽然比BNA与BP结合的模型验证 $R ^ { 2 }$ 略小，但有最小的RMSEP和最大的RPD(达1.67),所以BD与BP结合的模型能够较好地估算水稻叶片类胡萝 $\boldsymbol { \mathsf { h } }$ 素含量。对于叶绿素的预测，BDA的验证效果所得到的 $R ^ { 2 }$ 、RPD均高于原始波段 $R$ 的验证效果，RMSE则低于原始波段 $R$ 验证的对应值,说明BDA比原始波段 $R$ 能够更好地预测叶绿素含量。BNA与BP结合的模型建模集 $R ^ { 2 }$ 最大，验证集 $R ^ { 2 }$ 为0.73，虽然比BD与BP结合的模型验证$R ^ { 2 }$ 略小，差异不大，但有最小的RMSEP和最大的RPD(达1.91)，所以BNA与BP结合的模型能够较好地估算水稻叶片总叶绿素含量。

表7光谱指数对水稻叶片不同色素含量样本子集预测结果的均方根误差 Table 7RMSE of prediction results for samples subsets of diferent pigment contents of rive leaves   
表8BDA与BP结合的模型估算水稻叶片类胡萝卜素和叶绿素含量的效果  

<html><body><table><tr><td rowspan="2">均方根误差 RMSE</td><td rowspan="2">卡特指数-2 (CTR2) Carter index-2 malized difference-1</td><td rowspan="2">(PSSNRa) Pigment specific nor-</td><td rowspan="2">归一化色素差异指数-1归一化色素差异指数-2光化学植被指数 (PSSNRb) Pigment specific</td><td rowspan="2">(PRI) Photochemical</td><td rowspan="2">植被衰老反射率指数 (PSRI) Plant senescence reflectance index</td><td rowspan="2">结构不敏感色素指数 (SIPI) Structure insensitive pigment index</td></tr><tr><td>normalized difference-2 reflectance index</td></tr><tr><td>子集I Subset I</td><td>0.091</td><td>0.100</td><td>0.092</td><td>0.301</td><td>0.399</td><td>0.371</td></tr><tr><td>子集Ⅱ SubsetI</td><td>0.159</td><td>0.232</td><td>0.264</td><td>0.452</td><td>0.582</td><td>0.488</td></tr></table></body></html>

Performance of combination of BDA and BP for predicting rice leaves carotenoid and chlorophyll conte   

<html><body><table><tr><td rowspan="2">色素 Pigment</td><td rowspan="2">模型 Model</td><td colspan="2">建模集 Calibration</td><td colspan="3">验证集Validation</td></tr><tr><td>R²</td><td>RMSEC (mg:g-1)</td><td>R²</td><td>RMSEP (mg:g-1)</td><td>RPD</td></tr><tr><td>类胡萝卜素 Carotenoid</td><td>R+PCA+BP</td><td>0.65</td><td>0.112</td><td>0.54</td><td>0.144</td><td>1.42</td></tr><tr><td rowspan="8">叶绿素</td><td>BD+PCA+BP</td><td>0.80</td><td>0.110</td><td>0.61</td><td>0.128</td><td>1.67</td></tr><tr><td>BDR+PCA+BP</td><td>0.72</td><td>0.099</td><td>0.61</td><td>0.132</td><td>1.53</td></tr><tr><td>NBDI+PCA+BP</td><td>0.61</td><td>0.113</td><td>0.50</td><td>0.152</td><td>1.39</td></tr><tr><td>BNA+PCA+BP</td><td>0.74</td><td>0.108</td><td>0.64</td><td>0.140</td><td>1.65</td></tr><tr><td>R+PCA+BP</td><td>0.77</td><td>0.304</td><td>0.59</td><td>0.486</td><td>1.17</td></tr><tr><td>BD+PCA+BP</td><td>0.82</td><td>0.269</td><td>0.74</td><td>0.423</td><td>1.77</td></tr><tr><td>BDR+PCA+BP</td><td>0.79</td><td>0.317</td><td>0.63</td><td>0.415</td><td>1.55</td></tr><tr><td>NBDI+PCA+BP</td><td>0.74</td><td>0.319</td><td>0.61</td><td>0.402</td><td>1.56</td></tr><tr><td></td><td>BNA+ PCA+BP</td><td>0.83</td><td>0.293</td><td>0.73</td><td>0.343</td><td>1.91</td></tr></table></body></html>

各参数的意义见表 $2 _ { \circ }$ Meanings of parameters are shown in the Table 2.

1.4 reeeee a y= 0.91x+0.07 y= 0.86x+0.12 1.2 RMSEC=0.110 mgg R²= 0.80 X RMSEP=0.128 mggx R²=0.61 1.0 X X n=80 ■ 1 X X 0.8 ■ n=40 X 0.6 X 分藥期Tillering X 拔节期Jointing 0.4 ×孕穗期Booting 0.2 · ×抽穗期Heading ·灌浆期Filling L 0 0.2 0.4 0.6 0.8 1.0 1.2 1.4 0 0.2 0.4 0.6 0.8 1.0 1.2 1.4 类胡萝卜素实测值Measured carotenoid (mg'g-1)

4.0 a rre 3.5 3.0 RMSEC=0.293 mg:g y=0=6x +0.32 RMSEP=0.343 mgg y=0=5x+0.31 店 2.5 n=80 RPD=1.91 X \* \* 2.0 分藥期Tillering + 1.5 . \* ·拔节期Jointing \* \* 1.0 ×孕穗期Booting 0.5 \*抽穗期Heading ·灌浆期Filling L 0 0.5 1.0 1.5 2.0 2.5 3.0 3.5 4.0 0 0.5 1.0 1.5 2.0 2.5 3.0 3.5 4.0 叶绿素实测值Measured chlorophyll $( \mathbf { m g \cdot g ^ { - 1 } } )$ （24

http://www.ecoagri.ac.cn

与基于光谱参数建立的最佳回归模型相比，BDA与BP结合建立的模型均较大程度地提高了水稻叶片色素含量的估算精度。对比类胡萝卜素和叶绿素的估算模型，叶绿素的估算模型精度均高于类胡萝卜素的模型精度，由于类胡萝卜素和叶绿素的吸收峰所处波段重叠，且叶片中叶绿素含量远高于类胡萝卜素含量，因此类胡萝卜素含量的估算较为困难。

# 3结论与讨论

本研究为了解决高光谱植被指数反演水稻叶片色素含量存在的饱和问题，尝试将波段深度分析与BP神经网络结合建立水稻叶片色素含量估算模型。并与17种光谱参数分别建立的模型进行了精度比较。

研究表明，进行连续统去除变换后，更加突出了水稻叶片的吸收特征的差异，挖掘了更多的潜在信息，使得不同色素含量光谱曲线的差异性特征得到一定程度上的增强，尤其是红吸收谷区域的波段深度特征蕴藏了较多与水稻叶片色素含量相关的信息，能够更好地估算水稻叶片色素含量[。主要原因可能是波段深度分析处理可以有效减弱土壤背景、大气散射和吸收对目标光谱特征的影响。Kokaly等[13指出，波段深度分析方法可以降低土壤背景和大气吸收的影响，有效估算出叶片的生化参数。Mutanga等[12表明，波段深度分析可以解决现有指数的饱和问题，能够估算高密度植被区域的生物量。

大量研究结果表明，由于受天气、日照、叶片几何结构、土壤背景、人为操作等因素的影响，植被的生理生化参量与冠层光谱的关系是非线性的[30-31]。而神经网络对复杂且非线性问题的拟合有着极大的优势，能够很好的预测非线性函数逼近等问题，成为当前解决非线性问题的重要方法。

植被指数在色素含量较高时存在饱和问题，构建植被指数与水稻叶片色素含量的最佳回归模型估算精度不高。马文勇等[32]通过植被指数反演草地叶绿素，结果表明光谱指数构造形式多样，且与草地叶绿素含量关系复杂，在一定程度上影响叶绿素的估算精度。姜海玲等[33]通过地面高光谱数据重采样模拟不同传感器，利用光谱指数反演植被叶绿素含量，指出不同传感器的光谱指数估算精度和稳定性均不同。本文将波段深度分析与BP神经网络结合建立的水稻叶片色素含量模型能较好地解决饱和问题针对植被指数所囊括的波段具有一定的局限性，能够实现不同波段之间的优势互补，提高估算精度。

通过对可见光波段数据的波段深度分析，利用主成分分析进行降维，有效保留了信息，增强了网络性能，防止过度拟合，提高了色素含量反演精度。然而本文只针对单一品种和小区试验条件下，尚需要通过不同地区和品种类型等田间试验做进一步的验证和完善，辐射传输模型更具有普适性，仍需我们开展相关研究，建立经验-物理耦合模型[34]，进一步提高模型估算的准确性和适用性。同时，在更大尺度、更广范围内实现所构建模型与空间遥感信息的结合，可为大区域估算水稻叶片色素含量提供理论依据和实践参考。

# 参考文献References

[1]唐延林，黄敬峰，王人潮．水稻不同发育时期高光谱与叶 绿素和类胡萝卜素的变化规律[J]．中国水稻科学，2004, 18(1): 59-66 TangYL,HuangJF,Wang RC.Change law of hyperspectral data with chlorophyll and carotenoid for rice at different developmental stages[J].Chinese Journal of Rice Science, 2004,18(1): 59-66   
[2]王福民，黄敬峰，王秀珍．水稻叶片叶绿素、类胡萝卜素含 量估算的归一化色素指数研究[J]．光谱学与光谱分析, 2009,29(4): 1064-1068 Wang FM,Huang JF,Wang X Z.Normalized difference ratio pigment index for estimating chlorophyll and carotenoid contents in leaves of rice[J]. Spectroscopy and Spectral Analysis,2009,29(4): 1064-1068   
[3]Blackburn G A.Relationships between spectral reflectance and pigment concentrations in stacks of deciduous broadleaves[J].Remote Sensing of Environment,1999,70(2): 224-237   
[4] Sims D A,Gamon JA. Relationships between leaf pigment content and spectral reflectance across a wide range of species, leaf structures and developmental stages[J]. Remote Sensing of Environment, 2002,81(2/3): 337-354   
[5]Datt B.Remote sensing of chlorophyll a,chlorophyll b,chlorophyll $\ a + b$ ，and total carotenoid content in eucalyptus leaves[J].Remote Sensing of Environment,1998,66(2): 111-121   
[6]Lichtenthaler $\mathrm { ~ H ~ K ~ }$ ,Gitelson A,Lang M. Non-destructive determination of chlorophyll content of leaves of a green and an aurea mutant of tobacco by reflectance measurements[J]. Journal of Plant Physiology,1996,148(3/4): 483-493   
[7]GitelsonAA,MerzlyakMN,Lichtenthaler $\mathrm { ~ H ~ K ~ }$ .Detection of red edge position and chlorophyll content by reflectance measurements near $7 0 0 \ \mathrm { n m [ J ] }$ . Journal of Plant Physiology, 1996,148(3/4): 501-508   
[8]Gitelson A A,Merzlyak M N.Remote estimation of chlorophyll content in higher plant leaves[J]. International Journal of Remote Sensing,1997,18(12): 2691-2697   
[9] 姚付启，张振华，杨润亚，等．基于红边参数的植被叶绿素 含量高光谱估算模型[J].农业工程学报，2009、25(S2): 123-129 Yao F Q, Zhang Z H, Yang R Y,et al. Hyperspectral models for estimating vegetation chlorophyll content based on red edge parameter[J]. Transactions of the CSAE,2009,25(S2): 123-129   
[10]黄敬峰，王福民，王秀珍．水稻高光谱遥感实验研究[M]. 杭州：浙江大学出版社,2010 Huang JF,Wang F M, Wang X Z. Hyperspectral Experiment for Paddy Rice Remote Sensing[M]. Hangzhou: Zhejiang University Press,2010   
[11] Mutanga O, Skidmore A K. Integrating imaging spectroscopy and neural networks to map grass quality in the Kruger National Park,South Africa[J]. Remote Sensing of Environment, 2004,90(1): 104-115   
[12] Mutanga O, Skidmore A K.Hyperspectral band depth analysis for a better estimation of grass biomass(Cenchrus ciliaris) measured under controlled laboratory conditions[J]. International Journal of Applied Earth Observation and Geoinformation,2004,5(2): 87-96   
[13] Kokaly R F,Clark R N. Spectroscopic determination of leaf biochemistry using band-depth analysis of absorption features and stepwise multiple linear regression[J]. Remote sensing of Environment,1999,67(3): 267-287   
[14] Chen J,Gu S,Shen M G,et al. Estimating aboveground biomass of grassand having a high canopy cover: An exploratory analysis of in situ hyperspectral data[J]. International Journal of Remote Sensing,2009,30(24): 6497-6517   
[15] 黄秋婵，韦友欢，韦方立，等．常见夹竹桃科植物叶片颜色 及类胡萝卜素含量的比较分析[J]．安徽农业科学，2011, 39(25): 15203-15204 Huang Q C, Wei Y H, Wei F L,et al. The comparative analysis of leaf color and carotenoids content of the common apocynaceae plants[J]. Journal of Anhui Agricultural Science, 2011,39(25): 15203-15204   
[16] 贾方方，张黎明，任天宝，等．基于 BP 神经网络的烟草叶 片质体色素高光谱反演[J]．烟草科技,2016,49(7):8-13 JiaFF, Zhang L M,Ren TB,et al. Hyperspectral inversion to estimate plastid pigment contents in tobacco leaves based on BP neural network[J]. Tobacco Science &Technology, 2016, 49(7): 8-13   
[17] Wang S Q,Li W D,Li J, et al. Prediction of soil texture using FT-NIR spectroscopy and PXRF spectrometry with data fusion[J]. Soil Science,2013,178(11): 626-638   
[18]Gitelson A,Merzlyak M N. Spectral reflectance changes associated with autumn senescence of Aesculus hippocastanum L.and Acer platanoides L. leaves.Spectral features and relation to chlorophyll estimation[J].Journal of Plant Physiology，1994, 143(3): 286-292   
[19] Blackburn G A.Quantifying chlorophylls and caroteniods at leaf and canopy scales: An evaluation of some hyperspectral approaches[J]. Remote Sensing of Environment,1998,66(3):

# 273-285

[20] Carter G A.Ratios of leaf reflectances in narrow wavebands as indicators of plant stress[J]. International Journal of Remote Sensing,1994,15(3): 697-703   
[21] Rouse Jr JW, Haas R H, Deering D W. Monitoring the vernal advancement and retrogradation (green wave effect) of natural vegetation[R]. Greenbelt, MD, USA: NASA/GSFC,1974   
[22]朱西存，赵庚星，王瑞燕，等．苹果叶片的高光谱特征 及其色素含量监测[J]．中国农业科学，2010，43(6): 1189-1197 Zhu X C, Zhao G X,Wang R Y,et al. Hyperspectral characteristics of apple leaves and their pigment contents monitoring[J].Chinese Journal of Rice Science，2010，43(6): 1189-1197   
[23] Daughtry C S T,Walthall C L, Kim M S,et al. Estimating corn leaf chlorophyll concentration from leaf and canopy reflectance[J]. Remote Sensing of Environment, 200o,74(2): 229-239   
[24] Gamon JA,Penuelas J,Field C B.A narrow-waveband spectral index that tracks diurnal changes in photosynthetic efficiency[J]. Remote Sensing of Environment,1992,41(1): 35-44   
[25] Merzlyak M N,Gitelson A A，Chivkunova O B,et al. Non-destructive optical detection of pigment changes during leaf senescence and fruit ripening[J]. Physiologia Plantarum, 1999,106(1): 135-141   
[26] Gitelson A A, Kaufman Y J,Merzlyak MN. Use of a green channel in remote sensing of global vegetation from EOS-MODIS[J]. Remote Sensing of Environment,1996, 58(3): 289-298   
[27] Penuelas J,Baret F,Filella I. Semi-empirical indices to assess carotenoids/chlorophyll a ratio from leaf spectral reflectance[J]. Photosynthetica,1995,31(2): 221-230   
[28]薛惠云，张永江，刘连涛，等．干旱胁迫与复水对棉花叶片 光谱、光合和荧光参数的影响[J]．中国农业科学，2013, 46(11): 2386-2393 Xue HY, Zhang Y J, Liu L T,et al. Responses of spectral reflectance,photosynthesis and chlorophyll fluorescence in cotton during drought stress and rewatering[J]. Scientia Agricultura Sinica,2013,46(11):2386-2393   
[29]Filella I,Porcar-Castell A,Munné-Bosch S,et al. PRI assessment of long-term changes in carotenoids/chlorophyll ratio and short-term changes in de-epoxidation state of the xanthophyll cycle[J]. International Journal of Remote Sensing. 2009,30(17): 4443-4455   
[30] Curran P J,Dungan JL,Peterson D L.Estimating the foliar biochemical concentration of leaves with reflectance spectrometry:Testing the Kokaly and Clark methodologies[J]. Remote Sensing of Environment,2001,76(3): 349-359   
[31]杨可明，孙阳阳，刘飞，等．叶绿素含量 BP 反演模型的光 谱信息输入因子构建研究[J]．科学技术与工程，2015,

# 15(15): 82-87

Yang K M, Sun Y Y,Liu F,et al.Research on constructing the input factors of BP model for inversing leaf chlorophyll content based on the spectral information[J]. Science Technology and Engineering,2015,15(15): 82-87

[32]马文勇，王训明．基于高光谱分析的草地叶绿素含量估算 研究进展[J].地理科学进展,2016,35(1):25-34 MaWY,Wang X M.Progress on grassland chlorophyll content estimation by hyperspectral analysis[J].Progress in Geography,2016,35(1):25-34

[33]姜海玲，杨杭，陈小平，等．利用光谱指数反演植被叶绿素

含量的精度及稳定性研究[J].光谱学与光谱分析，2015, 35(4):975-981 JiangHL,YangH,Chen XP,et al.Research on accuracy and stability of inversing vegetation chlorophyll content by spectral index method[J].Spectroscopy and Spectral Analysis, 2015,35(4):975-981 [34]徐晋，蒙继华．农作物叶绿素含量遥感估算的研究进展与 展望[J].遥感技术与应用,2016,31(1):74-85 Xu J,Meng JH.Overview on estimating crop chlorophyll content with remote sensing[J].Remote Sensing Technology and Application,2016,31(1): 74-85