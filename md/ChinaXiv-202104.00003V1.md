# 心理病理学网络理论、方法与挑战

陈琛1,2，王力1,2，曹成琦1,2，李根1,2(1 中国科学院心理研究所心理健康重点实验室创伤应激研究实验室，北京100101)(2中国科学院大学心理学系，北京100049)

摘要对于精神障碍这一概念的理解，传统DSM-ICD分类诊断系统和研究领域标准RDoC均基于潜变量视角，认为精神障碍的症状由其潜在共同原因所致。这2种观点都忽略了症状间的相互作用。不同于分类和维度视角，Borsboom在 2008年对精神障碍的概念化提出了的全新视角——心理病理学网络理论。此理论的核心观点是症状之间的动态因果关系构成了精神障碍。基于心理病理学网络理论的网络分析方法，主要以结合 EBIC 的 glass 算法估计症状间的偏相关网络，并通过网络中节点中心性与网络连接性等指标，来考查精神障碍症状的不同特性。近几年来，研究者发现心理病理学网络分析方法在对症状间因果关系的推断、核心症状的识别和网络结构的可靠性与可重复性方面仍面临一些挑战。这些挑战为心理病理学网络理论与方法指明了未来可能的发展方向。

关键词心理病理学，网络理论，网络分析，症状网络，核心症状，精神障碍，GGM

# 1.引言

对于精神障碍疾病(disorder)与症状(symptom)之间关系的刻画，目前存在以下两种主流观点。一种是以《精神疾病诊断和统计手册》(Diagnostic and Statistical Manual of Mental Disorders,DSM)和《国际疾病分类》(Intermational Clasification of Diseases,ICD)为代表的 DSM-ICD 分类诊断视角，认为症状反映的正是其共同原因——疾病实体(McNally,2016)。这一视角参考了传统医学的观点。就像脑部恶性肿瘤是引发头痛、健忘、视力模糊等并发症状的共同原因，潜在的创伤后应激障碍(Post-traumatic Stress Disorder, PTSD)也被认为是闯入性思维、闪回、高警觉等症状的共同原因(如图1)。另一种是由美国国立精神卫生研究所(National Institute of Mental Health,NIMH)提出的研究领域标准 RDoC(Research Domain Criteria,Insel et al.,2010)的维度取向(图2)，认为精神健康状况是多维度的连续谱，症状反映的是认知系统、负性效价系统、正性效价系统、情绪调节系统等不同潜在维度上的功能异常，而各种精神障碍实际上是不同症状维度相组合的结果(Adam,2013)。

![](images/b25a0af10f6aa03ad202bcf8d4f703a877348511d1bb0b9ae4cec74eb1aca720.jpg)  
图1.分类诊断视角下，创伤后应激障碍(PTSD)与其症状之间的关系(Borsboom&Cramer,2013)。图顶部的椭圆形代表PTSD这一潜在疾病变量，图底部的方框代表DSM系统中PTSD 的症状：闯入性思维、噩梦、闪回等。此模型中，箭头单向地从PTSD 指向其可观测症状，表示PTSD 是引发这些症状的共同原因。

![](images/b26c5918165a4d3c707c7d52f704545d0a66de475574b3f1e0a391f915c3be1f.jpg)  
图2.RDoC倡议的精神障碍研究框架：研究应关注于负性效价系统、正性效价系统、认知系统、社会加工系统、唤起／调节系统和感觉运动系统这六大人类主要功能领域展开，每个领域包含基因、分子、细胞、环路、生理、行为和自我报告这些基本分析单元。（资料来源：https://www.nimh.nih.gov/research/research-funded-by-nimh/rdoc/about-rdoc.shtml)

上述两种观点的本质差别在于疾病究竟是按类型(即在本质上是不同的类别)还是因程度(即在维度上有所不同)而不同(Hofmann etal.,2016)。但无论是分类还是维度视角，它们都认为症状的出现存在潜在的共同原因(无论是一个潜在疾病实体，还是多个潜在维度)。二者本质上都是要求满足"局部独立性"(即潜变量完全解释观测变量之间的协方差)的潜变量模型，也就要求症状之间不存在任何因果关联(Borsboom,2008;Hofmann et al.,2016)。这就导致基于这两种理论都忽略了症状间的相互作用(Borsboom& Cramer,2013;Schmittmann etal.,2013)。而在精神障碍的发生发展过程中，症状间的相互作用是很常见而基本的现象。例如，某PTSD 患者因遭受丧亲打击，处于持续的负性情绪状态而出现失眠状况，导致白天工作时难以集中注意力，与同事相处也容易被激惹，久而久之对原本有兴趣的事也失去兴趣，而这又进一步加剧了他的负性情绪。显然这些PTSD症状的发生有着明确的先后顺序，且症状之间存在着不可忽视的因果关系。

针对上述不足，Borsbo0m (2008)提出了一种对精神障碍全新的概念化方式——心理病理学网络，它为理解精神障碍的疾病与症状之间的关系提供了全新的视角；而基于这一理论的分析方法也逐渐发展成为心理计量学中近年来最为流行的研究方法之一(Guloksuz et al.,2017)。本文旨在让读者了解心理病理学网络理论及其方法，并提醒研究者注意现有网络分析方法所面临的挑战与机遇。本文将从以下四个方面展开论述：心理病理学网络理论、心理病理学网络分析方法、心理病理学网络理论与方法的应用及价值、心理病理学网络分析方法的主要局限和未来展望。

# 2.心理病理学网络理论

# 2.1核心观点与基本原理

与上述两种潜变量视角不同，心理病理学网络理论将精神障碍刻画为由相互作用的症状组成的因果系统(Borsboom& Cramer,2013)；症状也不再是疾病这一潜在共同原因的被动指标，而成为因果系统中的动态组成部分(Robinaugh et al.,2020)。概括说来，心理病理学网络理论的核心观点是：症状构成精神障碍，而非反映精神障碍；精神障碍是交互症状的动态网络，而非产生症状的潜在实体(McNally et al.,2015)。在这种视角下，PTSD症状不再如图1中PTSD这一潜在共同原因引起，而是如图3所示，闪回、噩梦和高警觉等 PTSD 症状之间有直接的因果联系，且正是这些PTSD 症状及其关联构成了PTSD 这一概念(McNally et al.,2017)。具体而言，Borsboom(2017)将心理病理学网络理论细化为以下5条原理：

原理1.复杂性：精神障碍基于一个由大量症状组分组成的网络，是一个不存在中央控制的复杂系统。精神障碍的本质是由该复杂系统所涌现出的一种现象。

原理2.症状-组成成分一致性：心理病理学网络中的组成成分与诊断手册中的症状一致对应。

原理3.直接因果联系：网络结构是由症状之间直接因果联系的图式产生的。

原理4.精神障碍遵循网络结构：心理病理网络具有非平凡的拓扑结构：某些症状比其他症状连接更为紧密，这些症状集团产生了精神障碍的现象——成簇的症状经常一起出现；网络中症状地位并非等价，即不同症状对网络的影响不同。

原理5.滞后性：精神障碍由紧密连接的症状网络中存在的滞后现象引起，也就是即使症状的触发原因消失了，症状仍会继续互相激活。

原理1阐明了精神障碍的是多方面原因的复杂系统。原理2与原理3则指明了心理病理学网络的症状和症状间的联系都属于网络的基本组成元素。而原理4中提及的症状分簇现象，则与目前将精神障碍定义为综合征这一趋势相符合：同一精神障碍的症状，比不同精神障碍的症状之间的因果联系更紧密。而原理5的滞后性在精神障碍中很常见，如在PTSD中，创伤后应激症状不会随其触发条件——创伤事件的褪去而消失(Borsboom,2017)。

![](images/11dd2e64742863510a5f80faddfcef3440c6ca3d8d06ce263ce7c49ac1f15b73.jpg)

