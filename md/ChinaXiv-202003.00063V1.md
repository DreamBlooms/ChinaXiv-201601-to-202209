# 烟草TIR-NBS基因家族的生物信息学分析

董亚萍1，杨仕梅¹，赵德刚1²，宋 莉1\*

1.贵州大学 生命科学学院/农业生物工程研究院，山地植物资源保护与种质创新教育部重点实验室，贵州省农业生物工程重点实验室，贵阳 550025；2.贵州省农业科学院，贵阳550006)

摘要：TIR-NBS基因是一类与植物抗病调节和生长发育密切相关的基因，其特征解析有助于对植物免疫和发育调节的认识。通过生物信息学分析方法，从基因鉴定、染色体分布、基因结构、蛋白性质和结构、信号肽、亚细胞定位和顺式作用元件等方面，对烟草TIR-NBS 基因家族进行鉴定和分子特性分析。研究发现，烟草TIR-NBS基因家族含有30条成员，分布在 21条染色体上，含有3\~8个保守基序；编码蛋白均为不稳定蛋白，无信号肽，主要分布于细胞核、细胞质和叶绿体中，二级结构以 $\mathbf {  { a } }$ -螺旋和无规则卷曲为主要构成元件；进化时主要受纯化选择作用，与番茄的TIR-NBS 基因亲缘关系最近；顺式作用元件分析表明其可能受光照、温度以及生长素、茉莉酸甲酯、脱落酸、水杨酸、赤霉素等激素调控。研究结果为进一步探究TIR-NBS基因的生物学功能及提高植物产量和品质提供了依据。

关键词：烟草，抗病调节，生长发育，植物免疫，TIR-NBS 基因家族，生物信息学分析中图分类号：Q943 文献标识码：A

# Bioinformatics analysis of tobacco TIR-NBS gene family

DONG Yaping 1, YANG Shimei1, ZHAO Degang 12, SONG Li 1\* (1．College ofLife Sciences and Institute ofAgro-Bioengineering,Guizhou University/The Key Laboratory of Plant ResourcesConservation and Germplasm Innovation in Mountainous Region(Ministry of Education)/ Guizhou Key Lab of Agro-Bioengineering,Guiyang 550025,China; 2. Guizhou Academy of Agricultural Sciences,Guiyang 550006, China)

Abstract: The TIR-NBS gene is a class of gene closely related to plant disease resistance regulation and growth and development， and its characteristic analysis contributes to the understanding of plant immunity and developmental regulation. Through bioinformatics analysis method,the TIR-NBS gene family of tobacco was identified and molecularly analyzed from the aspects of gene identification, chromosome distribution， gene structure, protein properties and structure, signal peptide, subcelllar localization and cis-acting elements.The study found that the TIR-NBS gene family contains 3O members,distributed on 21 chromosomes,containing 3\~8 conserved motifs；the encoded proteins are unstable proteins，no signal peptides，mainly distributed in the nucleus, cytoplasm and chloroplast . The secondary structure is characterized by $\mathfrak { a }$ -helix and random coiling; it is mainly selected by purification in evolution,and has the closest relationship with TIR-NBS gene of tomato; Analysis of cis-acting elements showed that it may be regulated by light, temperature,and hormones such as auxin, methyl jasmonate,abscisic acid, salicylic acid,and gibberellin. The results provided a basis for further exploring the biological functions of the TIR-NBS gene and improving plant yield and quality.

Key words: Nicotiana attenuata, disease resistance regulation, growth and development, plant immunity, TIR-NBS gene family, bioinformatics analysis

植物在长期遭受真菌、细菌、病毒等各种病原体侵袭和危害过程中，逐渐形成保护自身的抗病免疫机制，由R 抗病基因(Resistance gene)介导的免疫反应就是其中一条主要的途径(房卫平，2015；孙岩，2017)。R基因由白细胞介素-1受体（Toll and in-terleukin-1 receptor，TIR）结构域、功能结构域核苷酸结合位点(Nucleotide bindingsite，NBS)、富含亮氨酸重复(Leucine rich repeat,LRR)位点等结构组成。其中，TIR 和NBS 结构与抗病调节相关（Meyers etal.，2002)，TIR-NBS 类抗病基因作为一类重要的植物免疫基因，是R基因抗病免疫的重要基础（Staal et al.，2008；谢冬微，2015）。

