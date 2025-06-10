# Irreversible Markov chain Monte Carlo algorithm for the self-avoiding walk

Hao Hu, $^ { 1 , 2 }$ Xiaosong Chen,² and Youjin Deng1,2,a)   
$^ { 1 ) }$ National Laboratory for Physical Sciences at Microscale and Department of Modern Physics,   
University of Science and Technology of China, Hefei,Anhui 230026,China   
$^ { 2 ) }$ State Key Laboratory of Theoretical Physics, Institute of Theoretical Physics， Chinese Academy of Sciences,   
Beijing 100190,China

(Dated:5 February 2016)

We design an irreversible Markov chain Monte Carlo algorithm for the self-avoiding walk (SAW).It outperforms the Berretti-Sokal algorithm. The gained eficiency increases with the spatial dimension,from about 10 times in two dimensions to around 40 times in five dimensions.The algorithm violates the widely used detailed balance condition and satisfes the weaker balance condition.We employ the irreversible method to study the finite-size scaling of SAW above the upper critical dimension.

Keywords: Monte Carlo algorithms, self-avoiding walk, irreversible,balance condition

# . INTRODUCTION

The self-avoiding walk (SAW) serves as an important model in polymer physics (see e.g. Ref.[1] and references therein).In the grand-canonical ensemble,the walks can have different lengths and the model is defined by the partition sum

$$
{ \mathcal Z } = \sum _ { \omega } x ^ { | \omega | } ,
$$

where the summation is over all possible self-avoiding paths,with $| \omega |$ being the length of a walk $\omega$ .It is equivalent to the $n  0$ limit of the $O ( n )$ model²．Markov chain Monte Carlo (MCMC） methods have been extensively used in the simulation of SAW3.

There are two key ingredients for designing a MCMC algorithm. One is the balance condition(BC)which tells that the probability flow entering into a configuration equals the flow out of the configuration,thus it is guaranteed that the chain converges to a stationary distribution. And the other one is the ergodicity which requires that all configuration states can be reached from a random initial configuration.In practice, the BC is usually satisfied by employing the detailed balance condition (DBC),which means that the probability fow from a configuration to another one equals the reverse flow,i.e.the dynamics is reversible. The DBC is sufficient but not necessary.

Recently there appear several successful studies $^ { 4 - 1 4 }$ which show promising future for MCMC algorithms be yond the DBC: geometric allocation approaches have been applied to the Potts modell2.13；i irreversible MCMC methods have been designed for the meanfield Ising model $^ { 4 , 5 }$ ; event-chain Monte Carlo (ECMC) methods have been proposed for simulation of hardsphere systems $^ { 6 , 7 }$ and generalized to particle systems with arbitrary pairwise interactions8,including the softdisk systems， the XY model $^ { 1 0 }$ and the Heisenberg modeli1. The geometric allocation method outperforms the Metropolis-Hasting (MH) method by 6.4 times for the $q = 4$ square lattice Potts model,and is increasingly advantaged as $q$ increases12.For the mean-field Ising model, the irreversible MCMC methods havea dynamic exponent $z \simeq 0 . 8 5$ ,which is much smaller than $z \simeq 1 . 4 3$ for the reversible MH method $^ { 4 , 5 }$ . Comparing with the MH method, the speedup of the ECMC method reaches two orders of magnitude in large systems consisting of $1 0 ^ { 6 }$ hard spheres7. And for the three-dimensional ferromagnetic Heisenberg model, it has been reported that the ECMC method has a dynamic exponent $z \simeq 1$ ，in contrast to z \~ 2 for the MH methodli.

While local probability flow circles are introduced in the geometric allocation approach,much larger or even global circles appears in other methods mentioned above. This is achieved by making use of the lifting technique. This technique makes replications of the system.In each replica, the probability flow goes either in a chosen direction or to another replica.There exists net probability flow in each replica,and between different replicas,but the combined flow is balanced,i.e.the BC is satisfied. For example,in simulating the mean-field Ising model4, two replicas are used.In one replica,only the positive spins are proposed to flip (the total magnetization $M$ always decreases), and only the negative spins are proposed to flip in the other replica（ $M$ always increases). If the spin-flip update is rejected,switching of replica will be proposed. Updates in one replica can persist very far until a spin-flip proposal is rejected,after which the replica changes and updates can persist in the other replica until another spin-flip is rejected. Thus large circles are introduced in the probability flow.In this way, the diffusive feature in phase space is suppressed or even replaced byballistic-like behavior.And due to this fact,for the mean-field Ising model, comparing with the MH method, the dynamics of the lifted Markov chain method is qualitatively faster,i.e. the dynamic exponent is $z ~ \simeq ~ 0 . 8 5$ instead of $z \simeq 1 . 4 3$ for the MH method $^ { 4 , 5 }$ . However,it is found that the lifting trick does not help much for the Ising model in low dimensions5,14.

