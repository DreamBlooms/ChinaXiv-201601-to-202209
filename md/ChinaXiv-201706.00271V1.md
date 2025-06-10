# 细菌小RNA的调控及在代谢工程中的应用

赵秀丽 周丹丹 闫晓光 吴昊财音青格乐 李艳妮\*\*乔建军(天津大学化工学院系统生物工程教育部重点实验室 天津化学化工协同创新中心合成生物学平台 天津 300072)

摘要细菌代谢工程需要优化基因的表达来平衡代谢物通量分布和减少有毒的中间体积累，从而提高产物生物合成。细菌小RNA（smaII RNA，sRNAs）与靶标mRNA 通过碱基互补配对结合来抑制或激活其靶标基因的表达。sRNA 在细菌的生理过程中都起到了至关重要的调控作用，因此被认为是细菌代谢工程中调节靶标基因表达的有力工具。近年来，越来越多的人工合成sRNA 在细菌代谢工程中得到应用，本文分别就细菌 sRNA 的靶标识别和其对靶标的调控及代谢工程中的应用做了总结概括。

关键词 细菌；小RNA;调控;代谢工程中图分类号Q752

# Regulation and Application in Metabolic Engineering

# ofBacterial SmallRNAs

ZHAO Xiu-li ZHOU Dan-dan YAN Xiao-guang WU Hao CAIYIN Qing-gele LI Yan-ni QIAO Jian-jun

(DepartmentofPharmaceutical Engineering，SchoolofChemical Engineering and Technology，Tianjin University; Key Laboratory of Systems Bioengineering，Ministry of Education; Syn Bio Research Platform, Collaborative Innovation Center of Chemical Science and Engineering，Tianjin 3ooo72，China)

AbstractMetabolic engineering in bacteria requires optimization of gene expression levels to balance metabolic flux distributions and minimize accumulation of toxic intermediates towards an efficient biosynthesis of target products. Small non-coding RNAs (sRNAs) in bacteria can interact with their target mRNA by base-pairing to inhibit or activate the translation of their target genes. Since small RNAs play critical regulatory roles in many physiological processes, they are considered to be powerful tools for the tuning of target genes expresson in bacterial metabolic engineering. Many artificial sRNAs are applied in metabolic engineering in recent years. In this review, identification of sRNA targes genes, interaction between sRNAs and their targets and application of sRNAs in metabolic engineering were summarized.

Key wordsBacteria; Small RNAs; Regulation; Metabolic engineering细菌代谢工程为环境治理、医学应用，可再生能源的化工生产提供了支持，但是代谢工程也面临诸多问题，如平衡关键代谢物的流量分布、有毒中间体积累和生产环境压力等。为了更好的感知和响应对外界环境的变化，同时完成自身的体内循环，使代谢产物的生物合成更高效，越来越多的细菌 sRNA应用于代谢工程中。细菌 sRNA是一类长度在 50-500 nt之间，不编码蛋白质的RNA分子，主要以转录后调控的形式来发挥其调控作用。这样可以利于较小的靶标mRNA的周转并且可以完成对不同靶标的分级调控[I]。sRNA是从转录水平对菌体生理活动进行调控，设计和合成 sRNA策略的优势在于不需要敲除染色体基因组，就可以调控微生物代谢网络，避免了突变菌株库的构建过程，省时省力；而且sRNA的表达不会为微生物代谢增加负担。现已发现了超过150多种细菌 sRNA[2.3]，有关sRNA的研究大多集中于革兰氏阴性菌。近年来伴随着现代生物学和信息学手段、技术的飞速发展，也有越来越多的sRNA在革兰氏阳性菌中（如酿脓链球菌Streptococcus pyogenes[4]，乳酸乳球菌Lactococcus lactis[5]）被发现，其生物学功能也逐渐被揭示。

# 1细菌sRNA靶标基因的预测与鉴定

随着大量的sRNA被发掘，识别sRNA的靶标进而探究其功能已然成为当今生物学领域研究的热点之一。细菌 sRNA靶标基因的识别主要通过基于生物信息学的计算机预测方法与实验分析方法结合来进行。

生物信息学的计算机预测方法对细菌sRNA靶标的预测主要依据序列长度、碱基匹配、RNA二级结构、序列保守性及其位置等特点。目前常用的 sRNA靶标 mRNA 预测的 软件有RNAPredator[]、sRNATarBase[7]、CopraRNA[8,9]、RNAup[10]、sRNATarget[11]、sTarPicker[12]、IntaRNA[13]、TargetRNA2[14]、RNAcofold[15]、RNAplex[16]和 RNAhybrid[17]。CopraRNA、RNAplex、IntaRNA、RNAup 和TargetRNA2是识别最有可能发生相互作用的局部区域并打分；RNAhybrid 和RNAcofold 更多用于sRNA与较长的RNA相互作用时。局部相互作用的软件(CopraRNA、IntaRNA、RNAplex、RNAup、TargetRNA2)比全部相互作用的软件（RNAhybrid 和RNAcofold）要好[18]。经实验验证软件的配对率IntaRNA/CopraRNA $* 7 6 . 7 \%$ ，RNAplex $73 . 6 \%$ ，TargetRNA2 $5 5 . 9 \%$ ，RNAup$7 8 . 9 \% [ 1 8 ]$ 。主要用于预测 sRNAs靶标mRNAs 计算机工具的特点比较见表1。

表1预测sRNAs靶标mRNAs的主要计算机工具  
Table 1 Main computational tool for prediction of bacterial sRNAs target mRNAs   

<html><body><table><tr><td>软件名称</td><td>网址</td><td>主要特征</td><td>参考文献</td></tr><tr><td rowspan="2">RNApredator</td><td>http://rna.tbi.univie.ac.at/RNApr</td><td>可预测与靶标位点相互做的的</td><td>[6]</td></tr><tr><td>edator</td><td>可及性位点</td><td></td></tr><tr><td>sRNATarBase3.0</td><td>http://ccb1.bmi.ac.cn/srnatarbas</td><td>预测sRNA与mRNA及sRNA</td><td>[7]</td></tr></table></body></html>

