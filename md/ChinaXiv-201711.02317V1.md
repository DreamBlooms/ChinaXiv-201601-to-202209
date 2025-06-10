# Holographic Rényi entropy for two-dimensional N=(2,2) superconformal field theory

Zhibin Li $^ { 1 , 2 }$ \* and Jia-ju Zhang $^ 3$ +

（204号 $^ { 1 }$ Theoretical Physics Division, Institute of High Energy Physics, Chinese Academy of Sciences, 19B Yuquan Rd, Beijing 100049, P.R. China （204号 $^ 2$ Theoretical Physics Center for Science Facilities, Chinese Academy of Sciences, 19B Yuquan Rd,Beijing 100049,P.R.China $^ 3$ Dipartimento di Fisica Universitä degli studi di Milano-Bicocca, Piazz dell Scienza 3, I-2O126 MilanoItaly

# Abstract

We investigate the holographic Rényi entropy for two-dimensional $\mathcal { N } = ( 2 , 2 )$ superconformal field theory (SCFT)，which is dual to $\mathcal { N } = 2$ supergravity in AdS $^ 3$ background. In SCFT we have the stress tensor, current,and their supersymmetric partners,and in supergravity we have the graviton,vector field,and two gravitinos.We get the Rényi mutual information of two short intervals on complex plane in expansion by the cross ratio $x$ to order $x ^ { 4 }$ ,and Rényi entropy of one interval on torus in expansion by $q = \exp ( - 2 \pi \beta / L )$ with $\beta$ being the inverse temperature and $L$ being the spatial period, to order $q ^ { 2 }$ .We calculate in both the supergravity and SCFT sides,and find matches of the results.

# Contents

# 1Introduction

# 2Rényi mutual information of two intervals on complex plane 3

2.1 Supergravity result 3   
2.2 Contributions of $T$ in SCFT 3   
2.3 Contributions of $T$ ， $J$ in SCFT 4   
2.4 Contributions of $T$ ， $J$ ， $G$ and $H$ in SCFT 5

# Rényi entropy of one interval on torus 6

3.1 Supergravity result 6   
3.2 Contributions of $T$ in SCFT 7   
3.3 Contributions of $J$ in SCFT 7   
3.4 Contributions of $G$ and $H$ in SCFT 8

# 4Conclusion and discussion 8

A Review of two-dimensional $\mathcal { N }$ =(2,2) SCFT 9   
B Some useful summation formulas 11

# 1Introduction

Holographic entanglement entropy [1,2] is an interesting subject in the investigation of AdS/CFT (anti-de Sitter/conformal feld theory)correspondence [3-6].To calculate the entanglement entropy one can use the replica trick,calculate the $n$ -th Rényi entropy with $n \in \mathrm { Z }$ and $n > 1$ ,and take the $n  1$ limit to get the entanglement entropy[7-9].Renyi entropy is not only a tool to calculate the entanglement entropy but also interesting in its own right,and one can directly investigate the holographic Rényi entropy [10-16].

Quantum gravity in AdS $_ 3$ background with cosmological constant $\textstyle \Lambda = - { \frac { 1 } { R ^ { 2 } } }$ and small Newton constant $G _ { N }$ （204号 is dual to a two-dimensional CFT with a large central charge [17]

$$
c = { \frac { 3 R } { 2 G _ { N } } } .
$$

There are many investigations of holographic Rényi entropy in AdS $^ 3$ /CFT $^ 2$ correspondence [10,13-15,18-34]. In gravity side,onecan not onlyget the classical part [14,15,25] but also use the partition function of Einstein gravity in handlebody background [35-37] and get the one-loop corrections [15]. In CFT side one can use the operator product expansion (OPE)of twist operators to calculate the Rényi mutual information of two short intervals on complex plane [10,13,18,19],and use the low temperature expansion of density matrix to calculate the Rényi entropy of one interval on torus with low temperature [24,25].

In this paper we investigate the holographic Rényi entropy in another kind of AdS $^ 3$ /CFT $^ 2$ correspondence, the dual between the $\mathcal { N } = 2$ supergravity in AdS $^ 3$ background and the $\mathcal { N } = ( 2 , 2 )$ superconformal field theory (SCFT). In supergravity side we have the fields of graviton, vector and two gravitinos,and we denote them by $g$ ， $v$ and $\psi$ , respectively. Correspondingly, in SCFT side we have the stress tensor $T$ ， $T$ ， current $J$ ， $J$ ,and their superpartners $G$ ， $G$ ， $H$ ， $H$ . Note that the duality between the bosonic part of the supergravity with only graviton and vector field and the bosonic part of the SCFT with only stress tensor and current is self-consistent,and we will also consider the holographic Rényi entropy in such a correspondence.

The remaining part of this paper is arranged as follows. In section 2,we investigate the Rényi mutual information of two short intervals on complex plane.In section 3,we consider the Renyi entropyof one interval on tours with low temperature. Then there is the conclusion and discusson in section 4.In appendix A，we review some details of the $\mathcal { N } = ( 2 , 2 )$ SCFT.In appendix B,we give some useful summation formulas.

# 2 Rényi mutual information of two intervals on complex plane

In this section we calculate the Renyi mutual information of two short intervals on complex plane.In other words,we have the ground state SCFTon space of one-dimensional infinite straight line.We expand the Renyi mutual information by the small cross ratio $x$ to order $x ^ { 4 }$ . In gravity side we use method in [15],and in CFT side we use OPE of twist operators in [10,18,19].

# 2.1 Supergravity result

The classical part of the holographic Rényi mutual information only depends on the classical confguration of the gravity background,and so it is the same as that of pure Einstein gravity. The result can be found in [15]

$$
t _ { n } ^ { \mathrm { c l } } = \frac { c ( n - 1 ) ( n + 1 ) ^ { 2 } x ^ { 2 } } { 1 4 4 n ^ { 3 } } + \frac { c ( n - 1 ) ( n + 1 ) ^ { 2 } x ^ { 3 } } { 1 4 4 n ^ { 3 } } + \frac { c ( n - 1 ) ( n + 1 ) ^ { 2 } ( 1 3 0 9 n ^ { 4 } - 2 n ^ { 2 } - 1 1 ) x ^ { 4 } } { 2 0 7 3 6 0 n ^ { 7 } } + O ( x ^ { 5 } ) .
$$

To calculate the one-loop part of the holographic Rényi mutual information to order $x ^ { 4 }$ ,we need the contributions of the consecutively decreasing words (CDWs)and the 2-CDWs [15].The one-loop part depends on the field content of the gravity theory. For the graviton $g$ we have [15]

$$
I _ { n , g } ^ { \mathrm { 1 - l o o p } } = \frac { ( n + 1 ) ( n ^ { 2 } + 1 1 ) ( 3 n ^ { 4 } + 1 0 n ^ { 2 } + 2 2 7 ) x ^ { 4 } } { 3 6 2 8 8 0 0 n ^ { 7 } } + O ( x ^ { 5 } ) ,
$$

for the vector field $v$ we have

$$
\begin{array} { l } { { I _ { n , v } ^ { \mathrm { 1 - l o o p } } = \displaystyle \frac { ( n + 1 ) ( n ^ { 2 } + 1 1 ) x ^ { 2 } } { 7 2 0 n ^ { 3 } } + \displaystyle \frac { ( n + 1 ) ( 2 3 n ^ { 4 } + 2 3 3 n ^ { 2 } - 4 0 ) x ^ { 3 } } { 1 5 1 2 0 n ^ { 5 } } \ ~ } } \\ { { \displaystyle ~ + \frac { ( n + 1 ) ( 2 1 2 9 n ^ { 6 } + 2 0 4 6 9 n ^ { 4 } - 6 2 8 5 n ^ { 2 } + 2 6 9 5 ) x ^ { 4 } } { 1 4 5 1 5 2 0 n ^ { 7 } } + O ( x ^ { 5 } ) } , } \end{array}
$$

and for the two gravitinos $\psi$ we have

