# 精细化交叉口数据模型的建模方法

张腾'，黄 敏1，张汉林²

(1.中山大学 智能交通研究中心广东省智能交通系统重点实验室，广州 510275；2.招商银行股份有限公司风险管理部，广东 深圳 518000)

摘要：针对现阶段交通网络数据模型对交叉口处物理几何形态以及交通组织渠化描述不足的现状，提出了一种面向精细化交叉口的路网数据模型，从物理、逻辑和几何三个层面对交叉口的逻辑拓扑、标线规则等信息进行描述，以支持交通分析的计算需求。同时，提出了一种基于物理拓扑和逻辑拓扑，采用基于要素的线性参考技术，构建交叉口几何拓扑的建模方法。最后对平面交叉口进行建模实验，实验结果表明该方法能够有效地支持精细化交叉口几何数据的自动生成。

关键词：数据模型；平面交叉口；分层拓扑；智能交通中图分类号：Tp391.9;U491 doi:10.19734/j.issn.1001-3695.2018.09.0763

Modeling approach of precise intersection data model

Zhang Teng1,Huang Min1, Zhang Hanlin² (1.Guangdong Provincial Key Laboratory of Intellgent Transportation System,ITSResearch Center，Sun Yat-sen University,Guangzhou510275,hina;2.Risk Management Dept,China Merchants Bank,ShenzhenGuangdong51800, China)

Abstract:Aimingatthedeficiencyofphysicalgeometryandtraficorganizationcanalizationdescription intrafc network data model at present,this paper presented aroad network data model oriented to refined intersections.And the model describedlogical topologyandruleofmarkingsofintersections fromphysical,logicaland geometriclevels.Itcouldalso support thecalculation requirements oftrafic analysis.Atthe same time,based on physical topologyand logical topology, the paper presented a modeling method of intersection geometry topology by using linear reference technology based on elements.The results showthatthis methodcan efectivelyrealize theautomatic generationof precise intersection models.

Key words: data model; planar intersection; layered topology; intelligent transportation

# 0 引言

可计算GIS-T是近年来智能交通研究的重要方向I，构建可计算GIS-T系统的第一步就是在计算机中实现对交通对象的表达存储，即构建数据模型。同时，道路平面交叉口作为城市道路系统的重要组成部分，是管理、组织道路交通的控制点。交叉口的交通状况也能很大程度上反映路网的交通状态。因此，精细化的交叉口数据模型是可计算GIS-T实现的关键。在可计算GIS-T平台上，交通领域的各类分析计算包括交通容量计算、交通状态计算、交通需求分析、交通仿真等都离不开精细化交叉口数据模型的支持。

