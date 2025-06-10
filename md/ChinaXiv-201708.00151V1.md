# Fractional Quantum Hall Effect via Holography: Chern-Simons,Edge States,and Hierarchy

Mitsutoshi Fujita $\underset { ^ { . } } { a 1 }$ ，Wei Li $^ { b 2 }$ , Shinsei Ryu $c 3$ and Tadashi Takayanagi $^ { b 4 }$

（204号 $a$ Department of Physics, Kyoto University, Kyoto 606-8502, Japan （204号 $b$ Institute for Physics and Mathematics of the Universe (IPMU), Universityof Tokyo，Kashiwa，Chiba 277-8582，Japan $c$ Department of Physics, University of California, Berkeley， CA 94720， USA

# Abstract

We present three holographic constructions of fractional quantum Hall efect (FQHE) via string theory. The first model studies edge states in FQHE using supersymmetric domain walls in $\mathcal { N } = 6$ Chern-Simons theory. We show that D4-branes wrapped on $\mathbb { C P } ^ { 1 }$ or D8- branes wrapped on $\mathbb { C P } ^ { 3 }$ create edge states that shift the rank or the level of the gauge group,respectively. These holographic edge states correctly reproduce the Hall conductivity. The second model presents a holographic dual to the pure $U ( N ) _ { k }$ (Yang-Mills-)Chern-Simons theory based on a D3-D7 system. Its holography is equivalent to the level-rank duality, which enables us to compute the Hall conductivity and the topological entanglement entropy. The third model introduces the first string theory embedding of hierarchical FQHEs,using A string on $\mathbb { C } ^ { 2 } / Z _ { n }$

# 1Introduction and Summary

The fractional quantum Hall effect (FQHE) is fascinating not only because its extraordinary experimental realizations,but more importantly, because it is a manifestation of the fundamental concept of topological phase (see e.g.[1, 2， 3, 4]). The fractional quantum Hall states are characterized by the filling fraction $\nu$ .5When $\nu$ is an integer, it is called the integer quantum Hall effect.

The simplest series of the fractional quantum Hall states is known as the Laughlin state which has $\textstyle \nu = { \frac { 1 } { k } }$ with $k$ being an odd integer6. At low energies, the Laughlin states are described by a (2+1)-dimensional $U ( 1 )$ Chern-Simons theory coupled to an external electromagnetic field $\tilde { A }$ [2]:

$$
S _ { Q H E } = \frac { k } { 4 \pi } \int { \cal A } \wedge d { \cal A } + \frac { e } { 2 \pi } \int \tilde { \cal A } \wedge d { \cal A } ,
$$

