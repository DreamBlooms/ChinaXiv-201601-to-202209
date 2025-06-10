# Wasserstein metric between a discrete probability measure and a continuous one

Weihua Yang and Xia Wang

December16,2021

# Abstract

The paper considers Wasserstein metric between the empirical probability measure of n discrete random variables and a continuous uniform one on the d-dimensional ball and give the asymptotic estimation of their expectation as $n \to \infty$ . Further We considers the above problem on a mixed process, i.e.,n discrete random variables are produced by the Poisson process.

Keywords:Wasserstein metric;optimal matching; from discrete to continuous; random variable；Poisson process.

# 1Introduction

Article [1] studied Olivier curvature of random geometric graphs,a key step in which is building up the estimation of Wasserstein metric between the empirical probability measure of n discrete random variables and a continuous uniform one on the d-dimensional ball and authors applied results in [5],but which are building on $[ 0 , 1 ] ^ { d }$ versus Ollivier curvature is built on balls,so the proof process in [1] seems tedious and vulnerable.Another hand,Lattice method in statistical mechanical approach [6] often involve similar notation and convergence froma discrete physical quantity to a continuous one,which should exist close links with the convergence from a discrete probability to a continuous one.Allinspire us to study approach problem between the discrete probability and the continuous one,in this article we choose the Wasserstein metric as the approach measure,by which we hope to build a bridge in studying the relation between a discrete quantity to a continuous one in more scenes.

# 2 Preliminary Estimation

Definiton 1. Let $X _ { 1 } , X _ { 2 } , \cdot \cdot \cdot , X _ { n } , Y _ { 1 } , X _ { 2 } , \cdot \cdot \cdot , Y _ { n }$ be independent uniformly distributed random variables on the $d$ -dimensional $B ( 0 ; 1 ) = \{ x \in R ^ { d } , \| x \| \leq 1 \} , d \geq 2$ ，where $\| \cdot \|$ is a norm on $R ^ { d }$ . The random variable $M _ { n } ^ { d } : = \operatorname* { i n f } _ { \sigma } \sum _ { i = 1 } ^ { n } \| X _ { i } - Y _ { \sigma ( i ) } \|$ denotes the optimal matching betwen $X _ { 1 } , X _ { 2 } , \cdots , X _ { n }$ and $Y _ { 1 } , Y _ { 2 } , \cdots , Y _ { n }$ ， where $\sigma$ takes over all permutations of $\{ 1 , 2 , \cdots , n \}$

By dual principle [2,3],one has

$$
M _ { n } ^ { d } = \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } \sum _ { i = 1 } ^ { n } ( f ( X _ { i } ) - f ( Y _ { i } ) ) = \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } | \sum _ { i = 1 } ^ { n } ( f ( X _ { i } ) - f ( Y _ { i } ) ) | ,
$$

where the set of Lipschitz functions $\mathcal { L } _ { 1 } = \{ f : B ( 0 ; 1 ) \to R ; | f ( x ) - f ( y ) | \leq \| x - y \| , \forall x , y \in B ( 0 ; 1 ) , f ( 0 ) =$ $0 \}$ . Notice every Lipschitz function in $\mathcal { L } _ { 1 }$ may extend to one in

$$
\begin{array} { r } { \mathcal { L } = \{ f : R ^ { d } \to R ; | f ( x ) - f ( y ) | \leq \| x - y \| , \forall x , y \in R ^ { d } , f ( 0 ) = 0 , \| f \| _ { L ^ { \infty } } \leq 1 \} , } \end{array}
$$

s0 $\mathcal { L } _ { 1 } = \mathcal { L } | _ { B ( 0 ; 1 ) }$ . The follwing Lemma 1 gives a upper and lower bound estimation for the expectation $E ( M _ { n } ^ { d } )$

Lemma 1 (optimal-matching). For the above optimal matching, one has for the dimension $d \geq 2$ （20

$$
1 - { \frac { 1 } { d + 1 } } \leq \operatorname* { l i m i n f } _ { n  \infty } { \frac { E ( M _ { n } ^ { d } ) } { n ^ { 1 - { \frac { 1 } { d } } } } } \leq \operatorname* { l i m s u p } _ { n  \infty } { \frac { E ( M _ { n } ^ { d } ) } { n ^ { 1 - { \frac { 1 } { d } } } } } \leq 2 d + 5 + 8 { \sqrt { 2 } } .
$$

Proof. we put the proof in appendix. The method is essentially from [5], we make some improvement and nodification for extending it to random variables on balls.

# 3 Main results and proofs

The following are results on the Wasserstein metric between empirical and uniform measures on the ddimensional ball. In general, the Wasserstein metric between two probability $\mu _ { 1 } , \mu _ { 2 }$ is given by the following definition.

Definiton 2.Let $\mu _ { 1 }$ and $\mu _ { 2 }$ be Borel probability measures on a compact metric space $( \mathcal { X } , d )$ and let （204号 $\Gamma ( \mu _ { 1 } , \mu _ { 2 } )$ denote the set of joint probability $\mu$ between $\mu _ { 1 }$ and $\mu _ { 2 }$ , whose marginals are $\mu _ { 1 }$ and $\mu _ { 2 }$ respectively. The Wasserstein metric is defined by

$$
W ( \mu _ { 1 } , \mu _ { 2 } ) = \operatorname* { i n f } _ { \mu \in \Gamma ( \mu _ { 1 } , \mu _ { 2 } ) } \int _ { \mathcal { X } \times \mathcal { X } } d ( x , y ) d \mu ( x , y ) .
$$

By duality principle (Kantorovich Dual Theorem) $[ 7 ]$ ， Wasserstein metric can be expressed as

$$
W ( \mu _ { 1 } , \mu _ { 2 } ) = \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } ( { \mathcal { X } } ) } \left( \int _ { { \mathcal { X } } } f ( x ) d \mu _ { 1 } ( x ) - \int _ { { \mathcal { X } } } f ( y ) d \mu _ { 2 } ( y ) \right) ,
$$

