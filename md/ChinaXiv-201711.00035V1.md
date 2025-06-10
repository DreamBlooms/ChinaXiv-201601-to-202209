# Heat Transfer Enhancement in a Parabolic Trough Solar Receiver using Longitudinal Fins and Nanofluids

Amina Benabderrahmane1\*， Miloud Aminallah1， Samir Laouedj1，Abdelylah Benazza1, J.P.Solano²

1. Laboratory of Reactive Systems and Materials, Djillali Liabes University, Sidi Bel Abbes, Algeria   
2. Ingenieria Térmica y de Fluidos, Universidad Politécnica de Cartagena, Cartagena, Spain

In this paper,we presenta three dimensional numerical investigationofheat transfer ina parabolic trough colectorreceiver with longitudinal fins using diferent kinds of nanofluid,with an operational temperature of $5 7 3 \mathrm { ~ K ~ }$ and nanoparticle concentration of $1 \%$ in volume.The outer surface of the absorber receives a non-uniform heat flux,which is obtained byusing the Monte Carlo ray tracing technique.The numerical results are contrasted with empirical results available in the open literature.A significant improvement of heat transfer is derived when the Reynolds number varies in the range $2 . 5 7 { \times } 1 0 4 \leq \mathrm { R e } \leq 2 . 5 7 { \times } 1 0 5$ ,the tube-side Nusselt number increases from 1.3 to 1.8 times,also the metalic nanoparticles improve heat transfer greatly than other nanoparticles,combining both mechanisms provides better heat transfer and higher thermo-hydraulic performance.

# Keywords: numerical study,Monte Carlo ray trace,parabolic trough colector, heat transfer, longitudinal fins, nanofluid

# Introduction

THE surge in fossil fuels prices during the petrol crisis launched the industrialized countries in the race for alternative and renewable energies such as solar energy. This source of energy is considered as the most economical and clean.At the same time,solar thermal power plants have been the subject of study among the technology of parabolic trough collectors,which are currently the mOSt prOVen SOLAR CONCENTRATION TECHNIQUES [1]. Several studies have recently focused on the tube-side heat transfer enhancement of these devices, following both numerical and experimental methodologies. The descriptions of the convective heat transfer, the effect of the geometry and the use of different working fluids have been analyzed by these authors.

Aggrey et al. [2]presented a numerical investigation

# Nomenclature

of thermal performance of receiver for a parabolic trough collector (PTC) with perforated plate inserts.Their results show that the use of inserts improve the thermodynamic performance of the receiver by minimizing the entropy generation rates,and described the dependence of the Nusselt number and friction factor on the spacing and size of the insert. Wang et al.[3] investigated numerically the heat transfer enhancement in the receiver tube of a direct steam generation system with parabolic trough by inserting metal foams; they reported the significant effect of the layout and dimensionless height of metal foams on the thermal performance greatly,whereas the porosity of the foam proved to have a slight influence on the heat transfer. Song et al. [4] analyzed the heat transfer enhancement of PTC receiver with non-uniform heat flux and helical screw-tape inserts; their results indicate that the maximum temperature on the outer surface p Density, kg/m³ 入 thermal conductivity, $\sf { W } / \mathrm { m } \mathrm { K }$ μ Viscosity, Pa s

