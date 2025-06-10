# 认知负荷取向下基于记忆一反应冲突的欺骗检

# 测

梁静1阮倩男²李贺3马梦晴1颜文靖²(1鲁东大学教育科学学院，烟台 264025)  
（2温州大学心理与行为科学研究所，温州325015）（3西北大学公共管理学院，西安710127）

摘要 欺骗检测一直是心理学的重要研究问题。基于欺骗理论的认知视角，研究者提出欺骗检测的认知负荷取向。采用隐瞒信息测试这一测谎范式，通过操纵认知负荷影响个体在虚假反应时的记忆-反应冲突解决过程，考察增加认知负荷对欺骗检测的影响，以期更好地揭示欺骗检测的认知机制。在此基础上，以普通人群和犯罪嫌疑人为被试探查基于记忆一反应冲突的欺骗检测的行为和生理指标，并根据获得的行为和生理指标，采用机器学习方法进行建模，预测个体的欺骗行为。研究结果将服务于司法、安防和人际交往等领域的欺骗检测。

关键词 欺骗检测；认知负荷；记忆一反应冲突；干扰任务；机器学习

# 1.问题提出

欺骗是指个体在知道事实真相的情况下，为了获得好处或者避免损失，故意地使用言语或者非言语信息使他人产生某种错误信念的行为（白学军,章鹏,张琪涵,宋璐,杨宇,2019;崔茜,蒋军,杨文静,张庆林,2013;张亭玉,张雨青,2008;Abe,2009,2011）。恶意欺骗往往会导致严重的后果。因此，及时有效地识别欺骗非常重要，能够帮助我们减少犯错的机会。欺骗检测一直是心理学的重要研究问题，引起了研究者的广泛关注。

早期很多欺骗检测研究基于欺骗者和诚实者情绪唤醒的差异来寻找欺骗线索（生理和行为差异）（Vrij,Granhag,&Porter,2010），然而，研究发现这些线索并不十分可靠（DePaulo et al.,2003;Sporer& Schwandt,2006,2007）。因此，一些研究者提倡转变欺骗检测取向以更有效地识别谎言。基于欺骗理论的认知视角（Suchotzki,Verschuere,VanBockstaele, Ben-Shakhar & Crombez,2017; Gamer, 2014; Meijer & Verschuere,2017; Spence etal.,2001; Zuckerman,DePaulo,&Rosenthal,1981），即欺骗伴随较高的认知负荷，需要耗费更多的认知资源，研究者提出欺骗检测的认知负荷取向（cognitive-load approach todeception detection）（Vrij,Fisher,Mann,&Leal,2006）。该取向提出由于欺骗本身需要较高的认知负荷，当增大说谎/说真话所需的认知负荷时，其对欺骗者影响更大，由此更能引发欺骗者和诚实者的生理和行为差异，这些差异可作为欺骗线索。

认知负荷取向下，研究者多采用“察言观色”的方法寻找欺骗线索（如表情、姿态、语调、语言内容等），Vrij，Fisher和Blank（2017）对相关研究进行元分析发现，该方法确实能够提高欺骗检测率，欺骗检测率可达 $71 \%$ 。然而，也有研究者提出Vrij等人的元分析存在方法问题，实际结果并非如此乐观（Levine,Blair,&Carpenter,2018），并且所获得的线索仍然面临着可靠性不足、分析困难等问题（梁静等,2014）。

近几十年来，有关记忆探测的研究已经对欺骗检测领域产生了很大的影响，研究者开始转换角度，通过记忆探测，即检验个体对关键信息（critical information）的再认（测真）来识别欺骗（Ben-Shakhar,2012）。当个体（如犯罪嫌疑人）头脑中存在关键信息（如犯罪相关信息）时，相比无关信息（irrelevant information），再认关键信息会引发其特定的生理心理反应。对于其他个体（如无辜者）而言，两类信息引发的生理心理反应是相似的。通过比较个体对关键信息和无关信息的反应差异对其是否说谎做出推断。另外，个体（如犯罪嫌疑人）往往对关键信息（如犯罪相关信息）进行再认时做出虚假反应（将“见过”反应为“没见过”，“记得”反应为“不记得”），引发记忆一反应冲突，这时个体需要抑制真实信息以及自动化的真实反应并将真实反应转换为虚假反应，上述反应抑制、反应冲突/监控等过程的参与使其耗费更多的认知资源（Christ,Van Essen,Watson,Brubaker,& McDermott,2009; Gamer & Berti, 2010; Hu, Wu,& Fu,2011; Kubo & Nittono,2009; Spenceetal.,2001）。那么基于认知负荷取向，采用增加认知负荷的方法是否影响欺骗者的冲突监控及反应抑制过程，从而增大欺骗者和诚实者的差异，提高欺骗检测率？基于该方法能否获得可靠的、具有生态学效度的欺骗检测指标？能否基于这些指标预测个体的欺骗行为？目前这方面的研究较少且结果不尽一致（Verschuere,Kobis,Bereby-Meyer,Rand,& Shalvi,2018）。本项目拟对上述问题进行探讨。

隐瞒信息测试（Concealed Information Test,CIT）是研究者广泛使用的测谎范式，其本质是对个体记忆痕迹的检测（Ben-Shakhar&Elaad,2003）。实验室环境下，被试首先要进行模拟犯罪环节，然后采用该测试进行测谎。该测试包括以下三类刺激：第一，探测刺激（Probe）是和犯罪信息相关的信息，一般只有罪犯和职权者（警察）才知道这些信息，而无辜者不知道这些信息。第二，无关刺激（Irrelevant）是和犯罪行为没有任何关系的刺激，无论是罪犯还是无辜者都无法识别这类刺激。第三，目标刺激（Target）其实也是无关刺激但是要求被试对其执行某种不同于探测刺激和无关刺激的特定反应，目的是维持被试的注意力。虽然所有被试对探测刺激和无关刺激再认时进行相同的行为反应（“否”反应），但由于探测刺激对“有罪”被试具有特定意义，对其做出虚假再认反应引发记忆一反应冲突，从而需要消耗更多的认知资源。综上，本项目采用隐瞒信息测试，通过在该测试中设置干扰任务增加认知负荷（Vrij etal.,2006），从而系统考察增加认知负荷是否提高基于记忆一反应冲突的欺骗检测的准确率；在此基础上，本项目以普通人群和犯罪嫌疑人为研究对象，采用合适的干扰任务，探查基于记忆一反应冲突的欺骗检测的行为和生理指标。本项目还拟采用机器学习的方法，基于所获得的行为和生理指标预测个体的欺骗行为。

# 2研究现状

# 2.1干扰任务对基于记忆一反应冲突的欺骗检测的影响

