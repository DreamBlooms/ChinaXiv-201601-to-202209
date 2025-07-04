# 工程管理专业BIM虚拟仿真实训平台构建研究

余宏亮1² 刘玲」许媛媛

（1.武汉科技大学管理学院，武汉 430081；2.华中科技大学BIM工程中心，武汉 430074）

摘要：推行实践教学改革，提升学生的工程实践能力和专业综合素质是全面落实国家中长期教育改革的重要举措，是培养复合型、应用型、创新创业人才的重要手段。但是，目前实践教学存在深度不够，关联性不强等问题。普遍采用的去建筑企业或工程项目现场实习、实践教学方式，又存在安全隐患且受时间和空间的限制。本文首先总结了BIM在国内外教育领域中的应用现状，然后提出BIM虚拟仿真实训平台的构建目标，设计了总体系统结构图，将平台分为建筑结构设计实训子平台、施工虚拟仿真实训子平台、BIM工程造价实训子平台、BIM一体化项目管理实训子平台等，最后给出了实训平台的云架构原理，列举了主要的软硬件构成，以供同行建立类似实训平台参考。

关键词：BIM；实训平台；工程管理；虚拟仿真中图分类号：G642.0；TU-4;TP391.9 文献标识码：A 文章编号：

# 1引言

建筑业是我国国民经济的支柱产业，对土木和工程管理人才需求旺盛。工程管理又是一门综合性、实践性很强的学科，截至 2017年，我国开设工程管理专业的高等学校超过400家。《高等院校工程管理本科指导性专业规范》对工程管理专业学生的素质结构、能力结构、知识结构提出了较高的要求，参照规范要求，教学中按照4个知识体系、5个知识领域开设了十几门专业基础课和专业方向课。但对于实践经验欠缺的工程管理学生，虽然通过课堂教学能习得若干知识点，但较难形成专业知识体系。因此，实践教学在本专业中具有举足轻重的地位。

推行实践教学改革，提升学生的工程实践能力和专业综合素质是全面落实《国家中长期教育改革和发展规划纲要（2010-2020年）的重要举措，是培养复合型、应用型、创新创业人才的重要手段。但是，目前实践教学存在深度不够，关联性不强等问题。普遍采用的去建筑企业或工程项目现场实习、实践教学方式，又存在安全隐患且受时间和空间的限制。2013年，教育部根据《教育信息化十年发展规划（2011-2020 年）》，决定开展国家级虚拟仿真实验教学中心建设工作[1]。其目的是鼓励高校采用多媒体虚拟现实技术和数值计算仿真技术，构建高度仿真的虚拟实验环境和实验对象，并进行教学方法、实验手段等方面的改革研究与实践探索，使实践训练及时跟上相关技术的发展[2]。

BIM(Building Information Modeling)是一种创新的建筑设计、施工和管理方法。基于共享的信息模型，在工程项目决策、设计、建造、运营、维护全寿命周期，实现各参与方协同管理，消除信息断层。如何利用 BIM虚拟仿真实训平台，培养学生的分析、研究、解决工程管理实际问题的综合专业能力将具有一定的理论价值和重要的实践意义。本文首先总结了BIM在国内外教育领域中的应用现状，然后提出BIM虚拟仿真实训平台的构建目标和具体建设内容，最后绘制了平台的云架构示意图，并列举了主要的软硬件构成，以供同行建立类似平台参考。

# 2BIM在工程管理专业教学中的应用现状

# 2.1BIM在国外教育领域的应用现状

收稿日期：  
作者简介：余宏亮(1970-)，男，高级工程师，博士，研究方向为工程管理。  
基金项目：武汉科技大学教研项目“基于 BIM的工程管理专业人才培养模式创新研究"(编号：2015Z020)

