# 完整的嗅觉神经通路假设及建模

张锦，田恬恬1

(湖南师范大学 信息科学与工程学院,湖南 长沙410081)通讯作者：张锦,E-mail:mail_zhangjin@163.com

摘要：嗅觉神经通路研究是嗅觉研究的基础，对脑科学研究同样具有多方面的重要意义。综合已有相关研究成果，探索了完整的嗅觉神经通路假设。该神经通路包括以嗅球层为核心的前端部分、以内嗅皮质为核心的中端部分和以齿状回为核心的后端部分。在此基础上，本文构建了完整的嗅觉神经通路结构模型，并进行了初步分析。

关键词:嗅觉神经通路;嗅球;内嗅皮质;齿状回;仿生模型

中图法分类号：TP399

# Hypothesis and Modeling of Complete Olfactory Neural Pathway

ZHANG Jin'， TIAN Tian-Tianl

1(College of Information Science and Engineering,Hunan Normal University,Changsha 410081,China)

Abstract:Theresearchontheolfactoryneuralpathwayis thebasisofolfactoryresearch,whichisofgreatsignificance inmanyaspects of brainscience.Basedontheexistingresearchresults,hypothesisabouttheompleteofactorynuralpathayasexplord,ndthe neuralpathwayincludesafrontpartwiththeofactorybulblayerasthecore,amiddlepart withtheentorinalcortexasthecorenda rearpartwiththedentategyrusasthecore.Basedonthis,acompletestructuralmodeloftheolfactoryneuralpathwayisconstructedand analyzed in this paper.

Key words:olfactory neural pathway;olfactory blub;entorhinal cortex; dentate gyrus; bionic model

提及嗅觉，令人惊讶的是，几乎所有生物都会在其外部环境中对气味做出反应，这种感知能力的存在提供了大量有关食物、危险、交配、保卫其领土等非常具体而有用的信息。因此，有关嗅神经通路的研究对理解由气味引发的一系列机体活动具有重要意义。

研究者通常会基于嗅觉神经通路分层的特点来构建嗅觉神经通路仿生模型，比较具有代表性的模型有K系列模型、Li模型、Liljenstrom 模型和一些生物物理模型。Liljenstrom 模型[模拟了三层的嗅皮质，由浅到深分别是，第一层：前馈抑制单元层（NI层)，包括抑制性中间神经元和从嗅球传入的神经纤维；第二层：兴奋单元层（NII层)，主要包括兴奋性的锥体细胞；第三层：反馈抑制单元层（NIII层)，包括锥体神经元和中间神经元。Li模型[2]是嗅球层和嗅皮层的耦合模型，嗅上皮传入的气味信息在嗅球层被编码为振荡模式，当来自嗅球层的气味模式与嗅皮层中存储的某个气味记忆模式相匹配时，这两种模式会形成共鸣振荡，从而，这个气味就会被模型识别。近年来，生物物理模型受到了许多研究者的青睐，这种模型不仅考虑各类细胞真实的细胞形态和突触特性，也考虑各种离子通道的动力学机制，通常采用的是多房室模型（multicompartmentalmodel)。房室模型是将空间上连续的单个神经元分成离散的多个房室，房室之间相互连接后整体描述神经元的时空变化[3]。Linster等人构建嗅球层到嗅皮层的多房室模型，用于研究嗅觉系统如何从背景气味中分离出目标气味[4]。De Almeida等人同样构建嗅球层到嗅皮层的多房室模型，用于研究输入到嗅球层和嗅皮层的胆碱能如何调节气味的表示[5]。Li和Cleland 针对嗅球试图构建一个通用的多房室模型，以生成影响僧帽细胞尖峰时间的伽马振荡[6]。K系列模型从低层次到高层次逐步实现了嗅觉神经系统的模拟，包括K0、KI、KII、KIII 模型[-8]。其中，KO、KI和 KII模型是 KIII模型的基本组成单元，KII模型真实地模拟了整个嗅觉神经系统。然而，这些模型对嗅觉神经通路的模拟局限在气味信息的过程，没有涉及由气味信息引发高级脑活动的相关脑区。

