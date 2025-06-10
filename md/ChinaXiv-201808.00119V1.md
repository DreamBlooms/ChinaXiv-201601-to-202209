# 基于组合模型的交通事故严重程度预测方法

石雪怀ä，戚湧a，张伟斌ʰ，李千目a(南京理工大学 a.计算机科学与工程学院;b．电子工程与光电技术学院，南京 210094)

摘要：由于各个单一分类模型对道路交通事故严重程度预测的局限性，为提升模型预测性能，致力于建立一种组合模型。结合卷积神经网络提取时空维度中的特征信息，采用 stacking方式将CNN与XGBoost 组合，最终生成道路交通事故严重性的分类模型（多层提升算法)。实验结果表明，此模型在测试集上预测精度为 $91 . 5 1 \%$ ，组合模型比单一分类模型具有更好的分类结果。基于组合模型的分类结果，对交通事故特征进行重要性排序，开展特征相关性分析，为减少道路交通事故及减轻道路交通事故严重等级的管理措施提供参考依据。

关键词：交通安全；交通事故严重程度；XGBoOSt；卷积神经网络；诱因分析中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.03.0273

# Traffic accident prediction approach based on ensemble approach

Shi Xuehuaia, Qi Yongat, Zhang Weibinb, Li Qianmua (a.Schoolof ComputerScience&Engineering,b.SholofElectronicEngineering&Photoelectric Technology,Nanjing University of Science & Technology,Nanjing 210094, China)

Abstract: Astheliitatiosofthesingleclassifierontaficaccidentsverityanensembleapproach isproposedforimproving the prediction performance.Using CNNs toextract the features from the spatial dimension,geting an ensemble approach with XGBoost and CNN by stacking (multi-level boosting algorithm).The predicting precision of the approach is $91 . 5 1 \%$ on the validationset.Incomparison withthe singleclasification model,theresultofthe experiment showsabeterperformance.For providing useful informationforreducing the numberof traffc acidents anddowngrading the severityoftrafficaccident,the paper gives out a correlation analysis by sorting the features based on the predictions.

Iey words: traffic safety; traffic accident severity; XGBoost; cnns; inducement analysis

# 0 引言

当今世界，道路交通事故已对社会造成严重的危害，成为现代化交通运输中亟需解决的一个重要问题。在我国，道路交通事故每年都会造成巨大的人员伤亡和经济损失，2016年共发生各类道路交通伤亡事故超过15万，死伤超过10万余人[1],直接经济损失50亿余元。因此，对道路交通事故严重程度进行科学预测，并结合预测结果进行诱因分析，掌握严重程度较高的道路交通事故的发生、发展、分布规律与特征，依此规律和特征为最大程度规避严重交通事故发生的风险提出行之有效的交通安全对策，成为当前亟需解决的问题。

