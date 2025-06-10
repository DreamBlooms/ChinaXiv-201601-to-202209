# On The Solution of Capillary Rise Dynamics

Bohua Sun1 $^ { 1 }$ Cape Peninsula University of Technology， Cape Town， South Africa \* (Dated: September 11,2017)

Capillary rise is one of the most well-known and vivid ilustrations of capillarity；however,there is no solution as yet except certain segmental solutions for asymptotic regimes.This paper used the singularity-free Bush equation and successfully obtained its Taylor's series solution. The solution revealed that capillary rise dynamics ismainly controlled by the Bond number and the Galileo number,while the Bond number is a key parameter within the solution.Due to the poor rate of convergence of the series solution,an approximate analytic capillary rise $h ( t )$ was proposed,which has been verified numerically.

PACS numbers: 68.03.Cd,68.03.Kn,47.55.nb Keywords:capillary rise dynamics,surface tension,gravity,viscosity,singularity

# INTRODUCTION

Capillary rise is one of the most well-known and vivid illustrations of capillarity. Knowledge of capillarity laws is important in oil recovery,civil engineering，dyeing of textile fabrics,ink printing,and a variety of other fields.It is the capillarity that brings water to the upper layer of soils,drives sap in plants,or lays the basis for the operation of pens [1-25, 27-33,35-38]. The capillary action has been studied by a number of masters in science.Leonardo da Vinci(1452-1519) recorded the effect in his notes and proposed that mountain streams may result from capillary rise through a fine network of cracks. Jacques Rohault (1620-1675） erroneously suggested that capillary rise occurs owing to suppression of air circulation in the narrow tube,which creates a vacuum.Geovanni Borelli （16o8-1675）demonstrated experimentally that $h \sim 1 / a$ .Geminiano Montanari (1633-87) attributed circulation in plants to capillary rise.Francis Hauksbee(17oos) conducted an extensive series of capillary rise experiments,as reported by Newton in his Opticks,but was left unattributed. James Jurin (1684-175O) independently confirmed $h \sim 1 / a$ ；hence Jurin's Law. Albert Einstein's first paper that was submitted to Annalen der Physik in 19o0,was on capillarity [1].

Washburn [3] developed the equation to describe the   
rate of the penetration of liquids into small cylindri  
cal capillaries，based on the laws of hydraulics.He   
assumed that the travelling distance in the initial tur  
bulence period was negligible,while the Poiseuille re  
gion covered practically the entire flow. According to   
Poiseuille's law,when neglecting the air resistance,the   
rate of flow through a cylindrical tube assumed the fol  
lowing form: $\begin{array} { r } { Q = \frac { \pi \Delta P } { 8 \mu h } ( a ^ { 4 } + L _ { s } a ^ { 2 } ) } \end{array}$ where $a$ is the radius   
of the tube, $h$ is the capillary penetration height,and   
$L _ { s }$ isdtieata grea mnaTle $Q \ : = \ : \pi a ^ { 2 } \frac { d h } { d t }$ $\Delta P$   
$P _ { e }$ ，the hydrostatic pressure $P _ { h }$ and the capillary pres  
sure, given by the Young-Laplace equation △P = 2gcosθ.

Combining the above relations and neglecting the s lip length gives the so-called Lucas-Washburn equation: $\begin{array} { r } { \frac { d h } { d t } = \frac { a ^ { 2 } } { 8 \mu h } ( P _ { a } + P _ { h } + \frac { 2 \sigma c o s \theta } { a } ) } \end{array}$ Ifthere isnoextemalpres sure,a commonly used form of Lucas-Washburn equation is $\begin{array} { r } { 8 \mu h \frac { d h } { d t } + \rho g h a ^ { 2 } s i n \psi = 2 a \sigma c o s \theta } \end{array}$ ，where $\psi$ is the incline angle of the tube with respect to the horizontal surface.

![](images/280c9643f573e5a02c9eddc96819bd81b0d5222aea03b1258caf109fcc16e1aa.jpg)  
FIG.1:The incline capillary rise

When the gravitational force is negligible，a wellknown Washburn's law can be obtained with the initial condition h(O) = 0: h = √ $\begin{array} { r } { h = \sqrt { \frac { a \sigma c o s \theta } { 2 \mu } } t } \end{array}$ /agcosθ t, which predicts burstlike behavior with the velocity being infinite at zero time. This singularity of the solution highlights a deep inconsistency of the above equation [2O]. Rideal [4] also obtained this equation through a rather simple derivation.

Taking into account the momentum of the liquid in the tube and end-effect drag on the fluid entering the tube, Brittin [6] derived a more rigorous formulations of the Lucas-Washburn equation,as follows: $\begin{array} { r } { h \frac { d ^ { 2 } h } { d t ^ { 2 } } + \frac { 5 } { 4 } ( \frac { d h } { d t } ) ^ { 2 } + } \end{array}$ $\begin{array} { r } { \frac { 8 } { \rho a ^ { 2 } } \mu h \frac { d h } { d t } + g h = \frac { 2 } { \rho a } \sigma \cos \theta } \end{array}$ ，where $\rho$ is density, $\mu$ is the viscosity, $\sigma$ is the liquid-air surface tension $\sigma = \gamma _ { L V }$ ， $\theta$ is the wetting angle of the liquid, $h$ is the height of capillary rise, $a$ is the capillary radius,and $g$ is the acceleration of gravity. This equation assumes the Poiseuille flow profile throughout the capillary.

The most popular equation of capillary rise dynamics 3 $\begin{array} { r } { h \frac { d ^ { 2 } h } { d t ^ { 2 } } + ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 } { \rho a ^ { 2 } } \mu h \frac { d h } { d t } + g h = \frac { 2 } { \rho a } \sigma \cos { \theta } } \end{array}$ μh+gh=2ocosθ.Although this equation has been widely used in the literature,it has a singularity of $t ~ = ~ 0$ ，namely $\begin{array} { r } { \begin{array} { r } { h \ = \ \frac { d h } { d t } \ \to \ \infty } \end{array} } \end{array}$ as $t  0$ ，which would lead to an ill-posed problem． This equation cannot even deal with the natural initial conditions $h ( 0 ) = \dot { h } ( 0 ) = 0$ ．A formal remedy is to take （204号 $\dot { h } ( 0 ) = \sqrt { 2 \sigma \cos \theta / ( \rho a ) }$ [5], neglecting such a logical drawback as the acceleration of the liquid front at zero time is infinite,hence hence more criticism of this equation can be found in [8, 20, 31].

