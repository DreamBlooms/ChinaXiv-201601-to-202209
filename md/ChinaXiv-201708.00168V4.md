# Exact Solution of the Generalized Rabi Model

Degang Zhang $^ { 1 , 2 }$ College of Physics and Electronic Engineering, Sichuan Normal University， Chengdu 610101, China $\mathcal { Z }$ Institute of Solid State Physics，Sichuan Normal University，Chengdu 610101，China

The generalized Rabi model is exactly solved by employing the unitary transformation method in the occupation number representation.The analytical expressons for the complete energy spectrum consisting of two sub-energy spectra are presented in the whole range of allthe physical parameters. Each energy level possesses twofold degeneracy and is determined by the parameter in the unitary transformation，which obeys a highly nonlinear equation. The corresponding eigenfunction is a convergent infinite series in terms of these physical parameters.Due to the level crossings between the neighboring eigenstates at certain parameter values, such the degeneracies could lead to novel physical phenomena in these quantum systems with the light-matter interaction.

PACS numbers:03.65.Ge,02.30.Ik,42.50.Pq

The Rabi model describes a two-level system coupled with a single bosonic mode[1]. Such a simplest interacting quantum model has had wide applications in many fields of physics,e.g. atomic physics [2],quantum optics [3], trapped ions [4,5], quantum dots [6], superconducting qubits [7,8,9], cold atoms [10], and etc.. It is also expected to be the theoretical basis for quantum information and quantum technology [11-14].

A generalized Rabimodel usually hastheHamiltonian [15]

$$
H = \omega a ^ { + } a + g ( a ^ { + } + a ) \sigma _ { x } + \lambda \sigma _ { z } + \epsilon \sigma _ { x } ,
$$

where $\sigma _ { x }$ and $\sigma _ { z }$ are the Pauli matrices for the two-level system with level splitting $2 \lambda$ ， $a ^ { + }$ and $a$ are the creation and annihilation operators for the single bosonic mode with frequency $\omega$ ,respectively, the light-matter interaction is controlled by the coupling parameter $g$ ，and the last term $\epsilon \sigma _ { x }$ is the driving term which breaks the $Z _ { 2 }$ symmetry and leads to tunnelling between the two levels. We note that the competition between $g$ and $\omega$ produces the different experimental regimes.When $g / \omega$ is small, by applying the rotating-wave approximation, the Rabi model（1）with $\epsilon = 0$ leads to the so-called Jaynes-Cummings model [16],which is relevant to most experimental regimes. Because the Jaynes-Cummings model is integrable,it is easy to derive its analytical solution. With increasing $g / \omega$ ， the ultrastrong coupling regime $( g / \omega > \sim 0 . 1 )$ [12] or the deep strong coupling regime $( g / \omega > \sim 1 . 0 )$ [9]is reached,where the JaynesCummings model is invalid and cannot be used to investigate the interaction between light and matter.Recently these regimes have rapidly growing interesting due to their fundamental characteristics and the potential ap plications in quantum devices [11-14].

