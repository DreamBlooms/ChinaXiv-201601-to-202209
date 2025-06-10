# Continuous percolation phase transitions of random networks under a generalized Achlioptas process

Jingfang Fan,1 Maoxin Liu,1 Liangsheng Li, $^ 2$ and Xiaosong Chenl （204 $^ { 1 }$ State Key Laboratory of Theoretical Physics， Institute of Theoretical Physics, Chinese AcademyofSciences，P.O.Box 2735，Beijing100190,China （204 $\mathcal { Z }$ Key Laboratory of Cluster Science of Ministry of Education and Department of Physics, Beijing Institute of Technology，Beijing 10oo81，China (Dated: January 13,2012)

Using the finite-size scaling,we have investigated the percolation phase transitions of evolving random networks under a generalized Achlioptas process (GAP).During this GAP,the edge with minimum product of two connecting cluster sizes is taken with a probability $p$ from two randomly chosen edges.This model becomes the Erdós-Rényi network at $p = 0 . 5$ and the random network under the Achlioptas process at $p = 1$ ．Using both the fixed point of $s _ { 2 } / s _ { 1 }$ and the straight line of $\ln { s _ { 1 } }$ ，where $s _ { 1 }$ and $_ { s 2 }$ are the reduced sizes of the largest and the second largest cluster，we demonstrate that the phase transitions of this model are continuous for $0 . 5 \le p \le 1$ .From the slopes of $\ln { s _ { 1 } }$ and $\ln ( s _ { 2 } / s _ { 1 } ) ^ { \prime }$ at the critical point we get the critical exponents $\beta$ and $\nu$ ，which depend on $p$ . Therefore the universality class of this model should be characterized by $p$ also.

PACS numbers:64.60.ah,64.60.De,89.75.Da,89.75.Hc Keywords:network,percolation phase transition

The modern theory of complex networks [1-3] has opened new perspectives in the study of complex systems in nature,social and economic systems,technical infrastructures and many other fields.The macroscopic properties of complex networks emerge from the interactions among individual constituents.The percolation phase transition of complex networks is an interesting macroscopic property and can be studied with the percolation theory in statistical physics [4]. It has been pointed out that the random network undergoes a continuous percolation phase transition during the random process [5]. The critical phenomena of complex networks arereviewed in Ref.[6].

However,Achlioptas et al.[7] reported that the percolationphase transition of randomnetworksbecomes discontinuous under the Achlioptas process (AP).During this AP, two unoccupied edges are chosen randomly and the edge with minimum product of the connecting cluster sizes is taken as the next occupied bond.This discontinuous phase transition in networks is called the explosive percolation [7]. The AP was applied later to other networks [8-1O] and some similar rules were also introduced [9-15].Using the finite-size scaling,the explosive percolation phase transition was also investigated [16,17]. These works support that the explosive percolation is discontinuous.Recently, Costa et al.[19] showed that the explosive percolation transition is actually a continuous phase transition with a uniquely small critical exponent. Riordan and Warnke [2O] prove mathematically that all Achlioptas processes have continuous phase transitions.

In this letter we investigate the percolation phase transitions of random networks under a generalized Achlioptas process (GAP).In the GAP, two unoccupied edges are chosen randomly and the edge with minimum product of two connecting cluster sizes is taken with a probability $p$ [22].At $p = 0 . 5$ ，this model becomes the Erdos-Rényi (ER)network [25]. At $p = 1$ ，the GAP is equivalent to the Achlioptas process which suppress the appearance of larger clusters. With the increase of $p$ from 0.5 to 1, this suppression is switched on gradually. After investigating the percolation phase transitions at different $p$ we can get more understanding about these phase transitions and make a more reliable conclusion about the character of the percolation phase transition at $p = 1$ ：

In our Monte carlo simulations,we begin with $N$ isolated nodes and then connect them with the edges added through the GAP. The network obtained is characterized by $N$ ，the number of edges $N _ { r }$ and the probability parameter $p$ of GAP. For $p ~ < ~ 1$ ，we take $N \ =$ （204号 $( 4 , \ 8 , \ 1 6 , \ 3 2 , \ 6 4 , \ 1 2 8 ) \times 1 0 ^ { 4 }$ and run 500,000 steps in each simulation. At $p = 1$ ，we choose much larger system sizes $N = ( 5 1 2 , 1 0 2 4 , 2 0 4 8 ) \times 1 0 ^ { 4 }$ to reach the asymptotic region of finite-size effects and run 1oo,Ooo steps in each simulation.