where $\mathcal { L } _ { 1 } ( \mathcal { X } )$ denotes the set ofLipschitz functions about metric on $\mathcal { X }$ with the coefficient 1.From the above duality formula, we may further assume $\mathcal { L } _ { 1 } ( \mathcal { X } )$ with the additional condition that is any $f \in \mathcal { L } _ { 1 } ( \mathcal { X } )$ satisfying $f ( 0 ) = 0$

Notice: In below all metrics are induced by some norms.To keep uniform math notation with most original articles,we still use $\mathit { \Delta } ^ { \circ } d ^ { \prime }$ expressed the metric in a space that shouldn't arise confusion with the dimension notation.

Theorem1.Let $X _ { 1 } , X _ { 2 } , \cdots , X _ { n }$ be independent uniformly distributed random variables on the d-dimensional ball $B ( 0 ; 1 )$ ，let $m _ { n } ^ { d }$ denote the empirical measure

$$
m _ { n } ^ { d } ( y ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } 1 _ { y = X _ { i } }
$$

and $\mu ^ { d }$ the uniform measure on $B ( 0 ; 1 )$ . Then as $n \to \infty$ ，

$$
E [ W ^ { d } ( m _ { n } ^ { d } , \mu ^ { d } ) ] = O ( n ^ { - \frac { 1 } { d } } ) , d \geq 2 .
$$

Proof.

$$
\begin{array} { l } { { \displaystyle W ^ { d } ( m _ { n } ^ { d } , \mu ^ { d } ) = \operatorname* { i n f } _ { \mu \in \Gamma ( m _ { n } ^ { d } , \mu ^ { d } ) } \int _ { B ( 0 ; 1 ) \times B ( 0 ; 1 ) } d ( x , y ) d \mu ( x , y ) } } \\ { { \displaystyle \quad \quad = \operatorname* { s u p } _ { f \in \mathcal { L } _ { 1 } ( B ( 0 ; 1 ) ) } \left( \int _ { B ( 0 ; 1 ) } f ( x ) d m _ { n } ^ { d } ( x ) - \int _ { B ( 0 ; 1 ) } f ( y ) d \mu ^ { d } ( y ) \right) . } } \end{array}
$$

Let $Y _ { 1 } , Y _ { 2 } , \cdots , Y _ { n }$ be independent uniformly distributed random variables on $B ( 0 ; 1 )$ ，then

$$
\int _ { B ( 0 ; 1 ) } f ( y ) d \mu ^ { d } ( y ) = E [ f ( Y _ { i } ) ] , i = 1 , \cdot \cdot \cdot , n .
$$

So

$$
\begin{array} { r l } { \mathbb { W } ^ { \delta } \{ \mathbf { n } _ { n } ^ { \theta } , \boldsymbol { q } ^ { \delta } \} = } & { \underset { f \in \mathcal { L } _ { n } ^ { 2 } \times \{ 0 , 1 : 1 \} } { \operatorname* { s u p } } \left( \int _ { \mathbb { R } ( n + 1 ) } f ( x ) d w _ { n } ^ { \delta } ( x ) - \int _ { B ( 1 , 1 ) } f ( y ) d w ^ { \delta } ( y ) \right) } \\ & { = \frac { 1 } { n } \underset { f \in \mathcal { L } _ { n } ^ { 2 } \times \{ 0 , 1 : 1 \} } { \operatorname* { s u p } } \left( \underset { \mathbb { S } = 1 } { \sum } \{ f ( X _ { \delta } ) - E \{ f ( X _ { \delta } ) \} \} \right) } \\ & { = \frac { 1 } { n } \underset { f \in \mathcal { L } _ { n } ^ { 2 } \times \{ 0 , 1 : 1 \} } { \operatorname* { s u p } } \left( \underset { \mathbb { S } = 1 } { \sum } E [ \{ X ( x ) - f ( Y ) \} | X _ { \delta } ] \right) } \\ & { = \frac { 1 } { n } \underset { f \in \mathcal { L } _ { n } ^ { 2 } \times \{ 0 , 1 : 1 \} } { \operatorname* { s u p } } \left( \underset { \mathbb { S } = 1 } { \sum } \{ f ( X _ { \delta } ) - f ( Y ) \} \right) \times \Biggr ] } \\ & { = \frac { 1 } { n } \underset { f \in \mathcal { L } _ { n } ^ { 2 } \times \{ 0 , 1 : 1 \} } { \operatorname* { s u p } } \left[ \underset { \sum _ { i = 1 } ^ { n } \operatorname* { s u p } } { \sum } \{ f ( X ( x ) - f ( Y ) ) \} \right] } \\ & { \leq \frac { 1 } { n } \frac { 1 } { n } \left[ \left( \int _ { f } \underset { f \in \mathcal { L } _ { n } ^ { 2 } \times \{ 0 , 1 : 1 \} } { \operatorname* { s u p } } \right) \underset { i = 1 } { \sum } \{ f ( X _ { \delta } ) - f ( Y _ { \delta } ) \} \right) \times \Biggr ] } \\ & { = \frac { 1 } { n } \frac { \varepsilon } { n } \left[ \left( \mathcal { R } _ { n } ^ { \delta } \big | \mathbf { x } \right) \right] , } \end{array}
$$

hence from lemma $^ { 1 }$ ,one has

$$
E [ W ^ { d } ( m _ { n } ^ { d } , \mu ^ { d } ) ] \leq \frac { 1 } { n } E [ M _ { n } ^ { d } ] = O ( n ^ { - \frac { 1 } { d } } ) .
$$

Corollary 1. Generally, let $X _ { 1 } , X _ { 2 } , \cdots , X _ { n }$ be independent uniformly distributed random variables on the $d$ -dimensional ball $B ( 0 , \delta )$ with radius $\delta > 0$ ，and $m _ { n } ^ { d }$ denote the empirical measure

$$
m _ { n } ^ { d } ( y ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } 1 _ { y = X _ { i } } ,
$$

