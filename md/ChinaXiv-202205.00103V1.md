# ALOWER BOUND OF THE NUMBER OF EDGES IN A GRAPH CONTAINING NO TWO CYCLES OF THE SAMELENGTH

Chunhui Lai \*   
Dept. of Math., Zhangzhou Teachers College,   
Zhangzhou,Fujian 3630o0,P.R. of CHINA. zjlaichu@public.zzptt.fj.cn

Submitted: November 3, 2000; Accepted: October 20,2001. MR Subject Classifications: O5C38,O5C35 Key words: graph, cycle, number of edges

# Abstract

In 1975, P. Erdos proposed the problem of determining the maximum number $f ( n )$ of edges in a graph of $n$ vertices in which any two cycles are of different lengths. In this paper, it is proved that

$$
f ( n ) \geq n + 3 2 t - 1
$$

for t = 27720r +169 (r ≥ 1) and n ≥ 6911t² + 514441t _ 3309665. Consequently, （20 $\begin{array} { r } { \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } \frac { f ( n ) - n } { \sqrt { n } } \geq \sqrt { 2 + \frac { 2 5 6 2 } { 6 9 1 1 } } } \end{array}$ （204号

# 1 Introduction

Let $f ( n )$ be the maximum number of edges in a graph on $n$ vertices in which no two cycles have the same length. In 1975, Erdos raised the problem of determining $f ( n )$ (see [1], p.247, Problem 11). Shi[2] proved that

$$
f ( n ) \geq n + [ ( \sqrt { 8 n - 2 3 } + 1 ) / 2 ]
$$

for $n \geq 3$ . Lai[3,4,5,6] proved that for $n \geq ( 1 3 8 1 / 9 ) t ^ { 2 } + ( 2 6 / 4 5 ) t + 9 8 / 4 5 , t = 3 6 0 q + 7 ,$ （20

$$
f ( n ) \geq n + 1 9 t - 1 ,
$$

and for $n \geq e ^ { 2 m } ( 2 m + 3 ) / 4$

$$
f ( n ) < n - 2 + \sqrt { n l n ( 4 n / ( 2 m + 3 ) ) + 2 n } + l o g _ { 2 } ( n + 6 ) .
$$

Boros, Caro, Firedi and Yuster[7] proved that

$$
f ( n ) \leq n + 1 . 9 8 { \sqrt { n } } ( 1 + o ( 1 ) ) .
$$

Let $v ( G )$ denote the number of vertices,and $\epsilon ( G )$ denote the number of edges. In this paper, we construct a graph $G$ having no two cycles with the same length which leads to the following result.

Theorem.Let $t = 2 7 7 2 0 r + 1 6 9$ ( $r \geq 1$ ),then

$$
f ( n ) \geq n + 3 2 t - 1
$$

for $\begin{array} { r } { n \geq \frac { 6 9 1 1 } { 1 6 } t ^ { 2 } + \frac { 5 1 4 4 4 1 } { 8 } t - \frac { 3 3 0 9 6 6 5 } { 1 6 } } \end{array}$

# 2 Proof of Theorem

Proof. Let $t = 2 7 7 2 0 r + 1 6 9 , r \geq 1$ ， $\begin{array} { r } { n _ { t } = \frac { 6 9 1 1 } { 1 6 } t ^ { 2 } + \frac { 5 1 4 4 4 1 } { 8 } t - \frac { 3 3 0 9 6 6 5 } { 1 6 } } \end{array}$ ， $n \geq n _ { t }$ . We shall show that there exists a graph $G$ on $n$ vertices with $n + 3 2 t - 1$ edges such that all cycles in $G$ have distinct lengths.

Now we construct the graph $G$ which consists of a number of subgraphs: $B _ { i }$ ， $( 0 ~ \leq$ i $\begin{array} { r } { \leq 2 1 t + \frac { \iota t + 1 } { 8 } - 5 8 , 2 2 t - 7 9 8 \leq i \leq 2 2 t + 6 4 , 2 3 t - 7 3 4 \leq i \leq 2 3 t + 2 6 7 , 2 4 t - 5 3 . } \end{array}$ $t + 5 7 , 2 5 t - 7 4 1 \leq i \leq 2 5 t + 5 8 , 2 6 t - 7 4 0 \leq i \leq 2 6 t + 5 7 , 2 7 t - 7 4 1 \leq i$ ≤ 27t + 57 $, 2 8 t - 7 4 1 \leq i \leq 2 8 t + 5 2 , 2 9 t - 7 4 6 \leq i \leq 2 9 t + 6 0 , 3 0 t - 7 3 8 \leq i \leq 3 0 t + 6 0$ ，and $3 1 t - 7 3 8 \leq i \leq 3 1 t + 7 9 9 )$