现阶段，国内外对于交叉口模型的研究，绝大多是是将交叉口作为路网的一部分进行表述，因此需要从路网数据模型的相关研究中梳理研究现状。现阶段的路网数据模型研究主要分为路段级路网数据模型和车道级路网数据模型。在路段级路网数据模型方面，主要研究包括 Sheffi提出的节点一弧段模型，Li等人提出的基于有向路段的路网模型以及GDF模型[2-4I，该类模型主要面向交通规划、运输管理以及路段级的交通出行方面的应用，对路段之间的逻辑连通关系描述较多，但仅将交叉口抽象为节点，并把交叉口作为判断交通流中断的依据，描述各方向交通流在交叉口处的连通关系，且对道路物理几何的描述比较粗略，不能够体现交叉口内部的组织渠化及交叉口拓宽等情况。在车道级路网数据模型方面，各类数据模型[5-7对于道路交通的描述细化到了车道级，能够有效地支持车道间的逻辑连通关系表达，但模型对交叉口内部几何信息的描述较为粗略，无法实现对交叉口处物理几何形态以及交通组织渠化的描述。

上述所述的模型研究，都将交叉口作为路网的一个对象进行建模，建模过程中重点放在了交通流、车道的连通关系等逻辑拓扑方面，对于交叉口内部的几何形态、组织渠化以及交叉口进出口道拓宽等属性描述较为缺乏，对左转待转区、右转渠化道、左转导向线等内部对象的考虑很少。部分模型涉及到交叉口几何形态表达的也只是停留在交叉口大致轮廓形态方面，非常粗略。此外，许多模型缺乏标准、统一、准确的语义表达，无法实现模型的整体化表达以及更好地支撑外部应用。

因此，本文以可计算GIS-T平台上交通领域各类计算分析对于交叉口数据模型的需求入手，对交叉口进行单独建模。并基于已有的物理基础拓扑和逻辑拓扑，采用线性参考和线性偏移的技术，探究系统构建交叉口的几何拓扑的方法。

# 1 精细化交叉口数据模型

通过对可计算GIS-T平台上各项交通计算需求进行分析，如信控优化、交通仿真等[8\~III，可知模型需要描述交叉口内部几何形态、逻辑关联等情况。因此，本研究将交叉口描述为物理拓扑、逻辑拓扑、几何拓扑组成的整体。其中物理拓扑描述交叉口的基本骨架，包括描述道路单元在空间上的物理基础属性和连通关系。逻辑拓扑基于物理拓扑，实现对标志标线传递的交通规则抽象表达。几何拓扑则通过构建承载交通规则的标志标线，利用标志标线的样式、颜色等表观信息反映一定的交通规则。同时模型采用统一的语义化表达，实现模型的整体性关联及支撑计算。三层拓扑模型示意图如图1所示。

![](images/5a40ec1c5850ad5b30500e5c344ff592d6bdc6b6417959e389d37b78c07ce445.jpg)  
Fig.1Three-level topology model

# 1.1物理拓扑

物理基础拓扑是精细化交叉口数据模型的基础，包含路段节点和路段两个组成部分，用 $G _ { p } = ( V , E )$ 表示，其中 $V = \left\{ \nu _ { i } \right\}$ 为路段节点集， $\nu _ { i }$ 为路段节点， $\nu _ { i }$ 包含属性edge， $\nu _ { i }$ .edge表示与路段节点 $\nu _ { i }$ 相连的路段集合； $E { = } \{ e _ { i } \}$ 为路段集， $\boldsymbol { e } _ { i }$ 表示连接路段节点 $\nu _ { m }$ 和 $\nu _ { n }$ 的路段。

路段是无向的，但为了方便后续对于几何拓扑的描述，引入方向路段的概念，定义 $e _ { i } ^ { t } ( \nu _ { m } )$ 为路段 $e _ { i }$ 中以 $\nu _ { m }$ 为终点的方向路段， $e _ { i } ^ { f } ( \nu _ { m } )$ 为路段 $\boldsymbol { e } _ { i }$ 以 $\nu _ { m }$ 为起点的方向路段，$e _ { i } ^ { f } \left( \nu _ { m } \right) = e _ { i } ^ { t } \left( \nu _ { n } \right)$ ，则 $e _ { i }$ 包含属性路段节点adjnode、允许行驶的方向路段diredge、道路类型roadtype等。物理拓扑的示意图如图1（a）所示。

# 1.2逻辑拓扑

逻辑拓扑是交叉口中交通规则的抽象表达，用$G _ { l } = ( A , L , L C L , L C V )$ 表示，其中 $A = \{ a _ { i } \}$ 表示有向路段集， $a _ { i }$ 为有向路段，方向为路段交通流向； $L = \{ l _ { i } \}$ 表示车道集， $l _ { i }$ 表示车道，车道是位于有向子路段中，规定车辆运行行为的最小道路单元； $L C V = \{ l c \nu _ { i } = < l _ { f } , l _ { t } > | l _ { f } , l _ { t } \in L \}$ 表示车道的纵向连通关系集，其中 $l c { \nu } _ { i }$ 表示从车道 $l _ { f }$ 到车道 $\mathbf { \mathcal { l } } _ { t }$ 的纵向通行是允许的； $L C L = \{ l c l _ { i } = < l _ { f } , l _ { t } > | l _ { f } , l _ { t } \in L \}$ 表示车道的横向连通关系集，其中 $l c l _ { i }$ 表示从车道 $l _ { f }$ 到车道 $\mid l _ { t }$ 的横向连通关系。逻辑拓扑的示意图及相关ER图如图2和3所示。

![](images/a24ef7eb6d3dc8608972ea591288cf00fe05617377f9e09d0c9f71a403bda516.jpg)  
图1三层拓扑结构模型  
图2逻辑拓扑示意图

![](images/55f1c4c28c23494be8224287c1514aec655f52c6340e84f8fce480e6cebca697.jpg)  
Fig.2Schematic diagram of logical topology   
图3逻辑拓扑层ER图  
Fig.3ER graph of logical topology layer

# 1.3几何拓扑

几何拓扑是指交叉口中承载交通规则的标志标线的几何表达及位置关系。其中几何表达包括标志标线的几何要素类型、颜色、样式以及标志标线具体类型，位置关系是指标志标线的实际位置信息描述。

# 1.3.1几何要素类型及位置关系

几何拓扑的位置关系是标志标线的重要属性之一。在本模型中，将物理拓扑作为构建几何拓扑基准参照系，选取方向路段 $e _ { i } ^ { f } ( \nu _ { m } )$ 作为有向的参考线，对归属于路段 $e _ { i }$ 的标志标线进行位置关系描述。

交叉口的标志标线归属于不同的几何要素类型，包括点要素、线要素、面要素。其中线要素包括线段、圆弧、平行曲线、二次贝塞尔曲线，面要素在文中只包含矩形一种。不同类型的几何要素通过线性参考、线性偏移的技术在基准参照系中进行几何位置表达。用fea表示任意一种几何要素，即点要素 $p$ ，线段 $\mathbf { \xi } _ { l }$ ，圆弧 $\boldsymbol { a }$ ，二次贝赛尔曲线 $b$ ，平行曲线$p l$ 以及矩形sq，则定义fea.loc为几何要素fea在基准参照系中的位置。各几何要素类型的位置关系如下所述：

a）点要素的几何位置用三元组 $p . l o c = < l i n e , \nu e r , l a t >$ 表示。其中line为物理基础拓扑中的参考线，ver为纵向偏移距离，lat为横向偏移距离，其中顺着参考线line方向左面的偏移为正，右面的偏移为负。b）线段i的几何位置可以用二元组 $\ l . l o c = < p _ { 1 } , p _ { 2 } >$ 表示，其中 $p _ { 1 } , p _ { 2 }$ 为点要素，分别对应线段两个端点。c）圆弧 $a$ 的几何位置描述为三元组 $a . l o c { = } < p _ { 1 } , p _ { 2 } , o >$ 。其中 $p _ { 1 } , p _ { 2 } , o$ 为点要素， $p _ { 1 } , p _ { 2 }$ 对应圆弧的起终点， $\mid o \mid$ 对应圆弧的圆心。d）二次贝塞尔曲线的几何位置可记为 $b . l o c { = } { < } p _ { 0 } , p _ { 1 } , p _ { 2 } >$ ，$p _ { 0 } , p _ { 1 } , p _ { 2 }$ 为点要素， $p _ { 0 } , p _ { 2 }$ 分别为二次贝塞尔曲线的两个端点控制点， $p _ { 1 }$ 为二次贝塞尔曲线的中间控制点。e）平行曲线 $p l$ 的几何位置表述为 $p l . l o c = < l i n e , p _ { 1 } , p _ { 2 } >$ ，其中line为平行曲线的参考线， $p _ { 1 } , p _ { 2 }$ 为平行曲线的两个端点，为点要素。f）矩形的几何位置可以表述为 $s q . l o c = < p _ { 1 } , p _ { 2 } , p _ { 3 } , p _ { 4 } >$ ，其中 $p _ { 1 } , p _ { 2 } , p _ { 3 } , p _ { 4 }$ 依次为矩形的四个端点，为点要素。

# 1.3.2标志标线几何表达

路网的几何拓扑用 $G _ { g } = ( L B , P C , S L , T A , G L , R T C )$ ，其中$L B = \{ l b _ { i } \}$ 表示车行道分界线的集合， $l b _ { i }$ 表示某一条车行道分界线； $P C = \{ p c _ { i } \}$ 表示人行横道集合， $p c _ { i }$ 表示单条人行横道；${ S L = \{ s l _ { i } \} }$ 表示停止线集合， $s l _ { i }$ 表示单条停止线； $T A = \{ t a _ { i } \}$ 表示导向箭头集合， $t \boldsymbol { a } _ { i }$ 表示单个导向箭头； $G L = \{ g l _ { i } \}$ 表示导向线集合， ${ { g l } _ { i } }$ 表示单条导向线； $R T C = \{ r t c _ { i } \}$ 表示右转弯曲线集合，$r t c _ { i }$ 表示单条右转弯曲线。此处规定，当交叉口设置了右转渠化道时，将右转弯曲线纳入右转渠化道车行道分界线中进行统一表述。标志标线的示意图如图4所示。

![](images/a386aaf7243245a7502c58f68751e4d0be7440b3785b9d4006615a2bc333554f.jpg)  
图4交叉口标志标线示意图  
Fig.4Schematic diagram of intersection marking line

1）车行道分界线

在本研究中把同向车行道分界线、对向车行道分界线以及道路边缘线都统称为车行道分界线，如图5所示。

单条车行道分界线 $l b _ { i }$ 包含属性 $l o c , s t y , c o l , t y p , p o s$ ，其中，车行道分界线的类型 $l b _ { i } . t y p$ 有5种，即 $\begin{array} { r } { l b _ { i } . t y p = \left\{ \begin{array} { r l r } \end{array} \right. } \end{array}$ 展宽段车行道分界线，渐变段车行道分界线，普通路段车行道分界线，右转渠化道车行道分界线，左转待转区车行道分界线}。 $l b _ { i } . s t y$ 表示 $l b _ { i }$ 的样式， $l b _ { i } . s t y =$ {单实线,单虚线}。 $l b _ { i } c o l$ 表示 $l b _ { i }$ 的颜色，$l b _ { i } . c o l =$ {白色，黄色}。biloc表示 $l b _ { i }$ 的几何要素位置信息。各类车行道分界线 $l b _ { i }$ 均有其次序pos，lbi.pos表示 $l b _ { i }$ 的次序，对每一种类型的车行道分界线按照其进、出口道划分以后分别进行编号，编号规则为顺着交通流方向从内侧往外侧依次编号。

![](images/02dee8b73fa09356b10bf79790983ca43688d46f945f26f522748a0ef6b93732.jpg)  
图5车行道分界线示意图

2）人行横道

在本研究中人行横道的几何要素类型被视为矩形。单条人行横道 $p c _ { i }$ 包含属性 $l o c , s t y , c o l , t y p$ ，pci.sty描述人行横道的样式， $p c _ { i } . c o l$ 描述人行横道的颜色。 $p c _ { i } J o c$ 描述人行横道的几何要素位置信息。 $p c _ { i } . t y p$ 表示人行横道的类型， $p c _ { i } . t y p = \ \{ \begin{array} { r l r } \end{array} \}$ 进口道人行横道，出口道人行横道，右转渠化道人行横道}。

# 3）停止线

停止线设定在交叉口进口道处，其几何要素类型为线段。单条停止线 $s l _ { i }$ ，其包含属性 $s t y , c o l , l o c , t y p$ ， $s l _ { i . } s t y$ 表示停止线的样式，一般为单实线， $s l _ { i . } c o l$ 表示停止线的颜色， $s l _ { i . } t y p$ 表示停止线的类型。 $s l _ { i . } l o c$ 表示停止线的几何要素位置信息。

# 4）导向箭头

导向箭头设置在车道中，用于规定车辆的允许行驶方向，在本研究中将各种类型的导向箭头的几何要素类型为点要素。单个导向箭头 $t \boldsymbol { a } _ { i }$ 包含属性 $l o c , t y p , p o s , s e q$ ， $t a _ { i } . t y p$ 描述导向箭头的类型，根据国标，导向箭头类型包含11种， $t a _ { i } . l o c$ 表示导向箭头的位置信息。pos,seq分别表示纵向次序和横向次序，同一组导向箭头的纵向次序一致，对于同一个进口道（出口道）的导向箭头，顺着交通流依次编号。同一组导向箭头的横向次序，则按照从道路内侧往外侧的顺序依次编号。如图6所示。

![](images/a54619a88fb2480129ac8bf76aaacfe56c6973203dc1e543449ac6a55bee6693.jpg)  
Fig.5Schematic diagram of lane boundary   
图6导向箭头次序  
Fig.6Order of guided arrows

# 5）导向线

单条导向线 ${ { g l } _ { i } }$ 包含属性 $l o c , t y p , s t y , c o l$ ， ${ { g l } _ { i } }$ typ表示导向线的类型， $g l _ { i } . t y p =$ {左转导向线,右转导向线}。 ${ { g l } _ { i } }$ .sty 表示导向线的样式， $g l _ { i } . s t y =$ (单实线,单虚线}。 $g l _ { i } . c o l$ 表示导向线的颜色。 $g l _ { i . } l o c$ 表示导向线的几何要素位置信息。对于导向线的几何要素类型，国内外许多学者的研究表明需要根据左转车的行驶轨迹来设计，但是都没有给出具体的渠化设计方案[12,13I，因此本文利用工程中常用的二次贝赛尔曲线作为导向线的几何要素类型。

# 6）右转弯曲线

右转弯曲线规定右转车流在交叉口内部向右侧转向时不得跨越右转弯曲线或者压线行驶，右转弯曲线的几何要素类型为圆弧。单条右转弯曲线 $r t c _ { i }$ 包含属性 $l o c , s t y , c o l$ ， $r t c _ { i } . s t y$ 表示右转弯曲线的样式，一般为单实线， $r t c _ { i } . c o l$ 表示右转弯曲线的颜色，一般为白色， $r t c _ { i } . l o c$ 描述右转弯曲线的几何要素位置信息。

综上所述，几何拓扑层的ER图如图7所示。

![](images/4dd8d47dbbc20689e79fa3353ffaf068d6d5d75b4043a86bd4c4b92c23a6e027.jpg)  
图7几何拓扑层ER图

# 2 几何拓扑构建方法

在第1章的描述中，逻辑拓扑是以物理拓扑为基础通过跨尺度层次化建模的方式构建的，侧重描述交叉口处抽象的交通规则。而几何拓扑侧重于描述承载交通规则的标志标线的几何表达及位置关系。物理拓扑、逻辑拓扑和几何拓扑三者方能组成完整的精细化交叉口数据模型，现有路网模型多包含物理拓扑和逻辑拓扑，但缺少几何拓扑。因此，本小节提出了一种基于现有物理拓扑和逻辑拓扑，通过引入外部几何参数（右转弯曲线的半径、人行横道宽度等）及线性参考和线性偏移的方式，构建交叉口的几何拓扑的方法。

根据国标、地标等规范对交叉口设计的明确规定，在交叉口构建的过程中，各交叉口的几何单元之间存在着一定的关联关系，如人行横道的位置需要根据路缘石的延长线进行确定，同时人行横道的长度需要根据导流岛的定位确定。因此交叉口各类标志标线在逻辑拓扑构建几何拓扑时，需要遵循一定的推导顺序。

根据几何单元之间的关联关系，对交叉口范围内几何单元按构建次序进行排序，即包含 $\mathfrak { n }$ 个几何单元的拓扑模型可按 $F e a _ { 1 } , F e a _ { 2 } , \cdots , F e a _ { n }$ 顺序进行构建，定义 $G _ { p } ^ { ( k ) }$ 为构建第 $k$ 种几何单元 $F e a _ { k }$ 后的几何拓扑模型，则有 $G _ { g } ^ { ( k + 1 ) } = G _ { g } ^ { ( k ) } \oplus F e a _ { k + 1 }$ ， $G _ { g } ^ { ( 0 ) } = \emptyset$ ，$G _ { g } ^ { ( n ) } = G _ { g }$ ，其中 $G _ { g } ^ { ( k ) } \oplus F e a _ { k + 1 }$ 表示几何单元的叠加，即在 $G _ { g } ^ { ( k ) }$ 的基础上导入外部几何参数可构建 $F e a _ { k + 1 }$ 。进一步地可得

$G _ { g } ^ { ( k ) } = F e a _ { 1 } \oplus F e a _ { 2 } \oplus \cdots \oplus F e a _ { k }$ 。符号 $\oplus$ 为左结合运算符。

构建几何拓扑的具体步骤如下：

a）根据逻辑拓扑计算 $\sum l _ { j } . w i d$ 得出路缘石位置，引入右转弯曲线的半径 $r t c _ { i }$ .rad作为外部几何参数，构建右转弯曲线rtc; ;b)根据逻辑拓扑判断是否存在右转渠化道，并确定右转渠化道车行道分界线进口道端点与出口道端点的位置及车道数，构建右转渠化道车行道分界线；c)引入外部几何参数人行横道内侧边线与出口路段的偏移距离 $p c _ { 1 } . d i s$ 以及人行横道的宽度 $p c _ { 1 } . w i d$ ，构建人行横道 $p c _ { i }$ ：d）引入停止线与路段 $e _ { 2 }$ 间的偏移距离 $s l _ { 1 } . d i s$ ，构建停止线 $s l _ { i }$ ;e）引入外部几何参数包括展宽段的长度slen，渐变段长度tlen，以及普通路段长度 $n l e n$ ，构建展宽段、渐变段、普通路段车行道三类分界线；f）引入外部几何参数 $t a _ { i } . d i s$ 表示导向箭头与停止线的距离，并且认为导向箭头是设置在车道的正中间，构建导向箭头 $t { { a } _ { i } }$ ;g）引入车行道分界线的半径 $l b _ { 1 0 } . r a d$ 作为外部几何参数，构建左转待转区车行道分界线；h)以起始车行道分界线端点、出口道最外侧车行道分界线端点及其车行道分界线延长线交点作为控制点，构建导向线。