<html><body><table><tr><td colspan="2"></td><td rowspan="2">与蛋白之间的相互作用，给出 sRNA与mRNA结合区域详细信 息 比较预测，合并并拓展了</td><td rowspan="2">IntaRNA，预测结果伴随着大量 [8,9] 后处理方法（功能富集分析、可</td></tr><tr><td>CopraRNA</td><td>http://rna.informatik.uni-freibur g.de.</td></tr><tr><td>RNAup</td><td>http://rna.tbi.univie.ac.at/cgi-bin /RNAup.cgi</td><td>视化交互的地区) 考虑到结合位点的可及性</td><td>[10]</td></tr><tr><td>sRNATarget</td><td>http://ccb.bmi.ac.cn/srnatarget/</td><td>考虑到RNA序列和RNA二级结 构; nai"ve Bayes 方法</td><td>[11]</td></tr><tr><td>sTarpicker</td><td>http://ccb.bmi.ac.cn/starpicker/</td><td>热力学稳定性;sRNA和靶标相 互作用的可及性位点;nai"ve</td><td>[12]</td></tr><tr><td>IntaRNA</td><td>http://www.bioinf.uni-freiburg.d</td><td>Bayes 方法 考虑到用户特殊种子区域的存 在及影响 sRNA与靶标相互作用</td><td>[13]</td></tr><tr><td>TargetRNA2</td><td>e/Software/ http://snowwhite.wellesley.edu/t</td><td>的可及性位点 杂化能，不考虑 sRNA或mRNA</td><td>[14]</td></tr><tr><td>RNAcofold</td><td>argetRNA/ http://www.tbi.univie.ac.at/RNA</td><td>结构 针对两个序列的最低能</td><td>[15]</td></tr><tr><td>RNAplex</td><td>/ http://www.tbi.univie.ac.at/~htaf</td><td>针对两个序列的最低能量算法。</td><td>[16]</td></tr><tr><td>RNAhybrid</td><td>er/ http://bibiserv.techfak.unibielefe ld.de/ranhybrid/</td><td>运行速度快 针对两个序列的最低能量算法。 忽略了分子内碱基互补和多重</td><td>[17]</td></tr></table></body></html>

用于验证sRNA靶标基因的方法有很多种，目前比较成熟，使用较多的有：遗传学方法、亲和技术、免疫共沉淀法和微阵列技术。除此之外,ribosome profiling(Ribo-seq)技术是最近开发的基因组规模的方法，可以同时确定体内RNA水平和翻译水平[18]，JingWang等[19]使用Ribo-seq 全面验证大肠杆菌（Escherichia coli)sRNARyhB已知的靶标，并确定很多新奇的 sRNA 靶标。实验数据表明,Ribo-seq是一种识别sRNA靶标强大的方法，并且是检测 sRNA各级调控(即转录、mRNA稳定性、翻译)的有效方法。各种用于鉴别 sRNA靶标的方法的比较见表2。

表2鉴别sRNA靶标的方法的比较  
Table2 Comparison of methodsof sRNA target identification   

<html><body><table><tr><td rowspan="2">方法</td><td rowspan="2">主要靶标类 型</td><td rowspan="2">优点</td><td rowspan="2">缺点</td><td rowspan="2">实例 (sRNA/mRNA)</td></tr><tr><td></td></tr><tr><td>遗传学方法</td><td>mRNA</td><td>一般通过与表型相关的生 理特征进行靶标识别；也</td><td>调节因子具多重效应 使得复杂化</td><td>MicF/ompF [20]</td></tr></table></body></html>

<html><body><table><tr><td>亲和技术</td><td>蛋白和 mRNA</td><td>直接鉴定相互作用;能找到第 一靶标</td><td>亲和力较低、靶标量 较少难操作</td><td>RseX/ompa 和 ompC [21]</td></tr><tr><td>免疫共沉淀</td><td>蛋白和 mRNA</td><td>直接识别靶标</td><td>出现假阳性或靶标量 较少易出错</td><td>RydC/yejAB[22] MucR/mucR[23]</td></tr><tr><td>微阵列</td><td>mRNA</td><td>高产、高灵敏度</td><td>假阳性较多、mRNA 水平受到影响时才有 效</td><td>GcvB/cycA[24]</td></tr><tr><td>蛋白组学</td><td>蛋白和 mRNA</td><td>不考虑相互作用方式</td><td>识别范围小，表达量 少或不溶性蛋白不易 被检测到</td><td>MicA/ompA[25]</td></tr><tr><td>Ribo-seq</td><td>蛋白和 mRNA</td><td>灵敏，具体，可检测 sRNA各 个水平的调控靶标</td><td>表现大量假阴性</td><td>RyhB /shiA, cirA和acnB[19]</td></tr></table></body></html>

# 2细菌sRNA与其靶标的相互作用

细菌非编码sRNA按照其在基因组中的位置不同，可以分为顺式编码sRNA(cis-encoded sRNA)和反式编码 sRNA(trans-encoded sRNA),顺式编码 sRNA由它所调控的mRNA的互补链合成，可以通过与靶标mRNA进行严格的互补配对，抑制其表达或使其基因沉默[26]。细菌 sRNA以反式编码 sRNA为主，反式编码 sRNA大部分都需要RNA分子伴侣Hfq蛋白的协助来发挥作用，主要通过与靶标mRNA上7-12个碱基进行不严格的互补配对，抑制或促进靶mRNA的翻译，加速或减缓靶mRNA的降解。

# 2.1细菌sRNA与mRNA的相互作用

# 2.1.1 sRNA调节mRNA翻译和mRNA稳定性

