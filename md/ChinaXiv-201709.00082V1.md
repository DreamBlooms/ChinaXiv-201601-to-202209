# On Solution of Capillary Rise Dynamics

Bohua Sun1 （204号 $^ { 1 }$ Cape Peninsula University of Technology， Cape Town， South Africa \* (Dated:September 11,2017)

Capillary rise is one of the most well-known and vivid illustrations of capillarity, however,there is no complete solution has been obtained except some segmental solutions for asymptotic regimes.In this paper, we use singularity-free Bush's equation and successfully obtain its series and perturbation solutions.The solutions reveal that the capillary rise dynamics is mainly controlled by the Bond number and the Galileo number,of which the Bond number is a key parameter on the existence of the solution. Due to the poor rate of convergence of the series solution, we propose an approximate t where $\alpha$ is a parameter. The proposed analytic solution has been verified numerically.

PACS numbers:68.03.Cd,68.03.Kn,47.55.nb Keywords:capillary rise dynamics,surface tension,gravity,viscosity,singularity

# INTRODUCTION

Capillary rise is one of the most well-known and vivid illustrations of capillarity. Knowledge of capillarity laws isimportant in oil recovery,civil engineering，dyeing of textile fabrics,ink printing,and a variety of other fields. It is the capillarity that brings water to the upper layer of soils,drives sap in plants,or lays the basis for operation of pens [1-25,27-33,35-38]. The capillary action has been studied by numbers of masters in science.Leonardo da Vinci(1452-1519) recorded the effect in his notes and proposed that mountain streams may result from capillary rise through a fine network of cracks. Jacques Rohault (1620-1675): erroneously suggested that capillary rise is due to suppression of air circulation in narrow tube and creation of a vacuum.Geovanni Borelli (1608-1675) demonstrated experimentally that $h \sim 1 / a$ Geminiano Montanari(1633-87) attributed circulation in plants to capillary rise. Francis Hauksbee(17oOs） conducted an extensive series of capillary rise experiments reported by Newton in his Opticks but was left unattributed. James Jurin （1684-1750） independently confirmed $h \sim 1 / a$ ； hence Jurin's Law.Albert Einstein,whose first paper was submitted to Annalen der Physik in 19oo,was on capillarity [1].

Washburn [3] developed the equation to describe the rate of penetration of liquids into small cylindrical capillaries based the laws of hydraulics. He assumed that the distance traveling in the initial turbulence period is negligible,and the Poiseuille region covers practically the entire flow.According to Poiseuille's law,neglecting the airresistance,the rate of flow through a cylindrical takes the followin form: $\begin{array} { r } { Q = \frac { \pi \Delta P } { 8 \mu h } ( a ^ { 4 } + L _ { s } a ^ { 2 } ) } \end{array}$ ，where $a$ is the radius of the tube, $h$ is the capillary penetration height, $L _ { s }$ is the slip length. $\mathrm { Q }$ is the rate of flow and for a cylindrical tube it is given by $Q \ : = \ : \pi a ^ { 2 } \frac { d h } { d t }$ .The total effective pressure $\Delta P$ ， consists of the external pressure $P _ { e }$ ，the hydrostatic pressure $P _ { h }$ and the capillary pressure given by Young-Laplace equation △P = 2gcosθ. Combining the above relations and neglecting the slip length gives the so-called Lucas-Washburn equation: $\begin{array} { r } { \frac { d h } { d t } = \frac { a ^ { 2 } } { 8 \mu h } ( P _ { a } + P _ { h } + \frac { 2 \sigma c o s \theta } { a } ) } \end{array}$ .If there is noexteral pres sure,a commonly used form of Lucas-Washburn equation is given by $\begin{array} { r } { 8 \mu h \frac { d h } { d t } + \rho g h a ^ { 2 } s i n \psi = 2 a \sigma c o s \theta } \end{array}$ where $\psi$ is the incline angle of the tube with respect to the horizontal surface.

![](images/31f8ad6c8b5229abc8abc803c121637425b3f650f37ed626777b60633f915825.jpg)  
FIG.1:The incline capillary rise

When the gravitational force is negligible，a wellknown Washburn'slaw can be obtained with initial condition $h ( 0 ) = 0$ ： $\begin{array} { r } { h = \sqrt { \frac { a \sigma c o s \theta } { 2 \mu } t } } \end{array}$ agcosθt, which predicts burst-like behavior with the velocity being infinite at zero time.

This singularity of the solution highlights a deep inconsistency of the above equation [2O].Rideal [4] also obtained this equation through a rather simple derivation.

Taking into account of the momentum of the liquid in the tube and end-effect drag on the fluid entering the tube,Brittin [6] derived a more rigorous formulations of Lucas-Washburn equation as follows: $\begin{array} { r } { h \frac { d ^ { 2 } h } { d t ^ { 2 } } + \frac { 5 } { 4 } ( \frac { d h } { d t } ) ^ { 2 } + } \end{array}$ $\begin{array} { r } { \frac { 8 } { \rho a ^ { 2 } } \mu h \frac { d h } { d t } + g h = \frac { 2 } { \rho a } \sigma \cos \theta } \end{array}$ ,where $\rho$ is density, $\mu$ is the viscosity, $\sigma$ is the liquid-air surface tension $\sigma = \gamma _ { L V }$ ， $\theta$ is the wetting angle of the liquid, $h$ is the height of capillary rise, $a$ is the capillary radius,and $g$ is the acceleration of gravity. This equation assumes the Poiseuille flow profile throughout the capillary.

The most papular equation of capillary rise dynamics 3 $\begin{array} { r } { h \frac { d ^ { 2 } h } { d t ^ { 2 } } + ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 } { \rho a ^ { 2 } } \mu h \frac { d h } { d t } + g h = \frac { 2 } { \rho a } \sigma \cos { \theta } } \end{array}$ Although this equation has been widely used in the literature,however it has a singularity at $t = 0$ ，namely $\begin{array} { r } { \dot { h } = \frac { d h } { d t }  \infty } \end{array}$ （20 as $t  0$ ，which would lead to an ill-posed problem.This equation can not even deal with the natural initial conditions $h ( 0 ) = \dot { h } ( 0 ) = 0$ ．A formal remedy is to take （204号 $\dot { h } ( 0 ) = \sqrt { 2 \sigma \cos \theta / ( \rho a ) }$ [5], neglecting such a logical drawback as the acceleration of liquid front at zero time being infinite,more criticism on this equation can be found in [8, 20, 31].