Now we define these $B _ { i }$ 's. These subgraphs all have a common vertex $x$ ，otherwise their vertex sets are pairwise disjoint.

For $\textstyle { \frac { 7 t + 1 } { 8 } } \leq i \leq t - 7 4 2$ , let the subgraph $B _ { 1 9 t + 2 i + 1 }$ consist of a cycle

$$
C _ { 1 9 t + 2 i + 1 } = x x _ { i } ^ { 1 } x _ { i } ^ { 2 } . . . x _ { i } ^ { 1 4 4 t + 1 3 i + 1 4 6 3 } x
$$

and eleven paths sharing a common vertex $x$ ，the other end vertices are on the cycle $C _ { 1 9 t + 2 i + 1 }$ ：

$$
\begin{array} { r l } & { x x _ { i , 1 } ^ { 1 } x _ { i , 1 } ^ { 2 } . . . x _ { i , 1 } ^ { ( 1 1 t - 1 ) / 2 } x _ { i } ^ { ( 3 1 t - 1 1 5 ) / 2 + i } } \\ & { x x _ { i , 2 } ^ { 1 } x _ { i , 2 } ^ { 2 } . . . . x _ { i , 2 } ^ { ( 1 3 t - 1 ) / 2 } x _ { i } ^ { ( 5 1 t - 1 0 3 ) / 2 + 2 i } } \\ & { x x _ { i , 3 } ^ { 1 } x _ { i , 3 } ^ { 2 } . . . x _ { i , 3 } ^ { ( 1 3 t - 1 ) / 2 } x _ { i } ^ { ( 7 1 t + 3 1 5 ) / 2 + 3 i } } \\ & { x x _ { i , 4 } ^ { 1 } x _ { i , 4 } ^ { 2 } . . . x _ { i , 4 } ^ { ( 1 5 t - 1 ) / 2 } x _ { i } ^ { ( 9 1 t + 3 1 3 ) / 2 + 4 i } } \\ & { x x _ { i , 5 } ^ { 1 } x _ { i , 5 } ^ { 2 } . . . x _ { i , 5 } ^ { ( 1 5 t - 1 ) / 2 } x _ { i } ^ { ( 1 1 t + 3 1 3 ) / 2 + 5 i } } \end{array}
$$

$$
\begin{array} { r l } & { x x _ { i , 6 } ^ { 1 } x _ { i , 6 } ^ { 2 } . . . x _ { i , 6 } ^ { ( 1 / \ell - 1 ) / 2 } x _ { i } ^ { ( 1 / 1 + 1 3 1 ) / 2 + 6 i } } \\ & { x x _ { i , 7 } ^ { 1 } x _ { i , 7 } ^ { 2 } . . . x _ { i , 7 } ^ { ( 1 / \ell - 1 ) / 2 } x _ { i } ^ { ( 1 / 1 + 3 0 9 ) / 2 + 7 i } } \\ & { x x _ { i , 8 } ^ { 1 } x _ { i , 8 } ^ { 2 } . . . x _ { i , 8 } ^ { ( 1 9 \ell - 1 ) / 2 } x _ { i } ^ { ( 1 7 / 1 + 2 9 7 ) / 2 + 8 i } } \\ & { x x x _ { i , 9 } ^ { 1 } x _ { i , 9 } ^ { 2 } . . . x _ { i , 9 } ^ { ( 1 9 \ell - 1 ) / 2 } x _ { i } ^ { ( 1 9 \ell + 3 0 1 ) / 2 + 9 i } } \\ & { x x _ { i , 1 0 } ^ { 1 } x _ { i , 1 0 } ^ { 2 } . . . x _ { i , 1 0 } ^ { ( 2 1 \ell - 1 ) / 2 } x _ { i } ^ { ( 2 1 \ell + 3 0 5 ) / 2 + 1 0 i } } \\ & { x x _ { i , 1 1 } ^ { 1 } x _ { i , 1 1 } ^ { 2 } . . . x _ { i , 1 1 } ^ { ( 1 \ell - 1 ) / 1 } x _ { i } ^ { ( 2 \ell ) } x _ { i } ^ { ( 2 5 1 \ell + 2 3 5 7 ) / 2 + 1 1 i } . } \end{array}
$$

From the construction, we notice that $B _ { 1 9 t + 2 i + 1 }$ contains exactly seventy-eight cycles of lengths:

Similarly, for $\textstyle 5 8 \leq i \leq { \frac { 7 t - 7 } { 8 } }$ , let the subgraph $B _ { 2 1 t + i - 5 7 }$ consist of a cycle

$$
x y _ { i } ^ { 1 } y _ { i } ^ { 2 } . . . y _ { i } ^ { 1 2 6 t + 1 1 i + 8 9 3 } x
$$

and ten paths

$$
\begin{array} { r l } & { x y _ { i , 1 } ^ { 1 } y _ { i , 1 } ^ { 2 } . . . y _ { i , 1 } ^ { ( 1 1 t - 1 ) / 2 } y _ { i } ^ { ( 3 1 t - 1 1 5 ) / 2 + i } } \\ & { x y _ { i , 2 } ^ { 1 } y _ { i , 2 } ^ { 2 } . . . y _ { i , 2 } ^ { ( 1 3 t - 1 ) / 2 } y _ { i } ^ { ( 5 1 t - 1 0 3 ) / 2 + 2 i } } \\ & { x y _ { i , 3 } ^ { 1 } y _ { i , 3 } ^ { 2 } . . . y _ { i , 3 } ^ { ( 1 3 t - 1 ) / 2 } y _ { i } ^ { ( 7 1 t + 3 1 5 ) / 2 + 3 i } } \end{array}
$$

$$
\begin{array} { r l } & { \mathcal { D } \| _ { \phi _ { i } ^ { 1 } , ( \frac { 1 } { 2 } , \theta _ { i } ^ { 2 } , \theta _ { i } ^ { 2 } , \theta _ { i } ^ { 2 } ) } ^ { 1 } \| \mathcal { D } _ { \phi _ { i } ^ { 1 } } ^ { ( 1 1 + 3 ) / 2 } \phi ^ { ( 1 1 + 1 3 ) / 2 + 4 1 } } \\ & { \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 5 ) } ^ { 1 } \theta _ { i , 5 } ^ { 2 } \theta _ { i , 5 } ^ { 2 } \theta _ { i , 5 } ^ { 3 } \| \mathcal { D } _ { \phi _ { i } ^ { 1 } } ^ { ( 1 1 + 1 3 ) / 2 + 5 6 } } \\ & { \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 6 ) } ^ { 1 } \theta _ { i , 5 } ^ { 2 } \theta _ { i , 5 } ^ { 3 } \theta _ { i , 5 } ^ { 4 } \theta _ { i , 7 } ^ { 4 } } \\ & { \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 6 ) } ^ { 2 } \theta _ { i , 5 } ^ { 2 } \theta _ { i , 7 } ^ { 3 } \| \mathcal { D } _ { \phi _ { i } ^ { 1 } } ^ { ( 1 1 + 1 3 ) / 2 + 6 6 } } \\ & { \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 7 ) } ^ { 2 } \theta _ { i , 7 } ^ { 2 } \theta _ { i , 7 } ^ { 3 } \| \mathcal { D } _ { \phi _ { i } ^ { 1 } } ^ { ( 1 1 + 1 3 ) / 2 + 2 8 } } \\ & { \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 3 ) } ^ { 3 } \theta _ { i , 8 } ^ { 2 } \theta _ { i , 5 } ^ { 3 } \| \mathcal { D } _ { \phi _ { i } ^ { 1 } } ^ { ( 1 1 + 1 3 ) / 2 + 6 8 } } \\ &  \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 3 ) } ^ { 4 } \theta _ { i , 8 } ^ { 2 } \theta _ { i , 5 } ^ { 3 } \theta _ { i , 5 } ^ { 3 } \| \mathcal { D } _ { \phi _ { i } ^ { 1 } } ^ { ( 1 1 + 1 2 9 ) / 2 + 8 0 } \\ & { \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 3 ) } ^ { 1 } \theta _ { i , 5 } ^ { 2 } \theta _ { i , 5 } ^ { ( 1 1 + 1 3 ) / 2 } \phi _ { i } ^ { 1 } } \\ & { \mathcal { N } \| _ { \phi _ { i } ^ { 1 } , ( 3 ) } ^ { 1 } \theta _ { i , 5 } ^ { 2 } \theta _ { i , 6 } ^ { 1 1 / 2 + 1 6 } } \\ &  \mathcal { N } \| _  \end{array}
$$

Based on the construction, $B _ { 2 1 t + i - 5 7 }$ contains exactly sixty-six cycles of lengths:

$B _ { 0 }$ is a path with an end vertex $x$ and length $n - n _ { t }$ .Other $B _ { i }$ is simply a cycle of length $i$ ：

It is easy to see that