![](images/51c07147d6fd34262d03931e8779b0dbf6722a1bf0f63db2eb12274d82ebf2b2.jpg)  
Fig.7ER graph of geometric topological layer   
几何拓扑构建的整体流程如图8所示。  
图8几何拓扑构建流程  
Fig.8Process of geometric topology construction

# 3 实例应用

本文以简单平面十字交叉口为例，将交叉口的物理拓扑及逻辑拓扑信息作为输入数据，在C#平台上利用ArcEngine二次开发组件和MicrosoftAccess关系数据库，实现交叉口几何拓扑的构建。其物理拓扑如图9所示，路段 $e _ { 1 } , e _ { 2 } , e _ { 3 } , e _ { 4 }$ 和交叉□ $\nu _ { \mathrm { { l } } }$ 相连接，逻辑拓扑按照 $e _ { 1 } , e _ { 3 }$ 路段上进口道为五车道（包括一条右转渠化道)，出口道为五车道， $e _ { 2 } , e _ { 4 }$ 路段上进口道为四车道，出口道为三车道的规则自动生成。各外部几何参数参考国家标准等规划设计规范进行设置，其中右转弯曲线的半径参照无非机动车道情况下路缘石的半径设置。构建的平面交叉口几何拓扑如图10所示。

![](images/6651a92b66262e735820226d7dca11bcacbea2157fecd0f5d780213d02f461e7.jpg)  
图9平面十字交叉口物理拓扑及逻辑拓扑

