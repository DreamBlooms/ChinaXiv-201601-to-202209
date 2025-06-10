# Motion of photons in a background of gravitational wave

Zhe Chang,Chao-Guang Huang,and Zhi-Chao Zhao

Institute of High Energy Physics,   
Chinese Academy of Sciences,Beijing 100049,China   
School of Physics, University of Chinese Academy of Sciences,Beijing 10o049. China

Abstract. The photon motion in a Michelson interferometer is re-analyzed in both geometrical optics and wave optics.The classical paths of the photons in the background of gravitational wave are derived from Fermat principle,which is the same as the null geodesics in general relativity. The deformed Maxwell equations and the wave equations of electric fields in the background of gravitational wave are presented in flat-space approximation.Both methods show that the response of an interferometer depends on the frequency of a gravitational wave,however it is almost independent of the frequency of the mirror's vibrations. It implies that the vibrating mirror cannot mimic a gravitational wave very well.

PACS numbers:04.30.Nk, 04.80.Nn

Keywords: Fermat principle, modified Maxwell equations, frequency dependency, gravitational wave vs mirror swing.

Submitted to: Class. Quantum Grav.

# 1.Introduction

The transient gravitational wave (GW） events， GW150914 and GW151226, were detected in the first run (O1, from September 12， 2015 to January 19, 2016) of the advanced LIGO [1],[2]. The events were reported to be the results of the coalescence of two black holes of masses $3 6 M _ { \odot }$ and $2 9 M _ { \odot }$ to a black hole of $6 2 M _ { \odot }$ and of two black holes of masses about $1 4 M _ { \odot }$ and $8 M _ { \odot }$ to a black hole of mass about $2 1 M _ { \odot }$ , respectively. The GW signals are chirps in the frequency ranges between 35 to 150 Hz and between 35 to about $7 0 0 ~ \mathrm { H z }$ , respectively. The signals of GW150914 and GW151226 are extracted from the sea of noises by the same methods (for example, see refs. [3], [4]). Hence, the explanation of the observations are widely accepted.

A LIGO detector is, basically, a Michelson intermerometer (MI) with its arms replaced by Fabry-Pérot (FP) cavities [5]. One of the roles of the FP cavities is to increase the interaction time of photons with GWs. On average, a photon travels 140 round-trips in the FP cavity. In other words, a photon stays in a cavity for about （204号 $2 8 0 L / c \approx 3 . 7 3$ ms on average, where $L \approx 4$ km is the average length of arms. In 3.73 ms, a GW with frequency about 268 Hz will propagate through the detector for a wavelength and thus a photon cannot ‘feel’ the length variation of the arms [6],[7]. However, it is widely accepted that the response of a Michelson-Fabry-Pérot interferometer is as about $2 N$ times as the response of a same size Michelson interferometer,where $N$ is the average number of the round trips (see, for example, [8],[3]). The previous studies on the instruments and calibration [8],[9],[10],[11],[12],[13],[14] show that the response of a detector to a GW will not depend on the frequency when the frequency of a GW is lower than 1 kHz. Why is there such a kind of inconsistency?

In fact，almost all previous studies on the response of detector to a GW are conducted by use of the swing of mirrors [9],[10],[11], [13],[14]. They seem to be supported by the theoretical analysis for the response to a GW [12]. In these analysis, the Laplace transformation is used, which is still questionablet. In the present paper, we shall re-analysis the response of a detector to a GW, without the help of Laplace transformation. We shall focus on the Michelson interferometer in this paper.

The motion of photons in a detector is govern by general relativity. In other words, the photons should move along the null geodesics in the space-time. In fact, there are two other ways to describe the motion of photons. The first one is the method of classical geometrical optics, in which paths of photons in three dimensional space are determined by the Fermat principle. To apply the Fermat principle in vacuum of a curved spacetime, the metric is regarded as a position-， direction-,and time-dependent refractive-index tensor of a special transparent medium in a fat space. The second one is the method of $\ddagger$ To our knowledge,the first application of the Laplace transformation in the study of the response of an interferometer is in [15] and [8]. In the references, the following equation is used

$$
\mathcal { L } \left( \int _ { t - L } ^ { t } h ( t ) d t \right) = \frac { 1 - e ^ { - p L } } { p } \mathcal { L } ( h ( t ) ) ,
$$

where $\mathcal { L }$ represents the Laplace transformation, $p$ is the Laplace domain variable. However，for $h ( t ) = \sin ( \omega t )$ ，a direct calculation shows

$$
{ \mathcal { L } } \left( \int _ { t - L } ^ { t } \sin ( \omega t ) d t \right) = { \mathcal { L } } \left( { \frac { 1 } { \omega } } \left( \cos ( \omega ( t - L ) ) - \cos ( \omega t ) \right) \right) = { \frac { 1 } { \omega } } { \frac { 1 } { p ^ { 2 } + \omega ^ { 2 } } } ( p \cos ( \omega L ) + \omega \sin ( \omega L ) - p ) .
$$

and

$$
\frac { 1 - e ^ { - p L } } { p } \mathcal { L } ( \sin ( \omega t ) ) = \frac { 1 - e ^ { - p L } } { p } \frac { \omega } { p ^ { 2 } + \omega ^ { 2 } } .
$$

They are not equal to each other. The equation should be revised as

$$
\mathcal { L } \left( \int _ { t - L } ^ { t } h ( t ) d t \right) = \frac { 1 - e ^ { - p L } } { p } \mathcal { L } ( h ( t ) ) - e ^ { - p L } \left[ \int _ { - L } ^ { 0 } e ^ { - p \tau } \left( \int _ { 0 } ^ { \tau } h ( t ) \mathrm { d } t \right) \mathrm { d } \tau \right] .
$$

classical wave optics,which is based on the wave equation of electric field derived from the Maxwell equations. The first aim of the present paper is to study the motion of photons in a single arm by use of the two methods. Although a realistic detector needs double arms, we may just consider a single one because the motion of photons in each arm is govern by the same law but has the different polarity due to the quadruple nature of the GW. We shall show that the paths of photons determined by the Fermat principle are the same as that determined by the null geodesics even in the background of GW. We shall also show that a GW may serve as a time-dependent medium in flat space-time and present the deformed Maxwell equations and wave equations of electric field in the fat space-time approximation. With the two methods, we may obtain the same claim as that by use of the null geodesics [6],[7]: the response of a detector depends on the frequency of a GW.

The key point for an interferometric detector of GW is to measure the variation of the phase difference between two beams of light. The variation of the phase difference comes from the variation of proper lengths of two arms induced by a GW. On one hand, GW signals are submerged in the sea of noises and one has to find ways to extract the GW signals from noises. On the other,a detector needs the calibration to determine the sensitivity of the detector. Since both a GW and the mirror's swings will result in the variations of the proper length of each arm, a naive idea is that the effect of GW on a detector can be mimicked by the vibrations of the mirrors' position and many detector investigations have been made in this way [9],[10],[11],[13], [14]. The other purpose of the paper is to show that there is essential difference for the motion of photons in the background of GW and in a vibrating arm. The response of a detector depends on the frequency of a GW. For some specific frequency, the detector has no response. In contrast, the response of a detector to the vibrations with different frequency is almost the same.

The rest of the paper is organized as follows. In section 2, the motion of photons in both a flat space-time and in the background of GW is studied in the framework of geometrical optics. The trajectories of photons are derived from the Fermat principle and are shown to be the same as those along null geodesics in general relativity. The time difference for a round trip between in the background of GW and in a flat spacetime is shown to be dependent on the frequency of GW. In section 3, the propagation of the electromagnetic wave is investigated in wave optics. The deformed Maxwell equations and thus the wave equations for electric field are presented in the background of GW in a flat space-time approximation. The time difference is also calculated in the framework of wave optics. The results are the same as those in geometrical optics. Section 4 is devoted to the comparison of the differences between motion of photons in the background of GW and in a vibrating arm. The conclusions and remarks are given in section 5. Throughout the paper, the $c = 1$ units are used in the derivation and thus $x ^ { 0 } = t$ ：

# 2.Motion of photons in the background of gravitational wave

We are interested in the Minkowski spacetime and the spacetime with a plus-polarized, linear,normally incident， plane GW. In a time-orthogonal coordinate system， the metrics for the both cases can be written as

$$
\mathrm { d } s ^ { 2 } = - \mathrm { d } t ^ { 2 } + g _ { i j } \mathrm { d } x ^ { i } \mathrm { d } x ^ { j } , ~ i , j = 1 , 2 , 3 ~ .
$$

The distance between two near points in a simultaneous hypersurface is measured by [16]

$$
\mathrm { d } l ^ { 2 } = g _ { i j } \mathrm { d } x ^ { i } \mathrm { d } x ^ { j } .
$$

We consider a photon travels from point $A$ to point $B$ in space. There are infinitely possible classical paths. The length for each path is given by

$$
L = \int _ { A } ^ { B } \left( g _ { i j } { \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } } { \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } } \right) ^ { 1 / 2 } \mathrm { d } t ,
$$

