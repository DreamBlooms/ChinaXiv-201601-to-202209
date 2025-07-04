# 针灸铜人三维可视化研究与应用

张文元，李晓旭，谈国新，孙传明(华中师范大学 国家文化产业研究中心，武汉 430079)

摘要：针灸铜人是中国古代医学珍贵的艺术品，具有重要的文化和艺术价值。针对针灸铜人这类文化遗产数字化保护手段单一、体验性差和传播力不强等问题，提出了一种综合利用三维激光扫描、三维可视化和虚拟现实等技术的数字化方法。以湖北省博物馆珍藏的腧穴针灸铜人为对象，首先采用三维激光扫描技术进行数据采集和三维建模；其次，使用 XML 语言对其承载的传统中医知识进行存储与表达；重点利用基于改进的二次误差度量和递进网格算法实现铜人多分辨率简化模型的自动生成；最后，利用Unity 引擎开发了一套针灸铜人虚拟交互展示系统，实现了穴位、经络和常见疾病等传统中医知识在三维场景下的快速可视化与交互查询，为历史文物与非物质文化遗产的数字化保护与传播提供了借鉴。

关键词：针灸铜人；文化遗产；三维可视化；模型简化；虚拟现实 中图分类号：TP391.41 doi: 10.3969/j.issn.1001-3695.2018.04.0274

# Research and application of 3D visualization for bronze acupuncture figure

Zhang Wenyuan,Li Xiaoxu, Tan Guoxin, Sun Chuanming (National Research Centerof Cultural Industries,Central China Normal University,Wuhan 43oo79,China)

Abstract:Bronzeacupuncture figure isa precious art in ancient Chinese medicine,which has importantcultural andartistic value.However,thetraditional protectionof thiskindofcultural heritagefocusesontext,pictures,andvideo,leadingtopoor user experience and dissmination.This paper proposed anew approach ofdigitalization by using threedimensional (D)laser scaning,3Dvisualizationand virtualreality.Taking the bronzeacupuncture figurewithacupointscolectedby Hubei Provincial Museum as an example,3D laser scanning technology was firstly applied to capture 3D point cloud dataof it. Secondly，knowledge models of traditional Chinese medicine were represented and stored through eXtensible Markup Language (XML).Thirdly,a mesh simplification algorithm based on modified quadric eror metric and progresive mesh construction was proposed toautomaticallygenerate multiresolution 3D models.Finaly,a Unity engine based virtual and interactive system forbronze acupuncture figure was developed,andit providedthe 3D visualizationand interactivequeryof acupoints,meridiansandcommon diseases.Theproposedmethod isable to provide areference solution forthe digital protection and dissemination of historical relics and intangible cultural heritage.

Key Words: bronze acupuncture figure; cultural heritage; 3D visualization; mesh simplification; virtual reality

# 0 引言

