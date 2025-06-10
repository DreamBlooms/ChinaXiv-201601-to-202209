# 基于知识组件的产品设计知识重用方法研究

颜端武魏雪艳赵 飞(南京理工大学信息管理系 南京 210094)

摘要：【目的】促进产品设计活动中设计知识的重用，提高产品设计效率。【方法】根据产品设计活动中知识重用需求，进行知识组件的结构分析，提出基于知识组件的产品设计系统框架，结合计算机组件技术进行知识组件的设计实现研究。【结果】以身管产品为研究对象，构建身管产品的知识组件，设计并实现基于知识组件的身管设计系统。【局限】开发的知识组件具有一定领域局限性，仅适用于相同产品或结构相似的同类产品，知识组件的通用性、系统的移植性和知识的迁移性还有待进一步验证。【结论】基于知识组件的方法可以有效地实现产品设计知识的重用。

关键词：知识组件产品设计知识重用组件技术分类号:TP311G358

# 1引言

产品设计是一个复杂、反复的过程，随着计算机技术的蓬勃发展，呈现出快速化、个性化和知识化的发展趋势。有关研究表明[1-3]，在产品设计中，一个新产品的零件大约有 $40 \% - 5 0 \%$ 是可以从已有产品的零件库中查找，能够实现相同的功能， $30 \% - 4 0 \%$ 的零件只需要在已有的零件上做微小的改进。只有 $1 0 \% - 2 0 \%$ 的零件是需要根据任务从零开始设计的，但是这些重新设计的零件也仅仅表现在结构和形状上与已有零件有差别，从产品所具有的功能、原理等高层信息上分析，它们仍然是对已有设计知识的重用。

产品设计知识重用的研究包含三个方面的内容:知识获取，研究如何有效、全面地获取产品设计过程中包含的各类设计知识；知识表示，研究如何将获取的设计知识以结构化或非结构化的方式存储和表示;知识利用，研究如何使设计知识有效地服务设计过程，提高设计效率和设计质量。知识获取方面，国内外学者提出了基于规则、创新算法、知识挖掘、人工神经网络、设计过程模型、知识建模和知识映射等知识获取方法[4-12]；知识表示方面，提出了诸如产生式规则、语义网络、Petri网模型、贝叶斯网络、神经网络等知识表示方法[13-16]。知识利用是知识重用的最终目的,尽管有学者提出了基于规则、基于案例的知识推理,但大量的设计知识仍然是“管而不用"的状态，为了提高设计知识的重用度，本文研究知识组件在产品设计中的应用实现。

计算机软件组件思想与产品设计知识重用具有先天契合性，本文研究的知识组件将产品设计知识与设计过程紧密结合，使设计知识服务于设计过程，减少设计人员在产品设计过程中收集经验知识的时间，降低时间成本、减少错误、提高设计效率和设计质量的可靠性。

# 2基于知识组件的产品设计知识重用

知识组件是将计算机软件中的组件技术与知识重用相结合的产物，可以将其视为具有一定功能的知识单元。在产品设计领域，知识组件可将设计过程中积累的多种不同类型知识(数据、规则、模板、标准、实例、流程等)以结构化的方式进行封装，在驱动程序控制下以自动化或半自动化的方式接受参数、执行动作并返回结果[17]

# 2.1基于知识组件的知识重用模式

根据知识重用对设计人员的辅助方式，有学者将产品设计知识重用模式归纳为4种：参考知识重用模式、导引知识重用模式、自动知识重用模式和协助知识重用模式[18]

参考知识重用模式，是设计知识在设计过程中为设计人员提供检索、浏览的作用，使设计人员能够快速获取与当前设计任务相关的设计知识，通常采用主动推送和被动检索的方式，为设计人员进行决策提供更好的知识支持。导引知识重用模式，是引导设计人员进行产品设计的知识重用方式，该模式下的设计知识以设计流程为主。自动知识重用模式，是指设计人员可以直接使用已有的设计模型、设计算法，将设计人员从繁琐的重复工作中解放出来，减轻工作负担。

