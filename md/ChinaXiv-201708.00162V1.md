# Exact result on the supercurrent through a superconductor/quantum-dot/superconductor junction

Wei Li，Yu Zhu,and Tsung-han Lin   
State Key Laboratory for Mesoscopic Physics and   
Department of Physics, Peking University, Beijing 100871, China

# Abstract

Wepresentan analytical result forthe supercurrent across a superconductor/quantum-dot/superconductor junction. By converting the current integration into a special contour integral, we can express the current as a sum of the residues of poles. These poles are real and give a natural definition of the Andreev bound states. We also use the exact result to explain some features of the supercurrent transport behavior.

PACS numbers: 74.50.+r, 73.40.Gk, 73.20.-b, 73.63.Kv.

Introduction. The mesoscopic superconductor/quantum-dot/superconductor (S-QD-S) junction is a typical structure to study the phase coherent current transport in mesoscopic hybrid systems [1]. When using Keldysh Green function technique [2] to evaluate the current across the S-QD-S junction, the usual method demands a numerical integration and faces the problem of explaining some features of the current transport behavior [3]. In this paper, we employ a new method to analytically compute the current across the S-QD-S junction in the absence of voltage bias, and use the analytical results to explain some features of current transport properties.

Model and Hamiltonian. In the system under consideration, a quantum dot defined in a 2-dimensional electron gas (2DEG) is coupled to two BCS superconducting leads. We model this system by the Hamiltonian

$$
\hat { H } = \hat { H } _ { L } + \hat { H } _ { d } + \hat { H } _ { R } + \hat { H } _ { T } \ ,
$$

where

$$
\hat { H } _ { L } = \sum _ { k , \sigma } \epsilon _ { k } ^ { L } a _ { k \sigma } ^ { \dagger } a _ { k \sigma } + \sum _ { k } [ \Delta _ { L } a _ { k \uparrow } ^ { \dagger } a _ { - k \downarrow } ^ { \dagger } + \Delta _ { L } ^ { * } a _ { - k \downarrow } a _ { k \uparrow } ]
$$

$$
\hat { H } _ { d } = \epsilon _ { 0 } ( d _ { \uparrow } ^ { \dagger } d _ { \uparrow } + d _ { \downarrow } ^ { \dagger } d _ { \downarrow } ) ~ ,
$$

$$
\hat { H } _ { R } = \sum _ { p , \sigma } \epsilon _ { p } ^ { R } b _ { p \sigma } ^ { \dagger } b _ { p \sigma } + \sum _ { p } [ \Delta _ { R } b _ { p \uparrow } ^ { \dagger } b _ { - p \downarrow } ^ { \dagger } + \Delta _ { R } ^ { * } b _ { - p \downarrow } b _ { p \uparrow } ] \mathrm { ~ , ~ }
$$

are the isolated (unperturbed) Hamiltonians of the left superconductor, the quantum dot, and the right superconductor, respectively.

We consider only a quantum dot with a negligible intra-dot Coulomb interaction. The reason is that we want to focus on the superconducting proximity effct on the QD,which is due to Andreev reflections; whereas a large charging effect caused by intra-dot Coulomb repulsion suppresses the transport mediated by Andreev process [4,5]. Study on the competition of a medium intra-dot Coulomb interaction with Andreev reflections in S-QD-S junction will be carried on in the coming work. Furthermore, we consider only one single energy level inside the QD. The generalization to QDs with several energy levels is straightforward.

The tunneling term

$$
\hat { H } _ { T } = \sum _ { k , \sigma } [ L _ { k } a _ { k \sigma } ^ { \dagger } d _ { \sigma } + c . c . ] + \sum _ { p , \sigma } [ R _ { p } b _ { k \sigma } ^ { \dagger } d _ { \sigma } + c . c . ] \ ,
$$

describes the electron-transfer between the QD and the leads.

Current Formula. The current flowing across the junction is [6]

$$
I = - \frac { 2 e \Gamma } { \hbar } \mathrm { T r } \{ \mathrm { R e } \int _ { - \infty } ^ { + \infty } \frac { d \omega } { 2 \pi } \left[ \mathbf { G } _ { d } ^ { r } \left( \omega \right) \mathbf { g } _ { L } ^ { < } \left( \omega \right) + \mathbf { G } _ { d } ^ { < } \left( \omega \right) \mathbf { g } _ { L } ^ { a } \left( \omega \right) \right] \} \ ,
$$

