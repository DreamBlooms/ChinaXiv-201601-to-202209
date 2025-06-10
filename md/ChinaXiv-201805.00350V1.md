# 面向移动终端的三维建筑物模型简化方法

王权，宋春花，牛保宁(太原理工大学 计算机科学与技术学院，太原 030024)

摘要：目前，针对单体建筑物的模型简化算法主要考虑单独简化墙面和屋顶房檐结构。但对于建筑物组，这些方法忽视邻接建筑物的特征，以及与周围特征间的相互连接关系。针对这些问题，利用屋顶结构特征，提出一种能自动生成保持建筑物组结构特征的模型简化方法。通过底面平面图的邻接关系将建筑物分割成不同的结构部分，通过判断屋顶特征，采用自顶向下的投影方法，重构建筑物模型，最后将各部分联合形成简化模型。实验表明，该简化方法在建筑物的顶层和墙面特征较好保留的基础上，能充分利用模型的拓扑结构，用较少的数据量描述模型，生成适合移动端应用需求的精度模型。

关键词：三维模型简化；建筑物模型重构；屋顶房檐结构；移动终端 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.08.0958

# 3D building model simplified method in mobile terminal

Wang Quan, Song Chunhua†, Niu Baoning (School ofComputer Science & Technology,Taiyuan Universityof Technology,Taiyuan O3o024,China)

Abstract:Atpresent,the simplified models forasinglebuildingconsistofsimple wallsandroofstructures.Forbuilding groups, thesemethodsignore thecharacteristicsofadjoiningbuildingsandtheinterconnectedrelationship withthesurounding features. Basedonthecharacteristicsof teroofstructures,this paper proposedamethodwhichcanautomaticallgenerate thestructural features ofthe building.It dividedthe building intodiferent structural partsbytheadjacencyof thebottomplan.Foreach structuralpartofthe partions,itreconstructedthebuilding modelbyusingatop-downprojection method thatdetermining the topstructuralfeatures.Finaly,itcombinedtheparts toformasimplifiedmodel.Theexperimentalresultsshowthattheethod canmake fulluseof thetopologyofbuildings and describe the modelwith the least amountofdatafor mobileapplications, while preserving the top and wall features of buildings.

Key Words: 3D simplify; reconstruction of building model; roof structures; mobile terminal

# 0 引言

随着空间信息技术和计算机图形图像技术水平的提高，三维建筑模型被广泛应用在各行各业中，如城市规划、个性化旅游、房地产管理、文物保护、导航等。真实感和高效性是衡量三维城市模型质量好坏的最重要的两个方面。现有三维建模与绘制技术能将现实生活中的场景逼真地呈现，但需要大量的计算资源，包括CPU、存储和网络带宽。对于移动终端，其特点是计算资源有限。精细的模型，包含较大的数据量，占据较大的存储空间；大量的计算快速消耗电池能量，导致续航时间短；大量的数据传输消耗网络流量，增加使用成本。这些因素严重地影响三维建筑模型在移动终端的实时交互式操作和应用。

当前，PC端能高效地展示精细三维建筑模型，但由于移动终端资源受限的原因，同程度的精细模型不能直接在移动端直接展示。三维建筑模型在移动设备上的应用通常采取以下三种措施：a）建筑物用低精度的几何描述；b）地标性建筑物采用高精度的几何描述,其余的建筑物用低精度的几何描述；c)在地图中，地标性建筑物用高精度的几何描述，并进行纹理贴图，其余的建筑物采用二维描述。当前研究主要聚焦在减少建筑物模型数据量和优化实时渲染上，以达到平衡模型精度和移动设备性能的目的。为此，对复杂三维建筑物构建不同的精度模型成为必然选择[I]。另外，针对单体建筑物模型的简化算法研究很多，但针对建筑物组模型的研究工作相对较少。现有的简化算法把研究重点主要集中在整体简化建筑物模型，屋顶、墙体和底面平面同时考虑，虽然能一定程度上减少冗余，但仍难以满足轻量化移动终端实时计算的要求。从移动端建模特点考虑，需要在现有的三维建筑物模型基础上，对模型进行再简化。

本文的宗旨是在保持模型认知的前提下，最大化地减少几何模型的复杂度，输出质量较高的简化模型，较好地适应应用需求。主要创新如下：研究聚焦在简化处理建筑物组模型，充分考虑邻近建筑物相互关系和作用效果，对建筑物组进行块拆分，对拆分单体利用顶部结构构建墙体，重构完整模型。利用顶部结构特征构建模型的方法，能较好地保持模型的几何特征和避免过于依赖模型拓扑结构特征。既简化模型处理过程又减少模型数据传输量，从而提高移动端建筑物组的建模效率。

