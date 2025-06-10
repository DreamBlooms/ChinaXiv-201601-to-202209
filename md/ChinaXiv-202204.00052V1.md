# 基于商品描述文案的点击预测模型

黄皓炫，盛武

(安徽理工大学 经济与管理学院，安徽 淮南 232000)

摘要：为了预测商品描述文案中商品特征对点击的影响，量化分析用户的消费行为特征及缓解冷启动问题，建立了一种基于LDA模型和文本情感分析的点击预测模型。该模型基于LDA主题模型对商品描述词的分类筛选，对构成词进行情感分析，构建特征向量以表示用户对商品各特征的情感倾向，并通过LightGBM算法进行对点击的预测。模型可以将非结构化文本数据转换为结构化数据，量化用户对商品不同特征的兴趣倾向，并利用不同商品的相似特征缓解冷启动问题。实验结果表明模型有效提高了点击预测效果并能缓解冷启动问题。

关键词：LightGBM；点击预测；文本情感分析；LDA主题模型；冷启动； 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.01.0025

Click prediction model based on product description

Huang Haoxuan, Sheng Wu† (Dept.of Economics &Management,Anhui University OfScience& Technology,Huainan Anhui 2320oo,China)

Abstract: Inorder to predict the impact ofcommoditycharacteristicsonclick incommoditydescriptioncopy,quantitatively analyze users'consumption behavior characteristicsandaleviate thecold start problem,this paper established a click prediction model based on LDAmodeland text emotion analysis.Based on the LDA topic model,the model classifies and screns the commodity description words,analyzes the emotion ofthe constituent words,constructs the feature vector to representheuser'semotional tendencytothecharacteristicsofthecommodity,and predicts theclick throughthelightgbm algorithm.The modelcan transformunstructured text datainto structured data，quantifyusers'interest indifferent characteristicsof goods,and use the similarcharacteristicsof diferent goods to allviate thecold start problem.The experimentalrsultsshowthat themodelcaneffctively improvetheclickpredictioneffctandallviate thecoldstartproblem.

Key words: lightgbm; click prediction; text sentiment analysis; LDA topic model; cold start;

# 0 引言

网购平台上有很多商家等撰写的商品描述文案，其中往往包括了对商品的外观、尺寸、颜色、功能、打折信息等多方面多角度的详细描写，体现了行业从事者对消费者核心需求的思考、对同行及自己产品卖点特征的判断。产品的属性特征是多方面的，对消费者的吸引力也各有区别，有研究表明，商品描述的差异会影响消费者的购物意愿[1,2]。通过研究商品描述及其商品点击量的不同，可以了解到消费者对商品不同属性点的偏好和需求的差异。相比能够直接体现用户对商品主观感受的购物后的用户评价，购物前的商品描述更能反映消费者的消费冲动，体现了消费者的核心需求。对商品描述的研究，不仅可以为消费者更高效获取商品信息提供支持，也能为商家改善商品性能、研发新产品、调整商品卖点宣传提供依据。

目前国内外专门针对电商领域的中文商品描述的研究比较少，与此研究问题涉及内容相近的研究主要有计算广告领域的点击率预测研究、推荐系统领域的评分预测研究等。点击率预测是计算广告领域中一个重要的研究内容[3]。因为按点击付费是互联网广告的主要计价模型之一，从而通过对点击率的预测研究，可以提高广告主的投资回报率的同时，最大化用户对展示广告的满意程度[4]。点击率预测模型主要分为基于历史日志的预估模型和基于稀疏数据的预估模型。前者基于广告的丰富的历史数据(如广告的位置、内容等)，然后通过逻辑回归、贝叶斯网络等算法从而进行对点击率的预测[5-7].但这些方法的缺点是难以处理稀疏数据型的广告或新广告，因此诞生了后者如基于层次聚类分析、相似项、因子分解机等方法的预估模型[8-10]。文献[4]就从广告语义的角度出发，通过LDA 主题模型以挖掘广告文本中的主题，以广告与主题的相关性基于FM模型建立了点击率预测模型，证实了文本语义和点击的相关性。

