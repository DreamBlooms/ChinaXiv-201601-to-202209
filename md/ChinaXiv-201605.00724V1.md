# Research on Co-expression Genes of a Fig Wasp

CUI Dong-Ya $^ { 1 , 2 , 3 ) ^ { * * } }$ , SUN Xu-Bin $^ { 1 , 2 ) ^ { * * } }$ ,WANG Jia-Jia1,2), ZHANG Peng2, SUN Bao-Fa4 CHEN Xiao-Wei, Robert W.Murphy,HE Shun-Min $^ { 2 ) ^ { * } }$ \*\*, HUANG Da-Wei1 ,2)\*\*\*

（ $^ { 1 ) }$ School of Life Science,Hebei University,Baoding O71oO2,China; （204号 $^ { ( 2 ) }$ KeyLabratoryoftheZologicalSytemticsdEolution,stituteofZogineAcadeyfeceia; 3 College ofLife Science,Yuncheng University,Yuncheng O44ooo,China; $^ { 4 ) }$ LaboratoryofteoriseasesenomedPersoliedMedine,ituteofenoe,CieseAcdefencseig; 5)LaboratoryofBioiformaticsndNoncodingRNA,Istituteofiophysics,ChineseAcademyofSciences,Beijing10o,China; Centre for Biodiversityand Conservation Biology,Royal Ontario Museum,Toronto M5S2C6,Canada)

Abbreviations: WGCNA, weighted gene co-expression network analysis;DAVID,Database for Annotation, Visualization and Integrated Discovery; FPKM,fragments per kilobase ofexon model per millon mapped reads; GE,gene expresion; CV, coefficient of variation; Pcc, Pearson correlation coeficient; GO, gene ontology.

