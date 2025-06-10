# General Decomposition Theory of Spin Connections, Topological Structure of Gauss-Bonnet-Chern Density and The Morse Theory \*

Xi-Guo Lee Institute of Modern Physical,Academia Sinica, Lanzhou,Gansu,73oooo,P.R.China

December1,2017

# Abstract

In order to commemorate Professor Duan Yi-Shi, I hereby publish in Helv. Phys. Acta,(68(1995)513.article on the Internet By means of methods of the geometric algebra the general decomposition of the spin connections on the sphere bundle of a compact $n$ -dimensional Riemannian manifold has been studied in detail. Using this decompo sition theory it is shown that the Gauss-Bonnet-Chern density of the Euler- Poincaré characteristic can be expressed in terms of a smooth vector field $\vec { \phi }$ and taken the form of the $\delta$ function $\delta ( \vec { \phi } )$ .The topological structure of the Gauss-Bonnet-Chern density is detailed. Furthermore the Morse theory formula of the Euler-Poincar $\acute { e }$ characteristic has been obtained via the topological structure.

# 1.Introduction

The Gauss-Bonnet-Chern (GBC) theorem is one of the most signicant results in differential geometry .It relates the curvature of the compact and oriented even-dimensional

Riemannian manifold $M$ with an important topological invariant,the Euler-Poincaré characteristic $\chi ( M )$ . An elegant intrinsic proof of the theorem was discovered by Chern $^ { [ 1 , 2 ] }$ ,whose instructive idea was to work on the sphere bundle $S ( M )$ rather than on $M$ ,or exactly on the individual fibre of $S ( M )$ . A summary and some historical comments on the GBC theorem are given by Kabayashi,Nomizu $[ 3 ]$ , and Spivak $[ 4 ]$ respectively. Recently,a detailed review of Chern's proof of the GBC theorem is presented in Ref[5].

A great advance in this field was the discovery of a relationship between supersymmetry and the index theorem,which includes the derivation of the GBC theorem via supersymmmetry and path integral techniques as presented by Alvarez-Gaume et al. $[ 6 ]$ .In topological quantum field theory which was initiated by Wittenl7],the GBC theorem can be derived by means of a general Morse theoryl8]. On the physics side,the optical Berry phase is a direct result of the Gauss-Bonnet theorem $[ 9 ]$ and the black hole entropy emerges as the Euler class through dimensional continuation of the Gauss-Bonnet theorem[10].

Using the special decomposition of a spin connection for the group $S O ( n )$ in a previous work $[ 1 1 ]$ by one of the authors Duan of this paper ,the GBC density(the Euler-Poincaré characteristic $\chi ( M )$ density) can be taken as a $\delta$ function $\delta ( \vec { \phi } )$ of a smooth vector field $\vec { \phi }$ （1 which implies that only the zeros of a smooth vector field $\vec { \phi }$ on the manifold $M$ contribute to $\chi ( M )$ . This fact is the classical Hopf theorem[12,13].But we must point out here that the decomposition of the spin connection in the previous paperl11] was sopposed only for a special gauge condition .

In this paper we will try to establish a general decomposition theory of the spin connections for an $S O ( n )$ gauge theory in terms of the unit vector field $\vec { n }$ by means of the methods of the geometric algbra and give a general decomposition formula of the spin connections with a global property .A Chern- Simons $( n - 1 )$ -form on the whole bundle （204号 $S ( M )$ can be rigorously obtained without using a gauge condition .One shows that the GBC density takes a form of the $\delta$ function $\delta ( \vec { \phi } )$ of the smooth vector field $\vec { \phi }$ and the topological structure of the GBC density can be labeled by the Brouwer degrees and the Hopf indices. Furthermore we show that a expression for $\chi ( M )$ in the Morse theory can be represented by the Hopf indices and the Hessian matrices via the topological structure of the Gauss-Bonnet-Chern density.

This paper is arranged as follows . In sec.2 we will study a general decomposition theory of spin connections in an $S O ( n )$ gauge theory on a sphere bundle $S ( M )$ .In sec.3 we will derive the Chern-Simons $( n - 1 )$ form from the Chern formula on the sphere bundle $S ( M )$ using the general decomposition expression of the spin connections and express it completely in terms of a unit vector field $\vec { n }$ .In sec.4 we investigate the topological structure of the GBC density.In sec.5 we derive the expression for $\chi ( M )$ in the Morse theory by the topological sturcture of the GBC density given in sec.4.

# 2. The sphere bundle and the general decomposition theory of the spin connections

In this section we will begin with the introduction of some definitions and the basic notions to discuss the general decomposition problems. The intrinsic proof of the GaussBonnet-Chern theorem of the Euler-Poincaré characteristic $\chi ( M )$ of the Riemannian manifold $M$ given by Chern $^ { \lfloor 1 , 2 \rfloor }$ makes use of a unit vector field on $M$ with only a finite number of isolated singular points via introducing a sphere bundlel14,15] $S ( M )$ over $M$ ： We recall also that the topological invariant $\chi ( M )$ is identified to the sum of the indices of a smooth vector field on $M$ at its zeros,which was given by a famous Hopf theorem.To give a unified version of the above two viewpoints,let $M$ be the compact and oriented （204号 $n$ -dimensional Riemannian manifold and $\vec { \phi }$ be a smooth vector feld (a section of vector bundle) on $M$ , as in Refs.[16,17,18,19],we define a unit vector field $\vec { n }$ on $M$ as

$$
n ^ { a } = \phi ^ { a } / \phi , \qquad \phi \equiv \mid \mid \vec { \phi } \mid , \qquad \phi ^ { 2 } = \phi ^ { a } \phi ^ { a } , \qquad a = 1 , 2 , . . . , n .
$$

in which the superscript“ $u$ ”is the local orthonormal frame index.

From(1） we see that the zeros of $\vec { \phi }$ are just the singularities of $\vec { n }$ This expression naturally give a constraint condition

$$
n ^ { a } n ^ { a } = 1
$$

we get

$$
n ^ { a } d n ^ { a } = 0 .
$$

In fact, $\vec { n }$ is just a section of the sphere bundle $S ( M ) ^ { [ 5 ] }$ .For the $S O ( n )$ gauge theory,i.e.,the principal bundle $P ( \pi , M , G )$ with a structure group $G \ : = \ : S O ( n )$ ,let $x ^ { \mu }$ be the local coordinates on the base manifold $M$ ，the covariant derivative 1-form $D _ { \omega } n ^ { a }$ of the unit vector field $n ^ { a }$ is defined by

$$
D _ { \omega } n ^ { a } = d n ^ { a } - \omega ^ { a b } n ^ { b }
$$

and the curvature 2-form,

$$
F ^ { a b } ( \omega ) = d \omega ^ { a b } - \omega ^ { a c } \wedge \omega ^ { c b } ,
$$

where $\omega ^ { a b }$ is a spin connetion 1-form (the $S O ( n )$ gauge potential)

$$
\omega ^ { a b } = \omega _ { \mu } ^ { a b } d x ^ { \mu } , \qquad \omega ^ { a b } = - \omega ^ { b a } .
$$

From $( 3 ) , ( 4 ) \mathrm { a n d } ( 6 )$ we see that

$$
n ^ { a } D _ { \omega } n ^ { a } = 0 .
$$

Let the $n$ anti-commuting Dirac matrices $\gamma _ { a } ( a = 1 , . . . , n )$ ina $n$ -dimensional vector space of the vector ffeld $\vec { \phi }$ be a set of the bases of the Clifford algebral20],which satisfy the anti-commutation relation

