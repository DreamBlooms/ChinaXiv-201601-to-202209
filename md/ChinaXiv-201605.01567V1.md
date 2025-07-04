# STANDING SAUSAGE MODES IN NONUNIFORMMAGNETIC TUBES: AN INVERSION SCHEME FORINFERRINGFLARELOOPPARAMETERS

Shao-Xia Chen1

Bo Li1

bbl@sdu.edu.cn   
Ming Xiong²   
Hui Yu1   
and   
Ming-Zhe Guo1

# ABSTRACT

Standing sausage modes in flare loops are important for interpreting quasiperiodic pulsations (QPPs) in solar flare lightcurves. We propose an inversion scheme that consistently uses their periods $P$ and damping times $\tau$ to diagnose fare loop parameters. We derive a generic dispersion relation governing linear sausage waves in pressure-less straight tubes, for which the transverse density inhomogeneity takes place in a layer of arbitrary width $l$ and is of arbitrary form. We find that $P$ and $\tau$ depend on the combination of $[ R / v _ { \mathrm { A i } } , L / R , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ . where $R$ is the loop radius, $L$ is the looplength, $v _ { \mathrm { A i } }$ is the internal Alfvén speed, and $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ is the density contrast. For all the density profiles examined, $P$ and $\tau$ experience saturation when $L / R \gg 1$ ，yielding an inversion curve in the $[ R / v _ { \mathrm { A i } } , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ space with a specific density profile when $L / R$ is sufficiently large. When applied to a spatially unresolved QPP event, the scheme yields that $R / v _ { \mathrm { A i } }$ is the best constrained,whereas $l / R$ corresponds to the other extreme. For spatially resolved QPPs,while $L / R \gg 1$ cannot be assumed beforehand,an inversion curve remains possible due to additional geometrical constraints. When a spatially resolved QPP event involves another mode, as is the case for a recent event, the full set of $[ v _ { \mathrm { A i } } , l , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ can be inferred. We conclude that the proposed scheme provides a useful tool for magneto-seismologically exploiting QPPs.

Subject headings: magnetohydrodynamics (MHD) - Sun: fares - Sun: corona Sun: magnetic fields - waves

# 1. INTRODUCTION

The original ideas that laid the foundation for the field of solar magneto-seismology (SMS) were put forward in the 1970s (Uchida 1970, Rosenberg 1970, Zaitsev & Stepanov 1975, see also Roberts et al. 1984). However, this field flourished only after a rich variety of lowfrequency Magnetohydrodynamic (MHD） waves and oscillations were identified with the advent of the TRACE, SOHO, Hinode, and SDO satellites (for recent reviews, see Banerjee et al. 2007, De Moortel & Nakariakov 2012， Mathioudakis et al. 2013; and also Ballester et al. 2007， Nakariakov & Erdélyi 2009, Erdélyi & Goossens 2011 for three recent topical issues). It is also indispensable to refine the theoretical understanding of the colective wave modes supported by magnetized tubes, thereby enabling one to employ the measured wave properties to infer the solar atmospheric parameters that are difficult to measure directly (e.g., Roberts 2000; Nakariakov & Verwichte 2005). Regarding its applications to the solar corona,SMS can offer such key information as the magnetic field strength in coronal loops (e.g., Nakariakov $\&$ Ofman 2001; Erdélyi & Taroyan 2008; Ofman & Wang 2008; White （20 $\&$ Verwichte 2012) and above streamer stalks (Chen et al. 2010, 2011), the magnitude of fieldaligned loop flows (Li et al. 2013; Chen et al. 2014),the temperature of loop plasmas (e.g, Marsh & Walsh 2O09), the coronal effective adiabatic index (Van Doorsselaere et al. 2011), as well as the longitudinal (Verth & Erdélyi 2008; Andries et al. 2009; Luna-Cardozo et al. 2012a) and transverse structuring (e.g., Arregui et al. 2007; Goossens et al. 2008; Yuan et al. 2015). In addition, SMS applications with torsional Alfvén waves have proven invaluable in inferring the magnetic field structure at chromospheric heights (Jess et al. 2009; Fedun et al. 2011). Likewise, Luna-Cardozo et al. (2012a) demonstrated the potential of using longitudinal waves to infer the longitudinal variation of density and magnetic feld strength in chromospheric waveguides.

Magneto-seismological applications with standing kink modes (with azimuthal wavenumber $m = 1$ ） have been a common practice since their detection with TRACE (Aschwanden et al.1999). Kink oscillations tend to experience substantial damping (e.g., Ofman $\&$ Aschwanden 2002; Ruderman & Erdélyi 2009; Verwichte et al. 2013, and references therein), which is usually interpreted in terms of resonant absorption (Ruderman & Roberts 2002,

Goossens et al. 2002, also Hollweg $\&$ Yang 1988, and the comprehensive review by Goossens et al. 2011). With this interpretation， Ruderman $\&$ Roberts (2002） and Goossens et al. (2002） suggested that the measured period $P$ and damping time $\tau$ can be used to infer the lengthscale $l$ of the density inhomogeneity across coronal loops in units of loop radius （20 $R$ . For this purpose, the largely unknown transverse density distribution was shown to be important，since its formulation has a considerable impact on $P$ and $\tau$ (Soler et al. 2013, 2014).

While kink modes have attracted much attention， sausage modes (with $m = 0$ ）are equally important in SMS.In fact, sausage modes are even more important from the standpoint of solar atmospheric heating given their stronger compressibility and ubiquity in the lower solar atmosphere (Morton et al. 2011, 2012; Freij et al. 2014; Dorotovic et al. 2014; Grant et al. 2015; Moreels et al. 2015). In addition, sausage modes are important for interpreting quasi-periodic pulsations (QPPs) in the lightcurves of solar flares (see Nakariakov （20 $\&$ Melnikov 2009, for a recent review). Two distinct regimes are known to exist, depending on the axial wavenumber $k$ along flare loops (Nakariakov $\&$ Verwichte 2005). The trapped regime results when $k$ exceeds some critical value $k _ { \mathrm { c } }$ ， where the energy of sausage modes is well confined to magnetic tubes. When $k \ < \ k _ { \mathrm { c } }$ ， the leaky regime arises and sausage modes experience apparent temporal damping by radiating their energy into the surrounding fluid (Spruit 1982; Cally 1986). It is known that $k _ { \mathrm { c } }$ depends sensitively on the density contrast between loops and their surroundings (e.g., Kopylova et al. 2007). In addition, both eigen-mode analyses (Kopylova et al. 2007; Vasheghani Farahani et al. 2014) and numerical simulations from an initial-value-problem perspective (Nakariakov et al. 20l2; Chen et al. 2015)indicated that the period $P$ of sausage modes increases smoothly with decreasing $k$ (or equivalently with increasing looplength $L$ given that $k = \pi / L$ for fundamental modes） until reaching some saturation value $P _ { \mathrm { s } }$ for sufficiently thin loops ( $R / L \ll 1$ ).Likewise,identically infinite in the trapped regime for ideal MHD fluids, the attenuation time $\tau$ decreases with decreasing $k$ before experiencing saturation at $\tau _ { \mathrm { s } }$ when $R / L \ll 1$

Magneto-seismological applications of sausage modes are possible due to their dependence on atmospheric parameters (Luna-Cardozo et al. 2012a,b). The practice based on the measured period and damping time can be illustrated by the study presented in Kopylova et al.(2007) where a step-function (top-hat） form was adopted for the transverse density distribution. The saturation values, $P _ { \mathrm { { s } } }$ and ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ ， for large density contrasts are approximately

$$
P _ { \mathrm { s } } \approx 2 . 6 2 { \frac { R } { v _ { \mathrm { A i } } } } , \ { \frac { \tau _ { \mathrm { s } } } { P _ { \mathrm { s } } } } \approx { \frac { 1 } { \pi ^ { 2 } } } { \frac { \rho _ { \mathrm { i } } } { \rho _ { \mathrm { e } } } } .
$$

As an example, Kopylova et al. (2007) examined the QPP in the radio emissions reported in McLean & Sheridan (1973)，where $P$ and $\tau / P$ were found to be $\sim 4 . 3$ secs and $\sim 1 0$ ， respectively. With the damping attributed to wave leakage, Eq.(1） then yields a density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ of $\sim 1 0 0$ , and a transverse Alfvén transit time $R / v _ { \mathrm { A i } }$ of $\sim 1 . 6 4$ secs, provided that the flaring loop in question is sufficiently thin. However, the dependence of $P$ and $\tau$ on loop parameters is substantially more involved if one goes a step closer to reality by replacing a step-function density profile with a smooth one. Even for thin loops where neither （204号 $P$ nor $\tau$ depends on looplength,both $P _ { \mathrm { s } }$ (Nakariakov et al. 2012） and $\tau _ { \mathrm { s } }$ (Chen et al. 2015) may be sensitive to the steepness, or equivalently the lengthscale, of the transverse density distribution. In mathematical terms, this means that for a given density profile,

$$
\begin{array} { r l } & { P _ { \mathrm { s } } = \displaystyle \frac { R } { v _ { \mathrm { A i } } } F \left( \frac { l } { R } , \frac { \rho _ { \mathrm { i } } } { \rho _ { \mathrm { e } } } \right) , } \\ & { \displaystyle \frac { \tau _ { \mathrm { s } } } { P _ { \mathrm { s } } } = G \left( \frac { l } { R } , \frac { \rho _ { \mathrm { i } } } { \rho _ { \mathrm { e } } } \right) . } \end{array}
$$

When only $P _ { \mathrm { { s } } }$ and $\tau _ { \mathrm { s } }$ are known as is the case for measurements without imaging capabilities, the appearance of $l / R$ no longer allows a unique pair of $[ \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } , R / v _ { \mathrm { A i } } ]$ to be deduced. Despite this,one can still constrain the combination $[ R / v _ { \mathrm { A i } } , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } , l / R ]$ by developing a scheme in much the same way that kink modes were employed (Arregui et al. 2007; Goossens et al. 2008; Soler et al. 2O14)，the only difference being that the transverse Alfvén time $R / v _ { \mathrm { A i } }$ （204号 replaces the longitudinal one $L / v _ { \mathrm { A i } }$ ：

The present study aims to develop the aforementioned scheme employing measured periods and damping times of standing sausage modes. An essential ingredient will be to establish the functions $F ^ { \prime }$ and $G$ in Eq. (2). To this end,we will derive an analytical dispersion relation (DR） governing linear sausage waves hosted by magnetized tubes with a rather general transverse density distribution. The only requirement here is that this density distribution can be decomposed into a uniform cord, a uniform external medium, and a transition layer connecting the two.However,the density distribution in the transition layer is allowed to be arbitrary, thereby making the DR applicable to a rich variety of density profiles. We note that this kind of density profiles has been extensively adopted in kink mode studies (e.g.， Soler et al. 2O14, and references therein). We further note that developing an analytical DR is important in its own right. Apart from the step-function profile (e.g., Spruit 1982; Cally 1986),analytical DRs in the cylindrical case are available only for a limited set of density profiles (Edwin & Roberts 1986, 1988; Lopin & Nagorny 2014).

This manuscript is organized as follows. Section 2 presents the derivation of the DR and our solution method. A parameter study is presented in Sect. 3 to examine how the period and damping time of sausage modes depend on tube parameters, thereby establishing our numerical scheme for inverting measurements of spatially unresolved QPPs. An extension to spatially resolved QPPs is then given in Sect. 4. Finally, Sect. 5 closes this manuscript with our summary and some concluding remarks.

# 2. MATHEMATICALFORMULATION

# 2.1. Description for the Equilibrium Tube

We consider sausage waves in a structured corona modeled by a density-enhanced cylinder with radius $R$ aligned with a uniform magnetic field $\mathbf { B } = B \hat { z }$ ，where a cylindrical coordinate system $( r , \theta , z )$ is adopted. The equilibrium density is assumed to be a function of $r$ （20 only and of the form

$$
\begin{array} { r } { \rho ( r ) = \left\{ \begin{array} { l l } { \rho _ { \mathrm { i } } , } & { 0 \leq r \leq r _ { \mathrm { i } } = R - l / 2 , } \\ { \rho _ { \mathrm { t r } } ( r ) , } & { r _ { \mathrm { i } } \leq r \leq r _ { \mathrm { e } } = R + l / 2 , } \\ { \rho _ { \mathrm { e } } , } & { r \geq r _ { \mathrm { e } } . } \end{array} \right. } \end{array}
$$

The profile between $[ r _ { \mathrm { i } } , r _ { \mathrm { e } } ]$ is such that the equilibrium density $\rho$ decreases continuously from the internal value $\rho _ { \mathrm { i } }$ to the external one $\rho _ { \mathrm { e } }$ . The thickness of this transition layer, denoted by $l$ ， is bounded by $0$ and $2 R$ . The former represents the steepest profile of a step-function form,whereas the latter corresponds to the least steep case.

While our analysis is valid for arbitrary prescriptions of $\rho _ { \mathrm { t r } }$ , a number of choices have to be made to evaluate quantitatively the efects of equilibrium density profiles. To this end, we select the following profiles,

$$
\begin{array} { r } { \rho _ { \mathrm { t r } } ( r ) = \left\{ \begin{array} { l l } { \rho _ { \mathrm { i } } - \frac { \rho _ { \mathrm { i } } - \rho _ { \mathrm { e } } } { l } \left( r - R + \displaystyle \frac { l } { 2 } \right) , } & { \mathrm { l i n e a r , } } \\ { \rho _ { \mathrm { i } } - \frac { \rho _ { \mathrm { i } } - \rho _ { \mathrm { e } } } { l ^ { 2 } } \left( r - R + \displaystyle \frac { l } { 2 } \right) ^ { 2 } , } & { \mathrm { p a r a b o l i c , } } \\ { \rho _ { \mathrm { e } } - \frac { \rho _ { \mathrm { e } } - \rho _ { \mathrm { i } } } { l ^ { 2 } } \left( r - R - \displaystyle \frac { l } { 2 } \right) ^ { 2 } , } & { \mathrm { i n v e r s e - p a r a b o l i c , } } \\ { \displaystyle \frac { \rho _ { \mathrm { i } } } { 2 } \left[ \left( 1 + \displaystyle \frac { \rho _ { \mathrm { e } } } { \rho _ { \mathrm { i } } } \right) - \left( 1 - \displaystyle \frac { \rho _ { \mathrm { e } } } { \rho _ { \mathrm { i } } } \right) \sin \frac { \pi \left( r - R \right) } { l } \right] , } & { \mathrm { s i n e . } } \end{array} \right. } \end{array}
$$

The profiles labeled linear,parabolic and sine have been examined in substantial detail in the context of standing kink modes (Soler et al. 2013, 2014). An additional profile,labeled inverse-parabolic,is added to make the list more comprehensive in that it naturally complements the parabolic one. Figure 1 illustrates the $r$ -dependence of the chosen equilibrium density profiles. For illustration purposes, $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ is chosen to be 100,and $l / R$ is chosen to be unity.

# 2.2. Solutions for Radial Lagrangian Displacement and Total Pressure Perturbation

Appropriate for the solar corona, we work in the framework of cold (zero- $\beta$ ）MHD,in which case sausage waves do not perturb the $z$ -component of the plasma velocity. Let $\delta v _ { r }$ denote the radial velocity perturbation,and let $\delta b _ { r }$ and $\delta b _ { z }$ denote the radial and longitudinal components of the perturbed magnetic field $\delta \mathbf { b }$ ， respectively. The perturbed total pressure is then $\delta p _ { \mathrm { t o t } } = { \bf B } \cdot \delta { \bf b } / 4 \pi = B \delta b _ { z } / 4 \pi$ given the absence of thermal pressure in the zero $\beta$ （204号 limit. Fourier-decomposing any perturbed value $\delta f ( r , z ; t )$ as

$$
\delta f ( r , z ; t ) = \mathrm { R e } \left\{ \tilde { f } ( r ) \exp \left[ - i \left( \omega t - k z \right) \right] \right\} ,
$$

one finds from linearized, ideal, cold MHD equations that

$$
\frac { 1 } { r } \left( r \tilde { \xi } _ { r } ^ { \prime } \right) ^ { \prime } + \left( \frac { \omega ^ { 2 } } { v _ { \mathrm { A } } ^ { 2 } } - k ^ { 2 } - \frac { 1 } { r ^ { 2 } } \right) \tilde { \xi } _ { r } = 0 \ ,
$$

where the prime $\mathbf { \omega } ^ { \prime } = \mathrm { d } / \mathrm { d } r$ . In addition, $\tilde { \xi } _ { r } = i \tilde { v } _ { r } / \omega$ is the Fourier amplitude of the radial Lagrangian displacement, and $v _ { \mathrm { A } } ( r ) = B / \sqrt { 4 \pi \rho ( r ) }$ is the Alfvén speed. The Fourier amplitude of the perturbed total pressure is

$$
\tilde { p } _ { \mathrm { t o t } } = - \frac { B ^ { 2 } } { 4 \pi r } \left( r \tilde { \xi } _ { r } \right) ^ { \prime } .
$$

With azimuthal wavenumber $m$ being $0$ , the equations governing linear sausage waves are free of singularities,making our derivation simpler than in kink mode studies where a treatment of singularity is necessary (Soler et al. 20l3). To be specific, the solutions to Eq. (6) in the transition layer can be expressed as a regular series expansion in $x \equiv r - R$ Let $\tilde { \xi } _ { \mathrm { t r } , 1 }$ and $\tilde { \xi } _ { \mathrm { t r } , 2 }$ denote two independent solutions,

$$
\tilde { \xi } _ { \mathrm { t r } , 1 } ( x ) = \sum _ { n = 0 } ^ { \infty } a _ { n } x ^ { n } ~ , ~ \tilde { \xi } _ { \mathrm { t r } , 2 } ( x ) = \sum _ { n = 0 } ^ { \infty } b _ { n } x ^ { n } ~ .
$$

Without loss of generality, one may choose $[ a _ { 0 } , a _ { 1 } ] = [ R , 0 ]$ and $[ b _ { 0 } , b _ { 1 } ] = [ 0 , 1 ]$ . Expanding the equilibrium density $\rho$ about $x = 0$ as well, one finds that

$$
\rho _ { \mathrm { t r } } ( x ) = \sum _ { n = 0 } ^ { \infty } \rho _ { n } x ^ { n } ,
$$

with $\rho _ { 0 } = \rho | _ { x = 0 }$ and

$$
\rho _ { n } = { \frac { 1 } { n ! } } \left. { \frac { \mathrm { d } ^ { n } \rho ( x ) } { \mathrm { d } x ^ { n } } } \right| _ { x = 0 } , \ n \geq 1 .
$$

Plugging Eq. (8) into Eq.(6) with the change of independent variable from $r$ to $x$ ,and then ordering the terms according to powers in $x$ , one finds that

$$
\begin{array} { r c l } { \chi _ { 2 } } & { = } & { \displaystyle \frac { - 1 } { 2 R ^ { 2 } } \left[ R \chi _ { 1 } + \{ \bar { \nu } \bar { \nu } \bar { \omega } ^ { 2 } R ^ { 2 } \rho _ { 1 } - \bar { k } ^ { 2 } R ^ { 2 } - 1 \} \chi _ { 0 } \right] , } \\ { \chi _ { 3 } } & { = } & { \displaystyle \frac { - 1 } { 6 R ^ { 2 } } \left[ 6 R \chi _ { 2 } + ( \bar { \nu } \omega ^ { 2 } R ^ { 2 } \rho _ { 3 0 } - R ^ { 2 } R ^ { 2 } ) \chi _ { 1 } \right. } \\ & & { \displaystyle \left. + ( \bar { \nu } \omega ^ { 2 } R ^ { 2 } \rho _ { 1 } + 2 \bar { \nu } \omega ^ { 2 } R \rho _ { 0 } - 2 \bar { \nu } ^ { 2 } R ^ { 2 } ) \chi _ { 0 } \right] , } \\ { \chi _ { 6 } } & { = } & { \displaystyle \frac { - 1 } { \pi ( \alpha - 1 ) R ^ { 2 } } \Bigg \{ ( \pi - 1 ) ( 2 n - 3 ) R \chi _ { 1 } + \pi \omega ^ { 2 } R ^ { 2 } \sum _ { \ell = 0 } ^ { \infty - 2 } \rho _ { 1 } \dots \sigma _ { \ell } } \\ & & { \displaystyle + \left[ ( \alpha - 3 ) ( n - 1 ) - k ^ { 2 } R ^ { 2 } \right] \chi _ { \ell = 2 } + 2 \bar { \nu } \omega ^ { 2 } R \sum _ { \ell = 0 } ^ { \infty - \beta _ { 1 } - \bar { \nu } \bar { \omega } \ell } } \\ & & { \displaystyle - 2 k ^ { 2 } R \chi _ { 2 - 3 } - k ^ { 2 } \chi _ { 3 - 4 } + \bar { \nu } \omega ^ { 2 } \sum _ { \ell = 0 } ^ { \infty - \bar { \nu } \bar { \omega } _ { \ell - 3 - 4 } } \chi _ { \ell } \Bigg \} , ( n \geq 4 ) } \end{array}
$$

where $\eta = 4 \pi / B ^ { 2 }$ and $\chi$ represents either $a$ or $b$

With Eq. ）at hand, the solution to Eq. (6) can be expressed as

$$
\tilde { \xi } _ { r } ( r ) = \left\{ \begin{array} { l l } { A _ { \mathrm { i } } J _ { 1 } ( \mu _ { \mathrm { i } } r ) , } & { 0 \leq r \leq r _ { \mathrm { i } } , } \\ { A _ { \mathrm { 1 } } \tilde { \xi } _ { \mathrm { t r } , 1 } ( x ) + A _ { \mathrm { 2 } } \tilde { \xi } _ { \mathrm { t r } , 2 } ( x ) , } & { r _ { \mathrm { i } } \leq r \leq r _ { \mathrm { e } } , } \\ { A _ { \mathrm { e } } H _ { 1 } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } r ) , } & { r \geq r _ { \mathrm { e } } , } \end{array} \right.
$$

where $A _ { \mathrm { i } } , A _ { \mathrm { e } } , A _ { 1 }$ and $A _ { 2 }$ are arbitrary constants, and $J _ { n }$ and $H _ { n } ^ { ( 1 ) }$ are the $n$ -th-order Bessel and Hankel functions of the first kind, respectively (here $n ~ = ~ 1$ ). In addition, $\mu _ { \mathrm { i , e } } ^ { 2 } ~ =$ （204号 $\omega ^ { 2 } / v _ { \mathrm { A i , e } } ^ { 2 } - k ^ { 2 }$ with $v _ { \mathrm { A i , e } } ^ { 2 } = B ^ { 2 } / ( 4 \pi \rho _ { \mathrm { i , e } } )$ .As discussed in Cally (1986),requiring that $- \pi / 2 <$ （204号 $\operatorname { a r g } \mu _ { \mathrm { i } }$ ， $\arg \mu _ { \mathrm { e } } \leq \pi / 2$ does not exclude any additional independent solution. Furthermore, expressing the external solution in terms of $H _ { n } ^ { ( 1 ) }$ permits a unified examination ofboth trapped and leaky waves. Indeed, the trapped regime arises when $\arg \mu _ { \mathrm { e } } = \pi / 2$ , in which case one finds that $H _ { 1 } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } r ) = - ( 2 / \pi ) K _ { 1 } ( \alpha r )$ with $\alpha = \mu _ { \mathrm { e } } / i$ being real and positive (see discussions on page 281 in Cally 1986). Now the Fourier amplitude for the total pressure perturbation can be evaluated with Eq. (7), the results being

$$
\begin{array} { r } {  { \boldsymbol { \cdot } } ) = \left\{ \begin{array} { l l } { \displaystyle - \frac { A _ { \mathrm { i } } B ^ { 2 } } { 4 \pi } \mu _ { \mathrm { i } } J _ { 0 } ( \mu _ { \mathrm { i } } r ) \ , \ } & { 0 \le r \le \frac { \pi ^ { 2 } } { 2 r ^ { 2 } } , } \\ { \displaystyle - \frac { B ^ { 2 } } { 4 \pi r } \left\{ A _ { 1 } \frac { \mathrm { d } } { \mathrm { d } x } \left[ ( x + R ) \tilde { \xi } _ { \mathrm { t r } , 1 } ( x ) \right] + A _ { 2 } \frac { \mathrm { d } } { \mathrm { d } x } \left[ ( x + R ) \tilde { \xi } _ { \mathrm { t r } , 2 } ( x ) \right] \right\} \ , } & { r _ { \mathrm { i } } \le r \le \frac { \pi ^ { 2 } } { r ^ { 2 } } , } \\ { \displaystyle - \frac { A _ { \mathrm { e } } B ^ { 2 } } { 4 \pi } \mu _ { \mathrm { e } } H _ { 0 } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } r ) \ , } & { r \ge r _ { \mathrm { e } } , } \end{array} \right. } \end{array}
$$

The expression for $\tilde { p } _ { \mathrm { t o t } }$ for the ranges $r \leq r _ { \mathrm { i } }$ and $r \geq r _ { \mathrm { e } }$ can also be independently verified by using an alternative relation between $\tilde { \xi } _ { r }$ and $\ddot { p } _ { \mathrm { t o t } }$ ，

$$
\widetilde { \xi } _ { r } = \frac { \mathrm { d } \widetilde { p } _ { \mathrm { t o t } } / \mathrm { d } r } { \rho ( \omega ^ { 2 } - k ^ { 2 } v _ { \mathrm { A } } ^ { 2 } ) } .
$$

# 2.3. Dispersion Relation of Sausage Waves

The dispersion relation (DR) governing linear sausage waves can be derived by requiring that both $\tilde { \xi } _ { r }$ and $\tilde { p } _ { \mathrm { t o t } }$ be continuous at the interfaces $r = r _ { \mathrm { i } }$ and $r = r _ { \mathrm { e } }$ . This leads to

$$
\begin{array} { r c l } { { A _ { \mathrm { i } } J _ { \mathrm { 1 } } ( \mu _ { \mathrm { i } } r _ { \mathrm { i } } ) } } & { { = } } & { { A _ { \mathrm { 1 } } \tilde { \xi } _ { \mathrm { t r , 1 } } ( x _ { \mathrm { i } } ) + A _ { \mathrm { 2 } } \tilde { \xi } _ { \mathrm { t r , 2 } } ( x _ { \mathrm { i } } ) , } } \\ { { A _ { \mathrm { e } } H _ { \mathrm { 1 } } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } r _ { \mathrm { e } } ) } } & { { = } } & { { A _ { \mathrm { 1 } } \tilde { \xi } _ { \mathrm { t r , 1 } } ( x _ { \mathrm { e } } ) + A _ { \mathrm { 2 } } \tilde { \xi } _ { \mathrm { t r , 2 } } ( x _ { \mathrm { e } } ) , } } \\ { { A _ { \mathrm { i } } \mu _ { \mathrm { i } } r _ { \mathrm { i } } J _ { 0 } ( \mu _ { \mathrm { i } } r _ { \mathrm { i } } ) } } & { { = } } & { { \lbrack A _ { \mathrm { 1 } } \tilde { \xi } _ { \mathrm { t r , 1 } } ( x _ { \mathrm { i } } ) + A _ { \mathrm { 2 } } \tilde { \xi } _ { \mathrm { t r , 2 } } ( x _ { \mathrm { i } } ) ] + r _ { \mathrm { i } } [ A _ { \mathrm { 1 } } \tilde { \xi } _ { \mathrm { t r , 1 } } ^ { \prime } ( x _ { \mathrm { i } } ) + A _ { \mathrm { 2 } } \tilde { \xi } _ { \mathrm { t r , 2 } } ^ { \prime } ( x _ { \mathrm { i } } ) ] , } } \\ { { A _ { \mathrm { e } } \mu _ { \mathrm { e } } r _ { \mathrm { e } } H _ { \mathrm { 0 } } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } r _ { \mathrm { e } } ) } } & { { = } } & { { \lbrack A _ { \mathrm { 1 } } \tilde { \xi } _ { \mathrm { t r , 1 } } ( x _ { \mathrm { e } } ) + A _ { \mathrm { 2 } } \tilde { \xi } _ { \mathrm { t r , 2 } } ( x _ { \mathrm { e } } ) ] + r _ { \mathrm { e } } [ A _ { \mathrm { 1 } } \tilde { \xi } _ { \mathrm { t r , 1 } } ^ { \prime } ( x _ { \mathrm { e } } ) + A _ { \mathrm { 2 } } \tilde { \xi } _ { \mathrm { t r , 2 } } ^ { \prime } ( x _ { \mathrm { e } } ) ] , } } \end{array}
$$

where $x _ { \mathrm { i } } = - l / 2$ and $x _ { \mathrm { e } } = l / 2$ .Eliminating $A _ { \mathrm { i } }$ ( $A _ { \mathrm { e } }$ ）by dividing the third (fourth） by the first (second) equation, one finds that

$$
\begin{array} { r } { \Lambda _ { 1 } A _ { 1 } + \Lambda _ { 2 } A _ { 2 } = 0 , } \\ { \Lambda _ { 3 } A _ { 1 } + \Lambda _ { 4 } A _ { 2 } = 0 , } \end{array}
$$

wherethecoefficientsread

$$
\begin{array} { r l } & { \Lambda _ { 1 } = \tilde { \xi } _ { \mathrm { t r } , 1 } ( x _ { \mathrm { i } } ) + r _ { \mathrm { i } } \tilde { \xi } _ { \mathrm { t r } , 1 } ^ { \prime } ( x _ { \mathrm { i } } ) - X _ { \mathrm { i } } \tilde { \xi } _ { \mathrm { t r } , 1 } ( x _ { \mathrm { i } } ) , } \\ & { \Lambda _ { 2 } = \tilde { \xi } _ { \mathrm { t r } , 2 } ( x _ { \mathrm { i } } ) + r _ { \mathrm { i } } \tilde { \xi } _ { \mathrm { t r } , 2 } ^ { \prime } ( x _ { \mathrm { i } } ) - X _ { \mathrm { i } } \tilde { \xi } _ { \mathrm { t r } , 2 } ( x _ { \mathrm { i } } ) , } \\ & { \Lambda _ { 3 } = \tilde { \xi } _ { \mathrm { t r } , 1 } ( x _ { \mathrm { e } } ) + r _ { \mathrm { e } } \tilde { \xi } _ { \mathrm { t r } , 1 } ^ { \prime } ( x _ { \mathrm { e } } ) - X _ { \mathrm { e } } \tilde { \xi } _ { \mathrm { t r } , 1 } ( x _ { \mathrm { e } } ) , } \\ & { \Lambda _ { 4 } = \tilde { \xi } _ { \mathrm { t r } , 2 } ( x _ { \mathrm { e } } ) + r _ { \mathrm { e } } \tilde { \xi } _ { \mathrm { t r } , 2 } ^ { \prime } ( x _ { \mathrm { e } } ) - X _ { \mathrm { e } } \tilde { \xi } _ { \mathrm { t r } , 2 } ( x _ { \mathrm { e } } ) , } \end{array}
$$

with

$$
\begin{array} { r c l } { { X _ { \mathrm { i } } } } & { { = } } & { { \displaystyle \frac { \mu _ { \mathrm { i } } r _ { \mathrm { i } } J _ { 0 } ( \mu _ { \mathrm { i } } r _ { \mathrm { i } } ) } { J _ { 1 } ( \mu _ { \mathrm { i } } r _ { \mathrm { i } } ) } , } } \\ { { } } & { { } } & { { } } \\ { { X _ { \mathrm { e } } } } & { { = } } & { { \displaystyle \frac { \mu _ { \mathrm { e } } r _ { \mathrm { e } } H _ { 0 } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } r _ { \mathrm { e } } ) } { H _ { 1 } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } r _ { \mathrm { e } } ) } . } } \end{array}
$$

Evidently, for Eq. (14) to allow non-trivial solutions of $[ A _ { 1 } , A _ { 2 } ]$ , one needs to require that

$$
\Lambda _ { 1 } \Lambda _ { 4 } - \Lambda _ { 2 } \Lambda _ { 3 } = 0 ,
$$

which is the DR governing sausage waves in nonuniform loops.

Does Eq. (17), the DR valid for arbitrary $l / R$ , recover the well-known result for the step-function profile when $l / R  0$ ? Retaining only terms to the O-th order in $l / R$ and noting that $r _ { \mathrm { i } } \approx r _ { \mathrm { e } } \approx R$ ,one finds that $\Lambda _ { n }$ ( $n = 1 , \cdots , 4$ ）simplify to

$$
\begin{array} { r l } & { \Lambda _ { 1 } = ( 1 - X _ { \mathrm { i } } ) a _ { 0 } + R a _ { 1 } , } \\ & { \Lambda _ { 2 } = ( 1 - X _ { \mathrm { i } } ) b _ { 0 } + R b _ { 1 } , } \\ & { \Lambda _ { 3 } = ( 1 - X _ { \mathrm { e } } ) a _ { 0 } + R a _ { 1 } , } \\ & { \Lambda _ { 4 } = ( 1 - X _ { \mathrm { e } } ) b _ { 0 } + R b _ { 1 } . } \end{array}
$$

Substituting these expressions into Eq. (17), one finds that

$$
( X _ { \mathrm { i } } - X _ { \mathrm { e } } ) ( a _ { 1 } b _ { 0 } - a _ { 0 } b _ { 1 } ) = 0 .
$$

This leads to $X _ { \mathrm { i } } = X _ { \mathrm { e } }$ ， given that $a _ { 1 } b _ { 0 } - a _ { 0 } b _ { 1 }$ is not allowed to be zero for $\tilde { \xi } _ { \mathrm { t r } , 1 }$ and $\tilde { \xi } _ { \mathrm { t r } , 2 }$ to be independent. In other words (see Eq. (16))

$$
\frac { \mu _ { \mathrm { i } } J _ { 0 } ( \mu _ { \mathrm { i } } R ) } { J _ { 1 } ( \mu _ { \mathrm { i } } R ) } = \frac { \mu _ { \mathrm { e } } H _ { 0 } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } R ) } { H _ { 1 } ^ { ( 1 ) } ( \mu _ { \mathrm { e } } R ) } ,
$$