$$
I _ { n , \psi } ^ { 1 \mathrm { \tiny { l } } \mathrm { { l o o p } } } = \frac { ( n + 1 ) ( 2 n ^ { 4 } + 2 3 n ^ { 2 } + 1 9 1 ) x ^ { 3 } } { 3 0 2 4 0 n ^ { 5 } } + \frac { ( n + 1 ) ( 3 3 n ^ { 6 } + 3 5 8 n ^ { 4 } + 2 8 5 7 n ^ { 2 } - 3 6 8 ) x ^ { 4 } } { 3 0 2 4 0 0 n ^ { 7 } } + O ( x ^ { 5 } ) .
$$

# 2.2 Contributions of $T$ in SCFT

Using the replica trick we get the $n$ -fold of the original SCFT,which we call SCFT $^ { " \mathit { n } }$ . In SCFT $^ { 1 \prime } { } ^ { t }$ we use OPE of twist operators to calculate the partition function,and the Rényi mutual information turns out to be [19-21]

$$
I _ { n } = \frac { 2 } { n - 1 } \log \Big [ \sum _ { K } \alpha _ { K } d _ { K } ^ { 2 } x ^ { h \kappa } { } _ { 2 } F _ { 1 } \big ( h _ { K } , h _ { K } ; 2 h _ { K } ; x \big ) \Big ] ,
$$

where the summation of $K$ is over all the linearly independent orthogonalized holomorphic quasiprimary operators （204号 $\Phi _ { K }$ in SCFT $^ n$ .Here $\alpha _ { K }$ ， $d _ { K }$ ， $h _ { K }$ are,respectively, the normalization factor, OPE coeffcient, and conformal

<html><body><table><tr><td>level</td><td>operator</td><td>degeneracy</td><td>number</td></tr><tr><td>0</td><td>1</td><td>1</td><td>1</td></tr><tr><td>2</td><td>T</td><td>n</td><td>n</td></tr><tr><td rowspan="2">4</td><td>A</td><td>n</td><td rowspan="2">n(n+1) 2</td></tr><tr><td>TT</td><td>n(n-1)</td></tr></table></body></html>

Table 1: To level 4 the holomorphic quasiprimary operators in SCFT $^ { 1 \prime } { } ^ { t }$ with contributions of only $T$ . We follow the convention in [31] and omit the replica indices that take values from $0$ to $n - 1$ .Note that the 4th column agrees with the counting in (2.6).

weight of $\Phi _ { K }$ . Note that there is a factor 2 in the right-hand side of (2.5),and this concerns the contributions from the anti-holomorphic sector.

In this subsection we repeat the calculation in [19],with the contributions of only the vacuum conformal family, i.e. the contributions of operators that are constructed solely by $T$ . To level 4 the SCFT $^ { " \mathit { n } }$ quasiprimary operators we have to consider are counted as

$$
( 1 - x ) \chi _ { ( 0 ) } ^ { n } + x = 1 + n x ^ { 2 } + \frac { n ( n + 1 ) } { 2 } x ^ { 4 } + O ( x ^ { 5 } ) ,
$$

with $\chi _ { ( 0 ) }$ in (A.1),and they are listed in table 1. For these quasiprimary operators we have the normalization factors

$$
\alpha _ { 1 } = 1 , \alpha _ { T } = \frac { c } { 2 } , \alpha _ { A } = \frac { c ( 5 c + 2 2 ) } { 1 0 } , \alpha _ { T T } = \frac { c ^ { 2 } } { 4 } ,
$$

and the OPE coefficients

$$
d _ { 1 } = 1 , d _ { T } = \frac { n ^ { 2 } - 1 } { 1 2 n ^ { 2 } } , d _ { A } = \frac { ( n ^ { 2 } - 1 ) ^ { 2 } } { 2 8 8 n ^ { 4 } } , d _ { T T } ^ { j _ { 1 } j _ { 2 } } = \frac { 1 } { 8 n ^ { 4 } c } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 4 } } + \frac { ( n ^ { 2 } - 1 ) ^ { 2 } } { 1 4 4 n ^ { 4 } } .
$$

Using (2.5) we get the Rényi mutual information organized by the large central charge

$$
I _ { n } ^ { ( 0 ) } = I _ { n } ^ { \mathrm { L } } + I _ { n , ( 0 ) } ^ { \mathrm { N L } } + \cdots ,
$$

with the leading part $I _ { n } ^ { \mathrm { L } }$ equaling $I _ { n } ^ { \mathrm { c l } }$ (2.1） and the next-to-leading part In(o) equaling I-oop (2.2).

# 2.3 Contributions of $T$ ， $J$ in SCFT

By adding the contributions of $J$ ，we have to consider the extra quasiprimary operators that are counted as

$$
- x ) \chi _ { ( 0 ) } ^ { n } ( \chi _ { ( 1 ) } ^ { n } - 1 ) = n x + \frac { n ( n + 1 ) } { 2 } x ^ { 2 } + \frac { n ( n ^ { 2 } + 1 2 n - 1 ) } { 6 } x ^ { 3 } + \frac { n ( n ^ { 3 } + 2 6 n ^ { 2 } + 5 9 n + 1 0 ) } { 2 4 } x ^ { 4 } + O ( x ^ { 5 } )
$$

