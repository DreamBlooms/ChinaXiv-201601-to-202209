# Complex-valued Deng Entropy

Lipeng Pana, Yong Denga,b,c,d,\*

$a$ InstituteofFundamentalandFrontier Science,Unioersityof Electronic Scienceand TechnologyofChina, Chengdu,610054,China bSchoolofducation,hanni Normalniersity,i'an,6in School ofKnowledgeScience,Japan Aduanced InstituteofScienceand Technology,Nomi,Ishikawa 923-1211,Japan dDepartmentofanagement,Technology,andEconomics,ETHZrich,Zurich,witzrld

# Abstract

Complex evidence theory has been applied to several fields due to its advantages in modeling and processing uncertain information. However,to measure the uncertainty of the complex mass function is still an open issue. The main contribution of this paper is to propose a complex-valued Deng entropy. The complex-valued Deng entropy can effectively measure the uncertainty of the mass function in the complex-valued framework. Meanwhile, the complex valued Deng entropy is a generalization of the Deng entropy and Shannon entropy. That is, the complex-valued Deng entropy can degenerate to classical Deng entropy when the complex-valued mass function degenerates to a mass function in real space. In addition, the proposed complex-valued Deng entropy can also degenerates to Shannon entropy when the complex-valued mass function degenerates to a probability distribution in real space. Some numerical examples demonstrate the compatibility and effectiveness of the complex-valued Deng entropy.

Keywords: complex-valued mass function, Deng entropy, complex-valued Deng entropy, Shannon entropy, uncertain information

# 1. Introduction

How to model and process uncertain information has received increasing attention,and a number of theories have been developed, such as probability theory[1], fuzzy set [2], intuitionistic fuzzy set[3], pythagorean fuzzy set[4], 5and rough sets[5]. Among these theories, probability theory is fundamental to most theoretical studies and practical applications[6,7, 8, 9]. Faced with complex problems, probability is extended from real to complex spaces. For example,researchers introduced complex-valued probability into quantum mechanics and quantum game theory to describe interference phenomena[10,11].

10 Moreover,as another extension of probability theory, the Dempster-Shafer evidence theory[12,13], it also has own advantages,the support degree of propositions in evidence theory is not point estimation but interval estimation,and the support degree of correct propositions is further improved after Dempater combination rule. These advantages lead to the wide application   
15 of evidence theory in the fields of decision making[14,15],risk analysis[16], pattern recognition[17], target clustering[18] and other hybrid[19, 20]. Recently, Pan and Deng proposed a complex-valued evidence theory by introducing the phase angle into the mass function,and defined the Dempater combination rule in the complex-valued framework[21]. In the frame  
20 work of complex-valued evidence theory, it is experimentally demonstrated based on the data set that the complex-valued mass function is more reasonable for modeling uncertain information. This work promotes the application of complex-valued evidence theory in engineering,however there is no mention of uncertainty measurements of complex-valued mass functions in complex  
25 valued evidence theory. Therefore, to reasonably measure the uncertainty of the complex-valued mass function is still an open issue.

In this paper, we propose a generalized Deng entropy, named as complexvalued Deng entropy, which fully considers the effect of phase angle in support

and can effectively measure the uncertainty for the complex-valued mass func30tion. Concurrently, it is compatible with classical Deng entropy and Shannon entropy, i.e,when the complex-valued mass function degenerates to a realvalued mass function, the complex-valued Deng entropy degenerates to classical Deng entropy or Shannon entropy. Some numerical examples explain the compatibility and effectiveness of the complex-valued Deng entropy.

35 The remaining work is organized as follows. Section 2 introduces the knowledge of the complex-valued mass function and Deng entropy. Complex-valued Deng entropy is presented in section 3. In section 4, some numerical examples to explain the compatibility and effectiveness of complex-valued Deng entropy are presented. Section 5 summarizes the work.

# 40 2.Preliminaries

In the section, The related concepts of complex-valued mass function and Deng entropy are introduced.

# 2.1. Complex-valued mass function

45 In this subsection, we introduce the concept of complex-valued mass function and mass function,and the relationship between them.

Definition II.1 (Frame of discernment)[12,13]

Suppose there exists a positive definite,non-negative,mutually exclusive set （20 ${ \mathbb { E } = \left\{ E _ { 1 } , E _ { 2 } , \cdot \cdot \cdot , E _ { j } , \cdot \cdot \cdot , E _ { n } \right\} } _ { }$ , denoted as frame of discernment, whose power set is described as follows:

$$
\mathfrak { z } ^ { \mathbb { E } } = \left\{ \varnothing , \left\{ E _ { 1 } \right\} , \left\{ E _ { 2 } \right\} , \cdot \cdot \cdot , \left\{ E _ { n } \right\} , \left\{ E _ { 1 } , E _ { 2 } \right\} , \cdot \cdot \cdot , \mathbb { E } \right\}
$$

Definition II.2 (Complex-valued mass function)[21] There exists a mapping function from $2 ^ { \mathbb { E } }$ to [0,1] that

$$
\left| \mathbb { C } \mathbb { M } \right| : 2 ^ { \mathbb { E } } \to [ 0 , 1 ]
$$

where $| \mathbb { C } \mathbb { M } |$ is modulo of the complex-valued CM. CM satisfies that

$$
\mathbb { C } \mathbb { M } \left( \varnothing \right) = 0 ,
$$

$$
\mathbb { C } \mathbb { M } \left( A \right) = \mathbb { M } \left( A \right) e ^ { i \pi \theta _ { A } } = x _ { A } + i y _ { A }
$$

55

$$
\sum _ { A \subseteq \mathbb { K } } \mathbb { M } \left( A \right) = \sum _ { A \subseteq \mathbb { K } } \sqrt { x _ { A } ^ { 2 } + y _ { A } ^ { 2 } } = 1
$$

$\mathbb { C } \mathbb { M } \left( A \right)$ is the form of Euler's formula, $\mathbb { C } \mathbb { M } \left( A \right)$ is the support degree for the proposition, named as complex-valued mass function, and $\pi \theta _ { A }$ is the phase angle, satisfying the $\pi \theta _ { A } \in [ - \pi , \pi ] .$ ,that is, $\theta _ { A } \in \left[ - 1 , 1 \right]$

Definition II.3 (Mass function)[12,13]

6o For a map M from $2 ^ { \mathbb { E } }$ to [0,1], that is, $\left| \mathbb { M } \right| : 2 ^ { \mathbb { E } } \to [ 0 , 1 ] ,$ , and satisfies that

$$
\mathbb { M } \left( \varnothing \right) = 0 , \sum _ { A \subseteq \mathbb { K } } \mathbb { M } \left( A \right) = 1
$$

$\mathbb { M } \left( A \right)$ is denoted as mass function,which indicates the support degree of the evidence for proposition $A$ . Obviously, $\mathbb { M } \left( A \right)$ is a special case of $\mathbb { C } \mathbb { M } \left( A \right)$ ,i.e., when $\theta _ { A } = 0$ $\mathbb { C } \mathbb { M } \left( A \right)$ degenerates to a mass function $\mathbb { C } \mathbb { M } \left( A \right)$ of real-valued space.

# ；2.2. Deng entropy

Benefit from the application of Shannon entropy in uncertainty measurement under a probability distribution framework， several researchers have

proposed uncertainty measures for real-valued mass functions in evidence theory, such as Dubois and Prade's weighted Hartley entropy[22],Hohle's con  
70 fusion measure[23], Yager's dissonance measure[24], Deng entropy[25] and other[26,27,28]. These entropies can effectively measure uncertain information and thus are widely studied and applied in various fields. Taking Deng entropy as an example,Abelln analyzed the five properties of Deng entropy[29], Kang et al. analyzed the distribution of maximum Deng entropy[30]. Liu et   
75al. established the relationship between Deng entropy and other non-additive entropies[31]. Moral-Garcia et al. critiqued the Deng entropy and proposed maximum of entropy for belief intervals[32, 33]. Deng proposed information volume of mass function based on fractal idea based on Deng entropy[34]. Buono and Longobardi proposed the dual entropy of Deng entropy[35]. Pan   
8oet al. introduced the idea of power-law fractal of maximum Deng entropy in the correlation coeficient to solve the conflict problem between evidences[36]. Liao et al. introduced Deng entropy in the decision-making process to the selection of effective drugs for the COVID-19[37]. Boulkaboul and Boulkaboul apply Deng entropy to IoT decision-making[38]. Zhou et al. proposed the mul  
85tiple attribute decision-making method based on Deng entropy[39]. Kazemi et al analyzes the fractional law of Deng entropy and discusses its application[40]. Thus, it is defined as follows.

