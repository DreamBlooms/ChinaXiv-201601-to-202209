# MLR和PLSR的沙壤土盐分含量光谱检测对比研究

王涛¹,²，喻彩丽1,²，姚娜,²，王斐¹²，白铁成1,3(1 塔里木大学信息工程学院,新疆阿拉尔843300；2 新疆南疆农业信息化研究中心,新疆阿拉尔 843300;3Gembloux Agro-Bio Tech,University of Liege,Gembloux 25030,Belgium)

摘要：为了快速有效检测南疆地区典型土壤(沙壤土)的盐分含量变化，利用光谱仪和电导仪测得南疆阿拉尔市红枣种植区盐渍土近红外高光谱和电导率数据，基于7种不同光谱预处理方法和2种特征波长选择算法，分别建立多元线性回归(MLR)和偏最小二乘回归(PLSR)的土壤盐分监测模型。结果表明：7种预处理方法中，归一化，多元散射，变量标准化和一阶导数能够有效提高土壤盐分的预测模型精度。基于多元逐步回归(SMR)波长选择方法的多元线性回归(SMLR)模型的1 $\mathring { \Omega } _ { v a l } { } ^ { 2 } < 0 . \ 9 4 8 \ 9 , R P D < 6 . \ 2 9 4 \ 9 , R M S E P > 0 . \ 4 3 5 \ 6$ ;基于连续投影算法（SPA)的多元线性回归（SPA-MLR)模型的 ${ R _ { v a l } } ^ { 2 } < 0 . 9 5 6 ~ 8 , R P D < 6 . 9 2 2 ~ 1 , R M S E P > 0 . 3 6 1 ~ 6$ ,预测结果要优于偏最小二乘回归(PLSR)模型,其中基于归一化处理后的 SMLR和 SPA-MLR的预测精度最为理想,分别为 ${ R _ { v a l } } ^ { 2 } =$ （204号$0 . 9 7 9 \ 2 , R P D = 9 . 9 0 7 \ 8 \ , R M S E P = 0 . 2 8 7 \ 6$ 和 ${ R _ { v a l } } ^ { 2 } = 0 . 9 8 0 \ 5 \mathrm { , } R P D = 1 0 . 5 0 \mathrm { , } R M S E P = 0 . 2 7 8 \ 3$ ，而且筛选的特征波长较少。说明归一化是更有效的光谱预处理方法，多元线性回归(MLR)更适合建立南疆典型沙壤土盐分含量的预测模型。

关键词：土壤电导率；多元线性回归；偏最小二乘回归方法;

中图分类号： S151.9 文献标识码：A 文章编号

土壤盐渍化是新疆南部地区土地退化的主要问题，对南疆农业可持续发展以及生态环境的保护至关重要[1]。传统土壤盐渍化监测,依赖于土壤理化分析方法，不能快速有效的反映区域土壤盐渍化动态信息[2],近年来通过土壤光谱信息估算土壤中全氮[3]水分[4]、有机质[5]等研究较多，利用高光谱预测土壤盐渍化定量分析也逐步展开，遥感技术利用土壤的盐分光谱特征，能够快速、实时的获得盐渍化土壤的盐分信息[6-7],因此,研究土壤盐分的光谱特征，建立基于光谱分析的土壤盐分定量反演模型是一项重要的工作。

土壤盐渍化的高光谱定量反演模型是土壤盐渍化高光谱遥感监测的重要研究内容之一。目前，已有学者利用不同的研究方法对不同地区的盐渍化土壤盐分进行了高光谱定量反演。常用的建模方法包括偏最小二乘回归、多元线性回归和主成分回归等。

GOLDSHLEGE $\mathbf { N } ^ { [ 8 ] }$ 等通过获取番茄地高光谱反射率与土壤盐分含量，使用偏最小二乘法建立预测模型，取得了较好的预测精度，其中预测均方根误差RMSE是 $0 . 6 \%$ ，决定系数 $R ^ { 2 }$ 是0.87。NETO OR[9]等在巴西半干旱地区使用土壤电导率进行土壤盐渍化评价，对比使用主成分回归，多元线性回归和偏最小二乘法建立预测模型，其中偏最小二乘法获得了较好的预测精度，RMSE是0.22，RPD是2.21。彭杰等[10]通过分析南疆地区土壤的高光谱数据与盐分含量关系，基于连续统去除法所建模型的相对分析误差(RPD)达2.5以上。屈永华等[1建立了内蒙古河套灌区土壤盐分与高光谱数据的偏最小二乘回归（PLSR）模型，验证数据的决定系数（ $R ^ { 2 }$ )为0.73,预测方差比为1.79。丁建丽等[12]通过分析新疆塔里木盆地北缘渭干河一库车河三角洲绿洲盐渍化土壤光谱信息与盐分关系，发现利用综合光谱指数来监测土壤盐渍化是非常有效的，预测的RMSE为0.009。段鹏程等[13]通过对新疆阜康500水库下游的盐渍化土壤实地定点取样和光谱测量，建立了土壤反射光谱与盐分含量之间的多元线性回归预测模型，在不同类型的土壤含盐量预测模型中，一阶导数建立的模型预测效果最优， $R ^ { 2 }$ 均超过0.983。李亚莉等[14]以新疆典型盐渍化灌区为研究对象,获取不同质地的土壤水盐含量光谱曲线，采用偏最小二乘回归方法构建水盐反演模型，模型的决定系数$R ^ { 2 }$ 均大于0.65。

