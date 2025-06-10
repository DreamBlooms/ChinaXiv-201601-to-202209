# Silver Ratio in Maximum Deng Entropy Triangle

Jixiang Denga, Yong Dengab,c,d,\*

$a$ InstituteofFundamental andFrontier Sciences,UniversityofElectronic Scienceand TechnologyofChina, Chengdu, China. bSchooloftiility cSchool of Knowledge Science,Japan Aduanced Institute of Science and Technology,Nomi, Ishikawa 923-1211, Japan dDepartment ofanagement,Tchnology,and Economics,ETHZurich, Zurich,Switzerland

# Abstract

Pascal's triangle is a mathematical triangle of combinatorial numbers, from which Fibonacci number sequence and golden ratio can be obtained. Similarly, silver ratio can be generated based on Pell number sequence. Recently, the relations between Pascal's triangle and maximum Deng entropy (MXDE) are studied and presented. A straightforward question arises: if we design a triangle based on MXDE, what will the associated number sequence and the limiting ratio be like? Hence, this paper proposes a Pascal-like triangle based on MXDE, called the maximum Deng entropy triangle (MDET). Besides, the number sequences based on MDET are investigated. Next, the general term for the MDET sequence is presented and the limiting ratio in MDET sequence is analyzed. We prove that the limiting ratio in the right MDET sequence converges to the silver ratio. Moreover, some examples are given to expound MDET and the MDET sequence.

Keywords: Pascal's triangle, Deng entropy, Maximum Deng entropy triangle (MDET), Number sequence, Silver ratio

# 1. Introduction

Pascal triangle refers to a triangular arrangement of the combinatorial numbers and has numerous properties [1]. One of the appealing properties of Pascal's triangle is that its diagonal sum can generate the Fibonacci number sequence [2, 3,4]. The Fibonacci numbers had occurred in lots of fields from the pattern of gerbera flower heads [5] to the rhythm of architecture [6]. The limiting ratio of two successive terms in Fibonacci numbers converges to 1.618, which shows the relationship between Pascal's triangle and the golden ratio ${ \frac { 1 + { \sqrt { 5 } } } { 2 } } \ [ 2 , 7 , 8 ]$ . Apart from the golden ratio,another important irational mathematical constant is the silver ratio $1 + { \sqrt { 2 } }$ . Similar to the way of generating the golden ratio from Fibonacci numbers, silver ratio can be acquired based on the limiting ratio of two successive numbers in Pell number sequence [9]. Golden ratio and silver ratio have been attracted many attentions and have been wildly used in modern sciences,such as set theory [10],architecture [6,11], shape optimization [12], nonlinear systems [13], generalized golden ratio [14], silver structure [15], and continued fraction algorithm [16].

The relationship between Pascal's triangle and entropy is a fascinating topic. Based on the probability theory, Tsalis entropy is a generalization of Boltzmann-Gibbs statistics [17], whose relationship to Pascal's triangle is investigated in [18]. Recently, Deng proposed a new entropy, called Deng entropy [19], which is an extension of Shannon entropy based on Dempster-Shafer evidence theory [20,21]. Then, Kang and Deng presented the maximum Deng entropy (MXDE) [19], where the analytical solution of MXDE and its associated distribution are analyzed. Since the form of MXDE contains combinatorial numbers, Deng entropy has many relations to Pascal's triangle. In 2019, Gao and Deng pointed out that pseudo-Pascal's triangle can be generated from MXDE [22]. In 2021, Song and Deng explained the power set in evidence theory from the perspective of Pascal's triangle and entropy [23], in which the relation between Deng entropy and

Pascal's triangle is also discussed.

On the one hand, Pascal's triangle can construct Fibonacci number sequence and further yield the golden ratio. On the other hand, Pascal's triangle has many relations to MXDE. A straightforward question arises: if we design a triangle based on MXDE, what will the generated number sequence and the associated limiting ratio be like?

To address the issue mentioned above, this paper proposes a Pascal-like triangle based on MXDE,called the maximum Deng entropy triangle (MDET). Besides, the number sequence based on MDET is investigated. MDET can yield two types of sequences, i.e., the left and the right MDET sequence. Next, the general term for the MDET sequence is presented and proved. Based on the general term, the limiting ratio for two successive terms in MDET sequence is analyzed. We prove that, under the condition of $n  \infty$ ,the limiting ratio in right MDET sequence converges to the silver ratio $1 + { \sqrt { 2 } }$ .Moreover, some examples are shown to expound MDET and the MDET sequence, where the MDET sequence is compared with several well-known number sequences, namely Fibonacci numbers,Pell numbers,and Jacobsthal numbers.

Section 2 reviews some preliminaries. In Section 3, the definition of MDET is proposed,and then the corresponding sequence and ratio of MDET is analyzed. Section 4 shows some examples for illustration. Section 5 makes a conclusion.

# 2.Preliminaries

# 2.1. Evidence theory

Evidence theory [20, 21] is a generalization of probability theory and has various applications, such as reasoning [24],and knowledge representation [25,26]. In evidence theory, the frame of discernment (FOD) is a finite sample space denoted by $\Theta =$ $\big \{ \theta _ { 1 } , \theta _ { 2 } , \ldots , \theta _ { N } \big \} _ { \mathrm { . } }$ ， which is the same as in probability theory. One of the most biggest differences compared to probability theory is that the event space of evidence theory is the power set $2 ^ { \Theta }$ , which considers all the possible subsets of $\Theta$

