# 基于5993个核基因的被子植物系统发育关系研究

金鑫12，程书1,2，杨拓³，余慷1,²，段肖霞1,4，倪雪梅1,4，李世明1,2，张耕耘1,4\*（1.深圳华大生命科学研究院，广东 深圳 518083；2.深圳市华大农业应用研究院，广东 深圳518120；3．国家基因库，广东 深圳518120；4.基因组学农业部重点实验室，广东 深圳 518083）

摘要：系统发育关系的构建对被子植物分类及进化研究非常重要。长期以来，被子植物系统发育的研究，大多使用质体基因、线粒体基因或少数保守的单拷贝核基因。本研究从已注释基因组或转录组中搜集88种被子植物（包含58目）的核基因集；通过对其进行同源基因聚类及去旁系同源基因，获得了5993个一对一的直系同源基因家族（即对于每个基因家族，每种植物最多一条序列，最少包含 50个物种)；使用截取各种不同数目基因集的 DNA或氨基酸序列，采用串联法（concatenation）和溯祖法（coalescence），共构建了20 棵进化树。比较这些进化树，虽然大部分结果支持APGIV中描述的被子植物主要支系之间的关系（（真双子叶植物，单子叶植物)，木兰类植物)，但真双子叶植物内部各目分支的演化关系与APGIV 有一个很大的不同，即本研究认为檀香目和石竹目是蔷薇类植物的姊妹群。基于这些进化树，估算了被子植物各目分支的分化时间，结果表明被子植物的起源时间为237.78 百万年前（ $9 5 \%$ 置信区间为202.6\~278.08)，与主流观点认为的 225\~240 百万年前一致。本研究为构建进化树提供了一种可行性策略，这种方法允许使用基因数目更多而计算速度更快。

关键词：系统发育关系，被子植物，核基因，同源基因聚类，串联法，溯祖法，分化时间中图分类号：Q949.4 文献标识码：A

# Reconstruction of angiosperm phylogeny based on 5 993

# nuclear genes

JIN Xin12,CHENG Shu1,2, YANG Tuo³, YU Kang1,2, DUAN Xiaoxia1,4, NI Xuemei14,LI Shiming1,2， ZHANG Gengyun1,4\* (1.BGI-Shenzhen,Shenzhen 518083,Guangdong,China;2.BGI Institute of Applied Agriculture,Shenzhen 518120, Guangdong, China; 3. China National Gene Bank, Shenzhen 518120, Guangdong, China; 4. Key

Abstract: Construction of phylogeny is important to classification and research of angiosperms. For a long time,angiosperm phylogeny has been analysed using plastid genes, mitochondrial genes or a few conserved single-copy nuclear genes.Here, we collected nuclear gene sets of 88 species of angiosperm (contains 58 orders) from annotated genomes or transcriptomes. By using a combined homology- and phylogeny tree-based approach, we obtained a total of 5 993 one-to-one ortholog groups (one sequence of each species for each ortholog group),each of which was represented by at least 5O species. Then, a total of 2O species trees were reconstructed using different combination of reconstruction methods (concatenation-based and coalescence-based) and sequence type (nucleotide or amino acid) for gene data sets with different gene occupancy values. Most of the resulting topologies support the relationships of the major clades of angiosperm as described in APG IV, but present different deep relationships among major clades in eudicots phylogeny such as the placement of Santalales and Caryophyllales as sisters to Rosids. We estimated the divergence times of the major clades of angiosperm and concluded that the origin of angiosperm is about 237.78 million years ago( $9 5 \%$ confidence interval is 202.6\~278.08),which is in accordance with the previously accepted $2 2 5 \sim 2 4 0$ million years ago. This study provided an effcient strategy for building phylogenetic trees using thousands of genes with ultrafast calculation.

Key words: phylogeny， angiosperms， nuclear genes， ortholog inference， concatenation,coalescence, divergence time

系统发育树的正确构建对植物分类及进化研究非常重要。进化树构建的准确度主要受以下因素的影响。其一，所使用的数据集的种类及大小。不仅使用形态性状数据、质体基因、线粒体基因及核基因序列建立的进化树不一样（Endress& Doyle,2009;Ruhfel etal.,2014;Soltis et al.,2011; Zeng etal.,2014)，使用全长核酸序列、或仅使用基因密码子某个位点的核酸序列及氨基酸序列所构建的进化树也有所不同（Wickett etal.,2014)。其二，构建树的方法及模型。方法有串联法（concatenation）和祖法（coalescence)：串联法是将所有基因串联作为一个整体，使用软件RAxML（Stamatakis,2014）或 iqtree（Nguyen et al.,2015）构建系统发育树；溯祖法是先对每个基因建树，再使用软件 ASTRAL（Zhang et al.,2017）建立所有基因树的共有树（Wickett et al.,2014)。而构建系统发育树使用的模型更是多种多样，如核酸模型GTR、HKY、JC、F81、K2P、K3P、K81uf 等，蛋白质模型 LG、Poisson、cpREV、mtREV、Dayhoff、mtMAM、JTT、WAG 等（Nguyen etal.,2015）。

被子植物是植物界最高等且种类最多的一类，它们在地球上占据着绝对优势。现在已报道被子植物有352 000 种（http://www.theplantlist.org/)，属于416科和64目，各目之间的演化关系一直是研究的热点和争论的焦点。被子植物除了最基部的三个目：无油樟目（Amborellales）、睡莲目（Amborellales）和木兰藤目（Austrobaileyales），又称ANITA组，其余的（ $9 9 . 9 5 \%$ ）可以分为五类：木兰类植物（magnoliids）、单子叶植物（monocots）、真双子叶植物（eudicots）、金栗兰科（Chloranthaceae）和金鱼藻科（Ceratophyllceae）。这五类的系统演化拓扑关系一直存在争论，Zeng etal.(2014)总结了已经发表的五种主要的拓扑关系（图1:A-E）,其中A是最主流的，也是APGIV（THE ANGIOSPERMPHYLOGENYGROUP,2016）的拓扑结构。Soltie etal.(2011)使用17个基因串联（包括质体基因、线粒体基因和核基因）为640种植物构建的系统发育进化树，和Ruhfeletal.(2014)使用78个质体基因串联为360 种植物构建的进化树，支持主流A拓扑结构。Wicketet al. (2014)使用 674个核基因串联为92 种植物构建的进化树，和 Zeng et al.(2014)使用 59 个核基因串联为 61种植物构建的进化树，支持B拓扑结构。除此之外，Qiu etal.(2010)使用4个线粒体基因为380 种植物构建的进化树，支持C拓扑结构；Endress ＆Doyle(2009)使用形态性状构建的进化树，支持D拓扑结构；Zhang etal.(2012)使用5个核基因为91种植物构建的进化树，支持E拓扑结构。

去掉金栗兰科和金鱼藻科后，单子叶植物、木兰类植物、真双子叶植物之间的系统发育关系有三种：((真双子叶植物，单子叶植物),木兰类植物);((真双子叶植物，木兰类植物)，单子叶植物)；（（单子叶植物，木兰类植物)，真双子叶植物)。Luet al. (2018)使用4个质体基因和1个线粒体基因分析了5864种中国被子植物（几乎包括所有中国地区被子植物）的系统发育关系，其构建的进化树支持拓扑结构((真双子叶植物，单子叶植物),木兰类植物)。Chen etal.(2019)发布了木兰类植物鹅掌楸（Liriodendron）基因组，使用其 502个核基因及溯祖法为18种植物构建的进化树，同样支持拓扑结构（（真双子叶植物，单子叶植物)，木兰类植物)。Chaw etal.(2019)发布了另一个木兰类植物牛樟（stout camphor tree）基因组,使用其211个核基因为13种植物构建的进化树，支持拓扑结构（（真双子叶植物，木兰类植物)，单子叶植物)。Liet al.(2019)使用 2881种被子植物的质体基因组的80个基因重建了被子植物高分辨率的系统发育树，支持拓扑结构（（真双子叶植物，单子叶植物)，木兰类植物)。从上述已有的研究中，我们发现，使用核基因串联法建立的进化树基本都支持拓扑结构（（真双子叶植物，木兰类植物)，单子叶植物)，使用核基因溯组法、质体和线粒体基因建立的进化树基本都支持拓扑结构((真双子叶植物，单子叶植物)，木兰类植物)。

