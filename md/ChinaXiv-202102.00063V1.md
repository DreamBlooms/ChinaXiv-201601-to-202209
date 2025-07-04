# Quantum entanglement measurement based on belief entropy\*

Yige Xue $\mathrm { a }$ , Yong Deng $^ { \mathrm { a , b } }$ ￥

$\boldsymbol { \mathscr { u } }$ InstituteofFundamental and Frontier Sciences,University of Electronic Science and Technologyof China，Chengdu,610054，China （20 $b$ School of Eduction, Shannri Normal University, Xian, 710o62, China $c$ School of Knowledge Science,Japan Advanced Institute of Science and Technology，Nomi, Ishikawa 923-1211,Japan

# Abstract

Partial entropy entanglement is a very popular method to measure the entanglement of quantum systems,which is based on the classic von Neumann entropy. However,because of the problem of classical von Neumann entropy in measuring the uncertainty of quantum systems, the partial entropy entanglement is not efficient enough to measure the entanglement of quantum systems. The new entropy measure of quantum uncertainty is a model for measuring the uncertainty of a quantum system based on the classic von Neumann entropy and belief entropy,which has higher performance than the classic von Neumann entropy in measuring the uncertainty entropy of a quantum system. Based on the new entropy measure of quantum uncertainty and the classic partial entropy entanglement, this paper proposes a new model to measure the quantum entanglement measurement,named quantum entanglement measurement based on belief entropy. When the new entropy measure of quantum uncertainty degenerates to classical von Neumann entropy, the quantum entanglement measurement based on belief entropy will degenerate to classical partial entropy entanglement. Numerical examples are used to prove that quantum entanglement measurement based on belief entropy is more efficient and reliable in measuring the entanglement of quantum systems than the classic partial entropy entanglement. The experimental results show that the quantum entanglement measurement based on belief entropy can measure the uncertainty of quantum systems more efficiently and reliably than the classical classic partial entropy entanglement.

Keywords: Quantum system, Belief entropy, Von Neumann entropy, Uncertainty,Entanglement,Partial entropy entanglement

# 1．Introduction

There is a lot of unknown information in the unknown world [1,2,3,4].In order to process unknown information, it is necessary to express the unknown first,so many scholars have proposed many mathematical methods and theories for expressing unknown information [5,6,7,8]. For example, Song et al. [9] proposed a novel combination method for temporal evidence. Pan et al. [10] proposed a new Pythagorean fuzzy sets and its similarity measure. After the unknown information is represented reasonably, many experts propose models and methods to deal with the unknown information [11,12,13]. For example, Deng and Jiang [14] applied the maximum uncertainty allocation to improve Dempster-Shafer belief structure. Garg et al. [15,16] used entropy theory to improve measurement methods under Pythagorean fuzzy environment. Prajapati and Saha [17] applied the entropy theory to predict next word in the text with the aid of language model. Abellan [18] analyzed the properties of belief entropy in evidential environment. Zhu [19] proposed the maximum value dimension and power law of belief distribution of the maximum belief entropy. Kang and Deng [20] proposed the maximum belief entropy. Gao and Deng [21] proposed the Pseudo-Pascal Triangle form for the maximum belief entropy.

Quantum theory is the most popular theory in recent years [22,23, 24, 25], and it has been studied by many experts [26, 27, 28]. A quantum system is a system based on quantum theory [29,30,31],which is different from traditional systems and has many characteristics [32, 33, 34]，such as quantum uncertainty, superposition of quantum states,and entanglement of quantum states [35,36,37]. So how to evaluate the entanglement of a quantum system has always been an important issue recognized by academia [38,39,40]. In response to this problem,many experts put forward their own methods and models to measure the entanglement of quantum systems [41,42,43]. For example Xavier and Rajabpour [44] proposed the entanglement and boundary entropy in quantum spin chains. Karabali [45] proposed a new entanglement entropy for integer quantum Hall effect under two and higher dimensions. Alimuddin et al.[46] studied the independence of entropy and work of equal-energetic finite quantum systems. Moitra and Sensarma [47] proposed the entanglement entropy of fermions from Wigner functions. Grimmett et al. [48] proposed the bounded entanglement entropy under quantum ising model. Verga and Elas [49] proposed the thermal state entanglement entropy under quantum graph.Hirano [50] proposed a new entanglement entropy for all orders in 1/N expansion. In these methods and models,partial entropy entanglement is one of the most popular models [51]. Many experts have conducted research on partial entropy entanglement [52]. For example,Han and Kye [53] proposed the convex cones under classifications of partial entanglement in the three qubit system.Huber et al. [54] proposed high-dimensional entanglement in states under positive partial transposition. Dwivedi et al. [55] proposed multi-boundary entanglement in Chern-Simons theory based on finite gauge groups. Shapourian and Ryu [56] proposed finite-temperature entanglement negativity of free fermions. Bauml et al. [57] studied the fundamental limits on the capacities of bipartite quantum

interactions.