where $\mathrm { d } x ^ { i } / \mathrm { d } t$ is the coordinate velocity of the photon.

In geometrical optics, the path of a photon is determined by the Fermat principle,

$$
\begin{array} { r l } & { ( 0 = \delta L = \delta \int _ { A } ^ { B } ( { \mathcal { J } } _ { \phi i } \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } ) ^ { 1 / 2 } \mathrm { d } t } \\ & { ~ = \frac { 1 } { 2 } \int _ { A } ^ { B } \frac { \partial g _ { i j } \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } + 2 g _ { i j } \frac { \mathrm { d } \delta x ^ { i } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } } { \sqrt { \beta m _ { m } } \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } } \mathrm { d } t } \\ & { ~ = \int _ { A } ^ { B } [ \frac { g _ { i j , k } \delta x ^ { k } \frac { \mathrm { d } x ^ { i } } { d t } \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } } { \sqrt { { \mathcal { J } } _ { \phi m } } \frac { \mathrm { d } x ^ { n } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } } - 2 \delta x ^ { i } \frac { \mathrm { d } } { \mathrm { d } t } ( \frac { g _ { i j } \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } } { \sqrt { { \mathcal { J } } _ { \phi m } \frac { \mathrm { d } x ^ { n } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { n } } { \mathrm { d } t } } } ) ] \mathrm { d } t ~ . } \end{array}
$$

Here,only the isochronal variation is considered, so that $\delta t = 0$ . In the last step, the total-derivative term is absent because the end point of the integral is fixed. From the above expression, it is easy to see that

$$
\frac { g _ { i j , k } \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } } { \sqrt { g _ { m n } \frac { \mathrm { d } x ^ { m } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { n } } { \mathrm { d } t } } } - 2 \frac { \mathrm { d } } { \mathrm { d } t } \left( \frac { g _ { k j } \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } } { \sqrt { g _ { m n } \frac { \mathrm { d } x ^ { m } } { \mathrm { d } t } \frac { \mathrm { d } x ^ { n } } { \mathrm { d } t } } } \right) = 0 \ .
$$

For convenience,we take $l$ as the path parameter. Then, Eq.(5) becomes

$$
g _ { i j , k } { \frac { \mathrm { d } x ^ { i } } { \mathrm { d } l } } { \frac { \mathrm { d } x ^ { j } } { \mathrm { d } l } } - 2 { \frac { \mathrm { d } } { \mathrm { d } l } } \left( g _ { k j } { \frac { \mathrm { d } x ^ { j } } { \mathrm { d } l } } \right) = 0 \ ,
$$

$$
{ \frac { 1 } { 2 } } g ^ { j \rho } \left( g _ { \mu \nu , \rho } - 2 g _ { \rho \mu , \nu } \right) { \frac { \mathrm { d } x ^ { \mu } } { \mathrm { d } l } } { \frac { \mathrm { d } x ^ { \nu } } { \mathrm { d } l } } - { \frac { \mathrm { d } ^ { 2 } x ^ { j } } { \mathrm { d } l ^ { 2 } } } = 0 \ .
$$

In terms of the Christoffel symbols, it can be recast into the spatial part of 4-dimensional geodesic equation:

$$
{ \frac { \mathrm { d } ^ { 2 } x ^ { i } } { \mathrm { d } l ^ { 2 } } } + \Gamma _ { \mu \nu } ^ { i } { \frac { \mathrm { d } x ^ { \mu } } { \mathrm { d } l } } { \frac { \mathrm { d } x ^ { \nu } } { \mathrm { d } l } } = 0 , \ \mu , \nu = 0 , 1 , 2 , 3 \ .
$$

It should be noted that Eq. (8) is different, in general, from the geodesic equation in 3-dimensinal space,

