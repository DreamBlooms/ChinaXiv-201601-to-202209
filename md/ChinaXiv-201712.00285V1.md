# 基于REVIT 的网架自动化建模

# 徐鹏 白玉星 高建岭

（北方工业大学，北京 100044)

【摘要】现阶段Revit网架建模存在很多弊端。常规建模方法由于杆件数量过多导致建模工作量繁重,难以检查修改。应用体量模型建模速度虽快但整体模型不够准确,构件参数不能单独设置。为了提高设计效率、提升建模精度,本文采用 Microsoft 公司的visual studio2015开发平台,对Revit进行二次开发，编写网架自动化建模程序。本程序通过读取LOG文本加载焊接空心球节点族和杆件族,快速、方便、准确地生成Revit 焊接空心球网架模型,适用于非曲面标准网架。生成的网架可以按照LOG文本更换对应构件的种类,网架整体尺寸与实际情况相符,极大的较少了设计工作人员的工作量，提高了设计效率和建模质量。

【关键词】Revit;二次开发；网架结构；自动化建模【中图分类号】TU17；TU356；TU391 【文献标识码】A【DOI】10.16670/j.cnki.cn11-5823/tu.2017.04.10

BIM的概念在建筑领域逐渐被更多的人认可，尤其被明确写入住建部“一三五”规划后，BIM的发展趋势更加迅速。Autodesk公司的Revit不仅自身拥有强大的功能，还为使用者提供了丰富的API,逐渐成为世界上主流的BIM平台。早在2005年公司就开始提供API接口，在不断更新的十多年里,Re-vitAPI得到了快速的发展，其功能也越来越强大。借助于API我们可以把琐碎的建模工作自动化，让+人员有更多的精力投身于方案修改的工作中[1] O

# 1 工程概况

某钢结构体育馆总建筑面积1.3万 $\mathbf { m } ^ { 2 }$ ,檐高$2 3 . 5 \mathrm { m }$ 。地下两层，地下一层为标准游泳池，地下二层为设备用房。地上采用双层大空间结构，层间设有夹层。屋架为正方四角锥焊接球空间网架，上弦周边支撑。网架轴线平面尺寸为 $6 0 \mathrm { m } \times 3 1 . 7 \mathrm { m }$ ，高度为 $2 . 6 \mathrm { m }$ ,屋面设置 $6 \%$ 找坡方便排水。经空间结构设计软件MSTCAD计算，网架杆件数1360个，杆件类型7种，焊接球368个，焊接球类型2种，网架在MSTCAD中显示的空间三维模型如图1所示。

【文章编号】1674-7461(2017)04-0052-05

![](images/887702941f87e4d3eb5add32775ea690eaf8a0eaed98d704ea3da5f6db1d42d2.jpg)  
图1空间网架在MSTCAD中的三维图

# 2 REVIT网架模型创建方式及存在的问题

# 2.1通过盈建科接口软件导入Revit

空间网架在MSTCAD中计算完成后，设计人员可以直接通过软件导出为ANSYS文件、SAP2000文件和命令行数据格式的LOG文本，也可以通过盈建科软件作为中转平台读取LOG文本实现网架分析模型到其他分析软件的互通。盈建科软件还自带了Revit接口补丁，可以实现分析模型到REVIT模型的转换,但是转换过程会产生一些错误。本案例通过盈建科软件读取MSTCAD导出的LOG文本生成分析模型，再通过接口软件导入到Revit中。生成的Revit网架不仅没有球节点，杆件也会发生轴线偏移错位的问题，如图2所示。导出生成的Revit网架模型并不能直接使用，需要设计人员花费大量时间进行修改。

只有杆件模型，没有节点模型

# 2.2 通过创建概念体量方式建立网架

创建网架概念体量模型并对其进行划分网格，幕墙嵌板填充图案的形式创建杆件和球节点[2]这种建模方式比较简洁，快速。但是缺点显而易见：首先多个杆件和球节点组成一个网格的幕墙嵌板图案，如图3所示。快速填充幕墙嵌板的图案建立的网架模型,节点和杆件的尺寸参数是统一的，都从属于幕墙嵌板填充图案族。这种建模方式并不能单独设置每个杆件和球节点的参数。

其次，由于幕墙嵌板图案只有上部4个自适应点，而下部的下弦节点与上弦面的高度是定值，并不能自动调整。本案例中的正方四角锥上弦平面有 $6 \%$ 找坡，采用此方法建模将造成下弦平面同样起坡。创建的网架模型与实际情况差异较大。

# 2.3常规方式建立网架