Recently， Xue and Deng [58] proposed a new entropy measure of quantum system uncertainty,which is based on von Neumann entropy and belief entropy.Compared with the classical von Neumann entropy, the new entropy measure of quantum system uncertainty can better measure the uncertainty of quantum systems. Because the new entropy measure of quantum system uncertainty has advantages in measuring the uncertainty of quantum systems that the classical von Neumann entropy does not have, the new entropy measure of quantum system uncertainty has a good research prospect

This paper proposed the quantum entanglement measurement based on belief entropy,which is based on the new entropy measure of quantum system uncertainty and partial entropy entanglement. The proposed model requires the entanglement degree of the quantum system to be obtained from the uncertainty of the quantum system and its subsystems. In other words, the uncertainty of all subsystems of the quantum system minus the uncertainty of the quantum system divided by 2 is the entanglement of the quantum system. The advantage of the proposed model over partial entropy entanglement is that the proposed model is based on new entropy measure of quantum uncertainty. The new entropy measure of quantum uncertainty is a better model than the classical von Neumann entropy in measuring the uncertainty of quantum systems. When the new entropy measure of quantum uncertainty degenerates to classical von Neumann entropy, the quantum entanglement measurement based on belief entropy will degenerate to classical partial entropy entanglement.

The remaining of this paper is structured as follows. Section 2 introduces the preliminary. Section 3 presents the quantum entanglement measurement based on belief entropy. Section 4 illustrates the flexibility and accuracy of the quantum entanglement measurement based on belief entropy. Section 5 summarizes the whole paper.

# 2.Preliminaries

Quantum systems are full of uncertainties [59, 60,61]. In order to deal with these uncertainties,many models and theories have been proposed [62, 63,64].

# 2.1. Belief entropy

Given $m$ is a mass function on frame of discernment $X = \{ x _ { 1 } , \ldots , x _ { n } \}$ ，the definition of belief entropy is as follows:

Definition 2.1. (Belief entropy） [65]

$$
E _ { d } = - \sum _ { A \subseteq X } m ( A ) \log { \frac { m ( A ) } { 2 ^ { \left| A \right| } - 1 } }
$$

Belief entropy is the generalization of Shannon entropy [66].

# 2.2. Von Neumann Entropy

Quantum theory is a famous field 67,68,69],which has attracted the attention of many scholars [70,71, 72, 73]. Von Neumann entropy, as a classic method to evaluate the uncertainty of quantum systems,has attracted the attention and research of many scholars [74]. Given a density matrix, $\rho$ , the definition of von Neumann entropy of $\rho$ is as follows:

Definition 2.2. (Von Neumann Entropy） [75]

$$
S ( \rho ) = - T r [ \rho \ln \rho ]
$$

The von Neumann entropy also can be defined as follows:

$$
S ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i }
$$

where, $0 * \ln 0 = 0$ ： $\lambda _ { i } , i \in \{ 1 , 2 , \dots , m \}$ is the eigenvalue of $\rho$

2.3.A new entropy measure of quantum uncertainty

Definition 2.3.（ $\boldsymbol { \mathrm { \check { A } } }$ new entropy measure of quantum system uncertainty) [58] Given a density matrix, $\rho$ ，of a quantum system, the definition of the new entropymeasureof $\rho$ is as follow:

$$
D ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 }
$$

where, $\lambda _ { i }$ is the eigenvalue of $\rho$ ： $| \lambda _ { i } |$ is the cardinality of $\rho$ ，which means that $| \lambda _ { i } |$ represents how many orthogonal ground states the eigenvector corresponding to $\lambda _ { i }$ is composed of.

Example 2.1.Suppose the quantum system at this time is a pure state，as shown below:

$$
| \psi > = { \frac { 6 e ^ { i \alpha } } { 1 0 } } | 1 0 > + { \frac { 8 e ^ { i \alpha } } { 1 0 } } | 0 1 >
$$

where,

$$
| 1 0 > = \left( \begin{array} { l } { 0 } \\ { 1 } \\ { 0 } \\ { 0 } \end{array} \right) , | 0 1 > = \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 1 } \\ { 0 } \end{array} \right)
$$

The density matrix obtained from the above is as follows:

$$
\rho = | \psi > < \psi | = \left( \begin{array} { c c c c } { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \frac { 3 6 } { 1 0 0 } } } & { { \frac { 4 8 } { 1 0 0 } } } & { { 0 } } \\ { { 0 } } & { { \frac { 4 8 } { 1 0 0 } } } & { { \frac { 6 4 } { 1 0 0 } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } \end{array} \right)
$$

The eigenvalues and the corresponding eigenvectors of $\rho$ are in following Table 1:

Table 1: The eigenvalues and the corresponding eigenvectors of $\rho$   

<html><body><table><tr><td>Eigenvalues</td><td>1</td><td>0</td><td>0</td><td></td></tr><tr><td rowspan="5">Eigenvectors</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>0.6</td><td>0</td><td>0</td><td>0.8</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>0.8</td><td>0</td><td>0</td><td>-0.6</td></tr><tr><td>0</td><td>0</td><td>1</td><td>0</td></tr></table></body></html>