This singularity problem was firstly pointed out by Szekely et al.[8],who successfully removed the singularity problem by composing the correct energy balance for the entry low: $\begin{array} { r } { ( h + \frac 7 6 a ) \frac { d ^ { 2 } h } { d t ^ { 2 } } + 1 . 2 2 5 ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 \mu } { \rho a ^ { 2 } } h \frac { d h } { d t } + g h = } \end{array}$ 2g cos 0. Xiao et al.[28] considered the entrance pressure loss effects by using Dreyer's model [13] and the dynamic contact angle effect by Newman's model [7] to further modify Lucas-Washburn's equation: $\begin{array} { r } { ( h + 1 . 0 2 8 a ) \frac { d ^ { 2 } h } { d t ^ { 2 } } + } \end{array}$ $\begin{array} { r } { 0 . 9 5 8 ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 \mu } { \rho a ^ { 2 } } ( h + 0 . 2 5 a ) \frac { d h } { d t } + g h = \frac { 2 \sigma } { \rho a } \cos { \theta } } \end{array}$ .Bush [36] derived a similar equation with a different coefficient of （204号 $\textstyle { \Bigl ( } { \frac { d h } { d t } } { \Bigr ) } ^ { 2 }$ ：

Despite researching capillary rise dynamics for centuries，no solution has yet been found.One should fisr obtain information for asymptotic regimes.Matching different solutions between the regimes has never been solved and,therefore remains an unsolved problem.It would be natural to think that one cannot satisfy those asymptotic solutions,and should hence seek a complete solution for the time domain. The following section focuses on Bush's model, including its series solution and approximate analytic solution.

To make the study self-contained,it is organised as follows:following the introduction,the next section presents Bush's formulated equation. Its series solution will then be obtained,and an approximate analytic solution will be proposed by using the initial conditions and the series solution. This will be followed by the numerical validation and as well as discussion thereof,and finally the study will be concluded.

capillarymay be expressed as

$$
\begin{array} { r l } & { \underbrace { ( \rho \pi a ^ { 2 } h } _ { i n e r t i a } + \underbrace { m _ { a } } _ { a d d e d m a s s } ) \ddot { h } = \underbrace { 2 \pi a \sigma \cos \theta } _ { c a p i l l a r y f o r c e } } \\ & { - \underbrace { \rho \pi a ^ { 2 } h g } _ { w e i g h t } - \underbrace { \pi a ^ { 2 } \frac { 1 } { 2 } \rho \dot { h } ^ { 2 } } _ { d y n a m i c a l p r e s s u r e } - \underbrace { 2 \pi a h \cdot \tau _ { \nu } } _ { v i s c o u s f o r c e } . } \end{array}
$$

