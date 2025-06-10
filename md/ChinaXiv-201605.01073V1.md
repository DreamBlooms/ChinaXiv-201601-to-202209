# Gas-Fluid and Fluid-Solid Phase Instability for Restricted Primitive Model\*

GUO Yuan-Yuan and CHEN Xiao-Song   
KeyLaboratory_of Frontiers in Theoretical Physics,Instituteof Theoretical Physics,Chinese Academy of Sciences,   
P.O.Box 2735,Beijing 100190, China

(Received May11,2009)

Abstract By considering the fluctuation of grand potential $\Omega$ around equilibrium with respect to small one-particle density fluctuations $\delta \rho _ { \alpha } ( \vec { r } )$ ,the phase instability of restricted primitive model (RPM) of ionic systems is investigated. Weuse the integral equation theory to calculate the direct correlation functions in the reference hypernettd chain approximationandobtain thespinodalineofRPM.Ouranalysis explicitly indicates that the gas-fuid phase instability is induced by $k = 0$ fluctuation mode,while the fluid-solid phase instabilityis related to $k \neq 0$ fluctuation modes.The spinodal line is qualitatively consistent with the result of computer simulations by others.

PACS numbers: 64.70.-p, 05.70.Fh Key words: phase instability, restricted primitive model, the reference hypernetted chain approximation

# 1 Introduction