Although the Hamiltonian (1）has a simple form,it has not been possible to obtain its analytical solution, which is considerably important for exploring accurately the light-matter interaction, from weak to extreme strong interaction.In Ref. [15],Braak presented an analytical solution of the Rabi model by using the representation of bosonic operators in the Bargmann space of analytical functions. The energy spectrum consists of two parts, the regular and the exceptional spectrum.However,such a spectrum structure is considerably strange.It has been proved that the Braak's analytical solution of the Rabi model is completely wrong due to the derivation error in solving the time-independent Schrodinger equation [17].

In this work,we exactly diagonalize the Hamiltonian (1) in the whole range of the physical parameters by using the unitary transformation technique in the occupation number representation.Such a direct and powerful approach has been used to solve successfully the complex two-dimensional electron gas in the presence of both Rashba and Dresselhaus spin-orbit interactions under a perpendicular magnetic field [18]. The eigenvalues are fixed by the parameters in the unitary transformations, which satisfy highly nonlinear equations. The eigenfunctions are convergent infinite series in terms of the physical parameters. The exact Landau levels have been accepted popularly [19](also see the citations of Ref.[18]).When the Rashba or Dresselhaus spin-orbit coupling vanishes, this two-dimensional electron system has the same bosonic Hamiltonian with the Jaynes-Cummings model except a constant [16,18].

The two-component eigenstate of the Hamiltonian (1) for the nth energy level with quantum number $s$ usually has the general form

$$
| n , s > = \frac { 1 } { A _ { n s } } \sum _ { m = 0 } ^ { + \infty } \left( \begin{array} { c c } { { 1 } } & { { \Delta _ { n s } } } \\ { { - \Delta _ { n s } } } & { { 1 } } \end{array} \right) \left( \begin{array} { c } { { \alpha _ { m } ^ { n s } } } \\ { { \beta _ { m } ^ { n s } } } \end{array} \right) \phi _ { m } ,
$$

$$
| { \cal A } _ { n s } | ^ { 2 } = ( 1 + \Delta _ { n s } ^ { 2 } ) \sum _ { m = 0 } ^ { \infty } ( | \alpha _ { m } ^ { n s } | ^ { 2 } + | \beta _ { m } ^ { n s } | ^ { 2 } ) ,
$$

where the $2 \times 2$ matrix is a unitary one, $s = \pm 1$ ， $\Delta _ { n s }$ is a real parameter to be determined below by requiring $\alpha _ { m } ^ { n s }$ and $\beta _ { m } ^ { n s }$ to be nonzero, $\phi _ { m }$ is the eigenstate of the mth energy level in the occupation number representation,i.e. $a ^ { + } \phi _ { m } = \sqrt { m + 1 } \phi _ { m + 1 }$ ， $a \phi _ { m } = \sqrt { m } \phi _ { m - 1 }$ and $< \phi _ { m ^ { \prime } } | \phi _ { m } > = \delta _ { m m ^ { \prime } }$ When $m  + \infty$ ， $\alpha _ { m } ^ { n s } = \beta _ { m } ^ { n s } = 0$ We solve the eigen-equation $H | n , s > = E _ { n s } | n , s >$ and obtain the double degenerate energy spectrum consisting of two sub-energy spectra,which is very different from that presented in Ref. [15].

The sub-energy spectrum $I .$ In order to obtain the analytical solution of the Hamiltonian(1) in the whole parameter space,we first choose

$$
\begin{array} { r l } { [ \omega ( n + 1 ) + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda - \frac { 2 \Delta _ { n s } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon - E _ { n s } ] \alpha _ { n + 1 } ^ { n s } } & { } \\ { + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } g \sqrt { n + 1 } \beta _ { n } ^ { n s } \ = \ 0 , } & { } \\ { ( \omega n - \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda + \frac { 2 \Delta _ { n s } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon - E _ { n s } ) \beta _ { n } ^ { n s } } & { } \\ { + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } g \sqrt { n + 1 } \alpha _ { n + 1 } ^ { n s } \ = \ 0 } & { } \end{array}
$$

in the eigen-equation. Then the eigenfunction associated with the eigenvalue $E _ { n s }$ is solely fixed by requiring

$$
[ 2 \lambda \Delta _ { n s } + \epsilon ( 1 - \Delta _ { n s } ^ { 2 } ) ] \beta _ { n } ^ { n s } - 2 g \Delta _ { n s } \sqrt { n + 1 } \alpha _ { n + 1 } ^ { n s } = 0 ,
$$

or

$$
[ 2 \lambda \Delta _ { n s } + \epsilon ( 1 - \Delta _ { n s } ^ { 2 } ) ] \alpha _ { n + 1 } ^ { n s } + 2 g \Delta _ { n s } \sqrt { n + 1 } \beta _ { n } ^ { n s } = 0 .
$$

We solve the homogenous linear equations (3） about $\alpha _ { n + 1 } ^ { n s }$ and $\beta _ { n } ^ { n s }$ by vanishing of thecoefficient determinant.Then the eigenvalue for the nth eigenstate with $s$ has the analytical expression

$$
\begin{array} { r l } & { E _ { n s } = ( n + \frac { 1 } { 2 } ) \omega + s \Xi _ { n s } , } \\ & { \Xi _ { n s } = \sqrt { ( \frac { \omega } { 2 } + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda - \frac { 2 \Delta _ { n s } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon ) ^ { 2 } + ( n + 1 ) g ^ { 2 } ( \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } ) ^ { 2 } } . } \end{array}
$$

Note that the quasiparticle energy $E _ { n s }$ must be larger than zero. Combining Eqs. (3)-(5),the parameter $\Delta _ { n s }$ is determined by the constraint

$$
\epsilon ( 1 + \Delta _ { n s } ^ { 2 } ) - 2 \Delta _ { n s } ( E _ { n s } - \omega n ) = 0 ,
$$

or

$$
\epsilon ( 1 + \Delta _ { n s } ^ { 2 } ) + 2 \Delta _ { n s } [ E _ { n s } - \omega ( n + 1 ) ] = 0 .
$$

Surprisingly, Eq. （7) with $s = - 1 ( 1 )$ coincides with Eq. (8) with $s = 1 ( - 1 )$ . So we have

$$
\epsilon ( 1 + \Delta _ { n s } ^ { 2 } ) + \Delta _ { n s } ( 2 \sigma \Xi _ { n s } - \omega ) = 0 ,
$$

where $\sigma = \pm 1$ ．Obviously，when $\epsilon = 0$ ，then $\Delta _ { n s } = 0$ （204 from Eq. (9).Therefore,the eigenvalue (6) has a simple form in the absence of the driving term.Fig. 1 plots the low-lying energy levels as a function of $g$ at different $\lambda$ under $\epsilon = 0$ . We can see that there are level crossings between the neighboring eigenstates.With increasing $\lambda$ ， the energy levels with $s = 1 ( - 1 )$ become higher (lower), and these crossing points move toward the origin.

When $\epsilon \neq 0$ ， $\Delta _ { n s }$ in Eq.(9)with $\sigma = 1$ has an $\omega$ dependent solution. The corresponding eigenvalues $E _ { n s }$

![](images/5c96c5c99566b74f5fec2317a5564c6e3087d455aabcc6a396bdaec46da6c908.jpg)  
FIG.1: (Color online) The low-lying energy levels of the subenergy spectrum Iin unit of $\omega$ as a function of the coupling parameter $g$ at different $\lambda$ under $\epsilon = 0$ . The solid lines denote $n = 0 , 1 , \cdots , 5$ and $s ~ = ~ 1$ while the dash lines mean $n =$ $1 , 2 , \cdots { } , 5$ and $s = - 1$ ：

L $n = 0 , 1 , 2 , \cdot \cdot \cdot , \infty , s = \pm 1$ ）form the sub-energy spectrum I. In Fig. 2,we show the low-lying energy levels of the sub-energy spectrum I as a function of $g$ at different $\lambda$ under $\epsilon = 0 . 4$ and the corresponding parameter $\Delta _ { n s }$ .From Fig. 1 and Fig. 2,we find that if $\lambda$ or $\epsilon$ （20 increases，the energy levels with $s = 1 ( - 1 )$ also move up (down),and the crossing points also shift toward the left side.When $g = 0$ ，the sub-energy spectrum I (6) recovers the exact eigenvalues for the interactionless case $E _ { n s } = \omega n + s \sqrt { \lambda ^ { 2 } + \epsilon ^ { 2 } }$ with $\Delta _ { n s } = ( \lambda - \sqrt { \lambda ^ { 2 } + \epsilon ^ { 2 } } ) / \epsilon$ Obviously, if $\epsilon  0$ ， $\Delta _ { n s }  0$ .We note that another sub-energy spectrum corresponding to the $\omega$ -dependent solution $\Delta _ { n s }$ in Eq.(9)with $\sigma = - 1$ is nothing but the sub-energy spectrum II (see below).

For the eigenstate associated with the eigenvalue (6), we have

$$
\alpha _ { n + 1 } ^ { n s } = \frac { ( 1 + \Delta _ { n s } ^ { 2 } ) ( E _ { n s } - n \omega ) + ( 1 - \Delta _ { n s } ^ { 2 } ) \lambda - 2 \Delta _ { n s } \epsilon } { \sqrt { n + 1 } ( 1 - \Delta _ { n s } ^ { 2 } ) g } \beta _ { n } ^ { n s } ,
$$

where $\beta _ { n } ^ { n s }$ is an arbitrary constant and can be set to $^ { 1 }$ ， and the coefficients $\alpha _ { i } ^ { n s }$ and $\beta _ { i } ^ { n s }$ are uniquely determined by the recursion relations

$$
\sqrt i \mathcal M ^ { n s } \left( \begin{array} { l } { \alpha _ { i - 1 } ^ { n s } } \\ { \beta _ { i - 1 } ^ { n s } } \end{array} \right) = - \mathcal N _ { i } ^ { n s } \left( \begin{array} { l } { \alpha _ { i } ^ { n s } } \\ { \beta _ { i } ^ { n s } } \end{array} \right) - \sqrt i + 1 \mathcal M ^ { n s } \left( \begin{array} { l } { \alpha _ { i + 1 } ^ { n s } } \\ { \beta _ { i + 1 } ^ { n s } } \end{array} \right) ,
$$

for $i = 0 , 1 , 2 , \cdots , n$ ,and

$$
\sqrt { i + 1 } \mathcal { M } ^ { n s } \left( \begin{array} { l } { \alpha _ { i + 1 } ^ { n s } } \\ { \beta _ { i + 1 } ^ { n s } } \end{array} \right) = - \mathcal { N } _ { i } ^ { n s } \left( \begin{array} { l } { \alpha _ { i } ^ { n s } } \\ { \beta _ { i } ^ { n s } } \end{array} \right) - \sqrt { i } \mathcal { M } ^ { n s } \left( \begin{array} { l } { \alpha _ { i - 1 } ^ { n s } } \\ { \beta _ { i - 1 } ^ { n s } } \end{array} \right) ,
$$

for $i = n + 1 , n + 2 , \cdots , + \infty$ .Here we have defined

$$
\begin{array} { r l } { \mathcal { M } ^ { n s } \ = \ \frac { g } { 1 + \Delta _ { n s } ^ { 2 } } \big [ ( 1 - \Delta _ { n s } ^ { 2 } ) \sigma _ { x } - 2 \Delta _ { n s } \sigma _ { z } \big ] , } & { } \\ { \mathcal { N } _ { i } ^ { n s } \ = \ ( \omega i - E _ { n s } ) I + \big ( \frac { 2 \Delta _ { n s } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon \big ) \sigma _ { x } } & { } \\ & { \ + \big ( \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda - \frac { 2 \Delta _ { n s } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon \big ) \sigma _ { z } , } \end{array}
$$

where $I$ is the $2 \times 2$ unit matrix.

The sub-energy spectrum $\varLambda .$ Now we use another choice

![](images/3cf44096c885099f7135b0fd4cc09b748327ab57a8a7a9f6224ca0b0345c82eb.jpg)  
FIG.2:(Color online) The low-lying energy levels of the subenergy spectrum Iin unit of $\omega$ as a function of the coupling parameter $g$ at different $\lambda$ under $\epsilon = 0 . 4$ ,shown in (a) and (c). The solid lines denote $n = 0 , 1 , \cdots , 5$ and $s = 1$ while the dash lines mean $n = 1 , 2 , \cdots , 5$ and $s = - 1$ ．The corresponding $\Delta _ { n s }$ are displayed in (b）and (d),respectively.

$$
\begin{array} { r l } { ( \omega n + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda - \frac { 2 \Delta _ { n s } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon - E _ { n s } ) \alpha _ { n } ^ { n s } } & { } \\ { + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } g \sqrt { n + 1 } \beta _ { n + 1 } ^ { n s } \ = \ 0 , } & { } \\ { \left[ \omega ( n + 1 ) - \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda + \frac { 2 \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon - E _ { n s } \right] \beta _ { n + 1 } ^ { n s } } & { } \\ { + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } g \sqrt { n + 1 } \alpha _ { n } ^ { n s } \ = } & { 0 } \end{array}
$$

in the eigen-equation. The corresponding eigenfunction is uniquely determined by letting

$$
[ 2 \lambda \Delta _ { n s } + \epsilon ( 1 - \Delta _ { n s } ^ { 2 } ) ] \alpha _ { n } ^ { n s } + 2 g \Delta _ { n s } \sqrt { n + 1 } \beta _ { n + 1 } ^ { n s } = 0 ,
$$

![](images/2b6ec7a52d7f4e23a5caa79f8392e1a6fa5a99b82df321e4ca917435d98c1702.jpg)  
FIG.3:(Color online) The low-lying energy levels of the subenergy spectrum II in unit of $\omega$ as a function of the coupling parameter $g$ at different $\lambda$ under $\epsilon = 0$ . The solid lines denote $n = 0 , 1 , \cdots , 5$ and $s ~ = ~ 1$ while the dash lines mean $n =$ $0 , 1 , \cdots , 5$ and $s = - 1$ ：

or

$$
[ 2 \lambda \Delta _ { n s } + \epsilon ( 1 - \Delta _ { n s } ^ { 2 } ) ] \beta _ { n + 1 } ^ { n s } - 2 g \Delta _ { n s } \sqrt { n + 1 } \alpha _ { n } ^ { n s } = 0 ,
$$

Solving Eqs. (14)，we have the eigenvalue for the nth eigenstate with $s$ （204号

$$
\begin{array} { r l } & { E _ { n s } = ( n + \frac { 1 } { 2 } ) \omega + s \Theta _ { n s } , } \\ & { \Theta _ { n s } = \sqrt { ( - \frac { \omega } { 2 } + \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } \lambda - \frac { 2 \Delta _ { n s } } { 1 + \Delta _ { n s } ^ { 2 } } \epsilon ) ^ { 2 } + ( n + 1 ) g ^ { 2 } ( \frac { 1 - \Delta _ { n s } ^ { 2 } } { 1 + \Delta _ { n s } ^ { 2 } } ) ^ { 2 } } . } \end{array}
$$

Here $\Delta _ { n s }$ satisfies the nonlinear equation

$$
\epsilon ( 1 + \Delta _ { n s } ^ { 2 } ) + 2 \Delta _ { n s } ( E _ { n s } - \omega n ) = 0 ,
$$

or

$$
\epsilon ( 1 + \Delta _ { n s } ^ { 2 } ) - 2 \Delta _ { n s } [ E _ { n s } - \omega ( n + 1 ) ] = 0 ,
$$

which is derived from Eqs. (14)-(16). Similar to Eqs.(7) and (8),Eq.(18) with $s = - 1 ( 1 )$ is also consistent with Eq.(19)with $s = 1 ( - 1 )$ .Therefore,we obtain

$$
\epsilon ( 1 + \Delta _ { n s } ^ { 2 } ) + \Delta _ { n s } ( 2 \tau \Theta _ { n s } + \omega ) = 0 ,
$$

where $\tau = \pm 1$ .If $\epsilon = 0$ ，then $\Delta _ { n s } = 0$ in Eq. (20).So the eigenvalue (17) also has an explicit expression in this case.We depict the low-lying energy levels as a function of $g$ at different $\lambda$ under $\epsilon = 0$ in Fig. 3. With increasing $\lambda$ , the energy levels with $s = - 1 ( 1 )$ become higher (lower) while the crossing points move away the origin,opposite to those in Fig. 1.

If $\epsilon \neq 0$ ， $\Delta _ { n s }$ in Eq.(20）with $\tau = 1$ also has an $\omega$ dependent solution. The corresponding eigenvalues constitute the sub-energy spectrum II.Fig. 4 exhibits the low-lying energy levels of the sub-energy spectrum II as a function of $g$ at different $\lambda$ under $\epsilon = 0 . 4$ and the corresponding parameter $\Delta _ { n s }$ .When $\lambda$ is increasing,the energy levels with $s = 1 ( - 1 )$ also move up (down)，and the crossing points also shift toward the origin. This resembles the level shifts in the sub-energy spectrum I (see Fig.2). From Figs. 3 and 4,we find that when $\lambda = 0 . 3 \omega$ the energy levels with $s = - 1 ( 1 )$ move up (down) with increasing $\epsilon$ .Oppositely, the energy levels with $s = 1 ( - 1 )$ move up (down） at $\lambda = 0 . 5 \omega$ . Obviously, the level shifts in the sub-energy spectrum I are more complex than those in the sub-energy spectrum I. We note that the sub-energy spectrum associated with $\Delta _ { n s }$ in Eq. (20) with $\tau = - 1$ is consistent with the sub-energy spectrum I. Therefore,both the sub-energy spectrum I and II are double degenerate.So the Braak's mathematical solution also loses a half of the eigenvalues.

For the nth eigenstate with $s$ in the sub-energy spectrum $\mathrm { I I }$ ，we have

$$
\beta _ { n + 1 } ^ { n s } = \frac { ( 1 + \Delta _ { n s } ^ { 2 } ) ( E _ { n s } - n \omega ) - ( 1 - \Delta _ { n s } ^ { 2 } ) \lambda + 2 \Delta _ { n s } \epsilon } { \sqrt { n + 1 } ( 1 - \Delta _ { n s } ^ { 2 } ) g } \alpha _ { n } ^ { n s } ,
$$

where $\alpha _ { n } ^ { n s }$ is an arbitrary constant and is set to $^ { 1 }$ . The coefficients $\alpha _ { i } ^ { n s }$ and $\beta _ { i } ^ { n s }$ obey the same recursion relations (11) and (12) in the sub-energy spectrum I.

In summary,we have exactly solved the generalized Rabi model(1) in the framework of quantum mechanics. The complete spectrum is comprised of two double-fold degenerate sub-energy spectrum I and II.Very different from the energy spectrum in Ref. [15], the level crossings occur even if $\epsilon$ is not a multiple of $\omega / 2$ .Such the physical solution can help us to deeply understand the lightmatter interaction,especially in strong coupling regime. It is expected that the level crossings at certain physical parameters could produce novel physical phenomena in the interaction systems, just like in two-dimensional electron gas with spin-orbit interaction under a perpendicular magnetic field [2O-22]. Finally, we would like to mention that the unitary transformation method presented here can be applied naturally to the general Rabi model,which is a further extension of the generalized Rabi model by adding $H ^ { \prime } = ( a ^ { + } + a ) ( g _ { y } \sigma _ { y } + g _ { z } \sigma _ { z } ) + \epsilon _ { y } \sigma _ { y }$ to the Hamiltonian (1),where $g _ { y } , g _ { z }$ ，and $\epsilon _ { y }$ are the physical parameters.

![](images/585cdef254fb4c730d34de55e69b4b4af8a4aae1c55eb9ebe2b2d58b189c38c2.jpg)  
FIG.4:(Color online) The low-lying energy levels of the subenergy spectrum II in unit of $\omega$ as a function of the coupling parameter $g$ at different $\lambda$ under $\epsilon = 0 . 4$ ,shown in (a) and (c). The solid lines denote $n = 0 , 1 , \cdots , 5$ and $s = 1$ while the dash lines mean $n = 0 , 1 , \cdots , 5$ and $s = - 1$ ．The corresponding $\Delta _ { n s }$ are displayed in (b）and (d),respectively.

This work was supported by the Sichuan Normal University and the "Thousand Talents Program”of Sichuan Province, China.

[1] I. I. Rabi,Phys. Rev. 49,324 (1936); Phys. Rev. 51,652 (1937).   
[2] S.Haroche and J.-M. Raimond, Exploring the Quantum: Atoms,Cavities,and Photons(Oxford University Press, Oxford, 2006).   
[3] V. Vedral, Modern Foundations of Quantum Optics (Imperial College Press,London, 2006).   
[4]D.Leibfried,R.Blatt,C.Monroe,andD.Wineland, Rev. Mod.Phys.75,281 (2003). [5] J.s. Pedernales et al., Sci.Rep. 5,15472 (2015). [6] D.E. Reiter,Phys.Rev.B 95,125308 (2017) [7]A.Wallraff et al.,Nat.431,162 (2004). [8]D.S.Shapiro et al.,Phys.Rev.A 91,063814 (2015)   
[9] F.Yoshihara et al.,Nat.Phys.13,44 (2017).   
[10] S.Felicetti et al.,Phys.Rev.A 95,013827 (2017).   
[11]M.A.Nielsen and I.L.Chuang,Quantum Computation and Quantum Information (Cambridge University Press, Cambridge,2004).   
[12] P.Nataf and C.Ciuti，Phys.Rev.Lett.107，190402 (2011).   
[13] G.Romero et al.,Phys.Rev.Lett.108,120501 (2012).   
[14] T.Kyaw et al., Sci.Rep.5,8621 (2015).   
[15] D.Braak,Phys.Rev.Lett.107,100401 (2011).   
[16]E.T. Jaynes and F.W.Cummings,Proc. IEEE,51,89 (1963).   
[17] Degang Zhang, chinaXiv:201804.01458.   
[18] Degang Zhang, J. Phys.A: Math. Gen. 39,L477 (2006).   
[19] Fu-Chun Zhang and Shun-Qing Shen,IJMP B 22,94 (2008).   
[20] Shun-Qing Shen,Michael Ma,X.C.Xie,and Fu-Chun Zhang,Phys.Rev.Lett.92,256603 (2004).   
[21] Degang Zhang,Yao-Ming Mu，and C. S. Ting，Appl. Phys.Lett.92,212103 (2008).   
[22] Degang Zhang and C.S.Ting,arXiv:1510.01012.