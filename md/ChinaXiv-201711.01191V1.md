# 新农合药品报销目录跨省整合信息系统设计与实施

李亚子　郑见立　周奕洋　李国垒(中国医学科学院医学信息研究所北京100020)

摘要：【目的】分析新农合药品报销目录存在的问题，提出整合技术路线，开发信息系统，整合多来源词表，生成国家新农合药品一体化目录。【方法】借鉴UMLS整合技术路线，采用映射的方法对多来源药品字典集成存在的问题进行解决。【结果】制定了相应的新农合药品编码目录数据结构和映射算法，完成了国家新农合一体化目录构建系统的设计与开发。【局限】药品之间相互药理作用关系还需进一步梳理完善。【结论】经过制定数据结构和映射算法对新农合目录编码进行映射，解决了构建国家新农合药品目录编码中多来源字典集成问题。

关键词：新型农村合作医疗多来源字典药品编码集成映射分类号:R19G350

# 1引言

随着新农合政策的执行，实现数据交换和数据共享已成为大势所趋，数据的共享有助于推动新农合政策的贯彻落实，实现新农合患者就医便利、报销便捷[1]。其中新农合药品报销目录是进行就医结算报销的依据，但是目前各省新农合信息系统药品目录不一致，难以进行相关数据分析以及跨省就医即时结算。因此有必要建立统一性、延展性与适应性均较好的国家一体化药品目录。

