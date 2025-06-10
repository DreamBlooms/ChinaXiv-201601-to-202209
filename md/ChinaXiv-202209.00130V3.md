# Quantum abstract neural automata

Guangcheng Xi (The State Key Laboratory of Management and Control for Complex Systems, Institute of Automation, Chinese Academy of Science, Beijing, 100190,P.R.China)

# Abstract

The nineties of the $2 0 ^ { \mathrm { t h } }$ century, I have proposed and constructed theory of Abstract Neural Automata (ANA) [1].Aim of present manuscript is exploring theory of ANA on quantum state. Some results have been obtained.

Keywords : Gibbs measure ，Quantum abstract neural automata, Existence，von Neumann algebra，Isomorphic，Consciousness.

# 1. Introduction

The nineties of the 2Oth century, I have proposed and constructed theory of Abstract Neural Automata (ANA) [1]. Some of the work having done:

Abstract neural automata are established on N-dimensional lattices、Euclidean Spaces and compact Riemannian manifolds respectively；and the objectives are achieved: concept generation, concept connection transfer and thinking formation in abstract neural automata; The origin of thought; There is a positive correlation between brain intelligence and the volume of related brain regions；The ergodicity of the genetic evolution of human brain intelligence; Abstract neural automata has a unique solution if and only if it goes to infinity in both micro and macro; (Consciousness is expected to unify micro and macro!)；Equivalent proposition: Abstract neural automata is Markov; The limiting probability distribution of abstract neural automata is Gibbsian; Abstract neural automata are evolutionary；Assuming the existence of information on network of the stochastic automata, abstract neural automata are forever moving machines in the sense of evolution； The representation theory of knowledge by abstract neural automata is established.

Aim of present manuscript is exploring theory of ANA on quantum state(QANA).The precondition for writing this article is to make sure that quantum mechanics plays a role in brain function[2][3][4] .In particular, Consciousness depends on quantum states of electrons within hydrophobic pockets in a class of brain proteins. Proof of existence Of QANA on the von Neumann algebra $L ^ { \infty } ( X , \mu )$ and on the $C ^ { * }$ 1 algebra . $\mathcal { A }$ has been given in present article; For $\Phi \in { \mathcal { R } }$ and $\psi \in I ( \tau )$ ， following proposition is mutually equivalent:

(1)There exists QANA on $C ^ { * }$ -algebra . $\mathcal { A }$ (2) $\psi$ is $( \sigma ^ { \Phi } , \beta )$ -KMS state. $( 3 ) P ( \psi ) = S ( \psi ) - \beta \psi ( A _ { \Phi } ) ;$ （204号

Conditional state of quantum measurement is Gibbsian; the brain of the observer begins the process of experiencing consciousness in process of the measurement . In particular, it is quite natural for us to see from the point of view of physics and mathematics that consciousness is the collapse of quantum states in the human brain system at the microscopic level, and is Gibbsian.

# 2.Definitions and a theorem about Abstract neural automata[1]

Definition 1.A stochastic automaton $\pmb { a }$ is defined as triplet with a function-pair $\pmb { a } = ( ( \mathrm { Q } , \mathrm { Y } , \mathrm { Z } ) , ( \mathrm { F } , \mathrm { G } ) )$ (1)

where Q:space of state;Y: set of input; $Z$ :set of output; $\operatorname { F } \colon \mathrm { Y } \times \mathrm { Q } ^ { 2 }  [ 0 , 1 ]$ ，such that

$$
\begin{array} { r l } & { \forall \mathrm { y } \in Y , \forall q \in Q , } \\ & { \quad \displaystyle \sum _ { \mathrm { q } ^ { \bullet } \in Q } F ( y , q , q ^ { \perp ) } = 1 } \end{array}
$$

exists;G $\ Q \times \ Z \to [ 0 , 1 ]$ ,such that $\forall \mathrm { q } \ \in \mathrm { ~ } Q$ ，

$$
\sum _ { z \in \mathcal { Z } } \operatorname { G } ( \mathtt { q } , \mathtt { z } ) = 1
$$

exists.

In fact, $F ( y , q , q ^ { \perp } )$ : the transition probability from state q to $q ^ { \intercal }$ when input is y ;

$\operatorname { G } ( q , z )$ : probability for output to be Z when state is $q$ ·

Definition 2.A network S of stochastic automaton $\mathbf { \mu } _ { \pmb { a } }$ is defined as a pair consisted of ddimensional the integer lattices(d-dimentional neuron -set ) $\boldsymbol { \mathrm { T } } ^ { d }$ and a function-pair

(R,C)

$$
S = ( T ^ { d } , ( R , C ) )
$$