推荐系统是在大量数据中筛选出最符合用户需求偏好的结果给用户的一种系统[11,12]。其中，协同推荐算法作为推荐系统中最主流的算法之一，主要通过用户对项目的评分来研究用户和项目之间的关联进行预测[13]。不过，早期的推荐系统算法主要将商家视为一个商品，通过寻找相似商品或相似用户进行推荐。而随着互联网的发展、社交网络的兴起，用户和商户的互动在不断增加，评论信息数量不断攀升，文献[14]通过分析用户的评论建立评分矩阵，提出了一种基于高斯模型的优化算法来研究用户在商品不同方面的偏好。而文献[15]从常用词或形容词的角度建立词袋的角度构建评分预测模型，文献[16]则通过LDA主题模型提取评论的主题特征分布作为自变量构建评分预测模型。这些方法根据对用户评论文本的分析处理，探究了文本信息与评分的关联性，从评论文本语义的角度构建了评分预测模型。针对如何进一步提高评分预测的精度，有学者通过融合其他因素或方法来解决这个问题，并获得了良好的效果。文献[17]提出结合融合元数据和评分数据构建特征变量进而进行对评分的预测。文献[18则基于文本情感分析，对文本数据进行情绪挖掘与分析，从而提取文本中的主要观点倾向，将其作为自变量构建了评分预测模型，并取得了较好的评分预测效果。

在以上相关研究中，本文与文献[16,18]的研究内容较为接近，都是通过对非结构化文本信息进行分析从而构建预测模型。其中主要区别如下：

a)预测的目标不同。文献[16,18]都是根据评论构建评分预测模型，关注的是商品的售后口碑，本文则通过对商品描述文案不同特征的情感分析及LightGBM的可解释性构建点击模型，更关注商品中不同属性对消费者的吸引力影响。

b)特征量化角度不同。文献[16]通过使用LDA主题模型对文档词语进行主题分类，以分词出现的概率作为各特征的量化值。本文考虑到商品不同功能对消费者的吸引力不同，以商品各特征的情感倾向作为量化值，进一步提高了预测效果。

c)特征值的量化不同。在情感分析中，情感词的确立及情感权重的加权都是十分重要的。文献[19,20]通过基于评论文本中通用情感词典的积极情感词、消极情感词等情感词进行对整段评论的情感分析。但对于商品描述文案而言，文本主要由对商品的描述词语组成，以功能性词和积极情感词为主，通用的情感词典无法反映消费者的情感倾向。本文通过对商品特征进行分解，以与商品特征关联度较高的词作为情感词，再通过定义一个情感倾向计算公式作为消费者的情感倾向权重，因而具有普适性，不需要预定的情感词典，并可应用到不同商品的不同特征。

d)冷启动问题。传统协同过滤算法利用用户对商品的评分数据做推荐，存在数据稀疏性和冷启动问题[21]。本文基于对商品描述文本的挖掘，以用户商品的特征的偏好构建预测模型，因此可以通过具有相似特征的商品的数据模型来解决新商品缺乏数据的问题，从而缓解商品的冷启动问题。

基于此，本文通过分析商品描述文本及点击量的之间的关系，提出一种基于商品描述文案的点击预测模型。本文先利用jieba分词对商品描述文本进行词语级分割，以及通过停用词去除无关词语；然后利用LDA主题模型提取商品隐含特征，建立商品的属性分类；再基于各词汇的概率分布及权重量化文本情感值，将商品描述文本特征量化；最后通过LightGBM算法模型对商品的点击进行分类预测，分析商品各项特征对点击量的影响，挖掘用户的行为特征，并缓冷启动问题。

# 1基于商品描述的点击预测模型设计

本文基于LightGBM和文本情感分析的点击预测模型主要包括数据预处理、特征提取、文本情感分析、LightGBM模型训练和结果分析五个部分，模型框架如图1所示。

![](images/13196742661adb09e0e8c5e88d8fc711c33a695246c0fc2c33c3d09f1016d425.jpg)  
图1基于商品描述文案的点击预测模型  
Fig.1Click prediction model based on product description

# 1.1特征提取

不同于便于提取分析的结构化数据，商品描述文案的结构不规则，不符合预设的既定处理方法，属于非结构化数据。其中，在对原始语句进行中文分词和去除停用词后，本文通过LDA主题模型进行对词语的主题分类，从而获得研究目标的主题分类，以其作为目标的特征属性，再进行下一步分析。LDA主题模型由Blei、David M.、Ng,AndrewY.等于 2003年提出的，一种基于词袋模型的分析文档主题分布的一种三层贝叶斯概率模型[22]。它假设一篇文章具有K个主题，而每个主题又对应不同的词。因此文档的生成如下：

a)从狄利克雷分布 $\mathbf { \alpha } _ { \mathrm { ~ \mathfrak ~ { ~ a ~ } ~ } }$ 中取样生成文档i的主题分布 $\theta _ { i }$ ub）从主题的多项式分布 $\theta _ { i }$ 中取样生成文档i的第j个的  
主题 $z _ { i , j }$ 。c）从狄利克雷分布 $\beta$ 中取样生成主题 $z _ { i , j }$ 对应的词语分  
布 $\phi _ { z i , j }$ □d）从词语的多项式分布 $\phi _ { z i , j }$ 中取样生成最终词语 $\omega _ { i , j }$ 。

重复步骤b)\~d)从而生成文档i。