直接创建杆件族和球节点族，通过导入CAD文件帮助节点定位,采用常规方式创建网架模型[3]这种建模方式比较准确，可以正确表达网架模型的实际大小和构件的尺寸。但是这种建模方式也存在缺点：整个网架的建模工作需要连接7种截面杆件共1360个，放置2种直径球节点共368个，建模工作量巨大，工作繁琐，易出错。如果产生设计变更，构件尺寸的修改将变的更加困难，且难以检查到产生的错误。

综上所述，无论导入还是直接创建，网架在建模过程中都会耗费设计者大量的精力，加重设计工作量。

# 3基于REVIT的二次开发

# 3.1 REVIT二次开发工具及准备工作

（1）本文采用较为普及的REVIT2014版本、NETFramework 4.5、Microsoft visual studio2O15 编程环境及C#编程语言，并添加RevitAPI.dll和Revi-tAPIUI.dII两个动态链接库的引用。

![](images/505ed1d868782255242d93b1c735e0420b74a6ec9abc7034cbb41bcbc34460d1.jpg)  
图2通过盈建科导入到Revit生成的网架模型  
图3幕墙嵌板填充图案族

(2)网架模型经MSTCAD计算后导出为命令行数据格式，生成名为\*.log的文本。在输出文件时，需选择输出数据的坐标系格式为右手坐标系并框选输出常规信息和球节点信息。

(3)创建焊接球族和端点为两个自适应点的杆件族，并按照MSTCAD杆件材料库和节点规格所给出的参数设置相应的族类型。由于加载族类型需要读取到LOG文本中的字符，所以族类型命名必须严格按照LOG文本给出的名称进行命名。

# 3.2 二次开发的流程及步骤

程序开发的流程如图4所示。

![](images/782bd5f9f1f53a66e68d81608d2aff11cbf2e55a0158388aab5e01f25522e687.jpg)  
图4程序开发流程

程序运行步骤：

（1)读取MSTCAD计算结果导出的LOG文本，  
及已经创建的Revit族文件。(2)按照文本给出的绝对坐标创建点，并在点  
上加载对应族类型的焊接球族，再通过以下代码创  
建焊接球节点族实例：public void PutBall(Document RevitDoc )3

foreach(var it in Points)

(new XYZ（it. Value.X,it. Value. Y,it. Value. Z）,  
it.Value. Symbol,StructuralType. NonStructural）as El-  
ement ;$\begin{array} { l } { { \mathrm { d i c I d } } [ \mathrm { i t . \ K e y } ] = \mathrm { e . \ I d } ; } \\ { ~ \nmid } \\ { ~ \nmid } \end{array}$ (3)设置提示信息，“焊接球放置完毕,开始放  
置杆件”,缩放视角便于观察。(4)按照LOG 文本配置杆件族类型,获取杆件  
两端自适应点,建立杆件族实例。（5)由于杆件两端自适应点获取的是焊接球球  
心点,需按实际情况对杆件进行剪切,核心代码  
如下：//剪切球杆链接if（ dicId.ContainsKey（ idStart） &&di-  
cId. ContainsKey(idEnd）)ElementId eIdStart $\mathbf { \tau } = \mathrm { d i c I d } \left[ \mathrm { i d S t a r t } \right]$ ：ElementId eIdEnd $\mathbf { \Sigma } = \mathbf { \Sigma }$ dicId[idEnd];Element eBall1 $\mathbf { \tau } = \mathbf { \tau }$ RevitDoc.GetElement（ eI-  
dStart）；Element eBall2 $\mathbf { \tau } = \mathbf { \tau }$ RevitDoc.GetElement（ eI-  
dEnd);if（eBall1！ $\mathbf { \Sigma } = \mathbf { \Sigma }$ null && eBall2！ $\mathbf { \Sigma } = \mathbf { \Sigma }$ null)JoinGeometryUtils.JoinGeometry（RevitDoc,  
eBall1,famIns1）;JoinGeometryUtils.JoinGeometry（RevitDoc,  
eBall2,famIns1） ;//杆一端和球剪切if （JoinGeometryUtils. AreElementsJoined（Revit-  
Doc ,famIns1,eBall1）)InstanceVoidCutUtils.AddInstanceVoidCut(Revit-  
Doc,famIns1,eBall1） ;//杆另一端和球剪切if （JoinGeometryUtils. AreElementsJoined（Revit-  
Doc ,famIns1,eBall2）)