TIR、NBS 结构域是抗病基因免疫反应必需的。当拟南芥的抗病基因 RPS4 或 RPP1A在仅含TIR 和NB 结构域的截短蛋白 $\mathrm { T I R } + 4 5$ 或 $\mathrm { T I R } + 8 0$ 片段时，即使没有病原菌效应蛋白的诱导也能引起细胞的坏死（Zhang et al.,2004；尹玲等，2018）。烟草抗病毒N蛋白的免疫作用与其TIR 结构域进行信号转导有关(Dinesh-Kumar etal.,2000)。还有研究表明,TIR-NBS类基因RLM3 参与了拟南芥广谱抗坏死致病真菌的免疫反应过程（Staal et al.,2008)。尽管TIR-NBS 类蛋白在植物抗病过程中扮演着非常重要的角色，但人们对该基因家族及其成员的了解仍极为有限。本研究通过生物信息学分析方法，对烟草 TIR-NBS 基因家族的分子特征和功能进行预测分析，为烟草TIR-NBS 类抗病基因的深入探究提供依据。

# 1材料与方法

# 1.1TIR-NBS基因家族鉴定

在 Pfam 中下载 NBS(NB-ARC)(htp://pfam.xfam.org/family/PF00931#tabview $\ v { r } = \ v { D }$ tab6)和 TIR（http://pfam.xfam.org/family/PF01582#tabview=tab6）隐马尔可夫模型。通过 hmmsearch程序用下载的 NB-ARC.hmm 和TIR.hmm文件对烟草全基因组蛋白数据库中的含 TIR-NBS结构域的蛋白家族进行预测，选取的期望值E为 $\mathrm { 1 { \times } 1 0 ^ { - 2 0 } }$ 。

# 1.2染色体定位分析

从Ensembl 植物全基因组数据库(ftp:/ftp.ensemblgenomes.org/pub/plants/release-42/fasta/nicotiana_attenuata)获得 TIR-NBS 基因在染色体上的位置信息，并用在线工具 MG2C(http:/mg2c.iask.in/mg2c_v2.0/)制作染色体定位图。

# 1.3基因结构与motif分析

利用在线工具 GSDS(http://gsds.cbi.pku.edu.cn/)对烟草 TIR-NBS 基因家族成员进行基因结构分析。通过在线工具 meme(http://meme-suite.org/tools/meme)对烟草 TIR-NBS 蛋白 motif进行预测分析。

# 1.4蛋白结构与亚细胞定位分析

利用在线软件 SOPMA（https://psa-prabi.ibcp.fr/cgi-bin/npsa_automat.pl?page $\vDash$ /NPSA/npsa_sopma.html）分析 TIR-NBS 蛋白二级结构。利用在线工具 SignalP 4.1 Server（http://www.cbs.dtu.dk/services/SignalP/）对烟草TIR-NBS 基因进行信号肽分析。利用在线工具DeepLoc（http://www.cbs.dtu.dk/services/DeepLoc/）对烟草TIR-NBS 基因进行亚细胞定位分析。

# 1.5TIR-NBS蛋白的理化性质分析

利用ExPASy 中的 ProtParam (http://web.expasy. org/protparam/)软件对烟草 TIR-NBS 蛋白基本特性进行分析，包括蛋白质大小、相对分子质量、理论等电点、不稳定系数、亲水性指数和脂溶性指数等指标。

# 1.6进化选择压力分析

利用 Blast 建库比对和 Calculator 工具(Wang et al.,201O),对烟草 TIR-NBS 基因核苷酸的同义替换率（Ks）和非同义替换率（Ka）进行计算，获得基因Ka/Ks 比率，进行选择压力分析。

# 1.7系统发育分析

将检索得到的烟草（Nicotiana atenuata）、拟南芥（Arabidopsis thaliana）、番茄（Solanumlycopersicum）的 TIR-NBS 蛋白的氨基酸序列通过软件ClustalX进行 TIR-NBS 蛋白序列比对，然后利用 MEGA-7.0 (Kumar etal.，2016)软件构建TIR-NBS 基因家族邻接(NJ,Neighbor-joining)系统发育树,Boostrap 值设置为1000,其他参数为系统默认值；使用FigTree（http://tree.bio.ed.ac.uk/software/figtree/）软件展示系统发育树。

# 1.8顺式作用元件分析

利用工具bedtools（Quinlan,2014）获得TIR-NBS 基因上游 $2 0 0 0 { \mathrm { b p } }$ 序列，利用在线网站PlantCARE(htp://bioinformatics.psb.ugent.be/webtools/plantcare/html/)对获得的序列进行预测，并对主要的顺式作用元件进行探讨。

# 2结果与分析

# 2.1TIR-NBS基因家族成员

根据Pfam 数据库中 TIR-NBS 基因家族主要含有 NB-ARC、TIR-NB-ARC-LRR、TIR-NB-ARC 功能域的特征，通过构建隐马尔可夫模型，设置E-value 为 $\displaystyle { 1 \times 1 0 ^ { - 2 0 } }$ ，共鉴定到217条基因，去掉不含有TIR-NB-ARC 结构的基因，最终获得30 条烟草TIR-NBS 基因。

# 2.2TIR-NBS基因家族的染色体分布

对 TIR-NBS 基因染色体定位分析，结果显示，30 条TIR-NBS 基因不均匀的分布在 21条染色体上。其中有4条 TIR-NBS 基因在 scaffold01866上，数量最多且以串联重复形式出现。其次是1、10、11、scaffold00577、scaffold01435、scaffold02060 号染色体分别有2条TIR-NBS 基因。其余染色体仅有1条TIR-NBS基因。

![](images/4f3ef3b60940a04b1f17efe24f7a5458b3d9d873c4aa7eaba88346ad664e032f.jpg)  
图1烟草TIR-NBS基因在染色体上的位置  
Fig.1 Position of TIR-NBS gene on chromosome in Nicotiana attenuata

# 2.3TIR-NBS基因的结构组成

利用在线网站工具GSDS 对30 条烟草TIR-NBS 基因家族成员进行基因结构分析，结果显示(图 2)，TIR-NBS 基因家族外显子数量主要分布 3\~8 之间。利用 meme 对 30 条烟草TIR-NBS 蛋白序列进行分析(图3)，发现OIT39360 所含基序最少，仅6个基序，其余所含基序都较多，最多为10个，说明该基因家族成员间在功能上可能存在差异。

![](images/7348565c816cfe363d3bb3a8485d5b2c73a7a258d2d2d072a959d038e68cd4b9.jpg)  
Fig.2StructureofTIR-NBSgeneinNicotianaattenuata

![](images/0d6e292c05b71abf4b7c357c401085bbe990d820f8db75a781e37635d190a0a0.jpg)  
图2烟草TIR-NBS基因的结构  
图3烟草TIR-NBS蛋白保守基序的分布  
Fig.3 Distribution of conserved motifs of TIR-NBS protein in Nicotiana attenuata

# 2.4TIR-NBS蛋白结构特点、细胞位置和信号肽

对 30 条烟草TIR-NBS 蛋白的二级结构的预测结果表明，TIR-NBS 蛋白由 $\mathfrak { a }$ -螺旋、延伸链、 $\beta$ -转角、无规则卷曲组成。其中TIR-NBS 蛋白的 $\mathbf { \boldsymbol { a } }$ -螺旋比例最高，其次是无规则卷曲。根据亚细胞定位分析，结果显示烟草TIR-NBS 基因家族主要定位在细胞核、细胞质、叶绿体。信号肽分析结果表明，TIR-NBS基因家族成员均不含有信号肽。

表1烟草TIR-NBS蛋白二级结构组成及亚细胞定位  
Table 1 Secondary structure and subcellular localizations of TIR-NBS Protein in Nicotiand   

<html><body><table><tr><td colspan="6">attenuata</td></tr><tr><td>蛋白质</td><td>α-螺旋</td><td>延伸链</td><td>β-转角</td><td>无规则卷曲</td><td>亚细胞定位</td></tr><tr><td>Protein</td><td>Alpha helix</td><td>Extended</td><td>Beta turn</td><td>Random coil</td><td>Subcellular</td></tr><tr><td></td><td>(%）</td><td>strand（%)</td><td>(%）</td><td>(%）</td><td>localization</td></tr><tr><td>OIT40722</td><td>45.27</td><td>14.43</td><td>3.95</td><td>36.34</td><td>nucl</td></tr><tr><td>OIT39360</td><td>50.86</td><td>13.83</td><td>5</td><td>29.88</td><td>cyto</td></tr><tr><td>OIT37819</td><td>46.19</td><td>14.01</td><td>4.06</td><td>35.74</td><td>nucl</td></tr><tr><td>OIT35975</td><td>38.97</td><td>19.83</td><td>9.02</td><td>32.18</td><td>nucl</td></tr><tr><td>OIT35745</td><td>48.55</td><td>17.34</td><td>11.18</td><td>22.93</td><td>cyto</td></tr><tr><td>OIT35602</td><td>45.09</td><td>15.1</td><td>4.24</td><td>35.57</td><td>chlo</td></tr><tr><td>OIT35319</td><td>43.92</td><td>19.5</td><td>9.84</td><td>26.75</td><td>chlo_mito</td></tr><tr><td>OIT35320</td><td>46.86</td><td>17.44</td><td>8.19</td><td>27.52</td><td>cyto</td></tr><tr><td>OIT34932</td><td>48.34</td><td>14.66</td><td>4.64</td><td>32.36</td><td>nucl</td></tr><tr><td>OIT31895</td><td>51.45</td><td>11.18</td><td>3.37</td><td>34</td><td>nucl</td></tr><tr><td>OIT30739</td><td>54.24</td><td>10.58</td><td>3.71</td><td>31.46</td><td>cyto</td></tr><tr><td>OIT30741</td><td>53.68</td><td>10.81</td><td>4.41</td><td>31.1</td><td>nucl</td></tr><tr><td>OIT30588</td><td>46.57</td><td>13.48</td><td>4.6</td><td>35.35</td><td>nucl</td></tr><tr><td>OIT29100</td><td>44.89</td><td>14.31</td><td>4.09</td><td>36.71</td><td>nucl</td></tr><tr><td>OIT29097</td><td>45.69</td><td>14.39</td><td>4.63</td><td>35.28</td><td>chlo</td></tr><tr><td>OIT29099</td><td>45.4</td><td>15.16</td><td>3.83</td><td>35.62</td><td>mito</td></tr><tr><td>OIT29096</td><td>49.84</td><td>12.91</td><td>6.54</td><td>30.72</td><td>chlo</td></tr><tr><td>OIT28454</td><td>44.8</td><td>14.25</td><td>4.1</td><td>36.86</td><td>nucl</td></tr><tr><td>OIT28456</td><td>41.91</td><td>14.67</td><td>4.47</td><td>38.95</td><td>nucl</td></tr><tr><td>OIT27720</td><td>50.28</td><td>13.08</td><td>3.64</td><td>32.99</td><td>cyto</td></tr><tr><td>OIT26264</td><td>55.11</td><td>13.95</td><td>6.22</td><td>24.72</td><td>cyto</td></tr><tr><td>OIT22858</td><td>51.81</td><td>11.12</td><td>4.68</td><td>32.39</td><td>nucl</td></tr><tr><td>OIT08655</td><td>51.96</td><td>12.66</td><td>6.89</td><td>28.49</td><td>chlo</td></tr><tr><td>OIT08444</td><td>48.22</td><td>13.31</td><td>3.87</td><td>34.6</td><td>nucl</td></tr><tr><td>OIT02262</td><td>55.39</td><td>10.03</td><td>3.53</td><td>31.05</td><td>nucl</td></tr><tr><td>OIT00998</td><td>52.19</td><td>12.14</td><td>4.56</td><td>31.11</td><td>cyto</td></tr><tr><td>OIS97981</td><td>50.18</td><td>12.44</td><td>3.22</td><td>34.17</td><td>nucl</td></tr><tr><td>OIS97980</td><td>51.82</td><td>10.91</td><td>3.35</td><td>33.93</td><td>vacu</td></tr><tr><td>OIS97230</td><td>50.62</td><td>12.35</td><td>3.7</td><td>33.33</td><td>cyto</td></tr></table></body></html>

<html><body><table><tr><td>OIS96639</td><td>43.85</td><td>14.81</td><td>4.53</td><td>36.81</td><td>chlo</td></tr></table></body></html>

# 2.5 TIR-NBS蛋白的理化性质

对烟草TIR-NBS家族蛋白的特征进行分析，结果表明烟草TIR-NBS蛋白长度范围在505\~1508aa之间，相对分子质量大小范围为 $4 6 . 7 3 { \sim } 1 7 2 . 5 3 \mathrm { ~ k D a }$ ，理论等电点范围在5.78\~9.40之间，编码氨基酸序列最长的是OIT34932,其相对分子质量也最大，为 $1 7 2 . 5 3 \mathrm { k D a }$ ; OIT39360相对分子质量最小，为 $4 6 . 7 3 \mathrm { k D a }$ 。分析表明，TIR-NBS蛋白为不稳定蛋白，其中OIT35745的不稳定系数最小，为 33.98。TIR-NBS蛋白脂溶指数为90.09\~104.23，总平均亲水性为-0.445\~-0.115，均为亲水性蛋白。

表2烟草TIR-NBS蛋白理化性质  
Table 2 Protein physical and chemical properties of TIR-NBS in Nicotiana attenuata   

<html><body><table><tr><td colspan="6">Tabie2Ffotenrplysicar nmcarproperties 氨基酸数量 理论等电点 分子量 不稳定指数 基因 Number of Theoretical</td></tr><tr><td>ID</td><td>amino acids (aa)</td><td>Molecular weight (kDa)</td><td>isoelectric point (pI)</td><td>Instability index</td><td>Aliphatic index</td><td>Grand average of hydropathicity (GRAVY)</td></tr><tr><td>OIT40722</td><td>1 164</td><td>132 616.63</td><td>6.30</td><td>45.34</td><td>98.59</td><td>-0.190</td></tr><tr><td>OIT39360</td><td>405</td><td>46 733.23</td><td>6.71</td><td>40.23</td><td>92.17</td><td>-0.445</td></tr><tr><td>OIT37819</td><td>985</td><td>111 440.67</td><td>8.70</td><td>47.15</td><td>96.35</td><td>-0.205</td></tr><tr><td>OIT35975</td><td>721</td><td>82 972.87</td><td>8.53</td><td>43.08</td><td>95.94</td><td>-0.273</td></tr><tr><td>OIT35745</td><td>519</td><td>59 284.23</td><td>8.30</td><td>33.98</td><td>94.61</td><td>-0.308</td></tr><tr><td>OIT35602</td><td>967</td><td>110 665.57</td><td>6.24</td><td>42.22</td><td>100.07</td><td>-0.191</td></tr><tr><td>OIT35319</td><td>1 159</td><td>130 160.26</td><td>8.79</td><td>39.02</td><td>102.51</td><td>-0.124</td></tr><tr><td>OIT35320</td><td>843</td><td>96 202.72</td><td>8.84</td><td>42.33</td><td>100.58</td><td>-0.184</td></tr><tr><td>OIT34932</td><td>1508</td><td>172 528.71</td><td>8.53</td><td>41.79</td><td>97.02</td><td>-0.115</td></tr><tr><td>OIT30895</td><td>1306</td><td>150 144.62</td><td>6.04</td><td>43.60</td><td>99.78</td><td>-0.144</td></tr><tr><td>OIT30739</td><td>1 427</td><td>160 867.22</td><td>8.29</td><td>47.07</td><td>104.23</td><td>-0.127</td></tr><tr><td>OIT30741</td><td>1360</td><td>154 530.93</td><td>6.70</td><td>40.43</td><td>101.77</td><td>-0.214</td></tr><tr><td>OIT30588</td><td>1 239</td><td>139 896.76</td><td>6.59</td><td>43.37</td><td>95.36</td><td>-0.264</td></tr><tr><td>OIT29100</td><td>1174</td><td>133 684.27</td><td>8.12</td><td>47.29</td><td>94.17</td><td>-0.240</td></tr><tr><td>OIT29097</td><td>1230</td><td>140 457.34</td><td>6.02</td><td>49.74</td><td>95.55</td><td>-0.208</td></tr><tr><td>OIT29099</td><td>1 227</td><td>140 396.59</td><td>8.47</td><td>44.32</td><td>99.21</td><td>-0.207</td></tr><tr><td>OIT29096</td><td>612</td><td>69 709.89</td><td>6.36</td><td>40.71</td><td>92.04</td><td>-0.379</td></tr><tr><td>OIT28454</td><td>1 172</td><td>133 098.54</td><td>6.00</td><td>43.27</td><td>92.73</td><td>-0.187</td></tr><tr><td>OIT28456</td><td>1186</td><td>134 835.18</td><td>6.60</td><td>50.18</td><td>96.88</td><td>-0.245</td></tr><tr><td>OIT27720</td><td>1070</td><td>122 707.11</td><td>5.78</td><td>45.65</td><td>92.73</td><td>-0.327</td></tr><tr><td>OIT26264</td><td>724</td><td>82 785.95</td><td>5.80</td><td>44.29</td><td>94.93</td><td>-0.245</td></tr><tr><td>OIT22858</td><td>1133</td><td>129 688</td><td>7.64</td><td>47.71</td><td>97.29</td><td>-0.184</td></tr><tr><td>OIT08655</td><td>537</td><td>61 305.41</td><td>6.36</td><td>50.18</td><td>95.40</td><td>-0.240</td></tr><tr><td>OIT08444</td><td>1 292</td><td>147 623.45</td><td>6.44</td><td>47.14</td><td>94.29</td><td>-0.177</td></tr><tr><td>OIT02262</td><td>1 446</td><td>165 295.46</td><td>6.10</td><td>43.85</td><td>99.02</td><td>-0.216</td></tr></table></body></html>

<html><body><table><tr><td>OIT00998</td><td>1 096</td><td>125 184.82</td><td>5.94</td><td>44.76</td><td>97.33</td><td>-0.233</td></tr><tr><td>OIS97981</td><td>1 399</td><td>161 296.18</td><td>7.62</td><td>47.28</td><td>97.09</td><td>-0.332</td></tr><tr><td>OIS97980</td><td>1 403</td><td>160 681.97</td><td>8.68</td><td>46.19</td><td>99.12</td><td>-0.216</td></tr><tr><td>OIS97230</td><td>1 053</td><td>121 469.36</td><td>6.40</td><td>46.61</td><td>91.92</td><td>-0.307</td></tr><tr><td>OIS96639</td><td>1 236</td><td>141 801.16</td><td>6.14</td><td>47.17</td><td>95.64</td><td>-0.253</td></tr></table></body></html>

# 2.6TIR-NBS基因的进化选择

非同义替换(Ka)和同义替换(Ks)比值Ka/Ks 可反映生物进化的过程中所受到的选择压力。对来源于TIR-NBS 亚家族间亲缘关系最近的10条基因成员进行Ka/Ks 分析，结果显示该基因对间的Ka/Ks 比值均小于1,表明烟草TIR-NBS基因在进化时主要受纯化选择作用。

表3烟草TIR-NBS基因核苷酸替换率  
Table 3 Nucleotide substitution rate of TIR-NBS gene in Nicotiana attenuata   

<html><body><table><tr><td colspan="2">旁系同源基因位点 Paralogous gene pair locus</td><td>非同义替换率 (Ka) Non-synonymous substitution rate</td><td>同义替换率(Ks) Synonymous</td><td>选择压力比值 （Ka/Ks）Select</td></tr><tr><td></td><td></td><td></td><td>substitution rate</td><td>pressure ratio</td></tr><tr><td>OIS97981</td><td>OIS97980</td><td>0.169 6</td><td>0.303 0</td><td>0.559 6</td></tr><tr><td>OIT30739 OIT29097</td><td>OIT30741</td><td>0.451 3</td><td>2.193 3</td><td>0.205 8</td></tr><tr><td>OIT37819</td><td>OIS96639</td><td>0.228 5 0.213 5</td><td>0.912 5 0.346 4</td><td>0.250 4</td></tr><tr><td></td><td>OIT35602</td><td></td><td></td><td>0.616 4</td></tr><tr><td>OIT22858</td><td>OIT08655</td><td>0.241 1</td><td>0.609 4</td><td>0.395 6</td></tr></table></body></html>

# 2.7TIR-NBS基因家族的系统发育树

为了进一步了解烟草TIR-NBS基因家族进化关系，利用烟草（30条）、番茄（27条）、拟南芥（176条）共 233条 TIR-NBS蛋白序列构建NJ系统发育树（图4)，由图可知，30条TIR-NBS基因家族成员与番茄的TIR-NBS基因家族亲缘关系相近。

注：浅蓝色为拟南芥，绿色为番茄，红色字体标记为烟草。

![](images/e1e0c2c2a34521dcb77711b1332544de3b8dbe1264769cacc2fa3da1de96a2ea.jpg)  
图4烟草TIR-NBS蛋白家族系统进化树

Note: Light blue is Arabidopsis thaliana, green is Solanum lycopersicum,red is marked as Nicotiana attenuate.

Fig. 4 Distribution of conserved motifs of TIR-NBS protein in Nicotiana attenuata

# 2.8TIR-NBS基因家族的顺式作用元件组成

通过对基因上游 $2 0 0 0 { \mathrm { b p } }$ 序列进行分析，预测基因的顺式作用元件(图5)。TIR-NBS 基因家族除了存在大量的基本元件CAAT-box和TATA-box外，还存在参与光响应顺式作用调节元件ACE、AE-boX、AT1-motif、Box 4、CAG-motif、GA-motif、GT1-motif、G-box，胚乳表达所需顺式作用调节元件GCN4_motif，参与种子特异性调节的顺式作用调节元件RY-element。此外，TIR-NBS 基因家族中还含有与分生组织表达相关的顺式作用调节元件CAT-box、茉莉酸甲酯反应的顺式作用调节元件CGTCA-motif、水杨酸反应顺式作用元件TCA-element、低温响应顺式元件LTR、防御和应激反应顺式作用元件TC-rich repeats、昼夜节律控制顺式作用调节元件circadian，生长素反应顺式作用元件 AuxRR-core、TGA-element以及赤霉素反应顺式作用元件TATC-box、P-box等。分析表明，TIR-NBS 基因可能受光、温度及生长素、茉莉酸甲酯、脱落酸、水杨酸、赤霉素等激素调控，并可能通过这些顺式作用元件参与了烟草中的防御机制，在植物生长过程中起到防御和保护植物的作用。

![](images/451e3e8d19a6de4ff78c407b128725b727818035a44b0c1906c813c0ce3f4b94.jpg)  
图5烟草TIR-NBS基因顺式作用元件位点图  
Fig.5 Site map of TIR-NBS gene element in Nicotiana attenuata

# 3讨论

TIR-NBS 类抗病相关基因是植物抗病免疫系统中的一个重要组成部分。它主要的抗病调节结构域包括TIR 和NBS 两部分，其中植物抗病蛋白（R蛋白）中TIR 结构域主要存在于拟南芥和其他双子叶植物中（Meyers et al.，2002)，而在单子叶植物中，仅发现了非 TIR序列（Tarr,2009)。TIR 结构域是大约 200 个氨基酸的蛋白质结构域，包括三个高度保守的基序（Slack etal,2000)。目前，已经在部分生物中鉴定了TIR-NBS 结构域，并证明它与植物致病诱导蛋白和其他植物信号转导蛋白的相互作用（Nandety et al.,2013)。但到目前为止，在烟草基因组水平上，仅有少数TIR-NBS 类基因家族被鉴定，对于大多数该类基因鲜有报道。

对烟草与拟南芥、番茄TIR-NBS类基因家族进化关系分析表明，烟草和番茄的TIR-NB$s$ 基因同源性较高，因此烟草和番茄的TIR-NBS基因家族在生物学功能、生长调控机制上可能存在相似性。当植物受到病原菌侵害时，水杨酸作为发生超敏反应及形成系统获得性抗性所需要的内源信号分子（陈冲等，2018)，其通过诱导病原相关蛋白(pathogenesis-related protein,PR 蛋白)等多种抗病蛋白产生 SAR 起作用(汪尚等，2016)。茉莉酸甲酯参与种子萌发、根生长、生育、果实成熟和衰老等多种发育过程的调节（丛汉卿，2015)。此外，茉莉酸甲酯还能激活植物防御机制，对昆虫引起的伤害、各种致病菌和环境胁迫（如干旱、低温和盐度）作出反应（Cheonget al.，2003）。通过对 TIR-NBS 基因顺式作用元件分析表明，TIR-NBS 基因家族中含有防御和应激反应、低温响应、光响应、脱落酸反应、MeJA反应、水杨酸响应、赤霉素响应、分生组织表达等顺式作用元件，可知其不但与植物生长发育有关，还参与免疫应激反应调节，这与上述报道是相符的。