This singularity problem was firstly pointed out by Szekely et al.[8],who successfully removed the singularity problem by composing the correct energy balance for the entry flow: $\begin{array} { r } { ( h + \frac { 7 } { 6 } a ) \frac { d ^ { 2 } h } { d t ^ { 2 } } + 1 . 2 2 5 ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 \mu } { \rho a ^ { 2 } } h \frac { d h } { d t } + g h = } \end{array}$ （20 ${ \frac { 2 \sigma } { \rho a } } \cos \theta$ . Xiao et al.[28] considered the entrance pressure loss effects by using Dreyer's model [13] and dynamic contact angle effect by Newman's model [7] to further modifed Lucas-Washburn equation: $\begin{array} { r } { ( h + 1 . 0 2 8 a ) \frac { d ^ { 2 } h } { d t ^ { 2 } } + } \end{array}$ $\begin{array} { r } { 0 . 9 5 8 ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 \mu } { \rho a ^ { 2 } } ( h + 0 . 2 5 a ) \frac { d h } { d t } + g h = \frac { 2 \sigma } { \rho a } \cos { \theta } } \end{array}$ .Bush [36] derived a similar equation with a different in the coefficient of $\textstyle { \bigl ( } { \frac { d h } { d t } } { \bigr ) } ^ { 2 }$ ：

For centuries of investigation on the capillary rise dynamics,it is incredible that no complete solution has been obtained yet.Ones have to find some information for asymptotic regimes. How to match the different solutions between the regimes has never been solved and still remains as an unsolved problem. It would be natural thinking that ones can not satisfy those asymptotic solutions,and must be looking for a complete solution that can cover whole domain of time.In the following,we will mainly focus on Bush's model and give its series solution and approximate analytic solution.

To make the paper self-contained,the paper is organised as follows. After this introduction，in Section 2 the Bush's equation has been formulated.In Section 3 the perturbation solution and the series solution are obtained. In Section 4 an approximate analytic solution is proposed by using the initial conditions and the series solution.In Section 5 the numerical verification and discussions have been presented. Finally, section 6 concludes the paper.

# BUSH'SFORMULATIONSOFCAPILLARYRISE DYNAMICS

In physics, the capillary dynamics process is a struggle between surface tension with the combining effect of wall resistance and gravity. In the initial stage, the surface tension plays a leading role,and later the combining effect of wall resistance and gravity takes over.

Capillary rise dynamics is governing by a combination of gravity, viscosity,fluid inertia and dynamics pressure. From continuum mechanics,the dynamics process must satisfy the conservation law of momentum: $\begin{array} { r } { \frac { d } { d t } [ m ( t ) \frac { d h ( t ) } { d t } ] = F + \int _ { S } \rho v \cdot v \cdot n d S } \end{array}$ ， where the second term on the right-hand side is the total momentum flux $\pi a ^ { 2 } \rho h ^ { 2 } = { \dot { m } } { \dot { h } }$ , so the force balance on the column capillary may be expressed as

$$
\begin{array} { r l } { { ( \underbrace { \rho \pi a ^ { 2 } h } _ { i n e r t i a } + \underbrace { m _ { a } } _ { a d d e d m a s s } ) \ddot { h } = \underbrace { 2 \pi a \sigma \cos \theta } _ { c a p i l l a r y f o r c e } - \underbrace { \rho \pi a ^ { 2 } h g } _ { w e i g h t } } } & { { } } \\ { { } } & { { - \underbrace { \pi a ^ { 2 } \frac { 1 } { 2 } \rho \dot { h } ^ { 2 } } _ { d y n a m i c a l p r e s s u r e } - \underbrace { 2 \pi a h \cdot \tau _ { \nu } } _ { v i s c o u s f o r c e } . } } \end{array}
$$

