# A mathematical review on the multiple solutions problem

K. Zhu, X. H. Mo, C. Z. Yuan, P. Wang Instituteof High Energy Physics,   
Chinese Academy of Science,PO Box 918(1),   
Beijing 100049，People's Republic of China\* (Dated:July 27,2011)

The recent multiple solutions problem in high energy physics has been reviewed with a more mathematical viewpoint.Although previously these multiple solutions are found via fit process,in this letter we have proved that if a sum of two coherent simple Breit-Wigner functions is used to fit the measured distribution,there should be two and only two non-trivial solutions,which are related with each other by analytical formulae.For real experimental measurements with more complex situations,we also provide a numerical method to extract the other solution with the already obtained one,and the excellent consistence between the exact solution and the fit process justifies this method. From our results it is clear that the physics interpretation should be very different depending on which solution is selected. So we suggest that allthe experimental measurements with potential multiple solutions problem should be re-analyzed to find the other solution because the result is not complete if only one solution was reported.

PACS numbers:14.40Gx,13.25.Gv,13.66.Bc,12.39.Mk

# I.INTRODUCTION

Interference as a nature phenomenon has been observed for a very long time in situations where waves intersect,no matter the mediate material is water wave, string,sound or light.It has been studied in depth and also widely used in a range of physical and engineering measurement applications,in that field Young's slits interferometer,Michelson-Morley experiment and Newton's rings are famous examples. Even in some leading edge physics experiments, interference play a major role, such as optic interferometer in gravity wave detection. However, classic physics and quantum mechanics provide basically different explanations of this phenomenon.In classic physics,if only two meeting waves are considered contributing to a process,what observed is just the sum of amplitudes of two waves is $A ( x ) = A _ { 1 } ( x ) + A _ { 2 } ( x )$ 5 where $x$ are generalized coordinates could be position, momentum,time,energy,etc.But in quantum mechanics,their wave functions are summed to obtain the total amplitude (generally there are relative phases between them)，i.e. $| \psi ( x ) \rangle = | a ( x ) \rangle + | b ( x ) \rangle$ . And the experimentally measured quantities are usually proportional to the modulus of the amplitude squared,and thus one generally has contribution from an interference term $\langle a | b \rangle$ ， not appears in classic physics, to the physics observable. Many new and fantastic features in quantum mechanics，compared with the classic one，are caused by this additional interference term $\langle a | b \rangle$ ，and the ambiguity of extracting information from observation is one of them.

Usually the experimental quantities depending on $| \psi | ^ { 2 }$ are measured,and from which we extract the information of the amplitudes $| a \rangle$ and $| b \rangle$ .Unlike to what in classic physics,there is a square operation between the observable and the amplitudes,we would expect other solutions, $| a ^ { \prime } \rangle$ and $\left| { b ^ { \prime } } \right.$ ，may be found in extracting amplitudes from physics measurements.It's true that the existing freedom on the global phase is non-relevant to the physics during this extraction procedure. However, more and more presented experimental analyses imply that different solutions with different relative phase angles would lead to non-trivial different physical interpretations.

Some earlier examples reporting multiple solutions are in the study of the so-called $Y$ states via initial state radiation $( I S R )$ by the Belle experiment [1,2]. The invariant mass distributions of $\pi ^ { + } \pi ^ { - } J / \psi$ and $\pi ^ { + } \pi ^ { - } \psi ( 2 S )$ are a fit with two coherent resonant terms and an incoherent background term.Another earlier example is the study of the decay dynamics of $\eta ^ { \prime }  \gamma \pi ^ { + } \pi ^ { - }$ mode.When the $\pi ^ { + } \pi ^ { - }$ invariant mass distribution is fitted with coherent sum of the $\rho$ resonance and a contact term,two solutions are found with one solution corresponds to constructive interference between the two amplitudes while the other destructive interference [3]. Some recent examples are presented in Refs.[4,5]. In Ref.[4] two solutions are found for both the branching faction measurement of $\phi \to \omega \pi ^ { 0 }$ and the $\rho - \omega$ mixing study. In Ref.[5], four sets of solutions are found by fitting the $R$ -values to extract the resonance parameters of the excited $\psi$ -family resonances, namely the $\psi ( 4 0 4 0 )$ ， $\psi ( 4 1 6 0 )$ ，and $\psi ( 4 4 1 5 )$ ：

