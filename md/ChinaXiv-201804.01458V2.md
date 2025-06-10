# Comment on "Integrability of the Rabi Model"

Degang Zhang $^ { 1 , 2 }$ $^ { 1 }$ College of Physics and Electronic Engineering, Sichuan Normal University， Chengdu 610101， China $\mathcal { Z }$ Institute of Solid State Physics，Sichuan Normal University，Chengdu 610101，China

PACS numbers:03.65.Ge,02.30.Ik,42.50.Pq

The Rabi model describes a two-level system coupled with a single bosonic mode [1]. Such a simplest interacting quantum model has possessed wide applications in many fields of physics [2-4]. Therefore,in order to understand thoroughly the physical properties of these systems,its exact solution,which has been a long-standing problem，is of special significance.However,Braak p resented an analytical solution of the Rabi model seven years ago [5]. The energy spectrum consists of two parts,i. e. the regular and the exceptional spectrum. Such a spectrum structure is considerably strange.In this Comment,I point out that the Braak's analytical solution doesn't exhibit the true energy spectrum of the Rabi model due to the derivation error in solving the time-independent Schrodinger equation.

Braak startedfromtheRabimodel

$$
H _ { s b } = \omega a ^ { + } a + g \sigma _ { z } ( a ^ { + } + a ) + \Delta \sigma _ { x }
$$

in Ref. [5]. After taking the transformations $\begin{array} { r } { a  \frac { \partial } { \partial z } } \end{array}$ and $a ^ { + } \to z$ , then the Hamiltonian (1） becomes

$$
H _ { s b } = \left( \begin{array} { c c } { \omega z \partial _ { z } + g ( z + \partial _ { z } ) } & { \Delta } \\ { \Delta } & { \omega z \partial _ { z } - g ( z + \partial _ { z } ) } \end{array} \right) .
$$

Suppose that $( \phi _ { 1 } \ \phi _ { 2 } ) ^ { T }$ is the two-component wave function of $H _ { s b }$ .Then one has a coupled system of the firstorder differential equations

$$
\begin{array} { r } { ( z + g ) \frac { d } { d z } \phi _ { 1 } ( z ) + ( g z - E ) \phi _ { 1 } ( z ) + \Delta \phi _ { 2 } ( z ) = 0 , } \\ { ( z - g ) \frac { d } { d z } \phi _ { 2 } ( z ) - ( g z + E ) \phi _ { 2 } ( z ) + \Delta \phi _ { 1 } ( z ) = 0 , } \end{array}
$$

where $\omega ~ = ~ 1$ and $E$ is the corresponding eigenvalue. Braak found that Eqs.(3) and （4) have the following solution

$$
\begin{array} { c } { { \phi _ { 1 } ( z ) = e ^ { - g z } \sum _ { n = 0 } ^ { \infty } K _ { n } ( x ) \Delta \frac { ( z + g ) ^ { n } } { x - n } , } } \\ { { \phi _ { 2 } ( z ) = e ^ { - g z } \sum _ { n = 0 } ^ { \infty } K _ { n } ( x ) ( z + g ) ^ { n } , } } \end{array}
$$

where $x = E + g ^ { 2 }$ ， $E$ can take an arbitrary value,and the constants $K _ { n } ( x )$ satisfy the recursive relation (4) in Ref. [5]. Obviously, $\phi _ { 1 } ( z )$ and $\phi _ { 2 } ( z )$ are divergent at $z  - \infty$ Therefore, this two-component solution $( \phi _ { 1 } \ \phi _ { 2 } ) ^ { T }$ of $H _ { s b }$ is trivial and non-physical due to the divergence of the wave function and the undetermined eigenvalue.

In order to fx the eigenvalue $E$ ，Braak employed the unitarytransformation

$$
U = \frac { 1 } { \sqrt { 2 } } \left( \begin{array} { c c } { 1 } & { 1 } \\ { T } & { - T } \end{array} \right) ,
$$

where the operator $T$ satisfies $T ( f ) ( z ) = f ( - z )$ .Itis easy to get

$$
U ^ { + } H _ { s b } U = \left( \begin{array} { c c } { { H _ { + } } } & { { 0 } } \\ { { 0 } } & { { H _ { - } } } \end{array} \right) .
$$