We can estimate the added mass $m _ { a }$ from the change in kinetic energy as column rise from $h$ to $h + \Delta h$ ,namely $\begin{array} { r } { \Delta E _ { k } = \frac { 1 } { 2 } \Delta ( m U ^ { 2 } ) } \end{array}$ ,where $m = m _ { c } + m _ { 0 } + m _ { \infty }$ (mass in the column, in the spherical cap and all other mass,respectively). In the column, $m _ { c } = \pi a ^ { 2 } h \rho$ ， $u = U$ ; in the spherical cap, $\begin{array} { r } { m _ { 0 } = \frac { 2 \pi } { 3 } a ^ { 3 } \rho } \end{array}$ ； and in theouter region,radical flow extends to $\infty$ ，nut $u ( r )$ decays.Volume preservation requires: $\pi a ^ { 2 } U = 2 \pi a ^ { 2 } u _ { r } ( a )$ leads to $u _ { r } ( a ) = U / 2$ . Continuity gives $2 \pi a ^ { 2 } u _ { r } ( a ) = 2 \pi r ^ { 2 } u _ { r } ( r )$ and leads to $u _ { r } ( r ) =$ $\begin{array} { r } { \frac { a ^ { 2 } } { r ^ { 2 } } u _ { r } ( a ) = \frac { a ^ { 2 } } { 2 r ^ { 2 } } U } \end{array}$ .Thus the kinetic energy inthefarfeld is $\begin{array} { r } { { \frac { 1 } { 2 } } m _ { \infty } U ^ { 2 } \ = \ { \frac { 1 } { 2 } } \int _ { a } ^ { \infty } u _ { r } ( r ) ^ { 2 } d m \ = \ { \frac { 1 } { 2 } } \int _ { a } ^ { \infty } u _ { r } ( r ) ^ { 2 } \rho 2 \pi r ^ { 2 } d r } \end{array}$ ， which leads to $\begin{array} { r } { m _ { \infty } = \frac { 1 } { 2 } \rho \pi a ^ { 3 } } \end{array}$ . Hence the change in ki

netic energy will be

$$
\begin{array} { l } { { \displaystyle \delta E _ { k } = \frac { 1 } { 2 } \Delta ( m _ { c } + m _ { 0 } + m _ { \infty } ) U ^ { 2 } + \frac { 1 } { 2 } m 2 U \Delta U } } \\ { { \displaystyle ~ = \frac { 1 } { 2 } \Delta m _ { c } U ^ { 2 } + \frac { 1 } { 2 } ( m _ { c } + m _ { 0 } + m _ { \infty } ) 2 U \Delta U } } \\ { { \displaystyle ~ = \frac { 1 } { 2 } \Delta ( \pi a ^ { 2 } \rho \Delta h ) U ^ { 2 } + ( \pi a ^ { 2 } h \rho + \frac { 7 } { 6 } \pi a ^ { 3 } \rho ) U \Delta U . } } \end{array}
$$

The added mass is estimated as $\begin{array} { r } { m _ { a } = m _ { 0 } + m _ { \infty } = \frac { 7 } { 6 } \pi a ^ { 3 } \rho } \end{array}$ For a typical capillary rise, $a = 1 0 ^ { - 4 } \sim 5 \times 1 0 ^ { - 4 } \mathrm { m }$ ， $\mu =$

![](images/a1b67db90d12e65054b61953ba52f5989c4c41a93f7bae735c9eab52ca59da13.jpg)  
FIG.2:The dynamics of capillary rise

![](images/f7f34fa188a68b95edf2e7da237d0a149240bba1288419489fed3f7a6cbb2849.jpg)  
FIG.3:Asymptotic regimes of capillary rise dynamics [36]

However， those segmental solutions have not been matched into a single solution that valid for whole domain of time.

# SOLUTION OFBUSH'S EQUATION OF CAPILLARYRISEDYNAMICS

# Perturbation solution

1.5 ×10-3Kg， 3g,ρ = 750kgm-³ and top velocity can be at $V \ = \ 0 . 0 4 \ \sim \ 0 . 7 7 8 \mathrm { m / s }$ ，hence the typical capillary rise Reynolds number $\mathrm { R e } = { \frac { \rho V a } { \mu } } = 1 0 \sim 1 9 5$ . At such low Reynolds number,if the tube is smooth one the flow in the tube is fully developed Poiseuille (laminar) flow, hence the viscous force is $\textstyle \tau _ { \nu } = - { \frac { 4 \mu } { a } } { \dot { h } }$ ：

Combining all above relations,we have Bush equation of capillary rise dynamics [36]:

$$
( h + \frac { 7 } { 6 } a ) \frac { d ^ { 2 } h } { d t ^ { 2 } } + \frac { 1 } { 2 } ( \frac { d h } { d t } ) ^ { 2 } + \frac { 8 \mu } { \rho a ^ { 2 } } h \frac { d h } { d t } + g h = \frac { 2 \sigma } { \rho a } \cos \theta .
$$

and initial height and velocity boundary conditions $h ( 0 ) = 0$ ， $\dot { h } ( 0 ) = 0$

