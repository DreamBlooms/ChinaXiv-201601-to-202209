# Lepton identification at particle flow oriented detector for the future $e ^ { + } e ^ { - }$ Higgs factories

Dan ${ \bf Y } { \bf u } ^ { 1 , 2 }$ , Manqi Ruana,1, Vincent Boudry², Henri Videau²

1IHEP, China   
2LLR,Ecole Polytechnique,France

Received:date/Accepted:date

Abstract The lepton identification is essential for the physici programs at high-energy frontier,especially for the precise measurement of the Higgs boson.For this purpose,a Toolkit for Multivariate Data Analysis(TMVA) based lepton identification $\mathrm { ( L I C H ^ { 1 } ) }$ ）has been developed for detectors using high granularity calorimeters.Using the conceptual detector geometry for the Circular Electron-Positron Collider (CEPC) and single charged particle samples with energylarger than $2 { \mathrm { ~ G e V } } ,$ LICH identifies electrons/muons with efficiencies higher than $9 9 . 5 \%$ and controls the mis-identification rate of hadron to muons/electrons to better than $1 \% / 0 . 5 \%$ . Reducing the calorimeter granularity by 1-2 orders of magnitude, the lepton identification performance is stable for particles with $\mathrm { E } > 2 \mathrm { G e V } .$ Applied to fully simulated $\mathrm { e e H } / \mu \mu \mathrm { H }$ events, the lepton identification performance is consistent with the single particle case: the efficiency of identifying all the high energyleptons in an event,is $9 5 . 5 { - } 9 8 . 5 \%$ ：

# 1 Introduction

Afterthe Higgs discovery, the precise determination of the Higgs boson properties becomes the focus of particle physics experiments.Phenomenological studies show that the physics at TeV scale would be revealed if the Higgs couplings could reach the percent level measurement accuracy[1][2].

The LHC is a powerful Higgs factory. However, the precision of Higgs measurements at the LHC is limited by the huge QCD background, the large theoretical and systematical uncertainties.In addition,the Higgs signal at the LHC is usually tagged by the Higgs decay products,making those measurements alwaysmodel dependent.Therefore,the precision of Higgs couplings at the HL-LHC is typically limited to $5 \mathrm { - } 1 0 \%$ level depending on theoretical assumptions [3][4].

In terms of Higgs measurements,the electron-positron colliders play a role complementary to the hadron colliders with distinguishable advantages.Many electron-positron Higgs factories have been proposed, including the InternationalLinear Collider (ILC),the CompactLInear Collider (CLIC), the Future $\mathrm { e + e \mathrm { - } }$ Circular Collider (FCC-ee) and the CEPC[1][5][6]. These proposed electron-positron Higgs factories pick and reconstruct Higgs events with an efficiency close to $100 \%$ ,and determine the absolute value of the Higgs couplings.Compared to theLHC, these facilities have much better accuracy on the Higgs total width measurements and Higgs exotic decay searches,in addition the accuracies of Higgs measurements are dominated by statistic errors.For example,the circular electron-positron collider(CEPC） is expected to deliver 1 million Higgs bosons in its Higgs operation, with which the Higgs couplings will be measured to percent or even per mille level accuracy[6].

The lepton identification is essential to the precise Higgs measurements.The Standard Model Higgs boson has roughly $10 \%$ chance to decay into final states with leptons,for example, $\mathrm { H } \to \mathrm { W W ^ { * } \to }$ llvv/lvqq, $\mathrm { H {  } Z Z ^ { \ast } {  } l l q q }$ ， $\mathrm { H } \to \tau \tau$ ， $\mathrm { H } $ $\mu \mu$ ,etc.The SMHiggs also has a branching ratio $\mathrm { \mathbf { B r } ( H {  } b b ) }$ （204号 $= 5 8 \%$ ，while the lepton identification provides an important input for the jet flavor tagging and the jet charge measurement. On top of that, the Higgs boson has a significant chance to be generated together with leptons.For example, in the ZH events,the leading Higgs generation process at $2 4 0 – 2 5 0 \mathrm { G e V }$ electron-positron collisions,about $7 \%$ of the Higgs bosons are generated together with a pair of leptons （ $\operatorname { B r } ( Z \to \mathrm { e e } )$ and $\operatorname { B r } ( \mathrm { Z } \to \mu \mu ) = 3 . 3 6 \%$ ).At the electronpositron collider, ZH events with Z decaying into a pair of leptons is regarded as the golden channel for the HZZ coupling and Higgs mass measurement[7]. Furthermore,leptons are intensively used as a trigger signal for the proton colliders to pick up the physics events from the huge QCD backgrounds.The Particle Flow Algorithm(PFA) becomes the paradigm of detector design for the high energy frontier[8 9,6,12]. The key idea is to reconstruct every final state particle in the most suited sub-detectors,and reconstruct all the physics objects on top of the final state particles.The PFA oriented detectors have high efficiency in reconstructing physics objects such as leptons, jets,and missing energy. The PFA also significantly improves the jet energy resolution,since the charged particles,which contribute the majorityof jet energy,areusuallymeasuredwithmuchbetter accuracies in the trackers than in the calorimeters[14,9,10, 11,13].

