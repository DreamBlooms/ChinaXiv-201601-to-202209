# THE LARGE SKY AREA MULTI-OBJECT FIBER SPECTROSCOPIC TELESCOPE QUASAR SURVEY:QUASARPROPERTIESFROMTHEFIRSTDATARELEASE

Y. L. A12, XUE-BING WU1.3, JINYI YANG1,3, QIAN YANG13,FEIGE WANG13,RUI GUO1.3, WENWEN ZUO4, XIAOYI DONG1,   
Y.-X. ZHANG,H-L. YUAN’,Y.-H. SONG’,JIANGUO WANG7, XIAOBO DONG67,M.YANG, H. -WU,S.-Y. SHEN4,JR. ${ \mathrm { S H I } } ^ { 5 }$ B.-L. $\mathrm { H E } ^ { 5 }$ ,Y.-J. $\boldsymbol { \mathrm { L E I } } ^ { 5 }$ ,Y.-B. $\mathrm { L I } ^ { 5 }$ , A.-L. LUO5, Y.-H. ZHAO5, AND H.-T. ZHANG5 1Department of Astronomy,School of Physics,Peking University,Beijing 100871, China;aiyl@pku.edu.cn 4Shanghai AtroocalsetoryhseAademyofiecesnga 5KeyLaboratoOiltrotiatroaetoieadeofecee Yunnan Observatories, Chinese Academ of Sciences,Kunming 650011, China 7KeyLaboratoryforthe StructureandEvolutionofCelestialObjects,ChineseAcadeyofSciences,Kunming 650China Received 2015 April17;accepted 2015 November 4;published 2016 January 22

# ABSTRACT

We present preliminary results of the quasar survey in the Large Sky Area Multi-Object Fiber Spectroscopic Telescope (LAMOST)first data release (DR1),which includes the pilot survey and the first year of the regular survey.There are 3921 quasars reliably identified,among which 118O are new quasars discovered in the survey. These quasars are at low to median redshifts,with a highest $z$ of 4.83.We compile emission line measurements around the $\boldsymbol { \mathrm { H } \alpha }$ $, \mathrm { H } \boldsymbol { \beta } , \mathrm { M g } \mathrm { I }$ I, and C Iv regions for the new quasars. The continuum luminosities are inferred from SDSS photometric data with model fiting,as the spectra in DRlare non-flux-calibrated.We also compile the virial black hole mass estimates，with flags indicating the selection methods,and broad absorption line quasars.The catalog and spectra for these quasars are also available. Of the 3921 quasars, $28 \%$ are independently selected with optical-infrared colors,indicating that the method is quite promising for the completeness of the quasar survey. LAMOST DR1 and the ongoing quasar survey wil provide valuable data for studies of quasars.

Key words: catalogs - quasars: general - surveys Supporting material:FITS file,machine-readable and VO table

# 1.INTRODUCTION

