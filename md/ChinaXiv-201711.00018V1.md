# Analysis of Nusselt Number Distribution in Case of a Strongly Heated, Horizontal Rod

K. Grunt\*,A. Zuraw, S. Pietrowicz

Departmentof Thermodynamics,Theoryof Machinesand Thermal Systems,Wroclaw Universityof Scienceand Technology,Wybrzeze Stanislawa Wyspianskiego 27, 50-370 Wroclaw,Poland

The presented research was focused on a comparison between diffrent means of obtaining a Nusselt number distribution,in asituation where neither temperature norheat fluxdensity isconstant.Two fundamentallydiffrent measurement techniques have been utilized,alongside a CFD simulation,inorder to designate temperature distributions in a horizontal rod.Dry air under normal pressure,regarded as a perfect gas,was chosen as the working fluid,whereas therod’scross-section was restricted to a ring.In this scenario heat exchange between the rod and the fluid is driven predominantly by natural convection, with a slight impact of thermal radiation,particularlyat temperatures approaching the top end ofthe available range.Temperature margins achieved at the heated end of the rod ranged from 60K up to 15oK,resulting in local Rayleigh numbers falling in-between $6 . 0 \mathrm { x } 1 0 ^ { 3 }$ and $2 . 6 \mathrm { x } 1 0 ^ { 4 }$ .Reconstruction of Nusselt numbers from a discrete temperature distribution was possible thanks to a dedicated method implemented using a Scilab script.A segregated,steady-state solver based on the SIMPLE scheme was utilized for the purpose of numerical simulations on the fluid side, whereas a heat conduction equation was solved over solid domain in the considered conjugated heat transfer problem. A corresponding setof empirical data has been obtained,using both resistance temperature detectors and athermal imaging camera,both forthe sake of numerical model validation and comparison of individual methods.The Nusselt numbers resulting from each approach were compared against values computed using available correlations valid for horizontal configuration.

# Keywords: natural convection,conjugate heat transfer, SIMPLE scheme,thermal imaging,horizontal roc

# Introduction

Even though heat transfer froma straight rod isarather straightforward phenomenon,it bears a significant practical importance. This feature owes greatly to the similarities it shares with heat transfer from multiple kinds of fins,commonly found in thermal enginering practice. Not only the physical mechanisms are analogous in both cases,but also their mathematical descriptions are almost identical,at least at the most fundamental level. Therefore, it appears to be solid testing grounds for a number of techniques aimed at heat transfer enhancement through surface area extension.

Natural convection around rods and cylinders was investigated by a number of researchers.The most popular studies concern temperature distribution and Nusselt number analysis.Atayilmaz [1] numerically and experimentally studied surface temperature distribution of a cylinder as a function of incination angle. Temperature distribution along a rod can be analyzed in various orientations as well: vertical (e.g. Basit et al. [2],Nagendra et al. [3]), horizontal (e.g. Atmane et al. [4], Liao and Lin [5])

<html><body><table><tr><td colspan="4">NOMENCLATURE</td></tr><tr><td>h</td><td>heat transfer coefficient</td><td>0=T-TA</td><td>temperature margin</td></tr><tr><td>P</td><td>perimeter</td><td>0=0/00</td><td>dimensionless temperature</td></tr><tr><td>m</td><td>coefficient</td><td>=x/L</td><td>dimensionless length</td></tr><tr><td>TA</td><td>ambient temperature</td><td></td><td>dimensionless coefficient</td></tr></table></body></html>

or as previously mentioned - at differing inclination (e.g.Heo and Chung [6],Al-Urabi and Salaman [7], Chand and Vir [8]).

Arrangement of surroundings was proven to play a significant role in establishing a thermal equilibrium in scenarios where heat transfer is driven predominantly by natural convection. Liao and Lin [5] analyzed this phenomenon using a horizontal cylinder located in a square enclosure. Different types of enclosures were also accounted for by Wang et al. [9] and Lee et al.[1O]. Most of the authors also took into consideration distribution of the Nusselt number. In the presented article heat transfer involving a horizontal rod is discussed, thusthe semi-empirical formulas for Nusselt number developed by Morgan [11],Fand et al.[12] and Churchill and Chu [13] were chosen for comparison.

# Theory

