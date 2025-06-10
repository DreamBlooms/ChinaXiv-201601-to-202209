# QZNs: Quantum $Z$ -numbers

Jixiang Deng， Yong Deng\*

Abstract-Because of the efficiency of modeling fuzziness and vagueness, $\mathbf { z }$ -number plays an important role in real practice. However,Z-numbers,defined in the real number field,lack the ability to process the quantum information in quantum environment.It is reasonable to generalize $\mathbf { z }$ -number into its quantum counterpart.In this paper, we propose quantum Znumbers (QZNs),which are the quantum generalization of Znumbers.In addition，seven basic quantum fuzzy operations of QZNs and their corresponding quantum circuits are presented and illustrated by numerical examples.Moreover,based on QZNs,a novel quantum multi-attributes decision making (MADM) algorithm is proposed and applied in medical diagnosis. The results show that, with the help of quantum computation, the proposed algorithm can make diagnoses correctlyand efficiently.

Index Terms—Z-numbers, quantum computation, quantum Znumbers,quantum fuzzy operations,quantum multi-attributes decision making algorithm.

# I.INTRODUCTION

Ntea theories have been developed,such as probability theory [1], fuzzy set theory [2],[3],evidence theory [4],[5],complex evidence theory [6],[7],belief structure [8],[9],Z-numbers [10],and D numbers [11],[12].

For representing and processing vagueness in the real world, fuzzy set theory，proposed by Zadeh in 1965 [2],attracts much attentions and is widely used in many field [13].In order to better dealing with information in fuzzy environment, fuzzy set theory is extensively developed,and modifications of fuzzy sets continuously emerge，e.g.，type-2 fuzzy sets [14],intuitionistic fuzzy sets [15],and Pythagorean fuzzy sets [16].However,classical fuzzy set just models the fuzziness of uncertain information,but does not take the reliability of the processed information into consideration.Hence,considering both fuzziness and reliability, Zadeh proposed Z-numbers [10]. Lots of researches further promote the development of Znumbers,such as arithmetic of Z-numbers [17],[18],applied model of $Z$ -numbers[19],ranking of $Z$ -numbers [20],[21], and uncertainty measurements of Z-numbers [22], [23].Based on these methods,Z-number has been broadly applied in various areas,including approximate reasoning[24],expert system [25],data fusion [26],medical diagnosis [27],environmental assessment [28],and decision making [23],[29], [30].

Jixiang Deng is with Institute of Fundamental and Frontier Science, University of Electronic Science and Technology of China, Chengdu,610054, China.

YongDeng is with Institute of Fundamental and Frontier Science,University of Electronic Science and Technology of China,Chengdu,610054, China；School of Education,Shannxi Normal University,Xi'an,710062, China; School of Knowledge Science,Japan Advanced Institute of Science andTechnology,Nomi,Ishikawa 923-1211,Japan.

Corresponding author: Yong Deng.(e-mail: dengentropy $@$ uestc.edu.cn; prof.deng @hotmail.com)

Blessed with the properties of quantum mechanics such as quantum entanglement and quantum parallelism,quantum algorithms have long been known for the speedups of several problems such as factoring [31] and searching [32].Recently, quantum mechanics and quantum computation draw more and more attentions [33], [34]. Many quantum algorithms emerge and lots of classical algorithms have been generalized into their quantum counterparts,such as quantum neural networks [35],[36],quantum support vector machine [37],quantum reinforcement learning [38], quantum Parrondo's games [39]- [41],and so on [42]-[44].

As for the quantum generalization of fuzzy set theory, Pykacz proposed quantum fuzzy logic [45], [46] and Mannucci presented quantum fuzzy sets [47].In 2O16,Reiser extended intuitionistic fuzzy set into its quantum model [48].However, $Z$ -numbers are defined in the real numberfield[1O],which lack the ability of representing quantum information,so that the existing algorithm based on $Z$ -numbers cannot be applied in quantum computation.Hence,it is reasonable to extend Znumbers into Hilbert space and propose the quantum model of $Z$ -numbers.

In this paper, we propose quantum Z-numbers (QZNs), which are the quantum generalization of classical Z-numbers. A QZN consists of two quantum fuzzy sets. The first set is a quantum fuzzy restriction,and the second set measures the reliability of the first set. In addition,several basic quantum fuzzy operations of QZNs and their associated quantum circuits are proposed. Numerical examples are shown to illustrate QZN and its operations. Moreover,we present a novel quantum multi-attributes decision making (MADM) algorithm based on QZNs,which is applied in medical diagnosis.The results show that, duo to the advantage of quantum computation, the proposed algorithm can eficiently dealing with fuzziness and correctly make diagnoses with low time complexity.

The major contributions of this paper are as follows.