尽管已有研究利用土壤电导率和含盐量指标，取得了相对理想的反演效果，但不同区域的土壤结构、成分差异显著，不同类型土壤的高光谱响应和敏感波段也具有一定的差异性，不同方法建模的预测效果也有很大不同。因此，本文在总结前人研究基础上，以新疆阿拉尔沙壤土为研究区，依据高光谱数据与土壤电导率实测数据，对获取的土壤光谱数据进行多元散射校正、矢量归一化、变量标准化、移动平滑、SG平滑、一阶导和二阶导等不同预处理，分别使用多元逐步回归（SMR）与连续投影算法（SPA)筛选土壤电导率敏感特征波长，对比分析多元线性回归(MLR)和偏最小二乘回归法(PLSR)建立土壤电导率检测模型的精度和效率，旨在筛选和建立一种适合该区域的土壤盐分预测方法和模型，为利用遥感技术快速、无损监测新疆南部地区土壤盐渍化提供理论依据和实用方法。

# 1 材料与方法

# 1.1 数据采集

试验区位于新疆阿拉尔市， $8 1 ^ { \circ } 1 3 ^ { \prime } 3 ^ { \prime \prime } \mathrm { E }$ ， $4 0 ^ { \circ } 3 4 ^ { \prime }$ $4 5 ^ { \prime \prime } \mathrm { N }$ ，枣园土壤类型为沙壤土。分别采集土壤表层盐分已结晶的表层土和 $0 \sim 2 0 \ \mathrm { c m }$ 的正常土壤，按$1 : 9 9 , 2 : 9 8 , \cdots , 9 9 : 1$ 的比例混合共获得142份不同盐分的土壤样本，带回实验室自然风干，磨细过筛，用于光谱及理化分析测试用。因为土壤电导率已成为国际上广泛使用的盐分表示方式[15],本研究使用电导率代表土壤盐分含量状况，电导率采用水土比为5:1,利用DDS—307电导率仪直接进行测定。光谱采用ZolixGaiaSorter近红外成像高光谱仪，光谱测定范围 $9 0 0 \sim 1 ~ 7 0 0 ~ \mathrm { { n m } }$ （实际测量到 $1 \ 7 5 0 \ \mathrm { n m }$ ），光谱分辨率 $5 \ \mathrm { n m }$ ,光谱采样点 $4 \ \mathrm { n m }$ ，共256个波段测定获取高光谱数据，每次测量前进行标准白板校正，每个样点重复采集10条光谱曲线，取平均值作为该样本的光谱反射率，剔除了2份异常样本后（光谱曲线缺失），共获得140个有效样本，如表1是根据 SPXY 算法[16挑选出的100 份样品作为定标集，其他40份土壤样品作为预测集。

光谱曲线通过异常剔除和算数平均值处理后，获取140个样本的光谱吸收谱（图1）。

# 1.2光谱数据预处理与建模方法

# 1.2.1光谱数据预处理方法与特征波长选择方法

由于近红外光谱区的吸收强度弱，光谱信噪比低，谱带易重叠，为了消除仪器噪声等对光谱数据的影响以及准确分析土壤样品中的含盐量，有必要对土壤原始光谱进行预处理以提高检测的精度。对原始光谱数据分别进行了多元散射校正（MSC）、矢量归一化（VN）、变量标准化（SNV）、移动平滑（MA）、SG平滑(SG)一阶导(1-Der)和二阶导(2-Der)等预处理，其中MSC，SNV，VN可以校正样品因颗粒散射而引起的光谱误差，VN可以较好的改善样品稀疏时的预测结果，平滑处理可以有效平滑高频噪声，提高信噪比，一阶导数和二阶导数分别用于消除光谱中基线的平移和漂移，可有效消除其他背景干扰，分

# 表1土壤校正集和预测集盐分含量统计

Tab.1 Statistics of soil electrical conductivity in calibration and validation set   

<html><body><table><tr><td>数据集</td><td>样本数</td><td>最小值</td><td>最大值</td><td>平均值</td><td>标准差</td></tr><tr><td>校正集</td><td>100</td><td>0.2720</td><td>10.540 0</td><td>5.656 1</td><td>2.8131</td></tr><tr><td>预测集</td><td>40</td><td>1.144 0</td><td>9.870 0</td><td>1.144 0</td><td>2.542 2</td></tr></table></body></html>

![](images/61d86ab86bfd8fb6550e651ff55822542b1f12a2ad4267e2dbebe167fd0a31b9.jpg)  
图1土壤原始光谱曲线图Fig.1Original spectrum of soil

辨重叠峰,提高分辨率和灵敏度[17-18] O

土壤电导率敏感特征波长选择分别采用多元逐步回归（SMR）与连续投影算法（SPA）算法，其中SMR算法可集成在MLR建模算法中，构建多元线性回归模型（SMLR）。

1.2.2建模方法及评价指标SMLR是在多元线性回归的基础上发展起来的[15,19],逐步回归按照全局自变量对因变量的作用、显著程度或贡献率，逐个引入到回归方程中，剔除对因变量不显著的自变量[20-21],建立多元线性回归模型,对因变量进行预测。

PLSR吸取了主成分分析中提取主成分的思想，能够简化数据结构，主成分之间不但相关性最小，而且与因变量的相关性最大，同时，能够克服主成分分析对自变量有较强解释的能力，有效提取对系统解释性最强的综合变量，提高模型的估测能力。因而，本研究分别采用多元线性回归和偏最小二乘回归方法[22-23]构建土壤电导率反演模型,预测光谱特征值和土壤电导率之间的关系。

预测模型采用外部验证，对其稳定性和预测精度进行评价，采用建模决定系数( ${ R _ { c a l } } ^ { 2 }$ ）、建模均方根误差（RMSEE）、预测决定系数（ ${ R _ { v a l } } ^ { 2 }$ )、预测均方根误差（RMSEP）、相对分析误差（RPD)为精度评价指标， ${ R _ { v a l } } ^ { 2 }$ 和 $R P D$ 越大,RMSEP越小,说明预测效果越好[24]