图3.心理病理学网络理论视角下的PTSD 症状网络。17个节点分别代表 DSM-IV中17个PTSD症状：闯入性思维、噩梦、闪回、情绪反应、生理反应、回避创伤相关想法、回避创伤提示活动、创伤相关遗忘、丧失兴趣、情感疏离、情感麻木、对未来的负性信念、睡眠问题、易激惹、注意力难以集中、高警觉、惊跳反应。节点间的绿边代表症状间的正相关，红边代表负相关。边越粗，相关性越高；无边相连的节点间无相关。（资料来源：McNally 等(2017))

# 2.2精神障碍发生与维持的动态过程

上述 5条原理意味着精神障碍的出现与发展可以被认为是症状在网络中激活扩散的过程(Borsboom,2017)。在某些外部事件(如一些创伤性事件)的影响下，出现某些症状。而这些症状的出现会影响与之相连接症状的出现概率。因此，在网络结构中连接紧密的症状集团将趋于一起出现。当紧密相连的症状集团激活并互相维持时，演变成一组自我维持的心理病理症状，就产生了精神障碍(详见图 4)。而原理 5同样强调，这样的动态过程仅在连接较强的网络中发生。在连接较弱的网络中不存在滞后性，即严重的触发条件可能引起强烈的反应，但是由于症状之间的联系较弱，不足以自我维持，网络将逐渐恢复至原来的无症状状态(如图5所示)。

![](images/89c3bed6cba7569ba07270a27885bd88dc19160d79dc31d274c0a9b727caeb92.jpg)  
图4.网络理论中精神障碍的发展阶段。阶段1为无症状阶段，网络处于稳定的休眠状态；阶段2为网络初步激活阶段，某些症状被外部事件 E1直接激活；阶段3为症状传播阶段，阶段2中被激活的症状激活与其相连接的症状；阶段4为稳定的网络激活状态，若网络连接紧密，外部事件的消失不会使网络恢复，即网络自我维持并持续处于激活状态。(资料来源：根据 Borsboom(2017)绘制)

![](images/f538c0dabecf8abce5cc25ababee2863df936fc81d21324601beb85daba17d33.jpg)  
图5.连接较弱的网络(上图)具有韧性。症状可能由外部事件激活，但症状之间的互相作用不够强，无法导致自我维持的症状激活。相反，连接较强的网络(下图)可以自我维持激活状态，从而发展成为疾病状态。（资料来源：根据 Borsboom(2017)绘制)

在这种网络视角下，可将精神障碍(Mentaldisorder)定义为"强连接网络的稳定状态”，而心理健康(Mentalhealth)则对应定义为"弱连接网络的稳定状态”。心理病理学网络理论对于精神障碍与心理健康的认识，不再以"有无症状"作为衡量标准；它将精神状态定义为一种动态平衡状态，而症状网络恰好可以反映这一动态过程：在外部事件的触发下，弱连接的网络也可能表现出症状，如亲人去世后出现正常的哀伤情绪，但没有发展出其他症状成为重性抑郁障碍(Major Depression Disorder,MDD)；相反，强连接的网络由于某些抑制因素(如药物使用)也可能暂时不会出现症状。在这样的动态过程中，可类似定义强连接网络更易发展为精神障碍的性质为易感性(Vulnerablity)；而弱连接网络迅速恢复至心理健康状态的性质则可对应定义为心理韧性(Resilience)。由此看出，心理病理学网络理论在本质上挑战了传统心理病理学理论中存在疾病实体这一说法，将精神障碍刻画为由相互作用的症状组成的动态因果系统(Borsboom &Cramer,2013)，症状间的相互激活直接驱动了精神障碍的发生与维持。

# 3.心理病理学网络分析方法

# 3.1网络估计方法

目前估计心理病理学网络最常用的模型是偏相关网络(Epskamp&Fried,2018)，也可叫做高斯图模型(Graphical Gaussian Model,GGM,Lauritzen,1996)。在这种偏相关网络中，构成网络的基本元素为节点(node)和边(edge)，节点表示各个症状，节点之间相连边的权重代表节点之间的偏相关，即控制其他节点变量的影响之后两个节点变量间的相关性(Borsboom& Cramer,2013)。通常使用 glass(graphical leastabsolute shrinkage and selection operator,Epskamp&Fried,2018; Friedman et al.,2008)算法，通过扩展贝叶斯信息准则(Extended Bayesian Information Criterion,EBIC,Chen & Chen,2008)选定一个惩罚参数，对节点变量的协方差矩阵进行正则化，将变量之间可能的虚假相关约束为零，从而估计得到较为精简的稀疏网络结构(Epskamp et al.,2018a)。对于这种偏相关网络的估计与可视化过程，分别可在R 软件的 qgraph(Epskamp et al.,2012)和 bootnet (Epskamp et al.,2018a)程序包中实现。

对于经典的心理病理学症状网络，节点对应症状，节点之间的边对应症状之间的关联。如图3所示，17个节点分别代表由平民版创伤后应激障碍检查表(PTSDCheckList-Civilian Version,PCL-C)测量的 17个PTSD 症状，节点之间绿色的边代表症状间的正相关，如高警觉与惊跳反应之间的边；红色的边代表症状间的负相关，如噩梦与对未来的负性信念之间的边。边越粗，表示相关越高，反之越低。如高警觉与惊跳反应之间，情感麻木与情感疏离之间，以及对创伤提示物的躯体反应与心理反应之间的边明显比网络中其他边更粗，表明这三对症状在这17个 PTSD 症状之间具有较高的正相关，而闯入性思维与睡眠问题之间无边相连，可认为它们之间不存在任何直接关联。

# 3.2基本网络特征

心理病理学网络方法中考查的网络特征来自于图论，主要包括节点中心性(Epskamp et al.,2012)、节点预测性(Haslbeck&Waldorp,2018)、网络分簇性(Golino & Epskamp,2017)和网络连接性等。其中节点中心性(网络局部性质)与基于边的权重计算的网络连接性(网络整体结构)是心理病理学网络中最常用的两种网络特征(Robinaugh et al.,2020)。

# 3.2.1节点中心性

节点中心性反映节点在网络中的重要程度，主要通过节点强度(strength)来测量²。某节点的强度，由这个节点和与其直接相连节点之间所有边的权重绝对值之和来计算，反映了这个节点与网络中其他节点直接相连的程度(Opsahl et al.，2010)。对于症状网络，中心性高的节点可被认为是网络中的核心症状(central symptom,如图6中X1症状)，因为中心性高(即节点强度大)的症状，与其他症状之间关联更紧密，而按照心理病理学网络理论，当一个中心性高的节点被激活时，通过它进一步激活与其相连症状的概率也相对更高；而中心性较低(即节点强度较低)的节点可被认为是边缘症状(peripheral symptom,如图6 中X2、X3、X4及X5症状)。核心症状也被认为是可能预防个体在受到外界事件刺激后发展为精神障碍的有效干预靶点(Borsboom& Cramer,2013; Cramer & Borsboom,2015)。

![](images/81cc08c66e84cc4487c5fb80f86e6d26e48fe7d48d87b1bb9589efb5c8250fcb.jpg)

图6.由症状X1-X5组成的网络。症状X1与其他4个症状均为强连接，为此网络中的核心症状；症状X2-X5与其他症状的连接均只有1个强连接和2个弱连接，为此网络中的边缘症状。

# 3.2.2网络连接性

网络连接性，主要由全局强度(global strength，即网络中所有边的权重绝对值之和)和网络密度(density，即所估计的网络中边的数目占网络中所有节点可以构建出的总边数的百分比)测量。全局强度和网络密度共同反映了网络整体连接的紧密程度。如上文所言，连接性越强的网络(即全局强度越大)，刻画的是精神障碍易感性越强的状态，反之，连接性越弱的网络(即全局强度越小)，反映的是越具韧性的心理健康状态(Borsboom,2017)。如图7所示，可以将网络中的症状视为多米诺骨牌，将症状之间的联系视为多米诺骨牌之间的距离。连接性弱的网络类似于间隔很远的多米诺骨牌(图7中的左图)，一个多米诺骨牌的倒塌不太可能导致其他多米诺骨牌的倒塌，因为它们之间的距离相对较大。例如，如果症状 X1出现，由它导致其他症状发展的可能性相对较小。而连接性强的网络类似于间距很小的多米诺骨牌(图7中的右图)，一个多米诺骨牌的倒塌很可能触发到其他多米诺骨牌的倒塌。例如，症状X3的激活很可能像病毒在人群中的扩散一样，通过网络迅速传播到其他症状。

