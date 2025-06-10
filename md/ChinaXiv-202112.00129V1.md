# Entropy of Random Permutation Set

Luyuan Chena, Yong Denga,b,c,d,\*

$\boldsymbol { a }$ Institute ofFundamental and Frontier Sciences,University of Electronic Science and Technology of China, Chengdu, China. bSchoolofiilsity C School of Knowledge Science, Japan Advanced Institute of Science and Technology, Nomi, Ishikawa 923-1211,Japan dDepartmentofManagement,Technology,and Economics,ETH Zurich,Zurich,Swtzerlan

# Abstract

Recently, a new kind of set, named as Random Permutation Set (RPS),is proposed. RPS takes the permutation of a certain set into consideration, which can be regarded as a generalization of evidence theory. Uncertainty is an important feature of RPS. A straightforward question is how to measure the uncertainty of RPS.To address this problem, the entropy of RPS is presented in this paper. When the order of elements in permutation event is ignored, the proposed RPS entropy degenerates into Deng entropy in evidence theory. When each permutation event is limited to containing just one element, the proposed RPS entropy degenerates into Shannon entropy in probability theory. Hence the RPS entropy can be regarded as the generalization of Deng entropy and Shannon entropy. Numerical examples are illustrated the efficiency of the proposed RPS entropy.

Keywords: Random permutation set, Shannon entropy, Deng entropy, Entropy of random permutation set, Uncertainty

# 1. Introduction

Uncertainty plays an important role in our daily life, different theories have been developed to deal with uncertainty [60,28,47, 40,34], such as probability theory [19], rough sets [29,22,8], fuzzy sets [53, 30], type-2 fuzzy sets [31, 3], Evidence theory [39,51], Z-numbers [54,18], D number [10],belief rule [4], three-way decision [52,58],etc. These methods are applied in various areas, like traffic control [21], decisionmaking [14, 57,27], classification [26,25], risk assessment [38], and so on [15, 7, 20].

Most existing theories are based on set theory. Set theory provides a tool for describing the collection of objects or elements,which is important and fundamental in math science [17]. For instance, the sample space of an experiment in probability theory is the set that contains all possible outcomes of that experiment [19]. In evidence theory, the power set is the set that considers all possible subsets of frame of discernment, which is a basis for basic probability assignment (BPA) [9, 32].

Recently, for exploring the meaning of the power set in evidence theo ry, a possible explanation of power set is proposed from the view of Pascal's triangle and combinatorial number [36]. Then inspired by the idea of replacing combinatorial number with permutation number, Deng pro posed a new type of set, called Random permutation set (RPS) [13]. RPS consists of permutation event space (PES) and permutation mass function (PMF). The PES of a certain set considers all the permutation of that set. The elements of PES are called permutation events. PMF describes the chance of a certain permutation event that would happen. RPS is compatible with evidence theory and probability theory [13].

RPS provides a new perspective to deal with uncertainty regarding the order of elements,a straightforward question is that how to measure the uncertainty of RPS. Reviewing the existing uncertainty measures, various kinds of entropy functions have been presented, such as Shannon entropy in probability theory [33], Deng entropy in evidence theory [11],and fuzzy entropy in fuzzy sets [37]. In this paper, the entropy of RPS is presented for handling the uncertainty measure. The entropy of RPS is compatible with Deng entropy and Shannon entropy. When the order of elements in permutation events is ignored, the proposed RPS entropy will degenerate into Deng entropy. When each permutation event is limited to containing just one element, the proposed RPS entropy will degenerate into Shannon entropy. Several numeric examples are illustrated the efficiency of the proposed RPS entropy.

The rest of this article is as follows. Section 2 introduces the preliminaries. Section 3 presents the entropy of RPS. Section 4 uses some numerical example to illustrate the presented RPS entropy. Section 5 makes a brief conclusion.

# 2.Preliminaries

In this section,we briefly review some preliminaries of this paper.

# 2.1. Random permutation set

Random permutation set (RPS) is a novel set consisting of permutation event space (PES) and permutation mass function (PMF) [13]. Some basic definitions of RPS are given as follows.

Definition 2.1 (Permutation event space). Given a fixed set of $N$ mutually exclusive and exhaustive elements $\Theta = \{ \theta _ { 1 } , \theta _ { 2 } , \ldots , \theta _ { N } \}$ , its permutation event space (PES) is a set of all possible permutations of $\Theta$ defined as follows:

$$
\begin{array} { r l } & { P E S \left( \Theta \right) = \{ A _ { i j } \mid i = 0 , . . . , N ; j = 1 , . . . , P ( N , i ) \} } \\ & { \qquad = \{ \emptyset , \left( \theta _ { 1 } \right) , \left( \theta _ { 2 } \right) , . . . , \left( \theta _ { N } \right) , \left( \theta _ { 1 } , \theta _ { 2 } \right) , \left( \theta _ { 2 } , \theta _ { 1 } \right) , . . . , \left( \theta _ { N - 1 } , \theta _ { N } \right) , } \\ & { \qquad \left( \theta _ { N } , \theta _ { N - 1 } \right) , . . . , \left( \theta _ { 1 } , \theta _ { 2 } , . . . , \theta _ { N } \right) , . . . , \left( \theta _ { N } , \theta _ { N - 1 } , . . . , \theta _ { 1 } \right) \} } \end{array}
$$

in whichP(N,i) isthe-permutationof NdefinedasP(Ni)=N The element $A _ { i j }$ in PES is called the permutation event, which is $a$ tuple representing a possible permutation of $\Theta$ where $i$ indicates the index for the cardinality of $A _ { i j }$ and $j$ denotes the index for the possible permutation.

Definition 2.2 (Random permutation set). Given a fixed set of $N$ mutually exclusive and exhaustive elements $\Theta = \{ \theta _ { 1 } , \theta _ { 2 } , \dots , \theta _ { N } \}$ , its random permutation set (RPS) is a set of pairs defined as follows:

$$
R P S \left( \Theta \right) = \left\{ \left. A , \mathcal { M } \left( A \right) \right. \mid A \in P E S \left( \Theta \right) \right\}
$$

where $\mathcal { M }$ is called the permutation mass function $( P M F )$ , which is defined as:

$\mathcal { M } : P E S ( \Theta )  [ 0 , 1 ]$ constrained by $\mathcal { M } ( \emptyset ) = 0$ and $\begin{array} { r } { \sum _ { A \in P E S ( \Theta ) } \mathcal { M } ( A ) = 1 . } \end{array}$ （20

Some important properties about RPS are discussed in [13]. Specifically, the PES of RPS is compatible with the power set in evidence theory and sample space in probability theory. The PMF of RPS is compatible with BPA and probability distribution.

# 2.2. Evidence theory

Evidence theory (Dempster-Shafer evidence theory) provides an efficient tool for dealing with uncertainty [12, 61,35]. Researchers have developed evidence theory theoretically, especially for some open issues [59, 48]. For instance, the decision-making model based on mass function [5], uncertainty measure of mass function [49] and the complex evidence theory [43, 46, 45]. With the superiority in uncertain environment, evidence theory also has been widely applied in engineering fields [16, 6].

Some basic conceptions about evidence theory are summarized as follows [9, 32].

Definition 2.3 (Frame of discernment). Let $\Omega ,$ called the frame of discernment $( F O D )$ ,denotes a fixed set of $N$ mutually exclusive and exhaustive elements, indicated by

$$
\Omega = \{ \omega _ { 1 } , \omega _ { 2 } , \ldots , \omega _ { N } \}
$$

$P S ( \Omega )$ is the power set of $\Omega ,$ which contains all subsets of $\Omega$ and has $2 ^ { N }$ elements,indicated by

$$
\begin{array} { r l } & { P S ( \Omega ) = \{ A _ { 1 } , A _ { 2 } , \cdot \cdot \cdot , A _ { 2 ^ { N } } \} } \\ & { \qquad = \{ \emptyset , \{ \omega _ { 1 } \} , \{ \omega _ { 2 } \} , \cdot \cdot \cdot , \{ \omega _ { N } \} , } \\ & { \qquad \{ \omega _ { 1 } , \omega _ { 2 } \} , \{ \omega _ { 1 } , \omega _ { 3 } \} , \cdot \cdot \cdot , \{ \omega _ { 1 } , \omega _ { N } \} , \cdot \cdot \cdot , \Omega \} } \end{array}
$$

Definition 2.4 (Mass function). Given a FOD of $\Omega$ , a basic probability assignment (BPA), also called a mass function, is a mapping from $P S ( \Omega )$ to $I O , \ 1 J ,$ （204号 formally defined by:

$$
m : P S ( \Omega )  [ 0 , 1 ]
$$

constrained by

$$
m ( \emptyset ) = 0 a n d \sum _ { A \in 2 ^ { \Omega } } m ( A ) = 1
$$

A is called a focal element if $m ( A ) > 0$

# 2.3. Shannon entropy

Shannon entropy, which was proposed by Shannon, addressed the prob lem of quantitative measurement of information [33]. The related definition is described below:

Definition 2.5. Given a probability distribution in a certain state space， Shannon entropy is defined as

$$
H _ { S E } ( p ) = - \sum _ { i = 1 } ^ { n } p _ { i } l o g _ { b } p _ { i }
$$

where n is the number of basic states, $b$ is the base of logarithm. $p _ { i }$ denotes the probability of state i appears, $\textstyle \sum _ { i = 1 } ^ { n } p _ { i } = 1$ ，

# 2.4. Deng entropy