通常情况下，反式编码sRNA通过与位于靶标mRNA5'-UTR的核糖体结合位点（RBS）进行不完全互补配对阻止30S核糖体的结合和翻译的起始（图1a)，例如在大肠杆菌中被首次发现的主要孔蛋白OmpC合成抑制因子sRNAMicC，MicC 通过与核糖体竞争结合位点抑制ompC翻译[27]。还有一种抑制方式是 sRNA在Hfq的协助下与正在进行翻译的mRNA结合，导致mRNA的发生结构重组，RBS区域进行碱基互补结合形成二级结构阻止了核糖体结合，使得翻译抑制（图1c)。相反，有些sRNA通过与靶标的 ${ \boldsymbol { 5 } } ^ { \prime }$ -UTR区结合激活翻译，通常这些靶标mRNA $5 ^ { \prime } .$ -UTR区内在的二级结构阻止核糖体结合，当sRNA结合到 ${ \boldsymbol { 5 } } ^ { \prime }$ -UTR区，RBS 被打开，使翻译起始(图1d)。例如在大肠杆菌中DsrA和RyhB可分别促进Rpos[28]和shiA[29]的翻译起始，就是这种调节机制在发挥作用。

RNA稳定性的调节是sRNA主要的调节机制，GadY属于顺式编码的一类sRNA，这种结合通常引导一个负调控，可以积极调节gadW和gadXmRNA水平参与应对酸压力。GadY可以直接与gadX-gadWmRNA基因间区域进行严格的碱基配对，形成双链结构，增加mRNA的稳定性，保护mRNA不被RNaseE降解[30-32]（图2b）。

![](images/b14e83409958d64ee0f4d12ef062a9d76014b4e5a0c5977d23926ab7f210045a.jpg)  
图1.反式编码sRNA调控靶标的机制  
Fig.1Regulatory mechanisms of trans-encoded sRNAs.

