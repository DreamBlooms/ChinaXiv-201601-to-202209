# 综述

# 机器学习在儿童创伤后应激障碍识别及转归预测中的

应用

刘笑晗，陈明隆，郭静（北京大学公共卫生学院，北京100191）

摘要 创伤后应激障碍（PTSD）会给儿童发展带来负面效应，其影响甚至延续至成年期。然而传统诊断方式难以做到快速、客观、准确的识别和诊断儿童PTSD，机器学习作为一种处理大量变量和数据的新兴方法，逐渐被应用到儿童PTSD 的早期预测、识别及辅助诊断等研究中。机器学习凭借其性能、原理等方面的优势，可被应用在儿童PTSD的识别与转归领域。相比自我报告式的诊断，通过机器学习辅助识别和诊断儿童PTSD的过程具有效率高、客观准确、节约资源等独特优势。然而，机器学习也在硬件成本、算法选择和预测准确度等方面存在局限性。未来研究人员需要进一步提高机器学习诊断识别儿童PTSD 的准确率，并将机器学习算法同传统诊断方法结合进行更多的探索和应用。

关键词机器学习，创伤后应激障碍，转归预测，儿童

# Application of Machine Learning in Prognosis and Trajectory of Post-Traumatic Stress Disorder in Children

XiaohanLIU， MinglongCHEN， JingGUO1 （School of Public HealthPeking University,Beijing 100191)

Abstract: Post-traumatic stress disorder (PTSD) has negative effects on children's development, even into adulthood. However, traditional diagnostic methods are diffcult to quickly,objectively and accurately identify and diagnose PTSD in children. Machine learning, as an emerging method to deal with a large number of variables and data, has gradually been applied to the research of early prediction, recognition and auxiliary diagnosis of PTSD in children. Machine learning, with its advantages in performance and algorithm, can be applied to the recognition and prognosis of

PTSD in children. Compared with self-reported diagnosis，the process of identifying and diagnosing PTSD in children through machine learning has unique advantages of high efficiency, objective accuracy and resource saving. However, machine learning also has limitations in terms of hardware cost, algorithm selection and prediction accuracy. In the future,researchers need to further improve the accuracy of machine learning diagnosis and recognition of PTSD in children, and combine machine learning algorithms with traditional diagnosis methods for more exploration and application.

Keywords: Machine learning, Post-traumatic stress disorder, Prognosis, Children

# 1.引言

创伤后应激障碍（Post-Traumatic Stress Disorder PTSD）是个体经历、目睹或遭遇到一个或多个威胁生命或造成严重伤害事件后所出现和持续存在的警醒、负向情绪、回避等精神症状(Weathers etal.,2013)。儿童PTSD具有较高流行率：据估计， $10 \sim 2 0 \%$ 的儿童在经历创伤性事件后，会出现警醒、回避、负向情绪等创伤后应激障碍症状（Post-Traumatic StressSymptoms PTSS）(Alisic et al.,2014)。儿童PTSD 的发展结局具有异质性：一项综述研究提示,灾难发生一个月后儿童PTSD发生率在 $2 1 \% , 3$ 个月后降至 $1 5 \%$ ，一年后保持在 $1 1 \%$ (Hilleret al.,2016)，并且罹患PTSD 的患者在疾病的后续阶段中会出现 $6 \%$ 恢复、 $10 \%$ 恶化或 $4 \%$ 长期患病等不同结局(Bryant et al.,2015)，意味着儿童PTSD 的发生与转归会随着环境、时间等因素发生动态变化。儿童创伤后应激障碍的追踪研究发现，PTSD与抑郁、物质滥用、犯罪、自杀等不良健康结果高度相关(Canciliere et al.,2021; Jensen et al.,2014,2019)，其负面影响可以持续到成年期,甚至具有代际传递效应(Yehuda etal.,2001)。因而,预测或识别儿童 PTSD的风险因素，提出有针对性的干预策略有利于降低儿童PTSD 的发生、减少其向其他身心疾病发展的可能性。