$$
{ \frac { \mathrm { d } ^ { 2 } x ^ { i } } { \mathrm { d } l ^ { 2 } } } + \Gamma _ { j k } ^ { i } { \frac { \mathrm { d } x ^ { j } } { \mathrm { d } l } } { \frac { \mathrm { d } x ^ { k } } { \mathrm { d } l } } = 0 .
$$

The difference comes from the time-dependence of $g _ { i j }$ in(8）or, in other words, from the time-dependent ‘refractive index'.

Since the light travels along a null curve and since the path length should take extremal value, the traveling time of a photon from $A$ to $B$ （204号

$$
T = \int _ { A } ^ { B } \mathrm { d } t = \int _ { A } ^ { B } \left( g _ { i j } { \frac { \mathrm { d } x ^ { i } } { \mathrm { d } t } } { \frac { \mathrm { d } x ^ { j } } { \mathrm { d } t } } \right) ^ { - 1 / 2 } \mathrm { d } l
$$

should also take the extremal value for fixed path. Namely,

$$
\begin{array} { l } { { \left\| { \bf { \bar { \Pi } } } \right\| = \delta T = - \frac 1 2 \int _ { A } ^ { B } \left( \int _ { 0 } { \cos { \frac { \mathrm { d } \pi ^ { \prime } } { \mathrm { d } t } } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } } \right)}  ^ { - 3 / 2 } }  \\ { { \left. { \tilde { \cal A } } \rho _ { \mathrm { { e f f } } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } } - 2 \rho _ { \mathrm { { e } f f } } { \frac { \mathrm { d } x ^ { \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } x ^ { \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } t } { \mathrm { ~ d } t } } \right. = \mathrm { d } t } } \\ { { - \ - \frac 1 2 \int _ { A } ^ { B } \left[ { \left( \int _ { 0 } { \cos { \frac { \mathrm { d } \pi ^ { \prime } } { \mathrm { d } t } } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t ^ { \prime } } } \right)}  ^ { \frac { 1 / 2 } { 1 / 2 } } { \mathcal { \bar { A } } } \rho _ { \mathrm { { e } f f } } { \frac { \mathrm { d } x ^ { \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } x ^ { \prime } } { \mathrm { ~ d } t } } \right.}  } \\ { { \left. \left. + 2 { \frac { \mathrm { d } \pi } { \mathrm { d } t } } \left( \rho _ { \mathrm { { o } } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } x ^ { \prime } } { \mathrm { ~ d } t } } \right) ^ { 1 / 2 } \right] \delta \mathrm { d } t \right.} } \\  { = - \frac 1 2 \int _ { A } ^ { B } \left( \rho _ { \mathrm { { o u t } } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } } \right) ^ { - 3 / 2 } \left[ \rho _ { \mathrm { { o f } } } { \frac { \mathrm { d } x ^ { \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } x ^ { \prime } } { \mathrm { ~ d } t } } \right. } \\  { \left. \mathrm { ~ \rho ~ } \right }. { \tilde { \cal A } } _ { P } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } } { \frac { \mathrm { d } x ^ { \prime \prime } } { \mathrm { ~ d } t } }  +  \frac  \mathrm { d } x \end{array}
$$

Here,only the time variation is considered ( $\delta x ^ { i } = 0$ ). In the second step,the total derivative is zero, too. Hence,

$$
g _ { i j , 0 } { \frac { \mathrm { d } x ^ { i } } { \mathrm { d } l } } { \frac { \mathrm { d } x ^ { j } } { \mathrm { d } l } } + 2 \left( { \frac { \mathrm { d } l } { \mathrm { d } t } } \right) ^ { 2 } { \frac { \mathrm { d } } { \mathrm { d } l } } { \frac { \mathrm { d } t } { \mathrm { d } l } } = 0 .
$$

When

$$
\left( { \frac { \mathrm { d } l } { \mathrm { d } t } } \right) ^ { 2 } = 1 ,
$$