道路交通事故严重程度预测是以道路交通微观环境活动作为考察对象，研究各个有关变量分布及其变动对于事故严重程度的影响，从而提出行之有效的解决方案，以减轻道路事故严重性和减少道路交通事故。近年来，国内外学者已经对道路交通事故严重性预测问题进行了大量研究[2\~I2]，国内道路交通事故严重程度预测研究如马壮林等采用有序Logit模型和广义Logit 模型，建立公路隧道交通事故严重程度预测模型[2]；刘海珠等从宏观层面筛选道路交通事故的主要影响因素，将事故严重程度划分为三个等级，建立基于累积Logistic回归模型的道路交通事故严重程度预测模型[6。国外道路交通事故严重程度预测研究如文献[8],通过选取事故严重程度相关数据特征(肇事车行驶速度、肇事车类型、安全气囊状态等）建立事故严重程度智能分类系统来为紧急服务机构提供指导意见；Sameen等人[9]则采用递归神经网络建立深度学习模型对事故严重性进行分类等。由于事故数据为序列化数据，在时空上具有一定关联性，O'Donnell等人[13]采用有序Logit 模型和有序probit模型，分析事故严重程度与驾驶人属性和车辆特征之间的关系；Sameen等人[9则通过建立递归神经网络来捕获数据之间的时空关联，通过添加多个长短时记忆模型最终通过两个全连接层和softmax多分类层实现道路交通事故严重性分类。

在目前交通事故严重程度预测模型中，更多根据事故结果信息预测事故严重程度，没有获取足够路段信息，如马壮林等人采用有序Logit 模型和广义Logit模型建立公路隧道交通事故严重程度预测模型[2]；在Fogue 等人[8]建立的事故严重程度智能分类系统，其目的在于紧急服务机构提供指导意见，没有通过相关数据特征分析事故发生主要原因；Sameen等人[9采用递归神经网络建立深度学习模型对事故严重性进行分类，通过照明情况、路表情况等道路信息特征以及事故发生时间等环境特征对事故严重性分类，但此模型并没有获取邻近路段信息特征且在验证集上预测精度为 $71 . 7 7 \%$ 。因此，提升道路交通事故严重程度预测精度并依此对事故发生原因进行诱因分析成为道路交通事故严重程度研究的主要内容。基于上述文献分析，本文通过路号获取事故地点邻近道路信息，结合卷积神经网络提取道路在空间维度中的信息，采用stacking方式将CNN 与XGBoost组合，最终生成道路交通事故严重性的分类模型（多层提升算法)，并依据分类模型的预测结果进行诱因分析，为减少道路交通事故及减轻道路交通事故严重等级的管理措施提供参考依据。

# 1 卷积神经网络与XGBoost简介

# 1.1 卷积神经网络

卷积神经网络(convolutional neural network,CNN）最早由

Fukishima 等人在1980 年提出[15],LeCun 在1998 年对 BP 算法优化进一步提升 CNN 性能[16],2012 年 CNN 在 ImageNetLSVRC-2012contest[18]中取得了极高的准确度最终将CNN 研究推向高潮。

CNN 结构如图1所示。由图1可知，CNN主要包含：卷积层（convolutional layer）、线性整流层（rectified linear units layer,ReLUlayer）、池化（pooling）层、全连接层、损失函数层。CNN相比于传统神经网络具有以下优点：a)能够获取非结构性数据的区域关联信息；b)CNN实现了特征提取的封装，简化训练过程；c)同时学习和产生信息提取和分类；d)权重共享可以减少网络的训练参数，使神经网络结构变得更简单，适应性更强[16]。CNN 也有一些缺点：a)CNN 的特性使其难以泛化；b)由于卷积层和池化层的计算量庞大，使CNN的研究依赖于硬件性能的支持[17]。卷积神经网络目前广泛应用于影像识别、视讯分析、自然语言处理、药物发现和围棋等多个领域。

# 1.2 XGBoost

XGBo0st 由 Chen 等人[22]于 2016 年提出，它基于GBDT（又名MART，multiple additive regression tree)，是一种迭代的决策树算法，该算法由多棵决策树组成，所有树的结论累加起来做最终答案[24])，对GBDT 进行优化，提供缓存感知预读取技术、分布式外存计算技术、AIIReduce 容错工具提高现有提升树增强算法运算速率，解决当前提升树增强算法局限于百万级别数据量的问题，提升算法运行速率。XGBoost的结构如图2所示，具体介绍详见文献[22，23]。

![](images/f7ce5d5ed241716b7ba295e2f629383dc7f07e9906357d0076dda4ff6f935be2.jpg)  
图1卷积神经网络结构图

![](images/327aa3b16b6d7924824761a2c3c5f357cbf9975ea239ea99dfcf70da3301ba0c.jpg)  
图2XGBoost模型结构和评分方法

# 2 模型建立

# 2.1强关联规则特征选择方法

根据GA1082一般事故采集标准，深圳市事故数据集对每起事故采集了69 条特征，本文依照交通安全工程[14]对特征分类，详情如表1所示。

表12014-2016年深圳事故数据特征分类  

