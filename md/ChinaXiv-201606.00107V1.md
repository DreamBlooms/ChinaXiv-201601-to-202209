# Sudden jumps and plateaus in the quench dynamics of a Bloch state

J. M. Zhang $^ { 1 , 2 }$ and Hua-Tong Yang3 $^ { 1 }$ Fujian Provincial Key Laboratory of Quantum Manipulation and New Energy Materials, College of Physics and Energy，Fujian Normal University，Fuzhou 35ooo7，China 1 $^ 2$ Fujian Provincial Collaborative Innovation Center for Optoelectronic Semiconductors and Efficient Devices，Xiamen，361oo5，China （204号 $^ 3$ School of Physics， Northeast Normal University， Changchun 130024， China

Take a one-dimensional tight binding chain with the periodic boundary condition and put a particle in some Bloch state,then quench it by suddenly changing the potential of some site. In the ensuing time evolution,the probability density of the wave function at an arbitrary site jumps constantly between plateaus. This phenomenon adds to another one that the survival probability of the particle in the initial Bloch state shows cusps periodicall,which was found previously in the same scenario (Zhang and Yang,arXiv:1601.03569). The two,one in the real space and one in the momentum space,complement each other to provide a comprehensive picture of the quench dynamics of a Bloch state.Underlying the cusps and jumps is the exactly solvable,nonanalytic dynamics of a fictitious model, based on which,the locations of the jumps and the heights of the plateaus are accurately predicted.

PACS numbers: 03.65.-W,02.30.Rz

# I. INTRODUCTION

Singularities can show up in the time evolution of a physical quantity. A classic example is provided by a model solved rigorously by Stey and Gibberd four decades ago [1]. The model is in the Lee-Friedrichs class [2,3],and is actually a paradigm for quantum decay [4- 6]. It consists of an equaldistant quasi-continuum extending from $- \infty$ to $+ \infty$ ，and an extra discrete level, which couples to all the continuum levels with the same strength.Initialize the system on the discrete level and let it decay into the quasi-continuum.It turns out that the survival probability of the initial state shows cuspS periodically in time. More recently,in the surge of nonequilibrium dynamics of many-body systems [7-11], Heyl et al. have discovered non-analyticities at critical times in the time evolution of some Loschmidt echo related quantities [12].In contrast to the former example, the non-analyticities were sought deliberately by noting the formal similarity between the Loschmidt amplitude （20 $\left. \Psi _ { i } | e ^ { - i H t } | \Psi _ { i } \right.$ and the partition function $\operatorname { T r } ( e ^ { - \beta H } )$ ，and by borrowing notions from equilibrium phase transitions. The singularities were thenlegitimately called dynamical quantum phase transitions. Thereafter,many systems demonstrating this novel type of phase transition in the time domain were found [13-18].

Personally,we have also found some nonsmooth dynamics recently in a very simple scenario [19].The setting is a one-dimensional tight binding chain with the periodic boundary condition,which is arguably the simplest model in solid state physics [2O].Initially a particle is put in some Bloch state with an arbitrary momentum. Then suddenly the potential of some site is changed.In the subsequent evolution，both the survival probability and the reflection probability,which correspond to the particle remaining in its initial state and being momentum reversed,respectively, show cusps periodically. The cusps were explained by exactly solving an idealized model. The mechanism is completely different from those functioning in the examples above.

The singularities invite experimental verifications.Unfortunately,so far this goal is yet to be fulfilled. For the model of Stey and Gibberd,a clean realization is to put a two-level atom in a multi-mode cavity and to position it at an appropriate point [21-24].However,to the best of our knowledge,this has never been attempted experimentally, possibly due to the challenge of the necessity of precisely locating the atom.An alternative scheme is to use the one-dimensional tight binding model [5].But the drawback is that it is confined to the perturbative regime. As for the dynamical quantum phase transition, the essential difficulty is that the central quantity, namely the Loschmidt amplitude for a many-body system,cannot be measured directly. Therefore, the phase transition has to be inferred from some conventional quantities which are experimentally accessible. Some proposals in this spirit do exist [13,14,18] but experimental realization is still missing.

