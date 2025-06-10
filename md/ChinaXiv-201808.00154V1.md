# 基于Revit的网架参数化建模

Parameterized modeling of Grid structure based on Revit 董爱平」，王海涵’，李国杰¹，仲伟秋²

（1中国汽车工业工程有限公司，天津 300113；²西安工程大学，西安710048)DONG Ai-Pingl,WANG Hai-Han1,LI Guo-Jie1,ZHONG Wei-Qiu²Automotive Engineering Corporation，Tianjin 300113;Xi'AnPolytechnic University,Xi'An710048.C.

【摘要】：目前Revit对于网架结构的建模存在很大问题。常规手动建模的方式几乎难以完成，而采用体量建模，所有的网架球和杆件类型相同，不符合工程实际。为了解决这一难题，本文分别研究了Revit Extensions 和Dynamo软件进行网架结构的建模解决方法，重点介绍了可视化编程工具 Dynamo 在 Revit 自动建模上的应用。对于设计人员，Dynamo 参数化编程工具相对容易掌握。本文编制的 Dynamo 程序，通过读取网架数据，能自动生成精确的网架模型，网架球和杆件的尺寸及定位与实际情况相符，提高了建模效率和模型质量。

【Abstract】：At present,Revit has great problems in the modelingof grid structure.Theconventional manual modeling approach is almost impossible tocomplete.Withtheconceptual mass,allte gridballand bar tpes are the same,don't meetthe actual engineering.Inorderto solve this problem,this paper studies the modeling methodof grid structure with Revit Extensionsand Dynamo software respectively,and the application of visual programming tool Dynamo in Revit automatic modeling is mainly introduced.Fordesigners,Dynamo parameterization tool is relativelyeasy to master.The Dynamo program developed in this papercan automatically generateanaccurate grid structure model by reading dataof grid structure.The sizeand locationof the gridballandbarareconsistent with theactual situation,and theefciencyof modeling and the quality of the model are improved.

【关键词】：Revit；Dynamo；参数化；网架结构【Keywords】:Revit；Dynamo；Parameterization；Grid structure中图分类号：TU391 文献标识码：A

# 文章编号：

# 前言

BIM模型的创建是一个参数化的设计过程，构件通过调整参数进行参变，衍生成设计模型。参数化设计是BIM建模软件的一个重要核心思想，因此软件的参数化能力是衡量一款BIM软件实用性最为重要的标准之一。在目前国内外的主流BIM软件中，Autodesk公司的Revit拥有非常强大的参数化设计能力，Revit通过族能参变生成各式各样的构件。

然而现阶段Revit也并没有专门的模块来创建空间网架结构模型。网架结构由网架球和杆件组成，通常模型构件数量巨大，即使是一般规模的小网架项目也包含成百上千个网架球和杆件。同时，实际项目中网架球的大小和杆件的类型没有规律，所以通过常规的手工建模几乎是难以完成的。如果采用Revit的概念体量创建网架，其网架球的大小和杆件的规格类型均相同，与工程项目实际不相符，难以保证网架模型的精度和质量。在网架的结构计算软件中，网架模型是自动生成的，同理也可以在Revit上采用二次开发的手段，编写自动创建网架的插件来实现。但是对于编程经验不足的设计人员来说，二次开发困难较大，因此探索其他相对易于掌握的方法，非常迫切。

在此情况下，本文研究探索了两个方案来解决Revit空间网架建模的问题。介绍了RevitExtensions插件基于Exce1生成模型的方法，重点阐述了采用Dynamo 程序实现网架自动建模的解决方案。希望本文介绍的BIM项目实践能为同行提供一些参考。

# 1Revit网架建模准备工作

Revit建模依赖于族构件，因此首先需要建立网架结构用的Revit网架族。网架结构由网架球、上弦杆、下弦杆和腹杆组成，网架的杆件有螺栓连接和焊接，为了方便使用，利用Revit强大的族功能，将杆件做成一个可以通用的族构件。经Revit族的构思，本文建立的网架球和网架杆件两种族即可满足网架构件的多样性。

# 1.1网架球

网架球族，Revit的构件类别为结构柱，使用的是结构柱的族样板，球中心锁定在底标高上，主要控制参数为球直径，如图1所示为网架球族模型。

![](images/2afa410a96835bdcbccc021c2a1a3d990b9a498539971250b99589601b33bdf5.jpg)  
图1网架球族  
图3Extensions工具

