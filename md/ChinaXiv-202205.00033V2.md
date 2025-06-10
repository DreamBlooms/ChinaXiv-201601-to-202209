# On the number of edges in some graphs \*

Chunhui Lai $^ { \mathrm { a , 1 } }$

（20 $\mathbf { a }$ School of Mathematics and Statistics, Minnan Normal University， Zhangzhou, Fujian, P.R. China.

# Abstract

In 1975,P. Erd's proposed the problem of determining the maximum number $f ( n )$ of edges in a graph with $n$ vertices in which any two cycles are of different lengths. The sequence $( c _ { 1 } , c _ { 2 } , \cdots , c _ { n } )$ is the cycle length distribution of a graph $G$ （204号 with $n$ vertices, where $c _ { i }$ is the number of cycles of length $i$ in $G$ .Let $f ( a _ { 1 } , a _ { 2 } , \cdots ,$ （204 （204 $\boldsymbol { a } _ { n }$ ) denote the maximum possble number of edges in a graph which satisfies $c _ { i } \leq a _ { i }$ ， where $a _ { i }$ is a nonnegative integer. In 1991, Shi posed the problem of determining $f ( a _ { 1 } , a _ { 2 } , \cdots , a _ { n } )$ which extended the problem due to Erdós.It is clear that $f ( n ) =$ （204号 $f ( 1 , 1 , \cdots , 1 )$ .Let $g ( n , m ) = f ( a _ { 1 } , a _ { 2 } , \cdot \cdot \cdot , a _ { n } )$ ，where $a _ { i } = 1$ if $i / m$ is an integer, and $a _ { i } = 0$ otherwise. It is clear that $f ( n ) = g ( n , 1 )$ . We prove that $\begin{array} { r } { \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } \frac { f ( n ) - n } { \sqrt { n } } \geq } \end{array}$ $\sqrt { 2 + { \frac { 4 0 } { 9 9 } } }$ , which is better than the previous bounds $\sqrt { 2 }$ (Shi, 1988), and $\textstyle { \sqrt { 2 + { \frac { 7 6 5 4 } { 1 9 0 7 1 } } } }$ (Lai, 2017). We show that $\begin{array} { r } { \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } { \frac { g ( n , m ) - n } { \sqrt { \frac { n } { m } } } } > \sqrt { 2 . 4 4 4 } } \end{array}$ g(n,m)-n > √2.444, for all even integers m. We make the following conjecture: $\begin{array} { r } { \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } { \frac { f ( n ) - n } { \sqrt { n } } } > \sqrt { 2 . 4 4 4 } } \end{array}$

Key words: Graph,cycle, number of edges.   
AMS 2000 MSC: 05C38, 05C35.

# 1 Introduction

Let $f ( n )$ be the maximum number of edges in a graph with $n$ vertices in which no two cycles have the same length. In 1975, Erdos raised the problem of determining $f ( n )$ (see Bondy and Murty [1],p.247,Problem 11). Shi [11] proved a lower bound.

Theorem 1 (Shi [11])

$$
f ( n ) \geq n + [ ( { \sqrt { 8 n - 2 3 } } + 1 ) / 2 ]
$$

for $n \geq 3$ ：

Chen,Lehel, Jacobson and Shreve [3], Jia [4], Lai [5-7], Shi [13,14] obtained some additional related results.

Boros, Caro, Fiüredi and Yuster [2] proved an upper bound as follows.

Theorem 2 (Boros,Caro, Fiüredi and Yuster [2]) For $n$ sufficiently large,

$$
f ( n ) < n + 1 . 9 8 { \sqrt { n } } .
$$

Lai [8] improved the lower bound by Shi as follows.

Theorem 3(Lai [8])Let $t = 1 2 6 0 r + 1 6 9$ ( $r \geq 1$ )，then

$$
f ( n ) \geq n + \frac { 1 0 7 } { 3 } t + \frac { 7 } { 3 }
$$

for $\begin{array} { r } { n \geq \frac { 2 1 1 9 } { 4 } t ^ { 2 } + 8 7 9 7 8 t + \frac { 1 5 9 5 7 } { 4 } } \end{array}$

Lai [5] proposed the following conjecture:

Conjecture 4 (Lai [5])

$$
\operatorname* { l i m } _ { n \to \infty } { \frac { f ( n ) - n } { \sqrt { n } } } \leq { \sqrt { 3 } } .
$$

It would be nice to prove that