<html><body><table><tr><td>大类</td><td>小类</td><td>特征</td></tr><tr><td rowspan="5">道路特征</td><td>公路</td><td>公路行政等级,公里数，单向路宽，双向路宽，路面结构，路面附着系数,道路</td></tr><tr><td>城市道路</td><td>类型,道路线型,长下坡路段,在道路·横断面位置 路口路段类型</td></tr><tr><td>交通管理设施</td><td>交通信号方式（控制），交通标志标线完善</td></tr><tr><td></td><td>安全防护设施中央隔离设施，其他交通安全设施不全，路侧防护设施类型,道路物理隔离</td></tr><tr><td>天气条件</td><td>天气，能见度</td></tr><tr><td rowspan="5">环境特征</td><td>道路环境</td><td>事故多发点段，地形，照明条件,路表情况，路面状况，道路安全属性，道路安</td></tr><tr><td></td><td>全隐患督办等级</td></tr><tr><td>事故基本信息</td><td>所属中队，文书状态，所辖乡镇,现场，行人数量，行政区划，调解人，米数</td></tr><tr><td>事故时空信息</td><td>事故发生时间,事故地点，路号，路名</td></tr><tr><td>事故原因信息</td><td>事故认定原因,事故认定原因分类小类</td></tr><tr><td rowspan="2">事故特征</td><td>事故类型信息</td><td>事故形态,事故严重程度,单车事故,是否简易程序,路外事故类型,车辆间 事故,逃逸事故侦破</td></tr><tr><td>事故伤亡信息</td><td>受伤人数，当事人总数，抢救死亡人数，机动车数量，死亡人数，直接财产</td></tr></table></body></html>

由表1可知，本文采用{道路特征，环境特征，事故严重程度}为数据集，以事故严重程度为预测目标，使用道路特征和环境特征预测事故严重程度，寻求道路特征与环境特征对于事故严重程度的影响。

本文使用一种强关联规则特征选择算法，通过关联规则进行特征选择，优先选取后件为标签的短规则，达到减小特征空间维度的目的，算法伪代码见算法1。

基于强关联规则特征选择算法结果，获取预测路段及邻近三条道路特征集合，并结合本路段其他特征集合预测道路交通事故严重程度，特征选择算法结果详见表2。

算法1强关联规则特征选择算法

1:Input: data set $x$ ,feature set $\boldsymbol { \mathsf { F } }$ ,association rule set $\boldsymbol { \mathsf { Y } }$ ,true   
rule set $\phi$ ，target label ${ \bf y } ,$ iteration number $\tau$ ，support   
threshold $\lambda$ ,confidence threshold $v$ ,final feature set M   
2:Initialize $\mathsf { Y } \gets \mathrm { A p r i o r i } ( \mathrm { X } , \mathbb { F } ) , \mathsf { t } \gets 0 , \mathsf { M } \gets \{ \}$   
3：for pin?Y then   
4: If yn?p andTift $\left( \mathrm { y } , \rho \right) > 1$ then   
5: Add $\rho$ to $\phi$ （20   
6: end if   
7: end for   
8： （204 ${ \phi }  \mathrm { s o r t } ( { \phi } )$   
9:while $\mathbf { t } < \mathbf { T }$ do   
10: Get $\varrho _ { \mathrm { f i r s t } }$ from $\phi$   
11: If $V _ { _ { \varrho _ { \mathrm { f i r s t } } } } > V a n d \lambda _ { _ { \varrho _ { \mathrm { f i r s t } } } } > \lambda$ then   
12: $M _ { \varrho _ { \mathrm { f i r s t } } }  \mathrm { g e t F e a t u r e s } ( \varrho _ { \mathrm { f i r s t } } )$   
13: Add Mefin toM without repetition   
14: end if   
15: $\mathbf { \boldsymbol { \mathfrak { t } } } \gets \mathbf { \boldsymbol { \mathfrak { t } } } + \mathbf { \boldsymbol { \mathsf { 1 } } }$   
16: end while   
17: Output: M

表2强关联特征选择的特征集合  

<html><body><table><tr><td colspan="2">小类 特征</td></tr><tr><td rowspan="3">特征</td><td>事故多发点段，交通标志标线完善,其他交通安全设施不全，</td></tr><tr><td>邻近三段道路路侧防护设施类型,路口路段类型,路面状况,路面结构,交通</td></tr><tr><td>信号方式（控制），道路安全属性,道路安全隐患督办等级，</td></tr><tr><td rowspan="6"></td><td>道路物理隔离,道路类型,道路线型,长下坡路段</td></tr><tr><td>路宽,中央隔离设施,是否双道,事故多发点段,交通信号方式</td></tr><tr><td>(控制),交通标志标线完善，其他交通安全设施不全,在道路横</td></tr><tr><td>本路段特征断面位置,地形,照明条件,路口路段类型,路表情况,路面状况，</td></tr><tr><td>路面结构,道路安全属性,道路安全隐患督办等级,道路物理</td></tr><tr><td>隔离,道路类型,道路线型,长下坡路段,路侧防护设施类型</td></tr><tr><td>环境特征</td><td>是否节假日，是否白天，天气,能见度</td></tr></table></body></html>

