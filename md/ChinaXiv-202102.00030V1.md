# A new entropy measure of quantum system uncertainty

Yige Xue $\mathbf { \nabla } \cdot \mathbf { \varepsilon }$ Yong Deng

Received: date /Accepted:date

Abstract Quantum theory is currently the most important research field. Before processing the information of a quantum system,we must first understand how to measure the uncertainty of a quantum system. Von Neumann entropy is a very classic method to measure the uncertainty of quantum systems.However, due to the particularity of quantum systems,it is very diffcult to measure the uncertainty of quantum systems, so that the measurement efficiency of the classical von Neumann entropy is not high in some cases. Based on the classic von Neumann entropy and belief entropy, this paper proposes a new entropy model to measure the uncertainty of quantum systems,which can use fully the eigenvalues and eigenvectors of the density matrix of quantum systems,and give the uncertainty of the quantum system. Some numerical examples are used to prove that the proposed entropy is more efficient and reliable in measuring quantum systems than the classical von Neumann entropy. The experimental results show that the proposed entropy can measure the uncertainty of quantum systems more effciently and reliably than the classical von Neumann entropy.

Keywords Quantum system $\mathbf { \nabla } \cdot \mathbf { \varepsilon }$ Belief entropy $\mathbf { \nabla } \cdot \mathbf { \varepsilon }$ Von Neumann entropy $\mathbf { \nabla } \cdot \mathbf { \varepsilon }$ Uncertainty

# 1 Introduction