![](images/24906750c4030d80c2614a9edb780f1242f5bdf6b6c51a7b2a7883eadc00d49c.jpg)  
Fig.9Physical topology and logical topology of a plane intersection   
图10平面十字交叉口几何拓扑  
Fig.10 Geometric intersection of intersection

# 4 结束语

本文基于交叉口相关研究的需求，以物理拓扑和逻辑拓扑为基础，通过获取逻辑拓扑中有向路段、车道、纵向车道连接器、横向车道连接器的逻辑连通关系以及相关属性数据（车道宽度、长度等)，结合外部的几何参数包括右转弯曲线半径、人行横道宽度、展宽段长度、渐变段长度等，参考国家标准等规划设计规范，以物理基础拓扑为基准参照系，采用线性参考、线性偏移等技术实现交叉口几何拓扑的构建。实践证明，本文提出的三层模型及其建模方法，能够有效地支持计算机进行交叉口的自动建模。

但目前模型对道路的交通规则描述有限，且没有考虑气候条件、环境条件等交通对象，因此难以描述复杂条件下的交叉口情况，须在下一步的研究中进一步完善。同时交叉口建模应当与路段建模建立更加紧密地耦合，以实现精细化表达的路网数据模型。

# 参考文献：

[1]温慧敏，全宇翔，孙建平．大数据时代城市智能交通系统发展方向

