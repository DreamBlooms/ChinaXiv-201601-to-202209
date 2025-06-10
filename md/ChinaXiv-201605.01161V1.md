# Holographic Entanglement Entropy in Insulator/Superconductor Transition

Rong-Gen Cai $^ *$ ，Song He†， Li Li $\ddagger$ ， Yun-Long Zhang $\ S$

State Key Laboratory of Theoretical Physics, Institute of Theoretical Physics, Chinese Academy of Sciences,P.O.Box 2735,Beijing 100190, China

March 29,2012

# Abstract

We investigate the behaviors of entanglement entropy in the holographical insulator/superconductor phase transition. We calculate the holographic entanglement entropy for two kinds of geometry configurations in a completely back-reacted gravitational background describing the insulator/superconductor phase transition. The non-monotonic behavior of the entanglement entropy is found in this system. In the belt geometry case, there exist four phases characterized by the chemical potential and belt width.

# 1 Introduction

The AdS/CFT correspondence [1, 2,3, 4] provides a powerful theoretical method to study the strongly coupled systems in various fields of physics. One of the most widely investigated objects is the holographic superconductor (superfluid) [5,6, 7, 8, 9]. The physical picture is that some gravity background will become unstable as one tunes some parameter, such as temperature for black hole and chemical potential for AdS soliton, to develop some kind of “hair”. This condensation of the “hair” induces the symmetry breaking,which results in the non-vanishing vacuum expectation value of the dual operator in the field theory side.

On the other hand, as a measurement of how a given quantum system is entangled or strongly correlated, the entanglement entropy is also considered as a useful tool for keeping track of the degrees of freedom of strongly coupled systems. Dividing a quantum system into a subsystem $\mathcal { A }$ and its complement, the entanglement entropy of $\mathcal { A }$ is known as the famous von Neumann entropy

$$
\begin{array} { r } { S _ { A } = - T r _ { A } ( \hat { \rho } _ { A } \ln \hat { \rho } _ { A } ) , } \end{array}
$$

where $\hat { \rho } _ { A }$ is the reduced density matrix for $\mathcal { A }$ by tracing over its complement of the total density matrix. However, the calculation of entanglement entropy for a given system is found to be very difficult except for the case in $1 + 1$ dimensions.

