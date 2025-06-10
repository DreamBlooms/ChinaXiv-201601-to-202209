# Solution of Inverse Heat Conduction Problem using the Tikhonov Regularization Method

# Piotr Duda

Institute ofThermal PowerEngineering,CracowUniversityofTechnologyal.Jana Pawla I37,31-864 Krakow,Poland $\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

It is hard to solve ill-posed problems,ascalculated temperaturesare very sensitive to errors made whilecalculating“measured" temperatures or performing real-time measurements.The errors can create temperature oscillation, which can be the cause of an unstable solution.In order to overcome such dificulties,a variety of techniques have been proposed in literature,including regularization,future time steps and smoothing digital filters.In this paper,the Tikhonov regularization is applied to stabilize the solution of the inverse heat conduction problem.The impact on the inverse solution stability and accuracy is demonstrated.

# Keywords:inverse problems,heat conduction, identification

# Introduction

The thermal analysis is necessary for the design of components operating in high temperatures.One of the difficulties in the thermal analysis is the definition of all boundary conditions,especially the convection boundary condition. The problem can be solved numerically,analysing the flow phenomena occurring when the fluid comes into contact with individual components [1].An alternative method of the temperature distribution deter minationisthe search for the solutionto the inverse heat conduction problem in the device under analysis.

Inverse problems,in contrast to direct problems,are characterized byan unknown part ofboundary conditions [2-4,9], some undefined material properties [5] or indeterminate heat sources [6]. They happen in engineering, because defining some boundary conditions,material properties or heat sources is often tough.These problems can be solved by performing additional temperature measurements instead of the unknown boundary condition or the parameters mentioned above.

# Formulation of the method

Using the semi-discrete control volume method to determine the temperature distribution in a plate,as presented in Fig.1,a system of non-linear differential equations can be obtained.

![](images/0a611e5bdeb93edad51b9177988462666e7b1fa7c467a2c0ffac59dd1715c05c.jpg)  
Fig.1 Plate with thickness $L$ with an unknown and known boundary condition

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>C</td><td> specific heat, J/(kgK)</td><td>T</td><td>temperature,C or K</td></tr><tr><td>k</td><td>thermal conductivity, W/(mK)</td><td>q</td><td>heat flux, W/m²</td></tr><tr><td>t</td><td>time, s</td><td></td><td></td></tr></table></body></html>

![](images/616c7f79618e13ed01143beeffec3b4fca6c25b3918e3814a22b0dc0f5d342ac.jpg)  
Fig.2Staircase approximation of temperature or heat flux at the plate front surface

If the temperature and the heat flux at the body surface are approximated by a continuous-time staircase function both at the plate front(cf.Fig.2) and back surface

$$
\begin{array} { c } { { u ( t ) = u ( k ) } } \\ { { w ( t ) = w ( k ) } } \end{array} \displaystyle k \Delta t < t < \left( k + 1 \right) \Delta t , k \in \left. 0 , . . , N \right.
$$

the following system of equations describes temperature distribution

$$
\dot { \mathbf { T } } = \mathbf { A } \mathbf { T } + \mathbf { B } u + \mathbf { W } w
$$

with the initial conditions

$$
\left. \mathbf { T } ( t ) \right| _ { t = t _ { 0 } } = \left\{ \begin{array} { l l } { T _ { 1 } \left( t _ { 0 } \right) } \\ { T _ { 2 } \left( t _ { 0 } \right) } \\ { \quad } \\ { \quad } \\ { \quad } \\ { T _ { N _ { E } } \left( t _ { 0 } \right) } \end{array} \right\} _ { N _ { I } }
$$

where ${ \bf T }$ is the $N _ { E }$ dimensional vector,which describes temperature transients at $N _ { E }$ nodes of a discrete space model (state vector), time variable $t$ varies in the range of $t _ { 0 } \leq t \leq t _ { N + 1 }$ ,A is the square matrix of $N _ { E } \mathrm { ~ x ~ } N _ { E }$ dimensions, $\mathbf { B }$ and $\mathbf { W }$ are vectors of the $N _ { E }$ dimensions, $u ( t )$ is the unknown boundary condition, $w ( t )$ is the known boundary condition. Both boundary conditions can be assumed in the form of the first or the second kind boundary condition. The solution of(2) can be written in a matrix form [7]