# 2数据处理结果与分析

# 2.1土壤电导率多元线性回归模型

对原始光谱分别进行VN、MSC、SNV、SG等预处理，在SMR特征波长选择的基础上，分别建立多元逐步线性回归（SMLR)模型，并进行验证。首先将样品电导率作为因变量，设定模型入选变量的 $F$ 检验概率为0.05，模型剔除变量的 $F$ 检验概率为0.1,将其对应的土壤原始光谱及其预处理数据作为自变量，建立SMLR模型，其预测结果如表2。基于7种预处理方法建模方程的 ${ R _ { c a l } } ^ { 2 }$ 和预测 ${ R _ { v a l } } ^ { 2 }$ 都很高,而且都大于交叉验证的 ${ R _ { c v } } ^ { 2 }$ 。其中，归一化,多元散射校正，变量标准化的预测精度相对较好且优于原始光谱，预测的RMSEP在0.2876和0.3312之间， ${ R _ { v a l } } ^ { 2 }$ 在0.9690和0.9792之间,RPD在8.1044和9.9078之间，其中归一化处理后的预测精度最高 $^ { \prime } R M S E P = 0 . 2 8 7 ~ 6 , R _ { v a l } { } ^ { 2 } = 0 . 9 7 9 ~ 2 , R P D =$ 9.907 8)。

在原始光谱预处理基础上，使用SPA筛选的特征波长作为自变量，建立SPA-MLR多元线性回归模型，对应的土壤电导率作为因变量，预测结果如表3。对于7种预处理方法,建模方程的 ${ R _ { c a l } } ^ { 2 }$ 和预测${ R _ { v a l } } ^ { 2 }$ 都很高,而且都大于交叉验证的 ${ R _ { c v } } ^ { 2 }$ 。移动平滑和二阶导数的预测精度较差，其它预处理的预测精度相对较好且优于原始光谱，模型的RMSEP在0.2675和0.3079之间， ${ R _ { v a l } } ^ { 2 }$ 在0.9689和0.980 5之间，RPD在8.1305和11.178之间，其中一阶导数预测精度最高 $\mathit { ^ { \prime } R M S E P } = 0 . 2 6 7 5 , { R _ { v a l } } ^ { 2 } = 0 . 9 8 0 5$ ，$R P D = 1 1 . 1 7 8 \$ ）。尽管经过MSC,SNV,1-Der和2-Der预处理后SPA筛选的变量较多，但和SMLR的预测结果比较,SPA-MLR 预测的 RMSEP 降低， ${ R _ { v a l } } ^ { 2 }$ 和RPD提高，说明SPA-MLR的预测效果略好于SMLR方法。

# 2.2土壤电导率偏最小二乘回归模型

原始光谱预处理基础上，直接使用PLSR建立土壤电导率回归模型，预测效果如表4。其中主成分数表示从土壤光谱曲线中提取的用于解释土壤电导率的成分个数，对于建模所需提取的主成分个数，可以通过交叉有效性检验来确定。基于7种预处理建模的 ${ R _ { v a l } } ^ { 2 }$ 和预测 ${ R _ { c a l } } ^ { 2 }$ 都很高,而且都大于交叉验证的 ${ R _ { c v } } ^ { 2 }$ 。除了卷积平滑的预测精度相对较差,其他处理后的模型预测值都优于原始光谱，预测的${ R _ { v a l } } ^ { 2 }$ 在0.9543和0.9737之间,RMSEP在0.3228和0.4004之间， $R P D$ 在6.6798和8.8381之间，说明在光谱不同预处理的模型预测精度存在较大差异。从预测的 ${ R _ { v a l } } ^ { 2 }$ 来看归一化，移动平滑，多元散射校正,变量标准交化，一阶导数，二阶导数都大于0.95，预测效果均较好，其中归一化处理后的精度最高( $R M S E P = 0$ 322 8, ${ R _ { v a l } } ^ { 2 } \ = \ 0$ . 973 7, $R P D =$ 8.838 1)。

表2基于逐步回归SMR的土壤电导率多元线性回归模型(SMLR)  
Tab.2Soil electrical conductivity multiple linear regression model based on SMLR   

<html><body><table><tr><td rowspan="2">数据变换</td><td rowspan="2">特征波 段个数</td><td colspan="2">定标</td><td colspan="2">交叉验证</td><td colspan="3">预测</td></tr><tr><td>RMSEE</td><td>Rcal²</td><td>RMSECV</td><td>Rc²</td><td>RMSEP</td><td>Rual²</td><td>RPD</td></tr><tr><td>原始光谱</td><td>4</td><td>0.477 4</td><td>0.941 0</td><td>0.505 0</td><td>0.934 2</td><td>0.388 6</td><td>0.953 2</td><td>6.579 8</td></tr><tr><td>归一化</td><td>3</td><td>0.4239</td><td>0.948 4</td><td>0.442 0</td><td>0.943 9</td><td>0.287 6</td><td>0.979 2</td><td>9.9078</td></tr><tr><td>移动平滑</td><td>5</td><td>0.380 5</td><td>0.964 2</td><td>0.4063</td><td>0.959 2</td><td>0.362 0</td><td>0.956 2</td><td>6.8051</td></tr><tr><td>多元散射校正</td><td>3</td><td>0.415 5</td><td>0.952 8</td><td>0.435 0</td><td>0.948 3</td><td>0.331 2</td><td>0.969 0</td><td>8.104 4</td></tr><tr><td>变量标准化</td><td>3</td><td>0.397 0</td><td>0.956 9</td><td>0.416 6</td><td>0.952 6</td><td>0.3314</td><td>0.969 4</td><td>8.154 9</td></tr><tr><td>卷积平滑</td><td>4</td><td>0.424 6</td><td>0.955 0</td><td>0.446 6</td><td>0.950 3</td><td>0.388 8</td><td>0.951 5</td><td>6.462 0</td></tr><tr><td>一阶导数</td><td>5</td><td>0.474 2</td><td>0.937 9</td><td>0.506 4</td><td>0.929 3</td><td>0.425 6</td><td>0.948 9</td><td>6.294 9</td></tr><tr><td>二阶导数</td><td>6</td><td>0.419 2</td><td>0.950 6</td><td>0.458 9</td><td>0.9410</td><td>0.435 6</td><td>0.949 4</td><td>6.325 7</td></tr></table></body></html>