$$
\gamma _ { a } \gamma _ { b } + \gamma _ { b } \gamma _ { a } = 2 \delta _ { a b } I .
$$

In the geometric algebra theory [21,22] the unit vector field $\vec { n }$ on $M$ can be expressed in the following matrix form

$$
n = n ^ { a } \gamma _ { a } ,
$$

1-vector ,then the spin connection 1-form and the curvature 2-form are respectively

$$
\omega = \frac { 1 } { 2 } \omega ^ { a b } I _ { a b } , \qquad F ( \omega ) = \frac { 1 } { 2 } F ^ { a b } ( \omega ) I _ { a b }
$$

in which $I _ { a b }$ are the generators for the group $S O ( n )$ .i.e.,

$$
I _ { a b } = \frac { 1 } { 4 } [ \gamma _ { a } , \gamma _ { b } ] ,
$$

and

$$
\left[ I _ { a b } , \gamma _ { c } \right] = \gamma _ { a } \delta _ { b c } - \gamma _ { b } \delta _ { a c } .
$$

Using (8) and (11） it is easy to prove that the covariant derivative l-form (4) can be rewritted in terms of $n$ and $\omega$

$$
D _ { \omega } n = d n - [ \omega , n ]
$$

and the curvature 2-form

$$
F ( \omega ) = d \omega - \omega \wedge \omega .
$$

Let $f$ and $h$ are two 1-vectors in geometric algebra theory ,i.e., $f = f ^ { a } \gamma _ { a } , h = h ^ { a } \gamma _ { a }$ ， the scalar pruduct of $\bar { f }$ and $\vec { h }$ can be defined by

$$
\vec { f } \cdot \vec { h } = \frac { 1 } { 2 } ( f h + h f ) = f ^ { a } h ^ { a } .
$$

It can be shown that the geometric product of $f$ and $h$ is

$$
f h = f ^ { a } h ^ { a } + ( f ^ { a } h ^ { b } - h ^ { a } f ^ { b } ) I _ { a b } .
$$

Making use of (15) and from (2),(3),(7),(8) we have

$$
n n = n ^ { a } n ^ { a } = I ,
$$

$$
d n n + n d n = 0 ,
$$

$$
D _ { \omega } n n + n D _ { \omega } n = 0 ,
$$

and

$$
d n n = ( d n ^ { a } n ^ { b } - n ^ { a } d n ^ { b } ) I _ { a b } ,
$$

$$
n D _ { \omega } n = ( n ^ { a } D _ { \omega } n ^ { b } - n ^ { b } D _ { \omega } n ^ { a } ) I _ { a b } .
$$

Let $T _ { r }$ bea $r$ -vector in the geometric algebra

$$
T _ { r } = { \frac { 1 } { r ! } } T ^ { a _ { 1 } \ldots , a _ { r } } \gamma _ { a _ { 1 } } \ldots , \gamma _ { a _ { r } }
$$

we can prove that the covariant derivative 1-form of $T _ { r }$ is

$$
D _ { \omega } T _ { r } = d T _ { r } - [ \omega , T _ { r } ] .
$$

Now we return to the main discussion on the decomposition theory of the spin connections .In the gauge theory it is well-known that when connection 1-form $\omega$ takes the gauge transformation

$$
\omega ^ { \prime } = S \omega S ^ { - 1 } + d S S ^ { - 1 } ,
$$

the curvature 2-form $F$ should be transformed as

$$
{ \cal F } ^ { \prime } = S { \cal F } S ^ { - 1 } .
$$

These are fundamental requirements to the gauge field theory. In our view-point[17],the spin connection 1-form $\omega ^ { a b }$ can be decomposed and may has a inner structure,which have been effectively used to study the magnetic monopole problems in the $S U ( 2 )$ gauge theory[17,18,19],the topological gaugetheoryofthdislocationand thedislinations ncondensed matter physics[23l,and the geometrization of the Planck constant in terms of the space-time defect in General Relativity $[ 2 4 ]$ The main feature of the decomposition theory of the connections (the gauge potential)l17] is that the connection $\omega$ can be generally decomposed by

$$
\omega = A + b ,
$$

where $A$ and $b$ are respectively required to satisfy the gauge transformations and vector covariant transformations,i.e.,

$$
A ^ { \prime } = S A S ^ { - 1 } + d S S ^ { - 1 } ,
$$

$$
b ^ { \prime } = S b S ^ { - 1 } .
$$

From(25)and (26) one shows that

$$
\omega ^ { \prime } = A ^ { \prime } + b ^ { \prime } = S ( A + b ) S ^ { - 1 } + d S S ^ { - 1 }
$$

This means that the decomposition of the connection $\omega = A + b$ with (25）and (26) rigorously satisfy the gauge transformations.

Using(16)，by (12）we see that

$$
D _ { \omega } n n = d n n - \omega + n \omega n .
$$

From above we find that

$$
\omega = \frac { 1 } { 2 } ( d n n + n D _ { \omega } n ) + \frac { 1 } { 2 } J _ { n } ( \omega ) ,
$$

where we define an useful symbol

$$
J _ { n } ( \omega ) = n \omega n + \omega .
$$

The expression (28) with (29) is the general decomposition formula of the spin connections for the $S O ( n )$ gauge theory. We call the term $\begin{array} { r } { \frac { 1 } { 2 } ( d n n + n D _ { \omega } n ) } \end{array}$ in（28） the fundamental term of the general decomposition of the connection $\omega$ respect to $n$ and $\frac { 1 } { 2 } J _ { n } ( \omega )$ ，the compensative term of the general decomposition of the connection $\omega$ respect to $n$ ，which makes the whole general decomposition expression of the connection $\omega$ to satisfy the gauge transformation rule.

Let a family $\{ W , V , U , \ldots \}$ be an open cover of $M$ and $S _ { V U }$ be the transition matrix functions which satisfy the following condition[25]

$$
S _ { U U } = I , \qquad S _ { V U } ^ { - 1 } = S _ { U V } , \qquad S _ { W V } S _ { V U } S _ { U W } = I \qquad W \cap V \cap U \neq 0 .
$$

For any two open neighborhoods $V$ and $U$ ,if $V \cap U \neq 0$ ,then

$$
n _ { v } = S _ { V U } n _ { u } S _ { V U } ^ { - 1 } ,
$$

where $n _ { v }$ and $n _ { u }$ are two smooth vector felds on $V$ and $U$ respectively and the spin connections $\omega _ { v }$ and $\omega _ { u }$ satifya relation

$$
\omega _ { v } = S _ { V U } \omega _ { u } S _ { V U } ^ { - 1 } + d S _ { V U } S _ { V U } ^ { - 1 } ,
$$

which is the foundamental condition of the existence of the connection on the principal bundle $P ( \pi , M , G )$ .In terminology of physics $S _ { V U }$ is just the gauge transformation (22） in the gauge field theory.In the following,for abbreviation we always denote that $\quad S _ { V U } = S .$ From (28),(29) and making use of (30) and (31) it can be proved that[26]

$$
\frac { 1 } { 2 } ( d n _ { v } n _ { v } + n _ { v } D _ { \omega _ { v } } n _ { v } ) + \frac { 1 } { 2 } J _ { n _ { v } } ( \omega _ { v } )
$$

$$
= S [ \frac { 1 } { 2 } ( d n _ { u } n _ { u } + n _ { u } D _ { \omega _ { u } } n _ { u } ) + \frac { 1 } { 2 } J _ { n _ { u } } ( \omega _ { u } ) ] S ^ { - 1 } + d S S ^ { - 1 } .
$$

And using(31) and (32) we see that

$$
\begin{array} { c } { { \displaystyle { \omega _ { v } - [ \frac { 1 } { 2 } ( d n _ { v } n _ { v } + n _ { v } D _ { \omega _ { v } } n _ { v } ) + \frac { 1 } { 2 } J _ { n _ { v } } ( \omega _ { v } ) ] } } } \\ { { \displaystyle { } } } \\ { { \displaystyle { = S [ \omega _ { u } - \frac { 1 } { 2 } ( d n _ { u } n _ { u } + n _ { u } D _ { \omega _ { u } } n _ { u } ) - \frac { 1 } { 2 } J _ { n _ { u } } ( \omega _ { u } ) ] S ^ { - 1 } . } } } \end{array}
$$

The above expression shows that if the decomposition formula on the open neighborhood （204号 $U$

$$
\omega _ { u } = \frac { 1 } { 2 } ( d n _ { u } n _ { u } + n _ { u } D _ { \omega _ { u } } n _ { u } ) + \frac { 1 } { 2 } J _ { n _ { u } } ( \omega _ { u } )
$$

holds true,then the decomposition formula on the open neighborhood $V$

$$
\omega _ { v } = \frac { 1 } { 2 } ( d n _ { v } n _ { v } + n _ { v } D _ { \omega _ { v } } n _ { v } ) + \frac { 1 } { 2 } J _ { n _ { v } } ( \omega _ { v } )
$$

must holds true also. This means that the general decomposition formula (28） has a global property and is independent of the choice of the local coordinates.

Now let us show that the decomposition formula (28) is independent of the choice of the unit vector field $\vec { n }$ .To do this let $k$ in geometric algebra be a unit vector field which is different from the unit vector field $n$ .Then quantity $n k$ by a terminology of the geometric algebra is a 2-vector and using(21) its the covariant derivative 1-form is

$$
D _ { \omega } ( n k ) = d ( n k ) - [ \omega , n k ] .
$$

This expression gives a relation as

$$
D _ { \omega } n k + n D _ { \omega } k = d n k + n d k - \omega n k + n k \omega .
$$

Multiplying both sides of the above formula by $n$ from left side and by $k$ from right side and using

$$
k k = k ^ { a } k ^ { a } I = I ,
$$

it is not difficult to get

$$
n D _ { \omega } n + D _ { \omega } k k = n d n + d k k - n \omega n + k \omega k .
$$

Making use of (17) and (18) and

$$
k d k + d k k = 0 , \qquad k D _ { \omega } k + D _ { \omega } k k = 0 ,
$$

from the expression (35) we find that

$$
\frac { 1 } { 2 } ( d n n + n D _ { \omega } n ) + \frac { 1 } { 2 } J _ { n } ( \omega ) = \frac { 1 } { 2 } ( d k k + k D _ { \omega } k ) + \frac { 1 } { 2 } J _ { k } ( \omega ) { . }
$$

This means that the general decomposition formula (28) is indeed independent of the unit vector feld $n$ we chose.

To give a more concrete decomposition formula of the connections on the sphere bundle $S ( M )$ we suppose in (24) that

$$
[ A , n ] \neq 0 ,
$$

$$
[ b , n ] = 0 .
$$

Let $a$ be an arbitrary element of the Lie algebra $s o ( n )$ . It is expressed by

$$
a = \frac { 1 } { 2 } a ^ { a b } I _ { a b } \quad \quad \quad a ^ { \prime } = S a S ^ { - 1 } .
$$

In the geometric algebra theory $a$ is an antisymmetric tensor.Using the unit vector feld $n$ we can always construct an argument $b$ as

$$
b = { \frac { 1 } { 2 } } ( n a n + a ) ,
$$

which obviously satisfies the commutation relation (39). Substituting (41) and (24) into (29)we have

$$
J _ { n } ( \omega ) = n ( A + a ) n + A + a .
$$

As we have mentioned above that $a$ is arbitrary,the argument $( A + a )$ in the（42） should be also arbitrary and by (25) and (40) we see that it satisfies the gauge transformations. This means that

$$
B = A + a
$$

is an arbitrary connection for $S O ( n )$ gauge theory with

$$
B ^ { \prime } = S B S ^ { - 1 } + d S S ^ { - 1 } .
$$

Making use of (43) and (41),(42) can be rewritten in following formulation

$$
J _ { n } ( \omega ) = J _ { n } ( B ) = n B n + B .
$$

Or

$$
J _ { n } ( B ) = n [ B , n ] + 2 B .
$$

So the general decompoaition formula (28） becomes

$$
\omega = \frac { 1 } { 2 } ( d n n + n D _ { \omega } n ) + \frac { 1 } { 2 } J _ { n } ( B ) .
$$

We can always choose $a$ as $a = B _ { 0 } - A$ ，where $B _ { 0 }$ is a flat connection

$$
B _ { 0 } = d U U ^ { - 1 }
$$

in which $U$ is a local matrix in spinor representation corresponding for the group $S O ( n )$ From (48),(45) and (47) we finally get

$$
\omega = \frac { 1 } { 2 } ( d n n + n D _ { \omega } n ) + \frac { 1 } { 2 } J _ { n } ( B _ { 0 } ) ,
$$

where

$$
J _ { n } ( B _ { 0 } ) = n B _ { 0 } n + B _ { 0 } .
$$

Substituting (49) into (13), for the flat connections $B _ { 0 }$ ，then $F ( B _ { 0 } ) = 0$ ，using (50) we derive the decomposition expression of the curvature 2-form as

$$
\begin{array} { c } { { F ( \omega ) = \displaystyle \frac { 1 } { 4 } [ - D _ { 0 } n \wedge D _ { 0 } n + D _ { \omega } n \wedge D _ { \omega } n + n d D _ { \omega } n - d D _ { \omega } n n } } \\ { { { } } } \\ { { + D _ { \omega } n \wedge ( B _ { 0 } n + n B _ { 0 } ) - ( B _ { 0 } n + n B _ { 0 } ) \wedge D _ { \omega } n ] , } } \end{array}
$$

where

$$
D _ { 0 } n = d n - [ B _ { 0 } , n ] .
$$

By(52),(51) can be rewritten in the covariant formlation

$$
F ( \omega ) = \frac { 1 } { 4 } [ - D _ { 0 } n \wedge D _ { 0 } n + D _ { \omega } n \wedge D _ { \omega } n + n D _ { 0 } D _ { \omega } n - D _ { 0 } D _ { \omega } n n ] .
$$

Using (9),(10),(15) and taking notice of $J _ { n } ( B _ { 0 } ) \ = \ { \textstyle { \frac { 1 } { 2 } } } J ^ { a b } ( B _ { 0 } ) I _ { a b }$ (through out this paper),from (46),(49) and (53) the component decomposition formula of $\omega , F ( \omega )$ and $J _ { n } ( \omega )$ are repectively given by

$$
\omega ^ { a b } = d n ^ { a } n ^ { b } - d n ^ { b } n ^ { a } + n ^ { a } D _ { \omega } n ^ { b } - n ^ { b } D _ { \omega } n ^ { a } + \frac { 1 } { 2 } J _ { n } ^ { a b } ( B _ { 0 } ) ,
$$

$$
F ^ { a b } ( \omega ) = - D _ { 0 } n ^ { a } \wedge D _ { 0 } n ^ { b } + D _ { \omega } n ^ { a } \wedge D _ { \omega } n ^ { b } + n ^ { a } D _ { 0 } D _ { \omega } n ^ { b } - n ^ { b } D _ { 0 } D _ { \omega } n ^ { a }
$$

and

$$
J _ { n } ^ { a b } ( B _ { 0 } ) = 2 ( B _ { 0 } ^ { b c } n ^ { c } n ^ { a } - B _ { 0 } ^ { a c } n ^ { c } n ^ { b } + B _ { 0 } ^ { a b } )
$$

where

$$
D _ { 0 } n ^ { a } = d n ^ { a } - B _ { 0 } ^ { a b } n ^ { b }
$$

It is easy to see that the special cases of (54) and (55） when $B _ { 0 } = 0 ( \mathrm { i . e . }$ ， ${ \cal J } _ { n } ^ { a b } ( B _ { 0 } ) =$ O) is just the result adopted in the Ref[11] .One notes that the special decomposition expressions in terms of the unit vector field $\vec { n }$ for the spin connection 1-form $\omega ^ { a b }$ and the curvature 2-form $F ^ { a b } ( \omega )$ in Ref[11] do not satisfy the gauge transformations (22) and (23) respectively and it may be regarded as a special gauge condition.

# 3.Chern- Simons form on the sphere bunble $S ( M )$

In this section we will discuss the Chern-Simons $( n - 1 )$ form by means of the decomposition expression (41).For a even dimensional compact and oriented Riemannian manifold （204号 $M$ ,there exists a unique $n$ -from $\Lambda$ over $M$ such that

$$
\Lambda = \frac { ( - 1 ) ^ { n / 2 } } { 2 ^ { n } \pi ^ { n / 2 } ( n / 2 ) ! } \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n - 1 } a _ { n } } F ^ { a _ { 1 } a _ { 2 } } ( \omega ) \wedge . . . \wedge F ^ { a _ { n - 1 } a _ { n } } ( \omega ) ,
$$

which is the closed $n$ -form.Let $\pi$ be a nature projection,thus $\pi ^ { - 1 } ( \mathrm { p } )$ is all that part of S(M) lying above the point $p \in M$ ,this fiber is isometric to the $( n - 1 )$ -dimensional

sphere $S ^ { n - 1 }$ .The transformation group in fiber can be taken the group $S O ( n )$ .The $n$ -form $\Lambda$ over $M$ , when pulled back to the sphere bundle $S ( M ) ^ { \left\lfloor 1 3 , 5 \right\rfloor }$ ,is exact

$$
\pi ^ { * } \Lambda = d \Omega
$$

Chern $^ { [ 1 , 5 ] }$ has proved that the $( n - 1 )$ form $\Omega$ on the sphere bundle $S ( M )$ is

$$
\Omega = \frac { 1 } { ( 2 \pi ) ^ { n / 2 } } \sum _ { k = 0 } ^ { n / 2 - 1 } ( - 1 ) ^ { k } \frac { 2 ^ { - k } } { ( n - 2 k - 1 ) ! ! k ! } \Theta _ { k } , n \ge 4
$$

which is called Chern formula,and $\Theta _ { k }$ is

$$
\Theta _ { k } = \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n - 2 k } a _ { n - 2 k + 1 } a _ { n - 2 k + 2 } . . . a _ { n - 1 } a _ { n } } n ^ { a _ { 1 } } D _ { \omega } n ^ { a _ { 2 } } \wedge . . . \wedge D _ { \omega } n ^ { a _ { n - 2 k } } \wedge . . .
$$

$$
\wedge F ^ { a _ { n - 2 k + 1 } a _ { n - 2 k + 2 } } ( \omega ) \wedge \ldots \wedge F ^ { a _ { n - 1 } a _ { n } } ( \omega ) ,
$$

where $F ^ { a b }$ is the curcature 2-form. Using the Bianchi identity

$$
{ \cal D } F ^ { a b } ( \omega ) = 0 .
$$

It can be proved that

$$
D \Lambda = 0 .
$$

This means that $\Lambda$ is independent of the connections and determines a cohomology class belonging to the cohomology gruop $H ^ { n } ( M )$ of the manifold $M$ .This is equivalent to saying that the integral $\int _ { M }$ takes over a closed manifold $M$ is a topological invariant which be called the Euler-Poincar $\acute { e }$ characteristic $\chi ( M )$ .Since $\pi ^ { * }$ maps the cohomology class of $M$ into that of $S ( M )$ ,while $\vec { n } ^ { * }$ performs the inverse operation. Thus $\vec { n } ^ { * } \pi ^ { * }$ amounts the identity ,the famous GBC theorem can be expressed as

$$
\chi ( M ) = \int _ { M } \Lambda = \int _ { M } { \vec { n } } ^ { * } \pi ^ { * } \Lambda = \int _ { M } { \vec { n } } ^ { * } d \Omega .
$$

Substituting(55) into (61) and taking notice of that the last two terms in (55) contribute nothing to $\Theta _ { k }$ due to thecompletely antisymmetric propertyof the tensor $\epsilon _ { a 1 \ldots , a _ { n } }$ （204 in the expression (61） we find the expanding expression for $\Theta _ { k }$ as

$$
\Theta _ { k } = \sum _ { l = 0 } ^ { k } ( - 1 ) ^ { k } C _ { k } ^ { l } ( - 1 ) ^ { l }
$$

$$
\epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n - 2 k } a _ { n - 2 k + 1 } a _ { n - 2 k + 2 } . . . , a _ { n - 2 k + 2 l - 1 } a _ { n - 2 k + 2 l } a _ { n - 2 k + 2 l } a _ { n - 2 k + 2 l + 1 } a _ { n - 2 k + 2 l + 2 \cdots , a _ { n - 1 } a _ { n } } }
$$

$$
\wedge D _ { 0 } n ^ { a _ { n - 1 } } \wedge D _ { 0 } n ^ { a _ { n } } ,
$$

where

$$
C _ { n } ^ { k } = { \frac { n ! } { k ! ( n - k ) ! } } .
$$

Since $D _ { \omega } \vec { n }$ and $D _ { 0 } \vec { n }$ also are two vectors both perpendicular to $\vec { n }$ ，let $D _ { \omega } \vec { n } - D _ { 0 } \vec { n }$ be （204号 $\vec { k }$ ,we have

$$
D _ { \omega } n ^ { a } - D _ { 0 } n ^ { a } = \alpha k ^ { a } ,
$$

where $\alpha$ is the magnitude of the vector $D _ { \omega } \vec { n } - D _ { 0 } \vec { n }$ . Since $n ^ { a } D _ { \omega } n ^ { a } = n ^ { a } D _ { 0 } n ^ { a } = 0$ ,from (66) we find that $\vec { k }$ is perpendicular to $\vec { n }$ ,i.e.,

$$
n ^ { a } k ^ { a } = 0 ,
$$

and it follows that

$$
k ^ { a } d n ^ { a } + n ^ { a } d k ^ { a } = 0 ,
$$

$$
n ^ { a } D _ { \omega } k ^ { a } + k ^ { a } D _ { \omega } n ^ { a } = 0 , \qquad n ^ { a } D _ { 0 } k ^ { a } + k ^ { a } D _ { 0 } n ^ { a } = 0 .
$$

From(66)and (34) one obtains

$$
\alpha = ( D _ { \omega } n ^ { a } - D _ { 0 } n ^ { a } ) k ^ { a } .
$$

Substituting this into (66) we have

$$
D _ { \omega } n ^ { a } = D _ { 0 } n ^ { a } + k ^ { a } k ^ { b } ( D _ { \omega } n ^ { b } - D _ { 0 } n ^ { b } ) .
$$

Using(68） the above expression becomes

$$
D _ { \omega } n ^ { a } = D _ { 0 } n ^ { a } - k ^ { a } n ^ { b } ( D _ { \omega } k ^ { b } - D _ { 0 } k ^ { b } ) .
$$

Putting(70) into (65),we get that $\Theta _ { k }$ as

$$
\Theta _ { k } = \sum _ { l = 0 } ^ { k } ( - 1 ) ^ { k } ( - 1 ) ^ { l } C _ { k } ^ { l } \epsilon _ { a _ { 1 } a _ { 2 } a _ { 3 } . . . , a _ { n } } ( n ^ { a _ { 1 } } D _ { 0 } n ^ { a _ { 2 } } \wedge D _ { 0 } ^ { a _ { 3 } } . . . , \wedge D _ { 0 } n ^ { a _ { n } }
$$

$$
- ( n + 2 l - 2 k - 1 ) n ^ { a _ { 1 } } k ^ { a _ { 2 } } n ^ { b _ { 2 } } ( D _ { \omega } k ^ { b _ { 2 } } - D _ { 0 } k ^ { b _ { 2 } } ) \wedge D _ { 0 } n ^ { a _ { 3 } } \wedge . . . , \wedge D _ { 0 } n ^ { a _ { n } } ) ,
$$

By formula

$$
( - 1 ) ^ { m } C _ { n - 1 } ^ { m } = \sum _ { j = 0 } ^ { m } C _ { n } ^ { j } \qquad m \neq 0
$$

and

$$
\sum _ { j = 0 } ^ { m } ( - 1 ) ^ { m + 1 } j C _ { k } ^ { m } = - \sum _ { j = 0 } ^ { m } ( - 1 ) ^ { m } j C _ { k } ^ { m } = 0 , \qquad k \not = 1
$$

it is not difficult to show that

$$
\sum _ { l = 0 } ^ { k } ( - 1 ) ^ { k } ( - 1 ) ^ { l } C _ { k } ^ { l } = ( - 1 ) ^ { k } [ \sum _ { l = 0 } ^ { k - 1 } ( - 1 ) ^ { l } C _ { k } ^ { l } + ( - 1 ) ^ { k } ] = 0 , \quad k \neq 0
$$

and

$$
- \sum _ { l = 0 } ^ { k } ( - 1 ) ^ { k } ( - 1 ) ^ { l } ( n + 2 l - 2 k - 1 ) C _ { k } ^ { l } = \left\{ \begin{array} { c } { { - 2 , \mathrm { i f } k = 1 , } } \\ { { 0 , \mathrm { i f } k > 1 . } } \end{array} \right.
$$

Substituting these into（71） we obtain

$$
\Theta _ { k } = \left\{ \begin{array} { c l } { \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } ( n ^ { a _ { 1 } } D _ { 0 } n ^ { a _ { 2 } } \wedge . . . , \wedge D _ { 0 } n ^ { a _ { n } } } & { } \\ { - ( n - 1 ) n ^ { a _ { 1 } } k ^ { a _ { 2 } } n ^ { b _ { 2 } } ( D _ { \omega } k ^ { b _ { 2 } } - D _ { 0 } k ^ { b _ { 2 } } ) \wedge . . . , \wedge D _ { 0 } n ^ { a _ { n } } ) , } & { \mathrm { i f } , k = 0 , } \\ { - 2 \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } n ^ { a _ { 1 } } k ^ { a _ { 2 } } n ^ { b _ { 2 } } ( D _ { \omega } k ^ { b _ { 2 } } - D _ { 0 } k ^ { b _ { 2 } } ) \wedge . . . , \wedge D _ { 0 } n ^ { a _ { n } } , } & { \mathrm { i f } , k = 1 , } \\ { 0 , } & { \mathrm { i f } , k > 1 . } \end{array} \right.
$$

By means of the expression (72), from (6O) we find a compact form of $\Omega$ as

$$
\Omega = { \frac { 1 } { ( n - 1 ) ! A ( S ^ { n - 1 } ) } } \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } n ^ { a _ { 1 } } D _ { 0 } n ^ { a _ { 2 } } \wedge . . . , \wedge D _ { 0 } n ^ { a _ { n } } ,
$$

where $A ( S ^ { n - 1 } )$ is the area of $S ^ { n - 1 }$ as

$$
A ( S ^ { n - 1 } ) = \frac { 2 \pi ^ { n / 2 } } { \Gamma ( n / 2 ) } .
$$

Using the geometric algebra methods , for a flat connection $B _ { 0 } = d U U ^ { - 1 }$ ，we take a simple matrix $U$ as

$$
U = n l , \qquad U ^ { - 1 } = l n ,
$$

is a local spinor matrix representation for the group $S O ( n )$ (see[27]),in which $n$ is the unit vector field defined as before and $l$ ，another unit vector field which is perpendicular to $n$ ，

$$
l n + n l = 0 .
$$

It is not difficult to verify that the matrix $U$ given by（74） transforms $l$ into $- l$ and $n$ into $- n$ （20

$$
U l U ^ { - 1 } = - l , \qquad U n U ^ { - 1 } = - n .
$$

The more detial discussion of the construction of the spinor matrix representation is given in Appendix.Substituting (74) into (45) and using (75) we find that the flat connection is of the form

$$
B _ { 0 } = d n n + n d l l n .
$$

By（77) and(52) we have

$$
D _ { 0 } n = - d n + [ d l l , n ] .
$$

Making use of (15) dll can be expressed explicitly by

$$
d l l = ( d l ^ { a } l ^ { b } - l ^ { a } d l ^ { b } ) I _ { a b } .
$$

From(78) and the above formula.using (8),(11), $d n ^ { a } l ^ { a } + n ^ { a } d l ^ { a } = 0$ ，one obtains

$$
D _ { 0 } n ^ { a } = - d n ^ { a } + 2 l ^ { a } l ^ { b } d n ^ { b } .
$$

Putting(79) into (73),we can express $\Omega$ as

$$
\begin{array} { l } { \Omega = \displaystyle \frac { 1 } { ( n - 1 ) ! A ( S ^ { n - 1 } ) } \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } ( - n ^ { a _ { 1 } } d n ^ { a _ { 2 } } \wedge . . . , \wedge n ^ { a _ { n } } } \\ { + 2 ( n - 1 ) n ^ { a _ { 1 } } d n ^ { a _ { 2 } } \wedge . . . , \wedge d n ^ { a _ { n - 1 } } \wedge l ^ { a _ { n } } l ^ { b } d n ^ { b } ) . } \end{array}
$$