# 2.2事故严重程度预测方法

在深度学习中，特征通过不同层之间进行信息传递，本文受此启发，采用stacking的方式将CNNs与xgboost 组合：CNNs提取预测路段及邻近的三条路段道路特征的空间信息，将提取的空间信息结合其他特征，结合xgboost进行 stacking 组合，在此命名为多层提升算法，算法伪代码见算法2，算法流程图如图3所示。

多层提升算法每层包括一个CNNs 提取空间数据信息输出3-dim空间信息的增强特征，结合其他特征代入xgboost，预测事故严重程度，输入3-dim结果向量，并作为增强特征代入下一层的CNNs 和xgboost。最终，使用argmax 确定预测结果。多层提升算法的层数自动确定，受deepforest[26]启发，在增加下一层时使用k折交叉验证，若预测结果没有明显提升则停止拓展下一层。

算法2多层提升算法

1:Algorithm configurations:parameters in CNN，parameters   
in XGBoost   
2：Input:data set $x$ (include spatial features $X _ { s }$ ，other   
features $X _ { o }$ )， target label ${ \bf y } ,$ cross validation parameter $\textbf { k }$   
performance estimation $\lambda$   
3：Initialize performanceestimation $\mathcal { N }  { } 1$ ,level $\scriptstyle { l \gets 0 }$   
4:while $v > \lambda$ then   
5: If $\scriptstyle { l = = 0 }$ then   
6: $\hat { y } _ { c \_ l } \gets \mathrm { h \_ C N N s } ( X _ { s } )$   
7: fit CNNs( $X _ { s } , { \bf { y } } )$ （204   
8: $\hat { y } _ { _ { X G _ { - } l } } \gets \mathrm { h \_ X G B o o s t } \big ( X _ { o } , \hat { y } _ { c } \big )$   
9: fit XGBoost( X,yc_y)

10: V←kFold_estimation $( X , y , k )$

11: end if

12： $\iota \gets \iota + 1$

13： $\hat { y } _ { c \_ l } \gets \mathrm { h \_ C N N s } ( X _ { s } )$

14: fit CNNs( $X _ { s } , \hat { y } _ { x G \_ l } , { \bf y } )$

15: $\hat { y } _ { _ { X G _ { - } l } } \gets \mathrm { h \_ X G B o o s t } \big ( X _ { o } , \hat { y } _ { c } \big )$

16:fit XGBoost( $X _ { o } , \hat { y } _ { c \_ l } , { \bf y } )$

17: $v $ kFold_estimation(X,y,k)

18:end while

19: $\hat { y } = \pmb { \mathscr { a } } r g m a x \left( \hat { y } _ { _ { X G _ { - } l } } \right)$

20:Output:y

![](images/45ce90c8f3cb41e207a7f97134f9ca1cdf73d323963f4d89e398c3489d4b55d8.jpg)  
图3多层提升算法流程图

# 3 实验分析

# 3.1基于组合模型的预测结果

本文实验数据由道路交通安全研究信息共享平台的深圳市道路交通事故数据分析竞赛提供，数据内容包含深圳市2014至2016年20余万条交通事故信息，包括伤亡事故和轻微事故。本文通过数据提供的道路信息和环境信息，预测不同事故的严重程度，并采用5折交叉验证对预测结果进行评估。本文根据数据预处理结果使用对应分类模型对数据预测。

多层提升算法基于5折交叉验证结果对模型参数调整，确定层数为2层。最终，采用5折交叉验证对此模型预测精度进行评估，多层提升算法预测精度为 $91 . 5 1 \%$ 。

# 3.2 误差分析及比较

为了进一步验证多层提升算法的准确性，使用单一XGBoost模型、单一RF模型（randomforest）与多层提升算法分类预测结果进行对比，可以判断各模型的准确性，详情如表3所示。

Spatial Features   
表3不同模型预测精度比较  

