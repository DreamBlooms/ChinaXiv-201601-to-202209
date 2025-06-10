# 一种新型冠状病毒肺炎(COVID-19)药物与天然产物快速发现的计算药理学方法

# aCODE: Agile Discovery of Drugs and Natural Products for Emerging Epidemic COViD-19 based on Computational Pharmacology

全源1,2、梁峰吉、熊江辉2,3,4\*

1哈尔滨工业大学(深圳)计算机科学与技术学院，广东深圳，5180552深圳市绿航星际太空科技研究院医学健康部表观遗传学实验室，广东深圳，518117航天医学基础与应用国家重点实验室，北京，1000944 Aromability Inc.Beijing,100o80．通讯作者:熊江辉,E-mail: xiongjh77 $@$ 163.com[摘要]新发传染病爆发流行期间，亟需提出候选药物功效与机制的科学假说。疫苗或新药研发均需要一定时间，因而药物重定位(老药新用)策略有其独特价值。但是新发疾病其病原体、宿主反应的临床数据不充分，制约了候选药物假设的提出。此阶段常根据病人临床特征进行广谱抗病毒药物的尝试。本文借鉴人工智能领域常见的启发式搜索思路，提出一种新方法(aCODE)，基于前期有一定疗效提示的广谱抗病毒药，获得其宿主靶蛋白集合，在全基因组尺度上搜索与之相关性最高的基因模块组合，进而对候选化合物（如已批准上市药物、天然产物）进行模式匹配与统计检验排序。本方法可根据临床实践的进展更新输入药物，迭代输出更精准结果，输出的天然产物或中药、药食同源成分结合其它信息后可实施快速测试，形成敏捷研发测试闭环。本方法的第二版更新及其与文献证据的比对分析请参考：http://chinaxiv.org/abs/202002.00024。

关键词：COVID-19；计算药理学；药物重定位；天然产物；网络药理学

# Abstract

During the outbreak of new infectious diseases, there is an urgent need to put forward scientific hypotheses for the efficacy，mechanism and side effects of candidate drugs. The research and development of vaccines or new drugs need a certain period of time, so the strategy of drug repositioning has its place. However, the clinical data of pathogen and host response of new diseases are not ready, restricts the hypothesis of candidate drugs. At this stage, we often try to use broad-spectrum antiviral drugs according to the clinical characteristics of patients. In this paper, we propose a new method aCODE (agile discovery method of drugs or natural products for emerging epidemic) which based on the heuristic search strategy widely used in the field of artificial intelligence. Based on the broad-spectrum antiviral drugs with some early efficacy tips, the host target protein collection is obtained, and the associated gene modules is searched on the whole genome scale. We then carry out pattern matching and statistics for candidate compounds (such as approved drugs and natural products ingredients). This method can update the input drugs according to the progress of clinical practice, and output more accurate results iteratively. The output components from natural products, traditional Chinese medicine or food can be used for quick trial to form a closed loop of agile R & D test. In addition,for the second update of this method and its comparison with literature evidence,please refer to: http://chinaxiv.org/abs/2020o2.00024.

Key words: COVID-l9; computational pharmacology; drug repositioning; natural products; Network pharmacology

# 1．前言

重大新发传染病爆发期的特点是时间紧迫、数据有限。基于病毒靶标的药物发现路径需要对病毒结构与功能的精细了解，而临床疗效毒副作用验证需要大量时间。基于表型的药物重定位（老药新用）技术是一种重要的新思路[1]，但是对于新发传染病而言，短期很难获得足量的基因组学、表型组学数据。针对这种数据极其有限情况下需要快速产生可验证药物假说并进行量化评价的需求，我们借鉴人工智能领域常用的启发式搜索策略，提出一种新方法即 aCODE (agilediscovery method of drugs or natural products for emerging epidemic)方法（图1）。基于有限疗效的广谱抗病毒药，获得其宿主靶蛋白集合，在全基因组尺度上搜索与之相关性最高的基因模块组合，进而对候选化合物（如已批准上市药物、天然产物）进行模式匹配与统计检验排序。本文以最近在我国爆发的新型冠状病毒COVID-19 为例，以部分报道有一定疗效提示的药物为输入，对天然产物成分进行计算排序，并将初始药物与天然产物分子混合聚类，以了解候选化合物发挥作用的潜在细胞分子机制。本方法可以随临床实践的进展将初始药物列表进行迭代更新，从而优化系统的精准度与预测能力；输出的天然产物或中药、药食同源成分可实施快速测试，形成敏捷研发测试闭环；并为爆发期医疗资源有限情况下大量人群的居家预防与方案测试提供科学支持。

aCODE (agilediscoverymethodofdrugsornatural productsforemergingepidemic) Aging-associated InitialDrugBank CandidateDrugBank FunctipnalGene Module 宝 T 8 2 35 VS. 80 Gene'sSimPoScore STITCHDatabase 9 TCMIDDatabase Gene-level Epigeneticfeatures ↓ ↓ ↓ ↓ Aging-associated GOterm Genee Target . 净 洪 藏 MGeuee Tarugt 洲 . 用 o -Biological Process -CellularComponent ↓ ￥ ↓ ↓ T ↓ -MolecularFunction Aging-associatedFunctionalGeneModules-BasedDrugValidation Gene Module Tarugt . .. Association Aging-associated Index Functional Gene Modules DrugSimilarityAnalysis DrugRankandPrediction 水 Gene Modules XWX饺

