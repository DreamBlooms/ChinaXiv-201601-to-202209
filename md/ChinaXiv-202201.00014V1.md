# Application of homogenization techniques for inflow transport approximation on light water reactor analysis

Xiang Xiao ', Kan Wang1\* Tong-Rui Yang², Yi-Xue Chen² 1.Department of Engineering Physics, Tsinghua University, Beijing 10oo84,China 2. State Power Investment Corporation Research Institute, Co.Ltd. Beijing 100029, China Corresponding author, xiaoxiang@mail.tsinghua.edu.cn (X. Xiao), wangkan@mail.tsinghua.edu.cn (K. Wang)

# Abstract

The transport cross-section based on inflow transport approximation can significantly improve the accuracy of light water reactor (LWR) analysis, especially for the treatment of the anisotropic scattering effect. The previous inflow transport approximation is based on the moderator crosssection and normalized fission source, which is approximated using transport theory. Although the accuracy of reactivity is increased, the $P _ { 0 }$ flux moment has a large error in the Monte Carlo code. In this study, an improved inflow transport approximation was introduced with homogenization techniques,applying the homogenized cross-section and accurate fission source. The numerical results indicated that the improved inflow transport approximation can increase the $P _ { 0 }$ flux moment accuracy and maintain the reactivity calculation precision with the previous inflow transport approximation in typical LWR cases. In addition to this investigation,the improved inflow transport approximation is related to the temperature factors.The improved inflow transport approximation is flexible and accurate in the treatment of the anisotropic scattering effect, which can be directly used in the temperature-dependent nuclear data library.

Keywords: Inflow transport approximation; Anisotropic scatering effect; Homogenization techniques; Light waterreactor

# 1．Introduction

