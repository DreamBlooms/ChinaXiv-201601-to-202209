# 融合多模态资源的教育知识图谱的内涵、技术与应用研究

高茂，张丽萍

(内蒙古师范大学 计算机科学技术学院，呼和浩特 010022)

摘要：传统的教育知识图谱研究多数面向文本资源，忽略了多模态资源对教育知识的解读作用及其自身丰富的特征表示。为了更好地推进后续研究工作，以多模态资源为切入点，对教育知识图谱进行综述。首先，介绍了知识图谱的概念和分类；其次，综述了教育知识图谱的内涵，对教育知识图谱的定义、分类及其构建框架进行梳理；接下来，结合以神经网络为代表的深度学习方式，对教育知识图谱的构建技术进行重点介绍；最后，总结了教育知识图谱的相关应用，并指出当前研究中存在的问题与未来的研究方向。

关键词：教育知识图谱；多模态资源；深度学习；知识图谱构建技术中图分类号：TP18 doi:10.19734/j.issn.1001-3695.2021.12.0686

# Research on connotation, technology and application of educational knowledge graph based on multi-modal resources

Gao Mao, Zhang Liping† (College ofComputer Science & Technology,Inner Mongolia Normal University,Hohhot O10022,China)

Abstract:The traditionalresearch oneducational knowledgegraph is mostly text-orientedand ignores the interpretation functionofmultimodalresoures toeducational knowledgeanditsrichcharacteristicrepresentatio.Inordertobeterpromote the follow-up research work,this paper reviews theeducational knowledge graph from the perspective of multi-modal resources.Firstly,itintroduces theconceptandclassificationofknowledge graph.Secondly,ititroduces theconnotationof theeducational knowledge graph，summarizes the definition,clasification and construction framework of educational knowledge graph; Thirdly，combinedwithdeep learningrepresented byneural network,it introduces theconstruction technologyof educational knowledge graph.Finally,itsummarizes the specificapplicationof theeducational knowledge graph, points out the problems existing in current research and future research directions.

Key words:educational knowledge graph;multimodalresources; dep learning; knowledge graphconstruction technology

# 0 引言

近年来，随着“互联网 $+$ 教育”模式的普及，教育领域逐渐积累了海量具有应用价值的教育数据。但不同来源的教育数据之间结构不同、没有建立起相应的联系，难以直观地服务于教学参与者，迫切需要人工智能、大数据等新兴技术采集并处理相关的教育数据，为教师、学生和家长群体提供智能服务，持续促进教育应用的智能化[]。

知识图谱作为人工智能技术在知识工程方面的代表，能够有效地处理和分析数据，重构知识之间的联系，为数据决策或者分析提供支持[2]。在2019年的“全国教育信息工作会议上”，知识图谱和深度学习、大数据一起被列为智能教育时代下的重点研究内容，针对教育知识图谱的研究也成为了教育技术的研究热点。

教育知识图谱能够基于教学过程中产生的教学数据和资源，对不同学科的多层次知识结构进行准确地表征，为教育教学对知识的建模提供可能性[3]。但目前教育知识图谱的数据来源通常是文本数据和结构化数据，关于多模态资源的研究较少。多模态资源区别于传统的单一媒体资源形式，泛指教学过程中产生的大量文本、视频、音频以及图片信息。结合多模态资源，能够在知识挖掘的过程中丰富知识的特征表示，提升教育信息挖掘的准确程度。同时，通过教育知识图谱对大量无序的多模态资源进行处理，能够有效地破解多模态资源汇聚融合的难题，对于生成个性化学习路径、教育资源推荐等智能教育应用具有极大的意义。

