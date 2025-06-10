# Low temperature thermal history reconstruction using apatite fission-track length distribution and apatite U-Th/He age

Ruxin Dinga,b, \*

a School of Earth Science and Engineering, Sun Yat-sen University, Guangzhou 51O275, China   
b Guangdong Provincial Key Laboratory of Mineral Resources & Geological Processes, Guangzhou   
510275, China   
\*Corresponding author: dingrux $@$ mail.sysu.edu.cn

Abstract: Low temperature thermochronology plays a key role in the study of tectonic evolution of the upper crust. The general application of thermal history modelling of apatite fission-track analysis requires both the parameters of the apparent age together with the confined track-length distribution of the spontaneous tracks. However, obtaining length data is relatively easy and does not require either irradiation or LAICP-MS commonly used for determining the uranium content of the grains for age dating. This leads to a shorter laboratory process.For this purpose,based on apatite UTh/He method, this paper attempts to decouple apatite fission-track age from apatite fission-track length,and then combine the lengths with the respective apatite U-Th/He age to model the thermal history. Therefore, experiments were designed and conducted using a new program “Low-T Thermo". Results of this modelling are presented from the following experiments: apatite fission-track age combined with apatite U-Th/He age; apatite fission-track confined track-length distribution plus apatite U-Th/He age.

The modelling precision using this method is related to the relative errors of the apatite U-Th/He ages and the helium diffusion model. This combination of apatite fission-track length and apatite U-Th/He ages has not been implemented before but is presented here as an alternative way of determining thermal histories without the addition of apatite fission-track ages.

Keywords: Thermal history modelling; Apatite U-Th/He; Apatite fission track

# 1 Introduction

Low-temperature thermochronology including fission-track and (U-Th)/He analyses is a widely used tool for investigating tectonics and surface processes. Thermal history modelling is a key component providing a quantitative analysis of the temperature evolution. Generally, the common methods of thermal history modelling are based on a combination of apatite fission-track (AFT) age and confined track- length distributions (e.g. Ketcham et al.， 2000;Ketcham， 2005;Gallagher, 1995,2012; Gallagher et al.,2Oo5). However, obtaining length data is relatively easy and does not require either irradiation or LA-ICP-MS commonly used for determining the uranium content of the grains for age dating. This leads to a shorter laboratory process. For this purpose, based on apatite U-Th/He (AHe) method, this paper attempts to decouple AFT age from AFT length,and then combine AFT lengths with the respective AHe age, in order to model the thermal history and compare these new combinations.

# 2 Thermal history modelling method

