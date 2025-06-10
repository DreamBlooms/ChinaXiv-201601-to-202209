# 基于Revit二次开发的PC建筑预制率计算方法研究

陈远 康虹

(郑州大学 土木工程学院，郑州 450001)

摘要：为改进目前预制装配式建筑预制率手工计算存在效率低下、误差加大的问题，本研究利用建筑信息模型 BIM 技术，通过对 Revit 软件的二次开发，实现了对基于BIM模型的预制装配式混凝土建筑(Precast Concrete，简称 PC)预制构件工程量的自动统计和预制率的自动计算，验证了基于Revit平台计算PC建筑预制率的可行性。利用本文的二次开发成果，通过不同构件预制率的动态选择组合，可以估算建设成本，进而选择成本可接受范围内的预制方案，增加经济效益，为决策者制定预制方案提供决策依据。

关键词：装配式建筑，；BIM,；预制率，；Revit二次开发中图分类号：TU-201；TU17 文献标志码：A

# The Calculation Method for PC Building Prefabrication Rate Based on Revit Redevelopment

Chen Yuan, Kang Hong (Zhengzhou University, School of Civil Engineering, Zhengzhou 450o01, China ）

Abstract:Inordertoimprove thecurrnt prefabricated building prefabricationrate manualcalculation,thereare problemsof ineficiencyand increased error,thisstudyusesBIMtechnology,throughtheRevit redevelopment,toachievetheBIMmodel based prefabricated concreteconstruction (Precast Concrete,PC)prefabricated componentsof theamountofautomatic statistics andthecalculationofprefabricatedrate，andverifies thefeasibilityofcalculating PCbuilding prefabricationratebasedonRevit platform.Byusing theredevelopmentresultsofthis paper,wecan estimate theconstructioncosthrough the dynamic selection combinationofdiferentcomponents,ndthenchoosetheprefabricatioschemewitintheacceptablerangeofthecosttoincrease the economic benefit and provide the decision basis.

Keywords:Prefabricated Construction,BIM,Prefabrication Rate,Revit Redevelopment

# 0-引言

个环节部件的协调，BIM平台能有效提高装配式建筑在设计，制作，安装等方面的效率3，促进装配式建筑的发展。

装配式建筑将工地作业为主的建造方式改变为工厂制造为主。与传统建筑工艺相比，装配式建筑能缩短工期，提升建筑质量，节约资源，保护环境，实现建筑业的可持续发展[1]。2016年9月《国务院办公厅关于大力发展装配式建筑的指导意见》明确要求，推动建造创新，落实绿色发展理念，大力发展装配式混凝土建筑和钢结构建筑，不断提高装配式建筑在新建建筑中的比例。

目前，装配式建筑与BIM技术结合应用还处于探索研究阶段。基于BIM技术解决装配式混凝土建筑建设的维护管理问题，可以有效减少施工过程的返工[4]。参考计算机集成制造系统，基于BIM的装配式建筑集成建造系统框架理论的提出对提高装配式建筑信息化，提高构件生产率方面具有重要意义[]。3D激光扫描技术和BIM技术结合，能实现自动检查预制构件的尺寸质量[5]。应用BIM软件建立预制梁柱的连接节点，可以设计符合规范要求的预制抗震框架模型，从而建立PC构件结构系统库[6]。

BIM(Building Information Modeling 建筑信息模型)是以工程项目各阶段数据信息为基础建立的建筑模型，能真实集成反应项目中有关信息。其具有可视化，协同性等特点[2。装配式建筑的强调各基于BIM平台对装配式建筑协同设计减少设计师重复工作，提高工作效率[7]。

综上所述，结合BIM技术实现预制构件工程量的自动统计和预制率的自动计算问题还有待研究，而预制率是衡量装配式建筑重要指标，因此研究自动提取构件工程量，计算预制率十分有必要。

# 1预制率计算问题分析

预制率是衡量装配式建筑的重要指标之一，也是政府制定装配式建筑扶持政策的主要依据指标。同时预制率的高低也直接影响工程成本，通过对不同预制装配率工程成本量化分析，预制装配式建筑的经济预制率在 $4 6 \% - 6 5 \%$ 之间[8。因此，预制率是装配式建筑实施时首先要考虑的指标。

然而，在预制率计算方面还存在一些问题。传统计算方法根据图纸尺寸手工计算预制构件混凝土量。计算过程复杂，计算效率低下，计算结果不准确。建筑信息模型BIM技术的出现为解决装配式建筑预制率的自动计算提供了强大的技术支持。但是仅仅建立装配式建筑的BIM模型，利用建模软件的自身功能，还很难实现工程量的自动统计和预制率的自动计算。Revit作为主流的BIM建模软件之一，其内部包含功能丰富的API(ApplicationProgrammingInterface应用程序接口），通过对Revit的二次开发，Revit使用者可以根据需要进行功能拓展，满足不同的设计和施工需求。因此，利用Revit平台的二次开发功能，解决基于BIM模型的预制装配式混凝土建筑预制构件工程量的自动统计和预制率的自动计算，是本文研究的重点。

本文通过BIM建模软件——Revit建立装配式建筑BIM模型，基于Revit二次开发，研究利用模型里的信息，统计各类预制构件的工程量，从而设定计算规则，计算项目中各类构件预制率，解决手工计算复杂，效率低，结果不准确的问题，实现准确快速计算的目的。通过不同构件预制率的动态选择组合，可以估算建设成本，进而选择成本可接受增幅范围内的预制方案，增加经济效益。

# 2开发思路和步骤

# 2.1开发工具及步骤

此次开发是基于Revit2016版本，主要开发工具有Visual Studio 2015，Revit SDK（SoftwareDevelopmentKit 软件开发工具包),RevitLookup等。其中采用VisualStudio2015开发环境来编写程序代码，RevitSDK里包含RevitAPI帮助文档以及一些源代码的实例，RevitLookup用来直观看到模型中构件的API。具体开发步骤如图1所示。

![](images/15776182c641c45cdb04542cbcae7fbc9109fdd288ce20abea1730450557f86a.jpg)  
图1：程序开发流程

# 2.2开发模式

Revit二次开发有两种开发模式，一种是通过外部命令（IExternalCommand)，另一种是外部应用（IExternal Application)。IExternal Command是用户扩展Revit时必须在外部命令中实现的接口，这个接口只有一个抽象函数Excute()，通过重载这个函数来实现外部命令[9]。IExternal Application接口有OnStartup和OnShutdown两个抽象函数，它们是在Revit启动和关闭时候定制所需要的功能。这两种模式在开发前首先要引用RevitAPI.DLL和

RevitAPIUI.DLL两个接口装配文件。本文采用添加外部命令的方式，编写好程序生成DLL文件，通过AddInMangaer加载DLL文件运行程序。

# 3基于Revit二次开发的PC建筑预制率计算方法

# 3.1参数设计

本文采用的计算规则是根据国标中的计算方法[0]，基于Revit二次开发，快速准确获取混凝土体积，用室外地坪以上预制构件混凝土体积除以混凝土总体积计算得出预制率。

根据预制率的计算规则，要计算预制率需要获得两个主要参数，一个是预制混凝土体积，另一个是现浇混凝土体积。其中，预制混凝土体积通过过滤规则获取构件模型的内置体积参数得到。现浇混凝土体积除了通过项目中的构件模型得到，还有一部分通过比例得出。对于预制叠合楼板，其厚度一般为 $6 0 \mathrm { { m m } . }$ ，现浇部分为70mm厚，因此楼板的现浇体积为预制叠合楼板体积乘以系数7/6.

# 3.2获取参数

为了查看各类构件的预制体积和预制率，预制混凝土体积应分构件类型分别获取。在RevitAPI中，有两种方式访问对象。对于系统族，如 $\mathbb { W } \mathrm { a l 1 }$ Floor,、Opening等，通过过滤其类名可以获得对象。对于柱子，梁等构件，没有专门的类来表示，他们都是FamilyInatance的实例，可以通过内置参数过滤。在Revit中系统族不能自建族，因而本项目预制墙，预制楼板，洞口等都是通过新建常规模型来建立的，他们也属于FamilyInstance，通过过滤其内置参数获取对象。创建预制构件必须满足一定的命名规则，这样才能设置过滤规则访问对应的构件参数。根据国家建筑标准设计图集15J939-1中的示例四，总结出一套预制构件命名规则，见表1.。

表1_：预制构件建模规则  

<html><body><table><tr><td>构件</td><td>命名</td><td>颜色（RGB）</td><td></td></tr><tr><td>预制外墙板</td><td>预制_YWQ_XX</td><td>220.20.60 □</td><td>t</td></tr><tr><td>预制内墙板</td><td>预制_YNQ_XX</td><td>0,250,154</td><td></td></tr><tr><td>预制楼板</td><td>预制_YDBS_XX</td><td>147,112,219</td><td>t</td></tr><tr><td>预制空调板</td><td>预制_KTB_XX</td><td>190.143.21</td><td>t</td></tr><tr><td>预制阳台板</td><td>预制_YTB_XX</td><td>251.140.0</td><td>t</td></tr><tr><td>预制楼梯</td><td>预制_YLT_XX</td><td>139.69.19 □</td><td>t</td></tr><tr><td>现浇构件</td><td>现浇_xx</td><td>65,105.225 2</td><td>t</td></tr></table></body></html>

(1)预制混凝土体积获取

预制构件有预制外墙，预制内墙，预制楼板，预制阳台板，预制空调板等，这些构件均通过新建常规模型这个族样板文件来建立。获取这些预制构件体积的过程如下：

1）创建收集器，访问项目中所有对象，收集器创建首先声明实例化FilteredElementCollector这个类。调用快捷函数OfClass（快速过滤出项目中的族类别。通过调用名称属性判断，过滤出所有预制构件，接着根据各预制构件名称的不同，通过LIMQ语句过滤各类构件。如图2所示，是获取预制外墙的具体方法。

Documentdoc $\mathbf { \sigma } = \mathbf { \sigma }$ cmdDataForm.Application.ActiveUlDocument.Document;   
//过滤所有名称包含预制的族类型   
FilteredElementCollectorcollector1=newFilteredElementCollector(doc);   
collector1.OfClass(typeof(FamilySymbol));   
List<string> pcName= new List<string>(0;   
foreach (Elementel incollector1) if(el.Name.Contains(预制")) L string name=el.Name; pcName.Add(name); 】   
1   
//过滤出族实例   
FilteredElementCollector collector2 $\mathbf { \sigma } = \mathbf { \sigma }$ newFilteredElementCollector(doc);   
collector2.OfClass(typeof(Familylnstance));   
foreach(string pcname in pcName)   
T var pc1= from element in collector2 whereelement.Name.Equals(pcname) select element;

2）预制构件的体积通过获取实例的内置参数获取。这样需要注意的是，Revit软件后台操作的单位是英尺，因此体积参数的值因乘以 $3 0 4 . 8 ^ { 3 }$ 转换为

# ChinaXiv合作期刊

立方米。代码如图3所示。

![](images/3575862476a88129346c145c6b90d60c393aec6359ec14aef7ad6b899b1ada59.jpg)  
图3计算构件体积的方法  
图4PC建筑预制率分析软件界面

3）获取构件体积后，通过调用属性获取每个构件的名称，数量等。最后这些数据信息设置为dataGridView这个控件的数据源，显示在列表里。

(2)现浇混凝土构件体积获取

现浇构件包括墙体，预制叠合板上的现浇部分，梁，楼梯休息平台楼板的现浇部分，节点处的现浇。墙体，梁，楼板，节点处的现浇体积采用和上述相似过程，得出构件的体积。预制叠合板上部的现浇体积是预制叠合板体积乘以对应的比例系数获得。

# (3)计算各类构件预制率

各类构件的预制率为该类的预制体积除以预制构件体积和现浇构件体积之和，总预制率为选择采取预制的构件预制率之和。

# 3.3界面交互

创建窗体，将各类构件的名称，体积等信息在窗体中显示。前面提到，Excute（函数有三个参数的重载，创建窗体执行Revit命令，必须要先传递这三个参数。首先，在Excute()函数中声明并实例化窗体，设置窗体显示，然后，在Forml中生成构造函数即可。窗体的设计中，用到Button,Label,CheckBox等多种控件，需要在每个控件的事件里编写代码实现软件功能。软件界面如图4所示。

al1 预制外墙预制内 预制楼板预制梯 预象阳台板预制空调板预制女儿墙 预制率上限  
PC建筑预制率分析软件 预制构件名称 体积(a3) 构件重量（t） 数量（个） 总体积（a3） >.1 制C1-629-1814（Y5） 2.22 5.55 1 2.22 构件 预制体积（m3） 预制率（%)2 预制-24294 1.2 3.30 2 2.64  
： 2017年9月 ， 3 制-21296） 1.15 2.09 2 2.31 □预制外墙  
1 18 28 2.8 □预制内墙7 1 \~ 3 □预制楼板8 HT7 3.45 8.63 2 6.90 □预制楼梯今天：2017/9/17 18 4 38 □预制阳台板1600 28 8 “ 54 □预制空调板13制T34100 1.80 4.51 2 3.61 □预制女儿墙14制T24100 2.26 5.64 2 4.5215H11 1.18 2.96 1 1.1816TQ29 1.34 3.96 2 2.69 选中构件预制体积17制LT3 1.84 4.6 2 3.6818制T30 3.09 7.72 2 6.17 选中构件预制率1913 1400 1.00 3.24 2 2.020制30 1.48 3.0 1 1.48 现浇构件总体积21T93900 1.44 3.60 2 2.0022制Q-42299） 4.27 10.67 2 8.6323-302（11）1 2.54 6.34 2 5.0724制 0.28 0.69 2 0.5525 0.26 0.64 2 0.5126预制 0.63 1.67 2 |1.25

# 4验证实例

本项目采用国家建筑标准设计图集15J939-1中的示例四，根据上述建模规则和示例四的构件详图，分别建立各类构件的BIM模型。然后将构件的模型组装成示例四标准层BIM模型，见图5。运行Revit软件，通过外部工具中的AddInMangaer加载插件的DLL文件，即可运行此预制率计算软件。如图6所示，点击不同的选项卡，可以分开显示各类预制构件的工程量清单。右边可以动态计算预制率，通过勾选不同的构件，实现自动计算出该类构件的预制体积和预制率，并且下面动态显示已勾选构件的预制体积和预制率。通过对不同构件预制率的组合，可以选择最佳的预制方案，增加经济效益。

示例四项目地上21层，五层及以上为装配式混凝土剪力墙结构，五层以下是现浇混凝土剪力墙结构。从两个方面对插件的可靠性进行验证，一是对单个预制构件的预制体积验证，二是建立了标准层BIM模型，通过此预制率计算插件计算示例四标准层预制率，与标准图集预制率结果对比，从而验证此插件计算的准确性。选取叠合板YDBS_01,规格参数为 $3 7 5 0 { * } 3 1 3 0 { * } 6 0$ (长\*宽\*厚,单位：mm)，其体积为 $0 . 7 \mathrm { m } ^ { 3 }$ ，其上部现浇体积应为 $0 . 8 2 \mathrm { m } ^ { 3 }$ 。在Revit中将此叠合板隔离，通过插件单独计算此构件的体积，结果与手算一致。当标准层中的外墙、内墙、楼板、楼梯均采取预制方式时，通过插件计算得出标准层预制率为 $6 0 . 8 4 \%$ ，如图6所示。标准图集中给出，此项目标准层预制率为 $6 0 . 8 1 \%$ ，两者相差 $1 \%$ 误差在可接受范围内，故此插件计算准确。本示例四项目案例采用预制外墙、预制内墙叠合板和预制楼梯组合的方式，预制率较高。根据文献的研究，在不考虑工期效益的情况下，采用这种组合方式，工程造价提升270元/m左右，而成本偏高是抑制装配式建筑发展的直接因素。在此插件中选择组合，采用预制外墙、叠合板和预制楼梯的的组合方式，直接计算出预制率为 $4 5 . 0 7 \%$ ，并且内墙采用轻质隔墙板，可以有效地减少建造成本。

![](images/ab4634b0f8570c22042b2dd4e8ab241b2d029c695c152af4d0507ccd6129feb2.jpg)  
图5示例四标准层BIM模型

15J939-1中的示例四为例，建立构件BIM模型，进而组装项目标准层BIM模型，结合Revit的二次开发技术，开发出一款预制装配式建筑预制率分析软件，实现快速统计项目各类预制构件体积，计算预制率的功能，提高工作效率，动态显示预制不同构件对应的预制率，进而为确定预制方案提供决策依据。

# 参考文献

![](images/a8d06bfb5c3d055d2c197b6cf0eaea3ae57c682b6c1c6831876defa0abf0a7cd.jpg)  
图6导出Excel预制构件清单工程量

[1]于龙飞，张家春．基于BIM的装配式建筑集成建 造系统[J]土木工程与管理学报， 2015(04):73-78.   
[2] Azhar S.Building Information Modeling (BIM): Trends,Benefits，Risks,and Challenges for the AEC Industry[J]. Leadership and Management in Engineering,2011,11(3):241-252.   
[3]白庶.BIM技术在装配式建筑中的应用价值分析 [J]．建筑经济,2015:106-109.   
[4] Ismail Z. Improving conventional method on precast concrete building maintenance:Towards BIM implementation[J]. Industrial Management & Data Systems,2017:1485-1502.   
[5] Kim M K, Wang Q, Park J W, et al. Automated dimensional quality assurance of full-scale precast concrete elements using laser scanning and BIM[J]. Automation in Construction,2016:102-114.   
[6] Guan D,Guo Z, Zhang C. Research on Precast ConcreteStructureswith BIMInvolving Information on Structural Details and Behaviors[J]. Engineering Village, 2015:222-228.   
[7]Li K. The application of BIM technology in prefabricatedassemblyconcretestructure design[J]. Engineering Village,2017:472-476.   
[8]李丽红．装配整体式建筑经济装配率的核算[J]. 建筑经济,2015:91-94.   
[9] 钱海，马小军，来侃．基于Revit二次开发的电气 设备族平台的搭建[J]．土木建筑工程信息技术, 2015，7(04):60-64.   
10] 田炜，朱海，刘智龙．建筑单体工业化程度评价 标准新计算方式研究[J]中外建筑， 2016(07):130-132.

# 5总结与展望

Revit是主要的BIM应用软件之一，但目前应用水平多停留在建模应用。基于Revit软件，通过API对其进行所需功能的开发，有助于发掘BIM技术更深层次的应用。本文以国家建筑标准设计图集