在烟草TIR-NBS 类抗病基因家族中，被报道的基因数目很少，大多数基因的功能到目前为止还不清楚。本研究通过生物信息学方法概括了烟草基因组中的TIR-NBS 类抗病基因的鉴定、基因结构、及顺式作用分析等，对于发掘新的与植物抗病性相关的基因，加快烟草中抗病机制的研究具有十分重要的意义，也为烟草的抗病育种研究奠定了基础。

# 参考文献

CHEN C, LIU S,WANG DD,et al., 2018. Identification of cucumber PCD induced by salicylic acid and expression analysis of related genes [J]. Acta Agric Boreal-Sin,33(6): 56 -63.[陈冲, 刘双，王丹丹，等，2018．水杨酸诱导黄瓜 PCD 的鉴定及相关基因的表达分析[J]．华北农 学报，33 (6): 56 -63.]

CHEONG Jong-Joo, Choi YANG D, 2O03. Methyl jasmonate as a vital substance in plants [J]. Trends Genet, 19(7).

CONG HQ, QI YY, ZHANG ZW, et al.,2O15. Sequence analysis of cassava EIN3 gene and itsinduced expression characteristics of ethylene and methyl jasmonate [J]. Mol Plant Breed,13(12):2705-2712.[丛汉卿，齐尧尧，张振文，等，2015．木薯EIN3 基因的序列分析及其乙烯和茉莉酸甲酯诱导表达特性[J].分子植物育种，13(12):2705-2712.]