Although sophisticated software such as AFTSolve (Ketcham et al., 2OoO), HeFTy (Ketcham, 2005） and QTQt (Gallagher, 2012） have been developed successfully to model thermal histories from fission-track, and U-Th/He analyses, these software are not available for further/secondary development at present. For testing the above ideas and adding new modelling procedures, a new comprehensive Mathematica $\textsuperscript { \textregistered }$ modelling software ("Low-T Thermo") for improving thermal history analysis of fission-track and U-Th/He has been developed. The details of the modelling procedure and algorithms are presented as follows.

# 2.1 Forward modelling

The forward modelling procedure of AFT and U-Th/He in this paper includes four steps.Firstly,the thermal history is discretized into 1OO evenly spaced time steps. Secondly, the reduced length distribution of the confined tracks is calculated for the duration of the thermal history. Thirdly, the modeled lengths are transferred into a fission-track modeled age. Finally helium diffusion is calculated (Flowers et al., 2009) based on the fission-track density and helium diffusion data is transferred into a UTh/He modeled age.

# AFT age and AFT length

The forward modelling procedure of apatite fission-track analysis is similar to that of Ketcham et al. (2OOO) and Ketcham (2Oo5). The fanning curvilinear fit annealing model of Ketcham et al. (2OO7) is used for C-axis projected track-lengths, assuming that ${ \bf r } _ { \mathrm { m r 0 } }$ value is O.83. The equation for C-axis projected track-lengths is from Ketcham et al. (20O7). The initial C-axis projected track length is $1 6 . 6 2 \mu \mathrm { m }$ (Ketcham et al., 2009). We assume a minimum detectable length of $7 . 3 1 \mu \mathrm { m }$ for C-axis projected track-length (Donelick et al.,1999). The assumption of a normal distribution of C-axis projected track-lengths is used at all stages of annealing. The relationship of C-axis projected mean versus standard deviation is （20 $\sigma _ { \mathrm { c , m o d } } = 0 . 0 0 6 1 5 \times { \mathrm { l } _ { \mathrm { c , m o d } } } ^ { 2 } - 0 . 1 7 7 1 9 4 \times { \mathrm { l } _ { \mathrm { c , m o d } } } + 1 . 8 2 9 9 7 5 ^ { \mathrm { ~ ~ c ~ } }$ which is obtained by fitting the data from Carlson et al.(1999) based on the projection model of Ketcham (2007) (Appendix: Ketcham et al., 2OO7). The fission-track modeled age is calculated by the cumulated track density in each time step divided by 0.893 (Ketcham et al., 2O00). The conversion model from fission-track length to density presented by Donelick et al. (1999） is used here. The forward modelled age and AFT length distribution is statistically consistent with HeFTy (Ketcham, 2OO5). The Kolmogorov-Smirnov (K-S) test probability, i.e. p-value (Marsaglia et al., 2Oo3), is calculated based on the C-axis projected confined track-length distribution.

# AHe age

In this paper, the following formula and models were used, including the spherical diffusion equation (Carslaw and Jaeger 1959), Arrhenius formula (Reiners and Brandon, 2006), U-Th/He age calculation formula (Farley, 2Oo2),alpha ejection correction model (Farley et al.，1996) and the radiation damage accumulation and annealing model (RDAAM) for apatite (Parameter set 2 in table 1 in Flowers et al, 2OO9). The finite difference method (Ketcham, 2OO5) was used to calculate U-Th/He modeled age from the thermal history. The forward modeled AHe age is statistically concordant with the AHe modeled age calculated by HeFTy (Ketcham, 2005).

# 2.2 Inverse modelling

In this inverse process,we used the Monte Carlo method to randomly search thermal histories (e.g.，1O,0oO） where time-temperature points are not regularly distributed and can be randomly perturbed.

Using the ages and fission-track length (any combination of AHe age,AFT age, and AFT length) to model the thermal history, the minimum of K-S test p-value and equivalent p-values were taken by assuming the grain ages have a normal distribution $p - \nu a l u e = 1 - \int _ { O - | O - M | } ^ { O + | O - M | } \frac { e ^ { - \frac { ( x - O ) ^ { 2 } } { 2 \sigma ^ { 2 } } } } { \sqrt { 2 \pi } \sigma } d x$ (similar to Ketcham， 2005). Where $O$ is the measured age, $M$ is the modeled age and $\sigma$ is the standard deviation of measured age. The 1o age standard deviation is equivalent to K-S test p-value 0.32.

The mean value of thermal histories was selected within a threshold equivalent pvalue as the result of the thermal modelling. The threshold equivalent p-value can be set as O.5, O.32, O.05 etc.according to the data set.Because the time-step size is variable, each selected thermal history was subdivided into 1OO evenly spaced time steps to calculate the mean temperature value at each time node.

# 3 Synthetic examples

Two synthetic examples are presented. In these examples, a simple cooling model and a reheating model were respectively analysed (Fig. 1) using two defined boxes as geological constraints. All pathways must pass through the boxes and be monotonic between the boxes. The age error (lo) of both AFT and AHe is assumed to be $10 \%$ of the age and surface temperature is $1 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ for every method; the radius of a spherical crystal was set at $1 0 0 \mu \mathrm { m }$ ,and the concentration of both U and $^ { 2 3 2 } \mathrm { T h }$ at $1 0 0 \mathrm { p p m }$ for UTh/He.

![](images/ec67d640dfa320da11a65a901176ee0d289dd61b8c514ac4611bac2aaa0a8906.jpg)  
Fig.1 The input thermal histories and corresponding modeled ages and length distributions.

(a) and (b) represent the input thermal history and corresponding modeled ages and the C-axis projected length distribution in the monotonic model, respectively. (c) and (d) represent the input thermal history and corresponding modeled ages and the length distribution in the reheating model, respectively. The boxes represent the constraint ranges through which all thermal history paths must pass.

Four results are illustrated using the combination of apatite fission-track and UTh/He data sets: a) AFT age and AFT length, b) AHe age and AFT age, c) AHe age and AFT length, d) AHe age and AFT age and AFT length (Fig. 2). All the acceptable thermal histories are within 1o age error.