基于此，LDA主题模型通过逆向该过程，即给定文档i及词语，然后通过吉布斯采样(Gibbs sampling)方法反推其主题的分布。从而获得文档i的K个主题，及组成主题的词语组。根据文档划分的K个主题，商品 $I _ { i }$ 的特征词组可以记为$\eta _ { i }$ ， $\eta _ { i } = [ \eta _ { i 1 } , \eta _ { i 2 } , \cdots , \eta _ { i K } ]$ ．。其中， $\eta _ { i K }$ 表示商品 $I _ { i }$ 中与主题K的相关性词的组合，若不存在相关词，则 $\eta _ { i K }$ 为空集。其中，相关性词为与主题K相关性最高的前1000个词。模型结构如图2所示。

![](images/5be34c22ca1329ecb46e38400c6fa04fb91a51ec6a009fed35cb7ee44fb93f78.jpg)  
图2LDA 模型结构Fig. 2 LDA topic model

# 1.2文本情感分析及特征量化

文本情感分析，又称倾向性分析或意见挖掘，是通过计算、分析、归纳文本信息，从而获得其中的观点、情绪或倾向的过程。根据粒度细分的不同，可以分为篇章级、句子级和词语级三个层次，即对一篇文章、一个句子或一个词的情感倾向分析。本文在获得预处理后的文本后，把每个商品描述文案的点击量作为其对应的情感倾向，然后基于统计方法进行情感分析，从而获得词语的情感倾向。由于点击量分布的位置平均数靠左，峰度陡峭，数值范围跨度大，若直接取其词语的数学期望作为其情感倾向会导致高点击量的权重过大，因此取词语的点击量进行对数处理后的数学期望作为词语的情感倾向，点击量分布如图3所示。

最后，词语的情感倾向计算式(1)定义如下：

$$
\omega _ { t } = \frac { 1 } { V } \sum _ { \nu = 1 } ^ { V } \log _ { 1 0 } C _ { \nu }
$$

其中， ${ \bf \omega } _ { \infty } \mathrm { ~ } _ { \mathrm { ~ \large ~ ( 0 ~ ) ~ } _ { \mathrm { ~ t ~ } } }$ 表示词语t的情感值， $\mathrm { \Delta V }$ 表示包含词语t的商品描述文案的频数， $\mathbf { C } _ { \mathrm { v } }$ 表示第 $\mathbf { v }$ 个词语的点击量。

根据商品 $T _ { i }$ 的特征词组 $\eta _ { i }$ ，通过情感倾向计算公式则可获得商品 $I _ { i }$ 的特征向量 $\psi _ { i }$ ， $\psi _ { i } = [ \psi _ { i 1 } , \psi _ { i 2 } , . . . , \psi _ { i K } ]$ 。其中， $\psi _ { i K }$ 表

示商品 $I _ { i }$ 的第K个特征的特征值。特征值的计算公式(2)如下：

$$
\psi _ { i K } = { \sum } _ { 1 } ^ { T } w _ { t }
$$

其中，T表示相关词特征词组 $\eta _ { i K }$ 中的词语数。若特征词组 $\eta _ { i K }$ 中没有其特征词，则 $\psi _ { i K } = 0$ 。特征量化的过程如图4所示。

![](images/20b787a07914cedba3b9b554acc46c8475daab9c4edbf22b5671024735488d12.jpg)  
图3点击量分布图

![](images/9ea2b6639ded8d933ac1a2b59a1e759e2defe103b84c6d600826286040a21691.jpg)  
Fig.3 Click distribution   
图4特征量化过程  
Fig.4Feature quantization process   
图5主题词云图  
Fig.5Theme word cloud

# 1.3LightGBM 算法

在上述特征向量构建完成后，将特征向量作为自变量输入LightGBM模型。LightGBM模型是由微软于2017年开源的一种基于决策树的集成算法[23]。相较于 XGBoost、GBDT等算法在计算信息增益时需要扫描所有样本以找到最优划分点，LightGBM 模型采用了Histogram、GOSS、EFB 等算法方法，从而在面对大量数据或者特征维度很高的数据集时，具有更快的训练速度、更低的内存消耗和更好的准确率等优点。

Histogram 算法，通过对每个特征进行分箱(bin)处理，构造成一个宽度为k的直方图，在遍历数据时，根据分箱在直方图中累积统计量，根据遍历后的累计统计量，遍历寻找最优的分割点。

GOSS 算法，又名单边梯度采样算法，从减少样本的角度出发，根据信息增益的定义，排除大部分对信息增益影响小的梯度小的样本，保留梯度大的样本。GOSS算法会先将进行分裂的特征的所有取值按绝对值大小降序排序，选取绝对值最大的 $a ^ { * } 1 0 0 \%$ 个样本，再从剩余数据中随机选取 $6 ^ { * } 1 0 0 \%$ 的样本，并乘以一个常数，从而减少改变原数据集分布的影响。