据调研，祝智庭、余胜泉等学者多次提出结合人工智能技术，在实现教育智慧化的过程中进行教育知识图谱研究的必要性[4,5]。李振等人[6在人工智能的视角下对教育知识图谱的内涵、构建技术以及具体的应用进行综述。李艳燕等人[7]则从智慧教育的角度讨论学科知识图谱的相关定义、构建技术和应用。本文以多模态资源为切入点，对教育知识图谱进行综述。首先，介绍知识图谱的基本概述；其次，总结教育知识图谱的内涵，对教育知识图谱的定义、分类情况和构建框架进行梳理；接下来，从教育本体构建、教育知识抽取、教育知识表示和教育知识融合四个方面对教育知识图谱构建技术进行重点介绍；最后，总结教育知识图谱的相关应用，分析当前面临的主要问题和研究趋势，在分析当前领域的同时，也为将来该领域的发展提供一些借鉴和参考。

# 1 知识图谱的基本概述

2012年5月，知识图谱这一术语正式被谷歌提出[8]，它使用实体、实体属性和实体关系的表述方式描述客观世界的各个概念实体及其之间的联系[9]，被广泛应用在知识的组织和语义化建模研究中。依据应用领域的不同，可以将知识图谱分为通用知识图谱(Universal Knowledge Graph，UKG)和领域知识图谱(Domain-specific Knowledge Graph，DSKG)。通用知识图谱重点表示不同领域知识之间的融合，涉及的知识范围较为广泛，对于知识的精确度要求不高。而领域知识图谱将关注点放在一个特定的领域，依据领域知识特点构建严格的数据模式，以保证数据的深度和精度。

面向通用领域的知识图谱有很多，如国内的 zhishi.me、搜狗的“知立方”，国外的YAGO、Freebase等，目前被广泛应用于搜索、推荐、问答等互联网应用中。其中，有一部分是融合多模态资源的通用知识图谱，例如Dbpedia[10]，Wikidata[11]，IMGpedia[12]，MMKG[13]和Richpedia[14]等，其特点以及优劣势如表1所示。

表1融合多模态资源的通用知识图谱的优缺点比较  
Tab.1Comparison of advantages and disadvantages ofuniversal knowledge graph fusing multi-modal resources   

<html><body><table><tr><td>名称</td><td>描述</td><td>优点</td><td>缺点</td><td>数据源</td></tr><tr><td>Dbpedia[10]</td><td>通过处理维基百科信息，得到结构化的知识低成本、大规模的知识库，拥 数据不会定时更新，过度依赖于维 形式，用户可以通过网络访问其信息</td><td>有完整的多领域知识本体结构 基模板的信息，语言版本不完整</td><td></td><td>维基百科</td></tr><tr><td>Wikidata[11]</td><td>从维基百科中进行知识抽取、存储、关联，知识库开源、用户可参与编数据大多来自国外，缺乏与国内机 进而形成的大规模链接知识库</td><td>辑，且拥有多语言版本</td><td>构知识库的连接</td><td>维基百科</td></tr><tr><td>IMGpedia[12]</td><td>将图片数据链接到语义知识图谱中，构建形 在解决语义查询的问题上有天 实体关系不丰富、种类少，图像分 维基百科、 成多模态知识图谱</td><td>然的优势</td><td>类不明确</td><td>Dbpedia</td></tr><tr><td>MMKG[13]</td><td>由三个知识图谱合并形成的多模态知识图 谱，包含了实体的数字特征和图像特征</td><td>技术有促进作用，能够加速多独存在，且实体匹配时没有考虑</td><td>对多关系链接预测和实体匹配图像实体依附于文本实体，没有单</td><td>Dbpedia、 Yago</td></tr><tr><td>Richpedia[14]</td><td>在传统文本知识图谱的基础上填充图像实包含全面的图像实体及其之间 体，构建包含文本、图像实体的知识图谱</td><td>模态学习方法的发展 的关系</td><td>图像的多样性 实体种类不够丰富，有待完善</td><td>维基百科、 Wikidata、谷 歌、雅虎和必应</td></tr></table></body></html>

领域知识图谱的研究重点聚焦于特定领域任务的解决方面，不少学者在农业、医疗、企业服务等领域构建知识图谱[15\~17]。在融合多模态资源的领域知识图谱研究工作方面，Xu等人[18]将知识图谱技术应用于多模态数据关联，构建了企业雷达产品开发的知识图谱。面向电力计量领域，Gao 等人[19]提出一种基于知识图谱的电力大数据混合索引结构和索引方法，为多模态数据的高效检索提供了技术参考。Wang 等人[20]提出一种基于知识图谱的方法来建立医疗领域中多模态临床数据之间的联系。Zhang等人[21]设计了一种将图像视觉信息与Wikimedia公共空间中的文本信息相结合的方法构造了金属材料领域的知识图谱。

使用知识图谱对教育活动过程中产生的数据进行建模也成为了当前的热点研究问题[22。目前，已经存在多个面向不同学科资源构建的教育知识图谱。Chen等人[23]提出了一个自动构建教育知识图谱的KnowEdu系统来支持教学。清华大学许斌副教授所在的项目组基于基础教育权威的教材教辅资源，结合互联网中的文本资源完成了我国第一个全学科基础教育知识图谱，为智能教育的实现提供了数据支撑。还有研究者在解决慕课(Massive Open Online Course,MOOC)知识资源管理的问题上，构建了包括课程资源、知识概念、学生行为等教学因素的教育知识图谱[24\~26]。除此之外，一些公司基于教育知识图谱进行应用，例如，百度公司的K-12教育知识图谱、美国Knewton自适应学习平台的教育知识图谱[27]等。

# 2 教育知识图谱的内涵

# 2.1教育知识图谱基本定义

目前，对于教育知识图谱还没有形成统一的定义。通过总结相关学者对教育知识图谱的研究，认为教育知识图谱应该从以下两个角度定义：(1)学科资源的角度。教育知识图谱可以准确地表征各类知识点及其关联的教学资源之间的联系，起到对学科资源进行建模与管理的作用[28.29]。(2)学习认知的角度。教育知识图谱可以建构学习者的学情信息，准确表征学习者的认知状态[30]。在二者的基础之上，结合学习资源与学习者的学情信息，教育知识图谱可以为学习者生成多种智能教育应用，促进教育领域智能化的发展[31]。

# 2.2教育知识图谱的分类

教育知识图谱不仅针对传统意义上的学科知识，而且对教学场景中产生的多种教学资源进行管理。包括以下两类：(1)静态知识图谱，以学科资源为主，建立学科知识点之间、学科知识点与学科资源之间的联系；(2)动态知识图谱，侧重于学科知识点与教学过程中的活动以及教学事件之间的联系等。

# 2.3教育知识图谱构建框架

知识图谱主要分为自顶向下和自底向上两种构建方式[32]。自顶向下的方式侧重于知识模式，也可以理解为领域知识的框架体系，通过构建好的知识模式填充知识实例。自底向上的方式偏重于知识实例，即先对知识实例进行抽取，通过获得的知识实例进一步提炼知识模式。当前，自底向上的方式多数被用在知识图谱构建之初对知识的整体框架不明确或者单纯为了收集多方面知识的通用知识图谱构建研究中，而对于内容较为明确、且要求体现相关领域知识深度的领域知识图谱，一般采用自顶向下的构建方式。考虑到教育领域对知识质量与知识深度的严格要求，教育知识图谱主要采用自顶向下的构建方式。

随着大数据技术的日益成熟，教育数据不仅存在于大量的书本教材中，还存在于教学过程中产生的非结构化的多媒体数据、半结构化的学科资源学习网站以及部分教育数据库的结构化数据中，需要通过知识图谱构建模型训练得到包含不同学科关系的三元组形式，以构建教育知识图谱。其具体构建流程分为教育本体构建、教育知识抽取、教育知识表示和教育知识融合。其中，教育本体构建是依据教育知识体系，结合教学专家的经验，通过人工或者自动化的方式挖掘教学资源之间的联系，制定知识框架；教育知识抽取是依据教育本体，从海量的教育资源中抽取相应的实体及其之间的对应关系；教育知识表示是在获得实体对的基础上采用计算机可以理解的形式表示教育知识实体及其之间的语义关系，为之后的知识融合提供帮助；教育知识融合是对获取到的三元组知识进行整合、语义消岐以及关联教学资源等操作，形成以学科知识体系为核心，融合多种教学资源的教育知识图谱，构建过程如图1所示。

![](images/a34201d61df61778e3b61a477e96b640e4b1641337469fd449b84fccd2d5a574.jpg)  
图1教育知识图谱的构建过程图

# 3 教育知识图谱构建技术

教育知识图谱的构建研究多数面向文本数据，以自然语言处理任务为主，多模态数据能够提供辅助特征，对实体信息进行准确地表征。同时，将多模态数据链接到教育知识图谱，作为文本实体的扩充，可以极大程度地丰富教育知识图谱的知识表示形式，满足智能教育应用的多元化需求。本节结合多模态资源的处理，对教育知识图谱的构建技术进行阐述。

# 3.1教育本体构建

教育本体是教育知识图谱的知识框架，详细描述了概念实体类型以及实体之间的关系类型，为后续教育数据的抽取过程设定了知识规范。本体构建主要分为人工构建、自动构建和半自动构建的方式。

人工构建方式是结合领域专家的指导，人为定义概念实体类型、概念实体的关系类型等相关约束。图2是人工构建的教育知识图谱顶层本体。其中，学科知识本体是知识点对应的一些属性，例如概念、定义等；课程标准本体包括教学目标、教学活动等在内的一些教学单元；学习资源本体涵盖教材、微课等教学资源。

![](images/72108d8458ccc71f67d0f61bbebb9d98fa7bb309196e7345a5c1d278ad1b18de.jpg)  
Fig.1The construction process of educational knowledge graph

自动构建方式是使用机器学习等相关技术处理数据得到知识本体，分为基于文本、基于词典和基于本体学习的方式[33],虽然上述方式能够有效地减轻人工构建本体的负担，但通常被应用于简单的领域知识本体构建研究中，考虑到教育领域知识的复杂性，自动方式并不适用于教育本体的构建。

半自动构建方式采用计算机为主，结合人工干预的方式，能够在保证准确率的前提下有效地减轻人工构建本体的负担被广泛应用于教育本体的构建研究中。童名文等人[34]前期通过基于关联规则的方式自动化地抽取课程本体，在此基础上，通过人工调优进一步保证本体构建的正确率。Wang 等人[35]通过分析电子书日志、挖掘维基百科信息的方式提取知识点之间可能存在的关系，以支持教师半自动地构建以课程为中心的本体。

目前教育本体的构建研究仅局限于某一门课程或针对于某一学科的具体任务，研究涉及的范围较小，且构建好的教育本体不具备迁移性，难以适应于其他学科的本体构建任务中。祝智庭等人[4]提出建立教育知识图谱的标准化本体，但促成这一目标，需要教育领域的相关专家以及从事教育数据文本分析的技术人员共同努力，从理论和技术层面挖掘出不同学科知识体系中的共性内容，制定通用的教育知识本体，为教育知识图谱的构建提供便利。

# 3.2教育知识抽取

知识抽取是面向开放的教育资源，利用人工或自动化方式抽取出知识单元及其之间的关系，形成“实体-关系-实体”的三元组表示形式。

早期的教育知识抽取方式是以即时制定规则的形式处理知识，这样的方式在面对规模较大的教育数据时就变得耗时耗力，且制定好的规则难以进行迁移。随后，支持向量机模型(Support Vector Machine,SVM)[36]、概率图模型(ProbabilisticGraphicalModel,PGM)[37]和隐马尔可夫模型(Hidden MarkovModel,HMM)[38]出现，研究者们开始利用教育数据的特征进行模型训练和信息抽取，有效地减轻了人工规则制定的负担，使得统计机器学习的方式得到了广泛应用。

以卷积神经网络(Convolutional Neural Networks,CNN)[39]和循环神经网络(Recurrent Neural Networks,RNN)[40]为代表的深度学习技术，在统计机器学习使用人工标注数据特征的基础上进一步优化，逐渐可以实现机器自动抽取特征信息。在其之上，注意力机制(Attention Mechanism,AM)[41]，以及后续出现的以Transformer[42]为架构的BERT预训练模型(BidirectionalEncoder Representations from Transformers)[43]进一步优化了信息抽取的深度学习方法，为教育知识抽取奠定了强有力的基础。

经过对文献[44,45]的参考与总结，得出教育知识抽取的流程，即通过实体识别获得文本资源的多个知识实体，在获得知识实体的基础上进行关系抽取，形成结构化的知识体系，具体流程如图3所示。

![](images/a7160351cbc35cfb775588f4776bd6dc461d3d8513908bd6bba9c6274393b774.jpg)  
图2人工构建的教育知识图谱顶层本体 Fig.2Artificial construction of the top ontology of educational knowledge graph   
图3教育知识抽取流程图  
Fig.3Flow chart of educational knowledge extraction

3.2.1实体识别

实体是教育知识的基本元素，其识别的准确率对于教育知识图谱的质量至关重要，所以实体识别是教育知识图谱构建的重点研究内容。

大量的深度神经网络技术被应用于实体识别任务，其中应用最广泛的就是 RNN 和长短期记忆网络[46](Long-ShortTermMemoryRNN，LSTM)。RNN能够很好地学习序列样本的时序信息和相互关系，LSTM的改进形式是在RNN中添加了“门结构”以模拟人脑的记忆过程。在LSTM的基础上，其双向形式BiLSTM[47]、基于注意力机制的BiLSTM[48]陆续被提出。教育领域经典的命名实体识别方法是BiLSTMCRF[49]，即利用BiLSTM提取深度特征，用条件随机场(ConditionalRandomField，CRF)模型进行文本序列标注。随着预训练模型的提出，研究者将BERT、XLNet等预训练模型与BiLSTM-CRF结合，进一步提升命名实体识别的准确率[50]。Wei等人[51]使用BERT $+$ BiLSTM-CRF模型对教育领域突发事件语料库进行实体识别，准确率达到了 $91 . 6 2 \%$ ，为政府对教育突发事件的决策提供了帮助。BERT $^ +$ BiLSTM-CRF模型结构如图4所示，首先，通过BERT编码层获取文本对应的向量表示；然后使用BiLSTM进行特征提取；最后使用CRF对序列进行解码和注释，以准确预测实体及其对应的类型。

![](images/423c1a6bb91ce5e5259fce629b597db4b73aefa52eaef707ff28c42be1688568.jpg)  
图4BERT+BiLSTM-CRF实体识别模型  
Fig.4BERT $^ { \ast } +$ BiLSTM-CRF entity recognition model

有研究者考虑到文本数据所提供的特征信息很有限，准确率较低，提出利用所要识别实体的上下文信息，即图像信息辅助预测实体信息。相关工作方面，文献[52]利用图像信息为文本提供互补的上下文信息，以提高实体识别的质量。考虑到图像中包含的细粒度实体特征与文本信息进行匹配的问题，文献[53]提出了一种基于门控双线性注意力机制的对抗神经网络(Adversarial GatedBilinearAttentionNeuralNetwork，AGBAN)，该模型从图像和文本中联合提取实体特征，并利用对抗训练的方式将两个不同的知识表示映射到共享表示中，有效地提取了与实体相关的细粒度特征信息。此外，除了文本和图像对齐的情况，如果出现图像与文本不匹配或者只包含一种模态信息的情况下，文献[54]提出了一个不确定性感知的多模态实体识别框架，处理图像不存在或者图像与实体不对应的问题。

在教育领域，传统的实体识别任务只针对文本数据，忽略了多模态数据对于准确预测实体的重要性。后续研究者可以从多模态数据为文本数据提供互补的特征或者挖掘多模态资源蕴涵的某些特质信息出发，对实体识别任务进行优化。例如，可以将课本中的图片或者学习网站中的插图信息作为辅助特征，为前沿的基于预训练模型的课程知识实体识别方法提供视觉上下文信息，进而提升准确率。也可以发掘多模态资源中的特质信息，为实体识别任务提供先验知识，例如使用课程语音资源的语气停顿信息对文本进行准确分词等[55]。

# 3.2.2关系抽取

关系抽取是在获得学科实体的基础上对其进行语义链接，即从教育文本资源中挖掘出知识点之间的语义关系以及学习的先后顺序[56]。

研究者早期通过人工的方式建立课程资源之间的依赖关系，即学习的先后顺序[57,58]。随着知识资源规模的扩大，为了减轻人工抽取概念关系的负担，研究者将机器学习的方式应用于学科知识点的关系抽取研究中。Chaplot等人[59]使用无监督的方式对MOOC视频的日志信息进行分析，以抽取知识点之间的依赖关系。Yu等人[24通过分析学习者的行为数据，采用基于关联规则的机器学习方式，获得知识点的学习顺序。文献[60,61]从MOOC课程资源出发，使用机器学习的方式，结合知识点的概念特征、图特征以及结构特征等进行知识点的关系抽取，取得了良好的效果。

相比于传统的基于规则和机器学习的关系抽取技术，深度学习技术能够有效地减少人力标注数据的需求，深受研究者的追捧。当前基于深度学习技术进行关系抽取的研究热点集中在有监督学习和远程监督学习的方面。有监督学习方面，主要以CNN、RNN、LSTM及其相应的改进形式为主，如表2所示。

表2基于深度学习的有监督关系抽取方法分类  
Tab.2Classification of supervised relation extraction method   

<html><body><table><tr><td colspan="3">based on deep learning</td></tr><tr><td>类型</td><td>相关工作</td><td>对比分析</td></tr><tr><td></td><td>CNN文献[62~65]</td><td>CNN能够很好的解决机器学习依赖手动提取特 征的问题，实现“端到端”的关系抽取</td></tr><tr><td></td><td>RNN 文献[66,67]</td><td>CNN模型较难实现时序特征的提取，而RNN 能够处理长距离词之间的依赖问题</td></tr><tr><td></td><td>LSTM 文献[68,69]</td><td>RNN无法解决关系抽取语料中长期依赖的问题， 而LSTM能够从语料中学习到长期依赖关系</td></tr></table></body></html>

Liu 等人[62]首先使用由输入层、卷积层、池化层和Softmax层构成的简单CNN模型，通过输入文本的词向量和位置向量抽取实体关系。Zeng等人[63]利用卷积深度神经网络CDNN进行关系抽取，通过提取文本资源中词汇级别和句子级别的特征，将其映射成高层次的语义特征以实现关系分类，避免了使用预处理操作提取到的错误特征问题。此后，Xu等人[64]在 Zeng 等人工作的基础上提出基于最短依存路径的CNN方法，结合负采样策略解决实体位置较远时依存分析树带来的噪声问题。Santos 等人[65]替换 Zeng 等人模型中的Softmax层，使用排名进行分类输出，并提出一种新的排名损失函数，能够给予正确类别排名信息更高的分数，对关系类别实现有效地区分。

除了使用CNN进行关系抽取，RNN首次被提出用来处理自然语言文本中句子结构的问题[66]，其通过不停的迭代获得句子的向量表示，在关系抽取任务中有效地融入了句子结构表示信息。此后研究者不断对RNN作出优化，例如增加特征、引入平均信息等方式[67]。

作为RNN的改进形式，LSTM模型[68]的提出主要是为了解决RNN在关系抽取中出现的梯度消失等问题，其具备从语料中学习长期依赖的优势。鄂海红等人[56采用LSTM的变体形式GRU,结合CNN、RNN对基于LSTM的关系抽取方式作出改进，进一步提升了关系抽取的准确率。

有监督的关系抽取方式不能很好地处理语料库中包含大量无标签数据的情况，而远程监督学习能够通过已有的知识库进行知识对齐，解决训练数据的标注问题。文献[69]使用远程监督的方法进行关系抽取，解决了语料标注稀少的问题。基于远程监督学习的方式容易产生错误标签，影响关系抽取的质量。基于此，CNN的改进模型PCNN+MIL[70]、PCNN+ATT[71]被提出且有效地降低了错误标签对关系抽取的影响。文献[72]基于远程监督的思想，结合Transformer架构，提出BTRE $^ { + }$ GCLSTM模型，对初中数学课程的知识点关系进行抽取，取得了较好的效果。

基于远程监督进行关系抽取是目前教育知识图谱中主流的关系抽取方式，但该种方式由于引入了外部知识，导致了大量数据噪声的产生，造成了相关研究者的困扰。使用强化学习和对抗学习能够进行噪声检测、提升神经网络模型对于噪声样本的鲁棒性，相关研究者可以基于强化学习和对抗学习的方式，对远程监督数据集进行降噪。

# 3.3教育知识表示

教育知识表示是针对教育知识图谱的数据实例层面，指采用计算机可以“理解”的方式描述通过知识抽取过程得到的三元组知识。传统的教育知识表示方法是采用网络本体语言(Web Ontology Language,OWL)或者资源描述框架(ResourceDescriptionFramework,RDF)等本体语言进行描述[73]，但上述方式存在计算效率不高与数据稀疏的问题。随着深度学习技术的发展和应用，教育知识表示逐渐转变为当前的向量表示形式，即从结构化的三元组中学习知识表示，将其嵌入到向量空间中[74]，准确表征知识实体之间的语义关系。根据处理数据类型的不同，将知识表示模型分为传统的知识表示模型和多模态知识表示模型，如表3所示。结合深度学习方法，本文对各类模型作出分析。

表3传统知识表示模型和多模态知识表示模型的比较  
Tab.3Comparison between traditional knowledge representation modeland multimodal knowledge representation model   

<html><body><table><tr><td>类型</td><td>方法</td><td>特点</td><td>优势</td><td>不足</td></tr><tr><td rowspan="3">传统知识表 示模型</td><td>TransE[75]</td><td>利用向量平移的思想，在同一个向量空间中建 简单、高效，能够较好地适应 模实体和关系</td><td>于多关系数据的处理问题</td><td>不能很好的表示复杂关系</td></tr><tr><td>TransR[76]</td><td>在实体空间和多个关系空间中建模实体和关 系，并在对应的关系空间中进行转换</td><td>同时兼顾了实体和关系的多样性</td><td>计算复杂度高，头尾实体的类型可能差 异很大，难以应用于大规模知识图谱</td></tr><tr><td>TransD[77]</td><td>对每个实体和关系用两个向量表示，第一个表 示本身的语义，第二个向量用于构造映射矩阵</td><td>计算复杂度较低，参数少</td><td>有的新事实很难从现有的情况中推 论得出</td></tr><tr><td rowspan="5">多模态知识 表示模型</td><td>TransAE[78]</td><td>在TransE 的基础上，加入了实体的文本描述和 显著提高了链路预测和三元组 图像特征信息</td><td>分类的性能</td><td>没有提取图像里的多个实体和实体关系</td></tr><tr><td>IKRL[79]</td><td>在TransE的基础上，加入了实体的图像特征信息</td><td>补充图谱的实体类型，使得准 只考虑图像里包含的单个实体，没有 确预测实体的几率增加</td><td></td></tr><tr><td>DIRL[80]</td><td>在 TransR 基础上，加入了实体的文本描述和图 在结构信息缺失时提供了必要 相较于基础的 TransE、TransR 模型，</td><td></td><td>考虑多个实体存在的情况</td></tr><tr><td>ITMEA[81]</td><td>像特征信息 结合 TransE、TransD，加入了实体属性描述和 为多模态实体对齐提供较好的 在多模态实体对齐过程中可能会引入</td><td>的补充信息</td><td>该模型的时间成本较高</td></tr><tr><td></td><td>实体对应的图像特征信息</td><td>解决方案</td><td>错误信息</td></tr></table></body></html>

作为知识图谱中传统知识表现形式的代表，TransE将实体和关系向量表示在同一个向量空间[75]，并将关系向量看做是头实体到尾实体向量之间的平移操作，如式(1)所示。文献[82]使用TransE和Distmult[83]的知识表示学习方式建构课程知识图谱中知识实体及其之间的关系，从学生的先验知识和课程内容的角度，为学生成绩预测应用中协同过滤算法的冷启动问题提供了较好的解决方案。

$$
l _ { h e a d } + l _ { r e l a t i o n } = l _ { t a i l }
$$

其中：lhead 与 $\mathbf { l } _ { \mathrm { t a i l } }$ 分别代表头实体向量与尾实体向量；lrelation表示关系向量。

Wang 等人[78]在TransE的基础上作出改进，提出第一个多模态知识表示模型TransAE，使用实体的文本描述和图像作为外源信息对知识表示进行补充，在链接预测和三元组分类的任务中取得了不错的效果。Xie等人[79]提出IKRL知识表示模型，通过神经网络图像编码器对图像信息编码，结合图谱的结构知识进行知识表示，能够较为准确地预测实体信息。文献[80]使用BERT模型对文本概念的语义表示进行编码，利用CNN编码器提取图像特征，在此基础上，将文本概念表示、图像特征表示与翻译模型TransR结合共同学习知识表示，在知识图谱补全(Knowledge Graph Completion，KGC)任务中取得了不错的效果。文献[81]使用深度卷积神经网络VGGNet表示图像信息，结合TransE和TransD，将文本信息和图像信息嵌入到统一的低维空间中，有效地支撑了多模态实体对齐任务。

目前针对教育知识图谱的多模态知识表示研究较少，但随着教育数据资源范围的不断扩大，教育知识表示正朝着更全面的模态层次以及更丰富的语言关联方向发展，未来可以从建模逻辑规则、结构化和非结构知识以及多模态知识表示等多个角度优化教育知识表示方法，为教育知识的融合、增量更新以及多种下游应用任务提供支持。

# 3.4教育知识融合

由于教育数据库中的知识来源复杂，知识质量参差不齐，且不同来源的学科知识实体间存在关系模糊的问题，所以必须在统一的规范下对多源异构、语义多元的教育数据进行整合、消岐、合并等操作，该过程也称为教育知识融合过程[84]。教育知识融合的关键技术是实体链接和实体对齐。

# 3.4.1实体链接

实体链接是通过同义词消岐等方式将文本资源中的实体对象正确链接到知识图谱实体的任务。具体过程如下，首先，通过实体识别技术，识别出文本中的实体(也称指代实体)，然后遍历知识图谱中的实体，形成候选的实体集合，依据不同的方式对二者进行匹配。实体链接的方式主要分为基于实体属性信息的方法[85]和基于上下文信息的方法[86]。

基于实体属性信息的方法主要对实体名称字符串进行匹配，祁晓慧等人[87使用语音识别技术将《数据结构》课程中的音频资源处理成文本资源，并利用正则语言的方式匹配课程知识图谱中的实体，以链接知识实体对应的语音资源，具体过程如图5所示。

![](images/2de7e26dddb251ce68ee0782d3294a8563e5db5b552cf7d36ac1ddd8c618010d.jpg)  
图5实体链接过程图  
Fig.5Entity linkage process diagram

此外，还有研究者依据Cosine距离和Jaccard相关系数的方法计算实体名称的相似度，如式(2)、式(3)所示，取得了较好的效果。

$$
\mathrm { S i m } _ { \mathrm { c o s i n e } } \left( e _ { 1 } , e _ { 2 } \right) = \frac { \left| A \left( e _ { 1 } \right) \cap A \left( e _ { 2 } \right) \right| } { \sqrt { \left| A \left( e _ { 1 } \right) \right| \left| A \left( e _ { 2 } \right) \right| } }
$$

$$
\mathrm { S i m } _ { \mathrm { j a c c a r d } } \left( e _ { 1 } , e _ { 2 } \right) { = } \frac { \left| A ( e _ { 1 } ) \cap A ( e _ { 2 } ) \right| } { \left| A ( e _ { 1 } ) \cup A ( e _ { 2 } ) \right| }
$$

其中：实体ei,e2指需要比较的实体对；而 $A ( e )$ 指的是实体相对应的字符串。 $\mathrm { S i m } _ { \mathrm { c o s i n e } } ( \mathbf { e } _ { 1 , \mathbf { e } _ { 2 } } )$ 是使用余弦距离计算向量相似度的方式，即利用向量空间中两个向量之间的夹角衡量实体e1,e2 的相似性。Simjaccard(ei,e2)通过计算 $A ( e _ { 1 } )$ 、 $A ( e _ { 2 } )$ 两段文本中交集元素个数与并集元素个数的比值来计算实体ei、e2的相似度。

基于上下文信息的实体链接方法根据实体所处的上下文环境以判断实体对的相似度。文献[88]针对计算机科学等学科的专业教材资源以及维基百科中的资源进行实体链接工作，通过所要识别实体的上下文信息与领域词典进行对比，确定实体所属的领域，然后结合领域特征进行实体链接，取得了较好的效果。

为了建立教育知识图谱中知识点与多模态教学资源之间的联系，研究者们一般利用多模态资源的元数据，例如教学网站中图片的超链接等文本描述形式，或者通过视频字幕处理、语音识别等技术将多模态数据转换成文本数据，进而使用实体链接技术为教育知识图谱添加多模态资源实体。但上述方式较为片面，并不能准确捕捉多模态资源本身的特征，且多模态资源转换成文本资源的过程中存在很大的噪声问题。以图像实体链接任务为例，后续的研究方向可以考虑引入图像特征提取模型以及注意力机制等方法获取图片的准确特征，解决上述方式存在的问题。

# 3.4.2实体对齐

实体对齐是判断不同来源的实体是否对应同一个现实对象的任务，通常被用于多个知识图谱的合并过程中。当前的主流研究趋势是利用知识表示的方法将实体嵌入连续低维向量空间，通过计算向量之间的相似度集成多个知识实体，以丰富教育知识图谱中现实对象的多种描述信息。

周炫余等人[89]在初中数学知识图谱构建的研究中，考虑到从百度百科和互动百科网站爬取的半结构化数据和教材中的非结构化数据之间没有建立联系，导致实体的数据来源零散和权威性不够等问题，提出图6所示的基于层次过滤思想的知识融合模型，极大程度地丰富了课程实体的多种描述信息。其中，对百度资源和教材资源均经过预处理层、字符串匹配层等五个环节进行实体对齐。在该过程中，除了使用传统的字符串匹配操作，还在词形匹配层中，将实体对应的摘要关键词信息转换为向量，并利用余弦相似度的方法补充判断实体间的相似度。在判断实体对齐的基础上，进一步使用HowNet语义相似度和谷歌距离语义相似度方法将课程知识实体的多种描述信息链接到知识图谱中。

![](images/51f2c7911e2121ae2eb77ef04aa53b16f0ffb48c8ae4565211cc4e6025909c22.jpg)  
图6基于层次过滤思想的知识融合模型处理逻辑示意图

ig.6Processing logic schematic diagram of knowledge fusion model based on hierarchical filtering idea

在教育领域大数据研究的驱动下，研究者提出将多模态数据作为实体对齐数据，扩充实体对应的多模态知识表示形式[90]。但该种方式存在多模态知识表征困难、难以将多源异构的多模态数据嵌入到统一的低维向量空间中进行知识表示的问题。Chen等人[91]提出一种实体对齐的方法，使得知识融合模块能够集成不同模态的知识表示。同时，为了减少不同模态资源之间的结构性差异，Guo 等人[92]提出一种实体对齐方法，对KG中的图像信息、三元组信息和属性信息进行知识表示，并最小化公共空间中跨多模态知识的两个不同KG的对齐实体之间的距离，为多模态知识集成提供了很好的解决办法。文献[93]提出一种对抗训练的方式来学习模态不变的嵌入空间，以缩小不同模态资源之间的差距，促进了多模态知识融合的效率。

实体对齐技术的优化依赖于教育知识表示的基础研究，所以未来的一段时间内，多模态资源在知识表示空间中存在的语义鸿沟和结构鸿沟仍然是实体对齐技术的关键性难题，后续可以从特征表示的相似性出发，对相似度模型进行探究，同时也可以考虑对抗生成网络等其他方案。

# 4教育知识图谱相关应用

融合多模态资源的教育知识图谱可以帮助学习者选择更具针对性的学习资源和更好的学习方式[7]。同时，其也为实现多模态课程知识图谱、个性化学习资源的推荐、知识问答、知识检索与可视化、学情信息建模等智能教育应用提供了较好的发展空间。

# 4.1多模态课程知识图谱

在教学场景中，会产生很多种模态的课程资源，帮助学生理解相关的知识点，但当前的课程资源往往是单独存在的，没有与知识点建立很好的联系，不能发挥多模态资源对知识点的解读作用。同时，课程知识的整体框架多是以书中的章节目录关系呈现的，而章节中所包含的细小知识点和知识点之间的关系并不是十分明确，从学生的角度来讲，难以对前后所学的知识建立联系，接受知识仍然很困难。通过对权威的教材和互联网学习平台中大量的课程资源进行知识挖掘，多模态课程知识图谱能够有效地解决上述问题，为课程知识建模提供帮助[94,95]。

MOOC平台蕴涵着丰富的课程资源，王亮[9使用BiLSTM-CRF模型对学科资源进行实体识别，获取课程知识实体，然后将MOOC课程资源目录中的层级关系和知识实体的来源(学习视频标题、练习题题目、讨论问题的标题)作为实体之间的初始关系，构建了包含微视频、练习题和讨论区问题等教学资源的《C语言程序设计》课程知识图谱。祁晓慧等人[87]运用CNN $+$ BiLSTM-CRF模型结合学科词典对《数据结构》课程教材和简书网站的文本资源进行实体识别，然后使用Attention+BiLSTM模型抽取知识点之间的关系，在此基础上，通过语音识别软件将课堂语音识别成文字，进一步链接实体对应的语音资源，构建了包含语音和文本资源的多模态课程知识图谱。文献[97]依据图7所示的研究框架，针对MOOC平台中大学电路课程的理论和实验课程内容构建了多模态课程知识图谱，在此基础上，讨论了知识点检索、个性化学习路径推荐、智能教育分析等应用。

![](images/dbc62edf59030df23d8bed4117ea12a637eb3d61ba16b1c9fafd18981d2d1b26.jpg)  
图7多模态电路课程知识图谱研究框架  
Fig.7Research framework ofknowledge graph of multimodal circuit course

从学科知识融合的角度来说，在内容上有关联的课程知识是可以被连接在一起的，但不同课程的内容不同，体系结构也不同，难以实现多学科知识的关联。因此，面对这样的问题，亟需制定一个应用在教育领域的普适的多模态课程知识图谱的构建规范，既可以加快单一模态到多模态课程知识图谱的研究步伐，也可以促进相互关联的多模态课程资源进行有效地融合，更好地为智能化教育应用提供服务。

# 4.2个性化学习资源推荐

依据学习者之间不同的学习进度，为他们提供适合自己的教学资源，促使其个性化发展是智能教育场景的基本要求。因此，如果能为学习者提供类似于个性化推荐学习视频这样的多元化应用形式，在一定程度上能够激发学习者的热情，提高学习效率。教育知识图谱能够为学习者集成多模态的学习内容，并依据学习者的学习进度为其推荐相关的学习资源。同时，利用教育知识图谱中实体之间丰富的语义关系表示，有助于改善传统的推荐算法中存在的数据稀疏、冷启动等问题，进一步提升推荐系统的质量。所以近年来，将教育知识图谱应用于知识资源推荐的研究逐渐开始涌现。

文献[98]构建了计算机网络课程知识图谱，结合知识点与习题生成信息向量，通过分析学习者的日志数据，利用错误答案练习题与知识点之间的相似度为学习者推荐期末习题。

吴昊等人[99]提出一种融合知识图谱的多任务特征推荐算法(Multi-LayerKnowledge GraphRecommendation，MLKR)，有效地解决了在线课程资源缺失导致推荐效果不理想的问题。文献[100]提出一个端到端的多模态兴趣相关项目相似性模型来提供基于多模态数据源的推荐，证明了融合多模态数据表示的方法能够有效地提升推荐系统的性能。Sun 等人[101]将多模态资源应用于基于知识图谱的推荐系统中，并使用图注意力机制描述图片信息，使得推荐结果更准确。文献[102]采用协同过滤结合知识图谱特征的方法(CollaborativeKnowledgeBaseEmbedding,CKE)进行资源推荐，着重利用知识图谱的文本信息、结构化信息和视觉信息进行嵌入，补充资源信息的特征表示，并通过联合学习用户信息与资源的知识表示，解决了传统的基于知识图谱的推荐技术中用户与推荐资源交互稀疏的问题，提升了推荐系统的质量，其推荐流程如图8所示。

![](images/bab65e0b4067fa3f41b97017cd17835d8c794dd6c6fa9d10223270e13f0fd963.jpg)  
图8基于CKE 的推荐系统流程图  
Fig.8Flow chart of recommendation system based on CKE

目前，基于教育知识图谱的资源推荐研究还处于初步阶段，多模态资源能够为学习者提供适合自己的多元化学习方式，但如何利用语义多样和结构多元的多模态资源解决传统的学习资源推荐方法中存在的数据稀疏等问题，是研究者当前应重点关注的问题。

# 4.3 知识问答

目前，在问答系统中引入图像等多模态信息的研究受到教育界的广泛关注，无论是在问题理解还是答案呈现方面，自然语言能够表达的信息都很有限，结合多模态信息可以为知识问答系统带来多元的知识表示形式，从多个角度精准刻画学习者的需求。教育知识图谱能够为体量巨大且结构关系错综复杂的学科知识处理提供支撑，然后根据学习者的个性化知识需求从图谱中查询或者经过复杂关系推理，得到能够满足学习者需求的教育知识解释。

Zhao[103]等人设计了一个多模态领域知识图谱驱动的智能问答系统，结合智能问答和图像识别技术，实现了高效的信息查询方案。文献[104结合图像和文本信息构建了上下文形式的图谱，解决了从长文本课程中提取知识特征并将其与视觉特征融合的问题，在教科书问答方面提供了很好的解决办法。

与学习者的需求相适应，学习者不再局限于一些简单的知识问答。例如，在大学计算机《数据结构》课程里的“逻辑结构是什么？”、“线性表是什么？”这样简单的问题，现实场景中学生更多关注于“逻辑结构中和线性表类型相同的数据结构有哪些?"等一系列涉及知识图谱中多个节点的复杂问题。解决这类问题，需要依据多跳推理的方式，从一条三元组找到另一条三元组，直至找到问题的解答。目前国内外基于多跳推理的知识图谱问答研究有很多，但融合多模态信息进行知识图谱的多跳推理研究却鲜有提及，如何利用丰富的多模态内容表示为复杂问题的多跳推理研究提供帮助，是教育知识图谱的一个重要研究内容。

# 4.4知识检索与可视化

为了增强学习者对知识体系的认知，提供全面、多层次的知识点检索与可视化展示功能，学者们将多模态知识融合到教育知识图谱中，其主要是以构建好的教育知识图谱为对象，将知识网络以图的形式展示给学习者，也要在学习者检索某个特定知识点时，将与该知识点相关的其他知识点等资源展示出来。

文献[87]基于构建好的《数据结构》课程知识图谱搭建知识检索系统，实现了课程底层的知识点检索路径，使得学生学习的效率得以大幅提升。Rafailidis 等人[105]提出一个多模态内容检索框架，通过构造多模态空间捕捉多模态内容之间的语义关联，支持学习者对文献中不同模态的资源(图像、音频、3D、视频和文本)进行统一检索。Alberts 等人[106]构建了VisualSem知识图谱，其包括多个图像以及视觉相关关系的节点，并在知识图谱的基础上，发布了一个多模态检索模型，可以使用图像或句子作为输入，检索知识图谱中的实体。Kannan等人[107]利用知识图谱集成多模态信息，并支持学习者对文献中的文本、图像和源代码进行查询。

基于教育知识图谱的知识检索与可视化功能不仅要展示一个知识点相对应的不同模态的教学内容，更重要的是，如何能通过自身已有的知识关系，推理出新的多样化关系，满足学习者对知识的深度需求，多模态资源在该过程中扮演着重要的角色，未来相关研究者应在此方向中投入更多的精力。

# 4.5学情信息建模

智能教育和传统的教育方式很大的一个区别就是能够依据学习者自身的学习状态和知识掌握情况进行调整教学。这其中，具有挑战性的工作就是对学习者的学情进行建模分析。该过程需要充分发挥教育知识图谱在数据处理、分析等层面的技术优势，利用信息抽取、情感分析以及数据可视化等技术，以标签化的信息描述学习者的多维特征，为不同阶段的学习作出引导和预测[108]。

单一模态数据能够表征的学情信息很有限，钟薇等人[109]通过课堂音视频录像和讨论区发帖信息追踪学习者的学习轨迹，获取了学习者的认知水平信息。Nandi等人[10]综述了在e-learning中挖掘多模态数据进行学习者情感识别的研究。Camacho 等人[11]利用物联网和可穿戴设备采集学习者的行为模式，并使用机器学习技术和多模态学习分析(MultimodalLearningAnalytics，MMLA)方法构建了能够解释学生参与学习情况的模型。Buitelaar等人[1l2]提出了一个可以从文本、音频和视频中有效挖掘用户情感信息的开源工具，并使用知识图谱进行可视化，为学习者学情信息的全方位表征提供了可能性。

当前，针对学习者学情信息建模的方法只停留在浅显的层次，并不能深层捕捉学习者的情感和认知特征。未来可以使用眼动追踪、脑电感应等多模态生物识别技术，结合课堂音视频录像信息，深度挖掘学习者的行为、心理和生理层数据，为学习者成绩预测、个性化学习路径生成等任务提供支持。

# 5 问题与挑战

面向智能教育应用的多模态数据处理方法日益成熟，将多模态资源融入教育知识图谱的研究已经成为了必然的趋势。然而，随着教育知识图谱处理的知识资源涵盖范围的不断扩大，很多问题随之产生。接下来，将从内涵、技术和应用研究的角度，对融合多模态资源的教育知识图谱研究中存在的问题与挑战进行总结。

a)对于教育知识图谱的认知有待进一步研究

目前，学术界对于教育知识图谱还没有形成统一的定义，相关研究者多是从知识管理、学习者认知以及教育信息服务等有限的研究视角对教育知识图谱的概念进行阐述，对其认知较为局限。后续应提供更全面的研究维度，拓宽学术界对于教育知识图谱的认知。例如，深度挖掘、融合和分析多模态教育数据特征，为智能教育应用提供服务的“多模态学习分析”研究视角等[113,114]，对教育知识图谱进行深层解读。

b)缺乏高质量的教育资源数据集

现阶段，深度学习技术被广泛应用于教育知识图谱的构建过程中，而深度学习模型的训练需要大量的数据集作为支撑。

目前，教育领域的高质量数据集较少，多数研究者依靠自己构建数据集来完成教育知识图谱构建的任务，该种方式耗时耗力，且不能完全体现相关模型的说服力。因此，加速对 MOOC 等传统开源学习网站和真实教学场景中多模态教学资源地采集与处理，丰富和完善教学资源数据集，是教育知识图谱的重点研究内容之一。

c)对于以词为单位的文本分析任务，BERT模型不能直接获取高质量的领域词向量

教育知识图谱的构建离不开自然语言技术的处理，而当前自然语言处理研究中炙手可热的研究方向当属以BERT为代表的预训练模型。目前，BERT多数是使用字向量表示文本，无法直接获取符合领域需求的高质量的词级向量，对实体识别等以词为处理单位的文本分析任务造成了一定的困扰下一阶段，研究者可以考虑利用少量的领域标注数据，例如课程词典或者结构化的教育知识库，对BERT模型进行微调以生成高质量的领域词向量[115,116]，支撑面向教育数据的以词为单位的文本分析任务。

d)教育知识图谱的知识评估方法较为匮乏

教育领域对于知识的正确性要求极为严苛，保证教育知识图谱的数据质量是极为重要的。目前，教育知识图谱的知识评估多数依靠专家知识或者教师的经验去判别相关数据是否正确以及多样化关系是否适用，不仅消耗大量的人力，而且不同专家与教师之间的主观评估容易导致评估结果的差异性。因此，制定统一的评估方法或者评估标准，在保证教育知识图谱数据准确性的基础上体现知识的多样化特性，对于教育知识图谱来说是至关重要的。

e)教育资源链接手段单一，难以准确地捕捉多模态数据自身的特征

分析当前的研究进展可知，教育知识图谱对多模态资源的链接手段较为单一，多数是将多模态数据转换成文本数据，然后使用实体链接技术添加多模态资源。下一阶段，利用多模态数据的元数据融入教育知识图谱的方式仍然会是一个优先选择项，但这种处理方式存在片面性的问题，不能准确地挖掘多模态资源自身的特征。因此，在教育知识图谱的构建过程中找到能够准确挖掘多模态数据特征的方法，是未来研究者应持续努力的方向。

f)现有的结构化教育知识库难以满足智能教育机器人的发展需求

目前，市场上出现的Siri、“小度机器人”等智能机器人以其良好的交互体验获得了较高的评价。以人机交互为主要知识获取形式的智能教育机器人引起了相关研究者的注意。然而，智能教育机器人需要大量的结构化数据作为支撑，现有的结构化教育知识库难以满足其发展需求。使用文本、图像、动画等多种方式呈现教学内容的教育知识图谱在知识处理与交互方面可以发挥较好的作用。因此，下一步的研究方向应更多地关注教育知识图谱与智能教育机器人的结合与应用

g)基于教育知识图谱的教育信息服务局限于多模态课程知识图谱研究中，并没有同相关的教学活动建立广泛的联系