However,it is notable that in Refs.[1-6] all the multiple solutions are found via fit process. And we know fit method always suffers from backgrounds and limit ed statistics. Then some interesting questions are raised naturally such as are these solutions exact solutions or only approximate results from the fit process? Do these solutions always exist or just coincidentally? How many are they? If one special solution has already been found, can the others be derived from it? Some of questions are explored from physics point of view in Refs.[4,5],and mathematical attempts are described in Ref.[7,8],following the clue of which the present study is performed. Comparing with Ref.[7] in which Fourier transformation is applied,the solution finding process is extremely simplified in this letter; comparing with Ref. [8]，more general conclusions are obtained.

In the next section,section I,at the outset,a general and mathematic model for the sum of two amplitudes is established on the basis of the known facts of physical analyses. If two amplitudes are both commonly used Breit-Wigner functions, the analytical expression for two solutions are obtained. Moreover,an effective approach is developed for acquiring the algebra equations related to solutions. Then many double-solutions are derived for the distinctive forms of amplitude functions. After that，we put forth the constraint relation for the ratio of two amplitude functions,which ensure that there will be double non-trivial solutions. In section III, firstly,a toy numerical example is used to check and confirm our results.Secondly, the published fit results are re-obtained by analytical calculation which demonstrates a numerical procedure to get the unknown solution from the known one.Finally there is a short discussion on the meaning about the multiple solutions problem and our suggestion.

# II. MATHEMATICALMETHODOLOGY

If scrutinizing the relevant results of multiple solutions [1-6],we can note two prominent characters:1.all set of solutions have the equal goodness-of-fit;2. although all parameters including the masses,the total widths, the partial widths and some other related parameters are allowed to float in the fit,it is observed that the only difference between multiple solutions is the partial widths and the relative phase angle between amplitudes. The first point indicates that all solutions are mathematically e quivalent while the second point implies that the main difference for difference solutions consists in a normalized factor and relative phase between them.In the light of these experimental facts,we abstract a general mathematic model for multi-solution problem.Without losing generality, the study that follows focuses on the case of two amplitude functions.

# A. Solutions for two Breit-Wigner amplitudes

Generally,a sum of two quantum amplitudes can be described by a complex function $e ( x , z _ { 1 } , z _ { 2 } )$ with form

$$
e ( x , z _ { 1 } , z _ { 2 } ) = z _ { 1 } \ g ( x ) + z _ { 2 } \ f ( x ) \ ,
$$

where $g ( x )$ and $f ( x )$ are both complex functions, $x$ isa real variable,and $z _ { 1 } , z _ { 2 }$ are complex numbers.The main purpose of this letter is to discuss how to find non-trivial

different series of parameters $z _ { 1 } ^ { \prime }$ and $z _ { 2 } ^ { \prime }$ that satisfy

$$
\left| e ( x , z _ { 1 } , z _ { 2 } ) \right| ^ { 2 } = \left| e ( x , z _ { 1 } ^ { \prime } , z _ { 2 } ^ { \prime } ) \right| ^ { 2 } ~ .
$$

Noticed the global phase plays no role in the amplitude square, then we can reduce the dimension of $z _ { 1 } - z _ { 2 }$ parameter space to a $z - d$ space in which $d$ is real number, and re-write $| e ( x , z _ { 1 } , z _ { 2 } ) | ^ { 2 }$ to a more convenient form by defining

$$
{ \begin{array} { l } { \displaystyle | e ( x , z _ { 1 } , z _ { 2 } ) | ^ { 2 } \equiv { \frac { 1 } { d } } | g ( x ) + z \ f ( x ) | ^ { 2 } } \\ { = \ \displaystyle { \frac { | g ( x ) | ^ { 2 } } { d } } \left| 1 + z { \frac { f ( x ) } { g ( x ) } } \right| ^ { 2 } \equiv { \frac { | g ( x ) | ^ { 2 } } { d } } \left| 1 + z \ F ( x ) \right| ^ { 2 } } \\ { \equiv \ \displaystyle { \frac { | g ( x ) | ^ { 2 } } { d } } E ( x , z ) ~ . } \end{array} }
$$

