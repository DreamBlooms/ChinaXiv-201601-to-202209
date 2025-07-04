# Critical Temperature of a Trapped Interacting Bose Gas in the Local Density Approximation

Hualin Shi and Wei-Mou Zheng Institute of Theoretical Physics, Academia Sinica, Beijing 10oo80, China

# Abstract

The Bose gas in an external potential is studied by means of the local density approximation. An analytical result is derived for the dependence of the critical temperature of Bose-Einstein condensation on the mutual interaction in a generic power-law potential.

PACS numbers: 03.75.Fi, 32.80.Pj

In an ideal Bose-Einstein gas, the zero momentum state can become macroscopically occupied, and the system then undergoes a phase transition — the Bose-Einstein condensation (BEC) [1]. The $\lambda$ -transition of liquid helium-II is often interpreted essentially as a result of BEC, the strongest degeneracy effect of a Boson system[2]. For many years,it was considered hopeless to experimentally observe BEC in an atomic gas with weak interactions. With the development of techniques to trap and cool atoms, BEC was recently observed directly in dilute atomic vapors[3,4,5]. The new experimental achievements have stimulated great interest in the theoretical study of inhomogeneous Bose gases.

For BEC in the atom-trapping experiments, the critical temperature $T _ { c }$ can be altered by the spatially varying potential of trapping. Furthermore, the noninteracting Bose gas can lead to unphysical results. The interaction between atoms may have a significant efect on the critical temperature. There have been several investigations analyzing the dependence of the critical temperature on the trapping potential and weak interaction in the Bose gas[6,7]. Here we shall derive an analytical result for the critical temperature of a trapped interacting Bose gas by means of the local density approximation.

When the energy level spacing of the trapping potential is much smaller than $k T = \beta ^ { - 1 }$ ，the local density approximation [8, 9,10] is a good approximation. Space may then be divided into small cells,and in each cell we may consider the trapping potential energy $V ( \mathbf { r } )$ to be a constant. In this approximation for an ideal Bose gas, the local density $\rho ( \mathbf { r } )$ of particles in the gaseous phase (i.e.,without BEC) is

$$
\rho ( \mathbf { r } ) = \lambda ^ { - 3 } g _ { 3 / 2 } ( \xi ) ,
$$

where

$$
\lambda = \left( \frac { 2 \pi \hbar ^ { 2 } } { m k T } \right) ^ { 1 / 2 } ,
$$

$$
\xi = z \exp [ - \beta V ( { \bf r } ) ] , \qquad z = e ^ { \beta \mu } , \qquad g _ { \nu } ( x ) = \sum _ { j = 1 } ^ { \infty } j ^ { - \nu } x ^ { j } ,
$$

and $\mu$ is the chemical potential. Equivalently, the density of states at energy $\varepsilon$ is[6]

$$
\rho ( \varepsilon ) = \frac { 2 \pi ( 2 m ) ^ { 3 / 2 } } { h ^ { 3 } } \int \sqrt { \varepsilon - V ( { \bf r } ) } d ^ { 3 } r .
$$

We may now extend the argument of BEC for rigid wals[1] to the case of the spatially varying trapping potential $V ( \mathbf { r } )$ . From Eq. (1),the total number of particles can be written as

$$
N = N _ { 0 } + \int _ { V } \rho ( \mathbf { r } ) d ^ { 3 } r ,
$$

where $N _ { 0 }$ is the number of particles in the ground state. Let us consider a generic power-law potential as in Ref. [6]

$$
V ( { \bf r } ) = \epsilon _ { 1 } \left| \frac { x } { L _ { 1 } } \right| ^ { p } + \epsilon _ { 2 } \left| \frac { y } { L _ { 2 } } \right| ^ { l } + \epsilon _ { 3 } \left| \frac { z } { L _ { 3 } } \right| ^ { q } .
$$

