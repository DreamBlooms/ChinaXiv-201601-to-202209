# Fast adaptive flat-histogram ensemble to enhance the sampling in large systems

XU Shun1, ZHOU Xin1\*, JIANG Yi² & WANG YanTing $^ { 1 }$ School ofPhysical Sciences, University of Chinese Academy of Sciences,Beijing 10o049,China, 2 Department of Mathematics and Statistics,Georgia State University,Atlanta 30303, USA; 3 State Key Laboratoryof Theoretical Physics,Instituteof Theoretical Physics, ChineseAcademy ofSciences,Beijingl0oi90,China

ReceivedFebruary 27,2015;acceptedApril 29,2015

An ffcient novel algorithm was developed to estimate the Densityof States (DOS)forlargesystems bycalculating the ensemble means of an extensive physical variable,such as the potential energy, $U$ ,in generalized canonical ensembles to interolte $\beta _ { s } ( U ) \equiv { \frac { { \widehat { \partial } } S ( U ) } { { \widehat { \partial } } U } }$ ， where $S ( U )$ is with different accuracies in diferent energy regions to capture the dependence of the reverse temperature on $U$ without seting prior grid in the $U$ space. By combining with a $U$ -compression transformation, we decrease the computational complexity from （204号 $\bar { O } ( N ^ { 3 / 2 } )$ in the normal Wang Landau type method to $\bar { O } ( N ^ { 1 / 2 } )$ in the current algorithm, as the degrees of freedom of system $N$ The efficiency of the algorithm is demonstrated by applying to Lennard Jones fluids with various $N$ ,along with its ability to find different macroscopic states,including metastable states.

# moleculardynamicssimulations,enhanced sampling,densityofstates,generalized canonical ensemble,flat-histogram ensemble

PACS number(s): 05.10.-a, 02.70.Ns, 64.70.D

Citation: XuS,ZhouXsiattoebeelic 58:590501,doi:10.1007/s11433-015-5690-7

# 1Introduction

