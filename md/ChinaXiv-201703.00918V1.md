# Monadic NM-algebras

Jun Tao Wang $\mathbf { \Pi } _ { . } ^ { . a . }$ , Xiao Long Xin $^ { a , * }$ ,Peng Fei He $b$

$\boldsymbol { a }$ School of Mathematics,Northwest University，Xi'an, 710127, China $b$ School of Mathematics and Information Science, Shaanxi Normal University，, Xi'an, 710119, China

# Abstract

The main goal of this paper is to investigate (strong) monadic NM-algebras and to prove the (chain） completeness of the monadic NM-logic. In this paper， we introduce monadic NM-algebras: a variety of NM-algebras equipped with universal quantifiers. Also,we study some properties of them and obtain some conditions under which a monadic NM-algebra becomes a monadic Boolean algebra. Besides, we show that the variety of NM-algebras are the equivalent algebraic semantics of the monadic fragment of NM predicate logic. Furthermore,we discuss relations between monadic NM-algebras and some related structures, likeness modal NMalgebras and rough approximation spaces. In addition, we introduce and investigate monadic filters in monadic NM-algebras. In particular, by using monadic filters on monadic NM-algebras, we characterize two kinds of monadic NM-algebras, which are simple and subdirectly irreducible. Moreover, we focus on a monadic analogous of representation theorem for NM-algebras and obtain that every strong monadic NM-algebra can be represented as subalgebras of products of linearly ordered ones. Then, we present monadic NM-logic, a system of many-valued logic capturing the tautologies of the predicate logics of nilpotent minimum t-norm and it's residua. As an application of (strong) monadic NM-algebras, we prove the (chain)completeness of monadic NM-logic. Our results constitute a crucial first step for providing a solid algebraic foundation for the one element fragment of NM predicate logic.

Keywords: monadic NM-algebra; monadic flter; subdirect representation; monadic NM-logic   
2000MSC:06D35，06B99

# 1．Introduction

It is well known that certain information processing approaches, especially inferences based on certain information， are based on the classical logic (classical two-valued logic). Naturally, it is necessary to establish some rational logic systems as a logical foundation for uncertain information processing. For this reason, various types of non-classical logic systems have been proposed and researched. Non-classical logic has become a formal and useful tool in computer science for dealing with uncertain and fuzzy information. Various logical algebras have been proposed as semantic systems for non-classical logic systems, such as MV-algebras, BL-algebras, Godel algebras, MTL-algebras and NM-algebras. Among these logical algebras, MTL-algebras are the most significant because the others are all particular cases of MTL-algebras. In fact， MTL-algebras contain all algebras induced by left continuous t-norm and their residua. As an most important class of MTL-algebras, nilpotent minimum algebras (NM-algebras for short） are MTL-algebras satisfying the low of involution of the negation $\neg \neg x = x$ and $( \neg ( x \odot y ) ) \lor ( x \land y )  ( x \odot y ) ) = 1$ ， are the corresponding algebraic structures of nilpotent minimum logic (NM for short)[25]. Well know fuzzy logic such as Lukasiewicz logic, Godel logic and Product logic can be regarded as schematic extensions of Basic Logic (BL for short) [26]. It must be to point out here that the NM logic is not an axiomatic extension of BL because the corresponding t-norm in the NM-algebra is not continuous but only left-continuous. In the last few years, the theory of NM-algebras has been enriched with structure theorems [28-30]. Many of these results have a strong impact with fuzzy logic. In particular， from the structure theory of NM-algebras, one established stone topological representation theorem and characterize the irreducibly representation theorem for NM-algebras[14, 9]. It is also investigated the basic structures of NM-algebras by the standpoint of quotient algebras[3]. As an algebraic structure based on left continuous t-norm, an NM-algebra without the identity $x \wedge y = x \odot ( x \to y ) = y \odot ( y \to x )$ . It follows that an NM-algebra is not BL-algebra and MV-algebra. Therefore, NM-algebras play an important role in studying fuzzy logics and the related algebraic structures. The filter theory of the NM-algebras plays an important role in studying these algebras and the completeness of the NM-logic. From a logic point of view, various filters have natural interpretation as various sets of provable formulas. Wang introduced the idea of filters and prime filters in NM-algebras to prove the completeness and chain completeness of NM-logic [8]. Zhang introduced the concepts of positive implicative filters， fantastic filters and MV-filters in NM-algebras and proved that positive implicative filters, implicative filters and Boolean filters are equivalent, fantastic filters and MV-filters are equivalent in NM-algebras [16].

Monadic (Boolean) algebras in the sense of Halmos [29] are Boolean algebras equipped with a closure operator $\exists$ whose range is a subalgebra of Boolean algebra. This operator abstracts algebraic properties of the standard existential quantifier “for some”. The name “monadic” comes from the connection with predicate logics for languages having one placed predicates and a single quantifier. Monadic Boolean algebras have been deeply investigated in [24,17]. Inspired by this, algebraic counterparts of the existential or universal quantifiers have been consequently studied also for certain non classical logics. Recall that monadic MV-algebras, an algebraic model of the one element fragment of Lukasiewicz predicate logic, were introduced and studied in [18] and the theory of monadic MV-algebras has been developed in [1]. Monadic GMV-algebras having the same sense for non-commutative Lukasiewicz logic were introduced and investigated in[20]. Monadic Heyting algebras were introduced in [2] as an algebraic model of the one-variable fragment of the intuitionistic predicate logic and consequently they were developed in [10]. Inspired by monadic Heyting algebras, monadic BL-algebras and monadic bounded hoops were introduced and investigated in [27] and [22], respectively. In the abovementioned monadic algebras, since both MV-algebras and GMV-algebras satisfy deMorgan and double negation laws, in the definition of the corresponding monadic algebras it is possible to use only one of the existential and universal quantifiers as initial, the other is then definable as the dual of the original one. In contrast to the monadic MV-algebras and GMV-algebras, the definitions of monadic Heyting algebras, monadic BL-algebras and monadic bounded hoops require using both kinds of quantifiers simultaneously, because these quantifiers are not mutually interdefinable.

In this paper, we will extend quantifiers to NM-algebras for providing a solid algebraic foundation for the one element fragment of NM predicate logic. One of our aims is to introduce monadic NM-algebras similarly as the monadic MValgebras in which only a single individual variable occurs. In particular, the paper [25] was a first attempt to define a pair of unary operators with some properties of quantifiers also for NM-algebras using the existential and universal quantifiers (analogously as for monadic BL-algebras, monadic Heyting algebras and monadic bounded hoops). But it seems to be more appropriate to introduce such monadic algebras similarly as the monadic MV-algebras in which only a single individual variable occurs since NM-algebras also satisfy deMorgan and double negation laws. On the other hand, the main focus of existing research about quantifiers is on MValgebras, BL-algebras, Heyting algebras and hoops,etc. All the above-mentioned algebraic structures satisfy the divisibility condition $x \wedge y = x \odot ( x \to y )$ . In this case，the conjunction $\odot$ on the unit interval corresponds to a continuous $ { \mathrm { ~  ~ t ~ } }$ -norm. However, there is no research about quantifiers on residuated structures without the divisibility condition so far. In fact,NM-algebras are the residuated structure induced by left continuous $\mathrm { t }$ -norm,which does not satisfy the divisibility condition. Therefore, it is interesting study quantifiers on NM-algebras for providing a solid algebraic foundation for the one element fragment of the NM predicate logic. These are motivations for us to investigate monadic NM-algebras.

This paper is structured in five sections. In order to make the paper as selfcontained as possible, we recapitulate in Section 2 the definition of NM-algebras, and review their basic properties that will be used in the remainder of the paper. In Section 3, we introduce quantifiers on NM-algebras and study some properties of them. Also,we give some conditions under which a monadic NM-algebra is a monadic Boolean algebra and discuss the relationship between monadic NMalgebras and related structures. In Section 4，we investigate monadic filters of monadic NM-algebras and focus on a monadic analogous of representation theorem for NM-algebras. Then we introduce and characterize simple and subdirectly irreducible monadic NM-algebras by monadic filters. In Section 5, we exhibit an axiom system of monadic NM-logic. As an application of (strong) monadic NMalgebras, we prove the (chain) completeness of monadic NM-logic.

# 2.Preliminaries

In this section, we summarize some definitions and results about NM-algebras, which will be used in the remainder of the paper.

Definition 2.1. [8,25] An algebraic structure $( L , \land , \lor , \odot ,  , 0 , 1 )$ of type $( 2 , 2 , 2 , 2 , 0 , 0 )$ is called an NM-algebra if it satisfies the following conditions:

（1） $( L , \wedge , \vee , 0 , 1 )$ is a bounded lattice,2） $( L , \odot , 1 )$ is a commutative monoid,3) $x \odot y \le z$ if and only if $x \leq y  z$ ，（4） $\begin{array} { l } { ( x  y ) \lor ( y  x ) = 1 , } \\ { ( x \odot y  0 ) \lor ( x \land y  x \odot y ) = 1 , } \\ { ( x  0 )  0 = x , } \end{array}$ （5）  
(6)

for any $x , y , z \in L$

It is important to remark that $\mathrm { R } _ { 0 }$ -algebras [12],which were introduced by Prof. Wang as an algebraic counterpart of the formal logic $\mathcal { L }$ in 1996,have been shown to be equivalent to NM-algebras in [4].

Definition 2.2.[5,12,30] Let $( L , \land , \lor , \lnot , 0 , 1 )$ be a bounded distributive lattice with order-reversing involution $\neg$ and a binary operation $$ . Then $( L , \land , \lor , \lnot , \to$ $, 0 , 1 )$ is called an $R _ { 0 }$ -algebra if it satisfies the following conditions:

$$
\begin{array} { r l } & { x  y = \neg y  \neg x , } \\ & { 1  x = x , } \\ & { ( y  z ) \wedge ( ( x  y )  ( x  z ) ) = y  z , } \\ & { x  ( y  z ) = y  ( x  z ) , } \\ & { x  ( y \vee z ) = ( x  y ) \vee ( x  z ) , } \\ & { ( x  y ) \vee ( ( x  y )  ( \neg x  y ) ) = 1 , } \end{array}
$$

for any $x , y , z \in L$

Due to the equivalence between $\mathrm { R } _ { 0 }$ -algebras and NM-algebras,we use the seventuple $( L , \land , \lor , \lnot , \to , 0 , 1 )$ to refer to an NM-algebra in the sequel, and by $L$ we denote the universal of an NM-algebra $( L , \land , \lor , \lnot , \to , 0 , 1 )$ . For any $x , y \in L$ ，we define $x \odot y = \lnot ( x \to \lnot y )$ and $x \oplus y = \lnot x \to y$ . It is proved that $x \oplus y = \lnot ( \lnot x \odot \lnot y )$ For any $x \in L$ and a natural number $n$ ， we define $x ^ { 0 } = 1$ and $x ^ { n } = x \odot x \cdot \cdot \cdot x$ for $n \geq 1$ ：

Proposition 2.3. [5,8, 12, 15,25,30] In any NM-algebra $( L , \land , \lor , \lnot , \lnot , 0 , 1 )$ ，the following properties hold: for all $x , y , z \in L$ ，

(1) $x \leq y$ if and only if $x  y = 1$ （2) $x \leq y  x$ ，  
(3) $\neg x = x  0$ ，  
(4) $x \leq y$ implies $y  z \leq x  z$ ，(5) $x \leq y$ implies $z  x \leq z  y$ ，  
(6) $\begin{array} { l } { ( ( x  y )  y )  y = x  y , } \\ { x \lor y = ( ( x  y )  y ) \land ( ( y  x )  x ) , } \end{array}$   
（7） （204号  
（8) （204号 $x \odot \lnot x = 0$ and $x \oplus \lnot x = 1$ ，  
(9) （204号 $x \odot y \le x \land y$ and $x \odot ( x \to y ) \leq x \land y .$   
(10) （204 $( x \odot y ) \to z = x \to ( y \to z )$   
(11) $x \leq y  ( x \odot y ) .$   
(12) $x \leq y$ implies $x \odot z \le y \odot z$   
(13) $x \to y \leq ( y \to z ) \to ( x \to z ) ,$   
(14) $( x  y ) \odot ( y  z ) \leq x  z ,$ （204号  
(15) $x ^ { n } = x ^ { 2 } , n \geq 2$ ，  
(16) $\begin{array} { l } { ( x \vee y ) ^ { n } = x ^ { n } \vee y ^ { n } , n \in N , } \\ { x  y = x  ( x \wedge y ) , } \\ { ( x  y ) ^ { n } \vee ( y  x ) ^ { n } = 1 , } \\ { ( x \wedge y )  z = ( x  z ) \vee ( y  z ) . } \end{array}$   
(17)  
(18)  
(19)

From Example 8.5.1 in [12], we know that every Boolean algebra is an NMalgebra. In the following, we give some conditions under which an NM-algebra is a Boolean algebra.

Theorem 2.4. [15] Let $( L , \land , \lor , \lnot , \lnot , 0 , 1 )$ be an NM-algebra. Then following conditions are equivalent:

(1) $L$ is a Boolean algebra, (2) $x \odot x = x$ for any $x \in L$ (3) $x \oplus x = x$ for any $x \in L$

