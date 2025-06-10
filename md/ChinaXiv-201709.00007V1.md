# Soft Computing On derivations of MV-algebras --Manuscript Draft--

<html><body><table><tr><td>Manuscript Number:</td><td colspan="2">SOCO-D-17-00986</td></tr><tr><td>Full Title:</td><td colspan="2">On derivations of MV-algebras</td></tr><tr><td>Article Type:</td><td colspan="2">Original Research</td></tr><tr><td>Keywords:</td><td colspan="2">Logical algebra; MV-algebra; additive derivation； fixed point set; Boolean algebra</td></tr><tr><td>Corresponding Author:</td><td colspan="2">Jun Tao Wang, Ph.D. Northwest University CHINA</td></tr><tr><td>Corresponding Author Secondary Information:</td><td colspan="2"></td></tr><tr><td>Corresponding Author's Institution:</td><td colspan="2">Northwest University</td></tr><tr><td>First Author:</td><td colspan="2">Jun Tao Wang, Ph.D.</td></tr><tr><td>First Author Secondary Information:</td><td colspan="2"></td></tr><tr><td>Order of Authors:</td><td colspan="2">Jun Tao Wang, Ph.D.</td></tr><tr><td rowspan="3">Funding Information:</td><td colspan="2">Bijan Davvaz</td></tr><tr><td colspan="2">Peng Fei He</td></tr><tr><td>National Natural Science Foundation of China (11601302)</td><td>Dr Peng Fei He</td></tr><tr><td>Abstract:</td><td colspan="2">In this paper, we investigate related properties of some particular derivations and give some characterizations of additive derivations in MV-algebras.Then,we obtain that the xed point set of additive derivations is stillan MV-algebra.Also,we study Boolean additive derivations and their adjoint derivations.In particular, we get that the xed point set of Boolean addition derivations and that of their adjoint derivations are isomorphism. Moreover,we prove that every MV-algebra is isomorphic to the direct product of the xed point set of Boolean additive derivations and that of their adjoint derivations. Finally, we show that the structure of a Boolean algebra is completely determined by its set of all Boolean additive (implicative) derivations.</td></tr><tr><td>Section/Category: Foundations</td><td colspan="2"></td></tr></table></body></html>

# On derivations of MV-algebras

Jun Tao Wang $^ { a , * }$ ， Bijan Davvaz $b$ , Peng Fei He $c$

（204号 $\boldsymbol { a }$ School of Mathematics, Northwest University， Xi'an, 710127, China （2 $b$ Department of Pure Mathematics, Yazd University, 89195-74, Iran cSchool of Mathematics and Information Science, Shaanxi Normal University， Xi'an, 710119, China

# Abstract

In this paper, we investigate related properties of some particular derivations and give some characterizations of additive derivations in MV-algebras. Then, we obtain that the fixed point set of additive derivations is still an MV-algebra. Also, we study Boolean additive derivations and their adjoint derivations. In particular, we get that the fixed point set of Boolean addition derivations and that of their adjoint derivations are isomorphism. Moreover, we prove that every MV-algebra is isomorphic to the direct product of the fixed point set of Boolean additive derivations and that of their adjoint derivations. Finally， we show that the structure of a Boolean algebra is completely determined by its set of all Boolean additive (implicative) derivations.

Keywords: Logical algebra; MV-algebra; additive derivation; fixed point set; Boolean algebra

# 1．Introduction

It is well known that certain information processing approaches, especially inferences based on certain information，are based on the classical logic (classical two-valued logic). Naturally, it is necessary to establish some rational logic systems as a logical foundation for uncertain information processing. For this reason, various types of non-classical logic systems have been proposed and researched. In recent years, non-classical logic has become a formal and useful tool in computer science for dealing with uncertain and fuzzy information. Various logical algebras have been proposed as semantic systems for non-classical logic systems. Among these logical algebras,MV-algebras are the first class of logic algebras introduced and investigated. In 1958, C.C.Chang introduced the notion of MV-algebras for the purpose of providing algebraic proof of the completeness theorem of infinite-valued propositional logics [8]. We are speaking here of the infinite-valued logic proposed in 1930 by Lukasiewicz and Tarski [18] with truth values in the internal [0,1] of real numbers. Thus, in a certain sense, MV-algebras stand in relations to many-valued logic as Boolean algebras do to classical two-valued logic. Furthermore, Chang [9] established a bijective correspondence between the linearly ordered MV-algebras and the linearly ordered abelian $\ell$ -groups with strong unit, then used this result in order to obtain an algebraic proof for the completeness theorem of Lukasiewicz propositional logic in another way. In [1O], Mundici extended Chang's result by proving the categorial equivalence between MV-algebras and abelian $\ell$ -groups with strong unit.

The notion of derivations, introduced from the analytic theory, is helpful for studying algebraic structures and properties in algebraic systems. In fact, the notion of derivation in ring theory is quite old and plays a significant role in algebraic geometry. In 1957, Posner[19] introduced the notion of derivations in prime rings. After then，a number of research articles have been appeared on derivations in the theory of rings and references there in [5,6,15,1]. Inspired by derivationS on rings, Jun et al [17] applied the notion of derivations to BCI-algebras and gave some characterizations of p-semisimple BCI-algebras. Based on this, several authors have studied derivations in BCI-algebras [24, 3,7]. In 2010, Alshehri[2] applied the notions of (additive) derivations to MV-algebras and discussed some related properties, they also proved that an additive derivation of a linearly ordered MV-algebra is isotone. After the work of Alshehri, many authors have investigated derivations of MV-algebras in different aspects [23,13, 4], for example, Yazarli et al [23] further investigated several kinds of generalized derivations on MV-algebras and obtain some interesting results. Ardekani and Davvaz [4] introduced the notion of $f$ -derivations and $( f , g )$ -derivations of MV -algebras and investigated some related properties of them. Ghorbain et al [13] introduced several kinds of these derivations and discuss some related results. They also discuss the relationship between these derivations on MV-algebras. Recently， the notion of derivations has been extended to various logical algebras such as BL-algebras [22], residuated lattices [16] and their non-commutative cases.

This paper is a continuation of the research from [2]. The paper is organized as follows: In Section 2, we review some basic definitions and results about MValgebras. In Section 3, we characterize some particular derivations in MV-algebras. In Section 4,we study Boolean derivations and their adjoint derivations. In particular, we show that every MV-algebra is isomorphic to the direct product of the fixed point set of Boolean additive derivations and that of their adjoint derivations.

# 2.Preliminaries

In this section, we summarize some definitions and results about M-algebras, which will be used in the following sections.

Definition 2.1. [8] An algebra $( L , \oplus , * , 0 )$ of type $( 2 , 1 , 0 )$ is called an MV-algebra if it satisfies the following conditions:

(MV1) $( L , \oplus , 0 )$ is a commutative monoid, (MV2) $( x ^ { * } ) ^ { * } = x$ ，   
(MV3) $0 ^ { * } \oplus x = 0 ^ { * }$ .

(MV4) $( x ^ { * } \oplus y ) ^ { * } \oplus y = ( y ^ { * } \oplus x ) ^ { * } \oplus x$ ， for any $x , y \in L$

In what follows, by $L$ we denote the universe of an MV-algebra $( L , \oplus , * , 0 )$ On each MV-algebra $L$ ，we define the constant 1 and the operations $\odot$ ， $\ominus$ ， $$ as follows: $1 = 0 ^ { * }$ ， $x \odot y = ( x ^ { * } \oplus y ^ { * } ) ^ { * } \ x \ominus y = x ^ { * } \odot y$ and $x \to y = x ^ { * } \oplus y$ . We define $x \leq y$ if and only if $x ^ { * } \oplus y = 1$ .It follows that $\leq$ is a partial order, called the natural order of $L$ . On each MV-algebra, the natural order determines a lattices structure, in which, $x \vee y = ( x \odot y ^ { * } ) \oplus y$ 。 $x \wedge y = x \odot ( x ^ { * } \oplus y )$ .In fact，one can prove that $( L , \wedge , \vee , 0 , 1 )$ is a distributive lattice. Since MV-algebras form a variety, the notions of homomorphism, subalgebra are just the particular cases of the corresponding universal algebraic notions [8, 9, 18].

Example 2.2. [11] Let $L = [ 0 , 1 ]$ be the real unit interval. If we define $x \oplus y =$ $\operatorname* { m i n } \{ 1 , x + y \}$ and $x ^ { * } = 1 - x$ for any $x , y \in L$ ，then $( L , \oplus , * , 0 )$ is an MV-algebra. Also,for each number n ≥ 2,then n-element set Sn = {0,π1n2 n-1,1}is a subalgebra of $L$ ：

Proposition 2.3. [8, 9, 18] In an MV-algebra, the following properties hold:

(1) $x \oplus x ^ { * } = 1$   
(2) $x \odot x ^ { * } = 0$ ，  
(3) （204号 $x \leq y$ if and only if $x  y = 1$   
(4) （20 $\begin{array} { l } { x \odot y \le x \wedge y , } \\ { x \to ( y \wedge z ) = ( x \to y ) \wedge ( x \to z ) , } \\ { ( x \vee y ) \to z = ( x \to z ) \wedge ( y \to z ) , } \end{array}$   
(5) （2  
(6) （204号  
(7) （20 $x \leq y$ implies $x \odot z \le y \odot z$ ，  
(8) （20号 $x \vee y = ( x  y )  y = ( y  x )  x ,$ （20  
(9) （20 $x \leq y  x$ ，  
10) （20 $\begin{array} { r } { x \odot ( y \lor z ) = ( x \odot y ) \lor ( x \odot z ) , } \\ { x \oplus ( y \land z ) = ( x \oplus y ) \land ( x \oplus z ) , } \end{array}$ （20  
11) （204  
12) （20 $x \odot y \le z$ if and only if $x \leq y  z$ ，  
13） $x \ominus y \le z$ if and only if $x \leq y \oplus z$ , for all $x , y , z \in L$

MV-algebras are non-idempotent generalizations of Boolean algebras. Indeed, Boolean algebras are just the MV-algebras obeying the additional identity $x \oplus x = x$ （20 or $x \odot x = x$ .Let $L$ be an MV-algebra and $B ( L ) = \{ a \in L | a \oplus a = a \} = \{ a \in$ $L | a \odot a = a \}$ be the set of all idempotent elements of $L$ . Then $( B ( L ) , \oplus , * , 0 )$ isa subalgebra of $L$ ，which is called the Boolean center of $L$ [8].

Proposition 2.4. [8] Let $L$ be an MV-algebra. Then the following statements are equivalent:

(1) $x \in B ( L )$   
(2) $x \oplus y = x \vee y .$ 号   
(3) $x \odot y = x \land y$ , for any $y \in L$

Proposition 2.5. [20] Let $L$ be an MV-algebra and $e \in B ( L )$ . Then the following properties hold:

$$
\begin{array} { r l } & { e \wedge ( x \odot y ) = ( e \wedge x ) \odot ( e \wedge y ) , } \\ & { e \vee ( x \odot y ) = ( e \vee x ) \odot ( e \vee y ) , } \\ & { e \wedge ( x \oplus y ) = ( e \wedge x ) \oplus ( e \wedge y ) , } \\ & { e \vee ( x \oplus y ) = ( e \vee x ) \oplus ( e \vee y ) , } \\ & { e \odot ( x \to y ) = e \odot [ ( e \odot x ) \to ( e \odot y ) ] , \mathrm { ~ f o r ~ a n y ~ } x , y \in L . } \end{array}
$$

