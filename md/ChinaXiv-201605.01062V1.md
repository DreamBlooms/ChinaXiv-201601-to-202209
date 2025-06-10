# Casimir Force at a Finite Cut-Off\*

XIONG Ai-Min $\dag$ and CHEN Xiao-Songt

Institute of Theoretical Physics,Chinese Academy of Sciences,P.O.Box 2735,Beijing 100080,China

(Received April 18,Revised June 3, 2008)

AbstractWe calculate the Casimir forceat a finite cut-off A by summing the forces inducedby the allfluctuation modes.We show that the Casimir force is independent of the cut-off function in the limit $L \Lambda \to \infty$ . There is a correction in the order of $( L \Lambda ) ^ { - 2 }$ ，when LΛ is finite and large. This correction becomes remarkable when $L$ is comparable with the microscopic length scale $\Lambda ^ { - 1 }$ .It has been demonstrated that the Casimir force at a finite cut-off should be defined by summing forces of all fuctuation modes，instead of the derivative of Casimir energy with respect to $L$ where an additional derivative of the cut-off function has been introduced.

PACS numbers:03.70.+k, 11.10.-z Key words: vacuum fluctuation, Casimir force, finite cut-off

# 1 Introduction

In 1948,Casimir predicted an attractive force between parallel conducting plates due to vacuum fluctuations of electromagnetic (EM) field.[il The study of Casimir effect has been a subject of extensive research,especially after significant progress in experiments $[ 2 - 5 ]$ (for a review on Casimir effect, see Ref. [6]).

Because the vacuum energy is notoriously ultravioletdivergent,one must use some regularization methods to extract the finite Casimir energy and define the Casimir force as the derivative of Casimir energy with respect to system size $L$ .The most useful regularization methods are the zeta functional regularization method $\lvert 7 \rvert$ and the cut-off technique.

The zeta functional regularization has a pure mathematical character. The cut-off technique is of a physical character.With finite cut-off all the physical quantities are free of divergence. The dropped parts of the vacuum energy,which are divergent when $\Lambda  \infty$ ，are the bulk, hyper-surface,..., surface and the edge energies $[ 8 ]$ in a rectangular box. It has been shown that the Casimir energy is independent of the cut-off function when the cut-off $\Lambda  \infty . ^ { [ 8 - 1 0 ] }$ Secondly, for quasi-one-dimensional systems such as film and piston system,it has been found out that the divergent parts inside and outside cancel each other and do not contribute to the Casimir force.[11-15]

Physically there should be no real divergence. Some kinds of cut-off functions must exit at ultra-high energy scale.In principle,quantum field theory(QFT) should be regarded as a low-energy effective theory of a more fundamental theory. When we use the QFT to the ultrahigh energy scale,as we do in calculating the vacuum energy, we should introduce a cut-off function $C ( | \boldsymbol { k } | / \Lambda )$ to describe the modification of QFT at high energy scale in principle. As an example,one can take a sharp cutoff related to Plank energy scale because of the smallest scale in the space-time. Another example is the Gaussian damping function as a result of the space-time noncommutativity.[16] Of course, the exact form of the cut-off function depends on the unknown fundamental theory at high energy scale.

Recently the Casimir energy at a finite cut-off was studied in Refs.[16] and [17]. The effect of the finite cut off cannot be neglected when system is not large enough. For example,the correction is about $5 \%$ when $L = 1 0 \Lambda ^ { - 1 }$ (Ref. [16]). For small enough system, the Casimir energy deviates from the standard behavior $L ^ { - d }$ and have a minimum around $L \approx \Lambda ^ { - 1 }$ . By the derivative of the Casimir energy they define the Casimir force which flips its sign at the point of minimum.[17] In the Casimir force they defined there is an artificial force related to the derivative of cut-off function $C ( | k | / \Lambda )$ with respect to $L$ .Ata finite cut-off we can obtain the bulk force of the vacuum.The derivative of the cut-off function gives also an additional contribution to thebulk force so that it becomes attractive and makes the vacuum unstable.This is also artificial.

In this paper we calculate the vacuum force by summing directly the forces induced by all vacuum fluctuation modes with a finite cut-off. This method can give a positive bulk force,which makes the vacuum stable.From the vacuum forces inside and outside the wall we can get the Casimir force at a finite cut-off,which is different from the derivative of the Casimir energy.

Our paper is organized as follows.In Sec.2 we discuss the two definitions of the Casimir force we mentioned above.In Sec.3 we investigate the asymptotic behavior of the Casimir force for large system size $L \gg { \Lambda ^ { - 1 } }$ with general cut-off function.In Sec.4,with exponential(4.1) and power (4.2) damping cut-off function the Casimir force is calculated for general $L$ .Finally we make some conclusions and discussions in Sec.5.

# 2Casimir Force at Finite Cut-off

Without loss of generality， we study a massless scalar field $\varphi ( t , x )$ confined in a one-dimensional (1D) interval $0 \leq x \leq L$ .Here we only consider typical Dirichlet-Dirichlet (DD） boundary conditions with $ \varphi ( t , 0 ) ~ = ~ \varphi ( t , L ) ~ = ~ 0$ and Dirichlet-Neumann (DN) boundary conditions with $\varphi ( t , 0 ) = \partial _ { x } \varphi ( t , x ) | _ { x = L } = 0$ ： It is easy to obtain the allowable fluctuation modes

$$
k _ { n } ( L ) = \frac { \pi } { L } ( n + \beta ) , \quad ( n = 0 , 1 , 2 , \ldots ) ,
$$

where $\beta _ { D D } = 1 , \beta _ { D N } = 1 / 2$ ．The other idealized boundary conditions (such as Neumann-Neumann (NN),periodical(PR),and anti-periodical (AP) boundary conditions) are quite similar to DD or DN boundary conditions.[8]

The energy of a vacuum fluctuation mode $k$ is given by ( $\hbar = c = 1$ ）

$$
\varepsilon _ { 0 } ( k ) = { \frac { 1 } { 2 } } \omega ( k ) = { \frac { | k | } { 2 } } .
$$

The force induced by this fluctuation mode can be obtained by the derivative,

$$
f _ { 0 } ( L , k ) = - \frac { \partial } { \partial L } \varepsilon _ { 0 } ( k ) = \frac { | k | } { 2 L } ,
$$

which can be considered also as the radiation pressure of a virtual particle with momentum $k$ ：

In literatures,[1,6,8,9,16,17] the Casimir force was defined mostly by the derivative of Casimir energy with respect to $L$ . At a finite cut-off this definition gives an artificial force relatedto the the derivative of the cut-off function.So the Casimir force should be calculated by summing all forces induced by vacuum fluctuation modes.In this section the difference between these two definitions will be discussed.

# 2.1 Casimir Force Defined by Summing Forces of Fluctuation Modes

After summing the force $f _ { 0 } ( L , k )$ of all fluctuation modes,we can get the vacuum force inside the interval. There is a notorious divergence if the summation is done until to infinite high energy scale. This divergence is artificial because the quantum field theory used above cannot be applied to infinite high energy and should be modified at very high energy scale. To take account of this modification，we introduce a dimensionless cut-off function $C ( | k | / \Lambda )$ with

$$
C ( 0 ) = 1 , \quad C ( x \to \infty ) \sim o ( x ^ { - 2 } ) ,
$$

where $C ( 0 ) = 1$ means that there is no modification at low energy scale and $C ( x )$ decays faster than $x ^ { - 2 }$ so that the total force is convergent.

Then the vacuum force inside the interval is

$$
F _ { 0 } ( L , \Lambda ) = - \sum _ { n = 0 } ^ { \infty } \frac { \partial \varepsilon _ { 0 } ( k _ { n } ) } { \partial L } C \Bigl ( \frac { k _ { n } } { \Lambda } \Bigr ) = \frac { 1 } { 2 L } \sum _ { n = 0 } ^ { \infty } k _ { n } C \Bigl ( \frac { k _ { n } } { \Lambda } \Bigr ) ,
$$

which iscalled the modes-summing vacuum force (MSVF).

Aftertaking the bulk limit $L  \infty$ ，weobtain the modes-summing bulk vacuum force

$$
F _ { b } ( \Lambda ) = \operatorname * { l i m } _ { L  \infty } F _ { 0 } ( L , \Lambda ) = \bar { F } _ { b } \Lambda ^ { 2 } ,
$$

where

$$
\bar { F } _ { b } = \int _ { 0 } ^ { \infty } \frac { \mathrm { d } k } { 2 \pi } k C ( k ) .
$$

The fluctuation modes outside the interval gives the the bulk vacuum force. The Casimir force is obtained by the sum of the vacuum force inside and outside the interval

$$
F _ { c } ( L , \Lambda ) = F _ { 0 } - F _ { b } = \frac { 1 } { 2 L } \sum _ { n = 0 } ^ { \infty } k _ { n } C \Big ( \frac { k _ { n } } { \Lambda } \Big ) - \bar { F } _ { b } \Lambda ^ { 2 } .
$$

We can rewrite the Casimir force in a scaling form

$$
F _ { c } ( L , \Lambda ) = L ^ { - 2 } \tilde { F } _ { c } ( L \Lambda ) ,
$$

with the scaling function

$$
\tilde { F } _ { c } ( l ) = \frac { \pi } { 2 } \sum _ { n = 0 } ^ { \infty } ( n + \beta ) C \Big ( \frac { n + \beta } { l / \pi } \Big ) - \bar { F } _ { b } l ^ { 2 } .
$$

# 2.2 Casimir Force Defined by Derivative of Vacuum Energy

As a comparison,we discuss here the Casimir force defined by the derivative of the vacuum energy. At first the vacuum force inside the interval is

$$
\mathcal { F } _ { 0 } ( L , \Lambda ) = - \frac { \partial } { \partial L } \sum _ { n = 0 } ^ { \infty } \varepsilon _ { 0 } ( k _ { n } ) C \Big ( \frac { | k _ { n } | } { \Lambda } \Big ) .
$$

Compared with Eq. (5),this vacuum force has an additional part,

$$
\delta F _ { 0 } ( L , \Lambda ) = { \mathcal { F } } _ { 0 } - F _ { 0 } = { \frac { 1 } { 2 L \Lambda } } \sum _ { n = 0 } ^ { \infty } k _ { n } ^ { 2 } C ^ { ( 1 ) } \Bigl ( { \frac { k _ { n } } { \Lambda } } \Bigr ) ,
$$

where $C ^ { ( 1 ) } ( x ) = \mathrm { d } C ( x ) / \mathrm { d } x$ is the derivative of cut-off function.The additional force is resulted from the deriva tive of the cut-off function and should be artificial.

We can argue this artificiality in analogy to the statistical physics. If we take the cut-off function as a probability function, the present system is an analogy to a thermodynamic system.In thermodynamics the pressure is defined by the derivative of free energy rather than the internal energy. The derivative of free energy is equivalent to summing forces induced by all particles. So the vacuum force at a finite cut-off should be calculated by summing forces of all fluctuation modes.

The bulk limit of the additional part of the vacuum force defined by the derivative is

$$
\delta F _ { b } ( \Lambda ) = \operatorname * { l i m } _ { L  \infty } \delta F _ { 0 } ( L , \Lambda ) = - 2 \bar { F } _ { b } \Lambda ^ { 2 } .
$$

The bulk vacuum force $F _ { b }$ is positive and repulsive.But the bulk vacuum force defined by the derivative

$$
\mathcal { F } _ { b } ( \Lambda ) = F _ { b } ( \Lambda ) + \delta F _ { b } ( \Lambda ) = - F _ { b } ( \Lambda ) ,
$$

which is negative and then attractive.The attractive bulk vacuum force makes the vacuum unstable and crash together.This is an artificial effect.

After subtracting the bulk vacuum fluctuation force we get the derivative Casimir force (DCF),

$$
\begin{array} { l } { \displaystyle \mathcal { F } _ { c } ( L , \Lambda ) = \mathcal { F } _ { 0 } ( L , \Lambda ) - \mathcal { F } _ { b } ( L , \Lambda ) } \\ { \displaystyle \quad = \frac { 1 } { 2 L } \sum _ { n = 0 } ^ { \infty } k _ { n } \Big [ C \Big ( \frac { k _ { n } } { \Lambda } \Big ) + \frac { k _ { n } } { \Lambda } C ^ { ( 1 ) } \Big ( \frac { k _ { n } } { \Lambda } \Big ) \Big ] + \bar { F } _ { b } \Lambda ^ { 2 } . } \end{array}
$$

It can be rewritten also in a scaling form,

$$
\mathcal { F } _ { c } ( L , \Lambda ) = L ^ { - 2 } \tilde { \mathcal { F } } _ { c } ( L \Lambda ) ,
$$

where the scaling function

$$
\tilde { \mathcal { F } } _ { c } ( l ) = \tilde { F } _ { c } ( l ) + \delta \tilde { F } _ { c } ( l )
$$

with an artificial part

$$
\delta { \tilde { F } } _ { c } ( l ) = \frac { 1 } { 2 l } \sum _ { n = 0 } ^ { \infty } ( n + \beta ) ^ { 2 } C ^ { ( 1 ) } \Big ( \frac { n + \beta } { l / \pi } \Big ) + 2 { \bar { F } } _ { b } l ^ { 2 } .
$$

In the following we will calculate the scaling function $\tilde { F } _ { c } ( l )$ of the mode-summing Casimir force. The artificial part $\delta \tilde { F } _ { c } ( l )$ of the derivative Casimir force will be discussed also.

# 3Asymptotic Behavior of the Casimir Force for General Cut-Off

Using the Able-Plana sum formula,

$$
\sum _ { n = 0 } ^ { \infty } g ( \alpha ( n + \beta ) ) = \frac { 1 } { \alpha } \int _ { 0 } ^ { \infty } \mathrm { d } y g ( y ) + \frac { g ( 0 ) } { 2 } \delta _ { \beta , 0 }
$$

$$
+ \mathrm { i } \int _ { 0 } ^ { \infty } \mathrm { d } y \Big [ \frac { g ( \mathrm { i } \alpha y ) } { \mathrm { e } ^ { 2 \pi ( y + \mathrm { i } \beta ) } - 1 } - \frac { g ( - \mathrm { i } \alpha y ) } { \mathrm { e } ^ { 2 \pi ( y - \mathrm { i } \beta ) } - 1 } \Big ] ,
$$

we can rewrite the scaling function of Eq.(1O) as

$$
\tilde { F } _ { c } ( l ) = - \frac { 1 } { 2 \pi } \int _ { 0 } ^ { \infty } \mathrm { d } t t \Bigl [ \frac { C ( \mathrm { i } t / l ) } { \mathrm { e } ^ { 2 ( t + \mathrm { i } \beta \pi ) } - 1 } + \frac { C ( - \mathrm { i } t / l ) } { \mathrm { e } ^ { 2 ( t - \mathrm { i } \beta \pi ) } - 1 } \Bigr ] .
$$

From this expression we can obtain the asymptotic behavior of this scaling function without knowing the specific form of the cut-off function $C ( x )$

# 3.1 Limit $L \Lambda \to \infty$

Taking the limit $l = L \Lambda  \infty$ in Eq. (20)，we have $C ( \pm \mathrm { i } t / l ) = C ( 0 ) = 1$ and obtain

$$
\tilde { F } _ { c } ( \infty ) = - \frac { \pi } { 4 } B _ { 2 } ( \beta ) ,
$$

where $B _ { i } ( x )$ is the Bernoulli polynomial with

$$
B _ { 2 } ( x ) = x ^ { 2 } - x + \frac { 1 } { 6 } .
$$

Now the Casimir force can be written as

$$
F _ { c } ( L , \infty ) = L ^ { - 2 } \tilde { F } _ { c } ( \infty ) = - \frac { \pi } { 4 } B _ { 2 } ( \beta ) L ^ { - 2 } .
$$

This result agrees with the Casimir force calculated by the derivative of vacuum energy with cut-off $\Lambda  \infty$ ：

The sign of this Casimir force depends on the parameter $\beta$ . For the Dirichlet-Dirichlet boundary condition

$$
B _ { 2 } ( 1 ) = \frac { 1 } { 6 } , \quad F _ { c } ^ { D D } ( L , \infty ) = - \frac { \pi } { 2 4 } L ^ { - 2 } < 0 .
$$

The Casimir force in the DD boundary condition is attractive.For the Dirichlet-Neumann boundary condition

$$
B _ { 2 } \Big ( \frac { 1 } { 2 } \Big ) = - \frac { 1 } { 1 2 } , \quad F _ { c } ^ { D N } ( L , \infty ) = \frac { \pi } { 4 8 } L ^ { - 2 } > 0 .
$$

Therefore the Casimir force in the DN boundary condition is repulsive.

# 3.2 Large $L \Lambda \gg 1$

For finite $l = L \Lambda$ the scaling function $\tilde { F } _ { c } ( l )$ has correction to its limit $\tilde { F } _ { c } ( \infty )$ . Here we discuss the asymptotic behavior of this correction for $l \gg 1$ ：

Because of the damping factor $( \mathrm { e } ^ { 2 t } \pm 1 ) ^ { - 1 }$ in the integrand of Eq. (20)， for $l \gg 1$ we can expand $C ( \pm \mathrm { i } t / l )$ around zero. Correspondingly the scaling function becomes

$$
\tilde { F } _ { c } ( l ) = \tilde { F } _ { c } ( \infty ) + \sum _ { i = 1 } \tilde { F } _ { c , 2 i } l ^ { - 2 i } ,
$$

where

$$
\tilde { \cal F } _ { c , 2 i } = - \frac { 1 + 2 i } { 2 ( 2 i + 2 ) ! } C ^ { ( 2 i ) } ( 0 ) \pi ^ { 2 i + 1 } B _ { 2 i + 2 } ( \beta ) ,
$$

with the $n$ -th derivative of the cut-off function

$$
C ^ { ( n ) } ( 0 ) = \frac { \mathrm { d } ^ { n } C ( x ) } { \mathrm { d } x ^ { n } } \Bigm | _ { x = 0 } \ .
$$

In Eq.(26) there are only even powers of $l ^ { - 1 }$ because $\beta = 1 , 1 / 2$ for DD and DN boundary conditions.For generalboundary conditions with other $\beta$ there should be also terms with odd powers.

The coefficient of the leading correction is

$$
\tilde { F } _ { c , 2 } = - \frac { \pi ^ { 3 } } { 1 6 } C ^ { ( 2 ) } ( 0 ) B _ { 4 } ( \beta ) ,
$$

which depends on the cut-off function (the second derivative of it).

When setting $C ^ { ( 2 ) } ( 0 ) = 1$ ， $l \ = \ 5$ ，the correction is about $- 1 . 9 7 \%$ for DD boundary conditions and about $- 3 . 4 5 \%$ for DN boundary conditions. $C ^ { ( 2 ) } ( 0 )$ could be larger than 1. For the power damping cut-off function used in subsection 4.2, $C ^ { ( 2 ) } ( 0 )$ is of the order 10.Then the correction is remarkable for $L \sim 5 \Lambda ^ { - 1 }$

When the system size $L$ becomes comparable with the microscopic length scale $\Lambda ^ { - 1 }$ ，the higher-order terms of the correction must be considered. Then the correction depends strongly on the form of the cut-off function.Although the condition $L \sim \Lambda ^ { - 1 }$ is hard to be achieved in the laboratory currently, it is possible for some theo retical models,such as the Casimir's semi-classic electron model18] and the bag model of quark.[19]

# 3.3 Large LA Behavior of Derivative Casimir Force

We have got the general asymptotic behavior of the Casimir force calculated by summing forces of all fluctuation modes.Here we give the large $L \Lambda$ behavior of the derivative Casimir force.

The scaling function of the derivative Casimir force canbe expanded similarly as

$$
\tilde { \mathcal { F } } _ { c } ( l ) = \tilde { F } _ { c } ( \infty ) + \sum _ { i = 1 } \tilde { \mathcal { F } } _ { c , 2 i } l ^ { - 2 i } ,
$$

where

$$
\tilde { \mathcal { F } } _ { c , 2 i } = ( 1 + 2 i ) \tilde { F } _ { c , 2 i } .
$$

When calculating the Casimir force,the artificialbulk vacuum forces inside and outside the interval cancel each other exactly. In the limit $l = L \Lambda  \infty$ ， $\tilde { \mathcal { F } } _ { c } ( l )$ gives the same result as we obtained in the last subsection.

For large $l \ = \ L \Lambda \gg 1$ the correction terms of the derivative Casimir force are obviously larger than the corresponding terms of the mode-summing Casimir force.

# 4Casimir Force for Specific Cut-offFunctions

To obtain the scaling function of the Casimir force in whole range，we need to know the specific form of the cut-off function,which depends on the physical properties at ultra-high energy scale. For example, the cut-off functionis a Gaussian damping factor when the space-time is noncommutativel16l and is quite similar in the presence of a minimal length.[20]

Here we consider an exponential damping cut-off func tion

$$
C _ { e } ( x ) = \mathrm { e } ^ { - x } ,
$$

and a power damping cut-off function

$$
C _ { p } ( x ) = ( 1 + x ) ^ { - s } , \quad ( s > 2 ) .
$$

# 4.1Exponential Damping Cut-off Function

For the exponential damping cut-off function $C _ { e } ( x )$ we obtain the scaling function of the Casimir force

$$
\tilde { F } _ { c } ( l ) = \frac { \pi } { 2 } \Big [ \frac { \mathrm { e } ^ { \pi ( 1 - \beta ) / l } } { \mathrm { e } ^ { \pi / l } - 1 } \Big ( \frac { 1 } { \mathrm { e } ^ { \pi / l } - 1 } + \beta \Big ) - \Big ( \frac { \pi } { l } \Big ) ^ { - 2 } \Big ] .
$$

For the DD boundary condition $\beta = 1$ and the scaling function becomes

$$
\tilde { F } _ { c } ^ { D D } ( l ) = \frac { \pi } { 8 } \Bigl [ \sinh ^ { - 2 } \Bigl ( \frac { \pi } { 2 l } \Bigr ) - \Bigl ( \frac { \pi } { 2 l } \Bigr ) ^ { - 2 } \Bigr ] .
$$

Because $\sinh ( x ) > x$ for any $x > 0$ ，s0 $\tilde { F } _ { c } ^ { D D } ( l )$ is always negative for any system size. When $l \gg 1$ ， the scaling

function can be expanded as

$$
\tilde { F } _ { c } ^ { D D } ( l ) = - { \frac { \pi } { 2 4 } } \Big [ 1 - { \frac { \pi ^ { 2 } } { 2 0 } } l ^ { - 2 } + { \mathcal O } ( l ^ { - 4 } ) \Big ] .
$$

The leading correction term here is consistent with the general expansion (27).

In Fig.1 we plot the correction $R ^ { D D } ( l )$ defined by

$$
\tilde { F } _ { c } ^ { D D } ( l ) = \tilde { F } _ { c } ^ { D D } ( \infty ) [ 1 + R ^ { D D } ( l ) ] .
$$

We can see that the cut-off dependent correction is remarkable $( \gtrsim 5 \% )$ when $L \lesssim 3 \Lambda ^ { - 1 }$

![](images/ee1ba41ab483038d02d92610b7613de30623155ea48b14752ed29da4b850a879.jpg)  
Fig.1 Correction of the Casimir force in the DirichletDirichlet boundary condition and with an exponential damping cut-off function $C _ { e } ( | k | / \Lambda ) = \textrm { e } ^ { - | k | / \Lambda }$ , which is given in Eq. (37).

We can get also the scaling function of the derivative Casimir force

$$
\tilde { \mathcal { F } } _ { c } ^ { D D } ( l ) = \frac { \pi } { 8 } \sinh ^ { - 2 } \left( \frac { \pi } { 2 l } \right) \left[ 1 - \frac { \pi } { l } \coth \left( \frac { \pi } { 2 l } \right) \right] + \frac { l ^ { 2 } } { 2 \pi } .
$$

This expression agrees with Eq. (6) of Ref.[17]. We find that $\mathcal { \tilde { F } } _ { c } ^ { D D } ( l )$ does change its sign at ${ \mathit { l } } \approx 1$ , which has been claimed in Ref.[17]. But this change of sign is an artificialeffect of thederivative Casimirforce.Sothederivative vacuum force has artificiality not only in bulk, but also for finite $L \Lambda$ ：

For the Dirichlet-Neumann boundary condition with L $\beta _ { D N } = 1 / 2$ )，we get the scaling function of the Casimir force,

$$
\tilde { F } _ { c } ^ { D N } ( l ) = \frac { \pi } { 8 } \sinh ^ { - 1 } \Bigl ( \frac { \pi } { 2 l } \Bigr ) \coth \Bigl ( \frac { \pi } { 2 l } \Bigr ) - \frac { l ^ { 2 } } { 2 \pi } ,
$$

which can be expanded as

$$
\tilde { F } _ { c } ^ { D N } ( l ) = \frac { \pi } { 4 8 } \Big [ 1 - \frac { 7 \pi ^ { 2 } } { 8 0 } l ^ { - 2 } + { \mathcal O } ( l ^ { - 4 } ) \Big ] ,
$$

for $l \gg 1$

In Fig. 2 we plot the correction $R ^ { D N } ( l )$ defined by

$$
\tilde { F } _ { c } ^ { D N } ( l ) = \tilde { F } _ { c } ^ { D N } ( \infty ) [ 1 + R ^ { D N } ( l ) ] .
$$

Similar to the DD boundary condition,the finite cut-off correction is remarkable $( \gtrsim 5 \%$ ）when $L \lesssim 4 \Lambda ^ { - 1 }$

With the exponential cut-off function we have shown that the finite cut-off must be considered when $L$ is comparable with the microscopic length scale $\Lambda ^ { - 1 }$ .In the next subsection we will consider the finite cut-off effects of the Casimir force with power damping cut-off function.

![](images/eb20fc79643c6ce47270a8c834227c1cabdbb7da81fa0770651912dab8fc246b.jpg)  
Fig.2 Correction of the Casimir force in the DNboundary condition and with an exponential damping cut-off function $C _ { e } ( | k | / \Lambda ) = \mathrm { e } ^ { - | k | / \Lambda }$ , which is given in Eq. (41).

# 4.2 Power Damping Cut-Off

From the power damping cut-off function $C _ { p } ( x )$ ,which has been given in Eq.(33),we obtain the scaling function,

$$
\begin{array} { c } { { { \displaystyle \tilde { F } _ { c } ( l ) = \frac { \pi } { 2 } \Big ( \frac { l } { \pi } \Big ) ^ { s } \Big [ \zeta \Big ( s - 1 , \beta + \frac { l } { \pi } \Big ) - \frac { l } { \pi } \zeta \Big ( s , \beta + \frac { l } { \pi } \Big ) \Big ] } } } \\ { { { - \frac { \pi } { 2 } ( s ^ { 2 } - 3 s + 2 ) ^ { - 1 } \Big ( \frac { l } { \pi } \Big ) ^ { 2 } , } } } \end{array}
$$

where

$$
\zeta ( s , a ) = \sum _ { n = 0 } ^ { \infty } ( n + a ) ^ { - s }
$$

is the generalized Zeta function.

The power damping cut-off function $C _ { p } ( x )$ is controlled explicitly by the parameter $s$ ．So it is convenient for us to study dependence of the Casimir force on the cut-off function.

For the Dirichlet-Dirichlet boundary condition with $\beta _ { D D } = 1$ , the scaling function can be expanded as

$$
\tilde { F } _ { c } ^ { D D } ( l ) = - \frac { \pi } { 2 4 } \Big [ 1 - \frac { \pi ^ { 2 } } { 2 0 } s ( s + 1 ) l ^ { - 2 } + \mathcal { O } ( l ^ { - 4 } ) \Big ] .
$$

The result of $\tilde { F } _ { c } ^ { D D } ( \infty )$ here agrees with the previous results.Only the corrections of the Casimir force depends on the cut-off function,as we have discussed in Sec.3 for general cut-off functions.

We plot the correction of the Casimir force for the power damping cut-off function with $s = 3 , 4 , 5$ in Fig. 3. We can see that the Casimir force is not sensitive to the parameter $s$ when $l \gtrsim 2 0$ ，while dependent strongly on $s$ （204号 when $l \lesssim 1 0$ . The correction is larger for a faster damping cut-off function with a larger $s$ .In comparison with the exponential cut-off function, the correction here is larger.

This can be explained by the larger second derivative of cut-off function $C _ { p } ^ { ( 2 ) } ( 0 ) = s ( s + 1 )$ ， which is much larger than $C _ { e } ^ { ( 2 ) } ( 0 ) = 1$ ：

![](images/ff9b26cd6b13760ab61df09e17271657c36ea88d32a01ea82ed48e7387ffffa2.jpg)  
Fig.3 Correction of the Casimir force in DD boundary condition and with a power damping cut-off function $C _ { p } ( | k | / \Lambda ) = ( 1 + | k | / \Lambda ) ^ { - s }$ ，which is obtained from Eq. (42).

Similarly the scaling function for the DirichletNeumann boundary condition can be expanded for $l \gg 1$ as

$$
\tilde { F } _ { c } ^ { D N } ( l ) = \frac { \pi } { 4 8 } \Big [ 1 - \frac { 7 \pi ^ { 2 } } { 8 0 } s ( s + 1 ) l ^ { - 2 } + { \mathcal O } ( l ^ { - 4 } ) \Big ] .
$$

In Fig.4 we plot the correction of the Casimir force in DN boundary condition for $s = 3 , 4 , 5$ .Similar to the DD boundary condition,the Casimir force here is dependent on the cut-off function for small system,while is unsensitive to the form of the cut-off function for large system.

![](images/fa970307098e1260bd1bfe75bffc2072f388a0a7d19e74994053ffcf503266cc.jpg)  
Fig.4 Correction of the Casimir force under DN boundary condition and with the power damping cut-off function $C _ { p } ( | k | / \Lambda ) = ( 1 + | k | / \Lambda ) ^ { - s }$ ，which is obtained from Eq. (42).

# 5Conclusions and Discussions

In the presence of a finite cut-off $\Lambda$ ，wehave shown that the Casimir force should be defined by summing the forces induced by all vacuum fluctuation modes. The usual definition of the Casimir force by the derivative of the vacuum energy has an attractive bulk force,which makes the vacuum unstable and is therefore unphysical. Wehave calculated the 1-dimensional Casimir force with the Dirichlet-Dirichlet and Dirichlet-Neumann boundary conditions. Its asymptotic behavior at large system size has been studied for general cut-off function. The complete behavior of the Casimir force for exponential and power damping cut-off functions have been investigated also.

In limit $L \Lambda  \infty$ ,it is shown that the Casimir force is independent of the cut-off function and in agreement with the result obtained by the derivative method. For large $L \Lambda$ , there is the correction with a leading term proportional to $( L \Lambda ) ^ { - 2 }$ . The derivative method has a strong overestimation of the correction.

The correction increases with the decrease of the system size $L$ .When $L$ is comparable with the microscopic scale $\Lambda ^ { - 1 }$ , the Casimir force deviates from the standard power law behavior and depends strongly on the cut-off function. Although the condition $L \ \sim \ \Lambda ^ { - 1 }$ cannot be achieved normally in laboratory, it could be possible for physical systems in microscopic scale such as Casimir's semiclassical electron model.[18] In the theoretical models of elementary particles the finite cut-off effect should be veryimportant also.

For the Casimir force of general $d$ -dimensional systems, we expect that there are the similar cut-off dependent corrections for finite $L \Lambda$

# References

[1]H.B.G.Casimir,Proc.K.Ned.Akad.Wet.51(1948) 793.   
[2] S.K.Lamoreaux,Phys.Rev.Lett.78(1997) 5.   
[3] U. Mohideen and A. Roy,Phys. Rev. Lett. 81 (1998) 4549.   
[4] A.Roy, C.Y. Lin,and U. Mohideen，Phys. Rev.D 60 (1999) 111101.   
[5] G. Bressi, G. Carugno,R. Onofrio,and G. Ruoso, Phys. Rev.Lett.88 (2002)041804.   
[6] M.Bordag,U. Mohideen,and V.M. Mostepanenko, Phys. Rep.353(2001）1.   
[7] J.S.Dowker and R. Critchley,Phys.Rev.D 13 (1976) 3224.   
[8] A.M. Xiong and X.S. Chen, in preparation.   
[9] L.A.Manzoni and W.F.Wreszinski,Phys.Lett.A 292 (2001) 156.   
10] L.A.Manzoni and W.F.Wreszinski,Eur.Phys.J.C 25 (2002) 315.   
[11]P.W.Milonni,R.J.Cook,and M.E.Goggin,Phys.Rev. A 38 (1988) 1621.   
[12]R.M.Cavalcanti, Phys.Rev.D 69 (2004) 065015.   
[13]M.P.Hertzberg,R.L.Jaffe,M.Kardar,and A.Scardicchio，Phys.Rev.Lett.95(2005)250402.   
[14] M.P. Hertzberg,R.L. Jaffe,M. Kardar,and A. Scardicchio,Phys.Rew.D 76(2007) 045016.   
[15]A.M. Xiong and X.S. Chen,submited to Chin.Phys.Lett.   
[16]R.Casadio,A.Gruppuso,B.Harms,and O.Micu,Phys. Rev.D 76(2007) 025016.   
[17] G.Mahajan,S.Sarkar,and T.Padmanabhan, Phys. Lett. B641(2006)6.   
[18] H.B.G. Casimir, Physica 19 (1953) 846.   
[19] M.Creutz,Phys.Rev.D 10(1974) 1749.   
[20] U.Harbach and S.Hossenfelder, Phys.Lett.B 632 (2006) 379.