Definition II.4 (Deng entropy)[25]

Consider a frame of discernment E, M is a mass function, whose uncertainty measure is described as follows:

$$
E _ { d } = \mathbb { M } \left( A \right) l n \frac { \mathbb { M } \left( A \right) } { 2 ^ { \left| A \right| } - 1 }
$$

where $| A |$ is the cardinality of $A$ ．The Deng entropy is an extension of the Shannon entropy, and when $| { \cal A } | \ = \ 1$ ， the Deng entropy degenerates to the Shannon entropy. The form of the Shannon entropy is described as follows.

# Definition II.5 (Shannon entropy)[41]

95 Fora probability distribution $P$ in the frame of discernment $\mathbb { E }$ ,its uncertainty measure is as follows.

$$
E _ { d } = p \left( A \right) l n p \left( A \right)
$$

where $p \left( A \right)$ is the probability of the event $A$ . The $p \left( A \right)$ is a special case of $\mathbb { M } \left( A \right)$ , when when $| A | = 1 , \mathbb { M } \left( A \right)$ and $p \left( A \right)$ are equivalent.

# 3. New entropy for complex-valued mass function

100 The methods in Subsection 2.2 have their own advantages in measuring the uncertainty of the mass function. However, these works cannot effectively measure the uncertainty for the complex-valued mass function, therefore, it is still an open issue. In this work,a complex-valued uncertainty measure, called as complex-valued Deng entropy is presented as follows:

105 Definition III.1 (complex-valued Deng entropy)

$$
C E _ { d } = \left. - \left. \mathbb { M } \left( A \right) e ^ { i \pi \theta _ { A } } \right. l n \frac { \mathbb { M } \left( A \right) e ^ { i \pi \theta _ { A } } } { 2 ^ { \left| A \right| } - 1 } \right.
$$

where $\left\| \mathbb { M } \left( A \right) e ^ { i \pi \theta _ { A } } \right\|$ is the mold of $\mathbb { M } \left( A \right) e ^ { i \pi \theta _ { A } }$ ： $| A |$ is the number of elements in the proposition $A$ ,also noted as the cardinality of $A$ . Further, the complexvalued Deng entropy is reexpressed.

$$
C E _ { d } = \left. - \left( \left. \mathbf { M } \left( A \right) e ^ { i \pi \theta _ { A } } \right. l n \mathbf { M } \left( A \right) + \left. \mathbf { M } \left( A \right) e ^ { i \pi \theta _ { A } } \right. l n e ^ { i \pi \theta _ { A } } - \left. \mathbf { M } \left( A \right) e ^ { i \pi \theta _ { A } } \right. l n 2 ^ { \left| A \right| } - 1 \right) \right.
$$

next, we organize the complex-valued Deng entropy:

$$
C E _ { d } = \left. - \left( \mathbf { M } \left( A \right) l n \mathbf { M } \left( A \right) + i \mathbf { M } \left( A \right) \pi \theta _ { A } - \mathbf { M } \left( A \right) l n 2 ^ { \left| A \right| } - 1 \right) \right.
$$

110 Obviously, the complex-valued Deng entropy is very similar to the classical Deng entropy and Shannon entropy, and the relationship between them is

described as follows:

$( i )$ When $\theta _ { A } = 0 ,$ ， the complex-valued Deng entropy degenerates to the classical Deng entropy, i.e.,

$$
C E _ { d } = - \left( \mathbf { M } \left( A \right) l n \mathbf { M } \left( A \right) - \mathbf { M } \left( A \right) l n 2 ^ { \left| A \right| } - 1 \right)
$$

115 (ii) For arbitrary $| A | = 0 .$ , the complex-valued Deng entropy degenerates to the complex-valued Shannon entropy:

$$
C E _ { d } = C H = \left. - \left( \mathbf { M } \left( A \right) l n \mathbf { M } \left( A \right) + i \mathbf { M } \left( A \right) \pi \theta _ { A } \right) \right.
$$

where $C H$ represents complex-valued Shannon entropy.

(i) For arbitrary $| { \cal A } | = 0$ and $\theta _ { A } = 0$ , the complex-valued Deng entropy degenerates to the Shannon entropy:

$$
C E _ { d } = - \mathbb { M } \left( A \right) l n \mathbb { M } \left( A \right)
$$

# 120 4.Numerical examples

In this section, some examples are designed to explain the compatibility and effectiveness of the complex-valued Deng entropy.

