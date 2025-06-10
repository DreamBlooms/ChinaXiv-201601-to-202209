# Pazy's fixed point theorem with respect to the partial order in uniformly convex Banach spaces

Yisheng Song\* Rudong Chen†

# Abstract

In this paper, the Pazy's Fixed Point Theorems of monotone $\alpha -$ nonexpansive mapping $T$ are proved in a uniformly convex Banach space $E$ with the partial order‘ $\leq ^ { \gamma _ { 7 } }$ ： That is, we obtain that the fixed point set of $T$ with respect to the partial order“ $\leq$ ” is nonempty whenever the Picard iteration $\{ T ^ { n } x _ { 0 } \}$ is bounded for some initial point $x _ { 0 }$ with $x _ { 0 } \leq T x _ { 0 }$ or $T x _ { 0 } \leq x _ { 0 }$ .When restricting the demain of $T$ to the cone $P$ ， a monotone $\alpha -$ nonexpansive mapping $T$ has at least a fixed point if and only if the Picard iteration $\{ T ^ { n } 0 \}$ is bounbed.Furthermore,with the help of the properties of the normal cone $P$ , the weakly and strongly convergent theorems of the Picard iteration $\{ T ^ { n } x _ { 0 } \}$ are showed for finding a fixed point of $T$ with respect to the partial order ‘ $\leq$ ” in uniformly convex ordered Banach space.

Key Words and Phrases: Ordered Banach space, fixed point， monotone $\alpha$ nonexpansive mapping, convergence.

2000 AMS Subject Classification: 47H06, 47J05, 47J25, 47H10, 47H17, 49J40, 47H04, 65J15.

# 1 Introduction

In 1971, Pazy [20] proved the following fixed point theorem for a nonexpansive mapping in Hilbert spaces, which is referred to as Pazy's Fixed Point Theorem.

Theorem P. Let $H$ be a Hilbert space and $C$ be a nonempty closed convex subset of $H$ ： Let $T : C \to C$ be a nonexpansive mapping. Then the following are equivalent: (i) $\{ T ^ { n } x \}$ is a bounded sequence in $C$ for some $x \in C$ ： (ii) $T$ has at least a fixed point in $C$ ：

Recently, many mathematical workers studied the Pazy's Fixed Point Theorem for many distinct types of nonlinear mappings. In 2008, Kohsaka and Takahashi [13] showed Pazy's Fixed Point Theorem of a nonspreading mapping in a Hilbert space $H$ . A mapping $T : C $ （204 $C$ is called a nonspreading mapping if

$$
2 \| T x - T y \| ^ { 2 } \leq \| T x - y \| ^ { 2 } + \| T y - x \| ^ { 2 } { \mathrm { ~ f o r ~ a l l ~ } } x , y \in C .
$$

They showed that $T$ has a fixed point whenever $\{ T ^ { n } x \}$ is a bounded sequence for some $x \in C$ . The same result was obtained by Takahashi [28] for a hybrid mapping in a Hilbert space $H$ . A mapping $T : C \to C$ is called a hybrid mapping if

$$
\begin{array} { r } { \| T x - T y \| ^ { 2 } \leq \| x - y \| ^ { 2 } + \langle x - T x , y - T y \rangle \mathrm { ~ f o r ~ a l l ~ } x , y \in C . } \end{array}
$$

In 2011, Takahashi and Yao [29] proved Pazy's Fixed Point Theorem of a $T J$ -mapping in a Hilbert space $H$ . A mapping $T : C \to C$ is called a $T J$ -mapping if

In 2012, Lin and Wang [14] showed Pazy's Fixed Point Theorem for an $( a , b )$ -monotone mapping in a Hilbert space $H$ . A mapping $T : C \to C$ is called an $( a , b )$ -monotone mapping if for all $x , y \in C$ ，

$$
\langle x - y , T x - T y \rangle \geq a \Vert T x - T y \Vert ^ { 2 } + ( 1 - a ) \Vert x - y \Vert ^ { 2 } - b \Vert x - T x \Vert ^ { 2 } - b \Vert y - T y \Vert ^ { 2 } ,
$$

where $a \in ( \textstyle { \frac { 1 } { 2 } } , \infty )$ and $b \in ( - \infty , a )$ Very recently, Song et. al. [22] firstly studied Pazy's Fixed Point Theorem for a monotone nonexpansive mapping in a uniformly convex Banach space with the partial order “ $\leq$ ”.Let $T$ be a mapping with domain $D ( T )$ and range $R ( T )$ （204号 in an ordered Banach space $E$ endowed with the partial order “ $\leq$ ”.Then $T : D ( T )  R ( T )$ （202 is said to be monotone nonexpansive ([2]) if for all $x , y \in D ( T )$ with $x \leq y$ ，

$$
T x \leq T y { \mathrm { ~ a n d ~ } } \| T x - T y \| \leq \| x - y \| .
$$

Clearly,a monotone nonexpansive mapping may be discontinuous. In 2015, Bachar and Khamsi [2] introduced the concept of a monotone nonexpansive mapping and studied common approximate fixed points of a monotone nonexpansive semigroup. Dehaish and Khamsi [4] proved some weak convergence theorems of the Mann iteration for finding some order fixed points of monotone nonexpansive mappings in uniformly convex ordered Banach spaces.

The Mann iteration was introduced by Mann [16] in 1953 for finding a fixed point of a nonexpansive mapping $T$ ，

$x _ { n + 1 } = \beta _ { n } x _ { n } + ( 1 - \beta _ { n } ) T x _ { n }$ for each positive integer $n$

