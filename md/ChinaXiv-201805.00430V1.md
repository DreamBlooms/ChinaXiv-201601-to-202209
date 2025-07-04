# 雨生红球藻低覆盖度基因组草图分析

陈军①②，郑华军③\*，刘亚铭①②，赵国屏③，秦松①\*$\textcircled{1}$ 中国科学院烟台海岸带研究所海岸带生物学与生物资源利用重点实验室,山东烟台 264003$\textcircled{2}$ 中国科学院大学，北京100049$\textcircled{3}$ 上海人类基因组研究中心，上海201203

摘要：开展雨生红球藻基因组测序研究，对于解读绿藻起源与进化及生物逆境胁迫响应机理，及推动雨生红球藻产业发展都具有重要意义。利用 Illumina Hiseq 2500 对雨生红球藻(Haematococcus pluvialis)进行高通量测序，获得低覆盖度全基因组草图。通过计算k-mer分布预测该基因组草图大小约为547 Mbp,GC含量为 $5 9 . 2 \%$ ，为纯合或单倍体。共得到11,059个预测基因，平均基因长度为1,711bp，平均CDS长度为681bp；平均每个基因包含3.2个外显子，外显子平均长度为353 bp。代谢通路分析表明，具有完整的糖酵解、三羧酸循环、磷酸戊糖途径、嘌呤和嘧啶合成等基本代谢通路。

关键词：雨生红球藻；基因组测序；基因预测；功能注释

# Title: The analysis of the low coverage Haematococcus pluvialis draft genome

Chen Jun@②, Zheng Hua-jun③\*, Liu Ya-ming@②, Zhao Guo-ping?, Qin Song①\* $\textcircled{1}$ Key Laboratory of Coastal Biology and Bioresource Utilization,Yantai Institute of Coastal Zone Research, Chinese Academy of Sciences, Yantai 264003 $\textcircled{2}$ University of Chinese Academy of Sciences, Beijing 101418 $\textcircled{3}$ Chinese National Human Genome Center at Shanghai, Shanghai 201203

Keywords: Haematococcus pluvialis; genome sequencing; gene prediction; gene functional annotation Abstract: The investigation on the genomic study of Haematococcus pluvialis would be significant to explore the origin and evolution of green algae and the stress responses in Haematococcus pluvialis,and promote the development of Haematococcus pluvialis industry.The low-coverage draft genome of Haematococcus pluvialis was constructed by the Iumina Hiseq 2500 platform. The predicted genome size was approximately 547 Mbp, with the GC content of $5 9 . 2 \%$ by calculating K-mer distribution. The draft genome contained 11,053 predicted protein-coding genes and the average gene size and CDS were 1,711 and 681 bp; every gene contained 3.2 exons and the size of exon was 353 bp in average.The analysis of metabolic pathway indicated that the low-coverage genome contained whole glycolysis,tricarboxylic acid cycle,phosphopentose,purine and pyrimidine synthesis and other basic metabolism pathway.

雨生红球藻（Haematococcus pluvialis Flotow 1844）是一种单细胞真核微藻，隶属绿藻门（Chlorophyta），绿藻纲（Chlorophyceae），团藻目（Volvocales）,红球藻科（Haematococcaceae）,红球藻属（Haematococcus），分布在各种小水体和潮湿土壤[1]。雨生红球藻具有复杂的生活周期，分为游动细胞、不动细胞、动孢子和不动孢子期[2.3]。在特定环境条件下，如高光、高盐、缺氮等，雨生红球藻从游动细胞转变为不动孢子，并累积虾青素，约占其细胞干重的 $1 \% - 4 \%$ ，被认为是虾青素的最好来源[4,5]。天然虾青素具有超强的抗氧化活性，有“超级维生素E”之美誉，生产能力远不能满足市场需求，国际市场价格高达10,000美元/kg，大约是人工合成虾青素的200倍，广泛应用在食品保健品、化妆品、饵料饲料等领域[5.6]。

为解读雨生红球藻合成虾青素的分子机制，摸清虾青素代谢机理，指导选育优良品种，建立雨生红球藻合成虾青素代谢模型，近年来，雨生红球藻分子生物学研究取得了很大进步。虾青素在雨生红球藻中的代谢途径已经基本清楚[7-9]。伴随着高通量测序技术的发展,雨生红球藻转录组学[10-14]、蛋白组学[15-17]和代谢组学[18,19]研究也不断增多。Chen 等[13]基于虾青素在雨生红球藻细胞内以虾青素酯的形式存在的特点，利用转录组学和代谢组学的手段，阐释了雨生红球藻虾青素和脂肪酸合成的协同调控分子机理，表明虾青素酯化过程对于虾青素的形成和积累具有推动作用。Gwak 等[14]利用转录组学和脂组学的手段，分析了雨生红球藻绿色游动细胞和红色不动孢子期细胞虾青素合成和脂肪酸代谢规律，重点阐述了高光胁迫条件下胞囊形成过程中，雨生红球藻虾青素合成和脂肪酸代谢协同调控机制。

