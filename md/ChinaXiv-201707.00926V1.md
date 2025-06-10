# {ultidimensionally-constrained relativistic mean field models and potential energy surfaces of actinide nuclei

Bing-Nan Lu,1 Jie Zhao,1 En-Guang Zhao, $^ { 1 , 2 }$ and Shan-Gui Zhou1,2, $^ *$ （20 （204号 $^ { 1 }$ State Key Laboratory of Theoretical Physics, Institute of Theoretical Physics, Chinese Academy of Sciences，Beijing 100190，China $^ 2$ Center of Theoretical Nuclear Physics，National Laboratoryof Heavy Ion Acelerator，Lanzhou 730oo0,China (Dated: July 30,2017)

Background:Many diferent shape degrees of freedom play crucial roles in determining the nuclear ground state and saddle point properties and the fission path.For the study of nuclear potential energy surfaces,it is desirable to have microscopic and self-consistent models in which allknown important shape degrees offreedom are included.

Purpose:By breaking both the axial and the spatial reflection symmetries simultaneously，we develop multidimensionally-constrained relativistic mean field (MDC-RMF） models.

Methods:The nuclear shape is assumed to be invariant under the reversion of $x$ and $y$ axes,i.e.,the intrinsic symmetry group is $V _ { 4 }$ and all shape degrees of freedom $\beta _ { \lambda \mu }$ with even $\mu$ ， such as $\beta _ { 2 0 }$ ， $\beta _ { 2 2 }$ ， $\beta _ { 3 0 }$ ， $\beta _ { 3 2 }$ ， $\beta _ { 4 0 }$ ，： are included self-consistently.The single-particle wave functionsare expanded inanaxially deformed harmonic oscillator (ADHO)basis.The RMF functional can be one of the following four forms: the meson exchange or point-coupling nucleon interactions combined with the nonlinear or density-dependent couplings.The pairing effects are taken into account with the BCS approach.

Results: The one-, two,and three-dimensional potential energy surfaces of $^ { 2 4 0 }$ Pu are illustrated for numerical checks andforthe studyof theefectofthe triaxialityon the fission barriers.Potential energy curves of even-even actinide nuclei around the first and second fssion barrers are studied systematically.Besides the frst ones,the second fsion barriers in these nuclei are also lowered considerably by the triaxial deformation.This lowering efect is independentof the effctive interactions used intheRMF functionals.Furtherdiscussions are made about different predictions on the efect of the triaxiality between the macroscopic-microscopic and MDC-RMF models, posible discontinuities on PES's from self-consistent approaches,and the restoration of broken symmetries.

Conclusions:MDC-RMF models give a reasonably good description of fission barriers of even-even actinide nuclei.Itis important to includeboth the nonaxial and the reflection asymmetric shapes simultaneously for the study of potential energy surfaces and fision barriers of actinide nuclei and of those in unknown mass regions such as, e.g., superheavy nuclei.

PACS numbers: 21.60.Jz,24.75.+i,25.85.-w, 27.90.+b

# I. INTRODUCTION

The occurrence of spontaneous symmetry breaking leads to nuclear shapes with a variety of symmetries [1, 2]. A lot of nuclear phenomena are connected with the nuclear deformation,including small and large amplitude collective motions,e.g.，the rotation and the fission [3,4]. The shape of a nucleus can be described by the parametrization of the nuclear surface or the nucleon density distribution.The multipole expansion of the nuclear surface is usually used in mean field calculations,

$$
R ( \theta , \varphi ) = R _ { 0 } \left[ 1 + \beta _ { 0 0 } + \sum _ { \lambda = 2 } ^ { \infty } \sum _ { \mu = - \lambda } ^ { \lambda } \beta _ { \lambda \mu } ^ { \ast } Y _ { \lambda \mu } ( \theta , \varphi ) \right] ,
$$

where $\beta _ { \lambda \mu }$ 's are deformation parameters.

The majority of observed nuclear shapes is of the spheroidal form which can be described by the axialquadrupole deformation parameter $\beta _ { 2 0 }$ though in early years theNilsson perturbed-spheroid parameter €2 was usually adopted for numerical convenience [5]. The nonaxial-quadrupole (triaxial) deformation $\beta _ { 2 2 }$ (or, equivalently, $\gamma$ ）manifests itself by the wobbling motion and chiral doublet bands [6-9],and it may also play important roles in superheavy nuclei (SHN) [10].

The octupole shapes with $\lambda = 3$ are predicted to exist in nuclei in several mass regions [11]. The low-lying negative parity bands observed in actinides and some rare-earth nuclei are related to the reflection asymmetric (RA）shapes [12-17]. In addition,reflection asymmetric shell model calculations revealed that the observed low-energy $2 ^ { - }$ bands in $N = 1 5 0$ nuclei [18] are caused by the $\beta _ { 3 2 }$ deformation [19].Indeed,strong $Y _ { 3 2 }$ correlations were found in some $N ~ = ~ 1 5 0$ isotones from multidimensionally-constrained covariant density functional theories (MDC-CDFT） [20].

Deformations of higher-order multipole with $\lambda > 3$ are important to different extents.The hexadecapole deformation, $\beta _ { 4 0 }$ or $\epsilon _ { \mathrm { 4 } }$ ,has been included in deformed mean field potentials since 196Os,see,e.g., Ref.[5]. The important effects of the higher-order deformation $\beta _ { 6 0 }$ or $\epsilon _ { 6 }$ on the angular momentum alignments and dynamic moments of inertia in superheavy nuclei were also re

vealed [21, 22].

The shape degrees of freedom are important not only for the ground states or small amplitude collective motions,but also for large amplitude collective motions such as fission. Since the discovery of the nuclear fission, the description of the fission process has been a difficult and challenging task. The fission dynamics are mostly governed by the barriers which prohibit the dissolving of the nucleus.In order to study the fission problem,one should have very accurate information about the fission barrier,i.e.,the height and width,or,more precisely, the shape of the fission barrier [23,24]. Particularly, to explore the island of stability of SHN,it is more and more desirable to have accurate predictions of fission barriers of SHN. To now,many popular nuclear structure models have been employed to study nuclear fission barriers,in cluding the macroscopic-microscopic (MM） models [25- 29],the extended Thomas-Fermi plus Strutinsky integral (ETFSI) method [30],the Hartree-Fock or Hartree-FockBogoliubov methods with the Skyrme force [31-38] and the Gogny force [39],and the CDFTs [31, 40-51].

Besides $\beta _ { 2 0 }$ which describes the elongation of a fissile nucleus and $\beta _ { 4 0 }$ which is relevant to the size of a neck,many other shape degrees of freedom are also crucial for determining the shape of fission barriers and the fission path. Let us take actinides as examples. Due to shell effects,actinide nuclei are characterized by a two-humped fission barrier [52].It has long been known from the MM model calculations that the inner fission barrier is lowered by the nonaxial-quadrupole deformation [53-55] and the outer one by the reflection asymmetric shape [56].Later,the important roles played by the nonaxial-quadrupole deformation and the octupole deformation were confirmed in the nonrelativistic [57] and relativistic [58] density functional calculations,respectively. Therefore what is usually done is to consider the triaxial but reflection symmetric (RS) shapes for the inner barrier and axially symmetric (AS)but RA shapes for the outer one [39,59,60] though in several publications,both the nonaxial and the octupole deformations are included [61].

In recent years, the nuclear CDFT has been very successful in the description of both ground states and excited states of the nuclei ranging from light to superheavy regions. The CDFTs have also been used to study the PES's and the fission barriers of heavy and superheavy nuclei [31, 40-51]. We have developed MDC-CDFTs by breaking both the axial and reflection symmetries simultaneously [46-48]. In these MDC-CDFTs,all shape degrees of freedom $\beta _ { \lambda \mu }$ with even $\mu$ ，e.g., $\beta _ { 2 0 }$ ， $\beta _ { 2 2 }$ ， $\beta _ { 3 0 }$ ， $\beta _ { 3 2 }$ $\beta _ { 4 0 }$ ， ，are included self-consistently. The covariant density functional can be one of the following four forms: the meson exchange or point-coupling nucleon interactions combined with the nonlinear or density-dependent couplings. For the particle-particle channel,either the BCS approach or the Bogoliubov transformation has been implemented. For convenience,we name the MDCCDFT with the BCS approach for the pairing as the

MDC-RMF models and those with the Bogoliubov transformation as the MDC-RHB models. Due to the heavy computational burden,MDC-RHB models have not been used to do multidimensionally constrained calculations yet (here “multi”means three or more).The MDC-RMF models have been used to study the PES's of actinide nuclei in the ( $\beta _ { 2 0 }$ ， $\beta _ { 2 2 }$ ， $\beta _ { 3 0 }$ ） deformation space and it was found that the triaxiality also plays an important role upon the second fission barriers [46].In this paper，we will present the detailed formulae for MDC-RMF models and some results of actinide nuclei.

The paper is organized as follows. The formalism of MDC-RMF models will be given in Sec.II. In Sec. III we present the numerical details and results on the PES's of the actinide nuclei. A summary is given in Sec.IV.

# II. FORMALISMOFMDC-RMFMODELS

In the RMF model,a nucleus is treated as a composite of nucleons interacting through exchanges of mesons and photons [42, 62-68]. The effects of mesons are described either by mean fields or by point-like interactions between the nucleons [69,7O].Meanwhile,the nonlinear coupling terms [71-73] or the density dependence of the coupling constants [74, 75] are introduced to give correct saturation properties of nuclear matter.Accordingly, the form of the covariant density functional can be one of the following four: the meson exchange or point-coupling nucleon interactions combined with the nonlinear or density dependent couplings.Most of the computational efforts are devoted to solving the Dirac equation and the calculation of various densities;this is common for all these RMF models. In this section,we mainly present the formalism of the RMF model with the nonlinear pointcouplings (NL-PC).

The starting point of the RMF model with the NL-PC is the following Lagrangian,

$$
{ \mathcal { L } } = { \bar { \psi } } ( i \gamma _ { \mu } \partial ^ { \mu } - M ) \psi - { \mathcal { L } } _ { \mathrm { l i n } } - { \mathcal { L } } _ { \mathrm { n l } } - { \mathcal { L } } _ { \mathrm { d e r } } - { \mathcal { L } } _ { \mathrm { C o u } } ,
$$

where

$$
\begin{array} { l } { { \mathcal { L } _ { \mathrm { l i n } } = \displaystyle \frac { 1 } { 2 } \alpha _ { S } \rho _ { S } ^ { 2 } + \frac { 1 } { 2 } \alpha _ { V } \rho _ { V } ^ { 2 } + \frac { 1 } { 2 } \alpha _ { T S } \bar { \rho } _ { T S } ^ { 2 } + \frac { 1 } { 2 } \alpha _ { T V } \bar { \rho } _ { T V } ^ { 2 } , } } \\ { { \mathcal { L } _ { \mathrm { n l } } = \displaystyle \frac { 1 } { 3 } \beta _ { S } \rho _ { S } ^ { 3 } + \frac { 1 } { 4 } \gamma _ { S } \rho _ { S } ^ { 4 } + \frac { 1 } { 4 } \gamma _ { V } [ \rho _ { V } ^ { 2 } ] ^ { 2 } , } } \\ { { \mathcal { L } _ { \mathrm { d e r } } = \displaystyle \frac { 1 } { 2 } \delta _ { S } [ \partial _ { \nu } \rho _ { S } ] ^ { 2 } + \frac { 1 } { 2 } \delta _ { V } [ \partial _ { \nu } \rho _ { V } ] ^ { 2 } + \frac { 1 } { 2 } \delta _ { T S } [ \partial _ { \nu } \bar { \rho } _ { T S } ] ^ { 2 } } } \\ { { + \left. \frac { 1 } { 2 } \delta _ { T V } [ \partial _ { \nu } \bar { \rho } _ { T V } ] ^ { 2 } , \right. } } \\ { { \mathcal { L } _ { \mathrm { C o u } } = \displaystyle \frac { 1 } { 4 } F ^ { \mu \nu } F _ { \mu \nu } + e ^ { \frac { 1 - \tau _ { 3 } } { 2 } } A _ { 0 } \rho _ { V } , } } \end{array}
$$

are the linear coupling，nonlinear coupling，derivative coupling,and the Coulomb part,respectively. $M$ is the nucleon mass, $\alpha _ { S }$ ， $\alpha _ { V }$ ， $\alpha _ { T S }$ ， $\alpha _ { T V }$ ， $\beta _ { S }$ ， $\gamma _ { S }$ ， $\gamma _ { V }$ ， $\delta _ { S }$ ， $\delta _ { V }$ ， $\delta _ { T S }$ ，and $\delta _ { T V }$ are coupling constants for different channels,and $e$ is the electric charge. $\rho _ { S }$ ， $\vec { \rho } _ { T S }$ ， $\rho _ { V }$ ，and $\vec { \rho } _ { T V }$ are the isoscalar density, isovector density, time-like components of isoscalar current，and time-like components of isovector current,respectively. The densities and currents are defined as

$$
\begin{array} { r l } { \rho _ { S } = \bar { \psi } \psi , } & { { } \quad \vec { \rho } _ { T S } = \bar { \psi } \vec { \tau } \psi , } \\ { \rho _ { V } = \bar { \psi } \gamma ^ { 0 } \psi , } & { { } \quad \vec { \rho } _ { T V } = \bar { \psi } \vec { \tau } \gamma ^ { 0 } \psi . } \end{array}
$$

Starting from the Lagrangian,using the Slater determinants as trial wave functions,and neglecting the Fock term as well as the contribution to the densities and currents from the Dirac sea (the no sea approximation),we can derive the RMF equation with the variational principle,

$$
\hat { h } \psi _ { k } ( \pmb { r } ) = \epsilon _ { k } \psi _ { k } ( \pmb { r } ) ,
$$

where

$$
\hat { h } = \pmb { \alpha } \cdot \pmb { p } + \beta \left[ M + S ( \pmb { r } ) \right] + V ( \pmb { r } ) ,
$$

is the single-particle Hamiltonian and

$$
\begin{array} { r l } & { S = \alpha _ { S } \rho _ { S } + \alpha _ { T S } \vec { \rho } _ { T S } \cdot \vec { \tau } + \beta _ { S } \rho _ { S } ^ { 2 } + \gamma _ { S } \rho _ { S } ^ { 3 } } \\ & { \quad \quad + \delta _ { S } \triangle \rho _ { S } + \delta _ { T S } \triangle \vec { \rho } _ { T S } \cdot \vec { \tau } , } \\ & { V = \alpha _ { V } \rho _ { V } + \alpha _ { T V } \vec { \rho } _ { T V } \cdot \vec { \tau } + \gamma _ { V } \rho _ { V } ^ { 2 } \rho _ { V } } \\ & { \quad \quad + \delta _ { V } \triangle \rho _ { V } + \delta _ { T V } \triangle \vec { \rho } _ { T V } \cdot \vec { \tau } , } \end{array}
$$

are the scalar and vector potentials,respectively. In the present work we suppose that the nuclei in question are invariant under the time-reversion,which means that all the time-odd or vector components of the currents and the potentials vanish. In this case the single-particle Hamiltonian has the time-reversal symmetry which simplifies the calculation.

It is customary to solve the deformed RMF equations by expanding the auxiliary single-particle wave functions in a complete basis,e.g.,the harmonic oscillator (HO) basis [76, 77] or the Woods-Saxon (WS) basis [78, 79]. By using a basis in a two-centre harmonic oscillator potential,a reflection asymmetric relativistic mean field (RAS-RMF) approach has been developed [80] and used to study PES's of even-even $^ { 1 4 6 - 1 5 6 }$ Sm in which the important role of the octupole deformation on shape phase transitions was found [81]. However, in our MDCCDFTs, the single-particle wave functions and various densities are expanded in an axially deformed harmonic oscillator（ADHO） basis. The ADHO basis consists of the eigenstates of the Schrodinger equation [76,77, 82],

$$
\left[ - \frac { \hbar ^ { 2 } } { 2 M } \nabla ^ { 2 } + V _ { B } ( z , \rho ) \right] \Phi _ { \alpha } ( \boldsymbol { r } \sigma ) = E _ { \alpha } \Phi _ { \alpha } ( \boldsymbol { r } \sigma ) ,
$$

where $\boldsymbol { r } = \left( z , \rho \right)$ with $\rho = { \sqrt { x ^ { 2 } + y ^ { 2 } } }$ and

$$
V _ { B } ( z , \rho ) = \frac { 1 } { 2 } M ( \omega _ { \rho } ^ { 2 } \rho ^ { 2 } + \omega _ { z } ^ { 2 } z ^ { 2 } ) ,
$$

is the ADHO potential and $\omega _ { z }$ and $\omega _ { \rho }$ are the oscillator frequencies along and perpendicular to the symmetry $z$ axis,respectively. The solution of Eq. (9） reads

$$
\Phi _ { \alpha } ( { \pmb r } \sigma ) = C _ { \alpha } \phi _ { n _ { z } } ( z ) R _ { n _ { \rho } } ^ { m _ { l } } ( \rho ) \frac { 1 } { \sqrt { 2 \pi } } e ^ { i m _ { l } \varphi } \chi _ { s _ { z } } ( \sigma ) ,
$$

where $\phi _ { n _ { z } } ( z )$ and $R _ { n _ { \rho } } ^ { m _ { l } } ( \rho )$ are the harmonic oscillator wave functions,

$$
\begin{array} { r l } & { \phi _ { n _ { z } } ( z ) = \frac { 1 } { \sqrt { b _ { z } } } \frac { 1 } { \pi ^ { 1 / 4 } \sqrt { 2 ^ { n _ { z } } n _ { z } ! } } H _ { n _ { z } } \left( \frac { z } { b _ { z } } \right) e ^ { - \frac { z ^ { 2 } } { 2 b _ { z } } } , \qquad ( 1 2 ) } \\ & { R _ { n _ { \rho } } ^ { m _ { l } } ( \rho ) = \frac { 1 } { b _ { \rho } } \sqrt { \frac { 2 n _ { \rho } ! } { ( n _ { \rho } + | m _ { l } | ) ! } } \left( \frac { \rho } { b _ { \rho } } \right) ^ { | m _ { l } | } L _ { n _ { \rho } } ^ { | m _ { l } | } \left( \frac { \rho ^ { 2 } } { b _ { \rho } ^ { 2 } } \right) e ^ { - \frac { \rho ^ { 2 } } { \hat { \ell } ^ { 1 2 } \beta _ { \mathrm { 3 } } } } , } \end{array}
$$

$\chi _ { s _ { z } }$ is a two-component spinor and $C _ { \alpha }$ is a complex number introduced for convenience.Harmonic oscillator lengths $b _ { z }$ and $b _ { \rho }$ are related to the frequencies by $b _ { z } = 1 / \sqrt { M \omega _ { z } }$ and $b _ { \rho } = 1 / \sqrt { M \omega _ { \rho } }$ .The corresponding eigenenergy $E _ { \alpha } = \omega _ { \rho } ( 2 n _ { \rho } + | m _ { l } | + 1 ) + \omega _ { z } ( n _ { z } + 1 / 2 )$ and the major quantum number $N _ { \alpha } = 2 n _ { \rho } + | m _ { l } | + n _ { z }$ ：

These basis states are also eigenstates of the $z$ component of the angular momentum $\hat { j } _ { z }$ with eigenvalues $K _ { \alpha } ~ = ~ m _ { l } + m _ { s }$ .For any state $\Phi _ { \alpha } ( { \pmb r } \sigma )$ ，the timereversal state is defined as $\Phi _ { \bar { \alpha } } ( \pmb { r } \sigma ) = \mathscr { T } \Phi _ { \alpha } ( \pmb { r } \sigma )$ ，where ${ \mathcal T } = i \sigma _ { y } \hat { K }$ is the time-reversal operator and $\hat { K }$ is the complex conjugation operator.Apparently，we have $K _ { \bar { \alpha } } ~ = ~ - K _ { \alpha }$ and $\pi _ { \bar { \alpha } } = \pi _ { \alpha }$ ，where $\pi _ { \alpha } ~ = ~ \pm 1$ is the parity. The deformation of the basis $\beta _ { \mathrm { b a s i s } }$ is defined through the relations $\omega _ { z } = \omega _ { 0 } \exp \left( - \sqrt { 5 / 4 \pi } \beta _ { \mathrm { b a s i s } } \right)$ and $\omega _ { \rho } = \omega _ { 0 } \exp \left( \sqrt { 5 / 1 6 \pi } \beta _ { \mathrm { b a s i s } } \right)$ ，where $\omega _ { 0 } = ( \omega _ { z } \omega _ { \rho } ^ { 2 } ) ^ { 1 / 3 }$ is the frequency of the corresponding spherical oscillator.

These basis states form a complete set for expanding any two-component spinors.For a Dirac spinor with four components,

$$
\psi _ { i } ( \pmb { r \sigma } ) = \left( \sum _ { \alpha } f _ { i } ^ { \alpha } \Phi _ { \alpha } ( \pmb { r \sigma } ) \right) ,
$$

where the sum runs over all the possible combination of the quantum numbers $\alpha = \left\{ n _ { z } , n _ { \rho } , m _ { l } , m _ { s } \right\}$ and $f _ { i } ^ { \alpha }$ and $g _ { i } ^ { \alpha }$ are the expansion coefficients.In practical calculations the summations in Eq. (14) have to be truncated. Following Ref.[83]， for the large component of the Dirac wave function, the states satisfying $[ n _ { z } / Q _ { z } +$ $( 2 n _ { \rho } + | m _ { l } | ) / Q _ { \rho } ] \ \leq \ N _ { f }$ are included in the expansion where $Q _ { z } = \operatorname* { m a x } ( 1 , b _ { z } / b _ { 0 } )$ and $Q _ { \rho } = \operatorname* { m a x } ( 1 , { b _ { \rho } } / { b _ { 0 } } )$ are constants related to the oscillator lengths $b _ { 0 } \equiv 1 / \sqrt { M \omega _ { 0 } }$ ， $b _ { z }$ ，and $b _ { \rho }$ ．For the expansion of the small component, the truncation is made up to $N _ { g } = N _ { f } + 1$ major shells in order to avoid the spurious states [76].

Ifa nucleus is invariant under the rotation around the symmetry $z$ axis and the spatial reflection,the angular momentum projection on the $z$ -axisand the parity are conserved and the RMF equation(5) can be decomposed into blocks characterized by the quantum numbers $K _ { \alpha }$ and $\pi _ { \alpha }$ .Usually only half of the space with $K _ { \alpha } > 0$ is considered due to the time-reversal symmetry.

Now let us turn to the general case that the axial symmetry as well as the spatial reflection symmetry are broken. Since we still expand the spinors in the ADHO basis,components with different $K$ and $\pi$ are mixed together; thus,we must diagonalize a larger single-particle

Hamiltonian matrix with non-zero matrix elements between two basis states with different $K$ and $\pi$ .Nevertheless,even in this case,we still have one symmetry operator that makes the Hamiltonian matrix block-diagonal. Due to the axial symmetry of the basis,it is convenient to introduce the simplex operator $\hat { S } = i e ^ { - i \pi \hat { j } _ { z } }$ .Note that for a fermionic system with a half-integer spin, $\hat { S }$ is a Hermitian operator and $\hat { S } ^ { 2 } = 1$ . This operator corresponds to the rotation by $\pi$ around the $z$ axis,thus leaving the nuclear mean field invariant.The eigenvalue of $\hat { S }$ ， $S$ , is also a good quantum number for the basis, $S \Phi _ { \alpha } = S \Phi _ { \alpha } = ( - 1 ) ^ { K _ { \alpha } - 1 / 2 } \Phi _ { \alpha }$ , which means that the basis $\Phi _ { \alpha }$ with $K _ { \alpha } = + 1 / 2$ ， $- 3 / 2$ ， $+ 5 / 2$ ， $- 7 / 2$ ，... span the subspace with $S = 1$ ,while their time-reversal states span the one with $S = - 1$ . Note that now the blocks with $K = + 1 / 2$ ， $- 3 / 2$ ， $+ 5 / 2$ ， $- 7 / 2$ ,...are mixed. Remember that for a nucleus with the time-reversal symmetry, only the basis with $S = 1$ are used in the expansions; for such a basis state,we set $C _ { \alpha } = 1$ [cf.Eq.(11)]when expanding the large component and $C _ { \alpha } = i$ for the small one. The basis states with $S _ { \alpha } ~ = ~ - 1$ are obtained by simply applying $\tau$ on those with $S _ { \alpha } = 1$ .Furthermore, for systems with the time-reversal symmetry,it is only necessary to diagonalize the matrix with $S = 1$ and the other half is obtained by a time-reversal operation on the obtained single-particle wave functions.

For deformed nuclei with the $V _ { 4 }$ symmetry,we expand the potentials $V ( r )$ ， $S ( \pmb { r } )$ ,and the densities in Eq. (4) in terms of the Fourier series,

$$
f ( \rho , \varphi , z ) = \sum _ { \mu = - \infty } ^ { \infty } f _ { \mu } ( \rho , z ) \frac { 1 } { \sqrt { 2 \pi } } \exp ( i \mu \varphi ) .
$$

Applying the symmetry conditions,it is easy to see that $f _ { \mu } = f _ { \mu } ^ { \ast } = f _ { \bar { \mu } }$ and $f _ { n } = 0$ for odd $n$ . Thus the expansion (15) can be simplified as

$$
f ( \rho , \varphi , z ) = f _ { 0 } ( \rho , z ) \frac { 1 } { \sqrt { 2 \pi } } + \sum _ { n = 1 } ^ { \infty } f _ { n } ( \rho , z ) \frac { 1 } { \sqrt { \pi } } \cos ( 2 n \varphi ) ,
$$

where

$$
\begin{array} { l } { { f _ { 0 } ( \rho , z ) = { \displaystyle \frac { 1 } { \sqrt { 2 \pi } } } \int _ { 0 } ^ { 2 \pi } d \varphi f ( \rho , \varphi , z ) , } } \\ { { f _ { n } ( \rho , z ) = { \displaystyle \frac { 1 } { \sqrt { \pi } } } \int _ { 0 } ^ { 2 \pi } d \varphi f ( \rho , \varphi , z ) \cos ( 2 n \varphi ) , } } \end{array}
$$

are real functions of p and $z$ .The details for calculating the matrix elements of the Dirac Hamiltonian and various densities and their derivatives are given in the Appendixes.

For open shell nuclei the pairing interaction becomes crucial and must be included.It has been shown that fission barriers depend very much on the form and strength of the effective pairing interactions [84]. Several methods have been developed to treat the pairing effects,e.g., the BCS approach,the Bogoliubov transformation,and the particle number conserving method [85-89];all of them have been used in the study of PES's and fission barriers. Since we use the BCS approach in our MDC-RMF calculations,we only show the formulas for the BCS approximation. In the particle-particle channel, the gap equation reads [2],

$$
\Delta _ { k } = \sum _ { k ^ { \prime } > 0 } \frac { 1 } { 2 } V _ { k \bar { k } k ^ { \prime } \bar { k ^ { \prime } } } ^ { \mathrm { p p } } \frac { \Delta _ { k ^ { \prime } } } { \sqrt { \tilde { \epsilon } _ { k ^ { \prime } } ^ { 2 } + \Delta _ { k ^ { \prime } } ^ { 2 } } } ,
$$

where $\tilde { \epsilon } _ { k } = \epsilon _ { k } - \lambda$ and $\lambda$ is the Fermi energy. The total pairing energy is

$$
{ \cal E } _ { \mathrm { p a i r } } = { \frac { 1 } { 4 } } V _ { 0 } \int d ^ { 3 } { \boldsymbol { r } } \kappa ^ { * } ( { \boldsymbol { r } } ) \kappa ( { \boldsymbol { r } } ) .
$$

In our models,either the $\delta$ -force or the finite-range separable force [90] is implemented.

To obtain a PES one can perform a constraint calculation which is equivalent to adding an external potential during the iteration [2]. The quadratic constraint method is usually used,

$$
E ^ { \prime } = E _ { \mathrm { R M F } } + \sum _ { \lambda \mu } \frac { 1 } { 2 } C _ { \lambda \mu } \left( Q _ { \lambda \mu } - m _ { \lambda \mu } \right) ^ { 2 } ,
$$

where $C _ { \lambda \mu }$ is the spring constant and $m _ { \lambda \mu }$ 's are desired moments.With this method the calculation always converges to a deformation point on the PES other than the desired one. To overcome this shortcoming and to get a PES with equally distributed points,we use a modified linear constraint method.The Routhian reads,

$$
E ^ { \prime } = E _ { \mathrm { R M F } } + \sum _ { \lambda \mu } \frac { 1 } { 2 } C _ { \lambda \mu } Q _ { \lambda \mu } ,
$$

where the variables $C _ { \lambda \mu }$ 's change their values during the iteration through the following relation,

$$
C _ { \lambda \mu } ^ { ( n + 1 ) } = C _ { \lambda \mu } ^ { ( n ) } + k _ { \lambda \mu } \left( \beta _ { \lambda \mu } ^ { ( n ) } - \beta _ { \lambda \mu } \right) ,
$$

where $\beta _ { \lambda \mu }$ is the desired deformation, $k _ { \lambda \mu }$ is a constant, and $C _ { \lambda \mu } ^ { ( n ) }$ is the value at the $n$ th step. This constraint method works well in our multidimensionally-constrained calculations.

The total energy of the nucleus reads

$$
\begin{array} { r l } & { E _ { \mathrm { t o t a l } } = \displaystyle \int d ^ { 8 } r \left\{ \sum _ { k } v _ { k } ^ { 2 } \hat { v } _ { k } ^ { \dagger } \right\} ( \alpha \cdot p + \beta M ) \hat { v } _ { k } } \\ & { \qquad + \displaystyle \frac { 1 } { 2 } \alpha s \rho _ { s } ^ { 2 } + \frac { 1 } { 2 } \alpha v \rho _ { V } ^ { 2 } + \frac { 1 } { 2 } \alpha _ { T S } \rho _ { T S } ^ { 2 } + \frac { 1 } { 2 } \alpha _ { T V } \rho _ { T V } ^ { 2 } } \\ & { \qquad + \displaystyle \frac { 1 } { 3 } \beta s \rho _ { s } ^ { 3 } + \frac { 1 } { 4 } \gamma s \rho _ { s } ^ { 4 } + \frac { 1 } { 4 } \gamma v \rho _ { V } ^ { 4 } } \\ & { \qquad + \displaystyle \frac { 1 } { 2 } \delta _ { s } \rho _ { s } \Delta \rho _ { s } + \frac { 1 } { 2 } \delta _ { \gamma } \rho _ { V } \Delta \rho _ { V } } \\ & { \qquad + \displaystyle \frac { 1 } { 2 } \delta _ { T S } \rho _ { T S } \Delta \rho _ { T S } + \frac { 1 } { 2 } \delta _ { T V } \rho _ { T V } \Delta \rho _ { T V } + \frac { 1 } { 2 } \epsilon \rho _ { C A } \Big \} } \\ & { \qquad + E _ { \mathrm { p a r i } } + E _ { \mathrm { c . m . } } , } \end{array}
$$

where $E _ { \mathrm { c . m } }$ . is the center of mass correction. Depending on the effective interactions used in the RMF functional, $E _ { \mathrm { c . m } }$ . can be calculated either in the oscillator approximation,

$$
E _ { \mathrm { c . m . } } = - { \frac { 3 } { 4 } } \times 4 1 A ^ { 1 / 3 } \ \mathrm { M e V } ,
$$

or from the quasi-particle vacuum,

$$
E _ { \mathrm { c . m . } } = - \frac { \langle \hat { P } ^ { 2 } \rangle } { 2 M A } ,
$$

where $\hat { P }$ is the total linear momentum and $A$ is the nuclear mass number.

The intrinsic multipole moments are calculated from the density by

$$
Q _ { \lambda \mu } = \int d ^ { 3 } { \pmb r } \rho _ { V } ( { \pmb r } ) r ^ { \lambda } Y _ { \lambda \mu } ( { \Omega } ) ,
$$

where $Y _ { \lambda \mu } ( \Omega )$ is the spherical harmonics.The deformation parameter $\beta _ { \lambda \mu }$ is obtained from the corresponding multipole moment by

$$
\beta _ { \lambda \mu } = \frac { 4 \pi } { 3 N R ^ { \lambda } } Q _ { \lambda \mu } ,
$$

where $R = 1 . 2 \times A ^ { 1 / 3 }$ fm is the nuclear radius and $N$ is the number of protons,neutrons,or nucleons.

# III. RESULTS AND DISCUSSIONS

# A.Numerical details

In this section we present the numerical details and some illustrative calculations ofMDC-RMF models.The potentials and densities are calculated in a spatial lattice [cf.Eqs. (15),(17),and (18) and Appendix B] in which mesh points in the $\rho$ and $z$ directions are designed in a way that the Gaussian quadrature can be made and those for the azimuthal angle $\phi$ are equally distributed. Since we keep the mirror reflection symmetry with respect to the $x = 0$ or $y = 0$ planes,only mesh points with positive $x$ and $y$ are considered.For the azimuthal angle $\phi$ ，more than 1O mesh points for light nuclei and about 2O mesh points for heavy nuclei are used,which are enough for most of practical applications.In two special cases the number of mesh points can be further reduced:(1） for axially symmetric nuclei the azimuthal degree of freedom vanishes and(2) for reflection symmetric nuclei the mesh points with $z ~ < ~ 0$ can be omitted.With these choices the values of the localized fields and potentials in the full lattice space can be simply obtained by symmetry transformations such as rotations or the spatial reflection. The Coulomb field must be treated carefully due to its long-range nature. In the pairing channel,we use a density-independent $\delta$ force with a smooth cutoff.The pairing strength parameters are $V _ { \mathrm { n } } = - 3 4 9 . 5$ MeV fm³ and $V _ { \mathrm { p } } = - 3 3 0 . 0$ MeV fm $^ 3$ which are obtained by fitting the average pairing gaps [91, 92].

![](images/1108045f95a26d94344fe756a5d540f75ec20abf668548241f085e55ebd30195.jpg)  
FIG.1.(Color online） The potential energy curve of $^ { 2 4 0 } \mathrm { { P u } }$ from MDC-RMF calculations with different truncations of the ADHO basis.Both triaxial(TA）and reflection asymmetric (RA)deformations are allowed.The results calculated with $N _ { f } = 1 6$ ,18,and 2O aredepictedby dashed,dotted,and solid curves,respectively. The four sub-figures show the detailed structure of the potential energy curve near the ground state (A),the inner barrier (B),the isomeric state(C)，and the outer barrier (D).The results calculated with $N _ { f } = 2 2$ (dotdashed curves)are also included in the sub-figures.The width ofeach sub-figure is O.1 and the height is1 MeV.

The calculated physical observables should converge as the truncation $N _ { f } \to \infty$ .In Fig.1 we show the potential energy curve of $^ { 2 4 0 }$ Pu calculated with different truncations, $N _ { f } = 1 6$ ，18,and 20.The effective interaction PC-PK1 [92] is used; accordingly, $E _ { \mathrm { c . m } }$ . is calculated with Eq. (26).As is found in most of earlier calculations, the results show a typical two-humped structure.To see more clearly the truncation errors we have amplified the figure near four important points,i.e., the ground state, the top of the inner barrier,the isomeric state,and the top of the outer barrier. In these four sub-figures,the results with $N _ { f } = 2 2$ are also shown and we can investigate in more details the convergence properties of our model. When $N _ { f }$ increases from 16 to 20,the binding energy changes differently for different points in the potential energy curve；the largest changes are near the ground state and about O.3 MeV.Around the ground state and the second minimum, $^ { 2 4 0 }$ Pu is axially deformed; the energy obtained from calculations with $N _ { f } ~ = ~ 2 0$ and 22 are almost the same. This means a good convergence; in the present work,we use $N _ { f } = 2 0$ in axially symmetric calculations.Around the two fission barriers,the triaxial deformation is very important. One finds that for the inner barrier, the results from $N _ { f } = 2 0$ and 22 are also almost identical; for the outer one,the difference between the barrier heights from calculations with $N _ { f } = 2 0$ and 22 is about several tens keV.It is very time consuming to make calculations with both axial and reflection symmetries broken.In our systematic calculations presented in this paper, $N _ { f } = 2 0$ is used around the ground state and the first saddle point, $N _ { f } = 1 6$ is used around the fission isomer and the second saddle point.As a result, the inner barrier height is described with an accuracy of $\sim 0 . 1 5$ MeV and the outer one with an accuracy of $\sim 0 . 4$ MeV. If in future calculations, $N _ { f } = 2 0$ can also be used around the second barrier, the accuracy for its height should be within O.2 MeV.

![](images/574e01668873493e36e8886585abf9b55d6d7b889aa6e21db9050338b0c23bca.jpg)  
FIG.2. (Color online) Mean field energy (i.e., $E _ { \mathrm { c . m } }$ . is not included) of $^ { 2 4 0 }$ Pu calculated by using basis with different basis deformation $\beta _ { \mathrm { b a s i s } }$ and different $N _ { f }$ ．The results calculated with $N _ { f } = 1 6$ ,18,and 2O shells are denoted by red diamonds, green squares,and blue dots,respectively. The deformation is constrained to $\beta _ { 2 0 } = 0 . 3$ ,1.3,and 2.0,respectively.

Next we show how the results depend on the deformation of the ADHO potential which is used to generate the ADHO basis; for brevity,we will call it the basis deformation and label it with $\beta _ { \mathrm { b a s i s } }$ .In Fig. 2 we depict the calculated mean field energy of $^ { 2 4 0 }$ Pu as a function of the basis deformation. Note that $E _ { \mathrm { c . m } }$ . is not included in Fig.2. In principle,if the basis space is complete, the results should not change when the basis deformation changes. Near the ground state, $\beta _ { 2 0 } = 0 . 3$ , the calculated energies are rather stable against the basis deformation.

![](images/3c9f7fe0d5f957c6953c83ba925de3744d89d3a5cb5248825d25122585880316.jpg)  
FIG.3.(Color online） Mean field energy (i.e., $E _ { \mathrm { c . m } }$ .is not included） of $\mathrm { ^ { 2 4 0 } P u }$ calculated with different truncations on large (upper panel) and small component (lower panel).In the calculations for the upper panel, $N _ { g }$ are fixed to 23,while the calculations for the lower panel are preformed with $N _ { f } = 1 0$ The deformation is constrained to $\beta _ { 2 0 } = 0 . 3$ ：

Furthermore,the results with $N _ { f } = 1 6$ ,18,and 20 almost coincide with each other.This conclusion holds also for the second barrier, $\beta _ { 2 0 } = 1 . 3$ ,except that two points with small basis deformations and $N _ { f } = 1 6$ are very high. For even larger deformations, $\beta _ { 2 0 } = 2 . 0$ , the results with $N _ { f } = 1 6$ deviate a bit from those with $N _ { f } = 1 8$ and 20; the differences between the results with $N _ { f } = 1 8$ and 20 are still very small. In the present work, the basis deformation is chosen in the following way: $\beta _ { \mathrm { b a s i s } } = \beta _ { 2 0 }$ for $\beta _ { 2 0 } < 0 . 3$ and $\beta _ { \mathrm { b a s i s } } = \beta _ { 2 0 } / 2$ for $0 . 3 < \beta _ { 2 0 } < 2 . 0$ ：

When the basis is not complete, the calculated single particle energies contain the contributions from the other levels in both the Fermi sea and the Dirac sea. This causes the “variational collapse” problem [93,94]. As shown in Fig.3,if we fix the truncation for the small component $N _ { g }$ and increase $N _ { f }$ alone,the nucleus becomes more and more bound. Note that we have to set $N _ { f } < N _ { g }$ to prohibit the occurrence of the spurious states,as we mentioned earlier.However,if we fix the truncation for the large component $N _ { f }$ and increase $N _ { g }$ alone,the nucleus becomes less and less bound.Thus,as more basis states are included in the expansion, the binding energy maynot change monotonically;this is different from the nonrelativistic calculations.

In the calculations,the oscillator length or,equivalently, the frequency of the oscillator potential $\hbar \omega _ { 0 }$ for the ADHO basis should also be chosen carefully. The dependence of the binding energy of $ { { } ^ { 2 4 0 } }  { \mathrm { P u } }$ on $\hbar \omega _ { 0 }$ has been investigated in detail. As shown in Fig. 4,when $R \equiv \hbar \omega _ { 0 } / ( 4 1 A ^ { - 1 / 3 } \mathrm { ~ M e V } )$ increases from 0.8 to 1.2, the binding energy of $^ { 2 4 0 }$ Pu in the whole potential energy curve varies by less than 1 MeV (O.05% of the absolute value).Moreover，when $\hbar \omega _ { 0 }$ is around $4 1 A ^ { - 1 / 3 }$ MeV, the binding_energy changes very slightly.So,we set $\hbar \omega _ { 0 } = 4 1 A ^ { - 1 / 3 }$ MeV in all calculations.

![](images/35b8b6826491224a29d7645c9bada025ee189dba96a9ec560a80f6efb4bac382.jpg)  
FIG.4.(Color online） The potential energy curve of $^ { 2 4 0 } \mathrm { { P u } }$ calculated by using basis with different oscillator frequency $\hbar \omega _ { 0 }$ ．The axial symmetry is imposed and $N _ { f } = 2 0$ is used. The results calculated with $R \equiv \hbar \omega _ { 0 } / ( 4 1 A ^ { - 1 / 3 } \mathrm { ~ M e V } ) = 0 . 8$ ， 0.9,1.0,1.1,and 1.2 are depicted by dotted,dashed,solid, dot-dashed，and dash-dot-dotted curves,respectively. The four sub-figures show the detailed structure of the potential energy curve near the ground state (A),the inner barrier (B), the isomeric state (C),and the outer barrier (D).The width of each sub-figure is O.1 and the height is 2 MeV.

# B. Three-dimensional PES of $\mathbf { \Delta ^ { 2 4 0 } P u }$

The double-humped fission barriers of actinide nuclei are usually used as a benchmark for theoretical models, see,e.g., Refs.[35,40, 43, 44, 57, 58,88, 95-101]. As a nucleus evolves from the ground state to the fission configurations,many shape degrees of freedom play important and different roles in determining the heights of the inner and outer barriers.It has long been known that the inner barrier islowered when the triaxial deformation is allowed [53-55],while for the outer barrier, the reflection asymmetric shape is favored [56].We have shown that the reflection asymmetric outer barrier may be further lowered by including the nonaxial shape degrees of freedom [46].In this section we show some results of multidimensional PES's for actinides. We will first present detailed results about the three-dimensional PES of $^ { 2 4 0 }$ Pu, then display systematic results of the actinide nuclei. In these calculations, the effective interaction PC-PK1 [92 is used.

In Figs.5 and 6 is shown the calculated threedimensional PES of $\mathrm { ^ { 2 4 0 } P u }$ .In these calculations,both non-axial and reflection asymmetric shapes are allowed and $N _ { f } = 1 6$ is used.In each sub-figure we fix the value of $\beta _ { 2 0 }$ and display the energy as a function of $\beta _ { 2 2 }$ and $\beta _ { 3 0 }$ In other words,we have made three-dimensional constraints on the corresponding multipole moments.Note that other shape degrees of freedom $\beta _ { \lambda \mu }$ with even $\mu$ ， e.g., $\beta _ { 3 2 }$ ， $\beta _ { 4 0 }$ ， $\beta _ { 4 2 }$ ， $\beta _ { 4 4 }$ ， $\beta _ { 5 0 }$ ， $\mathbf { \nabla } \cdot \cdot \mathbf { \nabla } \cdot \mathbf { \mu }$ ，are also included in the calculations self-consistently. The MDC-RMF equations are solved for each point on the deformation lattice $( \beta _ { 2 0 } , \beta _ { 2 2 } , \beta _ { 3 0 } )$ in which $\beta _ { 2 0 }$ runs from 0.25 to 1.70 with a step size of 0.05, $\beta _ { 2 2 }$ from $0$ to 0.25 with a step size of 0.01,and $\beta _ { 3 0 }$ from $0$ to 0.50 with a step size of O.05. The points with $\beta _ { 2 2 } ( \beta _ { 3 0 } ) < 0$ are obtained through the relation $E ( \beta _ { 2 0 } , \beta _ { 2 2 } , \beta _ { 3 0 } ) = E ( \beta _ { 2 0 } , | \beta _ { 2 2 } | , | \beta _ { 3 0 } | )$ ．That is, for each sub-figure,26 (for $\beta _ { 2 2 } ) \times 1 1$ (for $\beta _ { 3 0 } ) = 2 8 6$ points are calculated,and there are totally $2 8 6 ~ \times ~ 3 0 ~$ (for $\beta _ { 2 0 }$ ） $= 8 5 8 0$ points in Figs.5 and 6.This deformation lattice covers the shape space of the most interest for $^ { 2 4 0 }$ Pu, from the ground state to the isomeric state and fission configurations.

Now we examine the first three sub-figures with $\beta _ { 2 0 } =$ 0.25, O.30,and O.35.It is clear that the ground state with $\beta _ { 2 0 } \sim 0 . 3$ is both axially symmetric and reflection symmetric,though it is a little soft against the octupole distortion.When the nucleus is stretched by the quadrupole constraining potential, it becomes softer against the triaxial as well as the octupole distortions.From the subfigures with $\beta _ { 2 0 } = 0 . 4 0 \sim 0 . 6 5$ one finds that two symmetric minima with non-zero triaxial deformation $\beta _ { 2 2 }$ appear and the corresponding fission paths are much more favored than the axially symmetric one,which is consistent with earlier calculations [45]. Although $\beta _ { 3 0 } = 0$ for all minima in these sub-figures,the softness against the octupole distortion changes as the nucleus is elongated.The inner fission barrier locates near the deformation $\beta _ { 2 0 } \sim 0 . 6 0$ . For the last six sub-figures in Fig. 5 with $\beta _ { 2 0 } = 0 . 7 0 \sim 0 . 9 5$ ,the situation becomes much simpler,where the nucleus becomes axially symmetric and reflection symmetric again. Nevertheless,the trend to become softer against the octupole distortion can be seen from these sub-figures,which indicates that the reflection asymmetric shape becomes more relevant.

As the deformation $\beta _ { 2 0 }$ becomes larger,the second minimum and the second saddle point of the PES appear.From the last three sub-figures of Fig.5 and the first three sub-figures of Fig.6 we see that,the nucleus keeps reflection symmetric near the fission isomeric state with $\beta _ { 2 0 } \sim 0 . 9 5$ ，but it becomes softer against the $\beta _ { 3 0 }$ distortion. Note that the scales of the $\beta _ { 3 0 }$ axes are different in Figs.5 and 6.At $\beta _ { 2 0 } = 1 . 1 5$ ,two minima corresponding to reflection asymmetric shapes appear. Here the effect of the nonaxial deformation is not apparent, but along the $\beta _ { 2 2 }$ direction the PES becomes softer.At $\beta _ { 2 0 } = 1 . 2$ the energy of the reflection asymmetric shape is lower by about 1 MeV than that of the reflection symmetric one.Interestingly,when $\beta _ { 2 0 }$ increases further,around the top of the second barrier,each reflection asymmetric minimum splits into two minima with non-zero $\beta _ { 2 2 }$ This is the lowering effects of triaxiality on the outer barrier found in Ref.[46]. Around the second barrier,the largest energy gain due to the triaxial distortion is about 1 MeV. The nucleus becomes axially symmetric again when $\beta _ { 2 0 } > 1 . 6$ ：

![](images/e1e4571890f4ccb5b64de01e19db2d824421dfaf88ab0e328ff107010b3ba21f.jpg)  
FIG. 5.(Color online） Sections of the three-dimensional potential energy surface, $E = E ( \beta _ { 2 0 } , \beta _ { 2 2 } , \beta _ { 3 0 } )$ of $^ { 2 4 0 } \mathrm { { P u } }$ around the groundstate,theinnerbarrier,andthefisionisomerfrom MDC-RMFcalculations.Ineachsub-fgure theenergyisshownas a function of the deformation parameters $\beta _ { 2 2 }$ and $\beta _ { 3 0 }$ when $\beta _ { 2 0 }$ is fixed at a certain value.The energies are normalized with respect to the binding energy of the ground state. The contour interval is 1 MeV.

From the above discussions, we can draw the following conclusions for $^ { 2 4 0 }$ Pu: (1) Both the ground state and the fission isomeric state are axial and reflection symmetric; (2)Around the first fission barrier it assumes triaxial and reflection symmetric shapes;(3) Around the second fission barrier both triaxial and octupole deformations are important.

# C. PES's of even-even actinide nuclei around two fission barriers

Theself-consistent three-dimensionally-constrained calculations are very time-consuming,we have only performed such calculations for $^ { 2 4 0 }$ Pu. From this benchmark study we learned many experiences about the important rolesplayed by various shape degrees of freedom in different regions of the deformation space,including the conclusions listed in the end of Sec. IIIB. These experiences areused in a systematic study of even-even actinide nuclei.

Since around the inner barrier an actinide nucleus assumes triaxial but reflection symmetric shapes,we can make a one-dimensional constraint calculation with the triaxial deformation allowed and the reflection symmetry imposed. In Fig.7 we present potential energy curves of even-even actinide nuclei around the ground state and the first fission barrier from MDC-RMF calculations. The axially symmetric results are displayed by dotted curves and those from triaxial calculations are shown by solid curves.The empirical values of fission barrier heights are taken from Ref.[102l and shown with red dots.We also list in Table I the heights of the first and second fission barriers of actinide nuclei from MDC-RMF calculations compared with the empirical values.It is clearly seen that the triaxial deformation lowers the inner barrier of these actinide nuclei by about $1 \sim 4$ MeV and this is consistent with Ref.[45]. The agreement of our calculation results with the empirical ones is good for most of the nuclei studied here with exceptions in the two thorium isotopes and $^ { 2 3 8 , 2 4 0 }$ U. We have discussed possible reasons for these discrepancies in Ref. [46].

![](images/db9c7a4d59464ee8419b88b6ce09704a6f15157dcce5a5f34672ec5fb996e7f2.jpg)  
FIG. 6.(Color online) Sections of the three-dimensional potential energy surface, $E = E ( \beta _ { 2 0 } , \beta _ { 2 2 } , \beta _ { 3 0 } )$ ，of $^ { 2 4 0 }$ Pu around the fisionisomerandtheouterbarrerfrom MDC-RMFcalculations.Ineach sub-fgure theenergyisshownasafunctionof the deformation parameters $\beta _ { 2 2 }$ and $\beta _ { 3 0 }$ when $\beta _ { 2 0 }$ is fixed at a certain value.The energies are normalized with respect to the binding energy of the ground state. The contour interval is 1 MeV.

It is more complicated to determine the second fission barrier height because more shape degrees of freedom become important and there are often two or more fission paths.What we have done is the following [46]: (1) The axial symmetry is assumed and a two-dimensional constraint calculation in the $( \beta _ { 2 0 } , \beta _ { 3 0 } )$ plane is made; (2) From the two-dimensional calculation the lowest fission path $\beta _ { 3 0 } ^ { \mathrm { l o w e s t } } ( \beta _ { 2 0 } )$ is approximatelyidentifed; (3)Along this fission path,a one-dimensional $\beta _ { 2 0 }$ -constrained calculation is performed with the triaxial and octupole deformations allowed and at each point with $\beta _ { 2 0 }$ fixed, theinitialdeformationsaretakenas $\beta _ { 2 2 } ^ { \mathrm { i n i . } } \ = \ 0$ and $\beta _ { 3 0 } ^ { \mathrm { 1 n 1 . } } = \beta _ { 3 0 } ^ { \mathrm { l o w e s t } } ( \beta _ { 2 0 } )$ ; (4)Itsoate tial energy curve,the second saddle point is located and the second barrier height is extracted.

Potential energy curves of even-even actinide nuclei around the fission isomer and the second fission barrier from MDC-RMF calculations are shown in Fig.8. In addition, the experimental values of the energies for fission isomers [103] are also shown by short horizontal lines.For $^ { 2 4 4 }$ Pu, a suggested isomeric energy range (1.6 MeV to 2.6 MeV） from systematics was shown. From Fig.8 and Table I one finds that for most of the nuclei investigated here,the triaxialitylowers the second barrier by about $0 . 5 \sim 1$ MeV (about $1 0 \sim 2 0 \%$ of the barrier height) [46]. The calculation results with the triaxiality included agrees well with the empirical values for all actinide nuclei shown in Fig.8. In Ref.[46],we have found that for $^ { 2 4 8 }$ Cm,the height of the second barrier without the triaxial deformation included is already smaller than the empirical value.From Table Iit is seen that this is also the case for $2 5 0$ Cm and $^ { 2 5 0 , 2 5 2 }$ Cf. For these four nuclei, it is difficult to find the second saddle point when the triaxial deformation is included.Therefore the heights of the second barriers with the triaxial deformation included are not listed for them. The reason for these discrepancies may be related to a strong competition between the two or among more fission paths and the assumption on the barrier width made when the empirical value of the barrier height is evaluated,as discussed in Ref. [46].

![](images/866809cf4628fc5671428cf8a4185bc82324b45fccbe5cb5c2a75c5c56e5f356.jpg)  
FIG.7.(Color online)Potential energycurves of even-even actinide nuclei around the ground states and the first fision barriers from MDC-RMFcalculations.The axially symmetric resultsare displayed by doted curves,，while those from the triaxial calculationsareshown bysolidcurves.Thebinding energyisnormalizedwithrespecttothatofthegroundstateof each nucleus.The empirical values of fission barriers are taken from Ref.[102] and shown by red dots.

actions is about O.5 MeV to O.9 MeV which are clearly larger than the possible errors from the basis truncations discussed in Sec. IIIA.

# E.Further discussions

# D.Parameter dependence of the effect of triaxialityaround the second barrier

From the above detailed studies of PES's of actinide nuclei in the ( $\beta _ { 2 0 }$ ， $\beta _ { 2 2 }$ ， $\beta _ { 3 0 }$ ） space,it is clear that the triaxiality plays an important role upon the second fission barriers of actinide nuclei.We have studied the parameter dependence of the effect of triaxiality on the second barrier height and some results can be found in Refs.[46-48].In Table II are listed the second barrier heights of $^ { 2 3 4 }$ U calculated with different parameter sets, including meson-exchange ones NL3 $^ *$ [104],NL-Z2[105], DD-ME2 [106], and point-coupling ones PC-PK1 [92] and DD-PC1 [1O7]. One finds that the second barrier height may differ by a few MeV with different effective interactions,but in all cases the barriers are lowered considerably by the nonaxial deformations. For this specific nucleus,the lowering effect with different effective inter

A systematic study of fission barriers has been performed for even-even superheavy nuclei with $Z = 1 1 2 \sim$ 120 by using CDFTs and the outer fission barriers are found to be considerably affected by the triaxiality [49]. However,in a recent work within the MM model,it was found that the influence of the triaxiality on the second fission barriers is negligible [1O8]. This raises an open problem: What are the main reasons for the different effects of the triaxiality on the second fission barriers predicted by the MM model and CDFTs?It would be interesting to make more investigations with different models, especially,with the nonrelativistic DFTs.

One of the problems concerning the PES calculated from self-consistent approaches is that there may exist unexpected discontinuities on PES's [6O].This is mainly due to the complexity of multi-dimensional PES's. When a high-dimensional PES is projected onto a lowdimensional one, the minimizing procedure incorporated implicitly in the self-consistent approaches may cause a sudden change in the total energy at some points in the low-dimensional deformation space. This may result in spurious saddle points. In our MDC-RMF calculations，we have tried some ways to avoid discontinuities on the PES's and to exclude spurious saddle points [46]. To be completely free of discontinuities or spurious saddle points,one certainly should carry out multidimensionally-constrained calculations with higherorder multipole deformations included.In Ref.[109] the authors analyzed the origin of the discontinuities and proposed a numerical method to identify them.It will be useful to implement this method in the present MDCRMF calculations； this will be one of our topics in the future.

![](images/b7f4bf0f34e3d50d8588a84102c9e5c678e7530223671ed46e5fd80d46605732.jpg)  
FIG.8.(Color online)Potential energycurves of even-even actinide nuclei aroundthefision isomers andthe secondfision barriers from MDC-RMFcalculations.Thereflectionasymmetricshapesareallowedinthecalculations.Theaxiallysymmetric results are displayed bydottedcurves,whilethosefromthetriaxialcalculations areshown bysolidcurves.Thebinding energy is normalized withrespectto thatoftheground stateofeach nucleus.Theempiricalvaluesoffision bariers aretaken from Ref.[102]and shownbyreddots.Experimental valuesof energiesoffisionisomersare taken fromRef.[103]and show by green horizontal lines. For $^ { 2 4 4 }$ Pu,only an energy range was given for the isomer.

Since many symmetries are broken in mean field calculations,quantum numbers related to these symmetries are no longer conserved [2]. For example,the total angular momentum or nuclear spin $J$ is not a good quantum number when $\beta _ { 2 0 }$ is not zero；similarly,the projection of the total angular momentum on the symmetry axis $K$ is also not conserved if a nucleus is triaxially deformed [110]. When the reflection symmetry is broken,the parity is not a good quantum number.In our three-dimensional constraint calculations，all these quantum numbers are not good ones. One may intro duce techniques of projection to restore the broken symmetries [2].In recent years,the importance of various projections on the PES's and fission barriers have been investigated [39, 88,111, 112].

# IV. SUMMARY

We developed multidimensionally-constrained relativistic mean field(MDC-RMF) models.In these models,the nuclear shape is assumed to be invariant under the reversion of $x$ and $y$ axes，i.e.,the intrinsic symmetry group is $V _ { 4 }$ and all shape degrees of freedom $\beta _ { \lambda \mu }$ with even $\mu$ （ $\beta _ { 2 0 }$ ， $\beta _ { 2 2 }$ ${ \mathrm { ? 2 } } , \beta _ { 3 0 } , \beta _ { 3 2 } , \beta _ { 4 0 } , { \mathrm { ~ . ~ . ~ } }$ .）are included self-consistently. The RMF functional can be one of the following four forms: the meson exchange or point-coupling nucleon interactions combined with the nonlinear or density-dependent couplings. We solve the Dirac equation in an axially deformed harmonic oscillator（ADHO）basis.The convergence of the calculated results against the basis truncation,the oscillator length, and the basis deformation is studied and it is shown that reasonablylarge ADHO basis is able to provide a desired accuracy.

TABLE I.Heights of the first and second fission barriers of some even-even actinide nuclei from MDC-RMF calculations compared with the empirical values（“Emp"）which are taken from Ref.[1O2].The calculation results with and without the axial symmetry imposed are denoted by “AS” (axially symmetric) and “TA”(triaxial),respectively. Note that around the first barrier,the reflection symmetry is assumed and for the second barrier,the octupole deformation is included.The height is in MeV.   

<html><body><table><tr><td>Nucleus</td><td>Z</td><td>N</td><td>A</td><td colspan="2">First barrier</td><td colspan="2">Second barrier</td></tr><tr><td>230Th</td><td>90</td><td>140</td><td>230</td><td>AS 5.03</td><td>TA Emp 3.96</td><td>AS 6.80</td><td>TA Emp 6.37</td></tr><tr><td>232Th</td><td>90</td><td></td><td>232</td><td>4.94</td><td>6.10</td><td></td><td>6.50 6.18</td></tr><tr><td>232U</td><td>92</td><td>142 140</td><td>232</td><td>5.71</td><td>4.12 5.80 4.90</td><td>6.70</td><td>6.70 5.40</td></tr><tr><td>234U</td><td>92</td><td></td><td>234</td><td></td><td>4.81</td><td>6.20</td><td>5.64 5.55</td></tr><tr><td>236U</td><td>92</td><td>142 144</td><td>236</td><td>6.15 6.40</td><td>5.09 4.80</td><td>6.20</td><td>5.50</td></tr><tr><td>238U</td><td>92</td><td></td><td>238</td><td>6.54</td><td>5.11 5.00</td><td>6.15</td><td>5.31 5.70</td></tr><tr><td>240U</td><td>92</td><td>146</td><td>240</td><td>6.58</td><td>5.03 6.30</td><td>6.20</td><td>5.42 5.50</td></tr><tr><td>238Pu</td><td>94</td><td>148 144</td><td>238</td><td>7.72</td><td>4.96 6.10</td><td>6.38</td><td>5.43 5.80</td></tr><tr><td>240Pu</td><td>94</td><td>146</td><td>240</td><td>7.98</td><td>5.96 5.60</td><td>6.05 5.56</td><td>5.10</td></tr><tr><td>242Pu</td><td>94</td><td>148</td><td>242</td><td>8.05</td><td>5.92 6.05 5.77 5.85</td><td>6.24 5.60 6.43 5.74</td><td>5.20 5.10</td></tr><tr><td>244Pu</td><td>94</td><td>150</td><td>244</td><td>7.85</td><td>5.40 5.70</td><td>6.26 5.49</td><td>4.90</td></tr><tr><td>246Pu</td><td>94</td><td>152</td><td>246</td><td>7.37</td><td>4.76 5.40</td><td>5.84</td><td>4.96 5.30</td></tr><tr><td>242Cm</td><td>96</td><td>146</td><td>242</td><td>8.80</td><td>6.49 6.65</td><td>5.72</td><td>4.85 5.00</td></tr><tr><td>244Cm</td><td>96</td><td>148</td><td>244</td><td>9.04</td><td>6.34 6.18</td><td>5.90</td><td>4.88 5.10</td></tr><tr><td>246Cm</td><td>96</td><td>150</td><td>246</td><td>8.89</td><td>5.84 6.00</td><td>5.40 4.62</td><td>4.80</td></tr><tr><td>248Cm</td><td>96</td><td>152</td><td>248</td><td>8.43</td><td>5.35 5.80</td><td>4.10</td><td>4.80</td></tr><tr><td>250Cm</td><td>96</td><td>154</td><td>250</td><td>7.77</td><td>4.79 5.40</td><td>2.60</td><td>4.40</td></tr><tr><td>250Cf</td><td>98</td><td>152</td><td>250</td><td>8.87</td><td>5.70 5.60</td><td>2.40</td><td>3.80</td></tr><tr><td>252Cf</td><td>98</td><td>154</td><td>252</td><td>8.41</td><td>5.26 5.30</td><td>1.20</td><td>3.50</td></tr></table></body></html>

TABLE II.Height of the second barrier of $^ { 2 3 4 }$ U calculated from MDC-RMF models with different parameter sets.The results with and without nonaxial deformations included and their difference are denoted by $B _ { \mathrm { A S } }$ ， $B _ { \mathrm { T A } }$ ，and $\Delta B$ ，respectively.   

<html><body><table><tr><td>Parameter set</td><td>BAs (MeV)</td><td>BTA (MeV)</td><td>△B (MeV)</td></tr><tr><td>NL3*</td><td>7.54</td><td>6.85</td><td>0.69</td></tr><tr><td>NL-Z2</td><td>4.83</td><td>3.91</td><td>0.92</td></tr><tr><td>PC-PK1</td><td>6.20</td><td>5.55</td><td>0.65</td></tr><tr><td>DD-ME2</td><td>8.19</td><td>7.51</td><td>0.68</td></tr><tr><td>DD-PC1</td><td>6.13</td><td>5.64</td><td>0.49</td></tr></table></body></html>

Three-dimensional potential energy surface in the ( $\beta _ { 2 0 }$ $\beta _ { 2 2 }$ ， $\beta _ { 3 0 }$ ) plane is obtained for $^ { 2 4 0 }$ Pu and potential energy curves of actinide nuclei around the first and second fission barriers are studied systematically.It is found that the triaxiality is crucial in determining the height of both the first and the second fission barriers. Taking $^ { 2 3 4 }$ Uas an example,we have studied the parameter dependence of the effects of triaxiality on the second barrier height and found that the height of the second barrier may differbya few MeVwith different effective interactions,but in all cases the barriers are lowered considerably by the nonaxial deformations.

We conclude that it is important to include both the nonaxial and the spatial reflection asymmetric shapes simultaneously for the study of potential energy surfaces and fission barriers of actinide nuclei and of those in unknown mass regions such as, e.g., superheavy nuclei.

# ACKNOWLEDGMENTS

Helpful discussions with Haozhao Liang，Jie Meng, P.Ring，N. Schunck，D.Vretenar，Xi-Zhen Wu，and Zhen-Hua Zhang are acknowledged.This work has been supported by Major State Basic Research Development Program of China (Grant No． 2013CB834400), National Natural Science Foundation of China (Grants No.11121403，No.11175252，No．11120101005，No. 11211120152，and No. 11275248)，Knowledge Innovation Project of Chinese Academy of Sciences (Grant No. KJCX2-EW-N01). The results described in this paper are obtained on the High-performance Computing Clusters of ITP/CAS and the ScGrid of the Supercomputing Center,ComputerNetworkInformation Center of the Chinese Academy of Sciences.

# Appendix A:Matrix elements of the Dirac Hamiltonian

In the ADHO basis, the Dirac equation (5） is transformed into a matrix eigenvalue problem,

$$
\begin{array} { l } { { \displaystyle \sum _ { \alpha ^ { \prime } } \langle \alpha | M _ { + } ( { \pmb r } ) | \alpha ^ { \prime } \rangle f _ { i } ^ { \alpha ^ { \prime } } + \sum _ { \alpha ^ { \prime } } \langle \alpha | { \pmb \sigma } \cdot { \pmb p } | \alpha ^ { \prime } \rangle g _ { i } ^ { \alpha ^ { \prime } } = \epsilon _ { i } f _ { i } ^ { \alpha } , } } \\ { { \displaystyle \sum _ { \alpha ^ { \prime } } \langle \alpha | { \pmb \sigma } \cdot { \pmb p } | \alpha ^ { \prime } \rangle f _ { i } ^ { \alpha ^ { \prime } } + \sum _ { \alpha ^ { \prime } } \langle \alpha | M _ { - } ( { \pmb r } ) | \alpha ^ { \prime } \rangle g _ { i } ^ { \alpha ^ { \prime } } = \epsilon _ { i } g _ { i } ^ { \alpha } . } } \end{array}
$$

with $M _ { \pm } = \pm M + V \pm S$

In the cylindrical coordinate system the kinetic energy operator $\sigma \cdot p$ reads,

$$
\begin{array} { r } { \pmb { \sigma } \cdot \pmb { p } = - i \left( \begin{array} { c c } { \partial _ { z } } & { e ^ { - i \varphi } ( \partial _ { \rho } - i \rho ^ { - 1 } \partial _ { \varphi } ) } \\ { e ^ { i \varphi } ( \partial _ { \rho } + i \rho ^ { - 1 } \partial _ { \varphi } ) } & { - \partial _ { z } } \end{array} \right) . } \end{array}
$$

The matrix elements of the kinetic energy operator $\sigma \cdot p$ can be calculated as

$$
\begin{array} { r l } & { \langle \alpha | \pmb { \sigma } \cdot \pmb { p } | \alpha ^ { \prime } \rangle = \langle n _ { z } , n _ { \rho } , m _ { l } , m _ { s } | \pmb { \sigma } \cdot \pmb { p } | n _ { z } ^ { \prime } , n _ { \rho } ^ { \prime } , m _ { l } ^ { \prime } , m _ { s } ^ { \prime } \rangle } \\ & { \qquad = - i C _ { \alpha } ^ { * } C _ { \alpha ^ { \prime } } \delta _ { K , K ^ { \prime } } \left[ \delta _ { m _ { l } , m _ { l } ^ { \prime } } \delta _ { n _ { \rho } , n _ { \rho } ^ { \prime } } \delta _ { m _ { s } , m _ { s } ^ { \prime } } A _ { \alpha \alpha ^ { \prime } } \right. } \\ & { \qquad + \left. \delta _ { m _ { s } , - \frac { 1 } { 2 } } \delta _ { m _ { s } ^ { \prime } , \frac { 1 } { 2 } } \delta _ { n _ { z } , n _ { z } ^ { \prime } } \left( B _ { \alpha \alpha ^ { \prime } } - m _ { l } ^ { \prime } C _ { \alpha \alpha ^ { \prime } } \right) \right. } \\ & { \qquad \quad \left. + \delta _ { m _ { s } , \frac { 1 } { 2 } } \delta _ { m _ { s } ^ { \prime } , - \frac { 1 } { 2 } } \delta _ { n _ { z } , n _ { z } ^ { \prime } } \left( B _ { \alpha \alpha ^ { \prime } } + m _ { l } ^ { \prime } C _ { \alpha \alpha ^ { \prime } } \right) \right] , } \end{array}
$$

where the integrals read,

$$
\begin{array} { l } { { \displaystyle { \cal A } _ { \alpha \alpha ^ { \prime } } = \int d z \phi _ { n _ { z } } \partial _ { z } \phi _ { n _ { z } ^ { \prime } } , } } \\ { { \displaystyle { \cal B } _ { \alpha \alpha ^ { \prime } } = \int d \rho R _ { n _ { \rho } } ^ { m _ { l } } \rho \partial _ { \rho } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } , } } \\ { { \displaystyle { \cal C } _ { \alpha \alpha ^ { \prime } } = \int d \rho R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } . } } \end{array}
$$

The matrix elements of the potentials $U ( \pmb { r } ) \equiv M _ { \pm } ( \pmb { r } )$ are calculated by expanding $U ( r )$ into a Fourier series,

$$
U ( \pmb { r } ) = U ( z , \rho , \varphi ) = \frac { 1 } { 2 \pi } \sum _ { \mu = - \infty } ^ { \infty } U ^ { ( \mu ) } ( z , \rho ) e ^ { i \mu \varphi } ,
$$

where the components $U ^ { ( \mu ) } ( z , \rho )$ are calculated by the inverse Fourier transformation,

$$
U ^ { ( \mu ) } ( z , \rho ) = \int _ { 0 } ^ { 2 \pi } d \varphi U ( z , \rho , \varphi ) e ^ { - i \mu \varphi } ,
$$

where the integral over $\varphi$ is performed on a uniformly distributed mesh points.From the symmetry conditions one finds,

$$
U ^ { ( \mu ) } = U ^ { ( - \mu ) } = ( - 1 ) ^ { \mu } U ^ { ( - \mu ) } .
$$

Thus the Fourier series is abbreviated as

$$
U ( \pmb { r } ) = \frac { 1 } { 2 \pi } \left( U ^ { ( 0 ) } ( z , \rho ) + 2 \sum _ { n = 1 } ^ { \infty } U ^ { ( 2 n ) } ( z , \rho ) \cos ( 2 n \varphi ) \right) .
$$

Finally the matrix element of $U ( r )$ reads,

$$
\begin{array} { l } { { \displaystyle \langle \alpha | U | \alpha ^ { \prime } \rangle = \langle n _ { z } , n _ { r } , m _ { l } , m _ { s } | U | n _ { z } ^ { \prime } , n _ { r } ^ { \prime } , m _ { l } ^ { \prime } , m _ { s } ^ { \prime } \rangle } } \\ { { \displaystyle = \delta _ { m _ { s } , m _ { s } ^ { \prime } } C _ { \alpha } ^ { * } C _ { \alpha ^ { \prime } } \frac { 1 } { 2 \pi } \Big [ \delta _ { K , K ^ { \prime } } D _ { \alpha \alpha ^ { \prime } } ^ { ( 0 ) } } } \\ { { \displaystyle ~ + \sum _ { n = 1 } ^ { \infty } \left( \delta _ { K ^ { \prime } - K , 2 n } + \delta _ { K - K ^ { \prime } , 2 n } \right) D _ { \alpha \alpha ^ { \prime } } ^ { ( 2 n ) } \Bigg ] ( \} } } \end{array}
$$

where we have performed the integrals over $\varphi$ and

$$
D _ { \alpha \alpha ^ { \prime } } ^ { ( \mu ) } = \int _ { - \infty } ^ { \infty } d z \int _ { 0 } ^ { \infty } \rho d \rho U ^ { ( \mu ) } ( z , \rho ) \phi _ { n _ { z } } \phi _ { n _ { z } ^ { \prime } } R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } ,
$$

are performed numerically by using the Gaussian quadra ture.For axially symmetric potentials only the first term survives,while for triaxially deformed nucleus we must calculate additional terms with $n \neq 0$

# Appendix B:Densities and their derivatives

After solving the Dirac equation,we can calculate the densities from the wave functions.All the densities are linear combinations of the quantities $\rho _ { f } ( \pmb { r } , \tau )$ and $\rho _ { g } ( \pmb { r } , \tau )$ which are the contributions to the vector density from the large and small components,respectively. $\mathit { \Delta } ^ { \prime }$ represents the isospin. For vector potential we have

$$
\begin{array} { l } { \displaystyle \rho _ { V } ( \boldsymbol { r } ) = \sum _ { i = 1 } ^ { N } v _ { i } ^ { 2 } \sum _ { p = f , g } \psi _ { i } ^ { p \dagger } \psi _ { i } ^ { p } } \\ { = \sum _ { p = f , g } \displaystyle \sum _ { \alpha \alpha ^ { \prime } } \left( \sum _ { i = 1 } ^ { N } v _ { i } ^ { 2 } p _ { i } ^ { \alpha } p _ { i } ^ { \alpha ^ { \prime } } \right) \Phi _ { \alpha } ^ { \dagger } \Phi _ { \alpha ^ { \prime } } . } \end{array}
$$

Note that the factors with $\varphi$ in $\Phi _ { \alpha }$ and $\Phi _ { \alpha ^ { \prime } }$ are in an exponential form,rearranging the terms, $\rho _ { V } ( \pmb { r } )$ can be written as,

$$
\rho _ { V } ( r ) = \frac { 1 } { 2 \pi } \left( \rho _ { V } ^ { ( 0 ) } ( z , \rho ) + 2 \sum _ { n = 1 } ^ { \infty } \rho _ { V } ^ { ( 2 n ) } ( z , \rho ) \cos ( 2 n \varphi ) \right) ,
$$

where the components

$$
\begin{array} { c } { { \rho _ { V } ^ { ( \mu ) } = \displaystyle \sum _ { p = f , g } \sum _ { \alpha \alpha ^ { \prime } } \left[ \left( \sum _ { i = 1 } ^ { N } v _ { i } ^ { 2 } p _ { i } ^ { \alpha } p _ { i } ^ { \alpha ^ { \prime } } \right) \delta _ { K ^ { \prime } - K , \mu } \delta _ { m _ { s } , m _ { s } ^ { \prime } } \right. } } \\ { { \left. \times C _ { \alpha } ^ { * } C _ { \alpha ^ { \prime } } \phi _ { n _ { z } } \phi _ { n _ { z } ^ { \prime } } R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } \right] , } } \end{array}
$$

are calculated with the wave functions $f _ { i } ^ { \alpha }$ and $g _ { i } ^ { \alpha }$

The scalar density $\rho _ { S } ( \pmb { r } )$ can be calculated similarly. The isovector densities are just the linear combinations of the corresponding densities of protons and neutrons.

The derivatives of the vector density reads

$$
\nabla ^ { 2 } \rho _ { V } ( \boldsymbol { r } ) = \sum _ { p = f , g } \sum _ { \alpha \alpha ^ { \prime } } \left( \sum _ { i = 1 } ^ { N } v _ { i } ^ { 2 } p _ { i } ^ { \alpha } p _ { i } ^ { \alpha ^ { \prime } } \right) \nabla ^ { 2 } ( \Phi _ { \alpha } ^ { \dagger } \Phi _ { \alpha ^ { \prime } } ) ,
$$

where the derivatives of the basis can be calculated as,

$$
\nabla ^ { 2 } ( \Phi _ { \alpha } ^ { \dagger } \Phi _ { \alpha ^ { \prime } } ) = I _ { \alpha \alpha ^ { \prime } } + 2 J _ { \alpha \alpha ^ { \prime } } + I _ { \alpha ^ { \prime } \alpha } ^ { * } ,
$$

with ${ \cal I } _ { \alpha \alpha ^ { \prime } }$ and $J _ { \alpha \alpha ^ { \prime } }$ defined later.First,from Eq.(9） weget

$$
\nabla ^ { 2 } \Phi _ { \alpha } = - 2 M \left[ E _ { \alpha } - V _ { B } ( z , \rho ) \right] \Phi _ { \alpha } ,
$$

thus

$$
\begin{array} { l } { { \displaystyle I _ { \alpha \alpha ^ { \prime } } \equiv \Phi _ { \alpha } ^ { \dagger } \nabla ^ { 2 } \Phi _ { \alpha ^ { \prime } } } } \\ { { \displaystyle \quad = - 2 M \left[ E _ { \alpha } - V _ { B } ( z , \rho ) \right] \delta _ { m _ { s } , m _ { s } ^ { \prime } } C _ { \alpha } ^ { * } C _ { \alpha ^ { \prime } } } } \\ { { \displaystyle \quad \quad \times \phi _ { n _ { z } } \phi _ { n _ { z } ^ { \prime } } R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } \times \frac { 1 } { 2 \pi } e ^ { i ( m _ { l } ^ { \prime } - m _ { l } ) \varphi } . } } \end{array}
$$

Second,

$$
\begin{array} { l } { { J _ { \alpha \alpha ^ { \prime } } \equiv \nabla \Phi _ { \alpha } ^ { \dagger } \cdot \nabla \Phi _ { \alpha ^ { \prime } } } } \\ { { \ \quad = \delta _ { m _ { s } , m _ { s } ^ { \prime } } C _ { \alpha } ^ { * } C _ { \alpha ^ { \prime } } } } \\ { { \quad \quad \times \left[ \phi _ { n _ { z } } \phi _ { n _ { z } ^ { \prime } } \left( \partial _ { \rho } R _ { n _ { \rho } } ^ { m _ { l } } \partial _ { \rho } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } + m _ { l } m _ { l } ^ { \prime } \frac { 1 } { \rho ^ { 2 } } R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } \right) \right. } } \\ { { \quad \quad \left. + R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } \partial _ { z } \phi _ { n _ { z } } \partial _ { z } \phi _ { n _ { z } ^ { \prime } } \right] \times \frac { 1 } { 2 \pi } e ^ { i ( m _ { l } ^ { \prime } - m _ { l } ) \varphi } . \quad \mathrm { ( B \Omega \backslash \Omega ) } } } \end{array}
$$

Substituting them into Eq.(B5)and combining the same exponentials of $\varphi$ ，we get

$$
\nabla ^ { 2 } \rho _ { V } ( \boldsymbol { r } ) = \frac { 1 } { 2 \pi } \left( \tilde { \rho } _ { V } ^ { ( 0 ) } ( z , \rho ) + 2 \sum _ { n = 1 } ^ { \infty } \tilde { \rho } _ { V } ^ { ( 2 n ) } ( z , \rho ) \cos { ( 2 n \varphi ) } \right) ,
$$

in which

$$
\begin{array} { r l r } {  { \tilde { \rho } _ { V } ^ { ( \mu ) } = \sum _ { p = f , g } \sum _ { \alpha \alpha ^ { \prime } } ( \sum _ { i = 1 } ^ { N } v _ { i } ^ { 2 } p _ { i } ^ { \alpha } p _ { i } ^ { \alpha ^ { \prime } } ) \delta _ { K ^ { \prime } - K , \mu } \delta _ { m _ { s } , m _ { s } ^ { \prime } } } } \\ & { } & { \times { C } _ { \alpha } ^ { * } { C } _ { \alpha ^ { \prime } } \{ D _ { \alpha \alpha ^ { \prime } } ( z , \rho ) \phi _ { n _ { z } } \phi _ { n _ { z } ^ { \prime } } R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } }  } \\ & { } & {  + 2 \phi _ { n _ { z } } \phi _ { n _ { z } ^ { \prime } } \partial _ { \rho } R _ { n _ { \rho } } ^ { m _ { l } } \partial _ { \rho } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } + 2 R _ { n _ { \rho } } ^ { m _ { l } } R _ { n _ { \rho } ^ { \prime } } ^ { m _ { l } ^ { \prime } } \partial _ { z } \phi _ { n _ { z } } \partial _ { z } \phi _ { n _ { z } ^ { \prime } } \} , } \end{array}
$$

[1] A.Bohr and B.R.Mottelson,Nuclear Structure, Vol.II (World Scientific,1998).   
[2] P.Ring and P. Schuck, The Nuclear Many-Body Problem (Springer-Verlag Berlin,Heidelberg,and New York, 1980).   
[3] S. Frauendorf, Rev. Mod. Phys. 73, 463 (2001).   
[4] W. Nazarewicz, in Lecture Notes in Physics, Vol. 581, edited by J.Arias and M. Lozano (Springer Berlin Heidelberg,2001） pp.102-140.   
[5] S.G. Nilsson,C.F. Tsang,A. Sobiczewski,Z. Szymanski,S.Wycech,C.Gustafson, I.-L.Lamm, P. Moller, and B. Nilsson, Nucl. Phys. A 131,1 (1969).   
[6] S. Frauendorf and J. Meng, Nucl. Phys. A 617, 131 (1997).   
[7] K.Starosta,T.Koike, C.J. Chiara,D.B.Fossan, D.R. LaFosse,A.A.Hecht,C.W.Beausang,M.A.Caprio, J.R.Cooper,R. Krucken,J.R. Novak,N.V. Zamfir, K.E.Zyromski,D.J. Hartley,D.L. Balabanski, J.-y. Zhang,S.Frauendorf, and V.I. Dimitrov,Phys.Rev. Lett. 86, 971 (2001).   
[8] S.W.Odegard，G. B. Hagemann，D. R. Jensen, M.Bergstroem，B.Herskind,G.Sletten，S.Toermaenen,J.N.Wilson,P.O.Tjom,I.Hamamoto,K. Spohr, H.Huebel,A.Goergen，G. Schoenwasser，A.Bracco, S.Leoni,A.Maj,C.M.Petrache,P.Bednarczyk，and D. Curien, Phys.Rev. Lett.86, 5866 (2001).   
[9] J. Meng and S. Q. Zhang, J. Phys. G: Nucl. Phys. 37, 064025 (2010)；J. Meng,J. Peng， S.-Q. Zhang，and P.-W. Zhao, Front. Phys. 8, 55 (2013).   
10] S. Cwiok, P.-H. Heenen， and W. Nazarewicz, Nature 433, 705 (2005).   
11] P. A. Butler and W. Nazarewicz, Rev. Mod. Phys.68, 349 (1996).   
12] T.M.Shneidman,G.G.Adamian,N.V.Antonenko, R.V. Jolos, and W. Scheid,Phys.Rev. C 67, 014313 (2003)；T. M. Shneidman,G.G. Adamian,N.V. Antonenko， and R. V. Jolos, Phys. Rev.C 74，034316 (2006).   
13] S. Wang, H. Hua, J. Meng, Z. H. Li, S.Q. Zhang, F. R. Xu,H.L. Liu, Y. L. Ye, D. X. Jiang, T. Zheng,Q. J. Wang, Z. Q. Chen, C. E. Wu, G. L. Zhang, D. Y. Pang, J.Wang, J. L. Lou,B. Guo, G. Jin, S. G. Zhou, L. H. Zhu,X. G. Wu, G. S. Li, S. X. Wen, C. Y. He, X. Z.

are the Fourier components and

$$
D _ { \alpha \alpha ^ { \prime } } ( z , \rho ) = \frac { 2 m _ { l } m _ { l } ^ { \prime } } { \rho ^ { 2 } } - 2 M \left[ E _ { \alpha ^ { \prime } } + E _ { \alpha } - 2 V _ { B } ( z , \rho ) \right] .
$$

Cui,and Y. Liu, Phys. Rev. C 72, 024317 (2005).   
[14] D. Yang, J.-B.Lu, Y.-Z. Liu, L.-L. Wang, K.-Y.Ma, C.- D. Yang, D.-K.Han,Y.-X. Zhao, Y.-J.Ma,L.-H. Zhu, X.-G. Wu, and G.-S. Li, Chin. Phys. Lett. 26, 082101 (2009).   
[15] L. M. Robledo and G. F. Bertsch,Phys. Rev. C 84, 054302 (2011).   
[16] S.J. Zhu,M. Sakhaee,J.H. Hamilton,A.V.Ramayya, N.T.Brewer,J.K.Hwang,S.H.Liu，E.Y.Yeoh, Z.G.Xiao,Q. Xu, Z. Zhang,Y. X.Luo,J. O. Rasmussen, I. Y.Lee, K. Li, and W.C.Ma, Phys. Rev. C 85,014330 (2012)； S. J. Zhu, J. H. Hamilton,A.V. Ramayya,J.K.Hwang,Y.J.Chen,L.Y.Zhu,H.J.Li, Z. G.Xiao, E. Y. Yeoh, J. G. Wang, Y. X. Luo, S.H. Liu,J.O.Rasmussen，and I.Y.Lee,in Nuclear Structure in China 2012: Proceedings of the 14th National Conference on Nuclear Structure in China (NSC2012), edited by J. Meng, C.-W.Shen, E.-G. Zhao,and S.-G. Zhou(World Scientific,2012） pp.348-356.   
[17] L.P.Gaffney，P.A.Butler，M. Scheck,A.B. Hayes,F.Wenander,M.Albers,B.Bastin,C.Bauer, A.Blazhev, S. Bonig,N. Bree,J. Cederkall, T. Chupp, D.Cline,T.E.Cocolios,T. Davinson,H. De Witte, J.Diriken，T.Grahn，A.Herzan，M.Huyse,D.G. Jenkins,D.T.Joss,N.Kesteloot,J.Konki,MKowalczyk,T. Kroll，E.Kwan，R. Lutter，K.Moschner, P.Napiorkowski, J.Pakarinen,M. Pfeiffer,D.Radeck, P.Reiter，K.Reynders，S.V.Rigby，L.M.Robledo, M.Rudigier,S. Sambi, M. Seidlitz,B. Siebeck,T.Stora, P.Thoele,P.Van Duppen,M.J.Vermeulen,M.von Schmid,D.Voulot,N.Warr,K.Wimmer,K.WrzosekLipska, C. Y. Wu， and M. Zielinska,Nature 497,199 (2013).   
[18] A.P.Robinson,T.L.Khoo,I.Ahmad,S.K. Tandel, F.G.Kondev,T.Nakatsukasa,D.Seweryniak,M.Asai, B.B.Back，M.P.Carpenter，P.Chowdhury，C.N. Davids,S.Eeckhaudt，J.P.Greene,P.T.Greenlees, S.Gros,A.Heinz,R.-D.Herzberg,R.V.F.Janssens, G.D.Jones,T.Lauritsen，C.J.Lister，D.Peterson, J.Qian,U. S.Tandel，X. Wang， and S.Zhu,Phys. Rev. C 78, 034308 (2008).   
[19] Y.-S. Chen, Y. Sun, and Z.-C. Gao, Phys. Rev. C 77, 061305(R) (2008).   
[20] J. Zhao, B.-N.Lu, E.-G. Zhao, and S.-G. Zhou, Phys. Rev. C 86, 057304 (2012).   
[21] H. L. Liu, F. R. Xu, and P. M. Walker, Phys. Rev.C 86,011301(R) (2012).   
[22] Z.-H. Zhang,J. Meng,E.-G.Zhao, and S.-G. Zhou, Phys. Rev. C 87, 054308 (2013).   
[23] A. Zubov, G. Adamian,and N.Antonenko,Phys. Part. Nucl. 40,847 (2009).   
[24] C.-J. Xia, B.-X. Sun, E.-G. Zhao, and S.-G. Zhou, Sci. China-Phys. Mech. Astron. 54 (Suppl. 1),s109 (2011).   
[25] P.Moller,D.G.Madland,A. J. Sierk,and A.Iwamoto, Nature 409, 785 (2001).   
[26] K. Pomorski and J. Dudek, Phys. Rev. C 67, 044316 (2003).   
[27] F. A. Ivanyuk and K. Pomorski, Phys. Rev. C 79, 054327 (2009).   
[28] M. Kowal, P. Jachimowicz， and A. Sobiczewski, Phys. Rev. C 82, 014303 (2010).   
[29] G. Royer, M. Jaffre, and D. Moreau, Phys.Rev.C 86, 044326 (2012).   
[30] A. Mamdouh,J. M. Pearson,M. Rayet， and F. Tondeur,Nucl. Phys. A 644, 389 (1998)； Nucl. Phys. A 679, 337 (2001).   
[31] T.Burvenich,M. Bender，J.A. Maruhn， and P.-G. Reinhard, Phys. Rev. C 69, 014307 (2004).   
[32] M. Samyn, S.Goriely， and J.M.Pearson, Phys. Rev. C 72, 044316 (2005)； S. Goriely, M. Samyn, and J. M. Pearson, Phys. Rev. C 75,064312 (2007).   
[33] F.Minato,S.Chiba， and K.Hagino,Nucl.Phys.A 831,150 (2009).   
[34] J.C. Pei, W. Nazarewicz,J.A. Sheikh， and A. K. Kerman, Phys.Rev.Lett.102，192501 (2009)   
[35] M.Kortelainen，J.McDonnell，W.Nazarewicz,P.-G. Reinhard, J. Sarich, N. Schunck, M. V. Stoitsov， and S. M. Wild, Phys. Rev. C 85, 024304 (2012).   
[36] J. McDonnell, N. Schunck,and W. Nazarewicz, in Fission and Properties of Neutron-Rich Nuclei: Proceedings of the Fifth International Conference on Fission and Properties of Neutron-Rich Nuclei (ICFN5),Nov. 4-10,20i2, Sanibel Island,Florida,USA,Edited by J. H.Hamilton and A.V.Ramayya (World Scientific, Singapore, 2013)， pp. 597-604.   
[37] A. Staszczak,A.Baran, and W.Nazarewicz,Phys.Rev. C 87, 024320 (2013).   
[38] N.Schunck，D.Duke,H.Carr, and A. Knoll, arXiv:1311.2616 [nucl-th]； N. Schunck,D. Duke， and H. Carr,arXiv:1311.2620 [nucl-th].   
[39] J. L. Egido and L. M. Robledo, Phys. Rev. Lett. 85, 1198 (200O)； M. Warda and J. L. Egido, Phys. Rev. C 86, 014322 (2012).   
[40] V. Blum, J. Maruhn, P.-G. Reinhard, and W. Greiner, Phys. Lett. B 323, 262 (1994).   
[41] W. Zhang, S.-S. Zhang, S.-Q. Zhang, and J. Meng, Chin. Phys. Lett. 20,1694 (2003).   
[42] M. Bender, P.-H. Heenen，and P.-G. Reinhard,Rev. Mod. Phys. 75, 121 (2003).   
[43] H.-F. Lü, L.-S. Geng, and J. Meng, Chin. Phys. Lett. 23, 2940 (2006).   
[44] Z.P.Li, T. Niksic, D. Vretenar, P. Ring,and J. Meng, Phys. Rev. C 81, 064321 (2010).   
[45] H. Abusara, A. V. Afanasjev, and P. Ring, Phys. Rev. C 82, 044303 (2010).   
[46] B.-N. Lu, E.-G. Zhao, and S.-G. Zhou, Phys. Rev.C 85,011301(R) (2012).   
[47] B.-N. Lu, Multi-dimensional constrained relativistic mean field theory and the potential energy surfaces and fission barriers of actinide nuclei, Ph.D. thesis,Institute of Theoretical Physics,Chinese Academy of Sciences (2012),in Chinese.   
[48] B.-N.Lu, J. Zhao, E.-G. Zhao, and S.-G. Zhou, EPJ Web Conf. 38, 05003 (2012)； arXiv:1304.6830 [nucl-th].   
[49] H. Abusara, A. V. Afanasjev, and P. Ring, Phys. Rev. C 85, 024314 (2012).   
[50] V. Prassa, T. Niksic, G. A. Lalazissis, and D. Vretenar, Phys. Rev. C 86,024317 (2012)； V. Prassa, T. Niksic, and D. Vretenar, Phys.Rev. C 88, 044324 (2013).   
[51] A. V. Afanasjev, in Fission and Properties of NeutronRich Nuclei:Proceedings of the Fifth International Conference on Fission and Properties of Neutron-Rich Nuclei (ICFN5), Nov. 4-10,2012, Sanibel Island, Florida, USA,Edited by J. H. Hamilton and A. V. Ramayya (World Scientific, Singapore, 2013)， pp. 303-310.   
[52] M.Brack, J.Damgaard,A. S. Jensen,H.C.Pauli, V.M. Strutinsky， and C. Y. Wong, Rev. Mod. Phys. 44,320 (1972).   
[53] V. V. Pashkevich, Nucl. Phys. A 133, 400 (1969).   
[54] P. Moller and S. G. Nilsson, Phys. Lett.B 31， 283 (1970).   
[55] J. Randrup, S. E. Larsson, P. Moller， S. G. Nilsson, K.Pomorski， and A. Sobiczewski,Phys.Rev. C 13, 229 (1976).   
[56] T. Ledergerber and H.-C. Pauli, Nucl. Phys. A 207,1 (1973).   
[57] M. Girod and B. Grammaticos, Phys. Rev. C 27, 2317 (1983).   
[58] K.Rutz，J.A.Maruhn，P.G.Reinhard, and W. Greiner, Nucl. Phys.A 590, 680 (1995).   
[59] L. Bonneau, P. Quentin, and D. Samsoen, Eur.Phys. J. A 21,391 (2004).   
[60] P.Moler，A.J. Sierk，T.Ichikawa，A.Iwamoto, R.Bengtsson, H. Uhrenholt，and S. Aberg, Phys. Rev. C 79,064304 (2009).   
[61] J. Skalski, Phys. Rev. C 76, 044603 (2007)；P. Jachimowicz,M. Kowal, and J. Skalski, Phys. Rev. C 83, 054302 (2011).   
[62] B.D.Serot and J.D.Walecka,Adv.Nucl. Phys.16,1 (1986).   
[63] P. G. Reinhard, Rep. Prog. Phys. 52, 439 (1989).   
[64] P. Ring, Prog. Part. Nucl. Phys. 37, 193 (1996).   
[65] D.Vretenar,A.V.Afanasjev,G.A. Lalazissis， and P. Ring, Phys. Rep. 409,101 (2005).   
[66] J. Meng, H. Toki, S.G. Zhou, S. Q. Zhang, W. H. Long, and L. S. Geng, Prog. Part. Nucl. Phys. 57, 470 (2006).   
[67] N. Paar, D. Vretenar， and G. Colo, Rep. Prog.Phys. 70,691 (2007).   
[68] T. Niksic, D. Vretenar， and P. Ring, Prog. Part. Nucl. Phys. 66, 519 (2011).   
[69] B.A. Nikolaus,T.Hoch， and D.G.Madland,Phys. Rev. C 46, 1757 (1992).   
[70] T.Burvenich,D.G.Madland, J.A. Maruhn,and P.-G. Reinhard, Phys. Rev. C 65, 044308 (2002).   
[71] J. Boguta and A. R. Bodmer, Nucl. Phys. A 292,413 (1977).   
[72] R. Brockmann and H. Toki, Phys. Rev. Lett. 68, 3408 (1992).   
[73] Y. Sugahara and H. Toki, Nucl. Phys. A 579， 557 (1994).   
[74] C. Fuchs,H. Lenske, and H. H. Wolter, Phys.Rev. C 52, 3043 (1995).   
[75] T.Niksic,D.Vretenar,P. Finelli， and P. Ring,Phys. Rev. C 66,024306 (2002).   
[76] Y. K. Gambhir, P. Ring,and A. Thimet,Ann. Phys. 198, 132 (1990).   
[77] P. Ring, Y.K.Gambhir， and G.A. Lalazissis, Comput. Phys. Commun. 105, 77 (1997).   
[78] S.-G. Zhou, J. Meng， and P. Ring, Phys. Rev. C 68, 034323 (2003)； AIP Conf. Pr0c.865,90 (2006)； S.-G. Zhou,J. Meng, P. Ring， and E.-G. Zhao,Phys. Rev. C 82,011301(R) (2010); L. Li, J. Meng, P. Ring, E.-G. Zhao, and S.-G. Zhou, Phys. Rev. C 85, 024312 (2012).   
[79] Y. Chen, L. Li, H. Liang, and J. Meng, Phys.Rev. C 85,067301 (2012).   
[80] L.-S.Geng, J. Meng， and H. Toki, Chin. Phys. Lett. 24, 1865 (2007).   
[81] W. Zhang, Z. P. Li, S.Q. Zhang, and J. Meng, Phys. Rev. C 81, 034302 (2010).   
[82] B.-N. Lu, E.-G. Zhao, and S.-G. Zhou, Phys. Rev.C 84,014328 (2011).   
[83] M.Warda,J.L.Egido,L.M.Robledo， and K.Pomorski, Phys. Rev. C 66,014310 (2002).   
[84] S. Karatzikos,A. Afanasjev,G. Lalazissis, and P. Ring, Phys. Lett. B 689,72 (2010).   
[85] J.Y. Zeng and T. S. Cheng，Nucl. Phys. A 405，1 (1983).   
[86] H. Molique and J. Dudek,Phys.Rev. C 56,1795 (1997).   
[87] J. Meng, J.-y. Guo,L. Liu, and S.-q. Zhang, Frontiers Phys. China 1,38 (2006).   
[88] N.Pillet, P. Quentin, and J. Libert, Nucl. Phys.A 697, 141 (2002)； T.V.N. Hao,P. Quentin，and L.Bonneau, Phys. Rev. C 86, 064307 (2012).   
[89] Z.-H. Zhang, J.-Y. Zeng,E.-G. Zhao, and S.-G. Zhou, Phys. Rev. C 83, 011304(R) (2011)； Z.-H. Zhang, X.- T.He, J.-Y. Zeng, E.-G. Zhao, and S.-G. Zhou, Phys. Rev. C 85,014324 (2012).   
[90] Y. Tian and Z.-Y.Ma,Chin. Phys. Lett.23,3226 (2006)；Y. Tian,Z. Ma， and P. Ring,Phys.Lett.B 676, 44 (2009)； Y. Tian, Z.-y. Ma, and P. Ring, Phys. Rev. C 79, 064301 (2009).   
[91] M.Bender,K.Rutz,P.-G.Reinhard,and J.A.Maruhn, Eur. Phys. J. A 8, 59 (2000).   
[92] P.W. Zhao, Z. P.Li, J. M. Yao,and J. Meng, Phys. Rev.C 82, 054319 (2010)；P. W. Zhao, L. S. Song, B. Sun, H. Geissel, and J. Meng, Phys.Rev. C 86, 064324 (2012).   
[93] W. Kutzelnigg, Int. J. Quantum Chem. 25,107 (1984). [94] F.Fillion-Gourdeau,E.Lorin，and A.D.Bandrauk, Phys.Rev.A 85,022506 (2012). [95]I. Reichstein and F.Bary Malik，Ann. Phys. 98,322 (1976). [96] B. N. Pomorska, Nucl. Phys. A 327, 1 (1979). [97] F. Tondeur, Nucl. Phys. A 442, 460 (1985). [98] M. Bender, P.-H. Heenen，and P. Bonche,Phys. Rev. C 70, 054304 (2004). [99] A.Andreev, G. Adamian， N. Antonenko, and S. Ivanova, Eur. Phys. J.A 26,327 (2005).   
[100] L.M. Robledo,M. Baldo，P. Schuck，and X.Vinas, Phys. Rev. C 77, 051301 (2008).   
[101] W. Younes and D. Gogny, Phys. Rev. C 80,054313 (2009).   
[102] R.Capote，M. Herman，P. Oblozinsky，P. Young, S.Goriely,T.Belgya,A.Ignatyuk,A.Koning,S. Hilaire,V.Plujko,M.Avrigeanu,O.Bersillon,M.Chadwick,T.Fukahori, Z. Ge, Y. Han, S. Kailas, J. Kopecky, V.Maslov，G.Reffo，M.Sin，E.Soukhovitskii，and P.Talou, Special Issue on Nuclear Reaction Data,Nucl. Data Sheets 110, 3107 (2009).   
[103] B. Singh,R. Zywina, and R. B. Firestone, Nucl. Data Sheets 97, 241 (2002).   
[104] G.A. Lalazissis, J. Konig,and P. Ring, Phys.Rev.C 55,540 (1997)；G.A. Lalazissis, S. Karatzikos,R. Fossion,D. P. Arteaga, A. V. Afanasjev, and P. Ring, Phys.Lett. B 671, 36 (2009).   
[105]M.Bender,K.Rutz,P.-G.Reinhard,J.A.Maruhn, and W. Greiner, Phys. Rev. C 60,034304 (1999).   
[106] G.A. Lalazissis,T. Niksic, D. Vretenar， and P.Ring, Phys. Rev. C 71, 024312 (2005).   
[107] T. Niksic, D. Vretenar， and P. Ring, Phys. Rev.C 78, 034318 (2008).   
[108]P.Jachimowicz,M.Kowal,and J.Skalski, Phys.Rev. C 85,034305 (2012).   
[109] N. Dubray and D. Regnier, Comput. Phys.Commun. 183,2035 (2012).   
[110] J.M. Yao, J. Meng,P.Ring，and D.Vretenar, Phys. Rev. C 81, 044311 (2010); J. M. Yao,H. Mei, H. Chen, J. Meng, P. Ring， and D. Vretenar, Phys. Rev. C 83, 014308 (2011)；J.-M.Yao,J. Peng,J.Meng，and P. Ring, Sci. China Phys. Mech. Astron. 54, 198 (2011).   
[111] H. L. Liu, F.R. Xu, Y. Sun,P.M. Walker, and R.Wyss, Eur. Phys. J. A 47, 135 (2011).   
[112] T.V.Nhan Hao，J. Le Bloas,M.-H.Koh,L.Bonneau，and P.Quentin, Int. J. Mod.Phys.E 21,1250051 (2012).