Here, $H _ { \pm } = \omega z \partial _ { z } + g ( z + \partial _ { z } ) \pm \Delta T$ . Obviously, $H _ { - }$ can be obtained from $H _ { + }$ by letting $\Delta$ be $- \Delta$

The time-independent Schrodinger equation for $H _ { + }$ with positive parity reads

$$
z \frac { d } { d z } \psi ( z ) + g ( \frac { d } { d z } + z ) \psi ( z ) = E \psi ( z ) - \Delta \psi ( - z ) ,
$$

which becomes

$$
z { \frac { d } { d z } } \psi ( - z ) - g ( { \frac { d } { d z } } + z ) \psi ( - z ) = E \psi ( - z ) - \Delta \psi ( z )
$$

after manipulating $T$ on two sides of Eq. (9). Here $\omega = 1$ and $E$ is the eigenvalue of $H _ { + }$ (or $H _ { s b }$ )．It is obvious that $\psi ( z )$ and $\psi ( - z ) = T ( \psi ) ( z )$ in Eq.(9) or(10) are correlated due to the reflection operator $T$ ：

With the notation $\psi ( z ) = \phi _ { 1 } ( z )$ and $\psi ( - z ) = \phi _ { 2 } ( z )$ Eqs.(9) and(1O) lead to Eqs.(3) and(4),respectively. Such a notation is the solution of the coupled equations (3)and(4) rather than the single equation(9)with the presence of $T$ .I note that if and only if

$$
G _ { + } ( x ; z ) = \phi _ { 2 } ( z ) - T \phi _ { 1 } ( z ) = \phi _ { 2 } ( z ) - \phi _ { 1 } ( - z ) \equiv 0
$$

for any $z$ , this notation $\{ \psi ( z ) , \psi ( - z ) \}$ is the solution of Eq. (9).

Obviously, Braak treated $\psi ( z )$ and $\psi ( - z )$ as independent wave functions and neglected the condition (11). By requiring the wave function $\{ \psi ( z ) , \psi ( - z ) \}$ to be continuous at $z = 0$ ,i.e. $G _ { + } ( x ; z = 0 ) = 0$ ,Braak obtained the eigenvalues $E$ (see (3)and Fig.1 in Ref.[5]). However, the constraint(1l) does not hold for nonzero $z$ under these eigenvalues $E$ [see the expressions (5） and (6)]. So such a wave function $\{ \psi ( z ) , \psi ( - z ) \}$ with a cusp at $z = 0$ （204号 and the corresponding eigenvalue $E$ are not these of $H _ { + }$ ： Similarly, the solution for $H _ { - }$ with negative parity can be obtained by replacing $\Delta$ with $- \Delta$ . Therefore,it is out of question that the energy spectrum shown in Figs. 2 and 3 in Ref. [5] is not that of the Rabi model (1)[6].

Braak also applied the similar technique to the generalized Hamiltonian by adding $\epsilon \sigma _ { z }$ to (1) (i.e. (7) in Ref. [5])．However，the same derivation error occurs. The energy spectrum depicted in Fig.4 in Ref.[5] is also incorrect [6].

Finally,I would like to mention that I have exactly solved the Rabi model by using the unitary transformation technique in the occupation number representation [7]. The complete energy spectrum is comprised of two double-fold degenerate sub-energy spectrum I and II.

This work was supported by the Sichuan Normal University and the "Thousand Talents Program”of Sichuan Province, China.

[2] S.Haroche and J.-M.Raimond,Exploring the Quantum: Atoms,Cavities,and Photons (Oxford University Press, Oxford,2006).   
[3] V.Vedral,Modern Foundations of Quantum Optics (Imperial College Press,London,2006).   
[4] M.A. Nielsen and I.L.Chuang,Quantum Computation and Quantum Information (Cambridge University Press, Cambridge,2004).   
[5]D.Braak,Phys.Rev.Lett.107,100401(2011）and the Supplement Material.   
[6] Degang Zhang,chinaXiv:201804.01458.   
[7] Degang Zhang,chinaXiv:201708.00168.

[1]I.I.Rabi,Phys.Rev.49,324(1936); Phys.Rev.51,652 (1937).