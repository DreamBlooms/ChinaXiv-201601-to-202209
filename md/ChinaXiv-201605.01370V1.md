# 利用串联亲和纯化的方法筛选耻垢分枝杆菌中MutM的相互作用蛋白

范尚华1,2）周盈²）张泓泰2）Joy F1eming2喻子牛1）张先恩2)\* 毕利军2)\*\*(华中农业大学生命科学技术学院，农业微生物学国家重点实验室，武汉430070;2中国科学院生物物理研究所，中国科学院核酸生物学重点实验室和生物大分子国家重点实验室，北京 100101)

摘要MutM(formamidopyrimidine-DNA glycosylase，Fpg)是原核生物碱基切除修复系统(BER)中同时具有 DNA糖苷酶和脱嘌呤／脱嘧啶 AP裂解酶活性的一种双功能酶，不但可以识别DNA 损伤，而且能切除损伤的碱基，从而参与到许多种损伤的修复过程．除了高致突变率的8-羟基鸟嘌呤(8-oxoguanine，8-oxoG)外，MutM在其他损伤修复中具体作用机制还不清楚本研究主要以耻垢分枝杆菌(M.smegmatis)为研究对象，利用串联亲和纯化技术和质谱相结合的方法对可能与 MutM相互作用的蛋白因子进行发现和鉴定，并于体外用Far-westerm 和GST pul-down 方法对鉴定出的蛋白 DEAD-box ma helicase、RpsC、UvrA与 MutM的相互作用进行了验证．实验结果表明，利用串联亲和纯化方法来发现MutM相互作用的蛋白是切实可行的．本研究为进一步深入研究MutM在其参与的损伤修复中的具体机制提供了切入点.

关键词耻垢分枝杆菌，碱基切除修复，MutM，串联亲和纯化 学科分类号Q5，Q7 DOI: 10.16476/j.pibb.2015.0065

