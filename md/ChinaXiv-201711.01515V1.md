应用Illumina-MiSeq高通量测序技术分析脱氧雪腐镰刀菌烯醇对小鼠肠道菌群的影响

# 杨俊花 赵志辉\* 郭文博 郭晋丽

（上海市农业科学院农产品质量标准与检测技术研究所，上海201403）

摘要：本试验旨在研究脱氧雪腐镰刀菌烯醇（DON）对小鼠肠道微生物多样性、物种丰度的影响。选用平均体重为 $2 0 \ \mathrm { g }$ 的BALB/c小鼠40只，随机分成对照组（灌胃灭菌生理盐水）和DON组（灌胃1.8 mg/kgBWDON），每组20个重复，每个重复1只小鼠，连续灌服28 d。试验结束后，收集新鲜粪便，每组随机选取3份，用Ilumina-MiSeq高通量测序技术分析微生物群落结构和组成的变化。结果表明，1）与对照组相比，DON组测序数量减少（ $P$ 大于号0.05）。2)DON组降低了Alpha、Beta多样性，Shannon指数较对照组显著降低（P小于号0.05）。3）在门水平，与对照组相比，DON组显著降低了Bacteroidetes和Deferribacteres的物种丰度（P小于号0.05），显著提高了Proteobacteria的物种丰度（P小于号0.05）。在属水平，与对照组相比，DON组显著降低了Parabacteroides、Rikenella、Algoriphagus、Mucispirillum、Methylophilus、Francisella的物种丰度（P小于号o.05），显著提高了Clostridium、Robinsoniella、Allobaculum、Akkermansia的物种丰度（ $P$ 小于号0.05）。4）聚类分析显示，DON组与对照组的肠道微生物相似性降低。由此可见，DON能显著影响小鼠肠道微生物菌群多样性及物种丰度，提示DON致肠道损伤与这些肠道菌群的变化密切相关。

关键词：高通量测序；脱氧雪腐镰刀菌烯醇；肠道微生物

中图分类号：S811.6

脱氧雪腐镰刀菌烯醇（deoxynivalenol,DON）是由禾谷镰刀菌（Fusarium graminearum，

Fusariumculmorum)等在适宜的温度和湿度条件下产生的次级代谢产物[1],主要存在以小麦、玉米为基础的食物和饲料中[2]。研究指出，DON毒性虽低于其他真菌毒素，但由于污染普遍、含量高，对人畜具有非常高的危害性[3]。误食极易引起厌食、呕吐、腹痛、腹泻、发烧、站立不稳和反应迟钝等症状，长期暴露易导致肠道功能紊乱、生长缓慢、免疫和神经系统损伤、休克死亡等[4-5]，给畜牧业造成巨大经济损失。

肠道作为机体与外界物质接触的第一道屏障，不仅可以阻止异型生物质如饲料蛋白质、天然毒素、微生物以及真菌毒素等的入侵，同时也极易成为外源性物质的攻击靶标。近年来，许多研究都集中在DON对肠道功能的影响，发现DON可损伤肠道黏膜、破坏肠道屏障和细胞紧密连接、引起肠道炎症、降低肠道免疫应答、阻碍营养物质吸收等[6-7]。

肠道菌群作为肠道重要的组成部分，被誉为是机体自身的黑匣子，其一切的生命活动和代谢情况，如屏障功能、营养作用、免疫应答等都与健康密切相关[8]。然而，目前DON对肠道微生物的影响国内外研究鲜有报道。体外试验表明，DON不影响金黄色葡萄球菌、大肠杆菌和结肠炎耶尔森杆菌的生长，只对链球菌有抑制作用[9]。Waché等[10]研究表明，给猪饲喂DON污染的饲粮可增加厌氧菌的数量，降低厌氧性亚硫酸盐还原菌的数量；Saint-Cyr等[1]研究发现，小鼠灌胃DON可显著降低粪便中大肠杆菌的数量。但这些研究主要基于体外培养法、毛细管电泳-单链构象多态性（CE-SSCP）法和荧光定量PCR法，并不能充分反映DON对肠道菌群的作用，只局限于一定丰度细菌或特定微生物，对未知微生物均未涉及。因此，本研究选择高通量数据、高检测深度和高准确率的宏基因组测序技术，结合生物信息学分析技术，旨在定性、定量地研究DON对小鼠肠道结构组成、菌群多样性和丰度等各方面的影响，探索DON致肠道炎症、损伤以及营养物质吸收障碍的作用机制，筛选肠道暴露DON的敏感菌群和微生物标志物，为饲料中真菌毒素污染安全评价探索新的路径和方法。

# 1材料与方法

# 1.1 试验材料与仪器

DON标准品：粉末状，纯度 $2 9 9 \%$ （Pribolab，Singapore），购自北京普华仁生物技术开发有限公司，以高压灭菌水稀释。粪便DNA提取试剂盒、 $2 \times$ Taq PCRMasterMix购自天根生化科技(北京)有限公司。

主要仪器：Illumina-MiSeq DNA测序仪（Ilumina，美国）、紫外分光光度计（Shimadzu，日本）、Sorvall高速离心机（Thermo，美国）、PCR仪（Bio-Red，美国）、凝胶成像系统（Bio-Red，美国）。

# 1.2 试验动物与饲养管理