个体对真实记忆进行虚假反应时首先需要提取真实信息，并将其保留在工作记忆中（Debey,Houwer,&Verschuere,2014）；同时需要抑制真实反应，并将真实反应转换为欺骗反应（Debey,Liefooghe,De Houwer,& Verschuere,2015）。上述工作记忆、反应抑制和任务转换三个执行功能成分参与整个欺骗过程，使得欺骗耗费更多的认知资源（Christ et al.,2009; Gamer & Berti,2010; Hu, Wu,& Fu,2011; Kubo & Nittono,2009; Spence et al.,2001）。因此，研究者通常在隐瞒信息测试中设置干扰执行功能成分的伴随任务以增加认知负荷，考察干扰任务是否增大欺骗者和诚实者的行为和生理差异进而提高欺骗检测率。

Ambach，Stark，Peper 和 Vaitl（2008）在基于测谎仪的隐瞒信息测试中增加Go/No-go干扰任务，考察反应抑制干扰任务是否促进欺骗检测。该研究记录了反应时行为指标和皮肤电、呼吸、心率生理指标，结果发现，反应抑制干扰任务没有增大各指标在探测刺激和无关刺激间的差异，并未促进欺骗检测。随后，Ambach，Stark和Vaitl（2011）在基于测谎仪的隐瞒信息测试中引入n-back干扰任务，考察工作记忆干扰任务是否促进欺骗检测，同样记录反应时行为指标和皮肤电、呼吸、心率生理指标，结果发现工作记忆干扰任务增强探测刺激和无关刺激间在皮肤电指标的差异，减弱其在呼吸和心率指标的差异；但是工作记忆干扰任务并未促进欺骗检测。

一些研究发现反应时是探测记忆的有效指标（Gamer,2011; Rosenfeld,2011），而基于测谎仪的隐瞒信息测试更加关注生理指标的测量，不限制反应时间，导致反应时指标不敏感，因此研究者采用基于反应时的隐瞒信息测试对上述问题进一步考察。Visu-Petra，Varga，Miclea和Visu-Petra（2013）考察干扰任务是否促进欺骗检测，该研究设置了工作记忆干扰任务（说出前面3个项目每个项目的最后一个单词）和任务转换干扰任务（项目以黑体呈现按键一次，项目以斜体呈现按键两次），结果发现工作记忆和任务转换干扰任务增大欺骗者和诚实者在反应时指标上的差异，但可能由于任务难度不够导致干扰造成的差异不足以促进欺骗检测。Hu，Evans，Wu，Lee和Fu（2013）考察了点探测干扰任务对欺骗检测的影响。该干扰任务主要涉及任务转换成分，研究结果发现干扰任务能够增大欺骗者和诚实者在反应时指标上的差异，促进欺骗检测。

以往研究发现执行功能的三个成分与欺骗能力有不同的相关。个体的反应抑制和任务转换能力与欺骗速度和欺骗正确率正相关，而工作记忆能力与欺骗速度负相关（Visu-Petra,Miclea,&Visu-Petra,2012）。由此推测，三个成分在欺骗中的不同作用可能导致不同干扰任务对欺骗检测的影响及其大小不同。已有研究发现任务转换干扰任务可能促进欺骗检测，而反应抑制和工作记忆干扰任务的作用仍需进一步研究。另外，如前所述，Visu-Petra 等（2013）发现任务转换干扰任务并未促进欺骗检测，可能由于其所采用的干扰任务相对简单（正确率为 $93 \%$ ），并未对个体造成很大的认知负荷。因此干扰任务的难度也可能影响欺骗检测的结果。

综上，本项目拟在隐瞒信息测试中设置不同性质和难度的干扰任务，系统考察增加认知负荷是否促进基于记忆一反应冲突的欺骗检测。

# 2.2多指标的欺骗检测 反应时和ERP指标

如前所述，在考察增加认知负荷对欺骗检测的影响时，反应时可能是更为理想的行为指标。同时，反应时也是目前许多研究者一致认为有效的欺骗检测行为指标（Seymour&Kerlin,20o8; Verschuere,Rosenfeld,Winograd,Labkovsky,& Wiersema,20o9; Verschuere &DeHouwer, 2011; Verschuere & Kleinberg,2016; Visu-Petra,Bus,& Miclea,

2011）。Seymour，Seifert，Shaft和Mosmann（2000）比较了被试对犯罪相关信息、无关信息和特定信息的反应时差异，结果发现反应时指标对犯罪者和无辜者的鉴别率分别为 $89 \%$ 和 $100 \%$ 。最近，Suchotzki等（2017）对114项研究进行元分析发现，欺骗比说真话需要耗费更长的时间，这一结果也表明反应时可用来测谎。

个体欺骗过程中出现的自主神经系统反应（autonomic response）通常作为欺骗检测的生理指标，如皮肤电、呼吸和心率等。由于神经活动或大脑功能激活水平能够比自主神经系统更直接地反映认知和情绪的变化，研究者提出采用中枢神经系统反应指标（如ERP、fMRI指标）代替自主神经反应指标（Rosenfeld,Soskins,Bosh,&Ryan,2004）。研究发现，ERP技术的测谎准确率和 fMRI相似，且更加经济、便捷（Rosenfeld etal.,2008），因此被广泛使用（Meijer,Selle,Elber,&Ben-Shakhar 2014）。P300 是目前测谎技术中最常用的一种ERP成分，是一种表征“识别”的生理信号，当被试对某些犯罪活动细节有关的隐藏信息进行识别时，则会诱发P300，研究者正是利用P300的这一特性进行测谎。因此，本项目关注ERP指标，尤其是P300成分。

此外，许多研究者提出应结合多种指标来进行测谎（Ambach etal.,2010;Bhutta,Hong,Kim,& Hong,2015; Gamer, Verschuere, Crombez,& Vossel,2008; Gronau, Ben-Shakhar,&Cohen,2005;Hu,Pornpattananangkul,&Rosenfeld,2013）。大多数研究将行为和生理指标结合来探究欺骗过程中的行为和生理变化，发现结合指标测谎效果优于单一指标（Gronau,Ben-Shakhar,& Cohen,2005; Hu & Rosenfeld,2012; Rosenfeld et al.,2004; Vincent & Furedy,1992）。综上，本项目拟探查反应时和ERP指标结合在基于记忆一反应冲突的欺骗检测中的有效性。

# 2.3机器学习预测个体欺骗行为的研究现状及趋势