# Analyticframework

The basic theory of heat transfer in a straight, horizontal rod is based on the local equilibrium hypothesis followed by the energy conservation principle in a differential form.Considera said rod with a constantheat flux delivered to one of its ends.Given that the rod's diameter remains small in comparison with its length, temperature should be approximately uniform over its cross-sections, rendering the case a 1-D problem.

At any given distance $x$ measured from the beginning of the rod there is an infinitesimal slice of length dx perpendicular to the rod's axis.It experiences three distinc tive heat fluxes on its boundaries: conductive flux at one end $Q _ { \mathrm { x } }$ , its counterpart at the other $Q _ { \mathrm { x + d x } }$ and a total outgoing heat flux at its outer surface $\mathcal { Q } _ { \mathrm { o u t } }$ .The energy conservation principle states that:

$$
( { \dot { Q } } _ { x } - { \dot { Q } } _ { x + d x } ) - d { \dot { Q } } _ { o u t } = 0
$$

Application ofFourier's and Newton's laws:

$$
\dot { \mathcal { Q } } _ { x } = - k _ { s } A \frac { d \theta } { d x } , d \dot { \mathcal { Q } } _ { o u t } = h P d x \theta
$$

leads to the following form of the governing ordinary differential equation:

$$
\frac { d ^ { 2 } \theta } { d x ^ { 2 } } - \biggl ( \frac { h P } { k _ { s } A } \biggr ) ^ { 2 } \theta = 0
$$

which may be written in a dimensionless form, using

$\scriptstyle \xi = x / L$ ， $\scriptstyle { \Theta = \theta / \theta _ { 0 } }$ and $\scriptstyle { m = h P / k _ { s } A }$ ,as:

$$
\frac { d ^ { 2 } \Theta } { d \xi ^ { 2 } } - ( m L ) ^ { 2 } \Theta = 0
$$

The above equation possesses an analytic solution of the following form:

$$
\Theta \left( \xi \right) = C _ { 1 } e ^ { m L \xi } + C _ { 2 } e ^ { - m L \xi }
$$

In particular, a Dirichlet type boundary condition applied at the heated end: $\scriptstyle { \Theta _ { 0 } = 1 }$ and a Neumann type boundary condition at the other end: $q _ { 1 } { = } 0$ lead to a relatively simple form of temperature distribution:

$$
\Theta ( \xi ) = \frac { \cosh \bigl ( m L \bigl ( 1 - \xi \bigr ) \bigr ) } { \cosh \bigl ( m L \bigr ) }
$$

The main deficiency of the above framework lays in omission of the radiative heat transfer. This problem may be overcome by perceiving the total heat transfer coefficient $h$ asa sum of convective and radiative contributions:

$$
h = h _ { C } + h _ { R }
$$

where:

$$
h _ { R } = \varepsilon ( T ) \sigma \big ( T + T _ { A } \big ) \big ( T ^ { 2 } + T _ { A } ^ { 2 } \big )
$$

Although this approach allows for retainment of the solution's form of(5),it only does so under an assumption of a constant $h _ { \mathrm { R } }$ .Keeping in mind that it constitutes a $3 ^ { \mathrm { r d } }$ order polynomial of local temperature, this approach is only valid in case of a very small temperature difference $\theta$ or unique materials characterized by an emissivity $\varepsilon ( T )$ counteracting the temperature dependence.

On the other hand, utilization of the total heat transfer coefficient defined in（7)is suitable both for application in a simple 1-D numerical scheme and elimination of radiative contribution from empirical results.Hence,numerical methods have been rendered a useful tool in analysis of the presented conjugate heat transfer problem. Furthermore, they allow to conduct an analysis in case of a more complex geometry, where experimental methods fail either due to limited resolution or accessibility.

# Average Nusselt number at varying T and q

In order to obtain a Nusselt number distribution along the rod's length from a discrete set of empirical data,a certain numerical method has been applied.It's based on the $2 ^ { \mathrm { n d } }$ order central differencing scheme, although higher order numerics could be employed, given a denser distribution of temperature.Using the previously introduced notation one gets:

$$
{ \bf \Psi } ( m L ) ^ { 2 } = \frac { h P } { k _ { s } A } L ^ { 2 } = \frac { h D } { k _ { f } } \frac { k _ { f } } { k _ { s } } \frac { 4 D } { D ^ { 3 } } L ^ { 2 } = N u \frac { k _ { f } } { k _ { s } } \zeta ^ { 2 }
$$

where $\zeta ^ { 2 }$ constitutes a coefcient describing the geometry of the rod and equals for a full rod: $\scriptstyle \zeta _ { 1 } ^ { 2 } = 4 L ^ { 2 } / D ^ { 2 }$ whereasforacylindricalpipeoneobtains: $\zeta _ { 2 } ^ { 2 } { = } 4 L ^ { 2 } / ( D _ { \mathrm { \ o u t } } ^ { 2 } { - } D _ { \mathrm { \ i n r } } ^ { 2 } )$ .On the other hand,the dimensionless coefficient $\left( m L \right) ^ { 2 }$ equals to the governing equation:

$$
( m L ) ^ { 2 } = \frac { d ^ { 2 } T } { d x ^ { 2 } } \frac { L ^ { 2 } } { T - T _ { A } }
$$

Equating the right-hand sides of(9) and (1O) yields:

$$
N u { = } \frac { d ^ { 2 } T } { d x ^ { 2 } } \frac { L ^ { 2 } } { T { - } T _ { A } } \frac { k _ { s } } { k _ { f } } \frac { 1 } { \zeta ^ { 2 } }
$$

Let us assume, for the sole sake of simplicity, that a temperature distribution obtained from a set of linearly distributed values is given,yielding the spatial interval between each pair of neighbouring measurement points equal to $\scriptstyle \Delta x = L / n$ .Utilization of the 2nd order central differencing scheme implies that the second derivative at any point, excluding the boundaries, equals:

$$
\frac { { { d ^ { 2 } } T } } { { d { x ^ { 2 } } } } = \frac { { T _ { i + 1 } } - 2 { T _ { i } } + { T _ { i - 1 } } } { { { \left( \Delta x \right) } ^ { 2 } } }
$$

whichsubstituted into(11)leads to:

$$
N u _ { i } = \frac { k _ { s } } { k _ { f . i } } \frac { n ^ { 2 } } { \zeta ^ { 2 } } \frac { T _ { i + 1 } - 2 T _ { i } + T _ { i - 1 } } { T _ { i } - T _ { A } }
$$

or using the dimensionless temperature $\boldsymbol { \Theta }$

$$
N u _ { i } = \frac { k _ { s } } { k _ { f . i } } \frac { n ^ { 2 } } { \zeta ^ { 2 } } \Bigg ( \frac { \Theta _ { i + 1 } + \Theta _ { i - 1 } } { \Theta _ { i } } - 2 \Bigg )
$$

At the boundaries the $2 ^ { \mathrm { n d } }$ order right- or left-sided differencing scheme may be used instead.Finally, one obtains an average Nusselt number from:

$$
N u _ { A \nu } = \int \displaylimits _ { 0 } ^ { 1 } N u \bigl ( \xi \bigr ) d \xi \cong \frac { 1 } { n } \sum _ { i = 1 } ^ { n } N u _ { i }
$$

# Experimental set-up

All of the experiments have been conducted in a darkened, enclosed chamber, in order to efface the radiative impact of surrounding equipment and maintain steady conditions for natural convection.Dry air under atmospheric pressure was utilized as the working fluid.

# Experimental apparatus

Experimental apparatus consists of a straight rod,a cartridge heater, a power supply system,a data acquisition system， temperature sensors and appropriate harnessing. Reduction of rod's thermal capacity leads to a faster achievement of a steady-state,thus an aluminium pipe has been used instead of a full rod. The pipe measures $1 8 \mathrm { m m }$ in outer diameter, $1 6 \mathrm { m m }$ in inner diameter and $2 8 0 \mathrm { m m }$ inlength.As shown in Figure 1,the necessary heat flux is supplied to the rod from the cartridge heater. Temperature measurements were performed using $\mathtt { P t l 0 0 }$ resistance detectors glued to the outer surface of the rod and a single thermocouple located inside the heater. The acquisition system collects the data with a frequency equal to $0 . 2 \mathrm { H z }$ . The presented set-up was accompanied by a thermal imaging camera,which provided analternative measurement method.

