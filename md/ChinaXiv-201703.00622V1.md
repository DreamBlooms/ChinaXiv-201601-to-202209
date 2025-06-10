# On uncertainty of the beam energy measurement in $e ^ { + } e ^ { - }$ collision using Compton Backscattering.\*

X.H.Mo $^ { 1 }$ +

1（Institute of High Energy Physics,CAS,Beijing 1O0049,China）

March8,2017

AbstractThe beam energy is measured in $e ^ { + } e ^ { - }$ collision by using Compton Backscattering. The uncertainty of this measurement process is studied by virtue of analytical formulas, and the special effects of variant energy spread and energy drift on the systematic uncertainty estimation are also studied with Monte Carlo sampling technique. These quantitative conclusions are especially important for understanding the uncertainty of beam energy measurement system.

Key wordsCompton backscattering,uncertainty,energy shift PACS32.80.Aa, 06.20.Dk, 29.30.Kv

# 1 Introduction

The upgraded Beijing electron-positron collider (BEPCII） is a $\tau$ -charm factory with a center mass of energy ranging from 2.0 to 4.6 GeV and a design peak luminosity of $1 0 ^ { 3 3 }$ $\mathrm { c m ^ { - 2 } \ s ^ { - 1 } }$ （20 at beam energy of 1.89 GeV [1, 2]. The upgraded Beijing spectrometer detector (BESIII) with high efficiency and good resolution for both charged and neutral particles was constructed and started data taking in 2008 [3]. BESII research region covers charm physics， charmonium physics, spectroscopy of light hadrons and $\tau$ -lepton physics [4].

After vast amounts of data are acquired and analyzed, the statistical uncertainties in analyses of physics become smaller and smaller, while the systematic uncertainties play more and more prominent roles [5,6,7],one of which is the uncertainty due to the measurement of beam energy. To reduce such an uncertainty， start from year 2Oo7, a high accuracy beam energy measurement system (BEMS） was designed，constructed,and put into operation at the end of year 2010 [8,9,10,11],which is of great importance for many physics analyses at BESIII, such as $\tau$ mass measurement, charmonium resonance scans,and determination of the branching ratio with the uncertainty at the level of $1 \%$ to $2 \%$ .The measurement procedure of BEMS can be recapitulated as follows [12]: firstly, the laser source provides the laser beam and the optics system focuses the laser beam and guides it to make head-on colisions with the electron (or positron) beam in the vacuum pipe,after that the backscattering high energy photon will be detected by the High Purity Germanium (HPGe) detector, which is the key instrument of BEMS. The accuracy of beam energy depends merely on the detection result of backscattering photon.

The essence of working principle of BEMS is Compton backscattering process (CBS). In order to understand the main feature of BEMS, the uncertainty of this measurement process is addressed by virtue of analytical formulas, where some experimentally meticulous details are neglected. These acquired quantitative results are of greatest consequence for the qualitatively understanding the actual uncertainty of BEMS. Moreover,an experimentally special phenomenon is studied by simulation approach，which reveals a possible source of systematic uncertainty of BEMS.

# 2 Energy formulas

Here considered is a special and crucial case of CBS, that is the electron makes a head-on collsion with the photon, whose geometry is sketched in Fig.1. The energies of electron and photon before (denoted by subscript 1) and after (denoted by subscript 2) the collision are denoted as （204号 $\varepsilon _ { 1 , 2 }$ (for electron） and $\omega _ { 1 , 2 }$ (for photon),respectively.

![](images/c47b4b8587d0e25878375cc5e4fe9297830e5c89a41e4dda35b630b9735bef1c.jpg)  
Figure 1: Geometry of electron $( e )$ and photon $( \gamma )$ before(a) and after(b) the head-on collision.The stright line denotes $e$ while the wavy line $\gamma$ ：

In the light of the special theory of relativity, the energy and momentum can be expressed as

$$
\omega = h \nu \ , p _ { \gamma } = { \frac { \omega } { c } } \ ,
$$

for photon and

$$
\varepsilon = \frac { m _ { e } c ^ { 2 } } { \sqrt { 1 - \displaystyle \frac { v ^ { 2 } } { c ^ { 2 } } } } ~ , \quad p _ { e } = \frac { \varepsilon v } { c ^ { 2 } } ~ ,
$$

for electron. In above equations, $h$ is Plant constant and $m _ { e }$ the electron mass. With Eqs.(1) and (2), it is readily to obtain the kinematic for electron and photon colision system. According

to the law of energy and momentum conservation,

$$
\omega _ { 1 } + \varepsilon _ { 1 } = \omega _ { 2 } + \varepsilon _ { 2 } \ ,
$$

and

$$
- \frac { \omega _ { 1 } } { c } + \frac { \varepsilon _ { 1 } v _ { 1 } } { c ^ { 2 } } = \frac { \omega _ { 2 } } { c } + \frac { \varepsilon _ { 2 } v _ { 2 } } { c ^ { 2 } } \ ,
$$

or

$$
- \omega _ { 1 } + \frac { \varepsilon _ { 1 } v _ { 1 } } { c } = \omega _ { 2 } + \frac { \varepsilon _ { 2 } v _ { 2 } } { c } \ .
$$

Based on the Eqs.(3) and (4),it can be obtained with simple algebra

$$
\omega _ { 2 } = \frac { \varepsilon _ { 1 } ^ { 2 } \left( 1 + \displaystyle \frac { v _ { 1 } } { c } \right) ^ { 2 } } { 2 \varepsilon _ { 1 } \left( 1 + \displaystyle \frac { v _ { 1 } } { c } \right) + \displaystyle \frac { m _ { e } ^ { 2 } c ^ { 4 } } { \omega _ { 1 } } } \ .
$$

For BESII, the optimal energy point is at 1.89 GeV, the velocity of electron with such high energy is very closely to that of light $( c )$ , in another word, $v _ { 1 } / c \approx 1$ with the negligible error. With such an approximation, Eq. (5) is recasted as

$$
\omega _ { 2 } = \frac { \varepsilon _ { 1 } ^ { 2 } } { \varepsilon _ { 1 } + \displaystyle \frac { m _ { e } ^ { 2 } c ^ { 4 } } { 4 \omega _ { 1 } } } \ .
$$

In BEMS, $\omega _ { 1 }$ is provdied by laser and $\omega _ { 2 }$ is measured by HPGe detector, and $\varepsilon _ { 1 }$ is the beam energy that is to be determined with high accuracy. From Eq. (5), it is worked out

$$
\varepsilon _ { 1 } = \frac { \omega _ { 2 } } { 2 } \left( 1 + \sqrt { 1 + \frac { m _ { e } ^ { 2 } c ^ { 4 } } { \omega _ { 1 } \omega _ { 2 } } } \right) + \frac { m _ { e } ^ { 2 } } { 2 \omega _ { 2 } \left( 1 + \sqrt { 1 + \frac { m _ { e } ^ { 2 } c ^ { 4 } } { \omega _ { 1 } \omega _ { 2 } } } \right) } ,
$$

or from Eq. (6), it is acquired

$$
\varepsilon _ { 1 } = \frac { \omega _ { 2 } } { 2 } \left( 1 + \sqrt { 1 + \frac { m _ { e } ^ { 2 } \ c ^ { 4 } } { \omega _ { 1 } \ \omega _ { 2 } } } \right) \ .
$$

# 3 Uncertainty formulas

The start point of uncertainty analysis of this section is the two formulas obtained in the previous section,viz. Eqs.(7) and (8). For brevity, in this section we adopt the nature unity where $c = 1$ (the subscript $e$ is also suppressed for electron mass） and begin with the comparatively simple

case,that is Eq. (8),by virtue of which it is immediately obtained

$$
\begin{array} { r l } { \frac { \partial \varepsilon _ { 1 } } { \partial m } } & { = \ \frac { m } { 2 \omega _ { 1 } } \cdot \frac { 1 } { \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega _ { 2 } } } } \ , } \\ { \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 1 } } } & { = \ - \frac { m ^ { 2 } } { 4 \omega _ { 1 } ^ { 2 } } \cdot \frac { 1 } { \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega _ { 2 } } } } \ , } \\ { \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 2 } } } & { = \ \frac { 1 } { 2 } \left( 1 + \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega _ { 2 } } } \right) - \frac { m ^ { 2 } } { 4 \omega _ { 1 } \omega _ { 2 } } \cdot \frac { 1 } { \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega _ { 2 } } } } \ . } \end{array}
$$

