# ON THE BIRCH AND SWINNERTON-DYER CONJECTURE FOR CM ELLIPTIC CURVES OVER $\mathbb { Q }$

YONGXIONGLI,YULIU ANDYE TIAN

To John Coates for his 7Oth birthday

# CONTENTS

1. Introduction and Main Theorems 1   
2. Katz's $\cdot$ -adic L-function and Cyclotomic $\cdot$ -adic Formula 3   
3． $\cdot$ -adic and $p$ -adic Gross-Zagier Formulae 6   
4. Proof of Main Theorem 1.1 8   
References 9

# 1.INTRODUCTION AND MAIN THEOREMS

For an elliptic curve $E$ over a number field $F$ ，we write $L ( s , E / F )$ for its complex $L$ -function, $E ( F )$ （204号 for the Mordell-Weil group of $E$ over $F$ ，and $\operatorname { I I I } ( E / F )$ for its Tate-Shafarevich group. For any prime $p$ ， let $\mathrm { I I I } ( E / F ) ( p )$ or $\mathrm { I I I } ( E / \mathbb { Q } ) [ p ^ { \infty } ]$ denote the $p$ -primary part of $\operatorname { I I I } ( E / F )$ .When $F = \mathbb { Q }$ , we shall simply write $L ( s , E ) = L ( s , E / \mathbb { Q } )$ ：

Theorem 1.1. Let $E$ be an elliptic curve over $\mathbb { Q }$ with complex multiplication. Let $p$ be any potentially good ordinary odd prime for $E$ ：

(i) Assume that $L ( s , E )$ has a simple zero at $s = 1$ . Then $E ( \mathbb { Q } )$ has rank one and $\operatorname { I I I } ( E / \mathbb { Q } )$ is finite. Moreover the order ofII ${ \cal \tilde { \rho } } ( E / \mathbb { Q } ) ( p )$ is as predicted by the conjecture of Birch and Swinnerton-Dyer conjecture.   
(ii)If $E ( \mathbb { Q } )$ has rank one and III $( E / \mathbb { Q } ) ( p )$ is finite, then $L ( E , s )$ has a simple zero at $s = 1$

Remark. The first part of (i) is the result of Gros-Zagier and Kolyvagin. The remaining part is due to Perrin-Riou for good ordinary primes.In this paper,we deal with odd bad primes which are potentially good ordinary. The result can be easily generalized to abelian varieties over $\mathbb { Q }$ corresponding to a CM modular form with trivial central character.

The following theorem shows that there are infinitely many elliptic curves over $\mathbb { Q }$ of rank one for which the full BSD conjecture hold.

Theorem 1.2.Let $n \equiv 5$ mod 8 be a squarefree positive integer, all of whose prime factors are congruent to 1 modulo 4. Assume that $\mathbb { Q } ( { \sqrt { - n } } )$ has no ideal class of order 4. Then the full BSD conjecture holds for the elliptic curve $y ^ { 2 } = x ^ { 3 } - n ^ { 2 } x$ over $\mathbb { Q }$ . In particular, for any prime $p \equiv 5$ mod 8, the full BSD holds for $y ^ { 2 } = x ^ { 3 } - p ^ { 2 } x$ ：

Sketch of Proof. Consider the Heegner point $P$ constructed using the Gross-Prasad test vector as the below Theorem 1.3. Using an induction argument as in [16] or [17],one can show that $P$ is non-torsion. Thus both the analytic rank and Mordell-Weil rank of $E ^ { ( n ) } : y ^ { 2 } = x ^ { 3 } - n ^ { 2 } x$ are one.

By Perrion-Riou [12] and Kobayashi [8],we know that the $p$ -part of full BSD holds for all primes $p \nmid 2 n$ . The 2-part of BSD for $E ^ { ( n ) }$ is exactly the statement on 2-divisibility in Theorem 1.3 below by using explicit Gross-Zagier formula in [2] and noting that $\dim _ { \mathbb { F } _ { 2 } } { \operatorname { S e l } _ { 2 } } ( E ^ { ( n ) } / \mathbb { Q } ) / \mathrm { I m } ( E ^ { ( n ) } ( \mathbb { Q } ) _ { \mathrm { t o r } } ) = 1$ By Theorem 1.1, the $p$ -part of BSD also holds for all primes $p | n$ ， since all primes $p$ with $p \equiv 1$ mod 4 are potentially good ordinary primes for $E ^ { ( n ) }$ ： （204号 $\sqcup$

To solve the Diophantine equation $y ^ { 2 } = x ^ { 3 } - n ^ { 2 } x$ over $\mathbb { Q }$ ， we define the complex uniformization of $E ^ { ( n ) }$ by the following composition.

$$
{ \mathcal { H } } \stackrel { \pi } { \longrightarrow } \Gamma _ { 0 } ( 3 2 ) \backslash { \mathcal { H } } \cup P ^ { 1 } ( \mathbb { Q } ) = X _ { 0 } ( 3 2 ) \stackrel { f _ { 0 } } { \longrightarrow } E ^ { ( 1 ) } \stackrel { [ 2 - 2 i ] } { \longrightarrow } E ^ { ( 1 ) } \stackrel { \iota } { \longrightarrow } E ^ { ( n ) } ,
$$

where

· $\mathcal { H } \stackrel { \pi } { \longrightarrow } \Gamma _ { 0 } ( 3 2 ) \backslash ( \mathcal { H } \cup P ^ { 1 } ( \mathbb { Q } ) ) = X _ { 0 } ( 3 2 ) ( \mathbb { C } )$ is the natural quotient, ： $f _ { 0 } : X _ { 0 } ( 3 2 ) \to E ^ { ( 1 ) }$ is a degree 2 morphism over $\mathbb { Q }$ mapping $\left[ \infty \right]$ to $O$ ， ： $[ 2 - 2 i ]$ is the multiplication by $2 - 2 i$ on $E ^ { ( 1 ) }$ ,， where $i ( x , y ) = ( - x , i y )$ ， ： $\iota : E ^ { ( 1 ) } \stackrel { \sim } { \to } E ^ { ( n ) }$ is the twist isomorphism given by $( x , y ) \mapsto ( - n x , \ ( - n ) ^ { 3 / 2 } y )$

The following theorem,which is equivalent to the 2-part BSD for $E ^ { ( n ) }$ using explicit Gross-Zagier formulε in [2],and can be proved exactly as in [16].

Theorem 1.3. Let $n \equiv 5$ mod 8 be a square-free positive integer as in Theorem 1.2. Then the image （204号 $P _ { 0 } \in E ^ { ( n ) }$ of $( 4 - 4 \sqrt { - n } ) ^ { - 1 } \in \mathcal { H }$ under the above complex uniformization is defined over the Hilbert class feld $H$ of $\mathbb { Q } ( { \sqrt { - n } } )$ Moreover the Heegner point $\begin{array} { r } { P : = \sum _ { \sigma \in \mathrm { G a l } ( H / \mathbb { Q } ( \sqrt { - n } ) ) } P _ { 0 } ^ { \sigma } } \end{array}$ actually belongs to （204 $E ^ { ( n ) } ( \mathbb { Q } )$ Let $\mu ( n )$ be the number of prime factors of $n$ . Then $P \in 2 ^ { \mu ( n ) - 1 } E ^ { ( n ) } ( \mathbb { Q } ) + E ^ { ( n ) } ( \mathbb { Q } ) _ { \mathrm { t o r } }$ but $P \notin 2 ^ { \mu ( n ) } E ^ { ( n ) } ( \mathbb { Q } ) + E ^ { ( n ) } ( \mathbb { Q } ) _ { \mathrm { t o r } }$ . In particular, $P$ is of infinite order.

Moreover, the Mordell-Weil group $E ^ { ( n ) } ( \mathbb { Q } )$ is of rank one and the index of its subgroup generated by $P$ and torsion points satisfies

$$
\Big [ E ^ { ( n ) } ( \mathbb { Q } ) : \mathbb { Z } P + E ^ { ( n ) } ( \mathbb { Q } ) _ { \mathrm { t o r } } \Big ] = 2 ^ { \mu ( n ) - 1 } \cdot \sqrt { | \mathrm { I I I } ( E / \mathbb { Q } ) | } .
$$

Example For the prime $p = 1 4 9 3 \equiv 5$ mod 8, the Mordell-Weil group $E ^ { ( p ) } ( \mathbb { Q } )$ modulo torsion has a generator

$$
\left[ { \frac { 1 6 7 4 3 7 1 1 3 3 } { 7 4 4 7 6 9 } } , - { \frac { 5 1 2 2 4 2 1 4 7 3 4 7 0 0 } { 6 4 2 7 3 5 6 4 7 } } \right] ,
$$

as well that Heegner point $( x , y )$ has coordinates

2456153549914721493968975459422696932728951498371630131453   
x 2958501182854207571944468687561920064681205358510529 121725780668263596873618123810557983972375660184180439465365335709906181098721585260100   
y= 160919109605479862871753246473210772682219745687839109456974711787796868892833

It follows that $\operatorname { I I I } ( E ^ { ( p ) } / \mathbb { Q } ) \cong ( \mathbb { Z } / 3 \mathbb { Z } ) ^ { 2 }$