Although no complete solution of Eq.(3) has never been obtained,some segmental solutions (as shown in Figure 3) for asymptotic regimes have been proposed by reduced form of Eq.(3). (1) Initial regime: $h \sim 0$ ， $\boldsymbol { \dot { h } } \sim \boldsymbol { 0 }$ ， infers $\begin{array} { r } { \ddot { h } ( t ) = \frac { 1 2 } { 7 } \frac { \sigma \cos \theta } { \rho a ^ { 2 } } } \end{array}$ , hence $\begin{array} { r } { h ( t ) = \frac { 6 } { 7 } \frac { \sigma \cos \theta } { \rho a ^ { 2 } } t ^ { 2 } } \end{array}$ . (2) Quasisteady stage (Lucas-Washburn equation),where the capillary force is compensated by gravity and viscous drag, the asymptotic solution corresponding to the short-time limit (t → O) is given by h(t) = √ $\begin{array} { r } { h ( t ) ~ = ~ \sqrt { \frac { a \sigma \cos \theta } { 2 \mu } t } } \end{array}$ ag cos0t.(3) Lowviscosity limit (Quéré equation), the capillary rise is given by $\textstyle h = { \sqrt { \frac { 2 \sigma \cos \theta } { \rho a } } }$ 2σ cosθ.(4) The capillary liquid will rise to stationary level, established by the balance of gravity and capillarity, it gives H = 2g cosθ.

Bush's equation (3) can also be transferred into a dimensionless form as follows:

$$
z \frac { d ^ { 2 } z } { d \tau ^ { 2 } } + \frac { 7 } { 1 2 } \frac { \mathrm { B o } } { \cos \theta } \frac { d ^ { 2 } z } { d \tau ^ { 2 } } + \frac { 1 } { 2 } ( \frac { d z } { d \tau } ) ^ { 2 } + \frac { 1 6 \cos \theta } { \mathrm { B o } \cdot \mathrm { G a } } z \frac { d z } { d \tau } + z - 1 = 0 ,
$$

and the initial height and velocity boundary conditions are changed to $z ( 0 ) = 0$ ， $\dot { z } ( 0 ) = 0$ . In which, $\begin{array} { r } { z = \frac { h } { H } } \end{array}$ ， $\tau =$ $\textstyle { \frac { t } { T } }$ ， $\begin{array} { r } { H \mathrm { ~ = ~ } \frac { 2 \sigma \cos \theta } { \rho g a } } \end{array}$ ， $T \ = \ { \sqrt { \frac { H } { g } } }$ ， Bond number $\begin{array} { r } { \mathrm { B o } \ = \ \frac { \rho g a ^ { 2 } } { \sigma } } \end{array}$ represents the ratio of gravity and surface tension,and Galileo number $\begin{array} { r } { \mathrm { G a } = \frac { \rho ^ { 2 } g a ^ { 3 } } { \mu ^ { 2 } } } \end{array}$ represents the ratio of gravity and viscosity.

From the Eq.(4),we can notice that the Bond number Bo is playing a vital role in capillary rise dynamics, because it stands for the ratio of gravity and surface tension. In the very beginning (within the diffusion time （204号 $\frac { a ^ { 2 } } { \nu }$ ), surface tension is mainly compete with gravity, only after the diffusion time the viscous drag will come to against the surface tension.In other words,from the beginning of capillary rise, the Bond number Bo enters the process and later on the Galileo number Ga joins.

We choose the Bond number Bo as a perturbation parameter,the perturbation solution can take the form $\begin{array} { r } { z ( \tau ) = \sum _ { n = 1 } ^ { \infty } \mathrm { B o } ^ { - n } f _ { n } ( \tau ) } \end{array}$ , which leads to a solution as

follows

$$
\begin{array} { c } { { z ( \tau ) = \displaystyle \frac { 1 } { \mathrm { B o } } ( \frac 6 7 \cos \theta ) \tau ^ { 2 } - \displaystyle \frac { 1 } { \mathrm { B o } ^ { 2 } } ( \frac { 4 2 } { 3 4 3 } \cos ^ { 2 } \theta ) \tau ^ { 4 } } } \\ { { - \displaystyle \frac { 1 } { \mathrm { B o } ^ { 3 } } ( \frac { 1 4 4 } { 3 4 3 } \cos ^ { 3 } \theta ) \tau ^ { 4 } } } \\ { { - \displaystyle \frac { 1 } { \mathrm { B o } ^ { 4 } } ( \frac { 3 4 5 6 } { 1 7 1 5 } \frac { 1 } { \mathrm { G a } } \cos ^ { 4 } \theta ) \tau ^ { 5 } + { \cal O } ( \mathrm { B o } ^ { - 5 } ) } } \end{array}
$$

# Exact Taylor'sSeriessolution

Eq.(3) is a nonlinear ordinary differential equation,up to now there is no closed form solution has been founded.Fortunately,it has an exact Taylor's series solution $\begin{array} { r } { h ( t ) = \sum _ { n = 0 } ^ { \infty } c _ { n } t ^ { n } } \end{array}$ as follows

$$
\begin{array} { l } { { h ( t ) = \displaystyle \frac { 6 \sigma \cos \theta } { 7 \rho a ^ { 2 } } t ^ { 2 } - \frac { 3 \sigma \cos \theta ( 7 g \rho a ^ { 2 } + 2 4 \sigma \cos \theta ) } { 3 4 3 \rho ^ { 2 } a ^ { 5 } } t ^ { 4 } } } \\ { { - \displaystyle \frac { 8 6 4 \mu \sigma ^ { 2 } \cos ^ { 2 } \theta } { 1 7 1 5 \rho ^ { 3 } a ^ { 7 } } t ^ { 5 } + { \cal O } ( t ^ { 6 } ) } } \end{array}
$$