Entropy plays a significant role in uncertainty modelling [50,24, 55, 56,1], especially in complex systems [44, 2]. Deng entropy [11] is a kind of belief entropy, which measures the uncertainty in evidence theory and applied in many fields [42, 23, 41]. An important feature of Deng entropy is that it is compatible with Shannon entropy.

Definition 2.6 (Deng entropy). Given a mass function distribution defined on $\Omega ,$ , Deng entropy is defined as [11]:

$$
H _ { D E } ( m ) = - \sum _ { A \in P S ( \Omega ) } m ( A ) \log \frac { m ( A ) } { 2 ^ { \left| A \right| } - 1 }
$$

# 3. Entropy of random permutation set

For measuring the uncertainty of RPS, the entropy of RPS is presented in this section.

Definition 3.1 (Entropy of random permutation set). Given a RPS denoted asI $\mathring { \mathrm { ? } P S } \left( \Theta \right) \ : = \ : \big \{ \big < A _ { i j } , \mathcal { \bar { M } } \left( A _ { i j } \right) \big > \big | A _ { i j } \big > \in P E S \left( \Theta \right) \big \} .$ ,the entropy of RPS is defined as:

$$
H _ { R P S } \left( \mathcal { M } \right) = - \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \mathcal { M } \left( A _ { i j } \right) \log \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { F \left( i \right) - 1 } \right)
$$

where $\begin{array} { r } { P ( N , i ) = \frac { N ! } { ( N - i ) ! } } \end{array}$ is the i-permutation of $N$ and $\begin{array} { r } { F \left( i \right) = \sum _ { k = 0 } ^ { i } P \left( i , k \right) = } \end{array}$ $\scriptstyle \sum _ { k = 0 } ^ { i } { \frac { i ! } { ( i - k ) ! } }$ is the sumfromO-permutationof $i$ 0寳 $i$ permutation of $i$

Proposition 3.1. If the order of elements in permutation event is ignored, the proposed RPS entropy will degenerate into Deng entropy in evidence theory.

Proof 3.1. If the order of elements in permutation event is ignored, the permutation number $P ( N , i )$ degenerates into combinatorial number $C ( N , i )$ ,and $F ( i )$ should be calculated as $\begin{array} { r } { \bar { F ( i ) } = \sum _ { k = 0 } ^ { i } C ( i , k ) = 2 ^ { i } } \end{array}$ ，

$$
\begin{array} { r l } { \displaystyle H _ { R P S } \left( \mathcal { M } \right) = - \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \mathcal { M } \left( A _ { i j } \right) \log \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { F \left( i \right) - 1 } \right) } & { } \\ { = - \displaystyle \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { C \left( N , i \right) } \mathcal { M } \left( A _ { i j } \right) \log \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { 2 ^ { i } - 1 } \right) } & { } \\ { = - \displaystyle \sum _ { i = 1 } ^ { 2 ^ { N } } \mathcal { M } \left( A _ { i } \right) \log \left( \frac { \mathcal { M } \left( A _ { i } \right) } { 2 ^ { \left| A _ { i } \right| } - 1 } \right) } & { } \end{array}
$$

As discussed in Ref.[13],under the situation of ignoring the order of elements in permutation event,the PES of RPS degenerates to the power set,and the PMF of RPS degenerates to BPA in evidence theory. Hence Eq. (12) is also calculated as

$$
\begin{array} { c l c r } { { \displaystyle H _ { R P S } \left( \mathcal { M } \right) = - \sum _ { A _ { i } \in P S ( \Omega ) } m ( A _ { i } ) \log \left( \frac { m ( A _ { i } ) } { 2 ^ { \left| A _ { i } \right| } - 1 } \right) } } \\ { { = H _ { D E } ( m ) } } \end{array}
$$

Therefore, when the order of elements in permutation event is ignored, the proposed RPS entropy degenerates to Deng entropy.

Proposition 3.2. When each permutation event is limited to containing just one element, the proposed RPS entropy will degenerate into Shannon entropy in probability theory.

Proof 3.2. If each permutation euent is limited to containing just one element, $i = 1 , F ( i ) = F ( 1 ) = 2$

$$
\begin{array} { r l } { \displaystyle H _ { R P S } \left( \mathcal { M } \right) = - \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \mathcal { M } \left( A _ { i j } \right) \log \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { F \left( i \right) - 1 } \right) } & { } \\ { = - \sum _ { j = 1 } ^ { P \left( N , 1 \right) } \mathcal { M } \left( A _ { 1 j } \right) \log \left( \frac { \mathcal { M } \left( A _ { 1 j } \right) } { F \left( 1 \right) - 1 } \right) } & { } \\ { = - \sum _ { j = 1 } ^ { N } \mathcal { M } \left( A _ { 1 j } \right) \log \left( \mathcal { M } \left( A _ { 1 j } \right) \right) } & { } \end{array}
$$