EFB 算法，可以通过将一些特征进行融合绑定，从而降低特征数量。LightGBM的EFB算法将独立特征绑定转换为图着色问题，构建一个加权无向图，将所有特征视为图的各个定点，将不相互独立的特征用一条边链接，边的权重即为两个相互连接的特征的总冲突值，选取冲突小的特征融合，从而解决数据稀疏问题。

# 2 实验过程

# 2.1数据获取

本文实验数据取自阿里云天池实验室的公开数据“Product Description”[24]，以其中content 数据包中商品的描述文案及各类用户的点击量信息。本文所用点击量若无特别说明均为所有类型用户点击量之和，且缺失值视为0。其中，筛选以“外套”为关键词的数据作为研究对象，共包含34892条数据，其点击量分布如图3所示，其点击量百分位数如表1所示。

表1点击量百分位数  
Tab.1 Click percentile   

<html><body><table><tr><td>百分位 0%</td><td>25%</td><td>50%</td><td>75%</td><td>离群值线</td><td>100%</td></tr><tr><td>点击量 0.01</td><td>17.38</td><td>45.36</td><td>210.59</td><td>500.41</td><td>382745.58</td></tr></table></body></html>

根据样本的点击量分布，将点击量划分为2类：普通点击量，高点击量。由于商品的推荐算法大多以用户的点击率(CTR)为主要优化目标，这导致当某一类商品的点击率越高时，就会得到更多的曝光，因此点击量往往呈现两极分化的趋势。一般而言，曝光度低的商品的点击量主要与其商品的属性相关，而曝光度高的商品的点击量则容易受到各方面的影响。由此，本文对点击量的划分以离群值的判定为基础。离群值，也称溢出值，一般是指数据中与其他观察值具有明显不同特征的那些观察值。在此以四分位法划分离群值线，其计算式(3)如下：

$$
{ \cal O } u t l = { \cal Q } _ { 7 5 } + \left( { \cal Q } _ { 7 5 } - { \cal Q } _ { 2 5 } \right) \times 1 . 5 \ .
$$

其中， $\boldsymbol { Q } _ { 2 5 }$ ， $\varrho _ { \scriptscriptstyle 7 5 }$ 分别代表样本中点击量从小到大排列后的第$2 5 \%$ 和第 $7 5 \%$ 的值。记普通点击量为0，高点击量为1，则普通点击量的样本数为28667，高点击量的样本数为6225，比值为4.61，因此本样本为不平衡样本。

# 2.2数据处理及特征量化

本文在获取商品描述文本后，数据处理流程如下：

文本预处理。对商品描述文本进行预处理，对数据进行清洗，筛选出目标数据集；然后对商品描述文本信息进行jieba分词，将每个样本的文本转换为词组；再通过停用词表过滤掉不重要的词语，如“的”“啊”“！”等助词和符号。

特征提取。对预处理完的文本建立词典，使用LDA主题模型进行主题分析。对不同主题数进行分别迭代对比，其中，当主题数num_topics $\scriptstyle : = 6$ 时，主题比较清晰，主题分布如图5和图6所示。

夹克穿 时尚版型 后品牛仔设计 约 简首西装元素 羽绒 质优雅 少身 秋季节终天 保暖 衣服件穿冬季大衣 天氣秋 福 秋天搭穿 穿长搭配衣 时量件 打手衣品 款 个 衣裙显 连衣裙

如图5主题词云图所示，6个主题可大致标记为"风格”“设计”“保暖”“换季”“穿搭”“身材”6个特征。而在主题分布图中，圆圈表示不同的主题以及它们之间的距离，类似的主题看起来更近，而不同的主题更远，图中主题圆的相对大小对应于语料库中主题的相对频率。如图6主题分布图所示，6个主题的气泡较为分散，仅主题1和主题3有少量相交部分，证明该主题划分较为清晰独立，有较高的区分度。

![](images/e5cdf1d0a4bed4d08b738ba29d08753bbe3f1184698cd38f978a56fd25ce4515.jpg)  
图6主题词分布

特化。根据预处理后的分词构建词典，并按式(1)计算每个词的情感倾向，从而构建情感词典。对每个商品描述按主题进行特征分类，根据情感词典按式(2)对各特征值进行计算。其中，频数少于10，与主题关联度高低排名超过1000的词不参与特征的量化，以避免小概率事件的影响。部分特征量化后的商品描述如表2所示。

Tab.2Quantification of the characteristics of some product descriptions   