We can estimate the added mass $m _ { a }$ from the change in kinetic energy as column rise from $h$ to $h + \Delta h$ ，namely $\Delta E _ { k } = { \textstyle { \frac { 1 } { 2 } } } \Delta ( m U ^ { 2 } )$ ，where $m = m _ { c } + m _ { 0 } + m _ { \infty }$ (mass in the column, in the spherical cap,and all other mass, respectively).In the column, $m _ { c } = \pi a ^ { 2 } h \rho$ ， $u = U$ ; in the spherical cap $\begin{array} { r } { m _ { 0 } = \frac { 2 \pi } { 3 } a ^ { 3 } \rho } \end{array}$ ; and intheouter regionradical flow extends to $\infty$ ,nut $u ( r )$ decays.Volume preservation requires: $\pi a ^ { 2 } U = 2 \pi a ^ { 2 } u _ { r } ( a )$ leads to $u _ { r } ( a ) = U / 2$ . Con$2 \pi a ^ { 2 } u _ { r } ( a ) = 2 \pi r ^ { 2 } u _ { r } ( r )$ ardyimte $u _ { r } ( r ) =$ $\begin{array} { r } { \frac { a ^ { 2 } } { r ^ { 2 } } u _ { r } ( a ) = \frac { a ^ { 2 } } { 2 r ^ { 2 } } U } \end{array}$   
is $\begin{array} { r } { { \frac { 1 } { 2 } } m _ { \infty } U ^ { 2 } \ = \ { \frac { 1 } { 2 } } \int _ { a } ^ { \infty } u _ { r } ( r ) ^ { 2 } d m \ = \ { \frac { 1 } { 2 } } \int _ { a } ^ { \infty } u _ { r } ( r ) ^ { 2 } \rho 2 \pi r ^ { 2 } d r } \end{array}$ ， which leads to $\begin{array} { r } { m _ { \infty } = \frac { 1 } { 2 } \rho \pi a ^ { 3 } } \end{array}$ . Hence the change in kinetic energy will be

$$
\begin{array} { l } { { \displaystyle \delta E _ { k } = \frac { 1 } { 2 } \Delta ( m _ { c } + m _ { 0 } + m _ { \infty } ) U ^ { 2 } + \frac { 1 } { 2 } m 2 U \Delta U } } \\ { { \displaystyle ~ = \frac { 1 } { 2 } \Delta m _ { c } U ^ { 2 } + \frac { 1 } { 2 } ( m _ { c } + m _ { 0 } + m _ { \infty } ) 2 U \Delta U } } \\ { { \displaystyle ~ = \frac { 1 } { 2 } \Delta ( \pi a ^ { 2 } \rho \Delta h ) U ^ { 2 } + ( \pi a ^ { 2 } h \rho + \frac { 7 } { 6 } \pi a ^ { 3 } \rho ) U \Delta U . } } \end{array}
$$

The added mass is estimated as $\begin{array} { r } { m _ { a } = m _ { 0 } + m _ { \infty } = \frac { 7 } { 6 } \pi a ^ { 3 } \rho } \end{array}$ For a typical capillary rise, $a = 1 0 ^ { - 4 } \sim 5 \times 1 0 ^ { - 4 } \mathrm { m } .$ $\mu =$

![](images/13031ee39e47db5cb7dd2e90e1829bca2c096184be905ec5cfc1f89499ea670d.jpg)  
FIG.2: The dynamics of capillary rise

# BUSH'SFORMULATIONSOFCAPILLARYRISE DYNAMICS

In physics the capillary dynamics process is a struggle between surface tension with the combining effect of wall resistance and gravity. In the initial stage the surface tension plays a leading role,and later the combined effect of wall resistance and gravity takes over.

Capillary rise dynamics is governed by a combination of gravity, viscosity, fluid inertia and dynamics pressure. In respect of continuum mechanics,the dynamics process must satisfy the conservation law of momentum: （204号 $\begin{array} { r } { \frac { d } { d t } [ m ( t ) \frac { d h ( t ) } { d t } ] = F + \int _ { S } \rho v \cdot v \cdot n d S } \end{array}$ ，where the second term on the right-hand side is the total momentum flux （204 $\pi a ^ { 2 } \rho \dot { h } ^ { 2 } = \dot { m } \dot { h }$ ，hence the force balance on the column

$1 . 5 \times 1 0 ^ { - 3 } \frac { \mathrm { K g } } { \mathrm { m s } }$ ， $\rho = 7 5 0 \mathrm { { k g m } ^ { - 3 } }$ and top velocity can be at $V \ = \ 0 . 0 4 \ \sim \ 0 . 7 7 8 \mathrm { m / s }$ ，hence the typical capillary rise Reynolds number $\begin{array} { r } { \mathrm { R e } = \frac { \rho V a } { \mu } = 1 0 \sim 1 9 5 } \end{array}$ At such lowReynolds number,if the tube is smooth one the flow in the tube is fully developed Poiseuille (laminar） flow, hence the viscous force is $\textstyle \tau _ { \nu } = - { \frac { 4 \mu } { a } } { \dot { h } }$ ：

Considering the above relations,the Bush equation of capillary rise dynamics was realised [36]:

$$
( h + \frac { 7 } { 6 } a ) \frac { d ^ { 2 } h } { d t ^ { 2 } } + \frac { 1 } { 2 } ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 \mu } { \rho a ^ { 2 } } h \frac { d h } { d t } + g h = \frac { 2 \sigma } { \rho a } \cos \theta .
$$

with initial height and velocity boundary conditions of $h ( 0 ) = 0$ ， $\dot { h } ( 0 ) = 0$

Although no solution of Eq.(3) was obtained, some segmental solutions (as shown in Figure 3) for asymptotic regimes were proposed by a reduced form of Eq.(3).