Let $L$ be an NM-algebra. A nonempty subset $F$ of $L$ is called a filter of $L$ if it satisfies: (1) $x , y \in F$ implies $x \odot y \in F$ ； (2) $x \in F , y \in L$ and $x \leq y$ implies $y \in F$ .We denote by $F [ L ]$ be the set of all filers of $L$ .A filter $F$ of $L$ is called a proper filter if $F \neq L$ .A proper filter $F$ of $L$ is called a maximal filter if it is not contained in any proper filter of $L$ . A proper filter $F$ of $L$ is called a prime filter if for each $x , y \in F$ and $x \vee y \in F$ ， implies $x \in F$ or $y \in F$ . For a nonempty subset $X$ of $L$ ，we denote by $\langle X \rangle$ is the filter generated by $X$ . Clearly, we have $\langle X \rangle = \{ x \in L | x \geq x _ { 1 } \odot x _ { 2 } \odot \cdots \odot x _ { n }$ , for some $n$ and some $x _ { i } \in X \}$ . In particular, the principal filter generated by an element $x \in L$ is $\langle x \rangle = \{ y \in L | x ^ { n } \leq y , n \geq 1 \}$ If $F$ is a filter of $L$ and $x \in L$ ，then $\langle F \cup x \rangle = \{ y \in L | f \odot x ^ { n } \leq y$ ， for some （20 $f \in F , n \in N \rangle$ . It is obvious that the set of all filters forms a complete lattice with respect to inclusion [8,12, 33].

Let $L$ be an NM-algebra and $F$ be a filter of $L$ . Define the $c o n g r u e n c e \equiv _ { F }$ on $L$ （204号 by $x \equiv _ { F } y$ if and only if $x \to y \in F$ and $y  x \in F$ . The set of all congruence class is denote by $L / F$ ，i.e. $L / F = \{ [ x ] | x \in L \}$ ，where $[ x ] = \{ x \in L | x \equiv _ { F } y \}$ .Define □,u,一, $*$ on $L / F$ as follows: $[ x ]  [ y ] = [ x  y ]$ ， $[ x ] \sqcup [ y ] = [ x \vee y ]$ ， $[ x ] \Pi [ y ] = [ x \wedge y ]$ ， $[ x ] ^ { * } = [ \neg x ]$ . Therefore, $( L / F , \sqcap , \sqcup , \sqcap , \sqcap , * , [ 0 ] , [ 1 ] )$ is an NM-algebra which is called a quotient NM-algebra of $L$ with respect to $F ^ { \prime }$ . It is easily seen that if $F$ is a prime filter of $L$ if and only if $L / F$ is a linearly ordered NM-algebra [4,12, 15].

Definition 2.5. [31] Let $( L , \land , \lor , \lnot , \lnot , 0 , 1 )$ be an NM-algebra (1) $L$ is said to be simple if it has exactly two filters: $\{ 1 \}$ and $L$ (2) $L$ is said to be subdirectly irreducible if among the nontrivial congruence of $L$ （204号 there exists the least one.

At the end of this section, we review the known main results about representation theory of NM-algebras, which is helpful for studying a monadic analogous of representation theorem for NM-algebras

Definition 2.6. [32] An element $b$ of a lattice $L$ ， is meet irreducible if $\Lambda X = b$ （204号 implies $b \in X$ , for any finite subset $X$ of $L$

A filter $F$ of an NM-algebra $L$ is said to be prime if $F$ is a finitely meetirreducible element in the lattice $F [ L ]$ .A prime filter $F$ is said to be minimal if $F$ is a minimal element in the set of prime filters of $L$ ordered by inclusion. By Zorn's lemma, every prime flter contains a minimal prime flter [19].

Let $L$ be an NM-algebra, and $X \subseteq L$ . The set $X ^ { \perp } = \{ a \in L | a \vee x = 1$ , for each （20 $x \in X \}$ is called the co-annihilator of $X$ in $L$ . For any $a \in L$ ， we write $a ^ { \perp }$ instead of $\{ a \} ^ { \perp }$ [7].

Theorem 2.7. [12,19] Let $L$ be an NM-algebra and $P$ be a filter of $L$ . Then the following conditions are equivalent:

(1) $P$ is a minimal prime, (2) $P = \cup \{ a ^ { \perp } | a \in P \}$

Theorem 2.8.[12,19] Let $L$ be an NM-algebra. Then the following conditions are equivalent:

(1) L is representable, (2) There exists a set $S$ of prime filters such that $\cap S = \{ 1 \}$

# 3.Quantifiers on NM-algebras

In this section, we introduce universal and existential quantifiers in an NMalgebra and prove the corresponding relation between them. After a study of the basic properties of monadic NM-algebras, we show that monadic NM-algebras are the equivalent algebraic semantics of the monadic fragment of NM predicate logic. Then,we give some conditions under which a monadic NM-algebra is a monadic Boolean algebra and discuss the relation between monadic NM-algebras and some related structures, likeness modal NM-algebras and rough approximation spaces.

Definition 3.1. Let $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ be an NM-algebra. A mapping $\forall : L  L$ is called a universal quantifier on $L$ , such that the following conditions are satisfied:

$$
\begin{array} { l } { \forall ( x )  x = 1 , } \\ { \forall ( \neg x  \forall y ) = \neg ( \forall x )  \forall ( y ) , } \end{array}
$$

(U3) $\begin{array} { r l } & { \forall ( \forall ( x )  y ) = \forall ( x )  \forall ( y ) , } \\ & { \forall ( x \vee \forall ( y ) ) = \forall ( x ) \vee \forall ( y ) . } \end{array}$ (U4)

for any $x , y , z \in L$

Definition 3.2. Let $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ be an NM-algebra. A mapping $\exists : L $ （204号 $L$ is called an existential quantifier on $L$ ， such that the following conditions are satisfied:

$$
\begin{array} { r l } & { x  \exists ( x ) = 1 , } \\ & { \exists ( \neg ( \neg x  \exists ( y ) ) = \neg ( \neg ( \exists x )  \exists ( y ) ) , } \\ & { \exists ( \neg ( \exists x  y ) = \neg ( \exists ( x )  \exists ( y ) ) , } \\ & { \exists ( x \wedge \exists ( y ) ) = \exists ( x ) \wedge \exists ( y ) . } \end{array}
$$

for any $x , y , z \in L$

Now， we present some examples for quantifiers on NM-algebra.

Example 3.3. Let $( L , \land , \lor ,  , \lnot , 0 , 1 )$ be an NM-algebra. According to Proposition 2.3, one can see that $i d _ { L }$ is not only a universal quantifier but also an existential quantifier on $L$ ：

Example 3.4. Let $L ~ = ~ \{ 0 , a , b , c , d , 1 \}$ ，where $0 ~ \leq ~ a$ ， $\textit { b } \leq \textit { c }$ ， $d \ \leq \ 1$ .Define operations $\neg$ and $\longrightarrow$ as follows:

<html><body><table><tr><td>→</td><td>a</td><td>b</td><td>C</td><td>d 1</td><td></td><td></td></tr><tr><td>0</td><td>1 1</td><td>1</td><td>1</td><td>d</td><td>0</td><td>1</td></tr><tr><td>a</td><td>C 1</td><td>C</td><td>1</td><td>1 1</td><td>a</td><td>C</td></tr><tr><td>b</td><td>d d</td><td>1</td><td>1</td><td>d 1</td><td>b</td><td>d</td></tr><tr><td>C</td><td>a d</td><td>C</td><td>1</td><td>d 1</td><td>C</td><td>a</td></tr><tr><td>d</td><td>b C</td><td>b</td><td>C</td><td>1 1</td><td>d</td><td>b</td></tr><tr><td>1</td><td>0 a</td><td>b</td><td>C</td><td>d 1</td><td>1</td><td>0</td></tr></table></body></html>

Then $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ is an NM-algebra. Now, we define $\forall$ and $\exists$ as follows: $\forall ( 0 ) = \forall ( a ) = 0$ ， $\forall ( b ) = \forall ( c ) = b$ ， $\forall ( d ) = d$ ， $\forall ( 1 ) = 1$ ：， $\exists ( 0 ) = 0$ ， $\exists ( a ) = \exists ( d ) = d$ ， $\exists ( b ) = b$ ， $\exists ( c ) = \exists ( 1 ) = 1$ . One can easily check that $\exists$ and $\forall$ are existential and universal quantifiers on $L$ , respectively. However, $\exists$ is not an existential quantifier on the corresponding residuatd lattice $( L , \land , \lor ,  , \odot , 0 , 1 )$ ， since $\exists ( x \odot x ) = \exists ( x ) \odot$ （204号 $\exists ( x )$ for some $x \in L$ ， not hold, which shows that the NM-algebra with existential and universal quantifiers is not the same as that of monadic residuated lattice in [21].

Example 3.5. Let $L$ be a standard NM-algebra on [O,1] and $L _ { n } \subseteq L$ be a standard $n$ -valued NM-algebra for some $n \geq 2$ (its elements are $0 , { \frac { 1 } { n - 1 } } , \cdots , { \frac { n - 2 } { n - 1 } } , 1 )$ For any $x \in L$ ，we define $\forall ( x ) = \operatorname* { m a x } \{ y \in L _ { n } | y \leq x \}$ and $\exists ( x ) = \operatorname* { m i n } \{ y \in L _ { n } | x \leq y \}$ One can easily check that $\exists$ and $\forall$ are existential and universal quantifiers on $L$ ， respectively.

The following theorem shows the corresponding relation between universal and existential quantifiers in the case of NM-algebra. Therefore, it will be suffcient to investigate only one from this kinds of quantifiers.

Theorem 3.6.Let $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ be an NM-algebra. Then there exists a one to one correspondence between existential and universal quantifiers on $L$ . Namely, $i f \forall$ is a universal quantifier on $L$ ， then the mapping $\exists _ { \forall } : L  L$ such that for any $x \in L$ ， $\forall \exists x : = \neg ( \exists \neg x )$ is an existential quantifier on $L$ ；if $\exists$ is an existential quantifier on $L$ ， then the mapping $\forall \exists ~ \colon L  L$ such that for any $x \in L$ ， $\exists _ { \forall } : =$ $\neg ( \forall \neg x )$ is a universal quantifier on $L$ . Moreover, $\forall _ { ( \exists _ { \forall } ) } = \forall$ and $\exists _ { ( \forall \exists ) } = \exists$ ，

Proof. First, we will show if $\forall$ is a universal quantifier on $L$ and $\exists ( x ) = \exists _ { \forall } ( x )$ then $\exists$ is an existential quantifier on $L$

(E1） Applying(U1),we have $\forall ( \neg x ) \leq \neg x$ and hence $\lnot ( \forall ( \lnot x ) ) \geq \lnot \lnot ( x )$ . Therefore（20 $x \leq \exists ( x )$ ：  
(E2）Applying (U2)，we have $\forall ( x \oplus \forall ( y ) ) = \forall ( x ) \oplus \forall ( y )$ and hence $\exists ( \lnot ( \lnot x ) \to$ $\exists ( y ) ) = \exists ( x \odot \exists ( y ) ) = \exists ( x \odot \lnot ( \forall \lnot y ) ) = \exists ( \lnot x \oplus \forall ( \lnot y ) ) = \lnot \forall ( \lnot x \oplus \forall ( \lnot y ) ) = \lnot \forall ( \lnot x \oplus \forall ( \lnot y ) ) = \lnot \forall ( \lnot x \oplus \forall ( \lnot y ) ) = \lnot \lor ( \lnot x \oplus \forall ( \lnot y ) ) = \lnot \lor ( \lnot x \oplus \forall ( \lnot y ) ) = \lnot \lor ( \lnot x \oplus \forall ( \lnot y ) ) = \lnot \lor ( \lnot x \oplus \forall ( \lnot y ) )$ （204号$\lnot ( \forall ( \lnot x ) \oplus \forall ( \lnot y ) ) = \lnot ( \forall x ) \to \forall ( y ) = \exists ( x ) \odot \exists ( y ) = \lnot ( \lnot \exists ( x ) \to \exists ( y ) ) .$ Therefore $\exists ( \neg ( \neg x \to \exists ( y ) ) = \neg ( \neg \exists ( x ) \to \exists ( y ) )$ ：  
(E3) Applying(U3), we have $\forall ( \lnot ( \forall ( x ) ) \oplus y ) = \lnot \forall ( x ) \oplus \forall ( y )$ and hence $\exists ( \neg ( \exists ( x ) $ $y ) = \exists ( x \odot \lnot ( \exists ( y ) ) ) = \exists ( x \odot \forall ( \lnot y ) ) = \lnot \forall \lnot ( x \odot \forall ( \lnot y ) ) = \lnot \forall ( \lnot x \odot \lnot \forall ( \lnot y ) ) = \lnot \forall ( \lnot x \oplus \lnot \lnot \forall ( \lnot y ) ) = \lnot \forall \ l ( \lnot x \odot \lnot \forall ( \lnot y ) ) = \lnot \forall \ l ( \lnot x \odot \lnot \forall ( \lnot y ) ) = \lnot \forall \ l ( \lnot x \odot \lnot \forall ( \lnot y ) ) = \lnot \langle \ l ( \lnot x \odot \lnot \forall ( \lnot y ) ) = \ l ( \lnot x \odot \lnot \forall ( \lnot y ) ) = \ l ( \ l ( \lnot x \odot \lnot \lor \lnot y ) )$ $\lnot ( \lnot \forall ( \lnot y ) \oplus \forall ( \lnot x ) ) = \forall ( \lnot y ) \odot \lnot \forall ( \lnot x ) = \exists ( x ) \odot \lnot \exists ( y ) = \lnot ( \exists ( x ) \to \exists ( y ) ) .$ Therefore $\exists ( \lnot ( \exists ( x ) \to y ) = \lnot ( \exists ( x ) \to \exists ( y ) )$ ）  
(E4） Applying (U4),we have $\exists ( x \land \exists ( y ) ) = \neg ( \forall \neg ( x \land \exists ( y ) ) ) = \neg ( \forall ( \neg x \lor \neg \exists ( y ) ) ) =$ $\lnot ( \forall ( \lnot x ) \lor \forall ( \lnot y ) ) = \lnot \forall ( \lnot x ) \land \lnot \forall ( \lnot y ) = \exists ( x ) \land \exists ( y )$ . Therefore, $\exists ( x \land \exists ( y ) ) =$ $\exists ( x ) \land \exists ( y )$ ：

Next, we will show if $\exists$ is an existential quantifer on $L$ and $\forall ( x ) = \forall \exists ( x )$ ,then $\forall$ is a universal quantifier on $L$ ：

(U1） Applying (E1)，we have $\neg x \leq \exists ( \neg x )$ and hence $\neg \exists ( \neg x ) \ \leq \ x$ .Therefore （204号 $\forall ( x ) \leq x$ ，   
(U2) Applying (E2),we have $\exists ( x \odot \exists ( y ) ) = \exists ( x ) \odot \exists ( y )$ and hence $\forall ( \neg x  \forall ( y ) ) =$ $\forall ( x \oplus \forall ( y ) ) = \forall ( x \oplus \lnot \exists ( \lnot y ) ) = \lnot \exists ( \lnot \oplus \lnot \exists ( \lnot y ) ) = \lnot \exists ( \lnot x \odot \lnot \exists ( y ) ) =$ $\lnot ( \exists ( \lnot x ) \odot \lnot \exists ( x ) ) = \forall ( x ) \oplus \forall ( y ) = \lnot ( \forall ( x ) ) \to \forall ( y )$ .Therefore, $\forall ( \neg x $ $\forall ( y ) ) = \lnot \forall ( x )  \forall ( y )$   
(U3)Applying (E3)，we have $\exists ( x \odot \lnot \exists ( y ) ) = \exists ( x ) \odot \lnot \exists ( y )$ and hence $\forall ( \forall ( x ) $ （20 $y ) = \forall ( \lnot \forall ( x ) \oplus y ) = \forall ( \exists ( \lnot x ) \oplus y ) = \lnot \exists ( \lnot ( \exists ( \lnot x ) \oplus y ) ) = \lnot \exists ( \lnot \exists ( \lnot x ) \oplus \ l ( y ) ) = \lnot \exists ( \lnot \exists ( \lnot x ) \in \{ 0 , 1 \} )$ · $\lnot y ) = \lnot ( \exists ( \lnot y ) \odot \lnot \exists ( \lnot x ) ) = \forall ( y ) \oplus \lnot \forall ( x ) = \forall ( x ) \to \forall ( y ) .$ Therefore, $\forall ( \forall ( x )  y ) = \forall ( x )  \forall ( y )$ ：   
(U4) Applying (E4), we have $\forall ( x \lor \forall ( y ) ) = \forall ( x \lor \lnot \exists ( \lnot y ) ) = \lnot \exists ( \lnot ( x \lor \lnot \exists ( \lnot y ) ) ) =$ （204号 $\forall ( x ) \vee \forall ( y )$ . Therefore, $\forall ( x \vee \forall ( y ) ) = \forall ( x ) \vee \forall ( y )$

Moreover, one can easily check that $\forall \exists _ { \forall } ( x ) = \forall ( x )$ and $\exists _ { \forall \exists } ( x ) = \exists ( x )$ for any （20 $x \in L$ ：

Combining them, the proof is completed.

In order to establish monadic ideal and related theory, the existential quantifier instead of the universal quantifier $\forall$ were used to define monadic MV-algebra. But for NM-algebra, we would like to study the monadic filter rather than monadic ideal, using the universal quantifier as the original one is more natural and convenient. Therefore, we introduce the notion of monadic NM-algebra is an NM-algebra equipped with a universal quantifier.

Definition 3.7. Let $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ be an NM-algebra and $\forall$ be a universal quantifier on $L$ . Then the couple $( L , \forall )$ is called a monadic NM-algebra.

The axiomatisation above can be immediately translated into an equational one, so the class of monadic NM-algebras is a variety of algebras. Therefore, the notions of subalgebra and homomorphism are defined as usual.

In the following proposition we will present some useful properties of universal quantifier on a monadic NM-algebra $( L , \forall )$

Proposition 3.8. Let $( L , \forall )$ be a monadic NM-algebra. Then the following properties hold: for any $x , y , z \in L$

(1) $\forall ( 0 ) = 0$   
(2) $\forall ( 1 ) = 1$ ，  
(3) $\forall \forall ( x ) = x$ ，  
(4) $x \leq y \Rightarrow \forall ( x ) \leq \forall ( y ) .$   
(5) $\forall ( x  y ) \leq \forall ( x )  \forall ( y )$ ， especially, $\forall ( \neg x ) \leq \neg ( \forall x )$   
(6) $\forall ( x ) \leq y$ if and only if $\forall ( x ) \leq \forall ( y )$ ，  
（7) $\forall ( \forall ( x )  \forall ( y ) ) = \forall ( x )  \forall ( y )$   
（8） $\lnot ( \forall x ) = \forall \lnot ( \forall x )$   
(9) $\forall ( x \wedge y ) = \forall ( x ) \wedge \forall ( y ) .$   
10) $\forall ( x \odot y ) \ge \forall ( x ) \odot \forall ( y ) .$   
11) $\forall ( \forall x \oplus \forall y ) = \forall ( x ) \oplus \forall ( y ) ,$ （204号  
12) $\forall ( x \oplus y ) \geq \forall ( x ) \oplus \forall ( y )$ ，  
(13) $\forall ( \forall x \odot \forall y ) = \forall ( x ) \odot \forall ( y )$   
(14) $\forall L = L _ { \forall }$ ， where $L _ { \forall } = \{ x \in L | \forall x = x \}$   
'15)∀L is a subalgebra of $L$

Proof.(1） Applying(U1),we have $\forall ( 0 ) \leq 0$ . Thus $\forall ( 0 ) = 0$

(2） Applying (U3)，we have $\forall ( 1 ) = \forall ( \forall ( x )  x ) = \forall ( x )  \forall ( x ) = 1$ ：   
(3） From (U4) and (2),we deduce $\forall \forall ( x ) = \forall ( 1 \lor \forall ( x ) ) = \forall ( 1 ) \lor \forall ( x ) = 1 \lor \forall ( x ) =$ （204号 $\forall ( x )$ ：   
(4)If $x \leq y$ ,then $x  y = 1$ . It follows from (U3),(2) and Proposition 2.3(1) that （20 $1 = \forall ( 1 ) = \forall ( \forall ( x )  y ) = \forall ( x )  \forall ( y )$ . Thus, $\forall ( x ) \leq \forall ( y )$ ：   
(5） From (U1) and Proposition 2.3(4)，we get $x \to y \leq \forall ( x ) \to y$ .By (U3) and (4) we have $\forall ( x  y ) \leq \forall ( \forall ( x )  y ) = \forall ( x )  \forall ( y )$   
(6) Obviously. (7） By (U3) and (3),we deduce $\forall ( \forall ( x )  \forall ( y ) ) = \forall ( x )  \forall \forall ( y ) = \forall ( x )  \forall ( y )$ (8） Applying (U3)，we have $\forall \neg ( \forall x ) = \forall ( \forall ( x )  0 ) = \forall ( x )  \forall ( 0 ) = \neg ( \forall x ) .$ (9) From (U3) and Proposition 2.3(17),(19)，we have $( \forall ( x ) \land \forall ( y ) )  \forall ( \forall ( x ) \land$ $\forall ( y ) ) ~ = ~ ( \forall ( x ) ~  ~ \forall ( \forall ( x ) ~ \wedge ~ \forall ( y ) ) ) ~ \vee ~ ( \forall ( y ) ~  ~ \forall ( \forall ( x ) ~ \wedge ~ \forall ( y ) ) ) ~ = ~ \forall ( \forall ( x ) ~  ~ \forall ( y ) ) ~ .$ $\begin{array} { r } { ( \forall ( x ) \wedge \forall ( y ) ) \vee \forall ( \forall ( y )  ( \forall ( x ) \wedge \forall ( y ) ) = \forall ( \forall ( x )  \forall ( y ) ) \vee \forall ( \forall ( y )  \forall ( x ) ) = } \end{array}$ $( \forall ( x )  \forall ( y ) ) \lor ( \forall ( y )  \forall ( x ) ) = 1 .$ ，So from Proposition 2.3(1),(U1) and (4) we obtain $\forall ( x ) \land \forall ( y ) \leq \forall ( \forall ( x ) \land \forall ( y ) ) \leq \forall ( x \land y ) \leq \forall ( x ) \land \forall ( y )$ . Thus, $\forall ( x \wedge y ) = \forall ( x ) \wedge \forall ( y )$ ：   
(10） From $x \odot y \le x \odot y$ ，we get $y \leq x  ( x \odot y )$ . Applying (4),(5），we get （20 $\forall ( y ) \leq \forall ( x )  \forall ( x \odot y )$ . Thus, $\forall ( x ) \odot \forall ( y ) \leq \forall ( x \odot y )$ by Definition 2.1(3).   
(11) From (U2), we get $\forall ( x \oplus \forall ( y ) ) = \forall ( x ) \oplus \forall ( y )$ . By (3), we have $\forall ( \forall ( x ) \oplus \forall ( y ) ) =$ （20 $\forall \forall ( x ) \oplus \forall ( y ) = \forall ( x ) \oplus \forall ( y )$ . Thus, $\forall ( \forall ( x ) \oplus \forall ( y ) ) = \forall ( x ) \oplus \forall ( y )$   
(12) From (U1) and (11), we have $\forall ( x ) \oplus \forall ( y ) = \forall ( \forall ( x ) \oplus \forall ( y ) ) \leq \forall ( x \oplus y )$ （2   
(13)It follows from (7) and (8).   
(14) Let $y \in \forall L$ ， so there exists $x \in L$ such that $y = \forall ( x )$ . Hence $\forall ( y ) = \forall \forall ( x ) =$ （204号 $\forall ( x ) = y$ .It follows that $y \in L _ { \forall }$ .Conversely, if $y \in L _ { \forall }$ ，we have $y \in \forall L$ Therefore, $\forall L = L _ { \forall }$ ：   
(15) By (U3),(U4) and (8),(9), we have $\forall L$ is closed under the operations $\vee , \wedge ,  , \lnot$ Therefore, $\forall L$ is a subalgebra of $L$

From Theorem 3.6 we know that if $\forall$ is a universal quantifier on an NM-algebra $L$ then the corresponding existential quantifier $\exists$ is defined by $\exists x = \lnot ( \forall ( \lnot x ) )$ for all $x \in L$ . Now, we turn our attention to some properties of existential quantifier on a monadic NM-algebra $( L , \forall )$

Proposition 3.9. Let $( L , \forall )$ be a monadic NM-algebra. Then the following properties hold: for any $x , y , z \in L$ ，

（1） $\exists ( 0 ) = 0$ (2) $\exists ( 1 ) = 1$ ，(3） $\exists \exists ( x ) = \exists ( x )$ ，（4） $x \leq y \Rightarrow \exists ( x ) \leq \exists ( y )$ （5 $\exists ( \exists ( x ) \odot \exists ( y ) ) = \exists ( x ) \odot \exists ( y )$ (6) $\lnot ( \exists x ) = \exists \lnot ( \exists x )$ （7） $\lnot ( \exists x ) \leq ( \exists ( \lnot x ) )$ （8) $\exists ( x \vee y ) = \exists ( x ) \vee \exists ( y ) .$ (9) $x \leq \exists ( y ) \Leftrightarrow \exists ( x ) \leq \exists ( y ) ,$   
(10) $\forall \exists ( x ) = \exists ( x )$   
(11) $\exists \forall ( x ) = \forall ( x )$   
(12) $\forall ( x ) = x$ if and only if $\exists ( x ) = x$ ，  
(13) $\exists L = L _ { \exists }$ ， where $L _ { \exists } = \{ x \in L | \exists x = x \}$   
(14) $\exists L = \forall L$ ，  
(15) $( \exists , \forall )$ establishes a Galois connection over $( L , \leq )$

Proof. The proof is dual to that of Proposition 3.7, so we omit them.

In the following, we will show that the axioms of monadic NM-algebra is equivalent to the another system as following.

Theorem 3.10.Let $L$ be an NM-algebra, $\forall : L \longrightarrow L$ and $\exists : L \longrightarrow L$ be two mappings. The sets of $G = \{ U 1 , U 2 , U 3 , U 4 \}$ and $H = \{ W 1 , W 2 , W 3 , W 4 , W 5 \}$ are equivalent, where $W 1 - W 5$ defined as follows for any $x , y \in L$ ，

(W1) $\forall ( x )  x = 1$ ，  
(W2) $x \to \exists ( x ) = 1$ ，  
(W3) $\forall ( x  \exists ( y ) ) = \exists ( x )  \exists ( y )$   
(W4) $\forall ( \exists ( x )  y ) = \exists ( x )  \forall ( y )$   
(W5) $\forall ( x \vee \exists y ) = \forall ( x ) \vee \exists ( y ) .$ （20

Proof. $G \Rightarrow H$ : From Theorem 3.6, we have $\exists ( x ) = \lnot ( \forall ( \lnot x ) )$ for all $x \in L$

(W1）It follows from (U1).   
(W2)It follows form Theorem 3.6.   
(W3) By (U3), we have $\forall ( x  \forall ( y ) ) = \neg ( \forall ( \neg x ) )  \forall ( y ) = \exists ( x )  \forall ( y )$ ,for any （2 $x , y \in L$ ：   
(W4) From Proposition 3.8(10)，we have $\forall \exists ( x ) = \exists ( x )$ ， for any $x \in L$ .Moreover, by (U4),one can obtain that $\forall ( \exists ( x )  y ) = \forall ( \forall \exists ( x )  y ) = \forall \exists ( x )  y =$ $\exists ( x )  \forall ( y )$ ， for any $x , y \in L$ ：   
(W5) From Proposition 3.9(10)，we have $\forall \exists ( x ) = \exists ( x )$ , for any $x \in L$ . Moreover, by (U5),one can obtain that $\forall ( x \vee \exists ( y ) ) = \forall ( x \vee \forall \exists ( y ) ) = \forall ( x ) \vee \forall \exists ( y ) =$ $\forall ( x ) \lor \exists ( y )$ , for any $x , y \in L$ ：   
$H \Rightarrow G$ : First, from $W 1 , W 2 , W 3 , W 4 , W 5$ ， we have $\lnot ( \forall x ) = \exists ( \lnot x )$ ， $\forall \exists ( x ) = \exists ( x )$   
and $\exists \forall ( x ) = \forall ( x )$ ：   
(U1) It follows from (W2).   
(U2) From (W3)，we have $\forall ( \neg x \to \forall ( y ) ) = \forall ( \neg x \to \exists \forall ( y ) ) = \exists ( \neg x ) \to \exists \forall ( y ) =$ （204号 （204号 $\neg ( \forall x )  \forall ( y )$ , for any $x , y \in L$ ：   
(U3) From (W4)，we have $\forall ( \forall ( x )  y ) = \forall ( \exists \forall ( x )  y ) = \exists \forall ( x )  \forall ( y )$ 二 （20 $\forall ( x )  \forall ( y )$ , for any $x , y \in L$ ：   
(U4) From (W5), we have $\forall ( x \lor \forall ( y ) ) = \forall ( x \lor \exists \forall ( y ) ) = \forall ( x ) \lor \exists \forall ( y ) = \forall ( x ) \lor \forall ( y ) ,$ （204号 for any $x , y \in L$ ：

As one can see in [25], these axioms faithfully translate the axioms on quantifiers in NM predicate calculus and the deduction rule of generalisation. Thus, monadic NM-algebra that we defined become in a natural way the correspondent of this logic in monadic algebraic frame.

Monadic (Boolean) algebras in the sense of Halmos [24] are Boolean algebras equipped with a unary operator $\exists : L  L$ satisfying conditions (E1),(E3) and (1) in Proposition 3.9. From this point, one can check that the monadic NM-algebra essentially generalizes monadic Boolean algebra. In the following, we will give some conditions under which a monadic NM-algebra becomes a monadic Boolean algebra via the properties of universal quantifier.

Theorem 3.11. Let $( L , \forall )$ be a monadic NM-algebra. Then the following conditions are equivalent:

(1) $( L , \exists )$ is a monadic Boolean algebra,   
(2) every universal quantifier $\forall$ on L satisfies $\forall ( x \wedge y ) = \forall ( x ) \odot \forall ( y )$ for any （204 $x , y \in L$ ，   
(3) every universal quantifier $\forall$ on $L$ satisfies $\forall ( x \vee y ) = \forall ( x ) \oplus \forall ( y )$ for any （20 $x , y \in L$ ： Proof. $( 1 ) \Rightarrow ( 2 )$ Suppose that $L$ is a Boolean algebra and $\forall$ is any quantifier on $L$ . Then $L$ satisfies the property $x \odot x = x$ for all $x \in L$ ，which is equivalent to $x \odot y = x \land y$ for any $x , y \in L$ . By Proposition 3.8(10)，we have $\forall ( x \wedge y ) =$ $\forall ( x \odot y ) \ge \forall ( x ) \odot \forall ( y )$ . On the other hand, $\forall ( x \wedge y ) \leq \forall ( x ) \wedge \forall ( y ) = \forall ( x ) \odot \forall ( y )$ Thus, $\forall ( x \wedge y ) = \forall ( x ) \odot \forall ( y )$ for any $x , y \in L$ ：   
$( 2 ) \Rightarrow ( 1 )$ Suppose that every universal quantifier $\forall$ on $L$ satisfies $\forall ( x \wedge y ) =$ $\forall ( x ) \odot \forall ( y )$ for any $x , y \in L$ . Taking $\forall = i d _ { L }$ ， we have $x \odot y = x \land y$ for all $x , y \in L$ Taking $x = y$ , we get that $x \odot x = x$ for all $x \in L$ and hence $L$ is a Boolean algebra. Therefore, $( L , \exists )$ is a monadic Boolean algebra.   
$( 1 ) \Rightarrow ( 3 )$ Suppose that $L$ is a Boolean algebra and $\forall$ is any quantifier on $L$ . Then $L$ （204号 satisfies the property $x \oplus x = x$ for all $x \in L$ ,which is equivalent to $x \oplus y = x \lor y$ for any $x , y \in L$ . By Proposition 3.8(12), we have $\forall ( x \lor y ) = \forall ( x \oplus y ) \leq \forall ( x ) \oplus \forall ( y )$ .On the other hand, $\forall ( x \vee y ) \geq \forall ( x ) \vee \forall ( y ) = \forall ( x ) \oplus \forall ( y )$ . Thus, $\forall ( x \lor y ) = \forall ( x ) \oplus \forall ( y )$ for all $x , y \in L$ ：   
$( 3 ) \Rightarrow ( 1 )$ Suppose that every universal quantifier $\forall$ on $L$ satisfies $\forall ( x \vee y ) =$ $\forall ( x ) \oplus \forall ( y )$ for any $x , y \in L$ . Taking $\forall = i d _ { L }$ , we have $x \vee y = x \oplus y$ for all $x , y \in L$ Taking $x = y$ , we get that $x \oplus x = x$ for all $x \in L$ and hence $L$ is a Boolean algebra. Therefore, $( L , \exists )$ is a monadic Boolean algebra.

It is interesting to note that for linearly ordered monadic NM-algebra we have $\forall ( x \lor y ) = \forall ( x ) \lor \forall ( y )$ . So for these subvarieties the axiom (U4) can be rewritten in the form: (U4') $\forall ( x \vee y ) = \forall ( x ) \vee \forall ( y )$ . Motivated by the above consideration， we introduce a special kind of universal quantifier under the name of strong universal quantifier on an NM-algebra.

Definition 3.12. A strong universal quantifier on an NM-algebra $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ is a mapping $\forall : L  L$ satisfying (U1),(U2),(U3) and (U4'). The couple $( L , \forall )$ is called a strong monadic NM-algebra

Example 3.13. Let $L = [ 0 , 1 ]$ . For any $x , y \in L$ ， we define $x \wedge y = \operatorname* { m i n } \{ x , y \}$ $x \vee y = \operatorname* { m a x } \{ x , y \}$ ， $\neg x = 1 - x$ ,and $x  y = 1$ if $x \leq y$ ; otherwise $x \to y = \neg x \lor y$ ， then $( L , \land , \lor , \lnot , \to , 0 , 1 )$ is an NM-algebra. Now we define $\forall$ as follows:

$$
\forall x = { \left\{ \begin{array} { l l } { 1 , } & { x = 1 } \\ { 0 , } & { x \neq 1 } \end{array} \right. } .
$$

One can easily check that $\forall$ is a strong universal quantifier on $L$ . Therefore, $( L , \forall )$ is a strong monadic NM-algebra. However, the strong universal quantifier $\forall$ is not a homomorphism on $L$ ， since $\begin{array} { r } { \forall ( \frac { 1 } { 2 }  0 ) = 0 \neq 1 = \forall ( 0 )  \forall ( \frac { 1 } { 2 } ) } \end{array}$

In what follows, we will show that every strong monadic NM-algebra is always a monadic NM-algebra.

Proposition 3.14. Every strong monadic NM-algebra is a monadic NM-algebra.

Proof. Let V be a strong universal quantifier on $L$ . We prove that（U4'） implies (U4). Indeed,we have $\forall ( x \lor \forall y ) = \forall ( x ) \lor \forall \forall ( y ) = \forall ( x ) \lor \forall ( y )$ ，which is axiom (U4).Thus we obtain that (U4') implies (U4).

However, the converse of Proposition 3.14 is not true in general, that is, not all monadic NM-algebras are strong monadic NM-algebras. This is the reason why we called this kind of universal quantifier to be a strong universal quantifier.

Example 3.15. Consider the monadic NM-algebra $( L , \forall )$ in Example 3.4, one can easily check that it is a monadic NM-algebra but not a strong monadic NM-algebra since $\forall ( a \lor b ) = \forall ( d ) = d \neq b = \forall ( 0 ) \lor \forall ( b )$ ：

In what follows, we will give a relationship between monadic NM-algebras and modal NM-algebras, which is introduced by Duan and Wang [23] to prove the completeness of modal logic over logics valued on NM-algebras. Also， we show that every monadic NM-algebra can induce an abstract approximation space, which has been introduced by Cattaneo[11]，with the intention of describing imprecise, uncertain concepts that can be approximated from the bottom and the top by crisp ones.

Definition 3.16. [23] A modal NM-algebra is a structure $( L , \land , \lor , \to , \lnot , 0 , 1 , \tau )$ ， where $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ is an NM-algebra and $\tau : L  L$ is a unary operator on $L$ , called a modal operator, such that the following conditions are satisfied:

(1) (2) $\begin{array} { r l } & { \tau ( 1 ) = 1 , } \\ & { \tau ( x \vee y ) \leq \tau ( x ) \vee \tau ( y ) , } \\ & { \tau ( x  y ) \leq \tau ( x )  \tau ( y ) , } \\ & { \tau ( x ) \leq \tau \tau ( x ) , } \\ & { \tau ( x ) \leq x . } \end{array}$ (3) （204号 (4)   
(5)

for any $x , y \in L$

In what follows, we will show that a modal NM-algebra is a strong monadic NM-algebra if and only if $\forall ( \forall ( x )  \forall ( y ) ) = \forall ( x )  \forall ( y )$ for any $x , y \in L$

Theorem 3.17. Let $( L , \land , \lor , \lor , \lnot , 0 , 1 )$ be an NM-algebra and $\forall : L  L$ bea unary operator on $L$ . Then the following conditions are equivalent:

(1） $( L , \forall )$ is a strong monadic NM-algebra   
(2) $( L , \forall )$ is a modal NM-algebra with $\forall ( \forall ( x )  \forall ( y ) ) = \forall ( x )  \forall ( y )$ for any x,y∈L.

Proof. $( 1 ) \ \Rightarrow \ ( 2 )$ Conditions (M1),(M2),(M3),(M4)and (M5) are directly contained in the definition and proposition of a strong monadic NM-algebra as (U1),(U4') and Proposition 3.7(2),(3),(5). $( 2 ) \Rightarrow ( 1 )$ Conditions (U1),(U4) are directly contained in the definition of a modal NM-algebra. In order to show (U3)， from (M3),(M4) and (M5) we have that $\forall ( \forall ( x )  y ) \leq \forall \forall ( x )  \forall ( y ) = \forall ( x )  \forall ( y )$ . On the other hand, from (M5) and Proposition 2.2(6) we can write $\forall ( x ) \ \to \ \forall ( y ) \ \leq \ \forall ( x ) \ \to \ y$ ，where using $\forall ( \forall x )  \forall ( y ) ) = \forall ( x )  \forall ( y )$ we get $\forall ( x ) \ \to \ \forall ( y ) \ \leq \ \forall ( \forall ( x ) \ \to \ y )$ (U2) results from (M4),(M5) and where using $\forall ( \forall ( x )  \forall ( y ) ) = \forall ( x )  \forall ( y )$ ：

A monadic NM-algebra $( L , \forall )$ induce a rough approximation space $\mathcal { R } = ( L , L _ { \forall } , \forall , \exists )$ in which

· $L$ is the set of approximable elements, $L _ { \forall }$ is the set of exact or definable elements,   
： $\exists : L  L _ { \forall }$ is the inner approximation map,satisfying (for any $x \in L _ { \forall }$ )(for any $y \in L ) ( x \leq y$ iff $x \leq \exists ( y )$ )   
： $\forall : L  L _ { \forall }$ is the inner approximation map, satisfying (for any $x \in L _ { \forall } )$ (for any $y \in L ) ( x \leq y$ iff $\forall ( x ) \leq y$ ), and in which for any element $x$ in $L$ , its rough approximation is defined by $( \forall ( x ) , \exists ( x ) )$ ：

Proof. Suppose $x \in L _ { \forall }$ and $y \in L$ .If $x \leq y$ ，then $x = \forall ( x ) \leq \forall ( y )$ . Conversely, if $x \leq \forall ( y )$ ， then $x \le \exists ( y ) \le ( y )$

Suppose $x \in L$ and $y \in L _ { \forall }$ If $x \le y$ ，then $\exists ( x ) \leq \exists ( y ) = y$ . Conversely, if $\exists ( x ) \leq y$ ， then $x \leq \exists ( x ) \leq y$

Open Problem: Whether there exists a nontrival universal quantifier $\forall$ ensures that no two different elements have the same rough approximation?

# 4. Monadic filters in monadic NM-algebras

In this section, we introduce and investigate monadic filters in monadic NMalgebras. In particular, by using monadic filters, we prove a monadic analogous of representation theorem for NM-algebras and characterize two kinds of monadic NM-algebras, which are simple and subdirectly irreducible monadic NM-algebras.

Definition 4.1. Let $( L , \forall )$ be a monadic NM-algebra. A nonempty subset $F$ of $L$ is called a monadic filter of $( L , \forall )$ if $F$ is a filter of $L$ such that if $x \in F$ ，then $\forall ( x ) \in F$ for all $x \in L$ ：

We will denote the set of all monadic filters of $( L , \forall )$ by $M F [ L ]$

Example 4.2. Consider the monadic NM-algebra $( L , \forall )$ in Example 3.4, one can easily check that the monadic filters of $( L , \forall )$ are $\{ 1 \} , \{ 1 , d \}$ ， $\{ 1 , c , d \}$ and $L$ . However,consider the monadic NM-algebra $( L , \forall )$ in Example 3.13, one can check that $\left[ { \frac { 1 } { 2 } } , 1 \right]$ is a filter of $L$ but not a monadic filter of $( L , \forall )$ ：

Let $( L , \forall )$ be a monadic NM-algebra. For any nonempty set $X$ of $L$ ， we denote by $\langle X \rangle _ { \forall }$ the monadic filter of $( L , \forall )$ generated by $X$ ，that is, $\langle X \rangle _ { \forall }$ is the smallest monadic filter of $( L , \forall )$ containing $X$ .If $F$ is a monadic filter of $( L , \forall )$ and $x \not \in F$ ， we put $\langle F , x \rangle _ { \forall } : = \langle F \cup \{ x \} \rangle _ { \forall }$

The next theorem gives a concrete description of the monadic filter generated by a nonempty subset $X$ of an NM-algebra $L$

Theorem 4.3. Let $( L , \forall )$ be a monadic NM-algebra and $X$ be a nonempty set of $L$ . Then

Proof. The proof is easy, and we hence omit the details.

Theorem 4.4. Let $F$ ， $F _ { 1 }$ ， $F _ { 2 }$ be monadic filters of $( L , \forall )$ and $a \not \in F$ . Then

(1) $\begin{array} { r l } & { \langle a \rangle _ { \forall } = \{ x \in L | x \geq ( \forall a ) ^ { n } , n \geq 1 \} , } \\ & { \langle F \cup a \rangle _ { \forall } = \{ x \in L | x \geq f \odot ( \forall a ) ^ { n } , f \in F \} = F \vee [ \forall a ) , } \\ & { \langle F _ { 1 } \cup F _ { 2 } \rangle _ { \forall } = \{ x \in L | x \geq f _ { 1 } \odot f _ { 2 } , f _ { 1 } \in F _ { 1 } , f _ { 2 } \in F _ { 2 } \} , } \end{array}$   
(2)   
(3)   
4）f $a \leq b$ ，then $\langle b \rangle _ { \forall } \subseteq \langle a \rangle _ { \forall }$ ，   
5 （20 $\langle \forall a \rangle _ { \forall } = \langle a \rangle _ { \forall }$ ，   
(6) （204号 $\langle a \rangle _ { \forall } \vee \langle b \rangle _ { \forall } = \langle a \wedge b \rangle _ { \forall } = \langle a \odot b \rangle _ { \forall } .$   
(7）f $( L , \forall )$ is a strong monadic NM-algebra, then $\langle a \rangle _ { \forall } \cap \langle b \rangle _ { \forall } = \langle \forall a \lor \forall b \rangle _ { \forall }$

Proof. The proofs of $( 1 ) - ( 5 )$ are obvious.

(6) Since $a \odot b \le a \land b \le a , b$ ， we deduce that $\langle \boldsymbol { a } \rangle _ { \forall }$ ， $\langle b \rangle _ { \forall } \subseteq \langle a \land b \rangle _ { \forall } \subseteq \langle a \odot b \rangle _ { \forall }$ .It follows from that $\langle a \rangle _ { \forall } \vee \langle b \rangle _ { \forall } \subseteq \langle a \wedge b \rangle _ { \forall } \subseteq \langle a \odot b \rangle _ { \forall }$ . Conversely, let $a \in \langle a \odot b \rangle _ { \forall }$ Then for some natural number $n \geq 1$ ， $a \geq ( \forall ( a \odot b ) ) ^ { n } \geq ( \forall a \odot \forall b ) ^ { n } = ( \forall a ) ^ { n } \odot ( \forall b ) ^ { n }$ Hence $a \in \langle a \rangle _ { \forall } \lor \langle b \rangle _ { \forall }$ , we deduce that $\langle a \odot b \rangle _ { \forall } \subseteq \langle a \rangle _ { \forall } \lor \langle b \rangle _ { \forall }$ . Therefore $\langle a \rangle _ { \forall } \vee \langle b \rangle _ { \forall } =$ $\langle a \wedge b \rangle _ { \forall } = \langle a \odot b \rangle _ { \forall }$ ：   
(7） Since $\forall ( a ) \ \leq \forall ( a ) \ \vee \forall ( b )$ ，we deduce that $\langle \forall ( a ) \lor \forall ( b ) \rangle _ { \forall } \ \subseteq \ \langle \forall ( a ) \rangle _ { \forall } = \ \langle a \rangle _ { \forall }$ Analogously, $\langle \forall ( a ) \lor \forall ( b ) \rangle _ { \forall } \subseteq \langle \forall ( b ) \rangle _ { \forall } = \langle b \rangle _ { \forall }$ .It follows that $\langle \forall ( a ) \lor \forall ( b ) \rangle _ { \forall } \subseteq$ $\langle a \rangle _ { \forall } \cap \langle b \rangle _ { \forall }$ . Moreover, let $t \in \langle a \rangle _ { \forall } \cap \langle b \rangle _ { \forall }$ . Then for some natural number $n , m \geq 1$ ， （20 $t \ge ( \forall ( a ) ) ^ { m }$ and $t \geq ( \forall ( b ) ) ^ { n }$ .Hence $t \geq ( \forall ( a ) ) ^ { m } \vee ( \forall ( b ) ) ^ { n } \geq ( \forall ( a ) \vee \forall ( b ) ) ^ { m n } =$ （20 （204号 $( \forall ( a \lor b ) ) ^ { m n }$ , we deduce that $a \in \langle \forall ( a ) \lor \forall ( b ) \rangle _ { \forall }$ ,that is, $\langle a \rangle _ { \forall } \cap \langle b \rangle _ { \forall } \subseteq \langle \forall ( a ) \lor \forall ( b ) \rangle _ { \forall }$ Therefore, $\langle a \rangle _ { \forall } \cap \langle b \rangle _ { \forall } = \langle \forall ( a ) \lor \forall ( b ) \rangle _ { \forall }$

Theorem 4.5. Let $( L , \forall )$ be a monadic NM-algebra and $F$ be a filter of $L$ . Then the following conditions are equivalent:

(1) $F$ is a monadic filter of $( L , \forall )$ (2) $F = \langle F \cap L _ { \forall } \rangle _ { \forall }$

Proof. The proof is easy, and we hence omit the details.

Corollary 4.6. The set of monadic filters of $( L , \forall )$ is correspondence to the set of filters of $L _ { \forall }$ ：

Proof.It follows from Theorem 4.5.

Proposition 4.7. Let $( L , \forall )$ be a monadic NM-algebra, $x \in L _ { \forall }$ and $F$ be a monadic filter of $( L , \forall )$ ，then $\langle F \cup \{ x \} \rangle _ { \forall }$ is also a monadic filter of $( L , \forall )$

Proof. The proof is easy, and we hence omit the details.

Definition 4.8. Let $( L , \forall )$ be a monadic NM-algebra and $\theta$ be a congruence on $L$ Then $\theta$ is called a monadic congruence on $( L , \forall )$ if $( x , y ) \in \theta$ implies $( \forall ( x ) , \forall ( y ) ) \in$ （204号 $\theta$ , for any $x , y \in L$ ：

Theorem 4.9. For any monadic NM-algebra there exists a one to one correspondence between its monadic filters and its monadic congruences.

Proof. The proof is easy, and we hence omit the details

Let $( L , \forall )$ be a monadic NM-algebra and $F$ be a monadic filter. We define a mapping $\forall _ { F } : L / F \to L / F$ such that $\forall _ { F } ( [ x ] ) = [ \forall x ]$ , for any $x \in L$ ：

Proposition 4.10. Let $( L , \forall )$ be a monadic NM-algebra and $F$ a monadic filter of $( L , \forall )$ ，then $( L / F , \forall _ { F } )$ is a monadic NM-algebra.

Proof. The proof is easy, and we hence omit the details.

Definition 4.11. Let $( L , \forall )$ be a monadic NM-algebra. A proper monadic filter $F$ of $( L , \forall )$ is called a prime monadic filter of $( L , \forall )$ , if for all monadic fflter $F _ { 1 }$ ， $F _ { 2 }$ （20 of $( L , \forall )$ such that $F _ { 1 } \cap F _ { 2 } \subseteq F$ ，then $F _ { 1 } \subseteq F$ or $F _ { 2 } \subseteq F$ ：

Example 4.12. Consider the Example 3.4, one can easily obtain that $\{ d , 1 \}$ and $( b , c , 1 )$ are prime monadic flters of $( L , \forall )$ . However, consider the monadic NMalgebra $( L , \forall )$ in Example 3.13, one can check that $[ \textstyle { \frac { 1 } { 2 } } , 1 ]$ is a prime filter of $L$ but not a prime monadic filter of $( L , \forall )$

Theorem 4.13. Let $( L , \forall )$ be a strong monadic NM-algebra and $F$ be a proper monadic filter of $( L , \forall )$ . Then the following are equivalent:

（1） $F$ is a prime monadic filter of $( L , \forall )$ 上 (2)f $\forall ( x ) \vee \forall ( y ) \in F$ for some $x , y \in L$ ，then $x \in F$ or $y \in F$ ， (3) $( L / F , \forall _ { F } )$ is a linearly ordered monadic NM-algebra.

Proof. $( 1 ) \Rightarrow ( 2 )$ Let $\forall ( x ) \vee \forall ( y ) \in F$ for some $x , y \in L$ . Then $\langle x \rangle _ { \forall } \cap \langle y \rangle _ { \forall } =$ $\langle \forall ( x ) \vee \forall ( y ) \rangle _ { \forall } \in F$ . Since $F$ is a prime monadic filter of $( L , \forall )$ ， then $\langle x \rangle _ { \forall } \subseteq F$ or $\langle y \rangle _ { \forall } \subseteq F$ . Therefore, $x \in F$ or $y \in F$ ：   
$( 2 ) \Rightarrow ( 1 )$ Suppose that $F _ { 1 } , F _ { 2 } \in M F { \lfloor { L } \rfloor }$ such that $F _ { 1 } \cap F _ { 2 } \subseteq F$ and $F _ { 1 } \nsubseteq F$ and $F _ { 2 } \nsubseteq F$ .Then there exist $x \in F _ { 1 }$ and $y \in F _ { 2 }$ such that $x , y \notin F$ .Since （204号 $F _ { 1 } , F _ { 2 }$ is a monadic flter of $( L , \forall )$ ，then $\forall ( x ) \in F _ { 1 }$ and $\forall ( y ) \in F _ { 2 }$ .From $\forall ( x )$ ， $\forall ( y ) \leq \forall ( x ) \vee \forall ( y )$ ，we obtain that $\forall ( x ) \lor \forall ( y ) \in F _ { 1 } \cap F _ { 2 } = F$ . By (2)，we get （20 $x \in F$ or $y \in F$ ，which is a contradiction. Therefore, $F$ is a prime monadic filter of $( L , \forall )$ ：   
$( 1 )  ( 3 )$ One can easily prove that every prime monadic filter is a prime filter. Based on this, the equivalence of (2) and (3) is easily checked, and we hence omit the details.

Theorem 4.14. Let $( L , \forall )$ be a strong monadic NM-algebra and $F$ be a proper monadic filter of $( L , \forall )$ . Then the following are equivalent:

(1) $F$ is a prime monadic filter of $( L , \forall )$ ， (2)f $\exists ( x ) \lor \exists ( y ) \in F$ implies $\exists ( x ) \in F$ or $\exists ( y ) \in F$ (3) $F \cap L _ { \forall }$ is a prime filter of $L _ { \forall }$ ：

Proof. It follows from Theorems 4.5,4.13

Definition 4.15. Let $( L , \forall )$ be a monadic NM-algebra. A proper monadic filter $F$ of $( L , \forall )$ is called a maximal monadic filter if it not strictly contained in any proper monadic filter of $( L , \forall )$

Example 4.16. Consider the Example 3.4, one can easily obtain that $\{ d , 1 \}$ and $( b , c , 1 )$ are maximal monadic filters of $( L , \forall )$ . However, consider the monadic NMalgebra $( L , \forall )$ in Example 3.13, one can check that $[ \textstyle { \frac { 1 } { 2 } } , 1 ]$ is a maximal filter of $L$ （204号 but not a maximal monadic filter of $( L , \forall )$ ：

Theorem 4.17. Let $F$ be a proper monadic filter of $( L , \forall )$ . Then the the following conditions are equivalent:

(1) $F$ is a maximal monadic filter of $( L , \forall )$ (2) for any $x \in L$ ， $\forall x \in F$ or $\neg ( \forall x ) \in F$ (3) for any $x \in L$ ， $\exists x \in F$ or $\lnot ( \exists x ) \in F$

Proof. $( 1 ) \Rightarrow ( 2 )$ Let $F$ be a maximal monadic filter and there exists $x \in L$ such that $\forall ( x ) \notin F$ and $\lnot ( \forall x ) \notin F$ . Consider the filter $\langle \forall ( x ) \cup F \rangle _ { \forall }$ As $\lnot ( \forall x ) \notin F$ ， （204号 $\langle \forall ( x ) \cup F \rangle _ { \forall }$ is proper. Besides，from Proposition 4.7 it follows that $\langle F \cup \{ x \} \rangle _ { \forall }$ is also a monadic flter of $( L , \forall )$ and,according to our assumption, $F$ is strictly contained in $\langle \forall ( x ) \cup F \rangle _ { \forall }$ ，which leads to a contradiction.

$( 2 ) \Rightarrow ( 1 )$ Suppose for any $x \in L \ \forall ( x ) \in L$ or $\lnot ( \forall x ) \in L$ and,in contrary to (1)， $F$ is not a maximal monadic filter. Then there exists a proper monadic filter $D$ strongly containing $F$ . But then there exists $x \in D$ such that $x \not \in F$ . Hence, $\forall ( x ) \notin F$ and, according to our assumption, $\neg ( \forall x ) \in F$ . Therefore, $\neg ( \forall x ) \in D$ .On the other hand, as $x \in D$ and $D$ is a monadic filter, $\forall x \in D$ . But this contradicts the fact that $D$ is a proper filter.

The equivalence of (2) and (3) is easily checked.

For proving the subdirect representation theorem of strong monadic NM-algebras, we will need the following theorem.

Theorem 4.18. Let $( L , \forall )$ be a strong monadic NM-algebra, $F$ be a monadic filter of $( L , \forall )$ and $a \not \in F$ . Then there exists a prime monadic filter $P$ of $( L , \forall )$ such that $F \subseteq P$ and $a \not \in P$ ：

Proof. Denote $F _ { a } = \{ F ^ { \prime } | F ^ { \prime }$ is a proper monadic filter of $( L , \forall )$ such that $F \subseteq F ^ { \prime }$ ， $a \notin F ^ { \prime } \}$ . Then $F _ { a } \neq \emptyset$ since $F$ is a monadic filter not containing $a$ and $F _ { a }$ isa partially set under inclusion relation. Suppose that $\{ F _ { i } | i \in I \}$ is a chain in $F _ { a }$ ， then $\cup \{ F _ { i } | i \in I \}$ is a monadic filter of $( L , \forall )$ and it is the upper bounded of this chain. By Zorn's Lemma, there exists a maximal element $P$ in $F _ { a }$ . Now, we shall prove that $P$ is the desire prime monadic flter of ours. Since $P \in F _ { a }$ ，then $P$ isa proper monadic filter and $a \not \in P$ ：

Let $x \vee y \in P$ for some $x , y \in L$ .Suppose that $x \notin P$ and $y \notin P$ .Since $P$ is strictly contained in $\langle P , x \rangle _ { \forall }$ and $\langle P , y \rangle _ { \forall }$ and by the maximality of $P$ ，we deduce that $\langle P , x \rangle _ { \forall } \notin F _ { a }$ and $\langle P , y \rangle _ { \forall } \notin F _ { a }$ . Then $a \in \langle P , x \rangle _ { \forall } = P \lor [ \forall ( x ) )$ and （204号 $a \in \langle P , y \rangle _ { \forall } = P \lor \lbrack \forall ( y ) )$ . It follows from strong property of monadic NM-algebra, we have $a \in ( P \lor [ \forall ( x ) ) ] \land ( P \lor [ \forall ( y ) ) ) = P \lor ( [ \forall ( x ) ) \land [ \forall ( y ) ) ) = P \lor [ \forall ( x ) \lor \forall ( y ) ) =$ （20 $P \vee [ \forall ( x \vee y ) ) \in P$ ，which implies $a \in P$ , a contradiction. Therefore, $P$ is a prime monadic filter such that $F \subseteq P$ and $a \not \in P$ ：

Now, we will prove that every strong monadic NM-algebra is a subdirect product of linearly ordered monadic NM-algebras.

Theorem 4.19. Each strong monadic NM-algebra is a subalgebra of the direct product of a system of linearly ordered monadic NM-algebras.

Proof. The proof of this theorem is as usual and the only critical point is the above Theorem 4.18.

In the following, we will show that strong monadic NM-algebra is representable if and only if the correspondence NM-algebra is representable.

Theorem 4.20.Let $( L , \forall )$ be an arbitrarily strong monadic NM-algebra. Then the following condition are equivalent:

(1） $L$ is representable, （2） $( L , \forall )$ is a subdirect product of linearly ordered monadic NM-algebras

Proof. $( 1 ) \ \Rightarrow \ ( 2 )$ Suppose that the NM-algebra $L$ is representable. Then by Theorem 2.8, there exists a system $S$ of prime filter of $L$ such that $\cap S = \{ 1 \}$ Since every prime filter of $L$ contains a minimal prime filter,we get that in our case the intersection of all minimal prime filter is equal to $\{ 1 \}$ . Moreover, we will show that every minimal prime filter in $( L , \forall )$ . Let $P$ be a minimal prime filter of $L$ . Then by Theorem 2.7, $P = \cup \{ a ^ { \perp } | a \in P \}$ .If $x \in P$ ,then there is $a \not \in P$ such that $x \vee a = 1$ ，hence $1 = \forall ( x \vee a ) = \forall ( x ) \vee \forall ( a )$ . Since $a \not \in P$ ，we get $\forall ( a ) \notin P$ 5 therefore $\forall ( x ) \in P$ ，that means that $P$ is a monadic filter in $( L , \forall )$ . Therefore, $( L , \forall )$ is a subdirect product of linearly ordered monadic NM-algebras. $( 2 ) \Rightarrow ( 1 )$ Suppose that $( L , \forall )$ is a subdirect product of linearly ordered monadic NM-algebras. Taking $\forall = i d _ { L }$ we have $L$ is a subdirect product of linearly ordered monadic NM-algebras, i.e. $L$ is representable.

Now, we introduce two kinds of monadic NM-algebras and give some characterizations of them.

Definition 4.21. A monadic NM-algebra $( L , \forall )$ is said to be simple if it has exctly two monadic filters: $\{ 1 \}$ and $L$

Example 4.22. Consider the monadic NM-algebra $( L , \forall )$ in Example 3.13，one can easily check that it is a simple monadic NM-algebra.

The following theorem gives a characterization of simple monadic NM-algebras.

Theorem 4.23. $( L , \forall )$ be a monadic NM-algebra. Then the following conditions are equivalent:

(1） $( L , \forall )$ is simple,   
(2) $\forall L$ is simple,   
(3) $L _ { \forall } = \{ 0 , 1 \}$ ，   
(4) [1) is the only proper monadic filter in $( L , \forall )$ Proof. $( 1 ) \Rightarrow ( 2 )$ Let $F$ be a flter of $\forall L$ and $F \neq \{ 1 \}$ . We will prove that $F = \forall L$ Consider $F _ { f } = \{ z \in L | z \geq f$ for a certain $f \in F \}$ .If $x , y \in F _ { f }$ ， then there exist $f _ { 1 } , f _ { 2 } \in F$ such that $x \ge f _ { 1 } , y \ge f _ { 2 }$ ，s0 $x \odot y \ge f _ { 1 } \odot f _ { 2 } \in F$ ，hence $x \odot y \in F _ { f }$ ： If $x \in F _ { f }$ and $x \le y$ ，then $y \in F _ { f }$ .Moreover,if $\boldsymbol { x } \in F _ { f }$ ，then $x \geq f , f \in F$ ，s0 （20 $\forall x \geq \forall ( f ) = f$ (since $f \in \forall L$ ). Hence $\forall ( x ) \in F _ { f }$ . Therefore $F _ { f }$ is a monadic filter of $\forall L$ . Since $( L , \forall )$ is simple,and $F _ { f } \neq \{ 1 \}$ (since ${ \boldsymbol { F } } \subseteq { \boldsymbol { F } } _ { f }$ ),it follows that $F _ { f } = L$ ， so $0 \in F _ { f }$ ，hence $0 \in F$ , that is, $F = \forall L$ ：   
$( 2 ) \Rightarrow ( 1 )$ Let $F$ be a monadic filter of $( L , \forall )$ . Then $F \cap \forall L$ is a filter of $\forall L$ , and so $F \cap \forall L = \{ 1 \}$ or $F \cap \forall L = \forall L$ . If $F \cap \forall L = \forall L$ , then $\forall L \subseteq F$ and, since $0 \in \forall L$ ，we deduce that $F = L$ .If $F \cap \forall L = \{ 1 \}$ and $x \in F$ ，then $\forall ( x ) \in F \cap \forall L$ ，S0 $\forall ( x ) = 1$ ， that is, $x = 1$ (since $\operatorname { K e r } ( \forall ) = \{ 1 \}$ )，and so $F = \{ 1 \}$ . Therefore, $( L , \forall )$ is simple. $( 2 ) \Leftrightarrow ( 3 )$ The equivalence of (2） and (3) is widely known.   
$( 1 ) \Leftrightarrow ( 4 )$ The equivalence of (1） and (4) follows from Definition 4.21.

Theorem 4.23 brings a method of how to check a monadic NM-algebra is simple. As an application of Theorem 4.23, one can easily check that the monadic NMalgebra in Example 4.22 is simple since $L _ { \forall } = \{ 0 , 1 \}$ 业

Definition 4.24. A monadic NM-algebra $( L , \forall )$ is said to be subdirectly irreducible if it has the least nontrivial monadic congruence.

Let $( L , \forall )$ be a subdirectly irreducible monadic NM-algebra. Then by Theorem 4.9,there exists a monadic filter $F$ of $( L , \forall )$ such that $\theta _ { F } = F$ ，that meanS， $F$ is the least monadic filter of $( L , \forall )$ such that $F ~ \neq ~ \{ 1 \}$ .Thus，we can conclude that a monadic NM-algebra $( L , \forall )$ is said to be subdirectly irreducible if among the nontrivial monadic filters of $( L , \forall )$ there exists the least one,i.e., $\cap \{ F \in M F ( L ) | F \neq \{ 1 \} \} \neq \{ 1 \}$

Example 4.25. Consider the Example 3.4, one can easily check that the monadic NM-algebra $( L , \forall )$ is a subdirectly irreducible. It is known that every subdirectly irreducible NM-algebra is a chain. However, the subdirectly irreducible monadic NM-algebra in Example 3.4 is not a chain any more.

Nevertheless a subdirectly irreducible monadic NM-algebra $( L , \forall )$ is not necessarily linearly ordered, while every subdirectly irreducible strong monadic NMalgebra is always linearly ordered. For proving this important result, we need the following several propositions and theorems.

Proposition 4.26. Let $( L , \forall )$ be a subdirectly irreducible monadic NM-algebra and $F _ { 1 }$ ， $F _ { 2 } \in M F ( L )$ .If $F _ { 1 } \cap F _ { 2 } = \{ 1 \}$ ，then $F _ { 1 } = \{ 1 \}$ or $F _ { 2 } = \{ 1 \}$

Proof. Suppose $F _ { 1 } \neq \{ 1 \}$ and $F _ { 2 } \neq \{ 1 \}$ ,i.e., $F _ { 1 }$ ， ${ \cal F } _ { 2 } \in \cap \{ F \in M F ( L ) | F \neq \{ 1 \} \} \neq$ $\{ 1 \}$ ，then $\neg \{ F \in M F ( L ) | F \neq \{ 1 \} \} \neq \{ 1 \} \subseteq F _ { 1 } \cap F _ { 2 }$ By $F _ { 1 } \cap F _ { 2 } = \{ 1 \}$ ，we can get $\cap \{ F \in M F ( L ) | F \neq \{ 1 \} \} = \{ 1 \}$ ， which contradicts to the fact that $( L , \forall )$ isa subdirectly irreducible monadic NM-algebra. Hence, $F _ { 1 } = \{ 1 \}$ or $F _ { 2 } = \{ 1 \}$ （204号

Theorem 4.27.Let $( L , \forall )$ be a monadic NM-algebra. The the following conditions are equivalent:

(1） $( L , \forall )$ is a subdirectly irreducible monadic NM-algebra, (2) there exists an element $a \in L$ ， $a < 1$ ， such that for any $x \in L$ ， $x < 1$ ， $a \in \langle x \rangle _ { \forall }$

Proof. $( 1 ) \Rightarrow ( 2 )$ Suppose that $( L , \forall )$ is a subdirectly irreducible monadic NMalgebra, i.e., $\cap \{ F \in M F ( L ) | F \neq \{ 1 \} \} \neq \{ 1 \}$ ，then $\cap \{ \langle x \rangle _ { \forall } | x < 1 \} \neq \{ 1 \}$ .Take （20 $a \in \cap \{ \langle x \rangle _ { \forall } | x < 1 \}$ satisfying $a \neq 1$ ，then for any $x \in L$ ， $x \neq 1 , a \in \langle x \rangle _ { \forall }$ ，by Theorem 4.4, there exists $m \in N$ ， such that $a \geq ( \forall ( x ) ) ^ { m }$ . Clearly, $a$ is the element that we need.

$( 2 ) \Rightarrow ( 1 )$ Conversely, we need to prove that for any $F \in M F ( L )$ ，if $F \neq \{ 1 \}$ then $a \in F$ .In fact，by $F \neq \{ 1 \}$ ，it follows that there exists $x \in F$ ， $x \ : < \ : 1$ ， and then，by the known condition, $a \in \langle x \rangle _ { \forall }$ ， furthermore, $a \in F$ ，SO $a \in \cap \{ F \in$ （20 $M F ( L ) | F \neq \{ 1 \} \}$ .Hence, $\cap \{ F \in M F ( L ) | F \neq \{ 1 \} \} \neq \{ 1 \}$ ，i.e., $( L , \forall )$ isa subdirectly irreducible monadic NM-algebra.

We recall that a non-unit element $a \in L$ is said to be a coatom of $L$ if $a \leq b$ ， then $b \in \{ a , 1 \}$ ,i.e. $b = a$ or $b = 1$ (see [32]). In the following proposition, we will show that every subdirectly irreducible strong monadic NM-algebra has at most one coatom.

Proposition 4.28. Let $( L , \forall )$ be a subdirectly irreducible strong monadic NMalgebra. For any $x$ $y \in L$ ，if $x \vee y = 1$ ，then $x = 1$ or $y = 1$ ：

Proof. For any $x , y \in L$ ,if $x \vee y = 1$ , then by Theorem 4.4, we have $\langle x \rangle _ { \forall } \cap \langle y \rangle _ { \forall } =$ $\langle \forall ( x ) \lor \forall ( y ) \rangle _ { \forall } = \langle \forall ( x \lor y ) \rangle _ { \forall } = \langle 1 \rangle _ { \forall } = \{ 1 \}$ . By Proposition 4.26, we have $\langle x \rangle _ { \forall } = \{ 1 \}$ or $\langle y \rangle _ { \forall } = \{ 1 \}$ ，hence $x = 1$ or $y = 1$ ：

The following theorem shows that the subdirectly irreducible strong NM-algebra $( L , \forall )$ is linearly ordered, that is to say， the truth value of all propositions in monadic NM-logic are comparable, this is the key importance from the logical point of view.

Theorem 4.29. Let $( L , \forall )$ be a strong monadic NM-algebra. Then the following conditions are equivalent:

（1） $( L , \forall )$ is a subdirectly irreducible strong monadic NM-algebra, （2） $( L , \forall )$ is a chain.

Proof. $( 1 ) \Rightarrow ( 2 )$ Suppose that $( L , \forall )$ is a subdirectly irreducible strong monadic NM-algebra. Applying Definition 2.1，we have $( x \to y ) \lor ( y \to x ) = 1$ for any （204号 $x , y \in L$ , then by Proposition 4.28, we have $x  y = 1$ or $y  x = 1$ ,i.e., $x \leq y$ or （20 $y \leq x$ ，SO $( L , \forall )$ is a chain.   
$( 2 ) \ \Rightarrow \ ( 1 )$ Conversely， since $( L , \forall )$ is a chain and nontrivial, then there exists a unique dual atom，denoted by $a$ .Suppose $F$ is any monadic filter of $( L , \forall )$ satisfying $F \neq \{ 1 \}$ ，then $a \in F$ . Since $F$ is chosen arbitrarily from $M F ( L )$ ，then （20 $a \in \cap \{ F \in M F ( L ) | F \neq \{ 1 \} \}$ . Hence $\cap \{ F \in M F ( L ) | F \neq \{ 1 \} \} \neq \{ 1 \}$ ，i.e., $( L , \forall )$ （204号 is a subdirectly irreducible strong monadic NM-algebra.

From Example 4.25, we obtain that the subdirectly irreducible monadic NMalgebra is not necessary linearly ordered, while $\forall L$ is always linearly ordered.

Proposition 4.30. Let $( L , \forall )$ be a monadic NM-algebra. If $( L , \forall )$ is a subdirectly irreducible monadic NM-algebra, then $\forall ( L )$ is linearly ordered.

Proof. Let $F$ be the smallest non-trivial monadic filter of $( L , \forall )$ and let $x \in$ $F - \{ 1 \}$ . Suppose by contradiction that $\forall L$ is not linearly ordered,and let $\forall ( a )$ ， $\forall ( b ) \in \forall L$ such that $\forall ( a ) \notin \forall ( b )$ and $\forall ( b ) \notin \forall ( a )$ . Then the filters $\langle \forall ( a )  \forall ( b ) \rangle _ { \forall }$ and $\langle \forall ( b ) \ \to \ \forall ( a ) \rangle _ { \forall }$ generated by $\forall ( a ) \  \ \forall ( b )$ and $\forall ( b ) \  \ \forall ( a )$ respectively, are non-trivial. Hence both contain $F$ ，in particular $x \in \langle \forall ( a ) \ \to \forall ( b ) \rangle _ { \forall }$ and （204号 $x \in \langle \forall ( b ) \to \forall ( a ) \rangle _ { \forall }$ . Since $\forall ( a )  \forall ( b ) \in \forall L$ , by Theorem 4.4 there is a $n$ such that $x \geq ( \forall ( \forall ( a )  \forall ( b ) ) ) ^ { n } \geq ( \forall ( a )  \forall ( b ) ) ^ { n }$ and $x \geq ( \forall ( \forall ( b )  \forall ( a ) ) ) ^ { n } \geq ( \forall ( b ) $ $\forall ( a ) ) ^ { n }$ . Therefore, $x \geq ( \forall ( a )  \forall ( b ) ) ^ { n } \lor ( \forall ( b )  \forall ( a ) ) ^ { n } = 1$ by Proposition 2.2(18). Hence $x = 1$ which is a contradiction.

In the following theorem,we characterize the subdirectly irrsducible monadic NM-algebra in terms of the fixed point set of universal quantifier in a NM-algebra.

Theorem 4.31. Let $( L , \forall )$ be a monadic NM-algebra. Then the following condition are equivalent:

(1） $( L , \forall )$ is a subdirectly irrsducible monadic NM-algebra, (2) $L _ { \forall }$ is a subdirectly irreducible subalgebra of $L$

Proof. $( 1 ) \Rightarrow ( 2 )$ Let $( L , \forall )$ be a subdirectly irrsducible monadic NM-algebra, then $M F [ L ] - \{ 1 \}$ has a minimal element $F$ . By Proposition 3.7, it is clear that $L _ { \forall }$ is a subalgebra of $L$ . Now, we will show that $F \cap L _ { \forall }$ is the minimal monadic filter of $L _ { \forall }$ such that $F \cap L _ { \forall } \neq \{ 1 \}$ .First,if $F \cap L _ { \forall } = \{ 1 \}$ ， since $\forall F \subseteq F \cap L _ { \forall }$ and hence $\forall ( x ) = 1$ for any $x \in F$ . Thus $F \subseteq K e r ( \forall ) = \{ 1 \}$ and $F = \{ 1 \}$ , which is a contradiction. That means $F \cap L _ { \forall } \neq \{ 1 \}$ . Next, we will show that $F \cap L _ { \forall }$ is the minimal monadic filter of $( L , \forall )$ . Suppose that $G$ is a filter of $L _ { \forall }$ and hence $\langle G \rangle _ { \forall }$ is the monadic filter of $( L , \forall )$ generated by $G$ . Clearly $\langle G \rangle _ { \forall } \cap L _ { \forall } = G$ . By minimality of $F$ ， $F \subseteq \langle G \rangle _ { \forall }$ and hence $F \cap L _ { \forall } \subseteq \langle G \rangle _ { \forall } \cap L _ { \forall } = G$ .Therefore $F \cap L _ { \forall }$ is the minimal filter of $L _ { \forall }$ such that $F \cap L _ { \forall } \neq \{ 1 \}$ . Then $L _ { \forall }$ is a subdirectly irreducible subalgebra of $L$ ：

$( 2 ) \ \Rightarrow \ ( 1 )$ Let $L _ { \forall }$ isa subdirectly irreducible subalgebra of $L$ .Then there is a minimal filter $F$ of $L _ { \forall }$ such that $F \neq \{ 1 \}$ .From Theorem 4.5，we get that $\langle F \cap L _ { \forall } \rangle _ { \forall }$ is a monadic filter of $( L , \forall )$ . Further, we will show that $\langle F \cap L _ { \forall } \rangle _ { \forall }$ isa minimal monadic filter of $( L , \forall )$ . In fact if $G$ is another non-trivial monadic filter of $( L , \forall )$ ，then $G \cap L _ { \forall } \supseteq F \cap L _ { \forall }$ . Then $G$ contains the monadic filter generated by $F$ , that is, $\langle F \cap L _ { \forall } \rangle _ { \forall } \subseteq \langle G \cap L _ { \forall } \rangle _ { \forall }$ ,i.e., $\langle F \cap L _ { \forall } \rangle _ { \forall }$ is minimal. Thus, $( L , \forall )$ isa subdirectly irreducible monadic NM-algebra.

At the end of this section, we will show another extension to monadic NMalgebras of a representation theorem.

Proposition 4.32. Let $( L , \forall )$ be a strong monadic NM-algebra and $F$ be a monadic filter of $( L , \forall )$ . Then the following properties hold: for any $x , y , z \in L$ ，

$$
F = \langle F \cup \{ x  y \} \rangle _ { \forall } \cap \langle F \cup \{ y  x \} \rangle _ { \forall }
$$

Proof. The forward inclusion is straightforward. Now assume $z$ is an element of both $\langle F \cup \{ x \to y \} \rangle _ { \forall }$ and $\langle F \cup \{ y \to x \} \rangle _ { \forall }$ . Then, there are $f _ { 1 } , f _ { 2 } \in F$ ， $n _ { 1 } , n _ { 2 } \in N$ （20 such that $f _ { 1 } \odot ( \forall ( x  y ) ) ^ { n _ { 1 } } \leq z$ and $f _ { 2 } \odot ( \forall ( y  x ) ) ^ { n _ { 2 } } \le z$ . If we let $f = f _ { 1 } \odot f _ { 2 }$ （204号 and $n = \operatorname* { m a x } \{ n _ { 1 } , n _ { 2 } \}$ , it follows that $f \odot ( \forall ( x  y ) ) ^ { n } \leq z$ and $f \odot ( \forall ( y  x ) ) ^ { n } \leq z$ ： Using the residuation condition, $( \forall ( x  y ) ) ^ { n } \leq f  z$ and $( \forall ( y  x ) ) ^ { n } \leq f  z$ Thus we get $( \forall ( x  y ) ) ^ { n } \lor ( \forall ( y  x ) ) ^ { n } \leq f  z$ .But $( \forall ( x  y ) ) ^ { n } \lor ( \forall ( y $ $x ) ) ^ { n } = ( \forall ( ( x  y ) \lor ( y  x ) ) ) ^ { n } = \forall 1 = 1$ S0 $f \leq z$ and $z \in F$ ：

Proposition 4.33. Let $( L , \forall )$ be a strong monadic NM-algebra such that $\forall ( L )$ is totally ordered. Given $a \in L$ ， $a \neq 1$ ， there exists a prime monadic filter $P$ of $( L , \forall )$ such that $a \vee \forall ( r ) \notin P$ for any $r \neq 1$

Proof. Consider $C = \{ a \vee \forall ( r ) | r \neq 1 \}$ .Note that $1 \not \in { \cal C }$ ，since $a \vee \forall ( r ) = 1$ （204号 implies that $1 = \forall ( a \lor \forall ( r ) ) = \forall ( a ) \lor \forall ( r )$ and this,in turn，would imply that $a = 1$ or $r ~ = ~ 1$ ．Let $\mathcal { F }$ be the family of monadic filters $F$ in $( L , \forall )$ such that （20 $F \cap C = \emptyset$ . The above paragraph shows that $1 \in \mathcal { F }$ ，so that $\mathcal { F }$ is nonempty. In addition, it is straightforward to verify that any chain in $\mathcal { F }$ has an upper bound in $\mathcal { F }$ . Hence, by Zorns Lemma, there exists a maximal filter $P$ in $\mathcal { F }$ .We claim that $P$ is prime monadic filter. Indeed, let $x , y \in L$ and note that $P = \langle P \cup \{ x $ $y \} \rangle \neg \langle P \cup \{ y  x \} \rangle \forall$ . If we assume that neither $\langle P \cup \{ x \to y \} \rangle _ { \forall }$ nor $\langle P \cup \{ y \to x \} \rangle _ { \forall }$ belongs to $\mathcal { F }$ ，then there are $r _ { 1 } , r _ { 2 } \neq 1$ such that $a \vee \forall ( r _ { 1 } ) \in \langle P \cup \{ x  y \} \rangle _ { \forall }$ and $a \vee \forall ( r _ { 2 } ) \in \langle P \cup \{ y  x \} \rangle _ { \forall }$ .Since $\forall ( r _ { 1 } )$ and $\forall ( r _ { 2 } )$ are comparable,it follows that one of them belongs to both filters. Hence one of them belongs to $P$ ，a contradiction. This shows that either $\langle P \cup \{ x \to y \} \rangle _ { \forall } \in { \mathcal { F } }$ or $\langle P \cup \{ y \to x \} \rangle _ { \forall } \in \mathcal { F }$ Assume the first option is true. By the maximality of $P$ ， $P = \langle P \cup \{ x  y \} \rangle _ { \forall }$ s0 $x \to y \in P$ . Analogously, if $P = \langle P \cup \{ y  x \} \rangle _ { \forall }$ ，s0 $y  x \in P$ ：

Theorem 4.34.Let $( L , \forall )$ be a strong monadic NM-algebra. Then there exists a subdirect representation of the underlying NM-algebra $\begin{array} { r } { L \leq \prod _ { i \in I } L _ { i } } \end{array}$ ， where each $L _ { i }$ （204号 is a totally ordered NM-algebra and $\forall L$ is embedded in $L _ { i }$ via the corresponding projection map.

Proof. For each $a \in L$ ， $a \neq 1$ ，let $P _ { a }$ be one of the prime filters provided by the previous proposition. Clearly $\cap _ { a \neq 1 } P _ { a } = \{ 1 \}$ and we obtain a natural embedding （204号 $\begin{array} { r } { L  \prod _ { a \neq 1 } L / P _ { a } } \end{array}$ . To close the proof we need only show that the natural map $L  L / P _ { a }$ is injective on $\forall L$ . Indeed， suppose there were $r _ { 1 } , r _ { 2 } \in L$ such that $\forall ( r _ { 1 } ) \leq \forall ( r _ { 2 } )$ and $\forall ( r _ { 1 } ) / P _ { a } = \forall ( r _ { 2 } ) / P _ { a }$ . We have that $\forall ( r _ { 2 } )  \forall ( r _ { 1 } ) = \forall ( \forall ( r _ { 2 } ) $ $\forall ( r _ { 1 } ) )$ and $\forall ( r _ { 2 } )  \forall ( r _ { 1 } ) \neq 1$ . Hence,we know that $a \vee ( \forall ( r _ { 2 } )  \forall ( r _ { 1 } ) ) \notin P _ { a } ,$ which is a contradiction.

# 5.Monadic NM-logic

In this section, we translate the defining properties of monadic NM-algebras into logical axioms, and show that the resulting logic, i.e., monadic NM-logic (MNL, for short) is sounded and complete with respect to the variety of monadic NM-algebras.

The language of MNL consists of countably many proposition variables $( p _ { 1 } , p _ { 2 } , \cdots )$ the constants $0$ and $1$ ， the unary logic connectives $\neg , \forall$ ， the binary logic connectives $\longrightarrow$ ，V, $\wedge$ $\&$ and finally the auxiliary symbols $" ( " \mathrm { a n d " } ) "$ . Formulas are defined inductively: proposition variables, $0$ and $1$ are formulas; if $\phi$ and $\psi$ are formulas, then so are $( \phi \lor \psi )$ ， $( \phi  \psi )$ ， $\neg \phi$ ， $\forall \boldsymbol \phi$ . one useful shorthand notations: $1$ for $0 $ $0$ ， $\neg \phi$ for $\phi  0$ and $\phi \equiv \psi$ for $( \phi \to \psi ) \land ( \psi \to \phi )$ (where $( \phi \wedge \psi ) = \neg ( \neg \phi \vee \neg \psi ) )$ （20 for formulas $\phi$ and $\psi$ ：

Adapting for the propositional case the axiomatization of monadic NM-algebras given by Definition 3.6, we can define monadic NM propositional calculus MNL as a logic which contains NM-logic, the formulas as the axioms schemes: (MTL1) $( \phi \to \psi ) \to ( ( \psi \to \chi ) \to ( \phi \to \chi ) )$ ）， (MTL2) $( \phi \& \psi )  \phi$ ，

(MTL3) $( \phi \& \psi )  ( \psi \& \phi )$   
(MTL4) $( \phi \land \psi )  \phi$ ，  
(MTL5) $( \phi \land \psi ) \to ( \psi \land \phi )$ ，  
(MTL6) $\ ^ { \prime } \phi \& ( \phi \to \psi ) \to ( \phi \land \psi )$   
(MTL7a) $\begin{array} { r } { \langle \phi \to ( \psi \to \chi ) \rangle \to ( ( \phi \& \psi ) \to \chi ) } \end{array}$   
(MTL7b) $( ( \phi \& \psi )  \chi )  ( \phi  ( \psi  \chi ) )$ ，  
(MTL8) $( ( \phi \to \psi ) \to \chi ) \to ( ( ( \psi \to \phi ) \to \chi ) \to \chi )$ ，  
(MTL9) $0 \to \phi$ ，  
(DN) $\neg \neg \phi \to \phi$ ，  
(WNM) $\lnot ( \phi \& \psi ) \lor ( ( \phi \land \psi )  ( \phi \& \psi ) ) .$   
(U1) $\forall \phi  \phi$ ，  
(U2) $\forall ( \neg \phi  \psi ) \equiv \neg ( \forall \phi )  \forall \psi$   
(U3) $\forall ( \forall \phi  \psi ) \equiv \forall \phi  \forall \psi$ 5  
(U4) $\forall ( \phi \lor \forall \psi ) \equiv \forall \phi \lor \forall \psi$ ：  
The deduction rules are modus ponens (MP, from $\phi$ and $\phi  \psi$ infer $\psi$ ), General-  
ization(G,from $\phi$ infer $\forall \boldsymbol \phi$ ）

As well know, monadic Boolean algebras serve as algebraic models of the onevariable fragment of the classical predicate calculus CPC, while monadic Heyting algebras serve the same purpose for the one-variable fragment of intuitionistic predicate calculus IPC, where $S 5$ in the case of CPC and MIPC in the case of IPC. For monadic NM-algebras, which serve some purpose for the one-variable fragment of NM predicate calculus NMPC, one can check that MNL in the case of NMPC and $S 5$ in the case of CPC,MIPC in the case of IPC.In fact, MNL stands for $S 5 ( \mathbf { N M } )$ ， which contains two modal connectives $\sqsubseteq$ and $\diamondsuit$ ：（ $\forall$ stands to $\sqsubseteq$ just as $\exists$ stands to $\diamondsuit$ ，where $\exists \phi \equiv \neg ( \forall \neg \phi ) )$ ：

Let $N$ denote a first-order language based on $\wedge , \vee , \odot , \neg ,  , \forall$ and $N _ { m }$ denote the monadic propositional language based on $\wedge , \vee , \odot , \neg ,  , \forall$ ，and $F o r m ( N )$ and （20 $F o r m ( N _ { m } )$ be the set of all formulas of $N , N$ $N _ { m }$ , respectively. We fix a variable $x$ in （204号 $N$ ,associate with each propositional letter $p$ in $F o r m ( N _ { m } )$ a unique monadic predicate $p ^ { \bullet } ( x )$ in $F o r m ( N )$ and define by induction a translation $\Psi : F o r m ( N _ { m } ) \longrightarrow$ $F o r m ( N )$ by putting:

(1） $\Psi ( p ) = p ^ { \bullet } ( x )$ if $p$ is propositional variable,(2) $\Psi ( \alpha \circ \beta ) = \Psi ( \alpha ) \circ \Psi ( \beta )$ ，where $\circ = \vee , \wedge , \odot , \lnot , $ ，(3) $\Psi ( \forall \alpha ) = \forall x \Psi ( \alpha )$ ：

Through this translation $\Psi$ we can identity the formulas of $N _ { m }$ with the monadic formulas of $N$ containing the variable $x$ . Moreover, it is routine to check that $\Psi ( M N L ) \subseteq N M P C$ ，where $N M P C$ stand for the predicate calculus of NM-logic that is defined in the paper [25].

In order to prove a completeness theorem，we are going to summarize some necessary notions of of MNL,which will be used in the further.

The consequence relation $\vdash$ is defined as follows,in the usual way. Let $T$ be a theory,i.e.,a set of formulas in MNL. A (formula) proof of a formula $\phi$ in $T$ is a finite sequence of formulas with $\phi$ at its end, such that every formula in the sequence is either an axiom of MNL,a formula of $T$ , or the result of an application of an deduction rule to previous formulas in the sequence. If a proof of $\phi$ exists in $T$ ， we say that $\phi$ can be deduced from $T$ and we denote this by $T \vdash \phi$ .Moreover $T$ is complete if for each pair $\phi$ . $\psi$ ， $T \vdash \phi  \psi$ or $T \vdash \psi  \phi$ ：

Definition 5.1. Let $\mathcal { L } = ( L , \wedge , \vee , \neg , 0 , 1 , \forall )$ be a monadic NM-algebra and $T$ be a theory. An $\mathcal { L }$ -evaluation is a mapping $e$ from the set of formulas of MNL to $L$ （204号 that satisfies, for each two formulas $\phi$ and $\psi$ ： $e ( \phi \to \psi ) = e ( \phi ) \Rightarrow e ( \psi )$ ， $e ( \phi \lor \psi ) =$ （204号 $e ( \phi ) \sqcup e ( \psi )$ ， $e ( \phi \wedge \psi ) = e ( \phi ) \cap e ( \psi )$ ， $e ( \phi \& \psi ) = e ( \phi ) \odot e ( \psi )$ ， $e ( \lnot \phi ) = ( e ( \phi ) ) ^ { * }$ ， （204号 $e ( \forall \phi ) = \forall e ( \phi )$ ， $e ( \bar { 0 } ) { = } 0$ and $e ( \bar { 1 } ) { = } 1$ .If a $\mathcal { L }$ -evaluation $e$ satisfies $e ( \chi ) = 1$ for every $\chi$ in $T$ , it is called a $\mathcal { L }$ -model of $T$ ：

Now, we stress our attention to the Lindenbaum-Tarski algebra of MNL.

Definition 5.2. Let $T$ be a fixed theory over MNL. For each formula $\phi$ ，let $[ \phi ] _ { T }$ be the set of all formulas $\psi$ such that $T \vdash \phi \equiv \psi$ and $L / T$ be the set of all the class $[ \phi ] _ { T }$ .We define: $0 = [ 0 ] _ { T }$ ， $1 = [ 1 ] _ { T }$ ， $[ \phi ] _ { T }  [ \psi ] _ { T } = [ \phi  \psi ] _ { T }$ ， $[ \phi ] _ { T } \vee [ \psi ] _ { T } = [ \phi \vee \psi ] _ { T }$ $[ \phi ] _ { T } \wedge [ \psi ] _ { T } = [ \phi \wedge \psi ] _ { T }$ ， $[ \neg \phi ] _ { T } = \neg ( [ \phi ] _ { T } )$ ， $\forall _ { T } [ \phi ] _ { T } = [ \forall \phi ] _ { T }$ . This algebra is denoted by $\mathcal { L } _ { \mathcal { T } } = ( L / T ,  , \vee , \wedge , \supset , 0 , 1 , \forall _ { T } )$ ：

Proposition 5.3. $\mathcal { L } _ { \mathcal { T } } = ( L / T ,  , \vee , \wedge , \lnot , 0 , 1 , \forall _ { T } )$ is a monadic NM-algebra.

Proof. $L _ { T }$ with lattice ordering $[ \phi ] _ { T } \leq [ \psi ] _ { T }$ if and only if $T \vdash \phi \Rightarrow \psi$ ， indeed, if $T \vdash \varphi \Rightarrow \psi$ then $T \vdash \varphi \equiv ( \phi \land \psi )$ ，thus $[ \varphi ] _ { T } = [ \varphi ] _ { T } \cap [ \psi ]$ and $[ \varphi ] _ { T } \leq [ \psi ] _ { T }$ Conversely if $[ \varphi ] _ { T } \leq [ \psi ] _ { T }$ ， thus $T \vdash \varphi \equiv ( \varphi \land \psi )$ then $T \vdash \varphi \Rightarrow \psi$ . It remains to show that $\mathcal { L } _ { T }$ satisfies the axioms (U1)-(U4):   
(U1) $\forall _ { T } [ \phi ] _ { T } = [ \forall \phi ] _ { T } \leq [ \phi ] _ { T }$ ，   
(U2) $\forall _ { T } ( | \neg \phi | _ { T } \Rightarrow | \forall \psi | _ { T } ) = \forall _ { T } ( \neg | \phi | _ { T } \Rightarrow \forall _ { T } [ \psi | _ { T } ) = \forall _ { T } [ \neg \phi \to \forall \psi | _ { T } = | \forall \neg \phi | _ { T } ]$ (-Φ→ )] $\cdot = | \neg \forall \phi \to \forall \psi | _ { T } = | \neg \forall \phi | _ { T } \Rightarrow | \forall \psi | _ { T } = \neg \forall _ { T } [ \phi | _ { T } \to \forall _ { T } [ \psi ] _ { T } .$ (U3 $\begin{array} { r } { \nabla _ { T } ( \forall _ { T } \vert \phi \vert _ { T } \to \vert \psi \vert _ { T } ) = \forall _ { T } ( \vert \forall \phi \vert _ { T } \to \vert \psi \vert _ { T } ) = \forall _ { T } \vert \forall \phi \Rightarrow \psi \vert _ { T } = \vert \forall ( \forall \phi \Rightarrow \forall \phi ) \vert _ { T } = \forall ( \forall \phi \lor \phi ) } \end{array}$ γ)]r = $[ \forall \phi \Rightarrow \forall \varphi ] _ { T } = [ \forall \phi ] _ { T }  [ \forall \varphi ] _ { T }$ ：   
$( \mathbb { U } 4 ) \forall _ { T } ( [ \phi ] _ { T } \vee \forall _ { T } [ \psi ] _ { T } ) = [ \forall ( \forall [ \phi ] _ { T } \vee \psi ] _ { T } = [ \forall [ \phi ] _ { T } \vee \forall [ \psi ] _ { T } ] _ { T } = \forall [ \phi ] _ { T } \vee \forall [ \psi ] _ { T }$ （2 Therefore, $\mathcal { L } _ { \mathcal { T } } = ( L / T ,  , \vee , \lnot , 0 , 1 , \forall _ { T } )$ is a monadic NM-algebra and this is the Lindembaum-Tarski algebra of the MNL.

Theorem 5.4. Let $T$ be a theory over MNL. Then $T$ is complete if and only if the monadic NM-algebra $\mathcal { L } _ { \mathcal { T } } = ( L / T ,  , \land , \lor , \lnot , 0 , 1 , \forall _ { T } )$ is linearly ordered

Proof. It is similar to the proof of Theorem 4.13.

It is easy to check that MNL is sound with respect to the variety of monadic NM-algebras, i.e.,that is, if a formula $\phi$ can be deduced from a theory $T$ in MNL, then for every monadic NM-algebra $\mathcal { L }$ and for every $\mathcal { L }$ -model $e$ of $T$ ， $e ( \phi ) = 1$ Indeed, we need to verify the soundness of the new axioms and deduction of MNL (for the axioms and rules of NM, the reader can check [8]). For the axioms this is easy, as they are straightforward generalizations of axioms of monadic NM-algebras. We will now verify the soundness of the new deduction rules.

Proposition 5.5. The deduction rules of MNL are sound in the following sense, for any formula $\phi$ and $\psi$

(1) If for all monadic NM-algebra $\mathcal { L }$ and for all $\mathcal { L }$ -model e for $T$ ， $e ( \phi ) = 1$ ，then for all monadic NM-algebra $\mathcal { L }$ and for all $\mathcal { L }$ -tautology e for $T$ ， $e ( \forall \phi ) = 1$ ：   
(2) If for all monadic NM-algebra $\mathcal { L }$ and for all $\mathcal { L }$ -model e for $T$ ， $e ( \phi ) = 1$ and （204号 $e ( \phi \to \psi ) = 1$ ， then for all monadic NM-algebra $\mathcal { L }$ and for all $\mathcal { L }$ -model $e$ for （20 $T$ ， $e ( \psi ) = 1$ ： Proof. (1) Take such a monadic NM-algebra $\mathcal { L }$ and such a model $e$ . Then $e ( \phi ) = 1$ and $e ( \forall \phi ) = \forall e ( \phi ) = \forall 1 = 1$ ：   
(2) Take such monadic NM-algebra and a model $e$ . Then $e ( \phi ) \to e ( \psi ) = e ( \phi ) \to $ $e ( \psi ) = 1$ ，which means $e ( \phi ) \leq e ( \psi )$ .If $e ( \phi ) = 1$ ，we have $1 = e ( \phi ) \leq e ( \psi )$ and thus $e ( \psi ) = 1$ ：

In what following, the completeness theorem of MNL，which related to the provability in a theory to truth in all models of the theory.

Theorem 5.6.Let $T$ be a theory over MNL. For each formula $\phi$ ， the following are equivalent:

(1) $T \vdash \phi$ ，(2) for each monadic NM-algebra $\mathcal { L }$ and for every L-model e of $T$ ， $e ( \phi ) = 1$ ：

Proof. The implication (1) to (2) follows from Propositions 5.3 and 5.5. (2) to (1): To this end recall Proposition 5.3 saying，among other things, that the algebra $\mathcal { L } _ { T }$ of classes of equivalent formulas of monadic NM-logic, is a monadic NM-algebra, thus $\phi$ isa $\mathcal { L } _ { T }$ tautology if it satisfy (2). In particular, let $e ( p i ) = [ p i ] _ { T }$ and $e ( \forall p i ) = [ \forall p i ] _ { T }$ for all propositional variables pi. Then $e ( \phi ) = [ \phi ] _ { T } = [ 1 ] _ { T }$ thus $T \vdash \phi \equiv 1$ ，hence $T \vdash \phi$ ：

In what followings, we shall analyse one axiomatic extension of MNL in order to prove completeness with respect to linearly ordered structures. The corresponding classes of models are strong monadic NM-algebras, that is a subvarieties of monadic NM-algebras. First， we introduce the propositional calculus strong monadic NMlogic (SMNL, for short),which is an axiomatic extension of MNL.

Definition 5.7. The axioms of SMNL are those of MNL plus $\forall ( \phi \lor \psi )  \forall \phi \lor \forall \psi$ where $\phi$ and $\psi$ are arbitrary formulas of MNL.

The deduction rules are modus ponens (MP, from $\phi$ and $\phi  \psi$ infer $\psi$ ), Generalization( G, from $\phi$ infer $\forall \boldsymbol \phi$ ）

If $T$ is an arbitrary set of formulas then the Lindenbaum-Tarski algebra is defined as usual and it will be denoted by $S L _ { T }$ .It is obvious that $S L _ { \tau }$ isa monadic NM-algebra which satisfies the algebraic identities corresponding to the logical axioms $\forall ( \phi \lor \psi )  \forall \phi \lor \forall \psi$ ：

Theorem 5.8. Let $T$ be α theory over SMNL. If $T$ is a theory and $T \vdash \phi$ ，then there is a consistent complete supertheory $T ^ { \prime } \supseteq T$ such that $T ^ { \prime } \vdash \phi$

Proof. It is similar to the proof of Theorem 4.18.

By Definition 3.12, it follows that Lindenbaum-Tarski algebra $S L _ { \tau }$ is a strong monadic NM-algebra for any set $T$ of formulas. Hence, the semantics of SMNL uses evaluations with values in strong monadic NM-algebra and, by Theorem 4.19 the following completeness result is straightforward.

Theorem 5.9. The following are equivalent:

(1) $T \vdash \phi$ ，   
(2) for each strong monadic NM-algebra L and for every $\mathcal { L }$ -model e of $T$ ， $e ( \phi ) = 1$   
(3) for each linearly ordered strong monadic NM-algebra L and for every $\mathcal { L }$ -model eof $T$ ， $e ( \phi ) = 1$

Proof. It follows from Theorems 4.19,5.8

# 6．Conclusions

In this paper, motivated by the previous research of monadic MV-algebras, we extended the concept of quantifiers to NM-algebras. We introduce and study monadic NM-algebras and their monadic filters and find the relations between quantifiers and modal operators on NM-algebras. Using the notion of monadic filters, we characterize kinds of monadic NM-algebras and focus on a monadic analogous of representation theorem for NM-algebras. Then, we introduce the monadic NM-logic and study some properties of them. As an application of (strong) monadic NM-algebras, we prove the (chain) completeness of monadic NM-logic. Since the above topics are of current interest we suggest further directions of research:

(1） Introducing and studying polyadic NM-algebras, which are further generalizations of monadic NM-algebras given by polyadic structures.   
(2) Focusing on the varieties of monadic NM-algebras. In particular, one can investigate semisimple, locally finite, finitely approximated and splitting varieties of monadic NM-algebras as well as varieties with the disjunction and the existence properties.

# Acknowledgments

This research is supported by a grant of National Natural Science Foundation of China (11571281,11601302).

# References

[1] A. Di Nola, R. Grigolia, On monadic MV-algebras, Annals of Pure and Applied Logic,128(2004), 125-139.   
[2] A. Monteiro, Noemalidad de las álgebras de Heyting monadicas, Actas de las $X$ Jornadas de la Unió Mathematical Society, 174(1972), 1-43.   
[3] C. G. Sheng, G. J. Wang, R $_ 0$ -algebra and it's structure, Acta Mathematica Scientia, 19(2001), 584-588.   
[4] D. W. Pei, On equivalent forms of fuzzy logics systems NM and IMTL, Fuzzy Sets Syst,138(2003), 187-195.   
[5] D. W. Pei, G. J. Wang, The completeness and application of formal systems L, Sci China (Ser E)，1(2002), 56-64.   
[6] D. W. Pei, R $_ 0$ -implication: characteristics and applications, Fuzzy Sets Syst,131(2002)， 297-302.   
[7] E. Turunen， BL-algebras of basic fuzzy logic， Mathware Soft Comput, 6(1998),49-61.   
[8] F. Esteva,L. Godo,Monoidal t-norm based logic: towards a logic for leftcontinuoust-norms, Fuzzy Sets Syst,124(2001), 271-288.   
[9] F. Tan, C. W. Li, H. Z. Yi, The irreducibly representational theorems of Roalgebras, Fuzzy Systems and Mathematics, 21(2010),1-5.   
[10] G. Bezhanisvili, Varieties of monadic Heyting algebras I, Stud. Log, 61(1999), 367-402.   
[11] G. Cattaneo， Abstract approximation spaces for rough theories， in: L.Polkowski, A. Skowron(Eds),Rough Sets in Knowledge Discovery 1:Methodology and Applications,Physica-Verlag, Wurzhurg, 1998, 59-98.   
[12] G. J. Wang, H. J. Zhou, Introduction to Mathematical Logic and Resolution Principle, Alpha Science International Ltd, Oxford, 2009.   
[13] G. J. Wang,A formal deductive system for fuzzy propositional calculus, Chin.Sci.Bull, 42(1997), 1521-1526.   
[14] H. J. Zhou, Stone topological representation theorem for $\mathrm { R _ { 0 } }$ -algebras, Fuzzy Systems and Mathematics, 24(2010),14-23.   
[15] H. J. Zhou,B. Zhao, Stone-like representation theorems and three-valued filters in $\mathrm { R _ { 0 } }$ -algebras(nilpotent minimum algebras), Fuzzy Sets Syst,162(2011), 1-26.   
[16] H. R. Zhang,Q. J. Xie, Filter theory of $\mathrm { R } _ { 0 }$ -algebras, Fuzzy Systems and Mathematics, 23(2009), 17-21.   
[17] I. Nemeti, Algebraiaztion of quantifier logics, Stud. Log, 5O(1991), 485-569.   
[18] J. D.Rutledge,A preliminary investigation of the infinitely many-valued predicate calculus, Ph.D,Thesis, Cornell University,1959.   
[19] J. L. Zhang, Topological properties of prime filters in MTL-algebras and fuzzy set representations for MTL-algebras, Fuzzy Sets Syst,178(2011), 38-53.   
[20] J. Rachunek, D. Salounová, Monadic GMV-algebras， Arch. Math. Logic, 47(2008)， 277-297.   
[21] J. Rachunek，D. Salounov&，Monadic bounded residuated lattices, Order, 30(2013), 195-210.   
[22] J. T. Wang, X. L. Xin, P. F. He, Monadic bounded hoops, Soft Computing, revised.   
[23] J. Y. Duan, G. J. Wang, Three types of fuzzy modal logic about K, Journal of Shandong University(Natural Science), 43(2008), 31-39.   
[24] L. Henkin, D.J. Monk,A. Tarski, Cylindric algebras,part I, North Holland, Amster-dim,1971.   
[25] M. Bianchi, First-order Nilpotent minimum logics: first steps, Arch. Math. Logic, 52(2013), 295-316.   
[26] P. Hajek, Metamathematics of Fuzzy Logic, Kluwer Academic Publishers, Dordrecht,1998.   
[27] R. Grigolia, Monadic BL-algebras, Georgain Mathematical Journal, 13(2006), 267-276.   
[28] S. Aguzzoli, B. Gerla, Normal forms and free algebras for some extensions of MTL, Fuzzy Sets Syst, 159(2008)， 1131-1152.   
[29] R. P. Halmos, Algebraic logic. Chelsea Publ. Co, New York, 1962.   
[30] S. M. Wang, B. S. Wang, X. Y. Wang, A characterization of truth-functions in the nilpotent minimum logic, Fuzzy Sets Syst, 145(2004), 253-266.   
[31] S. Burris, M. P. Sankappanavar， A Course in Universal Algebra, SpringerVerlag, New York,1981.   
[32] T. S. Blyth, Lattices and ordered algebraic structures, Springer-Verlag London Limited, 2005.   
[33] Y. B. Jun, L. Z. Liu,Filter of R $_ 0$ -algebras, International Journal of Mathematics & Mathematical Sciences,171(2006), 61-71.