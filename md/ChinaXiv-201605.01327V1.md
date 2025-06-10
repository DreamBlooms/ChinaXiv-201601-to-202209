# Computational analysis of antigenic epitopes of avian influenza A (H7N9) viruses

LIU Mi1,2†,SONG TingRui1†, HUA Sha12, WU AiPing1\* & JIANG TaiJiaol

1Institute of Biophysics,Chinese Academy of Sciences,Beijing1Ooio1,China; ²University of Chinese Academy of Sciences,Beijing l0o049, China

Received March 30,2015;accepted May 15,2015; published online June 19,2015

Influenza virus canrapidlychange itsantigenicity,via mutationinthe hemagglutinin (HA)protein,toevade hostimmunity. The mergence ofthe novel human-infectingavian H7N9 virus in China has caused widespreadconcern.However,evolution of the antigenicityof thisvirusisnotwelluderstood.Here,weinferredtheantigenicepitopesoftheHAproteinfromallH7 viruses,based on the fivewel-characterized HA epitopes of the human H3N2 virus.Bycomparing the two majorH7 phylogenetic lineages,i.e.,theEurasianlineage andtheNorthAmerican lineage,wefoundthat epitopes AandBaremorefrequently mutated intheEurasian lineage,whileepitopes BandCare more frequentlymutated inthe North American lineage.Furthermore,we foundthat the novel H7N9 virus (derivedfrom theEurasian lineage)isolated in Chinaintheyear 2O13,contains six frequentlymutated sites onepitopes that include site135,which islocatedinthereceptorbindingdomain.This ndicates that the novel H7N9 virus that infects human may already have been subjected to gradual immune pressure and receptor-binding variation.Ourresults notonlyprovideinsights into theantigenicevolutionofthe H7virus but mayalsohelpin the selection of suitable vaccine strains.

# antigenic epitope,antigenic evolution, hemagglutinin,influenza H7N9 virus

Citation: LiuM,SongT,HuaWuJangputatiolalysisftigeciopsofeA()sciaLie 2015,58:687-693,doi:10.1007/s11427-015-4886-4

The avian influenza A virus of the H7 subtype isclassified asa low pathogenic avian influenza (LPAI) virus and has caused sporadic human infections in recent years [1,2].In the spring of 2013,an outbreak of the novel H7N9 virus occurred in a poultry in east China [3-6] that later caused human infections and deaths [4].Based on two major sequential re-assortments with the H9N2 virus,we inferred that the virus originated from both wild birds and domestic poultry[7].Recently,Lam et al. [8] analyzed H7N9 viruses that had emerged betweenDecember 2O13 and April 2014, and found that H7N9 had spread from eastern to southern China,generating multiple distinct lineages.The rapid evolution of this virus caused widespread concern,due to its changing pathogenesis,host adaptation [9,1O],and antigenicity.

Hemagglutinin (HA), the main antigen and major surface protein of the influenza A virus,is key to the process of infection caused by this virus.It is the primary target for neutralizingantibodies,which further inhibits attachment of the virus to the target cells and subsequent membrane fusion [11].In order to evade surveillance by the host's immune system,the influenza virus has gained the ability to change the antigenic properties of HA through mutationor re-assortment of the corresponding gene.Usually,HA antigenic properties are determined by a group of residues clustered into regions called epitopes.More specifically, the HA epitopes are composed of amino acids that directly interact with the neutralizing antibodies [12]. Thus,rapid mutation of HA epitopes could disrupt its interaction with antibodies, resulting in viral immune escape.

Given their critical role in influenza antigenic variation and strain selection for flu vaccines,many studies on influenza virus have focused on HA epitopes.Human H3N2 virus HA epitopes have been well characterized; they consist of five epitopes(A-E)[13-15]. Additionally,by comparing the HA structures,the $\mathrm { H } 3 \mathrm { \ H A }$ epitopes were used to define the epitopes for H1 and H2 HA[16]. More recently, using computational integration，we have formed a comprehensive picture of HA epitopes of highly pathogenic avian H5N1 viruses [17].