$$
\operatorname* { l i m } _ { n \to \infty } { \frac { f ( n ) - n } { \sqrt { n } } } \leq { \sqrt { 3 + { \frac { 3 } { 5 } } } } .
$$

Survey papers on this problem can be found in Tian [15], Zhang [16], Lai and Liu [9].

The progress of all 5O problems in [1] can be found in Locke [10]

The sequence $( c _ { 1 } , c _ { 2 } , \cdots , c _ { n } )$ is the cycle length distribution of a graph $G$ with （204 $n$ vertices, where $c _ { i }$ is the number of cycles of length $i$ in $G$ .Let $f ( a _ { 1 } , a _ { 2 } , \cdots ,$ （204 $a _ { n }$ ） denote the maximum possible number of edges in a graph which satisfies （204 $c _ { i } ~ \leq ~ a _ { i }$ ，where $a _ { i }$ is a nonnegative integer. Shi [12] posed the problem of determining $f ( a _ { 1 } , a _ { 2 } , \cdots , a _ { n } )$ which extended the problem due to Erdós. It is clear that $f ( n ) = f ( 1 , 1 , \cdot \cdot \cdot , 1 )$ . Let $g ( n , m ) = f ( a _ { 1 } , a _ { 2 } , \cdot \cdot \cdot , a _ { n } )$ ，where $a _ { i } = 1$ （204号 if $i / m$ is an integer, and $a _ { i } = 0$ otherwise. It is clear that $f ( n ) = g ( n , 1 )$ ：

In this paper, we obtain the following results.

Theorem 5 Let $m$ be even, $s _ { 1 } > s _ { 2 } , s _ { 1 } + 3 s _ { 2 } > k$ ，then

$$
g ( n , m ) \geq n + ( k + s _ { 1 } + 2 s _ { 2 } + 1 ) t - 1
$$

$$
\begin{array} { r l } & { \textup { r } n \geq ( \frac 3 4 m k ^ { 2 } + \frac 1 2 m k s _ { 1 } + \frac 3 2 m k s _ { 2 } + \frac 1 2 m s _ { 1 } ^ { 2 } + \frac 3 2 m s _ { 1 } s _ { 2 } + \frac 9 4 m s _ { 2 } ^ { 2 } + m k + m s _ { 1 } + } \\ & { n s _ { 2 } + \frac 1 2 m ) t ^ { 2 } + ( \frac 1 4 m k + \frac 1 2 m s _ { 1 } + \frac 3 4 m s _ { 2 } - k - s _ { 1 } - 2 s _ { 2 } + \frac 1 2 m - 1 ) t + 1 . } \end{array}
$$

Theorem 6 Let $t = 1 2 6 0 r + 1 6 9$ （ $r \geq 1$ )，then

$$
f ( n ) \geq n + \frac { 1 1 9 } { 3 } t - \frac { 2 6 3 9 9 } { 3 }
$$

for $\begin{array} { r } { n \geq \frac { 1 3 0 9 } { 2 } t ^ { 2 } - \frac { 1 3 4 9 1 5 9 } { 6 } t + \frac { 6 9 3 2 2 1 5 } { 3 } } \end{array}$

# 2 Proof of Theorem 5

Proof. Let $\begin{array} { r } { n _ { t } = { \left( \frac { 3 } { 4 } m k ^ { 2 } + \frac { 1 } { 2 } m k s _ { 1 } + \frac { 3 } { 2 } m k s _ { 2 } + \frac { 1 } { 2 } m s _ { 1 } ^ { 2 } + \frac { 3 } { 2 } m s _ { 1 } s _ { 2 } + \frac { 9 } { 4 } m s _ { 2 } ^ { 2 } + m k + \right. } } \end{array}$ （ $\begin{array} { r } { m s _ { 1 } + 3 m s _ { 2 } + \frac { 1 } { 2 } m ) t ^ { 2 } + ( \frac { 1 } { 4 } m k + \frac { 1 } { 2 } m s _ { 1 } + \frac { 3 } { 4 } m s _ { 2 } - k - s _ { 1 } - 2 s _ { 2 } + \frac { 1 } { 2 } m - 1 ) t + 1 , } \end{array}$ （204号 $m$ be even, $s _ { 1 } > s _ { 2 } , s _ { 1 } + 3 s _ { 2 } > k$ ， $n \geq n _ { t }$ . It suffice to show that there exists a graph $G$ on $n$ vertices with $n + ( k + s _ { 1 } + 2 s _ { 2 } + 1 ) t - 1$ edges such that all cycles in $G$ have distinct lengths and all the lengths of cycles are the multiple of $m$ ：

