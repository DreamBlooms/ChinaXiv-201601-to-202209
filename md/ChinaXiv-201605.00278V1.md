# THELATEST ASSESSMENTFORTHEREPROCESSEDGDRPRODUCT OFHY-2A ALTIMETER

Yalong Liul,Ke Xul\*, Youguang Zhang²,Lei Wangl, Xiyu Xul,Hua Chenl

1 CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing, China 2 National Satellite Ocean Application Service, Beijing, China

# ABSTRACT

This paper is aimed to assess the accuracy of HY-2A altimetry system. To further improve the accuracy and performance of HY-2A observed SSHs, several new treatments including 4 parameters maximum likelihood estimation (MLE4） retracking for Ku and C band,nonparameter sea state bias(NPSSB) model,and reprocessed dual-frequency altimeter ionospheric correction are included The evaluation from dual-crossover comparison of the fully reprocessed level-2 sensor geophysical dataset records (SGDRs） data suggests that the algorithm and model improvements mentioned above give rise to remarkable promotion to the accuracy of the forthcoming version GDRs In this study we conclude that the standard deviation of5.79 cm is achieved from crossover comparison between HY-2A and Jason-2 sea surface height (SSHs)， suggestinga promising situation ofHY-2A altimetry datasets.

Index Terms-HY-2A, Altimeter, Crossover Comparison, GDR Assessment

# 1.INTRODUCTION

The advent of satellite radar altimetry has provided a unique new perspective for monitoring global ocean topography with high frequency which never happened before with the conventional observation techniques such as tidal gauges and ships measuring [1]. The satellite-borne altimetry is qualified as a powerful tool in oceanography and climate change studies,by providing amount of valuable globally distributedoceandynamicobservationswiththe unprecedented precision,which serves a vital function in a range of fields including marine disaster prevention and reduction, ocean resource development and global change etc.[2].Higher requirements are put forward to the quantitative application of the observation in light of furthering and studying of the radar altimeter observed data, and extension of the study field.Nevertheless,the accuracy of altimetry restricts their application.The cross-comparison isthe determination of relative accuracy between the measurements of the different altimeters,which is expressed as the standard deviation of differences of SSHs at crossover points.

TheHY-2A is China'sfirstoceandynamic environment satellite,serving for monitoring of global oceantopography， sealevel, gravityfield,disaster prevention and mitigation,and further the EI Nino forecast. There are more than 3 years datasets acquired since its launch (l6 August 2O11),including sea surface height (SSH),wind field,wave height and water vapor etc.Due to the superior performance,HY-2A altimeter have been incorporated into dataunification and altimeter combination system (DUACS).

# 2.METHODOLOGY

The major measurement of the altimeter is range,while the sea surface height (SSH) is the most concerned parameter to the oceanographer,which can be expressed as:

$$
S S H { = } H { - } R + \Delta R _ { \mathrm { c o r r } }
$$

Where $H$ is the altitude of the altimeter determined by MOE (Medium Orbit Ephemeris),and $R$ is the distance from the altimeter to the nadir sea surface observed by $\mathrm { K u }$ band (C band is less accurate). The $\Delta R _ { \mathrm { c o r r } }$ consist of dry and wet delays,ionospheric corrections,sea state bias,and geophysical effects.The range $\mathrm { ~ R ~ }$ ,can be rewritten as:

$$
\begin{array} { r } { R = R _ { \mathrm { t r a c k e r } } + \Delta R _ { \mathrm { e p o c h } } + \Delta R _ { \mathrm { d o p p l e r } } \qquad } \\ { + \Delta R _ { \mathrm { s y s t e m \_ b i a s } } + \Delta R _ { \mathrm { m o d e l } } } \end{array}
$$

Where $R _ { \mathrm { t r a c k e r } }$ is the raw range obtained from onboard adaptive tracker. $\Delta R _ { \mathrm { e p o c h } }$ is derived from $2 0 \mathrm { { H z } }$ waveform retracking.△Rdopper is the Doppler correction determined by range rate, and $\Delta R _ { \mathrm { { s y s t e m } \_ b i a s } }$ is invariant for side B dada consisting of electronics delay，center of gravity (COG) distance, and $\Delta R _ { \mathrm { m o d e l } }$ is the modeled instrumental correction.

According to equation(1) and (2),all data (corrections) other than H (MOE）and $R _ { \mathrm { t r a c k e r } }$ (onboard value） are reprocessedas table.1.

Corrections are re-calculated to avoid that the improper treatments of previous IGDRs might lead to erroneous conclusions regarding not only the SSHs but also the ancillary measurements made by the satellite (especially here the dual-frequency ionospheric correction).

Table.1altimeterdata treatments   

<html><body><table><tr><td></td><td>HY-2A preocess</td><td>Jason-2 preocess</td></tr><tr><td>H</td><td>MOE</td><td>POE</td></tr><tr><td>R</td><td>Onboard tracker</td><td>GDR-D</td></tr><tr><td>△Repoch</td><td>MLE4</td><td>GDR-D MLE4</td></tr><tr><td>△Rdopper</td><td>Orbit altitude rate</td><td>GDR-D</td></tr><tr><td>△Rsystem bas</td><td>NSSCa</td><td>GDR-D</td></tr><tr><td>△Rmodel</td><td>NSSCa</td><td>GDR-D</td></tr><tr><td>△Rdry</td><td>ECMWF</td><td>ECMWF</td></tr><tr><td>△Rwet</td><td>ECMWF</td><td>ECMWF</td></tr><tr><td>△Ricno</td><td>HY-2A RA</td><td>Jason-2 Poseidon-3</td></tr><tr><td>△Rocean</td><td>TPXO</td><td>TPXO</td></tr><tr><td>△Rload</td><td>TPXO</td><td>TPXO</td></tr><tr><td>△R solid</td><td>Cartwright and Edden</td><td>Cartwright and Edden</td></tr><tr><td>△Rpole</td><td>Wahr</td><td>Wahr</td></tr><tr><td>△Rinverted baro</td><td>ECMWF</td><td>ECMWF</td></tr></table></body></html>

a: determined usingNational Space Science Center(NSSC) algorithm

# 2.1 crossover comparison

The crossover analysis ensures the continuity for multimission. It is essential,in a statistical point of view,to compare observations from different flying altimeters at crossover points.Due to the large number of globally distributed comparison points, the crossover analysis provides reliable assessment for altimeter,given that the reference altimeter is accurately calibrated.

To determine the SSHs,corrections including dry,wet and ionosphere components of troposphere,sea state bias, ocean tide,invertedbarometer,tideloading,earth solid and pole tide effects should be interpolated with at least four observers ( $\mathrm { 1 H z }$ data) in each side of crossover points. Theoretically，the bias between two altimeter observed SSHs at crossover points within relatively short time period is constant,which is not discussed in this paper.We put more weight on the standard deviation of the differences in crossover points to demonstrate altimetry accuracy.

The ionospheric delays vary spatially and temporally, the magnitude order of which can reach O to $5 0 ~ \mathrm { c m }$ .There are several models/algorithms to correct the effect including Bent model, global ionosphere map(GIM),IRI,and dualfrequency correction.Nevertheless,the former three models are less accurate than dual-frequency altimeter derived corrections since these models over-smooth electron content spatially and temporally.To ensure the validity, the HY-2A derived ionospheric corrections are compared with GIM (though less accurate than instrument derived value, however,in a statistical view of point,both of them are consistent).

The dual-frequency ionospheric correction is resulted from difference of ranges (C minus $\mathrm { K u } ^ { \cdot }$ ).Withrespect to HY-2A,Ku and C band share the same onboard tracker, subsequently, the differencesof ranges can be expressed as:

$$
\Delta R = e p o c h _ { \mathrm { C } } + S S B _ { \mathrm { C } } - e p o c h _ { \mathrm { K u } } - S S B _ { \mathrm { K u } }
$$

Where epoch is determined from MLE4 retracking algorithm,and SSB is the error induced by sea state.Dry and wet delays for two bands cancel out each other. Regarding to SSB,two non-parameter SSB models are introduced for $\mathrm { K u }$ and C band respectively.

# 3.DATA

ForHY-2A,SGDRs from1 June 2014 to 14 June 2014 are used,and for the reference mission Jason-2,GDRs(Version D）covering the same period are used.To monitor the performance over the stable surface,additional editing criteria are applied to remove data from swallow waters (bathymetry lessthan $- 1 0 0 0 \mathrm { m } )$ ，area with high ocean variability(oceanvariabilityabove $2 0 \mathrm { c m } )$ ,datafromhigh latitude (greater than $| 5 0 ^ { \circ } | )$ . Moreover,data with time span greater than 3 days are also rejected owing to timedependent surface topography.

# 2.2MLE4 retracking

Retracking is done by computing the departure of the waveform's leading edge from the altimeter tracking gate and correcting the satellite range measurement (and surface elevation） accordingly[3]. In previous version, MLE3 algorithm is used to retrieve epoch and SWH for both Ku and C band.We upgrade the estimator in the new version by using MLE4algorithm.

MLE4 simultaneously retrieves the 4 parameters that can be inverted from the altimeter waveforms:epoch, composite sigma,amplitude and Square of mispointing angle.Among the 4 parameters， epoch determinesthe range and ionospheric correction,composite sigma and amplitude are the indirect inputs for the sea state bias model.

# 2.3 dual-frequency altimeter ionospheric corrections

# 4.RESULTANDCONCLUSION

# 4.1 ionospheric corrections comparison

To ensure the validity and reliability of HY-2A dualfrequency ionospheric corrections. We compared HY-2A and Jason-2 derived ionospheric corrections at crossover pointswithin 3hours(Figure.1 left)， meanwhilewe compared the altimeters derived values with GIM model respectively (Figure.1 center and right).The comparisons suggest the HY-2A dual-frequency derived ionospheric corrections are reliable with a high precision of $0 . 7 5 4 ~ \mathrm { c m }$ and $0 . 5 4 ~ \mathrm { c m }$ compared with GIM model and Jason-2 measured values respectively except that there is a constant bias of $1 . 8 ~ \mathrm { c m }$ (with Jason-2).It is likely that this bias is caused by no calibration for C band yet since launch.

0.02 1000 0.01 rmse: 1.8 cm rmse = 1.695 cm 900 0 rmse = 0.811 cm 400 。 2 s-874 气 350 -0.04 300   
0.02 220   
g -0.05 李 -0.12 150 -0.06 -0.14 200 -0.14 100 -0.07 -0.16 y=0.834x-0.020 100 -0.16 y=0.863 x-0.004 50 -0.08 -0.18 -0.1 -0.08 -0.06 -0.04 -0.02 0 -0.15 -0.1 -0.05 0 -0.15 -0.1 -0.05 0 HY-2A_ALT_iono (m) GIM Corr (m) GIM Corr (m)

# 4.2 accuracy of SSHs from crossover comparison

The differences of SSHs at crossover points between HY2A and Jason-2 have been determined using independent treatments described as table.1.After applying the editing criteria,there are 47O6 values available.The crossover points distributed in figure .2,which indicates that there are no apparent geographically correlated signals in the map. Figure.3 is the histogram of the differences of SSHs at crossoverpoints,whichobeysnormaldistribution suggesting no nonlinear characteristics existed.

![](images/d70ee4813ffcf505345d59e889ac6548275a96fda1d9bde6218eefcdb941d60e.jpg)  
Figure.1Crossovercomparisonofionospericcoections(left:HY-2AvsJason-2;center:GIMvsHY-2A;right:GIMvsJason-2)

The standard deviation of crossover comparison is 5.79 cm ( $6 . 6 \mathrm { c m }$ for the previous version IGDRs)which is agree well with or even more excellent than the results concluded from other missions ( $7 . 5 ~ \mathrm { c m }$ for Mo0re (2002)[4], $6 . 5 \ \mathrm { c m }$ for Cryosat-2 from Labroue (2012)[5],and $6 . 1 5 ~ \mathrm { c m }$ from Dorandeu (2004)[6]).

![](images/c228baa4dc74eba39e8b02a050ec7d6b479ff8c50a64ad0f2cdc89a32815d0f5.jpg)  
Figure.2 Distribution of the differences of SSHs between HY-2A and Jason-2   
Figure.3Histogramof the differences of SSHs between HY-2A and Jason-2

The crossover comparison,which is the classical metrics used to evaluate the system performance in altimetry,is performed between HY-2A and Jason-2 shows that HY-2A has a very good level of accuracy with the standard deviation of $5 . 7 9 \ \mathrm { c m }$ .The result suggests that this is an encouraging achievement,and the fully reprocessed data is ofbetter accuracy than previous ones although the corrections from onboard radiometer has not been applied (6hECMWFand instead).

The statistics manifest that even MOE orbit is accurate enough for using HY-2A for oceanic studiesand applications.All the results confirm that HY-2A provides comparable observationsasthe counterpart Jason-2. Theoretically,there is still room for accuracy improvement and potential for detailing mesoscale structure and global circulation.

# REFERENCES

[1]Chelton,D.B.，et al.，Satellite Altimetry.In Satellite altimetry and earth sciences:A handbook of techniques and

applications,L.L.Fu and A.Cazenave,Editors.2oo1,San Diego:Academic Press.   
[2]Bonnefond,P.，B.Haines,and C.Watson,In situ absolute calibration and validation: a link from coastal to open-ocean altimetry,in Coastal altimetry.2011,Springer. p. 259-296.   
[3] Davis,C.H.A robust threshold retracking algorithm for extracting ice-sheet surface elevations from satellite radar altimeters.in Geoscience and Remote Sensing Symposium, 1996.IGARSS '96.'Remote Sensing for a Sustainable Future.', International. 1996.   
[4]Moore,P.and P.E. Sterlini,Cross-calibrationof TOPEX/Poseidon， ERS-2andGEOSATaltimetry. Advances in Space Research,2002(2).   
[5]Labroue,S.，et al.，First quality assessment of the Cryosat-2 altimetric system over ocean.Advances in Space Research,2012(8).   
[6]Dorandeu,J.,et al., Jason-1 global statistical evaluation andperformanceassessment: Calibrationand crosscalibration results.Marine Geodesy,20o4(3-4).