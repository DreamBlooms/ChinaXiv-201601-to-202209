# Maximum Entropy of Random Permutation Set

Jixiang Deng $^ { 1 }$ and Yong Deng1,2.3,4\*

1Institute of Fundamental and Frontier Science, University of   
Electronic Science and Technology of China,Chengdu, 610054, China.   
2School of Education, Shannxi Normal University, Xi'an, 710062, China. （204号 $^ 3$ School of Knowledge Science, Japan Advanced Institute of Science and Technology, Nomi, Ishikawa 923-1211, Japan.   
（204号 $^ 4$ Department of Management, Technology, and Economics, ETH Zurich, Zurich,8093, Switzerland.

\*Corresponding author(s). E-mail(s): dengentropy@uestc.edu.cn;

# Abstract

Recently,a new type of set,named as random permutation set (RPS), is proposed by considering all the permutations of elements in a certain set.For measuring the uncertainty of RPS,the entropy of RPS is presented.However, the maximum entropy principle of RPS entropy has not been discussed.To address this issue，in this paper，the maximum entropy of RPS is presented. The analytical solution for maximum entropy of RPS and its corresponding PMF condition are respectively proofed and discussed.Numerical examples are used to illustrate the maximum entropy RPS.The results show that the maximum entropy RPS is compatible with the maximum Deng entropy and the maximum Shannon entropy.When the order of the element in the permutation event is ignored,the maximum entropy of RPS will degenerate into the maximum Deng entropy. When each permutation event is limited to containing just one element,the maximum entropy of RPS will degenerate into the maximum Shannon entropy.

Keywords:Random permutation set, Shannon entropy, Deng entropy, Maximum entropy of random permutation set,Uncertainty

Springer Nature 2021 IIEX template

2 Maximum Entropy of Random Permutation Set

# 1 Introduction

In order to model and process the information with uncertainty,many theories have been developed, such as probability theory (Lee,l98O),fuzzy set theory (Zadeh， 1965)，Dempster-Shafer evidence theory (evidence theory)(Dempster, 1967; Shafer, 1976)，rough set theory (Pawlak， 1982)，and Z-numbers (Zadeh, 2Ol1),which have been further used in various fields,such as information fusion (Lai, Chang, Ang, & Cheong, 202O; Pan, Zhang, Wu, & Skibniewski, 2020), risk assessment (X. Gao, Su, Qian，& Pan, 2021; Wang, Abdin，Fang,& Zio, 2021; Wang,Fang,& Zio,2021)，game theory (Babajanyan，Allahverdyan，& Cheong, 2020; Cheong, Koh，& Jones， 2019)， fault diagnosis (X. Chen， Wang， Ying，& Cao, 2021; Huang et al.， 2021; Wang, Liu, Zhao, Guo, & Terzijae, 2020; Wang, Wei, et al., 202O), complex networks (T. Wen & Cheong, 2021), target recognition (Z. Wen,Liu, Zhang,& Pan, 2021; Xiao, 2021)，classification (Liu, Huang， Zhou,& Denoeux, 2021; Liu, Zhang, Niu,& Dezert, 2021) and decision making (Xie, Xiao,& Pedrycz, 2021).

Set theory is a fundamental theory, which provides a basis for most existing theories (Jech, 2O13). For example, the sample space of probability theory is the set that contains all the possible outcomes of a certain experiment (Lee, 1980).In Dempster-Shafer evidence theory， the power set considers all the possible subsets of a frame of discernment (Dempster, 1967; Shafer, 1976).