Since $g _ { 3 / 2 } ( \xi )$ is a bounded, positive, monotonically increasing function of $\xi$ , for the potential (6), the integral in Eq. (5) reaches its maximum value at fugacity $z = 1$ or $\mu = 0$ .From Eqs. (3) and (5） the critical temperature $T _ { c }$ , at which the ground state begins to take on macroscopic values, is determined by

$$
\begin{array} { r c l } { { { \cal N } \lambda _ { c } ^ { 3 } } } & { { = } } & { { \displaystyle \int d { \bf r } g _ { 3 / 2 } [ \exp ( - \beta _ { c } V ( { \bf r } ) ) ] } } \\ { { } } & { { = } } & { { \displaystyle \sum _ { j = 1 } ^ { \infty } j ^ { - 3 / 2 } \int \exp ( - j \beta _ { c } V ( { \bf r } ) ) ~ d { \bf r } . } } \end{array}
$$

The definition of the Gamma function

$$
\Gamma ( z ) = \int _ { 0 } ^ { \infty } t ^ { z - 1 } e ^ { - t } d t
$$

implies

$$
\int _ { 0 } ^ { \infty } d x \exp ( - a x ^ { p } ) = \frac { a ^ { - 1 / p } } { p } \Gamma ( 1 / p ) .
$$

For the specific choice (6) of the potential, expression（7) then becomes

$$
\begin{array} { r c l } { { N \lambda _ { c } ^ { 3 } } } & { { = } } & { { \displaystyle \sum _ { j = 1 } ^ { \infty } \frac { 8 j ^ { - 3 / 2 } } { ( j \beta _ { c } ) ^ { \eta - 1 / 2 } } \frac { L _ { 1 } L _ { 2 } L _ { 3 } } { \epsilon _ { 1 } ^ { 1 / p } \epsilon _ { 2 } ^ { 1 / l } \epsilon _ { 3 } ^ { 1 / q } } \frac { \Gamma ( 1 / p ) \Gamma ( 1 / l ) \Gamma ( 1 / q ) } { p l q } } } \\ { { } } & { { = } } & { { 8 \zeta ( \eta + 1 ) \displaystyle \frac { L _ { 1 } L _ { 2 } L _ { 3 } I ( p , l , q ) } { \beta _ { c } ^ { \eta - 1 / 2 } \epsilon _ { 1 } ^ { 1 / p } \epsilon _ { 2 } ^ { 1 / l } \epsilon _ { 3 } ^ { 1 / q } } , } } \end{array}
$$

where

$$
I ( p , l , q ) = ( p l q ) ^ { - 1 } \Gamma ( 1 / p ) \Gamma ( 1 / l ) \Gamma ( 1 / q ) ,
$$

