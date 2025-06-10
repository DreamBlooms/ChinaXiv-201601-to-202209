# On the size of graphs without repeated cycle lengths \*

Chunhui Lai $^ { \mathrm { a , 1 } }$

a School of Mathematics and Statistics, Minnan Normal University, Zhangzhou, Fujian, P.R. China.

# Abstract

In 1975,P. Erdos proposed the problem of determining the maximum number $f ( n )$ of edges in a graph with $n$ vertices in which any two cycles are of different lengths.In this paper,it is proved that

$$
f ( n ) \geq n + \frac { 1 0 7 } { 3 } t + \frac { 7 } { 3 }
$$

$t \ : = \ : 1 2 6 0 r \ : + \ : 1 6 9$ $( r \geq 1 )$ 1 $\begin{array} { r } { n \geq \frac { 2 1 1 9 } { 4 } t ^ { 2 } + 8 7 9 7 8 t + \frac { 1 5 9 5 7 } { 4 } } \end{array}$ 区 $\begin{array} { r } { \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } \frac { f ( n ) - n } { \sqrt { n } } \geq \sqrt { 2 + \frac { 7 6 5 4 } { 1 9 0 7 1 } } } \end{array}$ $\sqrt { 2 }$ Shi, Discrete Math. 71(1988), 57-71], $\sqrt { 2 . 4 }$ [C.Lai, Australas.J. Combin. 27(2003), 101-105]. The conjecture $\begin{array} { r } { \operatorname* { l i m } _ { n \to \infty } \frac { f ( n ) - n } { \sqrt { n } } = \sqrt { 2 . 4 } } \end{array}$ = √2.4 is not true.

Key words: Graph,cycle,number of edges.   
AMS 2000 MSC: 05C38,05C35.

# 1 Introduction

Let $f ( n )$ be the maximum number of edges in a graph on $n$ vertices in which no two cycles have the same length. In 1975， Erdos raised the problem of

determining $f ( n )$ (see Bondy and Murty [1]，p.247,Problem 11). Shi [15] proved a lower bound.

Theorem 1 (Shi [15])

$$
f ( n ) \geq n + [ ( \sqrt { 8 n - 2 3 } + 1 ) / 2 ]
$$

for $n \geq 3$ ：

Chen,Lehel, Jacobson,and Shreve [3],Jia [5],Lai [6-8],Shi [16,18-20] obtained some additional relatedresults.

Boros, Caro, Fiüredi and Yuster [2] proved an upper bound.

Theorem 2 (Boros, Caro,Firedi and Yuster [2]) For $n$ sufficiently large,

$$
f ( n ) < n + 1 . 9 8 { \sqrt { n } } .
$$

Lai [9] improved the lower bound.

Theorem 3 (Lai [9])

$$
f ( n ) \geq n + { \sqrt { 2 . 4 } } { \sqrt { n } } ( 1 - o ( 1 ) )
$$

Lai [6,9] proposed the following conjectures:

Conjecture 4 (Lai [9])

$$
\operatorname* { l i m } _ { n \to \infty } { \frac { f ( n ) - n } { \sqrt { n } } } = { \sqrt { 2 . 4 } } .
$$

Conjecture 5(Lai [6])

$$
\operatorname* { l i m } _ { n \to \infty } { \frac { f ( n ) - n } { \sqrt { n } } } \leq { \sqrt { 3 } } .
$$

Markstrom [13] raised the following problem:

Problem 6 (Markstróm [13]) Determine the maximum number of edges in a hamiltonian graph on $n$ vertices with no repeated cycle lengths.

Results for the maximum number of edges in a 2-connected graph on $n$ vertices in which no two cycles have the same length can be found in [2,3,15].

Survey articles on this problem can be found in Tian [21], Zhang [24], Lai and Liu [10].

The progress of all 5O problems in [1] can be find in Locke [12].

A related topic concerns the Entringer problem,which is to determine which simple graphs have exactly one cycle of each length $l$ ， $3 \leq l \leq v$ (see problem 10 in [1]). This problem was posed in 1973 by R. C. Entringer. For developments on this topic, see [4,11,13,14,17,22,23].

