# 锥（Castanopsischinensis）低磷胁迫响应基因的功能及代谢

# 通路分析

姜 楚²，李文琪1,²，曹洪麟¹，刘 卫1\*(1.中国科学院华南植物园，广州 510650；2.中国科学院大学，北京 100049)

摘要：磷是限制南亚热带常绿阔叶林植物生长的关键营养元素，研究森林群落中优势木本植物对低磷胁迫响应的内在分子机制具有重要意义。该研究以鼎湖山20ha固定监测样地常绿阔叶林中优势种锥（Castanopsischinensis）为研究对象，利用高通量测序技术结合生物信息学软件对锥基因组序列进行深入分析，完成锥基因组参考序列的草图拼接，并结合大样地土壤有效磷数据，共筛选出37个显著性磷响应基因。对筛选出的锥磷响应基因进行GO 功能注释分析，结果发现30个GO注释分类中属分子功能类的基因数最多，共有13条，所涉及的预测功能包括磷脂酶D活性、细胞色素c氧化酶活性、光电子传递、过氧化物酶活性等。对锥磷响应基因进行KEGG 富集分析，结果显示，显著性富集的1条代谢通路为psbD基因参与调控的植物光合代谢途径。该研究表明，在锥生长期中，有众多基因与磷代谢相关，并参与调控多种生物途径。其中psbD基因作为锥叶片主要的磷响应基因可通过调控光合作用来调节植物生长，但其功能有待今后进一步验证。

关键词：锥，低磷胁迫，磷响应基因，基因功能，代谢通路中图分类号：Q943 文献标识码：A

# Analysis of function and metabolic pathway of phosphorus-responsive genes of Castanopsis chinensis under

# low phosphorus stress

JIANG Chu1,²,LI Wenqi1,², CAO Honglin1,LIU Wei1\* (1. South China Botanical Garden, Chinese Academy of Sciences, Guangzhou 510650, China; 2. University of Chinese Academy of Sciences,Beijing 1Ooo49, China )

Abstract: Phosphorus is the key limiting factor for the plant growth and production in subtropical evergreen broadleaved forest. It is of great significance to study on the molecular mechanism of dominant species response to low phosphorus stress in the forest community. Castanopsis chinensis Hance. is the dominant species in $2 0 \mathrm { h m } ^ { 2 }$ lower subtropical evergreen broadleaved forest plot in Dinghushan and plays very important role in forest community assembly and maintenance ofbiodiversity. In thisstudy， high-throughput sequencing technology combined with bioinformatics softwares were used to deep analyze the genome sequence of Castanopsis chinensis. Sequencing quality was assessed by FastQC and demutiplexed by Stacks. The assembly of reference sequence of Castanopsis chinensis genome was preliminarily completed by dDocent and the fasta format file of genomic reference sequence totally contained 1488 contig sequences including forward strand and reverse strand. Sequencing alignment was conducted by Bowtie2 and the individual sequence information was completely aligned to reference sequence. Pearson correlation analysis was performed using the data of soil available phosphorus content in Dinghushan plot with the result of sequence alignment matrix and the result showed that 37 significant phosphorus-responsive genes were detected. The GO function annotation analysis of the phosphorus-responsive genes found that among the $3 0 ~ \mathrm { G O }$ annotation classifications,there were 13 genes in the molecular functional class and the predicting functions included NAPE-specific phospholipase D activity, RNA binding, cytochrome-c oxidase activity, electron transporter and peroxidase activity.The predicting function of 11 genes in the class of biological process class involved in RNA splicing，oxidative phosphorylation， photosynthetic electron transport in photosystem II. Cellular component class contained 9 genes, including chloroplast, integral component of membrane and photosystem II. Moreover, the result of KEGG analysis showed that the KEGG terms of 37 genes were significantly enriched to the metabolic pathway of photosynthesis and psbD was the major gene participated in the regulatory process. This study reveals that many phosphorus-responsive genes are involved in the regulation of various biological pathways in the growth stage of Castanopsis chinensis under low phosphorus stress. psbD gene is a major phosphorus-responsive gene adjusting plant growth by regulating photosynthesis in leaves.The specific function of psbD gene in Castanopsis chinensis needs to be further vertified.

Key words: Castanopsis chinensis, low phosphorus stress， phosphorus-reponsive genes， gene function, metabolic pathway