如何提高儿童PTSD 诊断方法的准确性一直是临床实践和学术研究中的挑战。以往识别儿童PTSD 的方法，通常使用美国心理学协会出版的《精神障碍诊断和统计手册》(Diagnosticand Statistical Manual of Mental Disorders DSM）、国际疾病和相关健康问题统计分类(International Statistical Classification of Diseases and Related Health Problems ICD）和婴幼儿心理健康与发育障碍的诊断分类（Diagnostic Classification of Mental Health andDevelopmental Disorders of Infancy and Early Childhood DC），我们国家也会使用中国精神障碍分类与诊断标准(Chinese Classification and Diagnostic Criteria of Mental Disorders CCMD）,根据儿童自我报告或父母报告的症状进行判断(Scheeringa et al.,2006)。但由于年龄较小的儿童难以准确清晰的表达症状，以及代理人（通常为父母）对儿童的了解程度不足往往导致诊断率低于真实情况(Scheeringa et al.,2006)。同时，在实际诊断过程中，医生的主观理解和判断也可能导致诊断率或敏感性偏低(De Young& Landolt,2018)。除此之外，儿童PTSD 疾病发展的过程具有长期性和复杂性，发展结局受多种因素影响。但由于可纳入的变量有限，用于预测PTSD转归的传统方法容易产生误差。

机器学习因其强大的数据处理、挖掘能力已经被广泛用于医疗领域。近年来机器学习已成功用于自闭症、注意缺陷多动障碍和精神分裂症的预测分类(G et al.,2015;Mueller et al,2010; Zandvakili et al.,2019),也被用于预测成人急性PTSD(Galatzer-Levy et al.,2014; Karstoftet al.,2015)。在儿童精神健康领域，机器学习被用来诊断注意力问题、学业问题、焦虑问题、注意缺陷多动障碍和广泛性发育障碍(Sumathi&B.,2016)。尽管目前使用机器学习诊断儿童PTSD 的研究还处于探索阶段，不具有统一的标准，对模型的选择和应用还没有形成成熟的体系。但越来越多的研究表明基于多源数据、大数据，运用机器学习方法，探索PTSD 的发展规律、转归机制和影响因素具有可行性(Takahashi et al.,2020; Worthington et al.,2020)。

本研究旨在整理机器学习方法应用于儿童PTSD诊断和转归的相关研究，归纳总结机器学习方法用于儿童PTSD 识别和转归中的优势、劣势，为完善机器学习在该领域的应用提供参考。

# 2.机器学习的原理及在儿童PTSD中的进展

# 2.1机器学习方法简介

机器学习是人工智能的一个分支、涉及多个学科，包含了能通过经验（训练）提高自身表现的程序(Al-Sahaf et al.,2019;Jones,2019)，致力于通过计算手段改善系统自身性能。机器学习研究的内容是关于在计算机上从数据中产生模型的算法，即学习算法（leamingalgorithm）（周志华，2018)。机器学习的分类非常广泛，根据数据是否带有标记信息（即是否提前规定了结果或其他指标）可以分为监督学习、无（非）监督学习、半监督学习和强化学习(Brownlee,2016)。按照学习策略可分为机械学习、示教学习、类比学习、归纳学习和基于解释的学习。也可以根据应用的领域如语言处理、计算机视觉、智能机器人等进行分类，或者依据获取知识的形式进行分类等。机器学习的主要过程是根据收集数据的特征或属性，将数据集分为训练集和测试集，在训练集中进行数据模拟和运算，用测试集不断调整和优化模型，最终能够良好的适用于新的数据，见图1。

![](images/92d5d32eebaa9bf81bec880f18e9f69986045a261afc8e933caf183c585c1c69.jpg)  
图1.机器学习预测儿童PTSD诊断与识别过程（以 Saxe等人的研究为例(Saxe et al.,2017)）

# 2.2机器学习在儿童PTSD领域的应用现况

近年来机器学习的应用越来越广泛。以在PubMed中的检索结果为例，截止到 2021年4月21日，得到111233 条有关机器学习的研究，PTSD 领域的研究有185篇，但聚焦于儿童群体只有10篇。机器学习最初应用到精神健康涉及抑郁症、精神分裂症、双相障碍等诊断技术较为准确和成熟的领域(Koprowski&Foster,2018)。2012年 James 等人利用机器学习的方法优化了成年人PTSD 的认知行为干预方式，将机器学习引入PTSD 领域(Kelly et al,2012)。2017年Glenn 等人首次尝试将机器学习的概念应用于儿童PTSD，探索与儿童PTSD发生相关的因素(Saxe et al.,2017)。机器学习在儿童 PTSD 中的研究是遵循着风险因素探索一—预测转归结局—一验证或选择治疗方案的逻辑路径。首先探索风险因素(Saxe et al.,2017)，再将相关因素作为机器学习的特征，用以进行 PTSD 的识别和诊断(Li etal.,2020)，根据长期追踪的结果预测转归结局(Ge etal.,2020)，最后研究治疗方法的有效性(Ucuz et al.,

2020)。在这一过程中以监督式机器学习为主，使用较多的模型是决策树、随机森林，支持向量机和回归(Li etal.,2020; Saxe et al.,2017)，近年来为优化机器学习效果，逐渐尝试非监督机器学习、深度学习等新方法(Schultebraucks, Yadav,et al.,2020)。

本研究在主要的文献检索平台PubMed、Embase、Scopus、Web of science、Ovid、中国知网、中国万方进行检索，最终纳入5篇调查研究。检索策略、结果和筛选标准如下（表1)：

表1.检索策略、结果和筛选标准  

<html><body><table><tr><td></td><td>关键词</td></tr><tr><td>机器学习</td><td>"Machine Learning" [Title/Abstract] OR "Artificial Inteligence"[Title/Abstract] OR "Deep Learning"[Title/Abstract] OR "NeuralNetwork"[Title/Abstract]OR"Supportvector machine"[Title/Abstract] OR "Prediction Network"[Title/Abstract] OR "Forecast Model"[Title/Abstract] OR "Data mining"[Title/Abstract] OR "Supervised Learning"[Title/Abstract]</td></tr><tr><td>PTSD/创伤 后应激障碍</td><td>"post-traumaticstress"[Title/Abstract]OR"postraumaticstress"[Title/Abstract] OR PTSD[Title/Abstract] OR PTSS[Title/Abstract] OR PTS[Title/Abstract]</td></tr><tr><td>儿童/青少年</td><td>child[Title/Abstract] OR children[Title/Abstract] OR girl[Title/Abstract] OR boy[Title/Abstract] ORinfant[Title/Abstract]ORbaby[Title/Abstract]ORbabies[Title/Abstract] OR toddler[Title/Abstract] OR preschool [Title/Abstract] OR "pre-school"[Title/Abstract] OR minor [Title/Abstract] OR teen[Title/Abstract] OR adolescent[Title/Abstract] OR youth[Title/Abstract]</td></tr></table></body></html>

纳入标准：1）研究对象：18岁以下的儿童。2）研究设计：包括横断面研究、队列研究或病例对照研究等中英文文章（中文检索结果为0）。3）研究内容：应用机器学习分析创伤后应激障碍或创伤后应激症状。排除标准：1）研究对象：18岁以上的成年人、老年人及其他特殊群体。2）研究设计：排除使用政策分析、描述性分析的文献。3）研究内容：排除与创伤后应激障碍或创伤后症状无关的心理疾病研究以及没有将创伤后应激障碍作为因变量的研究，或未应用机器学习方法的研究。4）出版物类型：描述性综述、评论，给编辑的书信、病例报告、书籍章节、报告、会议记录或未发表的手稿被排除。见图2.

![](images/afa3b6e2036bb4e90247bded7c7646e276cdf8410eaf4104e776c1ceb185234f.jpg)  
图2.应用机器学习诊断识别儿童PTSD相关研究的检索过程

# 3．机器学习在儿童PTSD诊断识别中的应用

传统方法识别诊断儿童PTSD 是临床医生或研究人员根据诊断手册上的症状标准进行比对，符合症状描述的儿童诊断为患有PTSD。识别儿童PTSD 的风险因素是通过既往文献或根据研究者经验做出假设，应用传统多元回归方法进行验证。这种判断儿童PTSD的方法过于依赖临床医生或研究者的个人经验，诊断或识别儿童PTSD受主观因素影响较大，临床医生和父母很大程度上决定了诊断结果。预测的风险因素结果也受到研究者所选择统计方法的影响，研究人员经常使用的基于回归模型的预测方法纳入的变量数量和类型有限，对风险因素的识别不够全面，并且在调查过程中需要消耗大量人力物力资源。

机器学习是根据已有经验进行规律总结和特征归纳，通过不断的数据训练使程序自行判断新数据中儿童是否会患有PTSD，比人为判断更为客观，而且速度更快，效率更高。在预测风险因素时，可以同时处理多个维度的变量。Saxe 等人(Saxe etal.,2017)基于儿童人口统计学信息、发育特征、症状和功能、儿童父母的症状、压力、损伤程度、相关基因、神经内分泌和心理生理反应等领域的105 个变量，选择重复嵌套5次交叉验证的模型，重复计算30 次，采用支持向量机（Support VectorMachines SVM）、随机森林和 Lasso 回归三类五种广泛应用的分类器。结果显示机器学习的AUC平均值是0.79，高于传统逻辑回归模型。最终确定了既往创伤应激障碍、既往损伤、相关基因、氯胺酮使用剂量等十个能导致儿童 PTSD的因果变量。Emel SariGokten 等人也进行了相似的研究，应用随机森林模型，得到0.76 的AUC 均值，并确定虐待类型和孩子的共同居住者两个最重要的影响特征(Gokten& Uyulan,2021)，详见表2。识别PTSD 的风险因素，意味着可通过客观指标进行PTSD的诊断，在提高诊断效率的同时能有效降低临床诊断中的主观偏倚，节约物质资源，减轻临床医生的工作量。若对风险因素进行早期干预与控制也能预防PTSS 恶化导致的不良心理健康结局。

除支持向量机、随机森林等常见模型，基于复合树模型的监督式分类和回归树算法(classification and regression trees CART）也表现出较高的准确度，AUC 等于 0.80(Ge et al.,2020)。而使用人工神经网络（Artificial Neural Network ANN）算法的准确度达到了$9 9 . 2 \%$ (Ucuz et al.,2020)。ANN是深度学习算法的基本组成部分，能够克服上述基于逻辑符号的机器算法在处理直觉、非结构化信息方面的缺陷，具有自适应、自组织和实时学习的特点，具有高速寻找最优解能力，更擅长处理复杂变量。

机器学习应用于儿童PTSD识别和诊断的过程中，影响因素覆盖范围从生物学指标（基因、脑核磁成像)到社会心理因素（压力、童年创伤），越来越广泛和全面(Lietal.,2020; Saxeet al.,2017;Ucuz et al.,2020)；机器学习的模型也从传统的决策树、回归发展到深度学习领域，诊断准确率大幅提高(Saxe et al.,2017; Ucuz et al.,2020)。

# 4.机器学习在儿童PTSD转归预测中的应用

儿童PTSD 的转归是指儿童在确诊PTSD 后的不同发展轨迹，其主要涉及两个内容，基于量变的轨迹（常用潜在生长混合模型分析）和基于质变的轨迹（常用潜在转变分析或潜在类别分析）。发展轨迹的分类根据不同的数据及分析方法呈现多样性。Betty 等人根据现有文献归纳出 PTSS 的三种基本轨迹，分别是：慢性，恢复和抗逆力型(Lai et al.，2017)。Galatzer-Levy 等人的文献综述则提出了潜在创伤事件发生后的抗逆力型、恢复、慢性和延迟发作四种轨迹(Galatzer-Levy et al.,2018)。Bonanno 等人认为大多数人在经历创伤后具有心理抗逆力，创伤经历与心理问题并不是绝对的因果关系(Bonanno,2004)。据此他们将面临潜在创伤后人们的反应分为了六类：抗逆力型，在人群中占 $3 5 \sim 6 5 \%$ ；持续性痛苦（ $5 \sim 1 5 \%$ ）；慢性功能障碍（ $5 \sim 3 0 \%$ ）；延迟性症状增加（ $10 \sim 1 5 \%$ ）；恢复 $( 1 5 \sim 2 5 \% )$ 和症状改善 $( 5 \sim$ $10 \%$ )(Bonanno et al.,2011; Bonanno&Diminich,2013)。只有不能从 PTSD自行恢复的儿童才需要进行早期干预(Masten& Narayan,2012)。因此研究儿童 PTSD 转归对筛选高危人群和帮助确定需要心理干预的儿童和青少年具有很强的理论和实践意义(Cheng etal.,2019)。

儿童PTSD的病因众多，疾病本身具有迟发性，预后呈现多模式性和复杂性的特点，追踪长期结局较为困难，因此关于儿童PTSD 结局转归的研究较少(Takahashi et al.,2020)。传统用于分类的统计方法例如潜在类别分析（Latent Category Analysis,LCA）和潜在生长混合模型（Latent Growth Mixture Modeling LGMM），根据个体在分类变量上的响应情况将个体分为互斥的群。例如 Jin Cheng 等人使用LCA探索地震后儿童 PTSD 的发展轨迹，将幸存儿童的状态划归为四类，命名为弹性 $( 5 3 . 8 \% )$ 、低症状 $( 3 2 . 6 \% )$ 、恢复 $( 7 . 0 \% )$ 和慢性功能障碍$( 6 . 6 \% )$ (Cheng etal.,2019)。然而这项长达四年的纵向研究中也存在回忆偏倚与遗漏重要变量等局限性。

机器学习主要有两种基本方法可以预测儿童PTSD 的结局。一种是预测离散数据的方法，也称为分类，属于监督学习，是人为设定训练数据集可能会出现的分类结果。例如根据以往经验，假设符合某些特征的儿童可能会出现PTSD的结局，如恢复、恶化等，或者是通过传统分类方法如潜在生长混合模型先确定转归结局。然后再通过机器学习将预测儿童PTSD 的特征与转归结局进行映射，训练集习得模型后，可以预测新的数据会出现哪种结局。另一种预测离散数据的方法是聚类，即训练集中的数据会按照特征或某些潜在的概念自动分成若干组，每一组称一簇，之后人为总结出这些簇的共性，属于非监督学习。聚类分析可以用于区别 PTSD 和其他精神疾病,或评估 PTSD 各症状之间的关系(Ramos-Lima et al.,2020)。Luis 等人的系统综述中详细的介绍了应用监督机器学习对PTSD转归结局进行分类的研究，包括主要算法和准确度(Ramos-Lima et al.,2020)。也有研究尝试使用其他非监督机器学习算法如图示分析（graph analysis）探索PTSD 的转归。例如Galatzer-Levy 等人首先应用LGMM确定了两种转归结局，恢复和未见好转(Galatzer-Levy et al.,2017)。随后采用支持向量机、随机森林、AdaBo0st 等算法，进行5次10折交叉验证，得到0.82的AUC。并且在图示分析中分类出尿皮质醇、回避症状、NE/皮质醇血浆比率和 PTSD 严重程度四类与PTSD 转归相关的信息，还确定了两种无法缓解创伤后应激症状的途径：路径1是没有报告童年期创伤的个体在急诊室经历了高度的交感神经兴奋和负面情绪，导致其出现回避症状，最终PTSD无法缓解。路径2是报告儿童期创伤的个体其尿皮质醇降低与无法缓解的PTSD 存在因果关系(Galatzer-Levy et al.,2017)。与监督机器学习相比，非监督机器学习确定疾病转归的结果更具有不确定性。但是目前检索到的文献中并未发现仅仅针对儿童PTSD 使用分类或聚类分析的研究，可能与对机器学习预测儿童PTSD 转归的关注较少，非监督机器学习的预测准确率较低有关。应用机器学习预测儿童PTSD 的发展轨迹可以弥补传统儿童PTSD长期预后调查难度较大，失访率较高，研究时限较长等问题，也可改善既往研究中出现的由于儿童PTSD的迟发性，未能持续追踪及时发现PTSD 症状，导致患者错过最佳疗愈时期的问题。

表2.机器学习在儿童PTSD诊断和识别中的应用  

<html><body><table><tr><td rowspan="2">时间</td><td rowspan="2">国家</td><td colspan="2">题目</td><td rowspan="2">样本量</td><td rowspan="2">年龄</td><td rowspan="2">主要变量</td><td rowspan="2">变量 数量</td><td rowspan="2">因变量测量</td><td rowspan="2">分类器</td><td rowspan="2">训练方法</td><td rowspan="2">评价指标</td></tr><tr><td></td><td></td></tr><tr><td rowspan="3">2017</td><td rowspan="3">美国</td><td>posttraumatic stress:</td><td>Machine learning methods to predict child a proof-of-concept</td><td rowspan="3">165</td><td rowspan="3">7~18</td><td>儿童发展、人口统计学信息、父母症状、 压力、基因、神经内分泌和心理生理反应、</td><td>105个</td><td rowspan="3">加州大学洛杉矶 分校创伤后应激 障碍反应指数</td><td rowspan="3">SVM;RF; Lasso回 归</td><td rowspan="3">5折交叉验证</td><td rowspan="3">AUC=0.75</td></tr><tr><td>study(Saxe et al., 2017)</td><td></td><td></td><td>受伤程度、儿童症状和功能</td></tr><tr><td>Identifying predictors of probable posttraumatic</td><td></td><td></td><td></td></tr><tr><td rowspan="4">C 2020 00:--</td><td rowspan="4">中国 中国</td><td>stress disorder in children and adolescents with</td><td></td><td></td><td></td><td>人口统计学信息、地震经历、睡眠、心情、</td><td>5个</td><td>修订版儿童事件</td><td></td><td></td><td></td></tr><tr><td>using a machine learning approach(Ge et al.,</td><td>earthquake exposure: A longitudinal study</td><td>2099</td><td>8~19</td><td>躯体症状和日常功能</td><td>方面</td><td>影响量表</td><td>CART</td><td>5折交叉验证</td><td>AUC= 0.66 ~0.80</td></tr><tr><td>2020)</td><td>Hippocampal subfield alterations in pediatric</td><td></td><td></td><td>静息态功能磁共振成像：海马亚区</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>et al., 2020)</td><td> patients with post-traumatic stress disorder(Li</td><td>46</td><td>11~16</td><td>CA1、CA2、CA3、CA4、齿状回、下托 及海马伞等</td><td>1个方 面</td><td>创伤后应激障碍 评估表</td><td>RF</td><td>5折交叉验证</td><td>AUC= 0.65</td></tr><tr><td>707:> 2020</td><td></td><td></td><td>Estimation of the Development of Depression and PTSD in Children Exposed to Sexual</td><td>170</td><td></td><td>年龄等人口统计学信息、虐待类型、虐待</td><td></td><td>精神障碍诊断和</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>土耳其</td><td></td><td></td><td>372</td><td>13.77</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>2020</td><td></td><td></td><td></td><td></td><td>均数</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>次数等虐待相关信息、事件报告者</td><td></td><td></td><td></td><td></td><td></td><td>99.2%</td></tr><tr><td></td><td>土耳其</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>准确度：</td></tr><tr><td>ivPi</td><td></td><td></td><td>Abuse and Development of Decision Support</td><td></td><td>5~17</td><td></td><td></td><td>10个</td><td></td><td>ANNs</td><td>3折交叉验证</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>统计手册</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>Systems by Using Artificial Intelligence(Ucuz</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td> and post-traumatic stress disorder in sexually</td><td></td><td></td><td></td><td></td><td>性别年龄等人口统计学信息、吸烟饮酒等</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>精神障碍诊断和</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>abused childrenusing a randomforest</td><td></td><td></td><td></td><td></td><td>20个</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>生活习惯信息、被虐待的经历程度信息、</td><td></td><td></td><td>RF</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>精神状态</td><td></td><td>统计手册</td><td></td><td>10 折交叉验证</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>AUC=0.76</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>classifier(Gokten & Uyulan, 2021)</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

注：RFado人工神经网络

# 5.机器学习应用于儿童PTSD的前景

尽管机器学习对儿童PTSD的诊断和识别具有一定优势，但应用仍处于初级阶段，机遇与挑战同时存在。

# 5.1机器学习在儿童PTSD应用的局限性

不同模型的预测结果可能存在差异。虽然可以通过大量的特征进行儿童PTSD 的诊断预测，但PTSD的结局包含诸多症状结构和不同的严重程度，对于有限的建模方法其定义相对广泛，可能无法保证每次运行结果的一致性(Galatzer-Levy& Bryant,2013)。其次目前有关儿童 PTSD 的机器学习研究采用监督式较多，对分类器（模型）的选择依靠人工选择、个人对模型的理解程度，缺乏具体的判断标准，只能通过各种模型的不断尝试选择预测概率最高的模型，而没有纳入计算的模型，无法进行判断。

预测准确度仍需要提高。以往研究结果显示，机器学习预测准确率在 $6 5 \% \sim 8 0 \%$ (Ge et al.,2020; Gokten& Uyulan,2021; Li etal.,2020; Saxe et al.,2017)，相较于机器学习用于其他领域的成熟发展，准确率相对较低。样本量、训练方法和所选模型均是准确率的影响因素。为推动机器学习在儿童PTSD诊断和识别的实践应用，尝试不同样本量、训练频次和各类模型以提高预测准确度，提升机器学习的效率十分必要。

关于治疗方法的研究相对不足。早期诊断和识别儿童PTSD 的目的是采取治疗措施减少对儿童未来发展的影响，排除治疗方法本身的局限，选择适宜不同程度PTSD 的治疗方法对于儿童的恢复和降低复发概率至关重要，但使用机器学习预测治疗方法的相关研究在儿童PTSD 中极度缺乏。早期干预决定了儿童PTSD 的长期健康结果，机器学习应用于儿童PTSD干预措施的评估和选择是对先前诊断和识别的紧密承接，也可能成为影响儿童PTSD 发展的重要因素。

应用于儿童PTSD 诊断和识别的机器学习算法较为单一。机器学习算法可以实现数据的回归、分类和聚类，不同算法的适用条件和运行结果有所差异，理论上尝试更多的算法有助于选择最佳模型，提高预测准确度，但在儿童PTSD 的诊断和识别领域，监督式算法较为常见，而非监督式算法（如神经网络算法）和深度学习算法（如卷积网络算法）相对少见。监督学习可用于对已知结果的分类分析，既可以评估儿童PTSD的患病风险，也可以诊断高风险因素儿童患病的情况，而非监督学习用于对未知结果的聚类分析，能够分析儿童PTSD发展的长期轨迹和趋势(Rajkomar et al.,2019)。儿童 PTSD 应用机器学习最常用的算法是处理分类问题的决策树（CART）、随机森林模型等集成算法、基于核的支持向量机以及延伸传统回归的正则化回归（lasso、ridge）算法等，均属于监督式机器学习。随机森林、支持向量机都可实现数据的分类和回归，但支持向量机泛化能力更优，内存要求高，训练时间长，适用于小样本数据，随机森林无需进行特征选择，计算速度快，在很多数据集上表现良好，普适性较强，适合处理高维数据，而对于样本较小的数据集，分类效果不佳。因此我们发现虽然有研究同时使用多种算法，但仅限于监督式学习中的算法，与广泛的机器学习算法相比，略显单一。

# 5.2机器学习应用于儿童PTSD领域的优势

目前,临床上对儿童 PTSD 的识别诊断主要基于各类量表中PTSD 诊断标准,结合患儿、其父母的访谈情况及医生诊疗经验进行。而影响儿童PTSD 发生与转归因素的识别主要依靠传统回归方法。相较于经验诊断和传统统计方法，机器学习的优势集中体现在四个方面。

首先，机器学习捕获、分析儿童PTSD 影响因素的能力更强。传统的统计学方法如多元线性回归所确定的预测因子单个预测能力较弱，因此需要建立基于多个预测因子的多元线性回归模型。PTSD 的发生与其转归的影响因素较多，如创伤后个体因素、心理社会学因素、精神病理学因素等(Trickey et al.,2012); (Rangaprakash et al.,2018; Zhang et al.,2016)。但是传统统计学方法同时处理大量因子易降低每个预测变量的准确性，不能对数据进行充分的挖掘，难以对PTSD的发生与转归过程做到很好的预测。为保持传统线性模型的稳定性和可重复性，预测因子的数量相对于样本量必须保持较小，因子子集之间不能高度相关，在变量的交互分析上也有相当大的限制。此外，影响儿童PTSD发生和转归的各因素之间存在交互影响，传统的加法模型不能识别数据中更复杂的非线性模式(Breiman，2001；Chekroud et al,2021)。利用机器学习可以捕获所有相关预测因子的同时效应(Saxe et al.,2017)，构建出准确预测儿童PTSD 识别和分类的模型，可以根据包含多种变量和小样本量的数据实现可靠因果关系推断(Saxe etal.,2017)，更好的分析儿童PTSD 这类复杂、影响因素众多的疾病。

其次，机器学习的建模过程和计算原理区别于传统方法。机器学习研究将重点转移到模型的整体预测能力上，可以通过直接针对感兴趣的现象建立预测分类模型并测试这些模型的稳定性和准确性，而无需数据生成模型和系数估计(Chekroud et al.,2021)，从而避免了估算准确的可变系数和对数据生成过程建模的误差(Saxe et al.，2017)。在分析影响儿童 PTSD的风险因素时，机器学习并不像传统回归方法一样以方差分析来识别关系，对变量和样本量的要求不高，不会因为变量之间的共线性影响导致运算错误概率的增加，在匹配疾病的多病因和异质性结果方面的能力更好(Galatzer-Levy et al.,2014)。机器学习充分考虑所研究对象的特征，从而产生更准确的预测结果，但以往建模是以实现结果均衡为目的，在一定程度上并不符合研究对象特征，也需要更多的指标辅助验证和判别真实结果。机器学习不仅仅作为一个用于组合和探索更大数据集的分析工具，也标志着研究范式的转变(Chekroud et al,2021)。

第三，对于研究产出，机器学习可以做到在非实验数据集中启用因果推理。当数据不是来自随机对照实验时，传统的广义线性模型揭示因果关系的能力有限，然而在有关创伤危险因素的研究中，实验设计是违背伦理的，在这种情况下，机器学习方法也能在非实验数据集中进行因果关系的检验。

最后，与人为诊断的方式相比，机器学习综合判断多种影响因素，特征存储、提取能力和速度比人工更强更快，分析数据更为客观。通过人为诊断和识别儿童PTSD 方法容易受到主观理解偏差的影响。儿童自述症状不清、父母代替回答过程中出现的转述误差都会影响诊断的准确性。机器学习的方法或许更适用于人群的PTSD 识别。当灾难（如自然灾害、疫情等）作为一种群体心理健康的应激源导致了人群PTSD，机器学习可以迅速高效的筛选出潜在或高危PTSD 患者，节约了人力成本，也可以避免情绪传递给救助人员带来心理创伤。随后及时为这部分人群提供早期心理干预，则有助于节约医疗资源。

# 5.3启示及前景展望

从理论上，第一，机器学习突破了传统回归方法可纳入变量有限性的局限，降低了对变量的要求，减少了前提假设的限制。算法上的非线性拟合更符合儿童PTSD 的实际情况，提高了预测的准确率。第二，机器学习为预测儿童 PTSD 的模型构建打开了新思路。为适应PTSD 的特征机器学习需构建新模型，推动了更多算法的研发和验证，而随着数据量的累积将加速理论模型应用于实践的进程。第三，机器学习弥补了传统模型中外部验证不足的问题。模型预测的方法虽然在概念预测中表现出较高的准确性(Galatzer-Levy et al.，2014，2017;Karstoft et al.,2015)，但需要外部验证作为评估预测模型外推的黄金标准，而在PTSD 预测模型的文献中关于外部验证的文献较为缺乏，因此阻碍了此类方法在临床中的应用(Altmanet al.,2009; Schultebrauck & Galatzer-Levy,2019; Schultebraucks, Shalev, et al.,2020)。机器学习自然的将数据集分为训练集与验证集，同时包含了模型的内外部验证，提高了理论到临床应用的速度。

从实践上，机器学习应用于临床将有助于节约人力成本和医疗资源。其快速准确进行转轨预测的优势可以避免重复就医，辅助医生确诊和判断病情。同时机器学习应用于PTSD 的早期预测和干预降低了后期健康结果恶化的风险。尤其对于儿童而言，机器学习应用于PTSD 的诊断可以减少其对生命历程的影响，降低PTSD 的长期疾病负担。此外，机器学习若应用于人群的心理健康干预还对提高群体健康水平有显著效益。例如自然灾害的发生常伴随人群出现PTSD症状，而缺乏心理专家的有效干预措施会导致精神健康状况被忽视，引入机器学习方法将大范围解决人群PTSD 的识别，或能减少因人群的健康损失带来的各种社会问题。

综上，虽然机器学习在儿童PTSD 识别和转归预测上有一定的方法学优势，但预测儿童PTSD 的指标本身存在一些问题，也会成为机器学习的发展的制约或机遇。首先，收集预测指标困难。预测PTSD 的指标数据主要来源于医院的临床问诊和患者自述，源于医院的指标数据相对较多，应用临床的指标与患者的自我报告相比，预测结果更为准确(Schultebraucks,Shalev,etal.,2020)。然而现实情况是突发创伤事件发生后少有医疗机构及时的收集数据，研究表明仅有 $7 \%$ 的一级创伤中心进行了PTSD 的筛查工作(Love& Zatzick,2014)。因此在预测PTSD 时，收集指标数据成为预测的首要阻碍。此外，收集指标过程中出现的过失误差、系统误差也可能存在。尽管机器学习无法解决数据来源的问题，但如何提高其预测能力，减少过失误差和降低系统误差需要进一步探讨。第二，确认准确的预测指标困难。尽管导致PTSD的因素多种多样，但并非所有的因素都可以作为有效的预测指标，例如患者自我报告的心理压力就还未被纳入医疗诊断的标准(Schultebraucks,Shalev,et al.,2020)。所以准确识别、确认风险因素与PTSD的关系，将其作为判断指标仍需要实证研究的反复验证。这一过程是漫长而不确定的，也将导致预测成本的增加。如何应用机器学习强大的数据处理能力，通过不断重复的高速运算，快速的排除无关因素，构建更为准确的医疗诊断预测指标体系或许会成为今后值得研究的方向。第三，潜在预测指标可能被遗漏。PTSD 的复杂性决定了不能仅依靠某个独立指标进行预测，但与之相关的生理、心理方面的指标又是繁杂的，如生物应激响应、免疫反应、威胁感知和心理社会决定因素等(Hinrichs et al.,2019; Michopoulos et al.,2017;Schultebraucks et al.,2019; Shalev et al.,2017)，如何选择指标，避免遗漏潜在指标造成预测偏倚有待进一步研究。

机器学习作为数据预测和分类的有效方法，应用于PTSD 领域需要随着PTSD 研究的深入不断更新。当出现越来越多新类型的PTSD，如DSM-5中正式确认的分离性PTSD(Haganet al.,2018)，机器学习的新算法迭代能否满足所出现疾病的识别和诊断需求，决定了临床应用的可行性和效率。目前机器学习的诊断准确率并不稳定，依然需要临床诊断的金标准来检验。在收集原始数据时也是通过问诊、问卷调研等基础传统的方式，而随着机器学习模型和预测指标的不断精准完善，相信机器学习预测准确性很有可能超越医生诊断，成为新的金标准。同时物联网等新型科技和智慧医疗也在持续发展，未来也有机会实现从数据收集到分析预测全过程的技术升级，帮助人们更高效便捷的进行疾病的科学预测。与此同时对深度学习的持续性探索以及大数据环境都为儿童 PTSD 的诊断和识别提供了良好的发展环境和进步空间。深度学习是机器学习中较新的研究方向，其中进化机器学习（Evolutionary MachineLearning）应用于精神健康领域解决了很多复杂的模式识别难题，推动了人工智能相关技术的进步，也很可能成为未来儿童PTSD 领域研究的突破口。另一方面大数据时代的海量信息也为机器学习的应用提供了前提，将有助于儿童PTSD 诊断和识别技术尽快投入临床实践，持续发展。

# 6.总结

目前机器学习已经渗透到普通人的生活之中，也正在不断与大数据技术以及其他学科互相融合、交叉发展，如天气预测、搜索引擎、营销策略等都应用了机器学习技术进行数据分析，逐渐改变了人们的生活方式。将机器学习算法应用于儿童PTSD领域，可以预测PTSD的发生发展情况以及可能的长期结局。其优势是可以减少人为诊断儿童PTSD 的主观性，并且效率较高，适合大范围内的筛查工作，节约长期跟踪随访所需要的人力物力资源，在此基础上提供预防性干预策略。然而机器学习应用于儿童PTSD 领域还处于探索阶段，对最优模型以及变量的选择还需要更多的证据支持，算法也相对单一，导致预测结果的准确性有待提高。随着未来我国医疗大健康产业的发展，机器学习作为方法学工具在精神病学领域将发挥巨大的潜力。相信未来儿童PTSD的机器学习实践应用也会迅速发展，为早期预防或治疗儿童 PTSD 提供指导建议。

# 参考文献

周志华.(2018)．机器学习．清华大学出版社.   
Alisic,E., Zalta,A. K., Van Wesel,F.,Larsen,S.E.,Hafstad, G.S.,Hassanpour, K.,& Smid, G.E.(2014). Rates of post-traumatic stress disorder in trauma-exposed children and adolescents: Meta-analysis. InBritishJournalofPsychiatry (Vol.204，Issue5，pp.335-340). https://doi.org/10.1192/bjp.bp.113.131227   
Al-Sahaf,H.,Bi, Y., Chen,Q.,Lensen,A., Mei, Y.,Sun,Y., Tran, B., Xue,B.,& Zhang,M. (2019).A survey on evolutionary machine learning. Journal of the Royal Society of New Zealand, 49(2), 205-228. https://doi.0rg/10.1080/03036758.2019.1609052   
Altman,D.G., Vergouwe, Y.,Royston, P.,& Moons,K. G. M. (20o9). Prognosis and prognostic research: Validating a prognostic model. British MedicalJournal,338, b605. https://doi.org/10.1136/bmj.b605   
Ammerman,R.T.,Scheiber,F.A.,Peugh,J.L.,Messer,E.P., Van Ginkel,J.B.,& Putnam,F.W.(2019). Interpersonal trauma and suicide attmpts in low-income depressed mothers in home visiting. Child Abuse and Neglect, 97,104126. https://doi.org/10.1016/j.chiabu.2019.104126   
Bonanno, G.A. (2004). Loss,Trauma,and Human Resilience: Have We Underestimated the Human Capacity to Thrive after Extremely Aversive Events? American Psychologist, 59(1),20-28. https://doi.0rg/10.1037/0003-066X.59.1.20   
Bonanno，G. A.，& Diminich，E.D. (2013). Annual research review: Positive adjustment to adversity—Trajectories of minimal-impact resilience and emergent resilience. Journal of Child Psychology and PsychiatryandAlliedDisciplines， 54(4)， 378-401. https://doi.org/10.1111/jcpp.12021   
Bonanno, G.A., Westphal, M.,& Mancini, A. D. (2011). Resilience to loss and potential trauma. Annual Review of Clinical Psychology, 7, 511-535. https://doi.org/10.1146/annurev-clinpsy-032210-104526   
Breiman,L. (20o1). Statistical Modeling: The Two Cultures (with comments and a rejoinder by the author). Statistical Science,16(3),199-215. https://doi.org/10.1214/ss/1009213726   
Brownlee, J. (2016). Master Machine Learning Algorithms Discover How They Work and Implement Them From Scratch. In Machine Learning Mastery With Python.   
Bryant,R. A., Nickerson, A., Creamer, M., O'Donnel, M.,Forbes,D., Galatzer-Levy, I., McFarlane,A. C., & Silove,D. (2015). Trajectory of post-traumatic stress following traumatic injury: 6-year follow-up. British Journal of Psychiatry, 206(5), 417-423. https://doi.org/10.1192/bjp.bp.114.145516   
Cancilliere, M. K., Kavanaugh, B.,Bodzy, M., & Holer, K. (2021).Psychiatric Outcomes of Childhood Maltreatment: A Retrospective Chart Review from a Children's Psychiatric Inpatient Program. Child Psychiatry & Human Development,published. https://doi.org/10.1007/s10578-021-01209-3   
Chekroud, A.M.,Bondar,J.,Delgadilo,J.,Doherty, G.,Wasil,A.,Fokkema,.,Cohen,.,Belgrave,D., DeRubeis,R., Iniesta, R., Dwyer, D.,& Choi, K. (2021). The promise of machine learning in predictingtreatmentoutcomesinpsychiatry.World Psychiatry， 20(2)， 154-170. https://doi.org/10.1002/wps.20882   
Cheng, J., Liang, Y. M., Zhou, Y. Y., Eli, B., & Liu, Z. K. (2019). Trajectories of PTSD symptoms among children who survived the Lushan earthquake: A four-year longitudinal study. Journal of Affective Disorders,252(1), 421-427. https://doi.0rg/10.1016/j.jad.2019.04.047   
De Young,A. C.，& Landolt, M. A. (2018). PTSD in Children Below the Age of 6 Years. Current Psychiatry Reports,20(11), 97. htps://doi.0rg/10.1007/s11920-018-0966-z   
G, B.,F, C.,& Cecchi G A, et al. (2015). Automated analysis of free speech predicts psychosis onset in high-risk youths.Nature Partner Journals Schizophrenia,15030,1-7.   
Galatzer-Levy,I. R.，& Bryant, R.A. (2013). 636,120 Ways to Have Posttraumatic Stress Disorder. Perspectives on Psychological Science, 8(6), 651-662. htps://doi.org/10.1177/1745691613504115   
Galatzer-Levy, I. R., Huang, S. H.,& Bonanno, G.A. (2018). Trajectories of resilience and dysfunction folowing potential trauma: A review and statistical evaluation. Clinical Psychology Review, 63, 41-55. https://doi.org/10.1016/j.cpr.2018.05.008   
Galatzer-Levy, I. R., Karstoft, K.-I.， Statnikov,A.,& Shalev, A. Y. (2014). Quantitative forecasting of PTSD from early trauma responses: A Machine Learning application. Journal of Psychiatric Research, 59, 68-76. htps://doi.org/10.1016/j.jpsychires.2014.08.017   
Galatzer-Levy, I. R.， Ma, S., Statnikov,A., Yehuda,R.,& Shalev, A. Y. (2017). Utilization of machine learning for prediction of post-traumatic stres: A re-examination of cortisol in the prediction and pathwaystonon-remitingPTSD.TranslationalPsychiatry，7(3), e1070. https://doi.0rg/10.1038/tp.2017.38   
Ge,F.,Li, Y., Yuan, M., Zhang, J.,& Zhang, W. (2020). Identifying predictors of probable posttraumatic stress disorder in children and adolescents with earthquake exposure: A longitudinal study using a machinelearningapproach. JournalofAffectiveDisorders，264， 483-493. https://doi.0rg/10.1016/j.jad.2019.11.079   
Gokten, E. S., & Uyulan, C. (021). Prediction of the development of depression and post-traumatic stress disorder in sexually abused children using a random forest classifier. Journal of Affective Disorders,279,256-265. htps://doi.0rg/10.1016/j.jad.2020.10.006   
Hagan,M. J., Gentry, M., Ippen, C.G.,& Lieberman, A.F. (2018). PTSD with and without dissociation in young children exposed to interpersonal trauma. Journal of Affective Disorders, 227, 536-541. https://doi.org/10.1016/j.jad.2017.11.070   
Hiller,R. M., Meiser-Stedman,R.,Fearon,P.,Lobo,S., McKinon, A.,Fraser, A.,& Haligan,S.L.(2016). Research Review: Changes in the prevalence and symptom severity of child post-traumatic stress disorder in the year following trauma - a meta-analytic study. Journal of Child Psychology and Psychiatry and Allied Disciplines, 57(8), 884-898. https://doi.org/10.111/jcpp.12566   
Hinrichs,R.， van Rooij, S. J. H.，Michopoulos,V., Schultebraucks, K.， Winters,S.，Maples-Keler, J., Rothbaum, A. O., Stevens, J. S., Galatzer-Levy, I., Rothbaum, B. O., Ressler, K. J., & Jovanovic, T. (2019). Increased Skin Conductance Response in the Immediate Aftermath of Trauma Predicts PTSD Risk. Chronic Stress,3, 2470547019844441. htps://doi.0rg/10.1177/2470547019844441   
Jensen,T. K. Skar,A. M. S., Andersson, E. S.,& Birkeland,M. S. (2019). Long-term mental health in unaccompanied refugee minors: Pre- and post-flight predictors. European Child and Adolescent Psychiatry,28(12),1671-1682. https://doi.0rg/10.1007/s00787-019-01340-6   
Jensen，T. K.， Skardalsmo,E.B. M.，& Fjermestad, K. W. (2014).Development of mental health problems-A follow-up study of unaccompanied refugee minors. Child and Adolescent Psychiatry and Mental Health, 8(1),29-39. https://doi.0rg/10.1186/1753-2000-8-29   
Jones,D. T. (2019). Setting the standards for machine learning in biology. Nature Reviews Molecular Cell Biology,20, 659-660. https://doi.0rg/10.1038/s41580-019-0176-5   
Karstoft, K.-1., Galatzer-Levy,I. R., Statnikov, A.,Li, Z.,& Shalev, A. Y. (2015). Bridging a translational gap: Using machine learning to improve the prediction of PTSD. BioMed Central Psychiatry, 15, 30. https://doi.0rg/10.1186/s12888-015-0399-8   
Kelly,J., Gooding,P.,，Pratt,D.,Ainsworth,J.，Welford,M.，& Tarrier,N. (2012).Intelligent real-time therapy: Harnessing the power of machine learning to optimise the delivery of momentary cognitive behavioural interventions. Journal ofMental Health, 21(4)， 404-414. https://doi.0rg/10.3109/09638237.2011.638001   
Koprowski, R.,& Foster, K. R. (2018). Machine learning and medicine: Book review and commentary. Biomedical Engineering Online,17(1),17. https://doi.org/10.1186/s12938-018-0449-9   
Lai, B. S., Lewis, R., Livings, M. S., La Greca,A. M.,& Esnard, A.-M. (2017). Postraumatic Stress Symptom Trajectories Among Children After Disaster Exposure: A Review. Journal of Traumatic Stress,30(6),571-582. https://doi.0rg/10.1002/jts.22242   
Li,L., Pan, N., Zhang,L.,Lui, S. u, Huang, X., Xu, X., Wang, S.,Lei, D.u,Li,L., Kemp, G. J.,& Gong, Q.(2020). Hippocampal subfield alterations in pediatric patients with post-traumatic stress disorder.SocialCognitiveand Affective Neuroscience, 16(5-6), 1-11. https://doi.org/10.1093/scan/nsaa162   
Love,J., & Zatzick, D. (2014). Screening and Intervention for Comorbid Substance Disorders,PTSD, Depression, and Suicide: A Trauma Center Survey. Psychiatric Services， 65()， 918-923. https://doi.0rg/10.1176/appi.ps.201300399   
Masten, A. S.,& Narayan, A. J. (2012). Child development in the context of disaster, war, and terrorism: Pathwaysofrisk and resilience. Annual Review of Psychology， 63， 227-257. https://doi.org/10.1146/annurev-psych-120710-100356   
Michopoulos, V.,Powers,A., Gillespie, C.F.,Ressler, K.J.,& Jovanovic,T. (2017). Inflammation in Fearand Anxiety-Based Disorders: PTSD, GAD，and Beyond. Neuropsychopharmacology, 42(1), 254-270. htps://doi.org/10.1038/npp.2016.146   
Morina,N.,& Sterr, T. N. (2019). Lack of evidence for the eficacy of psychotherapies for PTSD and depression in child and adolescentrefugees. World Psychiatry， 18(1)， 107-108. https://doi.0rg/10.1002/wps.20596   
Mueller, A., Candrian, G., Kropotov, J. D., Ponomarev, V.A.,& Baschera, G.-M. (2010). Classification of ADHD patients on the basis of independent ERP components using a machine learning system. Nonlinear Biomedical Physics, 4(S1), 1-12. htps://doi.0rg/10.1186/1753-4631-4-s1-s1   
Rajkomar, A.,Dean,J.,& Kohane,I. (2019). Machine Learning in Medicine. The New England Journal of Medicine, 380(14),1347-1358.   
Ramos-Lima,L.F., Waikamp, V., Antonelli-Salgado, T., Passos,I. C.,& Freitas,L. H. M. (202O). The use of machine learning techniques in trauma-related disorders: A systematic review. Journal of Psychiatric Research,121,159-172. htps://doi.org/10.1016/j.jpsychires.2019.12.001   
Rangaprakash,D., Dretsch,M.N., Venkataraman, A., Katz, J. S., Denney,T. S.J., & Deshpande, G. (2018). Identifying disease foci from static and dynamic effective connectivity networks: Ilustration in soldiers with trauma. Human Brain Mapping,39(1),264-287. https://doi.org/10.1002/hbm.23841   
Saxe,G.N.，Ma, S.，Ren，J.，& Aliferis，C. (2017). Machine learning methods to predict child posttraumatic stress: A proof of concept study. BioMed Central Psychiatry， 17(1)， 223. https://doi.0rg/10.1186/s12888-017-1384-1   
Scheeringa, M. S., Wright,M.J., Hunt, J.P.,& Zeanah, C.H. (2006). Factors affecting the diagnosis and prediction of PTSD symptomatology in children and adolescents. American Journal of Psychiatry, 163(4), 644-651. https://doi.0rg/10.1176/ajp.2006.163.4.644   
Schultebrauck, K.,& Galatzer-Levy, I.R. (2019). Machine Learning for Prediction of Postraumatic Stress and Resilience Following Trauma: An Overview of Basic Concepts and Recent Advances. Journal of Traumatic Stress,32, 215-225.   
Schultebraucks, K., Rombold, F.，Wingenfeld, K., Hellmann-Regen, J., Otte, C.，& Roepke, S. (2019). Heightened biological stress response during exposure to a trauma film predicts an increase in intrusivememories.JournalofAbnormalPsychology，128(7)，645-657. https://doi.0rg/10.1037/abn0000440   
Schultebraucks， K.， Shalev， A.Y.，Michopoulos，V.， Grudzen， C.R.， Shin， S.-M.， Stevens,J.S., Maples-Keller, J.L., Jovanovic,T., Bonanno, G. A., Rothbaum, B. O., Marmar, C.R., Nemeroff, C.B.，Ressler, K. J.，& Galatzer-Levy, I. R. (202O). A validated predictive algorithm of post-traumatic stress course following emergency department admission after a traumatic stressor. Nature Medicine, 26(7),1084-1088. htps://doi.0rg/10.1038/s41591-020-0951-z   
Schultebraucks,K.， Yadav,V.， Shalev,A. Y.，Bonanno,G. A.，& Galatzer-Levy, I. R. (2020). Deep learning-based classification of postraumatic stress disorder and depressionfolowing trauma utilizing visual and auditory markers of arousal and mood. Psychological Medicine,1-11. https://doi.0rg/10.1017/S0033291720002718   
Shalev,A.,Liberzon, I.,& Marmar, C. (2017). Post-Traumatic Stress Disorder. New England Journal of Medicine,376(25),2459-2469. htps://doi.0rg/10.1056/NEJMra1612499   
Sumathi, Ms., & B.,Dr. (2016). Prediction of Mental Health Problems Among Children Using Machine Learning Techniques. International Journal of Advanced Computer Science and Applications,7(1), 552-557. https://doi.0rg/10.14569/ijacsa.2016.070176   
Takahashi, Y., Yoshizoe, K.,Ueki,M.,Tamiya, G., Zhiqian, Y., Utsumi, Y., Sakuma,A., Tsuda, K., Hozawa, A.,Tsuji, I.,& Tomita, H. (202O). Machine learning to reveal hidden risk combinations for the trajectory of posttraumatic stress disorder symptoms. Scientific Reports， 10(1)， 21726. https://doi.0rg/10.1038/s41598-020-78966-z   
Trickey,D., Siddaway,A.P.,Meiser-Stedman,R.,Serpel,L.,&Field,A.P. (2012). A meta-analysis of risk factors for post-traumatic stress disorder in children and adolescents. Clinical Psychology Review, 32(2),122-138. https://doi.0rg/10.1016/j.cpr.2011.12.001   
Ucuz,I.，Ari，A.， Ozcan, O.O.， Topaktas, O.， Sarraf, M.，& Dogan, O. (2020). Estimation of the Development of Depression and PTSD in Children Exposed to Sexual Abuse and Development of Decision Support Systems by Using Artificial Intelligence. Journal of Child Sexual Abuse,1-13. https://doi.0rg/10.1080/10538712.2020.1841350   
Weathers,F.W., Litz,B.T., Keane,T.M., Palmieri, P.A., Marx, B.P., & Schnurr, P.P. (2013). The PTSD ChecklistforDSM-5(PCL-5). NationalCenterforPTSD， 5(August)， 2002. https://doi.0rg/10.1037/t02622-000   
Worthington, M. A., Mandavia, A., & Richardson-Vejlgaard, R. (2020). Prospective prediction of PTSD diagnosis in a nationally representative sample using machine learning. BioMed Central Psychiatry,20(1), 532. htps://oi.0rg/10.1186/s12888-020-02933-1   
Yehuda,R.,Halligan, S.L.,& Grossman, R. (2001). Childhood trauma and risk for PTSD: Relationship to intergenerational effects of trauma, parental PTSD,and cortisol excretion. Development and Psychopathology,13(3), 733-753. htps://doi.0rg/10.1017/S0954579401003170   
Zandvakili,A., Philip, N. S., Jones, S.R., Tyrka,A. R., Greenberg, B.D.,& Carpenter,L.L. (2019). Use of machine learning in predicting clinical response to transcranial magnetic stimulation in comorbidpostraumaticstressdisorderandmajordepression:Arestingstate

electroencephalographystudy.JournalofAffective Disorders, 252(1), 47-54. https://doi.0rg/10.1016/j.jad.2019.03.077 Zhang,Q.,Wu, Q., Zhu, H.,He,L., Huang,H., Zhang, J.,& Zhang, W. (2016). Multimodal MRI-based classification of trauma survivors with and without post-traumatic stress disorder. Frontiers in Neuroscience,10(JUN), 1-9.https://doi.org/10.3389/fnins.2016.00292

表2.机器学习在儿童PTSD诊断和识别中的应用  

<html><body><table><tr><td rowspan="2">时间</td><td rowspan="2">国家</td><td colspan="3">题目</td><td rowspan="2">样本量</td><td rowspan="2">年龄</td><td rowspan="2">主要变量</td><td rowspan="2">变量 数量</td><td rowspan="2">因变量测量</td><td rowspan="2">分类器</td><td rowspan="2">训练方法</td><td rowspan="2">评价指标</td></tr><tr><td>Machine learning methods to predict child</td><td></td><td></td></tr><tr><td rowspan="2">2017</td><td rowspan="2">美国</td><td>posttraumaticstress: study(Saxe et al., 2017)</td><td>a proof-of-concept</td><td>165</td><td>7~18</td><td>儿童发展、人口统计学信息、父母症状、 压力、基因、神经内分泌和心理生理反应、 受伤程度、儿童症状和功能</td><td></td><td>105个</td><td>加州大学洛杉矶 分校创伤后应激 障碍反应指数</td><td>SVM;RF; Lasso回 归</td><td>5折交叉验证</td><td>AUC=0.75</td></tr><tr><td>Identifying predictors of probable posttraumatic</td><td>stress disorder in children and adolescents with</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>00: 2020</td><td>中国</td><td>2020)</td><td>Hippocampal subfield alterations in pediatric</td><td></td><td>2099</td><td>8~19</td><td>人口统计学信息、地震经历、睡眠、心情、 躯体症状和日常功能 静息态功能磁共振成像：海马亚区-</td><td>5个 方面</td><td>修订版儿童事件 影响量表</td><td>CART</td><td>5折交叉验证</td><td>AUC= 0.66 ~0.80</td></tr><tr><td>ZOZ:AIY 2020</td><td>中国</td><td></td><td>Estimation of the Development of Depression</td><td></td><td>46 11~16</td><td></td><td>CA1、CA2、CA3、CA4、齿状回、下托</td><td>1个方</td><td>创伤后应激障碍</td><td>RF</td><td>5折交叉验证</td><td>AUC= 0.65</td></tr><tr><td>puw 2020 5</td><td>土耳其</td><td>et al., 2020)</td><td>and PTSD in Children Exposed to Sexual Abuse and Development of Decision Support Systems by Using Artificial Intelligence(Ucuz</td><td></td><td>170 5~17</td><td></td><td>年龄等人口统计学信息、虐待类型、虐待 次数等虐待相关信息、事件报告者</td><td>10个</td><td>精神障碍诊断和 统计手册</td><td>ANNs</td><td>3折交叉验证</td><td>准确度： 99.2%</td></tr><tr><td>2020</td><td>土耳其</td><td>classifier(Gokten & Uyulan, 2021)</td><td>Prediction of the development of depression and post-traumatic stress disorder in sexually abused children usinga randomforest</td><td></td><td>均数 372 13.77</td><td></td><td>性别年龄等人口统计学信息、吸烟饮酒等 生活习惯信息、被虐待的经历程度信息、 精神状态</td><td>20个</td><td>精神障碍诊断和 统计手册</td><td>RF</td><td>10 折交叉验证</td><td>AUC=0.76</td></tr></table></body></html>

注：RF：domsi人工神经网络