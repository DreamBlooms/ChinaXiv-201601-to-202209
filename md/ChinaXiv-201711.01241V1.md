# 基于位置感知的图书馆主动信息服务系统设计

邓志文都平平 穆亚凤(中国矿业大学图书馆徐州 221008)

摘要：【目的】建设具有位置感知的智慧型图书馆，为读者提供即时信息服务。【应用背景】读者在图书馆的不同位置对服务的要求不一样，同时在同一位置不同类型读者对服务的期望也不同，系统要能够预测读者即时需求并提供主动服务。【方法】设计一种基于位置感知的主动信息差异服务系统体系框架，采用WiFi和GPS 定位技术实现对读者的无缝位置感知，并根据读者角色分类生成差异信息实时推送给读者。【结果】读者通过安装APP 端能在图书馆不同位置得到不同的服务信息。【结论】位置服务为图书馆预测用户即时需求，改善用户体验提供了一种有效途径。

关键词：位置感知WiFi定位差异服务分类号：G250

# 1前言

移动互联网、智能手机与GPS技术的应用普及带动了基于位置服务(LBS)的发展。图书馆的位置感知服务是打造现代化智慧型图书馆的一个重要部分。近年来，图书馆界在不断通过改善软硬件环境来提升服务质量，努力打造现代化的馆舍，其中开展手机端的移动服务已经成为各馆服务创新的主要方面，很多图书馆已经开发了移动图书馆APP，在微信平台开通公众号服务，在各种社交网络如人人网、新浪微博提供咨询服务等，但这些应用都没有将位置感知服务融入其中。

本文给出了一种基于位置感知的图书馆主动信息差异服务系统，该系统将WiFi室内定位和GPS定位技术相结合，并通过位置和角色信息分类表生成差异信息，能以位置感知预测用户的即时需求实现差异服务，在一定程度上提高了图书馆的服务质量，改善了读者的体验。

# 2现状分析及技术思路

# 2.1 位置感知服务现状

基于位置服务理念的兴起让图书馆的工作人员开始探讨位置感知服务在图书馆的应用模式。文献[1]结合WiFi室内系统的应用对感知服务在博物馆应用的可行性和有效性进行分析；文献[2]从室内定位角度对图书馆的移动服务进行探究，给出了很多有指导性的服务策略；文献[3]结合WiFi室内定位技术，提出一种基于本体和位置感知的图书馆书籍推荐模型，为提供具有位置感知的个性化书籍推荐服务提供了思路。总结已有位置感知信息服务研究成果，其目的都是希望读者在图书馆的不同区域能够享受不同的信息服务内容，如一个读者在进入图书馆大厅时向其发送欢迎和祝福的信息，当他进入阅览室时可以推送阅览室当前占座情况，而当该读者是教师或者高年级学生时显然对这种占座情况的信息服务不太感兴趣，此时有关阅览室的新书情况可能更贴合读者的需求。可见不同类型的读者在同一位置其对服务的预期内容也存在差异，基于此本文设计了一种基于位置感知的图书馆主动信息差异服务系统。

# 2.2 位置感知