Relying on the equation of Eq.(4),the equations are obtained:

$$
D ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 } = l n 3
$$

# 2.4. Partial entropy entanglement

Definition 2.4. (Partial entropy entanglement) [51] Given a density matrix, $\rho$ ，of a quantum system, the definition of the partial entropy entanglement of $\rho$ is as follow:

$$
E _ { l } ( \rho _ { A B } ) = \frac { 1 } { 2 } \{ S ( \rho _ { A } ) + S ( \rho _ { B } ) - S ( \rho _ { A B } ) \}
$$

where, $S ( \rho _ { A } )$ ， $S ( \rho _ { B } )$ ， $S ( \rho _ { A B } )$ are the von Neumann entropy of subsystem $A$ ， subsystem $B$ and two-body quantum system $A B$ ，respectively.

# 3.The proposed method

The world is uncertain [76,77, 78],which causes a lot of issues [79, 80, 81]. The quantum system is flexibel,which means that more effective model should be proposed [82, 83, 84].

Definition 3.1. (Quantum entanglement measurement based on belief entropy) Given a density matrix, $\rho$ ，of a quantum system,the definition of the quantum entanglement measurement based on belief entropy of $\rho$ is as follow:

$$
E _ { D } ( \rho _ { A B } ) = \frac { 1 } { 2 } \{ D ( \rho _ { A } ) + D ( \rho _ { B } ) - D ( \rho _ { A B } ) \}
$$

where, $S ( \rho _ { A } )$ ， $S ( \rho _ { B } )$ ， $S ( \rho _ { A B } )$ are the new entropy measure of quantum uncertainty of subsystem $A$ ，subsystem $B$ and two-body quantum system $A B$ ，respectively.

The process of the proposed model to calculate the entanglement of a quantum system can be shown in Fig.1.

![](images/c877e662e31d594e7593ce25b223a72671e0e88458cb603e2f72eb9fb59fae2b.jpg)  
Figure 1: The calculation process of the proposed model

Theorem 3.1. When the new entropy measure of quantum uncertainty degenerates to classical von Neumann entropy, the quantum entanglement measurement based on belief entropy will degenerate to classical partial entropy entanglement.

Proof 3.1. Relying on the equations of Eq.(6), the equation is obtained:

$$
E _ { D } ( \rho _ { A B } ) = \frac { 1 } { 2 } \{ D ( \rho _ { A } ) + D ( \rho _ { B } ) - D ( \rho _ { A B } ) \}
$$

When the new entropy measure of quantum uncertainty degenerates to classical von Neumann entropy, we can obtain the following equation:

$$
\begin{array} { c } { { E _ { D } ( \rho _ { A B } ) = \displaystyle \frac { 1 } { 2 } \{ D ( \rho _ { A } ) + D ( \rho _ { B } ) - D ( \rho _ { A B } ) \} } } \\ { { = \displaystyle \frac { 1 } { 2 } \{ S ( \rho _ { A } ) + S ( \rho _ { B } ) - S ( \rho _ { A B } ) \} } } \\ { { = E _ { l } ( \rho _ { A B } ) } } \end{array}
$$

In this way, the quantum entanglement measurement based on belief entropy will degenerate to classical partial entropy entanglement. □

# 4.Numerical examples

Example 4.1. Suppose the quantum system at this time is a pure state，as shown below:

$$
| \psi > = \frac { 1 } { \sqrt { 2 } } | 0 0 > + \frac { 1 } { \sqrt { 2 } } | 1 1 >
$$

where,

$$
| 0 0 > = \left( \begin{array} { l } { 1 } \\ { 0 } \\ { 0 } \\ { 0 } \end{array} \right) , | 1 1 > = \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 0 } \\ { 1 } \end{array} \right)
$$

The density matrix obtained from the above is as follows:

$$
\rho _ { A B } = | \psi > < \psi | = \left( \begin{array} { c c c c } { { 1 / 2 } } & { { 0 } } & { { 0 } } & { { 1 / 2 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } \\ { { 1 / 2 } } & { { 0 } } & { { 0 } } & { { 1 / 2 } } \end{array} \right)
$$

The reduced density matrix of $\rho _ { A B } $ is as follows:

$$
\rho _ { A } = \left( \begin{array} { c c } { { 1 / 2 } } & { { 0 } } \\ { { 0 } } & { { 1 / 2 } } \end{array} \right) , \rho _ { B } = \left( \begin{array} { c c } { { 1 / 2 } } & { { 0 } } \\ { { 0 } } & { { 1 / 2 } } \end{array} \right)
$$

The eigenvalues and the corresponding eigenvectors of $\rho _ { A B } $ are in following Table 2:

Table 2: The eigenvalues and the corresponding eigenvectors of $\rho$   

<html><body><table><tr><td>Eigenvalues</td><td>0</td><td>0</td><td></td><td>0</td></tr><tr><td rowspan="5">Eigenvectors</td><td>0</td><td>0</td><td>0.7071</td><td>0.7071</td></tr><tr><td>0</td><td>1</td><td>0</td><td></td></tr><tr><td></td><td></td><td></td><td>0</td></tr><tr><td>-1</td><td>0</td><td>0</td><td>0</td></tr><tr><td>0</td><td>0</td><td>-0.7071</td><td>0.7071</td></tr></table></body></html>

Relying on the equation of Eq.(4), the equations are obtained:

$$
D ( \rho _ { A B } ) = \ln 3 , D ( \rho _ { A } ) = \ln 2 , D ( \rho _ { B } ) = \ln 2
$$

Relying on Eq.(6)， we get the entanglement degree of the quantum system $\rho _ { A B }$ as follows:

$$
E _ { D } ( \rho _ { A B } ) = \frac { 1 } { 2 } \{ D ( \rho _ { A } ) + D ( \rho _ { B } ) - D ( \rho _ { A B } ) \} = \frac { 1 } { 2 } \{ \ln 2 + \ln 2 - \ln 3 \}
$$

The comparison between the partial entropy entanglement and quantum entanglement measurement based on belief entropy is shown in following Table 3:

Table 3: The comparison of two models   

<html><body><table><tr><td>Partial entropy entanglement</td><td>The proposed model</td></tr><tr><td>ln2</td><td>1n</td></tr></table></body></html>

It can be seen from the above table that the proposed model is different from the partial entropy entanglement, which is related to the problem of von Neumann entropy in measuring the uncertainty of quantum systems.

Example 4.2. Suppose the quantum system at this time is a pure state,as shown below:

$$
| \psi > = \frac { 1 } { \sqrt { 3 } } | 0 0 > + \frac { 1 } { \sqrt { 3 } } | 0 1 > + \frac { 1 } { \sqrt { 3 } } | 1 0 >
$$

where,

$$
| 0 0 > = \left( \begin{array} { l } { 1 } \\ { 0 } \\ { 0 } \\ { 0 } \end{array} \right) , | 0 1 > = \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 1 } \\ { 0 } \end{array} \right) , | 1 0 > = \left( \begin{array} { l } { 0 } \\ { 1 } \\ { 0 } \\ { 0 } \end{array} \right)
$$

The density matrix obtained from the above is as follows:

$$
\rho _ { A B } = | \psi > < \psi | = \left( \begin{array} { c c c c } { { 1 / 3 } } & { { 1 / 3 } } & { { 1 / 3 } } & { { 0 } } \\ { { 1 / 3 } } & { { 1 / 3 } } & { { 1 / 3 } } & { { 0 } } \\ { { 1 / 3 } } & { { 1 / 3 } } & { { 1 / 3 } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } \end{array} \right)
$$

The reduced density matrix of $\rho _ { A B } { \bf \Psi }$ is as follows:

$$
\rho _ { A } = \left( \begin{array} { c c } { { 2 / 3 } } & { { 1 / 3 } } \\ { { 1 / 3 } } & { { 1 / 3 } } \end{array} \right) , \rho _ { B } = \left( \begin{array} { c c } { { 2 / 3 } } & { { 1 / 3 } } \\ { { 1 / 3 } } & { { 1 / 3 } } \end{array} \right)
$$

The eigenvalues and the corresponding eigenvectors of $\rho _ { A B }$ are in following Table 4:

Table 4: The eigenvalues and the corresponding eigenvectors of $\rho$   

<html><body><table><tr><td>Eigenvalues</td><td>0</td><td>0</td><td>0</td></tr><tr><td rowspan="5">Eigenvectors</td><td>0</td><td>-0.8026</td><td>-0.1498</td></tr><tr><td></td><td>0.5310</td><td>0.5774 0.5774</td></tr><tr><td>0</td><td></td><td>-0.6202 0.7700</td></tr><tr><td>0</td><td>0.2716</td><td>0.5774</td></tr><tr><td>1</td><td>0</td><td></td></tr></table></body></html>

Relying on the equation of Eq.(4), the equations are obtained:

$$
D ( \rho _ { A B } ) = \ln 7
$$

The eigenvalues and the corresponding eigenvectors of $\rho _ { A }$ and $\rho _ { B }$ are in following Table 5:

Table 5: The eigenvalues and the corresponding eigenvectors of $\rho _ { A }$   

<html><body><table><tr><td>Eigenvalues</td><td>0.1273 0.8727</td></tr><tr><td>Eigenvector s</td><td>0.5257 -0.8507 -0.8507 -0.5257</td></tr></table></body></html>

Relying on the equation of Eq.(4), the equations are obtained:

$$
D ( \rho _ { A } ) = D ( \rho _ { B } ) = 1 . 4 8
$$

Relying on Eq.(6)，we get the entanglement degree of the quantum system $\rho _ { A B }$ as follows:

$$
E _ { D } ( \rho _ { A B } ) = \frac { 1 } { 2 } \{ D ( \rho _ { A } ) + D ( \rho _ { B } ) - D ( \rho _ { A B } ) \} = \frac { 1 } { 2 } \{ 1 . 4 8 + 1 . 4 8 - \ln { 7 } \}
$$