For the cluster ranked $R$ and with size $S _ { R } ( N _ { r } , ~ N ; ~ p )$ we define its reduced size as

$$
s _ { R } ( r , \ N ; \ p ) \equiv S _ { R } ( N _ { r } , \ N ; \ p ) / N ,
$$

where $r ~ \equiv ~ N _ { r } / N$ is the reduced edge number. The reduced size of the largest cluster $s _ { 1 } ( r , N ; p )$ at $N \ =$ $1 . 2 8 \times 1 0 ^ { 6 }$ is shown in Fig. 1. $s _ { 1 }$ becomes finite for $r > r _ { c }$ and there is a percolation phase transition. The transition point $r _ { c }$ increases with $p$ and the corresponding phase transition becomes sharper.

If the percolation phase transition is continuous, the reduced sizes $s _ { R } ( r , \ N ; p )$ should follow a finite-size scaling form [23, 24]

$$
s _ { R } ( r , N ; p ) = N ^ { - \beta / \nu } \widetilde { s } _ { R } ( t N ^ { 1 / \nu } ; p ) ,
$$

![](images/cca545762a1e9730b76d6ab35007fb928b3b9c3740077d37a569878da8d6acd2.jpg)  
Figure 1: Reduced size of the largest cluster at $N = 1 . 2 8 \times$ $1 0 ^ { 6 }$

where $t = ( r - r _ { c } ) / r _ { c }$ and $\nu$ is the critical exponent of the correlation length $\xi = \xi _ { 0 } \left| t \right| ^ { - \nu }$ . The scaling form in Eq. (2)is valid in the asymptotic critical region with $| t | \ll 1$ and $N \gg 1$ ．Outside this region，additional correction terms should be taken into account.

From Eq. (2),we can obtain

$$
s _ { 2 } / s _ { 1 } = \widetilde s _ { 2 } ( t N ^ { 1 / \nu } ; p ) / \widetilde s _ { 1 } ( t N ^ { 1 / \nu } ; p ) \equiv U ( t N ^ { 1 / \nu } ; p )
$$

and

$$
\ln s _ { 1 } ( r , N ; p ) = - \beta / \nu \ln N + \ln \widetilde s _ { 1 } ( t N ^ { 1 / \nu } ; p ) .
$$

At a critical point, $s _ { 2 } / s _ { 1 } | _ { r = r _ { c } } = U ( 0 ; p )$ is a fixed point versus $N$ and $\ln s _ { 1 } ( r _ { c } , N ; p ) = - \beta / \nu \ln N + \ln \widetilde s _ { 1 } ( 0 ; p )$ is a straight line versus $\ln { N }$ .Using these properties,the critical point of complex network can be determined both from the fixed point of $s _ { 2 } / s _ { 1 }$ and the straight line of $\ln { s _ { 1 } }$ versus $\ln { N }$ . The critical exponent ratio $\beta / \nu$ can be obtained from the slope of $\ln { s _ { 1 } }$ at $r _ { c }$ ：

![](images/8f0fcda22527b81a4695482915eaa2dd63e95d4b0d2e9e6f6629d294acac80b6.jpg)  
Figure 2: (A) $s _ { 2 } / s _ { 1 }$ has a fixed point at $r _ { c } ^ { 1 } = 0 . 5 0 0 0 \pm 0 . 0 0 0 4$ (B)Log-log plot of the reduced size $s _ { 1 }$ versus $N$ .Around $r _ { c } ^ { 2 } = 0 . 5 0 0 0$ ,the curvature of $\ln { s _ { 1 } }$ changes its sign.