本文依据解剖学知识总结嗅觉神经通路通向高级脑区的神经传导机制，将其分为三部分：前端、中端和后端，并分别针对每一部分的关键组件展开模型研究。

# 1嗅觉神经系统通路建设

本文梳理了嗅觉神经系统到颞叶的神经通路，如图1所示，整体可分为三个部分：前端、中端和后端。前端是基本的嗅觉神经系统，负责气味信息的基础处理，气味分子作用于嗅上皮（olfactory epithelium，OE)，嗅上皮将化学信号转化为电信号，传递到嗅球层（olfactorybulb，OB)，嗅球层对气味信息进行编码，再由嗅皮层（olfactorycortex，OC）对气味信息做进一步的处理，为嗅觉的产生、记忆等做准备，前端的嗅皮层主要是指前嗅核（anterior olfactory nucleus，AON）和梨状皮质（piriform cortex，PC）。中端也是嗅皮层的一部分，包括杏仁核（amygdala）和内嗅皮质（entorhinalcortex，EC)，接受来自嗅球层和梨状皮质的投射。杏仁核根据气味信息引发一系列的情绪反应[9]。例如，当闻到清甜的花香，杏仁核调节产生积极的情绪反应，心情变得愉悦。内嗅皮质处理气味信息，为输入到海马形成记忆做准备。后端指的是海马（hippocampus)，主要由齿状回（dentate gyrus，DG）、CA3和CA1组成，是形成记忆的场所，最终由CA1经下托（subiculum）返回至内嗅皮质。最后，内嗅皮质将记忆信息投射到相关脑区存储，具体存储过程有待进一步研究。有研究指出，长期记忆并非存储在内侧颞叶中，而是经内侧颞叶编码处理之后，返回存储在最初参与处理各种感觉类型信息的新皮质区域[I0]。杏仁核调节情绪的过程与嗅觉本身无关，因此，在嗅觉神经通路的研究中，忽略与杏仁核相关的神经通路，主要研究气味信息进入颞叶脑区后产生记忆的过程。

![](images/9a679d88c9f3d552828a801f820cbcf08f6d00c7e28b020a782dba421c949714.jpg)  
图1嗅觉神经通路

# 1.1 前端嗅觉神经通路

根据层状排列方式划分，前端嗅觉神经通路从外到内主要由嗅上皮、嗅球层和嗅皮层组成。如图2所示，气味分子进入鼻腔后，与嗅上皮中特定嗅感受器细胞（olfactory receptor cell，ORC，也叫作嗅感觉神经元，olfactory sensory neuron，OSN）上的气味受体（odorant receptor，OR）结合，分布在同一个嗅感觉神经元上的多个气味受体属于同一种类型，结合后被激活的气味受体通过嗅神经将气味信息传递到嗅球层的嗅小球（glomerulus，GL)，或者中途经过球周细胞（periglomerular cell，PG）预处理后到达嗅小球，需要注意的是携带相同气味受体的嗅感觉神经元将气味信息汇聚到同一个嗅小球。嗅小球中被激活的僧帽细胞（mitral cell,M）和颗粒细胞（granule cell，Gr）相互作用产生局部振荡，气味信息的表达形式转换为嗅小球活动的空间分布模式[1]。僧帽细胞通过外侧嗅束（lateral olfactory tract，LOT）将处理后的气味信息传递到前嗅核和梨状皮质，进而到达嗅觉中枢，引发嗅觉的产生和其他一系列高级脑活动。前嗅核和梨状皮质通过中嗅束（medialolfactory tract，MOT）向嗅球层产生反馈信息，梨状皮质也可通过中嗅束向前嗅核发出反馈信息。

目前，关于LOT到达的嗅皮质区域定义比较模糊，没有具体的定论，大致包含前嗅核、梨状皮质、杏仁核、内嗅皮质、嗅结节（olfactory tubercle，OT）等区域[12-14]。其中，梨状皮质是直接接受嗅球投射区域最大的嗅皮质。