协助知识重用模式，知识库中无法包含所有的设计知识，有些设计知识过于复杂，不适于在知识库中存储，是当设计人员遇到无法解决的问题时，提供能够解决该问题的领域专家的信息。

本文研究的基于知识组件的知识重用结合了参考模式和自动模式，知识组件中不仅封装了设计功能，还封装了与之相关的设计知识，在调用知识组件进行产品设计时，会接收到组件推送的设计知识，帮助设计决策；知识组件作为具有一定功能的组件可以被设计系统重复调用，而且，知识组件运行时还会调用外部算法、工具等。

# 2.2 知识组件的执行过程

在产品设计时，设计任务通过半自动方式访问知识组件控制接口，激活知识组件，而后设计人员通过人机交互界面进行知识组件的参数输入，知识组件接受用户输入后运行知识组件核心(KCC)，KCC执行功能同时调用接口访问第三方软件、知识库或其他知识组件，输出运行结果，在反馈执行结果的前提下，把输出参数返回给人机交互界面或者通过控制接口访问输出数据，具体如图1所示：

![](images/81ce0a0f232909ce6f64d64266f2cbc4ebd2c2b31fa007bcf08cb3163146fc1e.jpg)  
图1知识组件执行过程

# 2.3基于知识组件的产品设计系统

将设计知识以结构化的形式封装成知识组件，设计系统调用知识组件，进行产品设计。界面层是设计系统与设计人员交互的窗口，系统接收设计人员的设计输入，驱动业务层的知识组件进行输入验证，验证不成功则将结果返回到界面层，提醒设计人员修改设计输入，验证成功则继续执行功能并生成结果，生成的设计结果也作为输出返回到界面层；知识组件在执行功能的过程中需要频繁地访问知识层获取设计知识，并将设计结果写人知识库中，具体如图2所示。

参数输人 组件驱动 参数输出  
界面层 + ↑返回结果 调用 返回结果参数验证 功能执行 结果  
业务层 ↑获取知识 获取知识 写入结果（约束、规则） (规则、经验、案例) √  
知识层 产品设计知识库  
设计案例 设计经验 设计规则 设计数据 设计资源

# 3知识组件的结构分析与设计实现

# 3.1 知识组件的结构分析