BALB/c小鼠40只，6周龄，体重 $1 8 \sim 2 2 { \mathrm { g } }$ ，无特定病原体（SPF）级，购自复旦大学实验动物科学部。室温维持（ $2 3 { \pm } 2$ ） $\mathrm { { } ^ { \circ } C }$ ，相对湿度为 $4 0 \% \sim 7 0 \%$ ，光照周期 $1 2 \mathrm { { h } }$ ，自由饮水和采食，提供高压灭菌蒸馏水和经 $1 . 5 { \sim } 2 . 5$ Mrad钴-60照射除菌的饲料，预饲喂1周。

# 1.3 试验方法

# 1.3.1 试验设计

将40只小鼠随机分成2组，每组20个重复，每个重复1只小鼠，分笼饲养在无菌隔离器中。分为对照组（灌胃灭菌生理盐水）和DON组（灌胃1.8mg/kgBWDON），试验剂量设计参考DON对BALB/c小鼠的急性、亚急性毒性结果[15]，每只小鼠每天每次灌胃 $0 . 2 \mathrm { m L }$ ，试验持续28 d。

# 1.3.2 样品采集

试验结束后，固定小鼠，将其尾部提起，用手指轻轻按压小鼠下腹部，采集新鲜粪便后置于 $1 . 5 ~ \mathrm { m L }$ 高压灭菌离心管中， $- 8 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 超低温冰箱保存。

# 1.3.3 粪便DNA的提取及质量检测

每组分别选取3份粪便样品，每份准确称取 $0 . 2 \ \mathrm { g }$ 置于 $2 { \mathrm { m L } }$ 离心管中，采用粪便DNA提取试剂盒提取盲肠内容物DNA，紫外分光光度计测定DNA 浓度， $0 . 8 \%$ 琼脂糖凝胶电泳检测纯度，后将DNA样品送上海派生诺生物科技股份有限公司测序分析。

# 1.3.4Illumina-MiSeq 宏基因组测序

# 1.3.4.1 16SrDNAV4区PCR反应

根据16SrDNA基因的V4区保守序列设计通用引物：上游引物为5'-AYTGGGYDTAAAGNG-3'，下游引物为5'-TACNVGGGTATCTAATCC-3'。为区分每个不同的样本，在通用引物的上游序列前随机添加7个核苷酸碱基的序列标签，即Barcoded-tag，形成Barcoded融合引物。PCR反应体系为：Loading Buffer ( $\mathrm { 1 0 \times ) }$ 2.5 μL，dNTP $2 \mu \mathrm { L }$ ，DNA模板 $1 ~ \mu \mathrm { L }$ ，上游引物 $1 ~ \mu \mathrm { L }$ ，下游引物 $1 ~ \mu \mathrm { L }$ ，DNA合成酶 $0 . 1 2 5 { \mu \mathrm { L } }$ ， $\mathrm { d d H _ { 2 } O \ 1 7 . 3 7 5 \mu L }$ 。PCR反应条件为： $9 4 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 预变性 $5 ~ \mathrm { m i n }$ ; $9 4 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 变性 $3 0 ~ \mathrm { s }$ ， $5 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 退火 $3 0 \mathrm { ~ s ~ }$ ，72 $\mathrm { { ^ \circ C } }$ 延伸 $3 0 ~ \mathrm { s }$ ，25个循环；72℃延伸 $7 ~ \mathrm { m i n }$ ，4℃保存。产物用 $2 \%$ 琼脂糖凝胶电泳检测，目标条带用DNA切胶回收试剂盒进行回收，得纯化样本，并用BioTek酶标仪测定各样本浓度并定量。

# 1.3.4.2富集并扩增DNA文库

每个样品DNA 等量混合，采用标准的 Illumina TruSeq DNA文库制备试验流程构建所需的宏基因组上机文库，并在 llumina-MiSeq 个人基因组分析平台上进行 Barcoded IlluminaMiseq 测序，采用PE250 测序策略。试验流程为：通过3'-5'核酸外切酶及聚合酶的共同作用，修复带有突出末端的DNA片段，在修复平整的DNA片段3末端引入单碱基A，接头的3'末端含有单碱基T，从而保证DNA片段和接头能通过A和T配对连接。利用PCR选择性地富集两端连有接头的DNA片段，同时扩增DNA文库。

# 1.3.4.3 验证文库、上机测序

利用PicoGreen 和荧光分光光度计定量文库，多样品DNA文库均一化至 $1 0 \ \mathrm { n m o l / L }$ 后等体积混合，并逐步稀释定量至 $4 { \sim } 5 \ \mathrm { p m o l / L }$ 后上机测序。

# 1.4 统计分析

# 1.4.1 测序基本数据处理

对经过双端（pair-end）测序的数据进行质量控制，截断或舍弃低质量序列（50个连续碱基平均质量大于号Q30，不允许有N）。用软件Flash 连接通过质量控制的序列，舍弃无法连接的序列。对选择通过的序列进行过滤，过滤原则为：舍弃碱基长度在 $2 0 0 { \sim } 1 \ 0 0 0$ 之外的、含有模糊碱基的、含有错配碱基的、连续相同碱基大于号6，模糊碱基大于号1的序列，获得最终用于分析的序列。

# 1.4.2 生物分类及统计分析

