# Y-system for $\gamma$ -deformed ABJM Theory

Hui-Huang Chen ${ } _ { a , b }$ \*，Peng Liu $\mathbf { \Delta } _ { a , b } ^ { a , b }$ t, Jun-Bao Wuc,d,a,b,et

（20 $a$ Institute of High Energy Physics, and Theoretical Physics Center for Science Facilities， Chinese Academy of Sciences， 19B Yuquan Road, Beijing 100049,P.R. China （204 $b$ University of Chinese Academy of Sciences, 19A Yuquan Road, Beijing 100049, P. R. China $c$ School of Science, University of Tianjin, 92 Weijin Road, Tianjin 30o72, P. R. China   
$d$ School of Physics and Nuclear Energy Engineering, Beihang University， 37 Xueyuan Road, Beijing 100191, P. R. China   
Center for High Energy Physics, Peking University, 5 Yiheyuan Road, Beijing 100871, P.R. China

# Abstract

We investigate the integrable aspects of the planar $\gamma$ -deformed ABJM theory and propose the twisted asymptotic Bethe ansatz equations. A more general method through a twisted generating functional is discussed,based on which,the asymptotic large $L$ solution of Y-system is modified in order to match the asymptotic Bethe ansatz equations. Several applications of our method in the $s l ( 2 )$ -like sector and some important examples in $\beta$ -deformed ABJM are presented as well.

# Contents

1Introduction 2

# 2The $\gamma$ -deformation of ABJM theory 3

2.1 The $s u ( 4 )$ sector 4   
2.2 The full $O S p ( 6 | 4 )$ sector 5   
2.2.1The distinguished basis 5   
2.2.2The $\eta = - 1$ grading 6   
2.3 Duality properties 7

# ； Asymptotic Bethe ansatz 8

# 4The $\gamma$ -deformed $\mathbf { A d S _ { 4 } } / \mathbf { C F T _ { 3 } }$ Y-system 9

4.1 The twisted generating functional 10   
4.2 Consistency checks 11   
4.3 The asymptotic solution 12

# 5Applications to $s l ( 2 )$ -like sector 13

5.1Two-loop wrapping corrections to twist-1 operators . 14   
5.2Four-loop wrapping corrections to twist-2 operators . 15

# 3 $\beta$ -deformation 15

6.1One-particle state 16   
6.2A simple case of two particle state 17

# 7Conclusions 18

A Algebraic Bethe Ansatz 19   
B The $s u ( 2 )$ grading 20

# 1Introduction

The celebrated AdS/CFT correspondence continues to be a source of exciting new results in both gauge and string theory, with the best studied example being the AdS $^ { 5 }$ /CFT $^ 4$ duality between fourdimensional $\mathcal { N } ~ = ~ 4$ superconformal Yang-Mills theory(SYM) and Type IIB superstring theory on $\mathrm { A d S _ { 5 } \times S ^ { 5 } }$ [1]. There are also other AdS/CFT examples [2, 3] with field theories being in lower dimensions and integrability properties discovered on both sides. One of these is the AdS $^ 4$ /CFT $^ 3$ （20 duality proposed in [4],which relates three-dimensional $\mathcal { N } = 6$ super Chern-Simons theory and type IIA string theory on $\mathrm { A d S } _ { 4 } \times \mathbb { C P } ^ { 3 }$ . The integrable structure on both sides in this gauge/string duality was first studied in [5]-[9]. Similarly to $\mathcal { N } = 4$ SYM [10, 11],a complete description of planar anomalous dimensions of infinitely long operators has been investigated by means of the Asymptotic Bethe Ansatz(ABA） equations [12]. To solve the spectral problem for single-trace operators with finite length, finite size effects must be computed. The complete solution to AdS $^ { 5 }$ /CFT4 spectral problem is encoded in the TBA/Y-system [13]-[15],which has an equivalent but simpler form— the Quantum Spectral Curve(QSC) [16]. In AdS $^ 4$ /CFT $_ 3$ , the TBA/Y-system was constructed in [17,18] and recently reduced to a QSC in [19]. One of the very impressive results is the computation of the triple wrapping corrections in ABJM theory [20] using the QSC method.Nevertheless,the good old Y-system is still efficient for computing leading wrapping corrections.

Integrability gives us some hopes to solve exactly highly non-trivial quantum field theories. However, such theories are quite rare and integrable structure usually only appears in the large N limit. Notice that the integrable structures in AdS/CFT correspondence first appear in theories with a large amount of supersymmetries. It would be very interesting to see how far one can go by reducing the supersymmetries of the original theory while keeping integrable structure at the same time. For AdS $^ { 5 }$ /CFT $_ 4$ , people have explored a lot through at least three approaches including the addition of favors [21]-[23],marginal deformations [24]-[27]and orbifolding [28]-[33].For more information on these topics see reviews [34, 35] and references therein. Some wrapping effects in $\beta$ and $\gamma$ -deformed SYM theories were computed using Lüscher method and/or Y-system in [36]-[39]. In three-dimensional case, similar aspects have been less studied. In [40],integrability of planar $\beta$ -deformed ABJM theories was established at two-loop order in the scalar sector.1 Recently, integrability of orbifold ABJM theories was studied in details in [42].

The $\gamma$ -deformation of ${ \mathcal N } = 4$ SYM theory are very special among classically marginal deformations in the sense that it preserves the integrable structure and can be implemented elegantly on both sides of gauge/string duality. On the gauge theory side, the deformation can be expressed through a noncommutative star product for each interaction term in the Lagrangian. On its dual string theory side, it can be constructed by T-duality-shift-T-duality(TsT) transformations [43,44].Marginal deformations of Bagger-Lambert-Gustavsson theory [49]-[53] were studied in [54]. Similar deformations were also studied on the gravity side in [55]. These deformations were reviewed in [57]. The $\gamma$ -deformed ABJM theories and their gravity duals were studied in [41]. Some classical string solutions in these deformed backgrounds of type IIA string theory have been studied in [45]-[48].

The integrability of $\gamma$ -deformed ABJM theory in [41] in the scalar sector at two-loop level can be proved in a similar way as it was done for $\beta$ -deformed theory [40]. In this paper we make the very natural assumption that the planar $\gamma$ -deformed ABJM theory is integrable for all the sectors and to all loop orders,and compute the twist matrix as in [26]. Then the proposal of asymptotic Bethe equations is straightforward to get.We investigate the duality properties which have been derived in [42] carefully. We find they are allsatisfied nicely as they should. Thanks to these duality properties, a more general twisted generating functional method is proposed. To match the twisted ABA equations, a modified asymptotic large $L$ solution of Y-system is presented. Various applications have been made in the $s l ( 2 )$ -like sector. Since the AdS $_ 4$ /CFT $^ 3$ Y-system have been proposed in [13] and refined in [17] (see also [18]),the investigation of its application for the non-symmetric solutions $Y _ { \bullet } \neq Y _ { \bullet }$ have not been made in the weak coupling region. For the $\beta$ -deformed ABJM theory, first few attempts have been made for some simple states.

The plan of the paper is the follwing. In section 2，we briefly discuss the basic properties of $\gamma$ -deformed ABJM theory, and the twist matrix is derived. In section 3,we present the asymptotic Bethe ansatz for $\gamma$ -deformed ABJM theory. In section 4, the twisted Y-system is proposed. Finally, in section 5 and 6 some applications are investigated.

# 2 The $\gamma$ -deformation of ABJM theory

The three-parameter deformation of ABJM theory can be performed by replacing all the ordinary products $f g$ of two fields $f$ and $g$ in the Lagrangian by the following non-commuting star product,

$$
f * g = e ^ { i \pi Q _ { f } \times Q _ { g } } f g = e ^ { i \pi Q _ { f } ^ { i } C _ { i j } Q _ { g } ^ { j } } f g .
$$

Table 1: Charges of felds under three $U ( 1 )$ generators of $S U ( 4 ) _ { R }$   

<html><body><table><tr><td>Fields</td><td>Y1</td><td>Y2</td><td>Y3</td><td>Y4</td><td>yt1</td><td>2t2</td><td>t3</td><td>t4</td></tr><tr><td>Qf</td><td>1-2</td><td>一</td><td>0</td><td>0</td><td>1-2</td><td></td><td>0</td><td>0</td></tr><tr><td>Q²</td><td>0</td><td>0</td><td>1-2</td><td></td><td>0</td><td>0</td><td>1-2</td><td></td></tr><tr><td>Q</td><td>1-2</td><td>1-2</td><td>-</td><td></td><td>1-2</td><td>1-2</td><td></td><td></td></tr></table></body></html>

We parameterize the anti-symmetric phase matrix $\mathbf { C }$ by three deformation parameters $\gamma _ { 1 } , \gamma _ { 2 } , \gamma _ { 3 }$ as

$$
{ \bf C } = \left( \begin{array} { c c c } { { 0 } } & { { - \gamma _ { 3 } } } & { { + \gamma _ { 2 } } } \\ { { + \gamma _ { 3 } } } & { { 0 } } & { { - \gamma _ { 1 } } } \\ { { - \gamma _ { 2 } } } & { { + \gamma _ { 1 } } } & { { 0 } } \end{array} \right) .
$$

The $U ( 1 ) ^ { 3 }$ charges of the fundamental fields are given in the Table 1. The gravity dual of $\gamma$ -deformed ABJM theory is the type IIA string theory on $\gamma$ -deformed background $\mathrm { A d S } _ { 4 } \times \mathrm { C P } _ { \gamma } ^ { 3 }$ , which is equivalent to the same theory on undeformed background but with twisted boundary conditions2

$$
\phi _ { i } ( 2 \pi ) - \phi _ { i } ( 0 ) = 2 \pi ( m _ { i } - \epsilon _ { i j k } \gamma _ { j } J _ { k } ) , \quad m _ { 1 } , m _ { 2 } , m _ { 3 } + \frac { m _ { 1 } + m _ { 2 } } { 2 } \in \mathbb { Z } .
$$

Here the $\phi _ { i }$ 's are three angles on $\mathrm { C P ^ { 3 } }$ and $J _ { i }$ are the corresponding angular momentum. We parameterize the $\mathrm { C P ^ { 3 } }$ by embedding it inside $\mathbb { C } ^ { 4 }$ as

$$
\begin{array} { l } { { \displaystyle Y ^ { 1 } = \cos \xi \cos \frac { \theta _ { 1 } } { 2 } e ^ { i ( + \phi _ { 1 } + \phi _ { 3 } ) / 2 } , } } \\ { { \displaystyle Y ^ { 2 } = \cos \xi \sin \frac { \theta _ { 1 } } { 2 } e ^ { i ( - \phi _ { 1 } + \phi _ { 3 } ) / 2 } , } } \\ { { \displaystyle Y ^ { 3 } = \sin \xi \cos \frac { \theta _ { 2 } } { 2 } e ^ { i ( + \phi _ { 2 } - \phi _ { 3 } ) / 2 } , } } \\ { { \displaystyle Y ^ { 4 } = \sin \xi \sin \frac { \theta _ { 2 } } { 2 } e ^ { i ( - \phi _ { 2 } - \phi _ { 3 } ) / 2 } . } } \end{array}
$$

This explains the charges in Table 1.

We must point out that the choice of the three linearly independent $U ( 1 )$ Cartan generators of $S U ( 4 ) _ { R }$ has some degrees of freedom. Our choice of these three charges are the same as the one in [41],since the three TsT transformations used there is exactly based on $\phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 }$ directions.Our choice is not the same as the one in [56]. However the three generators in the later paper are simply linear combinations of the generators we used here,and the two sets of deformation parameters are also related by linear transformation. So these two choices are in fact equivalent. The three $U ( 1 )$ charges we choose are related to the Dynkin labels $[ p _ { 1 } , q , p _ { 2 } ]$ of $S U ( 4 )$ by $\begin{array} { r } { J _ { 1 } \equiv J _ { \phi _ { 1 } } = Q _ { f } ^ { 1 } = \frac { p _ { 1 } } { 2 } , J _ { 2 } \equiv } \end{array}$ $\begin{array} { r } { J _ { \phi _ { 2 } } = Q _ { f } ^ { 2 } = \frac { p _ { 2 } } { 2 } , J _ { 3 } \equiv J _ { \phi _ { 3 } } = Q _ { f } ^ { 3 } = q + \frac { p _ { 1 } + p _ { 2 } } { 2 } } \end{array}$ .

# 2.1 The $s u ( 4 )$ sector

The Bethe ansatz equations of $\gamma$ -deformed theories are the same as the ones for the undeformed theory except for adding some phases. In order to obtain the appropriate twist phases in the $s u ( 4 )$ sector, using the same notation as in [26],we introduce the $\mathbf { B }$ matrix . When permuting two scalars $Y ^ { i }$ and $Y ^ { j }$ , we pick up a phase

$$
Y ^ { i } * Y ^ { j } = e ^ { 2 \pi i B _ { i j } } Y ^ { j } * Y ^ { i } .
$$

In the basis $( Y ^ { 1 } , Y ^ { 2 } , Y ^ { 3 } , Y ^ { 4 } )$ ，using the charges of the fundamental fields listed in Table $^ 1$ ，the $\mathbf { B }$ （20 matrix turns out to be

$$
\mathbf { B } = \frac { 1 } { 4 } \left( \begin{array} { c c c c } { 0 } & { 2 \gamma _ { 2 } } & { \gamma _ { 1 } - \gamma _ { 2 } - \gamma _ { 3 } } & { - \gamma _ { 1 } - \gamma _ { 2 } + \gamma _ { 3 } } \\ { - 2 \gamma _ { 2 } } & { 0 } & { \gamma _ { 1 } + \gamma _ { 2 } + \gamma _ { 3 } } & { - \gamma _ { 1 } + \gamma _ { 2 } - \gamma _ { 3 } } \\ { - \gamma _ { 1 } + \gamma _ { 2 } + \gamma _ { 3 } } & { - \gamma _ { 1 } - \gamma _ { 2 } - \gamma _ { 3 } } & { 0 } & { 2 \gamma _ { 1 } } \\ { \gamma _ { 1 } + \gamma _ { 2 } - \gamma _ { 3 } } & { \gamma _ { 1 } - \gamma _ { 2 } + \gamma _ { 3 } } & { - 2 \gamma _ { 1 } } & { 0 } \end{array} \right) .
$$

（204号 $s u ( 4 )$ is a rank 3 algebra, and there are three types of excitations in this sector. We denote the three creation operators by $B _ { 3 } , B _ { 4 } , B _ { \bar { 4 } }$ . Their actions are

$$
\mathcal { B } _ { 3 } : Y ^ { 2 } \to Y ^ { 3 } , \mathcal { B } _ { 4 } : Y ^ { 1 } \to Y ^ { 2 } , \mathcal { B } _ { \bar { 4 } } : Y ^ { 3 } \to Y ^ { 4 } .
$$

Since our vacuum is chosen as $\operatorname { T r } ( Y ^ { 1 } Y _ { 4 } ^ { \dag } ) ^ { L }$ ， we now should consider the twist matrix in the basis + YY3,Y†Y²,YY4). The twist matrix turns out to be

$$
\mathbf { A } = \left( \begin{array} { c c c c } { 0 } & { \gamma _ { 1 } - \gamma _ { 2 } } & { \gamma _ { 2 } - \frac { 1 } { 2 } \gamma _ { 3 } } & { - \gamma _ { 1 } + \frac { 1 } { 2 } \gamma _ { 3 } } \\ { - \gamma _ { 1 } + \gamma _ { 2 } } & { 0 } & { - \gamma _ { 2 } - \frac { 1 } { 2 } \gamma _ { 3 } } & { \gamma _ { 1 } + \frac { 1 } { 2 } \gamma _ { 3 } } \\ { - \gamma _ { 2 } + \frac { 1 } { 2 } \gamma _ { 3 } } \\ { \gamma _ { 1 } - \frac { 1 } { 2 } \gamma _ { 3 } } \end{array} \right) .
$$

The twist phases appearing in Bethe equations are simply given by $2 \pi ( \mathbf { A K } ) _ { i }$ ,where ${ \bf K } = ( L | K _ { 3 } , K _ { 4 } , K _ { \bar { 4 } } )$ This result is consistent with Appendix A, where direct computations through a deformed R-matrix were performed. For $\gamma _ { 1 } = \gamma _ { 2 } = 0 , \gamma _ { 3 } = - \beta$ , this comes back to the result in [40] for $\beta$ -deformed case. 3

