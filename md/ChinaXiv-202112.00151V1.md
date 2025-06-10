# 基于转录组的不同火龙果品种抗性差异分析

李健星1,2，谭艳芳1，李冬兴1,2，王斌1,2，陈婷1,2，黄甫昭1.2，陆树华1,2 \*

1.广西壮族自治区中国科学院广西植物研究所，广西桂林541006；2.广西喀斯特植物保育与恢复生态学重点实验室，广西壮族自治区中国科学院广西植物研究所，

广西桂林，541006)

摘要：不同的品种抗性不同，为进一步探究不同火龙果品种之间的抗性差异，为后续火龙果抗性育种提供参考，该研究利用 Illumina HiSeq 2000 测序平台对‘普通白肉'（BR）和‘厄瓜多尔黄龙’（EY）两个品种进行转录组测序分析，并参考GO Ontology、KEGG 等公共数据库对差异表达基因进行功能分类与富集分析。结果显示：（1）BR与EY共有14248个差异基因，其中5446个基因上调，8802个基因下调。（2）相关GO 功能分析表明这些差异基因主要参与酶催化活性、细胞组分、代谢过程等，其中参与氧化还原酶活性的349个差异基因在BR中表达量上调。（3）KEGG通路分析显示，大部分差异基因富集在新陈代谢、生物合成等，其中参与角质、木栓质和蜡质生物合成的差异基因有12个，如CYP86与CER1等。参与氧化还原酶活性的差异基因在BR中较EY 表达量上调，且显著富集，表明 BR 与EY在生长发育、细胞代谢过程差异显著。参与角质、木栓质和蜡质生物合成的差异基因在BR 中表达量上调，此类基因在BR中具有较高的表达量且显著富集，表明 BR可能具有较强的抗旱和抗病能力。

关键词：火龙果，转录组，品种，差异表达基因

# Resistance difference between different varieties of pitaya based on transcriptome data

LI Jianxing $^ { 1 , 2 }$ , TAN Yanfangl,LI Dongxing1,2, WANG Bin $^ { 1 , 2 }$ , CHEN Ting1,2, HUANG Fuzhao1,2, LU Shuhua1,2\*

(1. Guangxi Institute of Botany, Guangxi Zhuang Autonomous Region and Chinese Academy of Science, Guilin 541006, Guangxi, China; 2. Guangxi Key Laboratory of Plant Conservation and Restoration Ecology in Karst Terrain, Guangxi Institute of Botany, Guangxi Zhuang Autonomous Region and Chinese Academy of Sciences, Guilin 541006, Guangxi, China)

Abstract: Different varieties have different resistances. In order to further explore the resistance differences in different varieties of pitaya fruit and provide a reference for further study on breeding of pitaya fruit resistance. Our study using Ilumina HiSeq 2OoO sequencing platform to sequencing the transcriptome of‘Putongbairou’（BR） and‘Ecuador Yellow’（EY）.Functional classification and enrichment analysis of differentially expressed genes（DEGs） were performed by reference to GO Ontology,KEGG and others databases. The results were as follows: (1) There were 14 248 DEGs between BR and EY,of which 5 446 genes were up-regulated and 8 802 genes were down-regulated. (2) GO functional analysis showed that these DEGs are mainly involved in enzyme catalytic activity, cell components, metabolic processes, etc. Among them, there were 349 differential genes involved in oxidoreductase activity. (3） KEGG pathway analysis showed that most of the DEGs were enriched in metabolism, biosynthesis,etc.，and 12 key genes such as CYP86 and CER1 involving in Cutin, suberine and wax biosynthesis. We found the expression of DEGs involved in oxidoreductase activity were higher in BR than that in EY,which significantly enriched, indicating that may be differences in growth and cell metabolism between BR and EY. DEGs involved in the biosynthesis of Cutin, suberine and wax biosynthesis were up-regulated in BR. Such genes have higher expression in BR, and significantly enriched, suggesting that BR may be superior drought and disease resistance than EY.

Key words: pitaya fruit, transcriptomic, different varieties， differentially expressed genes火龙果属仙人掌科（Cactaceae）、量天尺属（Hylocereus Briton&Rose）或蛇鞭柱属（Selenicereus (Berger) BritIsraelton and Rose）植物，营养美味以及独特的外观使其成为消费者追捧的新兴热带水果（陶金 etal.,2014)。近几年，我国火龙果产业发展迅猛，据最新数据，截止2020年底，全国火龙果种植面积已超过100 万亩，并形成以广西、广东、海南、云南和贵州五省（区）为核心的主产区。特别近年来在广西石漠化区推广种植成功，形成贫困山区脱贫致富双赢的“果化模式”，火龙果耐旱、耐瘠，有利于石山地区水土保持，在改善生态环境的同时又可增加可观的经济效益。作为一种新兴水果，近年来国内外对火龙果的研究也越来越深入，主要集中在不同品种的理化性质和营养价值、功能性物质提取、栽培技术、病虫害研究（赵志平 和 杨春霞，2006；Menezes etal.,2015；陈煜 et al.,2017；彭金轮，2017；Kee et al.,2019；Magalhaes et al.,2019；Rahmati etal.,2019)，转录组测序与微卫星引物开发（杨仕美等,2018；武志江等,2020)，属间亲缘关系、杂交及新品种的培育（Tel-Zuret al.,2004a; Tel-Zur et al.,2004b; Tel-Zur et al.,2011；Ortiz-Hernandez & Carrillo-Salazar,2012；Tel-Zur et al.,2012）等方面。