真双子叶植物内部各目的系统发育关系也存在争论（图1:F-K)，真双子叶植物除了最基部的毛茛目（Ranunculales）、山龙眼目（Proteales）、昆栏树目（Trochodendrales）、黄杨目（Buxales）和洋二仙草目（Gunnerales），其余的可以分为两类：蔷薇类植物（Rosids）和菊类植物（Asterids)。这两类植物的基部有6个目的系统发育关系比较混乱，即五娅果目（Dilleniales）、虎耳草目（Saxifragales）、葡萄目（Vitales）、檀香目（Santalales）、智利藤目（Berberidopsidales）及石竹目（Caryophyllales）。Zeng etal.（2017)总结了已经发表的六种主要的拓扑关系（图1:F-K)，其中K是APGIV 中所认可的拓扑结构。Moore etal.(2010)使用83个质体基因为86种植物构建的进化树，支持“五娅果目是蔷薇类植物的姊妹群”;Soltie etal.(2011)等使用17个基因串联（包括质体基因、线粒体基因和核基因）为640种植物构建的进化树,和Moore etal.(2011)使用质体IR序列为87种植物构建的进化树，支持"五娅果目是菊类植物的姊妹群”；Worberg etal.(2007)等使用五个基因组区域序列为 56 种植物构建的进化树，和Moore etal.(2011)使用质体IR序列为244种植物构建的进化树，及APGIV都支持“五䅉果目是蔷薇类植物和菊类植物共同的姊妹群”。大部分研究都支持“葡萄目和虎耳草目是蔷薇类植物的姊妹群，智利藤目、檀香目和石竹目是菊类植物的姊妹群”（Moore et al.,2011,2010; Worberg et al.,2007; Yang et al.,2015)； Zeng et al.(2017)使用 504个核基因并联为100 种植物构建的进化树，支持“檀香目和智利藤目是蔷薇类植物的姊妹群”

被子植物的起源及进化一直是植物学界研究和争论的热点。在古生物学界，很长时期内，被子植物的最早化石记录都是白垩纪125 百万年前，也是最早的真双子叶植物化石记录（Herendeen,1995)。Fuetal.(2018)发现了早侏罗纪地层（约175百万年前）中的"南京花”，其具有花萼、花瓣、雌蕊，有明显的杯托、下位子房上位花、树状的花柱，其种子/胚珠确实是被完全包裹着，子房壁将种子与外界完全隔绝，这都满足了被子植物判断标准。“南京花”的发现，将被子植物最早化石记录向前推进了约5000万年，并填补了被子植物化石记录（125百万年前）与分子钟推算时间（225\~240百万年前）之间的“侏罗纪空缺”（Jurassicgap）(Lietal.,2019)。目前，大多数基于系统进化树的被子植物分化时间估计研究，都认为被子植物的起源为三叠纪 225\~240 百万年前（Magallon,2010; Mandel,2019; Smith et al.,2010;

Zeng etal.,2014)，这与起传粉作用的核心植食性鳞翅目昆虫的起源时间（约 230 百万年前）一致（Li et al., 2019; Zeng et al., 2014)。

本研究使用超过5000 个核基因的核酸及蛋白序列，用两种进化树构建方法分析了88种被子植物的系统发育关系（包括87科58目），并对各进化分支的分化时间进行了估计（总流程如图2)。为了得到准确可靠的被子植物系统发育进化树，我们对5000多个核基因进行了拆分，得到了包含不同基因数量的多个数据集，并对各个数据集进行系统发育树的构建，最后比较了所得到的20棵系统发育进化树之间的一致性。

![](images/76343a81bd51a4e4698601db2497cf289dd7d438b01709289db7f74f8a41d9a1.jpg)

注：A-E.五类被子植物间（金栗兰科(Chl)、金鱼藻科(Cer)、木兰类植物(Mag)、单子叶植物(Mon)及真双子叶植物(Eud)）5种代表性拓扑结构；F-K.真双子叶植物内部各目间6种代表性拓扑结构。

Note:A-E. Five representative topologies among eudicots (Eud), monocots (Mon), magnoliids (Mag), Ceratophyllaceae (Cer) and Chloranthaceae (Chl); F-K.Six representative topologies among eudicots.

![](images/4d5cca102f38c575168381d044150c52cfcacbc2e0be4932ae02ceee3518ac08.jpg)  
图1不同拓扑结构的被子植物演化关系Fig.1 Various topologies of angiosperm phylogeny  
图2被子植物系统演化关系重建总流程  
Fig.2 The overall workflow of angiosperm phylogeny reconstruction

# 1材料和方法

# 1.1材料