Here $F ( x ) \equiv f ( x ) / g ( x )$ and $E ( x , z ) \equiv { \left| { 1 + z \ F ( x ) } \right| ^ { 2 } }$ . Noticed $| g ( x ) | ^ { 2 }$ is only a multiply factor and independent of $d$ and $z$ ，then it can be dropped in following discussion. Now we only focus on finding different series of $d$ and $z$ （204号 that keep $E ( x , z ) / d$ unchanged. Denoting the real and imaginary parts of $F ( x )$ with $R _ { F } ( x )$ and $I _ { F } ( x )$ ，as well as $R _ { z }$ and $I _ { z }$ for $z$ respectively. Expressing $E ( x , z )$ by the real and imaginary components,we obtain

$$
( R _ { F } ^ { 2 } + I _ { F } ^ { 2 } ) ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } ) - 2 I _ { F } I _ { z } + 2 R _ { F } R _ { z } + 1 \ .
$$

Without losing generality, set $d = 1$ as an initial solution for convenience, so our task aims at finding all possible $d$ and $z ^ { \prime }$ to render $E ( x , z ^ { \prime } ) / d = E ( x , z )$ . To specialize our work,we consider the case when both $g ( x )$ and $f ( x )$ are non-relativistic Breit-Wigner(BW）amplitude functions [9]

$$
g ( x ) = \frac { \Gamma _ { g } } { ( x - M _ { g } ) + i \Gamma _ { g } } \mathrm { ~ , ~ } f ( x ) = \frac { \Gamma _ { f } } { ( x - M _ { f } ) + i \Gamma _ { f } } \mathrm { ~ , ~ }
$$

where $M$ and $\Gamma$ are resonance's mass and width，respectively. This BW-form amplitude function is chosen because it's universally adopted in high energy physics. With the above forms of $g ( x )$ and $f ( x )$ , the real and imaginary components of $F ( x )$ are

$$
R _ { F } = \frac { \Gamma _ { f } [ \Gamma _ { g } \Gamma _ { f } + ( M _ { g } - x ) ( M _ { f } - x ) ] } { \Gamma _ { g } [ \Gamma _ { f } ^ { 2 } + ( M _ { f } - x ) ^ { 2 } ] } ,
$$

and

$$
I _ { F } = \frac { \Gamma _ { f } [ \Gamma _ { f } ( M _ { g } - x ) - \Gamma _ { g } ( M _ { f } - x ) ] } { \Gamma _ { g } [ \Gamma _ { f } ^ { 2 } + ( M _ { f } - x ) ^ { 2 } ] } \ .
$$

After some algebra,we get an interesting relation:

$$
R _ { F } ^ { 2 } + I _ { F } ^ { 2 } = a R _ { F } + b I _ { F } + c ,
$$

with

$$
a = \frac { \Gamma _ { g } + \Gamma _ { f } } { \Gamma _ { g } } , b = \frac { M _ { g } - M _ { f } } { \Gamma _ { g } } , c = - \frac { \Gamma _ { f } } { \Gamma _ { g } } .
$$

With Eq.(5), $E ( x , z )$ is recast as

$$
R _ { F } ( a R _ { z } ^ { 2 } + a I _ { z } ^ { 2 } + 2 R _ { z } ) + I _ { F } ( b R _ { z } ^ { 2 } + b I _ { z } ^ { 2 } - 2 I _ { z } ) + c ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } ) + 1 .
$$

The similar expression can be obtained for $E ( x , z ^ { \prime } )$ .Notice that $R _ { F }$ and $I _ { F }$ are functions in variable space ( $x$ space),while $R _ { z }$ and $I _ { z }$ are functions in parameter space $( z - d$ space), if we want for any $x$ ， $E ( x , z ^ { \prime } ) / d = E ( x , z )$ ， then the corresponding functions in parameter space as the coefficients of the functions in variable space should be equal. The requirement immediately yields:

$$
\begin{array} { r c l } { { } } & { { } } & { { a R _ { z ^ { \prime } } ^ { 2 } + a I _ { z ^ { \prime } } ^ { 2 } + 2 R _ { z ^ { \prime } } \ = \ d ( a R _ { z } ^ { 2 } + a I _ { z } ^ { 2 } + 2 R _ { z } ) \ , } } \\ { { } } & { { } } & { { b R _ { z ^ { \prime } } ^ { 2 } + b I _ { z ^ { \prime } } ^ { 2 } - 2 I _ { z ^ { \prime } } \ = \ d ( b R _ { z } ^ { 2 } + b I _ { z } ^ { 2 } - 2 I _ { z } ) \ , } } \\ { { } } & { { } } & { { c R _ { z ^ { \prime } } ^ { 2 } + c I _ { z ^ { \prime } } ^ { 2 } + 1 \ = \ d ( c R _ { z } ^ { 2 } + c I _ { z } ^ { 2 } + 1 ) . } } \end{array}
$$