<html><body><table><tr><td>DNI</td><td>Direct normal irradiance,W/m²</td><td>n</td><td>thermo-hydraulic performance</td></tr><tr><td>f</td><td>Friction factor</td><td colspan="2">Subscripts</td></tr><tr><td>h</td><td>Heat transfer coefficient, W/m²K</td><td>amb</td><td>Ambient</td></tr><tr><td>hw</td><td>Glass cover outer heat transfer coefficient, W/m²K</td><td>b</td><td>Bulk fluid state</td></tr><tr><td>L</td><td>Receiver length, m</td><td>bf</td><td>Base fluid</td></tr><tr><td>m</td><td>Mass flow rate,kg/s</td><td>f</td><td>Fluid</td></tr><tr><td>Nu</td><td>Nusselt number</td><td>go</td><td>Outer glass cover wall</td></tr><tr><td>P</td><td>Pressure, Pa</td><td>in</td><td>Inlet</td></tr><tr><td>PEC</td><td>Performance evaluation criteria</td><td>nf</td><td>Nanofluid</td></tr><tr><td>Pr</td><td>Prandtl number</td><td>p</td><td>particle</td></tr><tr><td>q</td><td>Heat flux,W/m²</td><td>ri</td><td>absorber tube inner wall</td></tr><tr><td>Re</td><td>Reynolds number</td><td>sky</td><td>sky temperature</td></tr><tr><td>T</td><td>Temperature, K</td><td>W</td><td>wall</td></tr><tr><td>Vw</td><td>Wind velocity, m/s</td><td colspan="2">Abbreviation</td></tr><tr><td>Greek letters</td><td></td><td>HTF</td><td>heat transfer fluid</td></tr><tr><td>p</td><td>particle volume concentration</td><td>PTC</td><td>parabolic trough collector</td></tr><tr><td></td><td>emissivity</td><td></td><td></td></tr></table></body></html>

of the absorber tube increases along with inlet temperature and solar irradiation. Cheng et al.[5] carried out a numerical study of heat transfer enhancement by unilateral longitudinal vortex generators inside PTC receiver. They illustrated that the average Nusselt number and average friction factor increase with increasing each geometric parameter,whereas the thermalloss decreases with the increase of each geometric parameter.

Recently,a new class of fluids called nanofluid has been developed and tested, this term was proposed by Choi in 1995 [6] at Argonne National Laboratory; as a liquid mixture with a small concentration of nanometer-sized solid particles in suspension. Nanofluids have interesting thermo-physical properties such as high thermal conductivity.

The researches on the application of nanofluids have been popularized during the recent years; various authors have investigated the effects of using nanofluid on heat transfer enhancement inside PTC receiver.Sokhansefat et al.[7] studied the effect of using $\mathrm { A l } _ { 2 } \mathrm { O } _ { 3 } .$ /synthetic oil ina PTC tube,reporting that heat transfer augments for increasing nanoparticle volume fraction and operational temperature. Risi et al.[8] investigated the heat transfer enhancement for $\mathrm { C u O + N i / }$ nitrogen gas in a PTC tube, demonstrating that above $0 . 3 \mathrm { \ \% v o l }$ the drawback effect ofpressure drop overwhelm the beneficial effects of thermal properties,additionally the optimization procedure found a maximum solar to thermal efficiency equal to $6 2 . 5 \%$

The present work prospects the use of a compound enhancement technique for parabolic trough collector, based on the use of nanofluids and the presence of two longitudinal fins in the tube side of the PTC.A three dimensional numerical model is implemented in ANSYS Fluentfor the solutionof the flow field andheattransfer in the enhanced geometry. The heat flux around the absorber tube was obtained applying MCRT(Monte Carlo ray tracing) method. The first part of this study analyzes the effect of using longitudinal fins inserts when the Reynolds number varies in the range $2 . 5 7 \times 1 0 ^ { 4 } \leq \mathrm { R e } \leq$ $2 . { \overset { \cdot } { 5 7 } } \times 1 0 ^ { 5 }$ depending on the heat transfer fluid characteristics.In the last part we investigate a comparison between four different kinds of nanoparticles,with nanoparticle concentration of $1 \%$ in volume.The aim of this paper is to develop the influence of heat transfer fluid properties and receiver geometries of a parabolic trough solar collector.

# Physical model

In our investigation, we considered a simple model of receiver of the parabolic trough solar collector, in which all effects of the central rod and other supports are considered negligible.

Forour analysis, the solar collector which is shown in Fig.1 is chosen as the geometrical model in this simulation.The materials used for the glass cover and the absorber tube are respectively the borosilicate glass and steel.The space between both tubes is considered as a vacuumatlowpressure and ambient temperature.

