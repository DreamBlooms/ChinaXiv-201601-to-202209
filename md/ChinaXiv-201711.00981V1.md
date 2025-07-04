# Revit三维显示技术的开发及应用

贾盈平李春祥（上海大学土木工程系，上海200072）

【摘要】建筑模型的可视化，是数字化建模技术在各个专业之间信息交换与共享的重要途径，直观、高效、准确的模型显示是项目顺利进行的有力保障。目前，Revit通过“剖面框”功能实现基于区域的模型三维显示，但此功能受模型大小、硬件配置的制约，在实际应用过程中，还存在反复旋转模型视图、不断伸缩剖面框边界、重复操作、工作效率低下的问题。基于此基础，论文分析了Revit模型可视化技术的应用要点，假设出一种新的基于区域的三维模型显示功能，并且结合RevitAPI开发技术，实现了此功能的研发。最后介绍了研发的关键流程，同时以一装配式钢结构为应用实例，展示应用效果，为推动BIM软件其他技术的发展提供参考。

【关键词】BIM；可视化；剖面框；区域显示

【中图分类号】TU17 【文献标识码】A 【文章编号】1674-7461（2016）01-0038-05  
【DOI】10.16670/j.cnki.cn11-5823/tu.2016.01.06

# 引言

BIM思想来源于卡耐基梅隆大学的ChuckEastman，是计算机数字信息技术与图形技术的结合。BIM本质上是一个包含建筑工程生命全周期的数据库，在项目不同阶段，模型信息能够沿着项目链双向传递、动态关联、实时共享与转化，保证了信息技术在整个项目中的唯一性，实现了造价咨询，设计、施工各个参与方的协同合作，避免了“孤岛现象"的产生13。另一方面它通过三维图形技术将模型信息可视化，实现了从传统二维施工图纸到三维空间模型的转变，使得模型能够直观地展示各种构件之间的关系。同时，BIM模型附带工艺设备属性、建筑材料材质、模型环境、灯光渲染等信息，使得模型具有真实性45。

BIM可视化技术在投资方、设计方以及施工各方有重要应用意义。在Revit中它不仅可以实时展示各种设备、构件的空间布局，为初步建模提供设计依据，还可以对复杂节点的构造、相邻构件的位置、尺寸信息进行全方位展示，大大提高了后期碰

撞检查的效率。

BIM技术是建筑协同设计[6]的有力手段，由于各个专业技术软件都有自己的数据存储形式，自己的命名规则与映射关系，故如何准确高效地实现各专业之间的信息互通成为BIM技术应用的难点。目前，基于Revit软件插件的研发大多集中在研发插件使得不同专业的信息能够互通共享。高效准确地显示项目工作人员所要的模型信息，丰富视图显示功能，真正实现所想即所现，同样是BIM技术得到更全面的应用的关键。而对于可视化技术方面的研究，大多数国内外学者也只是针对标准化图层以及三维模型的视图管理实施方法进行了研究8-12]，并未实现技术的二次开发，创新实用性不大。虽然市面上个别软件研发公司开发了相关视图显示功能，但基于研发公司的性质，不会对后台研发关键技术步骤作阐述，理论背景不足，广大研发学子找不到任何头绪进行深入学习研究，因此学术研究意义并不大。

结合上述情况，本文对Revit模型可视化应用作了分析，结合Revit二次开发技术，实现了对三维显示技术的二次开发，并对关键研发技术做了阐述。

# 1三维显示技术应用分析

Revit中将各个图元对象按照不同类别，族，类型进行分类如图1。不同的类别按照对象自身功能属性的不同进行类别大类的分类如：墙、梁、板、柱、门、橱柜等为模型类别；参照线、参照点、剖面则归属于注释类别。每个类别按照对象材质、外形构造、参数定义、施工工艺等方面的不同又分为不同的族。对族的进一步实例化，如尺寸大小的不同又将族分为不同的类型。因此，Revit中“可见性图形”、“过滤器”等基本的构件三维视图显示命令，都是基于这种归类原则的。

模型类别  
类别 柱  
族 圆柱 方形柱  
类型 5m 8 40方00mm （204号$\pmb { 6 0 0 } \pmb { 6 0 0 } \pmb { \operatorname { m m } }$