Example 3.1 Suppose there is a complex valued mass function $\mathbb { C } \mathbb { M } \left( E _ { 1 } \right) = 1 .$ whose uncertainty information is measured as follows:

$$
\begin{array} { l } { H = - 1 \times l n 1 = 0 } \\ { C H = - 1 \times l n 1 = 0 } \\ { E _ { d } = - 1 \times l n \frac { 1 } { 2 ^ { | 1 | } - 1 } = 0 } \\ { C E _ { d } = - 1 \times l n \frac { 1 } { 2 ^ { | 1 | } - 1 } = 0 } \end{array}
$$

This example shows that for a perfectly certain proposition, the uncertainty 130 measure is O based on $H , C H , E _ { d }$ and $C E _ { d } ,$ which is intuitive.

Example 3.2 Exists a frame of discernment $\mathbb { E } = \{ E _ { 1 } , E _ { 2 } , E _ { 3 } , E _ { 4 } \} _ { }$ ， $\mathbb { C } \mathbb { M } \left( E _ { 1 } \right) =$

$\begin{array} { r } { \mathbb { C } \mathbb { M } \left( E _ { 2 } \right) = \mathbb { C } \mathbb { M } \left( E _ { 2 } \right) = \mathbb { C } \mathbb { M } \left( E _ { 4 } \right) = \frac { 1 } { 4 } } \end{array}$ is a complex-valued mass function, and its uncertainty information is measured as follows.

$$
\begin{array} { r l } & { H = - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } = 1 . 3 8 6 3 } \\ & { C H = - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } - \frac { 1 } { 4 } \times l n \frac { 1 } { 4 } = 1 . 3 8 6 3 } \\ & { E _ { d } = - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } = 1 . 3 8 6 3 } \\ & { C E _ { d } = - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } - \frac { 1 } { 4 } \times l n \frac { \frac { 1 } { 4 } } { 2 ^ { | 1 | } - 1 } = 1 . 3 8 6 3 } \end{array}
$$

Example 3.3 There is a complex-valued mass function $\mathbb { C } \mathbb { M } \left( E _ { 1 } \right) = \mathbb { C } \mathbb { M } \left( E _ { 2 } \right) =$ $\begin{array} { r } { \mathbb { C } \mathbb { M } \left( E _ { 2 } \right) = \mathbb { C } \mathbb { M } \left( E _ { 4 } \right) = \frac { 1 } { 4 } e ^ { i \frac { 1 } { 3 } \pi } } \end{array}$ in the frame of discernment $\mathbb { E }$ ,then

$$
\begin{array} { r l } & { C H = \left\| - \left( 4 \times \frac 1 4 \times l n \frac 1 4 + i \times 4 \times \pi \times \frac 1 3 \right) \right\| = 3 . 1 4 1 6 } \\ & { C E _ { d } = \left\| - \left( 4 \times \frac 1 4 \times l n \frac { \frac 1 4 } { 2 ^ { \left| 1 \right| } - 1 } + i \times 4 \times \pi \times \frac 1 3 \right) \right\| = 3 . 1 4 1 6 } \end{array}
$$

Example 3.2 and Example 3.3 are the measures of inaccurate information in real-valued space and complex-valued space,respectively. It is reasonable to see from the results that adding the phase angle leads to an increase of the uncertain information in the complex-valued framework.This also shows that the conditions for the application of $C H$ and $H$

Example 3.4 Consider a frame of discernment $\mathbb { E } = \{ E _ { 1 } , E _ { 2 } , E _ { 3 } , E _ { 4 } \} _ { . }$ ,for a complex valued mass function $\mathbb { C } \mathbb { M } \left( \mathbb { E } \right) = 1$ , which has the following uncertainty:

$$
\begin{array} { l } { H = - 1 \times l n 1 = 0 } \\ { C H = - 1 \times l n 1 = 0 } \\ { E _ { d } = - 1 \times l n \frac { 1 } { 2 ^ { | 4 | } - 1 } = 2 . 7 0 8 1 } \\ { C E _ { d } = - 1 \times l n \frac { 1 } { 2 ^ { | 4 | } - 1 } = 2 . 7 0 8 1 } \end{array}
$$