梨状皮质由锥体细胞（pyramidal cell，P）、半月细胞（semilunar cell，SL）和一些中间神经元构成。锥体细胞有两种类型，分别是浅层锥体细胞（superficial pyramidal cel,SP）和深层锥体细胞（deep pyramidalcell,DP)，是梨状皮质主要的输入和输出细胞。两种锥体细胞的顶树突和半月细胞的树突都可接受来自外侧嗅束和梨状皮质其他细胞的投射，但只有两种锥体细胞的轴突可投射到梨状皮质以外的区域，例如嗅球、杏仁核、内嗅皮质等区域，而半月细胞的轴突仅作用于两种锥体细胞的胞体[15]。中间神经元主要分为两类，介导梨状皮质内部的前馈抑制（feedforward inhibition，FF）的神经元和介导梨状皮质内部的反馈抑制（feedbackinhibition，FB）的神经元。

![](images/094891bf43d592f0eb76d788e908c223f250d4cb648a273c199b00c1c26b926a.jpg)  
图2前端嗅觉神经通路简化结构图

# 1.2 中端嗅觉神经通路

颞叶（temporal lobe）主要包含了嗅觉神经通路的中端和后端部分。根据颞叶的功能机制，颞叶中与嗅觉相关的结构主要是杏仁核、海马旁回和海马，其中，位于海马旁回的内嗅皮质和下托主要为海马提供输入和输出。

不考虑杏仁核调节情绪的过程，中端嗅觉神经通路主要包含嗅球和梨状皮质向内嗅皮质的投射通路，以及内嗅皮质的反馈投射过程[16-19]。也有文献提到，位于颞叶边缘的梨状皮质会将各种气味特征合并为气味对象，投射到内嗅皮质[20]。

内嗅皮质通常被分为六层，其中，第I、Ⅱ和III层为浅层、第IV、V和VI层为深层。内嗅皮质的浅层接受各种皮质区域的输入后，主要由Ⅱ和III层向海马进行投射，海马将处理后的信息返回到内嗅皮质的深层，再由深层投射到其他皮质区域。更为详细的过程是，II层主要向齿状回和CA3 提供输入，II层主要向CA1 和下托提供输入，CA1和下托的输出主要投射到内嗅皮质的深层[21]。文献[2]在研究内嗅皮质的输入输出时指出，嗅觉信息的输入会有选择地投射到内嗅皮质的I层和II层。

另外，根据其独特的细胞结构和连接模式，内嗅皮质可分为内侧内嗅皮质（medial entorhinal cortex，MEC）和外侧内嗅皮质（lateral entorhinal cortex，LEC)。MEC 在空间导航中起着重要作用，LEC 则向海马提供感觉相关信息[23]。文献[24-26]也特别指出，嗅球和梨状皮质向内嗅皮质的投射集中在LEC。如图3所示，内嗅皮质中与海马投射回路密切相关的两种神经元是星状细胞（stellate cell）和锥体细胞[27]。星状细胞位于ⅡI层，主要投射区域是海马的齿状回和CA3,锥体细胞不仅向CA1和下托提供输入，也投射到海马以外的其他脑区。星状细胞和锥体细胞属于兴奋性神经元，内嗅皮质中也分布有多种抑制性的中间神经元，与兴奋性神经元相互作用形成局部振荡回路。

![](images/7363a724773c0c5089e91fb1f0c5e36f1153b0712a628ec1b74c95adfc9530ed.jpg)  
图3内嗅皮质的分层及两种主要神经元

主要由内嗅皮质构成的中端部分是连接前端和后端嗅觉神经通路的桥梁，嗅球和梨状皮质是嗅觉信息投射到颞叶的神经通路中的关键部分，并且只考虑主要的投射关系，忽略掉次要的，因此，需要明确嗅球和梨状皮质到内嗅皮质的投射过程，才能完整构建出这条嗅觉神经通路。然而，关于嗅球和梨状皮质向其他脑区的投射情况比较模糊，研究相对比较少，缺少具体神经元投射回路的描述，无法得知嗅球和梨状皮质到内嗅皮质的神经元连接情况。尽管存在不明确的投射回路，仍然可以尝试基于已有的研究成果分别假设嗅球和梨状皮质到内嗅皮质的连接情况，并通过实验来验证假设是否具有合理性。