Human beings live in an unknown world. Boutabba and Eleuch (2O2O); Romagnoli (2019);Valero-Toranzo et al (2O18). To address these uncertain issues,many models and methods have been proposed de Lima Bernardo (2O2O);Luis et al (2016); Pan et al (2O2O),such as quantum theory Berrada and Eleuch (2O21); Chakraborty et al (202O); Yurischev (2O18),complex networks,Dempster-Shafer evidence theory Turhan and Demirekler (2017), Information Volume Deng (202Oa); Li et al (2021), information entropy Alkassar et al (2O2O); Gupta and Richhariya (2O18); Karci (2016) belief entropy Anjaria (2O2O); Romagnoli (2O2O)，game theory Koh and Cheong (2019); Wang et al (2O18) and von Neumann entropy Farhadinia and Xu (2018); Longo and Xu (2O2O); ur Rehman and Shin (2O19). Deng and Jiang Deng and Jiang (2020） applied the maximum uncertainty allocation to improve Dempster-Shafer belief structure. Jaunzemis et al Jaunzemis et al (2O19) used the judical evidential reasoning to gather evidence information of hypothesis resolution.Pedrycz and Bargiela Pedrycz and Bargiela (2OO3) applied the fuzzy membership function to improve the fuzzy modeling method of fuzzy fractal dimension.Khan and Anwar Khan and Anwar (2O19) applied the weighted evidence and Dempster-Shafer combination rule to improve time-domain data fusion and applied the proposed model to classify objects.Among these theories and models,a belief entropy Deng (2O2Ob),named as Deng entropy,is an extend of information entropy,which can evaluate uncertainties more flexible than information entropy Huang et al (2O19);Wang et al (2019). Relying on the advantages on representing uncertainty,the belief entropy has been widely studied by scholars Ozkan (2O18); Pan and Deng (2O2O). Zhu Zhu et al (2020) proposed the maximum value dimension and power law of belief distribution of the maximum belief entropy. Gao and Deng Gao and Deng (2O2O) proposed the PseudoPascal Triangle form for the maximum belief entropy.Liu et al.Liu et al (2019) applied generalized belief entropy to identify conflict evidence.

Quantum system is a very complex and interesting system Carrijo and Avelar (2019); Kurzyk et al (2O18), because quantum entanglement and other phenomena exist in quantum system, so it is more complicated than general system Abdel-Khalek et al (2O2Ob); Perez-Bernal et al (2O2O). In other words, quantum systems have great uncertainty due to their characteristics such as the principle of state superposition and the principle of uncertainty Alkhateeb and Abdel-Khalek (2O2O); Luis and Rodil (2013).The principle of state superposition makes multiple quantum states of a quantum system entangled together,and the quantum state of the quantum system is unpredictable before the quantum state collapses Abdel-Khalek et al (2O2Oa); Gaonkar et al (2O21); Mukhamedov and Watanabe (2O18).Entropy theory is also used to measure the uncertainty of quantum systems Rastegin (2O12); Zozor et al (2O13). Steeve et al. Zozor et al (2O14) proposed general entropy-like uncertainty relations under finite dimensions.Vladimir Majernik (2Oo8) expressed the uncertainty relation by means of a new entropic function. Von Neumann Von Neumann (1955) proposed the von Neumann entropy,which has been used to measure the uncertainty of quantum systems. Specifically, to measure the uncertainty of a quantum system by von Neumann entropy,it is necessary to find the density matrix corresponding to the quantum system first Boes et al (2O19),and then calculate its eigenvalues and eigenvectors according to that density matrix Kontopoulou et al (2O2O); Prunkl (202O); Zhu (2020). Based on the obtained eigenvalues, the von Neumann entropy of the quantum system can be determined Duboscq and Pinaud (2O2O); Sakamoto and Tanimura (2020). But after our research,we found that von Neumann entropy is not as effective as imagined when measuring some quantum systems.The reason is that we believe that von Neumann entropy only relies on the eigenvalues of the density matrix, because eigenvectors can also represent the internal information of a density matrix,and the calculation of von Neumann entropy does not rely on eigenvectors.At the same time, quantum states are based on complex numbers,so measuring the uncertainty of a quantum system is more difficult than measuring the uncertainty of a general system.

This paper proposes a new entropy measure of quantum system uncertainty, which is based on von Neumann entropy and belief entropy. The proposed entropy makes full use of the eigenvalues and eigenvectors of the density matrix. In other words, the proposed entropy can fully extract the information of the density matrix representing the quantum system and is effcient To evaluate the uncertainty of quantum systems.When the cardinalities of the eigenvectors of the density matrix are all 1, the proposed entropy will degenerate into the classic von Neumann entropy. Some numerical examples are used to verify the efficiency and reliability of the proposed entropy. The experimental results show that the proposed entropy has higher performance and reliability than the classical von Neumann entropy in measuring the uncertainty of quantum systems.

The remaining of this paper is structured as follows. Section 2 introduces the preliminary. Section 3 presents the new entropy measure of quantum system uncertainty. Section 4 illustrates the flexibility and accuracy of the new entropy measure of quantum system uncertainty. Section 5 summarizes the whole paper.

# 2Preliminaries

Quantum systems are full of uncertainties Deng et al (2O18); Rastegin (2O15); Sarantoglou et al (2O2O). To address these uncertain issues,many models and methods have been proposed Anaya Contreras et al (2O19); Deng and Deng (2O21); Feng et al (2019).

# 2.1 Density Matrix

The definition of density matrix, $\rho$ ,of a quantum system in Pure State, $\left| \varphi \right.$ ,as follows:

Definition 1 (The Density Matrix of Pure State) Johnson and Horn (1985)

$$
\rho = | \varphi \rangle \langle \varphi |
$$

The definition of density matrix, $\rho$ , of a quantum system in Mixed State, $\left| \varphi \right.$ ,as follows:

Definition 2 (The Density Matrix of Mixed State) Johnson and Horn(1985)

$$
\rho = \sum _ { i } P _ { i } | \varphi _ { i } \rangle \langle \varphi _ { i } |
$$

where, $\left\{ { P } _ { i } , \left| \varphi _ { i } \right. \right\}$ is the state and probability of the system.

# 2.2 Von Neumann Entropy

Von Neumann entropy, as a classic method to evaluate the uncertainty of quantum systems Bannwarth et al (2O19); Mukhamedov et al (2O2O),has atracted the attention and research of many scholars Gal (2O19). Given a density matrix, $\rho$ , the definition of von Neumann entropy of $\rho$ is as follows:

Definition 3 (Von Neumann Entropy） Von Neumann (1955)

$$
S ( \rho ) = - T r [ \rho \ln \rho ]
$$

The Eq.(3) can be defined as follows:

$$
S ( \boldsymbol { \rho } ) = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i }
$$

where, $0 * \ln 0 = 0 . \lambda _ { i } , i \in \left\{ 1 , 2 , . . . , m \right\}$ is the eigenvalue of $\rho$ （2

# 2.3 Belief entropy

Given $n$ is a mass function under frame of discernment $Y$ ,the definition of belief entropy is as follows:

Definition 4 (Belief entropy) Deng (2020b)

$$
E _ { d } = - \sum _ { C \subseteq Y } n ( C ) \log { \frac { n ( C ) } { 2 ^ { \left| C \right| } - 1 } }
$$

where, $| C |$ is the cardinality of $C$

# 3 A new entropy measure of quantum system uncertainty

The world is uncertain Berrada and Al-Rajhi (2O17); Yurischev (2O17),which causes a lot of issues Ion and Ion (2OO1); Panigrahi et al (2O2O); Ur Rehman and Shin (2019). The quantum system is flexibel, which means that more effective model should be proposed Dai and Deng (202O); Gao and Deng (202O); Guha and Das (2018). The von Neumann entropy can evaluate the uncertainty of quantum system effectively, which is based on the density matrix.However, the density matrix is difficult to predict, so the von Neumann entropy has limitations in evaluating quantum system. As we all know, the belief entropy has high performance in indicating uncertainty.

According to the principle of quantum state superposition, the state of a quantum system is composed of the superposition of orthogonal ground states,and the superposition weight of the orthogonal ground states is complex Jauregui et al (2018); Majernik et al (2OO3); Zozor et al (2Oo8). The complex number itself has a high degree of uncertainty, so the classical von Neumann entropy cannot correctly measure the uncertainty of some quantum systems Balazadeh et al (2O2O); Benabdallah et al (2O2O).In view of the problems of classical von Neumann entropy in measuring quantum systems, this paper proposes a new entropy measure of quantum system uncertainty,which is based on belief entropy. The proposed entropy can not only efficiently measure the quantum system that can be measured by classical von Neumann entropy, but also can measure the quantum system that cannot be measured by classical von Neumann entropy. Because belief entropy can effectively measure the uncertainty of unknown systems,this section uses belief entropys ideas to propose a entropy measure of quantum system uncertainty.

Definition 5 (A new entropy measure of quantum system uncertainty) Given a density matrix, $\rho$ ,of a quantum system,the definition of the new entropy measure of $\rho$ is as follow:

$$
D ( \boldsymbol { \rho } ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 }
$$

where, $\lambda _ { i }$ is the eigenvalue of $\rho . \ | \lambda _ { i } |$ is the cardinality of $\rho$ ，which means that $| \lambda _ { i } |$ represents how many orthogonal ground states the eigenvector corresponding to $\lambda _ { i }$ is composed of.

Example $\boldsymbol { { \mathit { 1 } } }$ Assume the density matrix $\rho$ has an eigenvector: $| \psi > = \alpha | 1 0 > + \beta | 0 1 >$ with eigenvalue $\lambda _ { i }$ ,which consists of two orthogonal ground states $| 1 0 >$ and $| 0 1 >$ as follows:

$$
| 1 0 > = \left( \begin{array} { l } { 0 } \\ { 1 } \\ { 0 } \\ { 0 } \end{array} \right) , | 0 1 > = \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 1 } \\ { 0 } \end{array} \right)
$$

