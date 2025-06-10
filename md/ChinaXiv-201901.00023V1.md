# 基于HBase的细粒度访问控制方法研究

黄良强，朱焱，陶霄(西南交通大学 信息科学与技术学院，成都 611756)

摘要：为增强 HBase 的安全访问控制能力，提出一种针对 HBase 的细粒度访问控制方法。该方法通过修改优化HBase 源码，扩展访问控制权限、重写访问控制器达到细粒度访问控制的目的。归纳出应用于HBase的RBAC模型，内建数据库角色以解决权限扩展后细粒度权限管理难度增大的问题。通过设计实验测试用例，验证了提出的细粒度访问控制方法能更全面地保护HBase数据，解决了原有方法带来的权限过粗的问题，降低了数据可能被恶意地执行修改、删除等操作所带来的巨大安全风险。

关键词：HBase数据库；访问控制；细粒度权限；数据库角色中图分类号：TP309.2 doi: 10.19734/j.issn.1001-3695.2018.08.0648

Research on fine-grained access control method based onHBase

Huang Liangqiang, Zhu Yan, Tao Xiao (SchoolofInformation Science&Technology,Southwest Jiaotong University,Chengdu 6l1756,China)

Abstract: Inorder to enhance the accesscontrol abilityofHBase,this paper proposed a fine-grained accesscontrolmethod for HBase.This methodachieves the purposeoffine-grained accesscontrol by modifying and optimizing the HBase source code,extending the access control permissons,and rewriting the AccessControllr.Moreover,this paper generalizes the RBAC model that aplied in HBase,and use built-in database roles to solve the problem thatfine-grained permisions management becomes more dificult after extending permisions.Bydesigning experimental testcases,itis verifiedthatthe proposed fine-grained acesscontrol method can protect HBase data more comprehensively.This paper solves the problem that excesive permissons caused by the original method,and reduces the huge security risk caused by data may be maliciously performing operations such as modification and deletion, etc.

Key words:HBase; access control; fine-grained permissions; database role

# 0 引言

NoSQL数据库因其对海量数据有着高效的管理能力，广泛应用于各类大数据生产场景，例如，阿里巴巴集团早在2011年就开始把HBase投入到上千台节点的集群中用于淘宝历史交易记录、蚂蚁安全风控等大数据的存储。然而，其安全性问题也被业界广泛关注。大多数NoSQL数据库只是提供简单的数据保护支持，无法满足实际生产中对数据安全性能的需求，特别是对较敏感数据的保护。例如，在医院大数据应用场景中，病人的姓名、疾病史等敏感信息是需要被重点保护的数据对象。HBase 作为一种NoSQL 列式存储数据库技术，同样存在以上安全性问题，因此，研究如何增强HBase的访问控制能力成为一种迫切需求。

关系型数据库在访问控制技术理论与应用方面更加成熟完备。占据着数据库引擎排行榜[1]前三的关系型数据库Oracle、MySQL、MicrosoftSQLServer都采用基于角色的访问控制（RBAC）技术，实现了表级、列级等细粒度对象，插入、修改、删除等细粒度操作两方面的访问控制。而新诞生的 NoSQL 数据库类型多样，例如，列式存储的 HBase、Cassandra，文档存储的MongoDB、Couchbase，键值对存储的 Redis、Memcached，图存储的 Neo4j、Microsoft Azure

CosmosDB。不同类型的NoSQL数据库采用不同的架构模型，实现访问控制的方法也不尽相同。

MongoDB采用RBAC技术，分为内建数据库角色和用户自定义角色两种。内建角色提供了数据库系统中常用的权限集合，权限粒度较粗，一个权限包括一系列操作；自定义角色可实现细粒度权限授权，但是权限操作范围只是控制在数据库或集合级别，没有进一步深入对集合中字段的访问控制。MicrosoftAzureCosmosDB使用主密钥和资源令牌进行身份验证，资源令牌与数据库中的权限相关联，确定用户是否对数据库中的应用程序资源拥有访问权限（读写、只读或无访问权限），应用程序资源包括集合、文档、附件、存储过程、触发器和用户定义函数，身份验证时，使用资源令牌允许或拒绝访问资源[2.3]。