# 1.2 网架杆件

网架杆件族，Revit的构件类别为结构框架，使用的是结构框架的族样板。将杆件锥头、封闭和焊接三种连接节点情况整合成一个通用的族，通过参变可以变化成相应的网架杆件族。网架杆件族的主要控制参数为杆件直径、杆件壁厚、网架球的直径、杆端的连接形式等，如图2所示为网架杆件族及杆端的细部构造，与实际情况相符。

# 2基于RevitExtensions的解决方案

RevitExtensions 提供——基于Excel生成模型的工具，通过该工具可以读取网架的excel 数据自动生成网架模型。此处注意，该工具并非存在于所有的Revit版本，其中2013、2016版有此模块。

如图3所示，“基于Excel生成模型”，打开后见图5模型生成器的数据输入界面。该工具只能生成以下5种Revit图元：标高、结构柱、梁、墙、基础。因此按照Revit类别，本文将网架球定为结构柱类别，网架杆件定为结构框架类别(梁）。

E ExE 川 項  
修改删除 首选项 建模 分析 钢筋 钢结构连接节点 工具1 1构件 项目 Extensions椽框架  
属性 基于Excel生成模型三维视图 框架生成器

使用该工具创建网架主要需要解决的是，网架球节点和杆件的坐标数据处理。具体的解决思路：

（1）从网架计算软件中导出DAT文本的网架数据，如图4所示，该数据为MST(浙江大学空间结构计算软件)和AMDE（中国汽车工业工程有限公司网架结构计算软件）的DAT网架数据格式，这两款软件可以直接另存为DAT格式网架数据；该数据格式记录了网架球节点坐标、球直径、网架杆件两端的球节点编号、杆件规格等等。

![](images/b47d06d62238cab225ca26ce052200ef02871a0c5032231efb00edb910726500.jpg)  
图2网架杆件及杆端细部  
图4DAT文本格式的网架数据  
图5模型生成器中的网架数据

（2）处理DAT文本获取节点球和杆件的坐标、尺寸类型等数据；根据RevitExtensions模型生成器的Exce1数据格式，需要的是网架球和杆件的尺寸规格和坐标点，此数据从DAT文本中批量整理得到，此处不再赘述。

(3)将处理的数据输入到基于Excel的模型生成器中，如图5所示。

（4）校核数据；此为RevitExtensions模型生成器的功能，用于校核数据格式的正确性，避免模型生成过程中出错。（5）模型生成；（6）完成。

文件（F）编辑（E）格式（O）查看（V）帮助（H)  

<html><body><table><tr><td></td><td>The Data File of</td><td></td><td>MSTC AD</td><td></td><td>Ver</td><td>0.2003</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>3051234567891</td><td>121500000</td><td></td><td>30100</td><td></td><td></td><td></td><td></td><td></td><td></td><td>1</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>10°</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>00</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>02000200020002000２：</td><td></td><td></td><td></td><td>1.75</td><td></td><td>-2.5</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>2000200020002000２○</td><td></td><td></td><td></td><td></td><td>0</td><td></td><td>0</td><td></td></tr><tr><td></td><td></td><td>2600000</td><td>００１０００１０0０１０００１？</td><td></td><td></td><td></td><td></td><td></td><td></td><td>1.75</td><td>-2.5</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0</td><td></td><td>0</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>1.75</td><td>-2.5</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>：</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>1.75</td><td>-2.5</td><td></td></tr><tr><td></td><td></td><td>000000</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>175</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>2.5</td><td></td></tr><tr><td></td><td></td><td>00</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>1.75</td><td>-2.5</td><td></td></tr><tr><td></td><td></td><td>0</td><td></td><td></td><td></td><td></td><td></td><td></td><td>：</td><td></td><td>0。</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>202０００２０００２０００２０００２０</td><td>1 02468124680245802.</td><td>1.75</td><td></td><td>-2.5</td><td></td></tr><tr><td></td><td></td><td>0</td><td></td><td></td><td></td><td></td><td></td><td></td><td>0</td><td></td><td>0。</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>1.75</td><td>-2.5</td><td></td></tr><tr><td>1012315675</td><td></td><td>00</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>：</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