<html><body><table><tr><td rowspan="2">评价指标</td><td colspan="3">模型</td></tr><tr><td>RF</td><td>XGBoost</td><td>多层提升算法</td></tr><tr><td>acc-on-trainSet</td><td>97.29%</td><td>97.42%</td><td>99.57%</td></tr><tr><td>acc-on-cv</td><td>74.32%</td><td>71.69%</td><td>91.51%</td></tr><tr><td>test-merror-mean</td><td>25.68%</td><td>28.31%</td><td>8.49%</td></tr><tr><td>test-merror-std</td><td>16.17%</td><td>2.12%</td><td>3.90%</td></tr><tr><td>train-merror-mean</td><td>2.71%</td><td>2.05%</td><td>0.36%</td></tr><tr><td>train-merror-std</td><td>None</td><td>0.28%</td><td>0.11%</td></tr></table></body></html>

表3中acc-on-trainSet表示模型在用于模型拟合的训练集中的准确率，acc-on-cv表示模型基于5折交叉验证对于测试集的预测准确率，test-merror-mean、test-merror-std、train-merror-mean和train-merror-std是以交叉验证为基础的评估指标，test-merror-mean表示在cv集合中多个测试集中多分类误差平均值，test-merror-std表示多个测试集中多分类误差的标准差，train-merror-mean表示多个训练集中多分类误差平均值，train-merror-std表示多个训练集中多分类误差的标准差。由表3可得：a)无论是RF、XGBoost或组合模型，模型总是在训练集上拟合效果最好，模型都偏于过拟合;b)组合模型相对于RF 或XGBoost单个模型，在训练集和交叉验证的测试集上表现都更好，且组合模型在交叉验证的测试集上的多分类误差的标准差为 $3 . 9 0 \%$ ，模型表现较为稳定且良好。

# 3.3诱因分析

根据基于组合模型的预测结果，根据道路交通专家意见，在组合模型特征重要性排序图的基础上，本文寻求道路信息特征集合和环境信息特征集合中对道路交通事故严重性预测结果产生重要影响的特征，并依此进行道路交通事故的诱因分析，模型重要性排序信息如图4所示。由图4可得，路宽、能见度、路侧防护设施类型、路口路段类型、道路物理隔离和交通信号方式（控制）都起到了比较重要的作用。

在图6和7中，对分类变量的不同分类进行了数值变换，其中“交通信号方式（控制）"中1-无控制，2-民警指挥，3-信号灯，4-标志，5-标线，6-其他，本实验由1-6组合为11种类别，其他特征对应数值的解释详情如表4所示。

由图6和7可得：

a)路宽。由图6中“路宽”与“事故类型”的双变量关系图可得，死亡事故和伤人事故更易出现于路宽较大的路段，相对伤人事故，死亡事故更集中于路宽较大的路段。由图7中“路宽”与“事故类型”的双变量关系图可得，两变量pearsonr相关系数为0.23，且假设pearson $\scriptstyle \mathrm { r = 0 }$ 的p值估计为0.0088，说明“路宽”与“事故类型”有一定的相关性。

b)交通信号方式(控制)。由图6中“交通信号方式(控制)"与“事故类型”的双变量关系图可得，事故更易出现于“交通信号方式（控制)”为8的情况下，即由标志和标线组成的交通控制方式。由图7中“交通信号方式（控制)”与“事故类型”的双变量关系图可得，相对于财产损失事故，此种控制情况下更易出现伤人事故和死亡事故，且“交通信号方式（控制)”与“事故类型"两变量pearsonr相关系数为0.32，假设pearsoni ${ \mathrm { : = } } 0$ 的p值估计为0.00022，说明“交通信号方式（控制)”与“事故类型”有一定的相关性。

表4不同特征数值解释表  

