# 信息技术相关医疗不良事件的国内外现状与思考

曾可¹；王玉²；朱卫国1 21中国医学科学院北京协和医院信息管理处，北京，1007302中国医学科学院北京协和医院普通内科，北京，100730通讯作者：朱卫国，北京协和医院普通内科、信息管理处，100730，

E-mail:zhuwg@pumch.cn

【摘要】随着信息技术在医疗领域的深入应用，信息技术相关的医疗不良事件也不断增加。本文对国内外信息技术相关医疗不良事件的术语、概念和研究现状进行了梳理，从事件表现形式、系统组成要素、根本原因三个方面对其进行分类，并给出相应界定和案例说明。结合国内外相关研究，进一步探讨了信息技术相关医疗不良事件的应对策略，提出提高重视程度、鼓励上报以及建立规范化防范体系的解决方案。以期提高医疗行业对此类不良事件的认识和关注，为相关研究提供参考。

【关键词】医疗信息技术；信息系统；医疗不良事件；医疗差错；技术危害

【中图分类号】 R197.3

# Current Situation and Consideration of Information Technology related Medical Adverse Events

Zeng $\mathsf { K e } ^ { 1 }$ , Wang $\mathrm { Y u } ^ { 2 }$ , Zhu Weiguo1,2

1Department of Information Management, Peking Union Medical Collge Hospital, Chinese Academy of Medical Sciences &Peking Union Medical College,Beijing 100730,China

2Department of General Internal Medicine ,Peking Union Medical Colege Hospital, Chinese Academy of Medical Sciences &Peking Union Medical College,Beijing 100730, China

Corresponding author: Zhu Weiguo, Department of General Internal Medicine ,Peking Union Medical College Hospital, Chinese Academy of Medical Sciences &Peking Union Medical College,Beijing 100730, China; Email:zhuwg@pumch.cn

[Abstract] With the deep application of the information technology in the medical field, the number of information technology-related medical adverse events has been increasing. In this paper, the terms, concepts and research status of medical adverse events related to information technology are reviewed and classified from three aspects: manifestation, system composition and error causes. And the corresponding definitions and case descriptions are discussed. Combining with relevant research at home and abroad, this paper further explores the countermeasures of information technology-related medical adverse events,and proposes solutions to enhance attention, encourage reporting and establish a standardized prevention system. Hope to improve the awareness and attention of the medical industry to such adverse events, and provide reference for relevant research.

[Keywords] Health Information Technology; Information System; Medical Adverse events; Medical Error; Technical Hazards

# 前言