我们收集了1个裸子植物(Ginkgo biloba作为外类群)基因组、43个被子植物基因组(主要来自NCBI和PHYTOZOME数据库）、43个被子植物已拼接转录组（http://www.onekp.com/public_data.html）及 2 个被子植物 RNA-seq 数据（其中无叶莲Petrosavia sakurai是本研究测序的物种)，其中被子植物共包含87科 58目（表1)。

表1本研究所用的89个植物物种及数据来源  
Table1 The list of the 89 plants used in this study and the data source   

<html><body><table><tr><td>物种 Species</td><td>数据来源类型 Data origin</td><td>缩写 目 Abbreviation Order</td><td></td><td>数据 来源</td></tr><tr><td>银杏Ginkgo biloba</td><td>type Genome</td><td>GGIBI</td><td>裸子植物门 Gymnosperm</td><td>Data origin http://gigadb.org/dataset/</td></tr><tr><td>猕猴桃Actinidia chinensis</td><td>Genome</td><td>GACCH</td><td>杜鹃花目 Ericales</td><td>100613 ncbi</td></tr><tr><td>无油樟Amborella trichopoda</td><td>Genome</td><td>GAMTR</td><td>无油樟目Amborellales</td><td>phytozome</td></tr><tr><td>菠萝 Ananas comosus</td><td>Genome</td><td>GANCO</td><td>禾本目Poales</td><td>ncbi</td></tr><tr><td>深圳拟兰Apostasia shenzhenica</td><td>Genome</td><td>GAPSH</td><td>天门冬目Asparagales</td><td>ncbi</td></tr><tr><td>拟南芥 Arabidopsis thaliana</td><td>Genome</td><td>GARTH</td><td>十字花目 Brassicales</td><td>tair</td></tr><tr><td>芦笋 Asparagus officinalis</td><td>Genome</td><td>GASOF</td><td>天门冬目Asparagales</td><td>phytozome</td></tr><tr><td>甜菜 Beta vulgaris</td><td>Genome</td><td>GBEVU</td><td>石竹目Caryophyllales</td><td>ncbi</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">胡桃 Juglans regia</td><td rowspan="2">Genome</td><td rowspan="2">GJURE</td><td rowspan="2">壳斗目Fagales</td><td rowspan="2">ncbi</td></tr><tr><td> https://datadryad.org/res</td></tr><tr><td>喜树 Camptotheca acuminata</td><td>Genome</td><td>GCAAC</td><td>山茱萸目 Cornales</td><td>ource/doi:10.5061/dryad.</td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td>nc8qr</td></tr><tr><td>phytozome</td></tr><tr><td>番木瓜 Carica papaya</td><td>Genome</td><td>GCAPA</td><td>十字花目 Brassicales</td><td></td></tr><tr><td rowspan="2">长春花Catharanthus roseus</td><td rowspan="2">Genome</td><td rowspan="2">GCARO</td><td rowspan="2">龙胆目 Gentianales</td><td> https://datadryad.org/res</td></tr><tr><td>ource/doi:10.5061/dryad.</td></tr><tr><td></td><td></td><td></td><td></td><td>hs593</td></tr><tr><td>土瓶草Cephalotus follicularis</td><td>Genome</td><td>GCEFO</td><td>酯浆草目 Oxalidales</td><td>ncbi</td></tr><tr><td>甜橙Citrus sinensis</td><td>Genome</td><td>GCISI</td><td>无患子目 Sapindales</td><td>phytozome</td></tr><tr><td>中粒咖啡 Coffea canephora</td><td>Genome</td><td>GCOCA</td><td>龙胆目 Gentianales</td><td>http://cofee-genome.org /download</td></tr><tr><td>胡萝卜Daucus carota</td><td>Genome</td><td>GDACA</td><td>伞形目Apiales</td><td>phytozome</td></tr><tr><td rowspan="2">龙眼 Dimocarpus longan</td><td rowspan="2">Genome</td><td rowspan="2">GDILO</td><td rowspan="2">无患子目 Sapindales</td><td>http://gigadb.org/dataset/</td></tr><tr><td>view/id/100276</td></tr><tr><td rowspan="3">几内亚薯 Dioscorea rotundata</td><td rowspan="3">Genome</td><td rowspan="3">GDIRO</td><td rowspan="3">薯目Dioscoreales</td><td>http://genome-e.ibrc.or.j</td></tr><tr><td> p/home/bioinformatics-te</td></tr><tr><td> am/yam</td></tr><tr><td>苦荞麦 Fagopyrum tataricum</td><td></td><td>GFATA</td><td></td><td> http://www.mbkbase.org</td></tr><tr><td></td><td>Genome</td><td></td><td>石竹目 Caryophyllales</td><td>/Pinku1</td></tr><tr><td rowspan="2">小果野蕉 Musa acuminata</td><td rowspan="2">Genome</td><td rowspan="2">GMUAC</td><td rowspan="2">姜目 Zingiberales</td><td>ncbi</td></tr><tr><td>https://genomevolution.0</td></tr><tr><td>画眉草Eragrostis tef</td><td>Genome</td><td>GERTE</td><td>禾本目Poales</td><td>rg/CoGe/GenomeInfo.pl</td></tr><tr><td></td><td></td><td></td><td></td><td>?gid=22790</td></tr><tr><td>巨桉 Eucalyptus grandis</td><td>Genome</td><td>GEUGR</td><td>桃金娘目 Myrtales</td><td>phytozome</td></tr><tr><td>欧洲白蜡树 Fraxinus excelsior</td><td>Genome</td><td>GFREX</td><td>唇形目 Lamiales</td><td> http://www.ashgenome.0</td></tr><tr><td>大豆 Glycine max</td><td></td><td>GGLMA</td><td>豆目 Fabales</td><td>rg/dup_annot11</td></tr><tr><td>向日葵 Helianthus annus</td><td>Genome Genome</td><td>GHEAN</td><td>菊目Asterales</td><td>phytozome</td></tr><tr><td>牵牛花 Ipomoea nil</td><td>Genome</td><td>GIPNI</td><td>茄目 Solanales</td><td>phytozome ncbi</td></tr><tr><td>伽蓝Kalanchoe fedtschenkoi</td><td>Genome</td><td>GKAFE</td><td>虎耳草目 Saxifragales</td><td>phytozome</td></tr><tr><td>博落回 Macleaya cordata</td><td>Genome</td><td>GMACO</td><td>毛茛目 Ranunculales</td><td>ncbi</td></tr><tr><td>苦瓜 Momordica charantia</td><td>Genome</td><td>GMOCH</td><td>葫芦目Cucurbitales</td><td>ncbi</td></tr><tr><td>中国莲 Nelumbo nucifera</td><td>Genome</td><td>GNENU</td><td>山龙眼目 Proteales</td><td>ncbi</td></tr><tr><td>海枣 Phoenix dactylifera</td><td>Genome</td><td>GPHDA</td><td>棕榈目 Arecales</td><td>ncbi</td></tr><tr><td>毛果杨 Populus trichocarpa</td><td>Genome</td><td>GPOTR</td><td>金虎尾目 Malpighiales</td><td>phytozome</td></tr><tr><td rowspan="2">委陵菜Potentilla micrantha</td><td rowspan="2">Genome</td><td rowspan="2">GPOMI</td><td rowspan="2">蔷薇目 Rosales</td><td> http://gigadb.org/dataset/</td></tr><tr><td>100407</td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2">杜鹃花目 Ericales</td><td> https://www.datadryad.o</td></tr><tr><td>rg/resource/doi:10.5061/</td></tr><tr><td></td><td>Genome</td><td>GPRVE</td><td></td><td>dryad.2s200</td></tr><tr><td>石榴 Punica granatum</td><td>Genome</td><td>GPUGR</td><td>桃金娘目 Myrtales</td><td>ncbi</td></tr><tr><td>栎栎 Quercus lobata</td><td>Genome</td><td>GQULO</td><td>壳斗目Fagales</td><td>https://valleyoak.ucla.ed W/genomicresources/</td></tr></table></body></html>

<html><body><table><tr><td>橡胶树 Hevea brasiliensis</td><td>Genome</td><td>GHEBR</td><td>金虎尾目Malpighiales</td><td>ncbi</td></tr><tr><td>丹参 Salvia miltiorrhiza</td><td>Genome</td><td>GSAMI</td><td>唇形目Lamiales</td><td>http://giga</td></tr><tr><td>马铃薯 Solanum tuberosum</td><td>Genome</td><td>GSOTU</td><td>茄目 Solanales</td><td>100164 phytozom</td></tr><tr><td>紫萍 Spirodela polyrrhiza</td><td>Genome</td><td>GSPPO</td><td>泽泻目 Alismatales</td><td>phytozom</td></tr><tr><td>可可 Theobroma cacao</td><td>Genome</td><td>GTHCO</td><td>锦葵目 Malvales</td><td>phytozom</td></tr><tr><td>葡萄 Vitis vinifera</td><td>Genome</td><td>GVIVI</td><td>葡萄目 Vitales</td><td>phytozom</td></tr><tr><td>大枣 Ziziphus jujuba</td><td>Genome</td><td>GZIJU</td><td>蔷薇目 Rosales</td><td>ncbi</td></tr><tr><td>大叶藻 Zostera marina</td><td>Genome</td><td>GZOMA</td><td>泽泻目 Alismatales</td><td>phytozom</td></tr><tr><td>美洲菖蒲 Acorus americanus</td><td>Transcriptome</td><td>MTII</td><td>菖蒲目 Acorales</td><td>onekp</td></tr><tr><td>青英叶 Helwingia japonica</td><td>Transcriptome</td><td>QACK</td><td>冬青目 Aquifoliales</td><td>onekp</td></tr><tr><td>木兰藤 Austrobaileya scandens</td><td>Transcriptome</td><td>FZJL</td><td>木兰藤目 Austrobaileyales</td><td>onekp</td></tr><tr><td>红花八角 Illicium floridanum</td><td>Transcriptome</td><td>VZCI</td><td>木兰藤目 Austrobaileyales</td><td>onekp</td></tr><tr><td>鳞枝树 Aextoxicon punctatum</td><td> Transcriptome</td><td>QUTB</td><td>智利藤目 Berberidopsidales</td><td>onekp</td></tr><tr><td>红金藤 Berberidopsis beckleri</td><td>Transcriptome</td><td>HAEU</td><td>智利藤目 Berberidopsidales</td><td>onekp</td></tr><tr><td>圆锥梅藤 Mertensia paniculata</td><td>Transcriptome</td><td>DKFZ</td><td>紫草目 Boraginales</td><td>onekp</td></tr><tr><td>加洲蓝钟 Phacelia campanularia</td><td> Transcriptome</td><td>YQIJ</td><td>紫草目 Boraginales</td><td>onekp</td></tr><tr><td>锦熟黄杨 Buxus sempervirens</td><td>Transcriptome</td><td>IWMW</td><td>黄杨目 Buxales</td><td>onekp</td></tr><tr><td>白桂皮 Canella winterana</td><td> Transcriptome</td><td>DDEV</td><td>白桂皮目 Canellales</td><td>onekp</td></tr><tr><td>林仙 Drimys winteri</td><td>Transcriptome</td><td>WKSU</td><td>白桂皮目 Canellales</td><td>onekp</td></tr><tr><td>玉女樱Crossopetalum rhacoma</td><td>Transcriptome</td><td>IHCQ</td><td>卫矛目 Celastrales</td><td>onekp</td></tr><tr><td>金鱼藻 Ceratophyllum demersum</td><td>Transcriptome</td><td>NPND</td><td>金鱼藻目 Ceratophyllales</td><td>onekp</td></tr><tr><td>红茎蛔囊花 Ascarina rubricaulis</td><td>Transcriptome</td><td>WZFE</td><td>金粟兰目 Chloranthales</td><td>onekp</td></tr><tr><td>水苏 Stachyurus praecox</td><td>Transcriptome</td><td>VYGG</td><td>燧体木目 Crossosomatales</td><td>onekp</td></tr><tr><td>美国省沽油 Staphyleatrifolia</td><td> Transcriptome</td><td>PTLU</td><td>燧体木目 Crossosomatales</td><td>onekp</td></tr><tr><td>五娅果 Dillenia indica</td><td>Transcriptome</td><td>EHNF</td><td>五娅果目 Dilleniales</td><td>onekp</td></tr><tr><td>日本珊瑚树 Viburnum odoratissimum</td><td>Transcriptome</td><td>HLJG</td><td>川续断目 Dipsacales</td><td>onekp</td></tr><tr><td>金银花 Lonicera japonica</td><td>Transcriptome</td><td>GSZA</td><td>川续断目 Dipsacales</td><td>onekp</td></tr><tr><td>红叶凤眼莲 Escallonia rubra</td><td> Transcriptome</td><td>CLMX</td><td>南鼠刺目 Escalloniales</td><td>onekp</td></tr><tr><td>杜仲 Eucommia ulmoides</td><td>Transcriptome</td><td>SZUO</td><td>绞木目Garryales</td><td>onekp</td></tr><tr><td>花茎草Francoa appendiculata</td><td>Transcriptome</td><td>HDWF</td><td>牛儿苗目 Geraniales</td><td>onekp</td></tr><tr><td>斑点老鹤草 Geranium maculatum</td><td> Transcriptome</td><td>YGCX</td><td>牛儿苗目 Geraniales</td><td>onekp</td></tr><tr><td>长萼大叶草 Gunnera manicata</td><td>Transcriptome</td><td>XMQO</td><td>洋二仙草目 Gunnerales</td><td>onekp</td></tr><tr><td>瘿椒树 Tapiscia sinensis</td><td>Transcriptome</td><td>WWKL</td><td>十齿花目 Huerteales</td><td>onekp</td></tr><tr><td>锦葵叶刺核藤 Pyrenacantha malvifolia</td><td>Transcriptome</td><td>QZZU</td><td>茶茱萸目 Icacinales</td><td>onekp</td></tr><tr><td>钩药茶 Oncotheca balansae</td><td>Transcriptome</td><td>PVGM</td><td>茶茱萸目 Icacinales</td><td>onekp</td></tr><tr><td>美国蜡梅 Calycanthus floridus</td><td>Transcriptome</td><td>FALI</td><td>樟目 Laurales</td><td>onekp</td></tr><tr><td>美擦树 Sassafras albidum</td><td>Transcriptome</td><td>ABSS</td><td>樟目 Laurales</td><td>onekp</td></tr><tr><td>阿福花状旱叶草 Xerophyllum</td><td>Transcriptome</td><td>AFLV</td><td>百合目Liliales</td><td>onekp</td></tr><tr><td>asphodeloides</td><td></td><td></td><td></td><td></td></tr><tr><td>锯齿绿荆棘 Smilax bona-nox 刺果番荔枝 Annona muricata</td><td>Transcriptome</td><td>MWYQ</td><td>百合目 Liliales</td><td>onekp</td></tr><tr><td>肉豆蔻Myristica fragrans</td><td>Transcriptome Transcriptome</td><td>YZRI OBPL</td><td>木兰目 Magnoliales 木兰目 Magnoliales</td><td>onekp onekp</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>黄瑞香 Daphne giraldii</td><td>Transcriptome</td><td>PUDI</td><td>锦葵目Malvales</td><td>onekp</td></tr></table></body></html>

<html><body><table><tr><td>圆叶肋果萍蓬草Nuphar advena</td><td>Transcriptome</td><td>WTKZ</td><td>睡莲目Nymphaeales</td><td>onekp</td></tr><tr><td>露兜树 Xerophyta villosa</td><td>Transcriptome</td><td>QOXT</td><td>露兜树目 Pandanales</td><td>onekp</td></tr><tr><td>马蹄香 Saruma henryi</td><td>Transcriptome</td><td>QDVW</td><td>胡椒目Piperales</td><td>onekp</td></tr><tr><td>墨西哥胡椒 Piper auritum</td><td>Transcriptome</td><td>MUNP</td><td>胡椒目Piperales</td><td>onekp</td></tr><tr><td>银桦 Grevillea robusta</td><td>Transcriptome</td><td>GRRW</td><td>山龙眼目 Proteales</td><td>onekp</td></tr><tr><td>框东坚果 Santalum acuminatum</td><td>Transcriptome</td><td>RSPO</td><td>檀香目 Santalales</td><td>onekp</td></tr><tr><td>昆栏树Trochodendron aralioides</td><td>Transcriptome</td><td>SWOH</td><td>昆栏树目 Trochodendrales</td><td>onekp</td></tr><tr><td>蔓茎刺球果 Krameria lanceolata</td><td>Transcriptome</td><td>ZHMB</td><td>蒺藜目 Zygophyllales</td><td>onekp</td></tr><tr><td>蒺藜Tribulus eichlerianus</td><td>Transcriptome</td><td>KVAY</td><td>蒺藜目 Zygophyllales</td><td>onekp</td></tr><tr><td>露水草Cyanotis arachnoidea</td><td></td><td>TCYTR</td><td>鸭跖草目Commelinales</td><td>https://www.ncbi.nlm.ni</td></tr><tr><td>无叶莲Petrosavia sakurai</td><td>RNA-SEQ RNA-SEQ</td><td>TPETR</td><td>无叶莲科 Petrosaviaceae</td><td>h.gov/sra/SRP144398 This study</td></tr></table></body></html>

# 1.2基于基因组序列的直系同源基因鉴定

我们使用 Yang& Smith(2014)报道的方法，对43个植物基因组的基因集进行同源基因聚类分析。先使用软件 $\mathrm { B L A S T N } \ \mathrm { v } 2 . 6 . 0 +$ 对 43 个基因集CDS 序列进行all-by-all blast，每条序列取最佳的1000条比对结果，去掉比对长度小于 $1 / 3$ 总长的序列，修剪未比对上的末端序列。再使用MCL软件（Van,2000）进行同源基因聚类（inflationvalue $= 1 . 4 \dot { . }$ ，去除少于20个植物的基因家族，剩余基因家族使用MAFFTv7.310软件（Katoh& Standley,2013）进行多序列比对（maximum iterative refinement cycles $= 1 0 0 0 \dot { . }$ ，使用PHYUTILITY $\mathbf { v } 2 . 2 . 6$ 软件（Smith&Dunn,2008）修剪缺失率大于 $9 0 \%$ 的位点，使用软件RAXMLv8.2.11（Stamatakis,2014）对修剪后的多序列比对数据估算系统进化树 $\mathrm { ( m o d e l = G T R C A T ) }$ 。最后修剪掉进化树上的所有旁系同源基因枝，修剪枝长大于0.6的枝、比姐妹枝长十倍的末端枝，单源且全部同样品的枝只保留一个，修剪枝长比预期碱基替换率大0.3倍的内部枝，再使用 MO 方法（Yang& Smith,2014）去除所有剩余的旁系同源枝，获得one-to-one同源基因家族（即每个样品最多一条序列)，只保留大于20 个样品的基因家族。