and $\mu ^ { d }$ the uniform measure on $B ( 0 , \delta )$ . Then

$$
E [ W ^ { d } ( m _ { n } ^ { d } , \mu ^ { d } ) ] = \delta { \cal O } ( n ^ { - \frac { 1 } { d } } ) , d \geq 2 .
$$

Proof. Let $y = \delta t$ and denote

$$
\bar { m } _ { n } ^ { d } ( t ) = \delta ^ { d } m _ { n } ^ { d } ( \delta t ) = \delta ^ { d } \frac { 1 } { n } \sum _ { i = 1 } ^ { n } 1 _ { \delta t = X _ { i } } , \bar { \mu } ^ { d } ( t ) = \delta ^ { d } \mu ^ { d } ( \delta t ) ,
$$

then ${ \bar { m } } _ { n } ^ { d } , { \bar { \mu } } ^ { d }$ are empirical and uniform measures respectively about variable $t$ on $B ( 0 ; 1 )$ . Especially one has

$$
\begin{array} { l l } { { { \displaystyle { \cal W } ^ { d } ( m _ { n } ^ { d } , \mu ^ { d } ) = \operatorname * { i n f } _ { \mu \in \Gamma ( m _ { n } ^ { d } , \mu ^ { d } ) } \int _ { B ( 0 , \delta ) \times B ( 0 , \delta ) } d ( x , y ) \mu ( x , y ) d x d y } } } \\ { { { } } } & { { { } = \operatorname * { i n f } _ { \mu \in \Gamma ( m _ { n } ^ { d } , \mu ^ { d } ) } \int _ { B ( 0 ; 1 ) \times B ( 0 ; 1 ) } d ( \delta t , \delta \tau ) \mu ( \delta t , \delta \tau ) \delta ^ { 2 d } d t d \tau } } \\ { { { } } } & { { { } = \displaystyle { \operatorname * { i n f } _ { \bar { \mu } \in \Gamma ( \bar { m } _ { n } ^ { d } , \bar { \mu } ^ { d } ) } \int _ { B ( 0 ; 1 ) \times B ( 0 ; 1 ) } \delta d ( t , \tau ) \bar { \mu } ( t , \tau ) d t d \tau } } } \\ { { { } } } & { { { } = \delta { \cal W } ^ { d } ( \bar { m } _ { n } ^ { d } , \bar { \mu } ^ { d } ) . } } \end{array}
$$

So

$$
E [ W ^ { d } ( m _ { n } ^ { d } , \mu ^ { d } ) ] = \delta { \cal O } ( n ^ { - \frac { 1 } { d } } ) , d \geq 2 .
$$

Theorem 2. Consider a Poisson process $\mathcal { P }$ with intensity measure $\begin{array} { r l } {  { ( 1 + \alpha _ { n } ) n \frac { d V _ { d } } { | B ( 0 ; 1 ) | } } } \end{array}$ on $d$ -dimensional ball $B ( 0 ; 1 )$ , for some sequence $0 \leq \alpha _ { n }  0$ .Let $m _ { \mathcal { P } } ^ { d }$ denote the empirical random measure with respect to $\mathcal { P }$ ， i.e.

$$
m _ { \mathcal { P } } ^ { d } ( y ) = \frac { 1 } { | \mathcal { P } | } \sum _ { p \in \mathcal { P } } 1 _ { y = p } ,
$$

and $\mu ^ { d }$ the uniform measure on the above ball. Then

$$
E [ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) ] = O ( n ^ { - \frac { 1 } { d } } ) .
$$

Proof. Since the size of random variables about $m _ { \mathcal { P } } ^ { d }$ is produced by mixed random process $\mathcal { S }$ ，so

$$
E [ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) ] = \sum _ { k = 1 } ^ { \infty } E [ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) \big | | \mathcal { P } | = k ] \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) = k ) .
$$

From Theorem 1,we know

$$
E [ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) \vert \vert \mathcal { P } \vert = k ] = O ( k ^ { - \frac { 1 } { d } } ) .
$$

Another hand, from lemma 1.2 in [4] one has

$$
\begin{array} { r l } & { ( 1 + \alpha _ { n } ) n ) > ( 1 + \alpha _ { n } ) n + c \sqrt { ( 1 + \alpha _ { n } ) n \log n } ) \leq e ^ { c \sqrt { ( 1 + \alpha _ { n } ) n \log n } + \left( ( 1 + \alpha _ { n } ) n + c \sqrt { ( 1 + \alpha _ { n } ) n \log n } \right) \log } } \\ & { \qquad \leq e ^ { - \frac { e ^ { 2 } ( 1 + \alpha _ { n } ) n \log n } { 2 \left( ( 1 + \alpha _ { n } ) n + c \sqrt { ( 1 + \alpha _ { n } ) n \log n } \right) } } = O ( n ^ { - \frac { c ^ { 2 } } { 3 } } ) } \end{array}
$$

where $c$ is a constant determined later,and

P(Po(1+ $\begin{array} { r } { x _ { n } ) n ) < ( 1 + \alpha _ { n } ) n - c \sqrt { ( 1 + \alpha _ { n } ) n \log n } ) \leq e ^ { - c \sqrt { ( 1 + \alpha _ { n } ) n \log n } + \left( ( 1 + \alpha _ { n } ) n - c \sqrt { ( 1 + \alpha _ { n } ) n \log n } \right) \log \frac { ( 1 + \alpha _ { n } ) } { ( 1 + \alpha _ { n } ) n - c \sqrt { ( 1 + \alpha _ { n } ) n \log n } } } } \end{array}$ Fa)mlg = 0(n-²）. (6)

Denote

$$
a _ { n } ^ { \pm } = [ ( 1 + \alpha _ { n } ) n \pm c \sqrt { ( 1 + \alpha _ { n } ) n \log n } ] .
$$

Then

$$
\begin{array} { r l } { E [ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) ] = \displaystyle \sum _ { k = 1 } ^ { a _ { n } ^ { - 1 } - 1 } E \left[ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) \big | | \mathcal { P } | = k \right] \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) = k ) } & { } \\ { \displaystyle } & { + \displaystyle \sum _ { k = a _ { n } ^ { - 1 } } ^ { a _ { n } ^ { + } } E \left[ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) \big | | \mathcal { P } | = k \right] \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) = k ) } \\ { \displaystyle } & { + \displaystyle \sum _ { k = a _ { n } ^ { + } + 1 } ^ { \infty } E \left[ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) \big | | \mathcal { P } | = k \right] \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) = k ) } \\ { \displaystyle } & { : = I _ { 1 } + I _ { 2 } + I _ { 3 } . } \end{array}
$$

