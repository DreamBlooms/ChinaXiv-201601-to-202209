# 多项式加工树模型在社会心理学中的应用

刘媛媛¹丁一²彭凯平³胡传鹏31

（1武汉大学哲学学院心理学系武汉430072）（2湖北大学教育学院心理学系武汉430062）（清华大学社会科学学院心理学系北京100084)

摘要多项式加工树(multinomial processing tree,MPT)从理论模型出发，使用多项式模型来拟合行为数据并估计理论模型中各个加工过程发生的可能性。该模型能够有效分离和量化不同心理过程，广泛应用于社会认知研究之中，如刻板印象、道德判断等。本文首先介绍该模型的基本原理及其实现，并以道德判断为例说明其在社会心理学中的最新应用。最后，总结其对社会心理学研究的意义，即可以作为一种方法提高研究的效度和精度，具有较高的实用价值，并指出其潜在不足。

关键词多项式加工树模型模型分析社会认知道德判断

# 1引言

理解人类社会行为背后的心理机制，并使用理论或者计算模型来解释这些行为是心理学中的重要目标(Johnson, Hopwood, Cesario,& Pleskac,2017; Stanley & Adolphs,2013)。例如,双加工模型假设人们使用自动加工和控制加工两种过程对外界信息进行处理，并可以用来解释一系列社会行为，包括社会评估(如：Gawronski& Bodenhausen,2006)、道德判断(如：Greene,Morelli,Lowenberg,Nystrom,& Cohen,2008)等。尽管自动化加工与控制加工在理论上可以被区分(Bargh,1994)，但是如何量化它们对特定行为的贡献率仍是待探索的问题。

为检验行为内部的心理过程并对其进行量化，研究者引入建模的方法对数据进行分析，其中多项式加工树(multinomial processing tree,MPT)模型能够较好地对社会认知的行为数据进行拟合并且提供较好的理论解释，因此被广泛地应用。MPT模型假设人们在完成某一任务时存在两种或者多种认知加工过程，以此为前提构建模型并通过对行为数据的拟合来估计心理过程发生的可能性，从而推断行为背后的心理过程及它们的贡献率。这一方法首先应用于认知心理学的来源监测（source monitoring）研究，以分离不同来源的记忆以及猜测判断的比例(如：Bayen,Murmane,& Erdfelder,1996)。最近，MPT 模型被引入社会心理学，用于量化不同心理过程对行为的影响，成为研究社会认知的重要方法。本文将首先介绍 MPT模型的基本原理及其实现，然后以道德判断为例说明其在社会心理学领域中的应用，最后总结 MPT模型对社会心理学研究的意义及其潜在不足。

# 2多项式加工树模型的原理

多项式模型(multinomialmodel)较早应用于统计遗传学中，对遗传学数据进行分析(如：Elandt-Johnson,1971)。Riefer 和 Batchelder(1988)首先将多项式模型引入心理学领域，后续的心理学研究对该模型进行了进一步发展(Erdfelder etal.,2009)。目前，这类模型被统称为多项式加工树模型。

MPT模型可以通过行为数据结果来检验其中存在的心理过程，为此，研究者必须首先假定在完成某一任务时，从刺激输入到反应输出之间存在多个心理决策过程，这些过程及其结果形成一个棵“决策树”，代表了从输入到达输出的不同路径。不同的路径通过分支和节点组成。每个节点代表了一种中间结果，连接着节点之间的心理加工过程；而心理过程在整个任务中出现的可能性可以用模型参数来表示，因此这些分支称为参数支。与末端节点相连的分支称为终止分支，其连接行为输出。因此，对于每一个终止分支在某个任务中的概率，可以通过这一个分支中包含的参数支的概率乘积得到；而整个加工树的概率为所有终止分支的概率之和。这样每个终止分支都存在一个方程式，包括一个或多个参数的乘积或加和;整个决策树最终的概率为1。这种数据形式符合多项式分布的特点，可使用多项式对其进行求解。