磷（Phosphorus,P）是植物生命活动所必需的大量营养元素，是核酸及磷脂的重要结构组成部分，参与多种酶的激活（Lambers etal.,2006)。无机磷酸盐（Pi）作为P可以被植物体直接吸收的主要生物利用形式，在大多数自然及农业生态系统中，其有效性成为限制植物生长、发育及产量的重要因素（Zhaoetal.,2018)。为适应外部低磷环境，植物已形成了一系列表型、生理生化、代谢及分子响应机制，促进植物对有效磷的吸收及重分配（李键等，2013)。植物对低磷胁迫的遗传学响应机制，主要是通过DNA序列的特异性变化和诱导体内某些沉默基因的表达，使植物形态和生理上产生适应性的变化，从而提高植物对土壤难溶态磷的活化及利用效率（马祥庆等，2004)。

目前，针对植物响应低磷的相关报道多限于模式草本植物及农作物，对森林木本植物的相关研究较少（于娇妲，2017)。Fan etal.（2016）利用MALDI-TOF/TOFMS方法对磷胁迫高耐受性的马尾松优良品系进行质谱分析，鉴定出的98种差异表达蛋白涉及光合作用、生物合成、能量代谢、次级代谢、信号转导等生物途径。Netzer etal.（2018）对土壤磷充足和磷受限的两类欧洲温带山毛榉森林生态系统中的全年山毛榉枝条组织进行极性代谢组和脂质组分析，发现植物通过自身调控不同代谢物在体内的分布以适应不同磷浓度和不同季节下的生长需求，涉及的代谢通路和机制极为复杂。因此，利用分子生物学方法可以为森林群落中木本植物对环境的适应性进化机制研究提供新的途径。

鼎湖山 $2 0 \mathrm { { h a } }$ 固定监测样地（以下简称鼎湖山大样地）位于广东省肇庆市鼎湖山国家自然保护区 $( 1 1 2 ^ { \circ } 3 0 ^ { \prime } 3 9 ^ { \prime \prime } - 1 1 2 ^ { \circ } 3 3 ^ { \prime } 4 1 ^ { \prime \prime } \mathrm { ~ F ~ }$ -， $2 3 ^ { \circ } 0 9 ^ { \prime } 2 1 ^ { \prime \prime } - 2 3 ^ { \circ } 1 1 ^ { \prime } 3 0 ^ { \prime \prime } \mathrm { N } )$ 的核心区内，海拔 $2 3 0 { \sim } 4 7 0 \mathrm { m }$ 坡度 $3 0 ^ { \circ } { \sim } 5 0 ^ { \circ }$ ，地形起伏较大（叶万辉等，2008)。鼎湖山大样地属南亚热带季风气候，年平均温度为 $2 0 . 9 ^ { \circ } \mathrm { C }$ ，年平均降雨量为 $1 9 2 7 \mathrm { m m }$ ，其中4至9月为雨季，月降雨量均高于200mm；11月至翌年1月为旱季，月降雨量少于 $1 0 0 \mathrm { m m }$ 。该区地带性土壤类型以赤红壤为主，山地垂直分布有黄壤及山地灌丛草甸土；地带性植被类型为典型的南亚热带常绿阔叶林，保存较为完好（王峥峰等，2000；叶万辉等，2008）。叶片 ${ \bf \cal N } : { \bf \cal P }$ 反映了土壤氮磷的相对有效性，当N： $\mathrm { P } { > } 1 6$ 时，则表现为P限制（刘兴诏等，2010)。由于地处南亚热带地区，鼎湖山大样地受高温多雨的气候条件影响，土壤风化和土壤P流失状况严重，造成该地区土壤P缺乏(邵宜晶等，2017)导致该地区叶片 ${ \bf \cal N } : { \bf \cal P }$ 普遍高于20,证明存在低P限制(Hedin,2004）。此外，莫江明等（2000）通过研究鼎湖山南亚热带常绿阔叶林中植物营养元素含量的分配格局，发现磷对南亚热带常绿阔叶林植物生产力起最主要的限制作用。

锥（Castanopsischinensis)，壳斗科锥属，常绿阔叶乔木。雌雄同株，风媒传粉，根据鼎湖山站的物候记录，鼎湖山锥的花期为3-4月，果期为5-11月。锥在鼎湖山大样地中的重要值排位第一，是森林生态系统中的重要建群种，对群落构建及生物多样性维持具有重要意义（叶万辉等，2008)。目前对锥的研究主要集中在种子萌发与扩散（杨期和等，2005；杜彦君等，2006）、种群动态（彭少麟等，1995；张咏梅等，2003）及遗传分化（王峥峰等，2001；刘孟等，2017）等方面，研究地点多集中于鼎湖山，但对其受环境胁迫因子影响下的分子响应机制研究仍较为缺乏。该研究利用高通量测序技术结合生物信息学分析手段，为锥自制遗传模板序列，并探寻其对土壤限制性因子磷的响应基因和这些基因所涉及的生物学功能以及参与的代谢途径，以期为群落生态学中受环境影响产生的分子进化机制提供理论依据。