中华民族积淀了丰富多彩且文化底蕴深厚的文化遗产资源，“针灸铜人”就是其中一例。针灸铜人是中国古代医学家发明的一种用青铜浇铸而成的人体经络腧穴模型，始于北宋天圣年间，明清时期也有少量制作。当前流传下来的明清及以前的针灸铜人数量极少，而且大多都被收藏在博物馆，被公众了解甚少。作为中国传统医学史上的稀世奇珍，针灸铜人具有较高的历史、文化和艺术价值[1。2017年1月18日，习近平主席在瑞士日内瓦向世界卫生组织(WHO)赠送中国针灸铜人雕塑，就彰显了其重要地位和医学价值。

针灸教学目前比较常用的雕版印刷的二维平面图，二维图纸难以准确地反映人体复杂的经络和腧穴。针灸铜人是一种直观有效的针灸教学工具，如果能将收藏在博物馆里面的针灸铜人利用三维可视化技术和新媒体展示给大众，不仅有利于促进中医传统文化的广泛传播，而且也是对文化遗产的一种有效保护与传承。

近年来，计算机、地理信息系统、三维可视化和虚拟现实等技术在文化遗产数字化保护与传播方面应用越来越广泛[2.3]。例如，李德仁院士介绍了虚拟现实技术在香港志莲净苑和敦煌莫高窟等文化遗产数字化保护中的应用[4]。宗立成等人采用三维激光扫描技术研究了文物的三维重建和虚拟展示方法[5]。孔黎明等人认为增强现实技术(augmentedreality，AR)在革新文化遗产展示手段方面大有可为，并列举了AR技术在建筑遗址、壁画、历史街区、博物馆文化展示等多方面的应用案例[。黄永林等人提出数字化采集与存储、数字化复原和再现、数字化展示与传播、虚拟现实等技术在我国非物质文化遗产保护与传承方面能发挥重要作用[7]。

尽管国内外有关文化遗产数字化与可视化的研究与应用非常多，但大多是针对古建筑、历史遗迹等物质文化遗产，针对针灸铜人及传统中医知识这类特殊遗产的三维可视化研究和应用较少[8]。本文以馆藏针灸铜人为例，利用三维可视化和虚拟现实等技术研究针灸铜人及其所承载的传统中医知识虚拟展示方法，为文化遗产数字化保护和传播提供新途径。

# 1针灸铜人三维模型构建方法

本文以湖北省博物馆珍藏的腧穴针灸铜人为对象，该铜人造像为明代风格，全身共有659个腧穴，单侧355个腧穴，标注了354个穴位名称。馆藏针灸铜人将人体经脉和穴位等信息直观形象地展现出来，是研究和传播传统中医知识的一种重要工具。为了实现中医针灸知识的三维虚拟交互展示，创建精准的铜人三维模型和中医知识表达模型是基础。

# 1.1针灸铜人三维建模

三维激光扫描技术可快速获取目标物高密度的三维点云数据，具有非接触、扫描速度快、精度高等特点，在文物保护领域应用广泛[9.10]。本研究采用手持式三维激光扫描仪对湖北省博物馆所藏的腧穴针灸铜人（图1（a)）进行非接触式扫描，获取针灸铜人表面高密度的三维点云数据。在扫描时尽量保证模型各部位的光线均匀，并对表面复杂区域进行多次扫描。扫描完成后，对获得的点云数据用专业软件进行配准和去噪等处理，处理完成后保存为WavefrontOBJ（\*.obj）这种通用3D模型文件格式，方便导入其他三维建模软件进行精细建模，如图1(b)所示。

![](images/75b2bed6c0bee1781ed73a4620c50d3c826a8f887220388bbd7ebda319fafdd3.jpg)  
图1针灸铜人三维模型

针灸铜人模型表面有着较为复杂的经络和穴位信息，为此，利用高清相机对针灸铜人实物从不同角度拍照，获得其表面高质量图片。然后将这些照片导入Photoshop 软件进行裁剪拉伸等操作，形成铜人模型的纹理材质文件。在此基础上，将上一步处理得到的针灸铜人几何模型导入Autodesk3dsMax三维建模软件中进行较为精细的纹理贴图处理。贴图完成后，在Autodesk3dsMax中使用RenderTo Textures工具对模型进行烘焙处理，将光照和阴影等使用贴图方式预先贴附到模型上，从而减少后期三维模型可视化时光照和阴影的实时计算，提高渲染效率，最终结果如图1(c)所示。

# 1.2中医知识表达模型设计

湖北省博物馆珍藏的针灸铜人是传统中医知识教学的一种载体，为了实现传统中医知识的可视化传播，本文采用知识本体(ontology)[方法来构建中医知识表达模型，并将知识表达模型与针灸铜人三维模型通过空间位置建立关联，便于后续虚拟交互应用的实现。

为了实现知识之间关系的表达，以及知识模型与三维模型的映射，本文选取自由度较高的原生XML语言进行中医知识的组织与表达。中医针灸知识主要涉及穴位、经络和疾病三种基本术语，它们之间的关系如图2所示。穴位是基础和核心，与经络和疾病相互关联。经络与穴位之间是一对多关系，而疾病与穴位则是多对多关系。

![](images/cb117ed5689c799a6fd5d071a24e6c8b4c93704c5100f452b7c6bddc55912aab.jpg)  
图2疾病、学位、经络E-R图

接下来根据中医领域知识的特点确定各类实体的固有属性。以穴位为例，主要包含编码、名称、功能和所在位置等属性，如表1所示。

表1穴位属性信息  

<html><body><table><tr><td>属性</td><td>描述</td></tr><tr><td>id</td><td>穴位ID</td></tr><tr><td>name</td><td>穴位名称</td></tr><tr><td>function</td><td>穴位主治疾病</td></tr><tr><td>location</td><td>穴位所在位置</td></tr></table></body></html>

属性确定后，采用XML语言对穴位知识按如下方式进行结构化描述：

<?xml version $= " 1 . 0 "$ encoding $\ c =$ "utf-8"standalone $\ c =$ "yes"?>

<Acupoints>

<Acupoint id="A3"name $\mathbf { \Phi } = \mathbf { \Phi } ^ { \prime }$ 天府"function="气喘，鼻，上臂内侧痛。"location $\ c =$ "位于人体臂内侧面，肱二头肌桡侧缘，腋前纹头下3寸处。 $" / >$

# </Acupoints>

对于疾病知识的表达，除了考虑疾病知识本身的特点以及疾病与穴位的关联关系之外，还要考虑到可视化时针灸铜人三维模型的姿态信息，便于三维交互场景的快速定位。因此，疾病本体的属性定义如表2所示。

表2疾病属性信息  

<html><body><table><tr><td>属性</td><td>描述</td></tr><tr><td>id</td><td>疾病 ID</td></tr><tr><td>name</td><td>用于标识疾病的名称</td></tr><tr><td>modelRotation</td><td>用于存储旋转信息</td></tr><tr><td>modelScale</td><td>用于存储缩放信息</td></tr><tr><td>modelPosition</td><td>用于存储位置信息</td></tr><tr><td>mainAcupoints</td><td>包含穴位的文字描述</td></tr><tr><td>AssociatedAcupoint</td><td>关联穴位ID 列表</td></tr></table></body></html>

疾病本体模型设计如下：

<?xml version $\iota = " 1 . 0 "$ encoding $\mathbf { \Psi } =$ "UTF-8"standalone $\ L =$ "yes"?>

<Diseases>

<Diseaseid="ZQGY" name="支 气 管 炎”modelRotation $\ " 0 , 0 , 0 \ "$ modelScale="2" modelPosition $\ v { x } = \ v {" }$ -1.51,0.02,0"mainAcupoints="大椎、肺 俞、膻中、天突">

<AssociatedAcupointid="M14"/> <AssociatedAcupoint id="G13"/> </Disease>

</Diseases>

其中，AssociatedAcupoint子节点建立了疾病与穴位之间一对多的关联关系。

经络的本体设计与疾病类似，也是通过AssociatedAcupoint子节点建立经络与相应穴位的关联。以手太阴肺经为例，其知识模型设计如下：

<?xmlversion="1.O"encoding="UTF-8"standalone $\ c =$ "yes"?>   
<Meridians> <Meridian id="STYFJ"name="手太阴肺经"targetRotation $= " 4 . 8 , 3 5 9 . 4 , 0 "$ scale $\ c =$ "1.5"position $= " 0 { , } 0 { , } 0 " >$ <AssociatedAcupoint id="A1 $" / >$ <AssociatedAcupoint id="A2"/> </Meridian>   
</Meridians >

采用XML实现了针灸铜人所承载的所有穴位、经络和常见疾病等知识的表示与存储之后，采用W3C（WorldWideWebConsortium）组织推荐的DOM解析方式可快速对知识模型进行解析，从而获得穴位、疾病或经络任意节点的属性信息。

# 2 针灸铜人三维模型简化算法

本文设计的针灸铜人三维模型需要在 Web 浏览器和智能手机等移动终端上显示，因此拟采用LOD（levelofdetails，层次细节模型）技术对三维模型进行简化，以提高可视化效率。LOD技术是由Clark提出的一种具有代表性的模型简化算法，其主要思想是化繁为简，即通过简化算法将原来的模型简化为近似模型，从而获得高效的渲染速度，增加三维场景的流畅度，并节省计算机资源[12]。

# 2.1 QEM算法

在使用LOD技术进行模型简化策略方面，本文主要采用基于边折叠的简化算法来自动生成针灸铜人的连续LOD模型。其中，由 Garland 等人提出的基于二次误差度量(quadric errormetrics，QEM)的边折叠算法[13]不仅计算速度快，而且简化质量较高，成为了是一种经典的格网简化算法。

QEM算法的基本思想是首先确定每个顶点的误差矩阵，再根据顶点误差矩阵来计算边折叠的代价。在边折叠的执行过程中每次都选择代价最小的边进行折叠，直到模型达到所要求的分辨率为止。边折叠代价的具体计算方法如下：

假如 $\nu$ 是三维空间空间中的一点， $\boldsymbol { \nu } = [ \nu _ { x } , \nu _ { y } , \nu _ { z } , 1 ] ^ { T } , \boldsymbol { p }$ 是三维空间与 $\nu$ 相关联三角形所在的一个平面， $\pmb { p }$ 由方程$ a x + b y + c z + d = 0$ 定义，其中 $a ^ { 2 } + b ^ { 2 } + c ^ { 2 } = 1$ ，令$p = [ a , b , c , d ] ^ { T }$ ，那么顶点 $\nu$ 到平面 $\pmb { p }$ 的距离平方可表示为

$$
d ^ { 2 } ( \nu ) = ( p ^ { T } \nu ) ^ { 2 } = \nu ^ { T } ( p p ^ { T } \nu ) = \nu ^ { T } K _ { p } \nu
$$

其中：

$$
K _ { _ { p } } = p p ^ { T } = { \left[ \begin{array} { l l l l } { a ^ { 2 } } & { a b } & { a c } & { a d } \\ { a b } & { b ^ { 2 } } & { b c } & { b d } \\ { a c } & { b c } & { c ^ { 2 } } & { c d } \\ { a d } & { b d } & { c d } & { d ^ { 2 } } \end{array} \right] } ^ { 2 }
$$

将 $K _ { p }$ 称做平面 $\pmb { p }$ 的基本误差二次型，用来求解空间中任意一点到该平面距离的平方。

假设与顶点 $\nu$ 相关联的三角形平面集合为 $P ( \nu )$ ，那么该顶点的二次误差度量被定义为它到这些三角形平面的距离平方之和：

$$
\Delta ^ { \prime } ( \nu ) = \sum _ { p \in P ( \nu ) } d _ { p } ^ { 2 } ( \nu ) = \sum _ { p \in P ( \nu ) } \nu ^ { T } K _ { p } \nu = \nu ^ { T } ( \sum _ { p \in P ( \nu ) } K _ { p } ) \nu
$$

设顶点 $\nu$ 的二次误差测度矩阵为 $\mathcal { Q } ^ { \prime } ( \nu )$ ，则有

$$
Q ^ { \prime } ( \nu ) = \sum _ { p \in P ( \nu ) } K _ { p }
$$

该矩阵是一个4阶的对称矩阵，是集合 $P ( \nu )$ 中面的二次矩阵 $K _ { p }$ 之和。

若边 $( \nu _ { i } , \nu _ { j } )$ 通过边折叠到新顶点 $\overline { { \nu } }$ ，则通过上述公式可计算得边折叠的代价：

$$
\Delta ^ { \prime } ( \overline { { \nu } } ) = \overline { { \nu } } ^ { T } ( Q _ { i } ^ { \prime } + Q _ { j } ^ { \prime } ) \overline { { \nu } } = \overline { { \nu } } ^ { T } Q _ { k } ^ { \prime } \overline { { \nu } }
$$

其中： $Q _ { k } ^ { \prime } = Q _ { i } ^ { \prime } + Q _ { j } ^ { \prime }$ 用于近似表示新顶点 $\overline { { \nu } }$ 的二次误差矩

阵。

# 2.2QEM算法改进

虽然经典的QEM算法能够对模型进行快速简化，但是由于只考虑距离度量，在大规模简化之后，模型表面较为尖锐的棱角等重要几何特征会丢失[14]。因此，不少学者对其进行了改进研究[15-17]，但是部分改进算法仍然存在尖端特征消失、边界收缩、计算复杂等不足。为了实现模型简化的同时尽可能保留原始模型的尖端特征，本文对QEM算法进行改进。

文献[18]证实绝对曲率相比于高斯曲率、平均曲率更适用于三角网格模型的简化，考虑到一个自适应权值与二次误差矩阵的乘积不会改变二次误差矩阵的基本性质，只会使边折叠的顺序发生改变[14]，为此本文的改进策略为：在QEM 算法中将顶点的二次误差矩阵与顶点的绝对曲率的乘积作为新的误差测度矩阵。改进算法的具体实现如下：假设有如图3所示的几何体：

![](images/24cc696ba771219e1967260a1b04982535271e274cff8d71d66c16d72e47075e.jpg)  
图3顶点曲率示意图

则其平均曲率 $H$ 定义为

$$
H = \frac { \sum m ( e _ { i } ) } { A }
$$

$H$ 表示相邻的三角形面片的弯曲程度，其中， $A$ 是和顶点$\nu$ 关联的三角形的面积总和， $m ( e _ { i } )$ 为与边 $e _ { i }$ 相邻的两个三角形面的法向量夹角。

几何体的高斯曲率为

$$
K = { \frac { 2 \pi - \sum _ { i = 1 } ^ { k } \theta _ { i } } { A } }
$$

该高斯曲率表示曲面的弯曲程度，其中 $\theta _ { i }$ 表示与顶点 $\mathbf { \sigma } _ { \nu }$ 相关的顶角。

假设 $k _ { 1 } , \ k _ { 2 }$ 为顶点 $\mathbf { \Phi } _ { \nu }$ 处的两个主曲率，那么有如下公式：

$$
k _ { 1 } = H + \sqrt { ( H ^ { 2 } - K ) }
$$

$$
k _ { 2 } = H - \sqrt { ( H ^ { 2 } - K ) }
$$

当 $H ^ { 2 } - K < 0$ 时，令 $H ^ { 2 } - K = 0$ 。由此便可得到顶点 $\mathbf { \Lambda } _ { \nu }$ 处的绝对曲率 $K _ { a b s }$

$$
K _ { a b s } = \left| k _ { 1 } \right| + \left| k _ { 2 } \right|
$$

假设边 $( \nu _ { i } , ~ \nu _ { j } )$ 折叠到新顶点 $\overline { { \nu } }$ ，则改进后的边折叠代价为

$$
\Delta ^ { \prime \prime } ( \overline { { { \nu } } } ) = \parallel \nu _ { i } \nu _ { j } \parallel \overline { { { \nu } } } ^ { T } ( K _ { i a b s } Q _ { i } ^ { \prime } + K _ { j a b s } Q _ { j } ^ { \prime } ) \overline { { { \nu } } }
$$

其中： $\big \| \nu _ { i } \nu _ { j } \big \|$ 为顶点 $\nu _ { i \setminus \nu _ { j } }$ 间的距离， $K _ { i a b s }$ 和 $K _ { j a b s }$ 分别为

Vi、vj的绝对曲率， $\boldsymbol { Q } _ { i } ^ { \prime }$ 、 $\boldsymbol { Q } _ { j } ^ { \prime }$ 分别为 $\nu _ { i }$ ， $\nu _ { j }$ 的误差矩阵。

由式 (11)可知，新顶点的位置不同会产生不同的边折叠代价，从而影响边折叠顺序，并最终影响简化模型的精度。在边折叠时，对于如何选取新顶点 $\overline { { \nu } }$ ，目前主要有两种策略：一种是分别计算边的两个端点和中点的 $\Delta ^ { \prime \prime } ( \overline { { \nu } } )$ ，从中选取折叠代价值最小的作为新顶点，某些改进算法就是通过这种半边折叠的思路来提高计算效率。第二种策略就是针对每条边选取 $\Delta ^ { \prime \prime } ( \overline { { \nu } } )$ 最小的点作为新顶点，这种方法简化效果较好，但计算量较大。本文采用这两种策略的综合，对于非模型边界的边，首先求解$\Delta ^ { \prime \prime } ( \overline { { \nu } } )$ 的最小值，如果能获取，就用对应的点作为新顶点，如果不能得到最小值，就采用策略一，从端点或中点中选择二次误差最小的点。对于处于边界的三角边，则直接采用策略一来选取新顶点。

# 2.3基于改进QEM的递进网格算法实现

常规网格简化算法只能构造静态LOD 模型。在三维可视化过程中，需要预先构造多个细节层次模型，以便在不同视距下加载不同LOD 模型，实现平滑过渡。递进网格(ProgressiveMesh，PM算法可以根据系统需求快速生成不同层次的网格模型，即任意两个LOD 模型之间可以互相转化[15]。PM算法是以边折叠和点分裂为基本操作的模型简化算法，其原理是每次在对网格进行简化的同时记录下本次简化操作的序列，而基于这组操作序列就可以还原初始模型。PM 算法的基本操作如图 4所示：

![](images/2e0a1d3ab4a19b749dcd8fa456b073bd5aa2acb35ce036dc8841133f8da596e2.jpg)  
图4PM算法中的边折叠和点分裂操作

从图中可以看出，PM算法必须在每次进行边折叠时保存必要的信息，这些信息包括：（1)需要折叠的边的两个顶点Vfrom和 $\nu _ { t o }$ ；（2）被删掉的三角形 $T _ { r e m o \nu e }$ ；（3）边折叠后需要改变顶点的三角形 $T _ { e f f e c t }$ 。

因此，采用改进后的边折叠代价函数和PM算法生成多细节层次模型的具体过程如下：

a)导入模型，对模型进行初始化。