$$
\begin{array} { l } { { \displaystyle { \bf T } \left( t \right) = e ^ { { \bf A } \left( t - t _ { 0 } \right) } { \bf T } \left( t _ { 0 } \right) + e ^ { t { \bf A } } \int _ { t _ { 0 } } ^ { t } e ^ { - s { \bf A } } { \bf B } u \left( s \right) d s } \ ~ } \\ { { \displaystyle ~ + e ^ { t { \bf A } } \int _ { t _ { 0 } } ^ { t } e ^ { - s { \bf A } } { \bf W } w \left( s \right) d s } } \end{array}
$$

Replacing $t$ with $t _ { 0 } + \varDelta t$ in equation (4), the following is obtained:

$$
\begin{array} { l } { \displaystyle \mathbf { T } \left( t _ { 0 } + \Delta t \right) = e ^ { \mathbf { A } \left( \Delta t \right) } \mathbf { T } \left( t _ { 0 } \right) } \\ { \displaystyle \qquad + e ^ { \left( t _ { 0 } + \Delta t \right) \mathbf { A } } \int _ { t _ { 0 } } ^ { t _ { 0 } + \Delta t } e ^ { - s \mathbf { A } } \mathbf { B } u \left( s \right) d s } \\ { \displaystyle \qquad + e ^ { \left( t _ { 0 } + \Delta t \right) \mathbf { A } } \int _ { t _ { 0 } } ^ { t _ { 0 } + \Delta t } e ^ { - s \mathbf { A } } \mathbf { W } w \left( s \right) d s } \end{array}
$$

As noted in (1), $u ( s )$ and $w ( s )$ are held constant throughout the interval at the value of $u ( k \varDelta t )$ and $w ( k \varDelta t )$ respectively. Therefore,equation(5) may be rewritten as

$$
\begin{array} { r } { \mathbf { T } \left( t _ { 0 } + \Delta t \right) = \mathbf { F } \left( \Delta t \right) \mathbf { T } \left( t _ { 0 } \right) + \mathbf { G } \left( \Delta t \right) u \left( t _ { 0 } \right) + \mathbf { H } \left( \Delta t \right) w \left( t _ { 0 } \right) } \end{array}
$$

Where

$$
\begin{array} { c } { \displaystyle \mathbf { F } \big ( \Delta t \big ) = e ^ { \mathbf { A } \Delta t } } \\ { \displaystyle \mathbf { G } \big ( \Delta t \big ) = \int _ { 0 } ^ { \Delta t } e ^ { \mathbf { A } s } d s \mathbf { B } } \\ { \displaystyle \mathbf { H } \big ( \Delta t \big ) = \int _ { 0 } ^ { \Delta t } e ^ { \mathbf { A } s } d s \mathbf { W } } \end{array}
$$

Matrix $\mathbf { G } ( \varDelta t )$ is given by

$$
\begin{array} { r } { \mathbf { G } \big ( \Delta t \big ) = \mathbf { G } = \displaystyle \int _ { t _ { 0 } } ^ { t _ { 0 } + \Delta t } e ^ { \mathbf { A } \big ( t _ { 0 } + \Delta t - s \big ) } \mathbf { B } d s } \\ { = - \displaystyle \int _ { \Delta t } ^ { 0 } e ^ { \mathbf { A } \tau } \mathbf { B } d \tau = \displaystyle \int _ { 0 } ^ { \Delta t } e ^ { \mathbf { A } \tau } d \tau \mathbf { B } } \end{array}
$$

where

$\tau = t _ { 0 } + \Delta t - s$ .Matrix $\mathbf { H }$ can be calculated in a similar way. Expanding $e ^ { \mathbf { A } \Delta t }$ into the McLaurin series in the same way as function $e ^ { x }$ $\mathbf { F } ( \varDelta t ) = \mathbf { F }$ can be written as

$$
\mathbf { F } = \mathbf { I } + \mathbf { A } \Delta t + { \frac { \left( \mathbf { A } \Delta t \right) ^ { 2 } } { 2 ! } } + { \frac { \left( \mathbf { A } \Delta t \right) ^ { 3 } } { 3 ! } } + \ldots
$$