HBase 提供六种简单的权限[4]，分别是Superuser、Admin(A)、Create(C)、Write(W)、Read(R)、Execute(X)。Superuser作为超级用户，可执行任意数据库操作;因此可授予普通用户的只能是另外五种权限。通过分析HBaseACLMatrix和实验验证发现，如果某个用户拥有Write权限，则该用户可以执行如put、delete、append、increment等写操作。在实际生产应用中，若要控制用户只能写入数据而不能删除数据，按照HBase现有的粗粒度权限授权则无法满足这样的操作控制需求。针对以上HBase的问题，本文的研究目的和意义在于解决HBase原有粗粒度权限控制方法的弊端，实现细粒度权限控制，增强HBase的安全访问控制能力。

关于NoSQL数据库细粒度访问控制方法的研究，Colombo等人[5]提出了一种通用的针对NoSQL数据库的基于属性的访问控制（ABAC）方法，该方法借助 $\mathrm { \ s Q L + + }$ 技术[6]实现，在Couchbase4.5平台上验证了所提出方法的可行性。然而， $\mathrm { \ s Q L + + }$ 仅支持如MongoDB、Couchbase、JSONiq、Hive等NoSQL或NewSQL数据库，不支持HBase；此外，他们也未说明在不支持 $\mathrm { \ s Q L + + }$ 的 NoSQL数据库平台上如何实施提出的细粒度访问控制方法。文献[7]存在许多与文献[5]相同的问题，尽管作者声称提出的方法适用于NoSQL数据库，却未解释如何在NoSQL数据库平台上实现。

文献[8]在MongoDB中集成使用了RBAC、ABAC和基于内容的访问控制技术，把MongoDB 定制成为一个私有的数据库。文献[9]中，蔡平在研究HBase的安全性时，提出通过修改HBase源码来拓展访问控制权限的方法是可行的，但是作者仅仅任意设定了三个权限加以验证提出的方法的可行性，没有给出如何划分细粒度权限的依据，也没有探讨可能出现的问题并给出解决方案。文献[10]中，Lai等人在保留HBase现有访问控制权限的条件下，按照HBaseShell命令的读、写等类别为依据划分细粒度权限，采用XACML技术来表达用户角色授权信息，通过定制观察者类型的协处理器[1I]来实现提出的细粒度访问控制方法。文献[10]的不足之处在于划分细粒度权限的依据不够严谨，没有考虑划分的细粒度权限之间是否存在权限依赖关系等问题。

本文针对HBase 提出的细粒度访问控制方法更全面完整，主要包括：a）分析了HBase 现有的访问控制方法，理清 Shell命令类别、Shell命令与JavaAPI的调用关系，给出细粒度权限划分依据;b）通过归纳应用于HBase的RBAC模型和内建数据库角色，解决了细粒度权限划分造成的权限管理难度增大的问题;c）通过修改优化源代码，扩展权限列表和重写访问控制器，实现所提出的细粒度访问控制方法;d)设计测试用例，验证所提出的细粒度访问控制方法的有效性。

# 1 细粒度访问控制方法设计

# 1.1HBase访问控制框架

HBase访问控制框架主要包括如下三个模块：

a)操作接口模块,它是HBase 提供给用户执行数据库操作和授权/撤权操作的接口，有Shell命令和JavaAPI两种客户端方式。

b)访问控制模块，用于拦截用户的操作请求。执行授权/撤权操作时，该模块与权限存储模块交互，写入/删除授权信息；执行数据库操作时，该模块用于判定用户是否拥有执行操作请求的权限。

c)权限存储模块，用于存储用户和角色的授权信息。HBase采用访问控制列表（ACL）的方式实现，ACL的表模式如表1所示。HBase 缺省使用名称为default 的命名空间（Namespace，等同于关系型数据库管理系统中的数据库），使用 $@$ 字符区分是命名空间级别授权还是命名空间下的低级别授权，也使用 $@$ 字符区分是对用户授权还是对角色授权。

表1ACL的表模式  
Table1Table schema of ACL   