[J．城市父通,20I/,I5(5): 20-25.(Wen Huimin,Quan Yuxiang,Sun Jianping.Developing trend of intelligent systems in the era of big data [J].Urban Transport of China,2017,15(5): 20-25.)   
[2]Sheffi Y.Urban transportation networks:equilibrium analysis with mathematical programming methods [M].[S.l.]:Prentice-Hall,1984.   
[3]Li Xiang，Lin Hui.A trajectory-oriented carriageway-based road network data model, part 1: Background [J]. Geo-spatial Information Science,2006,9(1):65-70.   
[4]Hijmans R J.Raster: Geographic data analysis and modeling [J].R Package,2016,12 (9):33-40.   
[5]Zhang T,Arrigoni S,Garozzo M,et al.Alane-level road network model with global continuity [J].Transportation Research Part C,2016,71: 32-50.   
[6]Zhu Qing,Li Yuan.Hierarchical lane-oriented 3D road-network model [J].International Journal of Geographical Information Science,2008, 22 (5): 479-505.   
[7]Huang Min,Rao Ming Lei,Li Min,et al.Lane-Based Road Network Model and its Application in Simulation Road Network Modeling [J]. Applied Mechanics&Materials,2013,253-255:1351-1355.   
[8] 安毅生，雷甜，袁绍欣,等．基于 TCPN 的交叉口信号控制模型与优 化[J].计算机应用研究，2016,33（1): $1 9 4 - 1 9 8 + 2 4 4$ (An Yisheng, Lei Tian，Yuan Shaoxin，et al.Traffic signal control model and optimization based on timed colored Petri nets [J].Application Research of Computers,2016,33 (1): 194-198+244.)   
[9] 赵靖，周溪召．基于车道控制的交叉口流向及信号组合优化模型 [J]．计算机应用研究，2016,33（11):3284-3288.(Zhao Jing，Zhou Xizhao.Lane based integrated model of movement prohibition and signal control for intersections [J]. Application Research of Computers, 2016,33 (11): 3284-3288.)   
[10] Ruan Xin,Zhou Junyong,Tu Huizhao,et al.An improved cellular automaton with axis information for microscopic traffic simulation [J]. Transportation Research Part C:Emerging Technologies,2017,78 (6): 63-77.   
[11]朱庆，李渊．道路网络模型研究综述[J].武汉大学学报:信息科学 版,2007,32(6): 471-476.(Zhu Qing,Li Yuan.Review of road network models [J]. Geomatics and Information Science of Wuhan University, 2007,32 (6): 471-476.)   
[12] WeiFulu,Guo Weiwei,Liu Xin,et al. Left-turning vehicle trajectory modeling and guide line seting at the intersection [J].Discrete Dynamics in Nature and Society,2014,2014 (11): 1-7.   
[13]杨晓光．城市道路交通设计指南[M].北京：人民交通出版社，2003. (Yang Xiaoguang. Manual of urban traffic design [M]. Beijing: China Communications Press,2003.）