where $ { \mathrm { R } } \colon  { \mathrm { T } } ^ { d } \to  { \mathrm { A } }$ ，A is a set of all automata which is defined as (Q，Y， Z）;C: $\mathrm { T } ^ { d } \times Z  Y$ ;in fact , $R ( t )$ is an automaton $\mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathbf { \delta } \mathbf { \alpha } \mathrm  \langle \mathbf { \delta \mathcal { \alpha } \mathcal { \alpha } \mathcal { \beta } } \mathbf { \alpha \mathcal { \delta \alpha } \mathcal } \mathbf { \delta \alpha } \mathcal { \beta } \mathbf { \alpha \delta } \mathbf { \alpha \delta } \mathbf { \delta \alpha } \mathbf { \delta \alpha } \mathbf { \delta \alpha } \mathrm \mathbf { \delta \alpha } \mathbf { \delta \alpha } \mathrm \mathbf { \delta \alpha } \mathbf { \delta \alpha } \mathrm \mathbf { \delta \alpha } \mathbf { \delta \delta \alpha } \mathbf  \delta \alpha \delta \delta \alpha \delta \delta \mathbf { \alpha \delta \alpha } \delta \delta \delta \mathbf  \alpha \delta \delta \alpha \delta \delta \delta \delta \delta \delta \delta \mathbf \alpha \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta \delta$ which corresponds to $t \in T ^ { d } : \mathrm { C }$ is a connected transformation of some network $N \subset S : \forall f \in Z ^ { T ^ { d } } , t _ { 0 } \in T ^ { d }$ ,when neuron $t \in T ^ { d }$ gives a output $f ( t ) , C ( t _ { 0 } , f ) = y$ is an input which is received by $t _ { \scriptscriptstyle 0 }$ ： Definition 3.Abstract Neural Automata(ANA)which are on the network is a set of random element $\{ \xi ( \mathfrak { t } ) , \mathfrak { t } \in T ^ { d } \}$ ， $\xi ( { \mathrm { t } } ) : ( { \mathrm { A } } , { \mathrm { B } } ( { \mathrm { A } } ) , { \mathrm { P } } )  ( { { \mathrm { Q } } ^ { T ^ { d } } = \mathrm { X } , \mathrm { B } ( \mathrm { X } ) , \mu } )$ ,where (A,B(A),P） and $\left( \mathsf { Q } ^ { T ^ { d } } \mathrm { = X , B \left( X \right) , } \mu \right)$ are two space of probability.

Definition 4.To every finite subset $L = ( \ t _ { 1 } , \dots , t _ { n } \ ) \subset T ^ { d }$ there corresponds probability distribution μ $( \mathrm { ~ ~ { ~ \bf ~ \mathscr ~ { ~ x ~ } ~ } ~ } _ { t _ { i } } , x _ { t _ { i } } \in \theta , i = 1 , \ldots , n$ ),such that $\mu ( \xi _ { { \iota } _ { i } } \mathrm { = x } _ { t _ { i } } , \mathrm { i = 1 , \ldots , n } ) = \mu _ { { \iota } } ( x _ { t _ { i } } , x _ { t _ { i } } \in Q , i = 1 , \ldots , n )$ and satisfies consistency condition with $L = ( t _ { 1 } , \dots , t _ { m } ) \subset L$

$$
\sum _ { x _ { t _ { m + 1 } } \in Q , \ldots , x _ { t _ { n } } \in Q } \mu _ { _ { L } } ( \mathrm { x } _ { t _ { i } } , \mathrm { i } = 1 , \ldots , \mathrm { n } ) = \mu _ { _ { L } } ( x _ { t _ { i } } , i = 1 , \ldots , m )
$$

We refer to the family of probability distribution $\mu ^ { = } \{ \mu _ { _ L } ^ { } ( \vartriangle ) \}$ asprobability distribution of ANA.

Definition 5.Family of conditional probability distribution

$$
\Lambda \ \{ \lambda _ { _ L } ( \mathrm { x } _ { t _ { i } } , \mathrm { i = 1 , ~ . ~ . ~ . ~ , n ) ~ | \ x ( t ) , t \in } T ^ { d } \backslash L \}
$$

Is called a conditional distribution ofANA,where $\begin{array} { r } { \mu \{ \mathfrak { \ x } ( \xi ( \mathfrak { t } _ { i } ) = \mathfrak { x } _ { t _ { i } } , \mathrm { i } = 1 , \dots , \mathrm { n } | \xi ( \mathfrak { t } ) , \mathfrak { t } } \end{array}$ $\begin{array} { c c l } { { \in { \cal T } ^ { d } \setminus { \cal L } } } &  { \} } & { { \mathrm {  ~ \lambda ~ } _ { \scriptscriptstyle { L } } ( \langle { \bf { \Delta } } _ { X _ { t _ { i } } } , i { \bf { \Delta } } _ { } 1 , \ldots , n \rangle \mathrm {  ~ \omega ~ } | { \bf { \Delta } } _ { X } ( t ) { \bf { \Delta } } , { \bf { t } } \in { \cal T } ^ { d } \setminus { \cal L } { \bf { \Delta } } ) } } \end{array}$ with probability one.

Definition 6.When $L = ( t _ { 1 } , \dots , t _ { m } ) \subset T ^ { d }$ ,for arbitrary $X _ { 1 } \ \in \ Q , \dots , X _ { m } \ \in \ Q$ ,and for arbitrary function $x \ ( \mathrm { t } ) , t \in T ^ { d } \backslash L$ ，conditional probability distribution

$$
\begin{array} { l } { \displaystyle \lambda _ { \mathit { l } } ( \left( \boldsymbol { \boldsymbol { \boldsymbol { \kappa } } } _ { 1 } , \ldots , \boldsymbol { \boldsymbol { \kappa } } _ { \mathit { \iota } } \right) \mid \boldsymbol { \boldsymbol { \kappa } } ( t ) ) } \\ { = \frac { 1 } { \Phi _ { \mathit { { L } } } ( \boldsymbol { \boldsymbol { \kappa } } ( t ) ) } \exp \left\{ - \beta U _ { \mathit { { L } } } ( \boldsymbol { \boldsymbol { x } } _ { 1 } , \ldots , \boldsymbol { \kappa } _ { \mathit { { \iota } } } ) \mid \boldsymbol { \boldsymbol { \kappa } } ( t ) \right\} } \end{array}
$$

Is called Gibbs distribution with a boundary condition $x ( t )$ in $L$ · Where

$$
\Phi _ { _ { L } } ( x ( t ) ) = \sum _ { \substack { x _ { 1 } \in \varnothing , \ldots , x _ { m \in \varnothing } } } \exp { - \beta U _ { _ { L } } ( ( x _ { 1 } , \ldots , x _ { m } ) \mid x ( t ) ) }
$$

And $\beta$ （2 constant， $0 < \beta < \infty$ ， inversely proportional to the temperature of network S of stochastic automata; $U _ { L }$ is called potential

$$
\begin{array} { l l } { { U _ { L } ( \left( X _ { 1 } , \dots , X _ { n } \right) \mid x ( t ) ~ ) } } & { { } } \\ { { } } & { { = - \mathrm { c } { \sum _ { i = 1 } ^ { n } X _ { i } } + { \displaystyle { \frac { 1 } { 2 } } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 , j \neq i } ^ { n } X _ { j } X _ { j } U ( t _ { i } - t _ { j } ) } + \sum _ { i = 1 } ^ { n } } } & { { \displaystyle { \sum _ { ( T ^ { i } - L ) } X _ { j } X ( t ) U ( t _ { i } - t ) } } } \end{array}
$$

Where c is a constant ,the chemical potential.

Definition 7.ANA and its distribution are called Gibbs ,if its conditional Distribution is given by equation (8).

Theorem 1.In theory of ANA,suppose collection of potential-functions of various form is $G ( U )$ ,and that Q is compact metric space ,then for given Continuous potential function $G ( U )$ ,ANA there exists on probability

Space ${ ( \mathsf { Q } ^ { T } } ^ { d } { = } \mathrm { X } , \mathrm { B } \left( \mathrm { X } \right) , \mu .$ [1].

# 3.Quantum abstract neural automata(QANA)

To describe abstract neural automa at quantum level （QANA） ,we associate with each neuron $a \in T ^ { d }$ ， quantum automaton, a finite dimentional Hilbert space $\mathcal { H } _ { a }$ Hence，we haveHilbert space $\mathcal { H } _ { \Lambda } { = } \bigotimes _ { a \in \Lambda \subset T ^ { d } } \mathcal { H } _ { \mathrm { a } }$ （204号 and then local $C ^ { * }$ -algebra

$$
\mathcal { A } _ { \Lambda } \stackrel { = } \otimes _ { a \in \Lambda \subset \mathcal { T } ^ { d } } \mathrm { , i f } \quad \mathrm { C ^ { * } \mathrm { - a l g e b r a } ~ \mathcal { A } _ { a } } = B ( \mathcal { H } _ { a } ) .
$$

Next we put

$$
\mathcal { S } ^ { = } \{ \Lambda \subset { T } ^ { d } , 0 < | \Lambda | < \infty \}
$$

where $| \Lambda |$ is the cardinality of set $\Lambda$ .Note that $\mathcal { S }$ is countable.On family of set $\{ \mathcal { X } _ { \Lambda } ~ , ~ \Lambda \in \mathcal { S } \} \qquad , \qquad \mathrm { l e t } \qquad \Lambda _ { 2 } \setminus \Lambda _ { 1 } \lnot \{ \mathsf { k } \in \Lambda _ { 2 } , k ~ \notin ~ \Lambda _ { 1 } \}$ ,then ${ \mathcal { A } } _ { \Lambda _ { 2 } } { = } . { \mathcal { N } } _ { \Lambda _ { 1 } } \otimes { \mathcal { N } } _ { \Lambda _ { 2 } \backslash \Lambda _ { 1 } }$ ,further when $\Lambda _ { 1 } \subset \Lambda _ { 2 }$ ,there exists embedding ${ \bf j } _ { \Lambda _ { 2 } \Lambda _ { 1 } }$ from $\begin{array} { r } { \mathcal { A } _ { \Lambda _ { 1 } } \mathrm { t 0 } \llcorner \mathcal { A } _ { \Lambda _ { 2 } } \mathrm { , ~  { \mathcal { A } } e f i n e d ~ b y ~  { j _ { { \Lambda _ { 2 } } \Lambda _ { 1 } } } } ( A ) = A \otimes I _ { \Lambda _ { 2 } \backslash \Lambda _ { 1 } } ( \forall A \in \mathcal { A } _ { \Lambda _ { 1 } } , I _ { \Lambda } , } \end{array}$ identity operator of. $\mathcal { A } _ { \Lambda }$ ),having following property

$$
\begin{array} { r l } & { ( 1 ) \Lambda _ { 1 } \subset \Lambda _ { 2 } \subset \Lambda _ { 3 } \Rightarrow J _ { \Lambda _ { 3 } \Lambda _ { 1 } } = J _ { \Lambda _ { 3 } \Lambda _ { 2 } } J _ { \Lambda _ { 2 } \Lambda _ { 1 } } ; } \\ & { ( 2 ) \Lambda _ { 1 } \subset \Lambda , \Lambda _ { 2 } \subset \Lambda , \Lambda _ { 1 } \bigcap \Lambda _ { 2 } = { \mathcal { O } } } \\ & { \qquad \Rightarrow \operatorname { \big [ } J _ { \mathrm { A M _ { 1 } } } ( { \cal A } _ { 1 } ) , J _ { \mathrm { A } \Lambda _ { 2 } } ( { \cal A } _ { 2 } ) { \big ] } = 0 , \forall A _ { 1 } \in  { \mathcal { A } } _ { \Lambda _ { 1 } } } \\ & { \qquad \forall { \cal A } _ { 2 } \in  { \mathcal { A } } _ { \Lambda _ { 2 } } . } \end{array}
$$

Therefore,when $\Lambda _ { 1 } \cap \Lambda _ { 2 } { = } \emptyset$ ，we have $\mathcal { A } _ { \Lambda _ { 1 } } \overline { { \Lambda } } _ { 1 } \overline { { \Lambda } } _ { 2 }$ ,hence $\{ \mathcal { A } , \ \Lambda \in \mathcal { A }$ is increasing family. And then, ${ \mathcal { A } } _ { 0 } ^ { = } \bigcup _ { \Lambda \in { \mathcal { S } } } { \mathcal { A } } _ { \Lambda }$ is normed $\ast$ -algebra ， completion of $\mathcal { A }$ by means of this norm : $v = v _ { 1 } \cdot v _ { n }$ ； $\Lambda \in \mathcal { S } \}$ is known as localC\*-algebra of local observables.

$$
\mathrm { ~ a ~ } = ( a _ { 1 } , \dots , a _ { d } ) \in T ^ { d } \qquad , \qquad \mathrm { w e } \qquad \mathrm { d e f i n e } \qquad \Lambda ^ { } \mathrm { ~ ( a ) } \subset T ^ { d }
$$

$\Lambda { \pmod { \alpha } } = \{ { \mathrm { b } } \in T ^ { d } ; 0 \leq b _ { j } \leq a _ { j } , j = 1 , \dots , d \}$ .The set of translation of $\Lambda$ (a) by $\mathrm { n } a = ( n _ { 1 } a _ { 1 } , \dots , n _ { d } a _ { d } )$

$$
\Lambda _ { \mathfrak { n } } = \Lambda ( a ) + \eta a , \mathfrak { n } \in T ^ { d }
$$

form a partition of $T ^ { d }$ .For any $\Lambda \subset T ^ { d }$ ,we let $\mathrm { N } _ { a } ^ { + } ( \Lambda ) ( \mathrm { r e s p . } \mathrm { N } _ { a } ^ { - } )$ to be the number of $\Lambda _ { \mathrm { n } } \cap \Lambda \neq \emptyset$ (resp. $\Lambda _ { n } \subset \Lambda \bar { . }$ ）of $\Lambda _ { \mathrm { n } }$ .At this time ,for all a finite subset $\Lambda \subset T ^ { d }$ are defined to tend to $\infty$ in the sense of Van Hove，if

$$
\mathrm { l i m } { \cal N } _ { a } ^ { - } ( \Lambda ) / \mathsf { N } _ { a } ^ { + } ( \Lambda ) = 1 ,
$$

to express as $\Lambda \Rightarrow \infty$ ：

For arbitrary $a , \xi \in T ^ { d }$ ,suppose unitary mapping $U _ { \xi } ^ { \mathbf { \alpha } } ( \alpha )$ from $\mathcal { H } _ { \xi }$ to $\mathcal { H } _ { \xi + a }$

satisfies conditions $( 1 ) U _ { \xi } ( 0 ) = \mathrm { { I } } _ { \xi } , ( 2 ) U _ { \xi } ( a + b ) = U _ { \xi + b } ( a ) U _ { \xi } ( b ) ( \forall \mathrm { { b \in } }$ $\forall \mathrm { b } \in T ^ { d }$ ;and let $U _ { \wedge } ( a ) = \bigotimes _ { \xi \in \Lambda } U _ { \xi } ( a )$ .Using this unitary operator,let

$$
\tau _ { { \scriptscriptstyle a } } ( \mathrm { A } ) = U _ { \scriptscriptstyle \Lambda } ( a ) \mathrm { ~ \AA ~ } \mathrm { U } _ { \scriptscriptstyle \Lambda + a } ( - a ) .
$$

Hence $\tau$ is automorphism mapping from $\mathcal { A } _ { \Lambda }$ to $\mathcal { A } _ { \Lambda + \mathrm { a } }$ (i.e.， $\tau \colon \operatorname { T } ^ { d }  A u t ( \mathcal { A } ) )$ ：

Suppose $\varphi$ is the state on : $\mathcal { A }$ .Restriction $\varphi _ { \Lambda }$ of $\varphi$ to： $\mathcal { A } _ { \Lambda }$ is known as local normal state if it satisfies conditioin:thereexists $\rho _ { { \scriptscriptstyle \Lambda } } \in { \cal T } ( { \mathcal { H } } _ { { \scriptscriptstyle \Lambda } } ) _ { + , 1 } , \varphi _ { { \scriptscriptstyle \Lambda } } ( { \mathtt { A } } ) = \mathrm { t r } _ { { \scriptscriptstyle \Lambda } } \rho _ { { \scriptscriptstyle \Lambda } } A$ （ $( \forall A \in { \mathcal { A } } )$ ， hence we have $\scriptstyle { \varphi = \{ \rho _ { \Lambda } \} }$ when $\rho _ { { } _ { \Lambda } } \mathrm { = t r } _ { { } _ { \Lambda ^ { \prime } \backslash \Lambda } } \rho _ { { } _ { \Lambda ^ { \prime } } }$ $( \Lambda \subset \Lambda ^ { \prime }$ ).Moreover if $\scriptstyle { \varphi = \{ \rho _ { \Lambda } \} }$ satisfies condition $\rho _ { \Lambda ^ { + } \mathrm { a } } = U _ { \Lambda } ( a ) \rho _ { \lambda } U _ { \Lambda ^ { + } a } ( - a )$ ,then $\varphi$ is known as $\tau ^ { - }$ invariable(i.e., $\varphi \in I ( \tau ) ) \mathrm { o r } T ^ { d }$ -invariable.

For $\scriptstyle { \varphi = \{ \rho _ { \Lambda } \} }$ ,entropy of $\rho _ { \mathrm { _ { \Lambda } } }$ equals $S _ { \Lambda } ( \varphi ) = - t r _ { \Lambda } \rho _ { \Lambda } \log \rho _ { \lambda } .$ （20

Theorem 2.Let $\varphi \in I ( \tau )$ , and soppose $\mid \Lambda \mid$ is volume of $\Lambda$ ， then we have:

$( 1 ) S ( \varphi ) = \operatorname * { l i m } _ { \Lambda \to \infty } \mid \Lambda \mid ^ { - 1 } S _ { \Lambda } ( \varphi ) , 0 \le S _ { \Lambda } ( \varphi ) \le \log 2 .$ (12) (2） $S ( \varphi )$ is affine and upper semi-continuous fuction on $I ( \tau )$ ： If mapping $\Phi \colon \Lambda \in \mathcal { S }  \Phi \ ( \Lambda ) \in \mathcal { N } _ { \Lambda }$ satisfies condition $\Phi \ ^ { \mathrm { ~ \tiny ~ ( ~ \Lambda ) = Phi ~ } \mathrm { ~ \tiny ~ ( ~ \Lambda ) ~ } ^ { * } }$ ,then $\Phi$ is called interaction potential(or simply apotential). Let $\parallel \Phi \parallel = \sum _ { \Lambda \ni 0 } \frac { \parallel \Phi ^ { \mathrm { ~ \tiny ~ ( ~ \Lambda ~ ) ~ } } \parallel } { | \Lambda \mid } \mathrm { , s e t ~ o f ~ a l l ~ \Phi ~ } \Phi ^ { \mathrm { ~ \tiny ~ ( ~ \parallel ~ \Phi ~ | | < ~ \infty ~ ) b e ~ } } \mathcal { D } \mathrm { , t h e n , }$ $\mathcal { B }$ becomes real Banach space for norm $\| \Phi \|$ . Further, $\Phi$ is known as finite range if number of finite set $\Lambda$ to have made $\Phi \ ( \Lambda ) \neq 0$ （ $\mathbf { \lambda } ( \Lambda \textbf { > } 0 )$ is finite.Let all of interaction potentials $\Phi \in { \mathcal { B } }$ of finite range be $\mathcal { R }$ ,hence completion of $\mathcal { R }$ for norm $\| \Phi \|$ equals $\mathcal { B }$ ,to express as $\begin{array} { r } { \overbrace { \mathcal { P } _ { \mathrm { 0 } } } ^ { \mathrm { ~ - ~ } \parallel . \mathrm { | } } = \mathcal { D } \mathrm { . W h e n } \Phi \mathrm { ~ } ( \Lambda ^ { + } \mathrm { a } ) = \tau _ { a } ( \Phi ( \Lambda ) ) \mathrm { , ~ } \Phi } \end{array}$ is known as $T ^ { d }$ -invariable or translationally invariable； there exists some number ${ { n } _ { 0 } }$ ,wh ${ \mathrm { ~ \mathsf ~ { ~ e ~ n ~ } ~ } } \mid \Lambda \mid > { \mathsf { n } } _ { \mathrm { { \boldsymbol { \imath } } } } , \Phi \mathrm { ~ \mathsf { ( } } \Lambda \mathcal { ) } { \mathrm { = } } 0 , \Phi$ is known as interaction potential of finite body.

For $\Phi \in { \mathcal { B } }$ ,let

$$
H _ { \Lambda } ( \Phi ) { = } \sum _ { X \subset \Lambda } ~ \Phi ( X )
$$

and

$$
{ \cal A } _ { \Phi } \ = \ \sum _ { 0 \in \Lambda } \ { \frac { \Phi ( \Lambda ) } { | \Lambda \ | } }
$$

then for $\varphi \in I ( \tau )$ ，frc $\mathrm { ~ m ~ } \mid \Lambda \mid ^ { - 1 } \varphi ( \sum _ { a \in \Lambda } \ \tau _ { _ a } ( \Lambda _ { \Phi } ) ) { = } \varphi ( \Lambda _ { _ \Phi } )$ , we have

$\operatorname* { l i m } _ { \Rightarrow \infty } \mid \Lambda \mid ^ { - 1 } \varphi ( \mathrm { H } _ { \Phi } ( \Lambda ) ) = \varphi ( { \cal A } _ { \Phi } ) . \mathrm { F o r }$ （2号 thermodynamic functions

$$
Z _ { \Lambda } ( { \Phi } ) = t r _ { \Lambda } e ^ { - H _ { \Lambda } ( { \Phi } ) } ,
$$

And

$$
P _ { _ { \Lambda } } ( \Phi ) = \frac { 1 } { \mid \Lambda \mid } \log Z _ { _ { \Lambda } } ( \Phi ) ,
$$

We have

Theorem 3.Suppose $\Phi \in { \mathcal { B } }$ is $T ^ { d }$ - invariant ,then

(1)there exists $P ( \Phi ) = \underset { \Lambda \Rightarrow \infty } { \mathrm { 1 i m } } P _ { \Lambda } ( \Phi )$ ：

$$
) P ( \Phi ) = \operatorname* { s u p } \{ S ( \psi ) - \psi ( A _ { \Phi } ) ; \psi \in I ( \tau ) \} .
$$

(3) $P ( \Phi )$ is continuous convex fubction,and

$$
\begin{array} { r } { \mid P ( \Phi ) - P ( \Psi ) \mid \leq \mid \mid \Phi - \Psi \mid \mid , \forall \Phi , \Psi \in \mathcal { D } . } \end{array}
$$

Lemma 1. Suppose that $\mathbf { M }$ is a commutative von Neumann algebra, then there exists locally compact Hausdorff space $E$ which satisfies second axiom of countability, and measure V ,such that M=L(E,v).

Lemma 2. A $C ^ { * }$ —algebra $\mathcal { A }$ is a von Neumann algebra if and only if it has adual $\mathcal { A }$ as a Banach space.

Denote set of linear functional $\varphi$ from $C ^ { * }$ —algebra. $\mathcal { A }$ to C(complex field) by $\mathcal { A }$ ,since $C ^ { * }$ —algebra $\mathcal { A }$ is bounded normed linear space ,its dual space is Banach

space fornorm $\varphi ( \mathtt { A } ) = _ { \rVert } \varphi _ { \rVert , \mathtt { A } } \in \mathcal { A } \mathrm { . W h e n ~ } \rVert \varphi _ { \rVert } = 1 , \varphi$ is called state on . $\mathcal { X } . \mathcal { A }$ is called space of state.From Lemma $^ { 2 , \mathrm { C ^ { * } } }$ —argebra . $\mathcal { A }$ is von Neumann algebra.Hence from Lemma 1 and Lemma 2,we have following

Theorem 4. Let $L ^ { \infty } ( E , \nu ) { = } L ^ { \infty } ( X , \mu )$ ,hence there exists QANA on von Neumann algebra $L ^ { \infty } ( X , \mu )$

Proof. Let $L ^ { \infty } ( X , \mu ) = \left( E ,  _ { \mathrm { E } } \right. , \left. \nu \right)$ , then ,from the nature of $L ^ { \infty } ( X , \mu )$ ,we have

$$
\nu _ { { \scriptscriptstyle f } } ( B , B \in \mathrm {  ~ E ~ } ) =  \mu ( \mathrm {  ~ f ~ } ^ { - } ( \mathrm {  ~ B ) ~ } ) =  \mu \{ { x : f ( x ) \in B } \} , a . e . ,
$$

therefore $L ^ { \infty } ( X , \mu )$ and $( \boldsymbol { X } , \mu )$ are isomorphic.Hence there exists ANA on $( \boldsymbol { X } , \mu )$ (Theorem 1) $\Leftrightarrow$ （204号 thereexists QANA onthe $L ^ { \infty } ( X , \mu )$ ．QANA $C ( \rho | \mathrm { P } _ { a } ) = \frac { \rho } { T r ( \rho ) } = \frac { e ^ { - \beta H } } { T r ( e ^ { - \beta H } ) }$ (22) （see subsection 4）.

Suppose set of all potentials $\Phi \in { \mathcal { R } }$ which are $T ^ { d }$ -invariant and have interaction of finite body is $\mathcal { R }$ .For $\Phi \in { \mathcal { K } }$ ，there exists （204 $\sigma _ { t } ^ { \Phi } \in A u t ( \mathcal { A } ) \left( \forall t \in \mathsf { R } \right)$ (i.e., $\operatorname* { l i m } _ { { \boldsymbol { \Lambda } } ^ { \dagger } { \boldsymbol { \mathcal { T } } } ^ { d } } \parallel \sigma _ { t } ^ { \Phi } ( { \boldsymbol { A } } ) - e ^ { i t H _ { \boldsymbol { \Lambda } } ( \Phi ) } A e ^ { - i t H _ { \boldsymbol { \Lambda } } ( \Phi ) } \parallel = 0 , \forall { \boldsymbol { A } } \in { \mathcal { A } } .$ （20

Definition 8. Let $\sigma _ { { } _ { t } }$ be a strongly—continuous oneparameter group of automorphism of $\mathcal { A } \in \mathcal { R }$ (real number).One says that a state （204 $\psi \in \mathcal { N }$ is KMSpstate for $\sigma$ if it is invariant under $\sigma _ { { } _ { t } }$ ,i.e. $\psi \in I ( \tau )$ ，and for all $a , b \in \mathcal { A }$ there exists a function $F _ { a , b } ( z )$ bounded and continuous on the stirp $0 \leq \mathrm { I M } \left( z \right) \leq \beta$ andanalyticon $0 < \mathrm { I M } \left( z \right) < \beta$ suchthat $F _ { _ { a , b } } ( t ) = \psi ( a \sigma _ { { t } } ( b ) )$ for all $t \in R$ ; and $F _ { _ { a , b } } ( t { + } \mathrm { i } \beta ) = \psi ( \sigma _ { { t } } ( b ) a )$ for all $t \in R$ ： Proposition. Let $A = K \left( \mathcal { H } \right)$ be the algebra of compact operators on a Hilbert space $\mathcal { H } , \beta \in R$ (real number) and $H$ a self

Adjoint operator such that e- BH is trace class.Then the Gibss state with density matrix $\varphi { = } \frac { e ^ { - \beta H } } { T r ( e ^ { - \beta H } ) }$ is the unique KMS—state for the one —parameter group generated by $H$ （20

Theorem 5.For $\Phi \in { \mathcal { R } } _ { 1 }$ and $\psi \in I ( \tau )$ ， following proposition is mutually equivalent:

(1)There exists QANA on $C ^ { * }$ -algebra. $\mathcal { A }$ $( 2 ) ^ { \psi }$ is $K M S _ { _ { \beta } }$ state. β $\phantom { } _ { ) } P ( \psi ) = S ( \psi ) - \beta \psi ( A _ { \Phi } ) \cdot _ { [ 5 ] }$

# 4.Coexistence of $\mathbf { N }$ and Q

The content of this section is to explain the coexistence of QANA and ANA in the brain and their interdependent relationship by means of the mean of method of text [6].

Suppose that human neural system at the ion level （QANA） is denoted by Q, while the human neural system at level of neural network(ANA) is denoted by N,that the category von Neumann algebra of Nis

$$
\mathbf { A } = \mathbf { C } ^ { A }
$$

for some finite set $A$ ,that the category von Neumann algebra ofQis B.Let's do linear map

$$
\varepsilon \colon \mathrm {  ~ B ~ } ^ { * }  \mathrm {  ~ A ~ } ^ { * } .
$$

Hence we have

$$
\varepsilon ( \rho ) \mathbf { \equiv } _ { a \in \mathcal { A } } ( E _ { a } ) \ ,
$$

where POVM $E _ { a } \ \ge \ 0$ ,and

$$
\sum _ { a \in { \cal A } } ( \mathrm { E } _ { a } ) { \it \Delta \phi } = 1 .
$$

In fact, $E _ { a } { : } A \to { \mathcal { D } } { \mathrm { + } }$ , a positive operator-valued measure on $A$ ,POVM, that takes values inpositive cone $\mathcal { D } +$

A conditional state on B:

$$
F = \bigoplus _ { a \in A } [ { \mathrm { a } } ] \otimes \rho ^ { { \sqrt { E _ { a } } } } .
$$

The conditional state of the POVM $\varepsilon$ applied to $\rho$ with outcomeais

$$
\mathrm { C } ( \rho | \varepsilon { = } a \ ) { = } \rho ^ { \sqrt { E _ { a } } } ,
$$

In fact ,we can see the linear map $\varepsilon$ asa set-valued measurement which is represented as an orthogonal decomposition:

$$
\mathcal { H } \overset { } { \underset { a \in \mathcal { A } } { } } \mathcal { H } ( \textbf { \em a } )
$$

The probability of the outcome $a$ is given by

$$
T r ( \rho P _ { a } )
$$

And the conditional state of $\mathbf { B }$ on A

$$
C ( \rho | \mathrm { P } _ { a } ) = \frac { \mathrm { P } _ { a } \rho \mathrm { P } _ { a } } { T r ( \rho \mathrm { P } _ { a } ) }
$$

Since $\mathcal { H } ( a )$ is invariant subspace of $\rho$ ,and reducing $\rho$ thus

$$
C ( \rho | \mathrm { P } _ { a } ) = \frac { \rho \mathrm { P } _ { a } } { T r ( \rho \mathrm { P } _ { a } ) } = \frac { \mathrm { P } _ { a } \rho } { T r ( \mathrm { P } _ { a } \rho ) } .
$$

The process of a measurement is process of the decoherence.State in that the decoherence has been achieved is called trivial quantum state—equilibrium state - classicalstate. $\mathrm { A t } \qquad \mathrm { t h i s } \qquad \mathrm { t i m e } , \qquad \because \mathrm {  ~ \cal { P } ~ } _ { a } { \cal { X } } = { \cal { X } } , \forall { \cal { X } } \in \mathrm { ~ { ~  ~ \cal ~ { ~ X ~ } ~ } ~ } ( a \mathrm { ~  ~ \mu ~ } ) ,$ ： $\mathrm { ~ P ~ } _ { a } = \mathrm { ~ I ~ }$ (travial projection）； and : $\rho \in \mathrm { T }$ （%）+，1， $e ^ { - \beta H } \in T$ （20 （ $\mathcal { H }$ （204号 （20 $( \Phi ( \Lambda ) { = } \Phi ( \Lambda ) ^ { * } )$ ,:let $\rho { = } \mathrm { e } ^ { - \beta H }$ ,hence we have

$$
C ( \rho | \mathrm { P } _ { a } ) = \frac { \rho } { T r ( \rho ) } = \frac { e ^ { - \beta H } } { T r ( e ^ { - \beta H } ) }
$$

Therefore the trivial conditional state is Gibbsian;conditioning on a measurement is also called "state collapse"or"wave function collapse"; the brain of the observer begins the process of experiencing consciousness in process of measurement [7]. In particular, it is proved mathematically that the trivial conditional state of quantum measurement is Gibbsian, thus proving that the consciousness of the observer is Gibbsian, which is consistent with the discussion on consciousness in article [7].

# References

[1] Xi Guangcheng, Abstract neural automata,Kyberneces:The International Journal of System and Cybernetics,Vol.27,No.1,1998,pp.81-86;Abstract neural automata -further considerations, Kyberneces:The International Journal of System and Cybernetics, Vol.27,No.2,1998,pp.176- 181;Variability of structure of abstract neural automata and   
the ability of thought, Kyberneces:The International Journal of System and   
Cybernetics,Vol.32,No.9\10,2003,pp.1549-1554; Abstract neural automata:   
Ergodicity of evolution of   
genetico-variable structure,Kyberneces:The International Journal of System and   
Cybernetics,Vol.28,No.8,1999,pp.939-944;   
Abstract neural automata on   
compact Riemannian manifold, Kyberneces:The International Journal of System and   
Cybernetics,Vol.32,No.9\10,2003,pp.1540-1548;   
Abstract neural automata (ANA):   
existence of"empty" and origin of   
thought,Kyberneces:The International Journal of System and   
Cybernetics,Vol.32,No.3,2003,pp.388-393; Gibbsian representation of knowledge in infinite dimensional random neural network (IDRNN),Chinaxiv:2O1803.01556v2.

[2]HerbertS.Green;Information Theory and Quantum physics,p.171,Springrer,1998. [3] FRIEDRICH BECK AND JOHN C.ECCLES;Quantum aspects of brain activity and the role of consciousness,Proc.Natl.Acad.Sci.USA,Vol.89,PP.11357-11361,Decembr 1992,Biophysics. [4]Stuart Hameroff, Alex Nip,Mitchell Porter, Jack Tuszynski;Conduction pathwaysin microtubules, biological quantum computation,and consciousness,BioSystems 64(20o2)149-168.) [5]梅垣壽春，大矢雅则;量子论的ン卜口ビ一，昭和58年8月. [6]Greg Kuperberg;A concise introduction to quantum probability， quantum mechanics,and

quantum computation,on Internet. Guangcheng Xi ; Entropy-partition of Complex Systems and Emergence of Human Brain's   
[7]   
Consciousness,ChinaXiv:201705.00829v3.