There had be many convergence conclusions of such an iteration in the past several decades. For more details, see Liu [15], Narghirad et al. [17], Suzuki [26], Song [24], Opial [19], Kim et al. [12], Okeke and Kim [18], Berinde [3], George and Shaini [6], Gu and Lu [10], Zhou et al. [32], Song and Wang [23], zhang and Su [31], Zhou [33] and the reference therein. Very recently, Song et. al. [21] studied weak convergence of the Mann iteration for monotone $\alpha$ -nonexpansive mappings in a uniformly convex Banach space with the partial order “ $\leq$ ” under the coefficient condition $ { \mathrm { : : } } \dim \operatorname* { s u p } \beta _ { n } ( 1 - \beta _ { n } ) > 0 ^ { \mathfrak { " } }$ or“liminf $\beta _ { n } ( 1 - \beta _ { n } ) > 0 ^ { ; \prime }$ ，which （204号 $n { \longrightarrow } \infty$ （204号 $n { \longrightarrow } \infty$   
excludes $\beta _ { n } = 0$ or $\textstyle { \frac { 1 } { n } }$ ：

If $\beta _ { n } = 0$ in Mann iteration, then such an iteration is called Picard iteration. In this paper, we willstudy the convergence of Picard iteration in a uniformly convex Banach space with the partial order“ $\leq$ ". More precisely, we consider the Pazy's Fixed Point Theorem for monotone $\alpha$ -nonexpansive mappings in a uniformly convex Banach space with the partial order“ $\leq$ ” in Section 3. That is, for a monotone $\alpha$ -nonexpansive mapping $T$ , the boundedness of the Picard iteration $\{ T ^ { n } x _ { 0 } \}$ for some $x _ { 0 }$ with $x _ { 0 } \leq T x _ { 0 }$ or $x _ { 0 } \geq I ^ { \prime } x _ { 0 }$ implies that ordered fixed point set $F _ { \geq } ( T ) \neq \emptyset$ or $F _ { \leq } ( T ) \neq \emptyset$ .Furthermore, for a monotone $\alpha$ -nonexpansive mapping $T$ defined on a closed convex cone $P$ with respect to the partial order $\stackrel { 6 6 } { = } \stackrel { 7 7 } { }$ ，its fixed point set $F ( T ) \neq \emptyset$ if and only if the Picard iteration $\{ T ^ { n } 0 \}$ is bounded (where O is the origin). In Section 4, under the frame of the partial order “ $\leq$ ” of a Banach space $( E , \| \cdot \| )$ defined by the normal cone $P$ ，we will show the weak and strong convergence of Picard iteration of a monotone $\alpha$ -nonexpansive mapping.

# 2 Preliminaries and basic results

Throughout this paper, let $E$ be an ordered Banach space with the norm $\| \cdot \|$ and the partial order “ $\leq$ ”.Let $F ( T ) = \{ x \in E : T x = x \}$ denote the set of all fixed points of a mapping $T$

Let $E$ be a real Banach space and $P$ be a subset of $E$ ： $P$ is called a closed convex cone if $P$ is nonempty closed, and $P \neq \{ 0 \}$ with $P \cap ( - P ) = \{ 0 \}$ ，and $a x + b y \in P$ for all $x , y \in P$ （20 and nonnegative real numbers $a , b$ . The partial order “ $\leq$ ”，“ $<$ ” and “<”with respect to $P$ （20

in $E$ are defined as follows: for all $x , y \in E$

$$
\begin{array} { r l } & { x \leq y ~ \mathrm { ~ i f ~ a n d ~ o n ~ i f } ~ y - x \in P , } \\ & { x < y ~ \mathrm { i f ~ a n d ~ o n ~ i f } ~ y - x \in P ~ \mathrm { a n d } ~ y \not = x , } \\ & { x \ll y ~ \mathrm { i f ~ a n d ~ o n ~ i f } ~ y - x \in \mathring { P } ~ \mathrm { w h e n e v e r } ~ \mathring { P } \not = \emptyset , } \end{array}
$$

where $\mathring { P }$ is the interior of $P$ . The partial order ${ \bf \Xi } ^ { \ast } \underline { { { \bf \Lambda } } } ^ { \ast } \underline { { { \bf \Lambda } } } ,$ is defined by

$$
x \geq y { \mathrm { ~ ~ i f ~ a n d ~ o n ~ i f ~ } } y \leq x .
$$

Then we have

$$
x = y { \mathrm { ~ i f ~ a n d ~ o n ~ i f ~ } } y \leq x { \mathrm { ~ a n d ~ } } y \geq x .
$$

In the sequel, $[ x , y ]$ stands for the order interval. An order interval $[ x , y ]$ for all $x , y \in E$ （204号 is given by

$$
[ x , y ] = \{ z \in E : x \leq z \leq y \} .
$$

Clearly, the order interval $[ x , y ]$ are closed and convex by the definition of the partial order “≤”,which implies that

$$
x \leq t x + ( 1 - t ) y \leq y
$$

for all $t$ with $0 \leq t \leq 1$ and all $x , y \in E$ with $x \leq y$

Definition 2.1. （[5]） Let $( E , \| \cdot \| )$ be an ordered Banach space with the partial order “≤”with respect to a cone $P$ ：

(1) A sequence $\{ x _ { n } \} \subset E$ is called monotonic if $\{ x _ { n } \}$ is either increasing, i.e., $x _ { n } \leq x _ { n + 1 }$ （20 for all positive integer $n$ ， or decreasing, i.e., $x _ { n } \geq x _ { n + 1 }$ for all positive integer $n$ ：   
(2) A subset $C$ of $E$ is called bounded above if $C$ has an upper bound with respect to $\overset {  } { \leq } \mathit { \ " }$ i.e., there exists $y \in E$ such that $x \leq y$ for all $x \in C$ ， and the least upper bound of $C$ with respect to “≤” is called the supremum of $C$ ， denote sup $C$ if it exists.   
(3) A subset $C$ of $E$ is called bounded below if $C$ has a lower bound with respect to $\because$ i.e.， there exists $z \in E$ such that $z \leq x$ for all $x \in C$ ， and the greatest lower bound of $C$ with respect to “≤”is called the infimum of $C$ ， denote inf $C$ if it exists.   
(4） The cone $P$ is called normal if there exists a constant $\gamma > 0$ such that $\| x \| \leq \gamma \| y \|$ for all $x , y \in E$ with $0 \leq x \leq y$ or equivalently, if the order interval $[ x , y ]$ for all $x , y \in E$ （204号 with $x \leq y$ is bounded with respect to the norm $\| \cdot \|$ ：   
(4） The cone $P$ is called minihedral ij $\mathrm { \{ ~ s u p } \{ \boldsymbol { x } , \boldsymbol { y } \} $ exists for all $x , y \in E$ ， and strongly minihedral if each set which is bounded above has a supremum.

Lemma 2.1. ([25]) Let $( E , \parallel \cdot \parallel )$ be an ordered Banach space with the partial order “≤" with respect to a cone $P$ ：

(i) Assume that $\{ x _ { n } \}$ and $\left\{ y _ { n } \right\}$ are two sequences on $E$ such that

If $x _ { n }$ and $y _ { n }$ weakly converges to $x$ and $y$ ， respectively， then

$$
x \leq y .
$$

(ii) The cone $P$ is normal if and only if there exists a equivalent norm $\| \cdot \| _ { 1 }$ of $E$ such that

Definition 2.2. ([2,21]) Let $K$ be a nonempty closed convex subset of an ordered Banach space $( E , \leq )$ . A mapping $T : K \to E$ is said to be:

(1）monotone ([2]） if $T x \leq T y$ for all $x , y \in K$ with $x \leq y$ ，

(2）monotone nonexpansive $( / 2 7 )$ if $T$ is monotone and

$$
\| T x - T y \| \leq \| x - y \|
$$

for all $x , y \in K$ with $x \leq y$

(3） monotone $\alpha$ -nonexpansive([21]) if $T$ is monotone and for some $\alpha < 1$

$$
\begin{array} { r } { \| T x - T y \| ^ { 2 } \leq \alpha \| T x - y \| ^ { 2 } + \alpha \| T y - x \| ^ { 2 } + ( 1 - 2 \alpha ) \| x - y \| ^ { 2 } } \end{array}
$$

for all $x , y \in K$ with $x \leq y$

(4）monotone quasi-nonexpansive(/21l) if $F ( T ) \neq \emptyset$ and

$$
\| T x - p \| \leq \| x - p \|
$$

for all $p \in F ( T )$ and all $x \in K$ with $x \leq p$ or $x \geq p$

Obviously, a monotone nonexpansive mapping is monotone 0-nonexpansive. In the sequel,we will use the fixed point sets with the partial order $F _ { \leq } ( T )$ and $F _ { \geq } ( T )$ given by

$$
F _ { \leq } ( T ) = \{ p \in F ( T ) : p \leq x { \mathrm { ~ f o r ~ s o m e ~ } } x \in K \}
$$

and

$$
F _ { \geq } ( T ) = \{ p \in F ( T ) : x \leq p { \mathrm { ~ f o r ~ s o m e ~ } } x \in K \} .
$$

Lemma 2.2. ([21, Lemma 2.1]) Let $K$ be a nonempty closed convex subset of an ordered Banach space $( E , \leq )$ and $T : K \to K$ be a monotone $\alpha$ -nonexpansive mapping. Then

（1） $T$ is monotone quasi-nonexpansive if $F _ { \leq } ( T ) \neq \varnothing$ or $F _ { \geq } ( T ) \neq \varnothing$

(2) for all $x , y \in K$ with $x \leq y$ (or $y \le x$ )

$$
\begin{array} { l } { \displaystyle \| T x - T y \| ^ { 2 } } \\ { \displaystyle \leq \| x - y \| ^ { 2 } + \frac { 2 \alpha } { 1 - \alpha } \| T x - x \| ^ { 2 } + \frac { 2 | \alpha | } { 1 - \alpha } \| T x - x \| ( \| x - y \| + \| T x - T y \| ) . } \end{array}
$$

Definition 2.3. Let $E$ ba a Banach space. Then

(1） a function $\delta _ { E } : [ 0 , 2 ]  [ 0 , 1 ]$ is said to be the modulus of convexity of $E$ if

$$
\delta _ { E } ( \varepsilon ) = \operatorname* { i n f } \{ 1 - { \frac { \| x + y \| } { 2 } } ; \ \| x \| \leq 1 , \ \| y \| \leq 1 , \ \| x - y \| \geq \varepsilon \} ;
$$

2）a number ${ \varepsilon _ { 0 } } ( E )$ is said to be the characteristic of convexity of $E$ if

$$
\varepsilon _ { 0 } ( E ) = \operatorname* { s u p } \{ \varepsilon \in [ 0 , 2 ] ; \delta _ { E } ( \varepsilon ) = 0 \} .
$$

Definition 2.4. A Banach space $E$ is said to be (1）uniformly convex if $\delta _ { E } ( \varepsilon ) > 0$ for all $\varepsilon \in ( 0 , 2 ]$ or equivalently if $\varepsilon _ { 0 } ( E ) = 0$ (2） strictly convex if $\delta _ { E } ( 2 ) = 1$

The following properties of the modulus of convexity of a Banach space $E$ were found in the references [1, 8, 9].

Lemma 2.3. Let $E$ be a Banach space with the modulus of convexity $\delta _ { E } ( \cdot )$ and the characteristic of convexity $\varepsilon _ { 0 }$ . Then we have the following:

(i） $\delta _ { E } ( \cdot )$ is continuous on $[ 0 , 2 )$   
(ii) $\delta _ { E } ( \cdot )$ is strictly increasing on $[ \varepsilon _ { 0 } , 2 ]$ ：   
(iii) If, in addition, $E$ is uniformly convex, $r > 0$ and $x , y \in E$ with $\| x \| \leq r , \ \| y \| \leq r$ then

$$
\left\| \lambda x + ( 1 - \lambda ) y \right\| \leq r \left[ 1 - 2 \operatorname* { m i n } \{ \lambda , 1 - \lambda \} \delta _ { E } \left( { \frac { \| x - y \| } { r } } \right) \right] { \mathrm { ~ } } f o r { \mathrm { ~ } } a l l \lambda \in [ 0 , 1 ] .
$$

In particular, taking $\begin{array} { r } { \lambda = \frac { 1 } { 2 } } \end{array}$

$$
\left\| { \frac { x + y } { 2 } } \right\| \leq r \left[ 1 - \delta _ { E } \left( { \frac { \left\| x - y \right\| } { r } } \right) \right] .
$$

(iv) Each uniformly convex Banach space has the Kadec-Klee property， i.e.,

The following conclusion is well known. For the more detail, see the references [5, 9, 27].

Lemma 2.4. Let $C$ be a nonempty closed convex subset of a reflexive Banach space $E$ Assume that $f : C \to ( - \infty , + \infty )$ is a proper convex lower semi-continuous and coercive function (i.e., $\begin{array} { r } { \operatorname* { l i m } _ { \| \boldsymbol { x } \|  \infty } f ( \boldsymbol { x } ) = \infty } \end{array}$ ). Then there exists $x \in C$ such that

$$
f ( x ) = \operatorname* { i n f } _ { y \in C } f ( y ) .
$$

# 3 Pazy type Fixed Point Theorems with the partial order

Let $K$ be a nonempty closed convex subset of an ordered Banach space $( E , \leq )$ and let （20 $T : K \to K$ be a monotone $\alpha$ -nonexpansive mapping. In this section， we consider the Picard iteration defined by

$$
x _ { n + 1 } = T x _ { n } = T ^ { n } x _ { 0 }
$$

for fixed $x _ { 0 } \in K$ and each positive integer $n \geq 1$ =

Definition 3.1. Let $T$ be a mapping on a Banach space $E$ and $x _ { 0 } \in D ( T )$ ， the domain of $T$ . Then the set of points, denoted by $O ( x _ { 0 } )$ is called the orbit of $x _ { 0 }$ under $T$ if

$$
O ( x _ { 0 } ) = \{ T ^ { n } x _ { 0 } ; n = 0 , 1 , 2 , \cdot \cdot \cdot \} ,
$$

and its closure is called the closed orbit.

The following technical lemma plays a key role in the proof of main results of this work, which may be found in the reference [25]. For the completeness, we give its proof.

Lemma 3.1. Let $( E , \parallel \cdot \parallel )$ be a Banach space with the partial order “≤". Assume that a sequence $\{ x _ { n } \} \subset E$ is monotonic.

(i) If there exists a subsequence $\{ x _ { n _ { k } } \} \subset \{ x _ { n } \}$ such that $x _ { n _ { k } }$ weakly converges to some point $x \in E$ ，then $x _ { n } \leq x$ for all positive integer $n$ when $\{ x _ { n } \}$ is increasing or $x _ { n } \geq x$ （204号 for all positive integer $n$ when $\{ x _ { n } \}$ is decreasing.

(ii)） If $( E , \parallel \cdot \parallel )$ is reflexive and $\{ x _ { n } \}$ is bounded with respect to the norm $\| \cdot \|$ ，then $x _ { n }$ weakly converges to some point $x \in E$ ：

Proof. (i) Assume that $\{ x _ { n } \}$ is increasing, i.e., $x _ { n } \leq x _ { n + 1 }$ for all positive integer $n$ .Then for given $n$ , there exists a positive integer $k _ { 0 }$ such that $n < n _ { k _ { 0 } }$ , and hence, $x _ { n } \le x _ { n _ { k _ { 0 } } } \le x _ { n _ { k } }$ （204号 for all $k > k _ { 0 }$ . It follows from Lemma 2.1 (i) and the weak convergence of $x _ { n _ { k } }$ that $x _ { n } \leq x$ ： Since $n$ is arbitrary, $x _ { n } \leq x$ for all positive integer $n$ ：

Using the same proof technique, it is easy to prove that $x _ { n } \geq x$ for all positive integer $n$ when $\{ x _ { n } \}$ is decreasing.

(ii) Without loss of generality, we may assume that $\{ x _ { n } \}$ is increasing. It follows from the reflexivity of $E$ and the boundedness of $\{ x _ { n } \}$ that $\{ x _ { n } \}$ is weakly sequentially compact. Then we may choose two subsequences $\{ x _ { n _ { k } } \}$ and $\{ x _ { n _ { j } } \}$ in $\{ x _ { n } \}$ such that $x _ { n _ { k } }$ and $\{ x _ { n _ { j } } \}$ weakly converge to $x$ and $y$ , respectively. We must have $x = y$ . In fact, using the the same proof technique as (i), for fixed $n _ { k }$ ， there is large enough $n _ { j }$ such that $x _ { n _ { k } } \le x _ { n _ { j } }$ . Then by Lemma 2.1 (i)，we have $x _ { n _ { k } } \ \leq \ y$ ， and so for all $k$ ， $x _ { n _ { k } } \ \leq \ y$ . Again using Lemma 2.1 (i), we have $x \leq y$ . Using the same proof technique,we also have $y \le x$ . Thus $x = y$ . Which means that any subsequences $\{ x _ { n _ { k } } \}$ of $\{ x _ { n } \}$ weakly converges to $x$ , and hence, $\{ x _ { n } \}$ weakly converges to $x$ ： □

Now we prove some existence theorems of fixed points with the partial order “≤” of monotone $\alpha$ -nonexpansive mappings in a partial order Banach space.

Theorem 3.2.Let $K$ be a nonempty closed convex subset of a uniformly convex Banach space $( E , \| \cdot \| )$ with the partial order “≤” and $T : K \to K$ be a monotone α-nonexpansive mapping.

(i）If $x _ { 0 } ~ \le ~ T x _ { 0 }$ and the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm $\| \cdot \|$ ，then $F _ { \geq } ( T ) \neq \varnothing$ ：   
(ii）If $F _ { \geq } ( T ) \neq \varnothing$ ， then there exists $x _ { 0 } \in K$ such that the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm $\| \cdot \|$ ：

Proof. (i) Since $x _ { 0 } \leq T x _ { 0 }$ , it follows from the monotonicity of $T$ that $T x _ { 0 } \leq T ^ { 2 } x _ { 0 }$ ， and so

$$
T ^ { 2 } x _ { 0 } \leq T ^ { 3 } x _ { 0 } , \cdot \cdot \cdot , T ^ { n } x _ { 0 } \leq T ^ { n + 1 } x _ { 0 } , \cdot \cdot \cdot .
$$

Namely,

$$
x _ { 0 } \leq T x _ { 0 } \leq T ^ { 2 } x _ { 0 } \leq T ^ { 3 } x _ { 0 } \leq \cdot \cdot \cdot \leq T ^ { n } x _ { 0 } \leq T ^ { n + 1 } x _ { 0 } \cdot \cdot \cdot \cdot .
$$

By Lemma 3.1, there exists $x \in E$ such that $T ^ { n } x _ { 0 }$ weakly converges to $x$ and $T ^ { \mathit { m } } x _ { 0 } \leq x$ for all positive integer $n$ . Since the closed convexity of $K$ implies that $K$ is weakly sequentially closed, we have $x \in K$ ：

Let $K _ { n } = \{ y \in K ; T ^ { n } x _ { 0 } \leq y \}$ for all positive integer $n$ . Clearly, for each $n$ ， $K _ { n }$ is closed convex and $x \in K _ { n }$ for all positive integer $n$ .Let $C = \bigcap _ { n = 1 } ^ { \infty } K _ { n }$ . Clearly, $C \subset K$ is a nonempty

closed convex ( $x \in C$ ). Since the orbit $O ( x _ { 0 } ) = \{ T ^ { n } x _ { 0 } ; n = 0 , 1 , 2 , \cdot \cdot \cdot \}$ is bounded with respect to the norm $\| \cdot \|$ ，we may define a function $f : C \to \lfloor 0 , + \infty \ u \to$ as follows

$$
f ( y ) = \operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } - y \| { \mathrm { ~ f o r ~ a l l ~ } } y \in C .
$$

It is obvious that $f$ is a proper convex, continuous and coercive function. It follows from Lemma 2.4 that there exists $z \in C$ such that

$$
f ( z ) = \operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } - z \| = \operatorname* { i n f } _ { y \in C } f ( y ) = r .
$$

By the definition of $C$ ， we have

$$
T ^ { n } x _ { 0 } \leq z { \mathrm { ~ f o r ~ a l l ~ p o s i t i v e ~ i n t e g e r ~ } } n ,
$$

and hence,

which implies that $T z \in C$ . Thus ${ \frac { z + T ^ { \prime } z } { 2 } } \in C$ , and so, it follows from (3.2) that

$$
r = f ( z ) \leq f { \bigg ( } { \frac { z + T z } { 2 } } { \bigg ) } \quad { \mathrm { a n d } } \quad r = f ( z ) \leq f ( T z ) .
$$

On the other hand, it follows from the definition of $T$ that

$$
\begin{array} { r } { \| T ^ { m + 1 } x _ { 0 } - T z \| ^ { 2 } \leq \alpha \| T ^ { n + 1 } x _ { 0 } - z \| ^ { 2 } + \alpha \| T z - T ^ { n } x _ { 0 } \| ^ { 2 } + ( 1 - 2 \alpha ) \| T ^ { m } x _ { 0 } - z \| ^ { 2 } , } \end{array}
$$

and so,

$$
\begin{array} { l } { \displaystyle ( \operatorname* { l i m s u p } _ { n \to \infty } \| T ^ { n + 1 } x _ { 0 } - T z \| ) ^ { 2 } \leq \alpha ( \operatorname* { l i m s u p } _ { n \to \infty } \| T ^ { n + 1 } x _ { 0 } - z \| ) ^ { 2 } + \alpha ( \operatorname* { l i m s u p } _ { n \to \infty } \| T z - T ^ { n } x _ { 0 } \| ) ^ { 2 } } \\ { \displaystyle \qquad + ( 1 - 2 \alpha ) ( \operatorname* { l i m s u p } _ { n \to \infty } \| T ^ { n } x _ { 0 } - z \| ) ^ { 2 } , } \end{array}
$$

that is,

$$
( 1 - \alpha ) ( \operatorname* { l i m } _ { n \to \infty } \| T z - T ^ { n } x _ { 0 } \| ) ^ { 2 } \leq ( 1 - \alpha ) ( \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { } \| T ^ { n } x _ { 0 } - z \| ) ^ { 2 } .
$$

Thus, we have

$$
f ( T z ) = \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { 0 \to \infty } \| T ^ { n } x _ { 0 } - T z \| \leq \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { 0 } \| T ^ { n } x _ { 0 } - z \| = f ( z ) = r .
$$

Combining (3.3) and (3.4)，we obtain

$$
r = f ( z ) = f ( T z ) \geq 0 .
$$

We claim $z = T z$ . In fact, suppose $r = 0$ . Then

$$
\operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } - T z \| = \operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } - z \| = 0 ,
$$

which means $z = T z$ . Next suppose $r > 0$ . It follows from the definition of the upper limit "lim sup” that for all $\varepsilon > 0$ ， there exists a positive integer $N$ such that

$\| T ^ { n } x _ { 0 } - T z \| < r + \varepsilon$ and $\| T ^ { n } x _ { 0 } - z \| < r + \varepsilon$ for all positive integer $n > N$ ：

It follows from Lemma 2.3 that for all positive integer $n > N$ ，

$$
\Big \| T ^ { n } x _ { 0 } - \frac { z + T z } { 2 } \Big \| = \Big \| \frac { ( T ^ { n } x _ { 0 } - z ) + ( T ^ { n } x _ { 0 } - T z ) } { 2 } \Big \| \leq ( r + \varepsilon ) \left[ 1 - \delta _ { E } \left( \frac { \| z - T z \| } { r + \varepsilon } \right) \right] .
$$

Without loss of generality, we may assume that $\varepsilon < 1$ . Then the above inequality can be rewritten as follow:

$$
\left. T ^ { n } x _ { 0 } - \frac { z + T z } { 2 } \right. \leq ( r + \varepsilon ) \left[ 1 - \delta _ { E } \left( \frac { \Vert z - T z \Vert } { r + 1 } \right) \right] ,
$$

and so, we have

$$
f \Bigl ( \frac { z + T z } { 2 } \Bigr ) = \operatorname* { l i m } _ { n \to \infty } \mathrm { s u p } \left\| T ^ { n } x _ { 0 } - \frac { z + T z } { 2 } \right\| \le ( r + \varepsilon ) \left[ 1 - \delta _ { E } \left( \frac { \| z - T z \| } { r + 1 } \right) \right] .
$$

From (3.3),it follows that

$$
r \delta _ { E } \left( \frac { \| z - T z \| } { r + 1 } \right) \leq ( r + \varepsilon ) \delta _ { E } \left( \frac { \| z - T z \| } { r + 1 } \right) \leq r - f \Big ( \frac { z + T z } { 2 } \Big ) + \varepsilon \leq \varepsilon .
$$

Since $\varepsilon$ is arbitrary, we have

$$
r \delta _ { E } \left( \frac { \lVert z - T z \rVert } { r + 1 } \right) = 0 ,
$$

and hence, $z = T z$ by Lemma 2.3 (ii). Clearly, $z \geq x _ { 0 }$ ，and so $z \in F _ { \geq } ( T )$

(ii) Let $z \in F _ { \geq } ( T )$ . Then there exists a $x _ { 0 } \in K$ such that $x _ { 0 } \le z$ . It follows from the monotonicity of $T$ that $T x _ { 0 } \leq T z = z$ ，and hence, ${ \cal T } ^ { 2 } x _ { 0 } = { \cal T } ( T x _ { 0 } ) \le { \cal T } z = z$ .By such analogy, we have

From Lemma 2.2, it follows that

which implies the boundedness of the sequence $\{ T ^ { n } x _ { 0 } \}$ . This completes the proof.

Using the same proof technique of Theorem 3.2 (the only change is $K _ { n } = \{ y \in K : y \leq$ $T ^ { n } x _ { 0 } \}$ and $T ^ { n + 1 } x _ { 0 } \leq T ^ { n } x _ { 0 } ,$ ), the following theorem is easy to be proved.

Theorem 3.3.Let $K$ be a nonempty closed convex subset of a uniformly convex Banach space $( E , \| \cdot \| )$ with the partial order “≤” and let $T : K \to K$ be a monotone $\alpha$ -nonexpansive mapping.

(i）If $x _ { 0 } ~ \ge ~ T x _ { 0 }$ and the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm $\| \cdot \|$ ，then $F _ { \leq } ( T ) \neq \varnothing$ ：   
(ii) If $F _ { \leq } ( T ) \neq \varnothing$ ， then there exists $x _ { 0 } \in K$ such that the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm $\| \cdot \|$

Theorem 3.4. Let $( E , \| \cdot \| )$ be a uniformly convex ordered Banach space with the partial order $\because$ with respect to closed convex cone $P$ and let $T : \ : P \ :  \ : P$ be a monotone α- nonexpansive mapping. Then $F ( T ) \neq \emptyset$ if and only if the orbit $O ( 0 )$ is bounded with respect to the norm $\| \cdot \|$ ：

Proof. Since $T ( P ) \subset P$ ，for all $x \in F ( T )$ ，we have $x \ \geq \ 0$ ，and so $x \in F _ { \geq } ( T )$ .Then ${ \cal F } ( T ) \subset { \cal F } _ { \geq } ( T ) \subset { \cal F } ( T )$ , and so, $F ( T ) = F _ { \geq } ( T )$

“Sufficiency”. It follows from the definition of the partial order ‘ $\leq "$ that $x _ { 0 } = 0 \leq T 0 =$ $T x _ { 0 }$ . Then the conclusion directly follows from Theorem 3.2.

"Necessity”. Take $x \in F ( T ) = F _ { \geq } ( T )$ . Then $x \geq 0$ , and hence,

$$
x = T x \geq T 0 , x = T x \geq T ^ { 2 } 0 , \cdot \cdot \cdot , x = T x \geq T ^ { n } 0 , \cdot \cdot \cdot .
$$

That is, $x \geq { \cal T } ^ { n } 0$ for all positive integer $n$ . It follows from Lemma 2.2 that

$$
\| T ^ { n + 1 } 0 - x \| \leq \| T ^ { n } 0 - x \| \leq \cdots \leq \| 0 - x \| = \| x \| .
$$

This means that the orbit $O ( 0 )$ is bounded with respect to the norm $\| \cdot \|$

# 4Weak and strong convergence of Picard iteration

Definition 4.1. Let $( E , \| \cdot \| )$ be a Banach space with the partial order “≤". The norm $\| \cdot \|$ is called monotonic if

It is well known that if the cone $P$ is normal, by Lemma 2.1, if and only if there exists a equivalent norm $\| \cdot \| _ { 1 }$ which is monotonic.

Theorem 4.1. Let $K$ be a nonempty closed convex subset of a uniformly convex Banach space $( E , \| \cdot \| )$ with the partial order $\because$ with respect to the normal cone $P$ and let $T : K $ $K$ be a monotone $\alpha$ -nonexpansive mapping. Assume that $x _ { 0 } \leq T x _ { 0 }$ and the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm $\| \cdot \|$ . If the norm $\| \cdot \|$ is monotonic, then $T ^ { n } x _ { 0 }$ weakly converges to some point $z \in F _ { \geq } ( T )$ ：

Proof. Using the same proof technique of Theorem 3.2, we obtain the following:

(i) ${ \boldsymbol { \mathit { T } } } ^ { \prime \prime } { \boldsymbol { x } } _ { 0 }$ weakly converges to some point $x \in K$ and $T ^ { \mathit { m } } x _ { 0 } \leq x$ for all positive integer $n$ Furthermore,

$$
x \in C = \bigcap _ { n = 1 } ^ { \infty } \{ y \in K ; T ^ { n } x _ { 0 } \leq y \} .
$$

(ii) Let $f ( y ) = \operatorname* { l i m } \operatorname* { s u p } \| T ^ { n } x _ { 0 } - y \|$ for all $y \in C$ . Then there exists $z \in C$ such that $n { \longrightarrow } \infty$ $z = T z \geq T ^ { n } x _ { 0 }$ for all positive integer $n$ and

$$
f ( z ) = \operatorname* { i n f } \{ f ( y ) ; y \in C \} \leq f ( x ) .
$$

Next we prove $z = x$ . It follows from Lemma 2.1 (i) that

$$
T ^ { n } x _ { 0 } \leq x \leq z = T z .
$$

Thus, we have

$$
0 \leq x - T ^ { n } x _ { 0 } \leq z - T ^ { n } x _ { 0 } ,
$$

whichimpliesthat

$$
\| x - T ^ { n } x _ { 0 } \| \leq \| z - T ^ { n } x _ { 0 } \|
$$

by the monotonicity of the norm $\| \cdot \|$ . Consequently,

$$
f ( x ) = \operatorname* { l i m } _ { n \to \infty } \| x - T ^ { n } x _ { 0 } \| \leq \operatorname* { l i m } _ { n \to \infty } \| z - T ^ { n } x _ { 0 } \| = f ( z ) \leq f ( x ) ,
$$

and hence, $f ( x ) = f ( z ) = r$ . Using the same proof technique of Theorem 3.2, we have $x = z$ （204 also.This completes the proof. □

Similarly, we also the following theorem.

Theorem 4.2.Let $K$ be a nonempty closed convex subset of a uniformly convex Banach space $( E , \| \cdot \| )$ with the partial order “≤” and let $T : K \to K$ be a monotone α-nonexpansive mapping. Assume that $x _ { 0 } \geq T x _ { 0 }$ and the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm （204号 $\| \cdot \|$ . If the norm $\| \cdot \|$ is monotonic, then $T ^ { n } x _ { 0 }$ weakly converges to some point $z \in F _ { \geq } ( T )$

Let the intersection of the domain $D ( T )$ of monotone $\alpha$ -nonexpansive mapping $T$ and the cone $P$ is nonempty, i.e., $D ( T ) \cap P \neq \emptyset$ . The following strongly convergent theorems may be obtained.

Theorem 4.3. Let $K$ be a nonempty closed convex subset of a uniformly convex Banach space $( E , \| \cdot \| )$ with the partial order “≤” and let $T : K \to K$ be a monotone α-nonexpansive mapping. Assume that $0 \leq x _ { 0 } \leq T x _ { 0 }$ and the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm $\| \cdot \|$ . If the norm $\Vert \cdot \Vert$ is monotonic, then $T ^ { n } x _ { 0 }$ strongly converges to some point （204号 $z \in F _ { \geq } ( T )$ ：

Proof. It follows from Theorem 4.1 that there exists $z \in F _ { \geq } ( T )$ such that $\mathbf { \chi } ^ { \prime n } \mathbf { \chi } _ { 0 }$ weakly converges to some point $z \in K$ and

$$
0 \leq x _ { 0 } \leq T ^ { n } x _ { 0 } \leq T ^ { n + 1 } x _ { 0 } \leq z { \mathrm { ~ f o r ~ a l l ~ p o s i t i v e ~ i n t e g e r ~ } } n .
$$

Then by the monotonicity of the norm,we have

$$
0 \leq \| x _ { 0 } \| \leq \| T ^ { m } x _ { 0 } \| \leq \| T ^ { n + 1 } x _ { 0 } \| \leq \| z \| { \mathrm { ~ f o r ~ a l l ~ p o s i t i v e ~ i n t e g e r ~ } } n .
$$

That is, the sequence $\{ \| T ^ { n } x _ { 0 } \| _ { 1 } \}$ is monotone increasing and bounbed. So there is a real number $\gamma$ such that

$$
\operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } \| = \gamma \leq \| z \| .
$$

From the weakly lower semi-continuity of the norm, it follows that

$$
\| z \| _ { 1 } \leq \operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } \| = \operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } \| = \gamma \leq \| z \| ,
$$

and hence,

$$
\operatorname* { l i m } _ { n \to \infty } \| T ^ { n } x _ { 0 } \| = \| z \| .
$$

By Lemma 2.3 (iv), we have $\operatorname* { l i m } _ { n \to \infty } T ^ { n } x _ { 0 } = z$ . This completes the proof.

Theorem 4.4.Let $K$ be a nonempty closed convex subset of a uniformly convex Banach space $( E , \| \cdot \| )$ with the partial order $\because$ and let $T : K \to K$ be a monotone α-nonexpansive mapping. Assume that $0 \geq x _ { 0 } \geq T x _ { 0 }$ and the orbit $O ( x _ { 0 } )$ is bounded with respect to the norm $\| \cdot \|$ . If the norm $\| \cdot \|$ is monotonic, then $T ^ { n } x _ { 0 }$ strongly converges to some point $z \in F _ { \leq } ( T )$ ：

Proof. It follows from Theorem 4.2 that there exists $z \in F _ { \leq } ( T )$ such that $T ^ { n } x _ { 0 }$ weakly converges to $z$ and

（20 $0 \geq x _ { 0 } \geq T ^ { n } x _ { 0 } \geq T ^ { n + 1 } x _ { 0 } \geq z$ for all positive integer $n$ ：

Then

（204号 $0 \leq - x _ { 0 } \leq - T ^ { n } x _ { 0 } \leq - T ^ { n + 1 } x _ { 0 } \leq - z$ for all positive integer $n$ ，

and so,

$0 \leq \| x _ { 0 } \| \leq \| T ^ { n } x _ { 0 } \| \leq \| T ^ { n + 1 } x _ { 0 } \| \leq \| z \|$ for all positive integer $n$ ：

The remainder of the proof are the same as ones of Theorem 4.3, we omit it.

Combining Theroem 3.4 and 4.1, the following conclusion is easy to be showed.

Corollary 4.5. Let $( E , \| \cdot \| )$ be a uniformly convex Banach space with the partial order “≤" with respect to the closed convex cone $P$ and let $T : P  P$ be a monotone α-nonexpansive mapping with $F ( T ) \neq \emptyset$ . If the norm $\| \cdot \|$ is monotonic, then $T ^ { n } 0$ strongly converges to some point $z \in F ( T )$ ：

Corollary 4.6. Let $( E , \| \cdot \| )$ be a uniformly convex Banach space with the partial order “≤" with respect to the closed convex $P$ and let $T : P  P$ be a monotone nonexpansive mapping with $F ( T ) \neq \emptyset$ . If the norm $\| \cdot \|$ is monotonic, then for all $x \in P$ with $x \leq T x$ ， $T ^ { n } x$ strongly converges to some point $z \in F ( T )$ ·

Proof. It follows from Theroem 3.4 that the orbit $O ( 0 )$ is bounded with respect to the norm （204号 $\| \cdot \|$ . Then by the monotonicity of $T$ , for all $x \in P$ (i.e., $0 \leq x$ ), we have $T 0 \leq T x$ ， $T ^ { 2 } 0 \le T ^ { 2 } x$ ， and so by the same manner, we obtain

Since $T$ be a monotone nonexpansive mapping, we have

$$
\left\| T ^ { n } 0 - T ^ { n } x \right\| \leq \left\| T ^ { n - 1 } x - T ^ { n - 1 } 0 \right\| \leq \cdots \leq \left\| x - 0 \right\| = \left\| x \right\|
$$

So the orbit $O ( x )$ is bounded with respect to the norm $\| \cdot \|$ . Then the conclusion directly follows from Theorem 4.3. □

# References

[1] R. P. Agarwal, D. O'Regan, D.R. Sahu, Fixed point theory for Lipschitzian-type mappings with applications, Springer New York. 2009.   
[2] M. Bachar, M. A Khamsi, On common approximate fixed points of monotone nonexpansive semigroups in Banach spaces, Fixed Point Theory Appl. (2015) 2015:160.   
[3] V. Berinde, A convergence theorem for Mann iteration in the class of Zamfirescu operators,An. Univ. Vest Timi. Ser. Mat. Inform. 45 (2007),33-41.   
[4] B. A. B. Dehaish, M. A. Khamsi, Mann iteration process for monotone nonexpansive mappings, Fixed Point Theory Appl. (2015) 2015:177.   
[5] K. Deimling, Nonlinear Functional Analysis， Dover Publications Inc. Mineola, New York, 2010.   
[6] S. George, P. Shaini, Convergence theorems for the class of Zamfirescu operators, Int. Math. Forum 7 (2012), no. 33-36,1785-1792.   
[7] K. Goebel, W. A. Kirk, Topics in metric fixed point theory, Cambridge University Press, 1990.   
[8] A. B. George, C. A. Nse, A Monotonicity Condition for Strong Convergence of the Mann Iterative Sequence for Demicontractive Maps in Hilbert Spaces, Appl. Math. 5(2014), 2195-2198.   
[9] W. A. Kirk, B. Sims, Handbook of metric fixed point theory, Kluwer Academic Publishers,2001.   
[10] F. Gu, J. Lu, Stability of Mann and Ishikawa iterative processes with errors for a class of nonlinear variational inclusions problem, Math. Commun. 9(2004), 149-159.   
[11] J. S. Jung， Iterative approaches to common fixed points of nonexpansive mappings in Banach spaces, J. Math. Anal. Appl. 302(2005)， 509-520.   
[12] J. K. Kim, Z. Liu, Y. M. Nam, S. A. Chun， Strong convergence theorems and stability problems of Mann and Ishikawa iterative sequences for strictly hemi-contractive mappings J. Nonlinear Convex Anal. 5 (2004), 285-294.   
[13] F. Kohsaka and W. Takahashi， Existence and approximation of fixed points of firmly nonexpansive-type mappings in Banach spaces, SIAM J. Optim. 19 (2008), 824-835.   
[14] L.J. Lin and S.Y. Wang, Fixed point theorems for $( a , b )$ -monotone mapping mapping in Hilbert spaces, Fixed Point Theory Appl. 2012, 2012:131.   
[15] L. S. Liu, Ishikawa and Mann iteration process with errors for nonlinear strongly accretive mappings in Banach spaces, J. Math. Anal. Appl. 194(1995), 114-125.   
[16] W. R. Mann, Mean value methods in iteration, Proc. Amer. Math. Soc. 4(1953), 506- 510.   
[17] E. Naraghirad, N. C. Wong and J. C. Yao, Approximating fixed points ofα-nonexpansive mappings in uniformly convex Banach spaces and CAT(O) spaces, Fixed Point Theory Appl. (2013) 2013:57   
[18] G. A. Okeke, J. K. Kim， Convergence and summable almost T-stability of the random Picard-Mann hybrid iterative process, J. Inequal. Appl. (2015) 2015:290.   
[19] Z. Opial, Weak convergence of the sequence of successive approximations for nonexpansive mappings in Banach spaces, Bull. Amer. Math. Soc. 73(1967), 591-597.   
[20] A. Pazy, Asymptotic behavior of contractions in Hilbert spaces, Israel J. Math. 9(1971), 335-340.   
[21] Y. Song, K. Promluang, P. Kumam, Y.J. Cho, Some convergence theorems of the Mann iteration for monotone α-nonexpansive mappings, Appl. Math. Comput. 287-288(2016), 74-82.   
[22] Y. Song, P. Kumam, Y.J. Cho, Fixed point theorems and iterative approximations for monotone nonexpansive mappings in ordered Banach spaces, Fixed Point Theory and Applications DOI: 10.1186/s13663-016-0563-y   
[23] Y. Song, H. Wang， Strong convergence for the modified Mann's iteration of X-strict pseudocontraction, Appl. Math. Comput. 237 (2014), 405-410.   
[24] Y. Song, Weak and strong convergence of Mann's-type iterations for a countable family of nonexpansive mappings, J. Korean Math. Soc. 45(2008), 1393-1404.   
[25] J. Sun, Nonlinear Functional Analysis and Its Application (In Chinese), Beijing, Science Publishing House, 2008.   
[26] T. Suzuki, Strong convergence of Krasnoselskii and Mann’s sequences for one-parameter nonexpansive semigroups without Bochner integrals, J. Math. Anal. Appl. 305 (2005), 227-239.   
[27] W. Takahashi, Nonlinear Functional Analysis-Fixed Point Theory and its Applications, Yokohama Publishers inc, Yokohama, 2000.   
[28] W. Takahashi, Fixed point theorems for new nonlinear mappings in a Hilbert space, J. Nonlinear Convex Anal. 11 (2010), 79-88.   
[29] W. Takahashi and J.C. Yao, Fixed point theorems and ergodic theorems for nonlinear mappings in a Hilbert space, Taiwan. J. Math. 15 (2011), 457-472.   
[30] H. K. Xu, Inequality in Banach spaces with applications, Nonlinear Anal. 16(1991), 1127-1138.   
[31] H. Zhang, Y. Su, Convergence theorems for strict pseudo-contractions in q-uniformly smooth Banach spaces, Nonlinear Anal. 71(2009)， 4572-4580.   
[32] H. Zhou, M. Zhang, H. Zhou, A convergence theorem on Mann iteration for strictly pseudo-contraction mappings in Hilbert spaces, (Chinese) J. Hebei Univ. Nat. Sci. 26(2006), 348-349.

[33] H. Zhou, Convergence theorems for X-strict pseudo-contractions in 2-uniformly smooth Banach spaces, Nonlinear Anal. 69(2008), 3160-3173.