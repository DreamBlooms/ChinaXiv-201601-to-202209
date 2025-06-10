# LncRNA在蜜蜂级型分化中的功能研究

郭昱1，5)\*\*苏松坤 2)\*\*陈盛禄3)\*\*\*张少吾 $^ { 1 , ~ 2 , ~ 4 ) * * * }$ 陈润生1)\*\*\*(中国科学院生物物理研究所，核酸生物学中国科学院重点实验室，北京100101;2)福建农林大学蜂学学院，福州350002；浙江大学蜂业研究所，杭州310058;4ResearchSchoolofiology,ColegeofMedicine,BiologyndEnironment,TheAustralianNational University,Australia;5)中国科学院大学，北京100049)

摘要蜜蜂的级型分化被证实是由蜂王浆中的 Royalactin决定，工蜂和蜂王幼虫在级型分化时编码基因的表达差异也被广泛研究．我们发现，在蜜蜂幼虫的级型分化过程中，lncRNA也有着显著的表达差异，因此认为，IncRNA 也参与了蜜蜂的级型分化过程．进一步的分析显示，IncRNA可能通过影响上下游基因的转录和功能执行的方式，在蜜蜂早期发育的多细胞组织发育、神经系统发育和转录调控的过程中起到重要的调控作用.

关键词蜜蜂，级型分化，lncRNA 学科分类号Q75，Q96，S89

DOI:10.16476/j.pibb.2015.0110