which is the DR for equilibrium density profiles of a step-function form (e.g., Cally 1986).

While the DR is equally applicable to propagating waves， we will focus on standing modes for which the axial wavenumber $k$ is real, while the angular frequency $\omega$ is allowed to be complex-valued. Furthermore,let us focus on fundamental standing modes supported by magnetized tubes of length $L$ . In this case,another measure to validate the DR,independent of the eigen-value problem approach, is to employ the linearized, time-dependent, cold MHD equations to derive an equation governing the transverse velocity perturbation $v _ { r } ( r , z , t )$ .In view of the line-tying boundary conditions at the loop ends $z ~ = ~ 0$ and $z \ = \ L$ ， one may express $v _ { r } ( r , z , t )$ as $v ( r , t ) \sin ( k z )$ with $k = \pi / L$ ， yielding (Nakariakov et al. 2012; Chen et al. 2015)

$$
\frac { \partial ^ { 2 } { v } ( r , t ) } { \partial { t } ^ { 2 } } = v _ { \mathrm { A } } ^ { 2 } ( r ) \left[ \frac { \partial ^ { 2 } } { \partial { r } ^ { 2 } } + \frac 1 r \frac \partial { \partial { r } } - \left( { k } ^ { 2 } + \frac { 1 } { { r } ^ { 2 } } \right) \right] v ( r , t ) \ .
$$