Let $L$ be an MV-algebra. A nonempty subset $I$ of $L$ is called an ideal of $L$ if it satisfies: (1) $x , y \in I$ implies $x \oplus y \in I$ ；(2) $x \in I$ ， $y \in L$ and $y \le x$ implies $y \in I$ . An ideal $I$ of an MV-algebra $L$ is proper if $I \ne L$ .A proper ideal $I$ of an MV-algebra $L$ is called a prime ideal if for any $x , y \in L$ such that $x \wedge y \in I$ ， then $x \in I$ or $y \in I$ ． A nonempty subset $I$ of an MV-algebra $L$ is called a lattice ideal of $L$ if it satisfies: (i) for all $x , y \in I$ ， $x \vee y \in I$ ； (ii) for all $x , y \in L$ ,if $x \in I$ （20 and $y \le x$ ，then $y \in I$ . That is,a lattice ideal of an MV-algebra $L$ is the notion of ideal in the underlying lattice $( L , \wedge , \vee )$ . For any nonempty subset $H$ of $L$ ，the smallest lattice ideal containing $H$ is called the lattice ideal generated by $H$ . The lattice ideal generated by $H$ will be denoted by $( H ]$ .In particular, if $H = \{ t \}$ ， we write $( t ]$ for $( \{ t \} ]$ ， $\mathit { \Omega } ( t ]$ is called a principal lattice ideal of $L$ . It is easy to check that $( t ] \ = \downarrow \ t \ = \ \{ x \in L | x \leq t \}$ .From the above and the Principle of Duality, we can define the lattice filter and the principal lattice filter of an MV-algebra $L$ [10, 11, 14].

Let $I$ be an ideal of an MV-algebra $L$ . We define a binary relation $\theta _ { I }$ on $L$ as follows: for any $x , y \in L$ ， $( x , y ) \in \theta _ { I }$ if and only if $( x \ominus y ) \oplus ( y \ominus x ) \in I$ . Then, $\theta _ { I }$ （204号 is a congruence relation on $L$ . Thus, the binary relation $\leq$ on $L / I$ which is defined by $[ x ] \le [ y ]$ , if and only if $x \to y \in I$ , is an order relation on $L / F$ . For any $x \in L$ ， let $[ x ] _ { I }$ be the equivalence class $[ x ] _ { \theta _ { I } }$ and $L / F = L / \theta _ { I } = \{ [ x ] _ { I } | x \in L \}$ . Then $L / I$ （20 becomes an MV-algebra with the natural operations induced from those of $L$ .For more details about ideals in MV-algebras [20].

Definition 2.6. [20] Given ordered sets $E , F$ and order-preserving mappings $f :$ （204号 $E \longrightarrow F$ and $g : F \longrightarrow E$ ， we say that the pair $( f , g )$ establishes a Galois connection between $E$ and $F$ if $f g \ge i d _ { F }$ and $g f \le i d _ { E }$ ：

# 3. On derivations of MV-algebras

In this section, we investigate some derivations in an MV-algebra. Then, we give some characterizations of additive derivations. Also, we discuss the relationship between additive derivations and ideals of MV-algebras..

Definition 3.1. [2] Let $L$ be an MV-algebra. A map $d : L \longrightarrow L$ is called a derivation on $L$ if it satisfies the following conditions: for any $x , y \in L$ ，

$$
d ( x \odot y ) = ( d ( x ) \odot y ) \oplus ( x \odot d ( y ) ) .
$$

Now，we present some examples for derivations on MV-algebras.

Example 3.2. Let $L$ be an MV-algebra. Define a map $d : L \longrightarrow L$ by $d ( x ) = 0$ for all $x \in L$ ， then $d$ is a derivation on $L$ ， which is called a zero derivation.

Example 3.3. Let $L = \{ 0 , a , b , c , d , 1 \}$ and operations $\bigoplus$ and $^ *$ be defined as follows:

<html><body><table><tr><td></td><td>0</td><td>a</td><td>b</td><td>C</td><td>d</td><td>1</td><td colspan="7"></td></tr><tr><td>0</td><td>0</td><td>a</td><td>b</td><td>C</td><td>d</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>a</td><td>a</td><td>C</td><td>d</td><td>C</td><td>1</td><td>1</td><td>*</td><td>0</td><td>a</td><td>b</td><td>C</td><td>d 1</td></tr><tr><td>b</td><td>b</td><td>d</td><td>b</td><td>1</td><td>d</td><td>1</td><td></td><td>1</td><td>d</td><td>C</td><td>b a</td><td>0</td></tr><tr><td>C</td><td>C</td><td>C</td><td>1</td><td>C</td><td>1</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>d</td><td>d</td><td>1</td><td>d</td><td>1</td><td>1</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

Then $( \{ 0 , a , b , c , d , 1 \} , \oplus , * , 0 )$ is an MV-algebra. Define a map $d : L \longrightarrow L$ （204号 by $d ( 0 ) = d ( a ) = d ( c ) = 0$ ， $d ( b ) = d ( d ) = d ( 1 ) = b$ . One can check that $d$ isa derivation on $L$ ：

Proposition 3.4. [2] Let $L$ be an MV-algebra and $d$ be a derivation on $L$ . Then we have: for any $x , y \in L$ ，

$$
\begin{array} { l } { d ( 0 ) = 0 , } \\ { d ( 1 ) \in B ( L ) , } \\ { d ( x ) \odot x ^ { * } = x \odot d ( x ^ { * } ) = 0 , } \\ { d ( x ) \le x , } \\ { d ( x ) = d ( x ) \oplus ( x \odot d ( 1 ) ) . } \end{array}
$$

Definition 3.5. [2] Let $L$ be an MV-algebra and $d$ be a derivation on $L$ 车

(1) $d$ is called an isotone derivation provided that $x \leq y$ implies $d ( x ) \leq d ( y )$ for all $x , y \in L$ ，   
(2) $d$ is called an additive derivation provided that $d ( x \oplus y ) = d ( x ) \oplus d ( y )$ for all （204号 $x , y \in L$ ：

Example 3.6. Considering the MV-algebra $S _ { 4 } = \{ 0 , { \scriptstyle { \frac { 1 } { 3 } } } , { \scriptstyle { \frac { 2 } { 3 } } } , 1 \}$ in Example 2.2. Define a map $d : S _ { 4 } \longrightarrow S _ { 4 }$ by $d ( 0 ) = d ( 1 ) = d ( \textstyle { \frac { 1 } { 3 } } ) = 0$ ）， $\begin{array} { l l l } { { d ( \frac { 2 } { 3 } ) ~ = ~ \frac { 1 } { 3 } } } \end{array}$ .One can check that $d$ is a derivation on $S _ { 4 }$ , but it is not an additive derivation on $L$ ，since （204号 $d ( \textstyle { \frac { 1 } { 3 } } + \textstyle { \frac { 2 } { 3 } } ) = d ( 1 ) = 0 \neq \frac { 1 } { 3 } = d ( \frac { 1 } { 3 } ) + d ( \frac { 2 } { 3 } )$ Also, $d$ is not an isotone derivation on $L$ ， since ${ \frac { 2 } { 3 } } \leq 1$ ，but $d ( \textstyle { \frac { 2 } { 3 } } ) = \frac { 1 } { 3 } \geq 0 = d ( 1 )$

Example 3.7. Considering the derivation $d$ in Example 3.3,one can see that $d$ is not only an additive and but also is an isotone derivation on $L$

Proposition 3.8. Let $L$ be an MV-algebra and $d$ be an additive derivation on $L$ Then we have: for any $x , y \in L$ ，

(1) $d$ is an isotone derivation,