Hence

$$
\therefore \sum _ { k = 1 } ^ { a _ { n } ^ { - } - 1 } E \left[ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) | | \mathcal { P } | = k \right] \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) = k ) \leq 2 \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) < a _ { n } ^ { - } ) = O ( n ^ { - \alpha } ) .
$$

and

$$
{ I } _ { 3 } = \sum _ { k = \alpha _ { n } ^ { + } + 1 } ^ { \infty } E \left[ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) \big | | \mathcal { P } | = k \right] \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) = k ) \leq 2 \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) > a _ { n } ^ { + } ) = O \delta _ { 1 } \operatorname { i n f } ( ( \alpha _ { 1 } - \alpha _ { n } ) n ) .
$$

The last part $I _ { 2 }$ , one has

$$
\begin{array} { r l } {  { I _ { 2 } = \sum _ { k = a _ { n } ^ { - } } ^ { a _ { n } ^ { + } } E [ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) \big | | \mathcal { P } | = k ] \mathbb { P } ( P o ( ( 1 + \alpha _ { n } ) n ) = k ) } } \\ & { = \sum _ { k = a _ { n } ^ { - } } ^ { a _ { n } ^ { + } } O ( k ^ { - \frac { 1 } { d } } ) \frac { e ^ { - ( 1 + \alpha _ { n } ) n } ( ( 1 + \alpha _ { n } ) n ) ^ { k } } { k ! } } \\ & { \leq O ( ( ( 1 + \alpha _ { n } ) n - c \sqrt { ( 1 + \alpha _ { n } ) n \log n } ) ^ { - \frac { 1 } { d } } ) = O ( n ^ { - \frac { 1 } { d } } ) . } \end{array}
$$

Finally one has for some adjusted $c$

$$
E [ W ( m _ { \mathcal { P } } ^ { d } , \mu ^ { d } ) ] = O ( n ^ { - \frac { 1 } { d } } )
$$

Corollary 2.Let $0 \leq \alpha _ { n }  0 , x \in R ^ { d }$ and consider a Poisson process $P$ with intensity measure $( 1 +$ $\begin{array} { r } { \alpha _ { n } ) n \frac { d V _ { d } } { | B ( 0 ; 1 ) | } } \end{array}$ on the $d$ -dimensional ball $\boldsymbol { B } ( \boldsymbol { x } ; \delta )$ with the radius $\delta > 0$ Let $m _ { x } ^ { d }$ denote the empirical measure with respect to $P$ ,i.e.

$$
m _ { x } ^ { d } ( y ) = \frac { 1 } { | \mathcal { P } | } \sum _ { p \in \mathcal { P } } 1 _ { y = p } ,
$$

and $\mu _ { x } ^ { d }$ the uniform measure on $B ( x ; \delta )$ . Then

$$
E [ W ^ { d } ( m _ { x } ^ { d } , \mu _ { x } ^ { d } ) ] = O ( n ^ { - \frac { 1 } { d } } ) .
$$

Proof.As the proof in Theorem 2. First it has the size $| \mathcal { P } |$ a Poisson distribution on $B ( x ; \delta )$ with mean value $( 1 + \alpha _ { n } ) n \delta ^ { d }$ . So

$$
E [ W ^ { d } ( m _ { x } ^ { d } , \mu _ { x } ^ { d } ) ] = E [ \delta W ^ { d } ( \bar { m } _ { x } ^ { d } , \bar { \mu } _ { x } ^ { d } ) ] = \delta E [ W ^ { d } ( \bar { m } _ { x } ^ { d } , \bar { \mu } _ { x } ^ { d } ) ] = \delta O ( ( n \delta ^ { d } ) ^ { - \frac { 1 } { d } } ) = O ( n ^ { - \frac { 1 } { d } } ) .
$$

ConclusionCorollary 2 may be directly applied to get the Appendix A.3 in [1]. Next we hope to apply our method to analyze electrostatic approach problem.

# AThe lower bound of $E ( M _ { n } ^ { d } )$

Since $\begin{array} { r } { M _ { n } ^ { d } = \operatorname* { i n f } _ { \sigma } \sum _ { i = 1 } ^ { n } \| X _ { i } - Y _ { \sigma ( i ) } \| \ge \operatorname* { i n f } _ { \sigma } \sum _ { i = 1 } ^ { n } \operatorname* { m i n } _ { j \le n } \| X _ { i } - Y _ { j } \| = \sum _ { i = 1 } ^ { n } \operatorname* { m i n } _ { j \le n } \| X _ { i } - Y _ { j } \| . } \end{array}$ one has

$$
E ( M _ { n } ^ { d } | X ) \geq \sum _ { i = 1 } ^ { n } { E ( \operatorname* { m i n } _ { j \leq n } \| X _ { i } - Y _ { j } \| \big | X ) } \geq n \operatorname* { m i n } _ { x \in D } { E ( \operatorname* { m i n } _ { j \leq n } \| x - Y _ { j } \| ) } .
$$

Let $B ( x , t ) = \{ y \in R ^ { d } : \| x - y \| \leq t \}$ , then $\begin{array} { r } { \frac { | B ( x , t ) \cap B ( 0 ; 1 ) | } { | B ( 0 ; 1 ) | } \leq \mathrm { m i n } \{ t ^ { d } , 1 \} } \end{array}$ and $\begin{array} { r } { P ( \operatorname* { m i n } _ { j \leq n } | | x - Y _ { j } | | \geq t ) \geq ( 1 - t ^ { d } ) ^ { n } } \end{array}$ for $t < 1$ . Thus