对于所有活的生物体，保持基因组的稳定性是至关重要的，但每个生物体又不可避免会受到来自各种致突变因素的影响，外源的如辐射、化学诱变剂等，内源的如活性氧类物质 (ROS)、活性氮(RON)等．这些因素可以改变DNA碱基的结构特性，从而造成DNA损伤．为此，生物体在进化过程中建立了不同的DNA修复途径，包括错配修复(MMR)、核苷酸切除修复(NER)、碱基切除修复(BER)、重组修复和 SOS 效应等[I．其中碱基切除修复对由氧化、烷基化和去氨基化等造成的范围较广的小损伤修复起着主导作用[2．这些特定损伤的去除是由一类糖基化酶来执行的[].Formamidopyrimidine-DNA glycosylase (MutM，或Fpg)就是这些糖基化酶中的一种，它在原核生物中称为MutM或Fpg，在真核生物中称为OGG1.其主要参与碱基切除修复的起始，并且对许多损伤有修复作用．目前研究最清楚的是MutM对8-oxoG(8-oxoguanine)的修复．8-oxoG是由于活性氧(ROS)攻击DNA 链中的鸟嘌呤，使之氧化而产生[4，它是一种致突变的DNA 损伤，既可以与C配对，也可以和A进行配对，后者的发生可以导致G:C到T:A的颠换．大肠杆菌中有3种DNA糖基化酶参与到8-oxoG的修复，它们分别为MutT、MutY和MutM，三者在8-oxoG修复过程中的催化机制不同．MutT负责将单独的8-oxo-dGTP水解为8-oxo-dGMP，可防止8-oxoG在DNA复制时进入基因组，MutY则切除与8-oxoG错配的A以减少错误蔓延，以上两种都不能切除DNA链中8-oxoG，只有MutM具有这种能力[．MutM在

8-oxoG修复中发挥多种催化活性，它不但具有识别8-oxoG的能力，使脱氧核糖磷酸链发生糖基化，以便产生单链断裂，而且对8-oxoG具有切割活性，产生AP位点，MutM的失活会使自然突变率急剧升高.

除了可以对8-oxoG进行有效修复外，MutM还可参与到许多不同类型损伤的修复中，如5-甲 酰基尿嘧 啶(5-formyluracil，5-foU)[8]、Guanidinohydantoin(Gh)、 spiroiminodihydantoin(Sp)[9]、错误重组[1]、FapydG[1]和C/C 错配[2-13]等．但是MutM在这些损伤中具体的催化机制还不清楚，如虽然发现MutM参与到C/C错配的修复中，具有结合C/C错配的能力，但是无法有效地修复C/C错配，因此推测C/C错配的修复可能需要别的蛋白质因子参与．已有文献报道[显示，MutM在减少错误重组发生几率方面也发挥着重要的作用，MutM是怎么发挥作用的，这些问题的解答还需要进一步的研究．特别对于分枝杆菌属，无论是慢速生长菌(如结核分枝杆菌)，还是快速生长菌(如耻垢分枝杆菌)，它们的基因组中都未发现MMR途径相关基因的存在[4；另外分枝杆菌基因组GC含量普遍很高，发生C/C错配的几率较其他物种高得多．所以在分枝杆菌中研究MutM以及与其相互作用的蛋白质有特殊的意义.

了解一个蛋白质具体作用机制，寻找与它有相互作用的蛋白质是一个重要的手段．Rigaut和Seraphin等[15于1999年首先提出了TAP技术，特别适用于研究蛋白质在生理条件下的相互作用．该技术通过基于同源重组的基因工程技术在靶蛋白一端嵌入一个纯化标签(TAP tag)，不破坏靶蛋白序列，且靶蛋白和TAPtag融合后的蛋白质表达量与体内水平相当；经过两步连续的亲和纯化获得接近自然条件的特定蛋白质复合体，然后通过质谱技术进行蛋白质鉴定，与免疫共沉淀等传统的研究蛋白质相互作用的技术相比，TAP技术具有周期短、假阳性结果少等优点.

耻垢分枝杆菌作为一种快速生长并且不致病的分枝杆菌，是研究分枝杆菌属特别是结核分枝杆菌的一种重要的模式生物．为弄清楚MutM的具体作用机制，我们利用最近发展起来的分枝杆菌重组系统[将TAPtag插到耻垢分枝杆菌基因组MutM基因的 $3 ^ { \prime }$ 端，使用串联亲和纯化的方法对MutM相互作用的蛋白质进行了筛选和质谱鉴定，同时将部分蛋白质纯化出来，并用Farwestern和GSTpull-down方法对MutM与这些蛋白质间的相互作用进行了体外验证．我们的研究为进一步阐明MutM在各种损伤修复中的作用机制提供了理论基础和切入点.

# 1材料与方法

# 1.1材料

1.1.1 菌株、质粒、培养基和生长状态

本研究所涉及到的菌株和质粒见表1，其中大肠杆菌在LB培养基中培养，对于大肠杆菌的固体培养，需要在LB培养基中加入 $1 . 5 \%$ 的琼脂．耻垢分枝杆菌在7H9液体培养基或者7H10固体培养基中培养，或者根据需要在加入 $0 . 5 \% ( v / v )$ 甘油和$0 . 0 5 \%$ Tween-80的LB培养基中培养．根据需要，在相应的培养基中还要加入氨苄青霉素(Amp)，卡那霉素(Kan)或 潮霉素(Hyg)，它们的终浓度分别为100、60和 $5 0 \mathrm { m g / L }$

Table 1 Strains and plasmids used in this study   

<html><body><table><tr><td>Name&relevant characteristics</td><td>Ref./source</td></tr><tr><td>Strains</td><td></td></tr><tr><td>E. coli BL21(DE3)</td><td>Save in the lab</td></tr><tr><td>M.smegmatis MC2 155</td><td>Save in the lab</td></tr><tr><td>M.smegmatis MC2 155/pJV53</td><td>Save in the lab</td></tr><tr><td>M.smegmatis MC2155/MutM-TAP tag</td><td>Present study</td></tr><tr><td>M.smegmatis MC2155/pSMT3-TAP tag</td><td>Present study</td></tr><tr><td>Plasmids</td><td></td></tr><tr><td>pET20b</td><td>Save in the lab</td></tr><tr><td>pET20b-up-TAP</td><td>Present study</td></tr><tr><td>pET20b-up-TAP-down</td><td>Present study</td></tr><tr><td>pET20b-up-TAP-hyg-down</td><td>Present study</td></tr><tr><td>pET28a</td><td>Save in the lab</td></tr><tr><td>pET28a-MutM</td><td>Present study</td></tr><tr><td>pET28a-MutM-sbp tag</td><td>Present study</td></tr><tr><td>pET28a-UvrA</td><td>Present study</td></tr><tr><td>pET28a-rna Helicase</td><td>Present study</td></tr><tr><td>pET28a-RpsC</td><td>Present study</td></tr><tr><td>pET28a-sbp tag</td><td>Present study</td></tr><tr><td>pGEX-6P-1</td><td>Save in the lab</td></tr><tr><td>pGEX-6P-1-MutM</td><td>Present study</td></tr><tr><td>pSMT3</td><td>Save in the lab</td></tr><tr><td>pJV53</td><td>Save in the lab</td></tr><tr><td>pBS1539</td><td>Save in the lab</td></tr></table></body></html>

# 1.1.2 试剂

IgG Sepharose 6 Fast Flow、 Calmodulin affinityresin、蛋白质银染试剂盒和ECLAdvanceWesternBlottingDetectionKit购自GE公司．AcTEV蛋白酶购自Invitrogen公司．PCR产物纯化试剂盒、胶回收试剂盒和质粒提取试剂盒为Omega公司产品．硝酸纤维素膜和碱性磷酸酶显色试剂盒购自北京鼎国生物公司．蛋白质浓度测定试剂盒为Bio-Rad公司产品．KODDNA聚合酶为TOYOBO公司产品．T4DNA连接酶和限制性内切酶购自NEB公司．BSA(牛血清白蛋白)和潮霉素B均为罗氏公司产品．琼脂糖、琼脂粉、氨苄青霉素、卡那霉素、IPTG、丙烯酰胺、PMSF和N， $\mathbf { N } ^ { \prime }$ -亚甲基双丙烯酰胺均为AMRESCO公司产品．蛋白脉和酵母提取物购自OXOID公司．Proteinmarker为GenStar公司产品．7H9 和7H10 培养基为BD公司产品．碱性磷酸酶－链霉亲和素偶联物为Promega 公司产品．Strep-Tactin Sepharose 购自IBA公司．寡核苷酸引物由上海生工公司合成.

# 1.2含TAP标签敲入片段的构建

本研究主要利用overlapPCR技术和酶切连接相结合的方法获得TAPtag 敲入基因组所需要的cassette(图1)，具体操作步骤如下：分别以质粒pBS1539为模板扩增出TAPtag基因，以质粒pSMT3为模板扩增出潮霉素基因hyg，从耻垢分枝杆菌基因组中分别扩增MutM基因的 ${ \boldsymbol { 5 } } ^ { \prime }$ 端 307 bp片段和 $3 ^ { \prime }$ 端非编码区 $3 0 0 ~ \mathrm { b p }$ 片段(分别简称为 up和 down)．通过overlapPCR 将其中的MutM基因的 ${ \boldsymbol { 5 } } ^ { \prime }$ 端 307 bp 片段和 $T A P \ t a g$ 基因连接起来，形成 $u p \ – T A P$ 片段，并把该片段通过酶切连接的方式连接到载体pET20b上，形成pET20b-up-TAP克隆子．再利用酶切连接的方法，将潮霉素基因hyg 及MutM基因的 $3 ^ { \prime }$ 端300bp非编码区片段分别连到pET20b-up-TAP质粒up-TAP片段的 $3 ^ { \prime }$ 端，最终构建出含敲入片段的质粒pET20b-up-TAP-hyg-down.通过酶切或者PCR的方法，得到含上述4个片段的全序列，形成敲入TAP tag所需的cassette．PCR扩增所用到的寡聚脱氧核糖核酸片段见表2.

![](images/51d1cc8e7cf41d2460a25003e31e7423fa44c79e9a2351329d9224d01c3931d6.jpg)  
Fig.1Strategy for the construction of a TAP-tag knock-in cassette and its integration into the ${ \pmb 3 } ^ { \prime }$ end of mutM in the M.smegmatis genome

TheTAP-tagciessrucdeeteblgestolgtoringoeC generated by fusing together the $3 ^ { \prime }$ end ofthe mutMand TAP-tag(TAP)gene using primer Up-1 and TAP-2.The up-TAP cassette was then cloned into a pET2Ob plasmid to generate the pET $ { \mathrm { \ T } } 2 0  { \mathrm { b / u p } }$ -TAP. The $3 ^ { \prime }$ UTR of mutM and the hygromycin gene $\left( h y g \right)$ were respectively cloned into pE $\mathrm { T } 2 0 \mathrm { b } / \mathrm { u p }$ -TAP generatigplasmidpET2Ob/up-TAP-Hyg-down.ThefullengthTAP-tagknoc-incassetewasobtainedusingPCRordoubledigestionof pET20b/up-TAP-Hyg-downand was knockedintothe genomeatthe endofmutMbyelectrotransformationandrecombineering.

Table 2Oligonucleotides used in this study   

<html><body><table><tr><td>Name</td><td>Sequence (5'-3') (Restriction Enzyme cuting site indicated in bold)</td></tr><tr><td colspan="2">Primers used for generating the TAP-tag knock-in cassete</td></tr><tr><td>Up-1</td><td>GCCGGGATCCCCTGTGGCGCACGAAGAT (BamHI)</td></tr><tr><td>Up-2</td><td>AGAAAAAGGTAGAAGAGAAAAGGTAGACCCGAGGCACCCGC</td></tr><tr><td>TAP-1</td><td>GCCGCGTCCGCGGGTGCCTCGGGTCATGGAAAAGAGAAGATGG</td></tr><tr><td>TAP-2</td><td>GCCCAAGCTT CAGGTTGACTTCCCCGC (Hind II)</td></tr><tr><td>Hyg-1</td><td>GCCCAAGCTTGACTTGCTTAATCAGTGAGGCAC(Hind III)</td></tr><tr><td>Hyg-2</td><td>ATAAGAATGCGGCCGCCTGTCCTCGTTGATCCTTGCC(NotI)</td></tr><tr><td>Down-1</td><td>ATAAGAATGCGGCCGCCAGGTCGGTGGCAGCCGATC (Not I)</td></tr><tr><td>Down-2</td><td>TCCGCTCGAGCCGCGCTGGACAACTACTTCTGTG(Xho I)</td></tr><tr><td colspan="2">Primers used for PCR analysis of TAP-tag knock-in strains</td></tr><tr><td>a</td><td>AACTGCTGGACCAGACCGTGGTGT</td></tr><tr><td>b</td><td>CAGCGGACCTCTATTCACAGGGTACG</td></tr><tr><td>c</td><td>AGGCCCTGGCATCCTCGATCATC</td></tr><tr><td>d</td><td>CTCAAGCAACAAGAAGGGCCTCATCAT</td></tr><tr><td colspan="2">Primers used in expression plasmid construction</td></tr><tr><td>MutM-1</td><td>GGAATTCCATATGATGCCTGAGCTTCCCGAG(NdeI)</td></tr><tr><td>MutM-2</td><td>CCGGAATTCTCCGACCCGAGGCACCC(EcoRI)</td></tr><tr><td>UvrA-1</td><td>GGAATTCCATATGTTGGCTGACCGTCTTGTTGTC(Nde I)</td></tr><tr><td>UvrA-2</td><td>CCG GAATTCTGTTGTTCGGTTAGGCGCTGA(EcoRI)</td></tr><tr><td>RpsC-1</td><td>GGAATTCCATATG GTGGGCCAGAAGATCAATCC (Nde I)</td></tr><tr><td>RpsC-2</td><td>CCGGAATTCTGAGCTCTCCGTGCTCTCG(EcoRI)</td></tr><tr><td>rna helicase-1</td><td>GGAATTCCATATG ATGACCTCGCAAGAACCGGATC (Nde I)</td></tr><tr><td>rna helicase-2</td><td>CCGGAATTCTCACTTCACCTTCCGGTGTG(EcoRI)</td></tr></table></body></html>

# 1.3耻垢分枝杆菌感受态细胞的制备[17-18]和电转

将新鲜保存的野生型耻垢分枝杆菌于7H10固体培养基上划线培养，3d后，挑取单菌落接种于 $5 \mathrm { m } \mathrm { \ m } \mathrm { \ m }$ 培养基(含有 ADC)中， $3 7 ^ { \circ } \mathrm { C }$ 振荡培养2d；按 $1 : 1 0 0$ 的比例将培养物接种于 $2 0 0 ~ \mathrm { m l } ~ \mathrm { 7 H 9 }$ 培养基(含有 ADC)中， $3 7 ^ { \circ } \mathrm { C }$ 过夜培养，至 ${ A _ { 6 0 0 } }$ 为0.6左右；将培养物于冰上放置 $3 0 \mathrm { m i n }$ ，然后 $4 ^ { \circ } \mathrm { C }$ $6 ~ 0 0 0 ~ \mathrm { r / m i n }$ 离心 $1 0 ~ \mathrm { m i n }$ 收集菌体；倒掉上清，将菌体用 $1 0 0 \mathrm { m l }$ 预先冰浴预冷的 $10 \%$ 无菌甘油重悬，于 $4 ^ { \circ } \mathrm { C } \ 6 \ 0 0 0 \ \mathrm { r / m i n }$ 离心 $1 0 ~ \mathrm { m i n }$ 收集菌体；重复清洗菌体3次，所用的 $10 \%$ 甘油体积依次减为原培养体积的1/4、1/8和1/10，最后加入 $1 0 \mathrm { m l }$ 预冷的$10 \%$ 甘油，混匀菌体后，以 $0 . 4 ~ \mathrm { m l / \Omega }$ 管进行分装，保存于 $- 8 0 ^ { \circ } \mathrm { C }$ 或立即使用.

将DNA加入 $4 0 0 \mu \mathrm { l }$ 的耻垢分枝杆菌感受态细胞中，冰上孵育 $1 0 \mathrm { m i n }$ ，然后转入电转杯中(冰上预冷)．擦净电转杯外壁上的水，然后电击，电击时参数设置为：电压 $2 . 5 \mathrm { k V }$ ，电阻 $1 0 0 0 \Omega$ ，电容$2 5 \mu \mathrm { F }$ ．电击完后，立即加入 $1 \mathrm { m l }$ 的LB或7H9(含有 ADC)液体培养基，冰上放置 $1 0 \mathrm { m i n }$ ： $3 7 ^ { \circ } \mathrm { C }$ 振荡培养 $ { 4 \mathrm { h } }$ ， $5 0 0 0 ~ \mathrm { r / m i n }$ 离心 $1 0 ~ \mathrm { { m i n } }$ ，去掉大部分上清，剩余 $1 0 0 \sim 2 0 0 ~ \mu \mathrm { l }$ 涂平板，使用LB固体培养基或7H10(含有 ADC)固体培养基(相应的抗性)培养 $3 \sim 5$ 天．然后挑取单克隆验证.

# 1.4 TAP纯化MutM蛋白

挑取新鲜的重组成功的单克隆 $M .$ smegmatisMC2155/MutM-TAP tag 接种于 ${ 5 } ~ \mathrm { m l }$ 的 ${ \mathrm { L B } } + { \mathrm { K a n } } +$ Hyg 培养基中， $3 7 ^ { \circ } \mathrm { C }$ 振荡培养长到饱和 $( 2 \sim 3$ 天)，接种于1L的 $_ \mathrm { L B + K a n }$ 培养基中， $3 7 ^ { \circ } \mathrm { C }$ 培养 $2 \sim 3 { \mathrm { d } }$ $\left( A _ { 6 0 0 } \sim 3 \right)$ ．收集菌体，用预冷的裂解缓冲液洗1次，再将菌体用预冷的 $5 0 \sim 1 0 0 ~ \mathrm { m l }$ 的裂解缓冲液重悬，加入蛋白酶抑制剂PMSF，使其终浓度为

$1 \mathrm { m m o l / L }$ ，进行超声破碎和高速离心，将上清转移至干净的新管中．吸取 $2 0 0 \mu \mathrm { l }$ 的IgG Sepharose 玻璃珠悬浮液，转入 $0 . 8 \ \mathrm { c m } \times 4 \ \mathrm { c m }$ 的Poly-Prep 柱子中，用 $1 0 \mathrm { m l }$ 裂解缓冲液洗3次．然后将细胞提取液上清转移到平衡好的柱中，重复过柱 $2 { \sim } 3$ 次.再用 $1 0 \mathrm { m l }$ 裂解缓冲液洗3次．接着用 $1 0 \mathrm { m l }$ TEV缓冲液洗2次，最后1次不要流的太干，用塑料小帽堵住出口．接着加入 $5 0 0 ~ \mu \mathrm { l }$ TEV缓冲液以及100UTEV蛋白酶，混匀， $4 ^ { \circ } \mathrm { C }$ 孵育过夜．次日从摇床取出柱子，静置 $1 0 \mathrm { m i n }$ 后，打开出口，用EP管收集流出液．在流出液中加入 $5 0 0 ~ \mu \mathrm { l }$ CBP结合缓冲液， $3 ~ { \mu \mathrm { l } } ~ 1 ~ \mathrm { m o l / L }$ 的 $\mathrm { C a C l } _ { 2 }$ 和已用CBP结合缓冲液平衡过的 $2 0 0 ~ \mu \mathrm { l }$ 钙调蛋白(calmodulin)玻璃珠,于 $4 ^ { \circ } \mathrm { C }$ 孵育 $^ { 2 \mathrm { ~ h ~ } }$ 后，用 $1 0 ~ \mathrm { m l } ~ \mathrm { C B P }$ 结合缓冲液洗3次，然后加入 $1 \mathrm { m l }$ CBP洗脱缓冲液洗脱结合的蛋白，分5次加入分开收集，每管 $2 0 0 ~ \mu \mathrm { l }$ ，通常洗脱峰出现在第2管和第3管.

# 1.5 银染与质谱鉴定

由于TAP纯化出来的蛋白质溶液体积较大，而且本身蛋白质浓度很低，所以一般在SDS-PAGE检测前需要先进行浓缩．可采用TCA(三氯乙酸)沉淀或者丙酮沉淀来浓缩蛋白，本次实验采用后一种方案，因为操作更简单，蛋白质损伤也较小．首先向洗脱的 $2 0 0 ~ \mu \mathrm { l }$ 蛋白质溶液中加入 $3 \sim 5$ 倍体积的冰预冷丙酮，混匀后， $- 2 0 ^ { \circ } \mathrm { C }$ 放置 $2 { \sim } 4$ h或过夜沉淀；蛋白质沉淀好后，于 $4 ^ { \circ } \mathrm { C } \ 1 6 \ 0 0 0 \ \mathrm { r / m i n }$ 离心$1 5 ~ \mathrm { m i n }$ ，用 $1 ~ \mathrm { m l }$ 预冷的丙酮洗蛋白沉淀2次．然后置于空气中干燥，去除丙酮后，加入 $1 0 ~ \mu \mathrm { l }$ 双蒸水，重悬后加入 $2 . 5 ~ { \mu 1 } ~ 6 \times$ 蛋白上样缓冲液，沸水煮样 $1 0 \mathrm { m i n }$ ．高速离心后上样，SDS-PAGE分离蛋白样品．用蛋白质银染试剂盒染胶．蛋白胶银染后，从中挖出差异条带，用胰酶酶解后，将获得的肽段用液质联用仪Maldi-tof质谱仪进行分析鉴定．最后把得到的肽段序列与NCBI耻垢分枝杆菌蛋白质序列数据库对比检索.

# 1.6 蛋白质表达纯化

# 1.6.1 His 标签融合蛋白的表达

分别挑取最新活化的表达菌株于 $5 \mathrm { m l }$ LB试管培养基中，加入相应的抗生素，于 $3 7 ^ { \circ } \mathrm { C }$ 、 $2 0 0 \mathrm { r / m i n }$ 振荡培养过夜．次日，按 $1 \%$ 接种量分别转接于$5 0 0 \mathrm { m l }$ 加入了抗生素的LB培养基中，继续 $3 7 ^ { \circ } \mathrm { C }$ 、$2 0 0 ~ \mathrm { r / m i n }$ 振荡培养．待菌液 ${ A _ { 6 0 0 } }$ 达到0.4时，加入诱导剂IPTG使其终浓度达到 $0 . 2 \ \mathrm { m m o / L }$ ，同时将菌液转移到 $1 6 ^ { \circ } \mathrm { C }$ 低温培养．诱导 $1 2 \sim 1 6 \mathrm { h }$ 后， $4 ^ { \circ } \mathrm { C }$ $4 5 0 0 \mathrm { r / m i n }$ 离心收集菌体，并用缓冲液 $\mathrm { A } ( 2 0 \mathrm { m m o l / L }$ Tris-HC1 $\mathfrak { p H } ~ 7 . 9$ ，500 mmol/L NaCl， 5 mmol/Limidazole)清洗1次，然后重悬于 $5 0 ~ \mathrm { m l }$ 缓冲液A中，超声破碎，以 $1 2 0 0 0 \mathrm { r / m i n }$ ，离心 $3 0 \mathrm { m i n }$ ，上清流经缓冲液A平衡的 $\mathrm { N i ^ { 2 + } { - } N T A }$ 亲和层析柱，然后依次用缓冲液A、B $( 2 0 \ \mathrm { m m o l / L }$ Tris-HCl pH 7.9,$5 0 0 \mathrm { m m o l / L } \mathrm { N a C l }$ ,60 mmol/L imidazole)、 $\mathrm { C } ( 2 0 \mathrm { m m o l } \mathrm { L }$ Tris-HCl $\mathrm { p H } 7 . 9$ ，500 mmol/L NaCl， $2 0 0 \ \mathrm { \ m m o l / L }$ imidazole)洗脱，根据蛋白质检测仪的读数收集洗脱物．SDS-PAGE检验纯度后用 $2 \mathrm { L }$ 透析缓冲液$( 2 0 \ \mathrm { m m o l / L }$ Tris-HCl， $\mathrm { p H } 7 . 9$ ， $\mathrm { N a C l ~ 1 5 0 ~ m m o l / L }$ $5 \%$ 甘油)进行透析．透析好的蛋白质样品用离心超滤管浓缩，在 $1 2 0 0 0 \mathrm { r / m i n }$ 离心 $1 5 \mathrm { m i n }$ 后，取上清保存.

# 1.6.2SBP 标签融合蛋白的纯化

SBP-tag亲和纯化系统的基本原理类似于众所周知的biotin和streptavidin之间的结合反应，SBP-标签是一种新的链霉亲和素结合肽，由38个氨基酸组成[19]，与 streptavidin 的解离常数为 $2 . 5 \mathrm { n m o l / L }$ 带有 SBP标签的蛋白可用固化 streptavidin进行纯化，洗脱条件非常温和，使用 $2 \mathrm { m m o l / L }$ 生物素即可将结合的SBP融合蛋白洗脱下来.

将 $E$ ，coli BL21/pET28a-sbp 和 $E$ coli BL21/pET28a-MutM-sbptag等菌株按照上面的方法进行诱导表达，离心收集菌体，用缓冲液D $\mathrm { 5 0 ~ m m o l / L }$ Tris $\mathrm { p H } 7 . 9$ ， $1 5 0 \mathrm { m m o l / L N a C l }$ ，1mmol/L EDTA)清洗菌体1次，然后重悬于 $5 0 \mathrm { m l }$ 缓冲液D中，超声破碎后，以 $1 2 \ 0 0 0 \ \mathrm { r / m i n }$ ，离心 $3 0 \mathrm { m i n }$ ，上清上样于经缓冲液D平衡的链霉亲和素琼脂糖beads层析柱．接着用10倍柱体积的缓冲液D洗柱3次．然后用3倍柱体积的缓冲液I $\vec { \Xi } ( 5 0 \ \mathrm { m m o l / L }$ Tris pH 7.9,$2 . 5 \mathrm { m m o l / L }$ desthiobiotin, 150 mmol/L NaCl, 1 mmol/LEDTA)洗脱目的蛋白并进行收集，将纯化的蛋白质进行透析、浓缩、SDS-PAGE检测和保存.

# 1.6.3 GST融合蛋白的纯化

按照1.6.1的方法对 $E .$ coli BL21/pGEX-6p-1-MutM进行培养和诱导表达．离心收集的菌体用$1 { \times } \mathrm { P B S }$ 清洗1次，然后重悬于 $3 0 ~ \mathrm { m l }$ 含 $0 . 1 \% ( v / v )$ Triton X-100的 $1 \times \mathrm { { P B S } }$ 中，超声破碎之后，$1 6 0 0 0 \mathrm { r / m i n }$ 离心 $3 0 \mathrm { m i n }$ ，取上清液与 $1 ~ \mathrm { m l }$ 处理好的glutathione-Sepharose 4B 柱材料混合， $4 ^ { \circ } \mathrm { C }$ 孵育$^ { \textrm { 1 h } }$ ．将样品以 $5 0 0 ~ \mathrm { r / m i n }$ 离心 $5 ~ \mathrm { m i n }$ ，稍静置，将上清转移走．用新鲜的PBST重悬柱料，在混合器孵育 $5 \mathrm { m i n }$ ，再次以 $5 0 0 ~ \mathrm { r / m i n }$ 离心 $5 \mathrm { { m i n } }$ ，去掉上清．如此重复3次后，将柱料转移到一个小型蛋白质纯化柱中．将配制好的洗脱液( $1 0 \mathrm { m m o l / L }$ 还原型谷胱甘肽溶液)加入到蛋白质纯化柱中，封闭出口，将其静置 $1 0 \mathrm { m i n }$ ，然后打开出口，收集流出液，即为目的蛋白GST-MutM.

# 1.7 Far western

将质谱鉴定的与MutM有相互作用的蛋白质以及作为阴性对照的BSA和GST进行梯度稀释，使每种蛋白质的终浓度分别为8、2、 $0 . 5 \mu \mathrm { m o l / L }$ 和0,按从左到右的顺序分别点样到硝酸纤维素膜上.将这个膜用溶液 $\mathrm { F } ( 2 5 \ \mathrm { m m o l / L }$ Tris-HC1 $\mathrm { p H } ~ 7 . 6$ $1 5 0 \mathrm { m m o l / L N a C l }$ ， $5 \% ( w / v )$ non-fat milk， $1 \mathrm { m m o l / L }$ EDTA)在室温下封阻 $^ { 2 \mathrm { ~ h ~ } }$ ，然后加入MutM-SBP蛋白液，使其终浓度为 $1 6 ~ \mathrm { \mu m o l / L }$ ，室温下孵育$^ \textrm { \scriptsize 1 h }$ ，分别用溶液E $( 2 5 \mathrm { \ m m o l / L }$ Tris-HCl pH 7.6,$1 5 0 \mathrm { m m o l } \mathrm { L N a C l }$ ， $0 . 0 5 \%$ Tween-20) 和不含Tween-20的溶液E各洗3次后，加入以PBS按 $1 : 3 0 0 0$ 稀释的碱性磷酸酶－链霉亲和素交联物(alkalinephosphatase conjugated strepavidin)，使酶和蛋白质通过 strepavidin 和 SBP 结合在一起，室温孵育1h后按照上述的方法洗膜6次．最后加入显色底物BCIP/NBT并且在 $3 7 ^ { \circ } \mathrm { C }$ 下显色，拍照.

# 1.8 GST pull-down

将GST-MutM与目的蛋白各取 $0 . 1 \ \mathrm { n m o l / L }$ ，加入到装有 $6 0 0 ~ \mu \mathrm { l }$ PBST的EP管中．同时，平行试验中将GST与目的蛋白各 $0 . 1 \mathrm { n m o l / L }$ 也混合孵育.将以上两个EP管于 $4 ^ { \circ } \mathrm { C }$ 孵育 $2 \mathrm { h }$ ，而后加入准备好的 glutathione-Sepharose 4B 柱材料，继续孵育1h.离心收集beads，加入 $6 0 0 ~ \mu \mathrm { l }$ PBST，充分混匀后，再次离心收集beads，重复4次．将beads与适量蛋白上样缓冲液混合， $1 0 0 ^ { \circ } \mathrm { C }$ 煮 $5 ~ \mathrm { m i n }$ ，离心$3 \mathrm { m i n }$ ．通过SDS-PAGE分离如上制备的蛋白样品，以抗His 标签的抗体为一抗，用Westernblotting 检测目的蛋白.

# 1.9 Western blotting

由于在基因组上MutM基因的C端整合了一段外源序列，基因组的部分结构可能发生改变．为了验证基因敲入菌株是否能正确表达带有TAP-tag的MutM蛋白，我们利用抗TAP-tag的抗体检测MutM和TAPtag融合表达情况.

挑取新鲜的已经通过PCR验证MutM基因 $3 ^ { \prime }$ 端成功整合了TAP-tag的单菌落，接种于 $5 { \mathrm { ~ m l ~ L B + } }$ $\mathrm { K a n } { + } \mathrm { H y g }$ 培养基中， $3 7 ^ { \circ } \mathrm { C }$ 振荡培养到饱和，离心收集菌体，加入 $1 0 0 \mu \mathrm { l }$ 蛋白缓冲液和 $2 0 ~ \mu \mathrm { l }$ 蛋白上样缓冲液，煮沸 $1 0 \mathrm { m i n }$ ，高速离心后，吸取 $1 0 ~ \mu \mathrm { l }$ 上样，SDS-PAGE分离样品．然后利用半干转膜仪将 SDS-PAGE 胶上的蛋白转移到硝酸纤维素(NC)膜上，电压 $1 5 { \mathrm { ~ V ~ } }$ ，转膜 $4 0 ~ \mathrm { m i n }$ ．将转印好的NC膜转移到含有 $5 \%$ 脱脂奶粉的封闭缓冲液中，室温封闭 $^ \textrm { \scriptsize 1 h }$ 或 $4 ^ { \circ } \mathrm { C }$ 封闭过夜．用PBST洗膜3次，每次 $5 \mathrm { m i n }$ ．洗好后置于杂交带中，加入 $1 : \ 2 0 0 0$ 稀释的一抗然后封上口，杂交带放置摇床上， $4 ^ { \circ } \mathrm { C }$ 过夜孵育．接着用PBST洗膜5次，每次 $5 ~ \mathrm { m i n }$ ，然后加入 $1 : 5 0 0 0$ 稀释的二抗，室温孵育 $1 \sim 2 \mathrm { ~ h ~ }$ ：接着用PBST洗膜5次，每次 $5 \mathrm { m i n }$ ．然后用吸样器吸取 $1 : 1$ 配置好的化学显色底物 $0 . 5 \sim 1 ~ \mathrm { m l }$ ，均匀地涂在膜上转印蛋白的一面．然后置于暗室用压片盒压片曝光，曝光时间长短根据信号强弱而定，一般3s至 $1 \mathrm { m i n }$ 左右，底片曝光后置于显影液中1min左右，取出放在水中轻轻漂洗一下，然后置于定影液中 $1 \mathrm { m i n }$ 左右，取出用水冲洗干净，晾干保存，做标记并拍照.

# 2结果与分析

# 2.1在基因组上MutM基因的C 端敲入TAP-tag片段

以耻垢分枝杆菌基因组为模板成功扩增出MutM基因 $3 ^ { \prime }$ 端307bp的DNA区段，以pBS1539质粒为模板扩增出TAP标签编码基因，大小约为$5 5 2 ~ \mathrm { b p }$ ，通过overlapPCR技术将二者连接起来获得up-TAP片段，再经过酶切连接的方式将up-TAP连接到载体pET20b上，形成重组质粒pET20b-up-TAP，我们通过单双酶切(图2a)和测序验证构建成功．然后，通过酶切连接的方法把MutM基因的 ${ \boldsymbol { 5 } } ^ { \prime }$ 端 $3 0 0 \mathrm { b p }$ 非编码区片段和 $H y g$ 基因依次连接到pET20b-up-TAP重组质粒上，最终获得含有敲入片段的重组质粒pET20b-up-TAP-Hygdown(图2b,c)．最后经过PCR扩增或者双酶切的方法获得TAP标签敲入基因组所需的cassette(图2d)，并作胶回收处理．接着通过电击转化将回收到的cassete转入带有重组工程系统的耻垢分枝杆菌感受态细胞内，将TAP-tag整合到耻垢分枝杆菌基因组上MutM基因的 $3 ^ { \prime }$ 端.

![](images/b5f37d467d93f4905ebdc93f0dcb132e712ea5e616b77bef91d55c4b6ff05b63.jpg)  
Fig.2Construction of a plasmid containing the TAP tag knock-in cassette

(a)Single digestion,double digestion and PCR of the pET20b/up-TAP recombinant plasmid.Lane $\boldsymbol { I }$ ，Marker1;Lane 2,Hind II digestion of pET20b/up-TAP;LnRfpbpA;Lane4HdnddigestiooEbp-A;ne5,arker2.(b)gedigio double digestion and PCR of the pET2Ob/up-TAP-down recombinant plasmid.Lane $\boldsymbol { I }$ ,Marker1;Lane 2,XhoI digestion of pET20b/up-TAP-down; Lane 3,Xho I and Not I double digestion of $\mathsf { p E T } 2 0 \mathsf { b } / u p$ -TA P-down; Lane 4,PCR of $\mathsf { p E T } 2 0 \mathsf { b } / u p$ -TAP-down.(c) Single digestion,double digestion and PCRofthepETOb/up-TAPHygdoecombinantplasmid.Lane1,Markr1;Lane2HndIdgestoofOb/up-TAPHygdo;an, HindndotIdubledigesib-Hdo;Ln4ofbHdo.dCRofcea Marker; Lane 2,PCR of knock-in cassette.

# 2.2PCR 和Western blot 验证TAP-tag 标签的敲入

为确保单克隆重组成功，我们利用PCR技术对这些重组子进行DNA水平上的验证．如图3a所示，共设计了2对引物，其中1对的1条引物a来自同源臂外侧，另1条引物b来自TAP-tag片段内部，只有整合了TAP-tag 的重组子才能扩增出相应大小的条带，而野生型菌是无法扩增出条带的；同时，利用另外1对引物验证MutM基因的3'端300bp非编码区片段是否同源重组成功，其中1条引物c来自 $H y g$ 基因内部，另1条引物d来自MutM基因的 $3 ^ { \prime }$ 端 $3 0 0 \mathrm { b p }$ 非编码区片段外侧，也是只有整合了TAP-tag 的重组子才能扩增出相应大小的条带，而野生型菌是无法扩增出条带的．在图 3b中的条带大小正好验证了这一结果，证明成功地将TAP-tag片段敲入到基因组上MutM基因的$3 ^ { \prime }$ 端.

由于在基因组上MutM基因的C端整合进去了一段外源序列，基因组的部分结构可能发生改变从而影响蛋白质表达．为了验证基因敲入菌株是否能正确表达融合了TAP-tag的MutM蛋白，我们利用抗TAP-tag 的抗体进行了Western blot 检测．从图3c 中可见，重组子能够表达带有TAP-tag 标签的MutM蛋白，而在含有pSMT3-TAPtag质粒的耻垢分枝杆菌中只能检测到TAP-tag．实验结果表明MutM蛋白融合有TAP标签可以获得正确表达.

![](images/f34285b5ac5dd71d930963b04ec1085e8ab898ce9965cfe0ce8ad4c5432133b0.jpg)  
Fig.3Identification of M. smegmatis strains with a TAP tag knocked into the C terminal of mutM by PCR and Western blotting

(a)PCRprimersusedforerifngM.smegisstrasithocked-iAtag.ColosereadbCusinipresd(o productforwildtypeM.smegmatis,914bpforM.smegmatisstraiswithaknocked-inTAPtag)orprimerscndd(noproductforwildtype M.smegmatis,556bpforM.smegmatis strains withaknocked-inTAPtag).(b)PCRanalysisof wildtypeM.smegmatisand $M$ 、s me gmatis strains with knocked-in TAP tags using two pairs of specific primers. Lane $\boldsymbol { I }$ ,DNA marker; Line 2 and 3,PCR analysis of two $M .$ ，smegmatis strains with knocked-in TAPtagsusingprimersaandb;Lne4and5,CalysisoftoM.smegmtistraisithakocked-inTPtagusingprmersndd;Lane $\boldsymbol { \mathscr { \sigma } }$ ,PCR analysisofwildtypsmetissgprirsandb;aneCalysisfildemegtisusigprescdd.(cWsteotf MutM-TAPtagexpeiiMsmets-AtgdMsmgtisrsitckd-itagusiiTAtgatisLa 1,M.smegmatis/pMST3-TAP tag; Lane 1 and 2,two M. smegmatis strains with knocked-in TAP tags.

# 2.3MutM蛋白串联亲和纯化及互作蛋白的质谱鉴定

本研究所使用的TAPtag包含有ProteinA和CBP 标签两部分，二者用TEV酶切位点隔开[4].先用IgGSepharose 玻璃珠材料结合标签上的

ProteinA蛋白，经过TEV蛋白酶切割去掉ProteinA标签后，再用和calmodulin玻璃珠材料结合剩下的标签，经过洗脱后，得到最终的结合蛋白，经过SDS-PAGE分离后，再用银染方法显色(图4)，结果显示，与对照组相比有明显差异的条带．选取银

![](images/94f5e97a79dc0bff102be43671bdeff0874b245085d490294d5fc75211f48564.jpg)  
Fig.4TAP purification of MutM-TAP(TAP-tagat the C-terminus) byaffinity chromatography with Protein A and calmodulin

ProteincomplexeswerevisualizedbysilverstainingafterseparationbySDS-PAGE.Severalspecificbandswereexcisedandsubjectedto spectrometry. (a) TAP purified proteins after silver staining.Lane $I$ ,Protein molecular weight marker;Lane 2,TAP-tagged MutM complex.(b) TAP purified proteins after silver staining (Control).Lane $I$ ,Protein molecular mass marker;Lane 2,Control- TAP tag alone.

染后的差异蛋白条带，经过胰酶降解后，进行质谱鉴定(表3)．结果显示，除了靶蛋白MutM，还鉴定出5种至少含有2条酶解片段的蛋白(图 4b)，分别为UvrA(excinuclease ABC subunit A)、DEAD-box rna helicase（编码基因为 MSMEG_5042)、D-amino-aciddehydrogenase(编码基因为MSMEG_6291)、RpsC（30Sribosomalprotein S3，编码基因为MSMEG_1442)和RubonucleaseII(编码基因为MSMEG_2418)．这些蛋白中UvrA主要参与核苷酸切除 修 复 途 径，DEAD-box rna helicase和Rubonuclease I主要参与RNA的代谢，D-amino-aciddehydrogenase主要参与氨基酸代谢，RpsC是核糖体16S亚基的组成部分．它们与MutM相互作用的机制都需要进一步研究.

Table 3Peptides identified by mass spectrometry   

<html><body><table><tr><td>Protein</td><td>Peptide</td></tr><tr><td>DEAD-box rna helicase</td><td>K.YLHDPVEVTVK.A</td></tr><tr><td>(ATP-dependent rna helicase,dead/deah box</td><td>R.NEFGHITIR.L</td></tr><tr><td>family protein[Mycobacterium smegmatis str.</td><td>R.SGHAVLFVTPR.E</td></tr><tr><td>MC2 155])</td><td>K.VGPGHIVGAIANEGGLHR.N</td></tr><tr><td rowspan="9">Ribonuclease II [Mycobacterium sme gmatis str. MC2 155]</td><td>R.ISGVLINLQPDRGPR.R</td></tr><tr><td>R.ISGVLINLQPDR.G</td></tr><tr><td>R.LDYSLVELPEKLPK.K</td></tr><tr><td>K.TAAFAIPILSK.I</td></tr><tr><td>R.SYSYENGGLPTNER.L</td></tr><tr><td>K.SSLQELTAAR.G</td></tr><tr><td>K.LRASIVNTQALADVGR.G</td></tr><tr><td>R.ASIVNTQALADVGR.G</td></tr><tr><td>R.GLTDEGLGAHLFLGKGEENSGGADK.S</td></tr><tr><td>D-amino-acid dehydrogenase [Mycobacterium</td><td>R.GLTDEGLGAHLFLGK.G</td></tr><tr><td></td><td>R.MADLGQDVK.F</td></tr><tr><td>smegmatis str.MC2 155]</td><td>R.GVDVTVVDR.T</td></tr><tr><td></td><td>R.TGEVLDVQPSKPGVR.I</td></tr><tr><td></td><td>R.FVHALADAVVAR.G</td></tr><tr><td></td><td>R.GYSFTVPVDRPVPTPIYLPDAR.V</td></tr><tr><td>RpsC</td><td>R.ELAAAAPASDRPR.R</td></tr><tr><td>(30S ribosomal protein S3 [Mycob acterium</td><td>R.KLLATGLER.A</td></tr><tr><td>smegmatis str．MC2155])</td><td></td></tr><tr><td>UvrA</td><td>R.SNPATYTGVFDKIR.S</td></tr><tr><td>(Excinuclease ABC subunit A[Mycobacterium</td><td>R.STVGTITEVYDYLR.L</td></tr><tr><td>smegmatis str．MC2155])</td><td></td></tr></table></body></html>

# 2.4Far western 和 GST pull-down 验证 MutM与质谱鉴定的蛋白质具有直接的相互作用

我们将鉴定的可能与MutM相互作用的蛋白质进行了克隆、表达和纯化，其中D-amino-aciddehydrogenase 和Rubonuclease II为不可溶性表达，UvrA、DEAD-boxrnahelicase和RpsC 都获得了可溶性蛋白．将SBP标签和GST标签分别融合到MutM蛋白的C端和N端，并进行表达纯化，最后用Far western 和 GST pull-down 方法对UvrA、

DEAD-boxrnahelicase、RpsC与MutM的相互作用进行了验证．Farwestern实验结果显示，随着3种蛋白质浓度的降低，结合MutM-SBP的量逐渐减少，作为对照，BSA和SBP标签都不能结合SBP-MutM（图5)，说 明UvrA、DEAD-box rnahelicase、RpsC和MutM之间存在着直接的相互作用．GSTpull-down 实验结果显示GST-MutM蛋白可以钓出 UvrA、DEAD-box rna helicase 和 RpsC,而GST蛋白却不能钓出任何蛋白(图6)，说明

UvrA、DEAD-box rna helicase、RpsC 和 MutM 确实有直接的特异的相互作用.

![](images/547ffbc2158c83c1a1ac0cfbc7b332ebd2d22e649cf20f99f39a7a8d2f2e73c7.jpg)  
Fig.5Far western analysis of interactions between MutM andUvrA,DEAD-box rna helicase and RpsC

UvrA,DEAD-box rna helicase,RpsC and BSA or GST were applied to a nitrocellulose membrane at different concentrations $( 8 \mathrm { \sim } 0 ~ \mu \mathrm { m o l / L }$ ,from left to right) and then incubated with MutM-SBP.BSA and GST were set as negative controls.MutM-SBP bound to the membrane was detected by sequentially incubating with a streptavidin alkaline phosphatase conjugate and BCIP/NBT. $l \colon { 8 } \ \mu \mathrm { m o l / L }$ ；2: $2 \ \mu \mathrm { m o l / L }$ ；3: $0 . 5 ~ \mathrm { \mu m o l / L } ; \mathrm { \it 4 : 0 }$

![](images/69d2b8150febe549023866ccae086873dbab4a1257aee0d079b897e8fd7b19a8.jpg)  
Fig.6GSTpull-downanalysisofinteractions between MutM andUvrA,DEAD-box rna Helicase and RpsC in vitro

Equimolar amounts of His-UvrA,His-DEAD-box rna helicase or His-RpsC combined with GST-MutM were used for the pull-down assay. GST was used as a negative control. The mixture was incubated for $^ \textrm { \scriptsize 1 h }$ at $1 6 ^ { \circ } \mathrm { C }$ ,and then purified by GST affinity. Samples were examined by Westernblottingusingananti-Histagantibody.His-UvrA, His-DEAD-box rna helicase and His-RpsC were used as the input in (a) $\sim ( \mathrm { c ) }$ ，respectively.(a) In vitro interactions between MutM and UvrA detected by the GST pull-down assay.(b) In vitro interactions between MutM and DEAD-box rna helicase detected in the GST pull-down assay. (c) GST pull-down analysis of the interaction between MutM and RpsC in vitro.

# 3讨论

本研究利用最近建立的分枝杆菌重组系统在基因组水平上将TAPtag（含有串联的ProteinA和CBP标签)的编码序列插入到MutM基因的 $3 ^ { \prime }$ 端，使它们在本底水平上融合表达，利用ProteinA和CBP两步纯化的方法将MutM和与之有相互作用的蛋白质纯化出来，并通过SDS-PAGE分离、银染显色和质谱鉴定，共鉴定出5种蛋白，即UvrA、DEAD-box rna helicase、D-amino-acid dehydrogenase、RpsC和RubonucleaseI，对这些蛋白质进行表达纯化，只有UvrA、RpsC、DEAD-box rna helicase获得了可溶性表达．最后利用Farwestern和GSTpull-down两种方法证实了这3种蛋白与MutM具有直接的相互作用.

UvrA是原核生物核苷酸切除修复系统 (NER)中一种具有错误识别和部分切除活性的ATP 水解酶，可招募UvrB到DNA损伤部位[20]．NER途径主要对具有化学性质和结构多样性的大体积损伤进行修复，例如由紫外线照射产生的胸腺嘧啶二聚体[21-22]．在啤酒酵母中，MMR 和 NER可以协同作用参与UV造成的损伤[23]．在粟酒裂殖酵母研究中发现，C/C 错配的修复必须在MMR和NER共同参与下才能完成[24]．结合无论是原核生物中的MutM，还是真核生物中的OGG1，都可以结合C/C 错配[12]，可以推测C/C错配的修复可能涉及到MMR、NER和BER3个系统的共同参与．但是分枝杆菌中至今仍未发现错配修复系统(MMR)的存在[25]，可以推测在分枝杆菌缺少MMR修复途径的情况下，BER途径和NER途径可以协同作用完成一些损伤的修复．已有报道[2，大肠杆菌中MutM可以和UvrA相互作用并参与到UVC（短波紫外线)损伤修复中．由于分枝杆菌基因组的GC含量较高，为 $6 5 \%$ 左右，产生C/C 错配的几率较其他物种大得多，所以对于C/C错配的修复至关重要．耻垢分枝杆菌中MutM与UvrA的相互作用是否像大肠杆菌中一样参与UVC的修复，同时也可以一起完成对C/C错配的修复，这些问题都值得进一步深入研究.

DEAD-boxRNA解旋酶是一个依赖ATP的RNA解旋酶大家族，广泛地存在于从原核生物的细菌到真核生物的酵母、植物和动物中，参与RNA转录、前体mRNA剪切、核质运输、蛋白质翻译、RNA降解等重要的生命活动．通常认为

RNA如果掺入DNA就会导致DNA双螺旋的伤害性破坏，促进基因组不稳定．但是最近研究发现，在一种常见的芽殖酵母细胞内RNA可充当模板来修复破坏性极大的DNA损伤，DNA双链断裂[];人体中DDX39DEAD-boxrnahelicase在维持基因组的稳定性中发挥着重要的作用[28]．我们发现的DEAD-boxrnahelicase与作为底物比较广泛的MutM的相互作用是否参与到一些损伤的修复途径还需要进一步深入研究．由于耻垢分枝杆菌中RubonucleaseⅢ不可溶，所以无法判断其是直接与MutM相互作用还是被DEAD-boxRNA解旋酶间接地垂钓出来．总之，RubonucleaseⅢ与MutM的相互作用还有待进一步确定.

30SribosomalproteinS3是原核生物核糖体小亚基的组成蛋白．已有文献报道，人体中对应的蛋白RPS3对8-oxoG具有结合活性，并且与MutM人体中的同源蛋白OGG1存在相互作用[2，说明RpsC(Rps3)不仅是一个核糖体组成蛋白，而且可以参与到对DNA损伤修复中，影响修复效率．由此可以推测分枝杆菌中RpsC与MutM可能一起完成对某些损伤的修复，但还有待进一步研究．截止到目前，D-amino-acid dehydrogenase 没有参与损伤修复的报道，因此D-amino-acid dehydrogenase 与MutM的相互作用还需要进一步的验证和研究.

综上所述，本研究通过将TAP标签融合到MutM的C端，利用串联亲和纯化的方法成功地对MutM相互作用的蛋白进行了分离和质谱鉴定，并通过Far western 和GST pull-down 的方法对UvrA、RpsC和DEAD-boxrnahelicase 进行了验证．我们的发现将为进一步深入研究MutM在许多损伤修复中的作用机制提供新的思路和切入点.

# 参考文献

[1]Lindahl T.Instability and decay of the primary structure of DNA. Nature,1993,362(6422): 709-715   
[2]Zharkov D O.Base excision DNA repair.Cell Mol Life Sci, 2008, 65(10): 1544-1565   
[3]Baute J,Depicker A.Base excision repair and its role in maintaining genome stability. Crit Rev Biochem Mol Biol,2008,43(4): 239-276   
[4] Cadet J,Berger M,Douki T,et al.Oxidative damage to DNA: formation,measurement,and biological significance.Rev Physiol Biochem Pharmacol,1997,131:1-87   
[5]Frommol/Le JC,Banerjee A，Verdine G L.DNA glycosylase recognition and catalysis. Curr Opin Struct Biol,2004,14(1): 43-49   
[6] Zharkov D O,Ishchenko A A,DouglasK T,et al.Recognition of damaged DNA by Escherichia coli Fpg protein:insights from structural and kinetic data. Mutat Res,2003,531(1-2): 141-156   
[7]Tajiri T,Maki H, Sekiguchi M. Functional cooperation of MutT, MutM and MutY proteins in preventing mutations caused by spontaneous oxidation of guanine nucleotide in Escherichia coli. Mutat Res,1995,336(3): 257-267   
[8]Zhang Q M, Miyabe I, Matsumoto Y,et al. Identification of repair enzymes for 5-formyluracil in DNA.Nth,Nei,and MutM proteins of Escherichia coli.JBiol Chem,2000,275(45): 35471-35477   
[9]Leipold MD, Muller JG,Burrows C J,et al.Removal of hydantoin products of 8-oxoguanine oxidation by the Escherichia coli DNA repair enzyme,FPG.Biochemistry,2000,39(48): 14984-14992   
[10] Onda M,Hanada K,Kawachi H,et dl.Escherichia coli mutM suppresses illegitimate recombination induced by oxidative stress. Genetics,1999,151(2): 439-446   
[11] Coste F,Ober M, Carell T,et al.Structural basis for the recognition ofthe FapydG lesion(2,6-diamino-4-hydroxy-5-formamidopyrimidine) by formamidopyrimidine-DNA glycosylase.J Biol Chem. 2004, 279(42): 44074-44083   
[12] Nakahara T, Zhang Q M, Hashiguchi K,et al.Identification of proteins of Escherichia coli and Saccharomyces cerevisiae that specifically bind to $\mathrm { C / C }$ mismatches in DNA. Nucleic Acids Res, 2000,28(13): 2551-2556   
[13] Fleck O,Lehmann E,Schar P,et al. Involvement of nucleotideexcision repair in msh2 pmsl-independent mismatch repair. Nat Genet,1999,21(3): 314-317   
[14] Springer B,Sander P,Sedlacek L,et al.Lack of mismatch correction facilitates genome evolution in Mycob acteria,2004, 53(6): 1601-1609   
[15]Rigaut G,Shevchenko A，Rutz B,et al.A generic protein purification method for protein complex characterization and proteome exploration. Nat Biotechnol,1999,17(10): 1030-1032   
[16] van Kessel JC,Hatfull G F.Recombineering in Mycobacterium tuberculosis.Nat Methods,2007,4(2): 147-152   
[17]Parish T,Stoker N G.Electroporation of mycobacteria.Methods Mol Biol,1998,101: 129-144   
[18] Goude R,Parish T.Electroporation of mycobacteria.J Vis Exp, 2008(15): pii761   
[19] Keefe A D, Wilson D S,Seelig B,et al. One-step purification of recombinant proteins using a nanomolar-affinity streptavidinbinding peptide,the SBP-Tag.Protein Expr Purif,2001,23 (3): 440-446   
[20] Truglio J J,Croteau D L,Van Houten B,et al.Prokaryotic nucleotide excision repair: the UvrABC system.Chem Rev,2006, 106(2): 233-252   
[21] Snowden A,Kow Y W,Van Houten B.Damage repertoire of the Escherichia coli UvrABC nuclease complex includes abasic sites, base-damage analogues,and lesions containing adjacent $5 ^ { \prime }$ or $3 ^ { \prime }$ nicks.Biochemistry,1990,29(31): 7251-7259   
[22] Sancar A.DNA excision repair. Annu Rev Biochem,1996, 65: 43-81   
[23] Bertrand P,Tishkoff D X,Filosi N,et $^ { a l }$ Physical interaction between components of DNA mismatch repair and nucleotide excision repair.Proc Natl Acad Sci USA,1998,95(24):14278- 14283   
[24]Fleck O,Lehmann E,Schar P,et al.Involvement of nucleotideexcision repair in msh2 pmsl-independent mismatch repair.Nat Genet,1999,21(3): 314-317   
[25]Mizrahi V,Andersen S J.DNA repair in Mycobacterium tuberculosis.What have we learnt from the genome sequence?.Mol Microbiol,1998,29(6):1331-1339   
[26] Silva-Junior A C,Asad L M,Felzenszwalb I,et al.The role of Fpg protein in UVC-induced DNA lesions. Redoxreport: communications in free radical research,2012,17:95-100   
[27]KeskinH, ShenY,HuangF,et al.Transcript-RNA-templated DNA recombination and repair.Nature,2014,515(7527):436-439   
[28] Yoo HH,ChungIK.Requirement ofDDX39 DEAD box RNA helicase for genome integrity and telomere protection.Aging Cell, 2011,10(4): 557-571   
[29]Hegde V,Wang M,Deutsch WA.Human ribosomal protein S3 interacts with DNA base excision repair proteins hAPE/Ref-1 and hOGG1. Biochemistry,2004,43(44): 14211-14217

# MutM Interaction Partners Detected in Mycobacterium smegmatis by Tandem Affinity Purification\*

FAN Shang-Hual2), ZHOU Ying², ZHANG Hong-Tai², Joy Fleming², YU Zi-Niu1, ZHANG Xian- $\mathrm { E n } ^ { 2 ) ^ { * * } }$ ,BI Li-Jun2)\*\* （ $^ { 1 ) }$ StateKeyLbtucolfedzueUesi; 2)CAS Laboratory of RNA Biologyand National Laboratory of Biomacromolecules,Institute of Biophysics, Chinese Academy of Sciences,Beijing 10o101,China)

AbstractMutM (Formamidopyrimidine-DNA glycosylase,Fpg),a bifunctional base excision repair enzyme (DNA glycosylase/AP lyase),is involved in the repair of many kinds of DNA damage, including the formation of 8-oxoguanine, 5-formyluracil, and $\mathrm { C / C }$ mismatches, through recognizing DNA damage and removing damaged bases.The mechanisms of MutM involvement, however,with the exception of 8-oxoG,are poorly understood. Here, we identified proteins which interact with MutM in Mycobacterium smegmatis using methods of tandem afnity purification and massspectrometry and used Far-western and GST pull-down analysis to validate the interactions between MutM and DEAD-box ma helicase,RpsC,and UvrA. Results demonstrated that tandem affinity purification is a suitable method for identifying MutM interacting proteinsand provided insights into the mechanism by which MutM is involved in DNA damage repair.

Key wordsMycobacterium sme gmatis,BER,MutM,TAP DOI: 10.16476/j.pibb.2015.0065