原始光谱预处理后，使用SPA算法筛选敏感波长建立偏最小二乘法回归模型（SPA-PLSR），SPA筛选的特征波长作为自变量，对应的土壤电导率作为因变量，预测结果如表5。对卷积平滑处理后的光谱建立SPA-PLSR模型，没有通过O.05的水平检验，因此没有建立预测模型。由表5可以看出，对于6种预处理方法，经过SPA特征波长选择后的建模预测精度都略低于原始光谱，尽管多元散射校正和一阶导数的预测精度相对较好，但是所选择的特征波长较多，计算量较大。这可能因为经过SPA选择后入选PLSR的主成分与直接使用PLSR的主成分相比较数目明显减少，丢失了部分有效信息导致模型的预测精度有所下降。

Tab.3Soil electrical conductivity multiple linear regression model based on SPA(SPA-MLR)   
表4土壤电导率偏最小二乘回归模型(PLSR)  

<html><body><table><tr><td rowspan="2">数据变换</td><td rowspan="2">特征波 段个数</td><td colspan="2">定标</td><td colspan="2">交叉验证</td><td colspan="3">预测</td></tr><tr><td>RMSEE</td><td>Rcal²</td><td>RMSECV</td><td>Rc²</td><td>RMSEP</td><td>Rval²</td><td>RPD</td></tr><tr><td>原始光谱</td><td>5</td><td>0.419 6</td><td>0.954 6</td><td>0.447 9</td><td>0.948 2</td><td>0.311 8</td><td>0.970 7</td><td>8. 444 5</td></tr><tr><td>归一化</td><td>7</td><td>0.414 7</td><td>0.950 7</td><td>0. 449 7</td><td>0.942 1</td><td>0.278 3</td><td>0.980 5</td><td>10.501 0</td></tr><tr><td>移动平滑</td><td>6</td><td>0.392 7</td><td>0.961 8</td><td>0.424 7</td><td>0.955 4</td><td>0.361 6</td><td>0.956 8</td><td>6.922 1</td></tr><tr><td>多元散射校正</td><td>14</td><td>0.375 0</td><td>0.961 6</td><td>0.4373</td><td>0.9481</td><td>0.2863</td><td>0.977 0</td><td>9. 791 1</td></tr><tr><td>变量标准化</td><td>14</td><td>0.372 2</td><td>0.962 2</td><td>0.430 6</td><td>0.949 5</td><td>0.304 9</td><td>0.9741</td><td>9. 152 4</td></tr><tr><td>卷积平滑</td><td>5</td><td>0.405 0</td><td>0. 959 1</td><td>0.431 3</td><td>0.953 7</td><td>0.307 9</td><td>0.968 9</td><td>8.130 5</td></tr><tr><td>一阶导数</td><td>18</td><td>0.366 7</td><td>0.9631</td><td>0.453 4</td><td>0.944 0</td><td>0.267 5</td><td>0.980 5</td><td>11. 178 0</td></tr><tr><td>二阶导数</td><td>12</td><td>0.399 3</td><td>0.955 2</td><td>0.4658</td><td>0.939 5</td><td>0.341 6</td><td>0.969 6</td><td>8.227 3</td></tr></table></body></html>

表3基于SPA选择特征波长的土壤电导率多元线性回归模型(SPA-MLR)  
表5基于 SPA选择特征波长的土壤电导率偏最小二乘回归模型(SPA-PLSR)  

<html><body><table><tr><td rowspan="2">数据变换</td><td colspan="2">定标</td><td colspan="2">交叉验证</td><td colspan="2">预测</td><td colspan="2">主成份</td></tr><tr><td>RMSEE</td><td>Rcal²</td><td>RMSECV</td><td>Rce</td><td>RMSEP</td><td>Ral²</td><td>RPD</td><td></td></tr><tr><td>原始光谱</td><td>0. 691 7</td><td>0.874 1</td><td>0. 702 0</td><td>0. 871 1</td><td>0. 556 9</td><td>0.916 0</td><td>5.087 9</td><td>4</td></tr><tr><td>归一化</td><td>0.397 1</td><td>0.954 8</td><td>0. 448 7</td><td>0.941 9</td><td>0.322 8</td><td>0.973 7</td><td>8.8381</td><td>6</td></tr><tr><td>移动平滑</td><td>0.383 0</td><td>0.963 7</td><td>0.434 8</td><td>0.953 4</td><td>0.365 7</td><td>0.954 3</td><td>6.679 8</td><td>7</td></tr><tr><td>多元散射校正</td><td>0.4087</td><td>0.954 3</td><td>0.437 0</td><td>0.947 8</td><td>0.344 7</td><td>0.966 7</td><td>7. 852 6</td><td>4</td></tr><tr><td>变量标准化</td><td>0.406 5</td><td>0.954 8</td><td>0.434 5</td><td>0.948 4</td><td>0.343 5</td><td>0.967 0</td><td>7. 877 5</td><td>4</td></tr><tr><td>卷积平滑</td><td>0.673 5</td><td>0.884 9</td><td>0. 712 9</td><td>0.8721</td><td>0.615 7</td><td>0.884 5</td><td>4.489 4</td><td>4</td></tr><tr><td>一阶导数</td><td>0.3568</td><td>0.965 1</td><td>0.491 3</td><td>0.934 9</td><td>0.337 8</td><td>0.969 3</td><td>8.8503</td><td>7</td></tr><tr><td>二阶导数</td><td>0.3863</td><td>0.9581</td><td>0.450 0</td><td>0.942 2</td><td>0.400 4</td><td>0.958 7</td><td>7. 176 5</td><td>5</td></tr></table></body></html>