Motivated by this problem,we have reinvestigated the singular dynamics of the Bloch state [19]. From the experimental point of view,to verify the singular dynamics by measuring directly the two probabilities (or populations） is not necessarily an easy task.In many circumstances,it is much easier to measure local quantities.We have thus investigated the time evolution of the probability density of the wave function at anarbitrary site. From the theoretical point of view, this study is also worthy as it provides a real space picture of the dynamics,complementary to the momentum space picture established previously. It turns out that the finding is as interesting as in the momentum space.On a large time scale,the trajectory of the local densityischaracterizedbyplateaus and sudden switches between them. The lengths of the plateaus depend on the site.In particular,the heights of the plateaus are very sensitive to the location of the site;they vary significantly even between adjacent sites. Therefore,we believe measuring the local density is a much more feasible means to verify the singular dynam ics of the particle.

The rest of the paper is organized as follows. First, the cusps and plateaus will be presented side by side in Sec.II, demonstrating that they are two aspects of the same scenario.Then in Sec.III, the plateaus will be explained by invoking the formalism developed previously in Ref.[19] for accounting for the cusps.After that,in Sec.IV,we discuss an experimental system promising for realizing the scenario.Finally,we conclude and discuss the implications of the findings in Sec.V.

# II. SUDDEN JUMPS AND PLATEAUS

The setting is a one-dimensional tight binding chain with the periodic boundary condition.The original Hamiltonian is ( $\hbar = 1$ throughout this paper,and the hopping strength between two adjacent sites is set as the unit of energy)

$$
\hat { H } _ { 0 } = - \sum _ { l = 0 } ^ { N - 1 } ( | l \rangle \langle l + 1 | + | l + 1 \rangle \langle l | ) ,
$$

where $| l \rangle$ denotes the Wannier function at site $\it { l }$ By the periodic boundary condition, $| l + N \rangle = | l \rangle$ . The socalled Bloch states are simultaneously eigenstates of $\hat { H } _ { 0 }$ and eigenstates of the translation operator ${ \hat { T } } | l \rangle = | l + 1 \rangle$ They are indexed by the integer $k$ ,and have the explicit expression of

$$
\langle l | k \rangle = \frac { 1 } { \sqrt { N } } e ^ { i q l } ,
$$

in the real space.Here $q = 2 \pi k / N$ is the so-called wave vector.Apparently, $| k \rangle = | k + N \rangle$ .The corresponding eigenenergies are $\varepsilon ( q ) = - 2 \cos q$ . Like the Wannier functions $| l \rangle$ are the basis vectors in the real space,the Bloch states $| k \rangle$ are the basis vectors in the momentum space.

Now the scenario is as follows.Initially a particle is put in some arbitrary Bloch state $| k _ { i } \rangle$ ,i.e., $| \Psi ( 0 ) \rangle = | k _ { i } \rangle$ = Then at $t ~ = ~ 0$ ，the potential of some site is changed to $U$ suddenly and held fixed afterwards.Without loss of generality, the site is assumed to be the ${ \it l } \ = \ 0$ one. The final Hamiltonian which will govern the evolution of the wave function $| \Psi ( t ) \rangle$ of the particle is then $\hat { H } _ { f } =$ $\hat { H } _ { 0 } + \hat { H } _ { 1 }$ ，with $\hat { H } _ { 1 } = U | 0 \rangle \langle 0 |$ . The characteristic feature of the newly introduced perturbation is that it couples two arbitrary Bloch states with the same strength,i.e.,

$$
g = U / N = \langle k _ { 1 } | \hat { H } _ { 1 } | k _ { 2 } \rangle
$$

regardless of the values of $k _ { 1 , 2 }$ ，as can be easily checked by using the explicit expression of (2).

The question is how does the wave function $| \Psi ( t ) \rangle$ e volve. An intuitive picture is that the particle will be

reflected back and forth between the two groups of Bloch states centered at $\mid + k _ { i } \rangle$ and $\mid - k _ { i } \rangle$ .Therefore,in a previous work [19], the two quantities

$$
\begin{array} { r } { P _ { i } ( t ) = | \langle + k _ { i } | \Psi ( t ) \rangle | ^ { 2 } , } \\ { P _ { r } ( t ) = | \langle - k _ { i } | \Psi ( t ) \rangle | ^ { 2 } , } \end{array}
$$

which are called the survival probability and the reflection probability, respectively,were studied. The finding is that，both $P _ { i }$ and $P _ { r }$ show cusps periodically. Examples are shown in Figs. $\mathrm { 1 ( a ) }$ and $1 ( \mathrm { c } )$ .In Ref. [19], the cusps and even the whole trajectories of $P _ { i , r }$ were explained by identifying and solving an ideal model behind.

Quantities like $P _ { i , r }$ are defined in terms of the momentum space.They are motivated by the Rabi oscillation picture above. From another point of view, the newly introduced barrier at site ${ \mathit { l } } = 0$ will excite scattering waves, which will propagate both forwards and backwards away from the barrier. Because the group velocity of a wave packet on the lattice chain is upper bounded, it will take finite times for the scattering waves to reach a site. Once the scattering waves come back to the barrier, they will generate secondary scattering waves,and so on.Therefore,the wave function $| \Psi ( t ) \rangle$ might exhibit rich temporal and spatial structures.

We have thus investigated numerically the time evolution of the probability density

$$
D _ { l } ( t ) \equiv | \langle l | \Psi ( t ) \rangle | ^ { 2 } = | \Psi _ { l } ( t ) | ^ { 2 }
$$

of the wave function at an arbitrary site $\it { l }$ . Corresponding to Figs. 1(a) and $1 ( \mathrm { c } )$ ，we have Figs.1(b) and 1(d), respectively,where the plateaus and the fast switch between them are the most prominent feature.They are not rigorously plateaus—there are fluctuations. But in each interval, the curve fluctuates apparently around a horizontal line.In Figs.1(a) and $1 ( \mathrm { b } )$ ，where $l = 5 \ll$ $N = 4 0 1$ , it seems that the sudden jumps happen simultaneously with the cusps.However,this is not the case in Figs.1(c) and 1(d),where $l / N \simeq 1 / 4$ .Further numerical examples indicate that the times when the jumps happen depend on the location of the site under observation. This is in line with the scattering wave picture above.

# III. EXPLANATION

Behind the plateaus and sudden jumps is actually the same ideal model which is responsible for the cusps [19]. This ideal model was motivated and justified by an important numerical observation.That is, for a wide range of parameters,only those Bloch states with energies in the vicinity of the energy of the initial Bloch state $| k _ { i } \rangle$ participate significantly in the dynamics.This means two groups of Bloch states,with wave vectors either in the vicinity of $+ q _ { i }$ or $- q _ { i }$ . Here $q _ { i } = 2 \pi k _ { i } / N$ is the wave vector of the initial Bloch state.Figure 2 demonstrates this point very well. There, for a lattice of size $N = 4 0 1$ ,and an initial Bloch state with $k _ { i } = 1 0 0$ ，the population on

P X0X0V P XX  
&0.5 &0.5  
P P  
(b) 3 (d)  
zl()N 2 ）Nm  
0 0  
0 500 1000 1500 2000 2500 0 500 1000 1500$t$ $t$ （204号

0.05$\ : - \ : - \ :$ W=60.040.03 wWwwwwWw川 moL0.020.01% 200 400 600 800 1000$t$ （204号

those Bloch states outside of the two slots of $| k - k _ { i } | \leq W$ and $| k + k _ { i } | \leq W$ is studied.That is,the quantity

$$
P _ { o u t } ^ { ( W ) } ( t ) \equiv \sum _ { \stackrel { | k - k _ { i } | > W } { | k + k _ { i } | > W } } | \langle k | \Psi ( t ) \rangle | ^ { 2 }
$$

is followed.Here $W$ is the cutoff.It is seen that even for $W = 4$ ，the two narrow slots,which cover less than $3 \%$ of the Brillouin zone,almost exhaust the probability.

![](images/2ce3ba6c375e183c9ac51508bc1b71298b3bd630b4f4476650542f0a0377c393.jpg)  
FIG.1.(Color online） Time evolution of the survival probability $P _ { i }$ (solid lines),the reflection probability $P _ { r }$ (dashed lines), and the local probabilitydensity $| \Psi _ { l } | ^ { 2 }$ [see Eqs.(4) and (5) for definition]. The left two panels correspond to one case,while the right two panels to another case.The common parameters are $N = 4 0 1$ ， $k _ { i } = 1 0 0$ , while the rest parameters are $( U , l ) = ( 2 . 5 , 5 )$ in left two panels,and $( U , l ) = ( 2 , 1 0 0 )$ in the right two panels.   
FIG.2.(Color online） Time evolution of the population on those Bloch states outside the two slots of $| k - k _ { i } | \leq W$ and $| k + k _ { i } | \le W$ [see Eq.(6) for definition].The parameters are the same as in the left two panels of Fig.1,i.e., $N = 4 0 1$ ， $k _ { i } = 1 0 0$ ，and $U = 2 . 5$ ：   
FIG.3.(Color online) The red solid curve depicts the dispersion relation $\varepsilon ( q ) = - 2 \cos q$ of the unperturbed Hamiltonian (1).The red solid dots on the curve indicate the Bloch states (2)．The blue hollow dots,which form two linear branches, indicate the levels in the ideal model. Note that while for the realistic model(1),the number of levels is finite and the value of the wave vector $q$ is confined to the interval $[ - \pi , + \pi ]$ ，in the ideal model, the number of levels is infinite and $q$ extends from $- \infty$ to $+ \infty$ ：

Therefore,it is tempting to construct a fictitious model,which resembles the realistic model $\hat { H } _ { f }$ in the two slots but can deviate from it (even significantly) outside. Around the two points of $\pm q _ { i }$ ,the dispersion relation of the unperturbed Hamiltonian(1) can be linearized. The wave vectors are equally spaced with a gap of $\delta = 2 \pi / N$ and the eigenenergies are equally spaced with a gap of $\Delta = \varepsilon ^ { \prime } ( q _ { i } ) \delta = 4 \pi \sin q _ { i } / N$ .Hence,we truncate the realistic spectrum of $\hat { H } _ { 0 }$ by retaining only the two slots and then extend them into two branches of linear spectra $\{ | R _ { n } \rangle \}$ and $\left\{ \left. L _ { n } \right. \right\}$ ， $- \infty < n < + \infty$ . See Fig.3. For $n$ in the vicinity of zero,these states correspond to the Bloch states as

$$
| R _ { n } \rangle  | k _ { i } + n \rangle , | L _ { n } \rangle  | - k _ { i } - n \rangle .
$$

The basis states $\{ | R _ { n } \rangle \}$ and $\{ | L _ { n } \rangle \}$ are eigenstates of the fictitious unperturbed Hamiltonian $\mathcal { \hat { H } } _ { 0 }$

$$
\hat { \mathcal { H } } _ { 0 } | R _ { n } \rangle = n \Delta | R _ { n } \rangle , \quad \hat { \mathcal { H } } _ { 0 } | L _ { n } \rangle = n \Delta | L _ { n } \rangle .
$$

Resembling (3),the fictitious perturbation $\mathcal { \hat { H } } _ { 1 }$ couples two arbitrary states with the same strength

$$
\begin{array} { r l } & { g = \langle R _ { n _ { 1 } } | \hat { \mathcal { H } } _ { 1 } | R _ { n _ { 2 } } \rangle = \langle L _ { n _ { 1 } } | \hat { \mathcal { H } } _ { 1 } | L _ { n _ { 2 } } \rangle } \\ & { \quad = \langle R _ { n _ { 1 } } | \hat { \mathcal { H } } _ { 1 } | L _ { n _ { 2 } } \rangle . } \end{array}
$$

![](images/6538928c2c2a591ccb8a008dbce5c4fc8305ea674cd4555731fa4b6f13ffeb7f.jpg)  
FIG.4. (Color online) Graphs of the functions (a) $\beta ( z )$ ， which is piecewise linear and (b) $\gamma _ { \pm } ( s )$ ， which are piecewise constant See Eqs. (16)-(19) for definition.

Equations (8)and (9)define the fictitious model completely. The idea of its construction is that,the exact details of the Hamiltonian beyond the two slots do not matter much,as the population on those levels is negligible. Therefore,it is free to rectify that part to make analytic calculation possible. This will be justified if the prediction of this fictitious model agrees with the exact results.

It should be stressed that although in the original problem,there are onlya finite number of ( $N$ actually)levels, here in the fictitious model,we have two branches of levels,each consisting of infinite levels.Moreover,in the original model,Bloch states $| k \rangle$ and $| k + N \rangle$ are identified as the same state,while here

$| k _ { i } \rangle = | R _ { 0 } \rangle$ under the control of the fictitious Hamiltonian $\mathcal { \hat { H } } _ { 0 } + \mathcal { \hat { H } } _ { 1 }$ has been solved.In terms of the states with definite parities, $\vert A _ { n } ^ { \pm } \rangle = ( \vert R _ { n } \rangle \pm \vert L _ { n } \rangle ) / \sqrt { 2 }$ , the state at time $t$ is in the form of

$$
\left. \Psi ( t ) \right. = \frac { 1 } { \sqrt { 2 } } \vert A _ { 0 } ^ { - } \rangle + \frac { 1 } { \sqrt { 2 } } \sum _ { n = - \infty } ^ { \infty } \psi _ { n } ( t ) \vert A _ { n } ^ { + } \rangle .
$$

At this point we have to introduce a very important quantity,i.e.,the so-called Heisenberg time $T \equiv 2 \pi / \Delta$ . This is the time which sets the time scale of the dynamics in question. It is actually the period between the cusps in Figs.1(a) and $1 ( \mathrm { c } )$ .For $r T < t < ( r + 1 ) T$ ，where $r$ isa nonnegative integer, the value of $\psi _ { 0 }$ is $( s \equiv t - r T$ ））

$$
\begin{array} { r l } & { | R _ { n _ { 1 } } \rangle \neq | L _ { n _ { 2 } } \rangle , \quad \forall n _ { 1 } , n _ { 2 } , } \\ & { | R _ { n _ { 1 } } \rangle \neq | R _ { n _ { 2 } } \rangle , \quad \mathrm { ~ i f ~ } n _ { 1 } \neq n _ { 2 } , } \\ & { | L _ { n _ { 1 } } \rangle \neq | L _ { n _ { 2 } } \rangle , \quad \mathrm { ~ i f ~ } n _ { 1 } \neq n _ { 2 } . } \end{array}
$$

Because eventually we are to calculate the amplitude of the wave function at an arbitrary site $l$ ,we have to postulate the expressions of the basis states $\{ | R _ { n } \rangle \}$ and $\{ | L _ { n } \rangle \}$ in the real space. This is done simply by generalizing(7) to all $n$ ,and taking (2), i.e.,

$$
\langle l \vert R _ { n } \rangle = \frac { 1 } { \sqrt { N } } \exp ( i 2 \pi ( k _ { i } + n ) l / N ) = \langle l \vert L _ { n } \rangle ^ { * } .
$$

In Ref.[19], the dynamics of the initial state $| \Psi ( 0 ) \rangle =$

$$
\psi _ { 0 } ( t ) = \left( 1 - \frac { i 2 g s } { 1 + i g T } \right) e ^ { - i r \theta } ,
$$

and the value of $\psi _ { n }$ ( $n \neq 0$ )is

$$
\psi _ { n } ( t ) = \frac { 2 g } { ( 1 + i g T ) \Delta } \left( \frac { e ^ { - i n \Delta s } - 1 } { n } \right) e ^ { - i r \theta } .
$$

Here $e ^ { - i \theta } = ( 1 - i g T ) / ( 1 + i g T )$ is a phase factor. In (13), we see that $\psi _ { 0 }$ is a continuous but nonsmooth function of time $t$ .Its trajectory on the complex plane is like the trajectory of a ball inside a circular billiard. This explains the cusps in Figs.1(a) and $1 ( \mathrm { c } )$ ，as $P _ { i , r } = | 1 \pm$ $\psi _ { 0 } | ^ { 2 } / 4$ .Substituting (11)，(13)，and (14) into (12),we have

$$
\begin{array} { l } { { \sqrt { N } \langle l | \Psi ( t ) \rangle = i \sin q _ { i } l + e ^ { - i r \theta } \biggl [ \cos q _ { i } l + \displaystyle \frac { g } { ( 1 + i g T ) \Delta } \sum _ { n = 1 } ^ { \infty } \frac { e ^ { - i n \Delta s } - 1 } { n } \left( e ^ { i q _ { i } l + i n \delta l } + e ^ { - i q _ { i } l - i n \delta l } \right) \biggr ] } } \\ { { = i \sin q _ { i } l + e ^ { - i r \theta } \biggl [ \cos q _ { i } l + \displaystyle \frac { i g } { ( 1 + i g T ) \Delta } \biggl ( e ^ { i q _ { i } l } \bigl ( \beta ( \delta l - \Delta s ) - \beta ( \delta l ) - \Delta s \bigr ) } } \\ { { + e ^ { - i q _ { i } l } \bigl ( \beta ( - \delta l - \Delta s ) - \beta ( - \delta l ) - \Delta s \bigr ) \biggr ) \biggr ] } } \\ { { = i \sin q _ { i } l + e ^ { - i r \theta } \biggl [ \cos q _ { i } l + \displaystyle \frac { i g } { ( 1 + i g T ) \Delta } \left( e ^ { i q _ { i } l } \gamma _ { + } ( s ) + e ^ { - i q _ { i } l } \gamma _ { - } ( s ) \right) \biggr ] . } } \end{array}
$$

Inthe second line we have defined the function

$$
\beta ( z ) = 2 \sum _ { n = 1 } ^ { \infty } \frac { \sin n z } { n } .
$$

It is apparently periodic with a period of $2 \pi$ . In Ref. [25],

![](images/7f684c2ecf63f1388ce314bf72c754608c714e89bcd099acd889a2715faceb9a.jpg)  
FIG.5.(Coloronline)Comparisonbetwen theanalytic predictions (reddashed ines）by(15)andthe numericalexact results (blue solid lines） for the local probability density. The common parameters are $N = 4 0 1$ and $U = 1$ . The rest parameters are shown in each panel. Panels (a) and(b) demonstrate that eve) between two adjacent sites,the evolution trajectories of the local probability densities can b6 erydifferent.Panel (d)shows that la ：tir when the plateaus are not well shaped,the analytic predictions still capture the trend ( f evolution of $| \Psi _ { l } | ^ { 2 }$ very well. Also note how the location of the observed site, namely the value of $l$ ,infuences the lengths of the plateaus by comparing the upper panels with the lower ones.

it is calculated to be [see Fig.4(a) for its graph]

$$
\beta ( z ) = \left\{ { \begin{array} { l l } { - ( z - 2 \pi \lfloor z / 2 \pi \rfloor - \pi ) , } & { z \neq 2 \pi r , } \\ { 0 , } & { z = 2 \pi r , } \end{array} } \right.
$$

where $\lfloor \cdot \rfloor$ is the floor function.In the third line,we have defined the functions

$$
\begin{array} { r } { \gamma _ { + } ( s ) = \beta ( + \delta l - \Delta s ) - \beta ( + \delta l ) - \Delta s , } \\ { \gamma _ { - } ( s ) = \beta ( - \delta l - \Delta s ) - \beta ( - \delta l ) - \Delta s , } \end{array}
$$

which are defined on the interval $[ 0 , T ]$ . Using (17),it is easy to determine [see Fig.4(b) for their graphs]

$$
\begin{array} { r l } & { \gamma _ { + } ( s ) = \left\{ \begin{array} { l l } { 0 , } & { 0 < s < s _ { c } , } \\ { - 2 \pi , } & { s _ { c } < s < T , } \end{array} \right. } \\ & { \gamma _ { - } ( s ) = \left\{ \begin{array} { l l } { 0 , } & { 0 < s < T - s _ { c } , } \\ { - 2 \pi , } & { T - s _ { c } < s < T , } \end{array} \right. } \end{array}
$$

where $s _ { c } = \delta l / \Delta$ . The physical meaning of $s _ { c }$ is the time needed for a wave packet,whose wave vector is centered at ,to go from the barrier to the site $\it { l }$ in the forward $q _ { i }$ direction.The reason is simply that the group velocity of the wave packet is exactly $v = \varepsilon ^ { \prime } ( q _ { i } ) = \Delta / \delta$ .Similarly,the Heisenberg time $T = 2 \pi / \Delta = N / v$ is just the time needed for the wave packet to complete the loop and return to the barrier. The time $T - s _ { c }$ in(19b）is then simply the time needed for a wave packet with wave vector $- q _ { i }$ to go from the barrier to the site $\it { l }$ ：

Equation(15）is our central result.We see that the amplitude $\Psi _ { l } ( t )$ jumps at $r T \pm s _ { c }$ .Between the jumps, the amplitude is a constant.Now we can compare the predictions of(15) and the numerical exact results. This is done in Fig.5.We see that the analytic predictions based on the fictitious model (red dashed lines） agree with the numerical results (blue solid lines） very well. Generally,not only the times when the jumps occur, but also the heights of the plateaus,are accurately predicted by(15). An important prediction of(15）is that，the value of $| \Psi _ { l } ( t ) | ^ { 2 }$ is very sensitive to the site index $\it { l }$ ，and this is vividly demonstrated in Figs. 5(a) and 5(b).

We should note the regularity of the time evolution of $| \Psi _ { l } | ^ { 2 }$ . The expression(15） contains two parts. The first part, $i \sin q _ { i } l$ ，is time independent. The second part is time dependent,but it factorizes into a part containing solely $\boldsymbol { r }$ and a part containing solely $s$ . Hence, $\Psi _ { l } ( r T + s )$ as a function of $r$ is of the form $a + b e ^ { - i r \theta }$ ，where $a$ and $b$ are constants.Its modulus squared is then a sinusoidal function of $r$ . This harmonic oscillation feature is easily perceived in Figs.1 and 5.In particular,when $\theta / \pi$ isa rational number,as in Fig.1(d),where $\theta = \pi / 2$ ， $\vert \Psi _ { l } ( r T +$ $s ) | ^ { 2 }$ is a periodic function of $r$ ：

The times when the jumps happen are in accord with the scattering picture below. As illustrated by Fig.6, the barrier generates forward scattering waves with wave vectors $q \simeq + q _ { i }$ ，and back scattering waves with wave vectors $q \simeq - q _ { i }$ .Their wave fronts move at a constant velocity of

![](images/f9ddbcb6bcfc7c5649adf1458f27795cdd730956b7db39b9bf7a34b70b2e3974.jpg)  
FIG.6.(Color online） Nine equal-distant snapshots of the probability distribution of the wave function in the time interval $[ 0 , T ]$ .For clarity, from bottom to top,the $j$ th curve is up shifted by $2 ( j - 1 )$ . The parameters are $N = 4 0 1$ ， $k _ { i } = 1 0 0$ 5 and $U = 1$ .The wave vector of the initial Bloch state is then （20 $q _ { i } = 2 \pi k _ { i } / N \simeq \pi / 2$ ．The dashed line indicates the motion of the back scattering wave front with a constant velocity of $v = 2 \sin q _ { i } \simeq 2$ ．The forward scattering wave front is also clearly visible.

$$
v = \frac { \partial \varepsilon } { \partial q } | _ { q = q _ { i } } = \frac { \Delta } { \delta } = 2 \sin q _ { i }
$$

forwards or backwards.It takes them exactly the time

$$
\frac { N } { v } = \frac { N } { \Delta / \delta } = \frac { 2 \pi } { \Delta } = T
$$

to return to the barrier. Then the scattering waves will generate secondary scattering waves which also travel at the velocities $\pm v$ along the lattice.The times when the scattering waves,or the secondary ones,pass by the site （204号 $\it { l }$ ,are just $r T \pm s _ { c }$ , the times when the jumps happen.

In Fig.6,snapshots of the probability distribution of the wave function in the first period $[ 0 , T ]$ are shown. In the four curves at the bottom, the steep forward moving wave front is clearly visible. For a fixed site $l$ ，before the wave front reaches it,the value of $| \Psi _ { l } | ^ { 2 }$ is almost stationary at $1 / N$ ；when the wave front crosses it,the value of $| \Psi _ { l } | ^ { 2 }$ experiences a swift change.

# IV. EXPERIMENTALREALIZATION

Like the van Hove singularity in the density of states of a solid [26-28], here the singularity in the dynamics is also worth experimental verifications.

A promising approach to observing the sudden jumps and plateaus is to use coupled optical waveguides [29]. Because of the quantum-optical correspondence,many coherent quantum phenomena have been successfully simulated using photonic guiding structures carefully engineered.In particular, some interesting phenomena with the tight binding model as the setting，such as the dynamical localization [3O,31] and the Bloch oscillation [32-34],have been realized.

In our case,the periodic boundary condition can be implemented by arranging the $N$ waveguides in a circular loop,and the initial Bloch state can be realized by carefully engineering the phases of the input laser beams,while the defect potential can be achieved by changing the refractive index of one of the waveguides,which can be done in several different ways [29]. The primary potential difficulty might come from the large time scale involved,which is linearly proportional to the lattice size $N$ .In contrast,the time scales of the dynamical localization and the Bloch oscillation are independent of $N$ ：

# V.CONCLUSIONS AND DISCUSSIONS

We have reinvestigated the single-site quench dynamics of a Bloch state in a one-dimensional tight binding lattice,which was previously studied by us in Ref. [19]. The motivation was on the one hand to get a complementary picture of the dynamics from another perspective, and on the other hand to find a quantity which is more convenient for measurement.

We have thus tracked the evolution of the probability density of the wave function at an arbitrary site,which is probably the quantity most readily measurable.It turns out to jump constantly, from plateau to plateau.In other words,its time development is not monotonic,but well structured.The times when the jumps happen, the durations as well as the heights of the plateaus,can all be accurately predicted by a fictitious model.Due to the nonlinearity of the realistic spectrum,and the finiteness of the number of levels in the realistic model,there are details beyond the predictions of the fictitious model,but the overall trend is well guided by its analytic predictions. The dependence of the times of the jumps on the site under consideration supports the scattering wave picture. Namely, the probability density jumps each time when a scattering wave passes by.

From the point of view of thermalization or equilibration,the model in question never thermalizes or equilibrates.First,in the figures,we can see that each time after the jump,the amplitude of fluctuation shrinks with time—it is equilibrating.However, this process is only to be interrupted by the next jump.The processes of jump and equilibration then alternate.Second,it is observed that even between two neighboring sites,the probability densities have completely different trajectories and never merge together.This means that the wave function will never become“even”across the lattice.Hence,the real space evidences corroborate the opinion that the dynamics of the model is very regular and non-chaotic.

dation under grant number 2O16J05004.

# ACKNOWLEDGMENTS

We are grateful to J.Ye for helpful discussions. This work is supported by the Fujian Provincial Science Foun

[1] G.C. Stey and R.W.Gibberd,Physica (Amsterdam) 60,1 (1972).   
[2] K.O.Friedrichs,Commun.Pure Appl.Math．1,361 (1948).   
[3] T.D.Lee,Phys.Rev.95,1329 (1954).   
[4] C. Cohen-Tannoudji, J. Dupont-Roc, and G. Grynberg, Atom-Photon Interactions:Basic Processes and Applications(John-Wiley & Sons,New York,1992).   
[5]J.M.Zhang and M.Haque,ScienceOpen Research 2014 (DOI:10.14293/S2199-1006.1.SOR-PHYS.A2CEM4.v1). [6]J.MZhang,arXiv:1604.06916.   
[7]M.Greiner,O.Mandel,T.Esslinger,T.Hänsch,and I. Bloch,Nature (London) 419,51 (2002).   
[8] T.Kinoshita, T.Wenger,and D.Weiss,Nature (London) 440,900 (2006).   
[9] M.Rigol,V.Dunjko,and M. Olshanii,Nature (London) 452,854 (2008).   
[10]A.Polkovnikov,K.Sengupta,A. Silva,and M.Vengalattore,Rev.Mod.Phys.83,863(2011).   
[11]J.Eisert，M. Friesdorf,and C.Gogolin,Nat.Phys.11, 124 (2015).   
[12]M.Heyl,A.Polkovnikov，and S.Kehrein，Phys.Rev. Lett.110,135704(2013).   
[13] M.Heyl, Phys.Rev. Lett.113,205701 (2014).   
[14] M.Heyl, Phys.Rev.Lett.115,140602 (2015).   
[15] C. Karrasch and D. Schuricht, Phys. Rev. B 87, 195104 (2013).   
[16] S. Sharma, U. Divakaran,A. Polkovnikov,and A. Dutta, arXiv:1601.01637.   
[17] U. Divakaran， S. Sharma, and A. Dutta, arXiv:1601.04851.   
[18] Z. Huang and A.V. Balatsky, arXiv:1604.04698.   
[19] J.M. Zhang and H. T.Yang,arXiv:1601.03569.   
[20] N.W.Ashcroft and N.D.Mermin,Solid State Physics (Harcourt,New York,1976).   
[21] M. Ligare and S.Becker,Am.J.Phys.63,788 (1995).   
[22] M.Ligare and R. Oliveri,Am. J.Phys.70,58 (2002).   
[23]J.Parker and C.R.Stroud,Jr.,Phys.Rev.A 35,4226 (1987).   
[24] H. Giessen, J. D. Berger, G. Mohs, P. Meystre,and S.F. Yelin,Phys.Rev.A 53,2816 (1996).   
[25]R.Courant and F.John，Introduction to Calculus and Analysis I (Springer,New York,1989),pp.592.   
[26]L.Van Hove,Phys.Rev.89,1189 (1953).   
[27]F.Bassani and G.Pastori-Parravicini,Electronic States and Optical Transitions in Solids (Pergamon Press,Oxford,1975).   
[28]G.Li,A.Luican,J.M.B.Lopes Dos Santos,A.H. Castro Neto,A.Reina, J.Kong,E.Y.Andrei,Nat.Phys.6,109 (2010).   
[29] S.Longhi,Laser Photon.Rev.3,243 (2009).   
[30] D.H. Dunlap and V. M. Kenkre,Phys.Rev.B 34,3625 (1986).   
[31] S.Longhi,MMarangoni,M.Lobino,R.Ramponi,P. Laporta，E.Cianci，and V.Foglietti，Phys.Rev.Lett. 96,243901 (2006).   
[32]R.Morandotti,U.Peschel,J.S.Aitchison,H.S.Eisenberg，and Y.Silberberg，Phys.Rev.Lett.83，4756 (1999).   
[33] T.Pertsch,P.Dannberg,W.Elflein,A.Bräuer,and F. Lederer,Phys.Rev.Lett.83,4752(1999).   
[34]N.Chiodo,G.Della Valle,R.Osellame,S.Longhi,G. Cerullo,R.Ramponi, P.Laporta,and U.Morgner, Opt. Lett.31,1651 (2006).