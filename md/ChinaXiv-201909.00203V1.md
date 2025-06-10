# 基于脑结构像的精神分裂症机器学习分类研究

郑泓1，²；蒲城城’；王毅1，²；陈楚侨1，2  
（」中国科学院心理研究所心理健康重点实验室，神经心理学与认知神经科学研究室，北京，100101)（²中国科学院大学心理系，北京，100049）  
（北京大学第六医院，北京大学精神卫生研究所，国家卫生健康委员会精神卫生学重点  
实验室（北京大学），国家精神心理疾病临床医学研究中心（北京大学第六医院），北京，100191)

摘要将机器学习应用于精神疾患的临床和基础研究是近年来的趋势。研究者将机器学习应用于精神分裂症患者及高危人群的 T1 加权像和弥散张量成像的脑影像数据中，为了解疾病的生理病理学机制提供帮助。回顾以往研究发现额叶及颞叶的脑结构特征具有较高的区分能力，行为数据和脑影像数据结合的分类效果优于单模态数据。现阶段研究存在样本量不足和泛化能力欠缺的局限，未来研究应注意扩大样本量、制定标准化的分类方法，从而进一步探究机器学习在精神疾患中的作用。

关键词脑结构像；弥散张量成像；机器学习；精神分裂症；高危人群

分类号 XXXX

# 引言