应用Qiime 分析软件，根据序列的相似度，将序列归为多个操作分类单元(operationaltaxonomic unit,OTU)。Qiime 调用Uclust对序列进行聚类，选取每个类最长的序列为代表序列。采用RDP-classifier，以RDP 数据库的序列为训练集，对OTU代表序列进行注释。

物种丰度按属层次进行归类计算，先对物种丰度进行log2 转换，接着再将转换后的数值与单样品丰度平均值之差除以单样品丰度标准差，完成数据标准化。将数据导入SPSS 19,采用方差分析（ANOVA）、t检验和LSD多重比较法进行统计分析， $P { < } 0 . 0 5$ 为存在显著性差异。

# 2结果与分析

# 2.1DON 对小鼠肠道微生物测序数据的影响

表1结果显示，经过16S rDNAV4区的 Ilumina Miseq 双端测序，对照组和DON 组分别获得有效序列86146.23和84 594.98条，其中优质序列分别为85843.64和84 305.31条，DON 组较对照组检测序列减少，但统计学差异不显著（ $P$ 大于号0.05）。反映 $9 7 \%$ 相似度下样品取样深度的稀释曲线见图1，每个样品均在80000 条左右，表明取样深度一致。所测序列长度集中在 $1 7 8 \sim 2 6 8 \mathrm { b p }$ 之间，平均长度为 $2 2 6 \mathrm { b p }$ ，见图2。

# 表1小鼠粪便样本测序数量分析

Table 1 Analysis of sequencing quantities for fecal samples of mice 条   

<html><body><table><tr><td>项目Items</td><td>对照组 Control group</td><td></td><td></td></tr><tr><td></td><td></td><td>DON 组 DON group</td><td>P值P-value</td></tr></table></body></html>

<html><body><table><tr><td colspan="4">有效序列</td></tr><tr><td></td><td>86 146.23±11 856.48</td><td>84 594.98±7 317.08</td><td>0.78</td></tr><tr><td>Effective sequences</td><td></td><td></td><td></td></tr><tr><td>优质序列</td><td></td><td></td><td></td></tr><tr><td></td><td>85 843.64±11 831.43</td><td>84 305.31±7 321.11</td><td>0.84</td></tr><tr><td>High quality sequences</td><td></td><td></td><td></td></tr></table></body></html>

同行数据肩标不同小写字母表示差异显著（ ${ \cdot } P { < } 0 . 0 5$ ），相同或无字母表示差异不显著（ $P$ 大于号0.05）。下表同。

In the same row,values with different small letter superscripts mean significant difference （20 $( P { < } 0 . 0 5 )$ ,while with the same or no letter superscripts mean no significant difference $P$ 大于号 0.05). The same as below.

![](images/e935fb48f5a2e06746ab4d3fb3878bd54ab8a546f6a503ac468aa6e2e8644472.jpg)  
C1、C2、C3为对照组样本1、2、3；T1、T2、T3为DON 组样本1、2、3。下图同。

C1,C2,C3 indicates the sample 1,sample 2and sample 3 in control group; T1,T2,T3 indicates the sample1, sample 2 and sample 3 in DON group. The same as below.

图1小鼠粪便样本测序序列稀释曲线（相似度： $9 7 \%$ ）

Fig.1Rarefaction curve of sequenced reads in feces of mice (similarity: $9 7 \%$ ）

![](images/c12ef6a97e9b21022869cb4d48f3e1e7514758c5d2298bd2df3617fc49024694.jpg)  
图2测序序列长度分布

# 2.2小鼠肠道微生物丰度分布曲线图

对各样本的OTU丰度大小排序，取log2的对数值作丰度分布曲线图，见图3，结果发现对照组和DON组样本中物种分布均匀，可用于多样性分析。

![](images/5ccf5a0bb78eec5da4ce1f09ccab48e8cc532f3d18bbeee9b78fb2e529ccf687.jpg)  
Fig.2Length distribution of sequenced reads   
图3小鼠粪便样品样本OTU丰度曲线图  
Fig.3Curves of OTU abundance in fecal samples of mice

2.3DON对小鼠肠道微生物菌群Alpha多样性的影响

将2组样品所有序列按 $9 7 \%$ 的相似度进行OTU聚类，利用程序运算得到评价微生物Alpha多样性丰度和均度的Shannon指数，见图4。结果发现，DON组Shannon指数降低，与对照组相比差异显著（ $P$ 小于号0.05）。

![](images/9653aa3aeb15daca2bfad78cbfd558369b360e5ba2535156931c102ff125f6b0.jpg)

\*表示与对照组相比差异显著（ $P$ 小于号0.05）。

\* indicates significant difference compared with control groups ( $P$ 小于号0.05).

图4DON处理后肠道微生物菌群的Shannon指数变化

Fig.4Change of Shannon diversity indexes of intestinal microbes exposed to DON

2.4DON对小鼠肠道微生物菌群Beta多样性的影响

Beta多样性是不同生态系统之间多样性的比较，是物种组成沿环境梯度或在群落间的变化率，用来表示生物种类对环境异质性的反应。经主坐标分析(principalco-ordinatesanalysis,PCoA)方法分析，见图5，结果显示DON组与对照组能显著区分，并且菌群结构（蓝色）分布紧凑、相似度高，多样性较对照组降低。

![](images/458139281af048688b6d974685d3ecdb1a13cf6310208f90b02580861463f154.jpg)

# 图5DON处理后肠道微生物Beta多样性变化

# 2.5物种丰度差异性分析

为探讨DON对肠道微生物群落结构和组成的影响，在门和属2个层次上对同类的OTU进行聚类比较研究。表2和图4结果显示，在门水平上，拟杆菌门（Bacteroidetes）的物种丰度与对照组相比显著降低 $( P$ 小于号0.05)，在总群落中的占比由 $4 5 . 0 1 \%$ 降低到 $3 5 . 2 5 \%$ ；脱铁杆菌门（Deferribacteres）的物种丰度与对照组相比也显著降低（ $P$ 小于号0.05)，占比由 $0 . 7 6 \%$ 降低到 $0 . 3 9 \%$ 。软壁菌门（Tenericutes）的物种丰度也呈降低趋势，与对照组相比差异不显著（ $P$ 大于号0.05）。变形菌门（Proteobacteria）的物种丰度与对照组相比显著提高（ $P$ 小于号0.05)，占比由 $6 . 6 6 \%$ 提高到 $8 . 7 8 \%$ 。疣微菌门（Verrucomicrobia）的物种丰度则呈上升趋势，与对照组相比差异不显著（ $P$ 大于号0.05）。对照组厚壁菌门（Firmicutes）在总群落中的占比为 $4 3 . 0 5 \%$ ，DON组Firmicutes的占比则上升到 $5 0 . 4 1 \%$ ，但物种丰度统计学差异不显著（ $P$ 大于号0.05）。