BIM 是近年来建筑业发展最有前途的技术之一。BIM在美国建筑业中的应用率也从2007年的 $28 \%$ 达到2012年的 $7 1 \% ^ { [ 3 ] }$ 。为适应美国建筑行业对BIM人才的需求，美国已有多所高校将BIM技术融入教学改革，在建筑类或工程管理专业BIM课程设置模式主要有：单一课程模式、交互教学模式、多课程联合模式、毕业设计模式，涵盖了建筑设计类课程、结构设计类课程、特殊专业课程、工程管理类课程[4]。

英国政府要求自2016年起所有公共建筑项目必须采用BIM设计过程。为了满足建筑行业对BIM人才的需求，威斯敏斯特大学、西英格兰大学、南威尔士大学等高等院校都开设了相关BIM课程[5]。

澳大利亚一些技术和继续教育（Technical and Further Education）机构提供 BIM类课程，这些课程一般面向专门的BIM软件使用培训，而很少考虑 BIM管理和协作环境下的工作过程[]。

巴基斯坦仅 $41 \%$ 的建筑类大学在开设或探讨BIM课程，预计花费5年时间才能将BIM纳入现有课程体系，最大的困难时缺乏训练有素的教师[7]。

# 2.2BIM在国内教育领域的应用现状

国内部分高校也开展了与BIM相关的研究。如2005年，华南理工大学建筑学院与欧特克联合创办了建筑物生命周期管理 BIM实验室；2010年，清华大学参考NBIMS 并结合调研，提出了中国建筑信息模型标准框架，2013年清华大学与广联达公司共同成立BIM研究中心；2011年华中科技大学BIM工程中心成立。国内仅有少数高校已经开设了BIM软件课程，例如清华大学、同济大学、天津大学、华中科技大学等在本科领域开设了BIM软件课程。另外，少量高校以选修课的形式开设了BIM课程，例如山东建筑大学、西安建筑科技大学、沈阳建筑大学等。