For $p = 0 . 5$ ,our model is equivalent to the ER model [25].Its continuous percolation phase transition can be studied with $s _ { 2 } / s _ { 1 }$ and $\ln { s _ { 1 } }$ . In Fig. 2(A), $s _ { 2 } / s _ { 1 }$ is shown as a function of $r$ at different $N$ .The different curves of $s _ { 2 } / s _ { 1 }$ for different $N$ have a fixed point at $r _ { c } ^ { 1 } = 0 . 5 0 0 0 ( 4 )$ In Fig. 2(B), $\ln { s _ { 1 } }$ is shown versus $\ln { N }$ for different $r$ The curvature of $\ln { s _ { 1 } }$ is negative at $r = 0 . 4 9 9 6$ and becomes positive at $r ~ = ~ 0 . 5 0 0 4$ ．At $r ~ = ~ 0 . 5$ ， $\ln { s _ { 1 } }$ isa straight line with slope $- 0 . 3 3 ( 1 )$ . We get $r _ { c } ^ { 2 } = 0 . 5 0 0 0 ( 4 )$ in consistence with $r _ { c } ^ { 1 }$ . Our results of $r _ { c }$ and $\beta / \nu$ agree with the exact results $r _ { c } = 0 . 5$ and $\beta / \nu = 1 / 3$ of the ER model [25].

In Fig.3, we show $s _ { 2 } / s _ { 1 }$ and $\ln { s _ { 1 } }$ of random network under the GAP at $p ~ = ~ 0 . 8$ .From the fixed point of $s _ { 2 } / s _ { 1 }$ ，we get the critical point $r _ { c } ^ { 1 } = 0 . 7 2 5 2 { \pm } 0 . 0 0 0 1$ . The curvature of $\ln { s _ { 1 } }$ is negative at $r = 0 . 7 2 5 0$ and becomes positive at $r = 0 . 7 2 5 4$ . So $r _ { c } ^ { 2 } = 0 . 7 2 5 2 \pm 0 . 0 0 0 2$ ,which is consistent with rl