# 1.3转录组及外类群数据处理

我们对两个来自两个科（无叶莲科Petrosavia sakurai和鸦跖草科Cyanotis arachnoidea）的 RNA-seq 数据从头拼接。首先使用 Trimmomatic v0.38 软件（Bolger et al.,2014）过滤原始reads 数据（参数：HEADCROP:15 LEADING:20 TRAILING:20 SLIDINGWINDOW:5:20MINLEN:50 AVGQUAL:20),再使用 Trinity v2.6.6 软件(Grabherr et al.,2011)拼接(min contiglength=150bp ） ， 最后使用 TransDecoder v5.5.0(https://github.com/TransDecoder/TransDecoder/releases/tag/TransDecoder-v5.5.0）进行 CDS和蛋白质序列预测（参考数据库为 Swissprot 和 Pfam-A)。将得到的这两个物种的基因集、从onekp 数据库下载得到的43种被子植物的基因集和1个裸子植物（Ginkgobiloba）的基因集,使用HaMStRv13.2.6 软件（Ebersberger et al.,2009）合并到利用基因组数据得到的同源基因家族中，最终只保留大于50个样品的基因家族。

# 1.4系统发育进化树构建

我们采用两种方法串联法（concatenation）和溯祖法（coalescence），并分别使用CDS序列和氨基酸序列构建进化树。无论是CDS序列还是蛋白质序列，都使用PRANKv.170427软件（http://wasabiapp.org/software/prank/）进行多序列比对，使用 PHYUTILITYv2.2.6 软件（Smith&Dunn,2008）修剪缺失率大于 $7 0 \%$ 的位点，其中CDS序列需去除长度小于 300个碱基的序列，蛋白质序列需去除长度小于100 个氨基酸的序列。

溯祖法，先对每个基因使用RAxMLv8.2.11软件（默认参数）（Stamatakis,2014）画树，再使用ASTRALv5.5.9 软件（Zhang et al.,2017）处理所有基因树，得到共有树，参数设置"-t1 --gene-only"以获得 bootstrap 值和基因支持率，枝长使用 iqtree v1.5.5 软件（Nguyen et al.,2015）获得。

串联法，先使用PartitionFinder v2.1.1软件（Lanfear etal.,2009）对串联序列进行分区和进化模型检测，从而设置较合理的分区和为每个分区选择合理的进化模型。对CDS 序列检测下列的四个分区策略（表 2）:no partitioning，partitioning by each codon position (threepartitions), partitioning by gene 和 partitioning by each codon position within each gene。对蛋白质序列检测下列两个分区策略：no partitioning 和 partitioning by gene。参数设置如下：branchlengths $\ c =$ linked; model_selection $\ c =$ aicc; search $\ c =$ user; models $\mathbf { \tau } = \mathbf { \tau }$ GTR,GTR $+ \mathrm { G }$ ,GTR $+ \mathrm { I + G }$ (CDS序列)或者models $= \mathrm { L G } + \mathrm { G }$ $_ \mathrm { L G + I + G }$ ， $\mathrm { \Delta W A G + G }$ ，WAG $+ \mathbf { I } { + } \mathbf { G }$ （蛋白质序列)。再使用iqtreev1.5.5软件画树（100O ultrafast bootstrap replicates（Von Haeseler et al.,2013)，-spp 设置最优分区策略），基因支持率使用ASTRALv5.5.9软件（-t1）获得。最后使用软件Evolviewv2（He etal.,2016）对获得的所有进化树进行美化。

