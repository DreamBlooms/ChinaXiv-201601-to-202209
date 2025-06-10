# Gibbsian representation of knowledge in infinite dimensional random neural networks(IDRNN)

Guangcheng Xi (The State Key Laboratory for Management and Control of Complex Systems, Institute of Automation, Chinese Academy of Science, Beijing,1O019o,P.R.China)

Abstract. In studying of a class of random neural network, some of relative researchers have proposed Markov model of neural network. Wherein Markov property of the neural network is based on “assuming". To reveal mechanism of generating of Markov property in neural network, it is studied how infinite-dimensional random neural network (IDRNN) forms inner Markov representation of environment information in this paper.Because of equivalence between markov property and Gibbsian our conclusion is that knowledge is eventually expressed by extreme Gibbs probability measure —ergodic Gibbs probability measure in IDRNN. This conclusion is also applicable to quantum mechanical level of IDRNN. Hence one can see“ concept “- “ consciousness” is generated at particle(ion) level in the brain and is experienced at the level of the neurons; We have discussed also ergodicity of IDRNN with random neural potential.

Keywords:Infinite-dimensional random neural network(IDRNN)， Markov representation， Random neural potential ,Ergodic Gibbs probability measure, Extreme point,Fock space.

# I .Introduction

In studying of a class of random neural network, some of relative researchers have proposed Markov model of neural network (Emile Aarts, Jan Korst, 1989; M.M. Van Hulle and G.A. Orban, 1991; Guangcheng Xi, 1991 ,and so on). It is studied how infinite-dimensional random neural network forms inner Markov representation of environmental information in this paper. Representational theory of neural network is one how environmental information is modeled in the neural network. Forming and renewing of representation of external world in neural network involve neural structure. Studying of forming mechanism for this class of representation is favourable for understanding location and mechanism of various neural structure, the class of representation is base for human brain to generate consciousness and can constitute new algorithm or given out solution of some algorithms.

