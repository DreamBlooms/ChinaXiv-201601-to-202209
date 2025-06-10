# Cumulants in the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models

Xue Pan,1 Lizhu Chen,1 X.S. Chen,² and Yuanfang Wu1   
$^ { 1 }$ Key Laboratory of Quark and Lepton Physics (MOE) and Institute of Particle Physics, Central China Normal University，Wuhan 430o79，China   
$^ { \mathcal { Z } }$ Institute of Theoretical Physics， Chinese Academy of Sciences， Beijing 100190, China

Based on the universal properties of a critical point in diffrent systems and that the QCD phase transitions fall into the same universality classes as the 3-dimensional Ising, $O ( 2 )$ or $O ( 4 )$ spin models,the critical behavior of cumulants and higher cumulant ratios of the order parameter from the three kinds of spin models is studied.We found that all higher cumulant ratios change dramatically the sign near the critical temperature.The qualitative critical behavior of the same order cumulant ratio is consistent in these three models.

PACS numbers: 25.75.Gz,25.75.Nq

# I.INTRODUCTION

One goal of current relativistic heavy ion collision experiments is to locate the QCD critical point.In the idealized thermodynamic limit, the correlation length $\xi$ would diverge at the critical point [1].But the system size，especially the evolution time of the formed system are finite in relativistic heavy-ion collisions [1,2]. $\xi$ may not be fully developed. It's estimated to be at most the value of 2-3 fm [2]. It's close to its "natural" value of1fm.So it's essential to find observable that is sensitive to the critical point.

Recently, it has proposed that the higher cumulants will be more sensitive to the critical point [3]. On one hand, they are more sensitive to the correlation length. For example, the third cumulant and fourth cumulant of net-proton in heavy-ion collisions individually diverge with $\xi ^ { 4 . 5 }$ and $\xi ^ { 7 }$ , which is much faster than the quadratic cumulant. On the other hand,the higher cumulant can reflect the fine-detail information of the net-proton distribution. The sign changes of various cumulants are noted in related papers. For example, the sign of the third order cumulant is discussed in Ref. [4], the negative fourth order cumulant is discussed in Ref.[5,6],and the sign change of sixth and eighth order cumulants is shown in Ref. [7]. In order to compare the results of theory with experiments, the ratios of higher cumulants to the second order one is usually used.

As we know，different systems have universal behavior in the vicinity of a critical point. The systems falling to the same universality class have the same value for the critical exponent. So the results of relatively simple systems, such as spin models with an $O ( N )$ -symmetry， play an important role in the analysis of phase transitions in much more complicated systems.

The critical point terminating the first order phase transition line in the QCD phase boundary belongs to the same universality class of the 3-dimensional Ising model [8-11]. In the chiral limit，if $U _ { A } ( 1 )$ symmetry is broken，the chiral phase transition of a 2-flavor QCD theory is argued to belong to the same universality class of the 3-dimensional $O ( 4 )$ spin model [8]. The critical behavior of the net-baryon number fluctuations is expected to be controlled by the universal $O ( 4 )$ symmetry group [12]. Because of lattice artifacts in calculations with the staggered fermions,the 2- and (2+1)-flavor chiral phase transitions may belong to the same universality class with the $O ( 2 )$ spin model [13-15]. So the critical behavior of cumulant and higher cumulant ratios in the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models are helpful.

In this paper，we first introduce the cumulants in the $O ( N )$ spin models and the corresponding relations of the 3-dimensional Ising and $O ( 4 )$ spin models to the QCD.Then through the Monte Carlo simulations without external magnetic field，we calculate the cumulants and higher cumulant ratios of the order parameter in the 3-dimensional Ising， $O ( 2 )$ and $O ( 4 )$

spin models. The critical behavior of the order parameter，the susceptibility，the ratios of the third，fourth and sixth to second order cumulant is presented and discussed, respectively. Meanwhile, the behavior of higher cumulant ratios in the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models is compared. Finally， the conclusions are drawn.

# II. FLUCTUATIONSOFORDERPARAMETER IN THE $O ( N )$ SPIN MODELS

The $O ( N )$ -invariant nonlinear $\sigma$ -models( $\mathrm { \nabla } O ( N )$ spin model) are defined as,

$$
\beta \mathcal { H } = - J \sum _ { \langle i , j \rangle } \vec { S } _ { i } \cdot \vec { S } _ { j } - \vec { H } \cdot \sum _ { i } \vec { S } _ { i } .
$$