Above $1 1 0 ^ { \circ } \mathrm { C }$ there is a deviation where there is a separation between the modeled line and the input history, but under $1 1 0 ^ { \circ } \mathrm { C }$ the model results are good and close to the input history. The results show that decoupling the AFT age and AFT length separately combined with AHe age is possible.

![](images/f431984306bfacd8cb7778ef8fca85b38dbb31523564f892629fbff96841c724.jpg)

![](images/64ce773735eafe8b540359ce4488778c308984c2d516d734b5550272e8579ceb.jpg)  
Fig.2 The thermal history modeling comparison of different combinations using AFT age,

AFT length and AHe age for both the monotonic and the reheating models.

All the thermal histories have ${ \geqslant } 0 . 3 2$ p-values (i.e.,within 1o age error).

# 4 Real examples

Examples are now presented to test the different combinations of AFT age,AFT length and AHe age. DB45 from Reiners et al. (2003) and Zhou et al. (2003), JR11-08 from Jiao et al. (2O14) were chosen as test cases. DB45 is located in Tiantangzhai peak, Dabie Mountain， China, which experienced continuous exhumation since the Cretaceous. JR11-O8 is from Ahimanawa Range， central North Island，New Zealand, where the basement rocks were exhumed to shallow depths of the crust in the

Early Cretaceous then followed by reheating before a second exhumation to shallow depths of the crust again.

Their age data are shown in Table 1 and C-axis projected length distributions in Figs. 3 and 4. The thermal histories of the combined AFT age, AHe age and AFT length were used as reference standards. The atmospheric lapse rate is assumed as $6 ~ \mathrm { { ^ \circ C / k m } }$ The present day surface temperature $T _ { s = T _ { s 0 } - \beta } \ X h ,$ where $T _ { s 0 }$ is the surface temperature at sea level, $\beta$ is the lapse rate and $h$ is the elevation.

The results (Figs.3,4） show that 1） both combinations of AFT age with AFT length and AHe age with AFT length are similar to that from the reference model; 2) the modeled temperature error range by combining AHe age with AFT length is smaller than that by combining AFT age with AFT length for DB45. On the contrary, the modeled temperature error range by combining AFT age with AFT length is a little less than that by combining AHe age with AFT length for JR11-08.

Table1.Apatite (U-Th)/He data and apatite fission-track age data   

<html><body><table><tr><td>Sample Name</td><td>Elevation Grain (m)</td><td>No.</td><td>U (ppm)</td><td>Th (ppm)</td><td>FT</td><td>eU</td><td>AHe age (Ma)</td><td>1σ (Ma)</td><td>Relative AFT age error</td><td>(Ma)</td><td>1σ (Ma)</td><td>Relative error</td></tr><tr><td>DB45</td><td>340</td><td>1</td><td>10.5</td><td>3.5</td><td>0.73</td><td>11.32</td><td>22.5</td><td>0.7</td><td>3.11%</td><td>47.4</td><td>6.6</td><td>13.92%</td></tr><tr><td rowspan="3">JR11-08</td><td></td><td>1</td><td>28.3</td><td>64.9</td><td>0.76</td><td>43.55</td><td>25.8</td><td>1.9</td><td>7.36%</td><td></td><td></td><td></td></tr><tr><td>431</td><td>2</td><td>6.5</td><td>15.0</td><td>0.74</td><td>10.03</td><td>15.8</td><td>1.2</td><td>7.59%</td><td>83.9</td><td>5.2</td><td>6.20%</td></tr><tr><td></td><td>3</td><td>24.6</td><td>34.4</td><td>0.72</td><td>32.68</td><td>31.7</td><td>2.4</td><td>7.57%</td><td></td><td></td><td></td></tr></table></body></html>

Note: DB45 is from Reiners et al. (2003) and Zhou et al.(2003),and JR11-08 is from Jiao et al.

![](images/82c885e3afb64ffdfb8707459bea229e21dff56b8dae04e3db419f8a9e393a1e.jpg)  
Fig.3 The thermal history modeling comparison of different combinations using AFT age,

AFT length and AHe age for DB45