b)计算原始模型中每个顶点的二次误差矩阵 $Q ^ { \prime } ( \nu )$ 和绝对 曲率 $K _ { a b s }$ 。

c)根据式(11)分别计算出每个顶点折叠到邻近顶点的代价cost，并存储代价最小的值和新顶点的位置。

d)对上一步中计算出的值进行比较，将顶点依据cost值升序排列，创建一个顶点队列。

e)从顶点队列中取出第一个顶点进行边折叠操作。假设要折叠的边为 $( \nu _ { f r o m } , \nu _ { t o } )$ ，该操作将把点Vfrom折叠到点 $\nu _ { t o }$ ，同时会移除点 $\nu _ { f r o m }$ 和与该边相关的三角形，用点 $\nu _ { t o }$ 代替点 $\nu _ { f r o m }$ ，从顶点队列中移除Vfrom。

f)重新计算点 $\nu _ { t o }$ 及其邻近点的边折叠代价，并更新顶点队列。

g)记录本次边折叠操作。

h)如果顶点为空或达到用户要求，则跳转到步骤9；否则跳转到步骤e)。

i)结束。

# 3 实验与分析

基于改进QEM的递进网格算法采用Visual $^ { C + + }$ 语言和OpenGL库编程实现，在Win10 操作系统，IntelCore i7-47703.40 GHz CPU、8 GB 内存和NVIDIAGeForceGTX1050 Ti显卡配置计算机上进行针灸铜人三角网模型的多尺度简化实验，简化结果利用开源MeshLab[20]软件进行可视化，如图5所示。