In contrast to $\mathbb { C } \mathbb { M } \left( E _ { 1 } \right) = 1 .$ $\mathbb { C } \mathbb { M } \left( \mathbb { E } \right) = 1$ indicates that for propositions that are completely unknown, in Example 3.1, $H = 0$ and $C H = 0$ .In Example 1553.4, it is still $H = 0$ and $C H = 0$ . Obviously, in Example 3.4, the results for $H$ and $C H$ are not reasonable,indicating that $H$ and $C H$ are more applicable to probability distributions than to mass functions. For $E _ { d }$ and $C E _ { d } ,$ the measures in both examples are intuitive,which indicate that $E _ { d }$ and $C E _ { d }$ can be effective measures of uncertainty in mass functions,and also, that $E _ { d }$ and $C E _ { d }$ are com

160 patiblewith $H$ and $C H$

Example 3.5 Suppose exists a complex-valued mass function $\mathbb { C } \mathbb { M } \left( \mathbb { E } \right) = e ^ { i \frac { 1 } { 2 } \pi }$ in $\mathbb { E } = \{ E _ { 1 } , E _ { 2 } , E _ { 3 } , E _ { 4 } \} _ { }$ ,then

$$
\begin{array} { l } { C H = \left\| - \left( 1 \times l n 1 + i \times \pi \times \frac { 1 } { 2 } \right) \right\| = 1 . 5 7 0 8 } \\ { C E _ { d } = \left\| - \left( 1 \times l n \frac { 1 } { 2 ^ { \left| 4 \right| } - 1 } + i \times \pi \times \frac { 1 } { 2 } \right) \right\| = 3 . 9 3 8 8 } \end{array}
$$

165 The $C E _ { d } ~ = ~ 2 . 7 0 8 1$ and $C E _ { d } ~ = ~ 3 . 1 3 0 6$ are the results of uncertainty information measurements based on complex-valued Deng entropy in the realvalued and complex-valued framework,respectively，and it is obvious that $2 . 7 0 8 1 < 3 . 1 3 0 6 ,$ . which is due to the uncertainty information of adding phase angles in Example 3.5, this result is intuitive and also shows that $C E _ { d }$ is com  
170 patible with $E _ { d }$ . Several examples above explain the relationship between $C E _ { d }$ and $E _ { d } , C H , H ,$ thatis, $C E _ { d }$ is compatible with $E _ { d } , C H , H$ . Next, two examples are designed to explain the effectiveness of $C E _ { d }$ in measuring uncertain information.

Example 3.6 Suppose the existence of a frame of discernment $\mathbb { E }$ , there are four 5complex-valued mass function, described as follows:

$$
\begin{array} { r } { \mathbb { C } \mathbb { M } _ { 1 } \left( \mathbb { E } \right) = 1 , \mathbb { C } \mathbb { M } _ { 2 } \left( \mathbb { E } _ { j } \right) = \frac { 1 } { \vert \mathbb { E } \vert } , \mathbb { C } \mathbb { M } _ { 3 } \left( \mathbb { E } \right) = e ^ { i \pi } , \mathbb { C } \mathbb { M } _ { 4 } \left( \mathbb { E } _ { j } \right) = \frac { 1 } { \vert \mathbb { E } \vert } e ^ { i \frac { 1 } { \mathbb { E } \vert } \pi } } \end{array}
$$

Table1:VariablesetE.   

<html><body><table><tr><td>E E</td><td></td></tr><tr><td>1</td><td>{E1}</td></tr><tr><td>2</td><td>{E1,E2}</td></tr><tr><td>3</td><td>{E1,E2,E3}</td></tr><tr><td>4</td><td>{E1,E2,E3,E4}</td></tr><tr><td>5</td><td>{E1,E2,E3,E4,E5}</td></tr><tr><td>j</td><td>{E1,E,E，.·，,Ej}</td></tr><tr><td>31</td><td>{E1,E2,E3,E4，..,E31}</td></tr><tr><td>32</td><td>{E1,E,E·.·,Ej，···,E32}</td></tr></table></body></html>

![](images/86c407d7c0c6c4625f3bb940b6f37e119b912da229297e20c4f24aacc9af8e24.jpg)  
Figure 1: Uncertainty measures of four complex-valued mass functions based on $C E _ { d }$

The form of $\mathbb { E }$ is shown in Table 1. Figure 1 shows the uncertainty infor