As discussed in Ref. [13l, under the situation of containing just one element in each permutation event, the PES of RPS degenerates to the sample space, and the PMF of RPS degenerates to probability distribution. Hence Eq. (14) is also calculated as

$$
\begin{array} { c } { { \displaystyle H _ { R P S } \left( \mathcal { M } \right) = - \sum _ { j = 1 } ^ { N } p _ { j } \log p _ { j } } } \\ { { = H _ { S E } ( p ) } } \end{array}
$$

Therefore, when each permutation event is limited to containing just one element, the proposed RPS entropy degenerates to Shannon entropy.

In conclusion, from Propositions 3.1 and 3.2, we can conclude that the proposed RPS entropy is compatible with Deng entropy and Shannon entropy, as shown in Fig. 1.

![](images/659c67b328eac8e6e9b4efbe8ac75045ffb158fd7d7afe8b51322982cc0bb7fa.jpg)  
Figure 1: The relationship between the proposed RPS entropy, Deng entropy and Shannon entropy

Situation 1: ignore the order of the element in permutation event Situation 2:each permutation event just contains just one element

# 4. Numerical examples and discussions

In this section, some numerical examples are shown to illustrate the presented entropy of RPS.

Example 4.1. Given the fixed set of $\Theta = \{ X , Y , Z \} .$ , a RPS defined on $\Theta$ is given as follows:

$R P S _ { 1 } ( \Theta ) = \left\{ < ( X ) , 0 . 4 > , < ( Y , Z ) , 0 . 1 > , < ( X , Y , Z ) , 0 . 1 5 > , < ( Y , Z , X ) , 0 . 3 5 > \right\}$ （

Based on Eq. (11), the associated entropy of $R P S _ { 1 }$ is calculated as

$$
\begin{array} { l } { \displaystyle H _ { B B S _ { 1 } } ( \mathcal { M } ) = - \sum _ { i = 1 } ^ { 3 } \sum _ { j = 1 } ^ { P ( \lambda , i ) } \mathcal { M } \left( A _ { i j } \right) \log \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { F \left( i \right) - 1 } \right) } \\ { \displaystyle = - 0 . 4 * l o g \left( \frac { 0 . 4 } { F ( 1 ) - 1 } \right) - 0 . 1 * l o g \left( \frac { 0 . 1 } { F ( 2 ) - 1 } \right) } \\ { \displaystyle ~ - 0 . 1 5 * l o g \left( \frac { 0 . 1 5 } { F ( 3 ) - 1 } \right) - 0 . 3 5 * l o g \left( \frac { 0 . 3 5 } { F ( 3 ) - 1 } \right) } \\ { \displaystyle = - 0 . 4 * l o g \left( \frac { 0 . 4 } { 2 - 1 } \right) - 0 . 1 * l o g \left( \frac { 0 . 1 } { 5 - 1 } \right) } \\ { \displaystyle ~ - 0 . 1 5 * l o g \left( \frac { 0 . 1 5 } { 1 6 - 1 } \right) - 0 . 3 5 * l o g \left( \frac { 0 . 3 5 } { 1 6 - 1 } \right) } \\ { \displaystyle = 2 . 8 9 5 } \end{array}
$$

Followed by Example 4.1, consider the following two scenarios:

· If the order of elements in permutation events is ignored, (X, Y, Z) and $( \Upsilon , Z , \Upsilon )$ are the same sets in Eq. (l6), the $R P S _ { 1 }$ is updated as

$$
R P S _ { 2 } ( \Theta ) = \{ < ( X ) , 0 . 4 > , < ( Y , Z ) , 0 . 1 > , < ( X , Y , Z ) , 0 . 5 > \}
$$

The associated $R P S _ { 2 }$ entropy is calculated as

$$
\begin{array} { l } { { H _ { R P S _ { 2 } } \left( \mathcal { M } \right) = \displaystyle - 0 . 4 * l o g \left( \frac { 0 . 4 } { F ( 1 ) - 1 } \right) - 0 . 1 * l o g \left( \frac { 0 . 1 } { F ( 2 ) - 1 } \right) - 0 . 5 * l o g \left( \frac { 0 . 5 } { F ( 3 ) - 1 } \right) } } \\ { { \mathrm { } = \displaystyle - 0 . 4 * l o g \left( \frac { 0 . 4 } { 2 - 1 } \right) - 0 . 1 * l o g \left( \frac { 0 . 1 } { 3 - 1 } \right) - 0 . 5 * l o g \left( \frac { 0 . 5 } { 7 - 1 } \right) } } \\ { { \mathrm { } = 1 . 8 6 5 6 } } \end{array}
$$

Actually, when the order of elements in permutation events is ignored, the permutation event space degenerates into the power set in evidence theory, i.e., $P E S ( \Theta )$ is the same as $P S ( \Omega )$ . Therefore, the $R P S _ { 2 }$ in Eq. (18) can be regarded a mass function in evidence theory, just as