In this paper, we construct a graph $G$ having no two cycles with the same length which leads to the following result.

Theorem 7 Let $t = 1 2 6 0 r + 1 6 9$ （ $r \geq 1$ ),then

$$
f ( n ) \geq n + \frac { 1 0 7 } { 3 } t + \frac { 7 } { 3 }
$$

for $\begin{array} { r } { n \geq \frac { 2 1 1 9 } { 4 } t ^ { 2 } + 8 7 9 7 8 t + \frac { 1 5 9 5 7 } { 4 } } \end{array}$

Hence conjecture 4 is not true.

# 2 Proofof theorem 7

Proof Let $t = 1 2 6 0 r + 1 6 9 , r \geq 1$ ，hm $\begin{array} { r } { n _ { t } = \frac { 2 1 1 9 } { 4 } t ^ { 2 } + 8 7 9 7 8 t + \frac { 1 5 9 5 7 } { 4 } } \end{array}$ $n \geq n _ { t }$ W $G$ $n$ $\begin{array} { l } { n + \frac { 1 0 7 } { 3 } t + \frac { 7 } { 3 } } \end{array}$ such that all cycles in $G$ have distinct lengths.

Now we construct the graph $G$ which consists of a number of subgraphs: $B _ { i }$ 5 L $0 \leq i \leq 2 0 t , 2 7 t \leq i \leq 2 8 t + 6 4 , 2 9 t - 7 3 d$ $2 9 t - 7 3 4 \leq i \leq 2 9 t + 2 6 7 , 3 0 t - 5 3 1 \leq i \ 3$ VI （204号 $3 0 t + 5 7 . 3 1 t - 7 4 1 < i < 3 1 t + 5 8 . 3 2 t - 7 4 0 < i < 3 2 t + 5 7 . 3 3 t - 7 4 1 <$ 公 $\leq 3 3 t + 5 7 , 3 4 t - 7 4 1 \leq i \leq 3 4 t + 5 2 , 3 5 t$ $1 \leq i \leq 3 4 t + 5 2 , 3 5 t - 7 4 6 \leq i \leq 3 5 t + 6$ 0,36t-738≤ $\begin{array} { r } { i < 3 6 t + 6 0 . 3 7 t - 7 3 8 < i < 3 7 t + 7 9 9 . i = 2 0 t + { \mathit { i } } ( 1 < { \mathit { i } } < \frac { t - 7 } { a } ) . i = } \end{array}$ 三 $\begin{array} { r } { 2 0 t + \frac { t - 1 } { 6 } + j \big ( 1 \leq j \leq \frac { t - 7 } { 6 } \big ) , i = 2 1 t + 2 j + 1 \big ( 0 \leq j \leq t - 1 \big ) , i = 2 1 t + 2 j } \end{array}$ 2j(0≤j≤ $\begin{array} { r } { \frac { t - 1 } { 2 } ) , i = 2 3 t + 2 j + 1 ( 0 \leq j \leq \frac { t - 1 } { 2 } ) } \end{array}$ ,and $\begin{array} { r } { i = 2 0 t + \frac { t - 1 } { 6 } } \end{array}$ ， $\begin{array} { r } { i = 2 0 t + \frac { t - 1 } { 3 } + \frac { t - 1 } { 6 } - 1 } \end{array}$ ， （20 $\begin{array} { r } { i = 2 0 t + \frac { t - 1 } { 3 } + \frac { t - 1 } { 6 } } \end{array}$ ， $\begin{array} { r } { i = 2 0 t + \frac { 2 \bar { t } - 2 } { 3 } } \end{array}$ ， $i = 2 1 t - 2$ ， $i = 2 1 t - 1$ ， $i = 2 6 t$ ）

Now we define these $B _ { i } \mathrm { s }$ . These subgraphs all only have a common vertex $x$ ， otherwise their vertex sets are pairwise disjoint.

For $1 \leq i \leq \frac { t - 7 } { 6 }$ , let the subgraph $B _ { 2 0 t + i }$ consists of a cycle

$$
x a _ { i } ^ { 1 } a _ { i } ^ { 2 } . . . a _ { i } ^ { \frac { 6 2 t - 8 } { 3 } + 2 i } x
$$