In light water reactor (LWR) analysis, the anisotropic scattering effect is generally treated by a simplified approximation， such as the transport cross-section (XS） with isotropic scattering approximation from the computational eficiency viewpoint. This approximation has been used in general LWR problems and has reached operational experiences,regardless of its simplicity. However, recent studies suggest that the conventional approximation is inaccurate due to several problems，such as high-leakage，small cores,and fuel assemblies with control rods [1][2]. Therefore,the treatment of the anisotropic scattring effect is important for the recent lattice physics code.

There are three major issues in the treatment of the anisotropic scattering effect. The first is a higher-order scattering matrix.The $P _ { 2 }$ or higher-order scattering matrix is sufficient to maintain calculation accuracy [3]. However, a large amount of memory and a long computing time are required to incorporate the higher-order scatering matrix. The high-order scattering matrix is implemented for the whole-core calculation in the Michigan Parallel Characteristics Transport (MPACT) code [4],and whole-core problems are calculated using the $P _ { 2 }$ scattering approximation. The second is the application of the angular-dependent total cross-section. Multi-group total XS is obtained from angular flux condensation [5][6][7]. Conversely, it employs the time-consuming Monte Carlo code,and it is also very difficult to attain the accurate angular flux.A previous study showed that l6O batches with 1 billion neutrons per tally can reach the converged results [8], which is also an impractical method.The third is the transport approximation for transport XS [9]. It can be used in the $P _ { 0 }$ scattering matrix and is eficient for large-core calculations. Nevertheless, the key point in the inflow transport approximation is the accurate higher-order flux moment from the neutron transport calculation. Yamamoto [2] adopted the typical neutron spectrum for the $\mathbf { P } _ { 0 }$ flux moment, and the higher order flux moment was inversely proportional to the total XS but did not improve the accuracy of reactivity compared to that using the outflow transport approximation. Choi [10] developed an inflow transport approximation from a one-dimensional $P _ { \mathrm { N } }$ transport equation, improving the accuracy in cases of high anisotropic scattering. However, Choi's one-dimensional $P _ { \mathrm { N } }$ transport equation is based on the moderator region and the normalization of the fission source. Although the accuracy of the reactivity calculation in the high anisotropic scattering cases improved， it was approximated with the theoretical model.

Nevertheless,there are many other studies related to the neutron transport problem and crosssection [11][12][13].

In this study， the improved inflow transport approximation was investigated， and its application in different LWR cases was tested. The transport XS was computed by solving the one-dimensional $\mathrm { \Delta P _ { N } }$ transport equation with the homogenized cross-section and accurate fission source，verified through typical LWR cases. The accuracy and application of these transport approximation methods can be determined by comparing the $k$ -infinity, $k$ -effective，and $P _ { 0 }$ flux moments to the reference results. In addition to the inflow transport approximation investigation, the application of the improved inflow transport approximation was tested using different typical LWR cases. Moreover, the results of inflow transport approximations were performed in the lattce code DRAGON5.0.5 [14] and compared to the results of experimental values and Monte Carlo code cosRMC [15]. The numerical results showed that the improved inflow transport approximation can reach a higher accuracy than the previous method for the $P _ { 0 }$ flux moment, and can retain the same accuracy as the previous inflow transport approximation for the reactivity calculation. In addition， the improved inflow transport approximation is only related to the temperature factor through the verification of typical LWR cases. As a result, the improved inflow transport approximation is precise and flexible in the LWR analysis when applied to a temperature-dependent nuclear data library.

The remainder of this manuscript is organized as follows. Section 2 describes the theory and methodology of the different inflow transport approximations.Section 3 explains the discrepancy analysis between these two methods. Section 4 presents the numerical results for the different LWR cases. The conclusions are expressed in Sect. 5.

# 2.Theory and methodology

# 2.1 Previous inflow transport approximation

The previous inflow transport approximation was developed by Choi, which is based on the moderator region and normalized fission source.In this method, the multi-group form of the onedimensional $P _ { \mathrm { { N } } }$ transport equation is derived as follows:

Where

where is the angular flux in group $g$ ，is the cosine angle in the $z$ -direction，is the Legendre polynomial, $l$ is the order of the Legendre polynomial, is the $l .$ -th moment macroscopic XS of $x$ reaction (f: fission, t: total, s: scattering), and is the $l$ -th flux moment.

It should be noted that the distinction between and $( n { = } 1 , 2 \ldots )$ disappears in the absence of self-shielding (i.e., infinity dilution) [16].

The multigroup transport equation in Eq.(1) can be extended using Eqs. (2)-(5),as follows:

Multiplying Eq. (6) by the Legendre polynomial and integratingfrom $^ { - 1 }$ to $+ 1$ , and using the following Bonnet's recursion formula and the orthogonality of the Legendre polynomials:

Inserting Eqs. (7) and (8) into Eq.(6) will lead to the following equation:

Approximating the spatial shape using buckling $B$

Inserting Eq. (1O) into Eq. (9) will produce the following equation:

Additionally, another approximation was introduced for Choi's method. The fission source is forced to normalize,and the value of $k$ is set to 1, leading to:

In Choi's method, Eq. (11) is then converted to the following equation:

Solving Eq. (13), the then leads to the following:

Where the transport XS is written as:

When $n$ is an even number and $n { - } 1$ and $n { + } 1$ are odd numbers.For $n { - } 1$ ：

For $n { + } 1$ ：

Inserting Eqs. (16) and(17) into Eq. (14) leads to the following:

Where

If the order of $n$ is the maximum value，becomes O.For the odd $n$ ，Eq.(14) becomes the following:

The high-order flux moments and $P _ { 0 }$ transport XS are then generated.Furthermore, the $P _ { 0 }$ scatering matrix is calculated using the transport XS,and can be used in the transport computation. Only the corrected diagonal elements are as follows:

The transport equation is related to the geometric value $z$ . It was calculated for a dominated moderator material in each problem case,and showed a problem-dependent result.

# 2.2Improved inflow transport approximation

From the above derivation,a key point in the inflow transport approximation is applying the accurate flux moment from a one-dimensional $P _ { \mathrm { { N } } }$ transport equation,considering the leakage effect and anisotropic scatering effect. This is the same as the assembly homogenization techniques [17]. However, there are two terms (multi-group data and fisson source) that are inconsistent with the theoretical model through the derivation of the previous inflow transport approximation.

When applying the flux shape with buckling $B$ ， the multigroup XS and scattering matrix in Eqs. (3) and (4) become the following:

This shows that applying the flux shape with buckling $B$ eliminates the geometrical value $z$ in the derivation. Therefore, the previous one-dimensional $P _ { \mathrm { N } }$ transport equation becomesa homogenized system. The cross-section and scattering matrix data are homogenized in the entire region, such as fuel, cladding,and moderator regions.

Excluding the homogenized system， the accurate fission source is also treated using homogenization techniques.Therefore,the transport equation in Eq.(11） is replaced by the following:

The solution of flux moment then leads to the following:

Where

When n is an even number and $n { - } 1$ and $n { + } 1$ are odd numbers.

For $n$ -1:

For $n { + } 1$

Inserting Eqs. (30) and (31) into Eq. (27) leads to the following:

Where

If the order of $n$ is the maximum value,becomes O.For the odd $n$ ，Eq.(27) becomes the following:

Therefore, the flux moment and transport XS were obtained using the improved inflow transport approximation. Compared with the form of the previous inflow transport equation, the improved inflow transport equation was based on the homogenization XS and accurate fission source,which is consistent with the homogenization techniques.

# 2.3 Implementation of improved inflow transport approximation

In Choi's parametric study, the inflow transport approximation is insensitive to the buckling and order of the Legendre polynomial. For the value of buckling,even with a ten-fold difference in buckling, the influence of $k$ -effective is less than 2 pcm error. Therefore, the typical buckling value $\scriptstyle B ^ { 2 } = 0 . 0 0 0 1 )$ ）was used for the calculation.For the order of the Legendre polynomial, the $P _ { 1 }$ transport equation is sufficient to calculate the converged ${ \bf P } _ { 0 }$ transport XS,which has the same impact as the $P _ { 5 }$ transport equation [9].

In the improved inflow transport approximation, the typical buckling value and $P _ { 1 }$ transport equation were used.The detailed iteration process is as follows.

(a) Obtain the homogenization data based on the outflow transport approximation in an actual problem. The DRAGON code produces the following homogenization data:

where $i$ is used for every region,mod is the moderator region, $x$ is represented as the reaction (f: fission, t: total, s: scattering),and $n$ is the order of the Legendre polynomial (the anisotropic scattering effect for non-light nuclides is ignored).

(b) Initial flux moments and transport XS.

(c) Update the $P _ { 0 }$ and $P _ { 2 }$ flux moments using Eq. (32),and the flux moments converge.

(d) Update the $P _ { 1 }$ flux moments.

(e) Update the $P _ { 0 }$ transport XS.

(f) Repeat steps (b)-(e) until the flux moments and transport XS converge.

In the above procedure, the flux moments and transport XS may be negative. The iterative equation is as follows:.

where $k$ is the iterative number.

In this study, the investigation focused only on the dominant moderator material $\mathrm { ( H } _ { 2 } \mathrm { O } )$ Therefore, the transport XS for $_ \mathrm { H _ { 2 } O }$ was selected for the improved transport approximation. A detailed discrepancy analysis between these transport approximations is presented in the next section.

# 3.Discrepancy analysis

The typical LWR benchmark was selected in this study to determine the accuracy of these transport approximations. This is the same as the problem Betis Atomic Power Laboratory (BAPL-1) in the WIMS-D Library Update Project (WLUP)[18]. The geometry is shown in Fig. 1, and the material composition is listed in Table 1.The temperature was set to $3 0 0 \mathrm { K }$ for all regions, and the inter-gap was omitted.

Fig.1The geometry ofBAPL-1   
Table 1 The material composition of BAPL-1   

<html><body><table><tr><td>Material</td><td>Nuclide</td><td>Density (atom/barn.cm)</td></tr><tr><td rowspan="2">Moderator</td><td>1H</td><td>6.6760×10-²</td></tr><tr><td>160</td><td>3.3380×10²</td></tr><tr><td>Cladding</td><td>27A1</td><td>4.8994×10²</td></tr></table></body></html>

<html><body><table><tr><td>Fuel</td><td>235U</td><td>3.1120×10-4</td></tr><tr><td rowspan="2"></td><td>238U</td><td>2.3127×10²</td></tr><tr><td>160</td><td>4.6946×10²</td></tr></table></body></html>

Figure 2a shows the transport XS for $_ \mathrm { H _ { 2 } O }$ in three transport approximations: outflow, previous inflow, and improved inflow transport approximation. The outflow transport approximation had a large discrepancy in the thermal and fast energy ranges to the inflow transport approximation. The transport XS for $_ \mathrm { H _ { 2 } O }$ showed a similar tendency between these two inflow transport approximation methods.

![](images/4f63a13468cbac6e2e3ec7892b9d5d9c8d445e937d07ce7b5aaf68ca3815a018.jpg)  
Fig.2(Color online) Comparison of transport XS and normalized $P _ { 0 }$ flux moment in the BAPL-1 case. (a) Transport XS for $_ \mathrm { H _ { 2 } O }$ ; (b) Comparison of normalized $P _ { 0 }$ flux moments in moderator region; (c) Comparison of normalized $P _ { 0 }$ flux moments in the homogenization region

Furthermore,to determine the difference between these inflow transport approximations, a comparison of the ${ \bf P } _ { 0 }$ flux moment is shown in Figs.2b and 2c.The treatment of the fission source and XS were the main differences between these inflow transport approximations.The reference result was obtained using the Monte Carlo code cosRMC,which was developed by Tsinghua University and the State Power Investment Corporation Research Institute (SPIC). Therefore, there are two types of $P _ { 0 }$ flux moment comparisons in this study.

1. The comparison in the moderator region.   
(a) Normalized fission source $^ +$ moderator XS (previous method). (b)Accurate fission source $+$ moderator XS.   
(Reference results: cosRMC's $P _ { 0 }$ flux moment in the moderator region) 2. The comparison in the homogenized region.   
(a) Normalized fission source $^ +$ homogenized XS.   
(b) Accurate fission source $+$ homogenized XS (improved method). (Reference results: cosRMC $P _ { 0 }$ flux moment in the homogenized region)

In Fig. 2b, the normalized $P _ { 0 }$ flux moment in the previous inflow transport approximation is significantly different from the cosRMC code. For the moderator system， the $P _ { 0 }$ flux moment changed with different fission sources.When adopting the normalized fission source, the $P _ { 0 }$ flux moment became more difficult than the accurate fission source.In Fig.2c,the normalized $P _ { 0 }$ flux moment in the improved inflow transport approximation agrees well with the cosRMC code. For the homogenized system, the $\mathbf { P } _ { 0 }$ flux moment also changed with different fission sources,which had the same tendency as the moderator system. Moreover, for the same fission source with different XS cases, the homogenized XS lead to a $1 \ \mathrm { M e V }$ decrease in the $P _ { 0 }$ flux moment and was closer to the LWR system [19],but the $P _ { 0 }$ flux moment in the moderator XS was different. Therefore, the inflow transport approximation, with an accurate fisson source and homogenized XS,can improve the accuracy of the $P _ { 0 }$ flux moment compared with that using the previous method.

# 4.Numerical results

# 4.1 General description of verification

The latice code DRAGON5.0.5 was used for verification. It was developed by Ecole Polytechnique de Montréal for lattice calculations,solving the neutron transport equation with a deterministic approach,and can read different types of multi-group libraries,such as the versions of WIMS-D and MATXS.In this study, the WIMS-D 70 library[20] based on ENDF/B-VI1.0 [21] was selected to study the influence of the anisotropic scattering effect. Different transport approximations are implemented in the WIMS-D 7O library through the transport XS and scattering matrix. Resonance self-shielding is an equivalence theory (SHI+LJ+LEVEL2) with the generalized Stamm'ler method [22],Livolant and Jeanpierre normalization factor, and Riemann integration [23]. The neutron transport calculation method was the interface current method (SYBILT). cosRMC was used as the reference code. The results of the $k$ -infinity, $k$ -effective, and $P _ { 0 }$ flux moments are compared for various verification problems.

# 4.2 Typical LWR fuel cell and fuel assembly cases

A typical LWR fuel cell and fuel assembly were used to verify the application of different transport approximations.The factors of the fuel cell, fuel assembly, boron concentration, fuel enrichment, control rod material,and temperature in the fuel assembly with a control rod were selected as verification cases.

# Fig.3(Color online) Geometry shape of 1A(left) and 2A(right)

The single fuel cell and $1 7 \times 1 7$ fuel assembly benchmark were extracted from problem-1A and 2A in VERA [24],which contained $3 . 1 \ \mathrm { w t \% } \ \mathrm { U O } _ { 2 }$ fuel, $0 . 7 4 3 \ { \mathrm { g / c c } }$ moderators with a $1 { , } 3 0 0 ~ \mathrm { p p m }$ boron concentration，and $\mathrm { Z r  – 4 }$ for cladding. The temperature was $3 0 0 \mathrm { ~ K ~ }$ for all regions. The geometric shapes for 1A and 2A are shown in Fig. 3,and a detailed description of each case is given in Table 2.

Table 3 shows the $k _ { \mathrm { i n f } }$ results for each case with different transport approximations. Compared with the $k _ { \mathrm { i n f } }$ in cosRMC, the $k _ { \mathrm { i n f } }$ error in DRAGON for inflow transport approximations was less than 100 pcm. Contrarily, the error of $k _ { \mathrm { i n f } }$ in DRAGON for outflow transport approximation was less than $1 0 0 \ \mathrm { p c m }$ in the fuel cell and fuel assembly, but could cause approximately 15O to 250 pcm in fuel assembly with the control rod. This discrepancy is consistent with that of previous research [9].

Table2Detailed descriptionof each case   

<html><body><table><tr><td>Cases</td><td>Description</td><td>235U w/0</td><td colspan="3">Temperature (K)</td><td colspan="2">Moderator</td></tr><tr><td></td><td></td><td></td><td>Fuel</td><td>Clad</td><td>Mod</td><td>g/cm³</td><td>ppm</td></tr><tr><td>1A</td><td>fuel cell</td><td>3.1</td><td>300</td><td>300</td><td>300</td><td>0.743</td><td>1300</td></tr><tr><td>2A</td><td>fuel assembly</td><td>3.1</td><td>300</td><td>300</td><td>300</td><td>0.743</td><td>1300</td></tr><tr><td>2H-typical</td><td>fuel assembly+24 B4C</td><td>3.1</td><td>300</td><td>300</td><td>300</td><td>0.743</td><td>1300</td></tr><tr><td>2H-0 ppm</td><td>2H-tyical+0ppm</td><td>3.1</td><td>300</td><td>300</td><td>300</td><td>0.743</td><td>0</td></tr><tr><td>2H-4.8%</td><td>2H-tyical+4.8 %</td><td>4.8</td><td>300</td><td>300</td><td>300</td><td>0.743</td><td>1300</td></tr><tr><td>2G</td><td>fuel assembly+24 AIC</td><td>3.1</td><td>300</td><td>300</td><td>300</td><td>0.743</td><td>1300</td></tr><tr><td>2H-600 K</td><td>2H-tyical+600 K</td><td>3.1</td><td>600</td><td>600</td><td>600</td><td>0.743</td><td>1300</td></tr></table></body></html>

Compared with the $k _ { \mathrm { i n f } }$ in the previous inflow transport approximation, the results of the improved transport approximation were less than $1 0 \ \mathrm { p c m }$ in cases 1A and 2A. Moreover, the results of the improved transport approximation were underestimated by 11 to $4 9 \ \mathrm { p c m }$ for 2Htypical, $2 \mathrm { H } \mathrm { - } 0 \ \mathrm { p p m }$ $2 H { - } 4 . 8 \%$ ,and 2G,and was also overestimated by 46 pcm for $2 \mathrm { H } \mathrm { - } 6 0 0 \mathrm { ~ K ~ }$ . This tendency indicates that the transport approximations have less influence on the fuel cell and fuel assembly, but they have some effect on the fuel assembly with control rod cases.For the $3 0 0 ~ \mathrm { K }$ cases, the application of homogenization techniques in the improved transport approximation is based on the homogenous XS and accurate fission source,considering the influence of the resonance self-shielding effect in fuel materials. Compared with the previous inflow transport approximation， the improved transport approximation can absorb neutrons in different cases, which finally decreases the $k _ { \mathrm { i n f } }$ results.During the $6 0 0 ~ \mathrm { K }$ case,the impact of the resonance selfshielding efect was weakened in the improved inflow transport approximation with an increase in temperature [25],leading to an increase in $k _ { \mathrm { i n f } }$ compared to that in the previous transport approximation.

Table3Results of $k _ { \mathrm { i n f } }$ in different cases   

<html><body><table><tr><td rowspan="2">Case</td><td rowspan="2">cosRMC</td><td colspan="3">DRAGON</td></tr><tr><td>Method1</td><td>Method2</td><td>Method3</td></tr><tr><td>1A</td><td>1.20116</td><td>1.20037</td><td>1.20033</td><td>1.20038</td></tr><tr><td rowspan="3">2A</td><td>(±30 pcm)</td><td>(-80 pcm)</td><td>(-83 pcm)</td><td>(-78 pcm)</td></tr><tr><td>1.19391</td><td>1.19404</td><td>1.19405</td><td>1.19407</td></tr><tr><td>(±30 pcm)</td><td>(13 pcm)</td><td>(14 pcm)</td><td>(16 pcm)</td></tr><tr><td rowspan="2">2H-typical</td><td>0.81444</td><td>0.81571</td><td>0.81422</td><td>0.81393</td></tr><tr><td>(±31 pcm)</td><td>(127 pcm)</td><td>(-22 pcm)</td><td>(-51 pcm)</td></tr><tr><td rowspan="2">2H-0 ppm</td><td>0.89927</td><td>0.90174</td><td>0.89999</td><td>0.89973</td></tr><tr><td>(±32pcm)</td><td>(247 pcm)</td><td>(72 pcm)</td><td>(46 pcm)</td></tr><tr><td rowspan="2">2H-4.8 %</td><td>1.00206</td><td>1.00419</td><td>1.00260</td><td>1.00211</td></tr><tr><td>(±31 pcm)</td><td>(213 pcm)</td><td>(54 pcm)</td><td>(5 pcm)</td></tr><tr><td rowspan="2">2G</td><td>0.87892</td><td>0.88044</td><td>0.87893</td><td>0.87882</td></tr><tr><td>(±29 pcm)</td><td>(152 pcm)</td><td>(1 pcm)</td><td>(-10 pcm)</td></tr></table></body></html>

<html><body><table><tr><td>2H-600 K</td><td>0.78723 (±27 pcm)</td><td>0.78956 (233 pcm)</td><td>0.78720 (-3 pcm)</td><td>0.78766 (43 pcm)</td></tr></table></body></html>

\*Method1:outflow transport approximation；Method2:previous inflow transport approximation； Method3: improved inflow transport approximation

![](images/33432cf5adff4a65a2f5ac21f757f5b55c63e924547d9b0a890201a5279374e0.jpg)  
Fig.4(Color online) Comparison of normalized ${ \bf P } _ { 0 }$ flux moment with the previous method.(a) 1A fuel cell; (b) 2A fuel assembly; (c) 2H-typical fuel assembly with $\mathrm { B } _ { 4 } \mathrm { C }$ ；(d) 2H-0 ppm fuel assembly with $\mathrm { B } _ { 4 } \mathrm { C }$ at $0 \ : \mathrm { p p m }$ ; (e)2H（204号 $4 . 8 \%$ fuel assembly with $\mathrm { B } _ { 4 } \mathrm { C }$ in $4 . 8 \%$ fuel enrichment; (f) 2G fuel assembly with AIC；(g $) 2 \mathrm { H } \mathrm { - } 6 0 0 \mathrm { K }$ fuel assembly with $\mathrm { B } _ { 4 } \mathrm { C }$ in $6 0 0 \mathrm { K }$ （204号

As a result, the different inflow transport approximations reached a higher accuracy than the outflow transport approximation in reactivity calculations,and the error of $k _ { \mathrm { i n f } }$ was less than 50 pcm for different inflow transport approximations.

Figures 4 and 5 show the comparison of the normalized $P _ { 0 }$ flux moment with different inflow transport approximations for these cases. Specifically, compared with the results of cosRMC, the $P _ { 0 }$ flux moment in the improved inflow transport approximation had a better agreement than the previous method. Furthermore, the $P _ { 0 }$ flux moment of the previous inflow transport approximation was slightly overestimated by approximately $1 \ \mathrm { M e V }$ and underestimated in the thermal energy range. Particularly, the previous inflow transport approximation made the $P _ { 0 }$ flux moment more difficult than the improved method.

In addition to the above investigation， the results of the improved inflow transport approximation in different LWR cases were in good agreement with the cosRMC, which is more versatile than the previous method. It can achieve higher accuracy for the cases of the fuel cell, fuel assembly， different boron concentrations， fuel enrichment, control rod material,and temperature in fuel assembly with the control rod.Therefore,the improved inflow transport approximation is accurate,universal, and suitable for LWR analysis.

![](images/33a2777bf3dca179b9daf4ac085dc31f208baface910384664317c036b7b5f74.jpg)  
Fig.5(Color online) Comparison of normalized ${ \bf P } _ { 0 }$ flux moment in the improved method. (a) 1A fuel cell; (b) 2A fuel assembly; (c) 2H-typical fuel assembly with $\mathrm { \Delta B _ { 4 } C }$ ; (d)2H-0 ppm fuel assembly with $\mathrm { B } _ { 4 } \mathrm { C }$ at $0 \mathrm { p p m }$ ; (e)2H$4 . 8 \%$ fuel assembly with $\mathrm { B } _ { 4 } \mathrm { C }$ in $4 . 8 \%$ fuel enrichment; (f) 2G fuel assembly with AIC; (g) $2 \mathrm { H } \mathrm { - } 6 0 0 \mathrm { K }$ fuel assembly with $\mathrm { B } _ { 4 } \mathrm { C }$ in $6 0 0 \mathrm { K }$ ：   
Fig.6(Color online) Macroscopic transport XS (left) and relative error (right) of 2A for $_ \mathrm { H } _ { 2 } \mathrm { O }$ (a) Results of previous inflow transport approximation; (b) Results of the improved inflow transport approximation.

# 4.3Analysisof influence factors

In a previous investigation, the inflow transport approximation was problem-dependent. However, transport approximations are problem-independent data in most nuclear data libraries. Hence,we need to study the influence of the transport approximation and produce a nuclear data library with a general transport approximation.

Figure 6 shows the macroscopic transport XS and relative error of 2A for $_ \mathrm { H } _ { 2 } \mathrm { O }$ in the different inflow transport approximations. The macroscopic transport XS for $_ \mathrm { H } _ { 2 } \mathrm { O }$ was similar in most LWR cases,but the biggest difference existed in the thermal energy group in the $6 0 0 \mathrm { ~ K ~ }$ case. The relative error of transport XS in the $6 0 0 ~ \mathrm { K }$ case was approximately $30 \%$ to $40 \%$ in the 2A case in the different inflow transport methods, but was less than $20 \%$ in other cases.Therefore, the most significant factor influencing inflow transport approximations is temperature through the comparison of transport XS.

Moreover, for the previous inflow transport approximation, the transport XS was based on the moderator region,and its relative error to 2A was less than $1 \%$ with the same moderator XS. Therefore, the previous inflow transport approximation was only related to the moderator region. For the improved inflow transport approximation， the transport XS was based on the homogeneous system, and its relative error to 2A was over $5 \%$ in $0 . 2 8 \ \mathrm { e V }$ to $2 7 . 7 \mathrm { e V } .$ Specifically, in a homogeneous system, the resonance self-shielding effect for fuel and absorber nuclides was considered in the derivation of transport XS. Then, the neutron spectrum was changed according to the diferent nuclide density ratios in the fuel and absorber nuclides.Thus,the transport XS in the improved inflow transport approximation was different from the previous inflow method, which is consistent with the actual LWR model.

The transport XS had a strong correlation with temperature and had less difference in the different LWR operation factors, such as fuel assembly, boron concentration,fuel enrichment, and control rod materials in the fuel assembly with the control rod.There are two different WIMS-D 70-group libraries, based on the improved inflow transport approximation, to test the influencing factors of transport approximations.The first is a problem-dependent library. The transport XS and scattering matrix data for $\mathrm { ^ { 1 } H }$ and $^ { 1 6 } \mathrm { O }$ are problem-dependent,which are developed by the improved inflow method in actual cases. The second is a problem-independent library. The transport XS and scatering matrix data for H-1 and O-16 are problem independent, developed by the improved inflow method, from the typical 2H case $( \mathrm { B } _ { 4 } \mathrm { C } , 3 0 0 \mathrm { K } , 1 , 3 0 0 \mathrm { p p m } ,$ and $3 . 1 ~ \mathrm { w t \% }$ ）

Table 4 shows the results of the $k _ { \mathrm { i n f } }$ in the improved transport approximation. Compared to the $k _ { \mathrm { i n f } }$ results between the problem-dependent and problem-independent libraries, the $k _ { \mathrm { i n f } }$ error was less than $2 0 \mathrm { p c m }$ for most cases.However, the $k _ { \mathrm { i n f } }$ error was 37 pcm for the 2H case at $6 0 0 ~ \mathrm { K }$ This indicates that the inflow transport approximation considering fuel and absorber nuclides has less influence on $k _ { \mathrm { i n f } }$ calculations, but the factor of temperature can influence the $k _ { \mathrm { i n f } }$ results. This is consistent with the difference in the transport XS in Fig. 6. Although the largest difference of transport XS was in the resonance energy range, the magnitude of transport XS in the resonance energy range was comparatively smallr than the thermal energy range, and its influence on the $k _ { \mathrm { i n f } }$ error was less than $2 0 ~ \mathrm { p c m }$ in each case. Therefore, the improved inflow transport approximation is only related to the temperature factor,and it can be easily implemented in a temperaturedependent nuclear data library.

Table 4 Results of $k _ { \mathrm { i n f } }$ in improved inflow transport approximatiol   

<html><body><table><tr><td rowspan="2">Cases</td><td rowspan="2">cosRMC</td><td colspan="2">DRAGON5.0.5</td></tr><tr><td>Dependent</td><td>Independent</td></tr><tr><td rowspan="2">2H(typical)</td><td>0.81444</td><td>0.81393</td><td>0.81393</td></tr><tr><td>(±31 pcm)</td><td>(-51 pcm)</td><td>(-51 pcm)</td></tr><tr><td rowspan="2">1A</td><td>1.20116</td><td>1.20038</td><td>1.20040</td></tr><tr><td>(±30 pcm)</td><td>(-78 pcm)</td><td>(-76 pcm)</td></tr><tr><td rowspan="2">2A</td><td>1.19391</td><td>1.19407</td><td>1.19408</td></tr><tr><td>(±30 pcm)</td><td>(16 pcm)</td><td>(17 pcm)</td></tr><tr><td rowspan="2">2H(0 ppm)</td><td>0.89927</td><td>0.89973</td><td>0.89967</td></tr><tr><td>(±32 pcm)</td><td>(46 pcm)</td><td>(40 pcm)</td></tr><tr><td rowspan="2">2H(4.8 wt%)</td><td>1.00206</td><td>1.00211</td><td>1.00231</td></tr><tr><td>(±31 pcm)</td><td>(5 pcm)</td><td>(25 pcm)</td></tr><tr><td rowspan="2">2G(AIC)</td><td>0.87892</td><td>0.87882</td><td>0.87880</td></tr><tr><td>(±29 pcm)</td><td>(-10 pcm)</td><td>(-12 pcm)</td></tr><tr><td rowspan="2">2H(600K)</td><td>0.78723</td><td>078766</td><td>0.78729</td></tr><tr><td>(±27 pcm)</td><td>(43 pcm)</td><td>(6 pcm)</td></tr></table></body></html>

# 4.4 Application of inflow transport approximation to core cases

The Babcock & Wilcox (B&W） critical experiment benchmarks [26] selected to verify the application of different transport approximations in core cases.The B&W 1484 core l and core 3 cases are selected in this section,and the geometry shape is given in Fig.7.The B&W 1484 core 1 is the $4 8 { \times } 4 8$ case,and the B&W 1484 core 3 is the $6 8 \times 6 8$ case.

Table 5 shows the results of the B&W 1484 core 1 and core 3 cases (2D and 3D). The results indicated that the outflow transport approximation can introduce an error of over $1 { , } 0 0 0 \ \mathrm { p c m }$ in these cases,and both inflow transport methods were close to the reference values.For the B&W 1484 core 1 (2D and 3D) cases, the results of $k _ { \mathrm { i n f } }$ in the improved inflow transport approximation were overestimated by approximately $3 6 4 ~ \mathrm { p c m }$ and 291 pcm,respectively.For the B&W 1484 core 3 (2D and 3D) case, the results of $k _ { \mathrm { i n f } }$ in the improved inflow transport approximation were overestimated by approximately $1 1 5 \ \mathrm { p c m }$ and $1 2 1 \ \mathrm { p c m }$ ，respectively. The $k _ { \mathrm { i n f } }$ error in the B&W 1484 core 1 and core 3 cases was inversely proportional to the cases of the LWR assembly. In addition, the different transport approximations were sensitive to the small core cases, which can cause over $1 { , } 0 0 0 \ \mathrm { p c m }$ for the $k _ { \mathrm { i n f } }$ calculations in core 1 and approximately $6 0 0 \mathrm { p c m }$ in core 3.

Although the previous inflow method is close to the reference results, the improved inflow method is close to the actual system, which is consistent with the theoretical model.The reason for this tendency may come from the limitation of the WIMS-D library， such as ignorance of scattering resonance integral, lumped fission spectrum, etc.

In summary, the outflow transport approximation can introduce an error of over $1 { , } 0 0 0 \ \mathrm { p c m }$ in the B&W 1484 core l and core 3 cases, but the inflow transport methods are relatively accurate in the core cases.

![](images/636451b1659a1f2cae56048f9835173951a5c44c4480999c6dc4ee401c184eea.jpg)  
Fig.7(Color online) Geometry shape of B&W 1484 Core 1 (left) and Core 3 (right)

Table5Results of $k _ { \mathrm { i n f } } / k _ { \mathrm { e f f } }$ in B&W1484 Core1and Core 3   

<html><body><table><tr><td rowspan="2">Case</td><td rowspan="2">CosRMC/ Experiment</td><td colspan="3">DRAGON</td></tr><tr><td>Method1</td><td>Method2</td><td>Method3</td></tr><tr><td>Core 1(2D)</td><td>1.01270</td><td>1.02851</td><td>1.01198</td><td>1.01562</td></tr><tr><td rowspan="2">Core 1(3D)</td><td>(±30 pcm)</td><td>(1581 pcm)</td><td>(-72 pcm)</td><td>(292 pcm)</td></tr><tr><td>1.00020</td><td>1.01387</td><td>0.99765</td><td>1.00076</td></tr><tr><td rowspan="2">Core 3(2D)</td><td>（）</td><td>(1367 pcm)</td><td>(-235 pcm)</td><td>(56 pcm)</td></tr><tr><td>1.01630</td><td>1.02800</td><td>1.02183</td><td>1.02298</td></tr><tr><td rowspan="2">Core 3(3D)</td><td>(±30 pcm)</td><td>(1170 pcm)</td><td>(553 pcm)</td><td>(668 pcm)</td></tr><tr><td>1.00000 (-)</td><td>1.01331 (1331pcm)</td><td>1.00725 (725 pcm)</td><td>1.00846 (846 pcm)</td></tr></table></body></html>

\*Method1: outflow transport approximation; Method2: previous inflow transport approximation; Method3: improved inflow transport approximation

# 5.Conclusion

In this study, the improvement and application of inflow transport approximation in LWR analysis were performed by comparing the results of the $P _ { 0 }$ flux moment, $k _ { \mathrm { e f f } } ,$ and $k _ { \mathrm { i n f } }$ with the reference results.The improved inflow transport approximation was based on the homogenized cross-section and accurate fission source, which was different from the previous method.

For the LWR assembly cases, the results of three transport approximations (outflow, previous inflow,and improved inflow) were compared for the cases of the fuel cell, fuel assembly, boron concentration, fuel enrichment, control rod materials,and temperature in the fuel assembly with a control rod. The $k _ { \mathrm { i n f } }$ error in the inflow transport approximation was less than 1oo pcm compared to that in the Monte Carlo code cosRMC,which was more accurate than the outflow transport approximation in the treatment of the anisotropic scattering effect. Compared to the $\mathrm { ~ P ~ } _ { 0 }$ flux moment, the results of the improved inflow transport approximation were closer to the cosRMC code in each case.The homogenized cross-section and accurate fission source were the main factors influencing the ${ \bf P } _ { 0 }$ flux moment. In addition to the above investigation,the improved inflow transport approximation is only related to the temperature factor for typical LWR cases. Excluding the temperature case, the $k _ { \mathrm { i n f } }$ error was less than 2O pcm between the problemdependent and problem-independent transport approximations. For the B&W 1484 core cases, the outflow transport approximation introduced an error of over $1 { , } 0 0 0 \ \mathsf { p c m }$ . The inflow transport approximation significantly improved the $k _ { \mathrm { i n f } }$ accuracy, and the results were closer to the reference value.

In summary, the improved inflow transport approximation is more flexible and accurate in the treatment of the anisotropic scatering effect, and it can be easily implemented in the temperaturedependent nuclear data library forLWR analysis.

# Author contributions

All authors contributed to the study conception and design. Material preparation, data collection and analysis were performed by Xiang Xiao, Kan Wang, Tong-Rui Yang, and Yi-Xue Chen. The first draft of the manuscript was written by Xiang Xiao and all authors commented on previous versions of the manuscript. All authors read and approved the final manuscript.

Funding This work was supported by the National Key R&D Program of China(2017YFC0307800-05).

# Reference

1. J.Rhodes,K. Smith, D. Lee, CASMO-5 development and applications. Paper presented at the Proceedings of PHYSOR 2006 ANS Topical Meeting, (Vancouver, Canada, 2006)   
2. A. Yamamoto, Y. Kitamura, Y. Yamane, Simplified treatments of anisotropic scatering in LWR core calculations. J. Nucl. Sci. Technol. 45(3)， 217-229(2008). htps://doi: 10.1080/18811248.2008.9711430.   
3. K. S. Kim, M. L. Williams, D. Wiarda et al., Development of a new 47-group library for the CASL neutronics simulators, Paper presented at the Mathematics and Computations, Supercomputing in Nuclear Applications and Monte Carlo International Conference, (Nashville,America,2015)   
4. B.Kochunas,B. Collins,D. Jabaay, et al., Overview of development and design of MPACT: Michigan parallel characteristics transport code，Paper presented at the International Conference on Mathematics and Computational Methods Applied to Nuclear Science and Engineering,(San Francisco,America, 2013)   
5．N.A. Gibson,Dissertation, Novel Resonance Self-Shielding Methods for Nuclear Reactor Analysis (Massachusetts Inst. Technol., America, 2016). http://dspace.mit.edu/handle/1721.1/103658.   
6. W. Boyd, N. Gibson,B.Forget et al.,An analysis of condensation errors in multi-group cross section generation for fine-mesh neutron transport calculations.Ann. Nucl. Energy 112, 267- 276(2018). https://doi: 10.1016/j.anucene.2017.09.052.   
7. L.X.Liu, C Hao, Y.L. Xu, Equivalent low-order angular flux nonlinear finite difference equation ofMOCtransportcalculation. Nucl. Sci. Tech.， 31， 125(2020). https://doi.0rg/10.1007/s41365-020-00834-2.   
8. B.R.Herman, B. Forget, K. Smith et al.， Improved diffusion coefficients generated from Monte Carlo codes. Paper presented at the International Conference on Mathematics and Computational Methods Applied to Nuclear Science and Engineering， (San Francisco, America,2013)   
9. G. Bell, G. Hansen, H. Sandmeier, Multitable Treatments of Anisotropic Scattering in S N Multigroup Transport Calculations. Nucl. Sci. Eng. 28(3)，376-383(1967). htps://doi: 10.13182/nse67-2.   
10. S.Choi, K. Smith, H. C.Lee, et al., Impact of inflow transport approximation on light water reactor analysis. J. Comput.Phys. 299， 352-373(2015). https://doi: 10.1016/j.jcp.2015.07.005.   
11. Z.X. Fang, M Yu, Y.G. Huang, et al., Theoretical analysis of long-lived radioactive waste in pressurized water reactor. Nucl. Sci. Tech. 32, 72 (2021). https://doi.0rg/10.1007/s41365-021- 00911-0.   
12. M Dai， M.S. Cheng， Application of material-mesh algebraic collapsing acceleration technique in method of characteristics-based neutron transport code. Nucl. Sci. Tech.32, 87 (2021). https://doi.0rg/10.1007/s41365-021-00923-w.   
13. G.C. Zhang,J Liu, L.Z. Cao,et al.， Neutronic calculations of the China dual-functional lithium-lead test blanket module with the parallel discrete ordinates code Hydra. Nucl. Sci. Tech. 31,74(2020). https://doi.0rg/10.1007/s41365-020-00789-4.   
14. R. Roy. G. Marleau,A. Hebert, User guide for dragon version 5: Technical Report IGE 335. (Ecole Polytechnique de Montréal, Canada, 2014)   
15. K. Wang, Z. G.Li, D She, et al., RMC - A Monte Carlo code for reactor core analysis. Ann. Nucl. Energy 82,121-129(2013). https://doi: 10.1016/j.anucene.2014.08.048.   
16. R. E. MacFarlane and D. W. Muir, The NJOY Nuclear Data Processing System, LA-12740- M. (Los Alamos National Laboratory, America 1999)   
17. A. Hebert, Applied Reactor Physics,(Ecole Polytechnique de Montréal, Canada,2009)   
18. D. L. Aldama, F. Leszczynski, and A. Trkov, WIMS-D Library Update, Paper presented at the Final Rep. a Coord. Res.Proj. (IAEA,Austria,2003), http://www.pub.iaea.org/MTCD/Publications/PDF/te_1468_web.pdf#page=22.   
19. K. S. Kim, M. L. Williams, D. Wiarda, et al., Development of the multigroup cross section library for the CASL neutronics simulator MPACT: Method and procedure. Ann. Nucl. Energy 133,46-58(2019). http://doi: 10.1016/j.anucene.2019.05.010.   
20. M. Edenius, K. Ekberg,B.H. Forssen, et al., CASMO-4,A Fuel Assembly Burnup Program, User's Manual. (Studsvik Am. Inc, 1995)   
21．M.B.Chadwick，P. Oblozinsky，M. Herman，et al.，ENDF/B-VI.0: Next Generation Evaluated Nuclear Data Library for Nuclear Science and Technology. Nucl.Data Sheets107(12), 2931-3060(2006). https://doi: 10.1016/j.nds.2006.11.001.   
22. A.Hebert, G. Marleau, Generalization of the Stamm'ler method for the self-shielding of resonant isotopes in arbitrary geometries. Nucl. Sci. Eng. 108(3),230-239(1991). htps://doi: 10.13182/NSE90-57.   
23.A. Hebert，Revisiting the Stamm'ler self-shielding method. Paper presented at the Conference: 25th CNS Annual Conference,(Toronto, Canada, 2004)   
24. A. T. Godfrey, VERA core physics benchmark progression problem specifications,(Oak Ridge National Laboratory, America,2014). https://doi: 10.1111/codi.12168.   
25.D.Lee,K. Smith, J. Rhodes,The impact of 238U resonance elastic scattering approximations on thermal reactor Doppler reactivity. Paper presented at the Int. Conf. Phys. React. 2008, PHYSOR 2008, (Interlaken, Switzerland, 2008)   
26.G.S. Hoovler，M.N. Baldwin，R.L. Eng et al.， Critical Experiments Supporting Close Proximity Water Storage of Power Reactor Fuel. Nucl. Technol. 51(2),217-237(1980). https:/doi: 10.13182/nt80-a32604.