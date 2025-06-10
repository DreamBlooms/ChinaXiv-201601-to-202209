# Reversible transient nucleation in ionic solutions as the precursor of ion crystalization

This content has been downloaded from IOPscience. Please scroll down to see the full text.

2014EPL10730005

(http://iopscience.iop.0rg/0295-5075/107/3/30005)

View the table of contents for this issue,or go to the journal homepage for more

Download details:

IPAddress:128.151.144.230   
This content was downloaded on 07/11/2014 at 07:33

Please note that terms and conditions apply.

# Reversible transient nucleation in ionic solutions as the precursor of ion crystallization

GAN REN and YANTING WANG(a)

StateKey LaboratoryofTheoreticalPhysics,Instituteof Theoretical PhysicsandKaoli InstituteforTheoretical Physics China， Chinese Academyof Sciences - 55 East Zhongguancun Road,P.O.Box 2735 Beijing,100190 China

received 9May 2014;accepted in final form 15July 2014   
published online 1 August 2014

PACS 05.40.-a-Fluctuation phenomena,random processes, noise,and Brownian motion   
PACS 61.20.Ja-Computer simulation of liquid structure   
PACS 64.60.Q--Nucleation

Abstract - Molecular dynamics simulations for aqueous sodium chloride solutions were carried out at various concentrations.Supplementary to the Debye-Hückel theory,reversible transient nucleation of ions was observed even in dilute solutions.The average size of formed ion clusters and the lifetime of ion pairs increases with concentration until the saturation point,when ion clusters become stable and individual ions adjust their positions to form ordered lattice structures,leading to irreversible ion crystallzation, which is beyond the description of the classical nucleation theory.

Copyright $\Cup$ EPLA,2014

Introduction.- Ionic solutions play an essential role in many areas,such as biology and chemistry [1-3]. Although thermodynamic and transport properties of ionic solutions,especially dilute solutions,have been extensively investigated [4],the majority of the studies have focused on their macroscopic properties in an ensembleaveraged fashion. Theoretically， the Debye-Hickel theory[5] well describes the ensemble-averaged properties of the extremely dilute solutions and its extended version can be applied to concentrated ionic solutions [6-8] as well as to hard-sphere ionic fluids [9,1O]. However, its microscopic structures,nucleation mechanism,crystallization process, and fast dynamics are still not thoroughly understood. In particular,the instantaneous fluctuations of ionic solutions around the statistical ensemble-averaged values, which are important for a better understanding of many biological and chemical processes,are not yet adequately investigated.

In recent years,several experiments have directly or indirectly observed ion cluster formation in ionic solutions.A Raman spectroscopy study of sodium nitrate solutions revealed ion clustering in unsaturated, saturated, and supersaturated solutions,suggesting that the coalescence of clusters results in ion nucleation [11].A combined ultra-fast 2D IR and pump/probe study of vibrational energy transfers discovered the cluster formation in thio cyanate metal solutions [12]. Calcium carbonate cluster formation was also observed by transmission electron microscopy [13].In addition,molecular dynamics (MD) simulations discovered the cluster formation in sodium chloride solutions under various conditions [14-16],their physical properties and nucleation mechanisms were studied[17-19]. MD simulations also suggested that stable ion clusters in sodium chloride solutions may serve as the nuclei for ion nucleation [2O]. In calcium carbonate solutions, the stable amorphous calcium carbonate [21],liquid-like ionic nanoscale polymer structure [22],and liquid-liquid separation [23] have been observed,suggesting a completely non-classical nucleation for this system. Despite those studies on ion clusters and their relation with ion nucleation,no microscopic mechanisms have yet been pro vided to systematically explain their molecular origin and their relation with the microscopic fluctuations in ionic solutions remains elusive.

Meanwhile,details of the ion crystallization process in ionic solutions,a special case of nucleation processes,have not been fully understood.The best known and widely used classical nucleation theory (CNT) [24,25] can provide qualitative descriptions for nucleation processes.However, it suffers from a faster nucleation time than experiment for most systems [26],because in the CNT,clusters are treated as spherical droplets without interior structures and the growth of clusters is simplified to be a process with a single ion attached to or departed froma stationary nucleus at each time.More sophisticated theories，such as the Dillmann-Meier theory [27]，are still not good at describing complex systems like ionic solutions.

![](images/fc027f3470e4b528fd1bb103d129cb91d329a968482f00592226c2cf768892d8.jpg)  
Fig.1: $\mathrm { N a ^ { + } }$ -Clradial distribution functions at various concentrations.

In this letter,we report our work on MD simulations of aqueous sodium chloride solutions at a wide range of concentrations from very dilute $0 . 0 9 \mathrm { M }$ to $6 . 2 4 \ : \mathrm { M }$ well above the saturation concentration. The purpose of our current study is investigating:1） instantaneous fluctuations in ionic solutions beyond the description of the DebyeHückel theory and its extensions; 2) ion clustering in various concentrations；3） ion crystallization process above saturation. Our simulation results suggest that，below saturation，ions instantaneously aggregate to form ion clusters in different places,but the clusters quickly segregate due to thermal energy and then ions reform new clusters in other places.This reversible transient nucleation of ions occurs even in very dilute solutions,but the ensemble average over all instantaneous configurations is always uniform below saturation, to which the Debye-Hückel-type theories apply. With increasing concentration,the average cluster size and lifetime of ion pairs increase until above saturation,when the ion clusters are large enough to overcome the thermal energy and become stable.The stable clusters serve as nuclei with more ions continuously joining them and the irreversible ion crystallization occurs,when the ions in the amorphous clusters adjust their positions to form ordered lattice structures. This observed ion crystallization is likely a multistep nucleation process beyond the description of the CNT and other existing nucleation theories.It might share theoretical fundamentals with other multistep nucleation processes,such as the crystallization process in organic molecular systems [13,23,28],dendritic structure formation of silver nanoclusters [29],and selfassembly of short peptides [30].

