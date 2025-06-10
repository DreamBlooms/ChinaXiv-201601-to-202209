# Glueball spectrum from $N _ { f } = 2$ lattice QCD study on anisotropic lattices

CLQCD collaboration   
Wei Sun,a,b Long-Cheng Gui,c,d Ying Chen,a,b Ming Gong, Chuan Liu, $^ { e , f }$ Yu-Bin   
Liu,9 Zhaofeng Liu,α,b Jian-Ping Ma,h Jian-Bo Zhangi   
a Institute of High Energy Physics, Chinese Academy of Sciences, Beijing 10o049,P.R. China   
bSchool of Physics, University of Chinese Academy of Sciences, Beijing 100049, P.R. China   
cDepartment of Physics and Synergetic Innovation Center for Quantum Effects and Applications, Hunan Normal University， Changsha 410081, P.R. China   
dKey Laboratory of Low-Dimensional Quantum Structures and Quantum Control of Ministry of Education,Changsha 410081,P.R. China   
eCollborative Innovation Center of Quantum Matter， Peking University， Beijing 100871， P.R. China   
f School of Physics and Center for High Energy Physics, Peking University, Beijing 100871, P.R. China   
9 School of Physics,Nankai University， Tianjin 30oo71,P.R. China   
h Institute of Theoretical Physics, Chinese Academy of Sciences, Beijing 10oo80, P.R. China   
（204号 $i$ Department of Physics, Zhejiang University, Hangzhou, Zhejiang 310027, P.R. China E-mail: sunw@ihep.ac.cn， guilongcheng@ihep.ac.cn， cheny@ihep.ac.cn, gongming@ihep.ac.cn， liuchuan@pku.edu.cn，liuyb@nankai.edu.cn, liuzf@ihep.ac.cn，majp@itp.ac.cn， jbzhang@zimp.zju.edu.cn

ABSTRACT:The lowest-lying glueballs are investigated from $N _ { f } ~ = ~ 2$ QCD study on aniostropic lattices. Only the gluonic operators built from Wilson loops are involved in calculating the corresponding correlation functions. In the tensor channel, we obtain the ground state mass to be 2.367(35) GeV and 2.380(61) GeV at $m _ { \pi } \sim 9 3 8$ MeV and 650 MeV, respectively. In the pseudoscalar channel, when we use the gluonic operator whose continuum limit has the form of $\epsilon _ { i j k } T r B _ { i } D _ { j } B _ { k }$ ，we obtain the ground state mass to be 2.559(50) GeV and 2.605(52) GeV at the two pion masses. These results are in agreement with the corresponding glueball masses in the quenched approximation and show little dependence of pion masses. In contrast, if we use the topological charge density as field operators for the pseudoscalar, the masses of the lowest state are much lighter (around 1GeV) and compatible with the expected masses of the flavor singlet $q q$ meson. This provides a strong hint that the operator $\epsilon _ { i j k } T r B _ { i } D _ { j } B _ { k }$ and the topological charge density couple very differently to the glueball states and $q q$ mesons. In the scalar channel, the ground state masses extracted from the correlation functions of gluonic operators are determined to be around 1.4-1.5 GeV, which are close to the ground state masses from the correlation functions of the quark bilinear operators. In all cases, the mixing between glueballs and conventional mesons remains to be investigated in the future.

KEYWORDs: Lattice QCD,Glueball Spectrum, Topological Charge Density

# Contents

1Introduction 1

2 Lattice setup 2

3Numerical details 4

3.1 Variational method 5   
3.2 Data analysis 6   
3.3 Interpretation of the ground states 12

4Further study on the pseudoscalar channel 13

5Summary and conclusions 17

# 1 Introduction

Due to the self-interactions among gluons, Quantum Chromodynamics (QCD) admits the existence of a new type of hadrons made up of gluons,usually called glueballs. Glueballs are of great physical interests since they are distinct from the conventional $q q$ mesons described in the constituent quark model. Glueballs have been intensively studied by QCD inspired phenomenological models [1-6] and also by lattice QCD. Early lattice QCD studies in the quenched approximation show that the lowest pure gauge glueballs are the scalar, the tensor,and the pseudoscalar gluebals, with masses of 1.5-1.7 GeV, 2.2-2.4 GeV,and 2.6 GeV, respectively [7-9]. For the masses of the scalar and tensor glueballs, some preliminary unquenched lattice studies have given compatible results [1O-13]. However, for the mass of the pseudoscalar glueball, a consensus has not been reached. Experimentally, there are several candidates for the scalar glueball, such as $f _ { 0 } ( 1 3 7 0 ) , f _ { 0 } ( 1 5 0 0 ) , f _ { 0 } ( 1 7 1 0 )$ ，however, none of them has been unambiguously identified as a glueball state. On the other hand, $J / \psi$ radiative decays are usually regarded as an ideal hunting ground for glueballs. A few lattice studies have been devoted to the calculation of the radiative production rate of the scalar and the tensor gluebals in the quenched approximation [14,15]. The predicted production rate of the scalar glueball is consistent with that of $f _ { 0 } ( 1 7 1 0 )$ ，and supports $f _ { 0 } ( 1 7 1 0 )$ to be either a good candidate for the scalar glueball or dominated by a glueball component. The predicted production rate of the tensor glueball is roughly $1 \%$ .It is interesting to note that the BESIII Collaboration find that the tensor meson $f _ { 2 } ( 2 3 4 0 )$ has large branching fractions in the processes $J / \psi  \gamma \eta \eta$ [16] and $J / \psi  \gamma \phi \phi$ [17].

Even though the quenched lattice QCD studies have provide some information on the existence of glueballs, it is highly desired that full lattice QCD studies can be performed in the glueball sector. In this work, we attempt to address this question using the $N _ { f } = 2$ （20 gauge field configurations that we generated on anisotropic lattices. The advantage of the use of anisotropic lattice is two-folds: on the one hand,a large statistics can be obtained by a relatively low cost of computational resources,on the other hand, the finer lattice spacing in the temporal direction can provide a better resolution for the signals of physical states. As the first step, we willfocus on the lowest-lying gluebal states, such as the scalar, the tensor and the pseudoscalar states. We will also explore the quark mass dependence of the masses of these states by using gauge configurations with different bare quark mass parameters. Special attention is paid in the pseudoscalar channel, since the results of the previous full-QCD studies in this channel are still ambiguous. On the other hand, owing to the $U _ { A } ( 1 )$ anomaly, gluons can couple strongly to the flavor singlet pseudoscalar meson 1 $\eta ^ { \prime }$ in the $N _ { f } = 2 + 1$ case).A recent $N _ { f } = 2 + 1$ lattice study showed that $\eta ^ { \prime }$ could be extracted from the negative tail of the correlation function of the topological charge density operator [18]. In contrast, a similar study in the quenched approximation found a pseudoscalar with a mass compatible with that in the pure gauge theory [19]. Therefore, we would like to check if a pseudoscalar glueball state also exists apart from the $\eta ^ { \prime }$ state in the presence of sea quarks.

Table 1. Parameters of configurations   

<html><body><table><tr><td>β L3×T</td><td></td><td>as</td><td>mπ</td><td>Nconf</td></tr><tr><td>2.5 12× 128</td><td>5</td><td>0.114fm</td><td>650 MeV</td><td>4800</td></tr><tr><td>2.5 12³× 128</td><td>5</td><td>0.118fm</td><td>938 MeV</td><td>10400</td></tr></table></body></html>

This paper is organized as follows: Section 2 contains a brief description for the generation of gauge field configurations. Section 3 presents the calculation details and the results of the glueball spectrum. The study of the pseudoscalar channel using the topological charge density operator will be discussed in Section 4,where we will also analyze the difference of the topological charge density operator from the conventional gluonic operators for the pseudoscalar glueball in previous quenched studies. Finally, we will give a summary and an outlook in Section 5.

# 2 Lattice setup

The gauge action we used is the tadpole improved gluonic action on anisotropic lattices [7]:

$$
S _ { g } = - \beta \sum _ { i > j } \left[ \frac { 5 } { 9 } \frac { T r P _ { i j } } { \gamma _ { g } u _ { s } ^ { 4 } } - \frac { 1 } { 3 6 } \frac { T r R _ { i j } } { \gamma _ { g } u _ { s } ^ { 6 } } - \frac { 1 } { 3 6 } \frac { T r R _ { j i } } { \gamma _ { g } u _ { s } ^ { 6 } } \right] - \beta \sum _ { i } \left[ \frac { 4 } { 9 } \frac { \gamma _ { g } T r P _ { 0 i } } { u _ { s } ^ { 2 } } - \frac { 1 } { 3 6 } \frac { \gamma _ { g } T r R _ { i 0 } } { u _ { s } ^ { 4 } } \right]
$$

where $P _ { i j }$ is the usual plaquette variable and $R _ { i j }$ is the $2 \times 1$ Wilson loop on the lattice. The parameter $u _ { s }$ , which we take to be the forth root of the average spatial plaquette value, incorporates the usual tadpole improvement and $\gamma _ { g }$ designates the gauge aspect bare ratio of the anisotropic lattice，denoted as $\xi _ { 0 }$ in our former quenched studies [20]. Although （204号 $\gamma _ { g }$ suffers only small renormalization with the tadpole improvement [21],we have to tune it by determining the renormalized anisotropy ratio $\xi _ { g }$ . As for the tadpole improvement parameter $u _ { t }$ for temporal gauge links,we take the approximation $u _ { t } \approx 1$ following the conventional treatment of the anisotropic lattice setup.