Recently, Song and Deng (2021) pointed out that a power set can be viewed as all the possible combination of the elements in a frame of discernment.A straightforward question is:“what a set would be if it not consider all the combinations of elements but all the permutations of elements in the frame of discernment?” To solve this problem, Y.Deng(2021） proposed a new type of set,called Random permutation set (RPS),which consists of permutation event space (PES) and permutation mass function (PMF).The PES of a certain set considers all the permutations of that set.PMF describes the chance that a certain element in PES would happen.

As is an efficient tool for deal with uncertainty,lots of information entropy have been proposed, such as Shannon entropy (Shannon,1948),Tsallis entropy (Tsallis, 1988; Xue & Deng, 2021b), and Deng entropy (Y. Deng, 2020b; Xue $\&$ Deng, 202la). Also, entropy has a wide variety of applications, including effect algebras (Di Nola, Dvurecenskij, Hycko, & Manara, 2O05), data fusion (Xiao, 2019), decision making (Xiao, 202O),and uncertainty measurements (Q. Gao, Wen,& Deng, 2021; Xue & Deng, 202la; Zhou $\&$ Deng, 2021). For measuring the uncertainty of RPS,L. Chen and Deng(2021） presented the entropy of RPS,which is compatible with Deng entropy and Shannon entropy.

The maximum entropy principle states that the distribution with maximal entropy best represents the current state of a system based on given information, which is widely used in many fields, such as negation transformation (Wu,Deng,& Xiong, 2021; Yager, 2014), imprecise side-conditions (Buckley, 2005), fuzzy cognitive maps (Feng,Lu, Pedrycz, Yang,& Liu, 2O19), decision making (Yager, 2009)，and uncertainty theory (Ma, 2021). As for the maximum entropy principle of RPS entropy, two aspects should be handled. The first one would be,“what is the maximum form for the entropy of RPS?” The second one would be,“what is the PMF condition for the maximum entropy of RPS?"

To address these issues,in this paper, the maximum entropy of RPS is presented. The analytical solution for maximum entropy of RPS and its corresponding PMF condition are respectively proofed and discussed. In addition, numerical examples are used to illustrate the maximum entropy RPS.The results show that the maximum entropy RPS is compatible with the maximum Deng entropy and the maximum Shannon entropy. When the order of the element in permutation event is ignored, the maximum entropy of RPS will degenerate into the maximum Deng entropy. When each permutation event is limited to containing just one element, the maximum entropy of RPS will degenerate into the maximum Shannon entropy.

The rest of this article is as follows. Section 2 introduces the preliminaries. Section 3 presents the maximum entropy of RPS. Section 4 uses some numerical examples to illustrated the maximum entropy of RPS. Section 5 makes a brief conclusion.

# 2 Preliminaries

In this section,we briefly review some preliminaries of this paper.

# 2.1 Dempster-Shafer evidence theory

Dempster-Shafer evidence theory (Dempster，1967； Shafer，1976） is anefficient tool for dealing with uncertainty (Y.Deng, 2020b).

Definition 2.1 (Frame of discernment).Let $\Theta$ ，called the frame of discern ment (FOD)，denotes a fixed set of $N$ mutually exclusive and exhaustive elements,indicated by $\Theta = \{ \theta _ { 1 } , \theta _ { 2 } , . . . , \theta _ { N } \}$ . The power set of $\Theta$ ，denoted as $2 ^ { \Theta }$ , contains all possible subsets of $\Theta$ and has $2 ^ { N }$ elements. $2 ^ { \Theta }$ is indicated by $2 ^ { \Theta } = \{ \emptyset , \{ \theta _ { 1 } \} , \cdots , \{ \theta _ { N } \} , \{ \theta _ { 1 } , \theta _ { 2 } \} , \cdots , \{ \theta _ { 1 } , \theta _ { N } \} , \cdots , \Theta \}$

Definition 2.2 (Mass function). Given a FOD of $\Theta$ ，a mass function is a mapping function defined by $m : 2 ^ { \Theta }  [ 0 , 1 ]$ ， which is constrained by $m ( \emptyset ) = 0$ （204 and $\sum _ { A \in 2 ^ { \Theta } } m ( A ) = 1$ ：

# 2.2 Deng entropy and maximum Deng entropy

In order to measure the uncertainty of mass function in evidence theory,a novel entropy,called Deng entropy，also named as belief entropy, is proposed (Y.Deng，2O2Ob)，which is further generalized into information volume (J. Deng & Deng, 2021; Y. Deng, 2020a; Q. Gao et al., 2021).

4 Maximum Entropy of Random Permutation Set

Definition 2.3 (Deng entropy). Given a certain mass function distribution defined on FOD $\Theta$ ， Deng entropy is defined as:

$$
H _ { D E } ( m ) = - \sum _ { A \in 2 ^ { \Theta } } m ( A ) \log ( \frac { m ( A ) } { 2 ^ { | A | } - 1 } )
$$

where $| A |$ isthe cardinal of a certain focal element $A$

The maximum entropy is an important conception in statistic.The analytical solution of the maximum Deng entropy and its corresponding condition are given as follows (Y. Deng, 2020b).

Theorem 1 (The mass function condition of maximum Deng entropy). Let the frame of discernment be $\Theta$ . The maximum Deng entropy appears if and onlyif the mass function distribution satisfies

$$
m ( A ) = { \frac { ( 2 ^ { \left| A \right| } - 1 ) } { \sum _ { A \in 2 ^ { \Theta } } ( 2 ^ { \left| A \right| } - 1 ) } } , A \in 2 ^ { \Theta }
$$

Theorem 2 (The analytic solution of maximum Deng entropy). The analytical solution of maximumDeng entropyis that

$$
H _ { \mathrm { { m a x } } \cdot D E } = \log \sum _ { A \in 2 ^ { \Theta } } ( 2 ^ { | A | } - 1 )
$$

# 2.3 Random permutation set

In 2021, Y.Deng (2021) proposed Random permutation set (RPS),which is a novel set consisting of permutation event space (PES） and permutation mass function (PMF). Some basic definitions of RPS are given as follows.

Definition 2.4 (Permutation event space).Given a fixed set of $N$ mutually exclusive and exhaustive elements $\Theta = \{ \theta _ { 1 } , \theta _ { 2 } , \dots , \theta _ { N } \}$ ， its permutation event space (PES)is a set of all possible permutations of $\Theta$ defined as follows:

$$
\begin{array} { r l } & { P E S \left( \Theta \right) = \{ A _ { i j } \mid i = 0 , . . . , N ; \ j = 1 , . . . , P ( N , i ) \} } \\ & { \qquad = \{ \ \varnothing , \left( \theta _ { 1 } \right) , \left( \theta _ { 2 } \right) , . . . , \left( \theta _ { N } \right) , \left( \theta _ { 1 } , \theta _ { 2 } \right) , \left( \theta _ { 2 } , \theta _ { 1 } \right) , . . . , \left( \theta _ { N - 1 } , \theta _ { N } \right) , } \\ & { \qquad \quad \left( \theta _ { N } , \theta _ { N - 1 } \right) , . . . , \left( \theta _ { 1 } , \theta _ { 2 } , . . . , \theta _ { N } \right) , . . . , \left( \theta _ { N } , \theta _ { N - 1 } , . . . , \theta _ { 1 } \right) \ \} } \end{array}
$$

in which $P ( N , i )$ is the $i$ -permutation of $N$ defined as $\begin{array} { r } { P ( N , i ) = \frac { N ! } { ( N - i ) ! } } \end{array}$ The element $A _ { i j }$ in PES is called the permutation event, which is a tuple representing a possible permutation of $\Theta$ ，where $i$ indicates the index for the cardinality of $A _ { i j }$ and $\jmath$ denotes the index for the possible permutation.

Definition 2.5 (Random permutation set). Given a fixed set of $N$ mutually exclusive and exhaustive elements $\Theta ~ = ~ \{ \theta _ { 1 } , \theta _ { 2 } , \ldots , \theta _ { N } \}$ ，its random permutation set (RPS) is a set of pairs defined as follows:

$$
R P S \left( \Theta \right) = \left\{ \left. A , \mathcal { M } \left( A \right) \right. \mid A \in P E S \left( \Theta \right) \right\}
$$

where $\mathcal { M }$ is called the permutation mass function $( P M F )$ ，which is defined as:

$\mathcal { M } : P E S ( \Theta )  [ 0 , 1 ]$ constrained by $\mathcal { M } ( \emptyset ) = 0$ and $\Sigma _ { A \in P E S ( \Theta ) } \mathcal { M } ( A ) = 1 .$

# 2.4 Entropy of random permutation set

For modeling the uncertainty of the RPS,L. Chen and Deng (2 presented the entropy of random permutation.

Definition 2.6 (Entropy of random permutation set). Let a RPS be denoted as $R P S \left( \Theta \right) = \left\{ \langle A _ { i j } , \mathcal { M } \left( A _ { i j } \right) \rangle \right.$ $\left| A _ { i j } \in P E S \left( \Theta \right) \right\}$ ， which is defined on I $^ { \mathcal { S } E S } \left( \Theta \right) = \{ A _ { i j } \ | i = 0 , . . . , N ; \ j = 1 , . . . , P \left( N , i \right) \}$ .The entropy of this RPS is defined as:

$$
H _ { R P S } \left( \mathcal { M } \right) = - \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \mathcal { M } \left( A _ { i j } \right) \log \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { F \left( i \right) - 1 } \right)
$$

where $\begin{array} { r } { P ( N , i ) = \frac { N ! } { ( N - i ) ! } } \end{array}$ is the $i$ -permutation of $N$ and $\begin{array} { r } { F \left( i \right) = \sum _ { k = 0 } ^ { i } P \left( i , k \right) = } \end{array}$ $\scriptstyle \sum _ { k = 0 } ^ { i } { \frac { i ! } { ( i - k ) ! } }$ is the sum from0-permutation of $i$ 0 $i$ -permutation of $i$ ，

# 3 Maximum entropy of random permutation set

In this section, the maximum entropy of RPS as well as its PMF condition are respectively presented and proofed.

# 3.1 The PMF condition for maximum entropy of RPS

Let the PES be $P E S \left( \Theta \right) = \{ A _ { i j } \ \vert i = 0 , . . . , N$ $j = 1 , . . . , P \left( N , i \right) \}$ ， $P ( N , i )$ be as follows $\begin{array} { r } { P ( N , i ) = \frac { N ! } { ( N - i ) ! } } \end{array}$ , and $F \left( i \right)$ be defined as $\begin{array} { r } { F \left( i \right) = \sum _ { k = 0 } ^ { i } P \left( i , k \right) = } \end{array}$ $\scriptstyle \sum _ { k = 0 } ^ { i } { \frac { i ! } { ( i - k ) ! } }$ . The PMFcondition for maximum entropyof RPS is presented as follows.

Theorem 3 (The PMF condition for maximum entropy of RPS). The maximum entropy of RPS happens if and only if the PMF satisfies the following condition

$$
\mathcal { M } \left( A _ { i j } \right) = \frac { F \left( i \right) - 1 } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] }
$$

# Springer Nature 2O21 IEX template

Proof 3.1 (Proof for Theorem 3). Let the entropy of RPS be denoted as

$$
H \left( \mathcal { M } \right) = - \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \mathcal { M } \left( A _ { i j } \right) \log _ { b } \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { F \left( i \right) - 1 } \right)
$$

which is contrained by

$$
\sum _ { A _ { i j } \in P E S ( \Theta ) } \mathcal { M } ( A _ { i j } ) = 1
$$

where $b$ is the base of logarithmic function. Then the Lagrange function with Lagrangianmultiplier $\lambda$ can be defined as follows:

$$
H _ { 0 } \left( \mathcal { M } \right) = - \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \mathcal { M } \left( A _ { i j } \right) \log _ { b } \left( \frac { \mathcal { M } \left( A _ { i j } \right) } { F \left( i \right) - 1 } \right) + \lambda \left( \sum _ { A _ { i j } \in P E S \left( \Theta \right) } \mathcal { M } ( A _ { i j } ) - 1 \right)
$$

In order to get the maximum of $H \left( \mathcal { M } \right)$ ， the gradient of $H _ { 0 } \left( \mathcal { M } \right)$ should be equal to O.Hence, the gradient can be deduced as follows:

$$
\frac { \partial H _ { 0 } \left( \mathcal { M } \right) } { \partial \mathcal { M } ( A _ { i j } ) } = - \log _ { b } \left( \frac { \mathcal { M } ( A _ { i j } ) } { F \left( i \right) - 1 } \right) - \frac { 1 } { \ln b } + \lambda = 0
$$

Based on Eq.(13)，it can be concluded that, with respect to different $\textit { i } \in$ $\{ 1 , 2 , . . . , N \}$ and $j \in \{ 1 , 2 , . . . , P ( N , i ) \}$ ， $\frac { \mathcal { M } ( A _ { i j } ) } { F ( i ) - 1 }$ is constat denoted s $C$ ：

$$
C \triangleq { \frac { \mathcal { M } ( A _ { i j } ) } { F \left( i \right) - 1 } }
$$

According to Eq.(14) and Eq.(11)，we can get:

$$
\begin{array} { c } { { \displaystyle \sum _ { A _ { i j } \in P E S ( \Theta ) } \mathcal { M } ( A _ { i j } ) = \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P ( N , i ) } \mathcal { M } \left( A _ { i j } \right) = \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P ( N , i ) } C * \left[ F \left( i \right) - 1 \right] } } \\ { { \displaystyle = \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) * C * \left( F \left( i \right) - 1 \right) \right] = 1 } } \end{array}
$$

