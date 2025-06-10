# Analytic continuation of single-particle resonance energy and wave function in relativistic mean field theory

S. S. Zhang, $^ { 1 }$ J. Meng,1,2,3, $^ *$ S. G. Zhou, $\mathbf { 1 } , \mathbf { 2 } , \mathbf { 3 }$ and G. C. Hillhouse $^ { 4 , 1 }$

$^ { 1 }$ School of Physics， Peking University， Beijing 100871， China （204号 $\mathcal { L }$ Institute of Theoretical Physics， Chinese Academy of Sciences, Beijing 10o080, China （204号 $\mathscr { S }$ Center of Theoretical Nuclear Physics, National Laboratory of Heavy Ion Accelerator， Lanzhou 730ooo， China 4Department of Physics， University of Stellenbosch, Private Bag X1， Matieland 7602， South Africa

Single-particle resonant states in spherical nuclei are studied by an analytic continuation in the coupling constant (ACCC） method within the framework of the self-consistent relativistic mean field (RMF） theory. Taking the neutron resonant state $\nu 1 g _ { 9 / 2 }$ in $^ { 6 0 }$ Ca as an example, we examine the analyticity of the eigenvalue and eigenfunction for the Dirac equation with respect to the coupling constant by means of a Padé approximant of the second kind. The RMF-ACCC approach is then applied to $\mathrm { ^ { 1 2 2 } Z r }$ and,for the first time, this approach is employed to investigate both the energies, widths and wave functions for $l \neq 0$ resonant states close to the continuum threshold. Predictions are also compared with corresponding results obtained from the scattering phase shift method.

PACS numbers: 25.70.Ef, 21.10.-k, 02.60.-x, 21.60.-n

# I. INTRODUCTION

The physics of exotic nuclei with unusual $N / Z$ ratios (isospin) has attracted world-wide attention. These nuclei are usually loosely bound and often exhibit resonances with a pronounced single-particle character since the Fermi surface approaches the continuum. In some nuclei, the valence nucleons can be easily scattered into single-particle resonant states (or Gamow states） in the continuum which is essential for the existence of exotic phenomena. For example, the halo in $^ { 1 1 }$ Li [1] can be successfully reproduced [2] and giant halo nuclei [3] are predicted by the relativistic continuum Hartree-Bogoliubov (RCHB) theory [4] in which the contribution from the continuum has been proven to be crucial to understand these halo phenomena. There are also other attempts to include the contribution from the continuum in the non-relativistic [5] and relativistic approaches [6]. By taking into account a few resonant states close to the continuum threshold with the BCS method [6],the relativistic mean field (RMF) theory seems to be able to reproduce the RCHB results and describe the main effcts of the continuum. It has also been shown that the contribution of the continuum to the giant resonances mainly comes from Gamow states [7, 8]. Therefore, a proper treatment of resonant states is important for a deeper understanding of the properties in exotic nuclei. Presently, several techniques have been developed to study resonant states in the continuum. One of them is the R-matrix theory in which resonance parameters (i.e. energy and width) can be reasonably determined from fitting the available experimental data [9]. The extended R-matrix theory [10] and the K-matrix theory [11] have also been developed. The conventional scattering theory is also an effcient tool for studying resonances. More precisely, the phase shift method is commonly used to determine parameters for a resonant state which corresponds to a pole of the S matrix [12]. By discretizing the continuum, the contribution of the resonant states can be self-consistently taken into account via a Bogoliubov transformation in coordinate space [2, 13].

Computationally, it is desired to deduce the properties of unbound states from the eigenvalues and eigenfunctions of Hamiltonians for bound states so that the methods developed for bound states can still be used. For this purpose, the bound-state-type methods have been developed, including the real stabilization method [14], the complex scaling method (CSM)[15],and the analytic continuation in the coupling constant (ACCC) method [16]. In the real stabilization method, the continuum is discretized in a box and the resonance can be found according to the fact that its energy should be stable against the change of the box size. Sometimes it is diffcult to find the appropriate box sizes,and it also turns out that this approach is suitable for narrow resonances only [17]. In the CSM, the wave function for a resonant state is transformed to the square-integrable wave function for a bound state by rotating the position vector in coordinate space into the complex plane. Since the CSM involves the calculations of complex matrix elements, the corresponding difficulties related to complex eigenvalue problem still exist. In the ACCC method, a resonant state becomes a bound state if one increases the attractive potential and the energy, width and wave function for the resonant state can be obtained by an analytic continuation carried out via a Padé approximant (PA） from the bound-state solutions. Compared with other bound-state-type methods, the ACCC approach is very effective and numerically quite simple because many methods available for bound-state problems can be used and the PA for analytic continuation can be implemented easily.

Within the framework of the non-relativistic Schrodinger equation, the ACCC method has been applied to investigate the energies and widths for resonant states in light nuclei combined with few-body methods [17, 18], and to study single-particle resonant states in spherical and deformed nuclei by solving the Schrodinger equation with Woods-Saxon potentials [19]. Based on the Schrodinger and Dirac equations,the stability and convergence of the energies and widths for single-particle resonant states with square-well, harmonicoscillator and Woods-Saxon potentials have been investigated and their dependence on the coupling constant interval and the order of the PA have been discussed in detail [20, 21].

The relativistic mean feld (RMF) theory is widely used to describe properties of nuclear matter and finite nuclei successfully, not only for those nuclei near the valley of stability, but also for exotic nuclei with large neutron (proton) excess [2, 22]. Previously the ACCC method was employed to study energies and widths for resonant states in stable nuclei $^ { 1 6 }$ 0 and $^ { 4 8 }$ Ca in RMF theory [23]. In the present work, we aim at exploring the single-particle resonant states, including resonance parameters and wave functions, in exotic nuclei by the ACCC method within the framework of the RMF theory. This paper represents the first application of the RMF-ACCC method to obtain both the wave functions and resonance parameters. The paper is organized as follows. In Sec. II the ACCC method combined with the RMF theory is presented. The numerical details are given in Sec. III and its application to the doubly magic nucleus $^ { 1 2 2 }$ Zr in Sec. IV. Finally, we give a brief summary in Sec. V.

# II. THEORETICALFRAMEWORK

# A. Relativistic Mean Field Theory

The basic ansatz of the RMF theory is a Lagrangian density whereby nucleons are described as Dirac particles which interact via the exchange of various mesons (the scalar $\sigma$ ， vector $\omega$ and iso-vector vector $\rho$ ）and the photon [4]

$$
\begin{array} { r l } { \mathcal { L } } & { = \bar { \psi } ( i \partial / - M ) \psi + \frac { 1 } { 2 } \partial _ { \mu } \sigma \partial ^ { \mu } \sigma - U ( \sigma ) - \frac { 1 } { 4 } \Omega _ { \mu \nu } \Omega ^ { \mu \nu } } \\ & { + \frac { 1 } { 2 } m _ { \omega } ^ { 2 } \omega _ { \mu } \omega ^ { \mu } - \frac { 1 } { 4 } \mathbf { R } _ { \mu \nu } \mathbf { R } ^ { \mu \nu } + \frac { 1 } { 2 } m _ { \rho } ^ { 2 } \rho _ { \mu } \rho ^ { \mu } - \frac { 1 } { 4 } F _ { \mu \nu } F ^ { \mu \nu } } \\ & { \quad - g _ { \sigma } \bar { \psi } \sigma \psi \ - \ g _ { \omega } \bar { \psi } \psi \psi \ - \ g _ { \rho } \bar { \psi } \pm \sigma \psi - \ e \bar { \psi } \mathbf { A } \psi , } \end{array}
$$

where $M$ is the nucleon mass and $m _ { \sigma } ( g _ { \sigma } ) , m _ { \omega } ( g _ { \omega } )$ ，and $m _ { \rho } \ \left( g _ { \rho } \right)$ are the masses (coupling constants) of the respective mesons.A nonlinear scalar self-interaction $U ( \sigma ) = \frac { 1 } { 2 } m _ { \sigma } ^ { 2 } \sigma ^ { 2 } + \frac { g _ { 2 } } { 3 } \sigma ^ { 3 } + \frac { g _ { 3 } } { 4 } \sigma ^ { 4 }$ 4 of theg meson has been included [24].The feld tensors for the vector mesons are given as

$$
\left\{ \begin{array} { l } { { \Omega ^ { \mu \nu } = \partial ^ { \mu } \omega ^ { \nu } - \partial ^ { \nu } \omega ^ { \mu } , } } \\ { { { } } } \\ { { { \bf R } ^ { \mu \nu } = \partial ^ { \mu } \pmb { \rho } ^ { \nu } - \partial ^ { \nu } \pmb { \rho } ^ { \mu } - g ^ { \rho } ( \pmb { \rho } ^ { \mu } \times \pmb { \rho } ^ { \nu } ) , } } \\ { { { } } } \\ { { F ^ { \mu \nu } = \partial ^ { \mu } { \bf A } ^ { \nu } - \partial ^ { \nu } { \bf A } ^ { \mu } . } } \end{array} \right.
$$

The classical variation principle gives the following equations of motion

$$
[ { \pmb \alpha } \cdot { \bf p } + V _ { V } ( { \bf r } ) + \beta ( M + V _ { S } ( { \bf r } ) ) ] \psi _ { i } \ = \ \epsilon _ { i } \psi _ { i } ,
$$

for the nucleon spinors,where $\varepsilon _ { i }$ and $\psi _ { i }$ are the single-particle energy and spinor wave function respectively, and the Klein-Gordon equations

$$
\left\{ \begin{array} { l l } { { \displaystyle ( - \Delta \sigma ~ + ~ U ^ { \prime } ( \sigma ) ) ~ = ~ g _ { \sigma } \rho _ { s } , } } \\ { { ~ } } \\ { { ( - \Delta ~ + ~ m _ { \omega } ^ { 2 } ) \omega ^ { \mu } ~ = ~ g _ { \omega } j ^ { \mu } ( { \bf r } ) , } } \\ { { ~ } } \\ { { ( - \Delta ~ + ~ m _ { \rho } ^ { 2 } ) \rho ^ { \mu } ~ = ~ g _ { \rho } { \bf j } ^ { \mu } ( { \bf r } ) , } } \\ { { ~ } } \\ { { - \Delta ~ A _ { 0 } ^ { \mu } ( { \bf r } ) ~ = ~ e j _ { \rho } ^ { \mu } ( { \bf r } ) , } } \end{array} \right.
$$

for the mesons, where

$$
\left\{ \begin{array} { l l } { { V _ { V } ( { \bf r } ) = g _ { \omega } \phi + g _ { \rho } \pmb { \rho } \tau + \frac { 1 } { 2 } e ( 1 - \tau _ { 3 } ) \pmb { \mathrm { A } } , } } \\ { { V _ { S } ( \pmb { \mathrm { r } } ) = g _ { \sigma } \sigma , } } \end{array} \right.
$$

are the vector and scalar potentials respectively and the source terms for the mesons are

$$
\left\{ \begin{array} { l l } { \rho _ { s } } & { = \displaystyle \sum _ { i = 1 } ^ { A } \bar { \psi } _ { i } \psi _ { i } , } \\ { j ^ { \mu } ( { \bf r } ) = \displaystyle \sum _ { i = 1 } ^ { A } \bar { \psi } _ { i } \gamma ^ { \mu } \psi _ { i } , } \\ { { \bf j } ^ { \mu } ( { \bf r } ) = \displaystyle \sum _ { i = 1 } ^ { A } \bar { \psi } _ { i } \gamma ^ { \mu } \tau \psi _ { i } , } \\ { j _ { p } ^ { \mu } ( { \bf r } ) = \displaystyle \sum _ { i = 1 } ^ { A } \bar { \psi } _ { i } \gamma ^ { \mu } \frac { 1 - \tau _ { 3 } } { 2 } \psi _ { i } . } \end{array} \right.
$$

It should be noted that the contribution of negative energy states are neglected, i.e.， the vacuum is not polarized. Moreover, the mean field approximation is carried out via replacing meson field operators in Eq. (3) by their expectation values, since the coupled equations Eq. (3) and Eq. (4) are nonlinear quantum field equations and their exact solutions are very complicated. In this way, the nucleons are assumed to move independently in the classical meson fields. The coupled equations can be solved self-consistently by iteration.

For spherical nuclei, the potential of the nucleon and the sources of meson fields depend only on the radial coordinate $r$ . The spinor is characterized by the angular momentum quantum numbers $l$ ， $j$ ， $m$ , the isospin $t = \pm \frac { 1 } { 2 }$ for neutron and proton respectively, and the other quantum number $i$ . The Dirac spinor has the form

$$
\psi ( { \bf r } ) = \left( \begin{array} { c } { \mathrm { i } \frac { G _ { i } ^ { l j } ( r ) } { r } Y _ { j m } ^ { l } ( \theta , \phi ) } \\ { \frac { F _ { i } ^ { l j } ( r ) } { r } ( \pmb { \sigma } \cdot \hat { \bf r } ) Y _ { j m } ^ { l } ( \theta , \phi ) } \end{array} \right) \chi _ { t } ( t ) ,
$$

where $Y _ { j m } ^ { l } ( \theta , \phi )$ are the spinor spherical harmonics. The radial equation of the spinor, i.e. Eq. (3),can be reduced to [4]

$$
\begin{array} { r } { ( - \displaystyle \frac { \partial } { \partial r } + \displaystyle \frac { \kappa } { r } ) F _ { i } ^ { l j } ( r ) + \left[ M + V _ { p } ( r ) \right] G _ { i } ^ { l j } ( r ) = \varepsilon _ { i } G _ { i } ^ { l j } ( r ) , } \\ { ( \displaystyle \frac { \partial } { \partial r } + \displaystyle \frac { \kappa } { r } ) G _ { i } ^ { l j } ( r ) - \left[ M - V _ { m } ( r ) \right] F _ { i } ^ { l j } ( r ) = \varepsilon _ { i } F _ { i } ^ { l j } ( r ) , } \end{array}
$$

in which $V _ { p } ( r ) = V _ { V } ( r ) + V _ { S } ( r )$ ， $V _ { m } ( r ) = V _ { V } ( r ) - V _ { S } ( r )$ ,and $\kappa = ( - 1 ) ^ { j + l + 1 / 2 } ( j + 1 / 2 )$ . The meson field equations can be reduced to

$$
\left( \frac { \partial ^ { 2 } } { \partial r ^ { 2 } } - \frac { 2 } { r } \frac { \partial } { \partial r } + m _ { \phi } ^ { 2 } \right) \phi = s _ { \phi } ( r ) ,
$$

where $\phi = \sigma$ ， $\omega$ ， $\rho$ ，and photon（ $m _ { \phi } = 0$ for photon). The source terms read

$$
s _ { \phi } ( r ) = \left\{ \begin{array} { l l } { - g _ { \sigma } \rho _ { s } - g _ { 2 } \sigma ^ { 2 } ( r ) - g _ { 3 } \sigma ^ { 3 } ( r ) \mathrm { ~ f o r ~ t h e ~ } \sigma \mathrm { ~ f i e l d } , } \\ { \qquad } \\ { g _ { \omega } \rho _ { v } } & { \mathrm { f o r ~ t h e ~ } \omega \mathrm { ~ f i e l d } , } \\ { g _ { \rho } \rho _ { 3 } ( r ) } & { \mathrm { f o r ~ t h e ~ } \rho \mathrm { ~ f i e l d } , } \\ { e \rho _ { c } ( r ) } & { \mathrm { f o r ~ t h e ~ C o u l o m } . } \end{array} \right.
$$

and

$$
\left\{ \begin{array} { l l } { \displaystyle 4 \pi r ^ { 2 } \rho _ { s } ( r ) = \sum _ { i = 1 } ^ { A } ( \vert G _ { i } ( r ) \vert ^ { 2 } - \vert F _ { i } ( r ) \vert ^ { 2 } ) , } \\ { \displaystyle 4 \pi r ^ { 2 } \rho _ { s } ( r ) = \sum _ { i = 1 } ^ { A } ( \vert G _ { i } ( r ) \vert ^ { 2 } + \vert F _ { i } ( r ) \vert ^ { 2 } ) , } \\ { \displaystyle 4 \pi r ^ { 2 } \rho _ { 3 } ( r ) = \sum _ { p = 1 } ^ { Z } ( \vert G _ { p } ( r ) \vert ^ { 2 } + \vert F _ { p } ( r ) \vert ^ { 2 } ) - \sum _ { n = 1 } ^ { N } ( \vert G _ { n } ( r ) \vert ^ { 2 } + \vert F _ { n } ( r ) \vert ^ { 2 } ) , } \\ { \displaystyle 4 \pi r ^ { 2 } \rho _ { c } ( r ) = \sum _ { p = 1 } ^ { Z } ( \vert G _ { p } ( r ) \vert ^ { 2 } + \vert F _ { p } ( r ) \vert ^ { 2 } ) . } \end{array} \right.
$$

# B. Analytic Continuation in the Coupling Constant for Resonance Parameters and Gamow Wave Functions

By solving Eqs. (8) and (9) in a meshed box of size $R _ { 0 }$ self-consistently, one can calculate the ground state properties of a nucleus. The vector potential $V _ { V } ( r )$ and the scalar potential $V _ { S } ( r )$ ， energies and wave functions for bound states are also obtained. By increasing the attractive potential as $V _ { p } ( r ) \to \lambda V _ { p } ( r )$ ，a resonant state will be lowered and becomes a bound state if the coupling constant $\lambda$ is large enough. Near the branch point $\lambda _ { 0 }$ ， defined by the scattering threshold $k ( \lambda _ { 0 } ) = 0$ [16], the wave number $k ( \lambda )$ behaves as

$$
k ( \lambda ) \sim \left\{ \begin{array} { l l } { i \sqrt { \lambda - \lambda _ { 0 } } , } & { l > 0 , } \\ { i ( \lambda - \lambda _ { 0 } ) , } & { l = 0 . } \end{array} \right.
$$

These properties suggest an analytic continuation of the wave number $k$ in the complex $\lambda$ （204号 plane from the bound-state region into the resonance region by Padé approximant of the second kind (PAII） [16]

$$
k ( x ) \approx k ^ { [ L , N ] } ( x ) = i \frac { c _ { 0 } + c _ { 1 } x + c _ { 2 } x ^ { 2 } + . . . + c _ { L } x ^ { L } } { 1 + d _ { 1 } x + d _ { 2 } x ^ { 2 } + . . . + d _ { N } x ^ { N } } ,
$$

where $x \equiv \sqrt { \lambda - \lambda _ { 0 } }$ ，and $c _ { 0 } , c _ { 1 } , \ldots , c _ { L } , d _ { 1 } , d _ { 2 } , \ldots , d _ { N }$ are the coeffcients of PA. These coefficients can be determined by a set of reference points $x _ { i }$ and $k ( x _ { i } )$ obtained from the Dirac equation with $\lambda _ { i } > \lambda _ { 0 } , i = 1 , 2 , . . . , L + N + 1$ .With the complex wave number （20 $k ( \lambda = 1 ) = k _ { r } + i k _ { i }$ ， the resonance energy $E$ and the width $\Gamma$ can be extracted from the relation $\varepsilon = E - i \frac { \Gamma } { 2 } ( E , \Gamma \in \mathbb { R } )$ and $k ^ { 2 } = \varepsilon ^ { 2 } - M ^ { 2 }$ ,i.e.,

$$
\begin{array} { l } { E = \sqrt { \frac { \sqrt { ( M ^ { 2 } + k _ { r } ^ { 2 } - k _ { i } ^ { 2 } ) ^ { 2 } + 4 k _ { r } ^ { 2 } k _ { i } ^ { 2 } } + ( M ^ { 2 } + k _ { r } ^ { 2 } - k _ { i } ^ { 2 } ) } { 2 } } - M , } \\ { \Gamma = \sqrt { 2 \sqrt { ( M ^ { 2 } + k _ { r } ^ { 2 } - k _ { i } ^ { 2 } ) ^ { 2 } + 4 k _ { r } ^ { 2 } k _ { i } ^ { 2 } } - 2 ( M ^ { 2 } + k _ { r } ^ { 2 } - k _ { i } ^ { 2 } ) } . } \end{array}
$$

In the non-relativistic limit ( $k \ll M ,$ ，Eq.(14) reduces to

$$
E = \frac { k _ { r } ^ { 2 } - k _ { i } ^ { 2 } } { 2 M } , \quad \quad \quad \quad \Gamma = \frac { 2 k _ { r } k _ { i } } { M } . \nonumber
$$

It is evident that the continuation in the coupling constant can be replaced by the continuation in $k$ plane along the $k ( \lambda )$ trajectory determined by Eq.(13) to the point $k _ { R }$ （204号 corresponding to the wave number for Gamow state, i.e., $k _ { R } = k ^ { \lfloor L , N \rfloor } ( \lambda = 1 )$ [16]. Similarly, the wave function $\varphi ( k _ { R } , r )$ for a resonant state can be obtained by an analytic continuation of the bound-state wave function $\varphi ( k _ { i } , r )$ in the complex $k$ plane. One can also prove that the wave function $\varphi ( k , r )$ is an analytic function of the wave number $k$ in the inner region （20 $r < {  { R _ { 0 } } }$ where the Jost function analyticity dominates [16]. Therefore, we use the technique, which has been adopted to find the complex resonance energy, to determine the resonance wave function $\varphi ( k _ { R } , r )$ . Firstly, we construct the PA to define the resonance wave function at any point $r$ in the inner region ( $( r < R _ { 0 }$ ）[16]

$$
\varphi ^ { [ L , N ] } ( k , r ) = \frac { P _ { L } ( k , r ) } { Q _ { N } ( k , r ) } = \frac { a _ { 0 } ( r ) + a _ { 1 } ( r ) k + a _ { 2 } ( r ) k ^ { 2 } + . . . + a _ { L } ( r ) k ^ { L } } { 1 + b _ { 1 } ( r ) k + b _ { 2 } ( r ) k ^ { 2 } + . . . + b _ { N } ( r ) k ^ { N } } ,
$$

where the coefficients $a _ { i } ( \boldsymbol { r } ) ~ ( i = 0 , 1 , \dots , L )$ and $b _ { j } ( r ) \ ( j = 1 , 2 , \ldots , N )$ are dependent on $r$ These coeffcients can be determined by a set of reference points $k _ { i }$ and $\varphi ( k _ { i } , r )$ obtained

from the Dirac equation with $\lambda _ { i } > \lambda _ { 0 } , ( i = 1 , 2 , . . . , L + N + 1 )$ . The resonance wave function （204号 $\varphi ( k _ { R } , r ) = \varphi ^ { \lfloor L , N \rfloor } ( k _ { R } , r )$ ( $r < R _ { 0 }$ ） can be extrapolated in this way.

Eq. (8) can be rewritten as two decoupled Schrodinger-like equations for the upper and the lower components respectively [25]. For neutrons,the Schrodinger-like equation for the upper component reads

$$
\frac { \partial ^ { 2 } G _ { i } ^ { l j } ( r ) } { \partial r ^ { 2 } } - \frac { \kappa _ { i } ( \kappa _ { i } + 1 ) } { r ^ { 2 } } G _ { i } ^ { l j } ( r ) + ( \varepsilon _ { i } ^ { 2 } - M ^ { 2 } ) G _ { i } ^ { l j } ( r ) = 0 ,
$$

in the outer region where $V _ { V } ( r ) \simeq 0$ and $V _ { S } ( r ) \simeq 0$ . Its solution is the well known RiccatiHankel function

$$
\hat { h } _ { \kappa } ^ { \pm } ( z ) = \hat { n } _ { \kappa } ( z ) \pm i \hat { j } _ { \kappa } ( z ) , ~ z = k r ,
$$

where $\hat { j } _ { \kappa } ( z ) = z j _ { \kappa } ( z )$ is the usual regular solution, i.e. Riccati-Bessel function, and $\hat { n } _ { \kappa } ( z ) =$ $z n _ { \kappa } ( z )$ is the irregular solution,i.e. Riccati-Neumann function. The outer wave function is matched to the inner wave function at $r = r _ { m } < R _ { 0 }$

$$
\varphi ^ { [ L , N ] } ( k _ { R } , r _ { m } ) = C ( k _ { R } ) \left[ \hat { j } _ { \kappa } ( k _ { R } r _ { m } ) + D ( k _ { R } ) \hat { n } _ { \kappa } ( k _ { R } r _ { m } ) \right] ,
$$

where $C ( k _ { R } )$ is the coefficient for matching and $D ( k _ { R } ) = \tan \delta _ { \kappa } ( k _ { R } )$ with $\delta _ { \kappa } ( k _ { R } )$ the phase shift. It has been found that $\delta _ { \kappa } ( k _ { R } )$ is almost a constant when $r _ { m }$ is large enough. Given the upper component, the lower component $F _ { \kappa } ( r )$ can be calculated from the relationship between the upper and the lower components derived from Eq.(8),i.e.,

$$
F _ { \kappa } ( r ) = \frac { ( \varepsilon - m ) } { k _ { R } C ( k _ { R } ) } \left[ \hat { j } _ { \kappa - 1 } ( k _ { R } r ) + D ( k _ { R } ) \hat { n } _ { \kappa - 1 } ( k _ { R } r ) \right] .
$$

Finally， the resonance wave function is normalized according to the Zel'dovich procedures [16].

# III. NUMERICAL DETAILS

In this section we give the details on how the ACCC method is realized within the framework of the RMF theory and exploit the analyticity of the eigenvalues and eigenfunctions of the Dirac equation with respect to the coupling constant. In RCHB calculations $^ { 6 0 }$ Ca is the doorway for exotic phenomena such as giant halos [3], in which the neutron resonant states play an important role in the continuum. We select the neutron resonant state $\nu 1 g _ { 9 / 2 }$ in $\mathrm { ^ { 6 0 } C a }$ （204 to investigate the analyticity of the eigenvalue and eigenfunction for the Dirac equation with respect to the coupling constant. The RMF equations are solved in a spherical box of the size $R _ { 0 } = 2 0$ fm,with a mesh size of $\delta r = 0 . 0 5$ fm [26]. Several well used effective interactions for the RMF Lagrangian will be used and the corresponding results will be compared. The energy, width and wave function for the $\nu 1 g _ { 9 / 2 }$ resonant state in $^ { 6 0 }$ Ca are obtained with the procedure given in the last section. As the stability and convergence (e.g., the dependence on PA order) of the energies and widths in the Dirac and Schrodinger equations have been investigated in Refs. [2O, 21],we do not discuss them here and use $L = N = 4$ PA for the present calculations.

In Tab. I, we present the energies and widths for $\nu 1 g _ { 9 / 2 }$ in $^ { 6 0 }$ Ca calculated with effective interactions NL3 [27], NLSH [28], TMA [29] and the newly developed PK1 [30] parametrization. The results from the scattering phase shift method (RMF-S) obtained similarly as in Ref. [6] are also included for comparison. The first step in RMF-S is to solve the Dirac equation [Eq. (8)] with scattering boundary conditions for the continuum spectrum. The solutions,upper and lower components, have the same form as here in Eq. (19) and Eq. (20) respectively. The coefficients $C$ and $D$ in Eq. (19) and Eq. (20) are fixed by the normalization condition of the scattering wave functions and the phase shift $\delta$ is calculated from the matching conditions. It should be mentioned that the energy used in the wave functions is real and not unique,as opposed to complex and the unique value which is determined by the ACCC method in advance. In the vicinity of an isolated resonance, the resonance energy and width are extracted from the derivative of the phase shift $\delta$ in Breit-Wigner form, i.e.,

$$
\frac { d \delta ( E ) } { d E } = \frac { \Gamma / 2 } { ( E _ { r } - E ) ^ { 2 } + \Gamma ^ { 2 } / 4 } .
$$

After discretizing the real energy for scattering solutions and phase shift variation， the resonance energy is uniquely determined.

One can find from Tab. I that the results from the ACCC and the scattering methods agree well. Different effective interactions give similar energies and widths. Therefore in the following calculations, we use only the effective interaction NL3 for illustration.

The resonance energy $E$ and width $\Gamma$ for the neutron resonant state $\nu 1 g _ { 9 / 2 }$ in $^ { 6 0 }$ Ca, as a function of the coupling constant $\lambda$ , are exhibited in Fig. 1. Filled circles and crosses are the solutions of the Dirac equation [Eq. (8)],and the former is used as input in the ACCC method. Solid curves are the outcome of $L = N = 4$ PA [Eq. (13)]. The dashed vertical line corresponds to the branch point $\lambda _ { 0 } > 1$ . When $\lambda > \lambda _ { 0 }$ ， the particle is bound. With $\lambda$ decreasing from $\lambda _ { 0 }$ down to 1,a nonvanishing imaginary part appears in the complex energy expressed by Eq. (14). At $\lambda = 1$ ， one gets the resonance energy $E$ and width $\Gamma$ . The agreement between the exact solutions of the Dirac equation with large coupling constant (crosses in Fig. 1) and the extrapolated results of PA (solid energy curve) is quite good, which demonstrates the validity of the ACCC method. The smooth solid line indicates good analyticity of the eigenvalue for the Dirac equation with respect to the coupling constant. The same results can also be obtained for the case of $L = N = 5$ and $L = N = 6$ PAs, similar as in Ref. [20, 21].

In Fig. 2, we show the real and imaginary parts of the upper component $G ( r )$ and the lower component $F ( r )$ at $r = 5$ fm and $r = 1 0$ fm respectively as functions of the resonance energy $E$ (which corresponds to the coupling constant $\lambda$ displayed in Fig. 1). Symbols in Fig. 2 have the same meaning as those in Fig.1. The neutron feels much stronger effect from the nuclear potential at $r = 5$ fm than at $r = 1 0$ fm. Similar to the case of the eigenvalue discussed above, the real and the imaginary part of each component behave smoothly, which indicates good analyticity of the eigenfunction for the Dirac equation with respect to the coupling constant.

The wave function obtained from the analytic continuation is connected continuously to the free wave function at the matching point $r _ { m }$ . On one hand, the matching point $r _ { m }$ （204号 should be large enough to make sure that the potential at $r _ { m }$ vanishes,which is required by the outer part of the wave function. On the other hand, $r _ { m }$ should be far enough from the box radius $R _ { 0 }$ to guarantee that the inner part of the wave function can be obtained accurately. In the lower panel of Fig. 3, the potential $V _ { V } ( r ) + V _ { S } ( r )$ for $^ { 6 0 }$ Ca is plotted. One finds that when $r > 1 4$ fm，the potential becomes smaller than $1 0 ^ { - 4 }$ MeV which is good enough for the precision in our calculations. The upper limit of the matching point $r _ { m }$ can be estimated by the behavior of the density from the upper panel in Fig.3. The neutron density $\rho _ { n } ( r )$ in $^ { 6 0 }$ Ca and $\rho _ { \nu 1 g _ { 9 / 2 } } ( r ) \equiv [ | G ( r ) | ^ { 2 } + | F ( r ) | ^ { 2 } ] / 4 \pi r ^ { 2 }$ decline rapidly in the vicinity of 20 fm because of the boundary condition in the RMF calculation. The density curves in the range $r < 1 8$ fm are smooth and behave reasonably. Therefore, the matching point should be chosen at any point between 14 fm and 18 fm. We present the wave function for the neutron resonant state $\nu 1 g _ { 9 / 2 }$ in $^ { 6 0 } \mathrm { C a }$ with different matching points in Fig. 4. As expected, the wave function is the same when changing the matching point $r _ { m }$ from 14 fm to 18 fm. In the following calculations, the wave function will be matched at $r _ { m } = 1 8$ fm,

unless otherwise specified.

# IV. APPLICATION TO SINGLE-PARTICLE RESONANT STATES IN $^ { 1 2 2 }$ ZR

We apply the ACCC method within the framework of the RMF theory to calculate the energies, widths and wave functions for the resonant states in $^ { 1 2 2 }$ Zr. Since $\mathrm { ^ { 1 2 2 } Z r }$ is the core of the giant neutron halo predicted in RCHB calculations [3], and the resonant states in $\mathrm { ^ { 1 2 2 } Z r }$ （20 have been obtained by the scattering method [6],we choose this nucleus for comparison.

In Fig. 5, the energies and widths for the resonant states $\nu 3 p _ { 3 / 2 } , \nu 3 p _ { 1 / 2 } , \nu 2 f _ { 7 / 2 } , \nu 2 f _ { 5 / 2 }$ $\nu 1 h _ { 9 / 2 }$ and $\nu 1 i _ { 1 3 / 2 }$ are presented as a planar $E$ $\Gamma$ plot.The results of the ACCC and the scattering methods are in good agreement with each other for most of these states. From both methods, $\nu 2 f _ { 5 / 2 }$ and $\nu 1 i _ { 1 3 / 2 }$ have large widths, while $\nu 2 f _ { 7 / 2 }$ and $\nu 1 h _ { 9 / 2 }$ are very narrow. The width for $\nu 3 p _ { 3 / 2 }$ from the scattering method is slightly larger than our calculation. As for the resonant state $\nu 3 p _ { 1 / 2 }$ ， neither the energy nor the width can be extracted from the scattering calculation. From a quantum mechanical point of view, these single-particle resonant states are quasi-stationary ones captured by centrifugal barriers. The decay width for a resonant state can be roughly explained by the penetration through the barrier. For those states with the same $l$ , i.e., the same centrifugal barrier, the higher state has a larger width, e.g., for the two $f$ states $\nu 2 f _ { 5 / 2 }$ and $\nu 2 f _ { 7 / 2 }$ . Although $\nu 1 h _ { 9 / 2 }$ is higher than $\nu 2 f _ { 5 / 2 }$ ， its width is smallr because of higher centrifugal barrier. A similar argument also holds for a much higher but narrow state $\nu 1 i _ { 1 3 / 2 }$

The wave functions for the resonant states $\nu 3 p _ { 3 / 2 } , \nu 2 f _ { 7 / 2 } , \nu 2 f _ { 5 / 2 }$ and $\nu 1 h _ { 9 / 2 }$ are respectively exhibited in Figs.6,7, 8,and 9. Since the imaginary part of the wave function is neglected in the scattering calculations [5, 6],only the real parts of the upper and the lower components are given and compared in these figures. In Fig. 6,one finds a considerable difference for the upper components at large $r$ in $\nu 3 p _ { 3 / 2 }$ between these two methods. This difference is consistent with the difference in energy and width as seen in Fig. 5.A similar difference is also seen for $\nu 2 f _ { 5 / 2 }$ in Fig.8. For those states where the two methods give nearly the same energies and widths, e.g., $\nu 2 f _ { 7 / 2 }$ and $\nu 1 h _ { 9 / 2 }$ , the wave functions agree quite well. The small difference for the wave functions between these two methods found in Figs. 7 and 9 might be from the neglect of the imaginary part of the wave function in the scattering method.

# V. SUMMARY

In summary, the method of the analytic continuation in the coupling constant (ACCC) has been developed within the framework of the relativistic mean feld (RMF） theory and used to investigate the resonance energies, widths and wave functions for single-particle resonant states in exotic nuclei. The analyticity of these quantities, as functions of the coupling constant, are exploited for the neutron resonant state $\nu 1 g _ { 9 / 2 }$ in $^ { 6 0 }$ Ca. The energies, widths and wave functions for some resonant states in $\mathrm { ^ { 1 2 2 } Z r }$ are calculated and compared with those obtained from the scattering method. The results from the ACCC method agrees satisfactorily with those from the scattering calculation as well as available data [23]. It is expected that the RMF-ACCC method, combined with the BCS theory, can be generalized to describe exotic phenomena in unstable nuclei.

# Acknowledgments

This work is partly supported by the Major State Basic Research Development Program Under Contract Number G2000077407, the National Natural Science Foundation of China under Grant No. 10025522，and 10221003,and the Doctoral Program Foundation from the Ministry of Education in China under Grant No. 20030001086,as well as the National Science Foundation of South Africa under Grant No. 2O54166.

[1] I. Tanihata, H. Hamagaki,and O. Hashimoto et al. Phys.Rev. Lett. 55, 2676 (1985).   
[2] J. Meng and P. Ring, Phys. Rev. Lett. 77, 3963 (1996).   
[3] J. Meng and P. Ring, Phys. Rev. Lett. 80, 460 (1998). J. Meng, H. Toki, J. Y. Zeng, S. Q.   
Zhang,and S. G. Zhou, Phy. Rev. C 65, 041302(R) (2002).   
[4] J. Meng, Nucl. Phys. A635,31 (1998).   
[5] N. Sandulescu, Nguyen Van Giai,and R. J. Liotta, Phy. Rev. C 61,O61301(R) (2000).   
[6] N. Sandulescu, L. S. Geng, H. Toki,and G. Hillhouse, Phys. Rev. C 68, 054323 (2003).   
[7] P. Curutchet, T. Vertse,and R. J. Liotta,Phys. Rev. C 39,1020 (1989).   
[8] L.G. Cao and Z. Y. Ma, Phys. Rev. C 66, 024311 (2002).   
[9] E. Wigner and L. Eisenbud, Phys.Rev. 72, 29 (1947). [10] G. M. Hale, R. E. Brown,and N. Jarmie, Phys. Rev. Lett. 59, 763 (1987).   
[11] J. Humblet, B.W.Filippone,and S.E. Koonin, Phys.Rev. C 44, 2530 (1991).   
[12] J. R. Taylor, Scattering Theory: The Quantum Theory on Nonrelativistic Collisions, (John Wiley & Sons,New York, 1972).   
[13] J. Dobaczewski, H. Flocard, and J. Treiner, Nucl. Phys. A422,1O3 (1984).   
[14] A. U. Hazi and H. S. Taylor, Phys. Rev. A 1, 1109 (1970).   
[15] Y. K. Ho,Phys. Rep. 99,1 (1983).   
[16] V. I. Kukulin, V. M. Krasnopl'sky and J. Horacek, Theory of Resonances: Principles and Applications (Kluwer Academic, Dordrecht, 1989).   
[17] N. Tanaka, Y. Suzuki, and K. Varga et al. Phys. Rev. C 59,1391 (1999).   
[18] S. Aoyama, Phys. Rev. Lett. 89,052501 (2002).   
[19] G. Cattapan and E. Maglione, Phys. Rev. C 61, O67301 (2000).   
[20] S. S. Zhang, J. Meng,and J. Y. Guo, High Ener. Phys. and Nucl. Phys. 27, 1095 (2003) (in Chinese).   
[21] S. S. Zhang, J. Y. Guo, S. Q. Zhang,and J. Meng, Chin. Phys. Lett. 21, 632 (2004). [22] P. Ring, Prog. Part. Nucl. Phys. 37, 193 (1996).   
[23] S. C. Yang, J. Meng,and S. G. Zhou, Chin. Phys. Lett.18, 196 (2001).   
[24] J. Boguta and A. R. Bodmer, Nucl. Phys. A292 (1977) 413.   
[25] J. Meng, K. Sugawara-Tanabe, S. Yamaji, P. Ring, and A. Arima, Phys. Rev. C 58, 628(R) (1998). J. Meng, K. Sugawara-Tanabe, S. Yamaji, and A. Arima, Phys. Rev. C 59,154 (1999). [26] S.G. Zhou, J. Meng,and P. Ring, Phys. Rev. C 68,034323 (2003).   
[27] G. A. Lalazissis, J. Konig, and P. Ring, Phys. Rev. C 55, 540 (1997).   
[28] M. M. Sharma, M. A. Nagarajan,and P. Ring, Phys. Lett. B 312,377 (1993)   
[29] Y. Sugahara and H. Toki, Nucl. Phys. A579, 557 (1994).   
[30] W. H. Long,J. Meng， N. V. Giai, and S. G. Zhou. Phys. Rev. C (in press). [arXiv: nucl-th/0311031]

Tab. I: Energies and widths ( $E$ , I) in MeV for the neutron resonant state $\nu 1 g _ { 9 / 2 }$ in $^ { 6 0 }$ Ca calculated by the ACCC (RMF-ACCC) and the scattering (RMF-S) method with the effective interactions NL3, NLSH, PK1, and TMA.

<html><body><table><tr><td></td><td>NL3</td><td>NLSH</td><td>PK1</td><td>TMA</td></tr><tr><td>RMF-ACCC [MeV]</td><td>(0.49, 0.0005)</td><td>(0.47, 0.0004)</td><td>(0.77, 0.0009)</td><td>(0.77, 0.0009)</td></tr><tr><td>RMF-S [MeV]</td><td>(0.54, 0.0001)</td><td>(0.53, 0.0001)</td><td>(0.85, 0.0006)</td><td>(0.83, 0.0005)</td></tr></table></body></html>

![](images/b144f7d1fcd950e6413593e39a32ce43947e6ea0bd4a40c13046711c538d39dd.jpg)  
Fig.1:Energy $E$ and width $\Gamma$ for the neutron resonant state $\nu 1 g _ { 9 / 2 }$ in $^ { 6 0 } \mathrm { C a }$ ， as a function of the coupling constant $\lambda$ . Filled circles and crosses are the solutions of the Dirac equation,and the former is used as input in the ACCC method. Solid curves are the outcome of $L = N = 4$ PA.

![](images/b8f1fa4513daa07c6cad1061dd9ca5c642cbd63b505d73546f6472513841b6a6.jpg)  
Fig. 2: The real and imaginary part of the upper component $G ( r )$ and the lower component $F ( r )$ for the neutron $\nu 1 g _ { 9 / 2 }$ state in $^ { 6 0 } \mathrm { C a }$ at (a) $r = 5$ fm and (b) $r = 1 0$ fm as functions of the resonance energy $E$ (which corresponds to the coupling constant $\lambda$ displayed in Fig. 1). Symbols have the same meaning as those in Fig. 1.

![](images/eb7cbefa183e297d15e14eaeaa22b8c8818e9dfb037d258cbee5c806fb14e4c2.jpg)  
Fig. 3: Neutron densities for $^ { 6 0 }$ Ca and for the neutron $\nu 1 g _ { 9 / 2 }$ state (upper panel)； the potential （204号 $V _ { V } ( r ) + V _ { S } ( r )$ ， the single-particle neutron bound states and the neutron resonant state $\nu 1 g _ { 9 / 2 }$ （20 (lower panel).

![](images/7d19e5ab0458291539de1c9ab06414c911a47a11956dafaef2f43be6de3fc74c.jpg)  
Fig. 4: Real parts of the upper and lower components of the radial wave function for the neutron （20 $\nu 1 g _ { 9 / 2 }$ state in $^ { 6 0 }$ Ca calculated by the ACCC method with diferent matching points $r _ { m }$ ：

![](images/0d94af518403d24401d779f8a362f357becf81d1961e04e9f00ccbb695a8dba5.jpg)  
Fig. 5:Energies and widths for the neutron state $\nu 3 p _ { 3 / 2 } , \nu 3 p _ { 1 / 2 } , \nu 2 f _ { 7 / 2 } , \nu 2 f _ { 5 / 2 } , \nu 1 h _ { 9 / 2 }$ ，and （20 $\nu 1 i _ { 1 3 / 2 }$ in $\mathrm { ^ { 1 2 2 } Z r }$ . Solid circles represent the results of the ACCC method, while open circles denote the results of the scattering method.

![](images/1d39a7260fab943635560c28548bbc298a6fe140aea126f469535f86a105227d.jpg)  
Fig.6:Real parts of the upper and lower components of radial wave functions for the neutron resonant state $\nu 3 p _ { 3 / 2 }$ in $^ { 1 2 2 } \mathrm { Z r }$ . Solid and dashed curves represent the results of the ACCC and the scattering method respectively.

![](images/874d89639d30b08f85db9137f09b41f9467e6155c8878df6e86acfd6b0db4499.jpg)  
Fig. 7: Similar as Fig. 6, but for the neutron resonant state $\nu 2 f _ { 7 / 2 }$ in $^ { 1 2 2 } \mathrm { Z r }$

![](images/bccb93a33b2f2a39d0cae9877c0a8b64d1a9cda49aac11656e6b44ce486c25f6.jpg)  
Fig. 8: Similar as Fig. 6, but for the neutron resonant state $\nu 2 f _ { 5 / 2 }$ in $\mathrm { ^ { 1 2 2 } Z r }$

![](images/ec61ebe68513db4692fb5182c652ec8203fd0e635f175cc1c16834ed3006f18c.jpg)  
Fig.9: Similar as Fig. 6, but for the neutron resonant state $\nu 1 h _ { 9 / 2 }$ in $^ { 1 2 2 } \mathrm { Z r }$