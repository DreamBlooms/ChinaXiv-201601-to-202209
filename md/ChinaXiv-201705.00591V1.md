# Thickness dependence of properties and structure of ultrathin tetrahedral amorphous carbon films: A molecular dynamics simulation

Xiaowei Li a, Shipeng Xu a,b, Peiling Ke a, Aiying Wang a,\*

Engineering,CineseAcademyofciences,Ningbo315201,Pina bCollegeofsicsdaterialsiecenjinmalUivesityianjin87n

Keywords:   
Ultrathin tetrahedral amorphous carbon   
Thickness   
Compressive stress   
Molecular dynamics simulation

# ABSTRACT

Molecular dynamics simulation was performed to investigate the efectof thickness on the properties and structureof ultrathin tetrahedralamorphous carbon films (ta-C).The present simulation showed thatboththe density and residual compressive stress decreased with increasing the thicknessof ultrathin ta-C films,which was in agreement with the experimental results.The gradient of properties with the thickness was dependent on the incident kinetic energy of deposited atoms;when the incident kinetic energy was 10 eV/atom,the slower gradient was observed.Further structural analysis indicated thatthe criticalrelaxationof highly distorted bond angles was responsible for the reduction of residual compressive stress in the films deposited at $1 0 \ \mathrm { e V } .$ /atom, whilethe jointrelaxationofboththe distortedbondanglesand C-Cbond length ledto the fastreleaseofresidual compressive stress in the films deposited at70 eV/atom.

# 1. Introduction

Owning to the excellent properties such as high hardness,low coefficient of friction,wear-resistance,extremely smoothness and chemical inertness,diamond-like carbon (DLC) films have been used as protective coatings on the disks and read-write heads of magnetic disk storage devices to minimize the mechanical wear and corrosion [1-3].Recently,the storage density of hard disk drivesis increasingat a very rapid rate.In order to meet the requirement for the high storage density,the magnetic spacing which is the vertical distance between the read head and magnetic storage layer,must be reduced. One effective way to reduce the magnetic spacing is to decrease the thickness of protective films [4,5].So a protective layer with several nanometers is required to satisfy the demand of storage density increasing. Generally, ultrathin tetrahedral amorphous carbon (ta-C) films with unique combination of desirable mechanical properties and tribological lubricity are studied [5-7].For example,Casiraghi etal. prepared ta-C films by filtered cathodic vacuum arc technology and showed that the film with the thickness of $2 \ : \mathrm { n m }$ Was pin-hole free and had a Young's modulus of ${ \sim } 1 0 0 \mathrm { G P a }$ an $ { s p } ^ { 3 }$ content of $\sim 5 0 \%$ and a roughness of ${ \sim } 0 . 1 2$ [5]. Beghi etal.also found thatultrathin $2 \mathrm { - n m }$ -thickcarbon-basedfilmsretained a Young's modulus of about 1Oo GPa [6].

However, the narrow range of applications of ultrathin ta-C films, mainly in the fields of magnetic recording media,restricts the wide,indepth studies on ultrathin ta-C films.In addition,it is known that the structure and properties of DLC films strongly depend on the thickness of films [8-1O].Especially forultrathin ta-C films,the decrease of thickness leads to the complexity in experimental characterization and the strong relationship between the structure and properties [11].Thus,in order to understand the evolution of structural properties with the thickness and provide guidelines for the preparation of the ultrathin ta-C films used in magnetic storage devices,a further insight into the ultrathin ta-C films from the viewpoint of atomic scale is required.Molecular dynamics simulation (MD) technique provides a robust method for the fundamental understanding of the atomic bond structure and properties of DLC films in atomic scale.By MD simulation,previous studies have investigated the variations of structure and properties with the kinetic energy of deposited carbonatoms[12], the energy of the carrier gas ions suchas $\mathrm { A r ^ { + } }$ [13] or growth species [14]. But the thickness dependence of the properties and structure of the ultrathin ta-C films is still not fully understood yet.