In this work,we design an efficient MCMC algorithm without DBC for SAW by employing the lifting technique with two replicas. The change of the SAW path is different in the two replicas: it cannot increase its length in one replica and cannot decrease its length in the other.And switching of replicas is allowed to enable formation of probability flow circles.This new algorithm isirreversible since it violates the DBC.Numerical results show that the irreversible MCMC method is far superior to the Berretti-Sokal (BS) algorithm17.We use this new method to explore the finite-size scaling (FSS) of SAW above the upper critical dimension.

The remaining part of this article is organized as follows.In Sec.I,we recall traditional Monte Carlo methods for SAW,including the MH algorithm and the BS algorithm.These algorithms preserve reversibility as indicated by the DBC.Section III describes in detail our irreversible MCMC algorithm for SAW.We compare the performance of the above algorithms in Sec.IV.Section V contains a FSS analysis for SAW on a periodic hypercubic lattice in five dimensions,which is above the upper critical dimension $d _ { c } = 4$ ．A brief conclusion and discussion is presented in Sec.VI.

# I=. REVERSIBLEMCMCALGORITHMS

We introduce below the MH and BS algorithms for SAW.These two algorithms employ the DBC, thus their dynamics are reversible.

# A.Metropolis-Hasting algorithm

Let $\mathcal { L }$ be a regular $d$ -dimensional lattice with coordination number $z$ .Then an $\mathcal { N }$ -step SAW $\omega$ on $\mathcal { L }$ （ $\mathcal { N } \equiv$ $| \omega |$ ） is a sequence of distinct sites $\omega ( 0 )$ ， $\omega ( 1 )$ ， $\dots , \omega ( \mathcal { N } )$ in $\mathcal { L }$ such that each site is a nearest neighbor of its predecessor. We assume that all walks have an open end fixed at the origin,i.e. $\omega ( 0 ) = 0$ ，and the other open end denoted by $I$ . The MH algorithm $^ { 1 5 , 1 6 }$ is a standard reversible MCMC algorithm,which is constructed as below.

