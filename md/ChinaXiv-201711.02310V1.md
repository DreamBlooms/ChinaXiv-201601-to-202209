# A Novel Collimation Method forLarge Hadron Colliders

Ye Zou1, Jianquan Yang1, Jingyu Tang2,3,1

1Key Laboratory of Particle Acceleration Physics and Technology,Institute of High Energy Physics, CAS,Beijing 100049, China 2China Spallation Neutron Source, Institute of High Energy Physics,CAS,Dongguan 523803,China 3Dongguan Institute of Neutron Science, Dongguan 523808, China

This paper proposes a novel collimation method for large hadron colliders by arranging betatron and momentum colimation systems in the same insertion to improve the overall cleaning efficiency.The method has the potential of avoiding beam losses at the downstream dispersion suppression section following the conventional betatron collimation section, which is caused by those particles with single diffractive scattering at the collimators. Evident beam loss in arc sections should be avoided to protect the superconducting magnets from quenching,especially when the stored beam energy is up to hundreds of MJ level or even higher in modern proton-proton collider. Our studies show that it is beneficial to arrange the momentum collimation system just after the betatron collimation system so that it can clean the particles with lower momentum due to the single diffractive scattering in the betatron collimators. This method is being applied to the future proton-proton collider SPPC. Preliminary multi-particle simulations are presented with the Merlin code.

# I. Introduction

Since the stored energy in beam is very high at large hadron colliders， the beams are highly destructive.Evena tiny fractional loss of the full beam in a superconducting magnet could lead to a quench,and large beam losses could cause seriousdamage to acceleratorcomponents. However,beam losses are unavoidable ina collider where the beam-beam collision is the leading loss source.Therefore,besides strictly controlling beam losses and very liable beam abort system,a robust and extremely-efficient collimation system is necessary to safely dispose beam losses.To quantify the performance of the collimationsystem，the local cleaning inefficiency is defined here as

$$
\begin{array} { r } { \eta = \frac { N _ { l o s t } ^ { \Delta s } } { \Delta s \cdot N _ { a b s } } , } \end{array}
$$

