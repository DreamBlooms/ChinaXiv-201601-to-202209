# Power Transfer Coefficients Between Two 3D Semi-lnfinite Solids in EFEA Formulation

Xiliang Chen1,a and Wenwu Zhang1.b

1Ningbo Institute of Materials Technology & Engineering, Chinese Academy of Sciences, China achenxl@nimte.ac.cn,bzhangwenwu@nimte.ac.cn

Keywords:EFEA,Power Transfer Coefficients,3D Solid,Wave.

Abstract. The energy finite element analysis (EFEA) is more effective for analyzing high frequency vibration problem compared to the traditional finite element method (FEM). When applying the EFEA to complicated structures, it is necessary to obtain power transfer coefficients at structural joints.This paper proposes the theoretical formulations of computing power transfer coefficients between two 3D semi-infinite solids,and demonstrates the validation of the developed theoretical formulations through two examples with diferent incident waves: dilatational wave and distortional wave.

# Introduction

For high frequency vibration problem of complicated structures,the traditional finite element method (FEM) needs much high dense elements because the size of elements is required smaller than the wavelength of vibration wave. Thus, the FEM takes much long computational time for complicated structures. Sometimes, the FEM cannot reach accuracy results and even cannot obtain results. To overcome the inherent drawback of the FEM, the energy finite element analysis (EFEA) has been developed [1]. The primary variable--energy density in the EFEA is discontinuous at locations of discontinuities with a single member or at positions where different member are connected. Hence, a special approach based on the continuity of power flow acrossthe joints is developed to form global system equation at the joints [2]. This continuity is expressed in terms of power transfer coefficients in the EFEA. When applying the EFEA to such structures, it is necessary to obtain power transfer coefficients at structural joints.

The power transfer coefficients among plates or at the joints between plates and beam have been developed [3]. This paper proposes the theoretical formulations of computing power transfer coefficients between two 3D semi-infinite solids,and demonstrates the validation of the developed theoretical formulations.

# Theoretical Formulations

For the simplicity of deriving equations, we let the $x { - } z$ plane in the wave propagation plane, and $y$ -axis is perpendicular to the $x { - } z$ plane and outward. In the 3D solids, two types of waves: dilatational and distortional waves can propagate.

Define $\Phi = \frac { \partial u } { \partial x } + \frac { \partial \nu } { \partial y } + \frac { \partial w } { \partial z }$ as a scalar quantity that is called the dilatation, which corresponds to the dilatational motion of particles. Define $\vec { \psi } = \nabla \times \vec { \bf u }$ as a vector quantity representing the displacement potential which corresponds to the rotational motion of particles. $\vec { \mathbf { u } } = u \vec { i } + \nu \vec { j } + w \vec { k }$ is displacement vector. $\nabla \bullet \vec { \psi } = 0$ is satisfied for vector quantity $\vec { \psi }$ ：   
From the partial diferential equations of motion for free vibrations in a homogeneous isotropic elastic 3D solid, the following second-order partial differential equation (PDE) for the dilatation is obtained:

$\nabla ^ { 2 } \Phi = \frac { 1 } { C _ { L } ^ { 2 } } \frac { \partial ^ { 2 } \Phi } { \partial t ^ { 2 } } ,$ where $C _ { _ L } = \sqrt { \frac { \lambda + 2 \mu } { \rho } }$ u is wave speed of dilatational wave. （20 Similarly, the following PDE for the distortional wave is obtained:

$$
\nabla ^ { 2 } \vec { \psi } = \frac { 1 } { C _ { s } ^ { 2 } } \frac { \partial ^ { 2 } \vec { \psi } } { \partial t ^ { 2 } } ,
$$

where $C _ { s } = { \sqrt { \frac { \mu } { \rho } } }$ is wave speed of distortional wave.

We suppose one dilatational plane wave (Fig. la) with heading to the interface $\phi _ { L i }$ or one distortional plane wave (Fig. 1b) with heading to the interface $\phi _ { S i }$ incidents in the upper 3D semi-infinite elastic isotropic solid. When the wave goes through the interface between the two 3D semi-infinite elastic isotropic solids, part of wave transmits in the lower 3D semi-infinite solid.Part of wave reflects back in the upper 3D semi-infinite solid. The transmitted and reflected waves may include both dilatational and distortional waves regardless the incident wave is dilatational or distortional wave.

![](images/2e04b9be88ed2f8a0afcbf49e1bc4ea5e32a6805a548fa14fa33f47aa8dd0081.jpg)  
Fig.la A dilatational incident wave and its transmitted and reflected waves

![](images/c5925966e5fec23076db90970f053223beb5db67fca18b3cdedcaa5da4c83660.jpg)  
Fig.1b A distortional incident wave and its transmitted and reflected waves

We assume that the scalar and vector quantities for incident, transmited and reflected waves as follows:

(a)For he icident wave, $\Phi _ { 1 } = \alpha _ { _ { I 1 } } e ^ { - i k _ { _ { I x 1 } x } - i k _ { _ { I y 1 } y } + \mu _ { _ { I 1 } z } + i \omega t } , \vec { \psi } _ { 1 } = \vec { \alpha } _ { _ { s 1 } } e ^ { - i k _ { _ { s x 1 } x } - i k _ { _ { s y 1 } y } + \mu _ { _ { s 1 } z } + i \omega t } .$ （20   
(b)Forthe trasmitted wave,Φ=ekx-ikyyit ( $\Phi _ { 2 } ~ = ~ e ^ { - i k _ { x 2 } x - i k _ { l x 2 } y + i \omega t } ( c _ { 1 } e ^ { \mu _ { l 2 } z } ) , \vec { \psi } _ { 2 } ~ = ~ e ^ { - i k _ { s x 2 } x - i k _ { s y 2 } y + i \omega t } ( \vec { d } _ { 1 } e ^ { \mu _ { s 2 } z } )$ (c) For the reflected wave, $\Phi _ { 3 } \ = \ \alpha _ { I 3 } e ^ { - i k _ { l x 3 } x - i k _ { l y 3 } y - \mu _ { l 3 } z + i \omega t } , \vec { \psi } _ { 3 } \ = \ \vec { \alpha } _ { s 3 } e ^ { - i k _ { s x 3 } x - i k _ { s y 3 } y - \mu _ { s 3 } z + i \omega t } .$ We assume that all the components of wave numbers of waves in the $x$ direction are the same.The totality of waves in the upper 3D solid is $\Phi ^ { + } = \Phi _ { \mathrm { { 1 } } } + \Phi _ { \mathrm { { 3 } } }$ ， $\vec { \psi } ^ { + } = \vec { \psi } _ { \scriptscriptstyle 1 } + \vec { \psi } _ { \scriptscriptstyle 3 }$ .The totality of waves in the lower 3D solid is $\Phi ^ { - } = \Phi _ { \mathrm { 2 } } , \vec { \psi } ^ { - } = \vec { \psi } _ { \mathrm { 2 } }$ ：   
There are eight unknown complex amplitudes.In order to solve the eight unknowns, we need to employthe six boundary conditions (displacements continuity and stresses continuity)in the interface （ $z = 0$ ) and two distortional wave requirements [4]: $\nabla \bullet \vec { \psi } ^ { + } = 0 , \nabla \bullet \vec { \psi } ^ { - } = 0$ ,where superscript （20 $^ { 6 6 } + ^ { , 9 }$ denotes that the terms belong to the upper solid while superscript“-” means that the terms belong to the lower solid.   
The eight unknown complex amplitudes can be solved out by employing the eight equations: the relationships between strains and displacements,the relationships between stresses and strains. Once the complex amplitudes of waves are obtained, the displacements of particles can be calculated using the following equation:

$$
\vec { \mathbf { u } } ( x , y , z , t ) = \nabla \Phi ( x , y , z , t ) + \nabla \times \vec { \psi } ( x , y , z , t )
$$

The power transfer coefcients can be calculated by the ratio of the power transmitted by the generated wave to the total incident wave power on the interface for a specific type wave with frequency $\omega$ and heading to the interface $\phi \left[ 3 \right]$ ：

$$
\begin{array} { r } { \tau _ { p r } ^ { i j } ( \omega , \phi ) = \frac { P _ { r } ^ { j } ( \omega , \phi ) } { P _ { p } ^ { i } ( \omega , \phi ) } } \end{array}
$$

where the indexes $p , \stackrel { \textstyle , } { r } , i , j$ represent the incident wave type, the transmitted or reflected wave type, the medium carrying incident wave, the medium carrying transmitted wave, respectively $( j = i$ represents carrying reflected wave). We use “L” to represent dilatational wave type and $^ { 6 6 } { \mathrm { S } } ^ { 3 }$ for distortional wave type.

Since the total power which is incident on the interface equals the total power which is carried away by the generated waves, the conservation of energy requires that $\textstyle \sum \tau = 1$ [3].

# Validation of Theoretical Formulations

The developed theory for calculation of power transfer coefficients are validated through some examples.

In the examples, Poisson's ratio is $\nu = 0 . 2 5$ . The ratio of density in the upper solid to the lower solid is $\rho _ { { } _ { 2 } } / \rho _ { { } _ { 1 } }$ . The ratio of group speed of dilatational wave in the upper solid to that in the lower solid is $C _ { L 2 } / C _ { L 1 }$ . Heading of the incident wave is $\phi$

Table 1 Power Transfer Coefficients (Dilatational Incident Wave)   

