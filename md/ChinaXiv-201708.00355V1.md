# The four-loop non-planar cusp anomalous dimension in ${ \mathcal N } = 4$ SYM

Rutger H. Boels\* II.Institut fir Theoretische Physik,Universitat Hamburg, Luruper Chaussee 149,D-22761 Hamburg，Germany

Tobias Hubert Naturwissenschaftlich-Technische Fakultat, Universitit Siegen, Walter-Flex-Str. 3， 57068 Siegen，Germany

Gang Yang‡ CASKey Laboratory of Theoretical Physics，Institute of Theoretical Physics, Chinese Academy of Sciences，Beijing 100190，China (Dated:May 10,2017)

The light-like cusp anomalous dimension is a universal function that controls infrared divergences in quite general quantum field theories. In the maximally supersymmetric Yang-Mills theory this function is fixed fully by integrability to the three-loop order.At four loops a non-planar correction appears which we obtain for the first time from a numerical computation of the Sudakov form factor.Key ingredients are widely applicable methods to control the number-theoretic aspects of the appearing integrals. Our result shows explicitly that quadratic Casimir scaling breaks down at four loops.

PACS numbers:11.25.Db，12.38.Bx

# INTRODUCTION

Quantum field theory is used throughout physics due to its unrivalled power to perform systematic computations. Connecting the calculated quantities to observed experimental variables,however,can be complicated.Perturbation theory for the theory of the strong nuclear force,quantum chromodynamics (QCD),for instance can famously only be trusted on very small length scales[1，2]. The physical detectors,however，involve vastly larger length scales where the perturbation theory is guaranteed to break down.A central role in the analysis is played by universal functions,a prime example of which is known as the light-like cusp anomalous dimension (CAD).

The universality of the CAD makes it appear in many contexts,e.g.(1)By definition,it refers to the anomalous dimension of a Wilson loop with a light-like cusp [3,4]. (2)It provides the leading infrared (IR) behavior of onshell amplitudes and is an essential ingredient in constructing amplitudes,see e.g.[5]. (3) It determines the logarithmic growth of anomalous dimensions of high-spin Wilson operators. Such operators naturally appear in the operator product expansion description of deep inelastic scattering processes in QCD in the so-called large Bjorken limit,see e.g.[6].(4) It is related to the gluon Regge trajectory,and can be obtained from the so-called BFKL equation, see e.g. [7]. (5) Via the AdS/CFT correspondence [8]，cusped Wilson operators in the planar limit admit a dual description in terms of spinning strings in a curved background[9]. There is therefore ample direct physical motivation to compute this function.

In $\mathcal { N } = 4$ super Yang-Mills (SYM) theory, the planar cusp anomalous dimension is known non-perturbatively via the so-called BES equation [1O] based on ideas of the AdS/CFT correspondence and integrability [11]. Consistency with field-theory computations through to four loops has been obtained at the planar level [12,13],and also confirmed by the strong coupling two-loop string computations [14]. There is an intriguing connection between $\mathcal { N } = 4$ SYM and QCD results,via the maximal transcendentality property: the $\mathcal { N } = 4$ anomalous dimensions correspond to the “leading-transcendentality" contribution in QCD [15,16]. Inspired by this,the threeloop $\mathcal { N } = 4$ results were first obtained in [16] using the three-loop QCD results [17].

At four loops in gauge theories with matter felds in the adjoint representation the first correction beyond the planar limit enters into the CAD.This Letter contains to our knowledge the first computation of this quantity. In perturbation theory four-loop non-planar integrals have to date proven to be largely prohibitively complicated. Non-planar corrections are also hard to analyse directly within the AdS/CFT correspondence as they correspond to string loop corrections,and the role of integrability beyond the planar limit is unclear. Moreover,a quite general conjecture has been posed by extrapolating threeloop results that the non-planar part of the CAD vanishes [18] in any theory. This is usually called quadratic Casimir scaling of the CAD,and plays an important role in the IR factorisation in gauge theories [18-23]. This scaling is known to break down in planar ${ \mathcal N } = 4$ at strong coupling,as well as through instanton effects [24];in this Letter the approach will be strictly perturbative.