<html><body><table><tr><td>特征</td><td>数值</td><td>解释</td><td>特征</td><td>数值</td><td>解释</td></tr><tr><td colspan="2"></td><td>其他安全设施</td><td rowspan="6"></td><td>1</td><td>绿化带 混凝土护拦</td></tr><tr><td></td><td>2</td><td>356</td><td>2</td></tr><tr><td>3</td><td>56</td><td>路侧防护设 3</td><td>防护墩(柱)</td></tr><tr><td>4</td><td>34</td><td>施类型 4</td><td>行道树</td></tr><tr><td>5</td><td>16</td><td>5</td><td>金属护拦</td></tr><tr><td>交通信号方</td><td>3456</td><td>6</td><td>无防护</td></tr><tr><td>式 (控制)</td><td>6 7</td><td>456</td><td>1</td><td>中心隔离</td></tr><tr><td></td><td>8</td><td>45</td><td></td><td></td></tr><tr><td></td><td>9</td><td>345</td><td>2</td><td>机非隔离</td></tr><tr><td></td><td>10 11</td><td>无信号</td><td>道路物理隔 离</td><td></td></tr><tr><td rowspan="12">路口路段类</td><td></td><td>标线</td><td></td><td>3</td><td>中心隔离加机非隔离</td></tr><tr><td>1</td><td>三枝分叉□</td><td rowspan="6">能见度</td><td></td><td></td></tr><tr><td>2</td><td>四枝分叉□</td><td>4</td><td>无隔离</td></tr><tr><td>3</td><td>多枝分叉□</td><td></td><td></td></tr><tr><td>4</td><td>环行交叉</td><td>1</td><td>50m以内</td></tr><tr><td>5</td><td>普通路段</td><td>2</td><td>50～100m</td></tr><tr><td>6</td><td>变窄路段</td><td>3</td><td>100～200m</td></tr><tr><td>型</td><td>7</td><td>路侧险要路段</td><td>4</td><td>200m以上</td></tr><tr><td></td><td>8</td><td>匝道□</td><td>1</td><td>财产损失事故</td></tr><tr><td></td><td>9</td><td>路段进出处</td><td>事故类型(即</td><td></td></tr><tr><td></td><td>10</td><td>高架路段</td><td>事故严重程 2</td><td>伤人事故</td></tr><tr><td></td><td>11</td><td>桥梁</td><td></td><td></td></tr><tr><td></td><td>12</td><td>隧道</td><td>度 3</td><td>死亡事故</td></tr></table></body></html>

c)能见度。由图6中“能见度”与“事故类型”的双变量关系图可得，道路交通事故并非出现于能见度很低的情况下，如图可知，大多数道路交通事故出现于能见度为4的情况下，即能见度 $2 0 0 \mathrm { m }$ 以上，相对于财产损失事故，伤人事故和死亡事故更易出现于能见度为4的情况下。由图7中“能见度”与“事故类型”的双变量关系图可得，相对于财产损失事故，能见度 $2 0 0 \mathrm { m }$ 以上的情况下更易出现伤人事故和死亡事故，且“能见度”与“事故类型”两变量pearsonr相关系数为0.038，假设pearson ${ \mathfrak { = } } 0$ 的 $\mathfrak { p }$ 值估计为0.67，说明“能见度”与“事故类型”关联度不大。

d)路侧防护设施类型。由图6中“路侧防护设施类型”与

“事故类型"的双变量关系图可得，相对于其他路侧防护设施，1、2和6路侧防护设施类型下，即绿化带、混凝土护栏和无防护，道路交通事故发生概率更大，且相对于财产损失事故，路侧防护设施类型1和6更易导致伤人事故和死亡事故，即绿化带和无防护。由图7中“路侧防护设施类型”与“事故类型”的双变量关系图可得，“路侧防护设施类型”与“事故类型”两变量pearsonr相关系数为0.087，假设pearsoni $\scriptstyle \mathrm { r = 0 }$ 的p值估计为0.33，说明“路侧防护设施类型”与“事故类型”关联度不大。

e)道路物理隔离。由图6中“道路物理隔离”与“事故类型”的双变量关系图可得，相对于其他路侧防护设施，道路物理隔离类型1、4下，即中心隔离和无隔离下，道路交通事故发生概率更大。由图7中“道路物理隔离”与“事故类型”的双变量关系图可得，“路侧防护设施类型”与“事故类型”两变量pearsonr相关系数为0.17,假设pearson $\scriptstyle \mathrm { r = 0 }$ 的p值估计为0.053,说明“道路物理隔离”与“事故类型”有一定的关联性。

f)路口路段类型。由图6中“路口路段类型”与“事故类型”的双变量关系图可得，大部分道路交通事故都发生在路口路段类型2和5的情况下，即四枝分叉口和普通路段，且相对于财产损失事故和死亡事故，路口路段类型2下更易发生伤人事故。由图7中“路口路段类型”与“事故类型”的双变量关系图可得，“路口路段类型”与“事故类型”两变量pearsonr相关系数为-0.3，假设pearsoni ${ \boldsymbol { \mathbf { \mathit { \sigma } } } } = 0$ 的p值估计为0.00051，说明"路□路段类型”与“事故类型”的关联性很强。