量天尺属包含有14个种，世界范围内广泛栽培的火龙果主要为量天尺属植物，有 $H .$ undatus、H.monacanthus 和 H.megalanthus （Ortiz-Hernandez & Carrillo-Salazar,2012)。通过杂交，目前火龙果品种繁多，文献有报导收集218份种质资源（黄凤珠等，2019)，也有相关文献报导，在种质资源保存过程中发现，不同品种的火龙果其抗旱和抗病能力差异显著（梁秋玲等，2011；李润唐等，2017)。目前通过RNA-seq技术，可获得大量的转录组序列信息，开展基因表达与功能分析，构建信号通路等。本文对火龙果品种'普通白肉'和·厄瓜多尔黄龙”植株幼嫩茎段组织进行转录组序列从头组装，通过Unigene 表达丰度分析、差异表达分析、GO 和KEGG富集分析等，从转录组层面阐明火龙果不同品种之间的差异，为火龙果产业的发展、推广应用提供一定的理论支持。

# 1材料与方法

# 1.1 材料

火龙果品种‘普通白肉'（BR，以下简称‘白肉'）、‘厄瓜多尔黄龙’（EY，以下简称‘黄龙"）均取自广西壮族自治区中国科学院广西植物研究所火龙果研究基地（图1)，选取标记这两个品种茎段上开始出芽的位置，待其生长7d，取幼嫩茎段，每个品种设3个生物学重复，采集后立即放入液氮中，交由北京诺禾致源生物信息科技有限公司进行测序。

![](images/5dfeca8f9e730eaab91e068d7cb66fe1be709dfcbf5197725044a6da15aae604.jpg)  
图1试验用火龙果品种  
Fig.1 Pitaya fruit was used in the experiment

# 1.2文库构建

用带有Oligo（dT）的磁珠富集火龙果样品中的mRNA。随后将打断的mRNA作为模板，合成二链cDNA，再进行纯化，末端修复、加A尾并连接测序接头。最后进行PCR扩增，纯化PCR产物，构建文库。待文库检测合格后上机测序，采用llumina HiSeq"2000 PE150对样品转录组文库进行高通量测序。

# 1.3Denovo 拼接和注释

过滤测序得到Raw read，获得的Clean read。在Trinity软件（Grabherr et al.,2011）中进行De novo拼接。在NCBIblast中将拼接完成的Unigene与NCBI非冗余蛋白序列数据库、NCBI核酸序列数据库、Swiss-Prot数据库、KOG（Clusters of orthologous groups foreukaryoticcomplete genomes）数据库和KEGG（Kyotoencyclopedia of genes and genomes）数据库进行比对注释。利用HMMER3.0package与Protein family（Pfam）进行比对（hmmscane-value≤1e-2）。在Blast2go（http://www.blast2go.com/ b2ghome）软件和WEGO软件中进行GO（Gene Ontology）注释、分类统计。

# 1.4差异基因表达分析

