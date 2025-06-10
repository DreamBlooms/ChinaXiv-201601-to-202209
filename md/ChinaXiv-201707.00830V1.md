# 以大肠杆菌为底盘细胞构建XyIR-Pu线路检测2,4,6-三硝基甲苯

温国霞}² 黄子豪1²　谭俊杰³阚乃鹏凌婧怡张　霞²刘　刚²\*\*陈惠鹏²（1安徽大学健康科学研究院合肥2306012军事医学科学院北京100071)(3 成都军区总医院成都6100834 福建省疾病预防控制中心福州350001)(5南京军区福州总医院福州350001)

摘要目的:恶臭假单胞菌中的TOL质粒上的 XyIR-Pu是经典的甲苯代谢通路,在甲苯类化合物存在时,调控蛋白XylR可以特异性的激活 $\mathrm { P u }$ 启动子,进而启动相应甲苯代谢通路的表达。基于合成生物学的思想,优化设计此通路并导入遗传背景清楚、操作简单的大肠杆菌中构建全细胞生物传感器,用于检测环境污染物2,4,6-三硝基甲苯(TNT)。方法:以 pETDuet-1 为载体骨架,构建了XyIR-Pu基因线路,并以绿色荧光蛋白GFP为报告分子,GFP的荧光值可以指征结合诱导剂后的XylR蛋白对Pu启动子的诱导强度,并在基因线路中加入四串联终止序列来降低背景值。最后对XyIR蛋白的信号识别区进行连续易错PCR,构建随机突变体文库,从中筛选具有更高感应强度、更好灵敏度及特异性的调控蛋白。结果：四串联终止序列可有效降低XylR-Pu通路的背景值,随机突变体文库中筛选出的生物元件eX0-4,对TNT表现出良好的感应强度、灵敏度及特异性。结论;XylR蛋白在大肠杆菌中对硝基甲苯响应不明显,但筛选得到的突变蛋白eX0-4,为后续生物传感器的更深层次地开发提供了优良的元件储备。另外，利用易错PCR构建随机突变体文库从中筛选发挥预定功能的突变蛋白质也可成为挖掘生物元件的一种通用方法。

关键词 2,4,6-三硝基甲苯 合成生物学 生物传感器 基因线路 TOL 质粒

中图分类号［Q815]

2,4,6-三硝基甲苯(TNT)是一种带苯环的有机化合物，因其良好的爆炸性能，常被用来制造地雷及各种炸药。地雷的广泛使用及TNT的长效性,导致战争遗留下来的地雷每年都造成上百人的伤亡，严重威胁着人们的生命安全。同时泄露在环境中的TNT还是一种重要的环境污染物，它可以渗入到土壤及水系统中，长期参与生态循环；而且TNT及其降解物还可以进入食物链进而引发急性中毒，其对生态环境和人类健康造成了极大威胁[1]。研发高效、准确的检测 TNT的工具,对战后雷场清除及环境治理都有重要意义。

TNT在工业生产过程中会产生多种不可避免的副产物，如1,3-二硝基苯（1,3-DNB）、2,4-二硝基甲苯(2,4-DNT)及2,6-二硝基甲苯(2,6-DNT），因此在检测TNT时,1,3-DNB、2,4-DNT及2,6-DNT等化合物也可作为检测的靶标[2]。目前传统的TNT检测方法有高效液相色谱（HPLC）、紫外检测（UV）、气相色谱-质谱（GC-MS）、激光表面增强拉曼光谱（SERS）、核磁共振(NMR)和离子迁移法等[34],但这些方法大都需要昂贵的仪器和繁复的样品制备方法以及专业的操作流程，在实际应用中会受到很大的限制。目前基于合成生物学思想构建生物传感器成为研究热点[5-6],由于生物传感器具有成本低、敏感度高及易操作等优点，因此为TNT 检测提供了新的思路,特别适合于战后雷场的大规模检测,具备良好的发展前景[7-8]

恶臭假单胞菌MT-2菌株携带的TOL质粒具有经典的甲苯代谢通路，常被广泛研究用来构建生物传感器实现甲苯、苯、乙苯及二甲苯的检测[9-I1]。在甲苯类化合物存在时，其中的调控蛋白XyIR可以特异性的激活 $\mathrm { P u }$ 启动子，进而引发甲苯代谢通路的表达（图1a）。原理大致是：反式作用因子XyIR蛋白属于 $\mathrm { N t r C }$ 家族成员，其由4部分组成，A区是诱导物的结合区，结合诱导物后构象改变，通过短的连接区域（B区），激活C区活性，C区结构高度保守，负责协调ATP的水解，并通过与依赖 $\mathbf { \sigma } _ { \mathbf { { \sigma } } ^ { 5 4 } }$ 因子的RNA聚合酶相互作用起始转录；D区的螺旋-转角-螺旋结构辅助其结合到 $\mathrm { P u }$ 启动子上,最终激活 $\mathrm { P u }$ 活性[12-15]（图1b）。

![](images/c6223bdba222d78cf4a6a37cf89c7383b4b7ba587ddb28dd40f4549702960e39.jpg)  
图1TOL质粒甲苯代谢通路(a)及XyIR蛋白结构(b)  
Fig.1Toluene degradation pathway of TOL plasmid (a)and domain organization of XylR（b

由于XylR 蛋白的天然诱导剂是甲苯,其对硝基甲苯没有明显感应,研究者[1]通过将XyIR蛋白的A区域与其NtrC家族的同源蛋白DmpR（其可结合苯酚类物从而激活Po启动子启动苯酚代谢通路的表达)进行DNAshuffling,得到了可感应2,4-DNT的XylR突变体蛋白XyIR5，并且构建XylR5-Pu基因线路在模拟雷场中首次实现了对爆炸物的定位。但XyIR5 蛋白的感应灵敏度很低，环境中的2，4-DNT浓度不低于364mg/L时才能激活 $\mathrm { P u }$ 启动子，而且XylR5蛋白的特异性较差,其对甲苯的感应强度要高于TNT。