然而，外界逆境如何精准调控雨生红球藻合成虾青素？雨生红球藻合成虾青素代谢通路中编码关键限速酶基因上游有哪些顺式作用元件？这些顺式作用元件如何与转录因子相互作用？雨生红球藻积累虾青素是细胞响应外界逆境，清除活性氧自由基时产生的副产物还是细胞产生虾青素的目的是为了清除自由基？雨生红球藻生物合成虾青素仍有诸多问题需要解决[20]，而通过传统 PCR、转录组学等方法获得的序列，信息往往不全面，因此，很有必要对雨生红球藻进行全基因组测序，以便于对其遗传信息进行更加系统的研究。本研究利用第二代高通量测序仪Illumina Hiseq 2500 对雨生红球藻进行低覆盖度全基因组测序，预测了雨生红球藻基因组大小等基因组基本特征,为绘制高质量雨生红球藻基因组精细图作了准备。

# 1．材料和方法

# 1.1实验材料及培养条件

本研究使用的雨生红球藻（Haematococcus pluvialis）购自英国CCAP藻种库，现保存于中国科学院烟台海岸带研究所海岸带生物学与生物资源利用重点实验室。雨生红球藻接种于 BBM培养基，于 $2 5 \mathrm { { ^ \circ C } }$ 光照条件下静止培养，光照强度为 $4 0 \mu \mathrm { m o l } / ( \mathrm { m } ^ { 2 } { \cdot } \mathrm { s } )$ ，光/暗周期为 $1 2 \mathrm { h } / 1 2 \mathrm { h }$ 。

# 1.2IIumina基因组文库构建和测序