$$
E ( \operatorname* { m i n } _ { j \leq n } \| x - Y _ { j } \| ) = \int _ { 0 } ^ { \infty } P ( \operatorname* { m i n } _ { j \leq n } \| x - Y _ { j } \| \geq t ) d t \geq \int _ { 0 } ^ { 1 } ( 1 - t ^ { d } ) ^ { n } d t \overset { t = n ^ { - 1 / d _ { u } } } { = } \pi ^ { - 1 / d } \int _ { 0 } ^ { n ^ { 1 / d } } ( 1 - u ^ { d } ) d u .
$$

Finally by Fatou lemma, one has

$$
\operatorname* { l i m i n f } _ { n \to \infty } \frac { E ( M _ { n } ^ { d } ) } { n ^ { 1 - \frac { 1 } { d } } } \geq \int _ { 0 } ^ { \infty } e ^ { - u ^ { d } } \geq 1 - \frac { 1 } { d + 1 } .
$$

# B The upper bound of $E ( M _ { n } ^ { d } )$

Set $\begin{array} { r } { r = \frac { 1 } { n ^ { \frac { 1 } { d } } } } \end{array}$ so $r  0$ as $n \to \infty$ and $\begin{array} { r } { | B ( x , r ) | = \frac { 1 } { n } \omega _ { d } } \end{array}$ ,where $\omega _ { d } = | B ( 0 ; 1 ) |$ . Set

$$
u ( i , j ) = { \left\{ \begin{array} { l l } { 1 , } & { { \mathrm { i f ~ } } \| X _ { i } - Y _ { j } \| \leq r } \\ { 0 , } & { { \mathrm { o t h e r w i s e } } } \end{array} \right. }
$$

Set

$$
b ( \boldsymbol { x } ) = \frac { | B ( \boldsymbol { x } , r ) \cap B ( 0 ; 1 ) | } { | B ( 0 ; 1 ) | } ,
$$

then $\textstyle b ( x ) \leq { \frac { 1 } { n } } < 1$ if $n > 1$ . First decomposed $\textstyle \sum _ { i \leq n } ( f ( X _ { i } ) - f ( Y _ { i } ) )$ as follows

$$
\sum _ { i \leq n } ( f ( X _ { i } ) - f ( Y _ { i } ) ) = \sum _ { i \leq n } f ( X _ { i } ) \sum _ { j \leq n } u ( i , j ) - \sum _ { j \leq n } f ( Y _ { j } ) \sum _ { i \leq n } u ( i , j ) + \sum _ { i \leq n } f ( X _ { i } ) ( 1 - \sum _ { j \leq n } u ( i , j ) ) - \sum _ { j \leq n } f ( Y _ { j } ) |
$$

so one has

$$
\begin{array} { l } { { \displaystyle \sum _ { i } ( f ( X _ { i } ) - f ( Y _ { i } ) ) | \le | \displaystyle \sum _ { i \leq n } f ( X _ { i } ) \sum _ { j \leq n } u ( i , j ) - \sum _ { j \leq n } f ( Y _ { j } ) \sum _ { i \leq n } u ( i , j ) | + | \displaystyle \sum _ { i \leq n } f ( X _ { i } ) ( 1 - \sum _ { j \leq n } u ( i , j ) ) - \sum _ { j \leq n } f ( Y _ { j } ) \sum _ { i \leq n } u ( i , j ) | } } \\ { { \displaystyle : = I _ { 1 } + I _ { 2 } . } } \end{array}
$$

Further we will run two parts estimation of $E \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } I _ { 1 }$ and $E \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } I _ { 2 }$ and finally get

$$
E ( M _ { n } ^ { d } ) = E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } | \sum _ { i \leq n } ( f ( X _ { i } ) - f ( Y _ { i } ) ) | \leq E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 1 } + E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 2 } \leq n ^ { 1 - \frac { 1 } { d } } + 2 d n ^ { 1 - \frac { 1 } { d } } + 4 n ^ { 1 - \frac { 1 } { d } } + 8 \sqrt { 2 } n ^ { 1 - \frac { 3 } { d } }
$$

hence one has

$$
{ \frac { E ( M _ { n } ^ { d } ) } { n ^ { 1 - { \frac { 1 } { d } } } } } \leq 1 + 2 d + 4 + 8 { \sqrt { 2 } } n ^ { { \frac { 1 } { d } } - { \frac { 1 } { 2 } } } = 5 + 2 d + 8 { \sqrt { 2 } } n ^ { { \frac { 1 } { d } } - { \frac { 1 } { 2 } } } .
$$

# B.1 The estimation of E supf∈£1 I1

$$
\begin{array} { r } { \iota _ { 1 } = \displaystyle | \displaystyle \sum _ { i \leq n } f ( X _ { i } ) \sum _ { j \leq n } u ( i , j ) - \displaystyle \sum _ { j \leq n } f ( Y _ { j } ) \sum _ { i \leq n } u ( i , j ) | = | \displaystyle \sum _ { i \leq n } \sum _ { j \leq n } u ( i , j ) ( f ( X _ { i } ) - f ( Y _ { j } ) ) | \leq r \displaystyle \sum _ { i \leq n } \sum _ { j \leq n } u ( i , j ) \leq r \displaystyle \sum _ { i \leq n } \sum _ { j \leq n } \sum _ { i \leq n } \sum _ { j \leq n } \mu ( i , j ) \sum _ { i \leq n } \mu ( i , j ) \lambda ( \lambda ( \lambda ( \lambda ( \lambda ( \lambda ) ) ) ) ) } \end{array}
$$

Since $f$ is Lipschitz,

