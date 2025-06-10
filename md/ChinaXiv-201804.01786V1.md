# CRISPR-dCas9调控基因转录的研究进展

田开仁1,2.3，薛二淑1,2.3，宋倩倩1,2.3，乔建军1,2,3，李艳妮1.,2\*\*（1 天津大学化工学院 天津 300072；2系统生物工程教育部重点实验室 天津 300072；3天津化学化工协同创新中心合成生

物学平台 天津 300072.)

摘要CRISPR/Cas9 系统已不仅仅是一种革命性的基因编辑工具，还能在各种原核和真核生物中调控基因转录。近年来，由CRISPR/Cas9衍生而来的CRISPR-dCas9 系统已被用于基因成像、高通量筛选、基因调控、必需基因功能研究及表观遗传调控等多个方向。本文总结了近年来CRISPR-dCas9系统在激活或抑制基因转录、降低脱靶效率、sgRNA 与转录强度及特异性之间的联系等方面的研究进展，以期对CRISPR-dCas9系统定向调控基因转录的研究提供参考和帮助，并就其未来可能的改进进行了展望。

关键词：CRISPR-dCas9；基因调控；转录激活；转录抑制

中图分类号：Q789

# The Research Progress of CRlSPR-dCas9 in Transcriptional Regulation

TIAN Kai-ren1,23,XUEEr-shu1,2,3,SONG Qian-qian1,2,3,QIAO Jian-jun1,2,3,LIYan-i2\*

(1.SchoolofhemicalEngineeringandTechnology,TianjinUniversityTanjin3Oo7,China;2.KeyLaboratoryofytems BioenginerigofnistryofducationanjinUiversityanjoo,na;3.SyBioesearchlatfo,Clbtie Innovation Centerof Chemical Science and Engineering,Tianjin University,Tianjin3ooo72,China.)

# Abstract

The CRISPR/Cas9 system is not only a revolutionary tool for gene editing but also regulates gene transcription in various prokaryotic and eukaryotic organisms. In the recent years, the system of CRISPR-dCas9 derived from CRISPR/Cas9 has been used in many fields such as gene imaging, high-throughput screening, gene regulation, investigating essential gene function and epigenetic regulation. In this review, the recent advances of CRISPR-dCas9 for activating or inhibiting gene transcription,reducing off-targeting efficiency and combing the intrinsic relationship between sgRNA and transcriptional regulation, application in the life science and further upgrading were described.

Key Words: CRISPR-dCas9, transcriptional regulation, transcriptional activation, transcriptional inhibition

# 1引言

CRISPR/Cas9（Clusteredregularlyinterspacedshortpalindromicrepeats-CRISPRassociated9,CRISPR/Cas9）系统是细菌和古细菌在长期进化过程中形成的一种适应性免疫防御系统，可以有效地切割降解进入细菌和古细菌细胞中外源 DNA[1-3]。近年来CRISPR/Cas9 就如同暴风雨一样席卷了生物学的众多领域[4-6]，同时这一系统也在不断的被改造升级。现在的CRISPR/Cas9系统已不仅仅是一种革命性的基因组编辑工具，还是一种重要的基因调控工具。缺乏核酸酶活性但仍具有RNA引导下与DNA 结合能力的Cas9蛋白（CRISPR-dCas9）已被广泛用在许多宿主中调节基因表达。该系统不会造成DNA双链断裂，可避免在特定基因上的永久突变对宿主的影响[7]。

CRISPR-dCas9系统的作用机理是：a.人工设计合成的一小段特异性RNA序列（single guideRNA,sgRNA）与dCas9 和转录调控因子形成的融合蛋白组成复合体；b.然后该复合体中的sgRNA的碱基互补配对序列与目标基因结合，c.最后是dCas9-sgRNA复合物作为一个支架将一系列效应分子募集到特定的位置来激活基因转录或因空间位阻阻止RNA聚合酶与启动子结合及抑制转录延伸，从而发挥调节功能（见图1（a）和图2（a)）。目前，已有很多关于CRISPR-dCAS9在转录水平调控基因表达的研究报道。本综述对CRISPR-dCas9系统的研究进展进行了详细介绍并对其发展前景进行了展望。

# 2CRISPR-dCas9与基因转录激活（CRISPRa）

研究人员发现将CRISPR/Cas9系统中Cas9的两个保守的内切核酸酶结构域分别进行RuvC催化结构域的第10位天冬氨酸突变为丙氨酸（D10A）和HNH催化结构域的第840 位组氨酸突变为丙氨酸（H840A）后，Cas9 蛋白失去核酸内切酶活性（deadCas9，dCas9)，不能切割DNA但dCas9仍能与sgRNA形成复合物并与特定DNA序列结合[2,8]。将转录激活因子或者RNA 聚合酶@亚基与dCas9融合表达，并利用 sgRNA的特异性引导功能，该系统即可用于激活特定基因的表达（CRISPRa）。