![](images/9824018f9dcd160d903db770435cd13ee2f12372f5b0d0c282160a604717e298.jpg)  
Fig.5Change of beta diversity of intestinal microbes exposed to DON   
图4在门水平上粪便微生物分布饼状图  
Fig.4The pie chart of intestinal microbes distributed on phylum level

# 表2肠道微生物丰度在门水平的显著性分析

Table 2Phylum level significance analysis of intestinal microbes 条   

<html><body><table><tr><td></td><td></td><td></td><td>相对倍数变化</td><td></td></tr><tr><td>门</td><td>对照组</td><td>DON组</td><td>Relative fold</td><td>P值</td></tr><tr><td>Phylum</td><td>Control group</td><td>DON group</td><td>change/[Log(C/T,2)]</td><td>P-value</td></tr><tr><td>拟杆菌门 Bacteroidetes</td><td>33 534.20±8 510.69a</td><td>28 922.44±1 495.53b</td><td>0.213</td><td>0.01</td></tr><tr><td>脱铁杆菌门</td><td></td><td></td><td></td><td></td></tr><tr><td>Deferribacteres</td><td>555.45±46.06a</td><td>378.73±95.61b</td><td>0.553</td><td>0.02</td></tr><tr><td>变形菌门 Proteobacteria</td><td>5 294.64±587.99b</td><td>6 441.51±841.95a</td><td>0.283</td><td>0.01</td></tr><tr><td>软壁菌门</td><td></td><td></td><td></td><td></td></tr><tr><td>Tenericutes</td><td>234.10±80.28</td><td>148.46±16.54</td><td>0.657</td><td>0.07</td></tr><tr><td>疣微菌门</td><td></td><td></td><td></td><td></td></tr><tr><td>Verrucomicrobia</td><td>680.95±35.77</td><td>2 472.37±474.48</td><td>-1.860</td><td>0.06</td></tr></table></body></html>

C为对照组，T为DON组。下表同。   
C represents the control group,T represents the DON group. The same as below.

表 3 结果显示，在属的水平上，与对照组相比，DON 组显著降低了副类杆菌属（Parabacteroides）、理研菌属（Rikenella）、Algoriphagus、Mucispirilum、嗜甲基菌属（Methylophilus）、Francisella 的物种丰度( $P$ 小于号0.05)，显著提高了梭菌属（Clostridium）、

Robinsoniella、Allobaculum、Akkermansia的物种丰度（ $\cdot P$ 小于号0.05)。同时，DON 组还影响了短杆菌属（Brevibacterium）、粪球菌属（Coprococcus）、Kordiimonas、Pusillimonas、厌氧原体属（Anaeroplasma）的物种丰度，但与对照组相比差异不显著（ $P$ 大于号0.05）。

此外，图6呈现了肠道微生物菌群在属水平的物种间相似性聚类关系（heatmap)，结果表明 DON组小鼠肠道微生物结构发生改变，与对照组相似性差异显著，与表3结果一致。

表3肠道微生物在属水平的物种丰度显著性分析

Table 3Genus level significance analysis of intestinal microbes 条   