$$
2 ^ { \Theta } = \{ \emptyset , \{ \theta _ { 1 } \} , \cdot \cdot \cdot , \{ \theta _ { N } \} , \{ \theta _ { 1 } , \theta _ { 2 } \} , \cdot \cdot \cdot , \{ \theta _ { 1 } , \theta _ { 2 } , \theta _ { 3 } \} , \cdot \cdot \cdot , \Theta \ \}
$$

As an extension of probability distribution, a basic probability assignment (BPA) is a map ping function indicated by

$$
m : 2 ^ { \Theta }  [ 0 , 1 ]
$$

satisfying $\Sigma _ { A \in 2 ^ { \Theta } } m ( A ) = 1$ and $m ( \emptyset ) = 0$ . Particularly, the element $A \in 2 ^ { \Theta }$ with $m ( A ) >$ O is called the focal element.

# 2.2. Deng entropy

For handling the uncertainty of BPA, Deng entropy is proposed based on the framework of evidence theory and is an extension of Shannon entropy [19,27]. Several properties of Deng entropy are analyzed in [19, 28]. Deng entropy has a variety of applications,such as time series analysis [29,30],evidentialreasoning[24],fractal-based eXtropy [31,32], information volume [33,34,35], and target classification [36,37]. Given a BPA defined on FOD $\Theta$ , Deng entropy is defined by [19]:

$$
H _ { D E } ( m ) = - \sum _ { A \in 2 ^ { \Theta } } m ( A ) \log ( \frac { m ( A ) } { 2 ^ { | A | } - 1 } )
$$

where $| \cdot |$ represents the cardinality. The maximum entropy principle is important in statistic. The maximum value of Deng entropy and its BPA distribution are discussed in [19]. If and only if the BPA satisfies:

$$
m ( A ) = { \frac { ( 2 ^ { | A | } - 1 ) } { \sum _ { A \in 2 ^ { \Theta } } ( 2 ^ { | A | } - 1 ) } } , A \in 2 ^ { \Theta }
$$

the maximum Deng entropy (MXDE) appears, which is as follows:

$$
H _ { M X D E } = \log \sum _ { A \in 2 ^ { \Theta } } ( 2 ^ { | A | } - 1 )
$$

# 2.3. Typical number sequences and their limiting ratios

In this subsection, the recurrence relations of several well-known number sequences and their corresponding general terms are briefly reviewed. In addition, the associated limiting ratios of these sequences are also presented, in which the limiting ratio of Fibonacci numbers is the golden ratio, and that of Pell numbers is the silver ratio.

· Fibonacci number sequence and its limiting ratio (golden ratio) [7,38,39, 40]:

$$
\begin{array} { l } { \displaystyle { F ( n ) = \frac { 1 } { \sqrt { 5 } } \left[ \left( \frac { 1 + \sqrt { 5 } } { 2 } \right) ^ { n } - \left( \frac { 1 - \sqrt { 5 } } { 2 } \right) ^ { n } \right] } } \\ { \displaystyle { \operatorname* { l i m } _ { n \to \infty } \frac { F \left( n \right) } { F \left( n - 1 \right) } = \frac { 1 + \sqrt { 5 } } { 2 } } } \end{array}
$$

Pell number sequence and its limiting ratio (silver ratio) [9,41]:

$$
\begin{array} { l } { P ( n ) = 2 P ( n - 1 ) + P ( n - 2 ) \ w i t h \ P ( 0 ) = } \\ { P ( n ) = \displaystyle \frac { 1 } { 2 \sqrt { 2 } } \left[ \left( 1 + \sqrt { 2 } \right) ^ { n } - \left( 1 - \sqrt { 2 } \right) ^ { n } \right] } \\ { \displaystyle \operatorname* { l i m } _ { n \to \infty } \frac { P \left( n \right) } { P \left( n - 1 \right) } = 1 + \sqrt { 2 } } \end{array}
$$

· Jacobsthal number sequence and its limiting ratio [41, 42]:

$$
\begin{array} { l } { { J ( n ) = J ( n - 1 ) + 2 J ( n - 2 ) ~ w i t h ~ J ( 0 ) = 0 , J ( 1 ) = 1 } } \\ { { J ( n ) = \displaystyle { \frac { 1 } { 3 } } [ 2 ^ { n } - ( - 1 ) ^ { n } ] } } \\ { { \displaystyle { \operatorname* { l i m } _ { n  \infty } } { \frac { J ( n ) } { J ( n - 1 ) } } = 2 } } \end{array}
$$

# 3. Silver ratio in maximum Deng entropy triangle

# 3.1. Maximum Deng entropy triangle

Pascal's triangle is an arrangement of combinatorial numbers, whose illustration is shown in Figure 1 (a). According to [19,22], given a certain FOD $\Theta$ , the BPA distribution

![](images/ea611983df3131885f429ac16a78bbbefda9c70dfcae71c31e0da97f6eb0083c.jpg)  
Figure 1: (a) Pascal's triangle; (b) Maximum Deng entropy triangle (MDET)