1998 年,Simon 等9发现大肠杆菌RNA聚合酶的α-亚基可提高RNA聚合酶活性并激活转录，可大大提高基因转录水平。Bikard等[10]在大肠杆菌中构建了@亚基与dCas9的融合蛋白，研究该系统是否可激活报告基因转录。在该研究中，与对照组相比，融合表达蛋白使报告基因的转录水平提高了2.8倍，但这一系统在大肠杆菌中只是进行了初步验证。最近，Yu等[I在溶杆菌中鉴定并利用@亚基与dCas9的融合蛋白显著激活了五个共表达的基因，这是CRISPRa系统在原核生物中的再次应用和验证。而在真核细胞中，VP64 激活域与dCas9的C末端融合蛋白不仅仅可以激活报告基因，还可以激活被沉默的内源基因或者上调可转录基因的转录量[8,12]（见图1b)。Polstein 等[13]在此基础上通过将光诱导的异二聚化蛋白CRY2和CIB1分别同转录激活域VP64及dCas9融合进一步开发了一个在蓝光下可激活内源基因的系统，可以实现在时间和空间上精确控制细胞行为。与此同时，以上描述的这种拆分成两部分的Cas9系统被借鉴并形成了一个分子更小的dCas9-VP64 系统[14]。这些系统都能在时间和空间动态激活基因转录。

研究显示：dCas9-VP64系统利用单个sgRNA在哺乳动物细胞中的激活转录水平较低，而在启动子上游区域设计多个 sgRNA可以增强该系统的激活能力[15,16]。这些现象提示研究者们可以通过改进融合蛋白使其能募集多个转录激活因子或具有多个激活子结构域从而增强CRISPRa系统的激活能力。基于这一理念，多种二代dCas9-激活子融合蛋白被开发出来，这些系统包括多拷贝数的VP16、VPR(VP64-p65-Rta)及 SunTag（募集多个抗体-VP64 复合物）[17-19]（见图1（c）,（d）和（e))。Chavez等[18]的研究表明这些不同构造的系统在多种哺乳动物细胞中能很好的激活基因。另外，转录激活因子可以通过一个RNA发夹环和MS2噬菌体外壳蛋白（与RNA 发夹环具有极高的亲和力）吸附到 sgRNA上[20]。Konermann 等[19]对 sgRNA的骨架进行修饰设计并开发出了一种与dCas9-VPR类似的系统（Synergistic actvation mediator,SAM）。SAM系统通过共表达dCas9-VP64融合蛋白、带发夹结构的 sgRNA及一个MS2-VP64或MS2-P65-HSF1融合蛋白来实现RNA介导的靶向激活基因转录。SAM系统不仅仅能显著激活编码基因的表达，而且对长链非编码RNA（Long noncoding RNA,lncRNA）的表达也具有很好的调节作用。

dCas9还可以与表观遗传修饰子融合来靶向修饰增强子区域的表观遗传标记，从而激活基因转录。在最近的一项研究中，将dCas9与转录激活因子乙酰转移酶 p300（一种高度保守的乙酰转移酶，涉及广泛的细胞过程）的催化核心融合（dCas9-p300core）可以在人类细胞中激活基因转录（见图1（f)）。该融合蛋白在靶位点催化组蛋白H3赖氨酸27乙酰化，引起启动子和近端或远端增强子变化从而显著激活靶基因转录。dCas9-p300core 引起的基因激活在全基因组范围内具有高度的特异性[21]。

(a) (c) VP64-P65-Rta or (VP16)n dCas9 dCas9 sgRNA 球 Protein-sgRNA 集 35 -10 H 1 HHH complexassembly Genomic DNA RNAP (d) VP64O 明 W sfGFP scFv A No-endonuclease activity dCas9 RNA-guide targeting M HAE HHHIH . 1 35 RNAp10 . Genomic DNA dCas9 (e) HSF1 00 VP64 1 -35W -10 O p65 D HHHHA. 1 HHHH MS2 2 Genomic DNA RNAP HHHHH 集 235 -1 Genomic DNA RNAP   
(b) VP64 (f) p300 core dCas9 dCas9 ARNAP m -35 -10 m H HHA HIHHIL H 1 趙書 Genomic DNA RNAP Genomic DNA Enhancer

dCas9-VP64 系统（c）dCas9-VPR或者(VP16)n系统（d）dCas9-SunTag 系统（e） SAM系统（f）dCas9-

p300core系统