![](images/2b6d97814b03349295d3cfb642530c09f3946bc6054584c6a1f902e6aead7712.jpg)  
Fig.2: Residence-time correlation functions for the NaCl solutions at various concentrations.

Simulation details. $-$ Aqueous sodium chloride solutions at different concentrations $c = 0 . 0 9$ ，0.92，2.14, 3.60,4.41,5.45,and $6 . 2 4 \mathrm { M }$ were simulated by using the Gromacs 4.5.4 software package [31,32] with the periodic boundary condition (PBC)applied. The particle-mesh Ewald algorithm [33] was employed to calculate the longrange electrostatic interactions.The CHARMM force field [34] and the TIP3P water model [35] were used to model the ionic solutions.The time step was 1 fs and the Nosé-Hoover thermostat [36,37] was employed to keep the system temperature constant at $T = 3 0 0 \mathrm { K }$ .The number of water molecules is 3ooo and the concentration is varied by including different numbers of ion pairs.After equilibration, $3 \times 1 0 ^ { 4 }$ different configurations were sampled for each concentration from a 60 ns $N V T$ MD simulation.All the simulations were also performed with the AMBER [38] and OPLS-AA [39] force fields and they all reached the same major qualitative conclusions.

Results.- The calculated radial distribution functions (RDFs）between $\mathrm { N a ^ { + } }$ and $\mathrm { C l ^ { - } }$ at various concentrations are plotted in fig.1. The shapes of the RDFs do not differ much from 0.09 M to 4.41M,but change a lot from 4.41M to 5.45 M, roughly showing that the saturation concentration of the aqueous NaCl solution given by the CHARMM force field and the TIP3P water model is somehow below 5.45 M and not far from the experimental value of 5.3M40l.Thehigh first peak of the RDF at $0 . 0 9 \mathrm { M }$ isattributed to the existence of ion clusters even in dilute solutions,indicating that the Debye-Hückel-type theories can only describe ionic solutions in the sense of ensemble average without instantaneous microscopic fluctuations. The crystalline features in the RDF at $c = 5 . 4 5$ M demonstrate that ions form ordered structures above the saturation concentration.It should be emphasized that throughout this paper, the saturation point we refer to is given by the CHARMM and TIP3P force fields whose exact value has to be determined by much more sophisticated method and may differ from the experimentally determined saturation point.However, the suggested qualitative physical mechanisms based on our simulation results should still be valid despite the quantitative deviation of the saturation point.

The residence-time correlation functions at various concentrations characterizing the lifetime of ion pairs are shown in fig.2.The residence-time correlation function is defined as $C ( t ) = \langle p ( 0 ) p ( t ) \rangle$ ，where $p ( t )$ is $^ { 1 }$ if a given ion is still in the same ion shell at time $t$ and $0$ otherwise,and the angular bracket represents the ensemble average over all sampled trajectories. With increasing concentration,the lifetime of ion pairs increases,demonstrating better stability of ion clusters due to their larger sizes.The lifetime drastically increases from $c = 4 . 4 1$ to 5.45 M, indicating a transition from below saturation to

100 0 0.92M 中 0 2.14M ? 10 △3.60M pgrriita 1 （%)fqaqgd H V4.41M 0.1 5.45M W □ 山 W 0.1 □ O 8 V WZ 0.0460 280 300size320 340 360 H 1 多 WT 0.01 □ 口□ 1 △△ 品 W 4 四 4 0.001 ■ W 4 V △ mm111 0.0001 L 1 L 1 0 10 20 30 40 50 60 70 size

