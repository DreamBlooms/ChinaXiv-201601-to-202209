# Deng entropy measure of quantum entanglement

Yong Denga,b,c,\*

$a$ Institute of Fundamental and Frontier Science,University of Electronic Science and Technology of China，Chengdu,610054，China （20 $b$ School of Eduction,Shannri Normal University， Xian, 7062,China $c$ Schoolof Knowledge Science,Japan Advanced Institute of Science and Technology，Nomi, Ishikawa 923-1211,Japan

# Abstract

How to measure quantum entanglement is still an open issue. Some entropy functions are applied to address this issue,such as von neumann entropy. In this paper,a new Deng entropy based method is presented to measure quantum entanglement. The main idea is calculation the entropy difference between the state of entanglement and the state of disentanglement as the quantum entanglement degree. The more the entropy difference, the less the quantum entanglement degree. Numerical examples on two typical quantum entanglement, namely GHZ state and W state,are illustrated the effciency of the proposed Deng entropy measure.

Keywords: Quantum entanglement, Entanglement degree, Deng entropy, Maximum Deng entropy, Entropy difference

# 1．Introduction

Quantum entanglement plays an important role in quantum information processing.However,an open issue is how to measure the quantum entanglement degree. A typical method is based on von neumann entropy [1,2,3]. How to measure the entanglement of a quantum system is an important issue [4]. Regarding this issue,many experts have made a lot of efforts and put forward many theories and models [5,6]. Krisnanda et al. [7] observed the quantum entanglement based on gravity theory. Ho et al. [8] proposed the matrix product state approach under quantum system.Bienfait et al.[9] proposed remote quantum qubit entanglement. Iadecola and Schecter [1O] measured the quantum many-body scar states with the aid of emergent kinetic constraints and finiteentanglement revivals. In this paper,we explore a new methodology to measure the quantum entanglement degree based on the Deng entropy. The main idea is using Deng entropy difference between the entanglement and disentanglement.

Numerical examples on two typical quantum entanglement,namely GHZ state and W state,are illustrated the efficiency of the proposed measure.

The remain of this paper is structured as follows. Section 2 introduces the preliminary, including Deng entropy and maximum Deng entropy. Section 3 presents the proposed measure of quantum entanglement degree and the application in the two typical cases. Section 4 concludes the paper.

# 2.Preliminaries

In this section， frame of discernment and mass function [11],Deng entropy [12,13],maximum belief entropy [14] are briefly introduced.

# 2.1.FrameofDiscernment

Given a frame of discernment $\Omega = \{ x _ { 1 } , x _ { 2 } , \ldots , x _ { n } \}$ , the power set of frame of discernment is defined as follows:

Definition 2.1. (Power Set of Frame of Discernment) [11]

$$
2 ^ { \Omega } = \{ \emptyset , \{ x _ { 1 } \} , \{ x _ { 2 } \} , \dots , \{ x _ { n } \} , \{ x _ { 1 } , x _ { 2 } \} , \dots , \{ x _ { 1 } , x _ { 2 } , \dots , x _ { i } \} , \dots , \Omega \}
$$

# 2.2.Mass Function

Given a frame of discernment $\Omega = \{ x _ { 1 } , x _ { 2 } , \ldots , x _ { n } \}$ , the mass function, $m$ . on $2 ^ { \Omega }$ is defined as follows:

Definition 2.2. (Mass Function) [11]

$$
m : 2 ^ { \Omega }  [ 0 , 1 ]
$$

Where, $m ( \emptyset ) = 0$ and $\Sigma _ { B \in 2 ^ { \Omega } } m ( B ) = 1$ with $a$ focal element, $B$ ，of $2 ^ { \Omega }$

# 2.3. Deng Entropy

Given a mass function $m$ on a given frame of discernment $\Omega = \{ x _ { 1 } , x _ { 2 } , \ldots , x _ { n } \}$ The definition of belief entropy under $m$ is as follows:

Definition 2.3. (Deng entropy） [13]

$$
E _ { d } = - \sum _ { B \in 2 ^ { \Omega } } m ( B ) \ln \frac { m ( B ) } { 2 ^ { | B | } - 1 }
$$

When the mass function is degenerated as a classical probability distribution, belief entropy will be degenerated into Shannon entropy.

# 2.4. The Maximum Deng Entropy

Given a mass function $m$ on a given frame of discernment $\Omega = \{ x _ { 1 } , x _ { 2 } , \ldots , x _ { n } \}$ The definition of the maximum belief entropy under $m$ is as follows:

Definition 2.4. (The Maximum Deng Entropy) [14]

$$
E _ { d } = - \sum _ { B \in 2 ^ { \Omega } } m ( B ) \ln \frac { m ( B ) } { 2 ^ { | B | } - 1 }
$$

Where, m(B)= ∑B∈22Bl-1·

# 3.The proposed method and application

Given the entanglement state and disentanglement state,the definition of the entanglement degree is as follows:

Definition 3.1. (The quantum entanglement degree)

$$
Q E D = E i - E e
$$

Where, Ei and Ee are the maximum Deng entropy of the initial state (entanglement state) and end state (disentanglement state).

It should be pointed our that the less of the QED value, the more the entanglement degree.

Example 3.1. Given GHZ status,meaning that entanglement among three particles when one of these particles collapses into a state, the other two particles collapse into a new entanglement respectively, shown in Fig 1.

![](images/f66064807551b8200d8c80dc4032cbd90afba5211acd46ef12a62809c8d57c35.jpg)  
Figure 1: The entanglement of GHZ state

For a discernment framework $\Theta = \{ A , B , C \}$ . The maximum Deng entropy distribution is

$$
m ( A ) = m ( B ) = m ( C ) = { \frac { 1 } { 1 9 } }
$$

$$
m ( A B ) = m ( A C ) = m ( B C ) = { \frac { 3 } { 1 9 } }
$$

$$
m ( A B C ) = \frac { 7 } { 1 9 }
$$

.The maximum Deng entropy of the initial state is as follow:

$$
E ( \{ A , B , C \} ) = - 3 \times { \frac { 1 } { 1 9 } } \ln { \frac { 1 } { 1 9 } } - 3 \times { \frac { 3 } { 1 9 } } \ln { \frac { 3 } { 1 9 } } - { \frac { 7 } { 1 9 } } \ln { \frac { 7 } { 1 9 } }
$$

The maximum Deng entropy of end state is as follow:

$$
E ( \{ A , B \} \{ C \} ) = - 3 \times { \frac { 1 } { 4 } } \ln { \frac { 1 } { 4 } } - 3 \times { \frac { 3 } { 4 } } \ln { \frac { 3 } { 4 } } = \ln 4
$$

Hence we can obtain that $\begin{array} { r } { Q E D ^ { G H Z } = l n \frac { 1 9 } { 4 } } \end{array}$

Example 3.2.W state stands for entanglement among three particles. When one of these particles collapses into a state,the other two particles still entangled. The entanglement figure in Fig.2.

®

The initial state $m ( \{ A , B , C \} ) = 1$ . Then the maximum Deng entropy is shown as follow:

$$
E ( \Theta ) = - 3 \times { \frac { 1 } { 1 9 } } \ln { \frac { 1 } { 1 9 } } - 3 \times { \frac { 3 } { 1 9 } } \ln { \frac { 3 } { 1 9 } } - { \frac { 7 } { 1 9 } } \ln { \frac { 7 } { 1 9 } } = \ln 1 9
$$

The maximum Deng entropy of end state is as follow:

$$
E ( \{ A \} , \{ B \} , \{ C \} ) = - 3 \times { \frac { 1 } { 3 } } \ln { \frac { 1 } { 3 } } = \ln 3
$$

In this case,since the mass function is degenerated as probability distribution, Deng entropy is degenerated as Shannon entropy. Hence we can obtain that $\begin{array} { r } { Q E D ^ { W } = l n \frac { 1 9 } { 3 } } \end{array}$ .

Since $\begin{array} { r } { l n { \frac { 1 9 } { 3 } } < l n { \frac { 1 9 } { 4 } } } \end{array}$ , the entanglement degree of GHZ state is higher than W state.

# 4.Conclusion

The measurement method of entanglement degree of a quantum system is still a open issue. This paper proposes a new method based on Deng entropy. We show that the Deng entropy difference between entanglement and disentanglement can be used to measure the quantum entanglement degree.It should be pointed out that with the concept of information volume [15,16], the information volume difference between entanglement and disentanglement is also a possible parameter to measure the quantum entanglement degree.

# Acknowledgment

The authors' Ph.D students Yige Xue and Qianli Zhou, master degree student, Jixiang Deng, have discussed with this idea and done some editorial works. The work is partially supported by National Natural Science Foundation of China (Grant No. 61973332), JSPS Invitational Fellowships for Research in Japan (Short-term).

# Reference

[1] Roberto Longo and Feng Xu.Von neumann entropy in qft. Communications in Mathematical Physics, pages 1-24， 2020. doi: 10.1007/ s00220-020-03702-7.   
[2] Adam Kaufman,M. Tai,Alexander Lukin,Matthew Rispoli, Robert Schittko,Philipp Preiss,and Markus Greiner.Quantum thermalization through entanglement in an isolated many-body system.Science, 353,O3 2016.doi: 10.1126/science.aaf6725.   
[3] Junaid ur Rehman and Hyundong Shin. purity-based continuity bounds for von neumann entropy. Scientific reports, 9(1):1-9, 2019. doi: 10.1038/ s41598-019-50309-7.   
[4] Nicolas Laflorencie. Quantum entanglement in condensed matter systems. Physics Rep0rts, 646:1-59,2016. doi: 10.1016/j.physrep.2016.06.008.   
[5] Jianwei Wang,Stefano Paesani, Yunhong Ding,Raffaele Santagati, Paul Skrzypczyk,Alexia Salavrakos, Jordi Tura Brugus,Remigiusz Augusiak, Laura Maninska， Davide Bacco,Damien Bonneau， Joshua Silverstone, Qihuang Gong，Antonio Acn， Karsten Rottwitt，Leif Oxenlwe， Jeremy O'Brien，Anthony Laing,and Mark Thompson. Multidimensional quantum entanglement with large-scale integrated optics. Science (New York, N.Y.),360:285-291, 03 2018. doi: 10.1126/science.aar7053.   
[6] Ralf Riedinger,Andreas Wallucks, Igor Marinkovic, Clemens Lschnauer, Markus Aspelmeyer, Sungkun Hong,and Simon Grblacher. Remote quantum entanglement between two micromechanical oscillators. Nature, 556, 2018. doi: 10.1038/s41586-018-0036-z.   
[7] Tanjung Krisnanda, Guo Tham,M.Paternostro,and Tomasz Paterek. Observable quantum entanglement due to gravity. npj Quantum Information, 6,12 2020. doi: 10.1038/s41534-020-0243-y.   
[8] Wen Wei Ho,Soonwon Choi,Hannes Pichler,and Mikhail Lukin.Periodic orbits, entanglement,and quantum many-body scars in constrained models: Matrix product state approach. Physical Review Letters,122, O1 2019. doi: 10.1103/PhysRevLett.122.040603.   
[9] A.Bienfait,K. Satzinger,Y. Zhong,H.-S Chang,M.-H Chou,C. Conner, Dumur,J.Grebel,G.Peairs,R.Povey,and A.Cleland.Phonon-mediated quantum state transfer and remote qubit entanglement.Science,364:368- 371,04 2019. doi: 10.1126/science.aaw8415.   
[10] Thomas Iadecola and Michael Schecter. Quantum many-body scar states with emergent kinetic constraints and finite-entanglement revivals.Physical Review B,101,01 2020. doi: 10.1103/PhysRevB.101.024306.   
[11] A.P.Dempster. Upper and lower probabilities induced by a multivalued mapping. The Annals of Mathematical Statistics,38(2):325-339,1967. ISSN 00034851. URL http://www .jstor.org/stable/2239146.   
[12] Yong Deng. Uncertainty measure in evidence theory. SCIENCE CHINA Information Sciences,63(11):210201, 2020.   
[13] Yong Deng.Deng entropy. Chaos, Solitons & Fractals, 91:549-553,2016.   
[14] Bingyi Kang and Yong Deng. The maximum deng entropy. IEEE Access, 7:120758-120765, 2019. doi: 10.1109/ACCESS.2019.2937679.   
[15] Jixiang Deng and Yong Deng. Information volume of fuzzy membership function.International Journal of Computers Communications & Control, 16(1):4106, 2021. doi: https://doi.org/10.15837/ijccc.2021.1.4106.   
[16] Yong Deng. Information volume of mass function. International Journal of Computers Communications & Control, 15(6):3983, 2020. doi: https: //doi.org/10.15837/ijccc.2020.6.3983.