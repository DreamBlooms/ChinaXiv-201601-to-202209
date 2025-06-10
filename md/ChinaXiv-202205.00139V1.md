# 面向偏差问题的推荐方法研究综述

郭楠，黄慧慧

(东北大学 计算机科学与工程学院，沈阳 110169)

摘要：推荐系统偏差的研究众多但零散，相关研究综述较少，因此，根据偏差产生的主体将偏差分为用户行为导致的偏差、物品展示导致的偏差和推荐算法导致的偏差，进而又细分为选择偏差、一致性偏差等九种具体的类别，并给出各个偏差的定义和造成原因；着重对解决偏差问题的相关性推荐方法和因果性推荐方法的研究进行整理，并根据所采用技术手段或者所处训练模型的前、中、后三个阶段进一步分类，分析不同类别研究之间的区别和优势;总结了在常用数据集上的偏差研究概况和新提出的偏差衡量指标；从不同的类别角度对面向偏差问题的推荐方法发展趋势进行分析和展望，希望为推荐系统中的后续的偏差研究提供一定的帮助。

关键词：推荐系统；偏差；去偏；因果性；相关性中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.02.0092

Review of recommendation methods for problem of bias

Guo Nan, Huang Huihui† (SchoolofComputer Science&Engineering,Northeastern University,Shenyangl10l69,China)

Abstract:Duetothe numerousbutscateredstudies on thebias ofrecommendationsystemsandfewrelevantresearchreviews, accordingtothesubjectthatcausesthebias,this paperdivides bias intothebias inuserbehavior,thebiasinitem display,nd the biasin recommendation algorithm,and then subdivides it into nine specific categories,such as selection bias and conformity bias,and gives thedefinitionandcausesofeach bias;This paper focusesonsortingouttheresearchoncorrelatin recommendation methodsand causal recommendation methods to solve the bias problem,and further clasifies them according tothetechnical means orthefirst,middleandlastthre stagesofthetraining model,andanalyzes thedierences between diferent types ofresearch; This paper summarizes common datasets andreviewers of bias studies and forecasts the developmenttrendof bias-oriented recommendation methods from different categories,and hopes to provide some help for the follow-up bias research in recommender system.

Key words:recommendation system; bias; debias; causality; correlation

# 0 引言

近年来，随着云计算、大数据等技术的迅猛发展，互联网中产生的信息量呈爆炸式增长。这些大规模的数据带来了严重的“信息过载”问题。推荐系统作为一种个性化信息筛选工具应运而生，它在用户没有明确需求的情况下，能够提供个性、精准、快速的筛选和推送，被认为是缓解信息过载的有效方法。如今，推荐技术已经被广泛成功应用于众多领域中，如电子商务平台、社交网络、视频分享平台、生活应用等。

虽然推荐系统在众多领域中被广泛应用，但是其面临着众多偏差问题，偏差问题的存在可能会使得本文无法精准捕捉用户偏好，从而降低推荐的有效性。例如，用户行为数据作为推荐模型训练的基础，是观察性的而不是实验性的。推荐系统最终观察到的用户行为历史数据是各种复杂因素结合碰撞之后产生的结果，而不单纯代表用户对物品的喜爱程度。如果推荐算法不考虑如何准确的“蒸馏”出用户对物品的偏好，可能会导致算法无法准确捕捉用户的偏好，进而影响推荐效果。除了用户行为的复杂性可能导致的偏差，推荐系统在把推荐物品展示给用户时的展示方式，包括但不限于物品是否被曝光给用户、物品曝光给用户的部分特征，物品在展示页面的位置、以及与周围其他物品形成的对比情况等，这些都会影响用户与物品交互的概率，混淆反馈数据，使得用户的偏好更难以捕捉。最后就是推荐算法可能有自己本身的一些倾向性。例如，基于流行度的算法倾向于推荐较为流行的物品和内容。再者，推荐模型是一个从反馈数据到训练模型，再到利用模型给用户产生推荐列表，用户交互后产生反馈数据往复循环的过程，这个不断循环的过程也会进一步加大各种偏差。推荐偏差的合理解决有利于更为准确的捕捉用户偏好，但当前大多数推荐方法研究旨在发明一些机器学习模型来拟合用户行为历史数据，而忽略由于用户行为习惯、物品展示方式以及推荐算法本身的设置导致观察到的用户行为数据存在众多偏差的问题，例如选择偏差[1,2]、曝光偏差[3]、位置偏差[4]等。这些偏差的普遍存在使得直接从数据中学习到的模型无法完全准确的表达出用户的偏好，降低了推荐效果。因此，如何去除这些偏差对模型学习的影响，从而提升推荐系统的性能，逐渐引起了广大学者和业界的关注。