$\mathcal { H }$ is the Hamiltonian. $J$ and $\vec { H }$ are both reduced quantities which already conclude $\beta = 1 / T$ ： $J$ isan interaction energy between the nearestneighbor spins $\langle i , j \rangle$ .In our simulation,we set $J = \beta$ ： $\vec { H }$ is the external magnetic field. $\vec { S } _ { i }$ is a unit vector of $N$ -components at $i$ th site of a $d$ -dimensional hyper-cubic lattice with a longitudinal (parallel to the magnetic field $\vec { H }$ )and a transverse component

$$
\vec { S } _ { i } = S _ { i } ^ { \parallel } \vec { e } _ { H } + \vec { S } _ { i } ^ { \perp } ,
$$

where

$$
\begin{array} { r } { \vec { e } _ { H } = \vec { H } / H . } \end{array}
$$

$H$ is the magnitude of the external field. The cases $N = 1 , 2 , 4$ and $d = 3$ are the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models, respectively. The energy of a spin configuration is defined as [17]

$$
E = - \sum _ { < i , j > } \vec { S } _ { i } \cdot \vec { S } _ { j } .
$$

The average of the longitudinal spin components is

$$
S ^ { \parallel } = \frac { 1 } { V } \sum _ { i } S _ { i } ^ { \parallel } ,
$$

where $V = L ^ { 3 }$ and $L$ is the number of spins in each direction.

Then the partition function is

$$
Z ( T , H ) = \int \prod _ { i } d ^ { N } S _ { i } \delta ( \vec { S } _ { i } ^ { 2 } - 1 ) \exp ( - \beta E + H V S ^ { \parallel } ) .
$$

The (reduced) free energy per unit volume is

$$
f ( T , H ) = - \frac { 1 } { V } \ln Z .
$$

The derivatives of the free energy density to $H$ are as following,

$$
\chi _ { n } = - \frac { \partial ^ { n } f } { \partial H ^ { n } } \bigg | _ { T } .
$$

They are related with the cumulants of order parameter. For instance,

$$
\begin{array} { r l } & { \chi _ { 1 } = \langle S ^ { \parallel } \rangle , } \\ & { \chi _ { 2 } = V \langle \delta S ^ { \parallel ^ { 2 } } \rangle , } \\ & { \chi _ { 3 } = V ^ { 2 } \langle \delta S ^ { \parallel ^ { 3 } } \rangle , } \\ & { \chi _ { 4 } = V ^ { 3 } \big ( \langle \delta S ^ { \parallel ^ { 4 } } \rangle - 3 \langle \delta S ^ { \parallel ^ { 2 } } \rangle ^ { 2 } \big ) , } \\ & { \chi _ { 6 } = V ^ { 5 } \big ( \langle \delta S ^ { \parallel ^ { 6 } } \rangle - 1 0 \langle \delta S ^ { \parallel ^ { 3 } } \rangle ^ { 2 } + 3 0 \langle \delta S ^ { \parallel ^ { 2 } } \rangle ^ { 3 } - 1 5 \langle \delta S ^ { \parallel ^ { 4 } } \langle \delta S ^ { \parallel ^ { 2 } } \rangle \big ) } \end{array}
$$

Where

$$
\delta S ^ { \parallel } = S ^ { \parallel } - \langle S ^ { \parallel } \rangle ,
$$

（204号 $\chi _ { 1 }$ and $\chi _ { 2 }$ are respectively the magnetization(order parameter) $M$ and longitudinal susceptibility $\chi _ { L }$ .Owing to the spatial rotation symmetry of the $O ( N )$ groups,the mean value of the order parameter is always zero without external magnetic field. In this case, the order parameter definition should be resorted [18], such as

$$
M = \langle | \frac { 1 } { V } \sum _ { i } \vec { S } _ { i } | \rangle .
$$

The scaling form of the critical part of the free energy in the second order phase transition can be write as

$$
f _ { s } ( t , h ) = l ^ { - 3 } f _ { s } ( l ^ { y _ { t } } t , l ^ { y _ { h } } h ) ,
$$

where $t$ is the normalized reduced temperature and $h$ is the normalized reduced magnetic field

$$
t = ( T - T _ { c } ) / T _ { 0 } , h = H / H _ { 0 } .
$$

（204号 $\mathrm { \Delta } T _ { 0 }$ and $H _ { 0 }$ are the normalized parameters. $y _ { t }$ and $y _ { h }$ are the thermal and magnetic exponents, respectively. For purpose of mapping the results of the 3-dimensional Ising model to that of QCD the linear ansatz as following is suggested [19-21]

