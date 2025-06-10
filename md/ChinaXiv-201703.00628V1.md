# Simulation of positron backscattering on Al, Cu, Ag and Au targets using GEANT4 code

Xin Lail,2, Xiaopan Jiangl, Xingzhong Caol§, Xi Zhang2\*, Zhiming Zhang', Xuexiang Caol, Gang Xiang², Baoyi Wangl, Long Weil δ

lBeijing Engineering Research Center of Radiographic Techniques and Equipment, Institute of High Energy Physics, CAS,Beijing 100O49, China

2Collge of Physical Science and Technology, Sichuan University, Chengdu 610064, China

Corresponding authour:

caoxzh@ihep.ac.cn, weil $@$ ihep.ac.cn, \*xizhang@ scu.edu.cn

# ABSTRACT

In this paper, backscattering of $3 { \cdot } 5 0 \ \mathrm { k e V }$ positrons on $A l , C u , A g$ and $A u$ metallic targets has been systematically investigated using GEANT4 code. The dependence of positron backscattering coefficients on atomic number $Z$ ， target thickness,incident energy and angleshasbeen discussed comprehensively. Besides， positron backscattering spectra for those metallic targets at different discrete scattering angles were also studied to provide theoretical basis of the most appropriate scattering angle selected for simulation parameters and specified applied measurement techniques. The impact of atomic number $Z$ of targets on positron backscattering spectra was investigated as well. Simulation results are in reasonable agreement with previous experiment data and theoretical work.

Keywords: GEANT4; Positron; Backscattering coeficients; Backscattering spectra

# 1. Introduction