above saturation,which is consistent with the RDFs.At the very high concentration of 6.24M, the lifetime of ion pairs becomes extremely long since most ions form irreversible stable structures.

The ion clusters were then identified to see how their sizes change with concentration.A cluster is defined as a set of ions with each ion connected with at least one other ion in the same cluster regardless of its charge and species.Two ions are considered connected if they are separated by a distance smaller than a certain cutoff.In this paper, $3 . 6 \textup { \AA }$ , the first minimum of the Na-Cl RDF, was used as the cutoff for connected ions.The probability of the appearance of a certain cluster size $i$ is defined as $\begin{array} { r } { p _ { i } = \frac { n _ { i } } { N } \times 1 0 0 \% } \end{array}$ ，where $n _ { i }$ is the number of ions composed of clusters with size $i$ and $N$ is the total number of ions. The cluster size distributions at different concentrations are shown in fig.3. Small ion clusters form even in solutions as dilute as $0 . 0 9 \mathrm { M }$ but with a small probability of about $1 \%$ .With increasing concentration,the number of single ions decreases,indicating that more ions incline to form ion clusters.Moreover,as the concentration increases,the probability of the appearance of larger clusters increases.When the concentration is above saturation,a majority of ions form large ion clusters.

The lattice heterogeneity order parameter (LHOP). which had been successfully applied to ionic liquids [41], was employed to characterize the structural fluctuations in ionic solutions. The heterogeneity order parameter (HOP) is defined as $\begin{array} { r } { h = { \frac { 1 } { N } } \displaystyle \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { N } \exp { \left( - r _ { i j } ^ { 2 } / 2 \sigma ^ { 2 } \right) } } \end{array}$ ,where $\boldsymbol { r } _ { i j }$ is the distance between ion $i$ and ion $j$ corrected by the PBC, and $\sigma = L / N ^ { 1 / 3 }$ with $L$ the side length of the cubic simulation box and $N$ the total number of ions in each cell. The LHOP, whose detailed definition can be found in ref. [42], quantifies the spatial heterogeneity in a lattice space by averaging the HOPs of all particles in the lattice.In our calculations, the simulation space was divided into $6 \times 6 \times 6$ lattices and the LHOP value was calculated for each lattice.The LHOPs for two randomly chosen instantaneous configurations are visualized in the first two columns in fig.4,and the third column illustrates theLHOPs for the ensemble-averaged configurations over 1ooO sampled configurations.The three rows in fig.4 represent the results for the concentrations of 0.92,4.41,and 5.45 M,respectively. Each cell is represented by a small sphere located in the center and colored according to the LHOP value of the cell. The color scale ranges from red to blue with colder colors representing larger LHOP values.