Then the $| \lambda _ { i } | = 2$

Theorem1 When all the eigenvectors of the density matrix of a quantum system consist of only one orthogonal ground state,then the proposed entropy degenerates to the classical von Neumann entropy.

Proof Relying on the equations of Eq.(6), the equation is obtained:

$$
D ( \boldsymbol { \rho } ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 }
$$

Since the all the eigenvectors of the density matrix of a quantum system consist of only one orthogonal ground state, then we can obtain that $| \lambda _ { i } | = 1$ for $i \in \{ 1 , 2 , \ldots , m \}$ Hence,the following equation can be obtained:

$$
D ( \boldsymbol { \rho } ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 } = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i }
$$

In this way, the proposed entropy degenerates to the classical von Neumann entropy. □

Given a quantum system, suppose it has four eigenvalues at this time,denoted as $\lambda _ { 1 }$ ， $\lambda _ { 2 }$ ， $\lambda _ { 3 }$ ， $\lambda _ { 4 }$ and the eigenvectors corresponding to these eigenvalues are denoted as $\alpha _ { 1 }$ ， $\alpha _ { 2 }$ ， $\alpha _ { 3 }$ ， $\alpha _ { 4 }$ . The calculation process of the proposed entropy of this quantum system can be shown in Fig. 1.

![](images/41041e8d6c6e5df5243dfedf1f82e942c17da11ad0f71955250644175ac955d1.jpg)  
Fig.1 The calculation process of the proposed entropy

# 4 Numerical examples

Numerical examples has been designed to verify the advantages of the proposed entropy compared to classical von Neumann entropy in measuring the uncertainty of various types of quantum systems.

Example 2 Suppose the quantum system at this time is a pure state, as shown below:

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

The eigenvalues and the corresponding eigenvectors of $\rho$ are in following Table l:

Table 1 The eigenvalues and the corresponding eigenvectors of $\rho$   

<html><body><table><tr><td>Eigenvalues</td><td colspan="4">1</td></tr><tr><td rowspan="3">Eigenvectors</td><td>0</td><td>0 1</td><td>0 0</td><td>0 0</td></tr><tr><td>0.6</td><td>0</td><td>0</td><td>0.8</td></tr><tr><td>0.8 0</td><td>0 0</td><td>0 1</td><td>-0.6 0</td></tr></table></body></html>

Relying on the equations of Eq.(4) and Eq.(6), the equations are obtained:

$$
S ( \pmb { \rho } ) = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i } = 0
$$

$$
D ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 } = l n 3
$$

The comparison between the proposed entropy and von Neumann entropy is shown in following Table 2:

Table 2 The comparison of two models   

<html><body><table><tr><td>von Neumann entropy</td><td>The proposed entropy</td></tr><tr><td>0</td><td>ln3</td></tr></table></body></html>

From the above table, the von Neumann entropy of $\rho$ is O at this time,indicating that the uncertainty of $\rho$ calculated using the classical von Neumann entropy is O, which is problematic,such as this Although the quantum system in the example is in a pure state, it does not mean that it is completely certain.For example, the angle of the complex number $\alpha$ in it is uncertain.From this we can see that the classical Von Neumann entropy may be inaccuracies in measuring the uncertainty of some quantum systems.The value of the proposed entropy is $\ln 3$ at this time,which is a number greater than O,indicating that the uncertainty of the quantum system can be effectively measured using the proposed entropy.

Example 3 Suppose the quantum system at this time is a mixed state,as shown below:

$$
| \psi > = { \frac { 6 e ^ { i \alpha } } { 1 0 } } | 1 0 > + { \frac { 8 e ^ { i \beta } } { 1 0 } } | 0 1 >
$$

where,

$$
| 1 0 > = \left( \begin{array} { l } { 0 } \\ { 1 } \\ { 0 } \\ { 0 } \end{array} \right) , | 0 1 > = \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 1 } \\ { 0 } \end{array} \right)
$$

The density matrix obtained from the above is as follows:

$$
\rho = | \psi > < \psi | = \left( \begin{array} { c c c c } { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \frac { 3 6 } { 1 0 0 } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { \frac { 6 4 } { 1 0 0 } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 0 } } & { { 0 } } \end{array} \right)
$$

The eigenvalues and the corresponding eigenvectors of $\rho$ are in following Table 3:

Table 3 The eigenvalues and the corresponding eigenvectors of $\rho$   