# 2.2 The full $O S p ( 6 | 4 )$ sector

# 2.2.1 The distinguished basis

From the above example, we know the crucial point is to find out the action of the creation operators. The full $O S p ( 6 | 4 )$ sector contains five types of excitations $u _ { 1 } , \ldots , u _ { \bar { 4 } }$ , and there are five corresponding creation operators $B _ { 1 } , \ldots , B _ { \bar { 4 } }$ . In the distinguished grading,the actions of these creation operators on the fundamental fields can be found as

$$
{ \mathcal { B } } _ { 1 } : \psi _ { I + }  \psi _ { I - } , { \mathcal { B } } _ { 2 } : Y _ { 1 } ^ { \dagger }  \psi ^ { \dagger 2 + } , { \mathcal { B } } _ { 3 } : Y ^ { 2 }  Y ^ { 3 } , { \mathcal { B } } _ { 4 } : Y ^ { 1 }  Y ^ { 2 } , { \mathcal { B } } _ { \bar { 4 } } : Y ^ { 3 }  Y ^ { 4 } .
$$

Then we find the twist matrix in the basis $( Y ^ { 1 } Y _ { 4 } ^ { \dag } | 1 , Y ^ { 1 } \psi ^ { \dag 2 + } , Y _ { 2 } ^ { \dag } Y ^ { 3 } , Y _ { 1 } ^ { \dag } Y ^ { 2 } , Y _ { 3 } ^ { \dag } Y ^ { 4 } )$ as

$$
\mathbf { A } ^ { \prime } = \frac { 1 } { 2 } \left( \begin{array} { c c c c c } { 0 } & { | 0 } & { \gamma _ { 2 } - \gamma _ { 1 } } & { 2 \gamma _ { 1 } - 2 \gamma _ { 2 } } & { 2 \gamma _ { 2 } - \gamma _ { 3 } } & { \gamma _ { 3 } - 2 \gamma _ { 1 } } \\ { 0 } & { 0 } & { 0 } & { 0 } & { 2 \gamma _ { 2 } } & { - 2 \gamma _ { 1 } } \\ { 2 \gamma _ { 2 } - \gamma _ { 2 } } & { 0 } & { 0 } & { \gamma _ { 1 } - \gamma _ { 2 } } & { 2 \gamma _ { 2 } } & { - 2 \gamma _ { 1 } } \\ { 2 \gamma _ { 3 } - 2 \gamma _ { 2 } } & { 0 } & { - 2 \gamma _ { 2 } } & { 0 } & { - 2 \gamma _ { 2 } - \gamma _ { 3 } } & { 2 \gamma _ { 1 } + \gamma _ { 3 } } \\ { 2 \gamma _ { 1 } - \gamma _ { 3 } } & { 0 } & { 2 \gamma _ { 1 } } & { - 2 \gamma _ { 1 } - \gamma _ { 3 } } & { 0 } & { 2 \gamma _ { 3 } } \end{array} \right) .
$$

Actually if we use a different parametrization of the $\mathbf { C }$ matrix

$$
\begin{array} { r } { \mathbf { C } = \left( \begin{array} { c c c } { 0 } & { \delta _ { 1 } + 2 \delta _ { 2 } + \delta _ { 3 } } & { - \delta _ { 1 } } \\ { - \delta _ { 1 } - 2 \delta _ { 2 } - \delta _ { 3 } } & { 0 } & { \delta _ { 3 } } \\ { \delta _ { 1 } } & { - \delta _ { 3 } } & { 0 } \end{array} \right) , } \end{array}
$$

we can obtain the $\mathbf { A } ^ { \prime }$ matrix more directly. Introducing the charges

$$
\begin{array} { r } { \mathbf { q } _ { 1 } = \left( 0 | 0 , 1 , - 2 , 1 , 1 \right) , } \\ { \mathbf { q } _ { 2 } = \left( 1 | 0 , 0 , 1 , - 2 , 0 \right) , } \\ { \mathbf { q } _ { 3 } = \left( 1 | 0 , 0 , 1 , 0 , - 2 \right) , } \end{array}
$$

the twist matrix can be obtained directly as

$$
\mathbf { A } ^ { \prime } = \frac { 1 } { 2 } \delta _ { 1 } ( \mathbf { q } _ { 1 } ^ { T } \mathbf { q } _ { 2 } - \mathbf { q } _ { 2 } ^ { T } \mathbf { q } _ { 1 } ) + \frac { 1 } { 2 } \delta _ { 2 } ( \mathbf { q } _ { 2 } ^ { T } \mathbf { q } _ { 3 } - \mathbf { q } _ { 3 } ^ { T } \mathbf { q } _ { 2 } ) + \frac { 1 } { 2 } \delta _ { 3 } ( \mathbf { q } _ { 3 } ^ { T } \mathbf { q } _ { 1 } - \mathbf { q } _ { 1 } ^ { T } \mathbf { q } _ { 3 } ) .
$$

# 2.2.2 The $\eta = - 1$ grading

In the following sections,we mainly work in the $\eta = - 1$ grading. Since it is the grading that makes easier to write the Bethe equations for the $s l ( 2 )$ sector, it can be called $s l ( 2 )$ -favored grading, or $s l ( 2 )$ grading for shortness sake, throughout the rest of the paper. In Appendix B we give the result on the the $\eta = + 1$ grading (also called $s u ( 2 )$ -favored or $s u ( 2 )$ grading for shortness sake). In the $s l ( 2 )$ （204号 grading, the actions of the creation operators read

$$
\begin{array} { r l } & { \mathcal { B } _ { 1 } : Y ^ { 3 } \to \psi _ { 4 - } , Y ^ { 4 } \to \psi _ { 3 - } , Y _ { 1 } ^ { \dagger } \to \psi ^ { \dagger 2 - } , Y _ { 2 } ^ { \dagger } \to \psi ^ { \dagger 1 - } , } \\ & { \mathcal { B } _ { 2 } : Y ^ { 2 } \to Y ^ { 3 } , \psi _ { 3 \pm } \to \psi _ { 2 \pm } , } \\ & { \mathcal { B } _ { 3 } : \psi ^ { \dagger 1 + } \to Y _ { 3 } ^ { \dagger } , \psi _ { 4 + } \to Y ^ { 2 } , \psi ^ { \dagger 3 + } \to Y _ { 1 } ^ { \dagger } , \psi _ { 2 + } \to Y ^ { 4 } , } \\ & { \mathcal { B } _ { 4 } : Y ^ { 1 } \to \psi _ { 4 + } , Y ^ { 4 } \to \psi _ { 1 + } , Y _ { 2 } ^ { \dagger } \to \psi ^ { \dagger 3 + } , Y _ { 3 } ^ { \dagger } \to \psi ^ { \dagger 2 + } , } \\ & { \mathcal { B } _ { \bar { 4 } } : Y ^ { 2 } \to \psi _ { 3 + } , Y ^ { 3 } \to \psi _ { 2 + } , Y _ { 1 } ^ { \dagger } \to \psi ^ { \dagger 4 + } , Y _ { 4 } ^ { \dagger } \to \psi ^ { \dagger 1 + } . } \end{array}
$$

The twist matrix is

<html><body><table><tr><td rowspan="7">A =1 2</td><td rowspan="2">0</td><td rowspan="2">2-1</td><td colspan="2">2(1-72)</td><td rowspan="2">22-1</td><td colspan="2">1+2-23</td><td rowspan="2">-γ1-γ2+3</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>21-22 2(22 - γ1)</td><td>0</td><td></td><td>Y1-2</td><td></td><td>2-1</td><td>1+2</td><td>11-2</td></tr><tr><td></td><td>γ2-1</td><td></td><td>0</td><td>γ1-22</td><td></td><td>12/1-22-2/3</td><td>γ1+γ2+γ3</td></tr><tr><td>γ1-2</td><td>1-2</td><td></td><td>2-1</td><td></td><td>0</td><td>3</td><td>123</td></tr><tr><td>-21-22+3</td><td>11-γ2</td><td></td><td>γ1 +2+3</td><td>173</td><td></td><td>0</td><td>0</td></tr><tr><td>1+γ2- /3</td><td>γ1+2</td><td></td><td>1γ1-γ2-γ3</td><td>3</td><td></td><td>0</td><td>0</td></tr></table></body></html>

In this case the three charges are found to be

$$
\begin{array} { r c l } { \mathbf q _ { 1 } } & { = } & { ( 0 | 1 , - 2 , 1 , 0 , 0 ) , } \\ { \mathbf q _ { 2 } } & { = } & { ( 1 | 0 , 1 , - 1 , - 1 , 1 ) , } \\ { \mathbf q _ { 3 } } & { = } & { ( 1 | 0 , 1 , - 1 , 1 , - 1 ) , } \end{array}
$$

and the twist matrix expressed in terms of $\delta$ 'sis

<html><body><table><tr><td rowspan="2">1 A=</td><td rowspan="2">0</td><td rowspan="2">83-81 0</td><td>2δ1-283</td><td>8-81</td><td>282</td><td>-282</td></tr><tr><td>51-03</td><td>8-81</td><td>-01-83</td><td>81+83</td></tr><tr><td>2</td><td>81-83 2δ3-2δ1 81-83 -282 282</td><td>8-81 81-83 81+83 -01-83</td><td>0 83-81 -2δ1-2δ2-283</td><td>81-83 0 δ1+282+δ3 2δ1+2δ2+283 -81-282-83</td><td>-81-282-83 0 0</td><td>2δ1 +2δ2+2δ3-2δ1-2δ2-203 δ1+2δ2+03 0</td></tr></table></body></html>

# 2.3 Duality properties

In this section we investigate the duality properties of the twist charges appearing in the Bethe ansatz equations,which were derived in detail in [42]. In that paper a series of relations between twist charges was obtained for orbifold ABJM theories due to the dynamical and fermionic duality. For $\gamma$ -deformation of ABJM theory,the case is similar,at least at the level of the Bethe ansatz equations. It turns out that all the relations are nicely satisfied.

Let's consider them carefully. The first important relation in $\gamma$ -deformed ABJM theory takes the form

$$
( \mathbf { A K } ) _ { 3 } = ( \mathbf { A K } ) _ { 1 } - ( \mathbf { A K } ) _ { 0 }
$$

for the $s l ( 2 )$ grading,and

$$
( \tilde { \bf A } \tilde { \bf K } ) _ { 3 } = ( \tilde { \bf A } \tilde { \bf K } ) _ { 1 } + ( \tilde { \bf A } \tilde { \bf K } ) _ { 0 }
$$

for the $s u ( 2 )$ grading. Here and in the following ${ \bf K } = ( L | K _ { 1 } , K _ { 2 } , K _ { 3 } , K _ { 4 } , K _ { \bar { 4 } } ) ; { \bf K }$ and $\mathbf { K } ^ { \prime }$ are defined in analogous way for the $s u ( 2 )$ and distinguished gradings,respectively. Here we used a tilde to denote the variables in the $s u ( 2 )$ grading. See Appendix B for its explicit expression. Relations (2.18),(2.19) are due to the dynamic duality property, which is essential for alloop Bethe ansatz equations. They are satisfied in the two gradings separately. They are actually relations linking elements of the twist matrix since the excitation numbers in both sides of these equations are the same.

The remaining relations are

$$
( \tilde { \bf A } \tilde { \bf K } ) _ { 4 } + ( \tilde { \bf A } \tilde { \bf K } ) _ { 3 } = ( { \bf A } { \bf K } ) _ { 4 } , ( \tilde { \bf A } \tilde { \bf K } ) _ { \bar { 4 } } + ( \tilde { \bf A } \tilde { \bf K } ) _ { 3 } = ( { \bf A } { \bf K } ) _ { \bar { 4 } } .
$$

$$
( \tilde { \bf A } \tilde { \bf K } ) _ { 0 } - 2 ( \tilde { \bf A } \tilde { \bf K } ) _ { 3 } = ( \tilde { \bf A } \tilde { \bf K } ) _ { 2 } - ( { \bf A } { \bf K } ) _ { 2 } .
$$

$$
( \mathbf { A K } ) _ { 0 } - 2 ( \tilde { \mathbf { A } } \tilde { \mathbf { K } } ) _ { 3 } = ( \tilde { \mathbf { A } } \tilde { \mathbf { K } } ) _ { 2 } - ( \mathbf { A K } ) _ { 2 } .
$$

$$
( \tilde { \bf A } \tilde { \bf K } ) _ { 1 } + ( { \bf A } { \bf K } ) _ { 1 } = 0 .
$$

$$
( \tilde { \bf A } \tilde { \bf K } ) _ { 3 } + ( { \bf A K } ) _ { 3 } = 0 .
$$

They are essential for the equivalence of the two different gradings and are all satisfied if we take the change of both twist matrix and excitation numbers into account when we switch from one grading to the other. Recall that the excitation numbers are related as 4

$$
\begin{array} { l } { { \tilde { K } _ { 1 } = K _ { 2 } - K _ { 1 } , } } \\ { { \tilde { K } _ { 3 } = K _ { 2 } + K _ { 4 } + K _ { \bar { 4 } } - K _ { 3 } , } } \\ { { \tilde { K } _ { i } = K _ { i } , \quad i = 2 , 4 , \bar { 4 } . } } \end{array}
$$

The distinguished grading can not be used for all loop ABAs, so we will not discuss dynamical duality in this grading. However this gradingcan be used at two loop order. This grading is related to the $s u ( 2 )$ grading by fermionic duality. The relations among excitation numbers are

$$
\begin{array} { r c l } { { { \tilde { K } } _ { 1 } } } & { { = } } & { { K _ { 3 } ^ { \prime } - K _ { 2 } ^ { \prime } , } } \\ { { } } & { { } } & { { } } \\ { { { \tilde { K } } _ { 2 } } } & { { = } } & { { K _ { 1 } ^ { \prime } + K _ { 3 } ^ { \prime } - K _ { 2 } ^ { \prime } , } } \\ { { } } & { { } } & { { } } \\ { { { \tilde { K } } _ { 3 } } } & { { = } } & { { K _ { 3 } ^ { \prime } , } } \\ { { } } & { { } } & { { } } \\ { { { \tilde { K } } _ { 4 } } } & { { = } } & { { K _ { 4 } ^ { \prime } , } } \\ { { } } & { { } } & { { } } \\ { { { \tilde { K } } _ { \bar { 4 } } } } & { { = } } & { { K _ { \bar { 4 } } ^ { \prime } . } } \end{array}
$$

Here we used a prime to denote the variables in the distinguished grading.From the fermionic duality, we obtain the following relations

$$
\begin{array} { r c l } { ( \tilde { \bf A } \tilde { \bf K } ) _ { 1 } } & { = } & { - ( { \bf A } ^ { \prime } { \bf K } ^ { \prime } ) _ { 1 } - ( { \bf A } ^ { \prime } { \bf K } ^ { \prime } ) _ { 2 } , } \\ { ( \tilde { \bf A } \tilde { \bf K } ) _ { 2 } } & { = } & { ( { \bf A } ^ { \prime } { \bf K } ^ { \prime } ) _ { 1 } , } \\ { ( \tilde { \bf A } \tilde { \bf K } ) _ { 3 } } & { = } & { ( { \bf A } ^ { \prime } { \bf K } ^ { \prime } ) _ { 2 } + ( { \bf A } ^ { \prime } { \bf K } ^ { \prime } ) _ { 3 } , } \\ { ( \tilde { \bf A } \tilde { \bf K } ) _ { 4 } } & { = } & { ( { \bf A } ^ { \prime } { \bf K } ^ { \prime } ) _ { 4 } , } \\ { ( \tilde { \bf A } \tilde { \bf K } ) _ { 4 } } & { = } & { ( { \bf A } ^ { \prime } { \bf K } ^ { \prime } ) _ { \bar { 4 } } . } \end{array}
$$

It is not hard to confirm that all these relations are valid.

# 3 Asymptotic Bethe ansatz

Having obtained the twist matrix, it is straightforward to write down the asymptotic Bethe ansatz equation. We will mainly work in the $s l ( 2 )$ favored grading. Let's first introduce some notation useful in the following. First we define the Zhukovski variable $x$ through