表2串联法建树分区模型检测  
Table2 AICc scores for each of the phylogenetic matrix partitioning strategies   

<html><body><table><tr><td></td><td>数据大小</td><td>分区策略</td><td>分区数目</td><td></td><td></td></tr><tr><td>数据 Matrix</td><td>Number of</td><td>Partitioning</td><td>Number of</td><td>对数似然值</td><td>赤池信息值</td></tr><tr><td></td><td>data</td><td> strategy</td><td>partitions</td><td>Log-likelihood</td><td>AICc</td></tr><tr><td>nt(≥50sample)</td><td>26 563 047</td><td>OnePart</td><td>1</td><td>-343 591104.000 000</td><td>687 182 578.003 000</td></tr><tr><td></td><td></td><td>CodonPart</td><td>3</td><td>-343 585 496.000 000</td><td>687 171 406.003 000</td></tr><tr><td></td><td></td><td>GenePart</td><td>5929</td><td>-342 778 283.430 175</td><td>685 687 673.619 000</td></tr><tr><td></td><td></td><td>CodonGenePart</td><td>3x5 929</td><td>-341 770 443.474 243</td><td>683 935 206.166 000</td></tr><tr><td>nt(≥70sample)</td><td>16 540 374</td><td>OnePart</td><td>1</td><td>-222 849 712.000 000</td><td>445 699 794.004 000</td></tr><tr><td></td><td></td><td>CodonPart</td><td>3</td><td>-222 846 000.000 000</td><td>445 692 414.005 000</td></tr><tr><td></td><td></td><td>GenePart</td><td>3384</td><td>-222 406 333.714 843</td><td>444 887 632.932 000</td></tr><tr><td></td><td></td><td>CodonGenePart</td><td>3x3384</td><td>-221 758 883.619 628</td><td>443 742 935.528 000</td></tr><tr><td>nt(≥ 80sample)</td><td>9 340 788</td><td>OnePart</td><td>1</td><td>-129 962 472.000 000</td><td>259 925 314.007 000</td></tr><tr><td></td><td></td><td>CodonPart</td><td>3</td><td>-129 960 500.000 000</td><td>259 921 414.009 000</td></tr><tr><td></td><td></td><td>GenePart</td><td>1791</td><td>-129 739 122.166 992</td><td>259 518 079.097 000</td></tr><tr><td></td><td></td><td>CodonGenePart</td><td>3×1791</td><td>-129 354 388.143 432</td><td>258 828 073.274 000</td></tr><tr><td>nt(≥85sample)</td><td>4 069 848</td><td>OnePart</td><td>1</td><td>-57 607 360.000 000</td><td>115 215 090.017 000</td></tr><tr><td></td><td></td><td>CodonPart</td><td>3</td><td>-57 606 964.000 000</td><td>115 214 342.021 000</td></tr><tr><td></td><td></td><td>GenePart</td><td>742</td><td>-57 512 358.070 313</td><td>115 041 422.363 000</td></tr><tr><td></td><td></td><td>CodonGenePart</td><td>3×742</td><td>-57 329 703.801 392</td><td>114 709 026.252 000</td></tr><tr><td>nt(≥ 89sample)</td><td>231 309</td><td>OnePart</td><td>1</td><td>-3 311 701.250 000</td><td>6 623 772.797 760</td></tr><tr><td></td><td></td><td>CodonPart</td><td>3</td><td>-3 311 505.937 500</td><td>6 623 426.247 620</td></tr><tr><td></td><td></td><td>GenePart</td><td>42</td><td>-3 304 863.765 625</td><td>6 611 003.043 870</td></tr><tr><td></td><td></td><td>CodonGenePart</td><td>3×42</td><td>-3 290 917.219 238</td><td>6 584 975.637 010</td></tr><tr><td>AA(≥50sample)</td><td>3 332 638</td><td>OnePart</td><td>1</td><td>-135 739 947.205 826</td><td>271 508 915.612 567</td></tr><tr><td></td><td></td><td>GenePart</td><td>5 929</td><td>-135 248 986.841 308</td><td>270 526 876.482 000</td></tr><tr><td>AA(≥70sample)</td><td>2 029 014</td><td>OnePart</td><td>1</td><td>-83 878 051.077 318</td><td>167 759 844.588 965</td></tr><tr><td></td><td></td><td>GenePart</td><td>3 384</td><td>-83 574 671.167 480</td><td>167169 596.938 000</td></tr><tr><td>AA(≥ 80sample)</td><td>1 165 765</td><td>OnePart</td><td>1</td><td>-47 214 500.000 000</td><td>94 429 354.054 100</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>GenePart</td><td>1791</td><td>-47 043 728.832 520</td><td>94 097 113.497 200</td></tr></table></body></html>

<html><body><table><tr><td>AA(≥85sample)</td><td>519 158</td><td>OnePart</td><td>1</td><td>-19 925 224.000 000</td><td>39 850 802.121 400</td></tr><tr><td rowspan="3">AA(≥89sample)</td><td></td><td>GenePart</td><td>742</td><td>-19 851 832.912 842</td><td>39707977.665 800</td></tr><tr><td>30148</td><td>OnePart</td><td>1</td><td>-979 643.625 000</td><td>1 959 681.828 340</td></tr><tr><td></td><td>GenePart</td><td>42</td><td>-973 566.588 867</td><td>1948 059.215 120</td></tr></table></body></html>

