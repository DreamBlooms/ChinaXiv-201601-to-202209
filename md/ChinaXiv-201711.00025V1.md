# Estimation of Exhaust Gas Temperature of the Rocket Nozzle using Hybrid Approach

ManoharKarnal,Beenish Batul²

1. ZARM Institute, Bremen, Germany   
2.Luleä University of Technology, Kiruna, Sweden

In this paper the theoretical model is built for ZEpHyR (ZARM Experimental Hybrid Rocket) main engine which is being developed at ZARM institute,Bremen,Germany.The theoretical model is used to estimate the temperature of exhaust gas.The Conjugate Gradient Method(CGM) with Adjoint Problem for Function Estimation iterative technique is used to solve the Inverse Heat Conduction Problem(IHCP) to estimate the heat flux and internal wall temperature at the throat section of the nozzle.Bartz equation isused to calculate theconvective heat transfer coefficient.The exhaust gas temperature is determined using the estimated heat flux,the wall temperature at internal surface of nozze and the heat transfer coefficient.The accuracy of CGM iterative scheme to solve the IHCP is also investigated and its results are presented.

# Keywords: Nozze throat, Inverse Heat Conduction Problem,Convective heat transfer coeficient, Conjugate Gradient Method, Exhaust gas temperature.

# Introduction