so that $C$ can be calculated as

$$
C = \frac { 1 } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] }
$$

Based on Eq.(14)and Eq.(16),we can get this equation:

$$
\frac { \mathcal { M } ( A _ { i j } ) } { F \left( i \right) - 1 } = \frac { 1 } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] }
$$

Therefore, the condition for maximum entropy of RPS can be obtained:

$$
\mathcal { M } \left( A _ { i j } \right) = \frac { F \left( i \right) - 1 } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] }
$$

# 3.2 The analytic solution for maximum entropy of RPS

Let $P ( N , i )$ be as follows $\begin{array} { r } { P ( N , i ) = \frac { N ! } { ( N - i ) ! } } \end{array}$ , and $F \left( i \right)$ be defined as $F \left( i \right) =$ $\begin{array} { r } { \sum _ { k = 0 } ^ { i } P \left( i , k \right) = \sum _ { k = 0 } ^ { i } \frac { i ! } { \left( i - k \right) ! } } \end{array}$ The nalyticalsolutionforthe maximumtropy of RPS is detailed as follows.

Theorem 4 (The analytic solution for maximum entropy of RPS). The analytical solution for maximum entropy ofRPS is that

$$
H _ { \operatorname* { m a x } { \ - R P S } } = \log \left( \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] \right)
$$