with $\chi _ { ( 0 ) }$ being (A.1） and $\chi _ { ( 1 ) }$ being(A.6),and they are listed in table 2. Only a few of them contribute to the Renyi mutual information. For the relevant operators we have the normalization factors

$$
\begin{array} { l l } { { \displaystyle \alpha _ { J J } = \frac { c ^ { 2 } } { 9 } , } } & { { \displaystyle \alpha _ { I ( J J ) } = \frac { 4 c ^ { 2 } } { 9 } , ~ \alpha _ { J K } = \frac { c ^ { 2 } ( c + 2 ) } { 1 8 } , ~ \alpha _ { \mathcal { M M } } = \frac { 4 c ^ { 2 } ( c - 1 ) ^ { 2 } } { 8 1 } , } } \\ { { \displaystyle \alpha _ { T J J } = \frac { c ^ { 3 } } { 1 8 } , ~ \alpha _ { J J \mathcal { M } } = \frac { 2 c ^ { 3 } ( c - 1 ) } { 8 1 } , ~ \alpha _ { J J J J } = \frac { c ^ { 4 } } { 8 1 } , ~ \alpha _ { I I ( J J ) } = \frac { 2 0 c ^ { 2 } } { 2 7 } , } } \end{array}
$$

and the OPE coefficients

$$
\begin{array} { l } { { d _ { J J } ^ { j _ { 1 } j _ { 2 } } = - \displaystyle { \frac { 3 } { 4 \pi ^ { 2 } c } \displaystyle { \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } } } , } , } } \end{array} \ d _ { I I J } ^ { j _ { 1 } j _ { 2 } } = - \displaystyle { \frac { 3 } { 8 n ^ { 3 } c } \displaystyle { \frac { \xi _ { j _ { 1 } j _ { 2 } } } { s _ { j _ { 1 } j _ { 2 } } ^ { 3 } } , } } \ d _ { J K } ^ { j _ { 1 } j _ { 2 } } = - \displaystyle { \frac { n ^ { 2 } - 1 } { 1 6 n ^ { 4 } c } \displaystyle { \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 2 } } } , } \ d _ { M M } ^ { j _ { 1 } j _ { 2 } } = \displaystyle { \frac { 9 } { 3 2 n ^ { 4 } c ( c - 1 ) } \displaystyle { \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 4 } } } , }   \\ { { d _ { I J J } ^ { j _ { 1 } j _ { 2 } j _ { 3 } } = \displaystyle { \frac { 1 } { 1 6 n ^ { 4 } c ^ { 2 } } \big ( \displaystyle { \frac { 1 } { c ^ { 2 } s _ { j _ { 1 } j _ { 2 } } ^ { 2 } s _ { j _ { 1 } j _ { 3 } } ^ { 2 } } - \frac { 1 } { c } \big (  { \frac { 1 } { s _ { j } _ { 2 } j _ { 2 } } } \big ) , }   { \frac { 1 } { s _ { j _ { 2 } j _ { 2 } } } ^ { 2 } } \big ) , } \ d _ { J J M } ^ { j _ { 1 } j _ { 2 } j _ { 3 } } = \displaystyle { \frac { 9 } { 1 6 n ^ { 4 } c ^ { 2 } } \displaystyle { \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 2 } } } , } } } \\   d _ { J J J } ^ { j _ { 1 } j _ { 2 } j _ { 1 } } = \displaystyle  \frac { 9 } { 1 6 n ^ { 4 } c ^ { 2 } } \big ( \displaystyle  \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 2 } s _ { j _ { 3 } j _ { 4 } } ^ { 2 } } + \frac { 1 } { s _ { j _ { 1 } j _ { 3 } } ^ { 2 } s _ { j _ { 2 } 4 } ^ { 2 } } + \frac { 1 } { s _ { j _ { 1 } j _ { 4 } } ^ { 2 } s _ { j _ { 2 } j _ { 3 } } ^ { 2 } \big ) , } \ d _ { I I } ^ { j _ { 1 } j _ { 2 } } = - \displaystyle  \frac { 3 } { 1 6 0 n ^ { 4 } c } \big ( \frac { 1 5 } { s _ { j _ { 1 } j _ { 2 } } ^ { 4 } } - \frac  2 ( n
$$

<html><body><table><tr><td>level</td><td>operators</td><td>？</td><td>degeneracy</td><td>number</td></tr><tr><td>1</td><td>J</td><td>×</td><td>n</td><td>n</td></tr><tr><td rowspan="2">2</td><td></td><td></td><td></td><td rowspan="2">n(n+1)</td></tr><tr><td>MJ</td><td>×></td><td>m</td></tr><tr><td rowspan="4"></td><td>K,0</td><td>×</td><td>2n</td><td rowspan="4">n(n2+12n-1)</td></tr><tr><td></td><td></td><td></td></tr><tr><td>TJJM</td><td>××</td><td>2n(n -1)</td></tr><tr><td>I(JJ)</td><td>√</td><td>n(n-1)</td></tr><tr><td rowspan="8">4</td><td>L,N,P1, P2</td><td>×</td><td>4n</td><td rowspan="9">n(n³+26n²+59n+10) 24</td></tr><tr><td></td><td></td><td></td></tr><tr><td>TM, JO</td><td>× √</td><td>2n(n -1) 3n(n-1)</td></tr><tr><td>JK, MM TJJ, JJM</td><td>√</td><td>n(n -1)(n- 2)</td></tr><tr><td>JJJJ</td><td>√</td><td>n(n-1)(n-2)(n-3)</td></tr><tr><td>I(TJ),I(JM)</td><td>×</td><td>2n(n -1)</td></tr><tr><td>I(JJJ)</td><td>×</td><td>n(n-1)(n-2)</td></tr><tr><td>II(JJ)</td><td>√</td><td>n(n-1)</td></tr><tr><td></td><td></td><td></td></tr></table></body></html>

with the definitions $\begin{array} { r } { s _ { j _ { 1 } j _ { 2 } } \equiv \sin \frac { ( j _ { 1 } - j _ { 2 } ) \pi } { n } } \end{array}$ ， $\begin{array} { r } { c _ { j _ { 1 } j _ { 2 } } \equiv \cos \frac { ( j _ { 1 } - j _ { 2 } ) \pi } { n } } \end{array}$ ，and the ones similar to them.Considering the relevant operators in table $^ { 1 }$ and table 2,we get the Rényi mutual information organized by the large central charge

$$
I _ { n } ^ { ( 0 , 1 ) } = I _ { n } ^ { \mathrm { L } } + I _ { n , ( 0 , 1 ) } ^ { \mathrm { N L } } + \cdot \cdot \cdot .
$$

Here the leading part $I _ { n } ^ { \mathrm { L } }$ equals $I _ { n } ^ { \mathrm { c l } }$ (2.1) and the next-to-leading part

$$
I _ { n , ( 0 , 1 ) } ^ { \mathrm { N L } } = I _ { n , g } ^ { \mathrm { 1 - l o o p } } + I _ { n , v } ^ { \mathrm { 1 - l o o p } } ,
$$

with $I _ { n , g } ^ { \mathrm { 1 - l o o p } }$ being (2.2） and $I _ { n , v } ^ { \mathrm { 1 - l o o p } }$ being (2.3).

# 2.4 Contributions of $T$ ， $J$ ， $G$ and $H$ in SCFT

By further adding the contributions of $G$ and $H$ ，we have to consider the extra quasiprimary operators that are counted as

$$
\stackrel { \wedge } { \langle { 0 } \rangle } \chi _ { ( 1 ) } ^ { n } ( \chi _ { ( 3 / 2 ) } ^ { n } - 1 ) = 2 n x ^ { 3 / 2 } + 2 n ^ { 2 } x ^ { 5 / 2 } + n ( 2 n - 1 ) x ^ { 3 } + n ^ { 2 } ( n + 5 ) x ^ { 7 / 2 } + n ( 2 n ^ { 2 } + n + 1 ) x ^ { 4 } + O ( x ^ { 9 / 2 } ) ,
$$

with $\chi _ { ( 0 ) }$ being (A.1), $\chi _ { ( 1 ) }$ being (A.6） and $\chi ( 3 / 2 )$ being (A.15),and they are listed in table 3. For the relevant operators we have the normalization factors

$$
\alpha _ { G G } = \alpha _ { H H } = - \frac { 1 6 c ^ { 2 } } { 9 } , \alpha _ { J G H } = \frac { 1 6 c ^ { 3 } } { 2 7 } , \alpha _ { I ( G G ) } = \alpha _ { I ( H H ) } = - \frac { 3 2 c ^ { 2 } } { 3 } ,
$$

and the OPE coefficients

$$
d _ { G G } ^ { j _ { 1 } j _ { 2 } } = - d _ { H H } ^ { j _ { 1 } j _ { 2 } } = - \frac { 3 \mathrm { i } } { 3 2 n ^ { 3 } c } \frac { 1 } { s _ { 1 } ^ { 3 } j _ { 2 } } , d _ { J G H } ^ { j _ { 1 } j _ { 2 } j _ { 3 } } = - \frac { 9 } { 6 4 n ^ { 4 } c ^ { 2 } } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } s _ { j _ { 1 } j _ { 3 } } s _ { j _ { 2 } j _ { 3 } } ^ { 2 } } , d _ { I ( G G ) } ^ { j _ { 1 } j _ { 2 } } = - d _ { I ( H H ) } ^ { j _ { 1 } j _ { 2 } } = - \frac { 3 \mathrm { i } } { 6 4 n ^ { 4 } c } \frac { c } { s _ { 1 } ^ { 4 } }
$$

<html><body><table><tr><td>level</td><td>operators</td><td>？</td><td>degeneracy</td><td>number</td></tr><tr><td>32</td><td>G,H</td><td>×</td><td>2n</td><td>2n</td></tr><tr><td rowspan="2">52</td><td>D1，D2</td><td>×</td><td>2n</td><td rowspan="2">2n²</td></tr><tr><td>JG,JH</td><td>×</td><td>2n(n -1)</td></tr><tr><td rowspan="3">3</td><td></td><td>×</td><td>n</td><td rowspan="3">n(2n - 1)</td></tr><tr><td>GH</td><td>×</td><td>n(n-1)</td></tr><tr><td>GG，HH</td><td>√</td><td>n(n-1)</td></tr><tr><td rowspan="4">72</td><td>B, C,F1,F2,F3, F4</td><td>×</td><td>6n</td><td rowspan="4">n²(n +5)</td></tr><tr><td>MG,TH,MG2</td><td>×</td><td>6n(n -1)</td></tr><tr><td>JJG，JJH</td><td>×</td><td>n(n -1)(n -2)</td></tr><tr><td>I(JG)，I(JH)</td><td>×</td><td>2n(n -1)</td></tr><tr><td rowspan="6">4</td><td>I1,I2,I3,I4</td><td>×</td><td>4n</td><td rowspan="6">n(2n² +n +1)</td></tr><tr><td>Jε,GD1, GD2 HDi，HD2</td><td></td><td> 5n(n - 1)</td></tr><tr><td>JGH</td><td>√</td><td>n(n - 1)(n - 2)</td></tr><tr><td>JGG，JHH</td><td>×</td><td>n(n -1)(n -2)</td></tr><tr><td>I(GH)</td><td>×</td><td>n(n -1)</td></tr><tr><td>I(GG)，I(HH)</td><td>√</td><td>n(n-1)</td></tr></table></body></html>

Table 3: Extra holomorphic quasiprimary operators in SCFT $^ { 1 \prime \mathit { n } }$ after further adding contributions of $G$ and $H$ The 5th column agrees with the counting in (2.15).

Considering the relevant operators in table 1,table 2,and table 3,we get the Rényi mutual information

$$
I _ { n } ^ { ( 0 , 1 , 3 / 2 ) } = I _ { n } ^ { \mathrm { L } } + I _ { n , ( 0 , 1 , 3 / 2 ) } ^ { \mathrm { N L } } + I _ { n , ( 0 , 1 , 3 / 2 ) } ^ { \mathrm { N N L } } \cdot \cdot \cdot .
$$

Here the leading part $I _ { n } ^ { \mathrm { L } }$ equals $I _ { n } ^ { \mathrm { c l } }$ (2.1),the next-to-leading part

$$
I _ { n , ( 0 , 1 , 3 / 2 ) } ^ { \mathrm { N L } } = I _ { n , g } ^ { \mathrm { 1 - l o o p } } + I _ { n , v } ^ { \mathrm { 1 - l o o p } } + I _ { n , \psi } ^ { \mathrm { 1 - l o o p } } ,
$$

with $I _ { n , g } ^ { \mathrm { 1 - l o o p } }$ being (2.2), $I _ { n , v } ^ { \mathrm { 1 - l o o p } }$ being (2.3), and $I _ { n , v } ^ { \mathrm { 1 - l o o p } }$ being (2.4),and the next-to-next-to-leading part is

$$
I _ { n , ( 0 , 1 , 3 / 2 ) } ^ { \mathrm { N N L } } = \frac { ( n + 1 ) ( n ^ { 2 } - 4 ) ( n ^ { 4 } + 4 0 n ^ { 2 } + 6 7 9 ) x ^ { 4 } } { 3 0 2 4 0 0 c n ^ { 7 } } + O ( x ^ { 5 } ) .
$$

# 3 Rényi entropy of one interval on torus

In this section we investigate the Rényi entropy of one length $\ell$ interval on a torus with low temperature. The SCFT on torus is just the theory on a circle in thermal state. We expand the Rényi entropy by $q = \exp ( - 2 \pi \beta / L )$ with $\beta$ being the inverse temperature and $L$ being the spatial period, to order $q ^ { 2 }$ . In supergravity side we use the method in [15,25],and in SCFT side we use the method in [24,25].

# 3.1 Supergravity result

The classical part of holographic Rényi entropy is [15,25]

$$
S _ { n } ^ { \mathrm { c l } } = \frac { c ( n + 1 ) } { 6 n } \log \Big ( \frac { L } { \pi \epsilon } \sin \frac { \pi \ell } { L } \Big ) - \Big ( \frac { c ( n - 1 ) ( n + 1 ) ^ { 2 } } { 9 n ^ { 3 } } \sin ^ { 4 } \frac { \pi \ell } { L } \Big ) q ^ { 2 } + O ( q ^ { 3 } ) .
$$

The one-loop correction to holographic Rényi entropy from graviton is [15]

$$
S _ { n , g } ^ { \mathrm { 1 - l o o p } } = - \frac { 2 n } { n - 1 } \bigg ( \frac { 1 } { n ^ { 4 } } \frac { \sin ^ { 4 } \frac { \pi \ell } { L } } { \sin ^ { 4 } \frac { \pi \ell } { n L } } - 1 \bigg ) q ^ { 2 } + O ( q ^ { 3 } ) .
$$

For the vector feld we get

$$
\begin{array} { c } { \displaystyle _ { \nu = 0 } ^ { \mathrm { ~ \tiny ~ \underline { ~ } { ~ l o o p } ~ } } = - \frac { 2 n } { n - 1 } \bigg \{ \bigg ( \frac { 1 } { n ^ { 2 } } \frac { \sin ^ { 2 } \frac { \pi \ell } { L } } { \sin ^ { 2 } \frac { \pi \ell } { n L } } - 1 \bigg ) q + \bigg [ \frac { 2 \sin ^ { 2 } \frac { \pi \ell } { L } } { n ^ { 4 } \sin ^ { 2 } \frac { \pi \ell } { n L } } \bigg ( n ^ { 2 } \cos ^ { 2 } \frac { \pi \ell } { L } - n \sin \frac { 2 \pi \ell } { L } \cot \frac { \pi \ell } { n L } } \\ { + \frac { \sin ^ { 2 } \frac { \pi \ell } { L } } { \sin ^ { 2 } \frac { \pi \ell } { n L } } \Big ( \cos ^ { 2 } \frac { \pi \ell } { n L } + \frac { 3 } { 4 } \Big ) \bigg ) + \frac { \sin ^ { 4 } \frac { \pi \ell } { L } } { 2 n ^ { 4 } } \sum _ { j = 1 } ^ { n - 1 } \bigg ( \frac { 1 } { \big ( \sin ^ { 2 } \frac { \pi j } { n } - \sin ^ { 2 } \frac { \pi \ell } { n L } \big ) ^ { 2 } } + \frac { 1 } { \sin ^ { 4 } \frac { \pi \ j } { n } } \bigg ) - \frac { 3 } { 2 } \bigg ] q ^ { 2 } + O ( q ^ { 4 } ) } \end{array}
$$

For the two gravitinos we get

$$
S _ { n , \psi } ^ { \mathrm { 1 - l o o p } } = - \frac { 4 n } { n - 1 } \bigg ( \frac { 1 } { n ^ { 3 } } \frac { \sin ^ { 3 } \frac { \pi \ell } { L } } { \sin ^ { 3 } \frac { \pi \ell } { n L } } - 1 \bigg ) q ^ { 3 / 2 } + O ( q ^ { 5 / 2 } ) .
$$

# 3.2 Contributions of $T$ in SCFT

In this subsection we consider the contributions of only the vacuum conformal family and repeat the calculation in [24,25]. One has the density matrix in expansion of low temperature

$$
\rho _ { \mathrm { v a c } } = | 0 \rangle \langle 0 | + \frac { q ^ { 2 } } { \alpha _ { T } } | T \rangle \langle T | + O ( q ^ { 3 } ) .
$$

Denoting the interval by $A$ and its complement by $B$ , one gets the Rényi entropy

$$
S _ { n } ^ { ( 0 ) } = - \frac { 1 } { n - 1 } \log \mathrm { t r } _ { A } \big ( \mathrm { t r } _ { B } | 0 \rangle \langle 0 | \big ) ^ { n } - \frac { 2 n } { n - 1 } \Bigg ( \frac { \mathrm { t r } _ { A } \big [ \mathrm { t r } _ { B } | T \rangle \langle T | \big ( \mathrm { t r } _ { B } | 0 \rangle \langle 0 | \big ) ^ { n - 1 } \big ] } { \alpha _ { T } \mathrm { t r } _ { A } \big ( \mathrm { t r } _ { B } | 0 \rangle \langle 0 | \big ) ^ { n } } - 1 \Bigg ) q ^ { 2 } + { \cal O } ( q ^ { 3 } ) .
$$

From the state operator correspondence one has

$$
\frac { \mathrm { t r } _ { A } \left[ \mathrm { t r } _ { B } | T \rangle \langle T | ( \mathrm { t r } _ { B } | 0 \rangle \langle 0 | ) ^ { n - 1 } \right] } { \alpha _ { T } \mathrm { t r } _ { A } \left( \mathrm { t r } _ { B } | 0 \rangle \langle 0 | \right) ^ { n } } = \frac { \langle T ( \infty ) T ( 0 ) \rangle \mathcal { C } ^ { n } } { \alpha _ { T } } .
$$

The $n$ -fold complex plane ${ \mathcal { C } } ^ { n }$ with coordinate $z$ can be mapped to a complex plane $\boldsymbol { \mathscr { C } }$ with coordinate $f$ by the conformal transformation

$$
f ( z ) = \left( \frac { z - \mathrm { e } ^ { \mathrm { i } \pi \ell / L } } { z - \mathrm { e } ^ { - \mathrm { i } \pi \ell / L } } \right) ^ { 1 / n } .
$$

Then one gets

$$
\frac { \langle T ( \infty ) T ( 0 ) \rangle _ { \mathcal { C } ^ { n } } } { \alpha _ { T } } = \frac { c ( n ^ { 2 } - 1 ) ^ { 2 } } { 1 8 n ^ { 4 } } \sin ^ { 4 } \frac { \pi \ell } { L } + \frac { 1 } { n ^ { 4 } } \frac { \sin ^ { 4 } \frac { \pi \ell } { L } } { \sin ^ { 4 } \frac { \pi \ell } { n L } } .
$$

The Rényi entropy can be organized by large central charge as

$$
S _ { n } ^ { ( 0 ) } = S _ { n , ( 0 ) } ^ { \mathrm { L } } + S _ { n , ( 0 ) } ^ { \mathrm { N L } } + \cdots ,
$$

with the leading part Sn,(0) equaling Snl (3.1) and the next-to-leading part Sn(o) equaling $S _ { n , g } ^ { \mathrm { 1 - l o o p } }$ (3.2).

# 3.3 Contributions of $J$ in SCFT

Adding the contributions of $J$ , we have to add the density matrix (3.5) by

$$
\rho _ { J } = \frac { q } { \alpha _ { J } } | J \rangle \langle J | + \frac { q ^ { 2 } } { \alpha _ { \mathcal { M } } } | \mathcal { M } \rangle \langle \mathcal { M } | + \frac { q ^ { 2 } } { \alpha _ { \partial J } } | \partial J \rangle \langle \partial J | + O ( q ^ { 3 } ) .
$$

We get the extra contributions of $J$ to the Rényi entropy

$$
\begin{array} { c } { { S _ { n } ^ { ( 1 ) } = - \displaystyle \frac { 2 n } { n - 1 } \bigg \{ \bigg ( \displaystyle \frac { \langle J ( \infty ) J ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { J } } - 1 \bigg ) q + \displaystyle [ \frac { \langle M ( \infty ) { \mathcal M } ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { \mathcal M } } + \frac { \langle \partial J ( \infty ) \partial J ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { \partial J } }  } } \\ { { \displaystyle  \qquad - \frac { n } { 2 } \bigg ( \displaystyle \frac { \langle J ( \infty ) J ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { J } } \bigg ) ^ { 2 } + \frac { 1 } { 2 } \sum _ { j = 1 } ^ { n - 1 } \frac { \langle J ( \infty ) J ( 0 ) J ( \infty _ { j } ) J ( 0 _ { j } ) \rangle _ { C ^ { n } } } { \alpha _ { J } ^ { 2 } } - \frac { 3 } { 2 } \bigg ] q ^ { 2 } + { \mathcal O } ( q ^ { 3 } ) \bigg \} . } } \end{array}
$$

With some calculation we get

$$
\begin{array} { r l } & { \frac { \langle J ( \infty ) J ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { J } } = \frac { 1 } { n ^ { 2 } } \frac { \sin ^ { 2 } \frac { \pi \ell } { L } } { \sin ^ { 2 } \frac { \pi \ell } { n L } } , \frac { \langle \mathcal { M } ( \infty ) \mathcal { M } ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { \mathcal { M } } } = \frac { 1 } { n ^ { 4 } } \frac { \sin ^ { 4 } \frac { \pi \ell } { L } } { \sin ^ { 4 } \frac { \pi \ell } { n L } } , } \\ & { \frac { \langle \partial J ( \infty ) \partial J ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { \partial J } } = \frac { 2 } { n ^ { 4 } } \frac { \sin ^ { 2 } \frac { \pi \ell } { L } } { \sin ^ { 2 } \frac { \pi \ell } { n L } } \Big ( n ^ { 2 } \cos ^ { 2 } \frac { \pi \ell } { L } - n \sin \frac { 2 \pi \ell } { L } \cot \frac { \pi \ell } { n L } + \frac { \sin ^ { 2 } \frac { \pi \ell } { L } } { \sin ^ { 2 } \frac { \pi \ell } { n L } } \Big ( \cos ^ { 2 } \frac { \pi \ell } { n L } + \frac { 1 } { 2 } \Big ) \Big ) , } \\ & { \frac { \langle J ( \infty ) J ( 0 ) J ( \infty _ { j } ) J ( 0 _ { j } ) \rangle _ { C ^ { n } } } { \alpha _ { J } ^ { 2 } } = \frac { \sin ^ { 4 } \frac { \pi \ell } { L } } { n ^ { 4 } } \Big ( \frac { 1 } { \big ( \sin ^ { 2 } \frac { \pi j } { n } - \sin ^ { 2 } \frac { \pi \ell } { n L } \big ) ^ { 2 } } + \frac { 1 } { \sin ^ { 4 } \frac { \pi j } { n } } + \frac { 1 } { \sin ^ { 4 } \frac { \pi \ell } { n L } } \Big ) . } \end{array}
$$

Then we reproduce the one-loop gravity result $S _ { n , v } ^ { \mathrm { 1 - l o o p } }$ (3.3).

# 3.4 Contributions of $G$ and $H$ in SCFT

Adding further the contributions of $G$ and $H$ , we need to add the density matrix (3.5) with (3.11) and

$$
\rho _ { G , H } = \frac { q ^ { 3 / 2 } } { \alpha _ { G } } | G \rangle \langle G | + \frac { q ^ { 3 / 2 } } { \alpha _ { H } } | H \rangle \langle H | + O ( q ^ { 5 / 2 } ) .
$$

We get the extra contribution for Rényi entropy from $G$ and $H$

$$
S _ { n } ^ { ( 3 / 2 ) } = - \frac { 2 n } { n - 1 } \bigg ( \frac { \langle G ( \infty ) G ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { G } } + \frac { \langle H ( \infty ) H ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { H } } - 2 \bigg ) q ^ { 3 / 2 } + O ( q ^ { 5 / 2 } ) .
$$

With the correlation functions

$$
{ \frac { \langle G ( \infty ) G ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { G } } } = { \frac { \langle H ( \infty ) H ( 0 ) \rangle _ { C ^ { n } } } { \alpha _ { H } } } = { \frac { 1 } { n ^ { 3 } } } { \frac { \sin ^ { 3 } { \frac { \pi \ell } { L } } } { \sin ^ { 3 } { \frac { \pi \ell } { n L } } } } ,
$$

wereproduce theogravityesult $S _ { n , \psi } ^ { \mathrm { 1 - l o o p } }$ (3.4).

# 4Conclusion and discussion

In this paper,we have investigated the holographic Rényi entropy in the correspondence of ${ \mathcal N } = 2$ supergravity under AdS $^ 3$ background and two-dimensional $\mathcal { N } = ( 2 , 2 )$ SCFT.For two short intervals on complex plane with small cross ratio $x \ll 1$ we got the Rényi mutual information to order $x ^ { 4 }$ ,and for one interval on torus with low temperature $q = \mathrm { e } ^ { - 2 \pi \beta / L } \ll 1$ we got the Rényi entropy to order $q ^ { 2 }$ ：

Such orders are lower than the previous results in literature,for examples,order $x ^ { \mathrm { s } }$ for complex plane case in [20] and order $q ^ { 4 }$ for torus case in [28]. This is because in the present case we have the spin-1 feld in supergravity side and the current with conformal weight 1 in SCFT side. The smallspin in supergravityand small conformal weight in SCFT make thecalculation to higher orders more complicated.To get higher order results in supergravity side we need to consider the contributions of $m$ -CDW's for the complex plane case and the $m$ -letter words in the torus case with $m \geq 3$ .In SCFT side the number of degenerate quasiprimary operators would increase very quickly in higher levels,and the orthogonalization of these primary and quasiprimary operators would be very complicated.Although much more complicated,it would be nice if higher order results can be got in the future,and perhaps more effective method has to be developed.

# Acknowledgements

The authors would like to thank Jun-Bao Wu and Hao Ouyang for valuable discussions and suggestions.And also we special thank Matthew Headrick for his Mathematica code Virasoro.nb which could be downloaded at the personal homepage http://people.brandeis.edu/\~headrick/Mathematica/index.html. ZL was supported by NSFC Grant No. 11222549 and No.11575202.

# A Review of two-dimensional $\mathcal { N }$ =(2,2) SCFT

In this appendix we review some useful properties of the $\mathcal { N } = ( 2 , 2 )$ SCFT. More details can be found in [38].

In the $\mathcal { N } = ( 2 , 2 )$ SCFT, we have the stress tensor $T ( z ) , T ( \bar { z } )$ , the current $J ( z )$ ， $J ( \bar { z } )$ , and their supersymmetric partners $G ( z )$ ， $G ( \bar { z } )$ ， $H ( z )$ ， $H ( \bar { z } )$ , as well as the operators that are constructed from them. These operators can be written as the products of the holomorphic ones and the anti-holomorphic ones,and there is one-to-one correspondence between the holomorphic and anti-holomorphic operators.So in this paper we only need to consider the holomorphic sector of the SCFT.

With only $T$ ,we get the character of the vacuum conformal family

$$
\chi _ { ( 0 ) } = \prod _ { k = 0 } ^ { \infty } { \frac { 1 } { 1 - x ^ { k + 2 } } } .
$$

The modes of $T$ are denoted by $L _ { m }$ with $m \in \mathrm { Z }$ ,and they form the Virasoro algebra

$$
\left[ L _ { m } , L _ { n } \right] = ( m - n ) L _ { m + n } + \frac { c } { 1 2 } ( m ^ { 3 } - m ) \delta _ { m + n } .
$$

The primary operator of the vacuum conformal family is the identity operator.At level 2 we have $T$ with normalization factor $\begin{array} { r } { \alpha _ { T } = \frac { c } { 2 } } \end{array}$ ,and at level 4 we have quasiprimary operator

$$
\mathcal { A } = ( T T ) - \frac { 3 } { 1 0 } \partial ^ { 2 } T , \alpha _ { \mathcal { A } } = \frac { c ( 5 c + 2 2 ) } { 1 0 } .
$$

Here we use the bracket ‘ $( ) ^ { \dag }$ to denote normal ordering. Under a general conformal transformation $z  f ( z )$ ， they transform as

$$
T ( z ) = f ^ { \prime 2 } T ( f ) + \frac { c } { 1 2 } s , { \cal A } ( z ) = f ^ { \prime 4 } { \cal A } ( f ) + \frac { 5 c + 2 2 } { 3 0 } s \Big ( f ^ { \prime 2 } T ( f ) + \frac { c } { 2 4 } s \Big ) ,
$$

with the Schwarzian derivative being

$$
s ( z ) = { \frac { f ^ { \prime \prime \prime } ( z ) } { f ^ { \prime } ( z ) } } - { \frac { 3 } { 2 } } \biggl ( { \frac { f ^ { \prime \prime } ( z ) } { f ^ { \prime } ( z ) } } \biggr ) ^ { 2 } .
$$

By adding the current operator $J$ with conformal weights $( 1 , 0 )$ we get the bosonic part of the SCFT1,and we have to multiply the character (A.1） by

$$
\chi _ { ( 1 ) } = \prod _ { k = 0 } ^ { \infty } { \frac { 1 } { 1 - x ^ { k + 1 } } } .
$$

The Virasoro algebra (A.2) is supplemented by

$$
\left[ L _ { m } , J _ { n } \right] = - n J _ { m + n } , \left[ J _ { m } , J _ { n } \right] = \frac { c } { 3 } m \delta _ { m + n } .
$$

<html><body><table><tr><td>level</td><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td>J</td><td>J</td><td></td><td>K</td><td>L</td></tr><tr><td>M</td><td></td><td>M</td><td></td><td></td></tr><tr><td>O</td><td></td><td></td><td>0</td><td></td></tr><tr><td>P1,P2</td><td></td><td></td><td></td><td>P1,P2</td></tr></table></body></html>

Table 4: Up to level 4 the extra quasiprimary operators because of the adding of $J$ . In the first column we list the primary operator of each conformal family.

Note that the algebra of SCFT bosonic part is close and self-consistent.Besides the ones in vacuum conformal block, there are other quasiprimary operators that can be counted as

$$
( 1 - x ) \chi _ { ( 0 ) } ( \chi _ { ( 1 ) } - 1 ) = x + x ^ { 2 } + 2 x ^ { 3 } + 4 x ^ { 4 } + O ( x ^ { 5 } ) .
$$

Among these quasiprimary operators, the primary ones can be counted as

$$
{ \frac { \chi _ { ( 0 ) } ( \chi _ { ( 1 ) } - 1 ) } { \chi } } = x + x ^ { 2 } + x ^ { 3 } + 2 x ^ { 4 } + O ( x ^ { 5 } ) , ~ \chi \equiv \prod _ { k = 1 } ^ { \infty } { \frac { 1 } { 1 - x ^ { k } } } .
$$

These primary and quasiprimary operators are listed in table 4. For the primary operator $J$ we have the normalization $\begin{array} { r } { \alpha _ { J } = \frac { c } { 3 } } \end{array}$ , for quasiprimary operator $\mathcal { K }$ we have

$$
\mathcal { K } = ( T J ) - \frac { 1 } { 2 } \partial ^ { 2 } J , \alpha _ { \mathcal { K } } = \frac { c ( c + 2 ) } { 6 } ,
$$

and for primary operator $\mathcal { M }$ we have

$$
\mathcal { M } = ( J J ) - \frac { 2 } { 3 } T , \alpha _ { \mathcal { M } } = \frac { 2 c ( c - 1 ) } { 9 } .
$$

Under a conformal transformation $z  f ( z )$ we have

$$
J ( z ) = f ^ { \prime } J ( f ) , \ : \ : \ : { \mathcal { K } } ( z ) = f ^ { \prime 3 } { \mathcal { K } } ( f ) + { \frac { c + 2 } { 1 2 } } s f ^ { \prime } J ( f ) .
$$

In this paper we need the structure constants

$$
C _ { J J J } = 0 , C _ { T J J } = \frac { c } { 3 } , C _ { J J \mathcal { M } } = \frac { 2 c ( c - 1 ) } { 9 } ,
$$

as well as the four-point function on complex plane

$$
\langle J ( z _ { 1 } ) J ( z _ { 2 } ) J ( z _ { 3 } ) J ( z _ { 4 } ) \rangle _ { \mathcal { C } } = \frac { c ^ { 2 } } { 9 } \Bigl ( \frac { 1 } { z _ { 1 2 } ^ { 2 } z _ { 3 4 } ^ { 2 } } + \frac { 1 } { z _ { 1 3 } ^ { 2 } z _ { 2 4 } ^ { 2 } } + \frac { 1 } { z _ { 1 4 } ^ { 2 } z _ { 2 3 } ^ { 2 } } \Bigr ) ,
$$

with the shorthand zjk = zj - zk·

By further adding the fermionic operators $G$ and $H$ with conformal weights $( 3 / 2 , 0 )$ ，we get the SCFT and the character is the product of (A.1),(A.6) and

$$
\chi _ { ( 3 / 2 ) } = \prod _ { k = 0 } ^ { \infty } \left( 1 + x ^ { k + 3 / 2 } \right) ^ { 2 } .
$$

Note that there are two primary operators at level $3 / 2$ and so there is a power 2 in the right-hand side of the above equation.Asargued in [30],in large centralcharge limit we only need to consider the Neveu-Schwarz

Table 5: The extra primary and quasiprimary operators because of the adding of $G$ and $H$   

<html><body><table><tr><td>level</td><td>3/2</td><td>5/2</td><td>3</td><td>7/2</td><td>4</td></tr><tr><td>G</td><td>G</td><td></td><td></td><td>B</td><td></td></tr><tr><td>H</td><td>H</td><td></td><td></td><td>C</td><td></td></tr><tr><td>D1,D2</td><td></td><td>D1,D2</td><td></td><td></td><td></td></tr><tr><td>8</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>F1,F2,F,F4</td><td></td><td></td><td></td><td>F1,F2,F,F4</td><td></td></tr><tr><td>I1,I2,I3,I4</td><td></td><td></td><td></td><td></td><td>I1,I2,I3,I4</td></tr></table></body></html>

sector for the fermionic operators. We have the modes $G _ { r } , H _ { s }$ with $r , s \in \mathrm { Z } + 1 / 2$ ，and to compose the ${ \mathcal N } = 2$ （20 super Virasoro algebra we need (A.2), (A.7), and

$$
\begin{array} { l } { { \displaystyle \left[ L _ { m } , G _ { r } \right] = ( \frac { m } { 2 } - r ) G _ { m + r } , ~ \left[ L _ { m } , H _ { r } \right] = ( \frac { m } { 2 } - r ) H _ { m + r } , } } \\ { { \displaystyle \left[ J _ { m } , G _ { r } \right] = H _ { m + r } , ~ \left[ J _ { m } , H _ { r } \right] = G _ { m + r } , ~ \left\{ G _ { r } , H _ { s } \right\} = - 2 ( r - s ) J _ { r + s } , } } \\ { { \displaystyle \left\{ G _ { r } , G _ { s } \right\} = 4 L _ { r + s } + \frac { 2 c } { 3 } ( r ^ { 2 } - \frac { 1 } { 4 } ) \delta _ { r + s } , ~ \left\{ H _ { r } , H _ { s } \right\} = - 4 L _ { r + s } - \frac { 2 c } { 3 } ( r ^ { 2 } - \frac { 1 } { 4 } ) \delta _ { r + s } . } } \end{array}
$$

The extra quasiprimary operators can be counted as

$$
( 1 - x ) \chi _ { ( 0 ) } \chi _ { ( 1 ) } \big ( \chi _ { ( 3 / 2 ) } - 1 \big ) = 2 x ^ { 3 / 2 } + 2 x ^ { 5 / 2 } + x ^ { 3 } + 6 x ^ { 7 / 2 } + 4 x ^ { 4 } + O \big ( x ^ { 9 / 2 } \big ) ,
$$

among which the primary ones can be counted as

$$
{ \frac { \chi _ { ( 0 ) } \chi _ { ( 1 ) } { \big ( } \chi _ { ( 3 / 2 ) } - 1 { \big ) } } { \chi } } = 2 x ^ { 3 / 2 } + 2 x ^ { 5 / 2 } + x ^ { 3 } + 4 x ^ { 7 / 2 } + 4 x ^ { 4 } + O ( x ^ { 9 / 2 } ) .
$$

These operators are listed in table 5.For $G$ and $H$ we have normalization constants $\begin{array} { r } { \alpha _ { G } = - \alpha _ { H } = \frac { 4 c } { 3 } } \end{array}$ ,and under conformal transformation they transform as

$$
G ( z ) = f ^ { \prime \frac { 3 } { 2 } } G ( f ) , H ( z ) = f ^ { \prime \frac { 3 } { 2 } } H ( f ) .
$$

There are useful structure constants

$$
C _ { J J G } = C _ { J J H } = C _ { J G G } = C _ { J H H } = 0 , C _ { J G H } = - \frac { 4 c } { 3 } .
$$

# BSome useful summation formulas

In this appendix we collect some summation formulas that are useful to calculation in sction 2.We define

$$
f _ { m } = \sum _ { j = 1 } ^ { n - 1 } { \frac { 1 } { \left( \sin { \frac { \pi j } { n } } \right) ^ { 2 m } } } ,
$$

and we need

$$
{ \begin{array} { r l } & { f _ { 2 } = { \frac { \left( n ^ { 2 } - 1 \right) \left( n ^ { 2 } + 1 1 \right) } { 4 5 } } , \quad f _ { 3 } = { \frac { \left( n ^ { 2 } - 1 \right) \left( 2 n ^ { 4 } + 2 3 n ^ { 2 } + 1 9 1 \right) } { 9 4 5 } } , } \\ & { f _ { 4 } = { \frac { \left( n ^ { 2 } - 1 \right) \left( n ^ { 2 } + 1 1 \right) \left( 3 n ^ { 4 } + 1 0 n ^ { 2 } + 2 2 7 \right) } { 1 4 1 7 5 } } . } \end{array} }
$$

Wehave

$$
\begin{array} { l } { { \displaystyle \sum _ { \vec { \varphi } } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 4 } s _ { j _ { 1 } j _ { 3 } } ^ { 4 } } = \frac { 4 n ( n ^ { 2 } - 1 ) ( n ^ { 2 } - 4 ) ( n ^ { 2 } + 1 1 ) ( n ^ { 2 } + 1 9 ) } { 1 4 1 7 5 } , } }  \\ { { \displaystyle \sum _ { \vec { \varphi } } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 2 } s _ { j _ { 1 } j _ { 3 } } ^ { 2 } s _ { j _ { 2 } j _ { 3 } } ^ { 2 } } = \frac { 2 n ( n ^ { 2 } - 1 ) ( n ^ { 2 } - 4 ) ( n ^ { 2 } + 4 7 ) } { 9 4 5 } , } } \\ { { \displaystyle \sum _ { \vec { \varphi } } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 2 } s _ { j _ { 1 } j _ { 3 } } ^ { 2 } s _ { j _ { 2 } j _ { 3 } } ^ { 4 } } = \frac { 2 n ( n ^ { 2 } - 1 ) ( n ^ { 2 } - 4 ) ( n ^ { 4 } + 4 0 n ^ { 2 } + 6 7 9 ) } { 1 4 1 7 5 } , } } \end{array}
$$