Tab.4Soil electrical conductivity partial least squares regression model （PLSR)   
Tab.5Soil electrical conductivity partial least squares regression model based on SPA（SPA-PLSR)   

<html><body><table><tr><td rowspan="2">数据变换</td><td rowspan="2">特征波 段个数</td><td colspan="2">定标</td><td colspan="2">交叉验证</td><td colspan="2">预测</td><td colspan="2">主成份</td></tr><tr><td>RMSEE</td><td>Rcal²</td><td>RMSECV</td><td>Rc²</td><td>RMSEP</td><td>Rral²</td><td>RPD</td><td></td></tr><tr><td>原始光谱</td><td>5</td><td>0.419 6</td><td>0.954 6</td><td>0.447 9</td><td>0.948 2</td><td>0.311 8</td><td>0.970 7</td><td>8.444 5</td><td>5</td></tr><tr><td>归一化</td><td>7</td><td>0.577 6</td><td>0.903 2</td><td>0.601 2</td><td>0.895 3</td><td>0.449 2</td><td>0.950 5</td><td>6.832 8</td><td>2</td></tr><tr><td>移动平滑</td><td>6</td><td>1.095 5</td><td>0.6849</td><td>1.145 8</td><td>0.661 4</td><td>1.051 5</td><td>0.589 4</td><td>2.3751</td><td>3</td></tr><tr><td>多元散射校正</td><td>14</td><td>0.412 0</td><td>0.953 6</td><td>0.463 3</td><td>0.941 4</td><td>0.355 6</td><td>0.963 9</td><td>7.793 3</td><td>5</td></tr><tr><td>变量标准化</td><td>14</td><td>0.422 1</td><td>0.951 3</td><td>0.448 7</td><td>0.945 0</td><td>0.3709</td><td>0.960 8</td><td>7.206 0</td><td>4</td></tr><tr><td>一阶导数</td><td>18</td><td>0.424 9</td><td>0.950 3</td><td>0.454 4</td><td>0.943 2</td><td>0.324 2</td><td>0.970 1</td><td>8.5631</td><td>4</td></tr><tr><td>二阶导数</td><td>12</td><td>0.472 1</td><td>0.9371</td><td>0.494 6</td><td>0.9307</td><td>0.4468</td><td>0.947 7</td><td>6.3093</td><td>4</td></tr></table></body></html>

比较表4和表5发现在光谱预处理前提下进行SPA特征波长选择后建立的PLSR模型的预测精度要低于直接使用PLSR模型，但是基于原始光谱的SPA-PLSR模型的预测精度高于PLSR模型。分析原因经过SPA选择后，通过选择特征波长来代表全波段进行建模本身就会丢失一些有效信息，在通过PLSR建模筛选主成分后，有效信息又会丢失一些，导致模型的预测精度降低。比较表3和表5发现在光谱预处理前提下建立的SPA-MLR模型精度高于PLSR，但基于原始光谱建立的模型预测精度却是一样的。分析原因MLR不会筛选主成分，有效信息相对PLSR丢失较少，因此精度相对较高。因为原始光谱存在噪声导致经过SPA筛选特征波长后与PLSR出现筛选一致的情况，2种模型预测精度一致，从而也说明，光谱在没有经过预处理进行建模时，因为受到噪声的影响，建模算法失效，预测结果没有了可比性。

综上，基于归一化处理后使用多元逐步回归(SMLR)和基于连续投影算法的多元线性回归模型(SPA-MLR)的预测精度相对较好，并且筛选的特征波长也较少，如图2所示。

# 3讨论

不同算法的预测结果比较如表6所示，不同变换形式对土壤光谱信息有一定影响，进而影响估测模型的精度。

本文基于不同光谱预处理，采用SPA选择回归变量建立的MLR模型的预测精度要优于SMR，其原因可能是SPA在选择特征波长的能力上要比SMR强，且SPA选择的特征波长要多于SMR,多个相关波长能够较好的反应土壤有机质的光谱信息，从而可以较好估算土壤有机质含量，但是SPA选择的回归变量较多，计算比较耗时，SMR建模仅有少量波长的光谱能进入模型，而且这些波长之间仍然存在一定的共线性，模型对于原始光谱信息利用较少。

直接使用PLSR方法建模的预测精度要优于SPA-PLSR模型。直接使用PLSR，可入选的主成分个数要多于SPA-PLSR,包含了更多的有效信息，分析原因是PLSR的基本作法是首先在自变量集中提出第一成分，然后建立因变量与第一成分的回归方程，如果回归方程已达到满意的精度，则算法中止。否则继续第二对成分的提取，直到能达到满意的精度为止。经过SPA选择特征波长后，入选的建模的变量有限，且在此基础上在进行PLSR回归，经过

![](images/378bd2a112b7092aa218043d925dbbc9381b41d736ab18f5c5d77644d2db89ec.jpg)  
图2基于归一化预处理的土壤盐分预测模型  
Fig.2The prediction model of soil salt content based on VN

表6不同建模算法预测精度比较  
Tab.6Comparison of the prediction based on the different model   