Now we construct the graph $G$ which consists of a number of subgraphs: $B _ { i }$ L $0 \leq i \leq s _ { 1 } t , i = s _ { 1 } t + j$ ( $1 \leq j \leq s _ { 2 } t$ ）， $i = s _ { 1 } t + s _ { 2 } t + j$ ( $1 \le j \le t$ 0）

Now we define these $B _ { i } s$ . These subgraphs all only have a common vertex $x$ ， otherwise their vertex sets are pairwise disjoint.

For $1 \leq i \leq s _ { 2 } t$ , let the subgraph $B _ { s _ { 1 } t + i }$ consists of a cycle

$$
x a _ { i } ^ { 1 } a _ { i } ^ { 2 } . . . a _ { i } ^ { m s _ { 1 } t + 2 m s _ { 2 } t + m i - 1 } x
$$

and a path:

$$
x a _ { i , 1 } ^ { 1 } a _ { i , 1 } ^ { 2 } . . . a _ { i , 1 } ^ { \frac { m s _ { 1 } t - m s _ { 2 } t + m i } { 2 } - 1 } a _ { i } ^ { \frac { m s _ { 1 } t + m s _ { 2 } t + m i } { 2 } } .
$$

Based on the construction, $B _ { s _ { 1 } t + i }$ contains exactly three cycles of lengths:

$$
m s _ { 1 } t + m i , m s _ { 1 } t + m s _ { 2 } t + m i , m s _ { 1 } t + 2 m s _ { 2 } t + m i .
$$

For $1 \leq i \leq t$ , let the subgraph $\boldsymbol { B } _ { s _ { 1 } t + s _ { 2 } t + i }$ consists of a cycle

$$
C _ { s _ { 1 } t + s _ { 2 } t + i } = x y _ { i } ^ { 1 } y _ { i } ^ { 2 } . . . y _ { i } ^ { m s _ { 1 } t + 3 m s _ { 2 } t + m k ( k + 1 ) t + m i - 1 } x
$$

and $k$ paths sharing a common vertex $x$ ，the other end vertices are on the cycle Cs1t+s2t+i:

$$
x y _ { i , p } ^ { 1 } y _ { i , p } ^ { 2 } . . . y _ { i , p } ^ { \frac { m s _ { 1 } t + 3 m s _ { 2 } t - m k t + m ( p - 1 ) t + m i } { 2 } - 1 } y _ { i } ^ { \frac { m s _ { 1 } t + 3 m s _ { 2 } t + m k ( 2 p - 1 ) t + m ( p - 1 ) t + m i } { 2 } } ( p = 1 , 2 , . . . , k ) .
$$

As a cycle with $k$ chords contains $\binom { k + 2 } { 2 }$ distinct cycles, $\boldsymbol { B } _ { s _ { 1 } t + s _ { 2 } t + i }$ contains exactly $\frac { ( k + 2 ) ( k + 1 ) } { 2 }$ cycles of lengths:

$$
m s _ { 1 } t + 3 m s _ { 2 } t + m k h t + ( h + j - 1 ) m t + m i ( j \geq 1 , h \geq 0 , k + 1 \geq j + h ) .
$$

$B _ { 0 }$ is a path with an end vertex $x$ and length $n - n _ { t }$ . The other $B _ { i }$ is simply a cycle of length $m i$ ：

$$
g ( n , m ) \geq n + ( k + s _ { 1 } + 2 s _ { 2 } + 1 ) t - 1 , { \mathrm { f o r } } \ n \geq n _ { t } .
$$

This completes the proof.

From Theorem 5,we have

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \mathbf { \sigma } } { \frac { g ( n , m ) - n } { \sqrt { \frac { n } { m } } } } \geq
$$

$$
\sqrt { \frac { ( k + s _ { 1 } + 2 s _ { 2 } + 1 ) ^ { 2 } } { ( \frac { 3 } { 4 } k ^ { 2 } + \frac { 1 } { 2 } k s _ { 1 } + \frac { 3 } { 2 } k s _ { 2 } + \frac { 1 } { 2 } s _ { 1 } ^ { 2 } + \frac { 3 } { 2 } s _ { 1 } s _ { 2 } + \frac { 9 } { 4 } s _ { 2 } ^ { 2 } + k + s _ { 1 } + 3 s _ { 2 } + \frac { 1 } { 2 } ) } } ,
$$

for all even integers $m$

Let $s _ { 1 } = 2 8 4 9 9 0 6 6$ , S2 = 4749839,k = 14249542, then

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \mathbf { \pi } } { \frac { g ( n , m ) - n } { \sqrt { \frac { n } { m } } } } > { \sqrt { 2 . 4 4 4 } } ,
$$