We use the Wilson-loop ratios approach, with which the finite volume artifacts mostly cancel [22, 23]. We measure the ratios

$$
\begin{array} { c c c } { { R _ { s s } ( x , y ) = \displaystyle \frac { W _ { s s } ( x , y ) } { W _ { s s } ( x + 1 , y ) }  e ^ { - a _ { s } V _ { s } ( y a _ { s } ) } , } } \\ { { R _ { s t } ( x , t ) = \displaystyle \frac { W _ { s t } ( x , t ) } { W _ { s s } ( x + 1 , t ) }  e ^ { - a _ { s } V _ { s } ( t a _ { t } ) } } } \end{array}
$$

and expect the spatial and temporal behaviors being the same at the correct $\xi _ { g }$ . Therefore we find $\xi _ { g }$ by minimizing

$$
L ( \xi _ { g } ) = \sum _ { x , y } \frac { ( R _ { s s } ( x , y ) - R _ { s t } ( x , \xi _ { g } y ) ) ^ { 2 } } { ( \Delta R _ { s } ) ^ { 2 } + ( \Delta R _ { t } ) ^ { 2 } }
$$

where $\Delta R _ { s }$ and $\Delta R _ { t }$ are the statistical errors of $R _ { s s }$ and $R _ { s t }$ . We interpolate $R _ { s t } ( x , \xi _ { g } y )$ and its error with a cubic spine interpolation at non-integer $\xi _ { g } y$ .Since small $x , y$ may introduce short-range lattice effects and large ones contribute only fluctuations, we scan and test different ranges and finally choose $x , y \in \{ 2 , 3 , 4 , 5 \}$

We adopt the anisotropic clover fermion action in the fermion sector [24]:

$$
\begin{array} { l } { { \displaystyle { \cal S } _ { f } = \sum _ { x } \bar { \psi } ( x ) \left[ m _ { 0 } + \gamma _ { t } \hat { W } _ { t } + \sum _ { s } \frac { 1 } { \gamma _ { f } } \gamma _ { s } \hat { W } _ { s } \right. } } \\ { { \displaystyle \left. - \frac { 1 } { 4 u _ { s } ^ { 2 } } \left( \frac { \gamma _ { g } } { \gamma _ { f } } + \frac { 1 } { \xi } \right) \sum _ { s } \sigma _ { t s } \hat { F } _ { t s } + \frac { 1 } { u _ { s } ^ { 3 } } \frac { 1 } { \gamma _ { f } } \sum _ { s < s ^ { \prime } } \sigma _ { s s ^ { \prime } } \hat { F } _ { s s ^ { \prime } } \right] \psi ( x ) } } \end{array}
$$

where $\begin{array} { r } { \hat { F } _ { \mu \nu } = \frac { 1 } { 4 } \mathrm { I m } ( P _ { \mu \nu } ( x ) ) } \end{array}$ and the dimensionless Wilson operator reads

$$
\begin{array} { l } { { \displaystyle \hat { W } _ { \mu } = \nabla _ { \mu } - \frac { 1 } { 2 } \gamma _ { \mu } \Delta _ { \mu } } } \\ { { \displaystyle \nabla _ { \mu } f ( x ) = \frac { 1 } { 2 } \left[ U _ { \mu } ( x ) f ( x + \mu ) - U _ { \mu } ^ { \dagger } ( x - \mu ) f ( x - \mu ) \right] } } \\ { { \displaystyle \Delta _ { \mu } f ( x ) = U _ { \mu } ( x ) f ( x + \mu ) + U _ { \mu } ^ { \dagger } ( x - \mu ) f ( x - \mu ) - 2 f ( x ) . } } \end{array}
$$

The bare fermion aspect ratio $\gamma _ { f }$ is also tuned to make sure that the measured aspect ratic $\xi _ { f } \approx \xi _ { g } \approx \xi = 5$ ： $\xi _ { f }$ is measured from the dispersion relation of the pseodoscalar and vector mesons

$$
E ( p ) ^ { 2 } a _ { t } ^ { 2 } = m ^ { 2 } a _ { t } ^ { 2 } + \frac { | \vec { p } | ^ { 2 } a _ { s } ^ { 2 } } { \xi _ { f } ^ { 2 } } .
$$

where $\vec { p } = 2 \pi \vec { k } / L _ { s }$ is the momentum on the lattice with periodic spatial boundary conditions.

The lattice spacings $a _ { s }$ are set by calculating the static potential parameterized as $V ( r ) = V _ { 0 } + \alpha / r + \sigma r$ . Using the Sommer scale pamameter $r _ { 0 } ^ { - 1 } = 4 1 0 ( 2 0 )$ MeV defined

Table 2. Ground state meson spectrum   

<html><body><table><tr><td>mpsat</td><td>mps(MeV)</td><td>mvat</td><td>mv(MeV)</td><td>msat</td><td>ms(MeV)</td></tr><tr><td>0.07508(50)</td><td>650(4)</td><td>0.1147(19)</td><td>993(16)</td><td>0.1574(61)</td><td>1362(53)</td></tr><tr><td>0.1119(4)</td><td>938(3)</td><td>0.1388(12)</td><td>1164(10)</td><td>0.1757(34)</td><td>1473(28)</td></tr></table></body></html>

through r2dV(r) $r ^ { 2 } \frac { d V ( r ) } { d r } | _ { r = r _ { 0 } } = 1 . 6 5$ lr=ro = 1.65,we can determine the ratio

$$
\frac { r _ { 0 } } { a _ { s } } = \sqrt { \frac { 1 . 6 5 + \alpha } { \sigma a _ { s } ^ { 2 } } }
$$

where $\alpha$ and $\sigma a _ { s } ^ { 2 }$ are derived from the fit to caluclated potential $\begin{array} { r } { V ( r ) = V ( \hat { r } a _ { s } ) } \end{array}$ with $\hat { r }$ being the spatial distance in the lattice units.

We generate two gauge ensembles on the $1 2 ^ { 3 } \times 1 2 8$ anisotropic lattice at $\beta = 2 . 5$ with the bare quark mass parameters $m _ { 0 } = 0 . 0 5$ and $m _ { 0 } = 0 . 0 6$ . The pion masses on the two ensembles are measured to be 938 MeV and 650 MeV respectively. In the following, we use these $m _ { \pi }$ 's to label the gauge ensembles for convenience. The ensemble parameters are listed in Table 1.

Apart from the pion masses, we also calculate the masses of the vector meson and scalar meson for calibration,which are listed in Table 2. We use the conventional $I = 1$ （204号 vector and scalar quark bilinear operators as sink operators and the corresponding Gaussian smeared wal source operators to calculate the correlation functions. There is no ambiguity for the vector meson masses $m _ { V }$ 's since they are all below the two-pion threshold. For the scalar,we actually deal with $a _ { 0 }$ whose two-body strong decay mode is mainly $\eta ^ { \prime } \pi$ (there is only one $I = 0$ pseudoscalar meson for $N _ { f } = 2$ ，which is taken as the counterpart of the (approximately） flavor-singlet $\eta ^ { \prime }$ in the $N _ { f } = 3$ case). At $m _ { \pi } \sim 9 3 8$ MeV,the calculated mass in $a _ { 0 }$ channel is 1473(28) MeV,which must be the mass of $a _ { 0 }$ since it lies below two-pion threshold and certainly below the $\eta ^ { \prime } \pi$ threshold． At $m _ { \pi } \sim 6 5 0$ MeV, $m _ { \eta ^ { \prime } }$ is estimated to be $m _ { \eta ^ { \prime } } \sim 8 9 0$ MeV (see below in Sec. 4), thus the mass value of 1362(53) MeV is also below the $\eta ^ { \prime } \pi$ threshold and can be taken as the mass of $a _ { 0 }$ scalar at this pion mass. In order to calculate the $I = 0$ scalar meson mass, the disconnected diagrams (quark annihilation diagrams) should be considered. We have not done this yet, but as a raw assumption,we take the $a _ { 0 }$ mass as an approximation to the mass of the isoscalar scalar meson.

# 3 Numerical details

In this work, the spectrum of the lowest-lying glueballs in three specific channels, namely scalar, tensor and pseudoscalar will be explored. The interpolating operators for these states are pure gluonic operators which have been extensively adopted in the previous quenched lattice studies. In other words,in each specific channel, no operators involving quark fields are included. This of course is only an approximation, assuming that the gluondominated state that we are after can be well-described by gluonic operators. Needless to say, mixing with the quark operators should be considered later on, especially for cases where the mixing is severe. For completeness, we briefly recapitulate the major ingredients of glueballspectrum computation in the following. One can resort to [9] for further details.

# 3.1 Variational method

The continuum $S O ( 3 )$ spatially rotational symmetry is broken into the discrete symmetry described by the octahedral point group $O$ on the lattice,whose irreducible representations $R$ are labelled as $A _ { 1 } , A _ { 2 } , E , T _ { 1 } , T _ { 2 }$ ，and have dimensionalities 1，1，2,3,3 respectively. Therefore, the lattice interpolation fields for a glueball of $J ^ { P C }$ quantum number should be denoted by $R ^ { P C }$ with $R$ the irreducible representation of $O$ which may include the components of $J$ in the continuum limit.The parity $P = \pm$ and the charge conjugation $C = \pm$ can be realized by considering the transformation properties under the spatial reflection and time reversal operations. Since the octahedral group $O$ is a subgroup of $S U ( 2 )$ ， the subduced representation of $S U ( 2 )$ with respect to $O$ is reducible in general (for integer spin,this occurs for $J \ \geq \ 2$ ). Table 3 shows the reduction of the subduced representation of $S U ( 2 )$ up to $J = 5$ . For instance, the scalar and pseudoscalar with $J = 0$ （20 states are represented by $A _ { 1 }$ , tensor states with $J = 2$ are reduced to direct sum of $E$ and $T _ { 2 }$ ,i.e. $( J = 2 ) \downarrow O = E \oplus T _ { 2 }$