Proof 3.2 (Proof for Theorem 4). According to Theorem 3, the maximum entropy of RPS happens when PMF satisfies Eq.(18).Hence, the analytic solution for maximum entropy of RPS can be calculated by substituting Eq.(18) into Eq.(8):

$$
H _ { \operatorname* { m a x } - R P S } = - \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \left\{ \frac { F \left( i \right) - 1 } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] } \log \left( \frac { 1 } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] } \right) \right\} ,
$$

For a certain PES, $N$ is a constant, so that $\begin{array} { r } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] } \end{array}$ is also a constant. Therefore,Eq.(20) can be calculated as:

$$
\begin{array} { c l } { { } } & { { \displaystyle - \log \left( \frac { 1 } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] } \right) \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { P \left( N , i \right) } \left( F \left( i \right) - 1 \right) } } \\ { { } } & { { \displaystyle - \frac { \log \left( \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] \right) } { \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] } \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] } } \\ { { } } & { { \displaystyle = \log \left( \sum _ { i = 1 } ^ { N } \left[ P \left( N , i \right) \left( F \left( i \right) - 1 \right) \right] \right) } } \end{array}
$$

As a result,the analytic solution for maximum entropy of RPS is obtained.

# 4 Numerical examples and discussions

In this section，some numerical examples are shown to illustrate the presented maximum entropy of RPS and its PMF condition.

Springer Nature 2021 IEX template

Example 4.1.Assume there are three balls in a box, whose colors are red,   
blue,and green, respectively. With respect to different colors, these balls in the   
box can be denoted by $\{ R , B , G \}$ . Then, we take the following actions:   
Action 1: Randomly take out one ball from the box.   
Action 2: Randomly take out $\textbf { \em a }$ number of balls from the box without replacement.   
Action 3: Randomly take out a number of balls from the box in sequence without replacement.

![](images/f5b671060c21563776f062e54cd21bfa427b135aaca6754acd47ccc2a2870b55.jpg)  
Fig.1: The illustration for all the possible results based on Action 1 to 3

All the possible results of the three actions can be respectively repre sented by sample space $\Theta$ ， power set $2 ^ { \{ R , B , G \} }$ ， and permutation event space $P E S ( \{ R , B , G \} )$ ，which are illustrated in Figure 1 and detailed as follows:

$$
\Theta = \{ R , B , G \}
$$

$$
\begin{array} { r l r } & { } & { 2 ^ { \{ R , B , G \} } = \{ \ \varnothing , \{ R \} , \{ B \} , \{ G \} , } \\ & { } & { \{ R , B \} , \{ R , G \} , \{ B , G \} , \{ R , B , G \} \ \} } \end{array}
$$