The correctness of this solution has been verified by using symbolic mathematics software Maple. Surprisely to see that the series solution is exact same as the perturbation solution in Eq.(5). The solution in Eq.(6) gives a important result,namely, the non-zero initial acceleration $\begin{array} { r } { \ddot { h } ( 0 ) = \frac { 1 2 } { 7 } \frac { \sigma \cos \theta } { \rho a ^ { 2 } } } \end{array}$ of approximate analytic solution.With the above solution in Eq.(6), there is no longer needs to divide the capillary dynamics process into several asymptotic regimes, since the solution in Eq.(6) is valid for the whore range of time domain. From Eqs.(5,6) we can see that the Bond number Bo is really vital for the existence of the solution.For those equations without the added mass term $\textstyle { \frac { 7 } { 6 } } a$ means thattheyhavezeroBond numberwhichwill lead to the infinite of height and velocity !

The academic value of the series solution is enable us to see the importance of the added mass that can void the singularity. However, the rate of convergence of this solution is very slow and useless for practical application. It would be natural attempts to propose a simple solution for the capillary rise.

# APPROXIMATEANALYTICALSOLUTION

General speaking, the whole dynamics process can be qualitatively described as follows: in an infinite reservoir, the capillary rise and velocity are zero in the initial state.Due to the effect of the surface tension, the capillary liquid obtains the initial acceleration (the initial acceleration must never be zero),begins to rise at a relatively uniform velocity,and the surface tension plays a dominant role in the ascending phase； however,as the capillary rises wall frictions and gravity begin to work in an attempt to prevent the rise of the capillaries,and their joint action succeeds in decelerating the capillaries at a point in time until the capillaries are finally stopped. Surface tension and wall resistance, gravity to achieve unity of opposites,capillary dynamics process are over,all attributed to calm.

From the physical understanding of capillary rising phenomena, the capillary liquid will rise to stationary level,established by the balance of gravity and capillarity,the height and velocity will tends to h → H = 2g cos0 and $\dot { h }  0$ at $t \to \infty$ , respectively. To satisfy the conditions,we can propose that the capillary rise takes the following form

$$
h ( t ) = H [ 1 - f ( t ) e ^ { - \beta t } ] ,
$$

where the exponent $\beta$ and function $f ( t )$ are to be determined.

Substitute the Eq.(7) and $\begin{array} { r } { \dot { h } ( t ) ~ = ~ - H f ^ { \prime } ( t ) e ^ { - \beta t } + } \end{array}$ $H \beta f ( t ) e ^ { - \beta t }$ into the initial conditions $h ( 0 ) = 0$ ， $\dot { h } ( 0 ) =$ $0$ ,the initial condition for the function $f ( t )$ is given by

$$
f ( 0 ) = 1 , f ^ { \prime } ( 0 ) = \beta .
$$

There are many possibility on the construction of $f ( t )$ which can satisfy the condition in Eq.(8), for instance, $f ( t ) = 1 + \beta t + \alpha t ^ { d }$ , in which the exponent $d > 2$ and $\alpha$ is a constant. Since capillary rise dynamics process usually takes a millisecond, so the lower order of time $t$ （204 will dominate the process,based on this understanding, we set the function $f ( t ) = 1 + \beta t + \alpha t ^ { 3 }$ ．Hence，the capillary rise can be proposed as follows

$$
h ( t ) = H [ 1 - ( 1 + \beta t + \alpha t ^ { 3 } ) e ^ { - \beta t } ] .
$$

Thus,we have capillary velocity $\dot { h } ( t ) = H ( \alpha \beta t ^ { 2 } - 3 \alpha t +$ $\beta ^ { 2 } ) t e ^ { - \beta t }$ and acceleration $\Ddot { h } ( t ) \ = \ - H ( \alpha \beta ^ { 2 } t ^ { 3 } + \beta ^ { 3 } t \ -$ $6 \alpha \beta t ^ { 2 } + 6 \alpha t - \beta ^ { 2 } ) e ^ { - \beta t }$ ：

The capillary rise in Eq.(9) satisfies both initial condition and infinity condition.The unknown constants $\beta$ （204号 can be determined by the exact series solution in Eq.(6), which gives the acceleration $\begin{array} { r } { \ddot { h } ( 0 ) = \frac { 1 2 } { 7 } \frac { \sigma \cos \theta } { \rho g a ^ { 2 } } H } \end{array}$ Hence, by equaling $\ddot { h } ( 0 ) = H \beta ^ { 2 }$ ，we obtain the exponent

$$
\beta = { \sqrt { { \frac { 1 2 } { 7 H } } { \frac { \sigma \cos \theta } { \rho g a ^ { 2 } } } } } = { \sqrt { \frac { 1 2 g } { 7 a } } } .
$$

To find the parameter $\alpha$ ，we can expand the capillary rise in Eq.(9) in Taylor series,and get its coefficient of the fth order team of $t ^ { 5 }$ as $- \textstyle { \frac { 1 } { 3 0 } } H \beta ^ { 2 } ( \beta ^ { 3 } + 1 5 \alpha )$ , and let it equal to the coefficient of $t ^ { 5 }$ in Eq.(6),namely