<html><body><table><tr><td>行键</td><td>数据</td></tr><tr><td><@命名空间命名空</td><td>列族：{<用户@角色>[列族[,列]]:'权限集合</td></tr><tr><td>间：表|表></td><td>}</td></tr></table></body></html>

# 1.2权限控制级别与权限判定算法

HBase提供五种权限控制级别，如图1所示。五种级别呈现包含关系，优先级从全局到列依次降低，低级别自动继承上级的授权。例如：授予用户 $A$ 在命名空间NS上有“读”权限，则 $A$ 在该NS下的所有树节点上都有“读”权限。

![](images/9d9cad175140b0a4d204e7e36ddfe80f6d1e67fc02518b2de59d0e221328a148.jpg)  
图1权限控制级别与优先级  
Fig.1Permission control level and priority

用户提交操作请求后，HBase向集群节点分发操作请求并执行。在操作请求执行前，访问控制器会捕获操作请求，并判定该用户是否具有执行操作请求的权限。

权限判定算法描述如下：

参数定义：ul=用户U角色组； $\ n s =$ 命名空间名称；tabl $\scriptstyle { \underline { { \gamma } } } =$ 表名称；cf=列族名称；cq=列名称；action=执行操作请求所需的权限。

输入参数列表：<ul[,ns[,table[,cf[,cqll],action>  
输出：true 表示权限判定通过；抛出权限异常信息表示判定失败，  
色执行操作请求。  
for i=O to ul.length do全局级权限匹配，参数列表<ul[i],action>  
if 全局级匹配成功 then结束循环，返回 true  
end if  
ifns 不为空 then命名空间级权限匹配，参数列表<ul[i],ns,action>if 命名空间级匹配成功 then结束循环，返回 trueend if  
end if  
if table不为空then表级权限匹配，参数列表<ul[i],ns,table,action>if 表级匹配成功 then结束循环，返回 trueend if  
end if  
if cf不为空 then列族级权限匹配，参数列表<ul[i],ns,table,cf,action>if 列族级匹配成功then结束循环，返回 trueend if  
end if  
if cq 不为空 then列级别权限匹配，参数列表<ul[i],ns,table,cf,cq,action>if 列级匹配成功 then结束循环，返回 trueend if  
end if  
for

抛出权限异常信息

算法主体中，权限匹配规则是根据输入参数在ACL表中查找是否存在相同的授权信息，有则匹配成功，否则匹配失败。

# 1.3细粒度权限设计

API是HBase提供给用户原子性的操作方式，Shell命令是基于API编写的功能封装。例如，Shell命令truncate的功能是清空表内数据，保留表的属性。为完成该任务，Shell命令的执行步骤如下：

a)执行获取表描述信息操作。

b)执行判断表是否停用操作。

c)如果表已停用则执行清空表内数据操作；否则终止任务执行。

d)执行删除表操作。

e)按照步骤a）获取得到的表描述信息执行重建表操作。其中，每一步操作调用一个API，如步骤a）调用getTableDescriptor，该API对应的Shell命令为describe。命令truncate调用了5个API，可见Shell命令会调用一个或多个API来完成对应的任务。此外，Shell命令没有覆盖所有的API，例如用于关闭集群的stopMaster、shutdown等API。如果按照文献[10]中对照shell命令划分细粒度权限，即一个shell命令划分为一种权限的方法，所划分出的细粒度权限可能无法控制相关API，细粒度权限划分不完整以及部分细粒度权限存在依赖关系，例如，权限'truncate'会依赖'describe'、drop'和'create'权限，从而造成HBase安全隐患。

针对细粒度权限划分不完整、部分细粒度权限之间存在依赖关系的问题，本文提出一种按API进行细粒度权限划分的方法，从API的角度实现细粒度访问控制，保证权限划分完整、权限之间不存在依赖关系。

首先参照SQL语句中数据定义语句（DDL）、数据操纵语句（DML）等命令集合，把会造成HBase 安全隐患的API按照其功能类型进行归类，共8种API类别，如表2所示。其目的在于能根据API类别更加集中地管理归类前凌乱的API。

表2HBase 中API类别Table2API types in HBase  

<html><body><table><tr><td>类别</td><td>API集合</td></tr><tr><td>DML</td><td>appendAfterRowLock,append,delete,getOp,increment, checkAndDelete,put,checkAndPut,</td></tr><tr><td>DDL</td><td>modifyTable,addColumn,modifyColumn,deleteColumn, createTable,disableTable,deleteTable,</td></tr><tr><td></td><td>enableTable,....</td></tr><tr><td>Security</td><td>grant,revoke,getUserPermissions</td></tr><tr><td>Snapshot</td><td>snapshot,listSnapshot,cloneSnapshot,restoreSnapshot, deleteSnapshot</td></tr><tr><td>Namespace</td><td>createNamespace,deleteNamespace,modifyNamespace, getNamespaceDescriptor, listNamespaceDescriptors</td></tr><tr><td></td><td>move,assign,unassign,regionOffline,balance,</td></tr><tr><td rowspan="3">Tools</td><td>balanceSwitch,flushTable,compact,openRegion,</td></tr><tr><td>closeRegion,split,shutdown,stopMaster,mergeRegions,</td></tr><tr><td>stopRegionServer,....</td></tr><tr><td>Quotas</td><td>setUserQuota(global level),setUserQuota(namespace</td></tr><tr><td></td><td>level),setNamespaceQuota, setTableQuota....</td></tr><tr><td>Endpoint</td><td>invoke</td></tr></table></body></html>