在对多个异构数据源进行集成时，若数据集成系统中的本体是单独建立而不是参照同一个共享本体构建，会造成局部本体间存在语义不一致的情况，为了系统内查询处理的正常运行，必须建立本体映射[2]。目前国内外就异构数据源集成技术已展开较多的研究。国外方面，Husain 等开发 SOCR (Statistics OnlineComputationalResource)系统来处理不同来源的数据集成问题[3]；Verbeke 等提出基于语义网络的数据集成方法实现对不同来源的肿瘤数据的集成[4]；Scheurwegs 等对每一个数据源分别建立模型，然后利用Meta-Learner分别对模型进行评价，最终实现异构数据源的集成[5]。在国内方面，才苗提出基于神经网络的异构数据库语义集成技术[；文语欣则采用语义技术解决临床信息异构问题，提出基于物理层、语义层和应用层的三层架构模型的临床信息交换框架，解决医疗信息系统之间的信息共享7；郭鑫提出基于本体的异构数据集成技术，以解决异构数据源之间存在的系统异构、语法异构和语义异构问题[8]。

UMLS(Unified Medical Language System)[9]是使用最为广泛的计算机化的情报检索语言集成系统，作为语言规范化、翻译的工具，可实现跨数据库交互的词汇转换。UMLS 通过对术语的标化等处理[10]，实现了对100 余词典100 万以上的概念的集成[11]，应用于健康信息互操作、医学术语、药品名称的联接、保险账单的编码等。本文主要针对新农合药品报销目录编码进行集成，由于各省的目录编码都是在《国家基本医疗保险、工伤保险和生育保险药品目录(2009 版)》、《国家基本药物目录(2012版)》目录的基础上根据本地情况进行适当改造[12]。因此本文借鉴UMLS的技术整合路线，参考UMLS词表结构进行数据结构设计，完成了《国家基本药物目录》《社会基本医疗保险、工伤保险和生育保险药品目录》以及安徽、河南等10个省的新农合药品报销目录的整合。

# 2研究对象与方法

# 2.1 数据来源

来源词表包括：《国家基本药物目录(2012版)》(简称"国家基药目录")(药品数，520)、《国家基本医疗保险、工伤保险和生育保险药品目录(2009版)》(简称“社保目录"药品数，3277)，以及安徽(药品数，1885)、福建(药品数,2341)、河南(药品数,2714)、江苏(药品数,1198)、四川(药品数,1330)、河北(药品数,1686)、吉林(药品数,1806)、黑龙江(药品数,2172)、湖南(药品数,1781)、内蒙古(药品数,2082)等10省新农合药品报销目录。

# 2.2 研究方法

(1）数据结构设计

本文借鉴UMLS词表整合系统设计了国家新农合一体化目录构建系统数据结构，如图1所示：

![](images/c8e51e1ea49280aebe8bafabcf85885e1dbc1994a9d1de94ff662484397c9bb9.jpg)  
图1国家新农合一体化目录构建系统的核心数据结构

图1中来源词表(SAB)用于登记来源词表，将国家基药目录、社保目录以及安徽等10个省目录按顺序存放到来源词表中；节点元数据表(NodeMeta)用于存放来源字表各字段信息，将国家基药目录、社保目录以及各省级药品目录中的字段信息存放到节点元数据表中；节点元数据关系表(ColRel)用于存储节点元数据表中各个字段之间的关系；主题词盛放表(Subject)用于存放一体化词表中的主题词相关信息；主题词项目信息表(NodeItem)用于存放主题词各项目详细信息;主题词关系表(Sub_Rel)用于存放一体化词表中主题词之间的关系；节点类型表(NodeType)用于存储主题词字段的类型，解决词系词簇问题。

(2）映射算法设计

构建映射算法规则，实现各省级目录向国家级目录集成映射，算法映射规则如下：

$\textcircled{1}$ 提示与该节点的父节点相同或相似的子节点;$\textcircled{2}$ 提示与该节点某些字段相同的词条，如名称相同的，编码相同的，对于编码相同的，又可提示该编码的兄弟节点;$\textcircled{3}$ 提示与该节点相似度最大的前20个词条;相似度计算 $\mathrm { \sf S } =$ (字段i的相同部分^2/字段i的总长度)(A1与 A2 相同部分^2/A1字段与 A2 字段的长度之和);$\textcircled{4}$ 在目录映射中，出现语义相同，名称不同的，主要原因是语序不一致，因此，忽略语序顺序进行词条比对相似度计算；$\textcircled{5}$ 提供包含关系的词条发现，如词条A，可检索完全包含词条A的词条。

# (3）映射流程

国家新农合一体化目录构建系统旨在基于各省新农合目录的基础上，构建一套全面、细粒度的国家级目录，从而建立各省与国家新农合一体化目录的映射。字典目录集成系统的构建流程如图2所示：

![](images/ce64d24c29c04bd96849105c46064bbbc1d929d5bf21e8b9152b6a942c72f91d.jpg)  
图2国家新农合一体化目录构建流程

首先将国家基药目录作为国家一体化目录的初始值，然后按顺序分别将社保目录，安徽、河南等各省级新农合目录转化为指定格式，根据制定的映射算法，完成药品名称的集成映射。

# 3研究过程

# 3.1 整合实例

以2012版国家基药目录和2015年河北省药品目录中的"青霉素"为例阐述系统的映射过程。表1和表

2分别为目录示例。

表12012版国家基药目录示例  

<html><body><table><tr><td>序号</td><td colspan="2">编码</td><td>品名</td><td>分类</td><td>标注剂型</td></tr><tr><td>1</td><td colspan="2">GJJY-HS-1</td><td>青霉素</td><td>青霉素类</td><td>注射用无菌粉末</td></tr><tr><td colspan="6">表2 2015年河北省药品目录示例</td></tr><tr><td>序号</td><td>编码</td><td>品名</td><td>拼音码</td><td>分类</td><td>标注剂型</td></tr><tr><td>1</td><td>10101006青霉素</td><td></td><td>qmsjyzsywjfm</td><td>青霉素类</td><td>注射用无菌粉末</td></tr></table></body></html>

(1）按顺序分别将国家基药目录、2015年河北省药品目录登记到来源词表(SAB)中，存储形式如表3所示：

表3来源词表(SAB)存储示例  

<html><body><table><tr><td>SAB_ID</td><td>SAB_Name</td><td>SAB_ABR</td><td>SAB_DESC</td><td>B1</td></tr><tr><td>2012版国家 基药目录ID</td><td>国家基药 目录</td><td>gjjyml</td><td>国家基药 目录</td><td>2012</td></tr><tr><td>2015 年河北省 药品目录ID</td><td>2015 河北省 药品目录</td><td>hbypml</td><td>河北省 药品目录</td><td>2015</td></tr></table></body></html>

(2)将来源词表中的各字段信息存放到节点元数据表(NodeMeta)中，存储形式如表 4所示，并将来源词表字段之间的关系存放到节点元数据关系表(Col_Rel)中，在示例中并未涉及相关字段，但在江苏省 2009 年药物目录中存在县(市、区)和乡(镇)两个字段，该两个字段之间的隶属关系应存放到节点元数据关系表中。

(3）将国家基药目录存放到主题词盛放表中作为初始值，形成初始化的国家新农合一体化目录，然后将社保目录，安徽、河南等新农合目录向一体化目录映射。在省级目录与国家新农合一体化目录进行映射时，将该省级目录与国家新农合一体化目录药品名称进行逐条比对，比对的对象是药品名称和剂型。如果国家新农合一体化药品目录中已包含该药品，则建立映射关系。如果国家新农合一体化目录中未包含该药品，则增加该药品到国家新农合一体化目录中。是否包含"的判断依据为，品名一致或品名不一致但有效成分一致，并且剂型一致，则判断为“包含”。同一种药品，不同剂型视作不同记录，暂不考虑规格的差异。主题词盛放表示例如表5所示。由于2015年河北省药品目录“青霉素"药品向一体化目录映射时，该药品已经存在，且品名和剂型均一致，故不存放到主题词盛放表中，而 2015 年河北省药品目录中的"头孢替唑"在一体化目录中不存在，故将其并增到一体化目录中。

(4)将主题词盛放表中主题词的项目信息存放到主题词项目信息表(NodeItem)，如表6所示。

表4节点元数据表(NodeMeta)存储示例  

<html><body><table><tr><td>Col_ID</td><td>Col_Key</td><td> LABEL</td><td>SAB_ID</td><td>Col_DESC</td><td>B1</td></tr><tr><td>序号ID</td><td>xh</td><td>序号</td><td>2012版国家基药目录ID</td><td>基药目录字段</td><td>2012</td></tr><tr><td>编码ID</td><td>bm</td><td>编码</td><td>2012版国家基药目录ID</td><td>基药目录字段</td><td>2012</td></tr><tr><td>品名ID</td><td>pm</td><td>品名</td><td>2012版国家基药目录ID</td><td>基药目录字段</td><td>2012</td></tr><tr><td>分类ID</td><td>fl</td><td>分类</td><td>2012 版国家基药目录ID</td><td>基药目录字段</td><td>2012</td></tr><tr><td>剂型ID</td><td>jx</td><td>标注剂型</td><td>2012版国家基药目录ID</td><td>基药目录字段</td><td>2012</td></tr><tr><td>序号ID</td><td>xh</td><td>序号</td><td>2015年河北省药品目录ID</td><td>河北省药品目录字段</td><td>2015</td></tr><tr><td>编码ID</td><td>bm</td><td>编码</td><td>2015 年河北省药品目录ID</td><td>河北省药品目录字段</td><td>2015</td></tr><tr><td>品名ID</td><td>pm</td><td>品名</td><td>2015年河北省药品目录ID</td><td>河北省药品目录字段</td><td>2015</td></tr><tr><td>拼音码ID</td><td>pim</td><td>拼音码</td><td>2015年河北省药品目录ID</td><td>河北省药品目录字段</td><td>2015</td></tr><tr><td>分类ID</td><td>fl</td><td>分类</td><td>2015 年河北省药品目录ID</td><td>河北省药品目录字段</td><td>2015</td></tr><tr><td>标注剂型 ID</td><td>jx</td><td>标注剂型</td><td>2015 年河北省药品目录 ID</td><td>河北省药品目录字段</td><td>2015</td></tr></table></body></html>

表6主题词项目信息表(NodeItem)存储示例  

<html><body><table><tr><td>Sub_ID</td><td>Sub_STR</td><td>Sub_ID</td><td>Sub_DESC</td><td>B1</td></tr><tr><td>青霉素 ID</td><td>青霉素</td><td>2012版国家基药目录ID</td><td>青霉素药品</td><td>2012版基药目录</td></tr><tr><td>头孢替唑 ID</td><td>头孢替唑</td><td>2015 年河北省药品目录 ID</td><td>头孢替唑</td><td>2015 年河北药品目录</td></tr></table></body></html>

表5主题词盛放表(Subject)存储示例  

<html><body><table><tr><td> Item_ID</td><td>Sub_ID</td><td>Item_Col_ID</td><td>Item_Col_Value</td><td>Node_Rank</td><td>B1</td></tr><tr><td>项目ID1</td><td>2012版国家基药目录ID</td><td>xh</td><td>1</td><td>1</td><td>序号</td></tr><tr><td>项目ID2</td><td>2012版国家基药目录ID</td><td>bm</td><td>GJJY-HS-1</td><td>2</td><td>编码</td></tr><tr><td>项目ID3</td><td>2012版国家基药目录ID</td><td>pm</td><td>青霉素</td><td>3</td><td>品名</td></tr><tr><td>项目ID4</td><td>2012版国家基药目录ID</td><td>fl</td><td>青霉素类</td><td>4</td><td>分类</td></tr><tr><td>项目ID5</td><td>2012版国家基药目录ID</td><td>jx</td><td>标注剂型</td><td>5</td><td>剂型</td></tr><tr><td>项目ID6</td><td>2015 年河北省药品目录ID</td><td>xh</td><td>1</td><td>1</td><td>序号</td></tr><tr><td>项目ID7</td><td>2015 年河北省药品目录ID</td><td>bm</td><td>10102013</td><td>2</td><td>编码</td></tr><tr><td>项目ID8</td><td>2015 年河北省药品目录ID</td><td>pm</td><td>头孢替唑</td><td>3</td><td>品名</td></tr><tr><td>项目ID9</td><td>2015年河北省药品目录ID</td><td>pim</td><td>tbtzzsj</td><td>4</td><td>拼音码</td></tr><tr><td>项目ID10</td><td>2015年河北省药品目录ID</td><td>fl</td><td>头孢菌素</td><td>5</td><td>分类</td></tr><tr><td>项目ID11</td><td>2015 年河北省药品目录ID</td><td>jx</td><td>注射剂</td><td>6</td><td>剂型</td></tr></table></body></html>

将主题词之间的关系(即相关药物之间的协同(增效)、相加(增加)、括抗(减效)等)存放到主题词关系表中，并将主题词所属的类型存放到节点类型表中，分别如表7和表8所示：

表7主题词关系表(Sub_Rel)存储示例  

<html><body><table><tr><td>Sub_Rel_ID</td><td>From_Sub_ID</td><td>To_Sub_ID</td><td>Sub_Rel_Type B1</td></tr><tr><td>关系ID</td><td>胺碘酮ID</td><td>美托洛尔 ID</td><td>协同作用 增效</td></tr></table></body></html>

表8节点类型表(NodeType)存储示例  

<html><body><table><tr><td>NodeType_ID</td><td>Item_ID</td><td>Type_STR</td><td>SAB_ID</td><td>B1</td></tr><tr><td>类型ID1</td><td>项目ID4</td><td>青霉素类</td><td>2012版国家 基药目录ID</td><td>2012版 基药目录</td></tr></table></body></html>

# 3.2 整合结果

通过对国家基药目录、国家社保药品目录、安徽等10省新农合药品目录进行整合。不考虑剂型的情况下，

共计4136种,其中西药2112种，中药2024种；考虑剂型,共计6061种，其中西药2946种，中药3115种。

# 4系统核心功能实现

通过设计基于UMLS的数据结构，制定相关的映射算法，并以整合药品目录为基础，开发了国家新农合一体化目录构建系统，完成国家新农合目录(疾病编码、药品编码、诊疗编码规范、耗材编码规范和机构编码)的初始化及与各省新农合字典目录的对照，建立了关联，并实现了国家新农合一体化目录的及时更新。系统主要通过国家新农合一体化目录初始化和映射管理实现集成目录的构建。在目录初始化界面，选择一个目录大类，然后选择一个省份以及省目录版本,此时会在省目录框中出现所选择的目录树，再选择国家新农合一体化目录版本，国家新农合一体化目录框中会出现国家新农合一体化目录树，将左侧省目录树中的树节点拖动到右侧国家新农合一体化目录树下面的某个节点，即完成了国家新农合一体化目录的初始化功能，如图3所示：

![](images/30492b36aba5a158098357f5810eb1f7674fc9d1b3747f225ff3d704e2e28b13.jpg)  
图3国家新农合一体化目录初始化功能

![](images/8c030f36cf083e3faf7ea69d41a4aa06c52d9ac925016c2462c882d1ed4269fc.jpg)  
图4映射管理功能

如图4所示，在映射管理功能模块中，选择一个目录大类，并选择一个省份以及省目录版本，和一个国家新农合一体化目录版本，在左侧显示的是省目录，右侧显示的是国家新农合一体化目录，然后点击建立对照，即可完成省级目录向国家新农合一体化目录的映射。

# 5结语

本文分析了构建新农合国家一体化目录中存在的问题，针对这些问题，提出了集成映射的解决方法，制定了相应的数据结构、集成映射规则与算法，并开发了国家新农合平台一体化目录构建系统，实现了各个省目录向国家新农合一体化目录的集成和映射。随着目录的成熟，以及配套政策的出台，可将集成目录用于新农合跨省就医的异地结算和即时结报中。

本研究还存在一定的局限，药品之间相互药理作用关系库还需进一步完善以及多种药品之间的药理作用关系还需进一步研究，系统功能完善后，将国家一体化目录作用于全国新农合跨省就医即时结报中，以指导各地结算政策的衔接。

# 参考文献：

[1]王秋月．新农合即报系统的研制与开发[J]．中国数字医学, 2014(1):109-111.(Wang Qiuyue.Research and Development of New Rural Cooperative Medical Instant Reimbursement System [J].China Digital Medicine,2014(1):109-111.)   
[2] 张红宇．数据集成中本体映射的研究[D]．长沙：中南大学, 2005.(Zhang Hongyu.Research on Ontology Mapping in Data Integration [D].Changsha: Central South University, 2005.)   
[3] Husain S S,Kalinin A,Truong A，et al.SOCR Data Dashboard: An Integrated Big Data Archive Mashing Medicare,Labor, Census and Econometric Information [J]. Journal of Big Data,2015.DOI:10.1186/s40537-015-0018-z.   
[4] VerbekeLPC.Van Den EyndenJ,Fierro AC,et al.Pathway Relevance Ranking for Tumor Samples Through NetworkBased Data Integration [J]．PLOS ONE，2015，10(7): e0133503.   
[5] ScheurwegsE,LuycksK,LuytenL,etal.Data Integration of Structured and Unstructured Sources for Assigning Clinical Codes to Patients Stays [J].Journal of the American Medical Informatics Association,2016,23:e11-e19.   
[6] 才苗．基于神经网络的异构数据库语义集成的研究[D].大 连：大连理工大学,2009.(Cai Miao.Research of Semantic Integration in Heterogeneous Database Based on Nerual Network [D].Dalian: Dalian University of Technology,2009.)   
[7] 文语欣．基于语义的临床信息交换方法研究[D]．杭州：浙 江大学,2014.(Wen Yuxin.Study on Semantic-based Clinical Information Exchange Method [D]. Hangzhou: Zhejiang University,2014.)   
[8] 郭鑫．基于本体的异构数据集成技术研究与实现[D].北 京：中国航天第二研究院，2008.(Guo Xin.Research and Implementation of Ontology Based Heterogenous Data Integration Technology [D].Beijing:The Second Academy of China Aerospace,2008.)   
[9] UMLS [EB/OL]. [2015-07-25].http://www.nlm.nih.gov/research/ umls/sourcereleasedocs/index.html.   
[10]McCray A T,Srinivasan S,Browne AC.Lexical Methods for Managing Variation in Biomedical Terminologies[C].In: Proceedings of the Annual Symposium on Computer Application in Medical Care.1994:235-239.   
[11]UMLS数据源介绍[EB/OL].[2015-07-26]．http://www. nlm.nih.gov/research/umls/new_users/online_learning/OVR_ 001.html.(Introducition of UMLS Data Source [EB/OL]. [2015-07-26]. http://www.nlm.nih.gov/research/umls/new_users/ online_learning/OVR_001.html.)   
[12]代涛，李亚子，郭珉江，等．新农合数据编码标准建设现状研 究[J]．中国卫生信息管理杂志，2014，11(1):47-50,56.(Dai Tao,Li Yazi,Guo Minjiang,et al.Study on Encoding Standard Application Status of the New Rural Cooperative Medical Data [J].Chinese Journal of Health Informatics and Management, 2014,11(1): 47-50,56.)

# 作者贡献声明：

李亚子：提出研究思路;  
郑见立：设计研究方法，准备实验环境;  
周奕洋：实施实验;  
李国垒：数据收集，论文起草及最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail: li.yazi@imicams.ac.cn。   
[1]李亚子．sbdrug.xlsx.《国家基本医疗保险、工伤保险和生育 保险药品目录(2009版)》： [2]李亚子.gjdrug.xlsx.《国家基本药物目录(2012版)》.   
[3]李亚子.ah34drug.xlsx.安徽省新农合药品目录.   
[4]李亚子.fj35drug.xlsx.福建省新农合药品目录.   
[5]李亚子.hn41drug.xlsx.河南省新农合药品目录.   
[6]李亚子.js32drug.xlsx.江苏省新农合药品目录.   
[7]李亚子.jl22drug.xlsx.吉林省新农合药品目录.   
[8]李亚子.hlj23drug.xlsx.黑龙江新农合药品目录.   
[9]李亚子.hn43drug.xlsx.湖南省新农合药品目录.   
[10]李亚子.nmgl5drug.xlsx.内蒙古新农合药品目录.   
[11]李亚子.allWdrug.国家新农合一体化药品目录(西药).   
[12]李亚子.allCdrug.国家新农合一体化药品目录(中药).

收稿日期:2015-10-21   
收修改稿日期:2016-04-08

# Building a National System for the Reimbursable Prescription Drugs

Li YaziZheng JianliZhou YiyangLiGuolei (Institute of Medical Information, Chinese Academy of Medical Sciences, Beijing 10oo20, China)

Abstract:[Objective]This paper examines the current reimbursable prescription drugs list and creates a national prescription drugs catalog for the new rural cooperative medical system (NCMS).[Methods] We modified the technology framework of the Unified Medical Language System and used the mapping algorithms to aggregate the multi-source list of reimbursable prescription drugs. [Results] We designed the data structure and directory-mapping algorithm,forthe integrated NCMS drugs catalog.[Limitations] More research was needed to analyze interactions among these drugs.[Conclusions] The proposed method helps us develop a list of reimbursable drugs from multiple sources. This new system solves the existing problems of data dictionary aggregation.

Keywords: New rural cooperative medical system Multiple sources dictionaryDrug codingIntegrated mapping