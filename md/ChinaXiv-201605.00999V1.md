# Thermodynamic Properties of a Trapped Interacting Bose Gas

Hualin Shi and Wei-Mou Zheng Institute of Theoretical Physics, Academia Sinica, Beijing 10oo80, China (31Oct,1996)

# Abstract

A Bose gas in an external potential is studied by means of the local density approximation. Analytical results are derived for the thermodynamic properties of an ideal Bose gas in a generic power-law trapping potential, and their dependence on the mutual interaction of atoms in the case of a non-ideal Bose gas.

PACS numbers: 03.75.Fi, 32.80.Pj

One of the most striking consequences of quantum statistics is the condensation of an ideal Bose-Einstein gas where the zero momentum state can become macroscopically occupied at a suffciently low temperature [1]. Some of the features of the transition to a superfluid phase exhibited by the Bose fluid $^ 4$ He is often interpreted essentially as a result of this Bose-Einstein condensation (BEC), the strongest degeneracy effect of a Boson system [2]. For many years, it was considered hopeless to experimentally observe BEC in an atomic gas with weak interactions. With the development of techniques to trap and cool atoms, BEC was recently observed directly in dilute atomic vapors [3-5]. The new experimental achievements have stimulated great interest in the theoretical study of inhomogeneous Bose gases.

The thermodynamic properties of trapped atomic Bose gases undergoing BEC can be altered by the spatially varying trapping potential. The interaction between atoms may have a significant efect on the thermodynamic properties. There have been several investigations analyzing the dependence of the critical temperature on the trapping potential and weak interaction in the Bose gas [6-8]. The thermodynamic properties of Bose gases in an external potential have also been discussed in Ref.[6], but no analytic results have been given. Here we shall derive some analytical expressions for the thermodynamic properties of a trapped non-interacting and interacting Bose gas under the local density approximation.

Let us first consider the case of an ideal Bose gas trapped in an external potential. When the energy level spacing due to the trapping potential is much smaller than the thermal energy $k T = \beta ^ { - 1 }$ , the local density approximation is adequate [9-11]. Space may then be divided into small cells,and in each cell we may consider the trapping potential $V ( \mathbf { r } )$ to be constant. With a trivial modification to indicate $r$ dependence explicitly we may directly extend the formula of the grand potential, which can be found in any textbook on statistical mechanics, e.g. Ref.[1], to write the local grand potential above the critical temperature $T _ { c }$ as

$$
\widetilde \Omega _ { B E } ( \mathbf r ) = - \frac { k T } { \lambda ^ { 3 } } g _ { 5 / 2 } ( \zeta )
$$

where $\mu$ is the chemical potential, the thermal wave length $\lambda = \left( 2 \pi \hbar ^ { 2 } / m k T \right) ^ { \frac { 1 } { 2 } }$ ，and

$$
\zeta = \exp [ - \beta ( V ( { \bf r } ) - \mu ) ] , \qquad g _ { \nu } ( x ) = \sum _ { j = 1 } ^ { \infty } j ^ { - \nu } x ^ { j } .
$$

From this grand potential the local density of the Bose gas in the external potential is

$$
\rho ( T , \mathbf { r } ) = - \left( \frac { \partial \widetilde { \Omega } _ { B E } ( \mathbf { r } ) } { \partial \mu } \right) _ { T } = \frac { 1 } { \lambda ^ { 3 } } g _ { 3 / 2 } ( \zeta ) .
$$

This is the same as [11]. For the generic power-law potential discussed in Ref. [6]

$$
V ( { \bf r } ) = \epsilon _ { 1 } \left| \frac { x } { L _ { 1 } } \right| ^ { p } + \epsilon _ { 2 } \left| \frac { y } { L _ { 2 } } \right| ^ { l } + \epsilon _ { 3 } \left| \frac { z } { L _ { 3 } } \right| ^ { q } ,
$$