建筑类高职院校（如：四川建筑职业技术学院、浙江广厦建筑职业技术学院）在 BIM人才培养方面提出专业课程教学内容改革、基于BIM虚拟仿真教学、创新校企合作等对策，探索 BIM技术人才的培养模式[]。部分高校教师将 BIM 技术应用于《建筑识图与构造》[10]、《钢结构》[1I、《工程项目管理》[12]等课程。中国矿业大学将 BIM 技术应用于土建类本科生创新训练计划、建筑结构竞赛、毕业设计等环节[13]。

皖西学院涂劲松提出基于 BIM技术构建土木类专业综合实训平台，涵盖建筑设计、结构设计、设备设计、计量计价、施工模拟等内容[14]。南昌工程学院陈丽萍简要论述了BIM 技术在工程管理教学中的意义和基于 BIM的工程管理专业教学实训平台的构建要求，未涉及具体的构建方法[15]。张金玉在论述高职院校工程造价专业BIM人才培养模式改革中，也提出建立BIM技术实训基地建设的设想和依托技能大赛提升学生 BIM技能的途径[1]。白泉等总结了沈阳工业大学土木工程专业 BIM教学改革研究与实践情况，着重介绍了基于BIM 的课程体系设置和各项教改实践举措[17]。。

综上所述，BIM技术在国内外教育领域的应用将愈加广泛，特别是将BIM纳入现有课程体系取得较好地进展。国内关于建立BIM实训平台/实验室方面的研究也取得了一定成果，但详细论述如何构建BIM虚拟仿真实训平台的文献还较少。

# 3BIM虚拟仿真实训平台的建设目标及建设内容

# 3.1BIM虚拟仿真实训平台的建设目标

从学生能力培养、平台功能规划、师资培养三方面规划BIM虚拟仿真实训平台的建设目标如下：

（1）工程管理专业BIM虚拟仿真实训平台建设能促进学生职业能力培养体系与专业实践教学体系改革，从而提升学生的专业素质和工程实践能力，在学生的动手能力、沟通、协作能力、思辨能力和创新创业精神培养方面也起到重要的作用；

（2）实现基于BIM的工程项目全生命周期管理模拟，涵盖工程项目决策、设计、建造、运营、维护全寿命周期工程管理的主要业务过程，全面培养学生的工程项目基本策划、组织、实施、优化的能力，从而增强职业竞争力；

（3）培养一批熟悉BIM技术的"双师型"师资队伍，借助本项目构建的BIM虚拟仿真实训平台将工程管理的知识体系和教学模式进行优化，满足社会发展对高素质BIM人才培养的新需求。

# 3.2BIM虚拟仿真实训平台的建设内容

通过教学研究和多个建设用人单位需求调研，将工程管理BIM虚拟仿真实训平台按专业培养方案和学生的基本职业能力分为若干子平台，其平台系统结构图如图1所示。以培养具有较高专业素质和创新精神，具有国际视野的高级专门工程管理人才，同时，对提升教师的教学科研能力，建设一支"双师型"教师队伍也具有较大贡献。

![](images/06bf1b1aa43b01b2918db7ef77d86dcfb6cd55c85713242f1beae6175c26ccf9.jpg)  
图1BIM虚拟仿真实训平台系统结构图

BIM 虚拟仿真实训平台分为建筑结构设计子平台、建筑施工过程仿真子平台、BIM工程造价子平台、BIM一体化工程项目管理子平台等，在满足实践教学的基础上，构建了专业赛事平台（支持BIM应用技能大赛等）与企业实际项目实战平台，支持学生的动手能力，沟通能力，职业能力以及创新创业精神的培养。BIM虚拟仿真实训平台与学生综合能力培养的支撑关系如表1所示。

表1BIM虚拟仿真实训平台与学生综合能力培养的支撑关系表  

<html><body><table><tr><td>综合能力分类</td><td>支撑子平台</td><td>实践环节</td><td>涉及相关课程</td></tr><tr><td>建模识图能力</td><td>建筑结构设计实训子平台</td><td>课程设计 认识实习</td><td>《建筑制图》、《房屋建筑学》、《城市 规划》、《AutoCAD&BIM》</td></tr><tr><td>协同设计能力</td><td>建筑结构设计实训子平台</td><td>课程设计</td><td>《工程力学》、《工程结构》、《建筑材 料》</td></tr><tr><td>施组设计能力</td><td>建筑施工虚拟仿真实训子 平台</td><td>课程设计 生产实习</td><td>《工程测量》、《建筑施工》、《建筑设 备》</td></tr></table></body></html>

<html><body><table><tr><td>计量计价能力</td><td>BIM的工程造价实训子平 台</td><td>课程设计 毕业设计</td><td>《建筑工程计量计价》、《安装工程计量 计价》、《市政工程计量计价》、《装饰 装修工程计量计价》</td></tr><tr><td>招投标能力</td><td>BIM一体化工程项目管理 实训子平台</td><td>课程设计</td><td>《招投标与合同管理》、《建设法规》</td></tr><tr><td>施工管理能力</td><td>BIM一体化工程项目管理 实训子平台</td><td>课程设计 毕业设计</td><td>《项目管理》、《工程经济学》、《建设 工程质量与安全管理》、《建设工程信息 管理》、《国际工程管理》</td></tr><tr><td>创新创业能力 动手能力、沟通</td><td>专业赛事平台</td><td>竞赛</td><td>《职业规划与就业指导》</td></tr><tr><td>能力、跨专业学 习能力</td><td>企业实际项目实战平台</td><td>项目实践</td><td>《职业规划与就业指导》</td></tr></table></body></html>

BIM虚拟仿真实训平台根据各类高校对工程管理专业学生的培养目标不同，在设计内容上有所侧重。对于科研教学型高校，宜加强学生的设计能力，特别重视信息技术在工程管理中的应用，因此，建筑结构设计子平台和一体化项目管理子平台的内容应丰富；对于教学科研型高校，宜注重学生专业知识的掌握，因此，加大BIM工程造价子平台和一体化项目管理子平台的训练内容；对于应用型高校，特别强调学生的实战能力，因此，重点关注建筑施工虚拟仿真实训平台、赛事训练平台和企业项目实战平台。

# 3.2.1建筑结构设计实训子平台

（1）建筑设计建模实训

以市场占有率高的主流BIM建模软件Revit为核心，构建面向工程管理专业学生的建筑设计建模实训平台，学生在此实训平台上可完成多层学生宿舍、剪力墙结构高层住宅、单层工业厂房的建筑设计建模，完成日照分析、碰撞检测、疏散模拟、能耗分析等功能学习。在BIM模型漫游功能下，较深刻的认识建筑设计原理、建筑构造要求。

# （2）基本的结构设计实训

以市场占有率高的PK+PMCAD 结构建模设计软件为核心，辅助配置结构计算工具箱软件，构建面向工程管理专业学生的建筑结构设计实训平台，学生在此实训平台上可完成多层框架结构、多层砌体结构的结构计算，实现肋形楼盖梁板结构课程设计，培养学生的基本结构设计能力，同时较好的理解建筑结构协同设计，具有较高的建模和识图能力以及掌握基本构件设计原理和设计方法。

# 3.2.2 建筑施工虚拟仿真实训子平台

（1）三维建筑施工平面布置图设计

在三维环境下进行建筑施工平面布置图设计可以更好的解决场地功能分区、内部道路规划、吊运设备轨迹干涉等问题，学生在此实训平台上可完成多层框架结构、单层厂房结构施工的平面布置图设计，培养学生的基本建筑施工组织设计能力。

# （2）施工方案编制和模拟

施工方案编制是投标和施工实施的重要环节，工程管理专业学生由于实践经验少，施工方案的编制是一个难点。借助施工方案编制系统，基于案例检索的方法，推荐类似施工方案编制模板，提升施工方案的编制效率。借助BIM的施工动画、虚拟漫游功能，施工方案模拟可完成关键施工环节的过程模拟，例如：吊装过程、混凝土支模、钢筋下料、混凝土浇筑等过程。此实训平台，培养学生的更好地理解施工过程，提高施工方案编制能力。

# 3.2.3BIM工程造价实训子平台

工程造价相关课程学习和能力培养是我校工程管理专业的特色，配置了基于BIM的计量计价软件，能导入主流BIM软件（Revit、Tekla、MagiCAD等）构建的模型，实现计价算量，能满足建筑、安装、市政、精装四个工程造价专业领域的基本理论教学和实践教学（课程设计）要求。作为一个整体，BIM工程造价平台应与建筑结构设计子平台、建筑施工模拟子平台等接口。

# 3.2.4BIM一体化工程项目管理实训子平台

基于 BIM实现建设工程项目的一体化管理，涵盖招投标、合同管理、项目管理沙盘模拟、三维进度控制、成本控制、质量管理、安全管理、信息管理等业务领域。学生在此实训平台上可完成建设项目的标书制作、合同文本拟定、项目管理沙盘模拟、进度计划编制、技术经济方案比选和分析、建设法规案例分析等工作任务，全面培养学生的工程项目基本策划、组织、实施、优化的能力。

# 4基于云技术的BIM虚拟仿真实训平台配置

针对BIM虚拟仿真实训平台涉及软件系统多、应用领域广、升级服务频繁的特点，需要灵活部署、及时响应、快速搭建相应的软硬件资源。为此，我们从硬件设备层、软件平台层、基础应用层和多端接入层等四个层次来构建统一的虚拟化云平台。其中硬件设备层由文件服务器、应用程序服务器、Web 服务器等各类刀片式服务器组成；软件平台提供身份认证、数据交换、资源调度等服务；基础应用层加载建筑建模、施工沙盘模拟、工程造价等基于BIM的虚拟仿真实训平台、BIM应用能力大赛、建筑结构设计等各类赛事平台以及企业委托的各类项目平台；多端接入层在防火墙的保护下，通过校园网、互联网完成手机、电脑、平板等多类终端的接入。

为了方便兄弟院校构建BIM虚拟仿真实训平台参考，现将我校构建平台的主要软硬件配置进行说明，如表2所示：

表2主要的软硬件配置表  

<html><body><table><tr><td>序号</td><td>设备名称</td><td>规格</td><td>单位</td><td>数量</td></tr><tr><td>1</td><td>硬件</td><td></td><td></td><td></td></tr><tr><td>1-1</td><td>虚拟化图像服务器</td><td>DL385P Gen8 24 核 CPU/128G 内存/1.8T SAS 硬盘/NvidaK1显卡/920 冗余电源</td><td>台</td><td>4</td></tr><tr><td>1-2</td><td>电脑</td><td>i7-6700 处理器，16G 内存，1T硬盘，19.5 寸 WLED显示器</td><td>台</td><td>70</td></tr><tr><td>1-3</td><td>显示屏</td><td>60 英寸,1920*1080 分辨率,16:9，Andriod4.2, 水平视角、垂直视角160-180 度</td><td>台</td><td>6</td></tr><tr><td></td><td>投影仪</td><td>5500 流明，1024*768，DLP,激光光源， 100000:1，光源 20000小时，360°安装，双画</td><td></td><td></td></tr><tr><td>1-4 2</td><td>建筑结构设计子平台软件</td><td>面显示</td><td>台</td><td>1</td></tr><tr><td>2-1</td><td>BIM建模软件</td><td></td><td>节点</td><td></td></tr><tr><td></td><td>BIM建模一致性检查软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>2-2</td><td></td><td></td><td></td><td>70</td></tr><tr><td>2-3</td><td>PK+PMCAD+STS网络版</td><td></td><td>节点</td><td>70</td></tr><tr><td>3</td><td>建筑施工虚拟仿真子平台</td><td></td><td></td><td></td></tr><tr><td>3-1</td><td>施工平面图布置软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>3-2</td><td>施工组织设计软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>3-3</td><td>BIM5D 施工管理软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>4</td><td>BIM工程造价子平台</td><td></td><td></td><td></td></tr><tr><td>4-1</td><td>BIM 建筑工程计价软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>4-2</td><td>BIM土建算量软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>4-3</td><td>BIM 钢筋算量软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>4-4</td><td>BIM安装算量软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>4-5</td><td>BIM市政算量软件</td><td></td><td>节点</td><td>70</td></tr><tr><td>4-6</td><td>BIM 精装算量软件</td><td></td><td>节点</td><td>70</td></tr></table></body></html>

# 5结束语

BIM技术在建筑行业的应用，正逐步进入深化应用阶段，社会对BIM人才需求很大，BIM虚拟仿真实训平台建设正是以提升学生职业能力为目的，通过构建建筑结构设计、施工虚拟模拟、BIM工程造价、BIM一体化项目管理等实训子平台，全面覆盖工程管理专业主干课程，设计了基于云架构的系统层次结构并列举了主要的软硬件构成，以供同行建立类似实训平台参考。进一步的研究工作包括：更多类型的平台实训课程开发，平台实训评价等。

# 参考文献

[1]教育部高等教育司．关于开展国家级虚拟仿真实验教学中心建设工作的通知（教高司函（2013）94号）[Z].  
[2]李炎锋，杜修力等．土木类专业建设虚拟仿真实验教学中心的探索与实践[J]．中国大学教学，2014，(9):82-85.  
[3]张尚，任宏．AlbertP.C.Chan.BIM的工程管理教学改革问题研究（一)[J]．建筑经济，2015，36(1)：113-117.  
[4] Sacks R.,E.Pikas.Building information modeling education for construction enginering and management.I:Industry requirements,state of the art,and gap analysis[J].Journal of Construction Engineering and Management,2013.  
[5] Adamu, Z.A., T. Thorpe. How should we teach BIM? A case study from the UK[C]. Washington, DC: The ${ \mathfrak { g } } ^ { \mathrm { t h } }$ BIMAcademic Symposium & Job Task Analysis Review,2015.  
[6] NATSPEC. BIM education - global -2015 update report[R]. NATSPEC Construction Information, 2015.  
[7] Ali A., Zia U.D.,Rizwan F. Integration of BIM in construction management education: an overviewof PakistaniEngineering universities[C]. Phoenix,AZ: International Conference on Sustainable Design,Engineering andConstruction , 2016.  
[8] 曾文海，付伟明．BIM技术在高校教学中的应用研究[J]．黑龙江生态工程职业学院学报，2014，(6)：85-86.  
[9]孙丽雅，李修强，程国强．建筑类高职院校BIM技术紧缺人才培养对策研究[J]．南阳师范学院学报，2015，14(12): 72-75.  
[10] 王晶莹．BIM技术在《建筑识图与构造》课程中的应用[J]．职业技术，2016，15(4)：66-68.  
[11] 王琳，杨先忠，苗莉娟．BIM 技术在高职钢结构课程教学中的应用研究[J]．高等教育在线，2015，(12):159-160.  
[12] 钟炜，张馨文，姜腾腾．BIM仿真在工程项目管理课程教学改革中的应用研究[J].土木建筑工程信息技术，2013，(06):7-11，34.  
[13] 朱红光，易成，王鹊等．BIM技术在土建专业教学中的应用现状及建议[J]．教育教学论坛，2015，(11):184-185.  
[14] 涂劲松，李瑞霞．基于 BIM 技术应用的土木类专业综合实训平台构建[J]．合肥学院学报，2015，25(3):76-80.  
[15] 陈丽萍，陈述．基于 BIM技术的工程管理专业教学实训平台的构建[J]．中国科教创新导刊，2010，(31):234-235.  
[16]张金玉．高职院校工程造价专业BIM人才培养模式[J]．项目管理技术，2015，13(7)：27-31.  
[17] 白泉，边晶梅．土木工程专业BIM教学改革研究与实践[J]．土木建筑工程信息技术，2017，9(5)：90-93.