To reconstruct every final state particle, the PFA requires excellent separation by employing highly-granularcalorimeters.In the detector designs of the International Large Detector(ILD)or the Silicon Detector(SiD)[1,15],the total number of readout channels in calorimeters reaches the $1 0 ^ { 8 }$ level.In addition to cluster separation,detailed spatial,energy and even time information on the shower developments is provided.An accurate interpretation of this recorded information will enhance the physics performance of the full detector[16].

Using the information recorded in the high granularity calorimeterand thedE/dxinformationrecorded in the tracker LICH(Lepton Identification in Calorimeter with High granularity),a dedicated lepton identification algorithm for Higgs factories has been developed.Using CEPC conceptual detector geometry [6](based on ILD) and the Arbor[14] reconstruction package, its performance is tested on single particles and physics events.For the single particles with energy higher than $2 { \mathrm { G e V } } _ { : }$ ，LICH reaches an efficiency better than $9 9 . 5 \%$ in identifying the muons and the electrons,and $9 8 \%$ for pions.Its performance on physics events $( \mathrm { e e H } / \mu \mu \mathrm { H } )$ and the final efficiency agrees with the eficiency at the single particle level.

This paper is organized as follows.The detector geometryand the samples are presentedin section2.In section 3,the discriminant variables measured fromcharged reconstructed particles are summarized and the algorithm architecture is presented.In section 4, the LICH performance on single particle events is presented.In section 5,the correlations between LICH performance and the calorimeter geometry are explored.In section 6,the LICH performance on ZH events where Z decays into ee or $\mu \mu$ pairs is studied, the results are then compared with that of single particle events. In section 7,the results are summarized and the impact of calorimeter granularity is discussed.

# 2 Detector geometry and sample

In this paper, the reference geometry is the CEPC conceptual detector [6],which is developed from the ILD geometry[1]. ILD is a PFA oriented detector meant to be used for centre of mass energies up to $1 \mathrm { T e V . }$ It is equipped with a low material tracking system and a calorimeter systems with extremely high granularity.

In this CEPC conceptual detector design, the forward region,and the yoke thickness have been adjusted to the CEPC collision environment with respect to theILD detector. The core part of this detector is a large solenoid of 3.5 Tesla. Thesolenoidsystemhasaninnerradiusof3.4metersanda length of8.O5meters,inside which both trackerand calorimeter system are installed.The tracking system is composed of a TPC as the main tracker, a vertex system,and the silicon tracking devices.The amount of material in front of the calorimeter is kept to $\sim 5 \%$ radiation length.Both ECAL and HCAL use sampling structures and have extremely high granularity. The ECAL uses tungsten as the absorber and silicon for the sensor.In depth,the ECAL is divided into 3O layers and in the transverse direction,each layer is divided into 5 by $5 \mathrm { m m } ^ { 2 }$ cells.The HCAL uses stainless steel absorber and GRPC(Glass Resistive Plate Chamber) sensor layers.It uses 10 by $1 0 \mathrm { m m } ^ { 2 }$ cells and has 48 layers in total.

As a Higgs factory, the CEPC will be operated at 240- $2 5 0 \mathrm { G e V }$ center of mass energy. To study the adequate lepton identification performance,we simulated single particle samples $( \mathrm { p i o n } +$ , muon-,and electron-) over an energy range of $1 { \mathrm { - } } 1 2 0 \mathrm { G e V }$ (1,2,3,5,7,10,20,30,40,50,70,120 GeV). At each energy point,1OOk events are simulated for each particle type.These samples followa flat distribution in theta and phi over the $4 \pi$ solid angle.