In the light of the series of equations,it turns out that $d$ must satisfy a second order equation and there're two roots of it.One is the trivial solution with $d = 1$ and $z ^ { \prime } = z$ correspondingly,and the other one is

$$
\begin{array} { l } { { d = \displaystyle \frac { a ^ { 2 } + b ^ { 2 } + 4 c } { ( a - 2 R _ { z } c ) ^ { 2 } + ( b + 2 I _ { z } c ) ^ { 2 } } } } \\ { { z ^ { \prime } = \displaystyle \left( R _ { z } d - \frac { a ( d - 1 ) } { 2 c } \right) + \left( I _ { z } d + \frac { b ( d - 1 ) } { 2 c } \right) i } } \end{array}
$$

# B.Some special solutions

In this section we consider some other forms for $f ( x )$ and $g ( x )$ .The first example is from the KLOE experiment on $e ^ { + } e ^ { - } \to \omega \pi ^ { 0 }$ with both $\omega ~ \to ~ \pi ^ { + } \pi ^ { - } \pi ^ { 0 }$ and $\omega \to \gamma \pi ^ { 0 }$ . The cross section of $e ^ { + } e ^ { - } \to \omega \pi ^ { 0 }$ as a function of the center-of-mass energy, $\sqrt { x }$ , is parameterized as

$$
\sigma ( \sqrt { x } ) = \sigma _ { n r } ( \sqrt { x } ) \cdot \left| 1 - z \frac { M _ { \phi } \Gamma _ { \phi } } { D _ { \phi } ( \sqrt { x } ) } \right| ^ { 2 }
$$

in Ref.[10]，where $\sigma _ { n r } ( \sqrt { x } ) = \sigma _ { 0 } + \sigma ^ { \prime } ( \sqrt { x } - M _ { \phi } )$ is the bare cross section for the non-resonant process,parameterized as a linear function of $\sqrt { x }$ ; $M _ { \phi }$ ， $\Gamma _ { \phi }$ ，and $D _ { \phi } = M _ { \phi } ^ { 2 } - x - i M _ { \phi } \Gamma _ { \phi }$ are the mass, the width,and the inverse propagator of the $\phi$ meson, respectively. Here $z$ is a complex number which depicts the interference effect. Comparing with definition of $E ( x , z )$ ， $f ( x )$ and $g ( x )$ have the forms

$$
g ( x ) = - 1 \ , f ( x ) = \frac { M _ { \phi } \Gamma _ { \phi } } { M _ { \phi } ^ { 2 } - x - i M _ { \phi } \Gamma _ { \phi } } \ .
$$

The simple algebra yields $R _ { F } ^ { 2 } + I _ { F } ^ { 2 } = - I _ { F }$ ,which in turn gives

$$
\begin{array} { r c l } { { R _ { z ^ { \prime } } ^ { 2 } + I _ { z ^ { \prime } } ^ { 2 } + 2 I _ { z ^ { \prime } } \ = \ d ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } + 2 I _ { z } ) \ , } } \\ { { R _ { z ^ { \prime } } \ = \ d R _ { z } \ , } } \\ { { 1 \ = \ d \ . } } \end{array}
$$

With the last equality $d = 1$ ，the relation $R _ { z ^ { \prime } } = d R _ { z }$ implies $R _ { z ^ { \prime } } = R _ { z }$ ，then the first equation provides the other non-trivial solution

$$
z ^ { \prime } = R _ { z } - i ( I _ { z } + 2 ) \ .
$$

They are just the results acquired in Ref.[8] by another method.

As the second example,we consider the from

$$
g ( x ) = \frac { 1 } { x } \ , f ( x ) = \frac { 1 } { m ^ { 2 } - x + i m \Gamma } \ ,
$$

which is usually used to extract the resonance information of $\omega$ in fitting the data of $e ^ { + } e ^ { - } \to \pi ^ { + } \pi ^ { - }$ .Here $m$ （20 and $\Gamma$ indicate the mass and total decay width of the resonance. Accordingly, we obtain $R _ { F } ^ { 2 } + I _ { F } ^ { 2 } = - R _ { F } + \zeta I _ { F } ( \zeta =$ $m / \Gamma$ ),which in turn gives