为了更好地将 $\mathrm { \ X y l R { 5 - P u } }$ 基因线路应用于TNT的检测，我们以pETDuet-1为载体骨架，构建了XylR- $\mathrm { \cdot P u }$ 和XyIR5-Pu两条基因线路，并以绿色荧光蛋白（GFP)为报告分子，GFP的荧光值可以指征结合诱导剂后的XylR蛋白对 $\mathrm { P u }$ 启动子的诱导强度，并将其导入遗传背景研究清楚、操作简单的大肠杆菌细胞中构建全细胞生物传感器，用于检测环境中的污染物TNT。通过对比两条线路的荧光值，既可以验证基因线路在大肠杆菌中是否发挥功能，又可以验证XyIR5突变体在大肠杆菌中对TNT是否仍具有较好的感应强度。最后通过对基因线路的优化设计，以及对XyIR蛋白的A区的随机突变，从中筛选出对靶标化合物TNT有更高感应强度、灵敏度及特异性的蛋白质元件，并构建性能更加优良的基因线路。

# 1材料与方法

# 1.1材料

2,4,6-三硝基甲苯（TNT），2-硝基甲苯（2-NT），3-硝基甲苯（3-NT），4-硝基甲苯（4-NT），1,4-二硝基苯（1,4-DNB），1,3-二硝基苯（1,3-DNB），2,4-二硝基甲苯（2，4-DNT），2，6-二硝基甲苯（2,6-DNT），甲苯（Toluene）,苯（Benzene），硝基苯（Nitrobenzene）均购自Sigma-Aldrich公司；质粒pETDuet-1为本实验室保存;感受态 $\mathrm { D H } 5 \alpha$ 及BL21（DE3)购于天根生物科技有限公司；Q5DNA聚合酶、限制性内切核酸酶及T4DNA 连接酶均购自NEB公司；96孔深孔板、黑色96孔荧光板均购自Thermo 公司。

# 1.2 基因线路的构建

1.2.1目的基因序列的获得从NCBI网站上获取XylR蛋白 $\left( 1 \ 7 0 1 \mathrm { b p } \right)$ 及 $\mathrm { P u }$ 启动子( $2 3 4 \mathrm { b p }$ )的基因序列，由北京奥科鼎盛生物技术有限公司合成2段序列并分别连接在pMD18-T载体上，分别命名为pMD18T-XylR和 $\mathrm { p M D 1 8 T \mathrm { - } P u }$ 。

通过在NCBI上查询XyIR与DmpR的序列，得到了XyIR5的核酸序列，合成后克隆到pGH载体上，命名为 pGH-XylR5。

质粒pPROBE-TT上含有783bp四串联的终止序列$4 \times$ Terminator，人工合成此四串联序列，并在两端分别加上HindIII和NotI酶切位点，克隆到pGH载体上，命名为 $\mathrm { p G H \mathrm { - } \mathrm { 4 T e r } }$ 。

1.2.2PCR扩增目的片段实验涉及的引物见表1。按照常规PCR方法，利用Q5DNA聚合酶组成PCR体系，以pMD18T-XylR为模板，使用引物XO-B和XO-N进行PCR,扩增目的片段XylR;以pGH-XylR5为模板,使用引物X5-B和X5-N进行PCR，扩增目的片段XylR5;以pMD18T-Pu为模板,使用引物 $\mathrm { P u } { - } B s r \mathrm { G } \mathrm { ~ I ~ }$ 和PU-NdeI进行PCR，扩增启动子 $\mathrm { P u }$ 序列；以质粒pPROBE-TT为模板,使用引物GFP-KpnI和GFP-AurII进行PCR，扩增质粒上的GFP基因。

# 表1引物列表

Table1Primers used in this study   

<html><body><table><tr><td>Primer name</td><td>Sequence(5'-3')</td><td>Restriction size</td></tr><tr><td>X0-B</td><td>CAGGATCCAATGTCGCTTACATACAAACCC</td><td>BamHI</td></tr><tr><td>X0-N</td><td>TAGCGGCCGCCTATCGGCCCATTG</td><td>NotI</td></tr><tr><td>X5-B</td><td>GGGGGGATCCAATGTCGCTTACATACAAA</td><td>BamHI</td></tr><tr><td>X5-N</td><td>TAGCGGCCGCCTATCGGCCCATTG</td><td>NotI</td></tr><tr><td></td><td>ATTGTACACGGCCGCATAATCGAAATGGAAAGCGCGATGAACCTTTTTTA</td><td>BsrGI</td></tr><tr><td>PU-NdeI</td><td>GCCATATGTATATCTCCTTCTTATACTTAACTAATATACTAAGATGGTGAAGGGTCA</td><td>NdeI</td></tr><tr><td></td><td>CCACTATTTTTATTTTAAGTCTCGTATA</td><td></td></tr><tr><td>GFP-KpnI</td><td>TCGGTACCATGAGTAAAGGAGAAGAA</td><td>KpnI</td></tr><tr><td> GFP-AurII</td><td>GGCCTAGGCTATTTGTATAGTTCATCC</td><td>AurII</td></tr><tr><td>Error-PstI</td><td>GTCTGCAGCTCGTAGCGCTCG</td><td>PstI</td></tr></table></body></html>