综上所述，相对于财产损失事故，在道路较宽的路段易出现严重程度更高的事故；在由标志和标线组成的交通控制方式更易出现伤人事故和死亡事故；且不同于“恶劣天气更易发生严重道路交通事故”，数据显示能见度为4的情况下，即能见度$2 0 0 \mathrm { m }$ 以上；相对于财产损失事故，伤人事故和死亡事故出现次数更多，相对于其他路侧防护设施，绿化带、混凝土护栏和无防护，道路交通事故发生概率更大，且相对于财产损失事故，路侧防护设施类型为绿化带和无防护的情况下，伤人事故和死亡事故发生次数更多；相对于机非隔离和中心隔离加机非隔离，道路物理隔离类型为中心隔离或无隔离的情况下，道路交通事故发生概率更大；且在四枝分叉口路段更易发生伤人事故。因此我们应根据上述数据描述结果采取合理手段减轻道路交通事故严重程度以及尽量避免道理交通事故。

Feature Importance on Multi-level Boosting Algorithm 40   
35  25 20   
teeeeee 15 10 5 0 器 1 ￥亚

![](images/03af184baa89c91ce53c0ed833d2621bc1087d22e9da08403a176ea053c082ac.jpg)  
图4模型特征重要性排序   
图5本文的多层提升算法架构

![](images/908d07c1f867c7b61801b2d1f3072a8c87e185fec3ee172ece61d2f0068c3a3e.jpg)  
图6不同特征与"事故类型"关系图(小提琴图)

![](images/0c6b8101f2d99f4410fcfa92cc20e0daca8d60f21c388f3e85c5428b84a41d53.jpg)  
图7不同特征与"事故类型"关系图(KDE图)

# 4 结束语

本文根据2014-2016年深圳道路事故数据的实际情况，提出了基于组合模型的交通事故严重程度预测方法，结合卷积神经网络提取时空维度中的特征信息，采用stacking方式将CNN与XGBoost组合，最终生成道路交通事故严重性的分类模型(多层提升算法)。实验结果表明，组合模型比任何单一分类模型具有更好的分类结果，是一种有效的道路交通事故严重程度预测方法。基于组合模型优秀的分类结果，对特征进行重要性排序，进行特征相关性分析，最终为减少道路交通事故及减轻道路交通事故严重等级提供参考意见。根据道路交通安全研究信息共享平台的要求，本数据不得对外发布、传播，因此在此只公开本实验相关代码，详见https://github.com/SXHSine/TrafficAccidentAnalysis。

由于道路交通事故的发生具有时空关联性，在将来的研究中，通过获取事故的路段空间数据，可以根据空间位置更为准确地获取附近路段信息，提取更多邻近道路的空间信息，结合有关驾驶人的相关属性和操作行为数据，从而更准确地预测道路交通事故严重程度，并分析致灾原因，为避免事故的发生提供更多建设性意见。

# 参考文献：

[1]2016 年全国道路交通事故数据统计 [N/OL].[2017-12-14].http://www.peichang.cn/detail/id18666.html.(Statistics of National Road TrafficAccident Data in 2016 [N/OL].[2017-12-14]. http://www.peichang.cn/detail/id18666. html.)

[2]马壮林，张祎祎，杨杨，等.公路隧道交通事故严重程度预测模型研究 [J].中国安全科学学报,2015,25(5):75-79.(Ma Zhuanglin,Zhang Yiyi, Yang Yang,et al.Research on models for predicting severity of traffic accident in highway tunnel[J]. China Safety Science Journal, 2015,25 (5): 75-79.)

[3]孙重静，辛飞飞．人车冲突风险度评价指标计算研究综述[J].交通信 息与安全,2016,34 (2): 9-16.(Sun Chongjing,Xin Feifei.An overview of the conflict indicators between vehicles and pedestrians [J].Journal of Transport Information and Safety,2016,34 (2): 9-16.)

[4]马壮林，邵春福，董春娇，等.基于累积Logistic 模型的交通事故严重 程度时空分析[J]．中国安全科学学报，2011,21(9):94-99.(Ma Zhuanglin, Shao Chunfu,Dong Chunjiao,et al. Temporal-spatial analysis model of trafc accident severity based on cumulative logistic model [J]. China Safety Science Journal,2011,21(9): 94-99.)