<html><body><table><tr><td rowspan="2">数据变换</td><td colspan="2">SMLR预测</td><td colspan="2">SPA-MLR预测</td><td colspan="2">PLSR预测</td><td colspan="2">SPA-PLSR 预测</td></tr><tr><td>RMSEP</td><td>Rual²</td><td>RMSEP</td><td>Ral²</td><td>RMSEP</td><td>Ral²</td><td>RMSEP</td><td>Rval²</td></tr><tr><td>原始光谱</td><td>0.388 6</td><td>0.953 2</td><td>0.311 8</td><td>0.970 7</td><td>0.556 9</td><td>0.916 0</td><td>0.311 8</td><td>0.970 7</td></tr><tr><td>归一化</td><td>0.287 6</td><td>0.979 2</td><td>0.278 3</td><td>0.980 5</td><td>0.322 8</td><td>0.973 7</td><td>0.449 2</td><td>0.950 5</td></tr><tr><td>移动平滑</td><td>0.3620</td><td>0.956 2</td><td>0.361 6</td><td>0.9568</td><td>0.365 7</td><td>0.954 3</td><td>1.051 5</td><td>0.589 4</td></tr><tr><td>多元散射校正</td><td>0.331 2</td><td>0.969 0</td><td>0.2863</td><td>0.977 0</td><td>0.3447</td><td>0.9667</td><td>0.355 6</td><td>0.963 9</td></tr><tr><td>变量标准化</td><td>0.3314</td><td>0.969 4</td><td>0.3049</td><td>0.974 1</td><td>0.3435</td><td>0.967 0</td><td>0.370 9</td><td>0. 960 8</td></tr><tr><td>卷积平滑</td><td>0.388 8</td><td>0.951 5</td><td>0.307 9</td><td>0.9689</td><td>0.615 7</td><td>0.884 5</td><td>/</td><td>/</td></tr><tr><td>一阶导数</td><td>0.425 6</td><td>0.948 9</td><td>0.2675</td><td>0.980 5</td><td>0.3378</td><td>0.969 3</td><td>0.324 2</td><td>0.970 1</td></tr><tr><td>二阶导数</td><td>0.435 6</td><td>0.949 4</td><td>0.341 6</td><td>0.969 6</td><td>0.4004</td><td>0.958 7</td><td>0.446 8</td><td>0.947 7</td></tr></table></body></html>

0.05的水平检验后，丢失了部分有效信息，入选的主成分个数也随之减少，导致模型的预测精度略低。

就PLSR与SMLR预测结果比较而言，除了导数预处理的情况，SMLR建模精度要优于PLSR模型，这可能是由于逐步回归建模仅有少量波段的光谱吸收率能进入模型，而且逐步回归也可以减少变量间共线性问题，模型对于所选取的特征波长信息利用较多，逐步回归所选择的变量更能代表所有的波段。当然PLSR也能够处理自变量较多的情况且能降低变量之间的共线性，但在本文的实验结果中不及SMLR建模效果好。因此，SMLR相对于PLSR可以更好地构建光谱与土壤盐分含量之间的关系模型。

# 4结论

利用高光谱成像技术获取南疆典型沙壤土光谱信息，并同步测定土壤电导率，通过SMR和SPA算法提取特征波段，结合MLR和PLSR建立回归模型，实现了对土壤电导率的快速检测。在文中所列的7种预处理方法中，较优的预处理方法是归一化,多元散射，变量标准化和一阶导数;预测模型SPA-MLR建模的预测精度要优于SMLR,直接使用PLSR建模的预测精度要优于SPA-PLSR，SMLR和SPA-MLR模型的预测效果相对PLSR和 SPA-PLSR较理想，表明相对于PLSR方法而言，MLR更适合建立典型沙壤土电导率预测模型。

本文通过地面实测土壤光谱和电导率数据，综合分析对比了不同方法在新疆南疆阿拉尔地区沙壤土盐分检测时的精度和效率，建立的SPA-MLR预测模型的 ${ R _ { v a l } } ^ { 2 } \ = 0$ .9805, $R P D = 1 1$ .50， $\ R M S E P =$ （200.2783，为快速、准确地检测南疆枣园土壤电导率提供了一定的理论参考依据。此外，新疆南部地区土壤盐渍化严重，本研究在地面尺度准确获取的典型沙壤土的盐分敏感波长和监测模型，为后续使用卫星和无人机遥感进行大范围的有效监测提供了理论依据和实用模型，为构建多尺度、多类型土壤的盐渍化遥感监测提供基础数据和技术支持。但是不同类型土壤的含水量、质地、结构以及有机质含量等理化指标不同，光谱特征和建模方法也可能存在一定的差异，针对不同类型土壤的光谱预处理方法、特征波长选择方法和建模方法可在未来工作中加强对比研究。

# 参考文献(References）

[1]PANG G,TAO W,JIE L,et al. Quantitative model based on fieldderived spectral characteristics to estimate soil salinity in Minqin County,China[J].Soil Science Society of America Journal,2014,   
78(2) :546-555. [2] ZHAO Z,TASHPOLATT,ZHANGF,et al. Spectral characteristics of soil salt content in typical oasis of Tarim River's middle reaches [J].Journal of Natural Disasters,2012,21(5):72-78. [3] 吴明珠，李小梅，沙晋明.亚热带红壤全氮的高光谱响应和反 演特征研究[J].光谱学与光谱分析，2013,33（11)：3111-   
3115.[WU Mingzhu,LI Xiaomei,SHA Jinming.Spectral inversion models for prediction of red soil total nitrogen content in subtropical region（Fuzhou）[J].Spectroscopy& Spectral Analysis,2013,   
33(11):3111 -3115.] [4] NAGY A,PETERRICZU,GALYAB,etal.Spectral estimation of soil water content in visible and near infra-red range[J].2014,3 (3):163 -171. [5] ZHANGP,LI Y.Study on the comparisons of the establishment of two mathematical modeling methods for soil organic matter content based on spectral reflectance[J].Spectroscopy & Spectral Analysis,2016,36(3):903-910. [6]张晓光，黄标,季峻峰,等.基于可见近红外高光谱的东北盐渍 土盐分定量模型研究[J].光谱学与光谱分析，2012,32（8）：   
2075-2O79.［ZHANG Xiaoguang,HUANG Biao,JI Junfeng,et al. Quantitative prediction of soil salinity content with visible-near