The physical parameters used in this study are given in Table1.

![](images/b87c607106f976cdb11ce92d6171eed3c0dfa8166fdcc7101d72a5a5b6ce2a60.jpg)  
Fig.1Schematic ofPTC receiver

Table1 Receiver dimension.   

<html><body><table><tr><td>Focal length</td><td>1.71 m</td></tr><tr><td>Aperture width</td><td>5.77 m</td></tr><tr><td>Absorber inner radius</td><td>3.2 cm</td></tr><tr><td>Absorber outer radius</td><td>3.5 cm</td></tr><tr><td>Glass cover inner radius</td><td>5.96 cm</td></tr><tr><td>Glass cover outer radius</td><td>6.25 cm</td></tr><tr><td>Material of the absorber</td><td>Steel</td></tr><tr><td>Material of the glass envelope</td><td>Borosilicate</td></tr><tr><td>Transmittance of glass cover</td><td>>96%</td></tr><tr><td>Coating absorbance</td><td>95%</td></tr><tr><td>Glass cover emissivity</td><td>0.837</td></tr></table></body></html>

The objective of our study is to improve the heat transfer inside parabolic trough collector receiver，for which we analyze the effect oflongitudinal fins inserted in the absorber tube.Fig.2 shows the fin's physical model utilized in this work.

![](images/c38f17d2eb3f225d40af128e7ea6f62c61e1321a000a88b75f9bbc2a0fa0002f.jpg)  
Fig.2Physical model of absorber with longitudinal fins inserts.

# Numerical model

The numerical solution is formed and meshed by using the commercial software GAMBIT 2.4.6; it's also utilized for setting and specifying the boundary conditions.The turbulent model used in this study is the $k { \mathrm { - } } \omega$ SST[9]. The governing equations such as the continuity, momentum, energy and other scalars are solved by using the Finite volume solver Fluent 6.3.26 [10].

The finite volume technique converts the non-linear partial differential equations with the first order upwind scheme.The pressure-based solver is used to solve the pressure based equation.

# Heat transfer fluid properties:

In the first part of this study,the heat transfer fluid (HTF)used is synthetic oil DOWTHERM A.this is a eutectic mixture of $73 \%$ Diphenyl Oxide $\mathrm { ( C _ { 2 } H _ { 1 0 } O ) }$ and $2 7 \%$ Biphenyl $( \mathrm { C } _ { 2 } \mathrm { H } _ { 1 0 } )$ .This fluid exhibits favorable physical properties and low vapor pressure at the maximum operating temperature [11].

The thermo-physical properties of DOWTHERM A as a function of temperature are provided in Appendix A. Table 2 shows the physical characteristics of base fluid at inlet temperature $5 7 3 \mathrm { K }$

Table2Thermo-physical properties of DOWTHERMA.   

<html><body><table><tr><td>Density (kg/m³)</td><td>803.3</td></tr><tr><td>Specific heat (J/kg K)</td><td>2373</td></tr><tr><td>Thermal conductivity(W/mK)</td><td>0.093</td></tr><tr><td>Viscosity (mPa s)</td><td>0.2</td></tr></table></body></html>

# Numerical modeling

For this study, the outer wall of the absorber tube receives a non-uniform heat flux; this distribution was obtained by using the Monte Carlo ray trace technique [12].Fig.3 illustrates the simulation results of the local concentration ratio(LCR) distribution on a cross-section of the absorber outer surface.The LCR is defined as the ratio of the concentrated radiant flux at a local position on the receiver surface to the direct normal irradiance (DNI), where a DNI of $1 0 0 0 \mathrm { W / m } ^ { 2 }$ was used in this work. Symmetryboundary condition isutilized for the inlet and the outlet of the space between the absorber and the glass cover.For the outer glass cover,a thermal boundary condition that combines the convection and radiation heat transfer is used.Glass emissivity is about O.83 and sky emissivity is determined by using the correlation proposed by Martin and Berdahl [13] given by:

$$
\begin{array} { r l r } & { } & { \varepsilon _ { s k y } = 0 . 7 1 1 + 0 . 5 6 \frac { T _ { d p } - 2 7 3 . 1 5 } { 1 0 0 } } \\ & { } & { + \ 0 . 7 3 \Biggl ( \frac { T _ { d p } - 2 7 3 . 1 5 } { 1 0 0 } \Biggr ) ^ { 2 } } \end{array}
$$

Sky temperature can be calculated using the following correlation [14]:

$$
T _ { s k y } = 0 . 0 5 5 2 T _ { a m b } ^ { 1 . 5 }
$$

where the ambient temperature used in this simulation is $3 0 0 \mathrm { K }$ and $\mathrm { T _ { d p } }$ is dew point temperature (K).

Additionally, the convection heat transfer coefficient

used for the boundary condition is defined by the experimental correlation [15]:

$$
h _ { w } = 4 \nu _ { w } ^ { ~ 0 . 5 8 } d _ { g o } ^ { ~ - 0 . 4 2 }
$$

where: ${ \bf v _ { w } }$ is the wind speed $2 ~ \mathrm { m / s }$ in this study) and ${ \bf d } _ { \mathrm { g o } }$ is the glass envelope outer diameter.

![](images/b2e22e2ca1b3173cc05b4b1347696e0cee8c4149edcb00b6c0338a0026ca991a.jpg)  
Fig.3The local concentration ratio on a cross-section of the absorber outer surface

# Results and discussion

# Validationofnumericalresults

The average Nusselt number and heat transfer coefficientaredefinedas:

$$
\begin{array} { c } { { \overline { { N u } } = \displaystyle \frac { h d _ { r i } } { \lambda } } } \\ { { \overline { { h } } = \displaystyle \frac { \overline { { q ^ { \mathfrak { w } } } } } { T _ { w } - T _ { b } } } } \end{array}
$$