雌性蜜蜂的级型分化是一种典型的发育可塑性现象[I，同样的受精卵在不同的环境下接受不同的食物导致了完全不同的两种发育途径．蜂王具有更大的体型，更长的寿命，完整的生殖能力，在蜂巢中负责交配和产卵．工蜂体型较小，寿命短，不具有生殖能力，在蜂巢中执行各种职能，包括筑造蜂巢、食物采集、抚养幼虫、保卫蜂巢等．蜂王幼虫在发育过程中一直以蜂王浆为食物，工蜂幼虫只在发育早期得到了少量的工蜂浆作为食物，之后都是以蜂蜜为食物．蜂王浆中富含多种蛋白质、糖类和核酸[²-7，其中的一种蛋白质—Royalactin 被认为在蜜蜂的级型分化中起到了决定性的作用，将Royalactin加入到高温灭活的蜂王浆中，蜂王浆可以重新获得使幼虫发育为蜂王的能力．此外，蜂王浆中所包含的miRNA也被证实在蜜蜂的级型分化过程中发挥了一定的作用．对蜜蜂幼虫在级型分化过程中各种基因的表达也有过较多的研究，一些重要的基因在工蜂和蜂王幼虫中有非常明显的表达差异，并影响了工蜂和蜂王不同的发育方向[0-14].

研究报道，长链非编码RNA(long noncodingRNA，IncRNA)在发育和调控中发挥了重要的作用[15]，因此，我们对 $4 \sim 6$ 日龄的工蜂和蜂王幼虫进行了高通量测序，检测了所有带polyA端的转录本表达情况，对其中IncRNA的表达进行了分析，从而找出IncRNA在蜜蜂级型分化过程中的作用.

# 1材料与方法

# 1.1单雄受精蜂群构建

实验采用“浙农大1号”意大利蜜蜂(Apismellifera)，由浙江大学负责孵育和收集．为了尽可能减小遗传背景的影响，采用单雄受精的蜂群进行实验，这种蜂群中的蜂王通过人工受精，只接受一只雄蜂的精子，从而保证整个蜂群中所有后代均为同父同母.

# 1.2 幼虫培育

为了收集同步化的蜂王和工蜂幼虫，让蜂王在空的框架中 $2 4 \mathrm { h }$ 内完成产卵，然后，把这个框架转移到一个空的干净蜂箱中． $6 6 \mathrm { h }$ 后，转移150只蜜蜂幼虫到人造王台，同样将转移后的王台放回原来的蜂箱．在第4天(幼虫孵化后 $7 3 \sim 9 0 \mathrm { h } )$ ，第5天(幼虫孵化后 $9 7 \sim 1 1 4 ~ \mathrm { h } )$ ，第6天(幼虫孵化后$1 2 1 \sim 1 3 8 { \mathrm { ~ h } } )$ 分别将普通框架和王台中的工蜂和蜂王幼虫取出，放入液氮中保存直到使用.

# 1.3总RNA提取，文库构建和高通量测序 1.6上下游编码基因的分析

总 RNA用Trizol方法提取．取 ${ 5 } ~ { \mu \mathrm { g } }$ 总RNA用于构建文库．mRNA文库按照Illumina'smRNA-Seq8 samplekit说明构建，先将带poly-A端的RNA分离出来，然后打断成短片段，反转成DNA加接头后通过PCR扩增构建成文库．构建好的文库通过Illumina Hiseq2000 平台完成测序.

# 1.4RNA-seq数据分析

测序数据通过cufflinks流程计算FPKM来检测转录本的表达水平．首先通过Tophat2对测序所得的原始序列与蜜蜂的基因组文件进行比对，能够回帖到基因组的序列用cufflink进行拼接，将每个样品中拼接好的转录组整合成一份基因组注释文件，以此注释文件为基础，计算每个转录本的FPKM(fragments per kilobase per million)，得到的结果通过cuffnorm进行归一化处理，所得结果作为最终的基因表达值，用来进行统计分析.

# 1.5 同源IncRNA分析

将差异表达的lncRNA与Noncode数据库中人和小鼠的lncRNA序列进行Blast比对，筛选出其中e-value $< 1 \times 1 0 ^ { - 8 }$ ，bit score ${ > } 6 0$ 的匹配作为同源的lncRNA，根据人鼠中的lncRNA功能预测结果，对工蜂幼虫和蜂王幼虫中有表达差异的IncRNA进行了功能预测.

用closetbed检测差异表达的IncRNA上下游10k的编码基因，用“reciprocalbesthit”方法找到了蜜蜂在果蝇中的同源基因．对这些差异表达的lncRNA上下游基因在果蝇中的同源基因，通过普林斯顿大学 Lewis-Sigler Institute 的 Gene OntologyTools进行GO分析.

# 2结果与分析

# 2.1IncRNA的整体表达情况

最新的蜜蜂基因组(Amel4.5)中注释为lncRNA的共有3993个[16-17]，在我们的实验中，能够检测到的有565个．其中，蜂王幼虫在4日龄、5日龄、6日龄时可以检测到的lncRNA分别有427、378、336个，工蜂幼虫可以检测到的lncRNA分别有385、362、374个．分别对4日龄、5日龄、6日龄时工蜂和蜂王幼虫中能够检测到的lncRNA的表达进行对比(图1).

![](images/9834aa78da5ac17208d981406bc3a4a532f75becb34baaa2850382bcb5cd58a7.jpg)  
Fig.1Expression of IncRNA in the queen larvae and worker larvae   
(a)ComparisofexpresoedoereoedW4fokrQ4foeae.()of lncRNAexprswoafoeQfl.pf between queen and worker larvae on the 6th day,W6 for worker larvae,Q6 for queen larvae.

在4日龄、5日龄、6日龄时都能检测到的lncRNA 有154个(表1)．在这154个共同表达的lncRNA中，4日龄时，蜂王与工蜂幼虫中表达差异达到2倍以上的lncRNA有66个，5日龄时，蜂王与工蜂幼虫中表达差异达到2倍以上的lncRNA有84个，6日龄时，蜂王与工蜂幼虫中表达差异达到2倍以上的lncRNA有114个．在3天中的表达差异都达到2倍的有28个(图2).

Table 1The number of identified IncRNAs for all the samples   

<html><body><table><tr><td></td><td>Q4</td><td>Q5</td><td>Q6</td><td>W4</td><td>W5</td><td>W6</td><td>Share</td></tr><tr><td>IncRNA</td><td>427</td><td>378</td><td>336</td><td>385</td><td>362</td><td>374</td><td>154</td></tr><tr><td>Coding genes</td><td>11 274</td><td>10 629</td><td>10 450</td><td>11 034</td><td>10 615</td><td>10 249</td><td>9307</td></tr></table></body></html>

$^ * \mathrm { Q }$ for queen larvae,W for worker larvae,the number for age of the larvae

![](images/a712cbd7062de5983eb0c084d19a774a07e17bc8bf402295566623ccab2773ea.jpg)  
Fig.2Distribution of differentially expressed IncRNAs

我们对所有能够检测到表达的IncRNA的表达量进行了聚类分析，结果显示，4日龄时，工蜂和蜂王的差异最小，随着时间的变化，差异越来越大，6日龄时，表达差异达到最大，其中6日龄的工蜂与其他幼虫的差异最明显(图3).

# 2.2 IncRNA保守性分析

把蜜蜂中的lncRNA和noncode数据库[8中人和小鼠中已知的lncRNA进行比对，找到了蜜蜂中保守性相对比较高的546个lncRNA．这些相对保守的lncRNA在4日龄、5日龄、6日龄时表达差异达到2倍以上的分别有12、13、28个．对这些lncRNA在人和小鼠中可能的同源lncRNA的功能预测显示，4日龄时，IncRNA的功能主要分布在急相蛋白反应、生长调控、记忆等方面(图 4a).5日龄时，lncRNA的功能主要分布在信号转导、DNA为模板的转录调控、G蛋白偶联受体通路和记忆等方面(图 4b)．6日龄时，lncRNA的功能主要分布在RNA聚合酶Ⅱ转录、DNA为模板的转录和调控以及信号转导等方面(图 4c).

![](images/0def72fc224a51bd8a790ae8256f019095302925d46230e0d997269263011f04.jpg)

Fig.3Cluster of lncRNAs for all samples

![](images/b0c11d93ffeee1645ac06bef39cf87d82fe7cbf59a21e0a292b423af4fcd61bd.jpg)  
Fig.4Functional prediction of differentially expressed IncRNAs The $X$ axis is the number of IncRNA predicted to having the function of this GO term.

# 2.3上下游编码基因分析

我们对有表达差异的lncRNA上下游10k的编码基因进行了检测．4日龄、5日龄、6日龄时表达差异达到2倍的基因里，分别有46、55、79个可以在上下游10k内找到编码基因.

用“reciprocal best hit”方法[19-20]找到了蜜蜂在果蝇中所有的同源基因．对这些在差异IncRNA上下游10k范围内找到的基因，找出其在果蝇中的同源基因并进行了GO分析．GO的结果显示，这些基因大部分都是调控基因．在4日龄时，调控主要集中在多细胞组织发育、细胞分化、多细胞组织过程、神经系统发育等方面(图5a)．在5日龄时，调控主要集中在信号、RNA聚合酶Ⅱ转录、细胞交流、多细胞组织过程等方面(图5b)．在6日龄时，调控主要集中在神经系统发育、多细胞组织发育、转录调控等方面(图 5c).

# 2.4编码基因的表达情况

除了IncRNA，还检测了编码基因的表达水平．最新的蜜蜂基因组注释OGSv3.2中共有15314个编码基因[．我们的实验中共检测到了10 566个．其中，蜂王幼虫在4日龄、5日龄、6日龄时可以检测到的编码基因分别有10212、9855、9761个，工蜂幼虫在4日龄、5日龄、6日龄时可以检测到的编码基因分别有10092、9819、9555个．分别对4日龄、5日龄、6日龄时工蜂和蜂王幼虫中能够检测到的编码基因的表达进行了对比(图6).

(a) 4 Day (b) 5 Day -lg(P-value) -lg(P-value) 0 0.5 1.0 1.5 2.0 2.5 0 0.5 1.0 1.5 2.0 2.5 3.0 3.5 4.0 Regulation of multicellular organismal development Regulation of cellular process Regulation of cell differentiation Single organism signaling Regulation of multicellular organismal process Signaling Regulation of nervous system development Regulation of biological process Regulation of developmental process Regulation of signaling Regulation of transcription from RNA polymerase II Regulation of cellular process Cell communication Regulation of cellular macromolecule biosynthetic process Regulation of transcription from RNA polymerase II Regulation of macromolecule biosynthetic process Regulation of cell communication Transcription from RNA polymerase II promoter Regulation of multicellular organismal process Regulation of cellular biosynthetic process Transcription from RNA polymerase II promoter Regulation of biosynthetic process Transmembrane receptor protein serine/threonine...   
(c) 6 Day -lg(P-value) 0 0.51.01.52.0 2.53.03.54.04.5 Regulation of cellular process Regulation of nervous system development Regulationofbiological process Regulation of multicellular organismal development Biological regulation Regulation of developmental process Regulation of cell differentiation Regulation of multicellular organismal process Negativeregulation of signaling Negative regulation of cell communication Regulation of cell morphogenesis Single-organism cellular process Negative regulation of signal transduction Regulation of signaling Regulation of cell communication Central nervous system development

![](images/447739d1961b9c4ae5741817e3b80b7ebc3cb1bc03b5c373aa23cb83a4f6d550.jpg)  
Fig.5GO analysis of nearby coding genes of differentially expressed lncRNAs The $X$ axis is $- \mathrm { l g } ( P .$ -value).   
Fig.6Expression of coding genes in the queen larvae and worker larvae

(a)Comparisonofcodinggenesexpresionbetweenqueenandworkerlarvaeonthe4thdayW4forworkerlrvaeQ4forqueenlaae.(b) ComparisonofodggeeexpesitwdokereetdafookereQfole.sf coding genes expresionbetween queen and worker larvae on the 6th day,W6 for worker larvae,Q6 for queen larvae.

在4日龄、5日龄、6日龄时都能检测到的编码基因有8986个．在这些共同表达的编码基因中，4日龄时，蜂王与工蜂幼虫中表达差异达到2倍以上的编码基因有1083个，其中工蜂幼虫中表达高的有448个，蜂王幼虫中表达较高的有635个，5日龄时，蜂王与工蜂幼虫中表达差异达到2倍以上的编码基因有2871个，其中工蜂幼虫中表达高的有876个，蜂王幼虫中表达较高的有1995个，6日龄时，蜂王与工蜂幼虫中表达差异达到2倍以上的编码基因有6744个，其中工蜂幼虫中表达高的有1335个，蜂王幼虫中表达较高的有5409个(图7)．可以看到，随着分化的时间越久，工蜂和蜂王幼虫中有表达差异的编码基因数目越来越多．但是，蜂王幼虫中表达量较高的编码基因数目始终多于工蜂幼虫，这与之前的研究结果一致[2].

![](images/44cefb5917fdccaf4014e2cf441257fe0d87bcb47afbd5869bbae92a88cee81c.jpg)  
Fig.7The number of genes having higher expression in queen and worker larvae 1:Worker larvae；:Queen larvae.

# 3讨论

在近来的研究中，越来越多地发现LncRNA在各种生命活动中发挥着重要功能，包括生长发育[22-25]、表观遗传[2、癌症的发生发展[27-28]、干细胞分化[2]、免疫应答[30等．虽然这些大多都是在高等动物中所做的研究，但是越来越多的实验证明，不只在脊椎动物中，在无脊椎动物中，lncRNA同样也发挥了重要的生物学功能.

蜜蜂是常用的社会学和行为学模式生物，蜜蜂中的级型分化现象也被广泛地关注和研究．蜂王浆中的Royalactin被证实在蜜蜂的级型分化中起到了决定性作用[8，工蜂和蜂王幼虫发育中的重要基因和通路也有较多研究，我们之前的研究证实，miRNA在蜜蜂的级型分化中也起到了辅助调控的作用[9].

在本实验中，通过mRNA-seq方法，检测了工蜂和蜂王幼虫中所有带poly-A端的转录本的表达量．虽然 lncRNA 通常都带有poly-A，但是在我们的实验中，仅有565个可以检测到有表达，占已注释lncRNA的比例只有 $14 \%$ ，而能够检测到的mRNA占已注释mRNA的比例可以达到 $66 \%$ .我们另外的实验中发现，蜜蜂脑组织中有1196个lncRNA可以检测到有表达．对这两部分取并集发现，有335个lncRNA在两份数据中都可以检测到，推测这可能是由于IncRNA组织特异和时间特异的表达引起的.

我们检测了lncRNA上下游 $1 0 \mathbf { k }$ 以内编码基因的表达情况，4日龄、5日龄、6日龄时，有表达差异的编码基因自身在工蜂和蜂王幼虫中表达差异达到2倍的分别有11、23、45个，比例分别达到了 $23 . 9 1 \%$ 、 $41 . 8 2 \%$ 和 $56 . 9 6 \%$ (表2).

Table 2The expression of nearby genes ofdifferentially expressed IncRNAs   

<html><body><table><tr><td></td><td>4d</td><td>5d</td><td>6d</td></tr><tr><td>Differentially expressed lncRNAs</td><td>64</td><td>84</td><td>114</td></tr><tr><td>Nearby mRNAs</td><td>46</td><td>55</td><td>79</td></tr><tr><td>Differentially expressed mRNAs</td><td>11</td><td>23</td><td>45</td></tr><tr><td>Percent</td><td>23.91%</td><td>41.82%</td><td>56.96%</td></tr></table></body></html>

差异表达的IncRNA随着幼虫的发育而越来越多，聚类的结果与此一致．对这些差异表达的IncRNA进行了进一步分析．Noncode数据库[8]中收集了人和小鼠中已知的lncRNA并且对这些lncRNA进行了功能预测，我们把蜜蜂中差异表达的lncRNA与Noncode数据库中的lncRNA进行了比对，找到其中相对保守的lncRNA及其预测的功能．结果表明，在4日龄、5日龄、6日龄时，lncRNA始终在信号传导、记忆、生长调控、转录调控等方面发挥作用，在5日龄、6日龄时，还在多细胞组织发育、DNA修复、蛋白质修饰等方面发挥了作用.

很多时候，IncRNA都是通过调控上下游的编码基因来发挥作用的，所以我们对工蜂和蜂王幼虫中差异表达的IncRNA上下游10k的基因进行了分析．结果显示，绝大多数基因都是调控相关基因.调控主要发生在多细胞组织发育、神经系统发育、

RNA转录酶Ⅱ启动的转录等方面．而这些基因中有很多本身在工蜂和蜂王幼虫中就有显著的表达差异，因此推测，IncRNA很可能通过影响这些上下游基因的转录和功能执行来发挥调控作用.

我们系统性地研究了IncRNA在蜜蜂级型分化中的表达，找到了工蜂和蜂王幼虫发育早期差异表达的lncRNA，通过对这些差异表达的IncRNA的同源IncRNA和上下游编码基因的功能分析，我们认为，IncRNA的确参与了蜜蜂级型分化的过程，lncRNA很可能通过影响上下游基因的转录和功能执行方式在蜜蜂幼虫的多细胞组织发育、神经系统发育、转录调控的过程中起到了重要的调控作用.

# 参考文献

[1]Westeberhard MJ.Phenotypic plasticity and the origins of diversity. Annu Rev Ecol Syst,1989,20: 249-278   
[2]Patel N G,Haydak M H,Gochnauer T A.Electrophoretic components of the proteins in honeybee larval food.Nature,1960, 186(4725): 633-634   
[3]Hanes J, Simuth J.Identification and partial characterization of the major royal jelly protein of the honey-bee (Apis-Mellifera L). JApicult Res,1992,31(1): 22-26   
[4]Lercker G,CapellaP,Conte L S,et al. Components of royal jelly .1. identification of the organic-acids.Lipids,1981,16(12): 912-919   
[5]Lercker G,Capella P,Conte L S,et al. Components of royal jelly .2. the lipid fraction,hydrocarbons and sterols.JApicult Res,1982, 21(3): 178-184   
[6]Sesta G.Determination of sugars in royal jelly by HPLC. Apidologie,2006,37(1): 84-90   
[7]Lercker G,Savioli S,Vecchi M A，et al．Carbohydrate determination of royal jelly by high-resolution gas-chromatography (Hrgc).Food Chem,1986,19(4): 255-264   
[8]Kamakura M. Royalactin induces queen differentiationin honeybees. Nature,2011,473(7348): 478-483   
[9]Guo X,Su S,Skogerboe G,et al.Recipe for a busy bee: microRNAs in Honey Bee caste determination. PloS One,2013, 8(12): e81661   
[10] De Azevedo S V,Hartfelder K.The insulin signaling pathway in honey bee (Apis mellifera） caste development- differential expression of insulin-like peptides and insulin receptors in queen and worker larvae.Journal of Insect Physiology，2008,54 (6): 1064-1071   
[11]Wheeler D E,Buck N,Evans JD.Expression of insulin pathway genes during the period of caste determination in the honey bee, Apis mellifera.Insect Molecular Biology,2006,15(5): 597-602   
[12]Barchuk A R,Cristino A S,Kucharski R,et al．Molecular determinants of caste differentiation in the highly eusocial honeybee Apis mellifera.BMC Developmental Biology,2007,7   
[13] Evans JD,Wheeler D E.Differential gene expression between developing queens and workers in the honey bee,Apis mellfera. Proc Natl Acad Sci USA,1999,96(10): 5575-5580   
[14] Corona M,Estrada E，Zurita M. Diferential expression of mitochondrial genes between queens and workers during caste determination in the honeybee Apismellfera.Journal of Experimental Biology,1999,202(8): 929-938   
[15] Kormienko AE,Guenzl PM, Barlow DP,et al.Gene regulation by the act of long non-coding RNA transcription.Bmc Biol,2013, 11: 59   
[16] Munoz-Torres M C,ReeseJT, Childers C P,et al. Hymenoptera genome database: integrated community resources for insect species of the order Hymenoptera.Nucleic Acids Research,2011, 39(Database issue): D658-662   
[17] Weinstock G M,Robinson G E,Gibbs R A,et al.Insights into social insects from the genome of the honeybee Apis mellifera. Nature,2006,443(7114): 931-949   
[18] Xie CY,Yuan J,Li H,et al. NONCODEv4: exploring the world of long non-coding RNA genes. Nucleic Acids Research,2014, 42(D1): D98-D103   
[19] Hirsh AE,Fraser HB.Protein dispensability and rate of evolution. Nature,2001, 411(6841): 1046-1049   
[20] Cristino A S,Barchuk AR,Freitas FC,et al.Neuroligin-associated microRNA-932 targets actin and regulates memory in the honeybee.Nature Communications,2014,5:5529   
[21] Chen X,Hu Y,Zheng H Q,et al. Transcriptome comparison between honey bee queen- and worker-destined larvae. Insect Biochemistry and Molecular Biology,2012,42(9): 665-673   
[22] KlattenhoffC A, Scheuermann JC, Surface L E,et al. Braveheart, a long noncoding RNA requiredfor cardiovascular lineage commitment. Cell,2013,152(3): 570-583   
[23] Sauvageau M, GoffL A,Lodato S,et al.Multiple knockout mouse modelsreveal lincRNAsare required for lifeand brain development. Elife,2013,2: e01749   
[24] Hu G Q,Tang Q S, Sharma S,et al. Expression and regulation of intergenic long noncoding RNAs during T cell development and differentiation. Nat Immunol,2013,14(11):1190-U1118   
[25] Hu W Q,Yuan B B,Flygare J,et al.Long noncoding RNAmediated anti-apoptotic activity in murine erythroid terminal differentiation. Gene Dev,2011,25(24): 2573-2578   
[26] Bonasio R,Shiekhattar R.Regulation of transcription by long noncoding RNAs.Annu Rev Genet,2014,48: 433-455   
[27] Li JG,Chen ZL,Tian L Q,et al.LncRNA profile study reveals a three-lncRNA signature associated with the survival of patients with oesophageal squamous cell carcinoma.Gut,2014,63(11): 1700-1710   
[28] Tseng YY,Moriarity B S,Gong WM,et al.PVT1 dependence in cancer with MYC copy-number increase. Nature,2014, 512(7512): 82-86   
[29] Lin N W,Chang KY,Li Z H,etdl. An evolutionarilyconserved long noncoding RNA TUNA controls pluripotency and neural lineage commitment.Mol Cell,2014,53(6): 1067-1067   
[30] Carpenter S,Aiello D,Atianand M K,et al.A long noncoding RNA mediates both activation and repression of immune response genes. Science,2013,341(6147): 789-792

# The Function of lncRNAs in The Caste Determination of The Honeybee\*

GUO Yu $1 , 5 ) ^ { * }$ \*, SU Song-Kun $2 ) ^ { \ast \ast }$ , CHEN Sheng-Lu $^ { 3 ) ^ { \ast \ast } }$ \*, ZHANG Shao-Wu $1 , 2 , 4 ) ^ { * * * }$ , CHEN Run-Shengl\*\*\*

（ $^ { 1 ) }$ CASKeyLaboratoryofRNA BiologyInstituteof Biophysics,ChineseAcademyofSciences,Beijingl0o01,China; （2 $^ { 2 ) }$ College of Bee Science,FujianAgriculture andForestry University,Fuzhou 35oo02,China; （20 $^ { 3 ) }$ College of Animal Sciences,Zhejiang University, Hangzhou 310o58,China; （204号 $^ { 4 ) }$ ResearchSchoolofBilogy,Colegeofedicine,BilogyandEnvironment,TheAustralianNtionalUnivesityAustralia; （20 $^ { 5 ) }$ University of Chinese Academy of Sciences, Beijing l0o049,China)

AbstractCaste determination in the honeybeehas been demonstrated to be decided bythe royalactin in the royal jelly.And the differentially expressed coding genes in caste determination of the worker and queen larvae have also been wellstudied. Our experiments identified that IncRNAs are also differentially expressed in the caste determination of the larvae，which indicates that lncRNAs are involved in the caste determination.Detailed analysis showed that in the early development of the larvae,lncRNAs play a regulatory role in multicellular organismal development, nervous system development and regulation of transcription by afecting the expression and function of the nearby coding genes.

Key wordshoneybee, caste determination, lncRNA DOI: 10.16476/j.pibb.2015.0110