# Critical behaviors and universality classes of percolation phase transitions on two-dimensional square lattice

Yong Zhu, $^ 1$ Ziqing Yang,1 Xin Zhang,1 and Xiaosong Chen1 $^ { 1 }$ State Key Laboratory of Theoretical Physics， Institute of Theoretical Physics, Chinese Academy of Sciences，P.O.Box 2735，Beijing 100190,China (Dated:April 30,2015)

We have investigated both site and bond percolation on two dimensional lattice under the random rule and the product rule respectively.With the random rule,sites or bonds are added randomly into the lattice.From two candidates picked randomly,the site or bond with the smaller size product of two connected clusters is added when the product rule is taken.Not only the size of the largest cluster but also its size jump are studied to characterize the universality class of percolation.The finite-size scaling forms of giant cluster size and size jump are proposed and used to determine the critical exponents of percolation from Monte Carlo data. It is found that the critical exponents of both size and size jump in random site percolation are equal to that in random bond percolation. With the random rule,site and bond percolation belong to the same universality class.We obtain the critical exponents of the site percolation under the product rule,which are diffrent from that of both random percolation and the bond percolation under the product rule.The universality class of site percolation differs different from that of bond percolation when the product rule is used.

PACS numbers:64.60.ah,64.60.De,89.75.Da,89.75.Hc Keywords:network,percolation phase transition

# I.INTRODUCTION