$$
x + \frac { 1 } { x } = \frac { u } { h ( \lambda ) } ,
$$

where $h ( \lambda )$ is the so-called interpolating function [58]-[60] which plays the role of effective coupling in the Bethe ansatz and TBA.Unlike the ${ \mathcal N } = 4$ SYM, it has nontrivial dependence on $\lambda$ . It has the following behavior at weak coupling [61]-[63],

$$
h ( \lambda ) = \lambda - \frac { \pi ^ { 2 } } { 3 } \lambda ^ { 3 } + \mathcal { O } ( \lambda ^ { 5 } ) ,
$$

and strong coupling [64]-[67],

$$
h ( \lambda ) = \sqrt { \frac { \lambda } { 2 } } - { \frac { \log 2 } { 2 \pi } } - { \frac { 1 } { 4 8 \sqrt { 2 \lambda } } } + \mathcal { O } ( ( { \frac { 1 } { \sqrt { \lambda } } } ) ^ { 2 } ) .
$$

Recently its exact form has been conjectured in [68] by comparing the quantum spectral curve method [19] and supersymmetric localization. The “physical” and “mirror” branch of the function $x ( u )$ are defined as

$$
x ^ { \mathrm { p h } } ( u ) = \frac { 1 } { 2 } \left( \frac { u } { h } + \sqrt { \frac { u } { h } - 2 } \sqrt { \frac { u } { h } + 2 } \right) , x ^ { \mathrm { m i r } } ( u ) = \frac { 1 } { 2 } \left( \frac { u } { h } + i \sqrt { 4 - \frac { u ^ { 2 } } { h ^ { 2 } } } \right) .
$$

In this section we will use $x ( u )$ to mean $x ^ { \mathrm { p h } } ( u )$ . The energy and momentum for a single Bethe root $u _ { 4 }$ and $u _ { \bar { 4 } }$ are given by

$$
\epsilon = { \frac { 1 } { 2 } } + h ( \lambda ) \left( { \frac { i } { x ^ { + } } } - { \frac { i } { x ^ { - } } } \right) , p = { \frac { 1 } { i } } \log { \frac { x ^ { + } } { x ^ { - } } } ,
$$

and the total momentum corresponding to the first conserved charge $\mathcal { Q } _ { 1 }$ is

$$
\mathcal { Q } _ { 1 } = \sum _ { j = 1 } ^ { K _ { 4 } } p ( u _ { 4 , j } ) + \sum _ { j = 1 } ^ { K _ { \bar { 4 } } } p ( u _ { \bar { 4 } , j } ) .
$$

Using the notation of [38], the Bethe equations have the form

$$
\begin{array} { r l } & { { e ^ { - z ^ { 2 z / ( 4 8 { \bf K } ) _ { 1 } } } } = { e ^ { \imath { \cal Q } _ { 2 } } } \frac { Q _ { 2 } ^ { 2 } } { Q _ { 2 } ^ { 2 } } { { \cal Q } _ { 2 } ^ { 2 } } \Big | _ { { { \bf 0 } , 1 } } , } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad }  \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \times \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \end{array}
$$

where various functions above are defined as5 :

$$
\begin{array} { l } { { \displaystyle R _ { l } ^ { ( \pm ) } = \prod _ { j = 1 } ^ { K _ { l } } \left( x ( u ) - x _ { l , j } ^ { \mp } \right) \ : , R _ { l } = \prod _ { j = 1 } ^ { K _ { l } } \left( x ( u ) - x _ { l , j } \right) \ : , } } \\ { { \displaystyle B _ { l } ^ { ( \pm ) } = \prod _ { j = 1 } ^ { K _ { l } } \left( \frac { 1 } { x ( u ) } - x _ { l , j } ^ { \mp } \right) \ : , \ : B _ { l } = \prod _ { j = 1 } ^ { K _ { l } } \left( \frac { 1 } { x ( u ) } - x _ { l , j } \right) \ : , } } \\ { { \displaystyle Q _ { l } = \prod _ { j = 1 } ^ { K _ { l } } \left( u - u _ { l , j } \right) \ : , S _ { l } = \prod _ { j = 1 } ^ { K _ { l } } \sigma _ { B E S } \left( x ( u ) , x _ { l , j } \right) \ : , } } \end{array}
$$

and the functions with no index mean a product of type-4 and type-4 ones: $R = R _ { 4 } R _ { \bar { 4 } } , B = B _ { 4 } B _ { \bar { 4 } } , S =$ $S _ { 4 } S _ { \bar { 4 } }$ . We have used the general notation

$$
f ^ { [ \pm a ] } \equiv f ( u \pm i a / 2 ) , f ^ { \pm } \equiv f ( u \pm i / 2 ) , f ^ { \pm \pm } \equiv f ( u \pm i ) .
$$

The Bethe roots must additionally be constrained by the momentum condition

$$
\prod _ { j = 1 } ^ { K _ { 4 } } \frac { x _ { 4 , j } ^ { + } } { x _ { 4 , j } ^ { - } } \prod _ { j = 1 } ^ { K _ { \bar { 4 } } } \frac { x _ { \bar { 4 } , j } ^ { + } } { x _ { \bar { 4 } , j } ^ { - } } = e ^ { - 2 \pi i ( \mathbf { A } \mathbf { K } ) _ { 0 } } \Leftrightarrow \mathcal { Q } _ { 1 } = 2 \pi m - 2 \pi ( \mathbf { A } \mathbf { K } ) _ { 0 } ,
$$

where $m$ is an integer. The anomalous dimension of the single-trace operator is given by

$$
E = h ( \lambda ) ( \sum _ { j = 1 } ^ { K _ { 4 } } ( \frac { i } { x _ { 4 , j } ^ { + } } - \frac { i } { x _ { 4 , j } ^ { - } } ) + \sum _ { j = 1 } ^ { K _ { \bar { 4 } } } ( \frac { i } { x _ { \bar { 4 } , j } ^ { + } } - \frac { i } { x _ { \bar { 4 } , j } ^ { - } } ) ) .
$$

# 4 The y-deformed AdS $^ 4$ /CFT $3$ Y-system

In this section,we briefly review some basic facts about the AdS $_ 4$ /CFT $^ 3$ Y-system,for a thorough treatment see [17,18]. The exact spectral information of the AdS/CFT correspondence could be computed through Y-functions which are constrained by the Y-system equations. Because we twist our theory, the TBA equations are slightly changed by adding some appropriate chemical potentials.

![](images/e6477d0eeae95fe62dad0c64bd12095e447860c28d40c9fc7b69be84b6e3eaa2.jpg)  
Figure 1: The AdS $_ 4$ /CFT $^ 3$ Y-system. As shown in the figure,we have considered the most generic case when the two black node Y-functions are not equal to each other. We denote them as $Y _ { \pmb { \nu } _ { a } }$ and $Y _ { \pmb { \mathscr { A } } _ { a } }$ in the main body.

However the Y-system is the same as the one for the untwisted theory. The equations of a generic Y-system basically have the form

$$
Y _ { M } ^ { + } Y _ { M } ^ { - } = \frac { \prod _ { H } ( 1 + Y _ { H } ) } { \prod _ { V } ( 1 + 1 / Y _ { V } ) } ,
$$

where $Y _ { M } ^ { \pm } = Y _ { M } ( u \pm i / 2 )$ and the index $H ( V )$ represent the nodes nearest to the $M$ node in the horizontal(vertical) direction in the Fig. 1. The explicit expressions of AdS $^ 4$ /CFT $_ 3$ Y-system equations have some unusual form,however they are not relevant here. Once the Y-functions are found, the exact energy of a state can be expressed by

$$
\mathrm { ~  ~ \Gamma ~ } = \sum _ { j = 1 } ^ { K _ { 4 } } \epsilon _ { 1 } ^ { \mathrm { p h } } ( u _ { 4 , j } ) + \sum _ { j = 1 } ^ { K _ { 4 } } \epsilon _ { 1 } ^ { \mathrm { p h } } ( u _ { 4 , j } ) + \delta E , \delta E = \sum _ { a = 1 } ^ { \infty } \int _ { - \infty } ^ { \infty } \frac { d u } { 2 \pi i } \frac { \partial \epsilon _ { a } ^ { \mathrm { m i r } } ( u ) } { \partial u } \log ( 1 + Y _ { \star _ { a } } ^ { \mathrm { m i r } } ) ( 1 + Y _ { \star _ { a } } ^ { \mathrm { m i r } } ) ,
$$

where the rapidities $u _ { 4 , j }$ and $u _ { 4 , j }$ are fixed by the exact Bethe ansatz equations

$$
{ \cal Y } _ { \bullet _ { 1 } } ^ { \mathrm { p h } } ( u _ { 4 , j } ) = - 1 , \quad { \cal Y } _ { \bullet _ { 1 } } ^ { \mathrm { p h } } ( u _ { \bar { 4 } , j } ) = - 1 .
$$

（204号 $\epsilon _ { n }$ is the asymptotic energy of a physical $n$ -magnon bound state when evaluated in the physical kinematics and defines the asymptotic momenta of mirror bound states when evaluated in the mirror kinematics:

$$
\epsilon _ { n } ( u ) = \frac { n } { 2 } + h ( \lambda ) \left( \frac { i } { x ^ { [ + n ] } } - \frac { i } { x ^ { [ - n ] } } \right) .
$$

The index‘ph’ and‘mir’ labeled on functions $\epsilon _ { a } ( \boldsymbol { u } )$ ， $Y _ { \pmb { \nu } _ { a } } ( u )$ and $Y _ { \pmb { \mathscr { A } } _ { a } } ( u )$ in eq. (4.2) and eq. (4.3) are evaluated at physical and mirror kinematics defined in eq. (3.4) respectively. Eq. (4.4) is valid for both physical and mirror kinematics.

# 4.1 The twisted generating functional

Our asymptotic Bethe ansatz equations can be derived from the twisted AdS $_ 4$ /CFT $^ 3$ Y-system. Inspired by [38],we propose a twisted generating functional $\mathcal { W }$ which generates an infinite set of transfer matrix eigenvalues of symmetric and anti-symmetric irreducible representations $T _ { 1 , s } , T _ { a , 1 }$ as

$$
\mathcal { W } = \sum _ { s = 0 } ^ { \infty } T _ { 1 , s } ^ { [ 1 - s ] } D ^ { s } \ , \qquad \mathcal { W } ^ { - 1 } = \sum _ { a = 1 } ^ { \infty } ( - 1 ) ^ { a } T _ { a , 1 } ^ { [ 1 - a ] } D ^ { a } \ ,
$$

where $D = e ^ { - i \partial _ { u } }$ . The generating functional we propose in the $s l ( 2 )$ favored grading is

$$
\begin{array} { r } { \upsilon = \left( 1 - \tau _ { 1 } \frac { B ^ { ( + ) + } Q _ { 1 } ^ { - } R ^ { ( + ) - } } { B ^ { ( - ) + } Q _ { 1 } ^ { + } R ^ { ( - ) - } } D \right) \frac { 1 } { \left( 1 - \tau _ { 2 } \frac { Q _ { 1 } ^ { - } Q _ { 2 } ^ { + + } R ^ { ( + ) - } } { Q _ { 1 } ^ { + } Q _ { 2 } R ^ { ( - ) - } } D \right) } \frac { 1 } { \left( 1 - \frac { 1 } { \tau _ { 2 } } \frac { Q _ { 2 } ^ { -- } Q _ { 3 } ^ { + } R ^ { ( + ) - } } { Q _ { 2 } Q _ { 3 } ^ { - } R ^ { ( - ) - } } D \right) } \left( 1 - \frac { 1 } { \tau _ { 1 } } \frac { Q _ { 3 } ^ { + } R ^ { ( - ) - } } { Q _ { 3 } ^ { - } R ^ { ( - ) - } } D \right) } \end{array}
$$

Then we find

$$
T _ { 1 , 1 } = \frac { R ^ { ( + ) - } } { R ^ { ( - ) - } } \left[ \tau _ { 2 } \frac { Q _ { 1 } ^ { - } Q _ { 2 } ^ { + + } } { Q _ { 1 } ^ { + } Q _ { 2 } } - \tau _ { 1 } \frac { B ^ { ( + ) + } Q _ { 1 } ^ { - } } { B ^ { ( - ) + } Q _ { 1 } ^ { + } } + \frac { 1 } { \tau _ { 2 } } \frac { Q _ { 2 } ^ { -- } Q _ { 3 } ^ { + } } { Q _ { 2 } Q _ { 3 } ^ { - } } - \frac { 1 } { \tau _ { 1 } } \frac { Q _ { 3 } ^ { + } R ^ { ( - ) - } } { Q _ { 3 } ^ { - } R ^ { ( + ) - } } \right] .
$$

The analyticity of $T _ { 1 , 1 }$ at zeros of the denominators will give the asymptotic Bethe equations for $u _ { 1 } , u _ { 2 } , u _ { 3 }$ （

$$
\left. \frac { \tau _ { 1 } } { \tau _ { 2 } } \frac { B ^ { ( + ) } Q _ { 2 } ^ { - } } { B ^ { ( - ) } Q _ { 2 } ^ { + } } \right| _ { u _ { 1 , k } } = 1 \left. , \tau _ { 2 } ^ { 2 } \frac { Q _ { 2 } ^ { + + } Q _ { 1 } ^ { - } Q _ { 3 } ^ { - } } { Q _ { 2 } ^ { -- } Q _ { 1 } ^ { + } Q _ { 3 } ^ { + } } \right| _ { u _ { 2 , k } } = - 1 \left. , \frac { \tau _ { 1 } } { \tau _ { 2 } } \frac { Q _ { 2 } ^ { - } R ^ { ( + ) } } { Q _ { 2 } ^ { + } R ^ { ( - ) } } \right| _ { u _ { 3 , k } } = 1 .
$$

We see that if we identify the twists $\tau _ { 1 } , \tau _ { 2 }$ as

$$
\begin{array} { l } { { \tau _ { 1 } = e ^ { i \frac { \pi } { 2 } \left( ( \delta _ { 1 } - \delta _ { 3 } ) ( K _ { 1 } - 2 K _ { 2 } + K _ { 3 } ) - \delta _ { 2 } ( 2 K _ { 4 } - 2 K _ { \bar { 4 } } ) \right) } , } } \\ { { \tau _ { 2 } = e ^ { i \frac { \pi } { 2 } \left( ( \delta _ { 3 } - \delta _ { 1 } ) ( 2 L + K _ { 1 } - K _ { 3 } ) + ( \delta _ { 1 } + \delta _ { 2 } + \delta _ { 3 } ) ( 2 K _ { 4 } - 2 K _ { \bar { 4 } } ) \right) } , } } \end{array}
$$

we find exactly our Bethe equations for $u _ { 1 } , u _ { 2 } , u _ { 3 }$ in the $s l ( 2 )$ grading. Notice that the consistence of the first and the third equations in (4.8) is guaranteed by eq. (2.18), which also plays an important role for the validity of the dynamical duality transformation.

# 4.2 Consistency checks

In this section we perform some consistency checks along the lines of [32,33]. We calculate the twists appearing in the total momentum and the twisted generating functional through the twisted boundary condition of fields eq. (2.3). In order to do this,we had better to rewrite the twist matrix $\mathbf { A }$ in terms of the three conserved angular momentum instead of the excitation numbers. In the $s l ( 2 )$ grading,we have

$$
\begin{array} { l } { { J _ { 1 } { = } \displaystyle \frac { p _ { 1 } } { 2 } { = } \displaystyle \frac { 1 } { 2 } ( L - K _ { 4 } + K _ { \bar { 4 } } + K _ { 2 } - K _ { 3 } ) , } } \\ { { J _ { 2 } { = } \displaystyle \frac { p _ { 2 } } { 2 } { = } \displaystyle \frac { 1 } { 2 } ( L + K _ { 4 } - K _ { \bar { 4 } } + K _ { 2 } - K _ { 3 } ) , } } \\ { { J _ { 3 } { = } q + \displaystyle \frac { p _ { 1 } + p _ { 2 } } { 2 } { = } L + K _ { 1 } - K _ { 2 } . } } \end{array}
$$