$$
- \frac { 1 } { 3 0 } { \cal H } \beta ^ { 2 } ( \beta ^ { 3 } + 1 5 \alpha ) = - \frac { 8 6 4 } { 1 7 1 5 } \frac { \mu \sigma ^ { 2 } \cos ^ { 2 } \theta } { \rho ^ { 3 } a ^ { 7 } } ,
$$

which gives

$$
\alpha = \frac { 7 \mu \sigma \cos { \theta } } { \rho ^ { 2 } a ^ { 5 } } - \frac { 1 } { 1 5 } \left( \sqrt { \frac { 1 2 g } { 7 a } } \right) ^ { 3 } .
$$

It is clear to see that $\alpha$ is crucial parameter which links to all constants the capillary rise dynamics.It is worth to mention an interesting thing that $\alpha$ can be set to zero by adjusting the radius.

Finally, we obtain the capillary rise $h ( t )$

$$
h ( t ) = \frac { 2 \sigma \cos \theta } { \rho g a } \left. 1 - \left[ 1 + \left( \sqrt { \frac { 1 2 g } { 7 a } } \right) t + \alpha t ^ { 3 } \right] e ^ { - \left( \sqrt { \frac { 1 2 g } { 7 a } } \right) t } \right. ,
$$

and the capillary velocity $\dot { h } ( t )$

$$
\frac { d h ( t ) } { d t } = \frac { 2 \sigma \cos \theta } { \rho g a } \left( \alpha t ^ { 2 } \sqrt { \frac { 1 2 g } { 7 a } } - 3 \alpha t + \frac { 1 2 g } { 7 a } \right) t e ^ { - \left( \sqrt { \frac { 1 2 g } { 7 a } } \right) t } ,
$$

as well as the capillary acceleration $\ddot { h } ( t )$ 业

The above solutions in Eqs.(13) and (14) are valid for the whole domain of time $t \in [ 0 , \infty )$ , for my knowledge, which have never been proposed before.

The solution in Eq.(13) reveals that the capillary rise $h ( t )$ is mainly controlled by the $\begin{array} { r } { H = \frac { 2 \sigma \cos \theta } { \rho g a } } \end{array}$ with decay rate of $e ^ { - \left( \sqrt { \frac { 1 2 g } { 7 a } } \right) t }$ ， where the radius $a$ is the only dominate parameter, the smaller radius the fast decay.

# NUMERICALVERIFICATION AND DISCUSSIONS

# Verification of the solution in Eq.(13)

To verify the correctness of the solution in Eq.(13),we can compare the result obtained numerically by Zhmud et al.[2O]. for comparison study, the data of the diethyl either in glass shown in Table I.

TABLE I:The diethyl ether in glass with arbitrary radius   

<html><body><table><tr><td></td><td>[]</td><td></td><td>0</td><td></td><td></td><td>gp]</td></tr><tr><td>2.2:10-4 1.67:10-2 260</td><td></td><td></td><td></td><td></td><td>9.81</td><td>710</td></tr></table></body></html>

In this case,for any radius $a$ ,we have the capillary rise $\begin{array} { r } { H = \frac { 4 . 3 } { a } \cdot 1 0 ^ { - 6 } } \end{array}$ , our analytical capillary rise is given by

$$
\begin{array} { l } { { h ( t ) = \displaystyle \frac { 4 . 3 \cdot 1 0 ^ { - 6 } } { a } \{ 1 - } }  \\ { { [ 1 + \displaystyle \frac { 4 . 1 } { \sqrt { a } } t + ( \frac { 4 . 5 8 5 \cdot 1 0 ^ { - 1 1 } } { a ^ { 5 } } - \frac { 4 . 5 9 7 } { a ^ { 3 / 2 } } ) t ^ { 3 } ] e ^ { - \frac { 4 . 1 } { \sqrt { a } } t } \} . } } \end{array}
$$

If we set the radius $a = 0 . 0 0 0 5$ ,we have the capillary rise as follows

$$
h ( t ) = 0 . 0 0 8 6 2 \left[ 1 - ( 1 + 1 8 3 . 3 9 7 t + 1 . 0 5 6 \cdot 1 0 ^ { 6 } t ^ { 3 } ) e ^ { - 1 8 3 . 3 9 7 t } \right] ,
$$

which is plotted in the figure 4. From this figure we can see that our solution agrees with [20] very well.

![](images/f804037aa1b459bf2f37e3f749a19a75967aa8810f6c722fd689e5eec499a92f.jpg)  
FIG.4:Comparison study: $a = 0 . 0 0 0 5 m$ and $\theta = 2 6 ^ { \mathrm { { 0 } } }$ （204号

# Capillaryrise,velocity and acceleration for radius （204号 $a = 0 . 0 0 0 1$ and wetting angle $\theta = 0$ （204号

Applying all formulations to the diethyl either in glass with data shown in Table II.

TABLEII:The diethyl ether in glass with radius $a = 0$   

<html><body><table><tr><td>]</td><td></td><td>0151</td><td></td><td>a[m] 0</td><td>g[]</td><td>pg]</td></tr><tr><td>2.2:10-4 1.67:10-2 1×10-4</td><td></td><td></td><td></td><td>0</td><td>9.81</td><td>710</td></tr></table></body></html>