On the strength of Eq. (8),Eq. (9) can be rewritten in the more concise forms as follows

$$
\begin{array} { r l r } { \frac { \partial \varepsilon _ { 1 } } { \partial m } } & { = } & { \frac { \varepsilon _ { 1 } } { m } \left( 1 - \frac { 1 } { \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega ^ { 2 } } } } \right) , } \\ { \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 1 } } } & { = } & { - \frac { \varepsilon _ { 1 } } { 2 \omega _ { 1 } } \left( 1 - \frac { 1 } { \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega } } } \right) , } \\ { \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 2 } } } & { = } & { \frac { \varepsilon _ { 1 } } { 2 \omega _ { 2 } } \left( 1 + \frac { 1 } { \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega ^ { 2 } } } } \right) . } \end{array}
$$

The compact expression for uncertainty evaluation is as follows:

$$
\frac { \delta \varepsilon _ { 1 } } { \varepsilon _ { 1 } } = \frac { f _ { + } } { 2 } \cdot \frac { \delta \omega _ { 2 } } { \omega _ { 2 } } \oplus \frac { f _ { - } } { 2 } \cdot \frac { \delta \omega _ { 1 } } { \omega _ { 1 } } \oplus f _ { - } \cdot \frac { \delta m } { m } \ ,
$$

with factors $f _ { \pm }$ defined as

$$
f _ { \pm } = 1 \pm \frac { 1 } { \sqrt { 1 + \displaystyle \frac { m ^ { 2 } } { \omega _ { 1 } \omega _ { 2 } } } } .
$$

Now we turn to Eq. (7). The similar process as that for Eq. (8) could lead to the fairly cumbersome derivative expressions of $\varepsilon _ { 1 }$ with respect to $\omega _ { 2 }$ ， $\omega _ { 1 }$ ,or $m$ , which have been degraded into appendix A. Herein we present another recipe. Comparing Eqs. (7) and (8), it is clear that the Eq.(8) is just the first term of Eq.(7),therefore it is nature to find an uncertainty expression for Eq.(7) which could incorporates the result acquired based on Eq.(8). To this end, we return to Eq. (5). If a function of $\varepsilon _ { 1 }$ ， $g ( \varepsilon _ { 1 } )$ , is introduced, Eq.(5） becomes

$$
\omega _ { 2 } = \frac { g ^ { 2 } ( \varepsilon _ { 1 } ) } { 2 g ( \varepsilon _ { 1 } ) + \displaystyle \frac { m ^ { 2 } } { \omega _ { 1 } } } \ .
$$

with

$$
g ( \varepsilon _ { 1 } ) = \varepsilon _ { 1 } \left( 1 + { \frac { v _ { 1 } } { c } } \right) = \varepsilon _ { 1 } + \sqrt { \varepsilon _ { 1 } ^ { 2 } - m ^ { 2 } } \ .
$$

Then it is readily to obtained

$$
g ( \varepsilon _ { 1 } ) = \omega _ { 2 } \cdot \left( 1 + \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \ \omega _ { 2 } } } \right) \ ,
$$

and

$$
\varepsilon _ { 1 } = \frac { g } { 2 } + \frac { m ^ { 2 } } { 2 g } \ .
$$

Noticing the similarity between Eqs. (8) and (15),it is immediately obtained

$$
\frac { \delta g } { g } = \frac { f _ { + } } { 2 } \cdot \frac { \delta \omega _ { 2 } } { \omega _ { 2 } } \oplus \frac { f _ { - } } { 2 } \cdot \frac { \delta \omega _ { 1 } } { \omega _ { 1 } } \oplus f _ { - } \cdot \frac { \delta m } { m } \ .
$$

Next, from Eq. (16), it also easy to get