# 1材料与方法

# 1.1DNA提取与F-MSAP实验

样品采自鼎湖山大样地，共采集381个锥个体样品，每个体取不同部位新鲜叶片，利用改良的CTAB 法进行 DNA 提取。利用 Hap ⅡI、MspⅠ与EcoRI对基因组 DNA 进行双酶切；再将酶切产物连上接头，设计并筛选引物进行预扩增，利用荧光标记的引物进行选择性扩增。该实验参考刘孟（2016）的锥F-MSAP 扩增优化体系。在EcoRI、Hpa II/MspI通用引物的基础上（Xiong etal.,1999)，在引物前后随机添加若干碱基，组合成不同引物，对用于选择性扩增引物进行筛选，通过聚丙烯酰胺凝胶电泳共筛选出6对符合实验条件的引物对，用于选择性扩增（表1)：E3/H-M2、E5/H-M2、E6/H-M1、E8/H-M1、E8/H-M5、E9/H-M2。扩增产物送至广州艾基生物技术有限公司利用HiSeq2500平台进行高通量测序。

表1F-MSAP接头和引物序列Table1 Adapters and primers sequences of F-MSAP  

<html><body><table><tr><td></td><td>名称 Name</td><td>序列(5'-3')Sequence(5'-3')</td></tr><tr><td rowspan="4">接头 Adapters</td><td>EcoRI-adapter I</td><td>CTCGTAGACTGCGTACC</td></tr><tr><td>EcoR I-adapter II</td><td>AATTGGTACGCAGTCTAC</td></tr><tr><td>Hap II/Msp I-adapter I</td><td>GATCATGAGTCCTGCT</td></tr><tr><td>Hap II/Msp I-adapter II</td><td>CGAGCAGGACTCATGA</td></tr><tr><td>预扩增引物</td><td>EcoRI+A</td><td>GACTGCGTACCAATTCA</td></tr></table></body></html>

<html><body><table><tr><td>Pre-amplification primers</td><td>Hap II/Msp I+T</td><td>ATCATGAGTCCTGCTCGGT</td></tr><tr><td>选择性扩增引物</td><td>E3(E+AG)</td><td>GACTGCGTACCAATTCAAG</td></tr><tr><td>Selective-amplification primers</td><td>E5(E+CA)</td><td>GACTGCGTACCAATTCACA</td></tr><tr><td></td><td>E6(E+CC)</td><td>GACTGCGTACCAATTCACC</td></tr><tr><td></td><td>E8(E+CT)</td><td>GACTGCGTACCAATTCACT</td></tr><tr><td></td><td>E9(E+GA)</td><td>GACTGCGTACCAATTCAGA</td></tr><tr><td></td><td>H-M1(H-M+AA) FAM</td><td>ATCATGAGTCCTGCTCGGTAA</td></tr><tr><td></td><td>H-M2(H-M+AC)FAM</td><td>ATCATGAGTCCTGCTCGGTAC</td></tr><tr><td></td><td>H-M5(H-M+CA) FAM</td><td>ATCATGAGTCCTGCTCGGTCA</td></tr></table></body></html>

# 1.2环境数据信息

该研究中土壤环境及物种信息均来自鼎湖山大样地的长期监测数据。研究对象锥所在小样方的土壤理化性质、地形因子来源于2005年样方建立时测量的数据，该研究分析使用的土壤有效磷数据（ap,mg·kg-1）经过 2014 年最新的土样分析校正（Chen etal.,2015）。

# 1.3数据处理