The capillary rise $h ( t )$ of the diethyl either is given by $h ( t ) = 0 . 0 0 4 7 9 [ 1 - ( 1 + 1 2 9 . 6 8 t - 9 4 3 7 3 t ^ { 3 } ) e ^ { - 1 2 9 . 6 8 t } ] ,$ (17)

the capillary velocity $\dot { h } ( t )$

$$
\dot { h } ( t ) = - 5 8 6 8 7 . 2 6 t ( t + 0 . 0 2 7 ) ( t - 0 . 0 5 ) e ^ { - 1 2 9 . 6 8 t } ,
$$

and the capillary acceleration $\ddot { h } ( t )$

$$
\ddot { h } ( t ) = 7 . 6 1 \times 1 0 ^ { 6 } ( t + 0 . 0 2 2 ) ( t - 0 . 0 0 8 ) ( t - 0 . 0 6 ) e ^ { - 1 2 9 . 6 8 t } .
$$

Those three equations are plotted in figure 5

Figure 5 shows that the capillary rise almost reaches $H$ at time $t \geq 0 . 0 6$ seconds,and the capillary velocity reaches its peak point at $t = 0 . 0 1$ and then to zero at （20 $t ~ \geq ~ 0 . 0 6$ .The capillary acceleration reaches the peak point at $t = 0 . 0 1$ and decrease to zero at $t = 0 . 0 0 8$ and （204号 $t \geq 0 . 0 6$ , respectively.

# Influence of radius change

If keeping the wetting angle as $\theta = 2 6 ^ { 0 }$ [20],and just adjusting the radius of the glass in Eq.(15). We have graphs in the Figure 6,which reveals that capillary rise is very sensitive to the radius. The smaller the radius in which the liquid can travel, the further up it goes. Therefore,the glass tube radius is a crucial parameter for capillary rise dynamics. The radius has also strong influence on the capillary velocity and acceleration which can been seen in the figure 7.The smaller the radius the fast the capillary goes.

![](images/2ec5cc4892d6d2a5cbd0bccff759684e122422f47c2068680cc5dfa459418740.jpg)  
FIG.5:The capillary rise,velocity and acceleration for radius $a = 0 . 0 0 0 1$ and wetting angle $\theta = 0$ （20

# Discussions

If we put all the pictures together,we can have a fair picture of the capillary rise dynamics as follows: the capillary rise onsets from zero initial height and velocity,at （20 $t = 0$ as the first driving force,the surface tension supplies a kick-off acceleration in the amount of $H \beta ^ { 2 }$ ，this surface tension steadily drives the capillary rising at an almost uniform speed until reaches its peak at certain point，then the capillary speed is gradually reduced to zero due to the combining effect of wall viscous friction of galls and gravity. In the same time, the capillary acceleration decrease and reaches its lowest point before the increase to its final static state.

# CONCLUSIONS

Since the capillary rise generally has low Reynolds number, the flow in the tube can be considered as a laminar flow. To avoid the singularity problem, the added mass must appear in the governing equation. From the dimensionless form of Bush's equation,we found that the capillary rise dynamics is mainly controlled by the Bond number and the Galileo number. We have successfully obtained the perturbation and series solutions. Due to the poor rate of convergence of this solution，we proposed a simple approximate analytic solution by using series solution and initial conditions.We have verified the proposed analytic solution by some numerical examples.

![](images/14537c680b40a734549f3b70f5b63b3975ee921e63f94a6627ea893fa786fbb7.jpg)  
FIG.6:The capillary rise of four different radius

![](images/03dcd33b038c8a961f7997eaafbd802c0e272a58d16936f7546fb1179a7e7cdc.jpg)  
FIG.7: The capillary rise velocity and acceleration for two different radius

Last but at least,it might be worth to point out that all previous solutions are for the non-oscillatory regime, however,when the liquid surface reaches $h = H$ , the surface will oscillating for while before asymptotically stop. Within the oscillatory regime, the above solutions should be modified a little bit，which will be investigated by Homotopy Analysis Method [26,34] in the forthcoming paper.

# ACKNOWLEDGEMENTS

This paper is dedicated to the victims and heroes of the September 11 attacks.This work is part of the selffunded project: Science in Small World.

