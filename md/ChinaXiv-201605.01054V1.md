# Holographic antiferromganetic quantum criticality and AdS $_ 2$ scaling limit

Rong-Gen Cai,1,\* Run-Qiu Yang,1,† and F.V. Kusmartsev $^ { 2 , \ddagger }$ （ $^ { 1 }$ State Key Laboratory of Theoretical Physics,Institute of Theoretical Physics, Chinese Academy ofSciences,Beijing 10019o，China. 2 Department of Physics， Loughborough University, Loughborough，Leicestershire，LE11 3TU，United Kingdom

A holographic description on antiferromagnetic quantum phase transition (QPT) induced by magnetic field and the criticality in the vicinity of quantum critical point (QCP) have been investigated numerically recently.In this paper,we show that the properties of QPT in this holographic model are governed bya CFT dual to the emergent AdS $^ 2$ in the IR region,which confirms that the dual boundary theory is a strong coupling theory with dynamic exponent $z = 2$ and logarithmic corrections appear.We also compare them with the results from Hertz model by solving RG equation at its upper critical dimension and with some experimental data from pyrochlores $\mathrm { E r } _ { 2 - 2 x } \mathrm { Y } _ { 2 x } \mathrm { ' I } \mathrm { i } _ { 2 } \mathrm { O } _ { 7 }$ （204号 and BiCoPO $^ { \mathrm { ~ b ~ } }$ ：

# I.INTRODUCTION

Quantum phase transitions (QPTs）happen at zero temperature.Such a phase transition and the critical behavior in the vicinity of the corresponding quantum critical points (QCPs) have attracted a great deal of interest both in theory and experiment sides recently [1-4]. In phase diagram,A QCP separates an ordered phase from a disordered phase at zero temperature.In contrast to classical phase transition at $T > 0$ where thermal fluctua tions play important role,QPTs are induced by quantum fluctuations associated with the Heisenberg uncertainty and driven by a control parameter in Hamiltonian rather than temperature.Usually, the control parameter could be composition,magnetic field,or pressure, etc.. In condensed matter physics,such a quantum criticality is considered to be an important mechanism for some of the most interesting phenomena,especially in itinerant electronic systems [5,6] and other phenomenons involving strongly correlated many-body systems [7, 8]. However, the complete theoretical descriptions valid at all the energy(or temperature) region are still lacking.

One of the most interesting and intensively discussed QPTs is the ordered-disordered QPT in antiferromagnetic materials induced by magnetic field,such as $\mathrm { C u _ { 2 } ( C _ { 5 } H _ { 1 } 2 N _ { 2 } ) _ { 2 } C l _ { 4 } }$ [9]，KCuCl3 [10],TlCuC] $^ 3$ [11], BiCoPO $^ { 5 }$ [12] and $\mathrm { E r _ { 2 - 2 } } _ { x } \mathrm { Y _ { 2 } } _ { x } \mathrm { T i _ { 2 } } ( ) _ { 7 }$ [13].A schematic phase diagram in the vicinity of a QPT as a function of magnetic field is shown in Fig $^ { 1 }$ ，where we plot the Néel temperature $T _ { N } ( B )$ when $B \ < \ B _ { c }$ and the spin gap $\Delta ( B )$ at zero temperature when $B > B _ { c }$ .In the antiferromagnetic (AF）phase (ordered phase),the uniform spontaneously staggered magnetization is accompanied by a long-ranged spin ordering，which persists up to a finite transition temperature $T _ { N }$ .When magnetic field increases,the transition temperature $T _ { N }$ is suppressed. When the magnetic field arrives at its critical value, $\boldsymbol { B } \ : = \ : \boldsymbol { B } _ { c }$ ，the transition temperature is suppressed to zero. When $B > B _ { c }$ and $T = 0$ ,the quantum disordered (QD) phase has gapped magnetic excitations.

![](images/2af4be3650124a1c22121383968b0eb4ea53b8ccba73699c89eff32d111c6d2a.jpg)  
FIG.1. Schematic phase diagram for a QPT,showing the Néel temperature and spin gap as functions of magnetic field [14]. For a magnetic QPT,the characteristic energy scales in the QD (quantum disordered) and AF phases are, respectively,the spin gap $\Delta$ and Néel temperature $T _ { N }$ ，both vanish at the QCP.

Another interesting feature in QPTs involving strong coupling is so called “hyperscaling violation” when the effective dimension is larger than or equal to $d _ { c }$ ,the upper critical dimension of corresponding field theory. In general for the case of dimension less than $d _ { c }$ , in the vicinity of QCP, there are the hyperscaling relations for free energy density $F ( b , T )$ ，Néel temperature $T _ { N }$ ，correlation length $\xi$ and characteristic energy $\Delta$ with respect to the tuning parameter $b = B / B _ { c } - 1$ as follows,

$$
\begin{array} { l } { { F _ { c } ( b , T ) = \lambda ^ { - ( d + z ) } F _ { c } ( b \lambda ^ { 1 / \nu } , T \lambda ^ { z } ) , b  0 } } \\ { { T _ { N } \propto ( - b ) ^ { \psi } , b  0 ^ { - } , } } \\ { { \xi \propto b ^ { - \nu } , \Delta \propto b ^ { z \nu } b  0 ^ { + } , } } \end{array}
$$

where $d$ is the spatial dimension of the system, $z$ is called dynamic exponent, $\psi$ and $\nu$ are two positive critical exponents depending on model. $F _ { c } ( b , T )$ is the critical contribution to the free energy density defined by $F _ { c } ( b , T ) = F ( b , T ) - F _ { \mathrm { r e g } } ( b , T )$ and $\lambda$ is an arbitrary scale factor. The effective dimension of the system at QPT then is $d _ { \mathrm { e f f } } = d + z$ .The scaling relations (lc） are always valid. But the naive scaling relation (la) is valid only when the effective dimension is less than the upper critical dimension,i.e., $d _ { \mathrm { e f f } } < d _ { c }$ [6].In particular,when $d = z = 2$ ，the hyperscaling relations（la） and（1b）are no longer valid. In that case,the quantum critical theory is not in a weak-coupling region in general. So for this case，a description of a strongly coupled effective field theory is called for near the QPTs [6].

In order to study and characterize strongly coupled quantum critical systems,some new methods are needed. The gauge/gravity duality or AdS/CFT correspondence provides us with a promising approach [15-18]. This duality relates a weak coupling gravitational theory in a $( d + 1 )$ -dimensional asymptotically anti de-Sitter (AdS) space-time to a $d$ -dimensional strong coupling conformal field theory(CFT) in the AdS boundary. In recent years, this duality has been extensively applied into condensed matter systems.Some remarkable progresses have been made in this direction,including holographic superfluids (superconductors) [19,2O] (for a recent review,see [21]), (non-)Fermi liquids [22-24] and so on. The models in the AdS/CFT frame for ferromagnetism/paramagnetism and anti-ferromagnetism/paramagnetism phase transitions have also been proposed in [25,26]. Especially in Ref. [26],we found that the antiferroamgnetic transition temperature $T _ { N }$ is indeed suppressed by an external magnetic field and tends to zero when the magnetic field approaches to a critical value $B _ { c }$ .In this way we realized a holographic description of antiferromagnetic quantum phase transition induced by an external magnetic field.Since the model involves rank-2 fields,the problems about ghost and causal violation may appear, which have not been discussed.Very recently,a modified model based on the previous works has been proposed in Ref.[27],which is shown to be ghost free and causal violation is absent,but keeps all the significant results in the previous works qualitatively. For this modified model, a numerical investigation about antiferromagnetic quantum phase transition induced by an external magnetic field was first presented in Ref. [28].

In this paper,we will further elaborate on the magnetic induced QPT and study its critical behavior in some details.In section II, we will first review some basic properties of holographic antiferromagnetic model by combining the ideas in Refs. [26,27] and study the behavior of Néel temperature $T _ { N }$ with respect to the external magnetic field,which shows that there is a critical magnetic field where quantum criticality appears and can be fitted well by adding a logarithmic correction to the usual power law form.In section III,we will show there is an emergent AdS $^ 2$ scaling limit which governs the low frequency behaviors in the vicinity of QCP.By this emergent AdS $^ 2$ geometry, we confirm the numerical results in section II and Ref. [28]. In section IV, we give a dual field computation from perturbation RG equation inspired by holographic results,which gives a confirmation about our holographic results.We will also discuss what our model can tell us about some real materials in this section.

# II. ANTIFERROMAGNETICMODELANDCRITICALTEMPERATURE

Antiferromagnetic phase in materials is a magnetic ordered phase without net magnetization.For the simplest case,there are two different sub-lattices which have two spontaneous magnetic moments with the same magnitude but opposite direction.The order parameter then is the staggered magnetization,i.e.,the difference between two different magnetic moments in two sub-lattices.The same as in the ferromagnetic phase,the time reversal transformation is also broken spontaneously in the antiferromagnetic phase.

# A.Holographic antiferromagnetic model

In Ref. [25]，we introduced an antisymmetric tensor field coupling with U(1） strength field to describe the phase which has one uniform spontaneous magnetization. In order to describe a spontaneous magnetic ordered phase which has a staggered magnetization,we introduce two antisymmetric tenser fields. Following Ref.[26] and Ref.[27], the action we will consider here takes the form

$$
S = \frac { 1 } { 2 \kappa ^ { 2 } } \int d ^ { 4 } x \sqrt { - g } [ R + \frac { 6 } { L ^ { 2 } } - F ^ { \mu \nu } F _ { \mu \nu } + \lambda ^ { 2 } ( L _ { 1 } + L _ { 2 } + L _ { 1 2 } ) ] ,
$$

where

$$
\begin{array} { c } { { { \cal L } _ { 1 2 } = \displaystyle \frac { k } { 2 } M ^ { ( 1 ) \mu \nu } M _ { \mu \nu } ^ { ( 2 ) } , } } \\ { { { \cal L } _ { ( a ) } = \displaystyle \frac { 1 } { 1 2 } ( d M ^ { ( a ) } ) ^ { \mu \nu \tau } ( d M ^ { ( a ) } ) _ { \mu \nu \tau } + \displaystyle \frac { m ^ { 2 } } { 4 } M ^ { ( a ) \mu \nu } M _ { \mu \nu } ^ { ( a ) } } } \\ { { + \displaystyle \frac { 1 } { 2 } M ^ { ( a ) \mu \nu } F _ { \mu \nu } + J V ( M _ { \mu \nu } ^ { ( a ) } ) , } } \\ { { { \cal V } ( M _ { \mu \nu } ^ { ( a ) } ) = ( { } ^ { * } M ^ { ( a ) } { } _ { \mu \nu } M ^ { ( a ) \mu \nu } ) ^ { 2 } , a = 1 , 2 . } } \end{array}
$$

$L$ is the radius of AdS space, $2 \kappa ^ { 2 } = 1 6 \pi G$ with $G$ the Newton constant.\* is the Hodge star dual operator. In this model, $k$ ， $m ^ { 2 }$ and $J$ are all model parameters with $J ~ < ~ 0$ ， $\lambda ^ { 2 }$ characterizes the back reaction of the two polarization fields $M _ { \mu \nu } ^ { ( a ) }$ with $a = 1 , 2$ to the background geometry,and $L _ { 1 2 }$ describes the interaction between two polarization fields. The equations of motion for polarization fields read

$$
3 \nabla ^ { \tau } \nabla _ { [ \tau } M _ { \mu \nu ] } ^ { ( a ) } - m ^ { 2 } M _ { \mu \nu } ^ { ( a ) } - k M _ { \mu \nu } ^ { ( b ) } - J V ^ { \prime } ( a ) _ { \mu \nu } - F _ { \mu \nu } = 0 .
$$

Here $\begin{array} { r l r } { ( a , b ) } & { { } = } & { ( 1 , 2 ) } \end{array}$ or $( 2 , 1 )$ and $\begin{array} { r l } { V ^ { \prime } ( a ) _ { \mu \nu } } & { { } = } \end{array}$ $( ^ { * } M ^ { ( a ) } \tau \sigma M ^ { ( a ) \tau \sigma } ) ^ { * } M ^ { ( a ) } \mu \nu$ .In the probe limit of $\lambda  0$ ， we can neglect the back reaction of the two polarization fields on the background geometry. The background we will consider is a dyonic Reissner-Nordstrom-AdS black brane solution of the Einstein-Maxwell theory with a negative cosmological constant,and the metric reads [29]

$$
\begin{array} { r } { d s ^ { 2 } = r ^ { 2 } ( - f ( r ) d t ^ { 2 } + d x ^ { 2 } + d y ^ { 2 } ) + \displaystyle \frac { d r ^ { 2 } } { r ^ { 2 } f ( r ) } , } \\ { f ( r ) = 1 - \displaystyle \frac { 1 + \mu ^ { 2 } + B ^ { 2 } } { r ^ { 3 } } + \displaystyle \frac { \mu ^ { 2 } + B ^ { 2 } } { r ^ { 4 } } . } \end{array}
$$

Here both the black brane horizon and AdS radius have been set to be unity. The temperature of the black brane is

$$
T = \frac { 1 } { 4 \pi } ( 3 - { \mu } ^ { 2 } - B ^ { 2 } ) .
$$

For the solution (5), the corresponding gauge potential is $A _ { \mu } = \mu ( 1 - 1 / r ) d t + B x d y$ .Here $\mu$ is the chemical potential and $B$ can be viewed as the external magnetic field in the dual boundary field theory. The zero temperature limit then corresponds to $B ^ { 2 } + \mu ^ { 2 } = 3 \qquad $ ：

In order to describe antiferromagnetic phase transition, following Ref.[26], we consider $M _ { t r } ^ { ( a ) } , M _ { x y } ^ { ( a ) }$ （ $a = 1 , 2$ )and define

$$
\begin{array} { r l r } & { } & { \alpha = \displaystyle \frac { 1 } { 2 } ( M _ { x y } ^ { ( 1 ) } + M _ { x y } ^ { ( 2 ) } ) , ~ \beta = \displaystyle \frac { 1 } { 2 } ( M _ { x y } ^ { ( 1 ) } - M _ { x y } ^ { ( 2 ) } ) , } \\ & { } & { p _ { 1 } = \displaystyle \frac { 1 } { 2 } ( M _ { t r } ^ { ( 1 ) } + M _ { t r } ^ { ( 2 ) } ) , ~ p _ { 2 } = \displaystyle \frac { 1 } { 2 } ( M _ { t r } ^ { ( 1 ) } - M _ { t r } ^ { ( 2 ) } ) . } \end{array}
$$

Then different values of $\alpha$ and $\beta$ correspond to different magnetic phases. The staggered magnetization $N ^ { \dagger }$ and total magnetization $N$ can be defined as,

$$
\begin{array} { l } { { N ^ { \dagger } / \lambda ^ { 2 } = - \displaystyle \int _ { 1 } ^ { \infty } \frac { \beta } { r ^ { 2 } } d r , } } \\ { { N / \lambda ^ { 2 } = - \displaystyle \int _ { 1 } ^ { \infty } \frac { \alpha } { r ^ { 2 } } d r . } } \end{array}
$$

When external magnetic field $B = 0$ , the antiferromagnetic phase corresponds to the phase with nonzero staggered magnetization but zero total magnetization density.

Put the expressions (7) into equations (4),we have the equations for $\alpha$ and $\beta$ as

$$
\begin{array} { r l r } & { } & { \alpha ^ { \prime \prime } + \frac { f ^ { \prime } \alpha ^ { \prime } } { f } - \left[ \frac { 4 J ( p _ { 1 } ^ { 2 } + p _ { 2 } ^ { 2 } ) } { r ^ { 2 } f } + \frac { m ^ { 2 } + k } { r ^ { 2 } f } \right] \alpha } \\ & { } & { + \frac { 8 J { p _ { 1 } } p _ { 2 } \beta } { r ^ { 2 } f } + \frac { B } { r ^ { 2 } f } = 0 , } \\ & { } & { \beta ^ { \prime \prime } + \frac { f ^ { \prime } \beta ^ { \prime } } { f } - \left[ \frac { 4 J ( p _ { 1 } ^ { 2 } + p _ { 2 } ^ { 2 } ) } { r ^ { 2 } f } + \frac { m ^ { 2 } - k } { r ^ { 2 } f } \right] \beta } \\ & { } & { + \frac { 8 J p _ { 1 } p _ { 2 } \alpha } { r ^ { 2 } f } = 0 } \end{array}
$$

with

$$
\begin{array} { l } { p _ { 1 } = \displaystyle \frac { r ^ { 2 } [ ( m ^ { 2 } - k ) r ^ { 4 } - 4 J ( \alpha ^ { 2 } + \beta ^ { 2 } ) ] \mu } { 1 6 J ^ { 2 } ( \alpha ^ { 2 } - \beta ^ { 2 } ) ^ { 2 } - 8 J ( \alpha ^ { 2 } + \beta ^ { 2 } ) m ^ { 2 } r ^ { 4 } + ( m ^ { 4 } - k ^ { 2 } ) r ^ { 8 } } , } \\ { p _ { 2 } = \displaystyle \frac { 8 J \mu \alpha \beta r ^ { 2 } } { 1 6 J ^ { 2 } ( \alpha ^ { 2 } - \beta ^ { 2 } ) ^ { 2 } - 8 J ( \alpha ^ { 2 } + \beta ^ { 2 } ) m ^ { 2 } r ^ { 4 } + ( m ^ { 4 } - k ^ { 2 } ) r ^ { 8 } } , } \end{array}
$$

The behavior of the solutions of Eqs.(9) in the UV region (near the AdS boundary) depends on the value of $m ^ { 2 } + k$ .When $m ^ { 2 } + k = 0$ , the asymptotic solutions will have a logarithmic term,we will not consider this case in present paper.On the other hand,when $m ^ { 2 } + k \neq 0$ ，we have the solution:

$$
\begin{array} { l } { { \alpha _ { U V } = \alpha _ { + } ^ { U V } r ^ { ( 1 + \delta _ { 1 } ) / 2 } + \alpha _ { - } ^ { U V } r ^ { ( 1 - \delta _ { 1 } ) / 2 } - \frac { B } { m ^ { 2 } + k } , } } \\ { { \beta _ { U V } = \beta _ { + } ^ { U V } r ^ { ( 1 + \delta _ { 2 } ) / 2 } + \beta _ { - } ^ { U V } r ^ { ( 1 - \delta _ { 2 } ) / 2 } , } } \\ { { \delta _ { 1 } = \sqrt { 1 + 4 k + 4 m ^ { 2 } } , \delta _ { 2 } = \sqrt { 1 - 4 k + 4 m ^ { 2 } } , } } \end{array}
$$

where $\alpha _ { \pm } ^ { U V }$ and $\beta _ { \pm } ^ { U V }$ are all finite constants. We require that the condensation happens spontaneously when $B =$ $0$ ，by the inspirit of AdS/CFT,which gives boundary conditions such that

$$
\alpha _ { + } ^ { U V } = \beta _ { + } ^ { U V } = 0 .
$$

# B. Conditions for antiferromagnetic phase transition when B=0

In our model, there are three parameters $J , m ^ { 2 }$ and （20 $k$ . In order that the dual boundary theory can describe antiferromagnetic system,these parameters need satisfy some conditions.

First, from the asymptotic behaviors in Eqs.(11),we see that the BF-bound at the boundary requires that $m ^ { 2 }$ （204号 and $k$ satisfy $1 + 4 m ^ { 2 } > 4 | k |$ .On the other hand,because of $J < 0$ , in order to make $p _ { 1 }$ and $p _ { 2 }$ finite in the region $( r _ { h } , \infty )$ ，we need following conditions,

$$
m ^ { 2 } > | k | \Leftrightarrow \delta _ { 1 } > 1 , \mathrm { ~ a n d ~ } \delta _ { 2 } > 1 .
$$

If conditions (13) are broken,we can see that the components $p _ { 1 } , p _ { 2 }$ will diverge at somewhere,which leads that there is some point where the energy-momentum tensor associated with these tensor felds diverges. So in this case,the bulk geometry becomes unstable and the probe limit is broken.

We can explain the conditions (12) and conditions (13) in other way. By the definitions (7),we see that the terms db $\alpha _ { \pm } ^ { U V } , \beta _ { \pm } ^ { U V }$ $B$ r $M _ { x y } ^ { ( 1 ) }$ $M _ { x y } ^ { ( 1 ) }$ is dominated by external magnetic field when $B \neq 0$ ， so the magnetic term should be the leading term near the boundary. This can be reached only when both the boundary conditions (12） and conditions (13) are satisfied.

Second,as pointed out in Ref.[26], in order to get an antiferromagnetic phase transition below a critical temperature when $B = 0$ ,we should achieve that $\beta$ can condense spontaneously, but $\alpha$ cannot，or in other words, the system is stable for $\alpha$ but not for $\beta$ .In RN-AdS black brane background, this can be achieved if the $\mathrm { A d S _ { 2 } }$ BF-bound is satisfied for $\alpha$ but violated for $\beta$ near the horizon when $T = 0$ .As in the critical cases for instability, we can treat $\alpha$ and $\beta$ both infinitesimal, so we get a linearized equations for them,

$$
\begin{array} { c } { { \alpha ^ { \prime \prime } + \displaystyle \frac { f ^ { \prime } \alpha ^ { \prime } } { f } - \left[ \frac { 4 J p _ { 1 } ^ { 2 } } { r ^ { 2 } f } + \frac { m ^ { 2 } + k } { r ^ { 2 } f } \right] \alpha = 0 , } } \\ { { \beta ^ { \prime \prime } + \displaystyle \frac { f ^ { \prime } \beta ^ { \prime } } { f } - \left[ \frac { 4 J p _ { 1 } ^ { 2 } } { r ^ { 2 } f } + \frac { m ^ { 2 } - k } { r ^ { 2 } f } \right] \beta = 0 } } \end{array}
$$

with $p _ { 1 } = \mu / [ ( m ^ { 2 } + k ) r ^ { 2 } ]$ . Then zero temperature corresponds to $\mu = \sqrt { 3 }$ .Let $r _ { * } = 1 / ( r - 1 )$ ,when $r _ { * } \to \infty$ ，we have following asymptotic solutions for $\alpha$ and $\beta$ ，

$$
\begin{array} { r l } & { \alpha _ { I R } = \alpha _ { + } ^ { I R } r _ { * } ^ { - ( 1 + \delta _ { 1 } ^ { * } ) / 2 } + \alpha _ { - } ^ { I R } r _ { * } ^ { - ( 1 - \delta _ { 1 } ^ { * } ) / 2 } , } \\ & { \beta _ { I R } = \beta _ { + } ^ { I R } r _ { * } ^ { - ( 1 + \delta _ { 2 } ^ { * } ) / 2 } + \beta _ { - } ^ { I R } r _ { * } ^ { - ( 1 - \delta _ { 2 } ^ { * } ) / 2 } , } \\ & { \delta _ { 1 } ^ { * } = \sqrt { 1 + 2 ( k + m ^ { 2 } + 4 J p _ { 1 0 } ^ { 2 } ) / 3 } , } \\ & { \delta _ { 2 } ^ { * } = \sqrt { 1 + 2 ( m ^ { 2 } - k + 4 J p _ { 1 0 } ^ { 2 } ) / 3 } . } \end{array}
$$

Here $p _ { 1 0 } ~ = ~ \sqrt { 3 } / ( m ^ { 2 } + k )$ ， $\alpha _ { \pm } ^ { I R }$ and $\beta _ { \pm } ^ { I R }$ are all finite constants. As a result，to have the antiferromagnetic instability requires that the parameters satisfy following conditions,

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { 1 + 2 ( k + m ^ { 2 } + 4 J p _ { 1 0 } ^ { 2 } ) / 3 > 0 , } \\ { 1 + 2 ( m ^ { 2 } - k + 4 J p _ { 1 0 } ^ { 2 } ) / 3 < 0 . } \end{array} \right. , } \end{array}
$$

which gives following constraint,

$$
J _ { c } ^ { + } ( k , m ^ { 2 } ) < J < J _ { c } ^ { - } ( k , m ^ { 2 } ) , \mathrm { ~ a n d ~ } k > 0 .
$$

with $J _ { c } ^ { \pm } ( k , m ^ { 2 } ) = - ( m ^ { 2 } + k ) ^ { 2 } ( m ^ { 2 } + 3 / 2 \pm k ) / 1 2$ （204号

When external magnetic field $B = 0$ ， for given mass square $m ^ { 2 }$ , the zero temperature phase of the dual boundary then depends on the parameters $J$ and $k$ . A typical example for $m ^ { 2 } = 1$ is plotted in Fig. 2. The red region corresponds to the case that parameters satisfy the conditions (13)and (17),which is what we will consider in this paper.

# C. Néel temperature and quantum criticality

When the magnetic field is absent,i.e., $B = 0$ ，under the conidtions (12)，(13) and (17),the solution of $\alpha$ is always zero，which means there does not exist spontaneous magnetization.But there is a critical temperature $T _ {  { \mathit { N } } 0 }$ ，lower than which a nonvanishing $\beta$ begins to appear,which shows the system transits into antiferromagnetic phase and gives a nonzero spontaneous staggered magnetization.

![](images/c2f4e6de4462693cadd63bd9d1deb551ea98f8da71da3938553ab6514fdcb106.jpg)  
FIG.2. Zero temperature phase diagram when $B = 0$ and （204号 ${ m ^ { 2 } = 1 }$ . Here FM,AFM,PM and Ferri stand for ferromagnetic phase,antiferromagnetic phase,paramagnetic phase and ferrimagnetic phase,respectively.

On the other hand,if turn on an external magnetic field $B$ ，we have $\alpha \neq 0$ .When the external magnetic field is small, the value of $| \alpha |$ will increase with the increasing of $B$ . Since the equation for $\beta$ couples with $\alpha$ the staggered magnetization is also influenced by magnetic field.This influence can be seen clearly from the effective mass square of $\beta$ in the IR region,namely, the near horizon region.Near the horizon,we have,

$$
m _ { \beta \mathrm { e f f } } ^ { 2 } | _ { r _ { h } } = \frac { 4 J \mu ^ { 2 } } { ( k + m ^ { 2 } ) ^ { 2 } } + m ^ { 2 } - k + \frac { 6 4 J ^ { 2 } \mu ^ { 2 } \alpha ^ { 2 } } { ( k + m ^ { 2 } ) ^ { 2 } ( m ^ { 2 } - k ) } .
$$

Under the restriction (13), we can see that, for smal magnetic field, the effective mass square of $\beta$ in the IR region will be increased by magnetic field $B$ ，which leads the nonzero solution of $\beta$ to appear in lower and lower temperature with increasing the magnetic field. Thus the antiferromagnetic critical temperature $T _ { N }$ will be suppressed by external magnetic field.

When the external magnetic is not very small, because of the nonlinear coupling between $\beta$ and $\alpha$ , it is not easy to directly give the relation between effective mass square of $\beta$ and the external magnetic field. Instead, the behavior of $T _ { N }$ with respect to magnetic field can be found numerically. Near the critical temperature, the staggered magnetization is very small, i.e., $\beta$ is a small quantity. In that case we can neglect the nonlinear terms of $\beta$ in the equations (9),which leads to

$$
\begin{array} { l } { { \alpha ^ { \prime \prime } + \displaystyle \frac { f ^ { \prime } \alpha ^ { \prime } } { f } - \displaystyle \frac { m _ { \alpha \mathrm { e f f } } ^ { 2 } } { r ^ { 2 } f } \alpha = \displaystyle \frac { B } { r ^ { 2 } f } , \hfill } } \\ { { \beta ^ { \prime \prime } + \displaystyle \frac { f ^ { \prime } \beta ^ { \prime } } { f } - \displaystyle \frac { m _ { \beta \mathrm { e f f } } ^ { 2 } } { r ^ { 2 } f } \beta = 0 , \hfill } } \end{array}
$$

with

$$
\begin{array} { l } { m _ { \alpha \mathrm { e f f } } ^ { 2 } = 4 J p _ { 1 } ^ { 2 } + m ^ { 2 } + k , } \\ { m _ { \beta \mathrm { e f f } } ^ { 2 } = m ^ { 2 } - k + 4 J p _ { 1 } ^ { 2 } + 8 J p _ { 1 } \tilde { p } _ { 2 } \alpha ^ { 2 } , } \\ { p _ { 1 } = \frac { r ^ { 2 } \sqrt { 3 - B ^ { 2 } - 4 \pi T } } { ( m ^ { 2 } + k ) r ^ { 4 } - 4 J \alpha ^ { 2 } } , } \\ { \widetilde { p } _ { 2 } = \frac { 8 J r ^ { 2 } \sqrt { 3 - B ^ { 2 } - 4 \pi T } } { ( 4 J \alpha ^ { 2 } - m ^ { 2 } r ^ { 4 } ) ^ { 2 } - k ^ { 2 } r ^ { 8 } } . } \end{array}
$$

When $T \neq 0$ ，in the IR region, the regularity of the solution gives following initial conditions

$$
\left\{ \begin{array} { l l } { \displaystyle \alpha ^ { \prime } = \frac { \alpha m _ { \alpha \mathrm { e f f } } ^ { 2 } + B } { 4 \pi T } , } \\ { \displaystyle \beta ^ { \prime } = \frac { \beta m _ { \beta \mathrm { e f f } } ^ { 2 } } { 4 \pi T } , } \end{array} \right.
$$

at the horizon. Without loss of the generality,we can set $\beta ( r _ { h } ) = 1$ due to the linearity of the equation of $\beta$

When $T _ { N } = 0$ , the initial conditions (21) imply that

$$
B = - \alpha m _ { \alpha \mathrm { e f f } } ^ { 2 } | _ { r _ { h } } , \mathrm { a n d } \ m _ { \beta \mathrm { e f f } } ^ { 2 } | _ { r _ { h } } = 0 ,
$$

at the horizon.For given parameters $J , m ^ { 2 }$ and $k$ ，these two equations give the solution $\alpha ( r _ { h } ) = \alpha _ { c }$ and $\boldsymbol { B } = B _ { c }$ Here $\alpha _ { c }$ is the initial value of $\alpha$ at the IR fixed point and （204号 $B _ { c }$ is the critical magnetic feld where the QPT occurs.

In Fig.3,we plot the Néel temperature $T _ { N }$ in the case of $B \ < \ B _ { c }$ .Because different parameters satisfying restrictions（13) and（17） give qualitatively same results,we here just show a typical example by taking $m ^ { 2 } = 1 , k = 7 / 8$ and $J = - 2 / 3$ .With the increasing the magnetic field from zero to $B _ { c }$ ,the Néel temperature decreases from $T _ { N 0 }$ to zero. For small $B$ ，numerical re sults show that $T _ { N } - T _ { N 0 } \propto B ^ { 2 }$ .When magnetic field approaches to $B _ { c }$ ，we find that the Néel temperature is fitted well by following relation

$$
\widetilde { T } _ { N } / \ln \widetilde { T } _ { N } \simeq - 0 . 4 0 7 4 ( 1 - B / B _ { c } ) .
$$

Here $\tilde { T } _ { N } = T _ { N } / T _ { N 0 }$ and $T _ { N 0 }$ is the Néel temperature in the case of $B = 0$ ：

The numerical results shown in Fig.3 and the relation (23） show that there is indeed a critical magnetic field $B _ { c }$ ，at which the critical temperature for staggered magnetization,i.e. $\beta$ ,is zero.So a quantum phase transition occurs，which separates antiferromagnetic phase and a quantum disordered phase at zero temperature. We can also obtain other critical properties in the vicinity of QCP by numerical methods [28]. Especially, in the vicinity of QCP, this model gives a dispersion relation for quasi-particle such as $\omega \sim q ^ { 2 }$ with energy $\omega$ and moment $q$ ，which shows that the boundary critical theory is a strong coupling theory with dynamic exponent $z = 2$ [6]. This agrees with the results from condensed matter theory about antiferromagnetic metal [6] and from the holographic model proposed by Ref. [30].

![](images/a18429ec88d00e6266260b474c1c1c8330696619a9d30046901b107898589383.jpg)  
FIG.3.The antiferromagnetic critical temperature $T _ { N }$ versus the magnetic field $B$ .(a)In the whole region of $0 \leq B \leq B c$ (b)In the region of $B \ll B _ { c }$ .(c)In the region of $1 - B / B _ { c } $ （20 $0 ^ { + }$ ：

The behavior of the Néel temperature in the vicinity of QCP is quite non-trivial and needs to be further understood. The relation (23) is not the usual power-law behavior in (1b) or square-root form. However, it agrees with the predication in the 2-D QPTs in strong coupling case [2, 6, 31]. The $d = z = 2$ quantum critical theory is in general not in a weak coupling region for any $T > 0$ and a strongly coupled effective classical model emerges that can be used to determine the critical dynamics [32]. As pointed out in Ref. [28]，it is just the reason that the AdS/CFT correspondence is very suitable for this description.In addition,the original numerical results in Ref. [28] need to be confirmed,especial for the logarithmic correction scaling rule Eq. (23).And we also need some more careful investigation to provide insight into physical properties in the vicinity of QCP in this holographic model. The most important is to clarify the relationship between this holographic model and the traditional theoriesof QPT and to knowwhat wecanlearn about real materials in experiment from our holographic results. These are our goals in the following sections.

# III. EMERGENTIRGEOMETRYANDTHE BEHAVIORSNEARQCP

In order to understand the scaling relation (23) and other numerical results presented in Ref. [28],we now pay attention to the background geometry in the zero temperature case. As the similar situation in Ref. [33], we will see that our numerical results about the behaviors in the vicinity of QCP are just controlled by the IR geometry which is governed by an emergent AdS $^ 2$ geometry.

# A．IR fixed point and critical magnetic field

In the vicinity of QCP, the system is dominated by the features of IR region,where an AdS $^ 2$ geometry emerges. Following Ref. [33],we introduce a new length scale $\widetilde { r }$ 、

$$
\mu ^ { 2 } + B ^ { 2 } = 3 \widetilde { r } ^ { 4 }
$$

Then the temperature of the black brane background can be written as,

$$
T = \frac { 3 } { 4 \pi } ( 1 - \widetilde { r } ^ { 4 } )
$$

Using this new scale,we define a new radial coordinate $\xi$ and time $\tau$ as,

$$
r - \widetilde { r } = \frac { \lambda } { 6 \xi } , 1 - \widetilde { r } = \frac { \lambda } { 6 \xi _ { 0 } } , t = \lambda ^ { - 1 } \tau , \lambda  0 .
$$

Use the variable $\xi$ ,we can define an inner IR boundary at $\xi  \xi _ { 0 }$ and an outer IR boundary at $\xi \to 0 ^ { + }$ (see Fig. 4). The line element can be written as,

$$
d s ^ { 2 } = \frac { 1 } { 6 \xi ^ { 2 } } \left[ - ( 1 - \frac { \xi ^ { 2 } } { \xi _ { 0 } ^ { 2 } } ) d \tau ^ { 2 } + ( 1 - \frac { \xi ^ { 2 } } { \xi _ { 0 } ^ { 2 } } ) ^ { - 1 } d \xi ^ { 2 } \right] + ( d x ^ { 2 } + d y ^ { 2 } )
$$

Then the radial function $f ( r )$ is,

$$
f ( \xi ) = \frac { \lambda ^ { 2 } } { 6 \xi ^ { 2 } } \big ( 1 - \frac { \xi ^ { 2 } } { \xi _ { 0 } ^ { 2 } } \big ) .
$$

And the temperature with respect to $\tau$ is,

$$
\widetilde { T } = \lambda ^ { - 1 } T = \frac { 1 } { 2 \pi \xi _ { 0 } } .
$$

Here the case of zero temperature corresponds to an infinity $\xi _ { 0 }$ . Note that in the scaling limit (26), finite $\tau$ corresponds to the long time limit of the original time coordinate.Thus in the language of the boundary field theory, the solution (27) corresponds to the low frequency limit.

Since the radial coordinate can be considered as the resolution scale for the dual theory. The evolution of the geometry and the fields propagating therein along this radial direction represent the RG-flow of the dual field theory. Using the coordinate transformations (26)，we can rewrite the equations(9) in the limit of $\lambda  0$ as

$$
\begin{array} { l } { { \displaystyle { \frac { d \alpha ^ { 2 } } { d \xi ^ { 2 } } - \frac { 2 \xi } { \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } } \frac { d \alpha } { d \xi } - \frac { \xi _ { 0 } ^ { 2 } ( B + \alpha m _ { \alpha \mathrm { e f f } } ^ { 2 } ) } { 6 \xi ^ { 2 } ( \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } ) } = 0 , } } } \\  { \displaystyle { \frac { d \beta ^ { 2 } } { d \xi ^ { 2 } } - \frac { 2 \xi } { \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } } \frac { d \beta } { d \xi } - \frac { \xi _ { 0 } ^ { 2 } m _ { \beta \mathrm { e f f } } ^ { 2 } \beta } { 6 \xi ^ { 2 } ( \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } ) } = 0 . } } \end{array}
$$