$$
\leq r \sum _ { i \leq n } \sum _ { j \leq n } E u ( i , j ) = r \sum _ { i \leq n } \sum _ { j \leq n } E \left( E \left( u ( i , j ) | X _ { i } \right) \right) = r \sum _ { i \leq n } \sum _ { j \leq n } E ( b ( X _ { i } ) ) \leq r \sum _ { i \leq n } \sum _ { j \leq n } { \frac { 1 } { n } } = n ^ { 1 - { \frac { 1 } { d } } } .
$$

Notice the estimation of $I _ { 1 }$ may further optimize,refer to [5].

# B.2 The estimation of E supf∈£1 I2

Decomposed $I _ { 2 }$ as follows

$$
\begin{array} { r l } & { \quad \displaystyle \left. \sum _ { i \leq n } f ( X _ { i } ) \left( 1 - n b ( X _ { i } ) \right) - \displaystyle \sum _ { j \leq n } f ( Y _ { j } ) \left( 1 - n b ( Y _ { j } ) \right) \right. + \displaystyle \left. \sum _ { i \leq n } f ( X _ { i } ) \left( n b ( X _ { i } ) - \sum _ { j \leq n } u ( i , j ) \right) \right. + \displaystyle \left. \sum _ { j \leq n } f ( Y _ { j } ) \right. } \\ & { = I _ { 2 1 } + I _ { 2 2 } + I _ { 2 3 } . } \end{array}
$$

We will run the estimation for these three parts and finally get

$$
E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 2 } \leq E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 2 1 } + E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 2 2 } + E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 2 3 } \leq 2 d n ^ { 1 - \frac { 1 } { d } } + 4 n ^ { 1 - \frac { 1 } { d } } + 8 \sqrt { 2 } n ^ { \frac { 1 } { 2 } } .
$$

# B.2.1 The estimation of $E \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } I _ { 2 1 }$

Notice $\| f \| _ { L ^ { \infty } [ B ( 0 ; 1 ) ] } \le 1$ and the value of $b ( X _ { i } )$ on $B ( 0 ; 1 )$ , one has

$$
\operatorname* { s u p } _ { \in { \mathcal { L } } _ { 1 } } \bigg ( \big | \sum _ { i \leq n } f ( X _ { i } ) \big ( 1 - n b ( X _ { i } ) \big ) \big | \bigg ) \leq E \bigg ( \sum _ { i \leq n } \big | 1 - n b ( X _ { i } ) \big | \bigg ) = \sum _ { i \leq n } E \bigg ( \big | 1 - n b ( X _ { i } ) \big | \bigg ) \leq n d r = d n
$$

so we can get

$$
\begin{array} { r c l } { E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 2 1 } } & { = } & { E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } \left( \big | \underset { i \leq n } { \sum } f ( X _ { i } ) \big ( 1 - n b ( X _ { i } ) \big ) - \underset { j \leq n } { \sum } f ( Y _ { j } ) \big ( 1 - n b ( Y _ { j } ) \big ) \big | \right) } \\ & { \leq } & { E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } \big | \underset { i \leq n } { \sum } f ( X _ { i } ) \big ( 1 - n b ( X _ { i } ) \big ) \big | + E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } \big | \underset { j \leq n } { \sum } f ( Y _ { j } ) \big ( 1 - n b ( Y _ { j } ) \big ) \big | } \\ & { \leq } & { 2 d n ^ { 1 - \frac { 1 } { d } } , } \end{array}
$$

B.2.2 The estimation of $\begin{array} { r } { E \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } I _ { 2 2 } , E \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } I _ { 2 3 } } \end{array}$

This part estimation is diffcult and one may use the convolution decomposition to impose $f$ on small areas, then there will has the below estimation

$$
E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } I _ { 2 2 } = E \underset { f \in L _ { 1 } } { \operatorname* { s u p } } I _ { 2 3 } = E \underset { f \in \mathcal { L } _ { 1 } } { \operatorname* { s u p } } \left( | \sum _ { i \leq n } f ( X _ { i } ) \big ( n b ( X _ { i } ) - \sum _ { j \leq n } u ( i , j ) \big ) | \right) \leq 2 n ^ { 1 - \frac { 1 } { a } } + 4 \sqrt { 2 } n ^ { \frac { 1 } { 2 } } .
$$

First we assume $f$ an indicator function on some set $A$ , and estimate $\begin{array} { r } { E \biggl ( \big | \sum _ { i \leq n } 1 _ { A } ( X _ { i } ) \bigl ( n b ( X _ { i } ) - \sum _ { j \leq n } u ( i , j ) \bigr ) \big | ^ { 2 } \biggr ) . } \end{array}$

So one has

$$
\sum _ { i \leq n } 1 _ { A } ( X _ { i } ) { \big ( } n b ( X _ { i } ) - \sum _ { j \leq n } u ( i , j ) { \big ) } | ^ { 2 } ) = E ( \sum _ { i , i ^ { \prime } \leq n } \sum _ { j , j ^ { \prime } \leq n } 1 _ { A } ( X _ { i } ) { \big ( } b ( X _ { i } ) - u ( i , j ) { \big ) } 1 _ { A } ( X _ { i ^ { \prime } } ) { \big ( } b ( X _ { i ^ { \prime } } ) - u ( i ^ { \prime } , j ) { \big ) } 1 _ { B } ( X _ { i ^ { \prime } } ) )
$$

Discussing as different cases of $i , i ^ { \prime } , j , j ^ { \prime }$ , there has

$$
E \bigg ( \Big | \sum _ { i \leq n } \sum _ { j \leq n } 1 _ { A } ( X _ { i } ) \left( b ( X _ { i } ) - u ( i , j ) \right) \Big | ^ { 2 } \bigg ) \leq n ^ { 2 } ( n - 1 ) \frac { | A | } { | B ( 0 ; 1 ) | } \frac { 1 } { n ^ { 2 } } + n ^ { 2 } \frac { | A | } { | B ( 0 ; 1 ) | } \frac { 1 } { n } \leq 2 n \frac { | A | } { | B ( 0 ; 1 ) | }
$$