<html><body><table><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>Mt</td><td></td></tr><tr><td rowspan="2">P/ p =1.0 C[2/CL1 = 0.5 =60°</td><td>Present</td><td>0.8485</td><td>0.0475</td><td>0.0454</td><td>0.0586</td><td>1.0000</td><td rowspan="2">Lr Sr St</td></tr><tr><td>Ref[5]</td><td>0.8484</td><td>0.0475</td><td>0.0454</td><td>0.0586</td><td>0.9999</td></tr><tr><td rowspan="2">P/p = 0.7 CL2/CL = 2.0 =90°</td><td>Present</td><td>0.9722</td><td>0</td><td>0.0278</td><td>0</td><td>1.0000</td><td>Li</td></tr><tr><td>Ref[5]</td><td>0.9722</td><td>0</td><td>0.0278</td><td>0</td><td>1.0000</td><td>Lt</td></tr><tr><td rowspan="2">P/p =1.3 CL2/CL = 2.0 =60°</td><td>Present</td><td>0</td><td>0.0696</td><td>0.8852</td><td>0.0452</td><td>1.0000</td><td rowspan="2">L Sr St Li</td></tr><tr><td>Ref[5]</td><td>0</td><td>0.0695</td><td>0.8853</td><td>0.0452</td><td>1.0000</td></tr></table></body></html>

Table 2 Power Transfer Coefficients (Distortional Incident Wave)   

<html><body><table><tr><td></td><td></td><td></td><td></td><td></td><td>t</td><td>Mt</td><td></td></tr><tr><td rowspan="2">P/ p =1.3 CL2/CL = 2.0 𝜙 = 78.6111°</td><td>Present</td><td>0.0951</td><td>0.7702</td><td>0.0463</td><td>0.0884</td><td>1.0000</td><td rowspan="2">S St LS,</td></tr><tr><td>Ref[5]</td><td>0.0951</td><td>0.7702</td><td>0.0464</td><td>0.0884</td><td>1.0001</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">P/ p =1.3 CL2/CL1 = 2.0 =90°</td><td>Present</td><td>0</td><td>0.8025</td><td>0</td><td>0.1975</td><td>1.0000</td><td rowspan="2">Si S</td></tr><tr><td>Ref[5]</td><td>0</td><td>0.8025</td><td>0</td><td>0.1975</td><td>1.0000</td></tr><tr><td rowspan="2">CL2/CL = 2.0 Φ= 73.2208° P/p=1.3</td><td>Present</td><td>0</td><td>0.8990</td><td>0.0453</td><td>0.0557</td><td>1.0000</td><td rowspan="2">LS S St</td></tr><tr><td>Ref[5]</td><td>0</td><td>0.8991</td><td>0.0452</td><td>0.0556</td><td>0.9999</td></tr></table></body></html>

The results are listed in Table 1 for dilatational incident wave and in Table2 for distortional incident wave. In Tables and2, $\tau _ { L L } ^ { 1 2 } , \tau _ { L S } ^ { 1 2 } , \tau _ { S L } ^ { 1 2 } , \tau _ { S S } ^ { 1 2 }$ aretra $\tau _ { L L } ^ { 1 1 }$ ， $\tau _ { L S } ^ { 1 1 }$ ， $\tau _ { S L } ^ { 1 1 }$ ， $\tau _ { S S } ^ { 1 1 }$ are reflected power coefficients,where the first subscript denotes incident wave type, the second subscript denotes the transmited or reflected wave type.“L” represents dilatational wave type and “S" represents distortional wave type.

# Conclusions

The developed theory and program can simulate wave propagation in 3D semi-infinite elastic medium very well. When a dilatational or distortional wave goes through the interface between two 3D semi-infinite mediums, both transmitted and reflected waves or part of them generate. The generated waves are both dilatational and distortional waves or part of them. Power carried away by the transmited and reflected waves equals to the total power carred in by the incident wave as expected.

# References

[1] W.G. Zhang, A.M. Wang, N. Vlahopoulos， An alternative energy finite element formulation based on incoherent orthogonal waves and its validation for marine structures, Finite Elements in Analysis and Design Vol. 38 1095-1113 (2002).   
[2] X.Y. Yan, Energy finite element analysis developments for high frequency vibration analysis of composite structures, PhD dissertation of Dept. of Naval Architecture and Marine Engineering, The University of Michigan (2008).   
[3] R.S.Langley and K.H. Heron, Elastic wave transmission through plate/beam junctions, Journal of Sound and Vibration Vol.143(2) 241-253(1990).   
[4] P.Borejko,Reflection and transmission coeficients for three-dimensional plane waves in elastic media, Wave Motion Vol.24 371-393(1996).   
[5] M.Muskat and M.W. Meres,Reflection and transmission coefficients for plane waves in elastic media, Geophysics Vol. 115-148 (1940).