# 灾后中小学生创伤后应激障碍和抑郁症状的共存模式

王文超」原昊2,1伍新春1

(1北京师范大学心理学部，应用实验心理北京市重点实验室，心理学国家级实验教学示范中心（北京师范大学)，北京 100875)(深圳市坪山区同心外国语学校，深圳 518118)

摘要为揭示灾后中小学生创伤后应激障碍(PTSD)和抑郁在症状层面的共存模式，本研究分别在汶川地震和雅安地震1年后，对灾区的中小学生进行问卷调查，并基于高斯图形模型和贝叶斯爬山算法构建了二者的共存症状网络。结果发现，在DSM-IV的框架下，PTSD和抑郁的重叠症状以及情绪麻木症状在二者的共存网络中起到了桥接作用；子网络探测结果与 DSM-IV划分的症状边界不同，PTSD中的闯入性症状和回避性症状是其区别于抑郁的特异性症状，且多为闯入性症状激发回避性症状；在二者的共存模式中，多为抑郁症状激发PTSD 症状。上述结果在汶川和雅安两个样本中均得到了交叉验证，具有一定的可推广性。

关键词创伤后应激障碍 (PTSD)，抑郁，网络分析，中小学生

分类号 B844

# 1引言

精神障碍症状会给个体的日常生活带来很大负面影响，若这些症状从属于不同类别的精神障碍，即出现了共存现象，问题则会更加严重。在这种情况下，个体需要更长时程的干预和更为专业的治疗，但往往依从性较差，治疗效果不佳(Flory&Yehuda,2015)。经历创伤事件会大幅增加个体出现精神障碍症状的概率(Foa etal.,2006)；中小学生心智发展尚未成熟，在面对创伤事件时缺乏足够的应对策略，出现精神障碍症状几率较高(Tang et al.,2018)。对遭受了重大自然灾难的中小学生而言，创伤后应激障碍(Postraumatic Stress Disorder,PTSD)和抑郁是最为常见的两种精神障碍，二者的症状往往相伴而生，具有较高的共存检出率(Eksiet al.,2007)。汶川地震后，对灾区中小学生心理健康的调查发现，PTSD 和抑郁的共存检出率约在 $8 . 7 \%$ 至 $1 1 . 2 \%$ 之间(Chen et al.,2017;Fan et al 2011; Ying et al 2013)；另有研究者在雅安地震3年后对灾区5563名中小学生进行了调查，发现二者的共存检出率约为 $6 . 5 \%$ ( Tang etal.,2018)；国外的研究也发现，在海地地震2年后，灾区872名中小学生PTSD 和抑郁的共存检出率高达 $2 2 . 2 5 \%$ (Cénat & Derivois,2015)。

在 DSM 框架(The Diagnostic and Statistical Manual of Mental Disorders)下，自 DSM-II至DSM-5，兴趣减退、睡眠问题和注意力问题这三个与抑郁重叠的症状始终都在PTSD 的诊断标准之中(Flory& Yehuda,2015)。那么，二者的高共存检出率是否可归为诊断标准的重叠呢？有研究者在龙卷风灾后6个月、9个月和12个月对中学生进行追踪调查，发现三个时间点上二者的共存检出率分别为 $4 6 . 8 \%$ 、 $4 2 . 9 \%$ 和 $4 3 . 5 \%$ ；但若将重叠的三个症状剔除之后，则发现二者的共存检出率分别下降至 $3 3 . 1 \%$ 、 $3 1 . 2 \%$ 和 $3 3 . 8 \%$ (An et al.,2019)。但也有研究发现，剔除重叠症状并不会使二者的共存检出率发生显著变化。例如，EIhai等(2008)使用了两种 PTSD 诊断标准对同一批被试的数据进行了分析：一种是基于DSM-IV的诊断标准，另一种则是 Spitzer 等(2007)提出的 PTSD 诊断标准，即将 PTSD 与抑郁、广泛性焦虑障碍(Generalized anxiety disorder,GAD)重叠的症状(兴趣减退、睡眠问题、注意力问题和烦躁易怒)以及可能不是由创伤事件导致的症状(失忆)从PTSD 的诊断标准中剔除。结果发现，若使用基于DSM-IV的诊断标准，二者的共存检出率为 $3 . 7 \%$ ；若使用 Spitzer 等(2007)的标准，共存检出率则为 $3 . 5 \%$ 。一项在军人群体中开展的研究也得到了类似的结果，在DSM-IV 的标准下，二者的共存检出率为 $8 . 3 \%$ ；在 Spitzer 等(2007)的标准下，共存检出率为$8 . 2 \%$ (Grubaugh etal.,2010)。由此，Flory 和 Yehuda(2015)认为，诊断标准的重叠仅能一定程度上解释PTSD 和抑郁的共存现象,PTSD 和抑郁高共存检出率的背后仍可能存在其他原因。

除了兴趣减退、睡眠问题和注意力问题这3个重叠症状之外，PTSD 的另一些症状也被认为和抑郁存在较高的相关性，Simms 等(2002)就将这3个与抑郁重叠的症状，外加失忆、疏离、情感麻木、未来受限和烦躁易怒这5个非特异性的症状，合称为PTSD 的躁郁(dysphoria)维度。研究表明，躁郁维度很可能是PTSD 和抑郁共享的、非特异性的负性情绪和躯体化症状的表征(Gootzeit&Markon,2011)。例如，有研究者采用探索性因素分析对遭受战争创伤的军人进行研究，发现虽然PTSD 和抑郁呈现出两因子结构，但PTSD 的兴趣减退、未来受限、疏离和情感麻木这四个症状却归属于抑郁因子，而在抑郁各症状中，却没有任何症状归属于PTSD 因子(Gros et al.,2010)。Armour 和 Shevlin(2010)则利用验证性因素分析的方法对12647名被试的数据进行分析，发现在控制抑郁和GAD 后，躁郁维度在PTSD 因子上的载荷显著降低。另一项军人群体的追踪研究也表明，相较于PTSD 的其他维度，躁郁维度与抑郁跨时间点的相关性更强(Meis et al.,2011)。这些研究都表明，非特异性的 PTSD 症状同抑郁的联系更为紧密，即PTSD 的躁郁维度也能在一定程度上为二者的共存现象作出解释。

值得注意的是，上述列举的研究大都是基于共同因素假说，该假说将症状(symptom)看作是某种精神障碍(disorder)的现实表征，用潜变量来解释症状之间存在的共变模式(蔡玉清等,2020)，以PTSD 为例，被诊断为PTSD 的个体之所以会出现闯入性思维和闪回等症状，是潜在的 PTSD 这一共同原因导致的(陈琛等，2021)。精神障碍的网络理论则认为，并不需要借助潜变量来解释症状间稳定存在的共变模式，因为症状间天然存在直接的因果联系。由于精神障碍在组成、成因和影响上都是多面性的，因此需要借助一个相互作用的复杂系统来对其进行描述和表征，这个复杂系统被称为症状网络，而精神障碍就是这个症状网络的概念化表征。网络的基本组成元素即为各个症状，又称节点，节点间的联系被称为边(Borsboom,2017)。在精神障碍网络理论的指导下，研究者多采用网络分析模型来拟合数据(蔡玉清等，2020)。需要说明的是，网络分析模型与共同因素假说指导下的潜变量模型不同，它不需要满足局部独立性假设(Krueger,1999)，允许症状间存在反馈回路，承认症状间的相对重要性是有差异的，并不是“平等的”或“可互换的”，这同临床实践更为贴合(Borsboom&Cramer,2013;Cramer et al.,2010)。同时，精神障碍具有相对稳定的网络结构，即隶属于同一精神障碍下的症状间的联系要比分属于不同精神障碍下的症状间的联系更为紧密，但症状网络的边界是模糊的，精神障碍间的共存现象可被实例化为隶属于不同症状网络节点间的联系。连接两个症状网络的节点被称为桥节点，在网络中起桥接作用(Borsboom,2017)。

随着精神障碍的网络理论逐渐被学界接受，研究者开始采用网络分析模型构建PTSD 和抑郁的共存网络。Afzali 等(2017)对 909 名在一生中至少有过一次创伤经历或抑郁症发作经历的成年人进行了调查，并在此基础上依次构建了两个PTSD 和抑郁的共存网络：第一个网络囊括了PTSD 和抑郁的所有症状，第二个网络则剔除了PTSD 和抑郁重叠的4 个症状(兴趣减退、睡眠问题、注意力问题和烦躁易怒）。结果发现，包含上述4个重叠症状在内的边在PTSD和抑郁各症状直连边的总权重中占比高达 $5 4 . 0 \%$ ，这说明重叠症状在共存网络中起到了重要的桥接作用；将上述4个重叠症状剔除后，发现隶属于抑郁的悲伤、内疚和精神运动性迟滞症状以及隶属于PTSD 的未来受限和闪回症状是桥节点。另一项研究通过在线调查平台对1184 名被试进行了调查，并构建了一个包括PTSD、抑郁和GAD三者在内的共存网络。结果发现，隶属于PTSD 的情感麻木症状，以及隶属于GAD 的无法放松症状是网络中的核心症状，起着重要的桥接作用(Price etal,2019)。也有研究者为 2313 名青少年构建了一个包含PTSD、抑郁和创伤后负性认知在内的共存网络，但该网络只包括了9个PTSD 的特异性症状，并不包含躁郁维度，结果发现，创伤相关线索引起的情绪反应和注意力问题在网络中起到了桥接作用(De Haan et al.,2020)。

对以往有关PTSD 和抑郁共存网络的实证研究进行分析后发现，仅有DeHaan 等(2020)的研究对象是中小学生，但在网络中并没有将 PTSD 的躁郁维度囊括在内；其次，上述研究中涉及的创伤事件多为人为创伤，较少有研究关注重大自然灾难(例如地震)，而创伤类型又会影响 PTSD 的症状网络结构(Benfer et al.,2018)，进而可能会对 PTSD 和抑郁的共存模式产生影响；再次，虽然 Price 等(2019)的研究探讨了PTSD、抑郁和GAD 这三者共存网络中可能存在的子网络，但仅报告了子网络探测的结果，并没有在此基础上确定子网络间的桥症状，而桥症状的确定又十分依赖于网络中子网络边界的划分。此外，在现有的关于PTSD 和抑郁共存网络的实证研究中，仅有Lazarov 等(2020)的研究为二者构建了一个基于贝叶斯推断的有向网络，这在一定程度上能借助PTSD与抑郁间的因果关系来解释二者的共存现象。不过，Lazarov 等(2020)的研究对象为具有 PTSD 临床诊断的军人群体；且PTSD 与抑郁之间的因果指向性仍未有定论：可能PTSD 是抑郁的因(An et al.,2019)，或 PTSD 是抑郁的果(Arbisi etal.,2012)，或二者互为因果(Geng et al.,2019)。最后，Duek 等(2020)在研究中依托大样本 $( \Nu =$ 32841)，计算了共存网络的分半信度，这在统计上为研究结果的可重复性做出了保证。而Yarkoni 和Westfall(2017)则认为，最好在多个样本中对结果进行交叉验证，以应对心理学研究中的可重复性危机。

为揭示重大自然灾难后中小学生PTSD 和抑郁的共存模式，本研究分别在汶川地震和雅安地震1年后对灾区的中小学生展开调查，首先，构建囊括PTSD 和抑郁所有症状的共存网络，考察重叠症状和躁郁维度是否在其中起到了桥接作用；而后，剔除4个重叠症状，探寻症状网络中可能存在的子网络，并在此基础上确认子网络间的桥症状；同时，为二者构建基于贝叶斯推断的有向网络，以确定PTSD 和抑郁各症状间的因果指向性；最后，借助网络比较的方法对两个样本中PTSD 和抑郁共存网络的可重复性进行交叉验证。

# 2方法

# 2.1被试与程序

# 2.1.1研究样本

于汶川震后1年对灾区22所中小学校的在读学生进行抽样调查，共计调查 2530人，年龄区间为8至17岁，平均年龄12.86岁( $\mathrm { \mathop { S D } } = 1 . 9 6 ) \$ ，男生1189人 $( 4 7 . 0 \% )$ ；于雅安震后1年对灾区2所中学和1所小学的在读学生进行抽样调查，共计调查723人，年龄区间为9至17岁，平均年龄13.40 岁 $\cdot S D = 2 . 2 9 )$ ，男生345人 $( 4 7 . 7 \% )$ 。

# 2.1.2研究程序

采用整班施测的形式，由心理学专业研究生采用相同的指导语统一施测，当场回收问卷。为消除问卷填答可能带来的不适，为施测对象开展团体辅导活动。整个施测过程征得了学生本人、家长、学校校长和当地教育局的同意，并与学生签订了知情同意书，且得到了北京师范大学心理学部伦理委员会的批准。

# 2.2研究工具

# 2.2.1儿童创伤后应激障碍症状量表(CPSS)

儿童创伤后应激障碍症状量表(Child PTSD Symptoms Scale,CPSS)由 Foa 等(2001)参照DSM-IV中有关PTSD 的诊断标准编制而成，用于测查中小学生最近两周内的PTSD 症状水平，其在震后青少年群体中的信效度良好(Zhen etal.,2019)。该量表共包含17道题目，包括闯入性症状(5题)、回避性症状(7题)和警觉性增高症状(5题)三个维度，采用0(从未)至3(总是)的4点计分方式。在汶川和雅安样本中该量表的Cronbach's $\alpha$ 系数均为0.87。