![](images/a02c67e9333cc52cdb6a746e2481a9ec3379a3974f050c7177288f8e4ed5ea01.jpg)  
Fig.1Scheme of the experimental apparatus

# Measurement's accuracy

The accuracy of the temperature measurements is determined mainly by the accuracy of the $\mathtt { P t l 0 0 }$ sensors, data acquisition modules and sensors'installation method The accuracy of the $\mathtt { P t l 0 0 }$ sensors depends on local temperature and was specified by their producer - under achieved conditions it does not exceed $\pm 0 . 4 \mathrm { K }$ . The data acquisition system is characterized by an accuracy of $\pm 0 . 1 5 \mathrm { K }$ . In order to account for the temperature gradient within the thermal baffle of glue which fixes sensors to the rod,an additional margin equal to $- 0 . 3 \mathrm { K }$ has been added.The sensors are distributed along the rod's length in a linear fashion with positioning accuracy equal to $\pm 1 \mathrm { m m }$

# Numerical set-up

The numerical methods utilized in the presented research may be divided into two groups -a CFD simulation of conjugate heat transfer involving the rod and surrounding fluid and an in-house utility based on equation (14), serving the purpose of post-processing temperature distributions obtained using individual means.An open-source solver used for the former part was chtMultiRegionSimpleFoam,which constitutes a part of the OpenFOAM3.0.1 toolbox.

# Topology,mesh and boundary conditions

In order to reduce the computational effort required to obtain meaningful results,a relatively simple topology has been chosen.It consists of a cuboid cut throughout bya cylinder representing the insides of the pipe,which were not taken into consideration in this analysis.The division into fluid and solid domains was performed on a supplied mesh using the topoSet utility, since individual regions are not singled out prior to a simulation run.

