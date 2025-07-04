# 基于大数据的公路隧道养护决策

胡珉1,2 张明正2,3 施永泉喻钢,2

（上海大学悉尼工商学院，上海201400；2.上海大学上海大学－上海城建建筑产业化研究中心上海，上海200072；3.上海大学土木工程系，上海200072；4.上海隧道工程股份有限公司，上海200232）

【摘要】为了解决公路隧道设施众多及信息异构分散等特点对公路隧道养护决策带来的困难，本文在对公路隧道养护特点分析的基础上，进行了从隧道全生命周期信息出发，利用大数据分析对隧道养护评估和优化进行了研究。文章围绕全生命周期养护评估方法和优化决策，描述了全生命周期信息评估决策的基本原理和实现路径，并根据评估结果进行了有约束条件下的养护策略选择。最后，文章对该方法的创新点和应用效果进行了总结，并指出了未来隧道养护评估的发展趋势。

【关键词】公路运输；运维；决策支持系统；公路隧道；全生命周期；建筑信息模型

【中图分类号】TU17；U459.2；U540.5【文献标识码】A 【文章编号】1674-7461（2016）01-0048-05  
【DOI】10.16670/j.cnki.cn11-5823/tu.2016.01.08

# 1引言

近年来，我国隧道发展迅速，隧道的长度和数量极限一次次被刷新。隧道作为重要的城市基础设施，尤其是城市公路隧道和地铁隧道，担负着重要的城市交通功能。据交通部门统计，截至2013年年底，全国共有公路隧道11359条，总长达9605.6$\mathbf { k m } ^ { [ 1 ] }$ 。相比我国隧道建设的发展速度，相关的隧道运营养护技术并没有得到很大的提升，并且随着城市的发展，我国隧道由大规模建设期进人了运维期的阶段，这对隧道的运营养护管理技术提出了更高的要求。然而目前公路隧道养护管理总体很难把握，养护经费的决策，隧道健康状况的评估都很难进行准确的判断。为开展公路隧道的经常性、及时性和预防性养护，实现公路隧道养护管理规范化、标准化、智能化，本文提出了基于BIM、物联网、大数据、云计算等技术的从全生命周期信息的角度进行隧道养护方案评估决策系统的方法。

# 2系统功能与需求分析

公路隧道养护管理主要应用于公路隧道各类养护数据采集、存储、检索、分析处理，提高数据使用效率，挖掘数据有用信息；提高公路隧道养护管理效率和降低管理成本[2]。通过对公路隧道病害形成机理、隧道病害评价与处置策略等进行研究，以及对公路隧道管理部门的管理模式、业务需求、用户需求和业务流程进行分析，提出如下总体需求：

(1)公路隧道建设与养护资料的规范化、标准化管理与存储

建立详细的隧道土建设施全生命周期的技术状态、地理与属性数据库，有效管理各种公路隧道养护数据；提供高效的养护数据采集手段和灵活的数据更新维护方法；

(2)公路隧道病害评价决策

隧道病害评价决策应针对隧道结构存在的病害，通过结构病害分析模型结合规范标准，对隧道内结构病害发展趋势进行预测，对结构病害等级以及整条隧道整体服役等级作出评价；

# (3)公路隧道病害处置策略

隧道病害处置策略需存储针对各种类型、各种等级结构病害的专家养护策略；

# (4)公路隧道养护计划制定

基于病害评价所确定的病害安全评价等级和病害发展趋势预测，通过数据分析在不同的约束条件下来制定养护计划、核算养护费用，从而形成养护计划报告。

# 2.1 系统流程设计

隧道养护决策的评价流程如图1所示。

# 2.1. 1 中间数据库

中间数据库是存储系统评估决策所需数据的数据库，通过中间表的形式将大连路隧道使用的其他运维养护系统中的数据提取过来，如隧道养护管理系统中的隧道结构基本信息，隧道结构日常检查、隧道结构定期检查、隧道结构专项检查结果；结构健康监测系统则是通过传感器采集到实时的隧道结构健康数据，如：纵向沉降、接缝张开、断面收敛等数据。