In the zero temperature case,which corresponds to $\xi _ { 0 } $ $\infty$ ，Eqs.(30)become

$$
\begin{array} { l } { { \displaystyle { \frac { d \alpha ^ { 2 } } { d \xi ^ { 2 } } - \frac { B + m _ { \alpha \mathrm { e f f } } ^ { 2 } \alpha } { 6 \xi ^ { 2 } } = 0 , } } } \\ { { \displaystyle { \frac { d \beta ^ { 2 } } { d \xi ^ { 2 } } - \frac { m _ { \beta \mathrm { e f f } } ^ { 2 } } { 6 \xi ^ { 2 } } \beta = 0 . } } } \end{array}
$$

![](images/fd5aa67edeea9eec8f474912945b8460f2b0d81bf6ba5b31de371a0b6d356d8f.jpg)  
FIG.4.A schematic figure for the inner IR region and outer bulk region.The horizon is located at $\xi = \xi _ { 0 }$ . The near horizon region is $\xi _ { 0 } < \xi < 0$ ，where an AdS $^ 2$ geometry emerges. The bulk region is not covered by $\xi$ -coordinate.The solutions in the IR region and the bulk region should be matched at $\xi = 0$ ：

With the boundary conditions that $\alpha$ and $\beta$ are both finite at inner IR boundary and outer IR boundary or the existence of IR fixed points for $\alpha$ and $\beta$ in the IR region,these two equations have regular solutions only when $\alpha$ and $\beta$ are both constants.As a result,we have,