<html><body><table><tr><td></td><td></td><td></td><td>相对倍数变化</td><td></td></tr><tr><td>属 Genus</td><td>对照组 Control group</td><td>DON组 DON group</td><td>Relative fold change/[Log(C/T,2)]</td><td>P值 P-value</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>短杆菌属 Brevibacterium</td><td>0.63±0.56</td><td>1.25±0.48</td><td>-0.976</td><td>0.09</td></tr><tr><td>副类杆菌属</td><td>1 806.26±607.93a</td><td>937.05±281.09b</td><td>0.946</td><td>0.03</td></tr><tr><td>Parabacteroides</td><td></td><td></td><td></td><td></td></tr><tr><td>文肯菌属 Rikenella</td><td>550.72±90.21a</td><td>323.72±14.15b</td><td>0.766</td><td><0.01</td></tr><tr><td>Algoriphagus</td><td>3.90±1.61a</td><td>1.30±1.08b</td><td>1.584</td><td>0.04</td></tr><tr><td>Mucispirillum</td><td>555.45±46.06a</td><td>378.73±95.61b</td><td>0.552</td><td>0.03</td></tr><tr><td>梭菌属</td><td>0.01±0.00b</td><td>1.41±0.69a</td><td>-10.468</td><td>0.03</td></tr><tr><td>Clostridium</td><td></td><td></td><td></td><td></td></tr><tr><td>粪球菌属</td><td>0.36±0.14</td><td>0.83±0.09</td><td>-1.171</td><td>0.09</td></tr></table></body></html>

<html><body><table><tr><td colspan="4">Coprococcus</td></tr><tr><td>Robinsoniella</td><td>121.38±60.49b</td><td>390.96±230.81a</td><td>-1.687</td><td>0.04</td></tr><tr><td>Allobaculum</td><td>0.92±1.61b</td><td>3.01±2.64a</td><td>-1.079</td><td>0.04</td></tr><tr><td>Kordiimonas</td><td>2.28±1.06</td><td>3.26±1.77</td><td>-0.511</td><td>0.08</td></tr><tr><td>Pusillimonas</td><td>0.01±0.00</td><td>0.82±0.09</td><td>-1.232</td><td>0.08</td></tr><tr><td>嗜甲基菌属</td><td>26.70±8.56</td><td>18.78±1.72</td><td>0.507</td><td>0.05</td></tr><tr><td>Methylophilus</td><td></td><td></td><td></td><td></td></tr><tr><td>Francisella</td><td>1.01±0.13a</td><td>0.33±0.00b</td><td>1.585</td><td>0.01</td></tr><tr><td>厌氧原体属</td><td>233.38±80.52</td><td>148.22±66.54</td><td>0.655</td><td>0.09</td></tr><tr><td>Anaeroplasma</td><td></td><td></td><td></td><td></td></tr><tr><td>Akkermansia</td><td>650.57±239.46b</td><td>2 446.55±1 277.54a</td><td>-1.911</td><td>0.05</td></tr></table></body></html>

![](images/f8d6e0de748d6f2c2bfc2bf3b2828402b302f29dc2ff3bd12c75a61d3c892b1c.jpg)  
图6DON处理后肠道微生物结构区系图的变化  
Fig.6Change of bacterial distribution of intestinal microbes exposed to DON

# 3讨论

动物肠道中栖居着大量的微生物菌群，不仅与宿主机体之间保持着一种动态平衡，不同菌群之间也存在着一定的比例关系。菌群的稳态对维持机体生长发育、营养消化吸收、免疫拮抗等生理功能都具有重要的影响[12]。本试验应用lumina-MiSeq高通量测序技术，突破传统的培养方法和以16S rDNA为基础的分子生物学方法，可产生覆盖广、深度深的测序数据，并通过比对或聚类分析，判定微生物群落物种组成的变化，同时挖掘低丰度或未知的细菌，能更加全面、准确地获得敏感菌群信息，对准确判定DON对肠道微生物毒性作用具有重要意义。

# 3.1DON对肠道菌群多样性的影响

肠道微生物多样性是促进营养物质吸收、维持机体免疫和新陈代谢的基础，多样性降低极易对宿主免疫产生影响，进而影响健康[13]。本研究指出，灌胃DON后小鼠肠道微生物测序数量2组之间没有显著差异，但DON组的有效序列和优质序列均较对照组降低，说明肠道微生物的种类有所减少。此外，DON组反映Alpha多样性丰度和均度的Shannon指数显著降低，PCoA方法分析Beta多样性发现DON组菌群结构分布紧凑，多样性降低。但Waché等[10]和Piotrowska等[14]的研究表明，饲粮添加DON处理不影响猪肠道菌群的丰度和多样性，不同的结果可能是由于检测方法、DON添加剂量和动物的种属等差异引起的。课题组前期研究指出灌胃DON后，肠道氨基酸、矿物元素等营养物质的表观消化率降低，小鼠体重减轻，免疫机能下降[15]，推测与DON致小鼠肠道微生物多样性降低有关。

# 3.2DON对肠道微生物菌群结构和物种丰度的影响

本研究通过Illumina-MiSeq测序技术检测小鼠粪便中微生物菌群结构和组成的变化，结果显示DON处理后小鼠肠道微生物物种丰度发生显著变化，并呈现一定的规律性。人类肠道中的优势菌群分别为Bacteroidetes和Firmicute，在肠道菌群所占的比例约 $9 0 \%$ 以上，小鼠肠道2个菌门的占比为 $8 5 \% ^ { [ 1 6 ] }$ ，本试验中小鼠肠道Bacteroidetes和Firmicutes菌门占 $80 \%$ 以上，