![](images/305a3f3b74cdf7f4a79913c5f4f937aca4abdcd9d8861b673c52ffb1a6a271d7.jpg)  
图5本文算法模型简化结果

在MeshLab软件中采用QEM简化算法所得结果如图6所示。

![](images/54b944ba55bda518483c2620fe03ca3c006399c7a478791b37c76478769b00dd.jpg)  
图6传统QEM算法模型简化结果

从两种算法结果对比可以看出，随着简化程度的递增，本文算法在保留模型尖端特征方面明显优于QEM算法，如铜人的手指、鼻子、耳朵等重要轮廓特征在简化率达到 $9 0 \%$ 以上时依然保持较好。这是因为本文算法在计算边折叠代价时不仅考虑了顶点的二次误差矩阵，而且还充分利用了顶点的绝对曲率，而绝对曲率能够更好地表达模型表面的尖端特征。图7展示了分别使用顶点的平均曲率、高斯曲率和绝对曲率对原始模型进行颜色渲染结果，可以看出铜人的手指、鼻子、眼睛、耳朵、额头等部位的绝对曲率特征比其他曲率特征体现更明显，绝对曲率与顶点的二次误差矩阵相乘可以使这些区域的顶点误差测度增大，从而改变边折叠次序，使得原始模型的重要特征在简化结果中较好地保留下来。

