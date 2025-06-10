# Explicit Equations to Transform from Cartesian to Elliptic Coordinates

# Che Sun

Institute of Oceanology, Chinese Academy of Sciences, Qingdao, China

Email address: csun@qdio.ac.cn

To cite this article:   
CheSun.ExplicitEquationstoTransform from Cartesian toEliptic Coordinates.MathematicalModelingand Applications. Vol.2,No.4,2017, pp.43-46.doi: 10.11648/j.mma.20170204.12

Received: January 16,2017; Accepted: January 25,2017; Published: October 31,2017

Abstract: Explicitequations areobtained toconvert Cartesiancoodinates toelipticcoordinates,basedon whichafunctionin elipticoordinatescanbereadily mapped inphysical space.Application to Kirchhoffvortex shows thatitselipticalcore induces two counter-rotating irrotational eddies.

Keywords:Elliptic Coordinates, Cartesian Coordinates,Kirchhoff Vortex

# 1. Introduction

![](images/5ab679fc5fbab529344e28a30fa0783fe102fdff3982921e58bfc0d50f99039f.jpg)  
Figure1.Coordinatelinesforan elliptic coordinate systemwith $a = 1 , b = 0 . 5$

Theellipticalcoordinatesystem(§,n) as a two-dimensional orthogonal coordinate system has many dynamical and engineering applications,such as Kirchhoff vortex [1],insect aerodynamics [2]，hydrodynamic wave diffraction [3], and theoretical physics [4].Its coordinate lines are confocal ellipses and hyperbolae and the transformation from elliptic to Cartesian coordinates is given by

$$
\begin{array} { l } { x = c \cosh ( \xi ) \cos ( \eta ) } \\ { y = c \sinh ( \xi ) \sin ( \eta ) } \\ { c ^ { 2 } = a ^ { 2 } - b ^ { 2 } } \\ { \xi \geq 0 , 0 \leq \eta < 2 \pi } \end{array}
$$

where $a$ and $b$ denote the semi-major and semi-minor axes of the ellipse and $c$ is the elliptical eccentricity (Figure 1).

In the meantime,explicit equations to transform from Cartesian to elliptic coordinates have not been found in the existing literature [5,6,7]. Such a conversion relation would be useful in mapping an elliptic-coordinate solution, for example the flow field of Kirchhoff vortex, in physical space.

# 2. Cartesian to Elliptic Coordinates

In order to invert the functional relation (1),we first eliminate $\xi$ and have

$$
\frac { x ^ { 2 } } { \cos ^ { 2 } ( \eta ) } - \frac { y ^ { 2 } } { \sin ^ { 2 } ( \eta ) } = c ^ { 2 }
$$

which means curves of constant $\eta$ are hyperbolae. The focus distance is $c$ and the eccentricity is $e = \sec ( \eta )$ ：

Let $p = \sin ^ { 2 } ( \eta )$ , we have

$$
{ \frac { x ^ { 2 } } { 1 - p } } - { \frac { y ^ { 2 } } { p } } = c ^ { 2 }
$$

which becomes

$$
c ^ { 2 } p ^ { 2 } + ( x ^ { 2 } + y ^ { 2 } - c ^ { 2 } ) p - y ^ { 2 } = 0
$$

Then eliminating $\eta$ from(1) we have

$$
\frac { x ^ { 2 } } { \cosh ^ { 2 } ( \xi ) } + \frac { y ^ { 2 } } { \sinh ^ { 2 } ( \xi ) } = c ^ { 2 }
$$

It shows that curves of constant $\xi$ are ellipses.The focus distance is $c$ and the eccentricity is $e = \cosh ^ { - 1 } ( \xi )$ ：

Let $q = - \sinh ^ { 2 } ( \xi )$ , we have

$$
{ \frac { x ^ { 2 } } { 1 - q } } - { \frac { y ^ { 2 } } { q } } = c ^ { 2 }
$$

