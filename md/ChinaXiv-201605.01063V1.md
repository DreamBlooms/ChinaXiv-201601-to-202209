# Critical behavior of spatial evolutionary game with altruistic to spiteful preferences on two-dimensional lattices

YANG Bo, $^ { 1 , 2 }$ LI Xiao-Teng, $^ { 1 , 2 }$ CHEN Wei, $^ 3$ LIU Jian,4 and CHEN Xiao-Song $^ { 1 , 2 }$ ， $^ *$

（204号 $^ 1$ Institute of Theoretical Physics， Key Laboratory of Theoretical Physics, Chinese Academy of Sciences，P.O.Box 2735，Beijing 100190，China $^ 2$ School of Physical Sciences, Universityof Chinese Academyof Sciences，No.19A Yuquan Road,Beijing 19Cina $^ 3$ Supercomputing Center of CAS, Computer Network Information Center, Chinese Academy of Sciences，P.O. Box 349，Beijing 100190，China （204号 $^ 4$ School of Science, Beijing Technology and Business University, Beijing 10o048, P.R. China (Dated: May 8, 2016)

Self-questioning mechanism which is similar to single spin-flip of Ising model in statistical physics is introduced into spatial evolutionary game model. We propose a game model with altruistic to spiteful preferences via weighted sums of own and opponent's payofs. This game model can be transformed into Ising model with an external feld. Both interaction between spins and the external field are determined by the elements of payoff matrix and the preference parameter. In the case of perfect rationality at zero social temperature,this game model has three diffrent phases which are entirely cooperative phase,entirely non-cooperative phase and mixed phase. In the investigations of the game model with Monte Carlo simulation,two paths of payoff and preference parameters are taken. In one path,the system undergos a discontinuous transition from cooperative phase to non-cooperative phase with the change of preference parameter. In another path,two continuous transitions appear one after another when system changes from cooperative phase to non-cooperative phase with the prefenrence parameter. The critical exponents $\nu$ ， $\beta$ and $\gamma$ of two continuous phase transitions are estimated by the finite-size scaling analysis.Both continuous phase transitions have the same critical exponents and they belong to the same universality class as the two-dimensional Ising model.

PACS numbers:64.60.De,05.40.Ca,02.50.Le,87.23.Ge

# INTRODUCTION

The spatial evolutionary game has been minutely studied to explain the emergence and maintenance of cooperation among selfish individuals during the past few years [1-4] in economics,biology and social sciences.

The structure of social networks and the evolutionary rules are two important research fields of evolutionary game [5]. Many interesting results have been obtained on different spatial structures,such as two dimensional regular lattices [6,7],small world networks [8] and scalefree networks [9]. Learning mechanism has been widely adopted in evolutionary rules [5-7, 9]. Players revise their strategies by learning from their neighbors. Selfquestioning mechanism is presented in Ref. [1O]. Each player adopts its anti-strategy to play a virtual game with all its neighbors,then obtains a virtual payoff. By comparing the real payoff and the virtual payoff,each player can get its optimal strategy corresponding to the highest payoff [1O-12]. This evolutionary rule is similar to Ising model's Metropolis algorithm in statistical physics.

Traditional economic theory predicts that individuals will not supply goods and services without being compensated. However， individuals do not always pursue self-interest: people risking their own life to rescue others,soldiers participatingin wars voluntarily,many kinds of charity etc [13]. Nowak summarized five possible rules for the evolution of cooperation corresponding to different situations:Kin selection,Direct reciprocity, Indirect reciprocity,Network reciprocity,Group selection [4].In economics,altruistic and spiteful preferences have been introduced to study evolutionary stability of altruism and spitefulness [13-16]. In this paper,altruism,egoism and spitefulness are considered through a preference parameter $p$ .When $p > 0$ ，player is altruistic,which means a player has a positive regard for his opponents. $p = 0$ represents the player as selfish. $p < 0$ determines the player as spiteful.

