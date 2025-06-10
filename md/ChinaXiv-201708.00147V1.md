# Holography and Entanglement in Flat Spacetime

Wei Li (李 微）and Tadashi Takayanagi (高柳匡) Institute for the Physics and Mathematics of the Universe (IPMU), University of Tokyo，Kashiwa，Chiba 277-8582，Japan (Dated: April 4,2011)

We propose a holographic correspondence of the fat spacetime based on the behavior of the entanglement entropy and the correlation functions.The holographic dual theory turns out to be highly nonlocal.We argue that after most part of the space is traced out,the reduced density matrix gives the maximal entropy and the correlation functions become trivial.We present a toy model for this holographic dual using a nonlocal scalar field theory that reproduces the same property of the entanglement entropy. Our conjecture is consistent with the entropy of Schwarzschild black holes in asymptotically fat spacetimes.

Introduction. One of the most powerful tools to study quantum gravity is the holographic duality conjecture: the quantum gravity in spacetime $\mathcal { M }$ is equivalent to a quantum field theory living on the boundary $\partial \mathcal { M }$ [1].In particular, the quantum gravity in anti-de Sitter space has been well developed via the AdS/CFT correspondence [2] from string theory. However,to understand our universe,we need to study quantum gravity in other spacetimes such as flat space,de Sitter space,and the big bang spacetime. The purpose of this Letter is to investigate holography in flat spacetime and to present a consistent outline of its basic properties and mechanism. We will focus on the Euclidean flat spacetime $\mathbb { R } ^ { d + 1 }$ since the Euclidean formulation is often simpler and better defined than the Lorentzian version,as in AdS/CFT [3].

In polar coordinates, the metric of the Euclidean spacetime $\mathbb { R } ^ { d + 1 }$ is

$$
d s _ { \mathbb { R } ^ { d + 1 } } ^ { 2 } = d \rho ^ { 2 } + \rho ^ { 2 } d s _ { S ^ { d } } ^ { 2 }
$$

The holographic principle dictates that the boundary dual theory of the gravity in $\mathbb { R } ^ { d + 1 }$ lives on the unit-radius sphere $S ^ { d }$ at $\rho = \rho _ { \infty }$ ，where $\rho _ { \infty }$ is the bulk cutoff radius and is related to the UV cutoff in boundary field theory (as in AdS/CFT);we take the limit $\rho _ { \infty } \to \infty$ ：

The assumptions we adopt in this Letter are the following:(1) the dual field theory allows a path-integral formulation even if it is nonlocal; (2) the bulk-to-boundary correspondence holds,i.e., the partition function of gravity in $\mathbb { R } ^ { d + 1 }$ equals that of holographic dual theory on $S ^ { d }$ [3]． In Lorentzian holography, $S ^ { d }$ is replaced by the $d$ dimensional de Sitter space (see [4,5] for earlier studies). See [6-8] for other approaches to holography in flat space. Holographic entanglement entropy. When a quantum system is divided into two subsystems $A$ and $B$ ， the von Neumann entropy $S _ { A } = - \mathrm { T r } [ \rho _ { A } \mathrm { l o g } \rho _ { A } ]$ (where $\rho _ { A }$ is the reduced density matrix after tracing out $B$ ） is called the entanglement entropy of the subsystem $A$ The scaling behavior and certain universal coefficients of the entanglement entropy encode important information on the degrees of freedom and nonlocal correlations of the system.Furthermore,the entanglement entropy is a general-purpose quantity since it can be defined in any quantum many-body system that allows a path-integral formalism — even in nonlocal field theories,as will be shown later. Thus the entanglement entropy is particularly useful when we know little else about the holographic dual of a given gravity theory as in our case.

On the gravity side,there is a general prescription to compute the entanglement entropy holographically: when the $d$ -dimensional boundary system is divided into two parts $A$ and $B$ ，the holographic entanglement entropy of the subsystem $A$ is given by the formula [9]

$$
S _ { A } ^ { h o l . } = \frac { \mathrm { a r e a } ( \gamma _ { A } ) } { 4 G _ { N } ^ { ( d + 1 ) } } ,
$$

where $\operatorname { a r e a } ( \gamma _ { A } )$ is the area of the minimal surface $\gamma _ { A }$ that lies inside the $( d + 1 )$ -dimensional bulk and borders on the boundary $\partial A$ of the subsystem $A$ ； $G _ { N } ^ { ( d + 1 ) }$ is the $( d + 1 )$ -dimensional Newton's constant.

Now we apply (2） to compute the holographic entanglement entropy of a Euclidean field theory living on the boundary of $\mathbb { R } ^ { d + 1 }$ . The metric of the boundary sphere $S ^ { d }$ B $d s _ { S ^ { d } } ^ { 2 } = d \tau ^ { 2 } + \cos ^ { 2 } \tau d \Omega _ { d - 1 } ^ { 2 }$ where $\tau \in [ - \frac { \pi } { 2 } , \frac { \pi } { 2 } ]$ 3e of constant $\tau$ is $S ^ { d - 1 }$ ， whose metric can be written as $d \Omega _ { d - 1 } ^ { 2 } = d \theta ^ { 2 } + \sin ^ { 2 } \theta d \Omega _ { d - 2 } ^ { 2 }$ . We divide the spatial slice $S ^ { d - 1 }$ at $\tau \ = \ \tau _ { 0 }$ into two spherical caps $A$ and $B$ using a subsphere $S ^ { d - 2 }$ given by $\theta \ : = \ : \theta _ { 0 }$ .The radius of this $S ^ { d - 2 }$ in $\mathbb { R } ^ { d + 1 }$ is $\begin{array} { r } { \rho _ { \infty } \cos \tau _ { 0 } \sin \theta _ { 0 } \equiv \rho _ { \infty } \sin \frac { \alpha } { 2 } } \end{array}$ ，where $\alpha \in [ 0 , 2 \pi ]$ and $\rho _ { \infty } \alpha$ is the geodesic distance in $S ^ { d }$ of antipodal points of $S ^ { d - 2 }$ (see Fig.1).

The holographic entanglement entropy is

$$
S _ { A } ^ { h o l . } = S _ { B } ^ { h o l . } = \frac { \pi ^ { \frac { d - 1 } { 2 } } } { \Gamma ( \frac { d + 1 } { 2 } ) } \cdot \frac { \rho _ { \infty } ^ { d - 1 } \left( \sin \frac { \alpha } { 2 } \right) ^ { d - 1 } } { 4 G _ { N } ^ { ( d + 1 ) } } .
$$

First we notice that for a small subsystem A ( $\alpha \ll 1$ ） (3)approaches $A$ 's volume instead of its area. Moreover, $S _ { A }$ with generic $\alpha$ is extensive since it is proportional to the spatial volume of the full boundary system (see also [10]).These two facts are in sharp contrast with the behavior both in local field theories [11] and in AdS/CFT. In a local field theory at its ground state,the leading divergence of the entanglement entropy is always proportional to the surface area of the subsystem (so-called “area law"） [11]. The entropy becomes extensive only when the system is in highly excited states with energy around the UV cutoff [12,13].However, the holographic dual of the gravity in flat space should not be restricted to any particular type of states in the boundary theory since this “volume law” applies to the holographic entanglement entropy of any asymptotically flat space. Taking all of these into account,we conjecture that the holographic dual is described by a certain nonlocal field theory. Below we will construct one such example based on the scalar field theory.

![](images/2ef71d7a51aedd59e9a4f5cdde5c17de64769d00c01de29972cfa01671fd86c6.jpg)  
FIG.1.The geometric computation of the entanglement entropy $S _ { A }$ in the flat space holography.

Also note that in the $\alpha  0$ limit $S _ { A }$ saturates the holographic bound [14] (here given by the volume of $A$ in $S ^ { d }$ ). Therefore although our total system is in a pure state as evidenced by $S _ { A } ~ = ~ S _ { B }$ ，an infinitesimal subsystem $A$ has a density matrix $\rho _ { A }$ with maximal entropy $\langle = \log d i m \mathcal { H } _ { \mathcal { A } }$ where $\mathcal { H } _ { \mathcal { A } }$ is the Hilbert space of $A$ ). Namely,an infinitesimal subsystem $A$ is maximally entangled with its complement $B$ ：

Let us consider a generic (not necessarily local) free scalar field theory on $S ^ { d }$ defined by the action

$$
S _ { b o u n d a r y } = \int d \Omega _ { d } \left[ \phi \cdot f ( - \Delta ) \cdot \phi \right] ,
$$

where $\Delta$ is the Laplacian on $S ^ { d }$ and $f ( x )$ is a smooth function (see [15] for an analogous computation in $\mathbb { R } ^ { d }$ ）

To see the extensive behavior of the entanglement en tropy,it suffices to consider the simplest configuration with $\alpha = \pi$ . In this case, $S _ { A }$ can be expressed as follows (similar to the geometric entropy in [16]):

$$
S _ { A } = \frac { \partial } { \partial N } \log \frac { Z _ { N } } { ( Z _ { 1 } ) ^ { 1 / N } } \Bigg | _ { N = 1 } ,
$$

where $Z _ { N }$ is the partition function of(4)on the orbifold $S ^ { d } / \mathbb { Z } _ { N }$ ; the $\mathbb { Z } _ { N }$ action is defined by a $\textstyle { \frac { 2 \pi } { N } }$ rotation of $S ^ { d }$ ： The partition function can be evaluated via Schwinger reta （204号 $\epsilon$ is related to the UV cutoff in the field theory.

Spherical harmonics on $S ^ { d }$ are labeled by angular momenta $( l , m _ { 1 } , \ldots , m _ { d - 1 } )$ ，which range as $l \ge m _ { 1 } \ge . . . \ge$ （204号 $m _ { d - 2 } \geq 0$ and $m _ { d - 2 } \geq | m _ { d - 1 } |$ . The eigenvalues of the Laplacian $\Delta$ are $- l ( l + d - 1 )$ . The $\mathbb { Z } _ { N }$ orbifolding acts by multiplying a phase factor 2πimd-1. The relevant trace of kernel $\begin{array} { r } { T r \equiv \mathrm { T r } _ { ( N ) } e ^ { - s f ( - \Delta ) } - \frac { 1 } { N } \mathrm { T r } _ { ( 1 ) } e ^ { - s f ( - \Delta ) } } \end{array}$ is then:

$$
T r = \frac { 1 } { N } \sum _ { k = 1 } ^ { N - 1 } \sum _ { l } e ^ { - s f ( l ( l + d - 1 ) ) } g \left( l , d , \frac { k } { N } \right) ,
$$

where g(ld,）=∑{m)e2imd-1 incorporates the sum over all magnetic angular momenta $m _ { i }$ and is computed to be

$$
g ( l , d , { \frac { k } { N } } ) = \sum _ { n = 0 } ^ { l } { \binom { n + d - 3 } { d - 3 } } \sum _ { m = - ( l - n ) } ^ { l - n } e ^ { 2 \pi i { \frac { k } { N } } m }
$$

for $d = 2$ ,the binomial is $\delta _ { n , 0 }$

Lower dimensional spheres have more compact results: $\begin{array} { r } { g ( l , 2 , \frac { k } { N } ) = \frac { \sin { [ \frac { \pi k } { N } ( 2 l + 1 ) ] } } { \sin { ( \frac { \pi k } { N } ) } } } \end{array}$ and $\begin{array} { r } { g ( l , 3 , \frac { k } { N } ) = \left( \frac { \sin { [ \frac { \pi k } { N } ( l + 1 ) ] } } { \sin { ( \frac { \pi k } { N } ) } } \right) ^ { \because } } \end{array}$ and need to be treated separately.

For higher dimensional spheres ( $d \geq 4$ ， $\begin{array} { r } { g ( l , d , \frac { k } { N } ) } \end{array}$ is a degree $( d - 3 )$ (pseudo-)polynomial of $\it { l }$ with leading term $\frac { l ^ { d - 3 } } { 2 \cdot ( d - 3 ) ! \cdot \sin ^ { 2 } { \frac { \pi k } { N } } }$ .Summing over all twisted sectors using $\begin{array} { r } { \sum _ { k = 1 } ^ { N - 1 } \sin ^ { - 2 } { \frac { \pi k } { N } } = { \frac { 1 } { 3 } } ( N ^ { 2 } - 1 ) } \end{array}$ and then applying $\begin{array} { r } { \operatorname* { l i m } _ { N \to 1 } \frac { \partial } { \partial N } } \end{array}$ ， we obtain the leading divergence of the entanglement entropy:

$$
S _ { A } ^ { d \geq 4 } = { \frac { 1 } { 6 } } \int _ { \epsilon } ^ { \infty } { \frac { d s } { s } } \sum _ { l = 0 } ^ { \infty } { \frac { l ^ { d - 3 } } { ( d - 3 ) ! } } e ^ { - s f ( l ( l + d - 1 ) ) } + \dots . . . .
$$

Now we impose the UV cutoff. For $S ^ { d }$ with radius $L$ （204号 and lattice spacing $a$ ,the azimuthal angular momentum $\it { l }$ has an upper bound given by $\begin{array} { r } { l _ { m a x } = { \frac { L } { a } } } \end{array}$ . This translates into a lower bound on the integration parameter $s$ ： $s \geq$ $\begin{array} { r } { \epsilon = \frac { 1 } { f ( l _ { m a x } ^ { 2 } ) } } \end{array}$

First,let us look at actions with $f ( x ) = x ^ { p }$ ；in particular, $p = 1$ gives the standard massless scalar. The leading divergence of the entanglement entropy is

$$
S _ { A } = \frac { \Gamma ( \frac { d - 2 } { 2 p } ) } { 6 \cdot ( d - 2 ) ! } \left( \frac { \cal L } { a } \right) ^ { d - 2 } .
$$

Although this result is obtained for $d \geq 4$ ，an exact computation for $d = 2 , 3$ shows that it actually holds for all $d \geq 2$ . In particular for $d = 2$ ，(9） gives $\begin{array} { r } { S _ { A } = \frac { p } { 3 } \log \frac { L } { a } } \end{array}$ (after an infinite constant term is dropped). Therefore all theories with $f ( x ) = x ^ { p }$ are local and obey the area law.

Now we make the theory nonlocal by choosing $f ( x ) =$ （20 $e ^ { x ^ { q } }$ For all $S ^ { d }$ with $d \geq 2$ , the leading divergence becomes

$$
S _ { A } = { \frac { 2 q } { 6 \cdot ( d - 2 ) ! \cdot ( d - 2 + 2 q ) } } \left( \frac { L } { a } \right) ^ { d - 2 + 2 q } .
$$

Therefore $S _ { A }$ obeys the volume law when $\begin{array} { r } { q = \frac { 1 } { 2 } } \end{array}$ , in any dimension $d$ .To summarize,we find that a nonlocal scalar field theory defined by the action

$$
S _ { b o u n d a r y } = \int d \Omega _ { d } \left[ \phi \cdot e ^ { \sqrt { - \Delta } } \cdot \phi \right] ,
$$

has entanglement entropies that exhibit the volume law.

The bulk Bekenstein bound requires that the maximal boundary statistical entropy is bounded by the volume law. We have computed, for the ground state in the Euclidean theory on $S ^ { d }$ , the entanglement entropy when exactly half of the system is traced out. This directly translates into the statistical entropy of the Minkowski theory on $d S _ { d }$ , thus the boundary statistical entropy for the ground state satisfies the volume law.

For thermal states we simply replace the flat space with Schwarzschild black holes. The entanglement entropy computed holographically still obeys the volume law.Indeed,since the volume law behavior stems from the nonlocal nature of the boundary theory, it cannot be changed by simply exciting the system. Hence the maximal boundary statistical entropy is bounded by the volume law,which ensures the bulkBekenstein bound.

We have used a free scalar theory to show that a nonlocal theory is needed to realize the volume law for entanglement entropies. The full holographic dual of flat space is likely to contain more felds and to be stronglyinteracting. As in AdS/CFT and in standard entanglement entropy computations,adding more fields and turning on local interactions do not alter the scaling behavior of the entanglement entropy;we expect that appropriate nonlocal interactions preserve the volume law as well.

We speculate that the holographic dual of the flat space is given by the nonlocal generalization of a non-abelian gauge theory on $S ^ { d }$ : the theory now has a nonlocal kinetic term like (11). Indeed,a similar nonlocal structure is known to appear in open string field theory (see e.g.[17]). Moreover,the unconventional kinetic term in (11) is natural when we rewrite our flat space metric into d² + (logr)2dΩ² and draw a paralel with AdS metric $\begin{array} { r } { d s ^ { 2 } = \frac { d r ^ { 2 } } { r ^ { 2 } } + r ^ { 2 } d \vec { x } ^ { 2 } } \end{array}$ :the boundarykinetic terms of these two spaces scale the same since $e ^ { \partial _ { \Omega } } \sim r \sim \partial _ { x }$ ： This comparison also shows that $\rho = \log r$ should be regarded as the energy scale, hence $\rho _ { \infty }$ is the UV energy cutoff — corresponding to the UV cutoff from the viewpoint of open string theory [18]. This argument can be seen as a logarithmic generalization of the holographic correspondence of Lifshitz-like fixed points introduced in [19].

Holographic correlation functions.Another important quantity in establishing the holography is the correlation function. Now we extend the bulk-to-boundary procedure [3] to the flat space(1) and compute its holographic correlation functions.

Consider a scalar field theory in the bulk:

$$
S _ { b u l k } = \frac { 1 } { 3 2 \pi G _ { N } ^ { ( d + 1 ) } } \int d ^ { d + 1 } x \sqrt { g } ( \partial _ { \mu } \phi \partial ^ { \mu } \phi + M ^ { 2 } \phi ^ { 2 } ) .
$$

UndertheDirichletboundarycondition, the boundary/bulk correspondenceis(eS dldΦ·O) $\begin{array} { r l } { \langle e ^ { \int d \Omega _ { d } \Phi \cdot \hat { O } } \rangle _ { S ^ { d } } } & { { } = } \end{array}$ $Z _ { \mathbb { R } ^ { d + 1 } } [ \phi ( \rho _ { \infty } , \Omega ) = \Phi ( \Omega ) ]$ ，where the left-hand side is the generating functional of correlation functions on the boundary $S ^ { d }$ and the right-hand side is the bulk partition function under the Dirichlet boundary condition; $\Phi$ is the boundary scalar field,which sources the operator $\hat { O }$ in $S ^ { d }$ .In the classical limit,

$Z _ { \mathbb { R } ^ { d + 1 } } [ \Phi ] \ \sim \ \exp { \left( - S _ { b u l k } ^ { o n - s h e l l } [ \Phi ] \right) }$ .Since the boundary Newton's constant is $\begin{array} { r } { G _ { N } ^ { ( d ) } ~ = ~ \frac { G _ { N } ^ { ( d + 1 ) } } { ( \rho _ { \infty } ) ^ { d - 1 } } } \end{array}$ a-r, in the limit of （204 $\rho _ { \infty } \to \infty$ the boundary theory decouples from gravity.

For the massless scalar, $\phi ( \rho , \Omega )$ can be solved using the bulk Dirichlet Green's function.The on-shell action gives the boundary two-point function:

$$
\langle \hat { \cal O } ( \Omega _ { 1 } ) \hat { \cal O } ( \Omega _ { 2 } ) \rangle = { \frac { 1 } { 2 ^ { { \frac { d + 9 } { 2 } } } \pi \mathcal { A } _ { d } } } \cdot { \frac { \rho _ { \infty } ^ { d - 1 } } { G _ { N } ^ { ( d + 1 ) } } } { \frac { 1 } { ( 1 - \cos \theta ) ^ { \frac { d + 1 } { 2 } } } }
$$

where $\cos \theta = \vec { \Omega } _ { 1 } \cdot \vec { \Omega } _ { 2 }$ and $\mathbf { \mathcal { A } } _ { d }$ is the area of the unit sphere $S ^ { d }$ .This agrees with the analysis in [20], though our interpretations are slightly different.Since(13) contains onlya divergent term，the physical two-point function vanishes after nonlocal boundary counterterms are added to cancel the divergence. Nonlocal counterterms were also used in the holography of NS5-branes [4, 21].

For the massive scalar,we decompose the boundary field as: $\begin{array} { r } { \Phi ( \Omega ) = \sum _ { l , \vec { m } } c _ { l , \vec { m } } Y _ { l , \vec { m } } ( \Omega ) } \end{array}$ ,where $Y _ { l , \vec { m } } ( \Omega )$ are the orthonormal spherical harmonics on $S ^ { d }$ . Then the same bulk-to-boundary procedure produces the boundary twopoint function:

$$
\langle \hat { O } ( \Omega _ { 1 } ) \hat { O } ( \Omega _ { 2 } ) \rangle = \frac { \rho _ { \infty } ^ { d } } { 3 2 \pi G _ { N } ^ { ( d + 1 ) } } \sum _ { l , \vec { m } } F _ { l } ( \rho _ { \infty } ) \bar { Y } _ { l , \vec { m } } ( \Omega _ { 1 } ) Y _ { l , \vec { m } } ( \Omega _ { 2 } )
$$

where $F _ { l } ( \rho ) \equiv \partial _ { \rho } \log \Big ( \rho ^ { \frac { 1 - d } { 2 } } I _ { l + \frac { d - 1 } { 2 } } ( M \rho ) \Big )$ and $I _ { \nu } ( z )$ is the modifiedBesselfunctionofthefirstkind.

$\rho _ { \infty } ^ { d } F _ { l } ( \rho _ { \infty } )$ as a polynomial of $\rho _ { \infty }$ has a nonzero constant term，which is a degree $\left[ \frac { d } { 2 } \right]$ polynomial of $l ( l + \underline { { { d } } } \mathrm { ~ - ~ } 1 )$ (eigenvalue of $- \Delta$ ).Using the identity $\begin{array} { r } { \sum _ { l , \vec { m } } Y _ { l \vec { m } } ( \Omega _ { 1 } ) Y _ { l \vec { m } } ( \Omega _ { 2 } ) = \delta ( \Omega _ { 1 } - \Omega _ { 2 } ) } \end{array}$ , we see that in the limit $\rho _ { \infty }  \infty$ ，after counterterms are added to cancel the divergence,the two-point functions consist of $\delta$ functions and their derivatives by Laplacian.Therefore, the holographic correlation functions for a massive scalar are essentially zero.

Next one could explicitly compute higher-point functions following the bulk-to-boundary principle.However, if we assume the dilaton-type massless scalar Lagrangian of the form ${ \mathcal { L } } = ( \partial _ { \mu } \phi ) ^ { 2 } P ( \phi )$ where $P ( \phi )$ is a polynomial, the correlators always scale as $\rho _ { \infty } ^ { d - 1 }$ . Therefore they can all be eliminated by adding boundary counterterms.

In summary, we argue that all $n$ -point correlation functions vanish after counterterms are added to cancel the divergences.This seems surprising until one recalls our previous observation from the holographic entanglement entropy: $A$ is maximally entangled with $B$ when the size of $A$ approaches zero.Define an infinitesimal subsystem $A$ as the disjoint union of the $n$ points in the correlation function: $A = \sqcup _ { i = 1 } ^ { n } x _ { i }$ . Our previous result implies that in this case the entanglement entropy $S _ { A }$ is maximal, therefore the density matrix $\rho _ { A }$ factorizes into a direct product $\rho _ { A } = \otimes _ { i = 1 } ^ { n } \rho _ { x _ { i } }$ where $\rho _ { x _ { i } }$ gives the maximal entropy for the subsystem at point $i$ ，as in a system at an infinitely high temperature.Therefore all correlation

functions vanish:

$$
\langle \hat { O } ( x _ { 1 } ) \ldots \hat { O } ( x _ { n } ) \rangle \equiv \mathrm { T r } [ \rho _ { A } \hat { O } ( x _ { 1 } ) \ldots \hat { O } ( x _ { n } ) ] = 0 .
$$

We emphasis that this does not mean that the boundary theory is empty: it stems from the fact that the boundary theory is nonlocal and highly entangled. Based on this we propose that the bulk physics in flat space should be reproduced by the boundary entanglement entropies (with all possible subsystems traced out).

The correlators of the free scalar toy model(11) are not exactly zero,but the usual divergence (when two operators coincide) already disappears.This leads us to expect that choosing appropriate interactions can further reduce the correlators to zero.Indeed,such a theory already exists in the discretized form: consider a spin model with the randomized antiferromagnetic Heisenberg interaction $\begin{array} { r } { H = J \sum _ { \langle i , j \rangle } \vec { \sigma } _ { i } \cdot \vec { \sigma } _ { j } } \end{array}$ where $J > 0$ and $\left. i , j \right.$ are pairs of two randomly chosen spins. Since the distance and orientation between two spins inside a pair is randomly distributed, all correlators are zero; and since generically the two spins in a given pair are separated far away from each other, the entanglement entropy obeys the volume law. The continuum limit of this type of spin models would provide field theory candidates for the holographic dual of the flat space.

Discussion. Nowwe draw an analogy between the boundary entanglement entropy and the bulk Schwarzschild entropy in the spirit of the connection between Unruh effect and Hawking radiation. In the Lorentzian version of(1） given by $d s ^ { 2 } = d \rho ^ { 2 } + \rho ^ { 2 } ( - d t ^ { 2 } +$ $\cosh ^ { 2 } t \ d \Omega _ { d - 1 } ^ { 2 } )$ ，a static observer at $\rho ~ = ~ \rho _ { 0 }$ detects a thermal state at the Unruh temperature Tu = 2πρo 1.The entanglement entropy $S _ { A }$ for maximal size $A$ （ $\alpha = \pi$ ） canbe rewrittsSA Since $S _ { A }$ measures the amount of information hidden in the subsystem $B$ ，which is inaccessible to observers in $A$ ，itis analogous to the entropy of Schwarzschild black hole with temperature $T _ { B H } ~ = ~ T _ { U }$ ．Indeed，the $( d + 1 )$ dimensional Schwarzschild black hole has an entropy $\begin{array} { r } { S _ { B H } = \frac { 2 ^ { - 2 d + 1 } \pi ^ { \frac { 2 - d } { 2 } } ( d - 2 ) ^ { d - 1 } } { \Gamma ( \frac { d } { 2 } ) \cdot G _ { N } ^ { ( d + 1 ) } \cdot T _ { B H } ^ { d - 1 } } } \end{array}$ ,which agrees with $S _ { A }$ up to a numerical constant.Thus our holographic interpretation is consistent with black hole entropies.

This also suggests a string theory interpretation of our holography. In AdS/CFT [2], the holographic dual theory comes from the D-branes that originally sit at the horizon $r ~ = ~ 0$ .In our flat spacetime,in the limit of $\rho  0$ ，the Unruh temperature $T _ { U }$ becomes infinitely large and the corresponding observer detects pair creations of many D-branes. We speculate that their open string theory is the nonlocal field theory conjectured to be the holographic dual of the flat spacetime.

Finally, let us reexamine the connection between UV cutoff in the field theory and the cutoff radius of the bulk.Matching the entanglement entropy obtained from the holographic computation（(3）with $\alpha = \pi$ ）and the field theory one（(10）with $q \ = \ \frac 1 2$ )，we see that if we switch to dimensionless coordinates defined by $\tilde { \rho } \equiv \frac { \rho } { R }$ where $R$ is a length unit,and accordingly consider the boundary theory on a unit sphere $S ^ { d }$ with dimensionless lattice spacing $\begin{array} { r } { \tilde { a } = \frac { u } { R } } \end{array}$ ， we can identify $\begin{array} { r } { \tilde { a } = \frac { 1 } { \tilde { \rho } _ { \infty } } } \end{array}$ Now $S _ { A }$ ,interpreted as the entanglement entropy for the holo graphic dualontheunit sphere $S ^ { d }$ ,scalesas: $\begin{array} { r } { S _ { A } \sim \frac { n } { \tilde { a } ^ { d - 1 } } } \end{array}$ where the dimensionless number n \~Rd-1 +1 counts the number of fields in the holographic dual. Since the bulk metric $d s ^ { 2 } = R ^ { 2 } ( d \tilde { \rho } ^ { 2 } + \tilde { \rho } ^ { 2 } d \Omega _ { d } ^ { 2 } )$ is invariant under the rescaling $( R , \tilde { \rho } )  ( R \lambda , \tilde { \rho } / \lambda )$ for arbitrary $\lambda$ ，there exists a corresponding symmetry in the holographic dual theory: $( n , \tilde { a } )  ( \lambda ^ { d - 1 } n , \lambda \tilde { a } )$ .Note that the total number of degrees of freedom in the boundary field theory is proportional tod- and therefore remains invariant. This symmetry suggests that the theory is highly nonlocal and entangled and will be useful when we go on to identify the precise holographic dual. We leave these questions for future study.

Acknowledgement. Authors are supported by WPI Initiative,MEXT,Japan. TT is supported in part by JSPS Grant-in-Aid for Scientific Research No. 20740132 and JSPS Grant-in-Aid for Creative Scientific Research No. 19GS0219.

[1]G.'t Hooft,arXiv:gr-qc/9310026;L. Susskind,J. Math. Phys.36(1995)6377.   
[2]J.M.Maldacena,Adv.Theor.Math.Phys.2(1998) 231.   
[3] S.S.Gubser,I.R.Klebanov and A.M. Polyakov, Phys. Lett.B 428,105 (1998).E.Witten,Adv.Theor.Math. Phys.2,253 (1998).   
[4]D.Marolf,JHEP0703（2007)122.   
[5] M.Alishahiha,A.Karch,E. Silverstein and D.Tong,AIP Conf.Pr0c.743(2004)393.   
[6]J.de Boer and S.N.Solodukhin，Nucl. Phys.B 665 (2003) 545.S.de Haro，K.Skenderis and S.N. Solodukhin,Class.Quant.Grav.18,3171 (2001)   
[7]B.Freivogel,Y.Sekino,L. Susskind and C.P.Yeh,Phys. Rev.D 74(2006)086003. [8] I. Bredberg,C.Keeler，V. Lysov and A. Strominger, arXiv:1006.1902 [hep-th]. [9] S.Ryu and T.Takayanagi,Phys.Rev.Lett.96 (2006) 181602；JHEP 0608(2006) 045.   
[10]J.L.F.Barbon,C.A.Fuertes,JHEP0804(2008)096.   
[11] L.Bombelli,R.K.Koul,J.H.Lee and R. D.Sorkin, Phys.Rev.D 34,373 (1986)；M. Srednicki,Phys.Rev. Lett.71,666 (1993).   
[12]P. Calabrese,J.Cardy,arXiv:cond-mat/O503393.   
[13]V.Alba,M.Fagotti,P.Calabrese,arXiv:0909.1999.   
[14] L. Susskind and E.Witten,arXiv:hep-th/9805114.   
[15] D.Nesterov, S. N. Solodukhin,arXiv:1007.1246 [hep-th].   
[16] M.Fujita,T.Nishioka and T.Takayanagi,JHEP 0809 (2008)016.   
[17]R.de Mello Koch，A.Jevicki，M.Mihailescu and R.Tatar,Phys.Lett.B 482(2000)249.   
[18] A.W.Peet and J.Polchinski,Phys.Rev.D 59 (1999)

065011. [19] S.Kachru,X.Liu and M.Mulligan,Phys.Rev.D 78 (2008)106005. [20] S.N. Solodukhin,Nucl. Phys.B 539 (1999) 403. [21] S.Minwalla and N. Seiberg, JHEP 9906 （1999) 007.