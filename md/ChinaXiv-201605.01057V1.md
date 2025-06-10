# Collapse of self-interacting scalar field in anti-de Sitter space

Rong-Gen Cai,\* Li-Wei Ji,† and Run-Qiu Yangt StateKey Laboratory of Theoretical Physics,Institute of Theoretical Physics, Chinese Academy of Sciences,Beijing 10019o，China.

The gravitational collapse of a massless scalar field with a self-interaction term $\lambda \phi ^ { 4 }$ in anti-de Siter space is investigated.We numerically investigate the effct of the self-interaction term on the critical amplitudes,forming time of apparent horizon,stable island and energy transformation. The results show that a positive $\lambda$ suppresses the formation of black hole,while a negative $\lambda$ enhances the process.We define two susceptibilities to characterize the effect of the self-interaction on the black hole formation,and find that near the critical amplitude,there exists a universal scaling relation with the critical exponent $\alpha \approx 0 . 7 4$ for the time of black hole formation.

# I.INTRODUCTION

Recently,a lot of attention has been focused to gravitational collapse in anti-de Sitter(AdS） spacetime.On the one hand,AdS spacetime is one of three maximal symmetric spacetimes (the other two are Minkowskian and de Sitter spacetimes).The gravitational collapse in AdS spacetime is an interesting issue in its own right.On the other hand, AdS spacetime is a ground state of some superstring/M theories.Due to the so-called AdS/CFT correspondence, the form of black holes in AdS space is equivalent to the thermalization process of dual conformal field theory (CFT) in the AdS boundary.

However，due to the complexity of Einstein's field equations,it is quite hard to solve this problem analytically.Numerical methods and perturbation methods are usually employed for this goal. The pioneering numerical study on this issue finds that an arbitrary small spherically symmetric initial data of massless scalar field will collapse to form black hole [1-3]. Other class of perturbations leads to a similar conclusion [4].This implies that the AdS spacetime is unstable nonlinearly, quite different from the cases of Minkowskian and de Sitter spacetimes. Later on，exceptions were found in works [5,6]，which show that there exist stable initial data immune to the black hole formation.Generalizations to massive scalar fields are investigated in [7-9].

On the perturbation method side,improved perturbative expansions have been constructed to describe the small amplitude dynamics on time scales of order $1 / \epsilon ^ { 2 }$ where $\epsilon$ denotes the amplitude of perturbation.The effective equations which describe the variations of the amplitudes and phases of AdS normal modes due to nonlinearities are derived using multiscale [1O],renormalization [11] and averaging [12] methods.

There are two crucial ingredients which are responsible for the instability of AdS space: confinement property of AdS boundary and local non-linearity. To investigate the role played by local non-linearity, new non-linearity due to higher curvature terms has been studied in [13]. They found that the stability of AdS in 5D Einstein-GaussBonnet gravity can be restored for small perturbations, due to the existence of mass gap of the Gauss-Bonnet black hole.Instead of adding new non-linear terms from gravity sector,in this paper,we consider the effect of self-interaction of matter field itself on the stability of AdS space. For simplicity,we consider the $\lambda \phi ^ { 4 }$ model of a massless scalar field.

The self-interaction has been considered in asymptotically flat spacetime [14]，which provides effective confinement and gives rise to some interesting phenomena. This is believed to have some connection with the massless scalar collapse in AdS spacetime. The energy flow between different modes on a fixed AdS background has been observed in [15] with self-interaction providing the nonlinearity. Note that the energy flow is very important for the weakly turbulence instability of AdS spacetime. Therefore, the self-interaction provides another “instability engine".These two engines may compete or cooperate with each other,which means that the self-interaction may enhance or suppress the instability of the system.

Our main motivation is to explore the effect of selfinteraction on the instability of AdS spacetime.One of our main results is that a positive $\lambda$ suppresses the formation of black hole while a negative one promotes it. In addition，we find a universal scaling relation on the sensibility of black hole formation time with respect to the self-interaction strength $\lambda$ . The paper is organized as follows. In Section II we present the setup of the massless scalar collapse with self-interaction. Section III is devoted to our numerical results. We conclude in Section IV.

# II. SETUP

We consider a real massless scalar field with selfinteraction in 3+1 dimensional spherically symmetric asymptotic AdS spacetime. The system is described by the following action,

$$
S = \int d ^ { 4 } x \sqrt { - g } \left[ \frac { 1 } { 1 6 \pi G } ( { \mathcal R } - 2 \Lambda ) - \frac { 1 } { 2 } ( \nabla \phi ) ^ { 2 } - \frac { \lambda } { 4 ! } \phi ^ { 4 } \right] ,
$$

where $\mathcal { R }$ is the Ricci scalar curvature, $G$ is the Newtonian gravitation constant,and $\lambda$ isareal parameter,describing the self-interaction strength of the scalar field. The Einstein's field equation and the equation of motion of the scalar field read

$$
\begin{array} { l } { { G _ { \alpha \beta } + \Lambda g _ { \alpha \beta } = 8 \pi G \left[ \nabla _ { \alpha } \phi \nabla _ { \beta } \phi - \frac { 1 } { 2 } g _ { \alpha \beta } ( \nabla \phi ) ^ { 2 } - \frac { \lambda } { 4 ! } g _ { \alpha \beta } \phi ^ { 4 } \right] , } } \\ { { g ^ { \alpha \beta } \nabla _ { \alpha } \nabla _ { \beta } \phi - \cfrac { \lambda } { 6 } \phi ^ { 3 } = 0 . } } \end{array}
$$

In order to find the solution of Eqs. (2)-(3) in spherically symmetric AdS spacetime,we take the ansatz for the metric

$$
d s ^ { 2 } = \frac { \ell ^ { 2 } } { \cos ^ { 2 } x } ( - A e ^ { - 2 \delta } d t ^ { 2 } + A ^ { - 1 } d x ^ { 2 } + \sin ^ { 2 } x d \Omega ^ { 2 } ) ,
$$

where $\ell ^ { 2 } = - 3 / \Lambda$ and $d \Omega ^ { 2 }$ is the standard metric on the round unit two-dimensional sphere,and $A , \delta$ and $\phi$ are all functions of time $t$ and radial coordinate $x$ ：

We now introduce two auxiliary variables $\Phi = \phi ^ { \prime }$ and （204号 $\Pi = A ^ { - 1 } e ^ { \delta } \dot { \phi }$ and set $\ell = 4 \pi G = 1$ , then the equations of motion can be written as

$$
\begin{array} { l } { { \displaystyle { \dot { \Phi } = \left( A e ^ { - \delta } \Pi \right) ^ { \prime } , } } } \\ { { \displaystyle { \dot { \Pi } = \frac { 1 } { \tan ^ { 2 } x } \left( \tan ^ { 2 } x A e ^ { - \delta } \Phi \right) ^ { \prime } - \frac { \lambda } { 6 } e ^ { - \delta } \sec ^ { 2 } x \phi ^ { 3 } } . } } \\ { { \displaystyle A ^ { \prime } = \frac { 1 + 2 \sin ^ { 2 } x } { \sin x \cos x } ( 1 - A ) } } \\ { { \displaystyle \qquad - \sin x \cos x A \left( \Phi ^ { 2 } + \Pi ^ { 2 } \right) - \frac { \lambda } { 1 2 } \tan x \phi ^ { 4 } } , }  \\ { { \displaystyle { \dot { \delta } ^ { \prime } = - \cos x \sin x \left( \Phi ^ { 2 } + \Pi ^ { 2 } \right) , } } } \\ { { \displaystyle { \dot { \phi } ^ { \prime } = \Phi } , } } \end{array}
$$

where an overdot stands for the derivative with respect to time $t$ and a prime to the radial coordinate $x$ .This model shares the same boundary conditions as the case without the self-interaction [1]. At the origin $x = 0$ ，

# III. NUMERICALRESULTS

Following [2],we use a 4th-order Runge-Kutta method to solve the time evolution equations (5)-(6). At each time step,the metric functions $A$ and $\delta$ are given by integrating the constraint equations (7)-(8) from the origin to the infinity also using a 4th-order Runge-Kutta method,while the scalar field $\phi$ is given by integrating the equation (9) backward from the infinity to the origin. In order to clearly see the influence of the self-interaction, wealso take the Gaussian initial data for the scalar field as

$$
\Phi ( 0 , x ) = 0 , \Pi ( 0 , x ) = \epsilon \exp \left( - \frac { \tan ^ { 2 } x } { \sigma ^ { 2 } } \right) ,
$$

where $\epsilon$ stands for the amplitude,while $\sigma$ for the width of the initial wave packet.

Under this class of initial data,the stability of spacetime depends on whether a black hole could form after some time,which is signalled by the appearance of an apparent horizon at a point $x _ { H }$ where $A ( t , x )$ falls into zero.There exists strong evidence that the initial data are classified into two categories: unstable states and sta ble states. For those unstable states, the wave configu ration oscillates between the origin and the boundary a few times,then collapses to black hole. For those stable states,the wave configuration stays regular everywhere in the cavity all the time. This kind of states is often referred to as “stable island” in the initial data phase space.There are three parameters in this system: selfinteraction strength $\lambda$ ，amplitude $\epsilon$ and width $\sigma$ of the initial data.We will study the effect of self-interaction on these two kinds of states separately for different amplitude $\epsilon$ and width $\sigma$ ：

$$
\begin{array} { l } { \phi ( t , x ) = f _ { 0 } ( t ) + \mathcal { O } ( x ^ { 2 } ) , } \\ { \delta ( t , x ) = \mathcal { O } ( x ^ { 2 } ) , } \\ { A ( t , x ) = 1 + \mathcal { O } ( x ^ { 2 } ) . } \end{array}
$$

and at the spatial infinity $x = \pi / 2$

$$
\begin{array} { l } { { \phi ( t , x ) = f _ { \infty } ( t ) \rho ^ { 3 } + \mathcal { O } ( \rho ^ { 5 } ) , } } \\ { { \delta ( t , x ) = \delta _ { \infty } ( t ) + \mathcal { O } ( \rho ^ { 6 } ) , } } \\ { { A ( t , x ) = 1 - 2 M \rho ^ { 3 } + \mathcal { O } ( \rho ^ { 6 } ) , } } \end{array}
$$

where $\rho = \pi / 2 - x$

The $\lambda \phi ^ { 4 }$ model appears in many toy models to study the effects of the self-interaction.For quantum field theory in flat spacetime,we need $\lambda \geq 0$ so that the scalar field has a stable ground state. In asymptotic AdS spacetime,because the asymptotic boundary at $x = \pi / 2$ gives an infinite high potential barrier, the massless scalar field can still be stable when $\lambda < 0$ . In this paper,we will consider both $\lambda > 0$ and $\lambda < 0$ to see how these two kinds ofinteractions influence the evolution of the scalar field in AdS space.

# A. Effect on unstable states

To see the effect of the self-interacting term on the instabilityof thesystem,we first fix width $\sigma = 1 / 1 6$ ,and try to find out the influence of $\lambda$ on the unstable states with different $\epsilon$ . Then we try to find out the influence of self-interaction on the unstable states with a few different $\sigma$ ：

# 1.The case with $\sigma = 1 / 1 6$

Since the apparent horizon is formed very close to the center of the space, the time difference of black hole formation due to the different strength of the self-interaction is diluted by the travel time over the whole cavity (from the origin to the boundary).So the time of black hole formation is still dominated by the time of the scalar field oscillation in the cavity. As a result,it is expected that the time difference caused by the self-interaction is small in general.

We fix the width of the initial data $\sigma = 1 / 1 6$ and set $\lambda = - 5 0 0 , - 1 0 0 , 0 , 1 0 0 , 5 0 0$ ，respectively. We show the influence of self-interaction on the formation time of black hole in Fig.1. The general behavior of the black hole formation time is similar to the case of $\lambda = 0$ for every $\lambda$ As the amplitude $\epsilon$ decreases,it approximately forms ascending steps and increases monotonically on every step. On every step,the black hole formation time is almost the same for every $\lambda$ . But as we improve the resolution, which is shown in the middle and bottom plots in Fig. 1, we can see the difference. Fig. $1 ( \mathrm { b } )$ shows the case around $\epsilon \in [ 3 0 , 3 4 ]$ and $t \simeq 4 \times \frac { \pi } { 2 }$ ,while Fig.1(c) shows the case in the same $\epsilon$ region but $t \simeq 2 \times \frac { \pi } { 2 }$ (which are around the second critical amplitude $\epsilon _ { 1 } \simeq 3 2 . 5$ ).If we fix the amplitude,the black hole formation time is decreased with the decrease of $\lambda$ , although very small. However,around the critical amplitude,this time difference between different $\lambda$ can be huge.We look at the critical amplitude around $\epsilon \sim 3 1 . 5$ , for instance. As we can see in Fig .1(b), when $\epsilon \lesssim 3 1$ ，the formation time decreases a little as wedecrease $\lambda$ .In this case,the time difference between $\lambda = - 5 0 0$ and $\lambda = 0$ is roughly $0 . 0 0 6 \times \frac { \pi } { 2 }$ . When $\epsilon \gtrsim 3 1 . 5$ ， some of the initial data disappear in Fig.1(b) and jump to the previous step shown in Fig.1(c).The smaller the self-interaction coefficient, the faster the jump happens. These jumps cause huge time difference between different $\lambda$ . In this case,the time difference between $\lambda = - 5 0 0$ and $\lambda = 0$ could be more than $2 \times \frac { \pi } { 2 }$ . When $\epsilon$ is large enough （ $\epsilon > 3 2 . 5$ in this case),all the formation times jump to the previous step.The similar time jump of black hole formation also happens in the case of $\lambda > 0$