The interaction of slow charged particles such as electrons and positrons with solid targets is of prime importance in many applications including electron spectroscopy, electron microlithography， positron annihilation spectroscopy and so $\mathrm { o n } ^ { [ 1 - 7 ] }$ For instance, slow positron beam techniques have been used as a probe of surfaces or thin films in many ways[8-12]. Positron backscattering has significant influence on applied measurement results reflecting the information of surface and interfaces of thin films, such as the structure,defects,and electrons distribution of density and momentum. There is a potential that positron beams would be developed as industrial analysis tools utilized to obtain damage distribution information of the surface or near-surface region[13l.In addition，a comprehensive understanding of the positron collsion process in solids underpins and strengthens the description of equivalent electron processes which govern the interpretation of an array of experimental techniques using mono-energetic electrons as detectors[14]. Backscatered positrons refer to those positrons which, when directed toward the surface of a solid target with some incident energy, are scattered backward with a scattering angle larger than $9 0 ^ { \circ [ 1 5 ] }$ . It is well known that the fraction of the primary positrons from surface can be described by the backscattering coefficient, which is usually used as a major index to characterize the absorbed rate of incident particles and could provide basic mechanism to describe the scattering processes accurately[16]. The dependence of backscatering coefficients for positrons or electrons on target thicknesses,atomic number $Z .$ ，particle energy and incident angles have been widely investigated[17-25]. However, most works focused on one certain factor of those mentioned above,and the corresponding backscattering spectra were rarely reported. In experiments, the energy loss spectra of backscattered positrons could be used to characterize the components,morphology and structure of the material surface.

It is necessary to point out that the direct measurement of positron backscattering coefficients in experiments has some inevitable and uncontrollable factors which affect the experimental results. For instance,the relatively weak intensity of positron beams compared with electron beams and the effect of confining magnetic field on positron beams could affect the results indeed. GEANT4[26-29] is a very strong toolkit aimed to simulate the passage of particles through condensed matter over a wide energy range. The standard electromagnetic processes related to electron/positron include bremsstrahlung,ionization and $\delta$ -ray production, positron annihilation and synchrotron radiation. In the present paper, the simulation results of backscattering coefficients and spectra of positrons impinging on several targets with various atomic number $Z$ and thickness using GEANT4 code are reported. Primary positron energy and incident angles are settled in the range of $3 { \cdot } 5 0 \ \mathrm { k e V }$ and $0 ^ { \circ } - 8 0 ^ { \circ }$ , respectively. Al, Cu, $\scriptstyle A g$ and $A u$ are selected as the targets for the following reasons: atoms are randomly uniformly distributed in the structure established through GEANT4 and the structure properties only depends on the density and its atomic number $Z$ set up in GEANT4. As a result, the models we build is very close to the actual cubic structures of $A l , C u , A g$ and $A u$ elements.

# 2. Theories and models

According to the wel-nown Vicanek and Urbassek theory[30],the backscattering coefficient could be expressed as:

$$
\eta \left( \theta _ { i } \right) = \left( 1 + a _ { 1 } \frac { \mu _ { 0 } } { \upsilon ^ { \frac { 1 } { 2 } } } + a _ { 2 } \frac { \mu _ { 0 } ^ { 2 } } { \upsilon } + a _ { 3 } \frac { \mu _ { 0 } ^ { 3 } } { \upsilon ^ { \frac { 3 } { 2 } } } + a _ { 4 } \frac { \mu _ { 0 } ^ { 4 } } { \upsilon ^ { 2 } } \right) ^ { - 1 / 2 }
$$

where $\upsilon$ is the mean number of wide-angle collisions defined as:

$$
\upsilon = N R \sigma _ { { } _ { t r } }
$$

in expression (2), $\sigma _ { { } _ { t r } }$ stands for the transport elastic scattering cross sections:

$$
\sigma _ { _ { t r } } = 2 \pi \int _ { 0 } ^ { \pi } \bigl ( 1 - \cos \theta \bigr ) \frac { d \sigma } { d \Omega } \mathrm { s i n } \theta d \theta
$$

where $\theta$ is the polar-scattering angle[31].

If the incident mono-energetic positron annihilates with electrons directly during the implantation process,then it is assigned to an “absorbed” positron,if it comes back to the same surface through which it penetrates,then it is assigned to a backscattered positron,and finally, if it crosses through the target, then it is assigned to a transmitted positron. The positrons interact with the atoms by the elastic scattering with the nuclei or the inelastic scattering with the electrons in targets. The scattering processes can be described by the scattering cross sections in the interior of the solid,which could be used to determine the trajectories of the positrons in a GEANT4 simulation[32]. G4eMultipleScatering are utilized to handle the elastic scattering process. The inelastic cross section is introduced in the present GEANT4 simulation by G4eIonisation to calculate the energy loss. The positron energy decreases gradually in a continuous manner between elastic collisions. The cut value is set to $1 \ \mathrm { n m }$ and the minimum energy is $2 0 { \mathrm { ~ e V } } ,$ the amount of positrons set up for each simulationis $1 0 ^ { 6 }$ . Fig. 1 shows the model structure used to calculate backscattering spectra. Constant $d$ is set to be $0 . 7 \ \mathrm { c m }$ which stand for the distance between the target and the annular detector. We select 1 cm as the thickness of the target which is far greater than its corresponding positron implantation depth. The target radius is set to be $0 . 5 \ \mathrm { c m }$ . the scattering angle $\theta$ is adjusted through the control of inside and outside diameters of the annular detector as shown in Table 1.

![](images/0c04fc1e7ea3343b70ed0b64852976db7bcb853b918959895b5ef063424dff02.jpg)  
Fig 1. Model constructed for the simulation of positron backscattering spectra.

<html><body><table><tr><td>0 (deg)</td><td>Inside (cm)</td><td>Outside (cm)</td></tr><tr><td>120°-130°</td><td>0.8337</td><td>1.2124</td></tr><tr><td>140°-150°</td><td>0.4039</td><td>0.5873</td></tr><tr><td>160°-170°</td><td>0.1232</td><td>0.2548</td></tr></table></body></html>

Table 1. The inside and outside diameters of the annular detector for different backscattering angles.

# 3.Results and discussions

Backscattering coefficients of $3 { \cdot } 5 0 \ \mathrm { k e V }$ positrons impinging on various semi-infinite targets versus incident energy are shown in Fig. 2. Available experimental and theoretical data are presented for comparison, P.G. Coleman et al[14] have investigated the positron backscattering from elemental solids experimentally. a $72 \%$ -efficiency HPGe detector was utilized to record the annihilation positrons through detecting the 0.511 MeV photons produced during annihilation. The amount of backscattered positrons was obtained by removing the annihilation fraction from the total number of positrons. Annihilation count rate $C _ { B e }$ for beryllium sample was used to deduce the incident beam intensity $I _ { \mathrm { 0 } }$

$$
I _ { 0 } = C _ { { \scriptscriptstyle B e } } / 0 . 9 6 2 5
$$

The backscattering coefficient is then evaluated from:

$$
\eta ( E ) = 1 - 0 . 9 6 2 5 C ( E ) / C ( B e )
$$

Where $C ( E )$ were the annihilation count rates for other samples for each positron energy $E$ selected. As for the theoretical calculation, Chaoui and Bouarissa[33] have utilized the well-known Vicanek and Urbassek theory mentioned above to calculate the backscattering coefficient of $ { 1 - 1 0 }  { \mathrm { \ k e V } }$ positrons. The only difference is that the transport cross section $\sigma _ { { } _ { t r } }$ used is expressed as the following series:

$$
\sigma _ { t r } = 4 \pi \sum _ { l = 0 } ^ { \infty } \left( l + 1 \right) \sin ^ { 2 } \left( \delta _ { l } - \delta _ { l + 1 } \right)
$$

In expression (6)，the phase shifts $\delta _ { \scriptscriptstyle l }$ are obtained by numerically solving the Schrodinger equation of a positron with an atom bound in a solid.

Our simulation results are reasonably agreeable with them in similar variation tendency, the deviations between simulation results and the experimental data may be introduced by experimental errors or GEANT4 code itself. Actually， the detailed crystal structure of the host material has not been perfectly incorporated in GEANT4 code.Although the model structures $( A l , C u , A g$ and $A u$ ） established are very close to their original cubic close packed structures, lack of the crystal effect still has an impact on the results to some extent.

![](images/f8885cd5e31dd617671e9ac5e513a30379f529915d4e8c83e382a17369b5328c.jpg)  
Fig 2. Backscattering coefficients of $3 { \cdot } 5 0 \mathrm { k e V }$ positrons on various targets. (a) $A l$ (b) （204号 $C u$ （c） $\scriptstyle A g$ and (d) $A u$ .experimental $( \mathrm { E x p } ) ^ { [ 1 4 ] }$ , and theoretical (Theor)[33] results are presented for comparison.

Table 2. GEANT4，experimental $( \mathrm { E x p } ) ^ { [ 1 4 ] }$ and theoretical (Theor)[3] results for positron backscattering coefficients from $A l , C u , A g$ and $A u$

<html><body><table><tr><td>Z</td><td>E(keV)</td><td>3</td><td>5</td><td>7</td><td>10</td><td>15</td><td>20</td><td>25</td><td>30</td><td>35</td><td>50</td></tr><tr><td rowspan="3">13</td><td>GEANT4</td><td>0.076</td><td>0.086</td><td>0.092</td><td>0.099</td><td>0.097</td><td>0.100</td><td>0.098</td><td>0.100</td><td>0.103</td><td>0.107</td></tr><tr><td>Theor</td><td>0.104</td><td>0.111</td><td>0.116</td><td>0.123</td><td></td><td>1</td><td>1</td><td></td><td></td><td>1</td></tr><tr><td>Exp</td><td>0.086</td><td>0.112</td><td>0.122</td><td>0.123</td><td>0.144</td><td>0.146</td><td>0.15</td><td>0.141</td><td>0.138</td><td>0.139</td></tr><tr><td rowspan="3">29</td><td>GEANT4</td><td>0.117</td><td>0.151</td><td>0.169</td><td>0.189</td><td>0.193</td><td>0.206</td><td>0.210</td><td>0.212</td><td>0.214</td><td>0.222</td></tr><tr><td>Theor</td><td>0.163</td><td>0.185</td><td>0.2</td><td>0.215</td><td></td><td>=</td><td></td><td></td><td>1</td><td>1</td></tr><tr><td>Exp</td><td>0.177</td><td>0.205</td><td>0.226</td><td>0.229</td><td>0.234</td><td>0.252</td><td>0.265</td><td>0.253</td><td>0.266</td><td>0.255</td></tr><tr><td rowspan="3">47</td><td>GEANT4</td><td>0.134</td><td>0.173</td><td>0.198</td><td>0.224</td><td>0.238</td><td>0.261</td><td>0.266</td><td>0.267</td><td>0.299</td><td>0.304</td></tr><tr><td>Theor</td><td>0.173</td><td>0.212</td><td>0.242</td><td>0.277</td><td></td><td>1</td><td></td><td>1</td><td></td><td></td></tr><tr><td>Exp</td><td>0.168</td><td>0.227</td><td>0.243</td><td>0.277</td><td>0.298</td><td>0.313</td><td>0.326</td><td>0.316</td><td>0.317</td><td>0.337</td></tr><tr><td rowspan="3">79</td><td>GEANT4</td><td>0.153</td><td>0.199</td><td>0.231</td><td>0.261</td><td>0.279</td><td>0.305</td><td>0.315</td><td>0.321</td><td>0.359</td><td>0.359</td></tr><tr><td>Theor</td><td>0.182</td><td>0.223</td><td>0.252</td><td>0.285</td><td></td><td>1</td><td></td><td></td><td>/</td><td></td></tr><tr><td>Exp</td><td>0.186</td><td>0.232</td><td>0.273</td><td>0.294</td><td>0.332</td><td>0.354</td><td>0.356</td><td>0.38</td><td>0.395</td><td>0.396</td></tr></table></body></html>

Table 3. Other MC simulation results[33-34] of backscattering coeffcients of $1 { - } 1 0 \ \mathrm { k e V }$ positrons on Al, Cu, Ag and $\boldsymbol { A u }$

<html><body><table><tr><td>Z</td><td>E(keV)</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>13</td><td>MC[33]</td><td>0.086</td><td>0.098</td><td>0.104</td><td>0.107</td><td>0.111</td><td>0.113</td><td>0.116</td><td>0.118</td><td>0.120</td><td>0.123</td></tr><tr><td>29</td><td>MC[34] MC[33]</td><td>0.095 0.117</td><td>0.098 0.146</td><td>0.098 0.163</td><td>0.096 0.175</td><td>0.099 0.185</td><td>0.099 0.193</td><td>0.100 0.200</td><td>0.104 0.205</td><td>0.105 0.210</td><td>0.109 0.215</td></tr><tr><td>47</td><td>MC[34] MC[33]</td><td>0.148 0.109</td><td>0.169 0.146</td><td>0.178 0.173</td><td>0.188 0.194</td><td>0.194 0.212</td><td>0.199 0.228</td><td>0.208 0.242</td><td>0.210 0.254</td><td>0.214 0.266</td><td>0.218 0.277</td></tr><tr><td></td><td>MC[34]</td><td>0.131</td><td>0.154</td><td>0.177</td><td>0.198</td><td>0.216</td><td>0.230</td><td>0.241</td><td>0.255</td><td>0.264</td><td>0.278</td></tr><tr><td>79</td><td>MC[33] MC[34]</td><td>0.112 0.128</td><td>0.153 0.161</td><td>0.182 0.189</td><td>0.205 0.207</td><td>0.223 0.226</td><td>0.239 0.240</td><td>0.252 0.251</td><td>0.264 0.263</td><td>0.275 0.273</td><td>0.285 0.276</td></tr></table></body></html>

As shown in Figure.2 and Table. 2, positron backscattering coefficients present a monotonic increase as the target atomic number $Z$ and incident energy increase,which could be explained by the fact that heavy atoms have a larger probability of scattering into large angles than the light atoms in elastic collisions, namely, a larger scattering cross section. It is worth noting that the backscattering coefficient increases gradually until the incident energy increases to a certain value (which depends on the target atomic number $Z$ ） and then becomes relatively constant for each metal. This suggests that the increase of positron incident energy may lead to the increase of scattering cross section in a particular energy range.

As shown in Table.3,we also presented other MC simulation results for positron $\mathrm { ( E { = } 1 { - } 1 0 ~ k e V ) }$ ）backscattering coefficients from Al, Cu,Ag and $A u$ ，It is found that GEANT4 results is more close to the experiment compared with other MC simulation results when the backscattering coefficient is relatively small(\~O.1OO ). This suggests GEANT4 simulation might be more reliable when the positron has a very low incident energy. Actually, the scattering model we selected leads to the difference of results obtained by various MC strategies. For example, ref-34 adopts the optimized Wentzel (OW2） model[35]，which is different with the our G4eMultipleScattering and G4eIonisation model. The elastic cross sections used in the optimized Wentzel (OW2) model are obtained utilizing the Dirac PW analysis (ELESPA code)[36] and the inelastic process is introduced through using a simple approximation to calculate the energy loss of the positron. Actually, ref-12 has also investigated the positron $( \mathrm { E } { = } 1 { - } 5 $ keV）backscattering coefficients from semi-infinite Al, Ag and Au through MC simulation, the results are in reasonable agreement with the present GEANT4 work.

![](images/fedc10aecf9de4fa0550233de365a74bfba6d39b523764315ec9dd230362b08a.jpg)  
Fig 3. Backscattering coefficients of positrons impinging on $A l$ and $A u$ targets versus incident angles. (a) $A l , 5 . 0 \mathrm { k e V }$ (b) $4 l , 3 5 . 0 \mathrm { k e V }$ (c) $A u$ ， $5 . 0 \mathrm { k e V }$ and (d) $A u , 3 5 . 0 \mathrm { k e V } .$ （204号 experimental $( \mathrm { E x p } ) ^ { [ 1 4 ] }$ ，and theoretical (Theor)[3]resultsarepresented for comparison.

Table 4. GEANT4, experimental $( \mathrm { E x p } ) ^ { [ 1 4 ] }$ , theoretical (Theor)[3] and MC simulation $\mathrm { ( M C ) } ^ { [ 3 4 ] }$ results for $5 \mathrm { k e V }$ positron backscattering coeficients from $A l$ and $A u$ versus incident angles.

<html><body><table><tr><td>Z</td><td>0 (deg)</td><td>0</td><td>10</td><td>20</td><td>30</td><td>40</td><td>50</td><td>60</td><td>70</td><td>80</td></tr><tr><td rowspan="4">13</td><td>GEANT4</td><td>0.086</td><td>0.091</td><td>0.104</td><td>0.123</td><td>0.155</td><td>0.204</td><td>0.280</td><td>0.386</td><td>0.538</td></tr><tr><td>Theor</td><td>0.111</td><td>0.114</td><td>0.124</td><td>0.143</td><td>0.177</td><td>0.237</td><td>0.341</td><td>0.517</td><td>0.754</td></tr><tr><td>Exp</td><td>0.112</td><td>0.113</td><td>0.11</td><td>0.116</td><td>0.141</td><td>0.166</td><td>0.24</td><td>1</td><td>-</td></tr><tr><td>MC</td><td>0.126</td><td>0.134</td><td>0.143</td><td>0.167</td><td>0.203</td><td>0.254</td><td>0.334</td><td>0.443</td><td>0.568</td></tr><tr><td rowspan="4">79</td><td>GEANT4</td><td>0.199</td><td>0.206</td><td>0.223</td><td>0.249</td><td>0.297</td><td>0.358</td><td>0.432</td><td>0.525</td><td>0.643</td></tr><tr><td>Theor</td><td>0.223</td><td>0.23</td><td>0.246</td><td>0.278</td><td>0.331</td><td>0.412</td><td>0.528</td><td>0.676</td><td>0.836</td></tr><tr><td>Exp</td><td>0.232</td><td>0.256</td><td>0.247</td><td>0.256</td><td>0.326</td><td>0.426</td><td></td><td>-</td><td>-</td></tr><tr><td>MC</td><td>0.290</td><td>0.295</td><td>0.301</td><td>0.336</td><td>0.369</td><td>0.422</td><td>0.478</td><td>0.552</td><td>0.673</td></tr></table></body></html>

Figure.3 and Table. 4 illustrates the dependence of positron backscatering coefficients on the incident angle $\theta$ ? $0 ^ { \circ } \leq \theta \leq 8 0 ^ { \circ }$ relative to the surface normal of the target species) for semi-infinite $A l$ (light element) and $A u$ (heavy element). 5.0 and $3 5 . 0 \ \mathrm { k e V }$ are selected as the typical incident energy for each target. The available experimental, MC simulation and theoretical results are also presented for comparison. The GEANT4 results indicate that backscattering coefficients of positrons impinging on both $A l$ and $\mathbf { \nabla } A u$ targets increase with the incident angle $\theta$ (independently of incident energy). It is worth noting that backscattering coefficients increase slowly below $2 0 ^ { \circ }$ , but vary rapidly when incident angles becomes larger. The discrepancies of the value of positron backscattering coefficients in these four situations are smaller and smaller. It is found that the backscattering coefficient of oblique incidence presents a significant increase compared with that of normal incidence,especially when the incident angle becomes larger. namely, it is easier for positrons to scatter through larger angle than $9 0 ^ { \circ }$ compared to the case of normal incidence. This could be atributed to the fact that positrons have encountered several small angle scatterings and lost more energy during the longer traversed path in targets and the small total elastic scatering cross sectionl22. As a result, the positron penetration depth becomes shallow, namely, the corresponding escape distance for positrons decreases,which causes positrons to emit out of the target surface more easily and leads to the increase of the positron backscattering coefficient at non-normal incidence. The results demonstrate that the positron backscattering coefficient is related to the incident angles and selecting an appropriate incident angle for measurement techniques could improve the effective counts and reduce the noise of background.

For $3 5 . 0 \mathrm { k e V }$ positrons with normal incidence, the variation of the backscattering coefficient ratio with the thickness of targets is shown in Fig. 4. Where,Bsc(t) is referred to a given thickness of targets and Bsc(si) is referred to the semi-infinite targets. The results show that for a certain material, the positron backscattering coefficient increases gradually until the target thickness increases to a critical value (which depends on the target material) and then becomes almost constant[15,21,37-38]. This could be explained by the simple fact that if the target is a bulk material, then the number of transmitted positrons would be zero and the fraction of backscattered positrons could reach its maximum value (backscattering coefficients of semi-infinite targets). It could be noticed that the critical thickness decreases with the increase of atomic number $Z$ ，which indicates that the impact of target surface on the backscattering coefficient is also related to the atomic number Z. Actually, the mean positron implantation depths for semi-infinite materials are customarily expressed as: $\overline { { z } } = \frac { A } { \rho } E ^ { n }$ AE",whereEis the positronenergy，pis the material densityndAand nare energy-independent constants for a particular material[39-40l. It could be speculated that the positron implantation depth is deeper for lighter atoms and hence a larger transmission probability considering the same target thickness.As a result， the possibility of emitting out of the target surface for incident positrons becomes smaller.

![](images/e3721a376a25eebb8aa3f7d468632c1e80087f53c6f8098030f2312aa93f9350.jpg)

Fig 4.The ratio of positron backscattering coefficient for the target thickness to that of the semi-infinite target, $\mathbf { B s c ( t ) } / \mathbf { B s c ( s i ) }$ versus the target thickness for $3 5 \mathrm { k e V }$ positrons.

Positron backscattering spectra for $A u$ targets are simulated at all angles in the range $1 0 0 ^ { \circ } \leq \theta \leq 1 8 0 ^ { \circ }$ at $1 0 ^ { \circ }$ intervals. It is relatively difficult to extract data for scattering angles less than $1 2 0 ^ { \circ }$ or more than $1 7 0 ^ { \circ }$ . Fig. 5 and Fig.6 present the backscattering spectra and relative (energy-integrated） backscattering yields of positrons impinging on $A u$ targets with normal incidence, respectively. It is found that that the most probable energy of backscattered positrons changes very little at different scattering angles. Besides, scattering angles in the range $1 2 0 ^ { \circ } - 1 4 0 ^ { \circ }$ have the maximal backscattering yields, backscattering yields decrease when scattering angles are less than $1 1 0 ^ { \circ }$ or more than $1 5 0 ^ { \circ }$ . This could provide theoretical support for parameters setting and specified applied measurement techniques.

![](images/5a8cd74a840737ba0b4bf23e01a31ebeddea3990e4798d6af22955ee43954d80.jpg)  
Fig 5. Backscattering spectra of $3 5 \ \mathrm { k e V }$ positrons impinging on semi-infinite $\mathbf { \nabla } A u$ targets at different discrete scattering angles.

![](images/53bf6b3f634051e1a11d843df11ad83eba6d9f9a3a6423690aea0a841f24eede.jpg)  
Fig 6. Relative backscattered yields (integrated over energy） of $3 5 \mathrm { \ k e V }$ positrons impinging on semi-infinite $A u$ targets.

In order to investigate the impact of atomic number $Z$ and scattering angles on the energy distribution, energy spectra of backscattered positrons with a normal incidence impinging on semi-infinite $A l , C u , A g$ and $\mathbf { \nabla } A u$ targets are simulated. On the basis of the parameters setting mentioned above, we select three typical discrete scattering angles $1 2 0 ^ { \circ } - 1 3 0 ^ { \circ }$ ， $1 4 0 ^ { \circ } { - } 1 5 0 ^ { \circ }$ and $1 6 0 ^ { \circ } - 1 7 0 ^ { \circ }$ . As shown in Fig.7, It is found that the most probable energy of backscattered positrons changes very litle at different scattering angles considering the same target species, but varies a lot for different target material considering the same scattering angle. This suggests that the influence of scattering angles on the energy distribution of backscattered positrons is less pronounced than that of atomic number Z. The peak of positron backscattering yields increases with target atomic number $Z$ considering the same scattering angle, which is consistent with the fact that the increase of target atomic mass leads to less energy loss and larger scattering cross section. Fig. 8 gives the relative (energy-integrated) backscattered yields versus the atomic number $Z$ 、The results show that the backscattering yields vary very little from $1 2 0 ^ { \circ } - 1 3 0 ^ { \circ }$ to $1 4 0 ^ { \circ } - 1 5 0 ^ { \circ }$ and the decrease at

$1 6 0 ^ { \circ } - 1 7 0 ^ { \circ }$ is significant compared to the former, which agrees with the results shown in Fig. 6 very well.

![](images/d4be57bc0136e90baf5ccf0eae4d6969e70c83129da53ce41bf067c868d3e496.jpg)  
Fig 7. Backscattering spectra of $3 5 \ \mathrm { k e V }$ positrons on various semi-infinite targets at three discrete scattering angles $1 2 0 ^ { \circ } - 1 3 0 ^ { \circ }$ ， $1 4 0 ^ { \circ } - 1 5 0 ^ { \circ }$ and $1 6 0 ^ { \circ } - 1 7 0 ^ { \circ }$ ： $1 0 ^ { 6 }$ incident positrons are used in each simulation run. (a) $A l$ (b) $C u$ (c） $\scriptstyle A g$ and (d) $A u$

![](images/6c5aa89b1aa73b6a5629642667aa7719dcc07f51f2a13d147731b18e7b28d102.jpg)

Fig 8. Relative backscattered yields (integrated over energy) of $3 5 \ \mathrm { k e V }$ positrons on semi-infinite $A l , C u , A g$ and $A u$ targets at three discrete scattering angles $1 2 0 ^ { \circ } - 1 3 0 ^ { \circ }$ $1 4 0 ^ { \circ } - 1 5 0 ^ { \circ }$ and $1 6 0 ^ { \circ } - 1 7 0 ^ { \circ }$ . The solid lines are drawn to guide the eye.

# 4. Conclusions

In the present paper, backscattering coefficients and spectra of $3 { \mathrm { - } } 5 0 \ \mathrm { k e V }$ positrons on a variety of targets $( A l , C u , A g$ and $A u$ ） with various thickness for different incident angles are simulated using GEANT4 code. The results show reasonable agreement with previous experiment data and theoretical calculation. It is found that positron backscattering coefficient presents a monotonic increase with both incident angles and atomic number $Z$ of targets. Considering a certain primary positron energy, the critical value of the target thickness at which backscattering coefficients become constant depends on the target material. The investigation of backscattering spectra indicates that atomic number $Z$ has a greater impact on the energy distribution of backscattered positrons compared to scattering angles. Our results may be useful for the application of slow positrons as a probe for obtaining information on the surface or near-surface region.

# Acknowledgments

This work is supported by the National Natural Science Foundation (Grant Nos.   
11475197, 11475193, 11175191).

# References

1. P.J. Schultz, K.G. Lynn, Rev. Mod. Phys. 1988, 60, 701.   
2.P.G. Coleman, Appl. Surf. Sci. 2002, 194, 264.   
3.C.J. Powell, A. Jablonski, S. Tanuma, J. Electron Spectrosc. Relat. Phenom. 1994,   
68, 605.   
4. I. Adesida, R. Shimizu, T.E. Everhart, J. Appl. Phys. 1980, 51, 5962.   
5. W.S.M. Werner, Surf. Interface Anal. 2001, 31, 141.   
6. J. Rundgren, Phys. Rev. B. 1999,59, 5106.   
7. G. Gergely, Prog. Surf. Sci. 2002, 71, 31.   
8.G.R. Massoumi, N. Hozhabri， K.O. Jensen， W.N. Lennard， M.S Lorenzo, P.J.   
Schultz, A.B. Walker, Phys. Rev. Lett. 1992, 68, 3873.   
9. M. Dapor, J. Appl. Phys.1995,77, 2840.   
10. N. Bouarissa, A.B. Walker, H. Aourag, J. Appl. Phys. 1998, 83, 3643.   
11. Z. Chaoui, N. Bouarissa, J. Appl. Phys. 2004, 96, 807.   
12.N. Bouarissaa, M.S. Al-Assiri, J. Electron. Spectrosc. Relat. Phenom. 2013,191,   
11.   
13. A. Zecca, Appl. Surf. Sci. 2002, 194, 4.   
14.P.G. Coleman, L. Albrecht, K.O. Jensen, A.B. Walker, J. Phys.: Condens. Matter.   
1992, 4, 10311.   
15.A.Bentabet, N. Bouarissa, Appl. Surf. Sci. 2007,253,8725.   
16.J. Makinen, S. Palko, J. Martikainen, P. Hautjarvi, J. Phys.: Condens. Matter 1992,   
4, L503.   
17. V.J. Ghosh, G.C. Aers, Phys. Rev. B. 1995, 51, 45.   
18. M. Dapor, J. Appl. Phys. 1996,79, 8406.   
19. G.R. Massoumi, W.N. Lennard, P.J. Schultz, A.B. Walker, K.O. Jensen, Phys. Rev.   
B. 1993, 47, 11007.   
20. K.O. Jensen, A.B. Walker, Surf. Sci. 1993, 292, 83.   
21. M. Dapor, Phys. Rev. B. 1992, 46, 618.   
22.N.Bouarissa, B. Deghfel, A. Bentabet, Europ. Phys. J. AP. 2002,19,89.   
23. G.R. Massoumi, N. Hozhabri, W.N. Lennard, P.J. Schultz, Phys. Rev. B.1991, 44,   
3486.   
24. A.P. Knights, P.G. Coleman, J. Phys.: Condens. Matter: 1995,7, 3485.   
25. J.A. Baker, P.G. Coleman, J. Phys. C: Solid State Phys. 1988, 21, L875.   
26. S. Agostinelli, J. Allison, K. Amako, et al, Nucl. Instrum. Methods Phys. Res., Sect.   
A. 2003, 506, 250.   
27.J. Dryzek, P. Horodek, Nucl. Instrum. Methods Phys. Res.， Sect. B. 2008, 266,   
4000.   
28. S. Agostinelli et al., Nucl. Instr. and Meth. A, 2003, 506, 250.   
29. V. N. Ivanchenko, Nucl. Instr. and Meth. A, 2003, 502, 666.   
30. M. Vicanek, H.M. Urbassek, Phys. Rev. B.1991, 44, 7234.   
31.A. Jablonski, Phys. Rev. B.1998, 58, 24.   
32. S. Valkealahti, R.M. Nieminen, Appl. Phys. A. 1983,32, 95.   
33. Z. Chaoui, N. Bouarissa, J. Phys.: Condens. Matter: 2004, 16,799.   
34.Z. E. A. Chaoui, J. Phys.: Condens. Matter 2006,18, 10303   
35.Z. Chaoui, Appl. Phys. Lett. 2006, 88, 024105   
36.F. Salvat, A. Jablonski, C. J. Powell, Comput. Phys. Commun, 2005,165,157   
37. B.Deghfel, A. Bentabet, N. Bouarissa, Phys. Status Solidi (b). 2003, 238,136.   
38. M. Dapor, Eur: Phys. J. Appl. Phys. 2002,18, 155.   
39. V. J. Ghosh, M. McKeown, D.O. Welch, KG. Lynn, Nucl. Instrum. Methods Phys.   
Res., Sect. B. 1994, 90, 442.   
40.N. Bouarissa, A.B. Walker, Int.J. Mod. Phys.B,2000, 14, 1603