(1）利用 FastQC 0.11.7 软件（http://www.bioinformatics.babraham.ac.uk/ projects/fastqc/)对测序后得到的原始数据进行质量检验，通过FASTX_Toolkit软件（http://hannonlab.cshl.edu/fastx_toolkit/）去除低质量及重复序列，去低质量的reads，使用fastq_quality_filter命令，设置最小质量阈值（Minimum Quality Threshold）为33，最小长度（MinimumLength）为80；去除重复序列，使用fastx_collapser命令，默认参数;

（2）对质控后所得的序列利用 Stacks 软件（http://catchenlab.life.ilinois.edu/stacks/）中的process_radtags命令根据barcode序列进行样本拆分，再利用dDocent软件（http://ddocent.com/assembly/）进行序列拼接;

（3）利用Bowtie2软件，将个体序列信息比对到拼接的模板序列上(http://bowtie-bio.sourceforge.net/bowtie2/index.shtml);

（4）环境因子与个体基因序列的相关性，利用 SPSS19.0 软件进行 Person 相关分析，筛选显著相关基因（ $_ { . } { P } { < } 0 . 0 5 )$ ：

（5）利用R3.4.2对所得基因利用已有模式植物拟南芥基因注释信息数据库进行比对，完成GO功能注释及KEGG代谢通路富集分析。

# 2结果

# 2.1模板序列拼接

原始测序数据经过质量过滤及样本拆分后，通过序列拼接软件操作，得到锥模板参考序列reference.fasta文件，共包含1488 条contig序列（包括正反互补链）。

# 2.2序列比对及环境关联分析

根据 2005 年鼎湖山大样地土壤环境数据，能够对应序列信息的锥个体共有377个。共筛选出37条与ap显著相关（ $\scriptstyle \cdot { P < 0 . 0 5 }$ ）的基因序列。

# 2.3功能注释及GO富集分析

经过基因功能注释以及GO 富集分析，在锥的30个GO 注释分类中（表2，图1)，归类于分子功能（molecular function，MF）的基因最多，共有13条，涉及磷脂酶D活性、RNA结合活性、钙离子结合活性、细胞色素c氧化酶活性、载流子活性、光电子转运活性、血红素结合活性、过氧化物酶活性等功能；归类于生物学过程（biological process，BP）的基因共有11条，涉及RNA 剪接、有氧呼吸、电子传递链、脂质代谢、mRNA 加工、氧化还原过程、氧化磷酸化、磷脂酰胆碱代谢、光系统II中光电子传递过程、抗氧化反应、tRNA 加工；归类于细胞成分（celllar component，CC）的基因共有9条，包括叶绿体、细胞膜、线粒体内膜、光系统Ⅱ、细胞壁、呼吸链等组分。

表2磷响应基因的功能分类  
Table 2 Functional classification of phosphorus-responsive genes   

<html><body><table><tr><td>GO 注释的功能分类 GO_function</td><td>GO 登录号 GO accession NO.</td><td>Unigene 数目 Unigene number</td><td>Unigene编号 Unigene ID</td></tr><tr><td>生物学过程（Biological process）</td><td></td><td>11</td><td></td></tr><tr><td>RNA剪接</td><td>GO:0008380</td><td>1</td><td>c650</td></tr><tr><td>RNA splicing 有氧呼吸</td><td>GO:0009060</td><td>1</td><td>c525</td></tr><tr><td>Aerobic respiration 电子传递链</td><td></td><td></td><td></td></tr><tr><td>Electron transport chain</td><td>GO:0022900</td><td>1</td><td>c525</td></tr><tr><td>脂质代谢过程 Lipid catabolic process</td><td>GO:0016042</td><td>1</td><td>c310</td></tr><tr><td>mRNA 加工</td><td>GO:0006397</td><td>1</td><td>c650</td></tr><tr><td>mRNA processing 氧化还原过程</td><td>GO:0055114</td><td></td><td></td></tr><tr><td>Oxidation-reduction process</td><td></td><td>1</td><td>c446</td></tr><tr><td>氧化磷酸化</td><td>GO:0006119</td><td>1</td><td>c525</td></tr><tr><td>Oxidative phosphorylation 磷脂酰胆碱代谢</td><td></td><td></td><td></td></tr><tr><td>Phosphatidylcholine metabolic process</td><td>GO:0046470</td><td>1</td><td>c310</td></tr><tr><td>光系统Ⅱ中光电子传递过程</td><td>GO:0009772</td><td></td><td></td></tr><tr><td>Photosynthetic electron transport in photosystem II</td><td></td><td>1</td><td>c31</td></tr><tr><td>抗氧化反应</td><td>GO:0006979</td><td>1</td><td>c446</td></tr><tr><td>Response to oxidative stress</td><td></td><td></td><td></td></tr><tr><td>tRNA加工</td><td>GO:0008033</td><td>1</td><td>c650</td></tr><tr><td>tRNA Processing</td><td></td><td></td><td></td></tr><tr><td>细胞成分（Cellularcomponent）</td><td></td><td>9</td><td></td></tr><tr><td>叶绿体</td><td>GO:0009507</td><td>2</td><td>c650;c31</td></tr><tr><td>Chloroplast</td><td></td><td></td><td></td></tr><tr><td>细胞膜完整成分</td><td>GO:0016021</td><td>2</td><td>c31;c525</td></tr><tr><td>Integral component of membrane</td><td></td><td></td><td></td></tr><tr><td>细胞膜</td><td>GO:0016020</td><td></td><td>c310</td></tr><tr><td>Membrane</td><td></td><td>1</td><td></td></tr><tr><td>线粒体内膜</td><td>GO:0005743</td><td></td><td></td></tr><tr><td></td><td></td><td>1</td><td>c525</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>光系统Ⅱ</td><td>GO:0009523</td><td>1</td><td>c31</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>Mitochondrial inner membrane</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>