![](images/1d58f9cfe38bc7334c3d134f1311b46395c87ec6522f8a72b08420ded5bdb968.jpg)  
图7针灸铜人模型采用不同离散曲率渲染结果

针灸铜人三角网模型由15926个顶点和31857个三角面组成。使用上述两种算法进行不同程度简化后的顶点、三角面片数量和耗时信息如表4所示。

表4不同细节层次的模型信息与耗时  

<html><body><table><tr><td rowspan="2">简化率</td><td rowspan="2">顶点数(个)</td><td rowspan="2">三角面数(个)</td><td colspan="2">耗时(s)</td></tr><tr><td>本文</td><td>QEM</td></tr><tr><td>50%</td><td>7966</td><td>15930</td><td>17.92</td><td>0.51</td></tr><tr><td>90%</td><td>1595</td><td>3186</td><td>25.23</td><td>0.64</td></tr><tr><td>95%</td><td>798</td><td>1592</td><td>25.42</td><td>0.68</td></tr></table></body></html>

从表4来看，当模型简化 $9 5 \%$ 时，模型顶点数量由原来的15926个减少到 798个，而三角面数量也减少了30 265个，obj模型文件大小也从 $5 6 9 6 \mathrm { K B }$ 减少到了 $5 0 \mathrm { K B }$ ，在内存消耗减小、可视化渲染效率大幅提升的同时，本文算法依然能够保持模型不失真。

