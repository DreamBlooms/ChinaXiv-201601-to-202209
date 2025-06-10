# 基于情境感知技术的移动数据自动采集系统设计与实现

夏立新 杨金庆 程秀峰(华中师范大学信息管理学院武汉 430079)

摘要：【目的】为移动环境下数据采集与分析提供一种基于情境感知技术(Context Awareness)的设计框架，以优化移动数据自动化采集过程。【应用背景】尽管基于移动端的情景感知数据采集较之传统网络环境下的人工与半自动方式有所发展，但利用移动端底层传感器直接获取实时用户信息，实现实时、动态、全面的数据采集与挖掘进而达到主动提供服务的目的，这方面的应用仍处于发展阶段。【方法】利用 Android 自带的众多传感器，设计了客户端自动采集、服务器主动接收的数据采集框架。在实证与评价方面，设计了一个通过动态情境感知推荐高层服务的实例。【结果】实证结果表明：该系统能够针对某一情境采集移动用户数据，为高层推荐服务提供良好支持。【局限】采集到的数据具有较大的冗余度，未进行多角度、全面、深度的情境推理，需要在以后的研究中针对用户数据进行深入分析。【结论】基于情境感知的移动数据自动采集系统能够进行移动数据的主动采集，并依据采集结果对个体或群体进行推送服务，对移动环境下用户行为研究与情境计算研究都起到较好的支撑作用。

关键词：情境感知 应用框架 Android 情境推理用户行为

分类号：G25 TP311

# 1引言

移动通讯技术的飞速发展，使得移动智能终端使用迅速普及。手机缩短了人与人沟通的距离，提升了工作效率，方便了社会生活。一方面，手机的普及为科研工作者与服务提供商获取用户数据提出更高的要求；另一方面，手机包含大量真实的行为数据，利用手机数据进行情境计算以及相关行为研究的好处不言而喻。如能快速获取这些数据，挖掘有效信息，感知用户所处环境，从而推导出用户所需并主动向其提供相应的服务，将能极大促进行为及服务研究的可靠性与准确性。同时，在情境计算(Contextual Computing)领域[1]研究者根据研究需要选择使用多种情境信息，并利用物联网技术、云计算技术、后台数据库、网络存储以及传感器技术等多种方式监测并获取这些环境信息，将这些通常是数量巨大且关系复杂的用户信息规则化。规则化过程具体为：首先建立形式化模型(静态),然后对静态模型设立匹配规则，动态推导出用户需求并筛选出最适合的用户服务从而进行服务推荐[2]。

以上是情境计算的一般过程。从整体上，它包括数据采集及规范化两部分，对于后者来说，模型的选取、规则语言及中间件的研发以及服务的匹配等，需要找到一种适用于特定环境及情境感知系统的方法体系，以统一已有的数据和模型。而对于前者，获取的数据的质量，包括精度、准确度、统一程度，直接影响整个情境计算的后续过程。然而，移动数据的采集存在种种技术瓶颈与安全隐私问题，使得大量基于移动数据采集的研究止步于理论模型。由此，如何高效、自动地采集移动情境数据，从而进一步设计一种良好的情境计算框架(包括情境模型、情境推理、感知服务、中间件技术)，使系统能够感知用户状态、提升用户体验[3]，是情境计算重点关注的内容。情境信息获取对象类型多样，所对应的获取手段也很多。对于空间位置、时间、网络、蓝牙、电量、温度、湿度、光线，噪音等物理信息一般通过搭载在设备上的物理传感器，或者通过使用多种通信协议统一设备接口获取[4]。对于邻近对象、交通、人群、风俗、景物等高级情境，则需要通过初级情境感知组合来推导。为了根据传感器中的初级情境识别出高级情境，研究者通常会依据研究目的，重点关注用户活动中的一些任务执行场景，展开调研，分解任务，计算情境。另外，结合数据挖掘和可视化技术发现情境信息间的隐含关系，并将其可视化，也是情境感知技术的发展方向之一。

