# Enhanced cooperativity for quantum nondemolition measurement induced spin squeezing of atoms coupled to a nanophotonic waveguide

Xiaodong Qi,1,\* Yuan-Yu Jau, $^ { 1 , 2 }$ and Ivan H. Deutsch1 （204号 $^ { 1 }$ Center for Quantum Information and Control, University of New Merico, Albuquerque, New Mexico 87131， USA （204号 $^ 2$ Sandia National Laboratories, Albuquerque, New Mexico 87185， USA (Dated: February 15,2018)

We study the enhancement of cooperativity in the atom-light interface near a nanophotonic waveguide for application to quantum nondemolition (QND) measurement of atomic spins. Here the cooperativity per atom is determined by the ratio between the measurement strength and the decoherence rate.Counterintuitively,we find that by placing the atoms at an azimuthal position where the guided probe mode has the lowest intensity,we increase the cooperativity.This arises because the QND measurement strength depends on the interference between the probe and scattered light guided into an orthogonal polarization mode,while the decoherence rate depends on the local intensity of the probe. Thus,by proper choice of geometry,the ratio of good to bad scattering can be strongly enhanced for highly anisotropic modes.We apply this to study spin squeezing resulting from QND measurement of spin projection noise via the Faraday efect in two nanophotonic geometries,a cylindrical nanofiber and a square waveguide. We find,that with about 250o atoms using realistic experimental parameters, $\sim 6 . 3$ dB and $\sim 1 3$ dB of squeezing can be achieved on the nanofiber and square waveguide,respectively.

# I. INTRODUCTION

Cooperativity is a measure of the entangling strength of the atom-light interface in quantum optics. Originally introduced in cavity quantum electrodynamics (QED), the cooperativity per atom, $C _ { 1 }$ ,can be expressed in terms of the ratio of the coherent coupling rate to decoherence rates, $C _ { 1 } = g ^ { 2 } / ( \Gamma _ { c } \Gamma _ { A } )$ where $g$ is the vacuum Rabi frequency, $\Gamma _ { c }$ is the cavity decay rate,and $\Gamma _ { A }$ is atomic spontaneous emission rate out of the cavity [1]. Alternatively, we can write $C _ { 1 } = ( \sigma _ { 0 } / A ) \mathcal { F }$ ，where $\sigma _ { 0 }$ is the resonant photon scattering cross section of the atom, $A$ is the cavity mode area,and $\mathcal { F }$ is the cavity finesse. Expressed in this way,cooperativity is seen to arise due to scattering of photons preferentially into the cavity mode, compared to emission into free space,here enhanced by the finesses due to the Purcell effect. Strong coupling dy namics seen in pioneering experiments in atomic cavity QED[2,3] is now a mainstay in quantum information processing in systems ranging from quantum dots [4- 6] to circuit QED [7,8]. The $N _ { A }$ atom cooperativity, $C _ { N } = ( N _ { A } \sigma _ { 0 } / A ) \mathcal { F } = ( O D ) \mathcal { F }$ ，where $O D$ is the resonant optical depth. In this configuration,the collective degrees of the atom can be manipulated by their common coupling to the cavity mode.

Cooperativity also characterizes the atom-light interface in the absence of a cavity. In free space,an atom at the waist of a laser beam will scatter into the forward direction at a rate $\kappa \propto ( \sigma _ { 0 } / A ) \gamma _ { s }$ ，where $\gamma _ { s }$ is the photon scattering rate into $4 \pi$ steradians [9]. Here the single atom cooperativity can be expressed to be proportional to ratio of these rates, $C _ { 1 } \propto \kappa / \gamma _ { s } \propto \sigma _ { 0 } / A$ The $N _ { A }$ -atom cooperativity, in a plane wave approximation,ignoring effects of diffraction and cloud geometry [9], $C _ { N } \propto N _ { A } \sigma _ { 0 } / A = O D$ . To be self-consistent,here the beam area must be very large, so $C _ { 1 }$ is very small, e.g. $C _ { 1 } \sim 1 0 ^ { - 6 }$ , but for a sufficiently large ensemble, the $O D$ can be large enough to lead to entanglement between the collective atomic degrees of freedom and the light.In that situation,measurement of the light leads to back action on the ensemble,and for an appropriate quantum nondemolition(QND) interaction,results in squeezing of the collective spin [10,11]. QND measurement-induced spin squeezing have been observed in free space dipoletrapped ensembles [12-14] and in optical cavities [15- 17].The rate of decoherence is set by the rate of optical pumping, $\gamma _ { o p } \propto \gamma _ { s }$ ，and we can characterize the cooperativity/atom by $C _ { 1 } = \kappa / \gamma _ { o p }$

In recent years nanophotonic waveguides have emerged asa new geometry that complements cavity QED，and can lead to strong cooperativity [18-24]. Notably, the effective beam area of a tightly guided mode can be much smaller than in free space and propagate for long distances without diffraction. As such, $\sigma _ { 0 } / A$ can be orders of magnitude larger than in free space, e.g., $\sigma _ { 0 } / A \sim 0 . 1$ ， and contribute collectively fora modest ensemble of a few thousand atoms trapped near the surface of the waveguide.Moreover,in some cases the Purcell effect can further enhance forward scattering into the guided mode when compared with scattering into free space. Taken together, these features make nanophotonic waveguides a promising platform for the quantum atom-light interface.

In this paper we show that one can achieve an additional enhancement to the cooperativity in a nanophotonic geometry that is not possible in free space.In particular,we consider the QND measurement of the collective spin of an atomic ensemble via a Faraday interaction followed by polarization spectroscopy. In this configuration the polarimeter effectively performs a homodyne measurement，where the probe is the“local oscillator" that interferes with the light scattered into the orthogo nally polarized guided mode [9]. This signal thus depends on the spatial overlap of the two orthogonal polarization modes at the position of the atom.In contrast,decoherence due to photon scattering into unguided $4 \pi$ steradians occurs at a rate $\gamma _ { s }$ isdetermined only by the intensity of the probe. The net result is that the cooperativity per atom, $C _ { 1 } \propto \kappa / \gamma _ { s }$ ，primarily depends on the strength of the orthogonal polarization mode,and this factor can be enhanced, especially for highly anisotropic guided modes. Counterintuitively,we will see that the strongest cooperativity arises when the atom is placed at the position of minimum intensity of the azimuthally anisotropic probe mode where the intensity of the initially unoccupied orthogonal mode is maximum.

We study the enhanced cooperativity for two nanophotonic geometries: a cylindrical nanofiber formed by tapering a standard optical fiber with cold atoms trapped in the evanescent wave,as recently employed ina variety of experimental studies [18, 25-38],and a nanofabricated suspended square waveguide,currently investigated at Sandia National Laboratories [39]. For each geometry we study the use of the Faraday effect and polarimetry to perform a QND measurement of the magnetic spins [40] and thereby induce squeezing of collective spins of cesium atoms.A dispersive measurement of the number of atoms trapped near the surface of an optical nanofiber was first performed in [41],and quantum spin projection noise was recently detected using a QND measurement with a two-color probe in [31, 38]. Previously, we studied QND measurement-induced spin squeezing mediated by a birefringence interaction [24]. We will see here that, through the enhanced cooperativity,QND measurement via the Faraday effect can lead to substantial squeezing, greater than 10 dB in some geometries, for 2500 atoms.

The remainder of the paper is organized as follows. In Sec.II,we lay out the theoretical description of the QND measurement and the relevant measurement strength.In addition,we describe how decoherence is included in the model through a first-principles stochastic master equation,here for the case of alkali atoms,and cesium in particular. From this we will see how cooperativity emerges as the key parameter that characterizes the squeezing. We calculate in Sec. III the squeezing dynamics for the different nanophotonic waveguides,atomic preparations, and measurement protocols. We conclude with a summary and outlook for future work.

# II. QNDMEASUREMENTANDCOOPERATIVITY

The theoretical framework describing the propagation of light guided in a nanofiber and interacting with trapped atoms in the dispersive regime was detailed in our previous work [24]. We review the salient features here and include the generalization to the square waveg

uide.