近年来，认知神经科学领域一个持续的研究热点是利用机器学习的方法从神经激活模式中解码大脑状态（Haxby,2012）。Davatzikos等人（2005）首次将支持向量机（supportvector machine,SVM）运用于欺骗检测领域。他们使用 SVM区分欺骗反应和诚实反应所导致的大脑激活模式，结果发现该方法可以达到高于 $90 \%$ 的鉴别率。此外，后续研究者也采用 SVM对欺骗反应和诚实反应的脑电信号进行鉴别，同样发现可达到高于 $90 \%$ 的鉴别率（高军峰,王沛,郑崇勋,2010;赵敏,郑崇勋,赵春临,2010; Simbolon,Turnip,Hutahaean,&Siagian,2015）。研究者还比较了SVM、线性判别分析（linear discriminant analysis）、K近邻法（k-nearest neighbor）和反向传播神经网络（back propagation neural network）四种不同机器学习方法对欺骗反应和诚实反应的脑电信号的鉴别效果，发现分别可达到$74 . 5 \%$ ， $7 9 . 4 \%$ ， $9 7 . 9 \%$ 和 $89 \%$ 的鉴别率（Haider, Jiang, Jamshed,Pervaiz,& Mumtaz,2018）。综上，本项目拟采用机器学习方法，探索与验证所获指标用于个体欺骗行为预测的有效性。

# 3研究构想

本项目在认知负荷取向下，主要采用隐瞒信息测试这一测谎范式进行欺骗检测研究。首先，本研究通过设置不同性质和难度的干扰任务系统探究增加认知负荷对基于记忆一反应冲突的欺骗检测的影响；其次，在此基础上，以普通人群和犯罪嫌疑人为被试探查基于记忆一反应冲突的欺骗检测的行为和生理指标——反应时和ERP指标，考察反应时和 ERP结合指标的鉴别力。本项目还拟基于获得的反应时和ERP指标，采用机器学习方法进行个体欺骗行为的预测。

研究问题 研究内容 研究方案  
n  
知负 认操 难扰性质和 EXP1 不同难度的反应抑制千扰任务对欺骗 GO/T+-g0  
荷取向 负纵 反应冲突的欺骗检 中 EXP2 不同难度的工作记忆干扰任务对欺骗 延迟匹配任务  
1  
露 不同难度的任务转换干扰任务对欺骗 CIT+  
士 行 EXP3 检测的影响 判断任务  
记忆一反 五标 美 ExP 以普通人群为被试的基于记忆一反应 CTP+  
四  
中  
突的欺骗检 欺行为 个体欺骗行为的预 A  
隧

3.1研究一：干扰任务的性质和难度对基于记忆一反应冲突的欺骗检测的影响

研究一在隐瞒信息测试基础上设置干扰任务以增加个体的认知负荷，进而考察增加认知负荷对基于记忆一反应冲突的欺骗检测的影响，以及探讨不同性质和难度的干扰任务对基于记忆一反应冲突的欺骗检测的不同影响。

实验1考察不同难度的反应抑制干扰任务对基于记忆一反应冲突的欺骗检测的影响。反应抑制是指抑制不符合当前需要的或不恰当行为反应的能力，它对人们在环境变化时做出灵活的和目标指向的行为至关重要（Aron,Robbins,&Poldrack,2004;Booth etal.,2004;Diamond,2013）。Go/No-go 任务（Trommer,Hoeppner,Lorber,& Armstrong,1988）是反应抑制研究中常用的任务，通常包括两种刺激，一种是高频刺激（如字母X），另一种是低频刺激（如字母O），任务中要求个体对高频刺激进行反应，对低频刺激不做反应。被试对低频刺激的错误反应通常被认为是反应抑制困难的指标。任务难度可以通过操纵高频刺激和低频刺激的比率变化得以改变（Thorell,Lindqvist,Bergman,Bohlin,&Klingberg,2009）。参照以往实验（Ciesielski,Harris,&Cofer,2004），本实验拟采用Go/No-go干扰任务，设置高频刺激和低频刺激的比率分别为3:1和1:3，考察不同难度的反应抑制干扰任务对基于记忆一反应冲突的欺骗检测的影响。

实验流程：将被试随机分为犯罪组和无辜组。犯罪组被试完成六个阶段的任务：模拟犯罪阶段、犯罪细节回忆阶段、靶刺激学习阶段、无干扰隐瞒信息测试阶段、简单干扰隐瞒信息测试阶段和困难干扰隐瞒信息测试阶段。

（1）模拟犯罪阶段：要求犯罪者进入实验室盗取带有秘密资料的一张黄色的光盘。被试推开门进入实验室（门没锁），门后有一把抵着门的椅子。实验室里有一个书柜，书柜上面笔记本旁边有一把钥匙，用钥匙打开书柜下面的抽屉，发现一张音乐卡，里面夹有光盘。

（2）犯罪细节回忆阶段：犯罪者回到测试室，询问其关于上述犯罪细节的问题，确保其清晰记得这些细节。（3）靶刺激学习阶段：要求被试记忆5个词，作为隐瞒信息测试的靶刺激。被试需要在隐瞒信息测试阶段对这些词按“是”键，对其余词按“否”键。（4）无干扰隐瞒信息测试阶段：该测试包含3类刺激：5个探测刺激（实验室、光盘、椅子、笔记本、音乐卡），5个靶刺激（图书馆、U盘、桌子、计算器、录音带），20个无关刺激（与探测刺激字数和类别相同的其他词）。所有刺激随机重复4次。实验过程如下：首先屏幕中央随机呈现注视点‘ $^ { \cdot } + ^ { \cdot \gg } 5 0 0 { \sim } 7 5 0 \mathrm { m s }$ ，接着呈现刺激 $3 0 0 \mathrm { { m s } }$ ，然后是 $1 0 0 0 \mathrm { { m s } }$ 的空白屏，要求被试在看到刺激后尽快反应是否见过该刺激。对靶刺激做见过的反应，按“是”键；对其他刺激做没见过的反应，按“否”键。因此，对无辜组被试来说，其对探测刺激为诚实反应；对犯罪组被试来说，其对探测刺激为欺骗反应。所有被试对无关刺激做诚实反应。

（5）简单干扰隐瞒信息测试阶段：首先屏幕中央呈现注视点‘ $^ { \cdot } + ^ { \cdot \gg } 5 0 0 { \sim } 7 5 0 \mathrm { m s }$ ，接下来呈现字母X或 $\mathrm { ~ O ~ } 1 0 0 { \sim } 2 5 0 \mathrm { m s }$ ，当呈现字母X时，按空格键进行反应，呈现字母O时不反应。字母X与O的呈现比率为1:3。字母消失后呈现刺激 $3 0 0 \mathrm { { m s } }$ ，被试对刺激的反应要求同阶段（4），所呈现刺激同阶段（4），然后是 $1 0 0 0 \mathrm { { m s } }$ 的空白屏。

（6）困难干扰隐瞒信息测试阶段：该阶段同（5），不同之处仅在于字母X与O的呈现比率为3:1。

对于无辜组被试，告知其需要帮助研究人员进入实验室取一张光盘，随后同样对其进行细节测试。随后的实验任务与犯罪组相同。