$$
m ( \{ X \} ) = 0 . 4 , m ( \{ Y , Z \} ) = 0 . 1 , m ( \{ X , Y , Z \} ) = 0 . 5
$$

Based on Eq. (1O), the associated Deng entropy is calculated as

$$
\begin{array} { l } { { H _ { D E } \left( m \right) = { - 0 . 4 * l o g \left( { \displaystyle { \frac { 0 . 4 } { { 2 ^ { 1 } - 1 } } } } \right) - 0 . 1 * l o g \left( { \displaystyle { \frac { { 0 . 1 } } { { 2 ^ { 2 } - 1 } } } } \right) - 0 . 5 * l o g \left( { \displaystyle { \frac { { 0 . 5 } } { { 2 ^ { 3 } - 1 } } } } \right) } } } \\ { { { } } } \\ { { { = 1 . 8 6 5 6 } } } \end{array}
$$

which is the same as $H _ { R P S _ { 2 } }$ in Eq. (19). As a result, if the order of elements in PES is ignored, the proposed RPS entropy will degenerate into Deng entropy in evidence theory.

· For the $R P S _ { 2 }$ in Eq. (16), let $A _ { 1 } = ( X ) , A _ { 2 } = ( Y , Z ) , A _ { 3 } = ( X , Y , Z ) .$ If these permutation events just contain one element, and they are mutually exclusive and independent, just as

$$
R P S _ { 3 } ( \Theta ) = \{ < ( A _ { 1 } ) , 0 . 4 > , < ( A _ { 2 } ) , 0 . 1 > , < ( A _ { 3 } ) , 0 . 5 > \}
$$

The associated entropy of $R P S _ { 3 }$ is calculated as

$$
\begin{array} { r l } & { H _ { R P S _ { 3 } } \left( \mathcal { M } \right) = 0 . 4 * l o g \left( \frac { 0 . 4 } { F ( 1 ) - 1 } \right) + 0 . 1 * l o g \left( \frac { 0 . 1 } { F ( 1 ) - 1 } \right) + 0 . 5 * l o g \left( \frac { 0 . 5 } { F ( 1 ) - 1 } \right) } \\ & { = - ( 0 . 4 * l o g \left( \frac { 0 . 4 } { 2 - 1 } \right) + 0 . 1 * l o g \left( \frac { 0 . 1 } { 2 - 1 } \right) + 0 . 5 * l o g \left( \frac { 0 . 5 } { 2 - 1 } \right) ) } \\ & { = 1 . 3 6 1 0 } \end{array}
$$

Actually, when each permutation event just contains one element and they are mutually exclusive and independent, the permuta tion event space is equivalent to the sample space composed of basic events in probability theory. Therefore, the $R P S _ { 3 }$ in Eq. (22) can be regarded a probability distribution, just as

$$
p ( X ) = 0 . 4 , p ( Y ) = 0 . 1 , p ( Z ) = 0 . 5
$$

Based on Eq. (9), the Shannon entropy is calculated as

$$
\begin{array} { c } { { H _ { S E } ( p ) = - 0 . 4 * l o g ( 0 . 4 ) - 0 . 1 * l o g ( 0 . 1 ) - 0 . 5 * l o g ( \strut } } \\ { { { } } } \\ { { = 1 . 3 6 1 0 } } \end{array}
$$

which is the same as $H _ { R P S _ { 3 } }$ in Eq. (23). As a result, if each permutation event just contains one element and they are mutually ex clusive and independent, the proposed RPS entropy will degenerate into Shannon entropy.

Based on the discussion of these two scenarios, it can be concluded that the proposed RPS entropy is compatible with Deng entropy and Shannon entropy, as shown in Fig. 2.

![](images/ffb1edfdd825b63a990db411bcd3cfa2ac731532c014d8658b0085364592512f.jpg)  
Figure 2: the proposed RPS entropy is compatible with Deng entropy and Shannon entropy

Example 4.2. Given a fixed set of $\Theta = \{ 1 , 2 , 3 , \dots , 1 0 \}$ . A RPS defined on $\Theta$ is shown as follows.

（204 $R P S ( \Theta ) = \{ < ( 3 , 4 , 5 ) , 0 . 4 > , < ( 6 ) , 0 . 1 > , < ( X ) , 0 . 8 > , < ( 1 , 2 , 3 , \dots , 1 0 ) , 0 . 1 \}$ >} If the order in permutation events is ignored, the RPS is a mass function in evidence theory.

$$
m ( \{ 3 , 4 , 5 \} ) = 0 . 4 , m ( \{ 6 \} ) = 0 . 1 , m ( \{ X \} ) = 0 . 8 , m ( \Theta ) = 0 . 1
$$

When $X$ changes from 1 to $1 , 2 , 3 , \ldots , 1 0 ,$ ， the values of Deng entropy and the RPS entropy are calculated, which are shown in Table 1 and Figure 3.