where ${ \bf g } _ { L }$ ， $\mathbf { G }$ are the Keldysh Green functions of the left superconductor and the QD in Nambu space [2]. The retarded Green function of the superconductor is

$$
\begin{array} { r } { \mathbf { g } _ { L / R } ^ { r } \left( \omega \right) = ( - i \pi ) \rho _ { L / R } ( \omega + i 0 ^ { + } ) \left( \begin{array} { l l } { 1 } & { \frac { \Delta _ { L / R } } { \omega } } \\ { \frac { \Delta _ { L / R } ^ { * } } { \omega } } & { 1 } \end{array} \right) , } \end{array}
$$

where $\begin{array} { r } { \rho _ { L / R } ( \omega ) = \frac { | \omega | } { \sqrt { \omega ^ { 2 } - \Delta _ { L / R } ^ { 2 } } } } \end{array}$ is the density of states (DOS) of a BCS superconductor. After solving the matrix Dyson equation, we obtain the retarded Green function of the QD:

$$
\mathbf { G } _ { d } ^ { r } \left( \omega \right) = \frac { 1 } { D \left( \omega \right) } \left( \begin{array} { c c } { g ^ { r } \left( \omega \right) _ { 2 2 } ^ { - 1 } - \Sigma ^ { r } \left( \omega \right) _ { 2 2 } } & { \Sigma ^ { r } \left( \omega \right) _ { 1 2 } } \\ { \Sigma ^ { r } \left( \omega \right) _ { 2 1 } } & { g ^ { r } \left( \omega \right) _ { 1 1 } ^ { - 1 } - \Sigma ^ { r } \left( \omega \right) _ { 1 1 } } \end{array} \right) \mathrm { ~ , ~ }
$$

where

$$
\mathbf { g } ^ { r } \left( \omega \right) = \left( \begin{array} { c c } { \frac { 1 } { \omega - \epsilon _ { 0 } + i 0 ^ { + } } } & { 0 } \\ { 0 } & { \frac { 1 } { \omega + \epsilon _ { 0 } + i 0 ^ { + } } } \end{array} \right)
$$

is the unperturbed retarded Green function of the QD. The QD's self-energy

$$
\Sigma ( \omega ) = \frac { \Gamma } { 2 \pi } { \bf g } _ { L } \left( \omega \right) + \frac { \Gamma } { 2 \pi } { \bf g } _ { R } \left( \omega \right) \ ,
$$

describes the proximity effect of superconductors on the QD; here we have used the wide band-width approximation [7]. $D ( \omega )$ in Eq. [8] is the determinant of the matrix $\left( \mathbf { g } ^ { r - 1 } - \Sigma ^ { r } \right)$

$$
\begin{array} { r } { D ( \omega ) = [ g ^ { r } ( \omega ) _ { 1 1 } ^ { - 1 } - \Sigma ^ { r } ( \omega ) _ { 1 1 } ] [ g ^ { r } ( \omega ) _ { 2 2 } ^ { - 1 } - \Sigma ^ { r } ( \omega ) _ { 2 2 } ] - \Sigma ^ { r } ( \omega ) _ { 1 2 } \Sigma ^ { r } ( \omega ) _ { 2 1 } } \end{array}
$$

Choice of Integration Contour. The supercurrent formula Eq.[6] can be expressed as

$$
I _ { s c } = - \frac { 4 e \Gamma } { \hbar } \mathrm { R e } \{ \int _ { - \infty } ^ { + \infty } \frac { d \omega } { 2 \pi } [ G _ { d } ^ { r } \left( \omega \right) _ { 1 2 } g _ { L } ^ { < } \left( \omega \right) _ { 2 1 } + G _ { d } ^ { < } \left( \omega \right) _ { 1 2 } g _ { L } ^ { a } \left( \omega \right) _ { 2 1 } ] \} \ .
$$

