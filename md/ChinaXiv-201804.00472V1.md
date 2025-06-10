# On the dwarf galaxies rotation curves diversity problem

Antonino Del Popolo $^ { 1 , 2 , 3 }$ Morgan Le Delliou $^ { 4 , 5 }$ Xi-Guo Lee1

（204号 $^ { 1 }$ Institute of Modern Physics,Chinese Academyof Sciences,Post Ofce Box 31,Lanzhou7300,Peoples Republicof China $^ 2$ Dipartimento di Fisica e Astronomia,Universityof Catania, Viale Andrea Doria 6,95125,Catania,Italy 3 INFN sezione di Catania,Via S. Sofia 64, I-95123 Catania, Italy   
$^ 4$ Instituteoficalicrntesitythsdo R China   
5 InstitutodeAstrofisicaeCienciasdoEspaco,UniversidadedeLisboa,Faculdadede Ciencias,Ed.C8,CampoGrande,169-016 Lisboa,Portugal

Abstract:In this paper,we show how baryonic physics can solve the problem of the striking diversity in dwarf galaxies rotation curves shapes.To this aim,we compare the distribution of galaxies of the SPARC sample,in the plane $V _ { \mathrm { 2 k p c ^ { - } } } V _ { \mathrm { l a s t } }$ (being $V _ { \mathrm { 2 k p c } }$ the galaxy rotation velocity at 2 kpc,and $V _ { \mathrm { l a s t } }$ that outermost one） with that of galaxies that we simulated taking account of baryonic effcts.The scatter in the rotation curves in the $V _ { \mathrm { 2 k p c } }$ -Vlast plane,and the trendof the SPARC sample's,andour simulated galaxies',distribution is in good agreement.The solutionof the"diversity”problem lies intheabilityof baryonic process toproducenonself-similar haloes,contrary to DM-onlysimulations.We show also that baryonic efects canreproduce the rotation curves of galaxieslike IC2574 characterized bya slow rising with radius.A solution to the diversity problem can be obtained taking appropriately into account the baryon physics effects.

Key words: cosmology: large structure of Universe,galaxy formation,DM halos

PACS:1-3 PACS(Physics and Astronomy Clasification Scheme, http://www.aip.org/pacs/pacs.html/)

# 1 Introduction

Among the predictions of the ACDM paradigm, agreeing very well with a plethora of observations [1-7] $^ *$ ,appears the forecast that dark matter (DM) haloes have a cuspy density profile,with $\rho \propto r ^ { - 1 }$ , close to the halo center,given by the socalled Navarro-Frenk-White (NFW) profile [10].More recent findings confirm this result,however with a lower slope for the cusp[11]. The rotation curves (RCs)of dwarf,and low brightenessgalaxies (LSB)are usually characterized byamore gentle increase than predicted by the NFW profle.This problem was noticed for the frst time more than two decades ago [12-23].

From a more general point of view,the cusp/core problem is better defined in terms of the excessof DM predicted in the inner parts of the galaxies compared with theobserved inner slope,and itcan beconnected to the Too-BigTo-Fail problem [24-26].

While dwarf galaxies usually have cored profiles,a more detailed study shows a significant spread in their RCs and the existence of cuspy dwarfs.

Despite disagreement on the above discrepancy, the inner profles of several dwarf galaxies or LSBs are clearly not always flat [e.g.27,28],and[29]noticed in the THINGS samplea clear massdependenceof inner profiles.[30] first predicted such mass dependence. Inner slope dependence on the halo mass and on the ratio $( M _ { g a s } + M _ { * } ) / M _ { t o t a l }$ ， where $M _ { * }$ is the stellar mass, was shown in more recent studies [31, 32].

Inaddition,currently,different techniques (e.g.spherical Jeans equation,multiplestellar populations techniques, Schwarzschild modeling)aplied to those or similar objects sometimes give diferent results (e.g.,the cuspy profile found by[33] inFornax,while[34-36],foundacore).Finalydiscrepancies areevidentforlargerobjectsthan those MW satellites (e.g., [37] found $- 0 . 1 7 < \alpha < - 0 . 0 1$ in the case of NGC2976,while [38] found $\alpha = - 0 . 9 0 \pm 0 . 1 5$ ，and [39] found $\alpha = - 0 . 5 3 \pm 0 . 1 4$ if stars were used to trace the potential, or $\alpha { = } - 0 . 3 0 { \pm } 0 . 1 8$ if it was the gas).

From the studies discussed above,and several others,results show the existence of a range of profiles,and that no agreement on the exact dark mater slopes distribution can be reached based on morphologies,despite current improvements in kinematic maps.

Recently, [28] quantifed this diversity in dwarf galaxies RCs. They compared the circular velocity at 2 kpc $V _ { 2 k p c }$ ， given a fixed maximum in the circular velocity, $V _ { m a x }$ . The scatter in $V _ { 2 k p c }$ ,in the $V _ { m a x }$ range $5 0 { - } 2 5 0 \ k m / s$ ， spans a factor 3-4.

Several authors proposed solutions to that problem,almost allrelying on core formation process due to supernovae feedback (hereafter SNM). At this point we want to emphasize that despite the majority of studies converging on the idea that baryon physics leads to the formation ofcores[17,18,31,40-43],some studies arive at theopposite conclusion 44-47].While this disagreementcanbeduetodiferent physical processes included in thesimulations,it motivates one to be more careful in accepting simulationresults.As for the diversity problem,it brings about one question: why wasnt the diversity problem seen and solved bythe large number of hydro-simulations run in the last decade,and especialyin the past years,before[28] pointed itout,if the galaxies they formed were as realistic as claimed? Actually,some years before [28],the problem was discused and solved by means ofbaryon physics,using a semi-analytical model in[17].Thatcore formation model,diferently from the SNM,is related to theexchange of energy and angular momentum between gas clumps and DMthrough dynamical friction (dynamical friction from baryonic clumps model (DFBC))[17, 18, 31, 40, 48-57].

However,after the [28]analysis,several authors claimed the problem could be solved by the same simulations, based onthe SNM,that were previously blind toit.In particular,[58]showed thatsimilar simulations can solve the diversity problem with cores formation bybaryons,while[28]could not.Even in thecase that thecoreformation scenario through supernovae feedback can solve the diversity problem,such scenario encounters serious dificulties to explain the structureof objects like IC2574,which displays acore extending to8kpc,where there is no star (the ICG2574 half-mass radius is 5kpc).Problems like this prompted [59]to explore a solutionbased onself-interacting dark matter (SIDM): they found that the SIDM alone cannot solve the problem and thus somehow some baryonic physics must be introduced.

In this paper, the distribution of galaxies produced by the GCDM in the $V _ { \mathrm { 2 k p c } ^ { - } } V _ { \mathrm { l a s t } }$ ，where $V _ { \mathrm { l a s t } }$ is the outermost radius,willbecompared,following[28],to the SPARC data [60],a collection of high quality RCs ofnearbygalaxies. We expect the massdependenceof theinnerstructureof thegalaxies,asshownin[31,56],to giverisetoascater in the $V _ { 2 k p c } – V _ { \mathrm { l a s t } }$ plane. Such scatter is not possible in the CDM scenario, producing self-similar DM haloes.

In the first Sec.2,the model and observations will be briefly detailed,and their confrontation discussed in Sec.3, before concluding remarks in Sec.4.

# 2 Model and comparison with observations

Our study of the diversity problem involved a subsample of the SPARC sample [60],which is a collection of nearby galaxies high-quality rotation curves, to determine $V _ { 2 k p c }$ ,and $V _ { \mathrm { l a s t } }$ . The subsample characteristics are described in Sec.2.2.

We then simulated 100 galaxies with the DFBC model [40,57],with similar characteristics to our SPARC subsample，and with $M _ { * } = 1 0 ^ { 7 } - 1 0 ^ { 1 1 } M _ { \odot }$ ，in a ACDM cosmology according to the [61] parameters.

Finally,we compared the SPARC subsample and simulated $V _ { 2 k p c }$ ， $V _ { \mathrm { l a s t } }$ ，as summarized in the following.

# 2.1 Model

The model simulating galaxy formation we used has been described in several papers [17,18, 40, 56,57].It provides a highly improved spherical colapse models from that described by [62-67],and includes the effects of dark energy [68-70],random angular momentum [e.g.,65,67] produced by the random motions arising in the collapse phase,ordered angular momentum [e.g.,71-73] arising from tidal torques,adiabatic contraction [e.g.,74-77]， gas and stellar clumps interactions with DM through dynamical friction [40,48-55],gas cooling,star formation, photoionization,supernova,and AGN feedback [78-80, see the following].

It follows perturbations of diffuse gas (baryons)and DM, which wil give rise to the proto-structure, from the linear to non-linear phase,through turn-around and collapse.Baryons fraction is set to the "universal baryon fraction” $f _ { b } = 0 . 1 7 \pm 0 . 0 1$ [81] [0.167 in 2]． The baryons collapse compresses DM (adiabatic compression),steepening the DM profile [74,75,77].

If a DM particle is located at a given radius $r < r _ { i }$

$$
r _ { i } M _ { i } ( r _ { i } ) = r \left[ M _ { b } ( r ) + M _ { d m } ( r ) \right]
$$

[71,74, 82] where $M _ { i } ( r _ { i } )$ is the initial dark halo distribution,then $M _ { b }$ the final mass distribution of baryons (i.e.for example,an exponential disk for spirals,or a Herquist configuration ([83,84] for elliptical galaxies), $r$ the final radius,and $M _ { d m }$ the final DM distribution,are obtained through solving iterativelly Eq.i [85]． This model can be improved to better reproduce numerical simulations by assuming conservation of the product of the radius by the inside mass for that orbit-averaged radius [75].

Radiative processes form baryons clumps, in turn collapsing towards the center of the galaxy and forming stars. Clumps formation, their life-time,and observation are discussed in [57].

Dynamical friction (DF) between baryons and DM transfers energy and angular momentum (AM) to the DM component [48, 49]. This gives rise to a predominantly outwards motion of DM particles, reducing the central density,and transforming the cusp into a core.[40,Appendix D] describes how DF is taken into account,inserting the DF force in the equation of motion [Eq.A14,40] to affects structure formation.

That mechanism,flattening the cusp,is amplified in the case of rotationally supported (spiral) galaxies through the ordered AM, $L$ ,acquired by the proto-structure through tidal interactions with neighbors [71, 86-88],and by random AM, $j$ , originating by the random motions arising in the collapse phase [65].

The “ordered” AM is calculated from evaluating the torque $\tau ( r )$ , and integrating it over time ([71], equation 35; see also Sect. C2 of [40]). “Random” AM is taken into account by assgning a specific angular momentum at turnaround (for details see Appendix C2 of [40]).

A classical cooling flow served as gas cooling mechanism [e.g.,89] [see Sect. 2.2.2 of 79]．The inclusion by[78] and[79,Sect.2.2.2 and 2.2.3]of star formation,reionization and supernovae feedback were replicated. Following [79], reionization reduces the baryon fraction by

$$
f _ { \mathrm { b , h a l o } } ( z , M _ { \mathrm { v i r } } ) = \frac { f _ { \mathrm { b } } } { [ 1 + 0 . 2 6 M _ { \mathrm { F } } ( z ) / M _ { \mathrm { v i r } } ] ^ { 3 } } ,
$$

with the virial mass $M _ { \mathrm { v i r } }$ and $M _ { \mathrm { F } }$ is the "filtering mass” [see 9o].We take the reionization redshift in the range 11.5-15. Our treatment of supernovae feedback also folows [91]. In that stage,each supernova explosion expels gas in successive events,lowering stellar density. The smallest clumps are destroyed by feedback soon after stars are formed from a small part of their mass [55].

AGN quenching becomes important for masses $\simeq 6 \times 1 0 ^ { 1 1 } M _ { \odot }$ [92]．Its feedback was taken into account modifying [93] model as in Sec.2.3 of [80],by forming a Super-Massive-Black-Hole (SMB) when the star density exceedes $2 . 4 \times 1 0 ^ { 6 } M _ { \odot } / k p c ^ { 3 }$ , then accreting mass into it.

Our model demonstrated its robustness in several ways:

a.cusp flattening from DM heating by collapsing baryonic clumps is in agreement with previous studies [48,49,51-55].   
b.galaxies density profiles correct shape [40,94],this before the [41,95] SPH simulations,and correct clusters density profiles [18] were predicted,and a series of correlations in clusters' observations [96, 97] were reobtained [98].   
c. inner slope dependence on halo mass [31],and on the total baryonic content to total mass ratio [18] were predicted,in agreement with [99]. In addition to these dependence,the inner slope was also found to depend on the angular momentum [18].Finally,the correct DM profile inner slope dependence on the halo mass is explained over 6 order of magnitudes in halo mass,from dwarves to clusters [17,18,31, 40, 98],a range that no other model can achieve.

# 2.2 Observational data

The choice we made of galaxies observations was a subsample extracted from the Spitzer Photometry $\&$ Accurate Rotation Curves (SPARC) [60]. Spanning large ranges in morphologies, surface brightnesses,and luminosities,and presenting new surface photometry at ${ \bf 3 . 6 ~ } \mu \mathbf { m }$ and high-quality rotation curves from previous $\mathrm { H I / H } \alpha$ studies,the entire sample contains 175 nearby disk galaxies. To minimizes the scatter in the baryonic Tull-Fisher relation,and following [1o0], we assumed a massto-light ratio $\Upsilon _ { \ast } = 0 . 5 M _ { \odot } / L _ { \odot }$ . To avoid a strong dependence of $V _ { \mathrm { 2 k p c } }$ on the extrapolation method, we excluded from the full sample all galaxies which rotation curves didn't provide pairs of data points bracketting 2 kpc.We also applied to the sample the conditions

![](images/d5e20ad3d98207c928ec0fb862bec63181490e2df106434d42b687a52edd5926.jpg)  
Fig.1. Comparison of the prediction from our model with a selection of SPARC data, using (a)(top panel) the spherical circular velocityapproximation；(b）(bottom panel) the disk plane cylindrical gravitational potential approximation.The full dots represent the SPARC sample,the open violet squares our simulated galaxies,the violet line represents the mean trend line,whilethe dashed line theexpectation if a NFW profile describedall haloes.

a. selecting stellar masses similar to our simulated galaxies,and b.selecting galaxies with inclination $> 4 5 ^ { \mathrm { o } }$ which are the most reliable RC data.

![](images/a45453dc9d18a1ac7dc91e10d0f0c676d517fa7fc621cde0073ab570df6f9278.jpg)  
Fig. 2.Rotation curve of IC2574 compared with our results.The SPARC rotation curve of IC2574 is presented as dots with error bars.Our simulations result yields the grey solid line,including the RCs from its stars (dotted gren line),and gas disk (dashed red line)components,themselves summed into the total baryonic mass(blue solid line).

# 3 Results

Once the observed sample and model simulated galaxies populations were determined, we compared their location in the plane $V _ { \mathrm { 2 k p c } } - V _ { \mathrm { l a s t } }$

In Fig.1,we compared the SPARC data with the result of our model. The models interpretation of circular velocity are based on the 3D spherical circular velocity approximation $\begin{array} { r } { \left( V _ { \mathrm { c i r c - s p h e r i c a l } } = \sqrt { \frac { G M ( < r ) } { r } } \right. } \end{array}$ （2 with $r$ the 3D radius and $M ( < r )$ its enclosed mass） in Fig.la and calculated using the disk plane cylindrical gravitationalpotential $( V _ { \mathrm { c i r c - p o t e n t i a l } } = \sqrt { R _ { \mathrm { \partial } \mathrm { \frac { \partial \Phi } { \partial R } } _ { z = 0 } } ^ { \mathrm { \partial \Phi } } }$ with $R$ the cylindrical radius and $\Phi$ the disk potential,restricted in the galactic plane $z = 0$ ）in Fig.1b.In both panels of Fig.1,the full dots represent the SPARC sample. The open violet squares mark our simulated galaxies,the violet line represents the mean trend line,while the dashed line the expectation if a NFW profile described all haloes.The plot shows the region occupied by our galaxies distributions predicted by our model are in much better agreement with the SPARC galaxy distribution and its scatter than the output of [28]. The maximum spread is observed in the velocity range at $5 0 < V _ { { \mathrm { l a s t } } } < 1 0 0 k m / s < ,$ ，which corresponds, to $M _ { \star }$ values at which the action of feedback is maximum.

Denoting as 惷utliers挤PARC galaxies having $V _ { \mathrm { 2 k p c } }$ outside the $\pm 3 \sigma$ range determined with respect to our model trend line,there are two outliers,namely: IC2574, UCGo5750. The circular-potential velocity definition employed in Fig.1b lowers the trend line,especially in the maximum feedback region，and gives rise to a small increase in scatter. This reintegrates,on one hand, the outliers IC2574, and UGC05750.

The successful reproduction of a similar distribution and scatter to SPARC galaxies by our model reflects the ability to model the total and stellar mass dependence of galaxies DM density profile and RCs,as shown in [56l: galaxies with $M _ { * } \simeq 1 0 ^ { 8 } M _ { \odot }$ are cored with a very flat profile and inner slope $\alpha \simeq 0$ ，while galaxies with $M _ { * } < 1 0 ^ { 8 }$ tend to be more cuspy (larger $\alpha$ ）as the feedback mechanism efficiency，producing the cores,is decreased for lack of baryon clumps. Conversely，galaxies with $M _ { * } > 1 0 ^ { 8 }$ also tend to be cuspier,this time as deeper potential well from the galactic centers larger quantities of stars steepen the cusp and lowers the feedback mechanism effciency. is reached for rotational velocities $< 1 0 k m / s$ ， It is important to notice that our galaxies follow the SPARC trend at $V _ { { \mathrm { l a s t } } } \gtrsim 1 5 0 k m / s$ ,thanks to our accounting of AGN feedback that counteracts baryons cooling,and modifies star formation.In addition,tidal interaction in our model makes it more environment dependent than several hydro-dynamic simulations,in which galaxies are usually isolated.

A recent paper of [101] shows similar results. We want to stress,that the method used in the two papers is totally different:simulations ([1o1])，vs a semi-analytic method (this paper)． The explanation of the "diversity problem” is related to interaction of baryon clumps with dark matter, and not due to Supernovae Feedback. Our results are dependent from environment (galaxies are not isolated),and the effect of AGN feedback,differently from [101]. Those effects change the distribution of galaxies in the $V _ { \mathrm { 2 k p c } } { \cdot } V _ { \mathrm { l a s t } }$ plane. There are also differences in the SPARC sample used. In that of [101] some SPARC galaxies,outliers in their case,were not plotted by the authors.

As previously discussed, IC2574, and UGCo5750 are no more outliers,once calculating $V _ { \mathrm { 2 k p c } }$ in the galactic plane,as seen in the bottom panel of Fig.1. In Fig.2 we showed how our model predictions for the case of IC2574 RC.There,the SPARC RC of IC2574 (dots with error-bars) is compared with our simulation's most similar galaxy RC (solid line).The plot also displays the contribution to the RC coming from stars,as the dotted green line,from the gas disk,the dashed red line,and from the total baryonic mass with the blue line.It shows a good agreement between our calculated RC and the SPARC's. The case of UCG05750 was not plotted since the RC fit using the previous correction gives as good results as for IC2574.

# 4 Conclusions

In this paper, we studied the problem of the diversity of RCs shapes in dwarf galaxies [28].To this aim,we simulated 100 galaxies with similar characteristics to a subsample of the SPARC compilation, and compared the distributions of galaxies of that subsample in the $V _ { \mathrm { 2 k p c } } { \bf - } V _ { \mathrm { l a s t } }$ plane with the simulated galaxies'.The distributions scatter,and trend show good agreement between the SPARC compilation and our galaxies.However,two outliers are present.Determining the circular velocity in the galactic plane,instead of from the spherical symmetrical evaluation,we showed that the two galaxies are no longer outliers.We also showed how the prediction of our model is in agreement with the observations for one of the outliers,namely IC2574. Referenres

1A.DelPopolo,Darkmater,densityperturbations,ndstructureformationAstronomyReports51(Mar.0)169-196, [arXiv:0801.1091]. 2 E.Komatsu,K.M.Smith, J. Dunkley,and et al. Seven-year Wilkinson Microwave Anisotropy Probe (WMAP) Observations:Cosmological Interpretation,ApJS 192 (Feb.,2011) $^ { 1 8 - + }$ ，[arXiv:1001.4538]. 3 A.Del PopoloNon-baryonic dark mater incosmology, inAIP Conf.Proc., vol.1548,pp.2-63,July2013. 4K.T.Story,C.L.Reichardt,Z.Hou,R.Keisler,K.A.Aird,B.A.Benson,L.E.Bleem,J.E.Carlstrom,C.L. Chang,and etal.，A Measurementof the Cosmic Microwave Background Damping Tailfromthe 250-Square-Degree SPT-SZ Suruey,ApJ 779 (Dec.,2013) 86,[arXiv:1210.7231]. 5S.Das,T.Louis,M.R.Nolta,G.E.Addison,E.S.Batisteli,J.R.Bond,E.Calabrese,D.Crichton,M.J. Devlin,S.et al.,J.Dunkley,R.Düinner,J.W.Fowler,M.Gralla,A.Hajian,M.Halpern,M. Hasselfield, M.Hilton,A.D.Hincks,R. Hlozek,K.M.Hufenberger,J.P.Hughes,K.D.Irwin,A.Kosowsky,R.H.Lupton, T. A.Marriage,D. Marsden,F. Menanteau,K. Moodley,M. D. Niemack, L.A.Page, B.Partridge,E.D.Reese, B.L. Schmitt,N.Sehgal,B.D.Sherwin,J.L.Sievers,D.N.Spergel,S.T.Staggs,D.S.Swetz, E.R.Switzer, R.Thornton,H.Trac,andE.Wollack,TheAtacama Cosmology Telescope:temperatureand gravitational lensing power spectrum measurements from three seasons of data, JCAP 4 (Apr.,2014) 014,[arXiv:1301.1037]. 6A.Del Popolo,Nonbaryonic Dark Mater in Cosmology,International Journal of Modern PhysicsD23 (Jan.,2014) 30005,[arXiv:1305.0456]. 7 Planck Collaboration XII, Planck 2015 results. XII. Cosmological parameters,A& A 594 (Sept., 2016) A13, [arXiv:1502.01589].   
8 S.Weinberg, The cosmological constant problem,Reviews of Modern Physics 61 (Jan.,1989)1-23.   
9 A. V. Astashenok and A. del Popolo, Cosmological measure with volume averaging and the vacuum energy problem, Classical and Quantum Gravity 29 (Apr., 2012) 085014, [arXiv:1203.2290].   
10J.F.Navarro,C.S.Frenk,andS.D.M.White,The StructureofCold Dark Mater Halos,ApJ462(May1996)563, [astro-ph/9508025].   
11 J.F.Navarro,A.Ludlow,V.Springel,J.Wang,M.Vogelsberger,S.D.M.White,A.Jenkins,C.S.Frenk,and A.Helmi,The diversity and similarity of simulated cold dark mater haloes,MNRAS 402 (Feb., 2010) 21-34, [arXiv:0810.1522].   
12 B.Moore,Evidenceagainst disspation-lessdark materfromobseruations ofgalaryhaloes,Nature 37o(Aug.,1994) 629-631.   
13R.A.Flores and J.R.Primack,Obseruational and theoreticalconstraints onsingulardark mater halos,ApJL 427 (May 1994) L1-L4,[astro-ph/9402004].   
14 V.F.Cardone,M.P.Leubner,andA.DelPopolo,Spherical galaxymodels asequilibriumconfigurations in non-ertensive statistics,MNRAS 414 (July,2011) 2265-2274,[arXiv:1102.3319].   
15V.F.Cardone,A.DelPopolo,C.Tortora,and N.R.Napolitano,Secondary infallmodel and dark mater scaling relations in intermediate-redshift early-type galaxies, MNRAS 416 (Sept.,2011) 1822-1835,[arXiv:1106.0364].   
16V.F.Cardone and A. Del Popolo, Newtonian acceleration scales in spiral galaries, MNRAS 427 (Dec., 2012) 3176-3187,[arXiv:1209.1524]. [arXiv:1105.0090].   
18A.DelPopolo,Onthedensity-profile slopeofclustersofgalaries,MNRAS424 (July,2012)38-51,[arxiv:1204.4439].   
19A.DelPopoloand V.F.Cardone,Statistical propertiesofthedark matterhaloesofduarfgalariesandcorelationswiththe environment, MNRAS 423 (June, 2012) 1060-1072, [arXiv:1203.3377].   
20A.Del Popolo,V.F.Cardone,andG.Belvedere,Surface densityofdark mater haloes on galacticand clusterscales, MNRAS 429 (Feb., 2013) 1080-1087, [arXiv:1212.6797].   
21 A.Del Popolo and N. Hiotelis, Cusps and cores in the presence of galactic bulges, JCAP1 (Jan., 2014) 47, [arXiv:1401.6577].   
22A.Del Popolo,J.A.S.Lima,J. C.Fabris,andD.C.Rodrigues,A unified solutionto thesmallscale problems ofthe ΛCDM model, JCAP 4(Apr.,2014) 21,[arXiv:1404.3674].   
23A.DelPopoloand M.Le Delliou,A unified solution to the smallscale problemsoftheACDM model II:introducing parent-satellite interaction, JCAP12 (Dec., 2014) 51,[arXiv:1408.4893].   
24M. Boylan-Kolchin,J.S. Bullck,and M. Kaplinghat,Toobig tofail? The puzing darknessof massiue Milky Way subhaloes, MNRAS 415 (July, 2011) L40-L44, [arXiv:1103.0007].   
25E.Papastergis,R.Giovanelli,M.P.Haynes,andF.hankar,Is therea"toobigtofail"probleminthefeld,AA 574(Feb.,2015) A113,[arXiv:1407.4665].   
26A.Del Popoloand M.Le Delliou,Smal Scale Problemsof the CDM Model: A Short Review, Galaxies 5 (Feb., 2017) 17,[arXiv:1606.07790].   
27J. D.Simon,A. D.BolattoA.Leroy,L.Blitz,and E.L. Gates, Hgh-Resolution Measurementsof the Halosof Four Dark Mater-Dominated Galaries: Deviations from a Universal Density Profile,ApJ 621 (Mar.,2005) 757-776, [astro-ph/0412035].   
28K.A. Oman, J.F. Navarro,A. Fatahi, C.S.Frenk,T.Sawala, S.D.M. White,R.Bower,R.A.Crain, M.Furlong,M.Schaler,J.Schaye,and T.Theuns,The unerpected diversityof dwarf galaryrotation curues,MNRAS 452(Oct., 2015) 3650-3665,[arXiv:1504.01437].   
29W.J. G.de Blok,F.Walter,E. Brinks,C.Trachternach,S.-H. Oh,andR. C.Kennicutt,Jr.,High-Resolution Rotation Curues and Galaxy Mass Models from THINGS,AJ136 (Dec.,2008) 2648-2719,[arXiv:0810.2100].   
30M. Ricotti, Dependence of the inner dark mater profile on the halo mass, MNRAS 344 (Oct.,2003)1237-1249, [astro-ph/0212146].   
31A.Del Popolo,On the universality of density profiles,MNRAS 408 (Nov.,2010) 1808-1817,[arxiv:1012.4322].   
32A.DelPopolo,Non-powerlawbehaviorof teradial profileofphase-space densityofhalos,JCAP7(July,2011)14, [arXiv:1112.4185].   
33M.A.Breddels,A.Helmi,R.C.E.van den Bosch,G.van deVen,andG.Battaglia, Orbit-based dynamical models of the Sculptor dSph galaxy,MNRAS 433 (Aug., 2013) 3173-3189,[arXiv:1205.4712].   
34M.G.Walker and J.Penarrubia,A Methodfor Measuring (Slopesof)the MassProfilesofDuarf Spheroidal Galaries,ApJ 742(Nov.,2011) 20,[arXiv:1108.2404].   
35G.Battaglia,A.Helmi,E.olstoy,M.Irwin,V.HillandP.Jablonka,The Kinematic Statusand MassContentofthe Sculptor Dwarf Spheroidal Galaxy, ApJL 681 (July, 2008) L13-L16,[arXiv:0802.4220].   
36A.Agnelo and N. W.Evans,A Virial Core in the Sculptor Duarf Sheroidal Galary,ApJL754 (Aug.,2012) L39, [arXiv:1205.6673].   
37J.D.Simon,A.D.Bolato,A.LeroyandL.Blitz,High-Resolution easurementsof theDark Matter Haloof NGC2976: Evidence for a Shallow Density Profile, ApJ 596 (Oct., 2003) 957-981,[astro-ph/0307154].   
38J.J.Adams,K.Gebhardt,G.A.Blanc,M.H.Fabricius,G.J.Hil,J.D.Murphy,R.C.E.van den Bosch,and G. van de Ven,The Central Dark Mater Distributionof NGC 2976,ApJ745 (Jan.,2012) 92,[arXiv:110.5951].   
39J. J. Adams,J.D.Simon,M. H.Fabricius,R. C.E.van den Bosch,J.C.Barentine,R.Bender,K.Gebhardt, G. J. Hill,J.D. Murphy,R.A.Swaters,J.Thomas,and G.vande Ven,Dwarf Galaxy Dark Matter Density Profiles Inferred from Stellar and Gas Kinematics, ApJ 789 (July, 2014) 63, [arXiv:1405.4854].   
40 A.Del Popolo,The Cusp/Core Problem and the Secondary Infall Model, ApJ 698 (June,2009) 2093-2113, [arXiv:0906.4447].   
41 F. Governato, C.Brook,L. Mayer,A.Brooks, G.Rhee,J.Wadsley,P. Jonsson,B. Willman, G.Stinson, T.Quinn,and P.Madau,Bulgeless darf galaxies anddark matercoresfromsuperoa-driven outflows,Nature 463(Jan, 2010）203-206,[arXiv:0911.2237].   
42J. Onorbe, M. Boylan-Kolchin, J.S.Bullock,P.F. Hopkins, D. Keres, C.-A.Faucher-Giguere,E. Quataert,and N. Murray,Forged in FIRE: cusps,cores,and baryons in low-mass duarf galaries,ArXiv e-prints (Feb., 2015) [arXiv:1502.02036].   
43 J.I. Read,O. Agertz, and M. L. M. Collins, Dark mater cores allthe way down, MNRAS 459 (July, 2016) 2573-2590,[arXiv:1508.04143].   
44M.Vogelsberger,J. Zavala, C.Smpson,andA.Jenkins,Duarfgalaries inCDMand S with baryons:oserational probes of the nature of dark matter,MNRAS 444 (Nov., 2014) 3684-3698,[arXiv:1405.5216].   
45A.Gonzalez-Samaniego,P.Colin,V.Avila-Reese,A.Rodriguez-Puebla,andO.Valenzuela,SimulationsofIsolated Dwarf Galaxies Formed in Dark Matter Halos with Diferent Mass Assembly Histories, ApJ 785 (Apr., 2014) 58, [arXiv:1308.4753].   
46T. Sawala, C.S. Frenk,A.Fattahi, J.F.Navarro,R. G. Bower,R. A. Crain,C. Dalla Vecchia, M.Furlong, A.Jenkins,I. G.McCarthy,Y.Qu,M.Schaller,J.Schaye,and T.Theuns, Bentby baryons:the low-mas galary-halo relation,MNRAS 448(Apr.,2015) 2941-2947, [arXiv:1404.3724].   
47M.Schaller,C.S.Frenk,R. G.Bower,T.Theuns,A. Jenkins,J.Schaye,R.A. Crain, M. Furlong, C. Dalla Vecchia,andI.G.McCarthy,Baryon efectsonthe internal structureofACDMhaloes in the EAGLEsimulations,MNRAS 451 (Aug., 2015) 1247-1267, [arXiv:1409.8617].   
48A.El-Zant,1.Shlosman,andY.Hoffman,Dark Halos:TheFlateningof theDensity CuspbyDynamical FrictionApJ 560(Oct.,2001) 636-643,[astro-ph/0103386].   
49 A.A.El-Zant, Y.Hoffman,J.Primack,F.Combes,and I. Shlosman,Flat-cored Dark Mater in Cuspy Clusters of Galaxies,ApJL 607 (June,2004) L75-L78,[astro-ph/0309412].   
50 C.-P.Ma andM.Boylan-Kolchin,Are Hlos ofCollisionles ColdDrk Matter Collsionless，PysicalReviewLeters93 (July,2004) 021301,[astro-ph/0403102].   
51E.Romano-Diaz,1.hlosman,Y.Hoffman,andC.Heler,Erasing Dark Matter Cusps inCosmological GalacticHalos with Baryons,ApJL 685 (Oct.,2008) L105-L108, [arXiv:0808.0195].   
52E.RomanDiaz,I.osman, C.Hellrand Y.Hoffman, Dsecting Galay ormation.I.Comprison BetweenPure Dark Matter and Baryonic Models,ApJ 702 (Sept., 2009) 1250-1267,[arXiv:0901.1317].   
53D. R. Cole,W. Dehnennd M.1. Wikinson,Weakening dark matercusps bycumpybryonic infall，A416 (Sept., 2011) 1118-1134,[arXiv:1105.4050].   
54S.Ioueand T.R.Saitoh,Coresandrevivedcuspsofdark materhaloes indiscgalacy formation through clumpclusters, MNRAS 418 (Dec., 2011) 2527-2531,[arXiv:1108.0906].   
55C.Nipoti and J.BinneyEarly flatening of dark mater cusps induarf spheroidal galaxies,MNRAS 446 (Jan.,2015) 1820-1828,[arXiv:1410.6169].   
56A.DelPopoloandF.Pace,The Cusp/Core problem: supernouae fedback versusthe baryonicclumpsanddynamicalfriction model,Ap&SS 361 (May,2016) 162,[arXiv:1502.01947].   
57A.Del Popolo,On the dark mater haloes inner structure and galaxy morphology, Ap&Ss 361 (July,2016) 222, [arXiv:1607.07408].   
58J.I.Read,G.Irio,O.Agertz,andF.Fraternali, Understandingtheshape anddiversityofduarfgalaryrotationcruein ACDM, MNRAS 462 (Nov., 2016) 3628-3645, [arXiv:1601.05821].   
59P.Creasey,O.Sameie,L. V.Saes,H.-B.Yu,M. VgelsbergerndJ. ZavalaSpreading out and stayingsarp creating diverse rotation curves via baryonic and self-interaction efects,MNRAS 468 (June,20i7) 2283-2295, [arXiv:1612.03903].   
60F.Lelli,S.S.McGaugh,and J.M.Schombert,Sparc: Mass models for175 disk galaries with spitzer photometry and accurate rotation curves, The Astronomical Journal 152 (2o16),no.6 157.   
61 Planck Collaboration, P.A.R. Ade,N. Aghanim, C.Armitage-Caplan, M. Arnaud, M. Ashdown, F.Atrio-Barandela, J.Aumont,C. Baccigalupi,A. J. Banday,and et al.,Planck 2013 results. XVI. Cosmological parameters,A& A 571 (Nov.,2014) A16,[arXiv:1303.5076].   
62J.E.GunnandJ.R.Gott,I,OntheInfallofMaterItoClustersofGalariesandSomeEfectsonTheirEolution,ApJ 176 （Aug.,1972） 1.   
63 E.Bertschinger,Self-similarsecondaryinfallandaretion innEstein-deSiternerse,ApS58(May985)39-65.   
64Y.HoffmanandJ.Shaham,Local density marima- Progenitors of structure,ApJ297 (Oct.,1985) 16-22.   
65B. S. Ryden and J. E. Gunn, Galaxy formation by gravitational collpse, ApJ318 (July,1987) 15-31.   
66Y. AscasibarG.Yepes,S.Gotlornd V.ullerOnthehsicalrginofdrk maerdesityprles,AS352 (Aug., 2004) 1109-1120, [astr0-ph/0].   
67L.L.R.Williams,A.Babul,andJ.J.Dalcanton,Inuestigating theOrginsof Dark Mater HaloDensityProfles,ApJ 604 (Mar., 2004) 18-39,[astro-ph/0312002].   
68A.DelPopolo,F.Pace,andJ.A.S.Lima,EtendedSphericalCollpseandtheAcceleratingUverse,Intertioal Journal of Modern Physics D 22 (July, 2013) 50038,[arXiv:1207.5789].   
69A.Del Popolo,F.Pace,and J.A.S.Lima,Sphericalcollpsemodel withshear and angularmomentum indark eergy cosmologies, MNRAS 430 (Mar., 2013) 628-637, [arXiv:1212.5092].   
70A.Del Popolo,F.Pace,S.P.Maydanyuk,J.A.S.Lima,and J.F.Jesus, Shearandrotation inChaplygin cosmology, Phys.Rev.D87 (Feb.,2013) 043527,[arXiv:1303.3628].   
71B.S.RydenGalaxy formation- Theroleof tidal torques anddisiptional infall，ApJ329 (June,1988)589-611.   
72A.DelPoolondM.Gambera,Substructureeffctsontheolapseofdesityperturbatios.,A& A321 (ay1997) 691-695,[astro-ph/9610052].   
73A.DelPopoloand M.Gambera,Nonradial motions and the shapes and the abundance ofclusters of galaries,A A 357 (May,2000) 809-815,[astro-ph/9909156].   
74G.R.Blumenthal,S.M.Faber,R.Flores,andJ.R.Primack,Contractionofdark mater galactichalos duetobaryonic infall,ApJ 301 (Feb.,1986) 27-34.   
75O.Y.Gnedin,A.V.Kravtsov,A.A.Klypin,and D.Nagai,Responseof Dark Mater Halos to ondensationofBaryons: Cosmological imulationsand Improved Adiabatic Contraction Model,ApJ616 (Nov.,2004)16-26,[astro-ph/0406247].   
76A.Klypin,H.Zhao,andR.S.Somerville,ACDM-based Models for the Milky Way and M31. 1. Dynamical Models，ApJ 573(July,2002) 597-613,[astro-ph/0110390].   
77M. Gustafsson, M.Fairbairn,and J.Sommer-Larsen, Baryonic pinchingof galactic dark mater halos, Phys. Rev. D74 (Dec.,2006) 123522,[astro-ph/0608634].   
78G.DeLuciaandA.Helmi,TheGalaxyanditsstelarhalo:insightsontheirformationfromahybridcosmologicalapproach， MNRAS 391 (Nov., 2008)14-31,[arXiv:0804.2465].   
79 Y.-S. Li,G.De Lucia,and A. Helmi,On the natureof the Milky Waysatelites,MNRAS401 (Jan.,2010)2036-2052, [arXiv:0909.1291].   
80 D.Martizzi,R.Teyssier,B.Moore,and T.WentzTheeffctsofbryonphsics,black holesand active galactic nucles fedback on the mass distrbution in clusters of galaxies,MNRAS 422 (June,20i2) 3081-3091,[arXiv:112.2752].   
81E.Komatsu,J.Dunkley,M.R.Nolta,and etal.,Five-Year Wilkinson Microwave AnisotropyProbeObseratios: Cosmological Interpretation, ApJS 180 (Feb., 2009) 330-376, [arXiv:0803.0547].   
82R.Flores,J.R.Primack,G.R.Bumenthal,and S.M.Faber，Rotation curuesfrom baryonicinfall- Dependenceon disk-to-halo ratio,nitial angularmomentum,andcoreradius,andcomparison with data,ApJ412 (Aug.1993) 443-454.   
83C.R.Keton,Cold Dark Matterand StrongGravitational Lensing:Concordor Conflict?,ApJ561(Nov.,201)46-60, [astro-ph/0105200].   
84 T.Treuand L.V.E.Koopmans,The Internal Structureand Formation of Early-Type Galaxies: The Gravitational Lens System MG 2016+112 at $z = 1 . 0 0 4$ ，ApJ 575(Aug.,2002)87-94,[astro-ph/0202342].   
85E.Spedicato,E.Bodon,A.Del Popolo,and N.Mahdavi-Amiri,ABS Methods and ABSPACK forLinear Systems and Optimization,a Review,4OR (2003) [astro-ph/0209241].   
86P.J. E. Peebles, Origin of the Angular Momentum of Galaxies, ApJ 155 (Feb.,1969) 393.   
87 S. D. M. White, Angular momentum growth in protogalaxies, ApJ 286 (Nov., 1984) 38-41.   
88D.J.EisensteinandA.Loeb,Ananalyticalmodelforthetriaxialcolapseofcosmologicalperturbations,ApJ439 (Fe,   
1995）520-541,[astro-ph/9].   
89S.D.M.White and C.S.Frenk,Galaxy formation through hierarchical clustering,ApJ379 (Sept.,1991) 52-79.   
90A.V.Kravtsov,O.Y.Gnedin,andA.A.Klypin,The Tumultuous LivesofGalactic Dwarfs and the Mising Satellites Problem,ApJ609 (July,2004) 482-497,[astro-ph/0401088].   
91 D.J. Croton, V. Springel, S.D.M. White,G.De Lucia, C.S.Frenk,L. Gao,A. Jenkins, G. Kauffmann, J.F. Navarro,andN.Yoshida,The manylivesofactive galactic nuclei:coling flows,black holesandthelumnositiesandcolours of galaxies,MNRAS 365 (Jan.,2006) 11-28,[astro-ph/0508046].   
92 A.Cattaneo,A.Dekel,J.evriendt,B.GuderdonindJ.Blazot,Modeling thegalaxybimodality:shutdoboe critical halo mass, MNRAS 370 (Aug., 2006) 1651-1665, [astro-ph/0601295].   
93C.M.Boothand J.Schaye,Cosmological simulationsof thegrowthof supermasiveblack holesand fedback fromactive galactic nuclei: method and tests,Monthly Notices of the Royal Astronomical Society 398 (209),no.1 53-74.   
94A.Del Popolo and P. Kroupa, Density profiles of dark mater haloes on galacticand cluster scales, A A 502 (Aug.,   
2009)733-747，[arXiv:0906.1146].   
95 F.Governato,A. Zolotov,A.Pontzen, C.Christensen,S.H. Oh,A.M.Brooks,T. Quinn,S. Shen,and J.Wadsley，Cuspy no more:howoutflous afectthecentraldarkmaterandbaryondistributioninAcolddark matergalaxies, MNRAS 422 (May, 2012)1231-1240,[arXiv:1202.0554].   
96A.B.Newman,T.Treu,R.S.Elis,D.J.Sand,C.Nipoti,J.Richard,andE.Jull,TheDensityProflesofassive Relaxed Galaxy Clusters.I.The TotalDensity Ouer Three Decadesin Radius,ApJ765 (Mar.2013)24,[arXiv:1209.391].   
97A.B.Newman,T.Treu,R.S.Elis,andD.J.Sand,The DensityProflesofMassiue,Relaxed Galaxy Clusters.I. Separating Luminous and Dark Mater in Cluster Cores,ApJ 765 (Mar.,2013) 25,[arXiv:1209.1392].   
98A.DelPopolo,Theflatdensityprofilesofmaive,ndrelaedgalarylusters,JCAP7(July14)19,arxiv44347.   
99A.Di Cintio,C.B.Brook,A. V.Maccio,G.S.Stinson,A.Knebe,A.A.Dutton,and J.Wadsley，The dependence of dark mattr profiles onthe stelar-to-alo massratio:a prediction for cusps versus cores,MNRAS 437 (Jan.,2014)   
415-423,[arXiv:1306.0898].   
100 F.Lell,S.S.McGaugh,andJ.M.Schombert,The SmallScatte of the Baryonic Tull-Fisher Relation,ApJL816 (Jan.,2016)L14,[arXiv:1512.04543].   
101 I. M.Santos-Santos,A. Di Cintio,C.B. Brook,A. Maccio,A. Dutton,and R. Dominguez-Tenreiro,NIHAO XIV: Reproducing the observed diversity of duarf galary rotation curue shapes in LCDM,ArXiv e-prints (June, 2017) [arXiv:1706.04202]. We thank ...