在教育信息服务领域，融合多模态资源的教育知识图谱应用已经开始向多方面拓展，但目前仍局限在多模态课程知识图谱研究中，并没有同相关的教学活动建立广泛的联系。随着相关技术的成熟，未来的研究可以深入到教学场景中，突破课程知识图谱的限制，将学科知识体系、教学资源和受教育者学习轨迹等教学活动进行关联，实现教与学过程的可视化，朝着智能教育应用的方向迈进，最大限度地促进教育信息服务。

# 6 结束语

教育知识图谱通过处理大量无序、结构复杂的多模态教育数据，使其形成结构化的、能够被直接利用的知识体系，是人工智能时代对教育知识建模的有效手段。同时，通过教育知识图谱结构化的多模态知识，能够为基于深度学习的数据挖掘技术提供先验知识，提升挖掘的准确度与效率。本文从多模态资源的角度，对教育知识图谱进行综述并得出以下结论。多模态资源对教育知识图谱构建技术性能地提升具有关键性的作用，是未来一段时间教育图谱构建技术改进的重要研究方向，融合多模态资源的教育知识图谱在多模态课程知识图谱、个性化学习资源推荐、知识问答、知识检索与可视化、学情信息建模等方面都有了积极的尝试，但都还处于探索阶段。未来应从教育知识图谱的认知、教育资源数据集、预训练模型以及教育知识图谱的知识评估方法等方面继续研究，为教育知识图谱在智能教育领域的应用提供有效地支撑。