<html><body><table><tr><td>Eigenvalues</td><td>0.64</td><td>0.36</td><td>0</td><td>0</td></tr><tr><td>Eigenvectors</td><td>0 0 1 0</td><td>0 1 0 0</td><td>0 0 0</td><td>0 0 0 1</td></tr></table></body></html>

Relying on Eq.(4) and Eq.(6), the equations are obtained:

$$
S ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i } = - 0 . 6 4 \ln 0 . 6 4 - 0 . 3 6 \ln 0 . 3 6 = 0 . 6 5 3 4
$$

$$
S ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i } = - 0 . 6 4 \ln 0 . 6 4 - 0 . 3 6 \ln 0 . 3 6 = 0 . 6 5 3 4
$$

The comparison between the proposed entropy and von Neumann entropy is shown in following Table 4:

Table 4 The comparison of two models   

<html><body><table><tr><td>von Neumann entropy</td><td>The proposed entropy</td></tr><tr><td>0.6534</td><td>0.6534</td></tr></table></body></html>

From the above table,we can see that the von Neumann entropy of the quantum system and the proposed entropy are both O.6534.In this example,we found that in some cases,the proposed entropy will degenerate into the classic von Neumann entropy,which is also the flexibility of the proposed entropy.

Example 4 Suppose the quantum system at this time is a pure state,as shown below:

$$
| \psi > = { \frac { e ^ { i \alpha } } { \sqrt 2 } } | 1 0 > + { \frac { e ^ { i \beta } } { \sqrt 2 } } | 0 1 >
$$

where,

$$
| 1 0 > = \left( \begin{array} { l } { 0 } \\ { 1 } \\ { 0 } \\ { 0 } \end{array} \right) , | 0 1 > = \left( \begin{array} { l } { 0 } \\ { 0 } \\ { 1 } \\ { 0 } \end{array} \right)
$$

The density matrix obtained from the above is as follows:

$$
\rho = | \psi > < \psi | = \left( \begin{array} { l l l } { 0 ~ 0 ~ 0 ~ 0 } \\ { 0 ~ \frac { 1 } { 2 } ~ \frac { 1 } { 2 } ~ 0 } \\ { 0 ~ \frac { 1 } { 2 } ~ \frac { 1 } { 2 } ~ 0 } \\ { 0 ~ 0 ~ 0 ~ 0 } \end{array} \right)
$$

The eigenvalues and the corresponding eigenvectors of $\rho$ are in following Table 5:

Table 5 The eigenvalues and the corresponding eigenvectors of $\rho$   

<html><body><table><tr><td>Eigenvalues</td><td>1</td><td>0</td><td></td><td>0</td><td>0</td></tr><tr><td rowspan="4">Eigenvectors</td><td>0</td><td></td><td>1</td><td>0</td><td>0</td></tr><tr><td>0.7071</td><td>0</td><td></td><td>0.7071</td><td>0</td></tr><tr><td>0.7071</td><td>0</td><td></td><td>-0.7071</td><td>0</td></tr><tr><td>0</td><td>0</td><td></td><td>0</td><td>1</td></tr></table></body></html>

Relying on Eq.(4) and Eq.(6), the equations are obtained:

$$
S ( \pmb { \rho } ) = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i } = 0
$$

$$
D ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 } = l n 3
$$

The comparison between the proposed entropy and von Neumann entropy is shown in following Table 6:

Table 6 The comparison of two models   

<html><body><table><tr><td>von Neumann entropy</td><td>The proposed entropy</td></tr><tr><td>0</td><td>ln3</td></tr></table></body></html>

From the above table,we see that when the quantum system $\rho$ still has large unknowns and uncertainties,the classical von Neumann entropy calculates the uncertainty of $\rho$ to be O, which once again illustrates the classical von Neumann Entropy is inaccurate in measuring the uncertainty of the quantum system,and the proposed entropy can measure the uncertainty of the quantum system $\rho$ here as $\ln 3$ ，which once again shows that the proposed entropy is better than the classical von Neumann entropy and has higher reliability when measuring the uncertainty of a quantum system.

Example 5 Given the density matrix of a quantum system is as follows:

$$
\rho = { \left( \begin{array} { l } { { \frac { 1 } { 4 } } \ 0 \ 0 \ 0 } \\ { 0 \ { \frac { 1 } { 4 } } \ 0 \ 0 } \\ { 0 \ 0 \ { \frac { 1 } { 4 } } \ 0 } \\ { 0 \ 0 \ 0 \ { \frac { 1 } { 4 } } } \end{array} \right) }
$$

The quantum system $\rho$ in this example is a special system, because the quantum system at this time is ina quantum fully mixed state.

The eigenvalues and the corresponding eigenvectors of $\rho$ are in following Table 7:

Table7 The eigenvalues and the corresponding eigenvectors of $\rho$   

<html><body><table><tr><td>Eigenvalues</td><td>0.25</td><td>0.25</td><td>0.25</td><td>0.25</td></tr><tr><td>Eigenvectors</td><td>1 0 0 0</td><td>0 1 0 0</td><td>0 0 1 0</td><td>0 0 0 1</td></tr></table></body></html>

Relying on the equations of Eq.(4) and Eq.(6), the equations are obtained:

$$
S ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \lambda _ { i } = - 4 * { \frac { 1 } { 4 } } \ln { \frac { 1 } { 4 } } = 2 \ln 2
$$