whichleads to

$$
c ^ { 2 } q ^ { 2 } + ( x ^ { 2 } + y ^ { 2 } - c ^ { 2 } ) q - y ^ { 2 } = 0
$$

It is essentially the same as (2). Therefore (p,q) constitute the two roots of a quadratic equation. Since （20 $0 \leq p \leq 1$ ， $q \leq 0$ , we have $p \geq q$ , and the two roots are

$$
p = { \frac { - B + { \sqrt { B ^ { 2 } + 4 c ^ { 2 } y ^ { 2 } } } } { 2 c ^ { 2 } } } , q = { \frac { - B - { \sqrt { B ^ { 2 } + 4 c ^ { 2 } y ^ { 2 } } } } { 2 c ^ { 2 } } }
$$

in which $B = x ^ { 2 } + y ^ { 2 } - c ^ { 2 }$

From the definition of $p$ we obtain

$$
\eta _ { \mathrm { 0 } } = \arcsin ( { \sqrt { p } } )
$$

It has four cases depending on which quadrant the Cartesian point $( x , y )$ is located, i.e.,

$$
\begin{array} { l l } { { \eta = \eta _ { \scriptscriptstyle 0 } , } } & { { x \geq 0 , y \geq 0 } } \\ { { \eta = \pi - \eta _ { \scriptscriptstyle 0 } , } } & { { x < 0 , y \geq 0 } } \\ { { \eta = \pi + \eta _ { \scriptscriptstyle 0 } , } } & { { x \leq 0 , y < 0 } } \\ { { \eta = 2 \pi - \eta _ { \scriptscriptstyle 0 } , } } & { { x > 0 , y < 0 } } \end{array}
$$

Based on the definition of $q$ ，we can solve $\xi$ from quadratic equation

$$
e ^ { 4 \xi } + ( 4 q - 2 ) e ^ { 2 \xi } + 1 = 0 ,
$$

which has two roots

$$
e ^ { 2 \xi } = 1 - 2 q \pm 2 \sqrt { q ^ { 2 } - q }
$$

Since $q \leq 0$ , both roots are real and denoted as $( \xi _ { 1 } , \xi _ { 2 } )$ They clearly satisfy $e ^ { 2 \xi _ { 1 } } \cdot e ^ { 2 \xi _ { 2 } } = 1$ ，which leads to $\xi _ { 2 } = - \xi _ { 1 } < 0$ ．Because in elliptical coordinatesonly non-negative $\xi$ value is considered,we obtain

$$
\xi = \frac { 1 } { 2 } \ln { ( 1 - 2 q + 2 \sqrt { q ^ { 2 } - q } ) }
$$

