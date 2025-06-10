# Characterization of phase transition in Heisenberg mixtures from density functional theory

L. S.Li \* and X. S. Chen † Institute of Theoretical Physics，Chinese Academy of Sciences，P.O.Box 2735， Beijing 10080， China

The phase transition of hard-sphere Heisenberg and Neutral Hard spheres mixture fluids has been investigated with the density functional theory in mean-field approximation (MF).The matrix of second derivatives of the grand canonical potential $\Omega$ with respect to the total density,concentration, and the magnetization fluctuations has been investigated and diagonalized.The zero of the smallest eigenvalue $\lambda _ { s }$ signalizes the phase instability and the related eigenvector $\mathbf { x } _ { s }$ characterizes this phase transition.We find a Curie line where the order parameter is pure magnetization and a mixed spinodal where the order parameter is a mixture of total density,concentration,and magnetization. Although in the fixed total number density or temperature sections the obtained spinodal diagrams are quite similar topology,the predominant phase instabilities are considerable diferent by analyzing $\mathbf { x } _ { s }$ in density-concentration-magnetization fluctuations space. Furthermore the spinodal diagrams in the different fixed concentration are topologically different.

PACS numbers:05.70.Jk,61.20.Gy,64.60.Cn,61.25.Em

# I.INTRODUCTION

The study of the properties of the Heisenberg liquid emerged as one of the fascinating theoretical problems since it was stimulated by MC simulations of Heisenberg fluid[1],which strongly hint that the ferromagnetic transition of the Heisenberg fluid challenge the traditional viewpoint to ferromagnetic transition theory. Nijmeijer et al. found the value of critical exponents of the Heisenberg and Ising fluid[2] differ from the expected results for the lattice models. They suggested that the the effective exponents is related to Fisher renormalization with the fixed density. Recently Mryglod et al. simulated the larger Heisenberg fluid system and obtained the critical exponents from standard finite size scaling theory[3]. They argued the effective exponents is corrected by Fisher renormalization when a thermdynamics system under a constraint[4].Although the spin liquids exhibit interesting phase transition by simulations, the formal theory of critical phenomena has not solved this problem completely.In fact the spin fluids have a complex phase behavior as the coupling between the additional spin degrees and spatial coordinates. Besides ordinary gas-liquid phase,such a spin fluid model displays paramagnetic gas-ferromagnetic Liquid phase transitions,critical end point，and tri-critical point. Many models have been proposed such as the discrete Ising [2,5,6,7, 8],continuous XY [9,10] and Heisenberg fluid [1，3，11，12，13，14，15，16，17]. Tavares et al.using both a mean field (MF) and a more refined modified mean field (MMF) density functional theory have found in some regime mixed first-order transition，namely a condensation-ordering transition[12] in the pure Heisenberg fluid. Both theoretical works and MC results showed that the frst-order transition (i.e.，an isotropic vapor phase and a ferromagnetic liquid phase) are the mixed transition of the ordering fluctuations and density fluctuations and Li et al. investigated it using the method proposed by Chen et al. [18,19] to characterize the mixed phase transition[17].

The phase diagrams of binary spin mixture calculated by the mean field theory and Monte Carlo simulation show many fascinating phase behaviors which come from competition among magnetic, condensation and concentration fluctuations[2O]. So far the microscopically motivated studies try to comprehend the picture of phase behavior of these fluids.However,as we shall demonstrate here,knowledge of the complete phase diagram is essential but not enough.In order to understand the existence of the mixed transition,we have to classify the phase transition characters. So our purpose in the present work is to characterize the phase transition along orderingcondensation-demixing transition line.Therefore,we investigate a mixture ofHeisenberg hard spheres and Neutral hard spheres (HHNH)using the method[18,19] to characterize phase transition. We address these questions using density functional theory in the so-called simple mean-field theory. As a result, the phase transitions of different character take place in this system,as studies of the phase diagram and of the associated critical phenomena have been shown.

# II. MODEL

In this paper we consider a binary mixture fluid of Heisenberg Hard-Sphere (HHS) and NeutralHard-Sphere (NHS)with equal diameters $\sigma$ . The pair potential for two of such particles at positions $\mathbf { r } _ { 1 }$ and $\mathbf { r } _ { 2 }$ is given by

$$
u _ { a b } ( { \bf r } _ { 1 } , \omega _ { 1 } , { \bf r } _ { 2 } , \omega _ { 2 } ) = \Delta ( a b ) u ^ { s s } ( r , \omega _ { 1 } , \omega _ { 2 } ) + u ^ { h s } ( r ) ,
$$

where $r = | \mathbf { r } _ { 1 } - \mathbf { r } _ { 2 } |$ is the distance between particles at positions $\mathbf { r } _ { 1 }$ and $\mathbf { r } _ { 2 }$ and $\omega _ { i } = ( \theta _ { i } , \phi _ { i } )$ are the orientations of particles with $0 \leq \theta _ { i } \leq \pi$ and $0 \leq \phi _ { i } \leq 2 \pi$ . The subscripts $a$ and $b$ denote the components in fluid considered $\mathrm { \{ a ( b ) = H H S , N _ { - } } $ HS},andwedefine