InstanceVoidCutUtils.AddInstanceVoidCut(RevitDoc,famIns1,eBall2）;

对杆件和球的剪切，需要先将杆件和球进行连接后才能剪切，焊接空心球族需采用实心球并空心剪切的方式创建，保证球和杆剪切后空心球节点内部没有杆件残留。杆件和空心球节点剪切效果前后对比，如图5所示。

![](images/f02888b75b83f53538e2c1a24704565f5f31c3df8bb2f1f82bda8083819a9550.jpg)  
图5杆件剪切效果对比

）意，使用用点大，50个后续工作,直至网架模型生成完毕,网架整体模1如图6所示。

网架整体上弦面正确起坡,下弦面仍为平面，整体模型和实际相符。将视角放大，可以看到模型按LOG文本匹配了对应族类型的族实例，如图7

所示。

![](images/a8284557f401ddf5e91213fb0269d809779115ccf8c0e2d807e7c72b0db7016a.jpg)  
图6网架整体模型三维图

![](images/00dbad75f582639a84388c5e271883332e11e26fcaa4d8dc478725b54d7b135d.jpg)  
图7网架放大三维图

生成网架模型的网格距离与分析模型在MST-CAD中的距离一致，如图8所示。

本程序通过“附加模块”命令加载,程序自动按照读取的LOG文本生成Revit网架模型。该模型无论整体形状、节点位置、构件连接关系和构件尺寸参数严格按照LOG文本给出的数据生成。由于LOG文本是通过软件导出得到，设计人员只需按照规范在MST中进行设计，保证计算结果的准确，即可生成正确、精准的网架模型。

![](images/514174198618aef9247560b2355ec30b7a678dc3bcf157c32ebcfc153f8dfc3b.jpg)  
图8模型网格间距

# 4结束语

本文通过某工程实例，指出现阶段三种创建网架方法中存在的问题。通过Revit二次开发编写网架自动建模程序，快速、准确地生成Revit网架模型，减少了大量的建模工作量。程序也可生成只有杆件和球节点组合的螺栓球网架,适应于各种非曲面标准网架。应用本程序设计人员需将MSTCAD8 结果导出为log文本,参照软件材料库创建对应的Revit族并参照log文本对族类型正确命名，启动程序前输入读取以上文件的位置，然后启动Revit不需要任何其他操作一键生成Revit网架模型。后期网架结构调整，设计人员只需对MSTCAD中的分析模型进行修改，重新导出log本文生成Revit网架模型。本案例网架1360 个杆件，368 个球节点重新生成修改后的网架模型只需几分钟，加快了设计效率，提升了设计质量。模型完成后设计人员只需将模型单独保存为网架结构模型，再通过链接方式与其他Revit模型进行协同设计。

后续的开发工作可以围绕以下几个方面进行：

(1)采用建立轴线方式放置杆件，生成曲面网架模型;(2)通过提取球节点半径，用算法推算出套筒，锥头等零件的定位坐标，加载log本文的族类型，生成具有高精度完整零件模型的螺栓球网架。

现阶段REVIT重复性建模工作或高精度建模工作需要耗费设计人员大量的时间,对Revit进行二次开发自动化建模将是未来Revit建模方式的主流。

# 参考文献

[1］AutodeskAsiaPteLtd.AutodeskRevit二次开发基础教程[M].同济大学出版社，2015.  
［2］缪纯乐.Revit自适应构件功能在形体和表皮建模方法上的研究[D].南京大学，2012.  
［3］王胜男.网架结构优化设计与BIM施工模拟［D].大连理工大学，2016.  
[4］罗尧治.MST2016 说明书.www.mstcenter.com.  
［5］JGJ7-1991，网架结构设计与施工规程［S].

# Automatic Modeling of Space Truss based on Revit

Xu Peng，Bai Yuxing，Gao Jianling (North China University of Technology，Beijing 1OO144，China)

Abstract：There are many drawbacks inthe present modeling of the grid structure in Revit.Due to the excessive numberofcomponents,theconventional modeling is heavyin workloadand diffcult in to check theerrors and to modify them.Applying the volume modeling can be in speed,but the overallmodel is not accurate enough，and thecomponent parameters cannotbe setseparately.In order to improve thedesign efficiencyand the modeling accuracy,this paper uses Microsoft’s visual studio 2015 development platform for a secondary development of Revit to prepare agrid automation modeling program.This program can generate the Revit model of the welded spherical joints grid quickly,easilyandaccurately,through reading theLOG textto load the welded hollow sphere joint family andthe member family.This program is suitable for the non-curved standard gridof welded spherical joints.The generated grid structure can be modified by the size of the corresponding components according to the LOG text. The overallsizeof the grid structure is inaccordance with the actual situation，which greatly reduces the workload of the design staff.

Key Words:Revit； Secondary Development；Grid Structure ；Automatic Modeling