MH Algorithm.   
(1) Randomly choose one of the $z$ neighboring sites of $I$ ， say $I ^ { \prime }$ ，and propose a symmetric update to for the edge connecting $I$ and $I ^ { \prime }$ , i.e.propose moving the open end $I$ to $I ^ { \prime }$ ·   
(2）Accept the proposalwith probability （204号 $\operatorname* { m i n } \{ 1 , \pi ( \omega ^ { \prime } ) / \pi ( \omega ) \}$ ，where $\omega ^ { \prime }$ ， $\omega$ representthe two walks with open end $I ^ { \prime }$ and $I$ ，respectively, and $\pi ( \omega )$ gives the weight of a configuration $\omega$ ：

Here the weight $\pi$ is given by

$$
\pi ( \omega ) = \frac { x ^ { | \omega | } } { \mathcal { Z } } \chi ( \omega ) \ ,
$$

where

$$
\chi ( \omega ) = \left\{ \begin{array} { l l } { { 1 } } & { { \mathrm { i f } \ \omega \ \mathrm { i s \ a n \ S A W } } } \\ { { 0 } } & { { \mathrm { i f } \ \omega \ \mathrm { i s \ n o t \ a n \ S A W } . } } \end{array} \right.
$$

The acceptance probabilities are given by

$$
P ( \Delta \mathcal { N } = + 1 ) = \operatorname* { m i n } \{ 1 , x \} \chi ( \omega ^ { \prime } )
$$

and

$$
P ( \Delta \mathcal { N } = - 1 ) = \operatorname* { m i n } \{ 1 , 1 / x \} ,
$$

where $\Delta \mathcal { N } = | \omega ^ { \prime } | - | \omega |$ . The a priori probability $A ( \omega $ $\omega ^ { \prime }$ ）describes the probability of proposing a transition from configuration $\omega$ to $\omega ^ { \prime }$ . Here we have $A ( \omega  \omega ^ { \prime } ) =$ $1 / z$ for both $\Delta \mathcal { N } = + 1$ and $\Delta \mathcal { N } = - 1$ . It can be verified that the DBC is satisfied

$$
\phi ( \omega  \omega ^ { \prime } ) = \phi ( \omega ^ { \prime }  \omega )
$$

where $\phi ( \omega  \omega ^ { \prime } ) = \pi ( \omega ) A ( \omega  \omega ^ { \prime } ) P ( \omega  \omega ^ { \prime } )$ is the local probability flow.

# B．Berretti-Sokal algorithm

An efficient MCMCalgorithm for the SAWis the BS method17. The BS algorithm uses a priori probabilities different from the MH method.

# BS Algorithm.

(1）Propose randomly to increase the walk length ( $\Delta \mathcal { N } = + 1$ ）or to decrease it ( $\Delta \mathcal { N } = - 1$ )，with equal probability.   
(2a) When $\Delta \mathcal { N } = + 1$ is proposed, one randomly selects a neighboring site of $I$ ，say $I ^ { \prime }$ .If the proposed move leads to self-intersection，it is rejected and the old configuration is counted again in sampling (a “null transition").Otherwise,with probability $P _ { \mathrm { B S } } ( \Delta \mathcal { N } = + 1 )$ L， accept the proposal and move the open end from $I$ to $I ^ { \prime }$ ： (2b)When $\Delta \mathcal { N } ~ = ~ - 1$ is proposed,if the proposal is made to delete a bond from an already-empty walk, it is rejected and a “null transition” presents. Otherwise, with probability $P _ { \mathrm { B S } } ( \Delta \mathcal { N } = - 1 )$ ，accept the proposal, delete the last bond and move the open end from $I$ to its predecessor $I ^ { \prime }$ ：

The predecessor of site $I$ is excluded from choice in (2a), thus each $I ^ { \prime }$ is selected with probability $1 / ( z - 1 )$ .The a priori probabilities are $A ( \omega  \omega ^ { \prime } ) = 1 / 2 ( z - 1 )$ for $\Delta \mathcal { N } = + 1$ ，and $A ( \omega  \omega ^ { \prime } ) = 1 / 2$ for $\Delta \mathcal { N } = - 1$ .The acceptance probabilities are chosen as

$$
P _ { \mathrm { B S } } ( \Delta \mathcal { N } = + 1 ) = \operatorname* { m i n } \{ 1 , x ( z - 1 ) \}
$$

and

$$
P _ { \mathrm { B S } } ( \Delta \mathcal { N } = - 1 ) = \operatorname* { m i n } \{ 1 , 1 / x ( z - 1 ) \} .
$$

It can be verified that the above $A$ and $P _ { \mathrm { B S } }$ also satisfy the DBC given in Eq.(6).

We note that when $\mathcal { N } = 0$ ，there are $z$ candidates for $I ^ { \prime }$ ,instead of $z - 1$ .A convenient treatment is to set for $\mathcal { N } = 0$ one of the $z$ neighbors not available. It is also noted that there is a slight difference between the BS algorithm described above and the original BS algorithm. In the original algorithm $^ { 1 7 }$ ,a priori probabilities are chosen such that acceptance probabilities always equal one if the proposed step does not lead to self intersection or does not delete a bond from an already-empty walk. However, since we focus on properties near the critical point $x _ { c }$ ，which has its value very close to $1 / ( z - 1 )$ ，this does not lead to significant difference in the efficiency.

# I三I. IRREVERSIBLEMCMCMETHOD

The BS algorithm in the previous section clearly decompose the proposed steps into those with $\Delta \mathcal { N } = + 1$ and others with $\Delta \mathcal { N } = - 1$ . To get an irreversible algorithm，a direct idea is to use two replicas,labeled with $( + )$ and $( - )$ ,and only propose to increase the walk length in the $( + )$ replica,and to decrease the walk length in the $( - )$ replica. The DBC is violated since in each replica the probability flow only goes in one direction. To ensure convergence to the equilibrium distribution,we use the BC instead,which is achieved by allowing transitions between the two replicas.Figure 1 shows the probability flow. The irreversible algorithm goes as follows.

# Irreversible Algorithm.

To observe the probability flow,we count the flow into and out of a configuration in the $( + )$ replica with length （204号 $\mathcal { N }$ . The input flow from a $\mathcal { N } - 1$ configuration is

$$
\phi _ { \mathrm { i n } } ^ { + } ( \mathcal N - 1  \mathcal N ) = x ^ { \mathcal N - 1 } \frac 1 { z - 1 } P ^ { + } .
$$

There also exists an input flow from the $\mathcal { N }$ -step walk in the $( - )$ replica

$$
\phi _ { \mathrm { i n } } ^ { + } ( { \mathcal N } ^ { - }  { \mathcal N } ^ { + } ) = x ^ { \mathcal N } ( 1 - P ^ { - } ) .
$$

The outgoing flow decomposes into two parts, one part is that leads to SAWs with length $\mathcal { N } + 1$

$$
\phi _ { \mathrm { o u t } } ^ { + } ( { \cal N }  { \cal N } + 1 ) = x ^ { { \cal N } } \frac { z ^ { \prime } } { z - 1 } { \cal P } ^ { + } ,
$$

![](images/78b6d1c0871fb41ce252ffa532abd6c94ae856dff97ce17e5dbfebcd9f6fc643.jpg)  
FIG.1.Probability flow of the irreversible Monte Carlo algorithm forSAW.

where $z ^ { \prime }$ ( $0 \leq z ^ { \prime } \leq z - 1$ )is the number of valid $( \mathcal { N } + 1 )$ step SAWs that can be obtained from the present $\mathcal { N }$ -step SAW. The other part is that leads to the corresponding $\mathcal { N }$ -step walk in the $( - )$ replica,due to rejection of the proposed $\Delta \mathcal { N } = + 1$ walk in the $( + )$ replica,

$$
\begin{array} { l } { \displaystyle \phi _ { \mathrm { o u t } } ^ { + } ( N ^ { + } \to \mathcal { N } ^ { - } ) } \\ { = \displaystyle x ^ { N } \frac { z ^ { \prime } } { z - 1 } ( 1 - P ^ { + } ) + x ^ { N } \frac { z - 1 - z ^ { \prime } } { z - 1 } . } \end{array}
$$

where $\mathcal { N } ^ { - }$ and $\mathcal { N } ^ { + }$ denote the $\mathcal { N }$ -step walk in the $( - )$ and $( + )$ replica,respectively.

The BC condition implies that

$$
\begin{array} { r l } & { \phi _ { \mathrm { i n } } ^ { + } ( \mathcal { N } - 1 \to \mathcal { N } ) + \phi _ { \mathrm { i n } } ^ { + } ( \mathcal { N } ^ { - } \to \mathcal { N } ^ { + } ) } \\ & { = \phi _ { \mathrm { o u t } } ^ { + } ( \mathcal { N } \to \mathcal { N } + 1 ) + \phi _ { \mathrm { o u t } } ^ { + } ( \mathcal { N } ^ { + } \to \mathcal { N } ^ { - } ) . } \end{array}
$$

The above equation is satisfed if we choose $P ^ { + } =$ $P _ { \mathrm { B S } } ( \Delta \mathcal { N } \ = \ + 1 ) = \ \operatorname* { m i n } \{ 1 , x ( z \ - \ 1 ) \}$ and $\begin{array} { r l } { P ^ { - } } & { { } = } \end{array}$ $P _ { \mathrm { B S } } ( \Delta \mathcal { N } = - 1 ) = \mathrm { m i n } \{ 1 , 1 / x ( z - 1 ) \}$ Similarly，one can verify that the BC is satisfied for a $\mathcal { N }$ -stepwalk in the $( - )$ replica.The above irreversible algorithm is easy to implement — only small changes to the BS code are needed, due to the similarity in their descriptions.

We note that this irreversible algorithm satisfies the skew DBO $^ { 4 , 1 8 }$ ，which requires that the probability flow from a configuration to another in one replica equals the reverse flow in the other replica, i.e. $\phi ^ { + } ( \mathcal { N }  \mathcal { N } + 1 ) =$ $\phi ^ { - } ( \mathcal { N } + 1  \mathcal { N } )$ ：

# IV.PERFORMANCE

We compare the efficiency of thealgorithms by observing the integrated autocorrelation time $\tau$ ,which is defined 19 by

$$
\delta \mathcal { O } = \sqrt { \frac { 1 + 2 \tau / \Delta t } { n - 1 } ( \overline { { \mathcal { O } ^ { 2 } } } - \overline { \mathcal { O } } ^ { 2 } ) } ~ .
$$

Here $\delta \mathcal { O }$ represents the statistical error for an arbitrary observable $\boldsymbol { \mathcal { O } }$ ， $\Delta t$ is the time interval at which the samples are taken，and $n = t _ { m a x } / \Delta t$ is the total number of samples,where $t _ { m a x }$ is maximum measure time.The quantity $\tau$ indicates how many Monte Carlo steps are needed to generate an effectively independent sample.

TABLE I.Value of critical point $x _ { c }$ in different spatial dimensions $d$ ：

![](images/3b42f353f7137911bcfc65ecb477e566933107b2ce2fc916e78aa8b931aade7f.jpg)  
FIG.2.Autocorrelation time of the Metropolis-Hasting (MH) algorithm $\tau _ { \mathrm { M H } }$ divided by that of the Berretti-Sokal (BS) or irreversible(IR）algorithm，versus the linear system size $L$ The autocorrelation time is calculated from observing the average walk length $N = \langle \mathcal { N } \rangle$ ，at the critical point $x _ { c }$ ,for two to five dimensions.For each linear size $L$ ，weran 20 independent jobs.In each job, $5 0 \times 1 0 2 4 \times L ^ { d } / 2 ^ { d }$ steps were thrown for thermalization,and another $2 0 0 \times 1 0 2 4 \times L ^ { d } / 2 ^ { d }$ steps were accounted for sampling.

We conducted simulations at the critical point $x _ { c }$ (see Table I for their values; simulations for $d = 5$ were conducted at $x _ { c } = 0 . 1 1 3 1 4 0 8 5 .$ ）for the square,cubic and $d$ -dimensional hypercubic lattice with the spatial dimension $d = 4 , 5$ ，using periodic boundary conditions.

Figure 2 compares the autocorrelation time $\tau$ for different algorithms,calculated from observing the average walk length $N = \langle \mathcal { N } \rangle$ .It can be seen that the performance of the irreversible algorithm is far superior to the BS and the MH algorithms. The efficiency of the irreversible algorithm increases as the spatial dimension $d$ becomes larger.For $d = 2$ ,it outperforms the MH algorithms about 12 times,and outperforms the BS algo rithm about 8 times.And for $d = 5$ ,it outperforms the MH algorithms over 2OO times,and outperforms the BS algorithm around 40 times.

We also compare the efficiency of different algorithms in units of CPU time using the same machine (a desktop computer with 3.8 GiB memory and four Intel i5 cores). The CPU time consumed in $\tau$ sweeps with $x = x _ { c }$ are shown in Table II for different algorithms. The results are similar to those from the comparison of the autocorrelationtime.

TABLE II. CPU time (in units of seconds) needed in $^ { \prime \prime }$ sweeps for different algorithms at $x = x _ { c }$ ,measured in $d$ -dimensional systems with linear size $L$ .For convenience, the ratio of CPU time $\scriptstyle t _ { \mathrm { B S } } / t _ { \mathrm { I R } }$ is calculated,as well as the ratio of autocorrelation time $\tau _ { \mathrm { B S } } / \tau _ { \mathrm { I R } }$ ：   

<html><body><table><tr><td>dL</td><td>tIR</td><td>tBs</td><td>tMH</td><td>tBS /tIR TBS/TIR</td></tr><tr><td></td><td>2 1024 0.130(11)</td><td>2.0(3)</td><td>3.3(3)</td><td>15(2) 8(2)</td></tr><tr><td>3128</td><td>0.014 8(7)</td><td>0.264(11)</td><td>0.81(14)</td><td>18(2) 13.2(11)</td></tr><tr><td>464</td><td>0.043(2)</td><td>0.73(3)</td><td>2.5(3)</td><td>17(2) 24(2)</td></tr><tr><td>532</td><td>0.035(2)</td><td>1.21(12)</td><td>4.3(9)</td><td>35(6) 43(6)</td></tr></table></body></html>

![](images/533bb9582f3756457c85abd56bc6c26d9652c15d0bd272ecfabf5915624f6c84.jpg)  
FIG.3.Autocorrelation time of the Metropolis-Hasting (MH) algorithm $\tau _ { \mathrm { M H } }$ divided by that of the Berretti-Sokal (BS） or irreversible (IR）algorithm，versus the linear systems size $L$ The autocorrelation time is calculated from observing the returning probability $D _ { 0 } = \left. \mathcal { D } _ { 0 } \right.$ ，at the critical point $x _ { c }$ ，for two to five dimensions.

From Eq.(14),different observablesmay lead to different estimations of the autocorrelation time $\tau$ . The results above are obtained from observing the walk length.In order to account for this difference,we measure another quantity, i.e. the returning probability $D _ { 0 } = \left. \mathcal { D } _ { 0 } \right.$ which is defined as the probability that the walk returns to its start point (thus having zero walk length). The results are shown in Fig.3.It can be seen that the improvement of efficiency is similar to those obtained from observing the walk length.

# V.FINITE-SIZE SCALING ABOVETHE UPPER CRITICALDIMENSION

While the FSS of SAW is usually presented in terms of the walk length or the end-to-end distance,here we analyze the dependence of observables on the linear size of the lattice $L$ . An example on this kind of FSS has been presented for three-dimensional SAW in Ref.23,where it isshown that dimensionless ratios nicely intersect at the critical point $x _ { c }$ .Here we use the irreversible method to investigate the FSS above the upper critical dimension $d _ { c } = 4$ . For the Ising model with periodic boundary conditions, Binder et al.24 predicts that above the upper critical dimension, the thermal and magnetic scaling exponent are $y _ { t } = d / 2$ and $y _ { h } = 3 d / 4$ respectively. We demonstrate below that the same exponents also apply to SAW.

![](images/0095483dc18fc147e44c507309344d905a96fd3241fac1fd36047353cc2097de.jpg)  
FIG.4.Finite-size scaling near the critical point $\begin{array} { r l } { x _ { c } } & { { } = } \end{array}$ 0.113 140 84. The left panel shows the rescaled average walk length $N / L ^ { 5 / 2 }$ versus $x$ (top),and the specific heat $C$ versus $x$ (bottom).The right panel shows the same quantities using a rescaled horizontal coordinate $( x - x _ { c } ) L ^ { 5 / 2 }$ , data points at different $( x , L )$ collapse well into a single scaling function as $L$ becomes large.

Using the irreversible method,extensive simulations were done for SAW in five dimensional hypercubic lattice with periodic boundary conditions. The average walk length $N$ is an energy-like quantity,which scales as

$$
N = L ^ { y _ { t } } ( a _ { 0 } + \sum _ { k = 1 } ^ { 2 } a _ { k } \epsilon ^ { k } L ^ { k y _ { t } } + b _ { 1 } L ^ { y _ { 1 } } ) \ ,
$$

where $\epsilon = x - x _ { c }$ and $y _ { 1 }$ is the leading correction exponent, $a _ { 0 } , \ a _ { 1 }$ ， $a _ { 2 }$ ， $b _ { 1 }$ are non-universal constants.We also sampled the specific-heat $C = L ^ { - d } \left( \langle \mathcal { N } ^ { 2 } \rangle - \langle \mathcal { N } \rangle ^ { 2 } \right)$ which behaves as following

$$
C = L ^ { 2 y _ { t } - d } ( a _ { 0 } + \sum _ { k = 1 } ^ { 2 } a _ { k } \epsilon ^ { k } L ^ { k y _ { t } } + b _ { 1 } L ^ { y _ { 1 } } ) \ .
$$

The MC data were fitted to Eqs.(15) and (16),with different values of $y _ { 1 }$ ， leading to $x _ { c } = 0 . 1 1 3$ 140 84(1） and values of $y _ { t }$ consistent with $5 / 2$ . The value of $x _ { c }$ agrees with the best previous estimates $x _ { c } = 0 . 1 1 3 1 4 0 8 1 ( 4 ) ^ { 2 2 }$ Figure 4 shows that the data collapse well onto a single scaling function when plotted in rescaled coordinates.

We also measured the returning probability $D _ { 0 }$ at the critical point, which is expected to scale as25

$$
D _ { 0 } = L ^ { d - 2 y _ { h } } ( a _ { 0 } + b _ { 1 } L ^ { y _ { 1 } } + . . . ) ,
$$

![](images/31e9539f0ad19be65f4d96b9c4052f5e8bafe1f2f24562d6a1de72cc04ea248f.jpg)  
FIG.5.Plot of ${ \cal D } _ { 0 } { \cal L } ^ { 2 y _ { h } - d }$ vs $L$ at the critical point $x _ { c } = { }$ 0.113 140 85,with $y _ { h } = 3 d / 4$ ， $d = 5$ ：

where $y _ { h } = 3 d / 4 = 1 5 / 4$ ，and higher-order correction terms are omitted.The above scaling behavior is demonstrated in Fig.5,where $D _ { 0 } L ^ { 2 y _ { h } - d }$ is plotted versus $L$ ： The fact that $D _ { 0 } L ^ { 2 y _ { h } - d }$ Converges to a nonzero value as system size increases indicates that the leading scaling behavior of $D _ { 0 }$ is indeed $\sim L ^ { d - 2 y _ { h } }$ ，

Theirreversible method can also be used to simulate SAW on lattices with free boundary conditions.Above the upper critical dimension,the above values $y _ { t } = d / 2$ and $y _ { h } = 3 d / 4$ account for effects of the dangerous irrelevant field $^ { 2 4 }$ , otherwise the exponents should be $y _ { t } ^ { \prime } = 2$ and $y _ { h } ^ { \prime } = d / 2 + 1$ .The latter values have been observed for SAW on five-dimensional hypercubic lattices with free boundary conditions26.

# VI. CONCLUSION AND DISCUSSION

We construct an irreversible Monte Carlo algorithm for SAW.It violates the DBC,and satisfies the weaker BC.Comparing with the MH and BS algorithms,both being reversible,the irreversible method is much more efficient.While the BS algorithm is about $d$ times more efficient than the MH algorithm,the irreversible algorithm is much more superior to the BS algorithm. Comparing the irreversible method with the BS method,the gain of effciency increases with the spatial dimension: from around 10 times in 2D to around 40 times in 5D.

The irreversible algorithm introduces an auxiliary variable to enlarge the configuration space,and as a return,this gives one some freedom in designing MCMC. More specifically, the irreversible algorithm makes use of two replicas. While the BS algorithm proposes either the $\Delta \mathcal { N } = + 1$ move or the $\Delta \mathcal { N } = - 1$ move with a nonzero probability， the irreversible algorithm proposes only $\Delta \mathcal { N } = + 1$ move in one replica,and only the $\Delta \mathcal { N } = - 1$ move in the other replica. The probability flow in each replica is irreversible.In order to satisfy the BC,switching of replica is employed when a proposed $\Delta \mathcal { N } = + 1$ or $\mathbf { \Sigma } - \mathbf { \Sigma } ]$ move is rejected.The implementation of the irreversible algorithm only needs small modifications to the BS code.It is expected that the irreversible MCMC method may be useful in studies of interacting SAW $^ 3$ , other polymeric systems and soft matter.

# ACKNOWLEDGMENTS

This work is supported by the National Natural Science Foundation of China under Grant No.11275185,and by the Open Project Program of State Key Laboratory of Theoretical Physics, Institute of Theoretical Physics, Chinese Academy of Sciences, China (No.Y5KF191CJ1). Y.Deng acknowledges the Ministry of Education (China) for the Fundamental Research Funds for the Central Universities under Grant No.2340000034.

1P. G.de Gennes, Scaling Concepts in Polymer Physics (Cornell University, Ithaca,1979).   
2P.G. de Gennes, Exponents for the excluded volume problem as derived by the Wilson method,Phys.Lett.A38,339 (1972). 3E.J.Janse van Rensburg，Monte Carlo methods for the selfavoiding walk,J.Phys.A:Math.Theor.42,323001 (2009). $^ 4$ K. S. Turitsyn, M. Chertkov, and M. Vucelja, Irreversible Monte Carlo algorithms for effcient sampling，Physica D 240，410 (2011).   
5H.C.M. Fernandes,M. Weigel， Non-reversible Monte Carlo simulationsof spin models,ComputerPhysics Communications 182,1856 (2011).   
6E.Bernard,W.Krauth,D.Wilson, Event-chain Monte Carlo algorithms for hard-sphere systems,Phys.Rev.E 80,056704 (2009).   
$^ 7$ M.Engel,J.A.Anderson,S.C.Glotzer,M.Isobe,E.P.Bernard, W.Krauth,Hard-disk equation of state: First-order liquidhexatic transitionin twodimensions with three simulation methods,Phys.Rev.E87,042134 (2013).   
$^ 8$ M. Michel, S.C.Kapfer，W.Krauth，Generalized event-chain Monte Carlo:Constructing rejection-free global balance algo rithms from infinitesimal steps，J.Chem.Phys.140,054116 (2014).   
$^ { 9 }$ S.C.Kapfer,W.Krauth,Soft-disk melting:From liquid-hexatic coexistence to continuous transitions,Phys.Rev.Lett.114, 035702 (2015).   
$^ { 1 0 }$ M. Michel, J. Mayer, W.Krauth,Euent-chain Monte Carlo for classical continuous spin models, EPL 112,20003 (2015).   
$^ { 1 1 }$ Y.Nishikawa,M. Michel, W. Krauth，K. Hukushima, Euentchainalgorithm fortheHeisenberg model:Evidence for $z \sim 1$ dynamic scaling,Phys.Rev.E92,063306 (2015).   
$^ { 1 2 }$ H. Suwa, S. Todo, Markov Chain Monte Carlo Method without Detailed Balance,Phys.Rev.Lett.105,120603 (2010).   
$^ { 1 3 }$ S. Todo, H. Suwa, Geometric allocationapproaches in Markou chain Monte Carlo,J.Phys.:Conf.Ser.473,012013 (2013).   
$^ { 1 4 }$ R. D. Schram, G.T. Barkema, Monte Carlo methods beyond detailed balance,Physica A 418,88 (2015).   
$^ { 1 5 }$ N.Metropolis, A. W.Rosenbluth, M. N. Rosenbluth，A.H. Teller,E. Teller，Equations of state calculations by fast computing machines,J.Chem.Phys.21,1087 (1953).   
$^ { 1 6 }$ W. K. Hastings, Monte Carlo sampling methods using Markou chains and their applications,Biometrika 57,97(1970).   
$^ { 1 7 }$ A. Berretti, A. D.Sokal, New Monte Carlo method for the selfavoiding walk,J.Stat.Phys.40,483 (1985).   
$^ { 1 8 }$ K. Hukushima, Y. Sakai, An irreversible Markou-chain Monte Carlo method with skew detailed balance conditions,J. Phys.: Conf. Ser.473,012012 (2013).   
$^ { 1 9 }$ H. Muller-Krumbhaar, K. Binder， Dynamic properties of the Monte Carlo method in statistical mechanics,J. Stat.Phys.8,1 (1973).   
$^ { 2 0 }$ 1. Jensen,Aparalelalgorithmfor theenumerationof selfavoiding polygons on the square lattice,J.Phys.A:Math.Gen. 36,5731 (2003).   
$^ { 2 1 }$ H.-P. Hsu, P. Grassberger，Polymers confined between two parallel plane walls,J.Chem.Phys.120,2034 (2004).   
$^ { 2 2 }$ A. L. Owczarek, T. Prellberg,Scaling of self-avoiding walks in high dimensions,J. Phys.A:Math.Gen.34, 5773 (2001).   
$^ { 2 3 }$ Q. Liu,Y. Deng, T. M. Garoni, H.W. J.Blote,The $O ( n )$ loop model on a three dimensional lattice,Nucl.Phys.B 859,107 (2012).   
$^ { 2 4 }$ K. Binder, M. Nauenberg, V. Privman, A. P. Yound,Finite-size tests of hyperscaling,Phys.Rev.B31,3 (1985).   
$^ { 2 5 }$ Y. Deng,T.M. Garoni,A.D.Sokal, Dynamic critical behavior of the worm algorithm for the Ising model,Phys.Rev.Lett.99, 110601 (2007).   
$^ { 2 6 }$ Jiasheng Zhang,Youjin Deng,to be published.