(1）Quantum Z-numbers (QZNs) are proposed,which are the quantum extension of classical $Z$ -numbers.   
(2）Seven quantum fuzzy operations of QZNs are proposed, which are illustrated by numerical examples.   
(3）A new quantum MADM algorithm is designed based on QZNs,and its advantage of time complexity in big data scenario is analyzed.   
(4) The proposed algorithm is applied in medical diagnosis, which shows its efficiency of handling fuzziness and the correctness of make diagnoses with low time complexity.

The rest of this paper is organized as follows.Section I briefly reviews some preliminaries. Section I proposes the quantum Z-numbers (QZNs) and the quantum fuzzy operations of QZNs.Some numerical examples are illustrated in Section IV. Section V proposes a quantum MADM algorithm based on QZNs and analyzes the time complexity of the proposed algorithm. In Section VI, the proposed algorithm is applied in medical diagnosis,and the results are analyzed and discussed Section VII makes a brief conclusion.

# II.PRELIMINARIES

Several preliminaries are briefly introduced in this section, including fuzzy sets,Z-numbers,three operations of fuzzy sets, quantum mechanics and quantum computation, quantum fuzzy sets and quantum fidelity.

# A. Fuzzy sets

Fuzzy set [2] is an efficient tool for processing fuzziness in different environment. Researchers have presented a lot of methods based on fuzzy sets,such as fuzzy distance [49],fuzzy divergence [5O],[51], fuzzy similarity [52], fuzzy entropy [53],and fuzzy information volume [54].

Let $U$ be a universe of discourse.A fuzzy set $A$ based on $U$ is a set of pairs defined as [2]:

Definition 2.1: Fuzzy sets

$$
A = \{ \langle x , \mu ( x ) \rangle | x \in U \}
$$

where $\mu ( x ) : U \to [ 0 , 1 ]$ is the membership function $( M F )$ of $A$ ,describingthemembershipdegreeofeach element $x$ to the fuzzy set $A$

# B.Z-numbers

Givena universe of discourse $U$ ，a $Z$ -numberisanordered pair of fuzzy numbers defined as follows [1O]:

Definition 2.2: $Z$ -numbers

$$
Z = ( A , B )
$$

wherethe first component $A$ isa fuzzy restriction on the realvalued uncertain variable $x \in U$ ，and the second component $B$ is a measure the reliability of component $A$

# C. Typical operations of fuzzy sets

In this subsection, several operation of fuzzy sets will be introduced, including fuzzy complements,fuzzy intersections, and fuzzyunions.

Given $x , y , z \in [ 0 , 1 ]$ ， fuzzy complements, fuzzy intersec tions,and fuzzy unions are defined as follows [3]:

Definition 2.3: Fuzzy complements

A fuzzy complement is an operation $C : [ 0 , 1 ] \ \to \ [ 0 , 1 ]$ which satisfies: (1) $C ( 0 ) = 1$ and $C ( 1 ) = 0$ (2)if $x \leq y$ then $C ( x ) \geq C ( y )$

Definition 2.4: Fuzzy intersections (t-norms) $A$ fuzzy intersection (also called t-norm）is an operation $I : [ 0 , 1 ] ^ { 2 } \to [ 0 , 1 ]$ which satisfies: (1) $I ( x , 1 ) = x$ ：(2) $i f$ $y \le z$ ，then $I ( x , y ) \ \leq \ I ( x , z )$ ：(3) $I ( x , y ) = I ( y , x )$ ： (4) $I ( x , I ( y , z ) ) = I ( I ( x , y ) , z )$

Definition 2.5: Fuzzy unions (t-conorms)

Afuzzyunion (alsocalled $t \cdot$ -conorm）is an operation $U :$ $[ 0 , 1 ] ^ { 2 } \ \to \ [ 0 , 1 ]$ which satisfies: (1) $U ( x , 0 ) ~ = ~ x$ ：(2）if$y \le z$ ，then $U ( x , y ) \leq U ( x , z ) ,$ ：(3) $U ( x , y ) = U ( y , x )$ ：(4)$U ( x , U ( y , z ) ) = U ( U ( x , y ) , z )$ ：

TABLE I: Basic quantum logic gates,circuit symbols,and their matrix representations   

<html><body><table><tr><td>Quantum gate</td><td>Circuit symbol</td><td>Matrixrepresentation</td></tr><tr><td>Hadamard gate</td><td></td><td>[i]</td></tr><tr><td>Pauli-X gate</td><td>X</td><td>[1]</td></tr><tr><td>Y-Rotation gate</td><td>R</td><td>cos 2 -sin sin COS 2</td></tr><tr><td>CCNOT gate</td><td></td><td></td></tr><tr><td>CSWAP gate</td><td>X1 y1 x2 y2 x3 y3</td><td></td></tr></table></body></html>

There are many different kinds of fuzzy complements, fuzzy intersections,and fuzzy unions.In this paper, the following operations are taken into consideration[3]:classical complement $C ( x ) = 1 - x$ ，algebraic product $I ( x , y ) = x y$ ，and algebraic sum $U ( x , y ) = x + y - x y$ ，where $x , y \in [ 0 , 1 ]$

# D.Quantum mechanics and quantum computation

According to [33],quantum mechanics is a mathematical framework for the development of physical theories.There are four postulates of quantum mechanics.

Firstly,complex vector space with inner product,namely Hilbert space denoted as $\mathcal { H }$ ，isassociated to any isolated physical system，which is known as the state space of the system. Quantum mechanical system can be fully described by state vector in Hilbert space.A qubit is the simplest quantum system,which can be described by superposition state

$$
| \psi \rangle = \alpha | 0 \rangle + \beta | 1 \rangle
$$

where $| 0 \rangle ~ = ~ [ 1 , 0 ] ^ { T }$ and $| 1 \rangle \ = \ [ 0 , 1 ] ^ { T }$ ( $T$ denotes the transpose） are the orthonormal basis. $\alpha$ and $\beta$ are complex numbers,which satisfy the normalization condition $\langle \psi | \psi \rangle =$ $\begin{array} { r } { | \alpha | ^ { 2 } + | \beta | ^ { 2 } = 1 } \end{array}$ ：

Secondly, the evolution of a closed quantum system from state $| \psi \rangle$ to $| \psi ^ { \prime } \rangle$ is described by a unitary transformation

$$
| \psi ^ { \prime } \rangle = U | \psi \rangle
$$

where $U$ is a unitary operator which satisfies $U ^ { \dagger } U = I$ In quantumcomputation,everyunitary operator has its associated quantum logic gate,which can be represented by quantum circuit symbol and matrix representation. Several basic quantum gates that this paper considers are summarize in TABLEI.For better understanding,let the input be $\left| x _ { i } \right.$ and the output be $\left| y _ { i } \right.$ shown in TABLE I. The truth tables of CCNOT gate and CSWAP gate are given in TABLE II.

TABLE II: Truth tables of CCNOT gate and CSWAP gate   

<html><body><table><tr><td colspan="2">CCNOT gate</td><td colspan="2">CSWAP gate</td></tr><tr><td>|x1x2X3)</td><td>lyiy2y3)</td><td>|x1x2x3)</td><td>ly1y2y3)</td></tr><tr><td>[000)</td><td>[000)</td><td>[000)</td><td>[000)</td></tr><tr><td>[001></td><td>[001)</td><td>[001)</td><td>[001)</td></tr><tr><td>|010)</td><td>[010)</td><td>[010)</td><td>[010)</td></tr><tr><td>[011)</td><td>[011)</td><td>[011)</td><td>[011)</td></tr><tr><td>[100)</td><td>[100)</td><td>[100)</td><td>[100)</td></tr><tr><td>[101)</td><td>[101)</td><td>[101)</td><td>[110)</td></tr><tr><td>[110)</td><td>[111)</td><td>[110)</td><td>[101)</td></tr><tr><td>|111></td><td>[110)</td><td>[111)</td><td>[111)</td></tr></table></body></html>

Thirdly,quantum measurements are described by a collectionof measurement operators.After being acted bya certain measurement operator $M _ { x }$ , the state of a quantum system $| \psi \rangle$ will collapse into state $\frac { } { \sqrt { \langle \psi | M _ { x } ^ { \dagger } M _ { x } | \psi \rangle } }$ with the probability

$$
p ( | x \rangle ) = \langle \psi | M _ { x } ^ { \dagger } M _ { x } | \psi \rangle
$$

where $\dagger$ denotes the conjugate transpose.

Fourthly，if a quantum system is composed by several subsystems,then the state space of this composite system can be represented by

$$
\bigotimes _ { i = 1 } ^ { N } | \psi _ { i } \rangle = | \psi _ { 1 } \rangle \otimes | \psi _ { 2 } \rangle \otimes \dots \dots \otimes | \psi _ { N } \rangle
$$

where $\otimes$ denotes the tensor product,and $| \psi _ { i } \rangle$ is the state of the $i$ -th component subsystem. For convenience, $\left| \psi _ { 1 } \right. \otimes \left| \psi _ { 2 } \right.$ can be written as $| \psi _ { 1 } \rangle | \psi _ { 2 } \rangle$ or $| \psi _ { 1 } \psi _ { 2 } \rangle$ . If the state of a certain system has the property that $| \psi \rangle \neq | x \rangle | y \rangle$ for all the single qubit states $| x \rangle$ and $| y \rangle$ ，such as $\textstyle { \frac { 1 } { \sqrt { 2 } } } ( \left| 0 0 \right. + \left| 1 1 \right. )$ ， then this special state is called the entangled state.

# E.Quantum fuzzy sets

Given a universe of discourse $X = \{ x _ { j } | j = 1 , 2 , \dots , N \}$ classical fuzzy membership functions $f _ { i } : X \to [ 0 , 1 ]$ ( $\overset { \cdot } { i } =$ $1 , 2 , \ldots , k )$ defined on $X$ ，and $c _ { i } \in \mathbb { C }$ $( i = 1 , 2 , \dots , k )$ ，a quantum fuzzy set(QFS） is defined as a linear combination of $N$ -dimensional quantum state,given by [47]:

Definition 2.6: Quantum fuzzy sets

$$
\left| s \right. = \sum _ { i = 1 } ^ { k } c _ { i } \left| s _ { f _ { i } } \right.
$$

where $\left| s _ { f _ { i } } \right. = \bigotimes _ { j = 1 } ^ { N } \left( \sqrt { 1 - f _ { i } \left( x _ { j } \right) } \left| 0 \right. + \sqrt { f _ { i } \left( x _ { j } \right) } \left| 1 \right. \right)$ isan $N$ -dimensional quantum state.

# $F .$ Quantum fidelity

In quantum information theory, quantum fidelity is measure of distance between quantum states [33]. Given two quantum states represented by density matrices $\rho$ and $\sigma$ ，the quantum fidelity of these two states is defined as [33]:

Definition 2.7: Quantum fidelity

$$
F ( \rho , \sigma ) = \left( \operatorname { t r } { \sqrt { { \sqrt { \rho } } \sigma { \sqrt { \rho } } } } \right) ^ { 2 }
$$

where tr denotes the trace of square matrix.

If the two states are pure state $| \psi \rangle$ and $\mathinner { | { \phi } \rangle }$ ，which means that their associated density matrices are $\rho = | \psi \rangle \langle \psi |$ and $\sigma =$ $| \phi \rangle \langle \phi |$ ,then their corresponding quantum fidelity is $F ( \rho , \sigma ) =$ $\mid \left. \psi | \phi \right. \mid ^ { 2 }$ ：

For measuring the similarity between two quantum states, Buhrman proposed a quantum computation trick called swap test,which can calculate the quantum fidelity of two quantum state [55].Its quantum circuit is shown as Fig.1.

![](images/b444095f4f32bbd9730b3cb589f83f5fd90750b4ef4fd531370967fc993e29d2.jpg)  
Fig.1:Quantum circuit for implementing quantum fidelity

The input state is $| 0 \rangle | \psi \rangle | \phi \rangle$ where $| 0 \rangle$ is the ancillary qubit. Firstly, the ancillary qubit gets through a Hadamard gate.Then, three qubits get through a CsWAP gate. If the ancillary qubit is $| 1 \rangle$ , CSWAP gate will swap $| \psi \rangle | \phi \rangle$ into $| \phi \rangle | \psi \rangle$ . Next, the ancillary qubit gets through another Hadamard gate.Finally, the output state is that

$$
\begin{array} { c }  { \displaystyle { \big | \psi _ { o u t p u t } \big \rangle = \left( H \otimes I \otimes I \right) \left( C S W A P \right) \left( H \otimes I \otimes I \right) \left( | 0 \rangle | \psi \rangle | \phi \rangle \right) } } \\ { { \displaystyle { = \frac { 1 } { 2 } | 0 \rangle ( | \psi \rangle | \phi \rangle + | \phi \rangle | \psi \rangle ) + \frac { 1 } { 2 } | 1 \rangle ( | \psi \rangle | \phi \rangle - | \phi \rangle | \psi \rangle ) } } } \end{array}
$$

An observation over the ancillary qubit will obtain the outcome $| 0 \rangle$ with the probability: $p \left( | 0 \rangle \right) ~ = ~ \frac { 1 } { 2 } + \frac { 1 } { 2 } | \langle \psi | \phi \rangle | ^ { 2 }$ where $\mid \langle \psi | \phi \rangle \mid ^ { 2 }$ is the quantum fidelity of $| \psi \rangle$ and $| \phi \rangle$

# III.QZNS:QUANTUM Z-NUMBERS

# A.The definition of quantum Z-numbers

Let $\mathbb { U }$ be a nonempty subset of the Hilbert space $\mathcal { H }$ ，which is called the quantum universe of discourse (QUOD). Given a quantum states $| \varphi \rangle \in \mathbb { U }$ ，quantum $Z$ -numbers（QZNs）are defined as follows:

Definition 3.1: Quantum $Z$ -numbers

$$
\boldsymbol { Z ^ { Q } } = ( A ^ { Q } , B ^ { Q } )
$$

which consist of two quantum sets:

$$
\begin{array} { r } { A ^ { Q } = \{ < | \varphi  , | \psi _ { \mu _ { A } }  > | \ | \varphi  \in \mathbb { U } \} } \\ { B ^ { Q } = \{ < | \varphi  , | \psi _ { \mu _ { B } }  > | \ | \varphi  \in \mathbb { U } \} } \end{array}
$$

Set $A ^ { Q }$ is a quantum fuzzy restriction of a certain quantum state $| \varphi \rangle \in \mathbb { U }$ ,and set $B ^ { Q }$ is a quantum measure of the reliability of $A ^ { Q }$ ，where $| \psi _ { \mu _ { A } }  : \mathbb { U }  \{ | \psi \rangle | | \psi \rangle \in \mathcal { H } , \langle \psi | \tau$ $\langle \psi | \psi \rangle = 1 \}$ and $| \psi _ { \mu _ { B } } \rangle : \mathbb { U } \to \{ | \psi \rangle | | \psi \rangle \in \mathcal { H } , \langle \psi | \psi \rangle = 1 \}$ are respectively the quantum membership function $( Q M F )$ of $A ^ { Q }$ and $B ^ { Q }$ definedasthevectorsinatwo-dimensionalcomplexHilbert space:

$$
\begin{array} { c } { { \left| \psi _ { \mu _ { A } } \right. = \alpha _ { \mu _ { A } } \left( \left| \varphi \right. \right) \left| 0 \right. + \beta _ { \overline { { { \mu _ { A } } } } } \left( \left| \varphi \right. \right) \left| 1 \right. \left( { Q M F o f A ^ { Q } } \right) } } \\ { { \left( 1 \psi _ { \mu _ { B } } \right. = \alpha _ { \mu _ { B } } \left( \left| \varphi \right. \right) \left| 0 \right. + \beta _ { \overline { { { \mu _ { B } } } } } \left( \left| \varphi \right. \right) \left| 1 \right. \left( { Q M F o f B ^ { Q } } \right) } } \end{array} ( 1 )
$$

where $\alpha _ { \mu _ { A } } \left( \left| \varphi \right. \right) , \beta _ { \overline { { \mu _ { A } } } } \left( \left| \varphi \right. \right) , \alpha _ { \mu _ { B } } \left( \left| \varphi \right. \right) , \beta _ { \overline { { \mu _ { B } } } } \left( \left| \varphi \right. \right) \in \mathbb { C }$ are respectively the probability amplitude of QMF $| \psi _ { \mu _ { A } } \rangle$ and $\mathinner { | { \psi _ { \mu _ { B } } } \rangle }$ for the state $| 0 \rangle$ and $| 1 \rangle$ ，which are constrained by the followingconditions:

$$
\begin{array} { r } {  \psi _ { \mu _ { A } } | \psi _ { \mu _ { A } }  = | \alpha _ { \mu _ { A } } ( | \varphi \rangle ) | ^ { 2 } + | \beta _ { \overline { { \mu _ { A } } } } ( | \varphi \rangle ) | ^ { 2 } = 1 } \\ {  \psi _ { \mu _ { B } } | \psi _ { \mu _ { B } }  = | \alpha _ { \mu _ { B } } ( | \varphi \rangle ) | ^ { 2 } + | \beta _ { \overline { { \mu _ { B } } } } ( | \varphi \rangle ) | ^ { 2 } = 1 } \end{array}
$$

For the convenience of expression,a QZN can be repre sented as:

$$
Z ^ { Q } = ( A ^ { Q } , B ^ { Q } ) = \{ < | \varphi  , | \psi _ { \mu _ { A } }  , | \psi _ { \mu _ { B } }  > | \ | \varphi  \in \mathbb { U } \}
$$

If there is only one element in the QUOD or we just focus on the QZN of one certain element in the QUOD,the QZN can be written as:

$$
Z ^ { Q } = < \left| \psi _ { \mu _ { A } } \right. , \left| \psi _ { \mu _ { B } } \right. >
$$

# B.Basic quantum fuzzy operations of QZNs

In this subsection，some basic operations of QZNs are introduced. Let $C C N O T \left( \left| x y z \right. \right)$ ， $X ( \left| x \right. )$ ，and $R _ { Y } ^ { \theta } ( | x \rangle )$ respectively denote the CCNOT gate，Pauli- $\boldsymbol { \cdot } \boldsymbol { \mathrm { X } }$ gate，and $\mathrm { Y - }$ Rotation gate in quantum computation. For two QZNs $Z _ { 1 } ^ { Q }$ and $Z _ { 2 } ^ { Q }$ defined on QUOD U, the basic operations of QZNs are defined as follows:

Definition 3.2: Basic operations of QZNs $( l )$ Inclusionrelation:

$Z _ { 1 } ^ { Q } \subseteq Z _ { 2 } ^ { Q }$ if and only if $p ( \vert 0 \rangle _ { \mu _ { A 1 } } ) ~ \le ~ p ( \vert 0 \rangle _ { \mu _ { A 2 } } )$ and $p ( \vert 0 \rangle _ { \mu _ { B 1 } } ) ~ \le ~ p ( \vert 0 \rangle _ { \mu _ { B 2 } } )$ ，where $p ( { \left| \dot { 0 } \right. } _ { \mu _ { k } } )$ is probability of $Q M F \ | \psi _ { \mu _ { k } } \rangle$ collapsing into state $| 0 \rangle$ by observation ( $k \in$ $\{ A 1 , A 2 , B 1 , B 2 \} )$ ，which is defined as

$$
\begin{array} { r l } & { p ( \left. 0 \right. _ { \mu _ { A 1 } } ) = \left. \psi _ { \mu _ { A 1 } } \right. M _ { 0 } ^ { \dagger } M _ { 0 } \left. \psi _ { \mu _ { A 1 } } \right. = \left. \alpha _ { \mu _ { A 1 } } \left( \left. \varphi \right. \right) \right. ^ { 2 } } \\ & { p ( \left. 0 \right. _ { \mu _ { A 2 } } ) = \left. \psi _ { \mu _ { A 2 } } \right. M _ { 0 } ^ { \dagger } M _ { 0 } \left. \psi _ { \mu _ { A 2 } } \right. = \left. \alpha _ { \mu _ { A 2 } } \left( \left. \varphi \right. \right) \right. ^ { 2 } } \\ & { p ( \left. 0 \right. _ { \mu _ { B 1 } } ) = \left. \psi _ { \mu _ { B 1 } } \right. M _ { 0 } ^ { \dagger } M _ { 0 } \left. \psi _ { \mu _ { B 1 } } \right. = \left. \alpha _ { \mu _ { B 1 } } \left( \left. \varphi \right. \right) \right. ^ { 2 } } \\ & { p ( \left. 0 \right. _ { \mu _ { B 2 } } ) = \left. \psi _ { \mu _ { B 2 } } \right. M _ { 0 } ^ { \dagger } M _ { 0 } \left. \psi _ { \mu _ { B 2 } } \right. = \left. \alpha _ { \mu _ { B 2 } } \left( \left. \varphi \right. \right) \right. ^ { 2 } } \end{array}
$$

in which $M _ { 0 } = \left. 0 \right. \left. 0 \right.$ is the measurement operator, and $M _ { 0 } ^ { \dag }$ means the conjugate transpose of $M _ { 0 }$

(2) Equality:（204号 $Z _ { 1 } ^ { \bar { Q } } = { \bar { Z } } _ { 2 } ^ { Q }$ if and only if $Z _ { 1 } ^ { Q } \subseteq Z _ { 2 } ^ { Q }$ and $Z _ { 2 } ^ { Q } \subseteq Z _ { 1 } ^ { Q }$ （号

# (3) Complement:

$\overline { { { Z ^ { Q } } } } = \{ < | \varphi  , | \psi _ { \mu _ { A } } ^ { C }  , | \psi _ { \mu _ { B } } ^ { C }  > | \ | \varphi  \in \mathbb { U } \}$ where $\left| \psi _ { \mu _ { A } } ^ { C } \right.$ and $\left| \psi _ { \mu _ { B } } ^ { C } \right.$ are called the complement states of $Z ^ { Q }$ ，which are defined as:

$$
\begin{array} { c } { { \left| \psi _ { \mu _ { A } } ^ { C } \right. \triangleq X \left( \left| \psi _ { \mu _ { A } } \right. \right) = \beta _ { \overline { { { \mu _ { A } } } } } \left( \left| \varphi \right. \right) \left| 0 \right. + \alpha _ { \mu _ { A } } \left( \left| \varphi \right. \right) \left| 1 \right. } } \\ { { \left| \psi _ { \mu _ { B } } ^ { C } \right. \triangleq X \left( \left| \psi _ { \mu _ { B } } \right. \right) = \beta _ { \overline { { { \mu _ { B } } } } } \left( \left| \varphi \right. \right) \left| 0 \right. + \alpha _ { \mu _ { B } } \left( \left| \varphi \right. \right) \left| 1 \right. } } \end{array}
$$

# (4)Intersection:

$Z _ { 1 } ^ { Q } \cap Z _ { 2 } ^ { Q } \ = \ \{ < | \varphi \rangle , | \psi _ { \mu _ { A 1 2 } } ^ { I } \rangle , | \psi _ { \mu _ { B 1 2 } } ^ { I } \rangle > | \ | \varphi \rangle \ \in \ \mathbb { U } \}$ where $\left| \psi _ { \mu _ { A 1 2 } } ^ { I } \right.$ and $\left| \psi _ { \mu _ { B 1 2 } } ^ { I } \right.$ arecalled the intersection states of $Z _ { 1 } ^ { Q }$ and $Z _ { 2 } ^ { Q }$ ，which are defined as:

$$
\begin{array} { r l } & { \left| \psi _ { \mu _ { A 1 2 } } ^ { I } \right. \triangleq C C N O T \left( \left( X \otimes X \otimes I \right) \left| \psi _ { \mu _ { A 1 } } \right. \left| \psi _ { \mu _ { A 2 } } \right. \left| 1 \right. \right) \left( 2 5 \right) } \\ & { = \alpha _ { \mu _ { A 1 } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { A 2 } } \left( \left| \varphi \right. \right) \left| 1 1 0 \right. + \alpha _ { \mu _ { A 1 } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { A 2 } } } } ( \left| \varphi \right. ) \left| 1 0 1 \right. } \\ & { + \beta _ { \overline { { \mu _ { A 1 } } } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { A 2 } } \left( \left| \varphi \right. \right) \left| 0 1 1 \right. + \beta _ { \overline { { \mu _ { A 1 } } } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { A 2 } } } } ( \left| \varphi \right. ) \left| 0 0 1 \right. } \\ & { \left| \psi _ { \mu _ { B 1 2 } } ^ { I } \right. \triangleq C C N O T \left( \left( X \otimes X \otimes I \right) \left| \psi _ { \mu _ { B 1 } } \right. \left| \psi _ { \mu _ { B 2 } } \right. \left| 1 \right. \right) \left( 2 6 \right) } \\ & { = \alpha _ { \mu _ { B 1 } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { B 2 } } \left( \left| \varphi \right. \right) \left| 1 1 0 \right. + \alpha _ { \mu _ { B 1 } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { B 2 } } } } ( \left| \varphi \right. ) \left| 1 0 1 \right. } \\ & { + \beta _ { \overline { { \mu _ { B 1 } } } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { B 2 } } \left( \left| \varphi \right. \right) \left| 0 1 1 \right. + \beta _ { \overline { { \mu _ { B 1 } } } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { B 2 } } } } ( \left| \varphi \right. ) \left| 0 0 1 \right. } \end{array}
$$

# (5) Union:

（204号 $Z _ { 1 } ^ { Q } \cup Z _ { 2 } ^ { Q } \ = \ \{ < | \varphi  , | \psi _ { \mu _ { A 1 2 } } ^ { U }  , | \psi _ { \mu _ { B 1 2 } } ^ { U }  > \ | \ | \varphi  \ \in \ \mathbb { U } \} .$ where $\big \vert \psi _ { \mu _ { A 1 2 } } ^ { U } \big \rangle$ and $\big | \psi _ { \mu _ { B 1 2 } } ^ { U } \big >$ are called the union states of $Z _ { 1 } ^ { Q }$ and $Z _ { 2 } ^ { Q }$ ,which are defined as:

$$
\begin{array} { r l r } & { \left| \psi _ { \mu _ { A 1 2 } } ^ { U } \right. \triangleq C C N O T \left( \left| \psi _ { \mu _ { A 1 } } \right. \left| \psi _ { \mu _ { A 2 } } \right. \left| 0 \right. \right) } & { ( 2 7 ) } \\ & { = \alpha _ { \mu _ { A 1 } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { A 2 } } \left( \left| \varphi \right. \right) \left| 0 0 0 \right. + \alpha _ { \mu _ { A 1 } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { A 2 } } } } ( \left| \varphi \right. ) \left| 0 1 0 \right. } & \\ & { + \beta _ { \overline { { \mu _ { A 1 } } } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { A 2 } } \left( \left| \varphi \right. \right) \left| 1 0 0 \right. + \beta _ { \overline { { \mu _ { A 1 } } } } ( \left| \varphi \right. ) \beta _ { \overline { { \mu _ { A 2 } } } } ( \left| \varphi \right. ) \left| 1 1 1 \right. } & \\ & { \left| \psi _ { \mu _ { B 1 2 } } ^ { U } \right. \triangleq C C N O T \left( \left| \psi _ { \mu _ { B 1 } } \right. \left| \psi _ { \mu _ { B 2 } } \right. \left| 0 \right. \right) } & { ( 2 8 ) } & \\ & { = \alpha _ { \mu _ { B 1 } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { B 2 } } \left( \left| \varphi \right. \right) \left| 0 0 0 \right. + \alpha _ { \mu _ { B 1 } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { B 2 } } } } ( \left| \varphi \right. ) \left| 0 1 0 \right. } & \\ & { + \beta _ { \overline { { \mu _ { B 1 } } } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { B 2 } } \left( \left| \varphi \right. \right) \left| 1 0 0 \right. + \beta _ { \overline { { \mu _ { B 1 } } } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { B 2 } } } } ( \left| \varphi \right. ) \left| 1 1 1 \right. } & \end{array}
$$

# (6) Convert $\pmb { Z }$ -number into QZN:

Given a classical $Z$ -number $Z = ( A , B )$ with the classical membershipfunction $\mu _ { A }$ and $\mu _ { B }$ ，its corresponding QZN is defined as: $Z ^ { Q } = \{ < | \varphi  , | \psi _ { \mu _ { A } }  , | \psi _ { \mu _ { B } }  > | \ | \varphi  \in \mathbb { U } \}$ ,where $| \psi _ { \mu _ { A } } \rangle$ and $| \psi _ { \mu _ { B } } \rangle$ are the QMF of QZN. By preparing qubit $| 0 \rangle$ and passing it through Y-Rotation gate, the QMF of QZN can be obtained:

$$
\begin{array} { c } { { \vert \psi _ { \mu _ { A } } \rangle \triangleq R _ { Y } ^ { \theta _ { \mu _ { A } } } \left( \vert 0 \rangle \right) = \sqrt { \mu _ { A } } \vert 0 \rangle + \sqrt { 1 - \mu _ { A } } \vert 1 \rangle } } \\ { { \vert \psi _ { \mu _ { B } } \rangle \triangleq R _ { Y } ^ { \theta _ { \mu _ { B } } } \left( \vert 0 \rangle \right) = \sqrt { \mu _ { B } } \vert 0 \rangle + \sqrt { 1 - \mu _ { B } } \vert 1 \rangle } } \end{array}
$$

where $\theta _ { \mu _ { A } } = 2 \operatorname { a r c c o s } \left( \sqrt { \mu _ { A } } \right)$ and $\theta _ { \mu _ { B } } = 2 \operatorname { a r c c o s } \left( \sqrt { \mu _ { B } } \right)$ are generated by the membership function ofclassical $Z$ -numbers.

# (7） Combination of QZN:

The combination of $a$ certain QZN $Z ^ { Q } \ = \ ( A ^ { Q } , B ^ { Q } )$ combines $A ^ { Q }$ and $B ^ { Q }$ ， and yields $c$ -QZN defined as: $C Z ^ { Q } =$ $\left\{ < | \varphi \rangle , | \psi _ { \mu _ { A B } } \rangle > | | \varphi \rangle \in \mathbb { U } \right\}$ ，where $| \psi _ { \mu _ { A B } } \rangle$ is called the combined state of $Z ^ { Q }$ ，which is defined as:

$$
\begin{array} { r l } & { \left| \psi _ { \mu _ { A B } } \right. \triangleq C C N O T \left( \left( X \otimes X \otimes I \right) \left| \psi _ { \mu _ { A } } \right. \left| \psi _ { \mu _ { B } } \right. \left| 1 \right. \right) \quad ( 3 1 \mathrm { ~ } } \\ & { = \alpha _ { \mu _ { A } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { B } } \left( \left| \varphi \right. \right) \left| 1 1 0 \right. + \alpha _ { \mu _ { A } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { B } } } } \left( \left| \varphi \right. \right) \left| 1 0 1 \right. } \\ & { + \beta _ { \overline { { \mu _ { A } } } } \left( \left| \varphi \right. \right) \alpha _ { \mu _ { B } } \left( \left| \varphi \right. \right) \left| 0 1 1 \right. + \beta _ { \overline { { \mu _ { A } } } } \left( \left| \varphi \right. \right) \beta _ { \overline { { \mu _ { B } } } } \left( \left| \varphi \right. \right) \left| 0 0 1 \right. } \end{array}
$$

For implementing the operations of QZNs in quantum computation, the quantum circuits of the operations (3) to（7) are illustrated in Fig.2.

# IV.NUMERICAL EXAMPLES

In this section，some numerical examples are shown to illustrate QZNs and their operations. After each example,

![](images/62159122e8df435d0fa96d10dc724f10fbf028bf4b709be27e842ad8998e3aeb.jpg)  
Fig.2:Quantum circuits of the operations (3） to（7)

we have a brief discussion.In the rest of this section,for convenience,let $k \in \{ A 1 , A 2 , B 1 , B 2 \}$

# Example 4.1:

Let two QZNs be

$$
\begin{array} { c } { { Z _ { 1 } ^ { Q } = < \sqrt { 0 . 3 } e ^ { 0 . 7 \pi i } | 0 \rangle + \sqrt { 0 . 7 } e ^ { 1 . 5 \pi i } | 1 \rangle , } } \\ { { \sqrt { 0 . 6 } e ^ { 0 . 9 \pi i } | 0 \rangle + \sqrt { 0 . 4 } e ^ { 0 . 3 \pi i } | 1 \rangle > } } \\ { { Z _ { 2 } ^ { Q } = < \sqrt { 0 . 4 } e ^ { 0 . 6 \pi i } | 0 \rangle + \sqrt { 0 . 6 } e ^ { 0 . 2 \pi i } | 1 \rangle , } } \\ { { \sqrt { 0 . 7 } e ^ { 0 . 5 \pi i } | 0 \rangle + \sqrt { 0 . 3 } e ^ { 0 . 4 \pi i } | 1 \rangle > } } \end{array}
$$

According to operation（1） of QZNs,calculate the probability: $p ( \vert 0 \rangle _ { \mu _ { A 1 } } ) = 0 . 3$ $p ( \vert 0 \rangle _ { \mu _ { A 2 } } ) = 0 . 4$ ， $p ( { \left| 0 \right. } _ { \mu _ { B 1 } } ) = 0 . 6$ $p ( { \left| 0 \right. } _ { \mu _ { B 2 } } ) ~ = ~ 0 . 7$ Because of $\widetilde { p } ( | 0 \rangle _ { \mu _ { A 1 } } ) ~ \le ~ p \bigl ( | \tilde { 0 } \rangle _ { \mu _ { A 2 } } \bigr )$ and $p ( | 0 \rangle _ { \mu _ { B 1 } } ^ {  } ) \ : \leq \ : p ( | 0 \rangle _ { \mu _ { B 2 } } )$ ，the inclusion relation of these two QZNs is $Z _ { 1 } ^ { Q } \subseteq Z _ { 2 } ^ { Q }$

This example shows that the inclusion relation of QZNs compares the probability $p ( | 0 \rangle _ { \mu _ { k } } )$ of different QMF $\mathinner { | { \psi _ { \mu _ { k } } } \rangle }$ collapsing into state $| 0 \rangle$ by observation. The larger the magnitude of the probability amplitude $\vert \alpha _ { \mu _ { k } } \vert$ is,the higher the corresponding probability $p ( \vert 0 \rangle _ { \mu _ { k } } )$ is.

# Example 4.2:

Let two QZNs be

$$
\begin{array} { c } { { Z _ { 1 } ^ { Q } = < \sqrt { 0 . 3 } e ^ { 0 . 7 \pi i } | 0 \rangle + \sqrt { 0 . 7 } e ^ { 1 . 5 \pi i } | 1 \rangle , } } \\ { { \sqrt { 0 . 6 } e ^ { 0 . 9 \pi i } | 0 \rangle + \sqrt { 0 . 4 } e ^ { 0 . 3 \pi i } | 1 \rangle > } } \\ { { Z _ { 2 } ^ { Q } = < \sqrt { 0 . 3 } e ^ { 0 . 6 \pi i } | 0 \rangle + \sqrt { 0 . 7 } e ^ { 0 . 2 \pi i } | 1 \rangle , } } \\ { { \sqrt { 0 . 6 } e ^ { 0 . 5 \pi i } | 0 \rangle + \sqrt { 0 . 4 } e ^ { 0 . 4 \pi i } | 1 \rangle > } } \end{array}
$$

Based on operation （1）of QZNs,it can be calculated that $p ( | 0 \rangle _ { \mu _ { A 1 } } ) = 0 . 3 ,$ ， $p ( | 0 \rangle _ { \mu _ { A 2 } } ) = 0 . 3$ 0.3，p(1O）μB1 （204号 0.6,p(10)μB2) $p ( | 0 \rangle _ { \mu _ { B 2 } } ^ {   } ) = 0 . 6 .$ Next, $p ( \ v u ) _ { \mu _ { A 1 } } ) \ \leq \ p ( \ v u ) _ { \mu _ { A 2 } } \ v u )$ and $p ( | 0 \rangle _ { \mu _ { B 1 } } ) ~ \leq ~ p ( | 0 \rangle _ { \mu _ { B 2 } } )$ ，s0 $Z _ { 1 } ^ { Q } \subseteq \bar { Z } _ { 2 } ^ { Q }$ .Also, $Z _ { 2 } ^ { Q ^ { \cdots } } \subseteq Z _ { 1 } ^ { Q }$ since $\bar { p ( | 0 \rangle _ { \mu _ { A 2 } } } ) \leq \dot { p ( | 0 \rangle _ { \mu _ { A 1 } } ) }$ and $p ( { \left| 0 \right. } _ { \mu _ { B 2 } } ) \leq p ( { \left| 0 \right. } _ { \mu _ { B 1 } } )$ .As a result,according to operation (2) of $\mathrm { Q Z N s }$ ，we can draw the conclusion that $\dot { Z } _ { 1 } ^ { Q } = Z _ { 2 } ^ { Q }$ ：

This example shows that the equality of QZNs compares the probability $p ( | 0 \rangle _ { \mu _ { k } } )$ of different QMF $\mathinner { | { \psi _ { \mu _ { k } } } \rangle }$ collapsing into state $| 0 \rangle$ by observation. If and only if $p ( \vert 0 \rangle _ { \mu _ { A 1 } } ) = p ( \vert 0 \rangle _ { \mu _ { A 2 } } )$ and $p ( | 0 \rangle _ { \mu _ { B 1 } } ) = p ( | 0 \rangle _ { \mu _ { B 2 } } )$ , two QZNs are equal.

Example 4.3:

Let a QZN be $Z ^ { Q } = < \sqrt { 0 . 3 } | 0 \rangle + \sqrt { 0 . 7 } | 1 \rangle$ ， $\sqrt { 0 . 6 } \left| 0 \right. +$ $\sqrt { 0 . 4 } \left| 1 \right. \ >$ ，which is converted by a classical $Z$ -number $Z _ { 1 } = < 0 . 3 , 0 . 6 >$ 、Based on the operation(3） of QZN,the complement state of this QZN can be calculated as:

$$
\left| \psi _ { \mu _ { A } } ^ { C } \right. = X \left( { \sqrt { 0 . 3 } } \left| 0 \right. + { \sqrt { 0 . 7 } } \left| 1 \right. \right) = { \sqrt { 0 . 7 } } \left| 0 \right. + { \sqrt { 0 . 3 } } \left| 1 \right.
$$

$$
\left| \psi _ { \mu _ { B } } ^ { C } \right. = X \left( \sqrt { 0 . 6 } \left| 0 \right. + \sqrt { 0 . 4 } \left| 1 \right. \right) = \sqrt { 0 . 4 } \left| 0 \right. + \sqrt { 0 . 6 } \left| 1 \right.
$$

And then，the complement of this QZN can be obtained:$\overline { { Z ^ { Q } } } = < \sqrt { 0 . 7 } \left| 0 \right. + \sqrt { 0 . 3 } \left| 1 \right. , \sqrt { 0 . 4 } \left| 0 \right. + \sqrt { 0 . 6 } \left| 1 \right. >$ ：

When an observation is performed over $\left| \psi _ { \mu _ { A } } ^ { C } \right.$ and $\left| \psi _ { \mu _ { B } } ^ { C } \right.$ they will collapse into state $| 0 \rangle$ with the probability:

$$
\begin{array} { c } { { p ( | 0 \rangle _ { \mu _ { A } } ) = \left. \psi _ { \mu _ { A } } ^ { C } \right| M _ { 0 } ^ { \dagger } M _ { 0 } \left| \psi _ { \mu _ { A } } ^ { C } \right. = 0 . 7 } } \\ { { p ( | 0 \rangle _ { \mu _ { B } } ) = \left. \psi _ { \mu _ { B } } ^ { C } \right| M _ { 0 } ^ { \dagger } M _ { 0 } \left| \psi _ { \mu _ { B } } ^ { C } \right. = 0 . 4 } } \end{array}
$$

where $M _ { 0 } = \left. 0 \right. \left. 0 \right.$ is the measurement operator. These probabilities can be composed into a classical $Z$ -number $Z _ { 2 } = <$ $0 . 7 , 0 . 4 >$ ，which is the complement of $Z _ { 1 } = < 0 . 3 , 0 . 6 >$ based on the fuzzy complement operation [3].

This example shows that the complement of QZN can be implemented by applying Pauli-X gate. In addition， the complement of QZN is compatible with the classical complement operation of Z-number. The complement of QZN can degenerate into classical complement operation of $Z$ -number by performing an observation of the complement state and obtaining their probability of collapsing into state $| 0 \rangle$ ：

# Example 4.4:

Let two QZNs be

$$
\begin{array} { r l r } & { } & { Z _ { 1 } ^ { Q } = < \sqrt { x _ { 1 } } \left| 0 \right. + \sqrt { 1 - x _ { 1 } } \left| 1 \right. , \sqrt { x _ { 2 } } \left| 0 \right. + \sqrt { 1 - x _ { 2 } } \left| 1 \right. > } \\ & { } & { ( 4 0 } \\ & { } & { Z _ { 2 } ^ { Q } = < \sqrt { y _ { 1 } } \left| 0 \right. + \sqrt { 1 - y _ { 1 } } \left| 1 \right. , \sqrt { y _ { 2 } } \left| 0 \right. + \sqrt { 1 - y _ { 2 } } \left| 1 \right. > . } \end{array}
$$

which are converted by two classical $Z$ -numbers $Z _ { 1 } = <$ $x _ { 1 } , x _ { 2 } >$ and $Z _ { 2 } ~ = < ~ y _ { 1 } , y _ { 2 } ~ >$ .Based on the operation (4) of QZNs,the intersection states of these two QZNs are that

$$
\begin{array} { r l } & { | \psi _ { \mu _ { A 1 2 } } ^ { I } \middle > = C C N O T ( ( X \otimes X \otimes I ) | \psi _ { \mu _ { A 1 } }  | \psi _ { \mu _ { A 2 } }  | 1  ) \ ( 4 2 ) } \\ & { \qquad = \sqrt { x _ { 1 } y _ { 1 } } | 1 1 0  + \sqrt { x _ { 1 } ( 1 - y _ { 1 } ) } | 1 0 1  } \\ & { \qquad + \sqrt { ( 1 - x _ { 1 } ) y _ { 1 } } | 0 1 1  + \sqrt { ( 1 - x _ { 1 } ) ( 1 - y _ { 1 } ) } | 0 0 1  } \\ & { | \psi _ { \mu _ { B 1 2 } } ^ { I } \middle > = C C N O T ( ( X \otimes X \otimes I ) | \psi _ { \mu _ { B 1 } }  | \psi _ { \mu _ { B 2 } }  | 1  ) \ ( 4 3 ) } \\ & { \qquad = \sqrt { x _ { 2 } y _ { 2 } } | 1 1 0  + \sqrt { x _ { 2 } ( 1 - y _ { 2 } ) } | 1 0 1  } \\ & { \qquad + \sqrt { ( 1 - x _ { 2 } ) y _ { 2 } } | 0 1 1  + \sqrt { ( 1 - x _ { 2 } ) ( 1 - y _ { 2 } ) } | 0 0 1  } \end{array}
$$

Hence, the intersection of $Z _ { 1 } ^ { Q }$ and $Z _ { 2 } ^ { Q }$ is that $Z _ { 1 } ^ { Q } \cap Z _ { 2 } ^ { Q } = <$ $\left| \psi _ { \mu _ { A 1 2 } } ^ { I } \right. , \left| \psi _ { \mu _ { B 1 2 } } ^ { I } \right. >$ ，

Byperforinganbsevatiooertetidqubit, $\left| \psi _ { \mu _ { A 1 2 } } ^ { I } \right.$ and $\left| \psi _ { \mu _ { B 1 2 } } ^ { I } \right.$ will colapse into state $| 0 \rangle$ with the probability:

$$
\begin{array} { c } { { p ( \left. 0 \right. _ { \mu _ { A 1 2 } } ^ { I } ) = \left. \psi _ { \mu _ { A 1 2 } } ^ { I } \right. M _ { 0 } ^ { ( 3 ) \dagger } M _ { 0 } ^ { ( 3 ) } \left. \psi _ { \mu _ { A 1 2 } } ^ { I } \right. = x _ { 1 } y _ { 1 } } } \\ { { p ( \left. 0 \right. _ { \mu _ { B 1 2 } } ^ { I } ) = \left. \psi _ { \mu _ { B 1 2 } } ^ { I } \right. M _ { 0 } ^ { ( 3 ) \dagger } M _ { 0 } ^ { ( 3 ) } \left. \psi _ { \mu _ { B 1 2 } } ^ { I } \right. = x _ { 2 } y _ { 2 } } } \end{array}
$$

where $M _ { 0 } ^ { ( 3 ) } = I \otimes I \otimes | 0 \rangle \langle 0 |$ is the measurement operator. These probabilities can be constructed into a classical $Z \cdot$

number $Z _ { 3 } = < x _ { 1 } y _ { 1 } , x _ { 2 } y _ { 2 } >$

According to the t-norm operation [3], it can be found that the first component for $Z _ { 3 }$ ，namely $x _ { 1 } y _ { 1 }$ ,is the t-norm of the first component for $Z _ { 1 }$ and $Z _ { 2 }$ ，namely $x _ { 1 }$ and $y _ { 1 }$ ; while the second component for $Z _ { 3 }$ ，namely $x _ { 2 } y _ { 2 }$ ,is the t-norm of the second component for $Z _ { 1 }$ and $Z _ { 2 }$ ，namely $x _ { 2 }$ and $y _ { 2 }$ .To illustrate the intersection of QZNs and t-norm of $Z$ -numbers, the relationship of $x _ { 1 } , y _ { 1 } , x _ { 1 } y _ { 1 }$ ，and the relationship of $x _ { 2 }$ $y _ { 2 } , x _ { 2 } y _ { 2 }$ are shown in Fig. 3.

![](images/8b51f69af79290742e9c92266c3ff0c2b9c0a6f869517a2e6c123ccbd2acbdea.jpg)  
Fig.3:(a) The relationship of $x _ { 1 } , y _ { 1 } , x _ { 1 } y _ { 1 }$ ，(b） The relationship of $x _ { 2 } , y _ { 2 } , x _ { 2 } y _ { 2 }$

This example shows that the intersection of QZNs can be obtain based on CCNOT gate and Pauli-X gate.Next,the intersection of QZNs is compatible with the classical t-norm of Z-numbers [3]. The intersection of QZNs can degenerate into t-norm of Z-numbers by performing an observation over the third qubit of the intersection states and obtaining their probabilities of collapsing into state $| 0 \rangle$ ：

# Example 4.5:

Let two QZNs be

$$
\begin{array} { r } { Z _ { 1 } ^ { Q } = < \sqrt { x _ { 1 } } \left| 0 \right. + \sqrt { 1 - x _ { 1 } } \left| 1 \right. , \sqrt { x _ { 2 } } \left| 0 \right. + \sqrt { 1 - x _ { 2 } } \left| 1 \right. > } \\ { ( 4 6 ) } \\ { Z _ { 2 } ^ { Q } = < \sqrt { y _ { 1 } } \left| 0 \right. + \sqrt { 1 - y _ { 1 } } \left| 1 \right. , \sqrt { y _ { 2 } } \left| 0 \right. + \sqrt { 1 - y _ { 2 } } \left| 1 \right. > } \end{array}
$$

which are converted by two classical $Z$ -numbers $Z _ { 1 } = <$ $x _ { 1 } , x _ { 2 } \ >$ and $Z _ { 2 } ~ = < ~ y _ { 1 } , y _ { 2 } ~ >$ . According to the operation (5) of QZNs, the union states of these two QZNs are that

$$
\begin{array} { c } { { \left| \psi _ { \mu _ { A 1 2 } } ^ { U } \right. = C C N O T \left( \left| \psi _ { \mu _ { A 1 } } \right. \left| \psi _ { \mu _ { A 2 } } \right. \left| 0 \right. \right) } } \\ { { = \sqrt { x _ { 1 } y _ { 1 } } \left| 0 0 0 \right. + \sqrt { x _ { 1 } \left( 1 - y _ { 1 } \right) } \left| 0 1 0 \right. } } \\ { { + \sqrt { \left( 1 - x _ { 1 } \right) y _ { 1 } } \left| 1 0 0 \right. + \sqrt { \left( 1 - x _ { 1 } \right) \left( 1 - y _ { 1 } \right) } \left| 1 \right. } } \\ { { \left| \psi _ { \mu _ { A 1 2 } } ^ { U } \right. = C C N O T \left( \left| \psi _ { \mu _ { B 1 } } \right. \left| \psi _ { \mu _ { B 2 } } \right. \left| 0 \right. \right) } } \\ { { = \sqrt { x _ { 2 } y _ { 2 } } \left| 0 0 0 \right. + \sqrt { x _ { 2 } \left( 1 - y _ { 2 } \right) } \left| 0 1 0 \right. } } \\ { { + \sqrt { \left( 1 - x _ { 2 } \right) y _ { 2 } } \left| 1 0 0 \right. + \sqrt { \left( 1 - x _ { 2 } \right) \left( 1 - y _ { 2 } \right) } \left| 1 \right. } } \end{array}
$$

As a result, the union of $Z _ { 1 } ^ { Q }$ and $Z _ { 2 } ^ { Q }$ is that $Z _ { 1 } ^ { Q } \cup Z _ { 2 } ^ { Q } = <$ $\left| \psi _ { \mu _ { A 1 2 } } ^ { U } \right. , \left| \psi _ { \mu _ { B 1 2 } } ^ { U } \right. >$ ，

After observing over the third qubit, $\left| \psi _ { \mu _ { A 1 2 } } ^ { U } \right.$ and $\left| \psi _ { \mu _ { B 1 2 } } ^ { U } \right.$ collapse into state $| 0 \rangle$ with the probability:

$$
\begin{array} { c } { { p ( | 0 \rangle _ { \mu _ { A 1 2 } } ^ { U } ) = \left. \psi _ { \mu _ { A 1 2 } } ^ { U } \right| M _ { 0 } ^ { ( 3 ) \dagger } M _ { 0 } ^ { ( 3 ) } \left| \psi _ { \mu _ { A 1 2 } } ^ { U } \right. } } \\ { { = x _ { 1 } y _ { 1 } + x _ { 1 } ( 1 - y _ { 1 } ) + ( 1 - x _ { 1 } ) y _ { 1 } = x _ { 1 } + y _ { 1 } - x _ { 1 } y _ { 1 } } } \\ { { p ( | 0 \rangle _ { \mu _ { B 1 2 } } ^ { U } ) = \left. \psi _ { \mu _ { B 1 2 } } ^ { U } \right| M _ { 0 } ^ { ( 3 ) \dagger } M _ { 0 } ^ { ( 3 ) } \left| \psi _ { \mu _ { B 1 2 } } ^ { U } \right. } } \\ { { = x _ { 2 } y _ { 2 } + x _ { 2 } ( 1 - y _ { 2 } ) + ( 1 - x _ { 2 } ) y _ { 2 } = x _ { 2 } + y _ { 2 } - x _ { 2 } y _ { 2 } } } \end{array} \nonumber
$$

where $M _ { 0 } ^ { ( 3 ) } = I \otimes I \otimes | 0 \rangle \langle 0 |$ is the measurement operator. These probabilities can be composed into a classical $Z$ -number $Z _ { 3 } = < x _ { 1 } + y _ { 1 } - x _ { 1 } y _ { 1 } , x _ { 2 } + y _ { 2 } - x _ { 2 } y _ { 2 } >$

Based on the t-conorm operation [3],it can be found that the first component for $Z _ { 3 }$ ，namely $x _ { 1 } + y _ { 1 } - x _ { 1 } y _ { 1 }$ ,is the $\mathbf { t } -$ （204 conorm of the first component for $Z _ { 1 }$ and $Z _ { 2 }$ ，namely $x _ { 1 }$ and $y _ { 1 }$ ; while the second component for $Z _ { 3 }$ , namely $x _ { 2 } + y _ { 2 } - x _ { 2 } y _ { 2 }$ ， is the t-norm of the second component for $Z _ { 1 }$ and $Z _ { 2 }$ ,namely $x _ { 2 }$ and $y _ { 2 }$ . To illustrate the union of QZNs and t-conorm of $Z$ -numbers,the relationship of $x _ { 1 }$ ， $y _ { 1 }$ ， $x _ { 1 } + y _ { 1 } - x _ { 1 } y _ { 1 }$ ,and the relationship of $x _ { 2 } , y _ { 2 } , x _ { 2 } + y _ { 2 } - x _ { 2 } y _ { 2 }$ are shown in Fig. 4.

![](images/bb259af21204e49e772abcbc802bdab298d15ee10d3759208f1265ed4f359e7a.jpg)  
Fig. 4: (a) The relationship of $x _ { 1 } , y _ { 1 } , x _ { 1 } + y _ { 1 } - x _ { 1 } y _ { 1 }$ (b) The relationship of $x _ { 2 }$ ， $y _ { 2 }$ ， $x _ { 2 } + y _ { 2 } - x _ { 2 } y _ { 2 }$ ：

This example shows that the union of QZNs can be obtain based on CCNOT gate.In addition，the union of QZNs is compatible with the classical t-conorm of Z-numbers [3].The union of QZNs will degenerate into t-norm of $Z$ -numbers under the condition of an observation over the third qubit of the union states and obtaining their probabilities of collapsing into state $| 0 \rangle$ ：

# Example 4.6:

Let a classical $Z$ -number be $Z = < 0 . 5 , 0 . 7 5 >$ According to operation (6) of QZN,we can obtain that:

$$
\begin{array} { l } { \displaystyle \theta _ { \mu _ { A } } = \operatorname { 2 a r c } \cos \left( \sqrt { 0 . 5 } \right) = \frac 1 2 \pi } \\ { \displaystyle \theta _ { \mu _ { B } } = \operatorname { 2 a r c } \cos \left( \sqrt { 0 . 7 5 } \right) = \frac 1 3 \pi } \end{array}
$$

Based on Y-Rotation gate,we can get the QMF of this $Z \cdot$ number :

$$
\begin{array} { l } { { \vert \psi _ { \mu _ { A } } \rangle = R _ { Y } ^ { \theta _ { \mu _ { A } } } \left( \vert 0 \rangle \right) = \sqrt { 0 . 5 } \vert 0 \rangle + \sqrt { 0 . 5 } \vert 1 \rangle } } \\ { { \vert \psi _ { \mu _ { B } } \rangle = R _ { Y } ^ { \theta _ { \mu _ { B } } } \left( \vert 0 \rangle \right) = \sqrt { 0 . 7 5 } \vert 0 \rangle + \sqrt { 0 . 2 5 } \vert 1 \rangle } } \end{array}
$$

Then the corresponding QZN of this classical $Z$ -number is that $Z ^ { Q } = < \sqrt { 0 . 5 } | 0 \rangle + \sqrt [ 5 ] { 0 . 5 } | 1 \rangle , \sqrt { 0 . 7 5 } | 0 \rangle + \sqrt { 0 . 2 5 } | 1 \rangle > .$ （204号

This example shows that a classical $Z$ -number can be converted into QZN by implementing Y-Rotation gate.

# Example 4.7:

Given a QZN $Z ^ { Q } \ = < \ \sqrt { x } \left| 0 \right. \ + \ \sqrt { 1 - x } \left| 1 \right. , \sqrt { y } \left| 0 \right. \ +$ $\sqrt { 1 - y } \left| 1 \right. >$ which is converted a classical $Z$ -number $Z = <$ $x , y >$ ,the combined state of this QZN can be calculated by operation(7) of QZN:

$$
\begin{array} { r l r } {  \psi _ { \mu _ { A B } }  = C C N O T ( ( X \otimes X \otimes I )  \psi _ { \mu _ { A } }   \psi _ { \mu _ { B } }   1  ) } & { } & { ( 5  } \\ { = \sqrt { x y }  1 1 0  + \sqrt { x ( 1 - y ) }  1 0 1   } & { } & \\ {  + \sqrt { ( 1 - x ) y }  0 1 1  + \sqrt { ( 1 - x ) ( 1 - y ) }  0 0 1   } \end{array}
$$

Then the $\mathsf { c - Q Z N }$ of this QZNis that $\begin{array} { r l } { C Z ^ { Q } } & { { } = < } \end{array}$ $\begin{array}{c} \begin{array} { r c r c r } { { \sqrt { x y } | 1 1 0 \rangle } } & { { + } } & { { \sqrt { x \left( 1 - y \right) } | 1 0 1 \rangle } } & { { + } } & { { \sqrt { \left( 1 - x \right) y } | 0 1 1 \rangle } } \end{array} ~ + ~ \sqrt { \left( 1 - x \right) y } | 1 1 0 \rangle ~ + ~ \sqrt { \left( 1 - x \right) y } | 1 1 0 \rangle ~ - ~   \end{array}$ $\sqrt { \left( 1 - x \right) \left( 1 - y \right) \left| 0 0 1 \right. } >$ ,which is actually a quantum fuzzy set (QFS) [47].It shows that QZN can degenerate into QFS by applying the combination of QZN.

An observation over the third qubit makes $| \psi _ { \mu _ { A B } } \rangle$ collapsing into state $| 0 \rangle$ and $| 1 \rangle$ with the probability:

$$
\begin{array} { l } { { p ( | 0 \rangle _ { \mu _ { A B } } ) = \langle \psi _ { \mu _ { A B } } | M _ { 0 } ^ { ( 3 ) \dagger } M _ { 0 } ^ { ( 3 ) } | \psi _ { \mu _ { A B } } \rangle = x y } } \\ { { p ( | 1 \rangle _ { \mu _ { A B } } ) = \langle \psi _ { \mu _ { A B } } | M _ { 1 } ^ { ( 3 ) \dagger } M _ { 1 } ^ { ( 3 ) } | \psi _ { \mu _ { A B } } \rangle = 1 - x y } } \end{array}
$$

where $M _ { 0 } ^ { ( 3 ) } = I \otimes I \otimes | 0 \rangle \langle 0 |$ and $M _ { 1 } ^ { ( 3 ) } = I \otimes I \otimes | 1 \rangle \langle 1 |$ are the measurement operators.

Because $x$ and $y$ are the first membership function and the second membership function of $Z ~ = < ~ x , y ~ >$ $p ( \left. 0 \right. _ { \mu _ { A B } } ) = x y$ can be seen as a combination of $Z$ -numbers, and $p ( \tilde { | 1 \rangle } _ { \mu _ { A B } } ) = 1 - x y$ can be seen as a negation of the combination of $Z .$ -numbers.In specific, $x y$ can be interpreted that $x$ is discounted by $y$ ，and $1 - x y$ is the negation of $x y$ To illustrate,the relationship of $x , y , x y$ ,and the relationship of $x , y , 1 - x y$ are shown in Fig. 5.

![](images/f80b869d2c38fb0d6d37cd937c925979453a21281be55f0ede9a3f6715f50081.jpg)  
Fig.5: (a) The relationship of $x , y , x y$ (b） The relationship of $x , y , 1 - x y$

This example shows that the combination of QZN is based on CCNOT gate and Pauli-X gate.Moreover, the combination of QZN can degenerate into the combination of $Z$ -number by observing over the third qubit of the combined state and obtaining the probabilities of collapsing into state $| 0 \rangle$ and $| 1 \rangle$

# V.QZN-BASED QUANTUMMULTI-ATTRIBUTES DECISION MAKINGALGORITHM

Making decision among different schemes with multiattributes has attracted many attentions.Researchers have proposed lots of multi-attributes decision making (MADM) algorithm based on various methods,such as soft likelihood functions [56],fuzzy set theory [57],evidence theory [58], Z-numbers [20],[30],D-numbers [59],distance [23],and divergence [6O].Because of the significance of the theoretical and practical use,MADM algorithms have been applied in risk analysis [61], [62], quality goals evaluation [63],and medical diagnosis [51], [64].

In this section，we propose a novel quantum MADM algorithm based on QZNs.Next, the time complexity of the proposed algorithm is analyzed.

# A.TheproposedQZN-based quantumMADMalgorithm

Assume that there are $M$ samples,and each sample has $K$ attributes.These samples are evaluated by experts or sensors, which are expressed by classical Z-numbers.Assume that there exists $N$ references of these samples,each reference contains $K$ attributes.These references are derived from big data and statistic,which are also expressed by classical Z-numbers.The aim is to classify the $M$ samples and match them to the $N$ references.It should be noted that the numberof theattributes of samples is equal to that of references,while the number of samples may not be equal to that of references.

Let $S$ denotes the UOD of all the samples,and $S _ { i j } \in S$ denotes the $i$ -th sample and its $j$ -th attribute，where $\begin{array} { r l } { i { \bf \Psi } } & { { } = { \bf { \Psi } } } \end{array}$ $1 , 2 , \ldots , M$ and $j = 1 , 2 , \dots , K$ Let $R$ denotes the UOD of all the references, and $R _ { x y } \in R$ denotes the $x$ -th reference and its $y$ -th attribute,where $x = 1 , 2$ ，.， $N$ and $y = 1 , 2 , \ldots , K$ Then,the proposed algorithm proceeds as the following steps. Step (1): Convert $\mathbf { Z }$ -numbers into SZM and RZM.

Input the classical $Z$ -numbers of the samples $Z _ { S _ { i j } }$ and references $Z _ { R _ { i j } }$ ，and convert them into sample $Z$ -numbers matrix(SZM) and reference $Z$ -numbers matrix (RZM):

$$
\begin{array} { r } { \boldsymbol { S Z M } = \left[ \overrightarrow { \pmb { Z } _ { S _ { 1 } } } \quad \overrightarrow { \pmb { Z } _ { S _ { 2 } } } \quad . . . \quad \overrightarrow { \pmb { Z } _ { S _ { i } } } \quad . . . \quad \overrightarrow { \pmb { Z } _ { S _ { M } } } \right] ^ { T } } \\ { \boldsymbol { R Z M } = \left[ \overrightarrow { \pmb { Z } _ { R _ { 1 } } } \quad \overrightarrow { \pmb { Z } _ { R _ { 2 } } } \quad . . . \quad \overrightarrow { \pmb { Z } _ { R _ { x } } } \quad . . . \quad \overrightarrow { \pmb { Z } _ { R _ { N } } } \right] ^ { T } } \end{array}
$$

in which

$$
\begin{array} { r l } & { \overrightarrow { Z _ { S _ { i } } } = \left( \begin{array} { l } { Z _ { S _ { i 1 } } , \ Z _ { S _ { i 2 } } , \ \dotsc , \ Z _ { S _ { i j } } , \ \dotsc , \ Z _ { S _ { i K } } } \end{array} \right) } \\ & { \overrightarrow { Z _ { R _ { x } } } = \left( \begin{array} { l } { Z _ { R _ { x 1 } } , \ Z _ { R _ { x 2 } } , \ \dotsc , \ Z _ { R _ { x y } } , \ \dotsc , \ Z _ { R _ { x K } } } \end{array} \right) } \end{array}
$$

are respectively the sample $Z$ -numbersvector(SZV）and the reference $Z$ -numbers vector (RZV)，where $Z _ { S _ { i j } } = <$ $\mu _ { A } \left( S _ { i j } \right) , \mu _ { B } \left( S _ { i j } \right) >$ and $Z _ { R _ { x y } } = < \mu _ { A } \left( R _ { x y } \right) , \mu _ { B } \left( \check { R } _ { x y } \right) >$ are respectively the $Z$ -number for the $j$ -th attribute of the $i$ -th sample,and the $Z$ -numberfor the $y$ -th attribute of the $x$ -th reference.

# Step (2): Calculate therotation angles of SZM and RZM.

Calculate the corresponding rotation angles for every element of SZM and RZM,which are defined as:

$$
\begin{array} { r l } & { \theta _ { \mu _ { A } S _ { i j } } = 2 \operatorname { a r c c o s } \left( \sqrt { \mu _ { A } \left( S _ { i j } \right) } \right) } \\ & { \theta _ { \mu _ { B } S _ { i j } } = 2 \operatorname { a r c c o s } \left( \sqrt { \mu _ { B } \left( S _ { i j } \right) } \right) } \\ & { \theta _ { \mu _ { A } R _ { x y } } = 2 \operatorname { a r c c o s } \left( \sqrt { \mu _ { A } \left( R _ { x y } \right) } \right) } \\ & { \theta _ { \mu _ { B } R _ { x y } } = 2 \operatorname { a r c c o s } \left( \sqrt { \mu _ { B } \left( R _ { x y } \right) } \right) } \end{array}
$$

where $\textit { i } \in \{ 1 , 2 , . . . , M \}$ ， $x ~ \in ~ \{ 1 , 2 , . . . , N \}$ ，and $j , y \in$ $\{ 1 , 2 , . . . , K \}$ ：

# Step (3): Calculate the similarity of SZV and RZV based on quantum fidelity coefficient.

For one SZV $\xrightarrow  \phantom { }$ and one RZV $\overrightarrow { Z _ { R _ { x } } }$ , from step (3-1) to (3-6),calculate their similarity based on quantum fidelity coefficient $F _ { i x }$ , until all $F _ { i x }$ are calculated, where $i \in \{ 1 , 2 , . . . , M \}$ and $x \in \{ 1 , 2 , . . . , N \}$ ：   
Step (3-1): Prepare quantum ground state constructed by $4 K$ dimensional qubits |o)= 0)@4K.   
Step (3-2): According to the operation (6) in Definition 3.3, convert $Z _ { S _ { i } }$ and $Z _ { R _ { x } }$ into sample QZN vector(SQZV） and

reference QZN vector (RQZV):

$$
\begin{array} { r l } & { \overrightarrow { Z _ { S _ { i } } ^ { Q } } = \left( \begin{array} { l } { Z _ { S _ { i 1 } } ^ { Q } , \ Z _ { S _ { i 2 } } ^ { Q } , \ \dotsc , \ Z _ { S _ { i j } } ^ { Q } , \ \dotsc , \ Z _ { S _ { i K } } ^ { Q } } \end{array} \right) } \\ & { \overrightarrow { Z _ { R _ { x } } ^ { Q } } = \left( \begin{array} { l } { Z _ { R _ { x 1 } } ^ { Q } , \ Z _ { R _ { x 2 } } ^ { Q } , \ \dotsc , \ Z _ { R _ { x y } } ^ { Q } , \ \dotsc , \ Z _ { R _ { x K } } ^ { Q } } \end{array} \right) } \end{array}
$$

in which $Z _ { S _ { i j } } ^ { Q } ( j = 1 , 2 , \dots , K )$ and $Z _ { R _ { x y } } ^ { Q } ( y = 1 , 2 , \dots , K )$ are respectively the QZNs for the $j$ -th attributes of the $i$ -th samples and $y$ -th attributes of the $x$ -threferences,which are defined as:

$$
\begin{array} { r l } & { \mathcal { Z } _ { S _ { t , i } } ^ { Q } = < \left| \psi _ { \theta , \mathbf { A } _ { t } S _ { t } } \right. , \ \left| \psi _ { \theta , \mathbf { A } _ { t } S _ { t } } \right. > } \\ & { \quad = < R _ { \mathrm { e } } ^ { \theta _ { \mathrm { A } _ { t } \mathbf { A } _ { t } S _ { t } } } \left( | 0 \rangle \right) , \ R _ { \mathrm { e } } ^ { \theta _ { \mathrm { A } _ { t } \mathbf { A } _ { t } S _ { t } } } \left( | 0 \rangle \right) > } \\ & { \quad = < \sqrt { \mu _ { \mathrm { A } } \left( S _ { t } \right) } \ | 0 \rangle + \sqrt { 1 - \mu _ { \mathrm { A } } \left( S _ { t } \right) } \ | 1 \rangle , } \\ & { \quad \quad \quad \quad \quad \sqrt { \mu _ { \mathrm { B } } \left( S _ { i j } \right) } \ | 0 \rangle + \sqrt { 1 - \mu _ { B } \left( S _ { t } \right) } \ | 1 \rangle > } \\ & { \mathcal { Z } _ { R _ { t , v } } ^ { Q } = < \left| \psi _ { \theta , \mathbf { A } _ { t } R _ { v } } \right. , \ \ \left| \psi _ { \theta , n _ { B } R _ { v } } \right. > } \\ & { \quad \quad = < R _ { \mathrm { e } } ^ { \theta _ { \mathrm { A } _ { t } \mathbf { A } _ { t } v } } \left( | 0 \rangle \right) , \ R _ { v _ { t } v } ^ { \theta _ { \mathrm { A } _ { t } R _ { v } } } \left( | 0 \rangle \right) > } \\ & { \quad \quad \quad = < \sqrt { \mu _ { \mathrm { A } } \left( R _ { v } \right) } \ | 0 \rangle + \sqrt { 1 - \mu _ { \mathrm { A } } \left( R _ { v } \right) } \ | 1 \rangle , } \\ & { \quad \quad \quad \quad \quad \sqrt { \mu _ { \mathrm { B } } \left( R _ { v } \right) } \ | 0 \rangle + \sqrt { 1 - \mu _ { B } \left( R _ { v } \right) } \ | 1 \rangle > } \end{array}
$$

where $\theta _ { \mu _ { A } S _ { i j } }$ and $\theta _ { \mu _ { A } R _ { x y } }$ are respectively the rotation angle for the Y-Rotation gates defined in Step (2).

The way for implementing this step in quantum circuit is to pass $| \phi _ { 0 } \rangle$ through $4 K$ Y-Rotation gates, then the quantum state of SQZV and RQZV $\left| \phi _ { 1 } \right.$ can be obtained:

$$
\left| \phi _ { 1 } \right. = \bigotimes _ { j = 1 } ^ { K } \left[ \left| \psi _ { \mu _ { A } S _ { i j } } \right. \left| \psi _ { \mu _ { B } S _ { i j } } \right. \right] \otimes \bigotimes _ { y = 1 } ^ { K } \left[ \left| \psi _ { \mu _ { A } R _ { x y } } \right. \left| \psi _ { \mu _ { B } R _ { x y } } \right. \right]
$$

Step (3-3):Based on the operation (7）of QZN，combine SQZV and obtain c-SQZV; combine RQZV and get c-RQZV. c-SQZV and c-RQZV are defined as:

$$
\begin{array} { r l } & { \overrightarrow { C Z _ { S _ { i } } ^ { Q } } = \left( \begin{array} { l } { C Z _ { S _ { i 1 } } ^ { Q } , \ C Z _ { S _ { i 2 } } ^ { Q } , \ \ldots , \ C Z _ { S _ { i j } } ^ { Q } , \ \ldots , \ C Z _ { S _ { i K } } ^ { Q } } \end{array} \right) } \\ & { \overrightarrow { C Z _ { R _ { x } } ^ { Q } } = \left( \begin{array} { l } { C Z _ { R _ { x 1 } } ^ { Q } , \ C Z _ { R _ { x 2 } } ^ { Q } , \ \ldots , \ C Z _ { R _ { x y } } ^ { Q } , \ \ldots , \ C Z _ { R _ { x K } } ^ { Q } } \end{array} \right) } \end{array}
$$

where CzQ and Cz are respectively the $\mathrm { ~ c ~ }$ -QZNs of samples and references:

$$
\begin{array} { r l } & { C Z _ { S _ { i j } } ^ { Q } = \{ <  \varphi  ,  \psi _ { \mu _ { A B } S _ { i j } }  >  \  \varphi  \in \mathbb { U } \} } \\ & { C Z _ { R _ { x y } } ^ { Q } = \{ <  \varphi  ,  \psi _ { \mu _ { A B } R _ { x y } }  >  \  \varphi  \in \mathbb { U } \} } \end{array}
$$

in which $\big | \psi _ { \mu _ { A B } S _ { i j } } \big \rangle$ and $\left| \psi _ { \mu _ { A B } R _ { x y } } \right.$ are the combined state for $\mathrm { ~ c ~ }$ -QZNs of samples and references:

$$
\begin{array} { r l } { \left| { \psi _ { \mu _ { A B } S _ { i j } } } \right. = \sqrt { \mu _ { A } \left( { S _ { i j } } \right) } \sqrt { \mu _ { B } \left( { S _ { i j } } \right) } \left| 1 1 0 \right. } & { } \\ { + \sqrt { \mu _ { A } \left( { S _ { i j } } \right) } \sqrt { 1 - \mu _ { B } \left( { S _ { i j } } \right) } \left| 1 0 1 \right. } & { } \\ { + \sqrt { 1 - \mu _ { A } \left( { S _ { i j } } \right) } \sqrt { \mu _ { B } \left( { S _ { i j } } \right) } \left| 0 1 1 \right. } & { } \\ { + \sqrt { 1 - \mu _ { A } \left( { S _ { i j } } \right) } \sqrt { 1 - \mu _ { B } \left( { S _ { i j } } \right) } \left| 0 0 1 \right. } & { } \end{array}
$$

$$
\begin{array} { r l } & { \left| { \psi _ { \mu _ { A B } R _ { x y } } } \right. = \sqrt { \mu _ { A } \left( R _ { x y } \right) } \sqrt { \mu _ { B } \left( R _ { x y } \right) } \left| 1 1 0 \right. } \\ & { \qquad + \sqrt { \mu _ { A } \left( R _ { x y } \right) } \sqrt { 1 - \mu _ { B } \left( R _ { x y } \right) } \left| 1 0 1 \right. } \\ & { \qquad + \sqrt { 1 - \mu _ { A } \left( R _ { x y } \right) } \sqrt { \mu _ { B } \left( R _ { x y } \right) } \left| 0 1 1 \right. } \\ & { \qquad + \sqrt { 1 - \mu _ { A } \left( R _ { x y } \right) } \sqrt { 1 - \mu _ { B } \left( R _ { x y } \right) } \left| 0 0 1 \right. } \end{array}
$$

The implementations of thisstep in quantum circuit are asfollows.Firstly，add $2 K$ ancillary qubits ${ | 1 \rangle } ^ { \otimes 2 K }$ to $\left| \phi _ { 1 } \right.$ Secondly，apply $4 K$ Pauli-X gate on $\hat { | \psi _ { \mu _ { A } S _ { i j } } \rangle } , ~ \hat { | \psi _ { \mu _ { B } S _ { i j } } \rangle } , ~ \hat { | \psi _ { \mu _ { A } R _ { x y } } \rangle }$ ，and $\left| \psi _ { \mu _ { B } R _ { x y } } \right.$ . Finally， apply $2 K$ CCNOT_gateon $\dot { X } \left( \left| \psi _ { \mu _ { A } } \dot { s } _ { i j } \right. \right) X \left( \left| \psi _ { \mu _ { B } } s _ { i j } \right. \right) \left| 1 \right. .$ $\left. \mathrm { \bar { \it X } } \left( \left| \psi _ { \mu _ { A } R _ { x y } } \right. \right) \mathrm { \boldsymbol { X } } \left( \left| \bar { \psi } _ { \mu _ { B } R _ { x y } } \right. \right) \left| 1 \right. \right.$ ，and obtain the quantum state $\left| \phi _ { 2 } \right.$ of c-SQZV and c-RQZV:

$$
\begin{array} { c } { { \vert \phi _ { 2 } \rangle = \displaystyle \bigotimes _ { j = 1 \atop j = 1 } ^ { K } \left[ C C N O T \left( X \left( \left. \psi _ { \mu _ { A } S _ { i j } } \right. \right) X \left( \left. \psi _ { \mu _ { B } S _ { i j } } \right. \right) \left. 1 \right. \right) \right] } } \\ { { \displaystyle \otimes _ { y = 1 } ^ { K } \left[ C C N O T \left( X \left( \left. \psi _ { \mu _ { A } R _ { x y } } \right. \right) X \left( \left. \psi _ { \mu _ { B } R _ { x y } } \right. \right) \left. 1 \right. \right) \right] } } \end{array}
$$

$$
= \bigotimes _ { j = 1 } ^ { K } \left[ \big | \psi _ { \mu _ { A B } S _ { i j } } \big \rangle \right] \otimes \bigotimes _ { y = 1 } ^ { K } \left[ \big | \psi _ { \mu _ { A B } R _ { x y } } \big \rangle \right]
$$

For convenience, let $ { \vert \psi _ { \mu _ { A B } S _ { i } } \rangle }$ and $\left| \psi _ { \mu _ { A B } R _ { x } } \right.$ denote that:

$$
\begin{array} { c } { { \displaystyle | \psi _ { \mu _ { A B } S _ { i } } \rangle = \bigotimes _ { j = 1 } ^ { K } \left| \psi _ { \mu _ { A B } S _ { i j } } \right. } } \\ { { \mathrm { } } } \\ { { \displaystyle | \psi _ { \mu _ { A B } R _ { x } } \rangle = \bigotimes _ { y = 1 } ^ { K } \left| \psi _ { \mu _ { A B } R _ { x y } } \right. } } \end{array}
$$

Then $\left| \phi _ { 2 } \right.$ can be written as $| \phi _ { 2 } \rangle = | \psi _ { \mu _ { A B } S _ { i } } \rangle | \psi _ { \mu _ { A B } R _ { x } } \rangle$ （204

Step (3-4): Based on quantum fidelity [33] and swap test [55],measure the similarity of $\mathrm { c } { \mathrm { - } } \mathrm { S } \mathrm { Q } \mathrm { Z } \mathrm { V }$ and $\mathrm { ~  ~ c ~ }$ -RQZV. Let the operation of controlled-SWAP be $C S W A P ( | x \rangle | \psi \rangle | \phi \rangle )$ $| 0 \rangle | \psi \rangle | \phi \rangle  | 0 \rangle | \psi \rangle | \phi \rangle$ and $| 1 \rangle | \psi \rangle | \phi \rangle \to | 1 \rangle | \phi \rangle | \psi \rangle$ ，where the first one-dimensional qubit $| x \rangle$ is the control qubit, while $| \psi \rangle$ and $\mathinner { | { \phi } \rangle }$ are the target qubits whose dimension can be larger than one.In order to implementing this step in quantum circuit, firstly,add an ancillary qubit $| 0 \rangle$ to $\left| \phi _ { 2 } \right.$ . Next, implement the circuit for quantum fidelity,and get the quantum state $\left| \phi _ { 3 } \right.$ ：

$$
\begin{array} { l } { { \vert \phi _ { 3 } \rangle = \left( H \otimes I \otimes I \right) \otimes \left( C S W A P \right) } } \\ { { \displaystyle \otimes \left( H \otimes I \otimes I \right) \otimes \left( \left. 0 \right. \left. \psi _ { \mu _ { A B } S _ { i } } \right. \left. \psi _ { \mu _ { A B } R _ { x } } \right. \right) } } \\ { { \displaystyle ~ = \frac { 1 } { 2 } \left. 0 \right. \left( \left. \psi _ { \mu _ { A B } S _ { i } } \right. \left. \psi _ { \mu _ { A B } R _ { x } } \right. + \left. \psi _ { \mu _ { A B } R _ { x } } \right. \left. \psi _ { \mu _ { A B } S _ { i } } \right. \right) } } \\ { { \displaystyle ~ + \frac { 1 } { 2 } \left. 1 \right. \left( \left. \psi _ { \mu _ { A B } S _ { i } } \right. \left. \psi _ { \mu _ { A B } R _ { x } } \right. - \left. \psi _ { \mu _ { A B } R _ { x } } \right. \left. \psi _ { \mu _ { A B } S _ { i } } \right. \right) } } \end{array}
$$

Step (3-5): Observe the ancillary qubit and obtain the proba bility $p ( | 0 \rangle )$

$$
\begin{array} { l } { { p (  0  ) =  \phi _ { 3 }  M _ { 0 } ^ { \dagger } M _ { 0 }  \phi _ { 3 }  } } \\ { { \mathrm { ~ ~ } = \displaystyle \frac { 1 } { 2 } + \frac { 1 } { 2 } \vert  \psi _ { \mu _ { A B } S _ { i } }  \psi _ { \mu _ { A B } R _ { x } }  \vert ^ { 2 } } } \end{array}
$$

where $\begin{array} { c c l } { M _ { 0 } } & { = } & { \left| 0 \right. \left. 0 \right| } \end{array}$ is the measurement operator,and

![](images/2fb4d9c7442228a21f70099960f0ddd765359677722e5c3dce2c9f14edd7fb6a.jpg)  
Fig. 6: Quantum circuit for Step (3-1) to (3-6)

$| \left. \psi _ { \mu _ { A B } S _ { i } } | \psi _ { \mu _ { A B } R _ { x } } \right. | ^ { 2 }$ is the quantum fidelity of $ { \vert \psi _ { \mu _ { A B } S _ { i } } \rangle }$ and $\left| \psi _ { \mu _ { A B } R _ { x } } \right.$ ：   
Step (3-6): Calculate and output the quantum fidelity coefficient $F _ { i x }$

$$
F _ { i x } = 2 \times p \left( | 0 \rangle \right) - 1 = | \langle \psi _ { \mu _ { A B } S _ { i } } | \psi _ { \mu _ { A B } R _ { x } } \rangle | ^ { 2 }
$$

# Step (4): Construct quantum fidelity matrix.

Construct quantum fidelity matrix(QFM) based on quantum fidelity coefficient $F _ { i x }$ ：：

$$
\boldsymbol { Q F M } = \left[ \begin{array} { l l l l } { F _ { 1 1 } } & { F _ { 1 2 } } & { \cdots } & { F _ { 1 N } } \\ { \quad } & { \ddots } & { \quad } & { F _ { 2 N } } \\ { \quad } & { \quad } & { \quad } & { \vdots } \\ { \quad } & { \quad } & { F _ { i x } } & { \quad } \\ { \quad } & { \quad } & { \ddots } \\ { F _ { M 1 } } & { F _ { M 2 } } & { \cdots } & { \quad } & { F _ { M N } } \end{array} \right]
$$

# Step (5): Find the index of the maximum value of $F _ { i x }$ and makedecision.

For each row of QFM $( i = 1 , 2 , \dots , M )$ ,find the index of the maximum value of quantum fidelity coefficient:

$$
x _ { i } ^ { * } = \arg \operatorname* { m a x } _ { x } \left( F _ { i x } \right)
$$

where $x ~ \in ~ \{ 1 , 2 , . . . , N \}$ .After that,make multi-attributes decision: the $i$ -th sample best matches the $\boldsymbol { x } _ { i } ^ { * }$ -th reference. For example,if $F _ { 6 4 }$ is the maximum value in the 6-th row, then the 6-th sample can be classified as the 4-th reference.

To illustrate,the implementation of the quantum circuit for Step (3-1) to (3-6) is illustrated in Fig. 6.The overall procedure of the proposed algorithm is illustrated in Fig.7.

# B.Timecomplexityoftheproposed algorithm

In this subsection, firstly,the time complexity of the proposed algorithm is analyzed.Next,we compare the time complexity of the proposed algorithm with its classical counterpart.

In steps (1） and (2)，SZM and RZM are prepared and processed in classical computer,and the time cost is mainly taken for calculating the rotation angles of SZM and RZM. SZM and RZM respectively have $M K$ and $N K$ elements, and each element is a $Z$ -number which has 2 component.As a result,the time cost of calculating the rotation angles is $2 ( M + N ) K$ ：

![](images/8dc4fc893a5d15788b233f9ea29b85206f205352f0eeec23ebf26b2c865ba294.jpg)  
Fig.7:Procedure of the proposed algorithm

Step (3）is implemented in quantum computer for $M N$ times until all $F _ { i x }$ are calculated. As is shown in Fig.6, the Y-Rotation gates，Pauli-X gates，and CCNOT gates are respectivelyimplementedin parallel,so thatthe time cost of them is 3. Since each CsWAP gate works independently, these CSWAPs can be implemented in parallel, so that the time cost of them is also 1.The time cost of the two Hadamard gate is 2.Hence,the time cost of the quantum circuit in Fig. 8 for one time is 6.To achieve the desired error tolerance $\varepsilon > 0$ ，the quantum circuit in Fig.8 should be independently implemented for $O \big ( \textstyle { \frac { 1 } { \varepsilon } } \big )$ times [55]. As a result, the total time cost of step (3) is $O \big ( \frac { 1 } { \varepsilon } M N \big )$ ：

The main time cost of steps (4) and (5) is taken to find the maximum value for each row of QFM,which is conducted in classical computer. QFM has $M$ rows,each row contains $N$ elements.The time cost for finding the maximum value among $N$ elements is $O ( N )$ [65].Therefore,the total time cost of steps (4) and (5) is $O ( M N )$ ：

Based on above analysis, the total time cost of the proposed algorithm is $O ( \textstyle { \frac { 1 } { \varepsilon } } M N + M K + N K )$

Next,we will analyze the time complexity of the classical counterpart of the proposed algorithm. Since the classical counterpart is totally conducted in classical computer, the major difference between it and the proposed algorithm is in steps (3).

Step(3) measures the similarity of $K$ -dimensional SZV and RZV based on quantum fidelity, so that its classical counterpart should also be a similarity-based or a distance-based algorithm. Several common similarity and distance measurements are Pearson correlation coefficient [66],KL divergence [67], and JS divergence [68]. Given two $K$ -dimensional vectors,the time cost for these measurements of the two vectors is at least $O ( K )$ [65].Because the step(3) is conducted for $M N$ times until the similarity of every SZV and RZV are calculated, the time cost for the classical counterpart of step (3) is $O ( M N K )$ Hence,the total time cost of the classical counterpart of the proposed method is $O ( M N K + M K + N K )$ ：

To illustrate the efficiency of the time complexity of the proposed method, the time cost of the proposed method and that of its classical counterpart are shown in Fig.8 where the number of samples $M$ and the number of references $N$ are 1OoOO，the error tolerance $\varepsilon$ is O.0o2,and the number of attributes $K$ increases from 1 to lOooo.It can be seen that, when $\textstyle K > { \frac { 1 } { \varepsilon } }$ ，with the increase of $K$ ，the time cost of the proposed method is far less than that of its classical counterpart. Because $\textstyle { \frac { 1 } { \varepsilon } }$ is irrelevant to the number of attributes $K$ ，the larger the $\dot { K }$ ，the higher efficiency the quantum circuit is.Therefore,blessed with the quantum parallelism, the proposed algorithm has the advantage of time complexity in big data scenario where $K$ is much larger than $\frac { 1 } { \varepsilon }$

![](images/50d375b9765001a665724b13256294ddc49c31eb9aef61efddf00696a796e8da.jpg)  
Fig.8:Time cost of the proposed method and that of its classical counterpart

# VI．APPLICATION IN MEDICAL DIAGNOSIS

In this section, the proposed algorithm will be applied in practical medical diagnosis problems.In addition,we will analyze and discuss about the proposed algorithm.

# A.Problem statement

Assume there are three patients:Alice,Bob,and Charlie denoted as $P _ { i }$ where $i \in \{ 1 , \ldots , 3 \}$ ,and there are four symptoms: cough, temperature, headache,and chest pain denoted as $S P _ { j }$ where $j \in \{ 1 , \ldots , 4 \}$ .Several diagnoses made by doctors are stomach problem,viral fever,malaria,and typhoid denoted as $D _ { x }$ where $x \in \{ 1 , \ldots , 4 \}$ ,and the associated symptoms of the diagnoses are denoted as $S P _ { y }$ where $y \in \{ 1 , \ldots , 4 \}$ . These three patients can be seen as three samples,and these four diagnoses can be seen as four references.All of the samples and references have four symptoms which can be seen as four attributes.Our goal is to match the three samples to the four references to make a medical diagnosis for every patient.

Let $S$ denotes the UOD of all the patients (samples),and $S _ { i j } \in S$ denotes the $i$ -th patient and his or her $j$ -th symptom (attribute)，where $i \in \{ 1 , \ldots , 3 \}$ and $j \in \{ 1 , \ldots , 4 \}$ . Let $R$ denotes the UOD of all the diagnoses (references), and $R _ { x y } \in$ $R$ denotes the $x$ -th diagnosis and its $y$ -th symptom (attribute), where $x \in \{ 1 , \ldots , 4 \}$ and $y \in \{ 1 , \ldots , 4 \}$

The relationship between $P _ { i }$ and $S P _ { j }$ and their associated reliability are described by classical fuzzy membership function，which are shown in TABLE III and TABLEIV. In addition,the relationship between $D _ { x }$ and $S P _ { y }$ and their associated reliability are also described by classical fuzzy membership,which are shown in TABLEVand TABLE VI.

TABLE II: Relationship between $P _ { i }$ and $S P _ { j }$   

<html><body><table><tr><td></td><td>SP1</td><td>SP2</td><td>SP3</td><td>SP4</td></tr><tr><td>P1</td><td>(S11,0.35)</td><td>(S12,0.43)</td><td>(S13,0.12) (S14,0.61)</td><td></td></tr><tr><td>P2</td><td>(S21,0.26)</td><td>(S22,0.49)</td><td>(S23,0.43) (S24,0.36)</td><td></td></tr><tr><td>P3</td><td>(S31,0.68)</td><td></td><td></td><td>(S32,0.73) (S33,0.12) (S34,0.08)</td></tr></table></body></html>

TABLEIV:Reliability of relationship between $P _ { i }$ and $S P _ { j }$   

<html><body><table><tr><td></td><td>SP1</td><td>SP2</td><td>SP</td><td>SP4</td></tr><tr><td>P1</td><td>(S11,0.77)</td><td>(S12,0.38)</td><td>(S13, 0.84)</td><td>(S14,0.83)</td></tr><tr><td>P2</td><td>(S21, 0.33)</td><td>(S22,0.81)</td><td>(S23,0.72)</td><td>(S24,0.28)</td></tr><tr><td>P</td><td>(S31,0.82)</td><td>(S32,0.89)</td><td>(S33,0.86)</td><td>(S34,0.61)</td></tr></table></body></html>

TABLE V: Relationship between $D _ { x }$ and $S P _ { y }$   

<html><body><table><tr><td></td><td>SP1</td><td>SP2</td><td>SP3</td><td>SP4</td></tr><tr><td>D1 D2 D3</td><td>(R11,0.41) (R21,0.84)</td><td>(R12,0.43) (R22,0.86) (R32，0.32)</td><td>(R13,0.37) (R23,0.21) (R33,0.69)</td><td>(R14,0.12) （R24,0.15）</td></tr></table></body></html>

TABLE VI: Reliability of relationship between $D _ { x }$ and $S P _ { y }$   

<html><body><table><tr><td></td><td>SP1</td><td>SP2</td><td>SP3</td><td>SP4</td></tr><tr><td>D1 D2 D3</td><td>(R11,0.83) (R21,0.95)</td><td>(R12,0.87) (R22,0.92)</td><td>(R13,0.81) (R23,0.87)</td><td>(R14,0.82) (R24,0.85)</td></tr></table></body></html>

# B.Application of the proposed algorithm

In this subsection, the proposed QZN-based MADM algorithm is applied in medical diagnose.The calculating procedures are detailed as follows.

Step (1): Construct $Z$ -numbers for samples and references, where the first component and the second component of Znumbers for samples are respectively based on TABLE II and TABLE IV,and that of $Z$ -numbers for references respectively based on TABLE V and TABLE VI. Then,convert these Znumbers into SZM andRZM:

$$
\begin{array} { r } { S Z M = \left[ \begin{array} { l l l } { \langle 0 . 3 5 , 0 . 7 7 \rangle \ \langle 0 . 4 3 , 0 . 3 8 \rangle \ \langle 0 . 1 2 , 0 . 8 4 \rangle \ \langle 0 . 6 1 , 0 . 8 3 \rangle } \\ { \langle 0 . 2 6 , 0 . 3 3 \rangle \ \langle 0 . 4 9 , 0 . 8 1 \rangle \ \langle 0 . 4 3 , 0 . 7 2 \rangle \ \langle 0 . 3 6 , 0 . 2 8 \rangle } \\ { \langle 0 . 6 8 , 0 . 8 2 \rangle \ \langle 0 . 7 3 , 0 . 8 9 \rangle \ \langle 0 . 1 2 , 0 . 8 6 \rangle \ \langle 0 . 0 8 , 0 . 6 1 \rangle } \end{array} \right] } \\ { R Z M = \left[ \begin{array} { l l l } { \langle 0 . 4 1 , 0 . 8 3 \rangle \ \langle 0 . 4 3 , 0 . 8 7 \rangle \ \langle 0 . 3 7 , 0 . 8 1 \rangle \ \langle 0 . 1 2 , 0 . 8 2 \rangle } \\ { \langle 0 . 8 4 , 0 . 9 5 \rangle \ \langle 0 . 8 6 , 0 . 9 2 \rangle \ \langle 0 . 2 1 , 0 . 8 7 \rangle \ \langle 0 . 1 5 , 0 . 8 5 \rangle } \\ { \langle 0 . 2 5 , 0 . 9 1 \rangle \ \langle 0 . 3 2 , 0 . 9 6 \rangle \ \langle 0 . 6 9 , 0 . 8 9 \rangle \ \langle 0 . 3 8 , 0 . 9 2 \rangle } \\ { \langle 0 . 1 8 , 0 . 8 1 \rangle \ \langle 0 . 2 4 , 0 . 8 7 \rangle \ \langle 0 . 1 4 , 0 . 8 4 \rangle \ \langle 0 . 7 9 , 0 . 8 5 \rangle } \end{array} \right] } \end{array}
$$

Step (2): Calculate the corresponding rotation angles for every element of SZMandRZM,which are shown in TABLE VII

TABLE VII: Rotation angles of SZM and RZM   

<html><body><table><tr><td>OμASij</td><td>j=1</td><td>j=2</td><td>j=3</td><td>j=4</td></tr><tr><td>i=1</td><td>107.458°</td><td>98.048°</td><td>139.464°</td><td>77.291°</td></tr><tr><td>i=2</td><td>118.685°</td><td>91.146°</td><td>98.048°</td><td>106.260° 147.140°</td></tr><tr><td>i=3</td><td>68.900°</td><td>62.613°</td><td>139.464°</td><td></td></tr><tr><td>0μBSij</td><td>j=1</td><td>j=2</td><td>j=3 47.156°</td><td>j=4 48.700°</td></tr><tr><td>i=1</td><td>57.316°</td><td>103.887°</td><td>63.896°</td><td>116.104°</td></tr><tr><td>i=2 i=3</td><td>109.877°</td><td>51.684°</td><td>43.946°</td><td>77.291°</td></tr><tr><td>0μARxy</td><td>50.208° y=1</td><td>38.739° y=2</td><td>y=3</td><td>y=4</td></tr><tr><td>x=1 x=2</td><td>100.370°</td><td>98.048°</td><td>105.070°</td><td>139.464° 134.427°</td></tr><tr><td>x=3</td><td>47.156° 120.000°</td><td>43.946° 111.100°</td><td>125.451° 67.666°</td><td>103.887°</td></tr><tr><td>x=4</td><td>129.792°</td><td>121.332°</td><td>136.054°</td><td>54.549°</td></tr><tr><td>OμBRxy</td><td>y=1</td><td>y=2</td><td>y=3</td><td>y=4</td></tr><tr><td>x=1</td><td>48.700°</td><td>42.269°</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>51.684°</td><td>50.208°</td></tr><tr><td>x=2</td><td></td><td>32.860°</td><td></td><td></td></tr><tr><td></td><td>25.842°</td><td></td><td>42.269°</td><td>45.573°</td></tr><tr><td>x=3</td><td>34.915°</td><td>23.074°</td><td>38.739°</td><td>32.860°</td></tr></table></body></html>

Step (3): For one SZV $\overrightarrow { z _ { S _ { i } } }$ and one RZV $\overrightarrow { Z _ { R _ { x } } }$ ，calculate theirsimilarity based on quantum fidelity coefficient $F _ { i x }$ ,until all $F _ { i x }$ are obtained,where $i \in \{ 1 , . . . , 3 \}$ and $x \in \{ 1 , . . . , 4 \}$ Each $F _ { i x }$ is calculated by the quantum circuit shown in Fig. 6, which is simulated in Qiskit and implemented in the quantum computer of IBM.

Take $\overrightarrow { z _ { s _ { 1 } } }$ and $\overrightarrow { Z _ { R _ { 2 } } }$ as an example. Their corresponding rotation angles are $\theta _ { \mu _ { A } S _ { 1 j } } , \theta _ { \mu _ { B } S _ { 1 j } } \ ( j = 1 , . . . , 4 )$ and $\theta _ { \mu _ { A } R _ { 2 y } }$ ， $\theta _ { \mu _ { B } R _ { 2 y } }$ $( y = 1 , . . . , 4 )$ , which are shown in TABLE VII. Then, assign these rotation angles to their associated Y-Rotation gates,and create the quantum circuit for calculating the quantum fidelity coefficient $F _ { 1 2 }$ of $\overrightarrow { z _ { s _ { 1 } } }$ and $\overrightarrow { Z _ { R _ { 2 } } }$ . Next, simulate the quantum circuit and get the probability: $p ( | 0 \rangle ) = 0 . 6 3 1 6$ Finally, the quantum fidelity coefficient of $\overrightarrow { Z _ { S _ { 1 } } }$ and $\overrightarrow { Z _ { R _ { 2 } } }$ can be calculated: $F _ { 1 2 } = 2 \times p \left( \left| 0 \right. \right) - 1 = 0 . 2 6 3 2$ ，

Step(4):Construct the quantum fidelity matrix(QFM) based on $F _ { i x }$ in step(3),which is shown as follows:

# C.Analysis and discussion

In this subsection,we analyze and discuss about the pro posed QZN-based algorithm compared with ZN-based algo rithm and QFS-based algorithm.

1）ComparedwithZN-basedalgorithm

For comparing QZN with $Z$ -number (ZN),the ZN-based algorithmis as follows,which isa classical counterpart of the proposed QZN-based algorithm.

Step (1):Input Z-numbers of samples of references,and construct SZM and RZM.

Step (2):Construct combined-SZM and combined-RZM:

$$
\begin{array} { r } { C S Z M = \big [ \overrightarrow { C Z _ { S _ { 1 } } } \overrightarrow { C Z _ { S _ { 2 } } } \cdots \overrightarrow { C Z _ { S _ { i } } } \cdots \overrightarrow { C Z _ { S _ { M } } } \big ] ^ { T } } \\ { C R Z M = \big [ \overrightarrow { C Z _ { R _ { 1 } } } \overrightarrow { C Z _ { R _ { 2 } } } \cdots \overrightarrow { C Z _ { R _ { x } } } \cdots \overrightarrow { C Z _ { R _ { N } } } \big ] ^ { T } } \end{array}
$$

in which

$$
\begin{array} { r l } & { \overrightarrow { C Z _ { S _ { i } } } = \left( \overrightarrow { C Z _ { S _ { i 1 } } } , \overrightarrow { C Z _ { S _ { i 2 } } } , \dotsc , \overrightarrow { C Z _ { S _ { i j } } } , \dotsc , \overrightarrow { C Z _ { S _ { i K } } } \right) } \\ & { \overrightarrow { C Z _ { R _ { x } } } = \left( \overrightarrow { C Z _ { R _ { x 1 } } } , \overrightarrow { C Z _ { R _ { x 2 } } } , \dotsc , \overrightarrow { C Z _ { R _ { x y } } } , \dotsc , \overrightarrow { C Z _ { R _ { x K } } } \right) } \end{array}
$$

are called the combined-SZV and combined-RZV,where $C Z _ { S _ { i j } } = \mu _ { A } \left( S _ { i j } \right) \mu _ { B } \left( S _ { i j } \right)$ and $C Z _ { R _ { x y } } = \mu _ { A } \left( R _ { x y } \right) \mu _ { B } \left( R _ { x y } \right)$ Step (3): Given one combined-SZV $\overrightarrow { C Z _ { S _ { i } } }$ and one combinedRZV $\overrightarrow { C Z _ { R _ { x } } }$ ，measure their similarity between based on Pearson correlation coefficient [66]:

$$
r _ { i x } = { \frac { c o v ( \overrightarrow { C Z _ { S _ { i } } } , \overrightarrow { C Z _ { R _ { x } } } ) } { \sigma _ { \overrightarrow { C Z _ { S _ { i } } } } \sigma _ { \overrightarrow { C Z _ { R _ { x } } } } } }
$$

where cov(CZ,CZR） is covariance,andz are respectively the standard deviation of $\overrightarrow { C Z _ { S _ { i } } }$ and $\overrightarrow { C Z _ { R _ { x } } }$ Step (4): Construct Pearson correlation coefficient matrix (PM) based on $r _ { i x }$ ：

$$
P M = \left[ \sum _ { \vdots } ^ { r _ { 1 1 } } \cdots r _ { 1 N } \atop \vdots \atop r _ { M 1 } \cdots r _ { M N } \right]
$$

Step (5):For each row of PM, find the index of the maximum value of $r _ { i x }$ and make decision.

Then,this ZN-based algorithm is applied in medical diag nosis,and the PM is calculated as:

$$
P M = \left[ \begin{array} { c c c } { { - 0 . 8 5 2 4 - 0 . 3 3 6 1 - 0 . 4 3 7 1 } } & { { { \bf 0 . 9 1 9 8 } } } \\ { { { \bf 0 . 5 5 8 8 } } } & { { 0 . 1 6 2 4 } } & { { 0 . 4 1 5 8 - 0 . 4 6 4 3 } } \\ { { 0 . 7 9 2 8 } } & { { { \bf 0 . 9 9 1 5 } } } & { { - 0 . 6 6 1 6 - 0 . 5 2 8 5 } } \end{array} \right]
$$

$$
Q F M = \left[ \begin{array} { c c c c } { { 0 . 5 0 4 6 } } & { { 0 . 2 6 3 2 } } & { { 0 . 3 3 6 6 } } & { { \bf 0 . 6 4 3 4 } } \\ { { \bf 0 . 4 3 8 2 } } & { { 0 . 1 7 6 8 } } & { { 0 . 2 7 0 8 } } & { { 0 . 3 1 9 8 } } \\ { { 0 . 7 1 9 4 } } & { { \bf 0 . 8 1 4 6 } } & { { 0 . 3 2 8 2 } } & { { 0 . 2 5 2 0 } } \end{array} \right]
$$

Step(5):For each row of QFM, find the maximum value of $F _ { i x }$ ，which are highlighted in bold in Eq.9O,and then make medical diagnosis based on the index of the maximum value. The medical diagnosis generated by the proposed algorithm is shown in the first row of TABLE VIII.

TABLE VII: Medical diagnoses made by three algorithms   

<html><body><table><tr><td></td><td>Alice Bob</td><td>Charlie</td></tr><tr><td>Proposed algorithm ZN-based algorithm QFS-based algorithm</td><td>Typhoid Stomach problem Viral fever Typhoid Stomach problem Viral fever TyphoidMalaria</td><td>Viral fever</td></tr></table></body></html>

where the maximum values of each row are in bold.Next, the medical diagnosis generated by the ZN-based algorithm is shown in the second row of TABLE VIII.

The diagnosis for each patient made by the ZN-based algorithm is the same as that made by the proposed algorithm, which shows that both of these two algorithms can effectively handle fuzziness and make correct medical diagnosis for different patients.However,as is discussed in Subsection $B$ of Section V, since the ZN-based algorithm is based on Pearson correlation coefficient, its total time cost is much slower than that of the proposed algorithm in big data scenario.In addition, the ZN-based algorithmis a classical algorithm,which cannot be applied in quantum information processing.

By comparison,assisted by quantum computation, the pro posed QZN-based algorithm can efficiently make medical diagnosis.Moreover, it can be extended and applied in quantum information processing under other scenario.

2）Compared with QFS-based algorithm

To compare QZN with quantum fuzzy set (QFS),QZN in the proposed algorithm is replaced by QFS,while the other procedures of the proposed algorithm remain the same. This algorithm is called the QFS-based algorithm.Then,we compare the proposed QZN-based algorithm with the QFS-based algorithm. The quantum fidelity matrix(QFM) generated by the QFS-based algorithm is that

$$
Q F M = \left[ \begin{array} { l l l } { 0 . 6 5 5 4 } & { 0 . 4 5 1 4 } & { 0 . 6 0 3 0 } & { \mathbf { 0 . 8 7 9 2 } } \\ { 0 . 8 8 3 0 } & { 0 . 4 9 0 8 } & { \mathbf { 0 . 9 0 4 4 } } & { 0 . 6 5 7 2 } \\ { 0 . 7 4 7 4 } & { \mathbf { 0 . 9 1 1 2 } } & { 0 . 3 8 9 6 } & { 0 . 2 7 9 0 } \end{array} \right]
$$

where themaximumvalues of eachroware in bold.Then, the medical diagnosis made by the QFS-based algorithm is shown in the third row of TABLE VIII.

It can be seen that the diagnosis of Bob generated by the QFS-based algorithm is different from that of the proposed algorithm.The reason is that the QFS-based algorithm does not take reliability of quantum fuzziness into consideration,so thatit makes wrong diagnosis.To be specific, the QFS-based algorithm cannotuse the reliability information in TABLEIV and TABLE VI.Its omits that the reliability for the first and the fourth symptoms ofBob are O.33 and O.28,which means that the fuzzy relationships for the first and the fourth symptoms of Bob should not be fully trusted.

By contrast,with the help of quantum sets $A ^ { Q }$ and $B ^ { Q }$ QZN can not only use $A ^ { Q }$ to represent the quantum fuzzy restriction of the elements in QUOD,but also express the reliability of $A ^ { Q }$ based on $B ^ { Q }$ , so that the proposed algorithm can make diagnoses correctly and efficiently.

Based on above discussion,compared with ZN-based algorithm and QFS-based algorithm，the advantages of the proposed algorithm are summarized in TABLE IX.

TABLE IX:Comparison of three algorithms   

<html><body><table><tr><td></td><td></td><td>Efficiency of time</td><td>Quantum information processing</td></tr><tr><td>Proposed algorithm</td><td>Correctness √</td><td>complexity √</td><td>√</td></tr><tr><td>ZN-based algorithm</td><td>√</td><td>×</td><td>×</td></tr><tr><td>QFS-based algorithm</td><td>×</td><td>√</td><td>√</td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>

# VII.CONCLUSION

Z-number proposed by Zadeh is an efficient tool for modeling uncertainty in fuzzy environment. However, Z-numbers are unable to deal with uncertain information in quantum field. Therefore,in order to equipping Z-numbers with the ability of processing quantum information, this paper generalizes Znumber into its quantum counterpart and proposes quantum Z-numbers (QZNs).

The main contributions of this paper are summarized as follows.（1) Quantum Z-numbers (QZNs) are proposed, which are the quantum extension of classical Z-numbers.A QZN consists of two quantum fuzzy sets，taking both quantum fuzzy restriction and its reliability into consideration.(2) We present several basic quantum fuzzy operations of QZNs and their associated quantum circuits,which are expounded by numerical examples.(3） A novel QZN-based quantum MADM algorithm is proposed. The analysis shows that the proposed algorithm has the advantage of time complexity in big data scenario.(4） The proposed algorithm is applied in medical diagnosis,which shows that the proposed algorithm can not only process fuzzy information efficiently but also make diagnoses correctly with low time complexity.

In the future research,we will focus on designing other quantum algorithms of QZNs,such as quantum ranking of QZNs.Besides，applying QZN and its quantum algorithms into more practical fields is also worth exploring.

# ACKNOWLEDGMENT

The work is partially supported by National Natural Science Foundation of China(Grant No.61973332), Invitational Fellowships for Research in Japan (Short-term).

# REFERENCES

[1]P.Lee,“Probability theory,”Bulletin of the London Mathematical Society,vol.12,no.4,pp.318-319,1980.   
[2] L.A. Zadeh,“Fuzzy sets” Information and control,vol.8,no.3,pp. 338-353,1965.   
[3] G.Klir and B.Yuan,Fuzzy sets and fuzzy logic.Prentice hall New Jersey,1995,vol.4.   
[4] A.P.Dempster,“Upper and lower probabilities induced by a multivalued mapping”The Annals of Mathematical Statistics，vol. 38,no.2, pp. 325-339,04 1967.   
[5] G.Shafer,A mathematical theory of evidence．Princeton university press Princeton,1976,vol.1.   
[6] F.Xiao,“Generalization of Dempster-Shafer theory:A complex mass function,Applied Intelligence,vol. 50,no.10,pp.3266-3275,2019. [7] “Ceqd:A complex mass function to predict interference effects,’IEEE Transactionson Cybernetics， p DOI: 10.1109/TCYB.2020.3040770,2020.   
[8]R.R.Yager and N.Alajlan,“Maxitive Belief Structures and Imprecise Possibility Distributions,”IEEE Transactions on Fuzzy Systems,vol.25, no.4,pp.768-774,AUG 2017.   
[9] R.R.Yager,“Fuzzy rule bases with generalized belief structure inputs," Engineering Applications of Artificial Intelligence,vol.72,pp.93-98, JUN 2018.   
[10] L.A. Zadeh,“A note on $\textbf { \em z }$ -numbers,’Information Sciences,vol.181, no.14,pp.2923-2932,2011.   
[11]P.Liu and X. Zhang,“A novel approach to multi-criteria group decisionmaking problems based on linguistic D numbers,”Computational and Applied Mathematics,vol.39,p.Article number:132,2020.   
[12]B.liu and Y.Deng,“Risk Evaluation in Failure Mode and Effects Analysis Based on D Numbers Theory,’International Journal of Computers Communications & Control,vol.14,no.5,pp.672-691, 2019.   
[13] I.Dzitac,F. G. Filip,and M.-J. Manolescu,“Fuzzy logic is not fuzzy: World-renowned computer scientist lotfi a. zadeh,”International Journal ofComputers Communications& Control,vol.12,no.6, pp.748-789, 2017.   
[14]L.A.Zadeh,“The concept of a linguistic variable and its application to approximate reasoning—i” Information sciences, vol. 8,no.3, pp. 199-249,1975.   
[15] K. T.Atanassov,“Intuitionistic fuzzy sets,”in Intuitionistic fuzzy sets. Springer,1999,pp.1-137.   
[16]R.R.Yager,“Pythagorean fuzzy subsets,”in 2Ol3 joint IFSA world congress and NAFIPS annual meeting (IFSA/NAFIPS).IEEE,2013, pp. 57-61.   
[17]R.A.Aliev,A.V.Alizadeh,and O.H.Huseynov,“The arithmetic of discrete $\textbf { z }$ -numbers,Information Sciences,vol.290,pp.134-155,2015.   
[18]R.A.Aliev,O.H.Huseynov,and L.M.Zeinalova,“The arithmetic of continuous z-numbers, Information Sciences,vol. 373,pp.441-460, 2016.   
[19]P.Patel, S.Rahimi,and E. Khorasani,“Applied z-numbers,”in 2015 Annual Conference of the North American Fuzzy Information Processing Society(NAFIPS)held jointly with 2O155th World Conference on Soft Computing (WConSC). IEEE,2015,pp.1-6.   
[20] R.A. Aliev, O. H. Huseynov,and R. Serdaroglu,“Ranking of znumbers and its application in decision making” International Journal ofInformationTechnology&Decisionakingvol.15no.p 1503-1519,2016.   
[21] A.S.A.Bakar and A. Gegov,“Multi-layer decision methodology for ranking z-numbers," International Journal ofComputational Intelligence Systems,vol.8,no.2,pp.395-406,2015.   
[22]B. Kang, Y. Deng,K. Hewage,and R. Sadiq,“A method of measuring uncertainty for $\mathbf { z }$ -number”IEEE Transactions on Fuzzy Systems,vol.27, no. 4,pp.731-738,2018.   
[23] J.-q. Wang, Y.-x. Cao,and H.-y. Zhang,“Multi-criteria decision-making method based on distance measure and choquet integral for linguistic Z-numbers, Cognitive Computation,vol. 9, no.6,pp.827-842, 2017.   
[24] R.A.Aliev,W.Pedrycz,O.H. Huseynov,and S.Z.Eyupoglu, “Approximate reasoning_on a basis of z-number-valued if-then rules,” IEEE Transactions on Fuzzy Systems,vol. 25,no.6,pp.1589-1600, 2016.   
[25]Y.Tian,L. Liu,X. Mi,and B. Kang,“Zslf:A new soft likelihood functionbasedonz-numbersanditsapplicationinexpertdecision system”IEEETransactionsonFuzzySystems,2020.   
[26]W. Jiang, C. Xie, M. Zhuang,Y.Shou,and Y.Tang,“Sensor data fusion with z-numbersand itsapplication in fault diagnosis”Sensors,vol.16 no.9,p. 1509,2016.   
[27]D.Wu, X.Liu,F. Xue,H. Zheng,Y.Shou,and W. Jiang,“A new medical diagnosis method based on z-numbers,”Applied Intelligence, vol. 48, no.4, pp. 854-867,2018.   
[28] B.Kang,P. Zhang，Z. Gao,G.Chhipi-Shrestha,K. Hewage，and R.Sadiq,“Environmental assessment under uncertainty using dempstershafer theory and $\textbf { \em z }$ -numbers,’Journal of Ambient Intelligence and HumanizedComputing,vol.11,no.5,pp.2041-2060,2020.   
[29]B.Kang,D.Wei,Y.Li,and Y.Deng,"Decision making using z-numbers under uncertain environment,” Journal of computational Information systems,vol.8, no.7, pp.2807-2814,2012.   
[30]R.A.Alievand L.M. Zeinalova,“Decision making underZinformation,’ in Human-centric decision-making models for social sciences Springer,2014,pp.233-252.   
[31]P.W. Shor,“Algorithms for quantum computation: discrete logarithms and factoring”in Proceedings 35th annual symposium on foundations of computer science. Ieee,1994, pp.124-134.   
[32]L.K.Grover,“A fast quantum mechanical algorithm for database search,’in Proceedings of the twenty-eighth annual ACM symposium on Theory of computing,1996,pp.212-219.   
[33] M.A.Nielsen and I. Chuang,“Quantum computation and quantum information,’2002.   
[34]M. Schuld,1. Sinayskiy,andF.Petruccione,“An introduction to quantum machine learning”Contemporary Physics,vol.56,no.2,pp.172-185, 2015.   
[35] S.C. Kak,“Quantum neural computing,”Advances in imaging and electron physics,vol.94,pp.259-313,1995.   
[36] I. Cong,S. Choi,and M.D.Lukin,“Quantum convolutional neural networks,Nature Physics,vol.15,no.12,pp.1273-1278,2019.   
[37] P.Rebentrost, M. Mohseni,and S.Lloyd,“Quantum support vector machine for big data classification,’Physical review letters,vol.113, no.13,p.130503,2014.   
[38]D.Dong,C.Chen,H. Li,and T.-J. Tarn,“Quantum_reinforcement learning,”IEEE Transactionson Systems,Man,andCybernetics,Part B(Cybernetics),vol.38, no.5, pp.1207-1220,2008.   
[39]J.W.Lai and K.H. Cheong，“Parrondo effect in quantum coin-toss simulations”Physical Review E,vol.101,no.5,p. 052212,2020.   
[40] “Parrondo's paradox from classical to quantum:A review,’Nonlinear Dynamics,vol.100,no.1,pp.849-861,2020.   
[41] J. W. Lai, J. R.A. Tan, H. Lu, Z. R. Yap,and K. H. Cheong,“Parrondo paradoxical walk using four-sided quantum coins” Physical Review E, vol.102,no.1,p.012213,2020.   
[42]N.Wiebe,A. Kapoor,and K. Svore,“Quantum algorithms for nearestneighbor methods for supervised and unsupervised learning,”arXiv preprint arXiv:1401.2142,2014.   
[43]X.Gao and Y.Deng,"Quantum model of mass function,”International Journal of IntelligentSystems,vol.35,no.2,pp.26-82220.   
[44] X.Gao,L.Pan,and Y. Deng,“Quantum pythagorean fuzzy evidence theory (qpfet):A negation of quantum mass function view,’IEEE Transactions on Fuzzy Systems,2021.   
[45] J.Pykacz,“Fuzzy set ideas in quantum logics,”International Journal of Theoretical Physics,vol.31,no.9,pp.1767-1783,1992.   
[46] “Fuzzy quantum logics and infinite-valued lukasiewicz logic," International Journal of Theoretical Physics,vol.33,no.7,pp.1403- 1416, 1994.   
[47] M. A. Mannucci,“Quantum fuzzy sets: Blending fuzzy set theory and quantum computation,’arXiv preprint cs/0604064,2006.   
[48]R.Reiser,A.Lemke,A.Avila,J. Vieira,M.Pilla,and A.Du Bois,“Interpretations on quantum fuzzy computing: intuitionistic fuzzy operations $\times$ （204号 quantum operators”Electronic Notes in Theoretical Computer Science, vol. 324,pp.135-150,2016.   
[49] F. Xiao,“A distance measure for intuitionistic fuzzy sets and its application to pattern classification problems,”IEEE Transactions on Systems,Man,and Cybernetics:Systems,2019.   
[50] F. Xiao and W. Ding,“Divergence measure of pythagorean fuzzy sets and itsapplication in medical diagnosis,”Applied Soft Computing, vol. 79,pp. 254-267,2019.   
[51] Q.Zhou,H. Mo,and Y. Deng,“A new divergence measure of pythagorean fuzzy sets based on belief function and its application in medical diagnosis,’Mathematics,vol.8,no.1,p.142,2020.   
[52] Z.Xu and R.R.Yager,“Intuitionistic and interval-valued intutionistic fuzzy preference relations and their measures of similarity for the evaluation of agreement within a group,’Fuzzy Optimization and decision making,vol.8,no.2,pp.123-139,2009.   
[53] T. Nguyen Xuan and F. Smarandache,“A new fuzzy entropy on pythagorean fuzzy sets,'Journal of Intelligent &Fuzzy Systems,vol.37, no.1,pp.1065-1074,2019.   
[54]J.Deng and Y.Deng,“Information volume of fuzzy membership func tion,’International Journal of Computers Communications & Control, vol. 16,no.1,2021.   
[55] H. Buhrman,R. Cleve,J.Watrous,and R.De Wolf,“Quantum fingerprinting,”Physical Review Letters,vol.87, no.16,p.167902,2001.   
[56] L.Fei, Y. Feng,and L. Liu,“On pythagorean fuzzy decision making using soft likelihood functions,”International Journal of Intelligent Systems,vol.34,no.12,pp.3317-3335,2019.   
[57]Y.Xue and Y.Deng,“Refined Expected Value Decision Rules under Orthopair Fuzzy Environment,”Mathematics,vol.8,no.3,p.442,2020.   
[58]Y.Deng,“Uncertainty measure in evidence theory,”Science China Information Sciences,vol.63,no.11,pp.1-19,2020.   
[59]H.Mo,“An emergency decision-making method for probabilistic linguistic term sets extended by D number theory,’Symmetry，vol.12, no.3,p.380,2020.   
[60]Y. Song and Y.Deng，“A new method to measure the divergence in evidential sensor data fusion,’International Journal of Distributed Sensor Networks,vol.15,no.4,p.1550147719841295,2019.   
[61]H.Mo,“A SWOT method to evaluate safety risks in life cycle of wind turbine extended by D number theory” Journal of Intelligent & Fuzzy Systems,vol.40,no.3,pp.4439-4452,2021.   
[62] H. Wang,Y.P.Fang,and E. Zio,“Risk assessment of an electrical power system considering the influence of traffic congestion on a hypothetical scenario of electrified transportation system in new york state,’IEEE TransactionsonIntellgent TransportationSystems,vol.22,no.pp. 142-155,2021.   
[63]H.Mo,“A new evaluation methodology for quality goals extended by D number theory and FAHP,”Information,vol.11,no.4,p.206,2020.   
[64]L．Pan，X.Gao，Y.Deng，and K.H.Cheong，“The constrained pythagorean fuzzy sets and its similarity measure,”IEEE Transactions on Fuzzy Systems,2021.   
[65] S.Arora and B.Barak,Computational complexity: a modern approach. Cambridge University Press,2009.   
[66] J.Benesty,J.Chen,Y.Huang，and I.Cohen,“Pearson correlation coefficient’in Noise reduction in speech processing.Springer,2009, pp. 1-4.   
[67] S.Kullback and R.A.Leibler,“On information and sufficiency,”The annals of mathematical statistics,vol. 22,no.1,pp.79-86,1951.   
[68] J.Lin,“Divergence measures based on the shannon entropy,” IEEE Transactions on Information theory,vol.37,no.1,pp.145-i51,1991.