$$
\begin{array} { r l } & { P E S ( \{ R , B , G \} ) = \{ \begin{array} { l l } { \emptyset , ( R ) , ( B ) , ( G ) , } \\ & { ( R , B ) , ( R , G ) , ( B , G ) , } \end{array}  } \\ & { \qquad ( B , R ) , ( G , R ) , ( G , B ) , } \\ & { ( R , B , G ) , ( R , G , B ) , ( B , R , G ) , } \end{array}
$$

Based on $\Theta$ ， $2 ^ { \{ R , B , G \} }$ ，and $P E S \left( \{ R , B , G \} \right)$ ， the probability condition formaximum Shannon entropy (Shannon， 1948)， the mass function conditionfor maximum Deng entropy (Y. Deng， 2020b)，and the PMF condition formaximum entropyofRPS can be respectivelyobtained:

$$
\begin{array} { r l } & { \begin{array} { r l } & { P : P \left( \{ R \} \right) = P \left( \{ B \} \right) = P \left( \{ G \} \right) = 0 . 3 3 3 3 , } \end{array} } \\ &  \begin{array} { r l } & { m : m \left( \{ R \} \right) = m \left( \{ B \} \right) = m \left( \{ G \} \right) = 0 . 0 5 2 6 ; } \\ & { m : B \} \end{array} } \\ & { \begin{array} { r l } & { m \left( \{ R , B \} \right) = m \left( \{ R , G \} \right) = m \left( \{ B , G \} \right) = 0 . 1 5 7 9 ; } \\ & { m \left( \{ R , B , G \} \right) = 0 . 3 6 8 ; } \end{array} } \\ & { \begin{array} { r l } & { \mathcal { M } : \mathcal { M } = \mathcal { M } \left( \{ R \} \right) = 0 . 3 6 8 ; } \\ & { \mathcal { M } \left( R \right) = \mathcal { M } \left( \mathcal { B } \right) = \mathcal { M } \left( G \right) = 0 . 0 0 8 5 ; } \end{array} } \\ & { \begin{array} { r l } & { \mathcal { M } \left( R , B \right) = \mathcal { M } \left( R , G \right) = \mathcal { M } \left( B , G \right) } \\ & { \mathcal { M } \left( B , R \right) = \mathcal { M } \left( G , R \right) = \mathcal { M } \left( G , B \right) = 0 . 0 3 4 2 ; } \end{array} } \\ & { \begin{array} { r l } & { \mathcal { M } \left( R , B , G \right) = \mathcal { M } \left( R , G , B \right) = \mathcal { M } \left( \mathcal { B } , R , G \right) } \\ & { \mathcal { M } \left( R , B , G \right) = \mathcal { M } \left( R , G , B \right) = \mathcal { M } \left( \mathcal { B } , R , G \right) } \end{array} } \\ & { \begin{array} { r l } & { = \mathcal { M } \left( \mathcal { B } , G , R \right) = \mathcal { M } \left( \mathcal { B } , G , B \right) = \mathcal { M } \left( \mathcal { B } , R , G \right) } \\ & { \mathcal { M } \left( \mathcal { B } , G , R \right) = \mathcal { M } \left( G , \mathcal { B } , R \right) = \mathcal { M } \left( \mathcal { G } , R , B \right) = 0 . 1 2 8 2 . } \end{array} } \end{array}
$$

This example illustrate the PMF condition for maximum entropy of RPS. It can be seen in Eq. (29) that,with respect to the same cardinality of permutation event, the PMFs for that permutation events have the same value For example, the permutation events( $R$ )， $( B )$ ， $( G )$ are of the same value of cardinality. Their corresponding PMFs are the same, which is 0.0085.In addition,according to Eq. (29),the larger the cardinality of a certain permutation event,the larger the corresponding PMF is.

Example 4.2. Let α set of $N$ mutually exclusive and exhaustive elements be denoted by $\Theta = \{ \theta _ { 1 } , \theta _ { 2 } , . . . , \theta _ { N } \}$ .Based on $\Theta$ ，the sample space of maximum Shannon entropy， the power set of maximum Deng entropy，and the PES of maximum entropy of RPS can be respectively indicated by $\Theta$ ， $2 ^ { \Theta }$ ，and $P E S ( \Theta )$ . Hence， their corresponding maximum Shannon entropy $H _ { \mathrm { m a x } - S E }$ ， maximum Deng entropy $H _ { \mathrm { m a x } - D E }$ ， and maximum entropy of RPS $H _ { \mathrm { m a x } - R P S }$ （20 can be obtained:

$$
\begin{array} { r l } & { H _ { \operatorname* { m a x } } \boldsymbol { \mathrm { - } } S E = \log _ { 2 } \left( N \right) , } \\ & { H _ { \operatorname* { m a x } } \boldsymbol { \mathrm { - } } D E = \log _ { 2 } \left( \displaystyle \sum _ { A \in 2 ^ { \Theta } } ( 2 ^ { | A | } - 1 ) \right) , } \\ & { H _ { \operatorname* { m a x } } \boldsymbol { \mathrm { - } } R P S = \log _ { 2 } \left( \displaystyle \sum _ { i = 1 } ^ { N } [ P \left( N , i \right) \left( F \left( i \right) - 1 \right) ] \right) . } \end{array}
$$

With different value of $N$ ， the value of $H _ { \mathrm { m a x } - S E }$ ， $H _ { \mathrm { m a x } - D E }$ ，and $H _ { \mathrm { m a x } - R P S }$ （204号 can be calculated,which are shown in Table1 and Figure $\boldsymbol { \mathcal { Z } }$

This example shows that the trend of the maximum entropy of RPS changing with different value of $N$ . In addition,according to Figure 2,with respect to the same value of $N$ , the value of maximum entropy of RPS is larger than that of maximum Shannon entropy or maximum Deng entropy. This means that,with respect to the same number of samples of a certain set, the uncertainty of a RPS is larger than that of a power set or a sample space, since RPS takes permutation of a certain set into account while sample space and power set do not consider that.