采用DESeq2（Love et al.,2014）软件，进行样品组间的差异表达分析，将差异倍数llog2FoldChange|>1 且padj $< 0 . 0 5$ 作为筛选差异表达基因（DEGs）的条件。对符合条件的差异表达基因进行GO Ontology 和 KEGG Pathway 分类，利用超几何检验对注释到的不同的GO $( P < 0 . 0 5 )$ 和KEGG条目（ $( P < 0 . 0 5 ) ,$ 进行富集分析。采用FPKM 值(Fragmentsperkilobaseof transcriptper million fragments mapped）来展现基因表达水平的高低，在R软件中绘制差异基因表达量的火山图。

# 2结果与分析

# 2.1转录组测序与组装

为进一步理解不同品种火龙果的分子差异机制，对2个品种火龙果共6个样本进行RNA-seq，获得平均7.71 Gb clean reads，Q30 均在 $90 \%$ 以上，总碱基中的GC数量比例为$4 9 . 0 6 \%$ （表1），表明测序结果良好，cleanreads质量合格，可进行下一步数据分析。

# 表1测序数据质量表

Table1 Quality table of sequencing data   

<html><body><table><tr><td>样品</td><td>原始Reads</td><td>高质量Reads</td><td>数据量</td><td>准确率>0.999</td><td>GC含量</td></tr><tr><td>Sample</td><td>Raw Reads</td><td>Clean Reads</td><td>Clean bases</td><td>Q30 (%)</td><td>GC content (%)</td></tr></table></body></html>

<html><body><table><tr><td>BR_1</td><td>53 250 692</td><td>52 512 370</td><td>7.88Gb 91.36</td><td>48.98</td></tr><tr><td>BR_2</td><td>50 237 344</td><td>49 478 466</td><td>7.42Gb 90.77</td><td>49.56</td></tr><tr><td>BR_3</td><td>50 441 754</td><td>49 424 658</td><td>7.41Gb 90.14</td><td>48.69</td></tr><tr><td>EY_1</td><td>58 014 828</td><td>56 782 758</td><td>8.52Gb 91.12</td><td>48.82</td></tr><tr><td>EY_2</td><td>53 025 282</td><td>51 813 250</td><td>7.77Gb 90.99</td><td>49.16</td></tr><tr><td>EY_3</td><td>49 516 914</td><td>48 245 168</td><td>7.24Gb 90.75</td><td>49.19</td></tr></table></body></html>

注：BR_1、BR_2、BR_3分别为火龙果‘白肉’的3个重复；EY_1、EY_2、EY_3分别为火龙果‘黄龙’的3个重复。 Notes:BR_1,BR_2andBR_3are threebiologicalduplicatesofpitaya‘Bairou’;EY_1,EY_2andEY_3arethreebiological duplicates of pitaya‘Ecuador Yellow'.

# 2.2火龙果转录组Unigene 的功能注释

使用 BLAST 将所有Unigene 与 NR、GO、KO、SwissPort、PFAM、KOG、NT共7个数据库进行一致性比对分析，对各数据库注释的Unigene 数目进行统计，进而获得火龙果转录组Unigene的功能注释信息。结果表明，28551条Unigene（ $4 5 . 0 2 \%$ ）在NR数据库比对成功得到注释，在GO、KO、SwissPort等数据库获得注释的Unigene数目依次为 $2 3 \ 0 8 2 ( 3 6 . 4 \%$ ）11 011（ $1 7 . 3 6 \%$ ）、21352（ $3 3 . 6 7 \%$ ）（图2)。4493条Unigene同时在所有数据库中注释，至少有1种数据库注释成功共34692条（ $54 . 7 1 \% )$ ，28714条未获得注释。

![](images/23941736f9a08238851a7a1e3c109ce39655335a228771a1173db8e6a96f1534.jpg)  
图2注释结果柱状图

A．注释到NR 数据库；B.注释到NT数据库；C.注释到KO数据库；D.注释到 SwisProt数据库；E.注释到 PFAM 数据库；F.注释到GO数据库；G.注释到KOG 数据库。   
A.Anotated inN;B.AnnotatedinNT;C.Annotated inKO;D.Anotated inSwisProt;E.AnnotatedinPFAM;F.Aotated in GO; G. Annotated in KOG.

Fig.2 Histogram of Unigene annotation results

# 2.3不同火龙果品种差异表达基因分析

对‘白肉’和‘黄龙’火龙果的差异表达基因进行分析。结果表明，‘白肉’和‘黄龙'火龙果之间有14 248个差异基因（padj $< 0 . 0 5$ 且|log2FoldChange|>1)，其中，‘白肉’相对于‘黄龙'，有5446个基因上调，表达量高于‘黄龙’，有8802个基因下调，表达量低于‘黄龙’（图3）。

![](images/40f20e3654d14a87f4848850c613f4b4d9f30c8608c9fd93c7ccb32500dd7a36.jpg)