where $N _ { l o s t } ^ { \Delta s }$ isthenumberof particles ost locally over a length of $\Delta s = 1 0 ~ \mathrm { c m }$ ，and $N _ { a b s }$ is the total number of particles absorbed in the collimation system. Fig.1 shows the layout of the LHC collimation system,which has the state-ofthe-art performance.1O8 movable collimators were installed，including primary collimators (TCPs)，secondarycollimators(TCSGs), absorbers(TCLAs),tertiary collimators (TCTs), and other protection collimators [1].The local cleaning efficiency can reach up to $9 9 . 9 9 3 \%$ with the design stored energy of $3 6 0 \mathrm { M J }$ and it ensures that onlyabout $1 0 ^ { - 5 }$ local inefficiencyin superconductingmagnets [2].However, even this performance is considered not sufficient to prevent the superconducting magnets quenching when LHC will be upgraded to HL-LHC[3] with the stored energy up to about $7 0 0 ~ \mathrm { ~ M J }$ .The problem arises from that the beam loss at the downstream dispersion suppression(DS） section of the betatron collimation insertion (IR7) becomes too important,and this was found due to the single diffractive(SD）effect [4].Thus the collimation system should be upgraded to handle the challenging at HL-LHC.

CMS 6 TP T 公 6 B2   
B1 X TCLAATLT   
TTCP.5R3 TCLA,7R3 TCLCOGLT TCPG6 三 Betatron   
1 cleaning cleaning TCL A.4L8 TCL TCLA,A7R7 9 TCTPALE L LHC-b ALICE TPNALZ R 乐 ATLAS

The backbone of the HL-LHC collimation system will remain as for the current LHC and the main changes are to add two local collimators at the downstream DS of IR7 to largely reduce irradiation dose rate to the superconducting magnets in the section.In order to do so,each of the two original main dipoles of $8 . 3 \mathrm { ~ T ~ }$ at the locations where the dispersion starts rising are replaced by two new shorter dipoles with new $\mathrm { N b } _ { 3 } \mathrm { S n }$ magnet technology which can work at 11 T.The saved space is used to install a TCLD collimator in between the two new dipoles,as shown in Figure 2[5]. Simulations show that with this method,most of the beam losses at the local superconducting magnets could be cleaned and also this solution almost eliminates losses around the ring coming from the telescopic squeeze. Although this method is quite suitable for the LHCupgrading， becauseofthe TCLD collimators also situating in the cold region, much more energy losses at the TCLDs must not be permitted. Thus for new hadron colliders with higher stored beam energy and more serious SD effect, this method is not favored.From Ref.[4], the SD effect is proportional to beam energy,and this means much larger potential beam loss at the downstream DS region with the LHC collimation method.Even with more available space for installing collimators in warm environment, this method is not ideal due to high neutron radiation from the collimators.In this article,a novel collimation concept is proposed for hadron colliderswith extremely high stored beam energies.

# I.A novel collimation strategy for future proton-proton colliders

A novel collimation method for large hadron colliders is proposed to tackle the problem requiring extremely high collimation efficiency. The idea is to arrange both the betatron and momentum collimation in the same cleaning insertion to avoid important beam losses in the downstream DS due to the SD effects.The momentum collimation system will clean those particles which lose significant energy in the primary betatron collimators but survive from the secondary collimators including the absorbers. Only the protons with $\Delta \mathrm { p / p } < 0 . 5 \%$ would escape the DS without local collimators in the case of LHC [6]. The maximum momentum deviation $\delta _ { \mathrm { m a x } }$ which can pass the primary momentum collimatoris defined by

$$
\begin{array} { r } { \delta _ { \mathrm { m a x } } = \frac { n _ { 1 } \sqrt { \varepsilon } } { \eta _ { \mathrm { D } } } , } \end{array}
$$

where $n _ { 1 }$ is the primary momentum collimator aperture (with respect to the rms beam size), $\varepsilon$ is the geometric emittance and $\boldsymbol { \eta } _ { \mathrm { D } }$ is the normalized dispersion at the collimator.If the maximum normalizeddispersioninthemomentum collimation section is larger than the one in the DS section or the whole arc section, in principle there will be very little beam losses in the downstream DS section or even all the arc sections. With the betatron and momentum collimations in a same long straight section,how toproduce the required dispersion in the momentum collimation section is a key issue. Different from themomentumcollimation section at the LHC where dispersionis intentionally designed non-zero between the two adjacent DS sections,here itis required to have an achromatic end at the joint between the momentum collimationandthetransverse collimation sections.

![](images/528724f2f21da84f9d7f959aa0c66c1d54026de761f548757849bf9d62c26f31.jpg)  
Fig.2.Layout of a part of IR7 with the nominal sequence and with two main dipoles replaced by 11 T dipole assemblies with a TCLD collimator in between at the HL-LHC

![](images/f8074a747921913f4e730b2b461ea03ed4557c09ac14018dd3fb62ca453332a9.jpg)  
Fig.3.Layout of the novel collimation method

Different from the momentum collimation section at the LHC where dispersionis intentionally designed non-zero between the two adjacent DS sections,here it is required to have an achromatic end at the joint between the momentumcollimation and thetransverse collimation sections.This means that we need some cold dipole magnets to produce the required dispersion for the momentum collimation and cancel the dispersion at the section end. Necessary protection from local beam loss and sectional radiation for these cold dipole magnets isalso indispensable.Some protective collimators (TCPRs) are used to intercept particles with very large momentum deviation.Another limitation is that usually the betatron collimation requires significantlylongerspaceformulti-stage collimation and the two proton beams run in opposite directions.At last,the two ends of the long straight section which connect the two adjacent arcs should not be affected by the introduced dipoles.Altogether, one can imagine a chicane structure for the momentum collimation,

as shown in Fig. 3.

To see how the method works,we try to apply it to a practically-designed machine.The lattice designandmulti-particlesimulations are presented in the next section.

# III. Applying the novel collimation methodto the SPPC

# A.Brief introductionto the SPPC

SPPC(SuperProton-Proton Collider) isa nextgeneration proton-proton collider aiming for energy-frontier physics,especially for beyondStandard Model research.It is the second phase of the CEPC-SPPC project which was proposed by Chinese scientists,and the two colliders use the same tunnel[7].Figure 4 shows the layout of the SPPC and Table 1 shows some main parameters of the preliminary baseline design From Figure 3,one can see that each of the SPPC rings is composed of eight arcs and long straight sections (LSSs)，and LSS1 is used as the collimation insertion.

![](images/200624ae324fefa94f04c2362c47cba7e8848290aaa210a8e177f0b351dfbe0e.jpg)  
Fig.4.Layout of the SPPC

Table 1: Some main parameters of the SPPC   

<html><body><table><tr><td>Parameter</td><td>Value</td><td>Unit</td></tr><tr><td>C.M. Energy</td><td>74</td><td>TeV</td></tr><tr><td>Circumference</td><td>61</td><td>km</td></tr><tr><td>Dipole field</td><td>19.9</td><td>T</td></tr><tr><td>Injection energy</td><td>2.12</td><td>TeV</td></tr><tr><td>Number of IPs</td><td>2</td><td></td></tr><tr><td>Peak luminosity per IP</td><td>1.23E+35</td><td>cm-2s-1</td></tr><tr><td>Beta function at collision</td><td>0.75</td><td>m</td></tr><tr><td>Circulating beam current</td><td>0.9</td><td>A</td></tr><tr><td>Bunch separation</td><td>25</td><td>ns</td></tr><tr><td>Bunch population</td><td>2.0E+11</td><td></td></tr><tr><td>Normalized rms emittance</td><td>3.3</td><td>μm</td></tr><tr><td>SR heat load at arc (per aperture)</td><td>42.8</td><td></td></tr><tr><td>Stored energyperbeam</td><td>6.7</td><td>W/m GJ</td></tr></table></body></html>

# B.Beamcollimationmethodandlocal latticeatthe SPPC

The stored beam energy per beam will reach up to $6 . 7 \ : \mathrm { G J }$ , and this poses an extreme challenge to the beam abort system and collimation system. The local cleaning inefficiency should achieve $1 0 ^ { - 6 }$ or even less to prevent the quenching of superconductingmagnets.Amulti-stage collimation system for both the transverse and longitudinal planes is used at the SPPC,similaras the one at the LHC，but the two collimation systems are arranged in one long straight section asexplained in Section 2. The transverse collimation is illustrated in Figure 5,perhaps with one more stage than the LHC scheme.Figure 6 shows the betatron and dispersive functions in the whole cleaning insertion.Warm quadrupoles are used for the transverse collimation section while superconducting dipoles and quadrupolesare used in the momentum collimation section.The cryostats for the superconducting magnets are connected by warm vacuum tubes,and some local shieldingisprovided to protect the superconducting magnets.

In order to protect the arc aperture from off momentum particlelossesthenormalized dispersion at the primary momentum collimator must satisfy [1]:

$$
\begin{array} { r } { \big | \eta _ { D , \mathrm { p r i m } } ( n _ { 1 } ) \big | \ge \frac { n _ { 1 } \eta _ { D , \mathrm { a r c } } } { A _ { \mathrm { a r c , i n j } } ( \delta _ { p } = 0 ) - ( n _ { 2 } ^ { 2 } - n _ { 1 } ^ { 2 } ) ^ { 1 / 2 } } , } \end{array}
$$

where $A _ { \mathrm { a r c , i n j } } ~ ( \delta _ { p } = 0 )$ is the arc aperture for onmomentum particles; $\eta _ { \mathrm { _ { D , a r c } } }$ is the normalized dispersion with errors in the focusing quadrupole magnets; $n _ { 1 } , n _ { 2 }$ are the apertures of primary and secondary collimator jaws in multiples of rms beam size. For the present design of SPPC, $A _ { \mathrm { a r c , i n j } }$ （20 $( \delta _ { p } = 0 ) = 2 2 . 3$ ， $\eta _ { \mathrm { { D , a r c } } } = 0 . 2 4 6 ~ \mathrm { { m } } ^ { 1 / 2 }$ ， $n _ { 2 } = 7 . 5$ ， $n _ { 1 } =$ 5.5, thus, $| \eta _ { \mathrm { D , p r i m } } \left( n _ { 1 } \right) | \geq 0 . 0 7 9 ~ \mathrm { m } ^ { 1 / 2 }$ is required. In addition,for ensuring that the cut of the secondary halo is independent of the particle momentum, Eq. (4) must be satisfied at the position of the primary collimator [8]:

$$
\begin{array} { r } { \frac { D _ { x } ^ { \prime } } { D _ { x } } = - \frac { \alpha _ { x } } { \beta _ { x } } . } \end{array}
$$

Two pairs of dipole groups are used to produce asufficient dispersion for themomentum collimation and the final orbit would be back on the same line with betatron collimation section. Magnet group here denotes several magnet units arranged together and has a function of one magnet of extended length. The first-version parametersare listedin Table 2.

![](images/d29c7818fe71721412b8436ff8134a218a86ed36eec9a96aef25dd88ee84dd7e.jpg)  
Fig.6.The betatron and dispersive functions of the cleaning insertion

![](images/667ce81d3c9e14e20b126b38a7edc815b6ddb47e27ec3e52db7a6357babee33d.jpg)  
Fig.5.Schematic for the multi-stage betatron collimation system at the SPPC

Table 2.Basic parameters of the collimation insertion at the SPPC   

<html><body><table><tr><td>Parameter</td><td>Value</td><td>Unit</td></tr><tr><td>Total cleaning insertion length</td><td>3.5</td><td>km</td></tr><tr><td>Betatron/momentum cleaning insertion length</td><td>2.0/1.5</td><td>km</td></tr><tr><td>Betatron/momentum cleaning insertion phase advance (H)</td><td>1.8π/2.43π</td><td>rad</td></tr><tr><td>Warm/cold quadrupole length Warm quadrupole strength</td><td>3/4 0.0002</td><td>m m²</td></tr><tr><td>Dipole magnetic length</td><td>14.8</td><td>m</td></tr><tr><td>Dipole magnetic field Number of dipoles per group</td><td>19.9</td><td>T</td></tr><tr><td>Number of dipole groups Maximum beta function (βx/βy)1160/1196 Maximum normalized dispersion</td><td>3 4</td><td></td></tr></table></body></html>

# C.Multi-particle simulations

Multi-particle simulations using the lattice parameters and collimator settings have been carried out with the code Merlin[9]. As the first approach for the betatron collimator settings, similar physical gaps and phase advances as the LHC have been chosen for just verifying the effectiveness of the novel collimation method, especially in cleaning particles related to the SD effect. The primary momentum collimator is placed at the middle quadrupole between the second and third groups of dipoles to satisfy Eq. (4),where the normalized dispersion close to the maximum absolute value.The other momentum collimators are placed downstream with the same phase advances of the currentLHC.One can find the collimator positions in Figure 7.For simplicity, the IRs are replaced by simple FODO periods in the simulations. To increase the simulation efficiency with a huge number of particles of $1 0 ^ { 8 }$ ,the initial beam distributions are chosen as a ring type distribution in the horizontal plane and a Gaussian distribution in the vertical plane. Table 3 shows the initial beam parameters for the simulations and Table 4 shows the basic parameters of the collimator settings for each beam.Figure 7 shows the beam loss distribution in the cleaning insertion without additional protective collimators,where one can see that there are still cold-area losses of about $1 0 ^ { - 5 } ~ \mathrm { m ^ { - 1 } }$ ： The reason is,after the betatron collimation, the SD effect will induce beam losses in the region where the dispersion starts to rise，and thus protective collimators (used as absorbers） are needed here.Different from placing protective collimators in the DS region where the lattice structure is very strict and tight, it is much easier to provide the space for the collimators in room temperature in the momentum collimation section. According to the positions of the lost particles, three protective collimators in Tungsten with the aperture just the same as the primary momentum collimator are placed there to intercept the particles.The specific locations are as follows: one protective collimator is placed between the second and third dipole magnets of the first dipole group to intercept particles with very large momentum deviation,and the cryostat for the dipole group is split into two parts to allow the insertion of the collimator in room temperature; another one is placed before the quadrupole between the first and second groups of dipoles to protect the quadrupole; the third one is placed in front of the second group of dipole magnets. Figure 8 and Figure 9 show the beam loss distributions in the cleaning insertion and the full ring with the protective collimators,respectively. From these two figures,one can see that with suitable protective collimators,nearly all the beam losses in the DS regions due to the SD effect disappear. Almost all the lost particles are in the collimators which are warm regions.For present design, only considering the linear condition, the maximum energy spread of particles which can through the primary collimator is about $0 . 1 ~ \%$ The situation with energy spread is also simulated, as illustrated in Fig1O andFig11.From thistwo figures, one can see that even with the maximum energy spread, the novel collimation method also has the extremely high cleaning inefficiency in the downstream DS regions,at least better than $5 { \times } 1 0 ^ { - 7 }$ ,which meets the SPPC requirement.

Table 3.Main parameters of the initial beam   

<html><body><table><tr><td>Parameter</td><td>Value</td><td>Unit</td></tr><tr><td>Beam energy</td><td>37</td><td>TeV</td></tr><tr><td>Number of particles</td><td>108</td><td></td></tr><tr><td>Normalized emittance</td><td>3.3</td><td>μm</td></tr><tr><td>Impact factor</td><td>1.0</td><td>μm</td></tr><tr><td>Energy spread</td><td>0/0.001</td><td></td></tr><tr><td>Turns</td><td>300</td><td></td></tr></table></body></html>

Table 4.Basic parameters of the collimator settings for one beam   

<html><body><table><tr><td>Functional Type</td><td>Plane</td><td></td><td>Num.Material</td><td>Aperture (0)</td></tr><tr><td rowspan="3">Betatron</td><td>TCP H, V, S</td><td>3</td><td>C</td><td>5.5</td></tr><tr><td>TCSG H, V, S</td><td>11</td><td>C</td><td>7.5</td></tr><tr><td>TCLA H,V</td><td>5</td><td>W</td><td>11.0</td></tr><tr><td rowspan="3">Momentum TCP</td><td>H</td><td>1</td><td>C</td><td>15.0</td></tr><tr><td>TCSG H</td><td>4</td><td>C</td><td>18.0</td></tr><tr><td>TCLA H,V</td><td>4</td><td>W</td><td>20.0</td></tr><tr><td>Protective</td><td>TCPR H</td><td>3</td><td>W</td><td>15.0</td></tr></table></body></html>

![](images/75750ce2c61b80b91176381ccb34bcbbe2debca6baa34d19a92d589f9252a297.jpg)  
Fig.7.The beam loss distribution of the cleaning insertion without protective collimators

![](images/aa84fffdc9f7b2354faf4c15285e02aaa5ee759eb82741bf67452ed42e8aca2d.jpg)  
Fig. 8.The beam loss distribution of the cleaning insertion with protective collimators

![](images/8b7569d47979b595bd734b7960a1a576ae28ca4240ad458c84024aa633e9eccf.jpg)  
Fig. 9.The beam loss distribution along the full ring with protective collimators

![](images/14d412b0d9875ba0ce7b6abc826f64c9053dcea0f0d3716ccb0aa19217c98a92.jpg)  
Fig.10.The beam loss distribution of the cleaning insertion with energy spread $\delta = 0 . 1 \ \%$

![](images/5ec7523abdd56cf29f8da1da8a5782cba3a436fdb91c92c597daef4830794f3d.jpg)  
Fig.11. The beam loss distribution along the full ring with energy spread $\delta = 0 . 1 \ \%$

# IV. Conclusions and discussions

A novel collimation method for large hadron colliders is proposed by arranging both betatron and momentum collimation systems in the same cleaning insertion to largely reduce beamlosses in the downstream arc section,as the beamloss in the cold regionis considered a critical issue.This arrangement can take use of the momentum collmation system to clean the very large offmomentum particles caused in the upstream transverse collimators by the single diffractive effect,along with its original function to clean the particles of large momentum deviation which maycome from beam-beam collision,intra-beam scattering and instabilities.A very long straight section is required to host the two collimation systems, each for one of the twobeams. Sufficiently large dispersion is required for the momentum collimation section,and protective collimatorsare usedtoprotect the superconducting magnets used in the region. Preliminary studies including layout,linear optics and multi-particle simulations with Merlin show that the method is very effective in eliminating beam losses in arcs.Further optimization about the method and benchmark simulations with the SixTrack code will be carried out in the next step.

# Acknowledgments

This work was supported by the National Natural Science Foundation of China(11235012, 11575214). The authors would like to specially thank James Molson of LAL for sharing and debugging the Merlin code and also thank the SPPC colleagues for discussions.

[1] O.S.Bruning,P.Collier,P.Lebrun, S.Myers,R. Ostojic,J.Poole,and P.Proudlock (editors),LHC Design Report Volume I: The LHC Main Ring, CERN-2004-003-V1,2004   
[2] B.Salvachua,et al.,Cleaning performance of the LHC collimation system up to 4 TeV, Proceedings of IPAC13, Shanghai,China (2013),p.1002   
[3] G.Apollinari,et al.,High-Luminosity Large Hadron Collider (HL-LHC） preliminary design report:Chapter5.CERN-2015-005,2015.   
[4] K.Goulianos,Diffractive interactions of hadrons at high energies,Physics Reports,101(3):169-219, 1983.   
[5]R.Bruce et al., Cleaning performance with 11T dipoles and local dispersion suppressor collimation at the LHC，Proceedings ofIPAC14，Dresden,

# Germany (2014),p. 170

[6] A.Lechner et al.,Power deposition in LHC magnets with and without dispersion suppressor collimators downstream of the betatron cleaning insertion，ProceedingsofIPAC14，Dresden, Germany (2014),p.112   
[7] The CEPC-SPPC Study Group，CEPC-SPPC Preliminary Conceptual Design Report, Volume II: Accelerator,IHEP-CEPC-DR-2015-01 (2015)   
[8] T.Trenkler and J.B.Jeanneret, The principles of two-stage betatron and momentum collimation in circular accelerators，Part.Acc.，50，(1995）287, January 1995.   
[9]Merlin,https://sourceforge.net/projects/merlinpt/