然而以Revit自带的建筑样板一层厨房中的厨房家具模型为例（位置信息，构件类型信息图2，3所示），可以看出同一个模型构件可能包含不同的类别信息，因此Revit中引入“剖面框”命令，通过不断伸缩剖面框边界，确定要显示的空间，使模型能够实现区域显示。

![](images/ea9afd743f7cb8606855fe865b53bd41db4549bd57d8eabb5c1290c3105bde09.jpg)  
图1Revit图元分类

# 2二次开发效果的提出

虽然Revit实现了基于区域的三维显示功能，但是实际操作中会发现，确定剖面框的位置需要反复旋转整个模型，若是模型信息量较大，硬件配置一般，无疑需要一定的等待时间。除此之外，对于模型组合复杂的区域，很难将剖面框伸缩到恰当位置，建模师通常还会借助显隐功能将不需要的类型隐藏起来，操作过于繁琐。

![](images/23b16301c41f1fb33642f4b5c8dadc09f9cb50c43686294f819bd3bfa64d8d06.jpg)  
图3模型的图元类型信息

![](images/6a47bad4b5126602e2fc778b5bad0e83176120b19d6828699e2f5de7e2f11313.jpg)  
图2厨房家具模型在当前视图中的位置

如何快速确定剖面框的边界？能否根据当前视图中的对象直接确定剖面框的位置、尺寸，实现如下图4所示的功能？

当选择任意一个对象，该对象区域内全部类型被显示，如图4（a），由于 $\textcircled { 1 }$ 、 $\textcircled{2}$ 两处没有选择，因此剖面框将直接切割区域以外的部分。当选择多个对象时，如图4(b)，由于 $\textcircled{4}$ 被选中，而剖面框又是平行六面体，故显示区域在(a)的基础上沿Y方向增加了部分龙头高度， $\textcircled{3}$ 处也被显示。

![](images/1974c16bf929d5c201e91b1455e10b38671ee355123a7aa70a20c20f1f3b0ef1.jpg)  
图4三维实体显示效果对比图

本文在以上需求下，借助Revit二次开发平台，对三维区域显示技术进行了二次开发，实现了上述功能效果。

# 3技术研发要点

# 3.1 开发工具

Revit具有完善的二次开发平台，用户可以通过Revit的应用程序编程接口（ApplicationProgramIn-terface，简称“API”），参考RevitSDK手册，借助Vis-ualBasic.NET、C#以及 $\mathrm { C } + + / \mathrm { C L I }$ 等任何与.NET兼容的编程语言进行编程，实现应用程序的开发[13]。本技术研发依托Revit2016版本，借助VS2012开发程序，C#编程语言。

# 3.2 开发流程

每个视图都有一个裁剪盒，它的作用就是决定模型在视图中显示哪部分。BoundingBoxXYZ定义了一个三维的平行于坐标轴的长方体盒，空间位置由坐标点Max（盒子的上-右-前角），min（盒子的下-左-后角)两个属性参数确定。对于三维视图来说，存在另一个概念-剖面框（SectionBox），Sec-tionBox属性接受一个BoundingBoxXYZ实例，用来确定三维模型的可见部分[14-15]。虽然可以通过视图的裁剪盒属性（View，CropBox）定义视图的边界，但剖面框决定了模型的可见性，在剖面框外面的部分即使在裁剪盒内部也无法显示。基于上述理论基础确定本文的关键研发流程。

1）创建一个新的裁剪盒BoundingBoxXYZbox，一个新的剖面框SectionBoxbox2；

2)在当前三维视图界面中选择对象，并生成集合List $<$ ElementId $>$ elementIds。box2通过存储ele-mentIds的位置信息，确定其位置参数 $\mathbf { M a x ( \xi ) } , \mathbf { m i n ( \xi ) }$ 3）将box2的空间位置参数传递到box;4)将裁剪盒box空间位置参数更新到当前三维视图中，实现所选区域的三维显示。

# 3.3编程要点介绍