Where $\overline { { \boldsymbol { q } " } }$ is the average heat flux on absorber tube's inner wall; $\mathrm { { T _ { w } } }$ is the average inner wall temperature of the absorber tube and ${ \mathrm { T } } _ { \mathrm { b } }$ is the average bulk temperature of the HTF.

Also the Darcy friction factor for turbulent flow is defined in the following relation:

$$
f = \frac { \Delta p } { \frac { L } { d _ { r i } } \rho \frac { \nu ^ { 2 } } { 2 } }
$$

For validate purposes, the numerical results of Darcy friction factor are compared with the correlations proposed by Petukhov [16] and Blasius [17]; likewise the numerical results of average Nusselt number are compared with the correlations suggested by Gnielinski [18] and Notter-Rouse [19] which are given as follows:

Gnielinski correlation:

$$
N u = \frac { \frac { f } { 8 } \bigl ( \mathrm { R e } - 1 0 0 0 \bigr ) \mathrm { P r } } { 1 + 1 2 . 7 \biggl ( \frac { f } { 8 } \biggr ) ^ { 0 . 5 } \biggl ( \mathrm { P r } ^ { \frac { 2 } { 3 } } - 1 \biggr ) }
$$

where Re and $\mathrm { P r }$ are respectively the Reynolds number andPrandtl number.

In addition, $f$ is the friction factor calculated by Petukhov's correlation defined as:

$$
f = ( 0 . 7 9 \ln \mathrm { R e } - 1 . 6 4 ) ^ { - 2 }
$$

where: $1 0 ^ { 4 } \le \mathrm { R e } \le 5 \times 1 0 ^ { 6 }$

and $0 . 5 \le \mathrm { P r } \le 2 0 0 0$

Notter-Rouse represents the correlation of average Nusselt numberas follows:

$$
N u = 5 + 0 . 0 1 5 \mathrm { R e } ^ { 0 . 8 5 6 } \mathrm { P r } ^ { 0 . 3 4 7 }
$$

Blasius proposed a correlation for the calculation of friction factor which is given by:

$$
{ \begin{array} { l l } & { f = 0 . 3 1 6 \mathrm { R e } ^ { - 0 . 2 5 } } \\ & { { \mathrm { w h e r e ~ R e } } \leq 2 \times 1 0 ^ { 4 } } \\ & { f = 0 . 1 8 4 \mathrm { R e } ^ { - 0 . 2 } } \\ & { { \mathrm { w h e r e ~ R e } } \geq 2 \times 1 0 ^ { 4 } } \end{array} }
$$

Fig.4(a) shows compatible results of the Darcy friction factor between the numerical results and the empirical minimum error between our results and the correlation of Notter-Rouse are $9 . 3 \%$ and $1 . 8 \%$ . These results demonstrate that there is a good agreement between the present numerical results and those obtained by the empirical correlations.

![](images/77697519cae1b88cb4e38b9764e94a567a1c46ed81b528033a04d2e74490ba34.jpg)  
Fig.4Validation of numerical results for smooth absorber. correlations.The maximum deviation is around $4 . 1 \%$ and the minimum relative error is about $0 . 7 \%$ . Also; Fig. 4 (b) represents the results of average Nusselt number, the maximum and the minimum deviation between our numerical results and the correlation of Gnielinski are $4 . 8 \%$ and $0 . 6 4 \%$ respectively. Additionally; the maximum and

# Theeffectof using fins inserts in the absorber tube Thermal performance analysis:

The solution of the absorber with insert fins retrieves a higher Nusselt number, compared with the smooth tube model.Fig. 5 presents the Nusselt number evolution with Reynolds number for smooth tube absorber and for the case-1 and case-2 geometries three. Nusselt number augmentations between 1.3 to 1.8 times compared to the plain tube are reported,which means that heat transfer is enhanced greatly by inserting longitudinal fins.

Fig.6 shows that the Darcy friction factor in tube with fins inserts is higher than the empty tube,and it decreases with increasing Reynolds number. This higher friction factor is the results of the swirling flow induced by the longitudinal inserts that act like an obstacle.

In order to evaluate the heat transfer enhancement, we use the thermal performance criteria defined as the ratio of the dimensionless Nusselt number and the dimensionless friction factor, given by the following relation [20]:

$$
\mathit { P E C } = \frac { \frac { N u } { \mathit { N u } _ { 0 } } } { \left( \frac { f } { f _ { 0 } } \right) ^ { \frac { 1 } { 3 } } }
$$

where the subscript O refers to the solution of the smooth tube.

![](images/3a01cdb3c0369d93a32dccbd8d3da4265b78ccaab8912afcc5367f91f5d89beb.jpg)  
Fig.5Variation of Nusselt number with Reynolds number in absorber with and without fins.

Asexpected,the thermal performance decreases with increasing $\operatorname { R e }$ ，as is clearly shown in Fig.7.An average value of $\mathrm { P E C } { \approx } 1 . 5$ is reported in the range $2 . 5 7 \times 1 0 ^ { 4 } \leq \mathrm { R e } \leq$ $2 . 5 7 \times 1 0 ^ { 5 }$ .The thermal performance of the absorber with triangular fins is slightly greater than that of tube with rectangular fins which means that the geometric parameters of fins havea noticeable effect in heat transfer enhancement.The effects of the inserts on thermal performance factor are also principally governed by the influence of the heat transfer improvement.

![](images/3e7d38c97865c8c91dd9827f391f50acf2e027a7b31d67a3f91ea9026a8aae62.jpg)  
Fig.6Variation of friction factor with Reynolds number in tube with and without fins.

![](images/b9460ea2f730cb9059ef22fcc8f5da9e726cd417dd657d0d175a218076a3610c.jpg)  
Fig.7Evaluation of thermal performance for absorber with fins inserts.

# Circumferential temperature analysis

Fig. 8 presents the temperature distribution on the middle cross-section of the absorber inner surface with and without fins when the DNI, the HTF inlet velocity and the HTF inlet temperature are $1 0 0 0 \mathrm { W / m } ^ { 2 }$ ， $1 ~ \mathrm { m / s }$ and 573 K,respectively. It can be observed that the temperature of the absorber inner wall for tube with fins is higher than the smooth tube,especially where the fins are inserted.

Also the HTF temperature is augmented by inserting thelongitudinal fins when the difference is about $1 3 \mathrm { ~ K ~ }$ Fig.9 illustrates that the temperature of the fluid on the bottom is higher than that on the top;this is due to the non-uniform heat flux distribution which is higher in the bottom.

# The effects of using nanofluids as HTF

In recent years,a lot of researchers have investigated the effects of nanofluids on the enhancement of heat transfer in thermal engineering.

According to a recent research,adding nanoparticles into a base fluid can improve the thermo-physical properties of the heat transfer fluid. The nanoparticle volume fraction has a remarkable effect on heat transfer.

In this section we compare between four kinds of nanoparticles on the performance of a parabolic trough solar collector. The nanoparticles used are:

![](images/5b440c68cc3365b7c4f7f00ce9fdc5ebbc7aa387b1a34a896ad1de26ba74a7c2.jpg)  
Fig.8Temperature distribution on the middle cross-section of the absorber inner wall.

·Oxide ceramic $( \mathrm { A l } _ { 2 } \mathrm { O } _ { 3 } )$ ， ·Metal $\mathrm { ( C u ) }$ ， · Metal carbide (Sic),

· Nonmetal (C).

The correlations used for calculating the thermophysical properties of nanofluids are provided in Appendix A.

Fig.1O represents the variation of the local Nusselt number of the four types of nanofluids used where DOWTHERMA was used as base fluid, with nanoparticle concentration $1 \%$ in volume and particle diameter of $1 3 \ \mathrm { n m }$

The enhancement of heat transfer obtained by using nanofluids is due to the higher thermal conductivity of nanoparticles than normal fluids.The type of nanoparticle influences heat transfer;Fig.1O shows the different results obtained with a number of nanofluids; the metallic nanoparticles improve heat transfer better than other nanoparticles.

Fig 11 indicates that using nanofluids as HTF in the absorber with fins can improve heat transfer greatly. It can also be seen that the influence of fins insert on heat transfer is much more significant than the presence of nanoparticles in the fluid.It should be noted that local Nusselt number and convective heat transfer coefficient decrease with axial distance.

In order, to estimate thermo-hydraulic performance of this compound technique,the criteria proposed by Bergles et al. [21] was used, considering constant pumping power as:

$$
\eta = \frac { h } { h _ { s m o o t h } }
$$

![](images/d335c335678aeeddccf661c1e5b3f09418a811dc48d93a3855cf768484b298f5.jpg)  
Fig.9Variations of temperature distributions in the absorber

![](images/b204647825cdd21a66fc73816d642703ef5407788217fb05af150750bd5a6b5d.jpg)  
Fig.10Variation of local Nusselt number in a smooth tube for $\mathrm { R e } { = } 2 5 7 0 5 6$ and $\scriptstyle \mathtt { \mathtt { 4 } } = 0 . 0 1$

![](images/dae3ffcfb031a00ed03e254ca2c4168015dd5cbe40a89ceac7643a840303765e.jpg)  
Fig.11Effect of combining fins insert and nanofluids $\scriptstyle \mathrm { R e } =$ 257056 and $\scriptstyle \mathtt { \mathtt { 4 } } = 0 . 0 1$ ：

where:h is the convective heat transfer coefficient of the enhanced tube and, $\mathrm { \ h _ { s m o o t h } }$ is the convective heat transfer coefficient of the smooth absorber.

It can be observed from Fig. 12 that, the efficiency decreases with increasing Reynolds number and the combination of both mechanisms provide better heat transfer while the enhancement factor varied from 1.3 to 1.68 when $2 . 5 7 { \times } 1 0 ^ { 4 } { \le } \mathrm { R e } \le 2 . 5 7 { \times } 1 0 ^ { 5 }$ ：

![](images/ce12185d29f0f49ff0bce7c1966f052e2bda577147143963930d4958172380d1.jpg)  
Fig.12Thermo-hydraulic performance versus Reynolds number for $\mathrm { T } _ { \mathrm { i n } } { = } 5 7 3 \ \mathrm { K }$ and $\scriptstyle \mathtt { \mathtt { 4 } } = 0 . 0 1$

# Conclusion

In this paper, we have investigated the influence of heat transfer fluid properties and receiver geometries (with and without fins insert) of parabolic trough solar collector; on the whole the following conclusions can be made based on the results presented in this work:

· The Nusselt number for absorber with fins insert varied from1.3 to 1.8 times in comparison with that of smooth tube.   
·The friction factor forabsorber with fins varied from 1.6 to 1.85 than plain tube.   
· The geometric parameters of the fins have a remarkable effect in heat transfer improvement.   
· Thermo-physical properties of nanofluid depend on physical characteristics and type of nanoparticle.   
· The Nusselt number is responsive to type of nanoparticles used.   
·The metallic nanoparticle enhances heat transfer greatly than other types.   
·Higher enhancement results from combining the two mechanisms (fins and nanofluid).   
· At similar condition,using nanofluid in absorber with fins insert offer higher heat transfer performance and higher thermo-hydraulic performance than smooth tube with base fluid.

# Appendix A

The thermo-physical properties of DOWTHERM A as a function of temperature [11]: $p r o p e r t y = a + b T + c T ^ { 2 } + d T ^ { 3 } + e T ^ { 4 } + f T ^ { 5 }$   

<html><body><table><tr><td>property</td><td>a</td><td>b</td><td>C</td><td>d</td><td>e</td><td>f</td></tr><tr><td>Density (kg/m3)</td><td>1.493E+03</td><td>-3.332E+00</td><td>1.248E-02</td><td>-2.968E-05</td><td>3.444E-08</td><td>-1.622E-11</td></tr><tr><td>Specific heat (J/kg·K)</td><td>-2.364E+03</td><td>3.946E+01</td><td>-1.703E-01</td><td>3.904E-04</td><td>-4.422E-07</td><td>1.979E-10</td></tr><tr><td>Conductivity (W/m·K)</td><td>1.856E-01</td><td>-1.600E-04</td><td>5.913E-12</td><td></td><td></td><td></td></tr><tr><td>Viscosity (Pa·s)</td><td>5.135E+00</td><td>-8.395E-02</td><td>5.971E-04</td><td>-2.409E-06</td><td>6.029E-09</td><td>-9.579E-12</td></tr></table></body></html>

Thermo-physical properties of nanofluid [22,23,24,25]   

<html><body><table><tr><td>Density</td><td>PNF =(1-Φ)pF+ΦPp</td></tr><tr><td>Specific heat</td><td>Cp,NF =(1-Φ)Cp,F +ΦCp,P</td></tr><tr><td>Viscosity</td><td>HNF 1 MF(1-）%</td></tr><tr><td>Thermal conduc- tivity</td><td>Ap+2AF-2(△F-△p) Ap+2AF+Φ(△F-△p)</td></tr></table></body></html>

# References

[1]Kalogirou S. Solar energy engineering: processes and systems. First ed. Oxford, UK: Elsevier, Academic Press; 2009.   
[2]Aggrey Mwesigye, Tunde Bello-Ochende,Josua P. Meyer. Heat transfer and thermodynamic performance of a parabolic trough receiver with centrally placed perforated plate inserts.Applied Energy; 2014.   
[3]P. Wang,D.Y. Liu,C. Xuc. Numerical study of heat transfer enhancement in the receiver tube of direct steam generation with parabolic trough by inserting metal foams.Applied Energy 102 (2013), 449-460.   
[4] Xingwang Song, Guobo Dong, Fangyuan Gao, Xungang Diao,Liqing Zheng,Fuyun Zhou. A numerical study of parabolic trough receiver with nonuniform heat flux and helical screw-tape inserts. Energy; 2014.   
[5]Z.D. Cheng, Y.L. He, F.Q. Cui. Numerical study of heat transfer enhancement by unilateral longitudinal vortex generators inside parabolic trough solar receivers. International Journal of Heat and Mass Transfer 55 (2012) 5631-5641.   
[6]Choi S.In: Siginer DA,Wang HP,editors.Enhancing thermal conductivity of fluids with nanoparticles in development and applications of non-Newtonian flows. New York: ASME; 1995.P.99-105.   
[7]T.Sokhansefat,A.B.Kasaeian, F.Kowsary. Heat transfer enhancement in parabolic trough collector tube using $\mathrm { A l } _ { 2 } \mathrm { O } _ { 3 ^ { \prime } }$ synthetic oil nanofluid;Renewable and Sustainable Energy Reviews 33(2014),636-644.   
[8]Risi Ad, Milanese M, Laforgia D. Modelling and optimization of transparent parabolic trough collector based on gas-phase nanofluids. Renewable Energy; 2013； 58: 134-139.   
[9]D.C.Wilcox, Turbulence Modeling for CFD,DCW Industries Inc.,La Canada, California,1998.   
10] ANSYS Academic research，release 14.5,ANSYS FLUENT user's guide, ANSYS Inc.   
:11]Richard L.Moore.Implementation of DOWTHERM A Properties into RELALP5-3D/ATHENA;Idaho National Laboratory, Idaho Falls (Idaho),2010   
.12]NREL.SolTrace optical modeling software.SolTrace 2012; 2012.7.9; 2012.   
[13]Pandey DK,Lee III RB,Paden J.Effects of atmospheric emissivity on clear sky temperatures. Atmos Environ 1994; 29(16): 2201e4.   
[14]Garcia-Valladares O, Velazquez N. Numerical simulation of parabolic trough solar collector: improvement using counter flow concentric circular heat exchangers. Int J Heat Mass Transfer 2009; 52: 597-609.   
[15]Mullick SC,Nanda SK.An improved technique for computing the heat loss factor of a tubular absorber. Sol Energy 1989; 42: 1-7.   
[16]Petukhov BS.In:Irvine TF,Hartnett JP,editors.Heat transfer and friction in turbulent pipe flow with variable physical properties. Advance in heat transfer, vol. 6; 1970. p. 503-564.   
[17]Incropera F,Dewitt D.Fundamentals of heat and mass transfer. $3 ^ { \mathrm { r d } }$ ed. New York: John Wiley and Sons; 1990. p. 490.   
[18]Gnielinski V.New equations for heat and mass-transfer in turbulent pipe and channel flow. Int J Chem Eng 1976; 16(2): 359e68.   
[19]R.H. Notter, M.W. Rouse,A solution to the Graetz problem-III. Fully developed region heat transferrates, Chemical Engineering Science,27(1972),2073-2093.   
[20]A.A.Abbasian Arani,J.Amani, Experimental study on the effect of TiO2-water nanofluid on heat transfer and pressure drop,Exp.Thermal Fluid Sci. 42 (2012),107.   
[21] Manglik R.M. and Bergles A.E,Heat transfer and pressure drop relation for twisted tape inserts in Isothermal tube,Journal of Heat Transfer, Vol 116,pp.881-889, 1993.   
[22]B.C.Pak,Y.I. Cho,Hydrodynamic and heat transfer study of dispersed fluids with submicron metallic oxide particles,Experimental Heat Transfer 11 (1998),151.   
[23]D.Wen,Y.Ding,Experimental investigation into convec tive heat transfer of nanofluid at the entrance region under laminar flow conditions,International Journal of Heat and Mass Transfer 47 (2004), 5181-5188.   
[24]H. Brinkman,The viscosity of concentrated suspensions and solutions,J. Chem. Phys.20 (1952),571.   
[25]J.C.Maxwell,A Treatise on Electricity and Magnetism, vol.1, Clarendon Press,1881