(a)TranslationinhibitionbyblockingofRBS.(b)sRNAsimperfectlybase-pairwithtargetmRNAsinordertorepresstranslation and spedupdegradation by RNase.(c）Translation inhibitionbyblocking ofRBS(d) Translation activation by mediating mRNA structure change(e) s RNAs act by binding to the target protein to regulate their activities

# 2.1.2 sRNA调节mRNA降解

sRNA调控靶标mRNA的另一种机制是与mRNA碱基互补配对后，在核酸酶E(RNaseE)作用下使mRNA 降解。参与靶mRNA 降解的RNaseE可以特异性地作用于富含AU 的单链RNA，将靶mRNA 和 sRNA同时降解[33,34](图1b 和图2a)。在这一机制中Hfq参与 sRNA诱导的mRNA降解。最先发现的sRNA调控mRNA降解的是RyhB，在铁离子缺乏的情况下，RyhB可导致至少18种编码需铁蛋白的mRNA在10 分钟内迅速降解，使铁离子重新分布到细胞重要区域[35]。

类似的快速降解mRNA机制也在其他 sRNA如OmrA，OmrB[6]和 $\mathrm { R y b B ^ { [ 3 7 ] } }$ 中得到证实。在RNaseE 的作用下通过sRNAs/Hfq导致mRNA的降解的作用机制还不是很清楚，但可以从两种途径来说明mRNA的不稳定性：一种可能是mRNA与 sRNA碱基互补配对之后，失去核糖体的保护其更容易受RNase 的攻击；另一种可能是所形成的 sRNA/Hfq/RNaseE复合物对RNA 的降解有促进作用。

![](images/558fc143e645d1ce7eda1057854fdc4043e708d73af89d939737376ab2f9c803.jpg)  
图2.顺式编码sRNA调控靶标的机制  
Fig.2Regulatory mechanisms of cis-encoded sRNAs.

(a).sRNAsperfectcomplementaritywithtargetsanddegradedbyanRNaseE.(b).sRNAscomplementaritywithmRNAformingduplex structure to increase the stability of mRNA.

# 2.2细菌sRNA与蛋白相互作用

sRNA可与相应蛋白质结合行使相应的调控功能，sRNA和sRNA结合蛋白的研究均具有重要意义。大多数sRNA需要与蛋白质结合在体内起作用，sRNA和蛋白质相互作用可以分为两大类：调控RNA结合蛋白、调节酶的活性。

sRNA调节RNA结合蛋白通常是通过模仿作用，如在大肠杆菌中，sRNA基因CsrB和CsrC是CsrA蛋白(全局转录后调控因子)的拮抗物，CsrB和CsrC与CsrA蛋白相互作用可形成一个调控反应回路，从而调控该蛋白的活性[38]。CsrA通过与glgC(糖原代谢基因)转录物的RBS周围序列结合抑制翻译的起始。CsrB和 CsrC可通过与CsrA蛋白结合，作为CsrA的拮抗物发挥调节功能[39,40]。

有些sRNA结合具有酶活性的蛋白质，有可能抑制、激活或修改蛋白质的活动。在大肠杆菌中,6sRNA可以通过与σ70-RNA聚合酶的相互作用改变o70-RNA聚合酶对启动子识别的特异性。在转录起始时6sRNA二级结构的很大程度上模仿了DNA构象，与s70-RNA 聚合酶全酶结合改变RNA聚合酶的活性，从而抑制启动子区域-10bp上游含 TGn序列（TGn TATAAT）基因的转录[41,42]。Smaldone等[43]在枯草芽孢杆菌中发现了FsrA，FsrA 能与三种蛋白FbpA、FbpB 和 FbpC共同作用，抑制包括TCA循环中的琥珀酸脱氢酶和乌头酸酶以及含铁硫簇的谷氨酸合酶等的合成，从而调节细菌体内的铁离子平衡和代谢稳定。目前已经报道的sRNA结合蛋白见表3所示。

表3sRNA结合蛋白的总结  
Table 3 Summary of sRNA-binding protein   

<html><body><table><tr><td>sRNA 结合蛋白</td><td>所在菌株</td><td>结合的sRNA</td><td>参考文献</td></tr><tr><td rowspan="2">Hfq</td><td>E.coli</td><td>ArcZ、Oxys、DsrA、</td><td>[38-40]</td></tr><tr><td>Salmonella enteritidis</td><td>RprA</td><td></td></tr><tr><td>070-RNA聚合酶 FbpA、FbpB、FbpC</td><td>E.coli</td><td>6S RNA FsrA</td><td>[41,42]</td></tr><tr><td>RsmA</td><td>B.subtilis</td><td>RsmY、RsmZ</td><td>[43] [44]</td></tr><tr><td rowspan="2">CsrA、RsmA、RsmE</td><td>Pseudomonas aeruginosa</td><td></td><td></td></tr><tr><td>E.coli</td><td>CsrB、CsrC</td><td>[45,46]</td></tr><tr><td>RsmA</td><td>Pseudomonas fluorescens</td><td>RsmY</td><td>[44]</td></tr><tr><td>RsmA</td><td>P.fluorescens</td><td>RsmX</td><td>[47]</td></tr><tr><td>RsmE</td><td>P.fluorescens</td><td>RsmY</td><td>[47]</td></tr></table></body></html>

# 3细菌sRNA的功能与代谢工程中的应用

sRNA作为一种重要的基因表达调控工具，随着微生物中sRNA越来越多的被发现，它在微生物体内所起的作用以及调控机制也逐渐被阐明，其为改变细菌生理特性、改变菌株代谢途径、提高菌株的代谢物产量和微生物细胞工厂构建的方法创新提供了可能。

# 3.1细菌sRNA的功能

随着越来越多的细菌sRNA被识别，其在菌株中所起的作用也逐渐被挖掘出来。细菌 sRNA可通过调控细菌在宿主细胞中的毒力启动细菌细胞内部的相关机制，使细菌对生长条件的变化做出反应来适应感染细胞内的环境变化[48]，也可以通过调节群体感应系统的感应调节蛋白的表达来控制菌体的密度[49]。在生长环境中营养物质不足时，细菌sRNA可在抗营养应激（碳源、氮源）也发挥的重要的调控作用，在大肠杆菌中，sRNA基因CsrB 和CsrC 既调节糖原代谢[50]也可以调控氨基酸的代谢过程[51]。

细菌细胞中的微量元素是细菌代谢过程中不可缺少的一部分，有些参与辅助酶促反应，sRNA可以调节微量元素在细胞中的含量使其相对平衡，如 sRNA基因RyhB在大肠杆菌中能调节Fur基因的表达，在减缓细菌的铁饥饿中起着重要作用[52]。而 sRNA 基因 RyhB 在福氏志贺氏菌可以调节ydeP 基因的表达水平从而调控耐酸性[53]这点也说明了同种sRNA在不同细菌中可能有不同的调控机制，导致不同的功能效应。除了可以调控酸耐受之外，sRNA也可以调节其他环境应激，如温度[54]、氧气胁迫[55]。一种反式编码 sRNA基因DsrA在大肠杆菌中可以调节菌体对温度变化的感应。当温度较低时,DsrA可以在Hfq蛋白协助下与RpoSmRNA的前导序列碱基配对，激活mRNA的翻译，DsrA大量表达，促进RpoS基因调控细菌RNA 聚合酶的σ因子的表达[56-58]。sRNA的不同调控功能见图3。

![](images/037af9871c11799531e9ba2da8f15b9dfd81ef93edad20c9b7b86dff56bc6ba9.jpg)  
图3细菌sRNA对多种胁迫的调控作用  
Fig.3 Bacterial sRNA modulate cells to resist various stresses

# 3.2过表达细菌sRNA来调控环境胁迫

由于sRNA在许多环境压力中扮演至关重要的角色，如在发酵过程中，对保持鲁棒性和长期在压力条件下生产力起重要作用。因此，提高菌株的耐受性将有利于生物工艺应用。sRNA基因DsrA被认为是大肠杆菌中的一个多功能的基因调节器，全局转录调控因子rpoS，是由 sRNADsrA，RprA，和ArcZ 转录后的调节，由OxyS下调表达[59]。最近，Gaida 等[60]报道，同时过表达DsrARprA，ArcZ可大幅增加酸耐受并在对数生长期对羧酸和氧化应激提供保护。同样，应用这种多种转录后调控策略，Kang 等[61]建造了一个压力诱导系统来生产高级生产化学品、包括聚羟基丁酸酯和1，3-丙二醇。因此，用 sRNA来提高压力耐受是一种有效的策略。

本实验室以乳酸乳球菌F44为研究对象，在酸胁迫下转录组测序和差异基因表达分析挖掘乳酸乳球菌的sRNA，运用sRNA过表达的方法实验验证并筛选能明显提高乳酸乳球菌F44的sRNA。由预测验证得到的sRNA真正靶标来分析sRNA作用的耐酸机制。通过人工设计合成sRNA，然后将其导入乳酸乳球菌F44中构建出新的高耐酸菌株，从而提高菌株耐受酸性环境和生产nisin 的能力(未发表)。利用sRNA在乳酸乳球菌F44中介导的耐酸调控对构建乳酸乳球菌的耐酸网络具有重要的意义。

# 3.3利用反义sRNA“knock down”来调控代谢通路

反式作用调控小RNA(sRNA)由与mRNA互补结合的靶向性反义RNA和一个召集宿主Hfq 的支架组成，随后可以通过核糖核酸酶E诱导mRNA 降解[62]。人工合成反义sRNA现已广泛用于基因沉默，sRNA介导的基因沉默是利用天然RNA 辅助骨架构建了人工sRNA,afsRNA与mRNA复合物在Hfq协助下实现对内源基因表达进行微调和动态控制[63,64]。

以天然sRNA为依据，合理设计人工sRNA并将其连入载体质粒上，可以在不改变染色质基因的前提下，实现快速高通量的"knock-down"研究，这在代谢工程中得到了广泛应用[65]（表4)。如Lee等[66]通过在18株大肠杆菌菌株中合成调控 sRNA将酪氨酸生物合成途径中的碳存储调节器(csrA)和酪氨酸抑制因子(tyrR)两个调控因子"knock-down”。然后在E.coil中过表达酪氨酸生物合成路径中基因和酪氨酸酚裂合酶(TPL)基因，从葡萄糖出发生产苯酚，最后在18株工程菌株中筛选得到了苯酚产量为 $3 . 7 9 \ \mathrm { g / L }$ 的PheBL21菌株，达到了微生物发酵的最高效价。在大肠杆菌中利用sRNA策略来提高目标产品的产量已得到广泛使用，近来，在其他菌株中sRNA策略也成功实现了运用，如枯草芽孢杆菌（Bacillussubtilis）中，Liu 等[67]应用 sRNA 策略提高N-乙酰葡萄糖胺(GlcNAc)的产量。GlcNAc合成、GlcNA糖酵解和肽聚糖合成模块竞争相同的前体。为了直接进行GlcNAc合成、设计了两个靶向于pfk(编码6-磷酸果糖激酶)和glmM(编码磷酸葡糖胺变位酶)的sRNA分别用于限制糖酵解和肽聚糖合成。为了达到更佳抑制效果，对Hfq蛋白进行了共表达。和 sRNA一起同时抑制pfk和glmM表达，优化菌株的GlcNAc产量增加了4.3 倍。在丙酮丁醇梭菌(Clostridium acetobutylicumPJC4BK)中,Changhee Cho 等[68]使用合成 sRNA敲除pta基因使丁醇的产量增加。sRNA在代谢工程中的应用实例见表4。