$$
t = T - T _ { c p } + a ( \mu - \mu _ { c p } ) , ~ h = b ( T - T _ { c p } ) + \mu - \mu _ { c p } .
$$

$\boldsymbol { T } _ { c p } ^ { \prime }$ is the temperature and $\mu _ { c p }$ is the chemical potential at the QCD critical point. $a$ and $b$ have to be determined from QCD. We can get that

$$
\begin{array} { l } { \displaystyle { \partial / \partial \mu = \frac { - b } { 1 - a b } \frac { \partial } { \partial t } + \frac { 1 } { 1 - a b } \frac { \partial } { \partial h } , } } \\ { \displaystyle { \partial / \partial T = \frac { 1 } { 1 - a b } \frac { \partial } { \partial t } - \frac { a } { 1 - a b } \frac { \partial } { \partial h } . } } \end{array}
$$

Through the different orders of derivatives of free energy density to $\mu$ ， we can get the fluctuations of particle number,which can be measured by experiments. The exponent $y _ { h }$ is bigger than $y _ { t }$ in the 3-dimensional Ising model. Their ratio $y _ { h } / y _ { t } = \gamma + \beta = 2 5 / 1 6$ [22]． So $\partial / \partial h$ will be more singular than $\partial / \partial t$ . Although，we don't know the values of $a$ and $b$ ， the particle number fluctuations are dominated by the derivatives of the free energy density to $h$ , that's the order parameter fluctuations in the 3-dimensional Ising model.

The scaling form of the critical part of the free energy density in the chiral phase transition may be

$$
\frac { f _ { s } ( T , \mu _ { q } , h ) } { T ^ { 4 } } = A h ^ { \left( 1 + 1 / \delta \right) } f _ { f } ( z ) , \quad z = t / h ^ { 1 / \beta \delta } ,
$$

where $\beta$ and $\delta$ are critical exponents from the 3- dimensional $O ( 4 )$ spin model, $f _ { f } ( z )$ is the scaling function of the free energy density and

$$
t \equiv \frac { 1 } { t _ { 0 } } ( \frac { T - T _ { c } } { T _ { c } } + \kappa _ { \mu } ( \frac { \mu _ { q } } { T } ) ^ { 2 } ) , \quad h \equiv \frac { 1 } { h _ { 0 } } \frac { m _ { q } } { T _ { c } } .
$$

Here $T _ { c }$ is the chiral phase transition tempera ture. From Eq. (17)，we note that the derivatives of free energy density to $h$ in the $O ( 4 )$ spin model are equal to the derivatives of free energy density to $m _ { q }$ ，which is the fluctuation of order parameter,or the chiral condensate

$$
\langle \bar { \psi } \psi \rangle = - \frac { N _ { F } } { 4 } \frac { \partial f } { \partial m _ { q } } .
$$

So the critical fuctuations of order parameter from the 3-dimensional $O ( 4 )$ spin model can reflect the chiral condensate fluctuations in the QCD chiral phase transition. When it comes to the chiral limit, the quark masses vanish and the chiral symmetry is restored.It corresponds to that the magnetic field in the 3-dimensional $O ( 4 )$ model is zero.

# III. THECRITICALBEHAVIOROFHIGHER CUMULANTRATIOSIN THE 3DISING, $O ( 2 )$ AND $O ( 4 )$ SPIN MODELS

TheMonte Carlosimulations of the 3- dimensional Ising, $O ( 2 )$ ，and $O ( 4 )$ spin models in a finite system are performed by the Wolff algorithm with helical boundary conditions [25]. We choose sufficient big size for each case which can present the qualitative features well,that's $L = 2 4$ for the Ising model and $L = 2 0$ for the $O ( 2 )$ and $O ( 4 )$ spin models.In order to observe andcompare the trendofcumulantsandtheirratios varying with $T / T _ { c }$ in different models,we divide the cumulants or their ratios by their maximum values and rescale the values of $\chi _ { 2 }$ ， $\chi _ { 3 } / \chi _ { 2 }$ $\chi _ { 4 } / \chi _ { 2 }$ ， $\chi _ { 6 } / \chi _ { 2 }$ to plot them.Here $T _ { c }$ is the critical temperature of each model. In our calculation, we use approximate values 4.51 [18],2.202 [26] and 1.068 [26] for $T _ { c }$ in the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models, respectively.