2） $d ( x ) = d ( 1 ) \odot x ,$ （20  
3） $d d ( x ) = d ( x )$ ，  
（4） $d ( x ) \in B ( L )$ ，  
5 $d ( d ( x )  d ( y ) ) = d ( x  y )$   
(6） $F i x _ { d } ( L ) = d ( L )$ ，where $F i x _ { d } ( L ) = \{ x \in L | d ( x ) = x \}$   
（7）if $d ( L ) = L$ ,then $d = i d _ { L }$ ，  
(8） $\operatorname { K e r } ( d )$ is an ideal of $L$ ，where $\mathrm { K e r } ( d ) = \{ x \in L | d ( x ) = 0 \}$

Proof. (1） If $x \leq y$ ，then $y = x \vee y = x \oplus ( x ^ { * } \odot y )$ . From Definition 3.5(2)，wehave uvi u(y) $d ( y ) = d ( x \oplus ( x ^ { * } \odot y ) ) = d ( x ) \oplus d ( x ^ { * } \odot y ) \geq d ( x )$ . Thus, $d ( x ) \leq d ( y )$

(2) From Proposition 3.4(2),(4) and (1)，we have $d ( x ) = d ( 1 ) \wedge d ( x ) = d ( 1 ) \odot$ （204 $d ( x ) \leq d ( 1 ) \odot x$ . On the other hand,we conclude from Definition 3.1 that $d ( x ) \geq$ $x \odot d ( 1 )$ . Thus, $d ( x ) = d ( 1 ) \odot x$ ： (3) From Proposition 3.4(2） and (2)，we have $d d ( x ) = d ( d ( 1 ) \odot x ) = d ( 1 ) \odot$ $d ( 1 ) \odot x = d ( 1 ) \odot x = d ( x )$ ： (4) From Definition 3.1 and (2)，we have $d ( x ) = d ( x \odot 1 ) = ( d ( x ) \odot 1 ) \oplus ( x \odot $ $d ( 1 ) ) = d ( x ) \oplus ( x \odot d ( 1 ) ) = d ( x ) \oplus d ( x )$ . Thus, $d ( x ) \in B ( L )$ ： (5) From Proposition 2.5(5), 3.4(2) and (2)，we have $d ( d ( x )  d ( y ) ) = d ( 1 ) \odot$ $[ ( d ( 1 ) \odot x ) \to ( d ( 1 ) \odot y ) ] = d ( 1 ) \odot ( x \to y ) = d ( x \to y )$ . Thus, $d ( d ( x )  d ( y ) ) =$ $d ( x  y )$ ： (6) Let $y \in d ( L )$ . So there exists $x \in L$ such that $y = d ( x )$ and hence $d ( y ) =$ $d d ( x ) = d ( x ) = y$ ,that is, $y \in F i x _ { d } ( L )$ . Conversely, if $y \in F i x _ { d } ( L )$ , then we have $y \in d ( L )$ . Therefore, $F i x _ { d } ( L ) = d ( L )$ ： (7) For any $x \in L$ ，we have $x = d ( x _ { 0 } )$ for some $x _ { 0 } \in L$ .From (3)，we have （204号 $d ( x ) = d d ( x _ { 0 } ) = d ( x _ { 0 } ) = x$ . Therefore, $d = i d _ { L }$ ： (8）From Proposition $3 . 4 ( 1 )$ ，we have $d ( 0 ) = 0$ ，that is, $0 \in \mathop { \mathrm { K e r } } ( d )$ .If $x , y \in$ $\mathrm { K e r } ( d )$ , then $d ( x ) = d ( y ) = 0$ and hence $d ( x \oplus y ) = d ( x ) \oplus d ( y ) = 0$ , that is, $x \oplus y \in$ $\operatorname { K e r } ( d )$ . Finally, if $x \leq y$ and $y \in \mathop { \mathrm { K e r } } ( d )$ ,then $d ( x ) \leq d ( y ) = 0$ and hence $d ( x ) = 0$ ， that is, $x \in \mathop { \mathrm { K e r } } ( d )$ ：

Remark 3.9. In [2], the results (1) and (8) in Proposition 3.8 are proved as Theorems 3.16, 3.17 under the additional condition that $L$ is an linearly ordered MV-algebra, but this condition is redundant as our proof shows.

Theorem 3.10.Let $L$ be an MV-algebra and $d$ be a derivation on $L$ . Then the following statements are equivalent:

(1） $d$ is an additive derivation,  
2） $d$ is an isotone derivation,  
（3） $d ( x ) \leq d ( 1 )$ ，  
4 （204号 $\begin{array} { r l } & { d ( x ) = d ( 1 ) \odot x , } \\ & { d ( x \odot y ) = d ( x ) \odot y = x \odot d ( y ) , } \\ & { d ( x \wedge y ) = d ( x ) \wedge d ( y ) , } \\ & { d ( x \vee y ) = d ( x ) \vee d ( y ) , } \\ & { d ( x \odot y ) = d ( x ) \odot d ( y ) , } \end{array}$   
5 （204  
6  
7）  
(8）

(9) $d ( x ) \leq y$ if and only if $d ( x ) \leq d ( y )$ (10) $d ( x )  d ( y ) = d ( x )  y$

Proof. $( 1 ) \Rightarrow ( 2 )$ It follows from Proposition 3.8(1) $( 2 ) \Rightarrow ( 3 )$ It is straightforward. $( 3 ) \Rightarrow ( 4 )$ It follows from Proposition 3.8(2). $( 4 ) \Rightarrow ( 1 )$ From Proposition 2.5(4) and Proposition 3.8(2)，we have $d ( x \oplus y ) =$   
（204 $d ( 1 ) \odot ( x \oplus y ) = ( d ( 1 ) \odot x ) \oplus ( d ( 1 ) \odot y ) = d ( x ) \oplus d ( y )$ , that is, $d ( x \oplus y ) = d ( x ) \oplus d ( y )$ From the above proof, one can see the statements (1)-(4) are equivalent. $( 4 ) \ \Rightarrow \ ( 5 )$ Let $d ( x ) = d ( 1 ) \odot x$ for all $x \in L$ .It follows that $d ( x \odot y ) =$   
（202 $d ( 1 ) \odot x \odot y = x \odot ( d ( 1 ) \odot y )$ ， that is, $d ( x \odot y ) = d ( x ) \odot y = x \odot d ( y )$ for any   
（20 $x , y \in L$ ： $( 5 ) \Rightarrow ( 4 )$ Taking $y = 1$ in (5)，we have $d ( x ) = d ( 1 ) \odot x$ for any $x \in L$ ： $( 4 ) \ \Rightarrow \ ( 6 )$ Let $d ( x ) = d ( 1 ) \odot x$ for any $x \in L$ .It follows that $d ( x \wedge y ) =$   
$d ( 1 ) \odot ( x \wedge y ) = d ( 1 ) \wedge ( x \wedge y ) = d ( 1 ) \wedge d ( 1 ) \wedge x \wedge y = d ( x ) \wedge d ( y )$ for any $x , y \in L$ $( 4 ) \Rightarrow ( 7 )$ Since $( L , \wedge , \vee , 0 , 1 )$ is a distributive lattice. From (4)，we have $d ( x \vee$   
$y ) = d ( 1 ) \odot ( x \lor y ) = d ( 1 ) \land ( x \lor y ) = ( d ( 1 ) \land x ) \lor ( d ( 1 ) \land y ) = ( d ( 1 ) \odot x ) \lor ( d ( 1 ) \odot y ) = ( d ( 1 ) \odot y )$ y)=   
$d ( x ) \vee d ( y )$ for any $x , y \in L$ ： $( 7 ) \Rightarrow ( 2 )$ Let $x \le y$ ，we have $x \vee y = y$ .From (7)，we $d ( y ) = d ( x \vee y ) =$   
$d ( x ) \vee d ( y ) \geq d ( x )$ for any $x , y \in L$ . Therefore, $d$ is an isotone derivation. （204 $( 4 ) \Rightarrow ( 8 )$ From (4), we have $d ( x \odot y ) = d ( 1 ) \odot ( x \odot y ) = d ( 1 ) \odot d ( 1 ) \odot x \odot y =$   
$d ( x ) \odot d ( y )$ for any $x , y \in L$ ： $( 6 ) \Rightarrow ( 3 )$ ， $( 7 ) \Rightarrow ( 3 )$ ， $( 8 ) \Rightarrow ( 3 )$ are straightforward. $( 2 ) \Rightarrow ( 9 )$ For all $x , y \in L$ ，assume that $d ( x ) \leq y$ ，we have $d d ( x ) \leq d ( y )$   
By 3.8(2)， we get $d d ( x ) = d ( x )$ .Thus $d ( x ) \leq d ( y )$ .Conversely， suppose that   
$d ( x ) \leq d ( y )$ ，we get $d ( x ) \leq d ( y ) \leq y$ for all $x , y \in L$ ： （20 $( 9 ) \Rightarrow ( 2 )$ Let $x \leq y$ ，we have $d ( x ) \leq x \leq y$ and hence $d ( x ) \leq d ( y )$ for all   
（204号 $x , y \in L$ ： $( 2 ) \Rightarrow ( 1 0 )$ Suppose that $d$ is an isotone derivation on $L$ . From $d ( y ) \leq y$ for any   
（204号 $y \in L$ , it follows that $d ( x ) \to d ( y ) \leq d ( x ) \to y$ . On the other hand, $\operatorname { l e t } t \leq d ( x )  y$ （204号   
for all $t \in L$ ， we can obtain $d ( x ) \odot t \leq y$ . Since $d$ is an isotone derivation, we have   
（20 $d ( d ( x ) \odot t ) \leq d ( y )$ for all $x , y , t \in L$ .From $d ( x \odot y ) = ( d ( x ) \odot y ) \oplus ( x \odot d ( y ) )$ ，we   
get $d ( x ) \odot y \le d ( x \odot y )$ for all $x , y \in L$ . It follows $d ( d ( x ) ) \odot t \leq d ( d ( x ) \odot t )$ By   
Proposition 3.8(3)， we have $d ( x ) \odot t \leq d ( d ( x ) \odot t ) \leq d ( y )$ . Hence $t \leq d ( x )  d ( y )$ （20   
for all $t \in L$ , which implies $d ( x )  y \leq d ( x )  d ( y )$ for all $x , y \in L$ . Therefore, we   
obtain $d ( x )  d ( y ) = d ( x )  y$ for any $x , y \in L$ ： （20 $( 1 0 ) \Rightarrow ( 2 )$ Assume that $d ( x )  d ( y ) = d ( x )  y$ for all $x , y \in L$ .For any

$x , y \in L$ ,let $x \leq y$ ， by Proposition 3.4(4)， we have $d ( x ) \odot 1 = d ( x ) \le x \le y$ It follows that $1 \leq d ( x )  y = d ( x )  d ( y )$ ,which implies $d ( x ) \leq d ( y )$

Remark 3.11. (1） From the above theorem, one can see that isotone derivations are equivalent to additive derivations on MV-algebras.   
(2)From the Example 3.3， one can check that an additive derivation is not a homomorphism on an MV-algebra $L$ in general, since $d ( a ^ { * } ) = b \neq 1 = ( d ( a ) ) ^ { * }$   
(3) From the Example 3.3, one can check that the fixed point set of an additive derivation $d$ is not a subalgebra of an MV-algebra $L$ in general, since $0 ^ { * } = 1 \notin$ $\{ 0 , b \} = F i x _ { d } ( L )$ ：   
(4） From (4) of the above theorem，one can see that every additive derivation $d$ （204号 on an MV-algebra $L$ is completely defined by the image $d ( 1 )$ of the 1.   
(5） It is easily seen that every additive derivation is a lattice derivation in the sense of Ferrari [12],which is a unary map $d : L \to L$ satisfying conditions Theorem 3.10(7) and $d ( x \wedge y ) = ( d ( x ) \wedge y ) \vee ( x \wedge d ( y ) )$ . However, the converse is not true in general. Moreover, Ghorbain proved that a lattice derivation on an MV-algebra is an additive derivation if and only if $d ( L ) \subseteq B ( L )$ in [13].

The following theorem shows that the fixed point set $F i x _ { d } ( L )$ of additive derivations in an MV-algebra $L$ has the same structure as $L$ ，which reveals the essence of the fixed point set of additive derivations.

Theorem 3.12.Let $L$ be an MV-algebra and $d$ be an additive derivation on $L$ 业 Then $( F i x _ { d } ( L ) , \oplus , \lnot , 0 )$ is an MV-algebra, where $\neg x = d ( x ^ { * } ) = d ( 1 ) \odot x ^ { * } = ( x \oplus$ $( d ( 1 ) ) ^ { * } ) ^ { * }$ for any $x \in F i x _ { d } ( L )$

Proof. First, we will prove that $( F i x _ { d } ( L ) , \Phi , 0 )$ is a commutative monoid. From Definition 3.5(2), we have $F i x _ { d } ( L )$ is closed under $\bigoplus$ . It follows that $( F i x _ { d } ( L ) , \oplus )$ （20 is commutative semigroup. For all $x \in F i x _ { d } ( L )$ ， we can obtain that $x \oplus 0 = x$ ， thatis, $0$ is aunital element.

Next, we will prove that $F i x _ { d } ( L )$ is closed under $\neg$ . For all $x \in F i x _ { d } ( L )$ ， from Proposition $3 . 4 ( 2 )$ and $3 . 8 ( 2 )$ ，we have $d ( \neg x ) = d ( d ( x ^ { * } ) ) = d ( 1 ) \odot d ( 1 ) \odot x ^ { * } =$ $d ( 1 ) \odot x ^ { * } = d ( x ^ { * } ) = \lnot x$ , that is, $F i x _ { d } ( L )$ is closed under $\neg$ ：

Finally, we will verify the remaining axioms of an MV-algebra.

(MV2) For all $x \in F i x _ { d } ( L )$ ， from Theorem 3.10(3)，we have $\neg \neg x \ : = \ : ( \neg x \ : \oplus$ （204号 (d(1)\*)\*= ((x④(d(1))\*)④(d(1))\*)\*= (x④(d(1))\*)0d(1)= x∧d(1)=d(x)^d(1) = $d ( x ) = x$ , that is, $\neg \neg x = x$ ： (MV3) For all $x \in F i x _ { d } ( L )$ , from Theorem 3.10(3),we have $x \oplus \lnot 0 = x \oplus d ( 1 ) =$ （204号 $d ( x ) \oplus d ( 1 ) = d ( x ) \lor d ( 1 ) = d ( 1 )$ , that is, $x \oplus \lnot 0 = d ( 1 )$ ： (MV4) For any $x , y \in F i x _ { d } ( L )$ , we have $\lnot ( \lnot x \oplus y ) \oplus y = ( \lnot x \oplus y \oplus ( d ( 1 ) ) ^ { * } ) ^ { * } \oplus y =$ $\begin{array} { r } { ( x \oplus ( d ( 1 ) ) ^ { * } ) ^ { * } \oplus y ) \oplus ( d ( 1 ) ) ^ { * } ) ^ { * } \oplus y = ( ( x \oplus ( d ( 1 ) ) ^ { * } ) \odot d ( 1 ) \odot y ^ { * } ) \oplus y = ( ( x \wedge d ( 1 ) ) ^ { * } ) \oplus ( d ( 1 ) ) ^ { * } ) } \end{array}$ ))0 $y ^ { * } ) \oplus y = x \vee y$ . in the similar way, one can prove that $\lnot ( x \oplus \lnot y ) \oplus x = x \lor y$ ，and hence $\lnot ( \lnot x \oplus y ) \oplus y = \lnot ( x \oplus \lnot y ) \oplus x$ ：

Therefore,we obtain that $( F i x _ { d } ( L ) , \oplus , \lnot , 0 )$ is an MV-algebra

Theorem 3.13.Let $L$ be an MV-algebra and $d$ an additive derivation on $L$ . Then we have the following properties:

(1) $d : L \longrightarrow F i x _ { d } ( L )$ is a surjective homomorphism, (2) $d : L / K e r ( d ) \longrightarrow F i x _ { d } ( L )$ is an isomorphism.

Proof. (1) It follows from Theorem 3.10 and 3.12. (2)From Proposition 3.8(8)，we obtain that $K e r ( d )$ is an ideal of $L$ .Let $x \sim _ { K e r ( d ) } \ y$ .Then $( x \ominus y ) \oplus ( y \ominus x ) \in K e r ( d )$ ，which implies $d ( ( x \ominus y ) \oplus ( y \ominus$ $x ) ) = d ( x \ominus y ) \oplus d ( y \ominus x ) = 0$ .Furthermore, from Theorem 3.10(8)，we have （20 $d ( x \ominus y ) = d ( x ) \odot d ( y ^ { * } ) = d ( x ) \odot y ^ { * } = d ( y \ominus x ) = d ( y ) \odot x ^ { * } = 0$ , that is, $d ( x ) \leq y$ （20 and $x \leq d ( y )$ . Further by Theorem 3.10(9)，we have $d ( x ) = d ( y )$ .Thus, $\bar { d }$ is well defined. Moreovwe, it follows from(1） that $\bar { d } : L / K e r ( d ) \longrightarrow F i x _ { d } ( L )$ is an isomorphism.

Theorem 3.14. Let $L$ be an MV-algebra and $d : L  L$ be a map on $L$ such that $d ( L ) \subseteq B ( L )$ . Then the following statements are equivalent:

(1) $d$ is an additive derivation on $L$ 5 (2) $d ( x ) = d ( 1 ) \odot x$ ， (3) $d ( x \odot y ) = d ( x ) \odot y = x \odot d ( y ) .$ （204号

Proof. $( 1 ) \Rightarrow ( 2 )$ It follows from Proposition 3.8(2). $( 2 ) \Rightarrow ( 3 )$ The proof of that is similar to Theorem 3.10 $) ( 4 ) \Rightarrow ( 5 )$ $( 3 ) \Rightarrow ( 1 )$ Taking $y = 1$ in (3)，we have $d ( x ) = d ( 1 ) \odot x$ .From $d ( L ) \subseteq B ( L )$   
we have $d ( x \odot y ) = d ( x \odot y ) \oplus d ( x \odot y ) = ( d ( x ) \odot y ) \oplus ( x \odot d ( y ) ) _ { ! }$ that is, $d$ isa   
derivation on $L$ . Moreover，from Theorem $3 . 1 0 \ ( 1 ) \Leftrightarrow \ ( 4 )$ ，we obtain that $d$ is an   
additive derivation on $L$ ：

Corollary 3.15. Let $L$ be a Boolean algebra and $d : L  L$ be a map on $L$ . Then the following statements are equivalent:

(1） $d$ is an additive derivation on $L$ (2) $d ( x ) = d ( 1 ) \wedge x$ ，(3) $d ( x \wedge y ) = d ( x ) \wedge y = x \wedge d ( y ) .$ （204号

Proof.It follows from Theorem 3.14.

Theorem 3.16.Let $L$ be an MV-algebra and $d$ be an additive derivation on $L$ Then the following statements are equivalent:

(1) $d$ is an identity map.(2) $d ( x ^ { * } ) = ( d ( x ) ) ^ { * }$ ，(3) $d ( 1 ) = 1$ ，（4） $d$ is homorphism,5 $d$ is surjection,6） $d$ is one to one,（7） $d$ is isomorphic.

Proof. $( 1 ) \Rightarrow ( 2 )$ It is straightforward. $( 2 ) \Rightarrow ( 3 )$ From Proposition 3.4(1),we have $d ( 1 ) = d ( 0 ^ { \ast } ) = ( d ( 0 ) ) ^ { \ast } = 0 ^ { \ast } = 1$ $( 3 ) \Rightarrow ( 1 )$ From Proposition 3.8(2),we have $d ( x ) = d ( 1 ) \odot x = 1 \odot x = x$ ： $( 2 ) \Rightarrow ( 4 )$ From Proposition 3.4(1） and Theorem 3.10(8)，we obtain that $d$ is   
homorphism. $( 4 ) \Rightarrow ( 2 )$ It is straightforward. $( 1 ) \Rightarrow ( 5 )$ It is straightforward. $( 5 ) \ \Rightarrow \ ( 1 )$ Suppose that $d$ is surjection,then there exists $x \in L$ such that   
$d ( x ) = 1$ . From Proposition $3 . 4 ( 4 )$ ，we have $1 = d ( x ) \leq x$ and hence $x = 1$ ，that   
is, $d ( 1 ) = 1$ . Further from $( 3 ) \Rightarrow ( 1 )$ ， we get that $d$ is an identity map. $( 1 ) \Rightarrow ( 6 )$ It is straightforward. $( 6 ) \Rightarrow ( 1 )$ Suppose that $d$ is one to one, by Proposition 3.8(2), we have $d ( ( d ( 1 ) ) ^ { * } ) =$   
$d ( 1 ) \odot ( d ( 1 ) ) ^ { * } = 0$ and hence $d ( 1 ) = 1$ .hence $x = 1$ ，that is, $d ( 1 ) = 1$ .From   
$( 3 ) \Rightarrow ( 1 )$ ，we get that $d$ is an identity map. From $( 3 ) \Rightarrow ( 1 )$ ，we get that $d$ is an   
identity map. $( 1 ) \Leftrightarrow ( 7 )$ It follows from $( 1 ) \Leftrightarrow ( 4 ) , ( 1 ) \Leftrightarrow ( 5 ) , ( 1 ) \Leftrightarrow ( 6 ) .$ （20

In what follows, we discuss the relationship between ideals and derivations on MV-algebras.

The following example shows that the fixed point set $F i x _ { d } ( L )$ of a derivation $d$ is not an ideal of an MV-algebra $L$

Example 3.17. Considering $S _ { 3 } = \{ 0 , { \frac { 1 } { 2 } } , 1 \}$ in Example 2.2 and defining a map $d : S _ { 3 } \longrightarrow S _ { 3 }$ by $d ( 0 ) = d ( 1 ) = 0$ ， $\begin{array} { r } { d ( \frac { 1 } { 2 } ) = \frac { 1 } { 2 } } \end{array}$ . One can check that $d$ is a derivation, while it is not an additive derivation, and $\operatorname { F i x } _ { d } ( L ) = \{ 0 , { \frac { 1 } { 2 } } \}$ is not an ideal of $L$ （20 since $\begin{array} { r } { \frac { 1 } { 2 } \oplus \frac { 1 } { 2 } = 1 \not \in F i x _ { d } ( L ) } \end{array}$

However, if the conditions are strengthened, we can obtain the following result.

Proposition 3.18. Let $( L , \oplus , * , 0 , 1 )$ be an MV-algebra and $d$ be an additive derivation on $L$ . Then $F i x _ { d } ( L )$ is an ideal of $L$ =

Proof. It follows from Theorem 3.10 (1) ←(2) and Proposition 3.23 (3) in [13].

The following is a counterexample showing that the converse of Proposition 3.18 may not hold.

Example 3.19. Considering the Example 3.6, one can check that $F i x _ { d } ( L ) = \{ 0 \}$ is an ideal of $L$ . However, $d$ is not an additive derivation on $L$

Inspired by Proposition 3.18, it is natural to ask that whether there exists an additive derivation $d$ such that $F i x _ { d } ( L ) = I$ for given ideal $I$ in an MV-algebra $L$

According to Theorem 4.13 in [21],we give the positive answer under certain conditions to the above question.

Proposition 3.20. Let $L$ be a Boolean algebra and $I$ be a non-void prime ideal of $L$ . Then there exists an additive derivation $d$ such that $F i x _ { d } ( L ) = I$ . Indeed, a map $d : L \longrightarrow L$ that is defined by: for all $t , x \in L$ ，

$$
d ( x ) = { \left\{ \begin{array} { l l } { x , } & { x \in I } \\ { x \wedge t , } & { x \in L / I , } \end{array} \right. }
$$

is an additive derivation satisfying $F i x _ { d } ( L ) = I$

In fact, the above proposition shows under some suitable conditions, there exists an additive derivation on an MV-algebra $L$ such that $F i x _ { d } ( L ) = I$ for given ideal $I$ of $L$ . Furthermore, we have the following open problem:

(1） For any ideal $I$ of an MV-algebra $L$ , whether there exists an additive derivation （204号 $d$ such that $F i x _ { d } ( L ) = I$ ：

# 4.Boolean derivation and their applications

In this sections, we investigate Boolean additive derivations and their adjoint derivations. In particular, we prove that every MV-algebra is isomorphic to the direct product of the fixed point set of Boolean additive derivations and that of their adjoint derivations. Finally, we show that the structure of a Boolean algebra is completely determined by its set of all Boolean additive (implicative) derivations.

In what follows, let $L$ be an MV-algebra and $a \in L$ ， we define four maps as follows:

(1) $d _ { a } : L \to L$ such that $d _ { a } ( x ) = x \odot a$ , for all $x \in L$ ， (2) $d _ { a ^ { * } } : L \to L$ such that $d _ { a ^ { * } } ( x ) = x \odot a ^ { * } = x \ominus a$ , for all $x \in L$ ， (3) $g _ { a } : L \to L$ such that $g _ { a } ( x ) = a \oplus x$ , for all $x \in L$ ， (4) $g _ { a ^ { * } } : L  L$ such that $g _ { a ^ { * } } ( x ) = a ^ { * } \oplus x = a \to x$ , for all $x \in L$

Theorem 4.1. Let $L$ be an MV-algebra. Then the following statements are equivalent:

（1） $L$ is a Boolean algebra, (2) $d _ { a }$ is an additive derivation on $L$ , for all $a \in L$ ， (3） $d _ { a ^ { * } }$ is an additive derivation on $L$ , for all $a \in L$

Proof. $( 1 ) \Rightarrow ( 2 )$ If $L$ is a Boolean algebra, then we get that $x \oplus y = x \vee y$ for any （204号 $x , y \in L$ . Further by Corollary 3.15, we have $d _ { a }$ is an additive derivation on $L$

$( 2 ) \Rightarrow ( 1 )$ Assume that $d _ { a }$ is an additive derivation on $L$ . From Definition 3.1, we have $a = d _ { a } ( 1 ) = d _ { a } ( 1 \odot 1 ) = ( d _ { a } ( 1 ) \odot 1 ) \oplus ( 1 \odot d _ { a } ( 1 ) ) = a \oplus a$ for any $a \in L$ （204号 and hence $L \subseteq B ( L )$ . Therefore, $L$ is a Boolean algebra.

$( 1 ) \Leftrightarrow ( 3 )$ The proof of $( 1 ) \Leftrightarrow ( 3 )$ is similar to that of $( 1 ) \Leftrightarrow ( 2 )$

Remark 4.2. From Theorem 4.1,we obtain that $d _ { a }$ is an additive derivation on an MV-algebra if and only if $a \in B ( L )$ .Based on the above consideration，we called $d _ { a }$ a Boolean additive derivation on an MV-algebra $L$

Next，we will discuss the adjoint derivation of Boolean additive derivations. First, we introduce new derivation on MV-algebras.

Definition 4.3. Let $L$ be an MV-algebra. A map $g : L \to L$ is called an implication derivation on $L$ if it preserves $$ and satisfies the following conditions: for any $x , y \in L$ ，

$$
g ( x  y ) = ( g ( x )  y ) \oplus ( x  g ( y ) ) .
$$

Example 4.4. Let $L = \{ 0 , a , b , 1 \}$ be a chain and operations $\bigoplus$ and $*$ be defined as follows:

$$
\begin{array}{c} \begin{array}{c} { \begin{array} { c } { { \frac { \bigoplus } { \begin{array} { c c c c c c } { \boxplus } & { { 0 } & { a } & { b } & { 1 } \\ { 0 } & { a } & { b } & { 1 } \end{array} } } } \\ { { \begin{array} { c } { a } \\ { b } \end{array} } { | } { \begin{array} { c c c c c c } { a } & { a } & { 1 } & { 1 } & { } & { \qquad { \ast } \end{array} } { | } { \begin{array} { c c c c c } { 0 } & { a } & { b } & { 1 } & { } \\ { 1 } & { b } & { a } & { 0 } \end{array}  } } \\ { 1 } \end{array} } { | } { \begin{array} { c c c c c } { 1 } & { 1 } & { b } & { 1 } & { } & { } \end{array} } } \end{array} }  \end{array}  \qquad { \begin{array} { c } { { \frac { \bigoplus } { \begin{array} { c c c c c } { { \boxed { 1 } } } & { { 0 } } & { { 0 } } & { { 0 } } & { } \\ { { 1 } } & { { b } } & { { a } } & { { 0 } } \end{array} } } } \\ { { \begin{array} { c } { { 1 } } \end{array} } { | } { \begin{array} { c c c c c } { 1 } & { 1 } & { 1 } & { } & { { 1 } } \end{array} | } { \begin{array} { c } { { \boxed { 1 } } } & { { 0 } } & { { 0 } } \\ { { 1 } } & { { 0 } } & { { 0 } } \end{array} } } } \end{array} 
$$

Then $( \{ 0 , a , b , 1 \} , \oplus , * , 0 )$ is an MV-algebra. Define a map $g : L \longrightarrow L$ by $g ( 0 ) =$ （204号 $g ( a ) = a$ ， $g ( b ) = g ( 1 ) = 1$ . One can check that $g$ is an implicative derivation on $L$ ， while $g$ is not a homorphism on $L$ ， since $g ( 0 ) \neq 0$ ：

Theorem 4.5. Let $L$ be an MV-algebra. Then the following statements are equivalent:

(1） $L$ is a Boolean algebra, （2) $g _ { a ^ { * } }$ is an implicative derivation on $L$ ， for all $a \in L$ (3) $g _ { a }$ is an implicative derivation on $L$ , for all $a \in L$ ：

Proof. $( 1 ) \Rightarrow ( 2 )$ Let $L$ be a Boolean algebra and $a \in L$ . First，we will prove that $g _ { a ^ { * } } ( x  y ) = g _ { a ^ { * } } ( x )  g _ { a ^ { * } } ( y )$ . In particular, since $( a \odot x \to y ) \odot a \odot ( a \to$ $x ) \leq ( a \odot x \to y ) \odot a \odot x \leq y$ ，we have $a \odot x \to y \leq a \odot ( a \to x ) \to y$ and hence （20 $g _ { a ^ { * } } ( x  y ) = a  ( x  y ) = x  ( a  y ) = a \odot x  y \leq a \odot ( a  x )  y = ( a \odot y )$ a→ （204号 $x )  ( a  y ) = g _ { a ^ { * } } ( x )  g _ { a ^ { * } } ( y )$ . On the other hand, since $x \leq a  x$ , it easy to show that $a \odot x \le a \odot ( a \to x )$ and hence that $a \odot ( a \to x ) \to y \leq a \odot x \to y$ ,that is, $g _ { a ^ { * } } ( x )  g _ { a ^ { * } } ( y ) \leq g _ { a ^ { * } } ( x  y )$ . Thus, we have $g _ { a ^ { * } } ( x  y ) = g _ { a ^ { * } } ( x )  g _ { a ^ { * } } ( y )$ ：

Next, from Proposition 2.5, we have $g _ { a ^ { * } } ( x  y ) = a \oplus ( x  y ) = x ^ { * } \oplus g _ { a ^ { * } } ( y ) =$ $( ( g _ { a ^ { * } } ( x ) ) \vee x ^ { * } ) \oplus ( g _ { a } ( y ) \vee y ) = ( ( g _ { a } ( x ) ) ^ { * } \oplus y ) \oplus ( x ^ { * } \oplus g _ { a } ( y ) ) = ( g _ { a ^ { * } } ( x )  y ) \oplus ( g _ { a ^ { * } } ( x ) )$ x→$g _ { a ^ { * } } ( y )$ ：

Combing them,one can see that $g _ { a ^ { * } }$ is an implicative derivation on $L$

$( 2 ) \Rightarrow ( 1 )$ Assume that $g _ { a ^ { * } }$ is an implicative derivation on $L$ ， for any $a \in L$ ： Then $g _ { a ^ { * } } ( x  y ) = g _ { a ^ { * } } ( x )  g _ { a ^ { * } } ( y ) $ holds for all $x , y \in L$ ， then taking $x \ = \ a$ （20 and $y = a \odot a$ we have $a  ( a  a \odot a ) = ( a  a )  ( a  a \odot a )$ .Since $a  ( a  a \odot a ) = a \odot a  a \odot a = 1$ ， we have $1 = 1 \to ( a \to a \odot a ) = a \to a \odot a$ This implies that $a \leq a \odot a$ and hence that $a = a \odot a$ ，that is $L$ is a Boolean algebra.

$( 1 ) \Leftrightarrow ( 3 )$ The proof of $( 1 ) \Leftrightarrow ( 3 )$ is similar to that of $( 1 ) \Leftrightarrow ( 2 )$ 号

Remark 4.6. From Theorem 4.5,we obtain that $g _ { a }$ is an implication derivation on an MV-algebra if and only if $a \in B ( L )$ . Based on the above consideration， we called $g _ { a }$ a Boolean implication derivation on an MV-algebra $L$

Definition 4.7. Let $L$ be an MV-algebra and $\mu _ { a }$ be a Boolean additive derivation on $L$ .The Boolean additive derivation $\mu _ { a }$ is called residuated if there exists a Boolean implicative derivation $\nu _ { a }$ on $L$ such that a pair $( \mu _ { a } , \nu _ { a } )$ forms a Galois connection.

The Boolean implicative derivation $\nu _ { a }$ is called the adjoint derivation of the Boolean additive derivation μa:

From the notion of Galois connections, we have that if the Boolean additive derivation $\mu _ { a }$ is residuated, then $\mu _ { a }$ and it's adjoint derivation must be isotone. In particular,if the Boolean additive derivation $\mu _ { a }$ has the adjoint derivation $\nu _ { a }$ , then the adjoint of $\mu _ { a }$ unique. Therefore, we shall denote this unique $\nu _ { a }$ by $\mu _ { a } ^ { * }$

Example 4.8. Consider the MV-algebra in Example 4.7. Define two maps $\nu _ { b } ( 0 ) =$ （204 $\nu _ { b } ( b ) = b$ ， $\nu _ { b } ( a ) = \nu _ { b } ( 1 ) = 1$ ， $\mu _ { b } ( 0 ) = \mu _ { b } ( a ) = 0$ ， $\mu _ { b } ( b ) = \mu _ { b } ( 1 ) = b$ ， respectively. One can check that $\nu _ { b }$ and $\mu _ { b }$ are Boolean implicative derivation and Boolean additive derivation on $L$ , respectively. Further, one can check that $\left( \nu _ { b } , \mu _ { b } \right)$ froms a Galois connection.

Theorem 4.9. Let $L$ be an MV-algebra and $a \in B ( L )$ .The the map $g _ { a } ( g _ { a } ^ { * } )$ is the adjoint derivation of the Boolean additive derivation $d _ { a } ^ { * } ( d _ { a ^ { * } } ^ { * } )$ on $L$ ， that is, （204号 $d _ { a } ^ { * } = g _ { a ^ { * } } ( d _ { a ^ { * } } ^ { * } = g _ { a } )$ ：

Proof. First, from Theorems 4.1 and 4.5, we get $d _ { a }$ and $g _ { a ^ { * } }$ are Boolean additive derivation and Boolean implicative derivation on $L$ , respectively. Moreover, for all $x , y \in L$ ，let $x \le y$ ， we conclude from Proposition 2.3 that $g _ { a ^ { * } } ( x ) = a  x \leq a $ $y = g _ { a ^ { * } } ( y )$ ,that is, $g _ { a ^ { * } }$ is isotone. For all $x , y \in L$ , we have $d _ { a } ( x ) = a \odot x \le y$ if and only if $x \leq a  y = g _ { a ^ { * } } ( y )$ . Thus, $( d _ { a } , g _ { a ^ { * } } )$ forms a Galois connection. Combining them，we obtain that $g _ { a ^ { * } }$ is the adjoint derivation of $d _ { a }$ ，that is, $d _ { a } ^ { * } = g _ { a ^ { * } }$ .In the similar way, one can prove that $d _ { a ^ { * } } ^ { * } = g _ { a }$ ：

In what follows, we denote by $F i x _ { d _ { a } } ( L )$ the set of all fixed points for $d _ { a }$ and $F i x _ { g _ { a } } ( L )$ the set of all fixed points of $L$ for $g _ { a }$ ， respectively.

Theorem 4.10. Let $L$ be an MV-algebra and $a \in B ( L )$ .Then $( F i x _ { d a } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ is an MV-algebra, where $\neg _ { 1 } x = d _ { a } ( x ^ { * } )$ , for all $x \in L$ ：

Proof. The proof is similar to that of Theorem 3.12.

Theorem 4.11． Let $L$ be an MV-algebra and $a \in B ( L )$ . Then $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$ is an MV-algebra, where $x ^ { \circ _ { 1 } } = g _ { a } ( x ^ { * } )$ ， for all $x \in L$ ：

Proof. First, we prove that $( F i x _ { g _ { a } } ( L ) , \oplus , a )$ is a commutative monoid. One can easy to check that $F i x _ { g _ { a } } ( L )$ is closed under $\bigoplus$ .It follows that $( F i x _ { g _ { a } } ( L ) , \oplus )$ is commutative semigroup. For all $x \in F i x _ { g _ { a } } ( L )$ ,we can obtain that $x \oplus a = x$ ,that is, $a$ is a unital element.

Next, we will prove that ( $F i x _ { g _ { a } } ( L )$ is closed under $\mathrm { { ^ o 1 } }$ . For all $x \in F i x _ { g _ { a } } ( L )$ ，we have $g ( x ^ { \circ _ { 1 } } ) = g ( g ( x ^ { * } ) ) = a \oplus a \oplus x ^ { * } = a \oplus x ^ { * } = g ( x ^ { * } ) = x ^ { \circ _ { 1 } }$ ，that is, $F i x _ { g _ { a } } ( L )$ is closed under $\mathrm { { ^ o 1 } }$ ：

Finally, we will verify the remaining axioms of an MV-algebra. (MV2) For all $x \in F i x _ { g _ { a } } ( L )$ , we have $x ^ { \circ _ { 1 } \circ _ { 1 } } = ( x ^ { \circ _ { 1 } } \odot ( a ^ { * } ) ^ { * } = ( ( x \odot a ) ^ { * } ) \oplus a ^ { * } ) ^ { * } =$ （20 $( x \odot a ^ { * } ) \oplus a = x \lor a = g _ { a } ( x ) \lor g _ { a } ( a ) = d ( x ) = x$ ,that is, $x ^ { \circ _ { 1 } \circ _ { 1 } } = x$ ． (MV3) For all $x \in F i x _ { g _ { a } } ( L )$ ， we have $x \oplus a ^ { \circ _ { 1 } } = x \oplus 1 = 1$ ， (MV4) For any $x , y \in F i x _ { g _ { a } } ( L )$ ， we have $( x ^ { \circ _ { 1 } } \oplus y ) ^ { \circ _ { 1 } } \oplus y = ( x ^ { \circ _ { 1 } } \odot y \odot a ^ { * } ) ^ { * } \odot y =$ $( x \odot a ^ { * } ) ^ { * } \odot y ) \odot a ^ { * } ) ^ { * } \odot y = ( ( x \odot a ^ { * } ) \oplus a \oplus y ^ { * } ) \odot y = ( ( x \vee a ) \oplus y ^ { * } ) \odot y = x \wedge y$ . In the similar way, one can prove that $( x ^ { \circ _ { 1 } } \odot y ^ { \circ _ { 1 } } ) ^ { \circ _ { 1 } } \odot x = x \wedge y$ , and hence $( x ^ { \circ _ { 1 } } \oplus y ) ^ { \circ _ { 1 } } \oplus y =$ $( x \oplus y ^ { \circ _ { 1 } } ) ^ { \circ _ { 1 } } \oplus x$ ：

Therefore,we obtain that $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$ is an MV-algebra.

Corollary 4.12. Let $L$ be an MV-algebra and $a \in B ( L )$ . Then $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$ is an MV-algebra, where $\neg _ { 2 } x = d _ { a ^ { * } } ( x ^ { * } )$ ， for all $x \in L$

Proof. The proof is similar to that of Theorem 4.10.

Corollary 4.13. Let $L$ be an MV-algebra and $a \in B ( L )$ . Then $( F i x _ { g _ { a ^ { * } } } ( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$ is an MV-algebra, where $x ^ { \circ _ { 2 } } = g _ { a ^ { * } } ( x ^ { * } )$ ， for all $x \in L$ ：

Proof. The proof is similar to that of Theorem 4.11.

The following theorem shows the relationship between $F i x _ { d _ { a } } ( L )$ and $F i x _ { g _ { a ^ { * } } } ( L )$

Theorem 4.14. Let $L$ be an MV-algebra and $a \in B ( L )$ .Then MV-algebras $( F i x _ { d _ { a } } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ and $( F i x _ { g _ { a ^ { * } } } ( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$ are isomorphic.

Proof. For all $a \in L$ ,let $f : F i x _ { d _ { a } } ( L ) \longrightarrow F i x _ { g _ { a ^ { * } } } ( L )$ be defined by $f ( x ) = a ^ { * } \oplus x$ （20   
for all $x \in F i x _ { d _ { a } } ( L )$ . Clearly, $f$ is a map from $F i x _ { d _ { a } } ( L )$ to $F i x _ { g _ { a ^ { * } } } ( L )$ ,that is, $f$ is   
well defined. (1) For all $x , y \in F i x _ { d _ { a } } ( L )$ ， we have $f ( x \oplus y ) = a ^ { * } \oplus ( x \oplus y ) = a ^ { * } \oplus a ^ { * } \oplus x \oplus y =$   
$( a ^ { * } \oplus x ) \oplus ( a ^ { * } \oplus y ) = f ( x ) \oplus f ( y )$ ,that is, $f ( x \oplus y ) = f ( x ) \oplus f ( y )$ ， (2) For all $x \in F i x _ { d _ { a } } ( L )$ ，we have $f ( \neg _ { 1 } x ) = a ^ { * } \oplus ( a \odot x ^ { * } ) = a ^ { * } \lor ( a \land x ^ { * } ) =$   
$( a ^ { * } \vee a ) \wedge ( a ^ { * } \vee x ) = a ^ { * } \oplus x$ . One the other hand, we have $( f ( x ) ) ^ { \circ _ { 2 } } = ( a ^ { * } \oplus x ) ^ { \circ _ { 2 } } =$   
（20 $a ^ { * } \oplus ( a ^ { * } \oplus x ) = a ^ { * } \oplus x$ and hence $f ( \neg _ { 1 } x ) = ( f ( x ) ) ^ { \circ _ { 2 } }$ . (3) For all $x , y \in F i x _ { d _ { a } } ( L )$ ，that is, $x = a \odot x$ and $y = a \odot y$ ，if $f ( x ) = f ( y )$ ，   
then $a ^ { * } \oplus x \ : = \ : a ^ { * } \oplus y$ .From $a \odot x \le x$ ，we have $x \leq a  x = a ^ { * } \oplus x$ ，then   
（20 $x \leq a ^ { * } \oplus y = a \to y$ . It follows that $a \odot x \le y$ ，which implies $x \leq y$ . Similarly, we   
can prove $y \le x$ and hence $x = y$ . Consequently, we obtain that $f$ is injective. (4) One can easily prove the fact that $x ^ { * } \vee y = x ^ { * } \oplus ( x \odot y ) = y$ if and only if there   
exists $z \in L$ such that $x ^ { * } \oplus z = y$ for all $x , y \in L$ . From the above fact, we will prove   
that $f$ is surjective. Now, for all $x \in F i x _ { g _ { a ^ { * } } } ( L )$ , then $x = g _ { a ^ { * } } ( x ) = a ^ { * } \oplus x$ . Using the   
above fact, we have that $f ( a \odot x ) = a ^ { * } \oplus ( a \odot x ) = a ^ { * } \oplus ( a \odot ( a ^ { * } \oplus x ) ) = a ^ { * } \oplus x = x$ ：   
Thus, we conclude that $f$ is surjective. Also, it is easy to verify that $f ^ { - 1 } ( x ) = a \odot x$ （20   
is a homomorphism from $F i x _ { g _ { a ^ { * } } } ( L )$ to $F i x _ { d _ { a } } ( L )$ ：

Combining them,we obtain that $f$ is an isomorphism from $( F i x _ { d a } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ t0 $( F i x _ { g _ { a ^ { * } } } ( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$ . Therefore, MV-algebras $( F i x _ { d _ { a } } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ and $( F i x _ { g _ { a ^ { * } } }$ $( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$ are isomorphic.

Theorem 4.15. Let $L$ be an MV-algebra and $a \in B ( L )$ .Then MV-algebras $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$ and $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$ are isomorphic.

Proof. For all $a \in L$ ，let $u : F i x _ { d _ { a ^ { * } } } ( L ) \longrightarrow F i x _ { g _ { a } } ( L )$ be defined by $u ( x ) = a \oplus x$ （204号 for all $x \in F i x _ { d _ { a ^ { * } } } ( L )$ . Clearly, $u$ is a map from $F i x _ { d _ { a ^ { * } } } ( L )$ to $F i x _ { g _ { a } } ( L )$ , that is, $u$ is well defined.

(1) For all $x , y \in F i x _ { d _ { a ^ { * } } } ( L )$ ， we have $u ( x \oplus y ) = a \oplus ( x \oplus y ) = a \oplus a \oplus x \oplus y =$ $( a \oplus x ) \oplus ( a \oplus y ) = u ( x ) \oplus u ( y )$ ,that is, $\boldsymbol { u } ( \boldsymbol { x } \oplus \boldsymbol { y } ) = \boldsymbol { u } ( \boldsymbol { x } ) \oplus \boldsymbol { u } ( \boldsymbol { y } )$ ： (2) For all $x \in F i x _ { d _ { a ^ { * } } } ( L )$ , we have $u ( \lnot x ) = a \oplus ( a \odot x ^ { * } ) = a \lor ( a \land x ^ { * } ) = ( a \lor a ) \land$ （20 $( a \lor x ) = a \oplus x$ . One the other hand, we have $( u ( x ) ) ^ { \circ _ { 1 } } = ( a \oplus x ) ^ { \circ _ { 1 } } = a \oplus ( a \oplus x ) = a \oplus x$ and hence $u ( \neg _ { 2 } x ) = ( u ( x ) ) ^ { \circ _ { 1 } }$ ： (3) For all $x , y \in F i x _ { d _ { a ^ { * } } } ( L )$ , that is, $x = a \ominus x$ and $y = a \ominus y$ ，if $u ( x ) = u ( y )$ ， then $a \oplus x = a \oplus y$ . From $a \ominus x \le x$ ， we have $x \leq a \oplus x$ ， then $x \leq a \oplus y$ . It follows that $a \ominus x \le y$ ，which implies $x \le y$ . Similarly, we can prove $y \le x$ and hence （204号 $x = y$ . Consequently, we obtain that $u$ is injective. (4) One can easily prove the fact that $x \vee y = x \oplus ( y \ominus x ) = y$ if and only if there exists $z \in L$ such that $y \ominus z = x$ for all $x , y \in L$ . From the above fact,we will prove that $u$ is surjective. Now, for all $x \in F i x _ { g _ { a } } ( L )$ ，then $x = g _ { a } ( x ) = a \oplus x$ . Using the above fact, we have that $u ( x \ominus a ) = a \oplus ( x \ominus a ) = a \oplus ( ( a \oplus x ) \ominus a ) = a \oplus x = x$ Thus,we conclude that $u$ is surjective. Also, it is easy to verify that $u ^ { - 1 } ( x ) = x \ominus a$ （204号 is a homomorphism from $F i x _ { g _ { a } } ( L )$ to $F i x _ { d _ { a ^ { * } } } ( L )$ ：

Combining them, we obtain that $u$ is an isomorphism from $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$ to $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$ Therefore, MV-algebras $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$ and $( F i x _ { g _ { a } }$ $( L ) , \oplus , \circ _ { 1 } , a , 1 )$ are isomorphic.

In the following,we prove a representation theorem for MV-algebras

Theorem 4.16.Let $L$ be an MV-algebra and $a \in B ( L )$ . Then MV-algebra $L$ isisomorphic to the direct product $( F i x _ { d _ { a } } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ and $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$

Proof. For all $a \in L$ ，let $\tau : L \longrightarrow F i x _ { d _ { a } } ( L ) \times F i x _ { d _ { a ^ { * } } } ( L )$ be defined by $\tau ( x ) =$ $( x \odot a , x \odot a )$ for all $x \in L$ . Clearly, $\tau$ is a map from $L$ to $F i x _ { d _ { a } } ( L ) \times F i x _ { d _ { a ^ { * } } } ( L )$ ， that is, $\tau$ is well defined.

(1) From Theorem 3.13 and 4.1, we get $\tau$ is a homomorphism from $L$ to $F i x _ { d _ { a } } ( L ) \times F i x _ { d _ { a ^ { * } } } ( L )$ ： (2) Now, we prove that $\tau$ is injective. If $x _ { 1 } \in F i x _ { d _ { a } } ( L )$ and $x _ { 2 } \in F i x _ { d _ { a ^ { * } } } ( L )$ ， then for $x = x _ { 1 } \vee x _ { 2 }$ ， we have $\tau ( x ) = ( x _ { 1 } , x _ { 2 } )$ since $( L , \land , \lor )$ is a distributive lattice and $x = ( x \wedge a ) \vee ( x \wedge a ^ { * } )$ for all $x \in L$ . Consequently, we obtain that $\tau$ is injective. Also, it is easy to verify that $\tau ^ { - 1 } ( x , y ) = x \vee y$ for all $( x , y ) \in F i x _ { d _ { a } } ( L ) \times F i x _ { d _ { a ^ { * } } } ( L )$ is a homomorphism from $F i x _ { d _ { a } } ( L ) \times F i x _ { d _ { a ^ { * } } } ( L )$ to $L$ ：

Combining them,we obtain that $\tau$ is an isomorphism from $L$ to the direct product $( F i x _ { d _ { a } } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ and $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$ . Therefore, MV-algebra $L$ is isomorphic to the direct product $( F i x _ { d _ { a } } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ and $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$

Theorem 4.17.Let $L$ be an MV-algebra and $a \in B ( L )$ . Then MV-algebra $L$ is isomorphic to the direct product $( F i x _ { g _ { a ^ { * } } } ( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$ and $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$

Proof. For all $a \in L$ ，let $\phi : L \longrightarrow F i x _ { g _ { a } } ( L ) \times F i x _ { g _ { a ^ { * } } } ( L )$ be defined by $\phi ( x ) = $ （204号 $( x \oplus a , x \to a )$ for all $x \in L$ . Clearly, $\phi$ is a map from $L$ to $F i x _ { g _ { a } } ( L ) \times F i x _ { d _ { g ^ { * } } } ( L )$ ， that is, $\phi$ is well defined.

(1) From Theorems 4.11 and Corollary 4.13, we get $\phi$ is a homomorphism from $L$ to $F i x _ { g _ { a } } ( L ) \times F i x _ { g _ { a ^ { * } } } ( L )$ (2） Now, we prove that $\phi$ is injective. If $x _ { 1 } \in F i x _ { g _ { a } } ( L )$ and $x _ { 2 } \in F i x _ { g _ { a ^ { * } } } ( L )$ ， then for $x = x _ { 1 } \wedge x _ { 2 }$ ， we have $\phi ( x ) = ( x _ { 1 } , x _ { 2 } )$ since $( L , \wedge , \vee )$ is a distributive lattice and $x = ( x \vee a ) \wedge ( x \vee a ^ { * } )$ for all $x \in L$ . Consequently, we obtain that $\varphi$ is injective. Also, it is easy to verify that $\phi ^ { - 1 } ( x , y ) = x \wedge y$ for all $( x , y ) \in F i x _ { g _ { a } } ( L ) \times F i x _ { g _ { a ^ { * } } } ( L )$ is a homomorphism from $F i x _ { g _ { a } } ( L ) \times F i x _ { g _ { a ^ { * } } } ( L )$ to $L$ ：

Combining them,we obtain that $\phi$ is an isomorphism from $L$ to the direct product $( F i x _ { g _ { a ^ { * } } } ( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$ and $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$ . Therefore, MV-algebra $L$ is isomorphic to the direct product $( F i x _ { g _ { a ^ { * } } } ( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$ and $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$

From Theorem 4.14-4.17, the following theorems are immediate consequence.

Theorem 4.18.Let $L$ be an MV-algebra and $a \in B ( L )$ . Then MV-algebra $L$ is isomorphic to the direct product $( F i x _ { d _ { a } } ( L ) , \oplus , \lnot _ { 1 } , 0 , a )$ and $( F i x _ { g _ { a } } ( L ) , \oplus , \circ _ { 1 } , a , 1 )$

Proof.It follows from Theorem 4.14 and 4.16

Theorem 4.19.Let $L$ be an MV-algebra and $a \in B ( L )$ . Then MV-algebra $L$ isisomorphic to the direct product $( F i x _ { d _ { a ^ { * } } } ( L ) , \oplus , \lnot _ { 2 } , 0 , a ^ { * } )$ and $( F i x _ { g _ { a ^ { * } } } ( L ) , \oplus , \circ _ { 2 } , a ^ { * } , 1 )$

Proof. It follows from Theorem 4.15 and 4.17.

In what follows, as applications of Boolean derivations, some characterizations of Boolean algebras will be given.

Theorem 4.20.Let $L$ be an MV-algebra. Then the following statements are equivalent:

(1) $L$ is a Boolean algebra, (2) for any $a \in L$ ， $F i x _ { d _ { a } } ( L ) = ( a ]$ (3) for any $a \in L$ ， $F i x _ { g _ { a } } ( L ) = [ a )$

Proof. $( 1 ) \Rightarrow ( 2 )$ Assume that $L$ is a Boolean algebra, we have $x \odot x = x$ for all （204号 $x \in L$ . It follows that $d _ { a } ( a ) = a \odot a = a$ for all $a \in L$ . Thus, $a \in F i x _ { d _ { a } } ( L )$ . Since $L$ is a Boolean algebra,we have that $F i x _ { d _ { a } } ( L )$ is an ideal of $L$ by Proposition 3.19 and Theorem 4.1. That is, for all $x \in L$ ，if $x \leq a$ ，we obtain that $x \in F i x _ { d _ { a } } ( L )$ ， which implies that $( a ] \subseteq F i x _ { d _ { a } } ( L )$ . Next, we will show that $F i x _ { d _ { a } } ( L ) \subseteq ( a ]$ . For all （204号 $x \in F i x _ { d _ { a } } ( L )$ , we have $d _ { a } ( x ) = a \odot x = a \land x = x$ ，which implies that $x \leq a$ , that is, （204 $x \in ( a ]$ . It follows that $F i x _ { d _ { a } } ( L ) \subseteq ( a ]$ . Therefore,we obtain that $F i x _ { d _ { a } } ( L ) = ( a ]$ $( 2 ) \Rightarrow ( 1 )$ Assume that $F i x _ { d _ { a } } ( L ) = ( a ]$ for all $a \in L$ . Since $a \in ( a ]$ ，we get $a \in$ （204号 $F i x _ { d _ { a } } ( L )$ . It follows that $d _ { a } ( a ) = a$ ,that is, $a \odot a = a$ for all $a \in L$ . Therefore, we obtain that $L$ is a Boolean algebra.

$( 1 ) \Rightarrow ( 3 )$ Assume that $L$ is a Boolean algebra, we have $x \oplus x = x$ for all $x \in L$ 业 It follows that $g _ { a } ( a ) = a \oplus a = a$ for all $a \in L$ . Thus, $a \in F i x _ { g _ { a } } ( L )$ . Since $L$ isa Boolean algebra, one can easy to check that $F i x _ { g _ { a } } ( L )$ is a filter of $L$ by Theorem 4.5. That is, for all $x \in L$ ,if $a \leq x$ ，we obtain that $x \in F i x _ { g _ { a } } ( L )$ ，which implies that $[ a ) \subseteq F i x _ { g _ { a } } ( L )$ . Next, we will show that $F i x _ { g _ { a } } ( L ) \subseteq ( a ]$ . For all $x \in F i x _ { g _ { a } } ( L )$ ， we have $g _ { a } ( x ) = a \oplus x = a \lor x = x$ ，which implies that $a \leq x$ ,that is, $x \in [ a )$ .It follows that $F i x _ { g _ { a } } ( L ) \subseteq [ a )$ . Therefore,we obtain that $F i x _ { g _ { a } } ( L ) = [ a )$

$( 3 ) \Rightarrow ( 1 )$ Assume that $F i x _ { g _ { a } } ( L ) = [ a )$ for all $a \in L$ .Since $a \in [ a )$ ，we get （204号 $a \in F i x _ { g _ { a } } ( L )$ . It follows that $g _ { a } ( a ) = a$ , that is, $a \oplus a = a$ for all $a \in L$ . Therefore, we obtain that $L$ is a Boolean algebra.

In what follows, we focus on algebraic structure the set of all additive (implicative） Boolean derivations. We denote by $D ( L ) = \{ d _ { a } | a \in B ( L ) \} ( G ( L ) = \{ g _ { a } | a \in$ $B ( L ) \}$ ）be the set of all additive (implicative) Boolean derivations of $L$ ：

Theorem 4.21. Let $L$ be an MV-algebra. Then $( D ( L ) , \sqcup , \sqcap , \star , d _ { 0 } , d _ { 1 } )$ is a Boolean algebra,where $( d _ { a } \sqcup d _ { b } ) x = ( d _ { a } x ) \vee ( d _ { b } x )$ ， $( d _ { a } \sqcap d _ { b } ) x = ( d _ { a } x ) \wedge ( d _ { b } x )$ ， $( d _ { a } ) ^ { \star } x = d _ { a ^ { \ast } } x$ （204号 $( d _ { 0 } ) ^ { \star } = d _ { 1 }$ , for any $d _ { a } , d _ { b } \in D ( L )$

Proof. First, we show that $( D ( L ) , \sqcup , \sqcap , d _ { 0 } , d _ { 1 } )$ is a bounded lattice with $d _ { 0 }$ as the smallest element and $d _ { 1 }$ as the greatest element. For all $d _ { a } , d _ { b } \in D ( L )$ and $x \in L$ ，we have $( d _ { a } \Pi d _ { b } ) ( x ) = ( d _ { a } ( x ) ) \wedge ( d _ { b } ( x ) ) = ( a \odot x ) \wedge ( b \odot x ) = ( a \wedge x ) \wedge ( b \wedge x ) = ( a \wedge b ) \wedge x = ( a \odot b )$ $( a \wedge b ) \odot x = d _ { a \wedge b } ( x )$ , that is, $\left( d _ { a } \Pi d _ { b } \right) = d _ { a \wedge b }$ and hence $d _ { a } \cap d _ { b } \in D ( L )$ . Furthermore, we have $( d _ { a } \sqcup d _ { b } ) ( x ) = ( d _ { a } ( x ) \vee d _ { b } ( x ) ) = ( a \odot x ) \vee ( b \odot x ) = ( a \wedge x ) \vee ( b \wedge x ) =$ $( a \lor b ) \land x = ( a \lor b ) \odot x = d _ { a \lor b } ( x )$ , that is, $( d _ { a } \sqcup d _ { b } ) = d _ { a \vee b }$ and hence $d _ { a } \sqcup d _ { b } \in D ( L )$ Therefore, $( D ( L ) , \sqcup , \sqcap , d _ { 0 } , d _ { 1 } )$ is a lattice. For all $d _ { a } \in D ( L )$ and $x \in L$ ， we have $( d _ { a } \Pi d _ { 0 } ) ( x ) = d _ { a } ( x ) \wedge d _ { 0 } ( x ) = 0 = d _ { 0 } ( x )$ and $( d _ { a } \sqcup d _ { 1 } ( x ) = d _ { a } ( x ) \vee d _ { 1 } ( x ) = x = d _ { 1 } ( x )$ Thus, $d _ { 0 }$ is the smallest element and $d _ { 1 }$ is the greatest element in $D ( L )$ ：

Next, we prove that $( D ( L ) , \sqcup , \sqcap )$ is a distributive lattice. For all $d _ { a } , d _ { b } , d _ { c }$ and $x \in L$ ，from $( L , \vee , \wedge )$ is a distributive lattice,one can prove $( d _ { a } \sqcup ( d _ { b } \sqcap d _ { c } ) = ( d _ { a } \sqcup $ $d _ { b } ) \cap ( d _ { a } \sqcup d _ { c } )$ and $( d _ { a } \Pi ( d _ { b } \sqcup d _ { c } ) = ( d _ { a } \sqcap d _ { b } ) \sqcup ( d _ { a } \sqcap d _ { c } )$ . Therefore, $( D ( L ) , \sqcup , \sqcap , d _ { 0 } , d _ { 1 } )$ is a bounded distributive lattice.

Finally, we prove that $( D ( L ) , \sqcup , \sqcap , \star , d _ { 0 } , d _ { 1 } )$ is a Boolean algebra. For all $d _ { a } \in$ $D ( L )$ and $x \in L$ ， we have $( d _ { a } ) ^ { \star } ( x ) = d _ { a ^ { * } } ( x ) = a ^ { * } \odot x = d _ { a ^ { * } } ( x )$ ,that is, $( d _ { a } ) ^ { \star } ( x ) =$ （204号 $d _ { a ^ { * } } ( x )$ . One can easy check that if $a \in B ( L )$ ，then $a ^ { * } \in B ( L )$ ，and hence ${ d _ { a } } ^ { \star } \in$ （20 $D ( L )$ . furthermore, we have $( d _ { a } \sqcup ( d _ { a } ) ^ { \star } ) ( x ) = ( d _ { a } ) ( x ) \vee d _ { a ^ { * } } ( x ) = ( a \odot x ) \vee ( a ^ { * } \odot x ) =$ $( a \lor a ^ { * } ) \odot x = x = d _ { 1 } ( x )$ and $( d _ { a } \sqcap ( d _ { a } ) ^ { \star } ) ( x ) = ( d _ { a } ) ( x ) \wedge d _ { a ^ { * } } ( x ) = ( a \odot x ) \wedge ( a ^ { * } \odot x ) =$ $( a \lor a ^ { * } ) \land x = 0 = d _ { 0 } ( x )$ ,that is, $( d _ { a } \sqcup ( d _ { a } ) ^ { \star } ) = d _ { 1 }$ and $( d _ { a } \sqcap ( d _ { a } ) ^ { \star } ) = d _ { 0 }$ . Therefore, $( D ( L ) , \sqcup , \sqcap , \star , d _ { 0 } , d _ { 1 } )$ is a Boolean algebra.

Theorem 4.22. Let $L$ be an MV-algebra. Then $( G ( L ) , \cap , \cup , \bullet , g _ { 0 } , g _ { 1 } )$ is a Boolean algebra， where $( g _ { a } \cup g _ { b } ) x = ( g _ { a } x ) \vee ( g _ { b } x )$ ， $( g _ { a } \cap g _ { b } ) x = ( g _ { a } x ) \wedge ( g _ { b } x )$ ， $( g _ { a } ) ^ { \bullet } x = g _ { a ^ { \ast } } x$ ， （204号 $( g _ { 0 } ) ^ { \bullet } = g _ { 1 }$ , for any $g _ { a } , g _ { b } \in G ( L )$ ：

Proof. The proof is similar to that of Theorem 4.21.

Theorem 4.23.Let $L$ be an MV-algebra. Then Boolean algebras $( B ( L ) , \wedge , \vee , * , 0 , 1 )$ （204号 and $( D ( L ) , \sqcup , \sqcap , \star , d _ { 0 } , d _ { 1 } )$ are isomorphic.

Proof. Let $\phi : B ( L ) \longrightarrow D ( L )$ be defined by $\phi ( a ) = d _ { a }$ for all $a \in B ( L )$ . Clearly, $\phi$ is a map from $B ( L )$ to $D ( L )$ ,that is, $\phi$ is well defined. One can easily see that $\phi$ is one to one and onto.

Furthermore, for any $a , b \in B ( L )$ , we have $\phi ( a \wedge b ) = d _ { a \wedge b } = d _ { a } \sqcap d _ { b } = \phi ( a ) \sqcap \phi ( b )$ $\phi ( a \lor b ) = d _ { a \lor b } = d _ { a } \sqcup d _ { b } = \phi ( a ) \sqcup \phi ( b )$ and $\phi ( a ^ { * } ) = d _ { a ^ { * } } = ( d _ { a } ) ^ { \star } = ( \phi ( a ) ) ^ { \star }$ ：

Combining them, we obtain that $\phi$ is an isomorphism from $( B ( L ) , \wedge , \vee , * , 0 , 1 )$ to $( D ( L ) , \sqcup , \sqcap , \star , d _ { 0 } , d _ { 1 } )$ . Therefore, Boolean algebras $( B ( L ) , \land , \lor , * , 0 , 1 )$ and $( D ( L )$ $\sqcup , \sqcap , \star , d _ { 0 } , d _ { 1 } )$ are isomorphic.

Theorem 4.24. Let $L$ be an MV-algebra. Then Boolean algebras $( B ( L ) , \wedge , \vee , * , 0 , 1 )$ and $( G ( L ) , \cap , \cup , \bullet , g _ { 0 } , g _ { 1 } )$ are isomorphic.

Proof. The proof is similar to that of Theorem 4.23.

The next theorem is now an immediate consequence.

Theorem 4.25.Let $L$ be a Boolean algebra. Then （1） $( L , \wedge , \vee , * , 0 , 1 )$ is isomorphic to $( D ( L ) , \sqcup , \sqcap , \star , d _ { 0 } , d _ { 1 } )$ (2) $( L , \wedge , \vee , * , 0 , 1 )$ is isomorphic to $( G ( L ) , \cap , \cup , \bullet , g _ { 0 } , g _ { 1 } )$ ：

Proof. It follows from Theorem 4.23,4.24.

# 5．Conclusions

The notion of derivations gives a tool for studying structures and properties in algebraic systems. In the paper, some related properties of particular derivations are discussed. Also, we obtain that the fixed point set of additive derivations is still an MV-algebra. Besides, we get that the fixed point set of Boolean additive derivations and that of their adjoint derivations are isomorphism. Finally, we obtain that every MV-algebra is isomorphic to the direct product of the fixed point set of Boolean additive derivations and that of their adjoint derivations. In the future, we will consider the open problem in this paper.

# Compliance with Ethical Standard

This research is partially supported by a grant of National Natural Science Foundation of China (11601302).

Conict of Interest: The authors declare that there is no con ict of interests.

Ethical approval: This article does not contain any studies with human participants or animals performed by any of the authors.

Informed consent: Informed consent was obtained from all individual participants included in the study.

# References

[1]L.Aivao, utaId aiiu UIviuguiiai gtitiaIiztu utiivavIis UI spII Ig, Math. J. Okayama Univ., 49(2007) 53-58. [2] N. O. Alshehri, Derivations of MV-algebras, Int. J. Math. Math. Sci., 2010, doi:10.1155/2010/312027. [3] L. K. Ardekani, B. Davvaz, On Generalized derivations of BCI-algebras and their properties,Journal of Mathematics, 2015(2015） 1-10. [4] L. K. Ardekani， B. Davvaz， $f$ -derivations and $( f , g )$ -derivations of MValgebras, J. algebraic syst., 1 (2013) 11-31. [5] H. E. Bell, L. C. Kappe, Rings in which derivations satisfy certain algebraic conditions, Acta Math. Hungar., 53(1989) 339-346. [6] H. E. Bell,G. Mason， On derivations in near-rings and near-felds,NorthHolland Math. Studies., 137 (1987) 31-35. [7] R. A. Borzooei, O. Zahiri， Some results on derivations of BCI-algebras, J. natur. sci. math., 26 (2013) 529-545.   
[8] C. C. Chang, Algebraic analysis of many-valued logic, Trans Am Math Soc., 88 (1958) 467-490. [9] C. C. Chang，A new proof of the completeness of the Lukasiewicz axioms, Trans Am Math Soc., 93 (1959) 74-80.   
[10] R. Cignoli, D. Mundici, An elementary proof of Chang's completeness theorem for the infinite-valued calculus of Lukasiewicz, Stud. Log., 58 (1997) 79-97.   
[11] R. Cignoli, I.M.L. D'Ottaviano, D. Mundici, Algebraic Foundations of Manyvalued Reasoning. Kluwer Academic Publ., Dordrecht, 2000.   
[12] L. Ferrari, On derivations of lattices, Pure Math Appl., 12 (2001) 365-382.   
[13] S.Ghorbain，L. Torkzadeh， S. Motamed， $( \odot , \oplus )$ -derivations and $( \odot , \odot )$ derivations on MV-algebras, Iran. J. Math. Sci. Inform., 8 (2013) 75-90.   
[14] G. Grätzer, Lattice theory, W. H. Freeman and Company, San Francisco, 1979.   
[15] S.L. Huang, B. Davvaz, Generalized derivations of rings and Banach algebras, Comm. Algebra., 41 (2013) 1188-1194.   
[16] P. F.He, X. L. Xin, J. M. Zhan, On derivations and their fixed point sets in residuated lattices, Fuzzy Sets Syst., 303 (2016) 97-113.   
[17] Y. B. Jun, X. L. Xin, On derivations of BCI-algebras, Inform. Sci., 159 (2004) 167-176.   
[18] J. Lukasiewicz, A. Tarski, Untersuchungen über den Aussagenkalkul, Comptes Rendus des Séances de la Societé des Science et des Letters de., 23(1930) 30- 50.   
[19] E. Posner, Derivations in prime rings, Proc. Amer. Math. Soc., 8(1957) 1093- 1100.   
[20] E. Turunen， Mathematics Behind Fuzzy Logic. Physica-Verlag, Heidelberg, 1999.   
[21] X.L. Xin, The fixed set of aderivation in lattices, Fixed Point Theory Appl., 218(2012) 1-12.   
[22] X. L. Xin, M. Feng, Y. W. Yang, On $\odot$ -derivations of BL-algebras, J. of Math (P. R. C) ., 36 (2016) 552-558.   
[23] H. Yazarli,A note on derivations in MV-algebras,Miskolc Math Notes., 14 (2013) 345-354.   
[24] J. M. Zhan, Y.L. Liu, On $f$ -derivations of BCI-algebras, Int. J. Math.Math Sci., 11 2005,176-191.