AbstractFemale figasps diferphenotypicallyfromconspecific malestotheextentthatoftentheycannotbeassociated withone another.Weighted gene co-expression network analysis(WGCNA）of the genomeandtranscriptomesof one such fig wasp, Ceratosolensos,gneraedfiveexpresionmoduleshichereflagedasblue,urqiseow,genndyell.eoed twofemale-biased expresionmodulesandthreepupa-biasedexpresionmodules,respectively.Geneontologies indicatedthree functionalenrichmentgenesetsinmodulesturquoiseandyellow.Twofunctionalenrichment genesetsthatparticipateincellcycleor havenucleotidebindingactivityclustered in turquoise module.Thefunctionallyenriched genesetinyellowmodule playedrolesicel differentiation,especially in neuron morphogenesis.

Key wordsco-expression,network,functional enrichment DOI: 10.16476/j.pibb.2015.0287

Genes that co-participate in biological processes generally display similar expression patterns. Often such gene sets involve functional enrichments,which clustering methods can reveal. Thus,clustering of gene sets facilitates an understanding of the roles of genes play in a biological processes[1].

Weighted gene co-expression network analysis (WGCNA） can cluster together genes that function in concert. One of the most direct methods for identifying gene co-expression networks [2]，WGCNA has been successfully applied to the identification of functional enrichment modules in complex diseases[3-8].

Fig wasps are obligate symbiosis of their fig hosts.Female and male fig wasps exhibit extreme morphological dimorphism [9].Recently， the genome andtranscriptomesofCeratosolensolmsiwere published 9].Herein,we employ WGCNA to identify groupsofco-expressedfunctionalgenes from transcriptomes of male and female C.solmsi.

# 1Materials and methods

# 1.1 Differentially expressed genes

Fig wasps has three developmental stages: larva, pupa and adult[1o. Transcriptome data were accessed in the NCBI Short Read Archive(www.ncbi.nlm.nih.gov/ sra）under the accession No.SRPO297O3.The FPKM method (fragments per $\mathbf { k b }$ per million reads)[1] was used to calculate the expression of unigenes. Each gene expression $( G E )$ value was log2-transformed from its FPKM value.To identify the differentially expressed genes,we used the distribution of the overall $G E$ value to remove lowly expressed genes[12]. In total, 7 881 genes with $G E { > } 0 . 5$ in at least four samples were obtained.Next,we used the coefficient of variation $( C V )$ value to identify the differentially expressed genes[13]． Ultimately，we obtained 2 938 genes with $C V < 2$ ：

# 1.2Screening and clustering of highly correlated genes

WGCNA was used to describe the correlation patterns among 2 938 genes across the transcriptomic datasets and cluster the genes with highly correlated expression patterns.Firstly, the weights of each of the two genes were calculated using a soft threshold power of 12 because the $R ^ { \wedge } 2$ was greater than O.7 when applying this threshold[14]. Secondly, two genes with a weight of greater than O.476 were considered to possess highly correlated expression patternsfor $0 . 9 4 \ddots 1 2$ [15]．Thirdly，candidate highly correlated genes were clustered when minModuleSize $= 5$ and mergeCutHeight $= 0 . 0 5$ . Finally,each module of gene expressionpattern was visualized using Cluster 3.O and Treeview[16-17].

# 1.3Annotation and functional speculation

Fig wasp geneswere not well annotated. Therefore，the well-annotated genes of Drosophila melanogaster were used to imply the functions of fig waspgenes. Drosophila proteinsequenceswere downloaded from Flybase.Our co-expressed genes were aligned to those in Flybase by using BLASTP[18]. Functional annotationshad thehighest similar sequences of fig wasp genes to those in Flybase.The fly gene IDs,which were mapped by fig wasp genes, were put into Annotation,Visualization and Integrated Discovery (DAVID)[19] to deduce enrichment levels of the latter.

# 2 Results

# 2.1Highly correlated genesgrouped into five co-expression modules

Using a gene expression value $( G E )$ of $> 0 . 5$ [12] and a coefficient of variation $( C V )$ of $< 2 ^ { \mathrm { [ 1 3 } }$ ,2938 differentlyexpressed geneswere obtained. The weight-values between each two genes were calculated using WGCNA. For better screening of the highly correlated co-expression genes,O.476 was taken as a co-expression threshold value.This resulted in 336 genes being chosen. The Cytoscape $\mathbf { v } 2 . 6 . 3 \AA ^ { [ 2 0 ] }$ network divided 336 genes into four parts (Figure 1).The features of the network were show in Figure $s 1 \sim S 4$ and Table S1.Interestingly， the 336 genes clustered into five modules using WGCNA clustering function (Figure 2).Depicted in colors, these consisted of 54 (green)，62 (yellow)，63 (brown)，76 (blue） and 81 (turquoise) genes.

The turquoise and blue modules clustered together,as did green and brown.Yellow module did not cluster with any other module (Figure 1,2). To confirm that co-expressed genes had similar levels of expression，we visualized them in heatmaps using Cluster 3.O and Treeview [l6-17]． Genes clustered in brown， green and yellow moduleswere highly expressed in females,and genes in blue and turquoise module were expressed in pupa (Figure S5).

# 2.2 Gene ontology

In total,336 co-expressed genes clustered into three co-expression networks and five modules.These results suggested that each module of genes should have unique,enriched functions. Our annotation of fig wasp gene functions by using BLASTP against the genome of Drosophila discovered 251 genes(Table S2). These genes were then analyzed for the functional enrichmentsusing DAVID [19]. Three annotation clusters with enrichment scores of $> 3$ were chosen and we terms with Benjamini values of $< 0 . 0 5$ in each annotation cluster to be candidate functional terms.

We used the fold change $( c )$ to summarize the degree of functional enrichment by calculating formula (1) as follows:

$$
\scriptstyle { c = { \frac { a } { b } } } / { \frac { m } { n } }
$$

$a$ ：Number of enriched genesof a given module in an annotation function term. $b$ :Number ofall enriched genes in an annotation function term. $m$ : Number of all genes in a given module. $n$ : Number of all candidate genes (336).

Gene sets with clear function enrichments had $c$ values of greater than 2 and gene sets likely to have functional enrichments had $c$ values between 1 and 2.

GO results showed that three annotation-clusters involved biological processes and molecular functions (Table S3).Genes that played roles in cell cycle functions exhibited the greatest amount of enrichment and these belonged to annotation cluster 1，and modules turquoise and blue. Annotation cluster 2 contained genes enriched in nucleotide binding activity.They also exhibited the greatest levels of enrichment in modules turquoise and blue.Finally, annotation cluster 3 was comprised of genes enriched in morphogenesis. These genes tended to cluster into modules yellow and green (Figure 3).

![](images/eb2315451c2a2cfad09db79cbb1e902499a51d01ad2ecf7393b448ee4ef1e852.jpg)

![](images/991bff623bfabc99edf54f132c610f4a57e06c8535de0dd8f09ccc5db209e396.jpg)  
Fig.2Highly correlation genes clustered into five expression modules ueandturquoise module genesco-expressedtogether,genand brownmodule genesco-expressdtogether(connectedwithFigu   
Fig.3The enrichment of genes clustered in turquoise and yellow module

0 Cluster Cluster 2 Cluster 3 eeeseelss Prrrrernregietn Nnneeaeet Biology process Molecular function Biology process

GenesofnotatiocusterandaotaioncusterwereeichedoogyprocessndmolecularfunctionespectivelyHowevef annotation cluster 3 were enriched biology process.

Genes in modules turquoise and blue were expressed preferentiallyin female figwasps,butnotin males (Figure S5). This discovery suggested that these genes might play important roles in the development of females. For example，CSO_OOO580， whichwas annotated as $\mathrm { F B g n 0 0 0 0 0 } 6 3$ ,might have protein kinase activity [21l and play roles in female meiosis [22, female meiosis chromosomesegregation [23]and meiotic spindle assembly checkpoint[22l.Thus,this gene might beinvolvedinoogenesis.Anotherexample, CSO_000814,which was annotated by FBgn0004859, might also play roles in oogenesis [24]． These results suggested that clustered highly expressed genes in adult female fig wasps special roles in adult female development.

Genes clustering in modules yellow and green were highly expressed in the pupa stage of the fig wasp.Female and male pupa exhibited the same levels of expression. Thus,these genes might play roles in pupa morphogenesis. For example， CSO_O10218, which was annotated by $\mathrm { F B g n 0 0 } 3 0 6 6 2 ^ { \left[ 2 5 \right] }$ ，might be a component of the golgi cisterna membrane and be involved in glucuronosyltransferase activity; it may also function in the chondroitin sulfate biosynthetic process [26]. Ecdysteroid UDP-glucosyltransferases were shown to play a role in the conjugation of ecdysteroids with glucose or galactose [27]. Similarly, CSO_004410 (annotated by FBgnOo8668O) was found to be a RNA polymerase II core promoter in the proximal region of sequence-specific DNA binding transcription factor activity involved in positive regulation of transcription[28]. Further，CSO_004410 might play roles in motor neuron axon guidance [29]， regulation of dendrite morphogenesis[30] and brain development[31].

# 3Discussion

# 3.1Highly co-expressed genes clustered into five expression-modules

The fig wasp is a good organism for studying the co-expression of genes in males and females that exhibit extrememorphological dimorphism. We obtained 2 938 differentially expressed genes from 11 506 annotated genes in RNA-seq data. $G E$ values were used to remove lowly expressed genes [12] and $C V$ valueswereemployed toidentifydifferentially expressed genes [3]． To ascertain the most relevant genes， WGCNAwasused to clusterhighly co-expressed genes, those with a weight greater than 0.476[15]， into five expression-modules. Genes in modules turquoise and blue were co-expressed,as were genes in module brown and green.Genes in modules turquoise and blue were highly expressed in female fig wasp only.Further,genes in module green, brown and yellow were expressed mainly in pupae, suggesting involvement in the development of fig wasps.Genes in module yellow did not cluster with genes in modules brown or green， suggesting unique functions of genes in each module.Five differentially expressed gene modules were obtained,and genes function of these modules might be different to each other. The finding was useful for the exploration of fig wasp gene functions.

# 3.2 Modules with a low-fold change score are revealing

Highly correlated genes can facilitate explorations into the roles genes play in divergent phenotypes. Different modules appear to have different functional enrichments.Modules with a low-fold change score might have unknown functional enrichments. For example, genes in modules blue and turquoise belong to the same co-expression network,but they have different functional enrichment scores and the same situation occurs in modules brown and green.These observations suggest that most genes functions await detailed annotation.

AcknowledgementsWe are grateful to Dr.GU Hai-Feng for help in constructing the network.

Supplementary materialFigures $s 1 \sim s 5$ ，Tables $s 1 \sim s 3$ are available at paper online(http://www.pibb. ac.cn).

# References

[1]Ficklin S P,Feltus FA.Gene coexpression network alignment and conservation of gene modules between two grass species:maize and rice.Plant Physiol,2011,156(3): 1244-1256   
[2]Allen JD,Xie Y,Chen M,et al. Comparing statistical methods for constructing large scale gene networks.PLoS One,2012,7(1): e29348   
[3]Fuller TF,Ghazalpour A，Aten JE,et al．Weighted gene coexpression network analysis strategies applied to mouse weight. Mamm Genome,2007,18(6-7): 463-472   
[4]MillerJA, Oldham MC,Geschwind DH.A systems level analysis of transcriptional changes in Alzheimer's disease and normal aging. JNeurosci,2008,28(6): 1410-1420   
[5]Plaisier CL,Horvath S,Huertas-Vazquez A,et al.A systems geneticsapproach implicates USF1,FADS3,and other causal candidate genes for familial combined hyperlipidemia.PLoS Genet, 2009,5(9): e1000642   
[6]Kadarmideen HN,Watson-Haigh N S,Andronicos N M. Systems biology of ovine intestinal parasite resistance: disease gene modules and biomarkers.Mol Biosyst,2011,7(1):235-246   
[7]Rosen E Y,Wexler E M,Versano R,et al.Functional genomic analyses identify pathways dysregulated by progranulin deficiency, implicating Wnt signaling. Neuron,2011,71(6): 1030-1042   
[8]Winden K D,Karsten S L,Bragin A,et al．A systems level, functional genomics analysis of chronic epilepsy.PLoS One,2011, 6(6): e20763   
[9]Xiao JH, Yue Z, Jia L Y,et al. Obligate mutualism within a host drives the extreme specialization of a fig wasp genome.Genome Biol,2013,14(12): R141   
[10] JiaL Y,Xiao JH,Niu L M,et al. Delimitation and description of the immature stages of a pollinating fig wasp,Ceratosolen solmsi marchali Mayr (Hymenoptera: Agaonidae)．Bull Entomol Res, 2014,104(2): 164-175   
[11] Mortazavi A,Williams B A,Mccue K,et al. Mapping and quantifying mammalian transcriptomes by RNA-Seq. Nature Methods,2008,5(7): 621-628   
[12]Filteau M,Pavey SA,St-Cyr J,et al.Gene coexpression networks reveal key drivers of phenotypic divergence in lake whitefish.Mol Biol Evol,2013,30(6): 1384-1396   
[13] Mao L，Van Hemert JL,Dash S,et al．Arabidopsis gene co-expression network and itsfunctional modules. BMC Bioinformatics,2009,10:346   
[14] Langfelder P,Horvath S.WGCNA:an R package for weighted correlation network analysis.Bmc Bioinformatics,2Oo8,9: 559   
[15] Zheng Z L，Zhao Y. Transcriptome comparison and gene coexpression network analysis provide a systems view of citrus response to 'Candidatus Liberibacter asiaticus'infection.BMC Genomics,2013,14: 27   
[16] De Hoon M J,Imoto S,Nolan J,et al.Open source clustering software.Bioinformatics,2004,20(9):1453-1454   
[17]EisenMB,SpellmanPT,BrownPO,etal.Cluster analysis and display of genome-wide expression patterns.Proc Natl Acad Sci USA,1998,95(25): 14863-14868   
[18] Johnson M, Zaretskaya I,Raytselis Y,et al.NCBI BLAST: abetter web interface.Nucleic Acids Res,2O08,36(Web Server issue): W5-9   
[19] Huang Da W,Sherman B T,Lempicki R A.Systematic and integrative analysis of large gene lists using DAVID bioinformatics resources.Nat Protoc,2009,4(1): 44-57   
[20] Shannon P,Markiel A,Ozier O,et al.Cytoscape:a software environment for integrated models of biomolecular interaction networks.Genome Res,2003,13(11): 2498-2504   
[21] Morrison D K,Murakami M S,Cleghon V.Protein kinases and phosphatases in the Drosophila genome.JCell Biol,20o0,150(2): F57-62   
[22] Gilliland WD,Hughes SE,Cotitta JL,et al. The multiple roles of mpsl in Drosophila female meiosis.PLoS Genet,2007,3(7): e113   
[23] Gilliland WD,Wayson S M,Hawley R S.The meiotic defects of mutants in the Drosophila mpsl gene reveal a critical role of Mps1 in the segregation of achiasmate homologs.Current Biology,2005, 15(7): 672-677   
[24]Forbes AJ, Spradling AC,Ingham PW,et al. The role of segment polarity genes during early oogenesis in Drosophila.Development, 1996,122(10): 3283-3294   
[25] Ju T,Brewer K,D'souza A,et al.Cloning and expression of human core 1 betal,3-galactosyltransferase.JBiol Chem,2O02,277(1): 178-186   
[26] Wilson IB.Glycosylation of proteins in plants and invertebrates. Curr Opin Struct Biol, 2002,12(5): 569-577   
[27] Oreilly D R. Baculovirus-encoded ecdysteroid Udp-glucosyltransferases. Insect Biochemistry and Molecular Biology,1995,25(5):541-550   
[28] JunellA, Uvell H,PickL,et al.Isolation of regulators of Drosophila immune defense genes by a double interaction screen in yeast. Insect Biochem Mol Biol,2007,37(3): 202-212   
[29] Certel SJ,Thor S. Specification of Drosophila motoneuron identity bythe combinatorial action of POU and LIM-HD factors. Development,2004,131(21): 5429-5439   
[30] Hasegawa E,Kitada Y,Kaido M,et al. Concentric zones,cell migration and neuronal circuits in the Drosophila visual center. Development,2011,138(5): 983-993   
[31] Meier S,Sprecher SG,Reichert H,et al. ventral veins lacking is required for specification of the tritocerebrum in embryonic brain development of Drosophila. Mech Dev,2006,123(1):76-83

# 榕小蜂基因共表达研究

崔东亚1,2,3)\*\*孙旭斌1,2)\*\*王佳佳1,2）张鹏2）孙宝发4)陈小伟 Robert W.Murphy何顺民 2)\*\*\*黄大卫1,2\*\*\*(河北大学生命科学学院，保定071002；中国科学院动物研究所系统与进化重点实验室，北京 100101;3运城学院生命科学系，运城04000；中国科学院基因组研究所，北京100101；中国科学院生物物理研究所，北京 100101;③ Centre for Biodiversity and Conservation Biology,Royal Ontario Museum,Toronto M5S 2C6,Canada)

摘要榕小蜂的雌雄个体之间存在很大表型差异，以至于很难将雌雄个体彼此联系在一起．以对叶榕传粉榕小蜂作为材料，利用“加权基因共表达网络分析”软件(WGCNA)，对榕小蜂的基因组和转录组进行分析，结果发现，5个基因共表达模块，分别用蓝色、蓝绿色、棕色、绿色和黄色标识，其中2个模块偏爱在雌蜂中表达，3个模块偏爱在蛹中表达．基因本体(GO)分析发现在蓝绿色和黄色表达模块中发现3个功能富集的基因集合．在蓝绿色基因表达模块中发现2个基因集合，分别与细胞周期和核苷酸结合活性有关；在黄色基因表达模块中发现1个基因结合，与细胞分化有关，尤其是与神经发育有关.

关键词共表达，网络，功能富集学科分类号Q7

DOI:10.16476/j.pibb.2015.0287

# 附录

![](images/b88397801cd13774516194a7bb30f6bcabceb4f53429deb6e6bca6b5657b0b59.jpg)  
Fig.S1 Frequency distribution of characteristic path length

This figure was output directly by NetworkAnalyzer in Cytoscape $\mathbf { { v } } 2 . 6 . 3$ . The $x$ axis represents the shortest path length,which represents theexpected distance between two connected nodes,and the $y$ axis represents frequency.

![](images/aa24a307480fe2fde6d3ec7971c3d43efac58695b691d8a46ea81f783a9bc9cd.jpg)  
Fig.S2Frequency distribution of shared neighbors

This figure was output directly by NetworkAnalyzer in Cytoscape $\mathbf { v } 2 . 6 . 3$ . The shared neighbors represent the connections between neighbors. The $x$ -axis represents the number of shared neighbors,and the $y$ -axis represents frequency.

![](images/1129df621085c0f669701848dffb43317d5750ea4499e55db0bf2153a20bc4ff.jpg)  
Fig.S3Topological coefficient of neighbors

ThisfigureasoutputdtlyyetwoAaliyosaeTtlogcaloeetiselatiemeasuofetetch shares neighbors with other nodes. The $x$ -axisrepresents the number of neighbors,and the $y$ -axisrepresents the topological coefficient.

![](images/ab55eb5242a79c9fc06f8cb15ab9df7474c0adb933563db56094ab1e041a935b.jpg)  
Fig.S4Node degree distribution

Thifigure asoutputectlyyetwAalyeinoa6eumberofodeses)plotedspropertyoftregf connections with other nodes)shows apower-lawlikedistribution,which indicatesascale-free network topology

![](images/eb022c97c4c151721c290bdf1f23acc2e46eb1b72b85cfc8a4bf725eef774f9b.jpg)  
Fig.S5Heatmap for the expression of genes in five modules

ThisfigurewaseaedusiCustedeiowrftsoattdolosdateerexpresdeoe brillant green colors represent lower expression. The $\mathbf { x }$ -axis represents four different developmental stages in the fig wasp (larva,21-daypupa,25-day pupa and adults),while the y-axis represents the different genes.

Table S1Simple parameters of the network  

<html><body><table><tr><td>Serial number</td><td>Property</td><td>Value</td></tr><tr><td>1</td><td>Clustering coefficient</td><td>0.4081)</td></tr><tr><td>2</td><td>Connected components</td><td>4</td></tr><tr><td>3</td><td>Network centralization</td><td>0.1621)</td></tr><tr><td>4</td><td>Network heterogeneity</td><td>1.3101)</td></tr><tr><td>5</td><td>Characteristic path length</td><td>3.4622)</td></tr><tr><td>6</td><td>Network radius</td><td>12</td></tr><tr><td>7</td><td>Network diameter</td><td>102</td></tr><tr><td>8</td><td>Avg.number of neighbors</td><td>8.2143</td></tr><tr><td>9</td><td>Number of nodes</td><td>336</td></tr><tr><td>10</td><td>Network density</td><td>0.025</td></tr><tr><td>11</td><td>Shortest path</td><td>403062)</td></tr></table></body></html>

Column 1 lists the number of simple parameters.Column 2 lists the names of the basic properties.Column 3 lists the corresponding value of each property in the gene co-expression network. The parameter associated with scale-free distribution.²The parameter associated with shortest path length.The parameter associated with the number of neighboring nodes.