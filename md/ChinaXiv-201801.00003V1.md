# The Effect of High Spatial Harmonics on Beam Dynamics in RF Linac

Xiongwei Zhu Institute of High Energy Physics, Chinese Academy of Sciences, P.O.Box 918, Beijing 100049, China

# Abstract

In this paper, we continue our work [1] which analyzes the effect of high spatial harmonics on beam dynamics in RF linac. The approximate solution of the radial motion is obtained. Further, some numerical results are present using the mapping technique.

# 1 Introduction

RF linac accelerating structure is a kind of periodic slow wave guide in which $T M$ mode is excited and transported to accelerate the electron. Usually, the $T M _ { 0 1 }$ is the main mode (synchronous mode) to accelerate the electron. In addition to the fundamental mode,the spatial harmonic modes can also be excited according to the Floquet theorem whose amplitude is smaller than those of the main mode. In [1, 2,3,4], we have analyzed the effect of high harmonics mode in linac and proposed the bunch lengthening phenomenon existing in the photocathode RF gun. In this paper, we continue our work further to give the approximate solution of the radial motion taking into account the high harmonics mode, and some numerical results are present.

# 2 EM field in accelerating structure

The general RF $T M$ electromagnetic field in RF linac accelerating structure can be expressed as[1, 2]

$$
\begin{array} { c } { E _ { z } = E _ { 0 } \displaystyle \sum _ { n = - \infty } ^ { \infty } b _ { n } c o s ( \omega t - k _ { n } z ) , } \\ { E _ { r } = - \displaystyle \frac { r } { 2 } \frac { \partial E _ { z } } { \partial z } , } \\ { B _ { \theta } = \displaystyle \frac { r } { 2 c ^ { 2 } } \frac { \partial E _ { z } } { \partial t } , } \end{array}
$$

where $\begin{array} { r } { k _ { n } = k _ { 0 } + \frac { 2 \pi } { D } n } \end{array}$ ， $D$ is the periodical length of the accelerating structure, $k _ { 0 }$ is the fundamental mode wavenumber, $k _ { n } ( n \in Z )$ is the high harmonics mode wavenumber,and $z$ is the longitudinal position along the beam axis.

# 3Longitudinal Motion for Single Particle

The longitudinal motion equations are expressed as[1]

$$
\frac { d \gamma } { d z } = \frac { q E _ { 0 } } { m c ^ { 2 } } \sum _ { n = - \infty } ^ { \infty } b _ { n } c o s ( \Delta \phi - \frac { 2 \pi n } { D } z ) ,
$$

$$
\frac { d \Delta \phi } { d z } = k _ { 0 } \big ( \frac { \gamma } { ( \gamma ^ { 2 } - 1 ) ^ { \frac { 1 } { 2 } } } - 1 \big ) .
$$

As derived in [1], suppose $\gamma _ { n } = \gamma ( n D ) , \Delta \phi _ { n } = \Delta \phi ( n D )$ , we have the standard mapping under the case of $b _ { 0 } = b _ { n } = 1$ [1]

$$
\gamma _ { n + 1 } = \gamma _ { n } + \frac { q E _ { 0 } D } { m c ^ { 2 } } c o s ( \Delta \phi _ { n } ) ,
$$

$$
\Delta \phi _ { n + 1 } = \Delta \phi _ { n } + k _ { 0 } D ( \frac { \gamma _ { n } } { ( \gamma _ { n } ^ { 2 } - 1 ) ^ { \frac { 1 } { 2 } } } - 1 ) .
$$

We conclude in [1] that the high harmonic mode willincrease the energy spread and the bunch length.

# 4Transverse Motion for Single Particle