Notice that for the $s l ( 2 )$ grading, the relation between $[ p _ { 1 } , q , p _ { 2 } ]$ and the Dynkin labels $r _ { j } , j = 1 , \cdots , 4 , 4$ of $O S p ( 6 | 4 )$ is(see appendix B in [69] for more information)

$$
\begin{array} { r c l } { { p _ { 1 } } } & { { = } } & { { r _ { 3 } + r _ { 4 } , } } \\ { { q } } & { { = } } & { { r _ { 2 } , } } \\ { { p _ { 2 } } } & { { = } } & { { r _ { 3 } + r _ { \bar { 4 } } . } } \end{array}
$$

The total momentum of the spin chain reads

$$
P = 2 \pi m - 2 \pi ( { \bf A } { \bf K } ) _ { 0 } = 2 \pi m - \pi ( \gamma _ { 1 } ( 2 J _ { 2 } - J _ { 3 } ) + \gamma _ { 2 } ( J _ { 3 } - 2 J _ { 1 } ) + \gamma _ { 3 } ( J _ { 1 } - J _ { 2 } ) ) .
$$

Since we choose the vacuum as $\mathrm { T r } ( Y ^ { 1 } Y _ { 4 } ^ { \dagger } ) ^ { L }$ , the twisted boundary condition for the combined fields （20 $Y ^ { 1 } Y _ { 4 } ^ { \dagger }$ gives the total momentum

$$
Y ^ { 1 } Y _ { 4 } ^ { \dag } ( 2 \pi ) = Y ^ { 1 } Y _ { 4 } ^ { \dag } ( 0 ) e ^ { i ( \delta \phi _ { 3 } + \frac { \delta \phi _ { 1 } + \delta \phi _ { 2 } } { 2 } ) } = e ^ { i P }
$$