![](images/8f56bd8123c3d3ead36a2a2edb377b3446407abc17c40b52b1fbb848d14d93bb.jpg)  
图7.由症状 X1-X5组成的连接性强弱不同的网络及其类比多米诺骨牌图。左图为连接度较弱的网络，类似于间距较大的多米诺骨牌。右图为连接度较强的网络，类似于间距较小的多米诺骨牌。(资料来源：Cramer 等(2016))

# 3.3其他估计方法

除了基本的偏相关网络之外，还有一些其他新兴的网络模型，如贝叶斯网络、相对重要性网络(例如Robinaugh etal.,2014)等。其中较为常用的是贝叶斯网络。

贝叶斯网络是新兴发展起来的一种可以利用横断面观测数据做出一定因果推断的网络估计方法。其常见算法有R 软件的 bnleam程序包(Scutari,2010)中的 hill-climbing 算法：通过不断迭代地添加边、去掉边、反转边的方向，以确定最小 BIC确定最优模型作为网络结构，并生成有向无环图式的网络(directedacyclic graphs,DAG,Kalisch& Buhlmann,2007;Pearl,200)。贝叶斯网络应用于心理病理学网络，可以在一定程度上探究精神障碍症状之间的因果关系，并做到不依赖中心性指标而识别出因果意义上的驱动性症状。如 Mcnaly 等(2017)利用贝叶斯网络探究 PTSD 症状间关系时，识别出对创伤相关提示物的生理反应和心理反应，可能是PTSD中的驱动性症状(如图8)。

![](images/91106929aff45a171254222725f2c2053eb17c59c8116b792f10b79e20665aca.jpg)  
图8.PTSD的贝叶斯网络(DAG)。此网络中，17个节点代表17个DSM-IVPTSD症状(同图3)，边的厚度表示此边所代表预测方向的概率大小；位置越靠上的节点可认为越具有驱动力。(资料来源：McNallyetal.,2017)

但是，贝叶斯网络对横断面数据中的因果关系的统计推断力还有待进一步验证。首先，贝叶斯网络需要满足一定的假设条件(Pearl,2010)。一是网络中应纳入全部的相关因素。也就是说，如果贝叶斯网络中遗漏掉其他会对网络中变量间因果关系产生较大影响的变量(如未被测量到的症状)，症状间可疑的相关关系可能会被错误地推断为因果关系；二是必须满足因果推断的马尔科夫假设4。而对于复杂的精神障碍，这些假设并不那么容易满足(Bringmann et al.,2019)。其次，贝叶斯因果推论的结果(DAG 网络)仅能够推断出变量间的单向关系，不允许反馈环路的存在。而精神障碍的症状之间非常有可能存在相互影响的双向关系，从而相互抵消，在贝叶斯网络中表现出无直接因果关系或较微弱的因果关系(如图8中对创伤相关提示物的生理反应通过一条较细的边指向惊跳反应(startle),很可能是因为这两个症状之间存在相互的因果关系)。最后，网络结果在实际的计算过程中，不太容易确定唯一的最优贝叶斯网络，有时结果会出现很多都可行的DAG模型。

因此，鉴于贝叶斯网络的这些局限，我们对于其因果推断结果应当保持谨慎的态度。我们在基于贝叶斯网络的结果做任何推论时，应至少在确保贝叶斯网络中没有遗漏任何可能导致虚假相关的重要变量、以及多次计算均可以得到同样的稳定的贝叶斯网络模型的前提下。而面对贝叶斯推断结果中较微弱的因果关系(以较细的有向边表示)时，除了认为反映了症状间因果关联可能较小，也需要考虑是否存在可能部分抵消的双向因果关系。

# 4.心理病理学网络理论与方法的应用于价值

# 4.1心理病理学网络理论与方法的应用

心理病理学网络理论与方法的发展推动了一系列相关研究的开展。据 Robinaugh 等(2020)的系统综述，从 2008年到 2018年十年期间，已发表363篇心理病理学网络理论与方法相关文章。其中理论研究98篇，方法研究61篇，实证研究 204篇。心理病理学网络理论被研究者广泛应用于对 MDD(Belvederi Murriet al.,2018; Van Borkulo et al.,2015)、PTSD(McNally et al.,2015)、焦虑障碍(Heeren & McNally,2016)、进食障碍(Smith et al.,2018)、睡眠障碍(Blake et al.,2018)等多种心身疾病的症状表现、网络结构差异和共病机制的探讨中，以及多种精神障碍之间关系(Cao etal.,2020)的考查。以创伤后的常见精神障碍为例，多项PTSD 网络分析研究均发现创伤相关遗忘(amnesia)在 PTSD 网络中具有最低的中心性，与其他 PTSD 症状连接程度最低，表明创伤相关遗忘可能是PTSD 的边缘症状(Benfer et al.,2018;McNally et al.,2015,2017;Papini et al.,2020)；Cao 等(2019)对比地震后青少年PTSD 网络的性别差异发现，女性的PTSD 网络比男性的网络连接性更强，在核心症状上也有所不同；Afzali等(2017)通过构建 MDD和PTSD的共病网络，识别出了对二者共病起到关键作用的桥症状，包括睡眠问题、兴趣缺失和易激惹等重叠症状，以及闪回、自责感和精神运动迟滞等非重叠症状；Cao 等(2020)通过估计包含 PTSD、MDD 和广泛性焦虑等内化问题，以及攻击行为和违纪行为的外化问题的一系列创伤后常见心理问题的网络，在分别控制住每一种疾病考查剩余网络的结构后，发现控制 MDD 对于网络连接性(尤其是内化与外化问题之间的连接)的影响最大，表明MDD可能是创伤后多种心理问题并发的关键影响因素。

# 4.2心理病理学网络理论与方法的价值

心理病理学网络理论与方法对于精神障碍的全新刻画，具有重大的理论与临床意义。首先，心理病理学网络理论否认疾病实体的存在，将精神障碍刻画为由相互作用的症状组成的动态因果系统这一思想，回应了传统DSM-ICD 分类诊断系统的一个主要问题：此分类标准下确定的任何精神障碍均未找到其对应疾病实体。其次，心理病理学网络理论与方法改进了对共病机制的研究方式。传统分类诊断系统为使分类更清晰，在剔除各疾病的共享症状、保留各自独特症状方面做了很多尝试。这本质上相当于回避了对共病的解释，而心理问题中的共病现象已被证明是常态而非特例(Hasin &Kilcoyne,2012;Kessler etal,2005)。心理病理学网络理论与方法则通过估计共病的症状网络及识别对共病疾病起到关键桥接作用的桥症状，为共病的发生发展机制提供了有效的研究框架。另外，心理病理学网络理论也指导着不同于传统分类诊断系统下对于精神障碍的诊断和干预方式。如对于遭遇车祸后恐惧开车的患者，传统分类诊断系统指导下的临床评估者需要首先判定是潜在的特定恐惧症还是PTSD导致他恐惧和回避开车；而在网络理论下，评估者则更多需要考查还有什么其他症状被激活以及它们之间是如何关联的(Hofmann et al.,2016)。同样的，心理病理学网络理论也提示将干预的靶点从疾病层面细化到症状层面。

# 5.心理病理学网络分析方法的主要局限

# 5.1因果关系的推断