$$
B + m _ { \alpha \mathrm { e f f } } ^ { 2 } \alpha = 0 , m _ { \beta \mathrm { e f f } } ^ { 2 } = 0 .
$$

This is just what we have obtained in Eqs. (22). Note that in the case, $\alpha , \beta , p _ { 1 }$ and $\widetilde { p } _ { 2 }$ are all constants in IR region, so $\alpha m _ { \alpha \mathrm { e f f } } ^ { 2 }$ and $m _ { \beta \mathrm { e f f } } ^ { 2 }$ are also constants in IR region.With the restrictions that $m ^ { 2 } \geq | k |$ and $J$ satisfies Eqs.(17)，we can conclude that when $B < B _ { c }$ ，the solution with $\beta \neq 0$ exists.But when $B > B _ { c }$ ,there is only a trivial solution with $\beta = 0$ , by matching into bulk region, which will give a trivial solution such that $\beta ( r ) = 0$ in the whole bulk region.Thus there is a phase transition at $\boldsymbol { B } = B _ { c }$ at zero temperature,which divides an AFM phase from a quantum disordered phase.

# B. Linear perturbations and dynamic exponent

In order to compute the magnetic fluctuations in the vicinity of QCP.We need to turn on the perturbations of two polarization fields.Because of the non-linear term in equations (4),all the components couple with each other. As a result,we need consider the perturbations for all the components, i.e.,

