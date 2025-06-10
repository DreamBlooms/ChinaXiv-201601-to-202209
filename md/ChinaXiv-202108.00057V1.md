# Properties of fuzzy set

Huan Huang Departmentof Mathematics,Jimei University，Xiamen 361021,China

# Abstract

In this paper, we give some properties related to platform points of a fuzzy set and their applications.

Keywords: Fuzzy set; platform points; $\Gamma$ -convergence

# 1. Main results

Let $( X , d )$ be a metric space. For $u \in F ( X )$ ，let $[ u ] _ { \alpha }$ denote the $\alpha \mathrm { \Omega }$ -cut of （20 $u$ ，i.e.

$$
[ u ] _ { \alpha } = \left\{ \{ x \in X : u ( x ) \geq \alpha \} , \quad \alpha \in ( 0 , 1 ] , \right.
$$

where $\overline { S }$ denotes the closure of $S$ in $( X , d )$ ： $F _ { U S C } ( X )$ is the set of uppersemi-continuous fuzzy sets in $X$ ：

For $u \in F ( X )$ 2

$$
\begin{array} { r l r } & { } & { D ( u ) : = \{ \alpha \in ( 0 , 1 ) : [ u ] _ { \alpha } \notin \overline { { \{ u > \alpha \} } } \} , } \\ & { } & { P ( u ) : = \{ \alpha \in ( 0 , 1 ) : \overline { { \{ u > \alpha \} } } \subsetneq [ u ] _ { \alpha } \} . } \end{array}
$$

$\alpha \in P ( u )$ is called a platform point of $u$ . Clearly $P ( u ) \subseteq D ( u )$

We show that $D ( u )$ is at most countable when $u \in F ( \mathbb { R } ^ { m } )$ (Theorem 5.1 of [1]).

In this paper, we show that $D ( u )$ is at most countable for fuzzy set $u \in F ( X )$ with $( [ u ] _ { 0 } , d )$ being separable. This result follows directly from the proof of Theorem 5.1 of [1] and the fact that each separable metric space is homeomorphic to a subspace of the Hilbert space $l ^ { 2 } : = \{ ( x _ { i } ) _ { i = 1 } ^ { + \infty } : \textstyle \sum _ { i = 1 } ^ { + \infty } x _ { i } ^ { 2 } <$ $+ \infty \}$ . We also give some applications of this conclusion.

Theorem 1.1. Let $u \in F ( l ^ { 2 } )$ . Then the set $D ( u )$ is at most countable.

Proof. The proof is similar to that of Theorem 5.1 in [1]. A sketch of the proof is given as follows Similarly as in [1], for $u \in F ( l ^ { 2 } )$ ， $t \in { \mathrm { ~ } } l ^ { 2 }$ and $r \in \mathbb { R } ^ { + }$ ，we can define   
$S _ { u , t , r } ( \cdot , \cdot ) : \mathbf { S } ^ { \mathrm { 1 } } \times [ 0 , 1 ] \to \{ - \infty \} \cup \mathbb { R }$ by

$$
S _ { u , t , r } ( e , \alpha ) = \left\{ \begin{array} { l l } { - \infty , } & { \mathrm { i f ~ } [ u ] _ { \alpha } \cap \overline { { B ( t , r ) } } = \emptyset , } \\ { \operatorname* { s u p } \{ \langle e , x - t \rangle : x \in [ u ] _ { \alpha } \cap \overline { { B ( t , r ) } } \} , } & { \mathrm { i f ~ } [ u ] _ { \alpha } \cap \overline { { B ( t , r ) } } \neq \emptyset , } \end{array} \right.
$$

where $\mathbf { S } ^ { \mathrm { 1 } } : = \{ e \in l ^ { 2 } : \| e \| = 1 \}$ and ${ \overline { { B ( t , r ) } } } : = \{ x \in l ^ { 2 } : \| x - t \| \leq r \}$ （204号

Similarly as in [1],we can define $D ( u , t , r , e )$ ，which is the discontinuous point of $S _ { u , t , r } ( e , \cdot )$ ：

Proceed as in the proof of Lemma A.1. of [1], we can show the conclusion corresponding to Lemma A.1. of [1]: $D ( u , t , r ) = \cup _ { e \in { \bf S } ^ { 1 } } D ( u , t , r , e )$ is countable.

Note that $2 \langle a , b \rangle = \| a \| ^ { 2 } + \| b \| ^ { 2 } - \| a - b \| ^ { 2 }$ for each $a , b \in l ^ { 2 }$ . So proceed as in the proof of Theorem 5.1, we obtain that $D ( u )$ is at most countable.

Remark 1.2. In the proof of Theorem 5.1, the fact that $2 \langle a , b \rangle = \| a \| ^ { 2 } +$ $\| b \| ^ { 2 } - \| a - b \| ^ { 2 }$ for each $a , b \in \mathbb { R } ^ { m }$ is used.

Clearly, (A.6) in the proof of Theorem 5.1 can be shown by using the equality (e,x-q)=-q-)-²+y-a-y

Theorem 1.3. Let $( X , d )$ be a metric space and $u \in F ( X )$ .If $( [ u ] _ { 0 } , d )$ is separable, then the set $D ( u )$ is at most countable.

Proof. Let $f$ be a homeomorphism from $( [ u ] _ { 0 } , d )$ to a subspace of $l ^ { 2 }$ Consider $u _ { f } \in F ( l ^ { 2 } )$ defined by

$$
\begin{array} { r } { { u } _ { f } ( t ) = \left\{ \begin{array} { l l } { u ( f ^ { - 1 } ( t ) ) , } & { t \in f ( [ u ] _ { 0 } ) , } \\ { 0 , } & { t \in l ^ { 2 } \setminus f ( [ u ] _ { 0 } ) . } \end{array} \right. } \end{array}
$$

Note that $D ( u ) = D ( u _ { f } )$ ， thus $D ( u )$ is at most countable from Theorem l.1.

Remark 1.4. Here we mention that the closure operator in the definition of $D ( u )$ is taken in $( X , d )$ and the closure operator in the definition of $D ( u _ { f } )$ is taken in $l ^ { 2 }$ ·

Theorem 1.5.Let $( X , d )$ be a metric space and $u \in F ( X )$ .If $( [ u ] _ { 0 } , d )$ is separable, then the set $P ( u )$ is at most countable.

Proof. The desired result follows immediately from Theorem 1.3 and the fact that $P ( u ) \subseteq D ( u )$

There are various kinds of fuzzy sets [2]. Since the corresponding discussion in [3] is in the framework of normal fuzzy sets, we only discuss normal fuzzy sets in the following

$$
\begin{array} { r l } & { F _ { U S C G } ^ { 1 } ( X ) : = \{ u \in F ( X ) : [ u ] _ { \alpha } \in K ( X ) \mathrm { ~ f o r ~ a l l ~ } \alpha \in ( 0 , 1 ] \} , } \\ & { \ F _ { U S C } ^ { 1 } ( X ) : = \{ u \in F ( X ) : [ u ] _ { \alpha } \in C ( X ) \mathrm { ~ f o r ~ a l l ~ } \alpha \in ( 0 , 1 ] \} , } \\ & { F _ { U S C } ( X ) = \{ u \in F ( X ) : [ u ] _ { \alpha } \in C ( X ) \cup \varnothing \mathrm { ~ f o r ~ a l l ~ } \alpha \in ( 0 , 1 ] \} , } \end{array}
$$

where $K ( X )$ and $C ( X )$ denote the set of all non-empty compact subsets of $( X , d )$ and the set of all non-empty closed subsets of $( X , d )$ ， respectively.

Theorem 1.6. Suppose that $u$ ， $u _ { n }$ ， $n = 1 , 2 , \ldots$ ， are fuzzy sets in $F _ { U S C } ^ { 1 } ( X )$ If $( [ u ] _ { 0 } , d )$ is separable, then the following statements are true.

i $u _ { n } \xrightarrow { \Gamma } u$   
(i) $u _ { n } \xrightarrow { a . e . } u \left( K \right)$ ：   
(iii) $[ u ] _ { \alpha } = \operatorname* { l i m } _ { n \to \infty } [ u _ { n } ] _ { \alpha } \left( K \right)$ for all $\alpha \in ( 0 , 1 ) \setminus P ( u )$   
(iu) $\mathrm { l i m } _ { n  \infty } [ u _ { n } ] _ { \alpha } ( K ) = [ u ] _ { \alpha }$ holds when $\alpha \in P$ ，where $P$ is a dense subset of $( 0 , 1 ) \backslash P ( u )$ ：   
(u） $\mathrm { l i m } _ { n  \infty } [ u _ { n } ] _ { \alpha } ( K ) = [ u ] _ { \alpha }$ holds when $\alpha \in P$ ，where $P$ is a countable dense subset of $( 0 , 1 ) \backslash P ( u )$

Proof. The desired result follows immediately from Theorem 1.5 and Theorem 3.8 in [3].

Remark 1.7. Note that each compact metric space is separable. So if $u \in$ $F _ { U S C G } ^ { 1 } ( X )$ ，then $( [ u ] _ { 0 } , d )$ is separable. Thus Theorem 1.6 improves Theorem 3.9 in [3].

For $u \in F _ { U S C } ^ { 1 } ( X )$ ，the set $P _ { 0 } ( u )$ is defined by $P _ { 0 } ( u ) : = \{ \alpha \in ( 0 , 1 ) :$ $\begin{array} { r } { \operatorname* { l i m } _ { \beta \to \alpha } H ( [ u ] _ { \beta } , [ u ] _ { \alpha } ) \neq 0 \} } \end{array}$ ,where $H$ is the Hausdorff metric on $C ( X )$ induced by $d$ ：

By Theorem 1.5 and Lemma 3.6 in [3],we have that $P _ { 0 } ( u )$ is at most countable for each $u \in F _ { U S C G } ^ { 1 } ( X )$ ：

Lemma 3.6 in [3] is listed as follows

Let $U _ { n } \in K ( X )$ for $n = 1 , 2 , \ldots$   
(i）If $U _ { 1 } \supseteq U _ { 2 } \supseteq \dots \supseteq U _ { n } \supseteq \dots .$ ，then $\begin{array} { r } { U = \bigcap _ { n = 1 } ^ { + \infty } U _ { n } \in K ( X ) } \end{array}$ and$H ( U _ { n } , U ) \to 0$ as $n \to + \infty$ ：(ii）If $U _ { 1 } \subseteq U _ { 2 } \subseteq \ldots \subseteq U _ { n } \subseteq \ldots .$ and $\textstyle V = \bigcup _ { n = 1 } ^ { + \infty } U _ { n } \in K ( X )$ ， then$H ( U _ { n } , V ) \to 0$ as $n \to + \infty$ ：

However, for $u \in F _ { U S C } ^ { 1 } ( X )$ with $( [ u ] _ { 0 } , d )$ being separable, $P _ { 0 } ( u )$ need not be at most countable. A counterexample is given in page 7 of [3].

[1] H. Huang, Characterizations of endograph metric and $\Gamma$ -convergence on fuzzy sets, Fuzzy Sets Syst. 350 (2018) 55-84   
[2] C.Wu, M. Ma, The Basic of Fuzzy Analysis (in Chinese)，National Defence Industry press,Beijing,1991   
[3] H. Huang， Propertiesofseveral fuzzy set spaces， chinaXiv:202107.00011