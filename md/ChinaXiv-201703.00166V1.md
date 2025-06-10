# 以用户为中心的场景感知与分析技术

# 叶剑 朱珍民 陈援非 何哲

摘要 以用户为中心，基于场景感知实现任务计算是普适计算所追求的目标之一。但怎样从高维、非线性，并且具有一定耦合度的情境数据中提取场景特征，使计算系统能够在复杂的场景变化中完成用户的计算要求，是研究的难点和热点。本文主要研究在复杂的普适计算环境中，面向以用户为中心的计算需求实现智能场景感知。研究内容包括建立分布式模糊推理模型和参数学习方法；基于流形学习和云模型方法，研究场景特征分析技术，实现场景特征提取；基于场景感知，建立用户偏好计算模型，实现以用户为中心的普适计算模型。

关键词 情境感知 场景分析 模糊推理 用户偏好模型

# 1引言

普适计算环境的特点是具有随时随地访问信息和不可见的计算能力，计算透明性和无处不在是普适计算重点强调的技术特性。因此，普适计算以人为本而不是以计算机为中心，迎合了信息空间与物理空间的融合趋势，成为国际上一个蓬勃发展的研究热点。在动态的普适计算环境中，用户任务的精确执行与环境的情境（如地点、时间)以及用户的个性化信息（如偏好等）紧密相关，因此用户任务是场景依存的。场景感知的最终目的就是为普适计算环境中的用户任务计算提供决策支持。但围绕用户这一中心，重用采集的场景信息，对场景做出准确分析和判断，仍然是普适计算技术实现过程中困扰我们的难题。它不仅具有重要的理论意义，而且在移动运营增值服务、智能家居、城市综合信息服务领域有着广泛的应用前景。

当前，具有普适计算特征的研究项目对于物理空间特征的定义还停留在情境（又称为上下文）层面，通过对诸如位置、时间、用户身份、计算能力等情境的感知，获得高层情境语义。这种方式引发了“情境鸿沟”[[]问题，使得系统提供的情境信息与用户需要获得的情境之间存在差异。这一方面是由于传感装置的精度、情境表示方式引起数据表达的不准确（情境通常是数量值和语义概念混杂的数据，情境之间还会相互影响)，使情境信息难以完整地体现环境的特点；另一方面，用户需求是一个高层的抽象目标，与情境的抽象级别之间存在显著的不匹配现象，势必会造成情境知识与用户需求之间存在差距，影响用户与普适计算环境之间交互决策的正确性。而通过场景抽象，在高维情境信息中提取场景特征，研究基于情境感知与推理的场景感知与分析技术，将为弥合情境感知与用户需要之间的鸿沟提供新的途径。

# 2 国内外研究现状