An essential problem for molecular simulations in complex systems with a rugged potential energy surface,such as proteins [1,2] and glasses [3] or first-order phase-coexistence systems,is how to adequately sample the conformational space,since the existing high free-energy barriers prevent the regular Monte Carlo (MC) and Molecular Dynamics (MD） simulations to visit all the important regions sufficiently.In attempting to overcome this difficulty, many enhanced sampling methods [4-18] have been developed;

most of them tried to modify the potential energy surface to make the distribution function in a preselected collective variable space be almost flat.Although these methods have achieved great accomplishments,more attempts are still needed to further improve the sampling efficiency,especially in larger systems.

TheDensity of States(DOS)of a system isdefined as $\Omega ( U ) \equiv \int \mathrm { d } \boldsymbol { r } \delta ( U - U ( \boldsymbol { r } ) )$ ，where $U ( r )$ is the potential energy of the system (or more generally,any conformational function). Here, $r$ isa simple denotation of high-dimensional conformations,such as all-atomic position vectors,and the integral about $r$ is over the whole conformational space. Usually，we define the microcanonical entropy $S ( U ) { \equiv } 1 { \mathfrak { n } }$ $\Omega ( U )$ and the interior reverse temperature $\beta _ { s } ( U ) \equiv { \frac { { \widehat { \partial } } S ( U ) } { { \widehat { \partial } } U } }$ to describe the inner property of the system. Then,we have the flat-histogram ensemble,where the conformational distribution $P _ { f h } ( r ) \propto \mathsf { e } ^ { - S ( U ( r ) ) }$ .The standard simulation techniques, such as MC or MD simulations,can generate the desired distribution if a new potential $V _ { \mathrm { n e w } } ( r ) { = } T _ { 0 } \ S ( U )$ is applied, where $T _ { 0 }$ is the temperature of thermostat,which could be any value. Thus the histogram in the U space P(U)ce-s(U) $\int \mathrm { d } \boldsymbol { r } P ( \boldsymbol { r } ) \delta ( U - U ( \boldsymbol { r } ) )$ is flat. Since the flat-histogram ensemble can visit a much wider energy range than the usual Canonical Ensemble(CE)where the conformational distribution $P _ { \mathrm { c e } } ( r ) \propto \mathrm { e } ^ { - \beta U ( r ) }$ , it has been widely used to overcome free-energy barriers and thus enhances the sampling for complex systems [4-6,9,10,13]. Here, $\beta = 1 / k _ { \mathrm { { B } } } T ,$ with $k _ { \mathrm { B } }$ Boltzmann constant and $T$ the temperature.In the flathistogram ensemble, $S ( U )$ is an input quantity and the target of simulations at the same time,so $S ( U )$ should be solved iteratively. The convergence efficiency and the accuracy of the iteration are essential for different flat-histogram methods.

Among them, the Wang Laudau (WL) algorithm [5] lifts the value of $S$ in the current-visited $U$ range at each simulation step until the visiting histogram in $U$ space is almost flat. The WL algorithm is easy to implement and has been widely applied to various kinds of systems.However,the number of required simulation steps is at least in the order of $O ( N ^ { 2 } )$ [8] with the system size $N$ .The recently developed Statistical-TemperatureMolecularDynamics(STMD) method [1O] updates the intensive variable $T _ { s } ( U ) \equiv \beta _ { s } ^ { - 1 } ( U )$ instead of the extensive variable $S ( U )$ in the original WL, thus improving the efficiency of convergence to the order of $O ( N ^ { 3 / 2 } )$ . A short point of these WL-like methods is that they do not satisfy the detailed balance condition thus with less numerical stability in applications.Alternatively,the multimicro canonical method (MMCM) [7] calculates the microcanonical temperature $T _ { m } ( E )$ and relates the $T _ { m } ( E )$ to the interior reverse temperature $\beta _ { s } ( E )$ based on the thermodynamic equivalence of differently defined temperatures and can converge within $O ( N ^ { 3 / 2 } )$ simulation steps.Different from the original WL algorithm and the STMD, the MMCM satisfies the detailed balance condition, then has some benefits in numerical stability.In the WL-like algorithms and the MMCM, it is necessary to cut the extensive variable $U$ into homogeneous bins with a presumed bin size.We collect sufficient simulation data in each bin of $U$ to estimate the value of $\beta _ { s } ( U )$ at the centers of each $U$ bin, that is,preset a uniform grid $\{ U _ { i } \} , i { = } 1 , . . . , M$ and calculate $\beta _ { s } ( U )$ on the grid, then interpolate the whole curve $\beta _ { s } ( U )$ (or $T _ { s } ( U ) )$ . Since the varying rates of $\beta _ { s } ( U )$ at different $U$ regions may be very different, the presetting of a suitable $U$ grid for achieving both the accuracy and the efficiency is not trivial. We should use a sparse $\{ U _ { i } \}$ grid in the slow-varied regions of $\beta _ { s } ( U )$ ,but a more dense grid in the fast-varied regions of $\beta _ { s } ( U )$

In this paper,we present the Fast Adaptive Flat-histogram Ensemble (FAFE） method to efficiently estimate $\beta _ { s } ( U )$ . The FAFE calculates the ensemble means and fluctuations of $U$ in a series of generalized ensembles to adap tively form a $U$ grid and to get the values of $\beta _ { s } ( U )$ on the grid, $\{ ( \beta _ { i } , U _ { i } ) \}$ . The $\{ U _ { i } \}$ grid is non-uniform and the grid bin widths depend on both $U$ and $N$ automatically:dense $\{ U _ { i } \}$ points are applied in the $\beta _ { s } ( U )$ fast-changed regions but sparse $\{ U _ { i } \}$ in the $U$ regions where $\beta _ { s }$ varies slowly as $U$ In the $U$ regions where $\beta _ { s } ( U )$ was already well estimated, we apply a compression transformation to further depress the visit time in that regions so that more simulation costs are focus on the others.By doing so,in the FAFE,the estimate of $\beta _ { s } ( U )$ can be converged within the order of $N ^ { 1 / 2 }$ simulation steps.Also, the FAFE satisfies the detailed balance condition，and it can visit and identify coexistent phases,including metastable phases of systems.

# 2Theory and method

When an estimate of the entropy $\tilde { S } ( U )$ is obtained, the CE means of any conformational function $Q ( r )$ can be easily calculated by

$$
\left. Q \right. _ { T } = \frac { \sum _ { k } Q _ { k } w _ { k } } { \sum _ { k } w _ { k } } ,
$$

where $Q _ { k } { = } Q ( r _ { k } )$ is the value of the $Q ( r )$ at the sampled conformation $r _ { k }$ under the flat-histogram simulation,and the weight factor is $w _ { k } = \mathsf { e } ^ { \tilde { S } ( U ( r _ { k } ) ) - U ( r _ { k } ) / k _ { \mathrm { B } } T }$ . It is worth mentioning that the weighted average is efficient only while the effective size of the weighted sample is large enough,which usually requires the generated sample to cover the target sample,that is,the visited $U$ range of the flat-histogram ensemble sample covers that of the CE. We can approximately estimate the statistical error of the weighted average by the effective size of the weighted sample:

$$
B = \frac { \left( \sum w _ { k } \right) ^ { 2 } } { \sum w _ { k } ^ { 2 } } ,
$$

which decreases with increasing fluctuation of normalized weights.While the weights are constant, the effective size of the sample, $B$ ,is the realistic size of the sample,as per our expectation. Only while all significant regions of the target distribution are adequately sampled, the generated sample can be weighted efficiently to reproduce the target one,that is,the effective size $B$ of the weighted sample is much larger than unity.

For any $f ( U )$ ensemble, that is, $P _ { f } ( r ) \propto \mathsf { e } ^ { - f ( U ( r ) ) }$ ，the histogram $H _ { f } ( U ) \propto \mathbf { e } ^ { S ( U ) - f ( U ) }$ could be approximately writtn as:

$$
H _ { _ { f } } ( U ) \propto \exp \Biggl [ - \frac { 1 } { 2 \sigma _ { _ f } ^ { 2 } } ( U - E _ { _ f } ) ^ { 2 } \Biggr ] ,
$$

by Taylor expansion,if $N$ is very large,and $U { \propto } N$ is an extensive variable. The maximal point of $H _ { f } ( U )$ is approximately equal to the ensemble average of $U$ under the $f ( U )$ ensemble, $E _ { f } \approx \langle U \rangle _ { f } .$ Thus,we have

$$
\begin{array} { r l } & { \beta _ { s } ( E _ { f } ) = f ^ { \prime } ( E _ { f } ) , } \\ & { \beta _ { s } ^ { \prime } ( E _ { f } ) = - \sigma _ { f } ^ { - 2 } + f ^ { \prime \prime } ( E _ { f } ) , } \end{array}
$$

where the single prime and double prime mean the first derivative and the second derivative,respectively. $\sigma _ { f }$ is the fluctuation of $U$ in the $f ( U )$ ensemble. We calculate $E _ { f } =$ $\langle U \rangle _ { f }$ and $\sigma _ { f } ^ { 2 } = \left. \left( U - E _ { f } \right) ^ { 2 } \right. _ { f }$ in a series of different $f ( U )$ ensembles to generate points on the curve $\beta _ { s } ( U )$ . The whole curve $\beta _ { s } ( U )$ can be interpolated from these points，and $\tilde { S } ( U )$ can be estimated by integrating $\beta _ { s } ( U )$

Different $f ( U )$ ensembles,such as the CE $f ( U ) = \beta U$ and the microcanonical ensemble

$$
f _ { m c e } ( U ) = - \frac { l - 2 } { 2 } \mathrm { l n } [ ( E - U ) \Theta ( E - U ) ]
$$

can be used to construct $\beta _ { s } ( U )$ .Here, $l$ is number of degrees of freedom, the Heaviside step function $\Theta ( x ) = 1$ while $x { \geqslant } 0$ and zero otherwise.In this paper,we use the Generalized Canonical Ensemble (GCE) [17]:

$$
f ( U ) = \beta _ { 0 } U + \frac { 1 } { 2 } \alpha ( U - U _ { 0 } ) ^ { 2 }
$$

to generate points on $\beta _ { s } ( U )$ . In thermodynamic stable regions, $\beta _ { s } ^ { \prime } { < } 0$ .Thus,the distributions in the CE( $\scriptstyle ( x = 0 )$ are Gaussian-like functions around $E _ { f }$ However,in thermodynamic unstable regions such as two phase-coexistence regions,which cannot be sufficiently visited in the CE,we can use the GCE with $\alpha > \beta _ { s } ^ { \prime } \left( E \right)$ to stabilize the phasecoexistence regions, then reconstruct the data points of $\beta _ { s } ( U )$ in the regions.

The implementation of our algorithm is straightforward. Without losing generality, we choose $U$ as the total potential energy of a physical system and define ${ \cal T } _ { s } ( U ) { = } { \beta } _ { s } ^ { - 1 } ( U )$ . The steps of our algorithm are as follows:

(1）choose an initial $T _ { 0 }$ (usually the highest temperature we desired),and then set $T _ { s } ( U ) \equiv T _ { 0 }$ and estimate $S ( U ) =$ $U / T _ { 0 }$ ： (2） simulate a segment of trajectory in the current $S ( U )$ ensemble and generate an equilibrium sample; (3)choose a few $f _ { i } ( U )$ functions and calculate ${ \overline { { U } } } _ { i }$ and fluctuations $\sigma _ { i }$ from the generated sample in the step 2

based on eq. (1).

(4)Interpolate $T _ { s } ( U )$ and linearly extrapolate it out of the current visited regions from the ending $U _ { i }$ from the obtained points $\{ ( \overline { { U } } _ { i } , T _ { i } ) \}$ (and the derivative of $T _ { s } ( U )$ ， $\{ T _ { i } ^ { \prime } = T _ { i } ^ { 2 } \ /$ $\sigma _ { i } ^ { 2 } \}$ ), then integrate $S ( U )$ from the $T _ { s } ( U )$

(5) Repeat the steps 2,3,and 4 until the whole $T _ { s } ( U )$ and $S ( U )$ are generated.

At the step 3,we may use CEs,for example, $f ( U ) = U / T _ { i }$ with a series of $\{ T _ { i } \}$ . Here, $T _ { i }$ is chosen from the current $T _ { s } ( U )$ function: the corresponding $\tilde { U } _ { i }$ ，which satisfies the equation $T _ { i } { = } T _ { s } ( \tilde { U } _ { i } )$ ，must locate in the current visited regions and $| U _ { i } - U _ { i - 1 } | { \sim } \sigma _ { i - 1 }$ ,where $\sigma _ { i - 1 }$ is the fluctuation of $U$ at the temperature $T _ { i - 1 }$ .Also,we apply the mean and fluctuation at $T _ { i }$ when and only when the effective size of the weighted sample, $B$ ,is sufficiently large.Note that we can calculate the means and fluctuations at many $T _ { i }$ from the same sample without new simulations.The computational cost for the weighted mean is almost negligible compared with the generation of samples.In this step,we can check on whether larger $\alpha$ should be applied in applying the GCE to estimate $\tilde { U } _ { f }$ .For example,we first choose $\scriptstyle { \alpha = 0 }$ to calculate $( T _ { i } , \ { \tilde { U } } _ { i } )$ ,then set $\beta _ { 0 } = T _ { i } ^ { - 1 }$ ， $U _ { 0 } { = } \tilde { U } _ { i }$ , and use a positive $\alpha$ to calculate the means in the GCE ensemble,and finally compare the results to determine whether a larger $\alpha$ should be used to depress the possible deviation between the extreme point and the average $U$ . The points $( \beta _ { i } , U _ { i } )$ can be calculated using many samples generated in different segments of simulations in the step 3:

$$
\bar { U }  \frac { \sum \bar { U } ^ { j } B ^ { j } } { \sum B ^ { j } } ,
$$

where $\hat { U } ^ { j }$ and $B ^ { j }$ are the weighted mean of $U$ and the corresponding $B$ factor from the jth sample,respectively.The statistical error of $\bar { U }$ ，which is measured by the total $B =$ $\sum B ^ { j }$ factor, can be suppressed by this way.

Before all regions are sufficiently visited, $T _ { s } ( U )$ in some regionsmayalreadyconvergeifthe $B$ factor of the corresponding $\boldsymbol { \bar { U } }$ is large enough.For example,in normal physical systems, $T _ { s } ( U )$ at high temperatures can be obtained before the low-temperature regions are sufficient visited.

The necessary visiting time in the high- $U$ regions,which is proportional to $N$ even in the flat-histogram ensemble, can be further suppressed,so the simulation can focus its sampling more in the low- $U$ region.We transform $U$ to a new variable $Y$ by $\frac { \mathrm { d } Y } { \mathrm { d } U } = g _ { c } \left( \frac { U - U _ { c } } { b } \right) .$ where the compressed function $g _ { c } ( z )$ slowly approaches zero when $z { \longrightarrow } \infty$ and is almost unity when $z { \leqslant } 0$ Here, $U _ { c }$ and $b$ are parameters to be determined. One possible selectionis

$$
g _ { c } ( z ) = { \frac { \mathrm { e } ^ { - z } + 1 } { \mathrm { e } ^ { - z } + z + c } } ,
$$

with the parameter $c { \sim } 2$ or 3.The $U$ distribution of $Y$ -flat samplesis $P ( U ) { \sim } 1 / ( U { - } U _ { c } )$ when $U { > } U _ { c }$ .Attheend of each segment of simulations,we reset $U _ { c }$ to be the lower boundary of the clear region and choose $b$ in such a way that the expected visiting probability above $U _ { c }$ is comparable with that below $U _ { c } ,$ and then use $\tilde { S } ( Y )$ to generate the $Y .$ -flat sample. Here, $\widetilde { S } ( Y ) = S ( U ) - \ln g _ { c } \left( \frac { U - U _ { c } } { b } \right) ,$ Although the Y-flat simulations can still visit the high- $U$ region ergodically，the majority of the simulation time is spent in the low- $U$ region to refine $T _ { s } ( U )$ . The compression transformation significantly decreases the required computational cost of our algorithm in very large systems.

# 3 Results

Toverifythe applicability of our algorithm,we applied it to a truncated-and-shifted Lennard Jones(LJ) fluid $( r _ { c } = 2 . 5 \$ $\sigma _ { l j } )$ with the reduced density $\rho = 0 . 8$ ： $U$ was selected as the total potential energy,and the DOS were calculated in the range between $T _ { l } { = } 0 . 5$ and ${ \cal T } _ { h } { = } 1 0 0$ ，corresponding to a very large range of $U$ inlarge systems.The ensemble mean of $U$ is regarded as exact if the error of $\boldsymbol { \bar { U } }$ is smaller than $5 \%$ of the fluctuation of $U$ (i.e., $B > 4 0 0 \$ ).TheLangevinthermostat was adopted to keep the system temperature constant and conformations were sampled every $1 0 \mathrm { { M D } }$ steps. $T _ { s } ( U )$ was calculated and updated every ${ { 1 0 } ^ { 5 } }$ steps along with the parameters for the compressive transformation.In our simulations,the distance between neighboring $U _ { i }$ is much larger than in the WL-like methods [1O] in high- $T$ regions and large- $. N$ systems but automatically decreases in low- ${ \bf \nabla } \cdot { \cal T } $ regions and small $N$ systems.The results are shown in Figure 1. The $T _ { s } ( U / N ) , ~ c _ { \nu } \equiv \left( \frac { \mathrm { d } T _ { s } } { \mathrm { d } u } \right) ^ { - 1 }$ ，and $s ( u ) = S ( u ) / N$ quickly converged in the large $U$ regions,so the scaling relations were easily found.Here $\scriptstyle u = U / N$ 、Figure 2 shows the efficiency of our approaches by the number of required MD steps $t \propto N ^ { \gamma }$ with $\gamma { \approx } 0 . 5$ .Here,all ensemble means are required to reach the condition $B > 4 0 0$ so that their relative errors are smaller than 0.05.

As shown in Figure 3,at the lower temperature region, the obtained $T _ { s } ( U )$ is found to have multiple branches corresponding to the DOS of some separated parts in the conformational space.For a segment of simulated trajectory, we may know the branch of $T _ { s } ( U )$ the trajectory belongs to by calculating the corresponding $( T , \langle U \rangle _ { T } )$ points.In our simulations,the trajectories generated in the right branch of $T _ { s } ( U )$ (liquid phase) have the expected flat histograms in the region $U { > } U _ { 1 }$ ,but quickly transit into the low- $U$ region (solid phase).Similarly,simulations in the left branch of $T _ { s } ( U )$ (solid phase）homogeneously visit the $U { < } U _ { 2 }$ region and transit into the liquid phase.The two branches have an overlap region,indicating that the potential energy of the liquid phase can be lower than that of the solid phase,and $U$ definitely cannot serve as the order parameter for the liquid/solid phase transition.It is very hard to visit (and more difficult to identify） the low-energy liquid and high-energy solid conformations with the simulation techniques other than ours.Therefore,our approach,which is able to visit more parts of the configurational space and to identify them by forming their own DOS without a priorly defined order parameter,provides a new approach for better understanding phase transition processes.

![](images/25cd268801d7a61c415e5de803ce99b492566072374960689f9ce063d2dc14f7.jpg)  
Figure1(Color online) The obtained $T _ { s } ,$ （20 $\left( \frac { \mathrm { d } T _ { s } } { \mathrm { d } u } \right) ^ { - 1 }$ and $S$ are shown as functions of $U$ in the LJ systems with different size $N$ 、The number of requiring points $\{ ( U _ { i } , \beta _ { i } ) \}$ increases as $N$ increases.

![](images/8a4fd157bb31553aac592682c855e28cd718d553c3b5ef63280b0d3aef6cc935.jpg)  
Figure 2(Color online） The required MD steps for getting the same accuracy of $\beta _ { s } ( U )$ with the size of system $N$ .Theaccuracy ismeasured by the $B$ factors in estimating ensemble averages of $U$ (see the text). The red dash line is from $t _ { \mathrm { M D } } { \propto } N ^ { 1 / 2 }$ ：

![](images/45356fedc98d31beba96b6aa8d8ed6c98a8d4288824f3fdfc1f07ab61c08dbdd.jpg)  
Figure3(Color online) $T _ { s } ( U )$ in the supersaturated liquid and the solid phases,respectively,of the LJ system with $N { = } 1 0 8$ ，The transition can easily happen when $U { < } U _ { 1 }$ (from liquid to solid) and $U { > } U _ { 2 }$ (from solid to liquid).

![](images/8a851c2f8bea8ddf55d322a788050a8a0f84ea198e29646273df7c268339973e.jpg)  
Figure 4(Color online) The $T _ { s } ( U )$ function in a LJ system with $N { = } 1 0 8$ and $\scriptstyle \rho = 0 . 8$ at the low-temperature region.Each branch of the function corresponds to a particular macroscopic phase.The blue-filled squares cover the unstable liquid/solid coexistence region where $c _ { \nu } \equiv \left( \frac { \mathrm { d } T _ { s } } { \mathrm { d } u } \right) ^ { - 1 }$ which can be thought as the heat capacity in the iso $U$ ensemble,are negative,as shown in the bottom panel. The green down-triangles correspond to the complete FCC solid,which is a metastable state in the current system. Some phase transitions from metastable solids to the stable solid (the black circles） can be found at lower temperatures.When $T _ { s } {  } 0$ ，more complex phase behaviors are expected.

# 4Discussion

It is possible to calculate the total $S ( U )$ and $T _ { s } ( U )$ from the obtained $T _ { s } ( U )$ branches, $S ( U ) = \ln \sum _ { i } \exp [ S ^ { i } ( U ) ]$ ，the

corresponding $T _ { s } ^ { - 1 } ( U ) = \sum _ { i } \omega _ { i } ( U ) [ T _ { s } ^ { i } ( U ) ] ^ { - 1 }$ ，where

$$
S ^ { i } ( U ) = S _ { 0 } ^ { i } + \int _ { U _ { i 0 } } ^ { U } T _ { s } ^ { i } ( E ) \mathrm { d } E
$$

and $T _ { s } ^ { i } ( U )$ are the ith branch of the entropy and temperature, respectively. Here $\omega _ { i } ( U ) = \exp [ S ^ { i } ( U ) ] / \sum _ { i } \exp [ S ^ { i } ( U ) ]$ In the calculation, the integration constants $\{ \boldsymbol { S } _ { \mathrm { ~ 0 ~ } } ^ { i } \}$ must be determined from another simulation technique.However，it should be noted that even in the exact $S ( U )$ ensemble, free transition between states still cannot be guaranteed,because the application of $S ( U )$ does not change $P ( r )$ inside each iso- $U$ subspace.This is a general limitation in all lowdimension flat-histogram ensemble methods. The algorithms with good stabilities (e.g.， satisfying the detailed balance ina long time）are helpful foranalyzing and overcoming the limitation. For example,our approach generates $T _ { s } ( U )$ and $S ( U )$ (with an arbitrary constant） in each visited subspace instead of the expected total $T _ { s } ( U )$ and $S ( U )$ for the whole conformational space.Therefore,although the equilibrium among subspaces is difficult to reach,it still provides many useful results and might construct the total $S ( U )$ by determining the relative constants of $S ( U )$ for each subspace.Also,we may use the generalized ensembles described by eq.(6) to find more metastable states.For example,besides the stable liquid and solid phases in theLJ system,we detected some metastable solid states with different crystalline structures as well as the unstable multiphase coexistence,which are shown in Figure 4.These complex solid phases appear because the system is fixed at the density $\scriptstyle \rho = 0 . 8$ ，so the interparticle distance in the Face-CenterCubic (FCC) structure does not match the equilibrium distance of the LJ potential, $r _ { 0 } { = } 2 ^ { 1 / 6 }$ ：

The flat-histogram ensembles based on multiple collective variables are expected to better enhance the sampling than the ensembles based on a single variable [11,19].The computation complexity of our algorithm is $O ( N ^ { \gamma d } )$ ，where $d$ is the number of the collective variables and $\gamma = 1 / 2$ ，which is much faster than the WL-like with $\scriptstyle \gamma = 1 . 5$ to 3.Recently, Vogel et al. [2O] combined the original WL algorithm with the Replica Exchange Method (REM) to form a parallel WL sampling method,which makes application of the WL algorithm in large systems much efficient.It is also possible to combine the FAFE algorithm with the REM to further improve the efficiency of sampling.We may apply replicas in different $U$ ranges [2O],or in different branches of $T _ { s } ( U )$ then exchange conformations among these replicas.It might provide a possibility to overcome the main limitation in the application of REM,which requires $O ( N ^ { 1 / 2 } )$ replicas to achieve sufficient exchange acceptance ratio [21].

KeyLaboratory ofTheoreticalPhysics.Zhou Xthanksthefinancial supportof theHundredofTalentsPrograminChineseAcademyofSciences.

1 Fang Y.A Gibbs free energy formula for protein folding derived from quantum statistics.Sci China-Phys Mech Astron,2O14,57: 1547-1551   
2 Luo L F.Quantum theory on protein folding. Sci China-Phys Mech Astron,2014,57:458-468   
3 GongP,Wang X,Shao Y,etal.Ti-Zr-Be-Fe quaternary bulk metallic glasses designed by Fe alloying.2013,56: 2090-2097   
4 BergB,Neuhaus T.Multicanonical-algorithms for first orderphase transitions.Phys LettB,1991,267:249253   
5 WangF,LandauD.Efficient,multiple-range randomwalkalgorithm to calculate the density of states.Phys Rev Lett,2001,86:2050-2053   
6 Laio A,Parrinello M.Escaping free-energy minima.Proc Natl Acad SciUSA,2002,99:12562-12566   
7 Yan Q,de Pablo J.Fast calculation of the density of states of a fluid byMonte Carlo simulations.PhysRevLett,20O3,90:O35701   
8 Zhou C,Bhatt RN.Understanding and improving the Wang-Landau algorithm.PhysRevE,2005,72:025701   
9 Zhou X,Jiang Y,Kremer K,et al.Hyperdynamics for entropic systems: Time-space compression and pair correlation function approximation.PhysRevE,2006,74: 035701   
.0 KimJ,StraubJE,Keyes T.Statistical-temperature Monte Carlo and molecular dynamics algorithms.Phys Rev Lett, 2OO6,97: O50601   
.1 Zhou C,Schulthess TC,Torbriigge S,etal.Wang-landau algorithm for continuous models and joint density of states.Phys Rev Lett, 2006,96:120201   
12 Jezewski W. Stationary and nonstationary properties of evolving networks with preferential linkage.PhysRevE,2OO2,66:067102   
13 Gao Y Q.An integrate-over-temperature approach for enhanced sampling.JChemPhys,2008,128:064105   
14 Zhang C,Ma J.Enhanced sampling in generalized ensemble with large gap of sampling parameter:Case study in temperature space random walk.JChemPhys,2009,130:194112   
15 Gong L,Zhou X.Structuring and sampling complex conformation space:Weighted ensemble dynamics simulations.Phys Rev E,2009, 80: 026707   
16 Gong L,Zhou X.Kinetic transition network based on trajectory mapping.JPhys Chem B,2010,114:10266-10276   
17 Xu S,Zhou X,OuYang Z C.Parallel tempering simulation on generalized canonical ensemble.Commun Comput Phys,2012,12:1293- 1306   
18 Junghans C,PerezD,Vogel T.Moleculardynamics in the multicanonical ensemble:Equivalence of Wang-Landau sampling,statistical temperature molecular dynamics,and metadynamics.J Chem Theory Comput, 2014,10:1843-1847   
19 Mastny EA,de Pablo JJ.Direct calculation of solid-liquid equilibria from density-of-states Monte Carlo simulations.J Chem Phys,2005, 122:124109   
20 VogelT,LiYW,WiistT,etal.Generic,hierarchical frameworkfor massively parallel Wang-Landau sampling.Phys Rev Lett,2O13,110: 210603   
21 EarlDJ,Deem MW.Parallel tempering:Theory,applications,and new perspectives.Phys Chem ChemPhys,2005,7:3910-3916