# Photosystem II

<html><body><table><tr><td>植物型细胞壁</td><td>GO:0009505</td><td>1</td><td>c446</td></tr><tr><td>Plant-type cell wall</td><td></td><td></td><td></td></tr><tr><td>呼吸链</td><td>GO:0070469</td><td>1</td><td>c525</td></tr><tr><td>Respiratory chain</td><td></td><td></td><td></td></tr><tr><td>分子功能（Molecular function）</td><td></td><td>13</td><td></td></tr><tr><td>NAPE-特异性磷脂酶D活性</td><td>GO:0070290</td><td>1</td><td>c310</td></tr><tr><td>NAPE-specific phospholipase D activity</td><td></td><td></td><td></td></tr><tr><td>RNA结合</td><td>GO:0003723</td><td>1</td><td></td></tr><tr><td>RNA binding</td><td></td><td></td><td></td></tr><tr><td>钙离子结合</td><td>GO:0005509</td><td>1</td><td>c310</td></tr><tr><td>Calcium ion binding</td><td></td><td></td><td></td></tr><tr><td>细胞色素c氧化活性</td><td>GO:0004129</td><td>1</td><td>c525</td></tr><tr><td>Cytochrome-c oxidase activity</td><td></td><td></td><td></td></tr><tr><td>载流子活性</td><td>GO:0009055</td><td>1</td><td>c525</td></tr><tr><td>Electron carrier activity</td><td></td><td></td><td></td></tr><tr><td>电子传递</td><td>GO:0045156</td><td>1</td><td>c31</td></tr><tr><td>Electron transporter</td><td></td><td></td><td></td></tr><tr><td>血红素结合</td><td>GO:0020037</td><td>2</td><td>c446;c525</td></tr><tr><td>Heme binding</td><td></td><td></td><td></td></tr><tr><td>铁离子结合</td><td>GO:0005506</td><td>1</td><td>c525</td></tr><tr><td>Iron ion binding</td><td></td><td></td><td></td></tr><tr><td>金属离子结合</td><td>GO:0046872</td><td>2</td><td>c446;c31</td></tr><tr><td>Metal ion binding</td><td></td><td></td><td></td></tr><tr><td>过氧化物酶活性</td><td>GO:0004601</td><td></td><td></td></tr><tr><td>Peroxidase activity</td><td></td><td>1</td><td>c446</td></tr><tr><td>磷脂酶D活性</td><td>GO:0004630</td><td></td><td></td></tr><tr><td>Phospholipase D activity</td><td></td><td>1</td><td>c310</td></tr></table></body></html>

![](images/5e822e06c42fdf98825ffb4736137fd01218cefafb04090b0bf09ede9e30db81.jpg)

注：图中1-7.细胞成分1.细胞；2.细胞组分；3.细胞膜；4.细胞器；5.细胞膜组分；6.大分子   
复合物；7.细胞器组分。8-12.分子功能8.结合；9.催化活性；10.载流子活性；11.运输活性； 12.抗氧化活性。13-17.生物学过程13.代谢过程；14.细胞过程；15.单有机体过程； 16.应激反应；17.定位。 Note:1-7. Cellular component1. Cell; 2. Cell part; 3.Membrane; 4. Organelle; 5.Membrane part;   
6. Macromolecular complex; 7. Organelle part. 8-12. Molecular function8.Binding; 9. Catalytic activity;