表4细菌sRNA在代谢工程中的应用实例Application examples of sRNAs in metabolic engineering  

<html><body><table><tr><td>SRNA 类型</td><td>调控类型</td><td>宿主菌株</td><td>靶标基因</td><td>产物变化</td><td>研究策略</td></tr><tr><td rowspan="6">非人工合成</td><td rowspan="3">调控环境胁迫</td><td>E. coli MG1655</td><td>mutS，mutD 和 ndk</td><td>自发突变频率增加 2000倍</td><td>过表达反义sRNA[69]</td></tr><tr><td>E. coli MG1655</td><td>rpoS</td><td>酸耐受提高</td><td>过表达DsrA，ArcZ 和 RprA[60]</td></tr><tr><td>C.acetobutylicum ATTC 842</td><td>/</td><td>丁醇耐受性和丁醇产 量提高</td><td>过表达压力应激 sRNA: 6S 和 tmRNA[70]</td></tr><tr><td rowspan="2">调控铁离子</td><td>E.coli MG1655</td><td>sdhCDAB 和 acnAB</td><td>琥珀酸产量增加7倍</td><td>过表达 sRNA 基因 RyhB[71]</td></tr><tr><td>E. coli DALA</td><td>hemB，hemH, acnAB， sdhAB,</td><td>增加5-氨基乙酰丙酸 产量</td><td>过表达 sRNA 基因 RyhB[72]</td></tr><tr><td>调控糖代谢</td><td>E. coli K-12</td><td>fumA，和 cydAB ptsG</td><td>醋酸盐分泌减少</td><td>过表达 sgrS 基因[73]</td></tr><tr><td>人工合成</td><td>调控氮代谢</td><td>E.coli W3110</td><td> pfkA</td><td>1，3-二氨基丙烷的产 量提高</td><td>合成128个 sRNA "knock-down"靶标基 因[74]</td></tr></table></body></html>

<html><body><table><tr><td rowspan="7"></td><td rowspan="2">E. coli K-12，E. coli BL2和E.</td><td colspan="3">csrA 和 tyrR 苯酚产量提高</td><td rowspan="2">合成sRNA “knock-down"酪氨酸 合成途径中调控因子 [66]</td></tr><tr><td>coliW等</td><td></td><td></td></tr><tr><td rowspan="2">调控碳代谢</td><td>E. coli BW25113</td><td>PykF</td><td>琥珀酸产量提高 L-酪氨酸产量提高1.2</td><td>反义sRNA微调代谢通 路[75] 人工设计负调控L-酪</td></tr><tr><td>E.coli BKT5</td><td>csr A</td><td>倍 N-乙酰葡糖胺产量增</td><td>氨酸生物合成途径的 设计两个反义sRNA与 sRNA[76]</td></tr><tr><td>B.subtilis 168 C.acetobutylicum</td><td></td><td>pfk，glmM pta</td><td>加了4.3倍 丁醇产量提高</td><td>Hfq蛋白共表达[67] 合成sRNA系统 "knock-down"靶标基</td></tr><tr><td>调控糖代谢</td><td>E. coli WG/pZG07/</td><td>ls等多个s和</td><td>聚6-脱氧红震内</td><td>因[68] 合成反义基A制代</td></tr><tr><td>调控环境胁迫</td><td>pZG08 E.coli DH5α</td><td>murE</td><td>酪氨酸和尸胺的产量 提高</td><td>酪氨酸和尸胺的产量 提高[78]</td></tr></table></body></html>

# 4小结与展望

RNA 深度测序（RNAseq）技术的发展和生物信息学预测以及实验分析手段的完善为细菌 sRNA的发现提供了支持。预测并挖掘出更多天然 sRNA可以更好地推动代谢工程和合成生物学的发展。但目前仍有很多sRNA功能还未通过实验确定，识别细菌 sRNA的靶标，研究sRNA与其靶标之间的相互作用，可以极大地丰富调节代谢工程的方法。

通常加强调控和优化基因电路和代谢途径主要是集中在转录和翻译水平，转录后的方法显示许多优点，如反应迅速、灵活、调控精确，没有代谢负担。通过合理设计sRNA来动态调节代谢途径省去了敲除染色体基因和构建突变菌株库的繁琐步骤，可以使菌株的快速发展为理想型菌株；另外，在这一领域的研究将有助于对自然生物网络的控制机制的理解。但是，细菌体内的调控机制十分复杂，一个 sRNA通常调控多个靶标基因，天然或人工合成 sRNA在工程菌株中所调控的不同路径是否存在相互影响，人工sRNA与天然sRNA之间是否有相互作用，而且sRNA上游调控机制尚未清楚；这些问题的解决可以帮助我们更好的利用sRNA来调节工程菌株的代谢途径。目前，细菌 sRNA的研究与应用大多数集中在大肠杆菌等模式生物中，对致病菌的sRNA研究还有待进一步深入。随着对sRNA与靶标mRNA或靶标蛋白作用机制的进一步深入研究，相信会有更多的sRNA功能被发现，也为工程菌株的改造、致病微生物的预防和工业微生物育种等提供了保障。