and a path:

$$
x a _ { i , 1 } ^ { 1 } a _ { i , 1 } ^ { 2 } . . . a _ { i , 1 } ^ { \frac { 5 9 t - 5 } { 6 } } a _ { i } ^ { \frac { 6 1 t - 1 } { 6 } + i }
$$

Based the construction, $B _ { 2 0 t + i }$ contains exactly three cycles of lengths:

$$
2 0 t + i , 2 0 t + \frac { t - 1 } { 3 } + i - 1 , 2 0 t + \frac { 2 t - 2 } { 3 } + 2 i - 1 .
$$

For $\textstyle 1 \leq i \leq { \frac { t - 7 } { 6 } }$ , let the subgraph $B _ { 2 0 t + \frac { t - 1 } { 6 } + i }$ consists of a cycle

$$
x b _ { i } ^ { 1 } b _ { i } ^ { 2 } . . . b _ { i } ^ { \frac { 6 2 t - 5 } { 3 } + 2 i } x
$$

and a path:

$$
x b _ { i , 1 } ^ { 1 } b _ { i , 1 } ^ { 2 } . . . b _ { i , 1 } ^ { 1 0 t - 1 } b _ { i } ^ { \frac { 6 1 t - 1 } { 6 } + i }
$$

Based the construction, $B _ { 2 0 t + \frac { t - 1 } { 6 } + i }$ contains exactly three cycles of lengths:

$$
2 0 t + \frac { t - 1 } { 6 } + i , 2 0 t + \frac { t - 1 } { 3 } + \frac { t - 1 } { 6 } + i , 2 0 t + \frac { 2 t - 2 } { 3 } + 2 i .
$$

For $0 \leq i \leq t - 1$ , let the subgraph $B _ { 2 1 t + 2 i + 1 }$ consists of a cycle

$$
x u _ { i } ^ { 1 } u _ { i } ^ { 2 } . . . u _ { i } ^ { 2 5 t + 2 i - 1 } x
$$

and a path:

$$
x u _ { i , 1 } ^ { 1 } u _ { i , 1 } ^ { 2 } . . . u _ { i , 1 } ^ { ( 1 9 t + 2 i - 1 ) / 2 } u _ { i } ^ { ( 2 3 t + 2 i + 1 ) / 2 }
$$

Based the construction, $B _ { 2 1 t + 2 i + 1 }$ contains exactly three cycles of lengths:

$$
2 1 t + 2 i + 1 , 2 3 t + 2 i , 2 5 t + 2 i .
$$

For $\begin{array} { r } { 0 \leq i \leq \frac { t - 3 } { 2 } } \end{array}$ , let the subgraph $B _ { 2 1 t + 2 i }$ consists of a cycle

$$
x v _ { i } ^ { 1 } v _ { i } ^ { 2 } . . . v _ { i } ^ { 2 5 t + 2 i } x
$$

and a path:

$$
x v _ { i , 1 } ^ { 1 } v _ { i , 1 } ^ { 2 } . . . v _ { i , 1 } ^ { 9 t + i - 1 } v _ { i } ^ { 1 2 t + i }
$$

Based the construction, $B _ { 2 1 t + 2 i }$ contains exactly three cycles of lengths:

$$
2 1 t + 2 i , 2 2 t + 2 i + 1 , 2 5 t + 2 i + 1 .
$$

For $\begin{array} { r } { i = \frac { t - 1 } { 2 } } \end{array}$ ， $B _ { 2 1 t + 2 i }$ is simply a cycle of length $2 2 t - 1$

For $\begin{array} { r } { 0 \leq i \leq \frac { t - 3 } { 2 } } \end{array}$ , let the subgraph $B _ { 2 3 t + 2 i + 1 }$ consists of a cycle

$$
x w _ { i } ^ { 1 } w _ { i } ^ { 2 } . . . w _ { i } ^ { 2 6 t + 2 i + 1 } x
$$

and a path:

$$
x w _ { i , 1 } ^ { 1 } w _ { i , 1 } ^ { 2 } . . . w _ { i , 1 } ^ { ( 2 1 t + 2 i - 1 ) / 2 } w _ { i } ^ { ( 2 5 t + 2 i + 1 ) / 2 }
$$

Based the construction, $B _ { 2 3 t + 2 i + 1 }$ contains exactly three cycles of lengths:

$$
2 3 t + 2 i + 1 , 2 4 t + 2 i + 2 , 2 6 t + 2 i + 2 .
$$

For $\begin{array} { r } { i = \frac { t - 1 } { 2 } } \end{array}$ ， $B _ { 2 3 t + 2 i + 1 }$ is simply a cycle of length $2 4 t$

For $5 8 \leq i \leq t - 7 4 2$ , let the subgraph $B _ { 2 7 t + i - 5 7 }$ consists of a cycle

$$
C _ { 2 7 t + i - 5 7 } = x y _ { i } ^ { 1 } y _ { i } ^ { 2 } . . . y _ { i } ^ { 1 3 2 t + 1 1 i + 8 9 3 } x
$$

and ten paths sharing a common vertex $x$ , the other end vertices are on the cycle $C _ { 2 7 t + i - 5 7 }$

$$
\begin{array} { r l } & { \begin{array} { r l } & { \mathcal { A } _ { 1 , 1 } ^ { 0 } \xi _ { 1 , 1 } ^ { 2 } , \ldots , \phi _ { 1 , 1 1 } ^ { ( 1 , T ) } } \\ & { \mathcal { A } _ { 2 , 1 } ^ { 0 } \xi _ { 1 , 1 } ^ { 2 } , \ldots , \phi _ { 1 , 1 1 } ^ { ( 1 , T ) } } \\ & { \mathcal { A } _ { 3 , 2 } ^ { 0 } \xi _ { 2 , 1 } ^ { 2 } , \ldots , \phi _ { 1 , 2 } ^ { ( T ) } } \\ & { \mathcal { A } _ { 3 , 1 } ^ { 0 } \phi _ { 1 , 2 } ^ { 2 } , \ldots , \phi _ { 1 , 4 } ^ { ( T ) } } \\ & { \mathcal { A } _ { 4 , 3 } ^ { 0 } \phi _ { 2 , 2 } ^ { 2 } , \ldots , \phi _ { 1 , 4 } ^ { ( T ) } } \\ & { \mathcal { A } _ { 4 , 4 } ^ { 0 } \phi _ { 4 , 1 } ^ { 2 } , \ldots , \phi _ { 1 , 4 } ^ { ( T ) } , \mathcal { A } _ { 9 , 2 } ^ { 0 } \phi _ { 1 , 4 } ^ { ( T ) , 1 , 1 ; 2 ; 1 ; 4 ; 4 } } \end{array} } \\ &  \begin{array} { r l } & { \mathcal { A } _ { 1 , 1 } ^ { 0 } \xi _ { 2 , 1 } ^ { 2 } , \ldots , \phi _ { 1 , 4 } ^ { ( T ) , 1 } , \mathcal { A } _ { 2 , 1 ; 1 ; 1 ; 4 ; 1 ; 4 ; 1 ; 4 ; 1 } ^ { 2 } } \\ & { \mathcal { A } _ { 3 , 2 } ^ { 0 } \xi _ { 3 , 1 } ^ { 2 } , \ldots , \phi _ { 1 , 4 } ^ { ( T ) , 1 } , \mathcal { A } _ { 2 , 1 ; 1 ; 1 ; 4 ; 1 ; 1 ; 4 ; 1 ; 4 } ^ { 2 } } \\ & { \mathcal { A } _ { 4 , 3 } ^ { 0 } \xi _ { 4 , 1 } ^ { 2 } , \ldots , \phi _ { 1 , 4 } ^ { ( T ) , 1 } , \mathcal { A } _ { 2 , 1 ; 1 ; 1 ; 4 ; 1 ; 1 ; 4 ; 1 ; 1 ; 4 } ^ { 2 } } \\ &  \mathcal { A } _ { 4 , 4 } ^ { 0 } \xi _ { 2 , 4 } ^ { 2 } , \ldots , \phi _ { 1 , 4 } ^ { ( T ) , 1 / 2 } \phi _ { 1 , 4 } ^ { ( 1 , 2 ) , 1 } \ldots \mathrm { t a n h } _ { 1 } \phi _ { 1 , 4 , 1 ; 1 ; 1 ; 4 ; 1 ; 1 ; 4 ; 1 ; 4 ; 1 } \\ &  \mathcal { A } _ { 4 , 1 } ^ { 0 } \phi _ { 4 , 1 , 4 ; 1 } ^ { 2 } , \ldots , \phi _ { 1 , 4 , 1 ; 1 ; 4 ; 1 ; 4 ; 1 ; 1 ; 4 ; 1 ; 1 ; 4 ; 1 ; 1 ; 1 } \\ &  \mathcal  \end{array} \end{array}
$$