以简单的新旧再认任务为例。在此任务中，被试先学习一系列项目（例如，词汇），然后将这些学习过的旧（目标）项目与新（干扰）项目混合呈现给被试，被试接受“是-否”再认测试，即需要判断目标和干扰刺激是否属于旧项目并做出回答。因此，对于每个被试，可以观察到两个离散数据样本：（1）对目标刺激的正确“是”回答和错误“否”回答的频数（即击中和漏报次数）；（2）对干扰刺激的错误“是”回答和正确“否”回答的频数（即虚报和正确拒斥次数），并可以由此得出击中率、漏报率、虚报率和正确拒斥率。

![](images/f2618c4815c3092f1244cade132856fe1698472f2e75b2827298cf0af0af244e.jpg)  
图1“新-旧”再认范式的MPT模型

注：图中最左的实线方框代表给被试呈现的刺激项目，最右实线方框代表被试的判断，方框后面的代数式表示每个终止分支（即被试的反应）发生的概率。中间的虚线方框代表被试潜在的心理过程。 $\boldsymbol { r }$ 表示在测试阶段中确认呈现的项目是旧项目的概率， $g$ 表示在测试阶段不确定项目的新旧时将项目猜测为目标（旧）项目的概率。

在图1新旧再认任务的模型图中(Swets,1961)，研究者假设在人们的再认判断中仅使用一个阈值，即“高阈值(high threshold)"策略：一旦某个刺激的信息超过该阈值，就确定其属于某个类别（如新，或者旧），即确定状态；如果低于该阈值，则项目进入再认不确定状态，按固定的概率进行猜测。在这种简单的模型中，再认阈值的设置是为了避免熟悉性和其它因素使新项目（干扰刺激）高于该阈值，所以新项目只能进入再认不确定状态，而旧项目两种状态都可以进入。我们用参数 $\boldsymbol { r }$ 代表再认确定状态中对目标刺激回答“是”的概率，用参数“g"表示再认不确定状态下的猜测为旧（即回答“是”）的概率。因此，最终对目标刺激的“是”反应有两种可能的路径：（1）再认确定状态中的正确回答，概率为 $\boldsymbol { r }$ ：（2）再认不确定状态中的猜测“是”回答，概率为 $( 1 - r ) \cdot g$ （见图1）。由于这两种路径是互斥的，它们的概率之和等于目标刺激的正确“是”回答概率。即，存在以下方程：

$$
p ( { } ^ { \mathfrak { e } } \mathrm { \cdot } \mathrm { h i t } ^ { \mathfrak { s } } ) = r + ( 1 - r ) \cdot g
$$

而对于干扰（新）刺激中的“是”反应，存在方程：

$$
p ( { } ^ { \mathfrak { s } \mathfrak { c } } \mathrm { f a l s e \ a l a r m } ^ { \mathfrak { s } } ) = g
$$

对于目标和新旧这两种刺激而言，其各种行为反应的概率和各为1：

$$
\begin{array} { r l } & { p ( \mathrm { T } ) = r + ( 1 - r ) \cdot g + ( 1 - r ) \cdot ( 1 - g ) = 1 } \\ & { p ( \mathrm { N } ) = g + ( 1 - g ) = 1 } \end{array}
$$

方程1-4确定了模型方程，其中方程1和2是基于两种基本的心理过程，即“阈上再认” $( r )$ 和“猜测” $( g )$ ，解释了击中率和虚报率。根据这些方程和样本数据，可以通过参数估计的方法来估计出参数 $\boldsymbol { r }$ 和 $g$ 的值(Read& Cressie,1988)。由于模型的参数数目与独立分类数据数目一致，模型的自由度为零，这种情况下，只包含一组目标和干扰刺激的模型被称为饱和模型(saturatedmodel)，对参数 $\boldsymbol { r }$ 和 $g$ 的估计可以将击中率和虚报率带入方程进行计算：

$$
\begin{array} { r } { \hat { r } = \frac { \hat { p } ( \hat { h } i t ) - \hat { p } ( f a l s e \ a l a r m ) } { 1 - \hat { p } ( f a l s e a l a r m ) } } \end{array}
$$