精神分裂症是一种严重的精神障碍，患病率约为 $1 \%$ ，患者表现出思维方式和行为举止怪异、感知觉扭曲、认知失调等症状并且常伴有情感迟钝、社会退缩等特征(Carpenter＆Buchanan,1994）。近年来，研究者利用脑影像技术发现精神分裂症患者的脑结构存在异常，包括灰质体积和密度改变，白质异常和脑室体积增大等，为理解精神疾病的病理机制提供支持(Bakhshi& Chance,2015;Palaniyappan,2017）。现阶段精神分裂症脑影像研究多采用临床患者和健康对照的组间均值差异检验来考察患者的异常特征，然而这一方法获得的结果无法应用到个体水平上，机器学习(MachineLearning)技术可以弥补以上不足。机器学习这一概念最早由IBM(International Business Machines Corporation)公司的Arthur Samuel(1959）提出。TomMitchell提出更广泛且正式的机器学习定义：“对于某类任务T和性能度量P，如果一个计算机程序在T上以P衡量的性能随着经验E而自我完善，那么称这个计算机程序在从经验E学习”(Mitchell,1997)。在精神疾病领域，研究者利用机器学习从脑影像数据中学得规律、构建模型并利用模型在个体水平上进行预测，同时发现最具有鉴别能力的特征。

目前已经有研究者利用机器学习分类方法，尝试探讨如何从人群中识别出精神分裂症患者(Ardekani et al.,2011; Nieuwenhuis et al.,2012; Winterburn et al.,2017)、从高危人群中识别出未来转变为精神分裂症患者的个体(Zarogianni,Storkey,Johnstone,Owens,&Lawrie,2017)以及区分处于不同疾病阶段的临床患者(Guo,Palaniyappan,Liddle,& Feng,2016)。在训练模型的过程中，模型选取的特征一般是能够区分各类别的显著特征，因此精神分裂症患者、高危人群和健康对照的机器学习分类研究可以为精神分裂症的疾病诊断、预后判断、疗效判断相关生物标记物的寻找提供帮助。

本文将从以下四个方面进行系统论述：首先简要阐述机器学习的主要步骤，其次对以往利用脑结构像对精神分裂症患者及高危人群开展的机器学习研究进行系统梳理，并讨论现阶段精神分裂症领域机器学习研究的局限，最后提出未来研究方向。

# 1机器学习的主要步骤

将机器学习应用于精神分裂症的脑结构像(structural Magnetic Resonance Imaging,sMRI)数据时，主要步骤包括从脑影像中提取特征数据、特征降维和特征选择、训练模型、评估模型以及利用模型预测新样本（见图1）。

![](images/3e344b39a41e49f7fc860691571c942dbe8a936b237075e4a6a37443f0de07dd.jpg)  
图1．脑影像数据的机器学习分析步骤

# 1.1提取数据

在精神分裂症的脑结构像研究中，采用高信噪比的大脑图像是分析的基础。研究者应进行图像质量控制，以保证用于机器学习数据的可靠性和有效性。从脑影像中提取数据后，数据集将被分割成训练集和测试集或者训练集、验证集和测试集。研究者使用训练集数据寻找规律、生成模型，利用验证集数据调整模型参数、选择最优模型，最终使用测试集数据检验最终模型的性能。

# 1.2特征降维和特征选择

特征降维和特征选择能有效提高模型的泛化能力，是数据处理的重要步骤，对高维数据的处理尤为重要。特征降维是高维数据转变成低维数据的过程，常用方法是主成分分析(Principal Components Analysis,PCA)。特征选择是从原始或降维后的数据中选取具有最佳分类效果的特征子集的过程，该子集的类别分布应与原始数据的类别分布相似。Guyon,Weston,Barmhill和Vapnik(2002)基于评价准则将特征选择方法分为过滤法(Filter)、包装法（Wrapper）和嵌入法(Embedded)，三类特征选择方法在精神分裂症的脑影像分类研究中均有应用。过滤法根据特征的统计指标或特征与类别之间的相关性对特征进行评分，根据设定的阈值或设定的个数选择特征，有助于降低特征之间的相关性，提高特征与类别之间的相关性。包装法是根据算法的分类性能增减特征，如使用基于支持向量机的递归特征消除方法(Support Vector Machine-Recursive Feature Elimination,SVM-RFE） 选择特征。嵌入法合并特征选择和分类器训练过程，在训练过程中自动选择最优特征子集，如决策树算法在训练过程中优先选择分类能力更强的特征。除此之外，研究者还可以根据以往文献选择或移除特征，例如将精神分裂症患者受药物影响较大的纹状体的影像数据移除(Nieuwenhuis et al., 2012) 。

# 1.3训练模型

研究者利用机器学习算法寻找脑影像数据规律并生成模型。机器学习算法一般分为监督学习和无监督学习，区别在于算法是否使用样本数据的分类信息或目标值。在精神分裂症的研究中，研究者通常使用支持向量机（Support VectorMachine,SVM)、线性回归(Linear Regression）等监督学习算法探究精神分裂症患者或高危人群和健康对照的分类问题。

# 1.4评估模型和利用模型预测新数据

泛化能力是指模型适用于新数据的能力，研究者利用性能度量来衡量模型泛化能力，评估模型优劣（周志华，2016）。在精神分裂症的研究中，正确率（Accuracy)、敏感性(Sensitivity）即查全率(Recall）、查准率(Precision）和特异性（Specificity)是最直观的性能度量。正确率是判断正确的样本数占样本总数的百分比。敏感性指所有阳性样本中真阳性样本的比例。查准率指真阳性样本占判定为真的样本的百分比。特异性指真阴性样本占所有阴性样本的百分比。根据性能度量结果，研究者采取更改算法、调节模型参数等方法调整模型。最终模型确立后，可用来预测新数据的类别。

# 1.5交叉验证

交叉验证是特征选择、参数调整和最终模型检验中评估模型性能的有效方法，数据处理操作（如特征降维和特征选择）必须嵌入在交叉验证中。K折交叉验证(K-fold crossvalidation,K-foldCV）是最常见的交叉验证方法，它将样本分为K份，每次取K-1份为训练集，剩下1份为测试集，将平均正确率作为最终预测结果。在大多数研究中，研究者选择使用5折或10折交叉验证，也可根据样本大小和数理统计标准确定K值(Dwyer,Falkai,&Koutsouleris,2018)。由于受到样本量的限制，脑影像的机器学习研究通常采用K折交叉验证法的特殊形式——留一法(Leave One Out Cross Validation,LOOCV)，其K取样本总数N。留一法虽然简单，但具有高偏差、高耗时等缺点。

另外，有研究者建议使用嵌套交叉验证(Nested Cross Validation)(Madsen,Krohne,Cai,Wang,& Chan,2018)。嵌套交叉验证包括评估模型性能的外循环和用于选择最优特征、最优参数的内循环，令小样本数据集能够采用不同的数据来评估模型和选择特征、调整参数，最大程度减少偏差，缓解小样本数据的可用性问题，提高评估结果的可信度。目前已有多篇脑影像数据机器学习研究使用嵌套交叉验证方法(Borgwardt et al.,2013;Dyrba,Grothe,Kirste,& Teipel,2015; Peng et al.,2017; Zarogianni et al.,2017）。

# 2基于脑结构特征的精神分裂症患者与健康对照的分类研究

我们对2010年以来精神分裂症领域采用脑结构像数据（包括 T1加权像、弥散张量成像 (Diffusion tensor imaging,DTI））的机器学习研究进行文献搜索，使用的数据库包括Web of Science,PubMed，Elsevier，采用的关键词包括“structural MRI”，“MachineLearning”，“Support Vector Machine”，SVM，schizophrenia，“ highrisk”，schizotype 以及“ voxel based morphometry”， VBM，“ grey matter”，“graymater”，DTI，“diffusion tensor imaging”的不同组合。表1中列出截止到2019年1月17日搜索到的34篇文献的主要方法和结果。

根据分类特征是否来源于同一模态，脑影像数据分为单模态数据和多模态数据。为探讨上述两种数据和不同脑结构特征对精神分裂症脑影像的机器学习分类的影响，下文将按照基于脑结构像的单模态机器学习研究、基于DTI的单模态机器学习研究、多模态机器学习研究、脑影像数据和行为数据相结合的机器学习研究这一顺序进行综述。

# 2.1基于脑结构像的单模态机器学习研究

基于脑结构像的机器学习研究中，最常用的特征包括大脑灰质体积、白质体积和皮层厚度。在这些研究中，以慢性精神分裂症患者、首发精神分裂症患者，以及精神病高危个体为对象的分类研究均有报道。从机器学习的分类表现上看，现有研究的分类正确率在$3 6 . 8 4 \%$ 到 $9 8 \%$ 之间；在特征方面，使用额叶、颞叶的脑结构特征可以达到较高的正确率。

# 2.1.1精神分裂症

在精神分裂症的分类研究中，总样本量最小值为39，最大值为606，多数研究总样本量超过100；分类正确率在 $44 . 7 4 \%$ 到 $98 \%$ 之间；研究结果指出，额上回、额中回、额下回、颞中回、颞上回、梭状回、海马、楔前叶、丘脑和枕叶的脑结构特征具有较高的分类正确率；算法对分类正确率的影响不明显，特征选择方法可能会影响分类表现，相同特征对于不同病程患者的重要性有差异。

精神分裂症患者的脑结构随病程改变，有研究者采用98例不同病程的精神分裂症患者和83例健康对照的皮层厚度数据进行分析，去除了年龄和性别对皮层厚度的影响，使用基于RBF(RadialBasis Function)核的 SVM 算法进行分类并用留一法验证，获得 $8 1 . 7 7 \%$ 的平均分类正确率， $7 7 . 5 5 \%$ 的平均敏感性和 $8 6 . 7 5 \%$ 的平均特异性，进一步研究发现病程小于两年的患者与健康对照的分类正确率最高（ $9 6 . 3 \%$ ，特异性为 $9 8 . 8 \%$ 、敏感性为$8 8 \%$ ）；患者尤其是长病程患者的颞叶－边缘系统和额叶－顶叶的皮层厚度减少，但枕叶皮层厚度增加（Guo et al.,2016）。

在分类过程中，有研究者提出与使用全脑灰质密度数据相比，利用特征选择方法选取部分脑区的灰质密度作为特征能提高分类正确率。Chin,You,Meng,Zhou 和 Sim(2018)使用序列感兴趣区选择方法(sequential region-of-interest (ROI) selection）在64个脑区的灰质密度数据中选择最优特征，结果发现使用该特征选择方法可将84个精神分裂症患者和43个健康对照（训练集）的分类正确率从 $8 6 . 6 \%$ 提高到 $9 2 . 0 \%$ ，将57个精神分裂症患者和28个健康对照（测试集）的分类正确率从 $8 3 . 5 \%$ 提高到 $89 . 4 \%$ ，同时筛选出包含7个ROI的最佳分类子集，包括梭状回、额中回、额下回、颞上回、额上回、左丘脑和左侧脑室。还有研究者比较不同特征选择方法对分类正确率的影响。Nieuwenhuis 等人 (2012)采用基于体素的形态学分析（Voxel-Based Morphometry,VBM）提取脑结构像每个体素的灰质密度数据，用线性回归去除年龄、性别和利手的影响，将残差作为原始输入数据，分别采用嵌入法和基于先验知识选取特征，前者使用 SVM算法训练模型，选取权重绝对值前 $10 \%$ 的特征作为输入特征，后者基于以往研究去除受药物影响的纹状体的灰质密度，将余下脑区的灰质密度作为输入特征。使用线性 SVM算法在239个被试（128个患者和111个健康对照）中建立模型，使用留一法交叉验证。结果发现采用嵌入法选取特征建立的模型具有较好的分类表现： $71 . 4 \%$ 的平均正确率， $7 3 . 4 \%$ 的平均敏感性和 $6 9 . 4 \%$ 的平均特异性;最后在277个被试（155个患者和122个健康对照）的数据中进行验证，得到 $70 . 4 \%$ 的分类正确率， $67 . 1 \%$ 的敏感性和 $7 3 . 8 \%$ 的特异性；研究发现患者额叶、颞上回和海马的灰质密度降低，而基底神经节和左侧枕叶灰质密度增加。

除了使用不同的特征选择方法，研究者还探究不同算法对分类正确率的影响，Salvador等人(2017)使用127个健康对照和128个精神分裂症患者的灰质体积探究不同算法的分类性能。该研究采用的算法包括 Ridge，Lasso，弹性网络(Elastic Net），L0范数正则化逻辑回归(LO Norm Regularized Logistic Regressions），线性 SVM，正则化判别分析(Regularized Discriminant Analysis)，随机森林(Random Forests）和高斯过程分类（Gaussian Process Classifier)，发现使用这八种算法得到的分类结果并无较大差异，分类正确率在 $7 4 . 1 \%$ 到 $7 6 \%$ 之间。

现有研究不仅将机器学习应用于区分精神分裂症患者和健康对照，而且还尝试区分不同亚型精神分裂症患者。有研究者使用机器学习区分有无强迫症状的精神分裂症患者，在23例无强迫症状的精神分裂症患者和23例有强迫症状的精神分裂症患者的样本中发现中央旁小叶（包括辅助运动区）、中扣带回（middle cingulate gyrus）和额叶－皮层下(fronto-subcortical）区域的灰质密度能很好地区分两组被试，正确率达到 $78 . 2 6 \%$ (Tas etal., 2018)。

# 2.1.2首发精神分裂症

因受到病程和长期服用药物的影响，慢性精神分裂症患者的脑结构可能发生一定的改变，影响机器学习研究的分类表现。首发精神分裂症患者较少受到药物和病程的干扰，对这一群体的研究有利于探讨精神分裂症的神经病理机制。在首发精神分裂症患者的分类研究中，总样本量最小仅为42，最大达到480；分类正确率在 $44 . 7 4 \%$ 与 $9 6 . 7 \%$ 之间。在特征方面，额叶（如额上回、额中回和额极等）、颞中回、梭状回和舌回的脑结构特征能提高分类正确率。

分类问题是研究者首要关注的问题，在127个首发患者和127个健康对照的分类研究中，Squarcina等人(2017)提取68个感兴趣区的皮层厚度数据，分别对每个感兴趣区应用SVM 算法，根据分类结果选取5个最优特征；利用最优特征建立模型，使用SVM或多核学习(Multiple KernelLearning,MKL)算法进行训练和预测，在额上回，额中回喙部和颞中回取得 $8 5 \%$ 的最高正确率。

在首发精神分裂症患者中有研究者探究了不同算法应用于灰质密度和皮层厚度数据的分类表现。Winterburn 等人(2017)使用逻辑回归(Logistic Regression,LR)、SVM（包括线性 SVM 和 SVM-RBF）和线性判别分析（Linear Discriminant Analysis,LDA）三种算法进行分类，脑结构像数据包括灰质密度和皮层厚度，数据样本包括50例首发精神分裂症患者和50例健康对照，研究者首先将样本分为 2/3的训练集和1/3 的测试集，应用线性SVM 算法于灰质密度数据时，分类正确率最高可达 $6 9 . 6 \%$ （敏感性 $7 7 . 8 \%$ ，特异性$5 7 . 9 \%$ ）；使用 SVM-RBF 算法和皮层厚度数据进行分类，最高分类正确率可达 $7 3 . 5 \%$ （敏感性 $5 8 . 8 \%$ ，特异性 $8 8 . 2 \%$ ）。

# 2.1.3高危人群

与首发精神分裂症患者相比，识别高危人群与探究其脑结构有利于解释精神分裂症的发生机制、预测精神疾病的发生。目前利用脑结构像对高危人群的分类研究较少，总样本量均不超过50，分类正确率在 $3 6 . 8 4 \%$ 与 $72 \%$ 之间。其中，有研究者使用灰质体积数据和SVM 算法对25名高危个体和25名健康对照个体进行分类，应用留一法进行交叉验证，获得 $72 \%$ 的分类正确率（敏感性 $68 \%$ ，特异性 $76 \%$ ），双侧海马、海马旁回、壳核、额上回、额中回、梭状回和顶下小叶，左侧颞下回、右侧颞上回、左侧楔前叶和左侧小脑等区域具有较高的特征权重（Valli et al.,2016）。

# 2.2基于弥散张量成像的单模态机器学习研究

弥散张量成像是另一种常用的脑结构成像。水分子在脑中受到白质纤维（如髓鞘和轴突膜等）的约束，各个方向上的弥散不同，呈现各向异性。弥散张量成像利用水分子弥散的各向异性成像，用于探究脑白质纤维束的位置和方向(Meoded,Poretti,Mori,& Zhang,2017）。现有基于DTI的机器学习分类研究较少，样本量在42到154之间，研究常采用的特征包括各向异性分数（Fractional Anisotropy,FA）、轴向弥散张量（Axial Diffusivity,AD)、垂直弥散张量(Radial Diffusivity,RD)、平均弥散率(Mean Diffusivity,MD)等，从机器学习的分类表现上看，现有研究的分类正确率最低为 $60 \%$ ，最高可达 $9 8 \%$ 。

有研究者将50名精神分裂症患者和50名健康对照分为训练集和测试集，基于DTI数据计算FA和MD值，使用PCA降维并在数据中进行独立样本t检验，移除P值大于0.5的特征，利用Fisher 线性判别分析训练模型。结果发现使用FA 值构建的模型在测试集中获得 $94 \%$ 正确率（敏感性 $96 \%$ ，特异性 $92 \%$ ），有区分能力的特征集中在大脑深部白质区域，如双侧外囊(external capsule）；使用MD 值构建的模型在测试集中的正确率为 $9 8 \%$ （敏感性 $96 \%$ ，特异性 $100 \%$ ），影响正确率的特征集中在皮层和脑室；结合FA和MD数据进行分类并没有显著改变模型的分类正确率（正确率、敏感性和特异性均为 $9 6 \%$ ）(Ardekani et al., 2011）。

另外，有研究者基于DTI数据计算18条主要白质纤维束的FA、MD、RD 和AD值使用基于随机森林的递归特征消除法(Random Forest-Recursive Feature Elimination,RF-RFE）选择特征，采用随机森林算法在52个首发患者和48个健康对照的数据中进行训练和测试，得到 $71 \%$ 的分类正确率（敏感性 $67 . 3 \%$ ，特异性 $7 5 \%$ ）；用最终模型区分13个首发患者和12个健康对照得到 $76 \%$ 的分类正确率（敏感性 $7 6 . 9 \%$ ，特异性 $7 5 \%$ ），具有区分能力的特征位于连合纤维、小脑-丘脑-皮层回路(the cerebello-thalamo-cortical circuits)和长纤维(Deng et al.,2019)。

Pettersson-Yeo 等人(2013)利用FA 值分别对19个高危个体和23个健康对照、19个首发患者和23个健康对照进行分类，使用SVM算法均得到 $6 5 . 7 9 \%$ 的分类正确率，其敏感性均为 $6 8 . 4 2 \%$ ，特异性均为 $6 3 . 1 6 \%$ 。

# 2.3基于多模态脑影像数据的机器学习研究

除了单模态数据，现有研究还尝试结合多种模态脑影像数据对精神分裂症患者或高危人群与健康对照进行分类。目前多模态脑影像机器学习分类研究有8篇，总样本量在46到144 之间，分类正确率在 $54 . 9 \%$ 到 $100 \%$ 之间，常与 T1 加权像数据结合的脑影像数据有静息态功能磁共振成像(resting state functional Magnetic Resonance Imaging,rs-fMRI)数据和DTI数据。

Peruzzo 等人(2015)结合 T1 加权像和DTI数据，采用非参数统计检验和 SVM 算法选取特征，采用多核学习MKL 算法对23个首发精神分裂症患者和23个健康对照进行分类，正确率最高达到 $9 3 . 5 \%$ ，影响正确率的特征包括杏仁核、额上回、额下回、苍白球、海马旁回的灰质体积和侧脑室体积，额上回、额中回、额下回、梭状回、海马旁回、颞中回、眶额皮层和脑岛的皮层厚度，钩束、扣带、小脑下角和胼抵体压部的弥散张量值。此外，Sui 等人(2013)提出一种多模态融合的方法—— mCCA(multi-set Canonical Correlation

Analysis）和 jICA (joint Independent Component Analysis），将 rs-fMRI、结构像和 DTI的数据两两结合，对35名精神分裂症患者和28名健康对照个体进行分类，发现单模态数据的分类正确率在 $5 0 \% { \sim } 7 0 \%$ 之间，多模态数据正确率在 $6 0 \% { \sim } 8 0 \%$ 之间。另外，该研究团队还基于 rs-fMRI、T1 加权像和脑电数据（(Electroencephalogram，EEG）采用独立样本t检验，mCCA和 SVM-RFE 选择特征，应用 SVM算法和十折交叉验证方法在43个精神分裂症患者和48个健康对照中得到 $91 \%$ 的分类正确率，并且以 $100 \%$ 的正确率成功区分5个精神分裂症患者和5个健康对照个体 (Sui etal.,2014)。

虽然现阶段大部分多模态脑影像的机器学习研究分类正确率较高，但此类研究的样本量通常较小。因此，多模态脑影像数据对分类结果的影响仍需要进一步探讨。

# 2.4脑影像数据和行为数据相结合的机器学习研究

除结合不同模态的脑影像数据以外，目前也有将脑影像数据和行为数据相结合作为分类特征的机器学习研究，现有研究建议将脑影像数据和行为数据结合能提高分类正确率。

有研究将灰质、白质、脑脊液体积与威斯康星卡片分类测试（Wisconsin card sortingtest，WCST）的错误率结合，利用独立成分分析处理数据，使用 SVM算法在19个精神分裂症患者和16个健康对照的数据中取得 $91 . 5 8 \%$ 的分类正确率，证明WCST的错误率和脑影像数据结合能有效区分患者和健康对照（Chu,Huang,Jian,Hsu,&Cheng2016)。Zarogianni 等人(2017)预测34名具有家族遗传史的高危个体是否会转变为精神分裂症患者，应用 SVM-RFE 算法在各脑区的灰质密度数据、Rust Inventory of SchizotypalCognitions (RISC)问卷分数和雷氏听觉语言学习测验(Rey Auditory Verbal Learning Test,RAVLT)得分中进行特征选择，用 SVM算法进行预测，分类正确率达到 $94 \%$ ，高于仅使用灰质密度数据的分类正确率 $( 8 8 \% )$ 。Ebdrup等人(2018)对46个首发精神分裂症患者和58个健康对照进行分类，结合行为数据（包括韦氏智力量表第三版和丹麦成人阅读测试(DanishAdult Reading Test)）和 T1 加权像、DTI和EEG的数据仅获得 $5 1 \% { \sim } 6 8 \%$ 的分类正确率，低于仅使用认知数据的分类结果 $( 6 0 \% { \sim } 6 9 \% )$ ，稍高于单独使用单模态数据的分类结果 $( 4 9 \% { \sim } 5 6 \% )$ 。因此，现有研究提示结合行为数据和脑影像数据的分类结果可能优于单模态数据的分类结果，但结合这两类数据能否取得高正确率仍有待进一步探讨。

![](images/b92de0cf81917b51d372f4c092560ca10fd10005b8e7506f04f3e88cc251e39d.jpg)  
图2精神分裂症患者、高危人群基于脑结构像分类研究的总样本量和分类正确率。SCZ：精神分裂症；HC：健康对照；FEP：首发精神分裂症；HR：高危人群。实心点代表最高分类正确率；空心点代表最低分类正确率；虚线连接同一研究中相同样本量的最高与最低分

类正确率。

# 3机器学习研究的局限

将机器学习应用于精神分裂症领域，利用脑结构特征对精神分裂症患者、高危人群与健康对照进行分类，有助于理解疾病的生理病理机制。研究数量逐年递增，但仍具有一定局限，特别是在研究样本量和模型泛化能力上仍存在问题，亟待解决。

# 3.1样本量

图2总结了现有精神分裂症和高危人群中机器学习研究采用的总样本量以及分类的最高和最低正确率。如图2所示，样本量在50到150时，最高分类正确率较高，样本量大于400 时，最高正确率只有 $6 0 \% { \sim } 7 2 \%$ 。出现小样本分类正确率高而大样本分类正确率低的情况可能有如下原因：1）样本量小导致模型不稳定和测试不准确。训练样本量过小容易导致训练不充分，造成模型过拟合或不稳定；测试样本量过小，容易出现过高或过低的分类正确率，即使在小样本测试中得到高正确率仍难以验证一个模型的性能。有研究表明，验证一个模型的有效性至少需要75到100 个测试样本(Beleites,Neugebauer,Bocklitz,Krafft,&Popp,2013)；2）现有大样本研究的分类特征远大于样本量，研究中未进行特征选择，容易造成模型过拟合，降低分类正确率；3）大样本研究数据来自多个中心，患者的异质性可能更高，从而降低分类正确率。

样本量不足是现阶段精神分裂症领域机器学习研究面临的一大问题(Madsen et al.,2018)。样本量不足的主要原因包括磁共振扫描成本高、精神分裂症的特殊性和数据共享困难。高昂的磁共振成像扫描费用和较长的扫描时间导致研究者难以在短时间内收集大量脑影像数据。精神分裂症患者受到临床症状和药物副作用的影响，在采集脑影像数据时需要耗费更多的人力和物力，采集难度大，因此与精神分裂症有关的脑成像研究样本量通常较小。除此之外，多中心数据共享困难是也是可能的原因之一，各中心扫描仪器的型号和参数各不相同，并且存在数据管理、伦理和隐私保护的问题。

未来多个研究机构／中心可以通过制定详细协议保障被试隐私和数据安全，统一扫描参数和入组标准，在不违背伦理的情况下实现多中心数据共享，增大样本量。研究者在纳入多中心数据时，需要保证入组标准尽可能一致；在处理大样本数据时，进行数据清洗，利用降维和特征选择的方法保留有用特征，保证数据质量，得到更加可信的结果，从而利用大样本数据考察脑结构特征的有效性。有研究者提出可以通过合并多中心模型解决样本量问题。研究者分别在4个中心收集首发精神分裂症患者和健康对照的脑结构数据，分别使用4个中心的数据训练模型，利用这4个模型生成最终的元模型 (the meta-model)。研究发现该元模型与基于所有数据生成的模型有较高的相似性 (Dluhos et al.,2017）。因此,合并多中心模型为解决样本无法共享提供了一种新思路。

# 3.2泛化能力

机器学习的目标是使训练得到的模型能够很好地适用于新样本，即具有较好的泛化能力。除了样本量不足会影响模型泛化能力外，机器学习训练过程中出现信息泄露也会影响泛化能力。常见的信息泄露的情况是使用同一批样本调整参数和测试结果，在特征选择时提前使用测试集的标签，如在所有样本中进行独立样本t检验选取显著脑区，再进行训练集、测试集和验证集的拆分。提前使用测试集的信息，虽然能得到高正确率，但是不能反映模型真正的泛化能力。研究者在今后研究中应避免信息泄露并使用嵌套交叉验证(Madsen et al.,2018;Dwyer et al.,2018)，使评估结果更加精确，提高模型泛化能力。为测试泛化能力，Dwyer等人(2018)建议未来可设置第三方检测机构，收集各中心或机构的数据，一旦形成新模型，研究者可移交第三方机构，利用其数据进行测试，从而保证较好的泛化能力。

# 4未来研究展望

未来的精神分裂症脑影像机器学习研究可以考虑在特征中加入用药情况、临床症状和社会人口学等信息。Kambeitz等人(2015)在精神分裂症患者和健康对照的脑影像机器学习研究中，将特异性和敏感性作为效应量，考察年龄、阳性症状与阴性症状比率、抗精神病药物剂量对分类结果的影响。该元分析发现，年龄越大机器学习分类的敏感性越高；阳性症状与阴性症状比率越大特异性越高；抗精神病药物剂量越大特异性越高。因此，在区分不同病程的患者或探究预后情况时，可以纳入临床信息和社会人口学信息，提高分类表现。

近年来，随着计算机技术的高速发展，深度学习开始重新获得人们关注。深度学习是以人工神经网络为架构，对数据进行表征学习的算法，在图像、视频、语音等多个领域均表现优异(Bengio, Courvile,& Vincent, 2013; Lecun, Bengio,& Hinton,2015; Schmidhuber,2015）。Pinaya等人(2016)使用深度信念网络(Deep Belief Network），在143 例精神分裂症患者和83例健康对照中得到了 $7 3 . 6 \%$ 的分类正确率（敏感性 $76 . 3 7 \%$ ，特异性$70 . 7 4 \%$ ），稍高于使用 SVM 算法的正确率（ $6 8 . 1 \%$ ）。Dwyer等人(2018)指出，深度学习需要大样本数据来避免维度灾难和过拟合。因此，研究者可以在获得大样本数据的基础上，尝试使用深度学习的方法进行分类，探究精神分裂症的内在机制。

现有研究的数据处理流程和结果报告都不相同，由于缺乏具体信息和使用方法的差异，不同研究之间很难进行比较。据此Riley(2019)指出将机器学习应用于不同学科领域中时，应建立统一的数据分析和结果报告标准。

# 5总结

机器学习技术从数据中提取有用信息，可以协助研究者在个体水平上进行预测，探究精神分裂症的特点和内在机制，帮助寻找生物标记物、实现精神疾病的早期识别。本文主要从脑结构像出发，综述了单模态、多模态脑影像和结合行为数据与脑影像的机器学习研究。单模态脑影像的机器学习分类正确率在 $3 6 . 8 4 \%$ 到 $98 \%$ 之间，多基于 T1 加权像，结果提示额叶和颞叶的脑结构特征可以有效区分精神分裂症患者或高危人群和健康对照；基于DTI的机器学习研究多采用弥散张量值为特征，但因其样本量小且现有研究少，各研究者提出的能提高分类正确率的脑区或纤维特征大不相同，尚未达成统一意见。多模态脑影像的分类正确率在 $5 4 . 9 \% { \sim } 1 0 0 \%$ 之间，多数研究的分类正确率高，但样本量小，多模态数据是否显著优于单模态数据并有效提高分类正确率，有待研究者进一步探讨。行为数据和脑影像数据结合的分类效果优于单模态数据的分类效果，但能否显著提高分类正确率仍待进一步验证。目前精神分裂症领域的机器学习研究具有样本量不足和泛化能力弱等局限，未来还需要在多中心的大样本中进行模型训练和验证，以求获得更可靠的模型和更有效的特征，才能在临床实践中发挥更大作用。

表1文献总结  

<html><body><table><tr><td>作者</td><td>样本量</td><td>模态</td><td>算法</td><td>特征选择</td><td>交叉验证</td><td>正确率</td></tr><tr><td>Wang,L.,Shen, H., Li, B., & Hu, D., 2011</td><td>SCZ(32) HC(32)</td><td>T1</td><td> svm</td><td></td><td>十折交叉验证</td><td> 59.4%~82.8%</td></tr><tr><td>Greenstein, Malley, Weisinger, Clasen, & Gogtay, 2012</td><td>SCZ(98) HC(99)</td><td>T1</td><td>RF</td><td></td><td></td><td>73.7%</td></tr><tr><td>Nieuwenhuis et al., 2012</td><td>训练集： SCZ(128) HC(111) 测试集： SCZ(155)</td><td>T1</td><td>Linear SVM</td><td>结合SVM 选特征 基于以往知识</td><td>留一法</td><td>训练集： 67.5%~86.8% 测试集： 69.1%~70.6%</td></tr><tr><td>Iwabuchi, Liddle, & Palaniyappan, 2013 Schnack et al., 2014</td><td>HC(122) SCZ(19)HC(20)</td><td>T1</td><td>Linear SVM svm</td><td></td><td>留一法</td><td>63.9%~77%</td></tr><tr><td></td><td>训练集： SCZ(66) BD(66) HC(66) 测试集： SCZ(46) BD(47) HC(43)</td><td>T1</td><td></td><td></td><td>Leave-4-out, Leave-2-out</td><td>训练集： SCZ vs HC : 90.15% SCZ vs BD : 87.9% HC vs BD: 59.85% 测试集： HC vs SCZ : 76%</td></tr><tr><td>Gould et al., 2014</td><td>CD(74) CS(126)</td><td>T1</td><td>Linear SVM</td><td></td><td>Leave-2-out</td><td>BD vs SCZ : 66% HC vs BD : 61% HC vs CD: 64%~72%</td></tr></table></body></html>

<html><body><table><tr><td>Guo et al., 2016</td><td>SCZ(98) HC(83)</td><td>T1</td><td colspan="2"> SVM-RBF</td><td>留一法</td><td>81.77%~96.3%</td></tr><tr><td>Lu et al., 2016</td><td>SCZ(41) HC(42) SCZ(128)</td><td>T1 T1</td><td>SVM Ridge LR; Lasso LR; Elastic Net</td><td>SVM-RFE 单变量t值</td><td>留一法 嵌套交叉验证（外层：</td><td>79.5%~88.4% SCZ vs HC :</td></tr><tr><td>Salvador et al., 2017</td><td>BD(128) HC(127)</td><td></td><td>Regularization; L0-norm Regularization; SVM; RDA; GPC; RF</td><td></td><td>十折交叉验证，内层： 十折交叉验证)</td><td>58.2%~79.2% SCZ vs BD : 49.2%~66% BD vs HC: 49.1%~65.5%</td></tr><tr><td>Chin et al., 2018</td><td>训练集： SCZ(84) HC(43) 测试集： SCZ(57) HC(28)</td><td>T1</td><td>SVM</td><td>sequential ROI selection algorithm</td><td></td><td>训练集： 86.6%~92% 测试集： 83.5%~89.4%</td></tr><tr><td>de Pierrefeu et al., 2018</td><td>训练集： SCZ(276) HC(330) 测试集： FEP(43) HC(90)</td><td>T1</td><td> linear SVM, Elastic Net, Enet-TV</td><td></td><td>二折交叉验证</td><td>训练集： 61%~72% 测试集： 61%~73%</td></tr><tr><td>Takayanagi, Y. et.al., 2011 Zaneti, M. V., et. al,</td><td>FEP(52) HC(40)</td><td>T1</td><td>LDA</td><td></td><td></td><td>81.2%~96.7%</td></tr><tr><td>2013</td><td>FEP(62) HC(62)</td><td>T1</td><td>svm</td><td>结合•SVM 选特征</td><td>留一法</td><td>64.3%~73.4%</td></tr><tr><td>Dluhos et al., 2017</td><td>FEP(258) HC(222)</td><td>T1</td><td>SVM</td><td></td><td>留一法</td><td>52%~66%</td></tr><tr><td>Squarcina et al., 2017</td><td>FEP(127) HC(127)</td><td>T1</td><td> SVM-RBF, MKL</td><td>结合•SVM 选特征</td><td>留一法</td><td>68%~85%</td></tr></table></body></html>

<html><body><table><tr><td>Xiao et al., 2017</td><td>FEP(163) HC(163)</td><td>T1</td><td>Linear SVM</td><td>两样本</td><td>t检验 (p<0.05)</td><td>十折交叉验证</td><td>81.8%~85.0%</td></tr><tr><td>Winterburn et al., 2017</td><td>FEP(50) HC(220) SCZ(179)</td><td>T1</td><td>LR, SVM(RBF/Linear), LDA</td><td></td><td></td><td>十折交叉验证</td><td>训练集： SCZ vs HC : 50.0%~71.9%</td></tr><tr><td rowspan="5"></td><td></td><td rowspan="5"></td><td rowspan="5"></td><td rowspan="5"></td><td rowspan="5"></td><td></td><td>FEP vs HC : 50.0%~71.2%</td></tr><tr><td></td><td></td></tr><tr><td>测试集：</td><td></td></tr><tr><td></td><td>SCZ vs HC : 51.0%~70.8%</td></tr><tr><td rowspan="2"></td><td></td><td>FEP vs HC : 50.6%~73.5%</td></tr><tr><td rowspan="2">de Moura et al., 2018</td><td rowspan="2">FEP(32) chronic T1 SCZ(143)</td><td rowspan="2">MLDA LDA</td><td rowspan="2"></td><td rowspan="2">留一法</td><td> SCZ vs HC :</td><td>73.0%</td></tr><tr><td>FEP vs HC :</td><td>59.4%</td></tr><tr><td rowspan="2"> Ardekani et al., 2011</td><td>HC(32) 训练集： SCZ(25) HC(25)</td><td rowspan="2">DTI</td><td rowspan="2"></td><td rowspan="2">两样本t 检验 (p<0.5)</td><td rowspan="2">100 次二折交叉验证</td><td>sensitivity 训练集：94%~98%</td><td></td></tr><tr><td rowspan="2"></td><td rowspan="2">测试集：96%</td><td></td></tr><tr><td rowspan="2">Rathi Y. et. al., 2010</td><td rowspan="2">测试集： SCZ(25) HC(25) FEP(21) HC(20)</td><td rowspan="2">DWI</td><td rowspan="2">Parzen window classifier, KNN,</td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td></tr><tr><td>69%~86% sensitivity</td></tr><tr><td>Mikolas, P. et. al.,</td><td>FEP(77) HC(77)</td><td>DTI</td><td>SVM Linear SVM</td><td></td><td> Leave-2-out</td><td></td><td> 68%~85% specificity</td></tr><tr><td>2018 Deng et al., 2019</td><td>训练集：</td><td>DTI</td><td>RF</td><td>RF-RFE</td><td>留一法</td><td></td><td>62.34%</td></tr><tr><td rowspan="4"> Sui et al.,2013</td><td>FEP(52) HC(48)</td><td></td><td></td><td></td><td></td><td></td><td>训练集：71.0% 测试集：76.0%</td></tr><tr><td>测试集：</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>FEP(13) HC(12) SCZ(35) HC(28)</td><td>T1</td><td>SVM(RBF/Linear), KNN, GNB</td><td> mCCA+jICA</td><td>十折交叉验证</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>“单模态：≈ (50%~70%)</td></tr></table></body></html>

<html><body><table><tr><td colspan="2"></td><td colspan="2">DTI rs-fMRI</td><td colspan="3"></td><td colspan="2">a多模态： ≈ (60%~80%)</td></tr><tr><td rowspan="2">Sui et al., 2014</td><td rowspan="2">训练集： SCZ(43) HC(48) 测试集：</td><td rowspan="2">T1 rs-fMRI</td><td rowspan="2">Linear SVM</td><td rowspan="2">mCCA，两样本t检验， SVM-RFE</td><td rowspan="2">十折交叉验证</td><td>训练集：</td><td></td></tr><tr><td>单模态： a多模态：</td><td>66%~93%</td></tr><tr><td rowspan="3"></td><td rowspan="3">SCZ(5) HC(5)</td><td rowspan="3">EEG</td><td rowspan="3"></td><td rowspan="3"></td><td rowspan="3"></td><td></td><td>(≥80%)~91%</td></tr><tr><td>测试集：</td><td></td></tr><tr><td>单模态： 多模态：</td><td>50%~90%</td></tr><tr><td>Qureshi, Oh, Cho, Jo, & Lee,2017</td><td>SCZ(72) HC(72)</td><td>T1 rs-fMRI</td><td> SVM(RBF/Linear), ELM, LDA, RF</td><td></td><td>10 次十折交叉验证</td><td>单模态：</td><td>80%~100% 42.4%~93.0%</td></tr><tr><td rowspan="2">Tas et al., 2018</td><td rowspan="2">SCZ(23) schizo- obsessive (23)</td><td rowspan="2">T1 T2</td><td rowspan="2">SVM-RBF</td><td rowspan="2">ACO</td><td rowspan="2">嵌套交叉验证（外层： 六折交叉验证，内层：</td><td>多模态：</td><td>54.9%~99.3%</td></tr><tr><td>78.26%</td><td></td></tr><tr><td>Peruzzo et al., 2015</td><td>FEP(23) HC(23)</td><td>T1 DTI</td><td> SVM, MKL</td><td>非参数统计检验(p<0.05)+结合 SVM 选特征</td><td>五折交叉验证) 留一法</td><td>78.26%~93.48%</td><td></td></tr><tr><td>Lu et al.,2018</td><td>FEP(44) chronic SCZ(44) HC(56)</td><td>rs-fMRI T1</td><td>SVM</td><td>SVM-RFE</td><td></td><td>ä多模态：≥ 85%</td><td></td></tr><tr><td>Valli et al, 2016 Karageorgiou, E., et.</td><td>HR(25) HC(25) SCZ(28) HC(47)</td><td>T1 T2 T1</td><td>Linear SVM stepwise LDA</td><td>Wilk's A(p=0.05 保留 ,p=0.10</td><td>留一法 留一法</td><td>54%~72% 单模态： 70.7%~72%</td><td></td></tr><tr><td>al., 2011</td><td></td><td>Neuropsychological</td><td>PCA-LDA</td><td>删除）</td><td></td><td>神经心理和脑影像数据： 76%~92%</td><td></td></tr><tr><td>Chu et al., 2016</td><td>SCZ(19) HC(16)</td><td>T1 the error rate of the WCST</td><td> svm</td><td></td><td></td><td>82.794%~91.575%</td><td></td></tr><tr><td>Ebdrup et al., 2018</td><td>FEP(46)HC(58)</td><td>Cognition data(DART,WAIS III) T1</td><td>naive Bayes,LR,SVM,decision tree, RF, auto-sklearn</td><td>反向特征消除</td><td></td><td>单模态：49%~56% 认知数据和影像数据：</td><td></td></tr></table></body></html>

<html><body><table><tr><td colspan="2"></td><td>DTI EEG</td><td></td><td></td><td>51%~68%</td></tr><tr><td rowspan="5">Petterson-Yeo et al., 2013</td><td rowspan="5">UHR(19) FEP(19) HC(23)</td><td>T1 SvM</td><td></td><td>留一法</td><td>UHR vs HC :</td></tr><tr><td>DTI</td><td></td><td></td><td>36.84%~68.42%</td></tr><tr><td> fMRI</td><td></td><td></td><td> UHR vs FEP :</td></tr><tr><td> Molecular genetics</td><td></td><td></td><td>33.33%~76.67%</td></tr><tr><td>Neuropsychology</td><td></td><td></td><td>HC vs FEP :</td></tr><tr><td rowspan="3">Zarogianni et al., 2017</td><td>HR[ill](17) HR[symp](17)</td><td>T1</td><td>SVM</td><td>SVM-RFE 嵌套交叉验证（外层：</td><td>44.74%~68.42% 单模态：88%</td></tr><tr><td></td><td>behavioural data(RISC score,</td><td></td><td>留一法，内层：留</td><td>行为和影像数据：94.1%</td></tr><tr><td>RAVLT score)</td><td></td><td></td><td>法）</td><td></td></tr><tr><td colspan="3">SCZ：精神分裂症患者；HC：健康对照；FEP：首发精神分裂症患者；UHR：超高危人群；HR：高危人群，其中，HR[i]是转变为精神分裂症的高危人群，HR[symp]是未转变为精神分裂症的</td><td></td><td></td><td></td></tr><tr><td colspan="6">高危人群；BD：躁郁症患者；DII：弥散张量成像；T1：T加权像；DWI：difsonwegtdimging（弥散加权成像）；fMRI：功能性磁共振成像，is-MRI为静息态功能性磁共振成像；</td></tr><tr><td colspan="3">EEG：脑电，</td><td></td><td></td></tr><tr><td colspan="3">是核函数为高斯核的支持向量机，LinearSV为支持向量机：ELM：creeleamigmahine（极限学习机）；naivBayes：素贝叶斯；deitre：决策树；：：ees</td><td></td><td></td></tr><tr><td colspan="3">Neighbor（k最近邻）；G：ssaNivB高斯素斯）；：lpleeL（核）；lstiRegarizai则化，</td><td></td><td></td></tr><tr><td colspan="3">Els</td><td></td><td></td></tr><tr><td colspan="3">RF：Random）；），</td><td></td><td></td></tr><tr><td colspan="3">（基于支持向量：IuI</td><td></td><td></td></tr><tr><td colspan="3">Di</td><td></td><td></td></tr><tr><td colspan="3">神分裂症的认知缺陷亚型；cognitively spared subtype：精神分裂症的认知正常亚型</td><td></td><td></td></tr><tr><td colspan="3"></td><td></td><td></td></tr></table></body></html>

参考文献   
周志华.(2016)．机器学习．清华大学出版社．   
Ardekani, B.A., Tabesh,A., Sevy, S.,Robinson,D.G., Bilder, R. M.,& Szeszko,P.R.(2011). Diffusion tensor imaging reliably differentiates patients with schizophrenia from healthy volunteers. Human Brain Mapping, 32(1), 1-9. https://doi.org/10.1002/hbm.20995   
Bakhshi, K., & Chance, S. A. (2015). The neuropathology of schizophrenia: A selective review of past studies and emerging themes in brain structure and cytoarchitecture. Neuroscience. https://doi.org/10.1016/j.neuroscience.2015.06.028   
Beleites, C., Neugebauer, U., Bocklitz, T.,Krafft, C.,& Popp, J. (2013). Sample size planning for classification models. Analytica Chimica Acta, 760,25-33. doi:10.1016/j.aca.2012.11.007   
Bengio, Y., Courville, A., & Vincent, P. (2013). Representation learning: A review and new perspectives. IEEE Transactions on Patern Analysis and Machine Intelligence. https://doi.0rg/10.1109/TPAMI.2013.50   
Borgwardt, S., Koutsouleris, N.,Aston, J., Studerus, E., Smieskova, R., Riecher-Rosser, A.,& Meisenzahl, E. M. (2013). Distinguishing prodromal from first-episode psychosis using neuroanatomical single-subject pattern recognition. Schizophrenia Bulletin,39(5), 1105-1114. https://doi.org/10.1093/schbul/sbs095   
Carpenter, W.T.,& Buchanan, R. W. (1994). Schizophrenia. New England Journal of Medicine, 330(10), 681-690. htps://doi.0rg/10.1056/NEJM199403103301006   
Chin, R., You,A. X., Meng,F., Zhou, J.,& Sim, K. (2018). Recognition of Schizophrenia with Regularized Support Vector Machine and Sequential Region of Interest Selection using Structural Magnetic Resonance Imaging. Scientific Reports, 8(1),13858. https://doi.0rg/10.1038/s41598-018-32290-9   
Chu, W.-L., Huang, M.-W., Jian, B.-L., Hsu, C.-Y., & Cheng, K.-S. (2016). A Correlative Classification Study of Schizophrenic Patients with Results of Clinical Evaluation and Structural Magnetic Resonance Images. Behavioural Neurology, 2016, 1-11. https://doi.0rg/10.1155/2016/7849526   
de Moura, A. M., Pinaya, W. H. L., Gadelha, A., Zugman, A., Noto, C., Cordeiro, Q.,.. Sato, J. R. (2018). Investigating brain structural patterns in first episode psychosis and schizophrenia using MRI and a machine learning approach. Psychiatry Research - Neuroimaging, 275(March),14-20. https://doi.org/10.1016/j.pscychresns.2018.03.003   
de Pierrefeu, A., Lofstedt, T.,Laidi, C., Hadj-Selem,F., Bourgin, J., Hajek,T.,...Duchesnay, E. (2018). Identifying a neuroanatomical signature of schizophrenia, reproducible across sites and stages, using machine learning with structured sparsity. Acta Psychiatrica Scandinavica. https://doi.org/10.1111/acps.12964   
Deng, Y., Hung, K. S. Y., Lui, S. S. Y., Chui, W. W. H., Lee, J. C. W., Wang, Y.,.. Cheung, E. F. C. (2019). Tractography-based classification in distinguishing patients with first-episode schizophrenia from healthy individuals. Progress in Neuro-Psychopharmacology and Biological Psychiatry, 88, 66-73. https://doi.org/10.1016/j.pnpbp.2018.06.010   
Dluhos, P., Schwarz,D., Cahn, W., van Haren, N., Kahn, R., Spaniel,F.,.. Schnack, H. (2017). Multi-center machine learning in imaging psychiatry: A meta-model approach. NeuroImage, 155(April),10-24. https://doi.org/10.1016/j.neuroimage.2017.03.027   
Dwyer, D.B., Falkai, P., & Koutsouleris, N. (2018). Machine Learning Approaches for Clinical Psychology and Psychiatry. Annual Review of Clinical Psychology,14(1),annurev-clinpsy032816-045037. htps://doi.org/10.1146/annurev-clinpsy-032816-045037   
Dyrba,M., Grothe, M., Kirste, T.,& Teipel, S.J. (2015). Multimodal analysis of functional and structural disconnection in Alzheimer's disease using multiple kernel SVM. Human Brain Mapping,36(6),2118-2131. htps://doi.org/10.1002/hbm.22759   
Ebdrup, B. H., Axelsen, M. C., Bak, N., Fagerlund, B., Oranje,B., Raghava, J. M.,... Glenthoj, B.Y. (2018). Accuracy of diagnostic classification algorithms neuroanatomical data in antipsychotic-naive schizophrenia patients. Psychological Medicine. https://doi.0rg/10.1017/S0033291718003781   
Gould,1. C., Shepherd,A. M.,Laurens, K.R., Cairns, M. J., Car, V. J.,& Green, M.J. (2014). Multivariate neuroanatomical classfication of cognitive subtypes in schizophrenia: a support vector machine learning approach. NeuroImage: Clinical, 6, 229-236.   
Greenstein, D., Malley, J. D., Weisinger, B., Clasen,L., & Gogtay, N. (2012). Using Multivariate Machine Learning Methods and Structural MRI to Classfy Childhood Onset Schizophrenia and Healthy Controls. Frontiers in Psychiatry,3(June), 1-12. https://doi.0rg/10.3389/fpsyt.2012.00053   
Guo, S., Palaniyappan, L., Liddle, P.F., & Feng, J. (2016). Dynamic cerebral reorganization in the pathophysiology of schizophrenia: A MRI-derived cortical thickness study. Psychological Medicine,46(10),2201-2214. https://doi.0rg/10.1017/S0033291716000994   
Guyon, I., Weston, J., Barnhill, S., & Vapnik, V. (20o2). Gene selection for cancer classification using support vector machines. Machine Learning. https://doi.org/10.1023/A:1012487302797   
Iwabuchi, S. J., Liddle, P.F., & Palaniyappan, L. (2013). Clinical Utility of Machine-Learning Approaches in Schizophrenia: Improving Diagnostic Confidence for Translational Neuroimaging. Frontiers in Psychiatry, 4(August), 1-9. https://doi.0rg/10.3389/fpsyt.2013.00095   
Kambeitz, J.,Kambeitz-Ilankovic,L.,Leucht, S., Wood, S.,Davatzikos, C., Malchow,B.. Koutsouleris,N. (2O15). Detecting neuroimaging biomarkers for schizophrenia: A metaanalysis of multivariate pattern recognition studies. Neuropsychopharmacology, 40(7),1742- 1751. https://doi.org/10.1038/npp.2015.22   
Karageorgiou, E., Schulz, S. C., Gollub, R.L., Andreasen, N. C., Ho, B. C.,Lauriello,J.,.. & Georgopoulos, A. P. (2011). Neuropsychological testing and structural magnetic resonance imaging as diagnostic biomarkers early in the course of schizophrenia and related psychoses. Neuroinformatics, 9(4), 321-333.   
Lecun,Y., Bengio, Y., & Hinton, G. (2015). Deep learning. Nature. https://doi.org/10.1038/nature14539   
Lu, X. B., Zhang, Y., Yang, D. Y., Yang, Y. Z, Wu, F. C., Ning, Y. P., & Wu, K. (2018). Analysis of first-episode and chronic schizophrenia using multi-modal magnetic resonance imaging. European Review for Medical and Pharmacological Sciences, 22(19), 6422-6435. https://doi.org/10.26355/eurrev_201810_16055   
Lu, X.,Yang, Y., Wu,F., Gao,M., Xu,Y., Zhang,Y.,.. Wu, K. (2016). Discriminative analysis of schizophrenia using support vector machine and recursive feature elimination on structural MRI images. Medicine (United States), 95(30), e3973. https://doi.0rg/10.1097/MD.0000000000003973 Madsen, K.H., Krohne,L. G., Cai, X.L., Wang, Y.,& Chan, R. C. (2018).Perspectives on machine learning for classification of Schizotypy using fMRI data. Schizophrenia bulletin, 44(suppl_2), S480-S490. htps://oi.0rg/10.1093/schbul/sby026   
Meoded,A., Poreti, A., Mori, S.,& Zhang, J. (2017). Diffusion Tensor Imaging (DTI)☆. Reference Module in Neuroscience and Biobehavioral Psychology, (March 2016),1-11. https://doi.0rg/10.1016/B978-0-12-809324-5.02472-X   
Mitchell, T. (1997). Machine Learning.   
Nieuwenhuis, M., van Haren, N. E.M., Hulshoff Pol,H.E., Cahn, W., Kahn,R. S.R.S.,& Schnack, H. G. (2012). Classification of schizophrenia patients and healthy controls from structural MRI scans in two large independent samples. NeuroImage, 61(3), 606-612. https://doi.org/10.1016/j.neuroimage.2012.03.079 Mikolas,P.,Hlinka,J., Skoch,A.,Pitra, Z.,Frodl, T., Spaniel,F.,& Hajek,T. (2018). Machine learning classification of first-episode schizophrenia spectrum disorders and controls using whole brain white matter fractional anisotropy. BMC Psychiatry, 18(1), 97. https://doi.0rg/http://dx.doi.org/10.1186/s12888-018-1678-y   
Palaniyappan,L. (2017). Progressive cortical reorganisation: A framework for investigating structural changes in schizophrenia. Neuroscience and Biobehavioral Reviews. https://doi.org/10.1016/j.neubiorev.2017.04.028 Peng,B.,Lu, J., Saxena,A., Zhou, Z., Zhang,T., Wang, S.,& Dai, Y. (2017). Examining brain morphometry associated with self-esteem in young adults using Multilevel-ROI-FeaturesBased classification method. Frontiers in Computational Neuroscience, 11(May),1-10. https://doi.org/10.3389/fncom.2017.00037   
Peruzzo,D., Castellani, U.,Perlini, C.,Bellani,M., Marinelli, V.,Rambaldelli, G.,...Brambilla,P. (2015). Classification of first-episode psychosis: A multi-modal multi-feature approach integrating structural and diffusion imaging. Journal of Neural Transmisson (Vienna, Austria : 1996),122(6), 897-905. https://doi.0rg/10.1007/s00702-014-1324-x Petersson-Yeo, W., Benetti, S., Marquand,A.F.,Dell'Acqua,F., Williams, S. C.R., Allen,P.,. Mechelli, A. (2013). Using genetic, cognitive and multi-modal neuroimaging data to identify ultra-high-risk and first-episode psychosis at the individual level. Psychological Medicine, 43(12),2547-2562. https://doi.0rg/10.1017/S003329171300024X   
Pinaya, W. H.L., Gadelha,A., Doyle, O. M., Noto, C., Zugman,A., Cordeiro, Q.,.. Sato, J. R. (2016). Using deep belief network modelling to characterize differences in brain morphometry in schizophrenia. Scientific Reports, 6(1),38897. https://doi.0rg/10.1038/srep38897 Qureshi, M. N.I., Oh, J., Cho, D., Jo,H. J.,& Lee,B. (2017). Multimodal Discrimination of Schizophrenia Using Hybrid Weighted Feature Concatenation of Brain Functional Connectivity and Anatomical Features with an Extreme Learning Machine. Frontiers in Neuroinformatics,11(September),1-14. htps://oi.org/10.3389/fninf.2017.00059   
Rathi Y,Malcolm J, Michailovich O, Goldstein J, Seidman L, McCarley RW et al (2010). Biomarkers for identifying first-episode schizophrenia patients using diffusion weighted imaging. Med Image Comput Comput-Assist Interv 13: 657-665. Riley, P. (2019). Three pitfalls to avoid in machine learning. Nature, 572(7767), 27-29. Salvador,R., Radua, J., Canales-Rodroaguez, E.J. Solanes, A., Sarroa, S., Goikolea,J. M. Pomarol-Clote,E. (2017). Evaluation of machine learning algorithms and structural features

for optimal MRI-based diagnostic prediction in psychosis. PLoS ONE,12(4),1-24.

https://doi.org/10.1371/journal.pone.0175683   
Samuel,A.L. (1959). Some studies in machine learning using the game of checkers. IBM Journal of research and development, 3(3),210-229. https://doi.org/10.1147/rd.33.0210   
Schmidhuber, J. (2015). Deep Learning in neural networks: An overview. Neural Networks. https://doi.org/10.1016/j.neunet.2014.09.003   
Schnack, H. G., Nieuwenhuis,M., van Haren, N.E.M.,Abramovic,L., Scheewe,T. W., Brouwer, R. M.,... Kahn, R. S. (2014). Can structural MRI aid in clinical classification? A machine learning study in two independent samples of patients with schizophrenia, bipolar disorder and healthy subjects. NeuroImage, 84, 299-306.   
Squarcina,L.,Castellani, U., Bellani, M.,Perlini, C.,Lasalvia,A., Dusi,N.,.. Brambilla,P.(2017). Classification of first-episode psychosis in a large cohort of patients using support vector machine and multiple kernel learning techniques. Neurolmage, 145(Pt B), 238-245. https://doi.org/10.1016/j.neuroimage.2015.12.007   
Sui, J., Castro, E., He, H., Bridwel, D., Du, Y., Pearlson, G.D.,... Calhoun, V.D. (2014). Combination of FMRI-SMRI-EEG data improves discrimination of schizophrenia patients by ensemble feature selection. Conference Proceedings : .. Annual International Conference of the IEEE Engineering in Medicine and Biology Society. IEEE Engineering in Medicine and Biology Society. Annual Conference,2014(2),3889-3892. https://doi.0rg/10.1109/EMBC.2014.6944473   
Sui, J.,He, H., Yu, Q., Chen,J., Rogers, J.,Pearlson, G.D.,.. Calhoun, V. D.(2013). Combination of Resting State fMRI, DTI, and sMRI Data to Discriminate Schizophrenia by N-way MCCA $^ +$ jICA. Frontiers in Human Neuroscience, 7(May), 1-14. https://doi.org/10.3389/fnhum.2013.00235   
Takayanagi, Y., Takahashi,T., Orikabe,L., Mozue, Y., Kawasaki, Y., Nakamura, K.,..& Kurachi, M. (2011). Classification of first-episode schizophrenia patients and healthy subjects by automated MRI measures of regional brain volume and cortical thickness. PloS one, 6(6), e21047.   
Tas, C., Mogulkoc, H., Eryilmaz, G., Gogcegoz-Gul, 1., Erguzel, T. T., Metin, B., & Tarhan, N. K. (2018). Discriminating schizophrenia and schizo-obsessive disorder: a structural MRI study combining VBM and machine learning methods. Neural Computing and Applications, 29(2), 377-387. https://doi.0rg/10.1007/s00521-016-2451-0   
Valli, I., Marquand,A.F.,Mechelli, A., Raffin, M.,Allen,P., Seal, M.L., & McGuire,P. (2016). Identifying Individuals at High Risk of Psychosis: Predictive Utility of Support Vector Machine using Structural and Functional MRI Data. Frontiers in Psychiatry, 7, 52. https://doi.0rg/10.3389/fpsyt.2016.00052 Wang,L., Shen,H.,Li, B.,& Hu,D. (2011). Classification of schizophrenic patients and healthy controls using multiple spatially independent components of structural MRI data. Frontiers of Electrical and Electronic Engineering in China, 6(2), 353-362. https://doi.0rg/10.1007/s11460-011-0142-2   
Winterburn,J.L.,Voneskos,A.N.,Devenyi,G.A.,Plitman,E.,de laFuente-Sandoval,C.,Bhagwat, N.,... Chakravarty, M.M. (2O17). Can we accurately classify schizophrenia patients from healthy controls using magnetic resonance imaging and machine learning? A multi-method and multi-dataset study. Schizophrenia Research. htps://doi.org/10.1016/j.schres.2017.11.038   
Xiao,Y., Yan, Z., Zhao,Y.,Tao,B., Sun,H.,Li,F....Lui, S. (2017). Support vector machine-based classification of first episode drug-naive schizophrenia patients and healthy controls using structural MRI. Schizophrenia Research. https://doi.org/10.1016/j.schres.2017.11.037   
Zarogianni,E., Storkey,A. J., Johnstone,E. C., Owens,D. G. C.,& Lawrie, S.M. (2017). Improved individualized prediction of schizophrenia in subjects at familial high risk, based on neuroanatomical data, schizotypal and neurocognitive features. Schizophrenia Research,181, 6-12.https://doi.org/10.1016/j.schres.2016.08.027   
Zanetti, M.V., Schaufelberger,M.S.,Doshi, J.,Ou,Y.,Ferreira,L.K., Menezes,P.R.,..& Busato, G.F. (2013). Neuroanatomical pattern classification in a population-based sample of firstepisode schizophrenia. Progress in Neuro-Psychopharmacology and Biological Psychiatry, 43,116-125.

# The classification of schizophrenia based on brain structural features: A machine learning approach

Hong ZHENG 1.2; Cheng-cheng PU³; Yi WANG $^ { . 1 , 2 }$ ; Raymond C. K. CHAN $^ { 1 , 2 }$ （204 (1 Neuropsychology and Applied Cognitive Neuroscience Laboratory,CAS KeyLaboratory of Mental Health, Institute ofPsychology， Chinese Academy of Sciences,Beijing10o101,China) (2 Department of Psychology, University of Chinese Academy of Sciences,Beijing 10oo49,China) (3Peking UniversitySixthHospital,Peking University InstituteofMental Health,NHCKeyLaboratoryof Mental Health(Peking University),National Clinical Research Center for Mental Disorders (Peking University Sixth Hospital).Beijing 100191,China)

Abstract: Machine learning is a promising approach for mental disorders. In recent years,machine learning based on T1 weighted imaging and Diffusion Tensor Imaging (DTI) data has been used to investigate the psychopathology and underlying mechanisms of schizophrenia patients and high-risk population. The findings from the previous literature suggest that structural features of frontal lobe and temporal lobe can improve classification performance. In addition， the combination of behavioural performances and the features of brain structure is superior to the singlemodality structural images on classification accuracy. However, the existing empirical studies classifying schizophrenia patients or high-risk population from controls are limited in sample size and generalization ability.

Key Words :structural Magnetic Resonance Imaging; Diffusion Tensor Imaging; machine learning; schizophrenia; high risk population