$$
\frac { \delta \varepsilon _ { 1 } } { \varepsilon _ { 1 } } = \frac { g ^ { 2 } - m ^ { 2 } } { g ^ { 2 } + m ^ { 2 } } \cdot \frac { \delta g } { g } \oplus \frac { 2 m ^ { 2 } } { g ^ { 2 } + m ^ { 2 } } \cdot \frac { \delta m } { m } \ .
$$

# 4Statistical and systematic uncertainties

Analytical formulas acquired in the previous section are the foundation for the uncertainty analysis relevant to CBS. In principle, there are two types of uncertainty: statistical and systematic. In a nutshell, the statistical are those types of uncertainties that have a random spread, and their uncertainties decrease with augment of data; the systematic include everything else. In practice,it is not always easy to distinguish two types of uncertainty,and sometimes it is rather difficult to identify the feature of systematic uncertainty. For example,as to the each term in error formulas such as Eqs. (11) and (18), it could include both statistical and systematic uncertainties. From a pragmatistic point of view,we lay stress on the relative magnitude of each term instead of focusing on its feature,and try to figure out the leading contribution for the uncertainty evaluation.

Table 1: Some parameters related to BCS.   

<html><body><table><tr><td>Parameter</td><td>Central Value (value scope)</td><td>Relative error</td><td>Reference</td></tr><tr><td>me</td><td>0.51099828MeV</td><td>2.153×10-8</td><td>[13]</td></tr><tr><td>W1</td><td>0.114426901 eV</td><td>8.739×10-9</td><td>[14,10]</td></tr><tr><td>W2</td><td>(2-7) MeV</td><td>5 ×10-5</td><td>[12, 10]</td></tr></table></body></html>

To begin with,we estimate the deviation from 1 for the factor $f _ { \pm }$ defined in Eq. (12). With （204号 $m _ { e } = 0 . 5 1 0 9 9 8 2 8 \mathrm { M e V }$ $\omega _ { 1 } = 0 . 1 1 4 4 2 6 9 0 1 \mathrm { e V }$ ,and $\omega _ { 2 }$ ranges from 2 to 7 MeV, the corresponding deviation is within the scope $\pm ( 0 . 9 4 - 1 . 7 5 ) \ \%$ . Therefore,it is accurate enough to approximate $f _ { \pm }$ as $1$ . Then,according to the values listed in Table 1, the relative errors of $m _ { e }$ and $\omega _ { 1 }$ are three orders of magnitude lower than that of $\omega _ { 2 }$ ，which means the leading contribution for the uncertainty of BCS is the first term in Eq. (11), that is to say we have the relation

$$
\frac { \delta \varepsilon _ { 1 } } { \varepsilon _ { 1 } } \simeq \frac { 1 } { 2 } \frac { \delta \omega _ { 2 } } { \omega _ { 2 } }
$$