# 2.2.2流调中心抑郁量表儿童版(CES-DC)

采用Fendrich 等(1990)编制的流调中心抑郁量表儿童版(Center for Epidemiologic StudiesDepression Scale for Children,CES-DC)测查中小学生最近两周内的抑郁症状水平，该量表在震后青少年群体中的信效度良好(Zhen et al.,2019)。CES-DC 采用0(没有)至3(总是)的4点计分方式，共20道题目，其中包含4道测量积极情绪的题目，本研究将这4道测量积极情绪的题目单独作为一个子网络。在汶川和雅安样本中该量表的Cronbach's $\mathfrak { a }$ 系数为分别为0.87和0.89。

# 2.3数据分析

# 2.3.1缺失数据的处理

汶川样本数据的缺失比例为 $1 . 2 \%$ ，雅安样本数据的缺失比例为 $0 . 3 \%$ 。鉴于缺失比例较低，根据 Levinson 等(2018)的建议，本研究使用 R-package mice 中的 mice 函数对缺失数据进行多重插补。

# 2.3.2无向网络的估计与可视化

使用高斯图形模型(Gaussian graphical model,GGM)拟合PTSD 和抑郁症状间的无向网络(Costantini et al.,2015)。症状网络由节点和边组成，节点(node)代表各个症状，节点A与节点B之间的连线为边(edge)，意为在控制了网络中的其他症状后,A与B间的偏相关系数，又称为边权重。考虑到本研究需对比两个样本的结果，在估计GGM的过程中引入融合图像最小绝对值收敛和选择算子，对边权重正则化，尽可能去除网络中假阳性的边(Danaher,et al,2014; Fried et al., 2018)。

使用R-package qgraph 中的 qgraph 函数对 GGM进行可视化(Epskamp et al.,2012)，节点的相对位置使用 Fruchtermann-Reingold 算法确定(Fruchterman & Reingold,1991)，节点间的联系越强，视觉距离就越近。为了便于在视觉上比较两个样本的网络结构，使用R-packageqgraph 中的averageLayout 函数确定各节点的具体布局，以保证两个样本中相同节点绝对位置的一致性。将网络中边权重的最大值固定为两个样本中边权重的绝对值的最大值，蓝色的边代表症状间的偏相关系数为正，红色的边则为负，边越粗、饱和度越高意味着症状之间的偏相关系数越大，联系越紧密。

# 2.3.3有向网络的估计与可视化

使用贝叶斯爬山算法(Bayesian hillclimbing algorithm)来确定症状间的有向网络结构。该算法采用迭代思想，每次迭代的起始状态(边的有无和指向性)是随机的，在迭代过程中会对整个网络进行多次扰动(反复添加、剔除和反转边的指向性)，且每次迭代过程会包含多个起始状态，当得到一个最佳的贝叶斯信息指数(Bayesian Information Criterion,BIC)时，则停止迭代(Scutari,2010)。借助 BootStrap 法(有放回抽样，1000 次)来保证有向网络结构的稳定性。在1000 次 BootStrap 的结果中，依据 Scutari 和 Nagarajan(2013)提出的标准来确定边的有无，依据边指向性出现的次数来确定边的指向性，即由症状A指向症状B的边在1000 次中至少需出现 501次。

借助有向无循环图(Directed Acyclic Graphs,DAG)对基于贝叶斯推断的有向网络进行可视化，这能在一定程度上阐明症状间的因果模式。在DAG中，边越粗，代表其相对 BIC 值越大（即从 DAG 中移除一条较粗的边比移除一条较细的边对模型拟合的破坏性更大)，节点的位置越靠近布局顶端，则相对重要性越强(McNally et al,2017)。

# 2.4 中心性估计

本研究使用预期影响指数(expected influence,EI)来量化无向网络中各节点的影响力。不同于强度中心性(strength)，在计算某个节点的 EI时，并不会将小于0 的边权重取绝对值，而是保留其符号(Robinaugh,et al.,2016)。根据 Jones 等人(2019)的建议，本研究使用桥预期影响指数(bridge expected influence，BEI)来确定PTSD 与抑郁间桥节点。BEI的计算方法与EI类似，在计算网络中隶属于某个子网络的特定节点的BEI时，仅考虑该节点与其他子网络中节点间的边，与该节点自身所处子网络中剩余节点间的边则不纳入计算。

# 2.5无向网络的准确性和稳定性检验

第一步，使用R-package EstimateGroupNetwork 中的 GroupNetworkBoot 函数对无向网络的准确性进行检验。该函数借助 BootStrap 法(有放回抽样，1000 次)，同时对汶川和雅安两个样本进行检验，以得到各边权重的 $9 5 \%$ 置信区间(confidence intervals,CI)，各边权重的95% CI越宽，在解释时就越要谨慎。第二步，使用R-package bootnet 中的 bootnet 函数对无向网络的稳定性进行检验。该函数同样借助 BootStrap 法(成比例剔除样本，1000 次)来确定各节点中心性指数等级排序的稳定性。即在使用较少的样本重新估计网络后，各节点中心性指数的等级排序是否会发生变化。本研究同时使用bootnet包中的corStability 函数计算各网络的中心性稳定系数（centrality stability coefficient,CS-coefficient），CS-coefficient 的值在 0.5以上时意味着样本网络的节点中心性具有较高的稳定性。第三步，分别对网络中各边权重间的差异以及各节点中心性指数间的差异进行检验( $( \alpha = 0 . 0 5 )$ 。

# 2.6子网络探寻

本研究使用自旋玻璃算法(spin glass algorithm)来确定在剔除重叠症状后，PTSD 和抑郁共存网络中可能存在的子网络(Heeren etal.,2018)。这是一种基于模块化的子网络探测算法，其基本假设是子网络内各节点间的相互联系要显著强于这些节点与其他子网络内节点间的联系(Reichardt& Bormholdt,2006)。需要注意的是，该算法仅允许一个节点被划分到一个特定的子网络中，且该算法每次执行的结果可能会不同。为此，本研究重复执行该算法1000次，而后从中提取频率最高的聚类模式报告。

# 2.7 网络比较

本研究从全局不变性和局部不变性两个角度出发，使用置换检验 5000 次(Permutationtests)的方法对两个样本的无向网络进行比较(Network Comparison Test,NCT; van Borkulo etal.,2016)。全局不变性包括网络结构不变性和网络整体强度不变性两个方面。网络结构不变性检验的统计量是两个网络边权重的绝对值的最大差值，网络整体强度不变性检验的统计量则是两个网络中所有边权重绝对值之和的差值；局部不变性则是对两个样本网络中各边权重和各节点中心性指数的差值进行检验(使用 Holm-Bonferroni 算法进行校正)。考虑到本研究中汶川地震样本的被试量为 2530，雅安地震样本的被试量仅为723，而样本量又会对网络比较的结果产生影响。故本研究先从汶川样本中随机抽取723 名被试进行 NCT，并重复该步骤100次，而后统计并报告以上各个统计量显著的次数(Wang etal.,2020)。

# 2.8共同方法偏差检验

采用Harman单因子检验法对共同方法偏差进行检验，结果发现，在汶川和雅安两个样本中，未旋转的情况下分别得到了8和7个因子，第一个因子解释的变异量分别为 $1 9 . 6 \%$ 和$3 0 . 9 \%$ ，均小于 $4 0 \%$ 的临界值，故本研究不存在明显的共同方法偏差(Podsakoff etal.,2003)。

# 3结果

# 3.1描述性统计与样本间的差异检验

两个样本的人口统计学信息和创伤暴露情况见表1，CPSS 和CES-DC 各题项的标签、缩写和完整表述见附表1，各题项的描述性统计结果见附表2。由附表2可知，尽管本研究中各症状的得分均未违反正态分布的假设(偏度大于2或峰度大于7，Curran,etal.1996)，但依据网络分析的标准程序(Epskamp& Fried,2018)，本研究在进行网络分析之前，使用R-packagehuge中的huge 函数对数据进行转换。

汶川样本 CPSS 的均值为 $1 4 . 1 0 ( S D = 7 . 9 4 )$ ，雅安样本CPSS 的均值为 $1 3 . 8 6 ( S D = 8 . 1 4 )$ ，不存在显著差异 $( t = 0 . 7 2 , p = 0 . 4 7 )$ ；汶川样本CES-DC 的均值为 $1 9 . 8 0 ( S D = 9 . 1 3 )$ ，雅安样本CES-DC的均值为 $1 9 . 8 6 ( S D = 1 0 . 5 9 )$ ，不存在显著差异 $( t = - 0 . 1 4 , p = 0 . 8 9 )$ 。汶川样本中，以16 分作为划界标准(Zhou&Wu,2019),PTSD的检出率为 $3 9 . 8 \%$ ，以24分作为划界标准(Gotlib,et al．1995)，抑郁的检出率为 $3 1 . 1 \%$ ，二者的共存检出率为 $2 4 . 8 \%$ ；雅安样本中PTSD 的检出率为 $3 6 . 9 \%$ ，抑郁的检出率为 $3 2 . 1 \%$ ，二者的共存检出率为 $2 4 . 3 \%$ 。

# 3.2全症状网络估计结果

汶川样本囊括PTSD 和抑郁所有症状的网络(汶川网络1)见图 $1 ^ { 3 }$ ，汶川网络1的全局特性见表2，从中可看出各子网络内部的联结要强于子网络间的联结。在PTSD 和抑郁直连且权重不为0的172条边中，包含重叠症状4在内的边有55 条 $( 3 2 . 0 \% )$ ，总强度为 $1 . 8 2 ( 3 4 . 1 \% )$ ：包含躁郁维度在内的边有86 条 $( 5 0 . 0 \% )$ ，总强度为 $3 . 3 6 ( 6 3 . 0 \% )$ ；不包含躁郁维度在内的边共有86条 $( 5 0 . 0 \% )$ ，总强度为 $1 . 9 7 ( 3 7 . 0 \% )$ 。汶川网络1中权重较大的边见附表3，从中可知，PTSD 子网络内权重较大的边多为闯入性症状间的连边，PTSD 和抑郁子网络间的直连边中权重较大的边多为二者重叠症状间的连边。汶川网络1中所有边的权重见附表4，雅安网络1所有边的权重见附表5。

雅安样本囊括 PTSD 和抑郁所有症状的网络(雅安网络1)见图 $1 ^ { 3 }$ ，雅安网络1的全局特性与汶川网络1基本相同（见表2)，在雅安网络1PTSD 和抑郁直连且权重不为0的161条边中，包含重叠症状在内的边有 50条 $( 3 1 . 1 \% )$ ，总强度为 $1 . 8 0 ( 3 4 . 7 \% )$ ；包含躁郁维度在内的边有83条 $( 5 1 . 6 \% )$ ，总强度为 $3 . 3 9 ( 6 5 . 3 \% )$ ；不包含躁郁维度在内的边共有78 条 $( 4 8 . 4 \% )$ ，总强度为 $1 . 8 0 ( 3 4 . 7 \% )$ 。雅安网络1中权重较大的边见附表3，其表现出的特性与汶川网络1基本相同。汶川网络1和雅安网络1中边权重的 $9 5 \% \mathrm { C I }$ 见附录图3，从中可知，除个别权重较大的边外，各边的 $9 5 \% \mathrm { C I }$ 较宽，在解释时需谨慎；两个样本全症状网络的稳定性分析见附录图4，汶川网络1的CS-coeficient为0.75，雅安汶川网络1为0.60，故两个样本网络的节点中心性具有较高的稳定性；两个样本全症状网络中各边权重的差异性检验见附录图5，各节点EI值的差异性检验见附录图6，各节点BEI值的差异性检验见附录图7。从中可知两个网络中权重较大的边，EI/BEI值较大的节点均显著大于网络中其余的边或节点。

汶川网络1和雅安网络1各节点的标准化EI/BEI值见图2，可以看到两个样本中各节点EI和BEI的排序模式高度一致：两个样本中各节点标准化EI值的皮尔逊相关系数为0.97，标准化BEI值的皮尔逊相关系数为0.99。在两个样本中，节点A5（注意力问题_A）、A6（情绪低落）、A10(恐惧)、A18(悲伤)和A20（难以开始）的标准化EI值大于一个标准差，表明这些节点和网络中其余的节点有更多的联结；节点A5（注意力问题_A）、A10(恐惧)、C4（情绪麻木）、C6（疏离）和D1（注意力问题）的标准化BEI值大于一个标准差，表明这些节点是连接PTSD 和抑郁的桥节点。

对汶川样本随机抽样100次后的NCT结果进行统计发现，网络结构不变性显著的次数为24次；网络整体强度显著的次数为2次，可推断汶川网络1和雅安网络1具有全局不变性；各边权重和各节点EI值的显著性次数见附表6，从中可知，仅有少部分边和节点在对汶川样本随机抽样后进行的置换测试中显著，次数均很少，可推断汶川网络1和雅安网络1具有局部不变性。故本研究认为汶川和雅安两个样本的全症状共存网络是等价的。

# 3.3剔除重叠症状后的网络估计结果