In order to avoid calculating this integration numerically, we shall transform it into a contour integral. First, using the fluctuation-dissipation theorem $G ^ { < } \left( \omega \right) = \left[ G ^ { a } \left( \omega \right) - G ^ { r } \left( \omega \right) \right] f ( \omega )$ ， where $G$ stands for any Green function in the equilibrium state and $f ( \omega )$ is the Fermi distribution function, we have

$$
I _ { s c } = \frac { 4 e \Gamma } { \hbar } \mathrm { R e } \{ \int _ { - \infty } ^ { + \infty } \frac { d \omega } { 2 \pi } [ G _ { d } ^ { r } ( \omega ) _ { 1 2 } g _ { L } ^ { r } ( \omega ) _ { 2 1 } f ( \omega ) - G _ { d } ^ { a } ( \omega ) _ { 1 2 } g _ { L } ^ { a } ( \omega ) _ { 2 1 } f ( \omega ) ] \} .
$$

Then we make a change of the integration variable $\omega \to \omega - i 0 ^ { + }$ for $G _ { d } ^ { r } \left( \omega \right) _ { 1 2 } g _ { L } ^ { r } \left( \omega \right) _ { 2 1 } f ( \omega )$ （204号 and $\omega  \omega + i 0 ^ { + }$ for $G _ { d } ^ { a } \left( \omega \right) _ { 1 2 } g _ { L } ^ { a } \left( \omega \right) _ { 2 1 } f ( \omega )$ to divide $I _ { s c }$ into two integrals along different paths:

$$
\begin{array} { c } { { \displaystyle = \frac { 4 e \Gamma } { \hbar } \operatorname { R e } \bigl \{ \int _ { - \infty + i 0 ^ { + } } ^ { + \infty + i 0 ^ { + } } \frac { d \omega } { 2 \pi } [ G _ { d } ^ { r } \left( \omega - i 0 ^ { + } \right) _ { 1 2 } g _ { L } ^ { r } \left( \omega - i 0 ^ { + } \right) _ { 2 1 } f ( \omega - i 0 ^ { + } ) ] } } \\ { { \displaystyle - \int _ { - \infty - i 0 ^ { + } } ^ { + \infty - i 0 ^ { + } } [ G _ { d } ^ { a } \left( \omega + i 0 ^ { + } \right) _ { 1 2 } g _ { L } ^ { a } \left( \omega + i 0 ^ { + } \right) _ { 2 1 } f ( \omega + i 0 ^ { + } ) ] \ , } } \end{array}
$$

Since the above two integrands are actually the same, we define a new integrand equal to them:

$$
\begin{array} { r l r } & { } & { J ( \omega ) \equiv G _ { d } ^ { r } \left( \omega - i 0 ^ { + } \right) _ { 1 2 } g _ { L } ^ { r } \left( \omega - i 0 ^ { + } \right) _ { 2 1 } f ( \omega - i 0 ^ { + } ) } \\ & { } & { = G _ { d } ^ { a } \left( \omega + i 0 ^ { + } \right) _ { 1 2 } g _ { L } ^ { a } \left( \omega + i 0 ^ { + } \right) _ { 2 1 } f ( \omega + i 0 ^ { + } ) } \end{array}
$$

Thus the current integration can be rewritten into a contour integral in the complex- $\omega$ plane:

$$
I _ { s c } = \frac { 4 e \Gamma } { \hbar } \operatorname { R e } [ ( \int _ { - \infty + i 0 ^ { + } } ^ { + \infty + i 0 ^ { + } } - \int _ { - \infty - i 0 ^ { + } } ^ { + \infty - i 0 ^ { + } } ) \frac { d \omega } { 2 \pi } J ( \omega ) ] \ = \frac { 4 e \Gamma } { \hbar } \operatorname { R e } \int _ { c } J ( \omega ) \frac { d \omega } { 2 \pi } .
$$

The integration path $\begin{array} { r } { C = \int _ { - \infty + i 0 ^ { + } } ^ { + \infty + i 0 ^ { + } } + \int _ { + \infty - i 0 ^ { + } } ^ { - \infty - i 0 ^ { + } } } \end{array}$ is losecoorieset the real $\omega$ axis. The integral can then be evaluated analytically using Cauchy's theorem.

This choice of the integration contour has the advantage of leaving all (infinitely many) the poles at $\begin{array} { r } { \omega = i \frac { ( 2 n + 1 ) \pi } { \beta } } \end{array}$ arising from $f ( \omega )$ outside the contour,thus avoid the calculation of the summation over all the Matsubara frequencies ( $\begin{array} { r } { \omega = i \frac { ( 2 n + 1 ) \pi } { \beta } ) } \end{array}$ ：

Poles and definition of Andreev bound state. Since the current is proportional to the sum of the residues of the integrand $J ( \omega )$ inside the contour $C$ ， only real poles of $J ( \omega )$ contribute. For $J ( \omega ) \equiv { G _ { d } ^ { r } } \left( \omega - i 0 ^ { + } \right) _ { 1 2 } g _ { L } ^ { r } \left( \omega - i 0 ^ { + } \right) _ { 2 1 } f ( \omega )$ , there are only two pairs of real poles: $\omega = \pm \Delta$ and $\omega = \pm \epsilon ^ { * } ( | \epsilon ^ { * } | < \Delta )$ . The poles at $\omega = \pm \Delta$ originate from the singularities of the DOS of the BCS superconductors.

The poles at $\omega = \pm \epsilon ^ { * }$ come from the QD's Green function and are two real roots of the equation $D ( \omega ) = 0$ inside the gap（ $| \epsilon ^ { * } | < \Delta$ ). These two poles give the positions of the quasi-particle states of the QD inside the gap. The fact that they are real indicates that these two quasi-particle states are exactly bound states, usually called the Andreev bound states (ABS).

Before coupling to the superconductors, the unperturbed QD has a bound state at $\epsilon _ { 0 }$ （20 for the electron spectrum and one at $- \epsilon _ { 0 }$ for the hole spectrum. After coupled to the superconductors, through the electron-transfer with the two superconductors via Andreev process, the electron part and the hole part of the QD's Green function are coupled together, and give rise to signifcant modifications to the QD's energy spectrum: the original bound state at $\epsilon _ { 0 }$ for electron (or $- \epsilon _ { 0 }$ for hole) renormalizes into two symmetrical bound states at （2 $\pm \epsilon ^ { * }$ for both electron and hole spectrum.

To express $\epsilon ^ { * }$ as the algebraic function of $\epsilon _ { 0 }$ ， $\phi$ and $\Gamma$ , we transform the equation $D ( \omega ) = 0$

into a quartic equation of $x = \epsilon ^ { * 2 }$

$$
\begin{array} { c } { { x ^ { 4 } - ( 2 A ^ { 2 } - 4 \Gamma ^ { 2 } ) x ^ { 3 } + ( A ^ { 4 } + 2 \Delta ^ { 2 } B ^ { 2 } - 4 \Gamma ^ { 2 } \Delta ^ { 2 } ) x ^ { 2 } + ( 2 A ^ { 2 } \Delta ^ { 2 } B ^ { 2 } ) x + ( \Delta ^ { 2 } B ^ { 2 } ) ^ { 2 } = 0 } } \\ { { { } } } \\ { { A ^ { 2 } = \Delta ^ { 2 } + \epsilon _ { 0 } ^ { 2 } + \Gamma ^ { 2 } , \ B ^ { 2 } = \epsilon _ { 0 } ^ { 2 } + \Gamma ^ { 2 } \cos ^ { 2 } { \frac { \phi } { 2 } } \ ; \quad x = \epsilon ^ { * 2 } < \Delta ^ { 2 } . } } \end{array}
$$

This quartic equation of $x$ has only one positive real solution $x _ { 0 }$ less than $\Delta ^ { 2 }$ ： $\pm \epsilon ^ { * } = \pm \sqrt { x _ { 0 } }$ The quartic equation is easy to solve algebraically; but we omit the lengthy solution. The dependence of $\epsilon ^ { * }$ on $\epsilon _ { 0 }$ ， $\phi$ and $\Gamma$ is shown graphically in [3].

Residues and analytical result of the current. The current is obtained by adding up the residues of the four poles:

$$
I _ { s c } = \frac { 4 e \Gamma } { \hbar } \mathrm { I m } [ \sum _ { i = 1 } ^ { 4 } \mathrm { R e } s J ( \omega _ { i } ) ] ,
$$

where $\omega _ { i } = \pm \epsilon ^ { * } , \pm \Delta$ . The residues of $J$ at $\epsilon ^ { * }$ and $- \epsilon ^ { * }$ are :

$$
\begin{array} { l } { { \displaystyle \mathrm { R e } \mathrm { s } _ { \omega = \pm \epsilon ^ { * } } J ( \omega ) = \operatorname* { l i m } _ { \omega  \pm \epsilon ^ { * } } [ \frac { \omega - ( \pm \epsilon ^ { * } ) } { D ( \omega ) } \Sigma ^ { r } ( \omega - i 0 ^ { + } ) _ { 1 2 } g _ { L } ^ { r } ( \omega - i 0 ^ { + } ) _ { 2 1 } f ( \omega ) ] } , }  \\ { { \displaystyle \mathrm { s } _ { \omega = \pm \epsilon ^ { * } } J ( \omega ) ] = \mp \frac { \Gamma } { 2 } \frac { \Delta ^ { 2 } } { \Delta ^ { 2 } - \epsilon ^ { * 2 } } \frac { f ( \pm \epsilon ^ { * } ) \sin \phi } { 2 \epsilon ^ { * } [ ( \Delta ^ { 2 } - \epsilon ^ { * 2 } ) + \frac { \Gamma } { \sqrt { \Delta ^ { 2 } - \epsilon ^ { * 2 } } } ( 2 \Delta ^ { 2 } - \epsilon ^ { * 2 } ) + \frac { \Gamma ^ { 2 } } { \Delta ^ { 2 } - \epsilon ^ { * 2 } } \Delta ^ { 2 } \sin ^ { 2 } \phi ] } \frac { f ( \omega ) } { 2 \Delta ^ { 2 } } \mathrm { s } _ { \mathrm { t a n d } } ^ { 2 } . } }  \end{array}
$$