嗅球和梨状皮质中主要的神经元投射神经元分别是僧帽细胞和锥体细胞，内嗅皮质中主要由星状细胞接受各种感觉信息的输入后并投射到齿状回。在构建神经元连接的过程中，常用的连接方式有一对一连接、全连接和随机连接三种方式，但是在真实的神经通路中，神经元之间的连接具有特异性，并非以全连接的方式连接到所有的神经元，因此，不考虑全连接的方式。当然，随机连接只是模拟神经元之间看似随机的连接情况，不代表神经元之间的连接是杂乱无章的。选择僧帽细胞、锥体细胞和星状细胞这三种主要的神经元，可以分别尝试以一对一连接和随机连接的方式来构建嗅球、梨状皮质到内嗅皮质的连接。

# 1.3 后端嗅觉神经通路

后端部分是有关嗅觉记忆产生的神经通路，主要涉及颞叶中的海马结构。如图4所示，是海马内部的投射回路[28]。内嗅皮质向海马提供主要的皮质输入，海马内部的投射回路很多，其中最经典、同时也是最主要的是“三突触回路（trisynaptic circuitry）”,突触1：内嗅皮质向齿状回的投射，称为前穿质通路（perforant path，

PP)；突触2：齿状回向CA3的投射，称为苔藓纤维（mossy fibres，MF)；突触3：CA3向CA1的投射，称为谢弗尔侧支（schaffer collateral，SC)。另外，内嗅皮质可直接投射到CA3、CA1和下托，CA3向齿状回输出反馈信息，CA3自身也存在递归投射。下托是海马的主要输出结构，进而将信息传递到内嗅皮质，CA1也可直接将信息投射到内嗅皮质。在神经通路的相关研究过程中，通常会选择主要的投射回路：EC一>DG—>CA3- $\mathrm { \Sigma } \mathrm { > }$ CA1一>下托一 ${ \mathrm { - } } { \mathrm { } } { \mathrm { E C } }$ 。

![](images/e1e1e11ee8bc051d73ffc23df59c727756e40d8235ead03aa97cda8db5a7ab09.jpg)  
图4海马投射回路

在主要的投射回路中，齿状回是海马中信息输入的第一个结构，具有模式分离（pattern separation）的功能，通常被认为是处理最终用于产生记忆的信息的第一个环节，通过不同的神经回路来分离相似记忆的神经表示，以优化记忆的存储和后来的检索[29]。也就是说，齿状回是信息的预处理器，为CA3的后续处理做准备，在记忆的产生中起着非常重要的作用。当前输入信息的模式与过去的某个模式有相同的成分时，对相同成分的响应会受到抑制，从而达到模式分离的效果，这使得海马可以创建相似经历的独特表示，以最大程度减少对特定记忆存储和取回的干扰[30]。齿状回的存在，使得记忆的产生有条理，能够记忆很多相似的场景和事物，因此，研究记忆的产生机制时，齿状回是首要研究对象。

齿状回的主要神经元是颗粒细胞，主要接受来自内嗅皮质的投射。颗粒细胞的轴突不仅投向一些中间神经元，例如篮细胞、苔藓细胞等，同时也聚结纤维束离开多形层，延伸到CA3的透明层（statum lucidum），与CA3 的锥体细胞建立突触连接，并且，颗粒细胞对CA3的投射是齿状回向其外部脑区域投射的唯一方式。此外，颗粒细胞之间不存在相互连接，通过与齿状回内其他类型细胞的连接实现间接相互作用。

# 2嗅觉神经通路模型

根据前面对嗅觉神经通路的研究分析，忽略次要的结构和连接，构建嗅觉神经通路模型如图5所示。前端部分包含嗅上皮、嗅球、前嗅核和梨状皮质，中端部分包含内嗅皮质，后端部分包含齿状回，其中嗅球、梨状皮质到内嗅皮质的连接假设为一对一连接或随机连接。

另外，前端模型和中端模型的构建基于神经团理论，神经团理论由 Freeman 教授提出，指的是相似的神经元组成的细胞团具有相似的功能和一致的特性，可以作为整个神经系统的组成模块[31]。Feeman 的K系列模型就是基于神经团理论建立的，K0模型是基本模块，表示相似神经元组成的具有相似功能和一致特性的细胞团，除 KO模型外，其他层次模型的组成中均包含低层次模型构成的模块。KI模型是由两个KO模型互连