其中无干扰隐瞒测试阶段、简单干扰隐瞒测试阶段和困难干扰隐瞒测试阶段的顺序在被试间平衡。

已有研究发现，冷酷无情特质是一种与暴力犯罪相关的人格倾向（肖玉琴,张卓,宋平,杨波,2014），本实验要求所有被试完成上述阶段任务后填写《冷酷无情特质量表》。

# 实验数据分析：

统计比较犯罪组和无辜组被试的性别和年龄无显著差异，以保证各组被试的同质性。对无干扰隐瞒信息测试阶段、简单干扰隐瞒信息测试阶段、困难干扰隐瞒信息测试阶段的数据进行组别（犯罪组vs.无辜组） $\times$ 刺激类型（探测刺激vs.无关刺激）的方差分析。关注反应时和正确率指标。将《冷酷无情特质量表》得分作为协变量，以排除个体差异对实验结果造成的影响。

采用平均反应时、反应时方差、错误率进行回归分析，计算三种条件下的分类正确率、击中率和正确拒绝率。随后每种条件下的上述三个指标转化为z分数，随后将每种条件下的三个z分数平均形成一个新的z分数。基于该指标，采用信号检测法计算三种条件下对犯罪组和无辜者的鉴别力，并采用Z检验计算三种条件下的鉴别力是否差异显著。

实验2考察不同难度的工作记忆干扰任务对基于记忆一反应冲突的欺骗检测的影响。工作记忆是执行功能的一个重要成分。在工作记忆的保持阶段，前额叶皮层广泛激活。随着工作记忆任务难度的增加，前额叶激活的范围和强度也随之增加。当工作记忆任务的难度增大，被试在工作记忆保持的过程中所耗费的认知资源也随之增加。根据 Baddeley（Baddeley& Hith,1974）的工作记忆模式，工作记忆系统包含三个成分：语音环路（phonologicalloop）、视觉空间模板（visuospatial sketchpad）及中央执行系统（central executive）。在此基础上，将工作记忆区分为言语工作记忆和视空间工作记忆。本实验将分别考察不同难度的言语工作记忆干扰任务和视空间工作记忆干扰任务对欺骗检测的影响。实验2a拟采用字母延迟匹配任务来考察不同难度的言语工作记忆干扰任务对欺骗检测的影响。实验2b拟采用空间位置延迟匹配任务考察不同难度的视空间工作记忆干扰任务对欺骗检测的影响。

实验流程：同实验1，仅在阶段（5）和阶段（6）有所差别。

实验2a过程如下：首先屏幕中央呈现注视点 $^ { \alpha } + ^ { \gamma } 5 0 0 { \sim } 7 5 0 \mathrm { m s }$ ，接下来随机呈现大写字母 $3 0 0 { \sim } 5 0 0 \mathrm { m s }$ ，要求被试记忆这些大写字母。简单条件下呈现4个大写字母，困难条件下呈现8个大写字母。字母消失后呈现刺激 $3 0 0 \mathrm { { m s } }$ ，然后是 $1 0 0 0 \mathrm { { m s } }$ 的空白屏，要求被试看到刺激后尽快反应是否见过这些刺激。反应结束后单独呈现一个小写字母，要求被试忽略大小写，判断这个小写字母是否为刚才出现过的字母。

实验2b过程如下：首先屏幕中央呈现注视点 $^ { * } + ^ { , 3 } 5 0 0 { \sim } 7 5 0 \mathrm { m s }$ ，接下来在电脑上呈现$1 5 ^ { * } 1 5$ （cm）的方块 $3 0 0 { \sim } 5 0 0 \mathrm { m s }$ ，方块共16格。在简单条件下，一个黑色方块随机出现在十六格中的任意一格，被试需要记忆这个方块出现的位置。在困难条件下，五个黑色方块随机出现在十六格中的任意五个位置，被试需要在同样的时间内记忆五个黑色方块的准确位置。方块消失后呈现刺激 $3 0 0 \mathrm { { m s } }$ ，然后是 $1 0 0 0 \mathrm { { m s } }$ 的空白屏，要求被试看到刺激后尽快反应是否见过这些刺激。反应结束后呈现带有黑色方块的方格，判断黑色方块的位置与刚刚出现的是否一致。

实验数据分析与实验1类似。

实验3考察不同难度的任务转换干扰任务对基于记忆一反应冲突的欺骗检测的影响。任务转换是认知灵活性的重要心理成分，即个体要认识到当前的认知定向是不合适的，随即停止当前的认知定向，并改变为一种新的认知定向，使得个体的行为系统与环境的新要求很好地协调起来（Woodward,Ruff,&Ngan,2006）。任务转换一般要求被试在任务A和任务B或者A反应和B反应之间进行转换。任务转换时会出现转换损失（switch cost）（Monsell,2003）。本实验参照以往研究（王艳梅,郭德俊,2008），要求被试对某种颜色的靶数字做奇偶分类任务。

实验流程：同实验1，仅在阶段（5）和阶段（6）有所差别。

（5）简单干扰隐瞒信息测试阶段：首先屏幕中央呈现注视点‘ $^ { * } + ^ { * } 5 0 0 { \sim } 7 5 0 \mathrm { m s }$ ，接下来呈现靶数字和分心数字 $3 0 0 { \sim } 5 0 0 \mathrm { m s }$ ，要求被试判断某种颜色的靶数字是否为偶数，在靶数字的上下两个位置的任意位置有另一种颜色的数字作为分心物。靶数字和分心数字在任何时候保证奇偶不同。颜色为红、绿、黄、蓝四种颜色中的任意两种。靶数字和分心数字为 $0 \sim$ 9中的任意两个。每15个试次靶数字和随机数字的颜色转换一次。数字消失后呈现刺激$3 0 0 \mathrm { { m s } }$ ，然后是 $1 0 0 0 \mathrm { { m s } }$ 的空白屏，要求被试看到刺激后尽快反应是否见过这些刺激。

（6）困难干扰隐瞒信息测试阶段：该阶段同（5），不同之处在于干扰任务不仅包括靶数字判断，还包括靶字母判断，要求被试判断靶字母是否为元音。靶数字判断和靶字母判断随机出现，每组靶数字和靶字母的颜色相同，分心数字和分心字母的颜色相同。

实验数据分析与实验1类似。

3.2研究二：认知负荷取向下，基于记忆一反应冲突的欺骗检测的反应时和ERP指标