In the present work,we deposited the ultrathin ta-C films with the thickness of $2 \mathrm { - } 6 \mathrm { n m }$ by a classical MD to investigate the effect of thickness on properties and structure.The dependence of residual stress and density on thickness of films was studied,and the structural evolutions including bond angles and bond lengths were mainlyanalyzed.Structuralanalysis revealed thatwith the increase of thickness of ultrathin ta-C films,the distorted atomic bond structure was relaxed,which accounted for the reduction of residual stress.However,the incident energy of deposited carbonatoms also played a key role on the change of structural properties with the thickness of ultrathin ta-C films.

# 2. Computational methods

Classical MD simulation Was used to study the deposition process of ultrathin ta-C films with different thickness using the three-body empirical potential Tersoff [15].Previous results have revealed the limitation of Tersoff potential where the π bonding is not adequately considered [16-18],and also developed Brenner[19,2O],the 2nd generation reactive empirical bond order(REBO) potential [21] and the adaptive intermolecular reactive empirical bond order（AIREBO） potential [22] to simulate amorphous carbon growth,but Tersoff is still proved to be an effective and accurate potential for carbon-based systems.

A diamond(Oo1） single crystal was served as substrate with the dimensions of $2 5 . 2 2 1 0 \times 2 5 . 2 2 1 0 \times 2 4 . 0 7 5 8 \mathrm { ~ \AA ~ } ^ { 3 }$ in the $x , y$ and $z$ directions,which consisted of 28 atomic layers with 1O0 carbon atoms per layerand was equilibrated at $3 0 0 \mathrm { K }$ for 100 ps before deposition. The incident carbon atoms were introduced at the position of $1 0 \mathrm { n m }$ above the substrate surface at a random $\{ \mathbf { x } , \mathbf { y } \}$ position. The positions of atoms in the bottom two monolayers were frozen to mimic the bulk substrate, while all the other atoms were unconstrained.The deposition was simulated using NVE ensemble implemented in the large-scale atomic/ molecular massively parallel simulator(LAMMPS) code[23].Periodic boundary conditions were applied along the lateral xy dimensions.

The kinetic energy of incident carbon atoms was fixed at 7O eV/atom, because it was the optimum energy fora highly stressed and dense ta-C film deposition [24]. For comparison,the kinetic energy of 10 eV/atom wasalso considered.The thickness variations of ultrathin ta-C films were achieved by changing the deposition time.The time step of 1 fs was used.The time interval between two sequential deposited carbon atoms was 1O ps.The previous report has indicated that the time interval of 1O ps was enough for relaxing the atomic structure and diminishing the unrealistic effect of high carbon flux on the deposition process [24].However,a number of processes such as diffusion or rearrangement processes that occurred on much longer time scales were neglected in the simulation due to the required computation time.The substrate temperature was rescaled to $3 0 0 \mathrm { K }$ by the Berendsen method [25]after the atomic rearrangement caused by the bombardment of incident atoms was finished,and the heat bath coupling constant was 10 fs in the simulations.

# 3.Results and discussion

The final configurations of the deposited films as a function of the thickness are summarized in Fig.1,in which the red numbers correspond to the thickness of films calculated by subtracting the original thickness of substrate from the total thickness of systems after deposition.It shows that a typical amorphous filmis generated for each case,which will be described later by the radial distribution functions (RDF).As the deposition time increases from 2O to 5O ns,the thickness of films depositedat10 eV/atom varies from 23.19 to 57.97 A (Fig.1a),while the case at $7 0 \mathrm { e V } ,$ /atom increases from 24.08 to $5 7 . 9 7 \mathring { \mathrm { A } }$ (Fig.1b). It is deduced that changing the incident kinetic energy has little effect on the deposition rate of ultrathin ta-C films;Fig.1also shows that the surface roughness is independent on the thickness.In addition, it should be noted that when the incident kinetic energy is 7O eV/atom, the incident atoms can easily implant into the diamond lattice,resulting in an obvious intermixing layer between the flm and substrate (Fig.1b).

![](images/896813dd0bace9f21cb1f0b4954d3a828b72f7feccbdee4b4c3e650c557dc772.jpg)  
Fig.2.RDF of the deposited films with the different thickness when the incident kinetic energyis (a)10 eV/atom or (b) $7 0 \mathrm { e V } ,$ atom,respectively.

The RDF, $\mathrm { g ( r ) }$ ,is proportional to the density of atoms at a distance $r$ from another atom,which is a very important parameter for structural characterization of amorphous materials,and it is computed by the formula

$$
\begin{array} { r } { \displaystyle { \mathsf { g } ( \boldsymbol { r } ) = \frac { \mathrm { d } N } { \rho \cdot 4 \pi r ^ { 2 } \mathrm { d } r } } } \end{array}
$$

where $\rho$ is the average density of system, $\mathrm { d } N$ is the number of atoms from $r$ to $r + \mathrm { d } r$ Fig.2 shows the RDF for all ultrathin ta-C films,in which the red dotted lines represent the positions of the 1st nearest neighbor $( 1 . 5 4 \mathrm { \AA } )$ and 2nd nearest neighbor $( 2 . 5 2 \textup { \AA } )$ of crystalline diamond,respectively.For all films with the different thickness,the a (b) 4.5 1.5 4.5 1.5 4035 Transitionegion Sstable regionp-% Surtace region 1.2 4035 Transitonengih stableregon sp% Srtace region 1.2 3.0 WWWW WwWN 0.9 Hiaerriieliiiig (2u0/6) 3.0 2.5 A ge eg 2.0substrie 0.6 1.0 0.3 1.0 0.5 0.5 KXKXKKXKKXXXXKKKXXXXXXKKKXXXXXXXXXXXKXX 0.0 0.0 0.0 0.0 -10 0 10 20 30 40 50 -10 0 10 20 30 40 50 Thickness (A) Thickness (A)

![](images/fc07f4299146536c011fe066b6a482fcdb35fe2f580937fb908f20c01cf96bed.jpg)  
Fig.1.Crosstiolsapsotofthdepiedfsiththdintticessteidentieticenis(a)Vatoob) $7 0 \mathrm { e V } ,$ /atom,respectively.Thered numberson tp and the red dotted line means the position of substrate surface.