X、Y坐标轴均取筛选条件值的对数形式，图中每个点代表一个差异表达基因，红色圆点表示有显著性差异的上调基因，绿色圆点表示有显著性差异的下调基因，蓝色圆点表示无显著性差异的基因。FoldChange 表示差异倍数，padj表示校正后的 pvalue。  
X-axisandY-axispresentthresholdvalueinlogtransform.Eachdotisadifferential expressdgenes.Dotsinredmeanup-regulation genes,Dots in gren mean down-regulation gene and dots in blue means non-regulation genes.FoldChangerepresents fold change, padj represents after correction pvalue.

# 图3BRvsEY间基因差异表达分析火山图

Fig.3 Volcano graph of Differentially expressed genes in BR vs EY

# 2.4差异表达基因GO功能分类与富集分析

为了分析‘白肉’与‘黄龙’差异基因的生物学功能，将14248个差异基因注释到GOOntology 数据库中,分别从生物学过程（biological process,BP）、细胞组分（cellular component,CC）和分子功能（molecular function，MF）3个方面，其中在生物学过程分类中，参与氧化还原过程、碳水化合物代谢过程的差异基因数目最多，分别为632和371个；在细胞组分分类中，主要是被膜等的差异基因组多，有234个；在分子功能分类中，主要是氧化还原酶最多，有618个。

以富集 $P$ 值小于0.05作为富集标准。在生物过程分类中富集了包括DNA整合、mRNA修饰、mRNA甲基化、有丝分裂、RNA甲基化等39个条目；在细胞组分分类中显著富集了包括肌质、肌质网等28个条目；在分子功能分类中显著富集了包括四吡咯结合、血红素结合、铁离子结合等54项。结果说明，‘白肉’与‘黄龙’在生长发育、细胞代谢过程等方面存在差异。对上调和下调的差异基因分别进行功能分类，在‘白肉’与‘黄龙’差异表达基因中满足 $P$ 值小于0.05的GO条目即为GO功能显著富集，部分结果见图4。对5446个上调基因进行GO功能分类与富集分析，结果显示，在生物学过程分类中，参与氧化还原过程（oxidation-reduction process）的GO term 显著富集，其中包含差异基因 341个；在分子功能分类中，参与氧化还原酶活性（oxidoreductase activity）的GO term 显著富集，其中包含差异基因349个，表明‘白肉’与‘黄龙’在生长发育、细胞代谢过程等方面存在差异，在分子功能分类中，抗氧化活性（antioxidant activity）的GO term 富集，表明‘白肉’和‘黄龙’在抗旱性方面有差异。在下调基因中，主要集中在DNA整合（DNA integration）等方面，差异无显著表现。

![](images/13b33b5aecb9303fb3d6bbc98ddeb88044c103284864fecc6d8cf15dd15b75e3.jpg)

A：A．氧化还原过程；B．氧化还原酶活性；C．抗氧化活性；D．氧化还原酶活性，作用于过氧化物作为受体；E．铁离子结合；F．四吡咯结合；G．血红素结合。  
A.oxidation-reduction process；B.oxidoreductase activitys；C.antioxidant activity；D.oxidoreductase activity，actingonperoxide as acceptor;E.iron ion binding;F.tetrapyrrole binding; G.heme binding.  
B:A.DNA 整合；B.mRNA 修饰；C.mRNA 甲基化；D.RNA 甲基化；E.病毒壳体；F.virion 部件；G.RNA 定向 RNA聚合酶复合物；H.mRNA甲基转移酶活性；I.氧裂解酶活性，作用于磷酸盐；J.萜烯合酶活性；K.ADP结合；L.RNA甲基转移酶活性；M.腺苷甲硫氨酸依赖性甲基转移酶活性；N.RNA 定向RNA 聚合酶活性;  
A.DNA integration; B.mRNA modification; C.mRNA methylation; D.RNA methylation; E.viralcapsid;F.virion part;G.

RNA-directedRNA polymerase complex；H.mRNA methyltransferase activity;I.carbon-oxygen lyaseactivity,actingon phosphates;J. terpenesynthaseactivity；K.ADPbinding;L.RNAmethyltransferaseactivity；M. S-adenosylmethionine-dependent methyltransferase activity; N.RNA-directed RNA polymerase activity.

图4BRVSEY上调（A）下调（B）差异表达基因的GO分类及富集分析 Fig. 4 GO classification and enrichment analysis of up(A)-down(B)- regulation differentially expressed genes in BR VS EY

# 2.5差异表达基因KEGGPathway富集分析