These samples are reconstructed with Arbor (version 3.3) To disentangle the lepton identification performance from the effect of PFA reconstruction and geometry defects,we select those events where only one charged particle is reconstructed.The total numberof these events is recorded as $N _ { 1 P a r t i c l e }$ ,and the number of these events identified with correct particle types is recorded as $N _ { 1 P a r t i c l e , T }$ . The performance of lepton identification is then expressed as a migration matrix in Table 2,its diagonal elements $\varepsilon _ { i } ^ { i }$ refer to the identification efficiencies (defined as $N _ { 1 P a r t i c l e , T } / N _ { 1 P a r t i c l e } )$ and the off diagonal element $P _ { j } ^ { i }$ represent the probability of a type $i$ particle to be mis-identified as type $j$

Table1 Migration Matrix   

<html><body><table><tr><td></td><td>e-like</td><td>μ-like</td><td>π+like</td><td>undefined</td></tr><tr><td>e</td><td></td><td>p</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td></tr><tr><td>π+</td><td>P</td><td>P</td><td></td><td></td></tr></table></body></html>

# 3Discriminant variables and the output likelihoods

LICH takes individual reconstructed charged particles as in put,extracts 24 discriminant variables for the lepton iden

tification,and calculates the corresponding likelihood to be anelectron or a muon.These discriminant variables can be characterized into five differentclasses:

# - dE/dx