with definition $\begin{array} { r } { s _ { j _ { 1 } j _ { 2 } } \equiv \sin \frac { \pi ( j _ { 1 } - j _ { 2 } ) } { n } } \end{array}$ and the ones similar to it,and the summation is over $0 \leq j _ { 1 , 2 , 3 } \leq n - 1$ with constraints $j _ { 1 } \neq j _ { 2 }$ ， $j _ { 1 } \neq j _ { 3 }$ ， $j _ { 2 } \neq j _ { 3 }$ . We have

$$
\begin{array} { l } { { \displaystyle \sum _ { \vec { \tau } } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 4 } s _ { j _ { 3 } j _ { 4 } } ^ { 4 } } = \frac { n ( n ^ { 2 } - 1 ) ( n - 2 ) ( n - 3 ) ( n ^ { 2 } + 1 1 ) ( 7 n ^ { 3 } + 1 3 n ^ { 2 } + 9 3 n + 1 2 7 ) } { 1 4 1 7 5 } , } } \\ { { \displaystyle \sum _ { \vec { \tau } } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 2 } s _ { j _ { 3 } j _ { 4 } } ^ { 2 } s _ { j _ { 1 } j _ { 3 } } ^ { 2 } s _ { j _ { 2 } j _ { 4 } } ^ { 2 } } = \frac { 4 n ( n ^ { 2 } - 1 ) ( n ^ { 2 } - 4 ) ( n ^ { 2 } - 9 ) ( n ^ { 2 } + 1 1 9 ) } { 1 4 1 7 5 } , } } \end{array}
$$