typical amorphous character is observed, that is long-range disorder and short-range order.Increasing the thickness of ultrathin films makes no obvious effect on the positions of the 1st and 2nd peaks which are located at approximately $1 . 4 8 \mathring { \mathrm { A } }$ and $2 . 5 3 \mathring { \mathrm { A } }$ respectively.

Fig.3 shows the variations of density and hybridization ratio $( s p ^ { 3 } \%$ $s p ^ { 2 \% }$ 0 $s p \%$ )along the growth direction offilms deposited at10 eV/atom and 70 eV/atom.Similar to previous study [24],the whole system is also divided into four regions including substrate,transition region,stable region and surface region. It can be noted that the $ { s p } ^ { 3 }$ fraction in all films appears low values,which might attribute to the limit of Tersoff potential where the π bonding was not adequately considered. Because the densityand hybridization ratio exhibit relative constant values in the stable region,the representative properties (densityand compressive stress)as a function of the thickness of ultrathin ta-C films are quantified using this region,as illustrated in Fig.4.The residual stress, is computed by the formula

$$
\sigma = \frac { P _ { \mathrm { x x } } + P _ { \mathrm { y y } } + P _ { \mathrm { z z } } } { d V }
$$

where $d$ is the dimensionality of the system(2 or 3 for $2 d / 3 d$ ) $V$ is the system volume (or area in $2 d$ );and $P _ { \mathrm { x x } } , P _ { \mathrm { y y } }$ and $P _ { z z }$ are the diagonal components of the stress tensor.It shows that both the density and residual compressive stress decrease with increasing the film thickness whateverthe kinetic energy of incident carbonatoms.Notably,for the ultrathin ta-C films deposited at 7O eV/atom,the density and compressive stress with the thickness decrease linearly;as the thickness increases from 24.08 to $5 7 . 9 7 \mathring { \mathrm { A } } ,$ the compressive stress drops about $6 3 . 2 \%$ ,while the density is only reduced by $8 . 5 \%$ However,at the incident kinetic energy of $1 0 \ \mathrm { e V } / \$ atom,the densityis linearlyreduced from2.83 to $2 . 6 3 \mathrm { g } / \mathrm { c m } ^ { 3 } \mathrm { a } \mathrm { s }$ the thickness varies from 23.19 to $5 7 . 9 7 \mathring { \mathrm { A } }$ ,but the gradient is slower than that of the films deposited at $7 0 \mathrm { e V } ,$ /atom; the compressive stress decreases from 5.47 to 1.79 GPa and the gradient with the thickness increases gradually.