The comparison between the partial entropy entanglement and quantum entanglement measurement based on belief entropy is shown in following Table $\it { 6 }$ ：

Table 6:The comparison of two models   

<html><body><table><tr><td>Partial entropy entanglement</td><td>The proposed model</td></tr><tr><td>ln2</td><td>0.93</td></tr></table></body></html>

It can be seen from the above table that the proposed model is different from the partial entropy entanglement, which is related to the problem of von Neumann entropy in measuring the uncertainty of quantum systems.

# 5.Conclusion

Partial entropy entanglement is a classic tool for measuring the entanglement of a quantum system. Partial entropy entanglement is based on von Neumann entropy, and von Neumann entropy has some problems in measuring the uncertainty of quantum systems,which leads to partial entropy entanglement is not efficient enough to measure the entanglement of quantum systems. This article proposes quantum entanglement measurement based on belief entropy，which is based on the partial entropy entanglement and the new entropy measure of quantum system uncertainty. Because the new entropy measure of quantum system uncertainty is based on the classic von Neumann entropy,and the new entropy measure of quantum system uncertainty is more efficient than von Neumann entropy in measuring the uncertainty of the quantum system. Therefore, quantum entanglement measurement based on belief entropy is more efficient and reasonable in measuring the entanglement of a quantum system than the classical partial entropy entanglement.Numerical examples are used to prove that the quantum entanglement measurement based on belief entropy is more efficient and reliable in measuring the entanglement of quantum systems than the classical partial entropy entanglement. The experimental results show that the quantum entanglement measurement based on belief entropy can measure quantum systems more efficiently and reliably than the classical partial entropy entanglement.

# Acknowledgment

The work is partially supported by National Natural Science Foundation of China (Grant No. 61973332)，JSPS Invitational Fellowships for Research in Japan (Short-term).