从附表7可知，使用自旋玻璃算法探测两个样本PTSD 和抑郁共存网络中的子网络得到了相同的结果：共有3个子网络，CPSS 中的节点C2(未来受限)、C4(情绪麻木)、C5(失忆)和C6(疏离)与CES-DC中的节点(不包括 A10)聚为一个子网络;而CES-DC 中的节点A10(恐惧)则和CPSS 中的剩余节点聚为一个子网络；积极情绪的4个节点聚为一个子网络。在此基础上，本研究将包含4个积极情绪节点在内的子网络命名为积极情绪子网络；包含PTSD核心症状以及CES-DC 中节点A10(恐惧)在内的子网络命名为PTSD 类子网络；将最后一个子网络命名为抑郁类子网络。在本研究中，仅确定PTSD类和抑郁类子网络中的桥节点。

两个样本剔除重叠症状后PTSD 和抑郁的共存网络(汶川网络2 和雅安网络 2)见附录图2，节点的聚类模式与子网络探测的结果相一致。汶川网络2和雅安网络2的全局特性见表2，可以看到在正确划分了子网络后，各子网络的密度进一步提高，PTSD 和抑郁子网络间直连边的平均权重有所下降。汶川网络2和雅安网络2中权重较大的边见附表3,可知 PTSD和抑郁子网络内权重较大的边与汶川网络1和雅安网络1基本一致，但在剔除了重叠症状且正确划分了子网络后，PTSD 和抑郁间权重较大的直连边发生了变化。

汶川网络2和雅安网络2各节点的标准化EI/BEI值见图2。可以看到剔除重叠症状后两个样本中各节点EI和BEI的相对排序仍高度一致。在两个样本中,节点A10(恐惧)、A18(悲伤)和 B2（想法侵入）的标准化EI值大于一个标准差，表明这些节点和网络中其余的节点有更多的联结；节点A10(恐惧)、C4（情绪麻木）、D3（惊跳反应）和D4（高警觉）的标准化BEI值大于一个标准差，表明这些节点是连接PTSD 和抑郁的桥节点。

表1两个样本的人口统计学信息和创伤暴露情况  

<html><body><table><tr><td rowspan="2">变量</td><td colspan="2">汶川</td><td colspan="2">雅安</td></tr><tr><td>频数</td><td>百分比</td><td>频数</td><td>百分比</td></tr><tr><td>民族</td><td></td><td></td><td></td><td></td></tr><tr><td>汉族</td><td>405</td><td>16.0%</td><td>717</td><td>99.2%</td></tr><tr><td>藏族</td><td>628</td><td>24.8%</td><td>6號</td><td>0.8%</td></tr><tr><td>羌族</td><td>1434</td><td>56.7%</td><td></td><td></td></tr><tr><td>彝族</td><td>2</td><td>0.1%</td><td></td><td></td></tr><tr><td>其他</td><td>57</td><td>2.3%</td><td></td><td></td></tr><tr><td>年级（T1）</td><td></td><td></td><td></td><td></td></tr><tr><td>四年级</td><td>451</td><td>17.8%</td><td>130</td><td>18.0%</td></tr><tr><td>五年级</td><td>505</td><td>20.0%</td><td>150</td><td>20.7%</td></tr><tr><td>六年级</td><td>450</td><td>17.8%</td><td></td><td></td></tr><tr><td>初一</td><td>461</td><td>18.2%</td><td>128</td><td>17.7%</td></tr><tr><td>初二</td><td>431</td><td>17.0%</td><td>174</td><td>24.1%</td></tr><tr><td>高一</td><td>99</td><td>3.9%</td><td>112</td><td>15.5%</td></tr><tr><td>高二</td><td>127</td><td>5.0%</td><td>29</td><td>4.0%</td></tr><tr><td>创伤暴露</td><td></td><td></td><td></td><td></td></tr><tr><td>被困</td><td>500</td><td>19.8%</td><td>61</td><td>8.4%</td></tr><tr><td>受伤</td><td>155</td><td>6.1%</td><td>83</td><td>11.5%</td></tr><tr><td>父/母死亡</td><td>76</td><td>3.0%</td><td>2</td><td>0.3%</td></tr><tr><td>老师死亡</td><td>105</td><td>4.2%</td><td>2</td><td>0.3%</td></tr><tr><td>同学死亡</td><td>327</td><td>12.9%</td><td>82</td><td>11.3%</td></tr><tr><td>亲戚/朋友死亡</td><td>906</td><td>35.8%</td><td>79</td><td>10.9%</td></tr><tr><td>房屋严重或完全损毁</td><td>1607</td><td>63.5%</td><td>497</td><td>68.6%</td></tr><tr><td>害怕受伤</td><td>1609</td><td>63.6%</td><td>425</td><td>58.7%</td></tr><tr><td>害怕死亡</td><td>1510</td><td>59.7%</td><td>420</td><td>58.0%</td></tr></table></body></html>

注：某些变量存在缺失值，故各部分之和小于或等于总样本数

表2各网络的全局特性  

<html><body><table><tr><td colspan="2"></td><td>汶川网络1</td><td>雅安网络1</td><td>汶川网络2</td><td>雅安网络2</td></tr><tr><td></td><td>整个网络</td><td>666</td><td>666</td><td>465</td><td>465</td></tr><tr><td>所有</td><td>PTSD子网络</td><td>136</td><td>136</td><td>45</td><td>45</td></tr><tr><td>被估计的边</td><td>抑郁子网络</td><td>120</td><td>120</td><td>136</td><td>136</td></tr><tr><td></td><td>PTSD 与抑郁的直连边</td><td>272</td><td>272</td><td>170</td><td>170</td></tr><tr><td></td><td>整个网络</td><td>465</td><td>437</td><td>345</td><td>315</td></tr><tr><td>权重</td><td>PTSD子网络</td><td>111</td><td>104</td><td>43</td><td>42</td></tr><tr><td>不为0的边</td><td>抑郁子网络</td><td>99</td><td>98</td><td>115</td><td>114</td></tr><tr><td></td><td>PTSD 与抑郁的直连边</td><td>172</td><td>161</td><td>111</td><td>96</td></tr><tr><td rowspan="4">网络密度</td><td>整个网络</td><td>0.70</td><td>0.66</td><td>0.74</td><td>0.68</td></tr><tr><td>PTSD子网络</td><td>0.82</td><td>0.76</td><td>0.96</td><td>0.93</td></tr><tr><td>抑郁子网络</td><td>0.83</td><td>0.82</td><td>0.85</td><td>0.84</td></tr><tr><td>PTSD与抑郁的直连边</td><td>0.63</td><td>0.59</td><td>0.65</td><td>0.56</td></tr><tr><td rowspan="5">网络强度</td><td>整个网络</td><td>18.53</td><td></td><td></td><td></td></tr><tr><td>PTSD子网络</td><td>5.28</td><td>17.95 5.04</td><td>15.11 3.29</td><td>14.52 3.39</td></tr><tr><td>抑郁子网络</td><td>5.13</td><td>5.16</td><td>6.39</td><td>6.41</td></tr><tr><td>PTSD 与抑郁的直连边</td><td>5.33</td><td>5.19</td><td>2.73</td><td>2.30</td></tr><tr><td>整个网络</td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="4">平均权重</td><td></td><td>0.04</td><td>0.04</td><td>0.04</td><td>0.05</td></tr><tr><td>PTSD子网络</td><td>0.05</td><td>0.05</td><td>0.08</td><td>0.08</td></tr><tr><td>抑郁子网络</td><td>0.05</td><td>0.05</td><td>0.06</td><td>0.06</td></tr><tr><td>PTSD 与抑郁的直连边</td><td>0.03</td><td>0.03</td><td>0.02</td><td>0.02</td></tr></table></body></html>

注：在汶川网络1和雅安网络1中，PTSD子网络和抑郁子网络是依据CPSS 和CES-DC 进行划分的；在汶川网络2和雅安网络2中，PTSD子网络和抑郁子网络是依据附表7的子网络探测结果来划分的，附表3同理。

![](images/76529233cff6309e9bc08f11dda2e976cd8e1375faee55afd2a163f5c5a33339.jpg)  
图1汶川样本和雅安样本的全症状网络(仅呈现权重大于0.05的边)

B1:亚梦  
B2：想法侵入  
B3:情感反应  
B4：闪回  
B5：生理反应  
C1：兴趣减退  
C2：未来受限  
C3：回避线索  
C4:情绪麻木  
C5：失忆  
C6:疏离  
C7：回避想法  
D1：注意力问题_D  
D2：睡眠问题_D  
D3：惊跳反应  
D4:高警觉  
D5：烦躁易怒  
A1:感到困扰  
A2：食欲不振  
A3：外部支持无用  
A5：注意力问题A  
A6：情绪低落  
A7:精疲力竭  
A9：挫败无用  
A10:恐惧  
A11:睡眠问题_A  
A13：活力降低  
A14:孤独  
A15:被排斥  
A17:哭泣  
A18:悲伤  
A19:不被喜爱  
A20：难以开始  
A4：自我认可  
A8:乐观  
A12:开心  
A16:享受生活  
VWMM wWMM/ 汶川雅安  
-2-2-  
B1B2B3B4B5C1C2C3C4C5C6C7D1D2D3D4D5A1A2A3A5A6A7A9A10A1IA13A4Ai5A17A8A19A20A4A8A12A16 B1B2B3B4B5C12C3C4C5C67D1D2D3D4D5A1A2A3A5A6A7A9A0A1A13A14Ai5AI7A8A19A20全症状网络各节点的标准化BEI值全症状网络各节点的标准化EI值  
MWWMM W N 汶川雅安  
EI  
2  
B1B2B3B4B5C3C4C5C6DD4A1A2A3A6A7A9A10A3AI4AI5A17A18A19A20A4A8A12A16 A10A13A14A15A17A18A19A20剔除重叠症状后网络中各节点的标准化EI值 剔除重叠症状后网络中各节点的标准化BEI值

图2网络中各节点的标准化中心性指数

![](images/e4057485d272ecd3bfe246bccef325e5bde2a52d3b0dd97d2d9a740c44d02cdd.jpg)  
图3汶川和雅安样本的DAG （剔除重叠症状）

# 3.4有向网络估计结果

剔除重叠症状后汶川样本的有向网络见图3，从宏观上来看，多由抑郁症状激发PTSD症状；从微观上来看，节点A17(哭泣)位于布局的最顶端，没有任何一个节点指向 A17，其触发包括节点A10(恐惧)在内的10 个节点；节点A13(活力降低)和C5(失忆)位于布局的最底端，不触发任何节点；在PTSD 类子网络中，节点A10(恐惧)位置最高，触发包括节点B1(噩梦)在内的11个节点，且多由闯入性症状触发回避性症状。剔除重叠症状后雅安样本的有向网络结构见图3，但连边数量较少。和汶川样本相似，从宏观上来看，多由抑郁症状激发PTSD 症状；从微观上来看，节点A17(哭泣)位于布局的最顶端，其触发包括 B3(情感反应)在内的6个节点；节点A13(活力降低)和C7(回避想法)位于布局的最底端，不触发任何节点;在 PTSD 类子网络中，节点A10(恐惧)位置最高，触发包括节点B1(噩梦)在内的9个节点，且多由闯入性症状触发回避性症状。

# 4讨论

本研究在两个相互独立的样本中交叉验证了重大自然灾难后中小学生 PTSD 和抑郁症状的共存模式：揭示了二者的重叠症状以及躁郁维度下的部分症状是联结 PTSD 和抑郁的桥症状；并在剔除了重叠症状后重新划分了二者的症状边界，在此基础上确认了恐惧、惊跳反应和高警觉症状的桥接作用；同时借助贝叶斯爬山算法为二者构建了有向网络，揭示了症状间可能存在的因果关系模式，保证了研究结论的可推广性，这在一定程度上回应了心理学研究的可重复性危机。

# 4.1重叠症状在PTSD和抑郁共存网络中的作用