For comparison and validation with the simulation,the experiments were also carried out by preparing the ultrathin ta-C films with diferent thickness using a home-made $4 5 ^ { \circ }$ double-bent filtered cathodic vacuum arc(FCVA) technique.P-type silicon(1oO)wafers were used as substrates.Graphite with purity of $9 9 . 9 9 9 \%$ was used as the cathodic target. During deposition,the filmswere deposited ata bias voltage of $- 8 0 \mathrm { V }$ and the arc current was fixed at $6 0 \mathrm { A } .$ The deposition time was changed from 4 to $2 0 \mathrm { m i n }$ .The experimental results of ultrathin ta-C films with the thickness ranging from 7.6 to $2 4 \mathrm { n m }$ are shown in Fig.5.It reveals that following the thickness of ultrathin ta-C films the compressive stress also decreases significantly with a little deterioration of density. This is consistent with the simulation results.

In order to elucidate the evolution of properties with the thickness of ultrathin ta-C films,the atomic bond structure needs to be further analyzed.The distributions of both the bond angles and bond lengths for all ultrathin ta-C films are plotted to gain the fractions of distorted bond anglesand bond lengths,as shown in Fig.6.Itis known that the stable bond angle and bond length of graphite are $1 2 0 ^ { \circ }$ and $1 . 4 2 \mathring { \mathrm { A } }$ respectively (red dotted line in Fig.6);for crystalline diamond,the stable bond angle and bond length are $1 0 9 . 4 7 1 ^ { \circ }$ and $1 . 5 4 \mathring { \mathsf { A } }$ (black dotted line in Fig.6).Previous study has revealed that the high residual compressive stress is mainly originated from the distortion of both the bond angles and bond lengths of carbon network,which are less than $1 0 9 . 4 7 1 ^ { \circ }$ and $1 . 4 2 \mathring { \mathrm { A } }$ ,respectively [24]. By integrating the bond angle and bond length distributions (Fig.6),the fractions of distorted bond angles $( < 1 0 9 . 4 7 1 ^ { \circ } )$ and bond lengths $( < 1 . 4 2 \mathring \mathrm { A } )$ in each film are thus deduced separately,as shownin Fig.7.

First, it reveals that the films deposited at $7 0 ~ \mathrm { e V } .$ /atomhave higher fractions of both the distorted bond angles and bond lengths than that at $1 0 ~ \mathrm { e V } _ { I }$ /atom,which results in the higher residual stress shown in