# 2. 1.2 结构评估

针对隧道存在的病害，通过隧道评价决策数学模型算法并结合规范标准，对隧道内结构病害等级进行评价。

在建立盾构隧道结构安全评估指标体系时，鉴于难以一次性地考虑问题的全部细节，故采用系统科学中的层次性原理，即大系统理论中的分解协调原理，将问题分解为多个层次，每个层次又有多个构成要素，由粗到细，由表及里，从全局到局部地逐步深入分析，将影响盾构隧道结构安全状态的诸多因素条理化、层次化，从而建立递阶层次分析模型，即采用层次分析法（theAnalyticHierarchyProcess，简称为AHP)的思想建立盾构隧道结构安全评估指标体系[3]，如图2、图3。

![](images/124ca994d05dc52793e771f81582a7254f10e8e48a718c16432ac0219ad71bf0.jpg)  
图2指标体系递阶层次结构图

![](images/cb549d19115c8ccd46f831a43147647a644ea2faf406800da8134be0d74e754c.jpg)  
图3圆隧道段评价指标

![](images/11ab46621c43f849176fbe3c80b394a1c5b21459d3e166665f40995614dcb963.jpg)  
图1隧道设施养护决策流程图

万方数据

由于R语言在大数据处理和分析上有得天独厚的优势，所以数学模型的搭建是通过R语言将评价体系写成R脚本并放在系统的后台服务端。

后台服务端包含诸诸多独立的算法子程序，由统一的模型中心操作控制。图4给出了数据模型的控制框架，共包含模型配置和模型执行两个子模块。模型配置用于算法的参数设置、模型训练及存储、模型运行状态的监控等；模型执行用于模型的调用、输出判断结果等。

![](images/a70eb4d251b581a1d0dae8cc308e98d683271da477ae0892ce05ff768ae5a2b3.jpg)  
图4数据模型的控制框架

数据分析后台服务端的基本架构主要包含两个部分（如图5）：

# 1)应用程序

通过微软公司提供的.NETFramework技术搭建控制台程序，提供数据库读取和存储、文件访问、数据预处理、周期性调度等支持；

# 2)R服务器

通过Revolution公司提供的DeployRFramework技术搭建R语言分析引擎，提供API接口供应用程序访问及模型加载功能，调度控制RSession多脚本程序，执行复杂算法的运算。

![](images/a78a09a0ea89088fe9dc52c17ce85c4b19f4e8190ec48632554da56810e59da6.jpg)  
图5服务端基本架构

# 2.1.3 1 养护策略选择

根据不同的方案要求选择不同的养护策略，以大连路隧道为例，系统提供了性能优先和经济优先两种不同的养护策略。如在经济优先下，根据评估结果对于处于风险不可接受区的设施优先进行养护维修；对于处于风险可忽略区的设施结构暂时不考虑对其进行养护维修[4]。再通过对该养护策略后的性能进行性能预估和年度预算进行对比，如果满足要求则输出养护方案。

优先养护的方法则通过引用多属性决策的群排序方法的“加权偏差平方和最小的思想”排序方法来处理在资金受限制的情况下维修优先级问题[5]。优先级排序是目前国内外普遍采用的方法，即在有限资金的条件下，优先安排影响大，技术状况较差，维护等级高的项目，以达到合理地分配和使用有限资金，保证项目处在规定的服务水平上，使养护维修资金发挥最佳的经济效益和社会效益。

# 3 工程应用

公路隧道全生命周期养护决策对于提升公路隧道养护管理水平和效率，保障公路隧道结构安全和降低运维成本有着十分重要的意义。目前本系统已经在上海市大连路隧道养护管理中得到应用，使大连路隧道养护实现了数据采集标准化、分析处理智能化、养护决策科学化、业务管理信息化，为管理部门及时地发现病害并加以科学防治，减少事故发生，保证隧道的安全畅通提供了技术手段。