where $A$ is the $U ( 1 )$ gauge feld that describes the internal degrees of freedom and $e$ is the charge of the electrons. It follows straightforwardly from (1.1) that the Hall conductivity (defined by $j _ { x } = \sigma _ { x y } E _ { y }$ ） is fractionally quantized: $\begin{array} { r } { \sigma _ { x y } = \frac { \nu e ^ { 2 } } { h } } \end{array}$ .Since the Chern-Simons gauge theory is topological [5] and has no propagating degree of freedom in contrast to the Maxwell theory, the FQHE provides an example for the gapped many-body system whose ground state can be described by a topological feld theory.

A more generic category of FQHEs is defined by filing fractions which are continued fractions:

$$
\nu = { \frac { 1 } { a _ { 1 } - { \frac { 1 } { a _ { 2 } - { \frac { 1 } { a _ { 3 } - \cdots } } } } } } .
$$

Such FQHE appears in real materials and has a fascinating underlying structure calld hierarchy: they are described by a series of $U ( 1 )$ Chern-Simons gauge fields,each providing quasi-particles that act as constituent particles that form the quasi-particles in the next level—hence the name “hierarchy "[3,1, 2, 4].

Fig. 1 shows the standard experimental realization of QHE: a sample of two-dimensional electron gas is placed on the $x y$ -plane,with a magnetic field $B _ { z }$ applied perpendicular to the plane. The sample has four edges, to which four probes are attached. To measure the Hall conductivity $\sigma _ { x y }$ ， we apply an electric field $E _ { y }$ in the $y$ -direction and measure the current $j _ { x }$ 7． Since there is an energy gap and realistic samples contain impurities, the electrons in the (2+1)- dimensional bulk sufer from localization and cannot move around macroscopically, thus the bulk electrons do not contribute to the quantum Hall conductivity. Instead, the electrons can only move along the edges of samples,since the electron orbit at the boundary is stable against impurities. These are called the edge states (for more details,see textbooks [3,1,2,4]). In other words,the quantum Hallfuid is an insulator except at its boundaries. For this reason, quantum Hall states are sometimes called “topological insulator”. More general topologically insulating states,including the quantum spin Hall state and its higher-dimensional relatives, have been discussed,fully classified,[6] and experimentally realized recently [7]. In terms of the ChernSimons theory, the quantization of the Hall conductivity can be understood as follows: since the Chern-Simons action is not gauge invariant in the presence of (1+1)-dimensional boundaries of the (2+1)-dimensional spacetime,there exists a massess chiral scalar field on the boundaries [2] and they contribute to the conductivity.

![](images/e65e8e4270095f4d5be454c71d12b84d39f0e1aa25ccbf5f542c6364af28ea9d.jpg)  
Figure 1: Experimental setup of the quantum Hal effect: a sample of a two-dimensional electron gas is placed on the $x y$ -plane,with a magnetic field $B _ { z }$ perpendicular to the plane and an electric field $E _ { y }$ along the $y$ -direction. The quantum Hall current flows along the $x$ -direction, perpendicular to the $\vec { E }$ -field.

The main purpose of this paper is to model fractional quantum Hall effect—in particular its Chern-Simons theory description—in string theory and analyze them via AdS/CFT [8].8 We will present three different models, each focusing on different aspects of the FQHE.They are summarized as follows.

Model I: Supersymmetric edge states in $\mathcal { N } = 6$ Chern-Simons theory. The first model is based on the recently discovered $A d S _ { 4 } / C F T _ { 3 }$ correspondence: $\mathcal { N } = 6$ Chern-Simons theory as the holographic dual to type IIA string theory on $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ [22]. We will construct two types of supersymmetric D-brane configurations to model the edge state of FQHE. First， we wrap $M$ D4-branes on the $\mathbb { C P } ^ { 1 }$ inside the $\mathbb { C P } ^ { 3 }$ and attach them to a stack of $N$ D2-branes along one spatial dimension; the $( 1 + 1 )$ -dimensional intersection acts as a domain wall across which the gauge group $U ( N ) _ { k } \times U ( N ) _ { - k }$ jumps into $U ( N - M ) _ { k } \times U ( N ) _ { - k }$ . Similarly, we can also wrap $l$ D8-branes on the entire $\mathbb { C P } ^ { 3 }$ and attach them to the $N$ D2-branes in the same way; the gauge group now jumps into $U ( N ) _ { k - l } \times U ( N ) _ { - k }$ upon crossing the edge.

These intersecting D-brane configurations with generic $( N , k )$ and $M$ (or $l$ ）are interesting in their own right: first, they are new examples of supersymmetric edge states in $\mathcal { N } = 6$ ChernSimons theory; second, they are stable configurations that break the parity symmetry.9 However, in this paper,we will only focus on their application in modeling FQHE holographically. To model a realistic FQHE,we simply set $N = 1$ and treat the $U ( N ) _ { - k }$ part as inspector. Then the single D4-brane intersection produces a standard edge state for FQHE with $\textstyle \nu = { \frac { 1 } { k } }$ ; and the $l$ D8- brane intersection gives a novel construction of an edge state between two abelian FQHEs with different flling factions $\textstyle \nu = { \frac { 1 } { k } }$ and $\frac { 1 } { k - l }$ . We then compute the Hall conductivity holographically. The D4-brane computation correctly reproduces the standard FQHE result, while the D8-brane result provides a prediction for the yet-to-be measured Hall conductivity in such interfaces of quantum Hall fuids.

One may worry that realistic FQHE systems do not have any supersymmetry as opposed to the above examples. However,in the effective field theory description,the FQHE essentially Occurs due to the presence of the Chern-Simons gauge field and its superpartners such as scalar fields and fermions do not contribute in any important way. Therefore, we can still capture the standard FQHE even in supersymmetric theories.

Model II: holographic realization of level-rank duality and topological entanglement entropy.FQHE is described by pure Chern-Simons theories,whereas model I(which is based on $\mathcal { N } = 6$ Chern-Simons theory) has additional matter fields.10 Motivated by this, in the second model, we realize holographically the pure Chern-Simons gauge theory.

Model II is based on the AdS/CFT for a D3-D7 system.1l We start with the familiar nonsupersymmetric AdS/CFT correspondence generated by $N$ D3-branes compactified on a circle with anti-periodic boundary conditions for fermions: at low energies, the boundary theory is a 3D bosonic Yang-Mills theory with $U ( N )$ gauge group; while the bulk side is the $A d S _ { 5 }$ soliton of type IIB string [24]. We then deform this system by adding $k$ D7-brane at the tip of the soliton. The boundary theory now becomes a $U ( N ) _ { k }$ Yang-Mills-Chern-Simons theory; and the bulk geometry becomes a $A d S _ { 5 }$ soliton with additional $k$ axion fluxes. Finally we take the IR limit: at the boundary the Chern-Simons term dominates over the Yang-Mills term; while in the bulk the theory reduces to probe D7-brane worldvolume action. Therefore in the end we arrive at a duality between the $U ( N ) _ { k }$ Chern-Simons theory living on $N$ D3-branes compactified on a circle with the $U ( k ) _ { N }$ Chern-Simons theory living on the $k$ probe D7-brane compactifed on $S ^ { 5 }$ ： Interestingly, the holography in this D3-D7 system manifests itself as the level-rank duality of the pure $U ( N ) _ { k }$ Chern-Simons theory by taking low energy limit.

In this model, we can holographically compute the Hall conductivity both from the bulk supergravity and from the theory on a probe D3-brane or D7-brane which is dual to an edge state. The topological entanglement entropy is a quantity that can be computed from a given ground state of the FQHE or the Chern-Simons effective field theory [25,26,27],and encodes information on the type of quasi-particles (topological excitations) that can be build on the ground state. We will clarify how the topological entanglement entropy appears via the AdS/CFT duality [8].

Model III: holographic realization of hierarchical FQHE via resolved $\mathbb { C } ^ { 2 } / Z _ { n }$ singularity. As mentioned earlier, the single $U ( 1 )$ Chern-Simons theory can only describe FQHE whose filling fraction $\nu$ satisfies $\textstyle { \frac { 1 } { \nu } } \in \mathbb { Z }$ . To model more generic (hierarchical) FQHEs we need to employ systems with multiple $U ( 1 )$ gauge fields. Inspired by the resemblance between the continued fraction form of $\nu$ in hierarchical FQHEs and the Hirzebruch-Jung continued fraction in the minimal resolution of the (in general non-supersymmetric) orbifold $\mathbb { C } ^ { 2 } / Z _ { n }$ ，we consider the holographic duality between the F1-NS5 system on $\mathbb { C } ^ { 2 } / Z _ { n }$ and type IIA string in the $A d S _ { 3 } \times S ^ { 3 } \times \mathbb { C } ^ { 2 } / Z _ { n }$ background. The FQH system now lives in the bulk $A d S _ { 3 }$ and the RR 3-form compactified on the chain of blown-up 2-cycles (exceptional divisors) gives rise to a chain of $U ( 1 )$ gauge fields, corresponding to the hierarchy of $U ( 1 )$ fields in the effective description of the hierarchical FQHE.

Different from the previous two models, the FQH system in Model II lives in the (2+1)- dimensional bulk geometry and its edge states are at the boundary. The holographic duality in string theory is then exactly the edge/bulk correspondence in the condense matter physics context.

This paper is organized as follows. Model I, II and III are presented in Section 2, 3 and 4, respectively. Section 5 summarizes the main merits of our constructions and discusses several general issues in modeling FQHE using string theory in view of recent developments of FQHE.

# 2 Edge States in ${ \mathcal { N } } = 6$ Chern-Simons Theory

The purpose of this section is to define and holographically study the supersymmetric version of edge states,which are particular types of interfaces or defects,in the $\mathcal { N } = 6$ Chern-Simons theory. The $\mathcal { N } = 6$ Chern-Simons theory consists of bifundamental scalar fields and fermions in addition to the gauge felds. Therefore it includes dynamical degrees of freedom. However, the QHE is a rather topological phenomenon and these extra degrees of freedom do not play important roles,as we will confirm from the holographic calculations.

# 2.1 Holographic Dual of $\mathcal { N } = 6$ Chern-Simons Theory

We consider the $A d S _ { 4 } / C F T _ { 3 }$ duality of the $\mathcal { N } = 6$ Chern-Simons theory （ABJM theory）[22]. The duality can be generated by $N$ M2-branes probing the singularity $\mathbb { C } ^ { 4 } / Z _ { k }$ : the CFT side is the $\mathcal { N } = 6$ superconformal Chern-Simons-Matter theory; the gravity side is the M-theory living in $A d S _ { 4 } \times S ^ { 7 } / Z _ { k }$ ：

The $N = 6$ Chern-Simons theory consists of two gauge fields $A ^ { ( 1 ) }$ and $A ^ { ( 2 ) }$ for the $U ( N ) _ { k } \times$ （204号 $U ( N ) _ { - k }$ gauge group in addition to bifundamental matter fields (scalars and fermions). If we restrict to the gauge feld sector, the action is

$$
S _ { \mathcal { N } = 6 } ^ { g a u g e } = \frac { k } { 4 \pi } \int \mathrm { T r } A ^ { ( 1 ) } \wedge d A ^ { ( 1 ) } - \frac { k } { 4 \pi } \int \mathrm { T r } A ^ { ( 2 ) } \wedge d A ^ { ( 2 ) } .
$$

We represent this theory as $U ( N ) _ { k } \times U ( N ) _ { - k }$ Chern-Simons theory, where $k$ and $- k$ denote the levels. In our application to the quantum Hall efect,we will focus on the first $U ( N )$ gauge group.

Assuming $k$ is large, the gravity side is reduced to the type IIA string in $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ [22]. Before taking the $Z _ { k }$ quotient, the gravity side is $A d S _ { 4 } \times S ^ { 7 }$

$$
d s _ { 1 1 D } ^ { 2 } = { \frac { R ^ { 2 } } { 4 } } ( d s _ { A d S _ { 4 } } ^ { 2 } + 4 d s _ { S ^ { 7 } } ^ { 2 } ) , \qquad \mathrm { w i t h } \qquad d s _ { S ^ { 7 } } ^ { 2 } = ( d y + A ) ^ { 2 } + d s _ { \mathbb { C P } ^ { 3 } } ^ { 2 }
$$

where $R = ( 2 ^ { 5 } \pi ^ { 2 } k N ) ^ { 1 / 6 }$ and $y \sim y + 2 \pi$ . The metric of $\mathbb { C P } ^ { 3 }$ is explicitly expressed as follows in the coordinate system [28]

$$
\begin{array} { r c l } { { d s _ { \mathbb { C P } ^ { 3 } } ^ { 2 } } } & { { = } } & { { d \xi ^ { 2 } + \cos \xi ^ { 2 } \sin ^ { 2 } \xi \left( d \psi + \displaystyle \frac { \cos \theta _ { 1 } } { 2 } d \varphi _ { 1 } - \displaystyle \frac { \cos \theta _ { 2 } } { 2 } d \varphi _ { 2 } \right) ^ { 2 } } } \\ { { } } & { { } } & { { + \displaystyle \frac { 1 } { 4 } \cos ^ { 2 } \xi \left( d \theta _ { 1 } ^ { 2 } + \sin ^ { 2 } \theta _ { 1 } d \varphi _ { 1 } ^ { 2 } \right) + \displaystyle \frac { 1 } { 4 } \sin ^ { 2 } \xi ( d \theta _ { 2 } ^ { 2 } + \sin ^ { 2 } \theta _ { 2 } d \varphi _ { 2 } ^ { 2 } ) . } } \end{array}
$$

Now we take the $Z _ { k }$ quotient: $\tilde { y } \equiv k y$ with ${ \tilde { y } } \sim { \tilde { y } } + 2 \pi$ ; and reduce to IIA via the reduction formula (in this paper we always work with the string frame metric setting $\alpha ^ { \prime } = 1$ ）

$$
d s _ { 1 1 D } ^ { 2 } = e ^ { - 2 \phi / 3 } d s _ { I I A } ^ { 2 } + e ^ { \frac { 4 } { 3 } \phi } ( d \tilde { y } + \tilde { A } ) ^ { 2 } ,
$$

with $\begin{array} { r } { e ^ { 2 \phi } = \frac { R ^ { 3 } } { k ^ { 3 } } = 2 ^ { \frac { 5 } { 2 } } \pi \sqrt { \frac { N } { k ^ { 5 } } } } \end{array}$ and $\tilde { A } = k A$ The RR 2-form $F ^ { ( 2 ) } = d \tilde { A }$ in type IIA string （we sometimes call this a D6-brane flux) is explicitly given as follows

$$
\begin{array} { r c l } { { { \cal F } ^ { ( 2 ) } } } & { { = } } & { { k \Big ( - \cos \xi \sin \xi d \xi \wedge ( 2 d \psi + \cos \theta _ { 1 } d \varphi _ { 1 } - \cos \theta _ { 2 } d \varphi _ { 2 } ) } } \\ { { } } & { { } } & { { - { \displaystyle \frac { 1 } { 2 } } \cos ^ { 2 } \xi \sin \theta _ { 1 } d \theta _ { 1 } \wedge d \varphi _ { 1 } - { \displaystyle \frac { 1 } { 2 } } \sin ^ { 2 } \xi \sin \theta _ { 2 } d \theta _ { 2 } \wedge d \varphi _ { 2 } \Big ) , } } \end{array}
$$

while the RR 4-form remains the same: F(4) = 3Re 3éAdS4， produced by the background D2- branes.

The IIA string frame metric gives the $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ IIA background [22]:

$$
d s _ { I I A } ^ { 2 } = { \tilde { R } } ^ { 2 } ( d s _ { A d S _ { 4 } } ^ { 2 } + 4 d s _ { \mathbb { C P } ^ { 3 } } ^ { 2 } ) ,
$$

where $\begin{array} { r } { \tilde { R } ^ { 2 } \ = \ \frac { R ^ { 3 } } { 4 k } \ = \ \pi \sqrt { \frac { 2 N } { k } } } \end{array}$ √N.This background preserves 24 supersymmetries after the nearhorizon supersymmetry enhancement,which match the three-dimensional $\mathcal { N } = 6$ superconformal symmetry in the CFT side. Note that in this coordinate system the volumes of $\mathbb { C P } ^ { 1 }$ and $\mathbb { C P } ^ { 3 }$ （20 are:12

$$
\mathrm { V o l } ( \mathbb { C } \mathbb { P } ^ { 1 } ) = 4 \pi \tilde { R } ^ { 2 } , \qquad \mathrm { V o l } ( \mathbb { C } \mathbb { P } ^ { 3 } ) = \frac { 3 2 } { 3 } \pi ^ { 3 } \tilde { R } ^ { 6 } .
$$

At finite temperature, the $A d S _ { 4 }$ is replaced with the $A d S _ { 4 }$ black hole

$$
d s ^ { 2 } = - \left( r ^ { 2 } - \frac { r _ { 0 } ^ { 3 } } { r } \right) d t ^ { 2 } + \frac { d r ^ { 2 } } { r ^ { 2 } - \frac { r _ { 0 } ^ { 3 } } { r } } + r ^ { 2 } ( d x ^ { 2 } + d y ^ { 2 } ) .
$$

The temperature is given by $\begin{array} { r } { T = \frac { 3 r _ { 0 } } { 4 \pi } } \end{array}$

# 2.2 Edge States from Intersecting D-branes

Now we consider the generalization of edge states in the QHE to those in the pure $U ( N ) _ { k }$ ChernSimons theory. The edge state is naturally defined by a line defect beyond which the rank $N$ of the gauge group or its level $k$ changes. If we set $N = 1$ , then the first type of the defect reduces to the ordinary edge state of the QHE at least formally. The latter reduces to an edge which separates the quantum Halliquid with the different filling fractions $\textstyle \nu = { \frac { 1 } { k } }$ and $\textstyle \nu = { \frac { 1 } { k ^ { \prime } } }$ .Recently this kind of interface has been realized experimentally in [29] to detect the fractional statistics in the FQHE.

In our $\mathcal { N } = 6$ Chern-Simons theory with the gauge group $U ( N ) _ { k } \times U ( N ) _ { - k }$ ， we can define the two types of supersymmetric edge states in the same way by concentrating on the first $U ( N )$ gauge group; one shifts the rank,and the other shifts the level. Indeed, we can find two D-brane constructions of edge states in type IIA string on $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ ：

First,we can wrap a D4-brane on the $\mathbb { C P } ^ { 1 }$ inside $\mathbb { C P } ^ { 3 }$ and attach it to a stack of $N$ D2- branes along one spatial dimension,as shown in Fig. 2. Alternatively, we can wrap a D8-brane on the entire $\mathbb { C P } ^ { 3 }$ and then attach it to the D2-branes,as shown in Fig.3. These two kinds of intersections of the D4 and D8 with the D2-branes are (1+1)-dimensional defects. We regard them as the string theory descriptions of the two kinds of edge states in the $\mathcal { N } = 6$ Chern-Simons theory. As we willsee below,these two edge states affect the boundary theory in different ways. If we consider an edge state which consists of $M$ D4-branes, the rank of the gauge group jumps from $U ( N ) _ { k } \times U ( N ) _ { - k }$ to $U ( N - M ) _ { k } \times U ( N ) _ { - k }$ . On the other hand, at the edge states defined by $l$ D8-branes, the level jumps from $U ( N ) _ { k } \times U ( N ) _ { - k }$ to $U ( N ) _ { k - l } \times U ( N ) _ { - k }$ . Both constructions break the parity symmetry of the original ABJM theory.

The former argument is consistent with the interpretation of fractional branes in [23]. If we consider an unstable configuration of $M$ D4-brane wrapped on $\mathbb { C P } ^ { 1 }$ which are parallel with the background D2-branes, then the D4-branes fall into the horizon of $A d S _ { 4 }$ and only the flux remains. This background is argued to be dual to the $\mathcal { N } = 6$ Chern-Simons theory with the gauge group $U ( N - M ) _ { k } \times U ( N ) _ { - k }$ [23].

The latter argument leads us to a new setup of the $A d S _ { 4 } / C F T _ { 3 }$ as a byproduct. The IIA string on $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ with the RR flux due to $l$ D8-branes wrapped on $\mathbb { C P } ^ { 3 }$ is dual to the Chern-Simons theory with the gauge group $U ( N ) _ { k - l } \times U ( N ) _ { - k }$ ， which preserves $\mathcal { N } = 3$ （204号 supersymmetry.

Though we will not discuss below, we can also find other types of similar brane configurations i.e. a D2-brane or D6-brane wrapped on $\mathbb { C P } ^ { 3 }$ . They are edge states which shift the rank or level of both of the two $U ( N )$ gauge fields simultaneously.

![](images/0797109e9e4fa90f003fec22fe8dee692d071e3ff66b53052623a6aaae84a607.jpg)  
Figure 2: Edge state from intersecting $M$ D4-branes wrapped on $\mathbb { C P } ^ { 1 }$ with $N$ D2-branes: the gauge group on D2-branes changes from $U ( N ) _ { k } \times U ( N ) _ { - k }$ to $U ( N - M ) _ { k } \times U ( N ) _ { - k }$ when crossing the edge.

![](images/323403dec8a5c4c48a76a5ce399c7905109df74103891441ddd3ffd17e342164.jpg)  
Figure 3: Edge state from intersecting $l$ D8-branes wrapped on $\mathbb { C P } ^ { 3 }$ with $N$ D2-branes: the gauge group on D2-branes changes from $U ( N ) _ { k } \times U ( N ) _ { - k }$ to $U ( N ) _ { k - l } \times U ( N ) _ { - k }$ when crossing the edge.

# 2.2.1 D2⊥D4 Intersection

We first consider the domain wall produced by a probe D4-brane that wraps on the $\mathbb { C P } ^ { 1 }$ inside （204号 $\mathbb { C P } ^ { 3 }$ and attaches to $N$ D2-brane along one spatial direction:

$$
\begin{array} { r l r } {  { \frac { A d S _ { 4 } \times \mathbb { C P } ^ { 3 } : \mathrm { ~ | ~  ~  ~ } x \mathrm { ~ \ ~ } y \mathrm { ~ \ } r \mathrm { ~ | ~ \theta _ 1 ~ } \varphi _ { 1 } \mathrm { ~ \ } \theta _ { 2 } \mathrm { ~ \ } \varphi _ { 2 } \mathrm { ~ \ } \xi \mathrm { ~ \ } \psi \mathrm { ~ \ } }  } } \\ { \mathrm { ~  ~  ~ } N \mathrm { ~ D 2 : ~ | ~ \times ~ \times ~ \times ~  ~ } } \\ { k \mathrm { ~ D 6 \mathrm { - } f l u x : } } \\ { \mathrm { ~  ~ | ~ D 4 : ~ | ~ \times ~ \times ~  ~ } } & { \times \mathrm { ~ | ~ \times ~ \mathrm { ~ \scriptsize ~ \times ~ \times ~ \times ~ \times ~ \times ~ } ~  ~ } } \end{array}
$$

where the coordinate $( \theta _ { 1 } , \varphi _ { 1 } , \theta _ { 2 } , \varphi _ { 2 } , \xi , \psi )$ labels the $\mathbb { C P } ^ { 3 }$ .We choose the $\mathbb { C P } ^ { 1 }$ to be the one defined by $( \theta _ { 1 } , \varphi _ { 1 } )$ at $\xi = 0$ so that the D4-brane in $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ preserves 12 out of the total 24 supersymmetries. One can show this by lifting the system to M-theory and counting the number of supersymmetries. The detailed proof is in Appendix A.1.

This D4-brane has the world-volume action

$$
S _ { D 4 } = - T _ { 4 } \int d ^ { 5 } \sigma e ^ { - \phi } \sqrt { - \operatorname * { d e t } ( G + 2 \pi { \cal F } ) } + 2 \pi ^ { 2 } T _ { 4 } \int C ^ { ( 1 ) } \wedge { \cal F } \wedge { \cal F } ,
$$

where $T _ { 4 } = ( 2 \pi ) ^ { - 4 }$ in the unit $\alpha ^ { \prime } = 1$ and $C ^ { ( 1 ) }$ is sourced by the $k$ D6-flux (2.5), which leads to $\begin{array} { r } { \int _ { \mathbb { C P } ^ { 1 } } F ^ { ( 2 ) } = 2 \pi k } \end{array}$ . Integrating over the internal $\mathbb { C P } ^ { 1 }$ , the D4 Chern-Simons term becomes

$$
S _ { D 4 } ^ { C S } = \frac { k } { 4 \pi } \int A \wedge d A .
$$

Note that the D4-brane wrapped on $\mathbb { C P } ^ { 1 }$ is charged only under one (i.e. the first） of the two gauge groups $U ( N ) _ { k } \times U ( N ) _ { - k }$

The probe D4-brane ends on a codimension-1 subspace of the boundary $R ^ { 1 , 2 }$ of the $A d S _ { 4 }$ ， thus creating a domain wall on the $D 2$ -brane. The gauge group changes from $U ( N ) _ { k } \times U ( N ) _ { - k }$ to $U ( N - 1 ) _ { k } \times U ( N ) _ { - k }$ . The disappeared $U ( 1 )$ is carried by the D4-brane that extends into the bulk.

In order to relate to an ordinary QH system with a single gauge group, we can concentrate on the first gauge group $U ( N ) _ { k }$ of our Chern-Simons theory, treating the second one with $U ( N ) _ { - k }$ （204号 as a spectator. Even though the two gauge fields are interacting in our theory, this fact is not important when we consider the Hall conductivity since it is quantized and determined by the topological structure of the theory.

To understand the charge and statistics of a quasi-particle in the $ { \mathcal { N } _ { \mathrm { ~ \scriptsize ~ = ~ } } } 6$ Chern-Simons theory, consider a fundamental string (F-string) which is charged under one of the two gauge groups. To extract one of the gauge groups, we insert a D4-brane wrapped on $\mathbb { C P } ^ { 1 }$ (called the fractional D2-brane [23]) as a probe and consider a F-string which ends at a point $( x _ { 0 } , y _ { 0 } )$ on the D4-branes. Such a string can be found by considering the one between the edge D4-brane and a D4 wrapped on $\mathbb { C P } ^ { 2 }$ (called dibaryon [22, 23]). This corresponds to a static charge that generates $j ^ { \mathrm { u } } = \delta ( x - x _ { 0 } ) \delta ( y - y _ { 0 } )$ on the edge D4-brane. The relevant part of the edge D4-brane action including the F-string charge becomes

$$
\frac { k } { 4 \pi } \int A \wedge d A + \int j ^ { 0 } A _ { 0 } ,
$$

after integrated over $\mathbb { C P } ^ { 1 }$ . Solving the equation of motion, we obtained the magnetic field and its flux:

$$
F _ { x y } = \frac { 2 \pi } { k } \delta ( x - x _ { 0 } ) \delta ( y - y _ { 0 } ) , \quad \Phi = \int d x d y F _ { x y } = \frac { 2 \pi } { k } .
$$

Therefore,when two such quasi-particles are interchanged, the total wave-function acquires a phase factor $e ^ { i { \frac { \pi } { k } } }$ .13 Namely, the F-string creates an anyon with the fractional statistics. The same situation appears when we consider the FQHE with the filing fraction

$$
\nu = { \frac { 1 } { k } } .
$$

Indeed,the low energy efective theory of the FQHE with (2.13) is known to be described by the Chern-Simons theory at level $k$ , namely (2.11). The dibaryon (a D4 wrapped on $\mathbb { C P } ^ { 2 }$ ）is interpreted as the quasi-particle (anyon). In the ordinary FQHE, $k$ is taken to be an odd integer since an electron obeys the fermionic statistics.

This means that a F-string should have the fractional charge $\frac { e } { k }$ in the boundary quantum Hall system. Recall that in string theory, the F-string has unit charge under gauge field. To match with the experimental result,we rescale the gauge field: $A \ \to \ { \frac { e } { k } } A$ ，under which the Chern-Simons terms becomes

$$
S _ { D 4 } ^ { C S } = \frac { \tilde { k } _ { D 4 } } { 4 \pi } \int \cal A \wedge { } d \cal A , ~ { { \mathrm { w i t h } } } ~ \tilde { k } _ { D 4 } \equiv \frac { e ^ { 2 } } { k } .
$$

To summarize, a D4-brane wrapped on $\mathbb { C P } ^ { 1 }$ and attached to D2-brane creates an edge that divides the D2-brane into two parts: the gauge group of its CFT is $U ( N ) _ { k } \times U ( N ) _ { - k }$ on one side of the wall and $U ( N - 1 ) _ { k } \times U ( N ) _ { - k }$ on the other. Though this is already an interesting edge state in a generalized sense,to relate to the ordinary edge state in the QHE,one can simply set $N = 1$ .14 Then treating the second gauge field as a spectator, we can obtain a $U ( 1 ) _ { k }$ （20 Chern-Simons gauge theory which models a quantum Hall system with flling fraction $\textstyle \nu = { \frac { 1 } { k } }$ and the D2-D4 intersection describes the edge state of this quantum Hal system.

Generalizing to multiple D4-brane systems, we find that the edge between $U ( N ) _ { k } \times U ( N ) _ { - k }$ and $U ( N - M ) _ { k } \times U ( N ) _ { - k }$ is dual to the $U ( M ) _ { k }$ Yang-Mills-Chern-Simons theory.

Before we continue,let us compute the entropy of the D4-brane at finite temperature. It is estimated as follows (we assume that it is extended in $( t , x , r )$ direction with the interval $0 < x < L$ . We also put the UV cut off at $r = r _ { \infty }$ ）

$$
\beta F = - S _ { D 4 } = e ^ { - \phi } T _ { 4 } \cdot L \cdot \mathrm { V o l } ( \mathbb { C P } ^ { 1 } ) \int _ { 0 } ^ { \beta } d t \int _ { r _ { 0 } } ^ { r _ { \infty } } d r \ r .
$$

This leads to the entropy

$$
S = { \frac { 2 } { 9 } } \pi N L T .
$$

We might be able to compare with the standard result $\begin{array} { r } { S = \frac { c } { 3 } \cdot \frac { \pi L } { \beta } } \end{array}$ in two dimensional CFT and find the effective central charge $\begin{array} { r } { c = \frac { 2 } { 3 } N } \end{array}$ . These degrees of freedom represent the massless modes of the open strings between $N$ $D 2$ and the probe D4-brane. It is interesting to note that this entropy is of the same order as its free field theory result, in contrast to the bulk entropy which deviates strongly from its free field result—by a factor of $\sqrt { \frac { N } { k } }$ as noted in [22].

# 2.2.2 D2⊥D8 Intersection

Now we consider the second domain-wall construction: a D8-brane that wraps the entire $\mathbb { C P } ^ { 3 }$ and attaches to $N$ D2-brane along one spatial direction:

<html><body><table><tr><td>AdS4 × CP3:</td><td>t</td><td></td><td>y</td><td>r</td><td>01 1</td><td>02</td><td>2</td><td></td><td></td></tr><tr><td>N D2:</td><td>×</td><td>×</td><td>×</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>k D6-flux:</td><td>×</td><td>×</td><td>×</td><td></td><td></td><td>×</td><td>×</td><td>×</td><td>×</td></tr><tr><td>1 D8:</td><td>×</td><td>×</td><td></td><td>×</td><td>× ×</td><td>×</td><td>×</td><td>×</td><td>×</td></tr></table></body></html>

Same as the D4 case, this system preserves 12 supersymmetries. To prove it, we can no longer use the strategy applied in D4 case earlier, since there is no M-theory lift for D8-brane in massless

IIA theory. Instead, we can count the number of supersymmetries by directly solving the Killing spinor equation. The detailed proof is in Appendix A.2.

The D8-brane world-volume action is

$$
S _ { D 8 } = - T _ { 8 } \int d ^ { 9 } \sigma e ^ { - \phi } \sqrt { - \operatorname * { d e t } ( G + 2 \pi { \cal F } ) } + 2 \pi ^ { 2 } T _ { 8 } \int C ^ { ( 5 ) } \wedge { \cal F } \wedge { \cal F } ,
$$

where $T _ { 8 } = ( 2 \pi ) ^ { - 8 }$ in the unit $\alpha ^ { \prime } = 1$ and $C ^ { ( 5 ) }$ gives the background RR-flux $\begin{array} { r } { \int _ { \mathbb { C P } ^ { 3 } } F ^ { ( 6 ) } = ( 2 \pi ) ^ { 5 } N } \end{array}$ （204号 generated by $N$ D2 branes. Integrating over the internal $\mathbb { C P } ^ { 3 }$ ， the D8 Chern-Simons term becomes

$$
S _ { D 8 } ^ { c . s } = \frac { N } { 4 \pi } \int A \wedge d A .
$$

The analysis is similar to the D4 case. The intersection between the probe D8-brane wrapped on $\mathbb { C P } ^ { 3 }$ and the stack of $N$ D2-branes creates a domain wall on the $D 2$ -brane. Since the D8- brane background induces a Chern-Simons coupling of D2-branes,15 the sum of levels of the first and second gauge group jumps across the domain wall: i.e., the gauge group $U ( N ) _ { k } \times U ( N ) _ { - k }$ changes into $U ( N ) _ { k - 1 } \times U ( N ) _ { - k }$ . Same as the D4 case, we will concentrate on the first gauge group as the edge does not affect the second one.

Due to the same reason we explained for the D4 edge, the F-string charge should be regarded as $\begin{array} { r } { \frac { \epsilon } { \overline { { k } } } } \end{array}$ in the FQHE interpretation. By rescaling the gauge field $A \to { \frac { e } { k } } A$ , we obtain the D8 ChernSimons term

$$
S _ { D 8 } ^ { c . s } = \frac { \tilde { k } _ { D 8 } } { 4 \pi } \int A \wedge d A , \qquad \mathrm { w i t h } \qquad \tilde { k } _ { D 8 } \equiv \frac { N e ^ { 2 } } { k ^ { 2 } } .
$$

If we set $N = 1$ and ignore the $U ( N ) _ { - k }$ part,we obtain an edge state which sits between a （204号 $U ( 1 ) _ { k }$ Chern-Simons gauge theory and a $U ( 1 ) _ { k - 1 }$ theory. This gives the edge state between two quantum Haliquids (QHL)with different flling factions: $\textstyle \nu = { \frac { 1 } { k } }$ and $\begin{array} { r } { \nu ^ { \prime } = \frac { 1 } { k - 1 } } \end{array}$ . Generalizing to multiple D8-brane systems, we see that the edge between two QHL with different filling fractions （204号 $\textstyle { \frac { 1 } { k } }$ and $\textstyle { \frac { 1 } { k ^ { \prime } } }$ is dual to the level-1 $U ( k - k ^ { \prime } )$ Yang-Mils-Chern-Simons theory. More generally, if we add both $M$ D4-branes and $l$ D8-branes to the $N$ D2-branes with $k$ D6-flux system, the theory changes into the $U ( N - M ) _ { k - l } \times U ( N ) _ { - k }$ Chern-Simons theory when crossing the edge.

Finally, by computing the thermal entropy of the CFT

$$
S = \frac { 2 \pi } { 2 7 } \frac { N ^ { 2 } } { k } L T ,
$$

we can find the effective central charge c= 22.

# 2.3 Holographic Action of Edge State

We analyze the holographic description of the edge states by studying the D4 and D8-brane action. We assume the finite temperature background which is dual to the $A d S _ { 4 }$ black hole.We work with the following metric by setting $z = r ^ { - 1 }$ in (2.8)

$$
d s ^ { 2 } = - \frac { H ( z ) } { z ^ { 2 } } d t ^ { 2 } + \frac { d z ^ { 2 } } { H ( z ) z ^ { 2 } } + \frac { d x ^ { 2 } + d y ^ { 2 } } { z ^ { 2 } } , H ( z ) = 1 - r _ { 0 } ^ { 3 } z ^ { 3 } .
$$

After integrating the internal $\mathbb { C P } ^ { 1 }$ , the D4-brane worldvolume action is:16

$$
S _ { D 4 } = - \alpha _ { D 4 } \int d ^ { 3 } \sigma \sqrt { - \operatorname * { d e t } { ( g _ { i j } + 2 \pi { \cal F } _ { i j } ) } } + { \frac { { \tilde { k } } _ { D 4 } } { 4 \pi } } \int A \wedge d A .
$$

Similarly, a D8-brane wrapped on $\mathbb { C P } ^ { 3 }$ has the same action as (2.22), except that $( \alpha _ { D 4 } , \tilde { k } _ { D 4 } )$ is replaced by $( \alpha _ { D 8 } , \tilde { k } _ { D 8 } )$

Thevalues of coefficient $\alpha$ for D4-brane and D8-brane are

$$
\alpha _ { D 4 } = \mathrm { V o l } ( C P ^ { 1 } ) T _ { 4 } e ^ { - \phi } \tilde { R } ^ { 5 } = \frac { N } { 4 \pi } , \qquad \alpha _ { D 8 } = \mathrm { V o l } ( C P ^ { 3 } ) T _ { 8 } e ^ { - \phi } \tilde { R } ^ { 9 } = \frac { N ^ { 2 } } { 1 2 \pi k } .
$$

The levels $\tilde { k }$ of the Chern-Simons terms are

$$
\tilde { k } _ { D 4 } = \frac { e ^ { 2 } } { k } , \qquad \tilde { k } _ { D 8 } = \frac { N e ^ { 2 } } { k ^ { 2 } } .
$$

Since the D2 $\perp$ D4 and D2 $\perp$ D8 systems provide the same action to model the edge state, we will analyze the two systems simultaneously using the action (2.22) with generic parameter $( \alpha , k )$ . Plugging their values for D4 or D8-brane then produces the result for the corresponding system.

# 2.3.1 Gauge Choice and Boundary Term

There are two codimension-1 boundaries in our system: $z = 0$ (the position of the edge state) and $z = z _ { h } = 1 / r _ { 0 }$ (the position of the horizon).17 The $z = 0$ boundary is particularly important; 18 as we wil explain, it requires the addition of a boundary term for the Chern-Simons action. The contribution from the surface term is crucial to the holographic computation of the conductivity.

The existence of boundary creates two problems. First, it breaks the gauge invariance of the Chern-Simons term: under the gauge transformation $\delta A = d \chi$ （204号

$$
\delta _ { \chi } S _ { C S } = \frac { \tilde { k } } { 4 \pi } \int d \chi \wedge d A = - \frac { \tilde { k } } { 4 \pi } \int _ { \Sigma ( z = 0 ) } d t d x \chi F _ { t x } \neq 0 .
$$

This means that the gauge symmetry is preserved only if we restrict to the subspace with the flat connection $F _ { t x } = 0$ at $z = 0$

Second, the on-shell variation of Chern-Simons action has both $\delta A _ { t }$ and $\delta A _ { x }$ term on the （20 $z = 0$ boundary:

$$
\delta S \vert _ { o n - s h e l l } = \frac { \tilde { k } } { 4 \pi } \int _ { \Sigma ( z = 0 ) } d t d x ( - A _ { x } \delta A _ { t } + A _ { t } \delta A _ { x } )
$$

However,only one of the two terms should appear if $A _ { t }$ and $A _ { x }$ are considered as a pair of canonical variables with respect to $z$ ：

These two problems are improved simultaneously by adding a boundary term as in [33] at $z = 0$ ：

$$
S _ { b d y } = \eta \frac { \tilde { k } } { 4 \pi } \int _ { \Sigma ( z = 0 ) } d t d x A _ { t } A _ { x } \qquad \mathrm { w i t h } \qquad \eta = \pm 1 .
$$

First,after including the boundary term, the full action transforms under $\delta A = d \chi$ as

$$
\delta _ { \chi } ( S _ { C S } + S _ { b d y } ) = - \frac { \tilde { k } } { 4 \pi } \int _ { \Sigma ( z = 0 ) } d t d x \chi \left[ ( 1 + \eta ) \partial _ { t } A _ { x } + ( - 1 + \eta ) \partial _ { x } A _ { t } \right] .
$$

Even though we need to assume $\partial _ { t } A _ { x } = 0$ when $\eta = 1$ (or $\partial _ { x } A _ { t } = 0$ when $\eta = - 1$ ),we can still realize any non-vanishing electric flux $F _ { t x } \neq 0$

The second problem is resolved similarly. The on-shell variation of the total action contains （204号 $\delta A _ { t }$ or $\delta A _ { x }$ term:

$$
\delta ( S | _ { o n - s h e l l } + S _ { b d y } ) = \left\{ \begin{array} { l l } { \displaystyle \frac { \tilde { k } } { 2 \pi } \int _ { \Sigma ( z = 0 ) } d t d x ( A _ { t } \delta A _ { x } ) , \qquad } & { \eta = 1 ; } \\ { \displaystyle - \frac { \tilde { k } } { 2 \pi } \int _ { \Sigma ( z = 0 ) } d t d x ( A _ { x } \delta A _ { t } ) , \qquad } & { \eta = - 1 . } \end{array} \right.
$$

In our later computation of the Hall conductivity, we will set $\eta = - 1$

# 2.4Holographic Computation of Hall Conductivity via Perpendicular Edges

# 2.4.1 Set-up

The left part of Fig. 4 shows the standard experimental setup to measure the quantum Hall conductance: an $\vec { E }$ -field runs across the $y$ -direction and the Hall current flows along the two edge states in the perpendicular $x$ -direction. The right part depicts our D-brane configuration to model the two edge states: the probe D4-brane or D8-brane bends into an arch-bridge shape; its two ends are attached to the boundary CFT and form the two edge states. Near the boundary （204号 $z = 0$ , the system looks like a pair of parallel D4 and $\overline { { \mathrm { D 4 } } }$ (or D8 and $\overline { { \mathrm { D } 8 } }$ ). In high temperature regime, the single bending-brane will break into a pair of parallel D4 and $\overline { { \mathrm { D 4 } } }$ (or D8 and $\overline { { \mathrm { D } 8 } }$ ） that end at the horizon as in [32], but the analysis can be done essentially in the same way.

The probe bending D-brane is described by the world-volume coordinates $( \sigma ^ { 0 } , \sigma ^ { 1 } , \sigma ^ { 2 } ) =$ $( t , x , y )$ . Its profle is specified by the function $z = z ( y )$ ，with $\begin{array} { r } { - \frac { L } { 2 } \leq y \leq \frac { L } { 2 } } \end{array}$ . This is a holographic dual of the two parallel edge states separated by the distance $L$

![](images/ac769acc3380fc5d6cbc9c18048a3bdd124404efd56f91236dd5d9d3f2b1d837.jpg)  
Figure 4: A bending brane that models the pair of edge states perpendicular to $\vec { E }$ -field.

Since we are interested in computing the Hall conductance, we do not apply $\vec { E }$ -field along the edge state (i.e. $E _ { x } = 0$ ). Thus we can always choose

$$
A _ { t } = A _ { t } ( y ) , \qquad A _ { x } = A _ { x } ( y ) , \qquad A _ { y } = 0 .
$$

up to a gauge transformation. The probe D-brane action with the boundary term (2.27) is then simply

$$
\begin{array} { r l r } { \mathrm { ~  ~ \Gamma ~ } } & { = } & { - \alpha \displaystyle \int d t d x d y \frac { 1 } { z ^ { 3 } } \sqrt { H + z ^ { \prime 2 } + z ^ { 4 } H F _ { x y } ^ { 2 } - z ^ { 4 } F _ { t y } ^ { 2 } } + \frac { \tilde { k } } { 4 \pi } \displaystyle \int d t d x d y \left( A _ { x } \partial _ { y } A _ { t } - A _ { t } \partial _ { y } A _ { x } \right) } \\ & { } & { + \eta \displaystyle \frac { \tilde { k } } { 4 \pi } \left( \displaystyle \int _ { \mathrm { b d y - 1 } } d t d x A _ { t } A _ { x } + \displaystyle \int _ { \mathrm { b d y - 2 } } d t d x A _ { t } A _ { x } \right) \qquad ( \boldsymbol { \Sigma } ) } \end{array}
$$

with “bdy- $1 ^ { \mathfrak { v } }$ at $\begin{array} { r } { y = - \frac { L } { 2 } } \end{array}$ and “bdy- $2 ^ { \mathfrak { p } }$ at $\begin{array} { r } { y = \frac { L } { 2 } } \end{array}$

Its equations of motion are

$$
\begin{array} { l } { \displaystyle \partial _ { x } \left( \frac { \alpha z H F _ { x y } } { \sqrt { D } } \right) - \partial _ { t } \left( \frac { \alpha z F _ { t y } } { \sqrt { D } } \right) = 0 , \qquad \displaystyle \partial _ { y } \left( \frac { \alpha z H F _ { x y } } { \sqrt { D } } \right) + \frac { \tilde { k } } { 2 \pi } F _ { t y } = 0 , } \\ { \displaystyle \partial _ { y } \left( \frac { \alpha z F _ { t y } } { \sqrt { D } } \right) + \frac { \tilde { k } } { 2 \pi } F _ { x y } = 0 , } \\ { \displaystyle 3 z ^ { - 4 } \sqrt { D } - \frac { 1 } { \sqrt { D } } ( 2 H F _ { x y } ^ { 2 } - 2 F _ { t y } ^ { 2 } ) + \partial _ { y } \left( \frac { z ^ { \prime } } { z ^ { 3 } \sqrt { D } } \right) = 0 . } \end{array}
$$

where $D = H + z ^ { \prime 2 } + z ^ { 4 } H F _ { x y } ^ { 2 } - z ^ { 4 } F _ { t y } ^ { 2 }$ .At zero temperature,italos aalytical solutiosas shown in the appendix B. However,to obtain the Hall conductance, it is enough to compute the conserved charges. The bulk conserved charges corresponding to the translation symmetries of $A _ { t }$ and $A _ { x }$ are

$$
Q _ { A _ { t } } = \alpha \frac { z F _ { y t } } { \sqrt { D } } + \frac { \tilde { k } } { 2 \pi } A _ { x } , Q _ { A _ { x } } = - \alpha \frac { z H F _ { y x } } { \sqrt { D } } - \frac { \tilde { k } } { 2 \pi } A _ { t } .
$$

# 2.4.2 Fractional Quantum Hall Conductivity

The conserved currents on the boundary are charge density $\rho$ and current density $j$ . Following the arguments [31, 32], they are defined as

$$
\rho = \frac { \delta S } { \delta A _ { t } } \Big | _ { z = 0 } , \qquad j = \frac { \delta S } { \delta A _ { x } } \Big | _ { z = 0 } .
$$

In the holographic computation of the currents, we need to specify the boundary interactior Recall that the two choices of $\eta$ correspond to different boundary conditions of $A$ ：

$$
\begin{array} { r l r l r l r l } & { \delta A _ { x } | _ { b d y } = 0 } & & { \mathrm { a n d } \quad } & { \delta A _ { t } | _ { b d y } \mathrm { f r e e } } & { \quad } & { \mathrm { i f } \quad \eta = 1 } \\ & { \delta A _ { t } | _ { b d y } = 0 } & & { \mathrm { a n d } \quad } & { \delta A _ { x } | _ { b d y } \mathrm { f r e e } } & { \quad } & { \mathrm { i f } \quad \eta = - 1 . } \end{array}
$$

Since we are interested in computing the Hall conductance, we need to choose

$$
\eta = - 1
$$

so that on the boundary, $A _ { x }$ is allowed to vary and $A _ { t }$ is fixed. The boundary values of $A _ { t }$ correspond to the electric static potential and their difference is determined by the $\vec { E }$ -field:

$$
A _ { t } | _ { b d y - 2 } - A _ { t } | _ { b d y - 1 } = V _ { y } = E _ { y } L
$$

There is an additional subtlety for high temperature regime: as the temperature is increased, the horizon $z = z _ { h }$ moves closer to the tip of the bending-brane and eventually forces the single bending-brane to break into a pair of paralel D-branes that end at the horizon. In such a case, we need to also specify the boundary condition for the $z = z _ { h }$ boundary of the probe D-brane. As claimed in [32,31], the most natural one is simply $\delta A | _ { z = z _ { h } } = 0$ : the boundary condition at the horizon does not influence the physics at the spatial infinity. We will adopt this argument throughout this work.

The charge and current density at each edge are then

$$
\rho = Q _ { A _ { t } } , \qquad j _ { x } = Q _ { A _ { x } } + \frac { \tilde { k } } { 2 \pi } A _ { t } | _ { b d y } .
$$

Since the edge is (1+1)-dimensional, the current is equal to the current density: $I = j$ . What is measured experimentally is the net current along both edges; and since currents from the two edges flow in opposite directions, the net current along $x$ -direction is

$$
I _ { x } = I _ { b d y - 2 } - I _ { b d y - 1 } = j _ { b d y - 2 } - j _ { b d y - 1 } = { \frac { \tilde { k } } { 2 \pi } } ( A _ { t } | _ { \mathrm { b d y - 2 } } - A _ { t } | _ { \mathrm { b d y - 1 } } ) = { \frac { \tilde { k } } { 2 \pi } } V _ { y }
$$

This gives the Hall conductance

$$
G _ { x y } = \frac { I _ { x } } { V _ { y } } = \frac { \tilde { k } } { 2 \pi } = \frac { \tilde { k } } { h } .
$$

In the last step we restored $\hbar$ which has been set to 1.

Note that (2.38) is the conductance for the entire (2+1)-dimensional quantum Hall system, and in this dimension, the conductance is equal to the conductivity:

$$
\sigma _ { x y } = { \frac { j _ { x } } { E _ { y } } } = { \frac { j _ { x } \cdot L } { E _ { y } \cdot L } } = { \frac { I _ { x } } { V _ { y } } } = G _ { x y } = { \frac { \tilde { k } } { h } } .
$$

Now we translate the result (2.39) into the quantum Hall effect. For D4-brane case, recall that the D4-brane models the edge states of a QHL with filing fraction $\textstyle \nu = { \frac { 1 } { k } }$ and plugging $\begin{array} { r } { ( \tilde { k } , \nu ) _ { D 4 } = ( \frac { e ^ { 2 } } { k } , \frac { 1 } { k } ) } \end{array}$ into (2.39) reproduces the correct fractional quantum Hall conductivity:19

$$
\sigma _ { x y } = \frac { \nu e ^ { 2 } } { h } .
$$

Notice that our holographic calculation of the quantum Hall conductivity does not depend on the temperature. This is expected since in the Chern-Simons description of the QHE the excitation gap is infinitely large thus no quasi-particle (including excitation into higher Landau levels) can be thermally excited. This is the reason that we can measure the quantized Hall conductivity with remarkable accuracy.

On the other hand, the $l$ D8-branes model the edge state that separates two QHL with diferent filling fractions $\textstyle \nu = { \frac { 1 } { k } }$ and $\begin{array} { r } { \nu ^ { \prime } = \frac { 1 } { k - l } } \end{array}$ ，setting $N = 1$ .By preparing two edges as in the D4 case,we can realize a setup in which the QHL with $\nu$ is surrounded by the QHL with $\nu ^ { \prime }$ from the both left and right sides. Then we can consider the Hall conductivity $\tilde { \sigma } _ { x y }$ for the QHL with $\nu$ under this circumstance. Plugging $\begin{array} { r } { \tilde { k } _ { D 8 } = \frac { e ^ { 2 } } { k ^ { 2 } } } \end{array}$ into (2.39) then predicts that

$$
{ \tilde { \sigma } } _ { x y } = { \frac { l e ^ { 2 } } { 2 \pi k ^ { 2 } } } = { \frac { l \nu ^ { 2 } e ^ { 2 } } { h } } \simeq { \frac { | \nu ^ { \prime } - \nu | e ^ { 2 } } { h } } ,
$$

where we took into account that $k$ is taken to be large in the supergravity description of the $A d S _ { 4 } / C F T _ { 3 }$ duality. This result can be naturally understood if we remember the difference of the current between the left and right of the interface does contribute to the conductivity in these generic examples.

It is also possible to see that the lon

# 2.5 Alternative Computation of Hall Conductivity via Parallel Edges

# 2.5.1 Set-up:Edge D-brane Parallel to $\vec { E }$

In the previous subsection,we obtain the current density $j _ { x }$ by computing the current flowing along the two edges perpendicular to the field $E _ { y }$ . Experimentally, one actually measures $j _ { x }$ （20 as the current density flowing out of the edge parallel to $E _ { y }$ ，as shown in the left part of Fig. 5. Therefore we can also construct an edge state parallel to $E _ { y }$ , and compute $j _ { x }$ as the current density perpendicular to the edge state.20

Fig. 5 illustrates the brane construction of the edge state parallel to the $\vec { E }$ -field.The graph on the left side highlights the two edge states paralel to the $\vec { E }$ -field. The current $j _ { y }$ （204号 flows along these edge states and $j _ { x }$ flows across them. The graph on the right depicts an infinite D4-brane extending to the horizon and intersecting with D2-brane along $y$ -direction: this (1+1)-dimensional intersection models the edge state shown on the left.

![](images/58a7655d19937806a5e5cab6a194d37cd0e4213d1de65c3785889d9511eb9fdd.jpg)  
Figure 5: An infinite brane that models the single edge that is parallel to the $\vec { E }$ -field.

The continuity equation relates $j _ { x }$ to $\rho$ (charge density inside the edge） and $j _ { y }$ (current density along the edge):

$$
j _ { x } = - \left( { \frac { \partial \rho } { \partial t } } + { \frac { \partial j _ { y } } { \partial y } } \right) .
$$

To compute $\rho$ and $j _ { y }$ holographically, we can model this edge by a single D4-brane (or D8- brane）wrapped on $\mathbb { C P } ^ { 1 }$ ， intersecting with D2-brane along $y$ -direction. This construction is actually simpler than the previous one: since we only need to compute the current flowing out of one edge,it's enough to have a single brane that extends all the way to the horizon. Notice that even in this case we assume there are two edges which connect in the bulk or which end at the black hole horizon so that the electric current comes from one of them and flows into the other.

The D4-braneworld-volume action is

$$
S _ { D 4 } = - \alpha \int d t d y d z \frac { 1 } { z ^ { 3 } } \sqrt { 1 + z ^ { 4 } H ( z ) F _ { y z } ^ { 2 } - z ^ { 4 } F _ { t z } ^ { 2 } - z ^ { 4 } H ( z ) ^ { - 1 } F _ { t y } ^ { 2 } } + \frac { \tilde { k } } { 4 \pi } \int A \wedge d A .
$$

The full equations of motion are

$$
\begin{array} { l } { \partial _ { y } \left( \displaystyle \frac { \alpha z H F _ { y z } } { \sqrt { \tilde { D } } } \right) - \partial _ { t } \left( \displaystyle \frac { \alpha z F _ { t z } } { \sqrt { \tilde { D } } } \right) + \displaystyle \frac { \tilde { k } } { 2 \pi } F _ { t y } = 0 , } \\ { \partial _ { z } \left( \displaystyle \frac { \alpha z H F _ { y z } } { \sqrt { \tilde { D } } } \right) + \partial _ { t } \left( \displaystyle \frac { \alpha z H ^ { - 1 } F _ { t y } } { \sqrt { \tilde { D } } } \right) + \displaystyle \frac { \tilde { k } } { 2 \pi } F _ { t z } = 0 , } \\ { \partial _ { z } \left( \displaystyle \frac { \alpha z F _ { t z } } { \sqrt { \tilde { D } } } \right) + \partial _ { y } \left( \displaystyle \frac { \alpha z H ^ { - 1 } F _ { t y } } { \sqrt { \tilde { D } } } \right) + \displaystyle \frac { \tilde { k } } { 2 \pi } F _ { y z } = 0 . } \end{array}
$$

where $\dot { D } \equiv 1 + z ^ { 4 } H ( z ) F _ { y z } ^ { 2 } - z ^ { 4 } F _ { t z } ^ { 2 } - z ^ { 4 } H ( z ) ^ { - 1 } F _ { t y } ^ { 2 }$ . At zero temperature, it allows analytical solutions as shown in Appendix C.

# 2.5.2 Hall Conductivity from A Single Edge

The variation of the on-shell action gives the boundary currents

$$
\rho = - \frac { \alpha z F _ { t z } } { \sqrt { \tilde { D } } } + \frac { \tilde { k } } { 2 \pi } A _ { y } , \qquad j _ { y } = \frac { \alpha z F _ { y z } } { \sqrt { \tilde { D } } } ,
$$

almost in the same way as we did in (2.36). Note that for the $z = z _ { h }$ boundary of the probe D-brane, we again used the assumption $\delta A | _ { z = z _ { h } } = 0$ as in [32].

Then we plug these into (2.42） and finally we obtain by using (2.45)

$$
j _ { x } = - \frac { \tilde { k } } { 2 \pi } \partial _ { y } A _ { t } = \frac { \tilde { k } } { 2 \pi } E _ { y } ,
$$

where we assumed $\partial _ { t } A _ { y } = 0$ using the argument of gauge invariance in (2.28). This correctly reproduces the Hall conductivity

$$
\sigma _ { x y } = \frac { \tilde { k } } { 2 \pi } = \frac { \tilde { k } } { h } .
$$

Thus we reproduced the previous results (2.39) from this independent argument.

# 3 Holography of Pure Chern-Simons Theory and Topological Entanglement Entropy

So far we have studied the supersymmetric Chern-Simons theory since it can be holographically realized in a clear way. This theory includes matter fields in addition to the Chern-Simons gauge theory and is a dynamical CFT. However, if we have in mind the application to topological insulators in condensed matter physics, we need a mass gapped gauge theory. In this section we will consider a (2+1)-dimensional gauge theory which flows into a pure Chern-Simons gauge theory. We will also present its holographic dual. A holographic background dual to a pure $N = 1$ Chern-Simons model has already been given in [34] and our model shares several similar properties such as the level-rank duality.

# 3.1A Holographic Dual to Pure Chern-Simons and Level-Rank Duality

We start with the $\mathcal { N } = 4$ super Yang-Mills in four dimensions and compactify one of its three spatial directions (denoted by $\theta$ ). Then we impose the anti-periodic boundary condition on $\theta$ ， which makes the fermions massive. The quantum corrections give a mass to scalar fields and in the end we obtain a pure Yang-Mills theory in $( 2 + 1 )$ dimensions in the IR limit.This theory is dual to the $A d S _ { 5 }$ soliton (or double Wick-rotated $A d S _ { 5 }$ black brane) in IIB string theory [24]

$$
d s ^ { 2 } = R ^ { 2 } \frac { d r ^ { 2 } } { f ( r ) r ^ { 2 } } + \frac { r ^ { 2 } } { R ^ { 2 } } ( - d t ^ { 2 } + f ( r ) d \theta ^ { 2 } + d x ^ { 2 } + d y ^ { 2 } ) + R ^ { 2 } d \Omega _ { 5 } ^ { 2 } ,
$$

where $\begin{array} { r } { f ( r ) = 1 - \left( \frac { r _ { 0 } } { r } \right) ^ { 4 } } \end{array}$ . The coordinate $\theta$ is compactified as $\theta \sim \theta + L$ ，where $\begin{array} { r } { L = { \frac { \pi R ^ { 2 } } { r _ { 0 } } } } \end{array}$ , so that the total geometry becomes smooth. The cycle $\partial _ { \theta }$ shrinks at $r = r _ { 0 }$ . Thus the two-dimensional space spanned by $( r , \theta )$ is topologically a two-dimensional disk $D _ { 2 }$ . The boundary of the disk is at $r = \infty$ and this is the boundary of the AdS. The dual gauge theory lives in $R ^ { 1 , 2 }$ whose coordinate is $( t , x , y )$

Now we would like to deform this theory so that it includes the Chern-Simons term. Remember the WZ-term of a D3-brane,

$$
{ \frac { 1 } { 4 \pi } } \int _ { D 3 } \chi F \wedge F = - { \frac { 1 } { 4 \pi } } \int _ { D 3 } d \chi \wedge A \wedge F ,
$$

where $\chi$ is the axion field in IB theory. If we assume the background axion field $\begin{array} { r } { \chi = \frac { k } { L } \theta } \end{array}$ ，this leads to the CS coupling

$$
{ \frac { k } { 4 \pi } } \int _ { R ^ { 1 , 2 } } A \wedge F .
$$

In this way, we get a Maxwell-Chern-Simons theory which flows into the level $k$ pure ChernSimons theory in the IR. This argument can be easily generalized to $N$ D3-branes and we get the non-abelian Chern-Simons term $\begin{array} { r } { \frac { k } { 4 \pi } \int _ { R ^ { 1 , 2 } } \mathrm { T r } \left( A \wedge d A + \frac 2 3 A ^ { 3 } \right) } \end{array}$ ：

The axion field $\begin{array} { r } { \chi = \frac { k } { L } \theta } \end{array}$ can be regarded as $k$ D7-branes located at $r = r _ { 0 }$ . Therefore we find that the $U ( N ) _ { k }$ Yang-Mills-Chern-Simons theory is holographically dual to this $A d S _ { 5 }$ soliton background with the $k$ D7-branes (see Fig. 6). The IR limit of the CFT side is dual to the small $r$ region of the dual background and this is given by the D7-brane theory. Due to the Chern-Simons term $\textstyle { \frac { N } { 4 \pi } } \int _ { R ^ { 3 } } A \wedge F$ from the RR 5-form flux, we get $U ( k ) _ { N }$ pure Chern-Simons theory. Thus this holography in the low energy limit is equivalent to the level-rank duality of the Chern-Simons theory. Indeed, the level-rank duality becomes more direct for $U ( N ) _ { k }$ than for （204号 $S U ( N ) _ { k }$ as shown in [35]. Indeed, we can prove the following identity for the partition functions on $S ^ { 3 }$ [35]:

$$
Z ( S ^ { 3 } , U ( N ) _ { k } ) = Z ( S ^ { 3 } , U ( k ) _ { N } ) , \qquad Z ( S ^ { 3 } , S U ( N ) _ { k } ) = \sqrt { \frac { k } { N } } Z ( S ^ { 3 } , S U ( k ) _ { N } ) .
$$

The reason that the theory on the D7-branes should be regarded as a pure Chern-Simons theory without the Yang-Mills term can be understood by looking at the excitations on them. In the dual gauge theory side (the D3-brane theory), the mass gap due to the Kaluza-Klein compactification is given by

$$
m _ { K K } \sim \frac { 1 } { L } \sim \frac { r _ { 0 } } { R ^ { 2 } } .
$$

On the other hand, the gravity theory is given by the IIB supergravity and the D7-brane theory. In the presence of the ordinary Yang-Mills term obtained from the D-brane action,the D7-brane theory has a mass gap due to the Chern-Simons term, which is estimated as21

$$
m _ { g a u g e } \sim N \frac { r _ { 0 } \alpha ^ { \prime 2 } } { R ^ { 6 } } \sim \frac { m _ { K K } } { g _ { Y M } ^ { 2 } } \gg m _ { K K }
$$

![](images/809dda9fc4e89332a907942a0cbc9acfedc0316ac8595834bbca7af96f0df000.jpg)  
Figure 6: D3-D7 construction that generates a level-rank duality system: the D3-brane wraps the $\theta$ -direction and generates a $U ( N ) _ { k }$ Yang-Mills-Chern-Simons theory. The bulk geometry is a $A d S _ { 5 }$ soliton with additional $k$ axion flux, which are sourced by $k$ D7-branes sitting at $r = r _ { 0 }$ （20 where $\theta$ -circle shrinks to zero. The IR limit of D3-brane theory ( $U ( N ) _ { k }$ Chern-Simons theory) is dual to the D7-brane theory which is a $U ( k ) _ { N }$ Chern-Simons theory.

Thus the excitation on the D7-branes can be neglected and it reduces to the pure Chern-Simons theory.

# 3.2 Relation to Quantum Hall Effect

Now we would like to examine the gauge theory dual to the gravity background (3.48) with $k$ （20   
D7-branes.22

To interpret our model as one for the quantum Hall effect, we need to couple it to an external gauge field. To this end, we assume that the background RR 2-from field has the form

$$
B _ { R R } = A _ { R R } \land d \tilde { \theta } ,
$$

where $A _ { R R }$ is a 1-form in $R ^ { 1 , 2 }$ and will serve as the external gauge field. We define $\begin{array} { r } { \bar { \theta } \equiv \frac { 2 \pi } { L } \theta } \end{array}$ so that the period of $\tilde { \theta }$ is $2 \pi$

The relevant RR-coupling on D3-branes reads

$$
\frac { 1 } { 4 \pi ^ { 2 } } \int _ { D 3 } B _ { R R } \wedge \mathrm { T r } F = \frac { 1 } { 2 \pi } \int _ { R ^ { 1 , 2 } } A _ { R R } \wedge \mathrm { T r } F .
$$

Therefore in the IR limit, the QFT side becomes the Chern-Simons theory coupled to an external gauge field

$$
S _ { D 3 } = \frac { k } { 4 \pi } \int \mathrm { T r } \left( A \wedge d A + \frac 2 3 A \wedge A \wedge A \right) + \frac { 1 } { 2 \pi } \int A _ { R R } \wedge \mathrm { T r } F ,
$$

This is a non-abelian version of the standard Chern-Simons description of the quantum Hall effect.

It is also important to identify the anyons in this system. A D5-brane wrapped on $S ^ { 5 }$ is the baryon vertex in $A d S _ { 5 } \times S ^ { 5 }$ [36]. Due to the string creation,it comes with $N$ F-strings stretching between the D5 and $N$ D3-branes. The F-strings induce a unit charge for each $U ( 1 )$ gauge theory in $U ( 1 ) ^ { N } \subset U ( N )$ . Thus according to the same argument as in (2.11)，when two baryons are interchanged, the full wave-function acquires a phase factor $e ^ { \frac { \pi i N } { k } }$ , which means that the baryons are anyons for generic values of $N$ ：

Now we would like to compute the Hall conductivity in the holographic dual gravity side. Usually, the D7-branes extend to the boundary of AdS [37]. However, in our case, they are localized at the IR regin $r = r _ { 0 }$ . Therefore we can replace them with a background axion fux $\begin{array} { r } { \chi = \frac { k } { L } \theta } \end{array}$ instead of treating them as probe D-branes. Below we are only interested in the leading order effects produced by this axion flux so we will not take the backreaction to the metric, dilaton and fluxes into account. Please refer to Appendix. D for the calculation of Hall conductivity in the probe D7-brane analysis.

The holographic current is computed as the on-shell variation of the action:

$$
j ^ { \mu } = \frac { \delta S _ { I I B } } { \delta A _ { R R \mu } } \Bigr | _ { b d y } ,
$$

where $A _ { R R }$ is the 1-form that comes from the RR 2-form field $B _ { R R }$ via (3.54) and serves as the external gauge field in the D3-brane system. $S _ { I I B }$ is the type IIB supergravity action evaluated on-shell in the presence of D7-brane flux.

After we integrate over $S ^ { 5 }$ , the action which involves the $N S$ and $R R$ 3-form flux $H _ { N S }$ and $H _ { R R }$ can be written as follows (in the convention of [46] with $\alpha ^ { \prime } = 1$ ）

$$
\qquad \sb { t f l u x } = - \frac { \sb { R } \sp { 5 } } { 2 \sp { 4 } ( 2 \pi ) \sp { 4 } } \int d \sp { \tilde { s } } x \sqrt { - G } \left( { g _ { s } \sp { - 2 } } \vert H _ { N S } \vert \sp { 2 } + \vert H _ { R R } - \chi H _ { N S } \vert \sp { 2 } \right) - \frac { \sb { N } } { ( 2 \pi ) \sp { 3 } } \int B _ { N S } \wedge H _ { R R } \nonumber
$$

where the final term comes from the Chern-Simons term $\begin{array} { r } { - \frac { 1 } { 4 \kappa ^ { 2 } } \int C _ { 4 } \wedge H _ { N S } \wedge H _ { R R } } \end{array}$ together with the cross terms in $\begin{array} { r } { - \frac { 1 } { 8 \kappa ^ { 2 } } \int | \tilde { F } _ { 5 } | ^ { 2 } } \end{array}$ after compactifying on $S ^ { 5 }$ with 5-from flux (see also [38]).

Since the background field of quantum Hall effect on D3-branes is $F _ { R R } = d A _ { R R }$ ， we assume $B _ { N S } = 0$ in the solution we are looking for. This is consistent with equations of motion if

$$
\ast _ { 5 } H _ { R R } = \frac { 3 2 \pi ^ { 2 } N } { R ^ { 5 } k } F _ { R R } ,
$$

to the leading order of $k$ ； here $^ { * } 5$ denotes the Hodge dual in the 5D spacetime. Plugging this into the remaining action of ${ { H } _ { R R } }$ ： $\begin{array} { r } { S _ { H _ { R R } } = - \frac { R ^ { 5 } } { 2 ^ { 4 } ( 2 \pi ) ^ { 4 } } \int H _ { R R } \wedge * _ { 5 } H _ { R R } } \end{array}$ and integrating over $\theta$ we

finally obtain

$$
S _ { I I B } = \frac { N } { 4 \pi k } \int F _ { R R } \wedge F _ { R R } .
$$

Since this topological term leads to the boundary Chern-Simons term in the AdS/CFT procedure

$$
S _ { b d y } = \frac { N } { 4 \pi k } \int A _ { R R } \wedge F _ { R R } ,
$$

the $x$ component of (3.57） gives $\begin{array} { r } { j _ { x } = \frac { N } { k h } E _ { y } } \end{array}$ . Thus we find the fractional quantum Hall conductivity

$$
\sigma _ { x y } = \frac { N } { k h } .
$$

This clearly agrees with what we find from (3.56). Note that the quantization of D7-brane and D3-brane charges lead to the fractional quantization of the Hall conductivity in (3.62).

In this formalism，we can also easily see from (3.61） that the longitudinal conductivity vanishes

$$
\sigma _ { x x } = 0 ,
$$

as expected in the standard FQHE.

# 3.3 Topological Entanglement Entropy

The topological entanglement entropy $S _ { t o p }$ [25,26] is defined as the finite part of the entanglement entropy

$$
S _ { A } = \gamma \frac { l } { a } + S _ { t o p } \ ,
$$

where $a$ is the UV cutoff and $\gamma$ a certain numerical factor proportional to the number of UV degrees of freedom.The entanglement entropy $S _ { A }$ is defined as the von-Neumann entropy when we trace out a subsystem $A$ on a time-slice.We assume $A$ is a two-dimensional disk in a timeslice. $l$ is the length of the boundary $\partial A$ of $A$ . When the theory has a mass gap, the quantity $S _ { t o p }$ can be shown to be invariant under a continuous deformation of the region $A$ [25, 26].

Conformal field theories such as the $\mathcal { N } = 6$ Chern-Simons theory do not have any mass gap, so the finite part of $S _ { A }$ for these theories is not a topological invariant. In contrast, the pure Yang-Mills theory is a good example where we can define $S _ { t o p }$ non-trivially. Indeed we can show that it becomes the log of the partition function $Z ( S ^ { 3 } )$ of Chern-Simons theory on $S ^ { 3 }$ [33] using the standard surgery method [5].

On the other hand, the holographic calculation of topological entanglement entropy has recently been attempted in [39] employing the holographic formula of the entanglement entropy [40]. However, $S _ { t o p }$ for the (2+1)-dimensional Yang-Mills theory without Chern-Simons term turns out to be trivial. Therefore here we would like to see how the holographic computation of the topological entanglement entropy is modified in the presence of the Chern-Simons term.

In the holographic calculation [40],we introduce the (negative) deficit angle $\delta = 2 \pi ( 1 - n )$ on the $\partial A$ at $r = \infty$ . Then we extend this deficit angle surface toward the bulk AdS,called （20 $\gamma$ . Since the entanglement entropy is defined by $\begin{array} { r } { S _ { A } = - \frac { \partial } { \partial n } \log Z _ { n } } \end{array}$ ，where $Z _ { n }$ is the partition function on the manifold with the deficit angle $\delta = 2 \pi ( 1 - n )$ , in our setup we obtain

$$
S _ { A } = \frac { \mathrm { A r e a } ( \gamma ) } { 4 G _ { N } } + S _ { D 7 } ,
$$

where the part $S _ { D 7 }$ is the contribution of $k$ D7-branes. The action principle tells us that $\gamma$ （204号 is the minimal area surface [41, 4O] whose boundary coincides with $\partial A$ .It is clear from this holographic expression (3.65) that the topological entanglement entropy is given by $S _ { D 7 }$ as the Chern-Simons term appears due to the D7-branes.

Since we are interested in the (2+1)-dimensional Yang-Mils-Chern-Simons theory, the KaluzaKlein modes need to be negligible. This requires that the size of region $A$ be much larger than the compactified radius $L$ . When there is no D7-brane, the surface $\gamma$ ends at the bubble wall $r = r _ { 0 }$ （20 as shown in [42,43,39]. In our case with D7-branes,and with their backreactions neglected, the deficit angle surface $\gamma$ is extended into the (2+1)-dimensional theory on the $k$ D7-branes. Since the large $N$ limit corresponds to the large level limit,the D7-brane theory becomes the classical Chern-Simons theory. Then, the AdS/CFT tels us that $S _ { t o p }$ is given by $S _ { D 7 }$ ,i.e.the topological entanglement entropy of $U ( k ) _ { N }$ Chern-Simons theory. Using the level-rank duality, this reproduces the $S _ { t o p }$ of the original CS theory. In this way, we find how to reproduce the correct topological entanglement entropy via AdS/CFT.

If we reduce the size of the subsystem $A$ , eventually, the surface $\gamma$ separates from the the tip $r = r _ { 0 }$ . In the absence of D7-branes, this is interpreted as the confinement/deconfinement transition as the smaller size of $A$ probes more UV region of the gauge theory [42, 43]. Indeed the derivative of the entanglement entropy $S _ { A }$ jumps under this transition. In our case with D7-branes, the topological term $S _ { t o p }$ also disappears when $A$ gets enough small. It is interesting to confirm by direct calculations in specific models.

It would also be intriguing to find the backreacted geometry and compute $S _ { t o p }$ from purely bulk calculations. However, this seems to be not straightforward since the direct Chern-Simons result show the behavior (using the series expansion formula in [44] of $Z ( S ^ { 3 } )$ ））

$$
S _ { t o p } \sim - \frac { k ^ { 2 } } { 2 } \log N ,
$$

in the large $N$ limit with $k$ kept finite. This suggests that this is not obtained in the tree level supergravity. Finally we would like to mention that we can discuss the holographic Wilson-loops in exactly the same way.

# 3.4 Edge States

Since our holographic model is completely gapped in the low energy, it is interesting to see how to add some dynamical degrees of freedom in the UV. One of the best examples are the edge states,which we have already discussed in the $\mathcal { N } = 6$ Chern-Simons theory. The edge state which appears in the interface between $U ( N ) _ { k }$ and $U ( N + 1 ) _ { k }$ is described by a D3-brane which stretches from $r = \infty$ to $r = r _ { 0 }$ and wraps the $\theta$ cycle. On the other hand, the edge which appears in the interface between $U ( N ) _ { k }$ and $U ( N ) _ { k + 1 }$ is described by a D7-brane which stretches from $r = \infty$ to $r = r _ { 0 }$ and wraps the $S ^ { 5 }$ ：

First consider the edge state generated by D3-branes. In the dual gravity side, the $k$ D7- branes are regarded as the background axion source; thus the holographic edge state is described by the $U ( 1 ) _ { k }$ DBI-Chern-Simons theory living on the edge D3-brane that wraps on $\theta$ . The Hall conductivity can then be computed in the same way as in section 2. In contrast to the pure Chern-Simons theory living on the probe D7-branes that are localized at the tip $r = r _ { 0 }$ and wrapped on $S ^ { 5 }$ , this D3-brane theory has propagating degrees of freedom since the probe D3- brane extends to the boundary of the AdS.Similarly, in the case of the edge state generated by D7-brane, due to the presence of $F ^ { ( 5 ) }$ fux, the dual theory is a $U ( 1 ) _ { N }$ DBI-Chern-Simons theory living on the D7-brane wrapped on $S ^ { 5 }$ ：

# 4Hierarchical Fractional QHE from String Theory

So far we have only discussed the Chern-Simons gauge theory with a single gauge group. However, it can only describe those fractional QH systems with filling fractions in the form of

$$
\nu = { \frac { 1 } { k } } ,
$$

where $k$ is an integer and corresponds to the level of the Chern-Simons theory. This integer should be odd in the usual electronic systems since electrons have the fermionic statistics.

When $\nu$ is a more generic fractional number,an important effective description is given by Chern-Simons theories with multiple $U ( 1 )$ gauge fields [2,4],which is called the hierarchical (or general） description. Explicitly it is described by the following action on a three-dimensional spacetime $\Sigma$ (for details see [2])

$$
S = { \frac { 1 } { 4 \pi } } \int _ { \Sigma } \left[ \sum _ { i , j = 1 } ^ { r } K _ { i j } A ^ { ( i ) } \wedge d A ^ { ( j ) } + 2 \sum _ { i = 1 } ^ { r } q _ { i } \tilde { A } \wedge d A ^ { ( i ) } \right] ,
$$

where $K _ { i j }$ is an integer matrix; $q _ { i }$ are integers and $\mathbf { q } = ( q _ { 1 } , q _ { 2 } , \dots )$ is called the charge vector, which characterizes a fractional quantum Halltheory. See [45] for an analysis of quantum aspects of these theories. The field $\tilde { A }$ is the external $U ( 1 )$ gauge field and the $r$ fields $A ^ { ( i ) }$ are dynamical （20 $U ( 1 ) ^ { r }$ gauge fields that describe the internal degrees of freedom.

The equations of motion of (4.68) are

$$
K _ { i j } \partial _ { \alpha } A _ { \beta } ^ { ( j ) } + q _ { i } \partial _ { \alpha } \tilde { A } _ { \beta } = 0 .
$$

The electric current is then given by

$$
J ^ { \alpha } \equiv \frac { 1 } { 2 \pi } \epsilon ^ { \alpha \beta \gamma } q _ { i } \partial _ { \beta } A _ { \gamma } ^ { ( i ) } = \frac { 1 } { 2 \pi } q _ { i } K ^ { i j } q _ { j } \epsilon ^ { \alpha \beta \gamma } \partial _ { \beta } \tilde { A } _ { \gamma } ,
$$

where $K ^ { i j }$ is the inverse matrix of $K _ { i j }$

Thus we can find the filling fraction

$$
\nu = q _ { i } K ^ { i j } q _ { j } ,
$$

and the Hall conductivity

$$
\sigma _ { x y } = \frac { 1 } { 2 \pi } q _ { i } K ^ { i j } q _ { j } = \frac { \nu } { 2 \pi } .
$$

A $i$ -th quasi-particle ( $1 \leq i \leq r$ ）is defined by a particle which carries a unit charge only with respect to $A ^ { ( i ) }$ . If we consider a general quasi-particle with the charge $l = ( l _ { 1 } , l _ { 2 } , \cdots )$ ,its electric charge becomes

$$
Q ( l ) = l _ { i } K ^ { i j } q _ { j } ,
$$

and the phase $e ^ { i \theta }$ which appears when we exchange a quasi-particle with the charge $l$ and another one with $l ^ { \prime }$ is given by

$$
\theta = \pi l _ { i } K ^ { i j } l _ { j } ^ { \prime } .
$$

This angle $\theta$ becomes in general fractional and thus the quasi-particles obey fractional statistics, called anyons.

In this way the theory is defined by the pair $( K , q )$ . The two theories which are related by $S L ( r , \mathbf { Z } )$ transformation $( K , q )  ( M K M ^ { T } , M q )$ ,where $M$ isa $S L ( r , \mathbf { Z } )$ matrix, are considered to be equivalent as they preserve the charge lattice.

One of the most interesting classes of FQH systems can be described by

$$
K = [ K _ { i j } ] = \left( \begin{array} { l l l l } { a _ { 1 } } & { - 1 } & & \\ { - 1 } & { a _ { 2 } } & { - 1 } & \\ & { - 1 } & { a _ { 3 } } & { - 1 } \\ & & { - 1 } & { \ddots } \end{array} \right) , \quad q = ( 1 , 0 , 0 , 0 , \cdot \cdot \cdot ) ,
$$

where $a _ { 1 }$ should be an odd integer because electrons have the fermionic statistics,while $a _ { i \geq 2 }$ are even integers since all quasi-particles are bosons,if they are not dressed by statistical interactions of the Chern-Simons gauge fields. Then the $i$ -th quasi-particle can be regarded as a quasi-particle whose constituent particles are the $( i - 1 )$ -th quasi-particle. This interesting structure is called the hierarchy. The filling fraction (4.71） is now given by the continued fraction

$$
\nu = { \frac { 1 } { a _ { 1 } - { \frac { 1 } { a _ { 2 } - { \frac { 1 } { a _ { 3 } - \ldots } } } } } } ,
$$

where the integer $r$ is the depth of the continued fraction, namely the number of times we need to take the fractions.

It is a very interesting question as to whether we can realize such gauge theories in string theory. It would be very hard if we only consider gauge fields living on D-branes since D-branes usuall lead to non-abelian gauge theories, whose gauge symmetries are not consistent with the

action （4.68） when $K _ { i j } \neq 0$ for $i \neq j$ . Instead we will look for the gauge fields $A ^ { ( i ) }$ among the bulk supergravity fields.

Motivated by the observation that the matrix $K$ (4.75） resembles the intersection matrices of four-dimensional manifolds, we consider the type IIA string on

$$
R ^ { 1 , 2 } \times S ^ { 3 } \times M _ { 4 } ,
$$

where we take the four-dimensional manifold $M _ { 4 }$ to be an orbifold $\mathbb { C } ^ { 2 } / Z _ { n ( p ) }$ . We introduce $k$ （20   
units of $H = d B _ { N S }$ flux on $S ^ { 3 }$ .23

$$
\int _ { S ^ { 3 } } H = - 4 \pi ^ { 2 } k ,
$$

whose backreaction induces a linear dilaton in one of the space-like coordinates in $\Sigma = R ^ { 1 , 2 }$ [47]. The background (4.77) can be realized as the near-horizon limit of NS 5-branes wrapped on the orbifold $\mathbb { C } ^ { 2 } / Z _ { n }$ . We can add the F-string charge and consider in almost the same way the type IIA string on $A d S _ { 3 } \times S ^ { 3 } \times M _ { 4 }$ , which has a clearer holographic dual via the $A d S _ { 3 } / C F T _ { 2 }$ [8].

The action of $Z _ { n ( p ) }$ orbifold is defined by $( z _ { 1 } , z _ { 2 } )  ( e ^ { \frac { 2 \pi i } { n } } z _ { 1 } , e ^ { \frac { 2 \pi i p } { n } } z _ { 2 } )$ where $- n + 1 \leq p \leq n - 1$ （204号 and $( n , | p | ) = 1$ . The orbifold is non-supersymmetric for generic $p$ and is supersymmetric only when $p = \pm 1$ . The type IIA GSO projection requires $p$ to be an odd integer,otherwise the theory becomes type O string and suffers from a bulk tachyon. Though in general we cannot avoid localized closed string tachyons 48, 49], we ignore this issue in this paper.

The minimal resolution of the orbifold singularity $\mathbb { C } ^ { 2 } / Z _ { n ( p ) }$ is given by a chain of $r$ blown-up 2-cycles $[ i ]$ (exceptional $\mathbb { P } ^ { 1 }$ divisors).24 The intersection number between successive 2-cycles is 1 and the self-intersection number of cycle $[ i ]$ is $- a _ { i }$ where $a _ { i } \geq 2 ~ ( i = 1 , 2 , \cdot \cdot \cdot , r )$ . The integers （204号 $\left\{ { a } _ { i } \right\}$ are given by the Hirzeburch-Jung continued fraction [50, 49]:

$$
\frac { n } { \tilde { p } } = a _ { 1 } - \frac { 1 } { a _ { 2 } - \frac { 1 } { a _ { 3 } - . . . } } ,
$$

where $\tilde { p } = p$ for $p > 0$ and ${ \tilde { p } } = p + n$ for $p < 0$ .The integer $r$ is the depth of the continued fraction. Thus the intersection matrix of the resolved $\mathbb { C } ^ { 2 } / Z _ { n ( p ) }$ takes exactly the same form as (4.75) except for an overall minus sign and thus we call it $- \tilde { K } _ { i j }$ ：

Now we are interested in the felds in the twisted sectors and such a theory lives on the fixed points of the orbifold. Then we perform the Kaluza-Klein compactification on $S ^ { 3 }$ to get a theory on $R ^ { 1 , 2 }$ . We expand the 3-form potential as

$$
C _ { \mu \nu \rho } = ( 2 \pi ) ^ { 2 } \sum _ { i } A _ { \mu } ^ { ( i ) } \omega _ { ( i ) \nu \rho } ,
$$

where $\omega _ { ( i ) \mu \nu }$ is the harmonic 2-from dual to the $i$ -th 2 cycle, namely $\begin{array} { r } { \int _ { [ i ] } \omega _ { ( j ) } = \delta _ { i j } } \end{array}$ and ${ \tilde { K } } _ { i j } =$ （204号 $\int \omega _ { ( i ) } \wedge \omega _ { ( j ) }$ ：

The Chern-Simons term in IIA supergravity leads to

$$
\frac { 1 } { 4 \kappa _ { 1 0 } ^ { 2 } } \int H \wedge C \wedge d C = \frac { k } { 4 \pi } \sum _ { i , j = 1 } ^ { r } \tilde { K } _ { i j } A ^ { ( i ) } \wedge d A ^ { ( j ) } .
$$

To couple the system to an external gauge feld, we add a D4-brane wrapped on a linear combination of 2-cycles weighted by the charge vector $\mathbf { q }$ (with the resulting 2-cycle denoted by $\textstyle \sum _ { i } q _ { i } [ i ] )$ . Then it is easy to see that the WZ term $\textstyle { \frac { 1 } { ( 2 \pi ) ^ { 3 } } } \int _ { D 4 } C \wedge F$ on this D4-brane gives

$$
\frac { 1 } { 2 \pi } \int q _ { i } \tilde { A } \wedge d A ^ { ( i ) } ,
$$

where $\tilde { A }$ is the $U ( 1 )$ gauge field on the D4-brane and serves as the external gauge feld that couples to the FQHE system.

Because the Chern-Simons term dominates over the Maxwell term in the low-energy theory, the effective theory with the D4-brane coincides with the Chern-Simons description (4.68） of the hierarchical FQHE if we set the minimal value $k = 1$ . The electric charge is defined with respect to the gauge feld $\tilde { A }$ . It is also intriguing to note that the $i$ -th quasi-particle (anyon), which has a unit charge under $A ^ { ( i ) }$ via the coupling $\textstyle \int A ^ { ( i ) }$ , is the D2-brane which is wrapped on the 2-cycle [i].

If we go back to the orbifold limit,the wrapped D2 and D4-branes can be regarded as linear combinations of fractional DO and D2-branes (for the detailed analysis refer to [51]) . It is very amusing to notice that this fractionality of D-brane charge is related to that of FQHE,which essentially comes from the surprising resemblance between (4.71） and (4.79).

Thus we have found a remarkable relation between the string theory on the orbifold and the hierarchical description of the FQHE.It is intriguing to consider what the holography tells us. In our setup with F-strings and NS5-branes,we have the IIA string on $A d S _ { 3 } \times S ^ { 3 } \times M _ { 4 }$ so we can apply the $A d S _ { 3 } / C F T _ { 2 }$ correspondence.Indeed, the boundary CFT can be identified as the chiral boson theory which precisely describes the edge state. Note that the FQH system lives in the bulk $A d S _ { 3 }$ and the boundary of the $A d S _ { 3 }$ is the edge of the FQH system. In this way, we learned that the edge/bulk correspondence in condensed matter physics, which is sometimes called ‘holography' in condensed matter contexts (e.g. [52])，can be understood as the $A d S _ { 3 } / C F T _ { 2 }$ correspondence.

Before we finish this section,we would like to mention the issue of statistics. One of the most important cases is the supersymmetric orbifold given by $p = - 1$ (ALE singularity). One might think that this cannot be experimentally realized since it has $a _ { i } = 2$ for all $i$ ， whereas ordinary FQHE are constructed from strongly-interacting electrons and fermionic statistics requires $a _ { 1 }$ to be an odd integer. Nevertheless, even in realistic FQHEs, it is no longer absolutely necessary to start from fermionic degrees of freedom. Indeed, we can realize the FQHE at $\textstyle \nu = { \frac { 1 } { k } }$ with $k$ being an even integer in rotating Bose-Einstein condensates (BECs) in cold atomic gases [53]. While cold atoms are neutral under the electromagnetic $U ( 1 )$ gauge field, rotation plays the role of magnetic field,as seen from the Gross-Pitaevskii free-energy density $\mathcal { F }$ describing a BEC $\phi$ ina frame rotating at the angular velocity $\vec { \Omega }$ ， $\begin{array} { r } { \mathcal { F } = \frac { 1 } { 2 m } \left| \left( - i \vec { \nabla } - m ( \vec { \Omega } \times \vec { r } ) \right) \phi \right| ^ { 2 } + V ( \phi ) - \frac { m } { 2 } ( \vec { \Omega } \times \vec { r } ) | \phi | ^ { 2 } } \end{array}$ [53],where $V ( \phi )$ is some potential and $m$ the effective mass of the condensate. If the angular velocity is large enough and if the filling factor takes a particular fraction $\nu = 1 / k$ with $k$ being an even integer, the cold atoms are expected to be in a bosonic analogue of the Laughlin FQH state. Similarly, for more general filing fractions which can be written as continued fractions, the bosonic analogue of the hierarchical FQH states is expected to be realized, where $a _ { 1 }$ is an even integer.

# 5 Discussions

In this paper,we realized three diferent holographic constructions of fractional quantum Hall effect in string theory. Our models offer us systematic understandings of important theoretical concepts in FQHE, such as the fractional quantization of Hall conductivity, edge states, hierarchy, and topological entanglement entropy. In model I, the clasification of edge states is reduced to that of particular configurations of D-branes. Similarly in model III, we find that the classification of hierarchical FQHEs is equivalent tothatof the minimal resolutionsof $\mathbb { C } ^ { 2 } / Z _ { n ( p ) }$ orbifold singularities. Furthermore,model I reveals a deep insight holography: the AdS/CFT correspondence,when applied to the pure $U ( N ) _ { k }$ Chern-Simons theory, is reduced to the levelrank duality. Since the main results are already summarized in Section 1, below we would like to discuss a few connections between our results and recent developments in FQHE in condensed matter literature.

In both the first and second models, to apply the AdS/CFT correspondence, it is necessary to take the large- $N$ limit，whereas the most common QH systems are described in terms of the $U ( 1 )$ (or a collection of $U ( 1 )$ ) Chern-Simons gauge fields. However,we can break the nonabelian $U ( N )$ into $N$ copies of independent $U ( 1 )$ and extract the FQHE for any one of the $U ( 1 )$ factors as we did in section 2. In section 3,we concentrated on the diagonal $U ( 1 )$ of $U ( N )$ and considered FQHE for it. In both models,the holographic calculations of Hall conductivity seem to be closely related to those of anomalies.

More interestingly, non-abelian Chern-Simons theories also appear directly in the effective description of some new types of FQHEs. For example, $S U ( 2 )$ Chern-Simons gauge theory was suggested to describe fractional QHE at $\nu = 5 / 2$ [54,55] and the spin QHE in time-reversal symmetry breaking, singlet topological superconductors [56]. The candidate FQH state for $\nu = 5 / 2$ , called the Moore-Read Pfaffian state, is an example of non-abaliean FQH states, and excitations build on the ground state obey non-Abelian statistics. Beside $\nu = 5 / 2$ ,a FQH state at $\nu = 1 2 / 5$ (and 13/5),which was observed more recently with a very small energy gap, is also suspected to support non-Abelian statistics [57]. The prospect of realizing generic non-abelian Chern-Simons gauge theories in FQHE systems is very exciting from string theory's perspective:

we will have table-top experiments to realize some of the most fascinating aspects of string theory, such as holographic duality and D-brane resolution of orbifold singularity.

We considered the supersymmetric edge states in the $\mathcal { N } = 6$ Chern-Simons theory in model I. They are $\textstyle { \frac { 1 } { 2 } }$ BPS objects and are described by D4 or D8-branes. The $\mathcal { N } = 6$ Chern-Simons theory has the $U ( N ) _ { k } \times U ( N ) _ { - k }$ gauge symmetry. As one way to relate this system to the realistic FQHE,we simply set $N = 1$ and treat the $U ( N ) _ { - k }$ sector as spectators. We indeed reproduced the expected result of Hall conductivity. Moreover, if we take this model literally, our edge states have application beyond the FQHE: they provide a holographic description for interfaces in any systems whose effective theory is $\mathcal { N } = 6$ Chern-Simons theory. This is not a remote possibility. In fact, recently it has been suggested that the double Chern-Simons theory can serve as efective theories to a number of quantum critical phenomena in realistic materials, such as the quantum spin Hall effect,the three-dimensional topological insulators [6],and lattice models with the $Z _ { 2 }$ topological order [58, 59, 60]. It is an intriguing possibility that string theory can give a nice classification of general topological insulators in various dimensions.

Note Added: We noticed that the paper [61], which appeared in the arXiv on the same day, has a partial overlap with this paper in the interpretation of D8-brane charge in the $A d S _ { 4 } \times C P ^ { 3 }$ background as the shift of the total level in the $\mathcal { N } = 6$ Chern-Simons theory.

# Acknowledgments

We are grateful to M. Fukuma, S. Harashita, S.Hellerman, Y.Hikida, K. Hori, Y. Imamura, Y. Okawa, H. Ooguri, M. Sato, S. Shiba, S. Sugimoto, and Y. Tachikawa for useful discussions. This work is supported by World Premier International Research Center Initiative (WPI Initiative)， MEXT, Japan. The work of TT is also supported in part by JSPS Grant-in-Aid for Scientific Research No.20740132, and by JSPS Grant-in-Aid for Creative Scientific Research No. 19GS0219. SR thanks Center for Condensed Matter Theory at University of California, Berkeley for its support. WL thanks the high energy theory group of Kyoto university for their kind hospitality.

# A Supersymmetries Preserved by the Edge State Configuration

# A.1 D4-brane Edge

Now we show that the D4-brane that wraps on the $\mathbb { C P } ^ { 1 }$ defined by $( \theta _ { 1 } , \varphi _ { 1 } )$ with $\xi = 0$ and that extends along $r$ and one spatial direction of $A d S _ { 4 }$ boundary $( R ^ { 1 , 2 } )$ , preserves 6 supersymmetries (or 12 supersymmetries by taking into account the superconformal symmetry). This can be proved in the M-theory lift of ABJM,i.e. M2-branes probing the orbifold $\mathbb { C } ^ { 4 } / \mathbb { Z } _ { k }$ .We take （204号 $( x ^ { 0 } , x ^ { 1 } , x ^ { 2 } )$ to be directions along the M2-branes and $( x ^ { 3 } , x ^ { 4 } , \cdot \cdot \cdot , x ^ { 1 0 } )$ in the orbifold.

A 11D spinor can be represented as eigenstates:

$$
( \gamma _ { 2 } , \gamma _ { 3 4 } , \gamma _ { 5 6 } , \gamma _ { 7 8 } , \gamma _ { 9 1 0 } ) \eta = ( s _ { 0 } , i s _ { 1 } , i s _ { 2 } , i s _ { 3 } , i s _ { 4 } ) \eta ,
$$

where $s _ { i } = \pm 1$ . The M2-brane preserves half of the supersymmetries: $\gamma _ { 0 1 2 ^ { \prime } I I } = \prime I$ ， which gives $s _ { 1 } s _ { 2 } s _ { 3 } s _ { 4 } = 1$ . Since the orbifold acts as $e ^ { \frac { \pi i } { k } \left( s _ { 1 } + s _ { 2 } + s _ { 3 } + s _ { 4 } \right) }$ , it imposes $\textstyle \sum _ { i } s _ { i } = 0$ Namely, the orbifold projection only allows the following combination:

$$
( s _ { 1 } , s _ { 2 } , s _ { 3 } , s _ { 4 } ) = ( + + \mathrm { ~ -- } ) , ( + - + - ) , ( + - \mathrm { ~ -- } + ) , ( - + - + ) , ( - + + - ) , ( - - + + ) , \nonumber
$$

(Namely, it projects out $1 / 4$ of remaining supersymmetries.） Since each pattern has a degeneracy two (i.e. $s _ { 0 } = \pm 1$ ), we have 12 supersymmetries in the ABJM theory.

Now we introduce the M5-brane extending in the $( x ^ { 0 } , x ^ { 1 } , x ^ { 3 } , x ^ { 4 } , x ^ { 5 } , x ^ { 6 } )$ direction:

<html><body><table><tr><td rowspan="2">R1,2 × C4/Zk:</td><td rowspan="2">0</td><td rowspan="2">1</td><td rowspan="2">2</td><td rowspan="2">3</td><td rowspan="2">4</td><td rowspan="2">5</td><td rowspan="2">6</td><td rowspan="2">7</td><td rowspan="2">8</td><td rowspan="2">9</td><td rowspan="2">10</td></tr><tr><td>y</td></tr><tr><td>N M2:</td><td>t ×</td><td>x ×</td><td></td><td>21</td><td>21</td><td>22</td><td>22</td><td>23</td><td>23</td><td>24</td><td>24</td></tr><tr><td></td><td></td><td></td><td>×</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>1 M5:</td><td>×</td><td>×</td><td></td><td>×</td><td>×</td><td>×</td><td>×</td><td></td><td></td><td></td><td></td></tr></table></body></html>

which preserves the supersymmetry

$$
\gamma _ { 0 1 3 4 5 6 } \eta = \eta .
$$

This means that for each configuration in (A.84), $\gamma _ { 2 }$ is now fixed. This breaks half of the supersymmetries: we now have six supersymmetries. Finaly, due to the supersymmetry enhancement (doubling) at the horizon, the D2-D4 system preserves twelve supersymmetries.

# A.2 D8-brane Edge

Now we show that a D8-brane which is wrapped on $\mathbb { C P } ^ { 3 }$ and extends in the $( t , x , r )$ direction preserves 12 supersymmetries in $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ . The two ten-dimensional 16-components Killing spinors can be (formally） written as the 11D 32-component Kiling spinor after adding the 11th dimension as $\tilde { y }$ in (2.4). We follow the convention in [62] and set $( x ^ { 0 } , x ^ { 1 } , \cdot \cdot \cdot , x ^ { 1 0 } ) =$ $( t , r , \theta , \phi , \alpha , \beta , \gamma , \xi _ { 1 } , \xi _ { 2 } , \xi _ { 3 } , \xi _ { 4 } )$ . Then the Killing spinor [62] is given by

$$
\epsilon = e ^ { \frac { \alpha } { 2 } \hat { \gamma } \gamma 4 } e ^ { \frac { \beta } { 2 } \hat { \gamma } \gamma 5 } e ^ { \frac { \gamma } { 2 } \hat { \gamma } \gamma 6 } e ^ { \frac { \xi _ { 1 } } { 2 } \gamma \gamma 6 } e ^ { \frac { \xi _ { 2 } } { 2 } \gamma _ { 5 8 } } e ^ { \frac { \xi _ { 3 } } { 2 } \gamma _ { 6 9 } } e ^ { \frac { \xi _ { 4 } } { 2 } \hat { \gamma } \gamma _ { 1 0 } } e ^ { \frac { \rho } { 2 } \hat { \gamma } \gamma _ { 1 } } e ^ { \frac { t } { 2 } \hat { \gamma } \gamma _ { 0 } } e ^ { \frac { \theta } { 2 } \gamma _ { 1 2 } } e ^ { \frac { \phi } { 2 } \gamma _ { 2 3 } } \epsilon _ { 0 } ,
$$

where $\epsilon _ { 0 }$ is a constant 32-component Majorana spinor in 11D.

The $\Gamma$ -matrix that gives the projection operator from D8-brane is:25

$$
\begin{array} { r c l } { { \Gamma _ { D 8 } } } & { { = } } & { { \gamma _ { 0 1 } \Gamma _ { x } \gamma _ { \sigma _ { 1 } \cdots \sigma _ { 6 } } \gamma _ { 1 0 } , } } \\ { { \Gamma _ { x } } } & { { = } } & { { \displaystyle \frac { 1 } { \sqrt { ( \partial _ { x } \theta ) ^ { 2 } + \sin ^ { 2 } \theta ( \partial _ { x } \phi ) ^ { 2 } } } ( \partial _ { x } \theta \gamma _ { 2 } + \partial _ { x } \phi \gamma _ { 3 } ) . } } \end{array}
$$

It can be greatly simplified:

$$
\Gamma _ { D 8 } = \frac { 1 } { \sqrt { ( \partial _ { x } \theta ) ^ { 2 } + \sin ^ { 2 } \theta ( \partial _ { x } \phi ) ^ { 2 } } } ( \partial _ { x } \theta \gamma _ { 3 } - \partial _ { x } \phi \gamma _ { 2 } ) \equiv \Gamma _ { y } .
$$

Here $y$ is the orthogonal direction of $x$ . D8-brane preserves only those parts of the Killing spinors which satisfy

$$
\Gamma _ { D 8 } \epsilon = \epsilon .
$$

There are two solutions,which are equivalent by a rotation:

$$
\begin{array} { l l l l l l } { { } } & { { } } & { { \theta = x , } } & { { \phi = \phi _ { 0 } , } } & { { \qquad } } & { { \mathrm { w i t h } \quad ( - \sin \phi _ { 0 } \gamma _ { 2 } + \cos \phi _ { 0 } \gamma _ { 3 } ) \epsilon _ { 0 } = \epsilon _ { 0 } } } \\ { { \mathrm { o r } } } & { { \qquad } } & { { \theta = \frac { \pi } { 2 } , } } & { { \phi = x , } } & { { \qquad } } & { { \mathrm { w i t h } \quad \gamma _ { 1 } \epsilon _ { 0 } = - \epsilon _ { 0 } . } } \end{array}
$$

Now we can repeat the argument for D2-D4 system. Instead of $\gamma _ { 2 }$ ,we simply choose $\epsilon _ { 0 }$ to be the eigenstate of $- \sin \phi _ { 0 } \gamma _ { 2 } + \cos \phi _ { 0 } \gamma _ { 3 }$ for the first solution or $\gamma _ { 1 }$ for the second one. Then condition (A.89) breaks half of 24 supersymmetries preserved in $A d S _ { 4 } \times \mathbb { C P } ^ { 3 }$ . Thus the D8-brane preserve 12 supersymmetries.

# B Solution of the Bending Probe Brane at Zero Temperature

Here we would like to present an exact solution to (2.31) at zero temperature. First it is useful to notice that we have the 'Hamiltonian'

$$
D = 1 + z ^ { \prime 2 } + z ^ { 4 } F _ { x y } ^ { 2 } - z ^ { 4 } F _ { t y } ^ { 2 } - z ^ { 4 } ( 1 + z ^ { \prime 2 } ) F _ { t x } ^ { 2 } = { \frac { d ^ { 2 } } { z ^ { 6 } } } ,
$$

where $d > 0$ is a constant.

After we perform a constant shift of $f ( y )$ and $g ( y )$ (called $F ( y )$ and $G ( y )$ )，we find the equations of motion are conveniently summarized as follows:

$$
\begin{array} { l } { { { \displaystyle F ^ { \prime } = - \kappa \frac { \sqrt D } { z } G } , ~ G ^ { \prime } = - \kappa \frac { \sqrt D } { z } F } , }  \\ { { ( z ^ { \prime } ) ^ { 2 } = \displaystyle \frac { d ^ { 2 } } { z ^ { 6 } } ( 1 - \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } ) - 1 . } } \end{array}
$$

where we set $\begin{array} { r } { \kappa = \frac { \tilde { k } } { 2 \pi \alpha } } \end{array}$ k; β is also a constant defined by

$$
F ^ { 2 } - G ^ { 2 } = \beta ^ { 2 } .
$$

The profile of the D-brane is determined by solving (B.95). Its turning point is $z = z _ { * }$ defined by $\begin{array} { r } { \frac { d ^ { 2 } } { z _ { * } ^ { 6 } } ( 1 - \kappa ^ { 2 } \beta ^ { 2 } z _ { * } ^ { 2 } ) - 1 = 0 } \end{array}$ ：

We can solve $F$ and $G$ as

$$
F + G = A _ { 1 } \cdot e ^ { I ( y ) } , ~ F - G = A _ { 2 } \cdot e ^ { - I ( y ) } ,
$$

where $A _ { 1 } A _ { 2 } = \beta ^ { 2 }$ and the function $I ( y )$ is

$$
I ( y ) = \int _ { z _ { * } } ^ { z ( y ) } d z \frac { k d } { z \sqrt { d ^ { 2 } ( 1 - \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } ) - z ^ { 2 } } } .
$$

If we denote an odd and even functions which are two independent solutions for $F$ by $F _ { 1 } ( y )$ and $F _ { 2 } ( y )$ , then we can write

$$
A _ { t } ( y ) = a _ { 1 } F _ { 1 } ( y ) + a _ { 2 } F _ { 2 } ( y ) + a _ { 3 } , A _ { x } ( y ) = a _ { 1 } F _ { 2 } ( y ) + a _ { 2 } F _ { 1 } ( y ) + a _ { 4 } ,
$$

where $u _ { 1 } , u _ { 2 } , u _ { 3 }$ and $a _ { 4 }$ are all integration constants.

# C Solution for Single-Edge at Zero Temperature

If we assume the zero temperature i.e. $r _ { 0 } = 0$ , the profile of $A _ { x } = g ( z )$ and $A _ { t } = f ( z )$ can be solved exactly. Their EOMs become

$$
\frac { z F ^ { \prime } } { 1 - z ^ { 4 } ( F ^ { \prime } ) ^ { 2 } + z ^ { 4 } ( G ^ { \prime } ) ^ { 4 } } = - \frac { \tilde { k } } { 2 \pi \alpha } G , \frac { z G ^ { \prime } } { 1 - z ^ { 4 } ( F ^ { \prime } ) ^ { 2 } + z ^ { 4 } ( G ^ { \prime } ) ^ { 4 } } = - \frac { \tilde { k } } { 2 \pi \alpha } F ,
$$

wherewe defined

$$
{ \cal F } = f + \frac { 2 \pi } { \tilde { k } } j - \frac { 2 \pi } { \tilde { k } } \left( \frac { \tilde { k } } { 4 \pi } + \eta \right) f ( 0 ) , { \cal G } = g - \frac { 2 \pi } { \tilde { k } } \left( \frac { \tilde { k } } { 4 \pi } - \eta \right) g ( 0 ) - \frac { 2 \pi } { \tilde { k } } \rho .
$$

Below we assume $\tilde { k } < 0$ and define $\begin{array} { r } { \kappa = \frac { | \bar { k } | } { 2 \pi \alpha } } \end{array}$

First we notice $( F ^ { 2 } - G ^ { 2 } ) ^ { \prime } = 0$ . Thus we can set

$$
G ^ { 2 } = F ^ { 2 } + \beta ^ { 2 } ,
$$

where $\beta$ is a constant. The relation $G ^ { 2 } > F ^ { 2 }$ will be made clear later.

Then the EOMs are reduced to the differential equation for $F ( z )$

$$
F ^ { \prime } = \frac { \kappa \sqrt { F ^ { 2 } + \beta ^ { 2 } } } { z \sqrt { 1 + \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } } } .
$$

Its solution is given by

$$
F + \sqrt { F ^ { 2 } + \beta ^ { 2 } } = A \left( \frac { z } { 1 + \sqrt { 1 + \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } } } \right) ^ { \kappa } .
$$

In summary we find

$$
\begin{array} { r } { 2 F = A \left( \frac { z } { 1 + \sqrt { 1 + \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } } } \right) ^ { \kappa } - \frac { \beta ^ { 2 } } { A } \left( \frac { z } { 1 + \sqrt { 1 + \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } } } \right) ^ { - \kappa } , } \\ { 2 G = A \left( \frac { z } { 1 + \sqrt { 1 + \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } } } \right) ^ { \kappa } + \frac { \beta ^ { 2 } } { A } \left( \frac { z } { 1 + \sqrt { 1 + \kappa ^ { 2 } \beta ^ { 2 } z ^ { 2 } } } \right) ^ { - \kappa } . } \end{array}
$$

Thus the general solutions take the form

$$
\begin{array} { r } { \displaystyle { F = - \frac { \beta ^ { 2 } } { A } z ^ { - \kappa } + A z ^ { \kappa } + \cdot \cdot \cdot , } } \\ { \displaystyle { G = \frac { \beta ^ { 2 } } { A } z ^ { - \kappa } + A z ^ { \kappa } + \cdot \cdot \cdot . } } \end{array}
$$

The leading term $z ^ { - \kappa }$ implies that the operator to the gauge field has the conformal dimension （20 $\Delta = 1 + \kappa$ ( $> 1$ ）[63].

# D Another Derivation of Hall Conductivity in D3-D7 Model

Here we would like to compute the Hallconductivity in the holographic dual gravity side treating the D7-branes as probe D-branes instead of replacing it with the background axion flux. Since we are interested in the Hall conductivity in the low energy theory, we place the holographic screen (i.e. the boundary of AdS) near $r = r _ { 0 }$ ：at $r = r _ { 1 }$ with $r _ { 1 } \gtrsim r _ { 0 }$ . Then the holographic current is computed as the on-shell variation of the action:

$$
j ^ { \mu } = \frac { \delta S _ { I I B } } { \delta A _ { R R \mu } } | _ { r = r _ { 1 } } ,
$$

where $A _ { R R }$ is the 1-form that comes from the RR 2-form field $B _ { R R }$ via (3.54) and serves as the external gauge field in the D3-brane system. $S _ { I I B }$ is the type IIB supergravity action plus the D7-brane world-volume action evaluated on-shell. In the leading-order calculation of the holographic current，only $B _ { R R }$ and $B _ { N S }$ are important; and the type IIB supergravity action includes their kinetic terms:

$$
- \frac { 1 } { 4 \kappa ^ { 2 } } \int d ^ { 1 0 } x \sqrt { - g } \left( g _ { s } ^ { - 2 } | H _ { N S } | ^ { 2 } + | H _ { R R } | ^ { 2 } \right) = - \frac { 1 } { 2 ( 2 \pi ) ^ { 7 } } \int d ^ { 1 0 } x \sqrt { - g } \left( g _ { s } ^ { - 2 } | H _ { N S } | ^ { 2 } + | H _ { R R } | ^ { 2 } \right) ,
$$

In the presence of the 5-form fux, the Chern-Simons term $\begin{array} { r } { - \frac { 1 } { 4 \kappa ^ { 2 } } \int C _ { 4 } \wedge H _ { N S } \wedge H _ { R R } } \end{array}$ together with the cross terms in $- { \frac { 1 } { 8 \kappa ^ { 2 } } } \int | \tilde { F } _ { 5 } | ^ { 2 }$ gives a Chern-Simons coupling (after compactifying on $S ^ { 5 }$ ） [38]

$$
\frac { N } { ( 2 \pi ) ^ { 3 } } \int d B _ { N S } \wedge B _ { R R } .
$$

We fixed the surface term in (D.109) by requiring that the gauge symmetries $B _ { N S }  B _ { N S } + d \Lambda _ { N S }$ （20 and $B _ { R R }  B _ { R R } + d \Lambda _ { R R }$ are preserved even when $H _ { R R } \neq 0$

To write down the D7-brane world-volume action, we will use the ansatz in which the $U ( k )$ gauge field $A$ is proportional to the identity matrix $\mathbf { 1 } _ { k \times k }$ . Then terms involving $A$ are

$$
\frac { N } { 4 \pi } \int _ { R ^ { 1 , 2 } } \mathrm { T r } A \wedge d A + \frac { N } { ( 2 \pi ) ^ { 2 } } \int _ { R ^ { 1 , 2 } } \mathrm { T r } A \wedge B _ { N S } + \frac { 1 } { ( 2 \pi ) ^ { 6 } } \int _ { D 7 } \mathrm { T r } A \wedge * d B _ { R R } ,
$$

where in the first two terms we have integrated the RR 5-form flux over $S ^ { 5 }$ and the last term comes from the RR-coupling $2 \pi T _ { 7 } \int \mathrm { T r } F \wedge C _ { ( 6 ) }$

The equation of motion of the gauge field $A$ on D7-branes integrated over $S ^ { 5 }$ leads to

$$
\frac { N } { 2 \pi } d A + \frac { 1 } { ( 2 \pi ) ^ { 6 } } \int _ { S ^ { 5 } } \left( * H _ { R R } \right) | _ { D 7 } = 0 ,
$$

where $\cdots \_$ means the restriction to (pullback to) the D7-brane world-volume.

Now we assume a Dirichlet boundary condition for $B _ { R R }$ and a Neumann one for $B _ { N S }$ at the boundary $r = r _ { 1 }$ . Also we expect that the low-energy solution has $B _ { N S } = 0$ . The variation of $B _ { N S }$ vanishes at $r = r _ { 0 }$ by a cancellation between the bulk and D7-branes contributions only if

$$
\begin{array} { r } { A _ { R R } | _ { D 7 } + k A = 0 , } \end{array}
$$

using (D.109), (D.110) and (3.54). Note that the two equations (D.111) and (D.112) determine $A _ { R R }$ completely.

We are ready to compute the holographic charge density $\rho$ and current density $j$ . Define a 1-form $J \equiv \rho d t + j _ { x } d x + j _ { y } d y$ and assume $r _ { 1 }$ is very close to $r _ { 0 }$

$$
= { \frac { \delta S _ { I I B } } { \delta A _ { R R } } } \Big | _ { r = r _ { 1 } } = { \frac { 1 } { ( 2 \pi ) ^ { 7 } } } * _ { 3 } \int _ { S ^ { 1 } \times S ^ { 5 } } d \tilde { \theta } \wedge ( * H _ { R R } ) | _ { D ^ { 7 } } = { \frac { N } { 2 \pi } } * _ { 3 } ( d A ) = { \frac { N } { 2 \pi k } } * _ { 3 } ( F _ { R R } | _ { D ^ { 7 } } ) .
$$

where the first step is an on-shell variation of the kinetic term $\int _ { M } d ( \delta B _ { R R } ) \wedge * H _ { R R }$ which leads to the boundary variation $\int _ { \partial M } \delta B _ { R R } \wedge \ast H _ { R R }$ after imposing the bulk equation of motion of $B _ { R R }$ and we used (D.111) and (D.112) in the last two steps.

The $x$ component of (D.113） gives $\begin{array} { r } { j _ { x } = \frac { N } { k h } E _ { y } } \end{array}$ . Thus we find the fractional Hall conductivity

$$
\sigma _ { x y } = \frac { N } { k h } .
$$

This clearly agrees with what we find from (3.56).

# References

[1] “The quantum Hall effect, 2nd ed.,” Eds. R. E. Prange and S. M. Girvin, Springer-Verlag, Berlin (1990).   
[2] X-G. Wen， “Quantum Field Theory of Many-Body Systems,” Oxford University Press (2004).   
[3] D. Yoshioka,“The Quantum Hall Effect,” Springer, Solid-State Scineces (1998).   
[4] A. Zee,“Quantum Hall fluids,” [arXiv:cond-mat/9501022].   
[5] E. Witten,“Quantum field theory and the Jones polynomial,” Commun. Math. Phys.121 (1989) 351.   
[6] C.L. Kane and E. J. Mele,‘ $Z _ { 2 }$ Topological Order and the Quantum Spin Hall Effect," Phys. Rev. Lett.95(2005) 226801; B.A. Bernevig and S. C. Zhang, “Quantum Spin Hall Effect,” Phys. Rev. Lett. 96 (2006) 106802; R. Roy, “On the $Z _ { 2 }$ classification of Quantum Spin Hall Models,” arXiv:cond-mat/O604211; J. E. Moore and L. Balents,“Topological invariants of time-reversal-invariant band structures,” Phys. Rev.B 75 (2007) 121306(R); R.Roy，“Three dimensional topological invariants for time reversal invariant Hamiltonians and the three_ dimensional quantum spin Hall effect,” arXiv:cond-mat/0607531; L. Fu, C. L. Kane, and E. J. Mele, “Topological Insulators in Three Dimensions,”Phys. Rev.Lett.98(2007) 106803; A. P. Schnyder, S. Ryu, A. Furusaki, A. W. W. Ludwig, “Classification of topological insulators and superconductors in three spatial dimensions,” Phys. Rev. B 78 (2008) 195125; X. L. Qi, T, Hughes,and S. C. Zhang,“Topological Field Theory of Time-Reversal Invariant Insulators,” arXiv:0802.3537. [7] M. Konig et al.， “Quantum Spin Hall Insulator State in HgTe Quantum Wels,” Science 318(2007) 766; D. Hsieh et al.， “Topological phases of time-reversal invariant superconductors and electronic systems with sublattice (chiral) symmetry, in three spatial dimensions,” Nature 452 (2008) 970. [8] J.M. Maldacena,“The large N limit of superconformal field theories and supergravity,”Adv.Theor.Math.Phys.2 (1998) 231 [Int.J. Theor.Phys.38(1999)1113] [arXiv:hep-th/9711200]; [9] L. Susskind, “The quantum Hall fuid and non-commutative Chern Simons theory,” arXiv:hep-th/0101029.   
[10] A. P. Polychronakos,“Quantum Hal states as matrix Chern-Simons theory,” JHEP 0104 (2001) 011 [arXiv:hep-th/0103013]; “Quantum Hallstates on the cylinder as unitary matrix Chern-Simons theory,” JHEP 0106 (2001) 070 [arXiv:hep-th/0106011].   
[11] S.Hellerman and M. Van Raamsdonk,“Quantum Hall physics equals noncommutative field theory,” JHEP 0110 (2001） 039 [arXiv:hep-th/0103179].   
[12] S.Hellerman and L. Susskind，“Realizing the quantum Hall system in string theory,” arXiv:hep-th/0107200.   
[13] J. H. Brodie,“D-branes in massive IIA and solitons in Chern-Simons theory,” JHEP 0111 (2001）014 [arXiv:hep-th/0012068].   
[14] J. H. Brodie, L. Susskind and N. Toumbas,“How Bob Laughlin tamed the giant graviton from Taub-NUT space,” JHEP 0102 (2001) 003 [arXiv:hep-th/0010105].   
[15] O. Bergman, Y. Okawa and J. H. Brodie,“The stringy quantum Hall fluid,” JHEP 0111 (2001) 019 [arXiv:hep-th/0107178].   
[16] E. Keski-Vakkuri and P. Kraus,“Quantum Hall Effect in AdS/CFT,” JHEP 0809 (2008) 130 [arXiv:0805.4643 [hep-th].   
[17] J. L. Davis, P. Kraus and A. Shah,“Gravity Dual of a Quantum Hall Plateau Transition," JHEP 0811 (2008) 020 [arXiv:0809.1876 [hep-th].   
[18] S. J.Rey,“Quantum Phase Transitions from String Theory,” Talk given at Strings 2007in Madrid.   
[19] S. A. Hartnoll and P. Kovtun,“Hall conductivity from dyonic black holes,” Phys. Rev. D 76 （2007） 066001 [arXiv:0704.1160 [hep-th].   
[20] A. O'Bannon, “Hall Conductivity of Flavor Fields from AdS/CFT,” Phys. Rev. D 76, 086007（2007） [arXiv:0708.1994 [hep-th]].   
[21] R. C. Myers and M. C. Wapler， “Transport Properties of Holographic Defects,” arXiv:0811.0480 [hep-th].   
[22] O.Aharony, O. Bergman, D.L. Jafferis and J. Maldacena,“N=6 superconformal ChernSimons-matter theories, M2-branes and their gravity duals,” JHEP O810 (2008) 091 [arXiv:0806.1218 [hep-th]].   
[23] O.Aharony, O. Bergman and D.L. Jaferis,“Fractional M2-branes,” JHEP 0811 (2008) 043 [arXiv:0807.4924 [hep-th].   
[24] E. Witten,“Anti-de Sitter space, thermal phase transition,and confinement in gauge theories,” Adv. Theor. Math. Phys. 2 (1998) 505 [arXiv:hep-th/9803131].   
[25] A. Kitaev and J. Preskill,“Topological entanglement entropy,” Phys. Rev. Lett. 96 (2006) 110404 [arXiv:hep-th/0510092].   
[26] M. Levin, X-G. Wen,“Detecting topological order in a ground state wave function,” Phys. Rev. Lett. 96 (2006) 110405 [arXiv:c0nd-mat/0510613].   
[27] S.Dong， E. Fradkin，R. G. Leigh and S. Nowling，“Topological Entanglement Entropy in Chern-Simons Theories and Quantum Hall Fluids,” JHEP O805 (2008） 016 [arXiv:0802.3231 [hep-th]].   
[28] T. Nishioka_and T. Takayanagi， “On_Type IIA Penrose Limit and N=6 Chern-Simons Theories,” JHEP 0808 (2008) 001 [arXiv:0806.3391 [hep-th].   
[29] F.E. Camino et al.,“Aharonov-Bohm Superperiod in a Laughlin Quasiparticle Interferometer,”Phys.Rev. Lett. 95(2005) 246802; E. Camino et al., “Realization of a Laughlin quasiparticle interferometer: Observation of fractional statistics,” Phys. Rev. B 72(2005) 075342; E.-A.Kim,“Aharanov-Bohm Interference and Fractional Statistics in a Quantum Hall Interferometer,” Phys.Rev. Lett. 97(2006) 216404; B. Rosenow and B.I. Halperin,“Influence of Interactions on Flux and Back-Gate Period of Quantum Hall Interferometers,” Phys. Rev. Lett. 98 (2007) 106801; J. K. Jain and C. Shi,“Resonant Tunneling in the Fractional Quantum Hall Effect: Superperiods and Braiding Statistics,” Phys. Rev. Lett. 96 (2006) 136802; “Novel metallic and insulating states at a bent quantum Hall junction,” M. Grayson, L. Steinke, D. Schuh，M. Bichler,L. Hoeppel, J. Smet， K. v. Klitzing, D. K. Maude,G. Abstreiter, Phys. Rev. B 76 (2007) 201304(R).   
[30] X. G. Wen and A. Zee,“On the Possibility of a Statistics Changing Phase Transition,” J. de Physique 50（1989） 1623   
[31] A. Karch and A. O'Bannon,“Metallic AdS/CFT,” JHEP 0709 (2007) 024 [arXiv:0705.3870 [hep-th]].   
[32] S. Kobayashi, D. Mateos, S. Matsuura, R. C. Myers and R. M. Thomson，“Holographic phase transitions at finite baryon density,” JHEP 0702 (2007) O16 [arXiv:hep-th/0611099].   
[33] S. Elitzur,G.W. Moore，A. Schwimmer and N. Seiberg，“Remarks On The Canonical Quantization Of The Chern-Simons-Witten Theory,” Nucl. Phys. B 326 (1989） 108.   
[34] J. M. Maldacena and H. S. Nastase,“The supergravity dual of a theory with dynamical supersymmetry breaking,” JHEP 0109 (2001） 024 [arXiv:hep-th/0105049].   
[35] S. G. Naculich and H. J. Schnitzer,“Level-rank duality of the U(N) WZW model, ChernSimons theory, and 2d qYM theory,” JHEP 0706 (2007) 023 [arXiv:hep-th/0703089].   
[36] E. Witten，“Baryons_and branes in anti de Sitter space,” JHEP 9807 (1998) 006 [arXiv:hep-th/9805112].   
[37] A. Karch and E. Katz， “Adding flavor to AdS/CFT,” JHEP 0206 (2002） 043 [arXiv:hep-th/0205236].   
[38] O. Aharony and E. Witten, “Anti-de Sitter space and the center of the gauge group,” JHEP 9811 (1998) 018 [arXiv:hep-th/9807205].   
[39] A. Pakman and A. Parnachev,“Topological Entanglement Entropy and Holography,” JHEP 0807（2008) 097 [arXiv:0805.1891 [hep-th]].   
[40] S. Ryu_and T. Takayanagi， “Holographic derivation of entanglement entropy from AdS/CFT,” Phys.Rev. Lett. 96 (2006) 181602 [arXiv:hep-th/0603001]；“Aspects of holographic entanglement entropy,” JHEP 0608 (2006) 045 [arXiv:hep-th/0605073].   
[41] D.V. Fursaev, “Proof of the holographic formula for entanglement entropy,” JHEP 0609 (2006) 018 [arXiv:hep-th/0606184].   
[42] T. Nishioka and T. Takayanagi, “AdS bubbles, entropy and closed string tachyons,” JHEP 0701(2007) 090 [arXiv:hep-th/0611035].   
[43] I. R. Klebanov, D. Kutasov and A. Murugan,“Entanglement as a Probe of Confinement,” Nucl. Phys. B 796 (2008) 274 [arXiv:0709.2140 [hep-th].   
[44] V. Periwal，“Topological Closed String Interpretation Of Chern-Simons Theory,” Phys. Rev. Lett.71 (1993)1295 [arXiv:hep-th/9305115].   
[45] S. Gukov, E. Martinec, G.W. Moore and A. Strominger,“Chern-Simons gauge theory and the AdS(3)/CFT(2) correspondence,” arXiv:hep-th/0403225; D.Belov and G.W. Moore，“Classification of abelian spin Chern-Simons theories,” arXiv:hep-th/0505235.   
[46] J. Polchinski, “String theory. Vol. 1,2,” Cambridge, UK: Univ. Pr. (1998).   
[47] C.G. Callan, J.A. Harvey and A. Strominger,“World sheet approach to heterotic instantons and solitons,” Nucl. Phys. B 359 (1991) 611.   
[48] A. Adams, J. Polchinski and E. Silverstein, “Don't panic!_Closed string tachyons in ALE space-times,” JHEP 0110 (2001） 029 [arXiv:hep-th/0108075].   
[49] J. A. Harvey, D. Kutasov, E. J. Martinec and G.W. Moore, “Localized tachyons and RG flows,” arXiv:hep-th/0111154.   
[50] W. Fulton, “Introduction to Toric Varieties,” Princeton University Press (1993).   
[51] G.W. Moore and A. Parnachev, “Localized tachyons and the quantum McKay correspondence,” JHEP 0411 (2004) 086 [arXiv:hep-th/0403016]; G. Moore and A. Parnachev, “Profiling the_brane drain in a nonsupersymmetric orbifold,” JHEP O601 (2006） 024 [arXiv:hep-th/0507190].   
[52] P. Fendley， M. P. A. Fisher and C. Nayak,“TopologicalEntanglement Entropy from the Holographic Partition Function,” J. Statist.Phys.126 (2007） 1111 [arXiv:cond-mat/0609072].   
[53] J. W. Reijnders, F. J. M. van Lankvelt, K. Schoutens, N. Read,“Quantum Hall states and boson triplet condensate for rotating spin-1 bosons,” Phys. Rev. Lett.89 (2002) 120401; N. R. Cooper, N. K. Wilkin, and J. M. F. Gunn, “Quantum Phases of Vortices in Rotating Bose-Einstein Condensates,” Phys.Rev. Lett.87 (2001） 120405; N. R. Cooper, N. K. Wilkin,“A Composite Fermion Description of Rotating Bose-Einstein Condensates," Phys. Rev. B 60 (1999) R16279; N. K. Wilkin, J. M. F. Gunn, “Condensation of ‘composite bosons’ in a rotating BEC,"” arXiv:cond-mat/9906282; N. R. Cooper, “Rapidly Rotating Atomic Gases”, arXiv:0810.4398.   
[54] G. Moore and N. Read,“Nonabelions in the fractional quantum Hal ffect,” Nucl. Phys. B 360（1991） 362.   
[55] E.Fradkin, Chetan Nayak,A. Tsvelik,and Frank Wilczek,“A Chern-Simons Efective Field Theory for the Pfaffian Quantum Hall State,” Nucl. Phys. B 516 (1998) 704.   
[56] N.Read and D. Green,“Paired states of fermions in two dimensions with breaking of parity and time-reversal symmetries,and the fractional quantum Hall effct,” Phys. Rev.B 61 (2000）10267.   
[57] N. Read and E. Rezyai, “Beyond paired quantum Hall states: Parafermions and incompressible states in the first excited Landau level,” Phys. Rev. B 59 (1999) 8084.   
[58] T. H. Hansson, Vadim Oganesyan, S. L. Sondhi, “Superconductors are topologically ordered,” Ann. Phys. 313 (2004) 497.   
[59] S.P. Kou， M. Levin and X. G. Wen，“Mutual Chern-Simons theory for $Z _ { 2 }$ topological order,” arXiv:0803.2300 [cond-mat.str-el];   
[60] C. Xu and S. Sachdev, “Global phase diagrams of frustrated quantum antiferromagnets in two dimensions: doubled Chern-Simons theory,” arXiv:0811.1220 cond-mat.str-el].   
[61] D. Gaiotto and A. Tomasiello,“The gauge dual of Romans mass,” arXiv:0901.0969 [hep-th].   
[62] T. Nishioka and T. Takayanagi，“Fuzzy Ring from M2-brane Giant Torus,” JHEP 0810 (2008) 082 [arXiv:0808.2691 [hep-th].   
[63] P.Minces and V. O.Rivelles,“Chern-Simons theories in the AdS/CFT correspondence," Phys. Lett. B 455 (1999) 147 [arXiv:hep-th/9902123].