mation for the four complex-valued mass functions. As can be seen in Figure 1, the uncertainty of $\mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 3 }$ is larger than that of $\mathbb { C } \mathbb { M } _ { 2 }$ and $\mathbb { C } \mathbb { M } _ { 4 }$ . This   
180 is a reasonable result because the completely unknown information contains more uncertainty relative to the uncertainty information of the probability distribution.Also, there is a difference between $\mathbb { C } \mathbb { M } _ { 1 }$ and $\mathbb { C } \mathbb { M } _ { 3 }$ .For $\mathbb { C } \mathbb { M } _ { 3 }$ ，the phase angle also contains uncertainty information, so the uncertainty of $\mathbb { C } \mathbb { M } _ { 3 }$ is larger, which is 22.4. Similarly, the uncertainty of $\mathbb { C } \mathbb { M } _ { 4 }$ is larger than that of   
185 $\mathbb { C } \mathbb { M } _ { 2 }$ . This example explains that the complex-valued Deng entropy can effectively measure the uncertainty for the complex-valued mass function.

Example 3.7 Consider two of the following complex-valued mass functions in E={e1,e2,e3..,ej,·,e32}: $\mathbb { C } \mathbb { M } _ { 1 } \left( E _ { 5 } \right) = 0 . 0 5 , \mathbb { C } \mathbb { M } _ { 1 } \left( E _ { 4 } , E _ { 6 } , E _ { 7 } \right) = 0 . 1 ,$ 190 $\mathbb { C } \mathbb { M } _ { 1 } \left( X \right) = 0 . 7 , \mathbb { C } \mathbb { M } _ { 1 } \left( \mathbb { E } \right) = 0 . 1 5 .$ （20 $\mathbb { C } \mathbb { M } _ { 2 } \left( E _ { 5 } \right) = 0 . 0 5 e ^ { i 0 . 2 \pi } , \mathbb { C } \mathbb { M } _ { 2 } \left( E _ { 4 } , E _ { 6 } , E _ { 7 } \right) = 0 . 1 e ^ { i 0 . 4 \pi } ,$ （204 $\mathbb { C } \mathbb { M } _ { 2 } \left( X \right) = 0 . 7 e ^ { i 0 . 7 \pi } , \mathbb { C } \mathbb { M } _ { 2 } \left( \mathbb { E } \right) = 0 . 1 5 e ^ { i 0 . 6 \pi } .$ （204号

Table 2 lists some of the complex-valued Deng entropy when X varies, and more information is in Figure 2. It can be seen from Table 2 that the uncertainty 195 of $\mathbb { C } \mathbb { M } _ { 1 }$ and the uncertainty of $\mathbb { C } \mathbb { M } _ { 2 }$ increase as the elements in $X$ increases, and the complex-valued Deng entropy reaches the maximum when $\scriptstyle x = 3 2$ .It is worth noting that for each $X _ { \cdot }$ , the uncertainty of $\mathbb { C } \mathbb { M } _ { 2 }$ is always larger than that of $\mathbb { C } \mathbb { M } _ { 1 . }$ ，which is intuitive. This example also demonstrates the effectiveness of the complex-valued Deng entropy.

# 200 5.Conclusion

Most of the methods can effectively measure the uncertainty for the mass function in the real-valued framework, however, to reasonably measure the uncertainty of the complex-valued mass function is still an open issue.Therefore，we propose the generalized Deng entropy, named as complex-valued Deng entropy. The main contribution of the complex-valued Deng entropy is that the uncertainty of the complex-valued mass function can be effectively measured under the framework of complex-valued evidence theory. Also complex-valued Deng entropy has high compatibility. Some numerical examples demonstrate the compatibility and effectiveness of complex-valued Deng entropy. Thus, the new entropy provides a reliable tool to measure uncertain information. Further, we may discuss the properties of the new entropy and the physical meaning in future work.

Table2:VariablesetX.   

