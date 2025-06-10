# Null test of the cosmic curvature using $H ( z )$ and supernovae data

Rong-Gen Cai $^ { 1 }$ ,\* Zong-Kuan Guo $^ { 1 }$ ,† and Tao Yang1‡ $^ { 1 }$ State Key Laboratory of Theoretical Physics， Institute of Theoretical Physics, Chinese Academy of Sciences，P.O. Box 2735，Beijing 100190，China

We introduce a model-independent approach to the null test of the cosmic curvature which is geometrically related to the Hubble parameter $H ( z )$ and luminosity distance $d _ { L } ( z )$ . Combining the independent observations of $H ( z )$ and $d _ { L } ( z )$ ，we use the model-independent smoothing technique, Gaussian processes, to reconstruct them and determine the cosmic curvature $\Omega _ { K } ^ { ( 0 ) }$ in the null test relation.The null test is totally geometrical and does not assume any cosmological model. We show that the cosmic curvature $\Omega _ { K } ^ { ( 0 ) } = 0$ is consistent with current observational data sets, faling within the $1 \sigma$ limit.To demonstrate the effect on the precision of the null test,we produce a series of simulated data of the models with different $\Omega _ { K } ^ { ( 0 ) }$ .Future observations in better qualitycanprovide a greater improvement to constrain or refute the flat universe with $\Omega _ { K } ^ { ( 0 ) } = 0$ ：

PACS numbers:98.80.-k,98.80.Es,98.80Jk

# I. INTRODUCTION

Whether the space of our Universe is open, fat,or closed is one of the most fundamental problems in modern cosmology. The spatial topology of the Universe is also closely related to other important problems such as the evolution of the Universe, the property of the dark energy,etc. The effect of allowing nonzero curvature on dark energy models has been studied in many papers, see, for example,Refs.[1-4]. And the detection of a significant deviation from $\Omega _ { K } ^ { ( 0 ) } = 0$ would have profound consequences for inflation models and fundamental physics. A lot of attention has been attracted to this issue [5-8]. The ACDM model is consistent with all of the data and a flat universe is preferred even in recent Planck 2015 results [9].