From Table 1 and Figure 3, the results shows that as the size of sub set $X$ rises,both Deng entropy and the proposed RPS entropy increase monotonously. It is reasonable that the entropy values increase when the uncertainty involving a set increases. Importantly， with respect to the same size of $X _ { \cdot }$ ， the value of RPS entropy is larger than that of Deng entropy. This means that, the uncertainty of a RPS is larger than that of a mass function, since RPS takes permutation of a certain set into account while a mass function does not consider that.

Table 1: Deng entropy and the proposed RPS entropy when X chenges   

<html><body><table><tr><td>X</td><td>Dengentropy</td><td>TheRPSentropy</td></tr><tr><td>1</td><td>2.1622</td><td>3.5406</td></tr><tr><td>1,2</td><td>3.4301</td><td>5.1406</td></tr><tr><td>1,2,3</td><td>4.4080</td><td>6.6662</td></tr><tr><td>1,2,3,4</td><td>5.2877</td><td>8.3406</td></tr><tr><td>1,2,3,4,5</td><td>6.1255</td><td>10.2161</td></tr><tr><td>1,2,3,4,5,6</td><td>6.9440</td><td>12.2876</td></tr><tr><td>1,2,3,4,5,6,7</td><td>7.7531</td><td>14.5341</td></tr><tr><td>1,2,3,4,5,6,7,8</td><td>8.5576</td><td>16.9342</td></tr><tr><td>1,2,3,4,5,6,7,8,9</td><td>9.3599</td><td>19.4701</td></tr><tr><td>1,2,3,4,5,6,7,8,9,10</td><td>10.1610</td><td>22.1277</td></tr></table></body></html>

![](images/2fc9c40ba46053b1ed29e6276795130f26ac2111b9339f37499214d09e602d0c.jpg)  
Figure 3: The trend of Deng entropy and the proposed RPS entropy when X changes

# 5. Conclusion

Entropy is an important function to measure uncertainty. The main contribution of this paper is that the entropy of a new kind of set, named as Random permutation set (RPS),is first proposed. The proposed RPS entropy are compatible with Deng entropy and Shannon entropy. When the order of elements in permutation event is ignored, the proposed RPS entropy degenerates into Deng entropy. When each permutation event is limited to containing just one element, the proposed RPS entropy degenerates into Shannon entropy. Numerical examples are illustrated the proposed entropy of RPS. The new entropy provides a promising way for measuring the uncertain degree and handling ranked uncertain information.

# Acknowledgment

The Work is partially supported by National Natural Science Foundation of China (Grant No. 61973332), JSPS Invitational Fellowships for Research in Japan (Short-term).

[1] Manish Aggarwal. Decision aiding model with entropy-based subjective utility. Information Sciences, 501:558-572,2019.

[2] SG Babajanyan, AE Allahverdyan, and Kang Hao Cheong. Energy and entropy: Path from game theory to statistical mechanics. Physical Review Research, 2(4):043055,2020.

[3] Fatih Emre Boran,Diyar Akay, and Ronald R Yager. A probabilistic framework for interval type-2 fuzzy linguistic summarization. IEEE Transactions on Fuzzy Systems, 22(6):1640-1653, 2014.

[4] Leilei Chang, Limao Zhang, Chao Fu,and Yu-Wang Chen. Transparent digital twin for output control using belief rule base. IEEE Transactions 0n Cybernetics, page DOI: 10.1109/TCYB.2021.3063285, 2021.

[5] Luyuan Chen, Yong Deng, and Kang Hao Cheong. Probability transformation of mass function: A weighted network method based on the ordered visibility graph. Engineering Applications of Artificial Intelligence, 105:104438, 2021.

[6] Cuiping Cheng and Fuyuan Xiao. A distance for belief functions of orderable set. Pattern Recognition Letters,145:165-170,2021.

[7] Kang Hao Cheong, Jin Ming Koh,and Michael C Jones. Paradoxical survival: Examining the parrondo effect across biology. BioEssays, 41(6):1900027,2019.

[8] Lynn D'eer and Chris Cornelis. A comprehensive study of fuzzy covering-based rough set models: Definitions, properties and interrelationships. Fuzzy Sets and Systems,336:1-26,2018.