在算法执行效率方面，本文算法在这三种简化情况下平均耗时 $2 2 . 8 5 \mathrm { ~ s ~ }$ ，而QEM算法平均耗时不到1秒。由于本文算法在计算边折叠代价时不仅需要计算顶点绝对曲率，而且还需要存储边折叠时一些必要的信息，所以时间复杂度比QEM算法要高。虽然基于改进QEM算法的递进网格构造时间较长，但是递进网格的简化信息序列可以在预处理阶段完成，在后续简化过程中可以直接使用，不需要重新生成。在三维可视化时，通过正向或逆向跟踪简化信息序列并执行相应操作，即可实时生成相应LOD模型，实现模型的平滑过渡。

# 4基于Unity的针灸铜人虚拟交互系统设计与实现

根据以上关键技术研究，笔者基于Unity开发引擎和C#编程语言开发了一套针灸铜人虚拟交互展示系统，实现针灸铜人及传统中医知识在三维环境下的动态交互展示。

# 4.1系统设计

针灸铜人虚拟交互展示系统的构建流程如图8所示。系统主要由三维建模和虚拟现实技术开发两部分组成。其中，三维建模是指用三维激光扫描仪获取高精度针灸铜人三维点云，然后在3DSMax软件中进行贴图渲染和烘焙输出三维模型。中医知识表达模型利用XML语言构建，形成穴位、经络和常见疾病三种结构化文档数据。将利用模型简化算法生成的不同细节层次模型导入Unity软件中，设置LOD策略并搭建模型展示场景，设计交互界面，最后在VisualStudio2015开发平台中编程实现各类交互展示功能的消息响应。

三维激光扫描  
三维建模 仅理购，核有造染中医知识表达模型构建虚拟场景搭建  
虚拟现实开发 虚拟交互设计与实现编译发布针灸铜人虚拟交互展示系统

系统功能结构如图9所示，主要由三维模型交互和中医知识交互两大模块构成。模型交互主要包括针灸铜人模型的缩放、旋转和平移等基本操作；知识交互则重点展示针灸铜人的基本信息、穴位点击查询、经络分布信息展示、疾病知识及关联穴位信息展示等功能。

![](images/5a989cf62f9d135253c469453504ee1e136fdd7d9e00b614df5bba98e11f808b.jpg)  
图8针灸铜人虚拟交互展示系统构建流程

# 4.2交互功能实现

针灸铜人的平移、缩放、旋转等基本交互功能主要在Unity里面通过设置摄像机相关属性来实现，在此不赘述。下面重点介绍中医知识交互展示功能的实现方法。

穴位点击查询是本系统的一项重要功能，对于该功能的实现有两种方法：a）对每一个表示穴位的组件添加一个脚本，在脚本里面单独编写获取穴位信息的程序。这种方法虽然计算效率高，但是由于铜人模型共有354个穴位，对每个穴位手工添加脚本和响应事件显然工作量巨大，开发效率低;b）在Unity中捕获鼠标点击事件，当捕捉到该事件后，根据Unity里面的Raycast机制，从当前鼠标点击的位置向虚拟的三维世界里发射一条射线，通过碰撞检测获得射线穿过的物体信息，将物体的ID 作为参数传给中医知识模型的XML解析程序，最终获得对应穴位的相关信息，将其展示出来。

显然第二种方法开发效率高，本文主要采用该方法来实现交互响应。算法具体步骤描述如下：

a)捕获鼠标事件。

b)如果当前鼠标为左键点击状态则跳转到步骤3，否则跳

转到步骤k)。

c)获得鼠标的点击位置。

d)从鼠标的点击位置创建一条射向Unity世界里的射线raycast。