普适计算技术的研究得到了世界上许多发达国家和地区的政府、学术界的极大关注，投入了大量的人财物等资源，针对不同的需求对其展开研究。美国国防高级研究计划署(DARPA)、国家自然科学基金(NSF)、国家标准与技术研究院(NIST）都为普适计算研究设立了庞大的研究计划：国防高级研究计划署同时资助了麻省理工大学 的Oxygen 计划[3]、卡内基梅隆 大学的 Aura 计划[4]、伊利诺伊大学香槟分校的Gaia 系统[5]，俄勒冈研究院和佐治亚技术大学的InfoSphere 计划以及华盛顿大学的Portolano[7]；而美国国家标准与技术研究院针对普适计算制定了详细的研究计划，并由其下属的信息技术实验室专门负责协调、制定标准、测试等工作。欧盟也于 2001年启动 Disappearing Computer 计划[8,涉及17个为期 2-3年的普适计算项目和 Smart Tea/MyTea 计划[等相关工作。英国投入1000 万欧元设立了为期六年的 Equator 研究计划[10]。

在普适计算的研究项目中，智能感知技术始终作为核心关键技术研究的重点。尽管每一时刻情境感知系统都能从传感器网络中获得大量数据，但是这些未加工的信息，是对环境某一属性在一个时间点上的描述，同时传感数据也存在一定的不确定性与不可靠性[，这使得我们难以直接获得需要的语义信息。为此，必须通过情境推理，对这些原始信息进行信息抽取，获得语义知识，依照一定的规则进行推理，得到高层情境。情境感知系统采用的推理技术，吸取了人工智能领域的成果，把情境作为一种知识来推理。目前主要采用基于规则的逻辑推理和基于机器学习的推理两种方式。

# 2.1基于规则的逻辑推理

规则通常采用一阶谓词逻辑，通过规则条件定义，建立条件和结论直接的蕴含关系。由于规则逻辑与人类对客观世界认知习惯相吻合，因此是一种简单、实用并且常用的情境推理方式。

美国伊利诺大学香槟分校开发的Gaia系统[5.12]研究就是基于一阶谓词演算的情境模型。该模型可以充分利用布尔表达式的演算规则，同时结合对情境信息的量化处理，实现针对情境的自动化的演绎和推导。勃姆斯多夫（Bomsdorf）[3]通过规则，定义在特定情境中学习资料的选择方法。基于策略的演算是规则逻辑的另一种表现形式。香卡（Shankar）[14]研究基于策略的普适计算系统管理框架，通过将策略定义的 ECA规则扩展为带冲突检测的ECPAP规则，用以表示在特定条件发生时应该执行何种管理行为。

上述研究工作采用的都是精确规则定义。由于规则依赖于经验值，因此精确规则的自适应能力较差，并且无法灵活地仿真人们的智能推理决策习惯。为此，於志文（Zhiwen Yu)等[15]提出了一种模糊推理与学习方法，将模糊逻辑与推理规则结合，实现规则中的条件命题和结论的模糊化，进而完成模糊推理过程。

伴随着语义Web 技术的发展和相关理论的不断成熟，本体理论被逐渐引入情境建模和推理。基于本体的情境推理一般采用定义推理规则的方式，基于资源描述框架（ResourceDescription Framework，RDF）描述元数据的数据模型，采用XML'、OWL²、DAML'+OIL4语句进行建模，基于描述逻辑或者规则进行推理。这种方式可以扩展实现元数据语义的关系逻辑定义，因此逐渐成为情境数据和高层语义的表示规范。Gaia系统将本体与普适计算结合，采用语义描述语言DAML $+ \mathrm { O I L }$ 定义情境本体，在不同的普适计算环境中建立互操作机制。通过Gaia 的系统实验，证明了本体在情境推理中的重要作用[]。情境代理体系架构CoBrA[17采用 OWL 作为 COBRA-ONT 本体的建模工具，使用OWL 内建的规则检测情境中的冲突，当冲突发生后根据智能代理的假设权重对冲突的情境陈述进行处理。赫德尔（Khedr）等[18通过建立协商机制，实现了情境描述的创建和修改。并且在推理引擎中建立模糊推理规则，能够实现对情境本体的自然扩展。

将本体引入情境推理技术中，提供了一种方便、可行的情境数据建模方式。更为重要的是，本体与规则定义结合，可以发现情境之间蕴含的隐式语义关系，这已经在许多系统和模型中得以证明。但基于规则逻辑的推理方式始终无法摆脱对经验和常识的依赖，无论是规则定义还是语义建模，通常采用离线定义方式，无法在运行时进行动态调整。

# 2.2基于机器学习的推理

机器学习是智能系统非常重要的特征，有助于在情境推理中研究如何适应系统情境的变化，使得系统在具有相同或类似的情境时能做出一致性的反应。情境推理常用的机器学习方法包括贝叶斯网络、隐马尔可夫模型等工具。目前的研究趋势是机器学习方法与本体建模、模糊逻辑结合，实现混合推理模型。

贝叶斯网络近年来被广泛用于情境感知领域，由于非常适合处理信息的概率分布，因此成为该领域最重要的机器学习方法。贝叶斯网络的学习和决策过程[19如图1所示。顾涛（音译，Gu）等[20]针对情境本体模型进行概率扩展，用概率分布表示情境的不确定性，在此基础上采用贝叶斯网络作为不确定性推理的工具，研究资源描述框架图向贝叶斯网络的转化算法，其实质是在元数据关系描述中，求解元数据之间的条件依赖，用来表征语义关系的置信程度。於志文等[21研究基于情境感知的个性化混合多媒体推荐系统，提出了基于规则和贝叶斯分类器的推荐模型，采用朴素贝叶斯分类器作为特定情境条件下对待推荐资源的评价分类工具。

![](images/0389a559398be1e3deb3449d339e8300c36d6f4ee0dfd2bca925454c9e4c90b4.jpg)  
图1.贝叶斯网络的学习和决策过程

阮冈纳赞（Ranganathan）等[1研究模糊逻辑规则与贝叶斯网络混合学习模型，情境元数据采用本体建模，元数据之间的语义依赖关系通过模糊逻辑和贝叶斯网络学习。朴（Han-Saem Park）等[22]提出一种模糊贝叶斯网络模型，用于基于情境感知的音乐推荐系统，将模糊逻辑的混合数据处理能力用于贝叶斯推理的数据预处理。

隐马尔可夫模型也是一种可以在情景推理中用于情境识别和预测的重要的机器学习方法，但主要用于可穿戴计算领域的研究工作。克拉克森（Clarkson）等[23]和斯塔纳（Starner)等[24]将隐马尔可夫模型用于可穿戴计算环境中的位置和事件的判定。高帕拉特姆（Gopalratnam）等[25]设计并实现了基于隐马尔可夫模型的预测算法 Active LeZi，并将其内嵌入智能家居环境，用于预测家用电器的使用情况。

此外，支持向量机也是一种常用的情境分类工具。张彤（Tong Zhang）等[26利用传感器感知老人的身体特征参数，并以此为根据采用支持向量机的方法对老人处于摔倒或非摔倒状态进行判定。布林（Bulling）等[27]为了实现通过眼神捕捉用户动作的目的，采用支持向量机将眼神抽象为90个特征，根据眼神的特征识别用户当前的状态和行为，达到了较高的识别准确率。

# 2.3情境推理建模

基于Petri 网的智能推理机制的研究由来已久。早在上世纪80年代末，针对客观世界模糊推理要求，鲁尼（Looney）等[28]就提出基于 Petri 网的近似推理解决方案，当时被称为模糊 Petri 网或模糊逻辑网。陈锡明（Shyi-Ming Chen）等[29]明确了模糊 Petri 网的概念，提出规则生成方法和推理算法，并将其用于一般知识表示系统中。高梅梅（MeimeiGao）[30]在2003 年提出了模糊推理 Petri 网模型FRPN（Fuzzy Reasoning Petri Net）的定义，设计并实现基于FRPN的正向推理算法。

纵观基于Petri网的推理机制的研究工作，其重点在于推理算法研究，按照推理的逻辑顺序，推理算法分为正向推理和逆向推理两种方式。

在正向推理中[29-31]，模糊集的隶属度分布由 Petri 网的初始使能库所刻画，推理的目的是通过初始使能库所获得 Petri 网其他库所代表的命题的隶属度，隶属度反映了命题的真实程度。正向推理模型按照 Petri 网定义的变迁方向传递隶属度，计算某个库所的隶属度之后不会再考察该库所的前趋库所。

逆向推理[32则从待求解命题的表征库所入手，通过回溯的方式确定库所求解所依赖的推理树，然后正向求解该推理树上的各个库所的隶属度。逆向推理虽然与推理的逻辑顺序相逆，但逆向推理可以通过构建推理树，消除正向推理为计算结论库所的隶属度而引入的对不相关的库所隶属度求解的额外开销。因此，逆向推理具有较高的计算效率。

# 2.4多维一多目标偏好模型

传统的用户偏好计算大多是基于单一的用户模式（UserProfile)。从输入输出的角度，可以认为传统的偏好计算模型输入是二维的，即有用户偏好和推荐资源两个维度，输出是一维的，即用户对资源的评价（Rating)。评价越高，越有可能被推荐。传统的偏好计算模型的形式化表示如下。

设用户集合为user_set，资源集合为resource_set，则用户的偏好通过用户对资源的评价 $\pmb { R } ( \pmb { u } , \pmb { i } )$ 来定义,设评分集合为rating_set，则 $\pmb { R } ( \pmb { u } , \pmb { i } )$ 定义如下：

$$
R ( u , i ) \colon u s e r \_ s e t \times r e s o u r c e \_ s e t  r a t i n g \_ s e t
$$

普适计算环境中的偏好计算比传统单一基于用户模式的推荐要复杂得多，需要充分考虑环境中的情境信息，基于感知到的情境进行用户偏好求解[3][4]。此时，用户偏好计算需要综合考虑物理情境、逻辑情境、用户情境等情境信息，从二元偏好模型扩展到多元偏好模型[35]，即

$$
R ( u , i ) \colon u s e r \_ s e t \times r e s o u r c e \_ s e t \ \times \ c o n t e x t _ { 1 \_ s e t } \times \ \cdots \times c o n t e x t _ { n \_ s e t }  r a t i n g \_ s e t
$$

其中，contexti_set表示不同维度上的情境集合，可简化表示为

$$
R ( u , i ) \colon u s e r \_ s e t \times r e s o u r c e \_ s e t \ \times \prod _ { i = 1 } ^ { n } c o n t e x t _ { i } \_ s e t \to r a t i n g \_ s e t
$$

此时，基于情境感知的用户偏好计算问题描述为：

$$
\forall u \in u s e r \_ s e t , \ \forall \left( c _ { 1 } , c _ { 2 } , \cdots , c _ { n } \right) \in \prod _ { i = 1 } ^ { n } c o n t e x t _ { i } \_ s e t
$$

选择 $r \in$ resource_set，使得i $\cdot a t i n g ( \pmb { u } , \pmb { c } _ { 1 } , \pmb { c } _ { 2 } , \cdots , \pmb { c } _ { n } , \pmb { r } )$ 最大，即

更进一步，其计算结果可能需要从不同的角度描述用户对资源的兴趣。以餐馆推荐系统为例，就需要考虑到不同用户的多样化和个性化需求，往往需要从餐馆的环境、价位、风味、服务质量等方面进行综合评价。因此，用户偏好计算模型发展为 $N \times M$ 模型[35]，即

$$
R ( u , i ) \colon u s e r \_ s e t \times r e s o u r c e \_ s e t \ \times \prod _ { i = 1 } ^ { n } c o n t e x t _ { i } \_ s e t \to \prod _ { j = 1 } ^ { M } r a t i n g _ { j } \_ s e t
$$

其中， $\pmb { N } = \pmb { n } + 2$ 。当然，最后的评价体系与应用需求是密切相关的。在实际应用中，基于情境感知的偏好计算的本质还是用户在情境条件下的评价体系。嵌入情境的偏好模型层定义了情境空间到用户偏好空间的映射，主要的目标是将感知的情境知识与用户偏好求解相结合。

# 3 面临的挑战

普适计算强调以用户为中心，计算环境中的情境与特定用户密切相关，因而对场景的感知是实现普适计算的关键。但是现有的普适计算环境中的情境感知技术存在如下几个问题：

(1)．缺少从场景整体特征分析计算环境的技术

决定用户需求的是特定场景中的特定任务。因此对于场景进行精确分析与判断是做出满足用户任务需求的基础和重要依据。场景信息与场景中的情境语义息息相关，而不是情境数据的简单堆砌，需要我们研究基于用户计算环境的整体情境特征定义场景的途径。

(2)．缺少针对普适计算分布式特点的情境推理技术

普适计算环境是一个典型的分布式系统。目前的情境感知技术更多的是从推理的目标出发，通过语义规则定义和选择适当的机器学习方法，研究集中式推理。现有的模糊推理模型重点研究推理算法，无法针对普适计算环境的系统拓扑特点提供分布式推理规约机制。

# (3)．缺乏针对模糊规则的参数学习机制

在模糊推理Petri网理论模型中，定义了命题真实度和规则置信度两个重要的模糊规则的重要参数，分别表征命题和规则的可靠性。这一理念在机器学习混合推理技术中也得以体现。但与推理规则的设计相同，命题的真实度和规则的置信度目前还依赖于经验值，缺乏必要的针对模糊规则本身的学习方法，因此推理规则是静态的，无法反映命题和推理规则的准确性。

综上所述，以用户为中心的计算环境所依赖的基于情境感知的理论和方法还存在诸多不足。因此以情境感知为基础，发展场景感知和分析理论与技术具有重要的理论意义和实践价值。为此，本文针对分布式普适计算环境的特点，研究如何提供满足用户需求并符合场景特点的系统知识，为应用空间的用户任务执行提供决策依据。具体包括建立具有参数学习功能的分布式的模糊推理方法和规约机制；在此基础之上，研究复杂场景的语义特征表达和场景分析方法；以场景感知和分析为基础，建立内嵌场景特征的用户偏好模型，为普适计算环境中具有察觉计算能力的应用系统提供决策基础。

# 4 当前的研究工作

我们的研究工作主要包括两个部分：基于情境推理的场景感知和场景分析。场景感知技术的具体内容包括基于感知情境数据源实现分布式推理，研究分布式推理模型；在推理过程中，建立推理规则参数学习方法；通过场景分析研究情境语义与场景特征值之间映射关系，建立场景分析所需的学习方法；研究内嵌场景特征的用户偏好计算模型，基于场景特征，融合用户和任务描述，构建普适计算环境中以用户为中心的计算基础。图2表示整个研究内容框架。

![](images/f9b5008f423857129cb7ffaf2c64e6266373b1c75f5caf07ab03606b7f7af110.jpg)  
图2.面向任务计算的场景感知与分析技术框架

# 4.1基于情境推理的场景感知

普适计算环境具有分布式和异构性特点，在普适计算环境中将推理任务分配到不同的计算节点上是可行的方法。普适计算环境中的推理规则可以被有效分解为多个独立的命题，这就为分布式推理的实现提供了逻辑基础。为此我们做了两方面的工作：

# (1).分布式模糊推理建模

针对基于规则的情境推理方法的这一特征，我们研究分布式模糊推理Petri网模型，对模型中的库所和变迁的属性进行扩展，并引入新的关于节点状态的向量定义，设计并验证分布式模糊推理算法。

分布式模糊推理Petri 网的基本定义为 $d F R P N = ( P , R , T , L , G , C , \alpha , \beta )$ 。其中，$P = \{ P _ { 1 } , P _ { 2 } , \cdots , P _ { n } \}$ ，为有限库所集，表示推理规则中的命题。我们将在库所集中通过定义特定库所，用于表征终端上推理任务的完成状态，抑或发生推理任务迁移时的状态。

$\pmb { R } = \left\{ \pmb { R } _ { 1 } , \pmb { R } _ { 2 } , \cdots , \pmb { R } _ { m } \right\}$ ，为有限变迁集，表示推理过程。 $R = R R \cup M R \cup S R$ ，其中 $R R$ 为推理变迁集，MR为迁移变迁集， $S R$ 为提交变迁集。

dFRPN引入“负载度”和“负载增长率”两个时序状态变量，构成库所负载度向量 $L$ 和变迁负载增长率向量 $G$ 。同时将映射 $\alpha { : } P \to T$ 和 $\beta : T  C$ 修正为 $\alpha : P  T \times L$ 和$\beta : T \to C \times G$ ，即在库所上附加负载度的定义，在变迁上附加负载增长率的定义。

为此，在dFRPN模型的推理算法中，无论是推理树生成还是最终的推理，均需要对系统状态进行计算和分析。同时，求解dFRPN模型中的命题真实度和规则置信度，使之与推

理过程中的命题和规则的命中度相匹配。

(2)．模糊情境推理参数的学习方法

在模糊推理规则的定义中，命题的真实度和规则的置信度分别代表了命题和规则所蕴含的语义的可靠与准确程度，通常根据经验值确定。在应用模糊推理规则时，由于规则条件部分的命题语义本身具有模糊性，因此对于一次推理任务，往往需要应用多条推理规则，形成应用推理规则集，得出具有模糊性的推理结论。我们将针对模糊推理的两个重要参数：命题真实度和规则置信度，根据命题和规则在推理过程中的命中度，在模糊推理过程中引入推理参数学习方法，根据推理历史中的命题和规则命中度，求解命题真实度和规则置信度，使之符合推理过程的实际。

# 4.2基于智能感知的场景分析

情境信息是原始未加工的信息，是对环境某一属性在一个时间点上的描述。而计算环境是复杂的，与情境紧密相关却并非多种情境信息的叠加。场景分析技术的目的是为了从计算环境的整体特征入手，根据情境基本信息，构建场景特征模型，求解混杂的多模的情境信息所蕴含的统计规律和模糊逻辑关系，通过有限的场景特征值实现场景特征定义，实现不同场景之间的划分。

情境语义到场景特征的映射需要兼顾普适计算环境中信息的统计和模糊两方面的特点。云模型[3能够实现用自然语言值表示的某个定性概念与其定量表示之间的相互转换，反映了定性概念整体上的定量特征。因此，可以将云模型的特征值作为场景特征值，云之间的距离可以通过欧式空间距离表示，进而可以采用聚类分析方法实现云聚类，用以实现场景之间的划分。但由于降维会失去高维情境空间的部分特征，如何在特征损失和降维目标维度之间权衡，需要深入研究。

# 4.3内嵌场景特征的用户偏好计算

以用户为中心的场景感知和分析的目的是实现场景特征与用户偏好计算有机融合，建立面向动态的普适计算环境的用户个性化计算。

为此，我们研究内嵌场景特征的协同过滤算法，技术框架如图3所示。这是由于，一方面协同过滤技术是当前个性化服务中最成功、使用最广泛的方式。协同过滤通过目标用户的最近邻用户产生最终的推荐，首先计算用户

![](images/2f701b20d37d5ea52ad24b6a19de1ab67fd515752efb743a79eccdc69ef25741.jpg)  
图3.以用户为中心的场景感知和分析技术框架

之间和/或项目之间的相关性，然后通过邻居用户对相关项目的评分预测目标用户对未评分项目的评分。但另一方面，目前协同过滤技术通常应用在静态数据中，未考虑情境的情况。而在普适计算这种动态性非常强的环境，用户的决策将会受到环境周围情境的影响。

内嵌场景特征的协同过滤算法在用户对资源的评价中引入情境场景知识，邻居场景的判定依据不再依赖用户对资源的评分，而是根据高维的情境数据构成的原始场景信息进行降维和特征提取，获得低维的情境特征表示。在此基础上，通过基于情境场景的协同过滤的评分预测策略，对目标用户关于资源的评分进行预测。

# 5 结论

以用户为中心的场景感知和分析技术研究具有重要的理论意义和应用价值。它是在普适计算领域进一步开展智能感知、实现透明计算的基础。本文的研究内容针对智能物联和泛在网络环境特点，建立以用户为中心的场景感知和分析的一般方法，为环境中的智能人机交互提供决策知识基础。

今后研究工作将在突出场景感知的理论模型研究的基础上，重点关注如何将模型中的算法应用于普适计算环境的嵌入式原型实现。本文的研究工作将在国家863 计划重点项目“普适计算基础软硬件关键技术及系统”和国家自然科学基金面上项目“面向任务计算的分布式场景感知和分析技术研究”的支持下，力争向具有察觉计算能力的新型计算环境的研发目标迈出重要的一步。

# 参考文献：

[1] Louise Barkhuus.The Context Gap - An Essential Challenge to Context-Aware Computing. Ph.D Dissertation, The IT University of Copenhagen, 2005.   
[2] Barry Brown,Rebecca Rand.Building a Context Sensitive Telephone: Some Hopes and Pitfalls for Context Sensitive Computing. Copmputer Supported Cooperative Work,2004,13(3-4):329-345.   
[3] Larry Rudolph. Project Oxygen: Pervasive,Human-Centric Computing-An Initial Experience. Proceedings of CAiSE2OO0l， Interlaken， Switzerland, in Lecture Notes in Computer Science, Springer-Verlag,2001.   
[4] Joao Pedro Sousa,and David Garlan. Aura:an Architectural Framework for User Mobility in Ubiquitous Computing Environments Software Architecture: System Design, Development,and Maintenance. Proceedings of the 3rd Working IEEE/IFIP Conference on Software Architecture. Kluwer Academic Publishers,2002. pp.29-43.   
[5] Manuel Román, Christopher K. Hess,Renato Cerqueira, Anand Ranganathan, Roy H. Campbell, and Klara Nahrstedt.Gaia:A Middleware Infrastructure to Enable Active Spaces. IEEE Pervasive Computing,2002,74-83.   
[6] Calton Pu,Karsten Schwan, Jonathan Walpole.Infosphere Project: System Support for Information Flow Applications.ACM SIGMOD Record,2001, 30(1) : 25-34.   
[7] Mike Esler，Jeffrey Hightower，Tom Anderson，Gaetano Borriello.Next Century Challnges: Data-Centric Networking for Invisible Computing The Portolano_Project at the University of Washington.Proceedings of MOBICOM '99, Seattle,Washington,1999.   
[8] Norbert Streitz,Achills Kameas, Irene Mavrommati. The Disappearing Computer - Interaction Design, System Infrastructures and Applications for Smart Environments.LNCS 45Oo, Springer Berlin Heidelberg,2007.   
[9] Andrew Gibson,Robert Stevens,mc schraefel,Ray Cooke, Sacha Brostof. MyTea: Connecting the Web to Digital Science on the Desktop. Proceedings of WwW 2006,Edinburgh,UK,2006, pp. 22-26.   
[10] Matthew Chalmers.Place,Media and Activity.ACM SIGGROUP Bulletin,2001,22(3): 38-43.   
[11] Anand Ranganathan,Jalal Al-Muhtadi,Roy H. Campbell.Reasoning about Uncertain Contexts in Pervasive Computing Environments.IEEE Pervasive Computing,2OO4,3(2) : 62-70.   
[12] Anand Ranganathan,Roy H. Campbell.An Infrastructure for Context-Awareness Based on First OrderLogic.IEEE Pervasive Ubiquitous Computing,2003,7(6):353-364   
[13]Birgit Bomsdorf. Adaptation of Learning Spaces:Supporting Ubiquitous Learning in Higher Distance Education. Mobile Computing and Ambient Inteligence: The Challenge of Multimedia, Dagstuhl-Seminar 05181, Saarland,2005.   
[14]Chetan Shankar,Roy Campbell.A Policy-based Management Framework for Pervasive Systems using Axiomatized Rule-Actions.Proceedings of the 2005 Fourth IEEE International Symposium on Network Computing and Applications, Cambridge, MA, 2005, pp. 255-258   
[15]Zhiwen Yu,Norman Lin，Yuichi Nakamura,etc. Fuzzy Recommendation towards QoS-Aware Pervasive Learning.Proceedings of 21st International Conference on Advanced Networking and Applications,2007, pp. 604-610.   
[16]Anand Ranganathan, Robert E. McGrath,Roy H. Campbell, M. Dennis Mickunas. Use of Ontologies in a Pervasive Computing Environment. The Knowledge Engineering Review,Cambridge University Press,2004,18(3):209-220.   
[17]Harry Chen， Tim Finin，Anupam Joshi. An Ontology for Context-Aware Pervasive Computing Environments.Proceedings of IJCAI O3 Workshop Ontologies and Distributed Systems,IJCAI Press, 2003.   
[18]Mohamed Khedr, Ahmed Karmouch. Negotiating Context Information in Context-Aware Systems. IEEE Intelligent Systems,2004,19 (6):21- 29.   
[19]Chihiro Ono, Mori Kurokawa, Yoichi Motomura, Hideki Asoh. A Context-Aware Movie Preference Model Using a Bayesian Network for Recommendation and Promotion. Proceedings of the llth international conference on User Modeling,LNAI 4511,2007, pp.247-257.   
[20]Tao Gu, Hung Keng Pung,Da Qing Zhang. A Bayesian Approach for Dealing with Uncertain Contexts.Proceedings of the Second International Conference on Pervasive Computing, Vienna, Austria: Austrian Computer Society, 2004.   
[21]Zhiwen Yu, Xingshe Zhou, Daqing Zhang,et al. Supporting Context-Aware Media Recommendations for Smart Phones. IEEE Pervasive Computing,2006, 8(34):p68-75.   
[22]Han-Saem Park, Ji-Oh Yoo,and Sung-Bae Cho.A Context-Aware Music Recommendation System Using Fuzzy Bayesian Networks with Utility Theory. Proceedings of Fuzy Systems and Knowledge Discovery, China, 2006, pp. 970-979   
[23]Brian Clarkson, Kenji Mase,and Alex Pentland. Recognizing User's Context from Wearable Sensors: Baseline System. Proceedings of the Fourth International Symposium, 2000, pp. 69 - 75   
[24]Thad Starner, Bernt Schiele,and Alex Pentland. Visual Contextual Awareness in Wearable Computing. Proceedings of the Second International Symposium on Wearable Computers, Pitsburgh, PA, USA, 1998, pp. 50-57.   
[25]Karthik Gopalratnam, Diane J. Cook. Active LeZi: An Incremental Parsing Algorithm for Sequential Prediction.Proceedings of the Florida Artificial Intelligence Research Symposium,Florida, USA, 2003, pp. 38-42.   
[26]Tong Zhang, Jue Wang,Liang Xu, Ping Liu. Fal Detection by Wearable Sensor and One-Class SVM Algorithm. Lecture Notes in Control and Information Sciences,2006   
[27]Andreas Buling,Jamie A.Ward,Hans Gellersen,et al. Eye Movement Analysis for Activity Recognition. Ubicomp 2009   
[28]Carl G. Looney.Fuzzy Petri nets for rule-based decision making. IEEE Transactions on Systems, Man and Cybernetics,1988,18(1): 178-183.   
[29]Shyi-Ming Chen,Jyh-Sheng Ke,Jin-Fu Chang.Knowledge Representation Using Fuzzy Petri Nets. IEEE Transactions on Knowledge Data Engineering,1990, 2(3): 311-319.   
[30]Meimei Gao, Mengchu Zhou, Xiaoguang Huang, Zhiming Wu. Fuzzy Reasoning Petri Nets. IEEE Transactions on Systems, Man, and Cybernetics-Part A: Systems and Humans,2003,33(3): 314-324.   
[31]Huaiqing Wang, Changjun Jiang, Shaoyi Liao. Concurrent Reasoning of Fuzzy Logical Petri Nets Based on Multi-task Schedule.IEEE Transactions on Fuzzy Systems,2001,9(3):444-449.   
[32]Shyi-Ming Chen. Fuzzy Backward Reasoning Using Fuzzy Petri Nets. IEEE Transactions on Systems, Man and Cybernetics- Part B: Cybernetics,2000,30(6): 846-855.   
[33]Jongyi Hong, Eui-Ho Suh, Junyoung Kim, et al. Context-aware System for Proactive Personalized

Service based on Context History. Expert Systems with Applications,2009,36(4):pp.7448-7457. [34] Jason J. Jung,Hojin Lee,Kwang Sun Choi. Contextualized Recommendation Based on Reality Mining from Mobile Subscribers. Journal of Cybernectics and Systems,2009,40(2):pp.160-175. [35] Gediminas Adomavicius，Alexander Tuzhilin. Toward the Next Generation of Recommender Systems:A Survey of the State-of-the-Art and Possible Extensions. IEEE Transactions on Knowledge and Data Engineering,2005,17(6): pp.734-749. [36] 李德毅，杜鹤．不确定性人工智能．国防工业出版社,2005.7

作者简介：

叶剑: 中国科学院计算技术研究所，普适计算研究中心，高级工程师，jye $@$ ict.ac.cn朱珍民： 中国科学院计算技术研究所，普适计算研究中心副主任，正研级高级工程师陈援非： 中国科学院计算技术研究所，普适计算研究中心，助理研究员何哲： 中国科学院计算技术研究所，普适计算研究中心，工程师