Fig.1 The mechanism of CRISPRa and diferent types of CRISPRa activation systems（a）the mechanism of CRISPRa activates gene transcription（b） The dCas9-VP64 system（c）The dCas9-VPR or $( \mathrm { V P l } 6 ) _ { \mathrm { n } }$ system (d) The dCas9-SunTag system（e）The SAM system（f） The dCas9-p300core system

虽然这些二代CRISPRa系统已经证明可以通过体外sgRNA导向来进行有效功能遗传学研究，但是在体内使用它们仍然是一个不小挑战[22,23]。这主要是因为dCas9 融合蛋白体内转导和靶向激活效率低。另外，编码dCas9/sgRNA 和共转录激活复合物的基因序列太大，远远超出了大多数常见病毒载体运载能力，然而这是目前来说最有前途的用于体内基因递送的方法[22,23]。新的小型化的Cas9 可能为今后的研究提供更多的帮助。而体内激活率的提高应寄希望于新的转录激活子

的获得或已有系统的进一步优化设计。

# 3CRISPR-dCas9与抑制基因转录（CRISPRi）

干扰基因转录的能力，这一衍生的CRISPR系统被称为CRISPRi。CRISPRi通过dCas9-sgRNA复合物与目标DNA的靶向结合形成空间位阻，抑制目标DNA 的转录，进而形成对目标基因的表达抑制[24]。CRISPRi系统主要通过以下两种方式抑制目标基因转录：（1）阻止RNA聚合酶与目标基因的启动子结合抑制转录；（2）与开放阅读框靶向结合，抑制转录延伸（相当于转录终止子）（见图2（a)）。2013 年，Qi[25]等人在大肠杆菌首次证明了单独的dCas9就可以作为转录抑制子并实现序列特异性基因转录抑制，并证明这种CRISPR干扰（CRISPRi）系统是在基因组范围内选择性干扰基因表达的简单方法。与此同时，Bikard 等[10]使用CRISPR-dCas9系统通过阻止RNA聚合酶与启动子序列的结合或通过阻断RNA聚合酶的移动（相当于转录终止子）在大肠杆菌中实现可编程的转录抑制。dCas9引起的转录抑制与 sgRNA的位置有关，其抑制基因的转录量是可控的。与dCas9激活系统相比，dCas9 抑制系统的活性仅仅与sgRNA的靶向位置有关，理论上在不同的基因间、细胞和物种中均可发挥抑制作用。2015 年,Piatek 等[26]将 dCas9的C 端与 SRDX的转录阻遏结构域融合并成功用于植物细胞中内源基因的转录抑制。不久之后，Choudhary 等[27]介绍了一种CRISPR干扰（CRISPRi）方法，可有效抑制分枝杆菌中靶基因的表达。Smith等[28]系统地分析了各种gRNA设计，以便在酿酒酵母中实现有效的转录抑制，并提出有效的文库设计和全基因组可编程基因抑制目的的规则。目前，CRISPRi系统已在多种模式生物中得到了验证[28-31]。然而，这种基因转录抑制的研究很少在缺乏已开发的基因组工程工具的非常规微生物中得到证实。尽管dCas9 能够在真核生物中抑制基因转录，但是其抑制水平较低。为了提高转录抑制强度，研究人员[15,32]将dCas9 与不同转录抑制子融合表达并进行相关验证，最终发现KRAB-dCas9 融合蛋白具有较高的抑制效率，sgRNA设计合理时候其抑制效率可达 $90 \mathrm { \sim } 9 9 \%$ ，但是需要筛选多个sgRNA才能获得1\~2个有效的 sgRNA[33]（见图2（b)）。虽然 dCas9-KRAB工具也是依赖于局部染色质修饰来沉默基因表达（募集染色质修饰复合物）[34]，但是通过直接去除增强子特定区域特定的活化表观遗传标记也可以使基因沉默。例如，组蛋白去甲基化酶LSD1与小的同Cas9 同源的dNmCas9 融合后可直接去除激活的H3K4 甲基化标记导致增强子失效而抑制的基因转录[35]（见图2（c))。该工具通过增强子去活化发挥作用，提供了一种新的调控转录的表观遗传学方法。

![](images/39b75d54e5c771577eb01e046ad55fe9e03b47e5897a06d94647bb96fa8a5d47.jpg)  
图2CRISPRi系统作用机制及不同类型的CRISPRi抑制系统(a)CRISPRi系统抑制基因转录机理（b)

dCas9-KRAB系统（c）dCas9-LSD1系统

Fig.2 The mechanism of CRISPRi and diferent types of CRISPRi inhibition systems （a）the mechanism of CRISPRi inhibits Gene Transcription（b）The dCas9-KRAB system（c）The dCas9-LSDl system