图6、图7、图8为系统实时监测到的隧道断面收敛、接缝张开、纵向沉降。图9为系统根据病害评估结果，将处于危险等级的结构评估段展示出来，并提出维养建议。图10为根据结构健康的评估结果结合养护规范，在有约束条件下计算年度养护费用。

# 4结论

针对目前隧道运维有很多管理系统的现状，本文通过采用中间数据库的形式，提取整合隧道评估所需要的信息，并结合R语言的大数据分析优势，实现了隧道服役状况的评估和有约束状态卜的隧道年度养护方案生成，为城市公路隧道运维提供了一个新的思路与方法。但本系统的评估指标参数获取方法采用的是取最新时间的数据，如何考虑评估指标数据的突发变化对结构评估段的影响，这方面值得研究。

![](images/f2a6ba2bcf27dc2499de8e355192f07b62ac42507ce3ff591ba0ad4af0d9081a.jpg)  
图6断面收敛

![](images/1d8bf822370cd6a178df1d9ff6298339e03e9de2d218b27939fd10f2a3cbe4d4.jpg)  
图7接缝张开

![](images/9effbcef4b0aa27f13bdda0039a0b827c5f08c20bab0c06b81dc8549c7da0002.jpg)  
图8纵向沉降

![](images/830f0a057f377de69937d0f00f12f53e64315b9701a417a944479d62dcc9e1f4.jpg)  
图9结构评估

![](images/e52196b9cc9d0703a3518ed5117510ce9bac84c8332351f1f4f628ba36b04a16.jpg)  
图10 养护方案

# 参考文献

［1］王波．厦门翔安海底隧道土建结构维修养护计算机管理系统［D].西南交通大学，2009.  
[2］周健，杨洋，付立家.公路隧道预防性养护管理系统研究[J].公路交通技术，2011，06：131-134.  
［3］许慧，张礼敬，余健平，张二强.标度扩展的AHP在长江隧道安全设施评估中的应用[J].工业安全与环保，2013，10：49-52.  
「4]刘延芳，周泳涛，鲍卫刚.桥梁结构养护方案优先排序方法研究[J].公路，2013，04：201-204.  
[5］夏海兵，姚安林，尹继明.在路网中桥梁维修优先级的辅助决策方法[J].公路交通技术，2007，02：121-122+132.

# Research on Tunnel Operation and Maintenance Decision Support System based on Big Data

Hu Min1,²，Zhang Mingzheng²,³，Shi Yongquan4，Yu Gang1,

(1.SILCBusiness School,Shanghai University,Shanghai2O14OO,China； 2.SHU-SUCGResearchCenterofBuildingIndustrialization,Shanghai University，Shanghai2OoO72,China； 3.Civil Engineering Department,Shanghai University，Shanghai 2OoO72,China； 4.Shanghai Tunnel Engineering Co.,Ltd.,Shanghai 20O232,China）

Abstract:Inordertosolvethetheproblemscausedbydiversifed informationinthehighwaytunnel,thisarticleanalyzesthecharacteristicsof highway tunnel andusesbigdataanalysisandassessment ofBIMtechnology to studythetunnelmaintenanceandoptimization.Basedontheevaluationof the whole lifecycle maintenanceand optimizationdecisionmethod,thearticledescribesthebasicprincipleofwholelifecycleinformationevaluationdecisionandimplementationpath,andmakesstrategicchoicesaccording totheevaluationresults.Finally,innovation pointsandapplicationefectsofthismethodaresummarized,andthefuturedevelopmenttrendof thetunnelmaintenance evaluation is pointed out.

KeyWords:Highway Transportation；Operationand Maintenance；Decision Support System；Road Tunnel; Life Cycle；Building Information Modeling

万方数据