in terms of the Christoffel symbols, Eq. (12） reduces to the temporal part of fourdimensional geodesic equation:

$$
{ \frac { \mathrm { d } ^ { 2 } t } { \mathrm { d } l ^ { 2 } } } + \Gamma _ { \mu \nu } ^ { 0 } { \frac { \mathrm { d } x ^ { \mu } } { \mathrm { d } l } } { \frac { \mathrm { d } x ^ { \nu } } { \mathrm { d } l } } = 0 \ .
$$

Eqs. (8), (14), (13) show that in the framework of the geometrical optics a photon travels along a null geodesic of a 4-dimensional space-time in both cases of a flat spacetime and the background of GW,as expected in general relativity and the arc length $l$ along a path serves as the affine parameter of the null geodesic. The trajectories of photons are the straight line in the 3 space just as the absence of a GW. The distance that a photon travels is the arc-length of the geodesic, $L = \int \mathrm { d } l$ . Its value and thus the traveling time will be influenced by the time-dependent metric $g _ { \mu \nu }$ in the background of GW.

Now, we calculate the traveling time of a photon travels along $x$ axis from mirror $A$ at position $x _ { 1 } = 0$ to mirror $B$ at $x _ { 2 } ~ = ~ L$ .(From now on, $L$ is the coordinate length of the arm.） When there is no GW and matter, the metric is of the form $g _ { \mu \nu } = \mathrm { d i a g } ( - 1 , 1 , 1 , 1 )$ . When a monochromatic GW with plus-polarization incidents along the $z$ axis, the metric has the form

$$
g _ { \mu \nu } = \mathrm { d i a g } ( - 1 , 1 + h _ { 1 1 } , 1 - h _ { 1 1 } , 1 ) , \quad h _ { 1 1 } = \Re [ e _ { 1 1 } e ^ { - i ( 2 \pi f t + \phi ) } ] ,
$$

where $e _ { 1 1 }$ is the amplitude of the GW, $\Re$ means that the real part of the expression is taken, $\phi$ is the initial phase of the GW when the photon leaves mirror $A$ ：

It is well known that if there is no GW, the distance between two mirrors in one arm of the interferometer is

$$
L = \int _ { 0 } ^ { L } \mathrm { d } x .
$$

It is also the traveling time of a photon from one mirror to the other. In other words, $T = L$ ：

In the background of GW, the traveling time of a photon from one mirror to the other becomes $T ^ { \prime }$ and

$$
T ^ { \prime } = \int _ { 0 } ^ { L } ( g _ { 1 1 } ) ^ { - 1 / 2 } \mathrm { d } x = \int _ { 0 } ^ { L } \left( 1 + \frac { 1 } { 2 } h _ { 1 1 } \right) \mathrm { d } x \ .
$$

In the last step of (17)， the Taylor expansion has been used and the GW wave is supposed to be an extremely small perturbation around the flat space. Obviously,

$$
T ^ { \prime } = L + \frac { 1 } { 2 } \int _ { 0 } ^ { L } h _ { 1 1 } \left( t \right) \mathrm { d } x = T + \Delta T ^ { \prime } \ .
$$

As expected, a GW background will change the length of the interferometer's arm. In other words, a photon will feel’ the distance difference $\begin{array} { r } { \Delta L = \Delta T ^ { \prime } = ( 1 / 2 ) \int _ { 0 } ^ { L } h _ { 1 1 } ( t ) \mathrm { d } x } \end{array}$ （202 due to the presence of a GW. One should remember that $h _ { 1 1 }$ is a function of time $t$

Now we consider a photon moves a round trip from mirror $A$ to mirror $B$ and then back to mirror $A$ .For $A  B$ , the distance that a photon travels is

$$
T _ { A  B } ^ { \prime } = T + \Delta T _ { A  B } ^ { \prime } ~ ,
$$

and for $B  A$ , the distance that a photon travels is

$$
T _ { B  A } ^ { \prime } = \int _ { L } ^ { 0 } ( 1 + \frac { 1 } { 2 } h _ { 1 1 } ( t ) ) \mathrm { d } x = L + \frac { 1 } { 2 } \int _ { t _ { 0 } + T } ^ { t _ { 0 } + 2 T } h _ { 1 1 } ( t ) \mathrm { d } t = T + \Delta T _ { B  A } ^ { \prime } ,
$$

where $t _ { 0 }$ is the time when the photon leaves $A$ . In the first line of the equation, ${ \mathrm { d } } x$ is always negative. In the second line, the higher-order terms have been neglected. It should be noted that $\Delta T _ { A  B } ^ { \prime } \neq \Delta T _ { B  A } ^ { \prime }$ in principle.

For a round trip,we have

$$
\Delta T ^ { \prime } = \frac { 1 } { 2 } \int _ { t _ { 0 } } ^ { t _ { 0 } + 2 T } h _ { 1 1 } \left( t \right) \mathrm { d } t = \frac { e _ { 1 1 } \sin ( 2 \pi f T ) } { 2 \pi f } \Re \left[ e ^ { - i \left( \phi + 2 \pi f \left( t _ { 0 } + T \right) \right) } \right] .
$$

It shows that at specific values of the frequency of GW, $\begin{array} { r } { f = \frac { n } { 2 L } } \end{array}$ (with $n = 1 , 2 , 3 , \ldots$ ) （204号 $\Delta T ^ { \prime } = 0$ no matter what value the initial phase $\phi$ takes. It means that for the GW with the frequency $\textstyle { \frac { n } { 2 L } }$ there will be no measure difference between the presence and absence of a GW for traveling photons. The result has been reached in the literature [17], [8].

Define the dimensionless frequency of GW: $a = 2 L f ( > 0 )$ . Then, the traveling time of a photon for a round trip from $A$ to $B$ and back to $A$ is

$$
\Delta T ^ { \prime } = \frac { e _ { 1 1 } { \cal L } } { 2 \pi a } \Re \left[ - i e ^ { - i \left( \phi + \frac { a \pi t _ { 0 } } { { \cal L } } \right) } \left( 1 - e ^ { - 2 i a \pi } \right) \right] \ .
$$

In particular, when $t _ { 0 } = 0$ .

$$
\Delta T ^ { \prime } = \frac { e _ { 1 1 } L } { 2 \pi a } \left[ \sin \left( 2 a \pi + \phi \right) - \sin \left( \phi \right) \right] \ .
$$

# 3. Propagation of electromagnetic wave in the background of gravitational wave

In wave optics, light is treated as electromagnetic wave， which satisfies the Maxwell equations.

The Maxwell equations in vacuum of a curved space-time read

$$
F _ { ; \nu } ^ { \mu \nu } = \frac { 1 } { \sqrt { - g } } \left( \sqrt { - g } F ^ { \mu \nu } \right) _ { , \nu } = 0 ,
$$

$$
F _ { \mu \nu , \lambda } + F _ { \lambda \mu , \nu } + F _ { \nu \lambda , \mu } = 0 \ ,
$$

where $F _ { \mu \nu } ~ = ~ - F _ { \nu \mu } ~ = ~ \partial _ { \mu } A _ { \nu } - \partial _ { \nu } A _ { \mu }$ is the electromagnetic field tensor, $A _ { \mu }$ is the electromagnetic potential. The electric field is

$$
E _ { i } = - F _ { i \nu } U ^ { \nu } ,
$$

and the magnetic field is

$$
B _ { i } = - { \frac { 1 } { 2 } } { \epsilon _ { i \mu } } ^ { \lambda \sigma } U ^ { \mu } F _ { \lambda \sigma } \ ,
$$

where $\epsilon$ is the Levi-Civita tensor and $U ^ { \mu }$ is the 4-velocity of an observer, satisfying $g _ { \mu \nu } U ^ { \mu } U ^ { \nu } = - 1$ . For static observers, $U ^ { \mu } = ( 1 , 0 , 0 , 0 )$ . Then, the electric feld $E$ and magnetic field $B$ observed by the static observers are

$$
E _ { i } = - F _ { i \nu } U ^ { \nu } = - F _ { i 0 } = \partial _ { 0 } A _ { i } - \partial _ { i } A _ { 0 } \ ,
$$

$$
B _ { i } = - \frac { 1 } { 2 } \epsilon _ { i \mu } ^ { \lambda \sigma } U ^ { \mu } F _ { \lambda \sigma } = \frac { 1 } { 2 } \epsilon _ { i } ^ { \lambda \sigma } F _ { \lambda \sigma } = \frac { 1 } { 2 } g ^ { \alpha \lambda } g ^ { \beta \sigma } \epsilon _ { i \alpha \beta } \left( \partial _ { \lambda } A _ { \sigma } - \partial _ { \sigma } A _ { \lambda } \right) \ .
$$

In the background of GW (15)， the explicit forms of three components of the magnetic filed $B _ { i }$ are,

$$
\begin{array} { l } { { B _ { 1 } = \left( 1 + h _ { + } \right) \left( \partial _ { 2 } A _ { 3 } - \partial _ { 3 } A _ { 2 } \right) ~ , } } \\ { { B _ { 2 } = \left( 1 - h _ { + } \right) \left( \partial _ { 3 } A _ { 1 } - \partial _ { 1 } A _ { 3 } \right) ~ , } } \\ { { B _ { 3 } = \left( \partial _ { 1 } A _ { 2 } - \partial _ { 2 } A _ { 1 } \right) ~ . } } \end{array}
$$

Therefore,

$$
\begin{array} { l } { { F _ { 0 i } = E _ { i } ~ , } } \\ { { F _ { 1 2 } = B _ { 3 } ~ , } } \\ { { F _ { 2 3 } = \left( 1 - h _ { + } \right) B _ { 1 } ~ , } } \\ { { F _ { 3 1 } = \left( 1 + h _ { + } \right) B _ { 2 } ~ , } } \end{array}
$$

and,

$$
\begin{array} { l } { { F ^ { 0 1 } = - \left( 1 - h _ { + } \right) E _ { 1 } \ , } } \\ { { F ^ { 0 2 } = - \left( 1 + h _ { + } \right) E _ { 2 } \ , } } \\ { { F ^ { 0 3 } = - E _ { 3 } \ , } } \end{array}
$$

$$
\begin{array} { r } { F ^ { 1 2 } = B _ { 3 } \ , } \\ { F ^ { 2 3 } = B _ { 1 } \ , } \\ { F ^ { 3 1 } = B _ { 2 } \ . } \end{array}
$$

In the background of GW (15), the Maxwell equations (24) read

$$
F ^ { \mu 0 } { } _ { , 0 } + F ^ { \mu i } { } _ { , i } = 0 \ .
$$

Namely,

$$
F ^ { 0 i } { } _ { , i } = F ^ { i 0 } { } _ { , i } = 0 \ ,
$$

$$
F ^ { j 0 } { } _ { , 0 } + F ^ { j i } { } _ { , i } = 0 \ ,
$$

or

$$
\begin{array} { r l } & { ( h _ { + } - 1 ) E _ { 1 , 1 } - ( 1 + h _ { + } ) E _ { 2 , 2 } - E _ { 3 , 3 } = 0 \ , } \\ & { \qquad ( ( 1 - h _ { + } ) E _ { 1 } ) _ { , 0 } + B _ { 3 , 2 } - B _ { 2 , 3 } = 0 \ , } \\ & { \qquad ( ( 1 + h _ { + } ) E _ { 2 } ) _ { , 0 } - B _ { 3 , 1 } + B _ { 1 , 3 } = 0 \ , } \end{array}
$$

$$
{ \cal E } _ { 3 , 0 } + { \cal B } _ { 2 , 1 } - { \cal B } _ { 1 , 2 } = 0 \ .
$$

The Maxwell equations (25)

$$
\begin{array} { r c l } { { F _ { 0 i , j } + F _ { j 0 , i } + F _ { i j , 0 } } } & { { = 0 ~ , } } \\ { { } } & { { } } & { { } } \\ { { F _ { i j , k } + F _ { k i , j } + F _ { j k , i } } } & { { = 0 ~ , } } \end{array}
$$

reduce to

$$
\begin{array} { c } { E _ { 1 , 2 } - E _ { 2 , 1 } + B _ { 3 , 0 } = 0 , } \\ { E _ { 1 , 3 } - E _ { 3 , 1 } - \left( \left( 1 + h _ { + } \right) B _ { 2 } \right) _ { , 0 } = 0 , } \\ { E _ { 2 , 3 } - E _ { 3 , 2 } + \left( \left( 1 - h _ { + } \right) B _ { 1 } \right) _ { , 0 } = 0 , } \\ { B _ { 3 , 3 } + \left( 1 + h _ { + } \right) B _ { 2 , 2 } + \left( 1 - h _ { + } \right) B _ { 1 , 1 } = 0 . } \end{array}
$$

The above equations can be rewritten into a compact form

$$
\left\{ \begin{array} { l l } { \displaystyle \nabla \cdot \boldsymbol { E } = h _ { + } \left( E _ { 1 , 1 } - E _ { 2 , 2 } \right) ~ , } \\ { \displaystyle \frac { \partial E } { \partial t } - \frac { \partial h } { \partial t } \cdot \boldsymbol { E } + \nabla \times \boldsymbol { B } = 0 ~ , } \\ { \displaystyle - \nabla \times \boldsymbol { E } + \frac { \partial \boldsymbol { B } } { \partial t } = \frac { \partial h } { \partial t } \cdot \boldsymbol { B } ~ , } \\ { \displaystyle \nabla \cdot \boldsymbol { B } = h _ { + } \left( B _ { 1 , 1 } - B _ { 2 , 2 } \right) ~ , } \end{array} \right.
$$

where $\pmb { { \cal E } }$ and $\pmb { B }$ are electric field and magnetic field vector in column matrix form and （204号 $^ { h }$ is a square matrix:

$$
h = \left( \begin{array} { c c c } { { h _ { + } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { - h _ { + } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 0 } } \end{array} \right) \ ,
$$

$\nabla$ is the gradient operator in 3-dimensional flat space. These are the deformed Maxwell equations in the background of GW in a flat space-time approximation.

We try to setup the electromagnetic wave equations from the deformed Maxwell equations. First, making a time derivative at both sides of the second equation (37) and using the third equation, we get

$$
\frac { \partial ^ { 2 } \pmb { E } } { \partial t ^ { 2 } } - \nabla ^ { 2 } \pmb { E } = \frac { \partial ^ { 2 } ( \pmb { h } \cdot \pmb { E } ) } { \partial t ^ { 2 } } - \nabla \left( \nabla \cdot \pmb { E } \right) - \nabla \times \frac { \partial ( \pmb { h } \cdot \pmb { B } ) } { \partial t } \ .
$$

The ratio of the frequency of GW and that of photons is very small and can be used as a perturbation parameter. Then,

$$
{ \frac { \partial ^ { 2 } { \pmb { E } } } { \partial t ^ { 2 } } } - \nabla ^ { 2 } { \pmb { E } } = { \pmb { h } } \cdot { \frac { \partial ^ { 2 } { \pmb { E } } } { \partial t ^ { 2 } } } - h _ { + } \nabla \left( E _ { 1 , 1 } - E _ { 2 , 2 } \right) - \nabla \times \left( { \pmb { h } } \cdot \left( \nabla \times { \pmb { E } } \right) \right) ~ .
$$

It can be rewritten as

$$
\left( 1 - h \right) \cdot \frac { \partial ^ { 2 } \mathbf { E } } { \partial t ^ { 2 } } - \nabla ^ { 2 } \mathbf { E } = - h _ { + } \nabla \left( E _ { 1 , 1 } - E _ { 2 , 2 } \right) - \nabla \times \left( h \cdot \left( \nabla \times \mathbf { E } \right) \right) .
$$

In components, the deformed electromagnetic wave equations are of the form

$$
\{ \begin{array} { l l } { \displaystyle ( 1 - h _ { + } ) \displaystyle \frac { \partial ^ { 2 } E _ { 1 } } { \partial t ^ { 2 } } - \nabla ^ { 2 } E _ { 1 } = - h _ { + } ( E _ { 1 , 1 1 } - E _ { 2 , 2 1 } ) - h _ { + } ( E _ { 1 , 3 3 } - E _ { 3 , 1 3 } ) , } \\ { \displaystyle ( 1 + h _ { + } ) \displaystyle \frac { \partial ^ { 2 } E _ { 2 } } { \partial t ^ { 2 } } - \nabla ^ { 2 } E _ { 2 } = - h _ { + } ( E _ { 1 , 1 2 } - E _ { 2 , 2 2 } ) - h _ { + } ( E _ { 3 , 2 3 } - E _ { 2 , 3 3 } ) , } \\ { \displaystyle  \displaystyle \frac { \partial ^ { 2 } E _ { 3 } } { \partial t ^ { 2 } } - \nabla ^ { 2 } E _ { 3 } = h _ { + } ( E _ { 3 , 2 2 } - E _ { 3 , 1 1 } ) ~ . } \end{array} 
$$

The similar wave equations for $B$ can be obtained in the same way.

When the electromagnetic wave propagates along $x$ axis, $E _ { 1 } = 0$ . Then,the first equation of （42） is the identity $0 = 0$ in the leading order. The latter two equations read

$$
\left\{ \begin{array} { l l } { \displaystyle \left( 1 + h _ { + } \right) \frac { \partial ^ { 2 } E _ { 2 } } { \partial t ^ { 2 } } - \nabla ^ { 2 } E _ { 2 } = h _ { + } E _ { 2 , 2 2 } - h _ { + } \left( E _ { 3 , 2 3 } - E _ { 2 , 3 3 } \right) , } \\ { \displaystyle \frac { \partial ^ { 2 } E _ { 3 } } { \partial t ^ { 2 } } - \nabla ^ { 2 } E _ { 3 } = h _ { + } \left( E _ { 3 , 2 2 } - E _ { 3 , 1 1 } \right) . } \end{array} \right.
$$

Since the right hand side of the first equation of (43) is

$$
\begin{array} { r l } & { h _ { + } E _ { 2 , 2 2 } + h _ { + } [ ( E _ { 1 , 1 } + E _ { 2 , 2 } + h _ { + } E _ { 2 , 2 } - h _ { + } E _ { 1 , 1 } ) _ { , 2 } + E _ { 2 , 3 3 } ] } \\ & { = h _ { + } E _ { 2 , 2 2 } + h _ { + } \left( E _ { 2 , 2 2 } + E _ { 2 , 3 3 } \right) } \\ & { = h _ { + } E _ { 2 , 2 2 } + h _ { + } \left( \nabla ^ { 2 } E _ { 2 } - E _ { 2 , 1 1 } \right) \ , } \end{array}
$$

the first equation of (43) reduces to

$$
\left( 1 + h _ { + } \right) \frac { \partial ^ { 2 } E _ { 2 } } { \partial t ^ { 2 } } - \left( 1 + h _ { + } \right) \nabla ^ { 2 } E _ { 2 } = h _ { + } \left( E _ { 2 , 2 2 } - E _ { 2 , 1 1 } \right) \ .
$$

The leading order of the perturbation of the electromagnetic wave's equation is

$$
\frac { \partial ^ { 2 } E _ { 2 } } { \partial t ^ { 2 } } - \nabla ^ { 2 } E _ { 2 } = h _ { + } \left( E _ { 2 , 2 2 } - E _ { 2 , 1 1 } \right) \ .
$$

For the electromagnetic wave propagating along the $x$ axis, $E _ { 2 , 2 2 } ~ = ~ 0$ ， $E _ { 2 , 3 3 } ~ = ~ 0$ ， $E _ { 3 , 2 2 } = 0$ ， $E _ { 3 , 3 3 } = 0$ . Hence,

$$
\frac { \partial ^ { 2 } E _ { 2 } } { \partial t ^ { 2 } } - \left( 1 - h _ { + } \right) E _ { 2 , 1 1 } = 0 \ .
$$

The similar deduction gives rise to

$$
\frac { \partial ^ { 2 } E _ { 3 } } { \partial t ^ { 2 } } - \left( 1 - h _ { + } \right) E _ { 3 , 1 1 } = 0 \ .
$$

(47) and (48) are just the deformed form of the wave equation for electric field. The equations (47) and (48） gives the coordinate speed of the electromagnetic wave in the background of GW,

$$
v _ { x } = \sqrt { 1 - h _ { + } \left( t \right) } \approx 1 - \frac { h _ { + } } { 2 } \ .
$$

Similarly, one can obtain that

$$
v _ { y } = \sqrt { 1 + h _ { + } \left( t \right) } \approx 1 + \frac { h _ { + } } { 2 } .
$$

These mean that the photon's coordinate speeds vary with the perturbation of spacetime, which is caused by GW. The similar result has been obtained in other ways (say, in [8]).

Suppose that the electromagnetic wave spend $T ^ { \prime }$ and $T$ to propagate from $A$ to $B$ （204号 and then back to $A$ when there is and there is no GW, respectively. The time difference $\Delta T ^ { \prime }$ due to GW satisfies

$$
2 L = \int _ { t _ { 0 } } ^ { t _ { 0 } + 2 T + \Delta T ^ { \prime } } v \mathrm { d } t = \int _ { t _ { 0 } } ^ { t _ { 0 } + 2 T + \Delta T ^ { \prime } } \left( 1 - \frac { 1 } { 2 } \Re [ e _ { 1 1 } e ^ { - i ( 2 \pi f t + \phi ) } ] \right) \mathrm { d } t \ .
$$

Again, set $\begin{array} { r } { f = \frac { a } { 2 L } } \end{array}$ and $t _ { 0 } = 0$ . Eq.(51) results in

$$
\Delta T ^ { \prime } = \frac { e _ { 1 1 } L } { 2 a \pi } \left( \sin \left( \frac { a \pi ( \Delta T ^ { \prime } + 2 L ) } { L } + \phi \right) - \sin \phi \right) \ .
$$

Its leading terms are again given by Eq. (23) because $\Delta T ^ { \prime }$ is much smaller than $L$ ： Obviously, when the dimensionless frequency $a = 1 , 2 , 3 . . .$ ， $\Delta T ^ { \prime } = 0$ ,which means that the detector has zero response.

# 4.Gravitational wave vs swing of end mirror

In the above, only the ideal cases are discussed. Practically， an interferometer will undergo various vibrations. Whether it is possible to distinguish the GW from the swing of the mirrors is an important problem in the detection of GW. In the following, we shall show the difference between the effect of GW and the swing of a mirror.

For simplicity, we consider the case that the mirror $A$ is fixed and the mirror $B$ （204 undergoes a harmonic oscillation $\Re [ A e ^ { - i ( 2 \pi f t + \phi ) } ]$ ，where $f$ is now the frequency of the vibration and $\phi$ is the initial phase of the $B$ 's oscillation when the light leaves the mirror （204号 $A$ .Let $\tau$ be the traveling or propagating time of light for one-way trip when the mirror （204号 $B$ undergoes an oscillation. Then,

$$
2 \tau - 2 L = \Re \left[ 2 \left( A e ^ { - i ( 2 \pi f t + \phi ) } \right) \right] .
$$

Denote the difference of the traveling or propagating time for the light's one-way trip with and without end mirror's swing by $\Delta T$ . We let a photon leaves mirror $A$ at $t = 0$ （204号 and consider the photon with initial phase $\phi$ . Then,in the leading approximation,

$$
\Delta T = \Re [ A e ^ { - i ( 2 \pi f L + \phi ) } ] \ .
$$

$\Delta T = 0$ requires that

$$
\begin{array} { c } { { \Re [ e ^ { - i ( 2 \pi f L + \phi ) } ] = 0 ~ , } } \\ { { 2 \pi f L + \phi = \left( \displaystyle \frac { 1 } { 2 } + n \right) \pi ~ , } } \\ { { f = \displaystyle \frac { n } { 2 L } + \displaystyle \frac { 1 } { 2 L } \left( \displaystyle \frac { 1 } { 2 } - \displaystyle \frac { \phi } { \pi } \right) ~ . } } \end{array}
$$

![](images/0d8933992859b08404c46f48e9b3d3383220778466c1c322c1f8f557c4fec26b.jpg)  
Figure 1. Time difference of photon for a round trip from $A$ to $B$ and back to $A$ as a function of frequency of GW. Parameters are chosen as $t _ { 0 } = 0$ ， $c = 3 \times 1 0 ^ { 8 } \mathrm { m / s }$ （204号 $e _ { 1 1 } = 1 0 ^ { - 2 0 }$ and $L = 4 0 0 0 \mathrm { m }$ . The time difference also depends on the initial phase of GW. The different color curves represent the different initial phases.

Obviously, the initial phase of the mirror's swing will influence the difference of the traveling time.Since a continuous laser is used， the initial phases are uniformly distributed, equivalently. In other words, no matter what frequency the mirror $B$ swings at, there are always some photons who can ‘feel’ the swing. In contrast, the photons cannot ‘feel’ the GW with frequency f = ·

Figure. 1 presents the plot of $\Delta T ^ { \prime }$ due to a GW, given by Eq. (23). (The parameters are chosen as $e _ { 1 1 } = 1 0 ^ { - 2 0 }$ and $L = 4 0 0 0 \mathrm { m }$ .） The different color denotes the different initialphase $\phi$ ofG.Ithe $\begin{array} { r } { \phi = 0 , \frac { \pi } { 4 } , \frac { \pi } { 2 } , \frac { 3 \pi } { 4 } , \pi , \frac { 5 \pi } { 4 } , \frac { 3 \pi } { 2 } } \end{array}$ ， and $\frac { 7 \pi } { 4 }$ ,respectively. From the figure, we can see that the time difference of photon motions always vanishes when the frequency of a GW is $\scriptstyle { \frac { \prime \imath } { 2 L } }$ .It means that a photon spends the same time to travel for a round trip in the background of specific GW with frequency $\scriptstyle { \frac { \prime \imath } { 2 L } }$ as in a flat space-time. From Figure.1， we can also see that the initial phase of GW affects the readout in the measurement of GW. The envelop has the form of sinc $\textstyle x = { \frac { \sin x } { x } }$ ：

Figure.2 shows the dependence of time difference of photon motions on the initial phase of GW for specific frequencies. It should be noticed that the curve corresponding with $\begin{array} { r } { f = \frac { 1 } { 2 L } } \end{array}$ (i.e. $a = 1$ ） coincides with the abscissa axis exactly. It means that the photon cannot‘fel’ the GW with $\begin{array} { r } { f = \frac { 1 } { 2 L } } \end{array}$ no matter what theinitialphase is.

In the case of the mirror's swing, the time difference of photon motions is

$$
\Delta T = A \cos { ( 2 \pi f L + \phi ) } .
$$

We plot the frequency dependence of the time difference of photon motions caused by the mirror's swing in Figure.3. Form the picture， we can see that the responses of the interferometer to different frequencies are almost the same. In this case, the time difference of photon motions also depends on the initial phase when this photon leaves the mirror $A$ . The initial phase dependence is shown in Figure.4.

![](images/a401f4c61270872b52695abbcb5396f8432a2443293d3db60bdabe0c0bbe587a.jpg)  
Figure 2. The initial phase dependence of the measurement for GW. The frequency of GW takes as $\begin{array} { r } { f = \frac { a } { 2 L } } \end{array}$ , and a = 0.4,0.6,0.8,1.0,1.2,1.4,1.6.

![](images/522351642929f3cbd4264dd2f8461435bd9f5bc5bde4268c03f3363c4a463f74.jpg)  
Figure 3. Frequency dependence of the time difference of photon motions caused by the mirror's vibration.Parameters are taken as $L = 4 0 0 0 \mathrm { m }$ ， $c = 3 \times 1 0 ^ { 8 } \mathrm { m / s }$ ， $A =$ $4 \times 1 0 ^ { - 1 7 } \mathrm { m }$ ,gainFosf $\begin{array} { r } { \phi = 0 , \frac { \pi } { 4 } , \frac { \pi } { 2 } , \frac { 3 \pi } { 4 } , \pi , \frac { 5 \pi } { 4 } , \frac { 3 \pi } { 2 } , \frac { 7 \pi } { 4 } } \end{array}$ ， are depicted in different colors.

![](images/563010c5b8e86fd28fd26539869d6edc7f38c1f76c8662398c10dd918acaad18.jpg)  
Figure 4. Initial phase dependence of the detector's response. Parameters are taken as $L = 4 0 0 0 \mathrm { m }$ ， $c = 3 \times 1 0 ^ { 8 } \mathrm { m / s }$ ， $A = 4 \times 1 0 ^ { - 1 7 } m$ . The different vibration frequencies are depicted in different colors.

# 5.Conclusions and remarks

In this paper, the photon motions in the background of GW are re-analyzed in both geometrical and wave optics. In geometrical optics, the path of photons in 3-dimensional space is obtained by using the Fermat principle. The geodesic equations are re-produced and the photon paths are just the null geodesics in general relativity. The proper distance between the two mirrors and thus the traveling time that photons move inbetween change with GW. In wave optics, the deformed Maxwell equations and thus the wave equations for electric felds are presented. The wave equations show that the coordinate speed $\boldsymbol { v } ( t )$ of an electromagnetic wave moving between the two mirrors is modified by GW. The two methods give the exactly same equation (23) for the time difference influenced by GW.

Both GW and the mirror swings result in the variations of the proper distance between the two mirrors. However, the characteristics of the variations are different. For a gravitational wave, the amplitude of $\Delta T ^ { \prime }$ varies with the frequency of the GW, which is given by the envelop in Figure. 1. The property of the envelope has been reported in literature (see, for example,[6],[7],[8] etc.). For the mirror swing, however, the amplitude of $\Delta T$ is independent of the frequency of swings. The difference can be easily seen from the figures. The reason of the difference is as follows. A swinging mirror only affects the reflecting point of light, but does not affect the propagation of light in the arm. On the contrary, a GW affects the propagation of light in the arm everywhere. Therefore, the swinging mirror cannot mimic a gravitational wave very well, which is used in the previous studies on the instruments and calibration [8],[9],[10],[11],[12], [13],[14].

The above discussions are just for the motion of photons in a single arm. All the discussions are also valid for the motion of photons in the other arm. The only difference is that the phase variation in the two arms have different polarity due to the quadruple nature of the GW. The total effect should be the sum for two arms. If the time differences in both arms vanish for some specific frequency of GWs, then the detector has no response to these GWs. For the swinging mirrors, the detector may provide zero-response only when the two arms vibrates in synchronization.

Finally, the time difference in a Michelson interferometer is discussed in the present paper. The detectors, like LIGO, Virgo,are all Michelson-Pabry-Perot interferometers. The analysis for a Michelson-Pabry-Pérot interferometer will be discussed elsewhere.

# Acknowledgments

The project is supported by National Natural Science Foundation of China under the grants 11275207, 11375203,11690022 and 11675182 and by the Strategic Priority Research Program of the Chinese Academy of Sciences Multi-waveband Gravitational Wave Universe (Grant No. XDB23040000).

# References

[1] B.P. Abbott, et al, 20l6 Observation of gravitational waves from a binary black hole merger, Phys.Rev. Lett.116 061102   
[2] B.P. Abbott,et al, 2016 GW151226: Observation of Gravitational Waves from a 22-Solar-Mass Binary Black Hole Coalescence Phys.Rev.Lett.116 241103   
[3]E.D.Black and R.N. Gutenkunst,2003 An Introduction to Signal Extration in Interferometric Gravitational Wave Detectors,Am. J. Phys. 71 365   
[4] B.Allen, W. G.Anderson,P.R.Brady, D.A. Brown,and J.D.E. Creighton, 2012 FINDCHIRP: An algorithm for detection of gravitational waves from inspiraling compact binaries Phys. Rev. D 85 122006.   
[5] J.Aasi et al., 2015 Advanced LIGO, Class. Quant. Grav.32 074001   
[6] Z. Chang, C.-G. Huang, Z.-C. Zhao, 2016 Propagation effct of gravitational wave on detector response. Sci. China-Phys.Mech.Astro.59 100421   
[7] Z. Chang, C.-G. Huang, Z.-C. Zhao, 2017 Is GW151226 a really signal of gravitational wave? Chin. Phys. C 41 DO1:10.1088/1674-1137/41/2/025001.   
[8] J.Mizuno,A. Ridiger，R. Schiling,W. Winkler， K. Danzmann，1997 Frequency response of Michelson- and Sagnac-based interferometers Optics Commun.138 383-393.   
[9] M.Rakhmanov,R. L. Savage, D.H. Reitze, et al. 2002 Dynamic resonance of light in FabryCPerot cavities[J].Phys.Lett.A 305 239-244   
[10] J. Markowitz, R. Savage,and P. Schwinberg. 2003 Development of a Readout Scheme for High Frequency Gravitational Waves.LIGO Technical Document To30186-00-W   
[11] M.Rakhmanov,F.Bondu,O.Debieu,et al. 2004 Characterization of the LIGO 4 km FabryCPerot cavities via their high-frequency dynamic responses to length and laser frequency variations[J]. Class. Quantum Grav. 21 S487   
[12] M. Rakhmanov, 2005 Response of test masses to gravitational waves in the local Lorentz gauge Phys. Rev. D 71 084003   
[13] M.Rakhmanov, J. D.Romano,and J. T. Whelan, 2008 High-frequency corrections to the detector response and their effect on searches for gravitational waves. Class. Quantum Grav. 25 184017   
[14] B.P. Abbott, LIGO Scientific Collaboration, 2016 Calibration of the Advanced LIGO detectors for the discovery of the binary black-hole merger GW150914[J] arXivu preprint (arXiv:1602.03845)   
[15] J.Mizuno,1995 Comparison of optical configurations for laser-interferomettric gravitational-wave detectors Doctoral dissertation, Hannover University.   
[16]L.D.Landau and E.M.Lifshitz,The classical theory of felds,198O 4 edition，ButterworthHeinemann, Amsterdam.   
[17] K. S. Thorne,1987 Gravitational radiation in Three hundred years of gravitation,ed by S.W. Hawking and W. Israel, Cambridge University Press, Cambridge.