As a cycle with $d$ chords contains $\binom { d + 2 } { 2 }$ distinct cycles, $B _ { 2 7 t + i - 5 7 }$ contains exactly 66 cycles of lengths:

27t +i- 57, 28t+ i+7, 29t +i+ 210, 30t +i,  
31t +i+1, 32t+ i, 33t+ i, 34t+i-5,  
35t +i+ 3, 36t + i+ 3, 37t + i+ 742, 38t + 2i - 51,  
38t + 2i + 216, 40t + 2 + 209, 40t + 2i, 42t + 2i,  
42t + 2i-1, 44t + 2i-6, 44t + 2i-3, 46t + 2i + 5,  
46t + 2i + 744, 48t + 3i + 158, 49t + 3i + 215, 50t + 3i + 209,  
51t + 3i-1, 52t + 3i -1, 53t + 3i - 7, 54t + 3i -4,  
55t + 3i-1, 56t+ 3i+746, 59t + 4i+157， 59t + 4i + 215,  
61t + 4i + 208, 61t + 4i- 2, 63t + 4i - 7, 63t + 4i- 5,  
65t + 4i-2, 65t + 4i + 740, 69t + 5i + 157, 70t + 5i + 214,  
71t + 5i + 207, 72t + 5i - 8, 73t + 5i - 5, 74t + 5i - 3,  
75t+5i+739, 80t + 6i + 156, 80t +6i +213， 82t +6i + 201,  
82t +6i- 6, 84t +6i - 3, 84t + 6i +738， 90t +7i+155,  
91t + 7i + 207, 92t + 7i + 203, 93t + 7i - 4, 94t + 7i + 738,  
101t + 8i+149， $1 0 1 t + 8 i + 2 0 9$ ，103t +8i + 205,103t+8i+ 737,  
$1 1 1 t + 9 i + 1 5 1$ ， $1 1 2 t + 9 i + 2 1 1$ ， $1 1 3 t + 9 i + 9 4 6$ ，122t+10i + 153  
$1 2 2 t + 1 0 i + 9 5 2$ ， $1 3 2 t + 1 1 i + 8 9 4$

$B _ { 0 }$ is a path with an end vertex $x$ and length $n - n _ { t }$ . Other $B _ { i }$ is simply a cycle of length $i$ ：

Then $\begin{array} { r } { f ( n ) \geq n + \frac { 1 0 7 } { 3 } t + \frac { 7 } { 3 } } \end{array}$ ,for $n \geq n _ { t }$ . This completes the proof.

From Theorem 7, we have

$$
\operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { } \frac { f ( n ) - n } { \sqrt { n } } \geq \sqrt { 2 + \frac { 7 6 5 4 } { 1 9 0 7 1 } } ,
$$

which is better than the previous bounds $\sqrt { 2 }$ (see[15]), $\sqrt { 2 + \frac { 2 } { 5 } }$ (see[9])

So Conjecture 4 is not true.

Combining this with Boros, Caro, Firedi and Yuster's upper bound, namely

Theorem 2, we get

$$
1 . 9 8 \geq \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { \sqrt { n } } \frac { f ( n ) - n } { \sqrt { n } } \geq \operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \sqrt { n } } \frac { f ( n ) - n } { \sqrt { n } } \geq \sqrt { 2 + \frac { 7 6 5 4 } { 1 9 0 7 1 } } .
$$