For waveguides that are symmetric under a $\pi / 2$ rota tion around the $z$ (propagation）axis,there are two degenerate polarizations for each guided mode and for each propagation direction. Assuming a nanophotonic waveguide that supports only the lowest order guided mode, and restricting our attention to modes propagating in the positive $z$ -direction，we denote ${ \bf u } _ { H } ( { \bf r } _ { \perp } )$ and ${ \bf u } _ { V } ( { \bf r } _ { \perp } )$ as the horizontally and vertically polarized modes that adiabatically connect to $x$ and $y$ linearly polarized modes, respectively,as the cross section of the waveguide become large compared to optical wavelength. Note，in typical nanophotonic geometries these guided modes also have a nonnegligible $z$ component. For a cylindrically symmetric nanofiber,these are the well-studied $\mathrm { H E } _ { 1 1 }$ modes; for a square waveguide,these are the quasi-TE $_ { 0 1 }$ （204号 and quasi-TM $_ { 0 1 }$ modes,shown in Fig.(1). One can solve for the guided modes of a cylindrical fiber analytically [24,42，43]. We use a vector finite difference method to numerically solve for the guided eigenmodes of the square waveguide [44] with core material of SigN $^ 4$ （204号 whose index of refraction is $n = 2$ [45].

The quasimonochromatic positive frequency component of the quantized field associated with these guided modes $( g )$ at frequency $\omega _ { 0 }$ takes the form

$$
\begin{array} { r } { \hat { \mathbf { E } } _ { g } ^ { ( + ) } ( \mathbf { r } , t ) = \sqrt { \frac { 2 \pi \hbar \omega _ { 0 } } { v _ { g } } } \left[ \mathbf { u } _ { H } ( \mathbf { r } _ { \bot } ) \hat { a } _ { H } ( t ) + \mathbf { u } _ { V } ( \mathbf { r } _ { \bot } ) \hat { a } _ { V } ( t ) \right] } \\ { \mathbf { \epsilon } \cdot e ^ { i ( \beta _ { 0 } z - \omega _ { 0 } t ) } , \qquad } \end{array}
$$

where $v _ { g }$ is the group velocity, and $\beta _ { 0 }$ is the propagation constant of the guided modes. In the first Born approximation the dispersive interaction of the guided field with $N _ { A }$ atoms trapped near the surface of the waveguide at positions $\{ \mathbf { r } _ { \bot } ^ { \prime } , z _ { n } \}$ , detuned far from resonance, is defined by the scattering equation [24],

$$
\begin{array} { l } { \hat { \mathbf { E } } _ { g , o u t } ^ { ( + ) } ( \mathbf { r } , t ) = \hat { \mathbf { E } } _ { g , i n } ^ { ( + ) } ( \mathbf { r } , t ) } \\ { \displaystyle + \sum _ { n = 1 } ^ { N _ { A } } \overleftrightarrow { \mathbf { G } } _ { g } ( \mathbf { r } , \mathbf { r } _ { n } ^ { \prime } ; \omega _ { 0 } ) \cdot \hat { \boldsymbol { \alpha } } _ { n } \cdot \hat { \mathbf { E } } _ { g , i n } ^ { ( + ) } ( \mathbf { r } _ { n } ^ { \prime } , t ) , } \end{array}
$$

where $\hat { \vec { \alpha } } ^ { ( n ) }$ is the atomic polarizability operator of the $n ^ { t h }$ atom,and

$$
\overleftrightarrow { \mathbf { G } } _ { g } ^ { ( + ) } ( \mathbf { r } , \mathbf { r } _ { n } ^ { \prime } ; \omega _ { 0 } ) = 2 \pi i \frac { \omega _ { 0 } } { v _ { g } } \sum _ { p } \mathbf { u } _ { p } ( \mathbf { r } _ { \perp } ) \mathbf { u } _ { p } ^ { * } ( \mathbf { r } _ { \perp } ^ { \prime } ) e ^ { i \beta _ { 0 } ( z - z _ { n } ^ { \prime } ) }
$$

is the dyadic Green's function for a dipole to radiate into the forward-propagating guided mode. In principle the Green's function for an $N _ { A }$ -atom chain decomposes into a collective sub- and superradiant normal modes [23,46], but in the far-detuning limit, these all are equally excited. The result is equivalent to the symmetric mode of independently radiating dipoles. The input-output relation for the mode operators then reads [24]

$$
\hat { a } _ { p } ^ { o u t } ( t ) = \hat { a } _ { p } ^ { i n } ( t ) + i \sum _ { p ^ { \prime } } \hat { \phi } _ { p , p ^ { \prime } } \hat { a } _ { p ^ { \prime } } ^ { i n } ( t ) ,
$$

![](images/d1fbf4ed4ac35c4c3e3e6c76e5031edd338f36fb8e2d8761038eb1ce4dfddb53.jpg)  
FIG.1. Fundamental guided modes of the nanophotonic waveguides.(a)Electric field components of the $H$ -polarized $\mathrm { H E } _ { 1 1 }$ mode of a circular nanofiber.From left to right are $\mathrm { R e } [ u _ { x } ( \mathbf { r } _ { \perp } ) ]$ ， $\mathrm { R e } [ u _ { y } ( \mathbf { r } _ { \perp } ) ]$ and $\mathrm { I m } [ u _ { z } ( \mathbf { r } _ { \perp } ) ]$ in the $x y$ -plane. (b) Same as (a) but for the $H$ -polarized quasi-TEo1 mode of a square waveguide. Black lines outline the waveguide boundary. The color scale is normalized to the maximum value of all field components for each waveguide mode.All other mode components not shown for both waveguide geometries vanish everywhere.(c) The normalized intensity distribution on the transverse plane for both geometries. The blue arrows indicate the local electric field's direction and amplitude (relative length） at positions along the vertical waveguide axis,which only have an $x$ -component of the mode.The stars indicate typical positions of trapped atoms ( $r _ { \perp } ^ { \prime } / a = 1 . 8$ for nanofiber [18] and similar scale for the square waveguide, $r _ { \bot } ^ { \prime } / w = 1 . 0$ ，where $a$ and $w$ are the radius and width of the waveguides respectively).Dotted light gray lines show the corresponding $V$ -mode contour which is the $H$ -moderotated by $9 0 ^ { \circ }$ around the waveguide propagation axis. The atom's azimuthal position is chosen to be at a position with the $V$ 1 mode being strongest.

where

$$
\hat { \phi } _ { p , p ^ { \prime } } = 2 \pi \frac { \omega _ { 0 } } { v _ { g } } \mathbf { u } _ { p } ^ { * } ( \mathbf { r } _ { \bot } ^ { \prime } ) \cdot \sum _ { n = 1 } ^ { N _ { A } } \hat { \vec { \alpha } } _ { n } \cdot \mathbf { u } _ { p ^ { \prime } } ( \mathbf { r } _ { \bot } ^ { \prime } )
$$

is the phase operator associated with scattering polarization $\boldsymbol { p ^ { \prime } }  p$ by a collective atomic operator. When （204 $p = p ^ { \prime }$ ,this is a phase shift；for $p \neq p ^ { \prime }$ ，this leads to a transformation of the polarization of the guided mode.

The Faraday effect arises from the irreducible rank1 (vector） component of the polarizability tensor [47]. G.B thae $f$ is te ta $\hat { \alpha } _ { i j } ^ { v e c } = i \alpha _ { 1 } \epsilon _ { i j k } \hat { f } _ { k }$ $\begin{array} { r } { \alpha _ { 1 } = C _ { f } ^ { ( 1 ) } \frac { \sigma _ { 0 } } { 4 \pi k _ { 0 } } \frac { \Gamma _ { A } } { 2 \Delta } } \end{array}$ acteriticpabitIa $C _ { f } ^ { ( 1 ) } = \mp \frac { 1 } { 3 f }$ the D1- and D2-line transitions, respectively. We take the detuning, $\Delta$ , large compared to the excited state hyperfine splitting.The resonant scattering cross section on a unit oscillator strength is $\sigma _ { 0 } = 6 \pi / k _ { 0 } ^ { 2 }$ ，where $k _ { 0 } = \omega _ { 0 } / c$ The polarization transformation associated with scattering from $H$ to $V$ mode is determined by the operator

![](images/7babdc39bd34ec6788cb730b7ef009e6874e8f3c598a7fbdfa74a18caccadbd4.jpg)  
FIG.2.(a) Schematic polarization spectroscopy geometry for the QND measurement and spin squeezing generation based on the Faraday effect. Atoms trapped near the surface of the nanophotonic waveguide cause a Faraday rotation of the guided light,which is measured ina polarimeter that detects the $S _ { 2 }$ component of the Stokes vector (intensity in the diagonal $\mathcal { D }$ minus anti-diagonal $D$ modes)．(b） The evolution of the light's polarization state on the Poincaré sphere (left to right). The Stokes vector of the light is prepared along the $S _ { 1 }$ direction,and the Faraday interaction causes a rotation around the $S _ { 3 }$ -axis.Shot noise,shown as uncertainty bubble,limits the resolution of the detection.(c) The evolution of the collective state before and after the measurement (left to right).The spin is prepared in a coherent state with projection noise shown as an uncertainty bubble.After the measurement the uncertainty in $F _ { z }$ is squeezed,and the direction is correlated with the measurement outcome on the polarimeter.

$$
\hat { \phi } _ { V H } = i 2 \pi \frac { \omega _ { 0 } } { v _ { g } } \alpha _ { 1 } \left[ \mathbf { u } _ { V } ^ { * } \big ( \mathbf { r } _ { \perp } ^ { \prime } \big ) \times \mathbf { u } _ { H } \big ( \mathbf { r } _ { \perp } ^ { \prime } \big ) \right] \cdot \hat { \mathbf { F } } ,
$$

where ${ \hat { \mathbf { F } } } = \textstyle \sum _ { n } { \hat { \mathbf { f } } } ^ { ( n ) }$ is the collective spin of the atomic ensemble. Thus,

$$
\begin{array} { r l r } {  { \hat { a } _ { V } ^ { o u t } ( t ) = \hat { a } _ { V } ^ { i n } ( t ) + i \hat { \phi } _ { V , H } \hat { a } _ { H } ^ { i n } ( t ) } } \\ & { } & { = \hat { a } _ { V } ^ { i n } ( t ) - 2 \pi \frac { \omega _ { 0 } } { v _ { g } } \alpha _ { 1 } [ { \bf u } _ { V } ^ { * } ( { \bf r } _ { \perp } ^ { \prime } ) { \bf \times u } _ { H } ( { \bf r } _ { \perp } ^ { \prime } ) ] \cdot \hat { \bf F } \hat { a } _ { H } ^ { i n } ( t ) , } \end{array}
$$

and similarly for scattering from $V$ to $H$

The polarization transformation can be expressed as a rotation of the Stokes vector of the light on the Poincaré sphere with operator components

$$
\begin{array} { r l } & { \hat { S } _ { 1 } ( t ) = \frac { 1 } { 2 } \big [ \hat { a } _ { H } ^ { \dagger } ( t ) \hat { a } _ { H } ( t ) - \hat { a } _ { V } ^ { \dagger } ( t ) \hat { a } _ { V } ( t ) \big ] , } \\ & { \hat { S } _ { 2 } ( t ) = \frac { 1 } { 2 } \big [ \hat { a } _ { H } ^ { \dagger } ( t ) \hat { a } _ { V } ( t ) + \hat { a } _ { V } ^ { \dagger } ( t ) \hat { a } _ { H } ( t ) \big ] , } \\ & { \hat { S } _ { 3 } ( t ) = \frac { 1 } { 2 i } \big [ \hat { a } _ { H } ^ { \dagger } ( t ) \hat { a } _ { V } ( t ) - \hat { a } _ { V } ^ { \dagger } ( t ) \hat { a } _ { H } ( t ) \big ] . } \end{array}
$$

By measuring the output Stokes vector in a polarimeter, we perform a QND measurement of a collective atomic operator to which it was entangled. In a proper configuration，this leads to squeezing of a collective spin.

Launching $H$ -polarized light corresponds to the initial Stokes vector along $S _ { 1 }$ ，and Faraday rotation leads to an $S _ { 2 }$ component，which is measured in a polarimeter (Fig.2(a)). Taking the $H$ -mode as a coherent state with amplitude $\beta _ { H }$ ，the signal of the polarimeter measures $\hat { S } _ { 2 } ^ { o u t } \ : = \ : ( \beta _ { H } \hat { a } _ { V } ^ { \dagger o u t } + \beta _ { H } ^ { * } \hat { a } _ { V } ^ { o u t } ) / 2$ Expressed in this way we see that the polarimeter acts as a homodyne detector,with the input $H$ -mode acting as the local oscillator and the photons scattered into the $V$ -mode as the signal.Formally,the input-output relation follows from the scattering equation,Eq.(7),and reads

$$
\hat { S } _ { 2 } ^ { o u t } = \hat { S } _ { 2 } ^ { i n } + i \left( \hat { \phi } _ { V H } - \hat { \phi } _ { H V } \right) \hat { S } _ { 1 } ^ { i n } = \hat { S } _ { 2 } ^ { i n } + \chi _ { 3 } ( \mathbf { r } _ { \bot } ^ { \prime } ) \hat { F } _ { z } \hat { S } _ { 1 } ^ { i n } .
$$

The first term $\hat { S } _ { 2 } ^ { i n }$ represents the shot-noise that fundamentally limits the resolution of the measurement and thus the spin squeezing that can be obtained in a given time interval. The second term is the homodyne signal, where we have expressed the rotation angle around the 3-axis of the Poincaré sphere as

$$
\begin{array} { l } { { \displaystyle \chi _ { 3 } ( { \bf r } _ { \perp } ^ { \prime } ) = - \frac { 4 \pi \omega _ { 0 } } { v _ { g } } \alpha _ { 1 } \left| \mathrm { R e } [ { \bf u } _ { V } ^ { * } ( { \bf r } _ { \perp } ^ { \prime } ) \times { \bf u } _ { H } ( { \bf r } _ { \perp } ^ { \prime } ) ] \right| } } \\ { { \displaystyle ~ = - C _ { f } ^ { ( 1 ) } \frac { \sigma _ { 0 } } { A _ { F a r } ( { \bf r } _ { \perp } ^ { \prime } ) } \frac { \Gamma _ { A } } { 2 \Delta } . } } \end{array}
$$

We emphasize here the dependence of the rotation angle on the position of the atom in the transverse plane, $\mathbf { r } _ { \bot } ^ { \prime }$ ， assumed equal for all atoms in the chain.In particular $\chi _ { 3 } ( \mathbf { r } _ { \bot } ^ { \prime } )$ depends on the overlap of ${ \bf u } _ { H } ( { \bf r } _ { \perp } ^ { \prime } )$ and ${ \bf u } _ { V } ( { \bf r } _ { \perp } ^ { \prime } )$ ， indicating atomic scattering of photons from the $H$ to $V$ modes associated with the Faraday interaction.We have characterized this overlap by an effective area that defines the Faraday interaction at the position of the atom,

$$
A _ { \mathrm { F a r } } ( \mathbf { r } _ { \bot } ^ { \prime } ) = \frac { 1 } { n _ { g } | \mathrm { R e } [ \mathbf { u } _ { V } ^ { * } ( \mathbf { r } _ { \bot } ^ { \prime } ) \times \mathbf { u } _ { H } ( \mathbf { r } _ { \bot } ^ { \prime } ) ] | } ,
$$

where $n _ { g } = c / v _ { g }$ is the group index.A more tightly con fined (smaller) area corresponds to a stronger interaction.

By monitoring the Faraday rotation,we can perform a continuous measurement on the collective spin projection $\hat { F } _ { z }$ . The “measurement strength,” which characterizes the rate at which we gain information and thereby squeeze the spin,is given by

$$
\kappa = \left| \chi _ { 3 } ( \mathbf { r _ { \bot } ^ { \prime } } ) \right| ^ { 2 } { \frac { P _ { \mathrm { i n } } } { \hbar \omega _ { 0 } } } ,
$$

where $P _ { i n }$ is the input power transported into the guided mode. The measurement strength is the rate at which photons are scattered from the guided $H$ to $V$ mode. Decoherence arises due to diffuse scattering into unguided modes and the accompanied optical pumping of the spin. In principle the photon scattering rate into $4 \pi$ steradians is modified over free space due to the Purcell effect, but we neglect this correction here.In the case of the nanofiber,this is a small effect at typical distances at which the atom is trapped [48,49]. For the square waveg uide,we will examine this correction in future work.

Decoherence is due to optical pumping of the spin between different magnetic sublevels. Henceforth,we restrict to alkali atoms driven on the D1 or D2 line,with optical pumping rate

$$
\gamma _ { o p } = \frac { 2 } { 9 } \sigma ( \Delta ) \frac { I _ { \mathrm { i n } } ( \mathbf { r } _ { \bot } ^ { \prime } ) } { \hbar \omega _ { 0 } } .
$$

Here $\begin{array} { r } { \sigma ( \Delta ) = \sigma _ { 0 } \frac { \Gamma _ { A } ^ { 2 } } { 4 \Delta ^ { 2 } } } \end{array}$ istt $\Delta$ sition,and the factor of $2 / 9$ reflects the branching ratio for absorbing a $\pi$ -polarized laserphoton followed by spontaneous emission of a photon,causing optical pumping to another spin state. $I _ { \mathrm { i n } } ( { \bf r } _ { \bot } ^ { \prime } ) = n _ { g } P _ { \mathrm { i n } } | { \bf u } _ { H } ( { \bf r } _ { \bot } ^ { \prime } ) | ^ { 2 } \equiv$ $P _ { \mathrm { i n } } / A _ { \mathrm { i n } } ( \mathbf { r } _ { \perp } ^ { \prime } )$ is the input intensity into the guided $H$ mode at the position of the atom,where we have defined

$$
A _ { \mathrm { i n } } ( \mathbf { r } _ { \bot } ^ { \prime } ) = \frac { 1 } { n _ { g } | \mathbf { u } _ { H } ( \mathbf { r } _ { \bot } ^ { \prime } ) | ^ { 2 } }
$$

to be the effective area associated with the input mode. We thus define the cooperativity/atom

$$
C _ { 1 } ( \mathbf { r _ { \bot } ^ { \prime } } ) = \frac { \kappa } { \gamma _ { o p } } = \frac { \sigma _ { 0 } } { 2 f ^ { 2 } } \frac { A _ { \mathrm { i n } } ( \mathbf { r _ { \bot } ^ { \prime } } ) } { [ A _ { \mathrm { F a r } } ( \mathbf { r _ { \bot } ^ { \prime } } ) ] ^ { 2 } } .
$$

This is our central result.Roughly, $1 / [ A _ { \mathrm { F a r } } ( \mathbf { r } _ { \bot } ^ { \prime } ) ] ^ { 2 } \sim$ $| \mathbf { u } _ { V } ( \mathbf { r } _ { \bot } ^ { \prime } ) | ^ { 2 } | \mathbf { u } _ { H } ( \mathbf { r } _ { \bot } ^ { \prime } ) | ^ { 2 }$ ，thus $C _ { 1 } ( \mathbf { r } _ { \bot } ^ { \prime } ) \sim \sigma _ { 0 } | \mathbf { u } _ { V } ( \mathbf { r } _ { \bot } ^ { \prime } ) | ^ { 2 }$ . In the context of homodyne measurement, the signal to be measured is proportional to the overlap between the $H$ -and $V$ -modes,while the decoherence rate depends on the intensity of local oscillator or $H$ -mode. How large the initially unoccupied $V$ -mode is at the atoms'position determines the signal-to-noise ratio for a QND measurement. We thus enhance the cooperativity by choosing the position of the atoms so that the orthogonal, unoccupied mode is large,while the intensity of the local input mode that causes decoherence is small.

We contrast this with squeezing arising from a birefringence interaction,as we studied previously in [24]. Linear birefringence corresponds to a relative phase between the ordinary and extra-ordinary linear polarizations,which can arise both due to the geometry of the anisotropic modes relative to the placement of the atoms,as well as the atoms' tensor polarizability. Here, the coupling is not optimal at the position of minimum intensity;it is maximum at the angle $4 5 ^ { \circ }$ between the H and V modes.As such,one will not see as strong of an enhancement of the cooperativity as we will find in our protocol employing theFaraday effect.

Figs.3 and 4 show plots of $1 / A _ { \mathrm { F a r } }$ ， $1 / A _ { \mathrm { i n } }$ ，and $C _ { 1 }$ as a function of the position of the atom in the transverse plane, $\mathbf { r } _ { \bot } ^ { \prime }$ ，for the two nanophotonic geometries. We see that $A _ { \mathrm { F a r } }$ is essentially cylindrically symmetric sufficiently far from the surface for both the nanofiber and square waveguide geometries and thus the measurement strength is basically independent of the azimuthal position of the atoms. In contrast, $A _ { \mathrm { i n } }$ is azimuthally anisotropic.For input $x$ -polarization, $1 / A _ { \mathrm { i n } }$ is the smallest along the $y$ -axis at a given radial distance,which corresponds to the smallest intensity of the input $H$ -mode, and thus smallest optical pumping rate $\gamma _ { o p }$ .This angle corresponds to the position at which $| \mathbf { u } _ { V } ( \mathbf { r } _ { \bot } ^ { \prime } ) |$ is largest and thus yields the largest enhancement of $C _ { 1 }$ . Thus, counterintuitively,we enhance the cooperativity by placing the atom at the angle of minimum input intensity.

![](images/2d339870c66135b5394bc5e3ecbe153a095a72b0f5d136a0d6a189541ee2c805.jpg)  
FIG.3. Contour plots of the effective mode areas and the cooperativity per atom near an optical nanofiber.(a) and (b) show the contour of the reciprocal effective Faraday interaction mode area,Eq.(11),and the reciprocal input mode area in the $x y$ -plane,Eq.(14),respectively. An $x$ -polarized incident mode is assumed.(c) shows a contour plot of the cooperativity Eq.(15) in the $x y$ -plane.The isovalue lines of $C _ { 1 }$ increase by O.0o2428 on each gradient step from the outside inwards. The $x$ and $y$ coordinates are scaled in units of $a$ for all three plots.

![](images/d8248f901af27840a1dfd24bb5c413f2b06eeb39fd4838b2ded3cb7cffb34e67.jpg)  
FIG.4. Similar to Fig.3 but for the square waveguide. In (a),the contour lines outside of the waveguide are essentially concentric circles.There are distortions near the four corners of the square waveguide shown in the plot mainly caused by numerical divergences.In(c),the isovalue lines of $C _ { 1 }$ increase by O.0o51o9 on each gradient step from the outside inwards. The $x$ and $y$ coordinates are scaled in units of $w$ for all three plots.

This enhancement is even greater for the square waveguide which has more anisotropic guided modes compared to the cylindrical nanofiber. For typical geometries, given a nanofiber with radius $a = 2 2 5 \mathrm { { n m } }$ and atoms trapped on the $y -$ axis,a distance 200nm (O.8a） from the surface,the single atom cooperativity is $C _ { 1 } = 0 . 0 0 7 2 8$ at the optimal trapping angle; for the square waveguide of width $w = \mathrm { 3 0 0 n m }$ ,and atoms trapped 150nm from the surface, $C _ { 1 } = 0 . 0 1 0 2$ at optimum.Thus,with order 1000 trapped atoms the $N _ { A }$ -atom cooperativity is of order of 10,sufficient to generate substantial spin squeezing.

# III. SPIN SQUEEZING DYNAMICS

Given an ensemble of $N _ { A }$ atoms initially prepared in a spin coherent state for the hyperfine spin $f$ ，polarized in the transverse plane,e.g.，along the $x$ -axis，a QND measurement of the collective spin $F _ { z }$ will squeeze the uncertainty of that component.The metrologically rele vant squeezing parameter is [50],

$$
\xi ^ { 2 } \equiv \frac { 2 N _ { A } f \big < \Delta F _ { z } ^ { 2 } \big > } { \big < \hat { F } _ { x } \big > ^ { 2 } } .
$$

Under the assumption that the state is symmetric with respect to exchange of any two atoms,valid when we start in a spin coherent state and all couplings are uniform over the ensemble,the collective expectation value can be decomposed into

$$
\begin{array} { r l } & { \langle \Delta F _ { z } ^ { 2 } \rangle = N _ { A } \big \langle \Delta f _ { z } ^ { 2 } \big \rangle + N _ { A } ( N _ { A } - 1 ) \left. \left. \Delta f _ { z } ^ { ( i ) } \Delta f _ { z } ^ { ( j ) } \right. \right| _ { \dot { \boldsymbol { \psi } } \boldsymbol { j } } } \\ & { \quad \left. \left. \hat { F } _ { x } \right. = N _ { A } \big \langle \hat { f } _ { x } \right. . } \end{array}
$$

The first term of Eq. (17a) and Eq.(17b) is the projection noise associated with the $N _ { A }$ identical spin- $f$ atoms, and the second term of Eq.(17a) is determined by two body covariances, $  \Delta f _ { z } ^ { ( i ) } \Delta f _ { z } ^ { ( j ) }  | _ { i \ne j } =   \Delta f _ { z } ^ { ( 1 ) } \Delta f _ { z } ^ { ( 2 ) }  =$ $\langle \hat { f } _ { z } ^ { ( 1 ) } \hat { f } _ { z } ^ { ( 2 ) } \rangle - \langle \hat { f } _ { z } ^ { ( 1 ) } \rangle \langle \hat { f } _ { z } ^ { ( 1 ) } \rangle$ . Negative values in these twobody correlations correspond to the pairwise entangle ment between atoms,leading to spin squeezing [51]. Note,when the detuning is sufficiently far-off resonance, all collective sub- and super-radiant modes [23,46] are equally (and thus symmetrically) excited.In this paper, we work in the dispersive regime with a few thousands of atoms and can safely ignore the atom-atom interaction caused by multiple scattering，and hence the collective atomic system satisfy the exchange symmetry.

To study the spin squeezing dynamics,we follow the method first developed by Norris [52]. We employ a firstprinciples stochastic master equation for the collective state of $N _ { A }$ atoms,

$$
\mathrm { d } \hat { \rho } = \left. \mathrm { d } \hat { \rho } \right| _ { Q N D } + \left. \mathrm { d } \hat { \rho } \right| _ { o p } .
$$

The first term on the right-hand side of Eq.(18) governs the spin dynamics arising from QND measurement [9

$$
\left. \mathrm { d } \hat { \rho } \right. _ { Q N D } = \sqrt { \frac { \kappa } { 4 } } \mathcal { H } \left[ \hat { \rho } \right] \mathrm { d } W + \frac { \kappa } { 4 } \mathcal { L } \left[ \hat { \rho } \right] \mathrm { d } t ,
$$

where $\kappa$ is the measurement strength defined in Eq. (12), and $\mathrm { d } W$ isa stochastic Wiener interval. The conditional dynamics are generated by superoperators that depend on the collective spin

$$
\begin{array} { l } { { \displaystyle \mathcal { H } \left[ \hat { \rho } \right] = \hat { F } _ { z } \hat { \rho } + \hat { \rho } \hat { F } _ { z } - 2 \big \langle \hat { F } _ { z } \big \rangle \hat { \rho } , } } \\ { { \displaystyle \mathcal { L } \left[ \hat { \rho } \right] = \hat { F } _ { z } \hat { \rho } \hat { F } _ { z } - \frac { 1 } { 2 } \Big ( \hat { \rho } \hat { F } _ { z } ^ { 2 } + \hat { F } _ { z } ^ { 2 } \hat { \rho } \Big ) = \frac { 1 } { 2 } \Big [ \hat { F } _ { z } , \Big [ \hat { \rho } , \hat { F } _ { z } \Big ] \Big ] . } } \end{array}
$$

The second term governs decoherence arising from optical pumping, which acts locally on each atom, $\mathrm { d } \hat { \rho } | _ { o p } =$ （204号 $\begin{array} { r } { \sum _ { n } ^ { N _ { A } } \mathcal { D } ^ { ( n ) } \left[ \hat { \rho } \right] \mathrm { d } t } \end{array}$ ，where

$$
\mathcal { D } ^ { ( n ) } [ \hat { \rho } ] = - \frac { i } { \hbar } \Big ( \hat { H } _ { \mathrm { e f f } } ^ { ( n ) } \hat { \rho } - \hat { \rho } \hat { H } _ { \mathrm { e f f } } ^ { ( n ) \dagger } \Big ) + \gamma _ { o p } \sum _ { q } \hat { W } _ { q } ^ { ( n ) } \hat { \rho } \hat { W } _ { q } ^ { ( n ) \dagger } .
$$

Here $\hat { H } _ { \mathrm { e f f } } ^ { ( n ) }$ is the effective nonHermitian Hamiltonian describing the local light shift and absorption by the $n ^ { t h }$ atom and $\hat { W } _ { q } ^ { ( n ) }$ is thejumpoperatorcorrspondingto optical pumping through absorption of a laser photon followed by spontaneous emission of a photon of polarization $q$ [47] (see Appendix A).

The rate of decoherence is characterized by the optical pumping rate, $\gamma _ { o p }$ . Note, the optical pumping superoperator,Eq.(21),is not trace preserving when restricted to a given ground-state hyperfine manifold $f$ . Optical pumping that transfers atoms to the other hyperfine manifold in the ground-electronic state is thus treated as loss. Moreover,if the atoms are placed at the optimal position in the transverse plane, the local field of the guided mode is linearly polarized.In that case the vector light shift vanishes,and for detunings large compared to the excited-state hyperfine splitting,the rank-2 tensor light shift is negligible.The light shift is thus dominated by the scalar component,which has no effect on the spin dynamics. In that case $\begin{array} { r } { \hat { H } _ { \mathrm { e f f } } = - i \frac { \hbar \gamma _ { o p } } { 2 } \hat { \mathbb { 1 } } } \end{array}$ , representing an equal rate of absorption for all magnetic sublevels.

Following the work of Norris [52], the solution to the master equation is made possible by three approximations.Firstly, we restrict the subspace of internal magnetic sublevels that participate in the dynamics. The system is initialized in a spin coherent state,with all atoms spin-polarized along the $x$ -axis.We denote this as the“fiducial state” $| \uparrow \rangle = | f , m _ { x } = f \rangle$ . Through QND measurement,spin squeezing is induced by entanglement with the“coupled state” $| { \downarrow } \rangle = | { f , m _ { x } = f - 1 } \rangle$ .Optical pumping is dominated by “spin flips” $| { \uparrow } \rangle \to | { \downarrow } \rangle$ and “loss” due to pumping to the other hyperfine level. We finally include a third internal magnetic sublevel $| T \rangle = | f , m _ { x } = f - 2 \rangle$ to account for “transfer of coherences” that can occur in spontaneous emission [52,54] (see Fig.5). Restricted to this qutrit basis, the internal hyperfine spin operators are

$$
\begin{array} { l } { \displaystyle { \hat { f } _ { x } = f \hat { \sigma } _ { \uparrow \uparrow } + ( f - 1 ) \hat { \sigma } _ { \downarrow \downarrow } + ( f - 2 ) \hat { \sigma } _ { T T } , } } \\ { \displaystyle { \hat { f } _ { y } = - i \sqrt { \frac { f } { 2 } } \left( \hat { \sigma } _ { \uparrow \downarrow } - \hat { \sigma } _ { \downarrow \uparrow } \right) - i \sqrt { \frac { 2 f - 1 } { 2 } } \left( \hat { \sigma } _ { \downarrow T } - \hat { \sigma } _ { T \downarrow } \right) } } \\ { \displaystyle { \hat { f } _ { z } = \sqrt { \frac { f } { 2 } } \left( \hat { \sigma } _ { \uparrow \downarrow } + \hat { \sigma } _ { \downarrow \uparrow } \right) + \sqrt { \frac { 2 f - 1 } { 2 } } \left( \hat { \sigma } _ { \downarrow T } + \hat { \sigma } _ { T \downarrow } \right) } , } \end{array}
$$

where we have defined the atomic population and coherence operators $\hat { \sigma } _ { b a } = | b \rangle \langle a |$

$$
\begin{array} { r l r } { f ^ { \prime } = 5 \xrightarrow { m ^ { \prime } = 1 } } & { { } \equiv \equiv \equiv \equiv \equiv \equiv \stackrel { 3 } { \equiv } \ \stackrel { 3 } { \equiv } \ \stackrel { 4 } { = } \ \stackrel { 5 } { \equiv } \ } & { { } } & { } \\ { f ^ { \prime } = 2 \therefore \ } & { { } \equiv \equiv \equiv \equiv \stackrel { 3 } { \equiv } \ \stackrel { 4 } { \equiv } \ } & { { } } & { } \\ { m _ { \oplus } \equiv \left. \stackrel { 7 } { \equiv } \right| \left[ \partial _ { x } ^ { y } \right] ^ { \prime } \right| \left[ \left( \left[ \begin{array} { l } { 1 } \\ { 2 } \\ { 3 } \\ { 4 } \end{array} \right] \right) ^ { \prime } \right] ^ { \prime } } & { { } } & { } \\ { f = 4 \ \cdots \ } & { { } \equiv \left. \stackrel { 7 } { \equiv } \ \stackrel { \ \stackrel { 8 } { \equiv } \ } { \equiv } \ \stackrel { \ 9 } { \equiv } \ \stackrel { \ 9 } { \equiv } \ } & { { } \stackrel { 1 1 } { \oplus } \ } & { { \ 4 } } \\ { m _ { \oplus } = 1 } & { { } \ 2 } & { { } \equiv \ \stackrel { 1 } { \equiv } \ } & { { } } \end{array}
$$

FIG.5.Schematic energy level diagram for cesium atoms probed on the D2 line, $6 S _ { 1 / 2 } \  \ 6 P _ { 3 / 2 }$ .Relevant dynamics are restricted to a truncated qutrit subspace of ground levels.Atoms are prepared in the fiducial state $\left| \uparrow \right.$ ，and driven by $x$ -polarized $( \pi )$ light． The Faraday rotation corresponds to coherent scattering of $\pi  \sigma$ in this basis,and measurement backaction leads to entanglement between pairs of atoms in $| { \uparrow } \rangle ~ = ~ | { f = 4 , m _ { x } = 4 } \rangle$ and the coupled state $| { \downarrow } \rangle = | f = 4 , m _ { x } = 3 \rangle$ ．Optical pumping can cause spin flips $| { \uparrow } \rangle \to | { \downarrow } \rangle$ and $| \downarrow   | T  = | f = 4 , m _ { x } = 2 $ .The latter process is included to account for transfer of coherences. The detuning $\Delta$ is taken to be large compared to the excited state hyperfine splitting.

Secondly, we assume the collective state is symmetric under exchange of spins. This approximation is valid when all atoms see the same probe intensity and in the far-detuning regime when all sub- and super-radiant modes are equally excited.With this,we can limit our attention to the symmetric subspace and define,for example,the symmetric two-body covariances by

$$
\langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \rangle _ { s } \equiv \frac { 1 } { 2 } \Big [ \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \rangle + \langle \Delta \sigma _ { b a } ^ { ( 2 ) } \Delta \sigma _ { d c } ^ { ( 1 ) } \rangle \Big ] ,
$$

where the superscripts,(1） and (2)，label arbitrary tao difsymtetey $\left. \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \right. _ { s } ~ = ~ \left. \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \right. ~ =$ $\left. \Delta \sigma _ { b a } ^ { ( 2 ) } \Delta \sigma _ { d c } ^ { ( 1 ) } \right.$ , which reduces the number of $n$ -body moments required to simulate the spin dynamics of the ensemble.

Thirdly, we make the Gaussian approximation，valid for large atomic ensembles,so that the many-body state is fully characterized by one- and two-body correlations. Equivalently, the state is defined by the one- and twobody density operators, with matrix elements palb (ba)，Pac,bd $\rho _ { \underline { { a c } } , b d } ^ { ( 1 , 2 ) } =  { \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \rangle } _ { s }$ in the symmetric sabspace. We track the evolution of the correlation functions through a set of coupled differential equations [52]. Optical pumping,acting locally, couples only $n$ -body correlations to themselves,e.g.,

$$
\begin{array} { r l } & { \left. d \big \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \big \rangle _ { s } \right| _ { o p } } \\ & { = \big \langle \mathcal { D } ^ { \dagger } [ \Delta \sigma _ { b a } ^ { ( 1 ) } ] \Delta \sigma _ { d c } ^ { ( 2 ) } \big \rangle _ { s } d t + \big \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \mathcal { D } ^ { \dagger } [ \Delta \sigma _ { d c } ^ { ( 2 ) } ] \big \rangle _ { s } d t . } \end{array}
$$

QND measurement generates higher order correlations according to

$$
d \big \langle \hat { \sigma } _ { b a } \big \rangle \big | _ { Q N D } = \frac { \kappa } { 4 } \big \langle \mathcal { L } ^ { \dagger } \left[ \hat { \sigma } _ { b a } \right] \big \rangle d t + \sqrt { \frac { \kappa } { 4 } } \big \langle \mathcal { H } ^ { \dagger } \left[ \hat { \sigma } _ { b a } \right] \big \rangle d W .
$$

We can truncate this hierarchy in the Gaussian approximation,setting third order cumulants to zero.Thus, for example,

$$
\begin{array} { r l r } { \left. { \left. d \big \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \big \rangle _ { s } \right| _ { Q N D } } } \\ & { = \left. d \big \langle \hat { \sigma } _ { b a } ^ { ( 1 ) } \hat { \sigma } _ { d c } ^ { ( 2 ) } \big \rangle _ { s } \right| _ { Q N D } - \left. \big \langle \hat { \sigma } _ { b a } \big \rangle \right| _ { Q N D } \left( \left. d \big \langle \hat { \sigma } _ { d c } \big \rangle \right| _ { Q N D } \right) } \\ & { } & { - \left. \big \langle \hat { \sigma } _ { d c } \big \rangle \right| _ { Q N D } \left( d \big \langle \hat { \sigma } _ { b a } \big \rangle \big | _ { Q N D } \right) - d \big \langle \sigma _ { b a } \big \rangle \right| _ { Q N D } d \big \langle \sigma _ { d c } \big \rangle \big | _ { Q N D } } \\ & { } & { = - \kappa \big \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta F _ { z } \big \rangle _ { s } \big \langle \Delta F _ { z } \Delta \sigma _ { d c } ^ { ( 2 ) } \big \rangle _ { s } d t , \qquad \quad \quad ( 2 6 ) } \end{array}
$$

where we have employed the Ito calculus $d W ^ { 2 } ~ = ~ d t$ Note,by setting the third-order cumulants to zero,the contribution of the $\mathcal { L }$ superoperator to dynamics of $d \big < \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \big > _ { s } \Big | _ { \mathscr { L } } =$ $\begin{array} { r } { \frac { \kappa } { 4 } \big \langle \mathcal { L } ^ { \dagger } \left[ \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \right] \big \rangle _ { s } d t = 0 } \end{array}$ This indicates the events of no-photon detection under the Gaussian state approximation do not affect atom-atom correlations; the measurement backaction and squeezing arise from the homodyne detection in the guided modes.

Using all of the approximations above,the collective spin dynamics can be efficiently calculated for the ensemble of qutrits (dimension $d = 3$ ）with $d ^ { 2 } = 9$ equations   
o $\left. \hat { \sigma } _ { b a } \right.$ 景 $d ^ { 2 } ( d ^ { 2 } + 1 ) / 2 = 4 5$ $\left. \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \right. _ { s }$ atoms. With this formalism in hand,we can calculate the squeezing parameter, Eq.(16),as a function of time by finding time-dependent solutions for the one-body av  
erages $\left. \hat { f } _ { x } \right.$ and $\left. \Delta f _ { z } ^ { 2 } \right.$ ，and the two-body covariances $\left. \Delta f _ { z } ^ { ( 1 ) } \Delta f _ { z } ^ { ( 2 ) } \right.$ . The detailed approach to calculating the collective spin dynamics can be found in Appendix A.

Using this formalism,we calculate the squeezing of an ensemble of cesium atoms,initially spin-polarized in the $6 S _ { 1 / 2 } , | f = 4 , m _ { x } = 4 \rangle$ state.We choose the guided mode frequency near the D2 resonance, $6 S _ { 1 / 2 }  6 P _ { 3 / 2 }$ ，detuned far compared to the excited-state hyperfine split ting.In Fig.6,we plot the reciprocal of the spin squeezing parameter as a function of time and its peak as a function of atom number, $N _ { A }$ ,forboth the optical nanofiber and the square waveguide cases. By placing atoms 200 nm away from the nanofiber surface ( $r _ { \perp } ^ { \prime } = 1 . 8 a$ )，our simulations for 2500 atoms yield 6.3dB of squeezing. Using the square waveguide platform with the same number of atoms placed 15onm away from the surface,our calculation yields 12.9dB squeezing. As we have shown in Sec.II, the square waveguide geometry enhances the anisotropic contrast of the two orthogonal guided modes and dramatically reduces the relative local intensity when the atoms are placed on the $y$ -axis. This results in a large cooperativity,higher peak spin squeezing,achieved inshorter time,and with a relatively slower decay when compared to the nanofiber.In addition,in Figs.6(b) and 6(d) we show how the peak squeezing scales with the number of trapped atoms when the atom positions arefixedasabove.

![](images/8cd7019690f64b9f331b9409c667d9c42ae1ea2abcbec68322f6bcbe5c285a16.jpg)  
FIG.6. The reciprocal spin-squeezing parameter,Eq. (16). Subfigs.(a) and (c) are plots of $\xi ^ { - 2 }$ as a function of time in units of the optical pumping rate $\gamma _ { o p }$ ，for the cylindrical nanofiber and square waveguide,respectively, for $N _ { A } = 2 5 0 0$ with other parameters given in the text.These curves peak at time determined by the detailed balance of reduced uncertainty due to QND measurement and decoherence due to optical pumping.Subfigs.(b) and(d) show the plots of the peak value $\xi ^ { - 2 }$ as a function of $N _ { A }$ for the nanofiber and square waveguide correspondingly.

In the absence of any other noise,the cooperativity of atom-light coupling increases as the atoms are placed closer to the waveguide surface. Figs.7(a) and 7(c) show the peak squeezing as a function of $r _ { \perp }$ for both nanofiber and square waveguide geometries with 25oo atoms. With the same setting，we also plot out the cooperativity, $C _ { 1 }$ on a logarithm scale in Figs.7(b) and 7(d) as a function of atom radial distance to the center of both waveguide geometries. We find that C1 is proportional to e-βrl and the peak squeezing scales as $\sqrt { O D }$ ，where $\beta \approx 1 . 6 5 / a$ for the nanofiber and $\beta \approx 2 . 1 4 \times 2 / w$ for the square waveguide with 25oo atoms. The cooperativity of the square waveguide increases faster than the nanofiber as the atoms approach to the waveguide surface.

![](images/b1d5f8bcfdd2e8d95a51ebe33b13299b5cc9439d35ca69cf30bca26d715ed43a.jpg)  
FIG.7.Peak squeezing parameter((a) and(c)) and cooperativity at the optimal azimuthal trapping position((b)and (d)) asa function of the radial distance to the waveguide axis,for （204号 $N _ { A } ~ = ~ 2 5 0 0$ ，with other parameters given in the text. (a) and(b)are for the nanofiber case;(c)and (d) are for the square waveguide case.

# IV.SUMMARY AND OUTLOOK

In this paper we studied the cooperativity of the atomphoton interface for two nanophotonic geometries:a cylindrical nanofiber and a square waveguide.Due to the anisotropic nature of the guided modes,one can strongly enhance the cooperativity by trapping atoms at positions that maximize the rate at which photons are forwardscattered into the orthogonally polarized guided mode, while simultaneously minimizing the rate of which they are scattered into free space. Counterintuitively, the optimal geometry is such that atoms at a certain distance from the surface are trapped at the azimuthal angle of minimal intensity of the probe.We applied this idea to study the generation of a spin squeezed state of an ensemble atoms induced by QND measurement,mediated by the Faraday interaction in the dispersive regime.With realistic parameters,our simulation shows more than 6dB of squeezing for a cylindrical nanofiber or l2dB for the square waveguide with 25oo atoms. The amount of spin squeezing we predict based on Faraday effect is substantially larger than for the birefringence-based spin squeezing protocol studied in our earlier work [24]. Although we have only considered a cylindrical nanofiber and a square waveguide geometries,the ideas presented in this paper are applicable to other nanophotonic waveguide geometries which could show enhanced cooperativity. In addition,our model of decoherence,simplified when the detuning is large compared to the excited state hyperfine splitting,is almost certainly not the optimal operating condition.

Our simulations are based on a first-principles stochastic master equation that includes QND measurementbackaction that generates entanglement and results in spin squeezing，as well as decoherence due to optical pumping by spontaneous photon scattering [9，24，52]. This simulation is made possible by a set of simplifying assumptions: (i) we restrict each atom to a qutrit,embedded in the hyperfine manifold of magnetic sublevels; (ii) the state is exchange-symmetric with respect to any two atomic spins;(ii) the many-body state is fully characterized by one- and two-body correlations (the Gaussianapproximation).With these,we solve for the metro logically relevant squeezing parameter as a function of time and see the tradeoffs between QND measurement and decoherence for various geometries and choices of parameters. Our method is extendable to include higher or der correlations,which become manifest for large squeezing,when the Holstein-Primakoff (Gaussian) approximation breaks down.The computational framework we have developed here should allow us to study $n$ -bodymoments with an acceptable computational load.

In future work we intend to extend our analysis in a number of directions.While we focussed here on the enhancement of the cooperativity in a nanophotonic waveguide-based QND measurement, we did not fully analyze the impact of Purcell effect and the modification of spontaneous emission rates in our simulations.We have also neglected here the motion of atoms in the optical lattice.In practice,however，these effects are important，the latter having been observed in the nanofiber experiments [37,38，55,56]. We will include these in future studies,with an eye towards the development of new strategies for atomic cooling and state initialization in the nanophotonic platforms [57]. We expect that our proposed geometry,which places the atoms at positions of minimum intensity, could also help reduce the perturbation on the motion of trapped atoms due to the probe that causes a disturbance in the signal [37].

Finally,we have studied here the dispersive regime of a QND measurement,where the probe light is detuned faroff-resonance,and multiple scattering of photons among atoms is negligible. To extend our theory, it is necessary to include the collective effects such as super and subradiance [23,46, 58],with applications including quantum memories [34, 59], the generation of matrix product states and cluster states [60-64].

# V.ACKNOWLEDGMENTS

We thank Perry Rice for extensive discussions on suband super-radiance and its effects on collective spin squeezing in the dispersive coupling regime and Ezad Shojaee for helpful discussions on the effects of decoherence on spin squeezing. We also thank Poul Jessen for insightful discussions regarding the enhancement of cooperativity. We acknowledge the UNM Center for Advanced Research Computing for computational resources used in this study. This work was supported by the NSF. under grant PHY-1606989,and the Laboratory Directed Research and Development program at Sandia National Laboratories. Sandia is a multi-program laboratory operated by the National Technology and Engineering Solutions of Sandia (NTESS),a wholly owned subsidiary of Honeywell International Northrop Grumman and Universities Research Association,for theUnited States Department of Energy's National Nuclear Security Administration.

[1] H.Kimble,Physica Scripta 1998,127 (1998). [2] J.M.Raimond,M. Brune,and S.Haroche,Rev.Mod. Phys. 73, 565 (2001). [3] R.Miller,T.E.Northup,K.M.Birnbaum，A.Boca, A.D.Boozer，and H. J. Kimble,J. Phys. B 38,S551 (2005). [4] A. Akimov,A. Mukherjee, C. Yu, D. Chang,A. Zibrov, P. Hemmer,H. Park, and M. Lukin,Nature 450, 402 (2007). [5] N．Akopian，N.Lindner，E.Poem，Y.Berlatzky, J.Avron，D.Gershoni,B.Gerardot， and P. Petroff, Phys.Rev.Lett.96,130501 (2006). [6] R.-B. Liu, W. Yao， and L. Sham, Advances in Physics 59, 703 (2010). [7] A．Wallraff,D.I. Schuster,A. Blais,L. Frunzio,R.-S. Huang,J. Majer,S.Kumar,S.M. Girvin， and R. J. Schoelkopf, Nature 431, 162 (2004). [8] M.Hofheinz,H. Wang,M.Ansmann,R.C.Bialczak, E. Lucero,M. Neeley, A. O'connell, D. Sank,J. Wenner, J. M. Martinis, et al., Nature 459, 546 (2009). [9]B.Q.Baragiola,L.M.Norris,E.Montano,P.G.Mickelson, P. S. Jessen，and I. H. Deutsch, Phys. Rev.A 89, 033850 (2014).   
[10]A.Kuzmich,N.P.Bigelow，and L.Mandel,EPL(Europhysics Letters) 42, 481 (1998).   
[11] Y.Takahashi，K.Honda，N.Tanaka，K.Toyoda, K.Ishikawa， and T.Yabuzaki,Phys.Rev.A 60,4974 (1999).   
[12] J.Appel,P. J.Windpassinger,D.Oblak，U.B.Hoff, N. Kjaergaard， and E. S. Polzik,PNAS 106，10960 (2009).   
[13] T. Takano,M. Fuyama,R.Namiki， and Y. Takahashi, Phys. Rev. Lett. 102,033601 (2009).   
[14] R.J. Sewel, M.Koschorreck,M. Napolitano,B.Dubost, N. Behbood, and M. W.Mitchell, Phys.Rev.Lett.109, 253605 (2012).   
[15] M.H. Schleier-Smith,I. D.Leroux,and V. Vuletic,Phys. Rev. Lett. 104, 073604 (2010).   
[16] K. C. Cox, G.P. Greve, J. M. Weiner， and J. K. Thompson,Phys.Rev.Lett.116,093602 (2016).   
[17] O.Hosten,N.J. Engelsen,R.Krishnakumar,and M.A. Kasevich, Nature 529, 505 (2016).   
[18] E.Vetsch，D.Reitz，G. Sagué,R. Schmidt，S.T. Dawkins, and A. Rauschenbeutel, Phys.Rev.Lett.104, 203603 (2010).   
[19]D.E.Chang, J.I. Cirac，and H. J.Kimble,Phys.Rev. Lett. 110, 113606 (2013).   
[20] C.-L.Hung,S.M.Meenehan,D.E.Chang,O.Painter, and H. J. Kimble,New Journal of Physics 15,083026 (2013).   
[21] S.-P. Yu,J.D.Hood,J. A. Muniz,M. J. Martin, R.Norte,C.-L.Hung，S.M.Meenehan，J.D.Cohen, O.Painter, and H. J. Kimble, Applied Physics Letters 104, 111103 (2014).   
[22] J.S.Douglas,H. Habibian,C.-L.Hung,A.Gorshkov, H. J. Kimble, and D. Chang, Nature Photonics (2015), 10.1038/nphoton.2015.57.   
[23]A.Asenjo-Garcia，M.Moreno-Cardoner，A.Albrecht, H. J. Kimble，and D. E. Chang, Phys.Rev. X 7, 031024 (2017).   
[24] X. Qi,B.Q.Baragiola,P.S. Jessen，and I.H. Deutsch, Phys. Rev. A 93, 023817 (2016).   
[25] A. Goban, K. S. Choi, D. J. Alton, D.Ding, C.Lacroute, M.Pototschnig,T.Thiele,N.P. Stern，and H.J.Kimble, Phys. Rev.Lett.109,033603 (2012).   
[26] D.Reitz，C.Sayrin，R.Mitsch，P.Schneeweiss，and A. Rauschenbeutel, Phys. Rev. Lett.110, 243603 (2013).   
[27]J.Lee,J.A.Grover,J.E.Hoffman,L.A.Orozco，and S.L.Rolston，Journal of Physics B:Atomic,Molecular and Optical Physics 48, 165004 (2015).   
[28] A. Goban,C.-L. Hung, S.-P.Yu, J. D. Hood,J.A. Muniz,J.H. Lee,M. J. Martin,A. C.McClung,K. S. Choi, D.E. Chang, O.Painter, and H. J. Kimble, Nature Communications 5, 3808 (2014).   
[29] D.Reitz,C.Sayrin,B.Albrecht,I.Mazets,R.Mitsch, P. Schneeweiss， and A. Rauschenbeutel, Phys.Rev.A 89, 031804 (2014).   
[30] J.Volz,M. Scheucher, C.Junge,and A.Rauschenbeutel, Nature Photonics 8, 965 (2014).   
[31]J.-B.Béguin,E.Bookjans,S.Christensen,H. Sorensen, J. Müller, E. Polzik,and J.Appel, Physical Review Let ters 113, 263603 (2014).   
[32]R.Mitsch,C.Sayrin,B.Albrecht,P. Schneeweiss，and A. Rauschenbeutel, Phys.Rev.A 89, 063829 (2014).   
[33] S. Kato and T. Aoki，Phys. Rev.Lett.115，093603 (2015).   
[34] C.Sayrin,C.Clausen,B.Albrecht,P. Schneeweiss，and A. Rauschenbeutel, Optica 2, 353 (2015).   
[35] C. Sayrin,C. Junge,R.Mitsch,B.Albrecht,D.O'Shea, P.Schneeweiss,J. Volz, and A. Rauschenbeutel,Phys. Rev. X 5, 041036 (2015).   
[36] R.Mitsch,C. Sayrin,B.Albrecht,P.Schneeweiss，and A. Rauschenbeutel, Nature Communications 5,5713 (2014).   
[37] P. Solano,F. K. Fatemi, L.A. Orozco,and S.L. Rolston, Opt.Lett.42,2283 (2017).   
[38] J.-B.Béguin, J.H. Müller, J. Appel,and E. S. Polzik, ArXiv e-prints (2017),arXiv:1708.08387 [quant-ph].   
[39] Characterizations of SiN and AiN microfabricated waveguides for evanescent-field atom-trap applications,Vol.62 (American Physical Society, 2017).   
[40] G.A. Smith, S.Chaudhury, and P. S. Jessen, Journal of Optics B: Quantum and Semiclassical Optics 5, 323 (2003).   
[41] S. T. Dawkins,R. Mitsch,D. Reitz, E. Vetsch， and A. Rauschenbeutel, Phys.Rev. Lett.107, 243601 (2011).   
[42] F.L.Kien, J. Liang,K.Hakuta,and V.Balykin, Optics Communications 242, 445 (2004).   
[43] E. Vetsch，Optical interface based on a nanofiber atom-trap, Ph.D. thesis, Johannes Gutenberg-Universität Mainz, Mainz,Germany (2010).   
[44] A. B. Fallahkhair, K. S. Li, and T. E. Murphy, Journal of Lightwave Technology 26,1423 (2008).   
[45] J. Lee, D. Park, S. Mittal, M. Dagenais, and S. Rolston, New Journal of Physics 15, 043010 (2013).   
[46] A. Asenjo-Garcia, J. D. Hood, D. E. Chang，and H. J. Kimble, Phys. Rev. A 95,033818 (2017).   
[47] I. H. Deutsch and P. S. Jessen, Optics Communications 283, 681 (2010).   
[48] F.Le Kien, S.D.Gupta,K.P.Nayak,and K. Hakuta, Phys. Rev.A 72, 063815 (2005).   
[49] F.L. Kien and K. Hakuta,Phys. Rev. A 77,013801 (2008).   
[50] D.J. Wineland,J.J. Bollinger, W.M. Itano,F.L. Moore, and D. J. Heinzen, Phys. Rev. A 46, R6797 (1992).   
[51] X. Wang and B. C. Sanders, Phys. Rev. A 68, 012101 (2003).   
[52] L. M. Norris, Internal Spin Control, Squeezing and Decoherence in Ensembles of Alkali Atomic Spins, Ph.D. thesis, University of New Mexico (2014), arXiv:1410.0089 [quant-ph].   
[53] K. Jacobs and D. A. Steck, Contemporary Physics 47, 279 (2006).   
[54] L.M. Norris,C.M. Trail, P.S.Jessen,and I.H.Deutsch, Phys. Rev. Lett.109,173603 (2012).   
[55] P. Solano,J.A. Grover, Y.Xu,P.Barberis-Blostein, J. N. Munday,L. A. Orozco, W. D. Philips, and S. L. Rolston, ArXiv e-prints (2017), arXiv:1704.08741 [quant-ph].   
[56] P. Solano,J.A. Grover, J.E. Hoffman, S.Ravets, F. K. Fatemi，L.A.Orozco， and S.L. Rolston (Academic Press, 2017) pp. 439-505.   
[57] Y.Meng,A.Dareau, P. Schneeweiss,and A.Rauschenbeutel,ArXiv e-prints (2017),arXiv:1712.05749 [quantph].   
[58] P.Solano,P. Barberis-Blostein，F. K.Fatemi,L．A. Orozco，and S. L. Rolston， ArXiv e-prints(2017), arXiv:1704.07486 [quant-ph].   
[59] B.Gouraud，D.Maxein，A. Nicolas,O. Morin， and J. Laurat, Phys. Rev. Lett. 114,180503 (2015).   
[60] S.E.Economou,N.Lindner， and T.Rudolph,Phys. Rev.Lett.105,093601 (2010).   
[61] P.Lodahl, S.Mahmoodian,S. Stobbe,A.Rauschenbeutel,P. Schneeweiss,J. Volz,H. Pichler，and P. Zoller, Nature 541, 473 (2017).   
[62] I. Schwartz,D. Cogan，E. R. Schmidgall，Y. Don, L.Gantz,O.Kenneth,N.H. Lindner,and D.Gershoni, Science ，aah4758 (2016).   
[63] H. Pichler and P. Zoller,Phys.Rev.Lett.116,093601 (2016).   
[64]H.Pichler,S.Choi,P.Zoller，and MD.Lukin,ArXiv e-prints (2017),arXiv:1702.02119 [quant-ph]   
[65]M.Saffman,D.Oblak,J.Appel,and E.S.Polzik,Phys ical Review A 79, 023831 (2009).   
[66] E.Montano,Quantum control and squeezing of collective spins,Ph.D. thesis,University of Arizona (2015).

# Appendix A:Modelingcollectivespindynamics

In this Appendix we give further details of the equations of motion for spin squeezing as a function of time, as discussed in the main text,building on the work of Norris [52]. In the symmetric subspace,and in the Gaussian approximation,we track a set of one- and two-body correlation functions that determine the metrologically relevant squeezing parameter,Eqs.(16,17). The evolution is determined by the dynamics induced by the QND measurement and decoherence due to optical pumping, Eqs.(18-21). For concreteness,we consider here cesium atoms,initially prepared in a spin coherent state, with all atoms in the stretched state polarized along the $x$ -axis, $\left| \uparrow \right. = | 6 S _ { 1 / 2 } , f = 4 , m _ { x } = 4 \rangle$ . The atoms are trapped on the $y$ -axis at a distance $r _ { \perp } ^ { \prime }$ from the core axis of the waveguide and are probed with guided light in the $H$ -mode,which has linear polarization in the $x$ 1 direction at the position of the atoms. We take the detuning large compared to the excited state hyperfine splitting，e.g.，4 GHz red detuned from the D2 line, $\vert 6 S _ { 1 / 2 } , f = 4 \rangle  \ \vert 6 P _ { 3 / 2 } , f ^ { \prime } = 3 \rangle$ . Spontaneous emission from the probe may result in optically pumping of atoms to the other hyperfine manifold, $f = 3$ ；we treat this as a loss channel under the approximation that,over the time interval of interest,there isa negligible probability for these atoms to repump to $f = 4$ . We also include a bias static magnetic field along the $z$ -axis.This does not affect the QND measurement of $F _ { z }$ ，but ultimately,we must calculate all dynamics in the rotating frame.

Spontaneous emission，optical pumping,and the re sulting decoherence acts locally on each atomic spin,governed by the master equation,Eq. (21).For light linearly polarized in the $x$ -direction,and for detunings large compared to the excited state hyperfine splitting,this takes the simplified form [47]

$$
\begin{array} { r l } & { \quad \frac { \mathrm { d } \hat { \rho } ^ { ( n ) } } { \mathrm { d } t } \bigg \vert _ { o p } = \mathcal { D } [ \hat { \rho } ^ { ( n ) } ] } \\ & { = - \cfrac { i } { \hbar } [ \hat { H } _ { A } , \hat { \rho } ^ { ( n ) } ] - \gamma _ { o p } \hat { \rho } ^ { ( n ) } + \cfrac { \gamma _ { o p } } { 4 f ^ { 2 } } \bigg ( \hat { f } _ { + } ^ { ( n ) } \hat { \rho } ^ { ( n ) } \hat { f } _ { - } ^ { ( n ) } + \hat { f } _ { - } ^ { ( n ) } \hat { \rho } ^ { ( n ) } \hat { f } _ { + } ^ { ( n ) } \bigg ) , } \end{array}
$$

where f± （20 $\hat { f } _ { \pm } ^ { ( n ) } = \hat { f } _ { z } ^ { ( n ) } \pm i \hat { f } _ { y } ^ { ( n ) }$ are the raising and lowering operators for projection of spin along the $x$ -axis，and $\begin{array} { r } { \gamma _ { o p } = \frac { \Gamma _ { A } ^ { 2 } } { 1 8 \Delta ^ { 2 } } \ \sigma _ { 0 } \frac { I _ { i n } } { \hbar \omega _ { 0 } } } \end{array}$ T0Hin is the optical pumping for linear polarization in the far-detuned limit，given intensity $I _ { i n }$ at the position of the atom (we assume that all atoms are trapped the same distance for the waveguide,and thus see the same intensity).The atomic Hamiltonian is （204 $\begin{array} { r } { \hat { H } _ { A } = \sum _ { n } \hbar \Omega _ { 0 } \hat { f } _ { z } ^ { ( n ) } + \hat { H } _ { L S } } \end{array}$ , the sum of the Zeeman interaction with a bias magnetic field,giving rise to Larmor precession at frequency $\Omega _ { 0 }$ ，and the light shift, $\hat { H } _ { L S } =$ $\hbar \chi _ { 3 } \hat { F } _ { z } \hat { S } _ { 3 }$ , due to the probe. Even for far detuning, the residual tensor light shift cannot be neglected as it scales at $1 / \Delta ^ { 2 }$ , the same as $\gamma _ { o p }$ and $\kappa$ . In principle a two-color probe can remove the tensor term which would otherwise lead to a degradation of the mean spin,and thus a reduction metrologically useful squeezing [65, 66]. We neglect this effect here.Finally,going to the rotating frame at the Larmor frequency, $\hat { f } _ { x } ^ { ( n ) }  \hat { f } _ { x } ^ { ( n ) } \cos ( \Omega _ { 0 } t ) + \hat { f } _ { y } ^ { ( n ) } \sin ( \Omega _ { 0 } t )$ $\hat { f } _ { y } ^ { ( n ) }  \hat { f } _ { y } ^ { ( n ) } \cos ( \Omega _ { 0 } t ) - \hat { f } _ { x } ^ { ( n ) } \sin ( \Omega _ { 0 } t )$ ， and averaging the rapidly oscillating terms (RWA)，the master equation takes the form

$$
\begin{array} { r l r } {  {  \frac { \mathrm { d } \hat { \rho } ^ { ( n ) } } { \mathrm { d } t } | _ { o p } = \mathcal { D } [ \hat { \rho } ^ { ( n ) } ] } } \\ & { \Rightarrow - \gamma _ { o p } \hat { \rho } ^ { ( n ) } } \\ & { } & { + \frac { \gamma _ { o p } } { 8 f ^ { 2 } } ( \hat { f } _ { x } ^ { ( n ) } \hat { \rho } ^ { ( n ) } \hat { f } _ { x } ^ { ( n ) } + \hat { f } _ { y } ^ { ( n ) } \hat { \rho } ^ { ( n ) } \hat { f } _ { y } ^ { ( n ) } + 2 \hat { f } _ { z } ^ { ( n ) } \hat { \rho } ^ { ( n ) } \hat { f } _ { z } ^ { ( n ) } ) . } \end{array}
$$

With atoms initially prepared in the “fiducial state,” $| { \uparrow } \rangle = | f = 4 , m _ { x } = 4 \rangle$ ，we include in the dynamics the "coupled state,” $| { \downarrow } \rangle = | f = 4 , m _ { x } = 3 \rangle$ ，and the“transfer state,” $| T \rangle \ = \ | f = 4 , m _ { x } = 2 \rangle$ .Restricted to this qutrit substate, the spin projector operators $\{ \hat { f } _ { x } , \hat { f } _ { y } , \hat { f } _ { z } \}$ are given in Eqs. (22).

With all the components of the stochastic master equation defined in Eq.(18-21)，one can derive the equations of motion of one- and two-body moments straightforwardly using the symmetric Gaussian state approximation. Some explicit results have been given in Eq. (24 -26). The equation of motion for the optical pumping dynamics of the one-body moment $\left. \hat { \sigma } _ { b a } \right.$ , is given by

$$
d \langle \hat { \sigma } _ { b a } \rangle | _ { o p } = \langle D ^ { \dagger } [ \hat { \sigma } _ { b a } ] \rangle d t = \sum _ { c , d } \mathrm { t r } ( \mathcal { D } ^ { \dagger } [ \hat { \sigma } _ { b a } ] \hat { \sigma } _ { d c } ) \langle \hat { \sigma } _ { d c } \rangle d t .
$$

The equations of two-body moments of the optical pump ing can be derived similarly. Continued from Eq. (24), we have

$$
\begin{array} { r l } & { \quad d \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \rangle _ { s } \Big | _ { o p } } \\ & { = \langle \Delta \mathcal { D } ^ { \dagger } [ \sigma _ { b a } ^ { ( 1 ) } ] \Delta \sigma _ { d c } ^ { ( 2 ) } \rangle d t + \langle \Delta \sigma _ { b a } ^ { ( 1 ) } \Delta \mathcal { D } ^ { \dagger } [ \sigma _ { d c } ^ { ( 2 ) } ] \rangle _ { s } d t } \\ & { = \displaystyle \sum _ { m , n } \mathrm { t r } \big ( \mathcal { D } ^ { \dagger } [ \hat { \sigma } _ { b a } ] \hat { \sigma } _ { m n } \big ) \big \langle \Delta \sigma _ { m n } ^ { ( 1 ) } \Delta \sigma _ { d c } ^ { ( 2 ) } \big \rangle _ { s } } \\ & { \quad + \displaystyle \sum _ { m , n } \mathrm { t r } \big ( \mathcal { D } ^ { \dagger } [ \hat { \sigma } _ { d c } ] \hat { \sigma } _ { m n } \big ) \big \langle \Delta \hat { \sigma } _ { b a } ^ { ( 1 ) } \Delta \sigma _ { m n } ^ { ( 2 ) } \big \rangle _ { s } . } \end{array}
$$

In deriving Eqs.(25) and (26)，we have used the Gaussian state assumption to write three-body moments in connection to one- and two-body moments, $\left. { \hat { A } } { \hat { B } } { \hat { C } } \right. =$ $\langle \hat { A } \hat { B } \rangle \langle \hat { C } \rangle + \langle \hat { A } \hat { C } \rangle \langle \hat { B } \rangle + \langle \hat { B } \hat { C } \rangle \langle \hat { A } \rangle - 2 \langle \hat { A } \rangle \langle \hat { B } \rangle \langle \hat { C } \rangle$ .If only keeping coherence operators of the nearest coupling states, Eqs.(A3) and (A4) recover the same results found by Norris [52].

We apply similar techniques to derive the equations of motion due to QND measurement Eqs.(25) and(26) to yield

$$
\begin{array} { c } { \displaystyle d \big \langle \hat { \sigma } _ { b a } \big \rangle \big | _ { Q N D } = \frac { \kappa } { 4 } \sum _ { c , d } \mathrm { t r } \left( \mathcal { L } ^ { \dagger } \left[ \hat { \sigma } _ { b a } \right] \hat { \sigma } _ { d c } \right) \big \langle \hat { \sigma } _ { d c } \big \rangle d t } \\ { \displaystyle + \sqrt { \frac { \kappa } { 4 } } \sum _ { c , d } \mathrm { t r } \left( \mathcal { H } ^ { \dagger } [ \hat { \sigma } _ { b a } ] \hat { \sigma } _ { d c } \right) \big \langle \hat { \sigma } _ { d c } \big \rangle d W . } \end{array}
$$

$$
\begin{array} { r l } & { \quad \sin ( 2 \theta ) + \frac { \pi ^ { 2 } } { 2 } \sin ( 2 \theta ) } \\ & { = \sqrt { \frac { \pi ^ { 2 } } { 2 } } \left( \frac { \sin ( 2 \theta ) } { 2 } \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) \right) } \\ & { \quad + \frac { \sqrt { 2 } } { 2 } \left( \frac { \sin ( 2 \theta ) } { 2 } \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) \right) } \\ & { \quad + \frac { \sqrt { 2 } } { 2 } \left( \frac { \sin ( 2 \theta ) } { 2 } \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) \right) } \\ & { \quad - \sqrt { 2 } \cos ( 2 \theta ) \cos ( 2 \theta ) } \\ & { \quad - \sqrt { 2 } \cos ( 2 \theta ) + \sin ( 2 \theta ) } \\ & { \quad - \cos ( 2 \theta ) } \\ & { \quad \sqrt { 2 } \cos ( 2 \theta ) } \\ & { = \sqrt { \frac { \pi ^ { 2 } } { 2 } } \left( \frac { \sin ( 2 \theta ) } { 2 } \cos ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) \right) } \\ & { \quad + \frac { \sqrt { 2 } } { 2 } \left( \frac { \sin ( 2 \theta ) } { 2 } \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) \right) } \\ & { \quad + \frac { \sqrt { 2 } } { 2 } \left( \frac { \sin ( 2 \theta ) } { 2 } \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) \right) } \\ & { \quad + \frac { \sqrt { 2 } } { 2 } \left( \frac { \sin ( 2 \theta ) } { 2 } \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) \right) } \\ & { \quad \cos ( 2 \theta ) } \\ & { \quad \cos ( 2 \theta ) + \sin ( 2 \theta ) } \\ & { \quad + \frac { \sqrt { 2 } } { 2 } \cos ( 2 \theta ) \cos ( 2 \theta ) - \cos ( 2 \theta ) \cos ( 2 \theta ) } \\ & { \quad \cos ( 2 \theta ) + \sin ( 2 \theta ) } \\ & { \quad \cos ( 2 \theta ) + \sin ( 2 \theta ) } \\ & { \quad - \sqrt { 2 } \cos ( 2 \theta ) + \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) } \\ & { \quad - \sqrt { 2 } \cos ( 2 \theta ) } \\ & { \quad - \sqrt { 2 } \cos ( 2 \theta ) + \sin ( 2 \theta ) } \\ & { \quad + \sqrt { 2 } \cos ( 2 \theta ) + \sin ( 2 \theta ) + \sin ( 2 \theta ) \cos ( 2 \theta ) } \\ & { \quad + \sqrt { 2 } \cos ( 2 \theta ) } \\ & { \quad + \sqrt { 2 } \cos ( 2 \theta ) + \sin ( 2 \theta ) } \\ \end{array}
$$

By combining the optical pumping and QND measurement contribution to Eqs. (A3-A6),one can find a set of stochastic equations of a closed set of variables of

$$
\{  \hat { \sigma } _ { b a }  ,  \Delta \sigma _ { b a } \Delta \sigma _ { d c }  _ { s } | a , b , c , d \in \{ \uparrow , \downarrow , T \} \}
$$

in the symmetric qutrit subspace. The matrix of equations is sparse and close to diagonal which indicates only nearest neighboring coupling is possible in the $\left\{ \left. \hat { \sigma } _ { b a } \right. , \left. \Delta \sigma _ { b a } \Delta \sigma _ { d c } \right. _ { s } \right\}$ basis. In the symmetric qutrit subspace，we have 45 two-body moment variables and corresponding sparse second-order equations,which we solve numerically.