$$
\begin{array} { r c l } { ( G ) } & { = } & { v ( B _ { 0 } ) + \sum _ { i = 1 } ^ { 1 9 t + \frac { 7 t + 1 } { 4 } } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 1 } ^ { t - 7 4 2 } ( v ( B _ { 1 9 t + 2 i + 1 } ) - 1 ) } \\ & & { + \sum _ { i = \frac { 7 t + 1 } { 8 } } ^ { t - 7 4 2 } ( v ( B _ { 1 9 t + 2 i + 2 } ) - 1 ) + \sum _ { i = 2 1 t - 1 4 8 1 } ^ { 2 1 t } ( v ( B _ { i } ) - 1 ) } \\ & & { + \sum _ { i = 5 8 } ^ { \frac { 7 t - 7 } { 8 } } ( v ( B _ { 2 1 t + i - 5 7 } ) - 1 ) + \sum _ { i = 2 2 t - 7 9 8 } ^ { 2 2 t + 6 4 } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 2 3 t - 7 3 4 } ^ { 2 3 t + 2 6 7 } ( v ( B _ { i } ) - 1 ) } \\ & & { + \sum _ { i = 4 5 7 } ^ { 2 4 t + 5 7 } 3 1 ( v ( B _ { i } ) - 1 ) + \sum _ { i = 2 5 6 } ^ { 2 5 t + 5 8 } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 2 6 t - 7 4 0 } ^ { 2 6 t + 5 7 } ( v ( B _ { i } ) - 1 ) } \\ & & { + \sum _ { i = 2 7 t - 7 4 1 } ^ { 2 0 t + 5 7 } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 2 5 6 - 7 4 1 } ^ { 2 5 t + 5 8 } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 2 9 t - 7 4 6 } ^ { 2 0 t + 6 7 } ( v ( B _ { i } ) - 1 ) } \\ & & { + \sum _ { i = 2 7 t - 7 4 1 } ^ { 3 0 t + 6 0 } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 3 1 t - 7 3 8 } ^ { 3 1 t + 7 9 9 } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 2 9 t - 7 4 6 } ^ { 2 9 t + 6 7 } ( v ( B _ { i } ) - 1 ) } \\ & & { + \sum _ { i = 3 0 t - 7 3 8 } ^ { 3 0 t + 6 0 } ( v ( B _ { i } ) - 1 ) + \sum _ { i = 3 1 t - 7 3 8 } ^ { 3 1 t + 7 9 9 } ( v ( B _ { i } ) - 1 ) } \end{array}
$$

$$
\begin{array} { r l } { = } & { n - n _ { t } + 1 + \sum _ { i = 1 } ^ { 1 9 \Gamma } \frac { 7 + i } { 4 } \big ( i - 1 \big ) + \sum _ { i = 2 } ^ { i - 7 4 } \big ( 1 4 i + 1 3 i + 1 4 6 3 } \\ & { + \frac { 1 1 3 i - 1 } { 4 } + \frac { 1 3 i - 1 } { 2 } + \frac { 1 3 i - 1 } { 2 } + \frac { 1 5 i - 1 } { 4 } + \frac { 1 3 i - 1 } { 4 } + \frac { 1 4 i - 1 } { 2 } + \frac { 1 7 i - 1 } { 4 } + \frac { 1 7 i - 1 } { 2 } } \\ & { + \frac { 1 9 2 - 1 } { 2 } + \frac { 1 9 2 - 1 } { 2 } + \frac { 2 1 7 - 1 } { 4 } + \frac { i - 9 2 1 } { 2 } \big ) + \sum _ { i = 2 } ^ { i - 7 2 } \frac { 1 9 4 i } { 2 } \big ( 1 9 4 i + 2 i + 1 \big ) } \\ & { + \sum _ { i = 1 , 2 1 , \ldots 1 6 1 } ^ { 2 i + 1 0 \Gamma } \big ( i - 1 \big ) + \sum _ { j = 3 0 } ^ { i - 8 } \big ( 1 2 i + 1 1 i + 8 j 3 \big ) } \\ & { + \frac { 1 1 1 i - 1 } { 4 } + \frac { 1 3 i - 1 } { 4 } + \frac { 1 3 i - 1 } { 4 } + \frac { 1 5 i - 1 } { 4 } + \frac { 1 6 i - 1 } { 2 } + \frac { 1 7 i - 1 } { 4 } + \frac { 1 7 i - 1 } { 2 } } \\ & { + \frac { 1 9 2 - 1 } { 2 } + \frac { 1 9 2 - 1 } { 2 } + \frac { 2 1 7 - 1 } { 4 } \big ) + \sum _ { i = 2 } ^ { 2 i + 6 4 \Gamma } \big ( i - 1 \big ) } \\ & { + \sum _ { i = 2 , 3 0 , \ldots 2 6 } ^ { 2 i + 2 0 \Gamma } \frac { 7 - 1 } { 4 } ( i - 1 ) + \sum _ { i = 2 , 4 0 , \ldots 2 6 } ^ { 2 i + 6 4 \Gamma } ( i - 1 ) } \\ & { + \sum _ { i = 2 , 4 0 , \ldots 2 6 } ^ { 2 i + 3 + 2 0 \Gamma } ( i - 1 ) + \sum _ { i = 2 , 4 0 , \ldots 2 6 } ^ { 2 i + 6 4 \Gamma } ( i - 1 ) } \\ & { + \sum _ { i = 2 , 4 0 , \ldots 2 6 } ^ { 2 i + 1 0 \Gamma } ( i - 1 ) + \sum _ { i = 2 , 4 0 , \ldots 2 6 } ^ { 2 i + 6 4 \Gamma } ( i - 1 ) + \sum _ { i = 2 , 4 0 , \ldots 2 6 } ^ { 2 i + 6 4 \Gamma } 2 ( i - 1 ) } \\ & { + \sum _ { i = 2 , 4 0 , \ldots 2 6 } ^ { 2 i + 1 0 \Gamma } 2 ( i ) } \\ &  - \sum _  i = 2 ,  \end{array}
$$