with the summation being over $0 \leq j _ { 1 , 2 , 3 , 4 } \leq n - 1$ and the constraints being $j _ { 1 } \neq j _ { 2 }$ ， $j _ { 1 } \neq j _ { 3 }$ ， $j _ { 1 } \neq j _ { 4 }$ ， $j _ { 2 } \neq j _ { 3 }$ ， $j _ { 2 } \neq j _ { 4 }$ ， $j _ { 3 } \neq j _ { 4 }$ . Finally we have

$$
\sum ^ { \prime } \frac { 1 } { s _ { j _ { 1 } j _ { 2 } } ^ { 2 } s _ { j _ { 2 } j _ { 3 } } ^ { 2 } s _ { j _ { 3 } j _ { 4 } } ^ { 2 } s _ { j _ { 4 } j _ { 1 } } ^ { 2 } } = \frac { 4 n ( n ^ { 2 } - 1 ) ( n ^ { 2 } - 4 ) ( 3 n ^ { 4 } + 1 7 0 n ^ { 2 } - 6 5 3 ) } { 1 4 1 7 5 } ,
$$

with the summation being over $0 \leq j _ { 1 , 2 , 3 , 4 } \leq n - 1$ and the constraints being

$$
\neq j _ { 2 } , \ j _ { 2 } \neq j _ { 3 } , \ j _ { 3 } \neq j _ { 4 } , \ j _ { 4 } \neq j _ { 1 } , \ ( j _ { 1 } , j _ { 2 } ) \neq ( j _ { 3 } , j _ { 4 } )
$$