For a track in the TPC, the distribution of energy loss per unit distance follows a Landau distribution.The dE/dx estimator used here is the average of this value but after cutting tails at the two edges of the Landau distribution (first $7 \%$ and last $30 \%$ ).The dE/dx hasa strong discrim inant power to distinguish electron tracks from others at low energy (under $1 0 \mathrm { G e V } ,$ (Figure 1).

![](images/2cbd3b777186f3f73edb55705c7741ac6e69353e5062825a639c181d7d70b0db.jpg)  
Fig.1 dE/dx for $e ^ { - }$ $\mu ^ { - }$ and $\pi ^ { + }$ ,for electrons it is stable around $2 . 4 \times$ $1 0 ^ { - 7 }$ ,for muon and pion it is smaller at energy lower than $1 0 \mathrm { G e V }$ and after that they start mixing with electron

# -FractalDimension

The fractal dimension(FD)of a shower isused to describe the self-similar behavior of shower spatial configurations, following the original definition in [16], the fractal dimension is directly linked to the compactness of the particle shower.

Ata fixed energy, the EM showers are much more compact than the muon or hadron shower, leading to a large FD.The muon shower usually takes the configuration of a1-dimensional MIP(MinimumIonizing Particle) track, therefore has a FD close to zero.The FD of the hadronic shower usually lays between the EM and MIP tracks, since it contains both EM and MIP components.A typical distribution of FD for $4 0 \mathrm { G e V }$ showers is presented in Figure 2,

Foranycalorimetercluster,LICHcalculates5different FD values:from its ECAL hits,HCALhits,hits in10 or 20 first layers of ECAL,and all the calorimeter hits.

# -Energy Distribution

LICH builds variables out of the shower energy infor mation,including the proportion of energy deposited in the first1O layers in ECAL to the entire ECAL,or the

![](images/371ba6b2f52c66dba8535611f920823408aeb9b5c7620d0409d921757ab02ebc.jpg)  
Fig.2 Fractal dimension using both ECAL and HCAL for $e ^ { - }$ $\mu ^ { - }$ and $\pi ^ { + }$ at $4 0 \mathrm { G e V }$

energydeposited inacylinderaround the incidentdirectionwitharadius of1and1.5Moliereradius.

# -HitsInformation

Hits information refers to the number of hits in ECAL andHCAL and some other information obtained from hits, such as the number of ECAL (HCAL) layers hit by the shower, number of hits in the first1O layers of ECAL.

# -Shower Shape, Spatial Information

The spatial variables include the maximum distance between a hit and the extrapolated track, the maximum distance and average distance between shower hits and the axis of the shower (defined by the innermost point and the center of gravity of the shower),the depth (perpendicular to the detector layers) of the center of gravity, and the depth of the shower defined as the depth between the innermost hit and the outermost hit.

The correlation of those variables at energy $4 0 \mathrm { G e V }$ are summarized in Figure 3,the definitions of all the variables are listed in Appendix A.It is clear that the dE/dx,measured from tracks,does not correlate with any other variables which are measured from calorimeters.Some of the variables are highly correlated, such as FD_ECAL (FD calculated from ECAL hits) andEcalNHit (number of ECAL hits).Howeverall these variables are kept because their correlations change with energy and polar angle.

LICH uses TMVA[17] methods to summarize these input variables into two likelihoods,corresponding to electrons and muons.Multiple TMVAmethods have been tested and the Boosted Decision Trees with Gradient boosting (BDTG) method is chosen for its better performance.The e-likeness $( L _ { e } )$ and $\mu$ -likeness $( L _ { \mu } )$ for different particles in a $4 0 \mathrm { G e V }$ sample are shown in Figure 4.

![](images/5cc5134a0abba1334fbcaa8ee619f65528b4c8fed04d06d8e521065b57a4bd0c.jpg)  
Fig.3 The correlation matrix of all the variables

![](images/594bcd8515844641a411da807900ebc7ce0cb75587d0cca98c0f85ab19ca3321.jpg)  
Fig.4 The e-likeliness and $\mu$ -likeness of $e ^ { - }$ $\mu ^ { - }$ and $\pi ^ { + }$ at $4 0 \mathrm { G e V } ,$ grey lines are the cuts for different catalogs in next section

# 4 Performance on single particle events

The phase space spanned by the lepton-likelihoods $L _ { e }$ and $L _ { \mu } \mathrm { , }$ ） can be separated into different domains,corresponding to different catalogs of particles.The domains for particles of different types can be adjusted according to physics re quirements.In this paper, we demonstrate the lepton identification performance on single particle samples using the following catalogs:

- Muon: $L _ { \mu } > 0 . 5$   
- Electron: $L _ { e } > 0 . 5$   
- Pion: 1 $- ( L _ { \mu } + L _ { e } ) > 0 . 5$   
- Undefined: $L _ { \mu } < 0 . 5$ & $L _ { e } < 0 . 5$ &1 $- ( L _ { \mu } + L _ { e } ) < 0 . 5$

The probabilities of undefined particles are very low $( < 1 0 ^ { - 3 } )$ at single particle samples with the above catalog.

Since the distribution of these variables depends on the polar angle of the initial particle(θ),the TMVA is trained independently on four subsets:

- barrel 1: middle of barrel $( | \cos \theta | < 0 . 3 )$   
-barrel2:edge ofbarrel $( 0 . 3 < | \cos \theta | < 0 . 7 )$   
- overlap: overlap region of barrel and endcap $( 0 . 7 < | \cos \theta |$ $\left. < 0 . 8 \right)$ ，   
-endcap: $( 0 . 8 < | \cos \theta | < 0 . 9 8 )$

Take the sample of $4 0 \mathrm { \ G e V }$ charged particle as an example,the migration matrix is shown in Table 2. Comparing this table to the result of ALEPH for energetic taus[18], the efficiencies are improved,and the mis-identification rates from hadrons to leptons are significantly reduced.

Table2MigrationMatrixat40 GeV $( \% )$   

<html><body><table><tr><td>Type</td><td>e-like</td><td>μ-like</td><td>π+like</td></tr><tr><td>e</td><td>99.71±0.08</td><td><0.07</td><td>0.21±0.07</td></tr><tr><td>μ</td><td><0.07</td><td>99.87±0.08</td><td>0.05±0.05</td></tr><tr><td>π+</td><td>0.14±0.05</td><td>0.35±0.08</td><td>99.26±0.12</td></tr></table></body></html>

The lepton identification efficiencies(diagonal terms of the migration matrix） at different energies are presented in Figure 5 for the different regions.The identification efficiencies saturate at $9 9 . 9 \%$ for particles with energy higher than $2 { \mathrm { G e V } } .$ For those with energy lower than $2 { \mathrm { G e V } } ,$ the performance drops significantly, especially in barrel2 and overlap regions.For the overlap region, the complex geometry limits the performance;while for the barrel2 region,charged particles with $\mathrm { P t } < 0 . 9 7 \ \mathrm { G e V }$ cannot reach the barrel, they will eventually hit the endcaps at large incident angle, hence their signal is more difficult to catalog.

Concerning the off-diagonal terms of the migration matrix,the chances of electrons to be mis-identified as muons and pions are negligible $( P _ { \mu } ^ { e } , P _ { \pi } ^ { e } < 1 0 ^ { - 3 } )$ , the crosstalk rate $P _ { e } ^ { \mu }$ is observed at even lower level. However, the chances of pions to be mis-identified as leptons $( P _ { e } ^ { \pi } , P _ { \mu } ^ { \pi } )$ are of the order of $1 \%$ and are energy dependent.In fact, these misidentifications are mainly induced by the irreducible physics effects: pion decay and $\pi ^ { 0 }$ generation via $\pi$ -nucleon collision.Meanwhile,the muons also have a small chance to be mis-identified as pions at energy smaller than $2 \mathrm { G e V } .$ Figure 6 shows the significant crosstalk items ( $( P _ { e } ^ { \pi }$ $P _ { \mu } ^ { \pi }$ and $P _ { \pi } ^ { \mu }$ as a function of the particle energy in the endcap region. The greenshaded band indicates the probability of pion decay before reaching the calorimeter,which is roughly comparable with $P _ { \mu } ^ { \pi }$

# 5Lepton identification performance on single particle events for different geometries

The power consumption and electronic cost of the calorimeter system scale with the number of readout channels.It's important to evaluate the physics performance for different calorimeter granularities,at which theLICH performance is analyzed.

![](images/c17c9c9621285a30181671175914c78d5aff268dbf17f13add4de185a1d96a15.jpg)  
Fig.5The efficiency of lepton identification for $e ^ { - }$ ， $\mu ^ { - }$ and $\pi ^ { + }$ as function of particle energy in the four regions

![](images/a68b5bd49ab7411cf74ddeca8bd9570e5b5aa40ffe177914d1a538f5949d7750.jpg)  
Fig.6 The mis-identification rates of lepton identification for $\mu$ and （204号 $\pi$ in $\sim 5 0 0 0$ events for the endcap region; Pion decay rate band (to accountforthepolarangle spread)isindicatedforcomparison

The performance is scanned over certain ranges of the following parameters:

the number of layers in ECAL,taking the value of 20, 26,30;   
- the number oflayers in HCAL: 20,30,40,48;   
- the ECAL cell siz $\mathsf { a } = 5 { \times } 5 \ \mathrm { m m } ^ { 2 }$ ， $1 0 \times 1 0 ~ \mathrm { m m } ^ { 2 }$ ， $2 0 \times 2 0$ （204号 $\mathrm { m m } ^ { 2 }$ $4 0 \times 4 0 ~ \mathrm { m m } ^ { 2 }$   
HCAL cell size $= 1 0 \times 1 0 \ \mathrm { m m } ^ { 2 }$ ， $2 0 { \times } 2 0 ~ \mathrm { m m } ^ { 2 }$ ， $4 0 \times 4 0$ $\mathrm { m m } ^ { 2 }$ $6 0 \times 6 0 ~ \mathrm { m m } ^ { 2 }$ ， $8 0 \times 8 0 \mathrm { m m } ^ { 2 }$

In general, the lepton identification performance is extremely stable over the scanned parameter space. Only for HCAL cell size larger than $6 0 \times 6 0 ~ \mathrm { m m } ^ { 2 }$ or HCAL layer number less than 2O,marginal performance degradation is observed: the efficiency of identifying muons degrades by $1 - 2 \%$ for low energy particles( $\mathrm { E } \leq 2 \ \mathrm { G e V } ,$ ,and the identification efficiency of pion degrades slightly over the full energy range, see Figure 7.

![](images/0ee780b321495039a7697d743e09b1bd279df82c481e7c9b8ebf485d0973fb0c.jpg)  
Fig.7 The efficiency oflepton identification for two different geometries

# 6Performance on physics events

The Higgs boson is mainly generated through the Higgsstrahlung process (ZH) and more marginally through vector boson fusion processes at electron-positron Higgs factories. A significant part of the Higgs bosons will be generated together with a pair of leptons (electrons and muons). These leptons are generated from the Z boson decay of the ZH process.For the electrons,they can also be generated together with Higgs boson in the $Z$ boson fusions events,see Figure 8.At the CEPC, $3 . 6 \times 1 0 ^ { 4 } ~ \mu \mu \mathrm { H }$ events and $3 . 9 \times 1 0 ^ { 4 }$ eeH events are expected at an integrated luminosity of ${ 5 \mathrm { a b } ^ { - 1 } }$ . In these events,the particles are rather isolated.

![](images/4558318917cd41dc5dd3a7c2f6fd79065c68a68b6767f8a196c23bdbf450e699.jpg)  
Fig.8Feynman diagrams of major Higgs production with leptons at CEPC:the Higgsstrahlung and ZZ fusion processes.

The eeH and $\mu \mu \mathrm { H }$ events provide an excellent access to the model-independent measurement to the Higgs boson using the recoil mass method [7]. The recoil mass spectrum of eeH and $\mu \mu \mathrm { H }$ events is shown in Figure 9,which exhibits a high energy tail induced by the radiation effects (ISR,FSR, bremsstrahlung, beamstrahlung,etc),while in CEPC the beamstrahlung effectis negligible.The bremsstrahlung effects for the muons are significantly smaller than that for the electrons,therefore,it hasa higher maximumand a smaller tail.

![](images/9dbe81b1277e7d152ae038431bb608ee25d0ce72998664b2aba78f141d57e5d4.jpg)  
Fig.9 The recoil mass spectrum of $\mathrm { e e } / \mu \mu$ ,low energy peak in eeH corresponds to the Z fusion events

Figure 1O shows the energy spectrum for all the reconstructed charged particles in $1 0 \mathrm { k } \exp \mathrm { \# } / \mu \mu \mathrm { H }$ events.The leptons could be classified into 2 classes,the initial leptons (those generated together with the Higgs boson) and those generated from the Higgs boson decay cascade.For the eeH events,the energy spectrum of the initial electron exhibits a small peak at low energy,corresponding to the Z fusion events.The precise identification of these initial leptons is the key physics objective for the lepton identification performance of the detector.

![](images/7609b46b56aefc8d2006d8f370462c8bd57ef25eb3b8715a43c5cfd44158429a.jpg)  
Fig.10 Energy Spectrum of charged particles in eeH event at $2 5 0 \mathrm { G e V }$ center of mass energy

Since the lepton identification performance depends on the particle energy,and most of the initial leptons have an energy higher than $2 0 \mathrm { G e V } .$ ，we focused on the performance study of lepton identification on these high energy particles at detectors with two different sets of calorimeter cell sizes.

The $\mu$ -likeliness and e-likeliness of electrons,muons, and pions,for eeH events and $\mu \mu \mathrm { H }$ events are shown in Figure 11 and Figure 12.Table 3 summarizes the definition of leptons and the corresponding performance at different conditions.The identification efficiencies for the initial leptonsis degraded by $1 - 2 \%$ with respect to the single particle case. This degradation is mainly caused by the shower overlap,and it's much more significant for electrons as electron showers are much wider than that of muon,leading to a larger chance of overlapping.The electrons in $\mu \mu \mathrm { H }$ events and vice versa,are generated in theHiggs decay. Their identification efficiency and purity still remains at a reasonable level.For charged leptons with energy lower than $2 0 { \mathrm { G e V } } ,$ the performance degrades by about $10 \%$ because of the high statistics of background and the cluster overlap.The event identification efficiency,which is defined as the chance of successfully identifying both initial leptons,is presented in thelastrowofTable3.Theeventidentificationefficiencies is roughly the square of the identification efficiency of the initial leptons.Comparing the performance of both geometries,itis shown that when the number of readout channels is reduced by 4, the event reconstruction efficiencyis degraded by $1 . 3 \%$ and $1 . 7 \%$ ,for $\mu \mu \mathrm { H }$ and eeH events respectively.

# 7 Conclusion

The high granularity calorimeter is a promising technology fordetectors in collider facilities of the High Energy Frontiers.It provides good separation betweendifferent final state particles,which is essential for the PFA reconstructions.It also records the shower spatial development and energy profile to an unprecedented level of details,which can be used for the energy measurement and particle identifications.

To exploit the capability of lepton identification with high granularity calorimeters and also to provide a viable toolkit for the futureHiggs factories,LICH,a TMVAbased lepton identification package dedicated to high granular calorimeter,has been developed.Using mostly the shower description variables extracted from the high granularity calorimeter and also the dE/dx information measured from tracker,LICH calculates the e-likeness and $\mu$ -likeness for each individually reconstructed charged particle.Based on these output likelihoods,the leptons can be identified according to different physics requirement.

Applied to single particle samples simulated with the CEPC_v1 detector geometry, the typical identification efficiency for electron and muon is higher than $9 9 . 5 \%$ for energies higher than $2 \mathrm { G e V . }$ For pions,the efficiency is reaching $9 8 \%$ . These efficiencies are comparable to the performance reached by ALEPH,while the mis-identification rates are significantly improved. Ultimately, the performances are lim ited by the irreducible confusions,in the sense that the chance formuonto be mis-identified as electron andviceversa is negligible,the mis-identification of pion to muon is dominated by the pion decay.

The tested geometry uses a ultra-high granularity calorimeter: the cell size is 1 by $1 ~ \mathrm { c m } ^ { 2 }$ and the layer number ofECAL/HCAL is 30/48.In order to reduce the total channel number,LICHis applied to a much more modest granularity,it is found that the lepton identification performance degrades only at particle energies lower than $2 { \mathrm { G e V } }$ for an HCAL cell size bigger than $6 0 \times 6 0 ~ \mathrm { m m } ^ { 2 }$ or with an HCAL layer number less than 20.

The lepton identification performance of LICHis also tested on the most important physics events at CEPC.In these events,multiple final state particles could be produced ina single collision,the particle identification performance will potentially be degraded by the overlap between nearby particles.The lepton identification on $\mathrm { e e H } / \mu \mu \mathrm { H }$ event at 250

Table 3 $\mu \mu \mathrm { H / e e H }$ events lepton identification efficiency   

<html><body><table><tr><td></td><td colspan="2">Geom1 (ECAL and HCAL Cell Size 10×10 mm²)</td><td colspan="2">Geom 2 (ECAL and HCAL Cell Size 20×20 mm²)</td></tr><tr><td></td><td>μμH</td><td>eeH</td><td>μμH</td><td>eeH</td></tr><tr><td>μ definition</td><td>Lμ>0.1</td><td>Lμ>0.1</td><td>Lμ>0.1</td><td>Lμ>0.1</td></tr><tr><td>e definition</td><td>Le>0.01Lμ<0.1</td><td>Le>0.001 Lμ<0.1</td><td>Le>0.01Lμ<0.1</td><td>Le>0.001 Lμ<0.1</td></tr><tr><td></td><td>93.41±0.92</td><td>98.64± 0.08</td><td>91.60 ±1.02</td><td>97.89 ± 0.11</td></tr><tr><td>ne</td><td>92.02 ± 1.00</td><td>99.74 ± 0.04</td><td>89.89 ±1.10</td><td>99.67± 0.04</td></tr><tr><td></td><td>99.54± 0.05</td><td>95.53 ±0.76</td><td>99.19 ±0.06</td><td>86.48±1.26</td></tr><tr><td>nu</td><td>99.60±0.04</td><td>96.31±0.70</td><td>99.83 ±0.03</td><td>95.38 ±0.81</td></tr><tr><td>Eevent</td><td>98.53±0.13</td><td>97.06±0.19</td><td>97.24±0.18</td><td>95.40±0.24</td></tr></table></body></html>

![](images/f6f0fb7f0a80dd14762bbca36de54c3d82a5d0bb7a1a6b9570c4fa8425a1a524.jpg)  
rig.11 e-likelihood and $\mu$ -likelihoodofcharged particleswith $\mathrm { E } { > } 2 0$ GeVin eeH event

![](images/9b9b247e780c3e352f7e38352cb993d5bc970b63d66e46465437208d18c92775.jpg)  
Fig.12 e-likelihood and $\mu$ -likelihood of charged particles with $\mathrm { E } { > } 2 0$ GeVin $\mu \mu \mathrm { H }$ event

GeV collision energy has been checked.The efficiency for a single lepton identification is consistent with the single particle results. The efficiency of finding two leptons decreases by $1 \sim 2 ~ \%$ when the cell size doubles,which means that the detector needs $2 \sim 4 \%$ more statistics in the running.In eeH events,the performance degrades because the clusteringalgorithm still needs to be optimized.

To conclude,ultra-high granularity calorimeter designed forILC provides excellent lepton identification ability, for operation close to ZH threshold.It may be a slight overkill for CEPC and a slightly reduced granularity can reach a bet ter compromise.And LICH, the dedicated lepton identification for future $e + e -$ Higgs factory, is prepared.

Acknowledgements This study was supported by National Key Programme for S&TResearch and Development(Grant NO.: 2O16YFAO400400), the Hundred Talent programs of Chinese Academy of Science No. Y3515540U1,and AIDA2020.

# Appendix A: Appendix section

List and meaning of variables used in the TMVA which are not mentioned in the text:

NH_ECALF1O:Number of hits in the first1O layers of ECAL   
-FD_ECALL2O:FD calculated using hits in the last 20 layersofECAL   
FD_ECALF1O:FD calculated using hits in the first 10 layers ofECAL   
- AL_ECAL: Number of ECAL layer groups (each five layers forms a group) with hits   
：av_NHH: Average number of hits in each HCAL layer groups (each five layers forms a group)   
- rms_Hcal: The RMS of hits in each HCAL layer groups (each five layers forms a group)   
-EEClu_r: Energy deposited in a cylinder around the incident direction witha radius of1Moliere radius   
- EEClu_R: Energy deposited in a cylinder around the incident direction with a radius of1.5Moliere radius   
- EEClu_L1O:Energy deposited in the first 1O layers of ECAL   
-MaxDisHel:Maximum distance between a hit and the helix   
- minDepth:Depth of the inner most hit   
cluDepth:Depth of the cluster position   
- graDepth: Depth of the cluster gravity center   
-EcalEn: Energy deposited in ECAL   
-avDisHtoL:Average distance between a hit to the axis from the inner most hit and the gravity center   
-maxDisHtoL:Maximum distance between a hit to the axis from the inner most hit and the gravity center   
-NLHcal: Number ofHCAL layers with hits   
- NLEcal: Number of ECAL layers with hits   
-HcalNHit:Number ofHCAL hits   
-EcalNHit:Number ofECAL hits

# References

1．T.Behnke,J.E.Brau,P.N.Burrows,et al, The International Linear Collider Technical Design Report-Volume 4:Detectors[J].arXiv preprint arXiv:1306.6329,2013.   
2.M.E.Peskin,Physics goals of the linear collider[J].arXiv preprint hep-ph/9910521,1999.   
3．ATLAS collaboration,Physics ata High-Luminosity LHC with ATLAS[J].arXiv preprint arXiv:1307.7292,2013.   
4.CMS collaboration,Projected Performance of an Upgraded CMS Detector at the LHC and HL-LHC: Contribution to the Snowmass Process[J].arXiv preprint arXiv:1307.7135,2013.   
5.CLIC CDR,A multi-TeV linear collider based on CLIC technology: CLIC Conceptual Design Report[J].edited by M.Aicheler,P. Burrows,M. Draper, T. Garvey,P.Lebrun,K. Peach,N. Phinney, H. Schmickler,D.Schulte and N. Toge,CERN-2012-007,2012.   
6.M. Ahmad et al (The CEPC-SPPC Study Group)，CEPCSppCPreliminary Conceptual Design Report:Physics and Detector, http://cepc.ihep.ac.cn/preCDR/main preCDR.pdf, retrieved 4th May 2015   
7.Z.Chen,Y.Yang,M.Ruan,et al, Study of Higgsstrahlung Cross Section and Higgs Mass Measurement Precisions with ZH( $Z \to$ $\mu ^ { + } \mu ^ { - } ;$ eventsat CEPC[J].arXiv preprint arXiv:1601.05352,2016.   
8.CMS collaboration,Technical proposal for the phase-II upgrade of the CMS detector[J]. CERN,CERN-LHCC-2015-010.LHCC-P008,2015.   
9.M.A.Thomson,Particle flow calorimetry and the PandoraPFA algorithm[J].Nuclear Instruments and Methods in Physics Research Section A:Accelerators,Spectrometers,Detectors and Associated Equipment,2009,611(1): 25-40.   
10.F.Beaudette,The CMS Particle Flow Algorithm[J].arXiv preprint arXiv:1401.8155,2014.   
11.J.C.Brient,Improving the Jet Reconstruction with the Particle Flow Method;an Introduction[J].arXiv preprint physics/O412149, 2004.   
12.J.C.Brient,H. Videau,The calorimetry at the future $^ { \mathrm { e + } }$ e-linear collider[J].arXiv preprint hep-ex/0202004,2002.   
13.H. Videau,Energy flow or Particle flow-The technique of energy flow for pedestrians[C]//International Conference on Linear Colliders-LCWS04.Ecole Polytechnique Palaiseau,2O04:105- 120.   
14.M.Ruan,Arbor,a new approach of the Particle Flow Algorithm. arXiv:1403.4784 (2014).   
15．T.Abe, ILD Concept Group-Linear Collider Collaboration. The International Large Detector:Letter of Intent,2O1O[J].arXiv preprint arXiv:1006.3396,4(10).   
16.M.Ruan,D.Jeans,V.Boudry,J.C.Brient,&H.Videau,(2014), Fractal Dimension ofParticle Showers Measured ina Highly Granular Calorimeter,Physical review letters,112(1),012001.   
17．A.Hoecker,P.Speckmayer,J. Stelzer,J. Therhaag,E.von Toerne, H.Voss,.&D.Dannheim (20o7),TMVA-Toolkit for multivariate data analysis. arXiv preprint physics: O703039.   
18.Aleph Collaboration，Measurement of the Tau Polarisation at   
LEP[J].arXiv preprint hep-ex/0104038,2001.