10.Electron carrier activity;11.Transporteractivity;12.Antioxidant activity.13-17.Biological process 13.Metabolic process; 14. Cellular process; 15. Single-organism process; 16. Response to stimulus; 17. Localization.

# 2.4KEGG代谢通路分析

利用超几何检验对KEGG中所有代谢通路进行富集分析，结果显示，仅有 $2 . 7 \%$ 的基因被注释到具体的代谢通路中，其中显著性富集的1条代谢通路（代谢通路ID：ko00195）为psbD基因参与调控的植物光合代谢途径，该基因编码光系统ⅡIP680反应中心D2蛋白（图2）。

![](images/145a8df2315b1eb24d6f2f77f40ff1f824adf359a595361c31e79e802ab56580.jpg)  
图1磷响应基因的GO 富集分析  
Fig.1 GO enrichment analysis of phosphorus-responsive genes   
图2磷响应基因参与的光合作用代谢通路图

Fig.2Phosphorus-responsive genes involved in the metabolic pathway of photosynthesis

# 3讨论与结论

植物对磷胁迫的分子响应机制涉及由大量基因及转录因子等参与的复杂的调控网络，在低磷胁迫下，植物通过调控基因表达来调节生长及代谢途径以促进对环境中有效磷的吸收及高效利用（Xuetal.,2018)。高通量测序技术的发展，能够为深入的植物基因序列分析提供数据支撑，对目前无参考基因组信息的物种尤为重要（贾新平等，2014)。基于此，对锥的基因组测序信息进行系统分析，用以探寻木本植物对低磷胁迫响应的关键基因及其调控机制。该研究首先利用高通量测序数据为锥拼接出参考序列，共包含1488条模板序列，并将 377个个体序列与模板序列的比对结果结合鼎湖山大样地土壤ap 数据进行相关性分析，筛选出37条显著相关基因。

光合作用与植物生长和生物量生产密切相关，植物的生长依赖于光合作用，磷是叶绿体的重要组成元素,Pi参与重要的Calvin循环过程,因此磷在光合作用中起关键作用(Gu et al,2017)。已有研究表明，光合作用对低磷胁迫敏感，许多参与光合作用的调控基因在受低磷胁迫时表达发生显著变化（Slattery etal.,2017)。研究发现，大豆中编码光合过程中重要化合物成分的四个关键基因PsbZ、PsbN、PsbH和PsbK在磷受限时表达下调，而NADP+依赖的苹果酸酶基因和两个丙酮酸激酶基因受低磷诱导表达上调（Chu etal.,2018)。该研究对已筛选出的ap 显著相关基因进一步进行了GO 功能注释分析及KEGG 富集分析，结果发现，锥的 30个GO注释分类中属分子功能类的基因最多，共有13条，所涉及的分子功能包括磷脂酶D活性、细胞色素c氧化酶活性、过氧化物酶活性等。而KEGG 富集分析结果显示，锥的磷响应基因显著性富集的1条代谢通路为psbD基因参与调控的植物光合作用。研究表明，植物叶绿体光系统Ⅱ是植物进行光能转化、水的裂解和释放氧气的重要蛋白复合物，psbD 基因编码光系统ⅡI作用中心D2蛋白，D2 和D1蛋白共同构成的异源二聚体上结合着大量与电子传递有关的色素分子及辅助因子（许冰清等，2015)。

植物对环境胁迫产生的适应性生长调节，主要通过相关基因参与调控。该研究结果表明，在南亚热带常绿阔叶林中，植物体吸收的有效磷主要分配给光合作用用于植物的生长发育，而在低磷胁迫下，植物能够调控相关的磷响应基因促进有效磷的吸收以及体内循环再分配过程，从而达到高效利用有限资源。而该研究使用的锥样品采集于生长季，植物体吸收的有效磷可能主要用于叶片生长，因此该研究结果也可能在一定程度上受到季节和实验条件的影响。目前，仅有极少数树种成功完成全基因组测序，木本植物因生长周期长、基因组庞大导致其分子生物学研究较滞后于草本植物（于娇妲等，2017)，而对于森林群落中一些优势树种而言，分子生物学研究的技术进步有助于深入阐明其受环境胁迫影响下发生的适应性进化的内在机制，对探索调控其生长发育的关键基因功能具有重要生理学意义。今后可基于该研究结果，对不同生长季参与调控的主要磷响应基因及对筛选出的显著基因的具体调控机制进行进一步探究。