1.2.3 基因线路 $\mathrm { X 0 - P u }$ -GFP-Duet及 $\mathrm { X } 5 { - } \mathrm { P u }$ -GFP-Duet的构建以pETDuet-1为基础载体，用 $B a m \mathrm { H } \thinspace V N o t \mathrm { ~ I ~ }$ 对载体和扩增片段XylR分别进行双酶切,连接得到正确的载体pXO-Duet,其中XylR基因插入在pETDuet-1的第一个T7启动子控制的多克隆位点（MCS）内。

以构建的pX0-Duet为基础载体,用BsrGI/Nde I对载体和扩增片段 $\mathrm { P u }$ 进行双酶切，连接得到正确的载体 $_ { \mathrm { p X 0 - P u - D u e t } }$ ,其中 $\mathrm { P u }$ 启动子替换掉pETDuet-1的第二个T7 启动子。

以构建的 $\mathrm { { \ p X 0 - P u } }$ -Duet为基础载体，用KpnI/AurII对载体和扩增片段GFP进行双酶切，连接得到正确的载体 $\mathrm { { p X 0 - P u } . }$ -GFP-Duet,其中GFP 插入在有 $\mathrm { P u }$ 启动子控制的第二个MCS内（图2a）。

![](images/1761c0d7892ff9f57637bb871361d38e76efc969f357ca410944581a93338427.jpg)  
图2基因线路图谱  
Fig.2The map of gene lines

(a) $\mathrm { { \ p X 0 - P u } }$ GFP-Duet（b) $\mathrm { p X 0 - 4 T e r - P u }$ -GFP-Duet

以上述同样的方法，用XylR5片段替代XyIR片段，得到载体 $\mathrm { p X } 5 { - } \mathrm { P u }$ -GFP-Duet

1.2.4 SDS-PAGE 检测基因线路的蛋白质表达将质粒 $\mathrm { { p X 0 - P u } }$ -GFP-Duet或 $\mathrm { p X } 5 { - } \mathrm { P u }$ -GFP-Duet转化大肠杆菌后， $3 7 ^ { \circ } \mathrm { C } \ . 2 0 0 \mathrm { r / m i n }$ 培养至 $O D _ { 6 0 0 }$ 约0.6时，加入终浓度为 $1 \mu \mathrm { m o l }$ 的IPTG, $3 0 \%$ $2 0 0 \mathrm { r / m i n }$ 培养 $1 2 \mathrm { h }$ 后，取样进行电泳分析。

1.2.5 基因线路X0-4Ter $\mathrm { \cdot P u }$ -GFP-Duet及X5-4Ter-PuGFP-Duet 的构建分别将 $\mathrm { { p X 0 - P u } }$ -GFP-Duet及pGH-4Ter载体用HindIII/NotI双酶切后连接,得到在XylR序列末端带有4串联终止序列的的载体pX0-4Ter-Pu-GFP-Duet（图2b）。以同样的方法，得到载体pX5-4Ter-$\mathrm { P u } .$ -GFP-Duet

# 1.3 基因线路检测TNT

挑取 $\mathrm { { p X 0 - P u } }$ -GFP-Duet或 $\mathrm { p X } 5 { - } \mathrm { P u }$ -GFP-Duet单克隆过夜培养后，百倍稀释至新鲜LB培养基，并将其分为三组。 $3 7 ^ { \circ } \mathrm { C } \ , 2 0 0 \mathrm { r / m i n }$ 培养至 $O D _ { 6 0 0 }$ 约0.6时,于第一组加入终浓度为 $1 \mu \mathrm { m o l }$ 的 IPTG和终浓度为 $1 5 \mathrm { m g / L }$ 的 TNT;第二组加入终浓度为 $1 \mu \mathrm { m o l }$ 的IPTG;第三组为阴性对照。 $3 0 \mathrm { ^ c } \cdot 2 0 0 \mathrm { r / m i n }$ 培养 $1 2 \mathrm { h }$ 后,各吸取 $2 0 0 \mu \mathrm { l }$ 菌液至黑色96孔荧光板，在PekinElmerMultimodePlateReader 中测定荧光值（检测条件为excitation/emission,$4 8 8 / 5 0 7 \mathrm { n m }$ 。

基因线路X0-4Ter- $\mathrm { \cdot P u }$ -GFP-Duet及X5-4Ter-Pu-Duet 检测 TNT的方法与步骤同上。

18

# 易错PCR构建XyIR突变体文库

$\mathrm { \cdot P u }$ Duet 为模板,利用GeneMorph Random Mutagenesis Kitcat: $\# 2 0 0 5 5 0$ ,Agilent Technologies）对XylR基因的A区进行易错 $\operatorname { P C R }$ 。按照说明书配制扩增体系，扩增条件为： $9 5 \mathrm { ^ \circ C }$ 预变性 $2 \mathrm { m i n }$ ，然后以 $9 5 \mathrm { ^ \circ C }$ 变性 $3 0 \mathrm { s } \lrcorner 5 0 \mathrm { ^ q C }$ 退火$3 0 \mathrm { { s } } \sqrt { 7 } 2 \mathrm { { ^ circ C } }$ 延伸 $2 \mathrm { m i n }$ 扩增35个循环， $7 2 \%$ 延伸 $1 0 \mathrm { { m i n } }$ 。回收目的产物,以此为模板,进行第二轮易错PCR,PCR体系和程序不变;然后再以第二轮胶回收产物为模板，进行第三轮易错PCR,回收第三轮易错PCR产物。pX0-4Ter- $\mathrm { \cdot P u }$ -GFP-Duet和第三轮易错PCR产物分别用 $B a m \mathrm { H } \ V P s t \mathrm { ~ I ~ }$ 进行双酶切，连接产物转化大肠杆菌,构建XyIR 突变体文库。