Except for brief introduction, this paper consists of three parts. In second part we suppose $s$ is countable infinite set of neurons coupled by synapses to one another, $\left( \begin{array} { l } { \mathbf { \boldsymbol { E } } , \boldsymbol { B } ( \boldsymbol { E } ) } \end{array} \right)$ and( $\boldsymbol { X } = \boldsymbol { E } ^ { S } , \boldsymbol { B } ( \boldsymbol { X } )$ ）two measurable spaces，where $E$ is any measurable set of all possible values taking by single neuron. By means of analyzing generating process of so-called limit Markov process in IDRNN, we have shown in limit state of process for IDRNN to learn of environment (i.e. neuron in group of neurons $C \subset S$ takes a given value $y _ { b } = { \overline { { y } } } _ { b } \in E$ ） the limit Markov process is generated in IDRNN， this is to say，environment-knowledge is expressed by means of the limit Markov process in IDRNN, have pointed out set of all stationary distribution of the limit Markov process on IDRNN—set of limit Gibbs probability measure is a nonempty closed convex set of which ergodic Gibbs probability measure is extreme. Knowledge is eventually expressed by extreme Gibbs probability measures in IDRNN. In third part of this paper, we have discussed ergodicity of IDRNN with random neural potential. Fourth part is a remark.

# I . Markov representation of knowledge in IDRNN

Suppose $S$ is a countable infinite set of neurons coupled by synapses to one another, $\left( \mathbf { \Phi } _ { E , B \left( E \right) } \right)$ and ( $\boldsymbol { X } = \boldsymbol { E } ^ { s } , \boldsymbol { B } ( \boldsymbol { X } ) )$ two measurable spaces. Where $E$ is any measurable set of all possible values taken by single neuron. Hence，we have infinite dimensional random neural network (IDRNN).

In studying of human train's high function—consciousness, one suggested that a key neural mechanism underlying conscious experience are the recentrant interactions between posterior thalamocortical areas involved in perceptual categorization and anterior areas related to memory, value and planning for action. Such interactions among neural groups in distributed brain areas may be necessary in order to generate a unified neural process corresponding to a multimodal conscious scene (G. Tononi and Edelman. G. M.， 1998).In neurophysiological research of information representation in the cortex，a possible neural coding mechanism of spatiotemporal firing pattern of neurons is based on the temporal cell subassemblies which spontaneously dynamically organize into a dynamical cell assembly by synchronized activity of these subassemblies.Hebb's viewpoint has considered the assembly of neural cell has played key role in neural coding and neural information representatioin. Therefore, in the IDRNN by contrast to probability $p ( x , t )$ that IDRNN is in state $x \in X$ at the moment $t$ we have more interested in total probability (or its limit) that neurons in neural group （204 $C \subset S$ take given value ${ \overline { { y } } } _ { b } \in E , b \in C$ at the moment $t .$ ，Such total probability and its limit are expressed, respectively, as

$$
\begin{array} { r l } & { p _ { C } ( \overline { { y } } _ { b } , b \in C , t ) = \displaystyle \sum _ { x : y _ { b } = y _ { b } , b \in C } p ( x , t ) \ : , } \\ & { \hat { p } _ { C } ( \overline { { y } } _ { b } , b \in C ) = \displaystyle \operatorname* { l i m } _ { t  \infty } p _ { C } ( \overline { { y } } _ { b } , b \in C , t ) = \displaystyle \sum _ { x : y _ { b } = y _ { b } , b \in C } \hat { p } ( x ) \ : . } \end{array}
$$

Suppose for some ${ \overline { { x } } } \in X$ and any $x \in X$ and $l < \infty$ , can find finite sequence $x = x _ { 1 } , x _ { 2 } , \cdots , \overline { { x } } = x _ { l }$ such that

$$
p ( x _ { 1 } , x _ { 2 } ) p ( x _ { 2 } , x _ { 3 } ) \cdots p ( x _ { l - 1 } , x _ { l } ) > 0 ,
$$

where $p ( x _ { i } , x _ { j } ) , 1 \leq i , j \leq l$ is transition probability from $x _ { i }$ to $\boldsymbol { x } _ { j }$ , then there exists limit

$$
\hat { p } = \operatorname* { l i m } p ( x , t ) , \qquad x \in X
$$

independent of initial distribution $p ( 0 )$ .Probability distribution $\hat { p } = \{ \hat { p } ( x ) , x \in X \}$ is called stationary, if $p ( 0 ) = \hat { p }$ ,then $p ( t ) = \hat { p } , 0 \leq t < \infty$ ：

Let us suppose that

(i) The state change of the IDRNN only permits one neuron to change own state at a time. (ii) The set $S$ of neuron lies in $d$ —dimensional integer lattice $R ^ { d }$ ： $A \subset R ^ { d }$ isa cube with side $2 L$ in $R ^ { d }$ ，i.e. $a \in A$ such that $\boldsymbol { a } = ( a _ { 1 } , a _ { 2 } , \cdots , a _ { d } )$ ，where $a _ { i }$ is integer, （204号 $\left| a _ { i } \right| \leq L , i = 1 , 2 , \cdots , d$ ．Radiusof interaction between neuronsis $r$ ，i.e.，if （204号 $B _ { b } = \{ c : c \in A , \left| b - c \right| \leq r \}$ is a sphere with center $b$ , then when $x = ( y _ { a } , a \in A ) \in E ^ { A }$ ,we have

$$
p _ { b } ( x , \overline { { x } } ) = p _ { b } ( x , \overline { { y } } _ { b } ) = p _ { b } ( \overline { { y } } _ { b } \mid y _ { a } , a \in B _ { b } ) .
$$

if $B _ { b } \subset A$ . Where $p _ { b } ( x , \overline { { y } } _ { b } )$ is probability that over time $d t$ IDRNN lying in state $x$ changes state of own neuron $b$ from ${ \boldsymbol { y } } _ { a }$ to $\overline { { y } } _ { b }$ . Condition (5) means that probability density giving change of state of neuron $b$ is only dependent on states of neurons in IDRNN which are not more than $r$ distant from $b$ ：

In later description, the IDRNN will satisfy above-mentioned two conditions. For any neuron $b \in { \boldsymbol { R } } ^ { d }$ , density of transition probability $p _ { b } ( \overline { { y } } _ { b } \mid y _ { a } , a \in B _ { b } )$ is given and satisfies inequality

$$
0 \leq p _ { b } ( \stackrel { - } { y } _ { b } \mid y _ { a } , a \in B _ { b } ) \leq K ,
$$

for all $b \in R ^ { d } , \overline { { y } } _ { b } \in E , y _ { a } \in E , a \in B _ { b }$ and $K < \infty$ . Set of all density of transition probability （20 $\{ p _ { b } ( . | . ) , b \in R ^ { d } \}$ is called a family of density of transition probability and denoted by $\Lambda$ . Restriction on cube $A \subset R ^ { d }$ of the process $\{ x _ { b } ( t ) , t \in T , b \in R ^ { d } \}$ whose family of

transition probability is $\Lambda$ is a process $\{ x _ { b } ( t ) , t \in T , b \in A \}$ having finite number of state, if $B _ { b } \subset A$ , then when $x = ( y _ { a } , a \in A )$ , following expression

$$
p _ { b } ( x , \overline { { y } } _ { b } ) = p _ { b } ( \overline { { y } } _ { b } \mid y _ { a } , a \in B _ { b } ) \qquad x \in E ^ { A } , \quad \overline { { y } } _ { b } \in E \ ,
$$

holds.When cube $A$ is given, the restriction remains not uniquely be determined. Since for those $b \in A$ ,for which distance from $b$ to boundary of cube $A$ is smaller than $r$ ， possibilities of choosing the density by different manner still will exist. Such density is called boundary density,also satisfies following inequality

$$
0 \leq p _ { b } ( x , \overline { { y } } _ { b } ) \leq K , x \in E ^ { A } , \overline { { y } } _ { b } \in E , b \in A .
$$

If $p _ { b } ( x , \overline { { y } } _ { b } )$ only dependent on $y _ { a } \in B _ { b } \cap A ( b \in A )$ ，then we will call such boundary density local. Most natural method to give local boundary density is to set

$$
p _ { b } ( x , \overline { { y } } _ { b } ) = p _ { b } ( \overline { { y } } _ { b } \mid y _ { a } , a \in B _ { b } \cap A , y _ { a } ^ { 0 } \in E , a \in R ^ { d } \setminus A )
$$

having fixed values $y _ { a } ^ { 0 } \in E , a \in R ^ { d } \setminus A$ by any methods. When expression(9) is carried out, $( y _ { a } ^ { 0 } \in E , a \in R ^ { d } \setminus A )$ is called constant boundary condition.

# Proposition 1（Dobrushin R.L.,1971）

Supposeforany $L = 1 , 2 , \cdots$ therestrictionofneural process （204号 $\{ x ( a , t ) , a \in R ^ { d } , t \in \tau ( s e t \ o f \ t i m e ) \}$ with family of density $\Lambda$ on cube $A _ { L }$ with side $2 L$ is given. Let $\hat { x } _ { 0 } = ( y _ { a } ^ { 0 } , a \in R ^ { d } )$ —arbitrary collection of ${ y _ { a } ^ { 0 } \in E }$ ，and $p _ { x } ^ { L } ( t \vert x _ { L } ^ { 0 } ) , x \in X _ { L } , 0 \leq t \leq \infty$ ，where $X _ { \scriptscriptstyle L } = E ^ { A _ { L } }$ —space of state of the restriction on $A _ { L }$ , be probability of state $x$ on the restriction at moment $t .$ If initial distribution is chosen so that

$$
p _ { x _ { L } ^ { 0 } } ^ { L } ( 0 \left| x _ { L } ^ { 0 } \right. ) = 1 , \quad x _ { L } ^ { 0 } = ( y _ { a } ^ { 0 } , a \in A _ { L } ) \in X _ { L } ,
$$

thus, if $C \subset A _ { L } , \overline { { y } } _ { b } \in E , b \in C$ and under inspiration of expression (1) and (2), we have

$$
\mu _ { c } ^ { L } ( \stackrel { - } { y } _ { b } , b \in C , t \big | x _ { L } ^ { 0 } ) = \sum _ { x : y _ { b } = y _ { b } , b \in C } p _ { x } ^ { L } ( t \big | x _ { L } ^ { 0 } ) \quad .
$$

Then, for any $t$ $0 \leq t < \infty$ ,any finite $C \in R ^ { d }$ and any ${ \overline { { y } } } _ { b } \in E , b \in C$ , limit

$$
\mu _ { C } ^ { \infty } ( \stackrel { - } { y } _ { b } , b \in C , t \mid x _ { L } ^ { 0 } ) = \operatorname * { l i m } _ { L  \infty } \mu _ { C } ^ { L } ( \stackrel { - } { y } _ { b } , b \in C , t \mid x _ { L } ^ { 0 } ) \quad ,
$$

there exists.

In IDRNN，set of probability $\{ \mu _ { C } ^ { \infty } ( \overline { { y } } _ { b } , b \in C , t \mid x _ { L } ^ { 0 } ) , C \subset R ^ { d }$ ， $\overline { { y } } _ { b } \in E , b \in C \}$ gives consistent family of finite distribution for random field $\{ x ( b , t ) , b \in R ^ { d } , t \in \tau \}$ , and so, in accordance with well known Kolmogorov's theorem, gives probability measure $\mu ( \cdot , t | \hat { x } _ { 0 } )$ which is measurable with respect to $\hat { x } _ { 0 }$ on measurable space $\left( \boldsymbol { X } = \boldsymbol { E } ^ { S } , \boldsymbol { B } ( \boldsymbol { X } ) \right)$ . Also $\mu ( \cdot , t \mid \hat { x } _ { 0 } )$ （2 satisfies following Komogorov-Chapman equation

$$
\mu ( . , t + s \mid \hat { x } _ { 0 } ) = \int _ { X } \mu ( \cdot , s \mid \hat { x } ) \mu ( d \hat { x } , t \mid \hat { x } _ { 0 } ) , \quad \hat { x } _ { 0 } \in X , 0 \leq s < \infty , 0 \leq t < \infty .
$$

Hence probability measure $\mu ( \cdot , t | \hat { x } _ { 0 } )$ is transition probability. In accordance with Regular Markov existence theorem(M. Loéve, 1978, II)， the transition function $\mu ( \cdot , t | \hat { x } _ { 0 } )$ gives time-homogeneous Markov process in the IDRNN. It is limit Markov process.

Now we discuss correctness of expression (12)

Definition 1. (K.R.Parthasarathy, 1977).A measure $\mu$ on a metric space $X$ is said to be tight if for each $\varepsilon > 0$ there exist a compact set $K _ { \varepsilon } \subseteq X$ such that $\mu ( X - K _ { \varepsilon } ) < \varepsilon$ ：

Definition 2. A measurable space $( E , B ( E ) )$ is called a standard Borel space if there exists a metric $d$ on $E$ which turns $E$ into a complete separable metric space and is such that $B ( E )$ is the Borel $\sigma$ -algebra with respect to $d .$ （2

Lemma 1 (K.R.Parthasarathy，1967). Supposed metric space $X$ is a complete separable, then every measure on $X$ is tight.

In IDRNN, suppose $E$ is standard Borel space. Thus measurable space $( \boldsymbol { X } = \boldsymbol { E } ^ { R ^ { d } } , \boldsymbol { B } ( \boldsymbol { X } ) )$ （204号 is also standard Borel. From the two definitions 1,2 and Lemma 1，having considered subtractness of probability measure (i.e. $\mu ( X - K _ { \varepsilon } ) < \varepsilon$ can be expressed as $[ \mu ( X ) - \mu ( K _ { \varepsilon } ) ] < \varepsilon )$ , we known that there exists a number $N$ such that

$$
\left| \mu _ { C } ^ { L } ( \cdot | \cdot ) - \mu _ { C } ^ { \infty } ( \cdot | \cdot ) \right| < \varepsilon ,
$$

with $L { > } N .$ , i.e., sequence $\{ \mu _ { C } ^ { L } \} ( L = 1 , 2 , \cdots )$ converges to $\mu _ { C } ^ { \infty } ( \cdot | \cdot )$ ， $\operatorname* { l i m } _ { L \to \infty } \mu _ { C } ^ { L } ( \cdot | \cdot ) = \mu _ { C } ^ { \infty } ( \cdot | \cdot )$ ：

From preceding description, we showed in limit state of process for IDRNN to learn of environment (i.e. neuron in group of neuron $C \subset S$ takes a given value （204 $y _ { b } = { \overline { { y } } } _ { b } \in E$ )，the limit Markov process is generated in IDRNN. That is to say, environment-knowledge is expressed by means of limit Markov process in IDRNN. The limit Markov process is a limit behavior of learning process for IDRNN .

Definition 3. For any $A _ { L } = ( a _ { L } ^ { 1 } , \cdots , a _ { L } ^ { m } ) \subset R ^ { d }$ ，any $x _ { i } \in E , i = 1 , 2 , \cdots , m$ and any real function x( $\operatorname { \mathrm { 1 ) } } , a \in R ^ { d } \ \backslash A _ { L }$ ，probability distribution

$$
\lambda _ { A _ { L } } ( x _ { i } , i = 1 , 2 , \cdots , m \mid x ( a ) ) = \exp \{ - \beta U _ { A _ { L } } ( x _ { i } , i = 1 , 2 , \cdots , m ) \mid x ( a ) \} [ \Phi _ { A _ { L } } ( x ( a ) ) ] ^ { - 1 }
$$

is known as Gibbs distribution with boundary condition $x ( a )$ in $A _ { L }$ ， where

$$
\Phi _ { A _ { L } } \left( x ( a ) = \sum _ { x _ { i } \in E , i = 1 , \cdots , m } \exp \{ - \beta U _ { A _ { L } } \left( x _ { i } , i = 1 , 2 , \cdots , m \right) \vert x ( a ) \} \right.
$$

is called partition function; $0 < \beta = 1 / T < \infty$ $\boldsymbol { U } _ { A _ { L } }$ is called neural potential, it is defined as

$$
U _ { A _ { L } } ( ( x _ { i } , i = 1 , 2 , \cdots , m ) \mid x ( a ) ) = - c \sum _ { i = 1 } ^ { m } x _ { i } + \frac { 1 } { 2 } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 , j \neq i } ^ { m } x _ { i } x _ { j } U _ { A _ { L } } ( a _ { i } - a _ { j } ) + \sum _ { i = 1 } ^ { m } \sum _ { a \in R ^ { d } \backslash A _ { L } } x _ { i } x ( a ) U _ { A _ { L } } ( a _ { i } - a _ { j } )
$$

where $c$ is a constant, the chemical potential.When $\mathrm { L } \to \infty$ ,we have

$$
\operatorname* { l i m } _ { L \to \infty } \lambda _ { A _ { L } } ( \bullet | \bullet ) = \lambda ( \bullet | \bullet ) = \exp \{ - \beta U ( x _ { i } , i = 1 , 2 , \cdots \cdots , m | x _ { a } ) [ \Phi ( x _ { a } ) ] ^ { - 1 } .
$$

Under neighboringsituation,IDRNN is Markovian if and only if its limit probability measure is Gibbsian(John G. Kemeny et. al, 1992). By means of the Markov process，also i.e.by means of Gibbs probability measure，IDRNN expresses environment-knowledge.

Set of all stationary distribution of the Markov process on IDRNN—set of limit Gibbs probability measure is a nonempty compact convex set which ergodic Gibbs probability measure is extreme of (H.O. Georgii, 1988). Knowledge is eventually expressed by extreme Gibbs probability measure-ergodic Gibbs probability measure in IDRNN (Xi Guangcheng, 2OO3). Assume set of all stationary distribution in IDRNN is denoted by $M ( \mu )$ ,then we have: Suppose $\mu _ { i } , i = 1 , \cdots , n$ ， are n extreme points $\mathbf { \bar { \rho } } _ { n }$ -dimesional vector), denote n concepts memorized by IDRNN. Then any concept $\nu$ having n characteristic can be uniquelly expressed as convex combination of $\mu _ { i } , i = 1 , \cdots , n$ ，

$$
\nu = \sum _ { i = 1 } ^ { n } \alpha _ { i } \mu _ { i } , \sum _ { i = 1 } ^ { n } \alpha _ { i } = 1 .
$$

Under continuous case, we have

$$
\nu = \int \mu \omega ( d \mu )
$$

where $\omega \in \mathcal { P } ( \exp ( \mu ) , \mathrm { B } ( \exp ( \mu ) ) , \mathcal { P } ( . , . )$ denotes set of all probability measure on measurable space (.,.） (Xi Guangcheng,2003).

$\bullet$ The above conclusion is also applicable to quantum mechanical level of IDRNN.Suppose that a neuron is excited whenever a quantum particle is located inside the neuron.Having given a single particle Hilbert space $\mathsf { H }$ ,let $\mathcal { \hat { S } }$ be the boson Fock space corresponding to IDRNN.For each $\psi \in \mathsf { H }$ define a unit vector （204 $\psi ^ { \widetilde { } } \in \mathcal { F }$ ，called a coherent state.For space of measure $( \textsf { H } , \mathrm { B } ( \mathsf { H } ) , \sigma )$ （204号 there exists the states （204号 $\rho _ { . }$ _on the Fock space $\rho _ { _ { \sigma } } = \int _ { _ { H } } \tilde { | \psi | _ { } } \mathrm { \tilde { ~ } { \ s } } < \psi \tilde { | \ } \sigma ( d \psi ) .$ (21)

The states $\rho _ { \mathrm { . } }$ are called classical states and form a convex subset of the state space $\mathrm { \Delta V }$ of $\mathcal { \hat { S } }$ ：In certain conditions $\rho _ { \mathrm { . } }$ is Gibbsian.In addition， the set L of

linear combination

$$
\sum _ { l = 1 } ^ { n } \lambda _ { l } | \psi _ { \scriptscriptstyle l } ^ { \mathrm { - } } > < \psi _ { \scriptscriptstyle l } ^ { \mathrm { - } } | \ : ,
$$

where $\lambda _ { \iota } \in \mathrm { R }$ (real number) and $\psi _ { \scriptscriptstyle l } \in H$ ,is dense in $\mathrm { v }$ for the trace norm   
topology.(E.B.DAVIES,1976)   
Hence one can see“ concept “-“ consciousness” (Xi Guangcheng, 2003; Xi Guangcheng, 2007 ) is generated at particle(ion) level in the brain and is experienced at the level of the neurons from the above discussion.

# III. Ergodicity of IDRNN with random neural potential

Definition 4. Sequence $\textstyle \mu _ { n }$ of probability distribution on $X$ is called converging to distribution $\tilde { \mu }$ , if for any finite $C \subset { \cal R } ^ { d }$ and any ${ \overline { { y } } } _ { b } \in E , b \in C$ ，

$$
\operatorname* { l i m } _ { n \to \infty } \mu _ { n } ( \{ \hat { x } : y _ { b } = \overline { { y } } _ { b } , b \in C \} ) = \widetilde { \mu } ( \{ \hat { x } : y _ { b } = \overline { { y } } _ { b } , b \in C \} ) \enspace .
$$

Definition 5. The limit Markov process is called ergodic, if there exists probability distribution $\widetilde { \mu } ( \bullet )$ on $X$ such that for any ${ \hat { x } } \in X$ ，

$$
\operatorname* { l i m } _ { t  \infty } \mu ( \bullet , t \mid \hat { x } ) = \widetilde { \mu } ( \bullet ) ,
$$

in sense of definition of converging of expression (18).

# Proposition 2.

Suppose $U : X \to R$ is a random transformation, $\mathtt { R }$ set of all real number; $U ( x )$ is neural potential function corresponding to $x \in X$ . Thus we have probability space $( U , B ( U ) , Q )$ . Let $\mu ( \bullet , t \mid \hat { x } )$ ， ${ \hat { x } } \in X$ be transition function of the limit Markov process on IDRNN. Then there exists transition function $q ( \bullet , t | \hat { u } )$ induced by $\boldsymbol { \mathrm { \ell } }$ such that $q ( \bullet , t | \hat { u } ) = \mu ( \bullet , t | \hat { x } )$ ：

Proof of Proposition 2 relies on following two lemmas.

Lemma 1(K.R. Parthasurathy, 1977 ). Let $X$ be complete and separable metricspace $\mu ( \{ x \} ) = 0 , x \in X ; ( [ 0 , 1 ] , B [ 0 , 1 ] , l )$ probability space. Thus probability space $( X , B ( X ) , \mu )$ isisomorphic to $( [ 0 , 1 ] , B [ 0 , 1 ] , l )$ ：

Lemma 2(K.R. Parthasurathy,1977). Let $Q ( \{ y \} ) = 0 , y \in R$ . Then probability space（204号 $( U = R , B ( U ) , Q )$ is isomorphic to probability space $( [ 0 , 1 ] , B [ 0 , 1 ] , l \ )$

From lemma 1 and lemma 2 and having considered transitivity of the isomorphism，we find probability space $( X , B ( X ) , \mu )$ is isomorphic to the probability （204号 $( U = R , B ( U ) , Q )$ and further find proof of proposition 2. From proposition 2, we have following

Corollary 1. Suppose $U = \{ U _ { L ( t ) } , L ( t ) \subset R ^ { d } , \operatorname* { l i m } _ { t  \infty } L ( t ) = R ^ { d } \}$ is Markov process on probability space $( U = R , B ( U ) , Q )$ whose transition function is $q ( \bullet , t \mid \hat { u } )$ ． Then the limit Markov process on IDRNNisergodicifandonlyifMarkov process （204 $U = \{ U _ { L ( t ) } , L ( t ) \subset R ^ { d } , \operatorname* { l i m } _ { t \to \infty } L ( t ) = R ^ { d } \}$ is ergodic.

Corollary 2. （Bassalygo,L.A. and Dobrushin,R.L.） .For IDRNN with random neural potential there exist such constants $M { > } 0$ and $m { > } 0$ ，such that if

$$
Q ( | U _ { L ( t ) } | > M ) < m
$$

then for $\boldsymbol { \mathscr { Q } }$ —a.e. realization of U, IDRNN with random neural potential $U$ is ergodic.

Proof. From definition of probability distribution $\boldsymbol { \mathscr { Q } }$ on probability space （204号 $( U = R , B ( U ) , Q )$ and formula (15), the proof is completed.

Corollary 3. （Bassalygo,L.A. and Dobrushin,R.L.） . For IDRNN with random neural potential, if $U = \{ U _ { L ( t ) } ( x _ { L ( t ) } ) \}$ satisfies uniformly following formula

$$
\operatorname* { l i m } _ { d  \infty } Q ( | U _ { L ( t ) } | > d ) = 0
$$

for $L ( t )$ and $x _ { L ( t ) }$ ，then there exists such $\beta _ { 0 }$ that for almost all $\beta \ge \beta _ { 0 }$ and almost realization of all neural potential $U _ { L ( t ) }$ , IDRNN with random neural potential $U _ { L ( t ) }$ （204号 is ergodic.

Proof. From corollary 2 and formula (15), the proof is completed.

By the isomorphism between the state space of IDRNN with random neural potential and the space of its potential function， the studying of ergodicity of IDRNN with random neural potential is turned into the studying of ergodicity of the potential function, the resulting propositions shall be applied to the theory of ergodicity of IDRNN with random neural potential.

IV. Remark

We note that:

(1) Probabilityspace $( X , B ( X ) , \mu )$ isisomorphic toprobabilityspace (V,B(V),v） on the Fock space $\mathcal { \hat { S } }$ ,where V is state space of $\mathcal { \bar { S } }$ .Perhaps that is mathematical foundations of Gibbs sameness of representation of knowledge at quantum mechanical level and level of neurons in IDRNN.

(2) Let set of linear bounded operator(signal） on the Fock space （204号 $\mathcal { \hat { S } }$ bevonNeumannalgebra,considerquantummechanical dynamical system $\boldsymbol { C } ^ { * } - \mathrm { d }$ ynamic system $( A , S ( A ) , \alpha ( R ) )$ ,where A is von Neumann algebra, $S ( A )$ is the set of all normal states on A， $\alpha ( R )$ is a strongly continuous one - parameter group of automorphism of A.Let $( X , B ( X ) , \mu )$ be probability space on compact Hausdorffspace, $x \in X \to \omega _ { x } \in S ( A )$ （20 （20 $B ( X )$ -measurable,then （ $\Lambda ^ { * }$ defined by

$$
\Lambda ^ { * } \mu = \int _ { \stackrel { X } { X } } \omega _ { x } \mu d ( x ) , \mu \in M ( \mu )
$$

said to be a channel from $M ( \mu )$ to $S ( A )$ ，and channel $\boldsymbol { \Lambda } ^ { * }$ from S(A) to $M ( \mu )$ is defined by

$$
\Lambda ^ { ^ { * } } \phi ( \ . \ ) ^ { = } \phi ( m ( \ . \ ) ) \qquad \quad \phi \in S ( A ) ,
$$

where m is positive A-valued measure (POVM) from $B ( X )$ to $A$ with （204号 $m ( Q ) = \Lambda ( 1 _ { { \cal Q } } )$ ， $Q \in B ( X ) , 1 _ { Q }$ is indicator function(A.S. HOLEVO,1977).

The theory provided in present article has been used already innovatively (Guangcheng Xi and Jianxin Chen,2007).

# Referencesis

[1] Aorts. E., Korst. T(1989). Simulated Annealing and Boltzmann Machine. Anchor press.   
[2] Hulle V. M. M and Orban G. A. (1991). Representation and Processing in a Stochastic Neural Network. An Integrated Approach. Neural Network, 4, 643-655.   
[3] Guangcheng X.(1991). A Tentative Investigation of the Learning Process of Neural Network System. ACTA Automation Sinica, 17,311-316.   
[4] G. Tononi and Edelman. G. M.(1998). Consciousness and Complexity. Science, 282, 1846-1851.   
[5] Dobrushin. R. L.(1971). Markov Processes with a Large Number of Locally Interacting Components. Peredaci Inform., 7,70-87.   
[6] Loeve M.(1978). Probability Theory I1, $4 ^ { \mathrm { t h } }$ Edition. Springer-Verlag Neu York Inc. Corporation, Beijing.   
[7] Parthasurathy K. R.(1967,1977). Probability Measures on Metric Space. Academic Press Inc.; Introduction to Probability and Measure. First Published in the United Kingdom, the Macmillam Press.   
[8] Kemeny. J. G. etal(1992). Denumerable Markov Chains. World Publishing Corporation, Beijing.   
[9] H.O. Georgii(1988).Gibbs Measures and Phase Transitions.   
[10] Xi Guangcheng （2OO3） .Variability of structure of abstractneural automata and the ability of thought . International Journal of Cyber. and Sys., 32(3), 1549-1554,2003.   
[11]E.B.DAVIES(1976).Quantum Theory of Open Systems.   
[12] Xi Guangcheng(2OO7).Entropy -partition of Complex Systems and Emergence of Consciousness of Human Brain, Advances In Congnitive Neurodinamics,Edtiors:Rubin Wang， Fanji Gu,and Enhua Shen,939- 946,2007.   
[13] Bassalygo,L.A. and Dobrushin,R.L.(1986).Uniqueness of a Gibbs field with drandom potential:an elementary approach.Theory probab.Appl.,31,572-589.   
[14]A.S.HOLEVO.(1977).Problems in the mathematical theory of quantum communication channels,Rep. Math. Phys(12),273-278.   
[15]Guangcheng Xi and Jianxin Chen(2oo7).Phase TransitionGaused by Threshold in Random Neural Network and Its Medical Applications.D.Liu et.al.(eds.).INSNN 2007,Part II, LNCS 4492, pp. 1159-1167, 2007.

Acknowledgements

The research has been supported by National Basic Research Program of China (973 Program) under grant No.2003CB517106.