for all even integers $m$

# 3 Proof of Theorem 6

Proof. Let 1309t²_1349159t + 6932215,t = 1260r + 169,r ≥1,n≥ nt.It suffice to show that there exists a graph G on n vertices with n + 119t - 26399 edges such that all cycles in $G$ have distinct lengths.

Now we construct the graph $G$ which consists of a number of subgraphs: $B _ { i }$ ， （ $0 \leq i \leq 2 2 t , i = 2 2 t + j$ ( $\begin{array} { r } { 1 \le j \le \frac { 5 t - 8 } { 3 } , } \end{array}$ )， $\begin{array} { r } { i = 2 3 t + \frac { 2 t - 2 } { 3 } + j } \end{array}$ 0 $\begin{array} { r } { 1 \le j \le \frac { 5 t - 8 } { 3 } , } \end{array}$ ）， $i = 3 2 t + j - 6 0$ ( $5 8 \leq j \leq t - 7 4 2 )$ ）

Now we define these $B _ { i } s$ . These subgraphs all only have a common vertex $x$ ， otherwise their vertex sets are pairwise disjoint.

For $\begin{array} { r } { 1 \leq i \leq \frac { 5 t - 8 } { 3 } } \end{array}$ , let the subgraph $B _ { 2 2 t + i }$ consists of a cycle

$$
x a _ { i } ^ { 1 } a _ { i } ^ { 2 } . . . a _ { i } ^ { 2 8 t + \frac { 2 t - 2 } { 3 } + 2 i - 3 } x
$$

and a path:

$$
x a _ { i , 1 } ^ { 1 } a _ { i , 1 } ^ { 2 } . . . a _ { i , 1 } ^ { \frac { 5 6 t - 2 } { 6 } } a _ { i } ^ { \frac { 7 6 t - 4 } { 6 } + i } .
$$

Based on the construction, $B _ { 2 2 t + i }$ contains exactly three cycles of lengths:

$$
2 2 t + i , 2 5 t + \frac { t - 1 } { 3 } + i - 1 , 2 8 t + \frac { 2 t - 2 } { 3 } + 2 i - 2 .
$$

For $\begin{array} { r } { 1 \leq i \leq \frac { 5 t - 8 } { 3 } } \end{array}$ , let the subgraph $B _ { 2 3 t + \frac { 2 t - 2 } { 3 } + i }$ consists of a cycle

$$
x b _ { i } ^ { 1 } b _ { i } ^ { 2 } . . . b _ { i } ^ { 2 8 t + \frac { 2 t - 2 } { 3 } + 2 i - 2 } x
$$

and a path:

$$
x b _ { i , 1 } ^ { 1 } b _ { i , 1 } ^ { 2 } . . . b _ { i , 1 } ^ { 1 1 t - 1 } b _ { i } ^ { \frac { 7 6 t - 4 } { 6 } + i } .
$$

Based on the construction, $B _ { 2 3 t + \frac { 2 t - 2 } { 3 } + i }$ contains exactly three cycles of lengths:

$$
2 3 t + \frac { 2 t - 2 } { 3 } + i , 2 7 t + i - 1 , 2 8 t + \frac { 2 t - 2 } { 3 } + 2 i - 1 .
$$

For $5 8 \leq i \leq t - 7 4 2$ , let the subgraph $B _ { 3 2 t + i - 6 0 }$ consists of a cycle

$$
C _ { 3 2 t + i - 6 0 } = x y _ { i } ^ { 1 } y _ { i } ^ { 2 } . . . y _ { i } ^ { 1 3 7 t + 1 1 i + 8 9 0 } x
$$

and ten paths sharing a common vertex $x$ ，the other end vertices are on the cycle $C _ { 3 2 t + i - 6 0 }$

$$
x y _ { i , 1 } ^ { 1 } y _ { i , 1 } ^ { 2 } . . . y _ { i , 1 } ^ { 1 1 t - 2 } y _ { i } ^ { 2 1 t - 5 9 + i }
$$