大多数心理病理学网络相关研究使用的都是来自横断面的观测数据，且基本都是在探究数据间的相关关系，虽然贝叶斯网络可以作出一定的因果推断，但如前文所说，其应用于复杂的心理病理学变量时的统计推断力仍需进一步验证。因此仅使用横断面数据可能无法真正说明症状间的因果关系(DeYoung &Krueger,2018;Forbes etal.,2017)。这一问题关键在于，心理病理学网络理论所关注的症状间的因果关系更多偏向于个体内精神障碍症状的发展机制，而使用横断面数据发现的结论都被假设性地认为可以用来描述个体内的过程(Kievit et al.,2013)。但事实上，仅涉及一次测量的横断面数据只能反映个体间的变量关系，无法提供个体内的变量关系(Bringmann,2016)。以偏头痛和睡眠之间的关系为例，来自横断面的研究可能发现偏头痛和睡眠之间有正相关(Schmitz& Skinner,1993)。我们可能据此得出结论：睡眠更多的人更易患偏头痛。然而这种正相关的出现可能仅因为患有偏头痛的人倾向于睡得更多以防止偏头痛的发生。相反，基于个体的分析，则更有可能发现二者之间的负相关：睡眠更少更可能患偏头痛。事实上，反映了统计学中的一个著名现象：辛普森悖论(Simpson's paradox,Hamaker,2012)。这一现象在症状网络中的直观表现为：症状 A、B 间形成了无向边 A—B，但没有时间的先后性，很难确定谁是因是果，即究竟是$\mathrm { A { \to } B }$ ，还是 $^ { \mathrm { B \to } }$ A(Fried etal.,2017)。因此，近年来越来越多的研究者提议使用纵向数据来构建网络模型。

# 5.2核心症状的识别

由于上述因果推断的不明确性，症状网络中依靠强度这一中心性指标识别出来的核心症状也欠缺明确的临床意义，因为它们既可能是对其他症状影响最大的关键症状，也可能是最受到其他症状影响最大的结果症状(Fried et al.,2017)。近年来研究者也确实在多种精神障碍网络中发现了识别出的核心症状的结论混杂不一(Contreras et al.,2019;Forbes et al.,2017; Ryan et al.,2019)。如 MDD症状网络研究中，精力不足、情绪低落、兴趣缺失等症状都曾被不同研究者确定为核心症状或可能的干预靶点(Fried et al.,2016;Van Borkulo et al.,2015)；同样，在 PTSD 症状网络中各节点强度中心性的一致性也很低(Forbes et al,2019)。

事实上，在使用强度等中心性指标去识别核心症状时，应当首先明确所谓的"核心"症状究竟意味着什么，指明有怎样表现的症状可以称之为“核心"症状。而大部分研究对这一点阐释不足(Brandes,2016;Schoch& Brandes,2016)。而中心性相关结论存在较大异质性的可能原因之一可能是：首先，依靠网络中心性指标识别核心节点应首先满足一定的假设条件，如：(1）节点可交换性，即网络中的节点在概念上完全等价地可以互换(Snijders,2011)。事实上，心理病理学网络中的中心性概念与测量指标直接借鉴社会网络，社会网络的节点常为独立、等价的社交实体(如友情网络以人作为节点；交易网络以公司作为节点)，很容易满足可交换性。而对于心理病理学中具有复杂关联的症状，则似乎很难满足这一条件；(2)网络结构及其中心性指标能够揭示一定因果关系，必须保证所有具有相关因果关系的变量均应被网络纳入，即网络中不会遗漏任何重要的因果变量。然而对于复杂的某种精神障碍，找到其全部相关的因果因素都很难做到，更不用说将其全部纳入到相应网络中(Spiler etal.,2020)。另外，目前主要中心性指标主要被应用于横断面网络，而横断面数据的人群异质性问题自然会导致网络结果的可重复性问题。我们也会在6.4中具体探讨这一问题。

# 5.3网络的可靠性和可重复性

尽管 Borsbo0m 等(2017)提供了一定程度的实证证据以支持网络结构在样本内和样本间的可重复性和推广性，但研究者对网络分析结果的可靠性和可重复性仍然提出较多质疑(Forbes et al.,2017;Fried et al,2016;Fried& Cramer,2017)。Forbes 等(2019)对一些研究中的心理病理学网络特征进行量化后发现，估计网络中边的存在与否、边的正负以及最强且最稳定边的权重等基本网络结构特征，都存在可重复性低的问题。如MDD症状网络中边估计的结果有 $4 3 . 4 \%$ 不可重复(即一个网络中的边在另一个网络中不存在或者符号相反)；而 PTSD 症状网络则更是有 $6 3 . 8 \%$ 的边估计不一致(Forbes et al.,2019)。

网络的可靠性和可重复性问题的出现可能有以下两方面原因。一方面，由于目前心理病理学网络主要使用数据驱动的探索性网络分析方法，除方法的影响外，网络结构也在很大程度上依赖于数据和样本本身。前人研究表明，网络中节点的选取和测量对于网络结构的估计(Halquist etal.,2019)与解释(Forbes etal.,2017)起着至关重要的作用。如Hoffman 等(2018)在估计酒精使用障碍(alcohol use disorder,AUD)的症状网络时，发现仅仅控制单个症状的划界分高低不同，得到的网络便有显著的结构差异。Borsboom 等(2018)也发现同一网络结构无法同时适用于普通人群样本和病人样本。

另一方面，目前在方法学上欠缺跨研究的网络比较和网络整合的有效方法，造成研究结果较为分散。目前网络的比较主要借助R语言中 NetworkComparisonTest程序包(van Borkulo et al.,2017)，在网络结构、全局强度和边权重的差异上进行比较。但由于这些比较只能在2个网络间进行，无法比较跨研究的多个网络间的差异，导致各研究结果的差异的效应量不可知。而对于心理病理学网络分析结果的整合，目前仅有一些综述类文章(如 Contreras et al.,2019; McNaly et al.,2015; Robinaugh et al.,2020等)，尚无针对心理病理学网络理论与方法研究质量进行量化的元分析。

# 6.心理病理学网络分析方法的展望

# 6.1纵向数据的使用

心理病理学网络理论的核心思想主要是视症状之间的因果关系为疾病的组成部分。如前文所言，横断面数据在探究因果关系上具有很大的局限性。使用包含更多因果信息的数据，如纵向追踪数据或由经验取样法采集的密集型时序数据，可以更好地说明变量间的因果关系，以及发现横断面数据无法揭示的变量间关系(Forbes et al.,2017; Robinaugh et al.,2020)。

事实上，自心理病理学网络理论提出起，Borsboom 和 Cramer(2013)便已开始提倡研究者收集密集型时序数据，并利用心理病理学网络模型对时序数据进行分析。目前已有可将GGM运用于时序数据和面板数据的图形向量自回归分析(vector autoregression,VAR,Borsboom& Cramer,2013)方法，可以使用来自个体的密集型时序数据，同时估计出以回归系数为边的纵向网络(temporal network)和以回归残差间的偏相关为边的横向网络(contemporaneous network)。当使用包含至少三次测量的面板数据(即至少有三个测量时间点的多个个体的时序数据)时，除纵向网络和横向网络外，还可估计出以多个个体变量均值间的偏相关为边的个体间网络 (between-subjects network,Epskamp,2020; Epskamp et al.,2018b)。在动态纵向网络中，可以考查症状间(包括自身)前一时间点对后一时间点的预测作用，从而可以更深入地了解精神障碍的发展机制。如 Bringmann 等(2015)在使用 VAR 方法对贝克抑郁量表(Beck Depression Inventory,BDI-II)测量的 21个 MDD 症状动态纵向网络模型中，发现快感缺失症状具有对其他症状最强的预测作用，表明快感缺失可能对于维持 MDD动态网络具有相对重要的作用；而悲伤和兴趣缺失症状可以被包括快感缺失在内的多个症状预测，但几乎不能预测其他症状，反映出悲伤和兴趣缺失在MDD 的动态过程中可能更多是被动的反应性症状。

然而，对于纵向数据的使用和动态网络模型的建立，仍存在一定挑战。比如时间窗的问题：症状间的相互影响可能发生于不同的时间窗。如食欲减退可能在几周后才会观察到体重下降；睡眠问题可能以天为单位发生变化；而情绪状态则可能在几分钟甚至几秒钟内发生改变(如恐惧导致回避行为)。所以如何测量并关联这些不同时间尺度属性的症状，也是未来研究需要关注的主题(Boker et al.,2009;Robinaugh etal., 2020)。

# 6.2网络特征的拓展

随着新兴网络的发展，网络特征也已相应从最基本的节点强度、连接性拓展至节点预测性、网络分簇性等多种指标。然而，这些指标都只反映了症状的关联信息，未将临床严重程度的信息考虑在内，局限了网络结果的临床意义。如在临床严重程度不同的群体中考查网络的连接性时，临床严重程度越高的网络连接性表现不一：分别出现越紧密(Heeren &McNally,2018; Santos et al.,2017)，无差别(Levinson etal,2018)和越稀疏(Southward&Cheavens,2018)等情况。这种差异很大程度上来源于使用网络中变量的函数(如反映总体严重程度的症状得分总和)对数据进行划分，从而为网络结果引入了选择偏差(Berkson's bias,De Ron et al., 2019)。

这一统计学难题尚无较好的解决办法。但值得思考的是，在心理病理学网络分析方法中，症状严重程度作为症状本身自带的属性，似乎只发挥了估计症状之间关联性的作用，并不直接属于网络特征之一，也未真正参与到网络结果的讨论中。因此，如果能够拓展出可以结合症状严重程度的指标作为网络特征，那么网络中临床严重程度的影响便成为了网络的内在属性，而不再作为网络外部变量的干扰因素，就可以在一定程度上减小选择偏差出现的可能性。同时，结合症状严重程度，也为心理病理学网络分析方法增加了更多临床方面的量化信息，使得网络分析的结果更具临床意义。

# 6.3与现有理论的结合

由于目前心理病理学网络模型仍是以数据驱动的探索性分析方法，分析结果可能只适用于特定样本，难以推广至其他样本。未来可以发展由假设驱动的验证性网络分析方法(Fried&Cramer,2017)，以更好地考查网络模型在不同样本中的适用性。或至少在构建网络时考虑一些已经过验证的理论，以此作为网络结构的某些约束条件。如将心理病理学网络理论与经典潜变量理论相结合的潜变量网络模型(Epskamp etal.,2017)就是很好的尝试。

可以说，潜变量理论与心理病理学网络理论的结合有一定的理论基础和历史根源。一方面，虽然心理病理学网络模型通过对症状之间相关性的考查，克服了传统潜变量模型“局部独立性"的弊端；但不可否认的是，潜变量模型仍然拥有网络分析模型难以替代的优势(CAIet al.,2020)：潜变量模型(特别是广义结构方程模型)纳入了对测量误差的考查和控制(Borsboom et al.,2003)，有效规避了心理测量精确性的问题;而且潜变量模型也提供了有效的验证性分析的框架。另一方面，虽然潜变量模型和网络模型在理论上基于不同的对精神障碍的构念假设，但实际上两模型之间不仅具有统计意义上的等价性(van Bork et al.,2019)，也具有一定的互补性，并不是互斥的关系(Epskamp&Fried,2018)。同时，也有大量证据表明(Birkeland et al.,2020;Fried& Cramer,2017; Moshier et al.,2018)，对于PTSD、MDD、焦虑障碍等复杂性精神障碍，潜在的症状维度和症状维度间相互影响的网络结构可能同时存在。针对这些精神障碍的潜在症状维度网络模型则能够巧妙地将这两种视角结合，使其相辅相成地全面刻画精神障碍的心理病理特性(Epskamp et al., 2017)。

Epskamp 等(2017)对潜变量模型与网络模型的结合进行了初步探索，开发了可以用潜变量作为节点的网络模型。Li等(2020)利用此模型，对PTSD进行了症状维度之间网络结构的探索(见图9)，发现闯入和回避这两个症状维度间存在最强连接；在外化行为和负性情绪维度之间以及焦虑性唤起和精神痛苦性唤起维度之间也存在较强连接。这一结果提示着在 PTSD 的干预中需要更加关注特定症状维度之间(例如闯入与回避症状)的关联。这些探索性的发现也启发着我们，除了关注于症状水平上的动态交互作用，未来研究中可以继续发展完善这一结合潜变量模型优势的网络模型，将心理病理学网络理论拓展到症状维度水平上。

![](images/949e0cff9f1d33695404d5f84074b02968ac18d604157981ef549ac0db9ec5ea.jpg)

图9.PTSD 潜变量网络。方块节点B1-E6分别代表20个DSM-5PTSD症状，圆圈节点1-7代表7个PTSD潜在维度。（资料来源：Li等(2020)

# 6.4人群异质性的区分

目前 DSM-ICD诊断系统基于症状组合或划界分来确定是否患上精神障碍的诊断方式，导致具有相同诊断的个体之间，可能有极其不同的症状表现(如Fried & Nesse,2015; Galatzer-levy& Bryant,2013; Olbertet al.,2014)。采用一些结构方程模型(Structural equation modeling,SEM)的方法能够在一定程度上解决人群异质性的问题：潜在类别分析(Latent Class Analysis,LCA)、混合增长模型(Growth Mixture Model, GMM)等混合模型可以基于不同的症状剖面或不同发展轨迹对人群进行分类；同一类别的个体具有相似的症状表现，对特定治疗有相似的反应，或有相似的生物标志物剖面(Ten Have et al.,2016;Wardenaar et al.,2015)。心理病理学网络模型同样可以反映这一问题。如Fried 和 Cramer(2017)在文中所举的例子：在由 600 名具有相同诊断的病人组成的样本中，由于诊断的异质性，其中一半可能仅在症状簇A内有明显关联(见图 10左图)，另一半仅在症状簇B内有明显关联(见图10中图)，然而两个子样本合起来的平均网络则显示无法反映其各自真实模型，甚至可能据此得出毫无意义的临床结论(见图10 右图)。这一方面启示着我们应该谨慎将群体的心理病理学横断面网络结果推论到个体(如针对个体干预时以某中心性高的症状为干预靶点)。另一方面也提示着我们，本身聚焦于症状水平的心理病理学网络模型，若能够发展出可区分人群异质性的网络混合模型，对各精神障碍症状表现的个体差异的考查和网络结果的可靠性的验证可以起到关键作用(Fried& Cramer,2017)。目前，网络混合模型的一大挑战是由于估计参数的增加需要更大的样本量来确保网络的稳定性(Epskamp et al.,2018b)。

![](images/da49c1c79b84d18661246924870237ba35cbf0d0b658dbe171261b67008b413c.jpg)  
图10.左图、中图分别为仅在A、B症状簇内有连接的子样本网络；右图为合并两样本后的网络。（资料来源：根据Fried和Cramer(2017)绘制）

# 6.5研究结果的整合

除发展用以区分个体差异的网络混合模型外，对跨样本研究结果的整合也是未来重要的发展方向。已有一些研究借助跨样本的方法考查了网络结果的稳定性、相似性与可重复性。如Forbes 等(2019)在2个大型社区样本中考查了MDD 和焦虑症状网络的可重复性。Fried 等(2018)针对 PTSD 症状网络，在四个具有不同文化背景、创伤类型和严重程度的样本中验证了网络结果(包括症状剖面、网络结构和症状中心性)间较高的相似性。也有研究在针对同一精神障碍使用的不同测量工具所得的网络结果之间发现了较高的相似性(Moshier etal.,2018)。但这些研究所用的方法大多都是基于一般网络估计方法，对单个样本网络分别进行估计、比较后，将多个样本合并再次进行网络估计，比较的样本数量与指标有限。未来应在方法学上着重发展可以比较多个网络差异的方法，并增加更多比较的指标，对各网络结果间的差异进行更为细致的刻画。同时应开发针对跨样本网络结果整合与比较的特定方法(如估计相同疾病的样本合并网络或者不同疾病的症状合并网络的方法 Robinaugh et al.,2020)，或发展可定量整合各研究网络结果的元分析方法。为实现这样的整合方法，需要倡议研究者共享网络分析的代码与相关数据矩阵(Contreras et al.,2019;Epskamp,Rhemtulla, et al., 2O17; Robinaugh et al., 2020)。

# 7.总结

本文是第一篇详细介绍心理病理学理论与方法的中文文章，概述并总结了心理病理学网络理论内容、对应的网络分析方法、理论与方法的应用及价值、目前方法的主要局限与未来可能的发展方向。心理病理学网络理论为我们提供了看待精神障碍的崭新视角，将我们对于精神障碍的认识细化到症状水平，为我们探索症状间的动态关联开辟了新的途径。但目前此网络方法仍面临不小的挑战，如网络结果的可靠性与可重复性问题。未来在完善网络理论、积累实证研究证据的同时，也应更多致力于方法上的发展，如潜变量网络模型的进一步完善、网络混合模型的建立以及针对网络方法的元分析方法的开发等。

# 参考文献

蔡玉清,董书阳,袁帅,胡传鹏.(2020).变量间的网络分析模型及其应用.心理科学进展,28(1),178-190.CAI,Y.,DOG,S.,UA,S.,&HU,C.-.().Networaalysisaditsacatios ishlogAdvacs inolicalScience,28(1),178-190. https://doi.org/10.3724/sp.j.1042.2020.00178

Adam,D.(2013).Mental health:Onthespectrum.Nature,496,416-418.https://oiorg/10.1097/0006324-19290500-00003   
Afzali,M.Huderand,,sson,arrager,Nils,K.de,T.().etwokapproachthebi between postraumatic stressdisorder and majordepressive disorder: The role of overlapping symptoms.Journalof Affective Disorders,208(August 2016),490 -496. https://doi.org/10.1016/j.jad.2016.10.037   
Belvederi Murr,.,Amore,M,Resino,M.,&Alexopoulos,G.S.(018).Thesymptomnetwork structureofdepressveptos in late-life: Results fromaEuropean population study.Molecular Psychiatry. htps://oi.org/10.1038/s41380-018-0232-0   
Benfer,N.,Bardeen,J.RCero,I,Kramer,L.B.,Witeman,S.E,ogers,T.A,lverstein,.W.,&Weathers,F.W.(18). Network models of postraumatic stresssymptoms acrosstrauma types. Journal of Anxiety Disorders，58(June),70 -77. https://doi.org/10.1016/j.janxdis.2018.07.004   
Birkeland,M.S.reene,T.,&Spiler,T.R.().Tenetworkapproachtoposraumaticstress disorder:aystematicreview. European Journal of Psychotraumatology,11(1). https://doi.org/10.1080/20008198.2019.1700614   
Blake,M.J.,der,JA,&ll,N.(8).hssderlingeocatwoiaety inadolescence:Implications for behavioral sleep interventions.Clinical Psychology Review，63，25-40. https://doi.0rg/10.1016/j.cpr.2018.05.006   
Boker,S.M.,olearP.C..,&seoade,J.).ustrainiialVrabiityIivialereceia and Dynamics Over Multiple Time Scales.Psychology and Aging,24(4),858 -862. htps://oi.org/10.1037/a0017912   
Borsboom,D.(2008).PsychometricPerspectivesonDiagnosticSystems.Journalof ClinicalPsychology，64(9)089-108. https://doi.0rg/10.1002/jclp.20503   
Borsboom,D.(017).Anetworktheryofmentaldisorders.WorldPsyhiatry6(1),5-3.hps:/oig/10./wps.375   
Borsboom,D.,&Cramer,A.O.J.(Ol3).Network analysis:Anintegrativeapproach tthestructureofpsychopathology.Anual Review of Clinical Psychology,9(1),91-121. https:/doi.org/10.1146/annurev-clinpsy-050212-185608   
Borsboom,D,Fried,E.L,Epskamp,S.,Waldorp,L.JvaBorkuloC.D.van derMaas,H.LJ,&Cramer,A.O.J.().False alarm?Acomprehensive reanalysis of“evidencethat psychopathology symptom networks have limited replicability”by Forbes，Wright，Markon， and Krueger(2017). Journal of Abnormal Psychology，126(7)， 989-999. https://doi.org/10.1037/abn0000306   
Borsboom,D.,Mellenbergh,G.J,&VanHeerden,J.（2O03).Theheoretical StatusofLatentVariables.PsychologicalReview, 110(2),203 - 219. https://doi.0rg/10.1037/0033-295X.110.2.203   
Borsboom,D.,obinaugh,D.J,emtull,.,&Caer,A.O.J.(8).Robustnsandreplicabilityfpschopatholgetorks. World Psychiatry,17(2),143-144. https://doi.org/10.1002/wps.20515   
Brandes, U. (2016). Network positions. Methodological Innovations, 9, 205979911663065. https://doi.0rg/10.1177/2059799116630650   
Bringmann，L.(2016).Dynamical networks in psychology:More thana pretty picture.Thesis，October，1-193. https://doi.0rg/10.13140/RG.2.2.28223.10404   
Bringman,L.F.,Lemmens,L.H.J..,Huibers,M.J.H,Borsboo,D,&Tuerlinckx,F.(5).Revealingthe dynamicntwork structureoftheBeckDepressionInventory-II.PsychologicalMedicine，45(04)，747 757. https://doi.0rg/10.1017/S0033291714001809   
Bringman,LuraF,Epskamp,S.,Krause,R.W,choch,D.,Wichers,M.,Wigman,J.T.W,&nippe,E.(2O9).WhatDoCtri Measures Measure in Psychological Networks ? Journal of Abnormal Psychology,128(8),892- 903.   
CAI,Y.,DOG,S.A,S.,&HU,C-. ).Networkaalysisaditsaatiosisyholog.Advances inlical Science,28(1),178. htps://doi.0rg/10.3724/sp.j.1042.2020.00178   
Cao,X.,Wang,LCaoC.,Fang,R,Chen,C,HallB.J,&Eai,JD.(19).Sex dierencesnglobalandlocalcoiityof adolescent postraumatic stress disordersymptoms.JouralofChildPsychologyand Psychiatryand Alled Disciplines,60(2), 216 - 224. htps://doi.org/10.1111/jcpp.12963   
Cao,X.,WangL,Cao,CFg,R.e,CHal,.J,&i,J.().eictingtheassciatisbtweedito of psychopathology in trauma-exposed adolescents.European Child and Adolescent Psychiatry，29(6)，827 - 837. https://doi.0rg/10.1007/s00787-019-01400-x   
Chen,J.,&Chen,Z.(oo8).Extendedayesianformationriteriaforodelelectiowithlarge modelspaces.iometrika95(3), 759 - 771. https://doi.org/10.1093/biomet/asn034   
Contreras,A.,Neto,1.Valiente,C,spiosa,R.,&Vazquez,C. (O9).estudyofpsyhopathologyfrothenetworkalyis perspective: A systematic review. In Psychotherapy and Psychosomatics (Vol. 88， Issue 2， pp.71 - 83). https://doi.0rg/10.1159/000497425   
Cramer, AngéLiqueO.J.,&Borsboo,D.(015).ProblesAtractProblems: ANetworkerspectiveonMentalDisorders.Emerging Trends in the Social and Behavioral Sciences.,4(2),191 -193.   
Cramer,AngéliqueO.J.,VanBorkulo,C.D.,GiltayE.J.,VanDer Maas,H.L.J.Kendler,K.S.,Scheffer,M.,&Borsboom,D. (2016).Majordepresionasacomplexdynamicsystem.PLoSONE，11(12)，1-21. https://doi.org/10.1371/journal.pone.0167490   
DeRon,J.,Fried,E.,&Epsamp,S.(19).syholgicaletwrkinlinicalpopuatios:Ivestigatingthoseqcsof Berkson’s bias.Psychological Medicine,1-9. https://doi.org/10.1017/S0033291719003209   
DeYoung,C.G.,& Krueger,R.F.(2018).Understanding Psychopathology: Cyberneticsand Psychologyonthe Boundarybetween Order and Chaos. Psychological Inquiry,29(3),165 -174. https://doi.org/10.1080/1047840X.2018.1513690   
Epskamp，S.(2020).Psychometric network models from time-seriesand panel data.Psychometrika，85(1)，206-231. https://doi.0rg/10.1007/s11336-020-09697-3   
Epskamp,S.orsboo,D,&ried,E..(17).Estimating pschologicaletworsandteiruracy:AtutoralpaerBvior Research Methods,50(1),195 - 212. https://doi.0rg/10.3758/s13428-017-0862-1   
Epskamp, S., Cramer, A. O. J., Waldorp,L. J., Schmittmann, V. D.,& Borsboom, D. (2012). qgraph $\because$ Network Visualizations of Relationships in Psychometric Data. Journal of Statistical Sofware,48(4). htps://oi.org/10.1863/jss.v048.i04   
Epskamp,S.&Fied,E.(l).Autorialoreglaedpartialoeationetworks.Pycolgical Metd,(4),-64. https://doi.0rg/10.1037/met0000167   
Epskamp,S.,Rhemtull,M.,&Borsboom,D. (O7). GeneralizedNetworksyhometrics: CombiningNetworkandLatent Variable Models.Psychometrika,82(4),904 -927. https://doi.0rg/10.1007/s11336-017-9557-x   
Epskamp,S.，Waldorp,L.J.,Motus,R.，&Borsboom,D.(2O18).DiscoveringPsychological Dynamicsin Time-Series Data. Multivariate Behavioral Research,53(4),453- 480. htps://doi.org/10.1080/00273171.2018.1454823   
Forbes,M.K. Wright,A.G.C.Markon,K.E.,& Krueger,R.F.(017).Evidence thatpsychopathologysymptom networks have limited replicability. Journal of Abnormal Psychology,126(7),969 -988. https:/doi.org/10.1037/abn000276   
Forbes,M.K.，Wright,A.G.C.，Markon,K.E.，& Krueger,R.F.(2019).QuantifyingtheReliabilityandReplicabilityof Psychopathology Network Characteristics. In Multivariate Behavioral Research. https://doi.0rg/10.1080/00273171.2019.1616526   
Fried,E.I,&Cramer,A.O.J. (2O17).MovingForward: ChallengesandDirectionsforsychopathologicalNetworkTheoryand Methodology.Perspectives onPsychological Science,12(6),999 -1020. htps://oi.org/10.1177/1745691617705892   
Fried,E.I,do,.ic,.otai,s-nijH.cg,C..gead,oes A.B.S.,&Karstoft,K.I. (2018).Replicabilityand Generalizabilityof Postraumatic Stress Disorder (PTSD)Networks: A Cross-Cultural Multisite Study of PTSD Symptoms in Four Trauma Patient Samples.Clinical Psychological Science,6(3), 335 - 351. htps://doi.org/10.1177/2167702617745092   
Fried,E.1.,Epsamp,S.,e,R..uerlickxF.,&Borsboo,D.(6).Waare“go”depressionsmptomsCoring thecentralityofDSMandnon-DSMsymptoms of depressoninanetworkanalysis.JournalofAfectiveDisorders,189,314- 320. https://doi.org/10.1016/j.jad.2015.09.005   
Fried,E.I,&sse,..(5).epressisotosistetsoe:Aisigatofestotesi \*D study. Journal of Affective Disorders,172, 96 - 102. htps://doi.org/10.1016/j.jad.2014.10.010   
Fried,E.IBokloCa.JloLhvs.A,orbo,().easorders ofproblems:a review of recent insights. Social Psychiatryand Psychiatric Epidemiology， 52(1)，1-10. https://doi.0rg/10.1007/s00127-016-1319-z   
Friedman,J.Hastie,&hrani,R.().Sparseivrseovraneetimatoniteapicallassostatistics,9(), 432 - 441. htps://doi.org/10.1093/biostatistics/kxm045   
Galatzer-levy，I.R.，& Bryant，R.A.(2013). 636，12O WaystoHave PostraumaticStressDisorder. https://doi.0rg/10.1177/1745691613504115   
Golino,H.F.，&Epsamp,S.(2O17).Exploratory graph analysis: Anewapproach for estimatingthenumberof dimensions in psychological research. PLoS ONE,12(6),1- 27. htps://oi.org/10.1371/journal.pone.0174035   
Guloksuz,S.,Pries,L.K.,& Van Os,J.(2O17).Aplicationof network methods forunderstanding mental disorders: Pitfalsand promise. Psychological Medicine,47(16),2743 -2752. https:/doi.org/10.1017/S0033291717001350   
Halquist,M.N. Wright,A.G.C.C,& Molenar,P.C.M.M. (2019).Problems withCentrality Measures in Psychopathology Symptom Networks: Why Network Psychometrics Cannot Escape Psychometric Theory. Multivariate Behavioral Research, January,1 - 25. htps://doi.0rg/10.1080/00273171.2019.1640103   
Hamaker,E.L.(2Ol2).Whyresearchersshouldthink“within-person”:Aparadigmaticrationale.Handbookof Research Methods for Studying Daily Life,October,43 - 61.   
Hasin,D.,&Kilcoye,B.(O12).Comorbidityof psychiatricandsubstanceusedisordersintheUnited States: Currentisuesand findings fromtheNESARC.Current OpinoninPsychiatry,25(3),165-171.htps://oi.org/10.1097/YCO.0b013e3283523dcc   
Haslbeck,J.M.B.,&Waldorp,L.J.(2O18).Howwelldonetworkmodelspredictobservations?Ontheimportanceofpredictability in network models.Behavior Research Methods,50(2),853-861. https:/doi.org/10.3758/s13428-017-0910-x   
Heeren,A.&McNally,R.J. (2O16).Acalforcomplexityinthestudyofsocialanxietydisorder.Commentary:Theaetiologyand maintenanceof socialanxietydisorder:Asynthesisofcomplementarytheoretical modelsand formulationofanew integrated model.Frontiers in Psychology,7(DEC),1-3. https://doi.org/10.3389/fpsyg.2016.01963   
Heren,A.,&McNally,R.J.(O18).SocialAnxietyDisorderasaDenselyInterconnectedNetworkofFearandAvoidanceforSocial Situations. Cognitive Therapyand Research,42(1),103-113.htps://doi.org/10.1007/s10608-017-9876-3   
Hoffman,M.einley,D.Tru,T.J,&Ser,K.J(18).CriteriaDefiitiosndNetworkRelations:TemportanceofCiteio Thresholds. Clinical Psychological Science,6(4), 506 - 516. https://doi.org/10.1177/2167702617747657   
Hofmann,S.G.,Curtiss,J.，& Mcnally,R.J. (2016).A Complex Network Perspectiveon Clinical Science.Perspectiveson Psychological Science,11(5),597 - 605. https://doi.org/10.117/1745691616639283   
Insel,T.,Cutbert,.Grey,,Hissen,,ine,D.Quin,K,slo,C,Wag,P.().Rsearchoaia (RDoC): Towarda New Classification Framework for Research on Mental Disorders.American Journalof Psychiatry Online, July,748 - 751. https://doi.org/10.1176/appi.ajp.2010.09091379   
Kievit,R.A.Frankenhuis,W.E,Waldorp,LJ,&Borsboom,D.(3).Simpso’sparadoinpychologicasience:Aractical guide.Frontiers in Psychology,4,1-14. https://doi.org/10.3389/fpsyg.2013.00513   
Lauritzen, S.L. (1996). Graphical models (Vol. 17). Clarendon Press.   
Levinson,C.rosf,.Cla,IsaCesodebgh.ger.KieE.KenC J. W.,Menati,A.,Lim,M.H.,&Fernandez,K.C. (2O18).Social anxietyandeating disordercomorbidityand underlying vulnerabilities:Usingnetworkanalysis toconceptualizeomorbidity.InternationalJounalofEatingDisorders,51(7),693 709. https://doi.org/10.1002/eat.22890