All the thermal histories have ${ \geqslant } 0 . 3 2 { \mathfrak { p } }$ -values (i.e.,within1oage error).10,OoO thermal histories are used for the Monte Carlo randomly search. The surface temperature at sea level is $1 5 \mathrm { ^ \circ C }$ . The atmospheric lapse rate is $6 ^ { \circ } \mathrm { C } / \mathrm { k m }$ . The resulting models are very similar to those determined by Reiners et al. (2003) based on the AHe diffusion model(after Wolf et al.,1998) and AFTSolve.

![](images/30bb8031ac848649453442e002cb28cff07e6d4d682d4ccddc4e7ac04000c442.jpg)  
Fig.4 The thermal history modelling comparison of different combinations using AFT age,

AFT length and AHe age of the first grain of JR11-08.

All the thermal histories in Fig.4a and Fig.4c have ${ \geqslant } 0 . 0 5$ p-values.All the thermal histories in Fig.4e have ${ \geqslant } 0 . 0 0 1$ p-values.1Oo,OOO thermal histories are used for the Monte Carlo randomly search. The surface temperature at sea level is $2 0 ^ { \circ } \mathrm { C }$ . The atmospheric lapse rate is $6 ^ { \circ } \mathrm { C } / \mathrm { k m }$ . These models are very similar to those of Jiao et al. (2O14) based on their use of QtQt.

# 5 Discussion

# 5.1 The constraints of AFT age and AHe age on AFT length

How might one estimate the constraints of AFT age and AHe age on AFT length in the thermal history modelling?

Firstly,using DB45 as the example (Fig. 5),one can see the difference of the thermal history modelling using AFT length,AFT age or AHe age respectively.

1) Although the thermal histories using only AFT length scatter on a larger time scale and anneal completely at ${ \bf \Omega } \sim 1 1 0 \mathrm { ~ \Omega ~ } ^ { \circ } \mathrm { C }$ , the length modelling is sensitive to the whole temperature range between the AFT closure temperature and the surface temperature.

2) The thermal histories based separately on AHe age or AFT age intersect at or near the temperature of their partial retention zone (PRZ) or partial annealing zone (PAZ) and at the time of their respective apparent age, suggesting that the age modelling is more sensitive to the temperature of the respective PAZ or PRZ than outside these bounds. Therefore, the thermal history of both the AHe and AFT ages constrain the AFT length thermal history between surface temperature and AFT closure temperature (Fig. 5a, b,c). As expected, the AHe PRZ and AFT PAZ are the most sensitive temperature ranges for constraining AFT length thermal history.

3) For an AHe thermal history model using RDAAM, the temperature range between the AHe and AFT closure temperatures also has an influence on the AHe modeled age (Flowers et al., 2OO9). Therefore, the sensitive temperature range of the

AHe age thermal history modelling using RDAAM includes AHe PRZ and AFT PAZ.

![](images/1dc08c856bd0f26541946ca702d9c5a60e367b8ca400b695ecf1f1d06e027991.jpg)  
Fig.5 The thermal history modelling comparison using AFT length, AFT age or AHe age for

DB45.

All the thermal histories have ${ \geqslant } 0 . 3 2$ p-values (i.e.within 1o age error). 10,OoO thermal histories are used for the Monte Carlo randomly search.The thermal histories using only AFT length scatter and anneal completely at ${ \sim } 1 1 0 \ \mathrm { ~ } ^ { \circ } \mathrm { C }$ . The thermal histories using only AFT age and AHe age cross at their respective partial annealing zones.