# 1 相关工作

传统的二维地图中，利用一系列的二维地图综合中提出的聚合、典型化、位移以及夸张等算子[21，在放大和缩小变换的情况下，地图信息可以按照人们对客观世界的认知进行合理展示。三维建筑物综合是从二维综合扩展而来。Kada等人[3]认为，不同的应用需要不同细节层次的表达，其主要着眼点在于：通过删减次要信息，突出重要信息，提高数据的传输和可视化的效率；对于三维建筑物的综合，Biljecki等人[4认为，综合是生成一系列由粗到精的细节层次（levelofdetails，LoDs）三维模型的过程，在此过程中单体建筑物对象的几何与语义属性以及建筑物之间的关系都要被简化、聚合、典型化等。

为了充分地利用现有数字城市中三维建筑物模型数据，需要在保持模型外观特征的基础上减少冗余，生成多细节层次（levelofdetails，LoDs）模型，满足三维城市导航系统的可视化需求。CityGML是一种开放的用于三维模型数据交换和存储的格式，定义同种建筑物模型的不同层级表示（LoD0-LoD4)，以满足实际需求。图1为同一建筑物模型的不同LDs。其中LoD0表示的是二维平面图；LoD1表示的是用块体结构代替三维建筑模型，包含没有屋顶的建筑物；LoD2模型包含高度信息和屋顶结构特征；LoD3表示的建筑物在LoD2的基础上增加了更多特征信息，如窗户和门等细节特征；LoD4包含详细的建筑物信息，包括内部装饰和家具等，数据能够通过建筑信息模型（building information model,BIM）和雷达获取[5.6]。

![](images/a4e587d3c30fe7d61d08f2098ad06d72aed5c2610e369fd94d307c83e5c64cc1.jpg)  
图1同一建筑物模型的不同LoDs图

刘波等人[7提出一种构建建筑物单体几何模型的方法，用航拍图和地面拍摄的照片，分上、中、下三层构建单体建筑物的几何与纹理，生成模型库。这种方法适合构建样式比较固定的小区楼房建筑物模型库，然后重复调用模型。Baig等人[8采用边长度阈值大小约束平面图中边、曲线、角的数量，从LoD3建筑物模型中提取出LoD1模型，只适用于包含规则结构的平顶建筑物模型。Fan 等人[9提出一种从高精度模型中提取低精度模型的方法，该方法依次简化底面轮廓图和简化屋顶房檐结构，将底面边线和房檐结构连接，重构三维建筑模型。Mao等人[0提出基于最小生成树的动态典型化方法，以建筑物为中心，应用最小生成树进行聚类；然后根据子树的空间形态对建筑物分组；最后采用类似于线简化的方法对建筑组分组，进行三维典型化综合。以上方法都是基于预先规定的几何长度阈值对底面平面图进行简化处理，都没有考虑建筑物间的邻接关系，只适合处理单体。

对于建筑物组的综合，Glander[1提出基于单元块的聚类划分，对建筑物进行合并。EIlul等人[12]对三维场景中的建筑物设定几何长度阈值进行简化处理，后续的研究充分利用拓扑数据结构来最小化描述单个建筑物模型，以降低构建建筑物几何模型的数据量。以上方法能很大程度地减少数据量，使得性能得到提高，但通过底面平面图拉伸形成的建筑物模型是2.5维的块体建筑物，缺少顶层和墙面信息，缺乏真实感。Sun 等人[13]提出一种建筑物结构保留算法。该算法生成基于体素表达的模型，利用边界块的中心点对建筑物进行凸分解、简化凸块、合并所有凸块，从而重构简化模型。由于对结构复杂、细节特征丰富的建筑物进行分割时，难以得到理想的结构分割，不适用于处理多样式的建筑物。Li等人[14利用凹凸分析提取嵌入结构组成结构和相连结构，对建筑物进行拆分，制定相应的规则来简化对应结构部分。该简化算法能对模型进行简化和处理复杂的聚合模型，但该方法处理过程计算量大、耗时长，容易导致结果表面离散化失真。He等人[15提出基于高度拆分的简化方法，将建筑物组模型分为高度近似相同和高度不同两类，分别对模型组的底面平面图进行简化处理，但没有考虑对模型顶部的简化处理。

本文方法采用符合人类视觉感知的尺度空间理论，在简化处理过程中考虑对单个建筑物的感知和认知效果，同时兼顾邻近建筑物的影响和作用效果。简化模型过程中，无论是平顶还是斜顶建筑模型，都只通过作为全局特征的屋顶房檐结构进行构建，能有效地保持三维建筑物模型垂直棱角，底面平面图开放边界，屋顶等特征。

# 2 三维建筑物组模型简化算法设计

三维建筑物组模型简化算法设计分为三个阶段，即预处理阶段、建筑物拆分阶段、简化屋顶和重构建筑物组模型阶段。预处理阶段，对CityGML模型进行处理，提取模型的顶部结构和墙体结构的点坐标；建筑物组拆分阶段，通过底面平面图进行初拆分，未拆分部分按照高度和屋顶结构特征进行再拆分，直到不能拆分为止，将建筑物组拆分成结构良好的单体；简化屋顶和重构模型阶段，采用顶部结构简化算法，对拆分单体的屋顶平面进行简化，移除冗余特征。简化单体的屋顶后，对单体进行组合，具体步骤是将相邻平面合并，重构形成简化后的建筑物组模型。

通过实验发现，建筑物的轮廓特征对于识别建筑物具有很大的影响。考虑到实际可视化中受数据存储空间、传输速度、计算量的制约，可以将建筑物的外壳模型作为精细模型的替代，给用户近似的视觉印象[16]。例如当前移动版的高德地图，城市建筑物模型用块结构进行表示，能粗略地代替原始建筑模型，但难以很好地展示建筑物特征。本文提出一种简化后顶部结构的模型，具有更好的视觉感、沉浸感。为满足移动端可视化要求模型精简、场景渲染量小的特点，通过保留建筑物顶部房檐特征进行自顶向下建模，生成包含顶部特征的块体结构。其具体流程如图2所示。

![](images/6ca63af8b95672bac09cc3543af810f448783c53f033c709aa5efc032f13e22a.jpg)  
图2建筑物模型简化方法流程

无论是平顶建筑物还是斜顶建筑物，都能通过建筑物的顶部几何特征构建出建筑物的墙体，从而重构形成简化后的低层级（LoD2或LoD3）的建筑物模型。场景中的建筑物组中，相邻的建筑物可以相连或者分离，所以对建筑物的简化分为单体建筑物简化和相连建筑物简化。若为单体建筑物简化，通过区分建筑物顶部特征，判断平顶还是斜顶，分别按程序进行建模；若为相邻组合建筑物，则首先对建筑物按照底面平面图的邻接关系和高度特征进行结构划分，然后按照单体建筑物简化过程进行建模。

# 2.1CityGML模型预处理

CityGML使用BRep来表示城市模型的几何对象[17]，每个建筑物用多个平面作为边界来表示3D形状。CityGML建模的建筑物模型就是一组包含相应语义信息的平面组合。由于CityGML定义了对同一物体的多层次细节描述，并且保持几何和语义的描述一致性，可以利用这一特性进行不同层级建筑物模型间的转换处理。解析和处理CityGML模型是模型间转换过程必须考虑的。CityGML4j 是解析转换CityGML 格式的开源库，借鉴Deng 等人[18]的从上到下方法，对输入的三维城市模型，解析程序定位所有的建筑物，同时通过CityGML4j中相关方法将建筑物组成部分，如房顶结构、墙结构、空缺部分等分别提取出来，为后续工作做准备。

# 2.2建筑物组模型拆分方法

通过判定确定建筑物的复杂程度后，将复杂建筑物划分成规则的不同子建筑物部分。划分后的单体包含几何信息，这样便于提取建筑物顶部结构、简化概括和最后的地面投影操作。

在GIS（地理信息系统）的2D和3D空间中，物体通常使用外围边界线表示实体。它是由一系列的基础几何基元表示，几何基元包括点、线、面。其中二维欧氏空间中的点是用一个二元组（x,y）表示,而三维欧氏空间中的点是用三元组（x,y,z）表示，在欧氏空间中它们相同的是点构成线，线构成面，不同点在于面是否能构成三维几何实体。拆分过程中，由于建筑物组包含丰富结构特征，不能单一地采取比较高度进行划分，还需要考虑建筑物的顶部特征。为了更好地划分，提出利用底面平面图和建筑物的顶部特征共同判断邻接关系进行建筑物拆分的方法，这样可以精确拆分，避免错误发生。具体拆分过程如算法1所示。

# 2.2.1建筑物的连通性

建筑物模型拆分中确定建筑物邻接关系分为两步，第一步判断确定平面图连通性，第二步通过高度和顶部结构确定立体图的连通性。确定建筑物组邻接关系后进行拆分。

a)确定平面图连通性。若基元p1是另一个基元p2的一部分，说明p1依附于p2。若p1和p2共享低维的基元，则两个基元是邻接关系。如果共享的基元仅包含一个点，说明两个基元是弱连接关系；如果至少包含一条线段，说明两个基元是强连接关系。若为弱连接，则在立体图中共线；若为强连接，则在立体图中共面。弱连接部分在拆分中直接进行拆分，强连接部分需要借助高度和顶部特征再重新判断。

b)确定立体图连通性。在平面图基础上，建筑物组存在高度不同，则将其拆分成最高建筑物单元和相邻的子部分，对子部分进行同样的循环操作，直到不能再拆分为止。执行过程中，对高度设定一个阈值，当相对高度差大于阈值时才进行拆分，这样可以避免拆分过于精细。对于小于阈值的建筑物单元，确定建筑物顶部特征，相同顶部采取合并的原则，将建筑物合并成一个整体，否则继续拆分。合并后的新单体的高度由原单体的高度和平面面积共同决定，其中height $\left( b _ { i } \right)$ 是单体 $b _ { i }$ 的高度，$a r e a \left( b _ { i } \right)$ 是单体 $b _ { i }$ 的面积。依据组成新单体的每一个单体 $b _ { i }$ ，计算平均高度 $\overline { { h } }$ ：

$$
\overset { - } { h } = \frac { \sum _ { i = 1 } ^ { n } h e i g h t \bigl ( b _ { i } \bigr ) * a r e a ( b _ { i } ) } { \sum _ { i = 1 } ^ { n } a r e a ( b _ { i } ) }
$$

图3分别是相邻的三个建筑物组成的底面平面图、立体图的相互关系展示。

![](images/b100eb703a17bf48121c69aeba53983644444c21b6ec292a4397bd3513aefab9.jpg)  
图3平顶建筑物的平面图和边界表示图

# 2.2.2区分平顶和斜顶屋顶特征

确定建筑物屋顶特征：目前城市中大部分基础建筑物按照屋顶特征划分，分为平顶类型的块体建筑物、人字形屋顶建筑物和双面人字形屋顶建筑物三类。判断屋顶类型主要差别就在于形成屋顶的面是否存在倾斜，不存在倾斜就是平顶建筑。根据实际经验，将顶面倾斜角度在阈值 $0 ^ { \circ }$ ${ \sim } 9 0 ^ { \circ }$ 的建筑物判定为斜顶建筑物。

倾斜角度可以通过数学方法进行求解，假设平面 $F _ { i }$ 为：$A _ { i } x + B _ { i } y + C _ { i } z + D _ { i } = 0$ ， $F _ { i }$ 表示建筑物其中的第 $i$ 个平面； $D _ { i }$ 表示平面距离原点坐标系的最短距离； $\left[ A _ { i } , B _ { i } , C _ { i } \right]$ 表示平面 $F _ { i }$ 的法向量，则求平面 $F _ { i }$ 与 $F _ { j }$ 间的夹角公式如（2）所示。

$$
\theta _ { i j } = a r \cos \left( \frac { A _ { i } A _ { j } + B _ { i } B _ { j } + C _ { i } C _ { j } } { \sqrt { A _ { i } ^ { 2 } + B _ { i } ^ { 2 } + C _ { i } ^ { 2 } } \sqrt { A _ { j } ^ { 2 } + B _ { j } ^ { 2 } + C _ { j } ^ { 2 } } } \right)
$$

# 算法1建筑物组拆分算法

输入：建筑物组中所有二维平面图的点集合（PSet）和线集合（ESet)，二维平面图(footprint)集合 $\mathsf { D } _ { \mathsf { c } }$ （2

输出：三维建筑物组块划分集合(PartSet)。   
$\textcircled{1}$ procedure Segmentation(B-rep)   
$\textcircled{2}$ Partset=[]/\*存储结果集\*/   
$\textcircled{3}$ for all e in ESet   
$\textcircled{4}$ for all footprint in D do   
$\textcircled{5}$ if only one footprint contains the e   
$/ { * }$ 仅一个平面图含边 $\boldsymbol { \mathsf { e } } ^ { * }$ /   
$\textcircled{6}$ insert(PartSet)/\*插入结果集中\*/   
$\textcircled{7}$ else if (isSameheight(D)&&   
isSimilarbuildings(D))   
/\*包含边e的平面图对应的单体等   
高且顶部特征相似\*/   
$\textcircled{8}$ new_footprint $\mathbf { \sigma } = \mathbf { \sigma }$ [footprint1,   
Footprint2]   
/\*将满足条件的平面图合并\*/   
$\textcircled{9}$ else Respectively inserted into the PartSet /\*分别插入PartSet\*/   
$\textcircled{10}$ return PartSet   
$\textcircled{1}$ end procedure

# 2.3简化屋顶和重构简化后的建筑物组

屋顶结构通常是由不同法向量和倾斜角度的平面组成，形成符合人类视觉美观的造型，这种造型特点呈现在三维空间中具有立体效果。虽然二维空间的简化相对三维空间中的简化相对容易得多，但由于三维空间中的平面投影到二维空间中会产生扭曲，如边长度和角度改变、相邻多边形平面存在夹角投影到二维空间、会导致相对角度缺失、简化后的平面还原存在难度等，考虑简化屋顶结构在三维空间进行。根据Fan等人[9]提出的简化方法，通过在三维空间中移除不重要的曲线、角、边，消除冗余特征，达到简化的目的。图4是建筑物屋顶结构简化

前后对比。

简化顶部结构算法包括以下几步：

a)消除不重要的结构部分，如烟肉、采光窗等；

b)根据平面分组分别简化屋顶多边形；

c)将简化后相邻平面（共面平面和准共面）合并。

![](images/38d38e085900cacd774ca6c25eb4bb7cc506d1fe62266068364a45161136893d.jpg)  
图4建筑物顶部多边形简化合并示意图

简化屋顶结构操作后，通过屋顶边缘拐点向下投影形成墙面，达到重构建筑物的目的。简化和重构过程通过算法2实现。墙面可以看成是一个有若干个顶点的多边形，通过将屋顶边缘拐点向地面投影，与地面相交，重构形成一个屋顶和墙面没有间隙的完整建筑物单体，最后通过联合操作合并这些单体成为组合体。具体操作是通过移除单体间的共面和合并保留的面，形成一个与原始建筑物模型近似的满足拓扑结构的建筑物实体模型。

# 算法2建筑物简化重构算法

输入：建筑物组划分的块结构集合PartSet。输出：简化后的建筑物组合模型。  
$\textcircled{1}$ procedure Reconstruction(PartSet)$\textcircled{2}$ results=[ ]  
$\textcircled{3}$ parts=PartSet  
$/ { ^ * }$ 从划分块集合中赋初值\*/  
$\textcircled{4}$ while notEmpty(parts）do  
$\textcircled{5}$ （204号 ${ \mathsf p } =$ delete(parts)  
/\*从parts 集中选取块\*/  
$\textcircled{6}$ parts_roof $\dot { \mathbf { \eta } } = \dot { \mathbf { \eta } }$ selectTop(p,PartSet)$/ { ^ * }$ 从p中选取顶部结构\*/  
$\textcircled{7}$ parts=generateProto(parts_roof)/\*通过顶部结构生成单体\*/  
$\textcircled{8}$ insert(results,parts)  
$\textcircled{9}$ return results  
$\textcircled{10}$ end procedure

# 3 实验设计、结果及分析

本文算法通过 MATLAB 编程实现，实验平台为 Intel(R)Core(TM) i5-4670 CPU $\ @ 3 . 4 ~ \mathrm { G H z }$ 处理器，4GB 内存，1TB硬盘，Windows7操作系统的计算机，部分实验数据可从CityGML官网获取。

# 3.1简化实验设计

简化处理过程如图5所示。其主要分为数据预处理、模型简化和重构、数据转换成CityGML三个模块。数据预处理模块，由于原始的CityGML 建筑物数据模型不能直接被 Matlab 加载处理，仅建筑物的外壳顶点被提取用来后续的处理。首先从CityGML数据集中提取建筑物外壳部分的顶点集，分为两个组：屋顶结构部分和墙结构部分。简化和重构模块中，通过平面图的邻接关系判断建筑物邻接关系，对建筑物模型进行拆分和将拆分后的顶部结构分别进行简化，最后重构形成简化后的建筑物组。数据转换模块，将简化后的模型转换成便于在LandXplorerCityGMLViewer2009可读的CityGML格式。

![](images/e387e0a31a3a7611c7517918fc438525aa6f4ace9126d47e411a21075b06f949.jpg)  
图5三维建筑物模型数据解析和处理主要模块

# 3.2不同顶部建筑物模型简化实验结果

简化建筑物的运行时间和数据压缩量由建筑物几何结构的复杂程度决定。为了验证算法的有效性，使用平顶、单斜顶、组斜顶、混合型建筑物模型进行验证。另外，将本文算法与三种经典算法进行对比实验。

方案1为组合平顶建筑物，由两个高度不同的平顶建筑物组合而成，初始时底面平面图和包含局部细节特征的顶部结构图的边缘轮廓相同。图6是简化建筑物处理过程。将小于阈值长度的屋顶结构边移除，同时移除屋顶面上小于阈值的结构部分。对比简化前后，保留部分的屋顶平面图与原始的屋顶平面图轮廓非常相似，采用从顶向下投影生成的模型与原始模型近似相同。

![](images/e54f1c6927e40e467a2f09eecc91faf522098606c72afc3db5d81b46ee0c4643.jpg)  
图6简化平顶建筑物组图

建筑物模型包含屋顶结构特征时，简化过程需要考虑屋顶结构特征。方案2将建筑物模型分为单斜顶建筑物和组合斜顶建筑物.图7为斜顶单斜顶建筑物模型。简化过程不需要进行拆分,直接采用斜顶建筑物模型简化方法进行处理，生成简化模型。

对于组合斜顶建筑物模型，图8中建筑物模型屋顶结构部分由不同的斜顶组合形成。简化过程需要考虑是否拆分。由于组合模型顶部结构特征为斜顶且高度近似相同，不进行拆分，将其组合进行简化处理。采用斜顶建筑物模型简化算法先简化后投影操作，生成简化后的组合斜顶建筑物模型。

![](images/2d1a4a75f52e7d8b6c41b19abb03ec8fa6c45d19e0eda712dfdb1de9df8fdf5e.jpg)  
图7简化单斜顶建筑物图

![](images/a57b6efcc20977d4c6f516fe9bc146fb42d1c3fe8a7abb16da97cef85e67c981.jpg)  
图8简化组合斜顶建筑物图

方案3为混合建筑物组模型，同时包含斜顶和平顶，且建筑物高度不同。简化过程需要先综合考虑高度和屋顶类型，确定如何拆分，再依据单体简化，最后将简化单体合并。这样可以避免提取顶部结构不规则，导致简化过程复杂。简化过程严格按照本文提出的算法进行处理，具体的简化过程如图9所示。

![](images/d94e208424a71849f989e29aa5d43889992e7948d54c425b0a747fb7f0bd5ead.jpg)  
图9简化平顶斜顶组合建筑物图

刘波等人[7的建筑物模型分层简化法，综合考虑将建筑物模型分成上中下三层，分别进行简化处理，适合简化处理城市中的小区建筑物模型。上层顶部结构特征不进行简化处理；中间层由于结构相似性，通过建立单层模型，重复叠加单层模型构建中间层；底层包含更多的细节特征，单独进行简化处理。图10是采用刘波简化法生成的建筑物模型图。

![](images/a3d19cd5014b597456c644ad8953126d03e2db061763bf031284cfc15d1f9c55.jpg)  
图10采用刘波简化法生成的建筑物图

Fan 等人[9提出的三维建筑物简化方法，整个过程分为简化墙面部分、概括简化屋顶房檐结构、重构建筑物模型三步。简化墙面过程，通过将墙体投影到地面形成二维平面图，移除边、角冗余，形成简化后的平面图；简化屋顶结构过程，采用相似的策略，按多边形平面进行概括简化；重构建筑物模型过程，通过交叉点和屋顶多边形平面的拓扑关系计算出交叉线，移除墙体和屋顶空隙，从而形成一个简化后的三维建筑物模型。图11是采用Fan简化法生成的建筑物模型图。

![](images/626b20122edca3616629269198f2588c0b5b3532c9306fe90a717a83da0c3db0.jpg)  
图11采用Fan 简化法生成的建筑物图

Ellul等人[2]提出的三维建筑物简化法，主要采用二维地图中综合概括方法对底面平面图进行简化处理。通过对建筑物底面平面图进行几何长度阈值判断，移除冗余的边线，形成简化二维平面图，再将二维平面拉伸形成只包含平顶结构特征的三维立体建筑物模型。图12是采用EIlu1简化法生成的建筑物模型图。

![](images/ee0a8ef63f8a2f82b36416c59b737574dfca98633db607b2995f4a9a3b45959b.jpg)  
图12采用Ellul简化法生成的建筑物图

# 3.3 实验结果分析

对比上述实验结果表明，上述简化算法都能在一定程度上简化三维建筑物模型。当处理平顶建筑物模型时，四种方法生成的模型基本相同；当处理斜顶，组合斜顶型和混合型建筑物模型时，生成简化模型的差别主要在顶部结构特征，整体效果近似。对比四种简化算法，Fan 简化法需要考虑简化底面平面图和处理底面平面图与顶层结构相交情况，本文方法不需要考虑这些方面，使得简化运行时间减少，效率较高。EIlul简化法生成的模型虽然数据压缩量量最大，但模型缺乏顶部特征，会造成细节过分缺失。刘波的分层简化法由于没有进行顶部特征简化，会使得顶部细节特征过于冗余。另外，本文提出的建筑物组简化算法，可以通过块划分得到语义和几何意义上良好的建筑物单体，便于提取底面投影部分和简化概括操作，生成精简的建筑物组模型。无论是单体模型还是组合模型，采用本文算法都能生成适合移动端加载渲染的精简建筑物模型。

表1原始模型和简化模型数据量对比  

<html><body><table><tr><td rowspan="2">屋顶类型</td><td colspan="2">顶点</td></tr><tr><td>原始 压缩</td><td>刘波简化法 Fan 简化法 Ellul简化法 本文简化法</td></tr><tr><td>平顶</td><td>简化 46</td><td>压缩 简化 压缩 简化 压缩 简化</td></tr><tr><td></td><td>46 18</td><td>0% 24 26.1% 24 26.1% 24 26.1%</td></tr><tr><td>单斜顶</td><td>18</td><td>0% 10 44.4% 8 55.6% 10 44.4%</td></tr><tr><td>组斜顶</td><td>44 36 43</td><td>18.2% 26 40.9% 12 72.7% 17 61.2% 25.6%</td></tr><tr><td>混合顶 43</td><td>0% 36 16.3% 28 34.9% 32</td></tr></table></body></html>

表1通过比较上述三个方案简化前后的顶点数，判断数据量变化。在三维建筑物模型中，复杂顶部结构和墙体细节特征占数据量的很大部分，简化过程主要是处理这部分数据。因此，简化处理过程中模型的精细程度不同，压缩量也不同。对于简单的平顶和斜顶建筑物模型，由于底面平面图和顶部结构面图轮廓近似相同，四种方法形成的模型基本相同，所以数据压缩量相同。对于斜顶建筑物模型和混合建筑物模型，四种算法简化生成模型程度不同。

不同建筑物模型简化顶点数对比如13所示，不同建筑物模型简化压缩量对比如图14所示。分析图13和14不同实验方案简化结果，刘波简化法生成的模型简化程度最低，能较完整地保留原始模型的特征，数据压缩量最低为 $0 \%$ ，最高为$1 8 . 2 \%$ ，不能达到移动端所需模型的精度要求。对比其他三种算法，EIlul简化法生成模型的数据压缩量高，但这是以牺牲视觉效果为代价。简化模型缺失顶部结构特征，易导致模型不能清晰辨识。在保持模型轮廓特征情况下，Fan简化法有很好的效果，在一定程度上可以对模型简化。与Fan简化法相比，本文简化法压缩量较高，最低压缩量为 $2 5 . 6 \%$ ；相比Fan方法提高了 $9 . 3 \%$ ，最高压缩量为 $6 1 . 2 \%$ ；相比Fan 方法提高了 $20 . 3 \%$ 能更好地满足应用需求用最少的数据量描述整个建筑物模型。产生这一结果的原因是：a)将复杂建筑物组模型拆分成简单单体模型，便于简化处理；b)通过屋顶结构从顶向下投影产生房

体，简化模型整体结构。

![](images/22a3b5a08b6fef420e365b773b555573a83cd8848099bc8598d03b8d7c28be29.jpg)  
图13不同建筑物模型简化顶点数对比

![](images/a20c89ba606ba887ff19fa2cd521c5264b77558250a26773fb710d6f7c5b915f.jpg)  
图14不同建筑物模型简化压缩量对比

通过实验验证，本文方法能有效地简化包含平顶或者斜顶的单体或建筑物组模型，有效地减少数据量。在不影响视觉效果的情况下，与其他的简化方法相比，本文提出的方法数据压缩效果更好。综合考虑，本文的简化方法能大幅度提高简化的鲁棒性，降低对模型拓扑关系的约束，较好地输出高质量的简化模型。

通过各种典型外观的三维建筑模型进行简化实验，结果表明在保留基本形状情况下，对屋顶结构进行一定程度的简化，重构建筑物模型，能生成与原始模型匹配的模型。通过形状相似性测量方法进行简化质量评估发现，在保持相同顶点数的情况下，本文方法生成的模型具有更高的相似性，简化模型可以较容易地与原始模型进行匹配，适合移动端模型需求。另外，数据传输阶段，只需要从服务器端传输模型顶部结构的顶点坐标给客户端，这样可以减少数据的传输量，减少传输负载。

# 4 结束语

本文提出一种主要针对三维建筑物组的简化算法，旨在高效、快速地从高精度的模型中提取出低精度的建筑物模型，从而用建筑物的外壳模型代替原始模型。前人所采用方法思想是将底面结构和屋顶结构分开单独进行简化，最后综合考虑组合，过程繁琐且耗时，并且只能处理单体建筑物。本文提出的方法充分考虑人们对建筑物的特征感知和认知，同时兼顾邻近建筑物之间的相互关联，提出先拆分，后根据屋顶结构特征分别进行简化。该方法能大幅度提高简化的效率，降低对模型拓扑关系的约束要求。

该方法依然具有局限性，只是单纯针对三维建筑物几何模型，且不能有效地处理包含特殊结构的复杂建筑物模型，如古塔、古门楼等古建筑模型和包含其他类型顶部结构的建筑模型。后续研究将考虑简化此类建筑物模型和利用纹理再现技术来增加三维场景的真实感，使得三维城市构建过程高效性和真实感并存。

# 参考文献：

[1] 刘磊．基于简化的三维城市模型综合算法研究[D]．南京：南京大学, 2015.   
[2]赵君峤．复杂三维建筑物模型的多细节层次自动简化方法[J].测绘学 报,2013,42 (1): 156-156.   
[3]Kada M, Wichmann A,Filippovska Y,et al. Animation strategies forsmooth transformations between discrete lods of 3d building models[J]. International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences,2016,41 (B2): 413-420.   
[4]BiljeckiF,Ledoux H, StoterJ,et al.Formalisation of the level of detail in 3D city modelling [J]. Computers Environment & Urban Systems,2014,48 (16): 1-15.   
[5]朱亮，邓非．基于语义映射的BIM与3DGIS 集成方法研究[J].测绘 地理信息,2016,41(3):16-19.   
[6]Cheng JCP, Deng Y,Anumba C.Mapping BIM schema and 3D GIS schema semi-automatically utilizing linguistic and text mining techniques [J]. Electronic Journal of Information Technology in Construction,2015,20: 193-212.   
[7] 刘波，王章野，王丽英，等．大规模城市场景的高效建模及其实时绘制 [J].计算机辅助设计与图形学学报,2008,20(9):1153-1162.   
[8]Baig S U,Rahman AA.A three-step strategy for generalization of 3D building models based on CityGML specifications [J]. GeoJournal,2013,78 (6): 1013-1020.   
[9]Fan Hongchao,Meng L Q.A three-step approach of simplifying 3D buildings modeled by CityGML[J]. International Journal of Geographical Information Science,2012,26(6): 1091-1107.   
[10] Mao Bo,Harrie L，Ban Yifang.Detection and typification of linear structures for dynamic visualization of 3D city models [J]. Computers Environment & Urban Systems,2012,36 (3): 233-244.   
[11] Glander T. Multi-scale representations of virtual 3D city models [D]. Potsdam: Universitat Potsdam,2013.   
[12] Ellul C,Joubran JA. Investigating approaches to improving rendering performance of 3D city models on mobile devices [J].Geo-spatial Information Science,2014,17 (2): 73-84.   
[13] Sun Xuan, Yang Bisheng,Li Qingquan,et al. Linear geometric coding of complicated 3D building models [J]. Geomatics & Information Science f Wuhan University,2013,38(2): 225-229.   
[14]Li Qingquan,Sun Xuan，Yang Bisheng，et al.Geometric structure simplification of 3D building models [J]. Isprs Journal of Photogrammetry & Remote Sensing,2013,84(10): 100-113.   
[15]He Shuang,Moreau G,Martin JY.Footprint-based 3D generalization of building groups for virtual city visualization [C]// Proc of the 4th International Conference on Advanced Geographic Information Systems, Applications,and Services.Valencia:GEOProcessing,2012:177-182.   
[16] Fan Hongchao,Mao Bo,Shen Jie,et al. Shell model representation as a substitute of LoD3 for 3D modeling in CityGML [J].Geo-spatial Information Science,2011,14(2): 79-84.   
[17] Groger G,PlimerL.CityGML: interoperable semantic 3D city models[J]. Isprs Journal of Photogrammetry & Remote Sensing,2012,71:12-33.   
[18] Deng Yichuan,Cheng JCP,Anumba C.Mapping between BIM and 3D GIS in different levels of detail using schema mediation and instance comparison [J].Automation in Construction,2016,67: 1-21.   
[19]Xu Yongyang，Xie Zhong，Chen Zhanglong，et al.Shape similarity measurement model for holed polygons based on position graphs and Fourier descriptors [J]. International Journal of Geographical Information Science,2017,31(2):253-279.