自传体内隐联想测试（autobiographical Implicit Association Test,aIAT）是近年来发展起来的探测犯罪相关记忆的测试，并且研究发现综合采用自传体内隐联想测试和隐瞒信息测试更能提高欺骗检测率（Sartori,Agosta,Zogmaister,Ferrara,& Castiello,2008）。Hu 和Rosenfeld（2012）首次综合采用自传体内隐联想测试和隐瞒信息测试，并记录欺骗行为的反应时和ERP指标，结合这两个指标探究其对欺骗行为的鉴别力。综上，本研究采用自传体内隐联想测试和隐瞒信息测试，收集反应时和ERP指标，并将反应时和ERP指标相结合，采用信号检测方法从群体层面考察结合指标的鉴别力。基于Hu等（2013），本研究在上述测试中设置点探测干扰任务，考察认知负荷条件下上述指标的鉴别力。

实验4a以普通大学生为研究对象，探查反应时和ERP指标在普通人群的鉴别力；由于实验室测谎研究大多以普通人为被试通过模拟犯罪情景开展实验，生态效度较低，能否适用于现场测谎及法庭科学的实践，一直被研究者质疑（刘鑫,位东涛,张庆林,郭英慧,2018）。付翠（2011）首次将ERP测谎用于31例涉案犯罪嫌疑人，用案件真实结果来印证ERP 测谎的真实性，结果显示其正确率低于实验室的测谎效果。基于此，实验4b以真正的犯罪嫌疑人为研究对象，以真实犯罪现场为素材，提高生态效果，探查反应时和ERP 指标在犯罪人群的鉴别力，以便推动该指标在刑事侦查工作中的应用。

实验4a流程：被试进入实验室后，被随机分为犯罪组或无辜组。对于犯罪组被试，首先要执行模拟犯罪任务。主试宣读指导语：“现在你要想象自己是个小偷，行为实验室里面有个值钱的东西，在一个小盒子里面，你去把它偷出来”。被试会在一个桌子的抽屉里面发现一个戒指盒，然后把戒指偷走，装在口袋里面带出行为实验室。无辜组被试只需要进入行为实验室参观一下，并要求帮忙拿出来一篇文章。

所有被试首先参加脑电实验，然后参加自传体内隐联想测试。干扰任务参照 $\mathrm { H u }$ 等（2013），要求被试完成点探测任务（判断两个点是横向排列还是竖向排列）。

参照Rosenfeld等（2008），脑电实验流程如下：首先呈现“ $+ ^ { , }$ 注视点 ${ 5 0 0 } \mathrm { \sim } 7 0 0 \mathrm { m s }$ 随后呈现两个点 $3 0 0 { \sim } 5 0 0 \mathrm { m s }$ ，要求被试判断两个点是否为横向排列，如果“是”，右手按鼠标左键，如果“不是”，右手按鼠标右键，接着呈现实验刺激 $3 0 0 \mathrm { { m s } }$ ，要求被试尽快用左手按反应盒的任意键进行反应，实验刺激包括一个探测刺激（戒指），八个无关刺激（文章、项链、发卡、手表、手链、耳环、手镯、帽子），其中无关刺激中包括无辜组被试执行的操作（文章）。反应结束后呈现五个相同数字组合中的一个（11111,22222,33333,44444或55555） $3 0 0 \mathrm { { m s } }$ ，要求被试对靶刺激（11111）右手按鼠标左键反应，对其他非靶刺激右手按鼠标右键反应。一个探测刺激和八个无关刺激随机重复50次，共450个试次。

自传体内隐联想测试共包括5个区组：第1个区组要求被试对正确句子按“F"键（如我是一名学生；我坐在电脑前），对错误句子按“J"键（如我是一名老师；我坐在小河边），共20个试次；第2个区组要求被试对犯罪相关句子按“F"键（如我最近偷了一枚戒指），对犯罪无关句子按“J"键（如我从没偷过戒指），共20个试次；第3个区组要求被试对正确句子或犯罪相关句子按“F"键，对错误句子或犯罪无关句子按另“J"键，共60个试次（这个区组对犯罪者来说两类反应一致，而对无辜者来说不一致）；第4个区组要求被试对第2个区组的句子做与原来相反的按键，共40个试次；第5个区组要求被试对正确句子或犯罪无关句子按“F"键，对错误句子或犯罪相关句子按“J"键，共60个试次（这个区组对犯罪者来说两类反应不一致，而对无辜者来说一致）。每个试次首先呈现“ $+$ 注视点 ${ 5 0 0 } \mathrm { \sim } 7 0 0 \mathrm { m s }$ ，随后呈现两个点 $3 0 0 { \sim } 5 0 0 \mathrm { m s }$ ，要求被试判断两个点是否为横向排列，如果是，按“是”键，如果“不是”，按“否”键，接着呈现句子 $1 0 0 0 \mathrm { { m s } }$ ，被试按要求进行反应。

# 实验数据分析：

统计比较犯罪组和无辜组被试的性别和年龄无显著差异，以保证各组被试的同质性。

脑电实验分析：对实验刺激反应时、P300 波幅进行组别（犯罪组vs.无辜组） $\times$ 刺激类型（探测刺激vs.无关刺激）的方差分析，并基于刺激反应时、P300波幅采用信号检测方法计算鉴别力。

自传体内隐联想测试数据分析：D分数为止值意味着测试者倾向于将犯罪相关句子和正确句子相联系，D分数为负值意味着测试者倾向于将犯罪无关句子和正确句子相联系。对D分数进行犯罪组和无辜组的T检验，并基于D分数采用信号检测方法计算鉴别力。

实验4b选取30名在押犯罪嫌疑人参与实验，经筛查无生理或精神疾病，且满足以下条件：其犯罪现场信息齐全；已供认自己的犯罪行为，可比对真实和测谎结果；所犯罪行均为故意杀人未遂，刑罚后果较为严重。

脑电实验刺激为作案工具，其中探测刺激来自无关的犯罪现场，无关刺激来自无关的犯罪现场。自传体内隐联想测试刺激为犯罪细节相关句子，包括作案工具、现场痕迹、尸体、现场概貌。

实验流程同实验4a。

实验数据分析同实验4a。

3.3研究三：个体欺骗行为的预测

机器学习方法被广泛应用于各种领域，如文本分析、语音识别、面孔识别等，同时在神经影像数据分析中也得到了良好的应用。本研究拟选择目前在神经影像数据分析中常用的SVM、线性判别分析、K近邻法和反向传播神经网络等机器学习算法，探索如何结合不同分类器的特点实现对个体欺骗行为的有效预测。本部分拟分析的数据为研究一、研究二中的反应时和ERP数据。

ERP数据是神经元活动的体现，它由一系列特定的震荡成分组成，伴随着认知状态的改变，波形的变化往往也伴随频率特征的改变，因此ERP数据不仅包含丰富的时域信息，也包含了丰富的频域信息。本部分重点关注如何选择及提取合适的ERP时域及频域信息来预测欺骗行为。本研究还将结合不同的特征选择与提取方法，探索预测欺骗行为最有效的算法。

# 4理论构建