# 2．数据资源与分析方法

# 2.1人类基因模块的鉴定

在本研究中，人类基因模块数据源下载自MolecularSignaturesDatabase(MSigDB）数据库（https://www.gsea-msigdb.org/gsea/msigdb/）[2]。数据库包含常用的 GO BiologicalProcess，GO CellularComponent，GO MolecularFunction 等基因模块。

上述基因模块信息是静态的，是参与某生物学过程的所有基因的集合。基于衰老是影响人类各类疾病、免疫功能变化的最普遍因素，筛选与年龄相关的基因作为各个模块的代表。采用包含年龄信息的人类血细胞 DNA 甲基化数据GSE40279 (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc $\mathrel { \mathop : } =$ GSE40279）[3],该数据集包含来自人类全血的656个样本的DNA甲基化谱，年龄从19岁到101岁不等。利用新近提出的可提取基因水平DNA甲基化特征的算法[4-6]，筛选衰老相关的、受DNA 甲基化调控的基因集合。该算法（SIMPO）以每个基因的SIMPO 得分来代表基因水平的DNA甲基化程度。

SIMPO算法的计算公式如下：

$$
S i m P o s c o r e = \frac { \bar { \bf x } - \overline { { { \bf y } } } } { s _ { \mathrm { w } } \sqrt { \frac { 1 } { m } + \frac { 1 } { n } } } \sim t ( m + n - 2 )
$$

其中,

$$
S _ { \mathrm { w } } = { \frac { 1 } { \mathrm { m } + \mathrm { n } + 1 } } [ ( \mathrm { m } - 1 ) \mathrm { S } _ { 1 } ^ { 2 } + ( \mathrm { n } - 1 ) \mathrm { S } _ { 2 } ^ { 2 }
$$

$\pmb { x } ^ { - }$ ：位于基因body区域的所有探针的平均DNA甲基化值;  
$\overline { { y } }$ ：位于基因promoter区域的所有探针的平均DNA甲基化值；  
$\mathbf { m }$ ：位于基因body区域的所有探针数目;  
$\mathbf { n }$ ：位于基因promoter区域的所有探针数目;  
$s _ { 1 } ^ { 2 }$ ：位于基因body 区域探针的DNA甲基化值的方差;  
$S _ { 2 } ^ { 2 }$ ：位于基因 promoter 区域探针的DNA 甲基化值的方差。

接着，本研究基于T-检验计算了老年（ $\scriptstyle \sum = 8 0$ 岁）和青年（ $< 3 5$ 岁）个体之间的基因SIMPO得分差异，挑选T-检验结果中 $\mathrm { ~ \bf ~ P ~ }$ 值 $< 0 . 0 0 1$ 的基因作为年龄显著相关基因模块。该模块与 MSigDB 数据库收集的各个生物学功能基因模块的交集将作为各个生物学功能基因模块的代表。由此，本研究获得了多个与衰老相关的生物学功能基因模块。

# 2.2初始药物显著关联基因模块鉴定

当前版本，输入表1的10个药物作为初始药物，主要来源于国家第四版指南和部分有细胞学证据的药物[7]，及广谱抗病毒药。

表1．初始药物集合  

<html><body><table><tr><td>Drug name</td><td>药物名称</td><td>Drug name</td><td>药物名称</td></tr><tr><td>Lopinavir</td><td>罗匹那韦</td><td>Ribavirin</td><td>利巴韦林</td></tr><tr><td>Ritonavir</td><td>利托那韦</td><td>Indinavir</td><td>芘地那韦</td></tr><tr><td>Oseltamivir</td><td>奥司他韦</td><td>Saquinavir</td><td>沙奎那韦</td></tr><tr><td>Chloroquine</td><td>氯喹</td><td>Carfilzomib</td><td>卡非佐米</td></tr><tr><td>Mycophenolate mofetil</td><td>霉酚酸酯</td><td>Nelfinavir</td><td>奈非那韦</td></tr></table></body></html>

上述抗病毒初始药物的靶标收集自 STITCH（chemical association networks,http://stitch.embl.de）数据库[8]。为了兼顾STITCH 数据库中靶标数量较少的化合物，本研究只选择每个化合物综合打分（combinedscore）前300的靶标作为该化合物的候选靶标。基于超几何分布检验来计算初始药物与各个功能基因模块的相关性。挑选超几何分布检验结果中P值最显著top200 的生物学功能基因模块作为初始药物显著关联基因模块。

超几何分布检验公式如下：

$$
\begin{array} { r } { \mathrm { P } - \mathrm { V a l u e } = 1 - \mathrm { F } ( \mathrm { x } - 1 / M , K , N ) = 1 - \sum _ { i = 0 } ^ { x - 1 } \frac { { \binom { K } { i } } { \binom { M - K } { N - i } } } { \binom { M } { N } } ( } \end{array}
$$

其中 $\mathbf { \boldsymbol { x } }$ 是初始药物与功能基因模块交集的基因数量， $\mathbf { M }$ 是全集基因数量，K是初始药物靶标的基因数量，N是某个生物学功能基因模块的基因数量。

# 2.3潜在抗新型冠状病毒COVID-19药物预测

本研究用于筛选抗新型冠状病毒药物的背景药物数据集收集自天然产物（中药）化学成分数据库 Traditional Chinese Medicine Integrated Database（TCMID,http://www.megabionet.org/tcmid/）[8]。与抗新型冠状病毒COVID-19 初始药物一致，背景药物的靶标收集自STITCH数据库，并选择每个化合物综合打分(combined score）前300的靶标作为该化合物的候选靶标。接着，通过超几何分布检验，我们分别计算了背景药物与各个初始药物显著关联基因模块的相关性。此外，基于初始药物与背景药物计算的超几何分布检验P值，本研究通过聚类方法获得了初始药物与背景药物的相关性。

# 3．结果

本研究基于SIMPO算法，获得了年龄相关的DNA甲基化数据中每个基因的SIMPO 得分来代表基因水平的DNA甲基化程度。基于T-检验，本研究计算了老年（ $> = 8 0$ 岁）和青年（ $< 3 5$ 岁）个体之间的基因SIMPO得分差异，挑选T-检验结果中 $\mathrm { ~ \bf ~ P ~ }$ 值 $< 0 . 0 0 1$ 的基因作为年龄显著相关基因模块。接着，通过MSigDB 数据库中生物学功能基因模块与年龄显著相关基因模块做交集，本研究鉴定了衰老相关的生物学功能基因模块。

接着，结合抗病毒初始药物的靶标基因及衰老相关的生物学功能基因模块数据，通过超几何分布检验获得P值，本研究鉴定了200个与抗病毒初始药物显著关联的生物学功能基因模块(图2)。其中，图3显示的是抗病毒初始药物Ribavirin显著关联的生物学功能基因模块。

![](images/8a94cd82bb02f882d4088a3299e71deb2acd003cd4f53c1b74604e2bfc863a8d.jpg)  
图2.与COVID-19 具有显著相关性的基因模块（Top15)

![](images/ce24d9d5e6801dd4707856cae521a28758945e2263fb18f703db3879f3093074.jpg)  
图3.抗病毒初始药物Ribavirin 显著关联的生物学功能基因模块（Top15)

接着，本研究对天然产物（中药）化学成分进行抗病毒药物筛选。结合天然产物（中药）化学成分在 STITCH数据库中的靶标基因，通过超几何分布检验，我们分别计算了候选药物与各个初始药物显著关联基因模块的相关性得分，当一个化合物对应多个初始药物显著关联基因模块,则对-log(P值)进行累加(附表1)，其中p值是超几何分布检验的p值。

分析结果显示:初始输入药物Ribavirin与COVID-19 疾病相关基因模块的关联性最强（附表1）。此外，有4个天然产物成分的相关性得分高于已知的抗病毒初始药物（包括二氧化硅，3,4-苯并芘，芹黄素，富马酸）。值得注意的是，相关性得分排名靠前的芦丁(rutin)、芹莱素(apigenin)与山柰酚(Kaempferol），在国家卫健委及各中医机构推荐中药处方草药中出现频次较高（表2），提示本方法有利于促进潜在抗新型冠状病毒COVID-19 药物的发现。

此外，基于初始药物与候选药物计算的超几何分布检验P值，通过药物-基因模块双向聚类，可以观察候选药物与初始药物在基因模块相关性上的相似程度（图4和图5）。与已知的初始药物聚类较近的候选天然产物化合物将被预测为潜在的抗新型冠状病毒COVID-19 药物，并且具有类似的作用机制(Mechanismsof Action)。

![](images/e2a6e428d4bba4bdec0b3e71d9887915f8363fafdd5e9b1da90933b61f38f187.jpg)  
图4.提示候选药物与初始药物作用机制的聚类图 (药物视角）

![](images/d8fc1e16f6c82841b1789f6be564d905f2e4cb366609f5c3ec0fc7970d85b024.jpg)  
图5.提示候选药物与初始药物作用机制的聚类图 (基因模块视角)

# 4.讨论

本文结果提示，基于新发传染病早期有限的用药经验反馈，推测并计算疾病特征进而对更大范围的候选药物进行量化分析是可行的。本方法的实质是先在药物这个维度空间，聚集一组有一定疗效提示的药物；用此信息指导在基因维度空间上计算各个基因模块与该疾病的相关性并进行基因模块的聚类；最后回到药物空间对候选化合物进行聚类与排序。

表2.国家卫健委及各中医机构推荐中药处方中草药化学成分出现频次表  

<html><body><table><tr><td>化合物</td><td>频次</td><td>化合物</td><td>频次</td><td>化合物</td><td>频次</td></tr><tr><td>Linalool</td><td>59</td><td>Sucrose</td><td>32</td><td>Anethole</td><td>24</td></tr><tr><td>Stigmasterol</td><td>57</td><td>D-Limonene</td><td>31</td><td>Beta-Elemene</td><td>24</td></tr><tr><td>Vitamin C</td><td>55</td><td>Geraniol</td><td>31</td><td>Lauric Acid</td><td>24</td></tr><tr><td>Gamma-Sitosterol</td><td>51</td><td>Naphthalene</td><td>31</td><td>Trigonelline</td><td>24</td></tr><tr><td>Camphor</td><td>47</td><td>Vitamin B</td><td>31</td><td>Alpha-Limonene</td><td>23</td></tr><tr><td>Eugenol</td><td>47</td><td>Apigenin</td><td>30</td><td>Benzaldehyde</td><td>23</td></tr><tr><td>Kaempferol</td><td>47</td><td>Hexadecane</td><td>30</td><td>Caffeicacid</td><td>23</td></tr><tr><td>Rutin</td><td>47</td><td>Cholesterol</td><td>29</td><td>Campesterol</td><td>23</td></tr><tr><td>Palmitic Acid</td><td>45</td><td>Citral</td><td>29</td><td>Oleic Acid</td><td>23</td></tr><tr><td>Quercetin</td><td>44</td><td>Higenamine</td><td>29</td><td>Berberine</td><td>22</td></tr><tr><td>Adenine</td><td>43</td><td>Emodin</td><td>28</td><td>Beta-Sitosterol</td><td>22</td></tr><tr><td>Camphene</td><td>40</td><td>Acetic Acid</td><td>27</td><td>Choline</td><td>22</td></tr><tr><td>Alpha-Pinene</td><td>35</td><td>Scopoletin</td><td>27</td><td>Chrysophanol</td><td>22</td></tr><tr><td>Daucosterol</td><td>34</td><td>Thymol</td><td>27</td><td>Dibutyl Phthalate</td><td>22</td></tr><tr><td>Gallicacid</td><td>34</td><td>Stearicacid</td><td>26</td><td>Ecdysterone</td><td>22</td></tr><tr><td>Limonene</td><td>33</td><td>Phytol</td><td>25</td><td>Eugenol Methyl Ether</td><td>22</td></tr><tr><td>Stearic Acid</td><td>32</td><td>Vitamin B1</td><td>25</td><td></td><td></td></tr></table></body></html>

本文提出的aCODE方法具有如下特点：（1）敏捷迭代性：本方法可以随临床实践的进展将初始药物列表进行迭代更新，从而优化系统的精准度与预测能力；(2）快速闭环性：输出的天然产物或中药、药食同源成分可实施快速测试，形成敏捷研发测试闭环；（3）药理机制方面，可对候选药物与初始药物的药物作用的细胞分子生物学机制进行聚类、比对。并为爆发期医疗资源有限情况下大量人群的居家预防与方案测试提供科学支持。

aCODE方法本身可以持续更新的方面包括：（1）药物靶标数据库的更新。本研究目前使用的药物靶标数据来自公开的STITCH数据库，后续可以接入更精细的机构专有药物靶标数据库；（2）疾病相关基因的更新。如果有病毒感染的宿主细胞组学等数据，可以对本文用到的疾病相关基因模块数据进行更新；（3)基因模块特异性的更新。当前所用的 MsigDB基因模块，大部分来自GeneOntology，该知识表示体系是一个层级体系，为了兼顾特异性与一般性，选择了基因数量在50-500个之间的基因模块，后续可以对该数据库进行扩充或微调，并且优先选择基因数量比较小、特异性更高的基因模块；（4）其他药物证据的整合能力。本方法是一个纯数据驱动的计算过程，如果该结果与其他来源的临床或文献证据相符，按照贝叶斯原理，则我们对该候选物的信念与兴趣增强，后续可以结合其他因素进一步测试其成药潜力。

值得注意的是，本方法是一个类似GPS的快速聚焦锁定候选化合物的工具，具体到每个候选化合物，需要综合各个维度考察其发挥作用的大小、方向、毒副作用、成药性、经济性等。本方法只涉及药物与候选化合物的计算药理学分析，不对具体的候选药物进行临床提示。

# 参考文献

1. Bekerman E,Einav S. Infectious disease. Combating emerging viral threats. Science.2015;348(6232):282-283. doi:10.1126/science.aaa3778   
2. Arthur L，Aravind S ，Reid P，et al. Molecular signatures database (MSigDB) 3.0[J]. Bioinformatics(12):12.   
3. Hannum G, Guinney J, Zhao L, Zhang L et al. Genome-wide methylation profiles reveal quantitative viewsof human aging rates. Mol Cell 2O13 Jan 24;49(2):359-367.   
4. Fengji Liang，et al. Insulin-resistance and depression cohort data mining to identify nutraceutical related DNA methylation biomarker for type 2 diabetes. https://doi.0rg/10.1016/j.gendis.2020.01.013   
5. Yuan Quan，et al. Mining the Selective Remodeling of DNA Methylation in Promoter Regions to Identify Robust Gene-Level Associations with Phenotype. bioRxiv 2020.01.05.895326; doi: https://doi.0rg/10.1101/2020.01.05.895326.   
6. Yuan Quan, et al. Aging immune system-related blood cell DNA methylation can predict the onset of early stage colorectal cancer. bioRxiv 2020.01.13.905299; doi: https://doi.0rg/10.1101/2020.01.13.905299.   
7．中国疾控中心、国家卫生健康委员会。《新型冠状病毒感染的肺炎诊疗方案 （试行第四版）》.   
8.Szklarczyk Damian, Santos Alberto, von Mering Christian，et al. STITCH 5: augmenting protein-chemical interaction networks with tissue and affinity data[J].

Nucleic Acids Research, 2015(D1):D1. 9. Xue,R，Fang，Z, Zhang，M，et al. TCMID: traditional Chinese medicine integrative database for herb molecular mechanism analysis[J]. Nucleic Acids Research, 41(D1):D1089-D1095.

附表1．COVID-19药物与天然产物来源的候选化合物及其分子机制  

<html><body><table><tr><td>Compound</td><td>名称</td><td>类</td><td>相关</td><td>显著关联基因模块（Top 3)</td></tr><tr><td>name Ribavirin</td><td>利巴韦林</td><td>型 D</td><td>性 377</td><td>GSE13485_PRE_VS_POST_YF17D_VACCINATION_PBMC_DN,</td></tr><tr><td></td><td></td><td></td><td></td><td>GSE19888_ADENOSINE_A3R_INH_VS_ACT_WITH_INHIBITOR_PRETREATMENT</td></tr><tr><td></td><td></td><td></td><td></td><td>_IN_MAST_CELL_UP,GSE42724_NAIVE_BCELL_VS_PLASMABLAST_UP</td></tr><tr><td>Silicon</td><td>二氧化硅</td><td></td><td>327</td><td>GO_COFACTOR_METABOLIC_PROCESS,GO_CYTOKINE_ACTIVITY,</td></tr><tr><td>Dioxide</td><td></td><td></td><td></td><td>GO_REGULATION_OF_IMMUNE_EFFECTOR_PROCESS</td></tr><tr><td>3,4-Benzop</td><td>3,4-苯并</td><td></td><td>251</td><td>GO_DRUG_METABOLIC_PROCESS,</td></tr><tr><td>yrene</td><td>芘</td><td></td><td></td><td>GO_OXIDOREDUCTASE_ACTIVITY_ACTING_ON_PAIRED_DONORS_WITH_INC</td></tr><tr><td></td><td></td><td></td><td></td><td>ORPORATION_OR_REDUCTION_OF_MOLECULAR_OXYGEN,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_COFACTOR_METABOLIC_PROCESS</td></tr><tr><td>Apigenin</td><td>芹菜素</td><td></td><td>247</td><td>GO_MAMMARY_GLAND_DEVELOPMENT,PID_P53_DOWNSTREAM_PATHWAY,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_ANATOMICAL_STRUCTURE_HOMEOSTASIS</td></tr><tr><td>Chloroquine</td><td>氯喹</td><td>D</td><td>225</td><td>GO_DRUG_METABOLIC_PROCESS,GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_PRODUCTION_OF_MOLECULAR_MEDIATOR_OF_IMMUNE_RESPONSE</td></tr><tr><td>Fumaricacid</td><td>富马酸</td><td></td><td>216</td><td>GO_PROTEIN_TYROSINE_KINASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_PROTEIN_AUTOPHOSPHORYLATION,</td></tr><tr><td></td><td></td><td></td><td></td><td>REACTOME_SIGNALING_BY_RECEPTOR_TYROSINE_KINASES</td></tr><tr><td>Mycopheno</td><td>霉酚酸酯</td><td>D</td><td>204</td><td>GO_ENDOPEPTIDASE_ACTIVITY,GO_SERINE_HYDROLASE_ACTIVITY,</td></tr><tr><td>late Mofetil</td><td></td><td></td><td></td><td>GO_HUMORAL_IMMUNE_RESPONSE</td></tr><tr><td>1-Methoxyc</td><td>1-甲氧鸟</td><td></td><td>204</td><td>MODULE_197,KEGG_ERBB_SIGNALING_PATHWAY,</td></tr><tr><td>anthin-6-On</td><td>氨酸-6-一</td><td></td><td></td><td>PID_P53_DOWNSTREAM_PATHWAY</td></tr><tr><td>e</td><td></td><td></td><td></td><td></td></tr><tr><td>Atenolol</td><td>阿替洛尔</td><td></td><td>197</td><td>GO_PROTEIN_TYROSINE_KINASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_PROTEIN_AUTOPHOSPHORYLATION,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_POSITIVE_REGULATION_OF_PHOSPHATIDYLINOSITOL_3_KINASE_SIGNA</td></tr><tr><td></td><td></td><td></td><td></td><td>LING</td></tr><tr><td>L-Homocys</td><td>L-同型半</td><td></td><td>194</td><td>GO_DRUG_METABOLIC_PROCESS,GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td>teine</td><td>胱氨酸</td><td></td><td></td><td>GO_COLLAGEN_CONTAINING_EXTRACELLULAR_MATRIX</td></tr><tr><td>L-Alpha,Ga</td><td>L-α，γ-</td><td></td><td>190</td><td>GO_PROTEIN_TYROSINE_KINASE_ACTIVITY,</td></tr><tr><td>mma-Diami</td><td>二氨基丁</td><td></td><td></td><td>GO_PROTEIN_AUTOPHOSPHORYLATION,</td></tr><tr><td>nobutyric</td><td>酸</td><td></td><td></td><td>GO_POSITIVE_REGULATION_OF_PHOSPHATIDYLINOSITOL_3_KINASE_SIGNA</td></tr><tr><td>Acid</td><td></td><td></td><td></td><td>LING</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Baicalein</td><td>黄芩黄素</td><td></td><td>190</td><td>GO_PEPTIDYL_THREONINE_MODIFICATION,</td></tr></table></body></html>

<html><body><table><tr><td>Compound</td><td>名称</td><td>类</td><td>相关</td><td>显著关联基因模块（Top 3)</td></tr><tr><td>name</td><td></td><td>型</td><td>性</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>GO_BLOOD_VESSEL_ENDOTHELIAL_CELL_MIGRATION</td></tr><tr><td>1,7-Diphen</td><td>1,7-二苯</td><td></td><td>188</td><td>REACTOME_NEGATIVE_REGULATION_OF_THE_PI3K_AKT_NETWORK,</td></tr><tr><td>yl-5-Hepten</td><td>基-5-庚烯</td><td></td><td></td><td>GO_MAMMARY_GLAND_DEVELOPMENT,</td></tr><tr><td>e-3-One</td><td>-3--</td><td></td><td></td><td>GSE7509_UNSTIM_VS_FCGRIIB_STIM_DC_DN</td></tr><tr><td>Benzyl</td><td>水杨酸苄</td><td></td><td>188</td><td>REACTOME_NEGATIVE_REGULATION_OF_THE_PI3K_AKT_NETWORK,</td></tr><tr><td>Salicylate</td><td>酯</td><td></td><td></td><td>GO_MAMMARY_GLAND_DEVELOPMENT,</td></tr><tr><td></td><td></td><td></td><td></td><td>GSE7509_UNSTIM_VS_FCGRIIB_STIM_DC_DN</td></tr><tr><td>Creatinine</td><td>肌酐</td><td></td><td>187</td><td>MODULE_24,GO_CYTOKINE_ACTIVITY,</td></tr><tr><td>Benzene</td><td></td><td></td><td></td><td>GO_REGULATION_OF_VASCULATURE_DEVELOPMENT</td></tr><tr><td></td><td>苯</td><td></td><td>186</td><td>GO_DRUG_METABOLIC_PROCESS,PID_P53_DOWNSTREAM_PATHWAY,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_OXIDOREDUCTASE_ACTIVITY_ACTING_ON_PAIRED_DONORS_WITH_INC</td></tr><tr><td>Palmitoleica</td><td></td><td></td><td></td><td>ORPORATION_OR_REDUCTION_OF_MOLECULAR_OXYGEN</td></tr><tr><td>cid</td><td>棕榈油酸</td><td></td><td>179</td><td>GO_PROTEIN_TYROSINE_KINASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_PROTEIN_AUTOPHOSPHORYLATION,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_OXIDOREDUCTASE_ACTIVITY_ACTING_ON_PAIRED_DONORS_WITH_INC</td></tr><tr><td></td><td></td><td></td><td></td><td>ORPORATION_OR_REDUCTION_OF_MOLECULAR_OXYGEN</td></tr><tr><td>2-Propenal</td><td>2-丙烯醛</td><td></td><td>169</td><td>GO_ENDOPEPTIDASE_ACTIVITY,GO_SERINE_HYDROLASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td>Neoisorutin</td><td>新异芦丁</td><td></td><td>166</td><td>GO_ENDOPEPTIDASE_ACTIVITY,GO_SERINE_HYDROLASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>REACTOME_NEGATIVE_REGULATION_OF_THE_PI3K_AKT_NETWORK</td></tr><tr><td>Rutin</td><td>芦丁</td><td></td><td>166</td><td>GO_ENDOPEPTIDASE_ACTIVITY,GO_SERINE_HYDROLASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>REACTOME_NEGATIVE_REGULATION_OF_THE_PI3K_AKT_NETWORK</td></tr><tr><td>Deoxycholi</td><td>脱氧胆酸</td><td></td><td>165</td><td>GO_OXIDOREDUCTASE_ACTIVITY_ACTING_ON_PAIRED_DONORS_WITH_INC</td></tr><tr><td>cacid</td><td></td><td></td><td></td><td>ORPORATION_OR_REDUCTION_OF_MOLECULAR_OXYGEN,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_DRUG_METABOLIC_PROCESS,KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td>Delphinidin</td><td>德尔菲尼</td><td></td><td>157</td><td>REACTOME_NEGATIVE_REGULATION_OF_THE_PI3K_AKT_NETWORK,</td></tr><tr><td></td><td>丁</td><td></td><td></td><td>GO_REGULATION_OF_PEPTIDASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>GSE32986_CURDLAN_HIGHDOSE_VS_GMCSF_AND_CURDLAN_HIGHDOSE_STI</td></tr><tr><td></td><td></td><td></td><td></td><td>M_DC_DN</td></tr><tr><td>Zerumbone</td><td>花姜酮</td><td></td><td>157</td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_PEPTIDYL_THREONINE_MODIFICATION,</td></tr><tr><td></td><td></td><td></td><td></td><td>ZHOU_INFLAMMATORY_RESPONSE_LPS_UP</td></tr><tr><td>Wedelolacto</td><td>韦地内酯</td><td></td><td>157</td><td>NABA_SECRETED_FACTORS,GO_CYTOKINE_ACTIVITY,</td></tr><tr><td>ne</td><td></td><td></td><td></td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT</td></tr><tr><td>Anwulignan</td><td>安五脂素</td><td></td><td>157</td><td>GO_PHAGOCYTOSIS,GO_CYTOKINE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>RUAN_RESPONSE_TO_TNF_DN</td></tr><tr><td>Macelignan</td><td>肉豆蔻木</td><td></td><td>157</td><td>GO_PHAGOCYTOSIS,GO_CYTOKINE_ACTIVITY,</td></tr><tr><td></td><td>酚素</td><td></td><td></td><td>RUAN_RESPONSE_TO_TNF_DN</td></tr><tr><td>Ascorbic</td><td>抗坏血酸</td><td></td><td>152</td><td>GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td>Acid</td><td></td><td></td><td></td><td>GO_OXIDOREDUCTASE_ACTIVITY_ACTING_ON_PAIRED_DONORS_WITH_INC</td></tr></table></body></html>

<html><body><table><tr><td>Compound</td><td>名称</td><td>类</td><td>相关 性</td><td>显著关联基因模块（Top 3)</td></tr><tr><td>name</td><td></td><td>型</td><td>150</td><td>GO_ANTIGEN_RECEPTOR_MEDIATED_SIGNALING_PATHWAY,</td></tr><tr><td>Threonine</td><td>苏氨酸</td><td></td><td></td><td>GO_IMMUNE_RESPONSE_REGULATING_CELL_SURFACE_RECEPTOR_SIGNALI</td></tr><tr><td></td><td></td><td></td><td></td><td>NG_PATHWAY,GO_PEPTIDYL_THREONINE_MODIFICATION</td></tr><tr><td></td><td></td><td></td><td>150</td><td>GO_ADAPTIVE_IMMUNE_RESPONSE_BASED_ON_SOMATIC_RECOMBINATION</td></tr><tr><td>Methylpred</td><td>甲基泼尼</td><td></td><td></td><td>_OF_IMMUNE_RECEPTORS_BUILT_FROM_IMMUNOGLOBULIN_SUPERFAMILY</td></tr><tr><td>nisolone</td><td>松龙</td><td></td><td></td><td>_DOMAINS,GO_LYMPHOCYTE_MEDIATED_IMMUNITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>SMID_BREAST_CANCER_NORMAL_LIKE_UP</td></tr><tr><td>Kaempferol</td><td></td><td></td><td>148</td><td>GO_OXIDOREDUCTASE_ACTIVITY_ACTING_ON_PAIRED_DONORS_WITH_INC</td></tr><tr><td></td><td>山柰酚</td><td></td><td></td><td>ORPORATION_OR_REDUCTION_OF_MOLECULAR_OXYGEN,</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>GO_MAMMARY_GLAND_DEVELOPMENT,</td></tr><tr><td>Anthracene</td><td></td><td></td><td></td><td>GO_BLOOD_VESSEL_ENDOTHELIAL_CELL_MIGRATION</td></tr><tr><td></td><td>蒽</td><td></td><td>147</td><td>GO_CATALYTIC_ACTIVITY_ACTING_ON_RNA,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_CATALYTIC_ACTIVITY_ACTING_ON_DNA,</td></tr><tr><td>Piceatannol</td><td></td><td></td><td></td><td>GO_DNA_CONFORMATION_CHANGE</td></tr><tr><td></td><td>苦丁酚</td><td></td><td>144</td><td>GO_PROTEIN_TYROSINE_KINASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_REGULATION_OF_PEPTIDASE_ACTIVITY,</td></tr><tr><td>Eckol</td><td></td><td></td><td></td><td>GO_NEGATIVE_REGULATION_OF_HYDROLASE_ACTIVITY</td></tr><tr><td></td><td>埃科尔</td><td></td><td>144</td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT,</td></tr><tr><td></td><td></td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY,</td></tr><tr><td>3,4,5-Trihyd</td><td></td><td></td><td></td><td>GO_PEPTIDYL_THREONINE_MODIFICATION</td></tr><tr><td>roxybenzoic</td><td>3.4,5-三羟</td><td></td><td>143</td><td>GO_REGULATION_OF_PEPTIDASE_ACTIVITY, PID_P53_DOWNSTREAM_PATHWAY,GO_MAMMARY_GLAND_DEVELOPMENT</td></tr><tr><td>Acid</td><td>基苯甲酸</td><td></td><td></td><td></td></tr><tr><td>Gallicacid</td><td>没食子酸</td><td></td><td>143</td><td>GO_REGULATION_OF_PEPTIDASE_ACTIVITY,</td></tr><tr><td></td><td></td><td></td><td></td><td>PID_P53_DOWNSTREAM_PATHWAY,GO_MAMMARY_GLAND_DEVELOPMENT</td></tr><tr><td>1-Methoxy-</td><td>1-甲氧基</td><td></td><td>139</td><td>GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td>4-(1-Propen</td><td>-4-(1-丙烯</td><td></td><td></td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT,</td></tr><tr><td>yl)-Benzene</td><td>基)-苯</td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td>1-Methoxy-</td><td>1-甲氧基</td><td></td><td>139</td><td>GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td>4-(1-Propen</td><td></td><td></td><td></td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT,</td></tr><tr><td>yl)Benzene</td><td>-4-(1-丙烯</td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td>Anethole</td><td>基)苯 茴香脑</td><td></td><td>139</td><td>GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td></td><td></td><td></td><td></td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT,</td></tr><tr><td></td><td></td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td>Cis-Anethol</td><td>顺式茴香</td><td></td><td></td><td>GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td>e</td><td>脑</td><td></td><td></td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT,</td></tr><tr><td></td><td></td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td>P-Propenyl-</td><td>对丙烯基</td><td></td><td>139</td><td>GO_COFACTOR_METABOLIC_PROCESS,</td></tr><tr><td>Anisole</td><td>苯甲醚</td><td></td><td></td><td>GO_ENDOCRINE_SYSTEM_DEVELOPMENT,</td></tr><tr><td></td><td></td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Trans-Aneth ole</td><td>反茴香</td><td></td><td>139</td><td>GO_COFACTOR_METABOLIC_PROCESS,</td></tr></table></body></html>

<html><body><table><tr><td>Compound</td><td>名称</td><td>类相关</td><td>显著关联基因模块(Top 3)</td></tr><tr><td>name</td><td></td><td>型性</td><td></td></tr><tr><td></td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY</td></tr><tr><td>3,3',4',5,5',7</td><td>3,3',4',5,5',</td><td>137</td><td>GO_POSITIVE_REGULATION_OF_PHOSPHATIDYLINOSITOL_3_KINASE_SIGNA</td></tr><tr><td>-Hexahydro</td><td>7-六羟基</td><td></td><td>LING,KEGG_ERBB_SIGNALING_PATHWAY,</td></tr><tr><td>xyflavone</td><td>黄酮</td><td></td><td>GO_ENDOTHELIAL_CELL_PROLIFERATION</td></tr><tr><td>Myricetin</td><td>杨梅素</td><td>137</td><td>GO_POSITIVE_REGULATION_OF_PHOSPHATIDYLINOSITOL_3_KINASE_SIGNA</td></tr><tr><td rowspan="3">Honokiol</td><td rowspan="3">厚朴酚</td><td rowspan="3">134</td><td>LING,KEGG_ERBB_SIGNALING_PATHWAY,</td></tr><tr><td>GO_ENDOTHELIAL_CELL_PROLIFERATION GO_CYSTEINE_TYPE_PEPTIDASE_ACTIVITY,GO_ENDOPEPTIDASE_ACTIVITY,</td></tr><tr><td>GO_OXIDOREDUCTASE_ACTIVITY_ACTING_ON_PAIRED_DONORS_WITH_INC</td></tr><tr><td>Dihydrotest</td><td>二氢睾酮</td><td>133</td><td>ORPORATION_OR_REDUCTION_OF_MOLECULAR_OXYGEN GO_DNA_BINDING_TRANSCRIPTION_ACTIVATOR_ACTIVITY,</td></tr><tr><td>osterone</td><td></td><td></td><td>REACTOME_NEGATIVE_REGULATION_OF_THE_PI3K_AKT_NETWORK,</td></tr><tr><td></td><td></td><td></td><td>GO_POSITIVE_REGULATION_OF_PHOSPHATIDYLINOSITOL_3_KINASE_SIGNA LING</td></tr><tr><td>4-Methylsul</td><td>4-甲基亚</td><td>133</td><td>KEGG_ERBB_SIGNALING_PATHWAY,MODULE_197,</td></tr><tr><td>finyl Butyl</td><td>磺酰基丁</td><td></td><td>GO_COFACTOR_METABOLIC_PROCESS</td></tr><tr><td>Isothiocyan</td><td>基异硫氰</td><td></td><td></td></tr><tr><td>ate</td><td>酸酯</td><td></td><td></td></tr><tr><td>Sulforathan</td><td>硫氟烷</td><td>133</td><td></td></tr><tr><td></td><td></td><td></td><td>KEGG_ERBB_SIGNALING_PATHWAY,MODULE_197,</td></tr><tr><td>e</td><td></td><td></td><td>GO_COFACTOR_METABOLIC_PROCESS</td></tr></table></body></html>

注：“类型”栏标注"D"表示该化合物为初始输入药物