Using the the formula given in the Appendix of Ref [10]),

$$
\epsilon _ { A _ { 1 } a _ { 2 } . . . , a _ { n } } n ^ { a _ { 1 } } d n ^ { a _ { 2 } } \wedge . . . , \wedge d n ^ { a _ { n - 1 } } \wedge d n ^ { b } =
$$

$$
\frac { 1 } { n - 1 } ( \delta _ { a _ { n } } ^ { b } - n ^ { b } n ^ { a _ { n } } ) \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } n ^ { a _ { 1 } } d n ^ { a _ { 2 } } \wedge . . . , \wedge d n ^ { a _ { n } } ,
$$

we find that $\Omega$ on $M$ can be reduced to

$$
\Omega = { \frac { 1 } { ( n - 1 ) ! A ( S ^ { n - 1 } ) } } \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } n ^ { a _ { 1 } } d n ^ { a _ { 2 } } \wedge . . . , \wedge d n ^ { a _ { n } } .
$$

The above expression (80) is the Chern-Simons $( n - 1 )$ -form which be expressed cleanly in terms of the unit vector field $n ^ { a }$ on whole sphere bundle $S ( M )$ .This is a generalization of the result only on a fibre of $S ( M )$ in Ref [5].

# 4. The topological structure of the GBC density and the GBC theorem