位置感知服务的核心是位置的获取，需要实现室内的实时定位，目前室内定位技术主要有：蓝牙室内定位[4]、超宽带室内定位[5]、ZigBee室内定位[]、WiFi室内定位[、超声波定位[等。不同的定位技术优缺点不一样，且适应的环境也不同，对各种定位技术进行对比，如表1所示：

表1室内定位技术对比分析  

<html><body><table><tr><td>分类</td><td>覆盖范围 (m)</td><td>精度 (m)</td><td>稳定 程度</td><td>成本</td><td>移动 应用</td><td>缺点</td></tr><tr><td>蓝牙</td><td>10</td><td>1-5</td><td>较差</td><td>较高</td><td>容易</td><td>距离短，易被干扰</td></tr><tr><td>超宽带</td><td>20</td><td>6-10</td><td>好</td><td>高难</td><td></td><td>造价高</td></tr><tr><td>ZigBee</td><td>100</td><td>1-2</td><td>较好</td><td>较高难</td><td></td><td>易被干扰</td></tr><tr><td>WiFi</td><td>100</td><td>1-3</td><td>好</td><td>低</td><td>容易</td><td>建库工作量大, 易被干扰</td></tr><tr><td>超声波</td><td>20</td><td>1-10</td><td>较差</td><td>较高难</td><td></td><td>衰减明显，造价高</td></tr></table></body></html>

表1中的定位技术都是采用特定的算法对所接收到的待定位环境中的移动终端发出的无线信号强度进行测量以实现定位，基于WiFi的定位技术由于实施成本低、覆盖范围大、传输速率快、功率小，并且大部分图书馆都已实现WiFi的全覆盖，因此WiFi定位成为实现系统的最佳方案。

# 2.3 差异服务

差异服务是个性化服务的一种，通过将对象以某种相似性计算方法进行划分，进而提供不同的服务。位置感知融入差异服务使得系统既要能感知位置又要能感知人，本文通过定义角色信息分类表，并通过读者所在位置和所属角色两方面定位信息分类进而生成差异信息，使得同一位置区域不同角色的读者获得的主动信息具有差别性。

# 2.4 系统实现原理

(1）图书馆每个WiFi 信号基站(AP)都有一个全球唯一的MAC地址，并且一般来说无线AP的位置在一段时间内是不会改变的。

(2)移动智能终端可以通过设计程序扫描周围的AP信号，每个AP有两个重要数据:MAC地址和信号强度。MAC地址能确定唯一的AP；理论上，信号强度和AP之间的距离有函数关系，根据信号强度可以计算出和AP的距离。

(3）采集待定位区域的信号强度(RSSI)，并从中提取用于定位的特征库以及位置信息，将最终结果存入定位系统中用以匹配定位。(4）移动设备实时将周围WiFi数据发送到位置服务器，服务器可以通过与特征库匹配并采用合适的算法计算出设备的位置。(5）将预置在系统中的推送信息按所给的位置进行检索，同时以用户类型对信息进行分类，将合适的信息推送给读者。

# 3系统设计

# 3.1 系统体系框架

位置感知从顶层区分包括室内和室外两部分，系统包含室外的定位功能主要是便于后期扩展，进行新的增值服务。基于此思路，系统应用体系架构如图1所示：

![](images/0d4395af355e435f83dfd03dec058f85fea52a1e80b79d4da11b116ae189be26.jpg)  
图1系统体系架构

图1中室内的WiFi信号基站主要是利用图书馆既有的WLAN环境，室外的位置感知主要是依靠手机的GPS[9定位功能。智能手机端装有系统平台的APP 客户端，客户端可以以后台进程的方式在手机上运行，并通过3G或者WiFi网络将手机端获取的周围AP信息周期性地发送给应用服务器，如果能获取到GPS信息也一并发给服务器

# 3.2 系统软件架构

根据系统体系结构，并按照SOA架构对系统进行设计，本系统软件架构分为4层：环境访问层、数据处理层、应用服务层、应用层，如图2所示。

APPLer 德 APP 信 用管理 服务端应用服务层 读者注册 信息实时响应 位置感知SerLayer (计算)角色响应 位置特征管理 信管 读数据处理层 数据交换 信息处理 信号处理DataLayer XML  
环境访问层 WiFi信号 GPS信号 Android手机PhyLayer

(1）环境访问层：通过调用Android的API接口获取WiFi信号、GPS信号，它们都需要先获取手机端的访问权限。

(2)数据处理层：将下层传上来的位置信息进行处理封装成系统预定的数据格式，并交给上层的应用服务层，这里采用通用的开放数据交换格式JSON。(3）应用服务层：将数据层传过来的位置信息与特征库比对完成定位功能，同时设计多种功能的服务接口为上层服务。

(4）应用层：包括手机端的APP程序和Web管理平台。APP端主要包括：图书导航、新书推荐、咨询服务、位置显示、信息提醒、读友发现等。Web管理平台主要功能包括：统计分析、用户管理、特征指纹库管理、信息分类管理、推送信息管理等。

# 4核心功能实现

# 4.1 APP客户端

(1）信号采集

建立特征库和位置感知都需要对移动端周围AP信号进行采集，系统将此功能封装在环境访问模块PhyLayer中。PhyLayer首先要获取移动端WiFi、GPS等访问权限，然后将获取到的信号(如AP的MAC地址和信号强度)封装成指定的类交给数据处理层进行处理，Android开发平台提供有内置的API可以实现WiFi信号采集，本系统实现的关键代码如下所示：

public void GetWifiInfo(WifiInfo[] msg) {   
.//系统网络访问权限判断   
do{   
//getSystemService(String)通过名字返回服务句柄   
wm $\ O =$ (WifiManager) getSystemService(WIFI_SERVICE); wi $\ O =$ wm.getConnectionInfoO;//返回WiFi连接的动态信息 if(wi.getBSSIDO $\scriptstyle = =$ null)//null为未连接   
break;   
//获取网络的信号强度   
strength $\ l =$ wi.getRssi();   
WifiInfo $\mathrm { w } =$ new WifiInfo(wi.getBSSID(),strength); msg.add(w);   
} while(true);   
！

上述代码中客户端将采集到的WiFi信号的强度RSSI存放在结构类WifiInfo中，并以JSON格式发给服务器。

# (2）特征库建立

特征库是基于特征库定位方法的基础，通过对待定位区域进行数据采集得到特征库，而后才能用这些数据与实时数据进行匹配实现定位，本文参考了文献[7,10]特征库建立方法，对每个采样点所有信号都采集50次存人数据库，最后求其平均值Avg和波动权值Range。手动采集并处理的工作量大而繁琐，系统在APP 端设计了专用于信息采集的SignalGetActivity界面模块进行自动采集，其处理流程如图3所示，输入位置标识、X坐标和Y坐标，以一定时间间隔采集WiFi信号50次，将所有数据以JSON格式发给服务器端。

![](images/a5808d786815f401830dcf77de1611f617e0d3677f3f721fe6ad97f5a3fa9b91.jpg)  
图2系统软件架构  
图3特征库采集流程

服务器端将客户端发送过来的JSON格式数据解析存放在采集表中，表2为系统存放的手机端采集到的同一位置的原始信息，其中APname字段记录了AP的MAC 地址,Pos-name、Pos-X、Pos-Y字段记录了采集点的位置描述，该信息是在数据采集时由手机客户端录人。特征库管理模块对采集到的每个点的所有AP信号的50个采样值求平均，并将所求的值以数据列表的方式存入到如表3所示的数据库表中，其中字段

Avg-RSSI以列表的方式存储了AP的标识、平均信号强度和波动权值Range，这种列表方式存储主要是考虑AP数会动态变化，便于扩展。

表2原始采集的信号数据  

<html><body><table><tr><td></td><td>AP name Pos-name Pos-X</td><td></td><td>Pos-Y</td><td>RSSI1</td><td>RSSI2</td><td></td><td>RSSI50</td></tr><tr><td>AP1</td><td>Pos1</td><td>30</td><td>40</td><td>-75</td><td>-73</td><td></td><td>-77</td></tr><tr><td>AP2</td><td>Pos1</td><td>30</td><td>40</td><td>-81</td><td>-79</td><td></td><td>-86</td></tr><tr><td>AP3</td><td>Pos 1</td><td>30</td><td>40</td><td>-72</td><td>-78</td><td>··</td><td>-75</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

表3处理后的特征数据  

<html><body><table><tr><td>Pos-name</td><td>Pos-X</td><td>Pos-Y</td><td>Avg-RSSI</td></tr><tr><td>Pos1</td><td>30</td><td>40</td><td>(AP1,Avg1,Range1), (AP 2,Avg2, Range2)，.</td></tr><tr><td>Pos1</td><td>66</td><td>70</td><td>(AP1,Avg1,Range1),(AP2,Avg2, Range2),.</td></tr><tr><td>Pos2</td><td>50</td><td>30</td><td>(AP1,Avgl,Rangel),(AP2,Avg2, Range2),…</td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>

(3）实时位置服务信息

位置信息服务在APP端需要实现三个功能：客户端要以后台服务的方式在手机端运行；要按一定频率将周围获取的位置特征信息发送给服务器；将服务器端推送过来的信息通过后台消息的形式在手机端显示。Android提供了组件Service实现后台运行功能，类似Windows上的服务，其后台服务模块关键代码如下:

public class CumtLibService extends Service {   
$@$ Override   
public void onCreate({   
}   
$@$ Override   
public int onStartCommand(Intent intent, int flags,int startId) $\{$   
newWifiGetThread(.start();//启动信息采集线程   
return START_STICKY://确保服务被终止后自动启动   
}   
}

上述代码中APP服务开启了一个WifiGetThread(线程，该线程主要是以一定频率采集周围的WiFi信息，其模块关键代码如下：

Public class WifiGetThread extends Thread{ $@$ Override

public void run() {   
do{   
try{   
Thread.sleep(2000);   
WifiInfo[]msg $\mathbf { \tau } = \mathbf { \tau }$ new WifiInfo (;   
GetWifiInfo(msg);//调用WiFi信号采集函数   
GPSInfo gps=GetGPSInfoO://调用GPS信息获取函数   
PushInfoServlet(JsonLocInfo(msg,gps));//调用信息发送模块 }   
catch (InterruptedException e){   
e.printStackTrace();   
}   
}while (true);   
！   
}

WifiGetThread通过While循环方式不断进行信号采集，同时调用Thread.Sleep函数来产生采集频率，采集的频率太高会占用过多移动端硬件资源，同时也占用了WiFi的信号通道，频率太低会影响信息获取的及时性，考虑到WiFi和GPS信号获取有一定的延时性，系统设定采样频率为2秒比较合适。

通过信号的采集，系统将生成的GetWifiInfo和GPSInfo信息交给信号发送模块PushInfoServlet，该模块通过get方法从服务器拉取信息，将位置信息和读者ID作为参数发给服务器，并将服务器返回的数据在通知栏中显示，核心代码如下：

Public viod PushInfoServlet(JsonLocInfo)   
{   
//服务器端位置计算模块地址   
Stringurl $\mathbf { \Sigma } = \mathbf { \Sigma }$ "http://localhost/LocationServlet/";   
//采用get方式向服务器发送请求   
JsonLocInfo.Push("uid",UID);//加入读者ID   
AsyncHttpClient.get(url, JsonLocInfo,new   
AsyncHttpResponseHandler({   
$@$ Override   
public void onSuccess(int statusCode,Header[] headers, byte[] responseBody){   
try{   
JSONObject noticemsg $\ c =$ new JSONObject(new String( responseBody, "utf-8"));   
int state $\ c =$ noticemsg.getInt("state");   
//判断是否有信息服务   
if (state $\scriptstyle = =$ "success"){   
Notification(noticemsg)；//调用消息通知显示模块 }   
$\}$ catch (Exception e) {   
e.printStackTrace(;   
}}3）；   
！

# 4.2 服务端设计

(1）位置计算

服务器端接收到客户端传来的JSON位置数据并进行位置计算，其处理流程如图4所示：

![](images/be96be48177040998b4322fc19a7c67811407cda389a3ac791d9366a809a7a0a.jpg)  
图4位置感知处理流程

图4中服务器端在接收到客户端传来的JSON数据后进行解析，每次将GPS信息都存入数据库表中，而WiFi信息只有匹配成功后才将这条信息存入表中，因为匹配不成功说明这条WiFi信息是无效信息可以直接丢弃，同时融入了GPS位置推送接口(图4中阴影部份)便于系统后期的扩展。当前成熟的位置匹配算法有：

$\textcircled{1}$ 概率型算法：采用贝叶斯估计理论，通过不同的似然函数，如基于核函数的似然函数，计算目标位置的后验概率，并取后验概率最大的位置点作为目标的最终位置估计。

$\textcircled{2}$ 确定型算法[10]：在特征指纹库中选择与当前采集的信息距离最小的几个点的质心作为目标的位置估计。

确定型算法复杂性低，计算速度快，本文也是基于此方法，其位置定位函数描述如下：

输入参数：消息数据APs(Mac,RSSI)数组输出参数：位置数据 Loc(X,Y)  
Begin  
ForEach APi inAPs  
Select Loci IF RSSIi in (APi.RSSI $+ \varepsilon$ ,RSSIi $+ \varepsilon$ ）N=Count(Loci);  
IF Loci Selected  
$\mathrm { E i = } 1 / \mathrm { n }$ Else  
$\scriptstyle \operatorname { E i } = 0$ ：  
End If;  
End For;  
Return Loci Where max(Ei);End;

函数中通过在特征库建设时对每个AP的所有采集点的波动权值Range求平均得到，公式如下：

$$
\varepsilon _ { \mathrm { a p } } = \sum _ { \mathrm { i } = 0 } \mathrm { r a n g e _ { \mathrm { i } } } \mathord { \left/ { \vphantom { \mathrm { c o u n t } } } \right. \kern - delimiterspace } \mathrm { c o u n t } ( \mathrm { a p } )
$$

对传入的每个AP的RSSI值，在指纹库中查找满足[RSSI-ε, $\lvert \mathrm { R S S I + } \rvert$ 范围的位置点，如果有 $\mathbf { n }$ 个点属于此区间，则将这些点分别取权值为 $1 / \mathrm { n }$ ，其余点都取权值为0；在对所有AP按照上述过程处理后，选其权值最大的点为估计位置，当出现多个点的权值一样时，以信号强度的距离最小者为准。

# (2）信息分类

服务端在位置匹配成功后需要生成推送信息，根据图书馆日常的服务功能，本系统将推送信息分为6类，如表4所示：

表4推送信息分类  

<html><body><table><tr><td>信息分类</td><td>说明</td><td>优先级</td></tr><tr><td>介绍类信息</td><td>根据所处位置，推送有关阅览室介绍、 设施、读者在馆状况等</td><td>1</td></tr><tr><td>书籍类信息</td><td>根据所处阅览室位置，推送最新的本 书库新库</td><td>2</td></tr><tr><td>咨询类信息</td><td>根据所处位置，主动提供在线咨询服务</td><td>3</td></tr><tr><td>朋友类信息</td><td>获取附近相同专业的读者，形成一个 虚拟研究室</td><td>4</td></tr><tr><td>新闻类信息</td><td>有关图书馆最新的活动、新闻</td><td>5</td></tr><tr><td>其他信息</td><td></td><td>6</td></tr></table></body></html>

表4中每一类信息在不同的位置内容不同，而在同一位置可能包含有多种类型的信息，如一个阅览室可以有介绍信息、书籍推荐信息、朋友类信息，其中介绍信息优先级最高，能保证该类信息最先推送。为了准确区分图书馆各物理空间的服务功能，系统定义了各位置包含的服务信息类型如表5所示。

# (3）读者角色设定

不同类型读者对服务的期望不一样，如低年级学生会对图书馆的各种活动或新鲜事感兴趣，而教师、研究生可能更希望了解一些新书、新的数据库信息。

表5位置所包含的信息分类  

<html><body><table><tr><td>位置分类</td><td>包含的推送信息分类</td></tr><tr><td>图书阅览室</td><td>书籍推荐，朋友推荐，咨询服务，介绍信息</td></tr><tr><td>读者研究室</td><td>朋友推荐，咨询服务</td></tr><tr><td>电子阅览室</td><td>咨询服务，新闻信息，介绍信息</td></tr><tr><td>期刊阅览室</td><td>新闻信息，介绍信息</td></tr><tr><td>借阅大厅</td><td>咨询服务，新闻信息，其他信息，介绍信息</td></tr><tr><td>各服务部门</td><td>介绍信息</td></tr><tr><td>其他</td><td>新书推荐，其他信息，新闻信息</td></tr></table></body></html>

基于此，本文认为读者的类型越相近其对服务的期望也越相似，根据这一原则本系统将读者分为5类角色，每类角色包含的读者类型和服务信息分类如表6所示，其中读者类型依据本馆OPAC系统中包含的读者类型设定。

表6读者角色信息配置表  

<html><body><table><tr><td>角色分类</td><td>读者类型</td><td>包含的推送信息分类</td></tr><tr><td>高级读者</td><td>教师、实验员、 校职工</td><td>书籍推荐，介绍信息</td></tr><tr><td>普通读者</td><td>应用教育</td><td>本科生、二学位、新闻信息，书籍推荐，咨询服务， 介绍信息</td></tr><tr><td>学术读者</td><td>博士、硕士</td><td>朋友推荐，书籍推荐，介绍信息</td></tr><tr><td>外籍读者</td><td>外教、留学生</td><td>咨询服务，新闻信息，介绍信息</td></tr><tr><td>校外读者</td><td>校外读者、成人 教育、其他</td><td>咨询服务，介绍信息</td></tr></table></body></html>

# (4)读者角色获取

读者类型对应着读者角色，图书馆OPAC的读者信息中包含了读者类型，因此为了确定读者的角色，APP客户端第一次运行时，需要用户使用图书馆OPAC系统中的账号ID进行注册，在进行位置请求时将位置信息和ID一并以JSON格式发给服务器。服务端将接收到的ID 作为参数调用OPAC 获取读者信息的 Web服务接口，此接口会返回包含读者类型的XML数据包，服务端根据XML中的读者类型匹配角色配置表确定读者的角色，处理流程如图5所示。当读者未注册或者ID号错误时，系统将其归人“校外读者"类型。同时为了使用的方便，客户端将读者输入的账号信息作为APP的私有数据保存在手机存储中，程序下一次运行时会读取保存的私有数据，读者不再需要重新输入账号信息。

APP端 服务端 OPACWeb服务  
手机端位置 Get方法 提取读者ID API: 获取读  
请求JSON 者信息读者信息读者类型解析:XML角色配 角色信息置表 信息生成模块

(5）差异信息生成

系统通过读者所在位置和所属角色两方面定位当前推送信息分类列表，进而生成差异服务信息，其处理流程如图6所示：

位置计算 获得读者角色位置信息S 角色信息生成当前位 生成当前角色置信息分类A 信息分类B1生成公共 角色信息分类C 配置表  
位置  
信息生成 位置推送  
分类表 推送信息 信息列表

图6中将输入的位置信息S与位置信息分类表匹配生成当前位置可以推送的信息分类列表A；同时根据读者角色与角色信息分类表匹配生成此角色可以推送的信息分类列表B；对A和B求公共分类生成最终的分类列表C，最后检索推送信息列表中位置S处属于分类列表C的信息即为推送信息。通过图6的处理流程实现了不同角色在同一区域和同一角色在不同位置都将被推送不同的信息。

(6）信息失效时间

信息推送的频率直接影响读者的体验效果，比如读者进人图书馆大厅的欢迎信息可以每天进人馆内都发送，而阅览室的介绍信息每次定位后都发送就显得不合适。为了能够对每条推送信息依据其位置而采用合适的推送频率，本系统对配置的每条推送信息都设定一个失效时间T，在发送每条信息前都需查找消息日志表，只有日志表中读者的同条信息最后一次发送时间到现在的时间间隔超过该条消息设定的失效时间

T才推送该条信息。

# 4.3 服务质量提升策略

读者每天都要收到各种APP软件的推送信息，图书馆主动信息服务要想在重多的信息中引起读者的关注则需要切实根据用户的兴趣从多渠道改善推送内容。各种服务系统设计的信息推送策略在很多情况下可能是读者不感兴趣的，针对此情况本系统设计了服务反馈功能，读者可以对收到的服务信息进行评分，将评分等级按照信息类型分为5级：5分、4分、3分、2分、1分。服务器端接收到用户提交的评分结果后将其存人信息评分表，系统根据评分结果定期对信息类型的优先级进行调整。

# 5 系统应用与评价

依据图2的体系结构对平台进行主要功能的开发，系统包括服务器端、APP客户端和应用管理端三部分。服务器端以后台服务的方式在服务器上运行，为APP、管理端提供业务处理。图7(a)是系统接收到推送信息后的提示信息，图7(b)是打开一条信息后有关自然科学阅览室的介绍信息，该信息提供了读者对信息评分功能。

16:48 2015年9月21日 章 16:48中国矿业大学图书馆  
& C移动 未爱的读者：  
益才 WLAN 声 载据欢迎来到自然科学阅览室，所藏图书包括：  
进行中 N自然科学：P天文学、地球科学：Q生物科学：LBE正在保护您 bo 医药、卫生：S农业科学：T工业技术：U交通：0.00BN：22.41MB 00 运输：V航空、航天：X环境科学、安全科学：Z  
通知 清除 综合性图书等，总供设置座位150个，提供检案机5台，免费无线Vifi为cumtlib，上网密码是1ib_cumt中国业大学图书馆 16:48命度的请，欢定得次来到的书馆？ 如有任何问题，请咨询同览室门口服务台老师。感谢您的尚范，如对本条信息编意请回复评分：5分·4分\*3分·2分\*1分咨询服务 新书推荐 书刊导航中国移动 附近读者 当前位置 更多应用(a) (b)

以不同读者类型运行APP端，并在图书馆多个地点测试，以便对系统信息推送的准确性进行评测，测试10组数据统计结果如表7所示。表7中借阅大厅和阅览室所接收到的信息数与测试数基本相同，而研究室和查新部存在信息丢失，分析原因：主要是图书馆大厅、阅览室空间范围大，其空间半径都超过10米，位置计算所产生的误差基本能被对应空间的采样点包含在内；而研究室、查新部因为空间小，位置计算所产生的误差有时超出空间的半径，因而导致信息推送的失效。

表7测试收到的信息条数统计  

<html><body><table><tr><td>角色 类型</td><td>借阅 大厅</td><td>自然科学 阅览室</td><td>研究室</td><td>查新 部门</td></tr><tr><td>高级 读者</td><td>欢迎信息：10 咨询信息：10</td><td>介绍信息：9 书籍信息：9</td><td></td><td>介绍信息：8</td></tr><tr><td>普通 读者</td><td>欢迎信息：10 新闻信息：10 咨询信息：10</td><td>介绍信息：10 书籍信息：10</td><td>朋友信息：3 咨询服务：6</td><td>介绍信息：7</td></tr><tr><td>学术 读者</td><td>欢迎信息：9</td><td>介绍信息：9 书籍信息：9 朋友信息：5</td><td></td><td>介绍信息：8</td></tr><tr><td>校外 读者</td><td>欢迎信息：10 咨询服务：10</td><td>介绍信息：10</td><td></td><td>介绍信息：7</td></tr></table></body></html>

图8是管理端统计的读者反馈的评分记录，可以看出：介绍说明、书籍推荐类信息的评分相对要高，而咨询信息、新闻信息评分相对要低，这个结果也能从表7的统计中得出结论：图书馆大厅、阅览室包含了介绍信息、书籍推荐，且位置计算的成功率高；另外相比其他信息，读者对书籍推荐类信息更感兴趣，读者满意度更高。

图书馆位置信息服务系统-后台管理 X修改密码 退出系统  
功能导航《 A评分统计× 刷新X关闭全部  
应用管 搜索：信息类型请输入查询内容 aA读 窗删除  
者管理 读者ID 信息类型 信息ID 评分值反馈日期A指 1 01150007 推荐信息 005413 5 2015/10/12  
纹管理 2 01150008 介绍说明 004101 4 2015/10/12信 01150024推荐信息 005411 4 2015/10/12  
息管理 01150049 咨询信息 003102 4 2015/10/12 1200 □5分  
分评计 56 1150075 信 002101 25 2015/10/12 1000  
计 7 01150086 介绍说明 004111 5 2015/10/12 800 1分8 01150104 咨询信息 003101 3 2015/10/129 01150112 朋友信息 002101 3 2015/10/12 6001004151689介绍说明 0041024 2015/10/121104151695 推荐信息 005412 5 2015/10/12 4001204151708 其它信息 001102 2 2015/10/111304151723 推荐信息 005415 5 2015/10/11 200 11404151731 其它信息 001101 1 2015/10/111504151730 介极说明 004106 2015/10/11 推荐信息 介绍说明 咨询信息 朋友信息 其它信息  
系统管20 □ H 第1 共289页 H 0 显示1到20，共5765记录Copyright 2015

# 6结语

位置感知服务已经在大型商场、大型博物馆等服务领域开始应用，是未来建设智慧型图书馆的重要部分，国内很多图情研究者也开始了该领域的探索，而实际成熟的应用还不是很多。本文从应用角度出发，设计了基于位置感知的主动服务系统框架，对系统主要功能实现进行了阐述，通过室内WiFi和GPS定位技术实现读者的无缝位置感知，并通过读者角色信息分类表生成个性化的差异信息。系统在中国矿业大学图书馆实地应用，提升了用户体验，获得各类读者的一致认可。其局限性在于分类粒度需要细化，更进一步考虑个性需求。利用数据挖掘算法发现用户的个性化需求将是未来研究方向。

# 参考文献：

[1]朱中一．基于WiFi的室内定位技术在博物馆的应用[J]．软 件产业与工程,2013(3):38-41.(Zhu Zhongyi.The Application of a WiFi Indoor Positioning System in Museum [J]. Software Industry and Engineering,2013(3):38-41.)   
[2] 王智刚.基于WiFi室内定位技术的移动图书馆服务策略探 究[J]．图书馆理论与实践，2015(6):102-105.(Wang Zhigang.Research on Strategy of Mobile Library Services Based on WiFi Indoor Positioning Technology [J].Library Theory and Practice,2015(6):102-105.)   
[3] 李胜，王叶茂．一种基于本体和位置感知的图书馆书籍推 荐模型[J].现代图书情报技术，2015(3):58-66.(Li Sheng, Wang Yemao.An Ontology-based and Location-aware Book Recommendation Model in Library [J].New Technology of Library and Information Service,2015(3):58-66.)   
[4] 张浩，赵千川．蓝牙手机室内定位系统[J]．计算机应用, 2011,31(11):3152-3156.(Zhang Hao,Zhao Qianchuan. Indoor Positioning System for Bluetooth Cell Phone [J].Journal of Computer Applications,2011,31(11): 3152-3156.)   
[5] 房秉毅．基于超宽带技术的室内定位系统[J]．电子技术应 用,2006(7):124-127.(Fang Bingyi. Indoor Positioning System Based on Ultra Wide Band Technology[J].Application of Electronic Technique,2006 (7): 124-127.)   
[6] 白旭华，张瑞峰，张肖萌，等．基于ZigBee网络的室内定 位系统的设计与实现[J]．天津理工大学学报，2012，28(2): 11-15.(Bai Xuhua, Zhang Ruifeng，Zhang Xiaomeng, et al.Design and Implementation of Indoor Positioning SystemBased on ZigBeeNetwork[J].Journal ofTianjinUniversity of Technology,2012,28(2):11-15.) [7] 姜莉．基于WiFi室内定位关键技术的研究[D].大连：大连 理工大学,2010.(JiangLi.Research on the Key Technologies ofIndoor Location Based on Wifi[D].Dalian:Dalian University of Technology,2010.) [8] 汪苑，林锦国．几种常用室内定位技术的探讨[J]．中国仪 器仪表，201l(2):54-57.(Wang Yuan,Lin Jinguo．Indoor Location Technique Based on RFID[J].China Instrumentation,2011(2): 54-57.) [9]谢翔，荆昊，郭际明.室内环境下手机GPS 定位精度研究 [J]．测绘通报,2012(8):95-98.(Xie Xiang,Jing Hao,Guo Jiming.Research on Accuracy of Indoor-Mobile-GPS Positioning [J].Bulletin of Surveying and Mapping，2012(8):   
95-98.) [10]雷地球，罗海勇，刘晓明．一种基于WiFi 的室内定位系统设 计与实现[C]．见：第5届全国普适计算学术会议，洛阳.   
2010:295-300.(Lei Diqiu,Luo Haiyong,Liu Xiaoming.Design and Implement an Indoor Location System Based on WiFi [C]. In: Proceedings of PCC2010,Luoyang.2010: 295-300.)

# 作者贡献声明：

邓志文：设计系统框架，程序设计，论文起草及修订;  
都平平：提出研究思路，设计研究内容;  
穆亚凤：系统数据采集，应用测试。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版http://www.infotech.ac.cn。[1]邓志文，都平平，穆亚凤．outdata.xls.读者反馈的推荐信息评分记录.

收稿日期:2015-09-24  
收修改稿日期:2015-12-11

# Library Active-information Service System Based on Location Awareness

Deng Zhiwen Du PingpingMu Yafeng (China University of Mining and Technology Library, Xuzhou 2210o8, China)

Abstract:[Objective]This studytests anew system forbuildinga smart library which provides instant services to the readers based on theirlocations.[Context]Thereader's needs ofservice vary with his/her location,and readers at the same location might expect different services. Our new system can predict the real time needs ofreaders and provide services pro-actively.[Methods] Propose the framework of an active information differential service system based on the location awareness technology.This system can detect readers’precise locations with the help of WiFi and GPS technology,and then generate personalized service for each individual reader.[Results]After instaling the library's App,the readers canreceive diferent information services at various locations in the library.[Conclusions]Location service helps the library predict readers' real time needs and improve their user experience.

Keywords:Location awareness WiFi locationDifferential service

# ORCID联盟将改善英国研究的可见性和协作性

ORCID 作为一种用于研究人员身份标识的解决方案，将通过英国联合信息系统委员会(Jisc)所运营的全国联盟进行部署以提供给英国的高等教育机构。该解决方案将为学术交流生态系统带来广泛的改进。这份协议是由Jisc资源建设部负责协商拟定的，它将使得高校能够从降低的ORCID会员费用及增强的技术支持中受益。这将促进ORCID被各方采纳，同时也为英国高校的ORCID集成提供了一条平坦的路径。ORCID 通过改善科研体系和流程的集成及提高数据质量，最终将帮助完善英国科研产出的管理、复用和效率。目前有50 余所英国高校已经表明了在2015年加入ORCID 联盟的意向，另外22所高校表示希望在后期加入。

Jisc 副首席创新官 Rachel Bruce 表示：在以前，轻松地把有价值的科研成果关联起来是不可能的，即使是将专利或论文与其作者、合作者和机构关联起来都是非常困难的。这导致了科研管理极其低效，同时也很难确定之前有哪些的科研产出。由此产生的结果就是科研报告和共享效率的低下，这对个体研究人员和高校都造成了影响。ORCID 的广泛采纳和应用就是这一问题的解决方案，它将帮助英国继续提供一流的科研体系以及其他的益处，例如节约额外的成本和效率的提高。

ORCID 就像集线器一样将机构、资助者、出版商以及其他的研究人员标识系统联系起来，同时通过自动化流程和数据交换支持数据的复用。从最近对8所英国高校进行初步实验的反馈结果来看，采用ORCID 的机构有望在实施后两年内实现显著的效率提升，尤其是在内部数据管理、出版管理优化及提升资助者知情权等方面，同时在接下来的 3-4年内实现累计收益的稳定增长。越来越多的资助者要求在经费申请上标注ORCID，这也证明了该尝试对科学研究的重要性。从2015年8月开始，惠康基金会将 ORCID 标注作为强制性的要求，同时英国高等教育基金会(HEFCE)和英国研究理事会(RCUK)也对这一计划表示高度支持。此外，集成 ORCID 后的体系和流程所产生的预期改进将帮助高校应对资助者的开放获取(OA)政策，并在其中发挥重要的作用，例如作为下一代研究卓越框架(REF)的一部分支持走向开放的文化。高校将ORCID 看作是一项重要的服务，在确保符合开放获取要求的情况下，它能够减轻研究人员工作量，更加完善科研成果的可见性和可发现性，同时也为国际和跨学科的协作创造机会。

随着联盟开始运作,ORCID受到了诸多政策、实践及水平层面的支持，英国的ORCID采纳度已经达到了临界点。RachelBruce 继续说到：作为我们与英国高校及资助者工作的一部分，现在我们已经形成了一种共识:ORCID 是目前最佳的研究人员身份标注体系。这些讨论也催生出了强烈的需求，即要求 Jisc 建立全国联盟，以确保ORCID 被广泛采纳后发挥其优势。非常高兴我们现在能够提供这样的部署，以此实现英国更完善的科研信息管理。

ORCID 是一项全球化的、开放的、非营利性的、用户社群驱动的成就，它由研究社群开发并服务于研究社群。ORCID提供了有关在高校或研究机构科研信息系统中实施的附加使用案例及详细文档。

(编译自:htps:/jiscukatial-osort-forid-stmprouresearcvisiblitolbortio-jun.)

(本刊讯)