组成，KII模型由两个KI模型互连组成，KI和KII模型一般也都作为基本模块，不单独作为模型来分析。  
KIII 模型由KO、KI、KII通过前馈、延时反馈等方式构成，模拟了整个前端嗅觉神经通路。

![](images/d6b433e868e03305d3cdac10c76d617a367ea5bdc9cae78cc78a7e6fbcaa34cd.jpg)  
图5嗅觉神经通路模型

# 2.1 基于KII模型的前端模型

根据 Freeman 的研究成果，本文以KII模型为基础构建了前端嗅觉神经通路模型，如图6所示。

![](images/adae8e77dcc7610bbab7974d7d04acfb79ab4f900f9b63dd429fa2c5d41813b2.jpg)  
图6基于KIII模型的前端模型拓扑结构

基于KI模型的前端模型涵盖了前端嗅觉神经通路的关键部分。R对应于传入气味信息的嗅感受器，P对应于预处理气味信息的球周细胞，M和G分别对应于僧帽细胞和颗粒细胞，共同完成对气味信息的空间变换，E和I分别对应于前嗅核中的兴奋性神经元和抑制性神经元，PC层的关键部分分别对应于梨状皮质的不同部分，其中，Ff对应于介导前馈抑制的中间神经元，Py对应于提供梨状皮质主要输入输出的锥体细胞，Fb对应于介导反馈抑制的中间神经元，另外，模型不同部分之间加入连接和延迟。每一个R代表一类嗅感受器，投射到一个嗅小球，可直接投射或是通过P完成投射。Stettler等人对梨状皮质关于气味反应的光学成像显示，梨状皮质中的每个神经元只对特定的气味有响应，来自嗅球层僧帽细胞的投射在空间分布上没有明显的空间偏好，呈现出不连续的接受域，不同的气味激活一个独特、离散的梨状皮质神经元集合[32]。因此，可采用随机连接的方式模拟M到Py的投射过程。在PC层内部，Ff也接受来自M的投射，Ff的存在用于调节来自 M的兴奋性输入，Py发出兴奋性连接，Fb 发出抑制性连接，Py和Fb 的局部互连形成振荡回路。PC 层向 AON层和OB层的反馈，由Pr分别投射到I和G。

# 2.2 基于神经团的中端模型

中端嗅觉神经通路的结构主要是内嗅皮质，本文基于神经团理论构建以内嗅皮质核心的中端嗅觉神经通路模型，如图7所示。该内嗅皮质模型涵盖了内嗅皮质的主要神经元。内嗅皮质中的星状细胞接受感觉信息输入并投射到齿状回，星状细胞与一些中间神经元相互作用形成局部振荡回路。模型中的S对应于星状细胞，I对应于中间神经元。

![](images/9a3a4ee7d095df35a1c835af546ed60f41cc982e48c46a4f0d042f361cca02a8.jpg)  
图7基于神经团的中端模型拓扑结构

# 2.3 基于齿状回的后端模型

后端嗅觉神经通路主要涉及到海马结构，海马的记忆产生过程一直是个研究难点，因此，对海马的研究可以遵循由简单到复杂、由局部到整体的步骤，本文重点展开对海马传入信息的第一个结构，齿状回的模型研究。

如图8所示，基于仿生学原理，在齿状回模型的构建中，选择颗粒细胞（GC）、苔藓细胞（mossy cell,MC）、篮细胞（basket cell，BC）和轴突投射到前传质通路的门层细胞（hilar cellwith axonal projections to theperforant path，HIPP)，前两种是兴奋性神经元，后两种是抑制性神经元。这四种神经元在齿状回所有神经元的数量中占绝对优势，并且其他种类神经元的相关生理学数据较少[33]。模型较为完整地模拟了齿状回内部的神经通路，GC 是齿状回的主要输入神经元，所有的GC都可接受来自内嗅皮质的输入，所有的 BC 和 $1 5 \%$ 的MC 也将接受内嗅皮质的输入，但GC之间不存在直接连接，可通过与其他类型神经元的连接实现间接互连。另外，模型内部连接丰富，除了BC不投射到HIPP的情况外，这四类神经元之间存在互连，并且MC 和 BC在同类型神经元之间也存在连接。