![](images/92a392bc013b4bc92977abba0c39b8c127d4d8695283a8f542dc02a59fb7b7d9.jpg)  
Fig.3.Variations of density and hybridization ratio $( s p ^ { 3 \% }$ $s p ^ { 2 \% }$ or $s p \%$ along the growth direction at the thickness of (a) $4 6 . 3 7 \mathring { \mathrm { A } }$ in the film deposited at $1 0 \ \mathrm { e V } ,$ atom and (b) 45.48 Ain the film deposited at $7 0 \mathrm { e V } _ { I }$ atom.Thepositivedirectioinzotalaxisespondstotefs,iletegativediectioepresntstiginalbtate.   
Fig.4Evolutiosfsidmpietrsufofteositdtdetef $1 0 ~ \mathrm { e V } ,$ /atom and $7 0 \mathrm { e V } ,$ /atom,respectively.

![](images/dfaa7ffb320d25c459721793bd29742151ca5374dae8cb09bc4900fe7d08685f.jpg)  
Fig.5.Density and compressive stress as a function of thickness of the films deposited by FCVA method.The residual stress was calculated from the curvature of the film/substrate composite using Stoney's equation and the XRR was conducted to characterize the density of films.

Fig.4b.For the films deposited at $1 0 \ \mathrm { e V } ,$ /atom (Fig.7),increasing the thickness from 23.19 to $3 4 . 7 8 \mathring { \mathrm { A } }$ leads to the opposite changes in the fractions of distorted bond angles and bond lengths,and as a consequence which leads to the mediate change in the residual stress (Fig.4b).Nevertheless,as the thickness increases from 34.78 to $5 7 . 9 7 \mathrm { ~ \AA ~ }$ ，the fractions of distorted bond angles and bond lengths decrease simultaneously,and this combined contribution induces the fast reduction of residual stress,but the relaxation of distorted bond anglesis dominated in this case.However,when the incident kinetic energy is $7 0 ~ \mathrm { e V } ,$ /atom,Fig.7 shows that the fractions of both the distorted bond angles and bond lengths as a function of the thickness decrease gradually,which accounts for the significant release of the residual stress (Fig.4b).

For the films deposited at1O or 7O eV/atom,the different behaviors ofatomic bond structure with the thickness can be understood by the impact of carbonatoms with high incident energy.When the kinetic energy is $7 0 \mathrm { e V }$ /atom,more energy with increasing the thickness of films is released to the atoms around the deposition area,which not only relaxes the bond angles,butalso effectivelyrelaxes the C-C bond length with high strength and directionality (Fig.7).Therefore,in the ultrathin ta-Cfilms deposited at 7O eV/atom, the reduction of compressive stress is derived from the relaxation of both the highly distorted bond angles and bond lengths,which gives explanation for the significant gradient of residual compressive stress with the thickness in the simulation and experiments.

# 4. Conclusion

The ultrathin ta-C films with the thickness ranging from 2 to $6 \mathrm { n m }$ were deposited by MD simulation using Tersoff potential.The effect of thickness on properties and structure Was evaluated.For the films deposited at10 eV/atom or 70 eV/atom,the similar deposition rate was observed.The properties of ultrathin ta-C films seriously depended on the thickness.As the thickness of films deposited at $7 0 ~ \mathrm { e V } ,$ /atomvaried from 24.08 to $5 7 . 9 7 \mathring { \mathrm { A } }$ ,the compressive stress decreased linearly from 12.1 to 4.45 GPa with only $8 . 5 \%$ discount of the density.With the incidentkinetic energydecreased to $1 0 \ \mathrm { e V } ,$ /atom,theminimal compressive stress of1.79 GPa was obtained with the density of $2 . 6 3 \ : \mathrm { g } / \mathrm { c m } ^ { 3 }$ when the thickness was $5 7 . 9 7 \mathring { \mathrm { A } } .$ This behavior agreed well with the experimental results of ta-C films deposited by FCVA technique.By analyzing both the bond angle and bond length distributions,it revealed that when the incident kinetic energy was $1 0 \mathrm { ~ e V / a t o m }$ ,the reduction of residual compressive stress with the thickness mainly attributed to the relaxation of the distorted bond angles,while in the films deposited at 7O eV/atom, it resulted from the relaxation of both the distorted bond angles and bond lengths.The study for the thickness dependence of properties of ultrathin ta-C films provided a theoretical guide for designing and preparing ultrathin ta-C films with high performance.

![](images/ae2301946811f9ab4cb3299fbd256b89c38768d76cab1ae42335935542370eae.jpg)  
Fig.Distributionsofbondangleandbondlengthsfunctionofthetickessoffisdepositedattheincidentkineticeeisf(a) $1 0 \ \mathrm { e V } _ { I }$ (atom and (b) $7 0 \mathrm { e V } _ { I }$ atom,respectively

![](images/78bb407fc751ec9f4d7c1b837b2c505bbc547803697bf344ce4b989a0f391942.jpg)  
Fig.7.Fractions of(a) distorted bond angles $\mathit { \check { \Psi } } < 1 0 9 . 4 7 1 \ ^ { \circ } ,$ and (b) bond lengths $( < 1 . 4 2 \mathring \mathrm { A } )$ as a function of the thickness of films deposited at the incident kinetic energies of $1 0 \ \mathrm { e V } _ { I }$ atomand $7 0 \mathrm { e V } ,$ atom,respectively.

# Conflict of interest statement

The authors declare that there are no conflicts of interest

# Acknowledgments

This research was supported by the State Key Project of Fundamental Research of China （2012CB933003,2013CB632302),the National Natural Science Foundation of China(51371187),the China Postdoctoral Science Foundation （2014M551780）and the Ningbo Science and Technology Innovation Team (2011B81001).

# References

[1]J.Robertson,Mater. Sci. Eng.37(2002) 129-281.   
[2]C.Casiraghi, J.Robertson,A.C.Ferrari, Mater.Today 10(2007) 44-53. [3]A.C.Ferrari, Surf.Coat. Technol.180-181(2004) 190-206. [4]J.Robertson,Tribol.Int.36(2003)405-415. [5]C.Casiraghi, A.C.Ferrari, R. Ohr,D.Chu, J. Robertson, Diamond Relat.Mater.13 (2004) 1416-1421. [6]M.G.Beghi,A.C.Ferrari,K.B.K. Teo,J. Robertson, C.E.Bottani,A.Libassi,B.K.Tanner, Appl.Phys.Lett. 81(2002) 3804-3806. [7]P.Lemoine,J.P.Quinn,P.D.Maguire,J.A.D.McLaughlin,Carbon 44(2006) 2617-2624. [8]F.Liu, Z.Wang, Surf. Coat. Technol.203(2009) 1829-1832. [9] X.Z. Che,L.H. Chen,H.T. Ma,H.X. Fang, Chin. Sci. Bul55(2010) 1949-1951.   
[10]N. Soin,S.S. Roy, S.C.Ray,P. Lemoine,M.A.Rahman,P.D.Maguire,S.K.Mitra, J.A. McLaughlin,Thin Solid Films 520 (2012) 2909-2915.   
[11]D.Liu, G.Benstetter,E.Lodermeier,Thin Solid Films 436 (2003) 244-249.   
[12]E. Neyts, A. Bogaerts,R. Gijbels,J. Benedikt, M.C.M.van de Sanden, Diamond Relat. Mater.13(2004) 1873-1881.   
[13]E. Neyts,M. Eckert,A. Bogaerts,Chem.Vap.Depos.13 (2007)312-318.   
[14]E.Neyts,M.Tacq,A. Bogaerts,Diamond Relat.Mater.15 (2006) 1663-1676.   
[15]J.Tersoff,Phys.Rev.Lett. 61(1988)2879-2882.   
[16]N.Marks,J.Phys. Condens.Matter14(2002)2901-2926.   
[17] S.H.Lee, C.S.Lee, S.C.Lee,K.H. Lee,K.R. Lee, Surf. Coat.Technol.177-178 (2004) 812-817.   
[18] H.U. Jäger,A.Yu. Belov,Phys. Rev.B 68 (2003) 024201(1)-024201(13).   
[19]D.W.Brenner,Phys.Rev.B 42(1990) 9458-9471.   
[20]D.W.Brenner,Phys.Rev.B 46(1992) (1948-1948).   
[21]D.W. Brenner, O.A. Shenderova,J.A.Harrison,S.J. Stuart, B.Ni,S.B. Sinnott, J.Phys, Condens.Matter14(2002) 783-802.   
[22]S.J. Stuart, A.B.Tutein,J.A. Harrison,J. Chem. Phys.112 (2000) 6472-6486.   
[23]S.J. Plimpton, J. Comp.Physiol.117(1995) 1-19.   
[24]X.Li,P.Ke,H. Zheng,A.Wang,Appl. Surf. Sci.273 (2013) 670-675.   
[25]H.J.C. Berendsen, J.P.M. Postma, W.F.van Gunsteren, A. DiNola, J.R. Haak,J. Chem. Phys.81(1984)3684-3690.