注：黑体为最优模型 (即赤池信息值值最低) Note:Bold is the best partition (AICc value is the lowest).

# 1.5分化时间估计

我们使用PAMLv4.9软件包（Yang,2007）的 MCMCTREE 程序进行分化时间估计，输入拓扑结构为综合20棵进化树的最佳拓扑结构（即使用742个基因的CDS 序列串联法获得的拓扑结构),输入序列为742个基因的CDS序列。我们先对每个基因都分别估计分化时间，再综合742个基因的分析结果（即每个节点取所有基因的平均值）获得最终的分化时间树。拓扑结构的枝长使用 JONES+gamma 碱基替换模型获得；rgene gamma 设定为G(1，4.5);sigma2 gamma 设定为G(1,4.5)；clock 设定为3；Markov chain Monte Carlo(MCMC)设定为burnin $= 5 0 \ 0 0 0$ ， sampfreq $= 1 0 0$ ，nsample $= 1 0 \ 0 0 0$ 。对每个基因，都是分别运行两次独立的MCMC（即不同的randomseeds），使用Tracerv1.7软件(https://github.com/beast-dev/tracer/releases/tag/v1.7.1)观察运行结果是否稳定和收敛，所有节点及参数的 effective sample size 是否大于 200。九个化石校准设定为：银杏分化时间为290-310 百万年前（Gao etal.,1989)，单子叶植物和真双子叶植物分化时间为130\~200 百万年前（Kumar etal.,2017)，真双子叶植物共同祖先（即最早的双子叶植物化石记录）为125百万年前（Herendeen,1995; Zeng et al.,2014)，山龙眼目（Proteales）的共同祖先为108.8百万年前（Crane etal.，1996)，葡萄目（Vitales）与其余蔷薇类植物间分化时间为105-115百万年前（Fawcett et al.,2009; Kumar et al.,2017)，A. thaliana 与 P. trichocarpa 间分化时间为97\~109 百万年前（Kumar etal.,2017)，豆目（Fabales）与壳斗目（Fagales）间分化时间为 93.5百万年前（Fris etal.，1996），山茱萸目（Cormales）共同祖先为85.8 百万年前（Takahashi etal.,2002），唇形目（Lamiales）共同祖先为44.3百万年前（Calletal.,1992）。

# 2结果与分析

# 2.1直系同源基因鉴定

我们对44个植物基因组基因集和 45 个已拼接转录组CDS 序列进行同源基因聚类，并使用Yang＆ Smith(2014)报道的方法，去除所有旁系同源基因，最终获得大于 50个样品的one-to-one 基因家族（即每个样品最多一条序列）共5_993个（图3:A），各种植物的基因覆盖率从 $3 3 . 5 7 \%$ 到 $9 7 . 8 5 \%$ ，平均为 $8 0 . 4 0 \%$ （图3:B）。

Note: A. Number of samples for each orthologous gene family; B. Number of orthologous genes for each sample.

![](images/dfd8229ec8ffb06815c3d6dcb12f735d5b5a490bf7e8fa27d264ed7b4182af90.jpg)  
注：A.每个同源基因家族含有的基因数目；B.每个样品含有的同源基因家族数目。  
图35993个聚类的同源基因家族  
Fig.3 Results of 5 993 inferred orthologous gene groups

# 2.2系统发育进化树构建

我们采用串联和溯祖法共构建了20 棵进化树，并比较它们之间的不同（图4)，以评估树的稳定性。CDS序列和蛋白质序列，都分别使用五个数据集，总共构建20棵树（5棵CDS串联法树，5棵CDS 溯祖法树，5棵AA串联法树和5棵AA溯祖法树)。这5个数据集分别包含5928个orthologs（ $\geqslant 5 0$ samples）、3 384 个 orthologs（ $\geqslant 7 0$ samples）、1791个orthologs ( $\geqslant 8 0$ samples）、742 个orthologs ( $\geqslant 8 5$ samples）及 42个orthologs( ${ \geqslant } 8 9$ samples）。

这 20 棵进化树主要是为了进一步确定图1中五类被子植物间演化关系和真双子叶植物内部各目间系统发育关系。这些进化树中的大多数，是与使用742个基因CDS序列（共4069848 位点）串联方法建立的进化树高度一致的（图5）（使用3384个基因AA序列建立的进化树，和使用1791个基因AA序列建立的进化树，也是相同的最佳拓扑结构)。

2.2.1木兰类植物、单子叶植物及双子叶植物间演化关系

无论核酸序列还是蛋白质序列，使用串联法和溯祖法建立的进化树基本都支持拓扑结构(（真双子叶植物，单子叶植物)，木兰类植物）（图4)。

# 2.2.2金栗兰科与金鱼藻科

我们的研究表示，金鱼藻科是真双子叶植物的姊妹群，这与前人的研究结果一致(图4)。但金栗兰科是所有被子植物（除ANITA外）的基底旁系群，这与APGIV认为的“金栗兰科是木兰类植物的姊妹群”是不同的。

# 2.2.3双子叶植物内部各目的系统发育关系

我们的研究认为，五䅉果科是蔷薇类植物和菊类植物共同的姊妹群，虎耳草目是蔷薇类植物的姊妹群，这都与APGIV一致（图4)。

APGIV认为“檀香目和石竹目是菊类植物的姊妹群”，而我们的研究否定了这一结论：20棵进化树中，所有结果都支持“石竹目是蔷薇类植物的姊妹群”；大部分支持“檀香目是蔷薇类植物的姊妹群”，这与 Zeng etal.（2017)等的研究结果一致；少部分支持“檀香目是蔷薇类植物和菊类植物共同的姊妹群”(图4)。

APGIV认为“智利藤目是菊类植物的姊妹群”，而我们的研究只有少部分支持这一结论。使用蛋白质序列建立的进化树，无论串联还是溯祖法，都支持“智利藤目是蔷薇类植物和菊类植物共同的姊妹群”。使用核酸序列建立的进化树，随着基因数目的增多，逐渐转变为支持“智利藤目是菊类植物的姊妹群”，与APGIV一致（图4)。

![](images/18419da378e73aefd5d07f92db9c25ed0f8dfb4579e3fe7e2568899b861e7d98.jpg)

注：A.Bootstrap 值；B.基因支持率。(红色表示支持，蓝色表示拒绝，红色星星表示支持率最高的拓扑结构)

Note:A. Bootstrap values; B. Gene trees support values. (Red represents support, blue represents rejection, the topology labeled with a red star is the most supported.)

图4采用各种数据集并使用串联和并联方法建立的20棵进化树，对各种有争议拓扑结构的支持率统计

Fig.4 Statistics of support values for relationships among the clades which are controversial in previous studies by using different methods and gene numbers