![](images/1c4612ee2b26ace2fdd648aeb38fa49fec0f5ae15ccf69e8649f32e7e4378348.jpg)  
图8基于齿状回的后端模型拓扑结构

# 3结论

本文整理总结了嗅觉神经通路的神经传导机制，这条神经通路分为前端（嗅上皮、嗅球、前嗅核、梨状皮质）、中端（杏仁核、内嗅皮质）和后端（海马、下托)。其中，嗅球、梨状皮质到内嗅皮质的投射过程是未知的，假设其神经元连接方式为一对一连接或随机连接。接着，本文提出了嗅觉神经通路模型，分别从前端、中端和后端展开模型研究。基于KIII的前端模型是对 Freeman KIII模型的改进，扩展了对梨状皮质模拟的基本单元。基于神经团的中端模型主要以内嗅皮质为核心，结合内嗅皮质中主要的神经元，构建分布式的KII模型。基于齿状回的后端模型考虑了主要神经元之间的连接情况。

本文提出的嗅觉神经通路模型主要针对这条神经通路上的关键部分进行建模，尚未覆盖到所有的结构，并且嗅球、梨状皮质到内嗅皮质的真实连接情况是未知的。接下来的工作将跟进这条嗅觉神经通路有关神经生理学的研究进展，确定通路中的连接情况、神经元之间的比例等。另外，分别完善前端、中端和后端模型的结构，利用神经生理学数据确定模型的参数，并将三部分模型进行整合，利用小世界网络理论、脑电同步指标等对模型进行优化研究，分析模型的动力学特性，进行仿生度的评估，进而将模型应用到多个领域场景，分析模型的功能特点。

# References:

[1]Liljenstrom H.ModelingtheDynamicsofOlfactory CortexUsing SimplifiedNetwork UnitsandRealisticArchitecture. International Journal of Neural Systems,1991,2(1):1-15.   
[2]LiZ,HertzJ.Odorrecognitionandsegmentationbycoupledolfactorybulbandcorticalnetworks.Neurocomputing，1999, (26-27):789 - 794.   
[3]Zhang ZF,HanCJ,Liu LH.Compartmental ModelComputationandOptimizationBaesdon Single Thalamocortical Neuron. Science Technology and Engineering,2009,9(10):2564-2568 (in Chinese with English abstract).   
[4]LinsterC,HenryL,Kadohisa M,etal.Synapticadaptationandodor-backgroundsegmentation.NeurobiolLearn Mem,207, 87(3):352 - 360.   
[5]De AlmeidaL,IdiartM,LinsterC.Amodelofcholinergic modulationinolfactorybulbandpiriformcortex.Journalof Neurophysiology,2013,109(5):1360-1377.   
[6]LiG,ClelandTA.Generative Biophysical ModelingofDyamical NetworksintheOlfactorySystem.Methods MolBiol,2018, 1820:265 - 288. [/」YaoY，rreeman wJ.MoaeloI Dioiogicalpatern recogniuon witn spauallycnaouc aynamics.Neural Networks,199u, 3(2):153-170.   
[8]Chang HJ,Freeman WJ.Parameteroptimization inmodelsoftheolfactory neural system.Neural Networks,1996,9(l):1-14.   
[9]ObotiL,RusoETranT,etal.AmygdalaCorticofugalInput Shapes MitralCellResponsesintheAcessoryOlfactoryBulb. eNeuro,2018,5(3):ENEURO.0175-18.2018.   
[10]ClarkRE.Current Topics RegardingtheFunctionof the Medial TemporalLobe Memory System.Current Topics in Behavioral Neurosciences, 2017,37:12-42.   
[11]SporsH,GrinvaldA.Spatio-Temporal DynamicsofOdorRepresentations intheMammalianOlfactoryBulb.Neuron，2002, 34(2):301 - 315.   
[12]Giessel AJ,Datt SR.Olfactory maps,circuits adcomputations.CurrentOpinion in Neurobiology,2014,24:120-132.   
[13]Espinosa-JovelC,ToedanoR,Jimenez-HueteA,etal.Olfactoryfunctioinfocalepilepsies:Understandingmesialoal lobe epilepsy beyond the hippocampus. Epilepsia Open,2019,4(3):487-492.   
[14]MainlandD,LundstromJN,ReisertJ,etal.Frommoleculetomind:anintegrativeperspectiveonodorintensityedsin Neurosciences,2014,37(8):443-454.   
[15]YoungJCVaughanasserH,etal.AatoicalimagingoftepfocortexinpilepsyExperietaleurolog19, https://doi.org/10.1016/j.expneurol.2019.113013.   
[16]WouterloodFG，NederlofJ.TerminationsofolfactoryafferentsonlayerIandIIneuronsintheentorhinalarea: Degeneration-golgi-electron microscopic study in the rat .Neuroscience Letters,1983,36(2):105 - 110.   
[17]Shipley MT,Ennis M,Puche AC.The Rat Nervous System.New York: Elsevier,2004:923-964.   
[18]MoulyAM,ScalaGD.Entorhinalcortexstimulationmodulatesamygdalaandpirifomcortexesponses toolfactorybulbputsn the rat. Neuroscience,2006,137(4):1131-1141.   
[19]WenP,RaoX,XuLetal.CorticalOrganzationofCentrifugalAerentstothelfactoryBulb:MonoadTanssyaticTracing with Recombinant Neurotropic Viral Tracers. Neuroscience Bulletin,2019,35(4):709-723.   
[20]Barnes DC,Wilson DA.Sleep and olfactorycortical plasticity.Frontiers in Behavioral Neuroscience,2014,81-11.   
[21]CerastiE，TrevesA,GrahamLJ.How Informative AreSpatialCA3RepresentationsEstablishedbythe Dentate Gyrus?.Plos Computational Biology,2010,6(4):e1000759.   
[22]WiterMP.Organizationof theentorhinal—hippocampal system:Areviewofcurrentanatomicaldata.Hippocampus，1993, 3:33-44.   
[23]HargreavesEL.MajorDissociationBetween MedialandLateralEntorhinalInputtoDorsalHippocampus.Science2005, 308(5729):1792- 1794.   
[24]McnaughtonBL,BatagliaFP,JensenO,etal.Pathintegrationandtheneuralbasisofthe"cognitivemap".NatureReviews Neuroscience,2006,7(8):663-678.   
[25]Squire LR.Encyclopedia of Neuroscience.California: Elsevier, 20o9:101 - 106.   
[26]Cleland TA,Linster C. Smell and Taste. New York: Elsevier,2019:79-96.   
[27]McnaughtonBL，BattgliaFP,JensenO,etal.Pathintegrationandtheneuralbasisofthe"cognitivemap".NatureReviews Neuroscience,2006,7(8):663-678.   
[28]SmallSA,Schobel SA,BuxtonRB,etal.Apathophysiologicalframeworkofhippocampal dysfunctioninageinganddisease. Nature Reviews Neuroscience,2011,12(10):585-601.   
[29]HummosA,FranklinCC,NairS.Intrinsicmechanismsstabilizeencodingandrerievalcircuitsdiferentiallinaipocapal network model. Hippocampus,2014,24(12):1430 - 1448.   
[30]Knierim J. The hippocampus. Current Biology,2015,25(23):R1116 - R1121.   
[31]ZhangJ,ZhuSW,WangY,etal.ResearchonOlfactoryNeural SystemModelBasedonBionics.JouralofSystem Siulation, 2011,23(08):1590-1593+1597 (in Chinese with English abstract).   
[32]Stettler DD,Axel R.Representations of Odor in the Piriform Cortex.Neuron,2009,63(6):854 -864.   
[33]MorganRJ,Santhakumar V,Soltesz I.Modeling thedentate gyrus.Progress in Brain Research,2O07,63:639-658.

# 附中文参考文献：

# 张锦等：完整的嗅觉神经通路假设及建模

[3]张召峰，韩婵娟，刘利华．基于单个丘脑皮层神经元的房室模型计算与优化．科学技术与工程，2009，9(10)：2564-2568.  
[31]张锦，朱尚武，王莹等．面向仿生的嗅觉神经系统建模研究．系统仿真学报，2011，23(08)：1590-1593+1597.