with fairly high accuracy (the additional uncertainty is much less than $1 0 ^ { - 3 }$ ）

Equation (19) indicates that the feature of electron (positron） beam (denoted by $\varepsilon _ { 1 }$ and （204号 $\delta \varepsilon _ { 1 }$ ）is totally determined by that of backscattering photon (denoted by $\omega _ { 2 }$ and $\delta \omega _ { 2 }$ )，and vice versa.With use of BEMS, $\omega _ { 2 }$ is determined by the position of Compton edge while $\delta \omega _ { 2 }$ by the slope of the edge1. Herein, the existent of edge slope is just due to $\delta \varepsilon _ { 1 }$ , the energy spread of accelerator. It is noticeable en passant that $\varepsilon _ { 1 }$ and $\delta \varepsilon _ { 1 }$ are constants during measurement. For the certain beam energy (fixed $\varepsilon _ { 1 }$ ), the energy spread ( $\delta \varepsilon _ { 1 }$ ） is solely determined by the structure of accelerator itself and therefore must be fixed in common sense [15]. However, during the data taking of $J / \psi$ sample performed in year 2Ol2,a peculiar phenomenon is found. As shown in Fig. 2,it is noticed that the cross sections vary with the decrease of beam current，which means some variations of beam status during energy measurement ². Such variations imply the variant energy,or energy spread,or both of them. The effects,as being elucidated in the next section,can lead to energy shift in measurement of beam energy. This is a crux matter for the uncertainty analysis of BEMS.

# 5Effects of variations of energy spread and energy drift on measured energy

This section is devoted to the investigation of efects of variations of energy spread and drift on measured energy. Two cases are considered: 1. Assuming there is no energy drift, the energy shift is only due to the variation of energy spread; 2. Assuming energy spread is fixed, the energy shift is only due to the energy drift. Monte Carlo simulation approach is adopted for the following study.

# 5.1 Simulation of Compton edge

The backscattering photons from head-on colision with electron (positron） beam will form a sharp edge in a detective spectrum. The pure sharp edge at certain energy (denoted by $\omega$ ）is approximated by the normalized function [16]

$$
h ( x ) = [ p _ { 3 } + p _ { 2 } ( x - p _ { 0 } ) ] \Theta ( p _ { 0 } - x ) \ .
$$

Here, the product $p _ { 2 } ( x - p _ { 0 } )$ is small compared to $p _ { 3 }$ ; for $p _ { 2 } = 0$ and $p _ { 3 } = 1$ ， $h ( x )$ reduces to the normal step function.The function $h ( x )$ is then folded with a Gaussian of standard deviation

# one vs another

![](images/10a2afaf9685d673a69b7ad2200fb86363158c9992b2ca3274c0b3ca655e45b7.jpg)  
Figure 2: The relation between beam current and the “relative” cross section with data taken at $J / \psi$ resonance. The horizontal scale is denoted by ‘ $\cdot I _ { e } \times I _ { p } / A ^ { 2 }$ ” which means the product of electron current ( $I _ { e }$ ）and positron current ( $I _ { p }$ )，whose unit is the square of Ampere. The ratio of the number of inclusive hadronic events to that of the two-gamma events (both from online database)，which is proportional to the observed cross section, is denoted as “relative” cross section.

$p _ { 1 }$

$$
g ( x ) = \frac { 1 } { \sqrt { 2 \pi } p _ { 1 } } e ^ { - \frac { x ^ { 2 } } { 2 p _ { 1 } ^ { 2 } } } \ .
$$

The resulting function for variable position and height of the edge is given by

$$
f ( x ) = \int _ { - \infty } ^ { + \infty } d t h ( t ) g ( x - t ) \ .
$$

Anyway, due to the existence of background, a linear function $p _ { 4 } ( x - p _ { 0 } ) + p _ { 5 }$ is added to $f ( x )$ to describe the shape of background. Therefore, the final synthetic function has the form:

$$
g ( x , { \vec { p } } ) = { \frac { 1 } { 2 } } ( p _ { 2 } ( x - p _ { 0 } ) + p _ { 3 } ) \cdot \mathrm { e r f c } \left[ \frac { x - p _ { 0 } } { \sqrt { 2 } p _ { 1 } } \right] - { \frac { p _ { 1 } p _ { 2 } } { \sqrt { 2 \pi } } } \cdot \exp \left[ - \frac { ( x - p _ { 0 } ) ^ { 2 } } { 2 p _ { 1 } ^ { 2 } } \right] + p _ { 4 } ( x - p _ { 0 } ) + p _ { 5 } \ ,
$$

with [17]

$$
\mathrm { e r f c } ( z ) \equiv \frac { 2 } { \sqrt \pi } \intop _ { z } ^ { \infty } d u e ^ { - u ^ { 2 } } .
$$

The parameters in Eq. (23) are: $p _ { 0 }$ - edge position; $p _ { 1 }$ - edge width; $p _ { 2 }$ - slope left; $p _ { 3 }$ - edge amplitude; $p _ { 4 }$ - slope right; $p _ { 5 }$ - background. Parameter $p _ { 0 }$ gives the information about the average electron beam energy during the data acquisition period,while $p _ { 1 }$ is mostly coupled with the electron beam energy spread.

In the simulation,the following form is adopted

$$
f ( x ) = \frac { 1 } { 2 } a _ { 2 } [ q + a _ { 1 } ( x - \omega ) ] \cdot \mathrm { e r f c } \left[ \frac { x - \omega } { \sqrt { 2 } \sigma } \right] - \frac { q a _ { 1 } a _ { 2 } } { \sqrt { 2 \pi } } \cdot \exp \left[ - \left( \frac { x - \omega } { \sqrt { 2 } \sigma } \right) ^ { 2 } \right] + b _ { 2 } [ q + b _ { 1 } ( x - \omega ) ] \ ,
$$

where $\omega$ is the position of Compton edge that is used to determine the beam energy; $\sigma$ is the edge width that is related with the beam energy spread ( $o _ { s }$ )； $q$ is unity parameter that is used to determine the unity of $x$ ( $q = 1$ , the unity of $x$ is MeV while $q = 1 0 0 0$ , the unity of $x$ is keV).

Table 2: Input parameters for Compton edge simulation.   

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>me</td><td>0.51099828MeV</td></tr><tr><td>Wo</td><td>0.114426901 eV</td></tr><tr><td>Ecm</td><td>3096.916MeV</td></tr><tr><td>△</td><td>1 MeV</td></tr><tr><td>e</td><td>1548.418MeV</td></tr><tr><td>Js</td><td>0.707107MeV</td></tr><tr><td>W</td><td>4190.521keV</td></tr><tr><td></td><td>3.8272keV</td></tr><tr><td>q</td><td>1000</td></tr><tr><td>a1</td><td>-0.1</td></tr><tr><td>a2</td><td>0.3</td></tr><tr><td>b1</td><td>-0.2</td></tr><tr><td>b2</td><td>0.1</td></tr></table></body></html>

The relation between $\omega$ and $\epsilon$ is as follows 3

$$
\omega = \frac { \epsilon ^ { 2 } } { \epsilon + \frac { m _ { e } ^ { 2 } } { 4 \omega _ { 0 } } } , \epsilon = \frac { \omega } { 2 } \left( 1 + \sqrt { 1 + \frac { m _ { e } ^ { 2 } } { \omega \omega _ { 0 } } } \right) ;
$$

and the relation between $\sigma _ { s }$ and $\sigma$ is as follows 4

$$
\boldsymbol { \sigma } = 2 \cdot \frac { \boldsymbol { \omega } } { \epsilon } \cdot \boldsymbol { \sigma } _ { s } .
$$

In addition, it should be noted that $\epsilon = E _ { c m } / 2$ and $\sigma _ { s } = \Delta / \sqrt { 2 }$ ，where $E _ { c m }$ is the center-of-mass (C.M.) energy, and $\Delta$ the spread of $E _ { c m }$ . For the energy at $J / \psi$ resonance, the input parameters for Compton edge simulation are tabulated in Table 2.

# 5.2 Relation between observed cross section and energy spread

The cross section of the process $e ^ { + } e ^ { - } \to J / \psi \to f$ (where $f$ denotes some final state) is described by the Breit-Wigner formula

$$
\sigma _ { B W } ( s ) = \frac { 1 2 \pi \cdot \Gamma _ { e } \Gamma _ { f } } { ( s - M ^ { 2 } ) ^ { 2 } + \Gamma _ { t } ^ { 2 } M ^ { 2 } } \ ,
$$

where $\sqrt { s }$ is the C.M. energy( $\sqrt { s } \ : = \ : E _ { c m }$ ， $\Gamma _ { e }$ and $\Gamma _ { f }$ are the widths of $J / \psi$ decaying into $e ^ { + } e ^ { - }$ and $f$ ， $\Gamma _ { t }$ and $M$ are the total width and mass of $J / \psi$ . Taking the initial state radiative correction into consideration, the cross section becomes [18]

$$
\sigma _ { r . c . } ( W ) = \int _ { 0 } ^ { x _ { m } } d x F ( x , s ) \frac { 1 } { | 1 - \Pi ( s ( 1 - x ) ) | ^ { 2 } } \sigma _ { B W } ( s ( 1 - x ) ) ,
$$

where $x _ { m } = 1 - s ^ { \prime } / s$ ， $\sqrt { s ^ { \prime } }$ is the experimentally required minimum invariant mass of the final state $f$ after losing energy due to multi-photon emission; $F ( x , s )$ has been calculated in many references [18,19, 20] and $\Pi ( s ( 1 - x ) )$ is the vacuum polarization factor. The $e ^ { + } e ^ { - }$ colliders have finite energy spread. The energy spread function $G ( { \sqrt { s } } , { \sqrt { s ^ { \prime } } } )$ is usually a Gaussian distribution :

$$
G ( \sqrt { s } , \sqrt { s ^ { \prime } } ) = \frac { 1 } { \sqrt { 2 \pi } \Delta } e ^ { - \frac { ( \sqrt { s } - \sqrt { s ^ { \prime } } ) ^ { 2 } } { 2 \Delta ^ { 2 } } } ,
$$

where $\Delta$ describes the C.M.energy spread of the accelerator, $\sqrt { s }$ and $\sqrt { s ^ { \prime } }$ are the nominal and actual C. M. energy respectively. So the experimentally measured resonance cross section (observed cross section) is the radiatively corrected Breit-Wigner cross section folded with the energy spread function:

$$
\sigma _ { e x p } ( \sqrt { s } ) = \int _ { 0 } ^ { \infty } \sigma _ { r . c . } ( \sqrt { s ^ { \prime } } ) G ( \sqrt { s ^ { \prime } } , \sqrt { s } ) d \sqrt { s ^ { \prime } } .
$$

where $\sigma _ { r . c }$ is defined by Eq. (26)

Numerical calculation indicates that the radiative correction reduces the maximum cross section of $J / \psi$ by $5 2 \%$ ; the energy spread further lowers down the cross section by an order of magnitude depending on the value of the energy spread. Both the radiative correction and the energy spread shifts the maximum height of resonance peak to above the resonance nominal mass. In actual experiments,data are naturally taken at the energy which yields the maximum inclusive hadron cross section. When the energy spread change, both the maximum cross section and the position of energy for the maximum cross section change correspondingly.

# 5.3 Relation of cross section with energy spread and energy drift

The minimization subroutine program DMINFC from CERNLIB [21] is used to find the position of energy $( E _ { m a x } )$ ）for the maximum cross section and the corresponding maximum cross section $\left( \sigma _ { m } \right)$ itself corresponding to distinctive energy spread ( $\Delta$ ). The energy shift ( $\delta E _ { m n }$ ) is defined as

![](images/c3e97acdd21bbb1a6a43667ceb78566c382a125a4ef9611c20ab32253fa076af.jpg)

![](images/692021cef2f49acd5c939f809e7221777c365877c6c2fe3633525b428b4b80bf.jpg)  
Figure 3: The relation between the energy spread $\Delta$ and the maximum observed cross sectior （204 $\sigma _ { m }$ (a),and the energy shift $\delta E$ and the observed cross section $\sigma$ (b).

![](images/b7a40c57a895379a0933087ba0e2f0c6b4a9fca55b49ce3cb57ac355864c3ee9.jpg)  
Figure 4: The relation between beam current and the “relative” cross section, $R _ { \sigma }$ (denoted by diamond in (a)） and “relative” energy spread $R _ { \Delta }$ (denoted by solid circle in (a)). The horizontal scale is denoted by $^ { 6 4 } I _ { e } \times I _ { p } / A ^ { 2 }$ ” which means the product of electron current ( $I _ { e }$ ） and positron current $\left( I _ { p } \right)$ ,whose unit is the square of Ampere.   
Figure 5: The relation between beam current and the “relative” cross section, $R _ { \sigma }$ (denoted by diamond in (a)）and energy drift $\delta _ { E }$ (denoted by solid circle in (a)). The horizontal scale is denoted by “ $Y _ { e } \times I _ { p } / A ^ { 2 }$ ” which means the product of electron current $\left( I _ { e } \right)$ and positron current $\left( I _ { p } \right)$ , whose unit is the square of Ampere.

the difference between the maximum energy ( $E _ { m a x }$ ） and the nominal energy ( $E _ { n o m } = 3 0 9 6 . 9 1 6$ （204 MeV),that is

$$
\delta E _ { m n } = E _ { m a x } - E _ { n o m } \ ,
$$

and the fit curve for $\delta E _ { m n }$ against $\Delta$ is

$$
f _ { \delta E _ { m n } } ( x ) [ \mathrm { k e V } ] = 1 . 1 1 1 7 \cdot x [ \mathrm { M e V } ] + 9 8 . 5 6 7 \ ,
$$

and the fit curve for $\sigma _ { m }$ against $\Delta$ is (refer to Fig. 3(a))

$$
f _ { \sigma _ { m } } ( x ) [ \mathrm { p b } ^ { - 1 } ] = 3 . 3 8 8 5 / x ^ { 0 . 8 2 3 2 2 } - 0 . 2 4 2 3 7 \ , \quad [ x \colon \mathrm { M e V } ] \ .
$$

In Fig. $4 ( \mathrm { a } )$ ， the ordinate is the ratio of the number of inclusive hadronic events to that of the two-gamma events,which is proportional to the observed cross section and denoted as “relative” cross section ( $R _ { \sigma }$ ） in this monograph; in Fig. 4(b),the ordinate is the ratio of two energy spread, denoted as “relative” energy spread $( R _ { \Delta } )$ . The fit curve for $R _ { \Delta }$ against $I _ { e } \times I _ { p }$ is

$$
f _ { R _ { \Delta } } ( x ) = 0 . 9 6 4 5 1 + 4 . 5 0 1 2 \cdot x - 4 6 . 6 1 2 \cdot x ^ { 2 } + 1 2 9 . 4 4 \cdot x ^ { 3 } \ .
$$

Figure 3(b) show the relation between observed cross section $\sigma$ and energy drift $\delta E$ ，which is defined as follows

$$
\delta E = E - E _ { m a x } \ ,
$$

where $E _ { m a x } = 3 0 9 6 . 9 9 8 1$ MeV corresponding to the energy spread 1 MeV. The fit curve is

$$
f _ { \sigma } ( x ) [ \mathrm { p b } ^ { - 1 } ] = 3 . 1 3 9 1 \cdot e ^ { - 0 . 4 2 6 3 8 \cdot x ^ { 2 } } , \quad [ x \colon \mathrm { M e V } ] .
$$

The ordinate of Fig. 5(a) is the same as that of Fig. 4(a); the ordinate of Fig. 5(b) is the energy drift, denoted as ( $\delta _ { E }$ ). The fit curve for $\delta _ { E }$ against $I _ { e } \times I _ { p }$ is

$$
f _ { \delta _ { E } } ( x ) = - 0 . 3 8 5 4 8 + 2 3 . 9 5 5 \cdot x - 2 1 6 . 4 7 \cdot x ^ { 2 } + 5 6 1 . 1 5 \cdot x ^ { 3 } \ .
$$

As a matter of fact, in order to obtain the relation between $R _ { \sigma }$ and $R _ { \Delta }$ ( $\delta _ { E } )$ ，the special normalization is adopted. The nitty-gritty is elaborated in Appendix B.Here, $f _ { R _ { \Delta } } ( x )$ in Eq. (31) and $f _ { \delta _ { E } } ( x )$ Eq. (33) reflect the possible variation of energy spread or energy drift within one beam injection,and can be treated as probability function for variation of $R _ { \Delta }$ and $\delta _ { E }$ . Therefore, the variable $x$ should take the value between O and 1. In the following simulation, the acceptancerejection technique [22, 23] is adopted for distribution sampling.

# 5.4 Fitted energy for different cases

# 5.4.1 Effect due to variant energy spread

The simulation for Compton edge is performed for two cases: 1) for the fix energy spread, the sampling of the edge is according to distribution formulated in Eq. (24); 2) for the variate energy spread,the sampling of the edge is also according to distribution formulated in Eq. (24) but with variate $\sigma$ , that is the fix value of $\sigma$ is replaced by variant $\sigma ( x )$ ,i.e.

$$
\sigma ( x ) = \sigma \cdot f _ { R _ { \Delta } } ( x ) \ ,
$$

![](images/f782dd184f02153a727270b7ad195194b2bbf1801f810f3c9c3258a476046bf3.jpg)  
Figure 6: The comparison of simulations of Compton edge for different cases: fix and variant energy spread (a); fix and variant energy drift (b). The fit results for diferent cases: fix energy (c) and variant energy spread (d); fix energy (e),with energy drift (f). Herein, $E _ { c m }$ is distinctive for (c)and (d) as indicted in Table 4. In all plot circle denote the fix cases while box the variant cases; the curve is the best fit result. There are O.5 Milion counts in each sample.

where $f _ { R _ { \Delta } } ( x )$ is the distribution in Eq. (31),and $x$ is a random number of between O and 1.   
The simulated distributions for two cases are shown in Fig. 6(a).

The fitted results based on the simulated distributions for two cases are given in Table. 3, and the fit curves for two cases is displayed in Fig. 6(c) and (d). The difference for fitted beam energy is about 0.113 MeV, or 0.226 MeV for C.M. energy.

Table 3: The fit results of beam energy for different cases of energy spread : fix energy spreac and variant energy spread.   

<html><body><table><tr><td>Parameter</td><td>Fix o</td><td>Variant o</td></tr><tr><td>x²</td><td>83.64406</td><td>77.50543</td></tr><tr><td>E</td><td>1548.300±0.082 MeV</td><td>1548.413±0.115MeV</td></tr><tr><td>△</td><td>1.1215 ±0.0480 MeV</td><td>1.0924±0.0573MeV</td></tr><tr><td>a1</td><td>-0.12464 ± 0.01937</td><td>-0.10374 ±0.03012</td></tr><tr><td>a2</td><td>5.8016 ± 0.0281</td><td>5.7938 ± 0.0285</td></tr><tr><td>b1</td><td>-2.0528 ±0.0807</td><td>-2.0300 ± 0.0819</td></tr><tr><td>b2</td><td>1.9456 ± 0.0134</td><td>1.9471 ± 0.0133</td></tr></table></body></html>

Table 4: The fit results of beam energy for different cases of energy drift : fix energy and with energy drift. The input $E _ { c m } = 3 0 9 6 . 9 9 8 1$ GeV instead of $E _ { c m } = 3 0 9 6 . 9 1 6$ GeV.   

<html><body><table><tr><td>Parameter</td><td>Fix w</td><td>Variant w</td></tr><tr><td>x²</td><td>86.93219</td><td>76.01074</td></tr><tr><td>E</td><td>1548.339±0.078MeV</td><td>1548.572±0.100MeV</td></tr><tr><td>△</td><td>1.1211±0.0469 MeV</td><td>1.0631±0.0517 MeV</td></tr><tr><td>a1</td><td>-0.12588 ±0.01884</td><td>-0.11371 ±0.02701</td></tr><tr><td>a2</td><td>5.7998 ±0.0280</td><td>5.7678 ± 0.0283</td></tr><tr><td>b1</td><td>-2.0572 ± 0.0804</td><td>-2.0276 ± 0.0822</td></tr><tr><td>b2</td><td>1.9461 ± 0.0134</td><td>1.9384 ± 0.0132</td></tr></table></body></html>

# 5.4.2 Effect due to energy drift

The simulation for Compton edge is performed for two cases: 1) for the fix energy, the sampling of the edge is according to distribution formulated in Eq.(24); 2) for the variant energy, the sampling of the edge is also according to distribution formulated in Eq. (24) but with variant （20 $\omega$ , that is the fix value of $\omega$ is replaced by variate $\omega ( x )$ ,i.e.

$$
\omega ( x ) = \omega \cdot f _ { \delta _ { E } } ( x ) \ ,
$$

where $f _ { \delta _ { E } } ( x )$ is the distribution in Eq. (33), and $x$ is a random number of between O and 1. The simulated distributions for two cases are shown in Fig. 6(b).

The fitted results based on the simulated distributions for two cases are given in Table. 4, and the fit curves for two cases is displayed in Fig.6(e) and (f). The difference for fitted beam energy is about 0.233 MeV, or 0.466 MeV for C.M. energy.

# 6 Summary

In this monograph, the energy relation between Compton backscattering photon and high energy electron is derived analyticaly, based on which the formula for uncertainty estimation of measured energy is obtained. The leading contribution of uncertainty is figured out by utilizing the present experimental information.

By virtue of the experimentally available information, the special phenomenon between beam current and cross section is explored in detail by simulation approach. The quantitative results indicate that for C.M.energy, the maximum energy shift is up to 0.226 MeV due to variant energy spread and O.466 MeV due to variant energy drift. These effects of energy shift studied herein disclose so to speak a significantly possible source of systematic uncertainty for BEMS, which in turn has the far-reaching meaning for the further analysis of physics error.

# Acknowledgement

Author acknowledges Dr. JianYong Zhang for his providing information on the relation between beam current and cross section.

# Appendix A

The nature unity with $c = 1$ is adopted hereafter. The velocity of electron is denoted as $\beta ( = v / c )$ and its corresponding energy is often expressed as $\varepsilon = m \gamma$ with $\gamma = 1 / \sqrt { 1 - \beta ^ { 2 } }$ . According to Refs. [24, 25], the general relation between $\omega _ { 1 }$ and $\omega _ { 2 }$ for Compton scattering process is

$$
\omega _ { 2 } = \frac { \omega _ { 1 } \big ( 1 - \beta \cos \phi _ { 1 } \big ) } { 1 - \beta \cos \phi _ { 2 } + \frac { \omega _ { 1 } } { \gamma m } \big ( 1 - \cos [ \phi _ { 1 } - \phi _ { 2 } ] \big ) } \mathrm { ~ , ~ }
$$

where $\phi _ { 1 }$ is the angle between incident photon and electron while $\phi _ { 2 }$ the angle between backscattering photon and electron. For head-on collison, $\phi _ { 1 } = 1 8 0 ^ { \circ }$ and $\phi _ { 2 } = 0 ^ { \circ }$ ， so Eq.（A.1) becomes

$$
\omega _ { 2 } = \frac { \omega _ { 1 } ( 1 + \beta ) } { ( 1 - \beta ) + \displaystyle \frac { 2 \omega _ { 1 } } { \gamma m } } = \frac { \displaystyle \frac { 1 + \beta } { 1 - \beta } } { \displaystyle \frac { 1 } { \omega _ { 1 } } + \frac { 2 } { m \gamma ( 1 - \beta ) } } \ ,
$$

Note two relations

$$
\frac { 1 + \beta } { 1 - \beta } = \gamma ^ { 2 } ( 1 + \beta ) ^ { 2 } \ , \frac { 1 } { \gamma ( 1 - \beta ) } = \gamma ( 1 + \beta ) \ ,
$$

and also the relation $m ^ { 2 } \gamma ^ { 2 } = \varepsilon _ { 1 } ^ { 2 }$ , Eq.(A.2) can be rewritten as

$$
\omega _ { 2 } = \frac { \varepsilon _ { 1 } ^ { 2 } ( 1 + \beta ) ^ { 2 } } { 2 \varepsilon _ { 1 } ( 1 + \beta ) + \displaystyle \frac { m ^ { 2 } } { \omega _ { 1 } } } \ ,
$$

and this is just Eq. (5), from which it yields

$$
\varepsilon _ { 1 } = { \frac { \omega _ { 2 } } { 2 } } \left( 1 + \sqrt { 1 + { \frac { m ^ { 2 } } { \omega _ { 1 } \ \omega _ { 2 } } } } \right) + { \frac { m ^ { 2 } } { 2 \omega _ { 2 } \left( 1 + \sqrt { 1 + { \frac { m ^ { 2 } } { \omega _ { 1 } \ \omega _ { 2 } } } } \right) } } \ .
$$

Then the partial derivative with respect to $\omega _ { 1 }$ ， $\omega _ { 2 }$ ，and $m$ can be expressed by

$$
\begin{array} { r c l } { { \displaystyle \frac { \partial \varepsilon _ { 1 } } { \partial m } } } & { { = } } & { { \displaystyle \frac { \varepsilon _ { 1 } } { m } \cdot \left( 1 - \frac { 1 } { \kappa } \right) + \frac { m } { \omega _ { 2 } } \cdot \frac { 1 } { \kappa ( \kappa + 1 ) } \ , } } \\ { { \displaystyle \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 1 } } } } & { { = } } & { { \displaystyle - \frac { \varepsilon _ { 1 } } { 2 \omega _ { 1 } } \cdot \left( 1 - \frac { 1 } { \kappa } \right) + \frac { ( \kappa - 1 ) ^ { 2 } } { 2 \kappa } \ , } } \\ { { \displaystyle \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 2 } } } } & { { = } } & { { \displaystyle \frac { \varepsilon _ { 1 } } { 2 \omega _ { 2 } } \cdot \left( 1 + \frac { 1 } { \kappa } \right) - \frac { m ^ { 2 } } { \omega _ { 2 } ^ { 2 } } \cdot \frac { 1 } { 2 \kappa } \ , } } \end{array}
$$

with

$$
\kappa \equiv \sqrt { 1 + \frac { m ^ { 2 } } { \omega _ { 1 } \omega _ { 2 } } } \ .
$$

Based on the law of error propagation, the $\delta \varepsilon _ { 1 }$ is obtained as follows

$$
( \delta \varepsilon _ { 1 } ) ^ { 2 } = \left( \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 2 } } \cdot \delta \omega _ { 2 } \right) ^ { 2 } \oplus \left( \frac { \partial \varepsilon _ { 1 } } { \partial \omega _ { 1 } } \cdot \delta \omega _ { 1 } \right) ^ { 2 } \oplus \left( \frac { \partial \varepsilon _ { 1 } } { \partial m } \cdot \delta m \right) ^ { 2 } ~ .
$$

# Appendix B

In this appendix, $\sigma$ ， $\delta$ and $x$ represent respectively the relative cross section ( $R _ { \sigma }$ ), energy spread $( R _ { \Delta } )$ , and energy drift $( \delta E )$ . Firstly,

$$
\begin{array} { r c l } { { \sigma _ { 1 } } } & { { = } } & { { \displaystyle \frac { p _ { 2 } } { \delta _ { 1 } ^ { p _ { 3 } } } + p _ { 1 } ~ , } } \\ { { \sigma _ { 2 } } } & { { = } } & { { \displaystyle \frac { p _ { 2 } } { \delta _ { 2 } ^ { p _ { 3 } } } + p _ { 1 } ~ . } } \end{array}
$$

Some algebra yields

$$
\frac { 1 } { r } = \frac { p _ { 2 } + a _ { 1 } } { p _ { 2 } + k a _ { 1 } } \cdot k \ ,
$$

withdefinitions

$$
r = \frac { \sigma _ { 2 } } { \sigma _ { 1 } } \ , k = \frac { a _ { 2 } } { a _ { 1 } } \ , a _ { i } = p _ { 1 } \cdot \delta _ { i } ^ { p _ { 3 } } ( i = 1 , 2 ) .
$$

Then it is easy to acquire

$$
k = \frac { p _ { 2 } } { ( p _ { 2 } + a _ { 1 } ) r - a _ { 1 } } \ .
$$

With the above relation, if $\sigma _ { 1 }$ and $\delta _ { 1 }$ (equivalently $a _ { 1 }$ ） are chosen, $\delta _ { 2 }$ can be calculated from $\sigma _ { 2 }$ ： In our study, $\sigma _ { 1 }$ is chosen as the maximum cross section,which guarantees $k$ is always greater than 1. As to $\delta _ { 1 }$ , 0.8 MeV,1.0 MeV,and 1.2 MeV, are used to calculate the $\sigma _ { 2 }$ , the shape of curve are exactly the same. Without loss of generality and actuality, $\delta _ { 1 }$ is set to be 1.0 MeV.

Secondly, we consider the relation between $\sigma$ and $x$

$$
\begin{array} { r c l } { { \sigma _ { 1 } } } & { { = } } & { { p _ { 1 } \cdot e ^ { - p _ { 2 } \cdot x _ { 1 } ^ { 2 } } , } } \\ { { \sigma _ { 2 } } } & { { = } } & { { p _ { 1 } \cdot e ^ { - p _ { 2 } \cdot x _ { 2 } ^ { 2 } } . } } \end{array}
$$

Some algebra yields

$$
\frac { \kappa } { p _ { 2 } } = \eta ( \eta + 2 x _ { 1 } ) \ ,
$$

with definitions

$$
\kappa = \ln \frac { \sigma _ { 1 } } { \sigma _ { 2 } } \ , \eta = x _ { 2 } - x _ { 1 } \ .
$$

According to root formula for quadratic equation and notice $\eta > 0$ ，then

$$
x _ { 2 } = \sqrt { x _ { 1 } ^ { 2 } + \kappa / p _ { 2 } } \ .
$$

Let $x _ { 1 }$ correspond to $\sigma _ { 1 }$ and $\sigma _ { 1 }$ to the maximum cross section, that is $x _ { 1 } = 0$ and $\sigma _ { 1 } = \sigma _ { m a x }$ ， then we have

$$
x _ { 2 } = \sqrt { \frac { 1 } { p _ { 2 } } \cdot \ln \frac { \sigma _ { m a x } } { \sigma _ { 2 } } } \ .
$$

# References

[1] WANG J.Q. et al., Proceedings of IPAC'10, Kyoto, Japan, (2010): 2359 [2] Preliminary Design Report of Accelerator BEPC/, Sec- ond version, 2003 (in Chinese) Refer to http://acc- center.ihep.ac.cn/bepcii/bepcii.htm   
[3] ABLIKIM M et al.(BES Collaboration), Nucl. Instr. Meth. A 614(2010) : 345 [4] CHAO Kuang-Ta, WANG YI-FANG. Internation Journal of Modern Physics A (Suppl. Issue 1), 2009, 24: 1   
[5] FU Cheng-Dong,MO Xiao-Hu. Chinese Phyusics C, 2008,32: 776   
[6] MO Xiao-Hu. Nucl. Phys. B (Proc. Suppl.), 2007, 169: 132   
[7] WANG You-Kai, MO Xiao-Hu, YUAN Chang-Zheng et al. Nucl. Instrum. Methods A, 2007, 583: 479   
[8] Achasov M N et al.,Nucl. phys. B (Proc. Suppl.), 2009, 189: 366   
[9] MO Xiao-Hu et al. Chinese Physics C, 2010, 34: 912   
[10] ABAKUMOVA E V et al.,Nucl. Instr. Meth.A,2011, 659 : 21   
[11] Zhang J Y et al., Nuclear Physics B (Proc. Suppl.), 2012, 225-227: 309   
[12] MO Xiao-Hu et al. Chinese Physics C, 2008, 32: 995   
[13] Beringeer J. et al. (Particle Data Group), Phys.Rev. D,2012, 86 : 010001.   
[14] Patkl C K N. PHYSICAL REVIEW, 1964, 136 : 1187   
[15] Lee S Y. Accelerator Physics. Second edition. World Scientific Publishing Co. Pte. Ltd., 2004.   
[16] Klein R et al. Nucl. Instr.and Methods A,1997, 384: 293   
[17] Gradshteyn I S, Ryzhik I M. Table of Integrals, Series,and Products. Elsevier Inc., 2007   
[18] Kuraev E A and Fadin V S. Sov.J. Nucl. Phys. 1985, 41 : 466   
[19] G. Altarelli and G. Martinelli, CERN 86-02 (1986) 47; Nicrosini O and Trentadue L. Phys. Lett. B 1987, 196 : 551   
[20] Berends F A, Burgers G and Neerven W L. Nucl. Phys.B,1988, 297 : 429; Nucl. Phys.B, 1988, 304 : 921   
[21] CERNLIB - CERN Program Library Short Writeups (CERN Geneva, Switzerland,1996)   
[22] Brandt S. Data Analysis, Springer-Verlag New York Inc. 1998   
[23] Zhu YongSheng.Probability and Statistics in Experimental Physics. Second Edition. Scientific Publishing. 2006.   
[24] Rullhusen P,Artru X, Dhez P. Novel Radiation Sources Using Relativistic Electrons. World Scientific Publishing. 1998.   
[25] Landau L D, Lifshitz E M. Relativistic Quantum Mechanics. Pergamon. 1971