# 1.5 文库筛选

挑取突变体文库中的单克隆至96孔深孔板进行培养， $3 7 ^ { \circ } \mathrm { C } \ . 2 0 0 \mathrm { r / m i n }$ 培养至 $O D _ { 6 0 0 }$ 约0.6时每孔加入终浓度为 $1 \mu \mathrm { m o l }$ 的IPTG和终浓度为 $1 5 \mathrm { m g / L }$ 的TNT,$3 0 \mathrm { ^ c } \cdot 2 0 0 \mathrm { r / m i n }$ 培养12h后，每孔吸取 $2 0 0 \mu \mathrm { l }$ 菌液测定荧光值，将荧光值高于XyIR5的菌挑选出来。

将挑选出的菌液百倍稀释进行培养，分为三组，第一组在 $O D _ { 6 0 0 }$ 约0.6时加入终浓度为 $1 \mu \mathrm { m o l }$ 的 IPTG和终浓度为 $1 5 \mathrm { m g / L }$ 的 TNT;第二组加入终浓度为 $1 \mu \mathrm { m o l }$ 的IPTG；第三组为阴性对照； $3 0 \mathrm { ^ c } \cdot 2 0 0 \mathrm { r / m i n }$ 培养 $1 2 \mathrm { h }$ 后，测定荧光值。将三组荧光值有显著差异( $\textstyle P < 0 . 0 5 ,$ 的克隆挑选出来。

# 1.6 特异性检测

将荧光值有显著差异的单克隆接种于LB培养基，

$3 7 ^ { \circ } \mathrm { C } \ . 2 0 0 \mathrm { r / m i n }$ 培养至 $O D _ { 6 0 } ^ { } 0$ 约0.6时加入终浓度为$1 \mu \mathrm { m o l }$ 的IPTG,按照国际公认的检测方法[16],分别加入终浓度为 $1 5 \mathrm { m g / L }$ 的如下10种目标化合物：2,4,6-$\mathrm { T N T } , 2 , 4 \mathrm { - D N T } , 2 , 6 \mathrm { - D N T } , 1 , 3 \mathrm { - D N B } , 1 , 4 \mathrm { - D N B } , 2 \mathrm { - N T } , 3 -$ NT、4-NT、Toluene 和Nitrobenzene, $3 0 \mathrm { ^ c } \cdot 2 0 0 \mathrm { r / m i n }$ 振荡培养 $1 2 \mathrm { h }$ 后，测定荧光值。挑选对TNT或其衍生物2,4-DNT、2,6-DNT及1,3-DNB的反应强度较其他化合物有明显差别( $P < 0 . 0 5 )$ 的克隆。

# 1.7 灵敏度检测

将筛选得到的阳性克隆与pX0-4Ter- $\cdot \mathrm { P u }$ -GFP-Duet、pX5-4Ter- $\mathrm { \cdot P u }$ -GFP-Duet分别接种至LB培养基, $3 7 \%$ 、$2 0 0 \mathrm { r / m i n }$ 培养至 $O D _ { 6 0 0 }$ 约0.6时加入终浓度 $1 \mu \mathrm { m o l }$ 的IPTG,并分别加入终浓度为 $\mathrm { 0 m g / L , 5 m g / L , 1 0 m g / L } .$ $\mathrm { 1 5 m g / L _ { \ell } 2 0 m g / L _ { \ell } 3 0 m g / L _ { \ell } 5 0 m g / L _ { \ell } 7 5 m g / L _ { \ell } 1 0 0 m g / L _ { \ell } } ,$ $1 5 0 \mathrm { m g / L } \sqrt { \Omega }$ 和 $3 0 0 \mathrm { m g / L }$ 的TNT,然后 $3 0 \mathrm { ^ c } \cdot 2 0 0 \mathrm { r / m i n }$ 振荡培养 $1 2 \mathrm { h }$ 后分别测定荧光值，通过计算元件的$\mathrm { E C } _ { 2 0 0 }$ 值,考察元件对TNT的感应灵敏度。

# 1.8 蛋白质结构分析

将筛选得到的阳性克隆送交测序，并将序列提交至PSIPRED(http://bioinf.cs.ucl.ac.uk/psipred/）进行二级结构预测和 SWISS-MODEL（http://swissmodel.expasy.org/)进行同源模建，对蛋白质结构进行比对分析。

# 2结果

# 2.1 基因线路X0-Pu-GFP-Duet及X5-Pu-GFP-Duet的鉴定

构建的重组质粒 $\mathrm { { p X 0 - P u } }$ -GFP-Duet 和 pX5-Pu-GFP-Duet经提取纯化后，分别利用限制性内切核酸酶BamHI/NotI、BamHI/NotI、KpnI/AurII进行双酶切，结果均获得了与预期大小相符的目的条带（图3），说明基因线路 ${ \mathrm { X 0 - P u } }$ -GFP-Duet 和 $\mathrm { X 5 - P u }$ -GFP-Duet构建成功。

# 2.2SDS-PAGE检测基因线路XyIR蛋白表达

SDS-PAGE结果表明，加入IPTG诱导后，特异性表达的XyIR和XyIR5蛋白分子质量大小与预期相符（图4），说明T7启动子可以启动XyIR和XyIR5蛋白的正常表达。

# 2.3 基因线路X0-Pu-GFP-Duet 及X5-Pu-GFP-Duet 检测TNT

将 $\mathrm { { p X 0 - P u } }$ -GFP-Duet及 $\mathrm { p X } 5 { - } \mathrm { P u }$ -GFP-Duet分别转

![](images/68002e2c37798528646c947bcf0e2bbb66f61e375c6adab59176fd0434ec5d9b.jpg)  
Fig.3Identification of recombinantplasmidsbyagarose gel electrophoresis

P-Duet(b) $\mathrm { p X } 5 { - } \mathrm { P u }$ GFP-Duet1-3:BamHI/Not I;4-6:BamHI/NotI;7-9:Kpn I/Aur II;Marker:Trans 15KDNA n

![](images/2ccc3422bc995cf5363d6dfd94b143fa31286e558b7c2e39207fcf02c2e1a58c.jpg)  
图3重组质粒酶切鉴定

化大肠杆菌，构建成全细胞生物传感器，用于检测TNT。 结果发现,诱导表达的XyIR/XyIR5蛋白在无TNT时也能启动下游GFP的表达,而且基因线路的本底表达值很高（图5）。分析原因可能是由于T7强启动子造成了线路通读，为了抑制通读、降低本底表达，尝试在XylR与 $\mathrm { P u }$ 之间插入四串联终止序列。

# 2.4基因线路X0-4Ter-Pu-GFP-Duet及X5-4Ter-Pu-GFP-Duet的鉴定

构建的重组质粒pX0-4Ter- $\cdot \mathrm { P u }$ -GFP-Duet和pX5-4Ter- $\mathrm { \cdot P u }$ -GFP-Duet分别用HindIII/NotI进行双酶切，结果表明带有四串联终止序列的基因线路构建成功（图6）。

# 2.5基因线路X0-4Ter-Pu-GFP-Duet及X5-4Ter-PuGFP-Duet检测TNT

将基因线路X0-4Ter $\cdot \mathrm { P u }$ -GFP-Duet及X5-4Ter-Pu-GFP-Duet经过相同的步骤检测TNT，结果表明在基因线路中加入四串联终止序列可以有效阻止通读，降低本底表达（图7a）。XylR5蛋白较XylR蛋白对TNT的感应强度高，但两者对TNT的感应效果都不显著，特异性较差(图7b)

![](images/cb57a0b2582cc9c09f3f5a2b3a0bdf642310216fe6ff14a0c25c6048dfbe7dc4.jpg)  
图4SDS-PAGE鉴定XyIR/XyIR5蛋白表达 Fig.4Identification of expression of XylR/XylR5 by SDS-PAGE （a）XylR（b）XylR5M:Protein marker; $1 - 3 : 1 \mu \mathrm { m o l }$ IPTG;4-6:Control   
图5pX0-Pu-GFP-Duet 及pX5-PuGFP-Duet检测TNT Fig.5Detection of TNT by $\mathbf { p X 0 - P u - }$ GFP-Duet and pX5-Pu-GFP-Duet

![](images/371c0e2bd6d3b43101b3185b6c1168e56b957c1e6f71b7da314d5cc1e068d09a.jpg)  
图6重组质粒pX0-4Ter-Pu-GFP-Duet及pX5-4Ter-Pu-GFP-Duet 酶切鉴定 Fig.6Identification of recombinant plasmids by agarose gel electrophoresis

1-3:pX0-4Ter-Pu-GFP-Duet;4-6:pX5-4Ter-Pu-GFP-Duet

![](images/9587f71edccfa676668a8ebcfb24cbbcbc733ca46511c441a4964dd0cfc6a635.jpg)  
图7pX0-4Ter-Pu-GFP-Duet及pX5-4Ter-Pu-GFP-Due 检测 TNT Fig.7Detection of TNT by pX0-4Ter-Pu-GFP-Duet and pX5-4Ter-Pu-GFP-Duet

Comparison of background values after optimization（b）Comparison of induction strength of gene lines $^ { * } P < 0 . 0 5$ \*\*P<0.01

# XyIRO突变体文库的构建及筛选

通过引物XO-B和Error- $. P s t \textbf { I }$ ，利用Agilent易错试剂盒对XyR基因的A区进行连续三轮易错PCR，BamHI/PstI双酶切第三轮PCR产物,然后连入经相同酶切后的载体pX0-4Ter $\cdot \mathrm { P u }$ -GFP-Duet，转化大肠杆菌,构建突变体文库。由于 $B a m \mathrm { ~ H ~ } V P s t \mathrm { ~ I ~ }$ 位于A区边缘，因此可以精确控制只对蛋白质A区进行随机突变。

挑取突变体文库中的单克隆至96孔深孔板，先通过在终浓度为 $1 5 \mathrm { m g / L }$ 的TNT条件下，筛选荧光值高于XylR5 ( $2 8 \times 1 0 ^ { 4 }$ )的克隆。为了去除假阳性，再将筛选出来的克隆经过三组不同处理，第一组加入 $1 \mu \mathrm { m o l }$ 的IPTG和终浓度为 $1 5 \mathrm { m g / L }$ 的 TNT,第二组只加入 $1 \mu \mathrm { m o l }$ 的 IPTG,第三组为阴性对照,将在三组中荧光值有显著差异的克隆挑选出来，最后得到11个，其中的克隆eX0-4在TNT中的荧光值较其余两组有极显著性差异（图8a）。

# 2.7 特异性检测

将筛选出来的11个XyIR突变体对十种苯类化合物的感应强度进行比较，筛选得到了1株能特异性感知TNT的阳性克隆eX0-4，如图8（b），其对TNT及其衍生物DNB的感应强度较其余化合物达到了极显著性差异，表现出了对靶标化合物良好的特异性。

# 2.8 灵敏度检测

$\mathrm { E C } _ { 2 0 0 }$ 值是目前构建生物传感器领域比较通用和认可的检测灵敏度的指标，具体是指感应元件引发的荧光值的倍数变化能达到初始荧光值2倍时所需的最低诱导物浓度， $\mathrm { E C } _ { 2 0 0 }$ 值越小，说明感应元件的灵敏度越高。

![](images/af20c8e4871cdd7307bdcd956bb13c45f02096737b575dc286bef80faabdda01.jpg)  
图8基因线路eX0-4检测TNT及其特异性研究

Fig.8Detection of TNT by peXo-4 and the study of its specificity（a）TNT fluorescence detection（b）Specificity study \*\*P<0.01我们将 px0-4Ter $\mathrm { \cdot P u }$ CrP-Duet PXx-4T-r $\mathrm { \cdot P u }$ GEPDue 及阳性克隆 peX0-4分别接种至LB 培养基,培养至 8 $\overline { { \theta D } } _ { 6 0 0 }$ 约为0.6时加入浓度呈梯度上升的 TNT 中,振荡培养 $1 2 \mathrm { h }$ 后测定荧光值，如图9所示， $\mathrm { p X 0 - 4 T e r - P u } .$ GFP-Duet对TNT没有明显感应,无法计算 $\mathrm { E C } _ { 2 0 0 }$ $\mathrm { p X } 5 4$ 'er- $\ifmmode \mathrm { \hat { P } } \mathrm { u } \else \mathrm { \hat { P } } \mathrm { u } \fi \qquad $ -GFP-Duet的 $\mathrm { E C } _ { 2 0 0 }$ 值为 $6 1 . 3 \pm 1 . 5 6 \mathrm { { m g / L } }$ ,peX0-4的值为 $( 1 2 \pm 5 . 2 1 ) \mathrm { m g / L }$ ，可见突变体 $\mathrm { e X 0 - 4 }$ 对TNT的感应灵敏度大幅度提高,其 $\mathrm { E C } _ { 2 0 0 }$ 值达到了国际上报道同类元件的领先水平。并且TNT浓度在 $1 5 \sim 7 5 \mathrm { m g / L }$ 时,pX5-4Ter $\mathrm { \cdot P u }$ -GFP-Duet及 $\mathrm { p e X 0 4 }$ 表现出了浓度依赖性,而随着 TNT浓度不断增加荧光值下降,原因是高浓度的TNT严重损害了细菌的正常生长。

# 2. 测序分析

通过测序分析，突变体eX0-4较野生型XyIR在A

![](images/5008c44c8c363d960377dbe1a72f09c410cd180f1cc62c27c6aa786a5c9cda74.jpg)  
图9基因线路对不同浓度TNT的感应强度 Fig.9Induction intensity of gene lines to different concentrations of TNT

区有12个碱基缺失，并且中间有7个碱基替换，造成N端4个氨基酸缺失及5个氨基酸替换（图10）。

![](images/858309aee281799e3804503ef68e0769f5cfb16262090aad97f60dbdc94a144f.jpg)  
图10 蛋白质序列比对  
Fig.10Protein sequence alignment of XylR and eX0-4

# 2.10 蛋白质结构预测分析

生物信息学软件分析表明，蛋白质突变前后二级结构及三维空间结构都发生了一定改变(图11）。我们推测eX0-4突变蛋白A区的氨基酸改变，使其可以产生更合适的取向，与小分子TNT能够充分接近，相互契合产生更稳定的复合物构象，作用在 $\mathrm { P u }$ 启动子上发挥功能。

![](images/f0710f539ee477ab34deed343ad7cd136c70acb97a43dc522a6e780c25a9c839.jpg)  
图11蛋白质三维结构模型  
Fig.11The three-dimensional structure models of XylR and eX0-4

# 3讨论

在本研究中，我们在合成生物学思想的指导下，首先将恶臭假单胞菌内的XyIR蛋白、突变体XyIR5、Pu等生物元件与绿色荧光蛋白进行逐级组装搭建检测线路，然后选择遗传背景清晰、操作简便的大肠杆菌作为底盘细胞，用来承载设计的生物元件及基因线路，构建成全细胞生物传感器用于检测TNT。由于国际上报道的感应元件对TNT的最高灵敏度达到 $1 5 \mathrm { m g / L }$ ，所以我们采用的TNT筛选终浓度也低至 $1 5 \mathrm { m g / L }$ ,希望获得的蛋白质元件能够对如此低浓度的TNT有明显感应。但两条基因线路 ${ \mathrm { X 0 - P u } }$ -GFP-Duet及 ${ \mathrm { X } } 5 { \mathrm { - P u } }$ -GFP-Duet 在检测TNT时，无论是否加TNT，IPTG诱导后表达的XylR/XyIR5蛋白都能激活下游的 $\mathrm { P u }$ 启动子。分析可能是因为T7启动子的启动活性太强，覆盖了 $\mathrm { P u }$ 启动子的活性，造成了整个基因线路的通读。为了更好地实现预定功能，尝试在XyIR与 $\mathrm { P u }$ 序列之间插入一个终止序列，发现背景值有所降低，直到最终加入四串联终止序列才彻底阻止了T7启动子的通读。

优化的基因线路在检测TNT时，XyIR5蛋白对TNT有感应，表明对XyIR蛋白的A区进行改造获得感应TNT的蛋白质元件的方法是可行的。但XylR5蛋白对TNT的感应强度及特异性差，分析可能是由于XyIR5蛋白的A区结合TNT后引发的构象并不能使之很好的结合到 $\mathrm { P u }$ 启动子上，最大程度地激活 $\mathrm { P u }$ 活性，于是进一步对XyIR蛋白的A区进行人工改造，通过采用连续易错PCR的方法对其进行随机突变构建文库，从中挖掘出性状更加优良的蛋白质元件。最终筛选得到的蛋白质突变体eX0-4对TNT表现出了高的感应强度和良好的特异性及灵敏度。同源模建结果表明蛋白质eX0-4的三维空间结构发生了改变，这可能有利于其以更合适的取向与TNT相互作用，蛋白质与小分子相互作用时,氨基酸残基的改变会直接影响两者的亲和力，我们目前正在尝试用分子对接的方法进行预测分析，期望从中归纳出XyIR蛋白与TNT相互作用的氨基酸残基类型，为未来的突变提供较为明确的筛选方向，也希望通过对元件作用机制以及底盘细胞研究更清楚的基础上，构建的生物传感器可以高灵敏度、高特异性的对环境中的TNT及其靶标化合物进行检测，可为战后雷场或现场爆炸物的大规模排查和清除提供重要的辅助手段。

另外,构建的基因工程菌对人类及环境可能造成的安全问题也一直牵动着科学家的神经，我们实验室也一直致力于实现细菌自裂解方面的研究。我们基于合成生物学的方法尝试构建了可受阿拉伯糖诱导的自杀线路,并取得了初步成效[17]。阿拉伯糖较常用的抗生素具有更好的环境亲和力，加入之后，线路表达的Holin蛋白可以在细菌的细胞膜上打孔，使得细胞内的溶解酶(lysozyme）可以透过小孔溶解细胞壁从而降解细胞，组成型表达的anti-Holin可以抑制本底表达的Holin,保证未诱导时细菌的正常生长。构建的自杀线路单独导入大肠杆菌，加入诱导剂2h后可以实现菌体完全裂解，但其配合peX0-4感应线路共同发挥作用的条件还在摸索，争取尽快做到检测、裂解合二为一。

合成生物学作为一门交叉学科，在21世纪获得了迅猛发展，基于标准化、模块化的生物元件，通过人工设计、化学合成和重新组装基因线路或基因组，合成生物学可以构建具有特定功能的生命系统，甚至是人造生命[18-20]。构建生物传感器是合成生物学研究的重要应用领域之一，通过挖掘自然界中对靶标化合物敏感的生物元件，并将其与报告元件组装成基因线路，报告元件的信号强度指征生物元件对靶标化合物的感应强度[21-22]

生物元件、装置和系统是合成生物学的三大基本要素。作为要素之一的生物元件是指遗传系统中最简单、最基本的生物积块（BioBrick），是具有特定功能的氨基酸或者核苷酸序列，可以说它是合成生物学的基石[23]。而且合成生物学与基因工程和代谢工程最显著的区别也正在于可以将大量生物元件进行快速、随意组装，以形成新的具有特定生物学功能的装置。而实现这一目标的前提是我们仍需要大量挖掘、鉴定并改造更多的生物元件。我们通过以XyIR- $\mathrm { \cdot P u }$ 为基因线路，以GFP为报告蛋白，以大肠杆菌为底盘细胞，以连续易错PCR构建随机突变体文库，挖掘到了可特异、高效感应TNT的蛋白质元件，为下一步成型的生物传感器提供了合成生物学的元件基础、线路基础以及技术基础。

# 参考文献

trinitrotoluene biosensorswith novel sensing elements from Escherichia coli K-12 MG1655.Cell Biochemistryand Biophysics,2015，72（2）:417-428. Habib M K.Controlled biological and biomimetic systems for of ion mobility spectrometry for the detection of explosives and explosive related compounds.Talanta,2001,54（3）：515-529. Armenta S，Alcala M,Blanco M.A review of recent, Analytica Chimica Acta,2011，703（2）：114-123. Magrisso S，Erel Y，Belkin S.Microbial reporters of metal bioavailability.Micro Biotechnol,2008,1(4）:320-330.   
[6]Robin T,van der Meer JR. Bacterial biosensors for measuring availability of environmental pollutants．Sensors,20o8,8（7）: 4062-4080.   
[7］Turner A P F.Biosensors：sense and sensibility.Chemical Society Reviews,2013，42（8）:3184-3196.   
[8]TrangPTK,Berg M，Viet PH,et al.Bacterial bioassay for rapid and accurate analysisof arsenic in highly variable groundwater samples．Environmental Science & Technology, 2005，39（19）:7625-7630.   
[9］Kim M N，Park HH,Lim WK，et al．Construction and comparison of Escherichia coli whole-cell biosensors capable of detecting aromaticcompounds.Journal ofMicrobiological Methods,2005,60（2）:235-245.   
[10]Pérez-Martin J,De Lorenzo V．Identification of the repressor subdomain within the signal reception module of the prokaryotic   
[Il」Delgado A,Kamos JL.Genetic evidence tor activation ot the positive transcriptional regulator Xy1R，a member of the NtrC family of regulators，by efector binding.Journal of Biological Chemistry,1994,269（11） :8059-8062.   
[12]NatashaV,Ann E M,Anisa Y,et al.Structure，function，and tethering of DNA-binding domainsin o54 transcriptional activators．Biopolymers，2013,99（12）:1082-1096.   
[13]Galvao T C，Mencia M,De Lorenzo V. Emergence of novel functions in transcriptional regulators by regression to stem protein types．Molecular Microbiology,2007,65（4）:907-919.   
[14]Garmendia J，De Las Heras A，Galvao TC，et al.Tracing explosives in soil with transcriptional regulators of Pseudomonas putidaevolved forresponding tonitrotoluenes．Microbial Biotechnology,2008，1（3）：236-246.   
[15] De Las Heras A,De Lorenzo V. Cooperative amino acid changes shift the response of the g54-dependent regulator XylR from naturalm-xylenetowardsxenobiotic2，4-dinitrotoluene. Molecular Microbiology,2011,79（5）：1248-1259.   
[16]Yagur-Kroll S，Lalush C，Rosen R，et al．Escherichia coli bioreporters for the detection of 2,4-dinitrotoluene and 2,4,6- trinitrotoluene.Applied Microbiology and Biotechnology,2014, 98 (2) : 885-895.   
[17］谭俊杰.基于合成生物学的地雷检测方法研究.北京：中国人 民解放军军事医学科学院,2015：90-96. Tan JJ,Research of Landmine Detection Methods Based on SyntheticBiology.Beijing:AcademyofMilitaryMedical Sciences,2015:90-96.   
[18]Mcdaniel R,Weiss R.Advances in synthetic biology:on the path fromprototypestoapplications.CurrentOpinionin Biotechnology,2005，16（4）:476-483.   
[19]Matsumura I. Bacterial cells as model factories.American Journal of Operations Research,2013,3（1):81-86.   
[20]Gibbs W W. Synthetic life.Scientific American,2004,290（5）： 74-81.   
[21］Van Der Meer JR,Belkin S.Where microbiology meets microengineering：design and applications of reporter bacteria. Nat Rev Micro,2010,8（7):511-522.   
[22]Marra A，Asundi J,Bartilson M,et al．.Differential fluorescence induction analysis of Streptococcus pneumoniae identifies genes involved in pathogenesis.Infection & Immunity,20o2,70（3）： 1422.   
[23]Endy D.Foundations for engineering biology.Nature,2005,438 (7067) : 449-453.

# Construction of XylR-Pugene Lines in Escherichia coli to Detect 2,4,6-trinitrotoluene

WEN Guo-xia1,2 HUANG Zi-hao1,2 TAN Jun-jie³ KAN Nai-peng4 LING Jing-yi5 ZHANG Xia1.2 LIU Gang2 CHEN Hui-peng 2 (1Institute of Health Sciences，Anhui University，Hefei23O6O1,China) (2Academy of Military Medical Sciences，Beijing1Ooo71,China) （3 Chengdu Military General Hospital,Chengdu 61Oo83，China） (4Fujian CenterFor Disease Control&Prevention,Fuzhou 35OoO1,China） (5 Fuzhou General Hospital of Nanjing Military Command,Fuzhou 35OOO1,China)

AbstractObjective：The XylR-Pu is a classic toluene catabolic pathway，which is from TOL plasmid of Pseudomonas putida. In the presence of toluene，the XylR regulatory protein can activate $\mathrm { P u }$ promoter and thus induce expression of corresponding metabolic genes.To detect 2,4,6-trinitrotoluene（TNT）,the significant environmental polutant，the pathway was optimized and put into Escherichia coli to construct whole-cell biosensor，which was based onthe idea of synthetic biology.E.coliwas chosen as chasss celldue to its genetic background was clear and it was simple to operate. Methods: pETDuet-1 was used as backbone to construct gene circuit of XylR- $\mathrm { \cdot P u }$ ， XylR was inserted in first multi cloning site. The second T7 promoter was substituted by $\mathrm { P u }$ promoter and reporter gene of green fluorescent protein was under the control of Pupromoter.The fluorescent values can indicate the strength of the activation of XylR protein to $\mathrm { P u }$ promoter. Then four series terminator was inserted between XylR and $\mathrm { P u }$ to minimize background expression．Finally，the receptor domain of XylR protein was randomly mutated using sequential eror prone PCR to construct a mutant library and to identify XylR mutants，which can be more sensitive and specific to TNT.Results:The four series terminator can effectively prevent read-through and decrease background fluorescent.After selection，one mutant protein named eX0-4 displayed better induction intensity，sensitivity and specificity to TNT.Conclusions:As Nitrobenzene was not XylR natural inducer，so XylR showed no obvious response to TNT.But the method is feasible to modify the A domain of XylR protein to obtain non-natural but beter protein components.The mutant of eXO-4 enriched the reservoir of TNT-sensing elements，and provided a moreapplicable toolkit to be applied in genetic routes and live systems of biosensors in future.It can bea common method to identify biological elements touse eror prone PCR to construct mutant library.

Key words2,4,6-trinitrotoluene Synthetic biology Biosensor Gene lineTOL plasmid