医疗不良事件是指临床诊疗活动中以及医院运行过程中，任何可能影响病人的诊疗结果、增加病人的痛苦和负担并可能引发医疗纠纷或医疗事故，以及影响医疗工作的正常运行和医务人员人身安全等的因素和事件[1]。美国每年因医疗不良事件导致患者死亡的案例约有40万～44万例，医疗不良事件已成为第三大死因[2][3]。随着医疗信息技术（Health Information Technology，HIT）广泛应用，利用信息技术减少不良事件、提升医疗安全，已成为应对医疗不良事件的一种重要策略。调查显示,计算机医瞩录入系统(Computerized Provider Order Entry,CPOE）每年可避免1740万例临床用药差错，减少率达 $1 2 . 5 \% ^ { [ 4 ] }$ 。条形码技术可使医嘱抄写过程及给药过程中的差错相对减少 $4 1 . 4 \%$ ，同时使潜在不良事件的发生率相对减少 $5 0 . 8 \% ^ { [ 5 ] }$ 。大量信息技术的应用，在减少医疗差错的同时，也逐渐成为导致医疗不良事件发生的一项重要因素。信息技术如果没有经过恰当的设计、实施和使用，其本身也会威胁到医疗质量和患者安全。研究显示，六分之一左右的医疗安全事故与医疗信息技术相关。HIT相关不良事件已成为医疗安全不可忽视的威胁之一[7]。近年来，人工智能应用可能对医疗安全造成危害的事件已有报道，例如IBMWatson对一位肺癌伴严重出血的患者提出了化疗和贝伐珠单抗的治疗建议，而贝伐珠单抗是一种可能引起严重出血的癌症药物8。人工智能用于辅助医疗决策有很大价值，但其本身的可靠性和安全性不应被忽视。

# 1信息技术相关医疗不良事件的定义

信息技术引起医疗不良事件的相关研究开始于21世纪初，随着全球医疗健康产业的现代化，以电子健康档案（Electronic HealthRecord，EHR）、计算机医嘱录入、临床决策支持系统（ClinicalDecision Support System，CDSS）等为代表的医疗信息技术能够显著地提高医疗服务的质量和效率，减轻医疗行业的负担，信息技术成为医疗行业的重要推动力[9]。随着信息技术在医疗领域应用的普及,研究人员发现，信息技术的应用产生了一种新型的医疗不良事件，这种不良事件会对患者或医护人员的安全造成危害[7]。信息技术相关的医疗不良事件目前尚无统一的定义，常见的术语有“Techologyinducederor]”、“Systemrelateder、““Information Technology Events[17]”等。Borycki EM等[18]认为信息技术引起的医疗不良事件是指在系统的设计与开发、实施与个性化定制、以及技术运用与新工作流程的交互过程中产生的医疗差错，这种差错通常发生在复杂的临床环境中，很难通过传统的软件测试方法检测出来。某些情况下这种不良事件可能会被用户注意到并及时纠正，比如，医生发现用药录入错误后进行修正。WeinerJP 等[15]创造性地提出“E-Iatrogenesis”一词，以定义因HIT技术应用而对患者造成的安全危害。Palmieri PA等[1提出“Technological Iatrogenesis”的概念，表示因技术创新融入复杂医疗系统时产生的新型医疗差错，警示用户应该提高对此类新风险的管理意识。

# 2信息技术相关医疗不良事件研究现状

自2005年起，国外关于HIT相关医疗不良事件的研究报道显著增加[。国内关于HIT相关不良事件的政策法规和文献报告极少。

美国急救医疗研究所（Emergency CareResearchInstitute，ECRI）每年发布《十大医疗技术危害》报告[19]，公布各医疗机构在使用医疗设备和系统时存在的安全问题，帮助医疗机构明确医疗技术存在的潜在危害。表1归纳出近6年ECRI发布的“十大医疗技术危害”中与信息技术相关的内容。

表 $1 2 0 1 4 { \sim } 2 0 1 9$ 年ECRI“十大医疗技术危害”中HIT 相关危害  

<html><body><table><tr><td>年份</td><td>医疗信息技术（HIT）相关危害</td></tr><tr><td rowspan="2">2014</td><td>电子病历和其他医疗信息系统数据不完整或不可靠</td></tr><tr><td>忽视联网设备与系统的变更管理</td></tr><tr><td rowspan="2">2015</td><td>电子病历和其他医疗信息系统数据不正确或不完整</td></tr><tr><td>联网医疗设备和系统保护不规范</td></tr><tr><td>2016</td><td>HIT 的配置和工作流程不匹配</td></tr><tr><td>2017</td><td>医疗设备软件管理设置缺陷影响患者数据安全</td></tr><tr><td rowspan="2">2018</td><td>医疗服务中的勒索软件和其它信息安全威胁可能会危及患者安全</td></tr><tr><td>未严格使用条码扫描给药系统而使其安全优势难以发挥</td></tr><tr><td>2019</td><td>黑客可利用远程访问医院信息系统，破坏医疗保健服务</td></tr></table></body></html>

2014年到2018年间，美国医疗机构评审联合委员会统计了170份与警报管理和警报疲劳有关的报告，其中有101起导致患者死亡，电子病历和医疗设备警报中的虚假警报占到 $8 5 \% - 9 9 \% ^ { [ 2 0 ] }$ ，这种过度警报造成的医疗安全风险极大，医务人员因大量不必要的警告而产生倦怠，以至于忽略了偶尔有意义的警告，从而导致医疗差错。

2011年，加拿大学者Bellwood Paule[21]对HIT 相关不良事件的影响因素进行了分析，将其归纳为：系统开发周期、知识/培训、工作流、人机交互、政策、用户参与等9个方面，并将这些因素归纳为个人、厂商、机构、政府这四个主题，这些主题间存在着复杂的交叉关系。

美国医疗器械不良事件报告数据库（Manufacturer and User Facility DeviceExperienceDatabase，MAUDE）收集了自1991年以来美国食品药品监督管理局（Food and DrugAdministration，FDA）接收的医疗器械不良事件报告，其中包含了大量HIT相关不良事件报告。表2罗列出近10 年信息技术相关患者死亡的部分典型案例[22]。

表2近10年MAUDE数据库中HIT相关的患者死亡事件案例  

<html><body><table><tr><td>事件时间</td><td>事件描述 事件发生原因</td></tr><tr><td>2008/12/18</td><td>患者主动脉内球囊导管破裂，血液在气动驱动线以上，但 系统告警消息故障 系统没有报警。</td></tr><tr><td>2009/8/11</td><td>患者进行X光检查期间，系统磁盘空间不足，无法运行 电脑故障 WINDOWS系统，系统多次重启期间，患者心梗死亡。</td></tr><tr><td>2009/12/5</td><td>软件程序错误设置为以1ml/hr 的速率输入1mg/ml 吗啡, 导致患者超剂量接受药物，大约一个小时后，设备发出警软件编程错误 报此时患者已死亡。</td></tr><tr><td>2010/1/24</td><td>患者进行心脏监测和血氧饱和度监测，其床边监测器的危 险警报音量被关闭，医护人员未及时发现患者心脏病发软件故障 作，最终患者死亡。</td></tr><tr><td>2014/12/6</td><td>在手术过程中，患者的血流动力学信息显示失真，最终患 应用程序异常退出 者死在手术台上。</td></tr><tr><td>2015/3/23</td><td>患者心室颤动，监护仪报警，护士没有发现。调查发现监 软件控制设置错误 护仪上的音调设置了5秒延迟（默认值是0秒）。</td></tr><tr><td>2015/7/1</td><td>一例急诊病例因心肌梗塞送达医院，在检查室准备进行干 预时系统自行关闭，重启系统两次但未成功。患者在转移操作系统问题 到其他医院期间死亡。</td></tr></table></body></html>

美国学者KangHong等[7][23][24]为了更好地了解当前HIT系统引起的不良事件的性质，构建了一套HIT事件识别策略，通过使用基于结构化特征的过滤器和基于非结构化特征的分类器来识别MAUDE 数据库中的HIT事件，并通过提取MAUDE 数据库中不良事件报告数据，建立了一个HIT事件专属数据库。

# 3信息技术相关医疗不良事件的类型

目前，国内外对于HIT相关医疗不良事件的分类方法并没有统一的界定和依据，因此，参考国外研究中的分类方法，结合具体工作，本文从表现形式、系统组成、错误原因三个方面对信息技术相关的医疗不良事件进行分类。

# 3.1按不良事件的表现形式分类

根据表现形式，将信息系统中的医疗差错归纳为：选择错误、使用错误、书写错误和系统错误[25]。

表3信息系统中不良事件表现形式  

<html><body><table><tr><td>类型</td><td>描述</td><td>举例</td></tr><tr><td>选择错误</td><td>从下拉菜单中错误选择了 药物/配方/途径/频率等</td><td>错误选择了硬膜外注射0.9%氯化钠，而非静 脉注射</td></tr><tr><td>使用错误</td><td>错误使用了药物/配方/给药 途径/频率等; 处方和药品说明相互矛盾</td><td>将硝酸甘油处方开为10mg/24h，1贴片，但 药品说明是50mg/24h</td></tr><tr><td>书写错误</td><td>内容出现书写错误</td><td>将150ug斯达力沃的每日剂量写成了37.5片</td></tr><tr><td>系统错误</td><td>系统发生提示错误、 默认时间/日期错误、与辅助 信息相关的错误等;</td><td>患者入院后医生开具急查血检验，当日已经 打印急查血条码并抽血化验，但系统中急查 血检验默认时间为次日凌晨，次日护士重新 打印条码并重复抽血</td></tr></table></body></html>

# 3.2按系统组成要素分类

在信息系统的各个关键节点中，由于系统或用户的原因，均可能导致不良事件发生。按照信息系统的组成要素，分为信息输入、信息传递、信息输出、通用技术、用户影响因素五种类型[26]。

表4按系统组成要素进行分类  

<html><body><table><tr><td>类型</td><td>描述</td><td>举例</td></tr><tr><td rowspan="2">信息输入</td><td>系统：数据采集故障</td><td>窗口人员在患者建档时，将姓名字段</td></tr><tr><td>用户：数据录入或记录问题</td><td>录入错误，影响医保报销</td></tr><tr><td>信息传递</td><td>系统：网络瘫痪或延迟、软件接口问题</td><td>医嘱系统中患者的口服药医嘱未及 时传入包药机系统，导致药品漏发</td></tr><tr><td rowspan="3">信息输出</td><td>系统：输入设备关闭、记录不可用、输患者到放射科取头部 MRI报告单时，</td><td></td></tr><tr><td>出/显示误差</td><td>自助机错误印制了其他患者的CT报</td></tr><tr><td>用户：数据查询、记录错误</td><td>告单</td></tr><tr><td>通用技术</td><td></td><td>计算机系统故障、访问问题、软件问题、计算机故障，导致检验结果的危急值</td></tr></table></body></html>

<html><body><table><tr><td>数据缺失等</td><td>接收失败</td></tr><tr><td>人员培训、认知负荷、不履行职责、职</td><td>用户对系统的功能和操作不熟悉，导</td></tr><tr><td>用户影响 业倦怠</td><td>致使用问题</td></tr></table></body></html>

# 3.3按事件的根本原因进行分类

参考美国医疗器械不良事件报告数据库对不良事件报告的分类方法，分为计算机问题、数据问题、报警问题、通讯问题、人机交互问题、应用系统问题等，其中每一类又可以细分为多种错误类型。

表5HIT相关不良事件的原因分类  

<html><body><table><tr><td>类型</td><td>描述</td><td>举例</td></tr><tr><td>计算机问题</td><td>硬件、操作系统、软件、系统安全问题</td><td>系统受到恶意入侵和攻击，导致药 品和耗材的供应链破坏</td></tr><tr><td>数据问题</td><td>数据备份问题、数据完整性问题</td><td>纸质和电子形式的数据共用，导致 患者部分数据缺失</td></tr><tr><td>报警问题</td><td>报警系统故障、错误或警告消息无法生成</td><td>系统未设置每日药物最大剂量警 示，导致患者超量用药</td></tr><tr><td>通讯问题</td><td>无线通讯问题、网络问题</td><td>网络故障造成远程操作失效、数据 丢失</td></tr><tr><td></td><td>程序异常退出、计算错误、参数设置错误、 应用系统问题功率计算错误、版本或升级问题、软件安</td><td>门诊高值系统和住院病房高值耗 材系统未关联，部分耗材未记账</td></tr><tr><td>人机交互问题人为因素、人机界面问题、使用问题等</td><td>装问题等</td><td>用户同时打开多个HIS界面，无意</td></tr></table></body></html>

# 4信息技术相关医疗不良事件应对策略探讨

2016年，加拿大学者BoryckiE等[27]针对信息技术引起医疗不良事件的现状，提出了“Cyclic Process of Improving HIT Safety”模型，用以概括 HIT 安全事件的解决方案（见图1）。

![](images/d561ecfc271d24cda2ba1ccf88601e7d103fb5a1a12b1293ed90aa8d3779a7c8.jpg)  
图1“Cyclic Process of Improving HIT Safety”模型

结合相关研究，对信息技术相关医疗不良事件提出几方面应对策略：

# 4.1重视信息技术相关医疗不良事件

无论是作为HIT使用方的医院，还是作为HIT提供方的供应商，以及作为监管方的各级行政机构，都应该对HIT相关医疗不良事件引起高度重视。针对医疗信息技术应用，加强安全隐患管理，采用多种技术和方法预测可能发生的差错，提前预防和纠正问题。对HIT不良事件发生的根本原因进行分析，制定有效的解决策略。随着人工智能技术在医疗行业的深入，AI应用更应该经过领域专家的严格把控，建立完善的测试机制和推广模式，才能保证医疗人工智能应用的安全可靠。

# 4.2鼓励信息技术相关医疗不良事件上报

医疗机构应该采取正向激励措施，鼓励HIT相关不良事件上报。将信息技术相关医疗不良事件纳入上报体系，建立HIT不良事件专属数据库，为统计分析提供数据支持，帮助研究人员分析HIT事件之间存在的关联和共通点，发展标准化HIT事件的分类体系。

# 4.3建立信息技术相关医疗不良事件防范体系

（1）系统设计方面：在设计之初即开始考虑患者安全问题，所有涉及关键医疗环节的程序设计都应该经过临床专家确认。系统设计的控制、默认值、自动计算、提示和警示等都需要严格遵循医疗原则。系统的界面和操作设计十分关键，应该确保系统的可用性、友好性、安全性。

（2）系统测试方面：建立规范的软件测试机制，对通讯网络、浏览器、运行环境、系统功能、承载能力、故障恢复能力等方面进行测试。核心业务系统不仅要进行软件安全认证，未来还应该考虑医疗安全认证。（3）系统实施方面：加强用户培训考核。不仅要培训系统的新模块、新功能，还应该培训系统的应急处理机制和HIT相关不良事件的应对策略。（4）系统运维方面：加强对软硬件的可用性监测，定期巡检，建立从运维事件中发现问题的机制，定期组织用户进行应急演练。（5）系统安全方面：制定健全的数据备份机制和应急管理策略，构建完善的信息安全保障体系。（6）用户使用方面：重视用户反馈，不断优化和改进。对于用户反馈的系统使用负担和倦怠感应该高度重视。简化重复性操作，优化人机交互。（7）信息共享：系统的最佳操作方式、安全隐患和应对策略都应该在用户间共享，建立用户之间、用户与技术人员之间的沟通机制。

总之，信息技术在医疗活动中发挥着越来越重要的作用，而信息技术相关医疗不良事件也随之出现，可能导致医疗差错，甚至可能危及生命。因此，应该重视信息技术相关医疗不良事件，提高对于医疗信息技术以及人工智能等新型技术的安全风险认识，在系统的设计、开发、实施、使用、运维等各个阶段引入安全管理理念，确保患者安全，才能充分发挥医疗信息技术的巨大价值。

# 【参考文献】

[1]医疗不良事件定义及分类[J].中国卫生质量管理,2014,21(04):28. [2] Schreiber M, Klingelhfer D, Groneberg DA, et al. Patient safety: the landscape of the global research output and gender distribution[J/OL].BMJ Open, 2O16, 6:8322. [3] Makary MA, Daniel M. Medical error—the third leading cause of death in theUS[J].BMJ,2016, 353:2139. [4] Radley,David C & Wasserman,Melanie R & Olsho, et al. Reduction in medication errors in hospitals due to adoption of computerized provider order entry

systems. Journal of the American Medical Informatics Association $:$ JAMIA, 2013, 20(3):470-476.   
[5] Poon EG, Keohane CA, Yoon CS, et al. Effect of bar-code technology on the safety of medication administration. N Engl J Med, 2010, 362 (18) :1698-1707. [6] Cheung KC, van der Veen W, Bouvy ML,Wensing M, van den Bemt PM, de Smet PA. Classification of medication incidents associated with information   
technology[J]. J Am Med Inform Assoc, 2014, 21(e1):e63-70.   
[7] Kang H, Yu Z, Gong Y. Initializing and Growing a Database of Health   
Information Technology (HIT) Events by Using TF-IDF and Biterm Topic Modeling. AMIA Annu Symp Proc, 2017,1024-1033.   
[8] Casey Ross, Ike Swetlitz. IBM's Watson supercomputer recommended ‘unsafe and incorrect' cancer treatments, internal documents show [EB/OL].   
https://www.statnews.com/2018/07/25/ibm-watson-recommended-unsafe-incorrect-tr eatments/, 2018-07-25   
[9] Borycki E. Trends in Health Information Technology Safety: From   
Technology-Induced Errors to Current Approaches for Ensuring Technology Safety. Healthcare Informatics Research,2013,19(2):69-78.   
[10] Kushniruk AW, Triola MM, Borycki EM, Stein B, Kannry JL. Technology induced error and usability: the relationship between usability problems and   
prescription errors when using a handheld application. Int JMed Inform, 2005, 74(7-8):519-26.   
[11] Borycki E, Kushniruk A. Identifying and preventing technology-induced error using simulations: application of usability engineering techniques. Healthc Q, 2005, 8:99-105.   
[12] Brushwood DB, Winterstein A.Manufacturer warnings of system-related medication errors. Am J Health Syst Pharm, 2002, 59(11):1110-2.   
[13] Ash JS,Berg M, Coiera E. Some unintended consequences of information technology in health care: the nature of patient care information system-related errors. J Am Med Inform Assoc, 2004,11(2):104-12. [14] Voight PE. Using safety tools to prevent system-related errors. AORN J, 2009, 89(6):969-70.   
[15] Weiner JP, Kfuri T, Chan K, Fowles JB.“e-Iatrogenesis": The Most Critical Unintended Consequence of CPOE and other HIT. Journal of the American Medical Informatics Association : JAMIA,2007, 14(3):387-388.   
[16] Palmieri PA, Peterson LT, Ford EW. Technological iatrogenesis: new risks force heightened management awareness. J Healthc Risk Manag, 2007, 27(4):19-24. [17] Abramson EL,Kern LM, Brenner S,Hufstader M, Patel V, Kaushal R. Expert panel evaluation of health information technology effects on adverse events. J Eval Clin Pract, 2014, 20(4):375-82.   
[18] Borycki EM, Kushniruk AW, Keay L, Kuo A. A framework for diagnosing and identifying where technology-induced errors come from. Stud Health Technol Inform, 2009,148:181-187.   
[19] Top 10 Health Technology Hazards for 2018[EB/OL]. [2018-08-12].   
https://www.ecri.org/Pages/2018-Hazards.aspx   
[20] Fred Schulte, Erika Fry. Death By 1,OO0 Clicks: Where Electronic Health Records Went Wrong[EB/OL].   
https://www.physicianspractice.com/article/death-10oo-clicks-where-electronic-health -records-went-wrong,2019-04-01   
[21] Bellwood, Paule. Qualitative Study of Technology-Induced Errors in Healthcare Organizations. M.Sc.University of Victoria (Canada),2011.   
[22] MAUDE - Manufacturer and User Facility Device Experience [EB/OL].   
[2018-10-10].   
https://www.accessdata.fda.gov/scripts/cdrh/cfdocs/cfmaude/search.cfm   
[23] Kang H, Yu Z, Gong Y. Initializing and Growing a Database of Health   
Information Technology (HIT)Events by Using TF-IDF and Biterm Topic Modeling. AMIA Annu Symp Proc,2018,2017:1024-1033.   
[24] Yao B, Kang H, Wang J, Zhou S, Gong Y. Exploring Health Information Technology Events from FDA MAUDE Database. Stud Health Technol Inform, 2018, 250:187-191.

[25] Westbrook JI1, Baysari MT, Li L, Burke R, et al. The safety of electronic prescribing: manifestations, mechanisms,and rates of system-related errors associated with two commercial systems in hospitals. J Am Med Inform Assoc. 2013,20(6): 1159-1167.

[26] Magrabi F, Ong MS,Runciman W, et al. Using FDA reports to inform a classification for health information technology safety problems.J Am Med Inform Assoc. 2012,19(1):45-53.

[27] Borycki E, Dexheimer JW, Hullin Lucay Cossio C, et al. Methods for Addressing Technology-Induced Errors: The Current State. Yearbook of Medical Informatics,2016,(1):30-40.