[1] S.Abdel-Khalek，E. Khalil，A.-B. Mohamed，M. Abdel-Aty，H. Besbes,Response of quantum fisher information， variance entropy squeezing and entanglement to the intrinsic decoherence of two non-degenerate fields interacting with two qubits,Alexandria Engineering Journal 59. doi:10.1016/j.aej.2020.09.044.   
[2] S.Dwivedi,V. Singh,P.Ramadevi, Y. Zhou, S.Dhara, Entanglement on multiple $s ^ { 2 }$ boundaries in chern-simons theory, Journal of High Energy Physics 2019. doi:10.1007/JHEP08(2019)034.   
[3] V.Alba, P. Calabrese,E. Tonni, Entanglement spectrum degeneracy and cardy formula in 1+1 dimensional conformal field theories,Journal of Physics A: Mathematical and Theoretical 51. doi:10.1088/1751-8121/ aa9365.   
[4] R.Gielerak,M. Sawerwain, Quantum information & computation 20 (2020) 1081-1108.   
[5] I. Dzitac, F.G. Filip,M.-J. Manolescu, Fuzzy logic is not fuzzy: Worldrenowned computer scientist lotfi a. zadeh, International Journal of Computers Communications & Control 12(6) (2017) 748-789.   
[6] E. Kaur, M. Wilde,Amortized entanglement of a quantum channel and approximately teleportation-simulable channels, Journal of Physics A: Mathematical and Theoretical 51. doi:10.1088/1751-8121/aa9da7.   
[7] X.Gao, L. Pan, Y. Deng, Quantum Pythagorean Fuzzy Evidence Theory (QPFET):A Negation of Quantum Mass Function View, IEEE Transactions on Fuzzy Systems(2021） 10.1109/TFUZZ.2021.3057993.   
[8] P.Padmanabhan,F. Sugino,D. Trancanelli,Generating w states with braiding operators, Quantum information & computation 20 (2020) 1154- 1162.   
[9] Y. Song, J. Zhu, L. Lei， X. Wang,A self-adaptive combination method for temporal evidence based on negotiation strategy， SCIENCE CHINA Information Sciences 10.1007/s11432-020-3045-5.   
10] L.Pan,X. Gao,Y. Deng,K.H. Cheong，The constrained Pythagorean fuzzy sets and its similarity measure ,IEEE Transactions on Fuzzy Systems (2021）10.1109/TFUZZ.2021.3052559.   
11] J.Angel-Ramelli, Entanglement entropy of excited states in the quantum lifshitz model, Journal of Statistical Mechanics: Theory and Experiment 2021.doi:10.1088/1742-5468/abcd35.   
[12] M. Berta,M.Wilde,Amortization does not enhance the max-rains information of a quantum channel, New Journal of Physics 2O. doi: 10.1088/1367-2630/aac153.   
[13] Y.Xue，Y. Deng,Decision making under measure-based granular uncertainty with intuitionistic fuzzy sets, Applied Intelligence (2021) 10.1007/s10489-021-02216-6.   
[14] X. Deng,W. Jiang, On the negation of a dempster-shafer belief structure based on maximum uncertainty allocation, Information Sciences 516 (2020) 346-352. doi:10.1016/j.ins.2019.12.080.   
[15] T. Athira， S. J. John，H. Garg，Entropy and distance measures of pythagorean fuzzy soft sets and their applications, Journal of Intelligent & Fuzzy Systems 37 (3) (2019) 4071-4084.   
[16] T.Athira, S.J. John,H.Garg,A novel entropy measure of pythagorean fuzzy soft sets,AIMS Mathematics 5(2)(2020)1050-1061.   
[17] G. L. Prajapati, R. Saha, Reeds: Relevance and enhanced entropy based dempster shafer approach for next word prediction using language model, Journal of Computational Science 35（2019) 1-11. doi:10.1016/j.jocs. 2019.05.001.   
[18] J.Abellän,Analyzing properties of deng entropy in the theory of evidence, Chaos，Solitons & Fractals 95(2017) 195-199. doi:10.1016/j.chaos. 2016.12.024.   
[19] R. Zhu,J.Chen,B.Kang,Power law and dimension of the maximum value for belief distribution with the maximum deng entropy, IEEE Access 8(2020) 47713-47719. doi:10.1109/ACCESS.2020.2979060.   
[20] B.Kang，Y.Deng,The maximum deng entropy, IEEE Access 7 (2019) 120758-120765.doi:10.1109/ACCESS.2019.2937679.   
[21] X. Gao, Y. Deng, The pseudo-pascal triangle of maximum deng entropy., International Journal of Computers, Communications & Control 15 (1).   
[22] R. Juhasz,J. Oberreuter, Z. Zimbors,Entanglement entropy of disordered quantum wire junctions, Journal of Statistical Mechanics: Theory and Experiment 2018 (2018) 123106.doi:10.1088/1742-5468/aaeda2.   
[23] H. Jahromi, S. Haseli, Quantum memory and quantum correlations of majorana qubits used for magnetometry, Quantum information & computation 20(2020) 935-956.   
[24] M. Mosca,Cybersecurity in an era with quantum computers: Will we be ready?,IEEE Security Privacy 16 (5) (2018) 38-41. doi:10.1109/MSP. 2018.3761723.   
[25] H. Al-Ameri, M. Abdullah,A.Al-khursan,Entanglement in ladder-plus-y double quantum dot structure via entropy, Applied Optics 58 (2019) 369. doi:10.1364/A0.58.000369.   
[26] J. Montanez, C. Damian,M. von Spakovsky， S. Cano-Andrade, Loss-ofentanglement prediction of a controlled-phase gate in the framework of steepest-entropy-ascent quantum thermodynamics,Physical Review A 101. doi:10.1103/PhysRevA.101.052336.   
[27] R. Sohal, B. Han, L. Santos, J. Teo, Entanglement entropy of generalized moore-read fractional quantum hall state interfaces,Physical Review B 102.doi:10.1103/PhysRevB.102.045102.   
[28] S.Mehrabankar, D.Afshar, M. Jafarpour,Quantum fidelity evolution of penning trap coherent states in an asymmetric open quantum system, Quantum information & computation 19 (2019) 413-0423.   
[29] A. Feller,E.Livine, Entanglement entropy and correlations in loop quantum gravity, Classical and Quantum Gravity 35. doi :10.1088/1361-6382/ aaa27c.   
[30] C. Pagani,M. Reuter, Finite entanglement entropy in asymptotically safe quantum gravity， Journal of High Energy Physics 2018. doi:10.1007/ JHEP07(2018)039.   
[31] B. Nash,V.Gheorghiu,M.Mosca,Quantum circuit optimizations for nisq architectures,Quantum Science and Technology 5. doi:10.1088/ 2058-9565/ab79b1.   
[32] Y. Nakata, M. Murao, Generic entanglement entropy for quantum states with symmetry, Entropy 22 (2020) 684. doi:10.3390/e22060684.   
[33] H. Pakarzadeh, Z. Norouzi, J. Vahedi, Time evolution of entanglement in a four-qubit heisenberg chain,Quantum information & computation 20 (2020） 736-0746.   
[34] L. F. Quezada, E. Nahmad-Achar, Entropy of entanglement between quantum phases of a three-level matter-radiation interaction model, Entropy 20. doi:10.3390/e20020072.   
[35] S. M. Chandran, S. Shankaranarayanan, Divergence of entanglement entropy in quantum systems: Zero-modes, Physical Review D 99. doi: 10.1103/PhysRevD.99.045010.   
[36] E.Bianchi,P.Dona,I. Vilensky，Entanglement entropy of bell-network states in loop quantum gravity:Analytical and numerical results,Physical Review D 99. doi:10.1103/PhysRevD.99.086013.   
[37] R.Mengoni, A. Di Pierro, L. Memarzadeh, S.Mancini, Persistent homology analysis of multiqubit entanglement, Quantum information & computation 20 (2020) 375-399.   
[38] A.Belenchia,D.Benincasa,M.Letizia,S.Liberati, On the entanglement entropy of quantum fields in causal sets,Classical and Quantum Gravity 35. doi:10.1088/1361-6382/aaae27.   
[39] M.-C. Cha, M.-H. Chung,Local entanglement entropy of fermions as a marker of quantum phase transition in the one-dimensional hubbard model, Physica B: Condensed Matter 536. doi:10.1016/j.physb.2017.08.046.   
[40] J.Ardenghi, Entanglement entropy between virtual and real excitations in quantum electrodynamics, International Journal of Modern Physics A 33. doi:10.1142/S0217751X18500811.   
[41] D.Ronquillo,A. Vengal, N. Trivedi， Signatures of magnetic-field-driven quantum phase transitions in the entanglement entropy and spin dynamics of the kitaev honeycomb model, Physical Review B 99. doi:10.1103/ PhysRevB.99.140413.   
[42] D.-S.Lee,C.-P. Yeh,Time evolution of entanglement entropy of moving mirrors influenced by strongly coupled quantum critical fields,Journal of High Energy Physics 2019. doi:10.1007/JHEP06(2019)068.   
[43] D. Solenov, Quantum walks as mathematical foundation for quantum gates, Quantum information & computation 20 (2020) 230-258.   
[44] J. Xavier, M. Rajabpour, Entanglement and boundary entropy in quantum spin chains with arbitrary direction of the boundary magnetic fields, Physical Review B10l. doi:10.1103/PhysRevB.101.235127.   
[45] D. Karabali, Entanglement entropy for integer quantum hall effect in two and higher dimensions, Physical Review D 102. doi:10.1103/PhysRevD. 102.025016.   
[46] M. Alimuddin, T. Guha, P. Parashar, Independence of work and entropy for equal-energetic finite quantum systems: Passive-state energy as an entanglement quantifier, Physical Review E 102. doi:10.1103/PhysRevE. 102.012145.   
[47] S.Moitra,R. Sensarma, Entanglement entropy of fermions from wigner functions: Excited states and open quantum systems, Physical Review B 102. doi:10.1103/PhysRevB.102.184306.   
[48] G.Grimmett,T. Osborne,P. Scudo, Bounded entanglement entropy in the quantum ising model, Journal of Statistical Physics 178 (2020) 281-296. doi:10.1007/s10955-019-02432-y.   
[49] A.Verga,R. Elas,Thermal state entanglement entropy on a quantum graph, Physical Review E 100. doi:10.1103/PhysRevE.100.062137.   
[50] S.Hirano, Quantum holographic entanglement entropy to all orders in 1/n expansion, Progress of Theoretical and Experimental Physics 2020. doi: 10.1093/ptep/ptaa019.   
[51] C.Bennett，H. Bernstein，S.Popescu,B. Schumacher，Concentrating partial entanglement by local operations,Physical Review A 53. doi: 10.1103/PhysRevA.53.2046.   
[52] K.H. Han, S.-H. Kye, Construction of three-qubit biseparable states distinguishing kinds of entanglement in a partial separability classification, Physical Review A 99. doi:10.1103/PhysRevA.99.032304.   
[53] K. Han, S.-H. Kye, On the convex cones arising from classifications of partial entanglement in the three qubit system 53.doi:10.1088/1751-8121/ ab5593.   
[54] M. Huber,L. Lami, C. Lancien，A.Mller-Hermes,High-dimensional entanglement in states with positive partial transposition, Physical Review Letters 121. doi:10.1103/PhysRevLett.121.200503.   
[55] S.Dwivedi,A. Addazi, Y. Zhou, P. Sharma, Multi-boundary entanglement in chern-simons theory with finite gauge groups, Journal of High Energy Physicsdoi:10.1007/JHEP04(2020)158.   
[56] H. Shapourian, S. Ryu, Finite-temperature entanglement negativity of free fermions, Journal of Statistical Mechanics: Theory and Experiment 2019 (2019) 043106.doi:10.1088/1742-5468/ab11e0.   
[57] S.Bauml, S. Das,M. Wilde,Fundamental limits on the capacities of bipartite quantum interactions,Physical Review Letters 121. doi:10.1103/ PhysRevLett.121.250504.   
[58] Y. Xue, Y. Deng, A new entropy measure of quantum system uncertainty, chinaXiv（2021） 10.12074/202102.00030.   
[59] G. Sarantoglou, M. Skontranis,C. Mesaritakis,All optical integrate and fire neuromorphic node based on single section quantum dot laser, IEEE Journal of Selected Topics in Quantum Electronics 26 (2020) 1-10. doi: 10.1109/JSTQE.2019.2945549.   
[60] J.Deng,Y. Deng, Information volume of fuzzy membership function, International Journal of Computers Communications & Control 16 (1) (2021) 4106.doi:https://doi.org/10.15837/ijccc.2021.1.4106.   
[61] T.Maslowski,N. Sedlmayr, Quasiperiodic dynamical quantum phase transitions in multiband topological insulators and connections with entanglement entropy and fdelity susceptibility, Physical Review B 101. doi: 10.1103/PhysRevB.101.014301.   
[62] J. Anaya Contreras, H. Moya-Cessa,A. Ziga-Segundo, The von neumann entropy for mixed states,Entropy 21 (2019) 49. doi:10.3390/e21010049.   
[63] A. Prudenziati,A geodesic witten diagram description of holographic entanglement entropy and its quantum corrections, Journal of High Energy Physics 2019. doi:10.1007/JHEP06(2019)059.   
[64] X. Feng，W.Wei,R. Zhang,J. Wang,Y. Shi, Z. Zheng，Exploring the heterogeneity for node importance by von neumann entropy, Physica A: Statistical Mechanics and its Applications 517. doi:10.1016/j.physa. 2018.11.019.   
[65] Y. Deng, Deng entropy, Chaos, Solitons & Fractals 91 (2016) 549-553.   
[66] S.Li, F.Xiao,J.H.Abawajy, Conflict management of evidence theory based on belief entropy and negation, IEEE Access 8 (2020) 37766-37774. doi:10.1109/ACCESS.2020.2975802.   
[67] W.Donnelly, E. LePage,Y.-Y.Li, A. Pereira,V. Shyam，Quantum corrections to finite radius holography and holographic entanglement entropy, Journal of High Energy Physics 2020. doi:10.1007/JHEP05(2020)006.   
[68] F.Leditzky, N.Datta,G. Smith,Useful states and entanglement distillation,IEEE Transactions on Information Theory 64(7) (2018） 4689-4708. doi:10.1109/TIT.2017.2776907.   
[69] H. Shapourian, S. Ryu,Entanglement negativity of fermions: Monotonicity, separability criterion,and classification of few-mode states,Physical Review A 99. doi:10.1103/PhysRevA.99.022310.   
[70] C. Bannwarth，S.Ehlert，S. Grimme, Gfn2-xtban accurate and broadly parametrized self-consistent tight-binding quantum chemical method with multipole electrostatics and density-dependent dispersion contributions,Journal of chemical theory and computation 15 (3) (2019) 1652-1671. doi:10.1021/acs.jctc.8b01176.   
[71] F. Leditzky, C. Rouz, N. Datta, Data processing for the sandwiched rnyi divergence:a condition for equality,Letters in Mathematical Physics 107. doi:10.1007/s11005-016-0896-9.   
[72] M. Mosca, J. M. Vensi Basso, S. Verschoor, On speeding up factoring with quantum sat solvers, Scientific reports 10 (2020) 15022. doi:10.1038/ s41598-020-71654-y.   
[73] D.Abo-Kahla,A.Farouk，Entanglement and entropy of a three-qubit system interacting with a quantum spin environment，Applied Sciences 9(2019) 5222.doi:10.3390/app9235222.   
[74] M. Gal, Maps on quantum states in $c ^ { * }$ -algebras preserving von neumann entropy or schatten $p$ -norm of convex combinations, Canadian Mathematical Bulletin 62(2019) 1-6. doi:10.4153/CMB-2018-011-3.   
[75] J. Von Neumann,Mathematical Foundations of Quantum Mechanics,1955.   
[76] J. Ur Rehman， H. Shin， Purity-based continuity bounds for von neumann entropy， Scientific Reports 9 (2019） 1-9. doi:10.1038/ s41598-019-50309-7.   
[77] P.Padmanabhan,F. Sugino,D.Trancanelli, Quantum entanglement,supersymmetry,and the generalized yang-baxter equation,Quantum information & computation 20(2020) 37-64.   
[78] Z. Liu, Y. Deng,R.R. Yager, Measure-based Group Decision Making with Principle-guided Social Interaction Influence for Incomplete Information: A Game Theoretic Perspective,IEEE Transactions on Fuzzy Systems (2021) 10.1109/TFUZZ.2021.3053324doi:{10.1109/TFUZZ.2021.3053324}.   
[79] K.Panigrahi,P. Howli，K.K. Chattopadhyay， 3d network of v2o5 for flexible symmetric supercapacitor, Electrochimica Acta 337 (202O) 135701. doi:10.1016/j.electacta.2020.135701.   
[80] P.Ruggiero，P.Calabrese，Relative entanglement entropies in 1+1- dimensional conformal field theories, Journal of High Energy Physics 2017. doi:10.1007/JHEP02(2017)039.   
[81] H. Adnane,M. Paris,Teleportation improvement by non-deterministic noiseless linear amplification，Quantum information & computation 19 (2019) 935-951.   
[82] X.Gao, Y. Deng,Quantum Model of Mass Function , International Journal of Intelligent Systems 35(2) (2020) 267-282.   
[83] J.Dai,Y.Deng，A new method to predict the interference effect in quantum-like bayesian networks,Soft Computing(2020) 1-8doi:10 .1007/ s00500-020-04693-2.   
[84] G. Mbeng,V.Alba,P. Calabrese, Negativity spectrum in 1d gapped phases of matter, Journal of Physics A: Mathematical and Theoretical 5O. doi: 10.1088/1751-8121/aa6734.