为保证划分的细粒度权限在实际应用中更具合理性，对表2进一步分析，可把各类别中相近功能的API归结为一种

具体操作，例如，DDL类别中的modifyTable、addColumn、modifyColumn、deleteColumn可归结为ALTER操作。本文在表2的基础上共归结出8种类别，46种具体操作，如表3所示。

Table 3API types and concrete operation sets   

<html><body><table><tr><td>类别</td><td>具体操作集合</td></tr><tr><td>DML</td><td>APPEND,DELETE,GET,INCR,TRUNCATE,SCAN, PUT</td></tr><tr><td>DDL</td><td>ALTER,CREATE,DESCRIBE,DISABLE,ENABLE, LIST,DROP</td></tr><tr><td>Security</td><td>GRANT,REVOKE,USER_PERMISSION</td></tr><tr><td>Snapshot</td><td>LIST_SNAPSHOT,CLONE_SNAPSHOT, RESTORE_SNAPSHOT,DELETE_SNAPSHOT, SNAPSHOT</td></tr><tr><td>Namespace</td><td>CREATE_NAMESPACE,DROP_NAMESPACE, ALTER_NAMESPACE,DESCRIBE_NAMESPACE, LIST_NAMESPACE</td></tr><tr><td>Tools</td><td>MOVE,ASSIGN,UNASSIGN,OFFLINE,SPLIT, BALANCER,COMPACT,SHUTDOWN, BALANCE_SWITCH,STOP_MASTER,FLUSH, MERGE_REGION,WAL_ROLL,BULKLOAD, OPEN_REGION,CLOSE_REGION,</td></tr><tr><td>Quotas</td><td>STOP_REGION_SERVER QUOTA</td></tr><tr><td>Endpoint</td><td>EXECUTE</td></tr></table></body></html>

所提出的细粒度权限划分依据是：将造成HBase安全隐患的API归为多个类别，每个类别划分为多个具体操作，一种具体操作划分为一种权限。根据这种划分思想，共划分为8种权限类别，46种细粒度权限，部分权限类别与权限集合如表4所示。

表4中，授权级别单元格值G表示全局级、N表示命名空间级、T表示表级、CF表示列族级、CQ表示列级。

表3API类别与具体操作集合  
表4部分权限类别与权限集合  
Table 4Partial permission types and permission sets   
(a)DML权限类别   

<html><body><table><tr><td colspan="3">(a)DML permission type</td></tr><tr><td>权限名称</td><td>权限控制的功能</td><td>授权级别</td></tr><tr><td>APPEND</td><td>单元格拼接新值</td><td>G|N|T|CF|CQ</td></tr><tr><td>DELETE</td><td>删除单元格数据</td><td>G|N|T|CF|CQ</td></tr><tr><td>GET</td><td>获取某行记录</td><td>G|N|T|CF|CQ</td></tr><tr><td>INCR</td><td>计数器单元格值做加减</td><td>G|N|T|CF|CQ</td></tr><tr><td>PUT</td><td>新增记录</td><td>G|N|T|CF|CQ</td></tr><tr><td>SCAN</td><td>扫描表数据</td><td>G|N|T|CF|CQ</td></tr><tr><td>TRUNCATE</td><td>清空表数据</td><td>G|N|T</td></tr><tr><td></td><td>(b)DDL权限类别</td><td></td></tr><tr><td></td><td>(b) DDL permission type</td><td></td></tr><tr><td>权限名称</td><td>权限控制的功能</td><td>授权级别</td></tr><tr><td>ALTER</td><td>更改表/列族定义</td><td>G|N|T|CF</td></tr><tr><td>CREATE</td><td>创建表</td><td>GN</td></tr><tr><td>DESCRIBE</td><td>获取表描述信息</td><td>G|N|T</td></tr><tr><td>DISABLE</td><td>停用表</td><td>G|N|T</td></tr><tr><td>DROP</td><td>删除表</td><td>G|N|T</td></tr><tr><td>ENABLE</td><td>启用表</td><td>G|N|T</td></tr><tr><td>LIST</td><td>列出所有表</td><td>G|N|T</td></tr></table></body></html>