# 3 Acknowledgment

The author would like to thank the referees for their many valuable comments and suggestions.

# References

[1] J.A. Bondy and U.S.R. Murty, Graph Theory with Applications (Macmillan, New York, 1976).MR3138588   
[2] E. Boros, Y. Caro, Z. Furedi and R. Yuster, Covering non-uniform hypergraphs, J. Combin. The0ry Ser.B 82(2001)，270-284. MR1842115 (2002g:05130)   
[3] G.Chen，J. Lehel，M. S. Jacobson and W. E. Shreve，Note on graphs without repeated cycle lengths, J. Graph Theory. 29(1998),11-15. MR1633908 (2000d:05059)   
[4] J. C. George,A. Khodkar, W. D. Wallis, Pancyclic and bipancyclic graphs, Springer Briefs in Mathematics,Springer,Cham,2016.MR3495006   
[5] X. Jia, Some extremal problems on cycle distributed graphs,Congr. Numer. 121(1996), 216-222. MR1431994 (97i:05068)   
[6] C.Lai, On the size of graphs with all cycle having distinct length, Discrete Math. 122(1993) 363-364. MR1246693(94i:05048)   
[7] C.Lai, The edges in a graph in which no two cycles have the same length, J. Zhangzhou Teachers College (Natural Science) 8(4)(1994)， 30-34. MR1336586 (96h:05121)   
[8] C. Lai, A lower bound for the number of edges in a graph containing no two cycles of the same length,Electron. J. Combin.8(2001),N9,1 - 6. MR1877662 (2002k:05124)   
[9] C.Lai, Graphs without repeated cycle lengths,Australas. J. Combin. 27(2003), 101-105.MR1955391 (2003m:05102)   
[10] C. Lai， M. Liu, Some open problems on cycles,J. Combin. Math. Combin. Comput. 91(2014), 51-64.MR3287706   
[11] S. Liu, On $r$ -(k)-pancyclic graphs,Ars Combin.accepted. [12] S. C.Locke, Unsolved problems: http://math.fau.edu/locke/Unsolved.htm [13] K. Markstrom,A note on uniquely pancyclic graphs,Australas. J. Combin. 44 (2009)，105-110. MR2527003 (2010i:05180) [14] Y. Shi, Some theorems of uniquely pancyclic graphs, Discrete Math. 59 (1986), no.1-2,167-180.MR0837964 [15] Y. Shi, On maximum cycle-distributed graphs, Discrete Math. 71(1988), 57-71. MR0954686 (89i:05169) [16] Y. Shi, The number of edges in a maximum graphs with uni-length cycles, Kexue Tongbao. 33(10)(1988), 795 - 796. [17] Y. Shi, H. P. Yap, S. K. Teo, On uniquely $r$ -pancyclic graphs, Graph theory and its applications: East and West (Jinan, 1986)，Ann. New York Acad. Sci.   
576(1989),487-499. MR1110849 (93d:05088) [18] Y. Shi， Some theorems on simple MCD-graphs,J. Math. Res. Exposition   
11(4)(1991), 551-554. MR1144956 (92i:05182) [19] Y. Shi, The number of edges in a maximum cycle distributed graph, Discrete Math.104(1992), 205-209. MR1172850 (93d:05083) [20] Y. Shi, On simple MCD graphs containing a subgraph homemorphic to $K _ { 4 }$ ， Discrete Math. 126(1994),325-338. MR1264498 (95f:05072) [21] F. Tian, The progress on some problems in graph theory, Qufu Shifan Daxue Xuebao Ziran Kexue Ban. 1986,no.2, 30-36.MR0865617 [22] H. P. Yap, S.K. Teo, On uniquely $r$ -pancyclic graphs, Lecture Notes in Math.   
1073(1984), 334-335. [23] C. T. Zamfirescu, (2)-pancyclic graphs, Discrete Appl. Math. 161(2013),1128-   
1136.MR3030597 [24] K. Zhang, Progress of some problems in graph theory, J. Math. Res. Exposition   
27(3)(2007)， 563-576. MR2349503