Traditionally， percolation phase transitions are considered to be continuous in various networks.However，Achlioptas et al. [1] concluded that the percolation transition in random network is discontinuous under the Achlioptas process (AP） in which the growth of large clusters is suppressed. During the evolution of a network under AP,edges are added into the network under product rule that the edge with minimum product of cluster sizes is connected from two randomly picked unoccupied edges.The percolation transitions under product rule in two-dimensional square lattice [2-4] and scalefree networks [4-6] are also investigated and argued to be discontinuous. Later,a series of investigations [7- 11,13] showed that different percolation transitions under product rule are actually continuous. In Ref. [7], Costa et al. [7] studied a model with stronger suppression of large clusters and its percolation transition is continuous.Lee et al. [8] concluded that the explosive percolation is continuous by studying cluster size distribution. Grassberger et al. [9] found that the explosive transition is still continuous but with unusual finite-size behavior. In the works of Liu et al.[10] and Fan et al. [11],a generalized Achlioptas process(GAP） was introduced to investigate the percolation transitions of two-dimensional lattice network and Erdos-Rényi (ER) network [12] respectively.In the generalized Achlioptas process，the edge with minimum product of cluster sizes is connected witha probability $p$ from two randomly picked unoccupied edges.When $p = 1 / 2$ ,GAP recovers to a random process.With $p = 1$ ，GAP becomes AP. The percolation transitions of two-dimensional lattice network and ER network under GAP keep to be continuous. Their critical exponents and and therefore universality classes depend on the probability parameter $p$ . With a rigorous mathematical proof,Riordan and Warnke [13] concluded that the percolation transitions under all Achlioptas processes are continuous.

The site percolation on a two-dimensional square lattice under product rule was first investigated by Choi et al.[14]. They claimed that the percolation is discontinuous from the non-vanishing hysteresis between the directed and reverse process for the fraction of the sites belonging to the largest cluster.However,Bastas et al. [15] demonstrated that the hysteresis phenomena will disappear in the thermodynamic limit.Using the finite-size behaviors of the largest cluster and its standard deviation,they concluded that the explosive percolation transition is continuous but belongs to different universality class. To clarify this controversy, further investigations are needed.

The notation of a universality class is a basic tenet in the physics of critical phenomena.Within a universality class, the universal quantities such as critical exponents and scaling functions are independent of microscopic details.It is accepted traditionally that a universality class is characterized by the spatial dimensionality of the system and by the number of the components of the order parameter.(See,e.g.,the review article [16].）On a twodimensional lattice, the random bond percolation has the same critical exponents as the random site percolation. The random bond and site percolation belong to the same universality class.For the bond percolation under GAP with $p > 1 / 2$ ,their critical exponents are different from that of randombondpercolationand depend on the probabilityparameter $p$ [10].The universality classes of bond percolation under GAP are different from that of random bond percolation [1O].It is of interest to investigate the critical behaviors and universality class of site percolation in relation to the Achlioptas process.

In this paper,we study the critical behaviors of site percolation under AP in two-dimensional square lattice. We investigate the sizes of giant clusters in the lattice. From the finite-size scaling behaviors of giant clusters, we can determine the percolation transition point and the corresponding critical exponents. Both the critical exponents of the sizes of giant clusters and their size gaps during evolution [8,17,18] are calculated.

Our paper is organized as following. In Section 2,we present the finite-size scaling behaviors of giant clusters near the phase transition point of percolation. The finitesize scaling behaviors of giant clusters for site percolation under random and product rules on two-dimensional lattice are studied in Sections 3 and 4 respectively. The universality classes of bond and site percolation under random and product rules are discussed in Section 5.

# II. CRITICALBEHAVIORSOFPERCOLATION PHASE TRANSITION

The percolation phase transition in a network with $N = L ^ { d }$ nodes is indicated by the appearance of a giant cluster whose size becomes comparable with $N$ . The size $S _ { 1 }$ of the giant cluster is taken as the order-parameter of percolation phase transition. Near a critical point,the size $S _ { 2 }$ of the second largest cluster in the network becomes comparable with $N$ also.Both $S _ { 1 }$ and $S _ { 2 }$ demonstrate critical behavior near the critical point [1O,11].

Following the finite-size scaling of order-parameter [23, 24],we anticipate that the reduced sizes of $S _ { 1 }$ and $S _ { 2 }$ ina network with $N$ nodes and $N _ { r }$ edges follow the finite-size scaling form as [10,11]

$$
\begin{array} { r } { s _ { 1 } ( r , L ) \equiv S _ { 1 } / L ^ { d } \ = \ L ^ { - \beta / \nu } \tilde { s } _ { 1 } ( t L ^ { 1 / \nu } ) , } \\ { s _ { 2 } ( r , L ) \equiv S _ { 2 } / L ^ { d } \ = \ L ^ { - \beta / \nu } \tilde { s } _ { 2 } ( t L ^ { 1 / \nu } ) , } \end{array}
$$

where $r \ : = \ : N _ { r } / N$ is the reduced number of edges and $t = ( r - r _ { c } ) / r _ { c }$ is the deviation from critical point $r _ { c }$ . The scaling variable $t L ^ { 1 / \nu }$ is related to the size ratio $L / \xi$ of $L$ to the correlation length in bulk $\xi = \xi _ { 0 } | t | ^ { - \nu }$ . The finitesize scaling form is supposed to be valid in the asymptotic critical region with $L \gg 1$ and $| t | \ll 1$ ：

From Eqs.(1） and (2)，the finite-size scaling form of size ratio $s _ { 2 } / s _ { 1 }$ is obtained as

$$
s _ { 2 } / s _ { 1 } = \tilde { s } _ { 2 } ( t L ^ { 1 / \nu } ) / \tilde { s } _ { 1 } ( t L ^ { 1 / \nu } ) \equiv U ( t L ^ { 1 / \nu } ) .
$$

At the critical point $r _ { c }$ ，the size ratio $s _ { 2 } / s _ { 1 } = U ( 0 )$ and becomes independent of system size $L$ .The curves $s _ { 2 } / s _ { 1 }$ of different $L$ against $r$ have a cross-point,which can be used to determine the critical point $r _ { c }$ ：

The logarithm of Eq.(1) is

$$
\ln s _ { 1 } ( r , L ) = - ( \beta / \nu ) \ln L + \ln \tilde { s } _ { 1 } ( t L ^ { 1 / \nu } ) .
$$

At the critical point,we have which is a straight line against $\ln { \cal L }$ .We can fix the critical point $r _ { c }$ by the straight line of $\ln s _ { 1 } ( r , L )$ with respect to $\ln { \cal L }$ .From the slope of the straight line,we can determine the critical exponent ratio $\beta / \nu$ . By introducing scaling variable $t L ^ { 1 / \nu }$ to make curves $s _ { 2 } / s _ { 1 }$ of different $L$ collapse into a scaling function $U ( t L ^ { 1 / \nu } )$ , the critical exponent $\nu$ can be estimated.

There are critical behaviors also during the evolution of a network. The percolation phase transition is accompanied not only by the appearance of a giant cluster but also by the giant size jump of the largest cluster.In the Refs.[17] and [18], the percolation phase transition was investigated by the size jumps of the largest cluster.

In a simulation of network evolution,edges are added under some rule one by one into network. At an evolution step $T$ ,the number of edges in the network increases from $T - 1$ to $T$ and the size of the largest cluster varies correspondingly from $S _ { 1 } ( T - 1 )$ to $S _ { 1 } ( T )$ .At this step,the largest cluster has a reduced size jump $\delta _ { T } \equiv \left[ S _ { 1 } ( T ) - S _ { 1 } ( T - 1 ) \right] / N$ .The largest reduced size jump of the whole evolution process is

$$
\Delta \equiv m a x \left\{ \delta _ { 1 } , \delta _ { 2 } , \delta _ { 3 } , . . . \right\} .
$$

The evolution step,where the largest size jump appears,is denoted as $T _ { c }$ . In the $i$ -th simulation,we obtain the largest reduced size jump $\Delta ^ { ( i ) }$ and the critical reduced evolution step $r _ { c } ^ { ( i ) } = T _ { c } ^ { ( i ) } / N$ . From the results of $M$ simulations,we can calculate following averages

$$
\begin{array} { l } { { \bar { \Delta } ( L ) = \displaystyle \frac { 1 } { M } \sum _ { i = 1 } ^ { M } \Delta ^ { ( i ) } , } } \\ { { \bar { r } _ { c } ( L ) = \displaystyle \frac { 1 } { M } \sum _ { i = 1 } ^ { M } r _ { c } ^ { ( i ) } . } } \end{array}
$$

In the bulk limit $L  \infty$ ，we suppose that $\bar { r } _ { c } ( L )$ ap proaches its bulk limit $r _ { c } ( \infty )$ as

$$
\bar { r } _ { c } ( L ) = r _ { c } ( \infty ) + a _ { r } L ^ { - 1 / \nu _ { 1 } } .
$$

The bulk limit $r _ { c } ( \infty )$ from the network evolution should be equal to the critical point $r _ { c }$ obtained from the largest cluster.

The character of percolation phase transition can be determined from the finite-size effect of $\Delta ( L )$ If $\Delta ( L )$ approaches a non-zero value in the limit $L \to \infty$ , the percolation is a discontinuous phase transition.For a continuous percolation phase transition, $\Delta ( L )$ has a power-law finite-size effect as

$$
\bar { \Delta } ( L ) = a _ { \Delta } L ^ { - \beta _ { 1 } } .
$$

In the $i$ -th simulation of network evolution,there are fuctuations $\delta r _ { c } = r _ { c } ^ { ( i ) } - \bar { r } _ { c } ( L )$ and $\delta \Delta = \Delta ^ { ( i ) } - \bar { \Delta } ( L )$ Their root mean squares are calculated as

$$
\ln s _ { 1 } ( r _ { c } , L ) = - ( \beta / \nu ) \ln L + \ln \tilde { s } _ { 1 } ( 0 ) \ ,
$$

$$
\begin{array} { r } { \chi _ { r } \equiv \sqrt { < ( \delta r _ { c } ) ^ { 2 } > } , } \\ { \chi _ { \Delta } \equiv \sqrt { < ( \delta \Delta ) ^ { 2 } > } . } \end{array}
$$

Their dependence on network size $L$ is described by the exponents $\nu _ { 2 }$ and $\beta _ { 2 }$ as

$$
\begin{array} { r c l } { { } } & { { } } & { { \chi _ { r } ~ \propto ~ L ^ { - 1 / \nu _ { 2 } } , } } \\ { { } } & { { } } & { { \chi _ { \Delta } ~ \propto ~ L ^ { - \beta _ { 2 } } . } } \end{array}
$$

In Ref.[17], the asymptotic behavior of $\Delta ( L )$ was used to judge the continuity of a percolation phase transition. The so-called upper pseudo transition point in Ref. [8] was estimated from $\bar { r } _ { c } ( L )$ . The general clique percolation phase transition in random networks are identified by studying the averages and fluctuations of $\Delta$ and $r _ { c }$ [18].

We will investigate the above critical behaviors of a percolation phase transition,which are characterized by the critical exponents $\beta$ ， $\beta _ { 1 }$ $\beta _ { 2 }$ ， $\mathbf { \Delta } _ { V } , \mathbf { \Delta } _ { V 1 }$ and $\nu _ { 2 }$ .The different percolation phase transitions with the same critical exponents belong to the same universality class.

# III.RANDOMSITEPERCOLATIONON TWO-DIMENSIONAL SQUARELATTICE

On a two-dimensional square lattice,the percolation transition can be investigated both for site and bond. For the site percolation,we consider a $L \times L$ square lattices with periodic boundary conditions in both directions.At first,there are $N = L \times L$ unoccupied sites in a lattice. Then the sites in the lattice are occupied one by one under some rule. Clusters consisting of adjacent sites appear during the evolution.When $N _ { r }$ sites are occupied in the lattice,we define a reduced number of occupied sites $r = N _ { r } / N$ . If the size of the largest cluster becomes comparable with $N$ ，there is a site percolation in the lattice.

For the random site percolation (SP),sites are added randomly.It is known that SP on two-dimensional square lattice occurs at $r _ { c } = 0 . 5 9 2 7 6 4 2 1 ( 1 3 )$ [19].From Coulomb gas arguments [2O] and conformal feld theory [21],the critical exponents $\beta = 5 / 3 6$ and $\nu = 4 / 3$ werepredicted.

Inour Monte Carlo simulation of site percolation， the algorithm of Newmann and Ziff[19,22] has been used.We have taken lattice sizes $\begin{array} { r l } { L } & { { } = } \end{array}$ 32,64,128,256,512,1024,2048,4096 and 8192in our simulations.12,8oo,Ooo independent simulations have been run for each lattice size.

In Fig.1, the size ratio $s _ { 2 } / s _ { 1 }$ is plotted with respect to $r$ for three different lattice sizes.From its cross-point, we get the critical point $r _ { c } = 0 . 5 9 2 7 6 ( 3 )$ which agrees with the results of Ref.[19].

In Fig.2, $\ln { s _ { 1 } }$ is shown with respect to $\ln { \cal L }$ for three different $r$ .At $r = 0 . 5 9 2 7$ , the curve is nearly a straight line with slope equal to $- 0 . 1 0 8$ . The curvature becomes negative for $r ~ = ~ 0 . 5 9 2 4$ and positive for $r ~ = ~ 0 . 5 9 3 0$ We can conclude that the critical point $r _ { c } = 0 . 5 9 2 7 ( 3 )$ and the critical exponent ratio $\beta / \nu = 0 . 1 0 8 ( 4 )$ ，which agrees well with the exact value $\beta / \nu = 5 / 4 8$ .Within error bounds,the critical point from $\ln { s _ { 1 } }$ agrees with that from $s _ { 2 } / s _ { 1 }$ .Using $1 / \nu = 0 . 7 5$ in Fig.3, three curves of $s _ { 2 } / s _ { 1 }$ at $L = 2 5 6 , 5 1 2 , 1 0 2 4$ collapse into a scaling func tion function $U ( t L ^ { 1 / \nu } )$

![](images/3ef383b0c45489b1db6f642c061eb0ede24eb5cf8a47dc6d0f7d1f833eb8ebdf.jpg)  
Figure 1: Size ratio of the second largest cluster to the largest cluster $U = s _ { 2 } / s _ { 1 }$ .The critical point of site percolation $r _ { c } = $ 0.59276(3)is obtained from its cross-point.

![](images/29ab2b43b5691be03ef55d5ad9c678cac180cb8d6d171377cc62eb68678e2699.jpg)  
Figure 2:Log-log plot of $s _ { 1 }$ with respect to $L$ for three different reduced number of occupied sites $r$ .At $r _ { c } = 0 . 5 9 2 7 ( 3 )$ the curve becomes a straight line and its slope gives the critical exponent ratio $\beta / \nu = 0 . 1 0 8$ ：

In Fig.4,we show critical behaviors of the largest cluster during the evolution of SP.The Monte Carlo simulation results of $\bar { r } _ { c } ( L )$ are demonstrated in Fig.4(A). Using $r _ { c } ( \infty ) = 0 . 5 9 2 7 ( 3 )$ from the above investigation,a log-log plot of $r _ { c } ( \infty ) - \bar { r } _ { c } ( L )$ with respect to $L$ is made. Our Monte Carlo data demonstrate a linear dependence of $\ln [ r _ { c } ( \infty ) - \bar { r } _ { c } ( L ) ]$ on $\ln { \cal L }$ . From its slope,we obtain the inverse of exponent $1 / \nu _ { 1 } = 0 . 7 5 ( 1 )$ .In Fig.4(B), the power-law finite-size behavior of $\bar { \Delta } ( L )$ in Eq.(10) is confirmed by the Monte Carlo simulation data.The exponent $\beta _ { 1 } = 0 . 1 0 4 ( 1 )$ is calculated from the slope of the straight line.

![](images/b5a0702cd7d53407037deb2a28f1b0600312e9dc4e20ca9545e9beecc0df87e3.jpg)  
Figure 3: Finite-size scaling function $U ( t L ^ { 1 / \nu } )$ of the size ratio （20 $s _ { 2 } / s _ { 1 }$ for random site percolation with $1 / \nu = 0 . 7 5$

![](images/b4066231f6441ef23e342ebb85d565a63b3274a1391c0a060d905053c7848739.jpg)  
Figure 4:Critical behaviors of random site percolation during network evolution: (A)log-log plot of $r _ { c } ( \infty ) - \bar { r } _ { c } ( L )$ with $r _ { c } ( \infty ) = 0 . 5 9 2 7$ and the exponent $1 / \nu _ { 1 } = 0 . 7 5 ( 1 )$ ； (B)log-log plot of $\Delta ( L )$ with the exponent $\beta _ { 2 } = 0 . 1 0 4 ( 1 )$ ; (C)log-log plot of $\chi _ { r }$ with the exponent $1 / \nu _ { 2 } = 0 . 7 4 ( 1 )$ ； (D)log-log plot of $\chi \Delta$ with the exponent $\beta _ { 2 } = 0 . 1 0 4 ( 1 )$ ：

The root mean squares of fluctuations $\chi _ { r }$ and $\chi \Delta$ are shown in Figs.4(C) and (D). Our Monte Carlo simulation data of $\chi _ { r }$ follow a power-law dependence on $L$ with the exponent $1 / \nu _ { 2 } = 0 . 7 4 ( 1 )$ . The power-law behavior of $\chi \Delta$ （204号 in Eq.14 is confirm by our simulation data and we obtain $\beta _ { 2 } = 0 . 1 0 4 ( 1 )$ ：

We have investigated also the evolution critical behaviors of random bond percolation (BP） on twodimensional square lattice. These results of BP are given in Table.I.We can see that the critical exponents of SP are equal to that of BP.Further, the critical exponent ratio $\beta / \nu$ is equal to $\beta _ { 1 }$ and $\beta _ { 2 }$ and $\nu$ is equal to $\nu _ { 1 }$ and $\nu _ { 2 }$ within error bounds.

# IV. SITEPERCOLATIONUNDERPRODUCTRULEON TWO-DIMENSIONAL SQUARELATTICE

In this section,we consider the site percolation under product rule (SPPR). We take the product rule [14, 15] for the site evolution as follows:(1)selecting two unoccupied sites randomly; (2)calculating the product of sizes of the clusters which are connected by two chosen sites respectively;(3)the site with smaller product is occupied.

The reduced sizes $s _ { 1 }$ of the largest cluster for lattice size $L$ from 512 to 8192 are shown in Fig.5. $s _ { 1 }$ is nearly zero at small $r$ and becomes finite when $r$ is larger than a critical value $r _ { c }$ .Finite $s _ { 1 }$ indicates the emergence of a giant cluster and a site percolation transition.

The results obtained from the size of the largest cluster are shown in Figs.6,7 and 8.From the fixed point of $s _ { 2 } / s _ { 1 }$ in Fig.6,we can get the critical point （20 $r _ { c } = 0 . 7 6 3 4 ( 2 )$ . The straight line in Fig.7 gives the critical point $r _ { c } ~ = ~ 0 . 7 6 3 4 ( 5 )$ ，which is in agreement with the value of the fixed point.The accuracy of our critical point is higher than that of $r _ { c } = 0 . 7 6 8 ( 3 )$ in Ref.[14] and $r _ { c } = 0 . 7 5 6 ( 6 )$ in Ref.[15].

![](images/5624bbb7aed224736775b3e534533df9c3b26b54d0d229b7d72850dbe40569c8.jpg)  
Figure 5:Reduced size of the largest cluster as a function of $r$ at lattice size $L = 5 1 2$ ,1024,2048,4096,8192.

![](images/66eb4a520aa3815af3a9234cda5dcf5935180e3248624c50c11fe4bdce790566.jpg)  
Figure 6: Size ratio of the second largest cluster to the largest cluster $U = s _ { 2 } / s _ { 1 }$ at different lattice sizes.Its fixed point gives the critical point $r _ { c } = 0 . 7 6 3 4 ( 2 )$ ：

The slope of the straight line in Fig.7 gives the critical exponent ratio $\beta / \nu = 0 . 0 1 0 ( 1 )$ ，which is different from $\beta / \nu = 0 . 0 4 \pm 0 . 0 2$ of Ref.[15].

We can see in Fig.8 that the size ratios $s _ { 2 } / s _ { 1 }$ of different lattice sizes collapse well with the scaling variable $t L ^ { 1 / \nu }$ for data of $L \ge 5 1 2$ . This means that the asymp totic region of SPPR is more restricted than that of SP. In the finite-size scaling plot of $s _ { 2 } / s _ { 1 }$ ，we use the inverse of the critical exponent $1 / \nu = 0 . 4 2 ( 1 )$

![](images/019c9dcccec5f2ff25759a34e871bbe01a3c0545e27586d5ab25eadde024129d.jpg)  
Figure 7: $\ln { s _ { 1 } }$ with respect to $\ln { \cal L }$ around the critical point （204号 $r _ { c } = 0 . 7 6 3 4 ( 5 )$ ，where the curve becomes a straight line with slope equal to $- 0 . 0 1 0$

![](images/f1a139b51ffab0c4c5b6e51f5f08e100bad89653f462960c4942d7e61726ee75.jpg)  
Figure 8: Finite-size scaling function $U ( t L ^ { 1 / \nu } )$ of size ratio $s _ { 2 } / s _ { 1 }$ with $1 / \nu = 0 . 4 2$ ：

The size ratio at critical point $U ( 0 )$ is supposed to be universal. We obtain $U ( 0 ) = 0 . 0 3$ for SPPR and $U ( 0 ) =$ 0.1 for SP.This difference of $U ( 0 )$ indicates also that SPPR and SP belong to different universality class.

We have studied also the size jumps of the largest cluster during network evolution for SPPR.The different quantities related to the size jump are shown in Fig.9 with respect to the lattice size $L$ . From Fig.9(A), we can conclude that the average transition point approaches to its bulk limit according the power-law in Eq.11. Using the Monte Carlo data of the lattice size $l \geq 5 1 2$ ，we get the inverse of exponent $1 / \nu _ { 1 } = 0 . 4 2 ( 2 )$ The root mean square of the fluctuations of transition point is plotted in Fig.9(C) and a power-law in Eq.13 is found $1 / \nu _ { 2 } = 0 . 4 2 ( 3 )$ .The simulation results of the size jumps of the largest cluster are presented in Figs.9(B) and (D). The average size jump $\bar { \Delta }$ shows a quite different $L$ -dependence from that of the random site percolation. No power-law behavior is found for $\Delta ( L )$ ，which increases with $L$ at first and then decreases. The root mean square of fluctuations of $\Delta$ follows a power-law of the lattice size also.From Monte Carlo simulation data, we get $\beta _ { 2 } = 0 . 0 0 8 ( 4 )$ ：

For comparison，we have studied also the evolution critical behaviors of bond percolation under product rule (BPPR).The critical exponents related to the cluster size jump $\beta _ { 1 } ~ = ~ 0 . 0 4 4 ( 5 )$ and $\beta _ { 2 } ~ = ~ 0 . 0 4 1 ( 4 )$ are obtained.For the exponents related to critical point，we get $1 / \nu _ { 1 } = 0 . 9 9 ( 5 )$ and $1 / \nu _ { 2 } = 0 . 9 4 ( 3 )$ . The critical exponent ratio $\beta / \nu$ and the inverse of critical exponent $1 / \nu$ of BPPR have been calculated in Ref.[10]. $\beta / \nu = 0 . 0 6 4 ( 3 )$ is different from the exponents $\beta _ { 1 }$ and $\beta _ { 2 }$ .Within error bounds, $1 / \nu = 0 . 9 3 ( 1 )$ is equal to $1 / \nu _ { 1 }$ and $1 / \nu _ { 2 }$ .All results of BP, SP, BPPR and SPPR are summarized in Table.I.We can see that the critical exponents of BPPR are different from that of SPPR. The universality classes of BPPR and SPPR are different.

![](images/33f7b60fc10173f84665b918f774c7a0296a0e2510526181a33988ba1d0293ac.jpg)  
Figure 9: Results of site percolation under the product rule: (A)log-logplot of $r _ { c } ( \infty ) - \bar { r } _ { c } ( L )$ with $r _ { c } ( \infty ) = 0 . 7 6 3 4$ and the exponent $1 / \nu _ { 1 } = 0 . 4 2 ( 2 )$ ； (B)log-log plot of $\Delta ( L )$ ，which increases at first and then decreases slowly;(C)log-log plot of $\chi _ { r }$ with the exponent $1 / \nu _ { 2 } = 0 . 4 2 ( 3 )$ ； (D)log-log plot of $\chi \Delta$ （204号 with the exponent $\beta _ { 2 } = 0 . 0 0 8 ( 4 )$

Table I: Summary of critical points and critical exponents of BP, SP,BPPR and SPPR. $r _ { c }$ ， $\beta / \nu$ and $1 / \nu$ of BPPR are taken from Ref.[10].   

<html><body><table><tr><td>BP</td><td>SP</td><td>BPPR</td><td>SPPR</td></tr><tr><td>rc 0.5000(4)</td><td>0.5927(3)</td><td>0.5266(1)</td><td>0.7634(2)</td></tr><tr><td>1/v 0.75</td><td>0.75(1)</td><td>0.93(1)</td><td>0.42(1)</td></tr><tr><td>1/v1 0.75(1)</td><td>0.75(1)</td><td>0.99(5)</td><td>0.42(2)</td></tr><tr><td>1/v2 0.74(1)</td><td>0.74(1)</td><td>0.94(3)</td><td>0.42(3)</td></tr><tr><td>β/v 0.108(4)</td><td>0.108(4)</td><td>0.064(3)</td><td>0.010(1)</td></tr><tr><td>β1 0.105(2)</td><td>0.104(1)</td><td>0.044(5)</td><td></td></tr><tr><td>β 0.104(1)</td><td>0.104(1)</td><td>0.041(4)</td><td>0.008(4)</td></tr></table></body></html>

# V.CONCLUSION

We have studied the critical behaviors of the sizes and the size jumps of giant clusters on two-dimensional square lattice for both site and bond percolation under random and product rules respectively. Under the random rule,sites or bonds are added randomly into the lattice. We add the site or bond with smaller size product of two connected clusters into the lattice from two candidates picked randomly when the product rule is taken. The finite-size scaling forms of giant cluster size and size jumps are proposed and used to determine the transition points and critical exponents of the percolation transitions from Monte Carlo data.

Our results show that the critical exponents of the size and size jump of random site percolation are equal to that of random bond percolation within error bounds of Monte Carlo data. As expected, the universality class ofpercolation is independent of site and bond under the random rule.The critical exponents of the size and size jump in the site percolation under the product rule are different from that in the random percolation and also the bond percolation under the product rule. The site percolation and bond percolation under the product rule do not belong to the same universality class.

This work is supported by the National Natural Science Foundation of China under grant 11l21403.

[1]D.Achlioptas,R.M.D'Sousa and J.Spencer,Science 323,1453 (2009).   
[2]R.M.Ziff,Phys.Rev.Lett.103,045701 (2009).   
[3]R.M.Ziff,Phys.Rev.E.82,051105 (2010).   
[4]F.Radicchi and S.Fortunato,Phys.Rev.E.81,036110 (2010).   
[5] Y.S. Cho, J.S.Kim,J.Park,B.Kahng,and D.Kim, Phys.Rev.Lett.103,135702 (2009).   
[6] F.Radicchi and S.Fortunato,Phys.Rev.Lett.103, 168701 (2009).   
[7]R.A.da Costa,S.N.Dorogovtsev,A.V.Goltsev，and J.F.F.Mendes,Phys.Rev.Lett.105,255701 (2010).   
[8]H.K.Lee,B.J.Kim,and H.Park,Phys.Rev.E.84, 020101(R) (2011).   
[9] P.Grassberger,C.Christensen,G.Bizhani,S.W. Son, and M.Paczuski,Phys.Rev.Lett.106,225701 (2011).   
10] M.X.Liu, J.F.Fan,L.S.Li,and X.S.Chen,Eur.Phys J.B 85,132 (2012).   
11] J.F. Fan,M.X.Liu,L.S.Li,and X.S. Chen, Phys. Rev. E 85,061110 (2012).   
12] P.Erdos and A.Rényi,Publ.Math.Inst.Hungar.Acad. Sci.5,17 (1960).   
13] O.Riordan and L.Warnke, Science 333,322 (2011).   
14] W.Choi,S.H. Yook,and Y. Kim, Phys.Rev. E.84, 020102(R)(2011).   
15] N.Bastas,K.Kosmidis,and P.Augyrakis,Phys.Rev.E. 84,066112 (2011).   
[16]V.Privman,A.Aharony,and P.C.Hohenberg,in Phase TransitionandCriticalPhenomena,editedbyC.Domb and J.L.Lebowitz (Academic,New York,1991),Vol.14, P.1.   
[17] J.Nagler,A. Levina and M. Timme,Nat.Phys.7,265 (2011).   
[18]J.F.Fan and X.S.Chen，Europhys.Lett.107,28005 (2014).   
[19] M.E.J.Newmann and R.M. Ziff,Phys.Rev.Lett.85, 4104 (2000).   
[20] B.Nienhuis,in Phase Transition and Critical Phenomena,edited by C.Domb and J.L.Lebowitz,Vol.11(Academic,London,1987).   
[21]J.L.Cardy,in Phase Transition and Critical Phenomena,edited by C.Domb andJ.L.Lebowitz,Vol.11(Academic,London,1987).   
[22] M.E.J. Newmann and R. M. Ziff,Phys.Rev.E.64, 016706(2001).   
[23]V.Privman and M.E.Fisher,Phys.Rev.B.30,322 (1984).   
[24] V.Privman,Finite-size Scaling and Numerical Simulation of Statistical Systems,(World Scientific, Singapore, 1900).