However,almost all of the papers studying and constraining the cosmic curvature assume some specific models for dark energy such as the equation of state $w ( z )$ These are all model-dependent and indirect methods. Note the fact that there is some degeneracy between the spatial curvature and the equation of state of dark energy in these studies.It would be better to detect the space curvature of the Universe by geometrical and model-independent methods.In this paper，we use a geometrical relation among the cosmic curvature Ω, Hubble parameter $H ( z )$ ，and luminosity distance $d _ { L } ( z )$ ， by combining the Hubble rate and luminosity distance, weare ableto directly determine and test whether the cosmic curvature deviates from O [3,1O,11]. For this goal,we should focus on two independent observations that directly give $H ( z )$ and $d _ { L } ( z )$ ,respectively. For $H ( z )$ data,it can be derived from differential ages of galaxies ["cosmic chronometer (CC) "] and from the radial baryon acoustic oscillation(BAO）scale in the galaxy distribu tion. As for $d _ { L } ( z )$ ，we use the SNIa Union 2.1 data sets. We use the model-independent method Gaussian processes(GP）for smoothing the observational data. The advantage of these methods is that they are all modelindependent； hence,we need not assume any models involving dark energy and gravity theory. They are purely geometrical and are constrained directly by observational data.However, the precision of the null test is also limited by the quality of observational data.If we want to detect a tiny cosmic curvature more precisely,a better quality of the observational data sets are also required, which will be also discussed in this paper.

This paper is organized as follows. In Sec.I, we introduce the theoretical method for the null test of the cosmic curvature.In Sec.III,we first give a brief introduction of Gaussian processes,and then apply GP method to the null test of the cosmic curvature using two independent data sets:CC $^ +$ BAO，Union 2.1.Further it is followed by a series of simulated data tests.We give discussions and conclusions in Sec. IV.

# II. THEORETICALMETHOD

In a FLRW universe, the luminosity distance $d _ { L }$ can be expressed as

$$
d _ { L } = { \frac { c ( 1 + z ) } { H _ { 0 } \sqrt { \Omega _ { K } ^ { ( 0 ) } } } } \sinh ( \sqrt { \Omega _ { K } ^ { ( 0 ) } } \int _ { 0 } ^ { z } { \frac { d \tilde { z } } { E ( \tilde { z } ) } } ) ,
$$

where $E ( z ) ~ \equiv ~ H ( z ) / H _ { 0 }$ ， $\Omega _ { K } ^ { ( 0 ) } \equiv - K c ^ { 2 } / ( a _ { 0 } H _ { 0 } ) ^ { 2 }$ and $K = + 1 , - 1 , 0$ corresponds to a closed,open，and fat universe,respectively.

Differentiating Eq.(1) and writing $D ( z ) = ( H _ { 0 } / c ) ( 1 +$ $z ) ^ { - 1 } d _ { L } ( z )$ as the normalized comoving distance,we can obtain

$$
\Omega _ { K } ^ { ( 0 ) } = \frac { E ^ { 2 } ( z ) D ^ { \prime 2 } ( z ) - 1 } { D ^ { 2 } ( z ) } .
$$

We can see that the cosmic curvature $\Omega _ { K } ^ { ( 0 ) }$ can be directly determined by using the Hubble parameter and luminosity distance from Eq. (2). Thus, the null test of $\Omega _ { K } ^ { ( 0 ) }$ is straightforward. Note the fact that $D ( 0 ) = 0$ will bring about a singularity at $z = 0$ . Therefore for more succinct, we transform Eq. (2) to

$$
\frac { \Omega _ { K } ^ { ( 0 ) } D ^ { 2 } ( z ) } { E ( z ) D ^ { \prime } ( z ) + 1 } = E ( z ) D ^ { \prime } ( z ) - 1 .
$$

Since the left-hand side (lhs) of Eq.(3) is a nonzero when $z \neq 0$ if $\Omega _ { K } ^ { ( 0 ) }$ is nonvanishing, the null test of cosmic curvature $\Omega _ { K } ^ { ( 0 ) }$ is equivalenttothenull testof the whole lhs of Eq. (3). If we define

$$
\mathcal { O } _ { K } ( z ) \equiv \frac { \Omega _ { K } ^ { ( 0 ) } D ^ { 2 } ( z ) } { E ( z ) D ^ { \prime } ( z ) + 1 } ,
$$

then a fat universe implies

$$
\mathcal { O } _ { K } ( z ) = E ( z ) D ^ { \prime } ( z ) - 1 = 0
$$

is always true at any redshift.A deviation from it will indicate a signal of nonvanishing cosmic curvature.Note that the theoretical value of $\mathcal { O } _ { K } ( z )$ is always zero at $z =$ O.So the null test is just to check whether there exists signal of nonvanishing $\mathcal { O } _ { K } ( z )$ at nonzero redshifts.

Thus we should use current observational data sets to reconstruct $E ( z )$ and $D ^ { \prime } ( z )$ , independently,and combine these two reconstructions to test whether the relation $E ( z ) D ^ { \prime } ( z ) - 1 = 0$ holds at arbitraryredshifts.We want to stress here that the null test is totally geometrical and cosmological model independent,the reconstructions of $E ( z )$ and $D ^ { \prime } ( z )$ are directly derived from observational data sets.

# III. NULL TEST USING $H ( z )$ AND SUPERNOVAEDATA

Given some observational data sets，it is crucial to use a model-independent method to reconstruct $E ( z )$ $D ( z )$ ，and its derivative $D ^ { \prime } ( z )$ .There are many different methodologies to reconstruct functions from the data. For a brief analysis,see [12]. Since we should use a nonparametric approach to smooth the data and to reconstruct the derivative, the so-called Gaussian processes [13-16] are very suitable for our purpose.

# A．Gaussian processes

The Gaussian processes allow one to reconstruct a function from data without assuming a parametrization for it.Here,we use the Gaussian processes in Python (GaPP)[16]. This GP code has been used in various papers for different studies[16-24]. The distribution over functions provided by GP is suitable to describe the

observational data. At each point $z$ ，the reconstructed function $f ( z )$ is also a Gaussian distribution with a mean value and Gaussian error. The functions at different points $z$ and $\tilde { z }$ are related by a covariance function $k ( z , \tilde { z } )$ which only depends on a set of hyperparameters $\ell$ and .Here, $\ell$ gives a measure of the coherence length of $\textit { O f }$   
the correlation in the $x$ direction and $\sigma _ { f }$ denotes the overall amplitude of the correlation in the $y$ direction.Both of them will be optimized by GP with the observational data sets.In contrast to actual parameters,GP does not specify the form of the reconstructed function.Instead, it characterizes the typical changes of the function. The detailed analysis and description of the GP method can be found in [16, 19].

# B. Hubble rate data and Union 2.1

Following [17,18],we proceed to an analysis based onobservational Hubble data compiled from several sources,independent of SNeIa. We combine measurements of $H ( z )$ obtained with two methods.One is cosmic chronometers,which are mainly passively evolving galaxies. There are 21 data points compiled by Moresco et al.[25,26]. The other is radial baryon acoustic oscillations from galaxy clustering in redshift surveys,which gives seven data points of Hubble parameters from different experiments [27-30]. We summarize the total 28 data points in Table I.

We normalize $H ( z )$ using Ho = 70km/(s Mpc); thus, we get the observational data points of $E ( z )$ ． Then we can use GP method to reconstruct $E ( z )$ . Note that $H _ { 0 }$ is just a normalization factor,whose value will not influence our null test Eq. (5).

To reconstruct $D ( z )$ ，we use SNeIa Union 2.1 data sets [31],which contain 58O SNeIa data. We transform the distance modulus $m - M$ given in the data set to $D$ using

$$
m - M + 5 \log \left[ \frac { H _ { 0 } } c \right] - 2 5 = 5 \log \left[ ( 1 + z ) D \right] .
$$

For consistency, here we also use $H _ { 0 } = 7 0 \mathrm { k m / ( s } \mathrm { M p c } )$ to normalize $d _ { L } ( z )$ .Obtaining these 580 observational data points of $D ( z )$ ,we can also use GP method to reconstruct $D ( z )$ and its derivative $D ^ { \prime } ( z )$ .Finally,we combine the reconstructions of $E ( z )$ and $D ^ { \prime } ( z )$ and apply them to the null test of $\mathcal { O } _ { K } ( z )$ in Eq. (5).We stress again that the null test is model independent，so we need not assume any cosmological model,and the two data sets of $H ( z )$ and supernovae are also independent of each other.

# C. Null test

Having obtained the total 28 data points of $E ( z )$ and 580 points of $D ( z )$ ，we now use the GP method to reconstruct them,respectively.

![](images/58d9ba1d18dc402b32a8cf651e1d978f1ab65a2f024dbaf0c19edd0188f43f02.jpg)  
FIG.1:Gaussian precess reconstruction of $E ( z )$ (left） from CO $+$ BAO, $D ( z )$ (middle),and $D ^ { \prime } ( z )$ (right） from Union 2.1. The shaded blue regions are the $6 8 \%$ and $9 5 \%$ C.L.of the reconstruction. The flat ΛCDM model (red line)with $\Omega _ { m 0 } = 0 . 2 7$ is also shown.

![](images/320bd7331d4226fc0d1c851bb1c202f40c4a61a8310a8be680573dd0c462440b.jpg)  
FIG.2:Reconstruction of $\mathcal { O } _ { K } ( z )$ from $\mathrm { C C + }$ BAOandUnion 2.1.The shaded blue regions are the $6 8 \%$ and $9 5 \%$ C.L.of the reconstruction.The red line corresponds to the flat universe $\Omega _ { K } ^ { ( 0 ) } = 0$ ：

higher redshifts, the errors become large due to the poor quality data in that region. Using the reconstructions of $E ( z )$ and $D ^ { \prime } ( z )$ ，we apply Monte Carlo sampling to determine the $\mathcal { O } _ { K } ( z )$ in Eq.(5)at each point $z$ ，which we want to reconstruct.In Fig.2,it is shown that the reconstructed $\mathcal { O } _ { K } ( z )$ is consistent with the vanishing cosmic curvature,falling in the $1 \sigma$ limit.It tells us that there is no significant signal to indicate the deviation of the cosmic curvature $\Omega _ { K } ^ { ( 0 ) }$ from $0$ at the current observational data $[ H ( z )$ and supernovae] level.In addition,let us mention that the mean value of the cosmic curvature is negative in the high redshift region,which is also consistent with the results from model-dependent constraints in the literature.

TABLE I: $H ( z )$ measurements from different surveys using passively evolving galaxies and radial BAO.   

<html><body><table><tr><td>Index</td><td>2</td><td>H(z)</td><td>Refs.</td></tr><tr><td>1</td><td>0.090</td><td>69±12</td><td>[25]</td></tr><tr><td>2</td><td>0.170</td><td>83±8</td><td>[25]</td></tr><tr><td>3</td><td>0.179</td><td>75±4</td><td>[25]</td></tr><tr><td>4</td><td>0.199</td><td>75±5</td><td>[25]</td></tr><tr><td>5</td><td>0.240</td><td>79.69 ±2.32</td><td>[27]</td></tr><tr><td>6</td><td>0.270</td><td>77 ±14</td><td>[25]</td></tr><tr><td>7</td><td>0.350</td><td>82.1 ± 4.9</td><td>[28]</td></tr><tr><td>8</td><td>0.352</td><td>83±14</td><td>[25]</td></tr><tr><td>9</td><td>0.400</td><td>95 ±17</td><td>[25]</td></tr><tr><td>10</td><td>0.430</td><td>86.45 ±3.27</td><td>[27]</td></tr><tr><td>11</td><td>0.440</td><td>82.6 ± 7.8</td><td>[29]</td></tr><tr><td>12</td><td>0.480</td><td>97±62</td><td>[25]</td></tr><tr><td>13</td><td>0.570</td><td>92.4 ± 4.5</td><td>[30]</td></tr><tr><td>14</td><td>0.593</td><td>104 ±13</td><td>[25]</td></tr><tr><td>15</td><td>0.600</td><td>87.9 ±6.1</td><td>[29]</td></tr><tr><td>16</td><td>0.680</td><td>92±8</td><td>[25]</td></tr><tr><td>17</td><td>0.730</td><td>97.3±7</td><td>[29]</td></tr><tr><td>18</td><td>0.781</td><td>105 ±12</td><td>[25]</td></tr><tr><td>19</td><td>0.875</td><td>125 ± 17</td><td>[25]</td></tr><tr><td>20</td><td>0.880</td><td>90±40</td><td>[25]</td></tr><tr><td>21</td><td>0.900</td><td>117 ± 23</td><td>[25]</td></tr><tr><td>22</td><td>1.037</td><td>154 ± 20</td><td>[25]</td></tr><tr><td>23</td><td>1.300</td><td>168 ±17</td><td>[25]</td></tr><tr><td>24</td><td>1.363</td><td>160 ± 33.6</td><td>[26]</td></tr><tr><td>25</td><td>1.430</td><td>177 ± 18</td><td>[25]</td></tr><tr><td>26</td><td>1.530</td><td>140 ±14</td><td>[25]</td></tr><tr><td>27</td><td>1.750</td><td>202 ±40</td><td>[25]</td></tr><tr><td>28</td><td>1.965</td><td>186.5 ± 50.4</td><td>[26]</td></tr></table></body></html>

# D. Mock data

We can see from Fig.1 that all of the reconstructions of $E ( z )$ ， $D ( z )$ ，and $D ^ { \prime } ( z )$ are consistent very well with the fat $\Lambda$ CDM model,which we assume for comparison. The dashed blue line is the mean of the reconstruction and the shaded blue regions are the 68% and $9 5 \%$ confidence level(C.L.）of the reconstruction.As expected,at

To demonstrate how a large number of data with what accuracy of the error will affect our null test when reconstructing $E ( z )$ and $D ( z )$ ，we firstly simulate a data set of 128 points for $E ( z )$ .Adopting the methodolOgy in [32l，we draw the error from a Gaussian distribution: $\sigma _ { E } ~ \sim ~ \mathcal { N } ( \bar { \sigma } , \epsilon )$ with $\bar { \sigma } ~ = ~ ( \sigma _ { + } + \sigma _ { - } ) / 2$ and $\epsilon = ( \sigma _ { + } - \sigma _ { - } ) / 4$ ，where $\sigma _ { + }$ and $\sigma _ { - }$ are the two straight lines that bound the uncertainties $\sigma ( z )$ of the observational $E ( z )$ data from above and below，respectively. Then $E ( z ) _ { s i m }$ is sampled from the Gaussian distribution $E ( z ) _ { s i m } \sim \mathcal { N } ( E ( z ) _ { f i d } , \sigma _ { E } )$ ,where $E ( z ) _ { f i d }$ is the theoretical value from the fiducial model.

![](images/11586ea1607be32de58f23d02077ea2d2493d721f3b3c69100c1c1736bc88ff2.jpg)  
FIG.3: Gaussian process reconstruction of $E ( z )$ ， $D ( z )$ (top)， $D ^ { \prime } ( z )$ ，and reconstruction of $\mathcal { O } _ { K } ( z ) ( b o t t o m )$ obtained from a mock data set of $E ( z )$ and future DES, assuming the concordance model with $\Omega _ { K } ^ { ( 0 ) } = 0$ (red line). The dashed blue line is the mean of the reconstruction,and the shaded blue regions are the $6 8 \%$ and $9 5 \%$ C.L.of the reconstruction,respectively.

As for simulated $D ( z )$ data,we create mock data sets of future SNeIa according to the Dark Energy Survey (DES) [33]. The DES is expected to obtain high quality light curves for about 40oo SNeIas from $z ~ = ~ 0 . 0 5$ to $z ~ = ~ 1 . 2$ .From Table 14 in [33]，we can calculate the errors of $D$ ， $\textit { O D }$ ，and the corresponding numbers of SNeIa for each redshift bin. At every redshift point $z$ ， $D ( z ) _ { s i m }$ is sampled from the normal distribution $D ( z ) _ { s i m } \sim \mathcal { N } ( D ( z ) _ { f i d } , \sigma _ { D } )$ ：

Having obtained the simulated data sets of $E ( z )$ and $D ( z )$ ，we use GP method to reconstruct $E ( z )$ ， $D ( z )$ ,and $D ^ { \prime } ( z )$ .Then we combine the reconstructions of $E ( z )$ and $D ^ { \prime } ( z )$ ,using Monte Carlo sampling to determine the $\mathcal { O } _ { K } ( z )$ and check whether GP can recover its theoretical value and distinguish it from $\Omega _ { K } ^ { ( 0 ) } = 0$ ：

We now simulate the data points for three different fiducial models:concordance model, namely, $\Lambda$ CDM model with $\Omega _ { K } ^ { ( 0 ) } = 0$ and $\Omega _ { m } = 0 . 3$ ; two models with nonvanishing cosmic curvature, $\Omega _ { K } ^ { ( 0 ) } = \pm 0 . 1 6$ and $\Omega _ { m } = 0 . 3$ ： We want to check whether the GP method can detect or recover all of them and distinguish them from each other. The results are shown in Figs. 3-5, respectively.

We can see from Fig. 3 that $E ( z )$ ， $D ( z )$ ,and $D ^ { \prime } ( z )$ are all reconstructed very well from the mock data sets assuming the concordance model $\Omega _ { K } ^ { ( 0 ) } = 0$ . And the reconstructed $\mathcal { O } _ { K } ( z )$ is also consistent with the concordance model nicely. As expected,at higher redshifts, the errors become large due to the poor quality data in that region. Furthermore,we see from Figs.4 and 5 that the reconstructions of model $\Omega _ { K } ^ { ( 0 ) } = \pm 0 . 1 6$ also recover the fiducial model very well, falling in the $1 \sigma$ limit and obviously deviating from the concordance model $\Omega _ { K } ^ { ( 0 ) } = 0$ at $9 5 \%$ C.L. The large errors and not so good reconstructions at high redshifts ( $z > 1 . 0$ ）are due to the poor quality data in that region for there are no simulated data of $D ( z )$ at $z > 1 . 2$ . Anyway,we can claim that with these quantities and errors of the observational data for $E ( z )$ and $D ( z )$ the GP method at least has the ability to detect the cosmic curvature $\Omega _ { K } ^ { ( 0 ) } \geq 0 . 1 6$ and to rule out $\Omega _ { K } ^ { ( 0 ) } = 0$ at $2 \sigma$ C.L.

However,as we have pointed out that the theoretical value of $\mathcal { O } _ { K } ( z )$ is always zero at $z = 0$ . So the theoretical valus of $\mathcal { O } _ { K } ( z )$ frthesemodelswith lifterent $\Omega _ { K } ^ { ( 0 ) }$ deviates from the model with $\Omega _ { K } ^ { ( 0 ) } = 0$ tiny at low redshifts. As $z$ increases,the difference becomes large.As a result,we can see from Figs.4 and 5 that it is very hard to rule out $\Omega _ { K } ^ { ( 0 ) } = 0$ at low redshifts. Maybe it can work out at a middle redshift ( $0 . 6 < z < 1 . 0$ ） as Figs. 4 and 5 show,but it is not always helpful when $\Omega _ { K } ^ { ( 0 ) }$ is smaller. So,if we wanttoetectmodelwith $\Omega _ { K } ^ { ( 0 ) } < 0 . 1 6$ or even smaller and can rule out $\Omega _ { K } ^ { ( 0 ) } = 0$ at $9 5 \%$ C.L., a larger number and higher quality data sets are required.

Figure 6 shows the reconstructed $\mathcal { O } _ { K } ( z )$ also using the mock data sets of $E ( z )$ and $D ( z )$ but with a quarter of the errors.The reconstructions are more nice.And the null test is more precise; it can detect the model with $\Omega _ { K } ^ { ( 0 ) } = 0 . 0 5$ or even smaller, ruling out $\Omega _ { K } ^ { ( 0 ) } = 0$ at $9 5 \%$ C.L.

![](images/38cbab773e9e9f6b74e85e1ea6236ce95f3cf4c636c5edbf35c529167536768c.jpg)  
FIG.4: Gaussian process reconstruction of $E ( z )$ ， $D ( z )$ (top)， $D ^ { \prime } ( z )$ ，and reconstruction of $\mathcal { O } _ { K } ( z ) ( b o t t o m )$ obtained from a mock data set of $E ( z )$ and future DES, assuming the fiducial model with $\Omega _ { K } ^ { ( 0 ) } = 0 . 1 6$ (green line). The dashed blue line is the mean of the reconstruction,and the shaded blue regions are the $6 8 \%$ and $9 5 \%$ C.L.of the reconstruction,respectively. The concordance model $\Omega _ { K } ^ { ( 0 ) } = 0$ is also shown (red line).

![](images/d8954909303d8a05496159f53d0e4b6449c78d912e9d13698469961dfcd32419.jpg)  
FIG. 5: Gaussian process reconstruction of $E ( z )$ ， $D ( z )$ (top）， $D ^ { \prime } ( z )$ ，and reconstruction of $\mathcal { O } _ { K } ( z ) ( b o t t o m )$ obtained from a mock data set of $E ( z )$ and future DES, assuming the fiducial model with $\Omega _ { K } ^ { ( 0 ) } = - 0 . 1 6$ (green line). The dashed blue line is the mean of the reconstruction,and the shaded blue regions are the $6 8 \%$ and $9 5 \%$ C.L.of the reconstruction,respectively. The concordance model $\Omega _ { K } ^ { ( 0 ) } = 0$ is also shown (red line).

![](images/8b8ead70f0bcfa90bd8fd831d6015147b2266659778553b05024e5100023a4d1.jpg)  
FIG. 6: Reconstructions of $\mathcal { O } _ { K } ( z )$ for models with different $\Omega _ { K } ^ { ( 0 ) }$ , the errors are a quarter of the original errors of the mockdata sets. (a) $\Omega _ { K } ^ { ( 0 ) } = 0 . 0 5$ ，(b） $\Omega _ { K } ^ { ( 0 ) } = - 0 . 0 5$ （c） $\Omega _ { K } ^ { ( 0 ) } = 0 . 0 9$ ，（d） $\Omega _ { K } ^ { ( 0 ) } = - 0 . 0 9$ ，（e） $\Omega _ { K } ^ { ( 0 ) } = 0 . 1 6$ ，(） $\Omega _ { K } ^ { ( 0 ) } = - 0 . 1 6$ , The shadedblue regions are the 68% and $9 5 \%$ C.L.for the reconstruction.

# IV. DISCUSSIONS AND CONCLUSIONS

In this paper,we have introduced a nonparametric ap proach to making a null test of the cosmic curvature.Using the Gaussian process method,we reconstructed the Hubble rate and distance-redshift relation $[ E ( z ) , D ( z )$ ， and $D ^ { \prime } ( z ) ]$ ，independently.In the reconstruction，we needed not to assume any cosmological model. By combining the reconstructions of $E ( z )$ and $D ^ { \prime } ( z )$ ，we can determine $\mathcal { O } _ { K } ( z )$ ，which is related to the cosmic curvature $\Omega _ { K } ^ { ( 0 ) }$ We have shown that $\Omega _ { K } ^ { ( 0 ) } = 0$ is consistent with current data sets (CC $^ +$ BAO,Union 2.1)， falling within the $1 \sigma$ limit,although the mean of the reconstructed curvature ${ \mathcal { O } } _ { K }$ is negative in the high redshift region,which is also consistent with the results from the model-dependent constraints in the literature.In addition,note that the mean of the reconstructed curvature ${ \mathcal { O } } _ { K }$ in Fig.3 is positive in the high redshift region for the fiducial flat ACDM model. In this sense, our result shown in Fig.2 indicates that there is a little possibility for a closed universe.

To demonstrate how a large number of data sets with different accuracies and errors will affect our null test, we create mock data sets of $E ( z )$ and $D ( z )$ using the methodology proposed in Refs. [32] and [33]. We found that with current quality of simulated data,the GP method can recover and distinguish models with a different cosmic curvature with an order of $1 0 ^ { - 1 }$ from $\Omega _ { K } ^ { ( 0 ) } = 0$ ： $\Omega _ { K } ^ { ( 0 ) }$ should decrease the uncertainties of the data sets.Making the errorsa quarter of the mock data,it can rule out $\Omega _ { K } ^ { ( 0 ) } = 0$ from the cosmic curvature with an order of $1 0 ^ { - 2 }$ at $9 5 \%$ C.L.

Based on a one-parameter extension to the sixparameter $\Lambda$ CDM model, CMB data [9, 34,35] provide a strong constraint on $\Omega _ { K } ^ { ( 0 ) }$ . This constraint can be improved dramatically byadding BAO data that break the geometricdegeneracy between $\Omega _ { K } ^ { ( 0 ) }$ and $H _ { 0 }$ However, the model assumption and priors on model parameters may bias estimates of the cosmic curvature. Here，we proposed a model-independent method for reconstructing the function $\mathcal { O } _ { K } ( z )$ with redshift,which characterizes a deviation from a flat universe.As we can see from Eq. (5)， $\mathcal { O } _ { K } ( z )$ is completely and directly determined by the Hubble parameter and luminosity distance.If we can reconstruct the Hubble parameter and luminosity distance,the reconstruction of the cosmic curvature is straightforward. GP is suitable for our purpose because it can smooth data and reconstruct a function model independently. Therefore,we can test the cosmic curvature neither assuming models nor imposing priors.Although current low-redshift data put weaker constraints on the cosmic curvature than CMB data, this method provides a new cross-check of the cosmic curvature using future data from large-scale structure measurements.

# Acknowledgments

This work is supported by the Strategic Priority Research Program of the Chinese Academy of Sciences, Grant No.XDB09000000. Z.K.G is supported by the National Natural Science Foundation of China Grants No. 11575272 and No.11335012.

[1]K.Ichikawa and T.Takahashi,Phys.Rev.D 73,083526 (2006)[astro-ph/0511821].   
[2]K.Ichikawa,M.Kawasaki,T.Sekiguchi and T.Takahashi, JCAP 0612,005 (2006) [astro-ph/0605481].   
[3] C.Clarkson,M.Cortes and B.A.Bassett,JCAP0708, 011(2007) [astro-ph/0702670 [ASTRO-PH]].   
[4] Y.G. Gong and A. Wang，Phys.Rev. D 75,043520 (2007）[astro-ph/0612196].   
[5]D.J.Eisenstein et al.[SDSS Collaboration],Astrophys. J.633,560 (2005) [astr0-ph/0501171].   
[6] M.Tegmark et al.[SDSS Collaboration],Phys.Rev.D 74,123507 (2006)[astro-ph/0608632].   
[7] G. B. Zhao, J. Q.Xia,H. Li,C. Tao, J. M.Virey, Z.H.Zhu and X.Zhang,Phys.Lett.B 648,8 (2007) [astro-ph/0612728].   
[8]E.L．Wright，Astrophys.J.664，633（2007）[astroph/0701584].   
[9] P.A.R.Adeetal.[PlanckCollaboration], arXiv:1502.01589 [astr0-ph.CO].   
10]A.Shafieloo and C.Clarkson,Phys.Rev.D 81,083537 (2010)[arXiv:0911.4858 [astro-ph.CO]].   
11]Y.L.Li, S.Y.Li,T.J. Zhang and T.P.Li,Astrophys. J.789,L15(2014) [arXiv:1404.0773 [astro-ph.CO]].   
12] S.D.P. Vitenti and M. Penna-Lima,JCAP 1509,no. 09,045 (2015) [arXiv:1505.01883 [astro-ph.CO].   
13]T.Holsclaw,U.Alam，B.Sanso,H.Lee,K.Heitmann, S.Habib and D.Higdon,Phys.Rev.D 82,103502 (2010) [arXiv:1009.5443 [astr0-ph.CO]].   
14] T.Holsclaw,U.Alam,B. Sanso,H.Lee,K.Heitmann, S.Habib and D.Higdon，Phys.Rev.Lett.105,241302 (2010)[arXiv:1011.3079 [astro-ph.CO]].   
15] T.Holsclaw,U.Alam,B. Sanso,H.Lee,K.Heitmann, S.Habib and D.Higdon,Phys.Rev.D 84,083501 (2011) [arXiv:1104.2041 [astro-ph.CO]].   
[16]M.Seikel,C.Clarkson and M.Smith,JCAP 1206,036 (2012)[arXiv:1204.2832 [astro-ph.CO]   
[17]M. Seikel,S. Yahya，R.Maartens and C. Clarkson, Phys.Rev.D 86,083001(2012) [arXiv:1205.3431 [astroph.CO]].   
[18] M.Bilicki and M. Seikel, Mon. Not.Roy. Astron. Soc. 425,1664(2012)[arXiv:1206.5130 [astro-ph.CO]].   
[19] M. Seikel and C.Clarkson， arXiv:1311.6678[astroph.CO].   
[20] S.Yahya，M.Seikel，C.Clarkson，R.Maartens and M.Smith，Phys.Rev.D 89，no.2，023503(2014) [arXiv:1308.4099 [astro-ph.CO]].   
[21]V.C.Busti,C.Clarkson and M.Seikel，Mon.Not. Roy. Astron. Soc.441,11 (2014) [arXiv:1402.5429 [astroph.CO]].   
[22] Y. Zhang,arXiv:1408.3897 [astro-ph.CO].   
[23] V.C. Busti and C. Clarkson,arXiv:1505.01821 [astroph.CO].   
[24] T.Yang,Z.K.Guo and R.G. Cai, Phys. Rev.D 91, no. 12,123533(2015) [arXiv:1505.04443 [astr0-ph.CO].   
[25]M.Moresco，L.Verde，L.Pozzetti，R.Jimenez and A.Cimatti，JCAP 1207，053（2012） [arXiv:1201.6658 [astro-ph.CO]].   
[26] M. Moresco,Mon.Not.Roy.Astron. Soc.450,no.1,L16 (2015）[arXiv:1503.01116 [astro-ph.CO]].   
[27] E.Gaztanaga,A. Cabre and L. Hui, Mon. Not. Roy. Astron.Soc.399,1663(2009) [arXiv:0807.3551 [astroph].   
[28] C.H. Chuang and Y.Wang,Mon. Not.Roy. Astron. Soc. 426,226(2012）[arXiv:1102.2251 [astro-ph.CO]].   
[29]C.Blake et al.，Mon.Not.Roy.Astron.Soc.425,405 (2012)[arXiv:1204.3674 [astro-ph.CO].   
[30] B.A.Reid et al.,Mon.Not.Roy.Astron. Soc. 426,2719 (2012)[arXiv:1203.6641 [astro-ph.CO]].   
[31] N. Suzuki et al., Astrophys.J. 746, 85 (2012) [arXiv:1105.3470 [astr0-ph.CO]].   
[32] C.Ma and T.J.Zhang,Astrophys.J.730,74(2011) [arXiv:1007.3787 [astro-ph.CO]].   
[33]J.P. Bernstein et al.,Astrophys.J.753，152 (2012) [arXiv:1111.1969 [astro-ph.CO]].   
[34]G.Hinshaw et al.[WMAP Collaboration]，Astrophys.J. Suppl.208,19 (2013)[arXiv:1212.5226 [astro-ph.CO]].   
[35]P.A.R.Ade et al. [Planck Collaboration],Astron.Astrophys.571,A16(2014) [arXiv:1303.5076 [astro-ph.CO]].