Secondly, the differences between the AHe age and AFT age relative errors (Table 1）also result in different constraints on AFT length thermal history modelling. These effects can be seen clearly from Figs 2 and 3. In Fig. 2 the relative errors of AHe age and AFT age are same. Therefore, the temperature error range of AFT age and AFT length thermal histories and that of AHe age and AFT length thermal histories are similar. However, in Fig. 3 the temperature error range of AHe age and AFT length thermal histories is smaller than that of AFT age and AFT length thermal histories because the relative error of the AHe age is smaller than that of the AFT age.

# 5.2 The influence of multiple grain AHe ages

AHe ages are known to frequently have poor reproducibility, so it is generally the practice to measure several grains from a single sample. How would such data be added to thermal history modelling? This is dependent on the helium diffusion model.

If the Durango fluorapatite model (Farley, 2OoO) is used, the age corresponding to a thermal history is constant and the age is not changed with the concentration of both U and $^ { 2 3 2 } \mathrm { T h }$ . Therefore using the mean age of the analysed grains (e.g.,the arithmetic mean age, central age (Vermeesch,2O1O)) as the sample's AHe age, and combined with every grain's U, Th content and the alpha-ejection correction factor $( \mathrm { F _ { T } } )$ each will yield a similar result.

However, if the RDAAM is selected as the helium diffusion model, it is difficult to give a sample's AHe age because the grain's age changes with eU (effective U concentration) and each grain has its own He closure temperature (Flowers et al., 2009). Therefore,the thermal history modelling results of different grains have different thermal sensitive ranges. Furthermore,the joint inversion of multiple grains improves the precision of the thermal history modelling. We use JR11-O8 as a real example to test this viewpoint (Fig. 6).

As shown in Fig. 6, the joint inversion of 3 apatite grains has a more precise thermal history modelling result than any single grain AHe age. Further, the joint inversion of 3 apatite grains together with the AFT length distribution yields the most precise thermal history modelling result (Fig. 6e). It must be noted that an assumption was made that apatite U-Th zonation (Ault and Flowers,2O12)，Bad Neighbours (Gautheron et al., 2O12) and the crystal breakage (Brown et al.,2O13) of all grains in the examples above have no significant influence on the thermal history modeling. The model results (Fig. 6e) are very similar to those determined by Jiao et al. (2O14) based on their use of QtQt.

![](images/a211ad10fb9ed0ba1c6653161538160b6ac96b827c464355789b202cf12f30ee.jpg)

![](images/7426c078bedf0b11567d8403f36bd563094ccfabe606aa8112e883e2ac98cd35.jpg)  
Fig. 6 The thermal history modelling comparison using different AHe grain-age data and confined

track lengths from JR11-O8.a-c JR11-O8 thermal history modelling using grains 1, 2 and 3 respectively; d JR11-O8 thermal history modeling based on combining three AHe grain ages and e, JR11-O8 thermal history modelling based on combining three AHe grain ages and the AFT confined track lengths.All the thermal histories have ${ \geqslant } 0 . 0 5 \mathfrak { p }$ -values.100,000 thermal histories are used for the Monte Carlo random search. The minimum equivalent p-values is taken as the evaluating parameter. The surface temperature at sea level is $2 0 \mathrm { ~ \textdegree C }$ . The atmospheric lapse rate is 6℃/km.

# 5 Conclusion

By testing the combination of AFT ages or AFT confined track lengths with AHe ages, it was determined that the decoupling of the apatite fission-track age and length is acceptable. The combination of AFT length and AHe ages yields results similar to other combinations with examples taken from the literature,and proves to be a very possible alternative method in modelling the data sets for thermal histories. Reconstruction of thermal histories offers more flexibility when AFT ages are not available. It may also act as a test for traditional modelling using the normally accepted procedure using a combination of AFT lengths and age. Certainly, when a higher quality modelling history is needed, both AHe age and AFT age are more recommendable.

# Acknowledgements

This study was supported by the National Natural Science Foundation of China (No.411O2131), the Fundamental Research Funds for the Central Universities of China (No.12lgpy22), Guangdong Natural Science Foundation (No.2015A030313193）) and China Scholarship Council. Diane Seward provided many important constructive suggestions for this paper writing, Shaowen Liu, Matt Sagar also provided reviewing this paper. The program is available through the author.

# References

1) Ault,A.K.,Flowers, R.M.2O12.Is apatite U-Th zonation information necessary for accurate interpretation of apatite (U-Th)/He thermochronometry data? Geochmica et Cosmochimica