<html><body><table><tr><td>序号</td><td>描述文案</td><td>特征1</td><td>特征2</td><td>特征3</td><td>特征4</td><td>特征5</td><td>特征6</td></tr><tr><td>1</td><td>理由，深谱，时髦,……</td><td>23.9</td><td>16.9</td><td>30.1</td><td>18.1</td><td>26.2</td><td>25.9</td></tr><tr><td>2</td><td>备，点，冬日，……</td><td>10.6</td><td>9.2</td><td>19.9</td><td>15.1</td><td>9.2</td><td>5.9</td></tr><tr><td>3</td><td>夹克，多种，同型</td><td>10.8</td><td>3.6</td><td>3.7</td><td>0.0</td><td>5.3</td><td>1.8</td></tr><tr><td>4</td><td>针织，温差，备选，</td><td>12.7</td><td>5.5</td><td>14.7</td><td>23.2</td><td>25.2</td><td>12.6</td></tr><tr><td>5</td><td>轻盈，外面，羽绒,…</td><td>29.2</td><td>36.8</td><td>36.7</td><td>24.5</td><td>31.2</td><td>12.8</td></tr></table></body></html>

# 2.3LightGBM模型训练

![](images/fc2c85b00b59fc0e01ccfe61e9de318795f270f8338991059cde919bbf4ceeea.jpg)  
Fig.6Topic distance map

在训练过程中，将数据集按7：3比例分成训练集和测试集，使用5折交叉验证及网格搜索(GridSearch)穷举的方式，对模型进行调参。将需要调参的参数的值分别进行训练，为以5折交叉验证的平均得分作为模型最优参数，然后进行一下步的调参直到调参完成，过程如图7所示。实线为模型在各个参数值下的5折交叉验证平均得分，色块上端和下端分别为得分的最高分和最低分。

其中，模型所训练的样本数据为不平衡数据，正负样本比值为4.6，因此本文通过正负样本惩罚权重的方法，对分类中不同样本数量的类别分别赋予权重。即对LightGBM模型的参数scale posweight进行设置，设置值为5。

# 3 实验结果

# 3.1模型的评价及对比

由于本文使用的是不平衡样本，因此本文将选用AUC值作为模型之间的主要评价指标。AUC值被定义为ROC曲线下与坐标轴围成的面积，一般用于表示模型的综合性能，其特点是不容易受到不平衡样本的影响。以普通点击量为负例，高点击量为正例。则当样本不平衡时，若模型的预测偏向于比例大的负例时，会导致模型的准确率偏大，不能客观反映模型的性能。而对于不平衡样本，对比例小正例样本的预测识别也相当重要，召回率可以表示样本中的正例有多少被正确预测了。因此本文用准确率和召回率指标作为辅助参考指标。

另外，为了验证模型的有效性，本文将添加已有模型的对比，及与XGBoost、随机森林、SVM、KNN等主流分类算法进行对比。其中，“LGBM”是以主题概率量化特征构建的LightGBM 模型，XGBoost等算法也通过相同的调参方法(5折交叉验证及网格搜索)进行调参，以确保对比的公平性。

模型性能对比结果如表3所示，从AUC值看，改进后的LightGBM模型的AUC值达到了 $6 3 . 1 3 \%$ ，比以主题相关性量化特征的LightGBM 模型的 AUC 高了 $3 . 4 3 \%$ ，比XGBoost、随机森林、SVM、KNN算法分别高了 $0 . 3 9 \% , 1 0 . 0 2 \%$ $2 . 4 8 \%$ 、 $8 . 6 3 \%$ ，证明了式(1)能够反映消费者的情感倾向，且LightGBM模型性能也比其他算法更优。

表2部分商品描述的特征量化  
表3模型性能对比  
Tab.3Model performance comparison   

<html><body><table><tr><td></td><td>AUC值</td><td>准确率</td><td>召回率</td><td>AUC差值</td></tr><tr><td>改进LGBM</td><td>63.13%</td><td>62.74%</td><td>63.73%</td><td>0.00%</td></tr><tr><td>LGBM</td><td>59.70%</td><td>58.53%</td><td>61.54%</td><td>3.43%</td></tr><tr><td>XGBoost</td><td>62.73%</td><td>62.63%</td><td>62.90%</td><td>0.39%</td></tr><tr><td>随机森林</td><td>53.11%</td><td>81.17%</td><td>8.81%</td><td>10.02%</td></tr><tr><td>SVM</td><td>60.65%</td><td>63.81%</td><td>55.65%</td><td>2.48%</td></tr><tr><td>KNN分类</td><td>54.50%</td><td>77.99%</td><td>17.40%</td><td>8.63%</td></tr></table></body></html>

从准确率和召回率的角度看，随机森林、SVM、KNN算法的准确率明显更好，但召回率极低，证明这三种算法对高点击样本的识别能力有限，模型效果差。而改进后的模型的准确率和召回率都比改进前的模型更好，再次证明了改进的有效性。