Second we consider convolution. Let $g$ is bounded Lipschitz in $R ^ { d }$ ， $h$ a bounded support function in $R ^ { d }$ and $\begin{array} { r } { g * h ( x ) = \int _ { R ^ { n } } g ( t ) h ( x - t ) d t } \end{array}$ to estimate the expectation of

$$
{ \big | } \sum _ { i \leq n } g * h ( X _ { i } ) \sum _ { j \leq n } { \big ( } b ( X _ { i } ) - u ( i , j ) { \big ) } { \big | } = { \big | } \int _ { R ^ { n } } g ( t ) \sum _ { i \leq n } \sum _ { j \leq n } h ( X _ { i } - t ) { \big ( } b ( X _ { i } ) - u ( i , j ) { \big ) } d t { \big | } .
$$

That is

$$
\begin{array} { r l } & { E \biggl ( \biggl | \underset { s \leq u } { \sum } g + h ( X _ { i } ) \underset { j \leq u } { \sum } \left( b ( X _ { i } ) - u ( \hat { x } , j ) \right) \biggr | \biggr ) } \\ & { = E \biggl ( \biggl | \int _ { R ^ { n } } g ( \hat { x } ) \underset { i \leq n \leq i \leq n } { \sum } h ( X _ { i } - t ) \bigl ( \hat { \theta } ( X _ { i } ) - u ( \hat { x } , j ) \bigr ) d t \biggr | \biggr ) } \\ & { \leq \left\| g \right\| _ { L ^ { n } } . E \biggl ( \int _ { R ^ { n } } \biggl | \underset { s \leq u \leq n \leq n } { \sum } h ( X _ { i } - t ) \bigl ( \hat { \theta } ( X _ { i } ) - u ( \hat { x } , j ) \bigr ) \biggr | d t \biggr ) } \\ & { \leq \left\| g \right\| _ { L ^ { n } } \biggl ( \int _ { R ^ { n } ( \{ 0 , 1 \} ) ^ { 2 \leq n } } \int _ { \mathbb { R } ^ { n } } \biggl | \underset { s \leq u \leq n } { \sum } \int _ { \mathbb { R } } \Bigl ( X _ { i } - t ) \bigl ( \hat { \theta } ( X _ { i } ) - u ( \hat { x } , j ) \bigr ) \Bigr | ^ { 2 } \rho d t d \sigma \biggr ) ^ { \frac { 1 } { 2 } } \times \biggl ( \int _ { R ( \{ 0 , 1 \} ) ^ { 2 } } \int _ { \mathbb { R } ^ { n } } 1 _ { z \sim i \times i \times j } } \\ & { = \bigl ( s u p ( h ) \bigr ) ^ { \frac { 1 } { 2 } } \left\| g \right\| _ { L ^ { n } } \biggl ( \int _ { R ^ { n } } E \bigl ( \underset { s \leq u \leq n \leq n } { \sum } h ( X _ { i } - t ) \bigl ( \hat { \theta } ( X _ { i } ) - u ( \hat { x } , j ) \bigr ) \bigr ) ^ { \frac { 1 } { 2 } } \rho d t d \sigma \biggr ) ^ { \frac { 1 } { 2 } } . } \end{array}
$$

Further set $h ( x ) = c _ { 0 } 1 _ { A } ( x )$ , there is by formula (8)

$$
\big | \sum _ { i \leq n } \sum _ { j \leq n } h ( X _ { i } - t ) \big ( b ( X _ { i } ) - u ( i , j ) \big ) \big | ^ { 2 } \big ) d t = \int _ { R ^ { n } } \int _ { B ( 0 ; 1 ) ^ { 2 n } } \big | \sum _ { i \leq n } \sum _ { j \leq n } c _ { 0 } 1 _ { A } \big ( X _ { i } - t \big ) \big ( b ( X _ { i } ) - u ( i , j ) \big ) \big | ^ { 2 } \rho d \sigma d t \leq
$$

hence one has the below estimation of $g$ convolution with characteristic function

$$
E { \bigg ( } { \Big | } \sum _ { i \leq n } g * ( c _ { 0 } 1 _ { A } ) ( X _ { i } ) \sum _ { j \leq n } \left( b ( X _ { i } ) - u ( i , j ) \right) { \Big | } { \bigg ) } \leq | A | ^ { \frac { 1 } { 2 } } c _ { 0 } ( 2 | A | n ) ^ { \frac { 1 } { 2 } } \| g \| _ { L ^ { \infty } } = { \sqrt { 2 } } c _ { 0 } | A | n ^ { \frac { 1 } { 2 } } \| g \| _ { L ^ { \infty } }
$$

Finally We decompose $f$ into a sum of some well-defined convolutions to estimate these parts. Since a Lipschitz function $f$ ,in $B ( 0 ; 1 ) \subset R ^ { d }$ with $f ( 0 ) = 0$ ,may extend to a whole Lipschitz function on $R ^ { d }$ with $\| f \| _ { L ^ { \infty } } \leq 1$ . So we may consider function $f \in \mathcal { L }$ and decompose $\begin{array} { r } { f = \sum _ { l = 1 } ^ { q + 1 } f _ { l } } \end{array}$ ，where