In present section,from the Chern-Simons $( n - 1 )$ -form in the expression (80),we will show that the singularities of a $n$ -form $d \Omega$ can be directly expressed by $\delta ( \Phi )$ .To do this ,from(1） we have

$$
d n ^ { a } = \frac { d \phi ^ { a } } { \phi } + \phi ^ { a } d ( \frac { 1 } { \phi } ) .
$$

Substituting it into（80）， $\Omega$ becomes

$$
\Omega = { \frac { 1 } { ( n - 1 ) ! A ( S ^ { n - 1 } ) } } \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } { \frac { \phi ^ { a _ { 1 } } } { \phi ^ { n } } } d \phi ^ { a _ { 2 } } \wedge . . . , \wedge d \phi ^ { a _ { n } } .
$$

Using

$$
\frac { \phi ^ { a } } { \phi ^ { n } } = - \frac { 1 } { n - 2 } \frac { \partial } { \partial \phi ^ { a } } ( \frac { 1 } { \phi ^ { n - 2 } } )
$$

the pull-back of the exterior derivative of (81） to $M$ can be written as

$$
\vec { \phi } ^ { * } d \Omega = - \frac { 1 } { A ( S ^ { n - 1 } ) ( n - 1 ) ! ( n - 2 ) } \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } \frac { \partial } { \partial \phi ^ { a } } \frac { \partial } { \partial \phi ^ { a _ { 1 } } } ( \frac { 1 } { \phi ^ { n - 2 } } ) \times
$$