In this study,by integrating epitope regions mapped from well-characterized H3N2 viruses,we inferred the antigenic epitope regions of H7,and analyzed mutations on five inferred epitopes for both lineages of H7 viruses.We further investigated the mutation frequencies of the different epitopes during the evolution of the two H7 lineages,and found that,although the mutations differ between the two lineages,epitope B changed frequently in both lineages. Furthermore,we identified new mutations that occurred in the five inferred epitopes of the 2O13 H7N9 viruses,which showed significant changes in the antigenicity of this new H7N9 virus as compared to earlier H7N9 viruses.These findings yield insight into the antigenicity of H7N9 and may facilitatesurveillanceof influenzaH7N9andvaccineselection.

# 1Materials and methods

# 1.1 Data preparation

Full-length HA sequences of human influenza H3N2 viruses, avian influenza H7 viruses,and H7N9 viruses were obtained from the NCBI Influenza Virus Resource [18] on March 16,2O15.Laboratory-derived and identical HA sequences were removed.For each subtype,the HA sequences were aligned using MUSCLE software [19],and the alignments were checked manually.After alignment, the signal peptide regions were removed and the sequences with X character content exceeding $10 \%$ were eliminated.Thisresulted in the inclusion of $6 1 1 ~ \mathrm { H A 1 }$ sequences for H7 and $3 3 4 3 \ \mathrm { H A l }$ sequences for human H3N2.We obtained 467 and 87 HA1 sequences for avian and human-infecting H7N9 viruses,which were collected since the 2O13 outbreak.ThestructuraldataforH7HA(A/NETHERLANDS/ 219/2003(H7N7)，PDB ID is 4DJ8)，H3N2 HA (strain A/AICHI/2/1968(H3N2)，PDBID: 5HMG)，H1N1 HA (A/Puerto Rico/8/1934(H1N1),PDBID:1RU7),H2N2HA (A/Japan/305/1957(H2N2),PDB ID:3KU3),and H5N1HA (A/Indonesia/5/2005(H5N1), PDB ID:4K64) were downloaded from theProtein Data Bank(PDB） database (http://www.rcsb.org/pdb/home/home.do).

# 1.2 Site entropy

Information entropy for each site was computed using the method describedbyWileyand Skehel[15].For each position,the information entropy was further normalized by the base entropy (natural logarithm of 2O),which was computed by assuming even distribution of the 2O amino acids.To illustrate the differences among sites more clearly,we defined relative entropy，which was calculated as the ratio of information entropy for each site to the average entropy.

# 1.3Mapping the epitope from H3 HA to H7 HA

The crystal structure ofH7HA(A/NETHERLANDS/219/ 2003(H7N7), PDB ID: 4DJ8) was aligned to that of $\mathrm { H } 3 \mathrm { \ : H A }$ (strain A/AICHI/2/1968(H3N2), PDB ID: 5HMG) by using TM-align [2O]. Then, the sites in H7 HA corresponding to those of the A-E epitopes in H3 were defined as candidate antigenic sites for H7. Since the antigenic regions are thought to be exposed, only the surface residues of the H7 structure 4DJ8 were retained.A residue was identified as exposed when the Accessible Surface Area (ASA),which Was calculated using the NACCESS program [21] based on the HA trimetric complex of 4DJ8, exceeded $1 \mathrm { \AA } ^ { 2 }$ ：

# 1.4 Construction of the phylogenetic tree

A phylogenetic tree of all H7 and H7N9 sequences was constructed by the neighbor-joining(NJ） method using the PHYLIP package [22].

# 2 Results

# 2.1Inferring five epitopes of H7 based on H3

Previous studies showed that influenza viruses withdifferent HAsubtypes may share similar antigenic structures[16,23,24] Moreover, the HAs of H7 and H3 subtypes belonged to the same clade [25]. Our structural comparison showed that the HA structures of the H7 virus and the human H3N2 virus are quite similar，with a TM-score of O.936,and a root-mean-square deviation (RMSD) of 1.66 (Figure 1A). The TM-score and RSMD of H7 were O.882 and 2.43,when compared to H1N1，0.902 and 2.15 when compared to H2N2,and O.886 and 2.26 when compared to H5N1. This suggested that H7 and H3N2 viruses shared a similar antigenic structure.Furthermore,we aligned the local structures of each epitope of H7 and H3N2 viruses,and found the RMSD for epitopes A-E to be 1.20,1.52,1.07,1.42,and 1.71,respectively.Based on the structural comparison of HAs,we mapped the five known epitopes of human H3N2 HA onto H7 HA (see Materials and methods). In this way, we inferred 13O antigenic sites for the H7 subtype:18,22, 27,41,and 22 antigenic sites for epitopes A,B,C,D,and E respectively (Figure S1).

![](images/2e745a1c06d78c32b527c8d34893e296fd6e1ae831baaaa992398ed4593a0be0.jpg)  
Figure tionfH7adHcbsofdHeolodyeloduplespecielyaogtfoa cladesrthood North American lineage (C),H7Eurasian lineage and H3N2viruses (D),andH7North Americanlineageand H3N2 viruses (E).

# 2.2Mutational profiles of HA from H7 Eurasian and North American lineages

As shown in the phylogenetic tree (Figure 1B),sequences of H7 mainly clustered into two lineages，i.e.， the Eurasian lineage and the North American lineage. Thus, we compared the similarities and differences of mutational profiles of HA1 among the H7 Eurasian lineage,the H7 North American lineage,and human H3N2 viruses (the latter was used as a reference). Mutational profiles were represented with relative entropies on all HA1 sites.As expected, the mutational profiles of HA1 for the H7Eurasian lineage was significantly correlated with that of the H7 North American lineage,with a Pearson's correlation coefficient of 0.51 $( P { < } 2 . 2 { \times } 1 0 ^ { - 1 6 }$ ,Figure 1C). This showed that HA1 of both lineages experienced similar selection pressures.Pearson'scorrelation coefficientsbetween the human H3N2 and H7 lineages exceeded 0.3( $( P { < } 1 . 2 { \times } 1 0 ^ { - 8 }$ ， Figure 1D and 1E),indicating that these were also significantly correlated.

# 2.3Mutations of five antigenic epitopes of H7 Eurasian and North American lineages

Although the mutational profiles of HA of the H7 Eurasian and North American lineages presented significant similarity,some differences were also observed,especially for five antigenic epitopes (Figure 1C-1E). Furthermore,we compared the average entropies of the five antigenic epitopes, receptor-binding domains (RBD),and other sites of the two H7lineages and human H3N2 viruses.Mutations in epitope D had relatively low frequencies,while mutations in epitope B had relatively high frequencies in both H7 and H3 viruses. Mutations in epitopes A and B of H7 Eurasian lineage were relatively higher than for the other three epitopes (Figure 2B).As for the H7 North American lineage,epitope C showed extremely high levels of mutation rates，while epitopes A and D had a low level of mutation rates (Figure 2C),which differed from the H7 Eurasian lineage.Further more,we found that the RBD sites of the H3N2 virus showed markedly higher frequencies of mutation than did the two H7 lineages.

![](images/cad193a96949ef76bed77260228d80ee7e8a035ad3aba81537a9bc585918c3e5.jpg)  
Figure 2Average site entropies of five epitopes and the receptor-binding domain of both H7 lineages and human H3N2 viruses.A-C,Average site entropies of five epitopes,the receptor-binding domain (RBD),and other sites of the H7 Eurasian lineage (A),the H7 North American lineage (B), and H3N2 viruses (C).

Furthermore,we attempted to identify sites with relatively high mutation rates in the receptor-binding domain. Those sites with entropies greater than the average entropy were regarded as high mutation-rate sites,and otherwise as low mutation-rate sites.In total, there were 15, 8,and 4 high mutation-rate sites for human H3N2, H7 Eurasian lineage, and H7North American lineage viruses,respectively.The common high mutation-rate sites were positions 135,158, and193,while p0sitions 98,134,153,183,194,195,224, and 228 (numbering in H3） were relatively conservative sites for the human H3N2 virus and the two H7 lineages (Figure 3).

# 2.4Mutations in HA of H7N9 viruses isolated in China from 2013 to 2014 and in the previously reported avian H7N9 virus

Some sites in the RBD are highly conserved among avian viruses,while these sites bear significant substitutions in human viruses [26]. By comparing the human-infecting H7N9 viruses isolated in China between 2O13 and 2014 to thepreviously reported avian H7N9 viruses,we discovered that most amino acids were conserved in the RBD,while positions 186,189,and 226 differed (H3 numbering; Figure 2；Table 1).Substitution G186V had already reported to influence receptor-binding specificity in Eurasian H7 viruses [27],while Q226L had previously been reported to increase the binding affinity to the human receptor for $\mathrm { H } 7 \mathrm { H A }$ [28].Some other mutations were also observed in other inferred antigenic sites,such as position 122 in epitope A, position 312 in epitope C,and positions 174 and 179 in epitope D (H3 numbering;Table 1).Furthermore,we compared human-infecting H7N9 viruses to avian H7N9 viruses isolated in mainland China from 2013 to 2O14 (Table 1). Most sites were identical, except for position 57,which was located on epitope E.In human-infecting H7N9 viruses, the majority had anR at position 57,whereas most avian influenza H7N9 had K at this position.

# 2.5Evolution of HA1 in H7N9 viruses during 2013 to 2014

Sincetheoutbreakin 2O13,avianH7N9viruseshave been circulating in China.To investigate the evolution of H7N9 during the past two years,we mapped the dynamic changes in the amino acids along the phylogenetic tree (Figure 4A), and listed the sites with less than $9 5 \%$ conservation. Among the nine sites,sites 132 and 135 were on the inferred epitope A,site 312 was on the inferred epitope C, site 177 was on the inferred epitope D,and sites 57 and 59 were on the inferred epitope E,while site 135 was in the RBD.Furthermore，we investigated the amino acid differences between human-infecting H7N9 viruses and avian H7N9 viruses (Figure 4B).Avian H7N9 virus demonstrated mutation at all nine sites,while in human-infectingH7N9 viruses,sites 59,114,177,and 255 remained quite conserved.During the early stage of the H7N9 outbreak,most sites remained conserved duringMarchto Mayof 2O13.However,from January to March of 2O14,all nine sites underwent significant mutation in the avian H7N9 viruses.Most altered amino acids in the human-infecting viruses were consistent with those in avian viruses,except for site 135,which had an S or $\mathrm { \Delta T }$ substitution, forming an N-linked glycosylation site. The A135T substitution of H7N9 had already been reported by Xu et al. [29],and had also been reported as a genetic marker for mammalian adaptation and virulence in other human-infecting avian influenza viruses, such asH1ON8[3O].

Tablefsaol each site)   

<html><body><table><tr><td>Epitope</td><td>Numbering in H3</td><td>Avian H7N9 before 2013a</td><td>Human-infecting H7N9 (2013-2014)</td><td>Avian H7N9 after 2013b)</td></tr><tr><td>A</td><td>122</td><td>T</td><td>A</td><td>A</td></tr><tr><td>B</td><td>186</td><td>G</td><td>V</td><td>V</td></tr><tr><td rowspan="2">C</td><td>189</td><td>T</td><td>A</td><td>A</td></tr><tr><td>312</td><td>E</td><td>R</td><td>R</td></tr><tr><td rowspan="2">D</td><td>174</td><td>D</td><td>S</td><td>S</td></tr><tr><td>179</td><td>I</td><td>V</td><td>V</td></tr><tr><td></td><td>226</td><td>Q</td><td>L</td><td>L</td></tr><tr><td>E</td><td>57</td><td>K</td><td>K</td><td>R</td></tr></table></body></html>

a)AllavianH7N9virusesbeforethe2O13H7N9outbreak.b)AvianH7N9virusescirculatinginmailandChinaduring2012014

![](images/42d0fe4dd4d22aacd82e1d8fe0150ca88f0657f4df55ab9c3ebbd0f72a1edd71.jpg)  
Figure 3Site entropies of the receptor-binding domain of both H7 lineages and human H3N2 viruses.

![](images/b9415714da022baeb25060b5245ab4df0b3072c81a6339937e1af52ae9769b58.jpg)  
FigureEvoutioofHviusesfto4.AgenetctrofH7virusessolatediChinaurig4achgsin amino acids are shown along the tree (only sites with conservation less than $9 5 \%$ were listed).B,Dynamic changes in amino acids over time are displayed. Avian H7N9 viruses are shown on the left,human-infecting H7N9 viruses are shown on the right. $^ *$ ：Site $2 7 6 \substack { + 1 }$ means the gap between sites 276 and 277 (H3 numbering) in TM-align.

# 3Discussion

In this study,we inferred the antigenic epitopes of the H7 subtype influenza virus and analyzed the antigenicity in both H7 subtype lineages and human influenza H3N2 viruses.Five epitopes were mapped from the human H3N2 virus.H7 fell in the same clade as H3 in terms ofHA classification,and is very likely to share a similar antigenic structure with H3.Moreover, the $\mathrm { H } 3 \mathrm { H A }$ epitopes were used to define the epitopes for H1 and H2 HA [16,23]. Thus,it was reasonable to infer the antigenic sites of H7 based on antigenic sites of human H3N2.

There are two main lineages,the Eurasian and North American lineages,in the phylogenetic tree of H7 viruses (Figure 1B). These two lineages showed different patterns in their antigenic sites.Epitopes A and B showed a high frequency of mutation in the Eurasian lineage,while epitopes B and C were frequently mutated in the North American lineage. Those results suggested that epitope B Was immune-dominant in H7 viruses. Compared to the former H7N9 virus, the $2 0 1 3 \ \mathrm { H } 7 \mathrm { N } 9$ virus circulating in China had particular mutations,and most of them were located in the inferred epitopes.Among these substitutions,some were non-conserved substitutions，such as T122A，E212R，and D174S,which suggested that these human-infecting H7N9 viruses may already have experienced gradual host immune pressure.Positions 186,189,and 226 (in H3 numbering), located in the receptor-binding region，also demonstrated non-conserved substitutions (G186V,T189A，and Q226L), and the two substitution at positions 186 and 226 were reported to influence the receptor-binding activity of the H7 virus [27,28]. The latter may indicate that human-infecting H7N9 viruses have also experienced certain host binding variation.

We also compared dynamic changes in HA1 in human-infecting H7N9 viruses to avian influenza H7N9 viruses from 2O13 to 2O14,but found no significant differences between these two categories of viruses.For human-infecting H7N9,most amino acid changes were consistent with avian H7N9,supporting the continuous transmission from avian to human hosts.Interestingly,site 135 showed S and T substitutions in the human-infecting H7N9 virus,which resulted in formation of an N-linked glycosyla tion site. Since genetic evolution is a continuous process, mutations in avian influenza H7N9 should continue to be monitored,and particularly at those sites in known epitopes and in the RBD,which may further cause human-to-human transmission.

In summary,we have inferred five antigenic epitopes for the H7 subtype influenza virus and have further analyzed the mutation patterns of each of these epitopes.We also identified new mutations in the 2O13 H7N9 virus.Our findings will facilitate monitoring of antigenic changes of this new virus,and may enhance H7N9 surveillance and vaccine selection.

Weare grateful to the authors who submitted the sequencesused in this study to GenBank.This study was supported by the National Basic ResearchProgramofChina(2015CB9i0501),theMajorNational Earmark Project forInfectiousDiseases (20l4ZXl0004002-001),theKey Research Program of the Chinese Academy of Sciences (KJZD-EW-Lo9-1-2） to JiangTaiJiao,andtheNationalNatural ScienceFoundationof China (31470273) to Wu AiPing.

1 Kurtz J,Manvell RJ,Banks J.Avian influenza virus isolated from a woman with conjunctivitis.Lancet, 1996,348: 901-902   
2 Banks J,Speidel E,Alexander DJ.Characterisation of an avian influenza A virus isolated from a human—is an intermediate host necessary for the emergence of pandemic influenza viruses? Arch Virol,1998,143: 781-787   
3 Shi JZ,Deng GH,Liu PH, Zhou JP,Guan LZ,Li WH,Li XY,Guo J, Wang GJ,FanJ,Wang JL,LiYY,Jiang YP,Liu LL,Tian GB,Li CJ Chen HL.Isolation and characterization of H7N9 viruses from live poultry markets—Implication of the source of current H7N9 infection in humans.Chin Sci Bull,2013,58:1857-1863   
4 Gao R,Cao B,HuY,Feng Z,WangD,Hu W,Chen J,Jie Z,Qiu H, Xu K,Xu X,LiH, Zhu W,Gao Z,Xiang N, Shen Y,He Z,Gu Y, Zhang Z,Yang Y,Zhao X,Zhou L,Li X, Zou S, Zhang Y,Li X, YangL,Guo J,DongJ,LiQun,DongL,Zhu Y,BaiT,WangS,Hao P,YangW,ZhangY,HanJ,YuH,LiD,Gao GF,Wu G,Wang Y, Yuan Z,Shu Y.Human infection with a novel avian-origin influenza A(H7N9) virus.N EnglJMed,2013,368:1888-1897   
5 Wu Y,Gao GF.Lessons learnt from the human infections of avian-origin influenza A H7N9 virus:live free markets and human health. Sci China Life Sci,2013,56:493-494   
6 Chen Y,Liang W,Yang S,Wu N, Gao H, ShengJ,Yao H,Wo J, Fang Q,Cui D,LiY,Yao X,ZhangY,WuH,Zheng S,Diao H,Xia S, Zhang Y,Chan KH,Tsoi HW,Teng JLL,Song W,WangP,Lau SY,Zheng M.Human infections with the emerging avian influenza A H7N9 virus from wet market poultry:clinical analysisand characterisation of viral genome.Lancet,2013,381:1916-1925   
7 WuA,Su C,WangD,PengY,Liu M,HuaS,LiT,Gao GF,TangH, Chen J,Liu X, Shu Y,Peng D,Jiang T. Sequential reassortments underlie diverse influenza H7N9 genotypes in China.Cell Host Microbe,2013,14: 446-452   
8 Lam TTY,Zhou B,Wang J,Chai Y, Shen Y,Chen X,Ma C,Hong W, Chen Y,Zhang Y,DuanL,ChenP, JiangJ,ZhangY,LiL,Poon LLM,Webby RJ,Smith DK,Leung GM,Peiris JSM,Holmes EC, Guan Y,Zhu H.Dissemination,divergence and establishment of H7N9 influenza viruses in China.Nature,2015,522:102-105   
9 LiJ,Yu XF,Pu XY,XieL,Sun YX,Xiao HX,WangFJ,Din H,Wu Y,Liu D,Zhao GQ,Liu J,Pan JG.Environmental connections of novel avian-origin H7N9 influenza virus infection and virus adaptation to the human. Sci China Life Sci,2013,56: 485-492   
.0 Liu D,Gao GF.The new emerging H7N9 influenza virus indicates poultry as new mixing vessels.Sci China Life Sci,2014,57:731-732   
11 Barbey-Martin C,Gigant B,Bizebard T,Calder LJ,Wharton SA, SkehelJJ,Knossow M.An antibody that prevents the hemagglutinin low pH fusogenic transition.Virology,2002,294: 70-74   
12 Laver WG,Air GM,Webster RG,Smith-Gill SJ.Epitopes on protein antigens: misconceptions and realities. Cell,2015,61: 553-556   
13 Webster RG，Laver WG.Determination of the numberof nonoverlapping antigenic areas on Hong Kong (H3N2） influenza virus hemagglutinin with monoclonal antibodies and the selection of variants with potential epidemiological significance.Virology,1980, 104: 139-148   
14 Skehel JJ, Stevens DJ,Daniels RS,Douglas AR,Knossow M,Wilson IA,Wiley DC.A carbohydrate side chain on hemagglutinins of Hong Kong influenza viruses inhibits recognition by a monoclonal antibody. Proc Natl Acad Sci USA,1984,81: 1779-1783   
15 Wiley DC, Skehel JJ.The structure and function of the hemagglutinin membrane glycoprotein of influenza virus.Annu Rev Biochem,1987, 56:365-394   
16 Caton AJ,Brownlee GG,Yewdell JW,Gerhard W.The antigenic structure of the influenza virus A/PR/8/34 hemagglutinin (H1 subtype).Cell,2015,31:417-427   
17 Peng Y,Zou Y,LiH,LiK,Jiang T.Inferring the antigenic epitopes for highly pathogenic avian influenza H5N1 viruses.Vaccine,2014, 32: 671-676   
18 BaoY,BolotovP,DernovoyD,KiryutinB,ZaslavskyL,Tatusova T, Ostell J,Lipman D.The influenza virus resource at the National Center for Biotechnology Information.J Virol,2008,82:596-601   
19 Edgar RC.MUSCLE: multiple sequence alignment with high accuracy and high throughput.Nucleic Acids Res，2OO4，32: 1792-1797   
20 Zhang Y，Skolnick J.TM-align:a protein structure alignment algorithm based on the TM-score.Nucleic Acids Res，2OO5,33: 2302-2309   
21 Hubbard JS，Thornton JM.NACCESS，Computer Program, Department of Biochemistry and Molecular Biology，University College London,1993,2   
22 Felsenstein J.PHYLIP (Phylogeny Inference Package） version 3.6. Distributed by the author.Department of Genome Sciences, University of Washington, Seattle,2005   
23 TsuchiyaE,SugawaraK,Hongo S,MatsuzakiY,MurakiY,LiZN, Nakamura K.Antigenic structure of the haemagglutinin of human influenza A/H2N2 virus.JGen Virol,2001,82:2475-2484   
24 Wang Q,Cheng F,Lu M,Tian X,Ma J.Crystal structure of unliganded influenza B virus hemagglutinin.JVirol,2Oo8,82: 3011-3020   
25 Corti D,Lanzavecchia A.Broadly neutralizing antiviral antibodies. Annu Rev Immunol,2013,31: 705-742   
26 Matrosovich MN，Gambaryan AS，TenebergS，PiskarevVE, Yamnikova SS,Lvov DK，Robertson JS，Karlsson KA．Avian influenza A viruses differ from human viruses by recognition of sialyloligosaccharides and gangliosides and by a higher conservation of the HA receptor-binding site.Virology,1997,233:224-234   
27 Gambaryan AS,Matrosovich TY,Philipp J,Munster VJ,Fouchier RA,Cattoli G,CapuaI,Krauss SL,Webster RG,Banks J,Bovin NV, Klenk HS,Matrosovich MN.Receptor-binding profiles of H7 subtype influenza viruses in different host species.JVirol,2O12,86: 4370-4379   
28 SrinivasanK,Raman R,Jayaraman A,Viswanathan K,Sasisekharan R.Quantitative description of glycan-receptor binding of influenza A virus H7 hemagglutinin.PLoS One,2013,8: e49597   
29 Xu R,de Vries RP,Zhu X,Nycholat CM,McBride R,Yu W, Paulson JC，Wilson IA．Preferential recognition of avian-like receptors in human influenza A H7N9 viruses.Science,2O13,342: 1230-1235   
30 To KKW,Tsang AKL,Chan JFW,Cheng VCC,Chen H,Yuen KY. Emergence in China of human disease due to avian influenza A (H10N8)—Cause for concern?JInfect,2014,68:205-215

OpeAcesss in any medium,provided the original author(s) and source are credited.

# Supporting Information

Figure S1TM-align of H7HA (A/NETHERLANDS/219/2003(H7N7)and H3 HA (strain A/AICHI/2/1968(H3N2).

The supporting information is available online at life.scichina.com and link.springer.com.The supporting materials are publishedassubmited,withouttypesetingorediting.Theresponsibilityforsientificauracyandcontentremainsetiely with the authors.