模型的学习曲线如图8所示，随着样本数的增加，训练集模型的得分在不断下降，而测试集的得分在不断上升，两者得分开始接近且逐渐趋于平稳。这表明随着样本数的继续增加，模型能获得更好的性能。

![](images/e2c824e533e7c631a6f1d78df4207149d3cd0f85bf3378fc083b0f9a70786c6f.jpg)  
图7调参示例 Fig.7Parameter adjustment   
图8模型学习曲线 Fig.8Learning curve

LightGBM算法可以通过各个特征提供的信息增益来评估特征的重要性，而特征的重要性可以作为商品各个特征对用户的整体吸引程度。特征重要性如图9所示，可以认为外套的“保暖”、“风格”方面的特征更能直接影响用户的点击，因此企业可以通过加大或重点宣传商品的这两方向特征，从而使生产的商品获得更高的点击。另外，企业可以根据商品不同特征的情感词典测试商品功能的组合，并通过本模型进行预测，发掘消费者需求，调整商品未来的研发方向，降低试错成本，研发更可能受到消费者青睐的产品。

![](images/51abd70951a40e731cdc34ab23949de39f35456b81a01d3244501a57f76c79f2.jpg)  
图9特征重要性图  
Fig.9Feature importance

# 3.2数据污染及新文本效果分析

本文中，模型的情感词典是基于所有样本构建的，存在数据污染的可能，因此本节通过分层抽样的标准5折交叉方法划分所有样本，训练集和验证集比例为8：2，仅以训练集数据构建情感词典，测试集不参与情感词典的构建，从而验证新样本或新数据对模型性能的影响及模型与情感词典的关系。

如表4所示，5个数据集的AUC值均稳定在 $61 \%$ 左右，平均AUC值为 $6 2 . 1 7 \%$ ，十分接近原数据集的AUC分数，表明模型在情感词典改变后依然有良好的性能，证明了数据污染的影响很低或没有影响，对新样本也保持着相似的预测能力。而平均值与原模型AUC值的差距很可能是由于构建情感词典的样本数量减少所导致的，根据大数定律，当样本足够大时，该差距无限接近于零。

表4新样本下的模型性能  
Tab.4Model performance with new samples   

<html><body><table><tr><td>数据集</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>平均</td><td>原数据</td></tr><tr><td>AUC</td><td>61.68%</td><td>62.75%</td><td>62.32%</td><td>62.55%</td><td>61.56%</td><td>62.17%</td><td>63.13%</td></tr><tr><td>准确率</td><td>60.60%</td><td>60.50%</td><td>61.18%</td><td>60.52%</td><td>58.94%</td><td>60.35%</td><td>62.74%</td></tr><tr><td>召回率</td><td>63.37%</td><td>66.27%</td><td>64.10%</td><td>65.70%</td><td>65.62%</td><td>65.01%</td><td>63.73%</td></tr></table></body></html>

# 3.3冷启动问题分析

本节通过对目标商品的近邻商品的模型适应效果分析，探讨冷启动问题对模型的影响。具体做法是用相同方法筛选对比商品的商品描述文案样本，并观察其在目标商品模型中的性能表现。商品关系及模型性能如图10所示。

其中AUC是以“外套”建立的情感词典，使用各商品各自的样本训练的预测模型的性能得分，反映的是“外套”的商品特征在其他商品中的有效性；原AUC及原召回率则是直接使用原商品模型对其他商品样本进行预测的模型性能，反映了原商品模型对其他商品样本的预测能力；为了客观阐述商品之间的关系，除了根据商品分类划分商品外，还通过信息论中正点互信息公式(PPMI)计算总样本库中，目标商品和其他商品关键词的关系(即图10中各商品括号内数值)。其中PPMI越大，表明商品之间关联性越高。按PMMI排名的模型性能如表5所示。

对于无关商品：由图10和表5可知，“零食”与“外套”两种商品可视作无关商品。其中，“零食"的AUC值为 $5 1 . 2 6 \%$ 表明“零食”仅具备“外套”很少的商品特征；原AUC值为$4 9 . 6 1 \%$ ，表明原模型对“零食”商品几乎没有识别能力，与

现实情况大致相符。

![](images/5fa606fee95eb170fe4290eed7941694fa358450785faa2d173dfec8ced464b9.jpg)  
图10商品关系及模型性能  
Fig.10 Commodity relationships and model performance 表5按PPMI排名的商品模型性能

Tab.5Commodity model performance ranked by PPMI   