Li,G.,Wang,LCCFang,R,u,P.uoS,Hal.J,Eai.)AexploatiooheD-5ptic stressdisordersymptomlatentvariablenetwork.EuropeanJournalofPsychotraumatology， $\boldsymbol { { I I } } ( 1 )$ . https://doi.0rg/10.1080/20008198.2020.1759279

McNaly，R.J. (2O16).Can network analysis transformpsychopathology? Behaviour Researchand Therapy，86,95-104. https://doi.0rg/10.1016/j.brat.2016.06.006   
McNally,R.J,Heren,A,&Robinaugh,D.J. (2Ol7).ABayesiannetwork analysisof postraumatic stressdisordersytoms in adultsreportingchildhoodsexualabuse.European Journal ofPsychotraumatology， 8(sup3)，1341276. https://doi.0rg/10.1080/20008198.2017.1341276   
McNaly,R.J.,Robinaugh,D.JWu,G.W.Y.,Wang,L,Deseno,M.K.,&Borsboom,D.(2O15).Mentaldisordersascausal systems:A network approach to postraumaticstressdisorder. Clinical Psychological Science，3(6)，836 -849. https://doi.0rg/10.1177/2167702614553230   
Moshier,S.JBovi,.N.GWiscoB.E,ielK.S.,DJlon.WeatrsF.uP.a T.M.,& Marx,B.P.(018).Examinationof postraumatic stressdisorder symptom networks using clincian-rated and patientrated data.Journal of Abnormal Psychology,127(6), 541 -547. https://doi.org/10.1037/abn0000368   
Olbert,C.M,Gala,G.J,&pler,L.A.(4).Quantifingeterogeityrbutabletolytheticagosicitea:teial framework andempiricalaplication.JouralofAbnormal Psychology23(2),452-462.hps://oiorg/10.1037/a006068   
Opsahl,T.,AgssF,&votz,J().detralityiiedetwos:aliegedrtestal Networks,32(3),245 - 251. htps://doi.org/10.1016/j.socnet.2010.03.006   
Papini,S.,Rubin,.elch.J,its,J.AJ,&n,D.A.().PretreatmentPotrumaticStressisorderymtotwok Metrics Predict the Strength of the Association Between Node Change and Network Change During Treatment. Journal of Traumatic Stress,33(1), 64 - 71. https://doi.org/10.1002/jts.22379   
Pearl, J. (2oo). Causality: Models, Reasoning,and Inference.   
Pearl,Judea.(2O1O).The Mathematics of Causal Relations From Associational to Causal Analysis $\because$ Distinctions. In Causality and Psychopathology: Finding the Determinants of Disorders and their Cures (Issue September, pp.1-17).   
Robinaugh,D.J.,Hoekstra,R.H.A,Toner,E.R,&Borsboom,D.(O2).Tenetworkapproachtosyhopathologyrviewof theliterature2008-2018 and anagenda forfutureresearch.Psychological Medicine，50(3)，353- 366. https://doi.0rg/10.1017/S0033291719003404   
Robinaugh,D.J.,LeBlanc,N.J,Vuletich,H.A,&McNalyR.J. (2O14).Ntworkanalysisof persistentcomplexbereavment disorderinconjugallybereavedadults.JournalofAbnormalPsychology，123(3)， 510 522. https://doi.0rg/10.1037/abn0000002   
Robinaugh,D.J,iler,.J,&NallR.J.(6).Ideniingighlyuenialnodesinecomplicatedgriefetwokual of Abnormal Psychology，125(6) : 747- 757. https://doi.org/10.1037/abn0000181   
Ronald C.Kessler,PhD;WaiTat Chiu,AM;Olga Demler,MA,MS;Ellen E.Walters,M.(2005).Prevalence,Severityand Comorbidity of 12-Month DSM-IV Disorders in the National Comorbidity Survey Replication.62(June).   
Ryan,O.,Bringmann,L.F.,& Schurman,N.K. (2019).The Challenge of GeneratingCausal HypothesesUsing Network Models. PsyArXiv,1 - 30.   
Santos,H.,Fried,E.safu-Adjei,J,&eaeRuiz,R.(7).tworsructreofperataldepreivesmtolati: Relationship tostressand reproductive biomarkers.Research in Nursing and Health，40(3)，218 - 228. https://doi.org/10.1002/nur.21784   
Schmittmann,V.D.,Cramer,A.O.J.,Waldorp,L.J.,Epskamp,S.,Kievit,R.A.,&Borsboom,D.(2013).Deconstructingthe construct:A network perspective on psychological phenomena. New Ideas in Psychology，31(1)，43- 53. https://doi.org/10.1016/j.newideapsych.2011.02.007   
Schmitz,B.,&iner,E.(993).erceivedotrolfort,ndcademiceformance:teridivdual,traindiidald Multivariate Time-SeriesAnalyses. Journal of Personalityand SocialPsychology， 64(6)，101o -1028. https://doi.0rg/10.1037/0022-3514.64.6.1010   
Schoch,D.,&rands,U.(16).Re-onceptualigcentralityinocialetworks.EuropeanoualofAppliedathematics(6), 971 - 985. https://doi.org/10.1017/S0956792516000401   
Smith,K.E.,Cosby,.,Woderlich,.A.FbshK.T.,ason,T.,esser.(8).etwkaalys:Aie framework forunderstanding eating disorder psychopathology.International JournalofEating Disorders,51(3),214-222. https://doi.org/10.1002/eat.22836   
Snijders，T.A.B.(201l).Statisical modelsfor social networks.Annual Review of Sociology，37，131-153. https://doi.org/10.1146/annurev.soc.012809.102709   
Southward,M.W.,&Cheavens,J.S.Ol8).IdentifyingCoreDeficitsinaDimensionalModelofBorderlinePersonalityDisoder Features: ANetworkAnalysis.Clinical Psychological Science,6(5),685-703.https://doi.org/10.1177/2167702618769560   
Spiler,T.R.,Levi,O.,Neria,Y.are-Jimenez,BBar-Hai,Y.,&LzarovA.().Onthevalidityoftheentralityothis incros-sectionaletween-subjectnetworksofpsychopatholgyBMCMdicne,18(1),-14.htps://org/10.1186/s291- 020-01740-5   
TenHave,M.,amers,F.,Wardenar,KBeekman,A,DJonge,P.,VaDorsselaerS.,uithof,,Kleijan,.,&eaaf. (2016).The identification of symptom-based subtypes of depression: Anationally representative cohort study.Journalof AffectiveDisorders,190,395-406.https://doi.org/10.1016/j.jad.2015.10.040   
vanBork,R.,emtulla,,Waldorp,L.J,Kruis,J,ezvanifar,S,&orsboo,D.(9).LatentVarbleodelsandNetwos: Statistical Equivalence and Testability.Multivariate Behavioral Research, 0(0)， 1 24. https://doi.0rg/10.1080/00273171.2019.1672515   
Van Borkulo,C.,Boschloo,L.,Borsboom,D.,Penninx,B.W.J.H.,Lourens,J.W.,&Schoevers,R.A.(215).Aociationof symptomnetwork structure with the course of longitudinal depresion. JAMA Psychiatry，72(12)，1219 -1226. https://doi.org/10.1001/jamapsychiatry.2015.2079   
vanBorkulo,Coshloo,LKskowkiJ.J,Tiochoevers,..orsbo,D,Waldop,LJ.(.cage NetworkComparisonTest.’In Manuscriptsubmitted (Isue March,p.34).htps://doi.org/10.13140/RG.2.2.29455.38569   
Wardenaar,K.Jonden,R,Conradi,H.J,&DeJonge,P.(Ol5).Symptom-specificoursetrajectoriesandtheirdeteriantsin primary care patients with Major Depressve Disorder:Evidence for two etiologicall distinct prototypes. Journal of Affective Disorders,179,38 -46. https://doi.0rg/10.1016/j.jad.2015.03.029

# Psychopathological network theory, methods and challenges

Abstract:As for the conceptualization of mental disorders,the traditional DSM-ICD classification diagnostic system and the Research Domain Criteria (RDoC)are both based on the latent variable perspective,assuming that the symptoms of mental disorders have an underlying common cause.Both views ignore the interaction between symptoms. In 2Oo8,Borsboom put forward the psychopathological network theory,a new perspective different from the categorical and dimensional views of the conceptualization of mental disorders.The core idea of the psychopathological network theory is thatthe dynamic causal relationship between symptoms constitutes the mental disorder. Based on this theory,the network methods mainly estimate the partial correlation network of symptoms using the glaso algorithm with EBIC,and examine the diferent characteristics of mental disorder symptoms using indicators such as node centrality and network connectivity.In recent years,researchers have found that there remained some challenges for the psychopathological network methods with respect to the causal relationship inference of symptoms,the identification of central symptoms,and also the reliability and replicability of the network structures. These challenges proposed possible agendas for future research on the psychopathological network theory and methods.

Keywords: psychopathology，network theory， network analysis,symptom network, central symptom, mental disorder, GGM