Table 3. Subduced representation of $S U ( 2 )$ with respect to $O$ up to $J = 5$   

<html><body><table><tr><td>J R</td><td>0 1 2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>A1</td><td>1 0</td><td>0 0</td><td>1</td><td>0</td></tr><tr><td>A2</td><td>0</td><td>0 0 1</td><td>0</td><td>0</td></tr><tr><td>E</td><td>0 0</td><td>1 0</td><td>1</td><td>1</td></tr><tr><td>T1</td><td>0 1</td><td>0 1</td><td>1</td><td>2</td></tr><tr><td>T2</td><td>0 0</td><td>1 1</td><td>1</td><td>1</td></tr></table></body></html>

As described in [9],we use Wilson loops (up to 8 gauge links) shown in Fig. 1. Each irrep $R$ of group $O$ can be realized by the specific linear combination of its 24 copies of a prototype Wilson loop under the 24 rotation operations of $O$ . The combination coefficients of each $R$ can be found in [9]. So each prototype may provide a different realization of $R$ ： On the other hand, the Wilson loops mentioned above can be built from smeared gauge links,such that different smearing schemes can provide more realizations of the gluonic operators. In practice,we have four different realization of each $R$ by choosing different prototypes. For the smearing of gauge links, we adopt 6 smearing schemes by combining the single-link and double-link smearing procedures with different iteration sequences. Finally we havea setof 24 diferent gluonic operators, $\{ \phi _ { \alpha } ^ { ( R ) } , \alpha = 1 , 2 , \ldots , 2 4 \}$ ,for each $R ^ { P C }$ ，

![](images/38d6eedc5c138dfb9546359430870c4254c7141416ff47f33c2e360a1334a17b.jpg)  
Figure 1. Prototypes of Wilson loops for the construction of glueball operators [8, 9]

Based on these operator sets，we use the variational method to get the optimized operators ${ \mathcal { O } } ^ { ( R ) }$ which mostly project to specific gluebal states. In each symmetry channel $R$ , we frst calculate the $2 4 \times 2 4$ correlation matrix $C ^ { ( R ) } ( t )$ ，

$$
C _ { \alpha \beta } ^ { ( R ) } ( t ) = \sum _ { \tau } \langle 0 | \bar { \phi } _ { \alpha } ^ { ( R ) } ( t + \tau ) \bar { \phi } _ { \beta } ^ { ( R ) \dagger } ( \tau ) | 0 \rangle , \quad \alpha , \beta = 1 , . . . , 2 4
$$

where $\bar { \phi } _ { \alpha } ^ { ( R ) }$ is the vacuum-subtracted operator of $\phi _ { \alpha } ^ { ( R ) }$ ，

$$
\bar { \phi } _ { \alpha } ^ { ( R ) } ( t ) = \phi _ { \alpha } ^ { ( R ) } ( t ) - \langle 0 | \phi _ { \alpha } ^ { ( R ) } ( t ) | 0 \rangle .
$$

In practice, we only apply the vacuum subtraction to the operators in $A _ { 1 } ^ { + + }$ channel. Secondly, we solve the following generalized eigenvalue problem,

$$
\begin{array} { r } { { \bf C } ^ { ( R ) } ( t _ { 0 } ) { \bf v } _ { i } ^ { ( R ) } = \lambda _ { i } ( t _ { 0 } ) { \bf C } ^ { ( R ) } ( 0 ) { \bf v } _ { i } ^ { ( R ) } , } \end{array}
$$