# 参考文献：

[1] 黄荣怀.智慧教育的三重境界：从环境、模式到体制[J].现代远程 教育研究,2014 (06):3-11.(Huang Ronghuai. Three realms of smart education: smart learning environment,ICT teaching model and modern educational system [J].Modern Distance Education Research,2014 (O6): 3-11.)   
[2]王鑫，邹磊，王朝坤，等．知识图谱数据管理研究综述[J].软件学 报,2019,30 (07):2139-2174.(Wang Xin,Zou Lei,Wang Chaokun,et al.Research on knowledge graph data management: a survey[J].Journal of Software,2019,30(7):2139 (2174.)   
[3]祝智庭，俞建慧，韩中美，等．以指数思维引领智慧教育创新发展 [J]．电化教育研究,2019,40 (01): $5 - 1 6 + 3 2$ (Zhu Zhiting,Yu Jianhui, Han Zhongmei, et al. Innovative development of smarter education led by exponential thinking (in Chinese)[J].e-Education Research,2019.40 (01): $5 - 1 6 + 3 2 .$ ）   
[4]祝智庭，许秋璇，吴永和.教育信息化新基建标准需求与行动建议 [J]．中国远程教育,2021(10): $1 - 1 1 + 7 6$ (Zhu Zhiting,Xu Qiuxuan,Wu Yonghe.Building new infrastructure for educational informatization: standards and implementation [J].Distance Education in China,2021 (10): $1 - 1 1 + 7 6 .$ ）   
[5] 余胜泉，彭燕，卢宇．基于人工智能的育人助理系统[J].开放教育 研究,2019,25(1).(Yu Shengquan,Peng Yan,Lu Yu.An artificial intelligence assistant system for educating people: the structure and function of"AIEducator”[J].Open Education Research,2019,25(1).)   
[6]李振，周东岱，王勇.“人工智能+"视域下的教育知识图谱：内涵、技 术框架与应用研究[J].远程教育杂志,2019,37(04):42-53.(Li Zhen, Zhou Dongdai,Wang Yong.Research of educational knowledge graph from the perspective of"artificial intelligence+":connotation,technical framework and application [J]. Journal of Distance Education.2019,37 (04): 42-53.)   
[7] 李艳燕，张香玲，李新，等．面向智慧教育的学科知识图谱构建与创 新应用[J]．电化教育研究,2019,40(08):60-69.(Li Yanyan,Zhang Xiangling,Li Xin,et al.Construction and innovative application of discipline knowledge graph oriented to smart education [J].e-Education Research,2019,40 (08):60-69.)   
[9]Wang Chengyu, Gao Ming,He Xiaotel, et al. Chalenges in Uhinese knowledge graph construction [C]// 2015 31st IEEE International Conference on Data Engineering Workshops. Piscataway: IEEE,2015: 59-61.   
[10] Auer S,Bizer C,Kobilarov G,et al.Dbpedia:A nucleus for a web of open data [M]/ The semantic web.Springer,Berlin,Heidelberg,2007: 722-735.   
[11] VrandecicD，KrtoetzschM.Wikidata:afree collaborative knowledgebase [J]. Communications of the Acm,2014,57 (10): 78-85.   
[12] Ferrada S, Bustos B,Hogan A. IMGpedia: a linked dataset with contentbased analysis of wikimedia images [C]// International Semantic Web Conference.Switzerland: Springer, Cham,2017: 84-93.   
[13] Liu Ye,Li Hui, Garcia-DuranA,etal. MMKG: multi-modal knowledge graphs [C]//European Semantic Web Conference. Switzerland: Springer, Cham, 2019: 459-474.   
[14] Wang Meng,Wang Haofen, Qi Guilin,et al. Richpedia: a large-scale, comprehensive multi-modal knowledge graph [J]. Big Data Research, 2020,22 (10): 100159.   
[15]党占海，赵蓉英，陈瑞，等．油料作物研究的知识图谱分析[J]．中 国农业大学学报，2011，16(03):178-186.(Dang Zhanhai,Zhao Rongying,Chen Rui,et al. Knowledge mapping analysis on the research of oil crops [J]. Journal of China Agricultural University,201,16 (3): 178-186.)   
[16]侯梦薇，卫荣，陆亮，等．知识图谱研究综述及其在医疗领域的应用 [J]．计算机研究与发展,2018,55(12):13.(Hou Mengwei,Wei Rong, Lu Liang,et al. Research review of knowledge graph and its application in medical domain [J]. Journal of Computer Research and Development, 2018, 55 (12): 13.)   
[17]陈晓军，向阳．企业风险知识图谱的构建及应用[J].计算机科学， 2020,47 (11): 237-243.(Chen Xiaojun,Xiang Yang.Construction and application of enterprise risk knowledge graph [J]. Computer Science, 2020,47 (11): 237-243.)   
[18] Zhang Xu. Research on enterprise knowledge unified retrieval based on industrial big data [C]// 2018 Sixth International Conference on Advanced Cloud and Big Data(CBD).Piscataway:IEEE,2018:130- 134.   
[19] Gao Lingchao,Yao Limeng,Yang Zhiwei,et al. Research on hybrid index method of double-layer $\scriptstyle \mathrm { \mathrm { B } } +$ tree for power big data considering knowledge graph [J].Journal of Physics: Conference Series,2021,1771 (1): 012004 (8pp).   
[20] Wang Xiaoli,Wang Yuan,Gao Chuchu,et al.Automatic diagnosis with efficient medical case searching based on evolving graphs [J].IEEE Access,2018,6: 53307-53318.   
[21] Zhang Xiaoming,Sun Xiaoling,Xie Chunjie,et al. From vision to content: construction of domain-specific multi-modal knowledge graph [J]. IEEE Access,2019,PP (99): 1-1.   
[22]王娟，陈世超，王林丽，等．基于CiteSpace 的教育大数据研究热点 与趋势分析[J].现代教育技术，2016,26(02):5-13.(Wang Juan, Chen Shichao,Wang Linli,et al. The analysis of research hot spot and trend on big data in education based on cite space[J]. Modern Educational Technology,2016,26 (02): 5-13.)   
[23] Chen Penghe,Lu Yu,Zheng VW,et al. KnowEdu: a system to construct knowledge graph for education [J]. IEEE Access,2018,PP (99): 1-1.   
[24] Yu Jifan,Luo Gan, Xiao Tong,et al. MOOCCube: a large-scale data repository for NLP applications in MOOCs [C]//Proceedings of the 58th Anual Meeting of the Association for Computational Linguistics.

Stroudsburg:ACL,2020:3135-3142.

[25] Zheng Yang,Liu Ruifang,Hou Junmeng.The construction of high educational knowledge graph based on MOOC [C]// 2017 IEEE 2nd Information Technology， Networking，Electronic and Automation Control Conference (ITNEC).Piscataway: IEEE,2017: 260-263.

[26]陆星儿，曾嘉灵，章梦瑶，等．知识图谱视角下的 MOOC 教学优化 研究[J]．中国远程教育,2016(07): $5 . 9 \substack { + 7 9 }$ . (Lu Xinger, Zeng Jialing, Zhang Mengyao,et al. Using knowledge graphs to optimize m oo c instruction [J].Distance Education in China,2016 (07): $5 . 9 \substack { + 7 9 . }$ ）   
[27]万海鹏，汪丹．基于大数据的牛顿平台自适应学习机制分析—“教 育大数据研究与实践专栏”之关键技术篇[J]．现代教育技术,2016, 26(05):5-11.(Wan Haipeng,Wang Dan.Investigation on adaptive learning mechanism of big data based on knewton platform ——the key technology of"research and practice column about big data in education" [J].Modern Educational Technology,2016 (05): 5-11.)   
[28]杨开城．论课程的易理解性与知识建模技术[J]．电化教育研究, 2011 (06):10-14.(Yang Kaicheng. On the comprehension of curriculum and knowledge modeling technology [J].Research of Audio-visual Education,2011 (06): 10-14.)   
[29]张波，金玉鹏，张倩，等．试论一种新型在线教育资源大数据组织框 架[J].中国电化教育,2018(03): 41-46.(Zhang Bo,Jin Yupeng,Zhang Qian,et al.A novel organizing framework for the online education resource big data [J]. China Educational Technology,2018 (O3): 41-46.)   
[30]余胜泉，李晓庆．区域性教育大数据总体架构与应用模型[J]．中国 电化教育,2019 (01):18-27. (Yu Shengquan,Li Xiaoqing.The studyon architecture and application model about regional education big data [J]. China Educational Technology,2019 (01):18-27.)   
[31]钟绍春，唐烨伟．人工智能时代教育创新发展的方向与路径研究 [J]．电化教育研究,2018,39 (10): $1 5 - 2 0 + 4 0$ ：(Zhong Shaochun,Tang Yewei.Research on the orientation and route of educational innovative development in the age of artificial intelligence[J].e-Education Research,2018,39 (10): $1 5 - 2 0 + 4 0 .$ ）   
[32]刘桥，李杨，段宏，等．知识图谱构建技术综述[J].计算机研究与 发展，2016,53 (3): 582.(Liu Qiao,Li Yang,Duan Hong,et al. Knowledge graph construction techniques [J]. Journal of Computer Research and Development,2016,53 (3): 582.)   
[33]金鑫．面向Web 信息资源的领域本体模型自动构建机制的研究[J]. 计算机科学,2012,39 (6):4.(Jin Xing.Research on mechanism of automatic construction of ontologies for web information resources [J]. Computer Science,2012,39 (6): 4.)   
[34]童名文，牛琳，杨琳，等．课程本体自动构建技术研究[J].计算机 科学,2016,43 (S2): 108-112.(Tong Mingwen,Niu Lin, Yang Lin,et al. Research on technique ofcourse ontology automatically constructing [J]. Computer Science,2016,43 (S2): 108-112.)   
[35] Wang Jingyun, Flanagan B,Ogata H. Semi-automatic construction of ontology based on data mining technique [C]// 2017 6th IIAI International Congress on Advanced Applied Informatics (IIAI-AAI) . Piscataway: IEEE,2017: 511-515.   
[36] Cortes C,Vapnik V.Support-vector networks [J]. Machine learning,1995, 20 (3): 273-297.   
[37] Pearl J.Probabilistic reasoning in inteligent systems: networks of plausible inference [M]. San Francisco: Morgan Kaufmann,1988.   
[38] Jelinek F. Statistical methods for speech recognition [M]. Cambridge: MIT Press,1997.   
[39] LeCun Y,BotouL,Bengio Y,etal. Gradient-based learningappliedto documentrecognition[J].Proceedings ofthe IEEE,1998,86(11): 2278-2324.   
[40]Mikolov T,Karafiat M,Burget L,et al. Recurrent neural network based language model [C]// Interspeech.2010,2 (3):1045-1048.

[42] Vaswani A, Shazeer N,Parmar N,et al.Attention is all you need [C]// Advances in neural information processing systems,Cambridge:MIT Press.2017: 5998-6008.

[43] Devlin J，Chang M W,Lee K,et al.Bert: Pre-training of deep bidirectional transformers for language understanding[J].arXiv preprint arXiv: 1810.04805,2018.   
[44]李冬梅，张扬，李东远，等．实体关系抽取方法研究综述[J].计算 机研究与发展,2020,57(07):1424-1448.(LiDongmei,Zhang Yang,Li Dongyuan, et al.Review of entity relation extraction methods [J]. Journal of Computer Research and Development,2020,57 (07): 1424-1448.)   
[45]杨波，杨美芳．知识图谱研究综述及其在风险管理领域应用[J].小 型微型计算机系统,2021,42(08):1610-1618.(Yang Bo,Yang Meifang. Research review of knowledge graph and its application in risk management [J]. Journal of Chinese Computer Systems,2012, 42 (08): 1610-1618.)   
[46] Graves A, Jyurgen Schmidhuber. Framewise phoneme classification with bidirectional LSTM and other neural network architectures [J]. Neural Networks,2005,18 (5-6): 602-610.   
[47] Wollmer M,Eyben F,Graves A,et al. Bidirectional LSTM networks for context-sensitive keyword detection in a cognitive virtual agent framework [J].Cognitive Computation,2010,2 (3): 180-190.   
[48] Zhou Peng,Shi Wei,Tian Jun,et al.Attention-based bidirectional long short-term memory networks for relation classification [C]/ Proceedings of the 54th annual meeting of the association for computational linguistics. Stroudsburg: ACL,2016 (volume 2: Short papers): 207-212.   
[49] Huang Zhiheng,Xu Wei, Yu Kai. Bidirectional LSTM-CRF models for sequence tagging [J].arXiv preprint arXiv: 1508.01991,2015.   
[50] Yan Rongen, Jiang Xue,Dang Depeng.Named entity recognition by using XLNet-BiLSTM-CRF[J]. Neural Processing Letters,2021: 1-18.   
[51] Wei Kangwei,Wen Bin.Named entity recognition method for educational emergency field based on BERT [C]/ 2021 IEEE 12th International Conference on Software Engineering and Service Science (ICSESS).Piscataway: IEEE,2021:145-149.   
[52] Moon S, Neves L, Carvalho V. Multimodal named entity recognition for short social media posts [J]. arXiv preprint arXiv: 1802.07862,2018.   
[53] Zheng Changmeng，Wu Zhiwei,Wang Tao，et al. Object-aware multimodal named entity recognition in social media posts with adversarial learning [J].IEEE Trans on Multimedia,202o,PP (99): 1-1.   
[54] Liu Luping,Wang Meiling,Zhang Mozhi,et al. UAMNer: uncertaintyaware multimodal named entity recognition in social media posts [J]. Applied Intelligence,2021: 1-17.   
[55] Sui Dianbo,Tian Zhengkun,Chen Yubo,et al.A Large-Scale Chinese Multimodal NER Dataset with Speech Clues [C]// Proceedings of the 59th Annual Meeting of the Association for Computational Linguistics and the lth International Joint Conference on Natural Language Processing. Stroudsburg: ACL,2021 (Volume 1: Long Papers): 2807-2818.   
[56]鄂海红，张文静，肖思琪，等．深度学习实体关系抽取研究综述[J]. 软件学报,2019,30(06):1793-1818.(E Haihong,Zhang Wenjing,Xiao Siqi, et al. Survey ofentity relationship extraction based ondeep learning [J]. Jourmal of software,2019,30 (06): 1793-1818.)   
[57] Al-Muhaideb S, Menai MEB.Evolutionary computation approaches to the curriculum sequencing problem [J].Natural Computing,2011,10 (2): 891-920.   
[58] Limongelli C,Sciarone F, Temperini M,et al.Adaptive learning with the LS-plan system: a field evaluation [J]. IEEE Trans on Learning Technologies,2009,2(3): 203-215.   
[60] Pan Liangming,Li Chengjiang,Li Juanzi,et al. Prerequisite relation learning for concepts in moocs [C]// Proceedings of the 55th Annual Meeting of the Association for Computational Linguistics,Stroudsburg: ACL,2017 (Volume 1: Long Papers): 1447-1456.   
[61] Manrique R,Pereira B,Marino O,et al. Towards the identification of concept prerequisites via knowledge graphs [C]// 2019 IEEE 19th International Conference on Advanced Learning Technologies (ICALT) Piscataway: IEEE,2019,2161: 332-336.   
[62] Liu Chunyang,Sun Wenbo,Chao Wenhan,et al. Convolution neural network for relation extraction [C]// International Conference on Advanced Data Mining and Applications.Springer, Berlin, Heidelberg, 2013: 231-242.   
[63] Zeng Daojian,Liu Kang,Lai Siwei,et al.Relation clasification via convolutional deep neural network [C]// Proceedings of COLING 2014, the 25th International Conference on Computational Linguistics: Technical Papers.New York: ACM Press,2014: 2335-2344.   
[64] Xu Kun,Feng Yansong,Huang Songfang，et al. Semantic relation classification via convolutional neural networks with simple negative sampling [J].arXiv preprint arXiv: 1506.07650,2015.   
[65] Santos C N,Xiang B,Zhou B.Classifying relations by ranking with convolutional neural networks [J].arXiv preprint arXiv:1504.06580, 2015.   
[66] Socher R, Huval B,Manning C D,et al. Semantic compositionality through recursive matrix-vector spaces [C]// Proceedings of the 2012 joint conference on empirical methods in natural language processing and computational natural language learning. Stroudsburg: ACL,2012: 1201-1211.   
[67] Hashimoto K,Miwa M,Tsuruoka Y,et al. Simple customization of recursive neural networks for semantic relation classification [C]// Proceedings of the 2013 Conference on Empirical Methods in Natural Language Processing. Stroudsburg: ACL,2013: 1372-1376.   
[68] Xu Yan,Mou Lili,Li Ge,et al. Classifying relations via long short term memory networks along shortest dependency paths [Cl// Proceedings of the 2015 conference on empirical methods in natural language processing. Stroudsburg: ACL,2015: 1785-1794.   
[69] Mintz M,Bils S,Snow R,et al. Distant supervision for relation extraction without labeled data [Cl/ Proceedings ofthe Joint Conference of the 47th Annual Meeting of the ACL and the 4th International Joint Conference on Natural Language Processing of the AFNLP. Stroudsburg: ACL,2009:1003-1011.   
[70] Zeng Daojian,Liu Kang,Chen Yubo,et al.Distant supervision for relation extraction via piecewise convolutional neural networks $[ \mathrm { C } ] / /$ （204 Proceedings of the 2O15 conference on empirical methods in natural language processing. Stroudsburg: ACL,2015: 1753-1762.   
[71]Lin Yankai, Shen Shiqi, Liu Zhiyuan,et al. Neural relation extraction with selective attention over instances [C]// Proceedings of the 54th Annual Meeting of the Association for Computational Linguistics, Stroudsburg: ACL,2016 (Volume 1: Long Papers): 2124-2133.   
[72]杨东明，杨大为，顾航，等．面向初等数学的知识点关系提取研究 [J]．华东师范大学学报：自然科学版，2019(05):53-65.(Yang Dongming, Yang Dawei, Gu Hang,et al. Research on knowledge point relationship extraction for elementary mathematics [J].Journal of East China Normal University: Natural Science,2019 (05): 53-65.)   
[73] Vas R.Educational ontology and knowledge testing[J].Electronic Journal of Knowledge Management, 2007,5 （1). 算机应用研究，2021,38(04):961-967.(Zhang Zhenghang,Qian Yurong,Xing Yanni,et al. Survey of knowledge representation learning methods [J].Application Research of Computers,2021,38 (04): 961- 967.)   
[75] Bordes A, UsunierN,Garcia-Duran A,et al. Translating embeddings for modeling multi-relational data [J].Advances in neural information processing systems,2013,26   
[76] Lei Zhenfeng,Sun Yuan,Nanehkaran YA,et al.A novel data-driven robust framework based on machine learning and knowledge graph for disease classification [J].Future Generation Computer Systems,2020, 102: 534-548.   
[77] Ji Guoliang,He Shizhu, Xu Liheng,et al. Knowledge graph embedding via dynamic mapping matrix [C]// Proceedings of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing, Stroudsburg: ACL,2015 (Volume 1: Long Papers): 687-696.   
[78] Wang Zikang,Li Linjing,Li Qiudan,et al.Multimodal data enhanced representation learning for knowledge graphs[C]//2019 International Joint Conference on Neural Networks (IJCNN).Piscataway: IEEE, 2019: 1-8.   
[79] Xie Ruobing,Liu Zhiyuan,Luan Huanbao,et al.Image-embodied knowledge representationlearing[J].arXiv preprint arXiv:1609.07028, 2016.   
[80]缴霖境，闫威．融合实体概念描述与图像特征的知识图谱表示学习 研究[J].计算机应用研究,2021,38(06):1759-1764.(Jiao Linjing, Yan Wei.Research on knowledge graph representation learning combining entity concept description and image features[J].Application Research of Computers,201,38 (06): 1759-1764.)   
[81]王会勇，论兵，张晓明，等．基于联合知识表示学习的多模态实体对 齐[J].控制与决策,2020,35(12):2855-2864.(Wang Huiyong,Lun Bing,Zhang Xiaoming,et al. Multi-modal entity alignment based on joint knowledge representation learning [J]. Control and Decision,2020, 35 (12): 2855-2864.   
[82]陈曦，梅广，张金金，等．融合知识图谱和协同过滤的学生成绩预测 方法[J].计算机应用,2020,40(02):595-601.(Chen Xi,Mei Guang, Zhang Jinjin,etal.Student gradeprediction methodbasedonknowledge graph and collaborative filtering [J]. Journal of Computer Applications, 2020,40 (02): 595-601.)   
[83] Yang Bishan,Yih W,He Xiaodong，et al.Embedding entities and relations for learning and inference in knowledge bases [J]. arXiv preprint arXiv: 1412. 6575,2014.   
[84]赵晓娟，贾焰，李爱平，等．多源知识融合技术研究综述[J].云南 大学学报：自然科学版,2020,42(03):459-473.(Zhao Xiaojuan,Jia Yan,Li Aiping,et al.A survey ofthe research on multi-source knowledge fusion technology[J]. Journal of Yunnan University: Natural Sciences Edition. 2020,42 (03): 459-473.)   
[85] Chen R C, Bau C T, Yeh C J. Merging domain ontologies based on the WordNet systemand fuzzy formalconcept analysis techniques [J]. Applied Soft Computing,2011,11 (2): 1908-1923.   
[86] Bhattacharya I, Getoor L. Collective entity resolution in relational data [J].ACM Trans on Knowledge Discovery from Data(TKDD),2007,1(1): 5-es.   
[87]祁晓慧．多模态课程知识图谱构建与应用研究[D]．吉林大学,2020. (QiXiaohui. Researchonconstructionandapplicationof multimodalcuriculum knowledge graph,[D]. Jilin University,2020.)   
[88]李钝，薛昊原，李伦，等．面向教学资源的实体链接算法[J]．南京 大学学报：自然科学版,2015,51(4):901-908.(Li Dun,Xue Haoyuan, LI Lun,et al. Entity linking for educational resources [J]. Jourmal of Nanjing University: Natural Science,2015,51 (4): 901-908.)   
[89]周炫余，唐祯，唐丽蓉，等．基于多源异构数据融合的初中数学知识 图谱构建[J]．武汉大学学报（理学版），2021,67(02):118-126. (Zhou Xuanyu, Tang Zhen,Tang Lirong,et al. Construction of junior high school mathematics knowledge graph based on Multi-Source heterogeneous data fusion [J]. Journal of Wuhan University: Natural Science Edition,2021,67 (02): 118-126.)   
[90] Chang M D，Forbus K D.Towards interpretation strategies for multimodal instructional analogies[C]// Proceedings of the 28th International Workshop on Qualitative Reasoning (QR2015).2015.   
[91] Chen Liyi,Li Zhi,Wang Yijun,et al.MMEA: entity alignment for multimodal knowledge graph [C]// International Conference on Knowledge Science,Engineering and Management. Switzerland: Springer, Cham, 2020: 134-147.   
[92] Guo Hao,Tang Jiuyang,Zeng Weixin,et al.Multi-modal entity alignment in hyperbolic space[J].arXiv preprint arXiv: 2106.03619,2021.   
[93] Mai Sijie,Hu Haifeng,Xing Songlong.Modality to modality translation: An adversarial representation learning and graph fusion network for multimodal fusion [C]// Proceedings of the AAAI Conference on Artificial Intelligence.Menlo Park, CA: AAAI,2020,34 (01): 164-172.   
[94] Haquin D M.Representation and communication of knowledge in secondary school: Multimodal discourse analysis of school teaching materials of history and biology[J]. On-omazein,2013,27(1): 35-52.   
[95] Dang Furong, Tang Jintao,Li Shasha. MOOC-KG: A MOOC knowledge graph for cross-platform online learning resources [C]// 2019 IEEE 9th International Conference on Electronics Information and Emergency Communication (ICEIEC) . Piscataway: IEEE,2019: 1-8.   
[96]王亮．深度学习视角下基于多模态知识图谱的MOOC课程重构[J]. 现代教育技术,2018,28 (10):100-106.(Wang Liang.Reconstruction of MOOC courses based on multimodal knowledge map from the perspective of deep learning [J]. Modern Educational Technology, 2018, 28 (10): 100-106.)   
[97] Xu Xing,Ji Dou, Wang Xiangjun,et al. Knowledge graph based teaching analysis on circuit course [C]//2020 International Conference on Modern Education and Information Management (ICMEIM). Piscataway: IEEE, 2020: 767-771.   
[98] Zhu Lei,Liu Yaolin,Hei Xinhong，et al.A study on exercise recommendation method using knowledge graph for computer network course [C]/ 2O20 Intermational Conference on Networking and Network Applications (NaNA).Piscataway: IEEE,2020: 436-42.   
[99]吴昊，徐行健，孟繁军．课程资源的融合知识图谱多任务特征推荐 算法[J].计算机工程与应用,2021,57(21):132-139.(Wu Hao,Xu Xingjian, Meng Fanjun. Knowledge graph-sssted multi-task featurebased course recommendation algorithm [J]. Computer Engineering and Applications,2021,57 (21): 132-139.)   
[100] Lv Junmei, Song Bin,Guo Jie,et al.Interest-related item similarity model based on multimodal data for top-N recommendation [J]. IEEE Access,2019,7: 12809-12821.   
[101] Sun Rui, Cao Xuezhi, Zhao Yan, et al. Multi-modal knowledge graphs forrecommender systems[C]// Proceedings of the 29th ACM International Conference on Information & Knowledge Management. New York: ACM Press,2020: 1405-1414.   
[102] Zhang Fuzheng, Yuan NJ, Lian Defu,et al. Collaborative knowledge base embedding for recommender systems [C]//Proceedings of the 22nd ACM SIGKDD international conference on knowledge discovery and data mining.New York: ACMPress,2016:353-362.   
[103] Zhao Zhengwei,Wang Xiaodong,Xu Xiaowei,et al.Multi-Modal Question answering system driven by domain knowledge graph [C]// 2019 5th International Conference on Big Data Computing and Communications (BIGCOM) . Piscataway: IEEE,2019: 43-47.   
[104] Kim D, Kim S, Kwak N. Textbook question answering with multimodal context graph understanding and self-supervised open-set comprehension [J]. arXiv preprint arXiv:1811. 00232,2018.   
[105]Rafailidis D,Manolopoulou S,Daras P.A Unified framework for multimodal retrieval[J].Pattern Recognition,2013,46 (12): 3358-3370.   
[106] Alberts H,Huang T,Deshpande Y,et al.VisualSem: a high-quality knowledge graph for vision and language[J].arXiv preprint arXiv: 2008. 09150,2020.   
[107]KannanAV,FradkinD,Akrotirianakis I,etal.Multimodal knowledge graph for deep learning papers and code [C]// Proceedings of the 29th ACM International Conference on Information& Knowledge Management. New York: ACM Press,2020: 3417-3420.   
[108] 黄涛，王一岩，张浩，等．智能教育场域中的学习者建模研究趋向 [J].远程教育杂志,2020,38(01):50-60.(Huang Tao,Wang Yiyan, Zhang Hao,et al.Learner modeling research trends in intelligent education Field[J].Journal of Distance Education,202o,38 (01):50-60)   
[109]钟薇，李若晨，马晓玲，等．学习分析技术发展趋向—一多模态数 据环境下的研究与探索 [J]．中国远程教育,2018(11):41-49+79-80. (Zhong Wei，Li Ruochen,Ma Xiaoling，et al. Learning analytics development trends in a multimodal data environment [J]. Distance Education in China,2018 (11): 41-49+79-80.)   
[110] Nandi A,XhafaF,Subirats L,et al.Asurvey on multimodal data stream mining for e-learner's emotion recognition [C]// 2020 International Conference on Omni-layer Intelligent Systems (COINS).Piscataway: IEE,2020: 1-6.   
[111] Camacho V L,de la Guia E, Olivares T,et al. Data capture and multimodal learning analytics focused on engagement with a new wearable IoT approach [J].IEEE Trans on Learning Technologies,2020, 13 (4): 704-717.   
[112]Buitelaar P,Wood ID,Negi S,et al. Mixedemotions: an open-source toolbox for multimodal emotion analysis [J]. IEEE Trans on Multimedia, 2018,20 (9): 2454-2465.   
[113]王一岩，王杨春晓，郑永和．多模态学习分析：“多模态"驱动的智 能教育研究新趋向[J].中国电化教育，2021(03):88-96.（Wang Yiyan，Wang Yangchunxiao, Zheng Yonghe.Multimodal learning analytics: a new research trend in intelligence education driven by multimodality [J]. China Educational Technology,2021(03):88-96.)   
[114]张琪，李福华，孙基男．多模态学习分析：走向计算教育时代的学 习分析学[J]．中国电化教育,2020 (09): $7 - 1 4 + 3 9$ (Zhang Qi, Li Fuhua,Sun Jinan. (Multi-modal learning analytics: learning analytics towards the age of computational education [J]. China Educational Technology, 2020 (09): $7 - 1 4 + 3 9 .$ ）   
[115]郭振东，林民，李成城，等．基于BERT-CRF 的领域词向量生成研 究 [J/OL].计算机工程与应用，[2022-01-26].http://kns.cnki. net/kcms/detail/11.2127．TP.20210706.1547．023．html.(Guo Zhendong,Lin Min,Li Chengcheng,et al. Research on Domain-specific word vector generation based on BERT-CRF [J/OL]. Computer Engineering and Applications, [2022-01-26]. http://kns. cnki. net/kcms/detail/11.2127.TP.20210706.1547.023.html.)   
[116] 胡婕，胡燕，刘梦赤，等．基于知识库实体增强 BERT 模型的中 文命名实体识别[J].计算机应用,2021:0.(Hu Jie,Hu Yan,Liu Mengchi, et al. Chinese named entity recognition based on knowledge base and entity enhanced BERT model[J].Journal of Computer Applications, 2021: 0.)