本项目中欺骗检测的认知机理在于，欺骗者对探测刺激做虚假反应时会产生记忆-反应冲突，如果在冲突解决过程中增加其认知负荷，会导致冲突更难解决，使反应时增加及正确率降低，并体现于神经生理的变化。通过认知负荷的操纵，增大欺骗者和诚实者表现的差异，进而促进欺骗检测。理论框架如图2所示。

![](images/cc96ca887cd3038ef8d3cd73bc4c7a22c5245cc862260cdc37eba22685c4e130.jpg)  
图2基于认知负荷的测谎原理

第一、CIT过程中欺骗者对探测刺激反应时存在记忆-反应冲突。基于认知负荷取向的测谎与基于情绪唤醒假设的测谎理论不同。传统欺骗检测多是基于情绪唤醒假设，该假设认为欺骗者被问到关键问题时（如“你是否偷了钱”）会产生特定情绪（如害怕被发现），身体唤醒水平升高，从而表现出不同于说真话时的生理和行为反应。然而根据美国国家研究委员会的详细报告（National Research Council,2003），这个假设的理论基础非常薄弱。欺骗者并不一定表现出身体唤醒水平升高，相反，诚实者有可能在被问到关键问题时由于焦虑表现出较高的唤醒水平。在此背景下，研究者提出了基于认知负荷这一测谎新取向。隐瞒信息测试中，欺骗者对头脑中存在的真实记忆（探测刺激）做出虚假反应时，便形成了记忆一反应之间的冲突，冲突的顺利解决需要反应抑制等执行功能成分的参与，同时消耗一定的认知资源。诚实者对探测刺激的反应为真实反应，无认知冲突存在。本项目在认知负荷取向下，通过操纵/增加认知负荷，考察其对欺骗者和诚实者反应的不同影响，以及对欺骗检测的影响。

第二，“第二任务”将增加CIT过程中的认知负荷。信息加工的观点认为人的认知能力是有限的，个体在特定的时间内执行任务的数量或可以利用的认知资源是特定并且有限的。当人们需要同时执行多个任务时，有限的认知资源需要在多个任务间进行分配，引发资源调用冲突。当用于某个特定任务的认知资源较少时，任务完成会变得困难，任务成绩也会下降。研究者通常采用让被试同时执行多种任务的方式来增加其认知负荷，并测量被试的任务表现（Eysenck&Eysenck,1979）。Vrij等人在审讯中要求嫌疑人以倒叙形式供述、要求嫌疑人与审讯者保持目光接触等增加认知负荷的方法，使嫌疑人说谎变得更加困难，从而表现出更多的欺骗线索（Vrij et al.,2006;Vrij etal.,2008;Vrij,Mann,Leal,&Fisher,2010）。而在CIT这种控制很严谨的、封闭式提问的实验范式中，设置认知干扰任务的方法更适合。因为这些基于反应时和正确率指标的认知任务，有明确的认知过程、方便的量化操作，以及前人对其认知机制的深入理解。在CIT中使用这些认知干扰任务，更适合深入细致地探讨增加认知负荷如何影响欺骗行为以及欺骗检测背后的认知机制。另外，任务的复杂程度也是影响执行任务所需认知资源量的重要因素，完成较为复杂的任务比完成较为简单的任务需要更多的认知资源。由于隐瞒信息测试过程中需要执行功能参与，因此本项目将设置不同难度的反应抑制、工作记忆和任务转换等执行功能有关的干扰任务增大个体的认知负荷。

第三，增加认知负荷对欺骗者和诚实者的反应过程产生不同的影响。隐瞒信息测试中，对欺骗者来说，探测刺激反应过程中存在记忆一反应冲突，冲突解决所需反应时间较长；对无关刺激做出真实反应，不存在认知冲突，所需反应时间较短。即欺骗者对探测刺激和无关刺激反应存在反应时差异。对诚实者来说，探测刺激和无关刺激均为真实反应，所需反应时间均较短，且对两类刺激的反应时差异不显著。

当设置干扰任务增加个体的认知负荷时，对欺骗者来说，干扰任务对于认知资源的消耗导致解决冲突的认知资源减少，使其对探测刺激反应更加困难（如反应时增加）。而欺骗者对无关刺激做出真实反应所需认知资源较少，即使干扰任务消耗一部分认知资源，认知资源对无关刺激反应的干扰较小。因而增加认知负荷会增大欺骗者对探测刺激和无关刺激的反应时差异。对诚实者来说，其对探测刺激和无关刺激均为真实反应，干扰任务对认知资源的消耗对这两类刺激反应的干扰程度相近，使得增加认知负荷并未增大诚实者对两类刺激的反应时差异。因此，增加认知负荷会增大欺骗者和诚实者行为上的差异，从而促进欺骗检测。

干扰任务对欺骗者和诚实者反应时的影响也应该反映在脑电指标上，尤其是P300成分。已有研究发现，对欺骗者来说，相比无关刺激，探测刺激反应引发较大的P300波幅。对诚实者来说，探测刺激和无关刺激反应引发的P300 波幅差异不显著（Mertens＆Allen,2008）。P300波幅与认知努力程度有关，认知努力程度越大，P300波幅越大。那么当增加认知负荷时，欺骗者需要投入更多的时间和努力以对探测刺激做出正确反应，导致探测刺激引发的P300 波幅更大，从而增大欺骗者对探测刺激和无关刺激反应引发的P300 波幅的差异，进而增大欺骗者和诚实者的差异。

隐瞒信息测试中，个体需要抑制对探测刺激自动化的“是”反应，并且目标刺激的设置要求被试外显地对探测刺激做出“否”反应，因而更加需要反应抑制的参与。研究发现当隐瞒信息测试变式（如隐瞒信息Oddball范式）要求更多反应抑制参与时，该测试能够取得更加稳定的测谎效果（Verschuere&Ben-Shakhar,2011）。因此，反应抑制是参与隐瞒信息测试的重要成分。当“第二任务”也需要反应抑制参与时，将干扰个体对探测刺激的反应。而由于在CIT中存在目标刺激和探测刺激的反应转换，所以“第二任务”为任务转换时也会对被测者的“正确反应”产生干扰。由于CIT过程中个体仅需识记一个目标刺激并对其做出“是”反应，所需工作记忆参与较少，因此工作记忆“第二任务”干扰可能较小。综上，本项目推测在隐瞒信息测试中设置反应抑制和任务转换干扰任务能取得更好地测谎效果。

总之，基于认知负荷的测谎方法能否取得更好的测谎效果需要进一步研究，而这首先需要了解该方法背后的认知过程及机制（Blandon-Gitlin,Fenn,Masip,&Yoo,2014）。因此，本项目系统考察不同性质和难度的干扰任务对基于记忆一反应冲突的欺骗检测的影响，研究结果可有助于理解基于认知负荷取向的测谎方法背后的认知过程和机制，并一定程度上回答该方法是否以及如何提高欺骗检测率。研究还将有助于探寻合适的欺骗检测指标并服务于自动谎言识别研究。