where $g = d e t ( g _ { \mu \nu } ) , g _ { \mu \nu }$ is the metric tensor on $M$ Using a Jacobian $D ( \phi / x )$ which is defined by

$$
\epsilon ^ { a a _ { 2 } . . . , a _ { n } } D ( \phi / x ) = \epsilon ^ { \mu _ { 1 } \mu _ { 2 } . . . , \mu _ { n } } \partial _ { \mu _ { 1 } } \phi ^ { a } \partial _ { \mu _ { 2 } } \phi ^ { a _ { 2 } } . . . , \partial _ { \mu _ { n } } \phi ^ { a _ { n } }
$$

and the formula

$$
\epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } \epsilon ^ { a a _ { 2 } . . . , a _ { n } } = ( n - 1 ) ! \delta _ { a _ { 1 } } ^ { a } ,
$$

(82) can be rewritten as

$$
\vec { n } ^ { * } d \Omega = - \frac { 1 } { A ( S ^ { n - 1 } ) ( n - 2 ) } \frac { \partial ^ { 2 } } { \partial \phi ^ { a } \partial \phi ^ { a } } ( \frac { 1 } { \phi ^ { n - 2 } } ) D ( \phi / x ) d ^ { n } x .
$$

By means of the general Green's-functin formula in the vector space for the $\phi$

