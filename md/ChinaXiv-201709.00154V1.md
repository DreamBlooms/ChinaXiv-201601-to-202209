# Principal component analysis of the reionization history from Planck 2O15 data

Wei-Ming Dai,\* Zong-Kuan Guo,† and Rong-Gen Cai‡ State Key Laboratory of Theoretical Physics，Institute of Theoretical Physics, Chinese Academy of Sciences，P.O. Box 2735，Beijing 100190，China

The simple assumption of an instantaneous reionization of the Universe may bias estimates of cosmological parameters.In this paper a model-independent principal component method for the reionization history is applied to give constraints on the cosmological parameters from recent Planck 2015 data.We find that the Universe are not completely reionized at redshifts $z \geq 8 . 5$ at $9 5 \%$ （202 CL.Both the reionization optical depth and the matter fluctuation amplitude are higher than but consistent with those obtained in the standard instantaneous reionization scheme.The high estimated value of the matter fluctuation amplitude strengthens the tension between Planck CMB observations and some astrophysical data,such as cluster counts and weak lensing. The tension can significantly be relieved if the neutrino masses are allowed to vary. Thanks to a high scalar spectral index,the low-scale spontaneously broken SUSY inflationary model can fit the data well, which is marginally disfavored at 95% CL in the Planck analysis.

PACS numbers: 98.80.Cq

# 1.INTRODUCTION

Accurate measurements of the reionization history of the Universe plays an important role in understanding the early stages of structure and star formation.Fortunately, the evolution of the inter-galactic Lyman-alpha opacity measured in the spectra of quasars can provide valuable information on the reionization history [1]. The recent measurements suggest that the reionization of the inter-galactic medium was largely complete at redshift $z ~ \approx ~ 6$ [2]. The rapid decline in the space density of Lyman-alpha emitting galaxies in the region $z = 6 - 8$ also implies a low-redshift reionization process [3].However, the detailed evolution of the electron ionization fraction with redshift is currently unknown due to the difficulties in probing the reionization state of the Universe at higher redshifts through the Lyman-alpha opacity. The most promising observation in the near future is detection of the 21 cm transition of neutral hydrogen. The 21 cm emission is a direct probe of the large-scale distribution of neutral hydrogen during the epoch of reionization, and is,therefore,a complementary probe to the Lymanalpha emission at lower redshifts.According to current understanding of reionization sources,high energy photons may arise from the first star-forming galaxies and quasars.The uniqueness of these objects as the sources of photons to reionize the Universe is more challenging to establish.