# 4CRISPR-dCas9的特异性和sgRNA设计

关于Cas9的脱靶效应已有很多研究报道，但是仍然未能很好的解决这一问题[36,37]。通常情况下，研究人员通常利用外源的绿色荧光蛋白作为靶标，设计特异性的 sgRNA 和阴性对照 sgRNA，用RNA 测序技术检测 sgRNA 的特异性。对于dCas9系统，如dCas9-VP64 和 SAM系统也采用类似的技术证明系统的特异性。尽管研究表明这些系统具有良好的特异性，但是研究的sgRNA数量较少，说服力还不够[19]。对于CRISPRi系统，Gibert 等[33]研究了1\~5bp 的 sgRNA 碱基错配对Cas9 和dCas9-KRAB 特异性的影响，发现dCas9-KRAB 系统对碱基错配更加敏感。这表明不同的效应子对dCas9 特异性的影响可能不一样，对于每一个新的dCas9融合蛋白，都有必要研究其特异性。

一直以来，关于sgRNA设计的研究从未停止过，希望通过精心设计的 sgRNA序列来增加RNA的靶向性并降低脱靶效率。有一些证据表明，精心设计的 sgRNA可以降低脱靶率。虽然在CRISPR/Cas9系统用于基因编辑的时候其脱靶范围是全基因组[4,8]，但是CRISPR-dCas9 系统用于调节基因功能脱靶造成转录抑制或激活的概率要小很多[3338]。因为这些脱靶的 sgRNA必须锚定到TSS上下1000bp的范围内才有可能导致靶基因转录抑制或者激活。CRISPR-dCas9系统 sgRNA的设计不仅要考虑脱靶率，还要考虑碱基配对与DNA结合位点对调控作用的影响[39]。然而现在还没有一个成熟的准则和算法来评估 sgRNA用于基因调控时的脱靶率，所以研究人员不得不采用Cas9 的脱靶算法[39-42]。当然研究人员也给出一定的参考：例如 Bikard 等[10]表明，当PAM与TSS 的距离在区域-50bp 到 $+ 5 0 \mathrm { { b p } }$ 之间时，单个的dCas9的抑制效应是最明显的。而Qi等[7说明，当靶向启动子区域和区域中的TFBS 结合位点时，导向RNA与正义链或反义链结合都具有良好的抑制效果，但在启动子区域的下游时只有与非模板链结合才有效。与此同时，2016 年的一项研究系统地评估了人类细胞中 sgRNA位置对CRISPRi效率的影响，分析了155个靶向41个基因的 sgRNAs 并发现CRISPRi效率很大程度上依赖于招募的效应复合物与靶基因转录起始位点（TSS）的结合位置[43]。专门针对CRISPRa 系统的 sgRNA设计指南相对来说更少。Liao 等[44]的最新研究显示一个长度缩短为14bp 的sgRNA(dgRNA）的CRISPR 激活系统仍能靶向高效的激活特定基因的转录。从某种意义上来说，CRISPR-dCas9系统 sgRNA的设计有其独特的特性。随着生物信息学的发展以及CRISPR-dCas9系统的不断开发和应用，研究人员最终必将解决这一问题。

# 5CRISPRa系统的应用和局限性

CRISPRa系统可以用于在多种生物过程中调节基因表达，包括干细胞分化、沉默基因激活、遗传缺陷补偿和全基因水平筛选。2016年，Black 等[45]的最新成果表明使用具有dCas9的N端和C端融合VP64 转录激活域的融合蛋白（VP64-dCas9-VP64）证明了直接通过激活特定内源性基因的细胞重编程可以将成纤维细胞诱导为神经元细胞。

一般来说，功能缺失型筛选可以通过RNAi或者CRISPR/Cas9系统来实现，而功能获得型筛选可以用过表达特定基因的方式来实现，但是这些方式都不能实现全基因组范围的基因调控。Konermannn 等[19]基于强大的dCas9-SAM系统设计并使用由70,290条引导RNA构成的文库在人类细胞全基因组范围内筛选针对BRAF抑制剂的抗性基因。这些筛选出来的基因与以前的发现高度一致，同时也发现了一些新的基因。总的来说，该技术用于抗性基因的筛选以及全基因组范围内的基因扰动是完全可行的。

CRISPR相关系统从诞生以来就得到了广泛的关注，但是由于其潜在的脱靶性以及DSB切割修复过程中的造成的突变，大大限制了这一技术的临床应用。CRISPR-dCas9这一衍生出来的系统保留了sgRNA介导直接靶向特定基因特性，但是不具有切割DNA的功能，这无疑会避免因为基因突变而给人体带来的未知伤害。尽管CRISPRa系统表现出了很好的医疗潜力，但是走向临床或者相关的研究报道还较少。一个潜在的医疗应用例子是将这一系统作为抗逆转录病毒的佐剂以治愈艾滋病[46,47]。CRISPRa 系统被用来激活潜伏的HIV 基因组上的基因，使其更易被抗逆转录病毒药物影响或者被免疫系统清除。当然，也可以利用这一系统快速筛选可以高效激活HIV基因的调控元件，并开发出新的方式用于治疗HIV。而另一个例子对于重度烧伤病人来说将是一个福音，Sun 等[48]通过靶向EDA编码基因的启动子的CRISPR-dCas9 激活系统有效诱导并重新编程人类骨髓来源的间充质干细胞，以促进其分化为汗腺样细胞。

现在CRISPRa系统的应用越来越广，并丰富了研究人员调节基因功能的手段[11]。Yu 等[11]利用CRISPR-dCas9与 $\omega$ 亚基的融合蛋白靶向激活溶杆菌的WAP基因簇的五个共表达的基因的转录与过表达自我保护基因结合的方法提高了对耐甲氧西林的金黄色葡萄球菌有强烈活性的抗生素-环脂缩肽WAP-8294A 的产量。2018 年，Gallego-Bartolomé 等[49]开发了一种利用人脱甲基酶 TET1催化结构域与修饰后的CRISPR/dCas9-SunTag共同组成的CRISPR-dCas9的靶向去甲基化系统，该系统可以在拟南芥中靶向除去甲基化状态，定向激活FWA基因。虽然 CRISPRa技术较其他传统手段有其显著的优势，但是也有不少问题，例如脱靶效应、递送困难及潜在的免疫原性，其中还有一个值得特别关注的问题就是激活内源基因依赖 sgRNA的选择以及激活效率较传统过表达低的多。当然在研究特定基因功能时，这可能不是一个大问题。但是如果涉及到多个因素时（例如成熟细胞的重编程)，这无疑会成倍加大研究的难度。因此，如何进一步提高激活转录的强度及快速设计大量且特异性良好的sgRNA需要进一步研究和探索。

# 6CRISPRi系统的应用和局限性

CRISPRi（CRISPRInterference）系统是在CRISPR/Cas9 的基础上衍生而来的，可以特异性的抑制基因的转录而并非将基因knockout来实现调控。同时，CRISPRi系统能将靶基因的转录量控制在不同水平。必需基因功能的发挥决定了细胞的核心过程，但是必需基因功能的丧失会导致细胞无法生存，基因突变或者基因缺失都不能用来研究必需基因功能。2016 年，Qi等[50]利用CRISPRi技术敲低了枯草杆菌的每个必须基因，并探究细菌相关表型。这一研究为在体内系统研究必需基因功能提供了一个广泛适应于各种微生物和比较分析的一个新的参考。而在 2017年，Dong 等[51]为了更好的理解金黄色葡萄球菌的遗传机制，开发了一种新的CRISPR-dCas9干扰方法用于靶基因的快速敲减。此外，使用这种方法可以同时抑制多个基因转录。CRISPRi系统在研究基因功能方面具有明显的优势。

长链非编码RNA（IncRNA）是一种神秘的长200多个核苷酸但不会编码任何蛋白质的分子。虽然lncRNA大量存在，但是人们并不清楚有多少数量的lncRNA以及哪些 lncRNA在基础生物学功能中发挥重要作用。高效快速的鉴定方法的开发对于研究这类重要的调控RNA具有重要的意义。Liu等[52]利用CRISPRi技术在多个细胞系中关闭非编码转录本的转录，鉴定出了细胞生长所需的 499 个lncRNA。因此，在发生细胞增殖的癌症等疾病中，这些鉴定出的位点可能用于开发一种基于RNA干扰的新的治疗方法。

CRISPRi这一能特异性使基因转录抑制以及可调控转录水平的平台已经在各个领域得到了良好的应用，例如基于分析代谢途径利用CRISPRi调控必须基因转录水平来提高代谢物产量[53]或减少副产物的分泌[54]、全基因组范围内基因筛选[55]及敲低特定基因转录量以研究基因功能[40]等。尽管目前的转录抑制系统已经非常高效并且应用广泛，但是仍有改进的空间，例如高丰度表达时抑制可能不明显和 sgRNA的筛选问题。

# 7展望

随着科研人员的不断研究改进以及更多新的CRISPR系统的发现，基于CRISPR系统的基因干扰或基因激活系统必将进一步被改进和优化。目前，dCas9与效应子融合表达的基因序列及融合蛋白的相对分子量较大，严重影响该系统在微生物中的开发和应用，同时也使体内应用时递送难度加大。以此来看，新的更小的CRISPR系统的发掘具有重大意义。一个在非培养微生物中挖掘出来的CasX就具有开发出更小的调控基因转录系统的潜在可能性[56]。最近，Hu等[57]通过改进得到的xCas9具有更多的识别位点和更低的脱靶效率。虽然xCas9系统的应用潜力需要进一步验证，但是谁能确定这个蛋白不能用于构建脱靶效率更低的基因调控系统。

由于其高效性和简便性，CRISPR/Cas9及CRISPR-dCas9系统已经广泛应用于生物医学和生物技术领域。无论是基因组编辑还是靶标调控在不久的将来必将完美应用于临床。尽管由于一些限制和缺点，CRISPR系统并不像我们想象的那么完美（例如，引导RNA的具体作用机制及如何进一步降低或者消除脱靶超出了我们现在的知识范围)，但是随着学习和探索的不断深入，我们面临的问题将会逐渐被解决。这些问题的解决可以帮助我们更好地利用CRISPR-dCas9系统去造福人类并将其用于临床，为干细胞分化、代谢工程、细胞重编程、基因功能研究和筛选以及工业微生物育种技术的发展奠定良好的基础。