取处于对数生长期的雨生红球藻细胞，利用天根新型植物基因组DNA 提取试剂盒（DP320-02，北京）提取基因组，然后使用 $1 \%$ 的琼脂糖凝胶电泳进行检测，并利用超微量分光光度计测定DNA浓度和纯度（A260/A280）。获得高质量的基因组后，构建Pair-end文库。利用Covaris S2（Covaris，美国）仪器将 DNA打断至 400 bp 大小的片段，利用 TruSeqTMDNA Sample Prep Kit－Set A (Ilumina，美国）制备文库，最后切胶回收350-450 bp 的片段。取 $1 0 \mathrm { n g }$ 构建好的文库DNA，用 TruSeq PECluster Kit (Illumina，美国）在cBot中进行cluster generation，然后在Ilumina HiseqTM2500 中进行双向测序。

# 1.3数据处理

通过高通量测序得到的原始数据使用软件 FASTX-Toolkit（http://hannonlab.cshl.edu/fastx_toolkit/）得到clean 序列，具体步骤如下：(1)使用 fastx_clipper 去除 reads 中的接头序列；(2)使用 fastq_quality_filter 从read的3端到5'端方向开始去除N至第一个不是N的碱基；(3)使用 fastq_quality_filter从read 的3'端到 5'端方向开始去除连续出现的低质量碱基 $( \mathsf { q } < 5 )$ ，当去除低质量的clean reads长度低于 50bp 时删除 read本身及其配对的序列；(4)使用本地脚本配对pair end reads。

然后利用序列综合分析软件jellyfish3.3.1绘制 $\mathbf { k }$ -mer分布图，并参照公式 $\scriptstyle \mathrm { M = N ^ { * } ( L - K + 1 ) / L }$ ，计算实际测序深度，其中N代表实际测序深度，M代表 $\mathbf { k }$ -mer 曲线的峰值，L代表reads 的长度，k代表字符串的碱基数量。最后，把全部序列长度除以实际测序深度N，预测基因组大小。

将 llumina 数据利用软件Velvet[21l进行拼接，组装获得基因组草图。然后将拼接组装后的contig，与NCBI中现有的1,002条雨生红球藻 EST序列进行比对，分析基因组草图覆盖率。拼装出的基因组草图，使用 Augustus[22进行基因预测。将预测基因的编码蛋白，通过blastp 分别与 NCBI的非冗余蛋白数据库(nr)、KEGG (Kyoto Encyclopedia of Genes and Genomes)和 UNIPORT(Universal Protein)数据库比对,进行功能注释，比对参数设为：E-value $< 1 \mathrm { e } ^ { - 5 }$ 。依据注释结果，绘制KEGG 代谢通路图；利用CDD 数据库[23]和RPS-Blast进行KOG分类，进一步进行功能注释。

# 2.结果与分析

# 2.1数据预处理和拼接

测序共得到38,189,673对序列，测序长度是 $2 ^ { * } 1 5 0 \mathrm { b p }$ ，总碱基数是11.45G，过滤得到高质量基因组序列37,185,329对，碱基数约 $1 0 . 5 5 \mathrm { G }$ 。通过对原始数据碱基组成分布和原始数据碱基质量分布进行分析，发现该文库每个位置上，A、C、G、T在开始有所波动，后面会趋于稳定。一般情况下A与T相等，C与G相等，各碱基所占百分比会因物种差异而不同。该文库碱基分布均匀，N的比例非常低，碱基质量良好，可用于后续分析。

# 2.2基因组大小预测与杂合度分析

k-mer 是指将 reads分成包含 $\mathbf { k }$ 个碱基的字符串，一般长度为L的reads可以分成 $\mathbf { L - k + } 1$ 个 $\mathbf { k }$ -mers。本研究中每条150 bp 的序列可以拆成134个17bp 长的字符串，得到测序reads 所有17-mer 片段，然后统计各17-mer 及其出现的次数（k-mer frequnce）。以出现次数（depth）为横坐标，以出现多次的片段总数为纵坐标作图，那么曲线的峰值M，就接近实际测序深度 $\mathrm { ~ N ~ }$ 。参照公式： $\scriptstyle \mathrm { M = N ^ { * } ( L - K + 1 ) / L }$ ，然后把全部序列长度除以实际测序深度N，获得预测的基因组大小。然后利用序列综合分析软件 jellyfish3.3.1,统计出10.55Gb clean reads中的17-mer，并作图（图1)，得出 $\mathbf { M } { = } 1 7$ ，实际测序深度 $\Nu { = } 1 9$ 。一般认为只出现1次或几次的17-mer 是测序错误，根据图3，最左侧的谷底17-mer对应深度为8，因此去除出现频率 $< 8$ 的全部17-mer，则有效数据为全部数据的 $9 8 . 5 \%$ 。所以雨生红球藻的基因组大小估计为$\mathrm { G } { = } 1 0 , 5 5 6 , 7 5 1 , 7 9 0 ^ { * } 0 . 9 8 5 / 1 9 { = } 5 4 7 \mathrm { M b }$ 。同时，由图3可以看出只有一个峰，表示雨生红球藻为纯合或单倍体。

![](images/c0c507012eb76e21d1187957a64c986b3bbe9663501f2e010381febc53755ebd.jpg)  
图1雨生红球藻基因组序列的17-mer分析Fig.1 17-mer analysis of genome contigs in Haematococcus pluvialis

# 2.3序列组装和基因组草图覆盖率评价

表1不同k-mer下的基因组组装结果  
Table 1 the result of genome assemble with different $\mathbf { k }$ -mer value   

<html><body><table><tr><td>k-mer</td><td>Contigs Number</td><td>Size (bp)</td><td>Ave Length (bp)</td><td>Reads Usage</td></tr><tr><td>35</td><td>113061</td><td>66423650</td><td>587</td><td>24.60%</td></tr><tr><td>45</td><td>118556</td><td>87506031</td><td>738</td><td>30.60%</td></tr><tr><td>55</td><td>63142</td><td>96909627</td><td>1534</td><td>34.80%</td></tr><tr><td>65</td><td>58115</td><td>101883098</td><td>1753</td><td>39.10%</td></tr><tr><td>75</td><td>56423</td><td>104818003</td><td>1857</td><td>42.00%</td></tr><tr><td>85</td><td>58995</td><td>106127310</td><td>1798</td><td>43.60%</td></tr><tr><td>95</td><td>66985</td><td>105643283</td><td>1577</td><td>44.40%</td></tr></table></body></html>

利用生物信息学软件Velvet对Ilumina数据进行拼接，得到了不同 $\mathbf { k }$ -mer值下基因组组装结果，如表1可见，不同的 $\mathbf { k }$ -mer 值对contig的数量和总长度影响均较显著。一般选择拼装结果，采取的原则是contig 尽量少，contig 的长度尽量大。所以，在一定的范围内，就是选择contig平均长度最大（contig 的长度除以 contig数目，获得contig平均长度)的拼装结果。故本研究中采用 $\mathbf { k }$ -mer 值为75的情况下的拼装结果，即获得56,423条contig，总长度为104,818,003 bp，contig 的平均长度为1,857bp，平均GC含量为 $5 9 . 2 \%$ 。由于有效覆盖率只有 17倍，因此只能组装出部分基因组序列。利用 NCBI中现有的1,002 条 EST序列与测序获得的 contig比对，结果显示910条序列可以比对到测序拼接的基因组，占总数的 $9 0 . 8 2 \%$ ；495条EST $90 \%$ 以上序列被单个contig 覆盖，比例为49.40；782条EST $50 \%$ 以上序列可以被单个contig覆盖，比例为78.04（表2）。将目前NCBI中现有的EST序列与我们预测的基因进行比对，有412条EST序列可以匹配，占总数的 $4 1 . 1 2 \%$ 。雨生红球藻EST序列覆盖度分析表明本草图覆盖了雨生红球藻基因编码区的 $90 \%$ 左右，表明获得了雨生红球藻低覆盖度基因组草图。

表2以已知雨生红球藻EST序列评价基因组草图完整性  
Table 2 Assessment the sequence coverage of H. pluvialis draft genome using known ESTs   

<html><body><table><tr><td>长度覆盖率 (%)</td><td>匹配的EST累积数目 累积比例 (%)</td></tr><tr><td>100</td><td>264 26.347</td></tr><tr><td>90</td><td>495 49.401</td></tr><tr><td>80</td><td>576 57.485</td></tr><tr><td>70</td><td>664 66.267</td></tr><tr><td>60</td><td>727 72.554</td></tr><tr><td>50</td><td>782 78.043</td></tr><tr><td>40</td><td>821 81.936</td></tr><tr><td>30</td><td>849 84.73</td></tr><tr><td>20</td><td>877 87.524</td></tr><tr><td>10</td><td>910 90.818</td></tr></table></body></html>

利用测序获得的contig与 NCBI中现有的藻类基因组序列进行比对，如表3所示，共有 4964条contig可以比对到雨生红球藻基因序列，匹配的contig 总长度为9534797bp，比对长度为696150；其次，匹配到莱茵衣藻（Chlamydomonas reinhardtii）的contig 数量为1977条，匹配的contig 总长度为 4068934bp，比对长度为246989bp。莱茵衣藻是绿藻门模式生物，与雨生红球藻同属绿藻门，团藻属，匹配同源性较高符合预期。

表3以已知NCBI藻类基因组序列评价基因组草图完整性  
Table 3 Assessment the sequence coverage of H. pluvialis draft genome using known algal genome sequences   

<html><body><table><tr><td colspan="4">updated from NCBI</td></tr><tr><td>匹配基因组</td><td>匹配的contig数量</td><td>匹配的contig总长度（bp）</td><td>比对长度 (bp)</td></tr><tr><td>雨生红球藻 (Haematococcus pluvialis)</td><td>4964</td><td>9534797</td><td>696150</td></tr><tr><td>莱茵衣藻 (Chlamydomonas reinhardtii)</td><td>1977</td><td>4068934</td><td>246989</td></tr><tr><td>团藻</td><td>401</td><td>800015</td><td>45726</td></tr><tr><td>(Volvox carteri f. nagariensis) 多变小球藻</td><td>347</td><td>747501</td><td>38375</td></tr><tr><td>(Chlorella variabilis) 胶球藻 C-169</td><td></td><td></td><td></td></tr><tr><td>(Coccomyxa subellipsoidea C-169)</td><td>178</td><td>352938</td><td>20464</td></tr><tr><td>原壳小球藻</td><td>165</td><td>316284</td><td>16626</td></tr></table></body></html>

# 2.4基因预测与功能注释

用拼装出的基因组，使用 Augustus 进行基因预测，共得到11,059 个预测基因，平均基因长度为1,711 bp,平均 CDS 长度为681bp；平均每个基因包含3.2个外显子，外显子平均长度为 $3 5 3 ~ \mathrm { b p }$ 。将预测基因的编码蛋白，通过 blastp 分别与 NCBI 的非冗余蛋白数据库（nr）、KEGG(Kyoto Encyclopedia of Genes and Genomes)和 UNIPORT(Universal Protein)数据库比对，进行功能注释，结果共有6,890 个蛋白具有明确的生物学功能，3,117个蛋白具有KEGG 的ortholog，注释率为 $6 2 . 3 0 \%$ 。利用预测的6,890个蛋白与NCBI中现有的藻类蛋白序列进行比对，如表4所示，预测基因所匹配的同源性最高的蛋白所属的物种分别是团藻（Volvox carterif.nagariensis）、莱茵衣藻（Chlamydomonas reinhardti）、单针藻（Monoraphidium neglectum）、胶球藻C-169（Coccomyxa subellpsoidea C-169）、多变小球藻（Chlorella variabilis）、原壳小球藻（Auxenochlorellaprotothecoides）、雨生红球藻（Haematococcus pluvialis）和盐生杜氏藻（Dunaliella salina）。其中，E-value为 $1 0 ^ { - 3 }$ 的情况下，预测蛋白与团藻蛋白序列匹配的数目为2148条，占比为 $2 4 . 0 6 \%$ 。

根据KEGG注释结果生成代谢通路图，共获得230个代谢通路图，具有完整的糖酵解、三羧酸循环、磷酸戊糖途径、嘌呤和嘧啶合成等基本代谢通路，说明拼装得到的序列中包含了基本的必需基因信息。其中注释率较高的代谢通路主要包括：碳水化合物代谢（Carbohydrate metabolism），氨基酸代谢（Amino acidmetabolism），能量代谢（Energy metabolism），蛋白质翻译（Translation），辅因子和维生素代谢（Metabolismof cofactors and vitamins），蛋白质折叠、分选与降解（Folding,sorting and degradation），膜转运（Membranetransport），信号转导（Signaltransduction），脂代谢（Lipid metabolism）等通路（图2）。

表4以已知藻类蛋白序列评价基因组草图完整性  
Table 4 Assessment the sequence coverage of $H .$ pluvialis draft genome using known algal protein sequences   

<html><body><table><tr><td rowspan="2">最佳匹配物种</td><td colspan="2">E-value=10-3</td><td colspan="2">E-value=10-10</td><td colspan="2">E-value=10-20</td></tr><tr><td>数目</td><td>比例</td><td>数目</td><td>比例</td><td>数目</td><td>比例</td></tr><tr><td>团藻</td><td>2148</td><td>24.06%</td><td>1900</td><td>23.57%</td><td>1511</td><td>21.92%</td></tr><tr><td>Volvox carteri f. nagariensis 莱茵衣藻</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Chlamydomonas reinhardtii</td><td>1820</td><td>20.39%</td><td>1618</td><td>20.07%</td><td>1315</td><td>19.08%</td></tr><tr><td>单针藻 Monoraphidium neglectum</td><td>516</td><td>7.49%</td><td>433</td><td>6.28%</td><td>313</td><td>4.54%</td></tr><tr><td>胶球藻</td><td>262</td><td>2.93%</td><td>225</td><td>2.79%</td><td>163</td><td></td></tr><tr><td>Coccomyxa subellipsoidea C-169</td><td></td><td></td><td></td><td></td><td></td><td>2.37%</td></tr><tr><td>多变小球藻 Chlorella variabilis</td><td>172</td><td>1.93%</td><td>143</td><td>1.77%</td><td>90</td><td>1.31%</td></tr><tr><td>原壳小球藻</td><td>72</td><td>0.81%</td><td>56</td><td></td><td></td><td></td></tr><tr><td>Auxenochlorella protothecoides 雨生红球藻</td><td></td><td></td><td></td><td>0.69%</td><td>38</td><td>0.55%</td></tr><tr><td>Haematococcus pluvialis</td><td>68</td><td>0.76%</td><td>68</td><td>0.84%</td><td>66</td><td>0.96%</td></tr><tr><td>盐生杜氏藻</td><td>41</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Dunaliella salina</td><td></td><td>0.45%</td><td>39</td><td>0.48%</td><td>37</td><td>0.54%</td></tr><tr><td>其他</td><td>1260</td><td>14.11%</td><td>1011</td><td>12.54%</td><td>796</td><td>11.55%</td></tr></table></body></html>

![](images/df72ebcd96dfd38640eae6b24e1db07464d499ffe22f5dfdd9d1e410666563d3.jpg)  
图2雨生红球藻预测蛋白的KEGG注释分析  
Fig.2KEGG analysis for predicted proteins of Haematococcus pluvialis

利用CDD数据库和RPS-Blast进行KOG分类，结果共有5,233个蛋白被KOG分类注释，按照功能不同可分成 26 个类群，主要包括一般功能预测（General function prediction only），翻译后修饰、蛋白折叠及操纵子（Postranslational modification,protein turnover,chaperones），信号转导机制（Signal transductionmechanisms），氨基酸转运与代谢（Amino acid transport and metabolism），蛋白翻译、核糖体结构与合成（Translation,ribosomal structure and biogenesis），碳水化合物转运与代谢（Carbohydrate transport andmetabolism）（图3）。在不同E-value下的KOG比对结果如表5所示。

表5预测蛋白在不同E-value下的KOG分类  
Table 5 Assessment the KOG analysis for predicted proteins of Haematococcus pluvialis under diferent E-values   

<html><body><table><tr><td>KOG分类</td><td>1.00E-03</td><td>1.00E-05</td><td>1.00E-10</td><td>coccuspiaviatts 1.00E-15</td><td>1.00E-20</td><td>L 1.00E-25</td><td>Warues 1.00E-30</td></tr><tr><td>Amino acid transport and metabolism</td><td>363</td><td>343</td><td>310</td><td>281</td><td>245</td><td>221</td><td>192</td></tr><tr><td>Carbohydrate transport and metabolism</td><td>334</td><td>314</td><td>256</td><td>213</td><td>179</td><td>149</td><td>129</td></tr><tr><td>Cell cycle control, cell division,</td><td>112</td><td>97</td><td>70</td><td>59</td><td>46</td><td>35</td><td>27</td></tr><tr><td>chromosome partitioning Cell motility</td><td></td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>Cell wall/membrane/envelope biogenesis</td><td>1 57</td><td>50</td><td>34</td><td>29</td><td>17</td><td>14</td><td>14</td></tr><tr><td>Chromatin structure and dynamics</td><td>73</td><td>67</td><td>53</td><td>48</td><td>43</td><td>34</td><td>23</td></tr><tr><td>Coenzyme transport and metabolism</td><td>124</td><td>115</td><td>101</td><td>87</td><td>81</td><td>71</td><td>56</td></tr><tr><td>Cytoskeleton</td><td>213</td><td>179</td><td>149</td><td>124</td><td>107</td><td>91</td><td>74</td></tr><tr><td> Defense mechanisms</td><td>21</td><td>20</td><td>16</td><td>6</td><td>2</td><td>2</td><td>2</td></tr><tr><td>Energy production and conversion</td><td>286</td><td>269</td><td>243</td><td>207</td><td>184</td><td>162</td><td>141</td></tr><tr><td>Extracellular structures</td><td>49</td><td>21</td><td>5</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td> Function unknown</td><td>177</td><td>146</td><td>103</td><td>70</td><td>50</td><td>38</td><td>25</td></tr><tr><td>General function prediction</td><td>482</td><td>410</td><td>293</td><td>236</td><td>196</td><td>167</td><td>132</td></tr><tr><td>Inorganic ion transport and metabolism</td><td>231</td><td>201</td><td>161</td><td>126</td><td>100</td><td>84</td><td>64</td></tr><tr><td>Intracellular trafficking, secretion, and Qesicular transport</td><td>220</td><td>191</td><td>170</td><td>139</td><td>111</td><td>91</td><td>79</td></tr><tr><td> Lipid transport and metabolism</td><td>209</td><td>193</td><td>159</td><td>134</td><td>111</td><td>88</td><td>76</td></tr><tr><td>Nuclear structure</td><td>16</td><td>14</td><td>10</td><td>7</td><td>5</td><td>4</td><td>3</td></tr><tr><td>Nucleotide transport and metabolism</td><td>148</td><td>141</td><td>130</td><td>110</td><td>97</td><td>83</td><td>66</td></tr><tr><td>Posttranslational modification, protein turnover, chaperones</td><td>470</td><td>434</td><td>364</td><td>312</td><td>259</td><td>218</td><td>185</td></tr><tr><td>Replication, recombination and repair</td><td>152</td><td>138</td><td>114</td><td>100</td><td>88</td><td>72</td><td>58</td></tr><tr><td> RNA processing and modification</td><td>278</td><td>261</td><td>229</td><td>190</td><td>158</td><td>130</td><td>110</td></tr><tr><td>Secondary metabolites biosynthesis, transport and catabolism</td><td>227</td><td>216</td><td>189</td><td>156</td><td>133</td><td>96</td><td>71</td></tr><tr><td>Signal transduction mechanisms</td><td>391</td><td>325</td><td>253</td><td>200</td><td></td><td></td><td></td></tr><tr><td>Transcription</td><td>240</td><td>195</td><td>142</td><td>109</td><td>157 91</td><td>117 69</td><td>88 57</td></tr><tr><td>Translation, ribosomal structure and</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>biogenesis</td><td>359</td><td>346</td><td>308</td><td>271</td><td>226</td><td>198</td><td>167</td></tr><tr><td>总计</td><td>5233</td><td>4687</td><td>3863</td><td>3216</td><td>2688</td><td>2236</td><td>1841</td></tr></table></body></html>

![](images/b38e861f3b4e1a58befd96e5a196e53bb4092be054d3fb059814fd894db34221.jpg)  
图3雨生红球藻预测蛋白的KOG分类

Fig.3KOG analysis for predicted proteins of Haematococcus pluvialis

# 3．讨论

真核藻类起源于内共生事件，种类繁多，进化地位特殊、过程复杂。内共生学说认为，原核生物蓝藻经过初级内共生以后，形成绿藻、红藻和灰藻；在绿藻和红藻的基础上，经过次级内共生形成了其他微藻，例如隐藻（Cryptophycean）。其中，绿藻形态多样，光合色素系统与高等植物相似，既含有叶绿素a，也含有叶绿素b，其进化地位虽介于高等植物和原核蓝藻之间，但又不可简单的看成是介于微生物和高等植物之间的过渡类群，长期以来也一直是植物学界和藻类学界研究的热点。开展雨生红球藻基因组测序研究，对于解析绿藻门演化趋向、真核藻类起源与演化等方面都具有极其重要的意义。

雨生红球藻分布广泛，耐受性强，能够适应缺氮、高光、低氧、高盐等特殊逆境，并合成虾青素。复杂的逆境孕育了其精细的信号转导系统和特殊的次生代谢系统，是研究生物逆境响应的理想材料。开展雨生红球藻的全基因组测序研究，将为建立雨生红球藻的基因组、转录组、代谢物组等系统生物学模式研究体系，深入地考察雨生红球藻能量存储和转化、逆境胁迫响应机理等一系列复杂性状的网络调控机制，从而建立雨生红球藻的基因调控网络的功能基因组学研究模型,为直接指引通过代谢工程手段和合成生物学的思路改造和构建高质量的藻株提供重要参考。

综上，无论是从研究真核藻类起源与进化的角度，还是推动雨生红球藻产业发展的层面，雨生红球藻的全基因组测序都亟待尽快被完成。本研究利用第二代高通量测序技术开展了雨生红球藻低覆盖度全基因组测序，并预测了雨生红球藻基因组大小等基因组基本特征，为绘制高质量雨生红球藻基因组精细图作了准备，但与近年来报道的高质量绿藻基因组精细图谱比较仍有差距。例如，Roth 等（2017）采用三代 Pacbio 和二代基因组测序技术相结合，完成了佐夫色绿藻染色体水平的基因组组装，共组装出19条染色体，发现编码基因1.5万多个。然后，采用转录组学技术和通过测定藻株类胡萝卜素含量，系统解读了雨生红球藻野生株和突变株响应不同光强胁迫条件时的虾青素积累机制。该研究不仅绘制了高质量的佐夫色绿藻基因组，并详细解读了有关该藻的重要科学问题，如不同光强胁迫条件下虾青素积累机制，为后续利用代谢工程等手段构建优良藻株提供了理论依据，值得后续开展雨生红球藻全基因组精细图谱绘制时参考。

开展雨生红球藻全基因组测序及精细图谱的绘制，需要注意以下几方面问题：（1）建立雨生红球藻无菌化培养体系。雨生红球藻常常伴有共生菌，且利用EG:JM等有机培养基培养时容易被细菌污染，开展全基因组测序研究需要特别注意无菌化处理，以避免测序获得的基因组拼接困难等问题。郑凌凌等（2017）研究发现，对于雨生红球藻FACHB-712藻株可选择青霉素、庆大霉素、卡那霉素两种或3种依次加入，实现藻株除菌操作[25]。本研究在开展全基因组测序前，特别注意了染菌问题，先后通过反复纯化、显微镜镜检，16S rRNA 测序等手段，确保测序样品未受到细菌污染。（2）建议将二代测序技术与三代测序技术结合运用。基于本研究预测发现，雨生红球藻基因组大约500M左右，且应该含有多条线性染色体，建议采用最新的第三代测序系统PacBioSMRT测序。该测序系统可以获得长达 $1 0 \mathrm { K b }$ 的reads，拼装效果较好。同时，辅以Illumina Hiseq2500 测序，可以校正 PacBio 测序中的单碱基 indel的错误，以便提高拼装结果的准确性。

# 参考文献：

[1]胡鸿钧，魏印心．中国淡水藻志-系统、分类及生态[M]．北京：科学出版社,2006. Hu H J, Wei Y X. The freshwater algae of China- Systematics, Taxonomy and Ecology[M]. Beijing: Science Press, 2006 (in Chinese).   
[2]刘建国，殷明焱，张京浦,etal．雨生红球藻的细胞周期初探．海洋与湖沼,2000,02:145-150. Liu JG, Yin M Y, Zhang JP,et al. Statues of cell cycle in Haematococcus pluvialis[J]. Oceanology et Limnologia Sinica, 2000,(02): 145-150 (in Chinese).   
[3]Kobayashi M, Kurimura Y, Kakizono T,et al.Morphological changes in the life cycle of the green alga Haematococcus pluvialis[J]. Journal of Fermentation and Bioengineering,1997,84(1): 94-97.   
[4] Lorenz R T, Cysewski G R. Commercial potential for Haematococcus microalgae as a natural source of staxanthin[J]. Trends in Biotechnology, 2000,18(4):160-167.   
[5] Borowitzka MA, High-value products from microalgae-their development and commercialisation[J]. Journal of Applied Phycology,2013, 25(3): 743-756.   
[6] Chen J,Wang Y,BenemannJR,etal.Microalgal industry in China: challengesand prospects[J].Journalof Applied Phycology, 2016, 28(2): 715-725.   
[7] Cui H L, Yu X N,Wang Y,et al.Evolutionary origins,molecular cloning and expression of carotenoid hydroxylases in eukaryotic photosynthetic algae[J]. BMC Genomics, 2013,14: 457.   
[8] HanD X,LiYT,Hu Q.Astaxanthin in microalgae: pathways,functions and biotechnological implications[J]. Algae,2013, 28(2): 131-147.   
[9]Lu YD,Jiang P,Liu SF,et al. Methyl jasmonate- or gibberellins A(3)-induced astaxanthin accumulation is associated with up-regulation of transcription of beta-carotene ketolase genes (bkts） in microalga Haematococcus pluvialis[J]. Bioresource Technology,2010,101(16): 6468-6474.   
[10]Gao Z Q,Li Y,Wu G X,et al. Transcriptome analysis in Haematococcus pluvialis: Astaxanthin induction by salicylic acid (SA) and jasmonic acid (JA)[J]. Plos One,2015,10(10): e0140609.   
[11]Li K, Cheng J,Lu H X,et al.Transcriptome-based analysis on carbon metabolism of Haematococcus pluvialis mutant under $1 5 \%$ CO2[J]. Bioresource Technology, 2017,233: 313-321.   
[12]Cheng J,Li K, Zhu Y X,etal.Transcriptome sequencing and metabolic pathways of astaxanthin accumulated in Haematococcus pluvialis mutant under $1 5 \%$ CO2[J]. Bioresource Technology,2017, 228: 99-105.   
[13]Chen G Q, Wang B B, Han D X,et al. Molecular mechanisms of the coordination between astaxanthin and fatty acid biosynthesis in Haematococcus pluvialis (Chlorophyceae)[J]. Plant Journal,2015,81(1): 95-107.   
[14]Gwak Y, Hwang Y S, Wang B B,et al. Comparative analyses of lipidomes and transcriptomes reveal aconcerted action of multiple defensive systems against photooxidative stress in Haematococcus pluvialis[J]. Journal of Experimental Botany,2014, 65(15): 4317-4334.   
[15]Wang S B,Chen F,Sommerfeld M,et al.Proteomic analysis of molecular response to oxidative stress by the green alga Haematococcus pluvialis (Chlorophyceae)[J]. Planta, 2004, 220(1): 17-29.   
[16]Kim JD,Lee WS,Kim B,et al.Proteomic analysis of protein expression patterns associated with astaxanthin accumulation by green alga Haematococcus pluvialis (Chlorophyceae） under high light stres[J]. Journal of Microbiology and Biotechnology, 2006,16(8): 1222-1228.   
[17]Gao Z Q, Miao X X, Zhang X W,et al. Comparative fatty acid transcriptomic test and iTRAQ-based proteomic analysis in Haematococcus pluvialis upon salicylic acid (SA) and jasmonic acid (JA) inductions[J].Algal Research-Biomass Biofuels and Bioproducts,2016,17: 277-284.   
[18]Su Y X, Wang JX, Shi ML,et al. Metabolomic and network analysis of astaxanthin-producing Haematococcus pluvialis under various stress conditions[J]. Bioresource Technology,2014,170: 522-529.   
[19]Lv H X, Xia F,Liu M,et al. Metabolomic profiling of the astaxanthin accumulation process induced by high light in Haematococcus pluvialis[J].Algal Research-Biomass Biofuels and Bioproducts,2016,20: 35-43.   
[20]Boussiba, S. Carotenogenesis in the green alga Haematococcus pluvialis: Cellular physiology and stress response[J]. Physiologia Plantarum,2000, 108(2): 111-117.   
[21]Zerbino DR,Birney E. Velvet: Algorithms forde novo short read asembly using de Bruijn graphs[J]. Genome Research, 2008,8(5): 821-829.   
[22]Stanke M,Schoffmann O,Morgenstern B,et al.Gene prediction in eukaryotes with a generalized hiden Markov model that uses hints from external sources[J]. BMC Bioinformatics,2006,7: 62.   
[23]Marchler-Bauer A,Bo Y, Han L,et al. CDD/SPARCLE: functional clasification of proteins via subfamily domain architectures[J]. Nucleic Acids Research, 2017, 45(D1): D200-D203.   
[24]Roth M S,Cokus SJ, Gallaher S D,et al.Chromosome-level genome asembly and transcriptome of the green alga Chromochloris zofingiensis illuminates astaxanthin production[J]. Proceedings of the National Academy of Sciences of the United States of America, 2017, E4296-E4305.   
[25]郑凌凌，张琪，李天丽,et al．雨生红球藻无菌化处理及其对生长和生理的影响[J]．福建师范大学学报(自 然科学版),2017,(01): 44-50. Zheng LL, Zhang Q，LiTL，et al.Axenation of Haematococcus pluvialis and the effects of axenic cultivation on the growth and physiology of the strain[J].Journal ofFujian Normal University (Natural Science Edition), 2017,33(1): 44-50 (in Chinese).