# 参考文献：

CHEN J，RUI Y， ZHOU X，et al.，2015. Determinants of the biodiversity patterns of ammonia-oxidizing archaea community in two contrasting forest stands[J]. J Soils Sediments, 16: 878-888.   
CHU SS,LI HY, ZHANG XQ，et al.， 2O18.Physiological and Proteomics analyses reveal low-phosphorus stress affected the regulation of photosynthesis in soybean[J]. Internat J Molec Sci, 19(6):1688.   
DU YJ, PENG SJ, XU GL, et al.,2OO6. Analysis of death factors in the process of diffusion of Castanopsis chinensis in Dinghushan[J]. Ecol Environ,15(6):1284-1288.[杜彦君，彭闪江,徐 国良,等，2006．鼎湖山锥栗种子扩散过程中死亡因素分析[J].生态环境, 15(6):1284-1288.]   
FAN F, DING G, WEN X, 2016. Proteomic analyses provide new insights into the responses of Pinus massoniana seedlings to phosphorus deficiency[J]. Proteomics,16(3):504-515.   
GU JF, ZHOU ZX,LI ZK, et al., 2O17. Photosynthetic properties and potentials for improvement of photosynthesis in pale green leaf rice under high light conditions[J]. Frontiers Plant Sci, 8.   
HEDIN L,2O04. Global organization of terrestrial plant-nutrient interactions[J]. Proceed Natl Acad Sci, 101(30):10849-10850.   
JIA XP, SUN XB, DENG YM, et al., 2014. Sequencing and analysis of the transcriptome of Asplenium nidus[J]．Acta Hortic Sin，41(11):2329-2341.[贾新平，孙晓波，邓衍明，等, 2014．鸟巢蕨转录组高通量测序及分析[J]．园艺学报,41(11):2329-2341.]   
LAMBERS H, 2O06. Root structure and functioning for efficient acquisition of phosphorus: Matching morphological and physiological traits[J]. Ann Bot, 98(4):693-713.   
LI J,HUANG JH, HONG T, et al.,2013. Effects of low phosphorus stress on leaf physiological and biochemical characteristic of Tripterygium wilfordii Hook. f. seedlings[J]. Plant Sci J, 31(3):286-296.[李键，黄锦湖，洪滔，等，2013．低磷胁迫对雷公藤幼苗叶片生理生化特 性的影响[J]．植物科学学报,31(3):286-296.]   
LIU M, OUYANG XJ, CHEN J, et al., 2017. F-MSAP sampling strategy and genetic diversity analysis of Castanopsis chinensis in South China Botanical Garden[J]. Guihaia, 37(1):15-21. [刘孟，欧阳学军，陈洁，等，2017.华南植物园锥栗 F-MSAP 采样策略及遗传多样性分 析[J].广西植物,37(1):15-21.]   
LIU XZ, ZHOU GY, ZHANG DQ, et al., 2010. N and P stoichiometry of plant and soil in lower subtropical forest successional series in southern China[J]. Chin JPlant Ecol, 34(1):64-71.[刘 兴诏，周国逸，张德强，等,2010．南亚热带森林不同演替阶段植物与土壤中N、P 的化学 计量特征[J]．植物生态学报,34(1):64-71.]   
MA XQ,LIANG X, 2004. Research advances in mechanism of high phosphorus use efficiency of plants [J].ChinJAppl Ecol,15(4):712-716.[马祥庆，梁霞,2004．植物高效利用磷机制的 研究进展[J]．应用生态学报,15(4):712-716.]   
MO JM, ZHANG DQ,HUANG ZL, et al.， 2000. Distribution pattern of nutrient elements in plants of Dinghushan lower subtropical evergreen broadleaf forest[J]. Trop Subtrop Bot, 8(3): 198-206.[莫江明，张德强，黄忠良，等，2000．鼎湖山南亚热带常绿阔叶林植物营养元素 含量分配格局研究[J]．热带亚热带植物学报,8(3):198-206.]   
NETZER F, HERSCHBACH C，OIKAWA A，et al.，2018. Seasonal alterations in organic phosphorus metabolism drive the phosphorus economy of annual growth in $F .$ sylvatica trees on P-impoverished soil[J]. Frontiers Plant Sci, 9:723.   
PENG SL, FANG W, 1995. Dynamics of populations of Castanopsis chinensis and Schima superba in the process of vegetation succession in Dinghushan[J]. Chin J Plant Ecol, 19(4):311-318.[彭少麟，方炜，1995．鼎湖山植被演替过程中椎栗和荷木种群的动态[J]. 植物生态学报,19(4):311-318.]   
SHAO YJ, YU MX, JIANG J, et al., 2017. Status and Dynamic of soil C,N and P of three forest succession gradient in Dinghushan[J].J Trop Subtrop Bot,25(6):5-12.[邵宜晶，俞梦笑，江 军，等,2017．鼎湖山3 种演替阶段森林土壤C、N、P现状及动态[J]．热带亚热带植物学 报,25(6):5-12.]   
SLATTERY RA,VANLOOCKE A， BERNACCHI CJ,et al.， 2017. Photosynthesis，light use efficiency, and yield of reduced-chlorophyll soybean mutants in field conditions[J]. Frontiers Plant Sci, 8:549.   
WANG ZF, WANG BS,LI MG, et al.， 2000. Molecular ecology of lower subtropical species, Schima superba and Castanopsis chinensis in three succession series communities[J]. Acta Bot Sin，42(10):1082-1088.[王峥峰，王伯荪，李鸣光，等，2000．南亚热带森林优势种群荷木 和锥栗在演替系列群落中的分子生态研究[J]．植物学报,42(10):1082-1088.]   
WANG ZF, WANG BS,LI MG, et al.， 2001. Genetic differentiation of Castanopsis Chinensis population in three communities in Dinghu Mountain, China[J]. Acta Ecol Sin,21(8).[王峥峰, 王伯荪，李鸣光，等，2001．锥栗种群在鼎湖山三个群落中的遗传分化研究[J]．生态学报, 21(8).]   
XIONG LZ, XU CG, MAROOF MAS, et al., 1999. Patterns of cytosine methylation in an elite ricehybrid and its parental lines， detected by a methylation-sensitive amplification polymorphism technique[J]. Mol Gen Genet, 261(3):439-446.   
XU BQ,AN MM, JIANG KY, et al., 2015. Cloning and functional analysis of the psbD gene in Pseudosasa japonica f. akebonosuji[J]. J Zhejiang A & F Univ, 32(4):557-565.[许冰清，安苗 苗，姜可以，等,2015．花叶矢竹叶绿体psbD基因的克隆与功能分析[J]．浙江农林大学学 报,32(4):557-565.]   
XU C， ZHANG HW, SUN JH, et al.， 2018. Genome-wide association study dissects yield components associated with low-phosphorus stress tolerance in maize[J]. Theoret Appl Gene, 131(1):1-16.   
YANG QH, YE WH, ZHANG Y, et al., 2005. Eco-physiological characteristics of germination and storage of Castanopsis chinensis seeds[J].JBeijing For Univ,27(1):92-95.[杨期和，叶万辉, 张云，等，2005.锥栗种子萌发和贮藏特性的初步研究[J]．北京林业大学学报, 27(1):92-95.]   
YE WH, CAO HL, HUANG ZL, et al., 2008. Community structure of a $2 0 \mathrm { h m } ^ { 2 }$ lower subtropical evergreen broadleaved forest plot in Dinghushan, China[J]. JPlant Ecol, 32(2):274-286.[叶万 辉，曹洪麟，黄忠良，等,2008．鼎湖山南亚热带常绿阔叶林 20 公顷样地群落特征研究[J]. 植物生态学报,32(2):274-286.]   
YU JD, YIN DY, WU JM, et al., 2017. A Review of adaptation mechanism of trees under low phosphorus stressJ].World For Res,30(1).[于姣妲，殷丹阳，吴佳美，等,2017．林木低磷 胁迫适应机制研究进展[J]．世界林业研究,30(1).]   
ZHANG YM, ZHOU GY, WEN DZ, et al., 2003. Dynamics of the Castanopsis Chinensis-Schima superba-Cryptocarya concinna community of monsoon evergreen broadleaved forest in Dinghushan Nature Reserve in lower subtropical China[J]. Chin J Plant Ecol, 27(2):256-262. [张咏梅，周国逸，温达志，等，2003．南亚热带季风常绿阔叶林锥栗-荷木-黄果厚壳桂群 落发展趋势探讨[J]．植物生态学报,27(2):256-262.]   
ZHAO PS, WANG LR, YIN HX, 2018. Transcriptional responses to phosphate starvation in Brachypodium distachyon roots[J]. Plant Physiol Biochem, 122:113-120.