Introducing $e ^ { \mathbf { A } \Delta t }$ into (8） and integrating (8） gives $\mathbf { G } ( \varDelta t ) = \mathbf { G }$

$$
\mathbf { G } = \left[ \mathbf { I } + \frac { \mathbf { A } \Delta t } { 2 ! } + \frac { \left( \mathbf { A } \Delta t \right) ^ { 2 } } { 3 ! } + \frac { \left( \mathbf { A } \Delta t \right) ^ { 3 } } { 4 ! } + \ldots \right] \mathbf { B } \Delta t
$$

Matrix $\mathbf { H } ( \varDelta t ) { = } \mathbf { H }$ can be calculated in a similar way.

$$
\mathbf { H } = \left[ \mathbf { I } + { \frac { \mathbf { A } { \Delta t } } { 2 ! } } + { \frac { \left( \mathbf { A } { \Delta t } \right) ^ { 2 } } { 3 ! } } + { \frac { \left( \mathbf { A } { \Delta t } \right) ^ { 3 } } { 4 ! } } + \ldots \right] \mathbf { W } { \Delta t }
$$

Using equation (6) and omitting $\varDelta t$ ,the temperature in time $t _ { I }$ is obtained

$$
\mathbf { T } \left( t _ { 1 } \right) = \mathbf { T } _ { 1 } = \mathbf { F } \mathbf { T } _ { 0 } + \mathbf { G } u _ { 0 } + \mathbf { H } w _ { 0 }
$$

Similarly, for time point 2

$$
\mathbf { T } _ { 2 } = \mathbf { F } \mathbf { T } _ { 1 } + \mathbf { G } u _ { 1 } + \mathbf { H } w _ { 1 }
$$

Substituting(14) into (15) gives

$$
\mathbf { T } _ { 2 } = \mathbf { F } \big [ \mathbf { F } \mathbf { T } _ { 0 } + \mathbf { G } u _ { 0 } + \mathbf { H } w _ { 0 } \big ] + \mathbf { G } u _ { 1 } + \mathbf { H } w _ { 1 }
$$

after transformation

$$
\mathbf { T } _ { 2 } = \mathbf { F } ^ { 2 } \mathbf { T } _ { 0 } + \mathbf { F } \mathbf { G } u _ { 0 } + \mathbf { F } \mathbf { H } w _ { 0 } + \mathbf { G } u _ { 1 } + \mathbf { H } w _ { 1 }
$$

and generally for point i

$$
\begin{array} { l } { { { \bf { T } } _ { i } = { \bf { F } } ^ { i } { \bf { T } } _ { 0 } + { \bf { F } } ^ { i - 1 } { \bf { G } } u _ { 0 } + { \bf { F } } ^ { i - 1 } { \bf { H } } w _ { 0 } + { \bf { F } } ^ { i - 2 } { \bf { G } } u _ { 1 } } } \\ { { \quad \quad \quad + { \bf { F } } ^ { i - 2 } { \bf { H } } w _ { 1 } + \ldots + { \bf { F } } { \bf { G } } u _ { i - 2 } + { \bf { F } } { \bf { H } } w _ { i - 2 } } } \\ { { \quad \quad \quad + { \bf { G } } u _ { i - 1 } + { \bf { H } } w _ { i - 1 } , } } \\ { { { \bf { T } } _ { i } = { \bf { F } } ^ { i } { \bf { T } } _ { 0 } + \displaystyle \sum _ { j = 0 } ^ { i - 1 } { \bf { F } } ^ { i - 1 - j } { \bf { G } } u _ { j } + \displaystyle \sum _ { j = 0 } ^ { i - 1 } { \bf { F } } ^ { i - 1 - j } { \bf { H } } w _ { j } } } \end{array}
$$

In order to determine the temperature at a selected spatial point $L$ ,the following row vector is introduced

$$
\mathbf { v } _ { L } = \left( 0 , . . . , a _ { L } , . . . , 0 \right) _ { N _ { T } }
$$

where $a _ { L } = I$ . The temperature at spatial point $L$ and at time $i$ can be written as

$$
T _ { L , i } = \mathbf { v } _ { L } \left[ \mathbf { F } ^ { i } \mathbf { T } _ { 0 } + \sum _ { j = 0 } ^ { i - 1 } \mathbf { F } ^ { i - 1 - j } \mathbf { G } u _ { j } + \sum _ { j = 0 } ^ { i - 1 } \mathbf { F } ^ { i - 1 - j } \mathbf { H } w _ { j } \right]
$$

Let us assume that temperature is measured at nodes: $L _ { I } , L _ { 2 } , . . . , L _ { N _ { T } } \ .$ . The aim of the proposed inverse method is to calculate the unknown boundary condition $u ( t )$ so that the calculated temperatures $T$ agree,within certain limits,withexperimentally measured temperatures $f .$ （20

$$
f _ { j , i } \cong T _ { j , i } , \quad j = 1 , . . , N _ { T } , i = 1 , . . . , \left( N + 1 \right)
$$

If there is just one measurement point at the insulated surface, $\scriptstyle { L = L _ { I } }$ ：

$$
\begin{array} { r l } & { f _ { L _ { 1 } , 1 } \cong \mathbf { v } _ { \mathrm { \ell _ { 1 } } } \left[ \mathbf { F T _ { 0 } } + \mathbf { G } u _ { 0 } + \mathbf { H } w _ { 0 } \right] } \\ & { f _ { L _ { 2 } , 2 } \cong \mathbf { v } _ { \mathrm { \ell _ { 2 } } } \left[ \mathbf { F ^ { 2 } T _ { 0 } } + \mathbf { F G } u _ { 0 } + \mathbf { G } u _ { 1 } + \mathbf { F H } w _ { 0 } + \mathbf { H } w _ { 1 } \right] } \\ & { . . . . . . . . . . } \\ & { f _ { L _ { 1 } , N + 1 } = \mathbf { v } _ { \mathrm { \ell _ { 1 } } } \left[ \mathbf { F } ^ { N + 1 } \mathbf { T _ { 0 } } + \sum _ { j = 0 } ^ { N } \mathbf { F } ^ { N - j } \mathbf { G } u _ { j } \right. } \\ & { \qquad \left. + \sum _ { j = 0 } ^ { N } \mathbf { F } ^ { N - j } \mathbf { H } w _ { j } \right] } \end{array}
$$

The above system of equations (23) can be written in a matrix form

$$
\mathbf { f } - \mathbf { c } \cong \mathbf { Z U }
$$

where

$$
\mathbf { f } = \left\{ \begin{array} { l } { f _ { L _ { 1 } , 1 } } \\ { \quad \dots } \\ { \quad \dots } \\ { f _ { L _ { 1 } , N + 1 } } \end{array} \right\}
$$

$$
\mathbf { c } = \left. \begin{array} { c } { \mathbf { v } _ { L _ { 1 } } \left[ \mathbf { F T } _ { 0 } + \mathbf { H } w _ { 0 } \right] } \\ { \ldots } \\ { \ldots } \\ { \mathbf { v } _ { L _ { 1 } } } \\ { \mathbf { v } _ { L _ { 1 } } \left[ \mathbf { F } ^ { N + 1 } \mathbf { T } _ { 0 } + \displaystyle \sum _ { j = 0 } ^ { N } \mathbf { F } ^ { N - j } \mathbf { H } w _ { j } \right] } \end{array} \right.
$$

$$
\mathbf { U } _ { K } = { \left\{ \begin{array} { l l } { u _ { 0 } } \\ { \cdots } \\ { \cdots } \\ { u _ { N } } \end{array} \right. }
$$

$$
\mathbf { Z } = \left[ \begin{array} { c c c c } { \mathbf { v } _ { L _ { i } } \mathbf { G } } & { 0 } & { \ldots } & { 0 } \\ { \mathbf { v } _ { L _ { i } } \mathbf { F } \mathbf { G } } & { \mathbf { v } _ { L _ { i } } \mathbf { G } } & { \ldots } & { 0 } \\ { \ldots } & { \ldots } & { \ldots } & { 0 } \\ { \mathbf { v } _ { L _ { i } } \mathbf { F } ^ { N } \mathbf { G } } & { \mathbf { v } _ { L _ { i } } \mathbf { F } ^ { N - 1 } \mathbf { G } } & { \ldots } & { \mathbf { v } _ { L _ { i } } \mathbf { G } } \end{array} \right]
$$

The least squares method is used to satisfy the condition expressed in (22)

$$
\sum _ { j = 1 } ^ { N _ { T } } \sum _ { i = 1 } ^ { N + 1 } \left( T _ { j , i } - f _ { j , i } \right) ^ { 2 } = \operatorname* { m i n }
$$

This can be written in the following matrix form

$$
S = \left( \mathbf { Z } \mathbf { U } - \mathbf { f } + \mathbf { c } \right) ^ { T } \left( \mathbf { Z } \mathbf { U } - \mathbf { f } + \mathbf { c } \right) = \operatorname* { m i n }
$$

The solution which satisfies condition (30) is

$$
\mathbf { U } = \left( \mathbf { Z } ^ { T } \mathbf { Z } \right) ^ { - 1 } \mathbf { Z } ^ { T } \left( \mathbf { f } - \mathbf { c } \right)
$$

The determinant of matrix $\mathbf { Z }$ is close to zero and calculations according to (31） could often lead to an ill-conditioned algorithm. Hence, it is necessary to investigate theproblem,estimate itsrange andlook forways of reducing it.

One of the possibilities of improving the inverse problem solution stability is the Tikhonov regularization [8]. Tikhonov proposes parallel minimization of the quadratic measure of the solution vector $\mathbf { U }$ ：

$$
S = \left\| \mathbf { Z } \mathbf { U } - \mathbf { f } + \mathbf { c } \right\| ^ { 2 } + \lambda \left\| \mathbf { U } \right\| ^ { 2 } = \operatorname* { m i n }
$$

Condition (32) leads to

$$
\mathbf { U } = \left( \mathbf { Z } ^ { T } \mathbf { Z } + \lambda \mathbf { I } \right) ^ { - 1 } \mathbf { Z } ^ { T } \left( \mathbf { f } - \mathbf { c } \right)
$$

where $\textbf { I }$ isaunit matrix.Here,the mechanism of improving the conditioning of matrix $\mathbf { z } ^ { T } \mathbf { Z }$ can be observed. It consists in adding constants $\lambda$ to the matrix diagonal. The weighting coefficient $\lambda$ should be relatively small so as not to change the main purpose of equation (3O) - minimization of the square residuals - but it cannot be too small, especially in the case of strongly ill-conditioned equation (31). The optimal choice of $\lambda$ will be discussed in the next section.

Total errors in the identified boundary condition $u ( t )$ can be estimated by comparing calculated values $u _ { i }$ with exact values $u _ { i } ^ { e x }$ for $i = 0$ $N$ using the following formula:

$$
\Sigma _ { u } = \sqrt { \frac { \displaystyle \sum _ { i = 0 } ^ { N } \Bigl ( u _ { j } - u _ { j } ^ { e x } \Bigr ) ^ { 2 } } { N } }
$$

Similarly, the total error in the calculated temperature

distribution can be obtained

$$
\Sigma _ { T } = \sqrt { \frac { \displaystyle { \sum _ { j = 1 } ^ { N _ { E } } \sum _ { i = 1 } ^ { N + 1 } { \left( T _ { j , i } - T _ { j , i } ^ { e x } \right) } ^ { 2 } } } { N \left( N _ { E } - 1 \right) } }
$$

# Analytical Solution

Let us assume that an infinite plate with thickness $L$ ，as presented inFig.1,isheated byaheat flux on itsfront surface and that the plate back surface is insulated.The initial temperature of the plate is constant and equals $T _ { 0 }$ .Material properties are assumed as temperature-independent. The temperature distribution in the plate is described by the heat conduction equation

$$
{ \frac { \hat { \sigma } T } { \hat { \sigma } t } } = a { \frac { { \hat { \sigma } } ^ { 2 } T } { { \hat { \sigma } } x ^ { 2 } } } \qquad 0 \leq x \leq L
$$

the boundary conditions

$$
- { \frac { \partial T } { \partial x } } { \bigg | } _ { x = 0 } = { \left\{ \begin{array} { l l } { q _ { m } \quad } & { t _ { 1 } < t < t _ { 2 } } \\ { 0 \quad } & { t \leq t _ { 1 } \ o r \ t \geq t _ { 2 } } \end{array} \right. }
$$

$$
\left. \frac { \partial T } { \partial x } \right| _ { x = L } = 0
$$

and the initial condition

$$
T \left( x , 0 \right) = 0 \qquad 0 \leq x \leq L
$$

The plate temperature distribution can be calculated using the superposition principle [4].

$$
\begin{array} { c } { { T \left( x , t \right) = 0 \qquad 0 \leq t \leq t _ { 1 } } } \\ { { T \left( x , t \right) = \mathcal { S } \left( x , t - t _ { 1 } \right) \qquad t _ { 1 } < t \leq t _ { 2 } } } \\ { { T \left( x , t \right) = \mathcal { S } \left( x , t - t _ { 1 } \right) - \mathcal { S } \left( x , t - t _ { 2 } \right) \quad t > t . } } \end{array}
$$

Where

$$
\begin{array} { c } { { \displaystyle { \mathcal { S } \Big ( x , t \Big ) = T _ { 0 } + \frac { q _ { m } L } { k } \Bigg [ \frac { a t } { L ^ { 2 } } + \frac { x ^ { 2 } } { 2 L ^ { 2 } } - \frac { x } { L } + \frac { 1 } { 3 } } } } \\ { { \displaystyle { - \frac { 2 } { \pi ^ { 2 } } \sum _ { n = 1 } ^ { \infty } \frac { 1 } { n ^ { 2 } } \cos \left( n \pi \frac { x } { L } \right) \exp \left( - n ^ { 2 } \pi ^ { 2 } \frac { a t } { L ^ { 2 } } \right) \Bigg ] } } } \end{array}
$$

# Numerical simulations

The plate presented in Fig.1 with thickness $\scriptstyle L = 0 . 1 \ m$ is insulated on its back surface and is subjected to the boundary condition of the second kind (37) with parameters: $t _ { 1 } { = } 7 3 0 \ \mathrm { s } ,$ $t _ { 2 } { = } 1 2 3 0 \mathrm { ~ s ~ }$ $q _ { \mathrm { m } } { = } 3 5 0 \mathrm { k W } / \mathrm { m } ^ { 2 }$ ：

The following material properties are adopted for the solution: $k { = } 4 0 \mathrm { W / ( m K ) }$ ， $c \rho { = } 4 . 0 \mathrm { E } { + } 6 \mathrm { J } / ( \mathrm { m } ^ { 3 } \mathrm { K } )$

The inverse problem is then formulated without specifying the boundary condition on the plate frontsurface with the measured temperature transient on the back insulated surface.The heat flux transient at the front surface of the plate with thickness $\scriptstyle { L = 0 . 1 \ m }$ and the temperature distribution on the thickness are determined based on the measured temperature history at the plate back surface, which is insulated.“Exact measurement data”at the back surface are obtained from the analytical solution (40-43). The plate thickness is divided into 6 control volumes $( N _ { E } { = } 6 )$ and the time step $\Delta t { = } 5 0 \ \mathrm { s }$ is used.

The algorithm for calculating the unknown boundary condition vector U,which is based on equation (31),is unstable. The results are presented in Fig. 3.

The solution formulated according to equation (33) using the Tikhonov regularization method makes it possible to find the unknown boundary condition. The smallest error is found with the weighting coefficient $\lambda =$ 5.7E-1O.The calculated heat flux at the plate front surface and the determined temperature transients are presented inFig.4 andFig.5.Total errors in the identified boundary condition and in the temperature distribution equal to $\scriptstyle \sum _ { \mathrm { u } } = 4 . 4 9 \mathrm { E } + 0 4 \mathrm { W } / \mathrm { m } ^ { 2 }$ and $\Sigma _ { \mathrm { T } } { = } 4 . 4 1 ^ { \circ } \mathrm { C } ,$ ,respectively.

![](images/22932209710fea777074c4919ea6aef0e7cb7915410e7dca1fbb8abeb2923dde.jpg)  
Fig.3Estimated unknown boundary condition at the plate front surface according to (31) without regularization

![](images/b853b02bd720a0b3eea1742aff48c14610fa0e95aef3f4687ba76d03db3f945e.jpg)  
Fig.4 Estimated unknown boundary condition at the plate front surface according to (33) using the regularization method

![](images/e6845a46abf18251daead4c4a6921362f66adc199bb919bce677daa714de5caa.jpg)  
Fig.5Comparison between the exact temperature histories and those calculated by means of the inverse method using regularization

In order to make the test more realistic,“noisy measured data’are obtained by adding normal random errors $\pm 1 0 ^ { \circ } \mathrm { C }$ of zero mean to “exact measured data".The smallest error is found with the weighting coefficient $\lambda { = } 1 . 7 \mathrm { E } { - } 9$ It is an order of magnitude larger than for undisturbed data.The calculated heat flux at the plate front surface and the determined temperature transients are presented in Fig. 6 and Fig.7. Total errors in the identified boundary condition and in the temperature distribution equal $\Sigma _ { \mathrm { u } } =$ $4 . 8 6 \mathrm { E } { + } 0 4 \ \mathrm { W } / \mathrm { m } ^ { 2 }$ and $\Sigma _ { \mathrm { T } } \mathrm { = } ~ 7 . 0 4 ^ { \circ } \mathrm { C }$ ，respectively. Despite large measurement errors,the total error in the identified boundary condition is comparable with the identification based onundisturbed data.

![](images/024bd9e61c13a0cbd638bc49a990e9e699c293f5cd6b854ef7384bc95713860d.jpg)  
Fig.7 Comparison between the exact temperature histories and those calculated by means of the inverse method using regularization based on“noisy measured data"

![](images/1c18b6b85ab5cc72148a8acddde38d4dabc8b0703f63cdfe0ea84a140df508bb.jpg)  
Fig.6 Estimated unknown boundary condition at the plate front surface according to (33) using the regularization method based on“noisy measured data"

# Conclusions

This paper presents a method of solving the inverse heat conduction problem.The problem is ill-posed and its solution is unstable.In order to improve the solution stability, the Tikhonov regularization is proposed.

The proposed method is applied to identify the heat flux at the frontsurface ofa thickplate based on the measured temperature history at the plate back surface,which is insulated.The “exact measurement data"at the back surface are obtained from the presented analytical solution. In order to make the test more realistic,“noisy measured data” are obtained by adding normal random errors $\pm 1 0 ^ { \circ } \mathrm { C }$ of zero mean to the“exact measured data".

The paper also presents the mechanism of improving the equation system conditioning.The optimal values of the weighting coefficient $\lambda$ are determined both for the "exact" and the“noisy measured data".It is an order of magnitude larger for disturbed data than for undisturbed data. The numerical verification of the presented inverse method applied together with the Tikhonov regularization demonstrates its good accuracyand stability.

# References

[1]Rup,K,Duda,P,Danys,L,20o2,Determination of heat transfer coefficients on the surfaces of plastic tubes, Journal of Heat and Mass Transfer,39,pp.89-95.   
[2]Bourquin,F,and Nassiopoulos,A,2011, Inverse reconstruction of initial and boundary conditions of a heat transfer problem with accurate final state,Int.J.of Heat and Mass Transfer, 54,pp.3749-3760.   
[3]Duda,P,2O16,A general method for solving transient multidimensional inverse heat transfer problems,Int.J.of Heat and Mass Transfer, 93,pp. 665-673.   
[4] Taler,J.,Duda,P.,2oo6.SolvingDirectandInverseHeat Conduction Problems,Springer,Berlin-Heidelberg.   
[5] Monde,M,Kosaka,M,and Mitsutake,Y,2010,Simple measurement of thermal diffusivity and thermal conductivity using inverse solution for one-dimensional heat conduction, Int. J.of Heat and Mass Transfer, 53,pp. 5343-5349.   
[6]Tian,N, Sun,J,Xu W,and Lai, C-H,2011,Estimation of unknown heat source function in inverse heat conduction problems using quantum-behaved particle swarm optimization, Int. J.of Heat and Mass Transfer,54,pp. 4110-4116.   
[7]Zill,D.G, 199o,Differential Equations with BoundaryValueProblems.Prindle,Weber&Schmidt,Boston.   
[8]Tikhonov,A,1965,On certain problemsof linear algebra and a stable method of their solutions,(in Russian) Dokl. AN SSSR 163/3, pp.591-594.   
[9]J.Taler, S.Gradziel,An Overdetermined Two-dimensional Transient Inverse Heat Conduction Problem,Forschung im Ingenieurwesen 65 (1999),98-106, Springer-Verlag 1999.