Let $E$ be an elliptic curve defined over $\mathbb { Q }$ ，with complex multiplication ( $=$ CM in what follows） by an imaginary quadratic field $K$ . Let $p \neq 2$ be a potential good ordinary prime for $E$ . Note that $p$ must split in $K$ ，and also $p$ does not divide the number $w _ { K }$ of roots of unity in $K$ ：

Assume that $L ( s , E )$ has a simple zero at $s = 1$ . Choose an auxiliary imaginary quadratic field $\mathcal { K }$ such that (i) $p$ is split over $\mathcal { K }$ and (ii) $L ( s , E / \mathcal { K } )$ still has a simple zero at $s = 1$ .Let $E ^ { ( \mathcal { K } ) }$ be the twist of $E$ （2 over $\mathcal { K }$ , then $L ( 1 , E ^ { ( \mathcal { K } ) } ) \neq 0$ .Let $\eta$ be the quadratic character associated to the extension $\kappa / \mathbb { Q }$ and $\eta _ { K }$ （204号 its restriction to $K$ .Let $\mathbb { Q } _ { \infty }$ be the cyclotomic $\mathbb { Z } _ { p }$ -extension of $\mathbb { Q }$ ， and put $\Gamma = \operatorname { G a l } ( \mathbb { Q } _ { \infty } / \mathbb { Q } )$ . For any finite order character $\nu$ of $\Gamma$ ,let $\nu \kappa$ denote its restriction to $\operatorname { G a l } ( K \mathbb { Q } _ { \infty } / K )$ . Consider the equality

$$
L ( s , E \otimes \nu ) L ( s , E ^ { ( K ) } \otimes \nu ) = L ( s , E _ { K } \otimes \nu _ { K } )
$$

and its specialization to $s = 1$ .Let $\mathcal { L } _ { \varphi } , \mathcal { L } _ { \varphi \eta \kappa }$ be the cyclotomic-line restrictions of the two Katz's two   
variable -adic L-fucntion corresponding to $E$ and $E ^ { ( \kappa ) }$ , respectively. Let $\mathcal { L } _ { E / \mathcal { K } }$ be the cyclotomic-line $p$   
restriction of the -adic Rankin-Selberg L-function for $E$ over $\mathcal { K }$ . The ingredients needed to prove the $p$   
$p$ -part BSD formula of $E$ are the following.   
(1） Rubin's two variable main conjecture[14] in order to relate the $p$ -part of III $( E / K )$ with $\mathcal { L } _ { \varphi } ^ { \prime } ( 1 )$ Note that $\operatorname { o r d } _ { p } ( | \mathrm { I I I } ( E / K ) | ) = 2 \operatorname { o r d } _ { p } ( | \mathrm { I I I } ( E / \mathbb { Q } ) | )$ for odd $p$ ：   
(2） The complex Gross-Zagier formula [19] and the $p$ -adic Gross-Zagier formula [4],which relate （20 $\mathcal { L } _ { E / \kappa } ^ { \prime } ( 1 )$ and $L ^ { \prime } ( 1 , E / \mathcal { K } ) = L ^ { \prime } ( 1 , E / \mathbb { Q } ) L ( 1 , E ^ { ( \mathcal { K } ) } / \mathbb { Q } )$ ：   
(3）The precise relationship between $\mathcal { L } _ { \varphi } ^ { \prime } ( 1 ) \mathcal { L } \varphi \eta _ { K } ( 1 )$ and $\mathcal { L } _ { E / \kappa } ^ { \prime } ( 1 )$ , and also between $\mathcal { L } _ { \varphi \eta _ { K } } ( 1 )$ and （204号 $L ( 1 , E ^ { ( \mathcal { K } ) } )$ . This follows from the above equality of L-series and the interpolation properties of these $p$ -adic L-fucntions.

Suppose that $E$ has bad reduction at $p$ which is potential good for $E$ .Let $\mathfrak { p }$ denote a prime of $K$ above $p$ . There is an elliptic curve $E ^ { \prime }$ over $K$ with good reduction at $\mathfrak { p }$ . In the process of proof,we need to compare periods,descends etc between $E$ and $E ^ { \prime }$

Notations. Fix a non-trivial additive character $\psi : \mathbb { Q } _ { p } \longrightarrow \mathbb { C } _ { p } ^ { \times }$ with conductor $\mathbb { Z } _ { p }$ . For any character $\chi : \mathbb { Q } _ { p } ^ { \times } \to \mathbb { C } _ { p } ^ { \times }$ , say of conductor $p ^ { \prime \iota }$ with $n \geq 0$ ， we define the root number by

$$
\tau ( \chi , \psi ) = p ^ { - n } \int _ { v _ { p } ( t ) = - n } \chi ^ { - 1 } ( t ) \psi ( t ) d t ,
$$

where $d t$ is the Haar measure on $\mathbb { Q } _ { p }$ such that $\mathrm { V o l } ( \mathbb { Z } _ { p } , d t ) = 1$ .Fix embeddings $\iota _ { \infty } : \overline { { \mathbb { Q } } } \hookrightarrow \mathbb { C }$ and （20 $i _ { p } : \overline { { \mathbb { Q } } } \hookrightarrow \mathbb { C } _ { p }$ such that $\iota _ { p } = \iota \cup \iota _ { \infty }$ for an isomorphism $\iota : \mathbb { C } \stackrel { \sim } { \to } \mathbb { C } _ { p }$ . For an elliptic curve $E$ over a number field $F$ and $p$ a potential good prime for $E$ ,let $( \mathbf { \nabla } , ) _ { \infty }$ and $( \ , \ ) _ { p }$ denote the normalized Néron -Tate height pairing,and the $p$ -adic height pairing with respect to cyclotomic character. Let $P _ { 1 } , \cdot \cdot \cdot , P _ { r } \in E ( F )$ form a basis for $E ( F ) \otimes _ { \mathbb { Z } } \mathbb { Q }$ , define the regulars by

$$
R _ { \infty } ( E / F ) = \frac { \operatorname* { d e t } \left( ( P _ { i } , P _ { j } ) _ { \infty } \right) _ { r \times r } } { [ E ( K ) : \sum _ { i } \mathbb { Z } P _ { i } ] ^ { 2 } } , \qquad R _ { p } ( E / F ) = \frac { \operatorname* { d e t } \left( ( P _ { i } , P _ { j } ) _ { p } \right) _ { r \times r } } { [ E ( K ) : \sum _ { i } \mathbb { Z } P _ { i } ] ^ { 2 } } .
$$

For any character $\chi$ of $\hat { K } ^ { \times }$ ，let ${ \mathfrak { f } } _ { \chi } \subset { \mathcal { O } } _ { K }$ denote its conductor. For an elliptic curve $E$ over $K$ ，let $\mathsf { f } _ { E }$ denote its conductor. For any non-zero integral ideals $\mathfrak { g }$ and $\mathfrak { a }$ of $K$ ，let ${ \mathfrak { g } } ^ { ( { \mathfrak { a } } ) }$ denote the prime-to（20 $\mathfrak { a }$ part of $\mathfrak { g }$ Let $\mathbb { D }$ be the completion of the maximal unramified extension of $\mathbb { Z } _ { p }$ and $\mathbb { D } _ { \chi }$ the finite extension of $\mathbb { D }$ generated by the values of $\chi$ Let $L _ { \infty } / K$ be an abelian extension whose Galois group $\mathcal { G } = \mathrm { G a l } ( L _ { \infty } / K ) \cong \Delta \times \Gamma$ with $\Delta$ finite and $\Gamma \cong \mathbb { Z } _ { p } ^ { d }$ . Then for any $\mathbb { D } [ [ \mathcal { G } ] ]$ -module $M$ and character $\chi$ of $\Delta$ ，put $M _ { \chi } = M \otimes _ { \mathbb { D } [ [ \mathcal { G } ] ] , \chi } \mathbb { D } _ { \chi } \lfloor \lfloor \Gamma \rfloor \rfloor$ .If $p \nmid \lvert \Delta \rvert$ ,let $M ^ { \chi }$ denote its $\chi$ -component (as a direct summand).

Acknouledgment. The authors thank John Coates,Henri Darmon and Shouwu Zhang for their encouragement.

# 2.KATZ'S $p$ -ADIC L-FUNCTION AND CYCLOTOMIC $p$ -ADICFORMULA

Let $E$ be an elliptic curve defined over $K$ with CM by $K$ and $\varphi$ its associated Hecke character.Let （20 $p \nmid w _ { K }$ be a prime split in $K$ and $p { \mathcal { O } } _ { K } = { \mathfrak { p } } { \mathfrak { p } } ^ { * }$ with $\mathfrak { p }$ induced by $\iota _ { p }$ . In particular, $K _ { \mathfrak { p } } = \mathbb { Q } _ { p }$ in $\mathbb { C } _ { p }$ and let $\psi _ { \mathfrak { p } } = \psi _ { p }$ on $K _ { \mathfrak { p } }$ under this identification. Let $\Omega _ { E }$ be a $\mathfrak { p }$ -minimal period of $E$ over $K$ .Let $\varphi$ be the associated Hecke character of $E$ and $\varphi _ { \mathfrak { p } }$ its $\mathfrak { p }$ -component. Let $\mathrm { f } _ { E }$ be the conductor of $\varphi$ ：

Let $F$ be an abelian extension over $K$ with Galois group $\Delta$ . Assume that $p \nmid \lvert \Delta \rvert$ and denote by $⨏ _ { F / K }$ （204 the conductor of $F$ .Let $\mathcal { G }$ be the Galois group of the extension $F ( E [ p ^ { \infty } ] )$ over $K$ . Then $\mathcal { G } \cong \mathcal { G } _ { \mathrm { t o r } } \times \Gamma _ { K }$ with $\Gamma _ { K } = \mathrm { G a l } ( F ( E [ p ^ { \infty } ] ) / F ( E [ p ] ) )$ .Let $\Lambda = \mathbb { Z } _ { p } [ | \mathcal { G } ] ]$ .Let $U _ { \infty }$ and $C _ { \infty }$ denote the $\mathbb { Z } _ { p } [ [ \mathcal { G } ] ]$ -modules formed from the principal local units at the primes above $\mathfrak { p }$ ，and the closure of the elliptic units for $K ( E [ p ^ { \infty } ] )$ (see $\ S 4$ of [14] for the precise definitions.)

Theorem 2.1 (Two variable -adic L-function). Let be any prime-to non-zero integral ideal of $K$ $p$ $\mathfrak { g }$ $p$   
Assume that $\boldsymbol { \mathfrak { f } } _ { E } ^ { ( p ) } | \mathfrak { g }$ There erists a unique measure $\mu _ { { \mathfrak { g } } } = \mu _ { { \mathfrak { g } } , { \mathfrak { p } } }$ on the group $\mathcal { G } = \mathrm { G a l } ( K ( \mathfrak { g } p ^ { \infty } ) / K )$ such   
that for any character $\rho$ of $\mathcal { G }$ of type $( 1 , 0 )$ ，

$$
\rho ( \mu _ { \mathfrak { g } } ) = \frac { \tau ( \rho _ { \mathfrak { p } } , \psi _ { \mathfrak { p } } ) } { \tau ( \varphi _ { \mathfrak { p } } , \psi _ { \mathfrak { p } } ) } \cdot \frac { 1 - \rho ( \mathfrak { p } ) p ^ { - 1 } } { 1 - \overline { { \rho ( \mathfrak { p } ) } } p ^ { - 1 } } \cdot \frac { L ^ { ( \mathfrak { g } p ) } ( \overline { { \rho } } , 1 ) } { \Omega _ { E } } .
$$

Here $L ^ { \left( { \mathfrak { g } } p \right) } ( { \overline { { \rho } } } , s )$ is the imprimitive $L$ -series of $\rho$ with Euler factors at places dividing $\mathfrak { f } p$ -removed.

Proof. It follows from the below lemma 2.3 and construction of Katz's two variable $p$ -adic measure,see Theorem 4.14. □

Theorem 2.2 (Yager). For any character $\chi$ of $\scriptstyle { \mathcal { G } } _ { \mathrm { t o r } }$ ，let $\mathfrak { f } = \mathfrak { f } _ { \chi } ^ { ( p ) }$ and $\mu _ { \mathfrak { f } } ^ { \chi } : = \chi ( \mu _ { \mathfrak { f } } ) \in \mathbb { D } [ [ \Gamma _ { K } ] ]$ . Then we have

$$
\mathrm { C h a r } ( U _ { \infty } / C _ { \infty } ) _ { \chi } \cdot \mathbb { D } [ [ \Gamma _ { K } ] ] = \left( \mu _ { \mathfrak { f } } ^ { \chi } \right) .
$$

Here the measure $\mu _ { \mathrm { f } }$ is defined as in Theorem 2.1.

Lemma 2.3. Let $E / K$ be an elliptic curve associated with to a Hecke character $\varphi , p$ splits in $K$ and write $p { \mathcal { O } } _ { K } = { \mathfrak { p } } { \mathfrak { p } } ^ { * }$ .Let $\varphi _ { 0 }$ beaHecke character over $K$ unramified at $\mathfrak { p }$ .Let $\Omega _ { E }$ and $\Omega _ { 0 }$ be $\mathfrak { p }$ -minimal periods of $E$ and $\varphi _ { 0 }$ ， respectively. Then

$$
{ \mathrm { o r d } } _ { p } \left( { \frac { \Omega _ { E } \cdot \tau ( \varphi _ { \mathfrak { p } } , \psi _ { p } ) } { \Omega _ { 0 } } } \right) = 0 .
$$

Proof.This follows from Stickelberger's theorem on prime ideal decomposition of Gauss sum. In fact, for ${ \mathfrak { p } } + w = w _ { K }$ ， $E$ has $\mathfrak { p }$ -minimal Weierstrass equation of form

$$
E : y ^ { 2 } = x ^ { 3 } + a _ { 2 } x ^ { 2 } + a _ { 4 } x + a _ { 6 } , \qquad a _ { 2 } , a _ { 4 } , a _ { 6 } \in K ^ { \times } \cap { \mathcal O } _ { \mathfrak p } .
$$

Note that for $w = 4 , 6$ ， we may-and do- take form $y ^ { 2 } = x ^ { 3 } + a _ { 4 } x$ ， $y ^ { 2 } = x ^ { 3 } + a _ { 6 }$ , respectively. Then there is an elliptic curve $E ^ { \prime }$ over $K$ which has good reduction at $\mathfrak { p }$ .Let $\varphi ^ { \prime }$ be its associated Hecke character. Then $\epsilon = { \varphi \varphi ^ { \prime } } ^ { - 1 } : \mathbb { A } _ { K } ^ { \times } / K ^ { \times } \to \mathcal { O } _ { K } ^ { \times }$ (also viewed as a Galois character via class feld theory) is of form $\chi ( \sigma ) = \sigma ( d ^ { 1 / w } ) / d ^ { 1 / w }$ for an element $d \in K ^ { \times } / K ^ { \times w }$ . Then the twist $E ^ { \prime }$ has $\mathfrak { p }$ -good model

$$
E ^ { \prime } : \left\{ \begin{array} { l l } { y ^ { 2 } = x ^ { 3 } + d a _ { 2 } x ^ { 2 } + d ^ { 2 } a _ { 4 } x + d ^ { 3 } a _ { 6 } , \qquad } & { \mathrm { i f ~ } w = 2 , } \\ { y ^ { 2 } = x ^ { 3 } + d a _ { 4 } x , \qquad } & { \mathrm { i f ~ } w = 4 , } \\ { y ^ { 2 } = x ^ { 3 } + d a _ { 6 } , \qquad } & { \mathrm { i f ~ } w = 6 . } \end{array} \right.
$$

It is easy to check the $\Omega _ { E _ { 0 } } = d ^ { 1 / w } \cdot \Omega _ { E }$ Let $\omega : \mathcal { O } _ { \mathfrak { p } } ^ { \times } \longrightarrow \mu _ { w } \subset K$ be the character characterized by $\omega ( a ) \equiv a$ mod $\mathfrak { p }$ and let $\chi = \omega ^ { - ( p - 1 ) / w }$ Then $\epsilon _ { \mathfrak { p } } = \chi ^ { k }$ for some $k \in \mathbb { Z } / w \mathbb { Z }$ Let $\kappa _ { \mathfrak { p } } \cong \mathbb { F } _ { p }$ be the residue feld of $K _ { \mathfrak { p } }$ .By Stickelberger's theorem,the Gauss sum $\begin{array} { r } { g ( \epsilon _ { \mathfrak { p } } , \psi ) : = - \sum _ { a \in \kappa _ { \mathfrak { p } } ^ { \times } } \epsilon _ { \mathfrak { p } } ( a ) \psi ( a ) } \end{array}$ has $\mathfrak { p }$ -valuation （204号 $\{ k / w \}$ . It remains to show that $k = { \mathrm { o r d } } _ { \mathfrak { p } } ( d )$ . Note that for any $u \in \mathcal { O } _ { \mathfrak { p } } ^ { \times }$ ， $K _ { \mathfrak { p } } ( u ^ { 1 / w } )$ is unramified over $K _ { \mathfrak { p } }$ . Thus it is equivalent to show that for any uniformizer $\pi$ of $K _ { \mathfrak { p } }$ ，

$$
\sigma _ { u } ( \pi ^ { 1 / w } ) / \pi ^ { 1 / w } \equiv u ^ { - ( p - 1 ) / w } \bmod \mathfrak { p } , \qquad \forall u \in \mathcal { O } _ { \mathfrak { p } } ^ { \times } .
$$

3ut it is easy to see this by using local class field theory for formal group associated to $x ^ { p } - \pi x$

For general Hecke character $\varphi _ { 0 }$ over $K$ unramified at $\mathfrak { p }$ (not necessarily $K$ -valued) and $\Omega _ { 0 }$ its $\mathfrak { p }$ -minimal period, it is easy to see that $\mathrm { o r d } _ { \mathfrak { p } } ( \Omega _ { 0 } / \Omega _ { E _ { 0 } } ) = 0$ ：

Let $\chi _ { \mathrm { c y c } , K } : \mathcal { G } \to \mathbb { Z } _ { p } ^ { \times }$ be the $p$ -adic cyclotomic character defined by the action on $p$ -th power roots of unity. Define

$$
\mathcal { L } _ { \varphi _ { E } } ( s ) : = \mu _ { \mathfrak { f } _ { E } ^ { ( \mathfrak { p } ) } } ( \varphi _ { E } \chi _ { \mathrm { c y c } , K } ^ { 1 - s } ) , \qquad \forall s \in \mathbb { Z } _ { p } .
$$

Rubin's two variable main conjecture implies the following theorem.

Theorem 2.4.Let $E$ be an elliptic curve defined over $K$ with CM by $K$ and $\varphi$ its associated Hecke character. Let $p \nmid w _ { K }$ be a prime split in $K$ and $p \mathcal { O } _ { K } = \mathfrak { p } \mathfrak { p } ^ { * }$ .Let $r$ be the ${ \mathcal { O } } _ { K }$ -rank of $E ( K )$ . Assume that II $( E / K ) ( p )$ is finite and the $p$ -adic height pairing of $E$ over $K$ is non-degenerate. Then

(1）both $\mathcal { L } _ { \varphi } ( s )$ and $\mathcal { L } _ { \overline { { \varphi } } } ( s )$ have a zero at $s = 1$ of exact order $r$ (2)the $p$ -adic $B S D$ conjecture holds for $E / K$ ：

$$
\mathrm { o r d } _ { p } \big ( | \mathrm { I I I } ( E / K ) | \big ) = \mathrm { o r d } _ { p } \left( \frac { \mathcal { L } _ { \varphi } ^ { ( r ) } ( 1 ) \mathcal { L } _ { \overline { { \varphi } } } ^ { ( r ) } ( 1 ) } { R _ { p } ( E / K ) } \cdot \prod _ { v | p } \Big ( ( 1 - \varphi _ { E } ( v ) ) \Big ( 1 - \overline { { \varphi _ { E } ( v ) } } \Big ) ^ { - 2 } \right)
$$

provided the assumption that if $w _ { K } = 4$ or6 then $E$ has bad reduction at both $\mathfrak { p }$ and $\mathfrak { p } ^ { * }$ or good reductionatboth $\mathfrak { p }$ and ${ \mathfrak { p } } ^ { * }$ ：

Moreover, if $E$ is defined over $\mathbb { Q }$ ， then we have

$$
\mathrm { o r d } _ { p } \big ( | \mathrm { I I I } ( E / \mathbb { Q } ) | \big ) = \mathrm { o r d } _ { p } \left( \frac { \mathcal { L } _ { \varphi } ^ { ( r ) } ( 1 ) } { R _ { p } ( E / \mathbb { Q } ) } \cdot \prod _ { v | p } \Big ( ( 1 - \varphi _ { E } ( v ) ) \Big ( 1 - \overline { { \varphi _ { E } ( v } } \Big ) \Big ) ^ { - 1 } \right) .
$$

Proof. Let $\epsilon$ be a Galois character over $K$ valued in ${ \mathcal { O } } _ { K } ^ { \times }$ such that $\varphi ^ { \prime } = \varphi \epsilon$ is unramified at both $\mathfrak { p }$ and ${ \mathfrak { p } } ^ { * }$ Let $E ^ { \prime }$ be the elliptic curve over $K$ as $\epsilon$ -twist of $E$ so that $\varphi ^ { \prime }$ as its Hecke character.Then $E ^ { \prime }$ has good reduction above $p$ .Let $F$ be the abelian extension over $K$ cut by $\epsilon$ ,then $[ F : K ] | w _ { K }$ .Moreover, $E$ and （204号 $E ^ { \prime }$ are isomorphism over $F$ ， $E ^ { \prime } ( F ) ^ { ( \epsilon ) } \cong E ( K )$ ,and $\mathrm { I I I } ( E ^ { \prime } / F ) [ p ^ { \infty } ] ^ { ( \epsilon ) } \cong \mathrm { I I I } ( E / K ) [ p ^ { \infty } ]$ .Let $F _ { 0 } = F ( E [ p ] )$ （20 and $\chi : \mathrm { G a l } ( F _ { 0 } ) / K ) \to { \mathcal { O } } _ { \mathfrak { p } } ^ { \times }$ be the character giving the action on $E [ p ]$

Let $F _ { \infty } = F ( { \cal E } [ p ^ { \infty } ] )$ ．Let $M _ { \infty , \mathfrak { p } }$ be the maximal $p$ -extension over $F _ { \infty }$ unramified outside $\mathfrak { p }$ and （204号 $X _ { \infty , \mathfrak { p } } = \operatorname { G a l } ( M _ { \infty , \mathfrak { p } } / F _ { \infty } )$ .Denote by $U _ { \infty }$ and $C _ { \infty } \subset U _ { \infty }$ the $\Lambda = \mathbb { Z } [ [ \operatorname { G a l } ( F _ { \infty } / K ) ] ]$ -modules of the principal local units at $\mathfrak { p }$ and elliptic units for the extension $F _ { \infty }$ (defined as in [14], $\ S 4$ ). Rubin's two variable main conjecture, together Yager [18], says that

$$
\mathrm { C h a r } _ { \Lambda } ( X _ { \infty , \mathfrak { p } } ^ { \chi } ) \mathbb { D } [ [ \mathrm { G a l } ( F _ { \infty } / F _ { 0 } ) ] ] = \left( \mu _ { f _ { E } ^ { ( p ) } , \mathfrak { p } } ^ { \chi } \right) ,
$$

where for an integral ideal $\mathfrak { g }$ of $K$ prime to $p$ ，the measure $\mu _ { \mathfrak { g } }$ is given as in Theorem 2.1.Let $\mathrm { S e l } ( F _ { \infty } , E [ { \mathfrak { p } } ^ { \infty } ] )$ be the $\mathfrak { p }$ -Selmer group of $E$ over $F _ { \infty }$ and $\mathrm { S e l } ( F _ { \infty } , E [ { \mathfrak { p } } ^ { \infty } ] ) ^ { \vee }$ its Pontryajin dual. Then $\mathrm { S e l } ( F _ { \infty } , E [ \mathfrak { p } ^ { \infty } ] ) ^ { \vee }$ is a finitely generated $\Lambda$ -torsion module and

$$
\operatorname { C h a r } _ { \Lambda } ( \operatorname { S e l } ( F _ { \infty } , E [ { \mathfrak { p } } ^ { \infty } ] ) ^ { \vee } ) = \iota _ { \mathfrak { p } } \operatorname { C h a r } ( X _ { \infty , \mathfrak { p } } ^ { \chi } ) ,
$$

where $\iota _ { \mathfrak { p } } : \Lambda \to \Lambda , \gamma \longrightarrow \kappa _ { \mathfrak { p } } ( \gamma ) \gamma$ for any $\gamma \in \operatorname { G a l } ( F _ { \infty } / K )$ and $\kappa _ { \mathfrak { p } }$ is the character of $\operatorname { G a l } ( F _ { \infty } / K )$ giving the action on $E [ { \mathfrak { p } } ^ { \infty } ]$ . Similarly, we also have that

$$
\begin{array} { r } { \mathrm { S h a r } _ { \Lambda } ( X _ { \infty , \mathbf { p } ^ { - } } ^ { x } ) \mathbb { D } [ [ \mathrm { G a l } ( F _ { \infty } / F _ { 0 } ) ] ] = \left( \mu _ { f _ { E } ^ { ( p ) } , \mathbf { p } ^ { * } } ^ { x } \right) , \qquad \mathrm { C h a r } _ { \Lambda } ( \mathrm { S e l } ( F _ { \infty } , E [ \mathbf { p } ^ { * \infty } ] ) ^ { \vee } ) = \iota _ { \mathbf { p } ^ { * } } \mathrm { C h a r } ( X _ { \infty , \mathbf { p } ^ { * } } ^ { x } ) . } \end{array}
$$

Let $F _ { \mathrm { c y c } }$ be the cyclotomic $\mathbb { Z } _ { p }$ extension, and $\Lambda _ { \mathrm { c y c } } = \mathbb { Z } _ { p } [ [ \operatorname { G a l } ( F _ { \mathrm { c y c } } / K ) ] ] \cong \Delta \times \Gamma$ where $\Delta = \operatorname { G a l } ( F / K )$ （20 and $\Gamma = \operatorname { G a l } ( F _ { \mathrm { c y c } } / F )$ Let $\mathrm { S e l } ( F _ { \mathrm { c y c } } , E [ p ^ { \infty } ] )$ denote the $p$ -Selmer group of $E$ over $F _ { \mathrm { c y c } }$ and then its Pontryagin dual $\mathrm { S e l } ( F _ { \mathrm { c y c } } , E [ p ^ { \infty } ] ) ^ { \vee }$ is a finitely generated torsion $\Lambda _ { \mathrm { c y c } }$ -module. We have

$$
\begin{array} { r l } & { \mathrm { S e l } ( F _ { \mathrm { c y c } } , E [ p ^ { \infty } ] ) = \mathrm { S e l } ( F _ { \mathrm { c y c } } , E [ p ^ { \infty } ] ) \oplus \mathrm { S e l } ( F _ { \mathrm { c y c } } , E [ p ^ { * \infty } ] ) } \\ & { \qquad = \mathrm { H o m } ( X _ { \infty , \mathfrak { p } } , E [ { \mathfrak { p } } ^ { \infty } ] ) ^ { \mathrm { G a l } ( F _ { \infty } / F _ { \mathrm { c y c } } ) } \oplus \mathrm { H o m } ( X _ { \infty , \mathfrak { p } ^ { * } } , E [ { \mathfrak { p } } ^ { * \infty } ] ) ^ { \mathrm { G a l } ( F _ { \infty } / F _ { \mathrm { c y c } } ) } } \end{array}
$$

Here the second equality is given [10] Proposition (1.3), Theorem (1.6) and Lemma (1.1),the last one is by the same reason as [14] Theorem 12.2. It follows that

$$
\begin{array} { r } { \mathrm { C h a r } _ { \Lambda _ { \mathrm { c y c } } } ( \mathrm { S e l } ( F _ { \mathrm { c y c } } , E [ p ^ { \infty } ] ) ^ { \vee } ) \mathbb { D } [ [ \mathrm { G a l } ( F _ { \mathrm { c y c } } / F ) ] ] = \left( \iota _ { \mathfrak { p } } \mu _ { f _ { E } ^ { ( p ) } , \mathfrak { p } } ^ { \chi } \iota _ { \mathfrak { p } ^ { * } } \mu _ { f _ { E } ^ { ( p ) } , \mathfrak { p } ^ { * } } ^ { \chi } \right) . } \end{array}
$$

Denote by $\chi _ { \mathrm { c y c } }$ the cyclotomic character. Let $f _ { E }$ be a generater of $\begin{array} { r } { \mathrm { C h a r } _ { \mathbb { Z } _ { p } [ [ \Gamma ] ] } ( \mathrm { S e l } ( F _ { \mathrm { c y c } } , E [ p ^ { \infty } ] ) ^ { \vee } ) ^ { \Delta } } \end{array}$ and define

$$
\begin{array} { r } { \mathcal { L } ( s ) = \chi _ { \mathrm { c y c } } ^ { 1 - s } ( f _ { E } ) , \qquad \forall s \in \mathbb { Z } _ { p } . } \end{array}
$$

Then we have $\mathcal { L } ( s ) = u ( s ) \mathcal { L } _ { \varphi _ { E } } ( s ) \mathcal { L } _ { \overline { { \varphi _ { E } } } } ( s )$ for some function $u ( s )$ valued in $\mathbb { D } ^ { \times }$

Note that $E$ over $F$ has good reduction above $p$ . Employing the descend argument as in [15], noting that the“descent diagram” in [15] \$7 for $E$ over $F$ is $\Delta = \operatorname { G a l } ( F / K )$ -equivariant,and taking $\Delta$ -invariant part,we have

Proposition 2.5. Let $r : = \mathrm { r a n k } \mathcal { O } _ { K } E ( K )$ . Assume that I $\operatorname { I I } ( E / K ) [ p ^ { \infty } ]$ is finite and $p$ -adic height pairing is non-degenerate on $E ( K )$ .Then $\mathcal { L } ( s )$ has exact vanishing order $2 r$ at $s = 1$ and if let ${ \mathcal { L } } ^ { * } ( 1 )$ denote its leading coefficient at $s = 1$ ，

$$
\frac { \mathcal { L } ^ { * } ( 1 ) } { R _ { p } ( E / K ) } \sim | \mathrm { I I I } ( E / K ) | \cdot \left| \prod _ { v | p } H ^ { 1 } ( \mathrm { G a l } ( F ( \mu _ { p ^ { \infty } } ) / F ) , E ( F ( \mu _ { p ^ { \infty } } ) \otimes _ { K } K _ { v } ) ) ^ { \Delta } \right| ^ { 2 } .
$$

Here for any $a , b \in \mathbb { C } _ { p } ^ { \times }$ ,write $a \sim b$ if $\mathrm { o r d } _ { p } ( a / b ) = 0$

The follow lemma will complete the proof.

Lemma 2.6. Let $v _ { 0 } = { \mathfrak { p } }$ or ${ \mathfrak { p } } ^ { * }$ . Assume that if $w _ { K } = 4$ or 6 then $E$ has bad reduction at both $\mathfrak { p }$ and ${ \mathfrak { p } } ^ { * }$ orgood reductionat both $\mathfrak { p }$ and ${ \mathfrak { p } } ^ { * }$ .Then

$$
\big | H ^ { 1 } ( \mathrm { G a l } ( F ( \mu _ { p ^ { \infty } } ) / F ) , E ( F ( \mu _ { p ^ { \infty } } ) \otimes _ { K } K _ { v _ { 0 } } ) ) ^ { \Delta } \big | \sim ( 1 - \varphi _ { E } ( v _ { 0 } ) ) ( 1 - \overline { { \varphi _ { E } ( v _ { 0 } ) } } ) .
$$

The remain part of this section will devote to the proof of this lemma.Note that [15] handled the case where $E$ has good reduction above $p$ .We now assume that $E$ has bad reduction either at $\mathfrak { p }$ orat ${ \mathfrak { p } } ^ { * }$ . The isomorphism between $E$ and $E ^ { \prime }$ over $F$ gives rise to an isomorphism

$$
H ^ { 1 } \left( \mathrm { G a l } ( F ( \mu _ { p ^ { \infty } } ) / F ) , E ( F ( \mu _ { p ^ { \infty } } ) \otimes _ { K } K _ { v _ { 0 } } ) \right) ^ { \perp } \stackrel { \sim } { \longrightarrow } H ^ { 1 } \left( \mathrm { G a l } ( F ( \mu _ { p ^ { \infty } } ) / F ) , E ^ { \prime } ( F ( \mu _ { p ^ { \infty } } ) \otimes _ { K } K _ { v _ { 0 } } ) \right) ^ { \epsilon } .
$$

We will need Proposition 2 in [15] that for any elliptic curve $A$ over a local field $k$ with good ordinary reduction and let $\widetilde { A }$ denote its reduction over the the residue feld $\kappa$ of $k$ ，we have

$$
| H ^ { 1 } \left( \mathrm { G a l } ( k ( \mu _ { p ^ { \infty } } ) / k ) , A ( k ( \mu _ { p ^ { \infty } } ) ) \right) = | \widetilde A ( \kappa ) [ p ^ { \infty } ] | .
$$

Let $w | v _ { 0 }$ be a place of $F$ above $v _ { 0 }$ and $\kappa _ { w } / \kappa _ { v _ { 0 } }$ be the residue fields of $F _ { w }$ and $K _ { v _ { 0 } }$ respectively, we have

$$
| E ^ { \prime } ( \kappa _ { w } ) | \sim \left( 1 - \varphi _ { E ^ { \prime } } ( v _ { 0 } ) ^ { [ \kappa _ { w } : \kappa _ { v _ { 0 } } ] } \right) \left( 1 - \overline { { \varphi _ { E ^ { \prime } } ( v _ { 0 } ) } } ^ { [ \kappa _ { w } : \kappa _ { v _ { 0 } } ] } \right) .
$$

If $w _ { K } = 2$ ,then $F / K$ is a quadratic extension. If $E$ is ramified at $v _ { 0 }$ ,then $F / K$ is ramified at $v _ { 0 }$ and let $w$ be the unique place of $F$ above $v _ { 0 }$ ，we have $\kappa _ { w } = \kappa _ { v _ { 0 } }$ and thus

$$
\begin{array} { l } { \displaystyle \big | H ^ { 1 } \left( \mathrm { G a l } ( F ( \mu _ { p ^ { \infty } } ) / F ) , E ^ { \prime } ( F ( \mu _ { p ^ { \infty } } ) \otimes _ { K } K _ { v _ { 0 } } ) \right) ^ { \epsilon } \big | = \frac { \big | H ^ { 1 } \left( \mathrm { G a l } ( F _ { w } ( \mu _ { p ^ { \infty } } ) / F _ { w } ) , E ^ { \prime } ( F _ { w } ( \mu _ { p ^ { \infty } } ) ) \right) \big | } { \big | H ^ { 1 } \left( \mathrm { G a l } ( K _ { v _ { 0 } } ( \mu _ { p ^ { \infty } } ) / K _ { v _ { 0 } } ) , E ^ { \prime } ( K _ { v _ { 0 } } ( \mu _ { p ^ { \infty } } ) ) \right) \big | } } \\ { \displaystyle \qquad = \frac { \big | \widetilde { E ^ { \prime } } ( \kappa _ { w } ) \big | } { \big | \widetilde { E ^ { \prime } } ( \kappa _ { v _ { 0 } } ) \big | } = 1 . } \end{array}
$$

If $E$ has good reduction at $v _ { 0 }$ ,then $F / K$ is unramified at $v _ { 0 }$ . If $v _ { 0 }$ is split over $F$ ,then $F \otimes _ { K } K _ { v _ { 0 } } \cong K _ { v _ { 0 } } ^ { 2 }$ and $\epsilon _ { v _ { 0 } } = 1 \$ . It is easy to see

$$
\big | H ^ { 1 } \left( \mathrm { G a l } ( F ( \mu _ { p ^ { \infty } } ) / F ) , E ^ { \prime } ( F ( \mu _ { p ^ { \infty } } ) \otimes _ { K } K _ { v _ { 0 } } ) \right) ^ { \epsilon } \big | \sim ( 1 - \varphi _ { E } ( v _ { 0 } ) ) ( 1 - \overline { { \varphi _ { E } ( v _ { 0 } ) } } ) .
$$

f $v _ { 0 }$ is inert in $F$ ,let $w$ be the unique prime of $F$ above $v _ { 0 }$ . Note that $\varphi _ { v _ { 0 } } ^ { \prime } = \varphi _ { v _ { 0 } } \epsilon _ { v _ { 0 } }$ and $\epsilon ( v _ { 0 } ) = - 1$

$$
\begin{array} { r } { ( \mathrm { G a l } ( F ( \mu _ { p ^ { \infty } } ) / F ) , E ^ { \prime } ( F ( \mu _ { p ^ { \infty } } ) \otimes _ { K } K _ { v _ { 0 } } ) ) ^ { \varepsilon } | = \frac { | H ^ { 1 } ( \mathrm { G a l } ( F _ { w } ( \mu _ { p ^ { \infty } } ) / F _ { w } ) , E ^ { \prime } ( F _ { w } ( \mu _ { p ^ { \infty } } ) ) ) | } { | H ^ { 1 } ( \mathrm { G a l } ( K _ { v _ { 0 } } ( \mu _ { p ^ { \infty } } ) / K _ { v _ { 0 } } ) , E ^ { \prime } ( K _ { v _ { 0 } } ( \mu _ { p ^ { \infty } } ) ) ) | } = \frac { | \widehat { E ^ { \prime } } ( \kappa _ { w } ) | } { | \widehat { E ^ { \prime } } ( \kappa _ { v _ { 0 } } ) } } \\ { \sim \frac { ( 1 - ( \varphi \epsilon ) ( v _ { 0 } ) ^ { 2 } ) ( 1 - \overline { { \varphi \epsilon ( v _ { 0 } ) } } ^ { 2 } ) } { ( 1 - ( \varphi \epsilon ) ( v _ { 0 } ) ) ( 1 - \overline { { \varphi \epsilon ( v _ { 0 } ) } } ) } = ( 1 - \varphi ( v _ { 0 } ) ) ( 1 - \overline { { \varphi ( v _ { 0 } ) } } ) } \end{array}
$$

If $w _ { K } = 4$ or $6$ ，by our assumption, $v _ { 0 }$ must be ramified over $F$ and $\epsilon$ is non-trivial on its inertia subgroup. The proof is now similar to the previous ramified case.

# 3. $\infty$ -ADIC AND $p$ -ADIC GROSS-ZAGIER FORMULAE

Let $E$ be an elliptic curve over $\mathbb { Q }$ of conductor $N$ and $\phi$ its associated newform. Let $p$ be a prime where $E$ is potential good ordinary or potential semi-stable. Let $\alpha : \mathbb { Q } _ { p } ^ { \times } \longrightarrow \mathbb { Z } _ { p } ^ { \times }$ be the character character contained in the representation $( V _ { p } E ) ^ { s s }$ of $G _ { \mathbb { Q } _ { p } }$ such that $\alpha | _ { \mathbb { Z } _ { p } ^ { \times } }$ is of finite order.

Let $\mathcal { K }$ be an imaginary quadratic field such that $\epsilon ( E / \mathcal { K } ) = - 1$ and $p$ splits in $\mathcal { K }$ . Let $\Gamma _ { \ / K }$ be the Galois group of the $\mathbb { Z } _ { p } ^ { 2 }$ -extension over $\mathcal { K }$ . Recall that [4] there exists a $p$ -adic measure $\mu _ { E / \mathcal { K } }$ on $\Gamma _ { \ / K }$ such that for any finite order character $\chi$ of $\Gamma _ { \ / { K } }$ （20

$$
\chi ( \mu _ { E / \mathcal K } ) = \frac { L ^ { ( p ) } ( 1 , \phi , \chi ) } { 8 \pi ^ { 2 } ( \phi , \phi ) } \cdot \prod _ { w \mid p } Z _ { w } ( \chi _ { w } , \psi _ { w } ) ,
$$

where $( \phi , \phi )$ is the Peterson norm of $\phi$

$$
( \phi , \phi ) = \iint _ { \Gamma _ { 0 } ( N ) \backslash \mathcal { H } } | \phi ( z ) | ^ { 2 } d x d y , \qquad z = x + i y ,
$$

and for each prime $w | p$ of $\mathcal { K }$ ,let $\alpha _ { w } = \alpha \circ \Nu _ { \mathcal { K } _ { w } / \mathbb { Q } _ { p } }$ and $\psi _ { w } = \psi _ { p } \circ \mathrm { T r } _ { \mathcal { K } _ { w } / \mathbb { Q } _ { p } }$ ,and let $\varphi _ { w }$ be a uniformizer of ${ { \mathcal { K } } _ { w } }$ ，then

$$
Z _ { w } ( \chi _ { w } , \psi _ { w } ) = \left\{ \begin{array} { l l } { ( 1 - \alpha _ { w } \chi _ { w } ( \varpi _ { w } ) ^ { - 1 } ) ( 1 - \alpha _ { w } \chi _ { w } ( \varpi _ { w } ) p ^ { - 1 } ) ^ { - 1 } , \qquad } & { \mathrm { i f ~ } \alpha _ { w } \chi _ { w } \mathrm { ~ i s ~ u n r a m i f i e d , } , } \\ { p ^ { n } \tau ( ( \alpha _ { w } \chi _ { w } ) ^ { - 1 } , \psi _ { w } ) , } & { \mathrm { i f ~ } \alpha _ { w } \chi _ { w } \mathrm { ~ i s ~ o f ~ c o n d u c t o r ~ } n \geq 0 . } \end{array} \right.
$$

The following lemma will be used to prove our main theorem.

Lemma 3.1. Let $E$ be an elliptic curve over $\mathbb { Q }$ with CM by an imaginary quadratic field $K$ . Assume $p$ is also split in $K$ write $p \mathcal { O } _ { K } = \mathfrak { p } \mathfrak { p } ^ { * }$ with $\mathfrak { p }$ induced by $\iota _ { p }$ ，i.e.identify $K _ { \mathfrak { p } }$ with $\mathbb { Q } _ { p }$ and the non-trivial element $\tau \in \operatorname { G a l } ( K / \mathbb { Q } )$ induces an isomorphism on $\mathbb { A } _ { K }$ and thus $\tau : K _ { \mathfrak { p } ^ { * } } \ : \tilde {  } \ : K _ { \mathfrak { p } } = \mathbb { Q } _ { p }$ .Let $\varphi$ be its associated Hecke character. Then we have $\alpha = \varphi _ { \mathfrak { p } ^ { * } } \circ \tau ^ { - 1 }$ and $( \alpha ^ { - 1 } \chi _ { \mathrm { c y c } } ) ( x ) = \varphi _ { \mathfrak { p } } ( x ) x ^ { - 1 }$ for any $x \in \mathbb { Q } _ { p } ^ { \times }$ Moreover,forany place wlp of $\mathcal { K }$ . any finiteorder character $\nu : \widehat { \mathbb { Q } } ^ { \times } / \mathbb { Q } ^ { \times } \widehat { \mathbb { Z } } ^ { \times ( p ) } \mathbb { Z } _ { p , \mathrm { t o r } } ^ { \times } \to \mu _ { p ^ { \infty } }$ viewed as character on $\Gamma _ { K }$ by compose with norm

$$
Z _ { w } ( { \alpha } _ { w } { \nu } _ { w } , { \psi } ) = { \tau } ( { \varphi } _ { \mathfrak { p } } { \nu } _ { p } ^ { - 1 } , { \psi } ) \cdot \frac { 1 - ( { \varphi } _ { \mathfrak { p } } { \nu } ^ { - 1 } ) ( p ) p ^ { - 1 } } { 1 - ( { \varphi } _ { \mathfrak { p } } { \nu } _ { p } ^ { - 1 } ) ( p ) p ^ { - 1 } } .
$$

Proof. The claim follws from the relations $\varphi \overline { { \varphi } } = | \mathbf { \Sigma } | _ { \mathbb { A } _ { K } ^ { ( \infty ) } } ^ { - 1 }$ A(∞） and  =.

Let $\chi _ { \mathrm { c y c , } \mathcal { K } } : \Gamma \kappa \to \mathbb { Z } _ { p } ^ { \times }$ denote the $p$ -adic cyclotomic character of $G _ { K }$ .Let $\chi$ be an anticyclotomic character. Define $\mathcal { L } _ { E / \kappa , \chi }$ to be the $p$ -adic L-function

$$
\begin{array} { r } { \mathcal { L } _ { E / \mathcal { K } , \chi } ( s ) = \mu _ { E / \mathcal { K } } ( \chi \chi _ { \mathrm { c y c } , \mathcal { K } } ^ { s - 1 } ) , \quad s \in \mathbb { Z } _ { p } . } \end{array}
$$

For trivial X, we write LE/x for LE/K,x

Theorem 3.2 (See [19] and [4]). Let $E$ be an elliptic curve over $\mathbb { Q }$ and $\mathcal { K }$ an imaginary quadratic field Let $p$ be a potentially good ordinary prime for $E$ and split over $\mathcal { K }$ . Assume that $\epsilon ( E / \mathcal { K } ) = - 1$ . Then

$$
\frac { \mathcal { L } _ { E / K , \chi } ^ { \prime } ( 1 ) } { R _ { p } ( E / K , \chi ) } \cdot \frac { L _ { p } ( E / K , \chi , 1 ) } { \prod _ { w | p } Z _ { w } ( \chi _ { w } , \psi _ { w } ) } = \frac { L ^ { \prime } ( E / K , \chi , 1 ) } { R _ { \infty } ( E / K , \chi ) \cdot 8 \pi ^ { 2 } ( \phi , \phi ) } .
$$

Here $L _ { p } ( E / \mathcal { K } , \chi , 1 )$ is the Euler factor at $p$ . In particular, $\mathcal { L } _ { E / \kappa } ^ { \prime } ( 1 ) = 0$ if and only if $L ^ { \prime } ( E / K , 1 ) = 0$

Proof. Let $B$ be an indefinite quaternion algebra over $\mathbb { Q }$ ramified exactly at the places $v$ of $\mathbb { Q }$ where （204 $\epsilon _ { v } ( E / K , \chi ) \eta _ { v } ( - 1 ) = - 1$ . It is known that there exists a Shimura curve $X$ over $\mathbb { Q }$ (with suitable level) and a non-constant morphism $f : X \to E$ over $\mathbb { Q }$ mapping a divisor in Hodge class to the identity of $E$ （20 such that its corresponding Heegner cycle $P _ { \chi } ( f )$ is non-trivial if and only if $L ^ { \prime } ( 1 , \phi , \chi ) \neq 0$ by Theorem 1.2 in[19],and if and onlyif $\mathcal { L } _ { E / K , \chi } ^ { \prime } ( 1 ) \neq 0$ by Theorem B in [4]. Thus $L ^ { \prime } ( E / \mathcal { K } , \chi , 1 ) = 0$ if and only if $\mathcal { L } _ { E / K , \chi } ^ { \prime } ( 1 ) = 0$ ．

Now assume that $L ^ { \prime } ( E / K , 1 ) \neq 0$ . By an argument of Kolyvagin, we know that $( E ( K _ { x } ) \otimes \mathcal { O } _ { x } ) ^ { \chi }$ is of ${ \mathcal { O } } _ { \chi }$ -rank one,

$$
\frac { \widehat { h } _ { \infty } ( P _ { \chi } ( f ) ) } { R _ { \infty } ( E / \mathcal { K } , \chi ) } = \frac { \widehat { h } _ { p } ( P _ { \chi } ( f ) ) } { R _ { p } ( E / \mathcal { K } , \chi ) } \in \overline { { \mathbb { Q } } } ^ { \times } .
$$

By [19] theorem 1.2,

$$
\frac { L ^ { \prime } ( E / \mathcal { K } , \chi , 1 ) } { R _ { \infty } ( E / \mathcal { K } , \chi ) \cdot 8 \pi ^ { 2 } ( \phi , \phi ) } = \frac { \widehat { h } _ { N T } ( P _ { \chi } ( f ) ) } { R _ { \infty } ( E / \mathcal { K } , \chi ) } \frac { 4 L ( 1 , \eta ) } { \pi c _ { \mathcal { K } } } \frac { L ( 1 , \pi , \mathrm { a d } ) } { 8 \pi ^ { 3 } ( \phi , \phi ) } \alpha ^ { - 1 } ( f , \chi )
$$

and by [4] theorem $\mathrm { B }$ (with our definition of $\mathcal { L } _ { E / \kappa , \chi }$ ）

$$
\frac { \mathcal { L } _ { E / \mathcal { K } , \chi } ^ { \prime } ( 1 ) } { R _ { p } ( E / \mathcal { K } , \chi ) } = \frac { h _ { p } ( P _ { \chi } ( f ) ) } { R _ { p } ( E / \mathcal { K } , \chi ) } \frac { 4 L ( 1 , \eta ) } { \pi c _ { \mathcal { K } } } \frac { \prod _ { w | p } Z _ { w } ( \chi _ { w } , \psi _ { w } ) } { L _ { p } ( E / \mathcal { K } , \chi , 1 ) } \frac { L ( 1 , \pi , \mathrm { a d } ) } { 8 \pi ^ { 3 } ( \phi , \phi ) } \alpha ^ { - 1 } ( f , \chi ) ,
$$

where the $\alpha ( f , \chi ) \in \overline { { \mathbb { Q } } } ^ { \times }$ . The theorem follows.

Now we give an explicit form of $p$ -adic Gross-Zagier formula as an application. Let $c$ be the conductol of $\chi$ . Assume the following Heegner hypothesis holds:

(1) $( c , N ) = 1$ ,and no prime divisor $q$ of $N$ is inert in $\mathcal { K }$ ,and also $q$ must be split in $\mathcal { K }$ if $q ^ { 2 } | N _ { \mathbf { \alpha } }$ (2) $\chi ( [ \mathfrak { q } ] ) \ne a _ { q }$ for any prime $q | ( N , D )$ ，where $\mathfrak { q }$ is the unique prime ideal of ${ { \mathcal { O } } _ { \kappa } }$ above $q$ and $[ { \mathfrak { q } } ]$ is its class in $\mathrm { P i c } ( { \mathcal { O } } _ { c } )$ ：

Let $X _ { 0 } ( N )$ be the modular curve over $\mathbb { Q }$ ,whose $\mathbb { C }$ -points parametrize isogenies $E _ { 1 } \to E _ { 2 }$ between elliptic curves over $\mathbb { C }$ whose kernel is cyclic of order $N$ . By the Heegner condition,there exists a proper ideal $\mathcal { N }$ of $\mathcal { O } _ { c }$ such that $\mathcal { O } _ { c } / \mathcal { N } \cong \mathbb { Z } / N \mathbb { Z }$ . For any proper ideal $\mathfrak { a }$ of $\mathcal { O } _ { c }$ ,let $P _ { \mathfrak { a } } \in X _ { 0 } ( N )$ be the point representing the isogeny $\mathbb { C } / { \mathfrak { a } } \to \mathbb { C } / { \mathfrak { a } }  { \mathcal { N } } ^ { - 1 }$ ，which is defined over the ring class field $\boldsymbol { H } _ { c }$ over $\mathcal { K }$ of conductor $c$ ，and only depends on the class of $\mathfrak { a }$ in $\mathrm { P i c } ( { \mathcal { O } } _ { c } )$ .Let $J _ { 0 } ( N )$ be the Jacobian of $X _ { 0 } ( N )$ .Let $f : X _ { 0 } ( N ) \to E$ be a modular parametrization mapping the cusp $\infty$ at infinity to the identity $O \in E$ . Denote by $\deg f$ the degree of the morphism $f$ . Define the Heegner divisor to be

$$
P _ { \chi } ( f ) : = \sum _ { [ \mathfrak { a } ] \in \operatorname { P i c } ( \mathcal { O } _ { c } ) } f ( P _ { \mathfrak { a } } ) \otimes \chi ( [ \mathfrak { a } ] ) \in E ( H _ { c } ) _ { \overline { { \mathbb { Q } } } } .
$$

Theorem 3.3. Let $E , \chi$ be as above satisfying the Heegner conditions (1） and (2). Then

$$
L ^ { \prime } ( 1 , E , \chi ) = 2 ^ { - \mu ( N , D ) } \cdot \frac { 8 \pi ^ { 2 } ( \phi , \phi ) _ { \Gamma _ { 0 } ( N ) } } { u ^ { 2 } \sqrt { | D c ^ { 2 } | } } \cdot \frac { \widehat { h } _ { \infty } ( P _ { \chi } ( f ) ) } { \deg f } ,
$$

where $\mu ( N , D )$ is the number of prime factors of the greatest common divisor of $N$ and $D$ ， $\boldsymbol { u } = [ \mathcal { O } _ { c } ^ { \times } : \mathbb { Z } ^ { \times } ]$ is half of the number of roots of unity in ${ \mathcal { O } } _ { c }$ ，and $\widehat { h } _ { \infty }$ is the Néron -Tate height on $E$ over $\kappa$ ：

Moreover, let $p$ be a prime split in $\mathcal { K }$ and assume that $E$ is potential ordinary at $p$ (i.e. either potential good ordinary or potential semistable),then we have

$$
\mathcal { L } _ { E / K , \chi } ^ { \prime } ( 1 ) = \frac { \prod _ { w | p } Z _ { w } ( \chi _ { w } , \psi _ { w } ) } { L _ { p } ( E / K , \chi , 1 ) } \cdot \frac { 2 ^ { - \mu ( N , D ) } } { u ^ { 2 } \sqrt { | D c ^ { 2 } | } } \cdot \frac { \widehat { h } _ { p } ( P _ { \chi } ( f ) ) } { \deg f } ,
$$

where $\widehat { h } _ { p }$ is the $p$ -adic height on $E$ over $\mathcal { K }$

Proof. The explicit form of Gross-Zagier formula is proved in [2]. The explicit form of $p$ -adic Gross-Zagier formula then follows from the relation in Theorem 4.1. □

# 4.PROOF OF MAIN THEOREM 1.1

In this section, let $E$ be an elliptic curve over $\mathbb { Q }$ with CM by $K$ and $\Omega _ { E }$ the minimal real period of $E$ （204号 over $\mathbb { Q }$ .Let $p \nmid w _ { K }$ be a prime split both in $K$ ：

Lemma 4.1. Let $\mathcal { K }$ be an imaginary quadratic field where $p$ splits, $\eta$ the associated quadratic character, and $\eta _ { K }$ its base change to $K$ . Assume that $\epsilon ( E / \mathcal { K } ) = - 1$ . Then there exists a $p$ -adic unit u such that

$$
\mathcal { L } _ { E / \mathcal { K } } = \frac { \tau ( \varphi _ { \mathfrak { p } } , \psi _ { \mathfrak { p } } ) ^ { 2 } \cdot \Omega _ { E } ^ { 2 } } { 8 \pi ^ { 2 } ( \phi , \phi ) } \cdot \mathcal { L } _ { \varphi } \mathcal { L } _ { \varphi \eta \kappa } .
$$

ProfIt'sogatfcte $\nu : \widehat { \mathbb { Q } } / \mathbb { Q } ^ { \times } \widehat { \mathbb { Z } } ^ { \times ( p ) } \mathbb { Z } _ { p , \mathrm { t o r } } ^ { \times } \to \mathbb { C } ^ { \times }$ , we have

$$
\nu _ { K } ( \mu _ { E / K } ) = \tau ^ { 2 } ( \varphi _ { p } , \psi _ { p } ) \frac { \Omega _ { E } ^ { 2 } } { 8 \pi ^ { 2 } ( \phi , \phi ) } \mu _ { \mathfrak { f } _ { 0 } } ( \varphi \nu _ { K } ^ { - 1 } ) \mu _ { \mathfrak { f } _ { 0 } } ( \varphi \eta _ { K } \nu _ { K } ^ { - 1 } ) .
$$

Here $\nu _ { \mathcal { K } } = \nu \circ \mathrm { N } _ { K / \mathbb { Q } }$ and $\nu _ { K } = \nu \circ \Nu _ { K / \mathbb { Q } }$ . By interpolation property, the left hand of the formula in the emma is

$$
{ \frac { L ^ { ( p ) } ( 1 , \phi , \nu _ { \mathcal { K } } ^ { - 1 } ) } { 8 \pi ^ { 2 } ( \phi , \phi ) } } \prod _ { w \mid p } Z _ { w } ( \alpha _ { w } \nu _ { w } , \psi _ { w } ) ,
$$

Note that $\kappa / \mathbb { Q }$ splits at $p$ and then $\eta _ { p }$ is trivial, the right hand side of the formula in the lemma is

$$
\frac { \tau ( \varphi _ { \mathfrak { p } } \nu _ { \mathfrak { p } } ^ { - 1 } , \psi _ { \mathfrak { p } } ) ^ { 2 } } { \tau ( \varphi _ { \mathfrak { p } } , \psi ) ^ { 2 } } \cdot \left( \frac { 1 - \varphi \nu ^ { - 1 } ( \mathfrak { p } ) p ^ { - 1 } } { 1 - \overline { { \varphi \nu ^ { - 1 } ( \mathfrak { p } ) } } p ^ { - 1 } } \right) ^ { 2 } \cdot \frac { L ^ { ( p \mathfrak { f } _ { 0 } ) } ( \overline { { \varphi \nu ^ { - 1 } } } , 1 ) } { \Omega } \cdot \frac { L ^ { ( p \mathfrak { f } _ { 0 } ) } ( \overline { { \varphi \nu ^ { - 1 } \eta _ { K } } } , 1 ) } { \Omega }
$$

Then the formula follows from lemma 3.1.

We are ready to prove Theorem 1.1. Assume that $L ( s , E / \mathbb { Q } )$ has a simple zero at $s = 1$ and that $p$ is a bad but potentially good ordinary prime for $E$ .Let $\varphi$ be the Hecke character associated to $E$ and $\mathrm { f _ { 0 } }$ （204号 its the prime-to- $p$ conductor. We may choose an imaginary quadratic field $\mathcal { K }$ such that

） $L ( s , E / \mathcal { K } )$ also has a simple zero at $s = 1$ · $p$ is splits in $\mathcal { K }$ ： $\bullet$ the discriminant of $\mathcal { K }$ is prime to $\mathrm { f _ { 0 } }$

Note that related Euler factors are trivial in this case,we then have

$$
\begin{array} { r l } & { \bullet \ { \mathcal { L } } _ { \varphi _ { \mathcal M } ( \mathfrak { x } ) } = \frac { L ( 1 , E ^ { ( K ) } ) } { \Omega _ { E ^ { \prime } } } , } \\ & { \bullet \ \frac { { \mathcal { L } } _ { E ^ { \prime } / K } ^ { \prime } ( 1 ) } { R _ { \rho } ( E / K ) \tau ( \varphi _ { \mathfrak { p } } , \psi _ { \mathfrak { p } } ) ^ { 2 } } = \frac { L ^ { \prime } ( E / K , 1 ) } { R _ { \infty } ( E / K ) 8 \pi ^ { 2 } ( \phi , \phi ) } \cdot } \\ & { \bullet \ \mathrm { o r d } _ { \rho } \ \mathrm { ( } \Pi \mathrm { T } ( E / \mathbb { Q } ) | ) = \mathrm { o r d } _ { p } \left( \frac { { \mathcal { L } } _ { \varphi ^ { \prime } } ^ { \prime } ( 1 ) } { R _ { p } ( E / \mathbb { Q } ) } \right) , } \\ & { \bullet \ \mathrm { o r d } _ { \rho } \left( \frac { { \mathcal { L } } _ { E ^ { \prime } / K } ^ { \prime } ( 1 ) } { { \mathcal { L } } _ { \varphi ^ { \prime } } ^ { \prime } ( 1 ) { \mathcal { L } } _ { \varphi \pi _ { K } } ( 1 ) } \right) = \mathrm { o r d } _ { p } \left( \frac { \tau ( \varphi _ { \mathfrak { p } } , \psi _ { \mathfrak { p } } ) ^ { 2 } \Omega _ { E ^ { \prime } / K } ^ { 2 } } { 8 \pi ^ { 2 } ( \phi , \phi ) } \right) , } \\ & { \bullet \ \mathrm { o r d } _ { \rho } \left( \frac { \Omega _ { E ^ { \prime } / K } ^ { \prime } } { \Omega _ { E } } \right) = \mathrm { o r d } _ { p } \left( \frac { R _ { \rho } ( E / K ) } { R _ { p } ( E / \mathbb { Q } ) } \right) = 0 . } \end{array}
$$

It follows that

$$
\operatorname { o r d } _ { p } ( | \mathrm { I I I } ( E / \mathbb { Q } | ) ) = \operatorname { o r d } _ { p } \left( \frac { L ^ { \prime } ( E / \mathbb { Q } , 1 ) } { \Omega _ { E } \cdot R _ { \infty } ( E / \mathbb { Q } ) } \right) .
$$

This proves Theorem 1.1 (i). Assume that $E ( \mathbb { Q } )$ has rank one and $\mathrm { I I I } ( E / \mathbb { Q } ) ( p )$ is finite, or equivalently, $E ( K )$ has ${ \mathcal { O } } _ { K }$ -rank one and $\operatorname { I I I } ( E / K )$ is finite.By[1],the cyclotomic $p$ -adic height pairing is nondegenerate. Thus both $\mathcal { L } _ { \varphi _ { E } }$ and $\mathcal { L } _ { \overline { { \varphi _ { E } } } }$ have exactly order $^ { 1 }$ at $s = 1$ ,therefore $\mathcal { L } _ { E / \mathcal { K } }$ has exactly order

one at $s = 1$ ．It follows from $p$ -adic Gross-Zagier formula that the related Heegner point is non-trivial and therefore $L ( E , s )$ has a simple zero at $s = 1$ . This completes the proof of Theorem 1.1.

# REFERENCES

[1]Daniel Bertrand,ProprietésArithmetiques deFonctions Thetaä plusieurs variables,Lect.Notes inMath,vol 1068,pp.17-22.Berlin-Heidelberg-New York-Tokyo:Springer 1984. [2]L.Cai, J.Shu and Y.Tian,Explicit Gross-Zagier and Waldspurger formulae.Algebra Number Theory8 (2014), no.10,2523-2572. [3] J.Coates and A.Wiles,On p-adic L-functions and elipticunits.J.Austral.Math.Soc.Ser.A 26 (1978),no.1, 1-25. [4] Daniel Diegni, The p-adic Gross Zagier formula on Shimura curves,Preprint. 5jE.de Shalit, The Iwasawa theory of eliptic curues with complex multiplication,Perspect.Math. Vol.3 (1987). [6] G.Faltings, Crystalline cohomology and $p$ -adic Galois-representations.Algebraic analysis,geometry,and number theory (Baltimore,MD,1988),Johns Hopkins Univ.Press,Baltimore,MD,1989. [7] S.Friedberg and J. Hoffstein,Nonvanishing theorems for automorphic L-functions on $G L ( { \boldsymbol { \mathcal { Q } } } )$ . Ann. of Math. (2) 142 (1995),no.2,385-423. [8] Kobayashi, Shinichi,The $p$ -adic Gross-Zagier formula for elliptic curves at supersingular primes.Invent.Math. 191 (2013),no.3,527 -629. [9]B.Mazur,J.Tate,and J.Teitelbaum，On p-adic analogues of the conjecturesof Birch and Suinnerton-Dyer. Invent.Math.(1986) Volume 84,no.1,pp 1-48.   
[10]B,Perrn-Riou,Groupe de Selmer d'unecourbe elliptique multiplication complere, Compositio Math.43 (1981), no. 3, 387-417.   
[11]B.Perin-Riou,Descente infinieet hauter p-adique sur les courbes eliptiques multiplicationcomplere,Invent. Math.70(1982/83),n0.3,369-398.   
[12] B. Perrin-Riou, Points de Heegner et derivees de fonctions L $p$ -adiques, Invent. Math.89 (1987)， no. 3,pp. 455-510.   
[13]K.Rubin,Tate-Shafarevich groups andL-functionsofellipticcuroes with complex multiplication,Invent.Math. 89 (1987),no. 3, 527-559.   
[14] K.Rubin,The "main conjectures”of Iwasawa theory for imaginary quadratic fields,Invent. Math.103 (1991), no. 1, 25-68.   
[15] P.Schneider,Iuasawa L -functions of varieties over algebraic number fields.A first approach,Invent.Math.71 (1983),no.2,251-293   
[16]Y.Tian,Congruent Numbers and Heegner Points,Cambridge J.of Math,Vol.2.1.117-161,2014.   
[17] Y.Tian,X. Yuan and S. Zhang, Genus Periods, Genus Points and Congruent Number Problem,to appear in Asian Journal of Mathematics.   
[18] R.Yager,On two variable $p$ -adicL-functions,Ann.of Math.(2) 115(1982),no.2,411-449.   
[19] X.Yuan,S. Zhang,and W. Zhang, The Gross-Zagier Formula on Shimura Curves,Annals of Mathematics Studies Number 184,2013.