<html><body><table><tr><td colspan="3">(c) Security 权限类别</td></tr><tr><td></td><td>(c) Security permission type</td><td>授权级别</td></tr><tr><td>权限名称 GRANT</td><td>权限控制的功能 授予用户权限</td><td>G|N|T|CF|CQ</td></tr><tr><td>REVOKE</td><td>撤销用户权限</td><td>G|N|T|CF|CQ</td></tr><tr><td>USER_PERMISSION</td><td>列出用户权限</td><td>G|N|T|CF|CQ</td></tr></table></body></html>

# 1.4调整授权命令语法

HBase 提供grant方法授予用户权限，使用revoke方法撤销用户权限。授权命令语法格式如图2所示，而撤权命令语法格式为图2中grant替换为revoke，并去掉权限集合项。

授权操作 权限集合 列族↑ <grant <User|@Role>,<Permissions>[,<Table|NS:Table|@NS>[,CF[,CQl]]√用户或角色！ 命名空间或表 列

命令语法中使用 $@$ 字符表示对角色授权，也使用 $@$ 字符表示在命名空间级别授权。HBase原有的五种权限，分别用字符'A''C''R''W''X'表示，图2中的权限集合项是五种权限的组合，例如：'CR'表示授予用户CREATE和READ权限。

本文扩展设计的细粒度权限个数较多，字符方式表示会使得权限组合更复杂，意义不明确。为此，本文采用权限全称，逗号隔开的方式，例如：DELETE,CREATE,DROP'表示授予用户DELETE、CREATE和DROP权限。

# 2 应用于HBase的RBAC模型

本文1.3节扩展的细粒度权限带来了权限控制更具体，覆盖面更广的优势，也造成了当用户数量增大，权限管理难度增大的问题，本文深入研究了HBase引入的RBAC模型，并通过内建数据库角色集中管理扩展后的细粒度权限。

# 2.1HBase 用户组机制

HBase用户组机制依赖于Hadoop 的用户组机制,Hadoop的用户组机制依赖于Linux/UNIX操作系统的用户组机制。把用户组视为角色，则构建起HBase中用户与角色的所属关系。因此，基于HBase用户组机制实现RBAC模型，需在Linux/Unix操作系统级别设置用户和用户组信息。

HBase获取到用户信息之后，根据用户名在操作系统中获取到所属的用户组集合作为该用户的角色组。

# 2.2 HBase 中的 RBAC 模型

参照RBAC96模型[12]，结合2.1节对HBase用户组机制的分析，本文归纳出如图3所示的应用于HBase的RBAC模型。

![](images/bc01374be28368e47ad6d46f62ddf435022ad897aaf807d0d3c34437437e9f29.jpg)  
图2HBase 授权命令语法格式  
Fig.2Authorization command syntax format of HBase   
图3应用于HBase 的RBAC模型Fig.3RBAC model that applied in HBase

关于图3的RBAC模型的定义如下：

四元组(用户，角色，权限，会话)，即 $U , R , P , S$ ：

权限分配 $P A \subseteq P \times R$ ，角色与权限是多对多的关系；

用户分配 $U A \subseteq U \times R$ ，用户与角色是多对多的关系；

user: $S \to U$ ,每一个会话 $s _ { i }$ 映射到一个单用户 $u s e r ( s _ { i } )$ ·roles: $S \to 2 ^ { R }$ ,每一个会话 $s _ { i }$ 映射到一个角色子集$r o l e s ( s _ { i } ) \subseteq \{ r | ( u s e r ( s _ { i } ) , r ) \in U A \}$ ，并且会话 $s _ { i }$ 具有权限$\mathbf { U } _ { r e r o l e s ( s _ { i } ) } \{ p | ( p , r ) \in P A \}$ ·

通过角色可把用户与权限联系起来，会话是一个用户对多个角色的映射，即一个用户激活某个角色子集，用户权限是激活的各角色权限的并集[12.13]。

# 2.3内建数据库角色

关系型数据库MicrosoftSQLServer是最成熟的数据库产品之一，它在访问控制模块中能做到细粒度权限的访问控制，采用了RBAC模型，通过内建数据库角色集中管理细粒度权限。MongoDB通过内建数据库角色来管理常用的权限集合。本文参考SQLServer和MongoDB在实际生产中积累的数据库权限管理经验，内建如表5所示的数据库角色，共五种角色类型。

表5内建数据库角色  
Table 5Built-in database roles   

<html><body><table><tr><td>角色</td><td>描述</td><td>权限</td></tr><tr><td>db_owner</td><td>拥有数据库中所有权限</td><td>命名空间级别所有权 限</td></tr><tr><td>db_securityadmin</td><td>授予、回收角色/用户权GRANT,REVOKE,</td><td>USER_PERMISSION</td></tr><tr><td rowspan="2">db_ddladmin</td><td>限 在数据库中运行任何</td><td></td></tr><tr><td>DDL指令</td><td>DDL类别所有权限</td></tr><tr><td>db_datawriter</td><td>添加、删除或更改数据</td><td>PUT,DELETE, APPEND,INCR</td></tr><tr><td>db_datareader</td><td>读取所有数据</td><td>GET, SCAN, GET_COUNTER</td></tr></table></body></html>

# 3 功能实现与测试

# 3.1实验环境

实验在3台PC机搭建的集群上进行，环境配置如下：Ubuntu 16.04 LTS，HBase1.2.6，Hadoop 2.7.6，Zookeeper3.10.4，JDK1.8。集群为主从节点架构，包含1个主节点，2个从节点。

# 3.2改写源码集成细粒度访问控制功能

HBase授权/撤权功能是向ACL表写入/删除授权信息。如图4所示是授权操作执行流程。源码修改优化需完成以下内容：

a)在权限列表中，增加2.3节划分的细粒度权限。HBase源码中使用Permission类定义枚举类型变量Action来保存权限列表，使用Byte数据类型保存权限值。