In the past couple of decades, development of the hybrid rockets has increased. The major reason being hybrid rockets are much safer and easier to use than liquid and solid rockets in terms of complexity and controllability.At ZARM Institute - Univeristät Bremen,a hybrid rocket engine is being developed under the framework of theDLR-STERN(StudentischeExperimentalrakten) program by DLR,German Aerospace Center. The ZEpHyR(ZARM Experimental Hybrid Rocket) engine runs on paraffin as solid fuel and liquid oxygen as the oxidiser to power it to an altitude exceeding $1 2 \mathrm { k m }$ [6]. One of the factors significant to the success of the rocket engine depends on the nozzle. The nozzle has to survive extreme temperature and pressure,where the combustion products (exhaust gas temperature） entering the nozzle can reach up to 35ooK and a pressure of up to 35 bar. Only handful of materials are present that can withstand these conditions without active cooling. Knowledge of the total heat transferred by the combustion gases is essential in order to find the temperature distribution in a rocket nozzle.Estimation of heat flux on nozzle wall is important to achieve best possible thermal protection system.In this paper,a hybrid approach is developed to estimate the temperature of the exhaust gas of ZEpHyR engine.Here, the hybrid approach is combination of both an iterative scheme and Bartz equation to estimate the exhaust gas temperature.

# Problem Description

It is very difficult to determine the unknown boundary conditionbydirectmeasurements ina rocket nozzle as it is subjected to very high temperatures.Due to extreme environmental conditions many experimental problems arise in implanting a sensor at the internal wall surface of thenozzle,to takeheatflux or temperaturemeasurements Moreover implanting the probe at the internal surface disturbs the boundarycondition and the accuracy of the measurements.But it is easier to accurately measure the temperature at interior location or outer surface of the rocket nozzle.This type of problem is called inverse problem or Inverse Heat Conduction Problem (IHCP) and requires an iterative technique for its solution. By using inverse technique,unknown boundary condition can be estimated indirectly from the measured temperature within the nozzle.In this paper one dimensional transient heat transfer mathematical model which describes the processes involved is established to solve the IHCP in order to estimate the internal wall temperature and heat flux.

<html><body><table><tr><td colspan="5">Nomenclature</td></tr><tr><td>r</td><td>Inner radius</td><td>[m]</td><td>Pr</td><td>Prandtl number</td></tr><tr><td>r</td><td>Outer radius</td><td>[m]</td><td>M</td><td>Mach number</td></tr><tr><td>△r</td><td>Node thickness</td><td>[m]</td><td>Y</td><td>Specific heat ratio</td></tr><tr><td>Dt</td><td>Throat Diameter</td><td>[m]</td><td>J</td><td>Number of thermocouples</td></tr><tr><td>rt</td><td>Throat radius of curvature</td><td>[m]</td><td>L</td><td>Number of measurements</td></tr><tr><td>At</td><td>Throat area</td><td>[m2]</td><td></td><td>Tolerance</td></tr><tr><td>Ac</td><td>Chamber area</td><td>[m2]</td><td>0</td><td>Standard deviation</td></tr><tr><td>△t</td><td>Time difference</td><td>[s]</td><td>@</td><td>Random variable</td></tr><tr><td>T。</td><td>Initial temperature</td><td>[K]</td><td>Subscripts</td><td></td></tr><tr><td>Y</td><td>Measured temperature</td><td>[K]</td><td>0,1..</td><td>Node identifier</td></tr><tr><td>Pc</td><td>Chamber pressure</td><td>[bar]</td><td>W</td><td>Wall surface</td></tr><tr><td>C*</td><td>Characteristic velocity</td><td>[ms−1]</td><td>g</td><td>Exhaust gas</td></tr><tr><td>p</td><td>Density</td><td>[kgm3]</td><td>S</td><td>Stagnation</td></tr><tr><td>k</td><td>Thermal conductivity</td><td>[Wm-1K-1]</td><td>f</td><td>Final value</td></tr><tr><td>h</td><td>Convective heat transfer coefficient</td><td>[Wm²2K1]</td><td>e</td><td>Exact</td></tr><tr><td>q</td><td>Heat flux</td><td>[Wm2]</td><td>j</td><td>Thermocouple number</td></tr><tr><td>CP</td><td>Specific heat at constant pressure</td><td>[Jkg1K1]</td><td></td><td></td></tr><tr><td>g</td><td>Gravitational acceleration</td><td>[ms2]</td><td></td><td></td></tr><tr><td>μ</td><td>Viscosity</td><td>[Pas]</td><td></td><td></td></tr></table></body></html>

# The mathematical model

In general, the mathematical theoretical model represents the physical system and processes involved in it and also it should be able to accurately predict the system behaviour. In this research the one dimensional theoretical model of the nozzle system is built using the heat transfer theory. Transient heat transfer model is built by taking the nozzle throat as hollowcylinder of finite thickness where it is convectively heated at the internal surface and perfectly insulated at the outer surface.

Considerahollowcylinder offinite thickness with internal radius $\cdot _ { \mathrm { r _ { i } } } \cdot$ and external radius $\cdot _ { \mathrm { r _ { \mathrm { 0 } } } } ,$ and assume constant thermal properties.Cylinder is perfectly insulated at $\mathbf { r } = \mathbf { r } _ { \mathrm { { o } } }$ . A heat flux $\mathfrak { q }$ (t)' is subjected at ${ \bf r } = { \bf r } _ { \mathrm { i } }$ ,at a time $\mathfrak { t } >$ 0.Figure 1 shows the geometry of the model built.

![](images/08de165f6adba7818d9ebe7a99f6643e618f79b956d57aeb0e2460aa7a7308f5.jpg)  
Fig.1The model geometry

The mathematical formulation for the one dimensional problem considered is given in Equations (1.1) to (1.4).

$$
k \frac { 1 } { r } \frac { \partial } { \partial r } \bigg ( r \frac { \partial T } { \partial r } \bigg ) = \rho \mathbf { c } _ { p } \frac { \partial T } { \partial t } r _ { i } \leq r \leq r _ { o } , t > 0
$$

$$
T ( r , t ) = T _ { o } r _ { i } \leq r \leq r _ { o } , t = 0
$$

$$
\frac { \partial T ( r , t ) } { \partial r } = 0 \qquad r = r _ { o } , t > 0
$$

$$
k \frac { 1 } { r } \frac { \partial } { \partial r } \left( r \frac { \partial T } { \partial r } \right) = \dot { q } \left( r , t \right) r = r _ { i } , t > 0
$$

The implicit method (backward difference） is used to numerically represent the above system in finite difference form.Implicit method uses both the current and future state of the system to solve the equation. The tran sient heat transfer equations for the model are written in finite difference form for $\mathbf { \dot { n } } ^ { \prime }$ number of nodes,current time ‘i' and future time $\cdot _ { \mathrm { i } + 1 } ,$ . The equations are represented in tri-diagonal formas follows.

For the $1 ^ { \mathrm { s t } }$ node

$$
\left( - 2 a _ { r } - \frac { 1 } { \tau } \right) T _ { o } ^ { i + 1 } + 2 a _ { r } T _ { 1 } ^ { i + 1 } = - \frac { 1 } { \tau } T _ { o } ^ { i } - \frac { 2 \Delta r \dot { q } ( t ) } { k }
$$

For (n-1) node

$$
\frac { 1 } { b _ { n } } T _ { n - 2 } ^ { i + 1 } + \left( - \frac { 2 } { b _ { n } } - \frac { 1 } { \tau } \right) T _ { n - 1 } ^ { i + 1 } + \frac { 1 } { b _ { n } } T _ { n } ^ { i + 1 } = - \frac { 1 } { \tau } T _ { n - 1 } ^ { i }
$$

For ${ \mathfrak { n } } ^ { \mathrm { t h } }$ node

$$
\begin{array} { r l } & { \displaystyle 2 c _ { r } T _ { n - 1 } ^ { i + 1 } + \left( - 2 c _ { r } - \frac { 1 } { \tau } \right) T _ { n } ^ { i + 1 } = - \frac { 1 } { \tau } T _ { n } ^ { i } } \\ & { \displaystyle \tau = \frac { \alpha \Delta t } { \Delta r ^ { 2 } } ; \alpha = \frac { k } { \rho c _ { p } } ; a _ { r } = \frac { r _ { i } + \Delta r } { r _ { i } } ; } \\ & { \displaystyle b _ { n } = \frac { r _ { n } } { r _ { n } + \Delta r } ; c _ { r } = \frac { r _ { o } + \Delta r } { r _ { o } } } \end{array}
$$

# Bartz equation:

Priorknowledge of the heat transfer coefficient is required to estimate the exhaust gas temperature.To determine the heat transfer coefficient Bartz equation [[1]] is used and is as follows.

$$
h = \frac { 4 1 . 8 5 6 5 } { D _ { t } ^ { 0 . 2 } } \left( \frac { \mu ^ { 0 . 2 } c _ { p } } { \mathrm { P r } ^ { 0 . 6 } } \right) \left( \frac { P _ { c } g } { c } \right) ^ { 0 . 8 } \left( \frac { D _ { t } } { r _ { t } } \right) ^ { 0 . 1 } \left( \frac { A _ { t } } { A _ { c } } \right) ^ { 0 . 9 } \xi
$$

Where

$$
\xi = \frac { 1 } { \left[ \displaystyle \frac { T _ { w } } { 2 T _ { s } } \left( 1 + \frac { \gamma - 1 } { 2 } M ^ { 2 } \right) + \displaystyle \frac { 1 } { 2 } \right] ^ { 0 . 6 8 } \left( 1 + \frac { \gamma - 1 } { 2 } M ^ { 2 } \right) ^ { 0 . 1 2 } }
$$

The values of Prandtl number, viscosity, specific heat and characteristic velocity are obtained from NASA Chemical Equilibrium with Applications (CEA) program [5].

Using the relationship given in Equation (4） the exhaust gas temperature, $\mathrm { T _ { g } }$ can be calculated.

$$
\dot { q } ( r , t ) = h ( T _ { g } - T _ { w } )
$$

The $\cdot { \dot { q } } ( \boldsymbol { r } , t ) ^ { \flat }$ and $^ { \mathrm { \bullet } } \mathrm { T _ { w } } ^ { \mathrm { \bullet } }$ values in above equation are calculated from IHCP while the heat transfer coefficient $\mathbf { \hat { h } } ^ { \prime }$ is calculated from the Bartz equation.

Using multiple thermocouples the transient temperatures can be measured at outer surface and at various depths of the nozzle wall. The IHCP is solved using the iterative scheme called "Conjugate Gradient Method with adjoint problem for function estimation"[2] to estimate the internal wall surface temperature and heat flux,using the temperature history measured at interior locations and outer surface of the rocket nozzle.This iterative technique is used to solve for the heat flux as no prior information about its functional form is available.This method is applied to the mathematical model developed. The iterative scheme used here comes under the class of Alfanov's iterative regularization methods [3].The convective heat transfer coefficient is calculated using the Bartz equation.Using the results of the iterative method and Bartz equation, the exhaust gas temperature is calculated.

# Results and Discussion

The rocket nozzle of ZEpHyR is made of Molybdenum having ${ \bf r } _ { \mathrm { i } } = 0 . 0 1 0 3 \mathrm { m }$ and ${ \bf r } _ { \mathrm {  o } } = 0 . 0 3 0 5 \mathrm { m }$ .The properties of Molybdenum are summarized in Table 1.Five thermocouples are used to take the temperature measurements,one at outer surface and four thermocouples at varying depths of the nozzle wall as shown in Figure 2. The parameters of ZEpHyR are used to estimate the heat flux and nozzle internal wall surface temperature using CGM for ${ \mathfrak { n } } = 2 1$ nodes.The results obtained along with the data obtained from NASA CEA Program are used to solve Bartz equation to approximate the heat transfer coefficient. Using all these values the exhaust gas temperature is computed.

Table1Properties of Molybdenum[4]   

<html><body><table><tr><td>Property</td><td>Value</td></tr><tr><td>k (Wm1 K-1)</td><td>138</td></tr><tr><td>cp (Jkg1 K−1)</td><td>250</td></tr><tr><td>p (kgm³)</td><td>10220</td></tr></table></body></html>

![](images/322277cd0779f2772683af12f9e03ebf34af439f782c0792486a82b49a02a349.jpg)  
Fig.2Thermocouples placed at varying depths at nozzle throat

# Verification for accuracy of CGM method:

To demonstrate the accuracy of CGM method in estimating the heat flux and surface wall temperature at boundary, two test heat flux functions are assumed to collect the exact temperatures’ $\mathrm { ( T _ { e } ) }$ data by the direct method given by Equations（1.1） to(1.4) for the total duration of 60s.

The thermocouples used to obtain temperature measurements during rocket nozzle testing have measurement error. But the exact temperatures obtained by using the test fluxes do not include these errors. Therefore, random measurement errors are introduced in the exact temperatures obtained by direct method. This is done by Equation (5) [2].

$$
Y = T _ { e } + \omega \sigma
$$

In Equation (5), $\cdot _ { \sigma } ,$ is the standard deviation and ${ \bf \cdot } _ { \infty } ,$ is the random variable having normal distribution with zero mean and unitary standard deviation.The random variable $\mathbf { \dot { \omega } } _ { \mathrm { { o } } } ,$ is in the range $- 2 . 5 7 6 < \infty < + 2 . 5 7 6$ for the confidence bound of $9 8 . 9 \%$ . Y is the measured temperature with errors [2]. The measurement errors considered are （204号 $\cdot _ { \sigma } ,$ of 3 K,5 K and increased to $1 0 \mathrm { K }$ .The stopping criterion is calculated for each standard deviation from Equa tion (6).

$$
\varepsilon = \sigma ^ { 2 } t _ { f }
$$

The relative root means square error for heat flux $\cdot _ { \mathrm { e _ { h r m s } } } ;$ and internal wall temperature $\cdot { _ { e _ { \mathrm { t r m s } } } } ^ { , }$ is calculated to find the difference between the estimated results obtained from CGM and the actual results from direct method using test heat flux functions.The relative means square error is obtained by using the Equations(7).

$$
e _ { h r m s } = \sqrt { \frac { \displaystyle \frac { 1 } { L } \sum _ { l = 1 } ^ { L } \left[ \dot { q } ( r _ { i } , l ) - \dot { q } ^ { \prime } ( r _ { i } , l ) \right] ^ { 2 } } { \displaystyle \frac { 1 } { L } \sum _ { l = 1 } ^ { L } \left[ \dot { q } ( r _ { i } , l ) \right] ^ { 2 } } } \ast 1 0 0 \%
$$

$$
e _ { t r m s } = \sqrt { \frac { \displaystyle \frac { 1 } { L } \sum _ { l = 1 } ^ { L } \biggl [ T ( r _ { i } , l ) - T ^ { \prime } ( r _ { i } , l ) \biggr ] ^ { 2 } } { \displaystyle \frac { 1 } { L } \sum _ { l = 1 } ^ { L } \bigl [ T ( r _ { i } , l ) \bigr ] ^ { 2 } } } \ast 1 0 0 \%
$$

In Equations(7),‘L’ denotes the total number of measurements,‘ $\dot { q } ^ { \prime } \big ( r _ { i } , I \big ) ^ { \ \prime }$ and‘ $T ^ { \prime } \left( r _ { i } , I \right) ^ { \prime }$ represents heat flux and internal wall temperature respectively.

Test case I (Step heat flux): The step change in the heat flux defined in Equation (8) is used to obtain the exact temperatures from the direct problem. Random measurement errors are introduced having $\cdot _ { \sigma } ,$ of3 K,5K and $1 0 \mathrm { K }$ in the exact temperatures using Equation (8).

$$
\dot { q } = \left\{ \begin{array} { l r } { 0 } & { 0 \leq t \leq 1 0 } \\ { 5 . 5 \times 1 0 ^ { 6 } 1 0 < t \leq 5 0 } \\ { 0 } & { 5 0 < t \leq 6 0 } \end{array} \right.
$$

The comparison of results obtained for $\cdot _ { \sigma } ,$ of3K,5K and $1 0 ~ \mathrm { K }$ is shown in Figure 3,Figure 4 and Figure 5 respectively.It can be seen that with increase in the standard deviation,increase in the difference in results between the test and estimated heat flux and wall temperature also increases.The root means square errors are calculated for the three standard deviations and are summarized in Table 2.

The general trend observed from the values of Table 2 is that with increasing $\cdot _ { \sigma } ,$ ，the error increases but maximum error observed is only $0 . 0 1 1 3 \ \%$ .Studyof the results shows that the solution of the inverse heat conduction problem using CGM iterative scheme remains stable with increase in errors.

![](images/a79a5c385630474da34f7d23ce2f92a0d96b25850bcfedd9ae93571b755edaa2.jpg)  
Fig.3Comparison of test and estimated step heat flux and temperature of internal wall for $\scriptstyle \cdot _ { \sigma ^ { \prime } = 3 }$

Test case II (Ramp heat flux): The linear variation in test heat flux is used to obtain the exact temperatures from direct problem. Random measurement errors are introduced in the exact temperatures using Equation (9).

$$
\dot { q } = \left\{ \begin{array} { l l } { 1 \times 1 0 ^ { 5 } t - 1 0 0 0 } & { 0 \leq t \leq 3 0 } \\ { - 1 0 0 0 0 0 t + 6 \times 1 0 ^ { 6 } } & { 3 0 < t \leq 6 0 } \end{array} \right.
$$

The comparison of results obtained for $\cdot _ { \sigma } ,$ of $3 \mathrm { K } , 5 \mathrm { K }$ and $1 0 \mathrm { ~ K ~ }$ is shown in Figure 6,Figure 7 and Figure 8 respectively.Analysis of results show thatas the standard deviation is increased the difference in results between the test and estimated heat flux and internal wall temperature also increases.The root mean square errors are calculated for the three standarddeviationsand are summarized in Table 3.

The general trend observed from the values of Table 3 is that with increasing $\mathbf { \epsilon } ^ { \bullet } \mathbf { \sigma } ^ { \bullet }$ , the error increases but maximum error observed is only $0 . 0 5 0 5 \%$ . It canbe observed that the results of the inverse problem using CGM method remain stable as errors are increased.

![](images/c2b8d103fd104e606f21c3b89da3e550fd94e95fd7eb0142858242f3a82f8914.jpg)

Table 2Root mean square error in heat flux and internal wall temperature for step heat flux   

<html><body><table><tr><td>Standard deviation ó'</td><td>ehrms</td><td>etrms</td></tr><tr><td>6=3</td><td>0.0011</td><td>0.0011</td></tr><tr><td>6=5</td><td>0.0018</td><td>0.0019</td></tr><tr><td>6=10</td><td>0.0113</td><td>0.0084</td></tr></table></body></html>

# Estimation of exhaust gas temperature:

The exhaust gas temperature is estimated using Equation (4). The $\cdot _ { \dot { q } } ( \boldsymbol { r } , t ) ^ { \flat }$ and $\mathrm { \hbar ^ { \circ } T _ { w } } ^ { \mathrm { ~ , ~ } }$ in this equation are obtained from the results of test case II (ramp heat flux) for $ { \mathbf { \cdot } } _ { \mathbf { \sigma } }  { \mathbf { \sigma } } _ { \mathbf { \sigma } } ,$ of 3.Further, the Bartz equation is used to calculate the heat transfercoefficient‘h'.

![](images/02314bb13e0e8ed4d6a93b05340ef551c7ffeaf83929ca555a9766bcaaabdddf.jpg)  
Fig.5Comparison of test and estimated step heat flux and temperature of internal wall for $\scriptstyle \cdot _ { \sigma ^ { \prime } = 1 0 }$

![](images/b83863961ed94b30d33e8a623607e0720c8b0e582c27d180972fc638e2c124f4.jpg)  
Fig.4Comparison of test and estimated step heat flux and temperature of internal wall for $\scriptstyle \cdot _ { \sigma } \prime = 5$   
Fig.6Comparison of test and estimated ramp heat flux and

Table 3Root mean square error in heat flux and internal wall temperature for ramp heat flux   

<html><body><table><tr><td>Standard deviation‘"</td><td>ehrms</td><td>etrms</td></tr><tr><td>6=3</td><td>0.0212</td><td>0.0062</td></tr><tr><td>6=5</td><td>0.0306</td><td>0.0097</td></tr><tr><td>6=10</td><td>0.0505</td><td>0.0182</td></tr></table></body></html>

![](images/3fffacd40cca3e93c37909e02be4037c3c8670cc68f4f0a47c039cce9b848b7c.jpg)  
Fig.7Comparison of test and estimated ramp heat flux and temperature of internal wall for $\scriptstyle \cdot _ { \sigma } \prime = 5$

Fig. 8.

Exhaust gas temperature: Equation(4) is re-arranged as follows to find the exhaust gas temperature.

$$
T _ { g } = \frac { \dot { q } ( r , t ) } { h } + T _ { w }
$$

The exhaust gas temperature profile over the time of 60s is shown in Fig.10.It can be observed that the exhaust gas temperature shows almost linear variation with time which is similar to the variation of test ramp heat flux applied as shown in Fig. 6.

![](images/d6e8ed31f7b04eb60925aa9dac5bd18f96fad6ff5ba075bf65bd784c90335df0.jpg)  
Fig.8Comparison of test and estimated ramp heat flux and temperature of internal wall for $\scriptstyle \cdot _ { \sigma ^ { \prime } = 1 0 }$

Calculation of heat transfer coefficient: The heat transfer coefficient is estimated at the throat section of the nozzle by using Equation (3). The parameters required for its calculations are obtained from NASA's CEA program for the oxidizer to fuel mixture ratio of 2.1 and the chamber pressure of $3 . 5 { \times } 1 0 ^ { 6 }$ Pa.The oxidizer and fuel used in ZEpHyR are liquid oxygen and paraffin respectively. The properties and transport parameters obtained fromNASA's CEA programare listed in Table 4.

The heat transfer coefficient is calculated using the information given in Table 4 combined with the internal wall temperature obtained from CGM iterative scheme. In equation (4),heat transfer coefficient is inversely pro portional to the wall temperature and similar trends are observed in the plots of heat transfer coefficient shown in

Table 4 Properties and transport parameters of combustion gas [6]   

<html><body><table><tr><td>Property</td><td>Value</td></tr><tr><td>i (Pa s)</td><td>9.8873×10'5</td></tr><tr><td>Cp (J kg1 K1)</td><td>2028</td></tr><tr><td>Dt (m)</td><td>0.0206</td></tr><tr><td>r (m)</td><td>0.0103</td></tr><tr><td>C* (m s1)</td><td>1768.1</td></tr><tr><td>Pr</td><td>0.6196</td></tr><tr><td>Ac/At</td><td>1</td></tr></table></body></html>

![](images/4d7337e83dbaa4cba1bac48ae0ea10853c144e31d9c46ea3cfd6e314b976e440.jpg)  
Fig.9Variation in heat transfer coefficient with time and internal wall temperature

![](images/0041bc0c814854c77207be8dfeaf3e057426907505278c906729b68a26892719.jpg)  
Fig.10Estimation of exhaust gas temperature for ramp heat flux

# Conclusion

The theoretical model developed for ZEpHyR nozzle is used to obtain the temperature of exhaust gas by applying Conjugate Gradient Method iterative technique to obtain the solution for the inverse heat conduction problem and Bartz equation to compute the heat transfer coefficient respectively. Conjugate gradient numerical iterative technique used to estimate the heat flux has the advantage that it requires no prior knowledge about the functional form of boundary heat flux and has high rate of convergence.Also high accuracy of results is obtained from CGM that shows that it is less sensitive to measurement errors.The hybrid approach adopted in this research can be accurately used to estimate the exhaust gas temperature of ZEpHyR.The ZEpHyR nozzle has not reached the testing phase yet due to which measured data for temperature is not available from the thermocouples.The test heat flux used shows promising results and the technique presented here can be applied to estimate the exhaust gas temperature using the actual test thermocouple data.

# Acknowledgements

Our sincere gratitude goes to Dr. Peter Rickmers of ZARM Institute, Germany for supervising this research and for providing the required data and guidance during the project. We would also like to thank Prof.Peter von Ballmoos and Prof. Mathias Milz for their support throughout the project.

# References

[1] Bartz,D.R.,"A Simple Equation for Rapid Estimation of RocketNozzle Convective Heat Transfer Coefficient,"Jet Propulsion,Vol.27,Jan.1957,pp.49-51   
[2]M.N.Ozisik and H.R.B Orlande,Inverse Heat Transfer,Fundamentals and Applications,Taylor& Francis, New York,2000.   
[3]Alifanov,O.M.，"Solution of an Inverse Problem of Heat-Conduction by Iterative Methods",J. Eng.Phys., 26(4),471-476, 1974.   
[4] Lide,David R.,ed. (1994). "Molybdenum". CRC Handbook of Chemistry and Physics 4.Chemical Rubber Publishing Company. Cleveland, Ohio,p. 18.ISBN 0-8493- 0474-1.   
[5]NASA CEA Program.Accessed on January 15,2015   
[6]http://www.grc.nasa.gov/WWW/CEAWeb/ceaHome.htm