The residues at $\pm \Delta$ turn out to be zero since

$$
{ \cal D } ( \pm \Delta ) = \infty , \qquad { \frac { 1 } { { \cal D } ( \pm \Delta ) } } = 0 .
$$

Thus the supercurrent is simply

$$
I _ { s c } = \frac { e \Gamma ^ { 2 } } { \hbar } \frac { \Delta ^ { 2 } } { \Delta ^ { 2 } - \epsilon ^ { * 2 } } \frac { \sin \phi \operatorname { t a n h } \frac { \beta \epsilon ^ { * } } { 2 } } { \epsilon ^ { * } [ ( \Delta ^ { 2 } - \epsilon ^ { * 2 } ) + \frac { \Gamma } { \sqrt { \Delta ^ { 2 } - \epsilon ^ { * 2 } } } ( 2 \Delta ^ { 2 } - \epsilon ^ { * 2 } ) + \frac { \Gamma ^ { 2 } } { \Delta ^ { 2 } - \epsilon ^ { * 2 } } \Delta ^ { 2 } \sin ^ { 2 } \frac { \phi } { 2 } ] } .
$$

where $\phi = \phi _ { R } - \phi _ { L }$ is the phase difference of the two superconductors.

Discussion. In addition to the splitting of the original energy level $\epsilon _ { 0 }$ into the two ABS,another modification to the QD's energy spectrum is that the QD begins to have a continuum energy spectrum outside the gap. In fact, one way to calculate the current integral ( $\begin{array} { r } { I _ { s c } = - \frac { 4 e ! } { \hbar } \operatorname { R e } \{ \int _ { - \infty } ^ { + \infty } \frac { d \omega } { 2 \pi } [ G _ { d } ^ { r } \left( \omega \right) _ { 1 2 } g _ { L } ^ { < } \left( \omega \right) _ { 2 1 } + G _ { d } ^ { < } \left( \omega \right) _ { 1 2 } g _ { L } ^ { a } \left( \omega \right) _ { 2 1 } ] \} } \end{array}$ ）is to divide the QD's spectrum into the continuum part ( $| \omega | > \Delta$ ）and the discrete part（ $| \omega | < \Delta$ ），and then evaluate their contributions to the current separately. However, this method involves a numerical integration and faces the problem of explaining why the peaks at $\omega = \pm \Delta$ in （20 $I _ { c o n t i n u u m }$ vs. $\epsilon _ { 0 }$ curve and in $\boldsymbol { I _ { d i s c r e t e } }$ vs. $\epsilon _ { 0 }$ curve exactly cancel out when the two parts add up to give the total current, see Fig.1.

In contrast, from our approach, this exact cancellation can be shown naturally. The current is obtained by adding the residues of the four poles. Since the residues at $\pm \Delta$ vanish, the total current curve has no peaks arising from the DOS singularities of the superconductors.

Now only residues at $\pm \epsilon ^ { * }$ contribute to the total current and give rise to a sharp peak in （20 $I$ vs. $\epsilon _ { 0 }$ curve at $\epsilon _ { 0 } = 0$ . The reason for the appearance of the peak at $\epsilon _ { 0 } = 0$ is that when $\epsilon _ { 0 } = 0$ , the upper and the lower ABS have same phase. As $\epsilon _ { 0 }$ departs from the Fermi level, the phase of the upper and lower ABS begins to differ and this difference severely reduces the supercurrent across the junction. Fig.2 shows the central peaks at different $\Gamma$ , the peaks broaden when $\Gamma$ increases.

A direct application of this result is a way to align the energy level of the QD to the Fermi level of the superconductor in the actual experiment: when changing the gate voltage, the state with the maximum supercurrent is at $\epsilon _ { 0 } = 0$ ：

Conclusion. In summary, we have calculated analytically the supercurrent across an SQD-S junction. The central results are Eq.[18] and Eq.[21]. They give the analytical result of both the positions of ABS and the supercurrent. We show two additional advantages of our method: (1) It presents a natural definition of the Andreev bound states inside the QD. (2) It explains the disappearance of the peaks at the gap edge in $I$ vS. $\epsilon _ { 0 }$ curve. The method devised in the paper can also be used in computing other equilibrium properties of the superconductor-normal hybrid systems.

We thank Q.F. Sun for his stimulating remarks. This work is supported by National Science Foundation of China under the Grant No. 1Oo74001.

# REFERENCES

[1] A.L. Yeyati, J.C. Cuevas, A. Lopez-Davalos, and A. Martin-Rodero, Phys. Rev. B 55, R6137 (1997).   
[2] L.V. Keldysh, Zh. Eksp. Theor. Fiz.47,1515 (1964) [Sov. Phys.-JETP 20,1018 (1965)}; C. Caroli, R. Combescot, P. Nozieres, and D. Saint-James, J. Phys. C 4, 916 (1971).   
[3] Yu Zhu, Qing-feng Sun, and Tsung-han Lin, J. Phys. Condens. Matter. 13, 8783(2001).   
[4] D.C. Ralph, C. T. Black and M. Tinkham, Phys. Rev. Lett. 78,4087 (1997).   
[5] K. Kang, Phys. Rev. B 57,11891 (1998).   
[6] Qing-feng Sun， Bai-geng Wang, Jian Wang， amd Tsung-han Lin， Phys. Rev, B 61, 4754(2000).   
[7] N.S. Wingreen, K.W. Jacobsen, J.W. Wilkins, Phys. Rev. B 40,11834(1989)

# FIGURECAPTIONS

Fig. 1 Supercurrent vs. $\epsilon _ { 0 }$ when $\Gamma = 0 . 1$ and $\textstyle \phi = { \frac { \pi } { 2 } }$ . The dash line is from discrete spectrum, and the dot line from continuum spectrum. The solid line is total current. Note that the continuum spectrum contributes negative current.   
Fig. 2 Supercurrent vs. $\epsilon _ { \mathrm { 0 } }$ with $\begin{array} { r } { \phi = \frac { \pi } { 2 } } \end{array}$ for different $\Gamma$ . Different curves are for $\Gamma = 0 . 1$ ，0.3, 1.0, respectively. Note the broadening effect as $\Gamma$ increases.

![](images/235371cdfffa18810666a6024aefc81db9cf8b01576ed865ae74f09811673041.jpg)  
Fig.1.

![](images/1332b26c8ddd51b8e7ae7ed12f4a9beaac689d7430a2417283e280e656a661df.jpg)  
Fig.2.