基于Excel的模型生成器-03Extensions网架数据表  
图 日 ? 文件· 编辑 数据[D]帮助R 校核数据  
日 J 1心 模型生成开始 插入 页面布局 公 数据 审阅 视图 福昕PDF  
L7 × √ fxA B C D E F G H 11 标高 坐标 偏移  
2 底部 族 类型 材料 X0 yo X1 y1 0 0  
3 m m m m m m  
4 标高1网架杆件D60\*3.5金属-钢Q2350.000 0.000 4.000 0.000 0.000 0.000  
5 标高1网架杆件D60\*3.5金属·钢Q235 0.000 0.000 0.000 3.500 0.000 0.000  
6 标高1网架杆件D76\*4 金属-钢Q235 0.000 0.000 2.000 1.750 0.000 2.5007 标高1网架杆件D76\*4 金属·钢Q235 2.000 1.750 6.000 1.750 2.500 2.5008 标高1网架杆件D60\*3.5金属-钢Q235 2.000 1.750 2.000 5.248 2.500 2.605  
9 标高1网架杆件D76\*4 金属·钢Q235 2.000 1.750 0.000 3.500 2.500 0.000  
10标高1网架杆件D60\*3.5金属-钢Q235 2.000 1.750 4.000 3.500 2.500 0.000

# 3基于Dynamo的可视化编程方案

# 3.1Dynamo网架建模思路

Dynamo是一款可视化编程软件，能独立运行或者运行于Revit上。通过基于节点的可视化编程界面，Dynamo可以极大地提升Revit的参数化设计能力，实现计算式设计模型或者其它自动化处理过程。Dynamo可以在BIM环境（Revit平台）中自动处理运算，并且与Revit进行实时的交互。同时最为重要的是，对于没有编程基础的设计人员来说，Dynamo相对容易上手掌握，可以让设计师灵活使用Revit的参数化设计，丰富BIM模型，极大提升模型的应用效率。

运用Dynamo 创建网架模型，主要需要解决三个技术难点：

（1)如何读取标准格式的DAT格式的网架数据；

(2）获取DAT数据转换为Dynamo中的坐标点;

（3）Dynamo中根据坐标点和三维线，如何生成网架球和网架杆件。

Dynamo网架建模的流程，如图6所示。

![](images/cd4038300f2206590f032db4fd4fb698a44ad496d31bde0e9b1e15148267c6fb.jpg)  
图6Dynamo 网架建模流程

# 3.2建模的主要Dynamo节点

Dynamo 中的每个命令块称为节点，每个节点自动运算实现数据的处理、运算、获取数据以及创建图元等各种功能。本文编写的Dynamo 网架建模程序需要用到的部分主要节点介绍如下：

（1）、FilePath。，允许用户选择本电脑上的文件以获得其文件名；此节点用于用户打开本机上的DAT网架数据文件，程序将读取该文件路径，并获取该文件名。

（2)、File.FromPath。，从路径创建文件对象；此节点读入【FilePath】节点的文件路径，并向下一节点输出文件对象。

(3)Excel.ReadFromFile $\cdot$ 从Excel表格中读取数据；此节点读入【File.FromPath】节点的Excel文件对象，同时需要输入该文件对象中“工作表名称”，并向下一节点输出Excel文件的数据。

（4)、List.GetItemAtIndex。，返回给定列表中的项；此节点读入上一节点的 Excel数据列表，输入要提取数据列表的项次，输出该项次的数据。

（5)、List.DropItems。删除列表中某些项；此节点用于删除数据列表中的多余项。

（6-）Point.ByCoordinates。，通过给定的3个笛卡尔坐标形成一个点；此节点输入X、Y、Z 三个坐标值，输出坐标点，此处坐标值为列表，输出的坐标点也相应为列表。

（7）、Line.ByStartPointEndPoint。，在输入的两点之间创建一条线；此节点输入起点和终点的坐标点，输出创建线段。

(8)、FamilyType.ByFamilyNameAndTypeName,根据族名称和类型名称选择族类型；此节点输入族名称和类型名称，向下一节点输出该族类型。

(9)StructuralFraming.ColumnByCurve,创建柱;此节点输入线、标高及柱族类型，输出创建结构柱模型，此处是生成了网架球。

(10)、StructuralFraming.BeamByCurve，创建梁。此节点输入线、标高及结构框架族类型，输出创建结构梁模型，此处是生成了网架杆件。

以上介绍详细用法请参见3.3节Dynamo 程序的运行，给出了网架杆件的创建过程。