where $L _ { 1 }$ ， $L _ { 2 }$ and $L _ { 3 }$ are the linear sizes of the volume，and $\varepsilon _ { 1 }$ ， $\varepsilon _ { 2 }$ ， $\varepsilon _ { 3 }$ ，p， $l$ and $q$ the parameters, integrating the local grand potential (1） over the whole volume,we find the total grand potential of the system to be

$$
\begin{array} { r } { \Omega _ { B E } ( T , \mu ) = - k T \lambda ^ { - 3 } \int g _ { 5 / 2 } ( \zeta ) d \mathbf { r } } \\ { = - \frac { W } { \lambda ^ { 3 } \beta ^ { \eta + 1 / 2 } } g _ { \eta + 2 } ( z ) , } \end{array}
$$

where $z = e ^ { \beta \mu }$ ， $\eta = 1 / p + 1 / l + 1 / q + 1 / 2$ ，and

$$
\begin{array} { r } { W = \frac { 8 L _ { 1 } L _ { 2 } L _ { 3 } I ( p , l , q ) } { \varepsilon _ { 1 } ^ { 1 / p } \varepsilon _ { 2 } ^ { 1 / l } \varepsilon _ { 3 } ^ { 1 / q } } , I ( p , l , q ) = ( p l q ) ^ { - 1 } \Gamma ( 1 / p ) \Gamma ( 1 / l ) \Gamma ( 1 / q ) . } \end{array}
$$

In the derivation we have used the definition of the function $g _ { \nu } ( x )$ and the formula for the gamma function

$$
\Gamma ( z ) = \int _ { 0 } ^ { \infty } t ^ { z - 1 } e ^ { - t } \ : d t .
$$

From the total grand thermodynamic potential the average atom number can be obtained as

$$
\begin{array} { l } { \displaystyle \langle N \rangle = - \left( \frac { \partial \Omega _ { B E } } { \partial \mu } \right) _ { T } } \\ { \displaystyle = \frac { W } { \lambda ^ { 3 } \beta ^ { \eta - 1 / 2 } } z \frac { \partial } { \partial z } g _ { \eta + 2 } ( z ) } \\ { \displaystyle = \frac { W } { \lambda ^ { 3 } \beta ^ { \eta - 1 / 2 } } g _ { \eta + 1 } ( z ) . } \end{array}
$$

This is in agreement with the result in Ref. [8] obtained directly from the local density $\rho ( r )$ instead of the grand partition function.

The total entropy can be obtained as

$$
\begin{array} { l } { \displaystyle \langle S \rangle = - \left( \frac { \partial \Omega _ { B E } } { \partial T } \right) _ { \mu } } \\ { \displaystyle = \frac { W k } { \lambda ^ { 3 } \beta ^ { \eta - 1 / 2 } } \left[ ( \eta + 2 ) g _ { \eta + 2 } ( z ) - \beta \mu g _ { \eta + 1 } ( z ) \right] . } \end{array}
$$

Although, for obvious reasons, the volume and pressure are not useful thermodynamic variables for a trapped gas [6],we may still consider an analogue to the capacity for the homogeneous system at constant volume with a fixed number of atoms,and define this heat capacity as

$$
C ( T ) = T \left( { \frac { \partial S } { \partial T } } \right) _ { N } ,
$$

which includes the work done against the potential as the energy of the gas is changed.

So far we have discussed the case for a temperature above $T _ { c }$ . When the temperature $T$ is below the BEC critical temperature $T _ { c }$ , the chemical potential $\mu = 0$ , and only the normal component of the Bose gas has a contribution to the heat capacity. From Eqs. (9) and (10) we can then obtain the heat capacity ( $T < T _ { c }$ ）tobe:

$$
\begin{array} { l } { { \displaystyle C _ { - } ( T ) = \frac { ( \eta + 1 ) ( \eta + 2 ) W k } { \lambda ^ { 3 } \beta ^ { \eta - 1 / 2 } } g _ { \eta + 2 } ( 1 ) } } \\ { { \displaystyle \quad = \frac { ( \eta + 1 ) ( \eta + 2 ) g _ { \eta + 2 } ( 1 ) } { g _ { \eta + 1 } ( 1 ) } \left( \frac { T } { T _ { c } } \right) ^ { \eta + 1 } \langle N \rangle k . } } \end{array}
$$

As a limit,at the critical temperature $T _ { c }$ ， the above expression reduces to

$$
C ( T _ { c } ^ { - } ) = \frac { ( \eta + 1 ) ( \eta + 2 ) ~ g _ { \eta + 2 } ( 1 ) } { g _ { \eta + 1 } ( 1 ) } \langle N \rangle k .
$$

When the temperature $T$ is above the critical temperature $T _ { c }$ , at a fixed $N$ the chemical potential $\mu$ is a function of temperature $T$ . In order to obtain the heat capacity, we have to calculate the derivative of $\mu$ with respect to temperature $T$ while holding $N$ fixed. Using

$$
\frac { \partial \langle N \rangle } { \partial T } = 0 ,
$$

from Eq. (8) we find

$$
( \eta + 1 ) g _ { \eta + 1 } ( z ) + \left[ \frac { 1 } { k } \left( \frac { \partial \mu } { \partial T } \right) _ { \langle N \rangle } - \beta \mu \right] g _ { \eta } ( z ) = 0 ,
$$

which yields

$$
\left( \frac { \partial \mu } { \partial T } \right) _ { \langle N \rangle } = \frac { \mu } { T } - \frac { k ( \eta + 1 ) g _ { \eta + 1 } ( z ) } { g _ { \eta } ( z ) } .
$$

From Eqs. (1O) and (15) the heat capacity above $T _ { c }$ is then given by

$$
\begin{array} { l } { { C _ { + } ( T ) = \displaystyle \frac { W k } { \lambda ^ { 3 } \beta ^ { \eta - 1 / 2 } } \left[ ( \eta + 1 ) ( \eta + 2 ) g _ { \eta + 2 } ( z ) - ( \eta + 1 ) ^ { 2 } g _ { \eta + 1 } ^ { 2 } ( z ) / g _ { \eta } ( z ) \right] } } \\ { { \displaystyle \quad \quad = \left[ ( \eta + 1 ) ( \eta + 2 ) \frac { g _ { \eta + 2 } ( z ) } { g _ { \eta + 1 } ( z ) } - ( \eta + 1 ) ^ { 2 } \frac { g _ { \eta + 1 } ( z ) } { g _ { \eta } ( z ) } \right] \langle N \rangle k . } } \end{array}
$$

At $T = T _ { c } ^ { + }$ , the chemical potential $\mu = 0$ ， so the above expression reduces to

$$
C ( T _ { c } ^ { + } ) = \left[ ( \eta + 1 ) ( \eta + 2 ) \frac { g _ { \eta + 2 } ( 1 ) } { g _ { \eta + 1 } ( 1 ) } - ( \eta + 1 ) ^ { 2 } \frac { g _ { \eta + 1 } ( 1 ) } { g _ { \eta } ( 1 ) } \right] \langle N \rangle k .
$$

By comparing with Eq. (12), the discontinuity of heat capacity at the critical point is

$$
\Delta C = C ( T _ { c } ^ { - } ) - C ( T _ { c } ^ { + } ) = \frac { ( \eta + 1 ) ^ { 2 } g _ { \eta + 1 } ( 1 ) } { g _ { \eta } ( 1 ) } \langle N \rangle k .
$$

From the Eqs. (11),(17) and (18), we see that the heat capacity depends only on the particle number and the exponents $p$ ， $l$ and $q$ of the external potential. We can further examine the continuity of $C ( T )$ and its derivatives. As we know, $g _ { \eta } ( 1 )$ is divergent for $\eta \leq 1$ . So, the heat capacity becomes discontinuous at the critical temperature $T _ { c }$ when $\eta > 1$ . From Eqs. (11) and (16)， the derivative $\partial C ( T ) / \partial T$ is discontinuous at $T _ { c }$ for either $\eta \leq 1$ or $\eta > 1$ . This is in agreement with Ref. [6]. From the analytical expressions we also see that the heat capacity at the critical point grows with increasing $\eta$

For a rigid wall box, $\eta = 1 / 2$ . It is straightforward to check that the above expressions indeed reduce to the known results in textbooks of statistical mechanics (e.g. Ref. [1]). As a special case let us consider the harmonic potential

$$
V ( \mathbf { r } ) = \frac { 1 } { 2 } m \omega _ { \bot } ^ { 2 } r _ { \bot } ^ { 2 } + \frac { 1 } { 2 } m \omega _ { z } ^ { 2 } r _ { z } ^ { 2 } .
$$

We find the heat capacity $C ( T _ { c } ^ { + } )$ ， $C ( T _ { c } ^ { - } )$ and $\Delta C$ to be

$$
\begin{array} { r l r } {  { C ( T _ { c } ^ { - } ) = \frac { 1 2 g _ { 4 } ( 1 ) } { g _ { 3 } ( 1 ) } \langle N \rangle k , } } \\ & { } & { C ( T _ { c } ^ { + } ) = [ \frac { 1 2 g _ { 4 } ( 1 ) } { g _ { 3 } ( 1 ) } - \frac { 9 g _ { 3 } ( 1 ) } { g _ { 2 } ( 1 ) } ] \langle N \rangle k , } \\ & { } & { \Delta C = \frac { 9 g _ { 3 } ( 1 ) } { g _ { 2 } ( 1 ) } \langle N \rangle k . } \end{array}
$$

This agrees with Refs. [12,6]

Along similar lines we may analyze the thermodynamic properties of a trapped interacting Bose gas. In the mean field approximation, the single particle effective potential can be written as:

$$
V _ { e f f } ( \mathbf { r } ) = V ( \mathbf { r } ) + 2 a \lambda ^ { 2 } \rho ( \mathbf { r } ) ,
$$

where $a$ is the $s$ -wave scattering length，which characterizes the strength of interaction between two atoms. We assume $| a | \ll \lambda$ for the weak interaction considered here. By similarity with Eq. (1), for the trapped interacting Bose gas the local grand potential can be written as

$$
\widetilde \Omega _ { B E } ^ { I } ( \mathbf { r } ) = - k T \lambda ^ { - 3 } \ g _ { 5 / 2 } ( \boldsymbol { \xi } ) ,
$$

where

$$
\xi = \exp [ - \beta ( V ( \mathbf { r } ) + 2 a \lambda ^ { 2 } \rho ( \mathbf { r } ) - \mu ) ] .
$$

Expanding the function $g _ { 5 / 2 } ( \xi )$ in Eq. (24) according to the small parameter $a / \lambda$ , and keeping terms only up to the lowest order in $a / \lambda$ ，we have

$$
\begin{array} { l } { { \widetilde \Omega } _ { B E } ^ { I } ( { \bf r } ) \simeq - k T \lambda ^ { - 3 } \left[ g _ { 5 / 2 } ( \zeta ) - 2 a \lambda ^ { 2 } \rho ( { \bf r } ) g _ { 3 / 2 } ( \zeta ) \right] } \\ { \simeq - k T \lambda ^ { - 3 } \left[ g _ { 5 / 2 } ( \zeta ) - 2 a \lambda ^ { - 1 } g _ { 3 / 2 } ^ { 2 } ( \zeta ) \right] , } \end{array}
$$

which coincides with the first order result of the virial expansion of the grand partition function [13]. This is not surprising since the mean field approximation is accurate to the first order. From the grand potential we can obtain the local density

$$
\begin{array} { l } { \displaystyle { \rho ^ { I } ( { \bf r } ) = - \left( \frac { \partial } { \partial \mu } { \tilde { \Omega } } _ { B E } ^ { I } ( { \bf r } ) \right) _ { T } } } \\ { \displaystyle = \lambda ^ { - 3 } \left[ g _ { 3 / 2 } ( \zeta ) - 4 a \lambda ^ { - 1 } g _ { 1 / 2 } ( \zeta ) g _ { 3 / 2 } ( \zeta ) \right] } \\ { \displaystyle \simeq \lambda ^ { - 3 } g _ { 3 / 2 } ( \exp [ - \beta ( V ( { \bf r } ) + 4 a \lambda ^ { 2 } \rho ( { \bf r } ) - \mu ) ] ) , } \end{array}
$$

which，compared with the density of an ideal Bose gas,means the effective fugacity is $\exp [ - \beta ( V ( \mathbf { r } ) + 4 a \lambda ^ { 2 } \rho ( \mathbf { r } ) - \mu ) ]$ . However, from a naive consideration based on the effective interaction one would think that it should be $\exp [ - \beta ( V ( \mathbf { r } ) + 2 a \lambda ^ { 2 } \rho ( \mathbf { r } ) - \mu ) ]$ instead.The factor two in the atomic density expression naturally appears by taking the derivative of the grand potential with respect to $\mu$

As the counterpart to Eq. (5),we can find the total grand potential for the interacting gas at $T > T _ { c }$ to be

$$
\Omega _ { B E } ^ { I } = - { \frac { W } { \lambda ^ { 3 } \beta ^ { \eta + 1 / 2 } } } \left[ g _ { \eta + 2 } ( z ) - 2 a \lambda ^ { - 1 } F _ { 3 / 2 , 3 / 2 , \eta } ( z ) \right] ,
$$

where

$$
F _ { \delta , \nu , \eta } ( x ) = \sum _ { i , j = 1 } ^ { \infty } \frac { x ^ { i + j } } { i ^ { \delta } j ^ { \nu } ( i + j ) ^ { \eta - 1 / 2 } } .
$$

When $a = 0$ , Eq. (28) recovers expression (5) for the non-interacting Bose gas,as it should. The average number of atoms is now given by

$$
\begin{array} { l } { { \displaystyle \langle N ^ { I } \rangle = - \left( \frac { \partial \Omega _ { B E } ^ { I } } { \partial \mu } \right) _ { T } } } \\ { { \displaystyle ~ = \frac { W } { \lambda ^ { 3 } \beta ^ { \eta - 1 / 2 } } \left[ g _ { \eta + 1 } ( z ) - 2 a \lambda ^ { - 1 } F _ { 3 / 2 , 3 / 2 , \eta - 1 } ( z ) \right] , } } \end{array}
$$

where we haveused

$$
\frac { \partial F _ { \delta , \nu , \eta } ( x ) } { \partial x } = \frac { 1 } { x } F _ { \delta , \nu , \eta - 1 } ( x ) .
$$

As we know, $g _ { \eta + 1 } ( z )$ is a bounded， positive, monotonically increasing function of $z$ ，and （204号 $F _ { \delta , \nu , \eta } ( x )$ is positive. From Eq. (3O) we see that the trapped interacting Bose gas has a higher chemical potential than an ideal Bose gas when the atomic number and temperature are the same in both systems.

From Eq. (30) for $\langle N ^ { I } \rangle$ we can calculate the derivative $\partial \mu / \partial T$ at a fixed $N ^ { I }$ ，and the result is

$$
\begin{array} { l } { { { \displaystyle ( \frac { \partial \mu } { \partial T } ) _ { \{ N ^ { I } \} } _ { \{ N ^ { I } \} } = \frac { \mu } { T } - \frac { ( \eta + 1 ) g _ { \eta + 1 } ( z ) - 2 a \lambda ^ { - 1 } ( \eta + 3 / 2 ) F _ { 3 / 2 , 3 / 2 , \eta - 1 } ( z ) } { g _ { \eta } ( z ) - 2 a \lambda ^ { - 1 } F _ { 3 / 2 , 3 / 2 , \eta - 2 } ( z ) } k } } } \\ { { { \displaystyle \qquad \simeq \frac { \mu } { T } - \{ \frac { ( \eta + 1 ) g _ { \eta + 1 } ( z ) } { g _ { \eta } ( z ) } + \frac { 2 a } { \lambda } [ \frac { ( \eta + 1 ) g _ { \eta + 1 } ( z ) F _ { 3 / 2 , 3 / 2 , \eta - 2 } ( z ) } { g _ { \eta } ^ { 2 } ( z ) }   } } } \\ { { { \displaystyle \qquad - \frac { ( \eta + 3 / 2 ) F _ { 3 / 2 , 3 / 2 , \eta - 1 } ( z ) } { g _ { \eta } ( z ) } ] \} k . } } } \end{array}
$$

Corresponding to Eq. (9), the total entropy of the trapped interacting Bose gas can then be derived as

$$
\begin{array} { l } { { \displaystyle \langle S ^ { I } \rangle = - \left( \frac { \partial \Omega _ { B E } ^ { I } } { \partial T } \right) _ { \mu } } } \\ { { \displaystyle \quad = \frac { W k } { \lambda ^ { 3 } \beta ^ { \eta - 1 / 2 } } \left[ ( \eta + 2 ) g _ { \eta + 2 } ( z ) - \beta \mu g _ { \eta + 1 } ( z ) \right] } } \\ { { \displaystyle \qquad - \frac { 2 a W k } { \lambda ^ { 4 } \beta ^ { \eta - 1 / 2 } } \left[ ( \eta + 5 / 2 ) F _ { 3 / 2 , 3 / 2 , \eta } ( z ) - \beta \mu F _ { 3 / 2 , 3 / 2 , \eta - 1 } ( z ) \right] . } } \end{array}
$$

Calculating the derivative of the entropy $\langle S ^ { I } \rangle$ ， we obtain the heat capacity above the BEC critical temperature to be

$$
\begin{array} { l } { \displaystyle { \mathrm {  ~ \Lambda ~ } ^ { \prime } ) = T \left( \frac { \partial S ^ { I } } { \partial T } \right) _ { N ^ { I } } } } \\ { = \displaystyle { \left[ ( \eta + 1 ) ( \eta + 2 ) \frac { g _ { \eta + 2 } ( z ) } { g _ { \eta + 1 } ( z ) } - ( \eta + 1 ) ^ { 2 } \frac { g _ { \eta + 1 } ( z ) } { g _ { \eta } ( z ) } \right] \langle N \rangle k - \frac { 2 a } { \lambda } \left[ \frac { ( \eta + 3 / 2 ) ( \eta + 5 / 2 ) b } { g _ { \eta + 1 } ( z ) } \right] \langle J \rangle ^ { 2 } } } \\ { + ( \eta + 1 ) \left( \frac { ( \eta + 1 ) g _ { \eta + 1 } ( z ) F _ { 3 / 2 , 3 / 2 , \eta - 2 } ( z ) } { g _ { \eta } ^ { 2 } ( z ) } - \frac { 2 ( \eta + 3 / 2 ) F _ { 3 / 2 , 3 / 2 , \eta - 1 } ( z ) } { g _ { \eta } ( z ) } \right) \Bigg ] \langle J \rangle ^ { 2 } , }  \end{array}
$$