$$
\Delta _ { \phi } ( \frac { 1 } { \phi ^ { n - 2 } } ) = - \frac { 4 \pi ^ { n / 2 } } { \Gamma ( n / 2 - 1 ) } \delta ( \vec { \phi } ) \qquad n \geq 3 ,
$$

where

$$
\Delta _ { \phi } = \frac { \partial ^ { 2 } } { \partial \phi ^ { a } \partial \phi ^ { a } }
$$

is the $n$ -dimensional Laplacian operator in the vector space .So $\vec { n } ^ { * } d \Omega$ can become

$$
\vec { n } ^ { * } d \Omega = \delta ( \vec { \phi } ) D ( \phi / x ) d ^ { n } x .
$$

Therefore we may define a Gauss-Bonnet-Chern density $\rho$ on $M$ as

$$
\rho = { \frac { 1 } { ( n - 1 ) ! A ( S ^ { n - 1 } ) } } \epsilon _ { a _ { 1 } a _ { 2 } . . . , a _ { n } } \epsilon ^ { \mu _ { 1 } \mu _ { 2 } . . . , \mu _ { n } } \partial _ { \mu _ { 1 } } n ^ { a _ { 1 } } \partial _ { \mu _ { 2 } } n ^ { a _ { 2 } } . . . , \partial _ { \mu _ { n } } n ^ { a _ { n } }
$$

$$
= \delta ( \vec { \phi } ) D ( \phi / x ) .
$$