Acta, 79(C), 60-78.   
2）Brown, R.W., Beucher, R., Roper, S., Persano, C., Stuart,F., Fitzgerald, P.,2O13. Natural age dispersion arising from the analysis of broken crystals， part I. Theoretical basis and implications for the apatite (U-Th)/He thermochronometer. Geochim. Cosmochim. Acta,   
122(0), 478-497.   
3）Carslaw H., Jaeger J., 1959. Conduction of Heat in Solids. Clarendon Press, Oxford.   
4）Donelick R.A.，Ketcham R.A.， Carlson W.D.，1999. Variability of apatite fission-track annealing kinetics II: Crystallographic orientation effects. American Mineralogist, 84, 1224-   
1234.   
5）Farley K.A., 2Ooo. Helium diffusion from apatite: General behavior as illustrated by Durango fluorapatite. J. Geophys Res.,105, 2903-2914.   
6）Farley K.A.， 2OO2. (U-Th)/He dating: Techniques,calibrations,applications.Rev Mineral Geochem, 47, 819-844.   
7）Farley K.A., WolfR.A., SilverL.T.,1996. The effcts of long alpha-stopping distances on (UTh)/He ages. Geochim Cosmochim Acta, 60, 4223-4229.   
8）Flowers R.M.，Ketcham R.A.， Shuster D.L.， Farley K.A.， 2009. Apatite (U-Th)/He thermochronometry using a radiation damage accumulation and annealing model Geochim. Cosmochim. Acta, 73, 2347-2365.   
9）Gallagher K.,1995.Evolving temperature histories from apatite fission-track data. Earth and Planetary Sci. Lett.,136, 421-435.   
10） Gallagher K.， 2O12. Transdimensional inverse thermal history modelling for quantitative thermochronology. J. Geophys Res., 117(B2):373-393.   
11） Gallagher K.， Stephenson J.， Brown R., Holmes C., Fitzgerald P. 2005. Low temperature thermochronology and modelling strategies for multiple samples 1: vertical profiles. Earth Planet Sci. Letts.,237,193-208.   
12） Gautheron, C. Tassan-Got, L., Ketcham, R.A., Dobson, K.J. 2012. Accounting for long alpha-particle stopping distances in (U-Th-Sm)/He geochronology: 3D modeling of diffusion, Zoning, implantation, and abrasion. Geochmica et Cosmochimica Acta, 96(11): 44-56.   
13）Jiao,R.,D. Seward, T. A. Little,and B.P. Kohn (2014), Thermal history and exhumation of basement rocks from Mesozoic to Cenozoic subduction cycles,central North Island, New Zealand, Tectonics,33,1920-1935.   
14）Ketcham R. A.， Carter A.，Donelick R.A.， Barbarand J. Hurford A.J.， 2O07. Improved modelling of fission-track annealing in apatite. American Mineralogist, 92, 799-810.   
15） Ketcham R.A., Donelick R.A. Donelick M.B., 2000.AFTSolve: a program for multikinetic modelling of apatite fission-track data. Geol. Mater. Res.,2, 1-32.   
16）Ketcham, R.A., Donelick, R.A., Balestrieri, M.-L., and Zattin, M. 2009.Reproducibility of apatite fission-track length data and thermal history reconstruction. Earth and Planetary Science Letters, 284 (3-4), 504-515.   
17） Ketcham R.A., 2O05.Forward and inverse modelling of low-temperature thermochrometry data. Reviews in Mineralogy and Geochemistry, 58 (1), 275-314.   
18） Marsaglia G., Tsang W. W., Wang J. 2003. Evaluating Kolmogorov's Distribution. Journal of Statistical Software,8 (18), 1-4.   
19） Reiners W.P., Brandon M.T., 2O06. Using thermochronology to understand orogenic erosion. Annu Rev Earth Planet Sci, 34, 419-466.   
20） Reiners W.P., Zhou Z.Y., Ehlers T.A., Xu C.H., Brandon M.T., Donelick R. A., Nicolescu S.,   
2003.Post-orogenic evolution of the Dabie Shan, eastern China, from (U-Th)/He and fissiontrack thermochronology. American Journal of Science 3O3, 489-518.   
21） Vermeesch,P.2010, HelioPlot,and the treatment of overdispersed (U - Th - Sm)/He data, Chem. Geol., 271(3-4),108-111.   
22） Wolf,R.A., Farley, K. A., Kass,D.M.,1998,Modeling of the temperature sensitivity of the apatite (U-Th)/He thermochronometer: Chemical Geology,148,105-114.   
23） Zhou Z.Y., Xu C.H., Reiners W.P., Yang FL.,Donelick R.A.,2003.Late Cretaceous-Cenozoic exhumation of Tiantangzhai region of Dabieshan orogen: constraints from (U-Th)/He and fission track analysis. Chinese Science Bulletin, 48 (11), 1151-1156.