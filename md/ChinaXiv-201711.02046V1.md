# 高校图书馆微信服务平台的设计与实现以浙江工业大学图书馆为例

# 佘静涛

(浙江工业大学图书馆 杭州 310032)

摘要：【目的】通过设计和开发微信服务平台，为图书馆用户提供方便快捷的个性化服务，同时也为系统管理员提供便利。【应用背景】目前多数高校图书馆微信服务平台中自定义菜单生成和改动都需要修改程序源代码，且没有网络系统管理功能。【方法】通过创新性地利用 Java 反射机制，使用微信公众平台的 API接口，利用 Java编程语言和Hibemate数据库框架，设计和开发适用于高校图书馆的微信服务平台。【结果】通过该平台，拥有权限的管理员不仅可以管理网络系统，而且可以实时地改变微信自定义菜单的名称、个数、排列顺序、响应动作类型和绑定的函数。【结论】通过使用和测试表明本应用能够极大地提高用户满意度和微信管理员的工作效率。

关键词:微信公众平台 API接口 Hibernate Java 反射机制分类号：G250.7

# 1引言

微信公众平台是腾讯公司在微信的基础上新增的功能模块，通过这一平台，个人和企业都可以打造一个微信公众号，并实现与特定群体通过文字、图片、语音的全方位沟通、互动[1]。微信用户不仅可以通过发送语音、文字、图片、视频等实现双方的在线交流，而且还可以通过微信公众平台群发推送消息、提供相关业务服务系统的对接，从而提升用户体验。

微信公众平台对于高校图书馆服务工作具有以下优势：