The radial electromagnetic force on the relativistic charged particle ( $v = \beta c \cong c$ ）due to the transverse electromagnetic field is

$$
F _ { r } = - \frac { q r } { 2 } \frac { d } { d z } E _ { z } ,
$$

the radial motion equation is

$$
\frac { d } { d t } ( \gamma \dot { r } ) = - \frac { q r } { 2 m } \frac { d } { d z } E _ { z } .
$$

As for the fundamental synchronous mode, one has $\omega t = k _ { 0 } z + \Delta \phi$ . So,in the position coordinates, the radial motion equation is expressed as

$$
r ^ { \prime \prime } = - \frac { q E _ { 0 } r } { 2 \gamma m \beta ^ { 2 } c ^ { 2 } } \sum _ { n = - \infty } ^ { \infty } \frac { d } { d z } ( b _ { n } c o s ( \Delta \phi - \frac { 2 \pi } { D } n z ) ) .
$$

we divide the field into two parts: the fundamental mode field and all the high spatial harmonic fields which is a small pertubation in comparision with the main fundamental synchronoumous field. In order to solve $r$ ， we expanse $r$ into $r _ { 0 } + r _ { 1 }$ （omitting higher order terms ） to get

$$
r _ { 0 } ^ { \prime \prime } = - \frac { q E _ { 0 } r _ { 0 } } { 2 \gamma m \beta ^ { 2 } c ^ { 2 } } \frac { d } { d z } ( b _ { 0 } c o s ( \Delta \phi ) ) ,
$$

$$
r _ { 1 } ^ { \prime \prime } = - \frac { q E _ { 0 } r _ { 0 } } { 2 \gamma m \beta ^ { 2 } c ^ { 2 } } ( \sum _ { n = 1 } ^ { \infty } \frac { d } { d z } ( b _ { n } c o s ( \Delta \phi - \frac { 2 \pi } { D } n z ) ) + \sum _ { n = - \infty } ^ { - 1 } \frac { d } { d z } ( b _ { n } c o s ( \Delta \phi - \frac { 2 \pi } { D } n z ) ) .
$$

Assuming $\Delta \phi$ is unchanged, we can get $r _ { 0 } = c o n s t a n t$ from Equation (1O). From the equation about $r _ { 1 }$ ，we get approximately

$$
r _ { 1 } ^ { \prime } = - \frac { q E _ { 0 } r _ { 0 } } { 2 \gamma m \beta ^ { 2 } c ^ { 2 } } ( \sum _ { n = 1 } ^ { \infty } ( b _ { n } c o s ( \Delta \phi - \frac { 2 \pi } { D } n z ) ) + \sum _ { n = - \infty } ^ { - 1 } ( b _ { n } c o s ( \Delta \phi - \frac { 2 \pi } { D } n z ) ) .
$$

We can finnally get the solution of $r$ to the first order approximately

$$
r = r _ { 0 } + \frac { q E _ { 0 } r _ { 0 } } { \gamma m \beta ^ { 2 } c ^ { 2 } } ( \sum _ { n = 1 } ^ { \infty } \frac { D } { 2 \pi n } b _ { n } s i n ( \Delta \phi - \frac { 2 \pi } { D } n z ) + \sum _ { n = - \infty } ^ { - 1 } \frac { D } { 2 \pi n } b _ { n } s i n ( \Delta \phi - \frac { 2 \pi } { D } n z ) ) .
$$

It is obvious that there exists high harmonical mode components in the transverse motion except the fundamental mode part. According to the principle of Flourier spectrum analyze, the amplitude of the high harmonics mode is small and the effect of each high harmonics is weak.But the sum effect of allthe harmonics can be strong if the high harmonics mode is not damped effectively.

Alternatively, we can use the mapping technique to have the following 2D mapping under the special case of $b _ { 0 } = b _ { n } = 1$ （204号

$$
r _ { n + 1 } ^ { \prime } - r _ { n } ^ { \prime } = - \frac { q E _ { 0 } r _ { n } } { 2 \gamma _ { n } m c ^ { 2 } } c o s ( \Delta \phi _ { n } ) D ,
$$

$$
r _ { n + 1 } - r _ { n } = D r _ { n } ^ { \prime } ,
$$

where $r _ { n } = r ( n D )$ 业

# 5 Numerical result

For the sake of convenience, we use the S-band electron linac parameters. The working frequency is $2 8 5 6 M H z$ ， $\begin{array} { r } { \lambda = 1 0 . 5 c m , k _ { 0 } = \frac { 2 \pi } { \lambda } , D = 3 . 5 c m } \end{array}$ . The typical accelerating electric field is $2 0 M V / m$ ( SLAC S-band accelerating structure ). We use numerical method to solve the mappings about longitudinal and transverse motion, the typical phase space is shown as

![](images/48bb688e8279764d27074c0349b7fc375a2c88186e384d9fa0e8100136699ca7.jpg)  
Figure 1. The typical phase space.

From the figure above,we can see that the radial motion includes high harmonic components. Actually, the condition $b _ { 0 } = b _ { n } = 1$ is strong,as the amplitude of the high harmonic mode is weaker than that of the fundamental mode. So the numerical result presented above overestimate the effect of the high harmonic modes comparatively.

# 6 Discussion

In this paper, we set up a series of equations and mappings to discuss the high harmonic mode effect on the beam dynamics in RF Linac. Some numerical results are also provided using the standard SLAC S-band electron linac parameters.

# References

[1] Xiongwei Zhu, The Effect of High Spatial Harmonics in RF Linac,International Journal of Infrared and Millimeter Waves, Vol.25, No.4, 667(2004).   
[2] Xiongwei Zhu, K.Nakajima, W-band accelerator study in KEK, AAC 200o, USA.   
[3] Xiongwei Zhu, K.Nakajima, Design of W-band photoinjector, 25th linac meeeting in Japan, Himeiji, 2000.   
[4] Zhu Xiong-Wei, HEP & NP, 2002.