b）重写授权请求封装接口，保证扩展的细粒度权限能成功写入到授权请求中。为缓解客户端的压力，HBase 把访问控制器部署在集群的每个节点上。客户端接收到授权命令后按照授权内容封装请求，然后通过HBase的二层查询技术找到操作请求执行的节点，将操作请求发送到该节点后，访问控制器将捕获操作请求，判定是否有GRANT权限，进而控制是否执行授权操作。

c）重写访问控制器。访问控制器继承自协处理器，提供如prePut、preDelete等预处理方法拦截数据库操作put、delete等，因此可在prePut、preDelete 等方法中执行权限判定算法，达到细粒度权限访问控制的目的。

# 3.3测试方法与测试结果

本文的测试工作包括三项目标:a)测试2.3节设计的所有细粒度权限；b)测试所设计的细粒度权限在各授权级别上是否能真实有效地达到访问控制的目的；c)测试低优先级能否继承上级的授权。

本文编写客户端程序调用HBase的API进行测试。

![](images/763f0bd1329d53a14c6a2450613ddcad08ecdd273b9e366cfd01fc979d8de53c.jpg)  
图4授权操作执行流程  
Fig.4Authorized operation execution process   
图5权限判定失败返回异常信息

3.3.1测试|

以PUT权限为例，PUT权限用于控制数据库新增记录操作，API名称为put和checkAndPut。操作定义：op1表示用户 $u I$ 调用putAPI向命名空间 $n s I$ 中表 $t I$ 的列族 $_ { c f I }$ 的列color新增一条记录。

测试方法描述如下：

a)不授予u1任何权限，u1不拥有任何角色。执行opI操作，系统应抛出如图5所示的异常信息，否则访问控制失败。

b)授予 $u I$ 在全局级别上有PUT权限，执行opl操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

c)撤销 $u I$ 在全局级别的PUT权限，授予 $u I$ 在命名空间ns1级别有PUT权限。执行op1操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

d)撤销 $u I$ 在命名空间 $n s I$ 的PUT权限，授予 $u I$ 在命名空间 $n s I$ 中表 $t I$ 级别有PUT权限。执行op1操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

e)撤销 $u I$ 在命名空间 $n s I$ 中表 $t I$ 级别的PUT权限，授予 $u I$ 在命名空间 $n s I$ 中表 $t I$ 的列族cfI级别有PUT权限。执行op1操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

f)撤销 $u I$ 在命名空间 $n s I$ 中表 $_ { t I }$ 的列族cfI级别的PUT权限，授予 $u I$ 在命名空间 $n s I$ 中表 $t I$ 的列族cfl的列color级别有PUT权限。执行op1操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

g)撤销 $u I$ 所有权限，分配 $u I$ 拥有角色rolel。用户授权替换为角色授权，重复a)\~f)测试过程。