# References

[1] S. Ryu and T. Takayanagi,“Holographic derivation of entanglement entropy from AdS/CFT," Phys.Rev.Lett.96 (2006) 181602,arXiv:hep-th/0603001 [hep-th].   
[2] S.Ryu and T. Takayanagi,“Aspects of Holographic Entanglement Entropy,” JHEP O608 (2006) 045, arXiv:hep-th/0605073 [hep-th].   
[3] J. M. Maldacena,“The Large N limit of superconformal field theories and supergravity,” Int. J. Theor. Phys.38 (1999)113-1133,arXiv:hep-th/9711200 [hep-th].[Adv.Theor.Math. Phys. 2, (1998) 231].   
[4]S.Gubser,I.R.Klebanov,and A.M.Polyakov,“Gauge theory correlators from noncritical string theory,” Phys.Lett.B428 (1998)105-114, arXiv:hep-th/9802109 [hep-th].   
[5] E.Witten,“Anti-de Sitter space and holography,” Adv. Theor. Math. Phys. 2 (1998) 253-291, arXiv:hep-th/9802150 [hep-th].   
[6] O.Aharony,S. S. Gubser, J. M. Maldacena, H. Ooguri,and Y. Oz,“Large N feld theories, string theory and gravity,” Phys.Rept.323 (2000) 183-386,arXiv:hep-th/9905111 [hep-th].   
[7] C.G. Callan Jr.and F. Wilczek,“On geometric entropy,” Phys. Lett. B333 (1994) 55-61, arXiv:hep-th/9401072 [hep-th]. [8] C.Holzhey,F.Larsen,andF.Wilczek,“Geometricand renormalized entropy in conformal feld theory,” Nucl. Phys. B424 (1994) 443-467, arXiv:hep-th/9403108 [hep-th]. [9] P. Calabrese and J. L. Cardy,“Entanglement entropy and quantum field theory,” J. Stat. Mech.0406 (2004) P06002,arXiv:hep-th/0405152 [hep-th].   
[10] M.Headrick,“Entanglement Rényi entropies in holographic theories,” Phys. Rev. D82 (2010) 126010, arXiv:1006.0047 [hep-th].   
[11] L.-Y. Hung, R. C. Myers, M. Smolkin,and A. Yale,“Holographic Calculations of Rényi Entropy,” JHEP1112 (2011) 047,arXiv:1110.1084 [hep-th].   
[12] D.Fursaev,“Entanglement Rényi Entropies in Conformal Field Theories and Holography," JHEP 1205 (2012) 080,arXiv:1201.1702 [hep-th].   
[13] T. Hartman,“Entanglement Entropy at Large Central Charge,” arXiv:1303.6955 [hep-th].   
[14] T. Faulkner,“The Entanglement Rényi Entropies of Disjoint Intervals in AdS/CFT,” arXiv:1303.7221 [hep-th].   
[15] T.Barrella, X. Dong, S. A. Hartnoll and V.L. Martin,“Holographic entanglement beyond classical gravity,” JHEP 1309 (2013) 109,arXiv:1306.4682 [hep-th].   
[16] X. Dong,“The Gravity Dual of Renyi Entropy,” Nature Commun.7 (2016) 12472, arXiv:1601.06788 [hep-th].   
[17] J.D. Brown and M. Henneaux,“Central Charges in the Canonical Realization of Asymptotic Symmetries: An Example from Three-Dimensional Gravity,” Commun. Math. Phys.104 (1986) 207-226.   
[18]P.Calabrese, J. Cardy,and E. Tonni,“Entanglement entropy of two disjoint intervals in conformal field theory I,” J. Stat. Mech.1101 (2011) P01021,arXiv:1011.5482 [hep-th].   
[19]B.Chen and J.-j. Zhang,“On short interval expansion of Rényi entropy,” JHEP 1311 (2013)164, arXiv:1309.5453 [hep-th].   
[20] B. Chen, J. Long,and J.-j. Zhang,“Holographic Renyi entropy for CFT with $W$ symmetry,” JHEP 1404 (2014) 041,arXiv:1312.5510 [hep-th].   
[21] E. Perlmutter,“Comments on Rényi entropy in AdS $^ 3$ /CFT $^ 2$ ,” JHEP 05 (2014) 052, arXiv:1312.5740 [hep-th].   
[22] B. Chen, F.-y. Song, and J.-j. Zhang,“Holographic Rényi entropy in AdS $_ 3$ /LCFT $^ 2$ correspondence," JHEP 1403 (2014) 137,arXiv:1401.0261 [hep-th].   
[23] M. Beccaria and G. Macorini,“On the next-to-leading holographic entanglement entropy in $A d S _ { 3 } / C F T _ { 2 }$ ”， JHEP 1404 (2014) 045,arXiv:1402.0659 [hep-th].   
[24] J. Cardy and C. P. Herzog,“Universal Thermal Corrections to Single Interval Entanglement Entropy for Two Dimensional Conformal Field Theories,” Phys. Rev. Lett.112 (2014) 171603, arXiv:1403.0578 [hep-th].   
[25]B.Chen and J.-q. Wu,“Single interval Rényi entropy at low temperature,” JHEPO8 (2014) 032, arXiv:1405.6254 [hep-th].   
[26] J. Long,“Higher Spin Entanglement Entropy,” JHEP12 (2014)055,arXiv:1408.1298 [hep-th].   
[27]B. Chen and J.-q. Wu,“Holographic calculation for large interval Renyi entropy at high temperature,” Phys. Rev.D92 (2015) 106001,arXiv:1506.03206 [hep-th].   
[28] B.Chen,J.-q. Wu,and Z.-c. Zheng,“Holographic Renyi entropy of single interval on torus: with W symmetry,” Phys. Rev. D92 (2015) 066002,arXiv:1507.00183 [hep-th].   
[29] B. Chen and J.-q. Wu,“1-loop partition function in AdS $^ 3$ /CFT $^ 2$ ,”JHEP 12（2015）109, arXiv:1509.02062 [hep-th].   
[30] J.-j. Zhang,“Holographic Renyi entropy for two-dimensional $\mathcal { N } = ( 1 , 1 )$ superconformal field theory," JHEP1512 (2015) 027,arXiv:1510.01423 [hep-th].   
[31] Z.Li and J.-j. Zhang,“On one-loop entanglement entropy of two short intervals from OPE of twist operators,” JHEP 1605 (2016) 130,arXiv:1604.02779 [hep-th].   
[32]B. Chen and J.-q. Wu,“Higher spin entanglement entropy at finite temperature with chemical potential," JHEP07 (2016) 049,arXiv:1604.03644 [hep-th].   
[33] B. Chen, J.-B. Wu, and J.-j. Zhang,“Short interval expansion of Rényi entropy on torus,” JHEP1608 (2016)130,arXiv:1606.05444 [hep-th].   
[34] J.-j. Zhang,“Note on non-vacuum conformal family contributions to Rényi entropy in two-dimensional CFT,” arXiv:1610.07764 [hep-th].   
[35] A. Maloney and E. Witten,“Quantum Gravity Partition Functions in Three Dimensions,” JHEP 1002 (2010) 029,arXiv:0712.0155 [hep-th].   
[36] X. Yin,“Partition Functions of Three-Dimensional Pure Gravity,” Commun.Num.Theor.Phys.2(2008) 285-324,arXiv:0710.2129 [hep-th].   
[37] S. Giombi, A. Maloney, and X. Yin,“One-loop Partition Functions of 3D Gravity,” JHEP 0808(2008) 007,arXiv:0804.1773 [hep-th].   
[38] R. Blumenhagen and E. Plauschinn,“Introduction to conformal field theory,” Lect. Notes Phys. 779 (2009) 1-256.