<html><body><table><tr><td></td><td>AUC</td><td>原模型AUC原模型召回率</td><td>PPMI</td></tr><tr><td>外套</td><td>63.13%</td><td>63.13%</td><td>63.73% /</td></tr><tr><td>夹克</td><td>57.66%</td><td>55.41%</td><td>47.36% 3.13</td></tr><tr><td>棉衣</td><td>58.85%</td><td>54.37%</td><td>79.65% 2.59</td></tr><tr><td>羽绒服</td><td>57.40%</td><td>52.50%</td><td>78.06% 1.91</td></tr><tr><td>衬衫</td><td>54.29%</td><td>52.13%</td><td>31.54% 0.90</td></tr><tr><td>衣服</td><td>61.32%</td><td>55.66%</td><td>49.76% 0.69</td></tr><tr><td>T恤</td><td>53.49%</td><td>52.27%</td><td>26.60% 0.66</td></tr><tr><td>零食</td><td>51.26%</td><td>49.61%</td><td>51.04% 0.00</td></tr></table></body></html>

对于近邻商品：由图10可知，模型对近邻商品的点击量依然保留着一定的识别能力。其中，直系商品(衣服、夹克、棉衣等)的AUC值及原AUC值都比同类商品(T恤、衬衫)更高，表明用户对直系商品的特征有着更相似的偏好。从AUC值看，直系商品的模型性能有着明显更高的得分，而同类商品则较低，且接近无关商品的得分，这可能是由于同类商品中特征的着重点不同所导致的。与现实中，对外套、棉衣等商品的关注点与T恤等明显不同这一情况大致符合。从PPMI看，除“衣服”外，与原商品之间的关联度(PPMI)越高，则模型在该商品的适应性就越强。基于这个特性，对于缺乏历史样本的新商品，可以通过筛选与新商品的直系商品或关联度高的商品的样本进行建模，从而缓解物品的冷启动问题。企业也能通过对比近邻商品特征的情感词典，挖掘具备其他商品特征的新产品的可能。

# 4 结束语

本文通过挖掘商品描述文案中商品属性，构建一个基于LightGBM的点击预测模型。该模型可以对商品非结构化文本信息进行量化，获得用户对商品各特征的情感倾向，同时利用LightGBM可解释性，根据特征重要性排序识别出对商品点击影响较大的主要因素，从而可以为商品提供宣传和研发上的决策支持。针对新商品的冷启动问题，模型利用不同商品特征的相似性，使得模型能在新商品在缺少历史数据的情况下进行点击预测。实验结果证明，模型较以主题概率量化特征构建的模型具有更好的预测效果。同时，模型对新商品的预测性能与商品的关联度呈正相关。本模型从对商品描述属性对点击量的影响分析问题，用LDA 主题模型对商品特征的划分带有一定主观性，也没有考虑到商品图片、价格等其他信息对商品点击的影响，模型性能不够高。未来工作可以通过使用更合适的主题模型及结合图像识别等技术进一步挖掘商品特征，来进一步提高模型的预测性能或可靠性。

# 参考文献：