# Research on construction of BIM virtual simulation training platform in construction management discipline

YU Hong-liang12,LULing',XuYuanuan' (1. School of Management,Wuhan University of Science and Technology,,Wuhan 430081, China; 2 BIM Engineering Center,Huazhong University of Science and Technology,Wuhan 43O074, China)

Abstract: Implementation of the practical teaching reform and improving students' ability of engineering practice and professional quality is an important measure to fully implement the national medium and long-term education reform .Itis alsoa critical approach to develop complex,application-oriented,innovative and pioneering talents. However,the depth of teaching practice is not reachable,and issues of relevance is not strong.Now construction enterprise or project site practice and practical teaching methods are commonly used, but there are also safety risks and the constraints of time and space.Firstly,the BIMapplication status of both at home and abroad in education field is presented,then proposed the building target of BIM virtual imitation practical training platform,designed general system structure figure. The platform is divided into building structure design practical training sub-platform, construction virtual simulation practical training sub-platform, BIM engineering cost practical training sub-platform,and BIM integration project management practical training sub-platform. Lastly，cloud schema schematic of practical training platform is proposed ，main of hardware and software constitute is listed, and it provides a reference of establishing similar practical training platform for peers.

Keywords: BIM; Practical training platform; Construction management; Virtual simulation

# 附第一作者简介

姓名：余宏亮  
性别：男  
籍贯：湖北武汉  
学位：博士  
职称：高级工程师  
主要研究方向：工程管理  
联系地址：武汉科技大学管理学院  
联系电话：027-68862135  
手机：13971380391  
电子信箱：yuhongliang@wust.edu.cn