where v(R is the i-th eigenvector,and Xi = e-mi(to)to is the i-theigenvalue where mi(to) is dependent on $t _ { 0 }$ and is close to the energy of the $i$ -th state. For all the $R$ channels, we use $t _ { 0 } = 1$ Itis $\mathbf { v } _ { i } ^ { ( R ) }$ gives thelinearlyombinational coefficients of operators $\bar { \phi } _ { \alpha } ^ { ( R ) }$ to build an optimal operator $\Phi _ { i } ^ { ( R ) }$ which overlaps mostly to the $i$ -th state,

$$
\Phi _ { i } ^ { ( R ) } ( t ) = \sum _ { \alpha = 1 } ^ { 2 4 } v _ { i , \alpha } ^ { ( R ) } \bar { \phi } _ { \alpha } ^ { ( R ) } ( t ) .
$$

# 3.2 Data analysis

In this work, the correlation function of the optimal operator $\Phi _ { i } ^ { ( R ) }$ for the $i$ -th state is calculated as

$$
\tilde { C } _ { i } ^ { ( R ) } ( t ) = \sum _ { \tau } \langle 0 | \Phi _ { i } ^ { ( R ) } ( t + \tau ) \Phi _ { i } ^ { ( R ) \dagger } ( \tau ) | 0 \rangle ,
$$

where we do the summation over the temporal direction to increase the statistics. Accordingly, the effective mass is defined as

$$
m _ { i , \mathrm { e f f } } ^ { ( R ) } ( t ) = \ln \left( \frac { \tilde { C } _ { i } ^ { ( R ) } ( t ) } { \tilde { C } _ { i } ^ { ( R ) } ( t + 1 ) } \right) .
$$

![](images/fb5013fbfc61778af37b59aac3fd603c657325a4ba33dd3debe32407f1a9555a.jpg)  
Figure 2. Effective mass plateaus of $\bar { C } _ { 1 } ^ { ( R ) } ( t )$ (red points） and $\bar { C } _ { 2 } ^ { ( R ) } ( t )$ (blue points) in the $R = A _ { 1 } ^ { + + }$ （204号 channel. The left and the right panel show the results at $m _ { \pi } \sim 9 3 8$ MeV and $m _ { \pi } \sim 6 5 0$ MeV, respectively. The shaded bands are plotted with the best fit parameters using model of Eq. (3.9) in the illustrated time range.

We divide the measurements into bins with each bin including 10O measurements. The statistical errors are obtained by the one-bin-eliminating jackknife analysis.

For $A _ { 1 } ^ { + + }$ channel, the subtraction of the vacuum is very subtle. Even though we have （204号 $O ( 1 0 ^ { 4 } )$ gauge configurations in each ensemble, when we perform the jackknife analysis above after subtracting the vacuum expectation values of the operator, we find there is still a residual (negative) constant term in the correlation function, which makes the effective mass $m _ { i , \mathrm { e f f } } ( t )$ going upward when $t$ is large. This problem can be attributed to the large fuctuation of gauge configurations in the presence of sea quarks. To circumvent this difficulty, we adopt a vacuum-subtraction scheme by subtracting the correlation function $C ( t )$ with the shifted one $C ( t + \delta t )$ ，

$$
\begin{array} { r } { \hat { C } _ { i } ^ { A _ { 1 } ^ { + + } } ( t ) = \tilde { C } _ { i } ^ { A _ { 1 } ^ { + + } } ( t ) - \tilde { C } _ { i } ^ { A _ { 1 } ^ { + + } } ( t + \delta t ) , } \end{array}
$$

whose spectral expression is

$$
\bar { C } _ { i } ^ { A _ { 1 } ^ { + + } } ( t ) = \sum _ { j } W _ { i j } ^ { A _ { 1 } ^ { + + } } ( 1 - e ^ { - m _ { j } \delta t } ) e ^ { - m _ { j } t } \equiv \sum _ { j } W _ { i j } ^ { \prime A _ { 1 } ^ { + + } } e ^ { - m _ { j } t } ,
$$

where WA++ visthspectralweightoftej-thstate . Obviously, the possible constant term cancels with the spectrum unchanged. In practice, we take $\delta t = 5 a _ { t }$ ：

We focus on the $R ^ { P C } = A _ { 1 } ^ { + + } , A _ { 1 } ^ { - + } , E ^ { + + }$ ，and $T _ { 2 } ^ { + + }$ channels in this work. For all thesechaels,theivemassofC(t)(repontsadC(t)(epo for $A _ { 1 } ^ { + + }$ channel） are plotted in Fig. 2, 3, 4 and 5,respectively. In each figure, the left panel shows the result at $m _ { \pi } \sim 9 3 8$ MeV,and the right panel is for $m _ { \pi } \sim 6 5 0$ MeV. Even though we have a set of 24 operators for each channel, it is seen that the effective masses do not show plateaus from the very early time slices. This is very different from the case in the quenched approximation. One important reason for this is that,in each channel, the spectrum of the full QCD is much more complicated than in the quenched approximation due to the sea quarks. This is true in principle, since $q q$ states and multi-hadron states with the same quantum number do contribute to the corresponding correlation function in the presence of sea quarks.

![](images/849f1c69b08aae452cbfb447134465840bc17b967ae2fc10b1521e094eb3ae55.jpg)  
Figure 3. Effective mass plateaus of $\tilde { C } _ { 1 } ^ { ( R ) } ( t )$ (red points） and ${ \tilde { C } } _ { 2 } ^ { ( R ) } ( t )$ (blue points) in the $R = A _ { 1 } ^ { - + }$ （204号 channel. The left and the right panel show the results at $m _ { \pi } \sim 9 3 8$ MeV and $m _ { \pi } \sim 6 5 0$ MeV, respectively. The shaded bands are plotted with the best fit parameters using model of Eq. (3.9) in the illustrated time range.

![](images/5e9627d19154c7eed988fed692f6930ca28ac6bd4537511a12081a64cc245c52.jpg)  
Figure 4. Effective mass plateaus of ${ \tilde { C } } _ { 1 } ^ { ( R ) } ( t )$ (red points) and ${ \tilde { C } } _ { 2 } ^ { ( R ) } ( t )$ (blue points) in the $R = E ^ { + + }$ （204 channel. The left and the right panel show the results at $m _ { \pi } \sim 9 3 8$ MeV and $m _ { \pi } \sim 6 5 0$ MeV, respectively. The shaded bands are plotted with the best fit parameters using model of Eq. (3.9) in the illustrated time range.

Given the limited number of independent operators,our optimal operator $\Phi _ { i } ^ { ( R ) }$ is actually not optimized as expected, namely, it does not only overlap to the $i$ -th state but also to other states substantiall. Asseen in the efective mass plots when $m _ { 1 , \mathrm { e f f } } ^ { ( R ) } ( t )$ tends to reach a plateau as $t$ inereases, $m _ { 2 , \mathrm { e f f } } ^ { ( R ) } ( t )$ decresesllly plateau at large $t$ (within errors). Even though one can carry out the single exponential fit to the mass of the ground state in the plateau range roughly beyond $t / a _ { t } \approx 6$ or 7, the bad signal-to-noise ratio in this time range results in a large statistical error. Since we focus on the ground states in the present study, in order to get more precise result of the masses of the ground states, we adopt the following data-analysis strategy which also make use of the measured data in the short time range. In each channel, we carry out a correlated fit to $\tilde { C } _ { 1 } ^ { ( R ) } ( t )$ and ${ \tilde { C } } _ { 2 } ^ { ( R ) } ( t )$ simultaneously through the following function forms,

![](images/7e2d2a15185338a92c00671eb11cdb81d1cbf279c9feac8bd3b27c93257c26ec.jpg)  
Figure 5. Effective mass plateaus of $\tilde { C } _ { 1 } ^ { ( R ) } ( t )$ (red points) and ${ \tilde { C } } _ { 2 } ^ { ( R ) } ( t )$ (blue points) in the $R = T _ { 2 } ^ { + + }$ （204号 channel. The left and the right panel show the results at $m _ { \pi } \sim 9 3 8$ MeV and $m _ { \pi } \sim 6 5 0$ MeV, respectively. The shaded bands are plotted with the best fit parameters using model of Eq. (3.9) in the illustrated time range.

$$
\begin{array} { r } { \tilde { C } _ { 1 } ^ { ( R ) } ( t ) = W _ { 1 1 } ^ { ( R ) } e ^ { - m _ { 1 } t } + W _ { 1 2 } ^ { ( R ) } e ^ { - m _ { 2 } t } , } \\ { \tilde { C } _ { 2 } ^ { ( R ) } ( t ) = W _ { 2 1 } ^ { ( R ) } e ^ { - m _ { 1 } t } + W _ { 2 2 } ^ { ( R ) } e ^ { - m _ { 2 } t } , } \end{array}
$$

where the second mass term is introduced to take into account the contribution of the second state and higher states (of course, one can add more mass terms, but more parameters willruin thedata ftting duetothelimited data points). In thefiting procedure, $\tilde { C } _ { 1 } ^ { ( R ) } ( t )$ and $\tilde { C } _ { 2 } ^ { ( R ) } ( t )$ are fited in the same time window $[ t _ { \mathrm { m i n } } , t _ { \mathrm { m a x } } ]$ . For each channel, we keep $t _ { \mathrm { m a x } }$ fixed and varies $t _ { \mathrm { m i n } }$ to check the stability and the quality of the fit. The fit results for the scalar $( A _ { 1 } ^ { + + } )$ ， the pseudoscalar $( A _ { 1 } ^ { - + } )$ and the tensor channels （ $E ^ { + + }$ and $T _ { 2 } ^ { + + }$ ）at the two pion masses are listed in Table 4 and 5. Except for $t _ { \operatorname* { m i n } } = 1$ case in $T _ { 2 } ^ { + + }$ channel, all other fits are acceptable with reasonable $\chi ^ { 2 } / d . o . f$ . For all the four channels, the fitted parameters $m _ { 1 }$ and $W _ { 1 1 }$ are stable with respect to the varying $t _ { \mathrm { m i n } }$ ，while $m _ { 2 }$ decreases as $t _ { \mathrm { m i n } }$ increasing gradually. This signals that our fitting model in Eq. (3.9) is not so good that we should include more mass terms to account for higher states, which, however, affect the second state more than the first state. Since we are interested only in the first states, we do not take $m _ { 2 }$ seriously and treat it as an object accommodating the effect of higher states. We also illustrate the fit results in Fig. 2,3, 4 and 5 with shaded bands. It shows that the fitting model Eq. (3.9) describes the data of the first states very well even at the very early time slices. For the second states,the fit model also fits the data more or less, especially in the small $t$ region and the large $t$ behavior. While in the middle $t$ region,the fitted results deviate somewhat from the data. This is understandable, since higher states, which do contribute,are missed in this model. This deviation actually contributes much to the $\chi ^ { 2 }$ . It is expected that the fitted $m _ { 2 }$ is generally (much） higher than the mass of the second state.

Table 4. Fitted results using fit model Eq. (3.9) with different $t _ { \mathrm { m i n } }$ at $m _ { \pi } \sim 9 3 8$ MeV.   

<html><body><table><tr><td>JPC</td><td>tmin</td><td>m1at</td><td>m2at</td><td>W11</td><td>W12</td><td>W21</td><td>W22</td><td>x²/d.o.f</td></tr><tr><td>A+</td><td>1</td><td>0.168(05)</td><td>0.545(07)</td><td>0.59(02)</td><td>0.37(02)</td><td>0.09(01)</td><td>0.86(01)</td><td>2.27</td></tr><tr><td></td><td>2</td><td>0.166(07)</td><td>0.484(12)</td><td>0.58(03)</td><td>0.37(03)</td><td>0.05(01)</td><td>0.85(01)</td><td>0.50</td></tr><tr><td></td><td>3</td><td>0.167(08)</td><td>0.471(19)</td><td>0.59(04)</td><td>0.35(05)</td><td>0.04(01)</td><td>0.83(02)</td><td>0.48</td></tr><tr><td></td><td>4</td><td>0.167(11)</td><td>0.462(31)</td><td>0.59(06)</td><td>0.34(08)</td><td>0.04(02)</td><td>0.82(04)</td><td>0.52</td></tr><tr><td></td><td>5</td><td>0.165(12)</td><td>0.508(52)</td><td>0.59(07)</td><td>0.42(12)</td><td>0.05(02)</td><td>0.94(14)</td><td>0.48</td></tr><tr><td>A+</td><td>1</td><td>0.306(08)</td><td>0.712(13)</td><td>0.65(02)</td><td>0.33(02)</td><td>0.13(2)</td><td>0.81(1)</td><td>2.24</td></tr><tr><td></td><td>2</td><td>0.314(12)</td><td>0.650(24)</td><td>0.66(04)</td><td>0.28(05)</td><td>0.09(3)</td><td>0.80(2)</td><td>1.06</td></tr><tr><td></td><td>3</td><td>0.302(18)</td><td>0.618(32)</td><td>0.60(07)</td><td>0.35(09)</td><td>0.07(03)</td><td>0.78(3)</td><td>1.09</td></tr><tr><td></td><td>4</td><td>0.269(29)</td><td>0.530(47)</td><td>0.43(12)</td><td>0.54(13)</td><td>0.01(3)</td><td>0.69(4)</td><td>0.98</td></tr><tr><td>E++</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>1</td><td>0.279(05)</td><td>0.695(09)</td><td>0.67(01)</td><td>0.31(01)</td><td>0.19(1)</td><td>0.77(1)</td><td>1.48</td></tr><tr><td></td><td>2</td><td>0.280(06)</td><td>0.675(17)</td><td>0.66(02)</td><td>0.31(02)</td><td>0.18(2)</td><td>0.76(1)</td><td>1.48</td></tr><tr><td></td><td>3</td><td>0.285(12)</td><td>0.582(32)</td><td>0.66(05)</td><td>0.27(06)</td><td>0.13(3)</td><td>0.71(2)</td><td>0.85</td></tr><tr><td></td><td>4</td><td>0.281(18)</td><td>0.535(50)</td><td>0.63(10)</td><td>0.27(12)</td><td>0.09(5)</td><td>0.67(3)</td><td>0.86</td></tr><tr><td></td><td>5</td><td>0.282(24)</td><td>0.508(75)</td><td>0.63(15)</td><td>0.25(20)</td><td>0.08(8)</td><td>0.64(6)</td><td>0.95</td></tr><tr><td>T++</td><td>1</td><td>0.282(04)</td><td>0.655(06)</td><td>0.63(01)</td><td>0.34(01)</td><td>0.15(1)</td><td>0.80(1)</td><td>4.47</td></tr><tr><td></td><td>2</td><td>0.287(05)</td><td>0.597(09)</td><td>0.63(02)</td><td>0.32(02)</td><td>0.10(1)</td><td>0.80(1)</td><td>1.69</td></tr><tr><td></td><td>3</td><td>0.300(08)</td><td>0.576(17)</td><td>0.70(04)</td><td>0.21(05)</td><td>0.10(2)</td><td>0.77(1)</td><td>1.08</td></tr><tr><td></td><td>4</td><td>0.289(12)</td><td>0.563(31)</td><td>0.63(06)</td><td>0.31(08)</td><td>0.08(3)</td><td>0.77(3)</td><td>1.11</td></tr><tr><td></td><td>5</td><td>0.275(17)</td><td>0.552(58)</td><td>0.55(09)</td><td>0.46(12)</td><td>0.07(4)</td><td>0.76(9)</td><td>1.13</td></tr></table></body></html>

As shown in Table 4 and 5,most of the fits using different $t _ { \mathrm { m i n } }$ are statistically acceptable and the masses of the first states are relatively stable. Therefore,for the final result of $m _ { 1 }$ in each channel, we take tentatively the average value of $m _ { 1 }$ 's at different $t _ { \mathrm { m i n } }$ （20 weighted by their inversed squared errors. The statistical errors are accordingly derived. This averaging is illustrated in Fig. 6,where data points are the fitted result of $m _ { 1 }$ at different $t _ { \mathrm { m i n } }$ and the shaded bands are the averaged values with averaged errors. The results are also listed in Table 6. At the heavy pion mass $m _ { \pi } \sim 9 3 8$ MeV, $m _ { 1 } ( E ^ { + + } )$ is very close to $m _ { 1 } ( T _ { 2 } ^ { + + } )$ , as expected by the rotational symmetry restoration in the continuum limit where they correspond to the mass of the same $2 ^ { + + }$ tensor state. However for the lighter $m _ { \pi } \sim 6 5 0$ MeV, the two masses deviate from each other by 2Oo MeV. Since the lattice spacings at the two pion massed are very close, the extent of the rotational symmetry breaking should be similar. We tentatively attribute this large deviation to the relatively small statistics at $m _ { \pi } \sim 6 5 0$ MeV,which is roughly one-half as large as that at $m _ { \pi } \sim 9 3 8$ （204 MeV (see Table 1). From Table 2 and Table 6 one can see that the masses of ground state scalar meson and our scalar glueball are very close to each other, this may indicate there are mixing between $q q$ and the scalar glueball,which needs further investigation.

Table 5.Fitted results using fit model Eq.(3.9)with different $t _ { \mathrm { m i n } }$ at $m _ { \pi } \sim 6 5 0$ MeV   

<html><body><table><tr><td>JPC</td><td>tmin</td><td>m1at</td><td>m2at</td><td>W11</td><td>W12</td><td>W21</td><td>W22</td><td>x²/d.o.f</td></tr><tr><td>A+</td><td>1</td><td>0.179(09)</td><td>0.544(12)</td><td>0.63(03)</td><td>0.35(03)</td><td>0.08(02)</td><td>0.86(02)</td><td>1.90</td></tr><tr><td></td><td>2</td><td>0.159(14)</td><td>0.477(17)</td><td>0.54(05)</td><td>0.43(06)</td><td>0.04(2)</td><td>0.85(2)</td><td>0.94</td></tr><tr><td></td><td>3</td><td>0.168(17)</td><td>0.49(30)</td><td>0.57(07)</td><td>0.39(08)</td><td>0.05(2)</td><td>0.86(03)</td><td>1.03</td></tr><tr><td></td><td>4</td><td>0.178(20)</td><td>0.518(64)</td><td>0.63(09)</td><td>0.30(12)</td><td>0.06(4)</td><td>0.89(10)</td><td>1.16</td></tr><tr><td></td><td>5</td><td>0.144(24)</td><td>0.527(91)</td><td>0.46(10)</td><td>0.75(20)</td><td>0.04(3)</td><td>1.00(27)</td><td>0.87</td></tr><tr><td>A+</td><td>1</td><td>0.291(08)</td><td>0.712(16)</td><td>0.61(02)</td><td>0.37(02)</td><td>0.12(2)</td><td>0.82(2)</td><td>2.04</td></tr><tr><td></td><td>2</td><td>0.316(13)</td><td>0.689(33)</td><td>0.69(05)</td><td>0.25(06)</td><td>0.13(3)</td><td>0.79(2)</td><td>1.53</td></tr><tr><td></td><td>3</td><td>0.333(19)</td><td>0.717(63)</td><td>0.77(09)</td><td>0.13(13)</td><td>0.16(5)</td><td>0.79(4)</td><td>1.65</td></tr><tr><td></td><td>4</td><td>0.276(40)</td><td>0.580(86)</td><td>0.47(17)</td><td>0.56(18)</td><td>0.05(6)</td><td>0.70(7)</td><td>1.58</td></tr><tr><td>E++</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>1 2</td><td>0.263(07) 0.266(10)</td><td>0.629(08) 0.597(16)</td><td>0.58(02)</td><td>0.39(02)</td><td>0.12(1)</td><td>0.82(1)</td><td>1.61</td></tr><tr><td></td><td>3</td><td>0.255(13)</td><td></td><td>0.58(03)</td><td>0.37(04)</td><td>0.10(2)</td><td>0.81(1)</td><td>1.30</td></tr><tr><td></td><td></td><td></td><td>0.548(23)</td><td>0.52(05)</td><td>0.42(06)</td><td>0.06(2)</td><td>0.78(1)</td><td>1.08</td></tr><tr><td></td><td>4 5</td><td>0.264(19)</td><td>0.546(40)</td><td>0.56(09)</td><td>0.36(11)</td><td>0.07(3)</td><td>0.77(5)</td><td>1.16</td></tr><tr><td></td><td></td><td>0.296(45)</td><td>0.411(78)</td><td>0.77(48)</td><td>-0.02(54)</td><td>-0.12(28)</td><td>0.74(21)</td><td>0.74</td></tr><tr><td>T++</td><td>1</td><td>0.282(06)</td><td>0.671(08)</td><td>0.66(01)</td><td>0.31(02)</td><td>0.18(1)</td><td>0.78(1)</td><td>2.82</td></tr><tr><td></td><td>2</td><td>0.301(10)</td><td>0.633(22)</td><td>0.71(04)</td><td>0.23(04)</td><td>0.16(3)</td><td>0.76(2)</td><td>1.07</td></tr><tr><td></td><td>3</td><td>0.294(15)</td><td>0.588(32)</td><td>0.68(06)</td><td>0.25(08)</td><td>0.13(4)</td><td>0.75(2)</td><td>1.00</td></tr><tr><td></td><td>4</td><td>0.287(24)</td><td>0.528(48)</td><td>0.63(12)</td><td>0.29(16)</td><td>0.07(6)</td><td>0.71(4)</td><td>1.05</td></tr><tr><td></td><td>5</td><td>0.275(38)</td><td>0.513(76)</td><td>0.55(21)</td><td>0.40(28)</td><td>0.06(7)</td><td>0.71(8)</td><td>1.36</td></tr></table></body></html>

Table 6. Final results for the masses of the lowest state we obtain in the $A _ { 1 } ^ { + + } , A _ { 1 } ^ { - + } , E ^ { + + }$ and $T _ { 2 } ^ { + + }$ channels. These are the averaged values weighted by the inversed squared errors at each $t _ { \mathrm { m i n } }$ ：   

<html><body><table><tr><td>mπ (MeV)</td><td>m1(At+)(MeV)</td><td>m1(E++)(MeV)</td><td>m1(T++)(MeV)</td><td>m1(Ai+)(MeV)</td></tr><tr><td>938</td><td>1397(25)</td><td>2342(25)</td><td>2392(25)</td><td>2559(50)</td></tr><tr><td>650</td><td>1480(52)</td><td>2276(43)</td><td>2484(43)</td><td>2605(52)</td></tr></table></body></html>

![](images/4d1411796bf3ae5f360d2e3c1b06a5ee3fe2ab6725a5c08c36254a9b512df018.jpg)  
Figure 6. Fitted $m _ { 1 }$ for $A _ { 1 } ^ { + + } , A _ { 1 } ^ { - + } , E ^ { + + }$ and $T _ { 2 } ^ { + + }$ are ploted with respect to $t _ { \mathrm { m i n } }$ (the left panel for $m _ { \pi } \sim 9 3 8$ MeV and the right panel for $m _ { \pi } \sim 6 5 0 \mathrm { M e V }$ ). The values are expressed in the physical units inverted by the latice spacing listed in Table 1. The color bands illustrate the averaged values weighted by the inversed squared errors at each $t _ { \mathrm { m i n } }$ ：

# 3.3 Interpretation of the ground states

Generally speaking, the two-point function of an interpolating operator $\mathcal { O } ( t )$ with definite quantum numbers is usually parameterized as

$$
C ( t ) = \langle 0 | \mathcal { O } ( t ) \mathcal { O } ^ { \dagger } ( 0 ) | 0 \rangle = \sum _ { n } \langle 0 | \mathcal { O } | n \rangle \langle n | \mathcal { O } ^ { \dagger } | 0 \rangle e ^ { - m _ { n } t } ,
$$

where $\{ | n \rangle , n = 1 , 2 , . . . \}$ are eigenstates of Hamiltonian with eigen-energy $m _ { n }$ , which make up an orthogonal, normalized,and complete state set with

$$
\sum _ { n } | n \rangle \langle n | = 1 , \langle n | n ^ { \prime } \rangle = \delta _ { n n ^ { \prime } } .
$$

For QCD on a Euclidean spacetime lattice, $m _ { n }$ take discretized values and the connection of these discretized energy levels to the relevant $S$ -matrix parameters should be established through other theoretical formalisms,such as Lüscher's. Here we would only focus on the physical meaning of the fitted masses of the lowest states.

We take the scalar channel for instance. A hadron system of the bare states with the scalar quantum number $J ^ { P C } = 0 ^ { + + }$ can be a bare scalar glueball $\mathinner { | { G _ { 0 ^ { + + } } } \rangle }$ ,a bare $q q$ （204号 scalar meson $\left| f _ { 0 } \right.$ ，or even $\pi \pi$ scattering states $| \pi \pi \rangle$ .We simplify the matter further by assuming that the two adjacent states mix most, then we can only consider a two-state system composed of the ground state scalar glueball $| G \rangle$ and its adjacent state,which could be of nature $| \pi \pi \rangle$ or $\left| f _ { 0 } \right.$ . This then yields the fitting model in Eq. (3.9) that we introduced previously.

Despite the fact that glueball correlation functions in the unquenched QCD acquire more complicated spectrum decomposition than the quenched case, the mass of the bare glueball states $| G \rangle$ can still be obtained by assuming the corresponding operators $\mathcal { O }$ couple weakly to other states. Therefore, it is naturally understood that the glueball spectrum in our full-QCD lattice studies is similar to that in the quenched approximation. The difference is still visible, however,and it is most evident in the scalar channel where one would expect that this weak coupling assumption is not valid anymore. We compare the results in the present study with the previous quenched and unquenched results in Table 7.

Table 7.We compare our results with previous results both from the quenched lattice QCD studies [8, 9] and the full-QCD study [13]. We average the masses of $E ^ { + + }$ and $T _ { 2 } ^ { + + }$ states to obtain the estimate of the $2 ^ { + + }$ glueball mass.   

<html><body><table><tr><td></td><td>mπ (MeV)</td><td>mo++ (MeV)</td><td>m2++ (MeV)</td><td>mo-+ (MeV)</td></tr><tr><td>Nf = 2</td><td>938</td><td>1397(25)</td><td>2367(35)</td><td>2559(50)</td></tr><tr><td></td><td>650</td><td>1480(52)</td><td>2380(61)</td><td>2605(52)</td></tr><tr><td>Nf = 2 +1 [13]</td><td>360</td><td>1795(60)</td><td>2620(50)</td><td></td></tr><tr><td>quenched [8]</td><td></td><td>1710(50)(80)</td><td>2390(30)(120)</td><td>2560(35)(120)</td></tr><tr><td>quenched [9]</td><td></td><td>1730(50)(80)</td><td>2400(25)(120)</td><td>2590(40)(130)</td></tr></table></body></html>

# 4Further study on the pseudoscalar channel

As presented in the last section,in the $A _ { 1 } ^ { - + }$ channel,we obtain the bare pseudoscalar glueball mass $m _ { A ^ { - + } } \sim 2 . 6$ GeV at the two pion masses,which is compatible with the quenched results. A subtle question is that, due to the anomalous $U _ { A } ( 1 )$ Ward identity,

$$
\partial _ { \mu } J _ { 5 } ^ { \mu } ( x ) = 2 m J _ { 5 } ( x ) - \frac { N _ { f } g ^ { 2 } } { 1 6 \pi ^ { 2 } } \epsilon _ { \mu \nu \rho \sigma } T r F ^ { \mu \nu } F ^ { \rho \sigma } ,
$$

where $g$ is the strong coupling constant, the gluonic oprator $\epsilon _ { \mu \nu \rho \sigma } F ^ { \mu \nu } F ^ { \rho \sigma }$ is usually called the topological charge density (up to a constant factor） and denoted by $q ( x )$ ， $q ( x )$ mixes with the flavor singlet pseudoscalar density $J _ { 5 } ( x )$ ， such that the gluonic pseudoscalar operator may have large overlap with the flavor singlet pseudoscalar meson (denoted by $\eta ^ { \prime }$ ） Since we are performing a $N _ { f } = 2$ unquenched lattice calculation, one may expect that $\eta ^ { \prime }$ can contribute to the pseudoscalar correlation functions. However，we do not observe the appearance of this state. So we would like to check the continuum form of the gluonic pseudoscalar (PS） operators involved in this work. Actually, in the construction of the gluonic pseudoscalar operators, only the spatially solid (instead of planar) Wilson loops (the last four prototypes in Fig.1) are used,

$$
\phi _ { \alpha } ^ { { A } _ { 1 } ^ { - + } } ( \mathbf { x } , t ) = \sum _ { R \in O } { c } _ { R } ^ { { A } _ { 1 } ^ { - + } } R e T r \left[ R \circ W _ { \alpha } ( \mathbf { x } , t ) - \mathcal { P } R \circ W _ { \alpha } ( \mathbf { x } , t ) \mathcal { P } ^ { - 1 } \right] ,
$$

where $R$ stands for each rotation operation in $O$ group, $c _ { R } ^ { A _ { 1 } }$ is the combinational coefficients corresponding to the $A _ { 1 }$ irreducible representation, $W _ { \alpha }$ is any of the four prototypes made up of a specifically smeared gauge links. According to the non-Abelian Stokes theorem [25],

a rectangle Wilson loop $P _ { \mu \nu } ^ { a \times b } ( x )$ of size $a \times b$ ，with $a , b$ small, can be expanded as

$$
\begin{array} { l } { { { \cal P } _ { \mu \nu } ^ { a \times b } ( x ) = { \bf 1 } + a b ( F _ { \mu \nu } ( x ) + \frac { 1 } { 2 } ( a D _ { \mu } + b D _ { \nu } ) F _ { \mu \nu } ( x ) } } \\ { { \ } } \\ { { \displaystyle ~ + \frac { 1 } { 1 2 } ( 2 a ^ { 2 } D _ { \mu } ^ { 2 } + 3 a b D _ { \mu } D _ { \nu } + 2 b ^ { 2 } D _ { \nu } ^ { 2 } ) F _ { \mu \nu } ( x ) } } \\ { { \ ~ + \frac { 1 } { 2 4 } ( a ^ { 3 } D _ { \mu } ^ { 3 } + 2 a ^ { 2 } b D _ { \mu } ^ { 2 } D _ { \nu } + 2 a b ^ { 2 } D _ { \mu } D _ { \nu } ^ { 2 } + b ^ { 3 } D _ { \nu } ^ { 3 } ) F _ { \mu \nu } ( x ) ) } } \\  { \ ~ + } \\ { { \ ( a b ) ^ { 2 } ( \frac { 1 } { 2 } F _ { \mu \nu } ^ { 2 } ( x ) + \frac { 1 } { 2 } F _ { \mu \nu } ( x ) ( a D _ { \mu } + b D _ { \nu } ) F _ { \mu \nu } ( x ) } } \\ { { \ ~ + \ \frac { 1 } { 2 4 } F _ { \mu \nu } ( x ) ( a ^ { 2 } D _ { \mu } ^ { 2 } + b ^ { 2 } D _ { \nu } ^ { 2 } ) F _ { \mu \nu } ( x ) ) } } \\ { { \ ~ + \ \frac { 1 } { 6 } ( a b ) ^ { 3 } F _ { \mu \nu } ^ { 3 } + { \cal O } ( ( a b ) ^ { 4 } ) . } } \end{array}
$$

For simplicity, the factor $i g$ is absorbed into the quantity $F _ { \mu \nu }$ . The small $a b$ expansion of $P _ { \pm \mu \pm \nu } ( x )$ is similar to Eq. 4.3 by replacing $a$ and $b$ with $\pm a$ and $\pm b$ ，respectively. Since the last four prototypes can be expressed as products of two rectangle Wilson loops, using the above relation one can obtain the leading term of the pseudoscalar operator,

$$
\phi _ { \alpha } ^ { A _ { 1 } ^ { - + } } ( { \bf x } , t ) \propto \epsilon _ { i j k } T r B _ { i } ( { \bf x } , t ) D _ { j } B _ { k } ( { \bf x } , t ) + O ( a _ { s } ^ { 2 } ) ,
$$

which is obviously different from the anomaly part of the anomalous WI, $\epsilon _ { \mu \nu \rho \sigma } F ^ { \mu \nu } ( x ) F ^ { \rho \sigma } ( x ) \propto$ （20 $\mathbf { E } ( x ) \cdot \mathbf { B } ( x )$ . This may imply that the two operators couple differently to specifc states. In order to clarify this,we would like to use $q ( x )$ as the operator for pseudoscalars and study their spectrum.The correlation function of $q ( x )$ is

![](images/887f61c30ef67bd9c9e4dca85d916f5e5e1468495966d23b83afe395e318db45.jpg)  
Figure 7. The correlation function $C _ { q } ( r )$ of topological charge density in terms of the four dimensional Euclidean distance (the left panel for $m _ { \pi } \sim 9 3 8$ MeV and the right panel for $m _ { \pi } \sim 6 5 0 \ \mathrm { M e V }$ Different curves correspond to $C _ { q } ( r )$ at different Wilson flow time $t = 0 . 2 , 0 . 3 , 0 . 4$ and 0.8.

$$
C _ { q } ( x - y ) = \langle q ( x ) q ( y ) \rangle .
$$

Since the topological susceptibility $\begin{array} { r } { \chi _ { t } = \frac { 1 } { V _ { 4 } } \int d ^ { 4 } x d ^ { 4 } y C _ { q } ( x - y ) > 0 } \end{array}$ （ $V _ { 4 }$ is the four-dimensional volume of the Euclidean spacetime), and $C _ { q } ( x - y ) < 0$ for $r = | | x - y | | > 0$ , intuitively

$C _ { q } ( x - y )$ can be expressed as

$$
C _ { q } ( x - y ) = A \delta ^ { 4 } ( x - y ) + \bar { C } _ { q } ( x - y ) ,
$$

where $C _ { q } ( x - y )$ is negative for $r > 0$ . On the Euclidean spacetime lattice with a finite lattice spacing,the delta function will show up a positive kernel with a width of a few lattice spacings, and $C _ { q } ( x - y )$ has a negative tail contributed from $C _ { q } ( x - y )$ .Because $q ( x )$ is a flavor singlet pseudoscalar operator, it is expected that $C _ { q } ( x - y )$ would be dominated by the contribution of the lowest pseudoscalar meson in the large $r$ range and can be parameterized as [26]

$$
\bar { C } _ { q } ( r ) = N \frac { m _ { \mathrm { P S } } } { 4 \pi ^ { 2 } r } K _ { 1 } ( m _ { \mathrm { P S } } r ) ,
$$

where $N$ is an irrelevant normalization factor, $m _ { \mathrm { P S } }$ is the mass of the lowest pseudoscalar, and $K ( z )$ is the modified Bessel function of second kind, whose asymptotic form at large $| z |$ is

$$
K _ { 1 } ( z ) \sim \sqrt { \frac { \pi } { 2 z } } e ^ { - z } ( 1 + \frac { 3 } { 8 z } ) , \quad | a r g \ z | < \frac { 3 } { 2 } \pi .
$$

Therefore,one can obtain $m _ { \mathrm { P S } }$ by fit the negative tail of $C _ { q } ( x - y )$ in the large $r$ range using the above functional form. This has been actually done by several lattice studies in both the quenched approximation [19] and full QCD calculations [18]. In the quenched approximation, the extracted $m _ { \mathrm { P S } } = 2 5 6 3 ( 3 4$ ） MeV is in good agreement with the pseudoscalar glueball mass $m _ { \mathrm { P S } } = 2 5 6 0$ (35) MeV. This is what should be, since the hadronic excitations of a pure gauge theory are only glueballs. In the full-QCD study with $N _ { f } = 2 + 1$ and pion masses close to the physical $m _ { \pi }$ ， $m _ { \mathrm { P S } }$ is obtained to be 1013(117) MeV,which is consistent with the mass of the physical $\eta ^ { \prime }$

In this work, we adopt the similar strategy to that in [18]. The topological charge density $q ( x )$ is defined by the spatial and temporal Wilson loops (plaquettes） as conventionally done. We use the gradient Wilson flow method as smearing schemes to optimize the behaviour of topological charge density correlator [18, 27]. The Wilson flow provides a reference energy scale $\scriptstyle { \frac { 1 } { \sqrt { 8 t } } }$ [28]. In practice, we use the code published by the BMW collaboration [29] to evaluate the topological charge density. Fig. 7 shows the topological charge density correlator for $m _ { \pi } \sim 9 3 8$ MeV and $m _ { \pi } \sim 6 5 0$ MeV at flow time $t = 0 . 2 , 0 . 3 , 0 . 4 , 0 . 8$ （204号 respectively. On our lattices,these $t$ values correspond to $\sqrt { 8 t } \mathrm { ~ \sim ~ } 0 . 1 5 , 0 . 1 8 , 0 . 2 1$ and 0.30 fm. As shown in the figures,at large flow time, the correlator is almost positive which implies that the gauge fields are over smeared. We then use the correlation function at flow time $t = 0 . 4$ ，which seems to have better signal-to-noise ratio and is smoother in our fitting range, to extract the $m _ { \mathrm { P S } }$ ：

We fit the negative tail region of $C ( \boldsymbol r )$ with Eq. 4.7,and the ftting range is determined by defining the effective mass $m _ { e f f } ( r )$ of $\eta ^ { \prime }$ through

$$
\frac { C ( r + \Delta r ) } { C ( r ) } = \frac { r } { r + \Delta r } \frac { K _ { 1 } ( m _ { e f f } ( r + \Delta r ) ) } { K _ { 1 } ( m _ { e f f } r ) } ,
$$

where we take $\Delta r \sim 0 . 0 5$ fm and $C ( \boldsymbol r )$ is averaged in $[ r , r + \Delta r ]$ ，then $m _ { e f f } ( r )$ is obtained by solving Eq. 4.9 numerically. Fig. 8 shows the effective mass plateaus for flow time $t = 0 . 2 , 0 . 3 , 0 . 4$ whose errors are estimated by jackknife method. Due to the small lattices and the periodic boundary condition we are using,we suffer from serious finite volume effects in fitting $m _ { \mathrm { P S } }$ since the positive kernel extends about $2 a _ { s }$ and the fitting range should be far enough from $L / 2 = 6 a _ { s }$ ：

![](images/61950d3c2ccbed0a37bc30ae20bda24f61eb963b822ec9a0cfcad751a5db7b98.jpg)  
Figure 8. The effective mass plateaus for Wilson flow time $t = 0 . 2 , 0 . 3 , 0 . 4$ at $m _ { \pi } \sim 9 3 8$ MeV (left panel) and $m _ { \pi } \sim 6 5 0$ MeV (right panel),respectively. The color bands show the fitted masses with errors and also the fit range.

Table 8 shows the fitted result of $m _ { \mathrm { P S } }$ at the two pion masses,which show explicitly the quark mass dependence of $m _ { \mathrm { P S } }$ . For the large uncertainties,we do not take the fitted values of $m _ { \mathrm { P S } }$ too seriously but obtain the impression that they are far below the pseudoscalar glueball mass in the quenched approximation and that in this study. Anyway, the $m _ { \mathrm { P S } }$ 's seem reasonable to some extent. Physically, the large $\eta ^ { \prime }$ mass is acquired through the interaction of sea quark loops and the mechanism can be described by the following expression,

$$
\frac { 1 } { q ^ { 2 } - m _ { \eta ^ { \prime } } ^ { 2 } } = \frac { 1 } { q ^ { 2 } - m _ { \pi } ^ { 2 } } \left( 1 + m _ { 0 } ^ { 2 } \frac { 1 } { q ^ { 2 } - m _ { \pi } ^ { 2 } } + m _ { 0 } ^ { 2 } \frac { 1 } { q ^ { 2 } - m _ { \pi } ^ { 2 } } m _ { 0 } ^ { 2 } \frac { 1 } { q ^ { 2 } - m _ { \pi } ^ { 2 } } + . . . \right) ,
$$

such that

$$
m _ { \eta ^ { \prime } } ^ { 2 } \approx m _ { \pi } ^ { 2 } + m _ { 0 } ^ { 2 } ,
$$

where $m _ { 0 } ^ { 2 }$ is related to the topological susceptibility $\chi _ { t }$ through Witten-Veneziano mechanism [30, 31] as

$$
m _ { 0 } ^ { 2 } = \frac { 4 N _ { f } } { f _ { \pi } ^ { 2 } } \chi _ { t } ,
$$

where $f _ { \pi }$ is the decay constant of $\pi$ . For our case of $N _ { f } ~ = ~ 2$ ，if we take the values $\chi _ { t } = ( 1 8 0 \mathrm { M e V } ) ^ { 4 }$ ， $f _ { \pi } \sim 1 5 0$ MeV for $m _ { \pi } \sim 6 5 0$ MeV and $f _ { \pi } \sim 2 0 0$ MeV for $m _ { \pi } \sim 9 3 8$ MeV, $m _ { 0 } ^ { 2 }$ is estimated to be approximately $( \mathrm { 6 1 0 M e V } ) ^ { 2 }$ and $( 4 6 0 \mathrm { M e V } ) ^ { 2 }$ , respectively. Thus the $\eta ^ { \prime }$ mass can be derived as $m _ { \eta ^ { \prime } } \sim 8 9 0$ MeV for $m _ { \pi } \sim 6 5 0 \ \mathrm { M e V }$ ，and $m _ { \eta ^ { \prime } } \sim 1 0 4 5$ MeV for $m _ { \pi } \sim 9 3 8$ MeV. These values are not far from the $m _ { \mathrm { P S } }$ 's we obtained.

Even though these are very coarse calculations, from which we can see that there does exist in the spectrum a flavor singlet $q q$ pseudoscalar meson corresponding to the $\eta ^ { \prime }$ meson in the real world, which can be accessed by the topological charge density operator. Along with the observation in the calculation of glueball spectrum, this proves to some extent that our operator for the pseudoscalar glueball couples very weakly to the $q q$ meson state but almost exclusively to the glueball states.

Table 8.The fitting details for $\eta ^ { \prime }$ meson mass from topological charge density correlator at $m _ { \pi } \sim 9 3 8$ MeV and $m _ { \pi } \sim 6 5 0$ MeV respectively.   

<html><body><table><tr><td>mπ</td><td>fit range(as)</td><td>mn'as</td><td>mn'(MeV)</td><td>x²/dof</td></tr><tr><td>938 MeV</td><td>3.74-5.92</td><td>0.856(21)</td><td>1481(36)</td><td>1.01</td></tr><tr><td>650 MeV</td><td>3.87-5.48</td><td>0.514(22)</td><td>890(38)</td><td>1.43</td></tr></table></body></html>

# 5 Summary and conclusions

The spectrum of the lowest-lying glueballs are investigated on the lattice with two flavors of degenerate quarks. We generate large ensembles of gauge configurations on anisotropic lattices at two pion masses, $m _ { \pi } \sim 6 5 0$ MeV and $m _ { \pi } \sim 9 3 8$ MeV. We focus on the ground states of the scalar， pseudoscalar and tensor glueballs, which are measured by gluonic operators constructed from different prototypes of Wilson loops. The variational method are applied to obtain the optimal operators which couple dominantly to the ground state glueballs.

In the tensor channel, we obtain the ground state mass to be 2.367(35) GeV and 2.380(61) GeV at $m _ { \pi } \sim 9 3 8$ MeV and 650 MeV, respectively. In the pseudoscalar channel, when we use the gluonic operator whose continuum limit has the form of $\epsilon _ { i j k } T r B _ { i } D _ { j } B _ { k }$ ， we obtain the ground state mass to be 2.559(50) GeV and 2.605(52) GeV at the two pion masses. These results are in agreement with the corresponding glueball masses in the quenched approximation and show little dependence of pion masses. In the scalar channel, the ground state masses extracted from the correlation functions of gluonic operators are determined to be around 1.4-1.5 GeV, which are close to the ground state masses from the correlation functions of the quark bilinear operators. In all the channels considered, the spectrum is similar to the quenched case and the mixing between glueballs and conventional mesons will be explored in the future.

We also investigate the pseudoscalar channel using the topological charge density as the interpolation field operator, which are defined through Wilson loops and smeared by the Wilson flow technique. The masses of the lowest state derived in this way are much lighter (around 1GeV） and compatible with the expected masses of the flavor singlet $q q$ （204 meson. This provides a strong hint that the operator $\epsilon _ { i j k } T r B _ { i } D _ { j } B _ { k }$ and the topological charge density (proportional to $T r \mathbf { E \cdot B }$ ） couple very differently to the glueball states and $q q$ mesons.

Admittedly the lattice volume we used is relatively small and the continuum limit remains to be taken, our current results are still helpful to clarify some aspects of unquenched effects of glueballs and serves as a starting point for further future studies.

Acknowledgements: The numerical calculations are carried out on Tianhe-1A at the National Supercomputer Center (NSCC) in Tianjin and the GPU cluster at Hunan Normal University. This work is supported in part by the National Science Foundation of China (NSFC)under Grants No. 11575196,No. 11575197,No. 11335001,and No. 11405053. Y.C., Z.L. and C.L. also acknowledge the support of NSFC under No. 11261130311 (CRC 110 by DFG and NSFC). Y.C. thanks the support by the CAS Center for Excellence in Particle Physics (CCEPP). C.L. is also funded in part by National Basic Research Program of China (973 Program） under code number 2015CB856700.

# References

[1] R. Jafe and K. Johnson, Unconventional states of confined quarks and gluons, Physics Letters B 60 (1976),no.2 201 - 204.   
[2] J. Cornwall and A. Soni, Glueballs as bound states of massive gluons, Physics Letters B 12 (1983),no.4 431 - 435.   
[3] W.-S. Hou and A. Soni, Low Lying Bound States of Three Gluons: Their Spectrum, Production and Decay Properties, Phys. Rev. D29 (1984) 101.   
[4] R.C. Brower, S. D.Mathur, and C.-I. Tan, Glueball spectrum for QCD from AdS supergravity duality, Nucl. Phys. B587 (2000) 249-276, [hep-th/0003115].   
[5] A.-l. Zhang and T.G. Steele, Instanton and higher loop perturbative contributions to the QCD sum rule analysis of pseudoscalar gluonium, Nucl. Phys. A728 (2003) 165-181, [hep-ph/0304208].   
[6] S. Narison, QCD tests of the puzzling scalar mesons, Phys. Rev. D73 (2006) 114024, [hep-ph/0512256].   
[7] C. J. Morningstar and M. Peardon, Effcient glueball simulations on anisotropic lattices, Phys.Rev.D 56（Oct,1997) 4043-4061.   
[8] C. J. Morningstar and M. J. Peardon, The Glueball spectrum from an anisotropic lattice study, Phys. Rev. D60 (1999) 034509, [hep-lat/9901004]. [9] Y. Chen et al., Glueball spectrum and matrix elements on anisotropic lattices, Phys. Rev. D73 (2006) 014516, [hep-lat/0510074].   
[10] TXL,T(X)L,G. S.Bali,B.Bolder,N. Eicker,T. Lippert,B. Orth,P. Ueberholz, K.Schilling,and T. Struckmann, Static potentials and glueball masses from QCD simulations with Wilson sea quarks, Phys. Rev. D62 (2000) 054503, [hep-lat/0003012].   
[11] UKQCD,A. Hart and M. Teper, On the glueball spectrum in O(a) improved lattice QCD, Phys. Rev. D65 (2002) 034502, [hep-1at/0108022].   
[12] UKQCD,C. M. Richards, A. C. Irving, E. B. Gregory, and C. McNeile, Glueball mass measurements from improved staggered fermion simulations, Phys. Rev. D82 (2010) 03450 [arXiv:1005.2473].   
[13] E. Gregory, A. Irving, B. Lucini, C. McNeile,A. Rago, C. Richards,and E. Rinaldi, Towal the glueball spectrum from unquenched lattice QCD, JHEP 1O (2012) 170, [arXiv:1208.1858].   
[14] CLQCD, L.-C. Gui, Y. Chen, G. Li, C. Liu, Y.-B. Liu, J.-P. Ma, Y.-B. Yang, and J.-B. Zhang, Scalar Glueball in Radiative J/ψ Decay on the Lattice, Phys. Rev. Lett. 110 (2013), no. 2 021601,[arXiv:1206.0125].   
[15] CLQCD, Y.-B. Yang, L.-C. Gui, Y. Chen, C. Liu, Y.-B. Liu, J.-P. Ma, and J.-B. Zhang, Lattice Study of Radiative J/ Decay to a Tensor Glueball, Phys. Rev. Lett.1l1 (2013), no. 9 091601, [arXiv: 1304.3807].   
[16] BESIII, M. Ablikim et al., Partial wave analysis of $J / \psi  \gamma \eta \eta$ , Phys. Rev. D87 (2013), no. 9 092009,[arXiv: 1301.0053]. [Erratum: Phys. Rev.D87,no.11,119901(2013)].   
[17] BESIII, M. Ablikim et al., Observation of pseudoscalar and tensor resonances in $J / \psi  \gamma \phi \phi$ , Phys. Rev. D93 (2016), no. 11 112011, [arXiv:1602.01523].   
[18] JLQCD,H. Fukaya, S. Aoki, G. Cossu, S. Hashimoto, T. Kaneko,and J. Noaki, $\eta ^ { \prime }$ meson mass from topological charge density correlator in QCD, Phys. Rev. D92 (2015), no. 11 111501,[arXiv:1509.00944].   
[19] A. Chowdhury, A. Harindranath,and J. Maiti, Correlation and localization properties of topological charge density and the pseudoscalar glueball mass in SU(3) lattice Yang-Mills theory, Phys. Rev. D91 (2015), no. 7 074507,[arXiv:1409.6459].   
[20] S.-q. Su, L.-m. Liu, X. Li, and C. Liu, A Numerical study of improved quark actions on anisotropic lattices, Int. J. Mod. Phys. A21 (2006) 1015-1032, [hep-lat/0412034].   
[21] G. P. Lepage and P.B. Mackenzie, Viability of lattice perturbation theory, Phys. Rev. D 48 (Sep,1993） 2250-2264.   
[22] CP-PACS, T. Umeda et al., Two flavors of dynamical quarks on anisotropic latices, Phys. Rev. D68 (2003) 034503, [hep-lat/0302024].   
[23] T.R. Klassen, The Anisotropic Wilson gauge action, Nucl. Phys. B533 (1998) 557-575, [hep-lat/9803010].   
[24] R. G. Edwards, B. Joo,and H.-W. Lin, Tuning for Three-flavors of Anisotropic Clover Fermions with Stout-link Smearing, Phys. Rev. D78 (2008) 054501, [arXiv:0803.3960].   
[25] Yu. A. Simonov, Cluster Expansion, Nonabelian Stokes Theorem and Magnetic Monopoles, Sov. J. Nucl. Phys.50 (1989) 134. [Yad. Fiz.50,213(1989)].   
[26] E.V. Shuryak and J. J. M. Verbaarschot, Screening of the topological charge in a correlated instanton vacuum, Phys. Rev. D 52 (Jul, 1995) 295-306.   
[27] P. J. Moran and D.B. Leinweber, Impact of Dynamical Fermions on QCD Vacuum Structure, Phys. Rev. D78 (2008) 054506, [arXiv:0801.2016].   
[28] M. Lüscher, Properties and uses of the Wilson flow in lattice QCD, JHEP O8 (2010) 071, [arXiv: 1006 .4518]. [Erratum: JHEP03,092(2014)].   
[29] S. Borsanyi et al., High-precision scale setting in lattice QCD, JHEP O9 (2012) 010, [arXiv:1203.4469].   
[30] E. Witten, Current Algebra Theorems for the U(1) Goldstone Boson, Nucl. Phys. B156 (1979) 269-283.   
[31] G. Veneziano, U(1) without instantons, Nuclear Physics B 159 (1979), no.1 213 - 224.