This kind of time jump caused by $\lambda$ near the critical amplitude can be understood as follows.When $\lambda < 0$ ， the self-interaction enhances the instability of the system, which makes the black hole formation a bit earlier than the case without the self-interaction. When this small time shift happens near the critical point,it may push the black hole formation out of the effective concentration region which is a small region very close to the origin of the space.This means that the black hole formation has to occur in the previous effective concentration region，which causes a huge time jump (earlier). When $\lambda > 0$ , the situation is just opposite.The self-interaction makesthe formationofblack holea bitlater.When this suppressing effect happens near the critical amplitude,it may pull the formation of black hole out of the effective concentration region and make the scalar oscillate one more time in the cavity. It causes a huge time delay in the formation ofblack hole.

Besides the time for the appearance of apparent horizon is influenced by the self-interaction,the critical amplitudes $\epsilon _ { n }$ which give the zero apparent horizon radius are also shifted by $\lambda$ ,though this shift is very small in the first few critical amplitudes.From Figs.(b) and (c) in Fig.1,we see that the second critical amplitude $\epsilon _ { 1 }$ is increased for positive $\lambda$ but decreased for negative $\lambda$ = For a given integer $n \geq 0$ , the critical amplitude $\epsilon _ { n }$ is an increasing function of $\lambda$ in the region our numerical computation can cover.This critical amplitude shift with $\lambda$ is consistent with the behavior of the time shift of black hole formation in the previous paragraph. To explore this，one can suppose that,for a given $\lambda \ : = \ : \lambda _ { 0 }$ ，there is amplitude $\epsilon ^ { \prime }$ which is larger but very close to a critical amplitude $\epsilon _ { i }$ and gives the apparent horizon radius $x _ { H } ( \epsilon ^ { \prime } , \lambda _ { 0 } )$ is very close to zero. Now suppose we alter $\lambda$ a little such as $\lambda = \lambda + \delta \lambda$ with $\delta \lambda > 0$ . Because the larger $\lambda$ will lead the apparent horizon to appear later, the peak of the $\Phi$ and $\mathrm { I I }$ or the bottom of $A$ can propagate into the region closer to the origin before an apparent horizon appears,which leads the apparent horizon radius to be smaller. By adjusting the value of $\delta \lambda$ ，we can make apparent horizon radius decrease to zero and $\epsilon ^ { \prime }$ is a new critical amplitude.We see that by increasing the value of $\lambda$ , the new critical amplitude is larger than the old one.