Android4.0版本以上通用智能移动终端内嵌了多种传感器，传感器能够采集大量准确、实时、可靠的数据，从而使得利用情境感知(Context Awareness)技术[5]采集终端数据成为可能。根据普适计算和移动计算理论[7]，从物理传感器采集到的数据能够转化为多用户、多任务之间分享的情境信息。由此，笔者在移动感知软件 AWARE[8的基础上开发了一款适合特定情境分析的情境感知系统(简称"MDCF")，并设计了一个较简单但容易扩展的情境规范化框架，使基于此系统采集到的数据更好地感知情境与用户行为。MDCF能将原始信息和低层情境信息抽象处理成普通应用可以理解的高层情境信息，进而提供给相关应用。大致过程为：通过手机自带传感器采集原始数据，然后将数据抽象为情境信息，最后将情境信息存储在SD 卡或远程传递存入服务器端，实现移动数据的采集、管理、利用与研究。

# 2相关研究

情境计算涉及领域广泛，呈现系统架构层次复杂化、技术多样化的特点,它包括情境数据的获取，建立形式化模型以及对数据进行分析和处理。自Schilit等1994 年提出情境计算的概念[以来，诸多学者利用语义网、物联网技术、本体理论、云计算技术、复杂网络、SOA等众多方法研究情景感知信息。仅在本文重点研究的情境数据获取技术部分，国内外学者已有相当丰富的研究。例如,设备信息访问(Device InformationAccess,DIA)中间件通过统一接口实现对底层异构数据的屏蔽[10], $\mathrm { \Delta X u }$ 等的Cabot组件致力于解决动态监测数据的一致性问题[11]。韩立等通过问卷、录屏、录音等综合实验方式提取用户体验数据[12，另外，在一些特定领域,应用多种方式采集数据进行行业服务[13-14]。然而，情境感知系统这一概念一直没有被精确定义,一般认为情境感知系统使用情境数据提供相关信息，并且为用户提供服务，它们的关联则取决于用户任务[15]。尽管如此，情境感知技术仍然得到工业界的高度重视,并取得众多应用成果。CORTEX[1融合移动智能手机传感器数据、记录和推理情境数据的移动数据采集软件。它使用事件通信协议在各种传感器、促动器以及应用程序之间交换数据信息，采用事件-条件-行为规则推理出新的情境信息。Context Studio[17]将用户的调解作用和可说明性应用于情境推理。它可以通过用户输入信息来控制情境数据，并使用Blackboard 方法将多种情境结合在一起生成新的高层情境。ContextPhone[18]将采集的信息和用户本身视为资源，根据情境用户的可理解性，理解并控制情境信息交流，支持应用程序和用户间的交流。AWARENESS[19]重视用户隐私问题并应用环境质量概念表达情境信息质量特征，通过控制共享情境信息解决用户的隐私问题。Momento[20]通过多种通信方式采集定性、定量数据，产生多种类型的情境信息并可远程控制。MyExperience[21]采集多种传感器和基于用户的各种数据。它支持可定制的、基于用户的定性数据采集以及随机同步上传数据到服务器端。CenceMe[22]通过利用移动智能手机的传感器和社会网络应用程序分享的信息以推断个体感知存在状态，抽取用户的生活模式和习惯。它支持对具有异步数据挖掘和高处理能力设备进行分流处理。EmotionSense[23]感知个人情感、行为活动、语言以及朋友间近距离互动，支持在线、离线以及多学科可扩展情境信息。SystemSens[24采集用户与应用软件交互的数据与信息。它内置的调试功能所产生的信息不仅支持本软件运行还用于情境推理和数据采集。AWARE[25]采集各种传感器数据并对数据进行抽象处理生成高层情境信息并实现可视化、远程传递存储等。相较于同类开源系统，AWARE 的优点在于插件的扩展性和重用性。

# 3需求与技术思路

当前，采集移动用户行为数据供科学研究的途径主要可概括为三类：手动采集、共享采集和主动采集。手动采集是指研究人员根据实验要求在数据拥有方的服务器中直接下载复制或索取；共享采集是指通过开放平台提供的接口使用第三方插件获取科研所需数据。从目前笔者收集到的文献所采用的数据来看，通过共享采集的方式获取科研所需的数据被大量使用。但是这种方式的接口开放权掌握在运营商的手中，对于研究者来说，在获取门槛上颇费周折。主动采集系统是指研究者根据实验需要自行开发数据采集软件，或者选择符合科研需求的开源软件开发组件进行采集。主动采集方式的优点在于数据采集的自主性、灵活性。但是仍面临采集的非可控性、非完整性、不可扩展性以及缺乏可视化等问题：非可控性主要是指采集软件由于功能的兼容问题导致不能有选择性地获取需要的科研数据；非完整性主要是指系统往往会采集不到科研需求所规定范围的数据，导致数据残缺；不可扩展性主要是指采集到的数据由于接口问题不能满足扩展需要。

鉴于以上问题，笔者从科研数据需求出发，将手机自带Android数据共享标准技术、可视化技术、数据挖掘及机器学习技术相结合进行系统构建。系统目标主要包括"传感器数据传输”、“情境规范与组合”、“服务发现”。实现的技术思路如图1所示。

![](images/38c1df68426d27cd45fd0de5ef7295196c26fc662c787ce9936f083d65df5118.jpg)  
图1基于情境感知的移动数据自动采集系统总体技术思路

(1）采集层功能：传感器数据传输。MDCF通过编程操控手机内的传感器数据的采集与远程存储，利用getDefaultSensor(方法实现每个传感器实例化，并在交互界面赋予传感器列表中的每个传感器启动键对情

境进行选择性采集。

(2）规范层初级功能：基于Android数据共享标准获取到的共享数据，针对研究对象进行情境建模，首先建立元数据表示模型(本体)，利用标准本体规范推理本体间、元组间的关联信息，获取用户初级(静态)情境。

(3）规范层高级功能：从静态情境利用描述逻辑进行高层推理，针对不同情境，推理面向服务的高级情境。

(4）服务层功能：对高级情境做出服务，并将反馈输入MDCF，进行进一步的服务发现

# 4关键技术实现

# 4.1 系统架构

MDCF系统作为情境感知系统中的采集部分，其框架仍然采用标准C/S体系架构。主要包括服务器、服务器端数据库(MySQL)、数据传输方式(MQTT)、移动手机客户端(Android)以及本地轻量级数据库(SQLite)。MDCF系统结构框架如图2所示。

<html><body><table><tr><td></td><td>移动数据采集系统服务器</td><td rowspan="2">服务器端</td></tr><tr><td></td><td>服务器数据库-MySQL</td></tr></table></body></html>

<html><body><table><tr><td>HTTP</td><td></td><td>MQTT</td></tr></table></body></html>

9 Observer》 Broadcast Provider客户B 本地数据库-SQLite 端传感器 心 插件目 移动数据采集客户端

MDCF由服务器端和客户端组成。服务器端封装服务请求处理和后台数据库(MySQL)访问操作，将本地数据以JSON对象的形式，经过HTTPS协议传送到服务器。通过使用MQTT协议实时、主动地向客户端进行情境信息交换。服务器端接收客户端应用传送过来的数据，并对存储在服务器数据库中的数据进行管理，为科学研究提供数据支持。客户端通过Android开发所提供的各种类(例如：Sensor类)，对移动智能手机上的传感器数据进行记录、收集和处理。

# 4.2 逻辑架构

MDCF通过将移动设备产生的原始数据进行存储、传输、挖掘、抽象形成初级情境信息并将部分信息可视化。因此,MDCF细分为5个层：原始数据采集层、数据存储层、数据交流层、上下文层、可视化层，如图3所示。

<html><body><table><tr><td>可视化层 可视化自适应</td><td>插 件</td></tr><tr><td>上下文层 抽象 模型分类</td><td rowspan="6">传 感器</td></tr><tr><td>数据交流层</td></tr><tr><td>协议 交流格式 并行化 加密 安全 数据存储层</td></tr><tr><td>挖掘 存储 集群</td></tr><tr><td>原始数据采集层</td></tr><tr><td>硬件传感器 软件传感器基于人传感器 社交网络</td></tr></table></body></html>

(1）原始数据层：是指从手机各种传感器上获取的第一个存储媒介。手机传感器不仅仅包含硬件传感器还有软件传感器、基于用户的传感器。本系统的硬件传感器、软件传感器、行为传感器共28个。HW 表示由手机硬件(如陀螺仪)可直接获得参数的硬件传感器；SW表示由手机软件(如APP)信息共享获得信息的传感器。H表示将用户视为传感器而获得的行为信息(如问卷)，它无法由硬件或软件感应得到。MDCF所使用的三种类型的部分传感器如表1所示。

(2）数据存储层：包括本地存储和远程存储。本地存储是指将情境数据存储在手机本地的轻量级数据库SQLite中；远程存储是指经Web服务上传情境数据至远程服务器数据库中。

(3）数据交流层：为情境信息共享提供技术支撑,并为本地和外部的情境数据的交流提供交流机制。移动数据采集系统使用MQTT技术支撑移动智能手机和服务器以及其他设备之间的情境数据交流。MDCF客户端内部使用Android的Broadcast和Observer方法进行情境数据的传输。

(4）上下文层：利用简单条件规则将原始数据抽象为初级情境信息。初级情境信息可以在交流层进行分享，并且可以进一步将产生的静态情境信息推理生成动态情境信息。

表1部分传感器列表  

<html><body><table><tr><td rowspan="2">传感器</td><td colspan="3">类型</td><td rowspan="2">描述</td></tr><tr><td>HW</td><td>SW</td><td>H</td></tr><tr><td>Accelerometer</td><td>√</td><td></td><td></td><td>表示沿着设备轴的加速度力包括重力</td></tr><tr><td>Application</td><td></td><td>√</td><td></td><td>用于记录设备上的前台和后台运行的应用名称</td></tr><tr><td>Barometer</td><td>√</td><td></td><td></td><td>表示记录大气气压有关的传感器信息</td></tr><tr><td>Battery</td><td>√</td><td></td><td></td><td>产生电池和电源事件数据(如重启、关闭)</td></tr><tr><td>Bluetooth</td><td>√</td><td></td><td></td><td>内置的蓝牙传感器产生信息和执行间隔扫描附近的蓝牙设备</td></tr><tr><td>Communication</td><td></td><td>√</td><td></td><td>用于用户的通讯活动，例如通话状态、信息状态</td></tr><tr><td>ESM</td><td></td><td></td><td>√</td><td>通过ESM问卷获取用户提供的数据,ESM是由情境事件、时间等触发</td></tr><tr><td>Gravity</td><td>√</td><td></td><td></td><td>表示沿着设备轴的重力有关的传感器信息</td></tr><tr><td>Installations</td><td></td><td>√</td><td></td><td>用于记录移动设备上的应用程序添加、删除或更新的信息</td></tr><tr><td>Light</td><td>√</td><td></td><td></td><td>用于感触周围环境亮度信息</td></tr><tr><td>Locations</td><td>√</td><td>√</td><td></td><td>记录移动设备的网络和GPS位置信息并提供最可靠的位置信息</td></tr><tr><td>Network</td><td></td><td>√</td><td></td><td>记录使用网络情况，例如移动网络、WiFi</td></tr><tr><td>Orientation</td><td>√</td><td></td><td></td><td>表示沿着设备轴的方位角有关的传感器信息</td></tr><tr><td>Processor</td><td></td><td>√</td><td></td><td>记录系统、用户和移动处理器的工作负载</td></tr><tr><td>Proximity</td><td>√</td><td></td><td></td><td>记录设备和对象之间的距离</td></tr><tr><td>Screen</td><td>√</td><td>√</td><td></td><td>记录屏幕状态以及用户的锁定和释放事件</td></tr></table></body></html>

(5）可视化层：利用上下文插件将上下文层的情境信息进行简单可视化呈现，使得用户可以对情境信息进行交互。其具有诸多功能，例如：共享选择、传感器列表、当前状态等。

# 4.3 客户端实现

(1）传感器控制功能

传感器控制功能是MDCF的关键技术。传感器控制功能的实现，需要根据不同传感器及其类型，采取相适应的程序设计：手机自身的物理传感器采用Android 中的 Sensor 类通过 SensorManager的getDefaultSensor(int TYPE)方法获取指定类型的传感器；软件传感器利用Android数据共享标准实现不同应用的数据交换(根据程序细化)；行为传感器通过用户与系统的交互，输入难以测录的数据信息，例如通过MQTT协议进行问卷推送，提醒用户填写。科研人员可以根据科研需求自主地启动个性化传感器，通过Android的PreferenceActivity结合PreferceFragment实现各类传感器的个性化控制界面。鉴于以上技术，实现各类传感器实例化如表2所示(其中参数TYPE用于标识不同的传感器，TYPE数值封装在Sensor类中，-1表示通用类型的传感器)。

(2)插件管理功能

MDCF考虑到面向科研数据采集需求的多样性，需要降低系统的耦合性，开放系统软件接口，提高软件应用的可扩展性。借助插件的灵活性可以对情境信息进行抽象，继而将机器学习、数据挖掘算法等技术融入情境推理，将原始数据抽象为更高等级的情境信息。

表2Sensor类  

<html><body><table><tr><td>TYPE</td><td>参数名称</td><td>传感器名称</td></tr><tr><td>1</td><td>TYPE_ACCELEROMETER</td><td>加速度传感器</td></tr><tr><td>4</td><td>TYPE_GYROSCOPE</td><td>陀螺仪传感器</td></tr><tr><td>5</td><td>TYPE_LIGHT</td><td>光照传感器</td></tr><tr><td>2</td><td>TYPE_MAGNETIC_FIELD</td><td>磁力计传感器</td></tr><tr><td>3</td><td>TYPE_ORIENTATION</td><td>方位传感器</td></tr><tr><td>6</td><td>TYPE_PRESSURE</td><td>压力传感器</td></tr><tr><td>8</td><td>TYPE_PROXIMITY</td><td>距离传感器</td></tr><tr><td>7</td><td>TYPE_TEMPERATURE</td><td>温度传感器</td></tr><tr><td>9</td><td>TYPE_APPLICATION</td><td>应用记录传感器</td></tr><tr><td>-1</td><td>TYPE_ALL</td><td>所有传感器</td></tr></table></body></html>

# (3）可视化功能

客户端可视化是MDCF主要特色之一，区别于其他一键式采集软件，可以提供信息采集情况反馈，对数据采集的整个流程起到一定的监控作用。这不仅提高了用户体验，还保证了人机交互的信任程度。使用户及时了解和改善发送策略，调整采集范围，保证科研人员的数据规范程度与用户的隐私安全。

# 4.4服务器管理端实现

服务器端主要是基于Tomcat+MySQL搭建一个轻量级服务，主要接收客户端上传的情境数据，能够对所收集的信息进行自主管理、抽象分析等。MDCF服务器是以Web和MQTT两种方式结合实现情境数据的远程存储和与客户端的信息交流，服务器端的构成如表3所示。

表3服务器端结构层次表  

<html><body><table><tr><td colspan="2">数据采集系统服务器</td></tr><tr><td>Web服务器</td><td>MQTT服务器</td></tr><tr><td>Data MVC</td><td>Messages Repository</td></tr><tr><td>Databases</td><td>Messages</td></tr></table></body></html>

通过Web服务器和MQTT服务器，可以在客户端进行设置实现数据远程发送。MQTT服务器支持分布式基础设施并与用户客户端进行实时情境信息交流，该服务器是一种RSMB发布/订阅代理，也可以实现集群以支持情境信息的负载平衡。为保证安全与隐私问题，MQTT中的RSMB支持安全认证连接。消息存储方式是基于文件或基于数据库的，主要存储情境信息、事件和数据。Web服务遵循MVC设计模式，即根据请求、控制器加载相应对象模型并执行命令。如果请求可视化，控制器另外加载相应的视图。因此，MDCF服务包括Web服务器和MQTT服务器，结合了两者的特性，提高了自身的性能。

# 4.5 应用效果

![](images/f9e5fb33992c5a665ca1463f5be6b774427ac92d5206dc9a5faae4f1bff4b49b.jpg)  
图4MDCF客户端功能界面

客户端启动后首先显示界面如图4(a)所示。它展示MDCF含有的软件和硬件传感器选项，还显示客户端唯一标识符等信息，其中唯一标识符是在用户安装软件时产生的。插件管理功能可打开添加插件界面，显示 MDCF系统兼容的数据采集和可视化的插件，如图4(b)所示。原始情境状态可视化界面可以根据启动的传感器和插件来显示更多的情境信息，如图4(c)所示。

# 5基于MDCF的情境建模与情境推理

# 5.1 情境建模

情景建模主要是利用一些理论模型或方法，以形式化的方式将得到的情境表示为有意义的线索。选择何种形式化方法来表达存储情境信息，建立情境模型，是情境信息获取后的重要工作。目前，比较经典的形式化方法有着色Petri网[26]、面向对象的方法[27]以及本体模型[28]。着色Petri网可以表达的情境信息有限，仅适用于分布式并发进程。面向对象模型具有很强的表达能力，但缺乏规则的支持[1]。而以本体论为理论基础的本体语言[29能够建立知识表示和推理系统，具有逻辑描述能力、推理能力和表达能力，能够很好地描述情境信息，进而达到采集结果形式上与语义推理上的统一。本文选择基于本体的情境模型对采集的情境数据进行描述。

MDCF系统构造本体的目标是获得两个层次的情境，面向低层和面向高层，低层的情境感知建模是任务推导型，即利用情境模型及数据逻辑推理出用户当前任务(例如，利用用户在用何种APP判断出用户在做何种事情)；高层的情境感知建模更加面向服务需求，即通过挖掘本体之间以及本体的元组之间的关联，对每种关联进行算法推理，进而推理出用户的情境需求(例如：通过检查APP出错率、设备温差、用户使用频率，推断出何种品牌手机更容易因电池问题而影响消费)。

初步设定一个含有9元组描述<Location、Device、Temperature、Battery、App-Foreground、App-History、App-Notification、App-Crash、WIFI>的情境信息本体(APP使用本体)，以及其内部元组的关联关系的本体模型。如表4所示，每个元组包含一系列传感器记录(有的记录名称重复，但并不表示可以表示别的元组，因为它们来自于不同传感器)。

表4MDCF情境建模部分元组及记录列表  

<html><body><table><tr><td>元组</td><td>记录</td><td>记录解释</td></tr><tr><td rowspan="5">Location 地理空间</td><td>device_id</td><td>设备ID</td></tr><tr><td> timestamp</td><td>记录时的时间戳</td></tr><tr><td>latitude</td><td>用户所处的纬度</td></tr><tr><td>longitude</td><td>用户所处的经度</td></tr><tr><td>accuracy</td><td>位置的误差值</td></tr><tr><td rowspan="5">Device 手机品牌、型号及软件版本 Device=<device_id,timestamp,hardware,product></td><td>device_id</td><td>设备ID</td></tr><tr><td>timestamp</td><td>记录时的时间戳</td></tr><tr><td>hardware</td><td>移动设备代码</td></tr><tr><td>product</td><td>移动设备名称及型号</td></tr><tr><td>device_id</td><td>设备ID</td></tr><tr><td>Temperature 手机外部温度</td><td>timestamp</td><td>记录时的时间戳</td></tr><tr><td rowspan="3">Temperature=<device_id,timestamp,tempOut,accuracy></td><td>tempOut</td><td>设备外部环境温度</td></tr><tr><td>accuracy</td><td>外部温度的误差</td></tr><tr><td>device_id</td><td></td></tr><tr><td>Batery</td><td></td><td>设备ID</td></tr><tr><td>手机电池温度 Battery =<device_id,timestamp,tempIn, battery_level></td><td>timestamp tempIn</td><td>记录时的时间戳 手机内部温度(电池温度)</td></tr><tr><td rowspan="2"></td><td>battery_level</td><td>电池温度的合理范围</td></tr><tr><td>device_id</td><td>设备ID</td></tr><tr><td>WIFI 手机WiFi,</td><td>timestamp</td><td>记录时的时间戳</td></tr><tr><td rowspan="3">WIFI=<device_id,timestamp,ssd,frequency></td><td>ssid</td><td></td></tr><tr><td>frequency</td><td>当前连接的网络接口名称</td></tr><tr><td>device_id</td><td>WiFi宽带频率</td></tr><tr><td>App-Foreground</td><td></td><td>设备ID</td></tr><tr><td rowspan="2">正在运行的 APP App-Foreground=<device_id,timestamp,app_name,Is_sys_app></td><td>timestamp</td><td>记录时的时间戳</td></tr><tr><td>app_name</td><td>正在运行的 APP 应用</td></tr><tr><td rowspan="2">App-History</td><td>Is_sys_app</td><td>判断是否系统自带 APP</td></tr><tr><td>device_id</td><td>设备ID</td></tr><tr><td>手机 APP 运行历史</td><td>timestamp</td><td>记录时的时间戳</td></tr><tr><td rowspan="2">App-History=<device_id,timestamp,app_name,end_time></td><td>app_name</td><td>使用过的所有APP 应用名称</td></tr><tr><td>end_time</td><td>APP 应用使用终止的时间</td></tr><tr><td>App-Notification</td><td>device_id</td><td>设备ID</td></tr><tr><td>手机应用通知</td><td> timestamp</td><td>记录时的时间戳</td></tr><tr><td>App-Notification=<device_id,timestamp,app_name,text></td><td>app_name</td><td>被发送通知消息的所有 APP 名称</td></tr><tr><td rowspan="2"></td><td>text</td><td>通知消息的标题内容</td></tr><tr><td>device_id</td><td>设备ID</td></tr><tr><td>App-Crash 手机应用运行错误</td><td>timestamp</td><td>记录时的时间戳</td></tr><tr><td></td><td>app_name</td><td>运行错误的所有 APP 应用名称</td></tr><tr><td>App-Crash=<device_id,timestamp,app_name,error></td><td>error</td><td>记录错误类型</td></tr></table></body></html>

在建立本体模型之后，可以从中挖掘元组与元组之间的关联，从关联推导出满足上文所指的高层情境感知信息。如图5所示，在使用手机行为过程中，可以根据APP使用规律推理其生活规律(Life)，根据手机通知发布信息推理用户受信息干扰状态(Influence)；根据手机内外部温差、品牌以及使用APP信息(Temperature)推理不同品牌用户使用APP的体验信息；根据APP出错率与使用APP信息推理用户对APP的接受程度。

![](images/9a6832487186ee4a1844a0b9aa44c848917a6a02cfb1dfffe94b7c94714ec2de.jpg)  
图5“APP使用"本体模型(元组及元组之间关系，中层情境)

# 5.2 情境推理

通过直接情境采集到数据并通过形式化方法建立情境模型，属于情境计算的先验环节，其难点在于对数据格式的统一处理模型的选择[1]。然而，直接情境并不能描述用户当前的完整情境，需要利用推理规则对获得的情境进行推理得到中高层情境信息或隐藏信息[30]。情境推理的方法很多，包括：基于相似度的计算推理[31]、基于多值逻辑的推理[32]、基于规则的推理[33]、基于本体的推理、基于本体和自定义规则的情境推理[34]。其中，基于本体和自定义规则的情境推理是利用自定义的描述逻辑与本体模型，将情境与情境关系和规则定义成本体、本体属性(元组)和约束关系，其典型代表OWL[35通过执行SWRL规则来对模型信息进行扩充，适用于中高层情境的推理。SWRL[规则表示如下：

适用规则与算法前件 后件

其语义是：只要前件中所表示的条件在模型中被满足，则后件中描述的事实也必须在模型中存在，如果后件中的事实模型不存在，推理引擎则会将其添加到模型中。本文在实证中基于“APP使用"本体中的若干元组关联(中层情境)进行情境推理，可以得到高层情境信息，如表5所示。

表5“APP使用本体"中当前情境向高层情境推理规则列表  

<html><body><table><tr><td>关联(中层情境)</td><td>推理适用算法</td><td>高层情境</td></tr><tr><td>Life 生活型情境</td><td>K-means、SOM、FCM…</td><td>表示 App-History 中存在某种生活规律</td></tr><tr><td>Influence 影响型情境</td><td>SVD、NSFCM、VSM…</td><td>表示 App-Notification 中通知信息的干扰性</td></tr><tr><td>Experience 体验型情境</td><td>Apriori、FP Growth、Eclat…</td><td>表示 Device、Location、tempIn-temp 间存在的相关关系</td></tr><tr><td>Mental心理型情境</td><td>Apriori、FP Growth、Eclat…</td><td>表示 App-Crash 与 App-History、Device 间存在的相关关系</td></tr></table></body></html>

由表5可知，通过设备信息(Device)与应用出错率 (App-Crash)的关系，可以判断用户当前手机状态为

“卡顿”，建议尽快升级软件版本或更换手机。

推理规则1基于用户某APP使用规律的推理规则：<timestamp,end_timestamp|Life> $\in$ App-HistoryK-means,SOM,FCM应用使用行为

从App-History元组中某APP的开始时间和终止时间，利用合适的聚类算法，从当前使用情境推理使用规律。

推理规则2基于用户获得通知信息的干扰性的推理规则:

<app_name,text|Influence> $\ r \in \ r _ { \mathbf { \theta } }$ App-Notification SVD,NSFCM,VSM干扰信息

从App-Notification元组中的通知信息，利用相关文本挖掘算法，提取关键字，以此判断通知信息的类型(干扰/不干扰)。从当前情境推理是否可以智能化地进行干扰消息拦截。

推理规则3基于手机在不同时间下温差的推理规则：<temperature,app_name|Experience>∈Device,Battery

Apriori,EclatFPGrowth户体验

从相关域中的情境信息，利用相关关联算法推理手机温度与用户体验间的隐含关系。

推理规则4基于手机在不同时间下温差、使用情况与出错率的推理规则：

<app_name, temperature, timestamp|Mental> $\in$ Device, App-Foreground,App-Crash Apriori、Eclat、FPGrowth用户心理

从相关域中的情境信息，利用关联算法推理用户心理信息。

# 6 应用实例

为验证MDCF采集系统及对应情境推理框架的适用性，从2016年9月15日到2016年11月15日，采集28份有效个人数据(实际采集30份)。学习类APP记录一共104052条，描述了18个APP使用信息，其中，从前文定义的"APP使用"本体的不同元组中抽取有关用户任务的简单列表，如表6所示。

表6静态情境例子  

<html><body><table><tr><td>Device_id</td><td>时间</td><td>经度</td><td>纬度</td><td>电量</td><td>任务</td></tr><tr><td>a32f534c4a</td><td>2016-09-09 15:01:18</td><td>30.521051</td><td>114.357306</td><td>45</td><td>有道词典</td></tr><tr><td>a32f534c4a</td><td>2016-09-09 15:18:00</td><td>30.521051</td><td>114.357306</td><td>45</td><td>有道词典</td></tr><tr><td>a32f534c4a</td><td>2016-09-09 15:19:45</td><td>30.521051</td><td>114.357306</td><td>44</td><td>有道词典</td></tr><tr><td>a32f534c4a</td><td>2016-09-09 16:02:18</td><td>30.521051</td><td>114.357306</td><td>30</td><td>有道词典</td></tr><tr><td>a32f534c4a</td><td>2016-09-09 16:28:22</td><td>30.521051</td><td>114.357306</td><td>30</td><td>有道词典</td></tr></table></body></html>

依据之前建立的本体模型，将数据从离散的原始数据输入本体，提取关联并进行情境组合：唯一标识、时间、地点、电量、任务，处理得出静态情境信息。如表6所示，该用户在某一时段在同一地点(某教学楼内)使用"有道词典"APP。接着，将处于不同元组中的APP相关信息提取出来，提取字段如表7所示。

表7数据集格式说明  

<html><body><table><tr><td>列</td><td>列名</td><td>说明</td></tr><tr><td>1</td><td>NA 行ID</td><td></td></tr><tr><td>2</td><td>Deviceid</td><td>设备 ID，同一手机内的不同 APP 应用使用 ID来关联</td></tr><tr><td>3</td><td>APP_name</td><td>对应不同用户不同的 APP，由"<app 分类名 称>.<app名称>"组成</td></tr><tr><td>4</td><td>timestamp</td><td>不同用户使用和终止APP时间</td></tr></table></body></html>

应用情境推理规则1，使用简单聚类算法求得某APP与其他APP间的相关关系，用于协同推荐服务。例如，设定7类APP：系统管理类，社会交流类，学习工具类，网络购物、支付类，检索工具类，休闲娱乐类,实用工具类。图6显示这7类APP根据用户使用频率相关性推导出的关联程度，其中节点代表APP、颜色代表APP类型，An代表聚类结果。

从图6可以发现,A2和A3内部相关程度较高。A2中的APP数量较少，但是在使用91(掌上阅读)和51(咪咕阅读)学习工具的同时，用户还倾向于使用记事本工具。即可根据此动态情境，在用户下载或使用阅读类APP时，进行记事本APP的主动服务推荐。

![](images/933c5273a294c7762a55f0724bc95950b5e52c5b164996c8ff3d5d9e3e5eed97.jpg)  
图6动态情境推理结果示例：根据用户使用频率相关性推导出7类APP的聚类

# 7结语

本文基于手机传感器与AWARE体系结构，设计了一个移动数据采集、推理、分析框架。针对APP使用情况与自定义推理规则，进一步对所获数据进行动态情境推理，得到用户规律并针对规律进行主动服务。实证表明，基于情境感知技术的移动数据采集能够实现基于数据的规范、推理与服务发现。这对数据采集的研究者来说，无疑是有支撑作用。结合国内移动数据采集的特殊环境进行移动采集系统的本地化、个性化，建立完整的情境推理系统，是今后需要努力的方向。

值得一提的是，MDCF所采集的数据适用于从情境原始数据到低层静态情境再到高层动态情境的有限推理。然而，这并不是情境感知的目的，情境感知的最终目的是优化服务。服务的种类多样，因此，可在此基础上，针对不同情境，发展多类服务体系。此外，运用中间件技术和相关关系算法进行高维度高层情境推理与行为发现，是情境计算领域未来的重要发展方向。

# 参考文献：

[1]李伟平，王武生，莫同，等．情境计算研究综述[J].计算机 研究与发展，2015，52(2):542-552.(Li Weiping，Wang Wusheng,Mo Tong,et al. Survey of Contextual Computing [J].Journal of Computer Research and Development,2015, 52 (2): 542-552.)   
[2] 莫同，李伟平，吴中海，等．一种情境感知服务系统框架 [J]．计算机学报，2010,33(11):2084-2092.(Mo Tong，Li Weiping,Wu Zhonghai,et al.Framework of Context-Aware Based Service System[J].Chinese Journal of Computers, 2010,33 (11): 2084-2092.)   
[3] Hassenzahl M,Tractinsky N.User Experience -A Research Agenda[J].Behaviour& Information Technology，2006, 25(2): 91-97.   
[4] LiW,Chu W,TungF,etal.AUniform Device Information Access for Context-Aware Middleware[C]//Proceedings of IEEE International Conference on Web Services. IEEE Computer Society,2010:654-657.   
[5]Abowd G D,Dey A K,Brown P J,et al. Towards a Better Understanding of Context and Context-Awareness[C]/ Proceedings of International Symposium on Handheld & Ubiquitous Computing，Karlsruhe,Germany.London,UK: Springer-Verlag,1999: 304-307.   
[6]Weiser M. Hot Topics-Ubiquitous Computing[J]. Computer, 1993,26(10): 71-72.   
[7]Imielinski T,Korth H F.Mobile Computing[M]. Boston Kluwer Academic,1996.   
[8]AndroidMobileContextInstrumentationFramework [EB/OL].[2017-02-10]. http://www.awareframework.com/.   
[9]Schilit B,Adams N，Want R. Context-Aware Computing Applications[C]// Proceedings of the Workshop on Mobile Computing Systems & Applications.Washington,USA: IEEE Computer Society,1994: 85-90.   
[10] Li W,Chu W, Tung F,et al.A Uniform Device Information Access for Context-Aware Middleware[C]// Proceedings of the 2010 IEEE International Conference on Web Services. Washington, USA: IEEE Computer Society,2010:654-657.   
[11] Xu C,Cheung S C. Inconsistency Detection and Resolution for Context-Aware Middleware Support[J].ACM SIGSOFT Software Engineering Notes,2005,30(5): 336-345.   
[12] 韩立，刘正捷,李晖,等．基于情境感知的远程用户体验数 据采集方法[J]．计算机学报，2015,38(11):2234-2246.(Han Li, Liu Zhengjie,Li Hui,etal.A Method Based on ContextAwareness for Remote User Experience Data Capturing [J]. Chinese Journal of Computers,2015,34(11): 2234-2246.)   
[13]薛霄，常静坤，曾志峰，等．基于情境感知的智慧矿山服 务系统研究[J]．计算机工程与科学，2013，35(9):36-44. (Xue Xiao,Chang Jingkun,Zeng Zhifeng，et al. ContextAware Intelligent Service System for Mine Industry [J]. Computer Engineering & Science,2013,35(9): 36-44.)   
[14]蒋达央，姚琪，季云．基于智慧校园的情境感知数据采集 的策略研究[J]．常州信息职业技术学院学报，2016,15(4): 29-31.(Jiang Dayang,Yao Qi, Ji Yun. Study on Strategies of Context Awareness Data Collection Based on Smart Campus [J].Journal of Changzhou Vocational College of Information Technology,2016,15(4): 29-31.)   
[15] Dey A K. Understanding and Using Context[J]. Personal and Ubiquitous Computing,2001,5(1): 4-7.   
[16]Biegel G,Cahill V.A Framework for Developing Mobile, Context-aware Applications[C]/Proceedings of the 2nd IEEE Conference on Pervasive Computing and Communications. IEEE,2004:361-365.   
[17]Korpipaa P,Mantyjarvi J,Kela J,et al.Managing Context Information in Mobile Devices[J]. IEEE Pervasive Computing,2003,2(3): 42-51.   
[18] Raento M,Oulasvirta A,Petit R,et al. ContextPhone:A Prototyping Platform for Context-Aware Mobile Applications [J].IEEE Pervasive Computing,2005,4(2): 51-59.   
[19] Wegdam M. AWARENESS: A Project on Context AWARE Mobile NEtworks and ServiceS[J].Mobile & Wireless Communication Summit,2005,6:19-23.   
[20] Carter S,Mankoff J,Heer J.Momento: Support for Situated Ubicomp Experimentation[C]// Proceedings of the SIGCHI Conference on Human Factors in Computing Systems, California, USA. New York, USA: ACM,2007:125-134.   
[21]Froehlich J,Chen MY，Consolvo S,et al. MyExperience:A System for in Situ Tracing and Capturing of User Feedback on Mobile Phones[C]// Proceedings of the 5th International Conference on Mobile Systems,Applications and Services. New York, USA: ACM,2007: 57-70.   
[22] Miluzzo E,Lane N D,Eisenman S B,et al.CenceMe InjectingSensingPresenceintoSocialNetworking Applications[C]// Proceedingsof EuroSSC 2007. Berlin, Germany: Springer, 2007: 1-28.   
[23] Rachuri KK,Musolesi M,Mascolo C,et al. EmotionSense: A Mobile Phones Based Adaptive Platform for Experimental Social Psychology Research[C]// Proceedings of the 12th ACM International Conference on Ubiquitous Computing, Copenhagen，Denmark．New York，USA:ACM，2010: 281-290.   
[24] Falaki H,Mahajan R,Estrin D. SystemSens:A Tool for Monitoring Usage in Smartphone Research Deployments[C]// Proceedings of the 6th International Workshop on MobiArch, Maryland, USA. New York, USA: ACM,2011: 25-30.   
[25]Ferreira D,Kostakos V,Dey A K.AWARE:Mobile Context Instrumentation Framework[J].Frontiers in ICT,2015,2: Article 6.   
[26] Kwon O B.Modeling and Generating Context-Aware AgentBased Applications with Amended Colored Petri Nets[J]. Expert Systems with Applications,2004,27(4): 609-621.   
[27] Henricksen K，Indulska J，Rakotonirainy A．Modeling Context Information in Pervasive Computing Systems[C]// Proceedings of the lst International Conference on Pervasive Computing.London,UK: Springer-Verlag,2002:167-180.   
[28] Wang W,Li W,Wu Z,et al. An Ontology-Based Context Model for Building Context-Aware Services[C]// Proceedings of the 2nd International Conference on Intelligent Systems, Modeling and Simulation.Washington,USA:IEEE Xplore, 2011:296-299.   
[29]Gruber T R．A Translation Approach to Portable Ontology Specifications[J].Knowledge Acquisition,1993,5(2):199-220.   
[30]郝倩．普适学习空间中情境建模及推理研究[D].大连：大 连理工大学,2011.(Hao Qian.Research on Context Modeling and Reasoning in Ubiquitous Learning Environment [D]. Dalian: Dalian University of Technology,2011.)   
[31]Li W,Xia Q.A Method of Concept Similarity Computation Based on Semantic Distance[J].Procedia Engineering,2011, 15:3854-3859.   
[32]刘宏岚，高庆狮，杨炳儒．多值逻辑中的命题相关性与逻 辑运算研究[J]．北京科技大学学报,2007,29(S2):172-177. (Liu Honglan，Gao Qingshi,Yang Bingru. Proposition Relativity and Logic Calculation in Many-Valued Logic [J]. Journal of University of Science and Technology Beijing, 2007,29(S2): 172-177.)   
[33]Chen H,Tolia S.Steps Towards Creating a Context-Aware Agent System[R].HPLaboratories Palo Alto,2001.   
[34] 张楚才，刘均岢，瞿绍军．一种基于本体和自定义规则的 情景推理方法[J]．计算机技术与发展，2014，24(4): 139-142.(Zhang Chucai,Liu Junke,Qu Shaojun.A Context Reasoning Method Based on Ontology and User-defined Rules [J].Computer Technology and Development,2014, 24(4): 139-142.)   
[35] McGuinness D L，Harmelened F.OWL Web Ontology Language Overview [EB/OL].[2004-02-10].https://www. w3.org/TR/2004/REC-owl-features-20040210/.   
[36]Horrocks I,Patel-Schneider P,Boley H,et al.SWRL:A Semantic Web Rule Language Combining OWL and RuleML [EB/OL].[2004-05-21].https://www.w3.org/Submission/ 2004/SUBM-SWRL-20040521/.

# 作者贡献声明：

夏立新：提出研究思路，设计研究方案;  
杨金庆：开发系统，采集、清洗和分析数据，起草论文;  
程秀峰：论文最终版本修订。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:yjq@mails.ccnu.edu.cn。  
[1]杨金庆.Mobile_Data_Collection.xlsx.MDCF系统采集数据.

收稿日期:2016-12-09   
收修改稿日期:2017-03-13

# Collecting Mobile Data Based on Content Awareness An Empirical Study

Xia Lixin Yang Jinqing Cheng Xiufeng (School of Information Management, Central China Normal University,Wuhan 430079, China)

Abstract:[Objective]This paper proposes the framework for a mobile data retrieval and analysis system based on context-awarenes,aiming tooptimize the relateddata mining procedures.[Context]Nowadays,the automatic dynamic and comprehensive applications for mobile data mining were stillbeing developed.[Methods]First, we proposed a framework tocollect mobiledata from theclient side with the helpof Android AWAREsensor.Thecolected data was received by the server automatically. Then, we designed an empirical study to analyze the retrieved APP usage data. [Results] The proposed system could efectively recommand useful APPs to the mobile users.[Limitations] More in-depth analysis was needed to examine the colected data.[Conclusions]The proposed framework could help us effectly retrieve and analyze mobile useage data, which benefits the contextual computing research and the mobile informaiton behavior studies.

Keywords: Context AwarenessApplication Framework Android Context Reasoning User Behavior