$$
\hat { g } = \hat { p } ( f a l s e \ a l a r m )
$$

其中，公式中的中p(hit)和p(falsealarm)是根据行为数据对公式1-2中理论上真实值p(hit)和p(falsealarm)的估计值；和 $\widehat { \theta }$ 则分别是参数 $r$ 和 $g$ 估计值。

根据这个思路，研究者对于“新-旧”再认范式任务中的心理过程进行了大量的研究，建立了多个认知模型。上述模型被称为单高阈((1HT)模型(Swets,1961)，即在新旧再认中，仅存在一个识别旧项目的阈值，当认知加工结果高于该阈值时，将当前刺激判断为旧项目否则判断为新项目。但是这个模型有一个很明显的不足：没有假定被试直接将新刺激判断为新的情况（即新刺激也可以直接进入确认状态）。因此后续出现了其他的模型，如低阈限(LT)模型(Krantz,1969)和双高阈限(2 HT)模型(Snodgrass & Corwin,1988)。除此之外，MPT还有一个特殊的简化模式一—加工分离程序(process dissociation procedure,PDP)(Jacoby,1991)——也被广泛使用，它可以被看作是只包含两个认知参数的简单MPT模型。

在 MPT模型的框架之下，研究者可以假设行为背后潜在的认知加工过程并建立模型，然后通过实验数据来检验模型的拟合效果并估计心理过程发生的可能性，或者通过实验操纵来调控相应的心理过程来检验该操纵是否有效，从而能够确认和量化行为背后的心理过程及其的影响因素，这是传统分析方法所不具备的优势。

# 3MPT模型的应用与实现

将 MPT 模型应用于社会认知研究中，大致包括如下三个主要步骤(Hutter＆Klauer,2016):

（1）构建模型结构。由于MPT模型反映的是研究者对人们某种行为背后心理过程所设想的框架，因此首先需要研究者根据研究问题及其涉及到的方法与范式，建构出能够充分描述数据并提供心理过程的理论模型，该理论模型需要尽可能地反映心理过程的交互作用及它们对行为表现的影响。建立理论模型后，可以绘制出如图1所示的树形图，清楚地表示出每种心理过程如何影响最后被试的行为表现。然后，可以按照建立的模型对被试的结果数据进行拟合，并估计每种心理过程的概率。数据拟合可以借助多种统计方法来判断理论模型与实际数据的拟合程度。例如，可以采用拟合优度统计量 $G ^ { 2 }$ ，以比较数据与模型的拟合情况： $G ^ { 2 }$ 值不显著表明模型与数据的拟合良好， $G ^ { 2 }$ 值显著表明模型与数据不能很好地拟合，模型可能需要调整(Read&Cressie,1988)。另一种方法则通过将感兴趣的心理过程的参数设置为0（或者根据其它的推测标准，设置为0.5或1），再评估模型参数限定对模型拟合的影响。如果将某一心理过程参数设置为0时，模型与数据的拟合优度减小，则表明该心理过程参数显著大于0，并且应该被包含在模型之中（如：Conrey,Sherman,Gawronski,Hugenberg,& Groom, 2005)。

（2）参数的有效性评估，即评估模型和参数的效度。虽然在步骤一中对MPT模型与数据拟合程度进行了检验，但是拟合程度并不能直接说明模型参数对心理过程解释的有效性。因此，研究者需要进一步对参数的有效性进行评估。一种常用的方法通过实验来操纵某个特定参数相应的心理过程，检验该心理过程对应的参数是否变化。若实验操纵能够影响该心理过程参数，并且参数值会随着操纵程度的不同而改变，则认为该模型参数可以较好地解释心理过程，即模型参数有效(如：Hüter,Sweldens,Stahl,Unkelbach,&Klauer,2012)。