as we expected. Here and in the following, $\delta \phi _ { i } = - 2 \pi \epsilon _ { i j k } \gamma _ { j } J _ { k }$ . Let us make some comments on these phases $\tau _ { 1 } , \tau _ { 2 }$ , whose origin has a very nice explanation. In literature [32, 33], the transfer matrix seems prha r( $\gamma$ n terad -d $^ { 5 }$ /CFT $^ 4$ Batd are two hbre What i hc $\tau _ { 1 }$ $x _ { 4 , j } ^ { \pm }$ $x _ { \bar { 4 } , j } ^ { \pm }$

$$
\tau _ { 1 } = e ^ { - \pi i ( \mathbf { A K } ) _ { 0 } } = \prod _ { j = 1 } ^ { K _ { 4 } } \sqrt { \frac { x _ { 4 , j } ^ { + } } { x _ { 4 , j } ^ { - } } } \prod _ { j = 1 } ^ { K _ { { \bar { 4 } } } } \sqrt { \frac { x _ { { \bar { 4 } } , j } ^ { + } } { x _ { { \bar { 4 } } , j } ^ { - } } } ,
$$

there is only one apparent phase $\tau _ { 2 }$ left to be explained. The global symmetry $O S p ( 6 | 4 )$ of AdS $^ 4$ /CFT $^ 3$ （204号 breaks down to centrally extended $S U ( 2 | 2 )$ after we choose the vacuum. We can insert some integrable twist $G \in S U ( 2 ) _ { r } \times S U ( 2 ) _ { G } \subset S U ( 2 | 2 )$ into the transfer matrix [33]. Consider a group element of the form

$$
G = \mathrm { d i a g } ( e ^ { i \varphi _ { 1 } } , e ^ { - i \varphi _ { 1 } } , e ^ { i \varphi _ { 2 } } , e ^ { - i \varphi _ { 2 } } ) \in S U ( 2 ) _ { r } \times S U ( 2 ) _ { G }
$$

For the $\gamma$ -deformation, we set $\varphi _ { 1 } = 0$ since there are no deformations in the $A d S _ { 4 }$ part of the string theory background. Then only $e ^ { i \varphi _ { 2 } }$ is relevant and this is consistent with that $\mathrm { d i a g } ( e ^ { i \varphi _ { 2 } } , e ^ { - i \varphi _ { 2 } } ) \in$ $S U ( 2 ) _ { G }$ is the unbroken part of $S U ( 4 ) _ { R }$ .The $S U ( 2 ) _ { G }$ transforms $Y ^ { 2 }  Y ^ { 3 }$ or $Y _ { 3 } ^ { \dagger }  Y _ { 2 } ^ { \dagger }$ .This suggests us to consider the twisted boundary condition of the combined fields

$$
Y _ { 2 } ^ { \dagger } Y ^ { 3 } ( 2 \pi ) = Y _ { 2 } ^ { \dagger } Y ^ { 3 } ( 0 ) e ^ { i ( { \frac { \delta \phi _ { 1 } + \delta \phi _ { 2 } } { 2 } } - \delta \phi _ { 3 } ) } \equiv Y _ { 2 } ^ { \dagger } Y ^ { 3 } ( 0 ) e ^ { i \psi }
$$

After rewriting $\tau _ { 2 }$ in terms of the three conserved angular momentum $J _ { 1 } , J _ { 2 } , J _ { 3 }$ as

$$
\tau _ { 2 } = e ^ { i ( { \frac { \pi } { 2 } } ( - \gamma _ { 1 } ( 2 J _ { 2 } + J _ { 3 } ) + \gamma _ { 2 } ( 2 J _ { 1 } + J _ { 3 } ) + \gamma _ { 3 } ( J _ { 1 } - J _ { 2 } ) ) ) } ,
$$

we find the relation

$$
\tau _ { 2 } = e ^ { - i \varphi _ { 2 } } = e ^ { - i \frac { \psi } { 2 } } ,
$$

which confirms our proposal.

# 4.3 The asymptotic solution

The Bethe equations for momentum-carrying $u _ { 4 } , u _ { \bar { 4 } }$ can be found from the exact Bethe equations (4.3). The asymptotic large $L$ solutions of the black nodes are given by [17]

$$
\begin{array} { l } { { \displaystyle Y _ { { \bf d } _ { a } } \simeq \left( \frac { x ^ { [ - a ] } } { x ^ { [ + a ] } } \right) ^ { L } T _ { a , 1 } \prod _ { n = - \frac { a - 1 } { 2 } } ^ { \frac { a - 1 } { 2 } } \Phi _ { 4 } ^ { \theta _ { n a } ^ { E } } ( u + i n ) \Phi _ { \bar { 4 } } ^ { \theta _ { n a } ^ { O } } ( u + i n ) ~ , } } \\ { { \displaystyle Y _ { { \bf b } _ { a } } \simeq \left( \frac { x ^ { [ - a ] } } { x ^ { [ + a ] } } \right) ^ { L } T _ { a , 1 } \prod _ { n = - \frac { a - 1 } { 2 } } ^ { \frac { a - 1 } { 2 } } \Phi _ { 4 } ^ { \theta _ { n a } ^ { O } } ( u + i n ) \Phi _ { \bar { 4 } } ^ { \theta _ { n a } ^ { E } } ( u + i n ) ~ , } } \end{array}
$$

where $\theta _ { n a } ^ { E }$ is $0$ for even and $1$ for odd factors in the product,

$$
{ \theta } _ { n a } ^ { E } \equiv \left\{ \begin{array} { c l } { { 1 , } } & { { n + \frac { a - 1 } { 2 } \mathrm { ~ i s ~ e v e n } } } \\ { { 0 , } } & { { n + \frac { a - 1 } { 2 } \mathrm { ~ i s ~ o d d } } } \end{array} \right.
$$

and $\theta _ { n a } ^ { O } \equiv 1 - \theta _ { n a } ^ { E }$ . To match the ABA equations for $u _ { 4 }$ and $u _ { \bar { 4 } }$ ， we have to deform the asymptotic solutions of the two black node Y-functions by the phases $\tau _ { 0 }$ and $\tau _ { 0 }$ ， respectively.

$$
( \boldsymbol { u } ) = \frac { B _ { 4 } ^ { ( + ) + } R _ { 4 } ^ { ( - ) - } B _ { 1 } ^ { + } B _ { 3 } ^ { - } } { B _ { 4 } ^ { ( - ) - } R _ { 4 } ^ { ( + ) + } B _ { 1 } ^ { - } B _ { 3 } ^ { + } } \left( \prod _ { j = 1 } ^ { K _ { 4 } } \frac { x _ { 4 , j } ^ { + } } { x _ { 4 , j } ^ { - } } \right) S \tau _ { 0 } , \quad \Phi _ { \vec { \mathbf { f } } } ( \boldsymbol { u } ) = \frac { B _ { 4 } ^ { ( + ) + } R _ { 4 } ^ { ( - ) - } B _ { 1 } ^ { + } B _ { 3 } ^ { - } } { B _ { 4 } ^ { ( -- ) - } R _ { 4 } ^ { ( + ) + } B _ { 1 } ^ { - } B _ { 3 } ^ { + } } \left( \prod _ { j = 1 } ^ { K _ { 4 } } \frac { x _ { 4 , j } ^ { + } } { x _ { \overline { { 4 } } , j } ^ { - } } \right) S \tau _ { \vec { \mathbf { 0 } } } ,
$$

where

$$
\begin{array} { r } { \tau _ { 0 } = e ^ { i ( \frac { 3 \pi } { 2 } \delta _ { 1 } ( K _ { 1 } - 2 K _ { 2 } + K _ { 3 } ) - \pi \delta _ { 2 } ( 2 L + 2 K _ { 2 } - 2 K _ { 3 } + K _ { 4 } - K _ { 4 } ) + \frac { \pi } { 2 } \delta _ { 3 } ( K _ { 1 } - 2 K _ { 2 } + K _ { 3 } ) ) } , } \\ { \tau _ { 0 } = e ^ { i ( - \frac { \pi } { 2 } \delta _ { 1 } ( K _ { 1 } - 2 K _ { 2 } + K _ { 3 } ) + \pi \delta _ { 2 } ( 2 L + 2 K _ { 2 } - 2 K _ { 3 } - K _ { 4 } + K _ { 4 } ) - \frac { 3 \pi } { 2 } \delta _ { 3 } ( K _ { 1 } - 2 K _ { 2 } + K _ { 3 } ) ) } . } \end{array}
$$

# 5Applications to $s l ( 2 )$ -like sector

In this section we will apply our proposals and results discussed in the previous sections to the $s l ( 2 )$ 1 like sector. The Y-functions simplify a lot in this sector, where we only excite symmetricall the same number of moment carrying roots $u _ { 4 }$ and $u _ { 4 } ^ { - }$ ： $u _ { 4 , j } = u _ { \bar { 4 } , j }$ . This leads to $Y _ { \bullet _ { a } } = Y _ { \bullet _ { a } } \equiv Y _ { a , 0 }$ ，s0 $\tau _ { 0 } = \tau _ { \bar { 0 } }$ （ and then $\delta _ { 2 } = 0$ . We then have $( \mathbf { A K } ) _ { 0 } = 0 , \tau _ { 1 } = 1$ and generically $\delta _ { 1 } \neq \delta _ { 3 }$ . From this,we know that the two loop Bethe ansatz equations for the twist operators is the same as the ones in the undeformed theory. The solutions of these equations have been studied in [71,72,39]. The deformation affects the results only through $\tau _ { 2 }$ which appears in $T _ { a , 1 }$ . The exact energy can be expressed as

$$
E = 2 \sum _ { j = 1 } ^ { K _ { 4 } } \epsilon _ { 1 } ^ { \mathrm { p h } } ( u _ { 4 , j } ) + \delta E , \delta E = 2 \sum _ { a = 1 } ^ { \infty } \int _ { - \infty } ^ { \infty } \frac { d u } { 2 \pi i } \frac { \partial \epsilon _ { a } ^ { \mathrm { m i r } } } { \partial u } \log ( 1 + Y _ { a , 0 } ^ { \mathrm { m i r } } ) .
$$

In this case, the only non-trivial Baxter polynomial is $\begin{array} { r } { Q _ { 4 } = Q _ { \bar { 4 } } = \prod _ { j = 1 } ^ { K _ { 4 } } ( u - u _ { 4 , j } ) } \end{array}$ . Then the twisted generating functional $\mathcal { W } ^ { - 1 }$ simplifies as

$$
\begin{array} { l } { \displaystyle \sum _ { \iota = 0 } ^ { \infty } ( - 1 ) ^ { a } T _ { a , 1 } ^ { [ 1 - a ] } D ^ { a } = } \\ { \displaystyle 1 - D ) ^ { - 1 } \left( 1 - \tau _ { 2 } \left( \frac { R _ { 4 } ^ { ( + ) - } } { R _ { 4 } ^ { ( - ) - } } \right) ^ { 2 } D \right) \left( 1 - \frac { 1 } { \tau _ { 2 } } \left( \frac { R _ { 4 } ^ { ( + ) - } } { R _ { 4 } ^ { ( - ) - } } \right) ^ { 2 } D \right) \left( 1 - \left( \frac { B _ { 4 } ^ { ( + ) + } R _ { 4 } ^ { ( + ) - } } { B _ { 4 } ^ { ( - ) + } R _ { 4 } ^ { ( - ) - } } \right) ^ { 2 } D \right) ^ { - 1 } . } \end{array}
$$

The asymptotics of the $Y _ { a , 0 }$ functions are then given by

$$
Y _ { a , 0 } ( u ) \simeq \left( \frac { x ^ { \left[ - a \right] } } { x ^ { \left[ + a \right] } } \right) ^ { L } \Phi _ { a } ( u ) T _ { a , 1 } ( u ) ,
$$

where the scalar factor $\Phi _ { a }$ is

$$
\Phi _ { a } ( u ) = \prod _ { k = - \frac { a - 1 } { 2 } } ^ { \frac { a - 1 } { 2 } } \Phi ( u + i k ) , \Phi ( u ) = \frac { B _ { 4 } ^ { ( + ) + } R _ { 4 } ^ { ( - ) - } } { B _ { 4 } ^ { ( - ) - } R _ { 4 } ^ { ( + ) + } } S _ { 4 } ^ { 2 } \left( \prod _ { j = 1 } ^ { K _ { 4 } } \frac { x _ { 4 , j } ^ { + } } { x _ { 4 , j } ^ { - } } \right) .
$$

Finally, the leading wrapping corrections at weak coupling is

$$
\delta { \cal E } ^ { \mathrm { L O } } \simeq - \sum _ { a = 1 } ^ { \infty } \int { \frac { d u } { \pi } } Y _ { a , 0 } ^ { \mathrm { m i r } } ( u ) .
$$

To compute the leading wrapping effect, in eq. (5.5) all we need is to find the large-volume asymptotics of $Y _ { a , 0 }$ functions evaluated in mirror dynamics. Here we give some useful formulas: Dispersion

The universal factor $( x ^ { [ - a ] } / x ^ { [ + a ] } ) ^ { L }$ , which is also called kinematic factor in literature, evaluated in the mirror dynamics is

$$
\left[ \frac { 4 h ^ { 2 } ( \lambda ) } { a ^ { 2 } + 4 u ^ { 2 } } \right] ^ { L } .
$$

Twisted Ta,s

After some computations, one find the following compact formula for ${ T _ { a , 1 } } ^ { 6 }$ （204号

$$
T _ { a , 1 } ^ { \mathrm { m i r } } \simeq 4 \sin ^ { 2 } \frac { \pi ( \delta _ { 1 } - \delta _ { 3 } ) L } { 2 } ( - 1 ) ^ { a } \sum _ { \stackrel { p = - a + 1 } { \Delta p = 2 } } ^ { a - 1 } \left( \frac { Q _ { 4 } ^ { [ p ] } } { Q _ { 4 } ^ { [ 1 - a ] } } \right) ^ { 2 } .
$$

To compute the fused scalar factor,one should be careful on the dressng phase, which is evaluated in the mirror-physical kinematics and has diferent weak coupling expansion from the physical-physical kinematics [70]. Taking this into account, we find7

$$
\Phi _ { a } ^ { \mathrm { m i r } } \simeq \left[ Q _ { 4 } ^ { + } ( 0 ) \right] ^ { 2 } \frac { Q _ { 4 } ^ { [ 1 - a ] } } { Q _ { 4 } ^ { [ - 1 - a ] } Q _ { 4 } ^ { [ a - 1 ] } Q _ { 4 } ^ { [ a + 1 ] } } .
$$

The asymptotic Bethe equations for states in the $s l ( 2 )$ sector(with twist $L$ and excitations $N$ ） read

$$
\left( \frac { x _ { k } ^ { + } } { x _ { k } ^ { - } } \right) ^ { L } = - \prod _ { j \neq k } ^ { N } \frac { u _ { k } - u _ { j } + i } { u _ { k } - u _ { j } - i } \left( \frac { x _ { k } ^ { - } - x _ { j } ^ { + } } { x _ { k } ^ { + } - x _ { j } ^ { - } } \right) ^ { 2 } \sigma _ { B E S } ^ { 2 } ,
$$

where we denote $u _ { 4 , j } ( = u _ { \bar { 4 } , j } )$ as $u _ { j }$ . Anomalous dimensions of twist operators will be expanded in power of $h ( \lambda )$ as

$$
\Delta _ { L , N } = L + N + \sum _ { l \geq 1 } \gamma _ { L , N } ^ { ( l ) } h ^ { l } ( \lambda ) .
$$

# 5.1 Two-loop wrapping corrections to twist-1 operators

The twist-1 operators in ABJM theory have also been discussed in [71,72,39]. In the undeformed ABJM theory, wrapping corrections appear at four-loop. But in our case, the wrapping effct appears at two-loop. The leading order Bethe ansatz equations are

$$
{ \frac { u _ { k } + { \frac { i } { 2 } } } { u _ { k } - { \frac { i } { 2 } } } } = - \prod _ { j \neq k } ^ { N } { \frac { u _ { k } - u _ { j } - i } { u _ { k } - u _ { j } + i } } , \qquad k , j = 1 , \dots , N
$$

It can be written in the very efficient Baxter function formalism

$$
\left( u + \frac { i } { 2 } \right) Q ( u + i ) - \left( u - \frac { i } { 2 } \right) Q ( u - i ) = i ( 2 N + 1 ) Q ( u ) ,
$$

where $Q ( u )$ is the Baxter polynomial

$$
Q ( u ) = \mathcal { N } \prod _ { k = 1 } ^ { N } ( u - u _ { k } ) .
$$

The solution of the Baxter equation (5.11) is [71, 72, 39]

$$
Q ( u ) = { } _ { 2 } F _ { 1 } \left( \begin{array} { c } { { - N , i u + \frac 1 2 } } \\ { { 1 } } \end{array} ; 2 \right) .
$$

Inserting it in the Y-system equations for wrapping effects,we obtain the simple result

$$
\delta E ^ { \mathrm { L O } } = ( - 1 ) ^ { N } \frac { 4 } { 2 N + 1 } h ^ { 2 } ( \lambda ) \sin ^ { 2 } \frac { \pi ( \delta _ { 1 } - \delta _ { 3 } ) } { 2 } .
$$

# 5.2 Four-loop wrapping corrections to twist-2 operators

After some manipulation, it turns out that the two loop Bethe equations for twist-2 operators is equivalent to the following leading order Baxter equation [71, 72, 39]

$$
\left( u + \frac { i } { 2 } \right) ^ { 2 } Q ( u + i ) - \left( u - \frac { i } { 2 } \right) ^ { 2 } Q ( u - i ) = i ( 2 N + 2 ) u Q ( u ) ,
$$

and its solution is known for even $N$ [72,39]

$$
Q ( u ) = { _ 3 F _ { 2 } } \left( \begin{array} { c c } { { - \frac { N } { 2 } , i u + \frac { 1 } { 2 } , - i u + \frac { 1 } { 2 } } } & { { _ { ; } } } \\ { { 1 , } } & { { 1 } } \end{array} ; 1 \right) .
$$

The leading wrapping correction appears at four loops.

$$
\delta E ^ { \mathrm { L O } } = 4 \sin ^ { 2 } ( \pi ( \delta _ { 1 } - \delta _ { 3 } ) ) \gamma _ { 2 , N } ^ { ( 4 ) } h ^ { 4 } ( \lambda ) .
$$

The Y-system provides the following result for the first 1O values

Howevera closed formula hasnot been found.

As it is evident in eq. (5.18), for $\delta _ { 1 } = \delta _ { 3 }$ but not necessarily zero (and $\delta _ { 2 } = 0$ as we are in the $s l ( 2 )$ like sector),the four-loop wrapping corrections due to deformation disappear for twist-2 operators. A similar discussion is also suitable for twist-1 operators.

# 6 $\beta$ -deformation

$\beta$ -deformation of ABJM theory corresponds to choose the three parameters as $( 0 , \delta _ { 2 } , 0 )$ ，and $2 \delta _ { 2 } =$ $- \gamma _ { 3 } \equiv \beta , \gamma _ { 1 } = \gamma _ { 2 } = 0$ . As discussed in [41], in this case the theory preserves ${ \mathcal N } = 2$ supersymmetry.

In this case,due to the fact that the phases in the scalar factor do not vanish,the two black node Y-functions are different. The leading wrapping corrections are expressed by

$$
\delta E ^ { \mathrm { L O } } \simeq - \sum _ { a = 1 } ^ { \infty } \int _ { - \infty } ^ { \infty } \frac { d u } { 2 \pi } ( Y _ { \bullet _ { a } } ^ { \mathrm { m i r } } + Y _ { \bullet _ { a } } ^ { \mathrm { m i r } } ) \ .
$$

# 6.1 One-particle state

In this section, we will discuss the leading wrapping of a single magnon state in $\beta$ -deformed theory. We consider the state with only one type-4 excitation $K _ { 4 } = 1$ . The unique momentum carrying root （204 $u _ { 4 }$ must satisfy the following Bethe equation and cyclicity condition

$$
\left( { \frac { x _ { 4 } ^ { + } } { x _ { 4 } ^ { - } } } \right) ^ { L } = e ^ { - \pi i L \beta } , \qquad { \frac { x _ { 4 } ^ { + } } { x _ { 4 } ^ { - } } } = e ^ { - \pi i \beta } .
$$

A solution is easily obtained

$$
u _ { 4 } = - \frac { 1 } { 2 } \cot ( \frac { \pi \beta } { 2 } ) - 2 \sin ( \pi \beta ) h ^ { 2 } ( \lambda ) + \cdot \cdot \cdot .
$$

The twisted generating functional reads

$$
\begin{array} { l } { { \displaystyle \sum _ { a = 0 } ^ { \infty } ( - 1 ) ^ { a } T _ { a , 1 } ^ { [ 1 - a ] } D ^ { a } = } } \\ { { \displaystyle \sum _ { 1 - e ^ { i \pi \beta / 2 } D ) ^ { - 1 } \left( 1 - e ^ { - i \pi \beta / 2 } \frac { R _ { 4 } ^ { ( + ) - } } { R _ { 4 } ^ { ( - ) - } } D \right) \left( 1 - e ^ { i \pi \beta / 2 } \frac { R _ { 4 } ^ { ( + ) - } } { R _ { 4 } ^ { ( - ) - } } D \right) \left( 1 - e ^ { - i \pi \beta / 2 } \frac { B _ { 4 } ^ { ( + ) + } } { B _ { 4 } ^ { ( - ) + } R _ { 4 } ^ { ( - ) - } } D \right) } } } \end{array}
$$

After some manipulations,we find the formula

$$
T _ { a , 1 } ^ { \mathrm { m i r } } \simeq ( - 1 ) ^ { a } \frac { 1 6 h ^ { 2 } e ^ { i \pi ( a + 1 ) \beta / 2 } a ( a ^ { 2 } + 4 u ^ { 2 } - \csc ^ { 2 } ( \pi \beta / 2 ) ) \sin ^ { 3 } ( \pi \beta / 2 ) } { ( a ^ { 2 } + 4 u ^ { 2 } ) ( i - i a + \cot ( \pi \beta / 2 ) + 2 u ) } .
$$

In this case $\tau _ { 0 } = e ^ { - \pi i ( 2 L + 1 ) \beta / 2 } , \tau _ { 0 } = e ^ { \pi i ( 2 L - 1 ) \beta / 2 }$ , and working carefully with these phases we find

$$
\begin{array} { r l } & { \Phi _ { \pm a } ^ { \mathrm { m i r } } \simeq \left\{ \begin{array} { l l } { \frac { e ^ { - i \pi ( a + 1 ) \beta / 2 } ( i - i a + \cot ( \pi \beta / 2 ) + 2 u ) } { \sin ( \pi \beta / 2 ) ( - i a - i + \cot ( \pi \beta / 2 ) + 2 u ) ( i a + i + \cot ( \pi \beta / 2 ) + 2 u ) } } & { a \mathrm { ~ i s ~ e v e n , } } \\ { \frac { e ^ { - i \pi \beta ( a + 2 L + 1 ) / 2 } ( i - i a + \cot ( \pi \beta / 2 ) + 2 u ) } { \sin ( \pi \beta / 2 ) ( - i a - i + \cot ( \pi \beta / 2 ) + 2 u ) ( i a - i + \cot ( \pi \beta / 2 ) + 2 u ) } } & { a \mathrm { ~ i s ~ o d d . } } \end{array} \right. } \\ & { \Phi _ { \pm a } ^ { \mathrm { m i r } } \simeq \left\{ \begin{array} { l l } { \frac { e ^ { - i \pi ( a + 1 ) \beta / 2 } } { \sin ( \pi \beta / 2 ) ( i a - i + \cot ( \pi \beta / 2 ) + 2 u ) } } & { a \mathrm { ~ i s ~ e v e n , } } \\ { \frac { e ^ { - i \pi ( a + 1 ) \beta / 2 } } { \sin ( \pi \beta / 2 ) ( i a - i + \cot ( \pi \beta / 2 ) + 2 u ) } } & { a \mathrm { ~ i s ~ o d d . } } \end{array} \right. } \end{array}
$$

Despite the annoying phases appearing in the T-functions and the fused scalar factors, the sums of the gauge invariant Y-functions are real when the two black nodes are combined. Their structures are totally different for $a$ even or odd. When $a$ is an even number

$$
\frac { 2 L + 2 } { 2 } 2 ^ { 2 L + 6 } a ( a ^ { 2 } + 4 u ^ { 2 } - \csc ^ { 2 } ( \pi \beta / 2 ) ) \sin ^ { 4 } ( \pi \beta / 2 )  { ( a ^ { 2 } + 4 u ^ { 2 } ) ^ { L + 1 } } \frac { 2 + a ^ { 2 } + 4 u ^ { 2 } - ( a ^ { 2 } + 4 u ^ { 2 } ) \cos ( \pi \beta ) + 4 u \sin ( \pi \beta / 2 ) } { y _ { a } y _ { - a } } .
$$

and for odd

$$
\begin{array} { r l } & { \mathrm { ~ a ~ r o r ~ o u t ~ } a } \\ & { Y _ { \bullet _ { a } } ^ { \operatorname* { m i r } } + Y _ { \bullet _ { a } } ^ { \operatorname* { m i r } } \simeq \frac { - h ^ { 2 L + 2 } 2 ^ { 2 L + 7 } a \left( a ^ { 2 } + 4 u ^ { 2 } - \csc ^ { 2 } ( \pi \beta / 2 ) \right) \sin ^ { 4 } \left( \pi \beta / 2 \right) } { ( a ^ { 2 } + 4 u ^ { 2 } ) ^ { L + 1 } } \times } \end{array}
$$

$$
\frac { ( ( a ^ { 2 } + 4 u ^ { 2 } ) \sin ^ { 2 } ( \pi \beta / 2 ) + \cos ( \pi \beta ) + 2 u \sin ( \pi \beta ) ) \cos ( \pi L \beta ) + ( 2 - 2 u \cos ( \pi \beta ) + \sin ( \pi \beta ) ) \sin ( \pi L \beta ) + \cos ( \pi L \beta ) \sin ( \pi L \beta ) } { y _ { a } y _ { - a } } .
$$

where

$$
y _ { a } = 2 + a ^ { 2 } + 2 a + 4 u ^ { 2 } - ( a ^ { 2 } + 2 a + 4 u ^ { 2 } ) \cos ( \pi \beta ) + 4 u \sin ( \pi \beta ) .
$$

If we take $\beta = 1$ ， these expressions simplify considerably. The summation cannot be done directly, because the even term and the odd term have different expressions. However，since the series is absolutely convergent, we can add the even term and odd term separately. Plugging eqs. (6.8),(6.9) and (6.10) into eq. (6.1) and summing the even and odd terms together, we get the following leading wrapping corrections at h2L+2.

$$
\begin{array} { r l } & { \delta E _ { L = 1 } ^ { \beta = 1 } / h ^ { 4 } = - 8 \zeta _ { 2 } , } \\ & { \delta E _ { L = 2 } ^ { \beta = 1 } / h ^ { 6 } = - 1 6 ( 2 \zeta _ { 2 } - 3 \zeta _ { 4 } ) , } \\ & { \delta E _ { L = 3 } ^ { \beta = 1 } / h ^ { 8 } = 1 3 6 \zeta _ { 4 } - 1 5 5 \zeta _ { 6 } , } \\ & { \delta E _ { L = 4 } ^ { \beta = 1 } / h ^ { 1 0 } = - 4 ( 5 6 \zeta _ { 4 } + 7 5 \zeta _ { 6 } - 1 4 0 \zeta _ { 8 } ) . } \end{array}
$$

In the computations above,we found all the odd powers of $\pi$ are canceled out.

# 6.2 A simple case of two particle state

In this subsection,we compute the wrapping effect for the operator with $L = K _ { 4 } = K _ { \bar { 4 } } = 1$ and other $K$ 's being zero.At lowest order,the $\beta$ -deformed Bethe equations read

$$
\begin{array} { r } { \frac { u _ { 4 } + \frac { i } { 2 } } { u _ { 4 } - \frac { i } { 2 } } = e ^ { - \pi i \beta } \frac { u _ { 4 } - u _ { \bar { 4 } } - i } { u _ { 4 } - u _ { \bar { 4 } } + i } , } \\ { \frac { u _ { \bar { 4 } } + \frac { i } { 2 } } { u _ { \bar { 4 } } - \frac { i } { 2 } } = e ^ { \pi i \beta } \frac { u _ { \bar { 4 } } - u _ { 4 } - i } { u _ { \bar { 4 } } - u _ { 4 } + i } , } \end{array}
$$

and the momentum conservation equation is not deformed

$$
\frac { u _ { 4 } + \frac { i } { 2 } } { u _ { 4 } - \frac { i } { 2 } } \frac { u _ { \bar { 4 } } + \frac { i } { 2 } } { u _ { \bar { 4 } } - \frac { i } { 2 } } = 1 .
$$

Their root is easily found to be $u _ { 4 } = \Delta , u _ { \bar { 4 } } = - \Delta$ with $\begin{array} { r } { \Delta \ = \ \frac { 1 } { 2 } \tan { \frac { \pi \beta } { 4 } } ^ { 8 } } \end{array}$ . In this case, we have two kinds of Baxter polynomial. $Q _ { 4 } ( u ) = u - \Delta , Q _ { \bar { 4 } } ( u ) = u + \Delta$ and define $Q = Q _ { 4 } Q _ { \bar { 4 } }$ .Since $\tau _ { 1 } = \tau _ { 2 } = 1 , \tau _ { 0 } = e ^ { - \pi i \beta } , \tau _ { \bar { 0 } } = e ^ { \pi i \beta }$ , the deformation does not appear in the $T$ functions. It onlyaffects the fused scalar factors.

$$
\begin{array} { r l } & { \Phi _ { \Phi _ { a } } ^ { \operatorname* { m i r } } \simeq \left\{ \begin{array} { l l } { \frac { Q _ { 4 } ^ { + } ( 0 ) Q _ { 4 } ^ { + } ( 0 ) Q _ { 4 } ^ { [ 1 - a ] } } { Q _ { 4 } ^ { [ a + 1 ] } Q _ { 4 } ^ { [ - a - 1 ] } Q _ { 4 } ^ { [ a - 1 ] } } \qquad \ \mathrm { ~ a ~ i s ~ e v e n } , } \\ { \frac { [ Q _ { 4 } ^ { + } ( 0 ) ] ^ { 3 } Q _ { 4 } ^ { [ 1 - a ] } } { Q _ { 4 } ^ { + } ( 0 ) Q _ { 4 } ^ { [ a - 1 ] } Q _ { 4 } ^ { [ - a - 1 ] } Q _ { 4 } ^ { [ a + 1 ] } } \ \qquad \mathrm { ~ a ~ i s ~ o d d } . } \end{array} \right. } \\ & { \Phi _ { \Phi _ { a } ^ { \operatorname* { m i r } } } ^ { \operatorname* { m i r } } \simeq \left\{ \begin{array} { l l } { \frac { Q _ { 4 } ^ { + } ( 0 ) Q _ { 4 } ^ { + } ( 0 ) Q _ { 4 } ^ { [ 1 - a ] } } { Q _ { 4 } ^ { [ a + 1 ] } Q _ { 4 } ^ { [ - a - 1 ] } Q _ { 4 } ^ { [ a - 1 ] } } \qquad \ \mathrm { ~ a ~ i s ~ e v e n } , } \\ { \frac { [ Q _ { 4 } ^ { [ 1 + a ] } ( 0 ) ] ^ { 3 } Q _ { 4 } ^ { [ 1 - a ] } } { Q _ { 4 } ^ { [ 1 ] } Q _ { 4 } ^ { [ 1 - a ] } Q _ { 4 } ^ { [ 1 - a ] } Q _ { 4 } ^ { [ 1 - a ] } } \qquad \ \mathrm { ~ a ~ i s ~ o d d } . } \end{array} \right. } \end{array}
$$

The $T$ -functions are the same as the ones in the undeformed theory

$$
T _ { a , 1 } ^ { \mathrm { m i r } } \simeq i c h ^ { 2 } ( \lambda ) \frac { ( - 1 ) ^ { a + 1 } } { Q ^ { [ 1 - a ] } } \sum _ { p = - a } ^ { a } \frac { Q ^ { [ - 1 - p ] } - Q ^ { [ 1 - p ] } } { u - \frac { i } { 2 } p } \Bigg | _ { Q ^ { [ - a - 1 ] } , Q ^ { [ a + 1 ] }  0 } ,
$$

where

$$
c = i ( \log Q ) ^ { \prime } | _ { u = - i / 2 } ^ { u = i / 2 } .
$$

For an even a

$$
\begin{array} { r l r } {  { \sum _ { \pm _ { a } } ^ { \mathrm { m i r } } + Y _ { \pm _ { a } } ^ { \mathrm { m i r } } \simeq \frac { 2 5 6 h ^ { 4 } a ( a ^ { 2 } - 4 \Delta ^ { 2 } + 4 u ^ { 2 } - 1 ) } { ( a ^ { 2 } + 4 u ^ { 2 } ) ^ { 2 } } \times } } \\ & { } & \\ & { } & { \times \frac { ( a ^ { 4 } + 8 a ^ { 2 } \Delta ^ { 2 } + 8 a ^ { 2 } u ^ { 2 } - 2 a ^ { 2 } + ( 4 \Delta ^ { 2 } + 1 ) ^ { 2 } + 1 6 u ^ { 4 } - 3 2 \Delta ^ { 2 } u ^ { 2 } + 8 u ^ { 2 } ) } { \tilde { u } _ { * } \tilde { u } _ { * } } , } \end{array}
$$

and for an odd $a$

$$
Y _ { \pm _ { a } } ^ { \mathrm { m i r } } + Y _ { \pm _ { a } } ^ { \mathrm { m i r } } \simeq \frac { - 2 5 6 h ^ { 4 } a ( a ^ { 2 } - 4 \Delta ^ { 2 } + 4 u ^ { 2 } - 1 ) } { ( a ^ { 2 } + 4 u ^ { 2 } ) ^ { 2 } ( 1 + 4 \Delta ^ { 2 } ) ^ { 2 } } \frac { \mathrm { n u m } } { \tilde { y } _ { a } \tilde { y } _ { - a } } ,
$$

where the numerator is

$$
\begin{array} { r l } & { \mathrm { n u m } = 1 6 a ^ { 4 } \Delta ^ { 4 } - 2 4 a ^ { 4 } \Delta ^ { 2 } + a ^ { 4 } + 1 2 8 a ^ { 2 } \Delta ^ { 6 } + 3 2 a ^ { 2 } \Delta ^ { 4 } - 8 a ^ { 2 } \Delta ^ { 2 } } \\ & { + 1 2 8 a ^ { 2 } \Delta ^ { 4 } u ^ { 2 } - 1 9 2 a ^ { 2 } \Delta ^ { 2 } u ^ { 2 } + 8 a ^ { 2 } u ^ { 2 } - 2 a ^ { 2 } + 2 5 6 \Delta ^ { 8 } + 2 5 6 \Delta ^ { 6 } + 9 6 \Delta ^ { 4 } + 1 6 \Delta ^ { 2 } } \\ & { + 2 5 6 \Delta ^ { 4 } u ^ { 4 } - 3 8 4 \Delta ^ { 2 } u ^ { 4 } + 1 6 u ^ { 4 } - 5 1 2 \Delta ^ { 6 } u ^ { 2 } - 1 2 8 \Delta ^ { 4 } u ^ { 2 } + 3 2 \Delta ^ { 2 } u ^ { 2 } + 8 u ^ { 2 } + 1 , } \end{array}
$$

and

$$
\tilde { y } _ { a } = a ^ { 4 } + 4 a ^ { 3 } + 8 a ^ { 2 } \Delta ^ { 2 } + 8 a ^ { 2 } u ^ { 2 } + 6 a ^ { 2 } + 1 6 a \Delta ^ { 2 } + 1 6 a u ^ { 2 } + 4 a + 1 6 \Delta ^ { 4 } + 8 \Delta ^ { 2 } + 1 6 u ^ { 4 } - 3 2 \Delta ^ { 2 } u ^ { 2 } + 8 u ^ { 2 } + 1 9 \Delta ^ { 4 } u ^ { 3 }
$$

Plugging eq.(6.18) and eq.(6.19) into the formula for the energy correction eq. (6.1), integrating on $u$ （204号 and summing the results,we find

$$
\delta E ^ { \mathrm { L O } } = \frac { 8 h ^ { 4 } ( \lambda ) ( 1 2 - \pi ^ { 2 } ( 1 + 4 \Delta ^ { 2 } ) ) } { 3 ( 1 + 4 \Delta ^ { 2 } ) ^ { 2 } } .
$$

Taking the deformation parameter $\beta \to 0$ ，which means $\Delta  0$ ,we get that,

$$
\delta E ^ { \mathrm { L O } } = h ^ { 4 } ( \lambda ) ( 3 2 - 1 6 \zeta ( 2 ) ) .
$$

This result is the same as one for the operator with $L = 2 , \tilde { K } _ { 4 } = \tilde { K } _ { \bar { 4 } } = 1 , \eta = 1$ in the undeformed ABJM theory [13, 62] (this operator is in the irreducible representation 20 of $S U ( 4 )$ ).In fact,this operator and the operator we started with are linked by two steps. First we add to the $L = 2 , \tilde { K } _ { 4 } =$ ${ \tilde { K } } _ { \bar { 4 } } = 1$ operator an $u _ { 3 }$ root at zero in the $s u ( 2 )$ grading and change $L$ from $L = 2$ to $L = 1$ [71]. Then we perform the fermionic duality to describe the operator with $L = K _ { 4 } = K _ { \bar { 4 } } = 1$ in the $s l ( 2 )$ grading (notice here we are in the undeformed theory, so ${ \cal K } _ { 3 } = \tilde { \cal K } _ { 4 } + \tilde { \cal K } _ { \bar { 4 } } - \tilde { \cal K } _ { 3 } - 1 = 0 ,$ ）

# 7 Conclusions

In this paper we have assumed the integrability of planar $\gamma$ -deformed ABJM theory at all loop order based on the algebraic Bethe ansatz at two loop in the planar scalar sector,and proposed the asymptotic Bethe ansatz equations via a similar treatment in $\gamma$ -deformed $\mathcal { N } = 4$ SYM [26]. Duality properties of the twist charges have been investigated, which are essential for the twisted Bethe equations. Utilising the Y-system techniques,we compute the leading wrapping corrections for various operators. Some important results of $\beta$ -deformed theory are obtained,which should be checked through a direct Feynman diagram computation as in [73, 74] for $\beta$ -deformed SYM. There are strong evidence that planar ABJtheory [75] is integrable as well[76,77],[61]-[63].As suggested in [78],then the results obtained in this paper on wrapping corrections are also valid for the same quantities in $\gamma$ -deformed ABJ theory once having replaced $h ( \lambda )$ by the function $h ( \lambda _ { 1 } , \lambda _ { 2 } )$ given in [78]． It will be also interesting to find the S-matrix of the spin chain for $\gamma$ -deformed ABJM theory based on the studies in [79]-[81] and to study the integrability of IIA string theory on $A d S _ { 4 } \times C P _ { \gamma } ^ { 3 }$ on the basis of [7]-[9],[82, 83].

# Acknowledgments

It is our great pleasure to thank C. Ahn, Z. Chang, F. Levkovich-Maslyuk, J. Plefka and Z.-Y. Xian for very helpful discussions. We would like to express our special thanks to the anonymous referee for valuable suggestions to improve the paper. HHC and JW thank Institute of Modern Physics, Northwest University for warm hospitality during the 9th Summer School in Theoretical Physics on Integrable Models and their Applications. This work was in part supported by Natural Science Foundation of China under Grant Nos. 11575202(HHC,JW),11275207(HHC),11275208(PL),11575195(PL), 11690022(HHC).JW would also like to thank the participants of the advanced workshop“Dark Energy and Fundamental Theory” supported by the Special Fund for Theoretical Physics from NSFC with Grant No.114476l3 for stimulating discussion. JW also gratefully acknowledges the support of K. C. Wong Education Foundation.

# AAlgebraic Bethe Ansatz

The proof of integrability of planar $\gamma$ -deformed ABJM theory in the scalar sector at two loop level is almost the same as the one for $\beta$ -deformed theory in [40],the only difference is that now we need to use the star product defined in eq. (2.1). So here we only list the Hamiltonian from the Feynman diagram computations,

$$
\widetilde { H } \ = \ \lambda ^ { 2 } \sum _ { i = 1 } ^ { 2 L } \left( \mathbb { I } - \widetilde { \mathbb { P } } _ { i , i + 2 } + \frac { 1 } { 2 } \mathbb { P } _ { i , i + 2 } \mathbb { K } _ { i , i + 1 } + \frac { 1 } { 2 } \mathbb { P } _ { i , i + 2 } \mathbb { K } _ { i + 1 , i + 2 } \right) ,
$$

where

$$
\begin{array} { l c l } { { \left( \widetilde { \mathbb { P } } _ { i , i + 2 } \right) _ { J _ { i } J _ { i + 1 } J _ { i + 2 } } ^ { I _ { i } I _ { i + 1 } I _ { i + 2 } } } } & { { \equiv } } & { { \exp ( - 2 \pi i ( Q _ { Y ^ { J _ { i } } } \times Q _ { Y ^ { J _ { i + 1 } } } + Q _ { Y ^ { J _ { i + 1 } } } \times Q _ { Y ^ { J _ { i + 2 } } } + Q _ { Y ^ { J _ { i + 2 } } } \times Q _ { Y ^ { J _ { i } } } ) ) } } \\ { { } } & { { \times } } & { { ( \mathbb { P } _ { i , i + 2 } ) _ { J _ { i } J _ { i + 1 } J _ { i + 2 } } ^ { I _ { i } I _ { i + 1 } I _ { i + 2 } } , } } \end{array}
$$

and the $\mathrm { R }$ matrices,

$$
\begin{array} { r c l } { { \widehat { \Re ^ { 4 4 } } ( u ) _ { K L } ^ { I J } } } & { { = } } & { { f _ { K L } ^ { I J } ( u \mathbb { I } + \mathbb { P } ) _ { K L } ^ { I J } , } } \\ { { \widehat { \Re ^ { 4 4 } } ( u ) _ { K L } ^ { I J } } } & { { = } } & { { ( f _ { K L } ^ { I J } ) ^ { - 1 } ( - ( u + 2 ) \mathbb { I } + \mathbb { K } ) _ { K L } ^ { I J } , } } \\ { { \widehat { \Re ^ { 4 4 } } ( u ) _ { K L } ^ { I J } } } & { { = } } & { { ( f _ { K L } ^ { I J } ) ^ { - 1 } ( - ( u + 2 ) \mathbb { I } + \mathbb { K } ) _ { K L } ^ { I J } , } } \\ { { \widehat { \Re ^ { 4 4 } } ( u ) _ { K L } ^ { I J } } } & { { = } } & { { f _ { K L } ^ { I J } ( u \mathbb { I } + \mathbb { P } ) _ { K L } ^ { I J } , } } \end{array}
$$

and the definition of $f _ { K L } ^ { I J }$ is

$$
f _ { K L } ^ { I J } = \exp ( i \pi ( Q _ { Y ^ { J } } \times Q _ { Y ^ { I } } - Q _ { Y ^ { K } } \times Q _ { Y ^ { L } } ) ) .
$$

The obtained Bethe ansatz equations are

$$
\exp \Big ( 2 \pi i \tilde { Q } \times ( Q _ { Y ^ { 1 } } - Q _ { Y ^ { 2 } } ) \Big ) \left( \frac { u _ { 4 , k } + \frac { i } { 2 } } { u _ { 4 , k } - \frac { i } { 2 } } \right) ^ { L } = \prod _ { j = 1 } ^ { K _ { 4 } } \frac { u _ { 4 , k } - u _ { 4 , j } + i } { u _ { 4 , k } - u _ { 4 , j } - i } \prod _ { j = 1 } ^ { K _ { 3 } } \frac { u _ { 4 , k } - u _ { 3 , j } - \frac { i } { 2 } } { u _ { 4 , k } - u _ { 3 , j } + \frac { i } { 2 } } ,
$$

$$
\exp \Big ( 2 \pi i \tilde { Q } \times ( Q _ { Y ^ { 2 } } - Q _ { Y ^ { 3 } } ) \Big ) = \prod _ { j = 1 } ^ { K _ { 4 } } \frac { u _ { 3 , k } - u _ { 4 , j } - \frac { i } { 2 } } { u _ { 3 , k } - u _ { 4 , j } + \frac { i } { 2 } } \prod _ { j = 1 } ^ { K _ { 4 } } \frac { u _ { 3 , k } - u _ { 4 , j } - \frac { i } { 2 } } { u _ { 3 , k } - u _ { 4 , j } + \frac { i } { 2 } } \prod _ { j = 1 } ^ { K _ { 3 } } \frac { u _ { 3 , k } - u _ { 3 , j } + i } { u _ { 3 , k } - u _ { 4 , j } - i } ,
$$

$$
\exp \left( 2 \pi i \tilde { Q } \times ( Q _ { Y ^ { 3 } } - Q _ { Y ^ { 4 } } ) \right) \left( \frac { u _ { 4 , k } + \frac { i } { 2 } } { u _ { \bar { 4 } , k } - \frac { i } { 2 } } \right) ^ { L } = \prod _ { j = 1 } ^ { K _ { 4 } } \frac { u _ { \bar { 4 } , k } - u _ { \bar { 4 } , j } + i } { u _ { \bar { 4 } , k } - u _ { \bar { 4 } , j } - i } \prod _ { j = 1 } ^ { K _ { 3 } } \frac { u _ { \bar { 4 } , k } - u _ { 3 , j } - \frac { i } { 2 } } { u _ { \bar { 4 } , k } - u _ { 3 , j } + \frac { i } { 2 } } \ .
$$

Here we have defined

$$
{ \tilde { Q } } \equiv ( L - K _ { 4 } ) Q _ { Y ^ { 1 } } + ( K _ { 4 } - K _ { 3 } ) Q _ { Y ^ { 2 } } + ( K _ { 3 } - K _ { { \bar { 4 } } } ) Q _ { Y ^ { 3 } } + ( K _ { { \bar { 4 } } } - L ) Q _ { Y ^ { 4 } } .
$$

The zero momentum condition is

$$
\exp \Big ( 2 \pi i \tilde { Q } \times ( Q _ { Y ^ { 4 } } - Q _ { Y ^ { 1 } } ) \Big ) = \prod _ { j = 1 } ^ { K _ { 4 } } \frac { u _ { 4 , j } + \frac { i } { 2 } } { u _ { 4 , j } - \frac { i } { 2 } } \prod _ { j = 1 } ^ { K _ { \bar { 4 } } } \frac { u _ { \bar { 4 } , j } + \frac { i } { 2 } } { u _ { \bar { 4 } , j } - \frac { i } { 2 } } .
$$

These equations can be written as

$$
e ^ { 2 \pi i ( \mathbf { A K } ) _ { j } } \left( \frac { u _ { j , k } + \frac { i } { 2 } V _ { j } } { u _ { j , k } - \frac { i } { 2 } V _ { j } } \right) ^ { L } = \prod _ { j ^ { \prime } = 3 , 4 , 4 } \prod _ { k ^ { \prime } = 1 \atop ( j ^ { \prime } , k ^ { \prime } ) \neq ( j , k ) } ^ { K _ { j ^ { \prime } } } \frac { u _ { j , k } - u _ { j ^ { \prime } , k ^ { \prime } } + \frac { i } { 2 } M _ { j , j ^ { \prime } } } { u _ { j , k } - u _ { j ^ { \prime } , k ^ { \prime } } + \frac { i } { 2 } M _ { j , j ^ { \prime } } } ,
$$

with $j = 3 , 4 , 4$ and

$$
e ^ { 2 \pi i ( \mathbf { A K } ) _ { 0 } } = \prod _ { j = 3 , 4 , \bar { 4 } } \prod _ { k = 1 } ^ { K _ { j } } \frac { u _ { j , k } + \frac { i } { 2 } V _ { j } } { u _ { j , k } - \frac { i } { 2 } V _ { j } } .
$$

Here we used the Cartan matrix of $S O ( 6 )$ ，

$$
M _ { j j ^ { \prime } } = \left( \begin{array} { c c c } { { 2 } } & { { - 1 } } & { { - 1 } } \\ { { - 1 } } & { { 2 } } & { { 0 } } \\ { { - 1 } } & { { 0 } } & { { 2 } } \end{array} \right) ,
$$

and the Dynkin labels $V _ { j } = ( 0 , 1 , 1 )$ . Since we are studying the scalar sector at two-loop level, flipping the signs of $\gamma _ { 1 } , \gamma _ { 2 } , \gamma _ { 3 }$ simultaneously just maps the Hamiltonian to its transpose matrix. Then this will not change the eigenvalues of the Hamiltonian. So the result here is consistent with the one in the main part of this paper.

In fact,we can further use the $U ( 1 ) _ { b }$ symmetry of ABJM theory as the fourth $U ( 1 )$ symmetry and construct a six-parameter deformation with the $\mathbf { C }$ matrix being

$$
{ \bf C } = \left( \begin{array} { c c c c } { 0 } & { - \gamma _ { 3 } } & { + \gamma _ { 2 } } & { \alpha _ { 1 } } \\ { + \gamma _ { 3 } } & { 0 } & { - \gamma _ { 1 } } & { \alpha _ { 2 } } \\ { - \gamma _ { 2 } } & { + \gamma _ { 1 } } & { 0 } & { \alpha _ { 3 } } \\ { - \alpha _ { 1 } } & { - \alpha _ { 2 } } & { - \alpha _ { 3 } } & { 0 } \end{array} \right) .
$$

Now the charges are listed in table 2. Notice that if we choose $\gamma _ { 1 } = \gamma _ { 2 } = \alpha _ { 3 } = 0$ ， this will go back to the three-parameter deformation considered in [40]. Using the fact that the four scalars share the same fourth charge,it is not hard to find that $\alpha _ { 1 } , \alpha _ { 2 } , \alpha _ { 3 }$ will not enter the phase of the Hamiltonian (eq. (A.1)） in the scalar sector at two loop order.

# BThe $s u ( 2 )$ grading

In the appendix, we briefly discuss some relevant formulas in $s u ( 2 )$ grading. The twist matrix is

<html><body><table><tr><td rowspan="7">A=1</td><td>0</td><td>81-83 0</td><td>81-83</td><td>-δ1+2δ2+δ3</td><td>-δ1-282+δ3</td></tr><tr><td>83-81</td><td>0 0</td><td>8-81</td><td>2δ1</td><td>-283</td></tr><tr><td>0</td><td>0 0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>83-81</td><td>81-83 0</td><td>0</td><td>δ1+2δ2+δ3</td><td>-81-282-83</td></tr><tr><td>δ1-282-83 -201</td><td>0</td><td>-81-282-83</td><td>0</td><td>2δ1 + 4δ2+2δ3</td></tr><tr><td>δ1+282-83 283</td><td>0</td><td>81+282+δ3</td><td>-281-482-283</td><td>0</td></tr></table></body></html>

Table 2: Charges of fields under four $U ( 1 )$ generators.   

<html><body><table><tr><td>Fields</td><td>Y1</td><td>Y2</td><td>Y3</td><td>Y4</td><td>t1</td><td>12</td><td>t3</td><td>t4</td></tr><tr><td>Qf</td><td>1-2</td><td>1 2</td><td>0</td><td>0</td><td>1-2</td><td></td><td>0</td><td>0</td></tr><tr><td>Q²</td><td>0</td><td>0</td><td>1-2</td><td>2</td><td>0</td><td>0</td><td>1-2</td><td>1-2</td></tr><tr><td>Q</td><td>1-2</td><td>1-2</td><td>-2 2</td><td>一</td><td>1-2</td><td>1-2</td><td>2</td><td>1 2</td></tr><tr><td>Q4</td><td>1-2</td><td>1-2</td><td>1-2</td><td>1-2</td><td>-</td><td>-</td><td>1-2</td><td>1-2</td></tr></table></body></html>

In this case, the twist matrix still have the form (2.13),but with the three different charges

$$
\begin{array} { r c l } { \mathbf { q } _ { 1 } } & { = } & { ( 0 | - 1 , 0 , - 1 , 1 , 1 ) , } \\ { \mathbf { q } _ { 2 } } & { = } & { ( 1 | 0 , 0 , 1 , - 2 , 0 ) , } \\ { \mathbf { q } _ { 3 } } & { = } & { ( 1 | 0 , 0 , 1 , 0 , - 2 ) . } \end{array}
$$

Here we propose the following twisted generating functional

$$
{ \ L } _ { s u ( 2 ) } = \frac { 1 } { 1 - \frac { 1 } { \tilde { \tau } _ { 1 } } \frac { B ^ { ( - ) } - Q _ { 1 } ^ { + } R ^ { ( - ) + } } { B ^ { ( + ) } - Q _ { 1 } ^ { - } R ^ { ( - ) - } } D } \left( 1 - \frac { 1 } { \tilde { \tau } _ { 2 } } \frac { Q _ { 1 } ^ { + } Q _ { 2 } ^ { -- } R ^ { ( - ) + } } { Q _ { 1 } ^ { - } Q _ { 2 } R ^ { ( + ) + } } D \right) \left( 1 - \tilde { \tau } _ { 2 } \frac { Q _ { 2 } ^ { + + } Q _ { 3 } ^ { - } R ^ { ( - ) + } } { Q _ { 2 } Q _ { 3 } ^ { + } R ^ { ( + ) + } } D \right) \frac { 1 } { 1 - \tilde { \tau } _ { 1 } \frac { Q _ { 2 } ^ { + } R ^ { ( - ) + } } { Q _ { 1 } ^ { - } Q _ { 2 } ^ { - } R ^ { ( + ) + } } D } \ ,
$$

The cancellation of potential poles in the $T _ { a , s }$ functions gives the following Bethe equations

$$
1 = \frac { \tilde { \tau } _ { 2 } } { \tilde { \tau } _ { 1 } } \frac { Q _ { 2 } ^ { + } B ^ { ( - ) } } { Q _ { 2 } ^ { - } B ^ { ( + ) } } \bigg | _ { u = u _ { 1 , k } } , ~ - 1 = \frac { 1 } { ( \tilde { \tau } _ { 2 } ) ^ { 2 } } \frac { Q _ { 1 } ^ { + } Q _ { 2 } ^ { -- } Q _ { 3 } ^ { + } } { Q _ { 1 } ^ { - } Q _ { 2 } ^ { + + } Q _ { 3 } ^ { - } } \bigg | _ { u = u _ { 2 , k } } , ~ 1 = \frac { \tilde { \tau } _ { 2 } } { \tilde { \tau } _ { 1 } } \frac { Q _ { 2 } ^ { + } R ^ { ( - ) } } { Q _ { 2 } ^ { - } R ^ { ( + ) } } \bigg | _ { u = u _ { 3 , k } } ~ .
$$

We choose

$$
\tilde { \tau } _ { 1 } = e ^ { - \pi i ( ( \delta _ { 3 } - \delta _ { 1 } ) L + ( \delta _ { 1 } - \delta _ { 3 } ) \tilde { K } _ { 1 } + ( \delta _ { 1 } + 2 \delta _ { 2 } + \delta _ { 3 } ) ( \tilde { K } _ { 4 } - \tilde { K } _ { \bar { 4 } } ) ) } , \quad \tilde { \tau } _ { 2 } = 1
$$

to match the Bethe equations for $u _ { 1 } , u _ { 2 } , u _ { 3 }$ in this grading. The scalar factors should behave as

$$
\tilde { \Phi } _ { 4 } ( u ) = \frac { Q _ { 4 } ^ { + + } B _ { 3 } ^ { + } B _ { 1 } ^ { - } } { Q _ { 4 } ^ { -- } B _ { 3 } ^ { - } B _ { 1 } ^ { + } } S \tilde { \tau } _ { 0 } , \qquad \tilde { \Phi } _ { \bar { 4 } } ( u ) = \frac { Q _ { \bar { 4 } } ^ { + + } B _ { 3 } ^ { + } B _ { 1 } ^ { - } } { Q _ { \bar { 4 } } ^ { -- } B _ { 3 } ^ { - } B _ { 1 } ^ { + } } S \tilde { \tau } _ { \bar { 0 } } ,
$$

where

$$
\begin{array} { r } { \mathrm { ~  ~ \xi ~ } _ { 0 } = e ^ { \pi i ( - 2 \delta _ { 2 } L - ( \delta _ { 1 } + \delta _ { 3 } ) \bar { K } _ { 1 } - ( \delta _ { 1 } + 2 \delta _ { 2 } + \delta _ { 3 } ) ( \bar { K } _ { 3 } - K _ { 4 } - K _ { 4 } ) ) } , \tilde { \tau } _ { 0 } = e ^ { \pi i ( 2 \delta _ { 2 } L + ( \delta _ { 1 } + \delta _ { 3 } ) \bar { K } _ { 1 } + ( \delta _ { 1 } + 2 \delta _ { 2 } + \delta _ { 3 } ) ( \bar { K } _ { 3 } - K _ { 4 } - K _ { 4 } ) ) } , } \end{array}
$$

# References

[1] J. M. Maldacena,“The Large N limit of superconformal field theories and supergravity,” Int. J. Theor. Phys.38,1113 (1999) [Adv. Theor.Math. Phys. 2, 231(1998)] doi:10.1023/A:1026654312961 [hep-th/9711200].   
[2] Babichenko,A., B. Stefaski, and Konstantin Zarembo.“Integrability and the AdS 3/CFT 2 correspondence.” Journal of High Energy Physics 2010.3 (2010): 1-45 [arXiv:0912.1723 [hep-th].   
[3] T. Klose,“Review of AdS/CFT Integrability, Chapter IV.3: N=6 Chern-Simons and Strings on AdS4xCP3,” Lett. Math. Phys. 99 (2012) 401 doi:10.1007/s11005-011-0520-y [arXiv:1012.3999 [hepth]].   
[4] O.Aharony, O. Bergman, D.L. Jaferis and J. Maldacena,“N=6 superconformal Chern-Simonsmatter theories，M2-branes and their gravity duals,” JHEP 0810, 091 (2008) doi:10.1088/1126- 6708/2008/10/091 [arXiv:0806.1218 [hep-th]].   
[5] J. A. Minahan and K. Zarembo,“The Bethe ansatz for superconformal Chern-Simons,” JHEP 0809 (2008) 040 doi:10.1088/1126-6708/2008/09/040 [arXiv:0806.3951 [hep-th].   
[6] D.Bak and S.J. Rey,“Integrable Spin Chain in Superconformal Chern-Simons Theory,” JHEP 0810,053 (2008) doi:10.1088/1126-6708/2008/10/053 [arXiv:0807.2063 [hep-th].   
[7] G. Arutyunov, S. Frolov,“Superstrings on $A d S _ { 4 } \times C P ^ { 3 }$ as a Coset Sigma-model,” JHEP 0809 (2008）129,[arXiv:0806.4940 [hep-th]].   
[8] B. Stefanski, jr, “Green-Schwarz action for Type IIA strings on $A d S _ { 4 } \times C P ^ { 3 }$ ,” Nucl. Phys. B808 (2009) 80-87,[arXiv:0806.4948 [hep-th].   
[9] D. Sorokin and L. Wulff,“Evidence for the classical integrability of the complete $A d S _ { 4 } \times C P ^ { 3 }$ superstring,” JHEP 1011,143 (2010),[arXiv:1009.3498 [hep-th].   
[10] N. Beisert and M. Staudacher， “Long-range $p s u ( 2 , 2 | 4 )$ Bethe Ansatze for gauge theory and strings,” Nucl. Phys.B 727 (2005) 1 doi:10.1016/j.nuclphysb.2005.06.038 [hep-th/0504190].   
[11] N. Beisert, B. Eden and M. Staudacher,“Transcendentality and Crossing,” J. Stat. Mech. 0701 (2007) P01021 doi:10.1088/1742-5468/2007/01/P01021 [hep-th/0610251].   
[12] N. Gromov and P. Vieira,“The alloop AdS4/CFT3 Bethe ansatz,” JHEP 0901, 016 (2009) doi:10.1088/1126-6708/2009/01/016 [arXiv:0807.0777 [hep-th]].   
[13] N. Gromov， V. Kazakov and P. Vieira， “Exact Spectrum of Anomalous Dimensions of Planar N=4 Supersymmetric Yang-Mills Theory,” Phys. Rev. Lett.103 (2009） 131601 doi:10.1103/PhysRevLett.103.131601 [arXiv:0901.3753 [hep-th].   
[14] D.Bombardeli， D. Fioravanti and R. Tateo，“Thermodynamic Bethe Ansatz for planar AdS/CFT: A Prop0sal,” J. Phys. A 42 (2009) 375401 doi:10.1088/1751-8113/42/37/375401 [arXiv:0902.3930 [hep-th].   
[15] G. Arutyunov and S.Frolov,“Thermodynamic Bethe Ansatz for the AdS(5)x S(5) Mirror Model," JHEP 0905 (2009) 068 doi:10.1088/1126-6708/2009/05/068 [arXiv:0903.0141 [hep-thl].   
[16] N.Gromov， V. Kazakov， S. Leurent and D. Volin， “Quantum Spectral Curve for Planar $\begin{array} { r l r } { \mathcal { N } } & { { } = } & { 4 } \end{array}$ Super-Yang-Mills Theory,” Phys. Rev. Lett. 112(2014） no.1， 011602 doi:10.1103/PhysRevLett.112.011602 [arXiv:1305.1939 [hep-th].   
[17] N. Gromov and F. Levkovich-Maslyuk,“Y-system, TBA and Quasi-Classical strings in AdS(4) x CP3,”JHEP 1006 (2010) 088 doi:10.1007/JHEP06(2010)088 [arXiv:0912.4911 [hep-th]].   
[18] D.Bombardelli, D. Fioravanti and R. Tateo,“TBA and Y-system for planar AdS(4)/CFT(3)," Nucl. Phys.B 834, 543 (2010) doi:10.1016/j.nuclphysb.2010.04.005 [arXiv:0912.4715 [hep-th].   
[19] A. Cavaglia， D. Fioravanti， N. Gromov and R. Tateo，“Quantum Spectral Curve of the （ $ { \mathcal { N } _ { \mathrm { ~ \scriptsize ~ = ~ } 6 } }$ Supersymmetric Chern-Simons Theory,” Phys. Rev. Lett.113，no. 2， 021601 (2014) doi:10.1103/PhysRevLett.113.021601 [arXiv:1403.1859 [hep-thl].   
[20] L.Anselmetti， D. Bombardelli，A. Cavagli and R.Tateo，“12 loops and triple wrapping in ABJM theory from integrability,” JHEP 1510，117 (2015） doi:10.1007/JHEP10(2015)117 [arXiv:1506.09089 [hep-th].   
[21] B. Chen, X. J. Wang and Y. S. Wu,“Integrable open spin chain in super Yang-Mills and the plane wave / SYM duality,” JHEP 0402, 029 (2004) doi:10.1088/1126-6708/2004/02/029 [hepth/0401016].   
[22] B. Chen, X. J. Wang and Y. S. Wu,“Open spin chain and open spinning string,” Phys. Lett. B 591,170 (2004) doi:10.1016/j.physletb.2004.04.013 [hep-th/0403004].   
[23] T.Erler and N. Mann,“Integrable open spin chains and the doubling trick in N=2 SYM with fundamental matter,” JHEP 0601,131 (2006) doi:10.1088/1126-6708/2006/01/131[hep-th/0508064].   
[24] R.Roiban，“On spin chains and feld theories,” JHEP 0409,023 (2004) doi:10.1088/1126- 6708/2004/09/023 [hep-th/0312218].   
[25] D.Berenstein and S.A. Cherkis,“Deformations of ${ \mathcal N } = 4$ SYM and integrable spin chain models," Nucl. Phys.B 702, 49 (2004) doi:10.1016/j.nuclphysb.2004.09.005 [hep-th/0405215].   
[26] N. Beisert and R. Roiban,“Beauty and the twist: The Bethe ansatz for twisted N=4 SYM,” JHEP 0508,039 (2005) doi:10.1088/1126-6708/2005/08/039 [hep-th/0505187].   
[27] T. Mansson and K. Zoubos,“Quantum Symmetries and Marginal Deformations,” JHEP 1010, 043(2010) doi:10.1007/JHEP10(2010)043 [arXiv:0811.3755 [hep-th].   
[28] X. J. Wang and Y. S. Wu,“Integrable spin chain and operator mixing in N=1, 2 supersymmetric theories,” Nucl. Phys.B 683,363 (2004) doi:10.1016/j.nuclphysb.2003.12.040 [hep-th/0311073].   
[29] K. Ideguchi, “Semiclasscal strings on AdS(5) x S(5)/Z(M) and operators in orbifold feld theories,”JHEP 0409,008 (2004) doi:10.1088/1126-6708/2004/09/008 [hep-th/0408014].   
[30] N.Beisert and R. Roiban,“The Bethe ansatz for Z(S)orbifolds of N=4 super Yang-Mills theory," JHEP 0511, 037 (2005) doi:10.1088/1126-6708/2005/11/037 [hep-th/0510209].   
[31] A. Solovyov,“Bethe Ansatz Equations for General Orbifolds of N=4 SYM,” JHEP 0804, 013 (2008) doi:10.1088/1126-6708/2008/04/013 [arXiv:0711.1697 [hep-th].   
[32] G.Arutyunov, M. de Leeuw and S.J. van Tongeren,“Twisting the Mirror TBA,” JHEP 1102, 025 (2011) doi:10.1007/JHEP02(2011)025 [arXiv:1009.4118 [hep-thl].   
[33] M. de Leeuw and S. J. van Tongeren,“The spectral problem for strings on twisted $A d S _ { 5 } \times S ^ { 5 }$ ”， Nucl. Phys. B 860,339 (2012) doi:10.1016/j.nuclphysb.2012.03.004 [arXiv:1201.1451 [hep-thl].   
[34] K. Zoubos,“Review of AdS/CFT Integrability, Chapter IV.2: Deformations, Orbifolds and Open Boundaries,” Lett. Math. Phys. 99, 375 (2012) [arXiv:1012.3998 [hep-th]].   
[35] S. J. van Tongeren,“Integrability of the AdS5 × S $^ { 5 }$ superstring and its deformations,” J. Phys. A 47,433001 (2014) doi:10.1088/1751-8113/47/43/433001 [arXiv:1310.4854 [hep-th].   
[36] C. Ahn, Z. Bajnok, D. Bombardelli and R. I. Nepomechie,“TBA, NLO Luscher correction, and double wrapping in twisted AdS/CFT,” JHEP 1112, 059 (2011） doi:10.1007/JHEP12(2011)059 [arXiv:1108.4914 [hep-th].   
[37] C. Ahn, Z. Bajnok, D. Bombardelli and R.I. Nepomechie,“Finite-size effect for four-loop Konishi of the $\beta$ -deformed N=4 SYM,” Phys. Lett.B 693,380 (2010) doi:10.1016/j.physletb.2010.08.056 [arXiv:1006.2209 [hep-th]].   
[38] N. Gromov and F. Levkovich-Maslyuk,“Y-system and $\beta$ deformed N=4 Super-Yang-Mills,” J. Phys.A 44 (2011) 015402 doi:10.1088/1751-8113/44/1/015402[arXiv:1006.5438 [hep-th].   
[39] M. Beccaria, F. Levkovich-Maslyuk and G. Macorini,“On wrapping corrections to GKP-like operators,” JHEP 1103 (2011) 001 doi:10.1007/JHEP03(2011)001 [arXiv:1012.2054 [hep-th].   
[4U] S.He ana J. B. Wu,“Note on Integraplty OI IMarginaIly Derormea ABJ(M) Ineories, JHEP 1304，012 （2013）Erratum:[JHEP 1604，139 (2016)] doi:10.1007/JHEP04(2013)012, 10.1007/JHEP04(2016)139,[arXiv:1302.2208 [hep-th].   
[41] E. Imeroni,“On deformed gauge theories and their string/M-theory duals,” JHEP 0810, 026 (2008) doi:10.1088/1126-6708/2008/10/026 [arXiv:0808.1271 [hep-th]]   
[42] N.Bai, H.H. Chen,X. C. Ding, D.S.Li and J.B. Wu,“Integrability of Orbifold ABJM Theories,” arXiv:1607.06643 [hep-th].   
[43] O.Lunin and J. M. Maldacena,“Deforming field theories with U(1) x U(1) global symmetry and their gravity duals,” JHEP 0505 (2005) 033 doi:10.1088/1126-6708/2005/05/033 [hep-th/0502086].   
[44] S.Frolov,“Lax pair for strings in Lunin-Maldacena background,” JHEP O505,069 (2005） [hepth/0503201].   
[45] M. Schimpf and R. C. Rashkov,“A Note on strings in deformed $A d S _ { 4 } \times C P ^ { 3 }$ : Giant magnon and single spike solutions,” Mod. Phys. Lett.A 24 (2009) 3227 doi:10.1142/S0217732309032113 [arXiv:0908.2246 [hep-th].   
[46] C. Ahn and P. Bozhilov,“Finite-size Giant Magnons on $A d S _ { 4 } \times C P _ { \gamma } ^ { 3 }$ ,” Phys. Lett.B 703 (2011) 186 doi:10.1016/j.physletb.2011.07.065 [arXiv:1106.3686 [hep-th].   
[47] J. B. Wu,“Multi-Spin Strings in $A d S _ { 4 } * C P ^ { 3 }$ and its $\beta$ -deformations,” Nucl. Phys. B 873 (2013) 260 doi:10.1016/j.nuclphysb.2013.04.011 [arXiv:1208.0389 [hep-th].   
[48] C. Ratti， “Notes on Multi-Spin Strings in $A d S _ { 4 } \times C P ^ { 3 }$ and its marginal deformations,” arXiv:1211.4694 [hep-th].   
[49] J. Bagger and N. Lambert,“Modeling multiple M2's”,Phys. Rev. D75,045020(2007)[arXiv:hepth/0611108].   
[50] J. Bagger and N. Lambert,“Gauge Symmetry and Supersymmetry of Multiple M2-Branes”, Phys. Rev. D77, 065008(2008) [arXiv:0711.0955].   
[51] J. BaggerandN. Lambert，“Commentson MultipleM2-branes”， JHEP 0802, 105(2008)[arXiv:0712.3738].   
[52] A.Gustavsson,“Algebraic structures on parallel M2-branes”， Nucl. Phys. B 811, 66 (2009), [arXiv:0709.1260].   
[53] A.Gustavsson,“One-loop corrections to Bagger-Lambert theory”,Nucl. Phys. B 807,315 (2009), [arXiv:0805.4443].   
[54] D. S. Berman, L. C. Tadrowski and D.C. Thompson,“Aspects of Multiple Membranes,” Nucl. Phys.B 802,106 (2008) doi:10.1016/j.nuclphysb.2008.05.006 [arXiv:0803.3611 [hep-th].   
[55] D. S. Berman and L. C. Tadrowski, “M-theory brane deformations,” Nucl. Phys.B 795, 201 (2008)doi:10.1016/j.nuclphysb.2007.11.016 [arXiv:0709.3059 [hep-th].   
[56] J. Caetano, O. Gurdogan and V. Kazakov,“Chiral limit of N = 4 SYMand ABJM and integrable Feynman graphs,” arXiv:1612.05895 [hep-th].   
[57] D.S. Berman， “M-theory branes and their interactions,” Phys.Rept. 456，89 (2008) doi:10.1016/j.physrep.2007.10.002 [arXiv:0710.1707 [hep-th]].   
[58] D.Gaiotto, S.Giombi and X.Yin,“Spin Chains in N=6 Superconformal Chern-Simons-Matter Theory,” JHEP 0904,066 (2009) doi:10.1088/1126-6708/2009/04/066 [arXiv:0806.4589 [hep-th].   
[59] G.Grignani, T. Harmark and M. Orselli，“The SU(2） x SU(2) sector in the string dual of N=6 superconformal Chern-Simons theory,” Nucl. Phys. B 810， 115 (2009) doi:10.1016/j.nuclphysb.2008.10.019 [arXiv:0806.4959 [hep-th].   
[60] T. Nishioka and T. Takayanagi,“On Type IIA Penrose Limit and N=6 Chern-Simons Theories,” JHEP 0808,001 (2008) doi:10.1088/1126-6708/2008/08/001 [arXiv:0806.3391 [hep-th].   
[61] J. A. Minahan, O. Ohlsson Sax and C. Sieg,“Magnon dispersion to four loops in the ABJM and ABJ models,” J. Phys. A 43, 275402 (2010) doi:10.1088/1751-8113/43/27/275402 [arXiv:0908.2463 [hep-th]].   
[62] J.A. Minahan， O. Ohlsson Sax and C. Sieg，“Anomalous dimensions atfour loops in N=6 superconformal Chern-Simons theories,” Nucl. Phys. B 846， 542 (2011) doi:10.1016/j.nuclphysb.2011.01.016 [arXiv:0912.3460 [hep-th].   
[63] M. Leoni, A. Mauri, J.A. Minahan, O. Ohlsson Sax, A. Santambrogio, C. Sieg and G. TartaglinoMazzucchelli, “Superspace calculation of the four-loop spectrum in N=6 supersymmetric ChernSimons theories,” JHEP 1012,074 (2010) doi:10.1007/JHEP12(2010)074 [arXiv:1010.1756 [hepth]].   
[64] T. McLoughlin, R. Roiban and A. A. Tseytlin,“Quantum spinning strings in AdS(4) x CP\*3: Testing the Bethe Ansatz proposal,” JHEP 0811,069 (2008) doi:10.1088/1126-6708/2008/11/069 [arXiv:0809.4038 [hep-th].   
[65] M. C. Abbott, I. Aniceto and D. Bombardelli,“Quantum Strings and the $A d S _ { 4 } / C F T _ { 3 }$ Interpolating Function,” JHEP 1012, 040 (2010) doi:10.1007/JHEP12(2010)040 [arXiv:1006.2174 [hep-th].   
[66] C.Lopez-Arcos and H. Nastase,“Eliminating ambiguities for quantum corrections to strings moving in $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ ,” Int. J. Mod. Phys. A 28,1350058 (2013) doi:10.1142/S0217751X13500589 [arXiv:1203.4777 [hep-th]].   
[67] L.Bianchi, M.S.Bianchi,A. Bres, V.Forini and E. Vescovi,“Two-loop cusp anomaly in ABJM at strong coupling,” JHEP 1410,13 (2014) doi:10.1007/JHEP10(2014)013 [arXiv:1407.4788 [hep-th]].   
[68] N. Gromov and G. Sizov， “Exact Slope and Interpolating Functions in N=6 Supersymmetric Chern-SimonsTheory,” Phys.Rev.Lett.113， no．12，121601 (2014) doi:10.1103/PhysRevLett.113.121601 [arXiv:1403.1894 [hep-th].   
[69]H. H. Chen and J. B. Wu，“Finite-size Effect for Dyonic Giant Magnons in $C P _ { \beta } ^ { 3 }$ ”， [arXiv:1612.04613 [hep-th].   
[70] N. Gromov, V. Kazakov, A. Kozak and P. Vieira,“Exact Spectrum of Anomalous Dimensions of Planar N = 4 Supersymmetric Yang-Mils Theory: TBA and excited states,” Lett. Math. Phys. 91 (2010)265 doi:10.1007/s11005-010-0374-8 [arXiv:0902.4458 [hep-th].   
[71] B.I. Zwiebel,“Two-loop Integrability of Planar N=6 Superconformal Chern-Simons Theory,” J. Phys.A 42, 495402 (2009) doi:10.1088/1751-8113/42/49/495402 [arXiv:0901.0411 [hep-th].   
[72] M. Beccaria and G. Macorini, “QCD properties of twist operators in the N=6 Chern-Simons theory,” JHEP 0906 (2009) 008 doi:10.1088/1126-6708/2009/06/008 [arXiv:0904.2463 [hep-th].   
[73] J. Gunnesson,“Wrapping in maximally supersymmetric and marginally deformed N=4 YangMills,” JHEP 0904 (2009) 130 doi:10.1088/1126-6708/2009/04/130 [arXiv:0902.1427 [hep-th].   
[74] F. Fiamberti, A. Santambrogio, C. Sieg and D. Zanon, “Finite-size effcts in the superconformal beta-deformed N=4 SYM,” JHEP 0808 (2008) 057 doi:10.1088/1126-6708/2008/08/057 [arXiv:0806.2103 [hep-th].   
[75] O.Aharony, O.Bergman and D.L. Jafferis,“Fractional M2-branes,” JHEP 0811, O43 (2008) [arXiv:0807.4924 [hep-th]].   
[76] D.Bak， D. Gang and S. J. Rey，“Integrable Spin Chain of Superconformal U(M) x anti-U(N） Chern-Simons Theory,” JHEP 0810 (2008） 038 doi:10.1088/1126-6708/2008/10/038 [arXiv:0808.0170 [hep-th].   
[77] J.A. Minahan,W. Schulgin and K. Zarembo,“Two loop integrability for Chern-Simons theories with N=6 supersymmetry,” JHEP 0903 (2009) 057 doi:10.1088/1126-6708/2009/03/057 [arXiv:0901.1142 [hep-th]].   
[78] A. Cavaglia, N. Gromov and F. Levkovich-Maslyuk,“On the Exact Interpolating Function in ABJ Theory,” arXiv:1605.04888 [hep-th].   
[79] C. Ahn and R.I. Nepomechie,“N=6 super Chern-Simons theory S-matrix and al-loop Bethe ansatz equations,” JHEP 0809, 010 (2008) [arXiv:0807.1924 [hep-th].   
[80] C.Ahn,Z. Bajnok,D. Bombardeli and R.I. Nepomechie,“Twisted Bethe equations from a twisted S-matrix,” JHEP 1102,027 (2011） [arXiv:1010.3229 [hep-th]].   
[81] C. Ahn, M. Kim and B. H. Lee,“Worldsheet S-matrix of beta-deformed SYM,” Phys. Lett.B 719 (2013) 458 doi:10.1016/j.physletb.2013.01.047 [arXiv:1211.4506 [hep-th]].   
[82] J.Gomis,D. Sorokin and L.Wulff,“The Complete $A d S _ { 4 } \times C P ^ { 3 }$ superspace for the type IIA superstring and D-branes,” JHEP 0903, 015 (2009),[arXiv:0811.1566 [hep-th].   
[83] D. Sorokin and L. Wulff,“Peculiarities of String Theory on $A d S _ { 4 } \times C P ^ { 3 }$ ,” arXiv:1101.3777 [hepth].