Ginkgo biloba Amborella trichopoda | Amborellaceae Amborellales Nuphar advena i-Nymphaeaceae Nymphaeales 100 95.37 Austrobailryascandens 1 Autrabaileyaceae Austrobaileyales Ascarinarubricaulis -Chloranthaceae Chloranthales100 61.06 l earganhee agalses Magnoliids 10086Annonamuricata iAnnonaceae 10089.28 10070.27 10076.LPiperauritum Saruma henryi I Pristolochiaceae Piperales ro0Cimy e 1 Cinellaceae Canellales Acorusamericanus Acoraceae Acorales 74/32.48 10088.98 100 58.57 三 gse   
Monocots 100708 10084.47 10041.63 Dioscorea rotundata --Dioscoreaceae Dioscoreales 10067.12 10087.64 Smiaylumasodeloids 1Mmlathiace Liliales 7037.98 10050.7910058.82 Apstagushinihenica Cyanotisarachnoidea 1Archidagaee -Commelinaceae Commelinales Asparagales Commelinids 98/37.2 10078.Musaacuminata Musaceae Zingiberales ascmos Promeliaceae Poales Phoenixdactylifera Arecaceae Arecales Ceratophyllumdemersum Ceratophyllaceae Ceratophyllales 130 10078.42 reumnog nbe Netumboneea Ranuncuales Buxussempervirens Buxaceae Buxales 10048.44 10044.64 Trochodendronaralioides -Trochodendraceae- Trochodendrales Dillenia indica --Dilleniaceae Dilleniales 10076.51 Gunneramanicata I-Gunneraceae I Gunnerales 10094.52 Bextexiconpunckeri Berberidapsidaceae Berberidopsidales 10093.6 Vitisvinifera IVitaceae Vitales 10031.5 Santalumacuminatum Santalaceae Santalales Kalanchoe fedtschenkoi Crassulaceae Saxifragales 85/34.99 9944.28 10038.84 100g5l atayramtstarcum 1 Amlyganthaceae Caryophyllales 10086.Stachyuruspraecox Staphylea trifolia Stachyuraceae Crossosomatales Malvids 99/47.56 10035.09 10050Francoaappendiculata Geraniummaculatum Franiaceae Geraniales 9/40.67 1cPunicegusgrandis 1-Lythraceae Myrtales 10077.13   
Eudicots 10044.58 54/36Momordicacharantia Fe i-Cucurbitaceae Cucurbitales Fabales Zygophyleses Fabids Rosids 94/41.98 100 403 Crossopetalumrhacoma Celastraceae Celastrales 10051.43 10097.Populustrchocara Hevea brasiliensis 1 Salhorbiaceae Malpighiales 10083.49 84/31.91 Tapalotus olicuais Cephalotaceae xelideales 10046.4810099.171 Dimussinus longan 1 Supindaceae Sapindales Malvids 10046.5106.L Caricaopshalana Cariscaeceae Brassicales 100 56.13 10076.89Theobromacacao Daphnegiraldii i Taymelaeaceae Malvales Camptothecaacuminata Nyssaceae Cornales 10054.29 10084.6Primulaveris Actinidia chinensis Primudiaee Ericales Oncotheca balansae -Oncothecaceae Icacinales 10094.69 97/32.13 Eeucommig lmnides 1Eucwmmiaceae Gquifolases 100 10095.07 Pnna 1aiace Laminales Lamiids Asterids 10095.561094.14 Ipoanum tuberosum Convoivulaceae Solanales 10051.8 8 1 Aubcynaceae Gentianales 94/34.15 10091.84 Mereia camnicutaria Boraginaceae Boraginales Helianthusannuus Asteraceae Asterales Campanulids 10052.46 Daucuscarota Apiaceae Apiales 10075.03 Escalloniarubra -1-Escalloniaceae Escalloniales 10047. 100766 Lonicumaponicismum i Aaprifoliaeae Dipsacales

注：枝上斜线左边数字为bootstrap值，右边数字为基因支持率。

Note：The left number at the notes is bootstrap value.The number on the right is gene trees support ratio. 图5使用742个基因CDS 序列串联方法构建的系统发育进化树   
Fig.5 Concatenation-based angiosperm phylogenetic tree based on CDS sequences of 742 orthologs

# 2.3分化时间估计

基于 742个基因CDS序列串联方法建立的进化树，我们估计了被子植物的分化时间(图6)。我们认为被子植物的起源时间为237.78百万年前（ $9 5 \%$ 置信区间为 202.6\~278.08)，与主流观点认为的 225\~240 百万年前一致(Magallon,2010; Smith et al.,2010; Zeng et al.,2014)。木兰类植物与单子叶植物和真双子叶植物的分化时间约为166.11 百万年前；五娅果科与蔷薇类和菊类植物的分化时间约为124.23百万年前；蔷薇类植物与菊类植物的分化时间约为116.98百万年前；唇形类植物（Lmiids）与桔梗类植物（Campanulids）的分化时间约为102.37百万年前。

![](images/84ba4dd11524adc56191dd98c2540bb989ed9bce9f3e5ab82e80ce3f7101cd64.jpg)

注：灰色条纹为分化时间的 $9 5 \%$ 置信区间,九个化石校准时间为：（1）银杏分化时间为290-310百万年前；（2）单子叶植物和真双子叶植物分化时间为130\~200 百万年前；（3）真双子叶植物共同祖先（即最早的双子叶植物化石记录）为125百万年前；（4）山龙眼目（Proteales）的共同祖先为108.8百万年前；（5）山茱萸目（Comales）共同祖先为85.8百万年前；（6）唇形目（Lamiales）共同祖先为44.3百万年前；（7）葡萄目（Vitales）与其余蔷薇类植物间分化时间为105-115 百万年前；（8)豆目（Fabales)与壳斗目（Fagales）间分化时间为93.5百万年前；（9）Arabidopsis thaliana与Populus trichocarpa间分化时间为97\~109 百万年前；（0）“南京花"的可能系统演化位置（175百万年前）。

Note:Grey bars are $9 5 \%$ confidence intervals, nine fossil calibration points are as follows: (1)The divergence time of Ginkgo biloba is 290-310 million years ago.(2) The divergence time of eudicots and monocots is 130-200 million years ago. (3) The divergence time of eudicots is 125 million years ago.(4) The divergence time of Proteales is 108.8 milion years ago. (5) The divergence time of Cornales is 85.8 million years ago.(6) The   
divergence time of Lamiales is 44.3 million years ago.(7) The divergence time of Vitales from Rosids is 105-115 million years ago. (8) The divergence time ofFabales and Fagales is 93.5 milion years ago. (9)The divergence time of Arabidopsis thaliana and Populus trichocarpa is 97-109 million years ago.

图6基于742个基因CDS序列对被子植物分化时间的估计结果

Fig.6 Chronogram presenting estimated divergence times by MCMCTREE using CDS sequences of 742 genes

# 3讨论与结论

长期以来，被子植物的系统发育关系重建，都是使用质体基因、线粒体基因或少数保守的单拷贝核基因。Yang＆ Smith(2014)报道了一种基于系统进化树的同源基因聚类及去旁系同源基因的方法，我们使用此种方法对收集的88种植物核基因集进行聚类，共获得了多达5 993个one-to-one 基因家族，并从这个数据集里面截取各种大小的数据进行进化树重建，以测定进化树的稳定性。

获得比以前更多的核基因家族后，制约系统演化关系构建的另一个因素就是大量的计算资源和计算时间。构建系统进化树时，一般需要设置bootstrap值（100\~1000）迭代，此步骤非常耗费计算时间。Nguyen et al.(2015)发表的软件 iqtree，采用ultrafast bootstrapapproximation(UFBoot)方法获得 bootstrap 值(Von Haeseler et al.,2013)，比 RAxML 软件的传统方法，计算速度快10\~40 倍，并且获得的bootstrap 值更精确。

我们使用多达5993个one-to-one 基因家族构建的进化树，与APGIV报道的主要差异为檀香目和石竹目在系统发育树中的位置，本研究认为“檀香目和石竹目是蔷薇类植物的姊妹群”，而APGIV认为"檀香目和石竹目是菊类植物的姊妹群”。可能原因有以下两个：一是基因数目的增多；二是本研究所选88个植物只有一半使用的基因组序列，另一半为转录组序列，而转录组序列一般存在大量的基因缺失（即未表达基因较多）。

总的来说，本研究不仅进一步确定了被子植物各目间系统发育关系，而且为“使用更多的基因和计算速度更快的方法构建进化树”探讨了一种可行性策略：即使用 Yang &Smith(2014)报道的同源基因聚类及去旁系同源基因方法，获得大量的one-to-one 基因家族，再使用IQ-TREE（串联法）和ASTRAL（溯祖法）软件，能快速精确的计算出进化树。随着更多植物基因组的测序和基因聚类及系统发育关系构建方法的进一步优化，被子植物系统发育关系将越来越精确，例如进一步准确确定檀香目和石竹目在被子植物中与其他进化分支之间的关系。

# 参考文献:

BOLGER AM,LOHSE M, USADEL B,2014. Trimmomatic: A flexible trimmer for llumina sequence data[J]. Bioinformatics, 30(15): 2114-2120.   
CALL VB, DILCHER DL,1992. Investigations of angiosperms from the Eocene of southeastern North America: Samaras of Fraxinus wilcoxiana Berry[J]. Rev Palaeobot Palynol, 74: 249-266.   
CHAW SM,LIU YC，WU YW, et al.， 2019. Stout camphor tree genome fills gaps in understanding of flowering plant genome evolution[J]. Nat Plants, 5(1): 63-73.   
CHEN JH, HAO ZD, GUANG XM, et al., 2019. Liriodendron genome sheds light on angiosperm phylogeny and species-pair differentiation[J]. Nat Plants, 5(1): 18-25.   
CRANE PR, HERENDEEN PS,1996. Cretaceous floras containing angiosperm flowers and fruits from eastern North America[J]. Rev Palaeobot Palynol, 9O: 319-337.   
EBERSBERGER I, STRAUSS S,VON HAESELER A,20O9.HaMStR: Profile hidden markov model based search for orthologs in ESTs[J]. Bmc Evol Biol, 9(1): 157-157.   
ENDRESS PK, DOYLE JA, 2OO9. Reconstructing the ancestral angiosperm flower and its initial specializations[J]. Amer J Bot, 96(1): 22-66.   
FAWCETT JA, MAERE S, VAN DE PEER Y, 2O09. Plants with double genomes might have had a better chance to survive the Cretaceous-Tertiary extinction event[J]. Proc Nat Acad Sci USA, 106(14): 5737-5742.   
FRIIS EM, PEDERSEN KR, SCHONENBERGER J,2006.Normapolles plants: A prominent componentof the Cretaceous rosid diversification[J]. Plant Syst Evol, 26O: 107-140.   
FU Q, DIEZ JB, POLE M, et al.，2018. An unexpected noncarpellate epigynous flower from the Jurassic of China[J]. Elife,7: e38827.   
GAO Z, BARRY AT, 1989. A review of fossil cycad megasporophylls,with new evidence of Crossozamia pomel and its associated leaves from the lower permian of Taiyuan, China[J]. REV Palaeobot Palynol, 60(3-4): 205-223.   
GRABHERR MG,HAAS BJ, YASSOUR M,et al.， 2011. Ful-length transcriptome assembly from RNA-Seq data without a reference genome[J]. Nat Biotechnol, 29(7): 644-652.   
HE ZL，ZHANG HK,GAO SH,et al.，2016. Evolview v2: An online visualization and management tool for customized and annotated phylogenetic trees[J]. Nucl Acid Res, 44(W1): 236-241.   
HERENDEEN PS,1995.The enigma of angiosperm origins[J]. Earth-Sci Rev, 39(1): 253-254.   
KATOH K, STANDLEY DM, 2013. MAFFT multiple sequence alignment software version 7: Improvements in performance and usability[J]. Mol Biol Evol, 30(4): 772-780.   
KUMAR S, STECHER G, SULESKI M, et al.,2017. TimeTree: A Resource for 598 Timelines, Timetrees,and Divergence Times[J]. Mol Biol Evol, 34: 1812-1819.   
LANFEAR R, FRANDSEN PB,WRIGHT AM, et al.,2016.PartitionFinder 2: New methods for selecting partitioned models of evolution formolecular and morphological phylogenetic analyses[J]. Mol Biol Evol, 34(3): 772-773.   
LU LM, MAO LF, YANG T, et al., 2O18. Evolutionary history of the angiosperm flora of China[J]. Nature, 554(1): 234-238.   
LI HT, YI TS, GAO LM, et al., 2019. Origin of angiosperms and the puzzle of the Jurassic gap. Nat Plants, 5(1): 461-470.   
MAGALLON S,2010. Using fossls to break long branches in molecular dating: A comparison of relaxed clocks applied to the origin of angiosperms[J]. Syst Biol, 59(4): 384-399.   
MOORE MJ, HASSAN N, GITZENDANNER MA,et al., 2011. Phylogenetic Analysis of the Plastid Inverted Repeat for 244 Species: Insights into Deeper-Level Angiosperm Relationships from a Long, Slowly Evolving Sequence Region[J]. Int JPlant Sci, 172(4): 541-558.   
MOORE MJ, SOLTIS PS,BELL CD,et al.，2010.Phylogenetic analysis of 83 plastid genes further resolves the early diversification of eudicots[J]. Proc Nat Acad Sci USA,107(10): 4623-4628.   
NGUYEN LT, SCHMIDT HA, VON HAESELER A, et al.,2015. IQ-TREE: A fast and effective stochastic algorithm for estimating maximum-likelihood phylogenies[J]. Mol Biol Evol, 32(1): 268-274.   
QIU YL,LI LB, WANG B,et al., 2010. Angiosperm phylogeny inferred from sequences of four mitochondrial genes[J]. JSE, 48(6): 391-425.   
RUHFEL BR，GITZENDANNER MA， SOLTIS PS， et al.， 2014. From algae to angiosperms-inferring the phylogeny of green plants (Viridiplantae） from 36O plastid genomes[J]. Bmc Evol Biol,14(1): 23.   
SMITH SA, BEAULIEU JM, DONOGHUE MJ, 2010. An uncorrelated relaxed-clock analysis suggests an earlier origin for flowering plants[J]. Proc Nat Acad Sci USA,1O7(13): 5897-5902.   
SMITH SA,DUNN CW,2008. Phyutility: A phyloinformatics tool for trees, alignments and molecular data[J]. Bioinformatics, 24(5): 715-716.   
SOLTIS DE， SMITH SA,CELLINESE N, et al.， 2011. Angiosperm phylogeny: 17 genes, 640 taxa[J]. Amer JBot, 98(4): 704-730.   
STAMATAKIS A, 2014. RAxML Version 8: A tool for Phylogenetic Analysis and Post-Analysis of Large Phylogenies[J]. Bioinformatics,30(9): 1312-1313.   
TAKAHASHI M, CRANE PR, MANCHESTER SR,2002. Hironoia fusiformis gen. et sp. nov., A cornalean fruit from the Kamikitaba locality (Upper Cretaceous，Lower Coniacian） in northeastern Japan[J]. JPlant Res,115: 463-473.   
THE ANGIOSPERM PHYLOGENY GROUP, 2016. An update of the Angiosperm Phylogeny Group classification for the orders and families of flowering plants: APG IV[J]. Bot JLinn Soc, 181(1): 1-20.   
VAN DS, 2000. Graph Clustering by Flow Simulation[M]. University of Utrecht.   
VON HAESELER A，MINH BQ，NGUYEN MAT，2013.Ultrafast Approximation for Phylogenetic Bootstrap[J]. Mol Biol Evol, 30(5): 1188-1195.   
WICKETT NJ, MIRARAB S,NGUYEN N, et al.， 2014. Phylotranscriptomic analysis of the origin and early diversification of land plants[J]. Proc Nat Acad Sci USA,111(45): 4859-4868.   
WORBERG A, QUANDT D, BARNISKE AM, et al., 2OO7. Phylogeny of basal eudicots: Insights from non-coding and rapidly evolving DNA[J]. ORG DIVERS EVOL,7(1): 55-77.   
Yang Z，2007. PAML 4: Phylogenetic analysis by maximum likelihood[J]. Mol Biol Evol, 24:1586-1591.   
YANG Y, MOORE MJ, BROCKINGTON SF, et al., 2015. Dissecting Molecular Evolution in the Highly Diverse Plant Clade Caryophyllales Using Transcriptome Sequencing[J]. Mol Biol EVOL,32(8): 2001-2014.   
YANG Y, SMITH SA, 2014. Orthology inference in nonmodel organisms using transcriptomes and low-coverage genomes: Improving accuracy and matrix occupancy for phylogenomics[J]. Mol Biol Evol, 31(11): 3081-3092.

ZENG LP, ZHANG N, ZHANG Q, et al., 2017. Resolution of deep eudicot phylogeny and their temporal diversification using nuclear genes from transcriptomic and genomic datasets[J]. New Phytol, 214(3): 1338-1354. ZENG LP, ZHANG Q, SUN RR, et al., 2014. Resolution of deep angiosperm phylogeny using conserved nuclear genes and estimates of early divergence times[J]. Nat Comm,5(1): 4956. ZHANG C, SAYYARI E, MIRARAB S,2017. ASTRAL-II: Increased Scalability and Impacts of Contracting Low Support Branches[J]. RECOMB-CG, Springer, Cham: 53-75. ZHANG N, ZENG LP, SHAN HY, et al.， 2O12. Highly conserved low-copy nuclear genes as effective markers for phylogenetic analyses in angiosperms[J].New Phytol,195(4): 923-937.