总之，随着CRISPR-dCas9系统的出现，CRISPRa/CRISPRi系统增强了我们探究基因功能及调控基因转录的能力。我们认为CRISPR调控系统将会应用到越来越多的原核和真核生物中，并且将在人类疾病的研究中发挥更加重要的作用。

# 参考文献

[1]Gasiunas G, Barrangou R, Horvath P,et al. Cas9-crRNA ribonucleoprotein complex mediates specific DNA cleavage for adaptive immunity in bacteria [J]. Proceedings of the National Academy of Sciences of the United States of America,2012,109(39): E2579-2586.   
[2]Jinek M, Chylinski K,Fonfara I, et al. A Programmable Dual-RNA-Guided DNA Endonuclease in Adaptive Bacterial Immunity [J]. Science,2012,337(6096): 816-821.   
[3]Westra E R, van Erp PB,Kunne T, et al. CRISPR immunity relies on the consecutive binding and degradation of negatively supercoiled invader DNA by Cascade and Cas3 [J]. Molecular Cell, 2012, 46(5): 595-605.   
[4] Hsu P D, Scott D A, Weinstein J A, et al. DNA targeting specificity of RNA-guided Cas9 nucleases [J]. Nature Biotechnology,2013,31(9): 827-832.   
[5]Hwang W Y,Fu Y, Reyon D,et al. Efficient genome editing in zebrafish using a CRISPR-Cas system [J]. Nature Biotechnology,2013,31(3): 227-229.   
[6]Jiang W, Bikard D, Cox D, et al. RNA-guided editing of bacterial genomes using CRISPR-Cas systems [J].Nature Biotechnology, 2013,31(3): 233-239.   
[7]Qi L S,Larson M H, Gilbert L A, et al. Repurposing CRISPR as an RNA-guided platform for sequence-specific control of gene expression [J]. Cell,2013,152(5): 1173-1183. and paired nickases for cooperative genome engineering [J]. Nature Biotechnology，2013,31(9): 833-838.   
[9]Dove S L and Hochschild A. Conversion of the omiga subunit of Escherichia coli RNA polymerase into a transcriptional activator or an activation target [J]. Genes & Development,1998, 12(5): 745-754.   
[10] Bikard D, Jiang W, Samai P, et al. Programmable repression and activation of bacterial gene expression using an engineered CRISPR-Cas system [J]. Nucleic Acids Research, 2013,41(15): 7429-7437.   
[11] Yu L, Su W, Fey P D, et al. Yield Improvement of the Anti-MRSA Antibiotics WAP-8294A by CRISPR/dCas9 Combined with Refactoring Self-Protection Genes in Lysobacter enzymogenes OH11 [J]. ACS Synthetic Biology, 2018, 7(1): 258-266.   
[12] Maeder M L,Linder S J, Cascio V M, et al. CRISPR RNA-guided activation of endogenous human genes [J]. Nature Methods, 2013,10(10): 977-979.   
[13] Polstein L R, Gersbach C A.A light-inducible CRISPR-Cas9 system for control of endogenous gene activation [J]. Nature Chemical Biology, 2015,11(3): 198-200.   
[14] Zetsche B, Volz S E, Zhang F.A split-Cas9 architecture for inducible genome editing and transcription modulation [J]. Nature Biotechnology, 2015, 33(2): 139-142.   
[15] Gilbert L A, Larson M H, Morsut L, et al. CRISPR-mediated modular RNA-guided regulation of transcription in eukaryotes [J]. Cell, 2013, 154(2): 442-451.   
[16] Kearns N A，Genga R M J，Enuameh M S,et al. Cas9 effector-mediated regulation of transcription and diferentiation in human pluripotent stem cells [J]. Development, 2014,141(1): 219-223.   
[17] Tanenbaum M E, Gilbert L A, Qi L S, et al. A Protein-Tagging System for Signal Amplification in Gene Expression and Fluorescence Imaging [J]. Cell, 2014,159(3): 635-646.   
[18] Chavez A, Scheiman J, Vora S,et al. Highly efficient Cas9-mediated transcriptional programming [J]. Nature Methods, 2015,12(4): 326-328.   
[19] Konermann S, Brigham M D, Trevino A E,et al. Genome-scale transcriptional activation by an engineered CRISPR-Cas9 complex [J]. Nature, 2015,517(7536): 583-588.   
[20] Peabody D S. The RNA binding size of bacteriophage MS2 coat protein [J]. EMBO Journal,1993, 12(2): 595-600.   
[21] Hilton I B, D'ppolito A M, Vockley C M, et al. Epigenome editing by a CRISPR-Cas9-based acetyltransferase activates genes from promoters and enhancers [J]. Nature Biotechnology,2015, 33(5): 510-517.   
[22] Thakore P I, Black JB, Hilton I B,et al. Editing the epigenome: technologies for programmable transcription and epigenetic modulation [J]. Nature Methods,2016,13(2): 127-137.   
[23] Komor A C,Badran A H,Liu D R. CRISPR-Based Technologies for the Manipulation of Eukaryotic Genomes [J]. Cell, 2017,168(1-2): 20-36.   
[24] Dominguez A A, Lim W A, Qi L S. Beyond editing: repurposing CRISPR-Cas9 for precision genome regulation and interrogation [J]. Nature Reviews Molecular Cell Biology,2015,17(1): 5-15. [25] Larson M H, Gilbert L A, Wang X, et al. CRISPR interference (CRISPRi) for sequence-specific control of gene expression [J]. Nature Protocols, 2013, 8(11): 2180-2196.   
[26] Piatek A,Ali Z, Baazim H, et al. RNA-guided transcriptional regulation in planta via synthetic dCas9-based transcription factors [Jl. Plant Biotechnology Journal, 2015,13(4): 578-589. [27] Choudhary E,Thakur P,Pareek M, et al. Gene silencing by CRISPR interference in mycobacteria [J]. Nature Communications, 2015,6: 6267-6277.   
[28] Smith JD, Suresh S,Schlecht U, et al. Quantitative CRISPR interference screens in yeast identify chemical-genetic interactions and new rules for guide RNA design [J]. Genome Biology, 2016,17: 45-56.   
[29] Singh A K, Carette X, Potluri L P, et al. Investigating essential gene function in Mycobacterium tuberculosis using an efficient CRISPR interference system [J]. Nucleic Acids Research, 2016, 44(18): e143.   
[30] Wang Y, Zhang Z T, Seo S O, et al. Gene transcription repression in Clostridium beijerinckii using CRISPR-dCas9 [J]. Biotechnology and Bioenginering, 2016,113(12): 2739-2743.   
[31] Yao L, Cengic I, Anfelt J, et al. Multiple Gene Repression in Cyanobacteria Using CRISPRi [J]. ACS Synthetic Biology, 2016, 5(3): 207-212.   
[32] Konermann S,Brigham M D, Trevino A E,et al. Optical control of mammalian endogenous transcription and epigenetic states [J]. Nature, 2013, 500(7463): 472-476.   
[33] Gilbert L A, Horlbeck M A, Adamson B, et al. Genome-Scale CRISPR-Mediated Control of Gene Repression and Activation [J]. Cell, 2014,159(3): 647-661.   
[34] Thakore P I, D'Ippolito A M, Song L, et al. Highly specific epigenome editing by CRISPR-Cas9 repressors for silencing of distal regulatory elements [J]. Nature Methods,2015,12(12): 1143-1149. [35] Kearns N A, Pham H, Tabak B,et al. Functional annotation of native enhancers with a Cas9-histone demethylase fusion [J]. Nature Methods, 2015,12(5): 401-403.   
[36] Ran FA,Hsu PD,Lin C Y,et al. Double nicking by RNA-guided CRISPR Cas9 for enhanced genome editing specificity [J]. Cell, 2013,154(6): 1380-1389.   
[37] Huang H, Zheng G, Jiang W, et al. One-step high-efficiency CRISPR/Cas9-mediated genome editing in Streptomyces [J]. Acta Biochimica et Biophysica Sinica, 2015, 47(4): 231-243.   
[38] Polstein L R, Perez-Pinera P, Kocak D D, et al. Genome-wide specificity of DNA binding, gene regulation,and chromatin remodeling by TALE- and CRISPR/Cas9-based transcriptional activators [J]. Genome Research,2015,25(8): 1158-1169.   
[39] Xu H, Xiao T, Chen C H, et al. Sequence determinants of improved CRISPR sgRNA design [J]. Genome Research, 2015,25(8): 1147-1157.   
[40] Martinko A J, Truillet C, Julien O,et al. Targeting RAS-driven human cancer cels with antibodies to upregulated and essential cell-surface proteins [J]. eLife, 2018,7: e31098.   
[41] Doench JG, Hartenian E, Graham D B,et al. Rational design of highly active sgRNAs for CRISPR-Cas9-mediated gene inactivation [J]. Nature Biotechnology,2014,32(12): 1262-1267. [42] Wong N, Liu W, Wang X. WU-CRISPR: characteristics of functional guide RNAs for the CRISPR/Cas9 system [J]. Genome Biology,2015,16 (1) : 218-225.   
[43] Radzisheuskaya A, Shlyueva D, Muller I, et al. Optimizing sgRNA position markedly improves the efficiency of CRISPR/dCas9-mediated transcriptional repression [J]. Nucleic Acids Research, 2016, 44(18): e141.   
[44] Liao H K， Hatanaka F， Araoka T， et al. In Vivo Target Gene Activation via CRISPR/Cas9-Mediated Trans-epigenetic Modulation [J]. Cell, 2017, 171(7): 1495-1507.   
[45] Black JB,Adler A F, Wang H G, et al. Targeted Epigenetic Remodeling of Endogenous Loci by CRISPR/Cas9-Based Transcriptional Activators Directly Converts Fibroblasts to Neuronal Cels [J]. Cell Stem Cell, 2016, 19(3): 406-414.   
[46] Zhang Y, Yin C, Zhang T, et al. CRISPR/gRNA-directed synergistic activation mediator (SAM) induces specific, persistent and robust reactivation of the HIV-1 latent reservoirs [J]. Scientific Reports, 2015,5: 16277-16290.   
[47] Limsirichai P, Gaj T, Schaffer D V. CRISPR-mediated Activation of Latent HIV-1 Expression [J]. Molecular Therapy,2016,24(3): 499-507.   
[48] Sun S, Xiao J， Huo J，et al. Targeting ectodysplasin promotor by CRISPR/dCas9-effector effectively induces the reprogramming of human bone marrow-derived mesenchymal stem cells into sweat gland-like cells [J]. Stem Cell Research & Therapy,2018, 9(1): 8-17.   
[49] Gallego-Bartolomé J, Gardiner J, Liu W, et al. Targeted DNA demethylation of the Arabidopsis genome using the human TET1 catalytic domain [J]. Proceedings of the National Academy of Sciences of the United States of America.2018,115(9): E2125-E2134.   
[50] Peters JM, Colavin A, Shi H, et al.A Comprehensive, CRISPR-based Functional Analysis of Essential Genes in Bacteria [J]. Cell, 2016,165(6): 1493-506.   
[51] Dong X,Jin Y,Ming D,et al. CRISPR/dCas9-mediated inhibition of gene expression in Staphylococcus aureus [J]. Journal of Microbiological Methods. 2017,139: 79-86.   
[52] Liu S J, Horlbeck M A, Cho S W, et al. CRISPRi-based genome-scale identification of functional long non-coding RNA loci in human cells [J]. Science, 2017, 355(6320): aah7111.   
[53] Lv L, Ren Y L, Chen J C,et al. Application of CRISPRi for prokaryotic metabolic engineering involving multiple genes，a case study: Controllable P(3HB-co-4HB) biosynthesis [J]. Metabolic Engineering,2015,29:160-168.   
[54] Wang J, Zhao P,Li Y,et al. Engineering CRISPR interference system in Klebsiell pneumoniae for attenuating lactic acid synthesis [J]. Microbial Cell Factories,2018,17(1): 56-67.   
[55] Evers B,Jastrzebski K, Heijmans JP, et al. CRISPR knockout screening outperforms shRNA and CRISPRi in identifying essential genes [J]. Nature Biotechnology,2016,34(6): 631-633.   
[56] Burstein D,Harrington L B, Strutt S C,et al. New CRISPR-Cas systems from uncultivated microbes [J]. Nature,2016, 542(7640): 237-241.   
[57] Hu JH, Miler S M, Geurts M H, et al. Evolved Cas9 variants with broad PAM compatibility and high DNA specificity [J]. Nature,2018,556(7699): 57-63.