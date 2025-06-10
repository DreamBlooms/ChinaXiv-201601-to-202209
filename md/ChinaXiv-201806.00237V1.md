# On the analytical solution of accelerating structure

Xiongwei Zhu Institute of High Energy Physics,Chinese AcademyofSciences，Beijing10o049,China

June 20,2018

# Abstract

In this paper,we discuss the analytical solution of the accelerating structure electromagnetic field. We mainly discuss the field and circuit method to analyze the accelerating structure. We discuss two kinds of accelerating structures: the traveling wave accelerating structure and the standing wave accelerating structure. Some results are presented in this paper.

Keywords: Accelerating structure, Analytical solution, Dispersion relation.

# 1Introduction

The accelerating structure is the core element of the accelrator[1, 2,3, 4, 5,6]. Usually, the structure works in the $T M$ mode. There are two kinds of accelerating structure,the traveling wave accelerating structure and the standing wave accelerating structure. The proton accelerator often uses the standing wave accelerating structure, while the electron accelerator often uses the traveling wave accelerating structure. As for the electron accelerator, there are several kinds of typical popular structures: L-band( $1 3 0 0 M H z$ )，S-band（2856MHz），C-band（ $5 7 1 2 M H z$ )，and X-band( $1 1 . 4 G H z$ ）which exist in the world accelerator laboratories. Figure 1 is the schematic model of the disk loaded structure.

![](images/f7020e7d066f73fba7b52598dab2a068a654f509ae67f65f77663035a7a570cb.jpg)  
Figure 1.The disk loaded accelerating struture

One of the main characteristics of the electromagnetic wave is its dispersion relation. The dispersion relation of the electromagnetic wave is the functional relation between the wave frequency and the wave number $f ( \omega , k ) = 0$ . The phase velocity of the electromagnetic wave is $\begin{array} { r } { v _ { p } = \frac { \omega } { k } } \end{array}$ , while the group velocity of the electromagnetic wave is $\begin{array} { r } { v _ { g } = \frac { d \omega } { d k } } \end{array}$ . The electromagnetic wave whose phase velocity is bigger than the light velocity is called the fast wave,but the electromagnetic wave whose phase velocity is less than the light velocity is called the slow wave.

# 2 Time harmonic factor of traveling wave field

There are two kinds of the accelerating structures: the traveling wave structure and the standing wave structure. Furture, there are two kinds of analyzing methods for solving the electromagnetic field in the accelerating structure: the analytical method and the numerical method. The analytical method is limited to some simple structure,and belongs to the closed electromagnetic feld theory. With the great step developement of the computer and the numerical method, there appear the electromagnetic field simulation softwares: MAFIA, Superfish, CST and HFSS. The simulation research becomes the routine for the accelerating structure research. One forgets the analytical method gradually. In this paper, we introduce the analytical method to solve the electromagnetic field of the accelerating structure. In cylindrical coordinate $( r , \theta , z )$ ， the time harmonic factor of the traveling wave field in the accelerating structure is $\exp ( i ( \omega t - k z ) )$ . The standing wave can be divided into two antipropagating traveling waves. Due to the linear overlapping principle of Maxwell equations, we only disscuss the case of the traveling wave.

# 3 The basic wave equations

In the accelerating structure, the sourceless wave equations can be expressed as

$$
\nabla \times \vec { E } = - \frac { i \omega } { c } \mu \vec { H } ,
$$

$$
\nabla \times \vec { H } = \frac { i \omega } { c } \varepsilon \vec { E } .
$$

Expanding the equations above,we obtain

$$
E _ { r } = \frac { c } { i \omega \varepsilon } ( \frac { 1 } { r } \frac { \partial H _ { z } } { \partial \theta } - \frac { \partial H _ { \theta } } { \partial z } ) ,
$$

$$
E _ { \theta } = \frac { c } { i \omega \varepsilon } ( \frac { \partial H _ { r } } { \partial z } - \frac { \partial H _ { z } } { \partial r } ) ,
$$

$$
E _ { z } = \frac { c } { i \omega \varepsilon } ( \frac { \partial H _ { \theta } } { \partial r } + \frac { 1 } { r } H _ { \theta } - \frac { 1 } { r } \frac { \partial H _ { r } } { \partial \theta } ) ,
$$

$$
H _ { r } = - \frac { c } { i \omega \mu } ( \frac { 1 } { r } \frac { \partial E _ { z } } { \partial \theta } - \frac { \partial E _ { \theta } } { \partial z } ) ,
$$

$$
H _ { \theta } = - \frac { c } { i \omega \mu } ( \frac { \partial E _ { r } } { \partial z } - \frac { \partial E _ { z } } { \partial r } ) ,
$$

$$
H _ { z } = - \frac { c } { i { \omega } \mu } ( \frac { { \partial } E _ { \theta } } { { \partial } r } + \frac { 1 } { r } E _ { \theta } - \frac { 1 } { r } \frac { { \partial } E _ { r } } { { \partial } \theta } ) .
$$

# 4Solving the wave equations from the longitudinal field equation

Using the lomgitudinal fields to express the transverse fields,we get

$$
\begin{array} { r } { E _ { r } = \big ( \frac { \omega ^ { 2 } } { c ^ { 2 } } { \mu } \varepsilon - k _ { z } \big ) ^ { - 1 } \big ( \frac { \partial ^ { 2 } E _ { z } } { \partial r \partial z } - \frac { i \omega \mu } { c } \frac { 1 } { r } \frac { \partial H _ { z } } { \partial \theta } \big ) , } \\ { E _ { \theta } = \big ( \frac { \omega ^ { 2 } } { c ^ { 2 } } { \mu \varepsilon } - k _ { z } \big ) ^ { - 1 } \big ( \frac { 1 } { r } \frac { \partial ^ { 2 } E _ { z } } { \partial \theta \partial z } + \frac { i \omega \mu } { c } \frac { \partial H _ { z } } { \partial r } \big ) , } \\ { H _ { r } = \big ( \frac { \omega ^ { 2 } } { c ^ { 2 } } { \mu \varepsilon } - k _ { z } \big ) ^ { - 1 } \big ( \frac { i \omega \varepsilon } { c } \frac { 1 } { r } \frac { \partial E _ { z } } { \partial \theta } + \frac { \partial ^ { 2 } H _ { z } } { \partial r \partial z } \big ) , } \\ { H _ { \theta } = \big ( \frac { \omega ^ { 2 } } { c ^ { 2 } } { \mu \varepsilon } - k _ { z } \big ) ^ { - 1 } \big ( \frac { 1 } { r } \frac { \partial ^ { 2 } H _ { z } } { \partial z \partial \theta } - \frac { i \omega \varepsilon } { c } \frac { \partial E _ { z } } { \partial r } \big ) . } \end{array}
$$

While the equations of the longitudinal fields are Hemholtz equations

$$
( \boldsymbol { \nabla } ^ { 2 } + \frac { \omega ^ { 2 } } { c ^ { 2 } } \mu \varepsilon ) E _ { z } = 0 ,
$$

$$
( \boldsymbol { \nabla } ^ { 2 } + \frac { \omega ^ { 2 } } { c ^ { 2 } } \mu \varepsilon ) H _ { z } = 0 .
$$

So,we first solve the longitudinal field equations. And then get the transverse fields from the longitudinal field solutions.

# 5 The eigen mode equation

As for thr Hemholtz equation of the longitudinal field part,we divide the operator $\nabla ^ { 2 } \longrightarrow$ $\nabla _ { \perp } ^ { 2 } + \frac { d ^ { 2 } } { d z ^ { 2 } }$ ,usingthetravengeondieattheoongtildifeeqin

$$
{ ( \bigtriangledown _ { \perp } ^ { 2 } + { \frac { \omega ^ { 2 } } { c ^ { 2 } } } \mu \varepsilon - k _ { z } ^ { 2 } ) f = 0 }
$$

where $f$ stands for the longitudinal field part. Its solution are the sum of a series of Bessel functions. The eigen mode equation is

$$
( \nabla _ { \perp } ^ { 2 } + \beta _ { n } ^ { 2 } ) f = 0 .
$$

In case of the cylindrical coordinates, the $T M$ eigen mode equation is

$$
( \frac { 1 } { r } \frac { \partial } { \partial r } r \frac { \partial } { \partial r } + \frac { \partial ^ { 2 } } { \partial \theta ^ { 2 } } + \beta _ { n } ^ { 2 } ) f _ { n } = 0
$$

In case of $T M _ { 0 n }$ ， $\begin{array} { r } { \frac { \partial ^ { 2 } } { \partial ^ { 2 } \theta } = 0 } \end{array}$ ,theqatife

$$
f _ { n } = A J _ { 0 } ( \beta _ { n } r )
$$

the conventinal fundamental mode is $T M _ { 0 1 }$

# 6 The equivalent circuit and the dispersion relation

The equivalent circuit method is a kind of simple tool to solve the main characteristics of the accelerating structure. The basic idea is to expanse the electric field as the form of $E ( r _ { \perp } ) V ( z , \omega )$ ， and to expanse the magnetic field as the form of $H ( r _ { \perp } ) I ( z , \omega ) Z$ ,where $Z$ is the wave impedance. Using this method,we can get the dispersion relation of the accelerating structure. To speak physically, we divide the accelerating structure into a series of the coupled resonant cavity. The equivalent circuit of the traveling accelerating structure is shown as Figure 2.

![](images/fec043028b4b99eaa665467e94cee2eac91f2d9b122cc5fc2290cb7d9d73da48.jpg)  
Figure 2.The equivalent circuit of the traveling wave accelerating struture

Using the equivalent circuit in Figure 2，we can get the common dispersion relation of the traveling wave accelerating structure

$$
\omega ^ { 2 } = \omega _ { 0 } ^ { 2 } ( 1 - \kappa c o s ( \theta ) ) .
$$

where $\omega _ { 0 } , \theta$ are the resonant frequency and the phase shift, $\kappa$ is the coupling coefficient.The coupling coefficient can be estimated roughly as

$$
\kappa \approx \frac { 8 } { 3 } \cdot \frac { a } { L }
$$

vhere $a$ is the bore radius,and $L$ is the length of the cavity. The group velocity of the traveling wave accelerating structure is

$$
v _ { g } = \frac { \omega _ { 0 } L } { 2 } \cdot \frac { \kappa s i n ( \theta ) } { \sqrt { 1 - \kappa c o s ( \theta ) } } .
$$

Using the typical parameters of the SLAC S-Band accelerating structure, the working frequency is $2 8 5 6 M H z$ , the coupling factor between the cells is estimated to be O.15 roughly. Therefore, the typical dispersion relation curve and the typical group velocity are shown in Figure 4 and Figure 5.

![](images/62fab294411dd36a580bd734cb0f638f708c26ed79db62ef89d3f008166e235f.jpg)  
Figure 3.The typical dispersion relation of the traveling accelerating structure

![](images/cfcf8b05f40cb1bdb0b9be7c180ff86ad3c84801bb88c44d25fb5c8952690dd2.jpg)  
Figure 4.The group velocity of the traveling wave accelerating struture   
Figure 5.The equivalent circuit of the standing wave accelerating struture

The coupling factor can be obtained from the experiment research,or from the field analyzing method. The accelerating structure can works in both the traveling wave mode and the returning wave mode. The working mode is determined by the working point in the dispersion relation curve. In case of the traveling wave region,the directions of the phase velocity and the group velocity are the same. While in case of the returning wave region,the directions of the phase velocity and the group velocity are vice verse.

As for the standing wave accelerating structure, its equivalent circuit is shown in Figure 3.

n-1 n $\mathfrak { n } { + } 1$ L -C3C3C3E C $\mathrm { c }$ C

From the equivalent circuit above,we can derive the dispersion relation of the standing wave accelerating structure

$$
\omega ^ { 2 } = \frac { \omega _ { 0 } ^ { 2 } } { 1 - \kappa c o s ( \theta ) }
$$

In the standing wave accelerating structure,the frequency is independent of the wave number, therefore the group velocity of the standing wave accelerating structure is $0$ . The flling time of the standing wave accelerating structure is the field buiding time of the cavity.

Because $\kappa$ is small, the dispersion relation of the standing wave accelerating structure can be also approximated as

$$
\omega ^ { 2 } = \omega _ { 0 } ^ { 2 } ( 1 - \kappa c o s ( \theta ) ) .
$$

Using the equivalent circuit method, we discuss the dispersion relation of the accelerating structure. Although,the dispersion relation of both the traveling wave and the standing wave accelerating structure can be expressed as $\omega ^ { 2 } = \omega _ { 0 } ^ { 2 } ( 1 - \kappa c o s ( \theta ) )$ , but the underline physics is different. the analytical result can describe the physics simply, we still need the numerical and experiment research to study further.

# 7 Discussion

With the development and the maturity of the computer and the numerical method, the numerical experiment willbe one of the important marching directions for physics. The classical macroscopic electromagnetic theory is an branch of the physics. The governing equations of the electromagnetic theory is the Maxwell partial differential equations. The simulation techniques for the electromagnetic theroy is well mature. The physical model whose analytical solution can be gotten is just a rice in the sea.But the familarity with the analytical method will be of the great help to the numerical experiment.

# References

[1] Xiongwei Zhu, et.al., layout of bunch compressor for Beijing XFEL test facility, NIM A, 566, 2006.   
[2] Xiongwei Zhu, et.al., Physical Design of BTF accelerator, Vol.30, Sup.1, 2006.   
[3] Xiongwei Zhu, et.al., Design of a L-Band DC photocathode RF Gun, 33, 4, 2009.   
[4] Xiongwei Zhu, et.al., Design of a L-Band photocathode RF injector, 34, 2, 2010.   
[5] Xiongwei Zhu, et.al., Concept design of CXFEL, BEPC Seminar, 2008,   
[6] Xiongwei Zhu, et.al., On the analytical solution of the accelerating structure, BEPC Annual Seminar,2015.