A huge effort has been undertaken to find quasars since the first one was discovered in 1963 (Schmidt 1963).The most distant quasar, $z ~ = ~ 7 . 0 8 5$ ，was identified by the United Kingdom Infrared Telescope (UKIRT）  Infrared Deep Sky Survey (UKIDSS； Mortlock et al. 2011). Quasars，with accretion onto their central supermassive black holes,emit a broad range of electromagnetic waves，from radio to $\gamma$ -ray (Antonucci 1993). They can be one hundred times brighter than their host galaxies.Quasars are important extragalactic objects in astrophysics that are used to map black hole growth (e.g.. Kollmeier et al. 2OO6) and to probe the galaxy evolution and intergalactic medium (e.g.,Hennawi & Prochaska 2OO7;Ross et al. 2009).

Quasars can be selected from stellar and normal galaxies in different wavelength ranges, from radio to $\gamma$ -ray,based ontheir distinguished spectral energy distribution,huge luminosity,and variations.The highest yields of quasars are from the Sloan Digital Sky Survey (SDSS; e.g., Shen et al. 2O11; Paris et al. 2012).The Two-Degree Fields survey (2dF) has also identified a large sample of quasars (Boyle et al. 20OO).Both SDSS and 2dF select quasar candidates mainly based on multi-color ultraviolet (UV)/optical photometric data,i.e.,UV excess (Fan et al. 2000； Richards et al. 2002， 2004， 2009； Smith et al.2Oo5).The completeness and efficiency of this selection are higher at redshifts less than 2,but drop significantly at $2 . 2 \leqslant z \leqslant 3 . 5$ ，the range in which the peak of the quasar luminosity function is reached (Fan 1999;Richards etal. 2002 2006；Schneider et al. 2OO7). The efficiency can be improved by combining the quasar selections based on the variability (Graham et al. 2014;MacLeod et al. 2011;Wu et al. 2011; Palanque-Delabrouille et al. 2011; Morganson et al. 2014), for which multi-epoch data are required.

The infrared survey is promising in its potential for finding quasars at high redshifts and improving the completeness and efficiency of quasar surveys at low and median redshifts.More quasars are identified with the UKIDSS survey (e.g.，Warren et al. 2000;Croom et al. 2001; Sharp et al. 2002；Hewett et al.2006;Chiu et al. 2007;Maddox etal.2008,2012; Smail et al.2OO8),and other studies are explored to select quasar candidates with SDSS/UKIDSS colors (e.g.,Wu & Jia 2010). Compared to the limited survey area of UKIDSS,the all sky survey Wide-field Infrared Survey Explorer(WISE;Wright et al.2O1O; Cutri et al. 2O12) data release shines more light on quasar surveys.Wu et al.(2O12） proposed criteria for quasar candidate selectionswith SDSS/WISE colors. With this method they detected an ultra-luminous quasar at a redshift of 6.3 (Wu et al. 2015).

Recently,data-mining algorithms have been applied to the search for quasar candidates. These methods have been exploited in the SDSS-III Baryon Oscillation Spectroscopic Survey (BOSS；Ross et al. 2O12)，including an extreme deconvolution method (XDQsO;Bovy et al. 2011),a kernel density estimator (KDE； Richards et al. 2004，2009)，a likelihood method (Kirkpatrick et al.2O11)，and a neutral network method(Yéche et al. 2010).Peng et al.(2012) also developed a classification system based on a support vector machine (SVM).Generally，different selection methods are combined to reach a higher completeness in quasar sky surveys.

The Large Sky Area Multi-Object Fiber Spectroscopic Telescope (LAMOST） is the Chinese multi-fiber telescope. Some quasar candidates,selected by optical-infrared colors, have been identified during the commission survey phase ( $\mathrm { \Delta W u }$ et al. 201O). The LAMOST regular survey began in 2012,and there were $\sim 7 0 { , } 0 0 0$ quasar candidates observed before 2013 June,as released in the LAMOST first data release.These objects are selected with several quasar selection methods.In this paper we describe the LAMOST quasar survey and candidate selections in Section 2.Spectral measurements and black hole mass estimations for the new quasars are described in Sections 3 and 4，respectively. Section 5 presents the description of the quasar catalog. Section 6 is the discussion. We use a $\Lambda$ -dominated cosmology with $h = 0 . 7$ ， $\Omega _ { m } = 0 . 3$ and $\Omega _ { \Lambda } = 0 . 7$ throughout the paper.

# 2.SURVEY OUTLINE

LAMOST is a reflecting Schmidt telescope with an effective aperture of $4 \mathrm { m }$ .It is equipped with 4OOO fibers that can be deployed across a $5 ^ { \circ }$ (diameter） field of view. The spectral resolution is $R \sim 1 8 0 0$ over the wavelength range from 3800 to $9 1 0 0 \mathring { \mathrm { A } }$ ，which is divided into red and blue spectroscopic channels. Two arms of each spectrograph cover this wavelength range with an overlap of $2 0 0 \textup { \AA }$ . The blue spectral coverage is $3 7 0 0 { \overset { \circ } { \mathrm { A } } } \sim 5 9 0 0 { \overset { \circ } { \mathrm { A } } }$ ,and the red is $5 7 0 0 \mathring { \mathrm { A } } \sim \mathring { 9 } 0 0 0 \mathring { \mathrm { A } }$ (Cui etal.2O12; Zhao et al. 2012). The raw data were reduced with LAMOST two-dimensional pipelines， including bias subtraction,cosmic-ray removal, spectral tracing and extraction,wavelength calibration,flat fielding,and sky subtraction (Luo et al. 2012).

LAMOST began a pilot survey in 2011 October and a regular survey in 2O12 September.The regular survey,carried out over five to six years,has two major components: the LAMOST Experiment for Galactic Understandingand Exploration (LEGUE) and the LAMOST Extragalactic Survey (LEGAS; Zhao et al. 2012).LEGAS only uses a small part of the available observing time due to the limitations of the LAMOST site, especially the bright sky background and poor seeing.The first data release (DR1） contains spectra taken before 2O13 June (Luo et al. 2015). In this paper we present the results of the quasar survey from LEGAS,while the quasars discovered in the vicinity of the Andromeda and Triangulum galaxies in LEGUE are presented in Huo et al. (2013).

# 2.1. Target Selections

The main objective of the LEGAS quasar survey is to discover more new quasars.Most candidates are selected based on SDSS photometry,of which the objects are required to be point sources in SDSS DR9(Ahn et al.2O12) and brighter than $i = 2 0$ .The SDSS point-spread function (PSF) magnitudes are usedwith the Galactic extinctioncorrected(Schlegel et al.1998). A bright magnitude limit, $i = 1 6 . 0$ ，is required to avoid saturation and cross-talk in the spectra. The primary targets are selected based on the following.

1.Optical-infrared colors.The investigations of quasar selection based on SDSS-UKIDSS/WISE colors are described in Wu & Jia(201O)and $\mathrm { w } _ { \mathrm { u } }$ et al. (2012). These quasar candidates are selected based on their locationsin multi-dimensionalSDSSopticaland UKIDSS/WISE infrared color space.In the LAMOST quasar survey，those selected SDSS point sources are

matched with UKIDSS/Large Area Survey (LAS) DR88 and the WISE All-Sky Data Release within a positional offset of $3 ^ { \prime \prime }$ and $6 ^ { \prime \prime }$ ,respectively. Only sources flagged as unaffected by known artifacts in all of the four bands are considered in the WISE catalog. The SDSS magnitudes referred to in the following are in AB magnitudes and the UKIDSS/WISE magnitudes are in Vega magnitudes.For the SDSS-UKIDSS matched objects we select quasar candidates with the criteria of $Y - K > 0 . 4 6 ( g - z ) + 0 . 8 2$ or $J - K > 0 . 4 5 ( i - Y - 0 . 3 6 6 ) + 0 . 6 4$ (Wu&Jia 2010).For the SDSS-WISE matched objects the quasar candidate selection criteria in the regular survey are $w 1 - w 2 > 0 . 5 7$ or $z - w 1 > 0 . 6 6 ( g - z ) + 2 . 0 1$ (Wu et al.2012). These selections mostly select quasars with redshift less than 4. 2.Data-mining algorithms. A combination of quasar selections with data-mining methods: SVM classifiers (SVM; Peng et al. 2O12),extreme deconvolution method (XDQSO;Bovy et al. 2O11)，and a KDE (Richards et al. 2009).

The primary sample described above was supplemented by the objects selected via multi-wavelength (optical-X-ray/radio) data matching,i.e.,objects which have SDSS photometry in the X-ray sources of XMM-Newton，Chandra,and ROSAT and radio sources in FIRST (Becker et al.1995） and NVSS (Condon et al. 1998).Among the above selected candidates there are known quasars in SDSS,and we include some of these known quasars in the LAMOST quasar survey.With the SDSS spectra of these known quasars we can test the calibrations of LAMOST spectroscopy and investigate the spectroscopic variability of quasars.Finally，the LAMOST quasar survey also includes a small number of quasars selected using serendipitous methods.

# 2.2. Spectroscopy

LAMOST LEGAS spectroscopic observations are taken in a series of at least three 3O minute exposures.There are 70,290 quasar candidates observed,with 82,625 spectra in DR1. Among them,there are ${ \sim } 1 0 { , } 0 0 0$ objects identified as QSO, STAR,or GALAXY by the LAMOST pipeline，while the remaining majority, $\sim 6 0 { , } 0 0 0$ ，areclassified as UNKNOWN. For some of these UNKNOWN,the spectra are taken under non-photometric conditions,i.e., varying seeing and/or cloudy Unstable efficiency for some fibers also contributes to the high fraction of UNKNOWN.The other factor is that the magnitude cutoff at $i = 2 0$ for quasar candidate selection is too faint for the LAMOST LEGAS survey. In Figure 1 we present the SDSS i-band PSF magnitude distributions of the observed quasar candidates.It is clear that the mean magnitude of these UNKNOWN, $i = 1 9 . 0 9$ ,is around one magnitude fainter than that of the identified QSO/STAR.The median signal-to-noise ratio $( \mathsf { S } / \mathsf { N } )$ per pixel in the wavelength regions of 4Oo0-5700 and $6 2 0 0 { - } 9 0 0 0 { \overset { \circ } { \mathrm { A } } }$ of LAMOST spectra are also shown in the figure.Most of these UNKNOWN have spectra with relatively lower $\mathtt { S } / \mathtt { N }$ compared to QSO/STAR.

![](images/aa7efcda4488c3dca40c953adedca5c512a30fcc29382b03ce2eca04eedc7aff.jpg)  
Figure 1.Distributions of the $\mathsf { S } / \mathsf { N }$ ofLAMOST spectra and SDSS i-band PSF magnitudes for the objects classified as UNKNOWN(black) and QSO/STAR (red) from the pipeline in the LAMOST LEGAS survey.

For the ${ \sim } 1 0 { , } 0 0 0$ identified QSO/STAR we visually inspect the spectra to confirm the identifications with the Java program ASERA (Yuan et al. 2O13). The misclassified objects are rejected or re-classified according to the $\mathsf { S } / \mathsf { N }$ .For quasars we only keep the spectra with at least one high $\mathtt { S } / \mathtt { N }$ emission line to ensure the reliability of systematic redshift estimations.The visually inspected redshift is set by eye at the maximum of the available typical quasar emission lines,i.e., [O Ⅲ],Mg I, C III, and $\mathrm { C w }$ . If the redshift provided by the pipeline does not match theone estimatedinASERA,wemanuallycorrecttheredshift given by the pipeline,when the spectrum has at least two emission lines available.

Finally, there are 3921 quasars and 5355 stars with reliable identifications as secured in ASERA.The highest redshift of the identified quasar is 4.83 and most of the quasars are at low to median redshift with redshifts less than 3,as shown in Figure 2.The drop in the redshift distribution at $z \sim 1 . 0$ is from inefficient identifications in this redshift range as the emission line of $\mathbf { M g } \mathbf { \pi } _ { \mathrm { f } }$ moves into the overlaps of the blue and red channels.

Among the visually secured LAMOST quasars there are 2741 previously known quasars as matched with NED/SDSS DR10.For $9 5 \%$ of them the redshift differences between SDSS and LAMOST are less than O.1.For the objects with redshift differences larger than O.2 we visually checked the SDSS and LAMOST spectra. The differences come from incorrect estimations of redshifts in LAMOST due to low $\mathtt { S } / \mathtt { N }$ of the spectra or misidentifications of the emission lines.Time lags between LAMOST and SDSS spectroscopic observations range from months to decades,which are suitable to study quasar variability on both short and long timescales.In the DR1 LAMOST release the spectra were non-flux-calibrated. Thus it is much more applicable to study line profile variabilities of quasars,instead of flux variations. In Figure 3 we present LAMOST and SDSS spectra as examples of quasars with consistent redshifts,including the one with the highest redshift $\mathit { \check { z } } = 4 . 8 3 \$ ）identifiedbyLAMOST.

The main purpose of this paper is to compile a catalog for the 1180 new quasars discovered inLAMOST DR1.The redshifts and i-band absolute magnitudes for these quasars are shown in Figure 4.Here luminosity is indicated using the (continuum and emission line）K-corrected,i-band absolute magnitude,

![](images/a946655b793c0e676e23f78e031f98fb147d6ae6d098515b5146166cd44abf7c.jpg)  
Figure 2.Redshift distributions of the reliably identified 3921 quasars in LAMOST DR1.

$M _ { i } ( z = 2 )$ ，normalized at $z = 2$ (Richards et al. 2006).In the following we present detailed descriptions about the emission line measurements and black hole mass estimations for these quasars.

# 3.SPECTRALMEASUREMENTS

We measure the properties of the $\mathrm { H } \alpha , \mathrm { H } \beta , \mathrm { M g } \mathrm { u }$ ，and C Iv lines with spectral fittings. These lines are the typical strong emissionlinesof quasarsandarecalibratedasvirialblackhole mass estimators. The fits are based on the MPFIT package (Markwardt 2009),which performs $\chi ^ { 2 }$ minimization using the Levenberg-Marquardt technique.Details of the spectral fitting in the optical and near-ultraviolet regions have been described in the literature (e.g., Dong et al. 2OO8; Wang et al. $2 0 0 9 \mathrm { a }$ ;Ho et al.2O12).The crossover between the red and blue channels, the wavelength range of $5 7 0 0 { - } 6 2 0 0 \mathring \mathrm { A }$ in observed frame,is masked out. All the LAMOST spectra are corrected for Galactic extinction using the extinction map of Schlegel et al. (1998）and the reddening curve of Fitzpatrick (1999). The spectra are shifted back to their rest frames in the fitting.

For each line we first fit a local pseudo-continuum,i.e.,a simple power law or a power law plus an Fe Ⅱ multiplet emission,to the wavelength regions least contaminated by the broad line emission.The pseudo-continuum fitting windows for eachline are referred to thoseusedin Shen et al.(2O11).The parameters of normalization $\alpha$ and slope $\beta$ of the power-law continuum are set as free.The parameters of the Fe I multiplet emissions,i.e.，normalization，velocity shift relative to the systemic redshift,and broadeningvelocity,are also set as free. The fitted pseudo-continuum emission is subtracted from the spectra and the leftover emission-line spectra are fitted with Gaussian and/or Gaussian-Hermiteprofiles. Belowwe describe the detailed fitting procedures for each line.

$$
3 . I . \ H \alpha \ a n d \ H \beta
$$

We fit the spectra of quasars with $z \lesssim 0 . 3 0$ for $\mathrm { H } \alpha$ and $z \lesssim 0 . 7 5$ for $\mathrm { H } \beta$ . The fitting windows of the power law plus Fe Il emission are [6000, 6250] $\mathring \mathrm { A }$ and $[ 6 8 0 0 , \dot { 7 } 0 0 0 ] \mathring { \mathrm { A } }$ for $\mathrm { H } \alpha$ and[4435,4700]A and [5100,5535]A for $\mathrm { H } \beta$ 、The template of optical Fe Ⅱ emission is from Véron-Cetty et al. (2OO4).A Gaussian function is used to model the emission lines.Both $\mathrm { H } \alpha$ and $\mathrm { H } \beta$ emission lines are modeled with one narrow and one broad component. The broad component is fitted with as many Gaussians as statistically justified (see Dong et al. 2OO8 for details).All of the narrow emission lines except the [O I] doublet are fitted with a single Gaussian.The upper limits of the FWHM for the narrow lines are set to be $1 2 0 0 \ \mathrm { k m \ s ^ { - 1 } }$

![](images/ef099fb81a5b32b403ede338e1bd67656acad2e26f87e9424af396ab499ea0c7.jpg)  
Figure3xasfddo SDSS,and all the spectra are smoothed with a boxcar of 5 pixels for ilustration.

![](images/8115b3e412bd3b59c642180ef2585fab5ccdb45be7ad7b471677b0c41be8e7c4.jpg)  
Figure 4.Distributions of the new quasars discovered in LAMOST DR1 in luminosity-redshift space,where the left panel shows the luminosity histograms.

Eachline of the [O]入入4959,5007 doubletis modeled with two Gaussians,one accounting for the line core and the other for a possible blue wing as seen in many objects (e.g., Greene & Ho 2005a,Komossa et al. 2008,Wang et al.2009b). The doublet is assumed to have the same redshifts and profiles, with the flux ratio fixed to the theoretical value of 3. Velocity offsets and line widths of the doublet core component are tied to those of the narrow $\mathrm { H } \beta$ component. The velocity offsets and linewidthsof [N1] $\lambda \lambda 6 5 4 8$ ，6584 and[SⅡ]入λ6717,6731 are tied to those of the $\mathrm { H } \alpha$ narrow component. The relative flux ratio of the two $[ \mathsf { N } \mathrm { I I } ]$ components is fixed to 2.96.We present the fittings to $\mathrm { H } \beta$ and $\mathrm { H } \alpha$ lines in Figure 5 as illustrations.

# 3.2. Mg I and $C _ { I V }$

We fit the spectra of quasars with $0 . 4 0 \lesssim z \lesssim 1 . 7 6$ for the Mg Iline, and $\bar { z } \gtrsim 1 . 5 8$ for $\mathbf { C } _ { \mathrm { { I V } } }$ .The pseudo-continuum fitting windows are [2200,2700] $\mathring \mathrm { A }$ and $[ 2 9 0 0 , 3 0 9 0 ] \mathring { \mathrm { A } }$ for $\mathbf { M g } _ { \mathrm { { I I } } }$ and [1445,1465]A and [1700,1705] $\mathring \mathrm { A }$ for $\mathrm { { C r } }$ .Theultraviolet Fe Itemplate from Tsuzuki et al. (2OO6） is included in the continuum modeling of $\mathbf { M g } \operatorname { I I }$ ，but not for $\mathrm { C } _ { \mathrm { I V } }$ .Thisismainly because Fe I emission is usually not strong for $\mathrm { { C } _ { \mathrm { { I V } } } }$ ，and inclusion of Fe I emission will add uncertainties to the fitted parameters based on the data quality ofLAMOST.

Each of the Mg Ⅱ 入入2796，2803 doublet components are modeled with one narrow and one broad component. The narrow component is modeled with a single Gaussian,and the upper limit of FWHM is set to be $9 0 0 \mathrm { k m } \mathrm { s } ^ { - 1 }$ (Wang et al.2Oo9a).We model the broad component with a truncated five-parameter Gauss-Hermite series (van der Marel & Franx 1993;see also Salviander et al. 2OO7). The broad components of the $\mathbf { M g }$ I doublet lines are set to have the same profile,with flux ratio set to be between 2:1 and1:1 (Laor et al.1997). The same prescription is applied to the narrow components.For C Iv we model the line with one Gaussian and one GaussianHermite function to obtain a smooth realization of the line profile.We do not set an upper limit for the FWHM of the Gaussian function since there are still debates on whether a strong narrow component exists for the Civline (Baskin & Laor 2005). We present the fittings to $\mathbf { M g } \mathbf { \pi } _ { \mathrm { i I } }$ and $\mathbf { C } _ { \mathrm { { I V } } }$ lines in Figure 6 as illustrations.

The fittings to $\mathbf { M g } \mathbf { \pi } _ { \mathrm { i I } }$ and C Iv emission lines are frequently affected by narrow or broad absorption features.The effects on the fittings from the broad absorption trough are hard to reduce in the automatic fitting procedure,while the impact of narrow ormoderate absorption featurescan be alleviated(Shen et al. 2011). We mask out $3 \sigma$ outliers below the 2O pixel boxcar-smoothed spectrum to reduce the effects of narrow or moderate absorptions on the Civ and Mg I emission line fittings.

![](images/a5bdc47879be3b55f6d46964d4f9bbef1ad696b8418f1ab75149d3b50fd32d3e.jpg)  
Figure 5.Representative example of the fiting applied to the $\mathrm { H } \beta + [ \mathrm { O } \mathrm { m } ]$ and $\mathrm { H } \alpha + [ \mathrm { N } \mathrm { \scriptsize ~ I I } ]$ ranges.The upper panel is the observed spectrum; middle panels show the psedootiidulsef deblending procedures applied to $\mathrm { H } \beta + [ \mathrm { O \ m } ]$ and $\mathrm { H } \alpha + [ \mathrm { N } \mathrm { \scriptsize ~ I I } ]$ emission lines,in which the combination of models (red) and individual components (blue)are shown. The observed spectra are smoothed with a boxcar of 5 pixels for the illustration.

# 3.3.Reliability of Spectral Fittings

We visually inspect the fitting results for each object. Most of the fits to the spectrum with high $\mathtt { S } / \mathtt { N }$ are acceptable,as shown in Figures 5 and 6.The bad fits include spectra with low $\mathrm { { } } S / \mathrm { { N } }$ ,too few good pixels in the fitting region, or objects with peculiar continuum and emission line properties,such as broad absorption line quasars and disk emitters.A flag is given for each line based on visual inspections to indicate the quality of the spectral fitting. $\mathrm { F l a g } = 0$ means that the fitting is acceptable and the inferred parameters are mostly reliable,while flag $= - 1$ means that the line measurements may be spurious.

# 4.CONTINUUMLUMINOSITYANDVIRIAL BLACKHOLEMASS

We fit the five-band SDSS photometry with model spectra to estimate the continuum luminosity for the new quasars.In the first step we extract SDSS PSF magnitudes for only the quasars that have clean photometry9 in the SDSS database.The Galactic extinction corrected SDSS ugriz magnitudes are converted to the corresponding magnitudes on the AB system.1° These AB magnitudes are then turned into the flux density, $F _ { \lambda }$ atthe effective wavelengthof each filter.We then fit the five data points, $F _ { \lambda } ,$ of each quasar at rest frame with model spectra composed of two components: continuum emission and line emission. The features of these two components are referred to those of the composite quasar spectra in Vanden Berk et al.(2OO1,hereafter VBO1).As described in VBO1 the continuum of composite quasar spectra is well fitted by broken power laws,and the features left after the subtraction of the continuum in the median composite quasar spectra are taken as the template of line emission in our model.

In our fitting，the indices of the broken power law and normalization of line emission are set as free parameters. The break of the two power laws is set to the value of $4 6 6 1 \mathring \mathrm { A }$ which is similar to the value inferred from median composite spectra in VBO1.The normalization of the continuum is tied to the mean value of the total emission in the regions of

![](images/de5c41242ef4b3ce810330af48835c9e07b748cee165b3f710499a89a923da06.jpg)  
Figure 6. Representative example of the fitting applied to $\mathbf { M g }$ I and C iv lines.The upper panel is the observed spectrum; middle panels show the pseudo-continuum ftinie applied to $\mathbf { M g }$ IandCemsioscbaifelsdalpotsueareosdsetraeoi a boxcar of 5 pixels for the illustration.

1350-1365 and $4 2 0 0 { - } 4 2 3 0 \mathring \mathrm { A }$ . The values of these two regions are taken from VBO1，in which they fit the continuum. Blueward of $\mathrm { L y } \alpha$ we only scale the composite median quasar spectra. The fitting is performed by minimizing the chisquared, $\chi ^ { 2 }$ ：

Wepresent examples of the modeling in Figure 7.As shown in the figure,the continuum model of quasars with $z \gtrsim 1$ is actually a single power law since for these quasars the value of the break of the two power laws,set in our model, moves out of the LAMOST wavelength region.For these quasars the degrees of freedom (dof) is 2,which is one more than that of the quasars with $z < 1$ . The mean frequency power-law index inferred from the fitting, $\left. \alpha _ { \nu } \right.$ ,is $- 0 . 4 3$ from ${ \sim } 1 3 0 0$ to $4 6 6 1 \mathring { \mathrm { A } }$ and $- 1 . 6 0$ redward of ${ \sim } 4 6 6 1 \mathring { \mathrm { A } }$ ，which are in good agreement with the values found in composite quasar spectra in VB01.

The distribution of the reduced chi-squared, $\chi _ { \nu } ^ { 2 }$ ,is shown in Figure 8.In the figure we mark the values of the reduced chisquared, $\chi _ { \nu , 0 . 0 5 } ^ { 2 } .$ thatcorrespondtoaprobabilityof0.05of obtaining a value $\chi _ { \nu } ^ { 2 } > \chi _ { \nu , 0 . 0 5 } ^ { 2 }$ The $\chi _ { \nu , 0 . 0 5 } ^ { 2 }$ is 3.841 with dof of 1and 2.996 with dofof2.Theftingswithx2<e good fits in the statistical significance level.However, not all of the fits with relatively larger $\chi _ { \nu } ^ { 2 }$ are unacceptable based on visual inspections.In Figure 8 we also present the distribution of the fraction of continuum emission accumulated in the data fitting wavelength range (from only a rest-frame wavelength of $1 2 0 0 \mathring { \mathrm { A } }$ if the data extend blueward ofLyα).The fractions of continuum emission are mostly in a range greater than $60 \%$ ， dispersed around the values $( 8 4 \% - 8 8 \% )$ of those in VB01.The fractions with extremely high values are mostly derived from the quasars with bad fitting.In a loose constraint we reject the fittings with fraction values greater than 0.989.

With the inferred continuum luminosity, i.e., $L _ { 5 1 0 0 } , \ L _ { 1 3 5 0 }$ and $L _ { 3 0 0 0 }$ ,and corresponding broad line width we can estimate the virial black hole masses with

$$
\begin{array} { r } { \log \biggr ( \frac { M _ { \mathrm { B H } } } { M _ { \odot } } \biggl ) = \alpha + \beta \log \biggr ( \frac { \lambda L _ { \lambda } } { 1 0 ^ { 4 4 } \mathrm { e r g } \mathrm { s } ^ { - 1 } } \biggl ) } \\ { + \gamma \log \biggr ( \frac { \mathrm { F W H M } } { \mathrm { k m } \mathrm { s } ^ { - 1 } } \biggl ) . \qquad } \end{array}
$$

The coefficients $\alpha , \beta ,$ and $\gamma$ are empirically calibrated and the values differ in the calibrations with different measurements of emission lines and samples (e.g.，McLure & Dunlop 2004; Greene & Ho $2 0 0 5 \mathrm { b }$ ；Vestergaard & Peterson 2006；Wang et al. $2 0 0 9 \mathrm { a }$ ; Zuo et al. 2015). In this paper for $\mathrm { H } \beta .$ -based and C iv-based estimates we use the virial black hole mass calibrations from Vestergaard & Peterson (2Oo6)，and for Mg I-based from Wang et al. (2OO9a).The FWHM of broad Mg II $\lambda 2 7 9 6$ and the FWHM of the whole $\mathbf { C } _ { \mathrm { { I V } } }$ emission are used in the estimations following the FWHM definitions adopted in these calibrations. The black hole masses are estimated only for those quasars with both inferred continuum luminosity and broad line widths flagged as reliable.

![](images/51f174e080b620c49d52424c15f97c505c6af9637e7537f668cf28db95e22e34.jpg)  
Figure7Eo oower law continuum (blue dashed lines) are shown.

![](images/5f26dffbc2934c20bf132902732d843c951db2c0bb0ce82d44d2036e1de8b1b5.jpg)  
Figure 8.Distribution of reduced chi-squared, $\chi _ { \nu } ^ { 2 }$ ，and flux ratio of the continuum to total emission in the data fitting range.Red points are the quasars with $z < 1$ ,and blue points are the rest. The vertical dashed lines label the values of 3.841 and 2.996 of $\chi _ { \nu , 0 . 0 5 } ^ { 2 }$ whichcoespondtoaprobabilityof005 of obtaining a value $\chi _ { \nu } ^ { 2 } > \chi _ { \nu , 0 . 0 5 } ^ { 2 }$ with dof of 1 and 2.

We note that the continuum luminosity estimations described above introduce additional uncertainties to the black hole mass estimations compared to those from single-epoch spectra. The uncertainties come from model fitting to the SDSS photometric data and intrinsic variations of quasar luminosity.Time lags between SDSS photometric data and LAMOST spectra are ${ \sim } 1 0$ years.On this timescale the optical/ultraviolet emissions of quasars are variable with amplitudes of $0 . 1 \mathrm { - } 0 . 2 \mathrm { m a g }$ (e.g., Vanden Berk et al. 2004; Zuo et al. 2012; Ai et al. 2013). To justify our estimations we present the apparent trend of the black hole masses with redshifts in Figure 9. It is evident that the distributions of the black hole masses for these LAMOST quasars are overlapped with those of SDSS DR7 quasars from Shen et al.(2O11).The result supports that our continuum modeling is mostly valid and the estimated black hole masses canbe taken asa proxy for these new quasars.

![](images/c5ea6a71d332628bd9b7895e948aa7307759872c674dd8cd3782cfd8cd4a110b.jpg)  
Figure9.Filled circles are the new quasars discovered in LAMOSTDR1 with estimated black hole masses based on emission lines of $\mathrm { H } \beta$ (black), $\mathbf { M } \mathbf { g }$ Ⅱ (green)，and $\mathbf { C } _ { \mathrm { ~ I ~ V ~ } }$ (blue).Small gray dots are SDSS quasars from Shen et al. (2011).

Table 1 Catalog Format for the 1180 New Quasars Discovered in LAMOST DR1   

<html><body><table><tr><td>Column</td><td>Name</td><td>Format</td><td>Description</td></tr><tr><td>1</td><td>LAMOST_NAME</td><td>STRING</td><td>LAMOST DR1 designation hmmss.ss+ddmmss (J2000)</td></tr><tr><td>2</td><td>R.A.</td><td>DOUBLE</td><td>R.A.in decimal degrees (J2000)</td></tr><tr><td>3</td><td>Decl.</td><td>DOUBLE</td><td>Decl. in decimal degrees (J2000)</td></tr><tr><td>4</td><td>MJD</td><td>LONG</td><td>MJD of spectroscopic observation</td></tr><tr><td>5</td><td>PLANID</td><td>STRING</td><td>Spectroscopic plan identification</td></tr><tr><td>6</td><td>SPID</td><td>STRING</td><td>Spectrograph identification</td></tr><tr><td>7</td><td>FIBERID</td><td>LONG</td><td>Spectroscopic fiber number</td></tr><tr><td>8</td><td>Z_VI</td><td>DOUBLE</td><td>Redshift from visual inspection</td></tr><tr><td>9</td><td>ZWARNING</td><td>LONG</td><td>ZWARNING flag from visual inspection</td></tr><tr><td>10</td><td>MI_Z2</td><td>DOUBLE</td><td>Mi (z = 2), K-corrected to z = 2 following Richards et al. (2006)</td></tr><tr><td>11</td><td>NSPECOBS</td><td>LONG</td><td>Number of spectroscopic observations</td></tr><tr><td>12</td><td>SNR_SPEC</td><td>DOUBLE</td><td>Median S/N per pixel of the spectrum</td></tr><tr><td>13</td><td>FWHM_BROAD_HA</td><td>DOUBLE</td><td>FWHM of broad Hα in km s-1</td></tr><tr><td>14</td><td>EW_BROAD_HA</td><td>DOUBLE</td><td>Rest frame equivalent width of broad Hα in A</td></tr><tr><td>15</td><td>FWHM_NARROW_HA</td><td></td><td>FWHM of narrow Hα in km s-1</td></tr><tr><td>16</td><td>EW_NARROW_HA</td><td>DOUBLE DOUBLE</td><td>Rest frame equivalent width of narrow Hα in A</td></tr><tr><td>17</td><td>EW_NII_6585</td><td></td><td>Rest frame equivalent width of [N u]6584 in A</td></tr><tr><td>18</td><td></td><td>DOUBLE DOUBLE</td><td>Rest frame equivalent width of [S u]6717 in A</td></tr><tr><td>19</td><td>EW_SII_6718</td><td>DOUBLE</td><td>Rest frame equivalent width of [S u]6731 in A</td></tr><tr><td>20</td><td>EW_SII_6732 EW_FE_HA</td><td>DOUBLE</td><td>Rest frame equivalent width of Fe within 600O-650o A in A</td></tr><tr><td>21</td><td>LINE_NPIX_HA</td><td>LONG</td><td>Number of good pixels for the rest frame 6400-6765 A</td></tr><tr><td>22</td><td>LINE_MED_SN_HA</td><td>DOUBLE</td><td>Median S/N per pixel for the rest frame 640o-6765 A</td></tr><tr><td>23</td><td>LINE_FLAG_HA</td><td>LONG</td><td>Flag for the quality in Hofitting</td></tr><tr><td>24</td><td>FWHM_BROAD_HB</td><td>DOUBLE</td><td>FWHM of broad Hβ in km s-1</td></tr><tr><td>25</td><td>EW_BROAD_HB</td><td>DOUBLE</td><td>Rest frame equivalent width of broad Hβ in A</td></tr><tr><td>26</td><td>FWHM_NARROW_HB</td><td></td><td>FWHM of narrow Hβ in km s-1</td></tr><tr><td>27</td><td></td><td>DOUBLE DOUBLE</td><td>Rest frame equivalent width of narrow Hβ in A</td></tr><tr><td>28</td><td>EW_NARROW_HB EW_OIII_4959</td><td>DOUBLE</td><td>Rest frame equivalent width of [O m]4959 in A</td></tr><tr><td>29</td><td>EW_OIII_5007</td><td>DOUBLE</td><td>Rest frame equivalent width of [O m]5007 in A</td></tr><tr><td>30</td><td></td><td>DOUBLE</td><td>Rest frame equivalent width of Fe within 4435-4685A in A</td></tr><tr><td>31</td><td>EW_FE_HB</td><td></td><td>Number of good pixels for the rest frame 4750-4950 A</td></tr><tr><td>32</td><td>LINE_NPIX_HB LINE_MED_SN_HB</td><td>LONG DOUBLE</td><td>Median S/N per pixel for the res tframe 4750-4950 A</td></tr><tr><td>33</td><td>LINE_FLAG_HB</td><td>LONG</td><td>Flag for the quality in Hβ fiting</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>34 35</td><td>FWHM_MGII EW_MGII</td><td>DOUBLE</td><td>FWHM of the whole Mg Ⅱ emission line in km s-1 Rest frame equivalent width of the whole Mg Ⅱ A</td></tr><tr><td>36</td><td>FWHM_BROAD_MGII</td><td>DOUBLE DOUBLE</td><td>FWHM of the whole broad Mg I in km s-1</td></tr><tr><td>37</td><td>EW_BROAD_MGII</td><td></td><td>Rest frame equivalent width of the whole broad Mg I in A</td></tr><tr><td>38</td><td></td><td>DOUBLE</td><td>FWHM of the broad Mg Ⅱ 2796 in km s-1</td></tr><tr><td></td><td>FWHM_BROAD_MGII_2796</td><td>DOUBLE</td><td></td></tr><tr><td>39</td><td>FWHM_NARROW_MGII_2796</td><td>DOUBLE</td><td>FWHM of the narrow Mg I 2796 in km s-1</td></tr><tr><td>40 41</td><td>EW_FE_MGII</td><td>DOUBLE</td><td>Rest frame equivalent width of Fe within 2200-3090 A in A</td></tr><tr><td>42</td><td>LINE_NPIX_MGII</td><td>LONG</td><td>Number of good pixels for the rest frame 27oo-2900 A Median S/N per pixel for the rest frame 270O-2900 A</td></tr><tr><td>43</td><td>LINE_MED_SN_MGII</td><td>DOUBLE</td><td>Flag for the quality in Mg fitting</td></tr><tr><td></td><td>LINE_FLAG_MGII</td><td>LONG</td><td></td></tr><tr><td>44</td><td>FWHM_CIV</td><td>DOUBLE</td><td>FWHM of the whole Civ in km s-1</td></tr><tr><td>45</td><td>EW_CIV</td><td>DOUBLE</td><td>Rest frame equivalent width of the whole C iv in A</td></tr><tr><td>46</td><td>FWHM_BROAD_CIV</td><td>DOUBLE</td><td>FWHM of the broad CIv in km s-1</td></tr><tr><td>47</td><td>EW_BROAD_CIV</td><td>DOUBLE</td><td>Rest frame equivalent width of the broad C iv in A</td></tr><tr><td>48</td><td>FWHM_NARROW_CIV</td><td>DOUBLE</td><td>FWHM of the narrow C iv in km s-1</td></tr><tr><td>49</td><td>EW_NARROW_CIV</td><td>DOUBLE</td><td>Rest frame equivalent width of the narrow Civ in A</td></tr><tr><td>50</td><td>LINE_NPIX_CIV</td><td>LONG</td><td>Number of good pixels for the rest frame 1500-1600 A</td></tr><tr><td>51</td><td>LINE_MED_SN_CIV</td><td>DOUBLE</td><td>Median S/N per pixel for the rest frame 1500-1600 A</td></tr><tr><td>52</td><td>LINE_FLAG_CIV</td><td>LONG</td><td>Flag for the quality in Civ fitting</td></tr><tr><td>53</td><td>ALPHA_LAMBDA_1</td><td>DOUBLE</td><td>Wavelength power-law index from ~1300 to 4661 A</td></tr><tr><td>54</td><td>ALPHA_LAMBDA_2</td><td>DOUBLE</td><td>Wavelength power-law index redward of 4661 A</td></tr><tr><td>55</td><td>MODEL_PHOT_REDCHI2</td><td>DOUBLE</td><td>Reduced chi-square</td></tr><tr><td>56</td><td>LOGL5100</td><td>DOUBLE</td><td>Monochromatic luminosity at 5100 A (erg s-1)</td></tr><tr><td>57</td><td>LOGL3000</td><td>DOUBLE</td><td>Monochromatic luminosity at 300o A (erg s-1)</td></tr><tr><td>58</td><td>LOGL1350 LOGBH_HB</td><td>DOUBLE</td><td>Monochromatic luminosity at 135o A (erg s-1)</td></tr></table></body></html>

Table 1 (Continued)   

<html><body><table><tr><td>Column</td><td>Name</td><td>Format</td><td>Description</td></tr><tr><td>60</td><td>LOGBH_MgII</td><td>DOUBLE</td><td>Virial BH mass based on Mg I (M)</td></tr><tr><td>61</td><td>LOGBH_CIV</td><td>DOUBLE</td><td>Virial BH mass based on C rv(Mo)</td></tr><tr><td>62</td><td>FPEAK</td><td>DOUBLE</td><td>FIRST peak flux density at 20 cm in mJy</td></tr><tr><td>63</td><td>BAL_FLAG</td><td>STRING</td><td>Broad absorption trough flag</td></tr><tr><td>64</td><td>FLAG_DATA_MINING</td><td>STRING</td><td>Flag of quasar selections based on data mining</td></tr><tr><td>65</td><td>FLAG_OI_COLOR</td><td>STRING</td><td>Flag of quasar selections based on optical-infrared color</td></tr><tr><td>66</td><td>FLAG_OTHERS</td><td>STRING</td><td>Flag of quasar selections from radio,X-ray,serendipitous algorithms.</td></tr></table></body></html>

(This table isavailable inits entirety inFITS format.)

# 5.THE SPECTRAL CATALOG

We present a compiled catalog for the new quasars identified in LAMOST DR1.All measured quantities are tabulated in the online catalog as a binary FITS table file at the LAMOST public website.We cross-correlate our quasar catalog with objects in the FIRST radio survey (Becker etal.1995) within a $2 . { } ^ { \prime \prime } 0$ radius and list the FIRST peak flux density. A summary of the information contained in each of the columns is described in Table 1.Below we describe the specifics of the cataloged quantities.

1.LAMOST object designation: LAMOST Jhhmmss.ss +ddmmss.s(J2000, truncated coordinates). The “LAMOST J" for each entry is dropped.   
2.R.A.and decl. (in decimal degrees, J2000).   
3.Informationofspectroscopicobservation:Modified Julian date (MJD)， spectroscopic plan identification (planID), spectrograph identification (spID),and spectroscopic fiber number (fiberID).These four numbers are unique for each spectrum named in the format of spec - MJD - planID_spID - fiberID.fits. Only information on the spectrum with the highest $\mathrm { { { S / N } } }$ is given if more than one spectroscopic observation is available for the quasar.   
4.Redshift.   
5.ZWARNING flag based on visual inspections. $1 = { \mathfrak { n } } \mathrm { o t }$ robust. 6. $M _ { i } ( z = 2 )$ :absolute i-band magnitude.K-corrected to $z = 2$ following Richards et al. (2006).   
7.NSPECOBS:number of spectroscopic observations for the quasar.   
8.SNR_SPEC:median $\mathrm { { } } S / \mathrm { { N } }$ per pixel in the wavelength regions of 4000-5700 and ${ \dot { 6 } } 2 0 0 { \dot { - } } 9 0 0 0 { \dot { \mathrm { A } } }$ ：   
9.FWHM,rest-frame equivalent width (EW) for broad $\boldsymbol { \mathrm { H } \alpha }$ narrow $\mathrm { H } \alpha$ ，[NⅡ]6584,[SⅡ]6717,and[S Ⅱ]6731.   
lO.Rest-frame equivalentwidth ofironemissionin $6 0 0 0 { - } 6 5 0 0 \mathring \mathrm { A }$   
[1.Number of good pixels and median $\mathrm { { } } S / \mathrm { { N } }$ per pixel for the $\mathrm { H } \alpha$ region in $6 4 0 0 { - } 6 7 6 5 \mathring \mathrm { A }$   
l2.Flag indicates reliability of the emission line fitting results in the $\mathtt { H } \alpha$ region upon visual inspections. $- 1 =$ unacceptable; $0 =$ acceptable.   
l3.FWHM,rest-frame equivalent width for broad $\mathrm { H } \beta$ narrow $\mathrm { H } \beta _ { \mathfrak { z } }$ $[ \mathrm { O } \mathrm { I I I } ] 4 9 5 9$ ， $[ \mathrm { O } \mathrm { m } ] 5 0 0 7$ ，fitted in the 4750-4950 A region.   
l4.Rest-frame equivalent width of iron lines in $4 4 3 5 { \ - } 4 6 8 5 \mathring \mathrm { A }$   
15.Number of good pixels and median $\mathrm { { } } S / \mathrm { { N } }$ per pixel for the （20 $\mathrm { H } \beta$ region in $4 7 { \dot { 5 } } 0 { - } 4 9 5 0 { \dot { \mathrm { A } } }$ ：   
16.Flag indicates reliability of the emission line fiting results in $\mathrm { H } \beta$ upon visual inspections. $- 1 =$ unacceptable; $0 =$ acceptable.   
17.FWHM,rest-frame equivalent width for total Mg I emission line.   
18.FWHM, rest-frame equivalent width for total broad $\mathbf { M g }$ Ⅱ lines.   
19.FWHM for broad and narrow $\mathbf { M g } \parallel 2 7 9 6$ emission line.   
20.Rest-frameequivalentwidth ofironlinesin $2 2 0 0 { - } 3 0 9 0 \mathring { \mathrm { A } }$   
21. Number of good pixels and median $\mathrm { { } } S / \mathrm { { N } }$ per pixel for the Mg I region in $2 7 0 0 { - } 2 9 0 0 \mathring { \mathrm { A } }$ ：   
22.Flag indicates reliability of the emission line fitting results in $\mathbf { M g }$ I upon visual inspections. $- 1 =$ unacceptable; $0 =$ acceptable.   
23.FWHM，rest-frame equivalent width for total C iv emission line.   
24.FWHM,rest-frame equivalent width for the GaussianHermite component of the C iv line.   
25.FWHM, rest-frame equivalent width for the Gaussian component of the C iv line.   
26. Number of good pixels and median $\mathrm { { } } S / \mathrm { { N } }$ per pixel for the C Iv region in $1 5 0 0 { - } 1 6 0 0 \mathring { \mathrm { A } }$   
27.Flag indicates reliability of the emission line fitting results in C iv upon visual inspections. $- 1 =$ unacceptable; （204号 $0 =$ acceptable.   
28.Wavelength power-law index， $\alpha _ { \lambda } ,$ from ${ \sim } 1 3 0 0$ to $4 6 6 1 \mathring { \mathrm { A } }$ , and redward of $4 6 6 1 \mathring { \mathrm { A } }$ ：   
29.Reduced chi-square in SDSS photometry modeling; -99 if not fitted.   
30.Continuum luminosity at 5100, 3000,and $1 3 5 0 \mathring { \mathrm { A } }$ =   
31.Virial black hole masses with calibrations of $\mathrm { H } \beta$ (VP06), Mg I (Wang08), and Civ (VP06).   
32.FIRST peak flux density at $2 0 \mathrm { c m }$   
33.Flag indicates whether a broad absorption trough is present in the spectra by visual inspection.1 is set if visually identified as a broad absorption quasar.   
34.Flag set as SVM，XD，or RichardsO9; mark quasars selected with corresponding data-mining method.   
35.Flag set as W, or U; mark quasars selected with SDSS/ UKIDSS or SDSS/WISE colors.   
36. Flag set as X-ray,RADIO, or S; mark quasars selected by X-ray,radio,or other serendipitous algorithms.

![](images/e8501b0179b8bc6becaa665d4700d24d34b4b1d0c1fcf08695dc7e6f1650d791.jpg)  
guree matchingdc in the pilot survey,of which the selections are a bit different from those in regular survey.

![](images/6c6ed1dfdcf2bd93a5f2e53a4b74f64b56cc1522cd8bcdaa146ca5bd08949586.jpg)  
Figure11.Distributionsof921quasarsand535 stars(black dots)inDSs-WSE/UKDSScolordagram.Buedotsre hequasars with $z < 2 . 2$ ,and green are $z \gtrsim 2 . 2$ .The dash-dotted lines indicate criteria used in the regular survey.

# 6.CONCLUSION AND DISCUSSION

We present our preliminary results of the LEGAS quasar survey in LAMOST DR1,which includes products from the pilot survey and the first year regular survey.We compile emission line measurements around the Hα, $\mathrm { H } \beta$ ,Mg I, and C Iv regions for the 118O new quasars discovered in the survey.We also compile the virial black hole mass estimates,with flags indicating the selection methods,and broad absorption line quasars.The catalog and spectra for these quasars are available online.

The candidates in the LEGAS quasar survey are selected from optical-infrared colors, data-mining algorithms，and multi-wavelength(optical-X-ray/radio) data matching. Object fractions selected from these methods for the reliably identified 5355 stars and 3921 quasars are shown in Figure 1O. There are $28 \%$ of the quasars that were independently selected with optical-infrared colors，indicating that the method is quite promising for completeness of low redshift quasars and searching for high redshift quasars (Wu et al. 2O12,2015; Yi et al. 2014; Wang et al. 2015). We have improved candidate selections in the regular survey compared to those in the pilot survey,in which a relatively larger fraction of stars is selected, asshown in the figure.We present the SDSS-WISE/UKIDSS color-color distributions of these quasars/stars in Figure 11, in which the criteria used in regular survey are shown in dashdotted lines.

Table 2 Parameters of the 2741Known Quasars   

<html><body><table><tr><td>NAME</td><td>MJD</td><td>PLANID</td><td>SPID</td><td>FIBERID</td><td>FLAG_DATA_MINING</td><td>FLAG_OI_COLOR</td><td>FLAG_OTHERS</td></tr><tr><td>000009.38 + 135618.4</td><td>56214</td><td>EG000024N121601B01</td><td>11</td><td>084</td><td>/XD/Richards09</td><td>/W/U</td><td>：</td></tr><tr><td>000015.17 + 004833.3</td><td>56213</td><td>EG000023N024031B01</td><td>01</td><td>155</td><td>/XD/Richards09</td><td>/W/U</td><td>：</td></tr><tr><td>000116.00 + 141123.0</td><td>56214</td><td>EG000024N121601B01</td><td>11</td><td>228</td><td>/SVM/Richards09</td><td>/W/U</td><td>：</td></tr><tr><td>000234.51 + 051344.1</td><td>55893</td><td>F9302</td><td>14</td><td>194</td><td>：</td><td>/W/U</td><td>：</td></tr><tr><td>000338.63 + 114138.3</td><td>56214</td><td>EG000024N121601B01</td><td>08</td><td>011</td><td>/SVM/Richards09</td><td>/W/U</td><td>：</td></tr><tr><td>000520.22 + 052410.7</td><td>55893</td><td>F9302</td><td>03</td><td>110</td><td></td><td>/W/U</td><td>：</td></tr><tr><td>000725.53 + 133313.5</td><td>56214</td><td>EG000024N121601B01</td><td>12</td><td>152</td><td>/Richards09</td><td>/W/U</td><td>：</td></tr><tr><td>000727.05 + 024113.1</td><td>56213</td><td>EG000023N024031B01</td><td>13</td><td>092</td><td>/Richards09</td><td>/W/U</td><td>：</td></tr><tr><td>004342.54 + 372519.9</td><td>56221</td><td>M31012N38B1</td><td>10</td><td>203</td><td>：</td><td>/W</td><td>：</td></tr><tr><td>004448.32 + 372114.7</td><td>55862</td><td>M6201</td><td>10</td><td>216</td><td>：</td><td>/W</td><td>：</td></tr><tr><td>004547.23 + 041023.4</td><td>55892</td><td>F9202</td><td>16</td><td>193</td><td>：</td><td>/W/U</td><td>：</td></tr><tr><td>004610.29 + 010644.1</td><td>55892</td><td>F9202</td><td>02</td><td>143</td><td>：</td><td>/W</td><td>：</td></tr><tr><td>004613.78 + 004410.3</td><td>55892</td><td>F9202</td><td>02</td><td>216</td><td>/SVM</td><td>/W</td><td>/Xray</td></tr><tr><td>004818.98 + 394111.7</td><td>55863</td><td>M31_011N40_B1</td><td>08</td><td>102</td><td>：</td><td>/W</td><td></td></tr><tr><td>005008.49 + 011330.1</td><td>55892</td><td>F9202</td><td>01</td><td>163</td><td>/SVM</td><td>：</td><td>/Xray</td></tr><tr><td>005050.74 + 353642.9</td><td>55874</td><td>M31_012N38_B1</td><td>01</td><td>214</td><td>…</td><td>/W</td><td></td></tr></table></body></html>

(This table is available in its entirety in machine-readable and Virtual Observatory (VO) forms.)

In DR1,a significantly high fraction $( \sim 8 0 \% )$ of the observed candidates cannot be identified by the pipeline.Most of these UNKNOWN have spectra with low $\mathtt { S } / \mathtt { N }$ due to nonphotometric conditions,unstable fiber efficiency,and a fainter magnitude cutoff at $i = 2 0$ for quasar candidate selections.To increase the quasar identification efficiency we have adjusted the magnitude cutoff to $i = 1 9$ in the ongoing survey.

We provide the information from LAMOST spectroscopic observations and selection methods for the 2741 known quasars in Table 2.With LAMOST and SDSS spectra of these quasars，we can investigate quasar spectral variability on timescales from months to decades.It is worthwhile to launch follow-up studies for the interesting quasars discovered in DR1,such as those with broad absorption troughs in C Iv and/ or $\mathbf { M g } \mathbf { \pi } _ { \mathrm { I I } }$ ，double-peaked Balmer line profiles,etc.LAMOST DR1 and the ongoing survey will provide valuable data in the studies of quasars.

This work is supported by the National Key Basic Research Program of China(No.2014CB845700,2013CB834900 and 2015CB857000), the NSFC grants (No.11103071, 11033001, 11033007，11373008，and 11533001)，the Strategic Priority Research Program “The Emergence of Cosmological Structures” of the Chinese Academy of Sciences (Grant No. XDBO9oooooO)，and State Key Development Program for BasicResearchof China(No.2O13CB834900and 2015CB8570oO). Guoshoujing Telescope (the Large Sky Area Multi-Object Fiber Spectroscopic Telescope LAMOST）is a National Major Scientific Project built by the Chinese Academy of Sciences. Funding for the project has been providedbytheNational Development and Reform

Commission.LAMOST is operated and managed by the National Astronomical Observatories,Chinese Academy of Sciences.

This publication makes use of data products from the Widefield Infrared Survey Explorer,which is a joint project of the University of California,Los Angeles,and the Jet Propulsion Laboratory/California Institute of Technology, funded by the National Aeronautics and Space Administration.

Funding for the Sloan Digital Sky Survey IV has been provided by the Alfred P. Sloan Foundation and the Participating Institutions. SDSS-IV acknowledges support and resources from the Center for High-Performance Computing at the University of Utah. The SDSS web site is www.sdss.org.

SDSS-IV is managed by the Astrophysical Research Consortium for the Participating Institutions of the SDSS Collaboration including the Carnegie Institution for Science, Carnegie Mellon University,the Chilean Participation Group, Harvard-Smithsonian Center for Astrophysics,Instituto de Astrofsica de Canarias,The Johns Hopkins University,Kavli Institute for the Physics and Mathematics of the Universe (IPMU)/University of Tokyo,Lawrence Berkeley National Laboratory,Leibniz Institut fir Astrophysik Potsdam (AIP), Max-Planck-Institut fuir Astrophysik (MPA Garching)，MaxPlanck-Institut fur Extraterrestrische Physik(MPE)，MaxPlanck-Institut fir Astronomie (MPIA Heidelberg),National Astronomical Observatory of China， New Mexico State University,New York University,The Ohio State University, Pennsylvania State University,Shanghai Astronomical Observatory，United Kingdom Participation Group，Universidad Nacional Autnoma de Mexico, University ofArizona, University of Colorado Boulder，University of Portsmouth, University of Utah,University of Washington，University of Wisconsin,Vanderbilt University,and Yale University.

# REFERENCES

Ahn,C.P.,Alexandroff,R.,Allende Prieto,C., et al.2012,ApJS,203,21 Ai,Y.L.,Yuan,W.,Zhou,H.,et al.2013,AJ,145,90A Antonucci,R.1993,ARA&A,31,473A Baskin,A.,&Laor,A.2005,MNRAS,356,1029B Becker,R.H.,White,R.L.,& Helfand,D.J.1995,ApJ,450,559 Bovy,J.,Hennawi,J.F.,Hogg,D.W.,et al. 2011,ApJ,729,141

Boyle,B.J.,Shanks,T.,Croom,S.M.,et al.2000,MNRAS,317,1014   
Casali,M.,Adamson,A.,Alves de Oliveira,C.,et al.2007,A&A,467,777   
Chiu,K.，Richards,G.T.,Hewett,P.C.,& Maddox,N.20O7,MNRAS, 375,1180   
Condon,J.J., Cotton,W.D.,Greisen,E.W.,et al.1998,AJ,115,1693   
Croom, S.M.,Warren,S.J.,&Glazebrook,K.2001,MNRAS,328,150   
Cui,X.-Q.,Zhao,Y.-H.,Chu,Y.-Q.,et al.2012,RAA,12,1197   
Cutri,R.M.,etal. 2012,VizieR On-lineData Catalog,2311,0   
Dong,X.-B.,Wang,T.-G.,Wang, J.-G., et al.2008,MNRAS,383,581   
Fan,X. 1999,AJ,117,2528   
Fan,X.,White,R.L.,Davis,M.,et al.2000,AJ,120,1167   
Fitzpatrick,E.L.1999,PASP,111,63   
Graham，M.J.，Djorgovski，S.G.，Drake，A.J.，et al.2014，MNRAS, 439, 703G   
Greene,J.E.,&Ho,L.C.2005a,ApJ,627,721   
Greene,J.E.,& Ho,L.C.2005b,ApJ,630,122   
Hambly,N.,Collins,R.S., Cross,N.J.G.,et al.2008,MNRAS,384,637   
Hennawi,J.F.,&Prochaska,J.X.2007,ApJ,655,735H   
Hewett,P.C.,Warren,S.J.,Leggett, S.K.,&Hodgkin, S.T.2006,MNRAS, 367, 454   
Ho,L.C.,Goldoni,P.,Dong,X.-B.,Greene,J.E.,& Ponti,G.2O12,ApJ, 754, 11   
Huo, Z.-Y.,Liu, X.-W., Liu, X., et al. 2013,AJ, 145,159   
Kirkpatrick,J.A., Schlegel,D.J., Ross,N.P., et al.2011,ApJ,743,125   
Kollmeier,J.A., Onken, C.A.,Kochanek,C. S.,et al.2006,ApJ,648,128   
Komossa,S.,Xu,D.,Zhou,H.,Storchi-Bergmann,T.,& Binette,L.2008, ApJ, 680, 926   
Laor,A., Jannuzi,B.T.,Green,R.F.,& Boroson,T.A.1997,ApJ,489,656   
Lawrence,A.,Warren, S.J.,Almaini, O., et al.2007,MNRAS,379,1599   
Luo,A.-L.,Zhang,H.-T.,Zhao,Y.-H.,et al.2012,RAA,12,1243   
Luo,A.-Li, Zhao,Yong-Heng,Zhao,G.,et al.2015,RAA,15,1095   
MacLeod,C.L.,Brooks,K.,Ivezic,Z.,et al.2011,ApJ,728,26   
Maddox,N.,Hewet,P.C.,Péroux,C.,Nestor,D.B.,& Wisotzki,L.2012, MNRAS, 424, 2876   
Maddox,N.,Hewett,P.C.,Warren,S.J.,& Croom, S.M.2008,MNRAS, 386,1605   
Markwardt,C.B.2009,in ASP Conf.Ser.411,Astronomical Data Analysis Software and Systems XVIII,ed.D.A.Bohlender,D.Daniel,&P.Dowler (San Francisco,CA:ASP),251   
McLure,R.J.,&Dunlop,J. S.2004,MNRAS,352,1390   
Morganson,E.,Burgett,W. S., Chambers,K.C.,et al. 2014,ApJ,784,92M   
Mortlock,D.J.,Warren, S.J.,Venemans,B.P.,et al.2011,Natur,474,616M

Palanque-Delabrouille,N.，Yeche,Ch.,Myers，A.D.，et al．2O11，A&A,   
530, 122   
Paris,I.,Petitjean,P.,Aubourg,E.,et al. 2012,A&A,548,66   
Peng,N., Zhang,Y., Zhao,Y.,& Wu,X.-b.2012,MNRAS,425,2599   
Richards,G.T.,Fan,X.,Newberg,H.J.,et al.2002,AJ,123,2945   
Richards,G.T.,Myers,A.D.,Gray,A.G.,et al.2009,ApJS,180,67   
Richards,G.T.,Nichol,R.C.,Gray,A.G.,et al. 2004,ApJS,155,257   
Richards,G.T.,Strauss,M.A.,Fan,X.,et al.2006,AJ,131,2766   
Ross,N.P.,Shen,Y.,Strauss,M.A.,et al.2009,ApJ,697,1634R   
Ross,N.P.,Myers,A.D.,Sheldon,E.S.,et al.2012,ApJS,199,3   
Salviander,S.,Shields,G.A.,Gebhardt,K.,& Bonning,E.W.2OO7,ApJ,   
662,131   
Schlegel,D.J.,Finkbeiner,D.P.,& Davis,M.1998,ApJ,500,525   
Schmidt,M.1963,Natur,197,1040   
Schneider,D.P.,Hall,P.B.,Richards,G.T.,et al.2007,AJ,134,102   
Sharp,R.G., Sabbey, C.N.,Vivas,A.K., et al.2002,MNRAS,337,1153   
Shen,Y.,Richards,G.T.,Strauss,M.A.,et al.2011,ApJS,194,45   
Smail,I.,Sharp,R., Swinbank,A.M.,etal.2008,MNRAS,389,407   
Smith,J.R., Croom,S.M.,Boyle,B.J.,etal.2005,MNRAS,359,57   
Tsuzuki,Y.,Kawara,K.,Yoshii,Y.,et al. 20O6,ApJ,650,57   
Vanden Berk,D.E.,Richards,G.T.,Bauer,A.,et al.2001,AJ,122,549   
Vanden Berk,D.E.,Wilhite,B.C.,Kron,R.G.,et al.20O4,ApJ,601,692   
van der Marel,R.P.,& Franx,M.1993,ApJ,407,525   
Véron-Cetty,M.-P.,Joly,M.,&Véron,P.2004,A&A,417,515   
Vestergaard,M.,&Peterson,B.M.2006,ApJ,641,689   
Wang,F.,Wu, X.-B., Xiaohui,F., et al. 2015,ApJL,807,L9   
Wang,J.-G.,Dong,X.-B.,Want,T.-G.,et al.2009a,ApJ,707,1334   
Wang,J.-M.,Chen,Y.-M.,Hu, C.,et al.2009b,ApJ,705,76   
Warren,S.J.,Hewett,P.C.,&Fsoltz,C.B.200O,MNRAS,312,827   
Wright,E.L.,Eisenhardt,P.R.M.，Mainzer，A．K.,et al．2O1O，AJ,   
140,1868   
Wu,X.-B.,Hao,G.,Jia,Z.,Zhang,Y.,&Peng,N.2O12,AJ,144,49   
Wu,X.-B.,&Jia,Z.2010,MNRAS,406,1583   
Wu,X.-B.,Wang,R., Schmidt,K.B., et al. 2011,AJ,142,78   
Wu,X.-B.,Chen,Z.-Y,Jia, Z.-D,et al.2010,RAA,10,8   
Wu,X.-B.,Wang,F.,Fan,X.,et al.2015,Natur.,518,512   
Yeche,Ch.,Petitjean,P.,Rich,J.,et al. 2010,A&A,523,14   
Yi,W.-M.,Wang,F.,Wu, X.-B,et al. 2014,ApJL, 795,L29   
Yuan,H., Zhang,H., Zhang,Y.,et al.2013,A&C,3,65   
Zhao,G., Zhao,Y.H.,Chu,Y.Q.,et al.2012,RAA,12,723   
Zuo,W.,Wu,X.-B.,Fan,X.,et al.2015,ApJ,799,189   
Zuo,W.,Wu,X.-B.,Liu,Y.-Q.,& Jiao, C.-L.2012,ApJ, 758,104