[9] A.P. Dempster. Upper and lower probabilities induced by a multivalued mapping. The Annals of Mathematical Statistics, 38(2):325-339, 04 1967.   
[10] Xinyang Deng and Wen Jiang. A total uncertainty measure for D numbers based on belief intervals. International Journal of Intelligent Systems,34(12):3302-3316, 2019.   
[11] Yong Deng. Deng entropy. Chaos, Solitons & Fractals, 91:549-553, 2016.   
[12] Yong Deng. Uncertainty measure in evidence theory. Science China Information Sciences, 63(11):1-19,2020.   
[13] Yong Deng. Random permutation set. International Journal of Computers Communications $\mathcal { E }$ Control, 17(1):4868,2022.   
[14] Chao Fu, Wenjun Chang, and Shanlin Yang. Multiple criteria group decision making based on group satisfaction. Information Sciences, 518:309-329,2020.   
[15] Hamido Fujita and Yu-Chien Ko. A heuristic representation learning based on evidential memberships: Case study of UCI-SPECTF. International Journal of Approximate Reasoning, 120, 2020.   
[16] Xianghao Gao, Xiaoyan Su, Hong Qian, and Xiaolei Pan. Dependence assessment in Human Reliability Analysis under uncertain and dynamic situations. Nuclear Engineering and Technology, 2021.   
[17] Thomas Jech. Set theory. Springer Science & Business Media, 2013.

[18] Wen Jiang, Ying Cao,and Xinyang Deng. A novel Z-network model based on Bayesian network and Z-number. IEEE Transactions on Fuzzy Systems,28(8):1585-1599,2020.

[19] PMLee. Probability theory. Bulletin of the London Mathematical Society, 12(4):318-319, 1980.

[20] Meizhu Li, Shaoguang Huang, Jasper De Bock, Gert De Cooman, and Aleksandra Pizurica.A robust dynamic classifier selection approach for hyperspectral images with imprecise label information. Sensors, 20(18):5262, 2020.

[21] Meng Li, Zehong Cao, and Zhibin Li. A reinforcement learning-based vehicle platoon control strategy for reducing energy consumption in traffic oscillations. IEEE Transactions on Neural Networks and Learning Systems, page DOI: 10.1109/TNNLS.2021.3071959,2021.

[22] Wentao Li, Witold Pedrycz, Xiaoping Xue, Weihua Xu, and Bingjiao Fan. Distance-based double-quantitative rough fuzzy sets with logic operations. International Journal of Approximate Reasoning， 101:206- 233,2018.

[23] Huchang Liao, Zhongyuan Ren, and Ran Fang. A Deng-entropybased evidential reasoning approach for multi-expert multi-criterion decision-making with uncertainty. International Journal of Computational Intelligence Systems,13(1):1281-1294, 2020.

[24] Peide Liu， Mengjiao Shen， Fei Teng, Baoying Zhu, Lili Rong,and Yushui Geng. Double hierarchy hesitant fuzzy linguistic entropy based TODIM approach using evidential theory. Information Sciences, 547:223-243, 2021.

[25] Zhun-Ga Liu, Lin-Qing Huang, Kuang Zhou, and Thierry Denoeux. Combination of transferable classification with multisource domain adaptation based on evidential reasoning. IEEE Transactions on Neural Networks and Learning Systems,32(5):2015-2029, 2021.

[26] Zhunga Liu, Xuxia Zhang, Jiawei Niu, and Jean Dezert. Combination of classifiers with different frames of discernment based on belief functions. IEEE Transactions on Fuzzy Systems,29(7):1764-1774, 2021.

[27] Lei Ni, Yu-wang Chen, and Oscar de Brujin. Towards understanding socially influenced vaccination decision making: An integrated model of multiple criteria belief modelling and social network analysis. European Journal of Operational Research,293(1):276-289, 2021.

[28] Yue Pan and Limao Zhang. Roles of artificial intelligence in construction engineering and management: A critical review and future trends. Automation in Construction, 122:103517,2021.

[29] Zdzislaw Pawlak. Rough sets. International journal of computer & information sciences, 11(5):341-356,1982.

[30] Barbara Pekala, Krzysztof Dyczkowski, Przemyslaw Grzegorzewski,and Urszula Bentkowska. Inclusion and similarity measures for interval-valued fuzzy sets based on aggregation and uncertainty assessment. Information Sciences,547:1182-1200,2021.

[31] Fariba Salehi,Mohammad Reza Keyvanpour,and Arash Sharifi. Gt2- cfc: General type-2 collaborative fuzzy clustering method. Information Sciences, 578:297-322,2021.

[32] G. Shafer. A mathematical theory of evidence, volume 1. Princeton university press Princeton, 1976.

[33] Claude Elwood Shannon. A mathematical theory of communication. ACM SIGMOBILE mobile computing and communications review, 5(1):3- 55,2001.

[34] Yafei Song, Qiang Fu, Yi-Fei Wang, and Xiaodan Wang. Divergencebased cross entropy and uncertainty measures of atanassov's intuitionistic fuzzy sets with their application in decision making. Applied Soft Computing, 84:DOI: 10.1016/j.as0c.2019.105703, 2019.

[35] Yafei Song, Xiaodan Wang, Lei Lei, and Shaohua Yue. Uncertainty measure for interval-valued belief structures. Measurement, 80:241- 250, FEB 2016.