![](images/49003672a2b219cb480de90162274e2bb7fa2ed117555ca021fb657551e59233.jpg)  
Fig.4:Instantaneous LHOP distributions (left and middle columns） and their ensemble averages (right column） for the NaCl solution with a concentration of O.92 (first row)，4.41 (second row),or $5 . 4 5 \mathrm { M }$ (third row).

![](images/b2453c6e1b677e9d90dc342a7c54b06132a007b57dcf401b1a8736cd9ae43600.jpg)  
Fig.3: Cluster size distributions for aqueous NaCl solutions at various concentrations.The inset is the size distribution of large clusters at $5 . 4 5 \mathrm { M }$   
Fig.5:Four consecutive snapshots of an aqueous NaCl solution with a concentration of $5 . 4 5 \mathrm { M }$ during a non-equilibrium nucleation process.Larger spheres represent the ions forming clusters.

The instantaneous LHOPs for all three concentrations show that the ions are non-uniformly distributed in the simulation box,and the distribution is more non-uniform for a higher concentration. The instantaneous LHOP is different from time to time,demonstrating that ions transiently associate and dissociate driven by thermal fluctuations,but the ensemble-averagedLHOPs are much smaller than the instantaneous LHOPs.For the unsaturated solutions $c ~ = ~ 0 . 9 2$ and 4.41 M,the ensemble-averaged

LHOPs are both close to zero for all cells,indicating that the ensemble-averaged ion positions distribute uniformly and no stable nuclei exist in the solution. In contrast,for the saturated solution $c = 5 . 4 5 \mathrm { M }$ , the ensemble-averaged LHOP is still non-uniformly distributed, indicating that stable ion clusters exist and serve as the nuclei for ion crystallization. Similar instantaneous microscopic structural fluctuations have also been observed in gold nanoclusters [42] and ionic liquids [41].

As we have discussed, the CNT is too simple to explain the nucleation process of real systems except several extremely simple systems [26,27]，while some experiments and simulations [13,20,43,44] have shown that, during nucleation,macromolecules or ions are likely to form intermediate structures before they form ordered structures. In order to study the nucleation process for ion crystallization，we performed non-equilibrium MD simulations for the NaCl solution at $c = 5 . 4 5 \mathrm { M }$ for 125 ns,starting from aninitial configuration with the ionsrandomly distributed in the cubic simulation box.Four consequently sampled snapshots are shown in fig.5.At the beginning,the ions are randomly distributed in space. As time goes on,ions first associate to form disordered clusters,and then the larger clusters continue to grow and the smaller clusters shrink.When some clusters become large enough,they are thermodynamically stable and automatically reorganize to form ordered structures.The ordered ion clusters serve as the nuclei and more ions irreversibly join the nuclei to crystallize.This observation agrees with Hassan's detailed simulation study of the ion aggregation and fusion in a NaCl solution [19],and seems to fall into the description of the two-step nucleation model proposed by Erdemir et al.[45],in which monomers first associate to form large enough clusters and then the clusters self-organize to form ordered structures.

Conclusions. $-$ In summary, by using MD simulations, we have discovered the importance of transient ion nucleation as the microscopic fluctuations in ionic solutions. The reversible transient nucleation was observed even at very dilute concentrations. With increasing concentration,the transiently formed ion clusters have larger sizes and longer lifetimes.Nevertheless,the ensemble average of instantaneous spatial configurations remains uniform below the saturation concentration. Above the saturation concentration,adequately large ion clusters appear, which overcome the thermal energy perturbation and serve as stable nuclei for irreversible nucleation. The ion crystallization is a multistep hierarchical process combining this nucleation process with the self-adjustment of ion positions. This work reveals that the microscopic fluctuations in ionic solutions,which are not described in the Debye-Hückel-type theories,are the molecular origin for ion crystallization.The most recent simulation study by the Kathmann group [46] investigating the charge and electric field fluctuations in concentrated aqueous NaCl solutions seems to be supportive to our conclusions.

Although this work has only studied aqueous sodium chloride solutions,the discovered mechanisms and qualitative theoretical framework should be independent of specific force fields and can be applied to other regular ionic solutions. The microscopic fluctuations in ionic solutions may help us better understand various chemical and biological processes involving ionic solutions.

\*\*\*

Funding by the National Basic Research Program of China (973 pr0gram，No. 2013CB932804)，the National Natural Science Foundation of China (Nos. 91227115 and 11121403）and the Hundred Talent Program of the Chinese Academy of Sciences (CAS)，and allocations of computer time from the Supercomputing Center in the Computer Network Information Center at the CAS are gratefully acknowledged.

# REFERENCES

[1] GURAU M. C.， LIM S.-M.， CASTELLANA E.T., ALBERTORIO F.,KATAOKA S.and CREMER P.S.,J.Am. Chem.Soc.,126 (2004)10522. [2] ZHANG Y.and CREMER P.S.,Curr. Opin. Chem. Biol., 10 (2006) 658.   
[3] HUYNH K.A. and CHEN K.L., Environ. Sci. Technol., 45 (2011） 5564.   
[4] ROBINsON R. A. and STOKEs R. H., Electrolyte Solutions (Dover Publications,New York) 2002. [5]DEBYE P.and HUCKEL E.,Phys.Z.,24(1923) 185. [6]SCATCHARD G.，J.Am.Chem.Soc.,83(1961) 2636.   
[7] SCATCHARD G.， RUSH R. M. and JOHNSON J. S. jr., J. Phys.Chem.,74(1970) 3786. [8]PITZER K.S.,J.Phys.Chem.,77(1973) 268.   
[9] FISHER M. E.and LEVIN Y.,Phys.Rev.Lett, 71 (1993) 3826.   
[10] LEVIN Y.and FIsHER M. E.,Physica A:Stat. Mech. Appl.,225（1996）164.   
[11] RUSLI I.，SCHRADER G.and LARSON M.，J. Cryst. Growth, 97 (1989) 345.   
[12] BIAN H.,WEN X.,LI J., CHEN H.,HAN S., SUN X., SONG J.,ZHUANG W.and ZHENG J.,Proc.Natl.Acad. Sci. U.S.A., 108 (2011) 4737.   
[13] POUGET E.M.,BOMANS P.H.,GOOS J.A.,FREDERIK P.M.and SoMMERDIJK N.A., Science, 323 (2009) 1455.   
[14] KOISHI T.，YASUOKA K.and EBISUZAKI T.，J. Chem. Phys.,119 (2003)11298.   
[15] YAMANAKA S.， SHIMOSAKA A.， SHIRAKAWA Y. and HIDAKA J.,J.Nanopart. Res.,12(2009) 831.   
[16] YANG Y. and MENG S.，J. Chem. Phys.,126 (2007) 044708.   
[17] HASSAN S.A., Phys. Rev.E,77(2008) 031501.   
[18] HAsSAN S.A., J. Phys. Chem.B,112 (2008) 10573.   
[19] HASSAN S.A.,J.Chem.Phys.,134(2011) 114508.   
[20] ZAHN D.,Phys.Rev. Lett.,92(2004) 040801.   
[21] GEBAUER D.,VOLKEL A.and COLFEN H.,Science,322 (2008) 1819.   
[22] DEMICHELIS R.,RAITERI P.,GALE J.D.,QUIGLEY D. and GEBAUER D.,Nat.Commun.,2(2011) 590.   
[23]WALLACEA.F.，HEDGESL.O.，FERNANDEZMARTINEZ A.，RAITERI P.，GALE J.D.，WAYCHUNAS G．A.，WHITELAM S.,BANFIELD J.F.and DE YOREO J.J.,Science, 341 (2013) 885.   
[24] BECKER R.and DoRING W.,Ann. Phys. (N.Y.)，24 (1935)719.   
[25]BINDERK.,Rep.Prog.Phys.,50(1987)783.   
[26] OxTOBY D.W.，J.Phys.:Condens. Matter,4(1992) 7627.   
[27] DILLMANN A.and MEIER G., J. Chem. Phys., 94 (1991) 3872.   
[28] NICOLIs G.and NICOLIs C.，Physica A: Stat. Mech. Appl.,323(2003) 139.   
[29] ZHOU Q.，WANG B., WANG P., DELLAGO C., WANG Y. and FANG Y.,CrystEngComm,15(2013) 5114.   
[30]ULIJN R.V.and SMITH A. M.，Chem. Soc. Rev.，37 (2008)664.   
[31] BERENDSEN H.J.， VAN DER SPOEL D.and VAN DRUNEN R.,Comput. Phys. Commun.,91 (1995) 43.   
[32]VANDER SPOELD.，LINDAHLE., HESS B., GROENHOF G.， MARK A.E.and BERENDSEN H. J.,J.Comput.Chem.,26(2005)1701.   
[33] DARDEN T.,YORK D.and PEDERSEN L.,J. Chem.Phys., 98(1993)10089.   
[34] BROOKS B.R.，BRUCCOLERI R.E.，OLAFSON B.D., SWAMINATHAN S.and KARPLUs M., J. Comput. Chem., 4(1983) 187.   
[35]JORGENSEN W.L.,CHANDRASEKHARJ.,MADURA J.D., IMPEY R.W.and KLEIN M.L.，J.Chem.Phys.，79 (1983)926.   
[36] NosE S.,J. Chem.Phys.,81(1984) 511.   
[37]HoOVER W.G.,Phys.Rev.A,31(1985)1695.   
[38] CORNELL W.D.，CIEPLAK P.，BAYLY C.I.，GOULD I.R.，MERZ K.M.，FERGUSON D.M.，SPELLMEYER D.C.,FOX T., CALDWELL J.W.and KOLLMAN P.A., J.Am. Chem.Soc.,117(1995) 5179.   
[39] RIZzO R.C.and JoRGENSEN W.L.,J.Am.Chem. Soc., 121(1999) 4827.   
[40] HAYES W.，WETZEL R.and FREUND R.,CRC Handbook of Chemistry and Physics (CRC Press,New York) 2010.   
[41] WANG Y.and VOTH G.A.,J. Phys. Chem.B,110 (2006) 18601.   
[42] WANG Y., TEITEL S.and DELLAGO C.,J. Chem. Phys., 122(2005）214722.   
[43] ABER J.E.,ARNOLD S.,GARETZ B.A.and MYERSON A.S.,Phys.Reu.Lett.,94(2005)145503.   
[44] LECHNER W.，DELLAGO C.and BOLHUIS P.G.,Phys. Rev.Lett.,106(2011) 085701.   
[45]ERDEMIRD.,LEEA.Y.and MYERSON A.S.,Acc. Chem. Res.,42 (2009) 621.   
[46] SELLNER B.,VALIEV M.and KATHMANN S.M.,J.Phys. Chem.B,117 (2013)10869.