$$
x y _ { i , 1 0 } ^ { 1 } y _ { i , 1 0 } ^ { 2 } . . . y _ { i , 1 0 } ^ { 1 6 t - 2 } y _ { i } ^ { 1 1 1 t + 1 5 1 + 1 0 i } .
$$

As a cycle with $d$ chords contains $\binom { d + 2 } { 2 }$ distinct cycles, $B _ { 3 2 t + i - 6 0 }$ contains exactly 66 cycles of lengths:

32t +i - 60, 33t + i+ 4, 34t + i+ 207, 35t + i- 3,  
36t +i- 2, 37t +i-3, 38t +i-3, 39t+i-8,  
40t+ i, 41t+i, 42t+i+739, 43t + 2i - 54,  
43t + 2i +213, 45t + 2i + 206, 45t + 2i-3, 47t + 2i - 3,  
47t + 2i-4, 49t + 2i- 9, 49t + 2i-6, 51t + 2i+2,  
51t + 2i + 741, 53t + 3i + 155, 54t + 3i + 212, 55t + 3i + 206,  
56t + 3i - 4, 57t + 3i - 4, 58t + 3i - 10, 59t + 3i - 7,  
60t + 3i- 4, 61t + 3i + 743, 64t + 4i + 154, 64t + 4i + 212,  
66t + 4i + 205, 66t + 4i - 5, 68t + 4i-10, 68t + 4i- 8,  
70t + 4i- 5, 70t + 4i + 737, 74t + 5i + 154, 75t + 5i + 211,  
76t + 5i + 204, 77t + 5i - 11, 78t + 5i-8, 79t + 5i- 6,  
80t + 5i + 736, 85t + 6i + 153, 85t +6i + 210， 87t +6i +198,  
87t + 6i -9, 89t +6i -6, 89t +6i+735，95t +7i+152,  
96t + 7i + 204, 97t + 7i + 200, 98t + 7i -7, 99t + 7i + 735,  
106t+ 8i+146， $1 0 6 t + 8 i + 2 0 6$ ， $1 0 8 t + 8 i + 2 0 2$ ，108t + 8i + 734,  
$1 1 6 t + 9 i + 1 4 8$ $1 1 7 t + 9 i + 2 0 8$ ， $1 1 8 t + 9 i + 9 4 3$ ， $1 2 7 t + 1 0 i + 1 5 0$   
$1 2 7 t + 1 0 i + 9 4 9$ ， $1 3 7 t + 1 1 i + 8 9 1$

$B _ { 0 }$ is a path with an end vertex $x$ and length $n - n _ { t }$ . The other $B _ { i }$ is simply a cycle of length $i$

Then $\begin{array} { r } { f ( n ) \ge n + \frac { 1 1 9 } { 3 } t - \frac { 2 6 3 9 9 } { 3 } } \end{array}$ ,for $n \geq n _ { t }$ ，

This completes the proof.

From Theorem 6,we have

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \infty } { \frac { f ( n ) - n } { \sqrt { n } } } \geq \sqrt { 2 + { \frac { 4 0 } { 9 9 } } } ,
$$

which is beter than the previous bounds $\sqrt { 2 }$ (see [1)， and $\textstyle { \sqrt { 2 + { \frac { 7 6 5 4 } { 1 9 0 7 1 } } } }$ （204 see [8]).

Combining this with Boros, Caro, Firedi and Yuster's upper bound, namely Theorem 2, we get

$$
1 . 9 8 \geq \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { \infty } \frac { f ( n ) - n } { \sqrt { n } } \geq \operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \sqrt { n } } \frac { f ( n ) - n } { \sqrt { n } } \geq \sqrt { 2 + \frac { 4 0 } { 9 9 } } .
$$

FromtheproofofTheorem6,wehave

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { } \frac { g ( n , m ) - n } { \sqrt { \frac { n } { m } } } \geq \sqrt { 2 + \frac { 4 0 } { 9 9 } } ,
$$

for all integers $m$

If $m = 1$ ， $1 \leq i \leq t$ , there exists the subgraph similar to $\boldsymbol { B _ { s _ { 1 } t + s _ { 2 } t + i } }$ consists of a cycle $C _ { s _ { 1 } t + s _ { 2 } t + i }$ and $k$ paths sharing a common vertex $x$ ，the other end vertices are on the cycle $C _ { s _ { 1 } t + s _ { 2 } t + i }$ such that all cycles in $\boldsymbol { B } _ { s _ { 1 } t + s _ { 2 } t + i }$ have distinct lengths, then we could obtain