e)如果该射线碰撞到了某物体则跳转到步骤f)，否则跳转到步骤j)。

f)获得碰撞检测到的物体hit。

g)将物体hit的ID传递给穴位本体解析程序得到穴位知识模型acupoint。

h)激活信息展示界面并将acupoint的信息展示到界面上。

i)更改物体hit的材质并跳转到步骤k)。

j)隐藏信息展示界面。

k)结束。

最终获得的穴位点击交互效果如图10所示，当前点击查询到的穴位用红点表示，左侧展示该穴位的名称和功效等知识信息。

![](images/c111c360bcd8f6950016b8fbcd6c0b1c022b9dccb356eeb5f9c0e8b9afb8193f.jpg)  
图10穴位点击交互功能效果图

由于常见病和经络的交互功能类似，这里仅选择常见病来简要说明交互功能的实现方法。当点击系统界面的“常见病”按钮时，弹出二级菜单界面，包含内科和外科一些常见疾病的名称，如图11所示。

![](images/643da4850033bc8bc131bc1a781514315185e2360fc634f01845ee437519062f.jpg)  
图9系统功能结构图  
图11常见病二级菜单界面图

针对图11二级菜单中按钮的响应，系统会根据前面构建中医疾病知识本体模型时存储的三维位置姿态信息进行知识模型到三维模型的映射，再将具体病症相关知识信息呈现到针灸铜人模型上展示。其算法描述如下：

a)获得鼠标点击按钮对应的button对象。

b)将该button 的name 属性传递给疾病本体解析程序，从疾病XML文档中获得对应疾病(disease)节点的相关属性信息。

c)取出 disease 节点中保存的 modelRotation、modelScale、modelPosition属性值，将其赋给针灸铜人模型的transform，从而调整模型的位置姿态。

d)取出disease节点中保存的AssociatedAcupoints（关联穴位)列表，根据每个穴位ID找到对应穴位在模型上的空间位置，并在针灸铜人三维模型上高亮显示这些穴位点。

e)取出disease 中保存的mainAcupoints 信息，将疾病名称和关联穴位等文本知识显示到三维场景中。

f)结束。

最终实现的疾病知识交互展示效果如图12所示。

![](images/1f813677344624ea6f0dd3e8ce592f45ea654913feba16acff0e371c9aeb394d.jpg)  
图12常见疾病与穴位关系交互展示示例

# 4.3 系统发布

系统功能全部实现之后，借助Unity的跨平台特性，可以快速将其编译并分别发布到Web 浏览器、安卓(Android)和苹果(iOS)手机系统等不同应用平台进行展示。系统能够自适应不同终端的屏幕分辨率，界面友好，操作简单，如图13所示。借助互联网和智能手机等终端进行针灸铜人和传统中医知识的三维交互展示，可以使其最大限度的共享共用，从而增强文化遗产的体验感和传播力。

![](images/7d2fb4ef1c12e3bb5b0277680c301b2c72ceaadb666cc27a5de1f53f33239cc8.jpg)  
图13针灸铜人虚拟交互展示系统手机端应用示例

# 5 结束语

非物质文化遗产的数字化保护与传承一直以来都受到了国家极大重视，然而传统的数字化手段比较单一，大部分是利用文字、图片、音频和视频等媒介形式简单记录，难以直观、动态展示某些文化遗产的内涵。本文尝试将三维激光扫描、三维可视化、虚拟现实和移动互联网等技术应用于针灸铜人及其承载的传统中医知识的数字化保护，不能能够建立逼真的三维模型，使得铜人模型在智能手机等移动终端运行流畅，而且还能借助该模型实现部分中医知识的虚拟交互展示，使中华传统针灸相关知识更容易理解、利用和传播。本文提出的技术方法为历史文物和非物质文化遗产相结合的数字化保护与传播提供了一种新的解决方案。然而，本文提出的中医知识表达模型较为简单，本体相关理论和方法应用不够深入。针对不同类别的非物质文化遗产项目，今后需要根据其特点，研究更多行之有效的数字化保护、传承与传播方法。

# 参考文献：

[1]甄雪燕，邹慧琴．国礼—“针灸铜人”[J].中国卫生人才，2017 (6): 90-91.(Zhen Xueyan, Zou Huiqin. National ceremony: bronze acupuncture figure [J]. China Health Human Resources,2O17(6): 90-91.)

[2] 泽金.世界文化遗产数字化保护与建设初探—一以西藏罗布林卡古建 筑为例[J].文物保护与考古科学,2017,29(4):115-122.(ZeJin.Digital protection and construction of world cultural heritage objects: taking as an example,ancient buildingsat Norbulingkain Tibet [J].Sciencesof Conservation and Archaeology,2017,29 (4): 115-122.)

[3]Murphy M,Mcgovern E,Pavia S.Historic building information modelling: adding intelligence to laser and image based surveys of European classical architecture [J]. ISPRS Journal of Photogrammetry and Remote Sensing, 2013,76: 89-102.