# 参考文献

[1] Mitarai N. Eficient degradation and expression prioritization with smal regulatory RNAs. Physical Biology, 2007, 4(3): 164-171.   
[2] Abu-Qatouseh LF，Chinni SV，SeggewiB J，et al. Identification of diferentially expressed small non-protein-coding RNAs in Staphylococcus aureus displaying both the normal and the smal-colony variant phenotype[J]. Journal of Molecular Medicine,2010, 88(6): 565-575.   
[3] Raabe C A, Hoe C H,Randau G,et al. The rocks and shallows of deep RNA sequencing: Examples in the Vibrio cholera RNome.RNA,2011,17(7): 1357-1366.   
[4] Perez N,Trevi o J,Liu Z, et al.A genome-wide analysis of smallregulatory RNAs in the human pathogen group A Streptococcus. PloS One,2009,4( 11) : e7668.   
[5] van der Meulen S B,de Jong A,Kok J. Transcriptome landscape of Lactococcus lactis reveals many novel RNAs including a smallregulatory RNA involved in carbon uptake and metabolism.RNA biology,2016, 13(3): 353-366.   
[6] Eggenhofer F, Tafer H, Stadler PF, Hofacker IL. RNApredator: fast accessbility-based prediction of sRNA targets. Nucleic acids research,2011,39:W149 - 54.   
[7] Wang J,Liu T, Zhao B,et al.sRNATarBase 3.O: anupdated database for sRNA-target interactions inbacteria. Nucleic acids research, 2015, 44:D248-D253.   
[8] Wright PR,Richter A S,Papenfort K, et al. Comparative genomics boosts target prediction for bacterial small RNAs.Proceedings of the National Academy of Sciences,2013,110(37): E3487-E3496.   
[9] Wright PR, Georg J, Mann M, et al. CopraRNA and IntaRNA: predicting small RNA targets, networks and interaction domains. Nucleic acids research,2014, 42(W1): W119-W123.   
[10] Mückstein U,Tafer H, Hackermuler J,et al. Thermodynamics of RNA-RNA binding. Bioinformatics 2006;22:1177-82.   
[11] Ying X, Cao Y,Wu J,etal. STarPicker: a method for efficient prediction of bacterial sRNA targets based on a two-step model for hybridization.PLoS One,2011, 6(7): e22705.   
[12] Busch A, Richter A S, Backofen R. IntaRNA: efficient prediction of bacterial sRNA targets incorporating target site accessbility and seed regions. Bioinformatics,2008,24(24): 2849-2856.   
[13] Lorenz R,Bernhart S H, Zu Siederdissen C H, et al. ViennaRNA Package 2.0.Algorithms for Molecular Biology,2011, 6(1): 26.   
[14]Tafer H,Hofacker IL.RNAplex:a fast tool for RNA-RNA interaction search. Bioinformatics,2008,24(22): 2657-2663.   
[15] Kery MB,Feldman M,Livny J, et al. TargetRNA2: identifying targets of smallregulatory RNAs inbacteria. Nucleic acids research, 2014, 42(W1): W124-W129.   
[16] Kriger J, Rehmsmeier M. RNAhybrid: microRNA target prediction easy,fast and flexible. Nucleic acids research,2006,34(suppl 2): W451-W454.   
[17] Papenfort K, Vanderpool C K. Target activation by regulatory RNAs in bacteria. FEMS microbiology reviews, 2015,39(3): 362-378.   
[18] Ingolia N T, Ghaemmaghami S,Newman JR S,et al. Genome-wide analysis in vivo of translation with nucleotide resolution using ribosome profiling. Science, 2009, 324(5924): 218-223.   
[19] Wang J, Rennie W,Liu C, et al. Identification of bacterial sRNA regulatory targets using ribosome profiling.   
Nucleic acids research,2015,43 (21): 10308-10320.   
[20] Delihas N,Forst S.MicF: an anti sense RNA gene involved in responseof Escherichiacoil to global stress factors . Journal of molecular biology,200l,3 13(1) : 1-12.   
[21] Douchin V,Bohn C,Bouloc P.Down-regulation of porins by a small RNA bypasss the essentiality of the regulated intramembrane proteolysisprotease RseP in Escherichia coli. Journal of Biological Chemistry,2006,281(18):12253-12259.   
[22] Antal M,Borteau V,Douchin V,et al.A small bacterial RNA regulates a Putative ABC transporter Journal of Biological Chemistry,2005,280(9): 7901-7908.   
[23]董浩，彭小薇，王晓英，等．染色质免疫共沉淀技术对羊种布鲁氏菌转录调控因子 MucR 靶基因的筛 选．中国农业大学学报,2016,21(4):102-106. Dong H,Peng X W,Wang X Y,et al.Identification of the targets of MucR by chromatin immunop recip itation in Brucella melitensis[J]. Journal of China Agricultural University,2016,(O4):102-106.   
[24] Pulvermacher S C, Stauffer L T, Stauffer G V. Role of the sRNA GcvB in regulation of cycA in Escherichia coli. Microbiology,2009,155(1): 106-114.   
[25] Rasmussen A A,Eriksen M, Gilany K,et al. Regulation of ompA mRNA stability the role of a small regulatory RNA in growth phase-dependent control. Molecular microbiology, 2005,58(5):1421-1429.   
[26] Cho K H, Kim JH. Cis-encoded non-coding antisense RNAs in streptococci and other low GC Gram $\left( + \right)$ （20 bacterial pathogens. Frontiers in genetics, 2015, 6.   
[27] Davanloo P,Rosenberg A H,Dunn JJ, et al. Cloning and expression of the gene forbacteriophage T7 RNA polymerase. Proceedings of the National Academy of Sciences,1984, 81(7): 2035-2039.   
[28] McCullen C A, Benhammou JN, Majdalani N, et al. Mechanism of positive regulation by DsrA and RprA small noncoding RNAs: pairing increases translation and protects rpoS mRNA from degradation. Journal of bacteriol0gy,2010,192(21): 5559-5571.   
[29] Salvail H,Lanthier-Bourbonnais P,Sobota JM, et al. A smallRNA promotes siderophore production through transcriptional and metabolic remodeling. Proceedings of the National Academy of Sciences,2010,107(34): 15223-15228.   
[30] Opdyke JA,Fozo E M, Hemm M R, et al. RNase II participates in GadY-dependent cleavage of the gadX-gadW mRNA. Journal of molecular biology, 2011, 406(1): 29-43.   
[31] Opdyke JA,Fozo E M, Hemm MR,et al. RNase II participates in GadY-dependent cleavage of the gadX-gadW mRNA. Journal of molecular biology,2011, 406(1): 29-43.   
[32] Tramonti A,De Canio M,De Biase D. GadX/GadW - dependent regulation of the Escherichia coli acid fitness island: transcriptional control at the gadY-gadW divergent promoters and identification offour novel 42 bp GadX/GadW - specific binding sites. Molecular microbiology,2008,70(4): 965-982.   
[33] Mackie GA.RNase E: at the interface of bacterial RNA procesing and decay.Nature Reviews Microbiology,2012,11(1):45-57.   
[34] Saramago M,Barria C,dos Santos RF,et al.The role of RNases in theregulation of small RNAs.Current Opinion in Microbiology,2014,18(4): 105-115.   
[35] Wang J,Rennie W,Liu C, et al. Identification ofbacterial sRNA regulatory targets using ribosome profiling. Nucleic acids research, 2015: gkv1158.   
[36] Smirnov A,Forstner K U, Holmqvist E,et al. Grad-seq guides the discovery of ProQ as a major small RNA-binding protein. Proceedings of the National Academy of Sciences,2016,113(41): 11591-11596.   
[37] Zhang A, Schu D J, Tjaden B C,et al. Mutations in interaction surfaces diferentially impact E.coli Hfq association with small RNAs and their mRNA targets. Journal of molecular biology，2013,425(19): 3678-3697.   
[38] Majdalani N,Cunning C, Sledjeski D,et al. DsrA RNA regulates translation of RpoS message by an anti-antisense mechanism, independent of its action as an antisilencer of transcription. Proceedings of the National Academy of Sciences,1998,95(21): 12462-12467.   
[39] Majdalani N, Hermandez D, Gottesman S.Regulation and mode of action of the second small RNA activator of RpoS translation,RprA.Molecular microbiology,2002,46(3): 813-826.   
[40]Mandin P, Gotesman S. Integrating anaerobic/aerobic sensing and the general stress response through the ArcZ small RNA. The EMBO journal, 2010, 29(18): 3094-3107.   
[41] Lee C A,Fournier MJ, Beckwith J. Escherichia coli 6S RNA is not essential for growth or protein secretion. J Bacteriol,1985,161(3): 1156-1161.   
[42] Willkomm D K, Hartmann R K. 6S RNA: an ancient regulator of bacterial RNA polymerase rediscovered. Biol Chem,2005,386(12): 1273-1277.   
[43] Smaldone GT,Revelles O,Gaballa A,et al.A global investigation of the Bacilus subtilis iron-sparing response identifies major changes in metabolism. Journal of bacteriology,2012,194(10): 2594-2605.   
[44]Richter AS, Schleberger C,Backofen R. Seed-based INTARNA prediction combined with GFP-reporter system identifies mRNA targets of the small RNA Yfr1. Bioinformatics,2010,26(1): 1-5.   
[45] Romeo A,Sonnleitner E,Sorger-Domenigg T,et al. Transcriptional regulation of nitrate assimilation in Pseudomonas aeruginosa occurs via transcriptional antitermination within the nirBD-PAl779-cobA operon. Microbiology,2012,158(Pt 6): 1543-1552.   
[46] Romeo T. Global regulation by the small RNA-binding protein CsrA and the non-coding RNA molecule CsrB. Molecular microbiology,1998,29(6): 1321-1330.   
[47] Wilderman P J， Sowa N A，David J. Identification of tandem duplicate regulatory small RNAs in Pseudomonas aeruginosa involved in iron homeostasis. PNAS,2004,101(26): 9792-9797.   
[48] Khan MA,Gopel Y,Milewski S,etal.Two SmallRNAs Conserved in Enterobacteriaceae Provide Intrinsic Resistance to Antibiotics Targeting the Cell Wall Biosynthesis Enzyme Glucosamine-6-Phosphate Synthase. Frontiers in Microbiology,2016,7.   
[49] Rutherford S T, van Kessel JC,Shao Y,et al. AphA and LuxR/HapR reciprocally control quorum sensing in vibrios.Genes & Development, 2011,25(4): 397-408.   
[50] Rutherford S T, van Kessel JC, Shao Y,et al. AphA and LuxR/HapR reciprocall control quorum sensing in vibrios.Genes & Development, 2011,25(4): 397-408.   
[51] Romeo A,Sonnleitner E,Sorger-Domenigg T,et al. Transcriptional regulation of nitrate assimilation in Pseudomonas aeruginosa occurs via transcriptional antitermination within the nirBD-PAl779-cobA operon. Microbiology,2012,158(Pt 6): 1543-1552.   
[52] Jonas K,Melefors O.The Escherichia coli CsrB and CsrC smal RNAs are strongly induced during growth in nutrient-poor medium. FEMS microbiology leters, 2009, 297(1): 80-86.   
[53] Oglesby A G,Murphy ER, Iyer VR, et al.Fur regulates acid resistance in Shigell flexneri via RyhB and ydeP.Molecular microbiology,2005, 58(5): 1354-1367.   
[54] Dudin O, Lacour S, Geiselmann J.Expresion dynamics of Rpo S/Crl-dependent genes in Escherichia coli . Research in Microbiology,2013,164(8): 838-847.   
[55] Updegrove TB,Wartell R M. The influence of Escherichia coli Hfq mutations on RNA binding and sRNA· mRNA duplex formation in rpoS ribo regulation. Biochimica et Biophysica Acta (BBA)-Gene Regulatory Mechanisms,2011,1809(10): 532-540.   
[56] Majdalani N, Hernandez D,Gottsman S. Regulation and mode of action of the second small RNA activator of RpoS translation,RprA. Molecular microbiology,2002, 46(3): 813-826.   
[57] Papenfort K, Said N, Welsink T, et al. Specific and pleiotropic paterns of mRNA regulation by ArcZ,a conserved,Hfq - dependent small RNA. Molecular microbiology, 2009,74(1): 139-158.   
[58] Sledjeski DD, Gupta A, Gottesman S.The smallRNA,DsrA,is essential for the low temperature expresion of RpoS during exponential growth in Escherichia coli. The EMBO Journal,1996,15(15): 3993.   
[59] Zhang A, Altuvia S, Tiwari A, et al. The OxyS regulatory RNA represses rpoS translation and binds the Hfq (HF - I) protein. The EMBO journal,1998,17(20): 6061-6068.   
[60] Gaida S M,Al-Hinai MA,IndurthiD C,et al. Synthetic tolerance: three noncoding smal RNAs,DsrA,ArcZ and RprA,acting supra-additively against acid stress. Nucleic acids research,2013, 41(18): 8726-8737.   
[61] Kang Z,Wang Q, Zhang H,et al.Constructionof a stress-induced system in Escherichia coli for efficient polyhydroxyalkanoates production. Applied microbiology and biotechnology,2008,79(2): 203-208.   
[62] Aiba H: Mechanism of RNA silencing by Hfq-binding smallRNAs. Curr Opin Microbiol,2007,10:134-139.   
[63] Park H, Bak G, Kim SC,et al. Exploring sRNA-mediated gene silencing mechanisms using artificial small RNAs derived from a natural RNA scaffold in Escherichia coli. Nucleic acids research，2013,41(6): 3787-3804.   
[64] Sharma V,Yamamura A, Yokobayashi Y. Enginering Artificial Small RNAs for Conditional Gene Silencingin Escherichia coli. ACS synthetic biology,2011,1(1): 6-13.   
[65] Yoo S M,Na D,Lee S Y,et al. Design and use of synthetic regulatory smallRNAs to control gene expression in Escherichia coli .Nature protocols, 2013, 8(9): 1694-1707.   
[66]Na D,Lee S Y,Kim B,et al.Metabolic engineering of Escherichiacoli for the production of phenol from glucose .Nature biotechnology,2014,9, 621 - 629.   
[67] Liu Y, Zhu Y,Li J, Shin H, Chen RR,DuG,Liu L, Chen J: Modular pathway enginering of Bacillus subtilis for improved N-acetylglucosamine production. Metabolic engineering, 2014, 23: 42-52.   
[68] Cho C,Lee S Y.Efficient gene knockdown in Clostridium acetobutylicum by synthetic small regulatory RNAs. Biotechnology and Bioengineering,2017,114(2): 374-383.   
[69] Nakashima N,Tamura T. Conditional gene silencing of multiple genes with antisense RNAs and generation of a mutator strain of Escherichia coli. Nucleic acids research, 2009,37(15): e103-e103.   
[70] Jones A J, Venkataramanan K P,Papoutsakis T.Overexpression of two stress-responsive,small non-coding RNAs, 6S and tmRNA, imparts butanol tolerance in Clostridium acetobutylicum. FEMS microbiology letters, 2016,363(8): fnw063.   
[71] Kang Z, Wang X,Li Y,et al. Small RNA RyhB as a potential tool used for metabolic engineering in Escherichia coli. Biotechnology leters,2012,34(3): 527-531.   
[72] Li F, Wang Y, Gong K, et al. Constitutive expresson of RyhB regulates the heme biosynthesis pathway and increases the 5-aminolevulinic acid accumulation in Escherichia coli.FEMS microbiology leters,2014, 350(2): 209-215.   
[73] Negrete A,Majdalani N,Phue JN,etal. Reducing acetate excretion from E.coli K-12 byover-expressing the small RNA SgrS.New biotechnology,2013,30(2): 269-273.   
[74] Chae T U,Kim W J,Choi S,et al. Metabolic engineeringof Escherichia coli for the production of 1,3- diaminopropane,a three carbon diamine. Scientific reports, 2015,5:13040-13053.   
[75] Zhao Y,Wang C S,Li F F,et al. Targeted optimization of central carbon metabolism for engineering succinate production in Escherichia coli. BMC biotechnology,2016,16(1): 52.   
[76] 姚元锋，赵莹，赵广荣．人工 sRNA 沉默 csrA 基因以优化大肠杆菌生产L-酪氨酸．中国生物工程 杂志，2013，33(8) 60-65. Yao Y F,Zhao Y,Zhao G R.Artificial sRNAs silencing csrA to optimize the production of L-tyrosine in Escherichia coli[J].China Biotechnology,2013,33(8): 60-65.   
[77] Meng HL,Xiong Z Q,Song SJ,et al. Construction of polyketide overproducing Escherichiacoli strains via synthetic antisense RNAs based on in silico fluxome analysis and comparative transcriptome analysis. Biotechnology journal,2016,11,530-541.   
[78] Yoo S M,Na D,Lee S Y. Design and use of synthetic regulatory small RNAs to control gene expression in Escherichia coli. Nat Protoc 2013,8:1694-1707.