DINESH-KUMAR SP, THAM WH, BAKER BJ,20O0. Structure-function analysis of the tobacco mosaic virus resistance gene N. Proc Natl Acad Sci USA, 97: 14789 - 94.

FANG WP, XIE DY,LI ZF, et al.，2O15.NBS-LRR-like disease-resistant protein-mediatedmolecular mechanisms of plant disease resistance [J]. Mol Plant Breed,13( 2): 469 - 474.[房卫平，谢德意，李志芳，等，2015.NBS-LRR 类抗病蛋白介导的植物抗病应答分子机制[J].分子植物育种,13(2):469-474.]

KUMAR S, STECHER G, TAMURA K, 2016. Mega7: molecular evolutionary genetics analysis version 7.O for bigger datasets[J]. Mol Biol Evol, 33(7): 1870 - 1874

MEYERS BC, MORGANTE M, MICHELMORE RW,2002. TIR-X and TIR-NBS proteins: two new families related to disease resistance TIR-NBS-LRR proteins encoded in Arabidopsis and other plant genomes[J]. Plant J, 32(1).

NANDETY RS,CAPLAN JL, Cavanaugh K, et al.， 2O13. The role of TIR-NBS and TIR-X proteins in plant basal defense responses[J]. Plant Physiol, 162(3), 1459 - 1472.