![](images/27cfc493bba568da6ca930943c429cb1c0e233bd3869e5461a13a87f763f35ef.jpg)  
FIG.1.Formation time of black hole from scalar field with different self-interaction strength $\lambda$ ，we set $\sigma ~ = ~ 1 / 1 6$ .In the top panel,we plot the formation time $t$ with respect to amplitude $\epsilon$ for different $\lambda$ ．The middle and bottom panels show the formation time $t$ when $\epsilon \in [ 3 0 , 3 4 ]$ for different $\lambda$ ， respectively.

# 2. The case with different $\sigma$

In this subsection,we fix $\lambda = - 1 0 0 , 0 , 1 0 0$ ，and consider the width of initial data as $\sigma = 1 / 1 6 , 1 / 8 , 1 / 4$ ，respectively. In order to see the influence of self-interaction on the gravitational collapse,we magnify the region around the first critical amplitude $\left( \epsilon _ { 0 } \right)$ ,while Fig.1 magnifies the region around the second critical amplitude (∈1).The results are shown in Fig. 2.

Qualitatively, the influence of self-interaction with different initial widths is the same.It enhances (when $\lambda < 0$ ）or suppresses(when $\lambda > 0$ )the formation of black hole. Quantitatively, there exist differences. Figs.2(ac）show the black hole formation times for the initial data with widthes $\sigma = { 1 } / { 1 6 } , { 1 } / { 8 } , { 1 } / { 4 }$ ,respectively.When $\sigma = 1 / 1 6$ ,the time difference between the two cases with a nonzero $\lambda$ and vanishing $\lambda$ is very small,less than $0 . 0 0 5 \times \frac { \pi } { 2 }$ .As we increase the width of initial data, the enhancement (or suppressing) effect caused by the same strength of self-interaction becomes obvious.When $\sigma = 1 / 8$ ，the time difference between the two cases with a nonzero $\lambda$ and vanishing $\lambda$ is bigger,and reaches about $0 . 0 1 \times \frac { \pi } { 2 }$ .When $\sigma = 1 / 4$ ，it is more obvious,the time difference is around $0 . 0 5 \times \frac { \pi } { 2 }$ .The time difference is much obvious for the case with a negative $\lambda$

The above observation can be understood as follows. When $\sigma$ is small, the wave packet decays rapidly in space, which means that the self-interaction only happens in a very narrow region and gives very weak influence on the system.In this case,one can expect that the time differences of black hole formation for different $\lambda$ are very small. However,when we increase the value of $\sigma$ ，the region where the self-interaction plays its role is enlarged, so its influence on the system become stronger.In this case,one can expect that the timedifferences for different $\lambda$ become obvious.

![](images/64ad1fa38fff56099b9d78ba203bc1bfa8342fafda5ad8cd8484d7840c6c91eb.jpg)  
FIG.2.Formation time of black hole from scalar field collapse with different initial widthes.Top: $\sigma = 1 / 1 6$ ，Middle: $\sigma =$ $1 / 8$ ，Bottom: $\sigma = 1 / 4$ . We set $\lambda = - 1 0 0 , 0 , 1 0 0$ （204号

# 3.Sensibilities

To characterize the influence of the self-interaction on the critical amplitude and time of black hole formation with respect to the self-interaction strength $\lambda$ under the initial data (12),we define two sensibility coefficients,

$$
\chi _ { \epsilon _ { n } } ( \sigma ) = \operatorname * { l i m } _ { \lambda  0 } ( { \frac { \partial \epsilon _ { n } } { \partial \lambda } } ) _ { \sigma } , \chi _ { t } ( \epsilon , \sigma ) = \operatorname * { l i m } _ { \lambda  0 } ( { \frac { \partial t } { \partial \lambda } } ) _ { \sigma , \epsilon } .
$$

TABLE I.Sensibility of critical amplitude $\epsilon _ { n }$ to $\lambda$ when $\sigma =$ 1/16   

<html><body><table><tr><td>En</td><td>E0</td><td>E1</td><td>€2</td><td>3</td></tr><tr><td>Xen ×103</td><td>0.15</td><td>1.2</td><td>1.0</td><td>0.90</td></tr></table></body></html>

The first one in Eqs.(13) describes the sensibility of critical amplitude and the second one describes the sensibility of forming time of black hole.

In Table.I,we list the first four $\chi _ { \epsilon _ { n } } ( \sigma )$ when $\sigma =$ $1 / 1 6$ . One can see that the values of $\boldsymbol { \chi } _ { \epsilon _ { n } }$ are all positive, which is in agreement with our numerical calculations that a larger $\lambda$ leads to a larger critical amplitude.In addition，we see that the values of $\boldsymbol { \chi } _ { \epsilon _ { n } }$ decrease with $n$ (the exception is the case with $n = 0$ ).This shows the fact that the sensibility of critical amplitude of scalar field to $\lambda$ is decreased with $n$ ：

One of very interesting results by including the $\lambda \phi ^ { 4 }$ from our numerical computations is about $\chi _ { t } ( \epsilon , \sigma )$ .By the definition in (13),we can see that $\chi _ { t } ( \epsilon )$ diverges when （204号 $\epsilon = \epsilon _ { n }$ . Near the critical amplitude $\epsilon  \epsilon _ { n }$ ， we observe a scaling relation as,

![](images/0a32082aa779b174ae37ac86ee53da9bbc56e48ac3ce8ed9f4525e19bd509294.jpg)  
FIG.3.The relation of $\chi _ { t } ( \epsilon , \sigma )$ with respect to $\epsilon$ when $\sigma =$ $1 / 8$ . In the upper plot,we scan $\epsilon$ from 11.25 to 22,and show that there isa pole for every $\epsilon = \epsilon _ { n }$ .In the bottom plot,we show the value of $\chi _ { t } ( \epsilon , \sigma )$ around $\epsilon = \epsilon _ { 1 }$ ．The inset in the bottom plot shows the fitting curves using Eqs.(14).The blue is the case $\epsilon  \epsilon _ { 1 } ^ { + }$ , while the red is the case $\epsilon  \epsilon _ { 1 } ^ { - }$ ：

$$
\chi _ { t } ( \epsilon , \sigma ) \propto \{ \begin{array} { l l } { \displaystyle \frac { 1 } { ( \epsilon _ { n } - \epsilon ) ^ { \alpha } } , } & { \epsilon  \epsilon _ { n } ^ { - } } \\ { \displaystyle \frac { 1 } { ( \epsilon - \epsilon _ { n } ) ^ { \alpha ^ { \prime } } } , } & { \epsilon  \epsilon _ { n } ^ { + } . } \end{array} 
$$

Fig.(3) shows the relation of $\chi _ { t } ( \epsilon , \sigma )$ with respect to $\epsilon$ when $\sigma = 1 / 8$ . In the upper plot,we scan $\epsilon$ from 11.25 to 22.As is expected, $\chi _ { t } ( \epsilon , \sigma )$ is always positive and a pole appears for every $\epsilon = \epsilon _ { n }$ ．In the bottom plot,we show the value of $\chi _ { t } ( \epsilon , \sigma )$ around $\epsilon = \epsilon _ { 1 }$ . By this figure,we can see it clear that when $\epsilon$ is near to its critical value,the system is very sensitive to the self-interaction $\lambda \phi ^ { 4 }$ term. At the critical amplitude,an infinitesimal $\lambda \phi ^ { 4 }$ term can give rise to a very essential difference. This is not very surprising.Because there is a naked singularity at the center of the space when $\epsilon = \epsilon _ { n }$ ，which will lead to the breaking of causality and stability of the spacetime [16]. To find the values of $\alpha$ and $\alpha ^ { \prime }$ in Eqs.(14),we fit the values of $\chi _ { t } ( \epsilon , \sigma )$ when $\epsilon  \epsilon _ { n }$ for different $n$ .We find that $\alpha \simeq \alpha ^ { \prime } \simeq 0 . 7 4 ( 2 )$ ，which are independent on $n$ and $\sigma$ ，up to numerical errors.

![](images/2869c2b9c6ff7b483b1418c32b7efe58a620c9acc183b338c920d3396914e2a4.jpg)  
FIG.4.Formation time of black hole from scalar filed collapse with large width $\sigma = 2 / 5$ .Red: $\lambda = - 1 0$ ，Black: $\lambda = 0$ ，Blue: $\lambda = 1 0$ （20

# B. Effect on stable states

“Stable islands”have been claimed to exist in the free scalar case. We want to see whether the self-interaction plays any role on these“islands”in the initial data.For simplicity,we here consider only the “island” with a large $\sigma$ [5].

We set the width of initial data $\sigma = 2 / 5$ ．The result is shown in Fig.4 for three different self-interaction strengthes: $\lambda = - 1 0 , 0 , 1 0$ ,respectively. We can see that all these three initial data sets show similar behavior for the black hole formation time and that there is a transition from the black hole formation phase to stable phase as $\epsilon$ decreases. We also notice the existence of the “bump”,as in [5],in the black hole formation time before it grows monotonically with the decrease of $\epsilon$ ：

When the self-interaction of the scalar feld is not vanishing,the bump is shifted.When $\lambda = 1 0$ ,the center of the bump is around $\epsilon \simeq 5 . 8 1$ which is larger than the case of $\lambda = 0$ whose bump is centered around $\epsilon \simeq 5 . 7 8$ .We believe that the shift of the bump is a sign of expansion of the size of “stable island”due to positive $\lambda$ .When $\lambda = - 1 0$ ，the situation is opposite. The center of the bump is around 5.75,which indicates the size of“stable island” shrinks due to a negative $\lambda$

The expansion or shrink of the size of “stable island" is an indication of suppressing or enhancing the instability of the system. So the self-interaction has the same effect on stable states as on unstable states: positive $\lambda$ suppresses the instability of the system,while negative $\lambda$ enhances it.

# C. Effect on the energy transfer

For small amplitude $\epsilon$ , the system can evolute a very long time before a trapped surface forms which indicts the appearance of apparent horizon. To see further the influence of $\lambda \phi ^ { 4 }$ on the instability of AdS space, in this section, following Ref.[1],we investigate the energy transfer between different modes.

In the case with small amplitude $\epsilon$ ,we can expand the functions $\{ \phi , A , \delta \}$ as,

$$
\phi = \sum _ { j = 0 } ^ { \infty } \phi _ { 2 j + 1 } \epsilon ^ { 2 j + 1 } , \ A = 1 - \sum _ { j = 1 } ^ { \infty } A _ { 2 j } \epsilon ^ { 2 j } , \ \delta = \sum _ { j = 1 } ^ { \infty } \delta _ { 2 j } \epsilon ^ { 2 j } .
$$

Then at the linear order of $\epsilon$ , the solutions of Eqs. (5)-(9) are $A = 1 , \delta = 0$ and $\phi$ can be expressed by hypergeometric function such as [1],

$$
\phi _ { j } = a _ { j } \cos ( \omega _ { j } t + \beta _ { j } ) e _ { j } ( x )
$$

with some constants $a _ { j } , \beta _ { j }$ and

$$
e _ { j } ( x ) = d _ { j } \cos ^ { 3 } x _ { \ 2 } F _ { 1 } ( - j , 3 + j , \frac { 3 } { 2 } ; \sin ^ { 2 } x ) .
$$

Here $\omega _ { j } = \pm ( 3 + 2 j )$ and $d _ { j } = \sqrt { 1 6 ( j + 1 ) ( j + 2 ) / \pi }$ with （204 $j = 0 , 1 , 2 , \cdots$

Using the linear order solutions (16),we can project a general solution $\{ \Phi , \Pi \}$ (not only in the linear order of $\epsilon$ ） as,

$$
\Phi _ { j } = \langle \sqrt { A } \Phi , e _ { j } ^ { \prime } \rangle , \Pi _ { j } = \langle \sqrt { A } \Pi , e _ { j } \rangle
$$

Here the inner product is defined as $\begin{array} { r l } { \langle f , g \rangle } & { { } = } \end{array}$ $\begin{array} { r } { \int _ { 0 } ^ { \pi / 2 } f ( x ) g ( x ) \tan ^ { 2 } x d x } \end{array}$ . Then the energy of $j$ -mode can be expressed as,

$$
E _ { j } = \Pi _ { j } ^ { 2 } + \omega _ { j } ^ { - 2 } \Phi _ { j } ^ { 2 } .
$$

To investigate the influence of $\lambda \phi ^ { 4 }$ term on the energy transfer,we use the two modes initial data as in Ref.[1], i.e., $\phi ( 0 , x ) = \epsilon [ e _ { 0 } ( x ) / d _ { 0 } + e _ { 1 } ( x ) / d _ { 1 } ]$ and define,

$$
\Delta _ { k } ( \lambda _ { 0 } ) = ( \sum _ { i = 0 } ^ { k } E _ { i } ) | _ { \lambda = \lambda _ { 0 } } - ( \sum _ { i = 0 } ^ { k } E _ { i } ) | _ { \lambda = 0 } .
$$

For a given $\lambda _ { 0 }$ ， $\Delta _ { k } ( \lambda _ { 0 } )$ describes the difference of the energy staying in the first $k$ models between the cases with $\lambda _ { 0 } ~ \neq ~ 0$ and with $\lambda \ : = \ : 0$ . Thus if it is negative, it means that the $\lambda \phi ^ { 4 }$ term can accelerate the energy transfer into high energy modes,and vice versa.

In Fig. 5,we plot $\Delta _ { k } ( \lambda _ { 0 } )$ when $\epsilon = 0 . 0 8 8$ for different $\lambda _ { 0 }$ and show the result for $\lambda = - 1 0 0 , - 1 0 , 1 0$ and 100,respectively. It can be clearly seen that $\Delta ( \lambda _ { 0 } )$ is positive when $\lambda > 0$ ，which means that a positive $\lambda$ can enhance the stability and make the energy stay in low energy modes much long.We can expect the in this case it will lead the black hole to form later than the case of $\lambda = 0$ ，which is consistent with our numerical computation in the case with large amplitudes.

![](images/0b9f7d553ef2ddbaec6f9adc45bde2b3ef9e3047191888520f26c6942d2e715d.jpg)  
FIG.5.The value of $\Delta _ { k }$ for different $\lambda$ with large width $\sigma = 2 / 5$ .Herewe take $k = 2$ ：

# IV.CONCLUSION

We have studied the gravitational collapse of massless scalar field with a self-interaction $\lambda \phi ^ { 4 }$ in AdS space, paying attention on the influence of the self-interaction on the instability of AdS space.This self-interaction leads to an enhancing ( $\lambda < 0$ ）or suppressing ( $\lambda > 0$ ）effect on the formation of black hole.We have seen that near the critical amplitude $\epsilon$ , this self-interaction may cause a large time difference of black hole formation between free scalar field case and self-interacting scalar field case (oscillating one more or one less in the cavity).We have defined two susceptibilities to characterize the effect of the self-interaction,one is the amplitude with respect to the self-interaction strength $\lambda$ ,the other is the formation time of black hole. We have found a universal scaling relation for the formation time of black hole near the criticalamplitude,whichisfoundindependentof $n$ and $\sigma$ ； the critical exponent $\alpha \approx 0 . 7 4$ .We have also investigated the effect of $\lambda \phi ^ { 4 }$ on the energy transfer. The results show that a positive $\lambda$ will delay energy transfer into high energy modes,while a negative $\lambda$ can accelerate this transfer.In addition,we have studied the effect of the self-interaction on the “stable island” in the initial data with a large $\sigma$ ,and found that a positive (negative) $\lambda$ expands(shrinks)the size of the“ stable island”and leads to a shift of the critical amplitude.

# ACKNOWLEDGMENTS

This work was supported in part by the National Natural Science Foundation of China (No.11375247 and No.11435006 ).

[1]P.Bizon and A. Rostworowski, Phys. Rev. Lett.107, 031102 (2011), arXiv:1104.3702 [gr-qc].   
[2] M.Maliborski and A. Rostworowski,Proceedings, Spring School on Numerical Relativity and High Energy Physics (NR/HEP2), Int. J. Mod. Phys.A28，1340020 (2013), arXiv:1308.1235 [gr-qc].   
[3] A.Buchel,L.Lehner， and S.L.Liebling,Phys.Rev. D86,123011 (2012), arXiv:1210.0890 [gr-qc].   
[4]O.J.C.Dias,G.T.Horowitz，and J.E.Santos,Class. Quant.Grav.29,194002 (2012)，arXiv:1109.1825 [hepth].   
[5] A.Buchel，S.L.Liebling， and L.Lehner,Phys.Rev. D87,123006 (2013), arXiv:1304.4166 [gr-qc].   
[6] M.Maliborski and A.Rostworowski,Phys.Rev.Lett. 111, 051102 (2013), arXiv:1303.3186 [gr-qc].   
[7] N. Kim, Phys. Lett. B742, 274 (2015), arXiv:1411.1633 [hep-th].   
[8] H.Okawa，J.C.Lopes, and V. Cardoso， (2015), arXiv:1504.05203 [gr-qc].   
[9] N. Deppe and A. R. Frey, (2015),arXiv:1508.02709 [hepth].   
[10]V.Balasubramanian,A.Buchel,S.R.Green,L.Lehner, and S.L. Liebling, Phys. Rev.Lett.113,071601 (2014), arXiv:1403.6471 [hep-th].   
[11]B.Craps，O.Evnin，and J.Vanhoof,JHEP 10，48 (2014), arXiv:1407.6273 [gr-qc].   
[12]B.Craps，O.Evnin， and J.Vanhoof,JHEP O1，108 (2015), arXiv:1412.3249 [gr-qc].   
[13]N.Deppe,A.Kolly，A.Frey，and G.Kunstatter,Phys. Rev. Lett. 114, 071102 (2015), arXiv:1410.1869 [hep-th].   
[14] H. Okawa, V.Cardoso， and P. Pani,Phys. Rev.D89, 041502 (2014), arXiv:1311.1235 [gr-qc].   
[15]P.Basu，C.Krishnan， and A.Saurabh,Int.J.Mod. Phys. A30, 1550128 (2015), arXiv:1408.0624 [hep-th].   
[16] D. Christodoulou, Annals of Mathematics Second Series, 149,183 (1999).