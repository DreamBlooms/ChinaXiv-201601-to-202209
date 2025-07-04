# Hydrofluoric acid-based etching effect on the surface pit, crack, scratch, and laser damage site of fused silica optics

Taixiang Liu, Ke Yang, Zhuo Zhang, Lianghong Yan, Beicong Huang, Heyang Li, Chuanchao Zhang, Xiaodong Jiang, Hongwei Yan\*

Laser Fusion Research Center, CAEP, Mianyang 621900, P. R. China.

Abstract Large-scale, high-power laser facility is currently a basis for the research of inertial confinement fusion (ICF). In the laser facility， fused silica opticsplays irreplaceable role to conduct extremely high-intensity ultraviolet laser to fusion target. However, the surface fractures,such as surface pit, crack, scratch,and laser damage site, of the optics will lower the beam quality of transmitted laser, weaken the laser damageresistance, shorten the lifetime of the optics, and thus limit the output performance of the laser facility. In this work, to mitigate the surface fractures,hydrofluoric acid-based (HFbased) etching effect on the surface fractures is experimentally and theoretically studied. From the experimental study，with the result of three-dimensional (3D) morphological evolution of surface fractures, it is shown that the surface fractures will be passivated and their profiles will get smoothed after etching, indicating HF-based etching is a promising way to improve the local surface quality of the fractures. Especially, it is found HF-based etching can greatly suppress the laser damage growth of laser damage site by mitigating its surface and subsurface fractures,and thus is a promising wet chemical method for repairing laser-induced damage optics. In the theoretical study,an explicit local-curvature dependent etching model is proposed. Based on this model, the result from finite difference time domain (FDTD） simulation agrees very well with that of experiment, which can reveal the detailed physical process of HF-based etching. It is demonstrated that the FDTD simulation can be a reliable and eficient way to predict the morphological evolution of the surface fractures during etching.

Key words: fused silica; HF-based etching; surface fracture; morphological evolution; finite difference simulation

# 1.INTRODUCTION

Large-scale， high-power laser facilities, such as National Ignition Facility[1] in America，SG series laser facility[2] in China,Laser Megajoule Facilityl3] in France,Iskra-6 facility[4] in Russia, Extreme Light Infrastructure[5,6]， etc.， are acting as the pioneers researching extremely highenergy-density physics (HEDP). In the research of HEDP, laser-supported inertial confinement fusion (ICF) is a major concern. One mission of the ICF research is to make fusion energy usable and controllable to meet the energy demand of the developing world in the next hundreds or thousands years.For achieving ICF,the output performance of the large high-power laser facilities is a crucial factor. In the facilities,for enhancing the output capability,large amount of fused silica optics components with excellent-surface-quality and high-laser-damage-resistance are much demanded, as the optics will withstand the radiation of extremely intense laser and work near or above their laser-induced surface damage threshold.

While the intrinsic laser-induced surface damage threshold of fused silica optics is higher than $1 0 0 \ \mathrm { J / c m ^ { 2 } }$ ， the optics typically exhibit laser damage when exposed to $3 5 1 ~ \mathrm { n m }$ ，3 ns laser pulses at fluences from $5 { - } 1 5 ~ \mathrm { J } / \mathrm { c m } ^ { 2 }$ depending on the finishing or post processing[7]. It is believed that when the fluence of laser is less than $1 0 \ \mathrm { J } / \mathrm { c m } ^ { 2 }$ ， surface fractures of fused silica optics are the most common native laser damage precursors[8]. In other words, the surface fractures, such as surface pit, crack, scratch, and preexisting laser damage site, will lower the beam quality of conducted laser beam, weaken the laser damage resistance and shorten the lifetime of the optics, and thus greatly limit the output performance of the laser facility. Fig.1 shows examples of micron-sized surface fractures with complicated morphology on the surface of fused silica optics after daily use.The surface fractures are pernicious when exposed to extremely intense laser irradiation， then hazardous to the expensive fused silica optics,and thus hinder the daily operation of the laser facility. Therefore, it is very imperative to mitigate the surface fractures

![](images/cc461ed72035f9b92a8d10ce225d32498ff39e7a0ff5291f134d735f0d80e657.jpg)  
Fig.1.Complicated morphology of surface (A)pit,crack,scratch,and (B)laser damage sites offused silica optics

To mitigate the surface fractures, there are mainly two ways for consideration. One way is so-called“dry physical etching”, such as ion beam etchingl9],reactive ion beam etching[10], ultra-fine surface finishing[1], laser polishing[12], etc.A shortcoming of the “dry” way is its low efficiency when processing meter-sized optics in industrialization mode. The other more efficient way is so-called “wet chemical etching",e.g. using hydrofluoric (HF) acid-based solution to etch the surface fractures.Historically, in 1771，Scheele first prepared HF acid and probably discovered it etches silicate glasses[13]. More than 5O years later, Berzelius found the reaction products of the reaction between $\mathrm { S i O } _ { 2 }$ and HF to be tetrafluorosilane and water[14].Today, it is known that the overall chemical reaction of $\mathrm { S i O } _ { 2 }$ in dilute HF solution can be simply summarized as:

$$
\mathrm { S i O } _ { _ { 2 ( s o l i d ) } } + 6 \mathrm { H F } _ { ( a q ) }  \mathrm { S i F } _ { 6 ( a q ) } ^ { 2 - } + 2 \mathrm { H } _ { ( a q ) } ^ { + } + 2 \mathrm { H } _ { 2 } \mathrm { O } _ { ( a q ) } .
$$

When the fraction of HF in a water solution become larger, there are $\mathrm { H + }$ ，F-，HF, $\mathrm { H F } _ { 2 } ^ { - }$ ，and （204 $\mathrm { H } _ { 2 } \mathrm { F } _ { 2 }$ in the solution,as HF is a weak acid and is not fully dissociated. The equilibrium constants between the species at $2 5 \ \mathrm { { ^ \circ C } }$ are:[14]

$$
\begin{array} { r l } & { [ \mathsf { H } ^ { + } ] [ \mathsf { F } ^ { - } ] \big / [ \mathsf { H F } ] = 6 . 8 5 \times 1 0 ^ { - 4 } \mathrm { ~ m o l / L } , } \\ & { [ \mathsf { H F } _ { 2 } ^ { - } ] \big / [ \mathsf { H F } ] [ \mathsf { F } ^ { - } ] = 3 . 9 6 3 \times 1 0 ^ { - 4 } \mathrm { ~ L / m o l } , } \\ & { [ \mathsf { H } _ { 2 } \mathsf { F } _ { 2 } ] \big / [ \mathsf { H F } ] ^ { 2 } = 2 . 7 \mathrm { ~ L / m o l } . } \end{array}
$$