Now we compute the number of edges of $G$

$$
\begin{array} { r l } { \kappa ( \mathcal { Q } ) } & { = \kappa ( \mathcal { R } _ { 1 } ^ { 2 } - \frac { 1 } { 2 } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } ) ^ { 2 } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } ( \bar { R } _ { 1 } ^ { 2 } - \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } ) ( \bar { R } _ { 1 } ^ { 2 } - \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } ) \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \mathrm { ~ R e } ^ { \mathrm { i } \tau } } \\ & { \quad - \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \sqrt { \Delta R + \mathrm { i } } \gamma _ { 1 } ^ { 2 } + \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } } \\ &  \quad - \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } + \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \\ &  \quad - \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \\ &  \quad - \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \frac { \mathrm { R e } ^ { \mathrm { i } \tau } } { \mathrm { R e } ^ { \mathrm { i } \tau } } \ \end{array}
$$

Then $f ( n ) \geq n + 3 2 t - 1$ ,for $n \geq n _ { t }$ . This completes the proof of the theorem.

From the above theorem,we have

$$
\operatorname* { l i m i n f } _ { n \to \infty } { \frac { f ( n ) - n } { \sqrt { n } } } \geq { \sqrt { 2 + { \frac { 2 5 6 2 } { 6 9 1 1 } } } } ,
$$

rhich is better than the previous bounds $\sqrt { 2 }$ (see [2]), $\textstyle { \sqrt { 2 + { \frac { 4 8 7 } { 1 3 8 1 } } } }$ (see [6]).

Combining this with Boros, Caro, Fiüredi and Yuster's upper bound, we have

$$
1 . 9 8 \geq \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { \sqrt { n } } \frac { f ( n ) - n } { \sqrt { n } } \geq \operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } _ { \sqrt { n } } \frac { f ( n ) - n } { \sqrt { n } } \geq 1 . 5 3 9 7 .
$$

# Acknowledgment

The author thanks Prof. Yair Caro and Raphael Yuster for sending reference [7]. The author also thanks Prof. Cheng Zhao for his advice.

# References

[1] J.A. Bondy and U.S.R. Murty, Graph Theory with Applications (Macmillan, New York,1976).   
[2] Y. Shi, On maximum cycle-distributed graphs, Discrete Math. 71(1988) 57-71.   
[3] Chunhui Lai, On the Erdos problem, J. Zhangzhou Teachers College(Natural Science Edition) 3(1)(1989) 55-59.   
[4] Chunhui Lai, Upper bound and lower bound of $f ( n )$ ， J. Zhangzhou Teachers College(Natural Science Edition) 4(1)(1990) 29,30-34.   
[5] Chunhui Lai, On the size of graphs with all cycle having distinct length, Discrete Math. 122(1993) 363-364.   
[6] Chunhui Lai, The edges in a graph in which no two cycles have the same length, J. Zhangzhou Teachers College (Natural Science Edlition) 8(4)(1994), 30-34.   
[7] E.Boros, Y. Caro, Z. Füredi and R. Yuster， Covering non-uniform hypergraphs (submitted, 2000).