$$
D ( \rho ) = - \sum _ { i } \lambda _ { i } \ln \frac { \lambda _ { i } } { 2 ^ { | \lambda _ { i } | } - 1 } = - 4 * \frac { 1 } { 4 } \ln \frac { 1 } { 4 } = 2 \ln 2
$$

The comparison between the proposed entropy and von Neumann entropy is shown in following Table 8:

Table 8 The comparison of two models   

<html><body><table><tr><td>von Neumann entropy</td><td>The proposed entropy</td></tr><tr><td>21n2</td><td>2ln2</td></tr></table></body></html>

The quantum system $\rho$ in this example is a special system,because the quantum system at this time is in a quantum completely mixed state,and the classical von Neumann entropy will reach its maximum at this time.From the above table, we can see that the proposed entropy is equal to the classical von Neumann entropy at this time,indicating that the proposed entropy can effectively measure the most special cases of the quantum system.

Example $\boldsymbol { \mathscr { \sigma } }$ Given a quantum state as follows:

$$
\begin{array} { c } { { | \eta > = c o s ( \psi ) | a _ { 1 } > + s i n ( \psi ) | a _ { 2 } > } } \\ { { = c o s ( \psi - \varepsilon ) | b _ { 1 } > + s i n ( \psi - \varepsilon ) | b _ { 2 } > } } \end{array}
$$

where $\psi$ ranging between O and $2 \pi$

Based on the above form of quantum state,Garrett Portesi and Plastino (1996) proposed the generalized entropic uncertainty measure to measure the uncertainty of $\eta$ can be shown below:

$$
U _ { q } ( \hat { A } , \hat { B } ; \eta ) = \frac { 1 - [ \cos ^ { 2 q } \psi + \sin ^ { 2 q } \psi ] [ \cos ^ { 2 q } ( \psi - \varepsilon ) + \sin ^ { 2 q } ( \psi - \varepsilon ) ] } { q - 1 }
$$

The MU-like Maassen and Uffink(1988) expression of the generalized entropic uncertainty measure to measure the uncertainty can be shown below:

$$
\beta _ { q } ^ { U M } ( \xi ) = \frac { 1 - ( 1 / c ) ^ { 2 ( 1 - q ) } } { q - 1 }
$$

where

$$
c = \operatorname* { m a x } \{ | c o s \varepsilon | , | s i n \varepsilon | \}
$$

The comparison of three models is shown as Fig.2

![](images/8a2884e297edd5523a35da1f49ff212a5cb0735bc3669449eccc680faed0726d.jpg)  
Fig.2 The comparison of three models

In the above figure, the $\varepsilon$ is the variable p compiled from O to $2 \pi$ ,and the ordinate is the uncertainty measurement model of three quantum systems.For the convenience of calculation, we set $\psi = \pi / 2$ . From the results in the above figure,we can see that the proposed entropy is larger than the Portesi and Plastino's model,indicating that the proposed model has a higher efficiency in measuring the uncertainty of the quantum system,because it can also obtain higher Information.The curve obtained by the Maassen and Uffink's model is not smooth enough,and is too sharp and sharp at some points,which shows that its measurement is not universal in some cases.The proposed entropy is larger and smoother than Maassen and Uffink's model, indicating that the proposed model has higher efficiency and adaptability in measuring the uncertainty of quantum systems.

# 5 Conclusion

This paper proposes a new entropy model to measure the uncertainty of quantum systems,which is based on the classic von Neumann entropy and belief entropy. The proposed entropy can fully use the eigenvalues and eigenvectors of the density matrix of the quantum system,and give the uncertainty of the quantum system.When the base of all eigenvalues of the density matrix of a quantum system is 1,the proposed entropy will degenerate into the classical von Neumann entropy. Numerical examples are used to prove that the proposed entropy is more effcient and reliable in measuring quantum systems than the classical von Neumann entropy. The experimental results show that the proposed entropy can measure quantum systems more efficiently and reliably than the classical von Neumann entropy.

AcknowledgementsThe work is partially supported by National Natural Science Foundation of China (Grant No.61973332),JSPS Invitational Fellowships for Research in Japan (Short-term).

# Funding

The work is partially supported by National Natural Science Foundation of China (Grant No. 61973332).

# Conflict of interest

The authors declare that they have no conflict of interest.

# Ethical approval

This article does not contain any studies with human participants or animals performed byanyof the authors.

# References

