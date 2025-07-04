# Reconstruction of the primordial power spectra with Planck and BICEP2

Bin Hu $^ { 1 }$ ，Jian-Wei Hu $^ 2$ ， Zong-Kuan Guo $^ 2$ ，Rong-Gen Cai $^ 2$ ￥ $^ 1$ Institute Lorentz of Theoretical Physics， University of Leiden， 2333CA Leiden， The Netherlands （204号 $^ 2$ State Key Laboratory of Theoretical Physics， Institute of Theoretical Physics, Chinese Academy of Sciences，P.O.Box 2735，Beijing 100190，China

By using the cubic spline interpolation method,we reconstruct the shape of the primordial scalar and tensor power spectra from the recently released Planck temperature and BICEP2 polarization cosmic microwave background data.We find that the vanishing scalar index running $( \mathrm { d } n _ { s } / \mathrm { d } \ln k )$ （20 model is strongly disfavored at more than $3 \sigma$ confidence level on the $k = \mathrm { 0 . 0 0 0 2 \ M p c ^ { - 1 } }$ scale. Furthermore,the power-law parameterization gives a blue-tilt tensor spectrum,no matter using only the first 5 bandpowers $n _ { t } = 1 . 2 0 _ { - 0 . 6 4 } ^ { + 0 . 5 6 }$ （95%CL)orthefull9bandpowers $n _ { t } = 1 . 2 4 _ { - 0 . 5 8 } ^ { + 0 . 5 1 }$ (95%CL) of BICEP2 data sets.Unlike the large tensor-to-scalar ratio value ( $r \sim 0 . 2 0$ ）under the scale-invariant tensor spectrum assumption,our interpolation approach gives $r _ { 0 . 0 0 2 } < 0 . 0 6 0$ （95%CL）by using the first 5 bandpowers of BICEP2 data. After comparing the results with/without BICEP2 data, we find that Planck temperature with small tensor amplitude signals and BICEP2 polarization data with large tensor amplitude signals dominate the tensor spectrum reconstruction on the large and small scales,respectively. Hence,the resulting blue tensor tilt actually reflects the tension betwen Planck andBICEP2data.

PACS numbers:

# I. INTRODUCTION

Recently BICEP2 experiment [1] reported an excess of Cosmic Microwave Background(CMB）B-mode polarization power spectrum over the base lensed- $\Lambda$ CDM expectation in the range $3 0 < \ell < 1 5 0$ ,inconsistent with the null hypothesis at a significance of $> 5 \sigma$ .Since the single field slow-roll inflationary model predicts a peak around multipole $\ell \sim 8 0$ in the B-mode auto-correlation (BB)spectrum seeded by the primordial gravitational wave/tensor perturbation mode, the BICEP2 results are believed as the first indirect detection of the primordial gravitational wave.Under the assumption of power-law scalar and scale-invariant tensor spectra,，the observed B-mode power spectrum is well-described by a lensed$\Lambda$ CDM+tensor theoretical model with tensor-to-scalar ratio $r = 0 . 2 0 _ { - 0 . 0 5 } ^ { + 0 . 0 7 }$ with $r \ = \ 0$ disfavored at $7 . 0 \sigma$ confidence level.

However, the scientific results of BICEP2 data are in tension with those from other CMB experiments,such as Planck [2]. The first discrepancy is in the amplitude of the scale-invariant tensor spectrum,which is described by the tensor-to-scalar ratio $r \equiv A _ { t } / A _ { s }$ . Unlike the scalar perturbatoins,due to the absence of acoustic oscillation mechanism the tensor contributions to the temperature CMB spectrum are rapidly washed out inside the horizon at electron-proton recombination epoch ( $\ell \geq 2 0 0$ ）） [3].Hence,the temperature anisotropies on the large scales are the mixture of scalar and tensor contributions. Furthermore,if one assumes the simple power-law form of the primordial scalar power spectrum, i.e.,no scalar index running $\mathrm { d } n _ { s } / \mathrm { d } \ln k = 0$ ，the precisely measured higher multipoles by Planck put stringent constraints on the scalar amplitude $A _ { s }$ and index $n _ { s }$ . Therefore, in order to explain the observed power deficit in the low- $\ell$ regime by Planck, one has to suppress the tensor spectrum amplitude.Consequently, from only the temperature anisotropy measured by Planck,one has $r ~ < ~ 0 . 1 1$ at $9 5 \%$ ，which is in a“very significant” tension (around $0 . 1 \%$ unlikely）with BICEP2 results [4]. As stressed by the BICEP2 team，however,this tension could be reconciledby adding the running of the scalar index which is the degree of freedom to suppress the scalar temperature anisotropy in low- $\ell$ regime.Then,combiningPlanck withWMAP low- $\ell$ polarization [5]and ACT [6] /SPT[7- 9high- $\ell$ data,one could get $r < 0 . 2 6$ at $9 5 \%$ ．Besides that,several other possible solutions to this tension have been proposed, such as step feature spectra [1O-12], fastslow roll model [13],anti-correlation scalar iso-curvature initial condition [14,15],sterile neutrino species [16-18], sudden change in speed of inflaton or Lorentz violation [19].And see also [2O-25] for other possibilities.

The second tension is between the observed blue-tilt tensor spectrum ( $n _ { t } ~ > ~ 0$ ）[26-30]by BICEP2 and the red-tilt one ( $n _ { t } = - r / 8$ )predicted by the standard inflationary paradigm.Generally,the blue tensor spectrum asks for violation of Null Energy Condition (NEC),which is equivalent to $\rho + P < 0$ (or $\dot { H } > 0$ )in the flat universe. There exist several NEC violation inflationary models in the literature,such as super-inflation [31],phantom inflation [32],G-inflation [33] etc. Some alternative paradigm of infation,such as “string gas cosmology” [34],bouncing universe [35-41] or other possibilities [42,43] (see the references therein) might be helpful to solve this tension.

In this paper,we start from a purely phenomenological point of view to reconstruct the shape of primordial scalar and tensor spectra from Planck temperature and BICEP2

polarization data.

# II. PARAMETERIZATIONOFPRIMORDIAL SPECTRA ANDDATASETS

In order to reconstruct a smooth spectrum with the continuous first and second derivatives，in this paper we adopt the cubic spline interpolation method,which has been used to analyze WMAP or Planck temperature and polarization data [44-51]. Beside the cubic spline interpolation reconstruction,there also exist other model independent algorithms,such as Bayesian evidence selected linear interpolation，[52，53] etc. Due to the fact that the amplitude of CMB anisotropy is so tiny, $\delta T / T \sim \mathcal { O } ( 1 0 ^ { - 5 } )$ ,and CMB observational windows cover several orders of magnitudein spatial scale,it is reasonable to parameterize the logarithms of primordial spectra,which seed the CMB anisotropy,in the logarithms of fluctuation wavenumber, $\ln { k }$ ．The method of cubic spline interpolation can be summarized as follows.

First,we uniformly sample $N _ { \mathrm { b i n } }$ points in the logarithmic scale of wavenumber.Second, inside of the sampled bins $\ln k _ { i } < \ln k < \ln k _ { i + 1 }$ ，we use the cubic spline interpolation to determine logarithmic values of the primordial power spectrum. Third, the boundary conditions are adopted,where the second derivative is set to zero. For $\textit { k } < \textit { k } _ { 1 }$ or $k \ > \ k _ { N _ { \mathrm { b i n } } }$ we fix the slope of the primordial power spectrum at the boundaries and linearly extrapolate to the outside regimes.Mathematically, the corresponding formula could be written as

$$
\begin{array} { r } { \ln \mathcal { P } ( k ) = \left\{ \begin{array} { l l } { \frac { \mathrm { d } \ln \mathcal { P } ( k ) } { \mathrm { d } \ln k } \Big | _ { k _ { 1 } } \ln \frac { k } { k _ { 1 } } + \ln \mathcal { P } ( k _ { 1 } ) , } & { k < k _ { 1 } ; } \\ { \ln \mathcal { P } ( k _ { i } ) , } & { k \in \{ k _ { i } \} ; } \\ { \mathrm { c u b i c ~ s p l i n e } , } & { k _ { i } < k < k _ { i + 1 } ; } \\ { \frac { \mathrm { d } \ln \mathcal { P } ( k ) } { \mathrm { d } \ln k } \Big | _ { k _ { N _ { \mathrm { b i n } } } } \ln \frac { k } { k _ { N _ { \mathrm { b i n } } } } + \ln \mathcal { P } ( k _ { N _ { \mathrm { b i n } } } ) , \ k > k _ { N _ { \mathrm { b i n } } } . } \end{array} \right. } \end{array}
$$

This reconstruction method has three advantages: first of all, it is easy to detect deviations from a scale-invariant ora power-law spectrum because both the scale-invariant and power-law spectra are just straight lines in the $\ln k$ ， $\ln \mathcal { P }$ plane. Second, negative values of the spectrum can be avoided by using $\ln \mathcal { P } ( k )$ instead of $\mathcal { P } ( k )$ for splines with steep slopes.Finally, the shape of the power spectrum reduces to the scale-invariant or power-law spectrum as a special case when $N _ { \mathrm { b i n } } = 1 , 2$ ， respectively.

Since the purpose of this work is to reconstruct the scalar and tensor spectra,we need to adopt different sampling logarithms based on the different observational windows.For the primordial scalar curvature spectrum，its constraints are mainly driven by the CMB temperature modes.With Planck sensitivities,we uniformly sample 3 bins ranged in $\ln { k } \in ( - 8 . 5 1 7 , - 1 . 6 0 9 )$ which corresponds to $k \in ( 0 . 0 0 0 2 , 0 . 2 ) ~ \mathrm { M p c ^ { - 1 } }$ .For the tensor spectrum，we adopt two uniformly logarithmic sampling strategies,one is corresponding to the scales $k \in ( 0 . 0 0 2 , 0 . 0 3 ) ~ \mathrm { M p c ^ { - 1 } }$ ，the other is $k \in ( 0 . 0 0 2 , 0 . 0 2 )$ （204号 $\mathrm { M p c ^ { - 1 } }$ . This is because the BICEP2 B-mode polarization data,which is a very sensitive probe for the primordial tensor spectrum,have an excess of B-mode power in all the range of polar angle mulitpoles ( $2 0 \leq \ell \leq 3 4 0$ ） And moreover,compared with the first 5 bandpowers, which is in the range of ( $2 0 \leq \ell \leq 2 0 0$ ),the power in the second 4 bandpowers has extraordinary excess over the base lensed- $\Lambda$ CDM expectation. This extraordinary excess might arise from exotic physical origin beyond standard inflationary paradigm or from some unresolved foreground contaminations.Given this consideration,in this work we take two different choices of BICEP2 data,the first is using the full 9 bandpowers,and the second is to use the selected first 5 bandpowers.Hence,we have to adjust our sampling logarithms as mentioned above.

In the left part of this section,we would like to briefly review the data sets we used.First of all,we utilize the Planck TT power spectra,namely, for low- $\ell$ modes ( $2 ~ \leq ~ \ell ~ < ~ 5 0$ ）via all the 9 frequency channels ranged from $3 0 \sim 3 5 3$ GHz,for high- $\ell$ modes ( $5 0 \leq \ell \leq 2 5 0 0$ ） through 100,143,and 217 GHz frequency channels 1 [55]. Second, in order to break the well-known parameter degeneracy between the re-ionization optical depth and the amplitude of CMB temperature anisotropy,we also include WMAP9 low- $\ell$ temperature/polarization spectra （ $2 ~ \le ~ \ell ~ \le ~ 3 2$ ）[5]．In addition，we use BICEP2 polarization (EE,EB,BB) spectra from 9 (or 5) bandpowers of multipoles in ( $2 0 \leq \ell \leq 3 4 0$ or 200）of 150 GHz channels [1] ². For the data analysis numerical package,we compute the CMB angular power spectra by using the public Einstein-Boltzmann solver CAMB [56] and explore the cosmological parameter space with a Markov Chain Monte Carlo sampler, namely CosmoMC [57].

<html><body><table><tr><td>Parameter</td><td>Range (min,max)</td></tr><tr><td>ln(101° A) ns</td><td>(2.7, 4.0) (0.9, 1.1)</td></tr><tr><td>dns/d ln k r0.05 nt</td><td>(-1.0, 1.0) (0.0,2.0) (-1.0, 5.0)</td></tr><tr><td>ln(101°Ai) ln(101° A2)</td><td>(1.0, 5.0) (1.0, 5.0)</td></tr><tr><td>ln(1010 A3)</td><td>(1.0, 5.0) ln(1010 B1)*(-3.0,3.0) /(-3.0,3.0)</td></tr><tr><td>ln(101° B2)* ln(1010B3)*</td><td>(-2.0,5.0)/(-3.0,3.0) (-1.0,5.0) /(-3.0,3.0)</td></tr></table></body></html>

TABLE I:List of the primordial spectrum parameters used in the Monte Carlo sampling.\*The left parameter ranges are for the chains from Planck+WP $+$ BICEP2 data compilation, and the right one are for those without BICEP2 data.

# III. RESULTS AND DISCUSSIONS

![](images/ab9a3f143ae2f36a0a06c375f0b492daf8ce7a137251c18f54613dfb28c8313d.jpg)  
FIG.1:Reconstruction of primordial scalar spectrum without BICEP2 data.

In this section we will start with the scalar spectrum reconstruction,and then turn to the tensor spectrum case. The prior ranges of the primordial spectrum parameters we studied are listed in Tab.I. Here we emphasize that the differences in the prior of tensor spectra amplitude at our cubic spline sampling knots when BICEP2 data are included,lie in the tension between Planck and BICEP2 data (we will show later).When our MCMC sampler investigates the wide parameter space spanned by $( \ln B _ { 1 } , \ln B _ { 2 } , \ln B _ { 3 } )$ ,at some points the resulting spectra are inconsistent with Planck TE cross-correlation data, in order to avoid this problem we have to adjust the prior ranges.But still the width of the priors are large enough and also the tensor amplitudes $( \ln B _ { 1 } , \ln B _ { 2 } , \ln B _ { 3 } )$ get well constrained in these prior ranges as shown in Fig.9. So,we conclude that our prior choices will not affect the results significantly.

# A． Scalar spectrum reconstruction

Since the main capability of scalar spectrum reconstruction is driven by the CMB temperature data,we firstly study the case without BICEP2 polarization,i.e. only with Planck temperature and WMAP9 low- $\ell$ polarization(WP） data sets. As mentioned in the previous section，here we uniformly sample 3 points in the logarithmic scale of wavenumber,which are located at $k _ { 1 } = 0 . 0 0 0 2$ ， $k _ { 2 } = 0 . 0 0 6 3$ and $k _ { 3 } = 0 . 2 ~ \mathrm { M p c ^ { - 1 } }$ with the logarithmic amplitudes $\ln A _ { 1 } , \ln A _ { 2 }$ and $\ln A _ { 3 }$ ，respectively.And then,we sample the parameter space spanned by vanilla $\Lambda$ CDM parameters without the scalar amplitude $\ln A _ { s }$ and its index tilt $n _ { s }$ and replacing them with $\ln A _ { 1 }$ ， $\ln A _ { 2 }$ and $\ln A _ { 3 }$ ，hereafter we call this parameter compilation as $\Lambda$ CD $\scriptstyle { \mathrm { M - l n } } A _ { s } - n _ { s } + \ln A _ { 1 } + \ln A _ { 2 } + \ln A _ { 3 }$

from Planck+WP data is represented by the black solid curve in Fig.1 and the corresponding $1 ~ \sim ~ 3 \sigma$ error bars at the sampling points are denoted by the blue,red and green segments,respectively.For comparison，we also show the primordial scalar spectrum from the Planck marginalized mean vanilla $\Lambda$ CDM and N $\mathrm { \Delta } \mathrm { \Omega } \mathrm { i } \mathrm { C D M } + \mathrm { d } n _ { s } / \mathrm { d } \ln k$ (scalar index running) with blue dashed and red dotted-dashed curves.From Fig.1, we can see that，first，our cubic spline interpolation result mimics the $\Lambda { \mathrm { C D M + d } n _ { s } } / { \mathrm { d } \ln k }$ case；second,on $k = \mathrm { 0 . 0 0 0 2 \ M p c ^ { - 1 } }$ scale, the simplest vanilla model is disfavored at nearly $2 \sigma$ level.

![](images/6fe656395dd2f29556a1d56370475e76b8d5725c0dbef24e5b7e07cf4553a69e.jpg)  
FIG.2: Reconstruction of primordial scalar spectrum with BICEP2 data.

The marginalized mean scalar spectrum reconstructed

Adding the BICEP2 polarization data，we show the results in Fig.2 for models including the tensor-to-scalar ratio $r$ ,i.e. $\Lambda$ CDM- $\ln A _ { s }$ ${ } _ { s } - n _ { s } + r + \ln A _ { 1 } + \ln A _ { 2 } + \ln A _ { 3 }$ .We find that,first of all,due to the anti-correlation between scalar and tensor amplitudes (see the bottom left subpanel of Fig.8 in Appendix A), the large value of tensorto-scalar ratio discovered by BICEP2 data will lead to the suppression of scalar amplitude on the large scales. This is also explicitly demonstrated in the top sub-panel of Fig.8 in Appendix A.As a result of deficit of scalar power on the large scales,as shown in Fig.2 the vanilla $\Lambda$ CDM model (blue curve） is strongly disfavored with $> 3 \sigma$ confidence level on the $k = \mathrm { 0 . 0 0 0 2 \ M p c ^ { - 1 } }$ scale. A similar result is obtained by authors of [51].By using Planck and BICEP2 data,they found a distinct preference for a suppression of power in the scalar spectrum at large scales, $k \leq 1 0 ^ { - 3 } \ \mathrm { M p c ^ { - 1 } }$ via a linear spline reconstruction method.Second,by assuming the scale invariant tensor spectrum,our scalar spectrum cubic spline interpolation parameterization still givesa large tensorto-scalar ratio $r = 0 . 2 1 _ { - 0 . 0 9 } ^ { + 0 . 1 0 }$ at 95%C.L., see Tab. II in Appendix A.

# B.Tensor spectrum reconstruction

In the previous subsection,we have assumed the tensor spectrum is scale-invariant.In this subsection we relax the assumption and use the same cubic spline interpolation method to reconstruct the shape of tensor spectrum. Unlike the CMB temperature spectrum which is mainly sourced by the primordial scalar perturbations, the B-mode polarization anisotropy seeded by tensor perturbation is only detected by BICEP2 on the large scales with the polar spherical harmonic mulitpoles ranged $2 0 \leq \ell \leq 3 4 0$ (9 bandpowers).As the case for the scalar spectrum,here the tensor spectrum is also uniformly sampled with 3 points in the logarithmic scale of wavenumber，but only on the scales covered by BICEP2 observations. Consequently，we sample them at $k _ { 1 } = 0 . 0 0 2$ ， $k _ { 2 } = 0 . 0 0 7 7$ and $k _ { 3 } = 0 . 0 3 ~ \mathrm { M p c ^ { - 1 } }$ ， respectively.The cosmological parameters we estimated are the 6 vanilla $\Lambda$ CDM model parameters plus the extra 3 tensor amplitudes $\ln B _ { 1 }$ ， $\ln B _ { 2 }$ and $\ln B _ { 3 }$ ：

![](images/0a03f868d422d74f4722eec125bdb1bea2ecd3531591ca97dc0562c7b782d815.jpg)  
FIG.3: Reconstruction of primordial tensor spectrum with BICEP2 data (9 bandpowers).

In Fig.3 we plot the primordial tensor spectra from the best-fit model of $\Lambda { \mathrm { C D M + l n } } B _ { 1 } + \ln B _ { 2 } + \ln B _ { 3 }$ (black solid curve)and $\Lambda$ CDM+ $r + n _ { t }$ (red dotted-dashed curve) as well as the error bars at the sampling points of the cubic spline interpolation method. First of all,both the standard power-law and our cubic spline parameterizations favor a blue-tilt tensor spectrum. The former (see Tab.III in AppendixB）reports

$$
\begin{array} { r } { r _ { 0 . 0 0 2 } \ < \ 0 . 0 6 1 , 9 5 \% \mathrm { C L } , ( 9 \ \mathrm { b a n d p o w e r s } ) , \ } \\ { n _ { t } \ = \ 1 . 2 4 _ { - 0 . 5 8 } ^ { + 0 . 5 1 } , 9 5 \% \mathrm { C L } , ( 9 \ \mathrm { b a n d p o w e r s } ) , } \end{array}
$$

and our cubic spline interpolation method gives

$$
r _ { 0 . 0 0 2 } < 0 . 0 6 4 , 9 5 \% \mathrm { C L } , ( 9 \mathrm { b a n d p o w e r s } ) .
$$

Second,we notice that in our cubic spline interpolation method the slope of the tensor spectrum becomes larger in the low- $k$ regime,but still is consistent with the powerlaw parameterization in $2 \sigma$ confidence level.

As we argued in the previous section, there exists an extraordinary power excess in the higher wavenumber regimes of BICEP2 data.Given this consideration，in what follows we only adopt the selected first 5 bandpower data of BICEP2 for our reconstruction. Based on the multipole ranges covered by these powerbands 1 $2 0 ~ \leq ~ \ell ~ \leq ~ 2 0 0 )$ ，we sample points at $k _ { 1 } ~ = ~ 0 . 0 0 2$ 5 $k _ { 2 } = 0 . 0 0 6 3$ and $k _ { 3 } = 0 . 0 2 \ \mathrm { M p c ^ { - 1 } }$ , respectively.

![](images/279c746ae657d806c17999f41c668cac7965b70d01038cb6b6088576c32b1eea.jpg)  
FIG.4: Reconstruction of primordial tensor spectrum with BICEP2 data (5 bandpowers).

The reconstructed tensor spectra as well as error bars are shown in Fig.4. First, from the power-law parameterization,we can see that the blue tensor spectra are still favored but with the tilt becomes smaller as expected

$$
\begin{array} { r } { r _ { 0 . 0 0 2 } \ < \ 0 . 0 6 7 , 9 5 \% \mathrm { C L } , ( 5 \ \mathrm { b a n d p o w e r s } ) , } \\ { n _ { t } \ = \ 1 . 2 0 _ { - 0 . 6 4 } ^ { + 0 . 5 6 } , 9 5 \% \mathrm { C L } . ( 5 \ \mathrm { b a n d p o w e r s } ) } \end{array}
$$

Second,with only the first 5 bandpower data,unlike the simplest power-law parameterization,a non-trivial shape of tensor spectrum is obtained. Concretely, in the range of $k \in ( 0 . 0 0 2 , 0 . 0 0 6 )$ BICEP2 data favor a large tensor blue-tilt, while when $k > 0 . 0 0 6 3 \mathrm { M p c } ^ { - 1 }$ the spectrum becomes almost flat. This is due to the fact that we do not use the last 4 bandpower data. The resulting tensorto-scalar ratio in our cubic spline interpolation method is

$$
r _ { 0 . 0 0 2 } < 0 . 0 6 0 , 9 5 \% \mathrm { C L } , ( 5 \mathrm { b a n d p o w e r s } ) .
$$

![](images/a80f71e30855ccc936f5466148c9960e7f7fb07b10491416f081d272af637029.jpg)  
FIG.5:Reconstruction of primordial tensor spectrum with Planck+WPand $P l a n c k { + } \tau$ prior.

Because the above blue tensor tilt is significantly inconsistent with the standard inflationary prediction,we have to figure out its reason on the data analysis level. Notice that for nowwealwaysutilize Planck+WP $^ +$ BICEP2 data compilation， so one natural guess is that this blue tensor tilt might reflect the tension among Planck, WMAP polarization and BICEP2data sets.In order to justify our conjecture,we have to remove the above data sets one by one.Since we vary both the primordial spectrum and standard $\Lambda$ CDM parameters,such as baryon $\left( \Omega _ { b } h ^ { 2 } \right)$ , cold dark matter density $( \Omega _ { c } h ^ { 2 } )$ etc,we have to keep the robust Planck temperature data in order to get well estimations of the $\Lambda$ CDM parameters. Hence,we first remove the BICEP2,i.e. using Planck+WP,and further discard WMAP polarization data,i.e. only using Planck temperature data.However,due to the fact that CMB temperature data are insensitive to the reionization optical depth ( $^ { \prime }$ ),if we discard WMAP polarization data we have to include gaussian prior on $\tau$ to break the wellknown degeneracy between $\tau$ and the scalar amplitude $A _ { s }$ . Here we take the gaussian prior as

$$
\tau = 0 . 0 8 9 \pm 0 . 0 1 3 .
$$

Besides this,because the contribution of tensor spectra to CMB temperature anisotropies is only significant in the mulitpole range ( $2 ~ \leq ~ \ell ~ \leq ~ 1 0 0$ )，when we use Planck+WP or $P l a n c k { + } \tau$ prior data sets,we sample the $k$ knots of tensor spectra in the range of (0.0oo2,0.01).

The resulting primordial tensor spectrum shape,corresponding marginalized 1D/2D posterior distributions and parameter regimes are shown in Fig.5,Fig.1O and Tab.V.First，we can see that the reconstructed tensor spectra from Planck+WP and Planck+ $^ { \circ }$ prior are very similar,both the central values and the marginalized error bars. So，we can draw the conclusion that WMAP low- $\ell$ polarization data are not crucial for the tensor reconstruction results. Second,as shown in Fig.6 the error bars from Planck temperature data are quite large compared with those from the data compilation Planck+WP+BICEP2 (see the error bars at sampling knot $k = 0 . 0 1 \mathrm { M p c ^ { - 1 } }$ in the dashed black curve and those at the second knot in the black solid curve in Fig.6). It means that the current Planck temperature data are not rubost to determine the shape of the primordial tensor spectrum.The resulting tensor spectrum from only Planck temperature data could be any shape among red, blue or scale-invariant types. Third,when we compare the second knot in Planck+WP(dashedblack curve) and the first left knot Planck+WP $^ +$ BICEP2results (solid black curve)，Fig.6 shows that both their central value and marginalized error bars are very close.It reflects the fact that the reconstructed tensor spectrum in the low$k$ regime is actually driven by Planck temperature data. Furthermore,considering the fact that the BICEP2 data dominate the high- $k$ part,we conclude that our reconstructed blue tensor tilt are due to the tension between Planck and BICEP2 data sets,i.e.the fact that small tensor amplitude signals from Planck temperature data dominates the large scale reconstruction, while the large tensor amplitude signals from BICEP2 B-mode polarization data dominates the small scale reconstruction,leads to the resulting blue tensor tilt.

![](images/180d36b6f3980a4cf10b6baa964ac3045bd8eb0d224a8ce6f5e2107c9da5daaf.jpg)  
FIG.6:Reconstruction of primordial tensor spectrum with/without BICEP2.

Finally, in order to give an intuitive impression of our reconstruction result，in Fig.7 we plot the BB autocorrelation power spectrum of our marginalized mean models (listed in Tab.IV of Appendix B） as well as the scale-invariant tensor spectrum with $r = 0 . 2$ model against the BICEP2 bandpowers data sets.We can see that in order to fit the BICEP2 data in the last 4 bandpowers,compared with the 5 bandpower reconstruction result (green curve） and the scale-invariant one (blue), the 9 bandpower (red） curve grows up in the high- $\ell$ more careful cross-check with future experiments,such as the polarization data of Planck and Keck Array.On the other hand,once this discovery is confirmed,it will lead to a paradigm revolution about our understanding of the early universe.

![](images/27136458f86ce6b7d4154aebbd06542e3f6d0ce980485834fc7ea8f7775254a9.jpg)  
FIG.7: CMB B-mode polarization auto-correlation spectrum CBB.

regimesignificantly

# IV.CONCLUSIONS

Starting with a purely phenomenological point of view, in this paper we have reconstructed the shape of the primordial scalar and tensor spectra by using the cubic spline interpolation method with Planck temperature and BICEP2 B-mode polarization data sets.We find that，due to the anti-correlation between scalar and tensor amplitudes on the large scales,the large value of tensor-to-scalarratio discovered by BICEP2 data will lead to the suppression of scalar amplitude in this regime. Concretely, the vanishing scalar index running model is strongly disfavored by Planck+WP $^ +$ BICEP2 data compilation with more than $3 \sigma$ confidence level on the $k = \mathrm { 0 . 0 0 0 2 \ M p c ^ { - 1 } }$ scale.Furthermore,for the tensor spectrum reconstruction,a blue-tilt spectrum is obtained no matter using only the first 5 bandpowers $n _ { t } ~ = ~ 1 . 2 0 _ { - 0 . 6 4 } ^ { + 0 . 5 6 }$ （95%CL）orthefull9bandpowers $n _ { t } = 1 . 2 4 _ { - 0 . 5 8 } ^ { + 0 . 5 1 }$ (95%CL) of BICEP2 data sets.Because of the large tensor tilt,compared with the large tensorto-scalar ratio value ( $r \sim 0 . 2 0$ ）under the scale-invariant assumption,our cubic spline interpolation method gives $r _ { 0 . 0 0 2 } < 0 . 0 6 0$ (95%CL） and $r _ { 0 . 0 0 2 } < 0 . 0 6 4$ (95%CL)by using the data sets Planck+WP $^ +$ BICEP2(5bandpowers）and (9 bandpowers)，respectively. Finally，we also studied the data without BICEP2,we found that our resulting blue tensor tilt actually reflects the tension in the tensor amplitude between Planck (small amplitude but dominate the reconstruction on the large scale) and BICEP2 (large amplitude but dominate the reconstruction on the small scale)data sets.

Our results show that the conclusion of the blue-tilt tensor spectrum is very significant and independent of using power-law or cubic spline parameterizations.More important, this blue-tilt spectrum is not consistent with the prediction of the standard single field inflationary paradigm $n _ { t } ~ = ~ - r / 8$ ．On the one hand,it asks for a

# Acknowledgments

BH are indebted to Ana Achucarro，Sabino Matarrese，Nicola Bartolo，Wessel Valkenburg and Frederico Arroja for various helpful discussions. BH is supported by the Dutch Foundation for Fundamental Research on Matter (FOM). JWH, ZKG and RGC are partially supported by the project of Knowledge Innovation Program of Chinese Academy of Science, NSFC under Grant No.11175225,No.11335012,and National Basic Research Program of China under Grant No.2010CB832805 and No.2010CB833004.

# AppendixA:Marginalizedstatistics inscalar spectrum reconstruction

Here we list the various marginalized statistical results for cubic spline interpolation and power-law parameterizations of scalar spectrum,including 1D,2D marginalized posterior distribution,marginalized mean values as well as the 68% (or $9 5 \%$ ） confidence levels.

![](images/0078b72196fdccdbb7208f2708a055d19fda3197fc0adca0196b0b0ab8c8a9f7.jpg)  
FIG.8:1D/2D posterior distribution of scalar spectrum reconstruction.

TABLE II: Mean values and $6 8 \%$ (or $9 5 \%$ ) confidence limits for primary/derived parameters in the cubic spline and power-law parameterization of scalar spectrum.   

<html><body><table><tr><td colspan="3">ACDM-ns-lnAs+r+lnA1+lnA2+lnA3</td><td>ACDM+dns/dlnk+r</td></tr><tr><td></td><td>Planck+WP</td><td></td><td>Planck+WP+BICEP2 (9 bandpowers)Planck+WP+BICEP2 (9 bandpowers)</td></tr><tr><td>Parameters</td><td>mean ± 68% C.L.</td><td>mean ± 68% C.L.</td><td>mean ± 68% C.L.</td></tr><tr><td>100Ωh²</td><td>2.224±0.031</td><td>2.224±0.030</td><td>2.238±0.028</td></tr><tr><td>Ωch²</td><td>0.1204±0.0028</td><td>0.1202±0.0027</td><td>0.1186±0.0017</td></tr><tr><td>1000MC</td><td>1.04125±0.00065</td><td>1.04133±0.00063</td><td>1.04150±0.00057</td></tr><tr><td>T</td><td>0.103±0.016</td><td>0.106±0.017</td><td>0.105±0.016</td></tr><tr><td>ln(1010 As)</td><td></td><td></td><td>3.122±0.033</td></tr><tr><td>ns</td><td></td><td></td><td>0.9600±0.0063</td></tr><tr><td>dns/dln k</td><td></td><td></td><td>−0.028+0.011 (95%CL)</td></tr><tr><td>r</td><td><0.41 (95%CL)</td><td>-0.19 (95%CL) 0.21+0.10</td><td>0.20±0.08 ±0.09 (95%CL)</td></tr><tr><td>ln(1010A1)</td><td>2.89±0.20</td><td>2.83±0.15</td><td></td></tr><tr><td>ln(1010 A2)</td><td>3.157±0.032</td><td>3.154±0.029</td><td></td></tr><tr><td>ln(1010 A3)</td><td>3.045±0.034</td><td>3.050±0.034</td><td></td></tr><tr><td>m</td><td>0.318±0.018</td><td>0.316±0.017</td><td>0.306±0.010</td></tr><tr><td>Ho[km/s/Mpc]</td><td>67.22±1.27</td><td>67.34±1.22</td><td>68.06±0.79</td></tr><tr><td>2/2</td><td>4901.833</td><td>4921.868</td><td>4924.052</td></tr></table></body></html>

# Appendix B:Marginalized statistics in tensor spectrum reconstruction

izations of tensor spectrum, including 1D,2D marginalized posterior distribution,marginalized mean values as well as the 68% (or $9 5 \%$ ） confidence levels.

Here we list the various marginalized statistical results for cubic spline interpolation and power-law parameter

![](images/16dee2fc0481b435c0f666264f5f2dedd08443a35babe5d49f7b4216863d79dd.jpg)  
FIG.9:1D/2D posterior distribution of tensor spectrum reconstruction with BICEP2.

TABLE III: Mean values and $6 8 \%$ (or $9 5 \%$ ) confidence limits for primary/derived parameters in the power-law parameterization of tensor spectrum.   

<html><body><table><tr><td colspan="3">ACDM+r+nt</td></tr><tr><td></td><td>Planck+WP+BICEP2 (9 bandpowers)Planck+WP+BICEP2 (5 bandpowers)</td><td></td></tr><tr><td>Parameters</td><td>mean±68%C.L.</td><td>mean ± 68% C.L.</td></tr><tr><td>100Ωh²</td><td>2.200±0.028</td><td>2.204±0.028</td></tr><tr><td>Ωch²</td><td>0.1194±0.0026</td><td>0.1195±0.0027</td></tr><tr><td>1000MC</td><td>1.04129±0.00064</td><td>1.04127±0.00063</td></tr><tr><td>T</td><td>0.090±0.013</td><td>0.089±0.013</td></tr><tr><td>ns</td><td>0.9611±0.0073</td><td>0.9615±0.0073</td></tr><tr><td>ln(1010 As)</td><td>3.087±0.025</td><td>3.086±0.025</td></tr><tr><td>r0.05</td><td><2.00 (95%CL) 1.24±0.51 (95%CL)</td><td><2.00 (95%CL) 1.20±0.56 (95%CL)</td></tr><tr><td>nt 2m</td><td></td><td></td></tr><tr><td></td><td>0.313±0.016</td><td>0.313±0.016</td></tr><tr><td>Ho[km/s/Mpc]</td><td>67.38±1.19</td><td>67.40±1.11</td></tr><tr><td>ro.002 /2</td><td><0.061 (95%CL)</td><td><0.067 (95%CL)</td></tr><tr><td></td><td>4920.773</td><td>4909.861</td></tr></table></body></html>

arXiv:1303.5082 [astr0-ph.CO].   
[3]W.Hu and M.J.White,Phys.Rev.D 56,596 (1997) [astro-ph/9702170].   
[4] K.M.Smith，C.Dvorkin，L.Boyle,N.Turok, M.Halpern，G.Hinshaw and B.Gold，arXiv:1404.0373 [astro-ph.CO].   
[5]G.Hinshaw et al.[WMAP Collaboration],Astrophys.J. Suppl.208,19 (2013)[arXiv:1212.5226 [astr0-ph.CO]].   
[6]S.Das,T.Louis,M.R.Nolta,G.E.Addison,E.S.Battistelli,JR.Bond,E.Calabrese and D.C.M.J.Devlin et al.,arXiv:1301.1037 [astro-ph.CO].   
[7] R.Keisler,C.L. Reichardt,K.A.Aird,B.A.Benson,

<html><body><table><tr><td colspan="3">ACDM+lnBi+lnB2+lnB3</td></tr><tr><td></td><td>Planck+WP+BICEP2 (9 bandpowers)Planck+WP+BICEP2 (5 bandpowers)</td><td></td></tr><tr><td>Parameters</td><td>mean±68% C.L.</td><td>mean±68%C.L.</td></tr><tr><td>100Ωh2</td><td>2.202±0.028</td><td>2.202±0.028</td></tr><tr><td>Ωch²</td><td>0.1194±0.0026</td><td>0.1195±0.0026</td></tr><tr><td>1000MC</td><td>1.04130±0.00063</td><td>1.04125±0.00062</td></tr><tr><td>T</td><td>0.090±0.013</td><td>0.090±0.013</td></tr><tr><td>ns</td><td>0.9610±0.0071</td><td>0.9614±0.0072</td></tr><tr><td>ln(1010 As)</td><td>3.087±0.025</td><td>3.087±0.025</td></tr><tr><td>ln(1010 B1)</td><td><0.45 (95%CL)</td><td><0.39 (95%CL)</td></tr><tr><td>ln(1010 B2)</td><td>-0.92 (95%CL) 0.98±0.88</td><td>-1.02 (95%CL) 1.12+1.05</td></tr><tr><td>ln(1010 B3)</td><td>2.37 (95%CL) 2.75±1.29</td><td>-2.00 (95%CL) 1.48±1.48</td></tr><tr><td>Ωm</td><td>0.313±0.016</td><td>0.314±0.016</td></tr><tr><td>Ho[km/s/Mpc]</td><td>67.43±1.17</td><td>67.37±1.17</td></tr><tr><td>ro.002</td><td><0.064 (95%CL)</td><td><0.060 (95%CL)</td></tr><tr><td>x/2</td><td>4920.558</td><td>4909.799</td></tr></table></body></html>

TABLE IV: Mean values and $6 8 \%$ (or $9 5 \%$ ） confidence limits for primary/derived parameters in the tensor spectrum cubic spline reconstruction.

![](images/fb6b0a820f9fcd0160443d840cd0083c96086fb28a22bce23632f360fa272ec6.jpg)  
FIG.10:1D/2D posterior distribution of tensor spectrum reconstruction without BICEP2.

L.E.Bleem,J.E.Carlstrom,C.L.Chang and H.M.Cho etal.，Astrophys.J.743，28(2011）[arXiv:1105.3182 [astro-ph.CO]].   
[8] K．T.Story，C.L.Reichardt，Z.Hou，R.Keisler, K．A． Aird， B. A.Benson，L.E. Bleemand J.E.Carlstrom et al.，Astrophys.J.779，86 (2013) [arXiv:1210.7231 [astro-ph.CO]].   
[9]C.L.Reichardt，L.Shaw,O.Zahn，K.A.Aird, B．A．Benson，L．E.Bleem，J.E.Carlstrom and C.L.Chang et al.，Astrophys. J. 755， 70 (2012) [arXiv:1111.0932 [astr0-ph.CO].   
[10]V.c.Miranda,W.Hu and P.Adshead,arXiv:1403.5231 [astro-ph.CO].   
[11]D.K.Hazra， A. Shafieloo， G．F. Smootand A.A.Starobinsky,arXiv:1403.7786 [astro-ph.CO].   
[12]R.Bousso,D.Harlow and L. Senatore,arXiv:1404.2278 [astro-ph.CO].   
[13] D.K.Hazra， A. Shafieloo and G.F. Smoot, arXiv:1404.0360 [astro-ph.CO].   
[14] M. Kawasaki and S. Yokoyama,arXiv:1403.5823 [astroph.CO].   
[15] M.Kawasaki，T. Sekiguchi,T. Takahashiand S. Yokoyama,arXiv:1404.2175 [astro-ph.CO].   
[16]E.Giusarma,E.Di Valentino,M.Lattanzi,A.Melchiorri and O.Mena,arXiv:1403.4852 [astro-ph.CO].   
[17] J. -F. Zhang,Y. -H. Li and X. Zhang,arXiv:1403.7028 [astro-ph.CO].   
[18] C.Dvorkin，M. Wyman，D.H. Rudd and W.Hu, arXiv:1403.8049 [astr0-ph.CO].   
[19] C.R. Contaldi, M. Peloso and L. Sorbo,arXiv:1403.4596 [astro-ph.CO].   
[20]B.Freivogel,M.Kleban,M.R.Martinez and L.Susskind, arXiv:1404.2274 [astro-ph.CO].   
[21] H.Firouzjahi and M. H. Namjoo,arXiv:1404.2589 [astroph.CO].   
[22] Y.-F. Cai, J. -O. Gong and S. Pi,arXiv:1404.2560 [hepth].   
[23] C. Cheng, Q. -G. Huang and W. Zhao, arXiv:1404.3467 [astro-ph.CO].   
[24] S.Choudhury and A.Mazumdar,arXiv:1403.5549 [hepth].   
[25] S.Hotchkiss,A. Mazumdar and S. Nadathur,JCAP 1202,008(2012) [arXiv:1110.5389 [astro-ph.CO]].   
[26] M.Gerbino,A.Marchini,L.Pagano,L.Salvati,E.Di Valentino and A. Melchiorri,arXiv:1403.5732 [astroph.CO].   
[27] F.Wu, Y.Li, Y.Lu and X. Chen,arXiv:1403.6462 [astroph.CO].   
[28] C.Cheng and Q. -G.Huang，arXiv:1403.7173 [astroph.CO].   
[29] H. Li, J. -Q. Xia and X. Zhang,arXiv:1404.0238 [astroph.CO].   
[30] B.Chang and L.Xu,arXiv:1404.1558 [astro-ph.CO].   
[31]M.Baldi,F.Finelli and S.Matarrese,Phys.Rev.D 72, 083504(2005) [astro-ph/0505552].   
[32] Y.-S. Piao and Y.-Z. Zhang,Phys.Rev.D 70,063513 (2004) [astro-ph/0401231].   
[33] T.Kobayashi, M. Yamaguchi and J.'i. Yokoyama, Phys. Rev.Lett.105,231302(2010) [arXiv:1008.0603 [hep-th]].   
[34]R.H.Brandenberger，A.Nayeri and S.P.Patil, arXiv:1403.4927 [astro-ph.CO].   
[35] P.Creminelli,M.A.Luty,A.Nicolis and L.Senatore, JHEP 0612,080 （2006）[hep-th/0606090].   
[36] P.Creminelli and L.Senatore,JCAP O711,O10 (2007) [hep-th/0702165].   
[37] E.I. Buchbinder,J. Khoury and B.A. Ovrut,Phys. Rev. D 76,123503 (2007) [hep-th/0702154].   
[38] J._-Q.Xia,Y. -F. Cai,H. Li and X. Zhang, arXiv:1403.7623 [astro-ph.CO].   
[39] T. Qiu,arXiv:1404.3060 [gr-qc].   
[40] Y.-S.Piao,B.Feng and X.-m. Zhang,Phys.Rev.D 69, 103520 (2004） [hep-th/0310206].   
[41] Z.-G. Liu, Z. -K. Guo and Y.-S. Piao, Phys. Rev. D 88, 063539（2013） [arXiv:1304.6527 [astro-ph.COl].   
[42] J.-O. Gong,arXiv:1403.5163 [astro-ph.CO].   
[43] Y.Wang and W. Xue,arXiv:1403.5817 [astro-ph.CO].   
[44] C.Sealfon,L.Verde and R. Jimenez,Phys.Rev.D 72, 103520(2005)[astro-ph/0506707].   
[45]L.Verde and H.V.Peiris，JCAP 0807,009 (2008) [arXiv:0802.1219 [astro-ph]].   
[46]H.V.Peiris and L.Verde，Phys.Rev.D 81，O21302 (2010）[arXiv:0912.0268 [astro-ph.CO].   
[47] Z. -K.Guo,D.J. Schwarz and Y.-Z. Zhang, JCAP1108, 031(2011） [arXiv:1105.5916 [astro-ph.CO]].   
[48] Z. -K. Guo and Y. -Z. Zhang, JCAP 1111, 032 (2011) [arXiv:1109.0067 [astro-ph.CO]].   
[49] Z. -K. Guo and Y. -Z. Zhang, Phys.Rev.D 85,103519 (2012）[arXiv:1201.1538 [astro-ph.CO]].   
[50] G. Aslanyan,L. C. Price, K.N.Abazajian and R. Easther,arXiv:1403.5849 [astro-ph.CO].   
[51] K.N.Abazajian， G. Aslanyan， R. Easther and L.C.Price,arXiv:1403.5922 [astro-ph.CO].   
[52] J.A. Vazquez, M. Bridges， M. P. Hobson and A.N.Lasenby,JCAP 1206,006(2012) [arXiv:1203.1252 [astro-ph.CO]].   
[53] J.A. Vazquez, M. Bridges, Y. -Z. Ma and M. P. Hobson, JCAP 1308,001 (2013)[arXiv:1303.4014 [astr0-ph.CO]].   
[54] P.A.R.Ade et al.[Planck Collaboration], arXiv:1303.5075 [astro-ph.CO].   
[55]P.A.R.Adeetal.[PlanckCollaboration], arXiv:1303.5076 [astro-ph.CO].   
[56] A.Lewis,A.Challinor and A.Lasenby，Astrophys. J.

<html><body><table><tr><td colspan="3">ACDM+lnBi+lnB2+ln B3</td></tr><tr><td></td><td>Planck+WP</td><td>Planck+r Prior</td></tr><tr><td>Parameters</td><td>mean ±68% C.L.</td><td>mean ± 68% C.L. 2.203±0.028</td></tr><tr><td>100Ωh² Ωch² T ns ln(1010 As) 1000MC</td><td>2.204±0.028 0.1200±0.0028 1.04122±0.00063 0.089±0.013 0.9603±0.0074 3.087±0.025</td><td>0.1201±0.0027 1.04119±0.00063 0.090±0.012 0.9599±0.0071 3.089±0.024 (-3.00,3.00) (95%CL)(-3.00,3.00) (95%CL)</td></tr><tr><td>ln(1010 B2) ln(1010 B3) 2m</td><td>(-3.00,0.49) (95%CL) (-3.00,3.00) (95%CL) 0.317±0.017</td><td>(-3.00,0.45) (95%CL) (-3.00,3.00) (95%CL) 0.317±0.016</td></tr><tr><td>Ho[km/s/Mpc] ro.002 /2</td><td>67.20±1.22 <0.064 (95%CL) 4902.387</td><td>67.14±1.17 <0.062 (95%CL) 3895.305</td></tr></table></body></html>

[astro-ph/0205436].