现有的推荐系统偏差研究主要可以分为相关性偏差研究和因果性偏差研究。有些研究致力于发明一些模型来拟合用户历史数据，单纯的通过匹配数据来学习或挖掘相关模式，也有研究在推荐过程中考虑因果关系，能在观测数据之外思考用户建模和个性化推荐[5]。关于解决推荐系统中偏差问题的研究众多但零散，相关的研究综述也很少[。因此，本文着重对近几年解决偏差的相关研究进行整理和综述，各个参考文献来源情况和发布时间汇总如图1所示。不同于推荐系统综述[6,7]，本文着重分析面向偏差问题的推荐方法研究，从相关性角度和因果性角度对研究进行了分类阐述，分析不同研究之间的区别和优势，并对面向偏差问题的推荐方法的发展趋势进行分析和展望。

![](images/82cc5d39a4b6d0c78bed5cccea3a82bd8636a9839db46d0374913502c864a2b6.jpg)  
图1参考文献来源  
Fig.1Sources of references

# 1 推荐系统中的偏差问题

文献[1]对推荐系统中的偏差问题进行了细致的总结与分析。不同于[1]，本文根据产生偏差的主体来划分偏差的类别，并丰富和完善了偏差的种类，根据偏差产生主体的不同划分偏差，从主体角度划分偏差的类别，有利于统一去除同一个主体产生的各种偏差，为一次去除多种偏差提供思路。

# 1.1用户行为导致的偏差

在推荐过程中，由于自身的行为、心理以及当时的状态，用户可以自由选择对哪些物品进行浏览检查、点击和评分，也可能受到从众心理、社交圈朋友或偶像的影响，从而作出一些不符合自己偏好的反馈行为，因此这些反馈数据并不能真实的表达出用户真实的偏好，如果单纯的使用这些反馈数据进行模型训练和下一次推荐结果的生成，会一定程度上降低推荐效果。用户行为导致的偏差主要有选择偏差和一致性偏差。

选择偏差 选择偏差发生在用户评分阶段，因此常存在于显式反馈数据中，由于用户可以自由的选择对哪些物品进行评分，因此最终观察到的评分并不是所有评分的代表性样本。文献[2]通过让用户根据自己对歌曲的喜爱程度来估计自身对歌曲的评价频率，证明了选择偏差的存在。文献[1]也表明，用户更倾向于选择和评价自己喜欢的物品，更有可能对特别差或特别好的物品评分。文献[8\~11]均提出无偏估计量来缓解选择偏差问题。

一致性偏差 披露先前的集体评分会扭曲个人的决策以及个人对质量和价值的看法，评级系统不是简单地汇总个人意见，而是创造一个以系统方式影响后续评级的环境[12]。一致性偏差就是指是用户受到大众或者朋友的影响，会倾向于给出与他人类似的反馈行为，即使并不符合自己的本意。这些反馈行为产生的数据并不总是可以精准的表达出用户的真实偏好。文献[13]通过对豆瓣数据集中的电影评分进行分析，证明了一致性偏差的存在。文献[14\~17]考虑通过建模社会因素对用户行为产生的影响，进而引入特定参数来调节一致性偏差。

# 1.2物品展示导致的偏差

在推荐过程中，由于物品的展示方式，包括但不限于物品是否被曝光给用户、物品曝光给用户的部分特征、物品在页面中的位置、以及与周围其他物品形成的对比情况等，这些都会影响用户与物品的交互，混淆反馈数据，使得不容易捕捉用户真实的兴趣偏好。物品展示导致的偏差主要有曝光偏差、点击诱饵、位置偏差和上下文偏差。

曝光偏差 曝光偏差是由于物品不能全部被暴露给用户那些没有曝光的物品没有交互信息，但没有交互信息不代表是负面偏好，因此存在正样本未标记问题，这种问题常存在于隐式反馈数据中。某个用户-物品对没有交互信息可能是因为用户不喜欢该物品或者并未检查该物品，这些数据无法明确的表达用户偏好，会产生歧义。影响物品曝光的因素有很多，例如先前推荐系统的偏差、用户的地理位置以及物品热度的影响等。文献[3]和文献[18]分别利用均匀数据和负样本采样来解决曝光偏差问题。

点击诱饵点击诱饵问题常存在于隐式反馈数据，指的是用户作出点击行为之前看到的物品曝光特征和点击行为之后的物品内容特征不相符。例如，有些物品的点击率虽高，但用户满意度却很低，这些物品有可能标题和内容不相符或者物品内容质量太差，从而损害了用户满意度，对这些物品，推荐系统应该致力于提升用户满意度而不是用户点击率。为了缓解点击诱饵问题，很多研究试图在推荐算法中加入更多的信息，如停留时间、物品特征和各种用户反馈，来缩小点击和喜欢之间的差距[19]。文献[20\~22]首先根据这些信息识别出虚假点击互动，然后仅使用正面互动去训练模型，文献[23\~27]合并额外的点击后反馈数据(如收藏)来优化推荐模型

位置偏差和上下文偏差 位置偏差主要存在于搜索引擎或者广告系统中，当用户倾向于与列表中较高位置的物品进行交互而不考虑实际相关性时，物品展示的位置影响用户与物品交互的概率，会干扰算法对用户偏好的捕捉。文献[4]进行了一项眼球跟踪的综合研究，印证了搜索引擎中位置偏差的存在。上下文偏差则是指用户和物品交互的时候会被其周围物品所影响，随着用户浏览深度的加大，上下文偏差的影响逐渐超过位置偏差，两者均常存在于隐式反馈数据中。文献[28,29]均采用IPS技术缓解上下文偏差。对各种偏差的总结如表1所示。

表1九种偏差及其相关文献  
Tab.1Nine bias and related literature   

<html><body><table><tr><td>主体 偏差类型</td><td>反馈类型</td><td>造成原因</td><td>主要解决方案</td><td>相关文献</td></tr><tr><td>选择偏差</td><td>显式</td><td>观察到的评分不是所有评分的代表性样本</td><td>均匀数据、逆倾向分数、元学习</td><td>[3,8~11,39,47,48,58,66,77~79,85]</td></tr><tr><td>用户一致性偏 差</td><td>显式、隐式</td><td>用户会受到大众和其他人的影响</td><td>生成性建模、逆倾向分数</td><td>[13~17,80]</td></tr><tr><td>曝光偏差</td><td>隐式</td><td>推荐结果中只能有一部分物品曝光给用户</td><td>均匀数据、逆倾向分数、采样</td><td>[3,18,41,70,72,74]</td></tr><tr><td>点击诱饵</td><td>隐式</td><td>物品在用户点击之前暴露的特征和点击之后的内容特征</td><td>采样、因果图、</td><td>[19~27]</td></tr><tr><td>物品</td><td></td><td>不相符</td><td>利用额外反馈信息</td><td></td></tr><tr><td>位置偏差 上下文偏</td><td>隐式</td><td>各个物品展示给用户时位置不同</td><td>生成性建模、逆倾向分数</td><td>[28,51,65,67,68,75,76,85]</td></tr><tr><td>差</td><td>隐式</td><td>物品展示给用户时，和周围物品形成的 对比</td><td>生产性建模、倾向分数</td><td>[28,29,49,68]</td></tr><tr><td></td><td>循环偏差 显式、隐式</td><td>推荐过程的循环过程使得各种偏差被放大</td><td>均匀数据、样本加权、强化学习、因果图</td><td>[38,42,56,83]</td></tr><tr><td></td><td>人气偏差显式、隐式</td><td>热门的物品被过度推荐</td><td>正则化、生成性建模、强化学习、评估器、重排序</td><td>[31~33,43,44,50,57,69,81,82]</td></tr><tr><td>算法</td><td></td><td></td><td>正则化、对抗学习、强化学习、自动编码器、重排</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>不公平显式、隐式</td><td>算法歧视某些群体或者个人</td><td>序、</td><td>[34,35,45,46,52~54,59,61~63,84]</td></tr></table></body></html>

注：其中文献[3]同时解决了选择偏差和曝光偏差，文献[40]同时解决了选择偏差、一致性偏差、曝光偏差、位置偏差，文献[68]同时解决了位置偏差和上下文偏差，文献[85]同时解决了选择偏差和位置偏差。另外文献[55.60,71，73]并未划分偏差类别，以实现无偏推荐为目的，不具体针对某种具体类型偏差。

# 1.3推荐算法导致的偏差

不同的推荐算法本身也带有一定的倾向，比如基于流行度的算法倾向于推荐较为流行的物品或内容，而基于协同过滤的算法则一般对交互比较多的用户或物品的推荐更友好些。推荐算法导致的偏差主要有人气偏差、不公平问题和循环偏差。

不公平推荐中的不公平指的是，系统不公平的歧视某些个人和群体，偏袒他人。例如，与男性相比，女性看到高薪工作的广告较少。文献[34]等就将此问题映射为一个有限的问题：公平的分配不可分割的物品，提出的FairRec算法不仅保证了大多数商品提供商的利益，也为每位用户提供了较高的满意度，相似的还有文献[35]，使用贪心算法来寻找公平的TOP-N列表解决组推荐中的公平性问题。

循环偏差 循环偏差的存在是由于推荐系统是一个从反馈数据训练模型，再到利用模型给用户产生推荐列表，用户交互后产生反馈数据往复循环的过程，在这个不断循环的过程中上述的各种偏差会进一步被加深。

# 2 基于相关性去偏

相关性研究致力于发明一些模型来拟合用户历史数据，单纯的通过匹配数据来学习或挖掘相关模式。但随着推荐算法研究的不断丰富，推荐结果的精确性和准确性不再是算法单纯追求的目标，有研究人员注意到，仅仅基于相关性或关联性无法很好的评估和解决公平性问题[36]。任何相关性的背后都隐藏着因果关系，相关性分析得到的结论有时是不可靠的甚至是错误的，且基于相关性的方法不能用于管理、控制和干预变量或事件[37]。因此基于因果性来缓解偏差的研究被提出。因果性研究在推荐过程中考虑因果关系，能在观测数据之外思考用户建模和个性化推荐[5]。本文将偏差相关文献分为相关性去偏研究和因果性去偏研究。

在相关性的去偏的研究中，根据文献采用的技术以及作用的阶段不同进行了分类和汇总，如图2所示。其中，均匀数据和采样属于前处理操作，在训练模型前就通过小部分无偏的数据或采样手段来解决偏差问题，而样本加权、正则化和训练模型则是作用于训练阶段，目的是训练出无偏的模型来产生无偏的推荐结果。训练模型根据采用的技术不同又细分为生成性建模、强化学习、元学习、自动编码器和对抗学习，评估器和重排序则是属于后处理，旨在通过无偏的推荐指标和推荐列表的重新排序来缓解偏差问题。

![](images/91e3fba0f5baf01686a8a53b08f5ab6d968c138e5fc236f6646b248922f8ff49.jpg)  
图2相关性去偏方法  
Fig.2Debias method of correlation

# 2.1均匀数据和采样

均匀数据可以缓解模型的偏差问题。对于用户的请求，系统不再使用推荐模型生成推荐列表，而是从所有候选物品中，随机选择某些物品进行推荐。均匀数据可以无偏差的反映用户的偏好，也不受先前模型的影响，但是由于均匀数据的收集会损害用户的体验，所以如何有效的利用均匀数据就显得十分重要。文献[38]通过均匀数据的反事实建模来缓解循环偏差问题，为了更有效地使用少数有价值的均匀数据，提出了一个用于反事实推荐的通用知识蒸馏框架，来实现均匀数据的建模，从而解决了循环偏差问题，不同的是，文献[39]则利用均匀数据解决了选择偏差。也有其他研究将均匀数据当作一种辅助手段来解决偏差问题。文献[40]通过均匀数据来监督框架参数的学习，最大化均匀数据的损失来优化框架的去偏参数，而文献[3]则是组合了均匀数据(Uniformdata)、逆倾向分数和数据填充(Dataimputation)来同时解决曝光偏差和位置偏差。

采样策略可以控制哪些数据用来更新模型，从而纠正数据的分布。文献[18]利用用户浏览但是未点击的数据通过负样本采样技术来解决曝光偏差问题，通过对抗训练来生成高质量的负样本。与之类似，文献[41]则是在构建的基于物品的知识图谱上进行采样来缓解曝光偏差。

# 2.2样本加权和正则化

样本加权是指在模型训练时修正每组样本的损失贡献值，倾向分数就可以用作样本加权。逆倾向分数是一种反事实技术，可以利用这种思想重新加权收集的数据进行无偏的学习。但是这种方法依赖于倾向分数的准确性，通常会有方差较高的缺点，所以也衍生出了很多改进方法。文献[42]提出用影响函数重新加权培训样本，更好的解决了循环偏差问题。

正则化也可以用来减少推荐模型的偏差[1]。为了解决人气偏差问题，文献[43]提出基于正则化的处理方法，通过降低物品流行度和模型预测分数之间的关联程度来最小化偏差，预测分数和物品流行度之间的皮尔逊相关系数作为正则化项。文献[44]也将正则化作为一种辅助手段根据人气值惩罚物品的预测得分，来缓解人气偏差问题。也有学者将正则化用作解决不公平性问题。文献[45]利用一个基于KL散度的正则化项，旨在对每个用户的分数进行归一化，文献[46]则利用正交正则化使得无偏差的用户嵌入正交于偏差感知的用户嵌入，以便更好的区分两者。

# 2.3 训练模型

偏差问题也可以通过训练无偏的推荐模型来解决，直接使用无偏的推荐模型产生的推荐结果就是无偏的。无偏模型的训练可以选用很多技术，根据各个研究采用技术的不同，本文将这些研究细分为生成性建模、强化学习、元学习、自动编码器和对抗学习等不同的类别。

# 2.3.1生成性建模

生成性建模来解决偏差问题的主要思想是假设反馈数据的生成过程并相应减少偏差[40]。该类研究假设数据的生成过程，有利于定位各个偏差，被广泛应用于解决各种偏差。图3 概括了点击数据和评分数据的生成过程。文献[47,48]通过建模评分的生成过程来解决选择偏差问题。前者通过探索物品的可观察性，用户选择和评分之间的复杂依赖性来解决MNAR(MissingNotatRandom)问题，评分生成过程为观察-选择-评分。后者考虑了社交网络，通过对观察过程和评分过程的建模，解决了选择偏差问题和受朋友推荐的物品会给出低分的问题，评分生成过程为观察-评分。

![](images/fec4ad70bc243db2c3f2d52c195481986a78824368ecb8c1604fb736fd9a0f85.jpg)  
图3数据生成流程

也有其他学者将生产性建模的思想用于解决其他偏差问题。文献[49]就提出了一个完全数据驱动的神经模型来解决上下文偏差问题，考虑点击特定物品和同一会话中其他物品之间的关联，包括相关性和位置，着重对检查过程建模。文献[50]则把人气偏差问题归因于整个推荐循环的各个阶段，而不单单是一个原因造成的，提出了一种动态的缓解偏差策略，对整个推荐过程进行建模。文献[51]则提出了一个增强的位置偏差模型，明确模拟了依赖于位置的点击噪声，解决了因用户信任排名质量而导致的位置偏差，着重对检查-点击过程建模，并提出了补充模型来建模用户感知相关性和实际相关性之间的关系。文献[52]致力于解决新物品推荐公平性，在证明了数据偏差可以通过物品内容特征从热启动物品转移到新物品之后，提出联合学习生成模型来解决冷启动阶段的不公平问题，模型不断调整物品匹配用户分数分布状况，弥补分数分布较低的物品，从而缓解不公平问题。不同的是，文献[53]为了解决在推荐职业相关敏感物品时的性别偏差，提出使用神经协同过滤的预训练和微调方法，加以偏差纠正技术开发了一种框架，更细致化的解决了推荐系统中的不公平问题。

# 2.3.2强化学习和元学习

![](images/302c16aacf437bf28c8d1d82d62920647a47e1f2375657ab93bd2d627b274289.jpg)  
Fig.3Data generation process

众多学者利用强化学习来解决各种偏差问题。文献[54]认为应该考虑长期的公平性，随着时间的发展，受公平性保护的物品组不应该是固定的。该研究关注不同物品组的曝光公平性，提出一种公平性约束的强化学习推荐算法，将推荐问题建模为一个约束马尔可夫决策过程，能够动态调整推荐策略，确保环境发生改变时，也能满足公平性的要求。文献[55]利用强化学习在模拟用户行为之前纠正记录数据中的偏差，实现了无偏的推荐。文献[56,57]通过强化学习分别来解决循环偏差和人气偏差，前者利用了反事实的技术，后者利用多臂老虎机来多样化用户偏好。

元学习的思想是如果模型能先在数据较多的数据集上学习，学习到一些先验知识后再去在数据较少的数据集上学习就变得容易。文献[58]为了解决逆倾向分数会遭受较大方差的问题，利用元学习缓解选择偏差。首先使用观察到的评分数据预训练三个推荐算法，然后使用其中两个算法对随机抽取的一系列用户-物品对进行预测评分，如果两个模型结果足够相似，便使用两个结果之一作为这一数据对的伪评分，这样可以得到一个可以信赖的伪标签数据集，最后在伪标签数据集上去训练第三个模型，由这个模型给出最终的推荐结果。文献[40]也提出了基于元学习的参数学习方法，通过最小化风险化差异来统一处理各种偏差，实现了自适应的偏差解决

方案。

# 2.3.3自动编码器

也有研究利用自动编码器来处理推荐系统中的各种偏差，自动编码器框架如图4所示。

文献[59]关注主流偏差，是指推荐系统倾向于向具有主流品味的用户提供更好的推荐结果，而忽略非主流用户，在学习用户和物品基于文本的卷积神经网络时添加自动编码器层，强制要求所有用户和物品的独特特征充分整合并保存在学习到的表示中，使得学习的表示更少的偏向于主流用户，缓解了主流偏差的同时又保持了主流用户的推荐质量，最终给所有用户提供更加平衡的推荐结果。自动编码器的原始输入是用户评论或物品属性的特征表示，用来重构用户和物品的原始特征向量。文献[60]为了更好的利用大量未观测数据，实现自适应的权重分配和有效的模型学习，提出了一种基于变分自动编码器的快速自适应加权矩阵分解方案对数据可信度权重进行建模，减少推断参数数量的同时，还能够捕获用户之间的潜在相互作用，其中编码器是用来编码用户影响力，即消费量，解码器用来预测用户的消费，共同组成自动编码器来学习矩阵分解的数据置信度权重和潜在因素。

# 2.3.4对抗学习

现有研究常使用对抗学习来解决推荐系统中的不公平问题，对抗式学习框架如图5所示。文献[61]提出一种基于图的解决方案，给定任何模型的原始嵌入，学习一组过滤器，将用户和物品的原始嵌入转换到基于敏感特征集的过滤嵌入空间中。对于每个用户，这种转换是在以用户为中心的图的对抗学习下实现的，以便混淆过滤后的用户嵌入和该用户子图结构之间的敏感特征。过滤后的嵌入不仅能表示用户偏好的同时还必须是公平的，不会泄露用户的敏感信息。采用对抗学习技术训练模型，过滤网络扮演生成器的角色试图掩盖用户的敏感信息，而鉴别器网络将过滤后的嵌入作为输入，试图预测敏感属性的值，两个网络进行极小极大博弈。

![](images/984286e7cf9b8132b4f1cb9ce4632529c11b7098906b141de8d72d8c8f30f941.jpg)  
图4自动编码器框架Fig.4Autoencoder frame  
图5对抗式学习框架  
Fig.5Adversarial learning framework

文献[45]通过一个去偏化的个性化排名模型展示了如何基于统计均等和机会均等来克服不公平问题，其中采用对抗学习来增强物品组之间分数分布的相似性，在BPR(BayesianPersonalizedRanking)模型和鉴别器之间进行极大极小博弈，BPR模型扮演生成器需要防止鉴别器对物品组进行正确分类，鉴别器则是根据BPR预测的用户物品得分对物品组进行分类。文献[46则是将用户兴趣分解为两个部分，一个组件用于学习一种感知偏差的用户嵌入来捕获敏感用户属性上的偏差信息，另一个组件用于学习无偏差的用户嵌入仅捕获用户兴趣信息，无偏差的用户嵌入则采用了对抗学习来训练，学习无偏差用户嵌入的模型扮演生成器角色，属性鉴别器则用来从无偏差用户嵌入中推断用户属性，两者形成对抗。最后，

为了实现公平的新闻排名系统，只使用无偏差用户嵌入来产生推荐结果。

# 2.4评估器和重排序

利用评估器去除偏差的主要思想是通过修正评估度量来实现无偏的推荐，修正评估度量的研究主要利用逆倾向分数技术来实现。也有相关学者提出新的指标来衡量人气偏差。文献[31]提出了校准的概念来衡量用户历史物品的人气分布和推荐物品之间的匹配度，从不同利益相关者角度衡量时，该度量能更好的反映算法的性能。之后的研究[32]又从用户角度出发，提出了一个可以衡量人气偏差的新指标UPD(UserPopularity Deviation)。

重排序是一种可以应用于任何推荐算法输出的后处理步骤，是以先前推荐模型输出的TOP-N列表为基础进行的，重排序的任务就是生成一个新的重新排序的TOP-K列表，其中（204号 $( \mathsf { K } \leq \mathsf { N } )$ ，该列表在保证一定准确性的同时也考虑了偏差问题文献[33]为了缓解人气偏差，引入了个性化的重新排名方法，来增加推荐列表中不太受欢迎的物品数量，同时保持可接受的推荐准确性。文献[62]则是根据用户的活动水平对不同用户群体进行分析，提出了一种基于启发式重新排序的公平性约束方法来缓解知识图上的不公平问题，除了群体不公平度量，还提出了个体不公平度量，只需替换约束条件即可。文献[63]也是从用户角度出发解决弱势群体的问题，提出了一种重新排序的方法，在评估指标上添加约束，生成公平感知的推荐列表，从而缓解了不公平问题，具体来说，将原始推荐算法输出的TOP-N列表为重新排序算法的输入，重新排序算法的目标函数是最大化公平约束下的预测评分总和，最后输出TOP-K列表，最终再对TOP-K列表中的物品进行排序，作为最终的推荐列表。

# 2.5基于相关性去偏总结

均匀数据是通过随机推荐策略实施推荐来收集的无偏数据，数据本身就是不存在偏差的，但缺点在于这种数据的收集和处理有可能会损害用户体验，成本较高。采样方式是通过合理的采样策略来控制哪些数据用来训练模型，采样策略的选定较为关键。样本加权则是在训练过程中给不同的样本赋于不同的权重来缓解偏差，正则化也属于训练模型的一种，在训练模型中通过正则化项，来影响偏差和推荐结果之间的关联程度，从而缓解偏差问题。训练模型则是利用各种技术在训练模型的过程中将偏差解决。评估器是通过修正评估度量来实现无偏的推荐，依赖于新提出的衡量偏差指标。重排序是一种可以应用于任何推荐算法的后处理步骤，对有偏差存在的推荐列表通过一定的重排序规则，减少偏差对推荐结果的影响程度。

均匀数据和采样属于前处理方式，致力于在将数据输入训练模型前就解决偏差问题，而样本加权、正则化、训练模型等中处理手段致力于在训练模型过程中解决偏差，评估器和重排序等后处理操作致力于在训练出模型之后再对推荐结果进行微调来调控偏差问题。

# 3 基于因果性去偏

相关性推荐对观测数据的依赖较大，优势在于思想简单，只需不断的拟合数据，最终使得模型能较好的匹配数据，但是仅仅基于相关性无法很好的评估和解决偏差问题，这是因为相关性无法推理出输入和输出之间的因果关系，而偏差存在的原因可能存在于用户和系统交互某一个阶段中的因果关系中。因此，因果性推荐比较适合解决偏差问题，更有利于偏差的定位和解决，更有利于准确的消除偏差所带来不良影响，也有利于提升推荐算法的可解释性。

因果推断是基于效果发生的条件来得出关于因果关系结论的过程[64]。基于因果推断的相关研究大多是在干预和反事实的基础上定义的，干预可通过随机实验来实现，而反事实则考虑现实世界之外的假设世界。当前主流研究主要是利用因果推断中的逆倾向分数和因果图来缓解推荐系统中的偏差。

# 3.1基于 IPS 技术的因果性去偏

IPS 属于因果推断中的一种技术，可以调节原始数据的分布。该方法通过重新加权样本将观察到的记录数据转换为伪随机实验，一般来说，首先估计倾向分数，然后用倾向分数的倒数重新加权样本，倾向分数可以看做是某种事件发生的概率，IPS已被广泛用于无偏评估和学习[65]。利用IPS 消除偏差的研究可以分为两类，评估器和模型训练。评估器主要是利用倾向分数的思想来纠正评价指标，而利用IPS的模型训练主要是利用倾向分数的思想融合到训练过程，进而实现无偏推荐。

IPS 思想也可以融合到模型训练中实现无偏推荐。文献[71]为推荐的因果效应提出了一个无偏的学习框架，首先构建用于排名度量的无偏估计，然后对估计器进行经验风险最小化，其中的倾向分数是通过数据集的统计指标来计算的。也有文献通过模型来计算倾向分数。例如，文献[72]提出一个组合联合学习，同时学习无偏的用户-物品相关性和无偏的倾向性，用数据集的不同部分去学习这两个子模型，以防数据重复使用带来的偏差问题，其中的倾向分数的计算就是通过模型从数据中学习出来的，而文献[73]为了提高倾向得分估计的准确性，使用了小型的注释数据集来推断可重复使用的倾向模型的参数，文献[74]则是提出了一种配对倾向得分估计方法，通过计算用户流行度和无偏流行度的配对程度更精确的缓解了曝光偏差。相关学者通过倾向估计来缓解位置偏差[65,75,76]和上下文偏差[29]。为了降低对用户搜索体验的侵入性干扰，文献[65]提出了一种从反馈日志中获取干预数据的方法，在无干预的情况下进行位置偏差的估计。也有相关学者致力于改进IPS方差较大的缺点来缓解选择偏差。文献[8]人结合了Data imputation 模型和IPS 模型，构建了无偏估计器，只要两种模型中有一种模型正确，便可保证算法的无偏性，最终实现了双重鲁棒性。文献[9,10]也提出了优于IPS的双重鲁棒性评估器，最新的研究中文献[11]为了进一步减少方差，提出了MRDR(MoreRobustDoublyRobust)估计量。

上述利用IPS思想的相关研究很好的解决了积极反馈的偏差，但却未考虑缺失反馈数据的偏差，忽略了未点击物品也不一定不相关的问题，所以有相关学者就此不足展开研究和改进。文献[77提出了一种双重的推荐学习框架，所提出的损失函数采用两种倾向加权，以更有效的估计点击和未点击数据的真实偏好，同时消除了点击和未点击数据的偏差。文献[78,79]则是对IPS进行改进，提出了一种新的加权方案(PropensityRatio Scoring)，来考虑缺失反馈偏差问题的解决。

本文对基于IPS的相关文献整理汇总如表2所示。其中使用数据范围是指文献中推荐算法输入的数据的范围，反馈数据是指用户和物品有交互记录的数据，没有反馈数据并不代表用户对物品不感兴趣。填充数据是指用户和物品没有交互记录的数据，但论文做了数据填充。

# 3.2基于因果图的因果性去偏

因果图是反事实推理的有力工具。从观察到的数据中解决因果推断问题有两种框架，分别是潜在结果框架(PotentialOutcome Framework)和结 构因果 模型(StructuralCausalModel)。结构因果模型包括因果图和结构方程式，可以将系统中的因果描述为一组变量和变量之间的因果关系，其中变量之间的因果关系由一组同时成立的结构不等式来建模[64]。

因果图能够描述推荐系统中的因果关系，模拟出用户和物品交互的可能因素，剖析具体某个偏差存在的位置，进而利用各种手段去除偏差的影响。文献[80]就利用因果推理来解决一致性偏差，首先假设用户对物品的点击行为取决于兴趣和一致性偏差，然后基于构建的因果图使用两种不同原因的数据分开训练两种嵌入，一种是兴趣嵌入来捕捉用户对物品的真实兴趣，另一种是符合性嵌入来捕捉从众心理引起的一致性偏差，然后利用多课程任务学习来平衡两种原因，最后消除了一致性偏差。每个用户的一致性偏差是基于因果图通过数据学习到的一种嵌入，保证了算法的可解释性和健壮性。该研究所基于的因果图较为简单，故而对一致性偏差的捕捉和定位也比较笼统。

文献[81]利用较为精细的因果图来描述整个推荐过程中重要的因果关系，将用户与物品的交互归因于用户和物品的匹配度、物品流行度和用户活跃度，在训练期间利用多任务学习模拟每种原因的贡献值，在测试期间执行反事实推理来消除人气的影响，最终缓解了人气偏差。但文献[82]则认为并不是所有的偏差都是有害的，不能盲目的消除所有偏差，提出有效的利用人气偏差来提高推荐效果，文献认为人气偏差的存在是因为热门的物品过度曝光，并通过更加精细化的因果图假定了反馈数据的生成过程，在训练阶段消除了人气偏差带来的消极影响的同时也利用了人气偏差的积极影响，达到了利用偏差提高推荐效果的目的。也有学者利用因果图解决点击诱饵问题。

表2基于IPS 的因果性偏差研究  
Tab.2Research on causal method bias based on IPS   

<html><body><table><tr><td rowspan="2">文 献</td><td rowspan="2">偏差</td><td rowspan="2">原因</td><td rowspan="2">假设</td><td rowspan="2">倾向分数 含义</td><td rowspan="2">倾向分数 计算方式</td><td rowspan="2">使用数 据 范围</td><td rowspan="2">改进阶 段</td></tr><tr><td></td></tr><tr><td>[66]</td><td>选择偏差</td><td>观察到的评分不是所 有评分的代表性样本</td><td>评分大小和是否评分相互独立</td><td>历史记录中某个 评分出现的概率</td><td>朴素贝叶斯、逻辑回归</td><td>反馈</td><td></td></tr><tr><td rowspan="2">[67]</td><td>位置偏差</td><td>物品位置影响交互</td><td>点击取决于检查和相关性</td><td>置物品的概率</td><td>用户看到不同位不同位置的物品随机交 换，交换前后求比值</td><td>反馈</td><td></td></tr><tr><td></td><td>位置偏差、上物品位置和周围环境</td><td></td><td></td><td>两种偏差倾向分 基于回归的期望最大化算</td><td></td><td>修正评</td></tr><tr><td rowspan="2">[68] [69]</td><td>下文偏差</td><td>影响交互</td><td>点击取决于检查性、相关性和比较</td><td>数之积</td><td>法</td><td>反馈</td><td>估指标</td></tr><tr><td>人气偏差</td><td></td><td>物品流行度影响物品倾向独立于用户；物品被呈现的概率由流行度决 历史记录中某个</td><td></td><td>利用物品流行度函数</td><td>反馈、</td><td></td></tr><tr><td rowspan="2">[70]</td><td></td><td>被推荐概率</td><td>定的；交互概率与物品被推荐的概率无关</td><td>互动出现的概率</td><td></td><td>填充</td><td></td></tr><tr><td>曝光偏差</td><td>物品曝光影响交互</td><td>点击取决于曝光概率和相关性</td><td></td><td>相对点击概率的b次幂反馈、</td><td></td><td></td></tr><tr><td rowspan="2"></td><td></td><td></td><td></td><td>曝光概率</td><td>(b为超参数)</td><td>填充</td><td></td></tr><tr><td></td><td></td><td>点击取决于曝光概率和相关性</td><td></td><td></td><td></td><td>练</td></tr><tr><td>[72]</td><td>曝光偏差</td><td>物品曝光影响交互</td><td></td><td></td><td>从数据中来学习倾向模型</td><td>反馈+填 模型训 充</td><td></td></tr></table></body></html>

文献[19]人首先想象一个反事实世界，在反事实世界里每个物品只有曝光特征，通过估计反事实世界中用户点击的可能性，能够降低曝光特征对预测评分的直接影响，从而消除点击诱饵问题。文献[83]建模用户表示对预测得分的因果效应，认为循环偏差产生的主要原因是用户表示和预测分数在物品的分布不平衡，用户表示在物品上的分布是一个存在于用户表示和预测分数之间的混淆因子，造成了两者之间的虚假相关性，去除混淆因子的影响后便可纠正循环偏差。将基于因果图的研究整理如表3和图6所示，其中的偏差定位是指每篇文献在因果图中对特定偏差的定位。

从图6可以看出，推荐系统中最简化的因果图由两条因果关系构成，分别是物品特征 $( \mathrm { I } ) ^ {  }$ 交互概率(Y)和用户特征$( \mathrm { U } ) \to$ 交互概率(Y)，代表用户和物品的交互概率由物品特征和用户特征决定。文献[81]则从物品特征 $( \mathrm { I } ) $ 交互概率(Y)因果关系中更细化出了用户特征和和物品特征的匹配度(K)。文献[82]也更加细化了物品特征 $( \mathrm { I } ) \to$ 交互概率(Y的因果关系，认为物品的人气(Z)是其中的一个混淆因子，并有效利用人气偏差提升了推荐效果。文献[19]在物品特征 $( \mathrm { I } ) \to$ 交互概率(Y)的因果效应中加入物品暴露特征(E)和内容特征(T)，分别代表物品在用户点击之前物品暴露给用户的特征和用户点击之后看到的物品内部特征，定位到了点击诱饵产生的具体原因，文献[83]则实现了对用户特征 $( \mathrm { U } ) \to$ 交互概率(Y)因果效应的精细化，加入了训练数据在物品不同类别中的分布(D)和组级别的用户特征(M)，定位了循环偏差。

基于因果图的研究提供了一种关于一次性解决同一主体各种偏差的思路，将各种用户产生偏差均定位到用户特征(U)$\mid  \mid$ 交互概率(Y)因果关系中，不断细化梳理各种偏差产生的因果过程，最后统一训练用户无偏的特征表示，一次性去除由用户产生的各种偏差。

![](images/da14b821f3a059eb12fdb6c8150bd28f00b5eb610b01c44536be5187f88a2d0c.jpg)  
图6文献[19,81\~83]整合后的因果图  
Fig.6Causal graph after integration in literature[19,81\~83]

# 3.3其他因果性去偏方法

除了IPS和因果图这两种因果技术，也有其他研究学者将因果性方法融合一些深度学习技术来实现因果性去偏。文献[84]指出用户对公平的需求是个性化的，提出从用户特征中剔除敏感特征，来实现个性化的反事实公平，通过对抗学习生成特征独立的用户嵌入进行推荐，同时算法也覆盖非个性化的情况。该研究同时训练预测器和对抗分类器，前者学习推荐任务的信息表示，后者从学到的信息表示中预测受保护特征，将敏感特征从学习到的表示中移除，确保了算法的公平性。另外，文献[85为了解决选择偏差和位置偏差提出了一种新的反事实方法，采用了Heckman两阶段法，并考虑了系统中的选择和位置偏差，在偏差不大的情况下，对噪声具有更强的鲁棒性和更好的精度。

# 3.4基于因果性去偏总结

基于IPS的偏差解决方案主要通过估计倾向分数和用倾向分数的倒数重新加权样本融合到推荐模型中来缓解偏差。

而基于因果图的偏差解决方案则是通过因果图来描述推荐系统中的因果关系，模拟出用户和物品交互的可能因素，剖析具体某个偏差存在与某条因果关系中，进而利用各种手段去除偏差的影响。基于IPS的偏差解决方案依赖于倾向分数的计算，倾向分数的不准确可能导致该方法的方差较大。倾向分数的计算可以通过简单的自定义函数，也可以通过预先的实验来确定，也可以在训练数据的过程中来学习。基于因果图的难点在于如何正确的拟定推荐系统中的因果关系，只有拟定的因果关系符合整个推荐过程的因果关系，才会缓解偏差，进而提升推荐效果。

Tab.3Research on causality method bias based on causal graph   

<html><body><table><tr><td rowspan="2">文献偏差</td><td rowspan="2"></td><td rowspan="2">原因</td><td>定</td><td rowspan="2">假设</td><td>实现方式</td><td>使用数据改进 范围</td><td>阶段</td></tr><tr><td>位 物品暴露特征影响</td><td>交互概率取决于用户特征、物品特征和物</td><td></td><td></td></tr><tr><td>[19]</td><td>点击诱 饵 一致性</td><td>交互</td><td>E-Y</td><td>品曝光部分的特征 点击概率取决于兴趣和</td><td>反事实推理去除曝光特征的直接影响</td><td></td><td></td></tr><tr><td>[80]</td><td>偏差 人气偏</td><td>物品人气值影响交互</td><td></td><td>从众心理 交互概率取决于用户-物品匹配度、物品流</td><td>分开学习兴趣特征和偏差特征</td><td>反馈</td><td>训练模</td></tr><tr><td>[81]</td><td>差</td><td>物品属性影响交互 人气偏 物品人气值影响曝光概</td><td>I-Y</td><td>行度和用户活跃度 交互概率取决于用户特征、物品特征和物 训练消除流行度对曝光的消极影响，推理时嵌入流</td><td>反事实推理去除物品内在属性的影响</td><td></td><td>型</td></tr><tr><td>[82]</td><td>差</td><td>率</td><td>Z-I</td><td>品的人气值 循环偏 历史记录分布不均匀影 D-交互概率取决于用户特征、物品特征和组</td><td>行度对交互的积极影响</td><td></td><td></td></tr><tr><td>[83]</td><td>差</td><td>响用户特征</td><td>U</td><td>级别的用户特征</td><td>因果建模去除混淆因子的影响</td><td></td><td></td></tr></table></body></html>

# 3.5基于相关性去偏和基于因果性去偏的对比分析

相关性去偏致力于通过不断的拟合数据来挖掘相关模式去实现无偏的推荐。思路较为简单，不需要推荐所属领域的因果先验知识，只需拟合数据，进而纠正偏差提升推荐效果即可。但是由于虚假相关性的存在，模型在训练数据中挖掘到的相关关系不一定总是成立，所以会导致训练好的模型，在与训练数据分布状况不同的数据中进行推荐时，效果会较差。虚假相关性也会导致不正确的推荐结果，所以就算是在训练数据和测试数据分布状况相同的情况下，相关性去偏也不一定总是可靠，而且推荐规则是不可解释和不可干预的。对相关性去偏方法与因果性去偏方法整理对比如表4所示。

因果性去偏能够去掉相关性去偏方法中的强虚假相关性，因此推荐规则更加可靠。因果性去偏中提前拟定的因果关系也导致推荐规则具有一定的可解释性，而且可以利用因果干预技术获得更优质的推荐结果。因果性去偏利用推荐系统中的因果关系实施推荐，不过分依赖于训练数据中的相关性，模型的推荐效果泛化能力较好。提前拟定的因果关系虽然能够带来一定的解释性，但如果提前拟定的因果关系不符合现实世界中实际的因果关系或者不全面不准确，推荐效果会较差。

# 表4相关性去偏方法和因果性去偏方法对比

表3基于因果图的因果性偏差研究  
Tab.4Comparison of correlation debias method and   

<html><body><table><tr><td colspan="3">causalitydebiasmethod</td></tr><tr><td>方法</td><td>优势</td><td>局限</td></tr><tr><td>相关性 去偏</td><td>思路简单; 无须因果先验知识； 拟合数据效果好</td><td>推荐规则不可靠、不可解释、不 可干预； 可能会存在强的虚假相关性，影 响推荐效果</td></tr><tr><td>因果性 去偏</td><td>推荐规则可靠、可解 释、可干预; 泛化能力较好</td><td>需要提前拟定因果关系； 只能拟合一部分数据； 因果关系抽取不全面不准确可能 会影响推荐效果</td></tr></table></body></html>

# 4 数据集和评价指标

推荐模型的推荐效果要想获得公认、客观的评价，统一的数据集和评价标准是必不可少的。偏差问题客观存在于各种推荐场景中，偏差研究目的是修正偏差，进一步提升推荐效果，因此偏差相关的研究所选用的数据集和推荐系统常用数据集无异。

本章主要总结前述偏差研究中所使用的公开数据集和评价指标，对当前学者所选用的数据集以及所研究的偏差种类进行汇总，如表5所示。

表5常用数据集以及目前数据集上的偏差研究概况  
Tab.5Common dataset of bias and an overview of bias studies   

<html><body><table><tr><td rowspan="2">数据集</td><td rowspan="2">用户数</td><td rowspan="2">物品数</td><td rowspan="2">评分数</td><td rowspan="2">稠密性</td><td rowspan="2">评分 范围</td><td rowspan="2">数据集上已实验验证的偏差种类(文献数量/篇)</td></tr><tr><td></td></tr><tr><td>MovieLens 100K</td><td>943</td><td>1682</td><td>100000</td><td>6.30%</td><td>[1,5]</td><td></td></tr><tr><td>MovieLens 1M</td><td>6040</td><td>3952</td><td>1000209</td><td>4.19%</td><td>[1,5]</td><td></td></tr><tr><td>MovieLens 10M</td><td>71567</td><td>10681</td><td>10000054</td><td>1.31%</td><td></td><td>[0.5,5]人气偏差(8)、不公平(5)、选择偏差(4)、曝光偏差(1)、循环偏差(1)、一致性偏差(1)</td></tr><tr><td>MovieLens20M</td><td>138493</td><td>27278</td><td>20000263</td><td>0.53%</td><td>[0.5,5]</td><td></td></tr><tr><td>MovieLens 25M</td><td>162541</td><td>62423</td><td>25000095</td><td>0.25%</td><td>[0.5,5]</td><td></td></tr><tr><td>Netflix</td><td>480189</td><td>17770</td><td>100480507</td><td>1.18%</td><td>[1,5]</td><td>一致性偏差(1)</td></tr><tr><td>Last.fm</td><td>1892</td><td>17632</td><td>92834</td><td>0.28%</td><td></td><td>人气偏差(2)、曝光偏差(1)、不公平(1)</td></tr><tr><td>Epinions</td><td>49290</td><td>139738</td><td>664824</td><td>0.01%</td><td>[1,5]</td><td>人气偏差(2)、选择偏差(1)</td></tr><tr><td>Amazon</td><td>5786</td><td>26573</td><td>14280000</td><td>0.002%</td><td>[1,5]</td><td>人气偏差(2)、曝光偏差(1)、循环偏差(1)、不公平(2)</td></tr><tr><td>Adressa 16G</td><td>3083438</td><td>48486</td><td>27223576</td><td>0.012%</td><td>--</td><td>人气偏差(1)、点击诱饵(1)、不公平(1)</td></tr><tr><td>Yelp</td><td>2189457</td><td>1162119</td><td>8635403</td><td>0.043%</td><td>[1,5]</td><td>人气偏差(1)、曝光偏差(1)</td></tr><tr><td>Yahoo ！R3</td><td>15400</td><td>1000</td><td>311704</td><td>2.02%</td><td>[1,5]</td><td>选择偏差(6)、曝光偏差(3)、循环偏差(2)、位置偏差(1)、上下文偏差(1)</td></tr><tr><td>Coat</td><td>290</td><td>300</td><td>6960</td><td>8.00%</td><td>[1,5]</td><td>选择偏差(7)、曝光偏差(1)、循环偏差(1)</td></tr></table></body></html>

# 4.1常用数据集

MovieLens包含多个用户对多部电影的评级数据和电影元数据信息。众多研究在MovieLens数据集上进行去偏实验，缓解了其中的人气偏差[31\~33,43,4450,57,81]、不公平[45,52,54,61,84]、选择偏差[10,58,6677]、曝光偏差[70]、一致性偏差[80]和循环偏差[83]。相关的电影数据集还有 Netflix，文献[80]使用该数据集进行实验缓解了一致性偏差。

Last.fm是一个在线音乐数据集，包含用户的收听记录以及匿名用户的社交网络情况。有研究缓解了其中的人气偏差[31,32]、曝光偏差[41]和不公平问题[61]。

Epinions数据集被广泛应用在商品推荐领域，有相关研究缓解了该数据集中的人气偏差[33,44]和选择偏差[48]。

Adressa数据集包含了用户对文章的评分记录。有相关研究缓解了该数据集中的人气偏差[81]、点击诱饵[19]和不公平问题[45]。Yelp数据集是美国最大的点评网站内部整理得到的数据集。文献[41]和文献[81]分别缓解了该数据集中的曝光偏差和人气偏差。

Yahoo！R3是音乐服务推荐中的一个数据集，其中测试集通过要求用户对随机选择的歌曲进行评分来收集。当前众多研究缓解了该数据集中的选择偏差[8,10,1139,47,58,79]、循环偏差[38,42]、位置偏差[75]、曝光偏差[70,72]和上下文偏差[49]。Coat数据集包含机械工人对外套的评分。其中测试集是通过要求工人对随机选择的外套进行评分而收集。众多研究缓解了该数据集中的选择偏差[8,10,1139,47,58,77]、循环偏差[42]和曝光偏差[72]

# 4.2性能评价指标

推荐算法的评估指标根据推荐任务的不同可分为评分预测指标、集合推荐指标、排名推荐指标以及偏差衡量指标，其中前三类评价指标都属于传统性能评价指标。在不考虑偏差的推荐算法中，评分预测指标降低，或者集合推荐指标和排名推荐指标升高，能直接代表推荐效果的提升。在考虑偏差的研究中，除了评分预测指标降低、集合推荐指标和排名推荐指标升高，还有偏差衡量效果指标的变化，可以代表去偏效果的提升，进而提升推荐效果。

# 4.2.1传统性能评价指标

评分预测指标。评分预测的准确度一般根据均方根误差(RMSE)、平均绝对误差(MAE)和均方误差(MSE)计算。去除偏差的效果越好，评分预测指标就会越小，推荐效果越好。

集合推荐指标。由于数据稀疏性和冷启动问题的存在，有时直接预测用户对物品的评分是困难的，TOP-N推荐方法被广泛使用，不再预测用户对物品的评分，而是生成一组用户最有可能喜欢的物品集合推荐给用户。去除偏差的效果越好，集合推荐指标就会越大。TOP-N推荐中广泛使用的推荐效果指标包括准确率、召回率、F1指标等。

排名推荐指标。当推荐物品的数量很大时，用户会更重视推荐列表中排在前面的物品，去除偏差的效果越好，排名推荐指标就会越大。常用的排名度量指标包括归一化折扣累计收益和平均准确率。

推荐领域数据集众多，且评价指标多样，本文对所涉及参考文献的实验效果进行了汇总对比。由于包含来自随机实验的无偏数据，Coat和Yahoo!R3数据集在推荐系统中的偏差领域被广泛使用，因此本文整理出Coat和Yahoo!R3上的部分实验数据，如表6和表7所示，希望为后续研究提供一定的指导性，从表中可以看出，因果性去偏方法在评分预测指标上较有优势但优势不明显，而在集合推荐指标上的效果对比显示，相关性的解决方案指标效果较好，也间接证明了基于相关性的偏差解决方案拟合数据效果更好，而基于因果性的偏差解决方案只能拟合一部分数据。

表6评分预测指标效果对比  
Tab.6Comparison of the performance of scoring predictive metrics   

<html><body><table><tr><td rowspan="2">文献</td><td rowspan="2">去偏 方法</td><td colspan="3">Coat</td><td colspan="3">Yahoo!R3</td></tr><tr><td>RMSE</td><td>MAE</td><td>MSE</td><td>RMSE</td><td>MAE</td><td>MSE</td></tr><tr><td>[8]</td><td>因果</td><td>:</td><td>0.756</td><td>0.967</td><td></td><td>0.736</td><td>0.957</td></tr><tr><td>[39]</td><td>相关</td><td>-</td><td>0.759</td><td>0.973</td><td></td><td>0.774</td><td>0.977</td></tr><tr><td>[47]</td><td>相关</td><td>0.857</td><td>0.670</td><td></td><td>1.165</td><td>0.771</td><td>:</td></tr><tr><td>[55]</td><td>相关</td><td></td><td>0.878</td><td>1.129</td><td></td><td>0.999</td><td>1.518</td></tr><tr><td>[58]</td><td>相关</td><td></td><td>0.831</td><td>1.105</td><td></td><td>0.765</td><td>1.014</td></tr></table></body></html>

表7集合推荐指标效果对比  
Tab.7Comparison of the performance of collection recommendation metrics   

<html><body><table><tr><td rowspan="2">文献</td><td rowspan="2">去偏方法</td><td colspan="3">Yahoo!R3</td><td colspan="3">Coat</td></tr><tr><td>Recall@5</td><td>NDCG@5</td><td>MAP @3</td><td>Recall@5</td><td>NDCG@5</td><td>MAP @3</td></tr><tr><td>[40]</td><td>相关</td><td></td><td>0.645</td><td></td><td></td><td>0.522</td><td></td></tr><tr><td>[72]</td><td>因果</td><td>:</td><td>:</td><td>0.6694</td><td></td><td></td><td>0.6741</td></tr><tr><td>[77]</td><td>因果</td><td>0.3388</td><td>0.2785</td><td>0.2068</td><td>0.3952</td><td>0.3984</td><td>0.2354</td></tr><tr><td>[79]</td><td>因果</td><td></td><td>0.6206</td><td>：</td><td></td><td>：</td><td>-</td></tr></table></body></html>

# 4.2.2偏差衡量指标

目前推荐系统中的偏差研究还不够完善和全面，因此，暂时还没有较为统一和权威的偏差衡量指标。因此本文对前述相关文献中所提出的偏差衡量指标进行汇总，希望为后续的推荐系统偏差研究提供参考。

ARP(Average Recommendation Popularity)指标用来计算每个列表中推荐物品的平均受欢迎程度，对于推荐列表中的任何给定建议物品，它测量这些物品的平均评分数，如式(1)所示，其中 $\mathbf { \boldsymbol { \mathcal { O } } } ( i )$ 表示培训集中物品i的评级次数。但是ARP指标会因为算法向每个人推荐一些非常不受欢迎的物品而取值较低，为了弥补这一缺点，出现了另一个指标来表示所有用户中独特推荐物品的比率，用来度量一个算法在多大程度上增加了唯一推荐物品的数量，如式(2)所示，此指标的值越高，说明推荐列表涵盖的物品类别越多，但是此指标不区分物品推荐的次数。所以经常考虑基尼指数来以确保建议在所有物品中公平分布。

$$
A R P = \frac { 1 } { \left| U \right| } \sum _ { u \in U } \frac { \sum _ { i \in L _ { u } } \mathcal { O } ( i ) } { \left| L _ { u } \right| }
$$

$$
A g g - D i \nu = \frac { \left| U _ { u \in \nu } L _ { u } \right| } { \left| I \right| }
$$

基尼指数用来测量推荐物品频率分布的不均匀性。如果经常推荐某些物品而忽略其他物品，基尼指数将很高。如式(3)所示。其中， $p ( i \mid L )$ 是物品i在 $L$ 中出现的比率。

$$
\operatorname { G i n i } ( L ) = 1 - { \frac { 1 } { | I | - 1 } } \sum _ { k = 1 } ^ { | I | } ( 2 k { - } | I | - 1 ) p \left( i _ { k } | \ L \right)
$$

文献[50]为了量化人气偏差，选择使用基尼系数来衡量与物品受欢迎程度相对应的真阳性率的平等性，假设物品i的

点击量为 $C _ { i }$ ，如式(4)(5)所示。其中， $A _ { i }$ 表示喜欢物品i的匹配用户总数，物品索引从1到 $M$ ，Gini的取值范围[-1,1]，取值越小代表人气偏差越小。

$$
T P R _ { i } = \frac { C _ { i } } { A _ { i } }
$$

$$
G i n i = \frac { \displaystyle \sum _ { i \in I } ( 2 i - M - 1 ) T P R _ { i } } { \displaystyle M \sum _ { i \in I } T P R _ { i } }
$$

文献[54]使用了人气率(PopularityRate)作为一种公平性度量方式。它是指推荐列表中受欢迎的物品相对于列表中的物品总数的比值，也可以看做受欢迎程度的公平性度量。度量值越小，系统越公平。文献[54]也使用基尼指数来量化个体推荐质量的不公平程度，给出所有物品的印象列表$M = \left[ g _ { 1 } , g _ { 2 } , \cdots , g _ { | l | } \right]$ ，基尼指数公式如公式(6)下。其中， $\overline { { g } }$ 表示印象列表的均值。

$$
G i n i I n d e x ( G ) = \frac { 1 } { 2 | I | ^ { 2 } \overline { { { g } } } } \sum _ { i = 1 } ^ { | I | } \sum _ { j = 1 } ^ { | I | } \bigl | g _ { i } - g _ { j } \bigr |
$$

文献[52]提出了一个指标平均贴现收益(MDG，MeanDiscountedGain)来衡量公平性，公式如下式(7)所示。其中，$U _ { i } ^ { + }$ 是新物品i在测试集中的匹配用户集， $\hat { z } _ { u , i }$ 是物品i在用户 $u$ 推荐列表中的排序位置。 $M D G _ { i } = 0$ 意味着物品i在测试期间并没有推荐给喜欢它的用户， $M D G _ { \mathrm { i } } = 1$ 意味着在测试过程中，物品i对所有匹配用户都排名第一。

$$
\ M D G _ { i } = \frac { 1 } { | U _ { i } ^ { + } | } \sum _ { u \in U _ { i } ^ { + } } \frac { \delta ( \hat { z } _ { u , i } \leq k ) } { \log ( 1 + \hat { z } _ { u , i } ) }
$$

文献[57]使用惊喜度指标，该指标反映了在推荐列表中为用户找到物品的意外程度，它是通过计算在为用户 $u$ 准备的推荐列表 $L _ { u }$ 的 $p$ 位置上找到物品i的可能性相对于随机用户找到该物品的可能性，公式如式(8-10)所示，例如，仅基于人气的非个性化推荐策略的得分为0，如果只推荐不同的和用户不相关的物品，包括长尾物品，得分也是0。

$$
{ \mathrm { \Delta } } \psi _ { u } \circledast k = \frac { 1 } { k } \Bigg [ \sum _ { p = 1 } ^ { k } \operatorname* { m a x } \left( \operatorname* { P r } _ { L _ { u } ^ { k } [ p ] } ( u ) - \operatorname* { P r } _ { L _ { u } ^ { k } [ p ] } ( U ) , 0 \right) \cdot r ( u , i ) \Bigg ]
$$

$$
\mathrm { P r } _ { i } ( u ) = \frac { k - \mathrm { r a n k } _ { i } } { k - 1 }
$$

$$
\operatorname* { P r } _ { i } ( U ) = { \frac { \displaystyle \sum _ { u \in U } P r _ { i } ( u ) } { \displaystyle | U | } }
$$

# 5 研究趋势分析和展望

本文将推荐系统中的偏差研究分为相关性缓解偏差和因果性缓解偏差，按不同的类别分别对相关研究进行分析和展望。

(1)前处理的技术手段主要有均匀数据和采样，数据的收集和处理有可能会损害用户体验，成本较高，所以很多研究致力于更好的利用均匀数据或者结合其他技术手段来达到缓解偏差的目的，如何更好的利用均匀数据以及更优质的采样策略是接下来的研究可以关注的问题。而后处理是在模型输出结果之后进行调整来缓解偏差问题，方法较为简单，成本低且具有一定的可解释性，后续研究可以定义更优质的评估器和重排序策略来缓解推荐系统中的偏差问题。

(2)中处理主要是通过一些训练模型或者手段来纠正偏差，相较于前处理和后处理，可解释性会较差，且相较于前处理和后处理，中处理训练的模型会更依赖于训练数据，模型的可移植性不高。构建更优质的模型、提高模型的可解释性以及提升去偏模型的通用性是接下来主要的研究问题。

(3)利用因果技术解决推荐系统中的偏差，主要分为基于IPS的研究和基于因果图的研究。利用IPS技术缓解推荐系统中的偏差主要是通过修正评价指标和样本加权两种方式，各个研究的主要不同之处在于倾向分数的计算以及其所基于的假设。该方法的效果好坏很大程度上依赖于倾向分数计算的准确性，倾向分数的不准确性会导致该方法的方差较大。关于倾向分数的计算，有的研究使用单纯自定义的函数来计算，有的进行一下预先的实验来提前确定，也有的通过无偏的模型从数据中来学习倾向分数。如何更加准确的计算倾向分数和改善IPS方差大的缺点将是未来主要的研究问题。

(4)基于因果图的因果性去偏主要思想就是理清推荐系统中的因果关系，定位到偏差的位置，然后利用反事实推断来去掉偏差带来的消极影响，难点是如何确定各种因果关系，只有拟定的因果关系符合整个推荐过程的因果关系，最终才会带来推荐效果的提升。未来的研究方向应是利用更准确细致的因果图，能够更全面理清推荐过程的因果关系，发现更细粒度的因果关系，去掉由混淆因子带来的虚假相关性，保留用户作出某种反馈行为的因果关系，进而准确捕捉隐藏于混淆反馈数据中的真实用户偏好，更好的提升推荐效果。

(5)由于同一推荐场景中会同时存在多种偏差，只解决某一种偏差并不能保证推荐算法的无偏性，最大程度的提升推荐效果，如何去除多种偏差也是亟待解决的一个问题。另外，传统的指标不足以衡量推荐问题的偏差程度，而目前尚未有统一的偏差衡量指标，更合理有效和统一的偏差衡量指标的出现能规范推荐算法偏差的相关研究。另外，像Yahoo！R3和Coat包含无偏数据的数据集的搜集和发布，也会极大的促进推荐系统偏差方面研究的进展。

# 6 结束语

由于推荐系统解决“信息过载”问题的有效性，推荐系统在各个领域的应用广泛且普遍，其中不可忽略的偏差问题也引起了广大学者和业界的关注和研究。偏差的存在影响了推荐效果，如何妥善缓解和处理偏差问题就显得十分重要。因果技术能够发现整个推荐过程中的因果关系，有利于准确清晰了解整个推荐过程的因果关系。同时也提供了一定的可解释性。为了更好的理解推荐系统中的各种偏差，本文首先根据不同的产生主体对偏差进行分类，从主体角度划分偏差的类别，有利于统一去除同一个主体产生的各种偏差，为一次性去除多种偏差提供思路。其次本文重点从相关性和因果性的角度分析和对比了推荐系统中有关解决偏差的各个研究希望能促进使用因果手段解决推荐系统偏差的研究，接下来本文总结和分析了当前推荐系统偏差研究普遍使用的数据集和性能评价指标以及新提出的偏差衡量指标，希望为偏差衡量指标的研究提供思路，最后对推荐系统中的偏差研究今后的发展方向进行探讨和展望。

# 参考文献：

[1]Chen Jiawei,Dong Hande,Wang Xian，et al.Bias and debias in recommender system:A survey and future directions [EB/OL].(2010) [2022-02-10]. https://arxiv.org/pdf/2010.03240.pdf.   
[2]Marlin B,ZemelR S,Roweis S,et al.Collaborative filtering and the missing at random assumption [EB/OL]. (2012） [2022-02-10]. https://arxiv.org/pdf/12.06.5267.pdf.   
[3]Yuan Bowen,Liu Yaxu,HsiaJY,et al.Unbiased Ad click prediction for position-aware advertising systems [C]//Fourteenth ACM Conference on Recommender Systems.New York:ACMPress,2020:368-377.   
[4]Joachims T,GrankaL,PanB,et al.Accurately interpreting clickthrough dataasimplicit feedback[C]//ACM SIGIRForum.New York:ACM Press,2017,51(1): 4-11.   
[5]Xu Shuyuan,Ge Yingqiang,Li Yunqi,et al.Causal Collaborative Filtering [EB/OL]. (2021） [2022-02-10]. https://arxiv. org/pdf/2110.

# 07122. pdf.

[6]李孟浩，赵学健，余云峰，等．推荐算法研究进展[J/OL].小型微型 计算机系统,2022,43(03):544-554.(2021-11-06).http://kns.cnki. net/kcms/deta1l/21.1106.1P.202105U/.1558.004.html. (L1 Menghao, Zhao Xuejian,Yu Yunfeng，et al.Survey on research progress of recommendation algorithms [J/OL]. Journal of Chinese Computer Systems,2022,43 (03): 544-554. (2021-05-07)[2022-02-10]. ttp://kns. cnki. net/kcms/detail/21.1106.TP.20210507.1358.004.html.)

[7]于蒙，何文涛，周绪川，等．推荐系统综述[J/OL].计算机应用, 2021，1-16.(2021-04-18)[2022-02-10].http://kns.cnki. net/kcms/detail/51.1307.tp.20210922.1115.002.html.(Yu Meng,He Wentao,Zhou Xuchuan,et al.Overview of recommendation system [J/OL].Journal of Computer Applications,2021,1-16.(2021-04-18) [2022-02-10]. http://kns.cnki. net/kcms/detail/21.1106.TP.20210507. 1358. 004. html.)   
[8]Wang Xiaojie, Zhang Rui, Sun Yu,et al.Doubly robust joint learning for recommendation on data missing not at random [C]// International Conference on Machine Learning. New York: ACM Press,2019: 6638- 6647.   
[9]Zhang Wenhao,Bao Wentian,Liu Xiaoyang,et al.Large-scale causal approaches to debiasing post-click conversion rate estimation with multitask learning [Cl/ Proceedings of The Web Conference 2020.New York: ACM Press,2020: 2775-2781.   
[10] Saito Y.Doubly robust estimator for ranking metrics with post-click conversions [C]// Fourteenth ACM Conference on Recommender Systems.New York: ACM Press,2020:92-100.   
[11] Guo Siyuan, Zou Lixin,Liu Yiding,et al. Enhanced Doubly Robust Learning for Debiasing Post-click Conversion Rate Estimation [EB/OL]. (2021) [2022-02-10]. htps://arxiv.org/pdf/2105.13623.pdf.   
[12] Wang Tian, Wang Dashun. Why Amazon's ratings might mislead you: The story of herding effects [J].Big data,2014,2(4):196-204.   
[13] Liu Yiming,Cao Xuezhi, Yu Yong.Are You Influenced by Others When Rating?Improve Rating Prediction by Conformity Modeling [C]// Proceedings of the 10th ACM Conference on Recommender Systems. New York: ACM Press,2016: 269-272.   
[14] Ma H,King I, Lyu M R. Learning to recommend with social trust ensemble [C]// Proceedings of the 32nd international ACM SIGIR conference on Research and development in information retrieval. New York:ACM Press,2009:203-210.   
[15] Tang J,Gao H, Liu H. mTrust: Discerning multi-faceted trust in a connected world [C]// Proceedings of the fifth ACM international conference on Web search and data mining.New York: ACM Pres,2012: 93-102.   
[16] Chaney AJB,Blei D M,Eliassi-Rad T.Aprobabilistic model forusing social networks in personalized item recommendation [Cl/ Proceedings of the 9th ACM Conference on Recommender Systems.New York: ACM Press, 2015: 43-50.   
[17] Wang Xin, Hoi S C H,Ester M,et al. Learning personalized preference of strong and weak ties for social recommendation [C]// Proceedings of the 26th International Conference on World Wide Web.New York: ACM Press,2017: 1601-1610.   
[18] Ding Jingtao,Quan Yuhan,He Xiangnan,et al. Reinforced Negative Sampling for Recommendation with Exposure Data [C]// International Joint Conference on Artificial Intelligence.Palo Alto, CA: AAAI Press, 2019: 2230-2236.   
[19] Wang Wenjie,Feng Fuli,He Xiangnan,et al. Clickscan be cheating: Counterfactual recommendation for mitigating clickbait issue [C]// Proceedings of the 44th International ACM SIGIR Conference on Press,2021: 1288-1297.   
[20] Lu Hongyu, Zhang Min,Ma Shaoping.Between clicks and satisfaction: Study on multi-phase user preferences and satisfaction for online news reading [C]//The 41st International ACM SIGIR Conference on Research & Development in Information Retrieval.New York:ACM Press,2018: 435-444.   
[21] Lu Hongyu,Zhang Min,Ma Weizhi,et al.Efects of User Negative Experience in Mobile News Streaming [C]// Proceedings of the 42nd International ACM SIGIR Conference on Research and Development in Information Retrieval.New York:ACMPress,2019:705-714.   
[22] Zannettou S,Chatzis S,Papadamou K,et al. The good,the bad and the bait: Detecting and characterizing clickbait on youtube [C]// 2018 IEEE Security and Privacy Workshops(SPW).Piscataway,NJ:IEEE Press, 2018: 63-69.   
[23] Wen Hongyi, Yang Longqi,Estrin D.Leveraging post-click feedback for content recommendations [C]// Proceedingsofthe 13th ACM Conference on Recommender Systems.New York:ACM Press,2019: 278-286.   
[24] Yi Xing,Hong Lianjie,Zhong Erheng,et al. Beyond clicks: dwell time for personalization [C]// Proceedings of the 8th ACM Conference on Recommender systems.New York: ACMPress,2014:113-120.   
[25] Yin Peifeng,Luo Ping,Lee W C,et al.Silence is also evidence: interpreting dwell time for recommendation from psychological perspective [C]// Proceedings of the 19th ACM SIGKDD international conference on Knowledge discovery and data mining. New York: ACM Press,2013: 989-997.   
[26] Yang B,Lee S,Park S,et al. Exploiting various implicit feedback for collaborative filtering [C]// Proceedings of the 2lst International Conference on World Wide Web.New York: ACMPress,2012: 639-640.   
[27] Liu Chao,White R W,Dumais S.Understanding web browsing behaviors through Weibull analysis of dwell time [C]// Proceedings of the 33rd international ACM SIGIR conference on Research and development in information retrieval. New York: ACMPress,2010: 379-386.   
[28] Wu Xinwei,Chen Hechang,Zhao Jiazhu,et al.Unbiased learning to rank infeeds recommendation [C]//Proceedingsof the 14th ACM International Conference on Web Search and Data Mining.New York: ACM Press,2021: 490-498.   
[29]Fang Z,Agarwal A,Joachims T.Intervention harvesting for contextdependent examination-bias estimation [C]// Proceedings of the 42nd International ACM SIGIR Conference on Research and Development in Information Retrieval.New York: ACMPress,2019: 825-834.   
[30]Abdollahpouri H,Mansoury M.Multi-sided Exposure Biasin Recommendation[C]//ACM KDD WorkshoponIndustrial Recommendation Systems.New York: ACMPress,2020.   
[31]Abdollahpouri H,Mansoury M,Burke R,et al.Addressing the Multistakeholder Impact of Popularity Bias in Recommendation Through Calibration [EB/OL].[2022-02-10]. https://arxiv.org/pdf/2007.12230. pdf.   
[32] Abdollahpouri H,Mansoury M, Burke R,et al. User-centered Evaluation of Popularity Bias in Recommender Systems [C]// Proceedings of the 29th ACM ConferenceonUserModeling， Adaptationand Personalization.New York: ACM Press,2021:119-129.   
[33] Abdollahpouri H,Burke R,Mobasher B.Managing popularity bias in recommender systems with personalized re-ranking [C]// The thirtysecond international flairs conference.Palo Alto,CA: AAAI Press,2019   
[34] Patro G K,Biswas A,Ganguly N,et al.Fairrec: Two-sided fairness for personalized recommendations in two-sided platforms [C]/ Proceedings Fourteenth ACM Conterence on Kecommender Systems.New York: ACMPress,2020:101-110.   
[36] Khademi A,Lee S,Foley D,et al.Fairness in algorithmic decision making: An excursion through the lens of causality [Cl//The World Wide Web Conference.New York: ACMPress,2019:2907-2914.   
[37]赵森栋，刘挺．因果关系及其在社会媒体上的应用研究综述[J]．软 件学报,2014,25 (12): 2733-2752.(Zhao Sendong,Liu Ting.Causality and its applications in social media: A survey[J]. Journal of Software, 2014,25 (12): 2733 - 2752.)   
[38] Liu Dugang，Cheng Pengxiang，Dong Zhenhua,et al.A general knowledge distillation framework for counterfactual recommendation via uniform data [C]//Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval.New York: ACM Press,2020: 831-840.   
[39] Wang Xiaojie, Zhang Rui,Sun Yu,et al. Combating Selection Biases in Recommender Systems with a Few Unbiased Ratings [C]/ Proceedings of the 14th ACM International Conference on Web Search and Data Mining. New York: ACM Press,2021: 427-435.   
[40] Chen Jinwei, Dong Hande,Qiu Yang,et al.AutoDebias: Learning to debias for recommendation [C]// Proceedings of the 44th International ACM SIGIR Conference on Research and Development in Information Retrieval.New York:ACMPress,2021: 21-30.   
[41] Wang Xiang,Xu Yaokun,He Xiangnan,et al. Reinforced negative sampling over knowledge graph for recommendation [C]//Proceedings of The Web Conference 2020.New York:ACM Press,2020: 99-109.   
[42] Yu Jiangxiang,Zhu Hong,Chang C Y,et al. Influence function for unbiased recommendation [C]//Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval.New York: ACMPress,2020:1929-1932.   
[43] BorgesR, StefanidisK. Onmitigatingpopularitybiasin recommendations via variational autoencoders [C]// Proceedings of the 36th Annual ACM Symposium on Applied Computing. New York: ACM Press, 2021: 1383-1389.   
[44] Zhu Ziwei,He Yun, Zhao Xing,et al. Popularity-Opportunity Bias in Collaborative Filtering [C]//Proceedings of the 14th ACM International Conference on Web Search and Data Mining. New York: ACM Press, 2021: 85-93.   
[45] Zhu Ziwei, Wang Jianling,Caverlee J. Measuring and mitigating item under-recommendation bias in personalized ranking systems[Cl// Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval.New York: ACM Press,2020: 449-458.   
[46] Wu Chuhan,Wu Fangzhao,Qi Tao，et al.Fairness-aware News Recommendation with Decomposed Adversarial Learning[C]// Proceedings of the AAAI Conference on Artificial Inteligence.Palo Alto, CA: AAAI Press,2021,35 (5): 4462-4469.   
[47] Zhang Qi, Cao Longbin,Shi Chongyang,et al. Tripartite Collaborative Filtering with Observability and Selection for Debiasing Rating Estimation on Missing-Not-at-Random Data [C]// Proceedings of the AAAI Conference on Artificial Intelligence.New York:ACM Press, 2021,35 (5): 4671-4678.   
[48] Chen Jiawei,Wang Can,Ester M,et al.Social recommendation with mising not at random data [C]//2018 IEEE International Conference on Data Mining (ICDM).Piscataway,NJ: IEEE Press,2018: 29-38.   
[49] Zhuang Honglei,Qin Zhen,Wang Xuanhui,et al.Cross-positional ZUZ1. NeW YOrK: ACM Press,ZU∠I: /88-/9/.   
[50] Zhu Ziwei,He Yun,Zhao Xing,etal.Popularity Bias in Dynamic Recommendation [C]// Proceedings of the 27th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD). New York: ACM Press,2021: 2439-2449.   
[51] Agarwal A, Wang Xuanhui, Li Cheng,et al.Addressing trust bias for unbiased learning-to-rank [Cl//The World Wide Web Conference. New York:ACMPress,2019:4-14.   
[52] Zhu Ziwei, Kim J, Nguyen T,etal. Fairness among New Items inCold Start Recommender Systems [C]// Proceedings of the 44th International ACM SIGIR Conference on Research and Development in Information Retrieval (SIGIR). New York: ACM Press,2021: 767-776.   
[53] Islam R,Keya K N,Zeng Ziqian,et al. Debiasing career recommendationswith neural fair collaborative filtering [C]// Proceedings of the Web Conference 2021.New York: ACM Press,2021: 3779-3790.   
[54] Ge Yingqiang,Liu Shuchang, Gao Ruoyuan,et al. Towards Long-term Fairness in Recommendation [C]// Proceedings of the 14th ACM International Conference on Web Search and Data Mining. New York: ACM Press,2021: 445-453.   
[55] Huang Jin, Oosterhuis H,De R M,et al. Keeping Dataset Biases out of the Simulation [C]// Proceedings of the 14th ACM Conference on Recommender Systems (RecSys). New York: ACM Press,2020: 190- 199.   
[56] McInerney J, Brost B,Chandar P,etal. Counterfactual evaluationof slate recommendations withsequentialreward interactions[C/ Proceding of the 26th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining. New York: ACMPress,2020:1779-1788.   
[57] Parapar J,Radlinski F.Diverse User Preference Elicitation with MultiArmed Bandits [Cl// Proceedings of the 14th ACM Intermational Conference on Web Search and Data Mining.New York:ACMPress, 2021: 130-138.   
[58] Saito Y.Asymmetric Tri-training for Debiasing Missing-Not-At-Random Explicit Feedback [C]// Proceedingsof the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval. New York: ACM Press,2020: 309-318.   
[59] Li R Z,Urbano J,Hanjalic A.Leave No User Behind: Towards Improving the Utility of Recommender Systems for Non-mainstream Users [C]/ Proceedings of the 14th ACM International Conference on Web Search and Data Mining.New York: ACM Press,2021: 103-111.   
[60] Chen Jiawei,Wang Can,Zhou Sheng,et al.Fast adaptively weighted matrix factorization for recommendation with implicit feedback [C]// Proceedings of the AAAI Conference on Artificial Intelligence.Palo Alto, CA: AAAI Press,2020,34 (04): 3470-3477.   
[61] Wu Le, Chen Lei, Shao Pengyang,et al. Learning Fair Representations for Recommendation: A Graph-based Perspective [C]// Proceedings of the Web Conference 2021.New York: ACMPress,2021: 2198-2208.   
[62] Fu Zuohui, Xian Yikun, Gao Ruoyuan,et al. Fairness-aware explainable recommendation over knowledge graphs [C]// Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval. New York:ACMPress,2020: 69-78.   
[63] Li Yunqi, Chen Hanxiong,Fu Zuohui,et al. User-oriented Fairness in Recommendation [Cl// Proceedings of the Web Conference 2021. New York: ACM Press,2021: 624-632.   
[64] Yao Liuyi, Chu Zhixuan,Li Sheng,et al.A Survey on Causal Inference [J]. ACM Trans on Knowledge Discovery from Data (TKDD),2021,15 (5): 1-46.   
[65] Agarwal A,Zaitsev I,Wang Xuanhui,et al.Estimating position bias without intrusive interventions [C]// Proceedings of the Twelfth ACM International Conference on Web Search and Data Mining.New York: ACM Press,2019: 474-482.   
[66] Schnabel T, Swaminathan A,Singh A,et al.Recommendations as treatments:Debiasing learning and evaluation [C]// International Conference on Machine Learning.Cambridge MA:JMLR,2016:1670- 1679.   
[67] Joachims T, Swaminathan A,Schnabel T.Unbiased learning-to-rank with biased feedback [C]//Proceedings of the Tenth ACM International Conference on Web Search and Data Mining.New York:ACMPress, 2017: 781-789.   
[68] Qin Zhen, Chen S J,Metzler D,et al. Attribute-based propensity for unbiased learning in recommender systems:Algorithm and case studies [C]// Proceedings of the 26th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining. New York: ACM Press,2020: 2359-2367.   
[69] Yang Longqi,Cui Yin, Xuan Yuan,et al. Unbiased ofline recommender evaluationformissing-not-at-randomimplicitfeedback[C]// Proceedings of the 12th ACM Conference on Recommender Systems. New York: ACM Press,2018: 279-287.   
[70] Saito Y, Yaginuma S,Nishino Y, et al. Unbiased recommender learning from missing-not-at-random implicit feedback [C]//Proceedings of the 13th International Conference on Web Search and Data Mining. New York: ACM Press,2020: 501-509.   
[71] Sato M,Takemori S,Singh J,et al.Unbiased learning for the causal effect of recommendation [C]/ Fourteenth ACM Conference on Recommender Systems.New York: ACM Press,2020:378-387.   
[72] Zhu Ziwei,He Yun，Zhang Yin，et al.Unbiased Implicit Recommendation and Propensity Estimation via Combinational Joint Learning [C]//Fourteenth ACM Conference on Recommender Systems. New York: ACM Press,2020: 551-556.   
[73] Schnabel T, Bennett P N.Debiasing item-to-item recommendations with small annotated datasets [C]// Fourteenth ACM Conference on Recommender Systems. New York: ACM Press,2020: 73-81.   
[74]骆锦潍，刘杜钢，潘微科，明仲．基于改进的倾向得分估计的无偏推 荐模型[J].计算机应用,2021,41(12):3508-3514.(Luo Jinwei,Liu Dugang,Pan Weike,et al. Unbiased recommendation model based on improved propensity score estimation [J].Journal of Computer Applications,2021,41 (12): 3508-3514.)   
[75] Agarwal A,Takatsu K, Zaitsev I,et al.A general framework for counterfactual learning-to-rank [C]//Proceedingsofthe 42nd International ACM SIGIR Conference on Research and Development in Information Retrieval. New York: ACM Press,2019: 5-14.   
[76] Vardasbi A,de Rijke M,Markov I. Cascade model-based propensity estimation for counterfactual learning to rank [C]// Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval. New York:ACM Press,2020: 2089-2092.   
[77] Lee J,Park S,Lee J.Dual Unbiased Recommender Learning for Implicit Feedback [C]// Proceedings of the 44th International ACM SIGIR Conference on Research and Development in Information Retrieval.New York: ACM Press,2021: 1647-1651.   
[78] Wang Nan，Qin Zhen，Wang Xuanhui，et al. Non-Clicks Mean Irrelevant?Propensity Ratio Scoring As a Correction [C]/ Proceedings of the 14th ACM International Conference on Web Search and Data Mining. New York: ACM Press,2021: 481-489.   
[79] Wang Nan,Wang Xuanhui,Wang Hongning.Unbiased Learning to Rank viaPropensity RatioScoring[EB/OL].(2020）[2022-02-10]. https://arxiv.org/pdf/2005. 08480. pdf.   
[80] Zheng Yu,Gao Chen,Li Xiang,et al. Disentangling User Interest and Conformity for Recommendation with Causal Embedding [C]// Proceedings of the Web Conference 2021.New York:ACMPress,2021: 2980-2991.   
[81] Wei Tianxin，Feng Fuli，Chen Jiawei，et al.Model-agnostic counterfactual reasoning for eliminating popularity bias in recommender system [C]// Proceedings of the 27th ACM SIGKDD Conference on Knowledge Discovery & Data Mining. New York:ACM Press,2021: 1791-1800.   
[82] Zhang Yang,Feng Feng,He Xiangnan,et al.Causal Intervention for Leveraging Popularity Bias in Recommendation [EB/OL].(2021) [2022- 02-10]. htps://arxiv. org/pdf/2105. 06067. pdf.   
[83] Wang Wenjie,Feng Fuli，He Xiangnan，et al.Deconfounded Recommendation for Alleviating Bias Amplification [EB/OL]. (2021) [2022-02-10]. https://arxiv.org/pdf/2105.10648.pdf.   
[84] Li Yunqi,Chen Hanxiong,Xu Shuyuan,et al. Towards personalized fairness based on causal notion [C]// Proceedings of the 44th International ACM SIGIR Conference on Research and Development in Information Retrieval.New York:ACMPress,2021:1054-1063.   
[85] Ovaisi Z,Ahsan R, Zhang Y,et al. Correcting for selection bias in learning-to-rank systems [C]//Proceedings of The Web Conference 2020. New York: ACM Press,2020: 1863-1873.