infrared hyper-spectra in northeast China［J].Spectroscopy & Spectral Analysis,2012,32(8）:2075-2079.]   
[7］杨爱霞,丁建丽,李艳红,等.基于表观电导率与实测光谱的干 旱区湿地土壤盐分监测[J].中国沙漠,2016,36（5）：1365- 1373.[YANG Aixia,DING Jianli,LI Yanhong,et al.Apparent electronic conductivity and measured spectral for monitoring soil salt content in Arid Lakeside Wetland[J]. Journal of Desert Research, 2016,36(5) :1365 -1373.]   
[8]GOLDSHLEGER N,CHUDNOVSKY A,BEN-BINYAMIN R. Predicting salinity in tomato using soil reflectance spectra[J]. International Journal of Remote Sensing,2013,34（17）:6079 -6093.   
[9]NETO O R,TEIXEIRA A,LEAO R,et al.Hyperspectral remote sensing for detecting soil salinization using ProSpecTIR-VS aerial imagery and sensor simulation[J].Remote Sensing,2017,9(1）:1 -16.   
[10］彭杰,王家强,向红英,等.土壤含盐量与电导率的高光谱反演 精度对比研究[J].光谱学与光谱分析,2014,34（2）：510- 514.[PENG Jie,WANG Jiaqiang,XIANG Hongying,et al.Comparative study on hyperspectral inversion accuracy of soil salt content and electrical conductivity[J]. Spectroscopy and Spectral Analysis,2014,34(2） :510-514.]   
[11］屈永华,段小亮,高鸿永,等.内蒙古河套灌区土壤盐分光谱定 量分析研究[J].光谱学与光谱分析,2009,29（5）：1362- 1366.[QU Yonghua,DUAN Xiaoliang,GAO Hongyong,et al. Quantitative retrieval of soil salinity using hyperspectral data in the region of Inner Mongolia hetao irrigation district[J]. Spectroscopy & Spectral Analysis,2009,29(5):1362-1366.]   
[12］丁建丽,伍漫春,刘海霞,等.基于综合高光谱指数的区域土壤 盐渍化监测研究[J].光谱学与光谱分析,2012,32（7）：1918- 1922.[DING Jianli,WU Manchun,LIU Haixia,et al. Study on the soil salinization monitoring based on synthetical hyperspectral index [J].Spectroscopy & Spectral Analysis,2012,32（7）:1918- 1922.]   
[13］段鹏程,熊黑钢,李荣荣,等.不同干扰程度的盐渍土与其光谱 反射特征定量分析[J].光谱学与光谱分析,2017,37（2）：571 -576.[DUAN Pengcheng,XIONG Heigang,LI Rongrong,et al. A auantitative analysis of the reflectance of the saline soil under different disturbance extent[J].Spectroscopy & Spectral Analysis, 2017,37(2) :571 -576.]   
[14］李亚莉,乔江飞,董天宇,等.不同质地盐渍化土壤水盐含量的 高光谱反演[J].应用生态学报,2016,27（12）：3807－3815. [LI Yali,QIAO Jiangfei,DONG Tianyu,et al.Hyperspectral inversion of soil water and salt content in soils with diferent textures [J]. Chinese Journal of Applied Ecology,2016,27（12）:3807 - 3815.]   
[15］刘娅,潘贤章,王昌昆,等.基于可见－近红外光谱的滨海盐土 土壤盐分预测方法［J].土壤学报,2012,49（4）：824－829. [LIU Ya,PAN Xianzhang,WANG Changkun,et al.Prediction of coastal saline soil salinity based onvis-nr reflectance spectroscopy [J].Acta Pedologica Sinica,2012,49(4）:824 -829.] [16]ZHAN XY,ZHAO N,LIN Z Z,et al.Effect of algorithms for calibration set selection on quantitatively determining asiaticoside content in centella total glucosides by near infrared spectroscopy[J]. Spectroscopy & Spectral Analysis,2014,34（12）:3267-3272. [17］尼珍,胡昌勤,冯芳.近红外光谱分析中光谱预处理方法的作 用及其发展[J].药物分析杂志,2008,28（5）:824－829.[NI Zhen,HU Changqin,FENG Fang.Progress and effect of spectral data pretreatment in NIR analytical technique[J].Chinese Journal of Pharmaceutical Analysis,2008,28（5） :824-829.] [18］夏俊芳,李培武,李小昱,等.不同预处理对近红外光谱检测脐 橙VC 含量的影响[J].农业机械学报,2007,38（6)：107-   
111.[XIA Junfang,LI Peiwu,LI Xiaoyu,et al.Effect of different pretreatment method of nondestructive measure vitamin C content of umbilical orange with near-infrared spectroscopy[J].Transactions of the Chinese Society for Agricultural Machinery,2007,38 (6):107 -111.] [19］刘娅,潘贤章,王昌昆,等.土壤湿润条件下基于光谱对称度的 盐渍土盐分含量预测[J].光谱学与光谱分析,2013,33（10）：   
2771-2776.[LIU Ya,PAN Xianzhang,WANG Changkun,et al. Predicting soil salinity based on spectral symmetry under wet soil condition[J]. Spectroscopy & Spectral Analysis,2013,33（10）：   
2771 -2776.] [20］陈文倩,丁建丽,谭娇,等.干旱区绿洲植被高光谱与浅层土壤 含水量拟合研究[J/OL].农业机械学报,2017,（9):1-16 [CHEN Wenqian,DING Jianli,TAN Jiao,et al. Analysis vegetation of hyperspectral reflectance and shallow soil water content in arid area[J].Transactions of the Chinese Society for Agricultural Machinery,2017,（9):1-16.] [21］侯艳军,塔西甫拉提·特依拜,买买提·沙吾提,等.荒漠土壤 有机质含量高光谱估算模型［J].农业工程学报,2014,30 （16）：113－120.［HOUYanjun，TIYIP Tashpolat，SAWUT Mamat,et al.Estimation model of desert soil organic matter content using hyperspectral data[J].Transactions of the Chinese Society of Agricultural Engineering,2014,30（16）:113-120.] [22］彭翔,胡丹,曾文治,等.基于 EPO-PLS 回归模型的盐渍化土 壤含水率高光谱反演[J].农业工程学报,2016,32（11)：167-   
173.[PENG Xiang,HU Dan,ZENG Wenzhi,et al. Estimating soil moisture from hyperspectra in saline soil based on EPO-PLS regression[J].Transactions of the Chinese Society of Agricultural Engineering,2016,32（11） :167 -173.] [23] ZENG W Z,HUANG J S,XU C,et al. Hyperspectral reflectance models for soil salt content by filtering methods and waveband selection[J].Ecological Chemistry & Engineering S,2016,23（1）:   
117 -130. [24]FARIFTEHJ,MEERFVD,ATZBERGER C,et al. Quantitative analysis of salt-afected soil reflectance spectra:A comparison of two adaptive methods（PLSR and ANN）[J].Remote Sensing of Environment,2007,110(1） :59 -78.

# A comparison of the salt content in sandy soil between the MLR model and PLSR model

WANG Tao'²，YU Cai-li1²， YAO $\mathrm { N a } ^ { 1 , 2 }$ ，WANG Fei1²2，BAI Tie-cheng1,3\* (1College of Information Engineering,Tarim University,Aral 8433oo,Xinjiang,China; 2South Xinjiang Agricultural Informatization Reaserch Center,Xinjiang Aral 8433oo,Xinjiang,China; 3Gembloux Agro-Bio Tech,University ofLiege,Gembloux 2503O,Belgium）

Abstract：Inorder to monitortypical soilsaltcontent（sandy loam soil）in South Xinjiang,Chinaquicklyand effectively,and to improvethe precisionof thesoilsaltcontentestimation modelby removing the noiseof soil hyperspectral absorbance,this paper focusedon the inversion relationship between soil spectrumand electrical conductivity（EC）by using multiple spectral pretreatment methods,and then the multiple linear regression （MLR）and he partial least squares regression （PLSR）modelling were applied to establish the salt content modelbased on the hyperspectral analysis technique.The effective and predictive capacities of diferent models were validated.This study took the typical arid area in South Xinjiang asthe research object,obtained the hyperspectral data and EC by using Near-infrared spectrometer（Zolix Gaia Sorter）and conductivity meter（DDS-307）,142 soil samples at $0 \sim 2 0$ cm depth were collected and these samples were highly representative for the EC.Seven pretreatment methods were used to pretreat the original spectral data,such asvector normalization（VN）,multiplicative scater correction （MSC）,standard normal variate（SNV）,moving-average（MA）smoothing,Savitzky-Golay（SG）smothing,first derivative（1-Der）and second derivative（2-Der）,then the characteristic wavelengths were extracted with stepwise multiple regression （SMR）and successive projection algorithm （SPA）,which were used as input variables of MLR and PLSR modeling.The results showed that the optimum pretreatment methods were VN,MSC,SNV and 1- Der.According to different pretreatments,in the stepwise multiple linear regression（SMLR）prediction model ${ R _ { v a l } } ^ { 2 }$ （20 was greater than O.95,RPD was greater than 6.2,and RMSEP was less thanO.44.In the multiple linear regression model based on the successve projections algorithm （SPA-MLR) ${ R _ { v a l } } ^ { 2 }$ was greater than $0 . 9 6 { , } R P D$ was greater than 6.9,and RMSEP was lessthan O.36,which were beter than those in SMLR.In the partial least squares regression prediction model ${ R _ { v a l } } ^ { 2 }$ was greater than $0 . 8 8 , R P D$ was greater than 4.4,RMSEP was less than O.62 and in the partial least squares regression model based on the successive projections algorithm （SPA-PLSR) ${ R _ { v a l } } ^ { 2 }$ was greater than $0 . 5 9 , R P D$ was greater than 2.4,and RMSEP was less than 1.1 which were less than those in SMLR and SPAMLR.The best prediction of SMLR and SPA-MLR after vector normalization（VN）was as the follows : $R M S E P = 0$ ： $2 8 7 \ 6 \ , { R _ { v a l } } ^ { 2 } = 0 . 9 7 9 \ 2 , R P D = 9 . 9 0 7 \ 8$ and $R M S E P = 0 . 2 7 8 \ 3 , R _ { v a l } ^ { \mathrm { \prime } } = 0 . 9 8 0 \ 5 , R P D = 1 1 . 5 0$ which had fewer characteristic wavelengths.Sothe VN isabest effctive pretreatment method.It is more suitable to establish the prediction model of soil conductivity in jujube tree by MLR with PLSR.Itcouldbean important part in future researches how to choose the right algorithm to analyze the soil salt content with the spectral data.

Key words:soil electrical conductivity；multiple linear regression；Partial least squares regression; Hyperspectral