<html><body><table><tr><td>X</td><td>CM1</td><td>CIM2</td><td>△</td></tr><tr><td>{E1</td><td>4.4360</td><td>4.8575</td><td>0.4215</td></tr><tr><td>{E1,E2}</td><td>5.2050</td><td>5.5686</td><td>0.3636</td></tr><tr><td>{E1,E,E}</td><td>5.7981</td><td>6.1266</td><td>0.3285</td></tr><tr><td>{E,E,E,E4}</td><td>6.3316</td><td>6.6337</td><td>0.3021</td></tr><tr><td>{E1,E,E,E5}</td><td>6.8398</td><td>7.1204</td><td>0.2806</td></tr><tr><td>{E1,E,E·,E6}</td><td>7.3362</td><td>7.5985</td><td>0.2623</td></tr><tr><td>{E1,E,E.,E7}</td><td>7.8269</td><td>8.0733</td><td>0.2464</td></tr><tr><td>{E,E,E,E8}</td><td>8.3149</td><td>8.5472</td><td>0.2323</td></tr><tr><td>{E1,E,E·,E}</td><td>8.8014</td><td>9.0212</td><td>0.2198</td></tr><tr><td>{E1,E,E,E10}</td><td>9.2873</td><td>9.4959</td><td>0.2086</td></tr><tr><td>{E1,E,E,E11}</td><td>9.7729</td><td>9.9713</td><td>0.1984</td></tr><tr><td>{E1,E,E.,E12}</td><td>10.2582</td><td>10.4474</td><td>0.1892</td></tr><tr><td>{E1,E,E.,E}</td><td>X</td><td>y</td><td>y-x</td></tr><tr><td>{E1,E2,E..,E}</td><td>19.4773</td><td>19.5776</td><td>0.1003</td></tr><tr><td>{E,E,E,.,E32}</td><td>19.9625</td><td>20.0604</td><td>0.0979</td></tr></table></body></html>

![](images/f9aa554bf8e2da9b098b6a5184f20d8c27c90e33fbb9f6debb6bae48fc26cc0e.jpg)  
Figure 2:Uncertainty measures of two complex-valued mass functions based on $C E _ { d }$ （204号

# Declaration of competing interest

The authors have no conflict of interests regarding the publication of this 215 paper.

# Acknowledgment

The work is partially supported by National Natural Science Foundation of China (Grant No. 61973332), JSPS Invitational Fellowships for Research in Japan (Short-term).

# 220 References

[1]P.-S.Laplace,Analytical theory of probabilities,published in.

[2] L. A. Zadeh,Fuzzy sets,in: Fuzzy sets, fuzzy logic, and fuzzy systems: selected papers by Lotfi A Zadeh, World Scientific, 1996, pp. 394-432. [3] K. T. Atanassov, Intuitionistic fuzzy sets, Vol. 20,Springer, 1986, pp.87-96.   
225 [4] R.R. Yager, A. M. Abbasov, Pythagorean membership grades, complex numbers, and decision making, International Journal of Intelligent Systems 28 (5) (2013) 436-452. [5] Z. Pawlak, Rough sets, International journal of computer & information sciences 11 (5) (1982) 341-356.   
230 [6] L.Vervoort, Probability theory as a physical theory points to superdeterminism, Entropy 21 (9) (2019) 848. [7] R. Durrett, Probability: theory and examples, Vol. 49, Cambridge university press, 2019. [8] L. Wang, L. Ma, C. Wang, N.-g. Xie, J. M. Koh, K. H. Cheong, Identify  
235 ing influential spreaders in social networks through discrete moth-flame optimization, IEEE Transactions on Evolutionary Computation. [9] L. P. Deng;, Complex-valued renyi entropy, chinaXiv (2021) 202106.00005. [10] G. Baym, Lectures on quantum mechanics, CRC Press, 2018. [11] J. W. Lai,J. R.A. Tan, H. Lu, Z.R. Yap,K.H. Cheong,Parrondo paradoxical   
240 walk using four-sided quantum coins, Physical Review E 102 (1) (2020) 012213. [12] A. Dempster, Upper and lower probabilities induced by a multivalued mapping(upper and lower probabilities induced by multivalued mapping).   
245[13] G. Shafer, A mathematical theory of evidence, Vol.42, Princeton university press, 1976. [14] X. Gao, L. Pan, Y. Deng, Quantum pythagorean fuzzy evidence theory (qpfet): A negation of quantum mass function view, IEEE Transactions on Fuzzy Systems.   
250[15] H. Abbasimehr, R. Paki, Prediction of covid-19 confirmed cases combining deep learning methods and bayesian optimization, Chaos, Solitons & Fractals 142 (2021) 110511. [16] B. Zhu, X. Zheng, H. Liu, J. Li, P. Wang, Analysis of spatiotemporal characteristics of big data on social media sentiment with covid-19 epidemic   
255 topics, Chaos, Solitons & Fractals 140 (2020) 110123. [17] D. Li, Y. Deng, K. H. Cheong, Multisource basic probability assignment fusion based on information quality, International Journal of Intelligent Systems 36 (4) (2021) 1851-1875. [18] T. Denoeux,Calibrated model-based evidential clustering using boot  
260 strapping, Information Sciences 528 (2020) 17-45. [19] Y. Fan,T. Ma, F. Xiao,An improved approach to generate generalized basic probability assignment based on fuzzy sets in the open world and its application in multi-source information fusion, Applied Intelligence (2020) 1-18.   
265[20] J. Zhao, Y. Deng, Complex network modeling of evidence theory, IEEE Transactions on Fuzzy Systems (2020) 10.1109/TFUZZ.2020.3023760. [21] L. Pan, Y. Deng, 202103.00132, chinaXiv (2021) 202103.00132. [22] D. Dubois,H. Prade,A note on measures of specificity for fuzzy sets, International Journal of General System 10 (4) (1985) 279-283.   
270[23] U. Hohle, Entropy with respect to plausibility measures,in: Proc. of 12th IEEE Int. Symp. on Multiple Valued Logic,Paris,1982,1982. [24] R. R. Yager, Entropy and specificity in a mathematical theory of evidence, in: Classic Works of the Dempster-Shafer Theory of Belief Functions, Springer, 2008, pp. 291-310.   
275[25] Y. Deng, Deng entropy, Chaos,Solitons & Fractals 91 (2016) 549-553. [26] J. Deng, Y. Deng, Information volume of fuzzy membership function, International Journal of Computers Communications & Control 16 (1) (2021) 4106.doi:https://doi.org/10.15837/ijccc.2021.1.4106. [27] Y. Xue, Y. Deng, Tsalis extropy, Communications in Statistics-Theory and   
280 Methods (2021) 10.1080/03610926.2021.1921804. [28] H. Zhang, Y. Deng, Entropy Measure for Orderable Sets, Information Sciences 561 (2021) 141-151. [29] J. Abelln, Analyzing properties of deng entropy in the theory of evidence, Chaos Solitons & Fractals 95 (2017) 195-199.   
285[30] Y. Deng, Uncertainty measure in evidence theory, SCIENCE CHINA Information Sciences 64 (2021) 10.1007/s11432-020-3006-9. [31] F Liu, X. Gao,J. Zhao, Y. Deng, Generalized belief entropy and its application in identifying conflict evidence, IEEE Access 7 (2019) 126625-126633. [32] S.Moral-Garcia, J. Abellan, Critique of modified deng entropies under the   
290 evidence theory, Chaos, Solitons & Fractals 140 (2020) 110112. [33] S.Moral-Garcia,J. Abellan, Maximum of entropy for belief intervals under evidence theory, IEEE Access 8 (2020) 118017-118029.   
[34] Y. Deng, Information volume of mass function, International Journal of Computers Communications & Control 15 (6) (2020) 3983. doi:https: //doi.org/10.15837/ijccc.2020.6.3983.   
[35] F. Buono, M. Longobardi, A dual measure of uncertainty: The deng extropy, Entropy 22 (5). doi : 10.3390/e22050582. URL https://www.mdpi.com/1099-4300/22/5/582   
[36] L.Pan, Y. Deng, An association coeficient of a belief function and its application in a target recognition system, International Journal of Intelligent Systems 35 (1) (2020) 85-104.   
[37] H. Liao, Z. Ren, R. Fang, A deng-entropy-based evidential reasoning approach for multi-expert multi-criterion decision-making with uncertainty, International Journal of Computational Intelligence Systems 13 (2020) 1281-1294. doi:https://doi.org/10.2991/ijcis.d.200814.001.   
[38] S.Boulkaboul，D. Djenouri，Dfiot:Data fusion for internet of things， Journal of Network and Systems Managementdoi:10.1007/ s10922-020-09519-y.   
[39] M. Zhou, Y.-W. Chen, X.-B. Liu, B.-Y. Cheng J.-B. Yang, Weight assignment method for multiple attribute decision making with dissimilarity and conflict of belief distributions, Computers & Industrial Engineering (2020) 106648.   
[40] M. R. Kazemi, S. Tahmasebi, F. Buono, M. Longobardi, Fractional deng entropy and extropy and some applications, Entropy 23 (5). doi : 10 .3390/ e23050623. URL https://www.mdpi.com/1099-4300/23/5/623   
[41] C.E. Shannon,A mathematical theory of communication,ACM SIGMOBILE mobile computing and communications review 5 (1) (2001) 3-55.