从汶川网络1和雅安网络1中可以看出，兴趣减退、注意力问题、睡眠问题和烦躁易怒这4个PTSD 和抑郁的重叠症状均在二者的共存网络中起到了桥接作用，可被视为二者共存网络中的桥节点。在汶川网络1和雅安网络1的PTSD 和抑郁各症状直连且权重不为0 的边中，从宏观的角度来看，包含上述4个重叠症状在内的边在数量和权重上都具有较高的比重;从微观的角度来看，权重最大的边都是D2(睡眠问题_D）一 A11(睡眠问题_A)和A5(注意力问题_A）一 D1(注意力问题_D)，这与Duek 等(2020)的结果一致，说明睡眠问题和注意力问题这两个PTSD与抑郁重叠的症状在二者的共存网中起到了重要的桥接作用，可被视为二者间的桥节点。同时，从节点的 BEI属性出发(见图 2)，虽然 D5(烦躁易怒)和C1(兴趣减退)的 BEI排序并没有D2/A11(睡眠问题)和D1/A5(注意力问题)高，但在汶川地震样本PTSD 和抑郁直连且包含上述4个重叠症状(6 个节点)在内的边中，包括节点 D5(烦躁易怒)和 C1(兴趣减退)在内的边共有 21条 $( 3 8 . 2 \% )$ ，总强度为 $0 . 7 1 ( 3 9 . 0 \% )$ ；这一数据在雅安地震样本中为20条 $( 4 0 . 0 \% )$ ，总强度为 $0 . 7 1 ( 3 9 . 4 \% )$ 。这说明烦躁易怒和兴趣减退这两个症状在PTSD 和抑郁的共存网络中也起到了桥接作用，也可被视为二者间的桥节点，这同Mitchell等(2017)和Garabiles 等(2020)的研究结论相一致。

不过，在Afzali等(2017)的研究中，包含上述4个重叠症状在内的边的总强度在二者间直连边的总强度中占比却高达 $5 4 . 0 \%$ ，明显高于本研究中所报告的 $3 4 . 1 \%$ 和 $3 4 . 7 \%$ 。这可能是因为在Afzali等(2017)的研究中测量抑郁症状所使用的量表为世界心理健康综合国际诊断访谈量表，该量表包含了CED-DC所没有的兴趣减退和烦躁易怒这两个症状题项。

# 4.2躁郁维度在PTSD和抑郁共存网络中的作用

从宏观的角度来看，在两个样本PTSD 和抑郁直连且权重不为0的边中，包含躁郁维度在内的边在强度上占有很大的比重，均在 $6 3 \%$ 以上，这表明躁郁维度在PTSD 和抑郁共存网络中起到了桥接作用。从微观的角度来看，除了4个重叠症状外，属于躁郁维度的症状/节点C6(疏离)、C4(情绪麻木)和C2(未来受限)其BEI在汶川网络1中分别位列第2、第4和第11位(见图2)；在雅安网络1中，分别位列第2、第4和第9位(见图2)；同时，包含上述 3个节点在内的边(C4-A3、C6-A14 和C2-A20)的权重在两个样本 PTSD 和抑郁的直连边中均排在前12位。这意味着，躁郁维度下的疏离、情绪麻木和未来受限这3个症状/节点也可被视为PTSD 和抑郁共存症状网络中的桥节点，这同 Afzali 等(2017)、Choi等(2017)、Price 等(2019)和 Gilbar(2020)的结果相一致。但同样是隶属于躁郁维度的节点C5(失忆)，其 BEI在两个样本中的排序都不靠前，分别位列第 24位和第 22位。这可能是因为节点C5的中心性指数 EI在两个样本中均较低，在网络中和其余节点的连边较少，属于网络中的边缘节点。这也同先前针对 PTSD 的网络分析结果相一致：失忆在PTSD 的各个症状中，其中心性指数往往是最低的(Lazarov etal.,2020)。故此，本研究认为躁郁维度下的失忆症状(节点C5)并没有在PTSD 和抑郁的共存网络中起到桥梁作用，不应当被认为是二者间的桥节点。

同时，剔除重叠症状后两个样本的子网络探测结果均表明，PTSD 躁郁维度下的C2(未来受限)、C4(情绪麻木)、C5(失忆)和C6(疏离)与抑郁各节点(节点A10除外)可归为一个子网络，这与 Gros 等(2010)采用因素分析的方法探讨 PTSD 和抑郁的结构所得结论相一致。该结果一方面证明了躁郁维度与抑郁的联系相较PTSD 的特异性症状更为紧密；另一方面，也说明了DSM-IV 预先划分的症状边界并不准确。在 2018 年面世的 ICD-11(InternationalClassificationof Diseases)中，PTSD 的诊断标准仅包含6个特异性症状，并未包括躁郁维度下的8个症状(Brewin et al.,2017)。而本研究恰恰发现 ICD-1I标准下PTSD 的6 个症状都归属在同一个子网络之内，考虑到 DSM-IV 本质上是DSM-5 的子集(Flory&Yehuda,2015)，故在 DSM 框架下，PTSD 的诊断标准可能存在一定程度冗余。此外，本研究还发现CES-DC中的症状A10（恐惧）也归在PTSD 类子网络中，这也从侧面提示ICD-1I对PTSD 的症状划分过于精简，即创伤事件后以恐惧为代表的负性情绪可能也是PTSD区别于抑郁的独特症状条目。

若基于子网络探测结果进一步考察PTSD类子网络和抑郁类子网络间的桥节点，则发现（见图2）无论在哪个样本中，节点C4(情绪麻木)仍是PTSD 和抑郁子网络间的桥节点，但节点C2(未来受限)和节点C6(疏离)的BEI排序则大幅下降。尤其是节点C6(疏离),在DSM-IV设定的边界下被确认为PTSD 和抑郁之间的桥节点：其在两个样本中的BEI都排在第2位。但若基于子网络探测的结果，其BEI却排在最后一位。而节点A10(恐惧)、D3(惊跳反应)和D4(高警觉)的标准化BEI值大于一个标准差，可被认为是PTSD 和抑郁子网络间的桥节点。这3个节点是首次被确认为PTSD 和抑郁间的桥节点，原因在于先前的研究都是在DSM 预先设定的边界下探讨PTSD与抑郁间的桥节点，在统计上遮蔽了上述3个节点在二者间的桥接作用。这进一步表明，在经历了重大自然灾难后的儿童和青少年群体中，当考察PTSD 和抑郁的共存网络结构时，DSM-IV预先划分的PTSD症状边界并不适用。

# 4.3 PTSD 和抑郁的有向网络(DAG)

在汶川和雅安两个样本中，从宏观上来看，DAG 的结果均表明更有可能是抑郁症状激发 PTSD 症状，这同先前部分研究结果一致。例如，Arbisi等(2012)发现，在控制了前一个时间点的PTSD症状水平后,抑郁的症状水平对3个月后PTSD 的诊断具有显著的预测作用。不过，Lazarov 等(2020)的研究却发现，在 PTSD 和抑郁的有向网络(DAG)中，更有可能是PTSD 症状激发抑郁症状。这可能是因为Lazarov 等(2020)的研究对象为反复暴露在战争创伤下经过临床诊断的军人样本，而本研究的对象则是地震后的中小学生，并非临床样本。Janoff-Bulman(1989)认为创伤事件会冲击个体的核心信念系统，考虑到中小学生尚未形成稳定的世界观，在经历了地震这样的重大创伤事件后可能仅看到了事情的消极面，并通过侵入性反刍持续放大消极影响(Ehlers& Clark,2008)，认为外界和他人都是不值得信赖的，产生悲观绝望的消极情绪，将自己和外界隔离开来，体验到被排斥和孤独感。这些消极情绪可能不利于中小学生理性看待创伤事件并尝试将其整合到自己的记忆系统中，导致这部分记忆难以进行有意识的检索，以至出现再体验等症状(Ehlers&Clark,2000)。同时考虑到本研究在汶川和雅安两个样本中进行了交叉验证，结果更具普遍性和说服力。

从微观角度看，在PTSD类子网络中，更有可能是闯入性症状激发回避性症状，这也同Lazarov 等(2020)的研究结论一致。Horowitz(1976)提出的关于PTSD 的应激反应理论认为，在经历创伤事件后，若个体未能将由创伤事件带来的新认知同化到自身已有的认知图式当中，有关创伤事件的记忆和线索就会不断闯入个体的意识(例如，出现侵入和闪回等症状)，导致个体出现不良的身心反应(例如，出现由创伤线索导致的生理反应和情感反应等症状)，此时个体就会采取防御性的措施来对抗这些消极的身心反应(例如，主动回避相关线索)，即出现回避性症状。在抑郁类子网络中，节点A17（哭泣）和A18（悲伤）等抑郁情绪更可能是上游症状，Abramson 等(1989)提出的抑郁无望理论认为，创伤事件会使个体体验到无望感，进而可能会出现悲伤等抑郁情绪和哭泣等行为表现，并由此引发孤独和情绪低落等症状。

# 4.4研究价值与不足

借助网络分析模型，本研究发现了灾后中小学生PTSD 和抑郁各症状的共存模式，揭示了联结二者的桥梁症状，重新划分了二者的症状边界，同时本研究也发现DSM对PTSD 症状边界的划分不够准确，ICD-11的 PTSD 诊断标准过于精简。更为重要的是，本研究的所有发现都在汶川和雅安两个相互独立的样本中进行了交叉验证，结论具有一定的可推广性。

除此之外，本研究对临床实践也具有一定的指导价值。在对灾后中小学生进行心理评估和干预时，首先应当重视PTSD 和抑郁的共存情况，优先识别并考虑二者之间的桥症状，以筛选出高风险来访者；其次，在对这一群体进行干预的过程中，应在厘清 PTSD 和抑郁症状边界的情况下，以桥症状作为突破口来拟定干预策略，因为桥症状在二者的共存网络中起着联结作用，桥症状的缓解对PTSD 和抑郁共存现象的消除意义重大；最后，在对出现了PTSD和抑郁共存现象的中小学生进行回访调查时，也应特别注意桥症状是否复发，以防止二者的共存现象再次出现。

需要注意的是，本研究也存在一些不足：第一，无论是汶川还是雅安样本，均为非临床样本，且自我报告法获取的数据可能会高估 PTSD 和抑郁的严重程度。第二，由于本研究收取数据时DSM-5的诊断标准尚未问世，故采用了基于DSM-IV 的工具对PTSD 症状进行测量，未来的研究可以进一步采用DSM-5的PTSD 诊断标准对本研究进行验证。第三，本研究针对的是震后中小学生，在将研究结论推广到经历了其他创伤类型的群体时需谨慎。未来可交叉对比多种创伤类型下PTSD 和抑郁的共存模式，以加深对这一问题的认识；第四，本研究使用CES-DC 获取震后中小学生的抑郁症状水平，但该量表缺少了测量兴趣减退和烦躁易怒的题项，未来可采用其他抑郁测量工具进行分析。最后，可考虑利用纵向设计构建PTSD 和抑郁之间有向且存在反馈回路的共存网络，以进一步确定各症状间可能存在的因果关系模式。

# 参考文献

Abramson,LYetasyG.,&llL.99).oplessspessedbeoepesiooicl Review,96(2),358-372.   
Afzali,M.Herd,sgr,deT().etwopoaceoit postraumatic stress disorder and major depresive disorder:Theroleof overlapping symptoms.Journal of Affective Disorders,208,490-496.   
An,Y.,Huang,JhenY&Deng,Z.(19).Lngidinalossggedatiosipsetweenpostraaticstressdsoder depression inadolescents folowing theYancheng tornado inChina.Psychological Trauma:TheoryResearch,Practice,and Policy,11(7),760-766.   
Arbisi,P.A.,Kaler,.E,Kehle-Forbes,S..Ebes,C.R.Pousny,.A.,&uras,P.(O2).Tepredictivevalidityofte Checklist inanonclinical sampleofcombat-exposed National Guard troos.PsychologicalAsessment,24(4),0341040.   
Armour,C.,&Shevlin,M.(2Ol0).TestingthedimensionalityofPTSDandthespecificityofthedysphoriaFactor.Journalofoss& Trauma,15(1),11-27.   
Benfer,N.,Barden,J.R.CeroL,Kramer,L.B.，Whiteman,S.E,Rogers,T.A.WeathersFW.(218).Networkodelsof posttraumatic stress symptoms across trauma types.Journal of Anxiety Disorders,58,70-77.   
Borsboom,D.(2O17).A network theory of mental disorders.World Psychiatry,l6(1),5-13.   
Borsboom,D,&Cer,A.O.).etworkalyisAtegatieroachtucturefpsyoatologyAnalRevief Clinical Psychology,9,91-121.   
Brewin,C.R.Cre,.,ynd,P.evin,.,ercker,A.,ryat,R.Aeed,G..().Arvieocurrteienc regarding the ICD-11 proposals for diagnosing PTSD and complex PTSD. Clinical Psychology Review,58,1-15.   
Cai,Y.Q,Dong.Y,Yuan,&H,C.P.().NtwkaalysaditslicatiosinologyAdancsinyoloical Science,28(1),178-190.   
[蔡玉清，董书阳，袁帅，胡传鹏.(2020).变量间的网络分析模型及其应用．心理科学进展,28(1),178-195.]   
Cenat,J.M.，& Derivois,D.(2O15).Long-termoutcomesamongchildandadolescentsurvivorsofthe20l0 Haitianearthquake. Depression and Anxiety,32(1),57-63.   
Chen,C.,Wang,L,CaoC.Q.,G.(1).Pschopatologicalntworkthoryethodsandchalenges.Advancesinycological Science,29(10),1724-1739.   
[陈琛，王力，曹成琦，李根.(2021).心理病理学网络理论、方法与挑战 心理科学进展,29(10),1724-1739.]   
Chen,X.C.,Xu,J.J,Li.,Li,GuoW.Jan,.S..Hu,J..(7).Teroleofpersonalityandsubjectiveepose experiences in postraumatic stress disorder and depresion symptoms among children following Wenchuan earthquake. Scientific Reports,7,1-9.   
Choi,K.W.,Batchelder,A.W,Ehlinger,P.P.，Safren,S.A.&OCleirigh,C.(217).Aplyngnetworkanalysistopsychological comorbidityandhealth behavior:Depresion,PTSD,andsexualrisk insexualminority enwithtrauma histories.Joumalof Consulting and ClinicalPsychology,85(12),1158-1170.   
Costantini,G.Epsamp,S.,Borsboom,D.,PeruginiM.,Motus,R.Waldorp,L.J,&Cramer,A.O.J.(2015).StateoftheaR personalityresearch: AtutorialonnetworkanalysisofpersonalitydatainR.Journalof Research inPersonality,54,13-29.   
Cramer,A.O.WaldorpLJaderasH.L&Borsboom,D.(Ol).Comorbidity:Aetworkperspective.Behavioralndrain Sciences,33(2-3),137-193.   
Curran,P.J.,West.G&chJF996.bsftsttolistioi factoranalysis.Psychological methods,I(1),16-29.   
Danaher,P.Wang,P&iD.().ejtgacalfoersevarceeaacsulileo of the Royal Statistical Society: Series B(Statistical Methodology),76(2),373-397.   
DeHaan,A.dlt.edE.lkesicEatseen)ioo cognitions,postraumaticstressanddepresion inchildrenandadolescents exposedtotrauma:Anetwork analysis.Jouralof Child Psychology and Psychiatry,6l(1),77-87.   
Duek,O.,Spilreak.HedE.,-o,I().tokalspresi 158,139 treatment-seeking veterans with PTSD.Depress and Anxiety,38(5),554-562.   
Ehlers Aand Clark DM(20o)Acognitive model of postraumatic stressdisorder.Psychiatria Hungarica 15,319-345.   
Ehlers,A,&ark,D.).ostrmatictrssdder:eeveloptofeiepshlogicalreamnts.NcJoual of Psychiatry, 62,11-18.   
Eksi,A.Bru,K.te-Veid,HeyerliGdm,paa,Dyaak,.O).sfctoforedeeot of PTSDanddepression among childand adolescent victims following a7.4 magnitude earthquake.InternationalJournalof Psychiatry in Clinical Practice,1l(3),190-199.   
Elhai,J.D.,Grubaugh,A.L.Kashdan,T.B.,&Frueh,B.C.(o8).EmpiricalexaminationofproposedrefiementtoD-IV postraumatic stress disorder symptom criteria using the National Comorbidity Survey Replication data.Journalof Clinical Psychiatry, 69(4),597-602.   
Epskamp,S.,&Frid,E.I.(18).Atoaloguarzdpatialoeationetwoks.Phologiclmehd,(4),34   
Epskamp,S.,Cramer,A.O.J.，Waldorp,L.J.，Schmitmann，V.D.，&Borsboom,D.(2012).qgraph:Network Visualizationsof Relationships in Psychometric Data.Journal of Statistical Software,48(4),1-18.   
Fan,F.,Zang,Y.YangY,o,L&iuX.(l1).Smptomsofostrmatcstresssorderdepresiondaieon adolescents following the 20o8 Wenchuan earthquake in China.Journal of Traumatic Stress,24(1),44-53.   
Fendrich,M.,Weissman,.,&Wer,V99).reengfoepesivedodrireddoesets:Validatigeter for epidemiologic studies depresson scale for children.American Journal of Epidemiology,131(3),538-551.   
Flory,J.D.，&Yehuda,R.(215).Comorbiditybetweenpostraumaticstressdisorderandmajordepresivedisorder:Alteative explanations and treatment considerations.Dialogues in clinical neuroscience,l7(2),141-150.   
Foa,E.B.,Johson,K.MFeny,N.C,&readwel,K.R.H. (l).ThechildDsymptomcale:Preliminaryexamintioofits psychometric properties.Journal of Clinical Child Psychology,30(3),376-384.   
Foa,E.B.,Stein,D.J,&McFarlane,A.C.(O6).Symptomatologyandpsychopathologyofmentalhealthproblemsafterdisaste JournalofClinical Psychiatry,67,5-25.   
Fried,E.I,ofos-,gC.)b and generalizabilityof postraumatic stress disorder (PTSD)networks: Across-cultural multisite studyof PTSD symptoms in four trauma patient samples. Clinical Psychological Science,6(3),335-351.   
Fruchterman,T.J,eingold,..(99).Gahawingbyfo-dietedplacent.oftware:racticendExperice), 1129-1164.   
Garabiles,M.R,Lao,C.K.,Wang,S.，&HallB.J.(O2).Tenetworkstructureofposraumaticstressdisorderamongflipina migrant domestic workers: Comorbiditywith depresion.European Journalof sychotraumatology,(1),765544.   
Geng,F.L.,Ling,Y.X,i,Y.ang,Y,am,.S.,LiuX.C,&Fan,F.(9).idirectioaoatosbetweeio postraumatic stress disorder,and depresivesymptoms among adolescent earthquake survivors: A longitudinal multiwave cohort study. Sleep,42(11),zsz162.   
Gilbar,O.(2020).Examining theboundaries between ICD-1PTSD/CPSDand depresionand anxietysymptoms:Anetwok analysis perspective. Journal of Affctive Disorders,262,429-439.   
Gootzeit,J,o,K.(l).ctsf:asiiideeaeatscaloev(), 993-1003.   
Gotlib,IH.,Lewinsohn,P.M,&leyJ.R.(995).Symptomsverssaiagnosisofdepresson:dierencsinpscosocial functioning.Journal of Consulting and Clinical Psychology,63(1),90-100.   
Gros,D.F,mms,L.J,&Acieo,R.().SpeciicityofostramaticStress Disodersmtoaninvestigatioofoobiity between Postraumatic Stress Disorder symptoms and depression in treatment-seeking veterans.Journal of Nervous and Mental Disease,198(12),885-890.   
Grubaugh,A.L,Long,M.E.,Ehai,J.D.Frueh,B.C.&Magruder,K..(2olo).Anexaminationoftheconstructvalidityof posttraumaticstress disorderwithveteransusingarevised criterionset.BehaviourResearchandTherapy48(9),909-914.   
Heeren,A.,Bestein,EE,&Naly.J.(8).ecosructigtraitaiety:twkrspctiveAnietyresdoing 31(3),262-276.   
Horowitz, M.J. (1976). Stress Response Syndromes. New York: Aronson.   
Janoff-Bulman,R.(989).Assmptivorldsndthestresoftaumaticevets:Aplicatiosoftheheacostructocialogitio 7(2), 113-1136.   
Jones,P.J.,Ma,R.&McNallyR.J.(019).BridgeCentrality:ANetworkApproachtoUnderstandingComorbidityMultivariate Behavioral Research,1-15.   
Krueger,R.F.(1999).The structure of common mental disorders.Archivesof General Psychiatry,56(10),921-926.   
Lazarov,A.uare-JimenzB.,Levi.,CopersithD..LubiGie,D..riaY.().Symptoucreo PTSD and co-morbid depresive symptoms -anetwork analysis of combatveteranpatients.Psychological Medicine,50(13), 2154-2170.   
Levinson,C..roso.Caula,isnCJosdebagh.LdezK.C).Sot eatingdisordercomorbidityandunderlyingvulnerabilities:Usingnetwork analysistoconceptualize comorbidity. International Journalof Eating Disorders,51(7),693-709.   
McNally,R.J,air,ugo,B.L,&ea,BC.().Cobidbsiveopsivesoderaddepresio:si network approach.Psychological Medicine,47(7),1204-1214.   
Meis,L.A.,Erbes,C.R.Kaler,.E,Arbisi,P.A.,&olusyM.A. ()ThestructurefDamongtwocoortsoftuing soldiers: Before,during,and folowing deployment to Iraq.Journal ofAbnormal Psychology,l2o(4),807-818.   
Mitchell,K.S.WolE.JBovin.J,L.O.Green,J.DosenR.CarxB.P.(7).Netwkmodes posttraumatic stress disorder: Implications for ICD-11.JournalofAbnormal Psychology,I26(3),355-366.   
Podsakoff,P..,acKenzie,..L,J.Y,&Podsakof,N.P.(Oo3).Commometodbiasesinbehavioraresearch:Ariical review of the literature and recommended remedies.Journal of Applied Psychology,88(5),879-903.   
Price,M.,Legrand,A.C.Brier,Z..F,&Hebert-Dufresne,L.(O19).Thesymptomsatthecenter:Examiingthecomorbidityf posttraumatic stress disorder,generalized anxietydisorder,anddepresion with network analysis.JourmalofPsychiatric Research,109,52-58.   
Reichardt,J.,&Bormholdt,S.(2oo6).Statistical mechanicsof communitydetection.Physical Review E,74(1),14.   
Robinaugh,D.il,.,&Nall.J(6).entifngiglfutialodesinhompcatedrifetoJol of Abnormal Psychology,125(6),747-757.   
Scutari,M.(2O10).Learming Bayesian Networks with thebnlearnRPackage.Journalof Statistical Software,35(3),-22.   
Scutari,M.,&Nagarajan,R.(l3).entifyingsigniicantedgesigrapicalmodelsofolecularetworks.AtificialIteligncein Medicine,57(3),207-217.   
Simms,L.J.,Watso,D.&Dobbeling,B.N.(o).Confimatoryfactoraalysesofpostraumaticstresssmptomsineplodand nondeployed veterans of the Gulf War.Journal of Abnormal Psychology,Ill(4),637-647.   
Spitzer,R.L.rst..,Wakeeld,J.C.().vingfroitselfi-VJoualfietysoders1()4.   
Tang,W.J.,LuY&uJP().osrticrssoderietydepioooletake victims:Comorbidityandassociated sleep-disturbing factors.Social PsychiatryandPsychiatric Epidemiology，53(11), 1241-1251.   
vanBorkulo,C.,oschloLKoskoki,JoP.,Lhoeves,R,orsboo,D&Waldop,L.).ag network structures on three aspects: A permutation test. (Preprint).doi:10.13140/RG.2.2.29455.38569   
Wang,Y,Shi,H.S.,Liu,W.H,Zheng,H,Wong,K.K.,Cheung,E.FC.,&Chan,R.C.K.(02).Applying networkanalyisto investigate thelinksbetwee dimensionalschizotypyandcognitiveandaffectiveempathyJournalofAfectiveDisorders，277, 313-321.   
Yarkoni,T.,&Westfall,J.().oigpdictiooepatiishogy:Lssfomaceagse Psychological Science,12(6),1100-1122.   
Ying,L.H.Wu,X.C.,Lin,C.D.,&Chen,C..(2l3).Prevalenceadpredictorsofpostraumaticstressdisorderanddepesie symptomsamong child survivors1year following the Wenchuan earthquake in China.European Child& Adolescent Psychiatry,22(9),567-575.   
Zhen,R.,Zhou,X,&Wu,X.C.(0l9).PattemsofPostraumatic StressDisorderand DepresionAmongAdolescentsFollowingan Earthquake:aLatent Profile Analysis.Child Indicators Research,12(6),2173-2187.   
Zhou,X.,&Wu,X.C.(2Ol9).TemporalTransitions inPattesofPostraumaticSressisorderandDepressonAmongAdolescents Following the Wenchuan Earthquake.Child Psychiatry and Human Development,50(3),494-504.