Abdel-Khalek S,Abo-Dahab S, Ragab M,Ahmad H (2O2Oa) Engineering entanglement,geometric phase,and quantum fisher information of a three-level system with energy dissipation. Mathematical Methods in the Applied Sciences DOI 10.1002/mma.6781   
Abdel-Khalek S,Alhag A,Ragab M,Abo-Dahab S,Algarni A,Ahmad H (2020b) Atomic fisher information and entanglement forecasting for quantum system based on artificial neural network and time series model. International Journal of Quantum Chemistry p 26446,DOI10.1002/qua.26446   
Alkassar Y,Agarwal VK, Pandey R,Behera N (2O2O) Experimental study and shannon entropy analysis of pressure fluctuations and flow mode transition in fluidized dense phase pneumatic conveying of fly ash. Particuology 49:169-178, DOI 10.1016/j.partic.2019.03.003   
Alkhateeb S,Abdel-Khalek S (2O2O) Some features of the nonlocal correlation and geometric phase of the quantum system in two-mode nondegenerate entangled states. Journal of Mathematical Chemistry 58,DOI 10.1007/s10910-019-01057-6   
Anaya Contreras J, Moya-Cessa H, Ziga-Segundo A (2O19) The von neumann entropy for mixed states.Entropy 21:49,DOI 10.3390/e21010049   
Anjaria K (2O2O) Negation and entropy: Effectual knowledge management equipment for learning organizations. Expert Systems with Applications p 113497, DOI 10.1016/j.eswa.2020.113497   
Balazadeh L,Najarbashi G, Tavana A (2O2O) Quantum renormalization of the l(1) -norm and relative entropy of coherence in various spin chains. Quantum Information Processing 19:181, DOI 10.1007/s11128-020-02677-7   
Bannwarth C，Ehlert S，Grimme S (2O19） Gfn2-xtban accurate and broadlyparametrized self-consistent tight-binding quantum chemical method with multipole electrostaticsand density-dependent dispersion contributions.Journal of chemical theory and computation 15(3):1652-1671，DOI 10.1021/acs.jctc.8b01176   
Benabdallah F, Slaoui A, Daoud M (2O2O) Quantum discord based on linear entropy and thermal negativity of qutritqubit mixed spin chain under the influence of external magnetic feld. Quantum Information Processing 19, DOI 10.1007/s11128- 020-02754-x   
Berrada K,Al-Rajhi M(2O17) Information quantifiers, entropy squeezing and entanglement properties of superconducting qubit-deformed bosonic field system under dephasing effect. Quantum Information Processing 16:239, DOI 10.1007/s11128- 017-1686-8   
Berrada K,Eleuch H(2O21） Einstein-podolsky-rosen steering and nonlocality in quantum dot systems.Physica E: Low-dimensional Systems and Nanostructures 126:114,412,DOI 10.1016/j.physe.2020.114412   
Boes P, Eisert J,Gallego R,Mller M,Wilming H(2O19) Von neumann entropy from unitarity.Physical Review Letters 122,DOI 10.1103/PhysRevLett.122.210402   
Boutabba N,Eleuch H(2O2O) Quantum control of an optically dense atomic medium: Pulse shaping in a V-type three-level system. Results in Physics 19:103,421, DOI 10.1016/j.rinp.2020.103421   
Carrijo T, Avelar A (2O19) Weak quantum correlation quantifiers with generalized entropies. Quantum Information Processing 18:308,DOI 10.1007/s11128-019-2416-   
Chakraborty S, Shaikh SH, Chakrabarti A, Ghosh R (2O2O)A hybrid quantum feature selection algorithm using a quantum inspired graph theoretic approach. Applied Intelligence 50:1775-1793,DOI10.1007/s10489-019-01604-3   
Dai J,Deng Y (2O2O) A new method to predict the interference effect in quantum-like bayesian networks. Soft Computing pp 1-8, DOI 10.1007/s00500-020-04693-2   
Deng J,Deng Y (2O21） Information volume of fuzzy membership function. International Journal of Computers Communications & Control 16(1):41O6,DOI https://doi.org/10.15837/ijccc.2021.1.4106   
Deng S,Diao P,Li F,Yu Q，Yu S,Wu H(2018) Observation of dynamical super-efimovian expansion in a unitary fermi gas. Physical review letters 120(12):125,301,DOI 10.1103/PhysRevLett.120.125301   
Deng X, Jiang W (2O2O) On the negation of a dempster-shafer belief structure based on maximum uncertainty allocation. Information Sciences 516:346-352, DOI 10.1016/j.ins.2019.12.080   
DengY(2O20a） Informationvolumeofmassfunction. International Journal of ComputersCommunications & Control 15(6):3983， DOI https://doi.org/10.15837/ijccc.2020.6.3983   
Deng Y (202Ob) Uncertainty measure in evidence theory. SCIENCE CHINA Information Sciences 63(11):210,201   
Duboscq R, Pinaud O (2O2O) Constrained minimizers of the von neumann entropy and their characterization. Calculus of Variations and Partial Differential Equations 59:105,DOI10.1007/s00526-020-01753-1   
Farhadinia B, Xu Z (2O18) Novel hesitant fuzzy linguistic entropy and cross-entropy measures in multiple criteria decision making. Applied Intelligence 48(11):3915- 3927   
Feng X,Wei W, Zhang R, Wang J, Shi Y, Zheng Z(2019) Exploring the heterogeneity for node importance by von neumann entropy. Physica A: Statistical Mechanics and its Applications 517, DOI 10.1016/j.physa.2018.11.019   
Gal M (2019) Maps on quantum states in $c ^ { * }$ -algebras preserving von neumann entropy or schatten $p$ -norm of convex combinations. Canadian Mathematical Bulletin 62:1-6,DOI10.4153/CMB-2018-011-3   
Gao X,Deng Y(2O2O) Quantum Model of Mass Function $\cdot$ International Journal of Intelligent Systems 35(2):267-282   
Gao X, Deng Y (2O2O) The pseudo-pascal triangle of maximum deng entropy. International Journal of Computers Communications & Control 15(1):1O06,DOI 10.15837/3735/ijccc.2020.1.3735   
Gaonkar B,Beckett J,Attah M,Ahn C,Edwards M,Wilson B,Laiwalla A, Salehi B,Yoo B,Bui A，Macyszyn L (2021） Eigenrank by committee: Vonneumann entropy based data subset selection and failure prediction for deep learning based medical image segmentation. Medical Image Analysis 67:101,834, DOI 10.1016/j.media.2020.101834   
Guha A,Das P (2O18)An extensive study of boseeinstein condensation in liquid helium using tsalis statistics.Physica A: Statistical Mechanics and its Applications 497:272-284, DOI 10.1016/j.physa.2018.01.020   
Gupta D, Richhariya B (2O18) Entropy based fuzzy least squares twin support vector machine for class imbalance learning. Applied Intelligence 48(11):4212-4231, DOI 10.1007/s10489-018-1204-4   
Huang Z, Yang L, Jiang W (2O19) Uncertainty measurement with belief entropy on the interference effect in the quantum-like bayesian networks.Applied Mathematics and Computation 347:417-428,DOI10.1016/j.amc.2018.11.036   
Ion D,Ion M (2Oo1） New nonextensive quantum entropy and strong evidences for equilibrium of quantum hadronic states.Physics Letters B 519:63-70, DOI 10.1016/S0370-2693(01)01066-8   
Jaunzemis AD, Holzinger MJ, Chan MW, Shenoy PP (2019) Evidence gathering for hypothesis resolution using judicial evidential reasoning. Information Fusion 49:26-45,DOI 10.1016/j.inffus.2018.09.010   
Jauregui M, Zunino L,Lenzi E,Mendes R,Valentin Ribeiro H (2O18) Characterization of time series via rényi complexity-entropy curves. Physica A: Statistical Mechanics and its Applications 498:74-85,DOI 10.1016/j.physa.2018.01.026   
Johnson CR,Horn RA (1985) Matrix analysis. Cambridge University Press Cambridge   
Karci A (2016) Fractional order entropy: New perspectives. Optik 127(20):9172- 9177,DOI 10.1016/j.ijleo.2016.06.119   
Khan MN,Anwar S (2O19) Time-domain data fusion using weighted evidence and dempster-shafer combination rule:Application in object classification. Sensors 19(23):5187, DOI 10.3390/s19235187   
Koh JM, Cheong KH (2O19) New doubly-anomalous parrondos games suggest emergent sustainability and inequality. Nonlinear Dynamics 96(1):257-266, DOI 10.1007/s11071-019-04788-y   
Kontopoulou EM, Dexter GP, Szpankowski W, Grama A,Drineas P (202O) Randomized linear algebra approaches to estimate the von neumann entropy of density matrices. IEEE Transactions on Information Theory 66(8):5003-5021, DOI 10.1109/TIT.2020.2971991   
Kurzyk D, Pawela u, Puchaa Z (2O18) Conditional entropic uncertainty relations for tsallis entropies. Quantum Information Processng 17, DOI 10.1007/s11128-018- 1955-1   
Li D,Deng Y, Cheong KH(2O21） Multi-source basic probability assignment fusion based on information quality. International Journal of Intelligent Systems 36:10.1002/int.22,363   
de Lima Bernardo B (2O2O) Proposal for a direct measurement of the von neumann entropy and the relative entropy of coherence.Physica Scripta 95(4):O45,1O4,DOI 10.1088/1402-4896/ab6359   
Liu F, Gao X, Zhao J, Deng Y (2O19) Generalized belief entropy and its application in identifying conflict evidence.IEEE Access 7(1):126,625-126,633   
Longo R,Xu F (2O2O) Von neumann entropy in qft. Communications in Mathematical Physics pp 1-24,DOI10.1007/s00220-020-03702-7   
Luis A， Rodil A (2O13） Alternative measures of uncertainty in quantum metrology: Contradictions and limits. Physical Review A 87,DOI 10.1103/PhysRevA.87.034101   
Luis A,Bosyk G, Portesi M (2O16) Entropic measures of joint uncertainty: Effects of lack of majorization.Physica A:Statistical Mechanics and its Applications 444:905-913, DOI 10.1016/j.physa.2015.10.097   
Maassen H, Uffink J(1988) Generalized entropic uncertainty relations.Physical review letters 60:1103-1106,DOI 10.1103/PhysRevLet.60.1103   
Majernik V(2Oo8) The uncertainty relation expressed by means of a new entropic function. Open Physics 6:363-371,DOI 10.2478/s11534-008-0057-6   
Majernik V,Majernkov E, Shpyrko S (2Oo3） Uncertainty relations expressed by shannon-like entropies. Central European Journal of Physics 1:393-420,DOI 10.2478/BF02475852   
Mukhamedov F, Watanabe N(2O18) On s-mixing entropy of quantum channels. Quantum Information Processing 17,DOI10.1007/s11128-018-1916-8   
Mukhamedov F, Ohmura K,Watanabe N (202O) A formulation of renyi entropy on $c ^ { * }$ -algebras.Quantum Information Processing 18,DOI10.1007/s11128-019-2430- 3   
Ozkan K (2O18） Comparing shannon entropy with deng entropy and improved deng entropy for measuring biodiversity when a priori data is not clear. Forestist 68(2):136-140,DOI10.26650/forestist.2018.340634   
Pan L,Deng Y (2O2O) Probability transform based on the ordered weighted averaging and entropy difference. International Journal of Computers Communications & Control 15(4):3743, DOI 10.15837/ijccc.2020.4.3743   
Pan Y,Zhang L,Wu X, Skibniewski MJ (2O2O) Multi-classifier information fusion in risk analysis.Information Fusion 60:121-136,DOI10.1016/j.inffus.2020.02.003   
Panigrahi K，Howli P, Chattopadhyay KK (2O2O） 3d network of v2o5 for flexible symmetric supercapacitor. Electrochimica Acta 337:135,701，DOI 10.1016/j.electacta.2020.135701   
Pedrycz W, Bargiela A (2Oo3) Fuzzy fractal dimensions and fuzzy modeling. Information Sciences 153:199-216   
Perez-Bernal F, Torres-Herrera E, Schiulaz M, Santos L (2O2O) Self-averaging in many-body quantum systems out of equilibrium: Approach to the localized phase. Physical Review B 102:094,310,DOI10.1103/PhysRevB.102.094310   
Portesi M, Plastino A (1996) Generalized entropy as a measure of quantum uncertainty. Physica A: Statistical Mechanics and its Applications 225:412-430, DOI 10.1016/0378-4371(95)00475-0   
Prunkl C (2020) On the equivalence of von neumann and thermodynamic entropy. Philosophy of Science 87,DOI 10.1086/707565   
Rastegin AE (2Ol2) Number-phase uncertainty relations in terms of generalized entropies.Quantum Information and Computation 12:743-762   
Rastegin AE (2O15) Uncertainty relations for general canonically conjugate observables in terms of unified entropies.Foundations of Physics 45:23-942   
ur Rehman J, Shin H(2019) purity-based continuity bounds for von neumann entropy. Scientific rep0rts 9(1):1-9,DOI 10.1038/s41598-019-50309-7   
Romagnoli S (2O19) A vague multidimensional dependency structure: Conditional versus unconditional fuzzy copula models.Information Sciences 512:12O2-1213, DOI 10.1016/j.ins.2019.10.052   
Romagnoli S (2O2O) A vague multidimensional dependency structure: Conditional versus unconditional fuzzy copula models. Information Sciences 512:1202-1213, DOI 10.1016/j.ins.2019.10.052   
Sakamoto S,Tanimura Y (2O2O) Numerically exact simulations of entropy production in the fully quantum regime: Boltzmann entropy vs von neumann entropy. The Journal of Chemical Physics 153:234,107,DOI 10.1063/5.0033664   
Sarantoglou G, Skontranis M, Mesaritakis C (2O2O) All optical integrate and fire neuromorphic node based on single section quantum dot laser. IEEE Journal of Selected Topics in Quantum Electronics 26:1-10, DOI 10.1109/JSTQE.2019.2945549   
Turhan H, Demirekler M (2O17)A novel combination methodology for dempstershafer theory. In: 2O17 25th Signal Processing and Communications Applications Conference (SIU), pp 1-4, DOI 10.1109/SIU.2017.7960625   
Ur Rehman J, Shin H (2O19) Purity-based continuity bounds for von neumann entropy. Scientific Rep0rts 9:1-9,DOI 10.1038/s41598-019-50309-7   
Valero-Toranzo I, Zozor S,Brossier J(2O18) Generalization of the de bruijn identity to general $\phi$ -entropies and $\phi$ -fisher informations. IEEE Transactions on Information The0ry 64(10):6743-6758,DOI 10.1109/TIT.2017.2771209   
Von Neumann J(1955) Mathematical Foundations of Quantum Mechanics   
Wang D, Gao J, Wei D (2019) A new belief entropy based on deng entropy. Entropy 21(10):987,DOI 10.3390/e21100987   
Wang L, Ye SQ, Cheong KH, Bao W, Xie Ng (2O18) The role of emotions in spatial prisoners dilemma game with voluntary participation. Physica A: Statistical Mechanics and its Applications 490:1396-1407,DOI10.1016/j.physa.2017.08.033   
Yurischev M (2O18) Bimodal behavior of post-measured entropy and one-way quantum deficit for two-qubit X states. Quantum Information Processing 17,DOI 10.1007/s11128-017-1776-7   
Yurischev MA (2O17) Extremal properties of conditional entropy and quantum discord for Xxz, symmetric quantum states. Quantum Information Processing 16, DOI 10.1007/s11128-017-1701-0   
Zhu JM (2O2O) Von neumann entropy distribution with influence factors in matrix product states.International Journal of Theoretical Physics 59:1-15,DOI 10.1007/s10773-020-04517-x   
Zhu R, Chen J,Kang B (2O2O) Power law and dimension of the maximum value for belief distribution with the maximum deng entropy. IEEE Access 8:47,713- 47,719,DOI 10.1109/ACCESS.2020.2979060   
Zozor S,Portesi M, Vignat C (2OO8） Some extensions of the uncertainty principle. Physica A: Statistical Mechanics and its Applications 387:4800-4808,DOI 10.1016/j.physa.2008.04.010   
Zozor S, Bosyk G, Portesi M(2O13) On a generalized entropic uncertainty relation in the case of the qubit. Journal of Physics A Mathematical and Theoretical 46, DOI 10.1088/1751-8113/46/46/465301   
Zozor S,Bosyk G, Portesi M (2O14) General entropy-like uncertainty relations in finite dimensions.Journal of Physics A: Mathematical and Theoretical 47,DOI 10.1088/1751-8113/47/49/495302