The structured mesh generated using blockMesh utility consist of 24 blocks and 340032 hexaedral elements, 4032 of which form the solid domain.A total of 3o512 external faces compose 7 main boundaries- six walls of the cuboid and the pipe's inner wall.All of them but the one at rod's insulated end were assigned wall type BCs with no-slip for velocity field and either fixed temperature or zero normal gradient (rod's inner wall) for temperature field. The last one was treated as a symmetry plane regarding all the variables.The rod was assigned boundary conditions analog ous to those used to obtain analytic solution given by(6) - fixed temperature at the heated end and a symmetry type BCat the other end.

# Numerical schemes

The chtMultiRegionSimpleFoam is a solver which combines the functionality of buoyantSimpleFoam and heatConductionFoam for the fluid and solid regions,respectively. BuoyantSimpleFoam,on the other hand,constitutes a SIMPLE based,steady-state solver for buoyant flows of compressible fluids.

In order to take the rod's irradiation into account, the viewFactor model was utilized with an appropriate coupling at the solid-fluid interface.Even though the convectively induced flow around the rod is purely laminar, the $\mathbf { k } { - } \mathbf { \mathcal { E } }$ turbulence model was incorporated as well It owes to the fact, that height of the domain is sufficient for corresponding Reynolds number to fall into the transition regime.

Among the most notable numerical schemes one should point out a bounded Gauss upwind scheme for most of the divergence terms and a Gauss linear scheme for the gradient terms.

# Data processing

Nusselt number distributions and resulting average values were computed in all cases using a dedicated Scilab script.Transport properties of air were obtained separately at each given point on the basis of a representative temperature, constituting an arithmetic mean of local and ambient temperatures.The polynomial interpolation utilized for processing of the thermograms was based on the least squares method.

# Results and Discussion

Three values of wattage were taken into consideration:

17W, 33W and 5oW. Approximately only one-third of the dissipated power is transported into the rod, due to losses at insulation connecting the rod to the frame.For this reason a Dirichlet type BC was supplied to the numerical calculations.

# Empirical results

Two sets of data were gathered at each of the 3 power levels - one obtained using RTDs and the other resulting from thermal imaging.Even though both are discrete, there is huge gap between spatial resolution of these methods,ranging up to two orders of magnitude.There are only 8 sensors mounted to the rod as opposed to about 300 pixels in the camera's measurement area.Thus, the results originating from the optical method are presented using continuous lines.

The temperature distributions obtained on empirical basis are presented in Figure 2.As anticipated,values from RTDs maintain a proportional difference and a good agreement with data from thermal imaging(TI), post-processed with an assumption of constant emissivity $\scriptstyle \varepsilon = 0 . 9 6$ . The data set characterized by $\scriptstyle { \varepsilon = 0 . 6 0 }$ is presented solely for comparison, since the value was used in a series of numerical simulations.What's troubling here is the systematic error at the $2 ^ { \mathrm { n d } }$ sensor from the heated end. It may be contributed to irradiation from the rest of the experimental apparatus,which also reaches a considerably high temperature.Nevertheless,conducting thrustworthy measurements at this point was impossible, hence causing serious issues in context of computing an average Nusselt number from this set of data.

![](images/554264396fbf8610c695e13c992a04b7be564d70e77fc6197d181d7510b6e6a0.jpg)  
Fig.2Temperature distributions along the rod's length resulting from experiment

Even though temperature distributions resulting from thermal imaging seem smooth, the spatial resolution of this method is relatively high,yielding differences between subsequent values of the same order of magnitude as measurement's accuracy. What follows is that the 2nd derivative with respect to spatial coordinate,computed accordingly to(12),is highly unstable.In order to overcome this problem a ${ 5 } ^ { \mathrm { t h } }$ order polynomial interpolation has been utilized to compute the derivative and so Nu Results of this approach, together with Nusselt numbers computed from the RTD measurements on the basis of (14),are presented in Figure 3.

It is clearly visible that the utilized polynomials were not capable of an accurate designation of Nusselt number distribution,particularly in the cases of medium and high wattage.Although higher order polynomials brought satisfactory results in terms of qualitative agreement over middle parts of individual distributions,they yielded very high discrepancies at the ends.Thus,they have been rendered inappropriate for designation of average Nusselt number,unless an arbitrary cut-off of distribution ends would be conducted.

In spite of the described difficulties,approximation procedure returned satisfactory results in the 17W case, both in qualitative and quantitative terms.The results achieved under an assumption of emissivity $\scriptstyle { \varepsilon = 0 . 9 6 }$ closely resemble those obtained using RTDs.This feature owes to a smoother initial temperature distribution obtained in this case,thus indicating that the problems with polynomials originate from the technical aspects of the experimental set-up,rather than from the methoditself.

![](images/32ca93e085586105d5e87bf2b7db8a2869bb45f73b798b9110aec64a6671e7d4.jpg)  
Fig.3Nusselt number distributions along the rod's length resulting from experiment

# Numericalresults

The choice of boundary conditions for the numerical simulations reflects the conducted experimental work. Two different sets of data were gathered,with and without inclusion of a model responsible for radiative heat transfer.A flow pattern typical for the utilized configuration is presented in Figure 4,alongside rod's temperature.

The temperature distributions obtained under absence of radiation (NR) are milder than their counterparts resulting from simulations conducted using the viewFactor model (VF),as shown in Figure 5.It is, without a doubt, a consequence of the associated decrease of heat flux density, since the impact of radiation is usually considerable at this range of temperature margin $\theta$

Omission of radiative heat transfer resulted in an overestimation of the achieved temperature distribution. Regrettably, at emissivity $\scriptstyle { \varepsilon = 0 . 9 6 }$ temperature is inconsistent with the RTD measurements,likewise.Artificial reduction of $\varepsilon$ finally brought satisfactory agreement and an accurate estimation of average Nu.This feature possibly owes to some minor flaws in the numerical set-up or the viewFactor model itself. On the contrary, Nu distributions obtained using this approach are relatively accurate. The characteristic teeth shown in Figure 6 result from agglomeration procedure utilized by the viewFactor model.

![](images/e600d153cd9997dd145beb89450c1749da4b6231133e34b48fcef1a6eb4b1db7.jpg)  
Fig.4Velocity streamlines originating from the mid-plane and rod's temperature in the 5oWNR case

Thus,their amplitude and simultaneously length may be reduced at the expense of required computational effort.

# Comparison

Four different types of semi-empirical correlations, valid for natural convection at $R a$ not exceeding ${ 1 0 } ^ { 9 }$ were taken into consideration. The one developed by Morgan[11] implies that $N u$ is a function of $R a$ exclusively:

$$
N u = 0 . 4 8 R a ^ { 0 . 2 5 }
$$

Fand [12] et al.postulate that $P r$ should be incorporated with a different exponent than $G r$ ：

$$
N u = 0 . 4 7 4 R a ^ { 0 . 2 5 } \operatorname* { P r } ^ { 0 . 0 4 7 }
$$

![](images/b17a545635c2555598776d2acd5842d460775777b8cac1b3dad4bf62dbce8fc5.jpg)  
Fig.5Temperature distributions along the rod's length re sulting from numerical simulations

![](images/fdaae631814564f2663d68ef484b862fd898373fc3e45c42d20b4f589df823ec.jpg)  
Fig.6Nusselt number distributions along the rod's length resulting from numerical simulations

Oosthuizen assumes that $N u$ depends only on $G r$ neglecting the impact of $P r$ completely:

$$
\mathit { N u } = 0 . 4 2 G r ^ { 0 . 2 5 }
$$

Finally, a general correlation given by Churchill and Chu [13] was chosen for the comparative analysis:

$$
N u ^ { 0 . 5 } = 0 . 5 4 + 0 . 3 9 \left( R a \left( 1 + \left( \frac { 0 . 5 5 9 } { \mathrm { P r } } \right) ^ { \frac { 9 } { 1 6 } } \right) ^ { - \frac { 1 6 } { 9 } } \right) ^ { 0 . 1 6 }
$$

Average Nusselt numbers computed on the basis of each of the above formulas,using temperature distributions obtained through the RTD measurements to find transport properties,are summarized in table 1, beside the empirical and numerical results.

First of all, the average Nu resulting from thermal imaging under an assumption of $\scriptstyle { \varepsilon = 0 . 6 0 }$ stand out as imprecise,which is natural given their comparative purpose. Secondly, the other set of data obtained using the optical method is highly accurate in comparison with semiempirical correlations,although it does not follow the expected pattern of $N u$ increase accordingly to the dissipated power. This could be a result of difficulties encountered at the higher levels of wattage,associated with increasing roughness of temperature distribution.

The values obtained using RTDs are defective, due to the problems with appropriate radiative insulation of the sensors.Nevertheless, they do not bring a severe underestimation.Hence,the presented method of Nu distribution reproduction seems promising in context of small, discrete data sets.Furthermore,the results are expected to be improved, given an increase in spatial resolution.

Finally, the numerical simulations constitute a precise and reliable source of knowledge about Nu distributions in the considered case.Not only they bring relatively stable results but also allow for a direct assessment of the radiative contribution to the overall heat transfer coefficient.Moreover, they are suitable for complex geometries,where neither of the presented experimental techniques is applicable. On the other hand, they require both an initial validation and precise knowledge of emissivity of the considered surfaces as a function of temperature.

# Conclusions

Even though direct sensor measurements constitute the most dependable method of obtaining a temperature distribution in terms of absolute values,they suffer greatly from limited spatial resolution. Thermal imaging technique provides means to overcome this difficulty at the expense of achieving measurement accuracy of the same order of magnitude as difference between subsequent values, leading to an unstable $2 ^ { \mathrm { n d } }$ partial derivative with respect to coordinates.Fortunately,this issue could be mitigated using a polynomial approximation of the temperature distribution,which leads to a continuous and more accurate distributionof Nu.

Table1 Comparison between empirical, numerical and semi-empirical results   

<html><body><table><tr><td rowspan="2">Wattage (W)</td><td colspan="3">NuAv empirical</td><td colspan="3">NuAv numerical</td><td colspan="4">NuAv semi-empirical</td></tr><tr><td>RTD</td><td>TIε=0.60</td><td>TIε=0.96</td><td>NR</td><td>VFε=0.60</td><td>VF ε=0.96</td><td>Morgan</td><td>Fand et al.</td><td>Oost-huizen</td><td>Chur-chill</td></tr><tr><td>16.6</td><td>3.106</td><td>2.044</td><td>5.085</td><td>3.830</td><td>5.371</td><td>6.350</td><td>4.912</td><td>4.776</td><td>4.666</td><td>4.376</td></tr><tr><td>33.2</td><td>3.319</td><td>2.346</td><td>4.775</td><td>4.097</td><td>5.762</td><td>6.771</td><td>5.443</td><td>5.293</td><td>5.174</td><td>4.851</td></tr><tr><td>49.7</td><td>3.945</td><td>2.406</td><td>4.377</td><td>4.200</td><td>6.003</td><td>7.064</td><td>5.652</td><td>5.495</td><td>5.374</td><td>5.039</td></tr></table></body></html>

Numerical methods share some strengths and weaknesses with thermal imaging, despite belonging to a completely different group of techniques. The spatial accuracy of virtual measurements may be easily adjusted up to values typical for the optical method.Furthermore,both methods require a priori knowledge of emissivity of the considered surface as a function of temperature.Nevertheless, the obtained temperature distribution is rather smooth,allowing for a direct computation of $N u$ ，instead of using a fitted curve.However, the numerical methods should not be applied without an appropriate validation, including a parameter sensitivity analysis.

All in all, thermal imaging technique maintains a compromise between provided accuracy and time effort required to set up.Under circumstances where its application becomes tedious, numerical methods may prove very handy It should be kept in mind though, that they have to be employed in a careful manner in order to bring quantitatively meaningful results.These methods seem superior to sensor measurements in context of an indirect identification of localNusselt number. The latter still constitutes a sound alternative,particularly whenever thermal imaging is impossible to conduct and numerical methods become unreliable.

# References

[1]Atayilmaz,S O,2011,Experimental and Numerical Study of Natural Convection Heat Transfer from Horizontal Concentric Cylinders,International Journal of Thermal Sciences,50,pp.1472-1483.   
[2]Basit,MA,Rafique,M,Chughtai,IR,Inayat,MH,2007, Computer simulation of natural convection heat transfer from an assembly of vertical cylinders of PARR-2,Applied Thermal Engineering,27,pp.194-201. [3]Nagendra,H R,Tirunarayan,M A,Ramachandram,A, 1970,Free convection from vertical cylinder with uniform heat flux, Journal of Heat Transfer, 92,pp.191- 194.   
[4]Atmane,M A,Chan,V S S,Murray,D B,2003,Natural convection around a horizontal heated cylinder: The effects of vertical confinement, International Journal of Heat and Mass Transfer, 46, pp. 3661-367. [5]Liao,Chuan-Chieh,Lin,Chao-An,2014,Transitions of Natural Convection Flows in a Square Enclosure with a Heated Circular Cylinder, Applied Thermal Engineering, 72, pp. 41-47. [6]Heo,J H,Chung,B J,2O12,Natural convection heat transfer on the outer surface of inclined cylinders, Chemical Engineering Science,73, pp. 366-372.   
[7]Al-Urabi, M, Salman, Y K,1980, Laminar natural convection heat transfer from an inclined cylinder,International Journal of Heat and Mass Transfer,23,pp.45-51. [8]Chand,J,Vir, D,1980,A unified approach to natural convection heat transfer in the laminar region from horizontal and inclined cylinders,Letters in Heat and Mass Transfer,7, pp. 213-225.   
[9]Wang, Q X,Lei,HY,Wang,S X,Dai, C S,2014,Natural convection around a pair of hot and cold horizontal microtubes at low Rayleigh numbers,Applied Thermal Engineering, 72, pp. 114-119.   
[10]Lee,JM, Ha,MY, Yoon,H S,2010,Natural convection in a square enclosure with a circular cylinder at different horizontal and diagonal locations,International Journal of Heat and Mass Transfer,53,pp. 5905-5919.   
[11]Morgan,V T,1975,The overall convective heat transfer from smooth circular cylinders,Advanced Heat Transfer, 11, pp. 199-212.   
[12]Fand,R M,Morris,E W,Lum,M,1977,Natural convection heat transfer from horizontal cylinders to air, waterand silicone oils for Rayleigh Numbers between $3 \times$ $1 0 ^ { 2 }$ and $2 \times 1 0 ^ { 7 }$ ，International Journal of Heat and Mass Transfer 20 (11), pp.1173-1184.   
[13]Churchill, S W, Chu, HH S,1975,Correlating equations for laminar and turbulent free convection from a horizontal cylinder, International Journal of Heat and Mass Transfer,18 (9),pp.1049-1053.