$$
\begin{array} { r c l } { { R _ { z ^ { \prime } } ^ { 2 } + I _ { z ^ { \prime } } ^ { 2 } - 2 R _ { z ^ { \prime } } \ = \ d ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } - 2 R _ { z } ) \ , } } \\ { { \zeta ( R _ { z ^ { \prime } } ^ { 2 } + I _ { z ^ { \prime } } ^ { 2 } ) - 2 I _ { z ^ { \prime } } \ = \ d [ \zeta ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } ) - 2 I _ { z } ] \ , } } \\ { { 1 \ = \ d \ . } } \end{array}
$$

After some algebra,we get the other non-trivial solution

$$
z ^ { \prime } = { \frac { 2 + ( \zeta ^ { 2 } - 1 ) R _ { z } - 2 \zeta I _ { z } } { 1 + \zeta ^ { 2 } } } + i { \frac { 2 \zeta ( 1 - R _ { z } ) - ( \zeta ^ { 2 } - 1 ) I _ { z } } { 1 + \zeta ^ { 2 } } } \ .
$$

We consider a more general case,when $f ( x )$ and $g ( x )$ are any non-trivial functions,but their ratio must ensure that the real or imaginary component of $F ( x )$ is constant [13]. In any of these two cases,there exist two solutions. Specially speaking，when $F ( x ) = \kappa + i h ( x )$ with $h ( x )$ being a non-trivial function and $\kappa$ is a nonzero real constant,besides the trivial solution $d = 1$ and $z ^ { \prime } = z$ , there exist the other solution

$$
\begin{array} { l } { { d = \displaystyle \frac { 1 } { 4 \kappa ^ { 2 } ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } ) + 4 \kappa R _ { z } + 1 } } } \\ { { z = d [ 2 \kappa ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } ) + R _ { z } ] + i ( I _ { z } d ) } } \end{array}
$$

When $F ( x ) = h ( x ) + i \kappa$ , the other non-trivial solution is

$$
\begin{array} { c } { { d = \frac { 1 } { 4 \kappa ^ { 2 } ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } ) - 4 \kappa I _ { z } + 1 } } } \\ { { z ^ { \prime } = R _ { z } d + i d [ 2 \kappa ( R _ { z } ^ { 2 } + I _ { z } ^ { 2 } ) - I _ { z } ] } } \end{array}
$$

There are also other cases for which there exist two solutions, such as when $R _ { F }$ is a linear function of $I _ { F }$ ，or viceversa,we should not discuss them in details here.

# C. Constraint for amplitude functions

However, despite previous examples,it should be clear that the double-solution issue is not universal. Actually, it is easy to find out some forms of $f ( x )$ and $g ( x )$ ，in which no multiple-solutions can be found, $g ( x ) = x$ and $f ( x ) = x ^ { 3 } + i x ^ { 2 }$ is such an example.

That's why, although still far from the final answer, we want discuss what kind of constraints should be required in the cases when double-solutions can be found,i.e. what kind of amplitude functions, $f ( x )$ and $g ( x )$ in the preceding section，can guarantee the double-solutions. When we return to the study of two Breit-Wigner amplitudes,we notice that the relation in Eq.(5) is crucial for obtaining the double-solutions. At the same time, this relation just provides a constraint on $F ( x )$ ．And it turns out that all the special forms with double-solutions, found by us,obey this requirement.Then we would like to extend this relation，geometrically the Argand diagram of $F ( x )$ is a circle,as a general criteria for the wave functions in any physics process that may take doublesolutions.

# III. CHECK AND APPLICATION

As a cross check,let's consider an ad hoc example: the parameters of the two Breit-Wigner functions and one solution are set as:

$$
M _ { g } = 3 . 0 , \Gamma _ { g } = 0 . 4 , M _ { f } = 2 . 1 , \Gamma _ { f } = 0 . 1 , z = 1 - i .
$$

Using the aforementioned method,we can find another solution,which is exactly repeated by fitting with minimal likely-hood method. The comparison of the results are shown in Table I.

TABLE I:Comparison between exact solution and fit process in the case of sum of two simple Breit-Wigner functions. For fit,Toy MC is used to generate l0oo0 events data sample, the minimal likely-hood method is applied,all of this is realized in RooFit frame.   