Table 1: Maximum Shannon entropy,maximum Deng entropy, and maximum entropy of RPS with different $N$   

<html><body><table><tr><td>N</td><td>Hmax-SE</td><td>Hmax-DE</td><td>Hmax-RPS</td></tr><tr><td>1</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td>2</td><td>1.0000</td><td>2.3219</td><td>3.3219</td></tr><tr><td>3</td><td>1.5850</td><td>4.2479</td><td>6.8704</td></tr><tr><td>4</td><td>2.0000</td><td>6.0224</td><td>10.9278</td></tr><tr><td>5</td><td>2.3219</td><td>7.7211</td><td>15.5406</td></tr><tr><td>6</td><td>2.5850</td><td>9.3772</td><td>20.6691</td></tr><tr><td>7</td><td>2.8074</td><td>11.0077</td><td>26.2495</td></tr><tr><td>8</td><td>3.0000</td><td>12.6223</td><td>32.2231</td></tr><tr><td>9</td><td>3.1699</td><td>14.2266</td><td>38.5424</td></tr><tr><td>10</td><td>3.3219</td><td>15.8244</td><td>45.1699</td></tr></table></body></html>

Note:the logarithm is based on 2.

![](images/e7531b3201f834ce6a24f17d1be4e758dbf1c3e60f3945883dac80d670accb54.jpg)  
Fig.2: The trend of maximum Shannon entropy, maximum Deng entropy, and maximum entropy of RPS with different $N$ （204

Example 4.3.Given a fixed set of $N$ mutually exclusive and exhaustive elements $\Theta = \{ X , Y \}$ ，its corresponding PES is that

$$
P E S ( \Theta ) = \{ \emptyset , ( X ) , ( Y ) , ( X , Y ) , ( Y , X ) \}
$$

Based on this PES, the maximum entropy of RPS is calculated by:

$$
\begin{array} { l } { { \displaystyle H _ { \operatorname* { m a x } - R P S } = \log _ { 2 } \left( \sum _ { i = 1 } ^ { 2 } [ P \left( 2 , i \right) \left( F \left( i \right) - 1 \right) ] \right) } } \\ { { = \log _ { 2 } \left[ 2 * \left( 1 + 1 - 1 \right) + 2 * \left( 1 + 2 + 2 - 1 \right) \right] = 3 . 3 2 1 9 } } \end{array}
$$

in which $F ( i )$ is defined as $\begin{array} { r } { F ( i ) = \sum _ { k = 0 } ^ { i } P ( i , k ) } \end{array}$

Consider the following two scenarios:

· According to Y. Deng (2021)，if the order of the element in $P E S ( \Theta )$ isignored, $P E S ( \Theta )$ will degenerate into the power set: $\begin{array} { r l } { { 2 } ^ { \Theta } } & { { } = } \end{array}$ $\{ \emptyset , \ \{ X \} , \ \{ Y \} , \ \{ X , Y \} \}$ . Based on this power set， calculate the maximum Deng entropy

$$
\begin{array} { l } { { \displaystyle H _ { \operatorname* { m a x } - D E } = \log _ { 2 } \left( \sum _ { A \in 2 ^ { \Theta } } ( 2 ^ { | A | } - 1 ) \right) } } \\ { { \displaystyle \qquad = \log _ { 2 } \left[ 2 * \left( 2 ^ { 1 } - 1 \right) + 1 * \left( 2 ^ { 2 } - 1 \right) \right] = 2 . 3 2 1 9 } } \end{array}
$$

Besides，since the order of the element is ignored, the permutation number $P ( N , i )$ degenerates into combinatorial number $C ( N , i )$ ，and $F ( i )$ should be calculated as $\begin{array} { r } { F ( i ) = \sum _ { k = 0 } ^ { i } C ( i , k ) } \end{array}$ . Hence， the corresponding maximum entropy of RPS in this scenario can be detailed by:

$$
\begin{array} { c } { { H _ { \mathrm { m a x } - R P S } = \log _ { 2 } \left[ C \left( 2 , 1 \right) \left( F \left( 1 \right) - 1 \right) + C \left( 2 , 2 \right) \left( F \left( 2 \right) - 1 \right) \right] } } \\ { { = \log _ { 2 } \left[ 2 * \left( 1 + 1 - 1 \right) + 1 * \left( 1 + 2 + 1 - 1 \right) \right] = 2 . 3 2 1 9 } } \end{array}
$$

which is the same as $H _ { \mathrm { m a x } - D E }$ . As a result, if the order of the element in PES is ignored, the maximum entropy of RPS will degenerate into the maximum Deng entropy.

· According to Y. Deng (2021)，if each permutation event is limited to containing just one element, $P E S ( \Theta )$ will degenerate into the sample space in probability theory: $\Omega = \{ \{ X \} , \{ Y \} \}$ . Based on this sample space, calculate the maximum Shannon entropy:

$$
H _ { \operatorname* { m a x } { - S E } } = \log _ { 2 } { ( 2 ) } = 1
$$

Additionally， since permutation event is limited to containing just one element,the permutation number $P ( N , i )$ degenerates into