Eqs.(4-7） are explicit equations to derive elliptic coordinates from Cartesian grid. They can easily be realized via computation software such as Matlab.

# 3.Application to Kirchhoff Vortex

Kirchhoff vortex is a rotating elliptical region of uniform vorticity $\omega$ embedded in an irrotational ideal fluid [8]. It is the simplest example of non-smooth weak solutions to the Euler equations and has wide application in vortex dynamics [9-11]. It has a discontinuity of vorticity across its elliptical boundary

$$
{ \frac { x ^ { 2 } } { a ^ { 2 } } } + { \frac { y ^ { 2 } } { b ^ { 2 } } } = 1
$$

where $a$ and $b$ are semi-major and semi-minor axes, respectively.Theboundarycorrespondstocontour $\xi = \mathrm { a r c s i n h } ( b / c )$ ，and the vortex rotates with constant angular velocity

$$
\Omega = \frac { a b } { \left( a + b \right) ^ { 2 } } \omega
$$

around the origin. From Act. 159 of Lamb [1],the streamfunction outside the core is

$$
\psi = \frac { 1 } { 4 } \Omega ( a + b ) ^ { 2 } e ^ { - 2 \xi } \cos ( 2 \eta ) + \frac { 1 } { 2 } \omega a b \xi
$$

The instantaneous streamlines in a unsteady flow are given by the curves $\psi = c o n s t$ . In a rotating frame with angular velocity $\Omega$ ，Kirchhoff vortex looks steady and its streamfunction outside the elliptic core is related to the inertial-frame streamfunction (8) by

$$
\psi _ { { } _ { R } } = \psi - \frac { 1 } { 2 } \Omega [ x ( \xi , \eta ) ^ { 2 } + y ( \xi , \eta ) ^ { 2 } ]
$$

From (9) it is straightforward to make a conformal mapping of steady streamfunction on a uniform mesh of elliptic coordinates (Figure 2).

![](images/8ed7e19133de3a3f218316f102928673bb259452f318b364949fe28e5ff157b4.jpg)  
Figure2.Mapping ofstreamfunction (9) on a uniform mesh of(,n),with a=1,b=0.5,@=10.

In order to view the flow field in physical space, we use the conversion equations (4-7) to plot streamfunction (9） on a uniform Cartesian mesh in Figure 3,which shows the elliptical core of Kirchhoff vortex induces two irrotational eddies that rotate in opposite directions.

![](images/233a6c9b6b62ea013db1723ed5649552e05415a370ccba83c8c7793f66bb3401.jpg)  
Figure3.Mapping of streamfunction(9) onauniformmesh ofxy-plane,with$a = 1 , b = 0 . 5$ $\omega = 1 0$ .The boundary of vortex core corresponds to $\xi = 0 . 5 5$ ：

# 4. Conclusion

This study obtains explicit equations that convert Cartesian coordinates to elliptic coordinates.The conversion relation can be easily realized with computer software and used to map a known function of elliptic-coordinates， such asthe streamfunction of Kirchhoff vortex,on a uniform Cartesian mesh.

# Acknowledgements

I would like to thank M. Roghani, V. Varghese and an anonymous reviewer for their comments and encouragement. The study was supported by the National Natural Science Foundation of China (Grant No.41576017).

# References

[1] Lamb,H. (1932） Hydrodynamics. Cambridge Univ. Press, 738pp.   
[2] Wang,Z.(2ooo),Vortex shedding and frequency selection in flapping flight.J.Fluid Mech.,410,323-341.   
[3] Chatjigeorgiou,I.,& Mavrakos,S.(2012),The analytic form of green's function in elliptic coordinates.J.Engineering Math., 72, 87-105.   
[4] Morse,P.,& Feshbach,H.(1953)，Methods of theoretical physics, McGraw-Hill, 1978pp.   
[5] Arfken,G.(1970),Mathematical Methods for Physicists,2nd ed., Academic Press, 815pp.   
[6] Hazewinkel，M. (1988)，Encyclopaedia of Mathematics, Springer, 488pp.   
[7] Korn G.，& Korn，T. (2ooO)，Mathematical handbook for scientists and engineers, Dover, 1152pp.   
[8] Kirchhoff, G.(1877),Vorlesungen iber mathematische Physik. Mechanik,Leipzig.   
[9]Miyazaki，T.，Imai，T.,&Fukumoto，Y.(1995), Three-dimensional instability of Kirchhoff's elliptic vortex. Phys.Fluids,7,195-202.   
[10]Muller,B.,& Yee,H.(2oo1),High order numerical simulation of sound generated by the Kirchhoff vortex.Comp.Visual. Sci., 4,197-204.   
[11] Mitchell,T.,& Rossi,L.(20o8), The evolution of Kirchhoff elliptic vortices.Phys.Fluids,20,054103. Matlab mfile scripts   
function [zeta,eta] $\begin{array} { r } { { \bf \Psi } = { \bf \Psi } } \end{array}$ xy2el(x,y,a,b)   
$\%$ 1   
（204号 $\%$ Conversion from Cartesian mesh $( \mathrm { x } , \mathrm { y } )$ to elliptic coordinates (zeta,eta) （20 $\%$ zeta $( > = 0 )$ ,eta $[ 0 2 \mathrm { p i } )$ （20   
（204 $\%$ a -- semi-major axis   
（204号 $\%$ b -- semi-minor axis   
（204号 $\%$ c -- elliptic eccentricity   
$\%$ (x,y,zeta,eta) same-size matrix   
（204 $\%$ Author: Che Sun (CAS, 2016)   
（204号 $\%$ Source: http://eprint.las.ac.cn/abs/201611.00721   
$\%$ 1   
（204号 $\scriptstyle \mathtt { c 2 = } ( \mathtt { a } ^ { \wedge } 2 \mathbf { - b } ^ { \wedge } 2 ) ; \mathtt { c = } 2 ^ { * } \mathrm { c } 2 ;$   
（20 $\mathbf { \boldsymbol { x } } \mathbf { \boldsymbol { 2 } } \mathbf { \mathrm { = } } \mathbf { \boldsymbol { x } } . \mathbf { \boldsymbol { \wedge } } 2$ ·， $\mathrm { y } 2 \mathrm { = y } . \Lambda 2$ ，   
（204号 $\scriptstyle \mathbf { B } = \mathbf { x } 2 + \mathbf { y } 2 - \mathbf { c } 2$ ：，   
del2 $\scriptstyle \mathbf { \underline { { \tau } } } = \mathbf { B }$ .^2+2\*c\*y2; del $\ c =$ sqrt(del2);   
（204 $\scriptstyle { \mathrm { q = } } ( - \mathbf { B } + \mathbf { d e l } ) / \mathrm { c }$ ; q=sqrt(q); et0 $\vDash$ asin(q);   
eta $\mathbf { \tau = X }$ ：   
i=find( $\scriptstyle \mathrm { X } > = 0 \& \ y > = 0 ,$ ); eta(i)=et0(i);   
i=find(x $_ { : < 0 }$ &y> $\scriptstyle \mathtt { \mathtt { = 0 } }$ )； eta(i) $\mid =$ pi-et0(i);   
i=find(x $\scriptstyle \mathtt { \backslash } < = 0$ &y ${ < } 0$ ); eta(i) $\ c =$ i $+$ et0(i);   
i=find(x>0&y ${ < } 0 ^ { \cdot }$ )； eta(i) ${ \boldsymbol { \mathbf { \mathit { \varepsilon } } } } = 2 ^ { * }$ pi-et0(i);   
$\mathrm { \Delta p { = } } ( { \mathrm { - } } \mathrm { B \mathrm { - } d e l } ) / \mathrm { c }$ ：，   
del2=p.^2-p; del $\ c =$ sqrt(del2);   
zet $\mathrm { a { = } l o g ( 1 { - } 2 ^ { * } p { + } 2 ^ { * } d e l ) / 2 ; \% }$ only keep the positive root   
function [x,y]=el2xy(zeta,eta.a,b)   
$\%$   
$\%$ Conversion from elliptic coordiantes (zeta,eta) to Cartesian coordinates （204 $\%$ zeta $( > = 0 )$ ,eta $[ 0 2 \mathrm { p i } )$ （204号   
（204号 $\%$ a -- semi-major axis   
$\%$ b -- semi-minor axis   
（204 $\%$ C -- elliptic eccentricity   
（204 $\%$ (x,y,zeta,eta) same-size matrix   
$\%$ Author: Che Sun (CAS, 2016)   
（204 $\%$ Source: http://eprint.las.ac.cn/abs/201611.00721   
$\%$ 1   
（204号 $\mathtt { c 2 = a } 2 { \cdot } 2 { \cdot } \mathtt { b } ^ { \wedge } 2$ ， $\mathrm { c } =$ sqrt(c2);   
X=c\*cosh(zeta).\*cos(eta);   
y=c\*sinh(zeta).\*sin(eta);