$$
\begin{array} { l } { { \delta M _ { \mu \nu } ^ { ( a ) } = \epsilon C _ { \mu \nu } ^ { ( a ) } e ^ { - i \left( \omega t + q x \right) } , ( \mu , \nu ) \not = ( r , y ) , ( t , x ) } } \\ { { \delta M _ { \mu \nu } ^ { ( a ) } = i \epsilon C _ { \mu \nu } ^ { ( a ) } e ^ { - i \left( \omega t + q x \right) } , ( \mu , \nu ) = ( r , y ) , ( t , x ) . } } \end{array}
$$

Substituting the ansatz (33) into (4) and compute up to the linear order of $\epsilon$ ，we can get the equations for perturbations.When $\omega , q \neq 0$ ， however，we can't decouple all the equations. In general, therefore we needs to solve the $6 \times 2$ components together in order to determine the dispersion relation.But if we consider the behavior for small frequency and wave vector in the vicinity of QCP, i.e., $\omega  0$ and $q \to 0$ ,the problem can be simplified.In that case,theequations for $C _ { t x } ^ { ( a ) }$ and $C _ { r y } ^ { ( a ) }$ decouple from the others and can be neglected.Then we obtain $4 \times 2$ coupled equations,

$$
\begin{array} { r l } & { \qquad \left[ ( q ^ { 2 } + m ^ { 2 } ) v ^ { 2 } - 4 J M _ { x y } ^ { ( 3 ) } 2 \right] C _ { t v } ^ { ( 4 ) } + q ^ { 2 } C _ { v x } ^ { ( 4 ) } } \\ & { \qquad - 8 J M _ { x y } ^ { ( 3 ) } M _ { t v } ^ { ( 4 ) } C _ { t v } ^ { ( 2 ) } + k r ^ { 2 } C _ { v v } ^ { ( 6 ) } = 0 , } \\ & { \qquad \left( m ^ { 2 } - \frac { \omega ^ { 2 } } { \gamma ^ { 2 } f } \right) C _ { m x } ^ { ( 6 ) } + \frac { 4 J ( C _ { t v } ^ { ( 4 ) } ) \cdot M _ { t v } ^ { ( 4 ) } M _ { v } ^ { ( 4 ) } } { r ^ { 4 } f } + k \ell _ { x x } ^ { ( 6 ) } = 0 , } \\ & { \qquad C _ { t v } ^ { ( 4 ) ^ { \prime \prime } } - \frac { m ^ { 2 } C _ { t v } ^ { ( 6 ) } } { \gamma ^ { 2 } f } - \frac { k C _ { t v } ^ { ( 6 ) } } { r ^ { 2 } f } + \frac { 4 J C _ { v x } ^ { ( 4 ) } \cdot M _ { v x } ^ { ( 6 ) } M _ { t v } ^ { ( 4 ) } } { r ^ { 4 } f } = 0 , } \\ & { C _ { s y } ^ { ( 4 ) ^ { \prime \prime } } + \frac { J ^ { \prime } C _ { t v } ^ { ( 4 ) } } { f } + \left( \frac { \omega ^ { 2 } } { r ^ { 2 } f ^ { 2 } } - \frac { m ^ { 2 } + 4 J M _ { v } ^ { ( 4 ) } } { r ^ { 2 } f } \right) C _ { v y } ^ { ( 4 ) ^ { \prime } } } \\ & { \qquad - \frac { C ^ { ( 2 ) } \cdot J ^ { ( 4 ) } \cdot 2 } { r ^ { 4 } f ^ { 2 } } - \frac { k C _ { t v } ^ { ( 6 ) } } { r ^ { 2 } f } - \frac { 8 J C _ { t v } ^ { ( 4 ) } \cdot M _ { v } ^ { ( 4 ) } M _ { v } ^ { ( 4 ) } } { r ^ { 2 } f } = 0 . } \end{array}
$$

with $( a , b ) = ( 1 , 2 )$ or $( 2 , 1 )$ . In the paramagnetic phase, i.e., $M _ { x y } ^ { ( 1 ) } = M _ { x y } ^ { ( 2 ) }$ and $M _ { t r } ^ { ( 1 ) } = M _ { t r } ^ { ( 2 ) }$ ，the second and the third equations in (34) show that $C _ { t y } ^ { ( 1 ) } = C _ { t y } ^ { ( 2 ) }$ and $C _ { r x } ^ { ( 1 ) } = C _ { r x } ^ { ( 2 ) }$ Let $\widetilde { \beta } = ( C _ { x y } ^ { ( 1 ) } - C _ { x y } ^ { ( 2 ) } ) / 2$ , then we obtain,

$$
\widetilde { \beta } ^ { \prime \prime } + \frac { f ^ { \prime } \widetilde { \beta } ^ { \prime } } { f } + \left[ \frac { \omega ^ { 2 } - Q q ^ { 2 } f } { r ^ { 2 } f ^ { 2 } } - \frac { m _ { \beta \mathrm { e f f } } ^ { 2 } } { r ^ { 2 } f } \right] \widetilde { \beta } + \mathcal { O } ( q ^ { 4 } ) = 0 .
$$

with

$$
Q = \frac { 6 4 J ^ { 2 } \alpha ^ { 2 } p _ { 1 } ^ { 2 } } { [ ( m ^ { 2 } - k ^ { 2 } ) r ^ { 4 } - 4 J \alpha ^ { 2 } ] ^ { 2 } } > 0 .
$$

As $q$ is infinitesimal,we can neglect the high order term $\mathcal { O } ( q ^ { 4 } )$ . Note that no matter how small $\omega$ and $q$ are,we here can't neglect the $( \omega ^ { 2 } - Q q ^ { 2 } ) / ( r ^ { 2 } f ^ { 2 } )$ term，because it diverges when $f = 0$ ：

In order to analyze the antiferromagnetic dispersion relation near the QCP for small frequency $\omega$ and wave vector $q$ ，we can take the IR-UV matching method proposed in Ref. [33]. We first compute the retarded Green's function in the IR region.Use the metric (27) in the limit of $\xi _ { 0 } \to \infty$ and scale frequency as $\widetilde { \omega } = \lambda \omega$ ,we obtain,

$$
\frac { d ^ { 2 } \widetilde { \beta } } { d \xi ^ { 2 } } + ( \widetilde { \omega } ^ { 2 } - Q _ { 0 } q ^ { 2 } / 6 \xi ^ { 2 } ) \widetilde { \beta } = 0 ,
$$

where we have used the results (32). $Q _ { 0 }$ is the value of $Q$ in the IR region. Because $\alpha$ is a constant in IR region, $Q$ is also a constant in IR region.Solving this equation with the ingoing condition at $\xi  \infty$ ，we have,

$$
\widetilde { \beta } \propto \sqrt { \xi } H _ { \nu } ^ { ( 1 ) } ( \widetilde { \omega } \xi ) .
$$

Here $H _ { \nu } ^ { ( 1 ) } ( x )$ is the first Hankel function with order $\nu =$ $\sqrt { 9 + 6 Q _ { 0 } q ^ { 2 } } / 6$ . Using the properties of Hankel function

and the fact that $q \ll 1$ ,we can find that the asymptotic solution for $\beta$ in the outer IR region is,