‘白肉’与‘黄龙’共有2237个差异表达基因注释到特定的KEGG通路中，这些通路主要为新陈代谢、生物合成、糖酵解、信号传导、蛋白质加工等，其中注释到为新陈代谢的差异基因838，占差异基因总注释数目的 $3 7 . 5 \%$ ，注释到生物合成的差异基因335个，占差异基因总注释数目的 $1 5 . 0 \%$ 。以 $P < 0 . 0 5$ 作为筛选显著富集的条件，‘白肉’中表达量较‘黄龙上调的差异基因主要富集在生物合成方面，例如角质、木栓质和蜡质生物合成(cutin,suberineand wax biosynthesis）、苯丙素的生物合成（phenylpropanoid biosynthesis）、吲哚生物碱的生物合成（indole alkaloid biosynthesis）等（图5）。其中参与角质、木栓质和蜡质生物合成的差异基因有12个，分别是HHT1、CYP86B1、CYP86A1、FAR、CYP86A1、HHT1、PXG、CYP86A4S、K15404、CER1FARK15404、CER1K15404、CER1。‘白肉’中表达量较‘黄龙’下调的差异基因主要富集在生物合成方面，例如类倍半萜和三萜的生物合成sesquiterpenoid and triterpenoid biosynthesis、精氨酸的生物合成（arginine biosynthesis）、脂肪酸的生物合成（fatty acid biosynthesis）等（图6）。

![](images/c9262f495e61a27f362db4b87390897b9a057e945f170540ad0dd5f6ef41e0ed.jpg)

A.维生素B6代谢；B.泛醌和其他萜类醌生物合成；C.酪氨酸代谢；D.RNA聚合酶；E.嘧啶代谢；F.蛋白酶体；G．光 合作用天线蛋白；H.光合作用；I.苯丙素的生物合成；J.苯丙氨酸代谢；K.戊糖和葡糖醛酸相互转化；L.氧化磷酸 化；M.吲哚生物碱生物合成；N.甘氨酸、丝氨酸和苏氨酸代谢；O.半胱氨酸和蛋氨酸代谢；P.角质、木栓质和蜡质 生物合成；Q.甜菜色素生物合成；R.抗坏血酸盐和醛酸盐代谢；S.精氨酸和脯氨酸代谢；T.氨基糖和核苷酸糖代谢。 A.Vitamin B6 metabolism；B.Ubiquinoneand other terpenoid-quinone biosynthesis；C.Tyrosine metabolism;D.RNA polymerase；E.Pyrimidine metabolism；F.Proteasome；G.Photosynthesis-antenna proteins;；H.Photosynthesis；I. Phenylpropanoid biosynthesis；J.Phenylalaninemetabolism；K.Pentoseand glucuronateinterconversions；L.Oxidative phosphorylation;M.Indole alkaloid biosynthesis;N.Glycine,serineand threonine metabolism;O.Cysteine and methionine metabolism;P.Cutin,suberineand waxbiosynthesis;Q.Betalain biosynthesis;R.Ascorbateand aldarate metabolism;S. Arginine and proline metabolism; T.Amino sugar and nucleotide sugar metabolism.

图5‘白肉’与‘黄龙’火龙果差异表达上调基因富集前20的KEGG通路

![](images/4867175f9bbccfc5a21d986e4065d04d641f77aa23172a6f210c8ff82b7308f6.jpg)  
Fig. 5BR VS EY Differentially expressed down-regulated genes were significantly enriched in the top 20 KEGG pathways   
图6‘白肉’与‘黄龙’差异表达下调基因富集前20的KEGG通路

A.缬氨酸、亮氨酸和异亮氨酸降解；B.类倍半萜和三萜的生物合成；C.RNA降解；D.核黄素代谢；E.丙酮酸代谢；F.苯丙素生物合成；G.过氧物酶体；H.其他类型的O-聚糖生物合成；I.其他聚糖降解；J.糖基磷脂酰肌醇-锚生物合成；K.糖酵解/糖异生；L.果糖和甘露糖代谢；M.脂肪酸降解；N.脂肪酸的生物合成；O.昼夜节律-植物；P.类胡萝卜素生物合成；Q.光合生物的固碳作用；R.生物素代谢；S.精氨酸的生物合成；T.α-亚麻酸代谢。A.Valine,leucineand isoleucine degradation；B.Sesquiterpenoidand triterpenoid biosynthesis；C.RNA degradation;D.Riboflavin metabolism;E.Pyruvatemetabolism;F.Phenylpropanoid biosynthesis; G.Peroxisome; H.Other typesofO-glycanbiosynthesis；I.Otherglycandegradation；J.Glycosylphosphatidylinositol(GP)-anchorbiosynthesis；K.Glycolysis/Gluconeogenesis;L.Fructose and mannose metabolism;M.Fattyacid degradation;N.Fattacid biosynthesis;O.Circadianrhythm-plant;P.Carotenoid biosynthesis; Q.Carbonfixationinphotosyntheticorganisms;R.Biotinmetabolism;S.Argininebiosynthesis; T.alpha-Linolenic acid metabolism.

Fig. 6BRVS EY Differentially expressed up-regulated genes were enriched in the top 20 KEGG pathways

# 3讨论

高通量测序技术已经成为不同品种差异分析的常用策略，例如烟草（李智奕，2014），大豆（张驰等，2015），桂花（张雪松等，2016），百香果（王宇等，2019）等。本研究中我们利用RNA-seq技术对火龙果不同品种进行转录组学分析，基于良好的测序结果，我们进一步分析‘白肉’与‘黄龙’火龙果二者之间的差异表达基因，发现共有14248个差异表达基因，通过GO Ontology分析表明这些差异基因主要富集在新陈代谢、生物合成、糖酵解、信号传导、蛋白质加工等过程，表明‘黄龙’可能在生长发育、抗性方面与‘白肉’有差异。在分子功能分类中，相较于‘黄龙’，‘白肉’火龙果上调表达的基因中，参与氧化还原酶活性（oxidoreductase activity）的差异基因349个，表明‘白肉’与‘黄龙’在生长发育、细胞代谢过程差异显著，‘白肉’比‘黄龙’的生长发育更快，代谢更加旺盛，与实际栽培种植过程中的现象相符，‘白肉’表现出比‘黄龙’更快的生长速度，在一年中结果的批次，果实的发育都有差异，‘白肉’一年结果大概8批，从授粉到成熟需要 $2 8 { \sim } 3 0 \mathrm { d }$ ，‘黄龙’一年结果2批，夏果和冬果，成熟期需要 $9 0 { \sim } 1 2 0 \mathrm { d }$ 。在分子功能分类中，抗氧化活性（antioxidantactivity）差异显著，表明‘白肉’和‘黄龙’在抗旱性方面有差异。为了在干旱环境中生存，仙人掌科植物必须具备干旱反应机制，特别是抗氧化防御系统。持续的干旱胁迫会导致氧化性物质如 $| \mathrm { O } ^ { 2 } \rrangle$ 、 $\mathrm { H } ^ { 2 } \mathrm { O } ^ { 2 }$ 、 $O ^ { 2 } .$ 、OH的积累，这些物质会损害细胞，甚至导致死亡（Fang＆Xiong,2015），这些抗氧化活性基因在‘白肉’中富集，上调表达，可能使得‘白肉’抗干旱能力强于‘黄龙’。

在KEGG Pathway 中以 $P < 0 . 0 5$ 作为富集条件，在‘白肉’上调表达的基因中，主要富集在角质、木栓质和蜡质生物合成，其中参与角质、木栓质和蜡质生物合成的差异基因有12个，主要代表有CYP86和CER1。植物蜡质是植物在进化过程中为了适应环境的变化而演变出来的一种结构，表皮蜡质在植物抵御外界不良环境、保持组织和器官功能、保证植物正常发育等方面起了重要的作用（胡晓敏等，2007；李魏强等，2006；任春涛等，2019）。上表皮蜡沉积的主要功能是减少表皮的水分流失，这一特性有助于增强耐旱能力。此外，在与草食性昆虫和植物病原真菌的相互作用中起着重要作用（Aarts etal.,1995），蜡质层在一定程度上可以使植物免受低温胁迫作用（李婧婧等，2011）。其中12个关键基因参与角质、亚黄素和蜡的生物合成，如CYP86编码o-基脂肪酸的形成，促进在软木脂生物合成，形成角质层。这些脂肪类生物聚合物可以防止植物水分和营养流失以及病原体的感染（Aarts et al,1995；Hoferetal.,2008）。CER1编码参与长链醛转化为烷烃的蛋白，这是植物体中蜡生物合成的关键步骤（Hofer etal.,2008）。本研究对这些关键调控基因分析发现，此类基因在‘白肉’中具有较高的表达量，这些可能与植物的抗旱和抗病有关。

# 参考文献

AARTS MG, KEIJZER CJ, STIEKEMA WJ, et al.,1995.Molecular characterization of the CER1 gene of arabidopsis involved in epicuticular wax biosynthesis and pollen fertility[J]. Plant Cell, 7(12): 2115-2127.   
BALAO F,HERRERA J, TALAVERA S, 2011. Phenotypic consequences of polyploidy and genome size at the microevolutionary scale: a multivariate morphological approach[J]. New phytol, 192: 256-265.   
CHEN Y， XIA ZK, GUO Q, et al., 2017. Optimization of Extraction Technology of Pitaya Seed Albumin by response Surface Method and Studies on its Antioxidant Activity [J]. Pharm Biot, 24(4):315-320.[陈煜，夏梓堃，郭俏，等，2017．火龙果籽白蛋白提取工艺及抗氧化能 力研究[J].药物生物技术，24（4）：315-320.]   
FANG Y, XIONG L. 2015. General mechanisms of drought response and their application in drought resistance improvement in plants[J]. Cell Mol Life Sci, 72 (4): 673.   
GRABHERR MG,HAAS BJ, YASSOUR M, et al., 2011. Full-length transcriptome assembly from RNA-Seq data without a reference genome[J]. Nat biotechnol, 29: 644-652.   
HOFER R, BRIESEN I, BECK M, et al., 2008. The Arabidopsis cytochrome P450 CYP86A1 encodes a fatty acid omega-hydroxylase involved in suberin monomer biosynthesis[J].JExp Bot, 59: 2347-2360.   
HU XM， ZHANG ZF，RAO LQ，et al.， 2007. Molecular biology research progress in the biosynthesis and genetic manipulation of plant cuticular wax [J]. J Wuhan Bot Res, 25 (4): 377-380.[胡晓敏，张志飞，饶力群，等，2007．植物角质层蜡质合成与调控的分子生物 学研究进展[J]．植物科学学报，25（4）：377-380.]   
HUANG FZ, LU GF,WU ZJ, et al. 2019. Analysis of fruit quality and character diversity of pitaya germplasm resources[J].S Chin Fruit,48 (6): 51-57.[黄凤珠，陆贵锋，武志江，等， 2019.火龙果种质资源果实品质性状多样性分析[J]．中国南方果树,48（06）：51-57.]   
KEE YJ, BAKAR MHA, HUDA-SHAKIRAH AR, et al., 2019. First report of reddish brown spot disease of red-fleshed dragon fruit (Hylocereus polyrhizus) caused by Nigrospora lacticolonia and Nigrospora sphaerica in Malaysia[J]. Crop Prot, 122: 165-170.   
LI JJ,HUANG JH, XIE SC, 2001. Plant wax and its response to environmental conditions: an overview[J].Acta Ecola Sin,31(2): 565-574.[李婧婧，黄俊华，谢树成，2001．植物蜡质 及其与环境的关系[J].生态学报，31（2）：565-574.]   
LI RT,WANG J, LIU HY, et al. 2017. Study on resistance of four pitaya cultivars to canker disease[J].Chin Trop Agric,75 (2):70-73.[李润唐，王静，刘虹源，等.2017.4个火龙果品 种对溃疡病的抗性研究[J]．中国热带农业,75（2）：70-73.]   
LI WQ, ZHANG ZB,LI JJ, 2006. Plant epicuticular wax and drought resistance as well as its molecular biology[J].JPlant Physiol Mol Biol,32(5): 505-512.[李魏强，张正斌，李景娟， 2006．植物表皮蜡质与抗旱及其分子生物学[J]．植物生理与分子生物学学报，32（5）： 505-512.]   
LI ZY.2014. Transcriptome analysis of different tobacco leaves [D]. Zhengzhou: Henan Agricultural University.[李智奕.2014．国内不同烟草品种的烟叶转录组分析[D]．郑州： 河南农业大学.]   
LIANG QL, WEI J,LI XY, et al. 2011. Identification on causal agent of dragon fruit stem rot and in-door determination of fungicide toxicity[J].S Chin Fruit,1: 9-12.[梁秋玲，韦健，李孝云, 等，2011．火龙果茎腐病病原鉴定及室内药剂毒力测定[J]．中国南方果树,1：9-12.]   
LOVE MI, HUBER W,ANDERS S. 2014. Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2[J]. Genome Biol, 15 (12): 550.   
MAGALHAES DS,DA SILVA DM, RAMOS JD, et al.， 2019. Changes in the physical and physico-chemical characteristics of red-pulp dragon fruit during its development[J]. Sci Hortic-amsterdam, 253: 180-186.   
MENEZES TP,RAMOS JD, BRUZI AT, et al., 2015.Artificial pollination and fruit quality in red pitaya[J]. Biosci J, 31: 801-807.   
PENG JL,2O17. Study on high quality and high yield cultivation techniques of Pitaya - Taking red pitaya as an example[J].S Chin Agric,11(12): 7-8.[彭金轮，2017.火龙果优质高产栽 培技术探究-以红肉火龙果为例[J]．南方农业，11（12）：7-8.]   
RAHMATI S,ABDULLAH A,KANG OLJBC,et al.， 2019. Effects of different microwave intensity on the extraction yield and physicochemical properties of pectin from dragon fruit (Hylocereus polyrhizus) peels[J]. Bioact Carbohydr Diet Fibre,18: 100186.   
REN CT, DONG LL, ZHANG XH, et al., 2019. Transcriptional regulation of plant cuticular wax synthesis and secretion[J].Plant Physiol J,55 (3):265-273.[任春涛，董路路，张新华，等, 2019．植物表皮蜡质生物合成与分泌过程中的转录调控[J]．植物生理学报，55（3）： 265-273.]   
TAO J,QIAO G, WEN XP,et al.， 2014. Establishment and optimization of IRAP marker methodology in dragon fruit[J].JHuazhong Agric Univ,33 (4): 33-38.[陶金，乔光，文晓鹏, 等，2014．火龙果IRAP分子标记反应体系的建立与优化[J]．华中农业大学学报，33（4)： 33-38.]   
TEL-ZUR N,ABBO S, BAR-ZVI D, et al. 2004a. Clone identification and genetic relationship among vine cacti from the genera Hylocereus and Selenicereus based on RAPD analysis[J]. Sci Hortic,100 (1-4): 279-289.   
TEL-ZUR N,ABBO S, BAR-ZVI D, et al. 2004b. Genetic relationships among Hylocereus and Selenicereus Vine Cacti (Cactaceae): Evidence from hybridization and cytological studies[J]. Ann Bot, 4: 527-534.   
TEL-ZUR N, MIZRAHI Y, CISNEROS A, et al., 2011. Phenotypic and genomic characterization of vine cactus collection (Cactaceae)[J]. Genet Resour Crop Evol, 58: 1075-1085.   
TEL-ZUR N, MOUYAI J, CISNEROS A, et al., 2012. Intergeneric hybridization within the tribe Hylocereeae, subfamily Cactoideae (Cactaceae) [J]. Isr JPlant Sci, 60: 325-334.   
WANG Y, CHEN N, YUAN QF, et al., 2019. Transcriptome analysis of three different varieties of passion fruit[J].Seed,38 (5):1-7.[王宇，陈楠，袁启凤，等，2019.3个不同品种百香果 转录组分析[J]．种子，2019，38（5）：1-7.]   
WU ZJ, DENG HY，LIANG GD, et al., 2020. Construction of molecular identity card of pitaya germplasm resources using fluorescent SSR Markers[J]. S Chin Fruit, 49 (4): 20-28.[武志江, 邓海燕，梁桂东，等，2020.利用荧光标记 SSR 构建火龙果种质资源分子身份证[J]．中 国南方果树，49（4）：20-28.]   
YANG SM, QIAO G,WEN XP, 2018. Establishment and optimization of EST-SSR marker methodology in pitaya[J].JMount Agric Biol,37(3): 14-20.[杨仕美，乔光，文晓鹏，2018. 火龙果 EST-SSR分子标记反应体系的建立与优化[J]．山地农业生物学报，37（3)：14-20.]   
YD ORTIZ-HERNANDEZ, CARRILLO-SALAZAR JA. 2012. Pitaya (Hylocereus spp.): A short review[J]. Com Sci, 3 (4): 220-237.   
ZHANG C,GAO ZR,DONG YK, 2015. Transcriptome analysis of inflorescences from four soybean cultivars[J].ChinJEcol,269 (12):111-116.[张驰，高振蕊，董友魁，等，2015．四 个大豆栽培种的转录组分析[J]．生态学杂志，269（12）：111-116.]   
ZHANG XS, PEI JJ, ZHAO LG, et al.， 2016. Transcriptome analysis of different Osmanthus reveals insight into the difference of Osmanthus oil components[J]. Nat Prod Res Dev, 28 (4): 529-535.[张雪松，裴建军，赵林果，等，2016.不同品种桂花转录组分析及桂花精油成 分差异的初步探讨[J]．天然产物研究与开发，28（04）：529-535.]   
ZHAO ZP, YANG CX, 2006. Development and prospect of pitaya[J]. Chin Seed Ind, 2: 13-14. [赵志平，杨春霞，2006.火龙果的开发与发展前景[J]．中国种业，2：13-14.]