(1）知识组件构建原则

确定知识组件的结构前，需要明确知识组件的构建原则，如何设计和获取可重用的知识组件是系统开发者要考虑的首要问题。一般来说，在进行知识组件构建和开发时应着眼于以下方面：

$\textcircled{1}$ 知识组件的封装性。组件开发人员可以在知识组件中定义自己的事件，知识组件使用者对复杂的内部细节无需知晓，只需提供输入，就可以得到输出。

$\textcircled{2}$ 合适的知识组件粒度。在功能与实现机制分析权衡的基础上，将设计流程分析设计为适合粒度的知识组件，保持知识组件功能与结构的独立性，从而既可有效地避免知识组件的臃肿，也能提高知识组件的执行效率，并降低其实现的复杂度。

$\textcircled{3}$ 知识组件的重用性。系统开发者在进行系统设计开发前，可以先从已开发的领域知识组件库中选择满足功能的知识组件来组装应用系统，从而加速系统的开发进度、提高系统开发效率，新开发的知识组件也可以在后续新的产品设计中继续使用。

# (2）知识组件分类

知识组件的类型根据系统功能需求的不同而随之变化，一般来说具有界面类、活动类和数据管理类三种类型。本文根据产品设计系统的功能需求，通过抽象产品设计系统各层次的功能模块，将其封装成通用知识组件，最终将知识组件划分为知识访问类知识组件、业务逻辑类知识组件和界面显示类知识组件，每类知识组件由多种功能的组件组成，根据三类知识组件的特点和开发技术，进行知识组件的设计与实现。知识组件的分类结果如表1所示。

表1知识组件分类表  

<html><body><table><tr><td>知识组 件类型</td><td>知识 组件</td><td>知识组件说明</td></tr><tr><td>知识访问</td><td>数据库 访问</td><td>数据库访问是知识组件中基本类型， 涉及数据的存储、检索和更新。</td></tr><tr><td rowspan="2">业务逻辑</td><td>数据 计算</td><td>接受输入参数，进行数据计算，如参 数计算、设计优化等。</td></tr><tr><td>参数 约束</td><td>对设计过程中的参数输入、生成的设 计结果进行实时检验、约束。</td></tr><tr><td>界面表示</td><td>检索 界面 参数 输入 结果 输出</td><td>对设计知识的检索，实现的功能包括 案例检索、知识资源检索等。 设计人员根据设计任务，填写产品设 计所需要输入的参数。 结果输出组件是一种展示运行结果 的载体，包括图表输出、数据输出和 文件输出，服务于设计案例显示、计</td></tr></table></body></html>

(3）知识组件结构

知识组件结构可抽象表示为： $\scriptstyle { \mathrm { K C } } = \{ { \mathrm { K C C } }$ ，DI,UII,AI, CI}。其中:KCC(Knowledge Component Core)是知识组件核心，表示知识内容或封装的知识求解器，是完成用户设计请求的核心工具，根据用户交互接口的启动指令而被启动，通过对知识单元的梳理，将相关的控制规则和经验值与输入数据接口进行关联，并智能判断输入参数的范围和输入参数之间的相互约束关系，将自身执行信息反馈给用户交互接口，还用于将求解出的结果文件提供给输出数据接口。DI(DataInterface)表示数据接口，包括输入数据接口和输出数据接口，输人数据接口获得数据，传递给KCC进行数据处理；输出数据接口获得KCC处理数据，然后返回到用户交互接口。UII(UserInteractionInterface)表示用户交互接口，是用户对知识组件进行设置、操作以及描述相关属性信息的人机交互界面，用户交互接口与KCC 相连接，用于向KCC发送启动指令。AI(AccessInterface)表示访问接口，用于知识组件调用或访问第三方软件、工具和其他知识组件。CI(Control Interface)表示控制接口，外部系统通过它来调用知识组件，驱动知识组件运行。通过知识组件的封装，实现了分析和设计知识过程的形式化，从而使这些知识分析设计过程得以积累、共享和重用。知识组件结构如图3所示。

![](images/cd414f6e69ebb118cdfaf4389b4b90bb6b780077c76e650ce260f418cb663099.jpg)  
图3知识组件结构

# 3.2 知识组件的设计实现

将知识组件功能封装到组件中，而不是通过调用外部程序，减少了运行时间，并且知识组件可以重复利用，减轻系统开发人员的负担，提高系统开发效率，降低系统维护难度。

# (1）知识访问类知识组件

知识访问类知识组件的功能是进行与数据库的数据流控制，既包括实现产品设计系统从数据库获取数据，又包括向数据库写人数据。知识访问类知识组件的功能包括数据库连接配置、数据库查询、数据库插入、删除和更新操作。在产品设计中，访问数据库是常有的操作，在对数据库操作前首先需要进行与数据库的连接，通过建立数据库配置连接组件，将数据库连接操作进行封装，省去了系统开发人员重复编码的繁琐，节省开发时间。

不同功能访问数据库时具有不同输人参数和输出结果，为了最大程度地实现软件重用，本文研究的知识访问类知识组件利用SQL语句传递参数，实现数据的查询、插入、删除和更新操作并返回操作结果，结果包括成功和失败两种情况。其中，数据库检索结果以检索结果集返回，检索方法参数包括SQL语句和字段等参数。不同应用系统通过知识组件的访问方法获得数据库访问接口，知识访问类知识组件的功能方法如表2所示。

# (2）业务逻辑类知识组件

业务逻辑类知识组件所处理的基本对象是通过知识访问类知识组件获得的实体数据或者页面表示类知识组件的用户输入。处理业务逻辑过程会涉及到多个基本对象之间的交互，以及多次进行知识访问类知识组件的交互，因此为了实现一致的对象和完整的处理过程，业务逻辑知识组件内部必须支持事务处理。业务逻辑知识组件的粒度比较大，因此会涉及多个知识组件，同时它向页面表示知识组件提供统一的方法与接口，可以重复应用于多个应用程序中。根据产品设计过程中每个设计活动的知识需求，收集与各设计活动相关的知识资源并将其组合为对应于各设计活动的知识单元模块，数据计算描述字段如表3所示：

表2知识访问类知识组件的功能方法  

<html><body><table><tr><td>访问 类型</td><td>功能方法</td><td>说明</td></tr><tr><td></td><td>public ResultSet getrsbysel (String 根据 stringsql SQL 语 stringsql,[参数类型1,parameterl]，句，返回执行结果集。 查询[参数类型2,parameter2],,[参其中[参数类型n, 数类型 n,parametern],）{…parametern]表示 SQL return ResultSet;}</td><td>语句中执行参数。 根据 stringsql SQL 语</td></tr><tr><td></td><td>[参数类型1,parameterl],[参数类操作，并根据执行结 插入型2,parameter2],,[参数类型 果返回int值。其中[参 n,parametern],.）{return 数类型 n,parametern] int;}</td><td>public intDbInsert(String stringsql，句，进行数据库插入 表示 SQL 语句中执行 参数。 根据 stringsql SQL 语</td></tr><tr><td></td><td>public int DbDelete(String stringsql，句，进行数据库删除 [参数类型1,parameterl],[参数类操作，并根据执行结 删除型2,parameter2],,[参数类型 果返回int值。其中[参 n,parametern],.）{.return 数类型 n,parametern] int;}</td><td>表示 SQL 语句中执行 参数。</td></tr><tr><td></td><td>public intDbUpdate(String stringsql，句，进行数据库更新 [参数类型1,parameterl],[参数类 操作，并根据执行结 更新型 2,parameter2],,[参数类型 果返回 int 值。其中[参 n,parametern],.）{return 数类型 n,parametern] int;}</td><td>根据 stringsql SQL 语 表示 SQL 语句中执行 参数。</td></tr></table></body></html>

表3数据计算描述字段  

<html><body><table><tr><td colspan="2">描述字段 描述</td></tr><tr><td>名称</td><td>数据计算单元名称，如理论强度计算公式</td></tr><tr><td>所属设计部件</td><td>数据计算公式所属的设计部件，如身管部件</td></tr><tr><td>所属设计活动</td><td>数据计算公式所属的设计活动，如理论强度计算</td></tr><tr><td>数据计算公式计算公式的内容</td><td></td></tr><tr><td>输入参数</td><td>用于设计知识组件的输入参数</td></tr><tr><td>输出参数</td><td>用于设计知识组件的输出参数</td></tr><tr><td>计算原理</td><td>阐明数据计算公式的原理</td></tr><tr><td>计算示例</td><td>按示例给出公式的实际示例求解过程</td></tr><tr><td>录入时间</td><td>数据计算公式的录入时间</td></tr><tr><td>录人人员</td><td>数据计算公式的录人人员</td></tr></table></body></html>

以单筒身管的设计为研究对象，单筒身管组件属性包括单筒身管设计任务编号、与炮尾连接方式、与炮尾支腿器连接方式、口径、弹丸重量、初速、参数权重、实例检索结果、药室面积、药室长、弹丸行程长、装药量和药室容积等。设计输人单体属性字段包括实例检索属性、内弹道设计参数、内膛设计参数、高低温压力数据、药室部安全系数、膛线部安全系数、炮口部安全系数和选择钢材钢号等。输入形式包括提供参数输入页面，读取Txt、Excel等文件和数据库数据读取。输出内容包括实例检索结果、实例属性展示、高低温压力曲线表格和理论强度图等，如表4所示：

表4单筒身管知识组件属性表  

<html><body><table><tr><td>步骤</td><td>组件属性定义</td><td>属性说明</td></tr><tr><td>设计任务</td><td>Strsjrwbh Strypwljfs,strypkztqljfs,strkj,strdwzl,strcs,strzdty;valueypwljfs,</td><td>设计任务编号</td></tr><tr><td>实例检索</td><td>valueypkztqljfs,valuekj, valuedwzl,valuecs,valuezdty, Vector vectorinstance</td><td>与炮尾连接方式、与炮尾支腿器连接方式、口径、 弹丸重量、初速、各参数权重和实例检索结果</td></tr><tr><td></td><td>内弹道设计参数strYsmj,strYsc,strDwxcz,strZyl,strYsrj</td><td>药室面积、药室长、弹丸行程长、装药量和药室 容积 药室本体长、连接锥长、圆柱部长、膛线长、导</td></tr><tr><td>内膛设计参数</td><td>strYsbtc,strLjzc,strYzbc,strTxc,strDxbc,strYsdbj, strYsbbtmdbj,strLjzmdbj,strYzbmdbj,strTxmdbj,</td><td>向部长、药室底半径、药室部本体末端半径、连 接锥末端半径、圆柱部末端半径和膛线末端半径</td></tr><tr><td>高低温压力曲线float[]l,float[]p,intlen</td><td></td><td>长度数组、压力数组和点数 药室部安全系数、膛线部安全系数、炮口部安全</td></tr><tr><td>理论强度计算</td><td>strysbaqxs,strtxbaqxs,strpkbaqxs,float[] qdl,float[] qdq, intlen</td><td>系数、长度数组、理论强度数组和点数</td></tr><tr><td>理论外形计算</td><td>strzdtyz,strgcgh,strqdjx,double[] gjd,double[] nj,double[] qd, double[] wj</td><td>最大膛压值、钢材钢号、极限强度、关键点长度 数组、内径值数组、强度值数组和外径值数组</td></tr></table></body></html>

# (3）界面表示类知识组件

界面担负着系统与设计人员之间的对话功能，接受并初步检查设计人员输入，并将参数传递给业务逻辑类知识组件进行业务处理，处理结果返回到用户界面，便于用户查看设计结果和对设计方案进行评定。界面表示类知识组件包括接受设计输入、进行设计输出、功能自动或半自动执行等。设计输入组件用于维护设计对象信息与产品单体元素设置，设计人员根据设计任务与知识需求，填写产品设计所需要输入的参数。设计输出组件是一种展示运行结果的载体，包括图表输出、数据输出和文件输出。由于设计语言的不同，界面表示类知识组件处理方式和设计方法也有所不同，本文采用Swing 进行页面组件的开发设计。通过Swing中间组件设计知识组件，然后将中间知识组件放入顶层组件中，进行界面显示，页面组件显示结构如图4所示：

![](images/70f78e866e85aee0113a9bc2af560eab1231183669863b8fc5868a208968e94b.jpg)  
图4界面结构组件

JFrame通过菜单及菜单点击事件弹出JInternalFrame用于实现子功能，JInternalFrame填充JPanel、JScroollPane 和JTabbedPane 等中间组件。其中,JInternalFrame、JPanel、JScroollPane 和 JTabbedPane等中间容器组件可以根据内容定义可重复使用的界面显示类知识组件。

# 4基于知识组件的产品设计知识重用应用示例

以某机械产品单筒身管部件的方案设计为例，研究知识组件在产品设计知识重用中的应用，结合身管部件的方案设计流程和设计系统实现的需求，对三类知识组件进行设计开发。知识访问类知识组件定义为DbAccess.java，设计系统通过DbAccess.java实现数据库操作访问；业务逻辑类知识组件定义为MonblockDesign.java，封装方案设计各步骤的方法;界面表示类知识组件包括InstanceShower.java表示检索实例显示和方案设计其他步骤页面和各应用系统的JInternalFrame页面，如图5所示。

母pdkm.ProductDesign  
DrawJpaneljava  
InstanceShower_Jpanel.java  
MonoblockDesign.java  
ParameterBrowseofMonoblock_Jpanel.java①SearchResult_Jpanel.java  
UnitofGDWYLQX_Jpanel.java  
UnitofLLQD_Jpanel.java  
UnitofLLQDT_Jpanel.java  
UnitofLLWX_Jpanel.java  
UnitofSearch_Jpanel.java  
UnitofSJJG_Jpanel.java  
UnitofWXTZ_Jpanel.java  
国产品设计如识管理系统 回x  
系统资通管理系统产品读计系统辅件配置助身管设计 叫区设计参款一览 实倒监案 松肃结果内道设计参 药室面积： 车载122营相批度079行长： 当的设计任务编号：1101201411020001快药量： 实列展示药室容积： 屋坐名 屋性值内构参数 主要参 参数权重 身管长度 4145： 与集尾连接方式：连接 □ 0.1 长度 1024连 □ 0.1 商价 出药室底半径： □径：122 0.5 药室部12 613药室部本体末调半径： 共室部43 87.1推术填半径： 弹丸置量：21 0.1 药室部 650柱部末填半径： 药室部d4来端半径 药重部4安全系数 机址：600.5 m/1 0.1 共室部45 85理论外形参 药室部5 661最大壁压：235 R 01 药室御柜教磨能高u 65.8处外径值 205烟口处外轻值 110大压能腔距 507检肃 最大压处直径4 1

![](images/6b32a67dc84c5b8cc62379def4b4b93a94c4a2df6cc209f6784f09abf5b9bf6b.jpg)  
图5页面显示类知识组件的开发  
图6单筒身管设计理论强度计算界面  
图7单筒身管设计实例检索界面

系统运行时首先调用界面表示类知识组件为设计人员与设计系统交互提供窗口，如图6所示：

而后，业务逻辑类知识组件包含了单筒身管方案设计步骤的方法，通过调用MonblockDesign单筒身管知识组件执行相关功能：

publicvoidcountsjrwbh(//根据一定原则对设计任务编号进行编码;  
public void instanceSearch(//根据检索字段进行实例检索;  
privatedouble countInstancesim(//计算实例相似度;  
publicvoid jsllqdO//计算单筒身管理论强度曲线;  
publicvoidllwx_jsgjd(//计算理论外形关键点值;  
publicvoidllwx_jsnjz(//计算理论外形内径值;  
publicvoidllwx_jsqdz(//计算理论外形强度值;  
public void llwx_jswjz(//计算理论外形外径值;  
public intcommit(//单筒身管设计实例存储到数据库。

在身管“实例检索"功能中，通过对设计任务的特征参数和参数权重的选择和设置，能够实现对已有成功设计案例的检索和查看，为设计人员在进行设计时提供决策依据，是参考模式知识重用的体现，如图7所示。

为了解决产品设计知识在产品设计过程中重用度不足，产品设计系统中设计知识固化在程序中重用和移植困难，以及知识重用与软件工程无有效衔接的问题，本文研究了基于知识组件的产品设计，总结出知识组件封装性、合适的粒度、重用性的构建原则；通过身管设计系统的设计实现，验证了知识组件结构和设计实现方法的可行性和有效性；解决了产品设计系统的移植和重用困难的问题，方便设计人员的使用，实现基于知识组件的产品设计知识重用，推动产品的快速化、知识化设计发展

# 参考文献：

# 5结语

[1] Wang F,Mills JJ,Devarajan V.A Conceptual Approach Managing Design Resource [J].Computers in Industry,2002, 47(2): 169-183.   
[2] Bsharah F,Less M.Requirements and Strategies for the Retention of Automotive Product Data [J]. Computer Aided Design,2000,32(2):145-158.   
[3] Hon K KB,Zeiner J.Knowledge Brokering for Assisting the Generation of Automotive Product Design [J].CIRP Annals - Manufacturing Technology,2004,53(1):159-162.   
[4] Prado R P,Garcia-Galan S,Exposito J,et al.Knowledge Acquisition in Fuzzy-Rule-Based Systems with ParticleSwarm Optimization [J]. IEEE Transactions on Fuzzy Systems,2010,18(6):1083-1097.   
[5] Wang J,Wu YP,Liu X N,et al.Knowledge Acquisition Method from Domain Text Based on Theme Logic Model and ArtificialNeuralNetwork[J].ExpertSystemswith Applications,2010,37(1):267-275.   
[6] He X D,Wu JW,ShiFQ,et al.Apply Fuzzy Case-Based Reasoning to Knowledge Acquisition of Product Style[C]. In: Proceedings of IEEE 1Oth International Conference on Computer-Aided Industrial Design & Conceptual Design. IEEE,2009:383-386.   
[7] Castellanos V,AlbiterA,HernandezP,etal.Failure Analysis Expert System for Onshore Pipelines.Part-I: Structured Database and Knowledge Acquisition [J].Expert Systems with Applications,2011,38(9):11085-11090.   
[8]周翼，张晓冬，郭波．面向产品创新设计的网络知识获取 及挖掘[J]．现代制造工程,2010(6):20-23.(Zhou Yi, Zhang Xiaodong，Guo Bo．Product Innovation Design-Oriented Network Knowledge Acquisition and Mining [J].Modern Manufacturing Engineering,2010(6): 20-23.)   
[9]陈友玲，肖莹姣．面向产品设计的隐性知识获取关键技术 研究[J]．科技进步与对策，2011，28(19):121-124.(Chen Youling, Xiao Yingjiao. Research on Key Technology of Tacit Knowledge Acquisition for Product Design [J]. Science & Technology Progress and Policy,2011,28(19):121-124.)   
[10]苏财茂．产品设计 Know-how 知识获取模型研究[J].装备 制造技术,2009(7): 45-46.(Su Caimao.Research on Capture Model of Know-how Knowledge for Product Design [J]. Equipment Manufacturing Technology, 2009(7): 45-46.)   
[11]谷建光，张为华，解红雨．实例与经验相结合的产品设计 知识获取技术[J]．计算机集成制造系统，2008，14(3): 417-424.(Gu Jianguang， Zhang Weihua， Xie Hongyu. Knowledge Acquisition Based on Combination of Product Casesand Domain ExpertsExperience[J]. Computer Integrated Manufacturing Systems,2008,14(3): 417-424.)   
[12] 孙伟,袁长峰,高天一，等.基于 ANN 支持产品设计过程 的知识获取方法研究[J]．大连理工大学学报，2007，47(2): 190-195.(Sun Wei， Yuan Changfeng，Gao Tianyi，et al. Research on Approach of Knowledge Acquirement Based on Artificial Neural Network and Supporting Design Process [J]. Journal of Dalian University of Technology，2007,47(2): 190-195.)   
[13] Bueno T,Hoeschl H C，Bortolon A，et al.Knowledge Engineering Suite:A Tool to Create Ontologies for Automatic Knowledge Representation in Knowledge-Based Systems [C]. In: Proceedings of the 4th International Conference (EGOV 2005)，Copenhagen，Denmark．Springer Berlin Heidelberg, 2005: 249-260.   
[14] Stanojevic M, Vranes S.Knowledge Representation with Soul [J].Expert Systems with Applications,2007,33(1): 122-134.   
[15]李志琴，赵宏安，赵凤起，等．基于语义网络的推进剂配 方设计知识表示[J]．含能材料，2014，22(4):542-547.(Li Zhiqin, Zhao Hong'an, Zhao Fengqi，et al. Knowledge Representation of Propellant Formula Design Based on Semantic Network [J]. Chinese Journal of Energetic Materials,2014,22(4):542-547.)   
[16]王力，李怀英．基于本体的产品设计知识表示研究[J]．计 算机技术与发展,2014,24(9):115-119,145.(WangLi,Li Huaiying. Research on Knowledge Representationfor Product Design Based on Ontology[J]. Computer Technology and Development,2014,24(9):115-119,145.)   
[17]郝佳，杨海成，闫艳，等．面向产品设计任务的可配置知识 组件技术[J].计算机集成制造系统，2012，18(4):705-712. (Hao Jia,Yang Haicheng，Yan Yan，et al.Configurable Knowledge Component Technology Oriented to Product Design Tasks[J].Computer Integrated Manufacturing Systems,2012,18(4): 705-712.)   
[18]郝佳.产品设计知识管理与重用关键技术研究[D].北京：北 京理工大学，2014.(Hao Jia.Study on Product Design Knowledge Management and Reuse Techniques [D]. Beijing: Beijing Institute of Technology,2014.)

# 作者贡献声明：

颜端武：提出研究课题，修订论文;  
魏雪艳：提出研究思路，设计研究方案，撰写论文;  
赵飞：提出研究思路，设计研究方案，完成实验。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:yanwu_nju $| \textcircled { a } 1 6 3 . \mathrm { c o m } .$ 0  
[1]颜端武，魏雪艳，赵飞.DbAccess.java.知识访问类知识组件.[2]颜端武，魏雪艳，赵飞.MonblockDesign.java.单筒身管业务逻辑知识组件.  
[3]颜端武，魏雪艳，赵飞.InstanceShower.java.界面表示知识组件.  
[4]颜端武，魏雪艳，赵飞.DesExamples.dbf.单筒身管设计实例数据.

收稿日期:2015-11-17  
收修改稿日期:2016-02-29

# Knowledge Reuse in Component-based Product Design

Yan DuanwuWei XueyanZhao Fei (Department of Information Management,Nanjing Universityof Science and Technology,Nanjing 210o94, China)

Abstract: [Objective]To promote the knowledge reuse in product design and improve its eficiency.[Methods]First, we analyzed structure of the knowledge components in acordance with the knowledge reuse requirements of product design activities. Second,we proposed a framework for product design system based on knowledge components. Finally we implemented the reuse of knowledge components with the help of related computer programs.[Results] We constructed the knowledge components for barel products,and then established adesigning system based on the new knowledge components.[Limitations]The new system had certain limits,and could only be applied to the same or similar products.More research is needed to examine theuniversalityof the knowledge components,the adaptability of the system，as well as the transferability of knowledge.[Conclusions] The new system based on knowledge components could effectively reuse the product design knowledge.

Keywords: Knowledge component Product designKnowledge reuse Component technology

# IMLS资助哈佛大学Perma.cc扩展其网络资源存储工具

美国博物馆和图书馆服务协会(Institute of Museum and Library Services,IMLS)已决定资助哈佛大学法学院图书馆创新实验室以进一步发展其Perma.cc工具以对抗链接无效。

IMLS 资助哈佛大学法学院图书馆创新实验室70多万美元，以供其与Berkman Center for Intemet& Society，以及130多个合作图书馆进行合作，以大规模地持续地扩展 Perma.cc工具以对抗所有学术领域中的链接无效现象。

链接无效是指在一个网页中的超链接或是在一个具体文档中指向网站的或是线上资源的超链接已经改变或是不再有效。这是一个严重的问题，它影响了在法律、医药、科学和技术领域超过 $70 \%$ 的学术文章，阻碍了对于数字学术记录的追踪和评价工作。该项目基于法律学术领域的解决方案和方式方法，将会添加到Perma 图书馆联盟中去，并且寻求在其他领域中链接无效问题的缓解方法。

“Perma.cc 是哈佛大学法学院图书馆创新实验室的一个智慧发明，她也是给法律研究世界的一个开创性的礼物,”哈佛法学院的法学教授 Martha Minow 说道。“我很高兴，这一项目将帮助其他领域的学者享受和律师以及法律学者一样的利益，这些利益是通过Perma.cc 获得的，即保持重要的链接永久性可用。”

“链接无效是一个广泛渗透到所有学术领域中的一个问题，”馆藏建设和数字计划副主任，哈佛图书馆创新实验室主任Kim Dulin说道。“IMLS项目能帮助扩展我们的链接无效解决方案到法律以外的其他学科上去，这一解决方案最初被设计用来解决法律领域中的链接无效问题。同时，还将为我们提供一个解决商业领域链接无效问题的机会。我们很感激IMLS 提供给我们扩展Perma 解决方案的机会。”

(编译自: htp:/today.law.harvard.edu/harvards-perma-cc-receives-grant-expand-tools-saving-sources-web-2/)

(本刊讯)