DON处理后2个优势菌门的总占比没有变化，但Bacteroidetes的物种丰度较对照组显著降低。Bacteroidetes是一类具有促进碳水化合物发酵，参与糖类、胆汁酸和类固醇代谢等功能的菌群[17]，Wang等[18]给大鼠灌胃黄曲霉毒素Bi能显著抑制肠道中Bacteroidetes相关菌群丰度，在肠道炎症或溃疡时Bacteroidetes的物种丰度也显著降低[19]，与本研究结果一致。此外，Deferribacteres的物种丰度降低，Proteobacteria的物种丰度提高。高脂肪饲粮诱导的非酒精性脂肪肝模型小鼠，Proteobacteria的物种丰度也增加，反映肠黏膜完整性的紧密连接蛋白occludin表达降低，提示肠道损伤发生[20]。综合这些结果表明DON可能与黄曲霉毒素、高脂饲粮一样可引起肠道菌群丰度发生改变，进而诱导肠道炎症，引发肠道损伤。

在属的水平,与对照组相比,DON组显著降低了Parabacteroides、Rikenella、AlgoriphagusMucispirillum、Methylophilus、Francisella的物种丰度。多有研究指出，这些菌属物种丰度的降低与肠道疾病密切相关。Noor等[21指出溃疡性结肠炎患者比正常人的粪便微生物中Parabacteroides菌属表达水平较低，并推测此菌属的缺失可能与肠道炎症有关。目前肠道中Rikenella的作用还没有明确，但有研究指出Rikenellaceae是肠道内具有保护性功能的菌群[22],本试验Rikenella的物种丰度显著降低，提示DON有抑制肠道有益菌的作用。Mucispirillum作为肠道细菌群落标志物，在肠炎早期或抗生素应用时丰度显著降低[23]，与本试验DON使肠道Mucispirillum的物种丰度降低结果相同。推测，小鼠灌胃DON可使肠道Parabacteroides和Mucispirillum炎症敏感菌群以及有益菌Rikenella的物种丰度降低，进而引起肠道炎症发生，导致肠道损伤同时危害机体健康。

此外，DON还降低了肠道中Algoriphagus、Methylophilus和Francisella的物种丰度，由于这些菌属在肠道中的占比较低，分离培养技术不成熟，其功能作用研究也鲜有报道，故有待进一步探索研究。

DON灌胃后显著提高了Clostridium、Robinsoniella、Allobaculum以及Akkermansia的物种丰度，许多研究表明这些菌属的变化也与肠道感染和炎症密切相关。Clostridium是厚壁菌门的一个菌属，包含产气荚膜梭菌、肉毒梭菌等多种致病菌，可产生外毒素，对人和动物都有较强的毒害作用。Piotrowska等[4]给猪饲喂DON污染的饲粮发现结肠内容物中产气荚膜梭菌含量增加，提示DON可诱导肠道中致病菌含量增加。Robinsoniella被认为是临床肠道感染的继发性入侵者，在伤口感染部位或菌血症患者血液均可分离得到[24]。在白细胞介素-10（IL-10）基因敲除的肠炎小鼠模型，肠道Robinsoniellapeoriensis的物种丰度也显著提高[25],而本研究肠道微生物中Robinsoniella的物种丰度增加，表明DON有诱发肠道炎症和感染的可能。Allobaculum尽管在肠道微生物中的占比较低，但有研究指出高胆固醇饲粮诱导的肠炎性小鼠肠道中Allobaculumde的物种丰度增加，并且Allobaculum的物种丰度与抗炎因子的表达呈负相关[26]。Zhou等[27]给小鼠灌胃地沟油后肠道黏膜损伤并诱发肠炎，Allobaculum丰度也显著提高，与本研究DON诱导肠道Allobaculum丰度增加结果一致。Akkermansia是近年来研究热门的一个菌属，作为是疣微菌门的优势菌群，约占 $8 3 \%$ ，占总肠道微生物的 $1 \% \sim$ 4%[28]，以肠道上皮黏蛋白为碳源和氮源，能削弱肠道黏液屏障的厚度[29-30]。多有研究发现超重或者肥胖者肠道中Akkermansia的物种丰度降低，推测肠道中Akkermansia有减缓脂肪沉积，减轻体重的作用[31-32]。杨俊花等[15]研究发现，小鼠灌胃DON后，体重显著降低。此外，Akkermansia还可干扰宿主黏膜平衡而加剧鼠伤寒沙门氏菌诱发的肠道炎症[33]。推断DON作用使小鼠体重减轻及肠道炎症发生，可能与肠道Akkermansia的物种丰度增加有关。

目前为止，DON致肠道炎症的报道较多，主要集中在DON使肠绒毛高度降低、隐窝减少、肠上皮细胞炎性因子白细胞介素-12(IL-12)和肿瘤坏死因子 $\mathbf { \nabla } \cdot \mathbf { a }$ （TNF-α)表达增加等[34-35]。但这些研究均没有涉及肠道微生物菌群的变化，DON致肠道菌群丰度变化是否与肠道炎症有直接的关系，还有待我们进一步验证。此外，鉴于Parabacteroides和Mucispirillum的物种丰度降低和Clostridium、Robinsoniella、Allobaculum、Akkermansia的物种丰度提高与肠道感染、炎症的相关性，故可以将这些菌群丰度的变化作为DON引发肠道炎症、危害肠道健康的菌群标志物。

# 4结论：

$\textcircled{1}$ DON灌胃处理后，小鼠肠道微生物菌群丰度减少，Alpha多样性和Beta多样性降低。