$$
\widetilde { \beta } \propto \xi ^ { - Q _ { 0 } q ^ { 2 } / 2 } + \mathcal { G } ( \widetilde { \omega } ) \xi ^ { 1 + Q _ { 0 } q ^ { 2 } / 2 }
$$

with the IR retarded Green's function $\mathcal { G } ( \widetilde { \omega } ) \propto \widetilde { \omega } ^ { Q _ { 0 } q ^ { 2 } / 3 }$ Then using the method in Ref. [33],one can find that the retarded Green's function can be expanded in small $\omega$ as,

$$
\begin{array} { r l } & { G ( \omega ) \propto } \\ & { \frac { b _ { + } ^ { ( 0 ) } + \omega b _ { + } ^ { ( 1 ) } + O ( \omega ^ { 2 } ) + \mathcal { G } ( \omega ) ( b _ { - } ^ { ( 0 ) } + \omega b _ { - } ^ { ( 1 ) } + O ( \omega ^ { 2 } ) ) } { a _ { + } ^ { ( 0 ) } + \omega a _ { + } ^ { ( 1 ) } + O ( \omega ^ { 2 } ) + \mathcal { G } ( \omega ) ( a _ { - } ^ { ( 0 ) } + \omega a _ { - } ^ { ( 1 ) } + O ( \omega ^ { 2 } ) ) } } \end{array}
$$

with $b _ { \pm } ^ { ( i ) }$ and $a _ { \pm } ^ { ( i ) }$ are the analyticalfunctions of $q ^ { 2 }$ By neglecting the irrelevant parts in (4O), the retarded Green's function can be written as the following form for small $\omega$ and $q$ ，

$$
G ( \omega ) = \frac { Z } { - q ^ { 2 } + a _ { 1 } \omega + a _ { 2 } \omega Q _ { 0 } q ^ { 2 } / 3 }
$$

with some constant $Z$ .Considering the fact that when $q = 0$ , the retarded Green's function has a pole at $\omega = 0$ ， we have $a _ { 2 } = 0$ ．Then the dispersion relation is determined by the equation,

$$
- Q _ { 0 } q ^ { 2 } + a _ { 1 } \omega = 0 ,
$$

which tells us $\omega \sim q ^ { 2 }$ .Thus we obtain the dynamic exponent $z = 2$ ：

One should note that,in general, the coefficients appearing in (4O) have scaling dimensions,and so dose for $a _ { 1 }$ in (42).From the expression (42),we find that $a _ { 1 }$ has scaling dimension 1. Thus under the scaling transformation such that $r  \lambda r$ ， $( t , x , y ) \to \lambda ^ { - 1 } ( t , x , y )$ ，which induces the transformations such that $\omega  \lambda \omega , q  \lambda q$ and $a _ { 1 }  \lambda a _ { 1 }$ , the equation(42) is invariant.As a result, the dynamic exponent $z = 2$ is compatible with scaling symmetry.

# C. The scaling relation of $T _ { N }$ with $B$ near the QCP

Now let us find the the scaling relation of $T _ { N }$ with $B$ in the region of $B \to B _ { c } ^ { - }$ ．The method we will take is similar to the one as in the previous subsection.We first compute the Green's function at finite temperature in the IR region,and then match it with the bulk solution.

In the IR region,near the fixed point $B = B _ { c } + \delta B$ with $\delta B \to 0 ^ { - }$ ，we can neglect the non-linear term of $\beta$ and can get the equations for finite $\xi _ { 0 }$ ，

$$
\begin{array} { r } { \frac { d \alpha ^ { 2 } } { d \xi ^ { 2 } } - \frac { 2 \xi } { \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } } \frac { d \alpha } { d \xi } = \frac { \xi _ { 0 } ^ { 2 } [ B + m _ { \alpha \mathrm { e f f } } ^ { 2 } \alpha ] } { 6 \xi ^ { 2 } ( \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } ) } , } \\ { \frac { d \beta ^ { 2 } } { d \xi ^ { 2 } } - \frac { 2 \xi } { \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } } \frac { d \beta } { d \xi } = \frac { \xi _ { 0 } ^ { 2 } m _ { \beta \mathrm { e f f } } ^ { 2 } \beta } { 6 \xi ^ { 2 } ( \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } ) } . } \end{array}
$$

Under the boundary conditions that $\alpha$ and $\beta$ are both finite at $\xi = 0$ and $\xi _ { 0 }$ ，the solutions for Eqs.(43）are constants. Then we have solution such that,

$$
B _ { c } + \delta B + m _ { \alpha \mathrm { e f f } } ^ { 2 } \alpha = 0 , \quad \beta = 0 ,
$$

Using Eqs. (22)，up to the order of $\delta B$ ，we find that Eqs.(44) give solution $\alpha = \alpha _ { 0 } \equiv \alpha _ { c } + \delta \alpha$ with

$$
\delta \alpha = - \left. \frac { \delta B } { ( m _ { \alpha \mathrm { e f f } } ^ { 2 } + \partial m _ { \alpha \mathrm { e f f } } ^ { 2 } / \partial \alpha ) } \right| _ { \alpha = \alpha _ { c } } .
$$

In order to compute the retarded Green's function,we consider the deviations from the fixed point with $\beta =$ $0 + \beta _ { 1 }$ and $\alpha = \alpha _ { 0 } + \alpha _ { 1 }$ . Note that $\delta B \to 0 ^ { - }$ ，up to the linear order of $\beta _ { 1 }$ and $\alpha _ { 1 }$ ，we have the equations of the fluctuations

$$
\begin{array} { r } { \displaystyle \frac { d \alpha _ { 1 } ^ { 2 } } { d \xi ^ { 2 } } - \frac { 2 \xi } { \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } } \frac { d \alpha _ { 1 } } { d \xi } = \frac { \xi _ { 0 } ^ { 2 } ( m _ { \alpha \mathrm { e f f } } ^ { 2 } + \partial m _ { \alpha \mathrm { e f f } } ^ { 2 } / \partial \alpha ) \alpha _ { 1 } } { 6 \xi ^ { 2 } ( \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } ) } , } \\ { \displaystyle \frac { d \beta _ { 1 } ^ { 2 } } { d \xi ^ { 2 } } - \frac { 2 \xi } { \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } } \frac { d \beta _ { 1 } } { d \xi } = \frac { \partial m _ { \beta \mathrm { e f f } } ^ { 2 } } { \partial \alpha } \frac { \delta \alpha \beta _ { 1 } } { 6 \xi ^ { 2 } ( \xi _ { 0 } ^ { 2 } - \xi ^ { 2 } ) } . } \end{array}
$$

Here effective mass terms and their derivative are taken the value at $\alpha = \alpha _ { 0 }$ . The solutions for $\alpha _ { 1 }$ and $\beta _ { 1 }$ can be expressed as hypergeometric functions as,

$$
\begin{array} { l } { { \alpha _ { 1 } = \displaystyle \sum _ { \pm } ( \frac { \xi } { \xi _ { 0 } } ) ^ { \frac { 1 \pm \delta _ { \alpha } } { 2 } } C _ { \pm } ^ { ( \alpha ) } { _ 2 F _ { 1 } } [ \frac { 3 \pm \delta _ { \alpha } } { 4 } , \frac { 1 \pm \delta _ { \alpha } } { 4 } ; 1 \pm \frac { \delta _ { \alpha } } { 2 } ; \frac { \xi } { \xi _ { 0 } } ] , } } \\ { { \beta _ { 1 } = \displaystyle \sum _ { \pm } ( \frac { \xi } { \xi _ { 0 } } ) ^ { \frac { 1 \pm \delta _ { \beta } } { 2 } } C _ { \pm } ^ { ( \beta ) } { _ 2 F _ { 1 } } [ \frac { 3 \pm \delta _ { \beta } } { 4 } , \frac { 1 \pm \delta _ { \beta } } { 4 } ; 1 \pm \frac { \delta _ { \beta } } { 2 } ; \frac { \xi } { \xi _ { 0 } } ] } } \end{array}
$$

with $\begin{array} { l l l } { \delta _ { \alpha } } & { = } & { \sqrt { 1 + 2 ( { m _ { \alpha \mathrm { e f f } } ^ { 2 } + \partial { m _ { \alpha \mathrm { e f f } } ^ { 2 } } } / { \partial \alpha } ) / 3 } } \end{array}$ and $\begin{array} { r l } { \delta _ { \beta } } & { { } = } \end{array}$ $\sqrt { 1 + { \textstyle \frac { 2 } { 3 } } ( \partial m _ { \beta \mathrm { e f f } } ^ { 2 } / \partial \alpha ) \delta \alpha }$ . These hypergeometric functions have logarithmic divergency when $\xi / \xi _ { 0 } \to 1$ . So the coefficients $C _ { \pm } ^ { ( \alpha ) }$ and $C _ { \pm } ^ { ( \beta ) }$ should counteract these detergency. Then we can get the retarded Green's functions in the outer IR region near $\xi  0$ as,

$$
\begin{array} { r } { \mathcal { G } _ { \alpha \alpha } ( \widetilde { T } ) = ( 2 \pi \widetilde { T } ) ^ { \delta _ { \alpha } } \frac { \Gamma ( \frac { 3 } { 4 } + \frac { \delta _ { \alpha } } { 4 } ) \Gamma ( \frac { 1 } { 4 } + \frac { \delta _ { \alpha } } { 4 } ) \Gamma ( 1 - \frac { \delta _ { \alpha } } { 2 } ) } { \Gamma ( \frac { 3 } { 4 } - \frac { \delta _ { \alpha } } { 4 } ) \Gamma ( \frac { 1 } { 4 } - \frac { \delta _ { \alpha } } { 4 } ) \Gamma ( 1 + \frac { \delta _ { \alpha } } { 2 } ) } , } \\ { \mathcal { G } _ { \beta \beta } ( \widetilde { T } ) = ( 2 \pi \widetilde { T } ) ^ { \delta _ { \beta } } . } \end{array}
$$

Now we can use the IR-UV matching method to express the UV Green's functions. Similar to the expression (40), we can get the Green's functions for and $\beta _ { 1 }$ with some coefficiets $a _ { \pm } ^ { ( n ) }$ and $b _ { \pm } ^ { ( n ) }$ whichshould beanalyticalfunctions of $\delta B$ .Note that two retarded Green's functions have poles at $\delta B = T = 0$ ，we have,

$$
\begin{array} { r } { G _ { \alpha \alpha } = \frac { Z _ { 1 } } { \delta B + c _ { 1 } ^ { ( \alpha ) } T + \mathcal { G } _ { \alpha \alpha } ( T ) c _ { 2 } ^ { ( \alpha ) } } , } \\ { G _ { \beta \beta } = \frac { Z _ { 2 } } { \delta B + c _ { 1 } ^ { ( \beta ) } T + \mathcal { G } _ { \beta \beta } ( T ) c _ { 2 } ^ { ( \beta ) } } . } \end{array}
$$