# 参考文献

白学军,章鹏,张琪涵,宋璐,杨宇.(2019).功能性近红外光谱技术在说谎研究中的应用.心理科学进展，崔茜,蒋军,杨文静,张庆林.(2013).欺骗的神经机制和测谎应用:来自 fmri研究的证据.心理科学进展,21(9),1629-1642.

付翠.(2011).P300 用于31例刑事在押人员的检测准确性研究.刑事技术,4,3-8.   
高军峰,王沛,郑崇勋.(2010).基于p300 和机器学习的测谎方法研究.西安交通大学学报,44(10),120-124.   
梁静,李开云,曲方炳,陈宥辛,颜文靖,傅小兰.(2014).说谎的非言语视觉线索.心理科学进展,22(6),995- 1005.   
刘鑫,位东涛,张庆林,郭英慧.(2018).GKT 范式在确定犯罪嫌疑人中的应用:一项 ERP测谎研究.心理科 学,41(3), 660-666.   
王艳梅,郭德俊.(2008).积极情绪对任务转换的影响.心理学报,40(3),301-306.   
肖玉琴,张卓,宋平,杨波.(2014).冷酷无情特质：一种易于暴力犯罪的人格倾向.心理科学进展,22(9), 1456-1466.   
张亭玉,张雨青.(2008).说谎行为及其识别的心理学研究.心理科学进展,16(4),651-660.   
赵敏,郑崇勋,赵春临.(2010).利用小波分解和支持向量机的心理意识真实性识别研究.西安交通大学学报, 44(4), 119-124.   
Abe,N. (2oo9).The neurobiology of deception: Evidence from neuroimaging and lossof-function studies. Current Opinion in Neurology, 2(6),594-600.   
Abe,N. (2011). How the brain shapes deception: An integrated review of the literature. The Neuroscientist,17(5), 560-574.   
Ambach, W.,Bursch,S., Stark,R.,& Vaitl,D.(2010).A Concealed Information Test with multimodal measurement. International Journal of Psychophysiology,75(3),258-267.   
Ambach, W., Stark,R.,& Vaitl,D. (2011).An interfering n-back task facilitates the detection ofconcealed information with EDA but impedes it with cardiopulmonary physiology. International Journal of Psychophysiology, 80(3),217-226.   
Ambach, W., Stark,R.,Peper, M., & Vaitl,D. (2oo8). An interfering Go/No-go task does not affect accuracy in a Concealed Information Test. International Journal of Psychophysiology, 68(1), 6-16.   
Aron,A.R.,Robbins,T.W.,&Poldrack,R.A. (2O04).Inhibition and the right inferior frontal cortex.Trends in Cognitive Sciences,8(4),170-177.   
Badeley,A.D., & Hitch, G. (1974). Working memory. In Psychology of learning and motivation (Vol.8, pp. 47- 89). Academic press.   
Ben-Shakhar, G. (2012). Current research and potential applications of the concealed information test: An overview. Frontiers in Psychology,3,342.   
Ben-Shakhar, G.,&Elaad,E.(2Oo3).The validityof psychophysiological detection ofinformation with the guilty knowledge test: A meta-analytic review. The Journal of Applied Psychology, 88(1),131-151.   
Bhutta,M.R., Hong,M.J.,Kim,Y.H.,& Hong,K.S.(2015).Single-trial lie detection using a combined fNIRSpolygraph system.Frontiers in Psychology,6,709.   
Blandón-Gitlin,I.,Fenn,E., Masip, J.,& Yoo,A.H. (2014). Cognitive-load approaches to detect deception: Searching for cognitive mechanisms. Trends in Cognitive Sciences,18(9),441-444.   
Booth,J.R., Burman,D.D., Meyer,J.R., Gitelman,D.R.,Parrish,T.B.,& Mesulam, M.M.(2004). Development of brain mechanisms for processing orthographic and phonologic representations. Journal of Cognitive Neuroscience,16(7),1234-1249.   
Christ,S.E.,Van Essen,D.C.,Watson,J.M.,Brubaker,L.E.,& McDermottK.B. (2009).The contributionsof prefrontal cortex and executive control to deception: Evidence from activation likelihood estimate metaanalyses. Cerebral Cortex,19(7),1557-1566.   
Ciesielski,K.T.,Harrs,R.J.,&Cofer,L.F. (2O4).Posterior brainERPpatterns related to the go/no-gotask in children. Psychophysiology, 41(6), 882-892.   
Davatzikos,C.,Ruparel,K.,Fan,Y.,Shen,D.G.,Acharya,M.,Loughead,J.W., Gur,R.C.,& Langleben,D.D. (2005). Classifying spatial patterns ofbrain activity with machine learning methods: Application to lie detection. Neuroimage, 28(3), 663-668.   
Debey,E.,De Houwer,J.,& Verschuere,B.(2014).Lying relies on the truth. Cognition,132(3),324-334.   
Debey,E.,Liefooghe,B.,De Houwer,J.,& Verschuere,B. (2015).Lie,truth,lie: the role oftask switching ina deception context. Psychological Research, 79(3), 478488.   
DePaulo,B.M.,Lindsay,J. J.,Malone,B.E.,Muhlenbruck,L., Charlton,K.,& Cooper,H. (20o3). Cues to deception. Psychological Bulletin,129(1),74-118.   
Diamond,A. (2013). Executive functions. Annual Review of Psychology, 64,135-168.   
Eysenck, M. W.,& Eysenck, M. C.(1979). Processing depth, elaboration of encoding, memory stores, and expended procesing capacity. Journal of Experimental Psychology: Human Learning & Memory,5(5), 472- 484.   
Gamer,M. (2011). Detecting of deception and concealed information using neuroimaging techniques. In B. Verschuere, G. Ben-Shakhar,& E. Meijer (Eds.), Memory detection: Theory and application of the Concealed Information Test (pp. 90-113). New York, NY: Cambridge University Press.   
Gamer, M. (2014). Mind reading using neuroimaging: is this the future of deception detection?.European Psychologist, 19(19),172-183.   
Gamer,M.,& Berti,S. (20l0).Task relevance and recognition of concealed information have different influences on electrodermal activity and event-related brain potentials. Psychophysiology, 47(2),355-364.   
Gamer, M., Verschuere,B., Crombez,G.,& Vosel, G. (2008). Combining physiological measures in the detection of concealed information.Physiology & Behavior, 95(3),3-340.   
Gronau,N., Ben-Shakhar, G.,& Cohen,A.(2Oo5).Behavioral and physiological measures in the detection of concealed information. Journal of Applied Psychology, 90(1),147-158.   
Haider, S.K., Jiang,A., Jamshed,M.A.,Pervaiz, H.,& Mumtaz, S.(2018).Performance enhancement inp300 erp single trial by machine learning adaptive denoising mechanism. IEEE Networking Letters, 1-1.   
Haxby, J. V. (2012). Multivariate patern analysis of fMRI: The early beginings. Neuroimage, 62(2),852-855.   
Hu,X.,& Rosenfeld,J.P. (2012).Combining the P300-complex trial-based Concealed Information Testand the reaction time-based autobiographical Implicit Association Testin concealed memory detection. Psychophysiology, 49(8),1090-1100.   
Hu,X.,Evans,A., Wu,H.,Lee,K.,&Fu, G. (013).An interfering dot-probe task facilitates the detection of mock crime memory in a reaction time (RT)-based concealed information test. Acta Psychologica,142(2), 278-285.   
Hu, X.,Pornpattananangkul,N.,& Rosenfeld, J.P. (2013).N2O0 and P3O0 as orthogonal and integrable indicators of distinct awareness and recognition processes in memory detection. Psychophysiology, 50(5), 454-464.   
Hu,X.,Wu, H.,&Fu, G. (2011).Temporal course of executive control when lying about self-and other-referential information: An ERP study. Brain Research,1369,149-157.   
Kubo,K.,& Nitono,H. (2o09).The role of intention to conceal in the P3o0-based concealed information test. Applied Psychophysiology and Biofeedback,34(3),227-235.   
Levine,T.R., Blair, J.P.,& Carpenter, C.J. (2018). A critical look at meta-analytic evidence for the cognitive approach to lie detection: Are-examination of Vrij, Fisher,and Blank (2O17). Legal and Criminological Psychology,23(1), 7-19.   
Meijer,E. H., & Verschuere, B. (2017). Deception detection based on neuroimaging: Beter than the polygraph?. Journal of Forensic Radiology and Imaging, 8,17-21.   
Meijer,E.H., Selle, N.K., Elber,L.,& Ben-Shakhar, G. (2014). Memory detection with the Concealed Information Test: A meta analysis of skin conductance,respiration, heart rate, and P300 data.Psychophysiology,51(9),879-904.   
Mertens,R.,& Allen, J. J. (2008).The role of psychophysiology in forensic assessments: Deception detection, ERPs,and virtual reality mock crime scenarios.Psychophysiology, 45,286-298.   
Monsell, S.(2003). Task switching. Trends in Cognitive Sciences,7(3),134-140.   
National Research Council (2003).The Polygraph and Lie Detection. Commitee to review the scientific evidence on the polygraph (2003), The National Academic Press, Washington, DC   
Rosenfeld,J.P.(2011).P300 in detecting concealed information.In B.Verschuere,G.Ben-Shakhar,&E.Meijer (Eds.),Memory detection: Theory and application of the Concealed Information Test (pp. 63-89). New York, NY: Cambridge University Press.   
Rosenfeld,J.P.,Labkovsky,E., Winograd,M.,Lui,M.A., Vandenboom,C.,& Chedid,E. (2008).The Complex Trial Protocol(CTP): A new, countermeasure-resistant,accurate,P3o0-based method for detection of concealed information. Psychophysiology, 45(6), 906-919.   
Rosenfeld,J.P.,Soskins,M.,Bosh,G.,&Ryan,A. (0o4).imple,effective countermeasures toP30-based tests of detection of concealed information. Psychophysiology, 41(2),205-219.   
Sartori, G.,Agosta, S., Zogmaister, C.,Ferrara, S.D.,& Castiello,U. (20o8). How to accurately detect autobiographical events. Psychological Science,19(8),772-780.   
Seymour,T.L.,& Kerlin,J.R. (2o08). Successful detection of verbal and visual concealed knowledge using an RT-based paradigm.Applied Cognitive Psychology: The Official Journal of the Society for Applied Research in Memory and Cognition, 22(4), 475-490.   
Seymour,T.L.,Seifert, C.M.,Shafto,M. G.,& Mosmann,A.L.(20oo). Using response time measures to asss" guilty knowledge". Journal of Applied Psychology, 85(1),30-37.   
Simbolon,A.I.,Turnip,A., Hutahaean,J.,&Siagian, Y. (2o15). An experiment of lie detection based EEG-P300 clasified by SVM algorithm. 2015 International Conference on Automation, Cognitive Science,Optics, Micro Electro-Mechanical System,and Information Technology (ICACOMIT). IEEE.   
Spence,S.A.,Farrow,T.F.,Herford,A.E.,Wilkinson,I.D.,Zheng,Y.,& Woodruff,P.W. (2oo1).Behavioural and functional anatomical correlates of deception in humans. Neuroreport, 12(13),2849-2853.   
Sporer,S.L.,& Schwandt, B. (2oo6).Paraverbal indicators of deception: Ameta-analytic synthesis.Applied Cognitive Psychology: The Ofcial Journal of the Society for Applied Research in Memory and Cognition, 20(4), 421-446.   
Sporer, S.L.,& Schwandt, B. (2oo7). Moderators of nonverbal indicators of deception: A meta-analytic synthesis.Psychology, Public Policy,and Law,13(1),1-34.   
Suchotzki,K.,Verschuere,B., Van Bockstaele,B., Ben-Shakhar, G.,& Crombez, G. (2017).Lying takes time: A meta-analysis on reaction time measures of deception. Psychological Bulletin,143(4), 428-453.   
Thorell,B.,Lindqvist, S., Bergman, S., Bohlin, G.,& Klingberg,T. (2009). Trainingand transfer efects of executive functions in preschool children. Developmental Science,12(1),106-113.

# Deception detection based on memory-response conflict: A cognitive load approach

Liang Jing'; Ruan Qiannan²; Li ${ \mathrm { H e } } ^ { 3 }$ ; Ma Mengqingl; Yan Wenjing²

(1 School of Educational Science,Ludong University, Yantai 264025) (2 Institute of Psychology and Behavior Sciences,Wenzhou University,Wenzhou 264025） (3 School of Public Administration,Northwest University, Xi'an 710127)

Abstract: Deception detection is an important topic in psychology. The cognitive approach to deception detection is based on the premise that lying is more cognitively demanding than truth tellng. Increased cognitive load is hypothesized to result in greater behavioral differences between truth tellers and liars. By manipulating cognitive load through different interfering task of various difficulties during the concealed information test, the influence of cognitive load on memory-response conflict was investigated to better illustrate the cognitive mechanism of deception detection. Second, behavioral and physiological cues for memory-response conflict based deception detection were examined in both noncriminal and criminal group. Finally, machine learning algorithms were employed to predict liars and truth tellrs via behavioral and physiological cues.These findings wil serve to aid in deception detection in the fields of judicial security and human communication.

Key Words: deception detection; cognitive load; memory-response conflict; interfering task; machine learning