由于本技术应用前提是在三维视图中，因此程序开始时要判断doc.ActiveView是否为View3D，不满足条件时跳出警告框。elementIds是用户通过鼠标单击直接获得的模型对象集合，因此需要首先定义一个IList $<$ Reference $>$ 集合存储拾取到的对象。

本技术采用了扩展存储技术，需要引用Schema类。在面向对象语言中，一个Schema好像是一个类，而一个Entity就是它的一个对象。利用此技术可以把任何的数据保存在Revit中的任何一个Enti-ty上，并且可以设置访问权限。本文首先创建了一个Schema，box2则是基于该架构创建的一个Entity类型，当box2的的Max（）， $\operatorname* { m i n } ( { } )$ 参数值确定以后，将它与上步定义的裁剪盒box相对应的参数关联，实现了空间位置的传递，完成了局部对象的三维视图显示，此过程主要借助函数view.SetEntity（box2）实现。

# 4 工程应用

# 4.1 项目背景

本工程是位于安徽省池州市的某宿舍楼。工程基底面积约 $5 0 0 \mathrm { m } ^ { 2 }$ ，总建筑面积约 $3 \ 0 0 0 \mathrm { m } ^ { 2 }$ ，建筑为六层，高度 $1 8 \mathrm m$ 。结构类型为钢结构采用装配式施工技术，如图5所示。本工程严格按照Revit建模及加工图要求、2015年9月28日项目装配式BIM协调会会议纪要等相关要求，完成Revit模型创建以及加工图设计说明。

![](images/4a21d9812925926886eb31cc876ea1bd5365b3f3cf0ba8f30f47fd0accdb9d5a.jpg)  
图5项目模型图

# 4.2 应用效果

# 4.2.1 快速展示区域模型

建模过程中，建模师一般选择“三维视图 $^ +$ 平面视图”的界面环境，平面视图中建模，三维视图中实时观察模型效果。过大的整体模型会影响视图浏览效果，因此三维视图通常是区域模型视图。另一方面，钢结构BIM模型是完全按照结构施工图进行建模的，但有些节点的建模是按照施工图节点详图大样创建的，即加工图必须要结合详细的BIM模型图与结构施工图，才能保证装配式模块顺利安装。所以本项目中需要大量使用区域模型视图。

以电梯间区域模型视图为例，由于此整体模型信息量偏大，采用“剖面框”命令时，模型旋转、剖面框拉伸过程中会出现停滞，视图不流畅现象，而此过程需要反复几次，使得效率大大降低。采用本文开发的技术，如图6，在当前视图界面下选定4个对象（图中标记处)作为剖面框边界条件，不需要旋转视图即可以生成相应的模型视图，一次操作既可以完成，为建模师节约大量时间。

![](images/9258667a05d2f40ef10388d26782d8e075b9d9a025529bd8e12480086a5d95a6.jpg)  
图6电梯间区域模型显示

# 4.2.2 快速查看构件间位置、尺寸

虽然建模人员是严格按照设计图纸创建模型，但由于二维图纸的局限性，避免不了三维模型中会出现构件位置尺寸设置不合理的情况。为了提高模型质量，Revit模型完成后，进入下一工作流程之前，建模人员首先会检查复杂部位是否存在碰撞交叉，位置尺寸不合理现象。此项目中机电管线复杂，管线位置尺寸是否合理不容易查看。利用本文开发技术，如图7（a），在模型“上视图”中确定剖面框的四个边界，将会得到相应区域的管线视图，同时由于视图内模型信息量的减少，通过鼠标“放大”“缩小”、“拖动”就可以快捷的查看任意关键部位，不会出现卡机不流畅等现象，如图7（b）。

![](images/b88f00e9ea20c8743184895da4cc1b38bfcc2971fc10be670fa25176b94b4ccf.jpg)  
图7复杂管线的位置、尺寸显示

# 5结论

可视化技术是一门语言，化抽象为具体，准确流畅的沟通了不同专业之间的工程信息，基于区域的三维显示技术在模型设计，项目交流方面发挥尤为重要的作用。“剖面框”功能使用时，剖面框的位置、尺寸必须通过反复旋转，伸缩操作才可以确定，效率低下。本文开发了一种通过选择的实体对象作为边界条件，直接确定剖面框位置尺寸的方法，一步到位，大大提高了工作效率，从而缩短项目周期，降低成本。