（3）模型的应用。如果前两步均有效，表明该模型能够较好地反映心理过程。则研究者可以设计进一步的实验来检验新的实验假设，例如，设计新的可能会改变某个特定心理过程的条件，从而检验该条件是否对相应的模型参数产生影响，进而验证该操作对心理过程影响的有效性。

一般而言，研究者可以通过以上三个步骤来提出、验证并应用MPT模型，并在此基础上检验新的研究假设。由于MPT模型能够使用拟合优度检验、参数估计等统计分析方法对模型与数据的拟合优度进行估计，并估计出各个参数值，因此研究者能够更加量化地比较变量对心理过程以及行为的影响程度，或者比较不同实验操纵对同一心理过程的影响，提高社会心理学研究的效度和精度。

虽然MPT模型的原理并不复杂，但是模型的拟合、参数估计以及模型比较的过程相对繁琐，因此需要专门的程序来辅助计算。目前，MPT模型的计算机程序主要有6个：MBT(Hu,1999)、GPT (Hu & Phillips,1999)、 AppleTree (Rothkegel,1999)、HMMTree (Stahl &Klauer, 2007)、multiTree (Moshagen,2010)和 TreeBUGS (Heck,Arnold,& Arnold, 2017)。这些程序均提供了MPT 建模所需要的统计计算，其中，Moshagen(2010)发展出来的 multiTree软件(http://psycho3.uni-mannheim.de/multitree)由于操作简单、功能相对全面等优点而被广泛使用。

值得注意的是，传统的MPT模型计算中（例如multiTree中的算法），一般将实验中所有被试的数据整合输入进行拟合及模型比较。这种算法假定同一实验组中被试的参数是同质的，忽略了各个被试之间的差异。最近研究者们开始考虑被试之间的差异，采用层级模型来对参数进行估计(Armold, Bayen,& Smith,2015; Klauer, 2010; Matzke,Dolan,Batchelder,&Wagenmakers,2015)，并开发了相应的工具来完成这些估计的过程，例如 TreeBUGS (Hecket al., 2017)。

# 4MPT模型在社会心理学中的应用

目前，MPT模型已经被应用于社会心理学的多个领域，例如：态度的自动获得(Hutter& Sweldens,2013)、刻板印象(Klauer& Meiser,2000)和道德判断(Gawronski, Conway,Armstrong,Friesdorf,&Huttr,2017)等。我们将以道德判断为例，说明MPT模型在社会心理学中的最新应用。

道德判断背后的心理过程是道德认知研究中的重要问题(彭凯平，喻丰，柏阳,2011;Greene,2015)。伦理学上将人们的道德判断划分为功利论(utilitarianism)倾向和道义论(deontologist)倾向(喻丰,彭凯平,韩婷婷,柴方圆，柏阳,2011)。功利论认为一个行为是否道德取决于行为结果对个体整体幸福感的影响；而道义论认为行为的道德性依赖于行为本身与道德规范的一致性。

道德判断的早期研究将被试的判断划分为功利论取向或者道义论取向，并将这两类判断与控制加工和自动加工对应起来(Greene,2008)。然而，该理论未考虑被试在做出道德判断时同时被两种动机驱动的可能性。最近，Gawronski等(2017)根据 MPT模型的思路，构建了CNI(consequence,norm,inaction)模型，试图分离被试在道德困境中做出判断时的不同认知加工过程（如图2b模型所示）。在这个模型中，研究者假设道德判断由三个心理过程来完成：结果导向的反应(consequence,参数 $C _ { \cdot }$ ），道德规范驱动的反应(norm,参数 $N _ { \ l }$ ，结果和道德规范驱动失败时被试倾向于不行动的反应(inaction,参数I)，它们分别代表了三种假设的潜在心理过程：功利论倾向，道义论倾向和反应倾向的主要特点。根据CNI模型，可以得出图2b的加工树模型。

为了验证CNI模型是否适用于道德困境研究并能很好地分离潜在的心理过程，Gawronski等(2017)设计了6种基本的道德困境情景用来验证CNI模型的适用性。每个道德困境包括行为的收益/成本比（收益大于vs.小于成本） $\times$ 道德规则（抑制vs.促进行为）4个版本（见图2a示例）。对于这24个版本的道德困境，被试需要做出接受与否的反应。

背景假设你是某个发展中国家一家医院的主任，来这儿志愿服务的一名外国学生感染了一种罕见的病毒...道德规则 抑制 促进治疗该学生的方法是使用 治疗该学生的方法是把他药物。虽然病毒不会使她死亡， 送回国治疗。如果不让该学生但是药物的副作用会使学生患 回国进行治疗的话，病毒会使上慢性免疫缺陷最终导致死亡。 他患上慢性免疫缺陷最终死亡。  
行动的收益  
成本比 大王 小于 大于 小于病毒有很高的传染 病毒有很高的传染 病毒有很高的传染 病毒有很高的传染性并且对老人和小孩来 性并会导致严重的胃绞 性并会导致严重的胃绞 性并且对老人和小孩来说是致命的。 痛。 痛。 说是致命的。1问题你能接受用药物治疗该学生吗？ 你能接受将该学生送回国治疗吗？(a)

![](images/7ad0a3aa68362e7e4cb2c0aa6015691d97b5a95bd5fc6e47dea037a729c05884.jpg)  
图2道德困境及相应CNI模型图解(a)和道德情境及条件示例(b)

注：a图中从上到下内容依次为道德困境的背景、道德规则抑制/促进行为维度的语言描述、收益/成本比（收益大于/小于成本）维度的语言描述，以及在每个具体版本中被试需要回答的问题。b图为Gawronski等(2017)的CNI模型，其中刺激栏、反应栏和概率栏分别代表了实验中的刺激、被试可能的反应以及该反应的概率，认知过程栏中的虚线方框代表被试潜在的认知加工过程。其中， $C =$ 结果（功利论）驱动反应的概率， $N =$ 道德规范（道义论）驱动反应的概率， $I =$ 结果（功利论）和道德规范(道义论)驱动反应失败时被试倾向于不行动的概率。

在实验一中，Gawronski等(2017)通过男/女性被试在做出道德判断时心理过程上的差异，来探究CNI模型是否适用。先前的研究已经表明，当伤害行为能够给更多人带来好结果时，男性比女性更加倾向于接受该伤害行为(Arutyunova,Alexandrov,& Hauser,2016)，女性可能会更加倾向于道义论(Friesdorf,Conway,&Gawronski,2015)。但是先前的结果并不能区分这种行为上的差异到底是由于不同性别个体在道义/功利倾向上的差异，还是行动/不行动倾向上的差异，而CNI模型则能够对这些心理过程进行检验。他们的结果表明，CNI模型与数据拟合良好，女性在参数 $N$ 和 $\boldsymbol { I }$ 值显著大于男性，表明女性的道义主义倾向和不作为倾向都比男性强。这一发现为先前的结果提供了较好的心理机制方面的解释，表明女性更倾向于不行动，并且对规范的敏感性更高，而对于后果的敏感性与男性没有差异。

采用这种思路，作者们进一步检验了道德判断中其他影响因素（认知负荷、框架效应和精神病态）对CNI模型参数的影响。这些实验表明，CNI模型能够较好地拟合被试判断时的心理过程，改变被试特定心理过程的实验操纵能够特异地改变相应的模型参数，为进一步对道德判断背后的心理过程进行探索提供了良好模型框架。

虽然道德判断的模型与经典的MPT模型看似不同，但它仍然采用多项式加工树模型的基本思路，建立并检验了该研究问题中特定的模型。最近，Gawronski,Conway,Armstrong,Friesdorf和Hutter(in press)对CNI模型进行进一步拓展，探究情绪在道德判断中的作用。此外，许多其他不同的研究也采用MPT模型的思路，例如在态度研究中，Meissner 和Rothermund(2013)根据MPT模型衍生出了ReAL模型。这些研究表明，可以根据研究问题和实验范式的不同而灵活地建立MPT模型。

# 5结论

MPT模型能够对简单的数据进行模型分析，采用更加量化的方式来研究社会认知问题，反映了社会认知研究的新趋势(Johnson et al.,2017; Stanley& Adolphs,2013)。与传统社会心理学的研究方法相比，MPT模型的主要优点在于提出并验证潜在的变量和加工过程，例如，在道德判断中对结果、道德规范和行动倾向对反应驱动的分离。同时MPT模型建立后，研究者能够通过操纵实验条件来影响模型的参数，从而更加精确地检验假设，具有较高的实用价值。

值得注意的是，MPT模型的使用前提是对心理过程有着明确的假设，因此使用前需要注意 MPT模型是否适合当前的实验范式和研究问题。在模型的数据分析中，MPT的参数值使用数据估计的方法（如极大似然法）进行估计，相互之间不能精确比较，只能理解为一种“优于”的关系(唐卫海,张红霞,白学军，刘希平,2015)。此外，MPT模型虽然与行为数据拟合较好，但是如何将心理过程与人脑的神经活动进行对应仍然缺乏研究，今后的研究需要进一步探索MPT模型中心理过程的神经基础。最后，由于MPT模型提供了与传统数据分析不一样的方法，增加研究者在方法上的灵活性，进而增加研究假阳性的可能(Silberzahn et al.,in press)。在当前心理学研究面临可重复性问题的背景下(如：胡传鹏等,2016)，采用提前注册研究等开放的方式(Munafo et al.,2017)，将MPT模型的使用及其检验的假设提前进行注册，将更有利于研究者得到可靠的研究结论。

参考文献   
胡传鹏,王非,过继成思,宋梦迪,隋洁，彭凯平.(2016).心理学研究的可重复性问题：从危机到契机.心理科学进展,24(9),1504- 1518.   
彭凯平,喻丰，柏阳.(2011).实验伦理学:研究、贡献与挑战.中国社会科学(06),15-25.   
唐卫海,张红霞,白学军，刘希平.(2015).MPT模型在事件性前瞻记忆研究中的应用.心理科学,38(5),1218-1222.   
喻丰,彭凯平,韩婷婷,柴方圆，柏阳.(2011).道德困境之困境——情与理的辩争.心理科学进展,19(11),1702-1712.   
Arold,N.nUJ,ithE.().raalolodegoh.pemetalolo( 152.   
Arutyunova,K.RlexandrovY.,&Hauser,.D. (o6).ocioculuraliuenesnmoraljudgments:EastWstaleeale and young-old.Frontiers inPsychology,7,1334.   
Bargh,J.A.(99).foofaiirstiyroalo Jr.,&T.K.Srull(Eds.)Handbookof Scial Cognition (2nded.,Vol.1,pp.1-40).Hillsdale,NJ:Erlbaum.   
Bayen,U.J,ae,K,dfer,E.(996).ouesatioeiodoaldelsoue Journal ofExperimental Psychology:Learning,Memory,andCognition,22(1),197-215.   
Conrey,F.R.anJ.woskigebg,K,oC.J.().epatingultileprocessinitil cognition:Thequadmodelofimplicittaskperformance.JournalofPersonalityandSocialPsychology,89(4),469-487.   
Elandt-Johnson,.C.(1971).Probbilitymodelsdstatisticalmethodsingnetics:eYork,odon,Sydnyoronto:JoWily& Sons, Inc.   
Erdfelder,E,uer,TSbigB.fal,.oshagn,darevic,L. (9).ultiomalprocessngtreels:A review of the literature.Journal ofPsychology,217(3),108-124.   
Friesdorf,R,oy,oski.)erdcsispotala:pocsstali Personality and Social Psychology Bulletin,41(5),696-713.   
GawronskiB,&odeusen,GV.(o).AsoiativendpropositoalprocesssivaatioAntegrativeieoflicitd explicit atitdechange.sycholgicalBulletin,32(5),97   
Gawronskiorog,Jsdf,&ter.().scsodgeraledacil dilemmas:TheCNImodelofmoral decision-making.JournalofPersonalityand Social Psychology,l13(3),343-376.   
Gawronski,B.owayrmsrong,riesdorf,R.&uter,.(inpres).ctsofcidentalemotiosonmoalila judgments: An analysis using the CNI model. Emotion.   
Grene,J.D.(o8).ThsecretjokeofKant'ssoulInW.Sinot-Armstrong(Ed.)，oralsyholgy(Vol.3,pp.35-8).Cambdge MA, US: MIT Press.   
Grene,J.D.(20l5).Theriseofmoralcognition.Cognition,35,39-42.   
Greene,J.D.,ei.ebg,K,L.E,nJ.).ideieleeii moral judgment.Cognition,107(3),1144-1154.   
Heck,D.W.,old,N.R,&Aold,D.(7).U:AnRpackgeforrarchicalmultiomal-procesing-treeodeling. Behavior Research Methods,1-21.   
Hu,X.(1999).Multinomial procesing treemodels:Animplementation.Behavior Research Methods,31(4),89-695.   
Hu,X.,&Phillps,G.A.(999).GPT.EXE:Apowerfultoolfortevisualizatioadnalsisofgeneralprocesingtreeodel. Behavior Research Methods,31(2),220-234.   
Hutter,,&l,K.C.().ngrocingtrsiolpolgunevefolhg 159.   
Hutter,M.,&Swdens,S.l3).Iplicitsatrbutionoevauatiespons:Contigencynaareevaatieonoii simultaneous stimuluspresentations.JournalofExperimental Psychology:General,142(3),638-643.   
Hutter,M.,weds,alCUkebac,ClerK.C.).ogoingearddiidi: evidenceofcontingency-unawareevaluativeconditioning.JournalofExperimentalPsychology:General,4l(3),9-5.   
Jacoby,L.L.(1991).Aproessdissociationframework:SparatingutomaticfromintentionalusesofemoryJoualofemorynd Language,30(5),513-541.   
Johnson,DJood,CarioJsac.J.).dcgsarchgiepressodli psychology:Ahierarchicaldrift diffusion model primer.Social Psychological and Personality Science,8(4),412-423.   
Klauer,K.C.(l).Hierarchicalmultinomial procesing treemodels:Alatent-traitapproach.Psychometrika,75(1),-98.   
Klauer,K.Ces.).oueitglysisfluoelaisersoalitdoalloeti 26(9),1074-1093.   
Krantz,D.H.(1969).Threshold theories of signal detection.Psychological Review,76(3),308-324.   
Matzke,D.,Dolan,C.Vatchelder,W.H,&Wageaker,.-J.().ayesanatiofutoialprocesingrdels with heterogeneity in participants and items.Psychometrika,80(1),205-235.   
Meissner,F.,&oteundK.(3).timatigteontrbtiosfssociatiosdrcodingiteiplicitssociatioste ReAL model for the IAT.Journal of Personality and Social Psychology,104(1),45-69.   
Moshagen,M.(0l0).MultiTree:Acomputerprogramfortheanalysisof multinomialprocessng tree models.BehaviorResearch Methods,42(1),42-54.   
Munafo,M.R,Nosek,B.A,BishopD.V,Button,K..Chambers,C.DPercieduSertN.aidis,J.P.().A manifesto for reproducible science.Nature Human Behaviour; 1,21-29.   
Read,T.,&Cresse,N.(1988).Goodnesof-fitstatisticsfordiscretemultivariateanalysis:Springer-Verlag,NewYork.   
Riefer,D.M,&Batchelder,W.H(988).Multinomialmodelingandthmeasurementofogitieprocesses.Psychologicalevie 95(3),318-339.   
Rothkegel,R.(1999).ApeTree:Amultinomial processng tree modelingprogramforMacintoshcomputers.BehaviorResearch Methods,Instruments,& Computers,31(4),696-700.   
Silberzahn,Uarssteyokssalesi transparent how variations in analytical choices affect results.PsyArxiv.   
Snodgrass,J.G,&owin,J.988).ragaticseasuigrcogtooryplcatiostmntiadesiaJoualf Experimental Psychology:General,I17(1),34-50.   
Stahl,C.,&erK..).re:outeraftetasccalioalpesigtreels. Behavior Research Methods,39(2),267-273.   
Stanley,D.A.,& Adolphs,R.(2o13).Toward a neural basis for social behavior. Neuron,80(3),816-826.   
Swets,J.A.(1961).Is there a sensory threshold? Science,134(3473),168-177.