Table1: BPA distribution of MXDE [19,22]   

<html><body><table><tr><td></td><td>|A| = 0 |A|= 1 |A|= 2 |A|= 3 |A| = 4</td></tr><tr><td>|0|=0 (1,0)</td><td></td></tr><tr><td>|0|= 1</td><td>(1,0) (1,1)</td></tr><tr><td>(1,0) (2,） (1,)</td><td></td></tr><tr><td>0|= 2 |0|= 3</td><td>(3,） (3,) (1,)</td></tr><tr><td>(1,0) |0|= 4 (1,0)</td><td>(4，） (6，） (4） (1,5)</td></tr></table></body></html>

Note: In $( x , y )$ 1 $x$ denotes the number of the focal elements that take the value $y ,$ and $y$ represents the value of the BPA.

of MXDE is shown in Table 1, where the numbers of the focal elements can actually construct a Pascal's triangle (shown in red). Gao and Deng pointed out that there are inextricable connections between Pascal's triangle and MXDE [22]. Inspired by this, a Pascal-like triangle is designed based on MXDE, which is called the maximum Deng entropy triangle (MDET). The definition of MDET is as follows:

Definition 3.1 (Maximum Deng entropy triangle). In the maximum Deng entropy triangle (MDET), the $k$ -th element of the $n$ -th row is defined by:

$$
M D E T ( n , k ) = C ( n , k ) * ( 2 ^ { k } - 1 )
$$

where $\begin{array} { r } { C ( n , k ) = \frac { n ! } { k ! ( n - k ) ! } , n \ge 0 , } \end{array}$ and $0 \leq k \leq n$ ：

For better understanding, the illustration of MDET is shown in Figure 1 (b).

# 3.2. MDET sequence

According to [2], Fibonacci number sequence can be derived from the diagonal sum of the entries in Pascal's triangle, which is illustrated in Figure 2 (a). Inspired by this idea, we present the diagonal sum of MDET, so as to obtain number sequences based on MDET. It should be noted that, since MDET is asymmetric, there are two directions for the diagonal sum of MDET, namely the left diagonal sum and the right diagonal sum, which are shown in Figure 2 (b) and (c).

![](images/49eee21c7f070ed4afe505a1728e1e186204c00e6213d4b30e1e146e5d00efde.jpg)  
Figure 2: (a) The diagonal sum of Pascal's triangle and its generated Fibonacci numbers $F ( n )$ . (b) The left diagonal sum of MDET and its generated left MDET sequence $D ^ { L } ( n )$ . (c) The right diagonal sum of MDET and its generated right MDET sequence $D ^ { R } ( n )$ ：

Then, based on these two directions of diagonal sum of MDET, two types of number sequences are derived, called left MDET sequence and right MDET sequence. In specific, as is shown in Figure 2 (b) and (c), the left (right) MDET sequence are respectively generated based on the left (right) diagonal sum of MDET. These two types of sequences are mathematically defined as below.

Definition 3.2 (MDET sequence). Based on the left and right diagonal sum of MDET, the left MDET sequence $D ^ { L } ( n )$ and the right MDET sequence $D ^ { R } ( { \bar { n } } )$ are defined by

$$
\begin{array} { l } { { \displaystyle { D ^ { L } \left( n \right) = \sum _ { k = 0 } ^ { \lfloor \frac { n } { 2 } \rfloor + 1 } M D E T \left( n - k , k \right) } } } \\ { { \displaystyle { D ^ { R } \left( n \right) = \sum _ { k = 0 } ^ { \lfloor \frac { n } { 2 } \rfloor + 1 } M D E T \left( n - k , n - k \right) } } } \end{array}
$$

where $\lfloor \cdot \rfloor$ is the floor function, which takes a real number as an input and returns the greatest integer less than or equal to that number.

# 3.3. General term of MDET sequence

In this subsection, the general terms for the two types of MDET sequences are investigated.If Eq. (15) is substituted into Eqs. (16) and (17), then the recurrence relations of left MDET sequence and that of right MDET sequence can be obtained:

$$
D ^ { L } \left( n \right) = 2 D ^ { L } ( n - 1 ) + 2 D ^ { L } ( n - 2 ) - 3 D ^ { L } ( n - 3 ) - 2 D ^ { L } ( n - 4 )
$$

$$
D ^ { R } \left( n \right) = 3 D ^ { R } { \left( n - 1 \right) } - 3 D ^ { R } { \left( n - 3 \right) } - D ^ { R } { \left( n - 4 \right) }
$$

$$
D ^ { R } ( 0 ) = 0 , D ^ { R } ( 1 ) = 1 , D ^ { R } ( 2 ) = 3 , D ^ { R } ( 3 ) = 9
$$

Based on the two recurrence relations, the general terms for the two types of MDET sequences can be derived:

Theorem 1. The general term of left MDET sequence is as follows:

$$
D ^ { L } \left( n \right) = \frac { 1 } { 3 } \left[ 2 ^ { n + 1 } - \left( - 1 \right) ^ { n + 1 } \right] - \frac { 1 } { \sqrt { 5 } } \left[ \left( \frac { 1 + \sqrt { 5 } } { 2 } \right) ^ { n + 1 } - \left( \frac { 1 - \sqrt { 5 } } { 2 } \right) ^ { n + 1 } \right]
$$

Theorem 2. The general term of right MDET sequence is as follows:

$$
n ) = { \frac { 1 } { 2 { \sqrt { 2 } } } } \left[ \left( 1 + { \sqrt { 2 } } \right) ^ { n + 1 } - \left( 1 - { \sqrt { 2 } } \right) ^ { n + 1 } \right] - { \frac { 1 } { \sqrt { 5 } } } \left[ \left( { \frac { 1 + { \sqrt { 5 } } } { 2 } } \right) ^ { n + 1 } - \left( { \frac { 1 - { \sqrt { 5 } } } { 2 } } \right) ^ { n } \right] ,
$$

# Proof 3.1 (Proof for Theorem3).

The corresponding characteristic equation of Eq. (18) is that

$$
\varphi ^ { 4 } - 2 \varphi ^ { 3 } - 2 \varphi + 3 \varphi + 2 = 0
$$

from which the characteristic roots can be solved:

$$
\varphi _ { 1 } = 2 , \varphi _ { 2 } = - 1 , \varphi _ { 3 } = { \frac { 1 + { \sqrt { 5 } } } { 2 } } , \varphi _ { 4 } = { \frac { 1 - { \sqrt { 5 } } } { 2 } }
$$

Based on the roots,the general term of left MDET sequence can be constructed:

$$
D ^ { L } \left( n \right) = c _ { 1 } 2 ^ { n } + c _ { 2 } \left( - 1 \right) ^ { n } + c _ { 3 } \left( \frac { 1 + \sqrt { 5 } } { 2 } \right) ^ { n } + c _ { 4 } \left( \frac { 1 - \sqrt { 5 } } { 2 } \right) ^ { n }
$$

Substitute the initial values $D ^ { L } ( 0 ) = D ^ { L } ( 1 ) = 0 , D ^ { L } ( 2 ) = 1 , D ^ { L } ( 3 ) = 2 ,$ and then calculate the constants:

$$
c _ { 1 } = { \frac { 2 } { 3 } } , \ c _ { 2 } = { \frac { 1 } { 3 } } , \ c _ { 3 } = { \frac { - 5 - { \sqrt { 5 } } } { 1 0 } } , \ c _ { 4 } = { \frac { - 5 + { \sqrt { 5 } } } { 1 0 } }
$$

Hence, the general term of left MDET sequence can be obtained:

$$
\begin{array} { c } { { D ^ { L } \left( n \right) = \displaystyle \frac 2 3 2 ^ { n } + \displaystyle \frac 1 3 \left( - 1 \right) ^ { n } + \displaystyle \frac { - 5 - \sqrt { 5 } } { 1 0 } \left( \displaystyle \frac { 1 + \sqrt { 5 } } { 2 } \right) ^ { n } + \displaystyle \frac { - 5 + \sqrt { 5 } } { 1 0 } \left( \displaystyle \frac { 1 - \sqrt { 5 } } { 2 } \right) ^ { n } } } \\ { { = \displaystyle \frac 1 3 \left[ 2 ^ { n + 1 } - \left( - 1 \right) ^ { n + 1 } \right] - \displaystyle \frac { 1 } { \sqrt { 5 } } \left[ \left( \displaystyle \frac { 1 + \sqrt { 5 } } { 2 } \right) ^ { n + 1 } - \left( \displaystyle \frac { 1 - \sqrt { 5 } } { 2 } \right) ^ { n + 1 } \right] } } \end{array}
$$

# Proof 3.2 (Proof for Theorem 4).

The associated characteristic equation of Eq. (19) is that

$$
\delta ^ { 4 } - 3 \delta ^ { 3 } + 3 \delta + 1 = 0
$$

from which the characteristic roots can be solved:

$$
\delta _ { 1 } = 1 + \sqrt { 2 } , \delta _ { 2 } = 1 - \sqrt { 2 } , \delta _ { 3 } = \frac { 1 + \sqrt { 5 } } { 2 } , \delta _ { 4 } = \frac { 1 - \sqrt { 5 } } { 2 }
$$

Based on the roots, the general term of right MDET sequence can be constructed:

$$
D ^ { R } \left( n \right) = c _ { 1 } \left( 1 + \sqrt { 2 } \right) ^ { n } + c _ { 2 } \left( 1 - \sqrt { 2 } \right) ^ { n } + c _ { 3 } \left( \frac { 1 + \sqrt { 5 } } { 2 } \right) ^ { n } + c _ { 4 } \left( \frac { 1 - \sqrt { 5 } } { 2 } \right) ^ { n }
$$

Substitute the initial values $D ^ { R } ( 0 ) = 0 , D ^ { R } ( 1 ) = 1 , D ^ { R } ( 2 ) = 3 , D ^ { R } ( 3 ) = 9 ,$ and then get the constants:

$$
c _ { 1 } = { \frac { 2 + { \sqrt { 2 } } } { 4 } } , \ c _ { 2 } = { \frac { 2 - { \sqrt { 2 } } } { 4 } } , \ c _ { 3 } = { \frac { - 5 - { \sqrt { 5 } } } { 1 0 } } , \ c _ { 4 } = { \frac { - 5 + { \sqrt { 5 } } } { 1 0 } }
$$

As a result, the general term of right MDET sequence can be obtained:

$$
\begin{array} { l } { { \displaystyle { D ^ { R } \left( n \right) = \frac { 2 + \sqrt 2 } { 4 } \left( 1 + \sqrt 2 \right) ^ { n } + \frac { 2 - \sqrt 2 } { 4 } \left( 1 - \sqrt 2 \right) ^ { n } } } } \\ { { \displaystyle { \qquad + \frac { - 5 - \sqrt 5 } { 1 0 } \left( \frac { 1 + \sqrt 5 } { 2 } \right) ^ { n } + \frac { - 5 + \sqrt 5 } { 1 0 } \left( \frac { 1 - \sqrt 5 } { 2 } \right) ^ { n } } } } \\ { { \displaystyle { \qquad = \frac { 1 } { 2 \sqrt 2 } \left[ \left( 1 + \sqrt 2 \right) ^ { n + 1 } - \left( 1 - \sqrt 2 \right) ^ { n + 1 } \right] - \frac { 1 } { \sqrt 5 } \left[ \left( \frac { 1 + \sqrt 5 } { 2 } \right) ^ { n + 1 } - \left( \frac { 1 - \sqrt 5 } { 2 } \right) ^ { n } + \frac { 1 - \sqrt 5 } { 2 } \right] ^ { n } } } } \end{array}
$$

Remark 1: Based on Theorem 1 and Eqs. (7) (13), the left MDET sequence can be calcu lated by Jacobsthal numbers $J ( n )$ and Fibonacci numbers $F ( n )$ ：

$$
D ^ { L } ( n ) = J ( n + 1 ) - F ( n + 1 ) , \ n \geq 0 .
$$

Remark 2: According to Theorem 2 and Eqs. (7) (10), the right MDET sequence can be calculated based on Pell numbers $P ( n )$ and Fibonacci numbers $F ( n )$

$$
D ^ { R } ( n ) = P ( n + 1 ) - F ( n + 1 ) , \ n \geq 0 .
$$

# 3.4.Siluerratio inMDET

In this subsection, we attempt to investigate the silver ratio in MDET. Based on Theorems 1 and 2, the limiting ratio for two successive terms in the left MDET sequence and that in the right MDET sequence satisfy the following theorems:

Theorem 3. When $n  \infty ,$ ，the limiting ratio for two successive terms in the left MDET sequence converges to:

$$
\operatorname* { l i m } _ { n  \infty } \frac { D ^ { L } ( n ) } { D ^ { L } ( n - 1 ) } = 2
$$

Theorem 4. When $n  \infty ,$ ， the limiting ratio for two successive terms in the right MDET sequence converges to:

$$
\operatorname* { l i m } _ { n  \infty } \frac { D ^ { R } ( n ) } { D ^ { R } ( n - 1 ) } = 1 + \sqrt { 2 }
$$

# Proof 3.3 (Proof for Theorem 5).

Based on Theorem 1,the limiting ratio can be calculated as

$$
\displaystyle \operatorname* { l i m } _ {  \infty } \frac { D ^ { L } ( n ) } { D ^ { L } ( n - 1 ) } = \operatorname* { l i m } _ { n  \infty } \frac { \frac { 1 } { 3 } [ 2 ^ { n + 1 } - ( - 1 ) ^ { n + 1 } ] - \frac { 1 } { \sqrt { 5 } } [ ( \frac { 1 + \sqrt { 5 } } { 2 } ) ^ { n + 1 } - ( \frac { 1 - \sqrt { 5 } } { 2 } ) ^ { n + 1 } ] } { \frac { 1 } { 3 } [ 2 ^ { n } - ( - 1 ) ^ { n } ] - \frac { 1 } { \sqrt { 5 } } [ ( \frac { 1 + \sqrt { 5 } } { 2 } ) ^ { n } - ( \frac { 1 - \sqrt { 5 } } { 2 } ) ^ { n } ] }
$$

Since $\varphi _ { 1 } = 2$ is the maximum characteristic root among the four roots,the limiting ratio can be written as:

$$
\operatorname * { l i m } _ { n  \infty } \frac { D ^ { L } ( n ) } { D ^ { L } ( n - 1 ) }  \operatorname * { l i m } _ { n  \infty } \frac { \frac { 1 } { 3 } ( 2 ^ { n + 1 } ) } { \frac { 1 } { 3 } ( 2 ^ { n } ) } = 2
$$

# Proof 3.4 (Proof for Theorem 6).

Based on Theorem 2,the limiting ratio can be calculated as

$$
{ \frac { \partial ^ { R } \left( n \right) } { \left. \left( n - 1 \right) \right.} } = \operatorname* { l i m } _ { n  \infty } { \frac { { \frac { 1 } { 2 { \sqrt { 2 } } } } \left[ \left( 1 + { \sqrt { 2 } } \right) ^ { n + 1 } - \left( 1 - { \sqrt { 2 } } \right) ^ { n + 1 } \right] - { \frac { 1 } { \sqrt { 5 } } } \left[ \left( { \frac { 1 + { \sqrt { 5 } } } { 2 } } \right) ^ { n + 1 } - \left( { \frac { 1 - { \sqrt { 2 } } } { 2 } } \right) ^ { n - 1 } \right] } { { \frac { 1 } { 2 { \sqrt { 2 } } } } \left[ \left( 1 + { \sqrt { 2 } } \right) ^ { n } - \left( 1 - { \sqrt { 2 } } \right) ^ { n } \right] - { \frac { 1 } { \sqrt { 5 } } } \left[ \left( { \frac { 1 + { \sqrt { 5 } } } { 2 } } \right) ^ { n } - \left( { \frac { 1 - { \sqrt { 3 } } } { 2 } } \right) ^ { n - 1 } \right] } } .
$$

Since $\delta _ { 1 } = 1 + \sqrt { 2 }$ is the maximum characteristic root among the four roots, the limiting ratio can be written as:

$$
\operatorname* { l i m } _ { n  \infty } { \frac { D ^ { R } ( n ) } { D ^ { R } ( n - 1 ) } }  \operatorname* { l i m } _ { n  \infty } { \frac { { \frac { 1 } { 2 { \sqrt { 2 } } } } ( 1 + { \sqrt { 2 } } ) ^ { n + 1 } } { { \frac { 1 } { 2 { \sqrt { 2 } } } } ( 1 + { \sqrt { 2 } } ) ^ { n } } } = 1 + { \sqrt { 2 } }
$$

Remark 3: Based on Theorem 3, under the condition of $n  \infty$ , the limiting ratio in the left MDET sequence is 2, which is the same as that in Jacobsthal numbers.

Remark 4: According to Theorem 4, when $n  \infty$ , the limiting ratio in the right MDET sequence is actually the silver ratio $1 + { \sqrt { 2 } }$ which is the same as that in Pell numbers.

# 4. Numerical examples

This section shows some examples to illustrate the presented maximum Deng entropy triangle (MDET) as well as the left and the right MDET sequences

Example 4.1. Assume that $n = 0 , 1 , 2 , 3 , . . . , 9 .$ ，Then,the associated Pascal's triangle and MDET are shown in Tables 2 and 3. It can be seen from the tables that Pascal's triangle has only one type of diagonal sum since it is symmetric. By contrast, because MDET is asymmetric, there exists two types of diagonal sum of MDET. Based on the diagonal sums, Fibonacci numbers (shown in Tables 2) and two MDET sequences (shown in Tables 3) can be obtained. As shown in the tables, because of the two types of diagonal sum of MDET shown in Eqs. (16) and (17), there are two different kinds of MDET sequences, namely the left MDET sequence $D ^ { L } ( n )$ and the right MDET sequence $D ^ { R } ( n )$ ：

Table 2: Pascal's triangle and Fibonacci numbers $F ( n )$   

<html><body><table><tr><td>n 0</td><td>F(n) 1</td><td</table></body></html>

Table 3: MDET, left MDET sequence $D ^ { L } ( n )$ , and right MDET sequence $D ^ { R } ( n )$   

<html><body><table><tr><td>n</td><td>DL(n)</td><td>DR(n)</td><td colspan="9">Maximum Deng entropy triangle</td></tr><tr><td>0</td><td>0</td><td>0</td><td colspan="18">0</td></tr><tr><td>1</td><td>0</td><td>1</td><td>0</td><td colspan="18">1</td></tr><tr><td>2</td><td>1</td><td>3</td><td>0</td><td colspan="18">2 3 9</td></tr><tr><td>3</td><td>2</td><td>9</td><td>0</td><td colspan="18">3</td></tr><tr><td>4</td><td>6</td><td>24</td><td>0</td><td>4</td><td>18</td><td>28</td><td></td><td>15</td><td></td><td colspan="6"></td><td></td><td>63</td></tr><tr><td>5</td><td>13 30</td><td>62</td><td>0</td><td>5</td><td></td><td>30</td><td>70</td><td></td><td>75</td><td>31</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>6</td><td></td><td>156</td><td></td><td>0</td><td>6</td><td>45</td><td>140</td><td>225</td><td></td><td>186</td><td></td><td>127</td><td></td><td></td><td></td><td></td></tr><tr><td>7</td><td>64</td><td>387</td><td></td><td>0 7</td><td></td><td>63</td><td>245</td><td>525</td><td></td><td>651</td><td>441</td><td>1016</td><td></td><td>255</td><td></td><td></td></tr><tr><td>8</td><td>137</td><td>951</td><td></td><td>0</td><td>8</td><td>84</td><td>392</td><td>1050</td><td></td><td>1736</td><td>1764</td><td></td><td></td><td>2295</td><td></td><td>511</td></tr><tr><td>9</td><td>286</td><td>2323</td><td></td><td>0</td><td>9</td><td>108</td><td>588</td><td></td><td>1890</td><td>3906</td><td>5292</td><td></td><td>4572</td><td></td><td></td><td></td></tr></table></body></html>

Example 4.2. Let n be from O to 10. Then, the illustrations of the trend for Pell numbers $P ( n ) .$ Fibonacci numbers $F ( n )$ , Jacobsthal numbers $J ( n )$ , left MDET sequence $\dot { D } ^ { L } ( n )$ , and right MDET sequence $D ^ { R } ( n )$ are shown in Figure 3. This example shows that $P ( n )$ and $D ^ { R } ( n )$ grow much faster than the other sequences,because the maximum characteristic roots of both $P ( n )$ and $D ^ { R } ( n )$ （20 are $1 + { \sqrt { 2 } } ,$ which is much larger than that of the other sequences. Although $D ^ { R } ( n )$ and $P ( n )$ have the same value of maximum characteristic root, $D ^ { R } ( n )$ grows faster than $P ( n )$ because the initial values of $D ^ { R } ( { \bf { \bar { n } } } ) ~ ( 0 , 1 , 3 , 9 )$ are larger than that of $P ( n ) \ ( 0 , 1 , 2 , 5 )$ . The growth rate of Fibonacci number sequence is the lowest， since the maximum characteristic root for Fibonacci numbers is $\textstyle { \frac { 1 + { \sqrt { 5 } } } { 2 } }$ ,whicismuchatfhc

![](images/23a4762a6ff69cbe3224cc90c9e40eef12e9d6fcc6668c2ca9ba911d60c9d6db.jpg)  
Figure 3: The trends fordifferent types of number sequences

Example 4.3. Given n from O to 100, the values of the ratio for two successive terms in Pell numbers $P ( n )$ , Fibonacci numbers $F ( n )$ , Jacobsthal numbers $J ( n ) _ { \cdot }$ , left MDET sequence $D ^ { L } ( n ) .$ and right MDET sequence $D ^ { R } ( n )$ are shown in Figure 4. It can be seen from the figure that, when n becomes more and more larger, the ratio for each sequence finaly converges to a certain value. The limiting ratio of $P ( n )$ and $D ^ { R } ( n )$ have the same value, which is the silver ratio. The limiting ratio of $J ( n )$ equals to that of $D ^ { L } ( n )$ , which is 2. The limiting ratio of $F ( n )$ is the golden ratio.

![](images/d031c56b3e399108527e130c5813629db869e015f3b10c22b20c407977965280.jpg)  
Figure 4: The ratio in different types of number sequences

# 5. Conclusion

Pascal's triangle is a mathematical form of combinatorial numbers. Based on Pascal's triangle,Fibonacci number sequence and the golden ratio can be generated. Similar to the golden ratio, silver ratio can be obtained based on Pell number sequence. Recently, the relations between Pascal's triangle and the maximum Deng entropy (MXDE) are studied and presented. A straightforward question comes: if we design a triangle based on MXDE, what will the associated number sequence and the limiting ratio be like? Hence, this paper proposes a novel triangle based on MXDE and analyzes its number sequence as well as limiting ratio. The major contributions of this paper are as follows:

· A Pascal-like triangle is proposed based on MXDE, which is called the maximum Deng entropy triangle (MDET).

· The number sequences based on MDET are investigated. The general term for the MDET sequence is presented and the limiting ratio in MDET sequence is analyzed. It is proved that the limiting ratio in the right MDET sequence converges to the silver ratio $1 + { \sqrt { 2 } }$   
· Numerical examples are given to expound MDET, and the MDET sequence is compared with several well-known number sequences.

# Acknowledgment

The work is partially supported by National Natural Science Foundation of China (Grant No. 61973332); JSPS Invitational Fellowships for Research in Japan (Short-term).

# Declaration of interest

Allthe authors certify that there is no conflict of interest with any individual or organization for this work.

# References

[1] H. Belbachir, L. Németh,L. Szalay, Hyperbolic pascal triangles, Applied Mathematics and Computation 273 (2016) 453-464.   
[2] J. Varnadore, Pascal's triangle and fibonacci numbers, The Mathematics Teacher 84 (1991) 314-319.   
[3] P. Catarino, On some identities for k-fibonacci sequence, Int. J. Contemp. Math. Sci 9 (2014) 37-42.   
[4] E. Ozkan, M. Tastan, A. Aydogdu, 3-fibonacci polynomials in the family of fibonacci numbers, Erzincan Universitesi Fen Bilimleri Enstitusu Dergisi 12 (2019).   
[5] T. Zhang, M. Cieslak,A. Owens, F. Wang, S. K. Broholm, T. H. Teeri, P. Elomaa, P. Prusinkiewicz， Phyllotactic patterning of gerbera flower heads, Proceedings of the National Academy of Sciences 118 (2021).   
[6] R. Thapa, Rhythm in architecture: An aesthetic appeal, Journal of the Institute of Engineering 13 (2017) 206-214.   
[7] R.A. Dunlap, The golden ratio and Fibonacci numbers, World Scientific, 1997.   
[8] i. Tugal, B. Sahin, A. Sahin, The shannon entropy of fibonacci numbers， MATI 4 (2022) 12-22.   
[9] P. Catarino, On some identities and generating functions for k-pell numbers, International Journal of Mathematical Analysis 7 (2013) 1877-1884.   
[10] Y. Deng, Random permutation set., International Journal of Computers, Communications & Control 17 (2022).   
[11] W.E. Lorenz,J. Andres,G. Franck, Fractal aesthetics in architecture, Applied Mathematics & Information Sciences 11 (2017) 971-981.   
[12] I. Craciun, D. Inoan, D. Popa,L. Tudose， Generalized golden ratios defined by means,Applied Mathematics and Computation 250 (2015) 221-227.   
[13] A. Cordero, J. L. Hueso, E.Martinez, J. R. Torregrosa, Efficient high-order methods based on golden ratio for nonlinear systems， Applied Mathematics and Computation 217 (2011) 4548-4556.   
[14] V. Krcadinac， A new generalization of the golden ratio， Fibonacci Quarterly 44 (2006) 335.   
[15] M. Ozkan, B.Peltek, A new structure on manifolds: silver structure, International Electronic Journal of Geometry 9 (2016) 59-69.   
[16] J. Bernat, Continued fractions and numeration in the fibonacci base, Discrete mathematics 306 (2006) 2828-2850.   
[17] C. Tsallis, Possible generalization of boltzmann-gibbs statistics, Journal of statistical physics 52 (1988) 479-487.   
[18] C. Tsallis, M. Gell-Mann, Y. Sato, Asymptotically scale-invariant occupancy of phase space makes the entropy sq extensive， Proceedings of the National Academy of Sciences 102 (2005) 15377-15382.   
[19] Y. Deng, Uncertainty measure in evidence theory， Science China Information Sciences 63 (2020) 1-19.   
[20] A. P. Dempster, Upper and lower probabilities induced by a multivalued mapping, The Annals of Mathematical Statistics 38 (1967) 325-339.   
[21] G. Shafer, A mathematical theory of evidence, volume 1, Princeton university press Princeton, 1976.   
[22] X. Gao, Y. Deng, The pseudo-pascal triangle of maximum Deng entropy, International Journal of Computers Communications & Control 15 (2020) 1006.   
[23] Y. Song, Y. Deng, Entropic explanation of power set, International Journal of Computers Communications & Control 16 (2021).   
[24] H. Liao, Z. Ren, R. Fang， A deng-entropy-based evidential reasoning approach for multi-expert multi-criterion decision-making with uncertainty, International Journal of Computational Intelligence Systems 13 (2020) 1281-1294.   
[25] F. Xiao, Generalization of dempster-shafer theory: A complex mass function, Applied Intelligence 50 (2020) 3266-3275.   
[26] H. Wang, Y.-P. Fang, E. Zio, Resilience-oriented optimal post-disruption reconfiguration for coupled traffic-power systems， Reliability Engineering & System Safety (2022) 108408.   
[27] N. Balakrishnan, F. Buono,M. Longobardi, A unified formulation of entropy and its application, Physica A: Statistical Mechanics and its Applications (2022) 127214.   
[28] J. Abellan， Analyzing properties of deng entropy in the theory of evidence, Chaos Solitons & Fractals 95 (2017) 195-199.   
[29] H. Cui, L. Zhou, Y. Li, B. Kang, Belief entropy-of-entropy and its application in the cardiac interbeat interval time series analysis, Chaos, Solitons & Fractals 155 (2022) 111736.   
[30] N. Balakrishnan, F. Buono,M. Longobardi， On cumulative entropies in terms of moments of order statistics，Methodology and Computing in Applied Probability 24 (2022) 345-359.   
[31] F. Buono, M.Longobardi, Adual measure of uncertainty: The deng extropy, Entropy 22 (2020).   
[32] N. Balakrishnan, F. Buono, M. Longobardi, On tsalis extropy with an application to pattern recognition, Statistics & Probability Letters 180 (2022) 109241.   
[33] Y. Deng, Information volume of mass function, International Journal of Computers Communications & Control 15 (2020) 3983.   
[34] J. Deng, Y. Deng, Information volume of fuzzy membership function, International Journal of Computers Communications & Control 16 (2021).   
[35] Q. Zhou, Y. Deng, Higher order information volume of mass function, Information Sciences 586 (2022) 501-513.   
[36] M.R.Kazemi, S.Tahmasebi,F. Buono,M.Longobardi, Fractional deng entropy and extropy and some applications, Entropy 23 (2021).   
[37] X. Gao, L. Pan, Y. Deng, A generalized divergence of information volume and its applications, Engineering Applications of Artificial Intelligence 108 (2022) 104584.   
[38] A. Coskun, N. Taskara，A note on the bi-periodic fibonacci and lucas matrix sequences, Applied Mathematics and Computation 320 (2018) 400-406.   
[39] W. M. Abd-Elhameed, Y. H. Youssri, N. El-Sissi, M. Sadek, New hypergeometric connection formulae between fibonacci and chebyshev polynomials, The Ramanujan Journal 42 (2017) 347-361.   
[40] W. M. Abd-Elhameed, N. Zeyada, New formulas including convolution, connection and radicals formulas of k-fibonacci and k-lucas polynomials, Indian Journal of Pure and Applied Mathematics (2022) 1-11.   
[41] S. Celik, 1. Durukan, E. Ozkan, New recurrences on pell numbers, pell-lucas numbers, jacobsthal numbers,and jacobsthal-lucas numbers, Chaos, Solitons & Fractals 150 (2021) 111173.   
[42] B. Kuloglu, E. Ozkan, Hyperbolic functions obtained from k-jacobsthal sequences, Asian-European Journal of Mathematics (2022) 2250178.