We see that the $\rho \neq 0$ and the $\vec { n } ^ { * } d \Omega \neq 0$ only when the $\vec { \phi } = 0$ . The above two expressions (83)and (84) are of great importance,it follows in our case an evident result of the Hopf theorem.

Suppose that $\phi ^ { a } ( x ) ( a = 1 . . . , n )$ possess $N$ isolated zeros and let the ith zero be $\vec { x } = \vec { z } _ { i }$ ， according to the $\delta$ -function theory [28] $\mathcal { S } ( \vec { \phi } )$ can be expressed by

$$
\delta ( \vec { \phi } ) = \sum _ { i = 1 } ^ { N } \frac { \beta _ { i } \delta ( \vec { x } - \vec { z } ) } { | D ( \phi / x ) | _ { \vec { x } = \vec { z } _ { i } } } ,
$$

then one obtains

$$
\delta ( \phi ) D ( \phi / x ) = \sum _ { i = 1 } ^ { N } \beta _ { i } \eta _ { i } \delta ( \vec { x } - \vec { z } _ { i } ) ,
$$

where $\beta _ { i }$ is a positive integer (the Hopf index of the ith zero）and $\eta _ { i }$ ,the Brouwer degree[12],

$$
\eta _ { i } = s g n D ( \phi / x ) | _ { \vec { x } = \vec { z } _ { i } } = \pm 1 .
$$

The meaning of the Hopf index $\beta _ { i }$ is that while $\vec { x }$ covers the region neighboring of the zero $\vec { z } _ { i }$ once ,the vector field function $\vec { \phi }$ covers the corresponding region $\beta _ { i }$ times.From above these and using (86) the GBC density on $M$ has a following topoloical structure

$$
\rho = \delta ( \vec { \phi } ) D ( \phi / x ) = \sum _ { i = 1 } ^ { N } \beta _ { i } \eta _ { i } \delta ( \vec { x } - \vec { z } _ { i } ) ,
$$

which shows that the local structure of $\rho$ is labeled by the Brouwer degrees and the Hopf indices .The integration of $\rho$ on $M$ is just the Euler-Poincar $\acute { e }$ characteristic

$$
\chi ( M ) = \int _ { m } \rho d ^ { n } x = \int _ { M } \vec { n } ^ { * } d \Omega = \sum _ { i = 1 } ^ { N } \beta _ { i } \eta _ { i } .
$$

The result of (88) says that the sum of indices of the zeros of the vector field $\vec { \phi }$ or the singularities of the unit vector field $\vec { n }$ is the Euler-Poincar $\acute { e }$ characteristic $\chi ( M )$ ： Therefore the topological structure of the GBC density shows the expected Hopf theorem. On the other hand, we must point out an important and a simple fact that from (87) and (88) we have

$$
\chi ( M ) = \int _ { M } \delta ( \vec { \phi } ) D ( \phi / x ) d ^ { n } x = d e g \phi \int _ { V } \delta ( \vec { \phi } ) d ^ { n } \phi = d e g \phi ,
$$

and

$$
d e g \phi = \sum _ { i = 1 } ^ { N } \beta _ { i } \eta _ { i } ,
$$

where $V$ is the elementary volume in the vector space of $\vec { \phi }$ and $d e g \phi$ is the degree of the mapping $\phi$ . The mapping degree $d e g \phi$ is to represent the globle topological property of Euler-Poincaré characteristic.

# 5.From the Gauss-Bonnet-Chern theorem to the the Morse theory

In the following ,we wil study the Euler-Poincar $\acute { e }$ characteristic $\chi ( M )$ in the Morse theory making use of the topological structure given in the sec.4.To reach our goal ,the frist we briefly review the elements of the Morse theory[16,28].Then we utilize (64),(83)and (85) to give the formula for $\chi ( M )$ in the Morse theory.

Let $f$ be a Morse function on the manifold $M$ ,for a point $p \in M$ , if the function $f$ satisfies

$$
d f \mid _ { p } = \partial _ { \mu } f d x ^ { \mu } \mid _ { p } = 0 ,
$$

then the point $p$ is a critical point of the function $f$ .The Hessian at $p$ ， $H _ { p } f$ ,is a guadratic form on $T _ { p } M$ ,the tangent space to $M$ at $p$ . In local coordinates $\{ x ^ { \mu } \}$ centered at $p$ ,the

matrix of $H _ { p } f$ relative to the base $\partial _ { \mu }$ at $p$ is

$$
\{ H _ { p } f \} _ { \mu \nu } = \partial _ { \mu } \partial _ { \nu } f ,
$$

which is called the Hessian matrix.If at $p$ that

$$
d e t H _ { p } f \neq 0 ,
$$

then the point $p$ is called a non-degenerate critical point of the function $f$ .the index of $p$ is the number of negative eigenvalues of the Hessian matrix $d e t H _ { p } f$ and it will be deneoted by $\lambda _ { i } ( f )$

Now let us suppose that a smooth vector field $\vec { \phi }$ on $M$ is a gradient field $[ 2 8 ]$ of the Morse function $f$ on the manifold $M$ .i.e.,

$$
\phi ^ { a } = e ^ { a \mu } \partial _ { \mu } f ,
$$

where $e ^ { a \mu }$ are the well-known vierbeins ( $g ^ { \mu \nu } = e ^ { a \mu } e ^ { a \nu }$ ). The relations (94) means that the critical points of the Morse function $f$ are just the zero points of the vector field $\vec { \phi }$

Using (94) we get,by differentiation

$$
\partial _ { \mu } \phi ^ { a } \mid _ { p } = e ^ { a \nu } \partial _ { \mu } \partial _ { \nu } f \mid _ { p } .
$$

Making use of formula

$$
\epsilon _ { a _ { 1 } . . . , a _ { n } } e ^ { a _ { 1 } \mu _ { 1 } } . . . , e ^ { a _ { n } \mu _ { n } } = \epsilon ^ { \mu _ { 1 } . . . , \mu _ { n } } , \frac 1 { \sqrt { g } }
$$

from（95) one obtains

$$
D ( \phi / x ) \mid _ { p } = \frac { 1 } { \sqrt { g } } d e t H _ { p } f \mid _ { p } ,
$$

Using(85) and (97) ,form the expression (83) we find that

$$
\vec { n } ^ { * } d \Omega = \sum _ { i = 1 } ^ { N } \beta _ { i } \delta ( \vec { x } - \vec { p _ { i } } ) \frac { d e t H _ { p } f } { \mid d e t H _ { p } f \mid } \mid _ { p _ { i } } d ^ { n } x .
$$

Substituting (98) into the Gauss-Bonnet-Chern theorem (64) ,we get a formula as

$$
\chi ( M ) = \sum _ { i = 1 } ^ { N } \beta _ { i } \frac { d e t H _ { p _ { i } } f } { \mid d e t H _ { p _ { i } } f \mid } ,
$$

where $N$ is the number of critical points of the Morse function $f$ .This means that the Euler-Poincar $\acute { e }$ characteristic $\chi ( M )$ has relation to not only the Hessian matrx but also the Hopf index.