When supplemented with appropriate boundary and initial conditions, the signal of $\boldsymbol { v } _ { \boldsymbol { r } } ( \boldsymbol { r } , t )$ at some arbitrarily chosen distance from the tube axis can be folowed. As demonstrated in Nakariakov et al. (2012); Chen et al. (2015),after a transitory phase this signal evolves into a harmonic (decaying harmonic） form when $k$ is larger (less) than some critical value, corresponding to the well-known trapped (leaky） regime. Numerically fitting the signal with a sinusoidal (exponentially decaying sinusoidal) function then yields the period $P$ ( $P$ together with the damping time $\tau$ ）for trapped (leaky） modes. We also adopt this approach and compare the derived values for $P$ and $\tau$ with what is found by solving the DR for complex-valued $\omega$ at given real $k$ . As will be shown in Fig. 2, the two sets of independently derived values for $[ P , \tau ]$ agree remarkably well. At this point, it should be remarked that once a choice for $\rho _ { \mathrm { t r } }$ is made, $P$ and $\tau$ depend only on the combination of parameters $[ \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } , l / R , L / R ]$ when they are measured in units of the internal Alfvén transit time $R / v _ { \mathrm { A i } }$ Here we have used $L / R = \pi / ( k R )$ in place of the dimensionless axial wavenumber $k R$

In general, the DR (Eq. (17)） is not analytically tractable and is solved numerically for a given $\rho _ { \mathrm { t r } }$ profile and some given combination of $[ \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } , l / R , L / R ]$ .To do so requires the infinite series expansion in Eq.(8) to be truncated by retaining the terms with $n$ up to a certain $N$ . A value of $N = 1 0 1$ is chosen for all the numerical results to be presented, and we have made sure that using an even larger $N$ does not introduce any appreciable difference. In addition,we focus only on the lowest order modes, namely those with the simplest radial structure in the eigen-functions. When verifying these results with the computations from an initial-value-problem perspective, we choose not to use a too localized initial perturbation （204号 $v ( r , t = 0 )$ (see Eq.(19))，otherwise higher order modes are introduced to contaminate the $\boldsymbol { v } ( \boldsymbol { r } , t )$ signals.

# 3.NUMERICAL RESULTS AND THE INVERSION SCHEME

Let us start with an examination of how the $\rho _ { \mathrm { t r } }$ profile impacts the dispersive properties of standing sausage modes. Figure 2 shows the dependence on the length-to-radius ratio $L / R$ of the period $P$ and damping time $\tau$ for different choices of $\rho _ { \mathrm { t r } } ( r )$ as labeled.For illustration purposes，we choose the density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ to be 100,and choose $l / R$ to be unity. The black line in Fig. 2a,which represents $2 L / v _ { \mathrm { A e } }$ ， separates the trapped (to its left，where $\tau$ is identically infinite） from leaky (to its right） regimes. The curves are found by solving the analytical DR (Eq. (17)), whereas the open circles are found by solving the corresponding time-dependent equation (see Eq. (19) and the associated description). Evidently, the periods $P$ and damping times $\tau$ obtained from the two independent approaches agree with each other remarkably well. Figure 2 indicates that the overall tendency for $P$ （ $^ { \prime }$ ） to increase (decrease） with $L / R$ is seen for all the equilibrium density profiles considered. In particular,regardless of the profles, both $P$ and $\tau$ tend to some asymptotic values at large $L / R$ . However, the choice of equilibrium density profiles has a considerable influence on the specific values for $P$ and $\tau$ . This is particularly true if one compares the results for the parabolic and inverse-parabolic profiles, given by the green and blue curves, respectively. Furthermore,while the periods $P$ for the linear and sine profiles differ little for the chosen （204 $l / R$ , the damping times $\tau$ show a stronger profile dependence. This signifies the importance of using $P$ and $\tau$ in a consistent manner when one attempts to deduce how the transverse

equilibrium density is structured.

The effects of equilibrium density profile can be better brought out by capitalizing on the fact that both $P$ and $\tau$ experience saturation for sufficiently thin loops. Let $P _ { \mathrm { s } }$ and （204 $\tau _ { \mathrm { s } }$ denote the saturation values. Figure 3 presents how $P _ { \mathrm { s } }$ and ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ depend on $l / R$ ，the width of the transition layer in units of loop radius. The density contrast is chosen to be 100,and different choices of $\rho _ { \mathrm { t r } }$ are represented by the curves in different colors as labeled in Fig. 3b. In addition, in place of $\tau _ { \mathrm { s } }$ , the ratio ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ is plotted since it is a better measure of signal quality. One sees from Figs. 3a and 3b that the curves converge at $l / R  0$ as expected given that the DR (Eq. (17)) simplifies to Eq.(18) pertinent to a top-hat density distribution. Figure 3a indicates that the $l / R$ -dependence of $P _ { \mathrm { s } }$ critically depends on how $\rho _ { \mathrm { t r } }$ is described. For the parabolic profile, $P _ { \mathrm { s } }$ increases monotonically with $l / R$ ，whereas the opposite trend is found for the inverse-parabolic profile. When it comes to the linear and sine profiles,Fig. 3a shows that the $l / R$ -dependence of $P _ { \mathrm { s } }$ is not as strong, and the difference between the two profiles is discernible only when $l / R \gtrsim 1$ . Moving on to Fig. 3b, one sees that the ratio ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ decreases monotonically with $l / R$ for all the profiles,meaning that wave leakage plays an increasingly important role in attenuating sausage modes when the loop becomes more diffuse.Reinforcing the impresson from Fig.2b,one sees that relative to $P _ { \mathrm { s } }$ ， （204 ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ better discriminates the equilibrium density profiles.

So far we have fixed the density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ at 100. One naturally asks what happens if $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ is varied? Figure 4 presents the distribution of $P _ { \mathrm { { s } } }$ (the left column） and ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ (right) in the $[ \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } , l / R ]$ plane. Each row represents one of the four density profiles as labeled. Besides, the red curve represents where $\tau _ { \mathrm { s } } / P _ { \mathrm { s } } = 1 0$ , the value for the QPP event reported in McLean $\&$ Sheridan (1973). Examine the left column first. One sees from Figs. 4b and 4c that in the parameter range examined, $P _ { \mathrm { { s } } }$ tends to increase (decrease） with $l / R$ at any given $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ when the parabolic (inverse-parabolic) profile is chosen. In contrast, Figs. 4a and 4d indicate that $P _ { \mathrm { { s } } }$ for the linear and sine profiles shows a nonmonotonical dependence on （204 $l / R$ ， even though this variation is hardly discernible. Now consider the right column， from which one can see that regardless of the profiles, ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ decreases with increasing $l / R$ for all the density contrasts examined. In addition, the dependence of $\tau _ { \mathrm { s } } / P _ { \mathrm { s } }$ on $l / R$ is the strongest for the inverse-parabolic profile,and the least strong for the parabolic one. The dependence for the linear and sine profiles lies in between, with the dependence in the linear case being slightly stronger.

Conceptually, Fig. 4 can be used to invert the measured values of the period and damping time of sausage modes, provided that the loops hosting these oscillations are sufficiently thin. Consider the QPP event reported in McLean $\&$ Sheridan (1973) as an example, for which $P _ { \mathrm { ~ s ~ } } = ~ 4 . 3$ secs and $\tau _ { \mathrm { s } } / P _ { \mathrm { s } } = 1 0$ .It then follows that for a given density profile,any point along the corresponding red curve in Fig. 4 can equally reproduce the measured ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ . After reading any pair of $[ \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } , l / R ]$ , one can read from the left column the corresponding value for $P _ { \mathrm { { s } } }$ in units of $R / v _ { \mathrm { A i } }$ .With $P _ { \mathrm { s } }$ known, one can then deduce $R / v _ { \mathrm { A i } }$ . In practice, however, constructing such a contour plot is not necessary, and one may simply consider the follwing 3-step inversion scheme. First, one starts with the dispersion relation for a step-function density profile ( $l / R = 0$ ), Eq. (18), to find the value for the density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ such that （204号 ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ agrees with the measured value. Second,with the $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ value for a smaller $l / R$ as a good guess, one can then solve Eq. (17) to find a new $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ that yields the measured ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ （204号 by increasing $l / R$ from O to 2 consecutively. Third,with $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ found for all possible $l / R$ ，one can solve Eq. (17) for a given pair of $[ \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } , l / R ]$ ， yielding a value for $P _ { \mathrm { s } } / ( R / v _ { \mathrm { A i } } )$ . Finding the transverse Alfvén transit time $R / v _ { \mathrm { A i } }$ is then straightforward since $P _ { \mathrm { s } }$ is known.

The product of the inversion scheme is an inversion curve in the three-dimensional (3D) space formed by $R / v _ { \mathrm { A i } }$ ， $l / R$ and $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ . Figure 5 presents such curves (the solid lines) and their projections onto various planes (dashed） for the examined density profiles,pertinent to the event reported in McLean $\&$ Sheridan (1973). To help digest this figure,a number of points are read from the curves and presented in Table 1. One sees that among the parameters forming this 3D space, $R / v _ { \mathrm { A i } }$ is the best constrained. The biggest (smallest) value,2.13(1.18） secs, is found for the inverse-parabolic (parabolic) profile when $l / R  2$ In other words,the biggest value exceeds the smallest one by only 79.7%. As to the density contrast, the biggest value (251.4 found for the inverse-parabolic profile when $l / R  2$ is larger than the smallest one (88.1 when $l / R  0$ )by $1 8 5 \%$ . The least constrained parameter is $l / R$ ，with any value in the allowed range from O to 2 being possible.

# 4.FURTHER DEVELOPMENT OF THE INVERSION SCHEME

Before proceeding， let us frst recap the key points in the scheme for inverting the measured period $P$ and damping time $\tau$ of sausage modes. From the outset, we have assumed that only $P$ and $\tau$ are known，whereas we have no information on either the geometric parameters $( R , ~ L$ ，and $l$ ） or the physical parameters( $v _ { \mathrm { A i } }$ ， $\rho _ { \mathrm { i } }$ ，and $\rho _ { \mathrm { e } }$ ). On top of that, the specific density profile is also assumed to be unknown. This happens when one has only spatially unresolved observations (see e.g., the majority of the events compiled in Aschwanden et al. 2004, Table 1). In this case, the dispersion relation, Eq. (17),suggests that in general the periods and damping times can be formally expressed as

$$
\begin{array} { r l } & { P _ { \mathrm { s a u s } } = \displaystyle \frac { R } { v _ { \mathrm { A i } } } F _ { \mathrm { s a u s } } \left( \frac { L } { R } , \frac { l } { R } , \frac { \rho _ { \mathrm { i } } } { \rho _ { \mathrm { e } } } \right) , } \\ & { \frac { \tau _ { \mathrm { s a u s } } } { P _ { \mathrm { s a u s } } } = G _ { \mathrm { s a u s } } \left( \frac { L } { R } , \frac { l } { R } , \frac { \rho _ { \mathrm { i } } } { \rho _ { \mathrm { e } } } \right) . } \end{array}
$$

With only two measured values available,any point on a two-dimensional (2D） surface in the four-dimensional （4D） space formed by $[ R / v _ { \mathrm { A i } } , L / R , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ can reproduce the measurements,even if one is allowed to prescribe a density profile. If the sausage modes are in the trapped regime in the sense that the QPPs do not show temporal damping, then the situation becomes even less desired since now the restriction from $\tau$ is no longer available. This complexity can be alleviated if the condition $L / R \gg 1$ holds for the flare loops in question since $L / R$ no longer appears such that Eq. (2） is restored. One then finds a curve in the $[ R / v _ { \mathrm { A i } } , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ space as shown by Fig. 5.

The situation improves if the QPP events are spatially resolved, since the looplength $( L )$ and the outer interface of the loops ( $r _ { \mathrm { e } } = R + l / 2$ ） can be considered known. In this case $L / R$ and $l / R$ are no longer independent but are related by

$$
{ \frac { L } { R } } = { \frac { L } { r _ { \mathrm { { e } } } } } \left( { 1 + { \frac { l } { { 2 R } } } } \right) ,
$$

where we haveused the relation

$$
R = \frac { 2 r _ { \mathrm { e } } } { 2 + l / R } .
$$

Now the situation is similar to what Eq. (2) implies: if the sausage mode is a trapped (leaky) one, then a 2D surface (1D curve) can be deduced in the $[ R / v _ { \mathrm { A i } } , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ space. It is just that now for a point on this 2D surface or along the 1D curve, one can further deduce $v _ { \mathrm { A i } }$ in view of Eq. (22).

Something fascinating happens if one observes a spatially resolved QPP event hosting more than just a sausage mode. For illustration purposes, we consider the situation where a temporally decaying kink mode is involved,and its damping can be attributed to resonant absorption. In this case, the period and damping time for the kink mode can be formally expressed by

$$
\begin{array} { l } { \displaystyle P _ { \mathrm { k i n k } } = \frac { L } { v _ { \mathrm { A i } } } F _ { \mathrm { k i n k } } \left( \frac { l } { R } , \frac { \rho _ { \mathrm { i } } } { \rho _ { \mathrm { e } } } \right) , } \\ { \displaystyle \frac { \tau _ { \mathrm { k i n k } } } { P _ { \mathrm { k i n k } } } = G _ { \mathrm { k i n k } } \left( \frac { l } { R } , \frac { \rho _ { \mathrm { i } } } { \rho _ { \mathrm { e } } } \right) . } \end{array}
$$

Note that while $L / R$ in principle can be incorporated into Eq. (23)，in reality there is no need to do so since the corrections to $P _ { \mathrm { k i n k } }$ and $\tau _ { \mathrm { k i n k } }$ due to finite $L / R$ are of the order $( R / L ) ^ { 2 }$ (Van Doorsselaere et al. 2004; Goossens et al. 2008). Even for relatively thick flare loops, $R / L$ is of the order O.1 and these corrections amount to only a few percent. Note further that $F _ { \mathrm { k i n k } }$ and $G _ { \mathrm { k i n k } }$ have been extensively studied, and a graphical representation can be found in Fig. 1 of Soler et al. (2014). With $F _ { \mathrm { k i n k } } ^ { \prime }$ ， $G _ { \mathrm { k i n k } }$ ， $F _ { \mathrm { s a u s } } ^ { \prime }$ ，and $G _ { \mathrm { s a u s } }$ known,it is then possible to fully constrain the unknowns $[ l , R , v _ { \mathrm { A i } } , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ , if one assumes a density profile. In fact， the measured values of $[ P _ { \mathrm { k i n k } } , \tau _ { \mathrm { k i n k } } , P _ { \mathrm { s a u s } } , \tau _ { \mathrm { s a u s } } ]$ are more than sufficient: $l$ and $R$ are not independent but are related through Eq. (22). This suggests that only three expressions contained in Eqs. (2O) and (23） are needed. In practice, we consider the expression for the kink mode period as the redundant one. Now the inversion procedure is rather straightforward. In view of the relation (21),the two expressions for the dampingtime-to-period ratio in Eqs. (20) and Eqs.(23） contain only two unknowns, namely $l / R$ （204号 and $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ .With both $\tau _ { \mathrm { s a u s } } / P _ { \mathrm { s a u s } }$ and $\tau _ { \mathrm { k i n k } } / P _ { \mathrm { k i n k } }$ available, one can deduce a unique pair of $[ l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ .The loop radius $R$ then follows from Eq. (22)，which then enables one to evaluate $v _ { \mathrm { A i } }$ with the first expression in Eq. (2O). Finally, as a safety check, one can proceed to evaluate, with the first expression in Eq. (23), the theoretically expected kink mode period $P _ { \mathrm { k i n k , t h e o r y } }$ . The deviation of $P _ { \mathrm { k i n k , t h e o r y } }$ from the measured one then allows to say a few words on how safe it is to identify the oscillation signals with some particular modes.

As an illustration of the aforementioned inversion procedure, let us consider the QPP event in microwave emissions measured with the Nobeyama Radioheliograph (NoRH) on 14 May 2013 (Kolotkov et al. 2015). Lucky enough, it is likely that this event contains a fundamental kink mode with $P _ { \mathrm { k i n k } } ~ = ~ 1 0 0$ secs and $\tau _ { \mathrm { k i n k } } / P _ { \mathrm { k i n k } } = 2 . 5$ ， in addition to a fundamental sausage mode with $P _ { \mathrm { s a u s } } = 1 5$ secs and $\tau _ { \mathrm { s a u s } } / P _ { \mathrm { s a u s } } = 6$ . Assuming that the apparent width measured therein corresponds to $2 r _ { \mathrm { e } }$ , one finds that $r _ { \mathrm { e } } = 4 \times 1 0 ^ { 3 }$ km and $L = 4 \times 1 0 ^ { 4 }$ km,meaning that $L / r _ { \mathrm { e } } = 1 0$ . Let us assume that wave leakage is responsible for damping the sausage mode, and resonant absorption is responsible for damping the kink one.Furthermore,let us assume that the sine profile best describes the equilibrium density distribution. In this case,the analytical expressons obtained in the thin-tube-thin-boundary approximation are accurate to within $\sim 2 5 \%$ (e.g.， Van Doorsselaere et al. 2O04; Soler et al. 2014). This enables us to illustrate our inversion procedure without resorting to a fully numerical solver to establish $F _ { \mathrm { k i n k } }$ and $G _ { \mathrm { k i n k } }$ . Now the formal expressions given by Eq. (23) can be replaced with (e.g., Goossens et al. 2008)

$$
\begin{array} { r l } & { P _ { \mathrm { k i n k } } = \cfrac { L } { v _ { \mathrm { A i } } } \sqrt { \cfrac { 2 ( 1 + \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ) } { \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } } } , } \\ & { \cfrac { \tau _ { \mathrm { k i n k } } } { P _ { \mathrm { k i n k } } } = \cfrac { 2 } { \pi } \cfrac { \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } + 1 } { \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } - 1 } \cfrac { 1 } { l / R } . } \end{array}
$$

Following the outlined inversion procedure,we find that $l / R = 0 . 2 7 2$ and $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } = 2 9 . 8$ as constrained by the ratios $\tau / P$ . It then follows that $R = 3 . 5 2 \times 1 0 ^ { 3 }$ km, from which one can deduce that $v _ { \mathrm { A i } } = 6 2 3 \ \mathrm { k m \ s ^ { - 1 } }$ .Finally, $P _ { \mathrm { k i n k , t h e o r y } }$ is found to be 92.2 secs， which agrees with the measured value of 100 secs to within 8%. This safety check lends support to the interpretation of the two modes in terms of fundamental kink and sausage modes as done by Kolotkov et al. (2015). Besides, the deduced Alfvén speed $v _ { \mathrm { A i } }$ and density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ both seem reasonable. On top of that, there is no need for one to worry too much about the accuracy of Eq.(24) describing the kink mode: at the deduced $[ l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ , this equation yields $P$ and $\tau / P$ to an accuracy better than $1 \%$ and $\sim 6 \%$ , respectively (see Fig. 1 in Soler et al. 2014).

# 5. CONCLUSIONS

How plasma density is structured across various magnetic structures in the solar corona remains largely unknown. It has been a common practice to deduce this key information by employing magneto-seismological techniques that invert the measured period $P$ and damping time $\tau$ of standing kink modes collectively supported by a magnetic structure (e.g., Goossens et al. 2008; Soler et al. 2014). In contrast，while quasi-periodic pulsations (QPPs) in the lightcurves of solar fares are often attributed to standing sausage modes in fare loops and therefore can also offer the associated period and damping time, a scheme is missing for inverting these two measurements to deduce the information on the density distribution transverse to flare loops. The primary aim of this study has been to construct such a scheme. To this end,we worked in the framework of cold (zero- $\beta$ )MHD and modeled flare loops as straight cylinders with a transverse density profile characterized by a transition layer sandwiched between a uniform cord and a uniform external medium. An analytical dispersion relation (DR) governing linear sausage waves, Eq. (17), was derived by solving the perturbation equations in terms of a regular series expansion in the transition layer. This DR,valid for arbitrary choices of the density profile in the transition layer, then enabled us to examine the effcts of density structuring on the periods and damping times of sausage modes,thereby facilitating the construction of the inversion scheme.

In general, we found that $P$ and $\tau$ of sausage modes depend on a combination of parameters $[ R / v _ { \mathrm { A i } } , L / R , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ as formally expressed by Eq. (2O), where the functions $F _ { \mathrm { s a u s } }$ and $G _ { \mathrm { s a u s } }$ are a product of the DR. Here $L$ and $R$ denote the looplength and loop radius, respectively. Furthermore, $l$ is the width of the transition layer, $v _ { \mathrm { A i } }$ is the Alfven speed in the cord,and $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ is the density contrast between the loop and its surrounding fluid. We showed that for the density profiles examined,both $P$ and $\tau$ experience saturation for sufficiently large $L / R$ when the rest of the four parameters are fixed. The choice of the transverse density profile was found to have a considerable influence on $P$ and $\tau$ , their dependence on $l / R$ in particular.

Our inversion scheme can find applications to both spatially unresolved and resolved QPP events.For spatially unresolved ones,we showed that the best one can do is to deduce a 1D curve in the $[ R / v _ { \mathrm { A i } } , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ space for a prescribed density profile. This happens if the QPPs in question experience temporal damping,and if the flare loops hosting them can be assumed to be sufficiently thin. When applied to a QPP event reported by McLean $\&$ Sheridan (1973), this inversion technique indicated that the transverse Alfven transit time $R / v _ { \mathrm { A i } }$ is the best constrained, varying by a factor of 8O% if the uncertainties in specifying the density profle are taken into account. The density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ is less well constrained, with the largest deduced value exceeding the smallest one by a factor of 1.85. The least constrained is the transverse density lengthscale in units of loop radius $( l / R )$ , any value in the allowed range $( 0 , 2 )$ can be equally possible to reproduce the measurements.

When it comes to spatially resolved events, the geometric parameters $L$ and $R + l / 2$ are additional constraints, on top of the measured values for $P$ and $\tau$ . Even though in this case one cannot assume $L / R \gg 1$ a priori, it is possible to deduce a 1D curve in the $[ v _ { \mathrm { A i } } , l , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ space for a chosen density profile since $R$ is expressible in terms of $l / R$ . If a spatially resolved QPP event comprises more than just one sausage mode, then it is possible to deduce the full information on $[ l , R , v _ { \mathrm { A i } } , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ . In this case, the inversion problem becomes an overdetermined one. We illustrated this fascinating application with the QPP event reported by Kolotkov et al. (2O15) where a fundamental kink and a fundamental sausage mode were suggested to co-exist and both experience temporal damping. Attributing the temporal damping of the kink mode to resonant absorption,and that of the sausage mode to wave leakage，we were able to deduce the full set of $[ l , R , v _ { \mathrm { A i } } , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ by using Eqs. (20) and (4) and assuming a sine profile for the density distribution. One redundant equation, here taken as the expression for the kink mode period, can then allow a safety check on, say, whether it is reasonable to interpret the signals in the QPP event as the aforementioned modes. For this particular event, our results demonstrated that the interpretation provided in Kolotkov et al. (2015) is reasonable, not only because the deduced parameters seem realistic,but also because the theoretical prediction for the kink mode period agrees with the measured one remarkably well.

Our scheme nonetheless has a number of limitations. First，we have assumed that the temporal damping of sausage modes is due to wave leakage,an ideal MHD process. In reality, non-ideal mechanisms like electron heat conduction and ion viscosity can provide additional channels for damping sausage modes. While these non-ideal processes were shown by Kopylova et al. (2007) to be unlikely the cause for the temporal damping in the QPP event reported by McLean & Sheridan (1973), their importance has yet to be assessed for the event reported by Kolotkov et al. (2015). Second, working in the cold MHD, we have not taken into account the possible effects due to finite plasma beta, which may be of the order unity in flare loops. However, the corrections due to finite beta seem marginal (Inglis et al. 2009). Third, the longitudinal variation in neither the plasma density nor the magnetic field strength has been considered, even though the corrections due to this variation are unlikely to be significant (Pascoe et al. 2009). Fourth, the density inhomogeneity in fare loops was assumed to be in a monolithic form, whereas in reality these loops may be multi-stranded. While the fine structuring in the form of randomly distributed concentric shells is found to have a far less significant influence than the monolithic component of the density distribution (Chen et al. 2015, see also Pascoe et al. 2007), there is a need to rigorously assess the effects due to fine structuring in the form of randomly distributed strands.

We thank the referee for the constructive comments, which helped improve this manuscript substantially. This work is supported by the National Natural Science Foundation of China (41174154, 41274176,and 41474149),and by the Provincial Natural Science Foundation of Shandong via Grant JQ201212.

# REFERENCES

Andries, J., van Doorsselaere,T.,Roberts, B., Verth,G., Verwichte,E.,& Erdélyi, R.2009, Space Sci. Rev., 149, 3   
Arregui, I.， Andries, J., Van Doorsselaere,T., Goossens, M.,& Poedts, S. 2007, A&A, 463, 333   
Aschwanden, M. J., Fletcher,L., Schrijver, C. J.,& Alexander, D.1999,ApJ, 520,880   
Aschwanden, M. J., Nakariakov, V. M.,& Melnikov,V. F. 2004,ApJ, 600, 458   
Ballester, J. L., Erdélyi，R.， Hood, A. W., Leibacher, J. W.,& Nakariakov,V. M. 2007, Sol. Phys., 246, 1   
Banerjee,D., Erdélyi, R., Oliver,R., & O'Shea, E. 2007, Sol. Phys., 246, 3   
Cally,P. S. 1986, Sol. Phys., 103, 277   
Chen,S.-X., Li, B., Xia, L.-D., Chen, Y.-J., & Yu, H. 2014, Sol. Phys., 289, 1663   
Chen, S.-X., Li, B., Xia, L.-D., & Yu, H. 2015, Sol. Phys.   
Chen,Y., Feng, S. W., Li, B., Song, H. Q., Xia, L. D., Kong, X. L.,& Li, X. 2011, ApJ, 728, 147   
Chen,Y., Song, H. Q., Li, B., Xia, L. D., Wu, Z., Fu, H.,& Li, X. 2010,ApJ, 714, 644   
De Moortel, I. & Nakariakov, V. M. 2012, Royal Society of London Philosophical Transactions Series A, 370, 3193   
Dorotovic, I., Erdélyi, R., Freij, N., Karlovsky, V., & Marquez, I. 2014, A&A, 563,A12   
Edwin，P. M.& Roberts,B. 1986,in NASA Conference Publication，Vol. 2449，NASA Conference Publication, ed. B.R. Dennis, L. E. Orwig,& A.L. Kiplinger,347-357   
Edwin，P.M.& Roberts,B.1988,A&A，192,343   
Erdélyi,R. & Goossens, M. 2011, Space Sci. Rev.， 158,167   
Erdélyi, R. & Taroyan, Y. 2008, A&A, 489, L49   
Fedun, V., Verth, G., Jess, D. B.,& Erdélyi, R. 2011,ApJ, 740, L46   
Freij, N., Scullion, E. M., Nelson, C. J.， Mumford, S.， Wedemeyer, S.,& Erdélyi, R. 2014, ApJ, 791, 61   
Goossens, M.， Andries, J., & Aschwanden, M. J. 2002, A&A, 394, L39   
Goossens,M.， Arregui, I., Ballester, J. L., & Wang,T. J. 2008,A&A, 484, 851   
Goossens, M.， Erdélyi, R.,& Ruderman, M. S. 2011, Space Sci. Rev.， 158, 289   
Grant, S. D. T., Jess, D. B., Moreels, M. G., Morton, R. J., Christian, D. J., Giagkiozis, I., Verth, G., Fedun， V., Keys,P.H.， Van Doorsselaere, T.,& Erdélyi, R. 2015,ApJ, 806,132   
Hollweg， J. V. & Yang, G.1988, J. Geophys. Res.， 93, 5423   
Inglis,A. R., van Doorsselaere, T., Brady, C. S.,& Nakariakov, V. M. 2009, A&A, 503, 569   
Jess, D.B., Mathioudakis, M., Erdélyi, R., Crockett, P. J., Keenan, F. P.,& Christian, D.J. 2009，Science,323，1582   
Kolotkov, D.Y., Nakariakov, V. M., Kupriyanova, E. G., Ratcliffe, H.,& Shibasaki, K. 2015, A&A, 574, A53

Kopylova, Y. G.， Melnikov, A. V., Stepanov, A. V., Tsap, Y. T., & Goldvarg, T. B. 2007,   
Astronomy Letters, 33,706   
Li, B., Habbal, S. R., & Chen, Y. 2013,ApJ, 767,169   
Lopin, I. & Nagorny, I. 2014, A&A, 572,A60   
Luna-Cardozo, M., Verth, G., & Erdélyi, R. 2012a,ApJ, 748, 110   
Luna-Cardozo，M.， Verth，G.，& Erdélyi，R. 2012b，in IAU Symposium，Vol. 286,IAU   
Symposium, ed. C. H. Mandrini & D. F. Webb, 437-440   
Marsh, M. S. & Walsh, R. W. 2009, ApJ, 706, L76   
Mathioudakis, M., Jess,D. B., & Erdelyi, R. 2013, Space Sci. Rev., 175,1   
McLean, D. J. & Sheridan, K. V. 1973, Sol. Phys., 32, 485   
Moreels, M. G., Freij, N., Erdélyi, R.， Van Doorsselaere,T.,& Verth, G. 2015,A&A, 579,   
A73   
Morton, R. J., Erdelyi, R., Jess, D.B.,& Mathioudakis, M. 2011, ApJ, 729, L18   
Morton, R. J., Verth,G., Jess, D.B., Kuridze, D., Ruderman, M. S., Mathioudakis, M.,&   
Erdélyi, R. 2012, Nature Communications, 3, 1315   
Nakariakov,V. M. & Erdelyi, R. 2009, Space Sci. Rev., 149,1   
Nakariakov, V. M., Hornsey, C.,& Melnikov, V. F. 2012, ApJ, 761, 134   
Nakariakov, V. M. & Melnikov,V. F. 2009, Space Sci. Rev., 149, 119   
Nakariakov, V. M. & Ofman, L. 2001, A&A,372,L53   
Nakariakov, V. M. & Verwichte, E. 2005, Living Reviews in Solar Physics, 2, 3   
Ofman, L. & Aschwanden,M. J. 2002,ApJ, 576,L153   
Ofman,L. & Wang, T. J.2008,A&A, 482,L9   
Pascoe,D. J., Nakariakov, V. M., & Arber,T. D. 2007, Sol. Phys., 246,165   
Pascoe,D. J., Nakariakov, V. M., Arber, T. D.,& Murawski, K. 2009,A&A,494, 1119   
Roberts,B. 2000, Sol. Phys., 193,139

Roberts,B., Edwin,P. M.,& Benz,A. O. 1984,ApJ, 279,857   
Rosenberg,H. 1970,A&A, 9,159   
Ruderman,M. S.& Erdélyi,R.2009,Space Sci. Rev., 149,199   
Ruderman, M. S. & Roberts, B. 2002,ApJ, 577, 475   
Soler, R., Goossens, M., Terradas, J.,& Oliver,R. 2013,ApJ,777, 158 -. 2014,ApJ,781,111   
Spruit, H. C. 1982, Sol. Phys.,75, 3   
Uchida, Y. 1970, PASJ, 22, 341   
Van Doorsselaere, T.， Andries, J., Poedts, S.,& Goossens, M. 2004,ApJ, 606, 1223   
Van Doorsselaere, T., Wardle, N., Del Zanna, G., Jansari, K., Verwichte, E.,& Nakariakov, V. M. 2011, ApJ, 727, L32   
Vasheghani Farahani, S.， Hornsey， C.， Van Doorsselaere,T.，& Goossens, M. 2014，ApJ, 781, 92   
Verth,G.& Erdélyi, R. 2008,A&A,486,1015   
Verwichte, E., Van Doorsselaere, T., White,R. S., & Antolin, P. 2013, A&A, 552, A138   
White,R. S. & Verwichte, E. 2012,A&A, 537,A49   
Yuan, D., Pascoe, D. J., Nakariakov, V. M., Li, B., & Keppens, R. 2015, ApJ, 799, 221   
Zaitsev, V. V. & Stepanov, A. V. 1975, Issledovaniia Geomagnetizmu Aeronomiii Fizike Solntsa, 37, 3

![](images/ee85282e3a81536aefdebf115f9d051df954ae09dceebc46ba5f0b8d6142e96f.jpg)  
Fig. 1.- Transverse equilibrium density profles as a function of $r$ . The profiles differ only in how they are described in a transition layer sandwiched between the internal (with a uniform density $\rho _ { \mathrm { i } }$ ）and external (with a uniform density $\rho _ { \mathrm { e } }$ ） parts. The transition layer is of width $l$ ，and is located between $r _ { \mathrm { i } } = R - l / 2$ and $r _ { \mathrm { e } } = R + l / 2$ ，with $R$ being the cylinder radius. Four different choices of the density profiles in the transition layer are adopted as labeled, and are given by Eq. (4). For illustration purposes, $l$ is chosen to be $R$ ，and $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ is chosen to be 100.

![](images/c2d4dc9d38db98d50555516588af4fd798d856c10d17615076d4eafed8270e9a.jpg)  
Fig. 2.—(a) Period $P$ and(b） damping time $\tau$ as functions of loop length $L$ .Four different choices of density profiles are examined as labeled. The black line in (a) represents （204号 $P = 2 L / v _ { \mathrm { A e } }$ and separates the trapped (to its left） from leaky (right） regimes. The open circles represent the values for $P$ and $\tau$ obtained by solving Eq. (19) from an initial-valueproblem perspective, which is independent from the eigen-value-problem approach presented in the text. Here the width of the transition layer $l = R$ , and the density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } = 1 0 0$ ：

![](images/cd6f9e420e68c86ea6d8a6c51513e01d21f6d4a4d6affa71cf1d83947e869a05.jpg)  
Fig. 3.-Saturation values for (a) period $P _ { \mathrm { s } }$ and (b） damping time $\tau _ { \mathrm { s } }$ as functions of the width of the transition layer $l$ . These saturation values are attained for sufficiently thin loops. Four different choices of the density profiles are examined as labeled. Here the density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } = 1 0 0$ ：

![](images/e0167b10bc018599255fde1b6b121ada741bfb5fa4ea428ab4f703eea5816508.jpg)  
Fig. 4.- Contour plots in the $[ l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ space for the saturation values for period $P _ { \mathrm { s } }$ (the left column） and damping-time-to-period ratio ${ \tau _ { \mathrm { s } } } / { P _ { \mathrm { s } } }$ (right). These saturation values are attained for sufficiently thin loops. Each row represents one of the four different choices of the density profiles as labeled. The red curve in each panel represents where $\tau _ { \mathrm { s } } / P _ { \mathrm { s } } = 1 0$ ， corresponding to the event reported in McLean $\&$ Sheridan (1973)

![](images/308c13fdcd7235ca5be6326c2c2391ca62141841601677c58becee0b0725f414.jpg)  
Fig. 5.— Inversion curves (the solid lines) together with their projections (dashed) in the three-dimensional space formed by $[ R / v _ { \mathrm { A i } } , l / R , \rho _ { \mathrm { i } } / \rho _ { \mathrm { e } } ]$ . Four choices for the density profiles are examined and given in different panels as labeled. All points along an inversion curve are equally compatible with the quasi-periodic-pulsation event reported in McLean $\&$ Sheridan (1973)where the oscillation period is 4.3 secs,and the damping-time-to-period ratio is 10.

<html><body><table><tr><td rowspan="2">1/R</td><td colspan="2">linear</td><td colspan="2">parabolic</td><td colspan="2">inverse-parabolic</td><td colspan="2">sine</td></tr><tr><td>Pi/pe</td><td>R/UAi (sec)</td><td>Pi/pe</td><td>R/UAi (sec)</td><td>Pi/pe</td><td>R/UAi (sec)</td><td>Pi/pe</td><td>R/UAi (sec)</td></tr><tr><td>0.01</td><td>88.1</td><td>1.62</td><td>88.2</td><td>1.62</td><td>88.1</td><td>1.62</td><td>88.1</td><td>1.62</td></tr><tr><td>0.2</td><td>88.9</td><td>1.62</td><td>89.2</td><td>1.57</td><td>89.3</td><td>1.68</td><td>89.1</td><td>1.62</td></tr><tr><td>0.4</td><td>94.6</td><td>1.63</td><td>92</td><td>1.52</td><td>93.2</td><td>1.74</td><td>91.9</td><td>1.62</td></tr><tr><td>0.6</td><td>102.4</td><td>1.63</td><td>95.8</td><td>1.48</td><td>100.4</td><td>1.81</td><td>96.4</td><td>1.63</td></tr><tr><td>0.8</td><td>112.75</td><td>1.62</td><td>100.4</td><td>1.43</td><td>111.5</td><td>1.88</td><td>102.4</td><td>1.63</td></tr><tr><td>1.0</td><td>124.7</td><td>1.61</td><td>105.4</td><td>1.39</td><td>127.5</td><td>1.95</td><td>109.8</td><td>1.62</td></tr><tr><td>1.2</td><td>137.4</td><td>1.6</td><td>110.5</td><td>1.35</td><td>148.4</td><td>2.02</td><td>118.2</td><td>1.62</td></tr><tr><td>1.4</td><td>149.8</td><td>1.57</td><td>115.4</td><td>1.3</td><td>173.2</td><td>2.07</td><td>127.4</td><td>1.61</td></tr><tr><td>1.6</td><td>161.5</td><td>1.54</td><td>120</td><td>1.26</td><td>200.1</td><td>2.1</td><td>136.9</td><td>1.6</td></tr><tr><td>1.8</td><td>172</td><td>1.51</td><td>124.4</td><td>1.22</td><td>226.8</td><td>2.12</td><td>146.4</td><td>1.58</td></tr><tr><td>1.99</td><td>181.1</td><td>1.47</td><td>128.2</td><td>1.18</td><td>251.4</td><td>2.13</td><td>155.4</td><td>1.56</td></tr></table></body></html>

Table 1: The inverted values for the transverse density length scale in units of loop radius $( l / R )$ ， density contrast $\rho _ { \mathrm { i } } / \rho _ { \mathrm { e } }$ and the transverse Alfvén transit time $R / v _ { \mathrm { A i } }$ . This inversion is made for the quasi-periodic-pulsation event reported in McLean $\&$ Sheridan (1973),assuming that the associated fare loop is suffciently thin. For this event,the oscillation period is 4.3 secs,and the damping-time-to-period ratio is 10.