$$
\operatorname* { l i m i n f } _ { n \to \infty } { \frac { f ( n ) - n } { \sqrt { n } } } > { \sqrt { 2 . 4 4 4 } } > { \sqrt { 2 + { \frac { 4 0 } { 9 9 } } } } .
$$

But we only for $m = 1$ ， $5 8 \leq i \leq t - 7 4 2$ ， construct a subgraph similar to （20 $\boldsymbol { B _ { s _ { 1 } t + s _ { 2 } t + i } }$ consists of a cycle $C _ { s _ { 1 } t + s _ { 2 } t + i }$ and ten paths sharing a common vertex （204 $x$ ， the other end vertices are on the cycle $C _ { s _ { 1 } t + s _ { 2 } t + i }$ such that all cycles in （204号 $\boldsymbol { B _ { s _ { 1 } t + s _ { 2 } t + i } }$ have distinct lengths and obtain

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \infty } \frac { f ( n ) - n } { \sqrt { n } } \geq \sqrt { 2 + \frac { 4 0 } { 9 9 } } .
$$

Since the liminf for g(nm)-n for even $m$ is $\sqrt { 2 . 4 4 4 }$ , it is reasonable to suspect that such a lower bound also holds for f(n)-n.

We make the following conjecture:

Conjecture 7

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \infty } { \frac { f ( n ) - n } { \sqrt { n } } } > { \sqrt { 2 . 4 4 4 } } .
$$

# 4 Acknowledgment

The author would like to thank Professor Endre Boros, Yair Caro, Ronald J. Gould, Gyula O.H. Katona, Raphael Yuster for their advice. The author would

like to thank the referees for their many valuable comments and suggestions.

# References

[1] J.A. Bondy and U.S.R. Murty, Graph Theory with Applications (Macmillan, New York, 1976). MR3138588   
[2] E. Boros, Y. Caro, Z. Firedi and R. Yuster, Covering non-uniform hypergraphs, J. Combin. Theory Ser.B 82(2001), 270-284. MR1842115 (2002g:05130)   
[3] G. Chen，J. Lehel，M. S. Jacobson and W. E. Shreve，Note on graphs without repeated cycle lengths, J. Graph Theory. 29(1998),11-15. MR1633908 (2000d:05059)   
[4] X. Jia, Some extremal problems on cycle distributed graphs, Congr. Numer. 121(1996), 216-222. MR1431994 (97i:05068)   
[5] C.Lai, On the size of graphs with all cycle having distinct length, Discrete Math.122(1993) 363-364.MR1246693(94i:05048)   
[6] C. Lai, A lower bound for the number of edges in a graph containing no two cycles of the same length， Electron. J. Combin. 8(2001)，Note 9,1 - 6. MR1877662 (2002k:05124)   
[7] C. Lai, Graphs without repeated cycle lengths, Australas. J. Combin. 27(2003), 101-105.MR1955391 (2003m:05102)   
[8] C. Lai, On the size of graphs without repeated cycle lengths, Discrete Appl. Math. 232 (2017), 226-229.MR3711962   
[9] C. Lai, M. Liu, Some open problems on cycles, J. Combin. Math. Combin. Comput.91(2014), 51-64.MR3287706   
[10] S. C. Locke, Unsolved problems: http://math.fau.edu/locke/Unsolved.htm   
[11] Y. Shi, On maximum cycle-distributed graphs, Discrete Math. 71(1988), 57-71. MR0954686 (89i:05169)   
[12] Y. Shi, Some problems of cycle length distribution, J. Nanjing Univ. (Natural Sciences)， Special Issue On Graph Theory, 27(1991), 233-234.   
[13] Y. Shi, The number of edges in a maximum cycle distributed graph, Discrete Math.104(1992),205-209.MR1172850 (93d:05083)   
[14] Y. Shi, On simple MCD graphs containing a subgraph homemorphic to $K _ { 4 }$ ， Discrete Math. 126(1994), 325-338. MR1264498 (95f:05072)   
[15] F. Tian, The progress on some problems in graph theory, Qufu Shifan Daxue Xuebao Ziran Kexue Ban. 1986, no. 2, 30-36. MR0865617   
[16] K. Zhang, Progress of some problems in graph theory, J. Math. Res. Exposition 27(3) (2007)， 563-576. MR2349503