$$
h _ { l } = \left\{ \begin{array} { l l } { | B ( 0 ; 1 ) | ^ { - 1 } ( 2 ^ { l } r ) ^ { - d } } & { x \in B ( 0 , 2 ^ { l } r ) } \\ { 0 } & { o t h e r w i s e } \end{array} \right. ,
$$

$f _ { 1 } = f - f { * } h _ { 1 }$ ， $\begin{array} { r } { \mathstrut _ { 2 } ^ { \ * } = f * h _ { 1 } - f * h _ { 2 } * h _ { 1 } , \cdot \cdot \cdot f _ { q } = f * h _ { l - 1 } * \cdot \cdot * h _ { 1 } - f * h _ { l } * h _ { l - 1 } * \cdot \cdot * h _ { 1 } , f _ { q + 1 } = f * h _ { q } \cdot \cdot \cdot * h _ { 1 } , } \end{array}$ （204号and q denoted by $\begin{array} { r } { 2 ^ { q + 1 } \frac { \eta ^ { d } } { n } = 2 ^ { q + 1 } r \geq 1 > 2 ^ { q } r = 2 ^ { q } \frac { \eta ^ { d } } { n } } \end{array}$ .So

$$
{ \ L } _ { 2 } = E { \biggl ( } \operatorname* { s u p } _ { f \in { \mathcal { L } } } { \Bigl | } \sum _ { i \leq n } \sum _ { l = 1 } ^ { q + 1 } f _ { l } ( X _ { i } ) \sum _ { j \leq n } { \bigl ( } b ( X _ { i } ) - u ( i , j ) { \bigr ) } { \bigr | } { \biggr ) } \leq \sum _ { l = 1 } ^ { q + 1 } E { \biggl ( } \operatorname* { s u p } _ { f \in { \mathcal { L } } } { \Bigl | } \sum _ { i \leq n } f _ { l } ( X _ { i } ) \sum _ { j \leq n } { \bigl ( } b ( X _ { i } ) - u ( i , j ) { \bigr ) } { \bigr | } { \biggr ) }
$$

For first part,one has

$$
E \bigg ( \Big | \sum _ { i \leq n } f _ { 1 } ( X _ { i } ) \sum _ { j \leq n } \big ( b ( X _ { i } ) - u ( i , j ) \big ) \big | \bigg ) \leq \sum _ { i \leq n } \| f - f * h _ { 1 } \| _ { L ^ { \infty } } E \bigg ( \Big | \sum _ { j \leq n } \big ( b ( X _ { i } ) - u ( i , j ) \big ) \big | \bigg ) \leq n .
$$

where we omit the computing process of $\begin{array} { r } { E \bigg ( \big | \sum _ { j \leq n } \big ( b ( X _ { i } ) - u ( i , j ) \big ) \big | ^ { 2 } \bigg ) \leq 1 } \end{array}$ ,further $\begin{array} { r } { E \bigg ( \vert \sum _ { j \leq n } \left( b ( X _ { i } ) - \right. } \end{array}$ $u ( i , j ) ) \ d j \Big | \Big ) \leq 1 .$ （20

For the expectation about $f _ { l } = \left( f - f * h _ { l } \right) * h _ { 1 } * \cdot \cdot \cdot * h _ { l - 1 }$ with $2 \leq l \leq q$ , one has from formula (9)

$$
E { \bigg ( } { \Big | } \sum _ { i \leq n } f _ { l } ( X _ { i } ) \sum _ { j \leq n } { \big ( } b ( X _ { i } ) - u ( i , j ) { \big ) } { \Big | } { \bigg ) } \leq { \sqrt { 2 } } { \big | } B ( 0 ; 1 ) { \big | } ^ { - 1 } ( 2 ^ { l - 1 } r ) ^ { - d } { \big | } s u p p ( h _ { l - 1 } ) { \big | } n ^ { \frac { 1 } { 2 } } { \big \| } ( f - f \ast h _ { i } ) \ast h _ { 1 } \ast \cdot \cdot \cdot h _ { l - 2 }
$$

For the last part expectation about $f _ { q + 1 } = f * h _ { 1 } * \cdot \cdot \cdot h _ { q - 1 } * h _ { q }$ , one has by (9) again

$$
E { \biggl ( } { \Bigl ( } | \sum _ { i \leq n } f _ { q + 1 } ( X _ { i } ) \sum _ { j \leq n } { \bigl ( } b ( X _ { i } ) - u ( i , j ) { \bigr ) } { \Bigr | } { \biggr ) } \leq { \sqrt { 2 } } | B ( 0 ; 1 ) | ^ { - 1 } ( 2 ^ { q } r ) ^ { - d } | s u p p ( h _ { q } ) | n ^ { \frac { 1 } { 2 } } \| f * h _ { 1 } * \cdot \cdot \cdot h _ { q - 1 } \| _ { L ^ { \infty } } \to \infty ,
$$

Summing all part estimations, one has

$$
E \operatorname* { s u p } _ { f \in { \mathcal { L } } _ { 1 } } I _ { 2 2 } \leq n 2 r + ( { \sqrt { 2 } } n ^ { \frac { 1 } { 2 } } 2 ^ { 2 } r + \cdot \cdot \cdot + { \sqrt { 2 } } n ^ { \frac { 1 } { 2 } } 2 ^ { q + 1 } r ) \leq 2 n ^ { 1 - \frac { 1 } { d } } + 4 { \sqrt { 2 } } n ^ { \frac { 1 } { 2 } }
$$

# References

[1] Hoorn P. van der ，Lippner G.， Trugenberger C., Krioukov D. Ollivier-Ricci curvature convergence in random geometric graphs. Physical Review Research 3, O13211 (2021).   
[2] Kuhn H. W. The Hungarian method for the assignment problem. Naval Res. Logistics Quarterly, Volume2, Issuel-2, March 1955,Pages 83-97.   
[3] Papadimitriou C.H., Steiglitz K. Combinatorial Optimization, Algorithms and Complexity. PrenticeHall, Englewood Cliffs, N.J. (1982).   
[4] Penrose M. Random geometric graphs. Oxford university press, 2003.   
[5] Talagrand M. Matching random samples in many dimensions. The Annals of Applied Probability 1992,Vol. 2, No. 4,846-856.   
[6] Veronika Kralj-Iglic, Ales Iglic， A Simple Statistical Mechanical Approach to the free Energy of the Electric Double Layer Including the Excluded Volume Effect. Journal de Physique I, Volume 6, Issue 4,April 1996,pp.477-491.   
[7] Villani C., Topics in optimal transportation. Graduate Studies in Mathematics, 58.American Mathematical Society, Providence,RI, 2003.