# Multinomial Processing Tree Models and Their Application in Social Psychology

# Yuanyuan Liu 1, Yi Ding ², Kaiping Peng ³, Chuan-Peng Hu ³

(Department of Psychology, School of Philosophy, Wuhan University, Wuhan, 430072) (Department of Psychology, School of Education, Hubei University, Wuhan, 430062) (Department of Psychology, School of Social Science, Tsinghua University, Beijing,100084)

Abstract Understanding the psychological processes and mechanisms behind social behaviors is one of the most important goals of social psychology. Psychologists have proposed many theoretical models to explain people's social behaviors. It is still, however, difficult to quantify the contribution of hypothesized psychological processes to a specific behaviour. Recently, social psychologist introduced multinomial processing tree (MPT) models to dissociate different processes and quantify the contributions of each hypothesized process to behaviors.

MPT, which combined knowledge from cognitive psychology, statistics,and other related disciplines, is a simple and effective way to model behavioural data. In these models,different hypothesized psychological processes take the external stimuli as input and determine the behavioural outcomes in a tree-like manner. More specifically, each stimulus was first processed by a hypothetical psychological process(i.e.,a branch with certain probability), which results in a binary outcome (i.e., a point): either a behavioural response (i.e., a resulting behavior), or an intermediate outcome that will be determined further by a downstream psychological proce (i.e., another branch, with a different probability) until behavioural outputs were produced. In this way, each behavioural output can be viewed as the combination of the processes before it, while the sum of all the behavioural output to a specific stimulus sum up to one. By fitting the behavioral data to multiple nominal formulas,the probability of each psychological process can be estimated.