High precision measurements of the cosmic microwave background (CMB） anisotropies provide new insights into the reionization history. There are two main effects of reionization on the CMB angular power spectra. The first effect produces a suppression of the acoustic peaks in the CMB angular power spectra through the optical depth integrated over the whole reionization history. Earlier reionization leads to the larger suppression of the acoustic peaks. The second effect changes the shape of the large-scale polarization angular power spectra.This gives a characteristic bump in the spectra on scales larger than the horizon size at reionization.The position of the bump is proportional to the square root of the redshift at which the reionization occurs,while the amplitude is proportional to the optical depth [4,5]. Therefore,measurements of the large-scale polarization angular power spectra can be used to constrain the reionization history [6,7].

Current constraint on the reionization optical depth from the Planck temperature data in combination with the low-multipole polarization data is $\tau = 0 . 0 7 8 \pm 0 . 0 1 9$ in the base ACDM model [8],which is smaller than $\tau =$ $0 . 0 8 9 \pm 0 . 0 1 4$ estimated by the WMAP 9-year data [9], but consistent with that from WMAP polarization measurements cleaned for dust emission using 353 GHz polarization maps from the high frequency instrument [10]. These results are based on the assumption of an instantaneous reionization. If such a simple assumption is not true, the estimated values of cosmological parameters are biased.Since there is currently no convincing model of the reionization history, it is important and necessary to constrain it in a relatively model-independent way.

Hu and Holder proposed a principal component analysis (PCA） of the reionization history to quantity the information contained in the large-scale $E$ -modepolarization [7]. The principal components are the eigenfunctions of the Fisher matrix that describes the dependence of the polarization angular power spectra on the reionization history.In practice,no more than the first five principal components are needed to parameterize the reionization history [11]. This approach has been applied to WMAP data and simulated future data [12-17]. It is recently claimed that the Harrison-Zel'dovich primordial spectrum is consistent with the WMAP 7-year data in such a general reionization scenario [18,19]. In this paper,we perform the principal component analysis of the reionization history from recently released Planck 2015 data and study the impact of the reionization history on the estimates of the cosmological parameters. We also investigate the bounds on the neutrino masses and primordial tensor perturbations in a general reionization scheme.

The paper is organized as follows. In Section 2 we describe the principal component method for parameterizing the reionization history that we will adapt in our analysis.The results are presented in Section 3. The last section is devoted to our conclusions.

# 2. MODEL

Since there is no convincing physical model of the reionization history, the instantaneous reionization history is usually assumed when investigating cosmological constraints from CMB measurements. Such a oneparameter phenomenological model may bias the estimates of the optical depth and other cosmological parameters. In general, the hydrogen ionization fraction $x _ { e } ( z )$ is a function of redshift.Binning the hydrogen ionization fraction in redshift bins is a good idea to parameterize the reionization history. However, the degeneracy betweenthebinned ionization fractionleadstoweak constraints [2O].The principal component analysis provides a solution to this problem [7].

The PCA approach is often adopted to reduce the number of variables while containing most of information of thesystem.It convertsa set of correlated variables into a set of linear uncorrelated variables by an orthogonal transformation.The principal components are the eigenvectors of the diagonalized matrix,which are picked out according to the corresponding eigenvalues.Intuitively, the larger the eigenvalue is,the more information the corresponding eigenvector gives.

Following [11],we parameterize the reionization history. Consider a binned ionization fraction $x _ { e } ( z _ { i } )$ ， $i \in$ $\{ 1 , 2 , \ldots , N _ { z } \}$ ，with redshift bins of width $\Delta z \ = \ 0 . 2 5$ spanning ²min ≤ z ≤ &max. The bin width of △z = 0.25 is sufficiently small so that the final results we obtain are independent of the redshift binning [11].Here we take $z _ { \mathrm { m i n } } ~ = ~ 6$ and $z _ { \mathrm { m a x } } ~ = ~ 3 0$ .With the definition $z _ { 1 } = z _ { \mathrm { m i n } } + \Delta z$ and $z _ { N _ { z } } = z _ { \operatorname* { m a x } } - \Delta z$ so that $N _ { z } + 1 =$ $( z _ { \mathrm { m a x } } - z _ { \mathrm { m i n } } ) / \Delta z$ .For $z \geq z _ { \mathrm { m a x } }$ ，the ionization fraction is set to the residual fraction of recombination,while $x _ { e } = 1 . 0$ for $3 \leq z \leq z _ { \operatorname* { m i n } }$ consistent with astrophysical observations [2] and $x _ { e } = 1 . 0 8$ for $z < 3$ when the Helium reionization is taken into account.The principal components of $x _ { e } ( z _ { i } )$ are the eigenfunctions of the following Fisher matrix Fij,

$$
F _ { i j } = \sum _ { \ell = 2 } ^ { \ell _ { \mathrm { m a x } } } \left( \ell + \frac { 1 } { 2 } \right) \frac { \partial \ln C _ { \ell } ^ { E E } } { \partial x _ { e } ( z _ { i } ) } \frac { \partial \ln C _ { \ell } ^ { E E } } { \partial x _ { e } ( z _ { j } ) } ,
$$

![](images/2baaac5b735806a74abfc9729179ebba26984dcba5de0c34b6f5f97459faba73.jpg)  
FIG.1: Fractional power spectrum response to a delta function perturbation of unit amplitude at $6 . 2 5 < z _ { i } < 2 9 . 7 5$ = Here we have chosen $\Delta z = 0 . 2 5$

which describes the dependence of the polarization spectrum $C _ { \ell } ^ { E E }$ on the ionization fraction $x _ { e } ( z _ { i } )$ . To calculate the Fisher matrix,we should set a fiducial reionization history $x _ { e } ^ { \mathrm { { f i d } } } ( z _ { i } )$ as well as other cosmological parameters. The fiducial model parameters are chosen as the estimated values of cosmological parameters from the Planck 2015 data including the temperature and polarization power spectra for the base $\Lambda$ CDM model [8],listed in Table I. We adopt $x _ { e } ^ { \mathrm { f i d } } ( z _ { i } ) = 0 . 1$ in the range of redshifts $6 \leq z \leq 3 0$ to get the same optical depth as the instantanous reionization.Actually our results are not sensitive to the fiducial model. Since the effect of $x _ { e } ( z _ { i } )$ on $C _ { \ell } ^ { E E }$ of can be neglected on high $\ell$ ，as shown in Fig.1,we can cut off $\ell$ safely to $\ell _ { \mathrm { m a x } } = 1 0 0$ in the Fisher matrix. The perturbation to the fiducial $x _ { e } ^ { \mathrm { f i d } }$ is a delta function correlated with the nearby region [7].

TABLE I:Fiducial model consistent with results from the 2015 Planck temperature and polarization spectra for the standard ACDM model.   

<html><body><table><tr><td>Ωh²</td><td>Ωch²</td><td>h</td><td></td><td>Ase-2T</td></tr><tr><td>0.02225 0.1198</td><td>0.6727</td><td>0.079</td><td>1.882 × 10</td><td>ns 0.9645</td></tr></table></body></html>

The Fisher matrix $F _ { i j }$ is decomposed as

$$
F _ { i j } = ( N _ { z } + 1 ) ^ { - 2 } \sum _ { \mu = 1 } ^ { N _ { z } } S _ { \mu } ( z _ { i } ) \sigma _ { \mu } ^ { - 2 } S _ { \mu } ( z _ { j } ) ,
$$

where $\sigma _ { \mu } ^ { 2 }$ are the inverse eigenvalues and $S _ { \mu } ( z )$ are the eigenfunctions that satisfy the orthogonality and completeness relations

$$
\begin{array} { r c l } { { } } & { { } } & { { \displaystyle \int _ { z _ { \operatorname* { m i n } } } ^ { z _ { \operatorname* { m a x } } } d z S _ { \mu } ( z ) S _ { \nu } ( z ) ~ = ~ ( z _ { \operatorname* { m a x } } - z _ { \operatorname* { m i n } } ) \delta _ { \mu \nu } , } } \\ { { } } & { { } } & { { \displaystyle \sum _ { \mu = 1 } ^ { N _ { z } } S _ { \mu } ( z _ { i } ) S _ { \mu } ( z _ { j } ) ~ = ~ ( N _ { z } + 1 ) \delta _ { i j } . } } \end{array}
$$

So these eigenfunctions form a set of orthogonal and com plete bases.An arbitrary reionization history can be de composed into a sum of the eigenmodes,

$$
x _ { e } ( z ) = x _ { e } ^ { \mathrm { f i d } } ( z ) + \sum _ { \mu } m _ { \mu } S _ { \mu } ( z ) ,
$$

where $m _ { \mu }$ are the amplitudes of the principal components for a particular reionization history. We order the eigenmodes so that the smallest $\sigma _ { \mu } ^ { 2 }$ has the lowest index number ，starting at $\mu = 1$ ．Since the effect of each eigenmode on $C _ { \ell } ^ { E E }$ becomes smaller as $\mu$ increases, we shall pick out the first few eigenmodes. It is enough to choose the first $3 - 5$ eigenmodes shown in Fig.2 because of the existence of the cosmic variance

$$
\frac { \Delta C _ { \ell } ^ { E E } } { C _ { \ell } ^ { E E } } = \sqrt { \frac { 2 } { 2 \ell + 1 } } ,
$$

So that the error in $C _ { \ell } ^ { E E }$ from high $\mu$ eigenmodes is smaller than the cosmic variace.

![](images/dba47e6a2e0f396ee587eda5189f30ded1c53bf8543558ff11cac2b6225b7e98.jpg)  
FIG.2: The five lowest-variance principal components of $x _ { e } ( z )$ over the redshift range of $6 . 2 5 < \mathrm { z } < 2 9 . 7 5$ .The variances increase with the index $\mu$ ：

In our analysis,we parameterize the reionizaton history as(5)with the five amplitudes $m _ { \mu }$ for $\mu = 1 , . . . , 5$ We consider a spatially-flat $\Lambda$ CDM model described by a set of cosmological parameters

$$
\{ \Omega _ { b } h ^ { 2 } , \Omega _ { c } h ^ { 2 } , \Theta _ { s } , A _ { s } , n _ { s } \} ,
$$

where $\Omega _ { b } h ^ { 2 }$ and $\Omega _ { c } h ^ { 2 }$ are the physical baryon and cold dark matter densities relative to the critical density, $\Theta _ { s }$ isthe ratio of the sound horizon to the angular diameter distance at decoupling, $A _ { s }$ is the amplitude of the primordial power spectrum of scalar perturbations and $n _ { s }$ is the scalar spectral index.Moreover,we consider two oneparameter extensions to the $\Lambda$ CDM model, ACDM $. + \Sigma m _ { \mu }$ and $\Lambda$ CDM $+ r$ ，where $\Sigma m _ { \mu }$ is the total mass of neutrinos and $r$ is the tensor-to-scalar ratio.When the tensor contribution to the CMB angular power spectra is considered, the inflationary consistency relation, $n _ { t } = - r / 8$ . is assumed where $n _ { t }$ is the tensor spectral index. For comparison with the Planck results, $r$ is defined at the pivot scale $k _ { * } = 0 . 0 0 2 ~ \mathrm { M p c ^ { - 1 } }$ (denoted $r _ { 0 . 0 0 2 }$ ）

We modified the Boltzmann CAMB code [21] to appropriately incorporate the PCA reionization history and used the publicly available CosmoMC package to explore the parameter space by means of Monte Carlo Markov chains technique [22].

In our analysis we use recently released Planck likelihood code and data,including the Planck low- $\it { l }$ likelihood at multipoles $2 \leq l \leq 2 9$ and high- $l$ Plik likelihood at multipoles $\textit { l } \geq 3 0$ based on pseudo $C _ { l }$ estimators. The former uses foreground-cleaned LFI 7O GHz polarization maps together with the temperature map obtained from the Planck 30 to 353 GHz channels by the Commander component separation algorithm over 94% of the sky. The polarization part of this likelihood is denoted as“lowP".The latter uses 100 GHz,143 GHz, and 217 GHz half-mission cross-power spectra, avoiding the Galactic plane as well as the brightest point sources and the regions where the CO emission is the strongest. “Planck TT+lowP”denotes the combination of the TT likelihood at $\iota \geq 3 0$ and a low- $\it { \Delta } l$ temperature-polarization likelihood.“Planck TT,TE,EE $^ +$ lowP”denotes the combination of the likelihood at $l \geq 3 0$ using TT, TE,and EE spectra and the low- $\it { l }$ temperature-polarization likelihood.

# 3. RESULTS

Table I summarizes the constraints on the reionization history and cosmological parameters from the Planck TT+lowPandPlanckTT,TE,EE $^ +$ lowPdata.Theresults from the temperature and polarization power spectra are consistent with those from Planck TT $^ +$ lowP, but with increased precision.Since temperature-topolarization leakage corrections are not considered in the 2015 Planck TE and EE power spectra [8], in our analysis Planck TT $^ +$ lowP is usually quoted. Actually the reionization history is not sensitive to the TE and EE power spectra at $\iota \geq 3 0$ ：

The mean posterior values and 68% confidence limits of $m _ { \mu }$ are listed in Table II. Compared to WMAP data, Planck data place strong constraints on the amplitudes of the principal components. The marginalized 2D contours and posterior probability distributions are plotted in Figure 7. As expected, the correlations between $\{ m _ { \mu } \}$ are weak and the probability distributions are Gaussian. Moreover,we reconstruct the reionization history from Monte Carlo chains using the PCA approach in Figure 3. The blue curve is the mean value of the hydrogen ionization fraction $x _ { e } ( z )$ in the redshift range $6 . 2 5 < z < 2 9 . 7 5$ 5 with $6 8 \%$ (dark color） and $9 5 \%$ （light color） confidence regions. As we can see the Universe is not completely reionized at $z \geq 8 . 5$ at 95% CL.This result is consistent with the estimated value of the reionization redshift $z _ { \mathrm { r e } } = 8 . 8 _ { - 1 . 4 } ^ { + 1 . 7 }$ derived from Planck TT+lowP+lensing in the instantaneous reionization model.

The constraint on the optical depth of the PCA reionization is $\tau = 0 . 0 9 2 { \pm } 0 . 0 1 7$ ,lager than that of the instantaneous reionization obtained in the 2O15 Planck analysis,but with nearly the same uncertainty [8]. The reason is that the ionization fraction at high redshift makes a larger contribution to the optical depth than at low redshift. The optical depth between any two redshifts $z _ { 1 }$ and $z _ { 2 }$ is an integration of $x _ { e }$ ，

TABLE II: $6 8 \%$ constraints on the PCA reionization and other cosmological parameters from 2015 Planck CMB angular power spectra.For the total mass of neutrinos and tensor-to-scalar ratio, the $9 5 \%$ upper limits are given.   

<html><body><table><tr><td rowspan="2">Parameters</td><td>ACDM</td><td>ACDM</td><td>ACDM+r</td><td>ACDM+Σmv</td></tr><tr><td>Planck TT+lowP</td><td>Planck TT,TE,EE+lowP</td><td>Planck TT+lowP</td><td>Planck TT+lowP</td></tr><tr><td>2h2</td><td>0.02223 ±0.00023</td><td>0.02224 ± 0.00016</td><td>0.02225 ±0.00023</td><td>0.02210 ±0.00030</td></tr><tr><td>Ωch²</td><td>0.1192±0.0021</td><td>0.1196 ± 0.0015</td><td>0.1190 ± 0.0021</td><td>0.1201 ± 0.0024</td></tr><tr><td>1000MC</td><td>1.04092±0.00047</td><td>1.04079 ± 0.00032</td><td>1.04095 ± 0.00047</td><td>1.04066 ± 0.00056</td></tr><tr><td>T</td><td>0.092±0.017</td><td>0.092 ± 0.015</td><td>0.092 ± 0.017</td><td>0.095 ±0.017</td></tr><tr><td>ns</td><td>0.9689±0.0064</td><td>0.9663 ± 0.0049</td><td>0.9698 ± 0.0064</td><td>0.9662 ± 0.0075</td></tr><tr><td>ln(1010 As)</td><td>3.115±0.033</td><td>3.117 ±0.030</td><td>3.115 ± 0.032</td><td>3.121 ± 0.034</td></tr><tr><td>Ho (km s-1 Mpc-1)</td><td>67.54±0.96</td><td>67.34 ± 0.65</td><td>67.64 ±0.96</td><td>64.85 ±3.34</td></tr><tr><td>8</td><td>0.838 ±0.014</td><td>0.840 ±0.012</td><td>0.839 ± 0.014</td><td>0.788 ±0.063</td></tr><tr><td>Ωm</td><td>0.3116 ±0.0132</td><td>0.3144 ± 0.0091</td><td>0.3104 ± 0.0131</td><td>0.3507 ± 0.0525</td></tr><tr><td>r0.002</td><td>1</td><td>1</td><td><0.091</td><td>1</td></tr><tr><td>∑mv (eV)</td><td>1</td><td>1</td><td>1</td><td><1.03</td></tr><tr><td>m1</td><td>-0.0534 0.0569±0.0625</td><td>-0.0510 0.0485±0.0590</td><td>-0.0523 0.0528±0.0608</td><td>-0.0563 0.0663±0.0712</td></tr><tr><td>m2</td><td>-0.1091 -0.0457±0.1193</td><td>-0.1065 -0.0689±0.1073</td><td>-0.1076 -0.0543+0.1198</td><td>-0.1096 -0.0536±0.1300</td></tr><tr><td>m3</td><td>-0.1440 0.0498±0.1450</td><td>-0.1489 0.0409±0.1338</td><td>-0.1340 0.0586±0.1381</td><td>-0.1613 0.0642±0.1465</td></tr><tr><td>m4</td><td>-0.1500 -0.010±0.1503</td><td>-0.1398 -0.0190±0.1499</td><td>-0.1427 -0.0127+0.1435</td><td>-0.1547 -0.0102±0.1549</td></tr><tr><td>m5</td><td>-0.1570 0.0524+0.1566</td><td>-0.1448 0.0406+0.1460</td><td>-0.1549 0.0519±0.1551</td><td>-0.1689 0.0560±0.1688</td></tr></table></body></html>

$$
\tau ( z _ { 1 } , z _ { 2 } ) = 0 . 0 6 9 1 ( 1 - Y _ { p } ) \Omega _ { b } h \int _ { z _ { 1 } } ^ { z _ { 2 } } d z \frac { ( 1 + z ) ^ { 2 } } { H ( z ) / H _ { 0 } } x _ { e } ( z ) ,
$$

where $Y _ { p }$ is the helium abundance.Since the Hubble parameter $H$ falls off as $( 1 + z ) ^ { 3 / 2 }$ in the matter domination epoch,the same $x _ { e }$ can contribute more to the optical depth at higher redshift.It is known that the amplitude of primordial spectrum of scalar perturbations $A _ { s }$ degenerates with optical depth $\tau$ in the form $A _ { s } e ^ { - 2 \tau }$ on small scale [1O],which means that a large $\tau$ leads to a large $A _ { s }$ .Hence a higher value of the matter fluctuation amplitude, $\sigma _ { 8 } = 0 . 8 3 8 \pm 0 . 0 1 4$ ,is favored in the PCA reionization than in the instantaneous reionization,as shown in the left panel of Figure 4. This means that such a general reionization history strengthens the tension between Planck CMBobservations and some astrophysical data,such as cluster counts and weak lensing. As shown in the right panel of Figure 4,this tension can significantly be relieved if the neutrino masses are allowed to vary,thanks to the degeneracy between the reionization history and the neutrino masses. Larger neutrino masses lead to a lower $\sigma _ { 8 }$ through the effects of neutrino free streaming on structure formation.The constraint on the total mass of neutrinos can be relaxed to $\Sigma m _ { \mu } < 1 . 0 3$ eV at 95% CL in the PCA reionization scenario. In Figure 5 we also show the correlation of the neutrino masses with the Hubble constant. The constraint has a broad tail to high masses,which illustrates the acoustic scale degeneracy with $\textstyle H _ { 0 }$ ：

![](images/7cf43725a5970a47651a5526650440055ebdd82851d2a16525982eb21926fca2.jpg)  
FIG.3: Reconstructed reionization history with the PCA method from PlanckTT $+$ lowP.The blue curve is the mean value of the hydrogen ionization fraction $x _ { e } ( z )$ in the redshift range $6 . 2 5 < z < 2 9 . 7 5$ ，with $6 8 \%$ (dark color） and $9 5 \%$ (light color） confidence regions.

It is claimed in [18] that the Harrison-Zel'dovich primordial spectrum (i.e.， scale-invariant spectrum） of scalar perturbations is consistent with the WMAP 7-year data in the PCA reionization scenario. However，our analysis indicates that the Harrison-Zel'dovich spectrum is disfavored by Planck TT+lowP at 4.9 $\sigma$ CL,although the scalar spectral index is shifted towards slightly higher values. To test inflationary models the contribution of primordial tensor fluctuations to the CMB angular power spectra is taken into account.Figure 6 depicts the marginalized 2D contour in the $r _ { 0 . 0 0 2 } - n _ { s }$ plane,with $6 8 \%$ and $9 5 \%$ CL,for the PCA(blue) and instantaneous (red) reionization history,derived fromPlanck TT $^ +$ lowP. We find that the allowed contour is shifted towards to higher values of $n _ { s }$ , compared to the instantaneous reionization.This shift is important for the constraints on inflationary models. For example,it is pointed out in [23] that the class of inflationary models with a power-law po tential $\phi ^ { p }$ for $p \ll 1$ and the low-scale spontaneously broken SUSY inflationary model are marginally disfavored byPlanck data at 95% CL.In the PCA reionization scenario,however,these models are in agreement with recent CMB observations.Moreover，the constraints on the tensor-to-scalar ratio is tighter compared to the instantaneous reionization because the large amplitude of scalar spectrum suppresses the tensor-to-scalar ratio.

![](images/a845917f803d885574871818a9bf59a1e43b58114829902e9c2596299b5e4823.jpg)  
FIG. 4: Marginalized 2D contours in the $\sigma _ { 8 } \mathrm { ~ - ~ } \Omega _ { m }$ plane，with $6 8 \%$ and 95% CL, for the ACDM model (left panel) and $\Lambda { \mathrm { C D M } } + \Sigma m _ { \nu }$ (right panel) with the PCA (blue)and instantaneous (red) reionization history,derived from Planck $\mathrm { T T } + \mathrm { \cdot }$ lowP.

![](images/f136230ae3b6d2eaafc31c25bb0812239a86ed467510100302572fd315b6bd3a.jpg)  
FIG.5:Marginalized 2D contour in the $H _ { 0 } - \Sigma m _ { \nu }$ plane,with $6 8 \%$ and $9 5 \%$ CL,for the $\Lambda _ { \mathrm { C D M + } \Sigma m _ { \nu } }$ model with the PCA (blue）and instantaneous (red） reionization history,derived from Planck TT+lowP.

![](images/7983550ce352f11d8414f697bc14420395ec35afd45214a064b453fdcb41da83.jpg)  
FIG.6:Marginalized 2D contour in the $r _ { 0 . 0 0 2 } - n _ { s }$ plane,with $6 8 \%$ and $9 5 \%$ CL，for the $\Lambda { \mathrm { C D M } } + r$ model with the PCA (blue）and instantaneous (red） reionization history,derived from Planck TT+lowP.

# 4. CONCLUSIONS

Wehaveconsideredtheprincipalcomponent parametrization of the reionization history and studied the effects of the PCA reionization on the estimates of cosmological parameters using recently released Planck data. From the reconstructed reionization history we found that the Universe is not completely reionized at $z \geq 8 . 5$ at $9 5 \%$ CL.This conclusion can be tested by future astrophysical experiments such as SKA.The reionization optical depth is higher than but consistent with that obtained in the instantaneous reionization scheme.The higher value of $\tau$ leads to the higher value of $A _ { s }$ ,hence the higher $\sigma _ { 8 }$ ，which strengthens the

0.15 ·   
0.00   
² −0.15   
−0.30   
-0.45   
0.4 N   
0.2 O   
2   
0.0   
−0.2   
：。   
0.00 000。   
−0.15 0.00 0.15 0.30 m1 m2 m4 $m _ { 5 }$

tension between Planck CMB observations and some astrophysical data， such as cluster counts and weak lensing. But the tension can significantly be relieved if the neutrino masses are allowed to vary. The constraint on the total mass of neutrinos from CMB data is relaxed due to the degeneracy with the reionization history. Thanks to the shift of the scalar spectral index to higher values in the PCA approach, the low-scale spontaneously broken SUSY inflationary model,which is marginally disfavored at $9 5 \%$ confidence level in the Planck analysis, can fit the data well.

tion Center of Chinese Academy of Sciences. ZKG is supported by the National Natural Science Foundation of China under Grant No.11175225 and No.11335012. RGC is supported by the Strategic Priority Research Program of the Chinese Academy of Sciences,Grant No.XDB09000000.We used CosmoMC and CAMB.We also acknowledge the use of Planck data.

# Acknowledgments

Our numerical analysis was performed on the “Era" of Supercomputing Center, Computer Network Informa

[1]J.E.Gunn and B.A.Peterson,Astrophys.J.142,1633 (1965).   
[2]X. H. Fan et al.， Astron.J. 132， 117 (2006) [astro-ph/0512082].   
[3] T.R.Choudhury，E.Puchwein，M.G.Haehnelt and J. S.Bolton,arXiv:1412.4790 [astro-ph.CO].   
[4] M. Zaldarriaga， Phys. Rev. D 55, 1822 (1997) [astro-ph/9608050].   
[5] W.Hu and M.J.White,Astrophys.J. 479,568 (1997) [astro-ph/9609079].   
[6] M.Kaplinghat， M.Chu，Z.Haiman，G.Holder, L.Knox and C. Skordis，Astrophys.J. 583,24(2003) [astro-ph/0207591].   
[7] W.Hu and G.P.Holder,Phys.Rev.D 68,023001 (2003) [astro-ph/0303400].   
[8] P.A. R.Adeetal.[PlanckCollaboration], arXiv:1502.01589 [astro-ph.CO].   
[9] C.L.Bennett et al.[WMAP Collaboration]，Astrophys. J. Suppl.208,20 (2013) [arXiv:1212.5225 [astro-ph.CO]].   
[10] P.A.R.Ade et al. [Planck Collaboration],Astron.Astrophys.571,A16(2014) [arXiv:1303.5076 [astr0-ph.CO]].   
[11]M.J. Mortonson and W.Hu，Astrophys.J.672，737 (2008)[arXiv:0705.1132 [astro-ph]].   
[12]M.J.Mortonson and W.Hu,Phys.Rev.D 77,043506 (2008)[arXiv:0710.4162 [astro-ph]].   
[13] L.P.L.Colombo and E.Pierpaoli,New Astron.14,269 (2009）[arXiv:0804.0278 [astro-ph]].   
[14] M.J.Mortonson and W.Hu,Astrophys.J.686，L53 (2008) [arXiv:0804.2631 [astro-ph]].   
[15] M.J.Mortonson,C.Dvorkin,H.V.Peiris and W.Hu, Phys.Rev.D 79,103519(2009) [arXiv:0903.4920 [astroph.CO]].   
[16] M.Archidiacono,A.Cooray,A.Melchiorri and S.Pandolfi，Phys.Rev.D 82,087302(2010) [arXiv:1010.5757 [astro-ph.CO]].   
[17]S.Pandolfi，A.Ferrara，T.R.Choudhury，A.Melchiorri and S. Mitra,Phys.Rev.D 84,123522 (2011) [arXiv:1111.3570 [astro-ph.CO]].   
[18]S.Pandolfi,A.Cooray,E.Giusarma,E.W.Kolb,A.Melchiorri,O.Mena and P.Serra,Phys.Rev.D81,123509 (2010）[arXiv:1003.4763 [astro-ph.CO]].   
[19] S. Pandolfi et al.，Phys. Rev.D 82，123527 (2010) [arXiv:1009.5433 [astr0-ph.CO]].   
[20]A.Lewis,J.Weller and R.Battye,Mon.Not.Roy. Astron.Soc.373,561 (2006) [astro-ph/0606552].   
[21]A.Lewis,A.Challinor and A.Lasenby，Astrophys.J. 538,473(2000)[astro-ph/9911177].   
[22] A.Lewis and S.Bridle,Phys.Rev.D 66,103511 (2002) [astro-ph/0205436].   
[23]P.A. R.Adeet al.[Planck Collaboration], arXiv:1502.02114 [astro-ph.CO].