org.apache.hadoop.hbase.security.AccessDeniedException: Insufficientpermissions(user=ul,scope $\scriptstyle \cdot = n s I$ :tl,family $\scriptstyle \prime = c f I$ :color, params=[table $\mathbf { \sigma } : =$ ns1:tlmily $\mathbf { \sigma } = \mathbf { \sigma }$ cfl:color],cion ${ } _ { = P U T _ { , } }$ 0

Fig.5Permission judge failed to return exception information

如表6所示为执行op1操作时，PUT权限判定通过与否，$P$ 表示通过， $R$ 表示拒绝。

Table 6PUT permission control result   

<html><body><table><tr><td></td><td>全局</td><td>命名空间</td><td>表</td><td>列族</td><td>列</td></tr><tr><td>无PUT权限</td><td>R</td><td>R</td><td>R</td><td>R</td><td>R</td></tr><tr><td>有PUT权限</td><td>P</td><td>P</td><td>P</td><td>P</td><td>P</td></tr></table></body></html>

同理，对于DDL权限类别中的CREATE 权限，其功能是控制创建表操作。表7所示为用户 $u I$ 在命名空间 $n s I$ 中执行创建表 $t 2$ 操作时，CREATE权限判定通过与否， $P$ 表示通过， $R$ 表示拒绝。

表6PUT权限控制结果  
表7CREATE权限控制结果  

<html><body><table><tr><td></td><td>全局</td><td>命名空间</td></tr><tr><td>无CREATE 权限</td><td>R</td><td>R</td></tr><tr><td>有CREATE权限</td><td>P</td><td>P</td></tr></table></body></html>

采用以上方法可对DML、DDL、Security、Snapshot、Namespace、Tools和Quotas权限类别进行测试，测试步骤根据权限的授权级别做相应调整，例如：对于CREATE权限，只需测试a) $\mathrm { \Pi ^ { \ s c } }$ )和g)步骤。

# 3.3.2测试I

Endpoint权限类别只包含原有的EXECUTE权限。本节测试只针对EXECUTE权限进行，该权限用于控制用户是否可以执行终端类型[1的协处理器。

操作定义：op2表示用户 $u 2$ 执行终端类型的协处理器，用于计算命名空间 $n s I$ 中表 $_ { t I }$ 的记录行数。

终端类型的协处理器需要与HBase的域服务器（RegionServer）直接通信，本节测试编写了RPC接口，以及基于RPC接口的客户端和服务端程序。

测试方法描述如下：

a)不授予 $u 2$ 任何权限， $u 2$ 不拥有任何角色。执行op2操作，系统应抛出类似如图5所示的异常信息，否则访问控制失败。

b)授予 $u 2$ 在全局级别上有EXECUTE权限，执行op2操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

c)撤销 $u 2$ 在全局级别的EXECUTE权限，授予 $u 2$ 在命名空间 $n s I$ 级别有EXECUTE权限。执行op2操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

d)撤销 $u 2$ 在命名空间 $n s I$ 级别的EXECUTE权限，授予$u 2$ 在命名空间 $n s I$ 中表 $t I$ 级别有EXECUTE权限。执行op2操作，不抛出权限异常信息则表示访问控制成功，否则访问控制失败。

e)撤销 $u 2$ 所有权限，分配 $u 2$ 拥有角色role2。用户授权替换为角色授权，重复a)\~d)测试过程。

表8所示为执行op2操作时，EXECUTE权限判定通过与否， $P$ 表示通过， $R$ 表示拒绝。

Table 7CREATE permission control result   
表8EXECUTE 权限控制结果  
Table8 EXECUTE permission control result   

<html><body><table><tr><td></td><td>全局</td><td>命名空间</td><td>表</td></tr><tr><td>无EXECUTE权限</td><td>R</td><td>R</td><td>R</td></tr><tr><td>有EXECUTE权限</td><td>P</td><td>P</td><td>P</td></tr></table></body></html>

# 3.3.3测试结果与优势分析

本文按照上述测试I和测试II的测试过程完成全部权限的测试工作，测试结果表明，本文设计改进的细粒度访问控制方法解决了HBase原有粗粒度访问控制方法的弊端，细粒度化后的权限能真实有效地达到对用户操作请求进行访问控制的目的，提升了集群和数据库的安全性。

文献[10]的测试结果暴露出权限之间存在包含的关系，如拥有SCAN权限不仅可以执行scan 操作也可以执行get操作。与文献[10]相比，本文设计的测试方法从权限控制级别和用户角色两个方面进行了细粒度权限测试，测试内容更全面，证明了本文所划分的细粒度权限之间不存在依赖和包含的关系，全方位验证了本文设计的细粒度访问控制方法的优越性。