For ionic system the most widely investigated model is therestricted primitive model (RPM),in which the ions are modeled as equal-sized hard spheres of diameter $a$ and carry charges of the same absolute value in a medium of dielectric constant $D$ .The whole system is electrically neutral. A number of studies have been focused on the gas-fluid phase transition and the critical behavior of ionic liquids relying on RPM. $[ 1 ]$ Comparatively less attention was paid to fluid-solid phase transition. Stillinger and Lovett[2] sketched the phase diagram including the fluid-solid phase transition for the charged hard sphere.In Ref.[3] Barrat used the density functional theory of freezing to calculate the fluid-solid phase diagram of RPM,and found that the solid changes from a disordered face-centered cubic (fcc) structure to a Caesium Chloride (CsCl） structure when the temperature decreases to be low enough.Monte Carlo(MC) computer simulation was applied to investigate the fluid-solid phase transition of RPM by the authors in Refs.[4,5].Later Bresme et al.in Ref.[6] found a new ordered fcc structure at low temperature and high density by using MC simulation.The full coexistence curves of gas,fluid,and solid phases of RPM were found by means of computer simulation.[7]

Since MC simulations mentioned above only gave the $T$ $\rho$ phase diagram and did not present explicit analysis of how the control parameters (e.g. $T$ ， $\rho$ )influence the phase transition characteristics. For this purpose,we focus on the gas-fluid and fluid-solid phase instability of RPM by means of soft mode analysis. Based on the correlation functions which are calculated in the framework of integral equation theory with the reference hypernetted chain (RHNC) approximation,we present a complete discussion on the phase instability of the RPM and obtain the spinodal line,which is the border line between stability and instability regime either of gas-fluid transition or of fluidsolid transition.Our results explicitly show that the gasfluid phase instability is related to $k = 0$ fluctuation mode, while the fluid-solid phase instability is induced by $k \neq 0$ fluctuation modes.

# 2 Model

Progress has been made in the theories and simulations of the restricted primitive model (RPM) with equal number of $\pm$ ions interacting by coulombic force in a medium of dielectric constant $D$ .All the ions are considered as hard spheres with the same diameter $a$ and carrying charges （204号 $q _ { \alpha } = \pm q _ { 0 }$ ， $q _ { 0 }$ is the charge of a proton. The ion-ion potential between ion $\alpha$ and ion $\beta$ is given by

$$
v _ { \alpha \beta } ( r ) = \left\{ \begin{array} { l l } { \infty , } & { r < a ; } \\ { \displaystyle \frac { q _ { \alpha } q _ { \beta } } { D r } , } & { r > a . } \end{array} \right.
$$

# 3Method for Analysis of Instability

In order to study the stability of the equilibrium state for the binary mixture,we consider the fluctuation of the grand potential around the minimum caused by small oneparticle density fluctuations $\delta \rho _ { \alpha } ( \vec { r } )$ and expand the grand potential to the second order

$$
\begin{array} { l } { \displaystyle \delta \Omega = \Omega [ T , V , \mu _ { \alpha } , \rho _ { \alpha } + \delta \rho _ { \alpha } ( \vec { r } ) ] - \Omega ( T , V , \mu _ { \alpha } , \rho _ { \alpha } ) } \\ { \displaystyle \simeq \frac { 1 } { 2 } \int \int \sum _ { \alpha \beta } \frac { \delta ^ { 2 } \Omega } { \delta \rho _ { \alpha } ( \vec { r } _ { 1 } ) \delta \rho _ { \beta } ( \vec { r } _ { 2 } ) } \left. \right| _ { e . } } \end{array}
$$

$$
\times \delta \rho _ { \alpha } ( \vec { r _ { 1 } } ) \delta \rho _ { \beta } ( \vec { r _ { 2 } } ) d ^ { 3 } \vec { r _ { 1 } } d ^ { 3 } \vec { r _ { 2 } } ,
$$

where $\alpha$ ， $\beta = 1 , 2$ ,and $^ { 1 }$ ，2 represent the two components of mixture. The second functional derivatives of $\Omega$ are related to the direct correlation functions $c _ { \alpha \beta } ( 1 , 2 ) ^ { \left\lfloor 8 , 9 \right\rfloor }$ by

$$
\frac { \delta ^ { 2 } \Omega } { \delta \rho _ { \alpha } ( \vec { r } _ { 1 } ) \delta \rho _ { \beta } ( \vec { r } _ { 2 } ) } \biggm \vert _ { e . } = k _ { B } T \bigg [ \frac { \delta _ { \alpha \beta } \delta ( \vec { r } _ { 1 } , \vec { r } _ { 2 } ) } { \rho _ { \alpha } ( \vec { r } _ { 1 } ) } - c _ { \alpha \beta } ( 1 , 2 ) \bigg ] .
$$

For $c _ { \alpha \beta } ( 1 , 2 )$ ， $1 \equiv \vec { r _ { 1 } }$ and $2 \ \equiv \ \vec { r _ { 2 } }$ .For a homogeneous system, the Fourier transformation of Eq. (2) reads

$$
\delta \Omega = \frac { 1 } { V } \sum _ { k } \delta \Omega ( k ) = \frac { k _ { B } T } { 2 } \frac { 1 } { V }
$$

$$
\times \sum _ { k } \sum _ { \alpha \beta } \delta \bar { \rho } _ { \alpha } ( k ) [ \delta _ { \alpha \beta } - ( \rho _ { \alpha } \rho _ { \beta } ) ^ { 1 / 2 } \tilde { c } _ { \alpha \beta } ( k ) ] \delta \bar { \rho } _ { \beta } ( k ) .
$$

Here the integral over $k$ is replaced by a sum over discrete $k$ -values:

$$
\frac { 1 } { ( 2 \pi ) ^ { 3 } } \int d ^ { 3 } k \to \frac { 1 } { V } \sum _ { k } , \qquad \delta \bar { \rho } _ { \alpha } ( k ) = \frac { \delta \tilde { \rho } _ { \alpha } ( k ) } { \rho _ { \alpha } ^ { 1 / 2 } } ,
$$

and $\widetilde { \rho } _ { \alpha } ( \boldsymbol { k } )$ is the Fourier transformation of $\rho _ { \alpha } ( \boldsymbol { r } )$ .It is more convenient to discuss the physical meaning of Eq. (4) by introducing two new fluctuation variables as follows

$$
\begin{array} { l } { { \delta \bar { \rho } ( k ) = \rho ^ { - 1 / 2 } [ \delta \tilde { \rho } _ { 1 } ( k ) + \delta \tilde { \rho } _ { 2 } ( k ) ] , } } \\ { { \delta \bar { c } ( k ) = \rho ^ { - 3 / 2 } ( c _ { 1 } c _ { 2 } ) ^ { - 1 / 2 } [ \rho _ { 2 } \delta \tilde { \rho } _ { 1 } ( k ) - \rho _ { 1 } \delta \tilde { \rho } _ { 2 } ( k ) ] , } } \end{array}
$$

where $\rho = \rho _ { 1 } + \rho _ { 2 }$ ， $c _ { 1 } = \rho _ { 1 } / \rho = c$ ，and $c _ { 2 } = \rho _ { 2 } / \rho = 1 - c$ The fluctuation variable $\delta \bar { \rho } ( k )$ corresponds to total one particle density fluctuation and $\delta { \bar { c } } ( k )$ corresponds to the concentration fluctuation.Now $\delta \Omega$ can be rewritten as

$$
\delta \Omega = \frac { k _ { B } T } { 2 } \frac { 1 } { V } \sum _ { k } \left( \delta \bar { \rho } ( k ) \quad \delta \bar { c } ( k ) \right)
$$

$$
\times \left( \begin{array} { c c } { { M _ { \rho \rho } ( k ) } } & { { M _ { \rho c } ( k ) } } \\ { { M _ { c \rho } ( k ) } } & { { M _ { c c } ( k ) } } \end{array} \right) \left( \begin{array} { c } { { \delta \bar { \rho } ( k ) } } \\ { { \delta \bar { c } ( k ) } } \end{array} \right) ,
$$

where the matrix $M ( k )$ is defined as

$$
\begin{array} { r l } & { M _ { \rho \rho } ( k ) = 1 - \rho [ c _ { 1 } ^ { 2 } \tilde { c } _ { 1 1 } ( k ) + c _ { 2 } ^ { 2 } \tilde { c } _ { 2 2 } ( k ) + 2 c _ { 1 } c _ { 2 } \tilde { c } _ { 1 2 } ( k ) ] , } \\ & { M _ { c c } ( k ) = 1 - \rho c _ { 1 } c _ { 2 } [ \tilde { c } _ { 1 1 } ( k ) + \tilde { c } _ { 2 2 } ( k ) - 2 \tilde { c } _ { 1 2 } ( k ) ] , } \\ & { M _ { \rho c } ( k ) = M _ { c \rho } ( k ) = ( c _ { 1 } c _ { 2 } ) ^ { 1 / 2 } \rho [ c _ { 2 } \tilde { c } _ { 2 2 } ( k ) } \\ & { \qquad - c _ { 1 } \tilde { c } _ { 1 1 } ( k ) - ( c _ { 2 } - c _ { 1 } ) \tilde { c } _ { 1 2 } ( k ) ] . } \end{array}
$$

The matrix $M ( k )$ can be diagonalized with eigenvalues $\lambda _ { \alpha } ( k )$ and eigenvectors $\vec { x } _ { \alpha } ( k )$ ,and then the grand potential fluctuation(7) becomes a sum of pure squares

$$
\delta \Omega = \frac { k _ { B } T } { 2 } \frac { 1 } { V } \sum _ { k } [ \lambda _ { 1 } ( k ) | \delta \bar { \rho } _ { 1 } ^ { \prime } ( k ) | ^ { 2 } + \lambda _ { 2 } ( k ) | \delta \bar { \rho } _ { 2 } ^ { \prime } ( k ) | ^ { 2 } ] ,
$$

where

$$
\begin{array} { l } { { \displaystyle \delta \bar { \rho } _ { i } ^ { \prime } ( k ) = x _ { i , 1 } ( k ) \delta \bar { \rho } ( k ) + x _ { i , 2 } ( k ) \delta \bar { c } ( k ) \ : , } } \\ { { \displaystyle \lambda _ { 1 , 2 } ( k ) = \frac { 1 } { 2 } [ M _ { \rho \rho } ( k ) + M _ { c c } ( k ) } } \\ { { \displaystyle \qquad \mp \left( ( M _ { \rho \rho } ( k ) - M _ { c c } ( k ) ) ^ { 2 } + 4 M _ { \rho c } ^ { 2 } ( k ) \right) ^ { 1 / 2 } ] \ : . } } \end{array}
$$

The system is stable if the grand potential increases for any fluctuation of one-particle densities.The fluctuation of the grand potential takes a quadratic form in Eq. (11) and the system is stable only when the eigenvalues of the coefficient matrix are positive.As a result,the border of a stability region,the spinodal line,is reached when the smaller eigenvalue $\lambda _ { 1 } ( k )$ goes to zero,and we can get the corresponding $\delta \bar { \rho } _ { 1 } ^ { \prime } ( k )$ ，which is most unstable.The eigenvector ${ \vec { x } } _ { 1 } ( k )$ characterizes the phase transition uniquely. When ${ \vec { x } } _ { 1 } ( k )$ is close to $\vec { x } _ { c } = ( 0 , 1 )$ ,the instability is dominated by demixing.If ${ \vec { x } } _ { 1 } ( k )$ is close to $\vec { x } _ { \rho } = ( 1 , 0 )$ ，the instability is dominated by condensation.

For RPM the two components of the mixture 1,2 are the cation and anion respectively. One has $\rho _ { + } = \rho _ { - } =$ $\rho / 2$ ， $c _ { + } = c _ { - } = 1 / 2$ ， $\tilde { c } _ { + + } ( k ) = \tilde { c } _ { -- } ( k )$ ,and then Eqs. (8),

(9),and（10)become

$$
\begin{array} { l } { { \displaystyle M _ { \rho \rho } ( k ) = 1 - \frac { 1 } { 2 } \rho [ \tilde { c } _ { + + } ( k ) + \tilde { c } _ { + - } ( k ) ] , } } \\ { { \displaystyle M _ { c c } ( k ) = 1 - \frac { 1 } { 2 } \rho [ \tilde { c } _ { + + } ( k ) - \tilde { c } _ { + - } ( k ) ] , } } \\ { { \displaystyle M _ { \rho c } ( k ) = M _ { c \rho } ( k ) = 0 . } } \end{array}
$$

Hence we can observe the pure condensation or demixing phase instability for RPM.When we change T and $\rho$ the pure condensation phase transition occurs if $\lambda _ { \rho \rho } ( k ) \equiv$ $M _ { \rho \rho } ( k ) = 0$ and $\lambda _ { c c } ( k ) \equiv M _ { c c } ( k ) \neq 0$ (i.e. $\lambda _ { \rho \rho } ( k )$ goes to zero first),and the pure demixing phase instability occurs if $\lambda _ { c c } ( k ) = 0$ and $\lambda _ { \rho \rho } ( k ) \neq 0$ (i.e. $\lambda _ { c c } ( k )$ goes to zero first).In order to calculate $\lambda _ { \rho \rho } ( k )$ and $\lambda _ { c c } ( k )$ ，we need to know the correlation functions $\tilde { c } _ { + + } ( k )$ and $\tilde { c } _ { + - } ( k )$ ,which will be calculated in the next section.

# 4Calculation of Correlation Functions

The correlation functions of ionic fluids can be calculated by integral equation theory which contains two equations.[10] The first one is the Ornstein-Zernike (O.Z.) equation which gives the exact relation between the ionion total correlation functions $h _ { \alpha \beta } ( 1 , 2 )$ and the ion-ion direct correlation functions $c _ { \alpha \beta } ( 1 , 2 )$ ．For homogeneous liquids,the O.Z.equation is

$$
h _ { \alpha \beta } ( 1 , 2 ) = c _ { \alpha \beta } ( 1 , 2 ) + \sum _ { \gamma } \rho _ { \gamma } \int h _ { \alpha \gamma } ( 1 , 3 ) c _ { \gamma \beta } ( 3 , 2 ) d ^ { 3 } \vec { r } _ { 3 } ,
$$

where $\alpha , \beta , \gamma = \pm$ are the ionic species.This equation can be interpreted as that the total correlation of two ions is the sum of direct correlation and indirect correlation transferred by all other particles.

For homogenous fluids the correlation functions depend on only the distance between two particles.We have then $h _ { \alpha \beta } ( 1 , 2 ) = h _ { \alpha \beta } ( r )$ and $c _ { \alpha \beta } ( 1 , 2 ) = c _ { \alpha \beta } ( r )$ with ${ r = | \vec { r } _ { 2 } - \vec { r } _ { 1 } | }$ ：

Since the O.Z.equation contains two unknown functions $h _ { \alpha \beta } ( r )$ and $c _ { \alpha \beta } ( \boldsymbol r )$ ，another relation between direct and total correlation functions is needed.This is

$1 + h _ { \alpha \beta } ( r ) = \exp [ - \beta { \upsilon } _ { \alpha \beta } ( r ) + h _ { \alpha \beta } ( r ) - c _ { \alpha \beta } ( r ) + b _ { \alpha \beta } ( r ) ] ,$ (17) where $v _ { \alpha \beta } ( r )$ is the interaction potential between $\alpha$ -ion and $\beta$ -ion, $b _ { \alpha \beta } ( r )$ is the so-called bridge term which can not be obtained exactly. The bridge term can be expressed as

$$
b _ { \alpha \beta } ( r ) = \sum _ { n = 3 } ^ { \infty } R _ { \alpha \beta } ^ { ( n ) } ( r ) ,
$$

where $R _ { \alpha \beta } ^ { ( n ) } ( r )$ represents the contribution of all $n$ particle direct correlation functions. Different forms of $b _ { \alpha \beta } ( r )$ lead to different approximations. In the RHNC approximation,[11,12] $b _ { \alpha \beta } ( r )$ is replaced by the bridge term of a reference system (usually the hard sphere system),[13,14]

$b _ { \alpha \beta } ^ { R } ( r ) = \ln [ 1 + h _ { \alpha \beta } ^ { H S } ( r ) ] - h _ { \alpha \beta } ^ { H S } ( r ) + c _ { \alpha \beta } ^ { H S } ( r ) , \quad r > a ,$ (19) where $h _ { \alpha \beta } ^ { H S } ( r )$ and $c _ { \alpha \beta } ^ { H S } ( r )$ are the total and direct correlation functions of hard spheres,which can be calculated by using Verlet and Weis's method.[13,14] The MC simulation for the ion-dipole mixture has shown that the RHNC approximation works very well15] for ionic fluids. So we take the RHNC approximation here to calculate the correlation functions.

The integral equation including O.Z. equation (16) and RHNC equation (17) can be solved numerically.[10] Because of the long range coulombic interaction,the direct correlation function has also a long range tail,which should be treated analytically.[16] The total correlation functions decay exponentially with the Debye screening length $\xi _ { D }$ as the correlation length.At very low densities $\xi _ { D }$ can be very large and the total correlation functions decaythen not so fast.According to the standard procedure to deal with long range interactions,in our calculation,we divide the correlation functions into two parts: the short range part and the long range part which are dealt with analytically.[16] The short range part can be calculated by numerical iteration method.

# 5Results for RPM

Using the ion-ion direct correlation functions $c _ { \alpha \beta } ( r )$ obtained from the RHNC integral equation,we calculate $M _ { \rho \rho } ( k )$ and $M _ { c c } ( k )$ inEqs.(13) and(14) for different temperatures and densities.Usually,only the homogeneous fluctuation mode $k ~ = ~ 0$ is considered. Figure 1 shows $\lambda _ { \rho \rho } ( k = 0 )$ for the reduced temperature $T ^ { * }$ at $\rho ^ { * } = 0 . 0 4$ 业 Here $T ^ { * } \equiv k _ { B } T D a / q _ { 0 } ^ { 2 }$ and $\rho ^ { * } \equiv \rho a ^ { 3 }$ denote the reduced temperature and thereduceddensity.Figure1shows that $\lambda _ { \rho \rho } ( k = 0 )$ decreases as the decrease of the reduced temperature,while $\lambda _ { c c } ( k )$ diverges when $k  0$ .It means $\lambda _ { \rho \rho } ( k = 0 )$ approaches to zero first as the decrease of $T ^ { * }$ for the fixed reduced temperature $\rho ^ { * }$ .The reduced temperature corresponding to the gas-fluid phase instability point $T _ { s } ^ { * }$ is obtained through extrapolating the values of $\lambda _ { \rho \rho } ( k = 0 )$ to zero.For example,see the solid curve in Fig. 1.

![](images/846b01a3cc82d455a2fef8ad8600c067ab32e6b174e45051b46037c25566a256.jpg)  
Fig.1 $\lambda _ { \rho \rho }$ ( $k = 0$ )forthe reduced temperatureat the reduced density $\rho ^ { * } = 0 . 0 4$ in RHNC approximation.The solid curve is the result of extrapolation,and $T _ { s } ^ { * }$ is the reduced temperature on spinodal line.

If $\lambda _ { \rho \rho } ( k )$ and $\lambda _ { c c } ( k )$ for $k \neq 0$ are considered, we can also study fluid-solid phase instability. In this article we study it.The curves in Fig.2 respectively correspond to $\lambda _ { \rho \rho } ( k )$ and $\lambda _ { c c } ( k )$ in RHNC approximation.

Figure 2 shows that the minimum values of $\lambda _ { \rho \rho } ( k )$ are always smaller than that of $\lambda _ { c c } ( k )$ for different reduced densities,and the minimum value of $\lambda _ { \rho \rho } ( k )$ approaches to zero first as the increase of the reduced density for the fixed reduced temperature $T ^ { * } ~ = ~ 1 . 0$ .To make it clearer，we summarize the minimum values of $\lambda _ { \rho \rho }$ and $\lambda _ { c c }$ for different reduced densities $\rho ^ { * }$ in Fig.3.The reduced density corresponding to the instability point $\rho _ { s } ^ { * }$ is obtained through extrapolating the minimum values of $\lambda _ { \rho \rho } ( k )$ to zero.A condensation phase transition happens at the value of reduced density $\rho _ { s } ^ { * }$ for $T ^ { * } ~ = ~ 1 . 0$ We also notice that $\lambda _ { \rho \rho } ( k )$ always goes to zero first. It's surely not a demixing transition (for which $\lambda _ { c c } ( k )$ goes to zero first） since the same type of ions cannot assemble together.In addition,Fig.2 shows that the minimum value of $\lambda _ { \rho \rho } ( k )$ occurs at $k \neq 0$ . Unlike the homogeneous phase instability indicated by $k = 0$ ,it denotes the fluidsolid phase instability caused by the density fluctuations $\rho _ { s } ^ { * } = 1 . 3 6 < \sqrt { 2 } = \rho _ { \mathrm { m a x } } ^ { * }$ ，and $\rho _ { \mathrm { m a x } } ^ { * }$ is the close packing reduced density,which implies our result is reasonable.

![](images/93e9ab82f781bdc01566ebefda2c0aa9aab15568cd031a34c2991f6381faae39.jpg)  
Fig.2 The comparison between $\lambda _ { \rho \rho } ( k )$ and $\lambda _ { c c } ( k )$ in RHNC approximation. $T ^ { * } = 1 . 0$ ， $\rho ^ { * }$ from 0.4 to 1.1 with increment of 0.1.

For $T ^ { * } ~ = ~ 0 . 0 5$ ，which is the reduced temperature lower than gas-fluid critical reduced temperature,we show $\lambda _ { \rho \rho } ( k )$ for different reduced densities in Fig.4. The minimum values of $\lambda _ { \rho \rho } ( k )$ occur at $k \neq 0$ for $\rho ^ { * } = 0 . 4 , 0 . 5 , 0 . 6$ while at $k = 0$ for $\rho ^ { * } = 0 . 2 2 , 0 . 2 6$ ：

The minimum values of $\lambda _ { \rho \rho } ( k )$ for different reduced density at $T ^ { * } = 0 . 0 5$ is shown in Fig. 5. For $\rho ^ { * } \leq 0 . 3$ the minimum values of $\lambda _ { \rho \rho } ( k )$ occur at $k = 0$ . The minimum value of $\lambda _ { \rho \rho } ( k )$ decreases as the reduced density decreases, and when it goes to zero,a homogeneous phase instability, i.e.gas-fluid phase instability happens.For $\rho ^ { * } > 0 . 3$ ，the minimum values of $\lambda _ { \rho \rho } ( k )$ occur at $k \neq 0$ ，and with the reduced density increasing the minimum value of $\lambda _ { \rho \rho } ( k )$ decreases and approaches to zero.At the point of $\lambda _ { \rho \rho } ^ { \mathrm { m i n } } = 0$ an inhomogeneous phase instability, i.e.fluid-solid phase instability, occurs.

![](images/c3e83d4dbd2eb9eb97bb51da2f152206b446a6910a6912751ee268eb5cbad8d0.jpg)  
Fig.3 The minimum value of $\lambda _ { \rho \rho } ( k )$ and $\lambda _ { c c } ( k )$ as the functions of the reduced density $\rho ^ { * }$ in RHNC approximation at the reduced temperature $T ^ { * } = 1 . 0$ . The solid curve is the result of extrapolation,and $\rho _ { s } ^ { * }$ is the reduced density on spinodal line.

![](images/b199737fef736e2a5e74d3967339625ef27de23334270db3ff7e1d4fea14a619.jpg)  
Fig.4 $\lambda _ { \rho \rho } ( k )$ at reduced temperature $T ^ { * } = 0 . 0 5$ and reduced densities $\rho ^ { * } = 0 . 2 2 , 0 . 2 6 , 0 . 4 , 0 . 5 , 0 . 6$ respectively in RHNC approximation.

Using the methods mentioned above we get the spinodal line of RPM. See Fig. 6. The $\rho _ { s } ^ { * } \leq 0 . 4$ region corre sponds to gas-fluid phase instability and $\rho _ { s } ^ { * } > 1 . 0$ region corresponds to fluid-solid phase instability. The RHNC integral function theory cannot give the result of the low temperature region between gas-fluid spinodal line and fluid-solid spinodal line possibly due to the complexity of triphasic coexistence. Comparing our result with the computer simulation results (Fig.6 in Ref.[7]),we find that our result of gas-fluid phase transition fits the simulation result very well, but for fluid-solid phase transition our result is only qualitatively consistent with the simulation.

It reveals that the RHNC approximation does not work well for high reduced densities.

![](images/6c1a9ac606d15e126c1f5a31b520ba9070d9e2ae0aa002d6a7075f8b2b1d3fdd.jpg)  
Fig.5The minimum values of $\lambda _ { \rho \rho } ( k )$ as the function of the reduced density $\rho ^ { * }$ with the reduced temperature $T ^ { * } = 0 . 0 5$

![](images/fb8cc356e263e9de330164b6b3df67e06649e6ba49a75b824de5db289a828187.jpg)  
Fig.6 The spinodal curve for the RPM in RHNC approximation.

# 6Conclusions

In this paper we use the integral equation theory in the reference hypernetted chain approximation to analyse the gas-fluid and fluid-solid phase instability of the restricted primitive model of ionic liquids.

Our analysis is based on the correlation functions of the fluid mixture. The correlation functions are calculated in the framework of integral equation theory. The integral equation contain two equations: the OrnsteinZernike equation and the closure. RHNC approximation is applied as the closure approximation.We use the iteration method to solve the integral equation and then we can obtain the direct and total ion-ion correlation functions.

We discuss the phase stability of a system by the grand potential fluctuation around equilibrium with respect to small one-particle density fluctuations in detail. The grand potential fluctuation is a quadratic form of density fluctuations and the coefficient matrix can be expressed by the direct correlation functions of the system. This matrix can be diagonalized by its eigenvalues and eigenvectors. Once one of the eigenvalues goes to zero, the system becomes unstable and the related eigenvector characterizes the phase instability uniquely.

For RPM there are two kinds of eigenvalues $\lambda _ { \rho \rho } ( k )$ and $\lambda _ { c c } ( k )$ .Using the correlation functions obtained from the RHNC integral equation theory, we can calculate $\lambda _ { \rho \rho } ( k )$ and $\lambda _ { c c } ( k )$ at different reduced densities and temperatures. If $\lambda _ { \rho \rho } ( k )$ goes to zero first, it denotes a condensa tion phase instability caused by the density fluctuations. If $\lambda _ { c c } ( k )$ goes to zero first,it denotes a demixing phase instability caused by the concentration fluctuations.

Fora given reduced temperature and density,the minimum value of $\lambda _ { \rho \rho } ( k )$ is smaller than that of $\lambda _ { c c } ( k )$ ，and the minimum value of $\lambda _ { \rho \rho } ( k )$ goes to zero first.It means that the phase instability ofRPM is a condensation phase transition caused by the density fluctuation.

Further investigation shows that if the minimum value of $\lambda _ { \rho \rho } ( k )$ becomes zero at the fluctuation mode of $k \neq 0$ this phase instability is fluid-solid phase instability. On the other hand, if the minimum value of $\lambda _ { \rho \rho } ( k )$ becomes zero at the fluctuation mode $k = 0$ ，this phase instabilityis a homogeneous condensation phase instability,i.e. gas-fluid phase instability.

Under the integral equation theory the minimum value of $\lambda _ { \rho \rho } ( k )$ cannot arrive at zero but very close.The spinodal line of RPM is obtained by extrapolating the minimum value of $\lambda _ { \rho \rho } ( k )$ to zero.Comparing our result with the phase diagram derived from computer simulation,we find that our result is qualitatively consistent with the result of simulation,and at the low reduced densities where gas-fluid phase instability occurs,our result fits the simulation very well.

# Acknowledgments

We would like to thank A.M. Xiong，L. Luo，and L.S.Li for useful discussions.

# References

[1] M.E.Fisher,J. Stat.Phys.75(1994)1.   
[2] F.H. Stillinger and R. Lovett,J.Chem. Phys.48(1968) 3858.   
[3] J.L.Barrat,J. Phys.C 20（1987)1031.   
[4] B.Smit，K.Esselink，and D.Frenkel，Mol.Phys.87 (1996) 159.   
[5] C.Vega, F.Bresme,and J.L.F.Abascal, Phys.Rev. E 54 (1996)2746.   
[6] F.Bresme, C. Vega,and J.L.F.Abascal, Phys.Rev. Lett. 85(2000) 3217.   
[7] C.Vega, J.L.F. Abascal, C.McBride,and F. Bresme, J. Chem.Phys.119(2003)964.   
[8] J.L.Lebowitz and J.K.Percus,J. Math.Phys.4(1963) 116.   
[9] W.F. Saam and C. Ebner, Phys.Rev. A 15 (1977) 2566.   
[10] J.P.Hansen and I.R.McDonald,Theory of Simple Liquids,Academic Press,London (1986).   
[11]F.Lado,Phys.Rev.A 135(1964)1013.   
[12] F. Lado,Mol. Phys.31(1976) 1117.   
[13]L.Verlet and J.J.Weis,Phys.Rev.A 5(1972) 939.   
[14] D.Henderson and E.W.Grundke,J.Chem.Phys.63 (1975)601.   
[15] J.M.Caillol,D.Levesque,and J.J.Weis,Mol. Phys.69 (1990)199.   
[16] X.S. Chen and F. Forstmann,Condens.Matter Phys.4 (2001) 679.