# Co-morbidity patterns of posttraumatic stress disorder and depressive symptoms: A network analysis of post-earthquake children and adolescent:

WANG Wenchao1,YUANHao²1,WU Xinchun1   
(l Beijing Key Laboratory of Applied Experimental Psychology; National Demonstration Center   
for Experimental Psychology Education (Beijing Normal University); Faculty of Psychology, Beijing Normal University, Beijing 1Oo875,China) ( Pingshan Foreign Languages School, Shenzhen 518118, China)

# Abstract

Post-traumatic stress disorder (PTSD) and depression have high rates of co-morbidity among children and adolescents who have experienced a major natural disaster. Some researchers have suggested that overlapping symptoms and dysphoria symptoms of PTSD contribute to co-morbidity, while others have attempted to explain the co-morbidity through a causal relationship between them.However, most of these studies have been based on the hypothesis of common causes, explaining co-morbidity at level of disorders or dimensions, while few studies have investigated patterns of the co-morbidity from the perspective of symptoms.

The Child PTSD Symptoms Scale (CPSS) and Center for Epidemiologic Studies Depression Scale for Children (CES-DC) were administered to two samples of children and adolescent one year after the earthquake (Wenchuan earthquake, $N = 2 5 3 0$ $4 7 . 0 \%$ males, $M _ { a g e } = 1 2 . 8 6$ $S D = 1 . 9 6$ Ya'an earthquake, $N = 7 2 3 , 4 7 . 7 \%$ males, $M _ { a g e } = 1 3 . 4 0$ $S D = 2 . 2 9$ ). Gaussian graphical models (GGM) and Bayesian hill climbing algorithms were used to describe patterns of the co-morbidity between PTSD and depression.

Overlapping symptoms and emotional numbness were the bridging symptoms. Detachment and future-limited symptoms were bridge symptoms in DSM-IV, were not bridge symptoms in the absence of DSM-IV,and fear, startle response and hypervigilance symptom were bridge symptoms. DSM-IV inaccurately defines the boundaries of PTSD, while intrusion and avoidance symptoms are core symptoms of PTSD.Depressive symptoms were more likely to trigger PTSD symptoms, while intrusive symptoms triggered avoidance symptoms.

The above findings were cross-validated in both Wenchuan and Ya'an samples,enhancing the generalizability of the findings and responding to the reproducibility crisis of psychological research.This enlightens clinical practitioners to prioritize the identification of bridging symptoms in the early assessment of clients who have suffered from traumatic events,in order to screen out clients at high-risk of co-morbid with depression.Secondly,the bridge symptoms should also be used as a breakthrough in the intervention process to develop intervention strategies. Finally, during the prognostic process, special attention should be paid to the recurrence of bridging symptoms to prevent the re-emergence of co-morbidity.

Key words:PTSD,depression, network analysis,children and adolescents注：红线表示样本边权重的估计值，黑线表示1000次BootStrap 得到的边权重均值，灰色区域表示 $9 5 \% \mathrm { C I }$ ，左侧为汶川样本各边权重的 $9 5 \% C \mathrm { I }$ ，右侧为雅安样本各边权重的 $9 5 \% C$

附录：  
附表1各题项的基本信息  

<html><body><table><tr><td>标签</td><td>缩写</td><td>题项</td><td>量表</td></tr><tr><td>B1</td><td>噩梦</td><td>会做噩梦</td><td>CPSS</td></tr><tr><td>B2</td><td>想法侵入</td><td>和地震有关的令人难过的想法或画面，会突然闯进我的脑海中</td><td>CPSS</td></tr><tr><td>B3</td><td>情感反应</td><td>当我想起或听别人说到地震的时候，会感到难过</td><td>CPSS</td></tr><tr><td>B4</td><td>闪回</td><td>我的行为或情绪反应好像不断经历地震一样</td><td>CPSS</td></tr><tr><td>B5</td><td>生理反应</td><td>当我想起或听别人说到地震的时候，会有一些身体上的反应</td><td>CPSS</td></tr><tr><td>C1</td><td>兴趣减退</td><td>对过去经常做的事明显失去兴趣</td><td>CPSS</td></tr><tr><td>C2</td><td>未来受限</td><td>感觉我未来的计划或希望不会实现</td><td>CPSS</td></tr><tr><td>C3</td><td>回避线索</td><td>试图躲避那些会让我想起地震的活动、人物或地点</td><td>CPSS</td></tr><tr><td>C4</td><td>情绪麻木</td><td>情绪麻木(比如，哭不出来，或高兴不起来)</td><td>CPSS</td></tr><tr><td>C5</td><td>失忆</td><td>无法记起这次地震的一些重要经历</td><td>CPSS</td></tr><tr><td>C6</td><td>疏离</td><td>感觉与周围的人亲近不起来</td><td>CPSS</td></tr><tr><td>C7</td><td>回避想法</td><td>试图不去回忆、谈论或感受地震这件事</td><td>CPSS</td></tr><tr><td>D1</td><td>注意力问题_D</td><td>很难集中注意力</td><td>CPSS</td></tr><tr><td>D2</td><td>睡眠问题_D</td><td>很难入睡或容易惊醒</td><td>CPSS</td></tr><tr><td>D3</td><td>惊跳反应</td><td>感觉紧张或很容易受到惊吓</td><td>CPSS</td></tr><tr><td>D4</td><td>高警觉</td><td>过分警觉</td><td>CPSS</td></tr><tr><td>D5</td><td>烦躁易怒</td><td>感觉焦躁不安或容易发火</td><td>CPSS</td></tr><tr><td>A1</td><td>感到困扰</td><td>我为一些以前并没有困扰我的事而觉得困扰</td><td>CES-DC</td></tr><tr><td>A2</td><td>食欲不振</td><td>我不想吃东西，也不怎么觉得饿</td><td>CES-DC</td></tr><tr><td>A3</td><td>外部支持无用</td><td>即使家人和朋友努力使我好受点，我也无法快乐起来</td><td>CES-DC</td></tr><tr><td>A4</td><td>自我认可</td><td>我觉得我和其他孩子一样好</td><td>CES-DC</td></tr><tr><td>A5</td><td>注意力问题_A</td><td>我觉得我无法集中精力做事</td><td>CES-DC</td></tr><tr><td>A6</td><td>情绪低落</td><td>我觉得情绪低落不开心</td><td>CES-DC</td></tr><tr><td>A7</td><td>精疲力竭</td><td>我觉得太累了，不能做事情了</td><td>CES-DC</td></tr><tr><td>A8</td><td>乐观</td><td>我觉得有好事要发生</td><td>CES-DC</td></tr><tr><td>A9</td><td>挫败无用</td><td>我觉得自己以前做的事没有起作用</td><td>CES-DC</td></tr><tr><td>A10</td><td>恐惧</td><td>我觉得恐惧</td><td>CES-DC</td></tr><tr><td>A11</td><td>睡眠问题_A</td><td>我睡得没有以前好</td><td>CES-DC</td></tr><tr><td>A12</td><td>开心</td><td>我觉得开心</td><td>CES-DC</td></tr><tr><td>A13</td><td>活力降低</td><td>我比以前安静多了</td><td>CES-DC</td></tr><tr><td>A14</td><td>孤独</td><td>我觉得孤独，好像我没有任何朋友似的</td><td>CES-DC</td></tr><tr><td>A15</td><td>被排斥</td><td>我觉得我认识的小孩对我不友好，他们不想和我在一起</td><td>CES-DC</td></tr><tr><td>A16</td><td>享受生活</td><td>我过得很好</td><td>CES-DC</td></tr><tr><td>A17</td><td>哭泣</td><td>我想哭</td><td>CES-DC</td></tr><tr><td>A18</td><td>悲伤</td><td>我觉得悲伤</td><td>CES-DC</td></tr><tr><td>A19</td><td>不被喜爱</td><td>我觉得人们不喜欢我</td><td>CES-DC</td></tr><tr><td>A20</td><td>难以开始</td><td>对我来说，很难开始着手做一些事情</td><td>CES-DC</td></tr></table></body></html>

附表2各题项的描述性统计结果  

<html><body><table><tr><td>题项</td><td colspan="4">汶川</td><td colspan="4">雅安</td></tr><tr><td>标签</td><td>平均数</td><td>标准差</td><td>偏度</td><td>峰度</td><td>平均数</td><td>标准差</td><td>偏度</td><td>峰度</td></tr><tr><td>B1</td><td>0.80</td><td>0.74</td><td>0.78</td><td>0.55</td><td>0.84</td><td>0.77</td><td>0.85</td><td>0.69</td></tr><tr><td>B2</td><td>0.98</td><td>0.85</td><td>0.61</td><td>-0.22</td><td>0.80</td><td>0.81</td><td>0.93</td><td>0.49</td></tr><tr><td>B3</td><td>1.19</td><td>0.90</td><td>0.37</td><td>-0.62</td><td>0.88</td><td>0.87</td><td>0.83</td><td>0.07</td></tr><tr><td>B4</td><td>0.82</td><td>0.83</td><td>0.83</td><td>0.10</td><td>0.71</td><td>0.79</td><td>0.90</td><td>0.16</td></tr><tr><td>B5</td><td>0.68</td><td>0.82</td><td>1.04</td><td>0.42</td><td>0.63</td><td>0.82</td><td>1.24</td><td>0.88</td></tr><tr><td>C1</td><td>0.84</td><td>0.67</td><td>0.68</td><td>1.17</td><td>0.86</td><td>0.73</td><td>0.73</td><td>0.68</td></tr><tr><td>C2</td><td>0.50</td><td>0.75</td><td>1.47</td><td>1.60</td><td>0.74</td><td>0.86</td><td>1.00</td><td>0.23</td></tr><tr><td>C3</td><td>0.79</td><td>0.83</td><td>0.85</td><td>0.08</td><td>0.66</td><td>0.83</td><td>1.09</td><td>0.37</td></tr><tr><td>C4</td><td>0.72</td><td>0.81</td><td>0.94</td><td>0.24</td><td>0.66</td><td>0.85</td><td>1.20</td><td>0.71</td></tr><tr><td>C5</td><td>0.70</td><td>0.89</td><td>1.16</td><td>0.44</td><td>0.68</td><td>0.87</td><td>1.17</td><td>0.53</td></tr><tr><td>C6</td><td>0.67</td><td>0.85</td><td>1.16</td><td>0.58</td><td>0.69</td><td>0.81</td><td>1.03</td><td>0.40</td></tr><tr><td>C7</td><td>0.86</td><td>0.86</td><td>0.80</td><td>-0.01</td><td>0.80</td><td>0.95</td><td>1.03</td><td>0.05</td></tr><tr><td>D1</td><td>1.05</td><td>0.85</td><td>0.60</td><td>-0.15</td><td>1.24</td><td>0.92</td><td>0.43</td><td>-0.59</td></tr><tr><td>D2</td><td>0.80</td><td>0.82</td><td>0.83</td><td>0.09</td><td>0.79</td><td>0.85</td><td>0.92</td><td>0.23</td></tr><tr><td>D3</td><td>0.95</td><td>0.83</td><td>0.69</td><td>0.00</td><td>0.92</td><td>0.87</td><td>0.73</td><td>-0.11</td></tr><tr><td>D4</td><td>0.78</td><td>0.85</td><td>0.89</td><td>0.09</td><td>0.87</td><td>0.91</td><td>0.83</td><td>-0.17</td></tr><tr><td>D5</td><td>0.98</td><td>0.90</td><td>0.62</td><td>-0.43</td><td>1.10</td><td>0.91</td><td>0.52</td><td>-0.51</td></tr><tr><td>A1</td><td>0.77</td><td>0.70</td><td>0.68</td><td>0.44</td><td>0.82</td><td>0.75</td><td>0.66</td><td>0.12</td></tr><tr><td>A2</td><td>0.83</td><td>0.85</td><td>0.85</td><td>0.09</td><td>0.85</td><td>0.86</td><td>0.74</td><td>-0.24</td></tr><tr><td>A3</td><td>0.53</td><td>0.76</td><td>1.44</td><td>1.60</td><td>0.47</td><td>0.72</td><td>1.60</td><td>2.25</td></tr><tr><td>A5</td><td>1.00</td><td>0.93</td><td>0.66</td><td>-0.44</td><td>1.11</td><td>0.94</td><td>0.57</td><td>-0.52</td></tr><tr><td>A6</td><td>0.90</td><td>0.85</td><td>0.71</td><td>-0.13</td><td>0.92</td><td>0.87</td><td>0.77</td><td>-0.02</td></tr><tr><td>A7</td><td>0.83</td><td>0.89</td><td>0.86</td><td>-0.07</td><td>0.87</td><td>0.94</td><td>0.83</td><td>-0.29</td></tr><tr><td>A9</td><td>0.74</td><td>0.83</td><td>0.96</td><td>0.28</td><td>0.85</td><td>0.89</td><td>0.87</td><td>0.02</td></tr><tr><td>A10</td><td>0.78</td><td>0.89</td><td>0.96</td><td>0.08</td><td>0.76</td><td>0.90</td><td>1.09</td><td>0.37</td></tr><tr><td>A11</td><td>0.95</td><td>0.97</td><td>0.69</td><td>-0.59</td><td>0.91</td><td>1.04</td><td>0.82</td><td>-0.63</td></tr><tr><td>A13</td><td>1.11</td><td>0.96</td><td>0.42</td><td>-0.82</td><td>1.23</td><td>1.00</td><td>0.34</td><td>-0.95</td></tr><tr><td>A14</td><td>0.76</td><td>0.94</td><td>1.05</td><td>0.08</td><td>0.76</td><td>0.96</td><td>1.07</td><td>0.06</td></tr><tr><td>A15</td><td>0.68</td><td>0.88</td><td>1.17</td><td>0.50</td><td>0.77</td><td>0.91</td><td>1.02</td><td>0.13</td></tr><tr><td>A17</td><td>0.92</td><td>0.94</td><td>0.79</td><td>-0.30</td><td>0.88</td><td>0.94</td><td>0.88</td><td>-0.16</td></tr><tr><td>A18</td><td>0.92</td><td>0.90</td><td>0.76</td><td>-0.19</td><td>0.91</td><td>0.93</td><td>0.84</td><td>-0.15</td></tr><tr><td>A19</td><td>0.71</td><td>0.88</td><td>1.13</td><td>0.43</td><td>0.81</td><td>0.91</td><td>1.03</td><td>0.27</td></tr><tr><td>A20</td><td>0.80</td><td>0.86</td><td>0.89</td><td>0.11</td><td>0.91</td><td>0.92</td><td>0.82</td><td>-0.17</td></tr><tr><td>A4</td><td>1.51</td><td>1.09</td><td>0.02</td><td>-1.29</td><td>1.59</td><td>1.07</td><td>-0.08</td><td>-1.24</td></tr><tr><td>A8</td><td>0.89</td><td>0.89</td><td>0.83</td><td>-0.02</td><td>1.03</td><td>0.90</td><td>0.63</td><td>-0.34</td></tr><tr><td>A12</td><td>1.46</td><td>0.98</td><td>0.06</td><td>-1.01</td><td>1.61</td><td>0.99</td><td>-0.11</td><td>-1.02</td></tr><tr><td>A16</td><td>1.58</td><td>1.04</td><td>-0.10</td><td>-1.17</td><td>1.73</td><td>1.01</td><td>-0.20</td><td>-1.09</td></tr></table></body></html>

附表4汶川网络1中各边权重  

<html><body><table><tr><td>B2</td><td>B3 B4 B10.0940.0360.0100.0350.000-0.0090.0500.0000.002-0.035</td><td>B5 C1</td><td>C2</td><td></td><td></td><td>C4 C5</td><td>C6</td><td>C7</td><td>D1 0.078 0.000</td><td>D2</td><td>0.175</td><td>D3 D4</td><td>D5</td><td>A1 A2 0.0750.0010.0340.0000.022</td><td>A3 A5 A6 A7 0.007 -0.0030.0020.000</td><td>A9 A10</td><td>A13 0.0000.1370.0540.0000.000</td><td>A15 0.025</td><td>A17 0.000</td><td>0.000</td><td>A19</td><td>A20 0.005-0.0180.0000.0160.0040.000</td><td>A4</td><td>A8</td></tr><tr><td>B2 B3</td><td>0.1720.1710.0570.0000.0090.1280.0310.000-0.0110.076</td><td></td><td>0.1010.1730.0180.000</td><td></td><td></td><td>0.0890.038-0.006-0.055</td><td></td><td>0.053</td><td>0.032 0.000</td><td>0.010</td><td></td><td>0.0580.000</td><td>0.002</td><td>0.051 0.043</td><td>0.000 0.000</td><td>0.00006806010007001000000706100080000080000 0.000 0.000 0.000 0.052</td><td>0.000 0.020-0.013</td><td>0.018</td><td>0.056</td><td>0.073</td><td>-0.009</td><td>0.000</td><td>0.017-0.003</td><td>0.000</td></tr><tr><td>B4</td><td></td><td></td><td>0.0000.000</td><td>0.1570.0000.0050.0820.0690.0390.0000.011</td><td>0.095</td><td>0.042 0.025</td><td>-0.001</td><td>0.059</td><td>0.000 0.010</td><td>0.000 0.015</td><td>0.006</td><td>0.0740.045 0.052</td><td>0.000 0.000</td><td>0.0420.015 0.015 0.006</td><td>0.000 0.0000.0000.000 0.018 0.000 0.009</td><td>0.0220.064 0.012 0.000 0.103</td><td>0.0130.000-0.011 0.022 0.018 -0.002</td><td></td><td>0.0140.0070.000 0.000</td><td>0.000 0.000</td><td>0.006 0.005 0.008</td><td>.023</td><td>0.0150.000 0.026</td><td>0.016 0.0210.000 0.000-0.004</td></tr><tr><td>B5 C</td><td></td><td></td><td></td><td>0.050</td><td>0.0690.0290.0150.061</td><td>0.0010.0010.0110.109-0.011</td><td></td><td>0.049</td><td>0.073 0.083</td><td>0.066 0.032</td><td>0.013 0.0460.021</td><td>0.006</td><td>0.024 0.017</td><td>0.047 0.010</td><td>0.006 0.0240.047 0.0500.0000.0000.0330.0000.063</td><td>0.016 0.0400.000</td><td>0.000 0.0360.000 0.0670.0000.0000.0000.031</td><td>0.000</td><td>0.000-0.0120.000</td><td></td><td>0.000 0.058</td><td>0.041</td><td>0.0800.0000.004-0.0140.025</td><td>0.000 0.0120.000</td></tr><tr><td>C3 C2</td><td></td><td></td><td></td><td></td><td></td><td>0.0150.0080.000 0.0230.0620.003</td><td></td><td>0.143</td><td>0.000 0.020 0.061</td><td>0.0700.0220.040</td><td>0.0170.048</td><td></td><td>-0.019 0.051</td><td>0.000-0.0030.017-0.026 0.0030.023</td><td>0.000 0.128 0.0000.0570.045</td><td>0.000 0.0000.018 0.003 0.0140.0110.0100.0260.027</td><td>0.0000.000</td><td>0.000</td><td>0.003 0.0090.0190.053</td><td>0.010</td><td>0.000 0.000</td><td>0.000 0.028</td><td>0.0050.007 0.0000.000</td><td>0.000 0.000 0.000-0.011</td></tr><tr><td>C4 C5</td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.069</td><td>0.055</td><td>0.002 0.000 0.0000.0210.009</td><td></td><td>-0.016 0.0230.024</td><td>0.037</td><td>0.036 0.150</td><td>0.010 0.010 0.003 0.000</td><td>0.048 0.000 0.000 0.024 0.058 0.0120.0450.045</td><td>0.000 0.039 0.005 0.042-0.034 0.018</td><td>0.014 0.000 0.0370.141</td><td>0.031 0.004 0.066</td><td>0.000 0.001</td><td>0.036 0.11</td><td>0.000 0.065</td><td>0.056</td><td>0.009 -0.001 0.000</td><td>0.015 0.0090.000 0.007</td></tr><tr><td>C6 C7 D1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0190.0000.0000.0480.000 0.1090.0130.0000.043</td><td></td><td></td><td></td><td>0.010</td><td>0.0000.041 0.000</td><td>0.055 -0.005-0.004 0.000 0.000 0.2950.029 0.003</td><td>0.0460.0030.0000.006-0.007 0.055 0.010 0.000</td><td>0.0000.000</td><td>0.0000.000-0.0020.0000.0200.0000.020 0.000 0.000</td><td>0.000</td><td></td><td>0.000</td><td>0.039</td><td>0.000 0.000</td><td>0.000 0.032 0.033 0.000</td></tr><tr><td>D2 D3</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.099</td><td></td><td>0.102 0.029</td><td>0.009 0.000</td><td>0.0470.0470.0040.000.0420.0000.0510.0000.000 0.011 0.033 0.011</td><td>0.0000.0170.220 0.003 0.108 0.000 0.009</td><td>0.0000.010 0.003</td><td>0.0120.0000.000 0.004 0.030</td><td>0.000</td><td></td><td>-0.019 0.032</td><td>0.019</td><td>0.0400.000-0.002 0.047 0.012</td><td>0.0000.000 0.0060.000</td></tr><tr><td>D4 D5</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0760.0610.001 0.026</td><td>-0.002-0.001 0.000 0.0730.0430.0000.0960.0450.062</td><td>0.0340.061 0.006 0.0000.018 0.0000.0000.002</td><td>0.0140.000 0.000</td><td>0.000 0.0000.0420.003</td><td>0.000</td><td>0.000</td><td>0.000 0.0400.007</td><td>0.000</td><td>0.072 0.0000.008</td><td>0.0040.000 0.0000.000</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0120.0140.065</td><td>0.074 0.034 0.0610.003 0.0860.0280.0660.054 0.0110.014</td><td>0.032 0.042 0.071 0.041</td><td>0.022 0.000 0.000 0.000</td><td>0.043 0.034</td><td>0.015 0.000</td><td>0.015 0.015</td><td>0.093 0.001</td><td>0.000</td><td>0.050 0.0000.012</td><td>0.000-0.002 0.0000.000</td></tr><tr><td>A3 A5</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.055 0.0890.062 0.047 0.016 0.1310.081 0.0360.000</td><td>0.049 0.005 0.037 -0.009</td><td>0.058 0.000 0.031 0.000</td><td>0.000 0.000</td><td>0.051 0.004</td><td>0.00</td><td>0.026 0.0000.123</td><td>0.036</td><td>0.000 0.010-0.004</td><td>0.054-0.019 0.000-0.014</td></tr><tr><td>A6</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.1400.0200.0240.017 0.0550.000</td><td>0.018 0.013</td><td>0.0290.059</td><td>0.0380.060 0.012</td><td></td><td>0.000</td><td>0.100</td><td></td><td>0.1110.0000.0140.0000.000</td><td>0.041-0.019</td></tr><tr><td>A7</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0860.025</td><td>0.011 0.000 0.0490.000</td><td>0.0180.000</td><td>0.014 0.005</td><td>0.097</td><td>0.073</td><td>-0.009 -0.012</td><td>0.060 0.033</td><td>0.005 0.000 0.0000.000</td></tr><tr><td>A10</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.122</td><td>-0.0140.032</td><td>0.009 0.038</td><td>0.099</td><td>0.002</td><td>0.033</td><td></td><td>0.024</td><td>0.0360.000</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0370.000</td><td></td><td>0.0420.0210.036</td><td>0.0480.0000.0170.0030.0000.0290.0250.015</td><td>0.0000.000</td><td></td><td>0.0000.018</td><td>0.000 -0.036 0.0880.126</td></tr><tr><td>A13 A14</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.2570.0440.097</td><td>0.135</td><td></td><td>0.002-0.0080.020</td><td></td><td>0.021-0.032</td></tr><tr><td>A15</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0140.0000.2560.025</td><td>0.0000.050</td><td></td><td>0.008-0.073</td></tr><tr><td>A17</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.4620.098</td><td>0.010 0.0850.0410.0000.015</td><td>0.017-0.023</td><td>0.037</td><td>0.0180.002 0.074-0.0430.0280.0000.006 0.000</td></tr><tr><td>A18 A19</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></table></body></html>

附表5雅安网络1中各边权重  

<html><body><table><tr><td>B1</td><td>B2 B3</td><td>B4 B5 C1 C2 0.0940.0110.0100.0350.000</td><td>C3 -0.009 0.0500.000</td><td>C4</td><td>0.000 0.000</td><td>C7 0.078</td><td></td><td>D2</td><td>0.075</td><td>D4</td><td>D5 A1 0.001 0.034</td><td>A2 A3 A5 0.000 0.022</td><td>A6 0.00 -0.003</td><td>A7 0.002 0.000</td><td>A10 0.000 0.137</td><td>0.054</td><td></td><td>A1</td><td>0.000 0.025</td><td>A1 A18 0.00</td><td></td><td>A19</td><td>0.0070.005-0.0180.000</td><td>A20</td><td></td><td>A8</td><td>0.039</td><td></td><td></td><td>A12 0.000</td><td></td><td>0.0160.0000.000</td><td>0.0000.000</td><td></td><td>A16 0.000</td><td></td><td>0.0280.000</td></tr><tr><td>B2</td><td></td><td>0.1720.1710.0570.000-0.0070.1280.031 0.1010.1740.018</td><td></td><td></td><td>0.000 -0.011</td><td></td><td>0.076</td><td>.000</td><td>0.000</td><td>0.068</td><td>0.061</td><td></td><td>0.01 0.000</td><td>0.007</td><td></td><td></td><td>0.000</td><td></td><td>0.070</td><td>0.026</td><td></td><td></td><td>0.000</td><td></td><td></td><td>0.004</td><td></td><td></td><td>0.0200.009</td><td>-0.005 0.00</td><td>0.000</td><td></td><td></td><td></td><td></td></tr><tr><td>B4 B5 B3</td><td></td><td>0.1570.000 0.0000.0000.095 0.005</td><td></td><td>0.062 0.042</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.00</td><td></td><td>0.009</td><td></td><td>0.041</td><td></td><td></td><td></td><td></td><td>0.000-0.004 0.0000.000-0.0120.000</td></tr><tr><td>C1 C2</td><td></td><td></td><td>0.0500.0690.029 0.0010.001</td><td></td><td>0.004 0.014</td><td>0.061 0.109</td><td>0.045</td><td>0.073 0.083</td><td>0.059</td><td></td><td>0.013</td><td></td><td></td><td></td><td>0.047</td><td>0.010 0.016</td><td>0.053</td><td>0.047</td><td>0.016 0.040</td><td></td><td></td><td></td><td></td><td>0.000 0.027</td><td></td><td></td><td></td><td></td><td>0.0100.000</td><td>0.000</td><td></td><td></td><td></td><td>0.000 -0.005</td><td>-0.004-0.014-0.031 0.0070.0000.000</td><td></td><td></td></tr><tr><td>C3 C4</td><td></td><td></td><td></td><td>0.015</td><td>0.000</td><td>0.000 0.0230.0620.003</td><td></td><td></td><td>0.000 0.061</td><td>0.020 0.070</td><td>0.017 0.022</td><td></td><td></td><td>0.019</td><td>0.000</td><td>0.003 0.128</td><td>0.017</td><td>0.000 0.057</td><td></td><td></td><td>0.027</td><td>0.010 0.003</td><td>0.060 0.009</td><td></td><td>0.000</td><td>0.031-0.00</td><td></td><td></td><td>0.001 0.002</td><td>0.000 0.118</td><td>0.0360.0000.056</td><td>0.028</td><td>0.000</td><td>0.000</td><td></td><td></td><td>0.0000.000-0.011 0.0000.0000.000 0.000-0.00-0.015 0.0000.000</td></tr><tr><td>C5 C6</td><td></td><td></td><td></td><td></td><td></td><td>0.0210.055</td><td>0.000</td><td></td><td>0.002 0.021</td><td>0.000 0.009</td><td>0.001 0.023</td><td></td><td>0.020</td><td></td><td>0.010 0.003</td><td>0.000 0.058 0.010</td><td>0.048</td><td>0.000 0.012</td><td>0.0000.024</td><td>0.014</td><td>0.039 0.034</td><td>0.018</td><td></td><td>0.037</td><td>0.007</td><td></td><td>0.000</td><td>0.000</td><td></td><td></td><td>0.000</td><td>0.052 0.02</td><td></td><td>0.001 0.000</td><td></td><td>0.020 0.028</td><td>-0.033</td></tr><tr><td>C7 D1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.000</td><td>0.000 0.060</td><td>0.000 0.013</td><td></td><td>0.048 0.000</td><td>0.000</td><td>0.000 0.010</td><td></td><td>0.05 0.005</td><td></td><td>0.000</td><td>0.01</td><td>0.003</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>-0.002</td><td></td><td></td><td>0.000 0.0000.000</td></tr><tr><td>D2 D3</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.047</td><td></td><td>0.047</td><td>0.004</td><td>0.000</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.003</td><td>0.000 0.000 0.000</td></tr><tr><td>D4 D5</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.076</td><td>0.045</td><td>0.001 0.026</td><td>0.002</td><td>0.000</td><td></td><td>0.018</td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.042</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.008</td><td></td><td></td><td>0.0000.000 0.000-0.002</td></tr><tr><td>A1 A2</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0420.043</td><td>0.000 0.012</td><td>0.096 0.042 0.065</td><td>0.045 0.074</td><td>0.062 0.034</td><td>0.061 0.003</td><td></td><td>0.032</td><td>04</td><td></td><td></td><td></td><td>0.043</td><td>0.033</td><td>0.000</td><td>0.015 0.015</td><td></td><td></td><td></td><td></td><td>0.000 0.012</td><td>0.000</td><td></td><td>0.0000.000</td></tr><tr><td>A3</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.0860.028</td><td>0.066</td><td>0.054 0.062</td><td>0.0110.014 0.0470.016</td><td>0.071</td><td></td><td></td><td></td><td></td><td></td><td>0.000</td><td></td><td></td><td></td><td></td><td></td><td>0.036</td><td></td><td></td><td>0.000</td><td></td><td>-0.054-0.019</td></tr><tr><td>A5 A6</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.1310.081</td><td></td><td>0.0470.000</td><td>0.031 0.0200.024</td><td>0.017</td><td>0.006 0.029</td><td>0.031 0.059</td><td></td><td>0.000 0.038</td><td>0.000 0.060</td><td></td><td>0.000</td><td>0.000 0.00</td><td></td><td></td><td></td><td></td><td>0.000 0.000</td><td>0.010-0.0040.000-0.014</td><td>0.056-0.0210.000</td><td>0.041-0.019</td></tr><tr><td>A7 A9</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></table></body></html>

附表3各网络中权重较大的边  

<html><body><table><tr><td></td><td colspan="2">PTSD子网络</td><td colspan="2">抑郁子网络</td><td colspan="2">PTSD 与抑郁的直连边</td></tr><tr><td></td><td>边</td><td>权重[95%CI]</td><td>边</td><td>权重[95%CI]</td><td>边</td><td>权重[95%CI]</td></tr><tr><td></td><td>B1-D2</td><td>0.18[0.12~0.20]</td><td>A17—A18</td><td>0.46[0.40~0.47]</td><td>A5-D1</td><td>0.29[0.24~0.32]</td></tr><tr><td>汶川网</td><td>B3-B5</td><td>0.17[0.11~0.19]</td><td>A14—A15</td><td>0.26[0.19~0.27]</td><td>D2-A11</td><td>0.22[0.16~0.24]</td></tr><tr><td>络1</td><td>B2-B3</td><td>0.17[0.14~0.21]</td><td>A15-A19</td><td>0.26[0.21~0.29]</td><td>C6-A14</td><td>0.14[0.10~0.17]</td></tr><tr><td></td><td>B2-B4</td><td>0.17[0.12~0.19]</td><td>A6-A7</td><td>0.14[0.09~0.17]</td><td>B1-A10</td><td>0.14[0.10~0.17]</td></tr><tr><td></td><td>B4-B5</td><td>0.16[0.12~0.20]</td><td>A14—A19</td><td>0.14[0.09~0.17]</td><td>C4-A3</td><td>0.13[0.08~0.16]</td></tr><tr><td></td><td>B1-D2</td><td>0.18[0.09~0.23]</td><td>A17—A18</td><td>0.46[0.37~0.49]</td><td>A5-D1</td><td>0.29[0.20~0.34]</td></tr><tr><td>雅安网</td><td>B3-B5</td><td>0.17[0.15~0.29]</td><td>A14—A15</td><td>0.26[0.21~0.36]</td><td>D2-A11</td><td>0.22[0.20~0.34]</td></tr><tr><td>络1</td><td>B2-B3</td><td>0.17[0.06~0.20]</td><td>A15-A19</td><td>0.26[0.15~0.28]</td><td>C6-A14</td><td>0.14[0.05~0.19]</td></tr><tr><td></td><td>B2-B4</td><td>0.17[0.11~0.25]</td><td>A6-A7</td><td>0.14[0.08~0.22]</td><td>B1-A10</td><td>0.14[0.04~0.17]</td></tr><tr><td></td><td>B4-B5</td><td>0.16[0.05~0.19]</td><td>A14—A19</td><td>0.14[0.10~0.23]</td><td>C4-A3</td><td>0.13[0.07~0.21]</td></tr><tr><td></td><td>B2-B3</td><td>0.17[0.14~0.21]</td><td>A17—A18</td><td>0.46[0.41~0.48]</td><td>A10—A18</td><td>0.11[0.07~0.14]</td></tr><tr><td>汶川网</td><td>B3-B5</td><td>0.17[0.11~0.19]</td><td>A14—A15</td><td>0.26[0.19~0.28]</td><td>A10-A9</td><td>0.09[0.06~0.13]</td></tr><tr><td>络2</td><td>B2-B4</td><td>0.17[0.12~0.19]</td><td>A15-A19</td><td>0.26[0.21~0.29]</td><td>B3-A18</td><td>0.07[0.04~0.11]</td></tr><tr><td></td><td>B1—A10</td><td>0.16[0.12~0.19]</td><td>A6-A7</td><td>0.16[0.11~0.19]</td><td>D4-A1</td><td>0.08[0.05~0.12]</td></tr><tr><td></td><td>B4-B5</td><td>0.16[0.12~0.20]</td><td>C6-A14</td><td>0.14[0.10~0.18]</td><td>C4-B4</td><td>0.07[0.04~0.11]</td></tr><tr><td></td><td>B3-B5</td><td>0.18[0.15~0.29]</td><td>A17—A18</td><td>0.46[0.37~0.49]</td><td>A10—A18</td><td>0.11[0.02~0.15]</td></tr><tr><td>雅安网</td><td>B2-B3</td><td>0.17[0.06~0.20]</td><td>A14—A15</td><td>0.26[0.21~0.36]</td><td>A10-A9</td><td>0.09[0.00~0.10]</td></tr><tr><td></td><td>B2-B4</td><td>0.17[0.11~0.26]</td><td>A15-A19</td><td>0.26[0.15~0.29]</td><td>B3-A18</td><td>0.07[0.00~0.08]</td></tr><tr><td>络2</td><td>B1-A10</td><td>0.16[0.06~0.19]</td><td>A6-A7</td><td>0.18[0.10~0.25]</td><td>C5-C7</td><td>0.06[0.00~0.14]</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>B4-B5</td><td>0.16[0.05~0.19]</td><td>A1-A20</td><td>0.16[0.11~0.25]</td><td>C7-A3</td><td>0.06[0.00~0.10]</td></tr></table></body></html>

附表6汶川样本随机抽样100次后网络比较的局部不变性显著情况   

<html><body><table><tr><td>项目</td><td>边/节点</td><td>显著次数</td></tr><tr><td>边权重</td><td></td><td></td></tr><tr><td></td><td>B4—C3</td><td>3</td></tr><tr><td></td><td>B1—C4</td><td>1</td></tr><tr><td></td><td>B2-D1</td><td>1</td></tr><tr><td></td><td>C7-D1</td><td>1</td></tr><tr><td></td><td>D1-D2</td><td>1</td></tr><tr><td></td><td>B5—D3</td><td>2</td></tr><tr><td></td><td>D4—A1</td><td>1</td></tr><tr><td></td><td>D5—A1</td><td>1</td></tr><tr><td></td><td>B3-A2</td><td>5</td></tr><tr><td></td><td>A1—A3</td><td>1</td></tr><tr><td></td><td>D1—A10</td><td>1</td></tr><tr><td></td><td>D2—A11</td><td>1</td></tr><tr><td></td><td>C4—A13</td><td>2</td></tr><tr><td></td><td>B2—A19</td><td>2</td></tr><tr><td></td><td>D1—A4</td><td>1</td></tr><tr><td></td><td>D3—A4</td><td>2</td></tr><tr><td></td><td>A10—A8</td><td>1</td></tr><tr><td>B4—A12</td><td></td><td>1</td></tr><tr><td>C5—A16</td><td></td><td>1</td></tr><tr><td>A13—A16</td><td></td><td>3</td></tr><tr><td></td><td>A18—A16</td><td>1</td></tr><tr><td>节点EI值</td><td></td><td></td></tr><tr><td></td><td>D1</td><td>3</td></tr><tr><td></td><td></td><td>3</td></tr><tr><td></td><td>A8</td><td></td></tr><tr><td></td><td>A12</td><td>2</td></tr><tr><td></td><td>A16</td><td>1</td></tr></table></body></html>

附表7子网络探测结果  

<html><body><table><tr><td>标签</td><td>缩写</td><td>汶川样本</td><td>雅安样本</td></tr><tr><td>B1</td><td>噩梦</td><td>1</td><td>1</td></tr><tr><td>B2</td><td>想法侵入</td><td>1</td><td>1</td></tr><tr><td>B3</td><td>情感反应</td><td>1</td><td>1</td></tr><tr><td>B4</td><td>闪回</td><td>1</td><td>1</td></tr><tr><td>B5</td><td>生理反应</td><td>1</td><td>1</td></tr><tr><td>C2</td><td>未来受限</td><td>2</td><td>2</td></tr><tr><td>C3</td><td>回避线索</td><td>1</td><td>1</td></tr><tr><td>C4</td><td>情绪麻木</td><td>2</td><td>2</td></tr><tr><td>C5</td><td>失忆</td><td>2</td><td>2</td></tr><tr><td>C6</td><td>疏离</td><td>2</td><td>2</td></tr><tr><td>C7</td><td>回避想法</td><td>1</td><td>1</td></tr><tr><td>D3</td><td>惊跳反应</td><td>1</td><td>1</td></tr><tr><td>D4</td><td>高警觉</td><td>1</td><td>1</td></tr><tr><td>A1</td><td>感到困扰</td><td>2</td><td>2</td></tr><tr><td>A2</td><td>食欲不振</td><td>2</td><td>2</td></tr><tr><td>A3</td><td>外部支持无用</td><td>2</td><td>2</td></tr><tr><td>A6</td><td>情绪低落</td><td>2</td><td>2</td></tr><tr><td>A7</td><td>精疲力竭</td><td>2</td><td>2</td></tr><tr><td>A9</td><td>挫败无用</td><td>2</td><td>2</td></tr><tr><td>A10</td><td>恐惧</td><td>1</td><td>1</td></tr><tr><td>A13</td><td>活力降低</td><td>2</td><td>2</td></tr><tr><td>A14</td><td>孤独</td><td>2</td><td>2</td></tr><tr><td>A15</td><td>被排斥</td><td>2</td><td>2</td></tr><tr><td>A17</td><td>哭泣</td><td>2</td><td>2</td></tr><tr><td>A18</td><td>悲伤</td><td>2</td><td>2</td></tr><tr><td>A19</td><td>不被喜爱</td><td>2</td><td>2</td></tr><tr><td>A20</td><td>难以开始</td><td>2</td><td>2</td></tr><tr><td>A4</td><td>自我认可</td><td>3</td><td>3</td></tr><tr><td>A8</td><td>乐观</td><td>3</td><td>3</td></tr><tr><td>A12</td><td>开心</td><td>3</td><td>3</td></tr><tr><td>A16</td><td>享受生活</td><td>3</td><td>3</td></tr><tr><td></td><td>频次</td><td>564</td><td>938</td></tr></table></body></html>

注：数字相同即代表处于一同个子网络中

![](images/2b35e6e93a2d4310dd129beaf34c06d415914d7a27a52c18f75c7f8ccb9e9f5e.jpg)  
附图1汶川样本和雅安样本的全症状网络

![](images/eea50efd82884790b51494beed1f631c4fa8dc4290eda718bc58fcaa061531bb.jpg)  
附图2汶川样本和雅安样本剔除重叠症状后的网络

![](images/d51be6cdc0e3406bf6092e8eeb21f02dc9a7db3b2a15ec91a3cbfd83e0aebc35.jpg)  
附图3汶川网络1和雅安网络1中各边权重的 $9 5 \% \mathrm { C I }$

![](images/47bdf636f822de26104e570e491bbbd36c9229af7ebb1a0bbef7f88c4d233ea2.jpg)  
附图4汶川网络1和雅安网络1的稳定性检验图

![](images/e3af0655076d59411e0b6631b122afbffacd5ba11c61a98aa21d047188551fbc.jpg)  
汶川网络1  
雅安网络1  
附图5汶川网络1和雅安网络1各边权重的差异性检验

![](images/3e54806501e4c066feac0976b65ef7af512047ef96f9c808c5173452c47970bf.jpg)  
附图6汶川网络1和雅安网络1各节点EI的差异性检验

![](images/158366aa325fc1db6e603f73156e30ac9e427868806f2d5d5f4b366cd42b81fb.jpg)

![](images/645dc85ea4a45b17f1689d93b99897712fe9968d4db1efb18be541f84c8f878c.jpg)  
附图7汶川网络1和雅安网络1各节点BEI的差异性检验

![](images/7ba3d9ac3941407a0b342be000c953d4fa79ad45286d2a4a9eff5e294f4d44b9.jpg)