The minimal observable that contains the cusp anomalous dimension is the Sudakov form factor.In maximally supersymmetric Yang-Mills theory this is a correlator of a member of the stress-tensor multiplet with two on-shell massless states. The first computation of the two-loop correction to the Sudakov form factor in $\mathcal { N } = 4$ SYM appeared in [25]. The three-loop correction to the QCD result was studied in a series of papers [26-3O]. In [31] these results were fine-tuned for the form factor in ${ \mathcal N } = 4$ SYM to the three-loop order. The integrand for the fourloop Sudakov form factor in $\mathcal { N } = 4$ SYM was derived in [32] based on the duality between color and kinematics,and its reduction to master integrals was presented in [33]. Recently progress for planar corrections at four loops in QCD was reported in [34-36]. For the five-loop integrand in $\mathcal { N } = 4$ SYM see [37].

# REVIEW

# Form factor and cusp anomalous dimension

The Sudakov form factor involves only a single scale $q ^ { 2 }$ which is the Lorentzian norm of the sum of the two onshell state momenta,i.e. $q ^ { 2 } = ( p _ { 1 } + p _ { 2 } ) ^ { 2 }$ with $p _ { 1 } ^ { 2 } = p _ { 2 } ^ { 2 } =$ 0.Dimensional analysis and maximal supersymmetry fix the form factor $\mathcal { F } ^ { ( l ) }$ at $\it { l }$ loops to be given by

$$
\mathcal { F } ^ { ( l ) } = \mathcal { F } ^ { \mathrm { t r e e } } g ^ { 2 l } ( - q ^ { 2 } ) ^ { - l \epsilon } F ^ { ( l ) } ,
$$

where the coupling constant is normalised as $\begin{array} { r l } { g ^ { 2 } } & { { } = } \end{array}$ 9²MNe(4πe-7E)e.The form factor has no ultraviolet (UV) divergences since the operator is protected, leaving only IR divergences. If dimensional regularisation with （204号 $D = 4 - 2 \epsilon$ is used to regulate the latter, $F ^ { ( l ) }$ is a purely numerical function of gauge group invariants and $\epsilon$ . This function is related to the cusp anomalous dimension Ycusp at $\it { l }$ loops by [38-41],

$$
( \log F ) ^ { ( l ) } = - \left[ \frac { \gamma _ { \mathrm { c u s p } } ^ { ( l ) } } { ( 2 l \epsilon ) ^ { 2 } } + \frac { { \mathcal G } _ { \mathrm { c o l l } } ^ { ( l ) } } { 2 l \epsilon } + \mathrm { F i n } ^ { ( l ) } \right] + \mathcal O \left( \epsilon \right) .
$$

At $\it { l }$ loops the planar (i.e. $N _ { c } ^ { l }$ leading-color in $S U ( N _ { c } )$ gauge theory) part of $F ^ { ( l ) }$ has leading divergence $\propto 1 / \epsilon ^ { 2 l }$ = This function needs to be expanded down to $\epsilon ^ { - 2 }$ to extract the $\it { l }$ -loop CAD,and also higher terms in the Laurent expansion in $\epsilon$ from lower-loop contributions are required. The gauge group dependence of the CAD shows that the first occurrence of non-planar (i.e.subleadingcolor) corrections is at four loops,see e.g. [32],due to the appearance of a quartic Casimir invariant. This invariant therefore breaks quadratic Casimir scaling explicitly. The relation between form factor and cusp anomalous dimension for the non-planar part at four loops is

$$
\left[ F ^ { ( 4 ) } \right] _ { \mathrm { N P } } = - \frac { \gamma _ { \mathrm { c u s p , \mathrm { \scriptsize ~ N P } } } ^ { ( 4 ) } } { ( 8 \epsilon ) ^ { 2 } } + \mathcal { O } \left( \epsilon ^ { - 1 } \right) ,
$$

i.e. $\big [ F ^ { ( 4 ) } \big ] _ { \mathrm { N P } }$ has only a double pole in $\epsilon$ . However, individual integrals that contribute to $\big [ F ^ { ( 4 ) } \big ] _ { \mathrm { N P } }$ will typically show the full $1 / \epsilon ^ { 8 }$ divergence.

The general CAD is expressible as a rational-coeffcient polynomial of Riemann Zeta values $\zeta _ { n }$ ，or their multiindex generalizations, Sn1,n2.. ，known as multiple zeta values (MZVs) (see e.g. [42]). These numbers have a transcendentality degree which is the sum of their indices, $\textstyle \sum _ { i } n _ { i }$ .At $\it { l }$ loops,the planar CAD in $\mathcal { N } = 4$ SYM has uniform transcendentality degree $2 l - 2$ ．At four loops for instance,the planar CAD in $\mathcal { N } = 4$ SYM has been computed [12,13] to be