![](images/c72126d32c3660174eec2e6f5b66d872ca4eaacd138c9a0ca21e8fd74eba958d.jpg)  
Fig.1:(Color online） The temperature dependence of the orderparameter ( $M$ ）and susceptibility（ $\chi 2$ ）in the vicinity of critical temperature from the 3-dimensional Ising ( $O ( 1 )$ ) $O ( 2 )$ and $O ( 4 )$ spin models.

The order parameter ( $M$ ）and susceptibility( ）from $\chi _ { 2 }$ the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models is presented in Fig.1. Its behavior in these three spin models is similar. $M$ decreases with the increasing temperature.When the temperature is much lower than $T _ { c }$ the system is ordered,all of the spins align to the same direction,the value of $M$ approaches one. When the temperature is much higher than $T _ { c }$ ,the system is disordered, the spins point to a direction at random, the value of $M$ approaches zero.The qualitative behavior of $\chi _ { 2 }$ in the three models are similar, too.There is a pronounced cusp near $T _ { c }$ .The peak is also observed in the chiral susceptibility in the 2-flavor QCDlattice calculation and the chiral effective model with the Polyakov loop [27, 28].

The ratios of the third $\left( \chi _ { 3 } / \chi _ { 2 } \right)$ and fourth $\left( \chi _ { 4 } / \chi _ { 2 } \right)$ to the second order cumulant in the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models are shown in Fig. 2.

![](images/0adf8304dd7fb6395dd4d00544b95b238fb88119407eb3f2a679f9385dc5da45.jpg)  
Fig.2:(Color online）The temperature dependence of$\chi _ { ^ 3 } / \chi _ { ^ 2 }$ and $\chi _ { 4 } / \chi _ { 2 }$ in the vicinity of critical temperature fromthe 3-dimensional Ising ( $O ( 1 )$ ）， $O ( 2 )$ and $O ( 4 )$ spin models.

![](images/151f0ba57d2b545c4c44d9578dc7d243edf28443dfb0d2183eea6a1e0c1fd083.jpg)  
Fig.3:(Color online)The temperature dependence of $\chi _ { 6 } / \chi _ { 2 }$ in the vicinity of critical temperature from the 3- dimensional Ising ( $O ( 1 )$ ）， $O ( 2 )$ and $O ( 4 )$ spin models.

The qualitative behavior of $\chi _ { 3 } / \chi _ { 2 }$ is the same in the three models.It changes dramatically the sign near $T _ { c }$ .It is negative when $T < T _ { c }$ ,and becomes positive when $T >$ $T _ { c }$ . The behavior of $\chi _ { 3 } / \chi _ { 2 }$ from the 3-dimensional Ising model is consistent with that in Ref. [29]. The third order cumulant reflects the skewness of the distribution.As the Gaussian distribution,it's symmetrical, then its skewness is zero.If the left tail of a distribution is longer than the right one,the third order cumulant will be negative.If theright tail is longer,the third order cumulant will be positive.The qualitative behavior of $\chi _ { 4 } / \chi _ { 2 }$ is the same in the three models. It oscillates greatly with temperature near $T _ { c }$ . They are negative when $T$ approaches $T _ { c }$ from $T > T _ { c }$ side.This is consistent with the prediction in [6], which said the fourth order cumulant will be negative when the system approaches the critical point from the crossover side. The fourth order cumulant reflects the kurtosis of the distribution.Gaussian distribution is also the reference.Its kurtosis is zero.Ifa distribution isless sharp than the Gaussian distribution,its fourth order cumulant will be negative.If it's more sharp,its fourth order cumulant is positive.

The ratios of sixth to second order cumulant from the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models are presented in Fig. 3.

Its generic structure in the three models is similar.It has two positive maximums and a pronounced negative minimum between them close to the transition region. Comparing $\chi _ { 3 } / \chi _ { 2 }$ ， $\chi _ { 4 } / \chi _ { 2 }$ and $\chi _ { 6 } / \chi _ { 2 }$ ，we found that the higher the order of the cumulant, the more complicated of the structure and quicker to get equilibrium after leaving the critical point.

From the simulation results,we already know that the behavior of the same order cumulant or higher order cumulant ratio is similar in the three models.Now let's analyze it briefly from the theory. As the order parameter in the spin models,it will approach one and zero in the ordered and disordered phases,respectively,which leads to the similar behavior of the order parameter.In the thermodynamical limit, the susceptibility diverges as $\chi _ { 2 } \sim | t | ^ { - \gamma }$ in the vicinity of the critical point.The value of $\gamma$ is $1 . 2 5 3 ( 4 )$ [22],1.3192 [23] and 1.4668 [24] for the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models.Their values are positive and close to each other.In a finite system, the divergence will be weakened and become a round peak.That's why the behavior of $\chi _ { 2 }$ is similar. All of the cumulants of the order parameter are derivatives of the free energy density with respect to the external field,the behavior of the first and second order cumulants is similar in these three models,so it's not difficult to understand the similar behavior of the higher order cumulant ratios.

# IV. SUMMARY

In this paper, the critical behavior of the order parameter,susceptibility,ratios of the third,fourth,sixth order cumulant to the second one are calculated from the 3-dimensional Ising, $O ( 2 )$ and $O ( 4 )$ spin models at a given system size without external field.For each order cumulant or higher cumulant ratios,its qualitative critical behavior in these three models is the same. The ratios of the third,fourth,and sixth order cumulant to the second one change dramatically near the critical temperature.They all have sign change.And the higher the order of the cumulant, the more complicated of the structure.From the 3-dimensional Ising model, we know that the sign changes of the cumulant ratios of baryon number fluctuations may predict the critical signals in heavyion collisions.For the 3-dimensional $O ( 2 )$ and $O ( 4 )$ spin models,in order to guide the experiments,the derivatives of free energy density to the temperature in a finite lattice is on going.

This work was supported in part by the National Natural Science Foundation of China under Grant No. 10835005，MOE of China under Grant No. IRT0624, B08033 and Laboratory of Quark and Lepton Physics (MOE) and Institute of Particle Physics,Central China Normal University,Wuhan 43o079,China under Grant No.QLPL201303.

[1] Stephanov M A,Rajagopal K,and Shuryak E V.Phys. Rev.D,1999,60:114028   
[2] Berdnikov B and Rajagopal K. Phys.Rev.D,2000,6: 105017   
[3]Stephanov M A.Phys.Rev.Lett,2009,102:032301   
[4] Asakawa M, Ejiri S,and Kitazawa M. Phys.Rev.Lett., 2009，103:262301   
[5]GavaiRV,Gupta S.Phys.Lett.B,2011,696:459   
6] Stephanov M A.Phys.Rev.Lett.,2011,107:052301   
[7]FrimanB,KarschF,RedlichK and SkokovV.Eur.Phys. J.C,2011, 71:1694   
[8]PisarskiRDand WilczekF.Phys.Rev.D,1984,29:338   
[9] P.de Forcrand and Philipsen O.Phys.Rev.Lett.,2010, 105:152001   
10] Stephanov M, Rajagopal K,and Shuryak E.Phys.Rev. Lett.,1998,81:4816   
11] Asakawa M.J.Phys.G:Nucl.Part.Phys.2009，36: 064042   
12]Hatta Y and Ikeda T.Phys.Rev.D,2003,67:014028   
13] Bernard C B et al.Phys.Rev.D,2000,61:054503   
14] Ejiri S et al. Phys.Rev.D,2009,80:094505   
[15] Kaczmarek O et al. Phys.Rev.D,2011, 83:014504   
[16] Rajagopal K and Wilczek F.Nucl. Phys.B,1993,399: 395   
[17] Engels J and Karsch F.arXiv:1105.0584   
[18] Talapov AL,Blote HW.J.Phys.A,1996,29:5727   
[19]Rchr JJand Mcrmin ND.Phys.Rev.A,1973,8:472   
[20] Wilding N B.J. Phys.: Condens. Matter, 1997,9: 585   
[21] Nonaka C and Asakawa M. Phys. Rev.C，2005,71: 044904   
[22] Garcia J,Gonzalo J A, Phys.A, 2003,326,464   
[23]EngelsJ,Holtmann S,Mendes T,Schulze T,Phys.Lett. B,2000,492,219   
[24]Engels J,Mendes T,Nucl.Phys.B 2000,572,289   
[25] Wolff U.Phys.Rev. Lett., 1989,62:361   
[26]Ballesteros HG,Fernández L A,Marin-Mayor V,Munoz Sudupe A,Phys.Lett.B,1996,387,125   
[27] Karsch F and Laermann E.Phys.Rev.D,1994, 50:6954   
[28]Fukushima K.Phys.Lett.B,2004,591:277   
[29]CHENLi-Zhu,PAN Xue,CHEN Xiao-Song,WU YuanFang.Chi Phys C,2012,36:1