![](images/5e703bb99ab71d26730cd43188d63c51f7af2e6b2863bbaea5ed175f9892d13d.jpg)  
FIG. 3: Asymptotic regimes of capillary rise dynamics [36]

(1) Initial regime: h \~0,h \~ 0,infers h(t)= 12csθ, hence $\begin{array} { r } { h ( t ) ~ = ~ \frac { 6 } { 7 } \frac { \sigma \cos \theta } { \rho a ^ { 2 } } t ^ { 2 } } \end{array}$ (2） The quasi-steady stage (Lucas-Washburn equation)，where the capillary force was compensated by gravity and the viscous drag，the asymptotic solution corresponding to the short-time limit (t -→O) is given by h(t)= √a2μs ag cos0t. (3) Low-viscosity limit (Quéré equation),the capillary rise was given by $\textstyle h = { \sqrt { \frac { 2 \sigma \cos \theta } { \rho a } } }$ /2g cosθ. (4) The capillary liquid rose to a stationary level,ans was established by the balance of gravity and capillarity, hence H = 2g cos@.

However, those segmental solutions were not matched into a single solution that was valid for the whole time domain.

# SOLUTION OF BUSH'SEQUATIONOF CAPILLARYRISEDYNAMICS

Eq.(3) is a nonlinear ordinary differential equation,and until now no closed form solution has been found. Fortunately, it has Taylor's series solution $\begin{array} { r } { h ( t ) = \sum _ { n = 0 } ^ { \infty } c _ { n } t ^ { n } } \end{array}$ which is as follows

$$
\begin{array} { l } { { h ( t ) = \displaystyle \frac { 6 \sigma \cos \theta } { 7 \rho a ^ { 2 } } t ^ { 2 } - \frac { 3 \sigma \cos \theta ( 7 g \rho a ^ { 2 } + 2 4 \sigma \cos \theta ) } { 3 4 3 \rho ^ { 2 } a ^ { 5 } } t ^ { 4 } } } \\ { { - \displaystyle \frac { 8 6 4 \mu \sigma ^ { 2 } \cos ^ { 2 } \theta } { 1 7 1 5 \rho ^ { 3 } a ^ { 7 } } t ^ { 5 } + { \cal O } ( t ^ { 6 } ) } } \end{array}
$$

The correctness of this solution was verified by using the symbolic mathematics software,Maple. To understand the effect of surface tension, gravity and viscosity, Bush's equation (3 was transformed into a dimensionless form, as follows:

$$
z \frac { d ^ { 2 } z } { d \tau ^ { 2 } } + \frac { 7 } { 1 2 } \frac { \mathrm { B o } } { \cos \theta } \frac { d ^ { 2 } z } { d \tau ^ { 2 } } + \frac { 1 } { 2 } ( \frac { d z } { d \tau } ) ^ { 2 } + 8 \left( \sqrt { \frac { \cos \theta } { \mathrm { B o } \cdot \mathrm { G a } } } \right) z \frac { d z } { d \tau } + z = 1 ,
$$

and the initial height and velocity boundary conditions were changed to $z ( 0 ) ~ = ~ 0 , { \dot { z } } ( 0 ) ~ = ~ 0$ .In which, $z \ =$ $\textstyle { \frac { h } { H } }$ H，T $\textstyle \tau \ = \ { \frac { t } { T } }$ ， $\begin{array} { r } { H \mathrm { ~ = ~ } \frac { 2 \sigma \cos \theta } { \rho g a } } \end{array}$ $T = { \sqrt { \frac { H } { g } } }$ H,the Bond number $\begin{array} { r } { \mathrm { B o } \ = \ \frac { \rho g a ^ { 2 } } { \sigma } } \end{array}$ represents the ratio of gravity and surface tension,and the Galileo number $\begin{array} { r } { \mathrm { G a } = \frac { \rho ^ { 2 } g a ^ { 3 } } { \mu ^ { 2 } } } \end{array}$ represents the ratio of gravity and viscosity.

To express a fair quantitative understanding,we can rewrite the series solution in terms of Bo and Ga as follows

$$
\begin{array} { c } { { z ( \tau ) = \displaystyle \frac { 1 } { \mathrm { B o } ^ { \mathrm { ( } } \frac { 6 } { 7 } \cos \theta ) \tau ^ { 2 } - \frac { 1 } { \mathrm { B o } ^ { \mathrm { 2 } } } ( \frac { 4 2 } { 3 4 3 } \cos ^ { 2 } \theta ) \tau ^ { 4 } } } } \\ { { - \displaystyle \frac { 1 } { \mathrm { B o } ^ { 3 } } ( \frac { 1 4 4 } { 3 4 3 } \cos ^ { 3 } \theta ) \tau ^ { 4 } } } \\ { { - \displaystyle \frac { 1 } { \mathrm { B o } ^ { 3 } } \cos ^ { 3 } \theta \left( \sqrt { \frac { \cos \theta } { \mathrm { B o } \cdot \mathrm { G a } } } \right) \tau ^ { 5 } + { \cal O } ( \tau ^ { 6 } ) } } \end{array}
$$

Qualitatively speaking，Eq.(6) reveals that the Bond number,Bo,plays a vital role in capillary rise dynamics,because it stands for the ratio of gravity and surface tension.In the beginning(within the diffusion time $\frac { a ^ { 2 } } { \nu }$ ） the surface tension competes mainly with gravity,while after the diffusion time the viscous drag will come up against the surface tension.In other words, from the start of the capillary rise,the Bond number,Bo,enters the process, followed the Galileo number,Ga.

The solution in Eq.(4) provides an important result, namely the non-zero initial acceleration h(O)= 12 gcosθ, which will later be used in the proposal of the approximate analytic solution.With the above solution in Eq.(4),there is no longer a need to divide the capillary dynamics process into several asymptotic regimes,since the solution in Eq.(4) is valid for the entire time domain. From Eqs.(6 and 4) we can see that the Bond number, Bo,is vital for the solution. Without the added mass term $\textstyle { \frac { 7 } { 6 } } a$ , the equations will have zero Bond number,which will lead to infinite height and velocity. This is the source of singularity.

The academic value of the series solution enables one to realise the importance of the added mass,which can void the singularity. However, the rate of convergence of this solution is slow and useless for practical application. It would be natural to propose a simple solution for the capillary rise dynamics.

# APPROXIMATEANALYTICALSOLUTION

Generally speaking, the entire dynamics process can be qualitatively described as follows: in an infinite reservoir the capillary rise and the velocity are zero in the initial state. Due to the effect of the surface tension, the capillary liquid obtains initial acceleration (the initial acceleration must never be zero),and begins to rise at a relatively uniform velocity, while the surface tension plays a dominant role in the ascending phase; however, as the capillary rises,wall frictions and gravity begin to work in an attempt to prevent the rise of the capillaries, and their joint action succeeds in decelerating the capillaries at a point until the capillaries are finally stopped. Surface tension and wall resistance as well as gravity to achieve unity of opposites,and the capillary dynamics process are over,and attributed to calm.

From a physical perspective of the capillary rising phenomena, the capillary liquid will rise to a stationary level,established by the balance of gravity and capillarity, while the height and velocity will tends to $h  H =$ 2g cosθ and h → O at t → oo,respectively. To satisfy the conditions,we can propose that the capillary rise takes the following form

$$
h ( t ) = H [ 1 - f ( t ) e ^ { - \beta t } ] ,
$$

where the exponent $\beta$ and function $f ( t )$ should be determined.

Substituting the Eq.(7) and $\dot { h } ( t ) ~ = ~ - H f ^ { \prime } ( t ) e ^ { - \beta t } +$ $H \beta f ( t ) e ^ { - \beta t }$ into the initial conditions $h ( 0 ) = 0$ ， $\dot { h } ( 0 ) =$ $0$ ,while the initial condition for the function $f ( t )$ is given by

$$
f ( 0 ) = 1 , f ^ { \prime } ( 0 ) = \beta .
$$

There are many possibilities for the construction of $f ( t )$ ， which can satisfy the condition in Eq.(8)；for instance, （20 $f ( t ) = 1 + \beta t + \alpha t ^ { d }$ , in which the exponent $d > 2$ and $\alpha$ is a constant. Since the capillary rise dynamics process usually takes a millisecond, the lower order of time $t$ will dominate the process,and based on this understanding, we set the function $f ( t ) = 1 + \beta t + \alpha t ^ { 3 }$ ．Hence,the capillary rise can be proposed as follows

$$
h ( t ) = H [ 1 - ( 1 + \beta t + \alpha t ^ { 3 } ) e ^ { - \beta t } ] .
$$

Thus,we have capillary velocity $\dot { h } ( t ) = H ( \alpha \beta t ^ { 2 } - 3 \alpha t +$ $\beta ^ { 2 } ) t e ^ { - \beta t }$ and acceleration $\ddot { h } ( t ) ~ = ~ - H ( \alpha \beta ^ { 2 } t ^ { 3 } + \beta ^ { 3 } t ~ -$ （204 $6 \alpha \beta t ^ { 2 } + 6 \alpha t - \beta ^ { 2 } ) e ^ { - \beta t }$ ：

The capillary rise in Eq.(9) satisfies both initial conditions and infinity conditions. The unknown constants $\beta$ can be determined by the Taylor's series solution in Eq.(4)，which gives the acceleration $\begin{array} { r } { \ddot { h } ( 0 ) = \frac { 1 2 } { 7 } \frac { \sigma \cos \theta } { \rho g a ^ { 2 } } H } \end{array}$ Hence,by equaling $\ddot { h } ( 0 ) = H \beta ^ { 2 }$ ，we obtain the exponent

$$
\beta = \sqrt { \frac { 1 2 } { 7 H } \frac { \sigma \cos \theta } { \rho g a ^ { 2 } } } = \sqrt { \frac { 6 g } { 7 a } } .
$$

To find the parameter $\alpha$ we can expand the capillary rise in Eq.(9) in the Taylor series,and obtain its coefficient of the fifth order team of $t ^ { 5 }$ as $- \textstyle { \frac { 1 } { 3 0 } } H \beta ^ { 2 } ( \beta ^ { 3 } + 1 5 \alpha )$ ,and let it equal the coefficient of $t ^ { 5 }$ in Eq.(4),namely

$$
- \frac { 1 } { 3 0 } { \cal H } \beta ^ { 2 } ( \beta ^ { 3 } + 1 5 \alpha ) = - \frac { 8 6 4 } { 1 7 1 5 } \frac { \mu \sigma ^ { 2 } \cos ^ { 2 } \theta } { \rho ^ { 3 } a ^ { 7 } } ,
$$

which gives

$$
\alpha \approx \frac { 7 \mu \sigma \cos { \theta } } { 1 2 \rho ^ { 2 } a ^ { 5 } } - \frac { 1 } { 1 5 } \left( \sqrt { \frac { 6 g } { 7 a } } \right) ^ { 3 } .
$$

It is clear that $\alpha$ is crucial parameter,which links the capillary rise dynamics, to all constants.It is worth mentioning an interesting aspect,namely that $\alpha$ can be set to zero by adjusting the radius as a = 2(²²cos@)1/7.

Finally, we obtain the capillary rise $h ( t )$

$$
h ( t ) = \frac { 2 \sigma \cos { \theta } } { \rho g a } \left. 1 - \left[ 1 + \left( \sqrt { \frac { 6 g } { 7 a } } \right) t + \alpha t ^ { 3 } \right] e ^ { - \left( \sqrt { \frac { 6 g } { 7 a } } \right) t } \right. ,
$$

and the capillary velocity $\dot { h } ( t )$

$$
\frac { d h ( t ) } { d t } = \frac { 2 \sigma \cos { \theta } } { \rho g a } \left( \alpha t ^ { 2 } \sqrt { \frac { 6 g } { 7 a } } - 3 \alpha t + \frac { 6 g } { 7 a } \right) t e ^ { - \left( \sqrt { \frac { 6 g } { 7 a } } \right) t } ,
$$

as well as the capillary acceleration $\ddot { h } ( t )$

The above solutions in Eqs.(13) and (14) are valid for the entire time domain $t \in [ 0 , \infty )$ ，which to the author's knowledge,has never been proposed in the lieterature.

The solution in Eq.(13) reveals that the capillary rise h(t) is mainly controlled by the H = 2gcosθ with the decay rate of e−( (√)t，where the radius α is the onlydominate parameter,and the smaller radius the fast decay.

# NUMERICALVALIDATION

# Validation of the solution in Eq.(13)

To validate the correctness of the solution in Eq.(13), we can compare the result obtained numerically by Zhmud et al.[2O]. For a comparative study, the data of the diethyl ether in glass is shown in the table below I.

TABLEI: The diethyl ether in glass with arbitrary radius   

<html><body><table><tr><td>μ kg ms</td><td></td><td></td><td></td><td></td><td>g[]</td><td>p kg</td></tr><tr><td>2.2 10</td><td>1.67· 10</td><td></td><td>26</td><td></td><td>9.81</td><td>m3 710</td></tr></table></body></html>

In this case, for any radius $a$ ，we have the capillary rise $\begin{array} { r } { H = { \frac { 4 . 3 1 } { a } } \cdot 1 0 ^ { - 6 } } \end{array}$ , hence the analytical capillary rise is given by

$$
\begin{array} { l } { { \displaystyle h ( t ) = \frac { 4 . 3 1 \cdot 1 0 ^ { - 6 } } { a } \{ 1 - } }  \\ { { \displaystyle [ 1 + \frac { 2 . 9 } { \sqrt { a } } t + ( \frac { 3 . 8 2 1 \cdot 1 0 ^ { - 1 2 } } { a ^ { 5 } } - \frac { 1 . 6 2 6 } { a ^ { 3 / 2 } } ) t ^ { 3 } ] e ^ { - \frac { 2 . 9 } { \sqrt { a } } t } \} . } } \end{array}
$$

If we set the radius $a = 0 . 0 0 0 5$ ,we have the capillary rise as follows

$$
h ( t ) = 0 . 0 0 8 6 2 \left[ 1 - ( 1 + 1 2 9 . 6 8 t - 2 3 1 1 2 . 5 4 t ^ { 3 } ) e ^ { - 1 2 9 . 6 8 t } \right] ,
$$

which is illustrated in the Figure 4. This figure shows that our solution agrees with [20].

![](images/eac368b97feabfb959777ed02b156157db8c6018e183231d3883c8a534056644.jpg)  
FIG.4: Comparison study: $a = 0 . 0 0 0 5 m$ and $\theta = 2 6 ^ { 0 }$

![](images/d84be4ee2b2876dfb4dfcb0c363adcdde83ff861830de7e15177f3f324c169e2.jpg)  
FIG.6:Acceleration profile for $a = 0 . 0 0 0 5 m$ and $\theta = 2 6 ^ { 0 }$ （204号

The capillary rise velocity is given by

$$
\dot { h } ( t ) = - 2 5 8 3 6 t ( t + 0 . 0 6 ) ( t - 0 . 0 8 ) e ^ { - 1 2 9 . 6 8 t } .
$$

which is illustrated in the Figure 5.The capillary rise

Therefore,the glass tube radius is a crucial parameter for capillary rise dynamics.

![](images/1cf8d806c73cc204adeb5d3780220348eafe7944bfba4fc509953322510f323b.jpg)  
FIG.5:Velocity profile for $a = 0 . 0 0 0 5 m$ and $\theta = 2 6 ^ { 0 }$

![](images/82554db7fdaad7e8143911073f90a2a0d6cf0a02c4dbbde3041c4c50f0c61f6a.jpg)  
FIG.7:The capillary rise of four different radius

acceleration is given by

$$
\ddot { h } ( t ) = 3 3 5 0 4 9 6 ( t + 0 . 0 0 6 ) ( t - 0 . 0 0 8 ) ( t - 0 . 0 9 6 ) e ^ { - 1 2 9 . 6 8 t } .
$$

which is illustrated in the Figure 6.

# Influence of radius change

By maintaining the wetting angle as $\theta = 2 6 ^ { 0 }$ [20],and adjusting the radius of the glass in Eq.(15),reveals the graphs that are shown in Figure 7,which shows that the capillary rise is sensitive to the radius.The smaller the radius in which the liquid can travel, the further it goes.

The radius also has a strong influence on the capillary velocityinFigure8and theacceleration,whichcanbeen seen in Figure 9.The smaller the radius,the faster the capillary moves.

# DISCUSSION AND CONCLUSION

Piecing all the pictures together,we see a fair clear picture of the capillary rise dynamics as follows: the capillary rise onsets from an initial zero height and velocity, at $t = 0$ , the surface tension,as the frst driving force, supplies a kick-off acceleration of $H \beta ^ { 2 }$ . This surface tension steadily drives the capillary rising at an almost uniform speed until it reaches its peak at a certain point; then the capillary speed is gradually reduced to zero after short oscillating owing to the combining effect of the wall viscous friction and gravity. At the same time, the capillary acceleration decreases and reaches its lowest point before it increases to its final static state.

![](images/5a2b8b0192cd7e133363f73644db4f9d9f13c7b03df2adf9350dadb26175a4c2.jpg)  
FIG.8:The capillary rise velocity for four different radius

![](images/25f1b5200cd3d78c0c2ca9bbd4e01e1b41cf2d1db2a323c9f1a6b957c7402108.jpg)  
FIG.9:The capillary rise acceleration for fourdifferent radius

Since the capillary rise generally has a low Reynolds number, the flow in the tube can be considered asa laminar flow. To avoid the singularity problem,the added mass must appear in the governing equation.From the dimensionless form of the Bush equation,we found that the capillary rise dynamics are mainly controlled by the Bond number and the Galileo number. We successfully obtained the Taylor series solution. Owing to the poor rate of convergence of this solution, we proposed a simple approximate analytic solution by using the Taylor series solution and initial conditions.We verified the proposed analytic solution by some numerical examples.

Last，but not least，it may be worth pointing out that all previous solutions were from the non-oscillatory regime,however,when the liquid surface reaches $h = H$ ， the surface will oscillate before asymptotically ending.

Within the oscillatory regime, the above solutions should be modified,which will be investigated by the Homotopy Analysis Method [26,34] in the forthcoming paper.

\* Electronic address: sunb@cput .ac.za   
[1]A.Einstein，Folgerungenaus den Capillaritätserscheinungen (Conclusions [drawn] from capillary phenomena)，Annalen der Physik,309 (3）: 513-523 (1901).   
[2] R. Lucas. Ueber das Zeitgesetz des kapillaren Aufstiegs von Flissigkeiten.Kolloid-Zeitschrift, 23:15-22 (1918).   
[3] E.W.Washburn. The dynamics of capillary flow.Physical Review,17(3):273-283 (1921).   
[4] E.K. Rideal. On the flow of liquids under capillary pressure.Philos. Mag. Ser.6,44:1152-1159 (1922).   
[5] C.H. Bosanquet. On the flow of liquids into capillary tubes.Philos.Mag.Ser.6,45:525-531 (1923).   
[6] W.E.Brittin.Liquid rise ina capillary tube,J.Applied Physics,17:37-45 (1946).   
[7] S. Newman. Kinetics of wetting of surfaces by polymers - capillary flow，J.of Colloid and Interface Science, 26(2)209-213 (1968).   
[8]J.Szekely,A.W.Neumann and Y.K.Chuang.The rate of capillary penetration and the applicability of the washburn equation. J. Colloid and Interface Science, 35,273- 278 (1971).   
[9] J.van Brakel and P.M. Heertjes.Capillary rise in porous media. Nature 254, 585-586 (1975).   
[10] S.Levine,P. Reed, E.J. Watson and G. Neale. A theory of the rate of rise of a liquid in a capillary.In M.Kerker,editor,J. Colloid and Interface Science,3:403-419. (Academic Press,New York,1976).   
[11] S. Levine, J.Lowndes, E.J.Watson and G. Neale.A theory of capillary rise of a liquid in a vertical cylindrical tube and in a parallel-plate channel. J. Colloid and Interface Science,73(1):136-151 (1980).   
[12] A.Marmur.Penetration and displacement in capillary systems of limited size.Adv. Colloid Interface Sci.,39:13- 33 (1992).   
[13] M. Dreyer,A.Delgado and H.J. Rath. Fluid motion in capillary vanes under reduced gravity,Microgravity Science and Technology,4:203-210 (1993).   
[14] N.Ichikawa and Y. Satoda. Interface dynamics of capillary flow in a tube under negligible gravity condition.J. Colloid and Interface Science,162:350-355 (1994).   
[15] T.Delker,D.B. Pengra and P.-Z. Wong. Interface pinning and the dynamics of capillary rise in porous media. Physical Review Letters,76(16):2902-2905 (1996).   
[16] A.Marmur and R.D.Cohen.Characterization of porous media by the kinetics of liquid penetration: The vertical capillaries model. J. Colloid and Interface Science, 189(2):299-304, (1997).   
[17] R.D.Deegan,Olgica Bakajin,T.F.Dupont,G. Huber,S.R. Nagel and T.A.Witten. Capillary flowasthe cause of ring stains from dried liquid drops,Nature 389, 827 - 829 (1997).   
[18] D. Quere.Inertial capillarity. Europhys. Lett.,39(5):533- 538 (1997).   
[19] J.Fisher.Physics takes the biscuit，Nature，397,469 (1999).   
[20] B.V.Zhmud，F．Tiberg，K.Hallstensson.DynamicS of capillary rise. J. Colloid and Interface Science, 228(2):263-269 (2000).   
[21]A.Siebold,M.Nardin,J.Schultz,A.Walliser and M. Oppliger.Effect of dynamic contact angle on capillary rise phenomena.Colloids and Surfaces A,161(1):81-87 (2000).   
[22]M.Lago and M.Araujo.Capillary rise in porous media. Physica A, 289:1-17 (2001).   
[23] J.Bico and D.Qur,Rise of liquids and bubbles in angular capillary tubes.J.Colloid Interface Sci. 247:162-166 (2002).   
[24] A.Hamraoui and T.Nylander.Analytical approach for the Lucas- Washburn equation.J.Colloid and Interface Science,250:415-421 (2002).   
[25] P.G.de Gennes,F.Brochard-Wyart and D.Quéré. Capillarity and Wetting Phenomena:Drops,Bubbles,Pearls, Waves. (Springer,New York,2003).   
[26] S.J.Liao,Beyond Perturbation: Introduction to the Homotopy Analysis Method,Chapman& Hall/CRC,Boca Raton,2003.   
[27]C.J.Lv,C.Chen,Y.C.Chuang,F.G. Tseng,Y.J.Yin, F.Grey,and Q.S.Zheng.Substrate curvature gradient drives rapid droplet motion,Phys.Rev.Lett.113, 026101 (2014).   
[28] Y.Xiao,F.Yang and R.Pitchumani,A generalized analysis of capillary flows in channels,J.Colloid and Interface Science,Vol. 298,pp:880-888 (2006).   
[29]J.W.M.Bush and D.L.Hu.Walking on Water:Biolocomotion at the Interface,Annu.Rev.Fluid Mech.,38:339- 36 (2006).   
[30]C.Hall and W.Hoff.Rising damp: capillary rise dynamics in walls.Proc.R. Soc.A 463(2007).   
[31] N. Fries and M.Dreyer.An analytic solution of capillary rise restrained by gravity,320,1:259-263 (2008).   
[32] F.J.Higuera,A.Medina and A.Linan.Capillary rise of a liquid between two vertical plates making a small angle. Phys.Fluids 20,102102,1871-1884(2008)   
[33]A.Ponomarenko，D.Quéré and C.Clanet．A universal law for capillary rise in corners,J.Fluid Mech.,vol. 666:146-154 (2011).   
[34] S.J.Liao,Homotopy Analysis Method in Nonlinear Differential Equations,Springer-Verlag,New York,2011.   
[35]Y.P.Zhao.Physical Mechanics of Surface and Interface (in Chinese)(Science Press,Beijing,2012).   
[36] W.M.Bush.Interfacial Phenomena,MIT Open Course (2013).   
[37]O.Shardt，P.R.Waghmare，J.J.Derksena and S.K. Mitrab.Inertial rise in short capillary tubes,RSC Adv., 4:14781-14785 (2014).   
[38] Jian-Lin Liu,Xi-Qiao Feng,Re Xia and Hong-Ping Zhao. Hierarchical capillary adhesion of microcantilevers or hairs. Journal of Physics D: Applied Physics 40(18):5564 (2007).