The last two formulas show the correction due to the mutual interaction of atoms to thermodynamic quantities such as the entropy and heat capacity.

The above derivations for the trapped interacting Bose gas is adequate only for the gas phase (without BEC),and furnish no information whatsoever about the condensed phase, or the nature of the condensation [13]. Any attempts to use the same equations in the regime of BEC will lead to some mistakes. According to Ref.[13] the mean field effective potential should be amended to include the contributions of atoms to Bose condensation. If we choose an appropriate efective mean field potential similar to Eq. (28) of Ref. [13], we can， in principle, extend the above discussion to calculate thermodynamic quantities below the critical temperature. However,the derivation will be so involved that no simple analytical formulas can be expected to exist any more.

# ACKNOWLEDGMENTS

The authors thank Hao Bai-lin for his encouragement and useful discussions. This work was supported in part by the National Natural Science Foundation of China.

# REFERENCES

[1] Kerson Huang, Statistical Mechanics,( Wiley, New York, 1987), 2nd ed .   
[2] O. Penrose and L. Onsager, Phys. Rev. 104, 576 (1956).   
[3] M.H. Anderson, J.R. Ensher, M.R. Matthews, C.E. Wieman, and E.A. Cornell, Science 269, 198 (1995).   
[4] C.C. Bradley， C.A. Sackett， J.J. Tollett，and R.G. Hulet， Phys. Reu. Let 75，1687 (1995).   
[5] K.B. Davis, M.-O. Mewes, M.R. Andrew, N.J. van Druten, D.S. Durfee, D.M. Kurn, and W. Ketterle, Phys. Rev. Lett. 75, 3969 (1995). [6] Vanderlei Bagnato,David E. Pritchard, and Daniel Kleppner， Phys. Rev.A35,4354 (1987).   
[7] S. Giorgini, L. Pitaevskii, and S. Stringari, Phys. Rev. A54, No.6 (1996).   
[8] Hualin Shi, Wei-mou Zheng, cond-mat/9609241 .   
[9] V.V. Goldman, I.F. Silvera, and A.J. Legget, Phys. Rev. B24, 2870 (1981).   
[10] J. Oliva, Phys. Rev. B39, 4197 (1989).   
[11] T.T. Chou, C.N. Yang, and L.W. Yu, Phys. Rev. A53, 4257 (1996).   
[12] S.R. de Groot, G.J. Hooyman and C.A. ten Seldam, Proc. R. Soc. London A203, 266 (1950).   
[13] Kerson Huang and C.N. Yang, Phys. Rev. 105, 776 (1957).