# 3.3Dynamo程序的运行

Dynamo 程序的运行是将Dynamo 的各个节点连接在一起，形成的完整电池图即能实现相应的功能。上一节中节点1到6用于处理网架数据的坐标点，如图7和图8所示。节点7到10用于生成直线路径，并创建网架球和网架杆件，如图9所示为创建网架杆件的节点电池图。

![](images/24fd40c48a8aba42972f9d81a57c3f11ab353f8adb344b67b2faefad91aa07d8.jpg)

![](images/c163495d078a9f19c9a38c84c7646d5a7ba4dcbb2d525bddd058b7a83ea8613f.jpg)  
图7读取网架的原始坐标数据

![](images/6ad1366c0cc5d0e9ac849982e2eaeb7ae780acd4779f23cd334ee1a0a0a1dc7d.jpg)  
图8将3个坐标值形成坐标点

# 图9创建网架杆件

# 4工程实例

本工程为某汽车工业厂房，该项目为EPC总承包项目，业主对于该项目定位高要求严。从项目的方案阶段就使用了BIM技术，借助BIM的可视化在方案探讨交流中提高了方案评审的效率。在设计阶段创建了设计BIM模型，通过Dynamo 创建Revit 网架结构模型，提高了建模效率，网架尺寸和定位均与实际相符，提高了碰撞检查的精确度，同时辅助出图提高了图纸质量。

本项目为四角锥空间网架结构，网架平面尺寸为$3 2 \mathrm { m } \times 5 1 \mathrm { m }$ ，失高 $2 . 5 \mathrm { m }$ ，屋面设置 $3 \%$ 找坡。采用空间结构设计软件MST和AMDE分别进行计算，网架球数量300个，球类型4种，网架杆件数量1092个，杆件类型6种。如果采用常规的手工建模方式，将需要大量的时间且难以保证建模的准确性和模型的精度。通过Dynamo 编写的程序，能自动参数化建模，整个网架结构的创建过程不到5分钟即完成，而且网架球和杆件均与实际情况一致，不仅保证了模型质量，同时节约了大量的建模时间。完成后的网架模型如图10所示。

Revit 构件。

（4）本文的研究给出了Revit网架建模的解决方案和具体操作方法，经工程项目论证具有实际应用价值。

# 参考文献：

[1]欧特克软件（中国）有限公司构件开发组.《AutodeskRevitStructure2012运用宝典》[M].上海:同济大学出版社.2012.  
[2]欧特克软件（中国）有限公司构件开发组.《AutodeskRevit2013族达人速成》[M].上海：同济大学出版社.2013.  
[3]徐鹏,白玉星,高建岭.基于REVIT的网架自动化建模[J].《土木建筑工程信息技术》.2017,9(4):52-56.  
[4]吴生海,刘陕南,刘永晓,徐骋.基于Dynamo 可视化编程建模的BIM技术应用与分析[J].《工业建筑》.2018(2).  
[5]薛忠华,谢步瀛.Revit API在空间网格结构参数化建模中的应用[J]．《计算机辅助工程》.2013.22(1):58-63.  
[6]王国兴,蔡东明,许志宏,杨冰.市政工程箱形截面结构的Revit快速建模方法《市政技术》[J].2018(1):68-70.

![](images/dd9fb08792b5be10e8701e092fea66f81f9be146b2230a030933909ca4096823.jpg)  
图10网架模型

# 5总结

本文研究了运用RevitExtensions模型生成器和基于Dynamo可视化编程来创建Revit的网架结构模型，解决了Revit网架建模的难题。通过在某汽车工业厂房中的项目实践，验证了这两种方法的可行性，取得了良好的应用效果。得出以下结论：

（1）运用RevitExtensions模型生成器能创建网架模型，并且网架球和杆件与实际情况一致，但是由于该插件要求的数据格式与原始数据格式差别较大，因此需要处理数据。同时该插件运行的稳定性有待提高，容易崩溃。

（2）借助Dynamo可视化编程工具，能自动生成网架模型，网架尺寸与实际情况相符，且建模效率很高，提高了模型的精度和质量，减少了网架建模的时间。

（3）与二次开发相比，对没有编程经验的设计人员，Dynamo 相对容易掌握，能解决复杂形体和复杂功能的参数化设计，参数化几何形体可直接转换成