Inspired by the Bekenstein-Hawking entropy of black hole and motivated by the development of AdS/CFT correspondence, the authors in Refs. [10, 11] have presented a proposal to compute the entanglement entropy of conformal field theories (CFTs） from the minimal area surface in gravity side. Precisely, in an asymptotically anti de-Sitter (AdS) spacetime, consider a slice at constant radial coordinate $r = 1 / \epsilon$ ，which is dual to a field theory “living” on this slice with a UV cutoff labeled by the small parameter $\epsilon$ .the （204号 $\epsilon  0$ corresponds to the UV limit of the dual field theory, which is known as the UV-IR relation [12]. Search for the minimal area surface $\gamma _ { \mathcal { A } }$ in the bulk with the same boundary （204号 $\partial \mathcal { A }$ of a region $\mathcal { A }$ on that slice. The entanglement entropy of $\mathcal { A }$ with its complement is defined as the “area law”:

$$
S _ { \mathcal { A } } = \frac { \mathrm { A r e a } ( \gamma _ { \mathcal { A } } ) } { 4 G _ { N } } ,
$$

where $G _ { N }$ is the Newton's constant in the bulk. A proof for this proposal from the basic principle of holographic duality is given in Ref.[13] and further properties of the holographic entanglement entropy are discussed in Ref. [14].

This proposal provides an elegant and executable way to calculate entanglement entropy of a strongly coupled system which has a gravity dual. Since then a lot of works have been carried out [15, 16,17,18, 19, 20, 21, 22, 23] for investigating and calculating the entanglement entropy in various gravity theories. In particular, Refs. [20, 21, 22] presented the calculations of entanglement entropy for AdS soliton geometry and Ref. [23] considered the case with higher derivative corrections. Very recently, the authors of Ref.[24] have studied the entanglement entropy in the holographic metal/superconductor phase transition. It was found that the entanglement entropy in superconducting phase is always less than the one in the metal phase. The entanglement entropy is continuous,but does not smoothly cross the second order phase transition.

The holographic insulator/superconductor phase transition was first studied in Ref. [9], where the AdS soliton background [25] was used to mimic the insulator/superconductor phase transition at zero temperature. Motivated by Ref.[24] we are going to explore the behaviors of the entanglement entropy in the insulator/superconductor phase transition.

The model of the holographic insulator/superconductor phase transition is constructed in the Einstein-Maxwell-scalar theory with a negative cosmological constant in five-dimensional spacetime. After completely solving the set of coupled equations of motion, we calculate the entanglement entropy for two geometry configurations,one is a half space and the other is a belt. In both cases,we find a discontinuity in the slope of the entanglement

entropy as a function of chemical potential across the phase transition. But,unlike the case of the metal/superconductor phase transition [24], after condensate, the entropy first rises as we increase the chemical potential $\mu$ ,arrives at its maximum at a certain chemical potential and then it decreases monotonously. For the belt geometry, there exits a so-called “confinement/deconfinement” transition controlled by belt width. Our results confirm the prediction in Ref. [21] that this phase transition must appear in any consistent gravity dual of a confining theory. So there are totally four “phases” parameterized by chemical potential $\mu$ and belt width $\ell$ . The complete “phase diagram” is drawn in Figure.(8). Here we would like to address that in fact there does not exist the parameter “belt width $\ell ^ { 9 }$ in the dual field theory. When one changes $\ell$ ,that a new“phase” occurs in the entanglement entropy manifests a length scale of dual field theory under consideration. For example, in this paper the length scale is nothing,but the correlation length of the confining theory.

This paper is organized as follows. In Section (2), we briefly review the holographic insulor/superconductor phase transition presented in Ref. [26], and give the complete equations of motion to be solved. In Section(3), the fully back-reacted system is solved by shooting method. In Section(4） we explore the behaviors of the entanglement entropy in insulator/superconductor phase transition. The conclusions and some discussons are included in Section (5).

# 2 AdS Soliton Background

Let us start with the Einstein-Maxwell-complex scalar theory with a negative cosmological constant in five-dimensional spacetime

$$
S = \int d ^ { 5 } x \sqrt { - g } \left( \mathcal { R } + \frac { 1 2 } { L ^ { 2 } } - \frac { 1 } { 4 } F ^ { \mu \nu } F _ { \mu \nu } - | D \psi | ^ { 2 } - m ^ { 2 } | \psi | ^ { 2 } \right) ,
$$

where $L$ is the radius of AdS spacetime, field strength $F = d A$ and $D _ { \mu } = \nabla _ { \mu } - i q A _ { \mu }$ . When the Maxwell field and scalar field are vanishing, the above action admits an exact solution named as AdS soliton

$$
d s ^ { 2 } = \frac { L ^ { 2 } d r ^ { 2 } } { r ^ { 2 } f ( r ) } + r ^ { 2 } ( - d t ^ { 2 } + d x ^ { 2 } + d y ^ { 2 } + f ( r ) d \chi ^ { 2 } ) , \qquad f ( r ) = 1 - \frac { r _ { 0 } ^ { 4 } } { r ^ { 4 } } \ .
$$

This asymptotically AdS solution approaches to $R ^ { 1 , 2 } \times S ^ { 1 }$ near the boundary at $r  \infty$ Moreover， the compactification $\chi \sim \chi + \pi L / r _ { 0 }$ needed to avoid a conical singularity at （204号 $r = r _ { 0 }$ gives a dual picture of a three-dimensional field theory with a mass gap,which resembles an insulator in the condensed matter physics [9]. The geometry in the $( r , \chi )$ sector just looks like a cigar with its tip at $r = r _ { 0 }$ . The temperature associated with the soliton background is zero.

In order to mimic the superconductor phase, we need the soliton solutions with nonvanishing $\psi$ . Furthermore, the back reaction of the matter fields must be taken into account in order to see the difference of the holographic entanglement entropy. So we choose the

ansatz as follows

$$
l s ^ { 2 } = \frac { d r ^ { 2 } } { r ^ { 2 } B ( r ) } + r ^ { 2 } \left( - e ^ { C ( r ) } d t ^ { 2 } + d x ^ { 2 } + d y ^ { 2 } + e ^ { A ( r ) } B ( r ) d \chi ^ { 2 } \right) , A _ { t } = \phi ( r ) , \psi = \psi
$$

Here we have set $L = 1$ without lose of generality. We require that $B ( r )$ vanishes at the tip of the soliton. And in order to obtain a smooth geometry at the tip $r _ { 0 }$ ， $\chi$ should be made with an identification

$$
\chi \sim \chi + \Gamma , \qquad \Gamma = \frac { 4 \pi e ^ { - A ( r _ { 0 } ) / 2 } } { r _ { 0 } ^ { 2 } B ^ { \prime } ( r _ { 0 } ) } \ .
$$

The independent equations of motion under this ansatz are given as

$$
\begin{array} { l } { { \displaystyle { \psi ^ { \prime \prime } + \left( \frac { \hat { \rho } } { r } + \frac { A ^ { \prime } } { 2 } + \frac { \beta ^ { \prime } } { B } + \frac { C ^ { \prime } } { 2 } \right) \psi ^ { \prime } - \frac { 1 } { r ^ { 2 } B } \left( \frac { e ^ { - C _ { 0 } ^ { \prime } \phi ^ { 2 } } } { r ^ { 2 } } - m ^ { 2 } \right) \psi = 0 , } } } \\ { { \displaystyle { \dot { \phi } ^ { \prime \prime } + \left( \frac { 3 } { r } + \frac { A ^ { \prime } } { 2 } \mid \frac { B ^ { \prime } } { B } - \frac { C ^ { \prime } } { 2 } \right) \phi ^ { \prime } - \frac { 2 \sigma ^ { \prime } \sigma ^ { 2 } \phi ^ { \prime } } { r ^ { 2 } B } = 0 , } } } \\ { { \displaystyle { A ^ { \prime } - \frac { 2 r ^ { 2 } C ^ { \prime \prime } + r ^ { 2 } C ^ { \prime \prime } + 4 r C ^ { \prime \prime } + 4 r ^ { 2 } \psi ^ { \prime \prime } - 2 e ^ { C } \phi ^ { 2 } } { r ( \theta - r \epsilon ^ { \prime } ) ^ { \prime } } } , } } \\ { { \displaystyle { C ^ { \prime \prime } + \frac { 1 } { 2 } C ^ { \prime \prime } + \left( \frac { 5 } { r } + \frac { A ^ { \prime } } { 2 } + \frac { B ^ { \prime } } { B } \right) C ^ { \prime } - \left( \phi ^ { 2 } + \frac { 2 q ^ { \prime } \phi ^ { \prime } + \frac { B ^ { \prime } } { r ^ { 2 } B } } { r ^ { 2 } B } \right) \frac { e ^ { - C } } { r ^ { 2 } } = 0 , } } } \\   \displaystyle { B ^ { \prime } \left( \frac { \hat { \rho } } { r } - \frac { C ^ { \prime } } { 2 } \right) + B \left( \psi ^ { 2 } - \frac { 1 } { 2 } \frac { A ^ { \prime } C ^ { \prime } + \frac { \theta ^ { \prime } C ^ { \prime } + \frac { \theta ^ { \prime } C ^ { \prime } } { 2 r ^ { 2 } } + \frac { 1 2 } { r ^ { 2 } } } { r ^ { 2 } }  } } \\  \\right)displaystyle { \qquad + \frac { 1 } { r ^ { 2 } } \left( \frac { e ^ { - C _ { 0 } ^ { \prime } \phi ^ { 2 } \phi ^ { 2 } + \theta ^ { \prime } + m ^ { 2 } \psi ^ { \prime \prime } - 1 2 }  = 0 , } } \end{\right)array} \end{array}
$$

where a prime denotes the derivative with respect to $r$ . The matter fields near the boundary $r  \infty$ should behave as

$$
\psi = \frac { \psi ^ { ( 1 ) } } { r ^ { \Delta _ { - } } } + \frac { \psi ^ { ( 2 ) } } { r ^ { \Delta _ { + } } } + . . . ,
$$

$$
\phi = \mu - { \frac { \rho } { r ^ { 2 } } } + . . . ,
$$

where $\psi ^ { ( i ) } = \langle \hat { O } _ { i } \rangle , ~ i = 1 , 2$ , up to a normalization constant, and ${ \hat { O } } _ { i }$ are the corresponding dual operators of $\psi ^ { ( i ) }$ in the feld theory side. The conformal dimensions of the operators are $\Delta _ { \pm } = 2 \pm \sqrt { 4 + m ^ { 2 } }$ ： $\mu$ and $\rho$ are the corresponding chemical potential and charge density in the dual field theory, respectively.

There are only four independent parameters at the tip, i.e., $r _ { 0 } , \psi ( r _ { 0 } ) , \phi ( r _ { 0 } ) , C ( r _ { 0 } )$ . However, the above equations of motion have two useful scaling symmetries [26]

$$
r  \alpha r , \qquad ( \chi , x , y , t )  ( \chi , x , y , t ) / \alpha , \qquad \phi  \alpha \phi ,
$$

$$
C  C - 2 \ln \beta , \qquad t  \beta t , \qquad \phi  \phi / \beta .
$$

These two symmetries allow us to pick any values for the position of the tip $r _ { 0 }$ and $C ( r _ { 0 } )$ In our numerical calculations,we will simply choose $r _ { 0 } = 1 , C ( r _ { 0 } ) = 0$ . Furthermore,to recover the pure AdS boundary, we also need $A ( \infty ) = 0$ and $C ( \infty ) = 0$ . In general,a solution will have a nonvanishing $C ( \infty )$ . In this case we will use the scaling symmetry (15) to shift $C ( \infty )$ to zero.

# 3 Insulator/Superconductor Phase Transition

From the discussion in Section 2, for given $m ^ { 2 } , q , \psi ( r _ { 0 } )$ ，we can solve the equations of motion for the system by choosing $\phi ( r _ { 0 } )$ as a shooting parameter. After solving the coupled equations,we can obtain the condensate $\langle \hat { O } \rangle$ from(12) and read off the chemical potential $\mu$ and charge density $\rho$ through (13).

In this paper we only focus on the case $m ^ { 2 } = - { \frac { 1 5 } { 4 } }$ and $q = 2$ . It is well known that in five-dimensional spacetime, when $- 4 < m ^ { 2 } < - 3$ , the scalar field admits two different quantizations related by a Legendre transform [27]. $\psi ^ { ( i ) }$ can either be identified as a source or an expectation value. In this paper we set $\psi ^ { ( 1 ) } = 0$ and consider $\psi ^ { ( 2 ) }$ acting as the vacuum expectation value of the operator ${ \hat { O } } _ { 2 }$ ：

It is convenient to make a coordinate transformation from $r -$ coordinate to $z -$ coordinate by defining $z = 1 / r$ . Therefore, the infinite boundary is now at $z = 0$ and the soliton tip sits at $z _ { 0 } = 1 / r _ { 0 } = 1$ .Figure $( 1 )$ exhibits a typical solution，where $A ( z )$ and $B ( z )$ are two metric functions, and $\psi ( z )$ and $\phi ( z )$ are the scalar field and static electric potential, respectively. Note that the metric functions $A ( z )$ and $B ( z )$ will be used in calculating the holographic entanglement entropy.

For different choices of $\psi ( r _ { 0 } )$ , the identification length $\Gamma$ in $\chi$ coordinate will be different. In order to compare different solutions with the same boundary behavior, we can use the symmetry (14) to set the boundary geometry the same. Taking advantage of the scaling symmetry (14), the relevant quantities scale as follows

$$
\Gamma  \frac { 1 } { \alpha } \Gamma , \mu  \alpha \mu , \rho  \alpha ^ { 3 } \rho , \langle \hat { O } _ { 2 } \rangle  \alpha ^ { \frac { 5 } { 2 } } \langle \hat { O } _ { 2 } \rangle .
$$

The combinations $\mu \Gamma$ ， $\rho \Gamma ^ { 3 }$ and $\langle \hat { O } _ { 2 } \rangle ^ { \frac { 5 } { 2 } } \Gamma$ are all scale invariant. By using these scale invariant quantities, we can accomplish our purpose easily. As in our units setup, the identification length $\Gamma$ in the pure soliton is $\pi$ ， we scale all $\Gamma$ for each solution to be $1 ^ { \prime } = \pi$ from now on. We should stress here that after the scaling transformation, the tip $r _ { 0 }$ will be no longer at $r _ { 0 } = 1$ ：

Figure(2) reproduces the results in Ref. [26] by a slightly different manner. It shows the condensate and the charge density as functions of chemical potential. It is clear from the figure that as the chemical potential $\mu$ exceeds a critical value $\mu _ { c }$ for given mass and charge, the condensation of the operators emerges. This can be identified as a superconductor (superfluid) phase. However, when less than $\mu _ { c }$ , the scalar field is vanishing and this can be thought of as the insulator phase, since this system has a mass gap $\sim 1 / \Gamma$ due to the identification in $\chi$ direction.Note that it is a second order phase transition in our choice of parameters. In addition,let us mention that in the theory described by the action (3) except for the AdS soliton solution (insulator) and hairy soliton solution (superconducting soliton） mentioned above, there do exist another two solutions: the black hole solution without hair (metal phase） and black hole solution with hair (another superconducting phase). The complete phase diagram has been drawn in [26]. The details depends on the coupling constant $q$ . In this paper we just focus on the case with zero temperature insultor/superconductor phase transition. As shown in [26], with our choice of parameters $m ^ { 2 } = - { \frac { 1 5 } { 4 } }$ and $q = 2$ , the phase transition from the insulator to the superconductor always happens. In particular, for any values of chemical potential beyond the critical one, the superconducting phase always exists.

![](images/ef2b3f4e469e9e45b1be7d808671a35030a55f40650234e3ed7195ffcb71fa5e.jpg)  
Figure 1: A typical soliton solution with nonvanishing scalar hair. Here the value of the scalar at tip is $\psi _ { 0 } = 0 . 5$ and the corresponding identification $\Gamma \simeq 3 . 0 0 8 5$ ：

# 4 Holographic Entanglement Entropy

After finding the gravitational soliton solution with full back reaction of matter fields, we are now ready to calculate the holographic entanglement entropy in this holographic model. Due to the fact that the choice of the subsystem $\mathcal { A }$ is arbitrary, we can define infinite entanglement entropies accordingly. In this paper we first consider a simple case where $\mathcal { A }$ is chosen to be a half of the total boundary space. We assume that the subsystem is defined by $x > 0$ and extended in the $y$ and $\chi$ directions, where $\begin{array} { r } { - \frac { R } { 2 } < y < \frac { R } { 2 } } \end{array}$ （ $R \to \infty$ ）， $0 \leq \chi \leq 1 ^ { \prime }$ ： Then the entanglement entropy can be deduced from the formula (2） as

![](images/f38fe5199bc1dd71d506b0d0d84a08bb83a1a194c5e7e4325742002d85059be2.jpg)  
Figure 2: The condensate of operator $\langle \hat { O } _ { 2 } \rangle$ (left plot） and the charge density $\rho$ (right plot) versus chemical potential $\mu$ respectively. Here $m ^ { 2 } = - 1 5 / 4$ ， $q = 2$ and $\Gamma$ is scaled to be $\pi$ . The critical chemical potential in this case is $\mu _ { c } \simeq 0 . 9 4 4 2$ . It is a typical second order phase transition which can be seen clearly from $\mu \sim \rho$ plot.

$$
S _ { \mathcal { A } } ^ { h a l f } = \frac { R \Gamma } { 4 G _ { N } } \int _ { r _ { 0 } } ^ { \frac { 1 } { \epsilon } } r e ^ { \frac { A ( r ) } { 2 } } d r .
$$

For the pure AdS soliton solution, $\begin{array} { r } { \Gamma = \frac { \pi L } { r _ { 0 } } } \end{array}$ and we can read $A ( r )$ from metric (4） that $A ( r ) = 0$ . So the entropy can be easily calculated as follows.

$$
S _ { A } ^ { h a l f } = \frac { R \Gamma } { 4 G _ { N } } \int _ { r _ { 0 } } ^ { \frac { 1 } { \epsilon } } r d r = \frac { R \Gamma } { 8 G _ { N } } r ^ { 2 } \mid _ { r _ { 0 } } ^ { 1 / \epsilon } = \frac { \pi L R } { 8 G _ { N } r _ { 0 } } ( \frac { 1 } { \epsilon } ) ^ { 2 } - \frac { \pi L R } { 8 G _ { N } } r _ { 0 } = \frac { R \pi } { 8 G _ { N } } ( \frac { 1 } { \epsilon ^ { 2 } } - 1 ) ,
$$

where $\begin{array} { r } { r = \frac { 1 } { \epsilon } } \end{array}$ is the UV cutoff. Note that in our units setup $L = 1 , r _ { 0 } = 1 , \Gamma = \pi$ . The first term is divergent ( $\epsilon  0$ ）and represents the “area law” [2O]. In contrast, the second term does not depend on the cutoff and thus is physical important. In fact,this finite term is the difference between the entropy in the pure AdS soliton and the one in the pure AdS space,because in both cases the divergent part of the entanglement entropy is the same. The result in (18) implies that the entropy in the AdS soliton is less than the one in the pure AdS space.

Note that the UV behavior of $S _ { A }$ will not change after the operator condensation. Thus the divergent part of the entropy known as the area law will not change because this part is only sensitive to UV quantities. This can be understood from the gravity solution side, the new solution after the operator condensation still asymptotically approaches to AdS space near the AdS boundary. We can write the entanglement entropy in general in the half embedding case as

$$
S _ { \mathcal { A } } ^ { h a l f } = \frac { R \Gamma } { 4 G _ { N } } \int _ { r _ { 0 } } ^ { \frac { 1 } { \epsilon } } r e ^ { \frac { A ( r ) } { 2 } } d r = \frac { R \pi } { 8 G _ { N } } ( \frac { 1 } { \epsilon ^ { 2 } } + s ) ,
$$

where $s$ has no divergence and $s = - 1$ corresponds to the pure AdS soliton. The value of $s$ as a function of chemical potential $\mu$ in the superconductor phase is presented in Figure (3). One can see from the figure that the entanglement entropy is a constant in the insulator phase.After condensate, the entropy first rises and arrives at its maximum as the chemical potential $\mu$ increases, then it decreases monotonously. Thus, from $\mu _ { c }$ to a certain value of $\mu$ , there exits a region where the entropies in the superconductor phase are larger than the one in the insulator phase. This behavior of entanglement entropy is quite different from the one discussed in Ref. [24],where the case for the holographic metal/superconductor phase transition has been studied in detail. It is shown that the entanglement entropy after condensate is always lower than the one in the metal phase and decreases monotonously as temperature is lowered, and the entropy as a function of temperate is found to have a discontinuous slop at the transition temperature $T _ { c }$ ，which indicates a reduction in the number of degrees of freedom after condensate. Similarly, we here also find a discontinuity in the slope of the increasing entropy at the critical chemical potential $\mu _ { c }$ indicated by the vertical dotted black line in Figure (3)，which may be considered as a significant reorganization of the degrees of freedom of the system. Furthermore, this discontinuity can be regarded as the signature of the second order phase transition.

![](images/62ef8466730c676e74ba503b84230c0c14111663d2fc33ef35437cd7b97f16eb.jpg)  
Figure 3: The entanglement entropy as a function of chemical potential in the half embedding. The solid red curve denotes the entropy in the superconductor phase,while the dashed blue line is for the pure AdS soliton solution. The entropy rises as the chemical potential $\mu$ is increased after the phase transition,arrives at its maximum at a certain $\mu$ ， and then decreases monotonously.

We next consider a more nontrivial geometry which is a straight belt with a finite width $\ell$ along the $x$ direction. The subsystem $\mathcal { A }$ sites on the slice $\begin{array} { r } { r = \frac { 1 } { \epsilon } } \end{array}$ and expends in $y$ and $\chi$ directions. The holographic dual surface $\gamma _ { \mathcal { A } }$ is defined as a three-dimensional surface

$$
t = 0 , x = x ( r ) , - \frac { R } { 2 } < y < \frac { R } { 2 } ( R  \infty ) , 0 \leq \chi \leq \Gamma .
$$

$R$ is the regularized length in $y$ direction. The holographic surface $\gamma _ { \mathcal { A } }$ starts from $\begin{array} { r } { x = \frac { \ell } { 2 } } \end{array}$ at $r = { \frac { 1 } { \varepsilon } }$ , extends into the bulk until it reaches $r = r _ { * }$ , then returns back to the AdS boundary $\begin{array} { r } { r = \frac { \ddot { 1 } } { \epsilon } } \end{array}$ at $\begin{array} { r } { x = - \frac { \ell } { 2 } } \end{array}$ . It is easy to obtain the induced metric on $\gamma _ { \mathcal { A } }$ as

$$
d s ^ { 2 } = h _ { i j } d x ^ { i } d x ^ { j } = \left( \frac { 1 } { r ^ { 2 } B ( r ) } + r ^ { 2 } \left( \frac { d x } { d r } \right) ^ { 2 } \right) d r ^ { 2 } + r ^ { 2 } d y ^ { 2 } + r ^ { 2 } e ^ { A ( r ) } B ( r ) d \chi ^ { 2 } .
$$

Using the proposal (2)，we need to minimize the following functional

$$
S _ { A } [ x ] = \frac { R \Gamma } { 2 G _ { N } } \int _ { r _ { * } } ^ { \frac { 1 } { \epsilon } } r e ^ { \frac { A ( r ) } { 2 } } \sqrt { 1 + r ^ { 4 } B ( r ) ( d x / d r ) ^ { 2 } } d r .
$$

We can deduce the equation of motion for the minimal surface from (22)

$$
\frac { r ^ { 5 } e ^ { \frac { A ( r ) } { 2 } } B ( r ) ( d x / d r ) } { \sqrt { 1 + r ^ { 4 } B ( r ) ( d x / d r ) ^ { 2 } } } = r _ { s } ^ { 3 } e ^ { \frac { A ( r _ { s } ) } { 2 } } \sqrt { B ( r _ { s } ) } ,
$$

where $r _ { s }$ is a constant.

We are interested in the case that the surface is smooth at $r = r _ { * }$ ,i.e. $d x / d r | _ { r = r _ { * } }  \infty$ This condition ensures that $r _ { s } = r _ { * }$ . The width $\ell$ of the subsystem $\mathcal { A }$ and $r _ { * }$ are connected by the relation

$$
{ \frac { \ell } { 2 } } = \int _ { r _ { * } } ^ { \frac { 1 } { \epsilon } } { \frac { d x } { d r } } d r = \int _ { r _ { * } } ^ { \frac { 1 } { \epsilon } } { \frac { 1 } { r ^ { 2 } { \sqrt { B ( r ) ( { \frac { r ^ { 6 } B ( r ) e ^ { A ( r ) } } { r _ { * } ^ { 6 } B ( r _ { * } ) e ^ { A ( r _ { * } ) } } } - 1 ) } } } } d r .
$$

Finally, we obtain the entanglement entropy as

$$
S _ { A } = \frac { R \Gamma } { 2 G _ { N } } \int _ { r _ { * } } ^ { \frac { 1 } { \epsilon } } \frac { r ^ { 4 } \sqrt { B ( r ) } e ^ { A ( r ) } } { \sqrt { r ^ { 6 } B ( r ) e ^ { A ( r ) } - r _ { * } ^ { 6 } B ( r _ { * } ) e ^ { A ( r _ { * } ) } } } d r = \frac { R \Gamma } { 4 G _ { N } } ( \frac { 1 } { \epsilon ^ { 2 } } + s ) ,
$$

where the UV cutoff has been taken into consideration. However, there is also a disconnected solution describing two separated surfaces that are located at $\begin{array} { r } { x = \pm \frac { \ell } { 2 } } \end{array}$ , respectively. This configuration is just two copies of the half embedding solution that we discussed above.So the entanglement entropy of the disconnected configuration is trivially twice of the half embedding case (19).

We find the behaviors of the entanglement entropy as a function of the belt width （204号 $\ell$ are quite similar for various chemical potential $\mu$ or condensation $\langle \hat { O } \rangle$ .The result for $\mu \ = \ 2 . 2 0 1 6$ is shown in Figure (4) as a typical example. When $\ell > \ell _ { m a x }$ ， there does not exist connected surface. The physically favored solution is replaced by the trivial disconnected one in this case. On the other hand,when $\ell < \ell _ { m a x }$ ，we have three different branches of entropy for a given $\ell$ ，i.e.，the upper connected branch (dashed magenta curve), the lower connected branch (solid red curve) and the middle disconnected branch (solid blue line). The physical entropy is determined by the choice of the lowest one. As we can see from Figure (4), for small $\ell$ ， the lower connected branch is favored. However, there is a critical value $\ell _ { c r i t i c a l }$ above which the lower connected branch is not a physical one since its entropy is larger than the one for the disconnected solution. Thus,when $\ell$ increases， a phase transition occurs as belt width $\ell = \ell _ { c r i t i c a l }$ . This is just the so-called "confinement/deconfinement” phase transition discussed intensively in Refs. [20, 21, 22, 23]. The transition can be understood as the fact that no correlation could be contributed among a distance larger than $\Gamma$ due to the mass gap $\sim 1 / \Gamma$ ：

![](images/60174876c6ff8047b8a74f47939097eb81878e4e0d5c4d75482c2b5bcd5fa895.jpg)  
Figure 4: The entanglement entropy as a function of strip width $\ell$ for $\mu = 2 . 2 0 1 6$ .The dashed magenta and solid red curves come from the connected solutions, while the solid blue one comes from the disconnected one. The lowest curve is physically favored compared with others because it has minimal entropy.

More numerical results for entanglement entropy are exhibited in Figure (5) with different chemical potential. For $\ell < \ell _ { c r i t i c a l }$ at fixed chemical potential, the entropy is dominated by the connected surface and exhibits a non-trivial dependence on $\ell$ . On the contrary, it is governed by the disconnected configuration and is independent of $\ell$ for $\ell > \ell _ { c r i t i c a l }$ ： The fact that the phase transition always appears at critical length $\ell _ { c r i t i c a l }$ is observed for all values of $\mu$ matches the prediction in Ref. [21] that this “confinement/deconfinemnet" phase transition must be exhibited in any consistent gravity dual of a confining theory. We find that $\ell _ { m a x } \simeq ( 0 . 2 2 0 \sim 0 . 2 3 7 ) \Gamma$ and $\ell _ { c r i t i c a l } \simeq ( 0 . 2 0 4 \sim 0 . 2 2 1 ) \Gamma$ for various chemical potentials up to $\mu = 5 . 1 6 4$ in our numerical calculation. If the belt width is large enough ( $\ell > 0 . 2 3 7 \Gamma$ )，the disconnected branch is always favored for all values of $\mu$ ．Thus，the behavior of $s$ as a function of $\mu$ for fixed $\ell$ is the same as the one shown in Figure (3).

![](images/e4e80a73d831e9164ed38857990f928488ba0918ceb521017ce56a9e91646282.jpg)  
Figure 5: The entanglement entropy as a function of belt width $\ell$ for different chemical potential $\mu$ . The dotted black curve is for the pure AdS soliton solution. With a fixed $\ell$ 5 the entanglement entropy increases (left plot） and then decreases (right plot） as $\mu$ becomes large.

It is helpful to slice the data in superconducting phase differently. We first study how the entropy of the system changes with chemical potential $\mu$ for fixing belt width $\ell$ ，which is presented in the left plot of Figure (6). It can be seen clearly that the entanglement entropy as a function of chemical potential for fixed $\ell$ has similar behavior as in the half embedding case. In particular,the purple curve in the confined phase is the same as that in Figure (3),in which $\ell  \infty$ . As the chemical potential $\mu$ increases，the entropy first rises and reaches its maximum at a certain value of chemical potential denoted as $\mu _ { m a x }$ ， then it decreases monotonously. The curve will flatten out as we decrease the belt width （204号 $\ell$ . The curve will finally become a line in the limit $\ell \to 0$ ， which can be understood from the geometric viewpoint. The minimal surface with smal belt length can only probe the bulk sufficiently near the boundary $r  \infty$ where the metric solution is nearly pure AdS. Furthermore, the value of $\mu _ { m a x }$ also decreases as we decrease the belt width $\ell$ . The values of critical belt width and entropy at the “confinement/deconfinemnet” transition point for different chemical potential are drawn in the right plot of Figure (6). The knot is a consequence of the non-monotonic behavior of the entanglement entropy.

In the deconfinement phase with $\ell < 0 . 2 2 1 \Gamma$ ，the connected branch appears, so the quantitative behavior of $s ( \mu , \ell )$ changes. In order to measure the degrees of freedom at energy scale $\sim 1 / \ell$ in this situation，we would like to calculate the so-called entropic c-function first introduced in Ref. [20]

$$
c ( \ell ) = \ell ^ { 3 } { \frac { d s ( \ell ) } { d \ell } } .
$$

The entropic c-function as a function of belt width $\ell$ for a fixed $\mu$ is plotted in Figure （7) Just as it is expected, the value of $c$ decreases monotonically as we increase the belt width $\ell$ Due to the appearance of mass gap $\sim 1 / \pi$ , the c-function jumps to zero at the critical width （204号 $\ell _ { c r i t i c a l }$ ( $\ell _ { c r i t i c a l } \simeq 0 . 6 6 1$ in Figure (7)） and keeps vanishing for larger $\ell$ . This is just the reason that one calls the phase transition mentioned above the “confinement/deconfinement”

![](images/5c28b50eae12441a042ac5789ca13798fa08d6cb590551b3f326bcb8b8e45a7b.jpg)  
Figure 6: The entanglement entropy of the system changes with chemical potential $\mu$ for fixing belt width $\ell$ (left plot). The red curve is for $\ell = 0 . 5 2 < \ell _ { c r t i c a l }$ and the blue one for $\ell = 0 . 5 7 < \ell _ { c r i t i c a l }$ . The purple curve is for sufficiently large $\ell > \ell _ { m a x }$ in the confining phase. The right plot presents the behavior of entropy as a function of belt width at critical point of the “confinement/deconfinement” transition for different chemical potential.

phase transition [20, 21, 22, 23]. We also show the change of entropic c-function as we tune the value of chemical potential for a fixed small $\ell$ in Figure(7). We can also see from the figure the non-monotonic behavior with the increment of chemical potential. Furthermore, the curve becomes flat as we decrease the belt width $\ell$ . It can be expected that the curve will finally become a line in the limit $\ell \to 0$ from the perspective of gravity side. The behavior of entropic c-function as a function of chemical potential for a fixed small $\ell$ is quite qualitatively similar to the entropy in Figure (6). The key diference here is that the entropy increases as we increase the belt width,while the c-function decrease for fixed chemical potential. But an important feature we observed here is that in both phases,“confinement and deconfinement phases”,the entanglement entropy is always non-monotonic in the superconducting phase.

To summarize, there do totally exist four phases probed by the entanglement entropy for a belt geometry for this holographic system,i.e.,the confinement/deconfinement insulator phase, and confinement/deconfinement superconductor phase. These phases are characterized by the chemical potential and belt width. In particular,the belt width controls the “confinement/deconfinement” phase transition. Strictly speaking, the term phase transition here is inappropriate since the system itself, i.e., the state of the boundary field theory, does not change at all as one changes the belt width $\ell$ . However, this behavior is reminiscent of many thermodynamic phase transitions in holographic calculations (see, for example Refs. [28, 29]) and so here we adopt the terminology “phase transition” to convey this picture as in the literature [20, 21, 22, 23]. Then one can draw the “phase diagram” as in Figure (8) for the system. The left part of the diagram is not new but just the one for the pure AdS soliton case which has been studied in Ref. [20]. In the superconductor phase, we find a non-trivial phase boundary between the confinement and deconfinement phases. In this sense our work is a generalization of Refs. [20, 21, 22, 23] to the superconducting

![](images/29b31aca34a501d70aff441da045992f6158a76968e0c5e67449e5ec96fcfb67.jpg)  
Figure 7: The entropic c-function as a function of belt width $\ell$ for $\mu = 1 . 1 0 9 6$ (left plot) and of chemical potential $\mu$ at fixed $\ell = 0 . 5$ (right upper curve） and $\ell = 0 . 6$ (right down curve), respectively.

soliton solution.

The non-monotonic behavior of the entanglement entropy in the superconductor phase looks strange at first glance. It is quite different from the case in the metal/superconductor transition [24], in which the result of the entanglement entropy decreasing as the temperature is lowered agrees with the fact that more degrees of freedom will be condensed in lower temperature. In our case, one can see from Figure (6) and Figure(7) that the behavior of both entropy and entropic c-function can be affected by belt width. However,the belt width $\ell$ does not play the essential role for the non-monotonic behavior. As we observed above,the non-monotonic behavior occurs in both the confinement and deconfinement superconducting phases.

Due to the lack of the knowledge of the dual field theory in the “bottom-up” approach, we do not know the details of the microscopic degrees of freedom and thus it is quite difficult to give a definite interpretation of the non-monotonic behavior of the entanglement entropy in the holographic insulator/superconductor phase transition. In order to understand the numerical result, however, we here try to give a simple physical picture as follows. Note that the entanglement entropy as a function of temperature near the critical temperature （204号 $T _ { c }$ shows the same behavior in s-wave and p-wave holographic metal/superconductor models [24, 30]. The metal phase can be thought of as the one filled with free charge carriers, such as electrons. At the critical temperature the condensate turns on and the free charge carriers are continuously condensed to a certain microstate as temperature is lowered. As a result, the entanglement entropy in the superconducting phase is always less than the one in the metal phase and decreases monotonically as temperature is lowered. In contrast, the insulator phase can be considered as having a little degrees of freedom and almost all charge carriers are bound and can not move freely. This is due to the appearance of a mass gap $\sim 1 / \Gamma$ which is the crucial distinction between the holographic metal/superconductor and insulator/superconductor transition. At the beginning of the phase transition the condensate emerges. Thus, a new kind of charge carriers (some quasi-particles like cooper pairs) that can move unconstrained make contribution to the degrees of freedom,which leads to the increase of the entanglement entropy. When the chemical potential is enough large,however, all bounded carriers are condensed to form cooper pairs. The system in this case is fullof “cooper pairs” and thus is an ordered state seen from momentum space. As a result, the number of degrees of freedom now are even less than the one in the insulator phase. The above argument may account for the non-monotonic behavior of the entanglement entropy in the insulator/superconductor phase transition.

![](images/97491905912cc45e3a8d91839c2dcd3f6bb6436c60ec3ab5e9016c7214dd016e.jpg)  
Figure 8: The “phase diagram” of entanglement entropy for a belt geometry in the holographic insulator/superconductor model for $m ^ { 2 } = - { \frac { 1 5 } { 4 } }$ ， $q = 2$ ，and $1 ^ { \prime } = \pi$ .The phase boundary between the confinement phase and deconfinement phase is denoted by the dotted blue line and solid red curve, while the insulator phase and superconductor phase are separated by the vertical dashed line.

To further understand the non-monotonic behavior of the entanglement entropy in the insulator/superconductor phase transition, it might be helpful to recall the microscopic model presented in [9]，where the authors wanted to compare the holographic insulator/superconductor transition with high- $T _ { c }$ cuprates, in particular with the RVB (resonating valence bond） scenario of high- $T _ { c }$ electron doped cuprates (e.g., Nd $2 - x$ Ce $_ x$ CuO $_ 4$ ). The phase diagrams for both systems are quite similar. The high- $T _ { c }$ cuprate at $x = 0$ (in the under-doped region, here $x$ stands for the electron doping) is the antiferromagnetic insulator.By doping holes,one frustrates the antiferromagnetic order and eventually destroys it. Beyond some critical doping $x _ { c }$ , the superconducting ground state emerges. The physics of the under-doped cuprates is well-described by the t-J model [9]. In the slave-boson (SU(2) slave-boson) approach, the electron operators can be decomposed into bosonic and fermionc parts,caled holons and spinons,respectively. In the confined insulator phase, spinons and holons are completely glued together. At the beginning of phase transition, the holons get condensed and the degrees of spinons might be released. This might be the reason that the entanglement entropy increases compared to the case in the insulator phase. When the electron doping continues to increase (chemical potential gets large enough in the holographic insulator/superconudctor phase transition)，the spinons will form cooper pairs and the degrees of freedom associated with spinons get condensed. In that case,the entanglement entropy of the system is even less than the case in the insulator phase. This model might explain the non-monotonic behavior of the entanglement entropy. But one caveat should be stressed here that in the gravity setup of the holographic insulator/superconductor model, an extra scalar field which is dual to the fermion bilinear in the field side does not included [9]. But one expects that including the extra scalar field to the model will not change the background geometry very much, so that the entanglement entropy keeps the same behavior. Of course, the above discussions are just some speculations, further more deep understanding for the non-monotonic behavior of the entanglement entropy is called for.

# 5 Summary and Discussions

By using entanglement entropy as a probe, in this paper, we investigated the holographic insulator/superconductor phase transition in a five dimensional Einstein-Maxwel-complex scalar theory with a negative cosmological constant，we calculated the entanglement entropy of dual field theory with two kinds of geometry in the AdS boundary: one is a half space,and the other is a belt geometry with width $\ell$ . In the former case, we found that there does exist a discontinuity of the slop of the entropy with respect to the chemical potential at the phase transition point. This discontinuity could be thought of as a significant reorganization of the degrees of freedom of the system and a signature of the phase transition. Beyond the critical chemical potential, we found that the entanglement entropy is not monotonic in the superconductor phase: at the beginning of the transition, the entropy increases and arrives at its maximum at a certain chemical potential, and then decreases monotonically.

In the belt geometry case, the so-called “confinement/deconfinement phase transition" happens in both the insulator and superconductor phases. As $\ell < \ell _ { c r i t i c a l }$ the connected surface is favored and the entropy depends on belt width $\ell$ non-trivially， while as $\ell > \ell _ { c r i t i c a l }$ the disconnected surface is favored and the entropy is $\ell$ independent. The results enhance the prediction made in Ref. [21] that this phase transition must happen in any consistent gravity dual of a confining theory. Thus, as a result, there do exist four different“phases” characterized by chemical potential $\mu$ and belt width $\ell$ , in the holographic insulator/superconductor phase transition. The complete “phase diagram” is drawn in Figure (8).

We observed the non-monotonic behavior of the entanglement entropy with respect to the chemical potential $\mu$ in both the “confinement/deconfinement superconductor phases. The entanglement entropy firstly rises and reaches its maximum at a certain chemical potential and then decreases monotonically (see Figure (3) and Figure (6)). Although the entanglement entropy and entropic c-function depend on the belt width, it does not play any essential role in the non-monotonic behavior of the entanglement entropy. The non-monotonic behavior of the entanglement entropy could be thought of as a key characteristic of difference between the holographic insulator/superconductor transition and the metal/superconductor transition. In the latter case, the entanglement entropy as a function of temperature near the critical transition point always monotonicall decreases as temperature is lowered [24, 30]. Clearly it would be of some interest to check whether the non-monotonic behavior of the entanglement entropy is universal in other holographic insulator/superconductor model, for example, the p-wave case [32].

In addition it is worth stressing here that we did not have a clear microscopic interpretation for the non-monotonic behavior of the entanglement entropy, but we did present some arguments which try to give a physical picture for this behavior. Needless to say, it is quite necessary to deeply understand this behavior further.

In this paper, we have limited ourselves to the choice of parameters as $\psi ^ { ( 1 ) } = 0$ ， $m ^ { 2 } =$ $- \frac { 1 5 } { 4 }$ ,and $q = 2$ Notett （204号 $q$ . It is worthy studying the cases with other $( m ^ { 2 } , \ q )$ 's and the case at finite temperature. It is also interesting to study entanglement entropy in other holographic superconductor models, such as the holographic p-wave superconductor [31, 32, 33, 34]. What's more, it is of some interest to see the effect on the entanglement entropy of the magnetic field in the holographic superconductors [35, 36, 37]. We will leave them for future studies.

# Acknowledgements

RGC thanks T. Takayanagi for helpful correspondences and the authors thank ZhangYu Nie, Hai-Qing Zhang and Shu-Hao Zou for their helpful discussions and suggestions. This work was supported in part by the National Natural Science Foundation of China (No.10821504, No.10975168 and No.11035008),and in part by the Ministry of Science and Technology of China under Grant No. 2010CB833004.

# References

[1] J. M. Maldacena, “The large N limit of superconformal field theories and supergravity,” Adv. Theor. Math. Phys.2, 231 (1998) [Int. J. Theor.Phys.38,1113(1999)] [arXiv:hep-th/9711200].   
[2] S. S. Gubser, I. R. Klebanov and A. M. Polyakov, “Gauge theory correlators from non-critical string theory,” Phys. Lett. B 428,105 (1998) [arXiv:hep-th/9802109].   
[3] E.Witten,_“Anti-de Sitter space and holography,” Adv. Theor. Math. Phys. 2, 253 (1998) [arXiv:hep-th/9802150].   
[4] O.Aharony, S. S.Gubser, J. M. Maldacena, H. Ooguri and Y. Oz, “Large N field theories, string theory and gravity,” Phys. Rept. 323,183 (2000) [arXiv:hep-th/9905111].   
[5] S. S. Gubser,“Breaking an Abelian gauge symmetry near a black hole horizon,” Phys. Rev. D 78, 065034 (2008) [arXiv:0801.2977 [hep-th]]. [6] S. A. Hartnoll, C. P. Herzog and G. T. Horowitz, “Building a Holographic Superconductor,” Phys.Rev.Lett.101, 031601 (2008) [arXiv:0803.3295 [hep-th].   
[7] S.A. Hartnoll, C. P. Herzog and G. T. Horowitz, “Holographic Superconductors,” JHEP 0812, 015 (2008)[arXiv:0810.1563 [hep-th].   
[8] S. S. Gubser, “Colorful horizons with charge in anti-de Sitter space,” Phys. Rev. Lett. 101,191601 (2008） [arXiv:0803.3483 [hep-th].   
[9] T.Nishioka, S. Ryu and T. Takayanagi, “Holographic Superconductor/Insulator Transition at Zero Temperature,” JHEP i003,131 (2010) [arXiv:0911.0962 [hep-th].   
[10] S. Ryu_and T. Takayanagi， “Holographic derivation of entanglement entropy from AdS/CFT,”Phys.Rev.Lett. 96,181602 (2006) [hep-th/0603001].   
[11] S. Ryu and T. Takayanagi, “Aspects of Holographic Entanglement Entropy,” JHEP 0608,045 （2006)[hep-th/0605073].   
[12] L. Susskind and E. Witten，“The Holographic bound in anti-de Sitter space,” hepth/9805114.   
[13] D. V. Fursaev, “Proof of the holographic formula for entanglement entropy,” JHEP 0609,018 (2006） [hep-th/0606184].   
[14] T. Hirata and T. Takayanagi, “AdS/CFT and strong subadditivity of entanglement entropy,” JHEP 0702,042 (2007） [hep-th/0608213].   
[15] T. Nishioka, S. Ryu and T. Takayanagi, Holographic Entanglement Entropy: An Overview,” J. Phys. A A 42, 504008 (2009) [arXiv:0905.0932 [hep-th].   
[16] T. Albash and C.V. Johnson,“Holographic Entanglement Entropy and Renormalization Group Flow,” JHEP 1202,095 (2012) [arXiv:1110.1074 [hep-th].   
[17] R. C. Myers and A. Singh, “Comments on Holographic Entanglement Entropy and RG Flows,” arXiv:1202.2068 [hep-th].   
[18] J. de Boer, M. Kulaxizi_and A._Parnachev,“Holographic Entanglement Entropy in Lovelock Gravities,” JHEP 1107,109 (2011) [arXiv:1101.5781 [hep-th]].   
[19] L. -Y. Hung,R. C. Myers and M. Smolkin, “On Holographic Entanglement Entropy and Higher Curvature Gravity,” JHEP 1104, 025 (2011) [arXiv:1101.5813 [hep-th].   
[20] T.Nishioka and T. Takayanagi, “AdS Bubbles, Entropy and Closed String Tachyons,” JHEP 0701,090 (2007） [hep-th/0611035].   
[21] I. R. Klebanov, D. Kutasov and A. Murugan, “Entanglement as a probe of confinement,” Nucl. Phys. B 796, 274 (2008) [arXiv:0709.2140 [hep-th].   
[22] A. Pakman_and A. Parnachev, “Topological Entanglement Entropy and Holography,” JHEP 0807, 097 (2008) [arXiv:0805.1891 [hep-th]].   
[23] N. Ogawa and T. Takayanagi， “Higher Derivative Corrections to Holographic Entanglement Entropy for AdS Solitons,” JHEP 1110,147(2011) [arXiv:1107.4363 [hepth]].   
[24] T. Albash and C. V._Johnson, “Holographic Studies of Entanglement Entropy in Superconductors,” arXiv:1202.2605 [hep-th].   
[25] G. T. Horowitz, R. C. Myers,“The AdS / CFT correspondence and a new positive energy_conjecture for general relativity,” Phys. Rev. D59, 026005 (1998). [hepth/9808079].   
[26] G. T. Horowitz and B. Way, “Complete Phase Diagrams for a Holographic Superconductor/Insulator System,” JHEP 1011, 011 (2010) [arXiv:1007.3714 [hep-th]].   
[27] I. R. Klebanov and E. Witten, “AdS_/ CFT correspondence and symmetry breaking," Nucl. Phys. B 556, 89 (1999) [hep-th/9905104].   
[28] A. Chamblin, R. Emparan, C. V. Johnson and R. C. Myers, “Charged AdS black holes and catastrophic holography,” Phys. Rev. D 60, 064018 (1999) [hep-th/9902170].   
[29] D. Mateos, R. C. Myers and R. M. Thomson, “Holographic phase transitions with fundamental matter," Phys.Rev. Lett. 97, 091601 (2006) [hep-th/0605046].   
[30] R. -G. Cai, S. He, L. Li and Y. -L. Zhang，“Holographic Entanglement Entropy on P-wave Superconductor Phase Transition,” arXiv:1204.5962 [hep-th].   
[31] S.S. Gubser and S. S. Pufu,“The Gravity_dual of a p-wave superconductor,” JHEP 0811,033 (2008) [arXiv:0805.2960 [hep-th]].   
[32] A. Akhavan and.M. Alishahiha，“P-Wave Holographic Insulator/Superconductor Phase Transition,” Phys. Rev. D 83,086003 (2011) [arXiv:1011.6158 [hep-th].   
[33] R. G. Cai, Z. Y. Nie and H. Q. Zhang,“Holographic_p-wave superconductors_from Gauss-Bonnet gravity,” Phys. Rev. D 82 (2010) 066007 [arXiv:1007.3321 [hep-th]].   
[34] R. -G. Cai, Z. -Y. Nie and H. -Q. Zhang,“Holographic Phase Transitions of P-wave Superconductors in Gauss-Bonnet Gravity with Back-reaction,” Phys. Rev. D 83, 066013（2011） [arXiv:1012.5559 [hep-th]].   
[35] T. Albash and C. V. Johnson, “A Holographic Superconductor in an External Magnetic Field,” JHEP 0809,121 (2008) [arXiv:0804.3466 [hep-th]].   
[36] X. -H. Ge, B. Wang, S. -F. Wu and G. -H. Yang,“Analytical study on holographic superconductors in external magnetic field,” JHEP 1008,108 (2010) [arXiv:1002.4901 [hep-th]].   
[37] R. -G. Cai,L. Li, H. -Q. Zhang and Y. -L. Zhang,“Magnetic Field Effect on the_Phase Transition in_AdS Soliton Spacetime,” Phys. Rev. D 84, 126008 (2011) [arXiv:1109.5885 [hep-th].