$$
\widetilde { P } \left( N , i \right) \triangleq \left\{ \begin{array} { l l } { 1 \ \left( i = 0 , N \geq 1 \right) } \\ { N \ \left( i = 1 , N \geq 1 \right) } \\ { 0 \ \left( o t h e r w i s e \right) } \end{array} \right.
$$

so that $F ( i )$ should be calculated as $\begin{array} { r } { F ( i ) = \sum _ { k = 0 } ^ { i } \tilde { P } ( i , k ) = i + 1 } \end{array}$ . Hence, the corresponding maximum entropy ofRPS in this scenario is that:

$$
\begin{array} { c } { { H _ { \mathrm { m a x } - R P S } = \log _ { 2 } \left[ \widetilde { P } \left( 2 , 1 \right) * \left( F \left( 1 \right) - 1 \right) + \widetilde { P } \left( 2 , 2 \right) * \left( F \left( 2 \right) - 1 \right) \right] } } \\ { { = \log _ { 2 } \left[ 2 * \left( 1 + 1 - 1 \right) + 0 * \left( 2 + 1 - 1 \right) \right] = 1 } } \end{array}
$$

which is the same as $H _ { \mathrm { m a x } - S E }$ . As a result, if each permutation event is limited to containing just one element， the maximum entropy of RPS degenerates into the maximum Shannon entropy.

This example shows that the maximum entropy RPS is compatible with the maximum Deng entropy and the maximum Shannon entropy.

# 5 Conclusion

Recently, Random permutation set (RPS) is proposed,which is a new kind of set considering all the permutation of elements in a certain set. The entropy of RPS is further presented for modeling the uncertainty of RPS.However, the maximum entropy principle of RPS entropy has not been discussed. To address this issue,in this paper, the maximum entropy of RPS is presented. The main contributions of this paper and some remarks on the maximum entropy of RPS are summarized as follows:

The analytical solution for maximum entropy of RPS and its PMF condition are respectively presented and proofed. Numerical examples are used to illustrate the maximum entropy RPS. The results show that the maximum entropy RPS is compatible with the maximum Deng entropy and the maximum Shannon entropy.   
When the order of the element in permutation event is ignored, the maximum entropy of RPS will degenerate into the maximum Deng entropy. When each permutation event is limited to containing just one element, the maximum entropy of RPS will degenerate into the maximum Shannon entropy.

Acknowledgments. The work is partially supported by National Natural Science Foundation of China (Grant No.61973332)；JSPS Invitational Fellowships for Research in Japan (Short-term).

# Declarations

· Funding: The work is partially supported by National Natural Science Foundation of China (Grant No. 61973332)； JSPS Invitational Fellowships for Research in Japan (Short-term). · Conflict of interest/Competing interests: All the authors certify that there is no conflict of interest with any individual or organization for this work.

Springer Nature 2021 IIEX template

· Ethics approval: This article does not contain any studies with human participants or animals performed by any of the authors.   
· Consent to participate: Informed consent was obtained from all individual participants included in the study.   
Consent for publication: The participant has consented to the submission of the case report to the journal.   
·Availability of data and materials: All data and materials generated or analysed during this study are included in this article.   
· Code availability: The code of the current study are available from the corresponding author on reasonable request.   
Authors’ contributions:All authors contributed to the study conception and design.All authors performed material preparation, data collection and analysis. Jixiang Deng wrote the first draft of the paper. All authors contributed to the revisions of the paper.All authors read and approved the final manuscript.

#

References   
Babajanyan, S., Allahverdyan,A., Cheong, K.H. (202O). Energy and entropy: Path from game theory to statistical mechanics.Physical Review Research，2(4),043055.   
Buckley, J.J.(2005).Maximum entropy principle with imprecise sideconditions. Soft Computing，9(7)，507-511.   
Chen,L.,& Deng,Y.(2021). Entropy of random permutation set.arXiv.   
Chen，X.，Wang,T.， Ying,R.,Cao, Z. (2021). A fault diagnosis method considering meteorological factorsfor transmission networks based on p systems.Entropy，23.   
Cheong,K.H., Koh, J.M., Jones,M.C. (2019). Paradoxical survival: Examining the parrondo effect across biology. BioEssays,41(6)，1900027.   
Dempster，A.P.(1967,O4). Upper and lower probabilities induced by a multivalued mapping. The Annals of Mathematical Statistics，38(2), 325-339.   
Deng,J.,& Deng,Y. (2021). Information volume of fuzzy membership function.International Journal of Computers Communications & Control,

Springer Nature 2021 IEX template

14 Maximum Entropy of Random Permutation Set 16(1), 4106. https://doi.org/10.15837/ijccc.2021.1.4106   
Deng,Y. (202Oa). Information volume of mass function. International Journal of Computers Communications & Control, 15(6), 3983.   
Deng,Y. (202Ob). Uncertainty measure in evidence theory. Science China Information Sciences, 63(11), 1-19.   
Deng,Y. (2021). Random permutation set. International Journal of Computers Communications& Control，Accepted.   
Di Nola,A., Dvurecenskij，A., Hycko,M.，Manara,C. (2005).Entropy on effect algebras with the riesz decomposition property i: Basic properties. Kybernetika, 41(2),143-160.   
Feng, G., Lu, W., Pedrycz, W., Yang, J., Liu, X. (2019). The learning of fuzzy cognitive maps with noisy data: A rapid and robust learning method with maximum entropy. IEEE transactions on cybernetics.   
Gao,Q., Wen, T., Deng, Y. (2021). Information volume fractal dimension. Fractals,DOI: 10.1142/S0218348X21502637.   
Gao,X., Su, X., Qian, H., Pan, X. (2021). Dependence assessment in Human Reliability Analysis under uncertain and dynamic situations. Nuclear Engineering and Technology,https://doi.org/10.1016/j.net.2021.09.045.   
Huang, Z., Wang, T., Liu, W., Valencia-Cabrera, L., Perez-Jimenez, M.J., Li, P.(202l).A fault analysis method for three-phase induction motors based on spiking neural p systems. Complexity, 2021.   
Jech,T. (2013). Set theory. Springer Science & Business Media.   
Lai, J.W., Chang, J., Ang,L.K., Cheong, K.H. (202O). Multi-level information fusion to alleviate network congestion. Information Fusion,63, 248-255.   
Lee,P. (198O). Probability theory. Bulletin of the London Mathematical Society,12(4),318-319.   
Liu, Z., Huang,L., Zhou, K., Denoeux, T. (2021). Combination of transferable classification with multisource domain adaptation based on evidential reasoning. IEEE Transactions on Neural Networks and Learning Systems，32(5),2015-2029.   
Liu,Z., Zhang,X.， Niu, J.，Dezert,J. (2021). Combination of classifers with different frames of discernment based on belief functions. IEEE Transactions on Fuzzy Systems, 29(7),1764-1774.   
Ma,G. (2021). A remark on the maximum entropy principle in uncertainty theory. Soft Computing，25(22)，13911-13920.   
Pan，Y.， Zhang,L.，Wu，X.， Skibniewski,M.J.(2020).Multi-classiffer information fusion in risk analysis. Information Fusion, 60,121-136. 10.1016/j.inffus.2020.02.003   
Pawlak, Z. (1982). Rough sets. International journal of computer £ information sciences, 11(5), 341-356.   
Shafer, G. (1976). A mathematical theory of evidence (Vol. 1). Princeton university press Princeton.   
Shannon, C.E. (1948). A mathematical theory of communication. Bell System Technical Journal, 27(4),379-423.   
Song, Y.,& Deng, Y. (2021). A possible explanation of power set in evidence theory.International Journal of Computers Communications & Control.   
Tsallis， C.(1988). Possible generalization of boltzmann-gibbs statistics. Journal of statistical physics, 52(1-2),479-487.   
Wang,H., Abdin, A.F., Fang, Y.-P., Zio, E. (2021). Resilience assessment of electrified road networks subject to charging station failures. ComputerAided Civil and Infrastructure Engineering.

Springer Nature 2021 IEX template

16 Maximum Entropy of Random Permutation Set https://doi.org/10.1111/mice.12736

Wang,H., Fang,Y.P., Zio,E. (202l). Risk assessment of an electrical power system considering the influence of traffic congestion on a hypothetical scenario of electrified transportation system in new york state. IEEE Transactions on Intelligent Transportation Systems, $\mathcal { Q } \mathcal { Q } ( 1 )$ ,142-155.

10.1109/TITS.2019.2955359

Wang，T.， Liu， W.， Zhao， J.，Guo，X.， Terzijae, V.(202O).A rough set-based bio-inspired fault diagnosis method for electrical substations. International Journal of Electrical Power & Energy Systems,119.

Wang, T., Wei, X., Wang, J., Huang, T., Peng,H., Song, X.,... Perez-Jimenez, M.J.(2O2O). A weighted corrective fuzzy reasoning spiking neural p system for fault diagnosis in power systems with variable topologies. Engineering Applications of Artificial Intelligence, 92.

Wen,T.,& Cheong,K.H.(2021).The fractal dimension of complex networks: Areview.Information Fusion，73,87-102.

Wen,Z., Liu, Z., Zhang, S., Pan,Q. (2021). Rotation awareness based selfsupervised learning for SAR target recognition with limited training samples.IEEE Transactions on Image Processing，30,7266-7279.

Wu,Q.,Deng,Y.,Xiong, N. (2021). Exponential negation of a probability distribution. Soft Computing,Accepted.

Xiao,F. (2Ol9). Multi-sensor data fusion based on the belief divergence measure of evidences and the belief entropy. Information Fusion，46, 23-32.

Xiao,F. (2O2O). Efmcdm:Evidential fuzzy multicriteria decision making based on belief entropy. IEEE Transactions on Fuzzy Systems，28(7) 1477-1491.

Xiao,F. (2021). CaFtR: A fuzzy complex event processing method. International Journal of Fuzzy Systems,DOI:10.1007/s40815-021-01118-6.

Springer Nature 2021 IIEX template

Xie,D.，Xiao,F.,Pedrycz，W.(2021). Information quality for intuitionistic fuzzy values with its application in decision making. Engineering Applications of Artificial Intelligence，Accepted.

Xue,Y.,& Deng,Y. (202la). Interval-valued belief entropies for Dempster Shafer structures. Soft Computing,25,8063-8071.   
Xue,Y.,& Deng,Y. (2021b). Tsallis extropy. Communications in StatisticsTheory and Methods,10.1080/03610926.2021.1921804.   
Yager, R.R. (20o9). Weighted maximum entropy owa aggregation with applications to decision making under risk. IEEE Transactions on Systems, Man，and Cybernetics-Part A:Systems and Humans，39(3),555-564.   
Yager,R.R. (2014). On the maximum entropy negation of a probability distribution. IEEE Transactions on Fuzzy Systems, 23(5),1899-1902.   
Zadeh,L.A. (1965). Fuzzy sets. Information and control, 8(3),338-353.   
Zadeh,L.A. (2011). A note on z-numbers. Information Sciences,181(14), 2923-2932.   
Zhou，Q.，& Deng，Y.(2021).Belief extropy:Measure uncertainty from negation. Communications in Statistics - Theory and Methods, 10.1080/03610926.2021.1980049.