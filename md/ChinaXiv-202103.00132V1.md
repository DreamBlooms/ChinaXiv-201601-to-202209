# CET: A New Complex Evidence Theory

Lipeng Pan $\mathbf { a }$ , Yong Denga,b,c, $*$

（204号 $a$ Institute of Fundamental and Frontier Science,University of Electronic Science and Technologyof China,Chengdu,610054，China （20 $b$ School of Education,Shannri Normal University, Xian,06,China $c$ School of Knowledge Science, Japan Advanced Institute of Science and Technology,Nomi, Ishikawa 923-1211,Japan

# Abstract

Dempster-Shafer evidence theory,as an extension of Probability theory, is wide ly used in the field of information fusion due to it satisfies weaker conditions than probability theory in dealing with uncertain information. Nevertheless ,the description space of the current evidence theory is only a real space,and it cannot effectively describe and process the uncertain information in the face of multidimensional characteristic data and periodic data with phase angle changes. Based on this gap ，in this paper,Dempster-Shafer evidence theory is extended to the complex Dempster-Shafer evidence theory. In complex Dempster-Shafer evidence theory,mass function that used to describe the uncertain information extends from the real space to the complex space,named as complex mass function,and the modulus of the mass function indicates the degree of support for the proposition. On this basis,other basic concepts used to describe uncertainty information are also defined and discussed, such as complex belief function, complex plausibility function,etc. In order to perfect the complex DempsterShafer evidence theory， the complex Dempster combination rule (CDCR） is supplemented. CDCR is an extension of Dempster combination rule (CDR), which satisfies the commutative and associative laws just as CDR does,and it can degenerate into CDR under certain condition. In addition，we propose a method to generate complex mass function and apply it to target recognition.

The recognized results show that compared with the mass function of the real plane, the target recognition rate can be larger by using complex mass function to describe the uncertain information.

Keywords: Dempster-Shafer evidence theory,complex Dempster-Shafer evidence theory,complex mass function,complex Dempster combination rule

# 1．Introduction

In nature,human cognition of things is often expressed through uncertain or imprecise information. In order to make this kind of cognitive expression more reasonable, scholars have developed many theories to describe and deal with un5certain or imprecise information, such as Probability theory[1],Dempster-Shafer evidence theory[2, 3]，Fuzzy set theory[4]，Atanassov's fuzzy set[5],entropybased[6,7] and etc[8]. On the one hand, scholars extend these theories to related theories, like evidence reasoning[9], fuzzy soft set[1O],information volume[11], interval Atanassov's fuzzy set[12],Pythagorean fuzzy set[13], mass function of 10 quantum[14] and other hybrid methods[15,16,17,18]. On the other hand,since above theories have their own advantages,researchers have applied them to a variety of fields such as target classification[19, 20,21,22， 23],cluster analysis[24，25，26,27，28]，medical diagnosis[29，30,31，32，33]，reliability analysis[34,35,36,37, 38],multi-criteria decision making[39,40, 41, 42,43] 15and other cross-application[44,45,46,47, 48].

Dempster-Shafer evidence theory as a mathematical tool for dealing with uncertain information,which is a generalization of Probability theory. Compared with Probability theory, evidence theory satisfies weaker uncertainty conditionS,and the multi-element expression of propositions shows that it has suficient 20 fault-tolerant ability. Dempster combination rule (DCR) can gradually improve the degree of support for the objective proposition and reduce the degree of support for the non-objective proposition. From the perspective of algebraic operations,DCR satisfies the commutative and associative laws of multiplication,which guarantees the stability and symmetry of algebraic operations. Due

25to these advantages,many decision theories have been extended and applied to various felds around the evidence theory. Whereas, it is found that the description of the uncertain information in the relevant theories of evidence theory is in the real number space,which leads to the lack of effective mathematical tools to describe and process the multidimensional characteristics of the uncertain infor  
30 mation.Furthermore,when the uncertain information is presented as periodic data of phase angle change, the existing description method cannot capture this change[49]. Consequently, the current research method has a gap that cannot be ignored when describing and processing uncertain information.

Hence,in this paper,we extend the evidence theory to the complex evidence 35theory. Specifically including the following contents,the description space of uncertain information expands from real space to complex space. Then,a new mass function is defined in the complex number plane, named as the complex mass function,and the support degree of the complex number mass function to the proposition is non-negative and normative. On this basis,some basic 40 concepts are also mapped from the real space to the complex space. For instance, complex belief function，complex plausibility function，etc.Moreover,a new combination rule is proposed in the complex plane,called complex Dempster combination rule (CDCR). CDCR inherits the advantages of DCR.It can not only gradually improve the support degree of the target proposition,but also 45satisfy the commutative law and associative law of multiplication,and ensure the stability and symmetry of CDCR in the complex plane.When the complex mass function degenerates to the classical mass function, CDCR degenerates to DCR. In addition, we propose a method to generate complex mass function. In the environment of complex evidence theory, complex mass function is applied 50to target recognition to improve the accuracy of target recognition.

The remain of the paper is structured as follows. The relevant knowledge of evidence theory is introduced in Section 2. Section 3 proposes the complex Dempster-Shafer evidence theory, and some numerical examples are given to explain it. In Section 4,we propose a method to generate complex mass function and apply it to target recognition. We summarize this work in Section 5.

# 2.Preliminaries

A brief review about Dempster-Shafer evidence theory is introduced in the section[2, 3].

Definition 1. (Frame of discernment)

60 Supposing there exists a positive definite non-empty set whose elements satisfy mutual exclusion $\boldsymbol \Theta = \{ \boldsymbol \theta _ { 1 } , \boldsymbol \theta _ { 2 } , \cdots , \boldsymbol \theta _ { n } \}$ ,then this set is a frame of discernment (FOD), its power set is described as follows:

$$
2 ^ { \Theta } = \left\{ \emptyset , \left\{ \theta _ { 1 } \right\} , \left\{ \theta _ { 2 } \right\} , \cdots , \left\{ \theta _ { n } \right\} , \left\{ \theta _ { 1 } , \theta _ { 2 } \right\} , \cdots , \Theta \right\}
$$

where $\mathcal { O }$ is called the empty set.

# Definition 2. (Mass function)

65 The mass function is used to indicate the degree of support for the proposition, it is defined as

$$
m : 2 ^ { \Theta } \to [ 0 , 1 ]
$$

which satisfies the following condition:

$$
m \left( \varnothing \right) = 0 a n d \sum _ { A \subseteq 2 ^ { \Theta } } m \left( A \right) = 1
$$

When $m \left( A \right) > 0$ ， $A$ is also called a focal element of the mass function, $m \left( A \right)$ indicates the degree of support for proposition $A$ ： $m \left( A \right)$ is also called the basic probability assignment function (BPA).

Definition 3. (Dempster combination rule)

There are two BPAs $m _ { 1 }$ and $m _ { 2 }$ in FOD $\Theta$ ，the Dempster combination rule $m _ { 1 } \oplus m _ { 2 }$ is formulated as follows:

$$
m \left( A \right) = \left\{ \begin{array} { r l r } { \frac { \sum _ { i , j : A _ { i } \cap B _ { j } = A } m _ { 1 } ( A _ { i } ) m _ { 2 } ( B _ { j } ) } { \sum _ { i , j : A _ { i } \cap B _ { j } \neq \emptyset } m _ { 1 } ( A _ { i } ) m _ { 1 } ( B _ { j } ) } } & { } & { A \neq \emptyset } \\ { 0 } & { } & { A = \emptyset } \end{array} \right.
$$

where $\begin{array} { r } { K = 1 - \sum _ { i , j : A _ { i } \cap B _ { j } \neq \emptyset } m _ { 1 } \left( A _ { i } \right) m _ { 1 } \left( B _ { j } \right) } \end{array}$ ， $K$ is a normalization constant, 75called conflict coefficient. $K \in [ 0 , 1 ]$ ， $K = 0$ shows that there is no conflict between $m _ { 1 }$ and $m _ { 2 }$ ，and $K = 1$ shows that there is complete conflict between $m _ { 1 }$ and $m _ { 2 }$ . Under normal circumstances, $0 \leq K < 1$ ：

# 3.Complex Dempster-Shafer evidence theory

In the section,we will introduce complex Dempster-Shafer evidence theory.

0 There is a frame of discernment $\mathbb { K } = \{ \kappa _ { 1 } , \kappa _ { 2 } , \cdot \cdot \cdot , \kappa _ { n } \}$ , the power set of $\mathbb { K }$ is described as follows:

$$
\mathfrak { Z } ^ { \mathbb { K } } = \left\{ \varnothing , \left\{ \kappa _ { 1 } \right\} , \left\{ \kappa _ { 2 } \right\} , \cdots , \left\{ \kappa _ { n } \right\} , \left\{ \kappa _ { 1 } , \kappa _ { 2 } \right\} , \cdots , \mathbb { K } \right\}
$$

The complex mass function on frame of discernment $\mathbb { K }$ is defined below:

Definition 4. (Complex mass function)

$$
| \mathbb { C M } | : 2 ^ { \mathbb { K } } \to [ 0 , 1 ]
$$

85 （204号 $| \mathbb { C } \mathbb { M } |$ is modulus of complex number CM,and satisfies

$$
\begin{array} { c } { \mathbb { C } \mathbb { M } \left( \varnothing \right) = 0 , } \\ { \mathbb { C } \mathbb { M } \left( A \right) = \mathbb { M } \left( A \right) e ^ { i \theta _ { A } } = x _ { A } + i y _ { A } } \\ { \displaystyle \sum _ { A \subseteq \mathbb { K } } \mathbb { M } \left( A \right) = \displaystyle \sum _ { A \subseteq \mathbb { K } } \sqrt { x _ { A } ^ { 2 } + y _ { A } ^ { 2 } } = 1 } \end{array}
$$

Obviously, $E q . 1 0$ is the equivalent of Euler's formula, the phase angle $\theta _ { A } = $ （204 $a r c t a n { \textstyle { \frac { y } { x } } }$ ，and $\theta _ { A } \in [ - \pi , \pi ]$ ． $\mathbb { M } \left( A \right)$ or $\sqrt { ( x _ { A } ^ { 2 } + y _ { A } ^ { 2 } ) }$ is represents how strongly 90this evidence supports the proposition $A$ ，not $x _ { A }$ .When $\theta _ { A } \ = \ 0$ ，complex mass function is degenerated to traditional mass function, $\mathbb { C M } \left( A \right)$ becomes a real number. The complex mass function is also known as the complex basic probability assignment function (CPBA). Now,a numerical example explains the difference between CPBA and BPA.

95

Example 3.1 Supposing that there is a CBPA $m$ in $\mathbb { K } = \{ \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \}$ =

$$
\begin{array} { r l } & { \mathbb { C } \mathbb { M } \left( \kappa _ { 2 } \right) = 0 . 4 8 3 2 + 0 . 1 2 4 2 i = 0 . 4 9 8 9 e ^ { i a r c t a n \frac { 0 . 1 2 4 2 } { 0 . 4 8 3 2 } } , } \\ & { \mathbb { C } \mathbb { M } \left( \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 2 4 0 3 + 0 . 1 5 2 9 i = 0 . 2 8 4 8 e ^ { i a r c t a n \frac { 0 . 1 5 2 9 i } { 0 . 2 4 0 3 } } , } \\ & { \mathbb { C } \mathbb { M } \left( \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 0 8 2 5 + 0 . 2 0 0 0 i = 0 . 2 1 6 3 e ^ { i a r c t a n \frac { 0 . 2 0 0 i } { 0 . 0 8 2 5 } } . } \end{array}
$$

Obviously, The supporting degree of evidence for propositions $\left\{ \kappa _ { 2 } \right\}$ ， $\{ \kappa _ { 2 } , \kappa _ { 3 } \}$ 100and $\{ \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \}$ are 0.4989, 0.2848 and O.2163 respectively. It is worth noting

that when $\theta = 0$ , the above three CBPAs degenerate into BPAS,but the support degree of the proposition remains the original value. For a BPA, the degree of support for a proposition corresponds to the way the proposition is expressed. For a CBPA, the degree of support for a proposition corresponds to a set of L05 expressions. This BPA is just one element of this set.This can be seen more clearly in Figure.1.

![](images/73ad84cb758821804a3e4c105ce2ab9d38a82e8aee6ef53fce7ff08388f99834.jpg)  
Figure 1:The relationship between BPA and CBPA

In complex evidence theory, there are some common functions,we define as follows:

Definition 5. (Complex belief function)

110

$$
C B e l \left( A \right) = \frac { \sum _ { B \subseteq A } \mathbb { C } \mathbb { M } \left( B \right) } { \left| \sum _ { C \subseteq \mathbb { K } } \mathbb { C } \mathbb { M } \left( C \right) \right| }
$$

Definition 6.(Complex plausibility function)

$$
C P l \left( A \right) = \frac { \sum _ { B \cap A \neq \emptyset } { \mathbb { C } \mathbb { M } \left( B \right) } } { \left| \sum _ { C \subseteq \mathbb { K } } { \mathbb { C } \mathbb { M } \left( C \right) } \right| }
$$

$| C B e l \left( A \right) |$ is the minimum support degree of evidence to proposition $A$ and $| C P l \left( A \right) |$ is the maximum support degree of evidence to proposition $A$ 15 Obviously, $\left| C B e l \left( A \right) \right| \le \left| C P l \left( A \right) \right|$ ,they form the upper and lower bounds of support degree $\left[ \left| C B e l \left( A \right) \right| , \left| C P l \left( A \right) \right| \right]$

Definition 7. (Complex Pignistic probability transformation) Pignistic probability transformation was proposed by Smet,which transformed

mass functions into probability distributions in the real number space[5O]. There120fore,we also transformed complex mass function into probability distribution through the following equation:

$$
B e t P \left( A \right) = \sum _ { B \subseteq \mathbb { K } } \frac { | A \cap B | } { | B | } \frac { | \mathbb { C } \mathbb { M } \left( B \right) | } { 1 - | \mathbb { C } \mathbb { M } \left( \varnothing \right) | } , \forall A \subseteq \mathbb { K }
$$

Let $\mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 2 }$ be are two CBPA on $\mathbb { K }$ ， $A _ { i }$ and $B _ { j }$ are subsets of $\mathbb { K }$ Thus,complex Dempster combination rule (CDCR) of $\mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 2 }$ is denoted $\mathbb { C } \mathbb { M } _ { 1 } \otimes \mathbb { C } \mathbb { M } _ { 2 }$ , it is defined as follows:

125 Definition 8. (Complex Dempster combination rule)

$$
\begin{array} { r } { \mathbb { C M } \left( A \right) = \left\{ \begin{array} { r l r } { \sum _ { i , j : A _ { i } \cap B _ { j } = A } \mathbb { C M } _ { 1 } ( A _ { i } ) \mathbb { C M } _ { 2 } ( B _ { j } ) } & { } & { A \neq \emptyset } \\ { \sum _ { i , j : A _ { i } \cap B _ { j } \neq \emptyset } | \mathbb { C M } _ { 1 } ( A _ { i } ) \mathbb { C M } _ { 1 } ( B _ { j } ) | } & { } & { A \neq \emptyset } \\ & { } & { 0 \quad A = \emptyset } \end{array} \right. } \end{array}
$$

In CDCR, $\begin{array} { r } { K \left( \mathbb { C } \mathbb { M } _ { 1 } , \mathbb { C } \mathbb { M } _ { 2 } \right) = 1 - \sum _ { i , j : A _ { i } \cap B _ { j } \not = \emptyset } \left| \mathbb { C } \mathbb { M } _ { 1 } \left( A _ { i } \right) \mathbb { C } \mathbb { M } _ { 1 } \left( B _ { j } \right) \right| } \end{array}$ and $K \in [ 0 , 1 ]$ , it denotes the degree of conflict between evidence.The bigger the $K$ value,the bigger the conflict degree,and the lower the credibility of the fusion results.In particular when $K = 1$ , there is something wrong with the evidence that cannot be ignored.In addition,for $\forall \ \mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 2 }$ ， $K \left( \mathbb { C } \mathbb { M } _ { 1 } , \mathbb { C } \mathbb { M } _ { 2 } \right)$ has some properties as follows:

$\mathbf { P ( 1 ) }$ :Nonnegativity, $K \left( \mathbb { C } \mathbb { M } _ { 1 } , \mathbb { C } \mathbb { M } _ { 2 } \right) \leq 0$ $\mathbf { P } ( \mathbf { 2 } )$ :Symmetry, $K \left( \mathbb { C } \mathbb { M } _ { 1 } , \mathbb { C } \mathbb { M } _ { 2 } \right) = K \left( \mathbb { C } \mathbb { M } _ { 2 } , \mathbb { C } \mathbb { M } _ { 1 } \right)$ $\mathbf { P ( 3 ) }$ :Bounded. $0 \leq K \left( \mathbb { C } \mathbb { M } _ { 1 } , \mathbb { C } \mathbb { M } _ { 2 } \right) \leq 1$

135

Example 3.2 Supposing that there are two CBPAs $\mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 2 }$ in $\mathbb { K } =$ $\{ \kappa _ { 1 } , \kappa _ { 2 } \}$ ，we express $\mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 2 }$ as follows:

$$
\begin{array} { r l } & { \mathbb { C } \mathbb { M } _ { 1 } \left( \kappa _ { 1 } \right) = \rho e ^ { i \theta } , \mathbb { C } \mathbb { M } _ { 1 } \left( \kappa _ { 2 } \right) = \left( 1 - \rho \right) e ^ { i \left( \frac { \pi } { 2 } - \theta \right) } . } \\ & { \mathbb { C } \mathbb { M } _ { 2 } \left( \kappa _ { 1 } \right) = \left( 1 - \rho \right) e ^ { i \left( \frac { \pi } { 2 } - \theta \right) } , \mathbb { C } \mathbb { M } _ { 1 } \left( \kappa _ { 2 } \right) = \rho e ^ { i \theta } . } \end{array}
$$

140 where $\rho \in [ 0 , 1 ]$ ， $\theta \ \in \ \left\lfloor - \frac { \pi } { 2 } , \frac { \pi } { 2 } \right\rfloor$ .Then， the calculation results of conflict coefficient $K$ are shown in Figure 2. As can be seen from the Figure.2,when （204号 $\rho = 0$ or $\rho = 1$ ， for any $\theta$ ， $K$ is always going to be 1. When $\rho ~ = ~ 0 . 5$ and （204号 $\theta = 0 . 1 4 9 2$ ,then $K = 0 . 5$ ：