$$
\Delta ( a b ) = \left\{ \begin{array} { l l } { { 1 , } } & { { a = b = H H S , } } \\ { { 0 , } } & { { a = b = N H S , \ a \neq b , } } \end{array} \right.
$$

which means all the particles have a diameter yielding a repulsive hard sphere potential $u ^ { h s }$ and only the HHS particles attract each other via a Heisenberg potential （204号 $u ^ { s s }$ .The repulsive hard sphere interaction and the spin part are given by

$$
u ^ { h s } ( r ) = \left\{ \begin{array} { l l } { { + \infty , } } & { { r \leq \sigma , } } \\ { { 0 , } } & { { r > \sigma . } } \end{array} \right.
$$

and

$$
u ^ { s s } ( r , \omega _ { 1 } , \omega _ { 2 } ) = \left\{ \begin{array} { c c } { 0 , } & { r \leq \sigma , } \\ { - J ( r ) \mathbf { s } _ { 1 } \cdot \mathbf { s } _ { 2 } , } & { \sigma < r \leq r _ { c } } \\ { 0 , } & { r > r _ { c } . } \end{array} \right.
$$

where

$$
J ( r ) = \epsilon \frac { e ^ { - z ( r / \sigma - 1 ) } } { r / \sigma } ,
$$

here ${ \bf s } _ { i }$ is a unit vector ( $| { \bf s } _ { i } | = 1$ ）in the direction of the spin moment with

$$
{ \bf s } _ { 1 } \cdot { \bf s } _ { 2 } = \cos ( \omega _ { 1 } , \omega _ { 2 } ) = \cos \theta _ { 1 } \cos \theta _ { 2 } + \sin \theta _ { 1 } \sin \theta _ { 2 } \cos ( \phi _ { 1 } - \phi _ { 2 } ) .
$$

In this paper we set the cutoff distance of the Yukawa potential $r _ { c }$ for $r _ { c } = \infty$ and the dimensionless parameter （204号 $z$ for $z = 1$ . To have ferromagnetic phase favoring parallel orientations the coupling constant $\epsilon$ here is taken to be positive.

# III. DENSITYFUNCTIONAL AND MEAN-FIELDAPPROXIMATION

The grand potential free energy $\Omega$ of a nonuniform spin liquid mixtures is the minimum of the functional,

$$
\begin{array} { l } { { \displaystyle \Omega [ \rho _ { H } ( { \bf r } , \omega ) , \rho _ { N } ( { \bf r } ) , V , T ] = F [ \rho _ { H } ( { \bf r } , \omega ) , \rho _ { N } ( { \bf r } ) ] } } \\ { ~ + ~ \int d \omega d { \bf r } \rho _ { H } ( { \bf r } , \omega ) ( V _ { e x t } ^ { H } ( { \bf r } , \omega ) - \mu _ { H } ) } \\ { ~ + ~ \int d { \bf r } \rho _ { N } ( { \bf r } ) ( V _ { e x t } ^ { N } ( { \bf r } ) - \mu _ { N } ) , } \end{array}
$$

where index $\mathrm { H }$ and N means HHS and NHS, respectively. （204号 $\mu$ is the chemical potential and the intrinsic Helmholtz free energy of the inhomogeneous fluid $F [ \rho _ { H } ( \mathbf { r } , \omega ) , \rho _ { N } ( \mathbf { r } ) ]$

is a unique functional of the densities $\rho _ { H } ( { \bf r } , \omega )$ and $\rho _ { N } ( \mathbf { r } )$ 业 The Helmholtz free energy can be written as [23]

$$
\begin{array} { l } { { \displaystyle F [ \rho _ { H } ( { \bf r } , \omega ) , \rho _ { N } ( { \bf r } ) ] = F ^ { h s } [ \rho _ { H } ( { \bf r } , \omega ) , \rho _ { N } ( { \bf r } ) ] } } \\ { { \displaystyle + \left. \frac { 1 } { 2 } \int _ { 0 } ^ { 1 } d \lambda \int d { \bf r } _ { 1 } d { \bf r } _ { 2 } d \omega _ { 1 } d \omega _ { 2 } g ( { \bf r } _ { 1 } , \omega _ { 1 } , { \bf r } _ { 2 } , \omega _ { 2 } ; \lambda ) \right. } } \\ { { \displaystyle \left. \rho _ { H } ( { \bf r } _ { 1 } , \omega _ { 1 } ) u ^ { s s } ( r , \omega _ { 1 } , \omega _ { 2 } ) \rho _ { H } ( { \bf r } _ { 2 } , \omega _ { 2 } ) \right. } } \end{array}
$$

where $F ^ { h s } [ \rho _ { H } ( \mathbf { r } , \omega ) , \rho _ { N } ( \mathbf { r } ) ]$ is the Helmholtz free energy of Hard-Sphere(HS) mixturessystem and $g ( \mathbf { r _ { 1 } } , \omega _ { 1 } , \mathbf { r } _ { 2 } , \omega _ { 2 } ; \lambda )$ is the pair distribution function in a system which the particles interact via a pairwise potential

$$
u _ { \lambda } ( r , \omega _ { 1 } , \omega _ { 2 } ) = h ^ { h s } ( r ) + \lambda u ^ { s s } ( r , \omega _ { 1 } , \omega _ { 2 } ) .
$$

The density of Heisenberg particle $\rho _ { H } ( { \bf r } , \omega )$ can be split into the number density $\rho _ { H } ( \mathbf { r } )$ and a normalized factor （204号 $O _ { H } ( { \bf r } , \omega )$ as

$$
\rho _ { H } ( \mathbf { r } , \omega ) = \rho _ { H } ( \mathbf { r } ) O _ { H } ( \mathbf { r } , \omega )
$$

where

$$
\int d \omega O _ { H } ( \mathbf { r } , \omega ) = 1
$$

In the local density approximation the Helmholtz free energy of HS mixtures system[22]

$$
\begin{array} { l } { { \displaystyle F ^ { h s } ~ = ~ \frac { 1 } { \beta } \int d \mathbf { r } d \omega \rho _ { H } ( \mathbf { r } , \omega ) \left[ \ln ( \Lambda _ { H } ^ { 3 } 4 \pi \rho _ { H } ( \mathbf { r } , \omega ) ) - 1 \right] } } \\ { ~ + ~ \frac { 1 } { \beta } \int d \mathbf { r } \rho _ { N } ( \mathbf { r } ) \left[ \ln ( \Lambda _ { N } ^ { 3 } 4 \pi \rho _ { N } ( \mathbf { r } ) ) - 1 \right] } \\ { ~ + ~ \frac { 1 } { \beta } \int d \mathbf { r } \rho ( \mathbf { r } ) \frac { 4 \eta ( \mathbf { r } ) - 3 \eta ( \mathbf { r } ) ^ { 2 } } { ( 1 - \eta ( \mathbf { r } ) ) ^ { 2 } } } \end{array}
$$

where $\beta = 1 / k _ { B } T$ is the inverse temperature, $\Lambda _ { a }$ is the thermal de Broglie wavelength of species $a$ , the total density $\rho ( \mathbf { r } ) = \rho _ { H } ( \mathbf { r } ) + \rho _ { N } ( \mathbf { r } )$ and $\eta ( { \bf r } ) = ( \pi / 6 ) \rho ( { \bf r } ) \sigma ^ { 3 }$ is the packing fraction.

In the mean field approximation where the pair distribution function takes its large-distance limit $g ( \mathbf { r _ { 1 } } , \omega _ { 1 } , \mathbf { r } _ { 2 } , \omega _ { 2 } ; \lambda ) = 1$ [12],the part of the free energy related to the spin-spin interactions in Eq.(9) becomes

$$
{ \cal F } _ { M F } ^ { s s } = \frac { 1 } { 2 } \int d { \bf r } _ { 1 } d { \bf r } _ { 2 } d \omega _ { 1 } d \omega _ { 2 } \rho _ { H } ( { \bf r _ { 1 } } , \omega _ { 1 } ) u ^ { s s } ( r , \omega _ { 1 } , \omega _ { 2 } ) \rho _ { H } ( { \bf r } _ { 2 } , \omega _ { 2 } 0 ] 1 3 )
$$

After the decomposition $\rho _ { H } ( { \bf r } , \omega ) = \rho _ { H } ( { \bf r } ) O _ { H } ( { \bf r } , \omega )$ the minimum conditionofthe functional （204号 $\Omega [ \rho _ { H } ( \mathbf { r } , \omega ) , \rho _ { N } ( \mathbf { r } ) ]$ is equivalent to the simultaneous

minimization of the grand canonical functional with respect to the number densities

$$
\begin{array} { r } { \frac { \delta \Omega [ \rho _ { H } ( \mathbf { r } , \omega ) , \rho _ { N } ( \mathbf { r } ) , T , \mu ] } { \delta \rho _ { H } ( \mathbf { r } ) } = 0 , } \\ { \frac { \delta \Omega [ \rho _ { H } ( \mathbf { r } , \omega ) , \rho _ { N } ( \mathbf { r } ) , T , \mu ] } { \delta \rho _ { N } ( \mathbf { r } ) } = 0 , } \end{array}
$$

and the orientational configuration

$$
\begin{array} { r } { \frac { \delta \Omega [ \rho _ { H } ( \mathbf { r } , \omega ) , \rho _ { N } ( \mathbf { r } ) , T , \mu ] } { \delta O _ { H } ( \mathbf { r } , \omega ) } = 0 . } \end{array}
$$

In the absence of the external feld $( V _ { e x t } ^ { H } ( { \bf r } , \omega ) =$ （204号 $V _ { e x t } ^ { N } ( \mathbf { r } ) ~ = ~ 0 \ :$ ） the system is homogeneous in position, but it could be ordered in orientation.So we have $\rho _ { H } ( \mathbf { r } ) = \rho _ { H }$ ， $\rho _ { N } ( \mathbf { r } ) = \rho _ { N }$ and $O _ { H } ( \mathbf { r } , \omega ) = O _ { H } ( \omega )$ .In the mean field approximation we obtain the bulk expression of the grand-canonical free energy density

with the average magnetization $\begin{array} { r } { \xi = \int d \omega O _ { H } ( \theta ) \cos \theta } \end{array}$ determined by

$$
\xi = \coth ( \beta \rho _ { H } J ^ { i n t } \xi ) - \frac { 1 } { \beta \rho _ { H } J ^ { i n t } \xi } .
$$

Then the grand function free energy density in an equilibrium state is expressed by

$$
\begin{array} { c } { { \displaystyle \frac { 1 } { V } \Omega _ { M F } [ O _ { H } ( \theta ) , \rho _ { H } , \rho _ { N } , T , \mu ] = f _ { C S } ^ { h s } ( \rho _ { H } , \rho _ { N } ) } } \\ { { + } } \\ { { \displaystyle \frac { 1 } { 2 } J ^ { i n t } \rho _ { H } ^ { 2 } \xi ^ { 2 } + \frac { \rho _ { H } } { \beta } k ( x ) - \mu _ { H } \rho _ { H } - \mu _ { N } \rho _ { N } . } } \end{array}
$$

# IV. THE SPINODAL OF HEISENBERG HARD MIXTURELIQUIDS

$$
\begin{array} { c } { { \displaystyle \frac { 1 } { V } \Omega _ { M F } [ O _ { H } ( \omega ) , \rho _ { H } , \rho _ { N } , T , \mu ] = f _ { C S } ^ { h s } ( \rho _ { H } , \rho _ { N } ) } } \\ { { - \displaystyle \frac { 1 } { 2 } J ^ { i n t } \rho _ { H } ^ { 2 } | \bar { \bf s } | ^ { 2 } + \displaystyle \frac { \rho _ { H } } { \beta } \int d \omega O _ { H } ( \omega ) \ln [ 4 \pi O _ { H } ( \omega ) ] - \mu _ { H } \rho _ { H } - \mu _ { N } \rho _ { N } , } } \end{array}
$$

here the Helmholtz free energy density of hard-sphere system $f _ { C S } ^ { h s } ( \rho _ { H } , \rho _ { N } )$ is given by Carnahan and Starling [22]

$$
\begin{array} { l } { { f _ { C S } ^ { h s } ( \rho _ { H } , \rho _ { N } ) = \frac { \rho _ { H } } { \beta } \left[ \ln ( \rho _ { H } \Lambda _ { H } ^ { 3 } ) - 1 \right] } } \\ { { \ } } \\ { { + \frac { \rho _ { N } } { \beta } \left[ \ln ( \rho _ { N } \Lambda _ { N } ^ { 3 } ) - 1 \right] + \frac { \rho } { \beta } \frac { 4 \eta - 3 \eta ^ { 2 } } { ( 1 - \eta ) ^ { 2 } } } } \end{array}
$$

and

$$
\begin{array} { r } { \bar { \bf s } = \displaystyle \int d \omega O _ { H } ( \omega ) { \bf s } ( \omega ) , \quad } \\ { J ^ { i n t } = \displaystyle \int _ { \sigma } ^ { \infty } d r \displaystyle 4 \pi r ^ { 2 } J ( r ) = 8 \pi \varepsilon \sigma ^ { 3 } . \quad } \end{array}
$$

From the equilibrium condition(15) and the mean field grand-canonical free energy (16) we can obtain the equilibrium orientational distribution function

$$
O _ { H } ( \omega ) = \frac { e ^ { \beta \rho _ { H } J ^ { i n t } { \bf s \cdot \bar { s } } } } { \int d \omega e ^ { \beta \rho _ { H } J ^ { i n t } { \bf s \cdot \bar { s } } } } .
$$

![](images/d878806c0f0990a5229840f8f20206573177f0c50dcdc9d50c533cb3ae4ff3ff.jpg)  
FIG.1:(Color Online）A schematic plot of the eigenvector which characterizes the phase transition. In the space $( \delta \rho / \rho , \delta C , \delta \xi )$ the eigenvector can be described by angles $\phi$ and $\theta$ which is in the range $\theta ~ \in ~ ( - 9 0 ^ { 0 } , 9 0 ^ { 0 } ]$ and $\phi \in \mathbf { \Xi }$ （204号 $( - 1 8 0 ^ { 0 } , 1 8 0 ^ { 0 } ]$ .When $\theta \ : = \ : 0$ the phase transition is a pure ferromagnetic phase transition．The phase transition is pure condensation when $\theta = 9 0 ^ { 0 }$ and $\phi = 0$ .The phase transition is pure demixing when $\theta = 9 0 ^ { 0 }$ and $\phi = 9 0 ^ { 0 }$ ：

Here we restrict to the case $O _ { H } ( \omega ) = O _ { H } ( \theta )$ and have

$$
O _ { H } ( \omega ) = O _ { H } ( \theta ) = \frac { 1 } { 4 \pi } e ^ { k ( x ) + x \cos \theta } ,
$$

where

$$
\begin{array} { r l } & { k ( x ) = \ln ( x / \sinh x ) , } \\ & { x = \beta \rho _ { H } J ^ { i n t } \xi , } \end{array}
$$

At a stable equilibrium state the grand potential has its minimum and its variation with respect to the changes of number densities and magnetization should be positive [18],

$$
\begin{array} { l } { { \displaystyle \delta \Omega / V = \frac { 1 } { 2 V } \biggl [ \frac { \partial ^ { 2 } \Omega } { \partial \rho _ { H } ^ { 2 } } ( \delta \rho _ { H } ) ^ { 2 } + \frac { \partial ^ { 2 } \Omega } { \partial \xi ^ { 2 } } ( \delta \xi ) ^ { 2 } } } \\ { { \displaystyle ~ + ~ \frac { \partial ^ { 2 } \Omega } { \partial \rho _ { N } ^ { 2 } } ( \delta \rho _ { N } ) ^ { 2 } + 2 \frac { \partial ^ { 2 } \Omega } { \partial \rho _ { H } \partial \xi } \delta \rho _ { H } \delta \xi } } \\ { { \displaystyle ~ + ~ 2 \frac { \partial ^ { 2 } \Omega } { \partial \rho _ { N } \partial \xi } \delta \rho _ { N } \delta \xi + 2 \frac { \partial ^ { 2 } \Omega } { \partial \rho _ { H } \rho _ { N } \xi } \delta \rho _ { H } \delta \rho _ { N } \biggr ] > 0 . } } \end{array}
$$

The variation of the grand potential can be rewritten

in a matrix form

$$
\delta \Omega / V = \frac { 1 } { 2 } \left( \begin{array} { l l l } { \delta \rho _ { H } } & { \delta \rho _ { N } } & { \delta \xi } \end{array} \right) \left( \begin{array} { l l l } { M _ { H H } } & { M _ { H N } } & { M _ { H \xi } } \\ { M _ { N H } } & { M _ { N N } } & { M _ { N \xi } } \\ { M _ { \xi H } } & { M _ { \xi N } } & { M _ { \xi \xi } } \end{array} \right) \left( \begin{array} { l } { \delta \rho _ { H } } \\ { \delta \rho _ { H } } \end{array} \right) \mathrm { ~ l o r ~ } \mathsf { h e a r ~ z e r o ~ a n d ~ } \phi
$$

We want to understand the character of the phase transition,which combinations of condensation,phase separation,and ferromagnetic order fluctuations are leading to the phase transition.For the following analysis it is more convenient to rewrite the matrix in terms of the total density $\rho = \rho _ { H } + \rho _ { N }$ ,the concentration $C = \rho _ { H } / \rho$ . and the ferromagnetic ordering, $\xi$ . We reexpress the variation of the grand potential in new fluctuations space $( \delta \rho , \delta C , \delta \xi )$ （204号

$$
\delta \Omega / V = \frac { 1 } { 2 } \left( \begin{array} { c } { { \delta \rho / \rho } } \\ { { \delta \rho / \rho } } \end{array} \delta C \delta \xi \right) \left( \begin{array} { c c c } { { M _ { \rho \rho } } } & { { M _ { \rho C } } } & { { M _ { \rho \xi } } } \\ { { M _ { C \rho } } } & { { M _ { C C } } } & { { M _ { C \xi } } } \\ { { M _ { \xi \rho } } } & { { M _ { \xi C } } } & { { M _ { \xi \xi } } } \end{array} \right) \left( \begin{array} { c } { { \delta \rho / \rho } } \\ { { \delta C } } \\ { { \delta \xi } } \end{array} \right) ^ { \mathrm { s } } .
$$

where total one particle density fluctuations $\delta \rho \quad = \quad$ （20 $\delta \rho _ { H } + \delta \rho _ { N }$ ，the demixing fluctuations $\begin{array} { r } { \delta C ~ = ~ \delta \frac { \rho _ { H } } { \rho } ~ = ~ } \end{array}$ $\rho ^ { - 2 } [ \rho _ { N } \delta \rho _ { H } - \rho _ { H } \delta \rho _ { N } ]$ . And the matrix $\mathbf { M }$ is defined by

$$
\mathbf { M } = \left( \begin{array} { l l l } { M _ { \rho \rho } } & { M _ { \rho C } } & { M _ { \rho \xi } } \\ { M _ { C \rho } } & { M _ { C C } } & { M _ { C \xi } } \\ { M _ { \xi \rho } } & { M _ { \xi C } } & { M _ { \xi \xi } } \end{array} \right)
$$

which has three eigenvalues $\lambda _ { 1 } , \lambda _ { 2 } , \lambda _ { 3 }$ with the corresponding eigenvectors $\mathbf { x } _ { 1 } , \mathbf { x } _ { 2 } , \mathbf { x } _ { 3 }$ ．The positive eigenvalues $\lambda _ { 1 }$ ， $\lambda _ { 2 }$ ，and $\lambda _ { 3 }$ of a stable state guarantee that the grand free energy will increase with respect to any variation of total number density, magnetization,and concentration. If the smallest eigenvalue $\lambda _ { s }$ vanishes, the system can deviate away from the original state without any increase of the grand free energy and becomes unstable, which is a phase transition. The eigenvector $\mathbf { x } _ { s }$ corresponding to the zero eigenvalue characterizes this phase transition precisely [18,19] and $\mathbf { x } _ { s }$ is the order parameter.Therefore,We investigate the direction of eigenvector $\mathbf { x } _ { s }$ in the $( \delta \rho , \delta C , \delta \xi )$ fluctuations space,which can characterize the type of phase transitions.

In Fig.1 we show a schematic plot of the Euclidean eigenvector $\mathbf { x } _ { s }$ in the space $( \delta \rho / \rho , \delta C , \delta \xi )$ with unit vectors $( \mathbf { e } _ { x } , \mathbf { e } _ { y } , \mathbf { e } _ { z } )$ of the Cartesian system. We normalize the eigenvector $| { \bf x } _ { s } | = 1$ of the zero eigenvalue,and calculate the angles $\theta$ and $\phi$ of $\mathbf { x } _ { s }$ in the spherical coordinate

$$
\begin{array} { r l } & { \theta = \operatorname { a r c c o s } ( \mathbf { x } _ { s } \cdot \mathbf { e } _ { z } ) , } \\ & { \phi = \operatorname { a r c c o s } \left( \frac { \mathbf { x } _ { s } \cdot \mathbf { e } _ { x } } { \sqrt { ( 1 - ( \mathbf { x } _ { s } \cdot \mathbf { e } _ { z } ) ^ { 2 } ) } } \right) . } \end{array}
$$

The angle $\phi$ and $\theta$ describe the portion of the total number density, the concentration and the magnetiza tion in the phase transition and is defined in the range $- 9 0 ^ { 0 } < \theta \leq 9 0 ^ { 0 } , - 1 8 0 ^ { 0 } < \phi \leq 1 8 0 ^ { 0 }$ .In general, the phase transition of the Heisenberg fluid is a combination

of condensation and ferromagnetic phase transition. If ferromagnetic phase transition. $\phi \neq 0$ ，we have a ferromagnetic n accompanied by a weak confuctuations.If $\theta \ : = \ : 9 0 ^ { 0 }$ and   
$\phi = 0$ ，we have then a pure gas-liquid phase transition.   
For $\theta \ : = \ : 9 0 ^ { 0 }$ and $\phi$ near zero,we have a condensation   
dominant phase transition accompanied by a weak phase   
separation and ferromagnetic phase transition.If $\theta = 9 0 ^ { 0 }$   
and $\phi = 9 0 ^ { 0 }$ , we have then a pure demixing phase tran  
sition. For $\theta = 9 0 ^ { 0 }$ and $\phi$ near $9 0 ^ { 0 }$ ，we have a demix  
ing dominant phase transition accompanied by a weak   
ordering and condensation phase transition. Now we in  
vestigate the phase behavior of the binary fluid by deter  
mining the border of stable region from the zero point of   
the smallest eigenvalue $\mathbf { x } _ { s }$ .What we will obtain is the o-called spinodal.

# V. RESULTS AND DISCUSSION

![](images/c4c6dd2cc80ccf95dce0af5a2954b0b9b2ecc3c558b4a3e885f7c57b1bd89ef9.jpg)  
FIG.2:(Color Online）Plot of the eigenvalues $\lambda _ { 1 }$ ， $\lambda _ { 2 }$ ,and $\lambda _ { 3 }$ ，vS $T$ for the Heisenberg Hard sphere mixture fluid at the density $\rho ^ { * } = 0 . 8$ and the concentration $C = 0 . 8$ .The Curie point and the mixed spinodal point here are on the Curier line and the mixed spinodal of Fig. 3(f).

In Fig.2 the eigenvalues $\lambda _ { 1 }$ ， $\lambda _ { 2 }$ and $\lambda _ { 3 }$ are shown as a function of the reduced temperature $T ^ { * } = 1 / \beta \epsilon$ for the reduced density $\rho ^ { * } = \rho \sigma ^ { 3 } = 0 . 8$ and the concentration $C = 0 . 8$ .The eigenvalues $\lambda _ { 2 }$ and $\lambda _ { 3 }$ always keep to be positive,but the the smallest eigenvalue $\lambda _ { s } ~ = ~ \lambda _ { 1 }$ approaches zero when decreasing or increasing the temperature.The instability at higher temperature is actually on the Curie line where $\theta = 0$ . And the smallest eigenvalue at lower temperature meet the mixed spinodal line where $\theta \ : = \ : 6 2 ^ { 0 }$ and $\phi = 8 0 ^ { 0 }$ .So we have a dominant phase separation accompanied by a weaker ordering and weakest gas-liquid phase transition.With the zero points of $\lambda _ { s }$ for different concentrations $C$ we can get the spin

6 a d 2.4 Curie Line CurieLine   
rneeee IG rergeeeeeg IG FL FL CEP CMixed Spinodal Mixed Spinodal p=0.3 p=0.8 0.80 0.850.90 0.95 1.00 8.40.50.60.70.80.91.0 Concentration Concentration 1.0 1.0 b e 0.8 0.8 0.6 0.6   
u u 0.4 0.4 0.2 p =0.3 0.2 p =0.8 08.80 0.85 0.90 0.95 1.00 0.8.4 0.50.60.70.80.9 1.0 Condensation Condensation 90 90 C 75 p=0.3 75 30 30 d 15 -- 15 Φ p =0.8 88 0.85 0.90 0.95 1.00 84 0.50.60.7 0.80.91.0 Condensation Condensation

pure ferromagnetic.In a more accurate theory the phase transition is not pure ferromagnetic and should be accompanied by the weak condensation and demixing phase transition.

# B. Case: $\xi \neq 0$ ,the total density is fixed

When $\xi \neq 0$ the determinant of the coefficient matrix （204号 $M$ （204号

$$
D e t ~ \left[ \begin{array} { l l l } { M _ { \rho \rho } } & { M _ { \rho C } } & { M _ { \rho \xi } } \\ { M _ { C \rho } } & { M _ { C C } } & { M _ { C \xi } } \\ { M _ { \xi \rho } } & { M _ { \xi C } } & { M _ { \xi \xi } } \end{array} \right] = 0 .
$$

which can be solved numerically. In Fig.3 $( a )$ ，we show the Curie line (Blue Dash Line) and the mixed spinodal (Green SolidLine)of the HHNH mixtures with the fixed density $\rho ^ { * } = 0 . 3$ section.

the magnetization and the angle as a function of concentrations.The phase diagram Will be discussed in de tail and characterized the type of phase transitions in the method[19].

odal phase diagram of the Heisenberg Hard sphere liquid, which is shown in Fig.3.

# A. Case:In the isotropic phases $\xi = 0$ （204号

At the isotropic phase of the Heisenberg fluid, there is no total magnetization and $x = 0$ .In this case we have

$$
\operatorname* { l i m } _ { x  0 } { \frac { \partial ^ { 2 } k ( x ) } { \partial x ^ { 2 } } } = - { \frac { 1 } { 3 } }
$$

For all densities $\rho$ the element $M _ { i j }$ is positive expect the element $M _ { \xi \xi }$ ，which can become zero and $\theta = 0$ corresponds to a pure ferromagnetic phase transition.

In Fig.3 ( $u$ ） we obtain the spinodal phase diagram of the Heisenberg Hard spheres mixture liquid in the constant density in the temperature concentration plane. The mixed spinodal meets the Curie line at the critical endpoint with the concentration $C = 0 . 8 5$ and the reduced temperature $T ^ { * } = 2 . 1 3$ . Below the temperature of the critical endpoint there is a first-order phase transition between isotropic vapor and ferromagnetic liquid. The magnetization $\xi$ along the mixed spinodal is shown in Fig.3(b) by using Eq.(24). The more Heisenberg particles the the liquid have,it show the bigger the magnetization. For the mixed spinodal the phase instability is a combination of condensation,demixing and ferromagnetic phase transition.To characterize the phase instability precisely we investigate the angles $\phi$ and $\theta$ of the eigenvector $\mathbf { x } _ { s }$ （204号 along it shown in Fig.3 $( c )$ ．For concentration near 1.0 the angle $\phi$ is very small and positive and $\theta > 4 5 ^ { 0 }$ ,where the phase instability is predominantly related to the condensation.The positivity of $\phi$ means that an increase of the total number density will be accompanied by a small demixing and ordering. This result is plausible,because the increase of concentration (more Heisenberg particles) will enhances the average attraction of the system which results in more ordering and demixing. The magnetization $\xi$ for the concentration larger than O.95 is larger than 0.5.With the decrease of the concentration the angle $\phi$ increases but $\theta$ decreases continuously. When the system approaches the critical endpoint $C = 0 . 8 5$ ，the angle $\theta$ approaches O.The phase transition at critical endpoint is then a pure ferromagnetic phase transition in the mean field approximation.

From $M _ { \xi \xi } = 0$ we can get the Curie line of the Heisenberg Hard mixture fluids. With the reduced density $\rho ^ { * } = \rho \sigma ^ { 3 }$ and the reduced temperature $T ^ { * } = 1 / \beta \varepsilon$ we can express the Curie line as

$$
T ^ { * } = \frac { 8 \pi } { 3 } \rho ^ { * }
$$

which agrees with the result of Li et al [17] because of the simple mean field approximation. And the meanfield approximation that makes the phase transition be

The spinodal curve and the CEP with $C = 0 . 6 9$ and $T ^ { * } = 2 . 8 9$ at $\rho ^ { * } = 0 . 8$ section is displayed in Fig.3 $( d )$ Corresponding the magnetization in Fig.3 (e) and the angles in Fig.3( $f$ )have a obviousregion $0 . 7 3 5 < C < 0 . 9 6 5$ that $\theta > 4 5 ^ { 0 }$ and $\phi > 4 5 ^ { 0 }$ , in which the phase instability is predominantly related to the demixing phase transition accompanied by the ordering and condensation.By comparing Fig.3(c) with $( f )$ the demixing predominant region disappear in the lower total density section.

0.70 a 90 b FL 60 0.60 IG CEP gebeg 30 0.55 T=4.5 T=4.5 0 0.50 0 0.80 0.85 0.90 0.95 1.00 0.80 0.85 0.90 0.95 1.00 Density Density 0.9 90 FL C d 0.8 o IG CEP a T=2.5 Φ 0 04 0506 070T-25 8304 0.5 0607080910 Density Density

sition predominate in thehigher temperature section.

# D.Case: $\xi \neq 0$ and Concentration is fixed

4.0 1.0 90   
3.5 a G GureLline 0.8 8   
3.0 uu   
rrere Mixed Spinodal 0.4 0 2.5 0.2 C=0.8 CEP C=0.8 C=0.8 2.0 0.0 0 0.300.450.600.750.90 0.300.450.600.750.90 0.300.45_0.600.750.90 Density Density Density 4.0 1.0 90 CureLline 8604 580463 0   
1.5 8 CEP 0.4 MixedSpinoda 0.6C=0.9 0.2 0.8.2 0.4 06-0.8 152 0.4 0.6 C-0 3.5 Density 1.0 Density 90 Density Curie Line C=0.99 0.8h 75 C=0.99 2.5 IG FL 0.6 5 θ u CEP 0.4 30 中 Mixed Spinodal 0.2 C=0.99 15 0.5 0.0 0 0.2 0.40.6 0.8 0.2 0.40.6 0.8 0.2 0.4 0.6 0.8 Density Density Density

The spinodal diagrams in the density concentration plane are shown in Fig. 4(a,c).In order to elucidate the differences of the mixture phase behavior at different temperatures,phase behavior is characterized by $\theta$ and $\phi$ Fig. 4(b) show in the $T = 4 . 5$ section the angles $\phi > 8 5 ^ { 0 }$ and $\theta < 4 5 ^ { 0 }$ along the mixed spinodal curve,in which the phase instability is predominantly related to the ordering phase transition accompanied by the weak demixing and tiny condensation. But in the lower temperature section $T = 2 . 5$ （Fig.4(d)）the instability predominantly related to the demixing accompanied by the weak ordering and gas-liquid phase transition at $\rho * > 0 . 6$ .Although the different temperature sections are quite similar topology, the predominant phase instability is considerable discrepancybetween them.Recently, Fenzel at.presented con centration pressure phase diagrams of the ideal Ising mix ture fluids at different temperatures via the Gibbs ensemble Monte Carlo simulation [2O],which the phase behavior can qualitatively agree with the $T$ sections calculated in our model. On the other hand the demixing phase transition in the mixtures can be easily observed in the lower temperature section but ferromagneticphase tran

Density-temperature spinodal diagrams are plotted in Fig.(5)(a,d,g) where the different sections belong to different values of the parameter $C$ .In Fig.5(a)the critical endpoint is at $\rho ^ { * } = 0 . 3 4 5$ and $T ^ { * } = 2 . 2 8$ and the slope of the mixed spinodal is positive which was found in asymmetric binary dipolar mixtures[21]. In Fig.5(c) the phase instability is predominantly related to the demix ing in the region $\rho ^ { * } > 0 . 5 5$ and the ordering in the range of $0 . 3 4 5 < \rho ^ { * } < 0 . 5 5$ .But the condensation fluctuations is always weakest in the $C ~ = ~ 0 . 8$ section．The positive slope of the mixed spinodal means that increase of the total number density,at fixed concentration,the first order phase transition temperature increase with increasing $\rho ^ { * }$ .When considering mixtures at $C = 0 . 9$ one finds from Fig. (5)(d) that the slope of the mixed spinodal move towards flat. Since increase of the Heisenberg particle concentration implies that the condensation instability gradually predominate the phase transition,as shown Fig. (5)(f). In the limit $C  1 . 0$ one recovers the MF spinodal diagram of the pure Heisenberg fluid contain only two fluid phases,which is an isotropic vapor and a ferromagnetic liquid[17]. Here we set $C = 0 . 9 9$ ， and then the spinodal diagram is shown in Fig.5( $\mathcal { I }$ )and the angle $\phi$ is always near the zero and $\theta$ is large than $4 5 ^ { 0 }$ when $\rho * > 0 . 2 5$ in Fig.5 (i).The predominant instability is related to the condensation with small ordering and demixing fluctuations which coincide with results of pure Heisenberg fluid.In particular, the angle is obtained as a function of the concentration in Fig.3 thereby providing an estimate of the crossover between the demixing predominant and the condensation predominant phase transition as expected. Such the crossover phenomena can be precisely characterized by the method[19].

# VI. CONCLUSIONS

In this paper we have investigated the phase transition of HHNH mixtures by using the density functional theory in the mean-field approximation. The phase instability of the system is discussed with the method developed in Ref.([19]).From the matrix of the second derivatives of the grand canonical free energy $\Omega$ with respect to the total particle density, the concentration and the magnetization,we can determine the thermodynamic stability of the system.When the smallest eigenvalue of the matrix becomes zero，the system becomes unstable. The eigenvector corresponding the zero eigenvalue can characterize the phase instability precisely. In the total density,concentration，magnetization space $( \delta \rho / \rho , \delta C , \delta \xi )$ the normalized eigenvector can be described by two angles $\theta$ and $\phi$ which is in the range $- 9 0 ^ { 0 } < \theta \leq 9 0 ^ { 0 }$ and $- 1 8 0 ^ { 0 } < \phi \leq 1 8 0 ^ { 0 }$ , respectively.

For temperature above of the critical endpoints,the angle $\theta = 0$ and the phase transition is pure ferromagnetic.This is the result in the mean-field approximation. With a more accurate approximation the angle $\theta$ does not equal exactly to O and is just near O.Then the total particle density and concentration will be related to the phase transition,which is predominantly ferromagnetic and accompanied by a weak condensation and demixing. Below CEP there is a first-order phase transition between isotropic gas and ferromagnetic liquid. The phase instability along the spinodal near the ferromagnetic liquid is a combination of condensation,demixing and ferromagnetic phase transition.The phase behavior can topologi callybe worthy to be compared with the simulations[20] in the different $T$ sections.Although the different temperature sections are similar topology,in the lower temperature section $T = 2 . 5$ the instability predominantly is related to the demixing but in the $T = 4 . 5$ section the ordering phase transition is predominant.The slope of the mixed spinodal is the positive in the less concentration $C = 0 . 8$ sections and is negative in the $C = 0 . 9 9$ section. Hence by accurately investigating the angles we quantitatively describe that the phase instability continuously changes from predominant demixing phase transition to predominant gas-liquid phase transition.Although these crossover phenomena in the concentration sections may be considered as different phase transitions,our analysis shows that their origin in fact is same.

These crossover phenomena within mean field approximation should be corroborated Monte Carlo simulations andfurther explore the combinations of phase transitions on the Curie line with more accurate approximation.

# Acknowledgments

This work was supported by the National Natural Science Foundation of China under grant 1O325418.

# VII. APPENDIX:THEELEMENTSOF THEMATRIX $M$ （204号

In this appendix we give the expressions of the matrix elements (29) in detail,

$$
\begin{array} { l } { { { \cal M } _ { \rho \rho } ~ = ~ { \rho ^ { 2 } } \times \Big ( C ^ { 2 } { \cal M } _ { H H } + 2 C { \cal M } _ { H N } } } \\ { { ~ - ~ 2 C ^ { 2 } { \cal M } _ { H N } + ( 1 - C ) ^ { 2 } { \cal M } _ { N N } \Big ) , } } \end{array}
$$

$$
M _ { C C } \ = \ \rho ^ { 2 } ( M _ { H H } - 2 M _ { H N } + M _ { N N } ) ,
$$

$$
M _ { \rho \xi } \ = \ M _ { \xi \rho } = \rho C M _ { H \xi } ,
$$

$$
M _ { C \xi } \ = \ M _ { \xi C } = \rho M _ { H \xi } ,
$$

$$
\begin{array} { l } { { M _ { C \rho } ~ = ~ M _ { \rho C } = \rho ^ { 2 } \times \Big ( C M _ { H H } } } \\ { { ~ + ~ ( 1 - 2 C ) M _ { H N } - ( 1 - C ) M _ { N N } \Big ) , } } \end{array}
$$

where the elementsof thematrixare related to

$$
\begin{array} { r l } { \mathcal { M } _ { R H } = } & { \beta \int _ { 0 } ^ { \infty } \mathrm { e } ^ { \mathrm { i } \phi } e ^ { \mathrm { i } \phi } \frac { \partial ^ { 2 } \mathrm { i } \phi } { \partial t ^ { 2 } } + 2 i \mathrm { e } _ { \mathrm { i } \phi } \delta ^ { 2 } \frac { \partial ^ { 2 } \mathrm { i } \phi ( x ) } { \partial x ^ { 2 } } - J _ { \mathrm { r e f } } \delta ( x ) \mathrm { d } \phi } \\ & { + \frac { 1 } { \tilde { \mathcal { M } } _ { R H } } + \frac { \partial ^ { 2 } \mathrm { r e } ^ { \mathrm { i } \phi } ( x ) } { \partial \phi _ { \mathrm { r e f } } ^ { \mathrm { i } \phi } } } \\ { \mathcal { M } _ { \mathrm { R P } } = } & { \frac { 1 } { \tilde { \mathcal { M } } _ { 0 } } + \frac { i \phi } { \partial x ^ { 2 } \phi _ { \mathrm { r e f } } ^ { \mathrm { i } \phi } \partial x ^ { 2 } } , } \\ { \mathcal { M } _ { \mathrm { R H } } = } & { \beta J _ { 0 } ^ { 2 } \mathrm { e } ^ { \mathrm { i } \phi } \frac { \partial ^ { 2 } \mathrm { i } \phi ( x ) } { \partial x ^ { 2 } } + J _ { \mathrm { r e f } } \delta ^ { 2 } , } \\ { \mathcal { M } _ { \mathrm { R P } } = } & { \mathcal { M } _ { \mathrm { R P } } + \frac { \partial ^ { 2 } \mathrm { r e } ^ { \mathrm { i } \phi } ( x ) } { \partial \phi _ { \mathrm { r e f } } ^ { \mathrm { i } \phi } } , } \\ { \mathcal { M } _ { \mathrm { R P } } = } & { \mathcal { M } _ { \mathrm { R P } } - \frac { \partial ^ { 2 } \mathrm { r e } ^ { \mathrm { i } \phi } ( x ) } { \partial \phi _ { \mathrm { r e f } } ^ { \mathrm { i } \phi } \partial x ^ { 2 } } , } \\ { \mathcal { M } _ { \mathrm { R H } } = } & { \mathcal { M } _ { \mathrm { R P } } - \frac { \partial ^ { 2 } \mathrm { r e } ^ { \mathrm { i } \phi } ( x ) } { \partial \phi _ { \mathrm { r e f } } ^ { \mathrm { i } \phi } \partial x ^ { 2 } } , } \\ { \mathcal { M } _ { \mathrm { R P } } = } & { \mathcal { M } _ { R H } - \partial ^ { 2 } \mathrm { r e } ^ { \mathrm { i } \phi } \frac { \partial ^ { 2 } \mathrm { r e f } } { \partial x ^ { 2 } } } \\ { \mathcal { M } _ { R H } = } & { \mathcal { M } _ { R H } - \partial ^ { 2 } \mathrm { r e f } \phi _ { \mathrm { r e f } } ^ { \mathrm { i } \phi } } \\ { \mathcal { M } _ { \mathrm { R P } } = } &  \mathcal { M } _ { \mathrm { R P } } + \mathcal  M \end{array}
$$

[1]M.J.P.Nijmeijer,andJ.J.Weis,Phys.Rev.Lett.75 2887(1995);Phys.Rev.E 53 591 (1996).   
[2] M. J. P. Nijmeijer, A. Parola, and L. Reatto, Phys. Rev. E 57 465 (1998).   
[3]I.M.Mryglod,I.P. Omelyan,and R. Folk,Phys.Rev. Lett.86 3156 (2001);   
[4]MichaelE.Fisher,Phys.Rev.176 257(1968).   
[5]N.B.Wilding，and P.Nielaba，Phys.Rev.E 53 926 (1996).   
[6]A.L.Ferreira,and W.Korneta,Phys.Rev.E 57 926 (1998).   
[7] W.Korneta,Phys.Rev.E 64 041109 (2001).   
[8]W.Fenz，R.Folk,I.M.Mryglod,and I.P.Omelyan, Phys.Rev.E 75 061504 (2007).   
[9]I.P.Omelyan，W.Fenz,I.M.Mryglod,and R.Folk, Phys.Rev.Lett.94 045701 (2005)；Phys.Rev.E 72 031506 (2005).   
10]F.Lado,and E.Lomba,Phys.Rev.E 76 041502 (2007).   
11]E.Lomba,J.J.Weis,N.G.Almarza,F.Bresme,and G. Stell,Phys.Rev.E 49 5169 (1994).   
12] J.M.Tavares,M.M. Telo da Gama,P.I.C. Teixeira, J.J.Weis,and MJ.P.Nijmeier,Phys.Rev.E 521915 (1995).   
13]J.J.Weis,M.J.P.Nijmeijer,J.M.Tavares,and M.M. Telo da Gama,Phys.Rev.E 55 436 (1997).   
[14]F.Lado,and E.Lomba,Phys.Rev.Lett.80 3535 (1998).   
[15] F.Lado,E. Lomba,and J.J.Weis,Phys.Rev.E 58 3478 (1998).   
[16] E. Lomba, J. J. Weis, and C. F. Tejero, Phys. Rev. E 58 3426 (1998).   
[17] L. S.Li,L. Li,and X. S. Chen (to be published).   
[18]X.S.Chen,M.Kasch,and F.Forstmann,67 2674(1991).   
[19] X.S. Chen and F. Forstmann,Mol. Phys. 76 1203(1992); J.Chem.Phys.97 3696   
[20] W.Fenz,and R. Folk,Phys.Rev.E 67 021507 (2003); Phys.Rev.E 71 046104 (2005).   
[21] Gabriel M. Range and Sabine H. L. Klapp,Phys. Rev. E 69 041201 (2004).   
[22]N.F.Carnahan and K.E.Starling,J.Chem.Phys.51 635 (1969).   
[23] R.Evans,Adv.Phys.28 143 (1979).   
[24] M.J.P. Nijmeijer and J.J. Weis，in Annual Review of ComputationalPhysicsIV,editedbyD.Stauffer(World Scientific, Singapore,1996).   
[25]J.Reske,D.M.Herlach，F.Keuser,K.Maier,and D. Platzek,Phys.Rev.Lett. 75 737 (1995).