In the Morse theory it is well-known that the Morse function $f$ at the Neighborhood of any critical point $p _ { i }$ can takes following form as

$$
f = f ( p _ { i } ) - ( x ^ { 1 } ) ^ { 2 } - . . . , - ( x ^ { \lambda _ { i } } ) ^ { 2 } + . . . , + ( x ^ { n } ) ^ { 2 } ,
$$

where $\lambda _ { i } ( f ) = 0 , 1 . . . , n$ .Since vierbein $e ^ { a \mu }$ is a single-vector function on the manifold $M$ ,from(94) and (100) it is easy to show that $\phi ^ { a }$ also is single-valued .This means that the Hopf indices $\beta _ { i } = 1$ (i=1,2,..,N).Substituting (100) into (99),we obtain

$$
\chi ( M ) = \sum _ { i = 1 } ^ { N } ( - 1 ) ^ { \lambda _ { i } ( f ) } .
$$

This is a famous result in the Morse theory .

From above we have seen that the topological structure of the Gauss-Bonnet-Chern density induces namely the Euler-Poincar $\acute { e }$ characteristic $\chi ( M )$ in the Morse theory.

Therefore in this paper we see that the general decomposition theory of connections in the gauge feld theory is an important and powerful tool in studying the topological problems not only in the theoretical physics but also in the Differential Geometry.

# Appendix

Theorem[27] : Let $\vec { n }$ and $\bar { l }$ 'be two unit vector fields in a $n$ -dimensional vector space with （204号 $\vec { n } \cdot \vec { l } \neq - 1$ ,and $\vec { h }$ be a unit vector field in the $\vec { n } - \bar { l }$ 'plane which bisects the angle $\theta$ between $\vec { n }$ and $\bar { l }$ Let $n , l$ and $h$ be three 1-vectors in the geometric algebra,then there exist two elementary transformations which brings $l$ into $n$ via the similarity transformation ,i.e.,

$$
n = L _ { i } l L _ { i } ^ { - 1 } , \quad i = 1 , 2 ,
$$

where

$$
L _ { 1 } = h \quad L _ { 1 } ^ { - 1 } = L _ { 1 } ,
$$

$$
L _ { 2 } = h l = n h L _ { 2 } ^ { - 1 } = l h = h n ,
$$

where $h$ has been defined by

$$
h = \frac { n + l } { 2 ( c o s \theta / 2 ) } ,
$$

and $\theta$ is

$$
c o s \theta = n ^ { a } l ^ { a } \neq - 1
$$

$L _ { i } ( i = 1 , 2 )$ are regarded as the spinor matrix representations of the orthogonal transformations, $L _ { 1 }$ represents the axial involution about $h$ and $L _ { 2 }$ represents the plane rotation in the $\vec { n } - \bar { l }$ plane.

Now let us consider further that the unit vector field $\bar { l }$ 'is perpendicular to the unit vector field $\vec { n }$ ，then

$$
L _ { 2 } = \frac { 1 } { \sqrt { 2 } } ( 1 + n l ) , ~ L _ { 2 } ^ { - 1 } = \frac { 1 } { \sqrt { 2 } } ( 1 + l n ) .
$$

Using $L _ { 2 }$ we can construct a simple spinor matrix representation of the orthogonal transformation $U$ as

$$
\begin{array} { r } { U = L _ { 2 } L _ { 2 } = n l , \quad U ^ { - 1 } = l n . } \end{array}
$$

Then

$$
\begin{array} { r } { { U l U } ^ { - 1 } = - l , \quad { U n U } ^ { - 1 } = - n } \end{array}
$$

This shows that $U$ brings $l$ into $- l$ ， $n$ into $- n$ ,respectively

# References

[1] S.S.Chern Ann.Math. 45,(1944) 747;46,(1945) 674.   
[2] S.S.Chern,Differentiale Manifold ,lecture note (Univ. of Chicago,Chicago.2,1959). [3] S.Kobayashi and K.Nomizu,Foundation of Differential Geometry (Interscience,New York,1969), Vol.2   
[4] M.Spivak,Differential Geometry (Publish or Perish,Boston, 1975).   
[5] J.S.Dowker and J.P.Schofield, J.Math.Phys. 31,(1990) 808.   
[6] L.Alvarez-Gaumé, Commun.Math.Phys. 90,(1983)161.   
[7] E.Wetten, Commun.Math.Phys.117,(1988) 353;118,(1989) 411.   
[8] J.M.F.Labastida, Commun.Math.Phys.123,(1989) 15.   
[9] L.H.Ryder, Eur.J.Phys.12,(1991) 15.   
[10] M.Banados,Claudio Teitelboim and Jorge Zanelli.Phys.Rev.Lett. 72,(1994) 957.   
[11] Y.S.Duan and X.H.Meng, J.Math.Phys.34,(1993) 1149.   
[12] H.Hopf,Math.Ann.96,(1929) 209.   
[13] J.H.Milnor,TopologyfromtheDifferentialViewpoint(Univ.ofVirginia press,Charlottes,VA,1965).   
[14] S.S.Chern,Shiing-Shen Chern Selected Papers (springer-verlag Press,1989) Vol.2.   
[15] R.Bott and L.W.Tu,Differential Form in Algebratic Topology (springer-verlag Press 1982).   
[16] A.T.Fomenko,Differential Geometry and Topology (consultants Bureau Press,New York,1987).   
[17] Y.S.Duan,M.L.Ge,Sci.Sinica11,(1979) 1072;KexueTongbao26,(1976) 282;Y.S.Duan and S.C.Zhao, Commun.Theor.Phys.2,(1983) 1553.   
[18] Y.S.Duan,SlAC-PUB-3301/84.   
[19] Y.S.Duan and J.C.Liu,in proceedings_ of Johns Hopkins Workshop 11 ,Edited by Y.S.Duan ,G.Domokes and S.Kovesi-Domokes(World Scientific,singapere,1988).   
[20] S.Okubo, J.Math.Phys.32,(1991) 1657 .   
[21] D.Hestones and G.Sobczyk,Clifford Algebra to Geometric Calculus (Reidel,Dorelrecht 1984).   
[22] C.Doran,D.Hestenes, F.Sommen and N.V.Acker,J.Math.Phys. 34,(1993)3642; A.Lasenby ,C.Doran and S.Gull, J.Math.Phys.34,(1993) 3683.   
[23] Y.S.Duan and S.L.Zhang,Int.J.Eng.Sci. 28,(1990) 689;29,(1991) 153; 30,(1992) 153.   
[24] Y.S.Duan ,S.L.Zhang and S.X.Feng J.Math.Phys. 35,(1994) 9.   
[25] S.S.Chern,An.da Acad.Brasileira de Ciéncias 35,(1963) 17.   
[26] X.G.Lee Doctorial Dissertation (Lanzhou University, P.R.C. 1994).   
[27] S.X.Kim,J.Math.Phys. 21,(1980) 1299.   
[28] AlbertS .Schwarz ,Topology For Physicists,(Springer-Verlag Press 1994 ).   
[29] J.Milnor,Morse Theory (Princton Univ.Press.1963).