<html><body><table><tr><td>Item</td><td>Input</td><td>Another sol.</td><td>Fit I</td><td>Fit II</td></tr><tr><td>d</td><td>1</td><td>0.529</td><td>1</td><td>1</td></tr><tr><td>Rz</td><td>1</td><td>0.647</td><td>1.019 ± 0.054</td><td>0.644 ± 0.040</td></tr><tr><td>I</td><td>-1</td><td>1.588</td><td>-1.019 ± 0.060</td><td>1.601 ±0.028</td></tr><tr><td>Mg</td><td>3.0</td><td>3.0</td><td>3.011 ± 0.010</td><td>3.011 ± 0.010</td></tr><tr><td>Ig</td><td>0.4</td><td>0.4</td><td>0.402 ± 0.010</td><td>0.402 ± 0.010</td></tr><tr><td>Mf</td><td>2.1</td><td>2.1</td><td>2.101 ± 0.003</td><td>2.101 ± 0.003</td></tr><tr><td>Tf</td><td>0.1</td><td>0.1</td><td>0.101 ±0.003</td><td>0.101 ± 0.003</td></tr></table></body></html>

This example indicates that in principle, the minimization can be used as a feasible approach to find the multisolution from the experimental data.

It is obvious, for two Breit-Wigner amplitudes case, if one solution is obtained by fitting, the other one can be readily and analytically obtained by applying Eq.(8). This definitely saves a lot of time and energy. However due to the complexity of the expressions in practice, the solution has to be obtained from following numerical method.Firstly,we draw the $F ( x )$ in the complex plane to check whether it is a circle,and obtain parameters $a , b , c$ in relation $R _ { F } ^ { 2 } + I _ { F } ^ { 2 } = a R _ { F } + b I _ { F } + c$ by three randomly selected points if the answer is positive.With $a , b , c$ obtained numerically we can derive the other solution with Eq.(8) as before.We illustrate this method by the examples which are selected from the initial state measurement at Babar and Belle [1,12],where the $\pi ^ { + } \pi ^ { - } \psi ( 2 s )$ and $\pi ^ { + } \pi ^ { - } J / \psi$ invariant mass distributionSare described by two coherent resonances.The cross

sections are formulated as

$$
\sigma ( s ) = | B W _ { 1 } ( s ) + B W _ { 2 } ( s ) \cdot e ^ { i \phi } | ^ { 2 } ,
$$

where $B W _ { 1 }$ and $B W _ { 2 }$ represent the two resonances and $\phi$ is the relative phase between them. And the BreitWigner form of a single resonance in these two papers is

$$
B W ( s ) = \sqrt { { \frac { M ^ { 2 } } { s } } } { \frac { \sqrt { 1 2 \pi \Gamma _ { e ^ { + } e ^ { - } } B ( R \to f ) \Gamma _ { t o t } } } { s - M ^ { 2 } + i M \Gamma _ { t o t } } } \sqrt { { \frac { P S ( s ) } { P S ( M ) } } } \ ,
$$

where $M$ is the mass of the resonance, $\Gamma _ { t o t }$ and $\Gamma _ { e ^ { + } e ^ { - } }$ are the total width and partial width to $e ^ { + } e ^ { - }$ respectively, $B ( R  f )$ is the branching fraction of $R$ decays into final state $f$ ，and $P S ( s )$ is the three-body decay phase space factor.Using the first solution as input we obtain the other solution as before,and the results are shown in TABLE II. From TABLE II it's clear our results repeat what from the fit process very well,and we consider that is a justification of our method.

TABLE II:Comparison of exact solutions with fit results for two real experimental measurements Refs.[1,12].   

<html><body><table><tr><td>Items</td><td>BTe+e-(R1) BTe+e-(R2)</td></tr><tr><td>fit results in Ref.[1]</td><td>12.4 20.6</td></tr><tr><td>12.8</td><td>-111 20.4 -111</td></tr><tr><td>by our method fit results in Ref.[12]</td><td></td></tr><tr><td>12.3</td><td>5.9 -74</td></tr><tr><td>by our method 12.3</td><td>6.0 -74</td></tr></table></body></html>

# IV.DISCUSSION