[36] Yutong Song and Yong Deng. Entropic explanation of power set. International Journal of Computers Communications $\mathcal { E }$ Control, 16(4):4413 2021.

[37] Eulalia Szmidt and Janusz Kacprzyk. Entropy for intuitionistic fuzzy sets. Fuzzy sets and systems,118(3):467-477,2001.

[38] H. Wang, Y.-P.Fang, and E. Zio. Risk assessment of an electrical power system considering the influence of traffic congestion on a hypothetical scenario of electrified transportation system in new york state. IEEE Transactions on Intelligent Transportation Systems,22(1):142- 155,2021.

[39] Xiaodan Wang and Yafei Song. Uncertainty measure in evidence theory with its applications. Applied Intelligence, 48(7):1672-1688, 2018.

[40] Tao Wen and Kang Hao Cheong. The fractal dimension of complex networks: A review. Information Fusion, 73:87-102,2021.

[41] Fuyuan Xiao. Multi-sensor data fusion based on the belief divergence measure of evidences and the belief entropy. Information Fusion, 46(2019):23-32, 2019.

[42] Fuyuan Xiao. EFMCDM: Evidential fuzzy multicriteria decision making based on belief entropy.IEEE Transactions on Fuzzy Systems, 28(7):1477-1491, 2020.

[43] Fuyuan Xiao. Generalization of dempster-shafer theory: A complex mass function. Applied Intelligence, 50:3266-3275, 2020.

[44] Fuyuan Xiao. CaFtR: A fuzzy complex event processing method. International Journal of Fuzzy Systems, pages DOI: 10.1007/s40815-021- 01118-6,2021.

[45] Fuyuan Xiao. CED: A distance for complex mass functions. IEEE Transactions on Neural Networks and Learning Systems,32(4):1525-1535, 2021.

[46] Fuyuan Xiao. CEQD: A complex mass function to predict interference effects. IEEE Transactions on Cybernetics, page DOI: 10.1109 /TCYB.2020.3040770, 2021.

[47] Dawei Xie, Fuyuan Xiao,and Witold Pedrycz. Information quality for intuitionistic fuzzy values with its application in decision making Engineering Applications of Artificial Intelligence, page Accepted, 2021.

[48] Leihui Xiong, Xiaoyan Su, and Hong Qian. Conflicting evidence combination from the perspective of networks. Information Sciences, 580:408-418, 2021.

[49] Yige Xue and Yong Deng. Interval-valued belief entropies for Dempster Shafer structures. Soft Computing,25:8063-8071, 2021.

[50] Yige Xue and Yong Deng. Tsallis extropy. Communications in StatisticsTheory and Methods, page 10.1080/03610926.2021.1921804,2021.

[51] Ronald R Yager, Naif Alajlan, and Yakoub Bazi. Uncertain database retrieval with measure-based belief function attribute values. Information Sciences, 501:761-770, 2019.

[52] Yiyu Yao. Three-way decisions with probabilistic rough sets. Information sciences, 180(3):341-353,2010.

[53] Lotfi A Zadeh. Fuzzy sets. Information and control,8(3):338-353,1965.

[54] Lotfi A Zadeh. A note on z-numbers. Information Sciences, 181(14):2923-2932, 2011.

[55] Hui Zhang and Yong Deng. Entropy Measure for Orderable Sets. Information Sciences, 561:141-151,2021.

[56] Jing Zhang, Ruqin Liu, Jianfeng Zhang, and Bingyi Kang. Extension of Yager's negation of a probability distribution based on Tsallis en tropy. International Journal of Intelligent Systems,35(1):72-84,2020.

[57] Zhang Zhenjie, Xu Xiaobin, Chen Peng, Wu Xudong, Xu Xiaojian, and Wang Guodong. A novel nonlinear causal inference approach using vector-based belief rule base. International Journal of Intelligent Systems, page DOI: 10.1002/int.22500, 2021.

[58] Jie Zhou, Witold Pedrycz, Can Gao, Zhihui Lai, and Xiaodong Yue. Principles for constructing three-way approximations of fuzzy sets: A comparative evaluation based on unsupervised learning. Fuzzy Sets and Systems, 413:74-98,2021.

[59] Mi Zhou,Yu-Wang Chen，Xin-Bao Liu,Ba-Yi Cheng，and Jian-Bo Yang. Weight assignment method for multiple attribute decision making with dissimilarity and conflict of belief distributions. Computers & Industrial Engineering,147:106648,2020.

[60] Mi Zhou, Xin-Bao Liu, Yu-Wang Chen, Xiao-Fei Qian, Jian-Bo Yang, and Jian Wu. Assignment of attribute weights with belief distri butions for MADM under uncertainties. Knowledge-Based Systems, 189:105110, 2020.

[61] Qianli Zhou and Yong Deng. Belief extropy: Measure uncertainty from negation. Communications in Statistics - Theory and Methods, page 10.1080/03610926.2021.1980049,2021.