BIM软件研发方面，研发公司具有雄厚的实力，但基于当前市场环境，公司盈利性质，研发技术保密性很强，不利于BIM技术的发展。科学技术的发展需要社会各界共同努力，将更多的技术正确阐述出来，供更多学者技术人员学习研究，对推动BIM技术的发展与应用有深远影响。

# 参考文献

[1］LaserinJerry，王新.BIM的历史[J].建筑创作，2011，(6):146-150.  
[2］何清华，钱丽丽，段运峰等.BIM在国内外应用的现状及障碍研究[J].工程管理学报，2011，26(1）：12-16.  
[3]HuangT,KongCW,GuoHL,etal.Avirtualprototyp-ingsystem for simulating constructionprocesses[J].Auto-mationinConstruction，2007，16(5）:576-585.  
[4］王立媛，高路.基于BIM的项目级在线问题沟通平台开发与研究-乌鲁木齐高铁站项目[J].土木建筑工程信息技术，2015，7（4）：104-107.  
［5］魏英洪.BIM技术中建筑工程可视化应用方法及价值探讨[J].铁道勘察，2014，01：17-19.  
［6］苏骏，叶红华.基于BIM的设计可视化技术在世博会德国馆中的应用[J].土木建筑工程信息术，2009，1(1):87-90.  
［7］刘火生，张燕云，杨振钦，等。基于BIM技术的施工现场的可视化应用[J].施工技术，2013，42：507-508.  
[8］申志超，王强强，谢卫.CAD标准是规范勘察设计企业协同设计活动的基本准则[J].中国勘察设计，2009，(6):48-52.  
[9]HowardR,BjorkB.UseofstandardsforCADlayersinbuilding[J].AutomationinConstruction，2007，16（3）：290-297.  
[10]周成，邓雪原.建筑协同设计的模型视图管理应用研究[J].图学学报，2013，34(2)：94-100.  
[11］王潜平，林宗楷，郭玉钗.计算机支持的协同设计[J].计算机辅助设计与制造，1995，（9）：28-3.  
[12]周成，邓雪原.广域网建筑协同设计平台安全性与适用性研究[J].土木建筑工程信息技术，2010，2（2）：16-21.  
[13]高佐人，吴炜煜.建筑设计协同系统模型研究与通用平台实现[J].计算机集成制造系统，2003，CIMS(S1):112-117.  
[14]AutodeskAsiaPteLtd，AUTODESKREVIT二次开发教程[M].上海：同济大学出版社，2015：1-28.  
[15]AutodeskAuthorizedAuthor.Revit2Ol1APIDeveloper'sGui-de[M].American:AutodeskAuthorizedPublisher,2010.

# Development and Application of Three-Dimensional Display Technology of Revit

Jia Yingping，Li Chunxiang

(DepartmentofCivil Engineering，Shanghai University，Shanghai2OOO72，China）

Abstract：Visualizationofbuildingmodelsisanimportant wayfordigitalmodeling technologiestorealizeinformationexchangesandsharingamongdiferent specialties，whiledirect，eficientandaccuratemodeldisplayisa powerfulguaranteeforthesuccessfulcompletionoftheprojects.Atpresent,Revitrealizesthe3Dregionmodelby thefunctionof“sectionbox”.Butthisfunctionisaffectedbythesizeofthemodelandthelimitoftheconfiguration.Inpracticalapplicationprocess,weneedtorotatethemodelviewandstretchtheboundariesofthesectionbox repeatedly，whichisinefcient.Basedonthose,thekeypointsoftheapplicationofRevitmodelvisualizationtechnologyareanalysed.BasedonthedevelopmentofRevitAPItechnology,anewwayofdisplaing3Dviewwhichis basedonthespatial location is proposed.Then thekeytechnologiesareintroduceedandsomeapplicationexamples ofanassemblytypesteel structurearedemonstrated.Thismethod providesareferenceforthedevelopmentofother technologies about BIM software.

KeyWords:BIM；Visualization；SectionBox；Region Display