$$
\gamma _ { \mathrm { c u s p , P } } ^ { ( 4 ) } = - 1 7 5 2 \zeta _ { 6 } - 6 4 \zeta _ { 3 } ^ { 2 } .
$$

We will provide strong evidence that also the non-planar CAD is of uniform transcendentality six at four loops.

In QCD,the CAD has the same maximal transcendentality degree as in $\mathcal { N } = 4$ ，but also contains lower transcendentality degree constants.The coefficient of the maximal transcendentality coefficients match between planar $\mathcal { N } = 4$ and QCD,an observation known as the maximal transcendentality principle.

# Integrands,integrals,integral relations

The non-planar part of the Sudakov form factor in （204 $ { \mathcal { N } _ { \mathrm { ~ \scriptsize ~ = ~ } 4 } }$ SYM was obtained as a linear combination of a number of four-loop integrals in [32] using colorkinematics duality [43,44]. The integrals take the generic form

$$
I = ( q ^ { 2 } ) ^ { 2 } \int d ^ { D } l _ { 1 } \ldots d ^ { D } l _ { 4 } { \frac { N ( l _ { i } , p _ { j } ) } { \prod _ { k = 1 } ^ { 1 2 } D _ { k } } } ,
$$

where $D _ { i }$ are propagators and the numerators $N ( l _ { i } , p _ { j } )$ are quadratic polynomials ofLorentz products of the four independent loop and two independent external on-shell momenta. The explicit form of the integrals for the problem at hand can be found in 32].There are 14 distinct integral topologies that contribute to the non-planar CAD, labelled(21）-(34) in the given reference,each with 12 internal lines.These coordinates and the full parametrisation of the integrals as in [33] will be used throughout.

The integrands are identified up to terms that integrate to zero.A special class of these are generated by infinitesimal linear reparametrisations of the loop momenta and are known as integration-by-parts (IBP) identities [45,46].Using these identities the form factor was simplified in [33] using the Reduze code [47]. A particular subset of such relations,dubbed‘rational IBP’relations and obtained in [48],will play an important role for the problem at hand. Note that integral relations due to graph symmetries are a particular subset of the rational IBP relations.Although simpler integrals emerged in [33] compared to [32], these have evaded integration so far due to their overwhelming complexity. The first obstacle to computing the CAD is therefore to find a complete set of integrals which are each simple enough to integrate.

# UNIFORMLYTRANSCENDENTALINTEGRALS

The key idea is to find a representation of the four-loop form factor such that all integrals have uniform transcendentality if the dimensional regularisation parameter is assigned transcendentality $- 1$ . Such integrals will be referred to as UT integrals. Such a representation of the form factor makes manifest the expected maximal transcendentality property of planar $\mathcal { N } = 4$ SYM,and has been achieved at three loops in [31]. Crucially for our purposes,the UT integrals turn out to be much simpler to integrate than generic integrals.

Beyond explicit computation，there are various ways to prove a general integral is a UT integral:

•A UT integral can be expressed in the so-called dLog form [49, 50].   
·A set of integral basis that are all UT integrals can lead to certain simple differential equations [51].   
· The leading singularities， or equivalently，the residues at all poles of a UT integral must always be a constant [34, 50].

We have obtained a dLog form for instance in topologies(21) and (23) for the integrals with numerator

$$
\left[ ( l _ { 3 } - p _ { 1 } ) ^ { 2 } \right] ^ { 2 }
$$

each.The dLog form of the topology-(21) integral as well as its analytic result were also obtained in [34].Another example where it was possible to derive a dLog form is topology（28） with numerator

$$
( l _ { 3 } - l _ { 4 } - p _ { 2 } ) ^ { 2 } \times ( l _ { 3 } - p _ { 1 } ) ^ { 2 } .
$$

Finding a dLog form in general,however, is a difficult problem. Moreover,the differential equations method is not directly applicable for the Sudakov form factor since it is a single-scale problem (see [34, 52] for a workaround). The last criterion in the above bullet-point list，however,allows an algorithm. For this the fourdimensional loop momenta are parametrised such that only scalar integration parameters remain,e.g.as

$$
l _ { 1 } = \alpha _ { 1 } p _ { 1 } + \alpha _ { 2 } p _ { 2 } + \alpha _ { 3 } q _ { 1 } + \alpha _ { 4 } q _ { 2 } ,
$$

where $p _ { 1 }$ and $p _ { 2 }$ are the external on-shell momenta,and （204 $q _ { 1 }$ ， $q _ { 2 }$ can be chosen as the two complex solutions to

$$
q _ { i } ^ { 2 } = q _ { i } \cdot p _ { j } = 0 \quad \forall i , j \quad { \mathrm { a n d } } \quad q _ { 1 } \cdot q _ { 2 } = p _ { 1 } \cdot p _ { 2 }
$$

With this,the integration volume changes to

$$
\int d ^ { 4 } l _ { 1 } \left( . . . \right) = ( p _ { 1 } \cdot p _ { 2 } ) ^ { 2 } \int \prod _ { i = 1 } ^ { 4 } d \alpha _ { i } \left( . . . \right) .
$$

In this so-called parametric form, the leading singularity is studied by computing subsequent residues for all occurring scalar parameters(16 at four loops).For this, one needs to choose an order of taking residues in the scalar parameters.If,after taking a residue in a particular parameter,one encounters other than a simple pole in a remaining parameter, the integral is not UT.In principle,there are $1 6 ! \sim 2 \times 1 0 ^ { 1 3 }$ different orders in which the residues can be taken. We will explain below how we deal with this in practice.

Besides checking that an integral at hand is UT or not,this procedure can be used to constrain the space of potential UT integrals of a given topology. We can start with an Ansatz of a linear combination of momentum products of mass dimension four.Given a set of integrals for a given topology one can see if one or more members fail the UT test for a particular randomly chosen order of residues.If a quadratic or higher pole is found,one canderive a linear constraint on the set of coefficients in the Ansatz to evade the pole. Solving these constraints gives a smaller set of integrals.In the case at hand about a thousand such random checks typically yields a list of candidate UT integrals that does not easily yield further constraints.Note a related strategy was used in [34, 50]. Through this strategy a set of candidate integrals was obtained for each topology.

For ease of integration it is advantageous to have a form of the numerator as a product of two factors,both quadratic in momenta. To find linear combinations of UT candidate integrals with this property one writes a product-type Ansatz and derives a set of quadraticconstraint equations.In some cases,a solution may not exist or may not be useful. For the non-planar four-loop form factor, this happens in topologies (26) and (25), respectively. Here the Ansatz can be widened by adding integrals with two fewer propagators (i.e. two pinched lines).

An example result is the topology (25) integral with numerator

$$
\begin{array} { r } { \left[ ( p _ { 1 } - l _ { 5 } ) ^ { 2 } + 2 ( l _ { 4 } - l _ { 5 } ) ^ { 2 } + ( l _ { 3 } - l _ { 4 } ) ^ { 2 } - ( l _ { 3 } - l _ { 5 } ) ^ { 2 } \right. } \\ { \left. - ( p _ { 1 } - l _ { 4 } ) ^ { 2 } \right] ^ { 2 } - 4 ( l _ { 4 } - l _ { 5 } ) ^ { 2 } ( p _ { 1 } - l _ { 3 } + l _ { 4 } - l _ { 5 } ) ^ { 2 } . } \end{array}
$$

This integral captures the full 12-line context of the nonplanar form factor in this topology.

Having obtained integrals which are product-form UT candidates - possibly up to a ten-line contribution - one needs to express the form factor as a linear combination of them. Since the form factor is expected to be uniformly transcendental itself,this linear combination must involve only rational numbers $-$ not $\epsilon$ .Theafore mentioned ‘rational IBP'relations obtained in [48] prove extremely useful for this task.

The first result of this article is that the non-planar part of the four-loop form factor obtained in [33] can be expressed in terms of 23 UT candidate integrals only, providing supporting evidence for maximal transcendentality in the non-planar sector.

The linear combination of product-form UT integrals that builds the non-planar four-loop form factor is not unique owing to the rational IBP relations between integrals. Our choice of basis focuses on minimising the number of different product-type integrals,and is guided by the condition that the appearing integrals can be computed numerically. The full list of all usedUT candidate integrals including their results will be provided in an accompanying long write-up [53].

Note that besides those integrals for which an explicit dLog form was obtained, all UT candidates have passed a significant number of residue checks,e.g. the two most complicated ones are in topology (26）and have passed $1 0 ^ { 5 }$ such checks. This provides strong evidence that they are indeed UT integrals.

# NUMERICALINTEGRATION

There is a variety of techniques available to compute loop integrals both analytically and numerically, see e.g.[54] for an overview. Here mainly sector decomposition and Mellin-Barnes (MB) integration have been used, as well as an exact integral result of topology (21) [34].

Two computer implementations of sector decomposition [55] have been used:mostly FIESTA [56-59],with cross-checks for simpler integrals using SecDec [60-62]. The numerical integration is performed using the VEGAS algorithm [63] as implemented in the CUBA library [64].To check on the reported uncertainties,several runs with different integration settings were performed. We observe that error bars reported by FIESTA scale with $1 / \sqrt { N _ { s } }$ ,with $N _ { s }$ the number of sampling points (typically in the range of a few up to several 1oo millions).Moreover，uncertainties given by FIESTA tend to be rather over- than underestimated which can be seen by comparing to MB or analytic results,and by the fact that fluctuations upon increasing $N _ { s }$ are well within the reported error bars.This error will therefore be interpreted as the standard deviation of a Gaufian distribution,and errors are added in quadrature.Further details will be provided in [53]. A feature of the numerical integration that can be observed is that UT integrals usually generate considerably fewer integration terms within FIESTA compared to non-UT siblings of comparable complexity, even though for instance single-sector contributions are not UT separately.

A second integration technique applied here is MB integration. Several automated tools exist，such as MB tools [65,66] and AMBRE [67-69]. Given an integral of the form (5)，one can derive a wide variety of MB representations,and the main challenge is to derive valid MB representations for crossed four-loop topologies. But even if the latter is possible,these representations often feature prohibitively complicated integrals for the problem at hand.Here efficient MB representations for a subset of(planar and crossed) integrals have been derived by means of a hybrid of the loop-by-loop approach and using the $\mathcal { F }$ and $\boldsymbol { \mathcal { U } }$ graph polynomials (we refer again to [53] for details).If an efficient MB representation is available,the precision of the integrals is typically three to four orders of magnitude better than FIESTA.We have cross-checked all our MB results with FIESTA.

# Results

Our results for the form factor up to an overall fac tor are summarised in table I. As expected on physical grounds, the first six orders of expansion of the nonplanar form factor cancel well within error bars.

TABLE I.Non-planar form factor.   

<html><body><table><tr><td>∈order</td><td>-8</td><td>-7</td><td>-6</td><td>-5</td><td>-4</td><td>-3</td><td>-2</td></tr><tr><td>result</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0.01056</td><td>1.5931</td></tr><tr><td>uncertainty</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>±0.02995</td><td>±0.3362</td></tr></table></body></html>

For the leading non-trivial poles, $\epsilon ^ { - \{ 8 , 6 , 5 , 4 \} }$ , the precision in each integral is good enough to write the number as a rational multiple of $\{ 1 , \zeta _ { 2 } , \zeta _ { 3 } , \zeta _ { 4 } \}$ ,respectively.Note the $\epsilon ^ { - 7 }$ coefficient should vanish for each integral, and indeed does well within error bars.The coefficients of e-{8,6,5,4,3} can be non-zero in individual integrals but must cancel in the linear combination of the form factor, which is indeed the case.We emphasize that the vanishing of all these poles provides a very strong consistency check for the computation,and gives further support for our error analysis.

The non-trivial coefficient for the non-planar form factor at order $\epsilon ^ { - 2 }$ yields the sought-after non-planar fourloop CAD:

$$
\gamma _ { \mathrm { c u s p , ~ N P } } ^ { ( 4 ) } = - 3 0 7 2 \times ( 1 . 5 9 3 1 \pm 0 . 3 3 6 2 ) \frac { 1 } { N _ { c } ^ { 2 } } ,
$$

where $3 0 7 2 = 2 \times 2 4 \times 6 4$ is the normalization factor including that from the permutational sum,the color factor [32],and the denominator of (3),respectively. This is the second major result of this paper. The naive significance of a deviation from zero is $4 . 7 \sigma$ .Note that evenwith a more conservative error estimate obtained by adding uncertainties from the individual UT integrals linearly, we still have 1.5931 $\pm$ 0.9813 which is significantly non-zero.

$\gamma _ { \mathrm { c u s p , P } } ^ { ( 4 ) } \sim - 1 8 7 5$ we see that the non-planar CAD has the same sign.If Nc = 3 is used, its central value becomes Yeusp, NP \~ $- 5 4 4$ ,i.e.the planar contribution is a factor of $3 \textrm { -- } 4$ （20 larger.

these that can be integrated relatively easily using methods that at face value have little to do with number theory.In other words,simplicity is persistent in Feynman integrals.

# DISCUSSION

In this Letter we present the first computation of the non-planar correction to the cusp anomalous dimension in the maximally supersymmetric Yang-Mills theory, which first starts at four loops.

While integrating a generic set of four-loop form factor master integral remains quite challenging,a key idea leading to the present breakthrough is to express the form factor in terms of uniformly transcendental integrals.The UT basis can be constructed algorithmically. While a generic integral contains mixed transcendentality degrees,the UT integrals contain only numbers of fixed (maximal for ${ \mathcal { N } } = 4$ SYM) transcendentality in each order of the $\epsilon$ expansion.What is interesting and deserves further study is that such simplicity is inherited in sector decomposition,where each sector integral is no longer UT separately. Once a good set of (candidate) UT basis integrals is determined, the full form factor can be expressed in this basis by using a simple subset of the IBP relations or,in principle,directly by unitarity cuts.In the case at hand,our results provide strong evidence for the maximal transcendentality of the four-loop non-planar form factor in ${ \mathcal N } = 4$ SYM.In particular this implies strongly that the four-loop CAD can be written as a rational linear sum of $\zeta _ { 6 }$ and $\zeta _ { 3 } ^ { 2 }$ . The UT basis finding algorithm is widely applicable.An immediate interesting application of already obtained results would be to four-loop propagator integrals in QCD, see e.g. [70]. A UT basis in QCD would always involve pre-factors with non-negative powers of $\epsilon$ , simplifying computations potentially drastically, see [71] for similar ideas.

Based on the UT basis,a numerical computation has also yielded the first information on the value of the CAD in ${ \mathcal N } = 4$ ,which is statistically significantly non-zero.In particular,our result indicates that quadratic Casimir scaling breaks down at four loops in this theory and is therefore not expected to hold in any other theory such as QCD.Direct further research directions include improving precision at order $1 / \epsilon ^ { 2 }$ and computing further orders in the $\epsilon$ -expansion which contain the so-called collinear anomalous dimension.Computing the non-planar CAD in other theories such as QCD at four loops is a prime further target.It would be extraordinarily interesting to extend integrability arguments to the non-planar CAD in $\mathcal { N } = 4$ ；our weak-coupling result provides the first data-point for this effort.

A more general lesson is that by focusing on the number-theoretically simple integrals we obtained a set of

# ACKNOWLEDGEMENTS

The authors would like to thank Dirk Seidel for collaboration in the early stages of this project as well as BerndKniehl and Sven-Olaf Moch for discussions and encouragement.This work was supported by the German Science Foundation (DFG）within the Collaborative Research Center 676“Particles,Strings and the EarlyUniverse”.GY is supported in part by the Chinese Academy of Sciences (CAS) Hundred-Talent Program, by the Key Research Program of Frontier Sciences of CAS,and by Project 11647601 supported by NSFC.

\* Rutger.Boels@desy.de † huber@physik.uni-siegen.de t yangg@itp.ac.cn   
[1]D. J. Gross and F. Wilczek, Phys.Rev.Lett.30,1343(1973).   
[2]H.D.Politzer,Phys.Rev.Lett.30,1346(1973).   
[3] A.M. Polyakov,Nucl. Phys.B164,171 (1980).   
[4] G.P.Korchemsky and A.V.Radyushkin, International Seminar:Quarks 86 Tbilisi,USSR，April 15-17,1986, Phys.Lett.B171, 459 (1986).   
[5]Z. Bern, L.J.Dixon, and V. A. Smirnov, Phys.Rev.D72,085001 (2005), arXiv:hep-th/0505205 [hep-th].   
[6] G.P. Korchemsky,Mod. Phys. Lett.A4,1257 (1989).   
[7]A. V. Kotikov and L. N. Lipatov, Nucl.Phys.B582,19 (2000), arXiv:hep-ph/0004008 [hep-ph].   
[8]J.M. Maldacena,Int. J. Theor.Phys.38,1113 (1999), [Adv. Theor. Math. Phys.2,231(1998)], arXiv:hep-th/9711200 [hep-th].   
[9]S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, Nucl. Phys.B636,99 (2002), arXiv:hep-th/0204051 [hep-th].   
10] N. Beisert, B. Eden, and M. Staudacher, J. Stat.Mech.0701, P01021 (2007), arXiv:hep-th/0610251 [hep-th].   
11] N.Beisert et al.,Lett.Math.Phys.99,3 (2012), arXiv:1012.3982 [hep-th].   
12] Z.Bern，M.Czakon，L.J.Dixon，D.A.Kosower, and V. A. Smirnov，Phys.Rev.D75,085010 (2007), arXiv:hep-th/0610248 [hep-th].   
13] J.M.Henn and T.Huber，JHEP 09,147(2013), arXiv:1304.6418 [hep-th].   
14] R.Roiban and A．A.Tseytlin，JHEP 11,O16 (2007), arXiv:0709.0681 [hep-th].   
15]A.V.Kotikov and L. N. Lipatov, Nucl.Phys.B661,19 (2003)， [Erratum: Nucl. Phys.B685,405(2004)], arXiv:hep-ph/0208220 [hep-ph].   
[16] A．Kotikov，L.Lipatov, A.Onishchenko, and V. Velizhanin, Phys.Lett.B595, 521 (2004), arXiv:hep-th/0404092 [hep-th].   
[17] S. Moch, J. A. M. Vermaseren, and A. Vogt, Nucl. Phys.B688,101 (2004), arXiv:hep-ph/0403192 [hep-ph].   
[18] T.Becher and M.Neubert,JHEP 06,081 (2009),[Erratum:JHEP11,024(2013)],arXiv:0903.1126 [hep-ph].   
[19] E.GardiandL. Magnea,JHEP 03,079 (2009), arXiv:0901.1091 [hep-ph].   
[20] L. J. Dixon, Phys. Rev. D79, 091501 (2009), arXiv:0901.3414 [hep-ph].   
[21] T. Becher and M. Neubert, Phys.Rev.D79,125004 (2009)， [Erratum: Phys. Rev.D80,109901(2009)],arXiv:0904.1021 [hep-ph].   
[22] L.J.Dixon， E.Gardi, andL.Magnea, JHEP 02,081 (2010),arXiv:0910.3653 [hep-ph].   
[23] V.Ahrens, M.Neubert, andL. Vernazza, JHEP 09,138 (2012),arXiv:1208.4847 [hep-ph].   
[24] G.P. Korchemsky， (2017),arXiv:1704.00448 [hep-th].   
[25] W. van Neerven, Z.Phys. C30, 595 (1986).   
[26] P.Baikov，K. Chetyrkin，A.Smirnov,V.Smirnov, and M. Steinhauser, Phys.Rev.Lett.102, 212002 (2009), arXiv:0902.3519 [hep-ph].   
[27] R. Lee，A. Smirnov, and V. Smirnov, JHEP 1004,020 (2010),arXiv:1001.2887 [hep-ph].   
[28] T.Gehrmann， E．Glover, T.Huber, N.Ikizlerli, andC.Studerus，JHEP 1006,094 (2010), arXiv:1004.3653 [hep-ph].   
[29] T.Gehrmann，E.W.N. Glover，T.Huber，N. Ikizlerli, and C.Studerus，JHEP 11,102 (2010), arXiv:1010.4478 [hep-ph].   
[30] A. vonManteuffel,E.Panzer, and R. M. Schabinger, Phys. Rev. D93,125014 (2016), arXiv:1510.06758 [hep-ph].   
[31] T.Gehrmann,J. M. Henn，and T. Huber, JHEP 1203, 101(2012),arXiv:1112.4524 [hep-th].   
[32]R. H. Boels, B.A. Kniehl, O. V. Tarasov,and G. Yang, JHEP 02,063 (2013),arXiv:1211.7028 [hep-th].   
[33]R. H. Boels, B. A. Kniehl, and G. Yang, Nucl. Phys.B902,387 (2016), arXiv:1508.03717 [hep-th].   
[34] J.M.Henn, A. V.Smirnov, V. A. Smirnov, and M. Steinhauser, JHEP 05,066 (2016), arXiv:1604.03126 [hep-ph].   
[35] J. Henn,A. V.Smirnov, V.A.Smirnov, M. Steinhauser, and R.N. Lee，(2016),10.1007/JHEP03(2017)139, arXiv:1612.04389 [hep-ph].   
[36]A. von Manteuffel and R. M. Schabinger, Phys. Rev. D95,034030 (2017), arXiv:1611.00795 [hep-ph].   
[37] G. Yang, Phys. Rev.Lett.117,271602 (2016), arXiv:1610.02394 [hep-th].   
[38] A. H. Mueller, Phys.Rev.D20, 2037 (1979).   
[39] J. C. Collins, Phys.Rev. D22,1478 (1980).   
[40] A. Sen, Phys.Rev. D24,3281 (1981).   
[41] L. Magnea and G. F. Sterman, Phys.Rev. D42, 4222 (1990).   
[42] J.Blumlein，D.J.Broadhurst, and J.A. M. Vermaseren， Comput. Phys. Commun.181, 582 (2010), arXiv:0907.2557 [math-ph].   
[43] Z.Bern, J.J.M. Carrasco, and H. Johansson, Phys. Rev.D78,085011 (2008), arXiv:0805.3993 [hep-ph].   
[44] Z.Bern，J.J.M. Carrasco, and H. Johansson, Phys.Rev.Lett.105,061602 (2010), arXiv:1004.0476 [hep-th].   
[45]K. Chetyrkin and F. Tkachov, Nucl.Phys.B192, 159 (1981).   
[46] F.Tkachov,Phys.Lett.B100,65 (1981).   
[47] A. von Manteuffel and C. Studerus, (2012), arXiv:1201.4330 [hep-ph].   
[48] R.H. Boels,B.A. Kniehl, and G. Yang, Proceedings, 13th DESY Workshop on Elementary Particle Physics: Loops and Legs in Quantum Field Theory (LL2016): Leipzig，Germany，April 24-29,2016,PoS LL2016,039 (2016),arXiv:1607.00172 [hep-th].   
[49] N.Arkani-Hamed,J.L. Bourjaily，F. Cachazo, andJ. Trnka， Phys.Rev.Lett.113,261603 (2014), arXiv:1410.0354 [hep-th].   
[50] Z.Bern，E.Herrmann, S.Litsey, J. Stankowicz, and J. Trnka, JHEP 06,202 (2015), arXiv:1412.8584 [hep-th].   
[51] J.M.Henn, Phys. Rev. Lett.110, 251601 (2013), arXiv:1304.1806 [hep-th].   
[52] J.M. Henn,A.V.Smirnov, and V. A. Smirnov, JHEP 03, 088 (2014),arXiv:1312.2588 [hep-th].   
[53] R. H. Boels, T. Huber,and G. Yang,To appear (2017).   
[54] V.A. Smirnov, Springer Tracts Mod.Phys. 250,1 (2012).   
[55] T. Binoth and G. Heinrich, Nucl.Phys. B585, 741 (2000), arXiv:hep-ph/0004013 [hep-ph].   
[56] A. Smirnov and M. Tentyukov, Comput.Phys.Commun.180,735 (2009), arXiv:0807.4129 [hep-ph].   
[57] A. Smirnov, V. Smirnov, and M. Tentyukov, Comput.Phys.Commun.182, 790 (2011), arXiv:0912.0158 [hep-ph].   
[58] A.V. Smirnov, Comput.Phys.Commun. 185, 2090 (2014), arXiv:1312.3186_[hep-ph].   
[59] A.V.Smirnov,Comput. Phys. Commun. 204,189 (2016), arXiv:1511.03614 [hep-ph].   
[60] J. Carter and G. Heinrich, Comput.Phys.Commun. 182, 1566 (2011), arXiv:1011.5493 [hep-ph].   
[61] S. Borowka, J. Carter, and G. Heinrich, Comput.Phys.Commun.184, 396 (2013), arXiv:1204.4152 [hep-ph].   
[62] S.Borowka,G.Heinrich,S. Jones,M. Kerner,J.Schlenk, et al.，(2015),arXiv:1502.06595 [hep-ph].   
[63] G. P. Lepage, CLNS-80/447 (1980).   
[64]T. Hahn， Comput.Phys. Commun.168,78 (2005), arXiv:hep-ph/0404043 [hep-ph].   
[65] M.Czakon， Comput.Phys.Commun. 175, 559 (2006), arXiv:hep-ph/0511200_[hep-ph].   
[66] A. V. Smirnov and V. A. Smirnov, Eur.Phys. J. C62,445 (2009), arXiv:0901.0386 [hep-ph].   
[67] J.Gluza, K.Kajda, and T. Riemann, Comput.Phys.Commun. 177, 879 (2007), arXiv:0704.2423 [hep-ph].   
[68] J. Gluza, K. Kajda, T. Riemann, and V. Yundin, Eur.Phys.J. C71, 1516 (2011), arXiv:1010.1667 [hep-ph].   
[69] J.Blmlein，I.Dubovyk, J.Gluza, M. Ochman, C. G. Raab, etal., PoSLL2014, 052 (2014), arXiv:1407.7832 [hep-ph].   
[70] B.Ruijl,T.Ueda，and J.A.M.Vermaseren，(2017), arXiv:1704.06650 [hep-ph].   
[71] A.von Manteuffel,E. Panzer， and R.M. Schabinger, JHEP 02,120 (2015),arXiv:1411.7392 [hep-ph].