[1]张秋韵，郭斌，郝少阳，等.CrowdDepict:多源群智数据驱动的个性 化商品描述生成方法 [J]．计算机科学与探索,2020,14(10):1670- 1680.(Zhang Qiuyun,Guo Bin,Hao Shaoyang,et al. CrowdDepict: personalizedrecommendationcontentgenerationbasedon heterogeneous crowdsourced data [J]. Journal of Frontiers of Computer Science and Technology,2020,14 (10): 1670-1680.)   
[2] Chan Zhangming, Chen Xiuying,Wang Yongliang,et al. Stick to the facts:Learning towardsa fidelity-oriented e-commerce product description generation [C]// Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing: EMNLP-IJCNLP. 2019: 4959-4968.   
[3] 刘梦娟，曾贵川，岳威，等．面向展示广告的点击率预测模型综述 [J].计算机科学,2019,46(07):38-49.(Liu Mengjuan,Zeng Guichuan, Yue Wei et al.Review on Click-through Rate Prediction Models for Display Advertising [J]. Computer Science,2019,46 (07): 38-49.)   
[4]朱志北，李斌，刘学军，等．基于LDA 的互联网广告点击率预测研 究[J].计算机应用研究,2016,33(04):979-982.(Zhu Zhibei,Li Bin, Liu Xuejun,et al.Research on click-through rate prediction of Internet advertising based on LDA[J].Application Research of Computers,2016, 33 (04): 979-982.)   
[5]Joachims T,Optimizing search engines using click through data [C]// Proceedings of the 8th ACMSIGKDD International Conference on Knowledge Discovery and Data Mining. ACM,2002: 133-142.   
[6]Guo Fan,Liu Chao,Kannan A,et al. Click chain model in web search [C]/ Proceedings of the 18th International Conference on World Wide Web.ACM,2009:11-20.   
[7]Graepel T,Candela JQ,Borchert T,et al,Web-scale Bayesian clickthrough rate prediction for sponsored search advertising in Microsoft's bingsearch engine [C]// Proceedings of the 27th International Conference on Machine Learning: ICML-10.2010: 13-20.   
[8]Regelson M,Fain D.Predicting click-through rate using keyword clusters [C]//Proceedings of the Second Workshop on Sponsored Search Auctions.2006,9623.   
[9]Richardson M, Dominowska E, Ragno R. Predicting clicks: estimating the click-through rate for new ads [C]// Proceedings of the 16th International Conference on World Wide Web.ACM,2007: 521-530.   
[10] Rendle S.Factorization machines [C]// Data Mining: ICDM,IEEE 10th International Conference on.IEEE,2010:995-1000.   
[11] Sun Mingxuan,Lebanon G,Kidwell P,Estimating Probabilities in Recommendation Systems [J].Applied Statistics,2010,61 (3).   
[12] Liu Hongyan, He Jun, Wang Tingting,et al, Combining user preferences and user opinions for accurate recommendation [J].Electronic Commerce Research & Applications,2013,12 (1-6): 14-23.   
[13]于蒙，何文涛，周绪川，崔梦天，吴克奇，周文杰．推荐系统综述 [J/OL].计算机应用,1-16 (2021-09-23)[2022-02-17].http://kns.cnki. net/kcms/detail/51.1307.tp.20210922.1115.002.html,(Yu Meng,He Wentao，Zhou Xuchuan，et al. Review of recommendation systems [J/OL].Journal of Computer Applications,1-16.(2021-09-23)[2022-02- 17]. http:/ns.cnki. net/kcms/detail/51.1307.tp.20210922.1115.002. html)   
[14] Li Xin,Xu Guandong,Chen Enhong,et al,MARS:A multi-aspect Recommender system for Point-of-Interest[C]//IEEE 31st International Conference on Data Engineering,IEEE,2015.   
[15] Fan Mingming,KhademiM,Predicting a Business Star in Yelp from Its Reviews Text Alone [J]. Computer Science,2014.   
[16] 杨贵军，徐雪，赵富强．基于LightGBM算法的用户评分预测模型及 应用[J]．数据分析与知识发现,2019,3(01):118-126.(Yang Guijun, Xu Xue，Zhao Fuqiang.Predicting User Ratings with XGBoost Algorithm [J].Data Analysis and Knowledge Discovery,2019,3 (01): 118-126.)   
[17]丁勇，陈夕，蒋翠清，等．一种融合网络表示学习与LightGBM的评 分预测模型[J].数据分析与知识发现,2020,4(11):52-62.(Ding Yong,Chen Xi, Jiang Cuiqing,et al. Predicting Online Ratings with Network Representation Learning and XGBoost [J]. Data Analysis and Knowledge Discovery,2020,4 (11): 52-62.)   
[18]张红丽，刘济郢，杨斯楠，等．基于网络用户评论的评分预测模型研 究[J].数据分析与知识发现,2017,1(08):48-58.(Zhang Hongli,Liu Jiying,Yang Sinan,et al.Predicting Online Users’Ratings with Comments [J].Data Analysis and Knowledge Discovery,2017,1 (08): 48-58.)   
[19]史伟，王洪伟，何绍义．基于微博情感分析的电影票房预测研究[J]. 华中师范大学学报：自然科学版,2015,9(1): 66-72.(Shi Wei,Wang Hongwei,He zhaoyi. Study on predicting movie box office based onsentiment analysis of micro-blog[J]. Journal of Central China Normal University: Natural Sciences,2015,9(1): 66-72.)   
[20]孙春华，刘业政．电影预告片在线投放对票房的影响——基于文本 情感分析方法[J]．中国管理科学,2017,25 (10):151-161.(Sun Chunhua,Liu Yezheng.The Effects of Online Pre-launch Movie Trailers on the Box Office Revenue- Based on Text Sentiment Analysis Method[J].Chinese Journal of Management Science,2017,25 (10):151- 161.)   
[21]李晓菊，协同过滤推荐系统中的数据稀疏性及冷启动问题研究 [D]. 华东师范大学,2018.(Li Xiaoju.Research on Data Sparsity and ColdStart Problem in Collaborative Filtering Recommendation System [D]. East China Normal University,2018.)   
[22] Blei D M,NgAY,Jordan MI,Latent Dirichlet Allocation [C]//Advances in Neural Information Processing Systems 14 [Neural Information Processing Systems, Natural and Synthetic,NIPS 2001, December 3-8, 2001,Vancouver,British Columbia,Canada].2001.   
[23] Ke G,L,Meng Qi,Finley T,et al.LightGBM,a Highly Efficient Gradient Boosting Decision Tree [C]// Advances in Neural Information Processing Systems 30, California,2017,3149-3157.   
[24] Chen Qibin,Lin Junyang,Zhang Yichang,et al. Towards KnowledgeBased Personalized Product Description Generation in E-commerce [J]. arXiv preprint arXiv: 1903.12457.