![](images/4a7835718c22e5db4d91a1a7008594f10f166fcbda650a36d8cb2670d3b00ca8.jpg)  
Figure 2:The conflict coefficient $K$ in Example 3.2

Example 3.3 Exist two CBPAs $\mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 2 }$ in $\mathbb { K } = \{ \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \}$ are 45 described as follows:

CM1: $\mathbb { C } \mathbb { M } _ { 1 } \left( \kappa _ { 2 } \right) = 1$   
CM $\begin{array} { r } { \mathrm { I _ { 2 } } \colon \mathbb { C } \mathbb { M } _ { 2 } \left( \kappa _ { 2 } \right) = 0 . 4 9 2 1 + 0 . 0 7 3 9 i } \end{array}$ $\mathbb { C } \mathbb { M } _ { 2 } \left( \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 2 9 3 7 + 0 . 0 9 8 2 i$ $\mathbb { C } \mathbb { M } _ { 2 } \left( \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 1 3 4 4 + 0 . 1 3 8 1 i .$ （204号

150 In this example, the $K$ is 0.0289, if we change $\mathbb { C } \mathbb { M } _ { 2 }$ to $\mathbb { C } \mathbb { M } _ { 2 } \left( \kappa _ { 2 } \right) = 1$ ,，under this condition, the calculation result of $K$ is $0$ , if by Dempster-Shafer evidence theory analysis, the $K$ is $0$ in both cases.Obviously, the conflict coefficient $K$ in the complex evidence theory has a stricter requirement on the expression form of CBPAs.

Example 3.4 Supposing there are four CBPA on the frame of discernment （204号 $\mathbb { K } = \{ \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \}$ , they are described as follows:

$\mathbb { C } \mathbb { M } _ { 1 } \colon \mathbb { C } \mathbb { M } _ { 1 } \left( \kappa _ { 1 } \right) = 0 . 7 7 6 5 + 0 . 0 0 0 9 i ,$ $\mathbb { C } \mathbb { M } _ { 1 } \left( \kappa _ { 1 } , \kappa _ { 2 } \right) = 0 . 0 7 5 6 + 0 . 0 6 7 4 i$ $\mathbb { C } \mathbb { M } _ { 1 } \left( \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 0 4 6 4 + 0 . 1 1 3 0 i ;$ （20  
$\mathbb { C } \mathbb { M } _ { 2 } \colon \mathbb { C } \mathbb { M } _ { 2 } \left( \kappa _ { 2 } \right) = 0 . 5 9 0 0 - 0 . 0 0 6 8 i _ { \mathrm { ~ } }$ $\mathbb { C } \mathbb { M } _ { 2 } \left( \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 4 0 9 1 + 0 . 0 2 6 3 i$

165

$\mathbb { C } \mathbb { M } _ { 3 } \colon \mathbb { C } \mathbb { M } _ { 3 } \left( \kappa _ { 2 } \right) = 0 . 5 4 3 0 - 0 . 0 1 7 7 i ,$ （204 $\mathbb { C } \mathbb { M } _ { 3 } \left( \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 4 5 6 4 + 0 . 0 1 6 6 i$   
$\begin{array} { r } { \Sigma \mathbb { M } _ { 4 } \colon \mathbb { C } \mathbb { M } _ { 4 } \left( \kappa _ { 2 } \right) = 0 . 5 5 8 0 + 0 . 0 2 8 7 i , } \end{array}$ （202 $\mathbb { C } \mathbb { M } _ { 4 } \left( \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 3 4 2 5 + 0 . 0 6 4 9 i$ $\mathbb { C } \mathbb { M } _ { 4 } \left( \kappa _ { 1 } , \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 0 9 1 0 + 0 . 0 1 7 7 i .$ （20   
Then, $\mathbb { C } \mathbb { M } _ { 1 } \bigoplus \mathbb { C } \mathbb { M } _ { 2 } \bigoplus \mathbb { C } \mathbb { M } _ { 3 } \bigoplus \mathbb { C } \mathbb { M } _ { 4 }$ is calculated as follows:   
$\mathbb { C } \mathbb { M } \left( \kappa _ { 2 } \right) = 0 . 4 4 1 7 + 0 . 8 4 5 2 i$   
$\mathbb { C } \mathbb { M } \left( \kappa _ { 2 } , \kappa _ { 3 } \right) = 0 . 0 0 4 7 + 0 . 0 4 6 1 i$

170 In the combined results, $| \mathbb { C } \mathbb { M } \left( \kappa _ { 2 } \right) | + | \mathbb { C } \mathbb { M } \left( \kappa _ { 2 } , \kappa _ { 3 } \right) | = 1$ . In addition, the support degree of $\kappa _ { 2 }$ is the biggest, $| \mathbb { C } \mathbb { M } \left( \kappa _ { 2 } \right) | = 0 . 9 5 3 7$ ,it is a non-counterintuitive result .

# 4. The generation method and application of complex mass function

In this section,we propose the generation method of complex mass func175tion. In addition,we apply the generated complex mass function to the target recognition of the iris dataset.

![](images/9f33cd5a34a485da0a83be379b3e24436de7683a3b14dd94a0898fd30120bbe9.jpg)  
Figure 3:The generation method of Complex mass function

Methods Described: Supposing there are N targets, denoted as $\{ C l a s s 1 , C l a s s 2 , \cdot \cdot \cdot , C l a s s j , \cdot \cdot \cdot , C l a s s N \} ,$ each target has $K$ attributes, represented as $\{ A t t r i b u t e 1 , A t t r i b u t e 2 , \cdot \cdot \cdot , A t t r i b u t e i , \cdot \cdot \cdot , A t t r i b u t e K \} .$ （20 Thus,we can use the process shown in Figure.3 to generate the complex mass 180functions for the jth attribute.

· Step 1: Select the training set and test set from the original data set.   
· Step 2: N class correspond to $2 ^ { N } - 1$ propositions，denoted as $\mathbb { N } \ =$ $\{ C a l s s _ { 1 } , C a l s s _ { 2 } , \cdot \cdot \cdot , C a l s s _ { 1 2 } , \cdot \cdot \cdot , C a l s s _ { 1 , } . . . , N \}$ ，where $C a l s s _ { 1 2 }$ is the union of $C a l s s _ { 1 }$ and $C a l s s _ { 2 }$ . Calculating the mean $\mu _ { p } ^ { j }$ and standard deviation $\delta _ { p } ^ { j }$ of pth proposition.   
· Step 3: Select an unknown target from the test set and add it to the training set,and calculate the mean $\mu _ { p } ^ { j ^ { \prime } }$ and standard deviation $\delta _ { p } ^ { j ^ { \prime } }$ of the pth proposition again.   
· Step 4: The complex mass function of the pth proposition is generated by the following equation:

$$
\mathbb { C } \mathbb { M } _ { j } \left( \boldsymbol { C } l a s s _ { p } \right) = \left( \frac { 1 } { e ^ { \left| \delta _ { p } ^ { j ^ { \prime } } - \delta _ { p } ^ { j } \right| } } \right) e ^ { i \left( \mu p ^ { j ^ { \prime } } - \mu _ { p } ^ { j } \right) } = \left( \frac { 1 } { e ^ { \left| \triangle \delta _ { p } ^ { j } \right| } } \right) e ^ { i \left( \triangle \mu _ { p } ^ { j } \right) }
$$

Experimental verification: we selected Iris data set, Seed data set and Banknote data set, Blood Transfusion Service Center data set (BTSC) and Fertility $-$ Diagnosis data set from UCI database (http://archive.ics.uci.edu/ml/index.php) for experiments. The details are shown in Table 1. 6O% of the data from each kind 195 of data set is randomly selected as the training set and the rest as the test set.We conducted 1O0 experiments,and the results are shown in Figure.4.As can be seen from Figure.4, compared with the mass function in the real number plane[51], the description of uncertain information by complex mass function can improve the accuracy of target recognition,which indicates that the description 200 of uncertain information by complex mass function is more reasonable.

Algorithm 1 :Generation of complex mass functions

Input: Training set and test set /\* They all have n classes,each class has k attributes. \*/

Output:Complex Mass Functions for the test set

1: for $j = 1  k$ do   
2: for $p = 1 \to 2 ^ { N } - 1$ do   
3: （204 $\begin{array} { r l } & { \mathrm { C a l c u l a t i n g ~ } \delta _ { p } ^ { j } , \mu _ { p } ^ { j } , \delta _ { p } ^ { j ^ { ' } } , \mu p ^ { j ^ { ' } } . } \\ & { \triangle \delta _ { p } ^ { j } = \delta _ { p } ^ { j ^ { ' } } - \delta _ { p } ^ { j } , \triangle \mu _ { p } ^ { j } = \mu p ^ { j ^ { ' } } - \mu _ { p } ^ { j } } \\ & { \mathbb { C } \mathbb { M } _ { j } \left( C l a s s _ { p } \right) = \left( \frac { 1 } { e \left| \triangle \delta _ { p } ^ { j } \right| } \right) e ^ { i \left( \triangle \mu _ { p } ^ { j } \right) } } \end{array}$   
4:   
5:   
6: end for   
7: return $\mathbb { C } \mathbb { M } _ { j }$ （204号   
8: end for

Table1:The details of the datasets   

<html><body><table><tr><td>Dataset</td><td>Instance</td><td>Class</td><td>Attribute</td><td>AttrDist</td><td>Missing value</td></tr><tr><td>Iris</td><td>150</td><td>3</td><td>4</td><td>4R</td><td>No</td></tr><tr><td>Seeds</td><td>210</td><td>3</td><td>7</td><td>7R</td><td>No</td></tr><tr><td>Banknote</td><td>1372</td><td>2</td><td>4</td><td>4R</td><td>No</td></tr><tr><td>BTSC</td><td>748</td><td>2</td><td>4</td><td>4R</td><td>No</td></tr><tr><td>Fertility_Diagnosis</td><td>100</td><td>2</td><td>9</td><td>4R5I</td><td>No</td></tr></table></body></html>

![](images/12063bb2f8f253cac8646d750bdce10d855afe0c55b84d428cf6b3bc1181d9d4.jpg)  
Figure 4: The target recognition accuracy based on mass functions in real plane and complex plane

# 5.Conclusion

In order to describe the uncertain information of multi-dimensional features, we extend the Dempster-Shafer evidence theory from the real number space to the complex number space,and propose the complex Dempster-Shafer evidence   
205 theory. Under the framework of complex Dempster-Shafer evidence theory, we define complex mass function，complex belief function and etc. Meanwhile, we also propose the complex Dempster combinatorial rule,which satisfies the commutative law of multiplication.When complex mass function degenerates into traditional mass function,complex Dempster combination rule will also   
210 degenerate into Dempster combination rule in real space. Then,we proposed a method to generate complex mass function based on the mean and variance changes of sample data. The results show that compared with the mass function in the real number space,the complex mass function can effectively improve the target recognition rate under the framework of complex evidence theory. In sub  
215 sequent work,we will explain complex Dempster-shafer evidence theory from an algebraic perspective,which will help to perfect the theoretical basis of complex Dempster-shafer evidence theory, and we will also apply complex Dempstershafer evidence theory to target classification,cluster analysis,intelligent decision making and other fields to deal with more practical problems.In addition,

220 complex probability is related to the description of quantum system[52, 53],so we will use complex evidence theory to further solve some problems of quantum system,such as entanglement effect, interference effect and etc.

# Declaration of competing interest

The authors declare that they have no known competing financial interests or 225personal relationships that could have appeared to influence the work reported in this paper.

# Acknowledgment

The work is partially supported by National Natural Science Foundation of China (Grant Nos. 61973332)，JSPS Invitational Fellowships for Research in 230 Japan (Short-term).

# References

[1] M.Loeve,Probability theory ii, Graduate texts in mathematics 46 (1978) 15. [2] A.P.Dempster, et al., Upper and lower probabilities generated by a random   
235 closed interval, The Annals of Mathematical Statistics 39 (3)(1968) 957- 966. [3] G. Shafer,A mathematical theory of evidence, Vol. 42,Princeton university press,1976. [4] L.A. Zadeh, Fuzzy sets,Information and control 8(3)(1965) 338-353.   
240 [5] K.T.Atanassov, Intuitionistic fuzzy sets,Vol. 20, Springer, 1986,pp.87- 96. [6] Y.Deng,Uncertainty measure in evidence theory, SCIENCE CHINA Information Sciences 64 (2021) 10.1007/s11432-020-3006-9. [7] J.Deng,Y. Deng, Information volume of fuzzy membership function, In  
245 ternational Journal of Computers Communications & Control 16 (1) (2021) 4106.doi:https://doi.org/10.15837/ijccc.2021.1.4106. [8] Z.Pawlak, Rough sets,International journal of computer & information sciences 11 （5) (1982) 341-356. [9] X. Xu, J. Zheng, J.-b. Yang, D.-1. Xu, Y.-w. Chen, Data classification using   
250 evidence reasoning rule, Knowledge-Based Systems 116 (2017) 144-151. [10] P. Maji, R. Biswas,A. Roy, Fuzzy soft set theory, The Journal of Fuzzy Mathematics 3（9)(2001) 589-602. [11] Y. Deng, Information volume of mass function, International Journal of Computers Communications & Control 15 (6) (2020) 3983. doi:https:   
255 //doi.org/10.15837/ijccc.2020.6.3983. [12] K. T.Atanassov,Interval valued intuitionistic fuzzy sets, in: Intuitionistic Fuzzy Sets, Springer,1999,pp. 139-177. [13] R.R. Yager, Pythagorean fuzzy subsets, in: 2O13 joint IFSA world congress and NAFIPS annual meeting (IFSA/NAFIPS), IEEE, 2013,pp. 57-61.   
260[14] X. Gao,Y.Deng, Quantum model of mass function, International Journal of Intelligent Systems 35(2) (2020) 267-282. [15] W. Jiang, Y. Cao, X. Deng,A novel z-network model based on bayesian network and z-number, IEEE Transactions on Fuzzy Systems. [16] D. Dubois, F. Faux, H. Prade,A. Rico,A possibilistic counterpart to shafer   
265 evidence theory, in: 2019 IEEE International Conference on Fuzzy Systems (FUZZ-IEEE), IEEE, 2019, pp.1-6. [17] P. Liu, X. Zhang,W. Pedrycz, A consensus model for hesitant fuzzy linguistic group decision-making in the framework of dempster-shafer evidence theory, Knowledge-Based Systems 212(2021） 106559.   
270[18] X. Gao, L. Pan, Y. Deng, Quantum Pythagorean Fuzzy Evidence Theory (QPFET): A Negation of Quantum Mass Function View, IEEE Transactions on Fuzzy Systems (2021) 10.1109/TFUZZ.2021.3057993. [19] Z.-g. Liu, L.-q. Huang,K. Zhou,T. Denoeux,Combination of transferable classification with multisource domain adaptation based on evidential   
275 reasoning., IEEE Transactions on Neural Networks and Learning Systems. [20] L. Chen, Y. Feng, M. A. Maram, Y. Wang, M. Wu, K. Hirota, W. Pedrycz, Multi-svm based dempster-shafer theory for gesture intention understanding using sparse coding feature, Applied Soft Computing 85 (2019) 105787. [21] O.Castillo,P. Melin,A novel method for a covid-19 classification of coun  
280 tries based on an intelligent fuzzy fractal approach,in: Healthcare, Vol. 9, Multidisciplinary Digital Publishing Institute, 202l, p. 196. [22] P. Ducange, F. Marcelloni, R. Pecori, Fuzzy hoeffding decision tree for data stream classification, International Journal of Computational Intelligence Systems.   
285[23] P. Roy, C. Chowdhury, M. Kundu, D. Ghosh, S. Bandyopadhyay, Novel weighted ensemble classifier for smartphone based indoor localization, Expert Systems with Applications 164 (2021) 113758. [24] J. Zhao, Y. Deng, Complex network modeling of evidence theory, IEEE Transactions on Fuzzy Systems (2020) 10.1109/TFUZZ.2020.3023760.   
290[25] I.-D.Borlea,R.-E. Precup,A.-B.Borlea，D. Iercan，A unified form of fuzzy c-means and k-means algorithms and its partitional implementation, Knowledge-Based Systems 214 (2021）106731. [26] H.Abdellahoum,N.Mokhtari，A.Brahimi,A. Boukra,Csfcm: An improved fuzzy c-means image segmentation algorithm using a cooperative   
295 approach, Expert Systems with Applications 166 (2021） 114063. [27] S. Askari, Fuzzy c-means clustering algorithm for data with unequal cluster sizes and contaminated with noise and outliers: Review and development, Expert Systems with Applications 165(2021） 113856. [28] F. Fanian,M. K. Rafsanjani, A. B. Saeid, Fuzzy multi-hop clustering pro  
300 tocol: Selection fuzzy input parameters and rule tuning for wsns, Applied Soft Computing 99 （2021） 106923. [29] A. Janghorbani,M.H. Moradi, Fuzzy evidential network and its application as medical prognosis and diagnosis models,Journal of biomedical informatics 72 (2017) 96-107.   
305[30] L. Pan，X.Gao,Y. Deng,K.H. Cheong，The constrained Pythagorean fuzzy sets and its similarity measure , IEEE Transactions on Fuzzy Systems (2021） 10.1109/TFUZZ.2021.3052559. [31] T. Mahmood, U. Ur Rehman, Z. Ali, T. Mahmood, Hybrid vector similarity measures based on complex hesitant fuzzy sets and their applications to   
310 pattern recognition and medical diagnosis, Journal of Inteligent & Fuzzy Systems (Preprint）(2020)1-22. [32] J. S. Chai, G. Selvachandran, F. Smarandache, V. C. Gerogiannis, Q.-T. Bui,B.Vo,et al., New similarity measures for single-valued neutrosophic sets with applications in pattern recognition and medical diagnosis prob  
315 lems,Complex & Intelligent Systems (2020) 1-21. [33] M.U. Molla,B.C.Giri, P. Biswas,Extended promethee method with pythagorean fuzzy sets for medical diagnosis problems, Soft Computing (2021) 1-10. [34] C.-l. Fan, Y. Song,L. Lei, X. Wang, S. Bai, Evidence reasoning for tem  
320 poral uncertain information based on relative reliability evaluation,Expert Systems with Applications 113(2018) 264-276. [35] R. Palm，A. Lilienthal, Gaussian noise and the intersection problem in human-robot systems-analytical and fuzzy approach, in: 2019 IEEE In

ternational Conference on Fuzzy Systems (FUZZ-IEEE), IEEE, 2019, pp. 325 1-6. [36] G. Liu, F. Xiao, C.-T. Lin, Z. Cao,A fuzzy interval time-series energy and financial forecasting model using network-based multiple time-frequency spaces and the induced-ordered weighted averaging aggregation operation, IEEE Transactions on Fuzzy Systems 28 (11） (2020) 2677-2690. doi: 330 10.1109/TFUZZ.2020.2972823. [37] S. Cobos-Guzman，E. Verdu, E. Herrera-Viedma, R. G. Crespo， Fuzzy logic expert system for selecting robotic hands using kinematic parameters, Journal of Ambient Intelligence and Humanized Computing 11 (4) (2020) 1553-1564. 335[38] H. Zhang, Y. Dong, J. Xiao,F. Chiclana,E. Herrera-Viedma, Consensus and opinion evolution-based failure mode and efect analysis approach for reliability management in social network and uncertainty contexts,Reliability Engineering & System Safety 208（2021） 107425. [39] M. Couceiro, D. Dubois, H. Prade,T. Waldhauser,Decision-making with 340 sugeno integrals, Order 33 (3) (2016) 517-535. [40] P. Wang, P. Liu, F. Chiclana, Multi-stage consistency optimization algorithm for decision making with incomplete probabilistic linguistic preference relation,Information Sciences. [41] L. Fan, J. Spirkova, R. Mesiar, R. R. Yager, L. Jin, Multi-criteria fuzzy 345 comprehensive evaluation in interval environment with dual preferences, Journal of Intelligent & Fuzzy Systems (Preprint) (2020)1-9. [42] J. P. Amezquita-Sanchez, N. Mammone, F. C. Morabito, H. Adeli, A new dispersion entropy and fuzzy logic system methodology for automated classification of dementia stages using electroencephalograms, Clinical Neurol350 ogy and Neurosurgery 201 （2021） 106446.

[43] I. Bueno,R.A. Carrasco, C.Porcel, G. Kou, E. Herrera-Viedma,A linguistic multi-criteria decision making methodology for the evaluation of tourist services considering customer opinion value,Applied Soft Computing 101 (2021) 107045.   
355[44] H. Seiti， A. Hafezalkotob,R. Fattahi, Extending a pessimistic-optimistic fuzzy information axiom based approach considering acceptable risk: Application in the selection of maintenance strategy, Applied Soft Computing 67 (2018) 895-909. [45] Z. Cao, C.-T. Lin, K.-L. Lai, L.-W. Ko, J.-T. King, K.-K. Liao, J.-L. Fuh,   
360 S.-J. Wang, Extraction of SSVEPs-based Inherent Fuzzy Entropy Using a Wearable Headband EEG in Migraine Patients, IEEE Transactions on Fuzzy Systems (2019) DOI: 10.1109/TFUZZ.2019.2905823. [46] V. F. Wasques,E. Esmi, L. C. Barros,P. Sussner, Numerical solution for fuzzy initial value problems via interactive arithmetic: Application to chem  
365 ical reactions, International Journal of Computational Intelgence Systems 13(1)(2020) 1517-1529. [47] S.D. L. R. De Sáa, M. A. Lubiano,B. Sinova,P. Filzmoser,M. A.Gil, Location-free robust scale estimates for fuzzy data,IEEE Transactions on Fuzzy Systems.   
370[48] E. Lughofer, Improving the robustness of recursive consequent parameters learning in evolving neuro-fuzzy systems, Information Sciences 545 (2021) 555-574. [49] F. Xiao, Generalized belief function in complex evidence theory, Journal of Intelligent & Fuzzy Systems (Preprint) (2020)1-9.   
375[50] P. Smets,R. Kennes,The transferable belief model,Artificial intelligence 66 (2）(1994） 191-234.

[51] P.Xu, Y. Deng,X. Su, S. Mahadevan,A new method to determine basic probability assignment from training data,Knowledge-Based Systems 46 (2013) 69-80. 380 [52] J.W. Lai, K.H. Cheong, Parrondo effect in quantum coin-toss simulations, Physical Review E 101 (5)(2020) 052212. [53] J. W. Lai,K. H. Cheong, Parrondos paradox from classical to quantum: A review, Nonlinear Dynamics 100(1)(2020) 849-861.