QUINLAN AR,2014.BEDTools: The Swiss-Army tool for genome feature analysis[J]. Current Protoc Bioinform,47(1),11.12.11-11.12.34.

SLACK JL, SCHOOLEY K, BONNERT TP, et al.,20O0. Identification of two major sites in the type I interleukin-1 receptor cytoplasmic region responsible for coupling to pro-inflammatory signaling pathways[J]. JBiol Chem, 275: 4670 - 4678.

STAAL J, KALIFF M, DEWAELE E, et al.,2008.RLM3,a TIR domain encoding gene involved in broad-range immunity of Arabidopsis to necrotrophic fungal pathogens[J]. Plant J,55(2): 188 - 200.

SUN Y, LIU BL, YUAN LX, et al.， 2O17. Identification and analysis of NBS resistance genefamily of flax carp[J].Mol Breed,15(4): 1417-1425.[孙岩，刘宝玲，苑丽霞，等，2017．亚麻荠NBS类抗病基因家族的鉴定与分析[J]．分子植物育种，15(4):1417-1425.

TARR DE,ALEXANDER H, 2OO9.TIR-NBS-LRR genes are rare in monocots: evidence from diverse monocot orders [J]. BMC Res Notes,2(1).

WANG DP, ZHANG YB, ZHANG Z, et al., 2010. Ka Ks_Calculator 2.0: a toolkit incorporating gamma-series methods and sliding window strategies[J]. Genom Proteom Bioinform,8(1): 77 - 80.

WANG S, XU LQ, ZHANG YX, et al., 2016. Research progress of salicylic acid-mediated diseaseresistance in plants [J].Acta Physiol Sin,52(5): 581-590.[汪尚，徐鹭芹，张亚仙，等，2016.水杨酸介导植物抗病的研究进展[J]．植物生理学报，52(5):581-590.

XIE DW,LU Y, ZHAO DB,et al., 2015. Genome-wide analysis of flax NBS disease resistance gene families[J].Plant Fiber Sci Chin,37(3):113-119+125.[谢冬微，路颖，赵德宝，等,2015. 亚麻 NBS 类抗病基因家族全基因组分析[J]．中国麻业科学，37(3):113-119+125.] YIN L,FANG H, HUANG Y,et al.， 2O16. Research progress on various domains of plant

TIR-NB-LRR type disease resistance genes [J]. Guihaia,37(2): 186 -190.[尹玲，方辉，黄羽,等，2016.植物 TIR-NB-LRR类型抗病基因各结构域的研究进展[J].广西植物，37(2)：186- 190.]

ZHANG Y, DOREY S,SWIDERSKI M, et al., 2OO4. Expression of RPS4 in tobacco induces an AvrRps4-independent HR that requires EDS1, SGT1 and HSP90[J]. Plant J, 40(2), 213 - 224.