Given that the psychological processes in MPT models need to be specified, researchers should construct the model structure before using the model. After the model structure is specified, researchers also need to fit the model with behavioral data and test the goodness-of-fit. Researchers need further validate the model and its parameters based on theory, only after validation, the model can be regarded as an acceptable model for such question. Then, the validated models can be used to generate and test new hypotheses.

Although the logic behind the MPT model is easy to understand,the estimation of parameterestimation and goodness-of-fit test often require massive computation that could hardly be finished by hand. Therefore, several computer programs (e.g. multitree, treeBugs) were developed, to simplify the calculating procedure.These user-friendly programs make the MPT models more accessible to social psychologists.

By now, MPT models have been applied in many areas of social psychology, such as attitude, stereotype acquisition etc. Recently, MPT models were applied to moral decision-making. For instance, Gawronski et al. (2017) built the CNI (consequence, norm, inaction preference) model based on MPT model. The CNI model can dissociate the contributions of consequences, norm, and inaction preference,therefore, extended previous studies on moral decision making by considering the possibility that moral decision-making can be motivated by both utilitarian and deontological motivations simultaneously, or neither of both. Using CNI model, Gawronski et al. (2017) tested the effect of gender, cognitive load, framework effect and psychopathy on moral decision-making.

It becomes increasingly clear that MPT models can serve as a tool for dissociating and quantifying the psychological processes underlying human behaviors.However, it is noteworthy that MPT models require clear assumptions about psychological processes and corresponding outcomes, this pre-request should be carefully checked before use. In addition, although MPT models fit well with many behavioral results, the neural correlates of the assumed psychological processes in MPT models are largely unknown, further studies are needed to explore and validate the neural basis of these models.Finally, MPT models might increase the research flexibilities, which might cause false positive results. Thus, researchers should keep transparent of their analysis and decision process when applying MPT to their own research questions.

Key words: multinomial processing tree model, model analysis,social cognition, moral judgment