[4]李德仁．虚拟现实技术在文化遗产保护中的应用[J].云南师范大学学报：哲学社会科学版，2008,40 (4):1-7.(Li Deren.The application ofvirtual reality technology to cultural heritage protection [J]. Journal ofYunnan Normal University: Humanities and Social Sciences,2oo8,40 (4):1-7.)

[5]宗立成，任斌．基于计算机辅助设计的文物数字化方法研究[J].计 算机工程与应用，2017,53(15):250-254.(Zong Licheng，Ren Bin. Research on digitalization method of cultural relics based on computer aided design [J]. Computer Engineering and Applications,2O17,53(15): 250-254. )

[6]孔黎明，荣晓曼．增强现实技术在文化遗产展示中应用综评[J]．中国 文化遗产,2017 (2): 62-69.(Kong Liming,Rong Xiaoman.Application of augmented reality in cultural heritage visualization:a review [J].China Cultural Heritage,2017 (2): 62-69.)

[7]黄永林，谈国新．中国非物质文化遗产数字化保护与开发研究[J].华 中师范大学学报：人文社会科学版,2012,51(2):49-55.(HuangYonglin, Tan Guoxin.Research on digital protection and development of Chinese intangible cultural heritage [J]. Journal of Huazhong Normal University: Humanities and Social Sciences,2012,51(2): 49-55.)

[8]李晓旭．基于VR 技术的针灸铜人中医知识可视化研究[D].武汉：华 中师范大学，2017.(Li Xiaoxu.Research on visualization of TCM knowledge about bronze acupuncture figure based on VR technology [D]. Wuhan: Central China Normal University,2017.)

[9]李清泉，杨必胜，史文中，等．三维空间数据的实时获取、建模与可视 化[M].武汉：武汉大学出版社,2O03.(LiQingquan,Yang Bisheng,Shi Wenzhong,et al.Real-time acquisition,modeling and visualization of 3D spatial data [M].Wuhan:Wuhan University Press,2003.)

[10]索俊锋，刘勇，蒋志勇，等．基于三维激光扫描点云数据的古建筑建模 [J]．测绘科学，2017，42(3):179-185.(Suo Junfeng，Liuyong，Jiang Zhiyong,et al.Modeling of ancient building based on 3D laser scanning point cloud data [J]. Science of Surveying and Mapping,2O17,42(3): 179-185. )

[11]邓志鸿，唐世渭，张铭，等.Ontology研究综述[J]．北京大学学报：自 然科学版,2002,38(5):730-738.(Deng Zhihong,Tang Shiwei,Zhang Ming，et al.Overview of ontology [J].Acta Scicentiarum Naturalum Universitis Pekinesis,2002,38 (5): 730-738.)   
[12] Clark JH. Hierarchical geometric models for visible surface algorithms [J]. Communications of the ACM,1976,19 (10): 547-554.   
[13] Garland M,Heckbert P S.Surface simplification using quadric error metrics [C]//Proc of the 24th annual conference on computer graphics and interactive techniques.1997:209-216.   
[14]杜晓辉，尹宝才，孔德慧．基于加权二次误差测度的边折叠简化算法 [J]．北京工业大学学报,2007,33(7):731-736.(Du Xiaohui,Yin Baocai, Kong Dehui.Edge collapse simplification based on weighted quadric error metrics [J].Journal of Beijing University of Technology,20o7,33（7): 731-736.)   
[15]顾耀林，赵争鸣，魏江涛．距离加权的二次误差测度多分辨率网格简化 [J].计算机工程与设计，2007，28(8):1966-1968.(Gu Yaolin，Zhao Zhengming，Wei Jiangtao.Multiresolution mesh simplification algorithm with distance-weighted quadric error metric [J].Computer Engineering and Design,2007,28 (8): 1966-1968.)   
[16]陈伟海，徐鲤鸿，刘敬猛，等．网格简化中基于特征矩阵的二次误差测 度算法[J].北京航空航天大学学报，2009，35(5):572-575.(Chen

Weihai,Xu Lihong,Liu Jiingmeng,et al.Quadric error metrics for mesh simplification based on feature matrix [J].Journal of Beijing University of Aeronautics and Astronautics,2009,35(5): 572-575.)

[17]熊仕勇，李沁翰，谢爱荣．基于半边折叠的LoD三维模型简化算法[J]. 计算机工程与设计,2016,37(3):655-659.(Xiong Shiyong,Li Qinhan, Xie Airong.Simplification algorithm for 3D LoD model based on half-edge collapse [J]. Computer Engineering and Design,2O16,37(3): 655-659. )

[18]Pulla S,Razdan A,Farin G. Improved curvature estimation for watershed segmentation of 3-dimensional meshes [J].IEEE Trans on Visualization & Computer Graphics,2001:1-15.

[19]Hopper H.Progressive meshes [C]// Proc of the 23rd International Conference on Computer Graphics and Interactive Techniques.1996: 99-108.

[20] CignoniP.,Callieri M.,Corsini M.,et al.MeshLab:an open-source mesh processing tool [C]//Proc of the Eurographics Association.2008:129-136.