Asbeen found,when the measured distribution is described by $| g ( x ) + z f ( x ) | ^ { 2 } / d$ and $F ( x ) = f ( x ) / g ( x )$ fulfill the relation of Eq.(5)，i.e.it's a circle in complex plane,there are and only are two non-trivial solutions.It's also been proved that if $f ( x )$ and $g ( x )$ are both simple Breit-Wigner, this relation is exactly satisfied and Eq.(8) can be utilized to derive one solution from the other obtained solution analytically. For other transmogrified Breit-Wigner functions have been considered, some of the forms are very complex, the relation of Eq.(5） is still satisfied by $F ( x )$ by numerical checks.So there will be double solutions for these forms also and with $a , b , c$ obtained numerically the other solution can be derived by using the same method.The excellent consistence between our solutions and experimental fit results justifies this method.

We also notice that for both solutions, the parameters of each resonance are the same but the normalization factors are different. That implies the couplings to decay channels are different for different solutions and some experimental reports may not be complete if only one solution was reported. So we suggest any experiment measurement with potential multiple solutions problem should redo the analysis to find other solutions,and our method would be helpful to indicate the results. Finally, we should point out that from Eq.(4) we may find more conditions where double solutions exist，for example if the real or virtual component of $F ( x )$ is zero or the real component of $F ( x )$ is a linear function of the virtual one, there should be double solutions too.However, they are not normal in high energy physics so we don't discuss it in detail here.Furthermore,only the sum of two coherent amplitudes has been considered in this paper, the generalization to more amplitudes are still in progress.

10775412，No．10825524，No．10935008，andNo. 11005115, the Instrument Developing Project of the Chinese Academy of Sciences under Contract No. YZ200713, Major State Basic Research Development Program under Contracts No. 2009CB825203 and No. 2009CB825206, Knowledge Innovation Project of the Chinese Academy of Sciences under Contract No. KJCX2-YW-N29 and Innovation Project of Youth Foundation of Institute of High Energy Physics under Contract No.H95461B0U2.

# Acknowledgments

This work is supported in part by the National Natural Science Foundation of China under Contracts No

[1] C.Z.Yuan et al. [Belle Collaboration],Phys.Rev.Lett. 99,182004(2007） [arXiv:0707.2541 [hep-ex]].   
[2] X.L.Wang et al. [Belle Collaboration],Phys.Rev.Lett. 99,142002（2007）[arXiv:0707.3699 [hep-ex]].   
[3]H.X.Chen [BES Collaboration]，Int.J.Mod.Phys.A 22,637 (2007).   
[4] C.Z.Yuan,X.H.Mo and P.Wang, Int.J.Mod.Phys. A 25,5963(2010)[arXiv:0911.4791 [hep-ph]].   
[5] X.H. Mo,C. Z. Yuan and P.Wang, Phys. Rev.D 82, 077501(2010） [arXiv:1007.0084 [hep-ex]].   
[6] C.P. Shen and C. Z. Yuan,[arXiv:0911.1591 [hep-ex]].   
[7]A.D.Bukin,[arXiv:0710.5627[physics.data-an]].   
[8] C.Z. Yuan,X.H. Mo and P. Wang, Chin. Phys.C 35, 543（2011） [arXiv:1009.0155 [hep-ex]].   
[9] D.H.Perkins,“Introduction to high energy physics”, p56,Cambridge,UK:Cambridge Univ.Pr.(200O) 426p,   
[10] F.Ambrosino et al.[KLOE collaboration],Phys.Lett.B 669,223 (2008) [arXiv:0807.4909 [hep-ex]].   
[11]M.Davier et al.,Eur.Phys.J.C 66,127 (2010) [arXiv:0906.5443 [hep-ph].   
[12] Z.Q.Liu, X. S.Qin and C. Z.Yuan, Phys.Rev.D 78, 014032(2008）[arXiv:0805.3560 [hep-ex]].   
[13] This can be realized.For example,if we write $f ( x ) = $ （204号 （20 $\rho _ { f } ( x ) e ^ { i \theta _ { f } ( x ) }$ and $g ( x ) = \rho _ { g } ( x ) e ^ { i \theta _ { g } ( x ) }$ ，where $\rho _ { f , g } ( x )$ and $\theta _ { f , g } ( x )$ are any non-trivial functions.As long as there exist relations $\rho _ { f } ( x ) = \rho _ { g } ( x ) \cdot \sqrt { h ^ { 2 } ( x ) + \kappa ^ { 2 } }$ and $\theta _ { f } ( x ) =$ $\theta _ { g } ( x ) + \mathrm { t a n } ^ { - 1 } ( h ( x ) / \kappa ) + 2 \pi n$ （ $n$ : any integer), it always has $F ( x ) = \kappa + i h ( x )$