[5]侯树展，孙小端，贺玉龙，等.高速公路交通事故严重程度与交通流特 征的关系研究[J].中国安全科学学报,2011,21(9):106-112.(Hou Shuzhan,Sun Xiaoduan,He Yulong,et al.Relationships between crash severity and trafic flow characteristics on freeways [J].China Safety Science Journal,2011,21 (9): 106-112.)

[6]刘海珠．道路交通事故严重程度影响因素分析及预测模型建立[D]. 长春：吉林大学,2O14.(Liu Haizhu.The analysis of influencing factors for crash severity and the establishment of predication model[J].Changchun: Jilin University,2014.)

[7]马柱，陈雨人，张兰芳．城市道路交通事故严重程度影响因素分析[J] 重庆交通大学学报：自然科学版,2014,33(1):111-114.(Ma Zhu,Chen Yu, Zhang Lanfang.Influence factors of accident severity for urban road [J]. Journal of Chongqing Jiaotong University:Natural Sciences,2014,33(1): 111-114. )

[8]Fogue M,Garrido P,Martinez FJ,et al.Using data mining and vehicular networks to estimate the severity of traffic accidents [M]//Management Intelligent Systems.Berlin: Springer,2012: 37-46.

[9]Sameen M I,Pradhan B.Severity Prediction of traffic accidents with

recurrent neural networks [J].Applied Sciences,2017,7(6).   
[10] Khera D,Singh W.A review on injury severity in trafc system using various data mining techniques [J].International Journal of Computer Applications,2014,100 (3): 17-22.   
[11] Gupta M, Solanki VK,Singh VK.A novel framework to use association rule mining for classification of traffic accident severity [J].Ingenieria Solidaria,2017,13 (21):37-44.   
[12] Baru A.Injury severity levels and associated factors among road traffic accident victims referred to emergency departments of selected public hospitals in Addis Ababa,Ethiopia: the study based on haddon matrix [J]. 2017.   
[13] O'Donnell C J,Connor D H. Predicting the severity of motor vehicle accident injuries using models of ordered multiple choice [J].Accident Analysis& Prevention,1996,28(6): 739-753.   
[14]肖贵平，朱晓宁．交通安全工程[M].北京：中国铁道出版社，2011. (Xiao Guiping,Zhu Xiaoning.Road safety engineering [M].Beijing: China Railway Publishing House,2011.)   
[15] Fukushima K,Miyake S. Neocognitron: a self-organizing neural network model for a mechanism of visual pattern recognition [M]//Competition and cooperation in Neural Nets.Berlin: Springer,1982:267-285.   
[16] LeCun Y,Bottou L,Bengio Y,et al.Gradient-based learning applied to document recognition [J]. Proceedings of the IEEE,1998,86 (11): 2278- 2324.   
[17] Convolutional Neural networks (LeNet): DeepLearning O.1 documentation. DeepLearning 0.1. LISA Lab.[2013-08-31].   
[18] Olshausen B A. Emergence of simple-cell receptive field properties by learning a sparse code for natural images [J].Nature,1996,381(6583): 607- 609.   
[19] LeCun Y,Botou L,Bengio Y,et al. Gradient-based learning applied to document recognition [J]. Proceedings of the IEEE,1998,86 (11): 2278- 2324.   
[20] Sabes PN,Jordan M I.Advances in neural information processing systems [C]//Advances in Neural Information Processing Systems.1995.   
[21] Krizhevsky A, Sutskever I, Hinton G E.ImageNet classification with deep convolutional neural networks [J]. Communications of the ACM,2017,60 (2): 2012.   
[22] Chen Tianqi, Guestrin C.XGBoost: a scalable tree boosting system [C]// Proc of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.New York:ACMPress,2016: 785-794.   
[23] Chen Tianqi,He Tong,Benesty M,et al.XGBoost:extreme gradient boosting[EB/OL].(2017）.https://cran.r-project.org/web/packages/ xgboost/vignettes/xgboost. pdf.   
[24] Friedman JH. Greedy function approximation: a gradient boosting machine [J].Annals of Statistics,2001,29 (5): 1189-1232.   
[25] Schapire R E,Singer Y. Improved boosting algorithms using confidencerated predictions [J].Machine Learning,1999,37(3):297-336.   
[26] Zhou Zhihua,Feng Ji.Deep forest: towards an alternative to deep neural networks[J].arXiv preprint arXiv: 1702.08835,2017.