phenomena)，Annalen der Physik，309 (3）： 513-523 (1901).   
[2] R.Lucas.Ueber das Zeitgesetz des kapillaren Aufstiegs von Flüssigkeiten.Kolloid-Zeitschrift,23:15-22 (1918).   
[3] E.W. Washburn. The dynamics of capillary flow.Physical Review,17(3):273-283 (1921).   
[4] E.K.Rideal. On the flow of liquids under capillary pressure.Philos.Mag.Ser.6,44:1152-1159 (1922).   
[5] C.H.Bosanquet.On the flow of liquids into capillary tubes.Philos.Mag.Ser.6,45:525-531(1923).   
[6] W.E.Brittin.Liquid rise in a capillary tube,J.Applied Physics,17:37-45 (1946).   
[7] S.Newman.Kinetics of wetting of surfaces by polymers - capillary flow,J.of Colloid and Interface Science, 26(2)209-213 (1968).   
[8]J.Szekely,A.W.Neumann and Y.K.Chuang. The rate of capillary penetration and the applicability of the washburn equation.J.Colloid and Interface Science,35,273- 278 (1971).   
[9] J.van Brakel and P.M.Heertjes. Capillary rise in porous media. Nature 254, 585-586 (1975).   
[10] S.Levine,P.Reed,E.J.Watson and G.Neale.A theory of the rate of rise of a liquid in a capillary.In MKerker,editor,J.Colloid and Interface Science,3: 403-419. (Academic Press, New York, 1976).   
[11] S.Levine, J. Lowndes,E.J.Watson and G. Neale.A theory of capillary rise of a liquid in a vertical cylindrical tube and in a parallel-plate channel.J.Colloid and Interface Science,73(1):136-151 (1980).   
[12] A.Marmur.Penetration and displacement in capillary systems of limited size. Adv. Colloid Interface Sci.,39:13- 33 (1992).   
[13] M. Dreyer,A.Delgado and H.J.Rath.Fluid motion in capillary vanes under reduced gravity, Microgravity Science and Technology, 4:203-210 (1993).   
[14] N. Ichikawa and Y. Satoda. Interface dynamics of capillary flow in a tube under negligible gravity condition. J. Colloid and Interface Science,162:350-355 (1994).   
[15] T.Delker, D.B. Pengra and P.-Z. Wong. Interface pinning and the dynamics of capillary rise in porous media. Physical Review Letters,76(16):2902-2905 (1996).   
[16] A.Marmur and R.D.Cohen. Characterization of porous media by the kinetics of liquid penetration: The vertical capillaries model. J. Colloid and Interface Science, 189(2):299-304, (1997).   
[17] R.D.Deegan,Olgica Bakajin,T.F.Dupont,G. Huber,S.R.Nagel and T.A.Witten. Capillary flowasthe cause of ring stains fromdried liquid drops,Nature 389, 827 - 829 (1997).   
[18] D. Quere. Inertial capillarity. Europhys. Lett., 39(5):533- 538 (1997).   
[19] J.Fisher.Physics takes the biscuit，Nature,397,469 (1999).   
[20] B.V. Zhmud，F. Tiberg，K. Hallstensson. Dynamics of capillary rise.J.Colloid and Interface Science, 228(2):263-269 (2000).   
[21] A.Siebold,M. Nardin,J. Schultz,A.Walliser and M. Oppliger. Effect of dynamic contact angle on capillary rise phenomena. Colloids and Surfaces A, 161(1):81-87 (2000).   
[22] M. Lago and M. Araujo. Capillary rise in porous media. Physica A, 289:1-17 (2001).   
[23] J. Bico and D. Qur,Rise of liquids and bubbles in angular capillary tubes.J. Colloid Interface Sci. 247:162-166   
[24] A. Hamraoui and T. Nylander. Analytical approach for the Lucas- Washburn equation.J.Colloid and Interface Science,250:415-421 (2002).   
[25] P.G.de Gennes,F.Brochard-Wyart and D.Quéré.Capillarity and Wetting Phenomena:Drops,Bubbles,Pearls, Waves. (Springer, New York, 2003).   
[26] S.J.Liao,Beyond Perturbation: Introduction to the Homotopy Analysis Method, Chapman & Hall/CRC,Boca Raton, 2003.   
[27] C. J. Lv, C. Chen, Y. C. Chuang, F. G. Tseng, Y. J. Yin, F.Grey,and Q.S. Zheng. Substrate curvature gradient drives rapid droplet motion,Phys.Rev.Lett.113,026101 (2014).   
[28] Y. Xiao, F. Yang and R. Pitchumani, A generalized analysis of capillary flows in channels,J. Colloid and Interface Science,Vol. 298, pp: 880-888 (2006).   
[29]J.W.M.Bush and D.L.Hu.Walking on Water: Biolocomotion at the Interface,Annu.Rev.Fluid Mech.,38:339- 36 (2006).   
[30] C. Hall and W. Hoff. Rising damp: capillary rise dynamics in walls. Proc. R. Soc. A 463(2007).   
[31] N. Fries and M. Dreyer.An analytic solution of capillary rise restrained by gravity, 320,1:259-263 (2008).   
[32] F.J.Higuera,A.Medina and A.Linan.Capillary rise of a liquid between two vertical plates making a small angle. Phys.Fluids 20,102102,1871-1884(2008)   
[33] A.Ponomarenko,D.Quéré and C. Clanet.A universal law for capillary rise in corners,J.Fluid Mech.,vol. 666:146-154 (2011).   
[34] S. J. Liao, Homotopy Analysis Method in Nonlinear Differential Equations,Springer-Verlag,New York, 2011.   
[35] Y.P. Zhao. Physical Mechanics of Surface and Interface (in Chinese)(Science Press,Beijing,2012).   
[36]W.M.Bush.Interfacial Phenomena,MIT Open Course (2013).   
[37]O.Shardt，P.R.Waghmare，J.J.Derksena and S.K. Mitrab. Inertial rise in short capillary tubes,RSC Adv., 4:14781-14785 (2014).   
[38] X.X. Dou,S.P. Li,and J.L.Liu. Zero curvature-surface driven small objects，Appl.Phys.Lett．111，081602 (2017).