(1）微信已经拥有相当大的用户群，特别是在高校人群中的使用率非常高，这就使得高校图书馆可以通过微信公众平台扩大高校图书馆服务工作的影响力[2]。(2）微信公众平台能够给高校图书馆带来更加真实稳定的客户群，能够充当图书馆和读者之间的桥梁、纽带的角色，以此提高消费者的口碑传播力度。另外，微信是双向个性化交流，图书馆可以根据信息反馈改进工作方式，实现服务最优化[3]。

(3）微信的成本非常小，对用户和高校图书馆来说都具有极佳的经济优势。(4）微信具有信息传播的便利与及时优势，这对于信息时代来说尤为重要。(5）微信公众平台提供了强大的API接口[4]，二次开发难度不高。这就使得经费有限的高校图书馆可以结合本馆的具体情况，在实践中考虑如何创新地、有效地应用微信公众平台，为广大用户提供便利、高效的服务。

国内已经有多家高校图书馆开通了微信公众账号，并且利用微信公众平台提供的API接口进行二次开发，搭建自己的微信服务平台。但是大多数高校图书馆的微信服务平台没有网络系统管理功能，对接一个业务服务系统或者改动微信自定义菜单就得修改多处源代码这使得系统管理员工作量大幅度增加。

从图书馆微信公众平台的研究成果来看，关于高校图书馆微信公众平台现状分析和服务创新的研究成果比较多，例如杨艳妮等[5选取6所高校图书馆，对比分析其微博、微信平台的服务功能、内容资源等，以讨论其微服务的传播效果及优化。杜辉等通过对211工程"高校图书馆微信公众平台的调研，阐述高校图书馆微信学科服务的现状。关于微信服务平台的设计与开发的研究成果也不少，例如罗涛搭建图书馆本地服务器，利用微信公众平台实现东南大学图书馆资讯、个人借阅消息、FAQ、书目以及文献等内容的查询。但是针对微信服务平台的网络系统管理服务和微信自定义菜单的可视化配置的研究几乎没有，所以高校图书馆如何充分利用微信公众平台设计和开发一个更加合理高效的微信服务平台，依旧是一个值得研究的课题。

# 2微信服务平台的设计

本文以浙江工业大学图书馆为实践对象，利用其现有的业务服务系统和数据资源，充分考虑图书馆用户和系统管理员的需求，设计微信服务平台。

# 2.1 系统设计思路

微信公众账号具有两种运营模式：编辑模式和开发模式，开发模式较于编辑模式最大的优势在于通过编写代码和搭建服务器，可以实现网站、数据库等业务服务系统与微信公众平台完美对接，正是这种开发模式真正造就了强大的微信公众平台。因此，本文确立了“以开发模式实现图书馆微信服务平台"的技术路线。

浙江工业大学图书馆微信服务平台根据用户需求与图书馆信息管理系统、课程预约系统、存包柜系统、Web服务器检测系统和图书馆Web系统进行对接。在此基础上，除了实现业务服务系统的个性化服务外，还创新性地引入网络系统管理服务，并在平台后端中实现微信自定义菜单的可视化配置。系统核心部分的设计思路如下：

(1）个性化服务：为了提高开发者的效率，微信服务平台使用Java反射机制实现个性化服务的快捷添加。开发者添加新的个性化服务只需要两步：

$\textcircled{1}$ 在系统核心业务类中添加响应函数，响应函数负责与业务服务系统接口对接和通信，对于不提供接口的业务服务系统需要进行二次开发，使其提供符合平台要求的接口。

$\textcircled{2}$ 在平台后端的微信自定义菜单设置中绑定该响应函数。

通过以上两步，微信服务平台就可以根据用户发送的消息利用Java反射机制动态调用核心业务类中的响应函数进行处理。

(2)网络系统管理：微信服务平台通过在业务服务系统上部署Agent(代理)程序实现网络系统管理的功能。Agent(代理)是针对不同业务服务系统定制开发的Web应用程序，该程序提供API接口并在业务服务系统启动后自动运行。微信用户通过身份认证后，具有管理员权限的用户可以通过微信服务平台调用Agent接口对业务服务系统进行管理。

(3）微信自定义菜单可视化配置：通过微信服务平台后端，对自定义菜单进行设置，设置的内容包括自定义菜单的名称、个数、排列顺序、响应动作类型和绑定的菜单资源(菜单资源根据响应动作类型分为地址链接和响应函数名称两种)。将菜单配置保存至数据库并同时更新微信服务平台系统中的自定义菜单静态变量(自定义菜单静态变量的数据结构为 HashMap,用于系统动态加载响应函数)。

微信服务平台系统架构如图1所示：

![](images/68a9a276473ecfe4bd542090b0e58fa89cc9f2a71a216589cb4f19be0dd15117.jpg)  
图1微信服务平台系统架构

微信服务平台的交互流程如下：

(1）移动设备用户通过Http协议将消息发送给微  
信服务器。(2）微信服务器将消息处理封装成XML或JSON  
数据格式转发给微信服务平台。(3）微信服务平台将消息解析后调用相应的业务  
服务系统接口或者Agent 程序接口，随后将返回的消

息封装成XML或JSON数据格式返回给微信服务器。

(4）微信服务器将解析后的消息转发给用户。

# 2.2 功能需求设计

浙江工业大学图书馆微信服务平台设计的目的在于不仅为师生用户提供方便快捷的个性化服务，同时也为系统管理员提供服务和便利。微信服务平台具体实现的功能模块如图2所示：

![](images/b8d876163169fa095032e4eb0ca349742f54906c42c80c76c128084eb72bb737.jpg)  
图2浙江工业大学图书馆微信服务平台功能模块

微信服务平台前端和后端依靠微信自定义菜单连接，通过平台后端的自定义菜单的可视化配置将响应函数的名称与微信自定义菜单的名称、次序，关键词等信息一一对应并保存在数据表中。利用Java反射机制，在系统运行的时候根据平台前端用户输入的关键词查找响应函数名称并动态调用。网络系统管理和微信管理的功能模块说明如下：

# (1）网络系统管理

$\textcircled{1}$ 存包柜管理：通过该功能，系统管理员可以重启存包柜服务。$\textcircled{2}$ 网站服务器管理：通过该功能，系统管理员可以重启图书馆主页服务器上的Apache Tomcat 服务和MySQL数据库。$\textcircled{3}$ 用户存包柜查询：通过该功能，系统管理员可以查询他人的存包柜记录。$\textcircled{4}$ 服务器状态查询：通过该功能，系统管理员能够很快发现状态异常的Web服务器。Web服务器的名称和地址可以在平台后端中添加。

# (2)微信管理

微信自定义菜单的可视化配置：通过该功能能够直接修改微信公众平台自定义菜单的名称、次序、数量、响应动作类型(响应动作类型有两种：点击菜单跳转到链接；点击菜单触发响应函数)和响应函数，而不需要修改源程序。系统管理员添加新的自定义菜单响应函数，只需要在系统核心业务类中实现方法，然后在后台管理系统的自定义菜单里设置绑定即可，这大大提高了开发效率。

# 3微信服务平台的实现

在充分考虑服务器操作系统兼容性问题的基础上，利用微信公众平台的API接口，使用Java编程语言和Hibernate数据库框架开发微信服务平台，服务平台的数据库采用MySQL关系型数据库,Web页面使用Ajax(异步JavaScript和XML)技术。

# 3.1 关键技术

(1)Hibernate 数据库框架

Hibernate是一个基于Java的开源的持久化中间件，对JDBC做了轻量的封装。采用ORM映射机制，负责实现Java对象和关系数据库之间的映射，它把SQL语句传给数据库，并且把数据库返回的结果封装成对象，其内部封装了JDBC访问数据库的操作，并向上层应用提供了面向对象的数据库访问API[8]。Hibernate以对象的形式操作数据，开发者不需要关心数据库种类，更换数据库只要修改配置文件，提高了程序的开发效率。

# (2)Java反射机制

Java反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法；这种动态获取信息以及动态调用对象的方法的功能称为Java语言的反射机制[9。反射机制的强大之处在于它能够很方便地创建灵活的代码，这些代码可以在运行时装配，无需在组件之间进行源代码链接。反射机制是通过java.lang.Class类来实现的，该类保存了对象的运行时类型标识，只要获取了Class对象，就能够知道这个类所有的属性和方法，对于任意一个对象，都能够调用它的任意一个方法。

# 3.2平台前端关键功能实现

浙江工业大学图书馆微信服务平台前端的业务流程如图3所示，微信服务平台自动根据用户的查询关键词查找对应的响应函数，并由函数决定是否操作数据库，是否调用业务服务系统接口或者Agent程序接口，如果没有找到对应的响应函数，微信服务平台就向用户返回一条出错的提示信息。

![](images/95f0af48e0183622534a0c541987106719594addd9ba95a3428dddcf29dbf62b.jpg)  
图3微信服务平台前端业务流程

平台前端中有以下关键功能需要实现:

(1）个性化服务消息处理

微信服务平台个性化服务中不同的消息类型由不同的函数来处理，例如接收到的用户消息属于文本类型则调用 private static String processRequestTextMessage(ReqTextMessagereqtextMessage)函数处理,该函数利用Java反射机制，调用静态的HashMap类型变量获取响应函数信息，函数的核心代码如下：

/接收文本信息,生成回复消息  
private static String processRequestTextMessage(ReqTextMessage reqtextMessage) {  
//CoreMethod核心业务类包含了所有的响应函数，响应函数负责与业务服务系统接口通信  
//Menus是一个静态的HashMap类型变量，系统初始化的时候从数据库读取微信自定义菜单的配置Iterator iter $\ O =$ CoreMethod.Menus.entrySet().iterator();String key=";boolean flag $\vartriangle$ false;while (iter.hasNextO){Map.Entry entry $\ O =$ (Map.Entry)iter.next();key $\ c =$ (String) entry.getKey(;//判断自定义菜单中的关键词是否跟用户消息中的文本信息一致if (choose.equals(key)) {flag=true;break;}if(flag){//利用Java反射机制，调用与关键词对应的响应函数Class ${ \mathrm { < } } ? { \mathrm { > } }$ cls $\vDash$ Class.forName("lib.zjut.weixin.service.CoreMethod");Method method=cls.getMethod(CoreMethod.Menus.get(choose).getResource(),ReqBaseMessage.class);//将响应函数处理结果封装成XML数据格式  
tmpStr $=$ MessageUtil.MessageToXML((RespBaseMessage)method.invoke(cls,(ReqBaseMessage)reqtextMessage));}else{//返回帮助信息  
tmpStr=MessageUtil.MessageToXML(CoreMethod.getHelp(reqtextMessage));}return tmpStr;  
}其他消息类型的处理函数结构类似。  
(2）业务服务系统接口

(ApacheAxis2是一种WebService 框架)连接具有WebServices接口的业务服务系统。针对没有提供开放接口的业务服务系统，需要分别为它们编写一个能够读取业务服务系统相关数据并将数据格式转化成JSON格式的API接口，以便响应函数的获取。

(3）微信信息翻页

微信信息翻页功能用于业务服务系统返回信息量比较大、手机屏幕无法完全显示的情况下，该功能利用数据表rule保存当前关键词和当前页码来实现。数据表rule的字段设置如表1所示：

表1rule表字段设置  

<html><body><table><tr><td>Column Name</td><td>Datatype</td><td>NOT NULL</td><td>Default Value</td><td>Comment</td></tr><tr><td>open_id</td><td>VARCHAR(45)</td><td>√</td><td></td><td>用户在微信公众号中的唯一标识</td></tr><tr><td>action</td><td>VARCHAR(45)</td><td></td><td>null</td><td>用户发送的关键词1</td></tr><tr><td>keyword</td><td>VARCHAR(45)</td><td></td><td>null</td><td>用户发送的关键词2</td></tr><tr><td>page</td><td>INTEGER</td><td></td><td>0</td><td>当前页码</td></tr></table></body></html>

例如浙江工业大学图书馆有两套不同的存包柜系统，分别标识为CH、PF。用户在使用存包柜查询功能时，系统用open_id记录用户的唯一标识，使用action字段记录“存包柜查询"这个关键词，用keyword 字段记录"CH"或者"PF"，用page 字段记录当前的页码。

# (4)网络系统管理

微信服务平台前端通过部署在业务服务系统上的Agent程序实现了查询用户存包柜记录、重启业务系统相关服务和查询Web服务器的运行状态网络系统管理功能。具体实现步骤如下：

$\textcircled{1}$ 对微信用户的身份进行认证，只有系统管理员才能使用网络系统管理功能。Agent程序首先解析用户查询消息，获取消息中的OpenID。然后通过OpenID查询微信服务平台数据库完成对微信用户身份的认证。

$\textcircled{2}$ 具有系统管理员权限的用户可以调用Agent程序，并返回处理结果。

1）查询用户存包柜记录：Agent程序调用存包柜系统查询接口，并将数据返回给微信服务平台。微信服务平台解析封装后通过微信公众平台发送给微信用户。

2）重启业务系统相关服务：为业务系统编写一个重启服务的批处理文件，Agent程序调用该批处理文件实现服务的重启，并返回运行结果。

3）查询Web服务器运行状态：Agent程序返回一个Web应用程序的地址链接，该Web应用程序的实现笔者已在文献[10]中进行阐述。

浙江工业大学图书馆微信服务平台前端的实现效果如图4所示：

G16:42 6 G16:43 6 G14:402 浙江工业大学图书馆 1 浙江工业大学图书馆 1 X 浙江工业大学图书馆-数据库..管理员快捷查询： 1.取消绑定回复#学工号'查询用户存包柜 2.绑定信息 有记录(朝晖) 4系统管理回复\*学工号查询用户存包柜 1.重启存包柜服务（朝晖） 首页|读者服务|数字资源|本馆概况|公共查询|特色服务|参考记录（屏峰) 2.重启网页服务 咨询|ZADL门户|教材管理|常用链接|3.答复用户留言其他功能，即将推... 【ZADL搜索】回复帮助'或者?'显示菜单 管理员快捷查询： 全部 图书期刊站内详情请访问移动图书馆 回复'#学工号'查询用户存包柜 立即搜索系统开发：技术部余静涛 记录(朝晖) 回复\*学工号查询用户存包柜 启动检测关闭检测 （间隔：1分钟）检测已启动...记录(屏峰)序号数据库名称 数据库链接 数库#04347 其他功能，即将... 1国研网 http://www.drcnet.com.cn/ ok回复'帮助'或者?显示菜单 2 产品样本 http://gpd.sunwayinfo.com.cn/ok用户余静涛最近存包记录-朝晖 详情请访问移动图书馆 3北大法宝网 http://www.pkulaw.cn/ ok校区（最多显示12条）： 系统开发：技术部余静涛 4独秀学术搜索htp://edu.duxiu.com/ ok\*记录1：16.04.17 16:38 5维普期刊网 http://qikan.cqvip.com/ 0k-03柜46箱-取包无物6中国知网 http://210.32.205.36/kns55/ ok3录2:1601711:13 42 7 浙江工业大学 http://www.lib.zjut.edu.cn ok\*记录3:16.04.1711:12 8 中国知网 http://210.32.205.36/kns551/ NotFound-03柜46箱-存包无物 重启网页服务成功！首页|读者服务|数字资源|本馆概况|公共查询|特色服务|参考IZADL门户|教材管理|常用链接|馆内交流国 ） O 十 围 1 图书馆.Allriqh

# 3.3 平台后端的实现

平台后端包括管理员管理、数据库管理、微信用户管理、绑定用户管理、微信自定义菜单管理、消息内容管理、在线咨询管理、用户留言管理、常见问题管理等功能模块，其中最为复杂的是微信自定义菜单功能模块，它实现了微信自定义菜单的可视化配置。其解决方案如下：

(1）在MySQL数据库中建立Menu数据表，结构

如表2所示。

(2）制作平台后端的微信自定义菜单可视化配置页面，页面使用Ajax技术。自定义菜单的一级菜单设置界面如图5所示。二级菜单的设置页面如图6所示，菜单类型是微信自定义菜单的响应动作类型，菜单资源是通过Java反射机制获取的响应函数名称或者是需要跳转的链接地址，关键词是微信用户调用对应响应函数所要输入的关键词。

表2Menu 表字段设置  

<html><body><table><tr><td>Column Name</td><td>Datatype</td><td>NOT NULL</td><td>Default Value</td><td>Comment</td></tr><tr><td>id</td><td>INT(10)</td><td>√</td><td>null</td><td>菜单项的唯一标识</td></tr><tr><td>father_id</td><td>INT(10)</td><td>√</td><td>0</td><td>菜单项的父菜单标识，如果没有父菜单则该字段为0</td></tr><tr><td>islink</td><td>TINYINT(1)</td><td>√</td><td>0</td><td>保存自定义菜单响应动作类型，链接类型该字段值为 1，函数类型值为0</td></tr><tr><td>resource</td><td>VARCHAR(200)</td><td></td><td>null </td><td>函数名或者链接地址</td></tr><tr><td>keyword</td><td>VARCHAR(45)</td><td></td><td>null</td><td>文本类型的查询关键词</td></tr><tr><td>voice</td><td>VARCHAR(45)</td><td></td><td>null</td><td>语音类型的查询关键词(通过微信语音识别录入)</td></tr><tr><td>Menu_describe</td><td>VARCHAR(150)</td><td></td><td>null</td><td>菜单项的描述</td></tr><tr><td>name</td><td>VARCHAR(45)</td><td>√</td><td></td><td>菜单项的名称</td></tr><tr><td>order</td><td>INT(10)</td><td>√</td><td>0</td><td>菜单项的顺序号</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">菜单名称：</td><td></td><td rowspan="2">排序号：</td><td></td><td rowspan="2">添加</td></tr><tr><td></td><td>4</td></tr></table></body></html>

![](images/d522bd3ff230f9eb4960de1b0cd67c3f3f0042bbbd46108282682b3240df6ad5.jpg)  
图5一级菜单设置界面  
图6二级菜单设置界面

(3）在添加完一级菜单和二级菜单并保存至数据库后，需要调用微信自定义菜单生成函数createMenu,该函数使用JSONObject插件先将数据表Menu中的数据格式化为微信生成自定义菜单所需要的JSON数据格式，然后加载自定义菜单并返回错误代码，最后更新系统中的自定义菜单静态变量。

# 4结语

浙江工业大学图书馆微信服务平台于2013年10月推出测试版，2014年8月正式投入使用。该平台投入使用后广受师生的好评，并得到一些学生团体的关注。截至2016年1月，图书馆微信公众号已有关注用户10000余人，绑定用户5000余人。

本文以浙江工业大学图书馆为例，利用馆内的信息管理系统、数据库和Web应用系统等信息资源，设计与开发图书馆微信服务平台，旨在利用移动通信的便利性为图书馆用户和系统管理员提供个性化、高效的服务，同时也希望与其他高校图书馆分享平台的构建方法和使用经验，让更多高校图书馆利用微信公众平台，搭建自己的微信服务平台。

# 参考文献：

[1]陈盈．微信公众平台及其在图书馆移动服务中的应用与研 究[J]．图书馆学研究，2013(20):71-75.(Chen Ying.The Application and Research of WeChat Public Platform in Library Mobile Service [J].Research on Library Science, 2013(20): 71-75.)   
[2] 邓巍．崭露头角的图书馆微信服务[J].图书馆情报论坛, 2013(5):38-41.(Deng Wei. The Budding Libary WeChat Service [J].Library & Information Science Tribune,2013(5): 38-41.)   
[3] 郭春玲，郑悦．在图书馆开展微信营销的思考[J].公共图 书馆,2013(3):35-37.(Guo Chunling,Zheng Yue.Reflections on Developing Micro Message Marketing in Library [J]. Public Library Journal,2013(3):35-37.)   
[4] 微信公众平台[EB/OL].[2016-01-15].http://mp.weixin.qq. com/wiki/home/index.html.(WeChat Public Platform [EB/OL]. [2016-01-15]. http://mp.weixin.qq.com/wiki/home/index.html.)   
[5] 杨艳妮，明均仁．高校图书馆微服务建设现状与优化[J]. 图书馆学研究,2015(19):8-14.(Yang Yanni,Ming Junren. The Current Situation and Optimization of the Construction of Academic Library in Micro-services [J].Research on Library Science,2015(19): 8-14.)   
[6] 杜辉，刘晓，袁百成．基于微信公众平台的高校图书馆学 科服务创新[J].图书情报工作,2015,59(6):41-45.(Du Hui, Liu Xiao,Yuan Baicheng.The Innovation of Subject Service Based on WeChat Public Platform in University Libraries [J]. Libraryand Information Service,2015,59(6):41-45.)   
[7] 罗涛．图书馆微信公众平台的建设与研究[J].现代图书情 报技术,2015(1):96-100.(Luo Tao.Construction and Research of Library WeChat Public Platform [J].New Technology of Library and Information Service,2015(1):96-100.)   
[8] Hibernate [EB/OL].[2016-01-17].http://www.howzhi.com/ course/2055/.   
[9] JAVA 反射机制[EB/OL].[2016-01-18]．http://baike.baidu. com/view/1865203.htm. (Java Refection Mechanism [EB/OL]. [2016-01-18].http://baike.baidu.com/view/1865203.htm.)   
[10]余静涛，王醒宇．数字资源Web 应用服务器的失效检测[J]. 计算机系统应用,2014,23(7):218-222.(She Jingtao,Wang Xingyu.Failure Detection of Digital Resources Web Server [J].Computer Systems & Applications,2014,23(7): 218-222.)

# 利益冲突声明：

作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:sjtxp@zjut.edu.cn。[1]余静涛.Manage_menu.jsp.微信自定义菜单可视化配置的代码.[2]余静涛.InterfaceUtil.java.微信自定义菜单生成函数createMenu的代码.

收稿日期:2016-03-25  
收修改稿日期:2016-04-27

# WeChat Service Platform for Academic Library: Case Study of Zhejiang University of Technology Library

She Jingtao (Library of Zhejiang University of Technology, Hangzhou 31oo32, China)

Abstract: [Objective]This study tries to provide beterservices to academic libraryusers and improve the efficiencyof library system administrations with the help of a new WeChat service platform. [Context] At present, generating and modifyig customized menu of the WeChat service platform for academic libraries requireus to edit the source codes, which contain no network administration functions.[Methods]The proposed model used Java's refection mechanism, and utilized API technologies,Java programing and Hibernate database framework to develop a WeChat service platform for academic libraries.[Results] The new platform helped administrators manage network system,and edit customized menu's features in real time.[Conclusions] The new WeChat service platform improves user experience and administration efficiency significantly.

Keywords:WeChat API interface Hibernate Java refection mechanism