Above chemical reaction makes the surface fractures of the optics dissolve in HF-based solution It has been demonstrated that HF-based etching process can improve the laser damage resistance of fused silica optical surfaces[7,15]. The wet chemical etching is efficient for producing metersized optics with high laser damage resistance and this method has been patented[16l.Recently, the wet chemical etching has been developed using ${ \mathrm { H F / H N O } } _ { 3 }$ or KOH as the etchant[17] and it was demonstrated the laser-damage resistance and surface quality of fused silica optics can be highly improved.

Nevertheless, the detailed morphological evolution of surface fractures during HF-based etching, which improves the surface quality and the laser-damage resistance of optics,is still not clearly known. There are two main reasons resulting in this problem. First, it is dificult and dangerous to in situ track the evolution of surface fractures when the optics is immersed in HFbased solution. Second, the detailed etching mechanism or reaction kinetics of silica glass dissolving in HF-based solution is very complicated and has not been deeply revealed[14,18]. To study the morphological evolution of the surface fractures of fused silica during wet chemical etching,Wong et al.[19] and Feit et al.[20] from Lawrence Livermore National Laboratory have done the pioneering works to model the etching process using finite difference simulation.

To move this research forward, in this work, the morphological evolution of surface fractures during HF-based etching is experimentally and theoretically studied. A local-curvaturedependent etching model is firstly proposed and the simulation result, as well as experimental result, is given. This paper is organized as follows.In section 2, experimental detail of HF-based wet chemical etching is given. In section 3,analytical model of the etching process is proposed and finite difference time domain (FDTD） simulation is performed. Then the results from experiment and simulation are comparatively shown and discussed in section 4. Finally, section 5 gives a summary of this work.

# 2.EXPERIMENTAL

For tracking the morphological evolution of surface fractures,round fused silica optics sample (type: D160, provided by Languang Optical Technology Co.,Ltd, China) with the density of 2.24 $\mathrm { g } / \mathrm { c m } ^ { 3 }$ ， the diameter of $5 0 . 0 \ \mathrm { m m }$ ， and the thickness of $5 . 0 \ \mathrm { m m }$ is used for HF-based etching experiment. Several pits are indented on the surface of the sample by using hardness tester (type: LAIHUA HVT-1000A） with indenting force load from 0.098 to $2 . 9 4 ~ \mathrm { N }$ ，Surface cracks with micron-sized depth and surface scratches with millimeter-sized length are found initially on the surface of the sample. The laser damage sites are generated by $3 5 5 ~ \mathrm { n m }$ ,6.3 ns, $\sim 1 5 ~ \mathrm { J / c m } ^ { 2 }$ laser shot.A buffered HF-based solution is prepared with $2 . 4 \%$ HF, $12 . 0 \%$ （204号 $\mathrm { N H _ { 4 } F }$ ，and $8 5 . 6 \%$ superpure water in weight fraction.

The initial sample is immersed in the HF-based solution for 5.0 minutes for wiping off the surface hydrolysis layer. Then the etching process is conducted with successively phased etching time of 0.5,1.0,1.0,1.0,and 2.0 hrs. In other words, the accumulate etching time is 0.5, 1.5,2.5,3.5,5.5 hours, successively. For surface laser damage site, the total etching time is 24.0 h. During etching,a mega-sonic agitation with the frequency of $1 . 3 0 ~ \mathrm { M H z }$ is applied at the bottom of the etchant container. Before every phase of etching process, the fused silica optics sample is rinsed in pure water with sweeping $4 0 – 2 7 0 ~ \mathrm { k H z }$ ultrasonic agitation for 30.O minutes. The etching experiment is conducted at room temperature of $2 3 . 0 \pm 1 . 0 \mathrm { ~ \overset { \circ } { C } }$ and relative humidity of $45 \pm 5 \%$ . After every etching phase, the two-dimensional morphological characterization of the concerned surface fracture is acquired by using optical microscopy (custom type by Nikon Inc.). The three-dimensional (3D) profile of the surface fractures is quantitatively measured by using atomic force microscopy (AFM， type: XEI-100，produced by PSIA Inc.） or 3D profilometer.

# 3.MODELING THEETCHING PROCESS

In this section, two kinds of etching model will be proposed. One is for isotropic etching and the other is for local-curvature-dependent etching. When fused silica optics with surface fractures is submerged into HF-based solution, the wet chemical etching is triggered.

![](images/1f8a04d50103f989fcd9197818c31b3d1f7624b637fc23aff4f7ba6db5dbec55.jpg)  
Fig.2.Ilustration of the wet chemical etching system.

![](images/b4ce26780647beee91b331442b46b4038933a976bb5c045ec26e405f3baeda3c.jpg)  
Fig.3.Meshed surface referring to a fixed reference frame.

One can have a basic recognition of the etching system, or for example, a simple illustration of the etching system is shown in Fig.2. The middle rugged curve denotes the surface fractures of the fused silica optics which are submerged into the upper HF-based solution. The arrows indicates the etching direction which are opposite to the normal vector of local surface. When the spatial frequency of local surface is considerably low, e.g. the surface is smooth enough as shown in the left half ofFig.2,the etching can be thought as isotropic.In other words, the etching rate at any position of the surface is uniform. However, it is important to point out that when the spatial frequency is considerably high, e.g. the surface is rough enough as shown in the right half of Fig. 2, the etching will not be isotropic. In this case,the etching rate at different position of the surface is highly local-curvature-dependent. One can have an intuitive image that the etching rate at a sharply peak point will be larger than that at a valley point. This phenomenon result from the reaction product of etching at the peak point can timely diffuse into its ambient solution, while that at the valley point is relatively difficult to diffuse into its ambient solution.

To model a surface fracture of fused silica optics, one can use a 3D grid to simulate the surface fracture if the grid is fine enough. Fig. 3 shows an example of meshed surface and its top projection to the ground fixed reference frame. The reference frame does not change during the variation of the meshed surface. The introduction of the fixed reference frame aims to avoid the problem of numerical divergence in FDTD simulation.

# 3.1 Isotropic etching

For a surface point $P _ { 0 }$ at the time of $t _ { 0 }$ , it evolves to a new position locates at point $P _ { 1 }$ after a very short etching time of $\delta _ { t }$ , i.e. at a new time of $t _ { 1 }$ . The point $P _ { 1 }$ can be regarded as being from $P _ { 0 }$ along the opposite direction of the local normal vector $\pmb { n }$ at point $P _ { 0 }$ at the time $t _ { 0 }$ ： Then the spacial relationship between $P _ { 1 }$ and $P _ { 0 }$ can be built as:

$$
P _ { 1 } = P _ { 0 } + E _ { r } ( t _ { 0 } ) \cdot ( t _ { 1 } - t _ { 0 } ) \cdot ( - \pmb { n } ) .
$$

In which, $E _ { r } ( t _ { 0 } )$ is not a position-dependent, but time-dependent etching rate. Eq. (5) is the basic

formula to model the wet chemical etching process. In Cartesian reference frame, Eq.(5) can be decomposed as:

$$
\begin{array} { r } { \begin{array} { r l } & { x _ { 1 } = x _ { 0 } - E _ { r } ( t _ { 0 } ) \cdot \delta _ { t } \cdot n _ { x } , } \\ & { } \\ & { y _ { 1 } = y _ { 0 } - E _ { r } ( t _ { 0 } ) \cdot \delta _ { t } \cdot n _ { y } , } \\ & { } \\ & { z _ { 1 } = z _ { 0 } - E _ { r } ( t _ { 0 } ) \cdot \delta _ { t } \cdot n _ { z } . } \end{array} } \end{array}
$$

Here, $\delta _ { t } = t _ { 1 } - t _ { 0 }$ ： $x _ { 1 } , y _ { 1 }$ and $z _ { 1 }$ are the positional projections of $P _ { 1 }$ to the reference frame, while the positional projections of $P _ { 0 }$ are respectively $x _ { 0 } ~ , ~ y _ { 0 }$ and $z _ { 0 } ~ { \cdot } ~ n _ { { } _ { x } } ~ , ~ n _ { { } _ { y } }$ and $n _ { z }$ are the directional components of the normal vector $\pmb { n }$ and it has $\sqrt { n _ { x } ^ { 2 } + n _ { y } ^ { 2 } + n _ { z } ^ { 2 } } = 1$ . The function $E _ { r } ( t )$ and the parameter $\delta _ { { _ t } }$ can be set according to result of experiment. The following gives the determination of the local normal vector.

![](images/0eab7fd7a26ba4cac41b1d86bcb9a31f25e1997b8d06557a106a778377e89700.jpg)  
Fig. 4.A surface point P relating to its neighbor points.

As is shown in Fig. 4, for a surface point $\mathrm { \bf P }$ with its neighbor points A, B, C,and D, the local normal vector at point $\mathrm { \bf P }$ can be determined as:

$$
\pmb { n } = \frac { \pmb { n } _ { 1 } + \pmb { n } _ { 2 } + \pmb { n } _ { 3 } + \pmb { n } _ { 4 } } { \left| \pmb { n } _ { 1 } + \pmb { n } _ { 2 } + \pmb { n } _ { 3 } + \pmb { n } _ { 4 } \right| } .
$$

In which, ${ \pmb n } _ { 1 } , { \pmb n } _ { 2 } , { \pmb n } _ { 3 }$ ,and ${ \pmb n } _ { 4 }$ are the unit normal vector of surface 1, 2, 3,and 4, respectively. It has:

$$
 \pmb { n } _ { 1 } = \frac { \overrightarrow { P A } \times \overrightarrow { P B } } { | \overrightarrow { P A } \times \overrightarrow { P B } | } \ \pmb { n } _ { 2 } = \frac { \overrightarrow { P B } \times \overrightarrow { P C } } { | \overrightarrow { P B } \times \overrightarrow { P C } | } ,
$$

$$
{ \pmb n } _ { 3 } = \frac { \overrightarrow { P C } \times \overrightarrow { P D } } { \left| \overrightarrow { P C } \times \overrightarrow { P D } \right| } , { \pmb n } _ { 4 } = \frac { \overrightarrow { P D } \times \overrightarrow { P A } } { \left| \overrightarrow { P D } \times \overrightarrow { P A } \right| } .
$$

Equation (5) can be solved by using finite difference time domain method.

# 3.2 Local-curvature-dependent etching

When the spatial frequency of surface fracture is considerably high,i.e. the surface fracture is rough enough, wet chemical etching is local curvature dependent. It is imperative to modify the basic formula Eq.(5) to fit this case. For a 3D spatial surface $S ( x , y )$ ,here the $S$ is the surface height corresponding the position $( x , y )$ . Set:

$$
u = \frac { \partial S } { \partial x } , \nu = \frac { \partial S } { \partial y } ,
$$

$$
E = 1 + u ^ { 2 } , F = u \nu , G = 1 + \nu ^ { 2 } ,
$$

$$
L = \frac { \displaystyle \frac { \hat { \sigma } u } { \hat { \sigma } x } } { \sqrt { 1 + u ^ { ' } + \nu ^ { 2 } } } , ~ N = \frac { \displaystyle \frac { \hat { \sigma } \nu } { \hat { \sigma } y } } { \sqrt { 1 + u ^ { ' } + \nu ^ { 2 } } } ,
$$

$$
M = \frac { \displaystyle \frac { \partial \nu } { \partial x } } { \sqrt { 1 + u ^ { 2 } + \nu ^ { 2 } } } = \frac { \displaystyle \frac { \partial u } { \partial y } } { \sqrt { 1 + u ^ { 2 } + \nu ^ { 2 } } } ,
$$

and the curvature of the local surface at position $( x , y )$ can be derived as: [21]

$$
C _ { m } = \frac { E N - 2 F M + G L } { 2 ( E G - F ^ { 2 } ) } .
$$

The above curvature is used for modifying the basic Eq. (5) in the following formulas.

In the present study, the following formula is introduced to build the relationship between the local etching-rate and local-surface-curvature:

$$
E _ { l c } = B _ { d } \cdot E _ { r } ,
$$

in which, $E _ { \scriptscriptstyle { l c } }$ is the local curvature-dependent etching rate, $E _ { r }$ is the etching rate on ideal flat surface of optics. Here, we propose the adaptive coefficient $B _ { d }$ on the right side of the equation with the following expression:

$$
B _ { d } = A _ { 0 } + ( A _ { 0 } - A _ { 1 } ) \cdot \left\{ 1 - \left[ \frac { p } { 1 + 1 0 ^ { ( \log x _ { 1 } - C _ { m } ) \cdot h _ { 1 } } } + \frac { 1 - p } { 1 + 1 0 ^ { ( \log x _ { 2 } - C _ { m } ) \cdot h _ { 2 } } } \right] \right\}
$$

Here, $A _ { 1 } \geq 1 . 0$ is set as the ratio of the maximum local-curvature-dependent etching rate (i.e. the etching rate at peaks） to the uniform etching rate $E _ { r }$ on flat surface,while $A _ { 0 } \leq 1 . 0$ is the ratio of minimum local-curvature-dependent etching rate (i.e. etching rate at valleys） to $E _ { \scriptscriptstyle r }$ .In this work, $A _ { 1 } = 3 . 0$ $\mathcal { A } _ { 0 } = 0 . 1 , p = \left( \mathcal { A } _ { 1 } - 1 \right) / \left( \mathcal { A } _ { 1 } - \mathcal { A } _ { 0 } \right) , x _ { 1 } = - 8 . 0 , x _ { 2 } = 8 . 0 , h _ { 1 } = 0 . 5 , h _ { 2 } = 0 . 4 , p = 1 . 2 , p = 1 . 2$ and $C _ { m }$ is the variable mean local curvature. Based on the values, a typical relationship between the local etching rate and local surface curvature can be presented and illustrated as Fig. 5.As is shown, the local etching rate changes little (i.e. behaves isotropic etching) when the local surface curvature varying in the range from $- 5$ to $5 ~ { \mu \mathrm { m } } ^ { - 1 }$ . But changes a lot when the local surface curvature varies from -5 to $- 1 0 ~ { \mu \mathrm { m } } ^ { - 1 }$ and from 5 to $1 0 ~ \mu \mathrm { m } ^ { - 1 }$ respectively getting approach to its maximum and minimum.

![](images/05eedfc83fd6e665b815d59a0ae3e7ddd3eecf18452d5937a7ff8502396a4365.jpg)  
Fig.5.The local etching rate vs.local surface curvature

As a result, the basic Eq.(5) is modified as:

$$
\begin{array} { r } { P _ { n e x t } = P + E _ { l c } \left( t \right) \cdot \delta _ { t } \cdot \left( - \pmb { n } \right) . } \end{array}
$$

In which, $P$ denotes a current point and $P _ { n e x t }$ denotes the evolved point from $\boldsymbol { P } . ~ E _ { l c } ( t )$ is both local-curvature-dependent and time-dependent etching rate. The evolving of surface refers to a fixed reference frame and grid, namely Euler description[22], is employed. Imaging an initial

surface ${ \bf S } _ { 0 } ( { \bf X } _ { 0 } , { \bf Y } _ { 0 } )$ (described as a matrix) referring to the fixed reference grid, it evolves to （202 $\mathbf { S } _ { 1 } ( \mathbf { X } _ { 1 } , \mathbf { Y } _ { 1 } )$ after a very short etching time $\delta _ { t }$ . Set the normal vector matrix of surface $\mathbf { S } _ { 1 }$ is $\left[ \mathbf { N } _ { \mathrm { x } } ~ \mathbf { N } _ { \mathrm { y } } ~ \mathbf { N } _ { \mathrm { z } } \right]$ and then $\mathbf { S } _ { 1 }$ interpolating to the fixed reference grid can be described as:

$$
\mathbf { S } _ { 0 } ^ { \prime } \mathbf { = } \mathbf { S } _ { 1 } + { \frac { \mathbf { N } _ { \mathrm { x } } } { \mathbf { N } _ { \mathrm { z } } } } { \bigl ( } \mathbf { X } _ { 1 } - \mathbf { X } _ { 0 } { \bigr ) } + { \frac { \mathbf { N } _ { \mathrm { y } } } { \mathbf { N } _ { \mathrm { z } } } } { \bigl ( } \mathbf { Y } _ { 1 } - \mathbf { Y } _ { 0 } { \bigr ) } .
$$

Here, $\mathbf { S } _ { 0 } ^ { \prime }$ is the varied $\mathbf { S } _ { 0 }$ referring to the fixed grid. It is recommended that the minimum size of the reference grid should be at least larger than two times of $E _ { r } \cdot \delta _ { t }$ for avoiding numeric divergence. Moreover, in practical， one can use low-pass Fast-Fourier-Transition filter or convolution to eliminate the singularity of surface fractures.

# 4.RESULTS AND DISCUSSION

In this section， experimental and simulation results will be comparatively presented. Hydrofluoric acid etching effect on the surface pit, crack, scratch, and laser damage site of fused silica optics will be successively discussed.

# 4.1 Mass removal of fused silica optics during HF-based etching

![](images/f7fc62ae0273e0b21313be96ffc1d5937065a26c5d5240a0c1577eefe450f752.jpg)  
Fig. 6.The mass removal of test sample during etching.

The mass removal of the fused silica optics sample during etching processis experimentally studied and the result is presented in Fig.6. The black dot-solid line gives the mass changing of the sample. As is shown, the mass reduces linearly with the increasing of etching time. The red-triangles give the mass removal comparing to its initial mass after different etching time.The blue solid line gives the linear fiting of the mass removal. The initial mass of the fused silica sample is $2 1 9 6 5 . 4 { \pm } 0 . 1 \ \mathrm { m g }$ while changes to $2 1 7 4 5 . 2 { \pm } 0 . 1 \ \mathrm { ~ n ~ }$ ng after 7.5 hrs of etching,i.e. the mass of the sample decreases about $1 . 0 \%$ . Hence,the volume of this sample decreases $1 . 0 \%$ corresponding to its initial and the surface area of the sample changes less than $1 . 0 \%$ . The linear effect results from that the volume of HF-based solution is much larger than that of the sample, as well as the area of the surface fractures is much small than the whole area of the optics sample. Therefore, the mass removal can be described using linear equation as:

$$
M _ { r } = m _ { r r } \cdot T ,
$$

in which, $M _ { r }$ is the mass removal, $T$ is the etching time in hours,and $m _ { r r } = 2 8 . 2 3 \mathrm { \ m g / h r }$ is the etching-induced mass removal rate. In other words,in the view of thickness,the etching rate is $2 . 6 7 \mu \mathrm { m / h r }$ （204号

# 4.2 HF-based etching effect on surface pit

![](images/dc2c1ae416bfd50c081883761e4d313ed16d3b3809db72033567287f408ac7c6.jpg)  
Fig.7. The morphological evolution of surface indented pits [23].The subfigures have the same size scaling to the scale bar in the top-left subfigure.

![](images/64cc02338fe9fe1a48876a768751a09ba4fb4e03d67f00f7b524e770595f426a.jpg)  
Fig. 8.The simulated morphological evolution of a single pit.

Surface pit is a most common kind of surface defect of fused silica optics limiting the laser damage resistance. As the pit will modulate the power distribution of laser pulse, laserinduced damage likely occurs at where the pit locates.Hence, the morphological evolution of surface pit during wet chemical etching is a major concern.

Fig. 7 shows the morphological evolution of indented surface pits during etching. As is shown,there are initially several pits on the surface of the optics $( ^ { 6 6 } 0 . 0 \mathrm { ~ h ~ } ^ { 3 } )$ . Some of them are separately placed (e.g. marked as “1",“2") and some are interconnected (e.g. marked as $^ { 6 6 } 3 ^ { , 9 }$ ） One can find the initial morphology of these pits are complicated and rough enough. The morphological difference of pit “1” and $^ { 6 6 } 2 ^ { , 9 }$ results from the difference of the indenting force load.To the pit “1”, it initially has a diamond-shaped core and six crack tails. Along with the etching, the core and tails get enlarged (e.g. at time of $^ { 6 6 } 0 . 5 \mathrm { h } ^ { , 3 }$ ， $\mathsf { i } . 5 \mathsf { h } ^ { \mathsf { * } }$ ）and then blend with each other (at time of $^ { \ 6 6 } 2 . 5 \ \mathrm { h } ^ { , , }$ ， $ { ^ { \cdot } } 3 . 5  { \mathrm { h } } ^ {  { \prime }  { \prime } }$ , and $^ { 6 6 } 5 . 5 \mathrm { h } ^ { , 9 }$ ） to a big circle pit with smoothed surface.For the circle-shaped pit $^ { \cdot \circ } 2 ^ { \cdot \circ }$ , its initial rough surface gradually varies into smooth surface during etching. The evolution of other separate pits behave in a similar way. For the interconnected pit $" \thinspace 3 " \thinspace$ ,its initial rough surface gets smooth during etching. It can be seen that the smoothing is a common effect to the morphological evolution of surface pits during HF-based etching. This smoothing effect is much promising to improve the laser-induced damage resistance of fused silica optics. Moreover, it is worth to mention that the wet chemical etching treatment only enlarges the size of surface pit a little, comparing to the $\mathrm { C O } _ { 2 }$ laser treatment on surface pit of fused silica optics[24], which usually enlarges the size of surface pit more than several times.

To know the morphological evolving mechanism of a single surface pit during wet chemical etching, a sharp cone-shape pit, which is shown as the top-left subfigure in Fig. 8, is numerically modelled as an initial morphology for simulation. As is shown, the cusp of the pit become slicked and the opening of the pit will be gradually enlarged along with etching. In addition,the diameter-depth ratio of the pit increases a lot after etching. In short, it shows that the morphology of the pit gets much smooth after etching. This smoothing effect results from the etching rate at the valley cusp being much lower than that at where else.

![](images/d2973b81e0cf4301b333381e0a5383d22655ce7f564258a3a3dd3470be3aa069.jpg)  
Fig.9. The experimental (left, optical microscopy) vs. simulatec (right) morphological evolution of a surface pit array.

Fig.10.The simulated morphological evolution of arranged pits.

The morphological comparison of a surface pit array before and after etching is given in Fig. 9.For every single pit, its morphological evolution varies in a same manner as the evolution of the single pit varies shown in Fig. 8. For the pit array, from the left experimental result, it shows the boundary of the pit will expand and get approach to that of its neighbors. In respect to the experimental result, the simulated morphological evolution of surface pit array is shown in the right of Fig.9. It can be found the simulation result agrees very well with the experimental result, indicating the FDTD simulation is effective and reliable.Moreover, it can be seen that the wet chemical etching is a promising way to produce micro concave optical lens array.

Fig.10 shows the morphological evolution of a hybrid of two kinds of surface pits with different sizes of opening and depth. The larger ones have initial opening diameter of $2 . 0 \mu \mathrm { m }$ and the smaller ones have that of $1 . 0 ~ { \mu \mathrm { m } }$ . The depth of the larger ones and the smaller ones are 3.0 and $1 . 5 ~ { \mu \mathrm { m } }$ ， respectively. Every larger pit is surrounded by four small pits. When the etching time is less than $2 . 5 \mathrm { ~ h ~ }$ ，every pit evolves individually.After 2.5 hrs of etching,the boundary of the pits wil get approach to its neighbors and then mingle with each other. It is very beautiful that the morphological evolving of the hybrid surface pits behaves just like the growing of fourleafed clover.From the result, one can be motivated that the wet chemical etching can be used to do micro-scale design and processing.

![](images/a491648eb87c26a59fe70e6b693c7a88168d8ee4e4f4837fff1256849735f49c.jpg)  
Fig. 11. The simulated morphological evolution of randomly dispersed surface pits during etching

In practical, the surface pits on fused silica optics have not only uncertain size of opening and depth, but also have random dispersion. Fig.11 gives the simulation of the morphological evolution of randomly dispersed surface pits during etching. The right subfigures are the top views corresponding to their left ones. It should be mentioned that the initial morphology at $\mathrm { \Omega } ^ { \ \bullet } \mathrm { t } = 0$ h" is from experimental AFM test on the fused silica optics sample. The initial peak-valley (PV) roughness of the surface is about $0 . 2 7 ~ { \mu \mathrm { m } }$ . The following two morphological evolution are simulated using FDTD simulation. From the result of simulation, after 2.0 hours of etching, it can be found that the surface pits become larger while the PV roughness reduces to less than 0.25 $\mu \mathrm { m }$ . Meanwhile, the boundaries of the surface pits have expanded to each other. After 5.5 hours of etching, the boundaries of neighbour pits get mingled and coevolved. The PV roughness reduces to $0 . 2 4 \mu \mathrm { m }$ . In respect to its initial value, it can be found that the PV roughness decreases about $1 1 . 1 \%$ . In addition, one can find that the surface pits are passivated and the whole surface gets smoothed after etching. Here,it is worth to mention that the passivating or smooth effect contributes to the improvement of surface quality, and thus is promising to improve the laser damage resistance of fused silica optics.

# 4.3HF-based etching effect on surface crack

![](images/4094166a4217f1aa7b4e67e0ca98d189fbaf0545a1ce63a98bca08164b991a82.jpg)  
Fig.12. The simulated morphological evolution of a single micron-sized crack during etching.

In the manufacture of fused silica optics,it is difficult or even impossible to avoid the generation of microscopic cracks on the surface of fused silica optics.The microscopic crack is always shown as ultra-fine line defect and usually not visible by our human eyes. It is difficult to detect the surface crack by using conventional method. However, the micro-crack will expose after HF-based etching. Fig.12 gives an example of the simulated morphological evolution of a single micron-sized crack during HF-based etching. The top-left subfigure shows the initial 3D profile of the crack. It has about $3 ~ { \mu \mathrm { m } }$ depth. After $0 . 5 \mathrm { ~ h ~ }$ of etching, the opening of the crack increases considerably while its depth changes little. During the subsequent etching, the crack keeps opening but its depth still changes litle. Fig. 13 shows the simulated morphological evolution of six paralel surface cracks during etching. It can be seen that every crack keeps opening during etching and the opened cracks willcoevolve along with the proceeding of etching. In addition, it can be also found the depth of the cracks decreases from initial about $1 . 7 ~ { \mu \mathrm { m } }$ to less than $0 . 5 ~ { \mu \mathrm { m } }$ after $5 . 5 \mathrm { ~ h ~ }$ of etching, or in other words, decreases more than $70 . 6 \%$ . Thus the surface PV roughness of the cracks improves substantially.

![](images/519185db1c72a124f98cda140edeb58762ec3ffa03a52f5b758e40f07ae6dd30.jpg)  
Fig.13.The simulated morphological evolution of parallel surface cracks.The right series shows the top contour view corresponding to the left series.

![](images/b84ea3df8b8a3b7899703dc6f07288d179435e7533fba4b65a37f936b8b2394a.jpg)  
Fig.14. The simulated morphological evolution of cross surface cracks.

Fig. 14 shows the simulated morphological evolution of crossed surface cracks during etching. The surface cracks cross with each other and the initial surface shows like a chessboard from the top view. It shows that every crack will get widened during etching. After $5 . 5 \mathrm { ~ h ~ }$ of etching,the initial square column-like surface changes to bar-array-like surface. The width of the gap between two bars is comparative to that of the bars. In the meantime, the PV roughness considerably reduces during the etching after $2 . 5 \mathrm { ~ h ~ }$ ， while the PV roughness changes little in the first $2 . 5 \mathrm { h }$ of etching.

![](images/d5e1479e949975d86c28d2a4b56922d5388e6bd43bc29c5cdf65b07add9699da.jpg)  
Fig.15.The experimental (left) vs. simulated (right) morphological evolution of a single surface crack during etching[23]. The middle series is the top contour view corresponding to the right series.

To track the evolution of a practical surface crack during etching, AFM test is implemented between successive etching phases. In Fig.15,the left series of subfigures show the effect of HF-based etching on a surface crack from experimental test. The crack has an initial snaggle-tooth profile. After $0 . 5 \mathrm { ~ h ~ }$ of etching, the teeth are “rubbed” down and the initial jammed crack evolves to an unobstructed furrow-like crack. Keep etching, the crack will become more widened and the internal surface of the crack wil get smoothed. The width of the crack changes from initial ${ \sim } 1 . 5 ~ \mu \mathrm { m }$ to final ${ \sim } 5 . 5 ~ \mu \mathrm { m }$ after the etching time of $1 . 5 \mathrm { ~ h ~ }$ 、Based on the result of the initial AFM test at $0 . 0 \mathrm { ~ h ~ }$ ,the initial 3D model of the crack is built and shown in the top-right subfigure. The lower two axonometrical views give the predicted morphological evolution of the top one by using FDTD simulation. It can be seen that the“snaggle-tooth” is also“rubbed” down after $0 . 5 \mathrm { ~ h ~ }$ of etching, which agrees very well with the result of experiment. The“rubbed” crack will keep opening and its internal surface will get more smoothed during subsequent etching. Comparing the experimental AFM result and the result of simulation, it is demonstrated that the FDTD simulation can be a reliable and efficient way to reveal the detail mechanism of the morphological evolution of fused silica optics during HF-based wet chemical etching.

# 4.4HF-based etching effect on the surface scratch

![](images/988eed2183649d24b15e891161b22e8dcb85a389d7d6e96971e996c01518cc59.jpg)  
Fig.16.The experimental (left) and simulated (middle and right) morphological evolution of a single surface scratch during etching.

Another typical defect on the fused silica optics is the surface scratch. For example,as the top-left subfigure of Fig. 16 shows,a surface scratch usually presents as an assembly of discontinuous directional surface cracks. The cracks are successively generated orthogonal to the direction of scratching. In Fig. 16,the left series is the experimental result from optical microscopy when track the morphological evolution of a surface scratch during etching. The topright subfigure shows an analytically built 3D model of the surface scratch.The middle-right and botom-right subfigures are the predictions of the morphological evolution of the top-right one by using FDTD simulation. The middle series shows the top views corresponding to their right ones.From the optical microscopy， one can find the initial discrete cracks expand and the borders of the cracks get approach to their neighbors’ during the etching time of the first $1 . 5 \mathrm { ~ h ~ }$ This expanding and mingling effect can also be demonstrated by using FDTD simulation, as the top-middle two subfigures of the middle series show. Along with the subsequent etching, it shows that the scratch will get continuous and the surface of the scratch will get smoothed.

![](images/574051a374e9610e2f9ac1cf4c8b4aca1fadcd7b8bf4812f565bb53c7ed13fe1.jpg)  
Fig.17. The morphological evolution of a wide surface scratch during etching， experimentally characterized by optical microscopy (upper) and AFM (middle), and predicted by using FDTD simulation (lower).

For a wide scratch shown as in the top-left subfigure in Fig. 17, it has a complicated morphology and the width of ${ \sim } 2 5 ~ \mu \mathrm { m }$ . Optical microscopy and AFM are used to characterize the morphology of the scratch. The experimental results from the two microscopy are shown as in the transversely top series and middle series subfigures, respectively. From the result of optical microscopy, one can find that the wide scratch consists of many pits and cracks.After $1 . 5 \mathrm { ~ h ~ }$ of etching,the pits and cracks get expanded. The internal surfaces of the pits and cracks get smoothed. Keep etching and the surfaces wil expand into their neighbours', combining as larger size smooth surfaces. This HF-based etching-induced smoothing effect is also demonstrated by the results of AFM,as the transversely middle series shows. In addition,based on the initial result of AFM test, the initial 3D model of the scratch's profile is built and then FDTD simulation is performed to give the prediction of its morphological evolution. The bottom-left subfigure gives the initial morphology of the scratch which is modelled according to the first AFM test (at $0 . 0 \mathrm { { h } ) }$ ). It shows that the initial pits and cracks in the scratch will become larger and smoother after etching. Comparing the results from experiment and simulation, one can find the simulation results agrees well with the results of experiments qualitatively. Here, it is worth to mention again that the smoothing effect on the surfaces contributes to the improvement of surface quality and is promising to enhance the laser damage resistance of the fused silica optics.

# 4.5 HF-based etching effect on the surface laser damage site

During the routine operation of large high power laser facility, laser-induced damage site will currently, unavoidably generate on the surface of fused silica optics. The laser damage site will grow exponentially in size along with subsequent high-intensity laser irradiation[25]. It is imperative to suppress the growth of the laser damage site preferentially using one-step processing. Fortunately, the HF-based etching can process all the laser damage sites on the

![](images/cfd9444577d92ad19218b1f98680d76fbf82dfbf55787902fef5003108e22ee8.jpg)  
Fig.18.The morphological evolution of laser damage sites during HF-based etching.

surface of fused silica optics in just one submergence step. Fig. 18 shows the morphological evolution of laser damage site during HF-based etching. The morphological evolution resembles to that Fig.7 shows. The surface of the damage site will get smoothed after HF-based etching. The HF-based etching effects on micron-sized laser-induced surface damage growth in fused silica has been studied by Hrubesh et al.[26] from Lawrence Livemore National Laboratory, USA and shows the HF-based etching can largely suppress the laser damage growth.

![](images/9a61eebbb07c22559480a00a929564cb2856b0139ebe525db4588d397c3c0510.jpg)  
Fig.19.Laser damage growth of an unetched site (Site 1) and a etched site (Site 2) on a same optics after flat-top-shaped ultraviolet laser irradiation with the wavelength of $3 5 1 ~ \mathrm { { n m } }$ ,the duration of 5.O ns and the fluence of $8 . 0 \mathrm { J } / \mathrm { c m } ^ { 2 }$ . The Site 2 is etched $2 4 . 0 \mathrm { h }$ by using HF-based solution.

![](images/11f4c804843c5131850cb8564aacc6dac948a20d3b832589c6a600845e405a36.jpg)  
Fig. 20.The comparison of laser damage growing sites of an etched optics (1#) to another unetched one $( 2 \# )$

For assessing the laser-damage growing resistance of millimeter or sub-millimeter-sized laser damage site, a flat-top-shaped $3 5 1 ~ \mathrm { { n m } }$ ,5.0 ns, $8 . 0 \mathrm { ~ J } / \mathrm { c m } ^ { 2 }$ ,“1 on $1 ^ { \circ }$ (one shot on one position) laser irradiation test was implemented. Fig.19 shows the laser damage growth of a typical etched laser damage site (i.e. Site 2) after one pulsed laser irradiation, comparing to that of a typical unetched site (Site 1). It shows that the laser damage of etched site grows little, while that of unetched site grows a lot. Thus, the HF-based etching can suppress the laser damage growth of sub-millimeter-sized damage site. Further, for an etched (1#) and an unetched $( 2 \# )$ fused silica optics with the diameter of $5 0 . 0 \mathrm { m m }$ and the thickness of $5 . 0 \mathrm { m m }$ , each optics has totally 48 laser damage sites that are monitored for their size growth after laser irradiation. Fig. 2O gives the statistical number of damage growing sites on both the two optics. On the etched 1# optics, there are l2 laser damage sites visibly growing after irradiation. Comparatively, there are 23 laser damage sites visibly growing on the unetched $2 \#$ optics. Though the monitored laser damage sites on the two optics and even the damage sites on each optics have different morphology, they have comparative dimension. Thus one can conclude that the HF-based etching can suppress the laser damage growth of millimeter-sized laser damage sites.

![](images/203e241aeb1ed83d2ee1af0558b946b17d6a081af772e7bc9cc1311576d68cae.jpg)  
Fig. 21. Laser damage growth of HF-etched laser damage sites after flat-top-shaped ultraviolet $3 5 1 ~ \mathrm { { n m } }$ 5.0 ns, $8 . 0 \ \mathrm { J } / \mathrm { c m } ^ { 2 }$ laser irradiation. The four laser damage sites in the left subfigure are generated with different extent in damage on the surface of fused silica optics and all sites are etched $2 4 . 0 \mathrm { ~ h ~ }$ by using HF-based solution.

Though the suppressing effect of HF-based etching on laser damage growth is evident, the number of laser damage growing sites is much larger than expected. Fig. 21 shows an example of damage growth of etched damage site after irradiation. To the left two relatively large damage sites (or heavily damaged sites), they apparently grow after laser irradiation. The grown sites have a lot of separate damage pits around their initial border,as well as on their initial surface. This damage growth of etched site differs to that of unetched site shown in the top subfigure of Fig.19.For the unetched site, the laser damage growth is more likely to result in the expansion of its border. In the mean time,from Fig.21,one can also find that the relatively small etched damage sites have no laser damage growth after irradiation. Therefore, for etched sites having different sizes (as is shown in the left subfigure of Fig.21), it shows that the larger the size, the easier the damage growing. In other words,the laser damage growth of etched damage site has a size-effect.

To explore how the size-effect occurs, 3D morphological evolution of a millimeter-sized laser damage site during HF-based etching is experimentally traced. As is shown in Fig. 22, the initial surface topography of this damage site is much rough with high spatial frequency features.

![](images/b025732b1e24fd712c54b0bee104e64e7f3bbff228eec7ab2c01ab4757d9c9fa.jpg)  
Fig. 22.The 3D morphological evolution of a large millimeter-sized laser-induced damage site with complicated morphology during HF-based etching.

With the HF-based etching proceeding, the surface topography will get smoothed into low spatial frequency features. In the mean while, it can be obviously found that the depth of the damage site will get more and more deeper during etching, and some new cracks appears around the site. Guss et al.[27] have given the high-resolution 3D imaging of surface damage sites in fused silica with optical coherence tomography,and it is shown that the damage site has many micro fractures below itself. Here,we give the HF-based etching effect of a laser damage site having these micro fractures. Thus for a optics having surface laser damage site, the HF-based etching is not isotropic at the damage site. The anisotropic etching effect most likely results from the existence of undetectable or weakly delectable micro-cracks below the damage site. Another reason for the anisotropic etching is that the physical or mechanical property of the material around the damage site varies during the damage occurring. If the micro-cracks and propertyvaried material below the surface of damage site are not mitigated, the laser-induced damage growth will easily occur when high-intensity laser irradiates to the damage site.For a heavily damaged or relatively large site, it is time consumptive to mitigate the large amount of micro cracks or property-varied material using HF-based etching.This can be an explanation for the finding“Deeply etched sites show reduced, but non-zero, fluorescence emission.” in the section "4. CONCLUSIONS” of Ref. [26]

![](images/3a532879e97461f81d57696f7e5e36e4af5b6b81a47a89ef9c69ca8be872bde4.jpg)  
Fig. 23.The 3D morphological evolution of a sub-millimeter-sized laser-induced damage site with complicated morphology during HF-based etching.

Comparatively, the morphological evolution of a relatively small sub-millimeter-sized laser damage site is shown in Fig. 23.It shows the same trend as above mentioned that that the initial rough surface gets smoothed after HF-based etching and the depth of the damage site gets much deeper than its initial.Nonetheless,it can be seen that there is no cracks exist after $1 2 . 0 \mathrm { { h } }$ of etching. In other words, the initial micro-cracks has been removed during HF-based etching. Having this result and in responding to Fig. 21 and Fig. 19，one can conclude that the enhancement of the laser damage resistance of etched laser damage site results from the removing of micro-cracks.

![](images/ce4bad561dfe5ebe67fc4ac827a6d3ca1e1cc1305a76330dd311eca1b9f6d850.jpg)  
Fig.24.A sketch of the form of laser damage site.

At present, it is very difficult or a big challenge to accurately modelling a laser damage site.For simplifying the analysis,Fig. 24 gives a sketch of the formation of laser damage site. The central sun likes shows the laser-induced plasma explosion core near the laser exit surface. The bold black line denotes the surface profile of laser damage site. The upper section of the profile near the flat exit surface always appears as a mechanically stripping trace of bulk material. The lower section of the profile usually appears as a molten surface with several jet traces. Below the surface of the damage site, there are many micro cracks (denote as thin black lines). These micro cracks extend in diverging directions and forms the cracked field (as brown line shows)below the surface profile. The cracked field is believed to be the intense field of laser damage precursors and more likely results in laser damage growth if unetched enough. The cracked field and the upper stripping profile are thought result from the influence of laserinduced shock wave.Below the cracked field, it is the deformed field (as light blue line shows). In this field, there is little micro crack,but the property of the bulk material has changed during the irradiation of laser and laser-induced plasma explosion. In both the cracked field and deformed field, the rate of HF-based etching is enhanced and result in the damage site getting deeper and deeper during etching.

# 5.SUMMARY

In this work, hydrofluoric acid-based etching effect on the surface fractures,i.e. surface pit, crack, scratch,and laser damage site of fused silica optics is studied. The morphological evolution of the surface fractures during etching is experimentally characterized by using optical microscopy and 3D profilometry. Moreover, the 3D profiles of the surface fractures are modelled and finite difference time domain simulation is performed to predict the morphological evolution of the surface fractures during etching. The following gives the main summaries of this work:

(1） For surface pit, it will be passivated and its surface morphology will get smoothed after HF-based wet chemical etching. The passivizing or smoothing effect contributes to the improvement of local surface quality， and thus is promising to enhance the laser-damage resistance of fused silica optics.In addition, it is demonstrated that the wet chemical etching can be a promising way to produce micro optical lens array.

(2) For surface crack, it will be opened and its surfaces will get smoothed after HF-based etching. The opened neighbour cracks will co-evolve along with the proceeding of etching and the co-evolving effect contributes to the improvement of local surface PV roughness.

(3）For surface scratch, it shows that an initially discontinuous scratch will become continuous and its local surface wil get smoothed after HF-based etching. The internal pits and cracks of a wide scratch will get involved with their neighbours’ during etching,resulting in generating larger concave smooth surfaces.

(4) For surface laser damage site,HF-based etching will improve the local surface topography by removing the high spatial frequency surface fractures,and can greatly suppress the laser damage growth of fused silica by mitigating the surface and subsurface fractures, indicating the HF-based etching is a promising wet chemical method for repairing laser-induced damage optics. Besides, the depth of laser damage site will get deeper and deeper during etching. This deepening effect is believed resulting from the existence of micro cracks below the damage site,as well as the change of the physical or mechanical property of fused silica material by laser irradiation.

In addition, it is worth to mention that a explicit local-curvature dependent etching model is proposed in this work. Based on the proposed model, FDTD simulation is performed and one can find the result of simulation agree very well with that of experiment, demonstrating the FDTD simulation can be a reliable and efcient way to reveal the detail mechanism of surface fracture's morphological evolution. What's more, it shows that the wet chemical etching can be used to do micro-scale design and processing.

# Acknowledgement

This work is supported by the National Natural Science Foundation of China (Grant Nos. 51535003 and 11602242). The authors deeply appreciate Prof. LAN Ke from Beijing Institute of Applied Physics and Computational Mathematics for her helpful suggestions.

# References

[1]E.I.Moses,“National ignition facility: 1.8-MJ 750-TW ultraviolet laser”,Proc. SPIE 5341,13 (2004).   
[2] W. G. Zheng, X.F.Wei, Q.H. Zhu,F. Jing,D. X. Hu,J. Q. Su, K. X. Zheng, X. D. Yuan, H. Zhou, W. J. Dai, W. Zhou,F. Wang, D.P. Xu, X. D. Xie,B.Feng, Z. T.Peng, L.F. Guo, Y.B. Chen, X. J. Zhang, L. Q. Liu,D. H. Lin, Z. Dang, Y. Xiang, and X. W. Deng,“Laser performance of the SG-II laser facility", High Power Laser Sci. Eng. 4,1 (2016).   
[3]P.Vivini,and M. Nicolaizeau,“The LMJ: overview of recent advancements and very first experiments”, Proc. SPIE 9345, 934503 (2015).   
[4] S.A.Sukharev,“High-power phosphate-glass laser system Luch: a prototype of the Iskra-6 facility module", Proc.SPIE 3492,12(1999).   
[5]B.Rus,P.Bakule,D. Kramer, G.Kom,J.T.Green,J.Novak,M.Fibrich,F.Batysta,J.Thoma,J.Naylon, T. Mazanec,M. Vitek,R. Barros,E.Koutris,J. Hrebicek,J.Polan,R.Base,P.Homer,M. Koselja,T. Hvlicek,M. Novak, C. Zervos, P. Korous,M. Laub,and J. Houzvicka,“ELI-beamlines laser systems: status and design options", Proc. SPIE 8780, 87801T (2013).   
[6] D.Ursescu, O. Tesileanu, D. Balabanski, G. Cata-Danil, C.Ivan,I. Ursu, S. Gales,and N. V. Zamfir, “Extreme light infrastructure nuclear physics (ELI-NP): present status and perspectives”,Proc. SPIE 8780, 87801H (2013).   
[7] T.I. Suratwala,P.E. Miller,J. D. Bude,R. A. Steele,N. Shen,M. V. Monticeli, M. D.Feit,and T.A. Laurence,“HF-based etching processes for improving laser damage resistance of fused silica optical surfaces", J. Amer. Cera. Soc.94, 416 (2011).   
[8] P.E. Miller,J.D.Bude,T.I. Suratwala,N. Shen,T.A. Laurence,W.A. Steele,J. Menapace, M. D.Feit, and L.L. Wong,“Fracture-induced subbandgap absorption as a precursor to optical damage on fused silica surfaces", Opt.Lett. 35,2702 (2010).   
[9] N. I. Chkhalo, M.S. Mikhailenko,A.V. Milkov,A.E.Pestov,V.N.Polkovnikov,N. N. Salashchenko,I. L. Strulya, M. V. Zorina, and S. Y. Zuev,“Effect of ion beam etching on the surface roughness of bare and silicon covered beryllium films", Surf. Coat. Tech.311, 351 (2017).   
[10] J. Zajadacz,P.Lorenz,F.Frost,R.Fechner, C.Steinberg,H. Scher,and K. Zimmer,“Reactive ion beam etching of fused silica using vertical lamellar patterns of PS-b-PMMA diblock copolymer masks”, Microelect. Eng. 141, 289 (2015).   
[11] Y.Wu,L. Jiao, H. Guo, M.Fujimoto,and K. Shimada,“Ultrafine surface finishing of fused silica glass using MCF (magnetic compound fluid) wheel",Adv. Mat. Res. 565, 3 (2012).   
[12] C.Weingarten，A. Schmickler,E.Willnborg, and K. Wissenbach，“Laser polishing and laser shape correction of optical glass", J. Laser Appl. 29, 011702 (2017).   
[13] A. B. Burg, Fluorine Chemistry (Academic Press, New York, 1950).   
[14] D.M. Knoter,“Etching mechanism of vitreous silicon dioxide in HF-based solutions”,J. Am. Chem. Soc. 122, 4345 (2000).   
[15] X. Ye, J. Huang, H. J. Liu,F. Geng,L. X. Sun, X. D. Jiang, W. D. Wu,L. Qiao, X. T. Zu, and W. G. Zheng,“Advanced mitigation process (AMP) for improving laser damage threshold of fused silica optics”, Sci. Rep. 6,31111 (2016).   
[16] L. Hackel, A. Burnham, B. Penetrante,R. Brusasco,P.Wegner,L. Hrubesh, M. Kozlowski, and M. Feit, “Method for producing damage resistant optics”, U.S. patent 6,518,539 (February 11, 2003).   
[17] M.Pfiffer,P. Cormont, E.Fargin, B.Bousquet, M. Dussauze,S.Lambert,and J. Neauport,“Effects of deep wet etching in HF/HNO3 and KOH solutions on the laser damage resistance and surface quality of fused silica optics at $3 5 1 ~ \mathrm { { n m ^ { \prime } } }$ , Opt. Express 25, 4607 (2017).   
[18] Y. Su, Y. H. Zhou, W. Huang, and Z. M. Gu,“Study on reaction kinetics between silica glasses and hydrofluoric acid", J. Chin. Cera. Soc.32, 287 (2004).   
[19]L.L. Wong,T.I. Suratwala, M.D.Feit,P.E. Miller,and R. Steele.“The effect of HF/NH4F etching on the morphology of surface fractures on fused silica", J. Non-Crys. Solids 355, 797 (2009).   
[20] M.D.Feit, T.I. Suratwala, L.L. Wong, W.A. Steele,P.E. Miler,and J.D. Bude,“Modeling wet chemical etching of surface flaws on fused silica",Proc. SPIE 7504,7504L (2009).   
[21] Y.H. Su, Differential Geometry (Press of Fuzhou University, Fuzhou,2014).   
[22] W.H. Yang, Mechanics (Press of University of Science and Technology of China,Hefei, 2006).   
[23] T.X. Liu, K. Yang, H. Y.Li,L. H. Yan, X. D. Yuan,and H. W. Yan,“Simulation of the evolution of fused silica's surface defect during wet chemical etching”,Proc.SPIE 10339,10339c (2017).   
[24] M.L. Spaeth,P.J. Wegner,T.I. Suratwala, M. C.Nostrand,J. D.Bude,A.D. Conder,J.A.Folta,J.E. Hebner,L.M. Kegelmeyer, B. J. MacGowan, D.C. Mason, M. J. Matthews, and P. K. Whitman,“Optics recycle loop strategy for NIF operations above UV laser-induced damage threshold",Fusion Sci.Tech. 69, 265 (2016).   
[25] R.Negres,D. Cross, Z.Liao,M. Matthews,and C. Carr,“Growth model for laser-induced damage on the exit surface of fused silica under UV, ns laser irradiation", Opt. Express 22, 3824 (2014).   
[26] L.W. Hrubesh, M. A. Norton, W.A. Molander,P.J. Wegner,M. Staggs,S. G.Demos,J. A. Britten,L.J. Summers,E.F. Lindsey,and M. R. Kozlowski,“Chemical etch effects on laser-induced surface damage growth in fused silica",Proc. SPIE 4347, 553 (2001).   
[27] G. Guss,I. Bass,R. Hackel, C. Mailhiot,and S.G. Demos,“High-resolution 3-D imaging of surface damage sites in fused silica with optical coherence tomography",Proc. SPIE 6720, 6720F (2007).