and $\begin{array} { r } { \zeta ( \nu ) = \sum _ { j = 1 } ^ { \infty } j ^ { - \nu } } \end{array}$ is the Riemann zeta function and $\eta = 1 / p + 1 / l + 1 / q + 1 / 2$ .Noticing the dependence (2） of the thermal wavelength $\lambda$ on the temperature,we finally obtain

$$
k T _ { c } = \left( \frac { N ( 2 \pi \hbar ^ { 2 } ) ^ { 3 / 2 } \epsilon _ { 1 } ^ { 1 / p } \epsilon _ { 2 } ^ { 1 / l } \epsilon _ { 3 } ^ { 1 / q } } { 8 m ^ { 3 / 2 } \zeta ( \eta + 1 ) L _ { 1 } L _ { 2 } L _ { 3 } I ( p , l , q ) } \right) ^ { 1 / ( \eta + 1 ) } .
$$

From Eqs.(5) and (1O) we can obtain the fraction of condensation at a temperature $T$ below $T _ { c }$ （20

$$
\frac { N _ { 0 } } { N } = 1 - \left( \frac { T } { T _ { c } } \right) ^ { \eta + 1 }
$$

where $N _ { 0 }$ is the number of Bose particles in the BEC state.

For the harmonic potential

$$
V ( \mathbf { r } ) = \frac { 1 } { 2 } m \omega _ { \bot } ^ { 2 } r _ { \bot } ^ { 2 } + \frac { 1 } { 2 } m \omega _ { z } ^ { 2 } r _ { z } ^ { 2 } ,
$$

the critical temperature and fraction of condensation reduce to

$$
k T _ { c } = \hbar \left( \frac { N \omega _ { \perp } ^ { 2 } \omega _ { z } } { 1 . 2 0 2 } \right) ^ { 1 / 3 } ,
$$

$$
\frac { N _ { 0 } } { N } = 1 - \left( \frac { T } { T _ { c } } \right) ^ { 3 } .
$$

where we have madeuse of

$$
\zeta ( 3 ) = 1 . 2 0 2 , \qquad I ( 2 , 2 , 2 ) = \pi ^ { 3 / 2 } / 8 .
$$

The results (15）and (16) were first obtained in Ref. [11] and have been verified in a recent experiment[12].

Relation (12) for the generic power-law potential may also be derived in terms of Eq. (4). In Ref.[6] it is given that

$$
k T _ { c } = \left[ \frac { h ^ { 3 } } { 2 \pi ( 2 m ) ^ { 3 / 2 } } \frac { N } { L _ { 1 } L _ { 2 } L _ { 3 } } \frac { \epsilon _ { 1 } ^ { 1 / p } \epsilon _ { 2 } ^ { 1 / l } \epsilon _ { 3 } ^ { 1 / q } } { F ( p , l , q ) Q ( \eta ) } \right] ^ { 1 / ( \eta + 1 ) }
$$

where

$$
Q ( \eta ) = \int _ { 0 } ^ { \infty } \frac { \theta ^ { \eta } } { \exp ( \theta ) - 1 } d \theta ,
$$

$$
( p , l , q ) = 8 \left[ \int _ { 0 } ^ { 1 } d x ( 1 - x ^ { p } ) ^ { 1 / 2 + 1 / q + 1 / l } \right] \left[ \int _ { 0 } ^ { 1 } d x ( 1 - x ^ { l } ) ^ { 1 / q + 1 / 2 } \right] \left[ \int _ { 0 } ^ { 1 } d x ( 1 - x ^ { q } ) ^ { 1 / 2 } \right] .
$$

In fact, we may integrate both $Q$ and $F$ to obtain

$$
Q ( \eta ) = \sum _ { j = 1 } ^ { \infty } \int _ { 0 } ^ { \infty } \theta ^ { \eta } e ^ { - j \theta } d \theta = \zeta ( \eta + 1 ) \Gamma ( \eta + 1 ) ,
$$

$$
F ( p , l , q ) = 4 \sqrt { \pi } I ( p , l , q ) / \Gamma ( \eta + 1 ) ,
$$

where in deriving the last equation we have used

$$
\int _ { 0 } ^ { 1 } ( 1 - x ^ { p } ) ^ { \nu - 1 } d x = { \frac { 1 } { p } } \int _ { 0 } ^ { 1 } ( 1 - t ) ^ { \nu - 1 } t ^ { { \frac { 1 } { p } } - 1 } d t = { \frac { 1 } { p } } B ( 1 / p , \nu ) = { \frac { \Gamma ( \nu ) \Gamma ( 1 / p ) } { p \Gamma ( \nu + 1 / p ) } } .
$$

It can then be verified that Eq.(18) coincides with (12) as it should.

Along similar lines we may analyze the critical temperature of a trapped interacting Bose gas. In Ref.[1O] it has been given that when the $s$ -wave scattering length $| a | \ll \lambda$ , in the local density approximation the local density of the gaseous phase as given in Eq. (1) is replaced by

$$
\rho ( \mathbf { r } ) = \lambda ^ { - 3 } g _ { 3 / 2 } ( \tilde { \xi } ) ,
$$

with

$$
\widetilde \xi = z \exp [ - \beta V ( \mathbf r ) - 4 a \lambda ^ { 2 } \rho ( \mathbf r ) ] ,
$$

where the term containing the scattering length $a$ describes the mutual interaction of atoms. From Eqs.(24) and(25) we have

$$
\rho ( 0 ) = \lambda ^ { - 3 } g _ { 3 / 2 } [ z \exp ( - 4 a \lambda ^ { 2 } \rho ( 0 ) ] .
$$

Thus,at the critical temperature the fugacity is

$$
z _ { c } = \exp [ 4 a \tilde { \lambda } _ { c } ^ { 2 } \rho _ { c } ( 0 ) ]
$$

where

$$
\rho _ { c } ( 0 ) = \tilde { \lambda } _ { c } ^ { - 3 } g _ { 3 / 2 } ( 1 ) .
$$

For this $z _ { c }$ Eq.(24) becomes

$$
\begin{array} { r c l } { \rho ( { \bf r } ) \tilde { \lambda } _ { c } ^ { 3 } } & { = } & { g _ { 3 / 2 } [ z _ { c } \exp ( - \tilde { \beta } _ { c } V ( { \bf r } ) - 4 a \tilde { \lambda } _ { c } ^ { 2 } \rho ( { \bf r } ) ) ] } \\ & { \approx } & { g _ { 3 / 2 } [ \exp ( - \tilde { \beta } _ { c } V ( { \bf r } ) ) ] + 4 a \tilde { \lambda } _ { c } ^ { 2 } [ \rho _ { c } ( 0 ) - \rho ( { \bf r } ) ] g _ { 1 / 2 } [ \exp ( - \tilde { \beta } _ { c } V ( { \bf r } ) ) ] } \\ & { \approx } & { g _ { 3 / 2 } [ \exp ( - \tilde { \beta } _ { c } V ( { \bf r } ) ) ] + 4 a \tilde { \lambda } _ { c } ^ { 2 } \rho _ { c } ( 0 ) g _ { 1 / 2 } [ \exp ( - \tilde { \beta } _ { c } V ( { \bf r } ) ) ] } \\ & & { \quad - 4 a \tilde { \lambda } _ { c } ^ { - 1 } g _ { 3 / 2 } [ \exp ( - \tilde { \beta } _ { c } V ( { \bf r } ) ) ] g _ { 1 / 2 } [ \exp ( - \tilde { \beta } _ { c } V ( { \bf r } ) ) ] , } \end{array}
$$

where we have used

$$
z { \frac { d } { d z } } g _ { 3 / 2 } ( z ) = g _ { 1 / 2 } ( z ) ,
$$

and kept only the lowest order in $a / \lambda$ . The determination of critical temperature $\ddot { T } _ { c }$ for the interacting Bose gas involves integration of $\rho ( \mathbf { r } )$ in (29). After some calculations similar to those in the derivation of (1O) from(7)，we find

$$
N \tilde { \lambda } _ { c } ^ { 3 } = 8 \left[ \zeta ( \eta + 1 ) + 4 a \tilde { \lambda } _ { c } ^ { - 1 } \left( \zeta ( 3 / 2 ) \zeta ( \eta ) - \chi ( \eta - 1 / 2 ) \right) \right] \frac { L _ { 1 } L _ { 2 } L _ { 3 } I ( p , l , q ) } { \beta _ { c } ^ { \eta - 1 / 2 } \epsilon _ { 1 } ^ { 1 / p } \epsilon _ { 2 } ^ { 1 / l } \epsilon _ { 3 } ^ { 1 / q } } ,
$$

where

$$
\chi ( \nu ) = \sum _ { i , j = 1 } ^ { \infty } \frac { 1 } { i ^ { 3 / 2 } j ^ { 1 / 2 } } \frac { 1 } { ( i + j ) ^ { \nu } } .
$$

We finally obtain the critical temperature $\tilde { T } _ { c }$

$$
\begin{array} { r } { \boldsymbol { \mathfrak { t } } \tilde { T } _ { c } = \left( \frac { N \ ( 2 \pi \hbar ^ { 2 } ) ^ { 3 / 2 } \ \epsilon _ { 1 } ^ { 1 / p } \epsilon _ { 2 } ^ { 1 / l } \epsilon _ { 3 } ^ { 1 / q } } { 8 \ m ^ { 3 / 2 } \ \left[ \zeta ( \eta + 1 ) + 4 a \tilde { \lambda } _ { c } ^ { - 1 } \ \left( \ \zeta ( 3 / 2 ) \zeta ( \eta ) - \chi ( \eta - 1 / 2 ) \ \right) \ \right] \ L _ { 1 } L _ { 2 } L _ { 3 } \ I ( p , l , q ) } \right) ^ { 1 ( \eta - 1 / 2 ) } \mathrm { ~ a ~ n ~ d ~ } \bigl ( \eta \bigr ) , } \end{array}
$$

Comparing Eq. (33) with Eq. (12) for the critical temperature $T _ { c }$ of the trapped ideal Bose gas, we can derive the relation between the critical temperatures of BEC for ideal and nonideal Bose gases in the power-law potential

$$
\frac { T _ { c } } { \tilde { T } _ { c } } = \left[ 1 + 4 a \tilde { \lambda } _ { c } ^ { - 1 } \frac { \zeta ( 3 / 2 ) \zeta ( \eta ) - \chi ( \eta - 1 / 2 ) } { \zeta ( \eta + 1 ) } \right] ^ { 1 / ( \eta + 1 ) } ,
$$

whichleads to

$$
\tilde { T } _ { c } = T _ { c } - \frac { \zeta ( 3 / 2 ) \zeta ( \eta ) - \chi ( \eta - 1 / 2 ) } { ( \eta + 1 ) \zeta ( \eta + 1 ) } \left( \frac { 8 k m { T _ { c } } ^ { 3 } } { \pi { \hbar } ^ { 2 } } \right) ^ { 1 / 2 } a .
$$

From this analytical relation between the critical temperature and the scattering length $a$ ，we see that the critical temperature $\ddot { T } _ { c }$ decreases for $a > 0$ ， and increases for $a < 0$ , compared with $T _ { c }$ of the ideal Bose gas. This agrees with Ref. [6].

We may also obtain an expression similar to the case of an ideal Bose gas for the condensate fraction at a temperature $T < \tilde { T _ { c } }$ to be

$$
\frac { { \cal N } _ { 0 } } { N } = 1 - \left( \frac { T } { \tilde { T } _ { c } } \right) ^ { \eta + 1 } + 4 \frac { a } { \tilde { \lambda } _ { c } } \frac { \zeta ( 3 / 2 ) \zeta ( \eta ) - \chi ( \eta - 1 / 2 ) } { \zeta ( \eta + 1 ) } \left( \frac { T } { \tilde { T } _ { c } } \right) ^ { \eta + 1 } \left[ 1 - \left( \frac { T } { \tilde { T } _ { c } } \right) ^ { 1 / 2 } \right]
$$

For the harmonic potential (14), Eq. (36) reduces to

$$
\tilde { T } _ { c } = T _ { c } - \frac { \zeta ( 3 / 2 ) \zeta ( 2 ) - \chi ( 2 / 3 ) } { 3 \zeta ( 3 ) } \left( \frac { 8 k m T _ { c } ^ { 3 } } { \pi \hbar ^ { 2 } } \right) ^ { 1 / 2 } a ,
$$

which has been obtained in Ref. [7].

The main effect of an external potential is to concentrate Bose particles. A repulsive mutual interaction between particles will weaken the efect of the external potential in concentrating particles around the center of the potential, hence lower the critical temperature.

The authors thank Prof. Bai-lin Hao for encouraging and useful discussions. This work was supported in part by the National Natural Science Foundation of China.

# References

[1] Kerson Huang, Statistical Mechanics, (Wiley, New York, 1987)， 2nd ed .   
[2] O. Penrose and L. Onsager, Phys. Rev. 104, 576 (1956).   
[3] M.H. Anderson, J.R. Ensher, M.R. Matthews, C.E. Wieman, and E.A. Cornell Science 269, 198 (1995).   
[4] C.C. Bradley, C.A. Sackett, J.J. Tollett, and R.G. Hulet,Phys. Rev. Lett.75,1687 (1995).   
[5] K.B. Davis, M.-O. Mewes, M.R. Andrew, N.J. van Druten, D.S. Durfee, D.M. Kurn, and W. Ketterle, Phys.Rev. Lett. 75,3969 (1995).   
[6] Vanderlei Bagnato, David E. Pritchard, and Daniel Kleppner, Phys. Rev. A35, 4354 (1987). [7] S. Giorgini, L. Pitaevskii, and S. Stringari, Preprint: cond-mat/9607117 .   
[8] V.V. Goldman, I.F. Silvera, and A.J. Legget, Phys. Rev. B24, 2870 (1981).   
[9] J. Oliva, Phys. Rev. B39, 4197 (1989).   
[10] T.T. Chou, C.N. Yang, and L.W. Yu, Phys. Rev. A53, 4257 (1996).   
[11] S.R. de Groot, G.J. Hooyman and C.A. ten Seldam, Proc. R. Soc. London A203, 266 (1950).   
[12] M.-O. Mewes, M.R. Andrews, N.J. van Druten, D.M. Kurn, D.S. Durfee, and W. Ketterle, Phys. Rev. Lett. 77, 416 (1996).