# 3.4时间性能分析

本文实现的细粒度访问控制方法是基于HBase已有的协处理器技术，通过重定制访问控制器达到控制的目的，没有额外增加控制操作过程，因此不会对HBase造成额外的时间性能开销。

# 4 结束语

本文在深入研究HBase 源码的基础上，对HBase的访问控制方法进行了详细的分析，针对存在的粗粒度权限问题，给出细粒度权限划分的依据，解决了文献[9,10]没有给出划分依据或划分依据不严谨的问题。分析了HBase中的RBAC模型，通过内建数据库角色解决了细粒度权限管理难度增大的问题，能更集中管理扩展后的细粒度权限。通过扩展权限列表、重定制访问控制器，能真实有效地达到细粒度权限授权和控制的目的，有效降低了由于HBase原有访问控制方法导致的权限过大而可能造成的数据安全风险。本文提出的细粒度访问控制方法不会对HBase造成额外的性能影响。

关于NoSQL数据库访问控制方法的研究，目前国内外很多学者聚焦基于属性的访问控制（ABAC）方法，凸显出了ABAC方法在大数据应用场景下灵活多变的优势。关于如何在HBase集成使用ABAC方法是下一步研究的重点。此外，关于HBase行级的访问控制方法研究也极具应用价值。

# 参考文献：

[1]DB-Engines．DB-engines ranking [EB/OL].[2018-O7-15]．https:// db-engines.com/en/ranking.   
[2]Paz JRG.Microsoft Azure Cosmos DB revealed [M].Apress,2018.   
[3]Microsoft.Azure Cosmos DB 数据库安全性 [EB/OL].(2017-11-15) [2018-07-15]. https://docs.microsoft.com/zh-cn/azure/cosmos-db/ database-security.   
[4]Apache HBase Team.Apache HBase reference guide,version 1.2.6 [EB/OL]. (2017) [2018-07-15]. http://hbase.apache.org/book.html.   
[5]Colombo P,Ferrari E.Towards a unifying attribute based access control approach for NoSQL datastores [C]//Proc of the 33rd IEEEI nternational Conference on Data Engineering.Piscataway,NJ:IEEE Press,2017: 709-720..   
[6] Ong K W,Papakonstantinou Y，Vernoux R.The SQL+Unifying semi-structured query language,and an expressiveness benchmark of SQL-on-Hadoop，NoSQL and NewSQL databases [J].Computer Science,2014.   
[7]Longstaff J，Noble J.Attribute based access control for big data applicationsbyquery modification[C]//Proc ofthe2nd IEEE International Conference on Big Data Computing Serviceand Applications.Washington DC:IEEE Computer Society,2016: 58-65.   
[8]Colombo P,Ferrari E. Towards virtual private NoSQL datastores [C]// Proc of IEEE International Conference on Data Engineering. Piscataway,NJ: IEEE Press,2016:193-204.   
[9]蔡平．基于Hadoop 的 NoSQL 数据库安全研究[D].上海:上海交通 大学，2O13.(Cai Ping.Research on security of NoSQL database on Hadoop [D]. Shanghai: Shanghai Jiao Tong University,2013.）   
[10] Lai Yanyan，Qian Quan．HBase fine grained access control with extended permissions and inheritable roles [C]//Proc of IEEE/ACIS International ConferenceonSoftwareEngineering， Artificial Intelligence,NetworkingandParallel/distributedComputing. Washington DC:IEEE Computer Society,2015: 1-5.   
[11] Lai Mingjie,Koontz E,Purtell A.Coprocessor introduction [EB/OL]. (2012-02-01）[2018-07-15].https:/blogs.apache.org/hbase/entry/ coprocessor_introduction.   
[12] SandhuR S,Coyne EJ,Feinstein HL,etal.Role-based access control models [J]. Computer,1996,29(2): 38-47.   
[13]何海云，张春，赵战生．基于角色的访问控制模型分析[J].计算机 工程,1999,25(8):39-41.(He Haiyun, Zhang Chun,Zhao Zhansheng. Analysis of role-based access control model [J]. Computer Engineering, 1999,25(8): 39-41. )   
[14] Colombo P,Ferrari E. Enhancing MongoDB with purpose based access control [J]. IEEE Trans on Dependable & Secure Computing,2017,PP (99): 1.   
[15] Shermin M.An access control model for NoSQL databases [D].London, Ontario,Canada: University of Western Ontario,2013.