Here $\mathcal { G } _ { \alpha \alpha }$ is irrelevant and can be neglected.One should note c( are also the functions of $c _ { 1 } ^ { ( \alpha ) }$ because the equation for $\beta$ in the bulk depends on $\alpha$ but the equation for $\alpha$ in the bulk is independent on $\beta$ .In the limit of $\delta B = 0$ 5 we will find $\delta _ { \beta } = 1$ ,so the $c _ { 1 } ^ { ( \beta ) }$ term and $c _ { 2 } ^ { ( \beta ) }$ term degenerate.In that case,as the similar as the case pointed out in Ref.[33],a logarithmic term appears. And the relevant terms in Green's functions read

$$
G _ { \alpha \alpha } = \frac { Z _ { 1 } } { \delta B + c _ { 1 } ^ { ( \alpha ) } T } , G _ { \beta \beta } = \frac { Z _ { 2 } } { \delta B + c _ { 3 } ^ { ( \beta ) } ( c _ { 1 } ^ { ( \alpha ) } ) T \ln T }
$$

with two constants $Z _ { 1 }$ and $Z _ { 2 }$ ．The poles for them are defined by,

$$
\delta B + c _ { 1 } ^ { ( \alpha ) } T = 0 , \delta B + c _ { 3 } ^ { ( \beta ) } ( c _ { 1 } ^ { ( \alpha ) } ) T \ln T = 0 .
$$

Now note the fact that $\delta B \to - \delta B , c _ { 1 } ^ { ( \alpha ) } \to - c _ { 1 } ^ { ( \alpha ) }$ will lead $\alpha  - \alpha$ ，which will not affect the solution of $\beta$ 5 $c _ { 3 } ^ { ( \beta ) }$ must be a function of $c _ { 1 } ^ { ( \alpha ) 2 }$ Then in the case of （204号 $T  0$ and $\delta B  0$ , there is a self-consistent ansatz such as c3 $c _ { 3 } ^ { ( \beta ) } = d _ { 1 } c _ { 1 } ^ { ( \alpha ) 2 } + { \cal O } ( c _ { 1 } ^ { ( \alpha ) 4 } )$ for small $c _ { 1 } ^ { ( \alpha ) 2 }$ and finite constant $d _ { 1 }$ .1 Then we can see that the relevant parts of the equations (51) can be expressed as,

$$
\delta B + c _ { 1 } ^ { ( \alpha ) } T = 0 , \delta B + c _ { 1 } ^ { ( \alpha ) 2 } d _ { 1 } T \ln T = 0 .
$$

Solving these equations,we find $\delta B \ \propto \ T / \ln T$ .Asa result we have $b \equiv \delta B / B _ { c } \propto T / \ln T$ and analytically show the relation (23).

# D. Energy gap and correlation length in the quantum disordered phase

In Ref. [28],numerical results show that there is a gapped antiferromagnetic excitation in the quantum disordered phase. The energy gap and correlation length still obey the power law form (lc) and (1b) with respect to the tuning parameter $b$ in the vicinity of QPT.These results can also be understood from the point of view of the emergent AdS $^ 2$ geometry.

In order to compute the energy gap of antiferromagnetic excitation,we should turn on a perturbation for $\beta$ with frequency $\omega$ .In the region of quantum disordered phase with $T = 0$ and $\delta B = B - B _ { c } \to 0 ^ { + }$ ，using the results in the previous section, the background and perturbation equations for polarization fields read,

$$
\begin{array} { r } { \alpha ^ { \prime \prime } + \displaystyle \frac { f ^ { \prime } \alpha ^ { \prime } } { f } - \displaystyle \frac { m _ { \alpha \mathrm { e f f } } ^ { 2 } } { r ^ { 2 } f } \alpha - \displaystyle \frac { B } { r ^ { 2 } f } = 0 , } \\ { \widetilde { \beta } ^ { \prime \prime } + \displaystyle \frac { f ^ { \prime } \widetilde { \beta } ^ { \prime } } { f } + \left[ \displaystyle \frac { \omega ^ { 2 } } { r ^ { 2 } f ^ { 2 } } - \displaystyle \frac { m _ { \beta \mathrm { e f f } } ^ { 2 } } { r ^ { 2 } f } \right] \widetilde { \beta } = 0 } \end{array}
$$

and $\beta = 0$ .The real frequency $\omega$ giving the pole for Green's function $G _ { \beta \beta } ( B )$ leads to the gapped quasiparticle excitation. To compute this Green's function,we take the similar method as in the previous subsections. In the IR region, considering the AdS $^ 2$ scaling limit at zero temperature,the equation (53) can be written as,

$$
\begin{array} { l } { { \displaystyle { \frac { d ^ { 2 } \alpha } { d \xi ^ { 2 } } - \frac { B _ { c } + \delta B + m _ { \alpha \mathrm { e f f } } ^ { 2 } \alpha } { 6 \xi ^ { 2 } } = 0 , } } } \\ { { \displaystyle { \frac { d ^ { 2 } \widetilde { \beta } } { d \xi ^ { 2 } } + \left( \widetilde { \omega } ^ { 2 } - \frac { m _ { \beta \mathrm { e f f } } ^ { 2 } } { 6 \xi ^ { 2 } } \right) \widetilde { \beta } = 0 . } } } \end{array}
$$

Up to the linear order of $\delta B$ , the equation(54a) gives the following regular solution with the IR fixed point,

$$
\alpha = \alpha _ { c } + \delta \alpha .
$$

Here $\delta \alpha$ is defined as (45). The equation for $\widetilde { \beta }$ can be written as

$$
{ \frac { d ^ { 2 } \widetilde \beta } { d \xi ^ { 2 } } } + \left[ \widetilde { \omega } ^ { 2 } - \left( { \frac { \partial m _ { \beta \mathrm { e f f } } ^ { 2 } } { \partial \alpha } } \right) _ { \alpha = \alpha _ { c } } { \frac { \delta \alpha } { 6 \xi ^ { 2 } } } \right] \widetilde \beta = 0 .
$$

Comparing it with the equation (37) in the subsection IIIB and note the relationship in (45),one can easily find that the Green's function for $\widetilde { \beta }$ has the following form,

$$
G _ { \beta \beta } ( \omega ) = \frac { Z _ { 3 } } { - \delta B + e _ { 1 } \omega }
$$

for small frequency $\omega$ and $\delta B \to 0 ^ { + }$ with two nonzero constants $e _ { 1 }$ and $Z _ { 3 }$ . Thus we obtain the relation between energy gap $\Delta$ and magnetic feld $B$ as

$$
\begin{array} { r } { \Delta \propto B - B _ { c } , } \end{array}
$$

As to correlation length,it can be computed in a similar way by setting $\omega = 0$ but turning on the perturbation for $\beta$ with nonzero moment $q$ . In that case,we still have equation(54a)but, the equation(54b) is changed to be

$$
\frac { d ^ { 2 } \widetilde { \beta } } { d \xi ^ { 2 } } - \frac { Q _ { 0 } q ^ { 2 } + m _ { \beta \mathrm { e f f } } ^ { 2 } } { 6 \xi ^ { 2 } } = 0 .
$$

For small $q$ and $\delta B$ , it gives the Green's function as,

$$
G _ { \beta \beta } ( \omega ) = \frac { Z _ { 4 } } { q ^ { 2 } + e _ { 2 } \delta B } = \frac { Z _ { 4 } } { q ^ { 2 } + 1 / \xi ^ { 2 } } ,
$$

where $Z _ { 4 }$ is another constant and $\xi$ is called correlation length. We then easily obtain

$$
\xi \propto ( B - B _ { c } ) ^ { - 1 / 2 } ,
$$

which is as the same as equation (1b) with $\nu = 1 / 2$

We see that results (61）and (59) obey the universal scaling relations(1b) for quantum criticality with $z = 2$ i.e., $\Delta \propto | B - B _ { c } | ^ { z \nu }$ . This can be viewed as the selfconsistency check for our model and computations.

# IV.CONCLUSIONS AND DISCUSSIONS

# A．Summarize the holographic model

We have investigated the quantum phase transition (QPT） from antiferromagnetic phase（AF） to quantum disordered phase(QD） and the criticality in the vicinity of quantum critical pointc(QCP) in the antiferroamgentic materials induced by magnetic field in a holographic model proposed in Ref. [26]. In the model, the Néel temperature $T _ { N }$ is suppressed by magnetic field $B$ .We proved that there is a critical magnetic field $B _ { c }$ ,at which $T _ { N } ~ = ~ 0$ and a QPT occurs.In order to analytically study the critical behavior in the vicinity of QCP,we employed the IR-UV matching methods in Ref. [33],and the results show that the analytical method confirms the numerical results obtained in Ref.[28]. In particular, we found that the dynamic exponent $z \ = \ 2$ ，which means that the boundary critical theory is indeed a strong coupling theory with effective dimension $d _ { \mathrm { e f f } } = d + z = 4$ .As a result, the hyperscaling law is violated and logarithmic corrections appear near the QCP.An interesting observation is that the critical behavior of the QCP is governed by the $A d S _ { 2 }$ geometry emerging in the IR region of the background geometry.

# B.Compare the results with RG-flow

In this subsection,we will review the results from field theory and compare them with the results from the holographic model. Our discussion follows Ref.[6], the details can be found there.A similar discussion as what we will do but mainly for the case of $d = z = 2$ can be found in Ref. [35].

In the original work by Hertz to quantum criticality [2], he considered the coupling between fermions and the lowenergy bosonic field which condenses at the QCP.By integrating the fast fermions,the effective field theory is the Landau-Ginsburg-Wilson (LGW) $\phi ^ { 4 }$ theory with the upper critical dimension $d _ { c } = 4 - z$ ,where $z$ is the dynamical exponent.Near the QCP,we can get the perturbative RG [34]. Let $u$ ， $T _ { N }$ ， $\lambda$ and $b$ are the coupling constant, condensed temperature for bosonic feld, scaling parameter and tuning parameter (in this paper,it's defined as $b = ( B - B _ { c } ) / B )$ ，respectively. Then the infinitesimal RG transformations are given by [34]

$$
\begin{array} { l } { \displaystyle \frac { d \mathcal { T } } { d \ln \lambda } = z \mathcal { T } , } \\ { \displaystyle \frac { d b } { d \ln \lambda } = 2 b + u f _ { 1 } ( T , b ) , } \\ { \displaystyle \frac { d u } { d \ln \lambda } = ( 4 - d - z ) u - u ^ { 2 } f _ { 2 } ( T , b ) . } \end{array}
$$

with some initial value $\mathcal { T } = T _ { N } , b = b _ { 0 } , u = u _ { 0 }$ .Here $f _ { 1 } ( \tau , b )$ and $f _ { 2 } ( \tau , b )$ are two functions of $\tau , b$ defined by the details of model. At low $T$ close to the critical point $b = 0$ ， $f _ { 1 } ( T , b )$ can be expressed as the power series of $T _ { N } ^ { 2 }$ and $f _ { 2 } ( \tau , b )$ is constant. Thus we can set $f _ { 1 } ( \mathcal { T } , b ) =$ $A _ { 0 } + A _ { 1 } T _ { N } ^ { 2 }$ and $f _ { 2 } ( \mathcal { T } , b ) = f _ { 2 }$ .The RG equations (62) have a Gaussian fixed point at $\mathcal { T } = u = b = 0$ ，which is unstable with respect to tuning parameter $b$ ， so a phase transition may occur at this point (see Fig. 5). Since the RG equations are obtained by perturbations,we assume that the initial values satisfy $T _ { N } , | b _ { 0 } | , | u _ { 0 } | \ll 1$ .One of remarkable features is that this RG equation hasa critical dimension at $d _ { c } = d + z = 4$ .So，in general，when $d > 4 - z$ ，we can find that the boundary of ordered phase $T _ { N }$ (such as the AF transition temperature,see Fig. 1),energy scale $\Delta$ in the quantum disordered phase and the correlation length $\it { l }$ in the vicinity of QCP obey the following scaling relations,

![](images/a5262e975fc43a84da1c72f3049be4f77101c561b0dc18e7db5009a124c28004.jpg)  
FIG.5.The schematic RG-flow diagram of $u$ $b$ for $d + z \ge 4$ There is a Gaussian fixed point at $u = b = 0$ ：

$$
T _ { N } \sim ( - b ) ^ { \psi } , ~ \Delta \sim b ^ { \nu z } , ~ l \sim b ^ { - \nu } .
$$

with $\psi = z / ( d + z - 2 )$ ， $\nu = 1 / 2$ .However,this simple power law will lose its efficacy in the case of $d = z = 2$ ， where the RG equations (62） need special consideration. In fact, logarithmic correction on $T _ { N }$ appears.In order to see this，we directly solve $\tau , u$ from the RG equation (62a),

$$
\mathcal { T } ( \lambda ) = T _ { N } \lambda ^ { z } , \mathrm { ~ } u ( \lambda ) = \frac { u _ { 0 } } { 1 + u _ { 0 } A _ { 2 } \ln \lambda } .
$$

Next,integrating the scaling Eq. (62b) for $b ( \lambda )$ and using Eqs. (62a) and (64)，we find

$$
b ( \lambda ) = \lambda ^ { 2 } \left[ b _ { 0 } + 2 e ^ { \frac { 2 } { u _ { 0 } f _ { 2 } } } E _ { 1 } ( 2 \ln \lambda + { \frac { 2 } { u _ { 0 } f _ { 2 } } } ) / ( u _ { 0 } f _ { 2 } ) \right] .
$$

Here $E _ { 1 } ( x )$ is exponential integral function.For large real $x$ ， $E _ { 1 } ( x ) \sim e ^ { - x } / x$ . In the quantum critical region, using the saling up to $\lambda \sim T _ { N } ^ { - 1 / 2 }$ ,where $\tau \sim 1$ ,we have,

$$
b ( \lambda ) = \frac { b _ { 0 } } { T _ { N } } + \frac { 1 } { f _ { 2 } u _ { 0 } \ln ( 1 / T _ { N } ) } + O ( \frac { 1 } { T \ln T } ) .
$$

Thus we see that the scaling relation depends on the value of $b ( \lambda )$ as $\lambda  \infty$ .However, the concrete form of $b ( \lambda )$ can not be found from the perturbational RG equations directly. Because the feature of strong coupling in the case of $z = d = 2$ , the perturbational methods can't give complete information of the system. We see that the perturbation method fails in this case to give a complete result.If $b ( \lambda )$ is a finite constant,then we can find a linear relation $b _ { 0 } \sim T _ { N }$ ，which is just the usual power law.If $b ( \lambda ) \ln \lambda \to 0$ as $\lambda = 1 / \sqrt { T _ { N } } \to \infty$ ，then we can get $b _ { 0 } \sim T _ { N } / \ln T _ { N }$ ．Comparing with the usual power law,there is an additional logarithmic correction,just as the same as what we have obtained in the holographic model.

We see that,with some additional assumption, the perturbational RG equations give the same results as the holographic model.In fact,in the case of $d = z = 2$ ， the low-energy Fermi liquid leads to long-range orderparameter interaction.As a result,the coefficients of the high-order interactions in the LGW functional diverge, leading to an infinite number marginal operators [31]. We see that the perturbational field method in this case fails to give out a complete description.However, the holographic setup can give self-consistent and complete predictions.

# C.Apply to real materials

Now let's turn our attention into real materials and see what we can learn from this holographic model about the real materials.Here we focus on Er2Ti2O $^ { 7 }$ ，as a kind of Magnetic pyrochlore oxides materials,which has amazing properties.At low temperatures there exists an antiferromagnetic order arising with a Néel temperature of 1.2 K.The compound is complex and there together with the nearest neighbor exchange，the Dzyaloshinskii-Moriya, dipolar and magnetoelastic interactions do exist and play an important role in the formation of the low temperature antiferromagnetic state.There is spins ordered on the vertex-sharing tetrahedra,in non-coplanar structure. There order is formed by quantum disorder,i.e.,in a very unconventional way [13]. To describe this material the XY-like theoretical model where local spins are coupled by near-neighbour antiferromagnetic exchange and long-range dipole interactions on the pyrochlore lattice has been proposed [36]. The key role in the model is played by the isotropic exchange between transverse components of near-neighbour spins and bond-dependent exchange anisotropy. The authors have shown that the interplay of these interactions dictates the formation of the ground state by the quantum disorder mechanism. The inclusion of the exchange anisotropy reproduces well the observed second-order magnetic phase transition in $\mathrm { E r _ { 2 } }$ Ti2O $^ { 7 }$ at zero field. However, in Ref. [37] it was argued that the dipolar interactions makes an important contribution into the formation of the second order phase transition observed [13]. Probably as argued in [36] the exchange anisotropy may overcome the dipolar interaction at zero magnetic field where the tetrahedral magnetic units have no net magnetic moment in the ground state.However with the field when the canted states are formed the dipolar-dipolar interaction，which certainly exists between large magnetic moments associated with free $\mathrm { E r ^ { 3 + } }$ ions ( $J = 1 5 / 2$ ， $g _ { J } = 6 / 5$ )，may become very important and can not be neglected.Therefore,the field evolution of the antiferromagnetic state and the role of the long-range part of the dipolar interactions in such an evolution remained unclear and beyond the scope of the discussed models. Here we proposed a holographic model which effectively absorbs all existing interactions inEr2Ti2O $^ { 7 }$ ina form of strongly interacting tensor fields embedded in AdS space of a higher dimension.The extra dimension play a role of the renormalization parameter, which separates relevant and irrelevant degrees of freedom in the system. The proposed holographic model describes well not only the zero temperature thermodynamic phase transition and spin wave excitation spectrumin Er2Ti2O $^ { 7 }$ but also their evolution in the applied magnetic field [28]. The model may uncover an intriguing picture of many possible coexisting phases,which can arise at such complexity of interactions existing in P $\pmb { \mathrm { r } _ { 2 } }$ Ti2O $^ 7$ [38].

In particular, in Ref. [38] it was found that with magnetic order there arise well defined spin wave excitations. With applied magnetic field their spectrum is softening (see the spin wave spectrum measured at the feld 1.5 T on the Fig.4 in Ref. [38]). At the studies of an array of magnetic particles where the dipolar interaction is usually relevant it was shown that its long range character may lead to a formation of a landscape of lowenergy states [39,4O]. With increasing field the spins form canted state and the energy landscape is flattering and there may arise continuous switching between these states.Therefore such evolution may lead to a quantum critical behavior and an appearance of quantum critical point QCP.Indeed the analysis of the low temperature phase diagram of Er2Ti2O $^ { 7 }$ made in Ref. [38] supports an existence of the rich variety of elementary excitations as the ground state is tuned by external magnetic field. The authors of Ref. [38] also suggested that most dramatic variations of the spectra with feld arising at 1.5 T may possibly correspond to the formation of a continuous QCP.Indeed in the framework of our holographic model similar picture emerges.The holographic model predicts that the magnetic order continuously changes with the field and the QCP arises at critical field $B _ { c } \simeq 1 . 4 5$ T. Our model provides not only qualitative but also quantitative description of the experimental data [12,13] of the Néel temperature lowering with magnetic field (see, Fig.6） and predict the QCP at 1.45T,which is very closed to the experimental results. There magnetic spins become partially aligned in the direction of the magnetic field. Therefore the system requires less thermal energy to destroy the remaining magnetic spins order. We found that similar behavior exist in other pyrochlore compounds which may be obtained from Er2Ti2O $^ { 7 }$ by $\mathrm { Y ^ { 3 + } }$ doping. Both doping and the increasing of magnetic field decrease the Néel temperature of the $\mathrm { Y ^ { 3 + } }$ -doped and undoped Er2Ti2O $^ { 7 }$ very similar until the QCP arises (see,Fig.6).We see from this figure that the critical temperature versus critical field curve is independent of the diamagnetic doping at the magnetic site. This fact that the influence of dilution in $( \mathrm { E r } _ { 1 - x } \mathrm { Y } _ { x } ) _ { 2 } \mathrm { T i } _ { 2 } \mathrm { O } _ { 7 }$ solid solutions is similar to the increase of magnetic field for pure （20 $\mathrm { E r } _ { 2 }$ Ti2O $^ { 7 }$ one more time stresses the importance and universality of complex magnetic interactions in these systems which canbe well describedin the framework of the proposed holographic model.

![](images/df335dc92f569e96bfbfedc8809daeca0432bce52b9d6b6d8f382e007966c074.jpg)  
FIG.6. The antiferromagnetic critical temperature $T _ { N }$ versus the external magnetic field $B$ calculated at the best fitting model parameters $m ^ { 2 } = 1 , k = 7 / 8$ and $J = - 0 . 7 1$ (solid curve) and compared with experimental data for pyrochlore compounds: $\mathrm { E r } _ { 2 - 2 x } \mathrm { Y } _ { 2 x } \mathrm { ' I } \mathrm { i } _ { 2 } \mathrm { O } _ { 7 }$ ．Black circles corresponds to zero doping, $x = 0$ ; magenta triangulars - to $x = 0 . 0 3 1$ ; green crosses - to $x = 0 . 0 8 5$ .The experimental data are from [13] and the figure is from [28].

Here we also found that the high-field ground state does not correspond to a simple disordered paramagnet. The high-field state is characterized by the intense dispersive excitation，which dispersion increases with the field. This was exactly observed in Ref. [38] where it was found that the critical fluctuations of the low-field state are accompanied by a precursor of the intense dispersive excitation noticed at high field. In Fig.7,we show the magnetic gap energy of $\mathrm { E r _ { 2 - 2 } } _ { x } \mathrm { Y _ { 2 } } _ { x } \mathrm { T i _ { 2 } } ( ) _ { 7 }$ asa function of magnetic dilution $( x )$ and magnetic field [13]. One should note that，in Fig.4 of Ref.[38],the excitation gap energy is zero when $B < B _ { c }$ and $T  0$ .But by the magnetic heat capacity method in Ref. 13],there is a nonzero gap energy ( $\simeq 0 . 1 \mathrm { s }$ meV)when $B < B _ { c }$ (see the case of $B = 1 \mathrm { T }$ in Fig.7).One can see that this nonzero gap energy is nearly independent on the doping $x$ which influences the antiferromagnetic electronic properties.So this nonzero gap in fact is from the background magnetic heat capacity which has nothing to do with the gap energy of the antiferromagnetic exaction. After removing this background contribution,we can find that the energy gap just satisfies the linear relationship (58),which

![](images/d7a741e748c17c81df73d030e2f6bfed0d266106f9a7446058afbda2ed74b441.jpg)  
FIG.7. The gap energy, $\Delta$ ,of $\mathrm { E r } _ { 2 - 2 x } \mathrm { Y } _ { 2 x } \mathrm { T i } _ { 2 } \mathrm { O } _ { 7 }$ as a function of magnetic dilution ( $x$ )and magnetic field.The data is from Ref. [13].

is equivalent to

$$
\widetilde { \Delta } \propto B / B _ { c } - 1
$$

with $\tilde { \Delta } \ = \ \Delta / T _ { N }$ .In the subfigure of Fig. 7 we plot the experimental data and the fitting curve by Eq. (67) The slope of the fitting curve is 4.2. We can also obtain the this slope from the holographic approach under the parameters of the best fitting from the Fig.6,which gives that the slope is 5.O. So we see that our holographic model can not only fit well the $T _ { N }$ $B$ behavior but also predict the critical magnetic field which is very close to the measurement result and the linear behavior of the energy gap with magnetic field with the slope nearly to the measurements at the same time.

We also found that holographic model describe well magnetic properties of other class of materials,which have strong magnetic anisotropy and large magnetic moments. The most illustrative example is BiCoPO $^ { 5 }$ [12, 28]. The compound consists of the interacting spins chains giving the 1D character to the compound. The spins have large magnetic moments,about 5.2 $\mu _ { B }$ per Co ion measured at 1.5 K [12]. It is much higher than the value 3.9 $\mu _ { B }$ expected for $\mathrm { C o ^ { 2 + } }$ ions having S=3/2. Such large value of $\mu _ { \mathrm { e f f } }$ is rather typical in Co $^ { 2 + }$ containing compounds due to additional orbital magnetic moment created in oxygen octahedra existed around the $\mathrm { C o ^ { 2 + } }$ ions.

Magnetic structure has been determined with the powder neutron diffraction experiments [41]. It was suggested there the ferromagnetic pairs of $\mathrm { C o ^ { 2 + } }$ ions are antiferromagnetically coupled within double chains. Because of these large values of the ferromagnetic pairs of $\mathrm { C o ^ { 2 + } }$ ions there exists a dipole-dipole interaction between the resulting magnetic moments,which is,probably, significantly, weaker than the exchange interactions. There is also strong the spin-orbital interaction,which always exists in heavy atoms such as Bi. The competition of all these interactions is probably responsible for the deviation from collinear AF ground state in BiCoPO $^ { 5 }$ [41]. In this sense the situation is very similar to the case of pyrochlore materials discussed above in the Fig.6. Therefore,as above the long range large interacting moments here can be replaced by the interacting tensor fields.It was found that the magnetic anisotropy and arrangements of magnetic moments in BiCoPO $^ { 5 }$ can be continuously tuned by temperature and external magnetic field [42].

However,neither field induced order-disorder nor spinflop transition was found in susceptibility and specific heat measurements under external field,although the spin-flop transition was seen in the magnetization dependence on magnetic field measured at T=2 K [12]. The Néel temperature, $T _ { N }$ and AF order were found to decrease gradually with the increase in field. But even at high fields no extra features other than the Néel transition was observed in specific heat [12] until the AF order was completely suppressed. Such behavior is consistent with the prediction of our holographic model suggesting that the quite strong and continuous change in magnetic anisotropy with the field may be well described with the interacting tensor field embedded in the gravitational AdS space, that is with the aid of the AdS/CFT duality.

# ACKNOWLEDGEMENTS

This work was supported in part by the National Natural Science Foundation of China with grants No.11035008,No.11375247 and No.11435006.

[1] S.Sachdev and B.Keimer,“Quantum criticality”,Phys. Today 64 (2),29 (2011).   
[2] J.A.Hertz，“Quantumcriticalphenomena”, Phys.Rev.B14,1165-1184 (1976).   
[3]S.Sachdev,Quantum Phase Transitions,Cambridge University Press,Cambridge (1999).   
[4] Focus issue: Quantum phase transitions,Nature Phys. 4,167-204 (2008).   
[5]P.Gegenwart，Q.Si,and F.Steglich，“Quantum criticality in heavy-fermion metals"，Nat.Phys.4,186-197 (2008).   
[6] H.v.Lohneysen，A.Rosch，M.Vojta and P.Wolfle, “Fermi-liquid instabilities at magnetic quantum phase transitions,”Rev.Mod.Phys.79,1015 (2007).   
[7]Q.Si, S.Rabello,K.Ingersent,and J.L.Smith,“Locally critical quantum phase transitions in strongly correlated metals”,Nature 413,804-808 (2001).   
[8] T.Senthil,A.Vishwanath,L.Balents,S.Sachdev,and M.P.A.Fisher,“Deconfined Quantum Critical Points”, Science 303,1490-1494 (2004)；H.Tanaka,et al.,“Observation of Field-Induced Transverse Néel Ordering in the Spin Gap System TlCuCl3"，J.Phys.Soc. Jpn.70, 939 (2001).   
[9] G. Chaboussant, P.A. Crowell, L.P. Levy, O. Piovesana, A.Madouri,and D.Mailly,“Experimental phase diagram of $\mathrm { C u _ { 2 } ( C _ { 5 } H _ { 1 2 } N _ { 2 } ) _ { 2 } C l _ { 4 } }$ :A quasi-one-dimensional antiferromagnetic spin-Heisenberg ladder"，Phys.Rev.B 55, 3046 (1997).   
[10] W. Shiramura,K. Takatsu, H. Tanaka,K.Kamishima, M. Takahashi,H.Mitamura,and T.Goto,“High-Field Magnetization Processes of Double Spin Chain Systems KCuCl3 and TlCuCl3”，J. Phys.Soc.Jpn.66，1900 (1997)；A. Oosawa,T. Takamasu,K. Tatani, H.Abe, N. Tsujii, O. Suzuki, H. Tanaka,G. Kido,and K.Kindo, “Field-induced magnetic ordering in the quantum spin system KCuCl3",Phys.Rev.B 66,104405 (2002).   
[11] Ch.Rüegg，N.Cavadini，A. Furrer，H.-U.Gdel,K. Krämer,H.Mutka,A.Wildes,K.Habicht and P.Vorderwisch，“Bose-Einstein condensation of the triplet states in the magnetic insulator TlCuCl3”，Nature 423，62 (2003)；T.Nikuni，M.Oshikawa，A.Oosawa,and H. Tanaka,“Bose-Einstein Condensation of Dilute Magnons in TlCuCl3",Phys.Rev.Lett.84 5868 (2000).   
[12] E.Mathews,K.M.Ranjith,M.Baenitz,R.Nath,“Field induced magnetic transition in low-dimensional magnets Bi(Ni,Co)PO5"，Solid State Communications 154 (2013), 55-59.   
[13] JF.Niven, M.B. Johnson, A. Bourque, P.J.Murray， D.D.James,H.A.Dabkowska, B.D.Gaulin,M.A.White, “Magnetic phase transitions and magnetic entropy in the XY antiferromagnetic pyrochlores $\mathrm { ' E r } _ { 1 - x } \mathrm { Y } _ { x }$ ） $^ 2$ Ti2O $^ { \circ }$ ”， Proc.R. Soc.A 470: 20140387 (2014).   
[14] Ch. Rüegg, et al., “Quantum Magnets under Pressure: Controlling Elementary Excitations in TiCuCl3”, Phys. Rev.Lett.100,205701(2008)   
[15] J.M. Maldacena,“The large N limit of superconformal field theories and supergravity,”Adv. Theor. Math. Phys.2,231 (1998)[Int.J. Theor.Phys.38,1113 (1999)] [arXiv:hep-th/9711200].   
[16] S.S. Gubser,1. R. KlebanovandA.M. Polyakov,“Gauge theory correlators from non-critical string theory,”Phys. Lett.B 428,105(1998) [arXiv:hep-th/9802109].   
[17] E.Witen,“Anti-de Sitter space and holography,” Adv.Theor.Math.Phys.2，253(1998）[arXiv:hepth/9802150].   
[18] E.Witten,Anti-de Sitter space,thermal phase transition，and confinement in gauge theories,Adv.Theor. Math.Phys.2,505(1998) [arXiv:hep-th/9803131].   
[19] S. S.Gubser,“Breaking an Abelian gauge symmetry near a black hole horizon,”Phys.Rev.D 78,065034 (2008) [arXiv:0801.2977 [hep-th]].   
[20] S.A. Hartnoll, C. P. Herzog and G. T. Horowitz,“Building a Holographic Superconductor,” Phys. Rev.Lett. 101,031601 (2008) [arXiv:0803.3295 [hep-th].   
[21] R. G. Cai, L. Li, L. F. Li and R. Q. Yang, “Introduction to Holographic Superconductor Models," Sci.China Phys.Mech.Astron. 58，060401 (2015) [arXiv:1502.00437 [hep-th]].   
[22] S. -S. Lee,“A Non-Fermi Liquid from a Charged Black Hole:A Critical Fermi Ball,”Phys.Rev.D 79,086006 (2009）[arXiv:0809.3402 [hep-th]   
[23] H.Liu, J. McGreevy and D.Vegh,“Non-Fermi liquids from holography,”Phys.Rev.D 83,065029 (2011) [arXiv:0903 2477 [hen-thl]   
[24] M. Cubrovic, J. Zaanen and K. Schalm,“String Theory, Quantum Phase Transitions and the Emergent FermiLiquid,” Science 325,439 (2009) [arXiv:0904.1993 [hepth]].   
[25] R.-G. Cai and R. -Q. Yang， “ParamagnetismFerromagnetism Phase Transition in a Dyonic Black Hole,”Phys. Rev. D 90,081901 (2014) [arXiv:1404.2856 [hep-th]].   
[26] R. G. Cai and R. Q. Yang,“Holographic model for the paramagnetism/antiferromagnetism phase transition," Phys.Rev.D 91,no.8,086001(2015） [arXiv:1404.7737 [hep-th]].   
[27] R.G. Cai and R.Q. Yang,“Antisymmetric tensor field and spontaneous magnetization in holographic duality," arXiv:1504.00855 [hep-th].   
[28] R.G. Cai, R. Q. Yang and F. V. Kusmartsev, “A holographic model for antiferromagnetic quantum phase transition induced by magnetic field,” arXiv:1501.04481 [hepth]:   
[29] R. -G. Cai and Y. -Z. Zhang,“Black plane solutions in four-dimensional space-times,” Phys.Rev.D 54,4891 (1996) [gr-qc/9609065].   
[30] N.Iqbal，H.Liu，M.Mezei and Q.Si，“Quantum phase transitions in holographic models of magnetism and superconductors,”Phys.Rev.D 82,045002 (2010) [arXiv:1003.0010 [hep-th]].   
[31] Ar. Abanov,A. Chubukov,“Anomalous Scaling at the Quantum Critical Point in Itinerant Antiferromagnets”, Phys. Rev.Lett.93 255702 (2004);   
[32] S. Sachdev,and E.R.Dunkel, “Quantum critical dynamics of the two-dimensional Bose gas”， Phys. Rev. B 73, 085116 (2006)   
[33] T. Faulkner, H. Liu, J. McGreevy and D. Vegh,“Emergent quantum criticality, Fermi surfaces,and AdS(2)," Phys.Rev.D 83,125002 （2011）[arXiv:0907.2694[hepth]].   
[34] A. J. Mills,“Effect of a nonzero temperature on quantum critical points in itinerant fermion systems”,Phys.Rev. B 48,7183 (1993).   
[35] J.Bauer,P.Jakubczyk,and W.Metzner,“Critical temperature and Ginzburg region near a quantum critical point in two-dimensional metals",Phys.Rev.B 84, 075122 (2011).   
[36] M.E. Zhitomirsky，M.V. Gvozdikova,P. C.W. Holdsworth,R.Moessner,“Quantum order by disorder and accidental soft mode in Er $^ 2$ Ti2O $\gamma$ ”, Phys. Rev. Lett. 109,077204 (2012).   
[37] J.Oitmaa,R.R.P.Singh,B.Javanparast，A.G.R. Day,B.V.Bagheri,M.J.P.Gingras,“Phase transition and thermal order-by-disorder in the pyrochlore antiferromagnetic Er2Ti2O $^ 7$ :a high-temperature series expansion study",Phys. Rev.B 88,220404 (2013).   
[38] J.P.C. Ruff,J.P. Clancy,A. Bourque,M. A. White,M. Ramazanoglu, J. S. Gardner, Y. Qiu, J. R. D. Copley, M.B.Johnson,H.A.Dabkowska,and B.D.Gaulin, “Spin Waves and Quantum Criticality in the Frustrated XY Pyrochlore Antiferromagnet Er $^ 2$ Ti2O $^ { \circ }$ ”, Phys. Rev. Lett.101,147205 (2008).   
[39] D.M.Forrester, K.E. Kuerten,F.V. Kusmartsev,“Magnetic cellular automata and the formation of glassy and magnetic structures from a chain of magnetic particles", Phys. Rev.B 75,014416 (2007).   
[40] K.E.Kurten,F.V.Kusmartsev,“Fractal structures in systems made of small magnetic particles",Phys.Rev.B

72,014433 (2005). [41]O.Mentre,F.Bouree,J.Rodriguez-Carvajal,A.El. Jazouli，N.El.Khayati and El.MKetatni,“Magnetic structure and analysis of the exchange interactions in BiMO(PO4) (M = Co, Ni)",J. Phys.: Condens. Matter,20,415211, (2008).

[42]H.Yamaguchi,S.Yasin，S.Zherlitsyn，K.Omura，S. Kimura,S.Yoshii,K.Okunishi,Z.He,T.Taniyama, M.Itoh,M.Hagiwara,“Novel Phase Transition Probed by Sound Velocity in Quasi-One-Dimensional Ising-Like Antiferromagnet BaCo2V2O8”，J.Phys. Soc.Jpn.,80, 033701，(2011).