For $p ~ = ~ 1 . 0$ ，our model becomes the PR model of Ref.[7]. $s _ { 2 } / s _ { 1 }$ at different $N$ are shown in Fig. 4(A） and there is a fixed-point at $r _ { c } ^ { 1 } = 0 . 8 8 8 4 4 ( 2 )$ . The curvature of $\ln { s _ { 1 } }$ is negative at $r = 0 . 8 8 8 4 0$ and becomes positive at $r = 0 . 8 8 8 5 0$ . We obtain $r _ { c } ^ { 2 } = 0 . 8 8 8 4 5 ( 5 )$ consistent with $r _ { c } ^ { 1 }$ . From the slope of $\ln { s _ { 1 } }$ at $r _ { c } ^ { 2 }$ ，we get $\beta / \nu = 0 . 0 4 ( 1 )$ Our $r _ { c }$ and $\beta / \nu$ at $p = 1$ agree well with Ref.[26].

To determine the critical exponent $\nu$ of correlation length,we study the derivative

$$
( s _ { 2 } / s _ { 1 } ) ^ { \prime } \equiv \frac { \partial ( s _ { 2 } / s _ { 1 } ) } { \partial r } = N ^ { 1 / \nu } r _ { c } ^ { - 1 } U ^ { \prime } ( t N ^ { 1 / \nu } ; p ) \ .
$$

Ata critical point,we have

$$
\ln ( s _ { 2 } / s _ { 1 } ) ^ { \prime } | _ { r = r _ { c } } = ( 1 / \nu ) \ln N + l n U ^ { \prime } ( 0 ; p ) - l n r _ { c } ,
$$

which is a straight line with slope $1 / \nu$ . From our Monte Carlo data,we can calculate $1 / \nu$ at different $p$ ,which are summarized in Table I.

![](images/bfb178b7296c624a5c05ea8d5c333d6620558893141bb027982463369c7a82ac.jpg)  
Figure 3: $( \mathrm { A } ) s _ { 2 } / s _ { 1 }$ has a fixed point at $r _ { c } ^ { 1 } = 0 . 7 2 5 2 \pm 0 . 0 0 0 1$ (B)Log-log plot of the reduced size $s _ { 1 }$ versus $N$ at different $r$ Around $r _ { c } ^ { 2 } = 0 . 7 2 5 2$ ,the curvature of $\ln { s _ { 1 } }$ changes its sign.

![](images/207cd2999bc5481bd7aad128681abafc833e6106d72ea43973e8abbe4ab1ada2.jpg)  
Figure 4:(A) $s _ { 2 } / s _ { 1 }$ has a fixed point at $r _ { c } ^ { 1 } ~ = ~ 0 . 8 8 8 4 4 \pm$ 0.00002.(B) Log-log plot of the reduced size $s _ { 1 }$ versus $N$ .At （204号 $r _ { c } ^ { 2 } = 0 . 8 8 8 4 5$ , the slope of $\ln { s _ { 1 } }$ versus $\ln { N }$ gives $\beta / \nu \approx 0 . 0 4$

Table I:Critical reduced edge number $r _ { c }$ ，critical exponent ratio $\beta / \nu$ and inverse of critical exponent $1 / \nu$ . We obtain $r _ { c } ^ { 1 }$ from $s _ { 2 } / s _ { 1 }$ and $r _ { c } ^ { 2 }$ from $\ln { s _ { 1 } }$ ：   

<html><body><table><tr><td>p</td><td>r1</td><td>r2</td><td>β/v</td><td>1/v</td></tr><tr><td>0.5</td><td>0.5000(4)</td><td>0.5000(4)</td><td>0.33(1)</td><td>0.33(1)</td></tr><tr><td>0.6</td><td>0.5599(1)</td><td>0.5599(3)</td><td>0.32(1)</td><td>0.33(1)</td></tr><tr><td>0.7</td><td>0.6349(2)</td><td>0.6349(3)</td><td>0.32(1)</td><td>0.34(1)</td></tr><tr><td>0.8</td><td>0.7252(1)</td><td>0.7252(2)</td><td>0.33(1)</td><td>0.35(1)</td></tr><tr><td>0.9</td><td>0.8216(1)</td><td>0.8216(3)</td><td>0.31(1)</td><td>0.38(1)</td></tr><tr><td>0.95 1.0</td><td>0.8603(2) 0.88844(2)</td><td>0.8604(2)</td><td>0.15(1) 0.04(1)</td><td>0.46(1) 0.50(1)</td></tr></table></body></html>

Using $r _ { c }$ and $1 / \nu$ given in Table I，we can define a finite-size scaling variable $t N ^ { 1 / \nu }$ at each $p$ .With this scaling variable，our Monte Carlo simulation data of $s _ { 2 } / s _ { 1 } ( r , N ; p )$ at a given $p$ and different $N$ collapse into a finite-size scaling function $U ( t N ^ { 1 / \nu } ; p )$ , which are shown in Fig.5 for $p = 0 . 5$ and $p = 1$ .The $p$ -dependence of $U ( 0 ; p )$ is demonstrated in Fig.6.

In summary,we have studied the percolation phase transitions of evolving random networks under a generalized Achlioptas process that the edge with minimum product of two connecting cluster sizes is taken with a probability $p$ from two randomly chosen edges. This model becomes the ER network [25] at $p \ = \ 0 . 5$ and the random network under the Achlioptas process [7] at $p = 1$ . Using the finite-size scaling,the percolation phase transitions of this model are studied.From the finite-size scaling forms of the largest cluster size $s _ { 1 } ( r , N ; p )$ and the second largest cluster size $s _ { 2 } ( r , N ; p )$ ，the fixed point of $s _ { 2 } / s _ { 1 }$ and the straight line of $\ln { s _ { 1 } }$ versus $\ln { N }$ can be used to determine the critical points.It has been found that the critical points $r _ { c }$ determined from $s _ { 2 } / s _ { 1 }$ and $\ln { s _ { 1 } }$ are consistent and increase with $p$ .From the slopes of $\ln { s _ { 1 } }$ and $\ln ( s _ { 2 } / s _ { 1 } ) ^ { \prime }$ at $r _ { c }$ ，we can obtain the critical exponent ratio $\beta / \nu$ and $1 / \nu$ respectively. $\beta / \nu$ decreases from $0 . 3 3 ( 1 )$ at $p = 0 . 5$ to $0 . 0 4 ( 1 )$ at $p = 1$ ： $1 / \nu$ increases from $0 . 3 3 ( 1 )$ at $p = 0 . 5$ to $0 . 5 0 ( 1 ) p = 1$ . With the scaling variable $t N ^ { 1 / \nu }$ ,the Monte Carlo data of $s _ { 2 } / s _ { 1 } ( r , N ; p )$ at

![](images/a0c0d3b693f23fc487307c3badde5358f27fcc8b72bede6a19566cf951491807.jpg)  
Figure 5: Finite-size scaling function $U ( t N ^ { 1 / \nu } ; p )$ at (A) $p =$ 0.5 with $1 / \nu = 0 . 3 3$ and (B) $p = 1 . 0$ with $1 / \nu = 0 . 5$ ：

![](images/599dd0f71c46cd3a9e51d1d3e3e0bafde3335d368191c57f60b7663cc37889f4.jpg)  
Figure 6: $U ( 0 ; p )$ with error bars smaller than the symbol. a given $p$ and different $N$ collapse into a scaling function

$U ( t N ^ { 1 / \nu } ; p )$ . The percolation phase transitions of random networks under the GAP are continuous always and its universality class depends on the probability parameter $p$ ：

This work is supported by the National Natural Science Foundation of China under grant 1o835005.

[1] R.Albert and A.-L. Barabasi, Rev.Mod. Phys. 74,47 (2002). 2] D.J Watts and S.H Strogatz, Nature 393,409 (1998) [3] M. E. J. Newman, Networks: An introduction, Oxford University Press,New York (2010). [4] D.Stauffer and A.Aharony,Introduction to Percolation Theory (Taylor & Francis,London,1994).   
[5] Béla Bollobas,Random Graphs (Cambridge University Press,Cambridge,2001).   
[6] S.N. Dorogovtsev,A.V.Goltsev,and J. F.F.Mendes, Rev.Mod.Phys.80,1275 (2008). [7]D.Achlioptas,R.M.D'Sousa,and J. Spencer,Science 323,1453 (2009). [8]R.M. Ziff,Phys.Rev.Lett.103,045701 (2009). [9] Y. S. Cho, J. S. Kim, J. Park,B.Kahng,and D. Kim, Phys.Rev.Lett.103,135702 (2009).   
[10]F.Radicchi and S. Fortunato，Phys.Rev.Lett. 103,168701 (2009).   
[11] E. J.Friedman and A.S.Landsberg,Phys.Rev.Lett. 103,255701 (2009).   
[12] Y. S. Cho,B. Kahng,and D. Kim, Phys. Rev. E. 81, 030103 (2010).   
[13] R.M.D'Souza and M. Mitzenmacher, Phys.Rev.Lett. 104,195702 (2010)   
[14] N.A.M.Araujo and H.J. Herrmann,Phys.Rev.Lett. 105,035701 (2010).   
[15] S. S. Manna and A. Chatterjee,Physica A 390，177 (2011).   
[16] Y. S. Cho,S.-W. Kim,and J. D. Noh,B.Kahng,and D.Kim,Phys.Rev.E 82,042102 (2010).   
[17]R.M. Ziff, Phys.Rev.E. 82,051105 (2010).   
[18]J.Nagler，A.Levina,and M.Timme,Nature Physics 7,(2011)   
[19] R.A. da Costa, S. N. Dorogovtsev,A. V. Goltsev，and J.F.F.Mendes,Phys.Rev.Lett.105,255701 (2010).   
[20] O.Riordan and L.Warnke, Science 333,322 (2011).   
[21] S.Fortunato and F.Radicchi,arXiv:11O1.356v1.   
[22] M.X.Liu, J.F.Fan,L.S.Li,and X.S. Chen,Eur.Phys. J.B,submitted.   
[23]V.Privman and M.E.Fisher,Phys.Rev.B.30,322(1984).   
[24]Finite Size Scaling and Numerical Simulation of Statistical Systems,edited by V.Privman(World Scientific,Singapore,1990).   
[25] P. Erdos and A.Rényi,Publ. Math. Inst. Hungar.Acad. Sci.5, 17 (1960).   
[26] P. Grassberger，C. Christensen,G. Bizhani, S.W. Son, and M. Paczuski, Phys.Rev.Lett.106, 225701 (2011).