$\textcircled{2}$ 在门水平，与对照组相比，DON组显著降低了Bacteroidetes和Deferribacteres的物种丰度，显著提高Proteobacteria的物种丰度。在属水平，与对照组相比，DON组显著降低Parabacteroides、Rikenella、Mucispirillum的物种丰度，显著提高了Clostridium、Robinsoniella、Allobaculum、Akkermansia的物种丰度。

$\textcircled{3}$ 肠道中这些菌属丰度的变化与肠道炎症密切相关，提示这些菌属可能是DON引发肠道炎症的菌群标志物。

# 参考文献:

[1] BENNETT J W,KLICH M.Mycotoxins[J].Clinical Microbiology Reviews,2003,16(3):497-516.

[2] WU Q H,LOHREY L,CRAMER B,et al.Impact of physicochemical parameters on the decomposition of deoxynivalenol during extrusion cooking of wheat grits[J].Journal of Agricultural and Food Chemistry,2011,59(23):12480-12485.

[3]李群伟.真菌毒素与人类健康[M].北京:人民军医出版社,2005.

[4] ROTTER BA,PRELUSKY D B,PESTKA J J.Toxicologyofdeoxynivalenol (vomitoxin)[J].Journal of Toxicology and Environmental Health,1996,48(1):1-34.

[5] PESTKA J J,SMOLINSKI A T.Deoxynivalenol:toxicology and potential effectson humans[J].Journal of Toxicology and Environmental Health,Part B,2Oo5,8(1):39-69.

[6] ANTONISSEN G,VAN IMMERSEEL F,PASMANS F,et al.Deoxynivalenol predisposes for necrotic enteritis by affecting the intestinal barrier in broilers[C]//International Poultry Scientific Forum.Atlanta,Georgia:Georgia World Congress Center,2O13:9-10.

[7] AWAD W A,ZENTEK J.The feed contaminant deoxynivalenol affects the intestinal barrier permeability through inhibition of protein synthesis[J].Archives of Toxicol0gy,2015,89(6):961-965.

[8] CHO I,BLASER M J.The human microbiome:at the interface of health and disease[J].Nature Reviews Genetics,2012,13(4):260-270.

[9] ALI-VEHMAS T,RIZZO A,WESTERMARCK T,et al.Measurement of antibacterial activities of T-2 toxin,deoxynivalenol,ochratoxin a,aflatoxin $\mathbf { B } _ { 1 }$ and fumonisin $\mathbf { B } _ { 1 }$ using microtitration tray-based turbidimetric techniques[J].Journal of Veterinary Medicine Series A,1998,45(8):453-458.

[10] WACHE Y J,VALAT C,POSTOLLEC G,et al.Impact of deoxynivalenol on the intestinal microflora of pigs[J].International Journal of Molecular Sciences,2Oo9,1O(1):1-17.

[11] SAINT-CYR M J,PERRIN-GUYOMARD A,HOUEE P,et al.Evaluation of an oral subchronic exposure of deoxynivalenol on the composition of human gut microbiota in a model of human microbiota-associated rats[J].PLoS One,2013,8(11):e80578.

[12] SHEN J,ZHANG B R,WEI G F,et al.Molecular profiling of the Clostridium leptum subgroup in human fecal microflora by PCR-denaturing gradient gel electrophoresis and clone library analysis[J].Applied and Environmental Microbiology,2006,72(8):5232-5238.

[13]HILDEBRAND F,NGUYEN T L A,BRINKMAN B,et al.Inflammation-associated enterotypes,host genotype,cage and inter-individual effects drive gut microbiota variation in common laboratory mice[J].Genome Biology,2013,14(1):R4.

[14] PIOTROWSKA M,SLIZEWSKA K,NOWAK A,et al.The effect of experimental Fusarium mycotoxicosis on microbiota diversity in porcine ascending colon contents[J].Toxins,2014,6(7):2064-2081.

[15] 杨俊花,刘峰良,刘丹,等.脱氧雪腐镰刀菌烯醇(DON)致BALB/c小鼠的急性、亚急性和免疫毒性研究[J].上海农业学报,2015,31(3):12-18.

[16] BEZIRTZOGLOU E,TSIOTSIAS A,WELLING G W.Microbiota profile in feces of breastand formula-fed newborns by using fluorescence in situ hybridization (FISH)[J].Anaerobe,2011,17(6):478-482.

[17] SALYERS A A.Bacteroides of the human lower intestinal tract[J].Annual Review of Microbiology,1984,38(1):293-313.

[18] WANG J C,TANG L L,GLENN T C,et al.Aflatoxin $\mathbf { B } _ { 1 }$ induced compositional changes in gut microbial communities of male F344 rats[J].Toxicological Sciences,2016,150(1):54-63.

[19] SCALDAFERRI F,GERARDI V,LOPETUSO L R,et al.Gut microbial flora,prebiotics,and probiotics in IBD:their current usage and utility[J].BioMed Research International,2013,2013:435268.

[20] 孙晓琦.加味泽泻汤对NAFLD小鼠肠道微生物干预作用的研究[D].博士学位论文.南京:南京中医药大学，2015.

[21] NOOR S O,RIDGWAY K,SCOVELL L,et al.Ulcerative colitis and irritable bowel patients exhibit distinct abnormalities of the gut microbiota[J].BMC Gastroenterology,2O10,10:134.