Instatistical physics,the internal energy decreases and approaches a minimum value at equilibrium in a closed system with constant external parameters and entropy (Principle of minimum energy）[17]. Similarly,in economics,profit maximization is an eternal pursuit to the individual and society, so one may expect that the equilibrium probability distribution function of payoffs in a closed system of agents has the Boltzmann-Gibbs form [18]. In analogy to Ising model,spatial evolutionary game model can convert into Ising-like model,the effective Hamiltonian of evolutionary game can be obtained. By analyzing the effective Hamilton of game, game model is divided into three different phases:entirely cooperative phase (ferromagnetic order upward),entirely non-cooperative phase (ferromagnetic order downward)，mixed phase (anti-ferromagnetic order）at zero social temperature (the noise introduced to permit irrational choices [6,7]). Two paths (the phase of game model translating from entirely cooperative phase to entirely non-cooperative phase） are investigated. Continuous and discontinuous phase transitions are observed at sufficiently low temperature. Fourth-order cumulant is investigated to locate critical points. The critical exponents $( \nu , \beta , \gamma )$ are obtained by finite-size scaling.

This paper is organized as follows.In section II,we make a brief review of Ising model with a nonzero field firstly, then we introduce our evolutionary game model and obtain the effective Hamilton of game model. Finally, the ground state of game model is divided into three phases in the condition of perfect rationality;in section III,we present and discuss the results;in section IV,we draw a conclusions from the results.

# MODEL

# A brief review of Ising model

The Hamiltonian of Ising model with an interaction $J _ { i j }$ for any two adjacent sites $i$ and $j$ and an external magnetic field $h _ { i }$ for any site $i$ is given by

$$
E = - \sum _ { < i j > } J _ { i j } S _ { i } S _ { j } - \sum _ { i } h _ { i } S _ { i } ,
$$

where $S _ { i }$ is the Ising spin( $S _ { i } ~ = ~ \pm 1$ ）at lattice site $i$ ， the first sum is over pairs of adjacent spins (every pair is counted once).The notation $< i j >$ indicates that sites $i$ and $j$ are the nearest neighbors.

Ising models can be classified according to the sign of the interaction: for $J _ { i j } > 0$ the interaction is ferromagnetic and it is antiferromagnetic if $J _ { i j } < 0$ ; when $J _ { i j } = 0$ ， the spins are noninteracting.Additionally, the spin site wants to line up with the external field,for $h _ { i } > 0$ the spin site $i$ desires to line up in the positive direction and it desires to line up in the negative direction if $h _ { i } < 0$ when $h _ { i } = 0$ ，there is no external influence on the spin site.For $h _ { i } = 0$ ，the Ising model is symmetric under switching the value of the spin in all the lattice sites, but a non zero field breaks this symmetry. The introduction of nonzero magnetic field destroys the continuous phase transition of the ferromagnetic Ising model, whereas the nonzero uniform field does not destroy the transition of the antiferromagnetic Ising model. The exact solution of antiferromagnetic Ising model in an external field can not be obtained.Instead, the researchers focus on the critical line (Néel temperature as a function of external feld) for the square lattice antiferromagnetic Ising in an external field[19-23]. For critical line, there are different approximations [20,22,24],for example $c o s h ( h / T _ { c } ) = s i n h ^ { 2 } ( 2 J / T _ { c } )$ ．The ends of the $( T , h )$ critical line are $( 2 . 2 6 9 , 0 )$ and $( 0 , 4 | J | )$ ,and the antiferromagnetic phase is completely enclosed by transition lines [25].

At zero temperature,a critical magnetic field $h _ { c }$ exist in antiferromagnetic Ising model such as $h _ { c } = 4 | J |$ for a square lattice.When $- 4 J < h < 4 J$ ，theantiferromagnetic order-states are preserved even though the magnetic field tries to align all spins along its direction. When $h > 4 J$ or $h < - 4 J$ , ferromagnetic ordered-states dominate.

In order to obtain energy difference $\Delta E$ ( $\textit { \textbf { \ i } }$ flips its direction $S _ { i }  - S _ { i }$ ),the Eq.1 can be rewritten as

$$
E = - \sum _ { < k j > } ^ { \prime } J _ { k j } S _ { k } S _ { j } - S _ { i } \sum _ { j } J _ { i j } S _ { j } + \sum _ { k } ^ { \prime } h _ { k } S _ { k } - h _ { i } S _ { i } ,
$$

where $k$ is a spin except $i$ .When the state of $i$ flips,the new energy $E ^ { \prime }$ is

$$
E ^ { \prime } = - \sum _ { < k j > } ^ { \prime } J _ { k j } S _ { k } S _ { j } + S _ { i } \sum _ { j } J _ { i j } S _ { j } + \sum _ { k } ^ { \prime } h _ { k } S _ { k } + h _ { i } S _ { i } .
$$

Thus,the energy difference $\Delta E = E ^ { \prime } - E$ is

$$
\Delta E = 2 S _ { i } \sum _ { j } J _ { i j } S _ { j } + 2 h _ { i } S _ { i } .
$$

# Introduction of game model

For a randomly given agent $i$ ，two available strategies cooperation ( $S _ { i } = + 1$ ）and non-cooperation ( $S _ { i } =$ $^ { - 1 ) }$ can be adopted to play with its nearest neighbors. Mutual cooperation yields the reward $a$ ，mutual noncooperation leads to punishment $d$ ,and the mixed choice gives the cooperator the suck's payoff $b$ and the noncooperation the temptation $c$ ：

The randomly chosen player $i$ revises its strategy according to self-questioning mechanism and the stochastic evolutionary rule. That is to say, player $i$ adopts its antistrategy to play a virtual game with all its neighbors, and calculates the virtual payoff. By comparing the real payoff and the virtual payoff,player will find out its optimal strategy [1O,11]. In next round, player $i$ will revise its current strategy to its anti-strategy with a given probability

$$
W _ { i } = m i n \{ 1 , e ^ { ( \frac { \Delta G _ { i } } { T } ) } \} ,
$$

where $\Delta G _ { i } = G _ { i } ^ { \prime } - G _ { i }$ ， $G _ { i }$ and $G _ { i } ^ { \prime }$ are the real and virtual payoff of player $i$ ，respectively. The noise can be described via $T$ .The $G _ { i }$ is defined as

$$
G _ { i } = g _ { i } + p g _ { i } ^ { \prime } ,
$$

where $g _ { i }$ represents the total payoff of player $i$ (player $i$ plays with all its nearest neighbors and accumulates the obtained payoff). $g _ { i } ^ { \prime }$ represents all its nearest neighbors's total payoff by playing with $i$ ： $p$ is preference parameter, positive denotes altruism,negative stands for spite,and zero characterizes classical own profit maximization.

This evolutionary rule is similar to single spin-flip of Ising model in statistical physics. We will find out the relationship between evolutionary game model and Ising model hereafter.

For a given agent $i$ ，the number of cooperative and non-cooperative neighbors are $^ { n _ { i + } }$ and $n _ { i - }$

$$
\begin{array} { c } { { n _ { i + } = \displaystyle \sum _ { j } \frac { 1 + S _ { j } } { 2 } = \displaystyle \frac { 1 } { 2 } ( k _ { i } + \sum _ { j } S _ { j } ) , } } \\ { { n _ { i - } = \displaystyle \sum _ { j } \frac { 1 - S _ { j } } { 2 } = \displaystyle \frac { 1 } { 2 } ( k _ { i } - \sum _ { j } S _ { j } ) , } } \end{array}
$$

where $j$ is the neighbors set of agent $i$ ， $k _ { i }$ is the sum of neighbors.

By playing the game with all its nearest neighbors, agent $i$ acquires its payoff $g _ { i }$ . At the same time,itS neighbors acquire $g _ { i } ^ { \prime }$ in this process. when $S _ { i } = + 1$ ， $g _ { i } = a n _ { i + } + b n _ { i - }$ and $g _ { i } ^ { \prime } = a n _ { i + } + c n _ { i - }$ ; when $S _ { i } = - 1$ ， （204号 $g _ { i } = c n _ { i + } + d n _ { i - }$ and $g _ { i } ^ { \prime } = b n _ { i + } + d n _ { i - }$ ：

In the process of virtual game (corresponding to $i$ flips its direct in Ising), $S _ { i }  - S _ { i }$ ,the payoffs difference are $\Delta g _ { i }$ and $\Delta g _ { i } ^ { \prime }$ . They can be calculated as

$$
\begin{array} { r } { \Delta g _ { i } = S _ { i } [ ( c n _ { i + } + d n _ { i - } ) - ( a n _ { i + } + b n _ { i - } ) ] , } \\ { \Delta g _ { i } ^ { \prime } = S _ { i } [ ( b n _ { i + } + d n _ { i - } ) - ( a n _ { i + } + c n _ { i - } ) ] . } \end{array}
$$

In our model,players care not only about their own monetary payoffs,but also about their opponent's monetary payoffs. Thus, the play $i$ does not necessarily maximize payoff itself,but rather weighted sums of own and opponent's payoffs. The change of payoffs when the state of $i$ flips: $S _ { i }  - S _ { i }$ can be written as,

$$
\Delta G _ { i } = \Delta g _ { i } + p \Delta g _ { i } ^ { \prime } .
$$

$\beta = 1 / T$ ， $T$ is the effective social temperature,which measures the extent of noise.For convenience,we define the effective energy as $E _ { e f f } = - G$ . Thus, the effective energy difference in this system is $\Delta E _ { i } = - \Delta G _ { i }$ . according to Eq.12,we obtain

$$
\begin{array} { l } { \Delta E _ { i } = - \displaystyle \frac 1 2 S _ { i } \{ [ ( c - d - a + b ) + p ( b - d - a + c ) ] \sum _ { j } S _ { j } } \\ { \qquad + [ ( c + d - a - b ) + p ( b + d - a - c ) ] k _ { i } \} . \qquad ( 1 3 ) } \end{array}
$$

As the Ising model, the strength of interaction $J _ { i j }$ and external field $h _ { i }$ can be defined as

$$
\begin{array} { c } { { J _ { i j } = - \displaystyle \frac { 1 } { 4 } [ ( c - d - a + b ) + p ( b - d - a + c ) ] , } } \\ { { h _ { i } = - \displaystyle \frac { 1 } { 4 } [ ( c + d - a - b ) + p ( b + d - a - c ) ] k _ { i } . } } \end{array}
$$

The effective energy can be obtained

By substituting Eq. 9 and Eq.10 into Eq. 11，we obtain

$$
\begin{array} { c } { { E _ { e f f } = \displaystyle \frac { 1 } { 4 } [ ( c - d - a + b ) + p ( b - d - a + c ) ] \sum _ { < i j > } S _ { i } S _ { j } } } \\ { { + \displaystyle \frac { 1 } { 4 } [ ( c + d - a - b ) + p ( b + d - a - c ) ] \sum _ { i } k _ { i } S _ { i } . } } \end{array}
$$

Asa special accommodation，we investigate weak Prisoner's Dilemma. We take $a = a$ ， $b = 0$ ， $c = 1 - a$ ， $d = 0$ and $1 / 3 < a < 1 / 2$ ．Thus,the strength of interaction, external field and effective energy can be written as

$$
\begin{array} { r } { J _ { i j } = - \displaystyle \frac { 1 } { 4 } ( 1 - 2 a ) ( 1 + p ) , } \\ { h _ { i } = - \displaystyle \frac { 1 } { 4 } ( 1 - 2 a - p ) k _ { i } . } \end{array}
$$

$$
E _ { e f f } = \frac { 1 } { 4 } ( 1 - 2 a ) ( 1 + p ) \sum _ { < i j > } S _ { i } S _ { j } + \frac { 1 } { 4 } ( 1 - 2 a - p ) \sum _ { i } k _ { i } S _ { i } .
$$

$$
\begin{array} { c } { { \Delta G _ { i } = \displaystyle \frac 1 2 S _ { i } \{ [ ( c - d - a + b ) + p ( b - d - a + c ) ] \sum _ { j } S _ { j } } } \\ { { + [ ( c + d - a - b ) + p ( b + d - a - c ) ] k _ { i } \} . } } \end{array}
$$

For two dimensional square lattices, $k _ { i } = 4$ ,the effective energy is

$$
E _ { e f f } = \frac { 1 } { 4 } ( 1 - 2 a ) ( 1 + p ) \sum _ { < i j > } S _ { i } S _ { j } + ( 1 - 2 a - p ) \sum _ { i } S _ { i } .
$$

Ising model in canonical ensemble is based on the Boltzmann-Gibbs law，which states that the probability distribution function (PDF） of energy $E$ is $P ( \{ S _ { i } \} ) =$ $e ^ { - \beta E ( \{ S _ { i } \} ) } / Z$ ，where $\beta = 1 / k _ { b } T$ ， $k _ { b }$ is Boltzmann constant, $T$ is temperature and $\begin{array} { r } { Z = \sum _ { i } e ^ { - \beta E ( \{ S _ { i } \} ) } } \end{array}$ is normalization constant. When $T  0$ ，the system abides the Ising interactions and external field strictly. When $T \to \infty$ , the system evolves randomly. By analogy with Ising model, one may expect that the equilibrium PDF of game payoff $G$ in a closed system of game agents has the Boltzmann-Gibbs form $P ( \{ G _ { i } \} ) = e ^ { \beta G ( \{ S _ { i } \} ) } / Z$ ，where

# Three phases of game model

The ground state of game model at zero temperature can be divided though three equations: the strength of interaction $J = 0$ ,the external field $h = 0$ and the critical external feld $h = 4 | J |$ .Results of these functions are $a = 1 / 2$ or $p = - 1$ for $J = 0$ ; $a = 1 / 2 ( 1 - p )$ for $h = 0$ $a = 1 / ( 2 + p )$ for $h = - 4 J$ ，and $p = 0$ for $h = 4 J$ ， which are shown in FIG.1.Game model is divided into three phases: entirely cooperative phase (ferromagnetic order upward), entirely non-cooperative phase (ferromagnetic order downward),mixed phase (anti-ferromagnetic order). The region of cooperative and non-cooperative coexistence is enclosed by the critical lines ( $p = 0$ and $a = 1 / ( 2 + p ) ;$ .In game model, $T$ is the measure of stochastic uncertainties (noise） allowing the irrational choices. $a$ is a inherent parameter,which belongs the payoff matrix.when $a > 0 . 5$ ,cooperation will gain much more benefit；when $a ~ < ~ 0 . 5$ ，non-cooperation will get more. But cooperation can survive for $a ~ < ~ 0 . 5$ owing to altruism. $p$ as a preference parameter measures the relationship between spitefulness,egoism and altruism. Non-cooperation can arise only spitefulness existing.

![](images/17f0522dd7b108610ad8603ffaba1ca7efbe380577f7854bf54f14caddf7f7fe.jpg)  
FIG.1. The ground state at zero temperature on the $( a , p )$ parameter space. Three phases can exist: four small upward arrows denote entirely cooperative phase (ferromagnetic order upward),four small downward arrows denote entirely non-cooperative phase (ferromagnetic order downward） and small arrows upward and downward alternatively denote cooperative and non-cooperative coexistence (antiferromagnetic order).The phase transition and critical phenomena are investigated by two special paths (two dash lines)，which cross cooperative and non-cooperative region.

# RESULTS AND DISCUSSIONS

We have preformed Monte Carlo simulations on square lattice with periodic boundary conditions using Metropolis algorithm. The randomly chosen player $i$ revises its strategy according self-questioning rule. In general,we discarded the first 10000 Monte Carlo Steps (MCS) in order to achieve the stationary regime for all lattices sizes. In order to estimate the quantities of interest，we considered the next $2 \times 1 0 ^ { 5 }$ MCS to calculate the averages. To further improve accuracy, the final results are average over 1Oo independent realization with different initial configurations.

Magnetization is the order parameter of ferromagnetic

Ising. Staggered magnetization is the order parameter of antiferromagnetic Ising. In order to obtain the formula of order parameter. The two-dimensional squarelattice is divided into two sublattices,one includes all spins up another includes all spins down for antiferromagnetic Ising model. We calculated the sublattice magnetization per spin, $m _ { 1 }$ and $m _ { 2 }$ , defined as $m _ { 1 } = 2 \langle \Sigma _ { i } S _ { i } \rangle / N$ and $m _ { 2 } = 2 \langle \Sigma _ { j } S _ { j } ^ { \prime } \rangle / N$ ，where $S _ { i }$ is the spin of the first sublattice,and $S _ { j } ^ { \prime }$ is the spin of the second sublattice. The total magnetization which is the order parameter of ferromagnetic systems can be defined as

$$
m _ { t } = { \frac { 1 } { 2 } } ( m _ { 1 } + m _ { 2 } ) .
$$

For antiferromagnetic Ising model, the staggered magne tization can be defined as

$$
m _ { s } = \frac { 1 } { 2 } | m _ { 1 } - m _ { 2 } | ,
$$

which is the order parameter for antiferromagnetic systems [26,27]. The corresponding susceptibilities are defined by

$$
\chi ( m ) = N [ < m ^ { 2 } > - < m > ^ { 2 } ] ,
$$

and the fourth-order Binder cumulants is

$$
U ( m ) = 1 - \frac { < m ^ { 4 } > } { 3 < m ^ { 2 } > ^ { 2 } } ,
$$

where $m$ can be $m _ { t }$ or $m _ { s }$ for $\chi ( m )$ and $U ( m )$

（204号 $m _ { t }$ ， $m _ { s }$ ， $\chi ( m )$ and $U ( m )$ obey the following finite size scaling relations in the neighborhood of the stationary critical point $p _ { c }$

$$
m _ { L } ( p ) = L ^ { - \beta / \nu } m _ { 0 } ( L ^ { 1 / \nu } \varepsilon ) ,
$$

$$
\chi _ { L } ( p ) = L ^ { \gamma / \nu } \chi _ { 0 } ( L ^ { 1 / \nu } \varepsilon ) ,
$$

$$
U _ { L } ( p ) = U _ { 0 } ( L ^ { 1 / \nu } \varepsilon ) ,
$$

where $\varepsilon = ( p - p _ { c } ) / p _ { c }$ ， $p _ { c }$ is the critical preference parameter for a given $T$

The derivative of fourth-order Binder cumulants $U _ { L } ( p )$ is

$$
U _ { L } ^ { \prime } ( p ) = L ^ { 1 / \nu } \frac { U _ { 0 } ( L ^ { 1 / \nu } \varepsilon ) } { p _ { c } } .
$$

We can obtain the critical exponent $\nu$ from a log-log plotof $U _ { L } ^ { \prime } ( p _ { c } )$ versus $L$ ：

In this model, the evolution of game model from entirely cooperative phase to entirely non-cooperative phase is aninteresting problem which involves the interaction between game'sparameter $a$ and individual preference $p$ at low social temperatures. Thus,two special evolutionary paths $a = 1 / 2 p + 0 . 6$ and $a = 1 / 2 p + 0 . 4$ (broken lines in FIG.1）are taken.The path $a = 1 / 2 p + 0 . 4$ passes through the antiferromagnetic region.

![](images/5fee15cff29a080ce016f58e2473d8dac3356f6ce2aacbe971b526182e0e3c52.jpg)  
FIG.2.Magnetisation as a function of $p$ for several lattice sizes $L$ along the path $a = 1 / 2 p + 0 . 6$ ,magnetisation is discontinuous at transition point ( $p = - 0 . 1 , a = 0 . 5 5 ,$ ）

![](images/4f95d81fb310f2216449e103cee658813d86c4c6fadc1ba4c4af722ad2b86543.jpg)  
FIG.3． Staggered magnetization $m _ { s }$ for various system sizes along the path $a = 1 / 2 p + 0 . 4$ at $T = 0 . 0 2$ .Apparently, two critical points exist,because of the finite-size effects near （20 $p = 0$ and $p = 0 . 1 5$ have been observed.

In FIG.2,magnetisation as a function of $p$ for several lattice sizes $L$ is shown at $T = 0 . 0 0 2$ .Thevalue of the magnetization $m _ { t }$ jumps from $+ 1$ to $- 1$ as the preference parameter $p$ is scanned from the positive direction to the negative direction by the path $a = 1 / 2 p + 0 . 6$ of FIG. 1. The order parameter of magnetisation $m _ { t }$ is discontinuous. Obviously, the critical exponent $\beta / \nu = 0$ ,indicate a discontinuous phase transition.

![](images/47db5ec5054a2759af3cc252be05d36e8237c204d98951c5392fdf6ad8c6b5a9.jpg)  
FIG.4.Susceptibility as a function of $p$ for various system sizes along the path $a = 1 / 2 p + 0 . 4$ at $T = 0 . 0 2$ .The susceptibility has sharp jump near $p = 0$ and $p = 0 . 1 5$ ：

Theoretically, the phase transition sweeping along path $a = 1 / 2 p + 0 . 6$ is a transition from ferromagnetic order upward to ferromagnetic order downward. This is equivalent to a magnetic material placed in an external field $h$ . If the temperature is lower than $T _ { c }$ (critical temperature at the intersection of $h = 0$ and $a = 1 / 2 p + 0 . 6 )$ ， the value of the magnetization $m$ jumps from positive to negative as the external magnetic field $h$ is scanned from the positive direction to the negative direction.Consider the 2D Ising model on a square lattice,the critical temperature is $T _ { c } = 2 . 2 6 9 J = 0 . 0 0 2 2 5$ at transition point 1 $p = - 0 . 1 , a = 0 . 5 5$ ）

In FIG.3,The order parameter of antimagnetisation $m _ { s }$ asa function of $p$ for several lattice sizes $L$ is shown at $T = 0 . 0 2$ . The staggered magnetization changes with the lattice sizes near critical points.In FIG.4,susceptibility as a function of $p$ for various system sizes is shown. The susceptibility has two maximum whose position shift toward the critical values as one increase $L$ . As one increases $L$ the peak around the critical point increases. Those phenomena display remarkable finite-size effects. There are two critical points existing.To see them more clearly, we narrow down the range of $p$ to redraw the staggered magnetization (FIG.5,FIG.6) and susceptibility (FIG.7, FIG. 8).

Theoretically，path $a ~ = ~ 1 / 2 p + 0 . 4$ intersects antiferromagnetic critical line.The antimagnetic phase transition is a second-order transition.In this situation, $\textit { J } = \ - ( 0 . 2 \ - \ p ) ( 1 \ + \ p ) / 4$ ， $h \ = \ 2 p \ : - \ : 0 . 2$ and the approximate critical line is $c o s h ( 2 p - 0 . 2 / T _ { c } ) =$ $s i n h ^ { 2 } [ ( p - 0 . 2 ) ( 1 + p ) / ( 2 T _ { c } ) ]$ .Two intersection can be obtained by solving this equation at $T _ { c } ~ = ~ 0 . 0 2$ ， $p _ { c } ~ =$ 0.01167 and $p _ { c } = 0 . 1 3 1 4 2 6$ ：

To locate the two critical points by using Monte Carlo simulations,we plot the reduced fourth-order cumulant, respectively. The fourth-order cumulant of the left phase transition point in FIG.3 is shown in FIG.9 as a function of $p$ for several values of $L$ .The scaling relation for the fourth-order cumulant shows that,at the critical preference parameter,all curves must cross at a common point. From the crossing of these curves,we estimate the critical preference parameter $p _ { c } = 0 . 0 1 1 2 7 \pm 0 . 0 0 0 1 4$ The fourth-order cumulant of the right phase transition point in FIG.3 is shown in FIG.1O as a function of $p$ for several values of $L$ . The critical preference parameter is $p _ { c } = 0 . 1 3 1 5 6 \pm 0 . 0 0 0 0 8$ . Critical points are in good agreement with the one found from theoretical prediction （ $p _ { c } = 0 . 0 1 1 6 7$ and $p _ { c } = 0 . 1 3 1 4 2 6$ ）

![](images/b68872dedbca6d81882644183829608ad5fa8d48be6862e968559c9bd0289420.jpg)  
FIG.5.The Staggered magnetization of the left critical point in FIG.3 near $p = 0$ ：

![](images/d91b40fffc557c912ab7f85f78c8f111dcc5c652f536f576ef271734d1edb3b4.jpg)  
FIG.6. The Staggered magnetization $m _ { s }$ of the right critical point in FIG.3 for various system sizes along the path $a =$ $1 / 2 p + 0 . 4$ near $p = 0 . 1 5$ ：

In order to compare the critical phenomena with Ising model,we evaluate the critical exponents via finite size scaling relations in FIG.11. The log-log plots of $m _ { L } ( p )$ as function of $L$ at the critical points $p _ { c } = 0 . 0 1 1 2 7$ and $p _ { c } = 0 . 1 3 1 5 6$ are shown at FIG.11(a) and FIG.11(b), respectively. The best fit to the data points furnishes the value $\beta / \nu = 0 . 1 1 6 \pm 0 . 0 0 9 3$ at $p _ { c } = 0 . 0 1 1 2 7$ . When $\begin{array} { r } { p _ { c } = } \end{array}$ 0.13156, the value is $\beta / \nu = 0 . 1 1 3 5 \pm 0 . 0 0 7 0 2$ . FIG. 11(c) and FIG. $1 1 ( \mathrm { d } )$ show the log-log plot of susceptibility $\chi _ { L } ( p _ { c } )$ vS $L$ at the critical points $p _ { c } = 0 . 0 1 1 2 7$ and $p _ { c } =$ 0.13156,respectively. the slope of the fitting lines are $\gamma / \nu = 1 . 7 4 9 \pm 0 . 0 2 1 2$ at $p _ { c } = 0 . 0 1 1 2 7$ ,and $\gamma / \nu = 1 . 7 3 6 \pm$ 0.0405 at $p _ { c } = 0 . 1 3 1 5 6$ ．The log-log plots of $U _ { L } ^ { \prime } ( p )$ as function of $L$ at the critical points $p _ { c } ~ = ~ 0 . 0 1 1 2 7$ and $p _ { c } = 0 . 1 3 1 5 6$ are shown at FIG. 11(e) and FIG.11(f), respectively. The solid lines are the best fit with slope $1 / \nu = 0 . 9 7 7 \pm 0 . 0 3 9 1$ at $p _ { c } = 0 . 0 1 1 2 7$ ，and $1 / \nu = 0 . 9 8 2 \pm$ 0.0296 at $p _ { c } = 0 . 1 3 1 5 6$ ：

![](images/45fde8dd063cdc334c3b98f6e8aca7eda978e404e9e7b8b0e8f49775795c210f.jpg)  
FIG.7. The susceptibility of the left critical point in FIG.4 for varying lattice size near $p = 0$ ：

![](images/985725a59e18452bf4d3ea7d318868e565a60b9b691341625db5e2f36517e937.jpg)  
FIG.8. The susceptibility of the right critical point in FIG. 4 as a function of $p$ for various system sizes along the path $a = 1 / 2 p + 0 . 4$ near $\mathrm { p } { = } 0 . 1 5$ ：

# CONCLUSIONS

A general game model about economical and social activities is proposed in this paper.We can relate this game model with Ising model in statistical mechanics.The interaction between spins and external field of the Ising model are determined by the reward $a$ of cooperation and the preference parameter $p$ ,which can be altruistic to spiteful. We have studied weak prisoner's dilemma on a square lattice with periodic boundary condition. At zero social temperature without noise for irrational decision,there are three different phases: entirely cooperative phase (ferromagnetic orderupward),entirely noncooperative phase (ferromagnetic order downward） and mixed phase (anti-ferromagnetic order）.In the investigation of evolution from entirely cooperative phase to entirely non-cooperative phase,two evolutionary pathS $a = 1 / 2 p + 0 . 6$ and $a = 1 / 2 p + 0 . 4$ have been taken.For the path $a = 1 / 2 p + 0 . 6$ ，the sytem undergoes a discontinuous transition under a critical temperature. For the path $a = 1 / 2 p + 0 . 4$ ，there are two continuous phase transitions at the critical points $p _ { c } = 0 . 0 1 1 2 7$ and $p _ { c } = 0 . 1 3 1 5 6$ respectively. The critical exponents $\beta / \nu$ $\gamma / \nu$ and $1 / \nu$ are estimated for the two critical points at a fixed reduced temperature $T = 0 . 0 2$ . Within the error range of data, the critical exponents at $p _ { c } = 0 . 0 1 1 2 7$ and $p _ { c } = 0 . 1 3 1 5 6$ are the same and equal to the results of two-dimensional Ising model. These results indicate that the continuous phase transitions of the game model belong to the same universal class as the two-dimensional Ising model.

![](images/e31289be7c7d73519bc1c433fb46580f5c6482cf8388a225ff76f33b57a44686.jpg)  
FIG.9.Fourth-order cumulant $U _ { L } ( p )$ of the left critical point as a function of $p$ ．The intersection point is $p _ { c } = 0 . 0 1 1 2 7 \pm$ 0.00014.

![](images/a545af297def5250c6688c8337fea65b54404c10df8284471c790fba1aa5612b.jpg)  
FIG.10.Fourth-order cumulant $U _ { L } ( p )$ of the right critical point as a function of $p$ for various system sizes and $T = 0 . 0 2$ The intersection point is $p _ { c } = 0 . 1 3 1 5 6 \pm 0 . 0 0 0 0 8$

# ACKNOWLEDGMENTS

This work was supported by the National Natural Science Foundation of China (grant Nos. 11l2l403 and 11504384).

![](images/89ae89a416fa96ff962e55989cd1999a8946467118712613d28c186906116f4b.jpg)  
FIG.11. Log-log plot of staggered magnetization $m _ { L } ( p _ { c } )$ vS $L$ ：(a) $p _ { c } ~ = ~ 0 . 0 1 1 2 7$ ，the slope of fitting line is $- \beta / \nu ~ =$ $- 0 . 1 1 6 \pm 0 . 0 0 9 3$ ；(b) $p _ { c } ~ = ~ 0 . 1 3 1 5 6$ ，the slope is $- \beta / \nu ~ =$ $- 0 . 1 1 3 5 \pm 0 . 0 0 7 0 2$ ．Log-log plot of susceptibility $\chi _ { L } ( p _ { c } )$ vs $L$ ：(c) $p _ { c } ~ = ~ 0 . 0 1 1 2 7$ ，the solid line is the best fit with slop $\gamma / \nu ~ = ~ 1 . 7 4 9 \pm 0 . 0 2 1 2$ ；(d) $\gamma / \nu ~ = ~ 1 . 7 3 6 \pm 0 . 0 4 0 5$ at $p _ { c } = 0 . 1 3 1 5 6$ . Log-log plot of $U _ { L } ^ { \prime } ( p _ { c } )$ vS $L$ ：(e) $p _ { c } = 0 . 0 1 1 2 7$ ， the solid line is the best fit with slop $1 / \nu = 0 . 9 7 7 \pm 0 . 0 3 9 1$ · (f) $1 / \nu = 0 . 9 8 2 \pm 0 . 0 2 9 6$ at $p _ { c } = 0 . 1 3 1 5 6$ ：

[1] R.Axelrod,The Evolution of Cooperation,Basic Books, New York, (1984).   
[2] M.A.Nowak and R.M.May, Nature(London) 359 (1992) 826.   
[3] M.A.Nowak,Evolutionary Dynamics: Exploring the Equations of Life,Harvard University Press,Harvard, MA, (2006).   
[4]M.A.Nowak,Science 314(2006)1560.   
[5] G. Szabó and G. Fath, Phys. Rep. 446 (2007) 97.   
[6] G.Szabó and C.Töke,Phys.Rev.E 58(1998)69.   
[7]G.Szabó,J.Vukov,and A.Szolnoki,Phys.Rev.E 72 (2005) 047107.   
[8]J.Vukov,1 G. Szabó,and A. Szolnoki,Phys.Rev.E 77 (2008)026109.   
[9]F.C.Santos and J.M.Pacheco,Phys.Rev.Lett.95 (2005)098104.   
10] W.X.Wang,J.Ren, G.R.Chen,and B.H. Wang, Phys. Rev.E 74(2006)056113.   
11]K.Gao,W.X.Wang，and B.H.Wang,Physica A 380 (2007) 528.   
12] Y.K.Liu, Z.Li,X.J.Chen,and L.Wang, Chin.Phys. Lett.26(2009)088902.   
13] H.Bester and W.Güth,Journal of Economic Behavior & Organization 34(1998) 193.   
14] A.Possajennikov,Journal of Economic Behavior & Organization 42(2000）125.   
15]D.K.Levine,Review of Economic Dynamics 1 (1998) 593-622.   
[16] F.Bolle and A.Kritikos,Theory and Decision 60 (2006) 371.   
[17] H.B.Callen,Thermodynamics and an Introduction to Thermostatistics (2nd).New York:John Wiley & Sons (1985).   
[18] Q. Zhuang,Z.R. Di,and J. S.Wu, PloS ONE 9 (2014) e105391.   
[19] L.Onsager,Phys.Rev.65(1944) 117.   
[20] E.Müller-Hartmann and J. Zittartz, Z.Phys.B 27 (1977) 261.   
[21]X.N.Wu and F.Y.Wu,Phys.Lett.A144(1990)123.   
[22] X.Z. Wang and J. S.Kim, Phys. Rev. Lett. 78 (1997) 413.   
[23] S.Y.Kim,J.Korean,Phys.Soc,61(2012) 1950.   
[24] S.J. Penney,V.K.Cumyn,and D.D.Betts,Phys.A 330(2003）507.   
[25]M.E.Fisher,Rep.Prog.Phys.30(1967)615.   
[26] J.P.Neirotti and M.J.de Oliveira,Phys.Rev.B 54 (1996)6351.   
[27] M.Godoy and W.Figueiredo,Phys.Rev.E 65 (2002) 026111.