[22] COX L M,YAMANISHI S,SOHN J,et al.Altering the intestinal microbiota during a critical developmental window has lasting metabolic consequences[J].Cell,2O14,158(4):705-721.

[23] 邓冠华.抗微生物药长期给药对小鼠肠道微生物组多样性的影响[D].硕士学位论文.广州:南方医科大学，2013.

[24] FERRARIS L,AIRES J,BUTEL M J.Isolation of Robinsoniella peoriensis from the feces of premature neonates[J].Anaerobe,2012,18(1):172-173.

[25]WOHLGEMUTH S,KELLER S,KERTSCHER R,et al.Intestinal steroid profilesand microbiota composition in colitic mice[J].Gut Microbes,2011,2(3):159-166.

[26] LEE S M,HAN H W,YIM S Y.Beneficial effects of soy milk and fiber on high cholesterol diet-induced alteration of gut microbiota and inflammatory gene expression in rats[J].Food & Function,2015,6(2):492-500.

[27] ZHOU Z K,WANG Y Y,JIANG Y M,et al.Deep-fried oil consumption in rats impairs glycerolipid metabolism,gut histology and microbiota structure[J].Lipids in Health and Disease,2016,15:86.

[28] BELZER C,DE VOS W M.Microbes inside-from diversity to function:the case of Akkermansia[J].The ISME Journal,2012,6(8):1449-1458.

[29] MCGUCKIN M A,LINDEN S K,SUTTON P,et al.Mucin dynamics and enteric pathogens[J].Nature Reviews Microbiology,2011,9(4):265-278.

[30] HASNAIN S Z,WANG H Q,GHIA J E,et al.Mucin gene deficiency in mice impairs host resistance to an enteric parasitic infection[J].Gastroenterology,2010,138(5):1763-1771.

[31] KARLSSON C L J, ONNERFALT J,XU J,et al.The microbiota of the gut in preschool children with normal and excessive body weight[J].Obesity,2012,20(11):2257-2261.

[32]TEIXEIRA T F S,GRZESKOWIAK L M,SALMINEN S,et al.Faecal levelsof Bifidobacterium and Clostridium coccoides but not plasma lipopolysaccharide are inversely related to insulin and HOMA index in women[J].Clinical Nutrition,2013,32(6):1017-1022.

[33] GANESH B P,KLOPFLEISCH R,LOH G,et al.Commensal akkermansia muciniphila exacerbates Gut inflammation in salmonella typhimurium-infected gnotobiotic mice[J].PLoS One,2013,8(9):e74963.

[34] VANDENBROUCKE V,CROUBELS S,MARTEL A,et al.The mycotoxin deoXynivalenol potentiates intestinal inflammation by Salmonella typhimurium in porcine ileal loops[J].PLoS One,2011,6(8):e23871.

[35] 邓波,万晶,徐子伟,等.脱氧雪腐镰刀菌烯醇吸附剂对断奶仔猪生长性能、血清生化指标 及肠道形态的影响[J].动物营养学报,2014,26(5):1294-1301.

Effects of Deoxynivalenol on Intestinal Microbiota of Mice Analyzed by Ilumina-MiSeq

High-Throughput Sequencing Technology

YANG JunhuaZHAO Zhihui\*GUO WenboGUO Jinli (Institute of Agri-Food Standards and Testing Technology, Shanghai Academy ofAgricultural Sciences, Shanghai 201403,China)

Abstract: This study was conducted to investigate the effects of deoxynivalenol (DON） on bacterial diversity and species abundance of intestinal microbiota.A total of 4O BALB/c mice weighted about $2 0 \ \mathrm { g }$ were randomly allotted to control group (intragastric gavage sterilized saline) and DON group (intragastric gavage $1 . 8 ~ \mathrm { m g / k g }$ BW DON) with 20 replicates per group and 1 mouse per replicate. The mice were fed by intragastric administration for 28 days. After the test, fresh fecal samples were collected and 3 samples in each group were randomly selected for investigating the microbial community and composition by using Illumina-MiSeq high-throughput sequencing technology. The results showed as follows: 1) the quantities of sequences observed in DON group was less than that in control group （P小于号O.05）.2) The Alpha and Beta diversity were respectively reduced in DON group,and the Shannon index was also significantly decreased compared with the control group (P小于号0.05). 3） At the phylum level, compared with the control group，the abundances of Bacteroidetes and Deferribacteres in DON group were significantly decreased (P小于号0.O5)，while the abundance of Proteobacteria was significantly increased (P小于号o.05). At the genus level, compared with the control group, the abundances of Parabacteroides, Rikenella,Algoriphagus,Mucispirillum,Methylophilus and Francisella in DON group were significantly decreased( $P$ 小于号 O.O5)，but the abundances of Clostridium, Robinsoniella, Allobaculum and Akkermansia in DON group were significantly increased (P小于 号0.05). 4) The cluster analysis showed low similarity of intestinal microflora between the control and DON group. In conclusion， the bacterial diversity and species abundance of intestinal microbiota can be influenced by DON,and it is suggested that the intestinal lesions caused by consumption of DON may be related with the change of intestinal bacteria communities. Key word: high-throughput sequencing; deoxynivalenol; intestinal microbiota