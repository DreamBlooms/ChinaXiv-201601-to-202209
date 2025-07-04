# SOUTHGALACTICCAP $u$ -BAND SKYSURVEY (SCUSS):DATAREDUCTION

HU ZOU1, ZHAOJI JIANG1, XU ZHOU1, ZHENYU $\mathrm { W U } ^ { 1 }$ ,JUN $\mathbf { M _ { A } } ^ { 1 }$ ，XIAOHUI $\mathrm { F A N } ^ { 2 }$ ,ZHOU FAN],BOLIANG $\mathrm { H E } ^ { 1 }$ ,YIPENG JING $^ 3$ MICHAEL LESSER², CHENG $\mathrm { L I } ^ { 4 }$ , JUNDAN $\mathrm { { N I E } } ^ { 1 }$ , SHIYIN SHEN4,JIALI WANG1,TIANMENG ZHANG1,AND ZHIMIN ZHOU1   
Keyaborat Steward Observatory,University of Arizona,Tucson,AZ 85721,USA CenterforAstrondstropsicsDepartentofisandtromyanJiaoonUiversityngai Shanghai Astronomical Observatory,Chinese Academy of Sciences,Shanghai 2ooo3o,China Received 20l4 August 25;accepted2015 August5;published 2015 September8

# ABSTRACT

The South Galactic Cap $u$ -band Sky Survey(SCUSS) is a deep $u$ -band imaging survey in the Southern Galactic Cap,using the 9OPrime wide-field imageron the 2.3 Bok telescope at KittPeak.The survey observations started in 2010 and ended in 2O13.The final survey area is about $5 0 0 0 \mathrm { d e g } ^ { 2 }$ with a median $5 \sigma$ point source limiting magnitude of ${ \sim } 2 3 . 2$ . This_paper describes the survey data reduction process,which includes basic imaging processing，astrometric and photometric calibrations,image stacking，and photometric measurements.Survey photometry is performed on objects detected both on SCUSS $u$ -band images and in the SDSS database. Automatic, aperture,point-spread function (PSF),and model magnitudes are measured on stacked images. Co-added aperture, PSF,and model magnitudes are derived from measurements on single-epoch images.We also present comparisons of the SCUSS photometric catalog with those of the SDSS and Canada-France-Hawaii Telescope Legacy surveys.

Key words: catalogs - surveys - techniques: image processing - techniques: photometric

# 1.INTRODUCTION

The South Galactic Cap $u$ -band Sky Survey (SCUSS; see X. Zhou et al.2O15,in preparation for more detail） is a deep imaging survey in the South Galactic Cap in $u$ -band with an effectivewavelengthof $3 5 3 8 { \mathring { \mathrm { A } } }$ .It isan international cooperative project between the National Astronomical Observatories of China and the Steward Observatory of the University of Arizona. The survey utilizes the $2 . 3 \mathrm { m }$ Bok telescope atKitt Peak.The camera, installed at the prime focus, provides a field of view(FOV) of about $1 \deg ^ { 2 }$ ，The adopted filter is similar to the $u$ band of the Sloan Digital Sky Survey (SDSS；York et al. 2OOO). The SCUSS project started in the summer of 2Oo9 and began its observations in fall 2010. Survey observations were completed in the fall of 2O13.The final survey area is about $5 0 0 0 \mathrm { d e g } ^ { 2 }$ with uniform imaging depth,of which more than $7 5 \%$ is covered by the SDSS footprint. The median imaging depth for point sources is about $2 3 . 2 \mathrm { m a g }$ at a signal-to-noise ratio $( \mathsf { S } / \mathsf { N } )$ of 5 with a 5 minute exposure time. Table 1 gives the basic characteristics of SCUSS.

The main goal of the survey is to supply input photometric catalogs to select spectroscopic targets for the Large Sky Area Multi-Object Fiber Spectroscopy Telescope (Cui et al. 2012). In addition,by combining with other bands in large-scale photometric surveys,such as the SDSS and Panoramic Survey Telescope & Rapid Response System (Pan-STARRS;Kaiser 2004), the survey data can be used for a wide range of scientific investigations,such as Galactic structure,Galactic extinction, galaxy photometric redshift,galaxy star formation rates,and stellar populations of nearby galaxies.

This paper describes the data reduction pipeline specially designed for the SCUSS survey.There are some instrumental issues that need to be specially handled,such as issues in overscan,substructures in bias,and crosstalk.In addition to detectingsourceson SCUSS images， we alsoprovide photometry for SDSS objects using consistent object parameters.Section 2 introduces the SCUSS survey and related facilities. Section 3 describes the basic image processing Astrometric and photometric calibrations are presented in Sections 4 and 5，respectively. Section 6 provides imagequality statistics of the observations. Section 7 describes image stacking. Sections 8 and 9 present photometry methods and a comparison with other surveys,respectively.A summary is given in Section 10.

# 2.THESURVEYANDFACILITIES

SCUSS is a $u$ -band imaging survey in the northern part of the southern Galactic Cap.The survey originally covered the region of Galactic latitude $b < - 3 0 ^ { \circ }$ and equatorial latitude $\delta > - 1 0 ^ { \circ }$ ，with a total area of about $3 7 0 0 \mathrm { d e g } ^ { 2 }$ . It was further extended to the Galactic anti-center region and the extra area covered by the SDSS,with a final survey area of about $5 0 0 0 \mathrm { d e g } ^ { 2 }$ (X. Zhou et al. 2015,in preparation). Normally, there are two exposures for each field and the total exposure time is 5 minutes,which generates images $1 { - } 1 . 5 \mathrm { m a g }$ deeper than the SDSS $u$ band.In the following，we give a general description of the telescope,camera,and flter that were used in SCUSS.

# 2.1.Telescope

The Bok telescope5 is a 90 inch $( 2 . 3 \mathrm { m } )$ telescope operated bythe Steward Observatory of theUniversity of Arizona.It is located on Kitt Peak,whose latitude is $+ 3 0 ^ { \circ } 5 7 ^ { \prime } 4 6 ^ { \prime \prime } 5$ and longitude is $1 1 1 ^ { \circ } 3 6 ^ { \prime } 0 1 \ { ^ { \prime } } 6 \mathrm { W }$ .The elevation is about $2 0 7 1 \mathrm { m }$ and the typical seeing is about $1 { ^ { \prime \prime } } 5$ ，The telescope runs year-round except on Christmas Eve and during a maintenance period in August. The accuracy of the absolute pointing of the telescope is recorded as $3 ^ { \prime \prime }$ over the entire sky.

Table 1 Survey Summary   

<html><body><table><tr><td>Telescope</td><td>2.3 m Bok telescope</td></tr><tr><td>Site</td><td>KittPeak in Arizona</td></tr><tr><td>CCD</td><td>2 ×24k ×4k CCD array</td></tr><tr><td>Field of view</td><td>1:08 × 1:03</td></tr><tr><td>Filter</td><td>u (3538 A)</td></tr><tr><td>Integral time</td><td>300 s</td></tr><tr><td>Magnitude limit</td><td>23.2 mag</td></tr><tr><td></td><td></td></tr><tr><td>Survey area Observation period</td><td>~5000 deg² 2010-2013</td></tr></table></body></html>

# 2.2. Camera

An imaging system，named 9OPrime,is deployed at the prime focus (corrected focal ratio: $f / 2 . 9 8$ ；corrected focal length: $6 8 2 9 . 2 \mathrm { m m }$ ).The detectoris a CCD array consisting of four $4 \mathrm { k } \times 4 \mathrm { k }$ backside-illuminated CCDs.They are STA2900 CCDs made by Semiconductor Technology Associates,Inc. and backside processed at the University of Arizona Imaging TechnologyLaboratory.These CCDs have been optimized for the $u$ -band response, giving a quantum efficiency at $u$ band of about $80 \%$ .Figure 1 displays the layout of the CCDs on the focal plane.The edge-to-edge FOVis about $1 \mathring { . } 0 8 \times 1 \mathring { . } 0 3$ . The pixel scale is $0 { ^ { \prime \prime } } . 4 5 4$ . There are inter-CCD spacings in the center of the array: $1 6 6 ^ { \prime \prime }$ in right ascension and $5 4 ^ { \prime \prime }$ in declination.Each CCD is read outby 4 amplifiers located at the corners.Each detector has $4 0 9 6 \times 4 0 3 2$ physical pixels and 20- row pixels of overscan for each amplifier. The full well is about 90,000 electrons or 65,OoO data numbers (DNs). The current system gain is set to be about 1.5 electrons per DN. The dark current is about 7 electrons per pixel per hr. The readout time is about $3 0 \mathrm { s }$ and the average readout noise is about 8.8 electrons. The response non-uniformity with the $u$ filter,which is the standarddeviationdividedbythe mean of a $u$ bandflatfield image,is about $2 \%$ .Table 2 summarizes these parameters of the detector.In 2010,CCD $\# 4$ had problems and only a quarter of this CCD could be used. CCD $\# 2$ and CCD $\# 3$ had relatively large readout noise.The camera was upgraded in 2011,at which time these two CCDs were replaced with new detectors. $\mathrm { C C D } \# 4$ was replaced and swapped with CCD $\# 1$ New video preamps were added to all four CCDs in order to reduce crosstalk and improve noise immunity.

# 2.3.Filter

The SCUSS $u$ filter is similar to the SDSS $u$ band. Figure 2 displays both SCUSS and SDSS system response functions. The SCUSS $u$ response curve includes the filter transmission, the CCD quantum efficiency,and the atmospheric extinction at a typical airmass of 1.3.The adopted atmospheric extinction is the same as that of the SDSS,which is based on the standard Palomar monochromatic extinction coefficients but here scaled to the elevation of Kitt Peak assuming an exponential scale height of the atmosphere of $7 0 0 0 \mathrm { m }$ (Doi et al. 2010). The effective wavelength and bandwidth of the filter are respec$\begin{array} { r } { \lambda _ { \mathrm { e f f } } = \frac { \int \lambda R ( \lambda ) d \lambda } { \int R ( \lambda ) d \lambda } } \end{array}$ $\lambda _ { \mathrm { e f f } } = \frac { \int \lambda R ( \lambda ) d \lambda } { \int R ( \lambda ) d \lambda }$ （20 tively defined as and JR()dx，where $R ( \lambda )$ is the filter response curve.The effective wavelength and bandwidth of the SCUSS $u$ band are about $3 5 3 8 { \mathring { \mathbf { A } } }$ and $\overset { \cdot } { 3 4 5 } \mathring { \mathrm { A } }$ respectively. The FWHM is about $5 2 0 \mathring { \mathrm { A } }$ .The effective wavelength,bandwidth,and FWHM of the SDSS $u$ filter is 3562,385,and $5 7 5 \mathrm { \AA }$ ，respectively. The SCUSS $u$ band is slightly bluer than the SDSS filter. In the rest of this paper, we will use the symbol $u ^ { * }$ to refer to the SCUSS $u$ band and the symbols $u , g , r , i ,$ and $z$ for the five SDSS bands.Throughout the paper,objects are classified as point-like or extended using the SDSS star-galaxy separation unless otherwise specified.

![](images/cc768896f72397802d50b7ab0d7fc078edf276bfaf2e1d1a469078ff4043be13.jpg)  
Figure1.Layout of the CCD array.There are four CCDs:CCD $\# 1$ $\# 2 .$ $\# 3$ and $\# 4$ Each CCD has four amplifiers highlighted by dashed lines.Overscan regions are also indicated.

Table 2 Detector Parameters   

<html><body><table><tr><td>CCD number</td><td>4 (in2×2array)</td></tr><tr><td>CCD gaps</td><td>166"in R.A.and 54" in decl.</td></tr><tr><td>CCD size</td><td>4096 × 4032 (extra 40 rows of overscan)</td></tr><tr><td>Full well</td><td>90,000 electrons/pixel (65,0oo ADUs/pixel)</td></tr><tr><td>Amplifier number</td><td>4</td></tr><tr><td>Quantum efficiency</td><td>~80% at 3500 A</td></tr><tr><td>Average dark current</td><td>7.2 electrons/pixel/hr</td></tr><tr><td>Response non-uniformity</td><td>2% at u band</td></tr><tr><td>Average readout noise</td><td>8.8 electrons</td></tr><tr><td>Readout time</td><td>~30s</td></tr><tr><td>Average gain</td><td>1.5 electrons/DN</td></tr><tr><td>Plate Scale</td><td>0'454 (15 μm)</td></tr></table></body></html>

# 3.BASICIMAGEPROCESSING

# 3.1.Image Division and Overscan Correction

90Prime has four CCDs and each CCD is read out by four amplifiers. Thus,every exposure file includes 16 FITS extensions.We split the file into four smaller FITS images, each of which represents one of the four CCDs. Overscan lines (40 pixels) are moved to the right side of the image.

We compute the median of the overscan columns for each amplifier and subtract it from the raw frame.There are some subtle issues about the overscan that require special care.For example,whena bright staris located right beside the overscan region,nearby overscan pixels are contaminated. Occasionally, some brighter stripes appear within or close to either end of the overscan region. The overscan in these regions needs to be interpolated or extrapolated.After overscan subtraction,frames are rotated counter-clockwise by $9 0 ^ { \circ }$ to keep north up and east left. These frames are then trimmed to the size of $4 0 9 6 \times 4 0 3 2$ pixels.

![](images/4dfaf54ca7c9f806a0033876171a2c5ec434049fde280aa9369309e2f2d33bbb.jpg)  
Figure 2.Response curves of the SCUSS $u ^ { * }$ and SDSS $u$ filters.Both curves include the atmospheric extinction at an airmass of 1.3 and normalized to their maximums.

# 3.2.Dark Current

The average dark current of the 9OPrime imager is about $7 . 2 \mathrm { e }$ per hr.For an exposure of $3 0 0 \mathrm { s }$ ,it is ignorable (about 0.6e) relative to the readout noise of about 8.8e,so we did not take dark exposures.

# 3.3. Bias

Bias frames are taken before and after the scientific exposures.A total of 2O bias frames are obtained each night. After combining them， there are large-scale structures, especially for CCD $\# 2$ and $\# 3$ as shown in Figure 3.Counts in some peaks of the structures can be more than $1 0 \mathrm { D N }$ These structures affect the accuracy of photometry significantly, especially in $u$ band,because counts of scientific frames in this band are low.The bias structures are stable for a long time (month-to-month variation is about O.25 ADU),so we derive a median“super”bias by combining all the bias frames taken within a month.All overscan-subtracted frames are corrected by this“super”bias.

# 3.4. Flat-fielding

Flat-fielding removes the instrumental signatures from raw frames using several exposures taken with the telescope facing a uniform light source.At the beginning and end of each night, a total of 2O dome flats are taken with the dome closed and the telescope pointing to a white screen.This screen is illuminated byUVlamps of Philips MasterColor Ceramic Metal Halide ED-17. Usually,a 6 s exposure generates about $2 0 { , } 0 0 0 \mathrm { D N }$ on the CCD.Although dome flats have extremely high S/Ns, there are some disadvantages to applying them in flat-fielding.First, lamps are point sources and the scattered light on the screen might be uneven in the radial direction. Second, the optical path of the light from the screen is not the same as the light from night sky.In addition,we also find that the gain of each amplifier changes considerably during the whole night. When using only dome flats,we find that average sky backgrounds in the four amplifiers of each CCD can be quite different.

![](images/4ad8935866f08ebd2c736b0bdbf2a23d0232569122127f21cf6aa18a6243dd5a.jpg)  
Figure 3.“Super”bias image of four CCDs in 2O11 December.The layout of these CCDs is the same as that shown in Figure 1.

Twilight flats are an alternative way and regarded as being more uniform than dome flats.They are obtained by observing the sky during evening and morning twilight.The brightness of the twilight sky changes rapidly and it strongly depends on the weather. It is difficult to get enough good high S/N flats. The problem of gain variation also persists.

Raw science images also contain the flat-field characteristics By combining all the science frames with outliers rejected,we can obtain a “super” sky flat.This kind of flat has more advantages than the two types of flats above. The light of night sky“super” flat comes through the same optical path as the observed objects.The CCD gain is the average of all science frames and it is closer to the real-time variation during the night.There are some structures in the“super” flat that present a different sensitivity amplitude relative to the dome flats possibly due to a different light path.About 15O science images onaverage are observed each night.The average level of the skybackground in each image is about15O ADU.As a result, the“super” sky flat has an average count of about 23,OoO ADU. We present the sky flats on 2O11December 28 as an example in Figure 4.After applying either the dome flat (higher $\mathrm { { { S / N } ) } }$ or super sky flat,we find that there is less than a $0 . 2 \%$ difference in the sky background fluctuations.The resulting error due to lower $\mathrm { { } } S / \mathrm { { N } }$ of the“super”flat is negligible relative to the large sky background fluctuation of about 12.7 ADU and CCD readout noise of 8.8 electrons.Thus,we use the“super’sky flat to do flat-fielding corrections of the science frames.

![](images/8953994868113fd1815d23ee3391ead6cb96c074811b0f775666d17f8d87dd58.jpg)  
Figure 4.“Super”sky flat image of four CCDs on 2O11 December 28.The layout of these CCDs is the same as that shown in Figure 1.

# 3.5. Crosstalk

Crosstalk frequently occurs in multi-channel CCD chip readout.When there are saturated objects in one of the CCD amplifiers,it can be best seen as mirror images in other amplifiers.The crosstalk usually causes contaminations across the output amplifiers at the level of 1:1O,OOO (Freyhammer et al.2OO1). The output counts of each amplifier are the sum of the true counts from the sky and a small fraction of counts from other amplifiers.The crosstalk signal can be either positive or negative and should be corrected for high-precision astronomical photometry.

The9OPrimecamerahas four CCDsand each CCDhasfour amplifiers.The crosstalk effect is clearly seen in our SCUSS raw images with saturated stars. The crosstalk signal is positive.We characterize the effect assuming that it is additive and proportional to the number counts of other amplifiers.The proportionality coefficients are relatively stable in SCUSS images.We correct crosstalk using the following prescription: a series of images with bright stars appearing in one of the CCD amplifiers isselected; the proportionality coefficientsare estimated by comparing the mirror signals with their original signals; the crosstalk signals in one quadrant are removed with the corresponding coefficients of the other three quadrants. The average coefficient for the SCUSS images is about 2:10,000. Figure 5 illustrates the crosstalk and the performance of its correction. The crosstalk signals are clearly seen as mirror images (arrows) of a bright star that is marked with a circle.

proper motions. Then, the projection center of the telescope can be calculated using this rough solution.A more accurate astrometric solution is then derived with the projection center and a radial second-order correction for the focal plane distortion.This distortion term is the same for all frames in our survey.

The left panel in Figure 6 shows the distribution of the astrometric errors in the plane of R.A.and decl.differences between SCUSS and UCAC4.It includes objects in one exposure of a randomly selected field.About l8oO objects are matched with UCAC4. The average position offsets are $0 _ { \cdot } ^ { \prime \prime } 0 0 2$ and $0 { ^ { \prime \prime } } . 0 0 4$ for R.A and decl.,respectively. The $1 \sigma$ position errors in R.A.and decl.are about $0 _ { \cdot } ^ { \prime \prime } 1 2 8$ and $0 \mathrm { ^ { \prime \prime } } 1 2 0$ .The right plot of Figure 6 illustrates the distortion of the focal plane. The plate scale varies from the center $( 0 \% 4 5 5 )$ to the edge $( 0 ^ { \prime \prime } 4 4 7 )$ of the FOV.The pixel area near the corner is about $3 . 3 \%$ smaller than that of the central pixel.

# 4.2.External Astrometric Errors

External astrometric errors are estimated by matching SCUSS objects with the UCAC4 catalog.About 165 objects on average for each CCD are crossing-identified and the global external position error is about $0 \prime . 1 3 \ \pm \ 0 . 0 2$ . The mean external astrometric offsets and rms errors for R.A.and decl. are

$$
\begin{array} { r l } & { \overline { { \Delta \alpha } } = - 0 \mathrm { . } 7 0 0 1 2 \pm 0 . 0 0 7 9 , \overline { { \Delta \delta } } = - 0 \mathrm { . } 7 0 0 1 5 \pm 0 . 0 0 7 1 , } \\ & { \sigma _ { \Delta \alpha } = 0 \mathrm { . } 7 1 1 1 1 \pm 0 . 0 1 7 8 , \sigma _ { \Delta \delta } = 0 \mathrm { . } 7 1 0 9 4 \pm 0 . 0 1 8 2 , } \end{array}
$$

where $\sigma$ corresponds to the $6 8 . 3 \%$ confidence level.

Figure 7 displays the external coordinate offset and rms error as functions of R.A.and decl.The offsets and rms errors are uniform over the entire survey.

# 4.3.Internal Astrometric Errors

Internal astrometric calibration errors are estimated using the cross-identifications of UCAC4 sources inside the overlapping areas between two adjacent exposures.Each field is observed with two exposures dithered by half a CCD size,so every CCD frame is covered by four other frames,whose astrometric solutions are independently derived.We calculate the internal astrometric uncertainties using the objects in common to both frames.The global average internal error is about $0 { } ^ { \prime \prime } 0 9 \pm 0 . 0 3$ = The mean internal R.A.and decl.offsets and rms errors over the whole survey are

$$
\begin{array} { r } { \overline { { \Delta \alpha } } = 0 . 7 0 0 0 9 \pm 0 . 0 1 0 2 , \overline { { \Delta \delta } } = 0 . 7 0 0 0 4 \pm 0 . 0 1 1 3 , } \\ { \sigma _ { \Delta \alpha } = 0 . 7 0 7 2 8 \pm 0 . 0 2 9 5 , \sigma _ { \Delta \delta } = 0 . 7 0 7 0 7 \pm 0 . 0 2 6 9 . } \end{array}
$$

# 4.ASTROMETRICCALIBRATION

# 5.PHOTOMETRICCALIBRATION

# 4.1.Astrometry by UCAC4

Astrometric solutions are derived by cross-identifying objectsinscience frameswith the Fourth USNaval Observatory CCD Astrograph Catalog (Zacharias et al. 2013, UCAC4). UCAC4 is an all-sky star catalog that is complete in $R$ band down to 16 mag.It contains proper motions for most stars. An approximate first-order guess of the astrometric solution for each CCD is first estimated using UCAC4 objects in the same area with positions revised according to their

# 5.1.External Calibration

The SDSS imaging survey has covered more than one third of the sky within both northern and southern Galactic caps.It provides photometric catalogs of about 52OO square degrees in the SGC.More than 21 million objects in this area are recorded.The exposure time for each band is about $5 4 \mathrm { s }$ .The $u$ magnitude limit with $9 5 \%$ completeness for point sources is about $2 2 . 0 \mathrm { m a g }$ .The photometric calibration accuracy in $u$ band is about $1 . 3 \%$ . The ninth data release (Ahn et al. 2012,

![](images/72a54cd9c2e25350ae19622e810a4b93126d477674ecb2a8d0df65b691ffd624.jpg)  
FigurLefaai aftercorrecting the crosstalk.

![](images/8cb191f7606ace14a8079ad1aa80ac7053c36fd5d9ec27b7be22ce2f9e2a2c00.jpg)  
Figure6ef ee reuresod plaelofbo colored surface.

DR9）is utilized to make photometric calibrations of the SCUSS images.

Because of gain and observational condition variations, individual zeropoints must be determined separately for each frame.Aperture photometry is performed using DAOPHOT (Stetson 1987) on the bias-subtracted and flat-fielded images. We choose an aperture radius of about 7'3 (16 pixels), similar to that of $7 ! 4 3$ adopted by the SDSS photometric calibration. The aperture diameter is about 7 times the typical seeing FWHM,which is large enough not to be affected by aperture correction.The transformation equation between the instrumental magnitudes $u _ { \mathrm { i n s t } } = - 2 . 5 \log _ { 1 0 } { }$ ADU to the SDSS calibrated magnitude is simply given by

$$
u = u _ { \mathrm { i n s t } } + c + k X + f ( u - g ) + f ^ { \prime } ( u - g , X ) ,
$$

where $c$ is the instrumental zeropoint, $k$ is the atmospheric extinction coefficient, $X$ is the airmass, $\boldsymbol { u } - \boldsymbol { g }$ is the SDSS color,and $f ( u \mathrm { ~ - ~ } g )$ is the color term.The final term of $f ^ { \prime } ( u - g , X )$ is related to the color effect due to the atmospheric extinction. The central wavelength of SCUSS $u ^ { * }$ band at an airmass of1.0,1.3,and1.5 is estimated to be 3534, 3538,and $3 5 4 2 \mathring { \mathrm { A } }$ .The photometric effect in the color terms for most main-sequence stars at different airmasses is less than

![](images/51873e285c76b6a1e61b33d502fe4e0e2057411579d40cd8540ff56127bfe646.jpg)  
Figure7Cdsfls $\pm 1 \sigma$ scatter around the average along the $x$ axis.The R.A.is transformed to the range of $( - 1 8 0 ^ { \circ }$ $1 8 0 ^ { \circ } )$ ：

$0 . 3 \%$ ,estimated using theoretical stellar spectral libraries.So, we ignore the second-order color term.Since the standard stars are the common SDSS objects within the same area of each image,the term solely related to the airmass is constant. Thus, Equation (1) can be simplified as

$$
u ^ { * } = u - f ( u - g ) = u _ { \mathrm { i n s t } } + C ,
$$

where $u$ is the calibrated SCUSS $u$ -band magnitude and $C$ is still termed as the“photometric zeropoint.”’The color term is estimated as follows:（1） SCUSS instrumental magnitudes are calibrated using the photometric magnitudes of common SDSS objects without considering the color term;(2） magnitude differences between these calibrated SCUSS magnitudes and SDSS magnitudes are calculated as a function of the SDSS $\boldsymbol { u } - \boldsymbol { g }$ color;(3)an approximate system transformation formula is fitted by a two-order polynomial:

$$
\begin{array} { c } { { u ^ { * } - u = - f ( u - g ) } } \\ { { = 0 . 1 4 5 9 - 0 . 1 9 5 7 ( u - g ) } } \\ { { + 0 . 0 5 9 1 ( u - g ) ^ { 2 } , } } \end{array}
$$

for $0 . 8 < u - g < 2 . 7$ (see Figure 8). This color term is only used for the photometric calibration.Here the SDSS is used for the zeropoint only,and the SCUSS photometry on its native system is defined to match the SDSS at $u - g = 0$ . We choose starswith $1 6 . 0 < u < 2 0 . 5$ to eliminate objects that are saturated or have large photometric errors.Equation (3）is then applied to transform $u$ to SCUSS $u ^ { * }$ .Following Equation (2),we measure the final zeropoint $C$ byiteratively rejecting outliers.

The CCD gain varies slightly during the observation. Furthermore, CCD gains of the four amplifiers did not change synchronously.In addition，there is a photometric response non-uniformity on the flat-fielded images.Itis possibly caused by the focal plane distortion and scattered light reflected in the optical system (Regnault et al. 2009; Betoule etal. 2013). Thus, we perform photometric calibration for each amplifier of each CCD.There are about 47 stars in each amplifier on average to derive the zeropoint,whose accuracy is estimated to be about $0 . 0 1 \mathrm { { m a g } }$ .The zeropoint here is expressed in units of mag for $1 \mathrm { A D U } \bar { \mathrm { s } } ^ { - 1 }$ ．After deriving independent zeropoints for each amplifier,we find a small residual pattern in the sensitivity as derived from objects observed in differentpositions in the field as shown in Figure 9.We use this residual map to further refine the flat-field.

![](images/c496479d23f82add8eba998e37e39914d466f854bb0a5f71365f696d81c06387.jpg)  
Figure 8.Magnitude difference between the SCUSS $u ^ { * }$ and SDSS $\boldsymbol { u }$ asa function of the SDSS $\boldsymbol { u } - \boldsymbol { g }$ color.The points are for point-like objects with $1 6 < u < 2 0 . 5$ .The error bars show the averages and $1 \sigma$ errors within different color bins.The red curve is the fitted transformation equation as shown in Equation (3).

![](images/e1b35f873d02e800303b78ebed16d987eba96f15fdd15aa40cb3b17c28da0043.jpg)  
Figure 9.Non-uniformity pattern used to correct the flat-fielded and calibrated images.The layout of these CCDs are the same as in Figure 1.

![](images/d411e8e8c1fa9752c1bb27c141e9629ff8b5ac4a352bfe03e27e941ccbea0360.jpg)  
FigurLeo observation time.The zeropoints are in units of mag for 1 ADU $\mathbf { s } ^ { - 1 }$ . The data for CCD $\# 1$ $\# 2$ ,and $\# 3$ are shifted by 2.O.The dashed lines separate the years of observations.Right: relative zeropoints compared with the above average for each amplifier of CCD $\# 1$ as a function of time.The data for three amplifiers,Amp. $\# 1$ $\# 2$ ,and $\# 3$ ,are shifted by 0.2.

# 5.2.Photometric Response Differences of the Four Amplifiers

The average zeropoints of four amplifiers are shown in the left panel of Figure 1O as a function of time.Usually during the night,we scan the sky from east to zenith and then to west. The airmass and corresponding atmospheric extinction first decrease and then increase.Therefore，zeropoints present nightly variations.From this figure,it can be seen that the weather conditions over 2O1O are worst. The right panel of Figure 1O shows the relative zeropoint variation with time for each amplifier of CCD $\# 1$ compared with the average zeropoint of all amplifiers.The relative zeropoint variations do not keep the same value and sometimes two amplifiers present opposite variations.The detectors have bad qualities in 2010, so the relative zeropoint changes more notably with time. Thus,it is critical that we obtain the photometric solutions independently for the four amplifiers.

Table 3 gives the zeropoint scatter of four amplifiers for each year and each CCD. The zeropoint differencesamong amplifiers originate from gain variation,photometric response non-uniformity as mentioned before,and the photometric calibration error. The overall zeropoint scatter of four amplifiers around the averages are $0 . 0 1 2 \pm 0 . 0 0 6 , 0 . 0 1 6 \pm$ 0.007, $0 . 0 1 5 \pm 0 . 0 0 9$ ，and $0 . 0 1 1 \pm 0 . 0 0 6$ for CCD #1,#2, $\# 3$ ，and $\# 4$ ,respectively.The general response differences of four amplifiers in all CCDs are less than $1 . 5 \%$ except CCD $\# 3$ of 2010,which is about $2 . 8 \%$

# 5.3.Internal Calibration

Each SCUSS field is observed twice and overlaps with the adjacent fields.Thus,each CCD image can be calibrated using the common objects cross-identified in surrounding images. The calibrating process begins with balancing the zeropoints of images covered by the SDSS and then transferring the photometric solutions to the images out of the SDSS footprints. The calibration iterates until the whole grid of photometric solutions finally converges.Figure 11 shows the magnitude difference distribution between measurements for objects that are observed twice.The histograms in black and red are the distributions of the same objects with the SCUSS $u$ -band magnitude calibrated externally and internally，respectively. The dispersion by external calibrations is about $0 . 0 2 8 \mathrm { \ m a g }$ while thatby internal calibrations is about O.O25.It seems the internal calibration is at least as good as or evena little better than the external calibration.

Table 3 Average Zeropoint Scatter of Four Amplifiers for Each CCD   

<html><body><table><tr><td rowspan="2">CCD year</td><td>#1</td><td>#2</td><td>#3</td><td>#4</td></tr><tr><td colspan="4"></td></tr><tr><td>2010</td><td>0.011 ± 0.007</td><td>0.015 ± 0.009</td><td>0.028 ± 0.009</td><td>：</td></tr><tr><td>2011</td><td>0.013 ±0.006</td><td>0.015 ± 0.006</td><td>0.011 ± 0.006</td><td>0.010 ± 0.006</td></tr><tr><td>2012</td><td>0.013 ± 0.006</td><td>0.013 ± 0.006</td><td>0.010 ± 0.006</td><td>0.011 ± 0.006</td></tr><tr><td>2013</td><td>0.010 ± 0.006</td><td>0.020 ± 0.007</td><td>0.017 ± 0.006</td><td>0.011 ± 0.006</td></tr><tr><td>All</td><td>0.012 ± 0.006</td><td>0.016 ± 0.007</td><td>0.015 ± 0.009</td><td>0.011 ± 0.006</td></tr></table></body></html>

# 6.IMAGEQUALITYSTATISTICS

Both weather and instrumental status affect the image quality. The camera was regularly updated after each observation season,so its performance was improved gradually.The weather and night sky conditions strongly affect the imaging depth of the survey.We can measure the characteristics tracing the image quality,such as airmass,sky background brightness, seeing，and photometric zeropoints.

![](images/ed04c635fff20b08f560e72a4f9faefbd307eac13be37a88e41d2a38c68014ec.jpg)  
Figure 11.Magnitude difference distributions between two measurements for objects observed more than twice.The black histogram is externally calibrated by the SDSS catalog，while the red one is internally calibrated.Only bright objects with $1 6 < u < 1 9$ are selected.

# 6.1. Seeing

The seeing is estimated by the FWHM measurements of isolated and bright point sources.The seeing distribution is presented in Figure 12(a). The best seeing is $1 { ^ { \prime \prime } } 2$ and the overall median seeing is about $2 { ^ { \prime \prime } } 0$ .The Bok telescope is located in the trough between two peaks of the mountain, so the wind speed is usuallylarger than other places on the same site, which has an effect on the seeing.

# 6.2. Airmass

Figure 12(b) shows the airmass distribution of all survey images.The median airmass is about 1.28,and this is used to determine the typical $u$ -band filter response as shown in Section 2.3.

# 6.3.Photometric Zeropoint

The variation of the photometric zeropoint mainly reflects the change in atmospheric transparency.The distribution of the photometric zeropoints is plotted in Figure 12(c). The mean photometric zeropoint is $2 3 . 8 1 \mathrm { m a g }$ for $1 \mathrm { \ A D U { s } ^ { - 1 } }$ The median zeropoints for airmasses of 1.O,1.2，and 1.4 are 23.93,23.85,and 23.75,respectively. There are some images with low zeropoints,most of which were observed when the weather was cloudy.

# 6.4.Sky Brightness

The sky background brightness is an important parameter to quantify a ground-based observation station.Compared with other light sources,the artificial light pollution from nearby cities is more serious at Kitt Peak.The distribution of the $u$ -band sky brightness at Kitt peak is shown in Figure 12(d). There are some images taken when the moon is above the horizon. The average night sky brightness of all observations isabout $2 2 . 0 5 \mathrm { m a g a r c s e c } ^ { - 2 }$ .The moonless median sky background at zenith is about $2 2 . 3 7 \mathrm { m a g } \mathrm { a r c s e c } ^ { - 2 }$ ，which iscomparabletothat oftheApachePointsite （204号 $( 2 2 . 1 \mathrm { m a } \bar { \bf g } \mathrm { a r c s e c } ^ { - 2 } .$ ).Note that the calibrated sky brightness uses the frame zeropoints that implicitly include atmospheric extinction,so the actual sky brightness is darker because the $u$ -band atmospheric extinction coefficient is about O.5，as estimated with the observations taken during photometric nights.

# 7.IMAGE STACKING

# 7.1.Quality Control

Most SCUSS fields are observed under good weather and moderate seeing conditions.There are some cases with bad image quality:（1） high sky background due to observations during astronomical twilight or when the moon was up; (2) large seeing due to strong wind; (3） low atmospheric transparency due to cirrus in the FOV;(4) bad focus of the CCD camera. In 2O13,we spent one and half observation runs re-observing most bad-quality fields.

To ensure homogeneity of the imaging depth and completeness of the SCUSS survey，we keep only the images with seeing ${ < } 3 { ^ { \prime } } { : } 0$ ，sky background ADU ${ < } 5 0 0$ ，and photometric zeropoint $> 2 2 . 5 6 \$ mag. About $9 2 . 6 \%$ of the survey area is covered by these images. For the remaining area,we take images with seeing ${ < } 3 { ^ { \prime } } { : } 0$ 0 $3 . 6 \%$ area),regardless of the sky brightness and photometric zeropoint.If none are available,we take all remaining images,which covers about $3 . 8 \%$ of the total area.

# 7.2.Image Resampling and Stacking

Based on the central coordinatesof each field,we stack related single-epoch images to form a combined image.We first project and resample the single-epoch images to a grid with a fixed pixel scale of $0 { ^ { \prime \prime } } { 4 } 5 4$ . The grid has $8 6 4 0 \times 8 2 0 0$ pixels,covering a sky area of $1 \div 0 9 0 \ \times \ 1 \div 0 3 4$ .If a singleepoch images contributes less than less than $1 2 8 \times 1 2 8$ ,itis not included in the stacking process.For each pixel of the grid, there are more than four related pixels in each single-epoch image.These pixels are regarded as having the same size after being flat-fielded. We calculate the fractions of these pixel areas that are covered by the grid pixel and sum them to conserve flux.

We subtract the sky backgrounds from the resampled images. Their photometric zeropoints are converted to linear flux weights. The remaining signal after removing backgrounds isweighted by these weights and then co-added.If there are more than three pixels involved in stacking，a cosmic-ray rejection is implemented using a sigma clipping algorithm.We redo the flux calibration for each stacked image with the SDSS DR9 catalog to derive the final photometric zeropoint. This zeropoint is approximately 29 mag for 1DN.In addition,a mask image for each field is also generated. Each mask pixel presents the number of images that are actually involved in the flux co-adding. The mask value is reduced by one for each epoch in which a pixel is bad, saturated,or blank.Figure 13 shows a typical stacked image and its mask image.Most of the stacked image has two exposures,an overlapping area has more than three exposures,and there are some small holes located in the CCD gaps that are blank. Some of the CCD gaps have only one exposure,so the depth is about O.75 mag shallower in those locations.

![](images/692c1c63d35d294140e540d53a64b7ea70f1d2fcd577413e3e41dda87c9da4a6.jpg)  
Figure 12. Histograms of seeing (in arcsec),airmass, photometric zeropoint (in mag for 1 ADU $\mathbf { s } ^ { - 1 }$ ),and sky background (in mag arcsec-²)for all SCUSS $u$ -band observations.

![](images/c505fd15b80a21ff43ae32402ac8b9d97d5962041b51dcb3cdc614158ff3134d.jpg)  
Figure 13.Examples of a stacked image (left) and its mask image (right).The central coordinate is $\alpha = 4 4 \div 7 5 3 6$ $\delta = 6 \div 1 0 7 4$ .North is up and east is left.A galactic clusterofAelsc presentigofsall smallhorizontallinesarecausedbythemissngCCDrows thatwerenotrecordedbythecameracontrolerduring2Olland 2012.

Table 4 Aperture Radii for the Aperture Photometry   

<html><body><table><tr><td>No.</td><td>Radius in Pixels</td><td>Radius in Arcseconds</td></tr><tr><td>1</td><td>3</td><td>1.36</td></tr><tr><td>2</td><td>4</td><td>1.82</td></tr><tr><td>3</td><td>5</td><td>2.27</td></tr><tr><td>4</td><td>6</td><td>2.72</td></tr><tr><td>5</td><td>8</td><td>3.63</td></tr><tr><td>6</td><td>10</td><td>4.54</td></tr><tr><td>7</td><td>13</td><td>5.90</td></tr><tr><td>8</td><td>16</td><td>7.26</td></tr><tr><td>9</td><td>20</td><td>9.08</td></tr><tr><td>10</td><td>25</td><td>11.35</td></tr><tr><td>11</td><td>30</td><td>13.62</td></tr><tr><td>12</td><td>40</td><td>18.17</td></tr></table></body></html>

# 8.PHOTOMETRY

The SCUSS photometric pipeline generates comprehensive catalogs using multiple photometric techniques so that different users can choose the one that suits their needs.Aperture, automatic aperture,point-spread function (PSF),and model photometry are applied to both SCUSS stacked and singleepoch images.The model photometry is consistent with the SDSS model photometry that utilizes the SDSS $r$ -band model shape parameters to measure brightnesses on the SCUSS $u$ -band images.

# 8.1.Source Detection

Source detections for astronomical science images are never complete,especiallyat the fainter magnitude end.Morphologies of extended sources in $u$ band are more fragmented and diffuse than those in other optical bands. Therefore，many fainter sources with low surface brightness might be missing. Inaddition,most of the science projects based on SCUSS data also need to use deeper and redder other bands from other large-scale surveys.More than $3 / 4$ of the SCUSS area is covered by the SDSS.Our sources include both SDSS detected objects and detections unique to our SCUSS images.For the area not covered by the SDSS,we perform photometry for only SCUSS detections. The resulting catalog within these areas will be useful to match with other wide imaging surveys (e.g., PanSTARRS).

SDSS objects with any one of the PSF,Petrosian, model, and CModel ugriz-band magnitudes brighter than 23.5 mag are selected.SExtractor is used to detect objects in SCUSS stacked images,and these are matched with the SDSS objects.The mismatched objects are rematched with SDSS catalogs with magnitudes fainter than $2 3 . 5 \mathrm { m a g }$ in order to find missing SDSS objects. The rest of the objects are SCUSS unique detections.

# 8.2.Aperture Photometry by DAOPHOT

Circular aperture photometry is a simple procedure to measure magnitudes of sources.The core code of the aperture photometry in DAOPHOT is utilized to measure aperture magnitudes (Stetson 1987).We use 12 apertures with radii ranging from $1 \%$ to $1 8 ^ { \prime \prime }$ (from 3 to 40 pixels; see Table 4).

It is important to apply aperture corrections to aperture magnitudes due to flux loss within a finite aperture size.For smallerapertures and larger seeing,this is especially important.

Figure 14 presents growth curves under different seeing conditions.The growth curve is calculated as the magnitude difference between 1 of 12 apertures and the $7 { } _ { \cdot { } 3 } ^ { \prime \prime }$ radius aperture as function of aperture radius.This reference aperture is the one used for photometric flux calibration.We choose isolated and point-like objects with photometric errors in all apertures less than $0 . 0 5 \mathrm { m a g }$ to derive the growth curve. Outlier objects are eliminated when the median growth curve is calculated.

# 8.3.Automatic Photometry by SExtractor

SExtractor (Bertin & Arnouts 1996) provides precise magnitudes of sources using automatic aperture photometry, generatingaso-called“automaticmagnitude,” whichis motivated by the Kron algorithm (Kron 198O).An elliptical aperture is automatically determined for each object to integrate the flux.Although most of the flux is expected to lie within the elliptical aperture and the flux lossshould be almost independent of the source magnitude,we discover that in fact, the flux loss does change with both the source magnitude and seeing.The magnitudes of objects that are brighter or objects observed with worse seeing have more corrections. We consider an equivalent circle whose area is equal to that of the ellipse.Thus,the radius of this circular aperture is equal to the root of the product of the semi-major and semi-minor axis lengths.We callthis circular radiusthe characteristic radius, which has the same meaning as the aperture size in normal aperture photometry discussed above.Figure 15 presents the aperture corrections for the automatic magnitudeswith different seeing.The black dots are point-like and isolated objects detected by SExtractor. They lie along with the growth curve of the aperture correction described in the previous section. Thus,an interpolation from the curve is good enough for correcting automatic magnitudes.

We also perform Petrosian-like photometry on SCUSS images by SExtractor. The Petrosian aperture is very similar to the Kron one. They share the same position angle and ellipticity.The Petrosian aperture radius is determined by the ratio of the isophotal brightness at a certain radius and average surface brightness within this radius.The ratio is set to be O.2 and the corresponding Petrosian radius is larger than the Kron radius. The aperture corrections for Petrosian magnitudes can be estimated the same way as mentioned above.

# 8.4.PSF Photometry

The PSF is obtained using PSFEx7(Bertin 2O11). The form of the PSF in PSFEx is expressed as a linear combination of basis vectors.The pixel basis is selected in our PSF modeling. The spatial PSF variation on the focal plane usually shows a smooth profile，which can be modeled by a low-order polynomial. For SCUSS single exposures，a second-order polynomial is good enough to describe the PSF variation over the CCD plane.For SCUSS stacked images,a seventh-order polynomial is used to describe the complexity of the image quality.

A code is specially designed to measure the PSF magnitudes at known object positions. The code takes the SCUSS image, SDSS and SCUSS-only object positions, the bad-pixel list, and the PSF model derived by PSFEx as inputs and then outputs the Gaussian-fitted position,local sky background and its error, local PSFFWHM, fitted PSF integrated flux and its estimated error,and a flag tagging the status of each object. Figure 16 shows the flowchart of the PSF photometry code.The local sky background for each object is measured using the pixels at $r > 7 . 5 \ \times \ \mathrm { F W H M }$ .Here,the FWHMisthe FWHM of the local PSF model. Outliers,such as cosmic rays and signals from real objects,are iteratively rejected by a sigma-clipped algorithm.After the sky background is subtracted, the object position on the CCD is fitted by a two-dimensional Gaussian function. The position is allowed to shift because the coordinates in SDSS redder bands are slightly different from those in the SCUSS $u$ band due to atmospheric refraction and star proper motions.The pixels centered at the initial position with $r < 2 . 5 \times \mathrm { F W H M }$ are considered in the calculation.If the new fitted position is more than 2.O pixels away from the old one,the following PSF photometry will be performed at the original position. The PSF model is interpolated to the same pixel scale of the CCD image and fitted to the fluxes of the object pixels within $r = 2 . 0 ~ \times$ FWHM.Flags are also provided by our PSF photometry to show the reliability. They are coded in decimal and expressed as a sum of powers of 2:(1) CCD artifacts; (2) bad pixels; (4) including saturated pixels; (8) contaminated by neighbors;(16) near image edges.

![](images/c2c2173928bf9aca3f1fbebba41b5bb9a1c6ee065ba69cff79f58283851e8857.jpg)  
Figure4 redlinesihd previous three panels in order to present the impact of seeing.

![](images/f346377b1d4b45806e34c0559ccc625618da16560ae0f6ee901ab6d0f9598119.jpg)  
Figure 15. Difference between the automatic and circular aperture magnitudes of $7 _ { \cdot } ^ { \prime \prime } 3$ radius as a function of the characteristic radius. Black dots are isolated point socesow those growth curves.

![](images/d625db85a5ad6bed43eb8f122eb7708e83d0202083840fa04b3a5b6d4664a9e2.jpg)  
Figure16s isfdtl together with the fitted positions and flags are given as outputs.

![](images/a149f82aee2b47897b043a77de6d7d1cb9e321da0309876e5052de8f5eecc47a.jpg)  
Figure 17.Comparisons ofour PSF photometry with DAOPHOT.Left is thecomparison for common bright objects with $1 6 < u < 1 8$ and right is the one for common faint objects with $2 1 < u < 2 2$ ：

We compare our PSF measurements with one of the popular PSF photometry software packages (DAOPHOT),which is a widely used package for accurate stellarphotometry designed to deal with crowded fields.We use DAOPHOT to findobjects in one single-epoch image and at the same time give the PSF magnitude measurements. Then,our code performs PSF photometry for those objects with the PSF model derived by

PSFEx. The magnitude comparison is shown in Figure 17.Two groups of objects are chosen:a brighter one with $1 6 < u < 1 8$ mag(leftinFigure17) andafainteronewith $2 1 < u < 2 2 \mathrm { m a g }$ (right in Figure 17). The scatter of the PSF magnitude differences between our code and DAOPHOT are $0 . 0 0 9 \mathrm { { m a g } }$ for the bright group and O.O21 for the faint group,respectively.Our PSF photometry is consistent with DAOPHOT,although the PSFs used by these two techniques are derived in different ways.

# 8.5.Model Photometry

The SDSS also provides a type of model magnitude,or “modelMag,” which can measure the unbiased colors of galaxies in the absence of color gradients through equivalent apertures in different bands.The “modelMag”is generated by choosing a shape model, either a deVaucouleurs or exponential profile,based on its best-fit likelihood in the SDSS $r$ band, then convolving them with seeing in other bands,and finally forcing magnitude measurements with the same aperture shape.

We divided SDSS objects into two groups, point sources and extended sources，based on the SDSS classification.For extended sources,we construct their theoretical 2D models with the effective radii,axis ratios,and position angles from the SDSS measurements. These models are convolved with local PSF profle derived by PSFEx.For point sources,we use local PSF from PSFEx directly as their models.In addition,the extended sources with small sizes orlow brightnesses (effective radii less than O.5 arcsec or SDSS $r$ -band magnitude fainter than $2 3 . 5 \mathrm { m a g } ,$ ）are also treated as point sources.

After the models are constructed,model amplitudes are calculated as the ratios of the models and raw SCUSS fluxes. The pixels within $r = 1 . 0 \times \mathrm { F W H M }$ are considered in the calculation，which is optimized for faint SDSS extended sources.According to the amplitudes,we then compute the corresponding deVaucouleurs and exponential magnitudes. Therefore, the“modelMag"in SCUSS $u$ band can be estimated by the SDSS $r$ -band deVaucouleurs and exponential profiles. The SCUSS model magnitude is aperture-corrected to make the magnitudes of bright point sources $( 1 6 < u < 2 0$ )equalto the SDSS $u$ -band model magnitudes.

# 8.6. Co-added Photometry

The stacked images are composed of single-epoch images taken with different observational conditions.The seeing varies between each single-epoch image,which makes the PSF profile of the stacked image quite complicated. Subsequently，the fraction of flux loss due to finite apertures for objects in different parts of the stack images might be different. In addition, the PSF profile cannot be perfectly determined unless the seeing of related single-epoch images is similar enough. On the other hand,the PSF profile of a single image varies smoothly and it is much easier to model.We can first perform photometry for an object observed with different exposures and then co-add its fluxes to generate different co-added magnitudes at the catalog level.

The aperture photometry for single-epoch images is obtained by DAOPHOT with 12 apertures as defined before.Aperture corrections are applied to the resulting aperture magnitudes. Corresponding corrected fluxes are weighted by the errors and averaged to generate the co-added aperture magnitudes.

The PSF photometry for single-epoch images is performed using our PSF fittng code. The PSF magnitudes are also aperture-corrected by comparing with the aperture magnitudes in a $7 \mathrm { ^ { \prime \prime } } 3$ radius.The co-added PSF magnitudes are calculated by averaging the fluxes weighted by their errors.

We perform the model photometry for single-epoch images and measure the exponential and deVaucouleurs magnitudes. We adopt the model magnitude with a higher SDSS $\mid r \mid$ -band likelihood. Aperture corrections are applied to make model magnitudes equal to the SDSS model magnitudes in the case of unresolved objects. The co-added model magnitudeis calculated by averaging the model fluxes weighted by their errors.

# 9.SOMEPHOTOMETRICCOMPARISONS

The photometric methods described above are applied to stacked and single-epoch images. Figure 18 illustrates the general photometric scheme.The detections are based on both SDSS and SCUSS images.We perform aperture,PSF,model, and automatic photometry for the stacked images.Note that the automatic magnitudes are only based on objects solely detected by SExtractor. We also obtain co-added aperture,PSF,and model magnitudes from photometry of single-epoch images. Since point sources can be best modeled while extended sources are much more complicated, the photometry of pointlike objects is better suited for comparisons of our different photometric methods.Thus,the comparisons of point sources are presented for most cases below and, for comparison with SDSS，we correct the magnitude with the SCUSS/SDSS color term.

# 9.1.Photometry of Stacked Images

We compare the different SCUSS photometric measurements for stacked images with the SDSS PSF or model magnitudes of point sources in Figure 19.The SCUSS model magnitude is compared with the SDSS $u$ -band model magnitude,while other magnitudes are compared with the SDSS PSF magnitude.We choose the 5 pixel $( 2 ! 2 7 )$ to present the aperture magnitude in this figure. For the smallest apertures, the aperture magnitudes might be problematic due to inhomogeneous image quality in some stacked images. Table 5 gives the magnitude offset and scatter in two magnitude intervals: $1 6 < u < 1 9 \mathrm { { m } } \mathrm { { : } }$ agand $2 0 . 5 < u < 2 1 . 5 \mathrm { \ m a g }$ (i.e., ${ \sim } 2 1 \mathrm { m a g }$ ).The automatic magnitude is best amongall photometric magnitudes for stacked images,with a scatter of 0.033 for bright stars and O.178 for faint stars at $u \sim 2 1 . 0$ mag.

# 9.2. Co-added Photometry for Single Images

The comparisons of the co-added PSF,aperture,and model magnitudes with the SDSS PSF or model magnitudes are shown in the right panels of Figure 19 and the last three rows of Table 5.The co-added PSF magnitude performs the best for point sources among all the magnitude types. The scatter is 0.033 for brighter sources and O.174 for fainter sources at $u \sim 2 1 . 0 \mathrm { m a g }$ .The co-added aperture magnitude isalso adequate if a proper aperture radius is considered. The aperture size should be chosen according to the object type,object brightness, signal-to-noise requirement, etc.

![](images/83bbdf7960043f74125e85dda22f5f264b24181026a12282675b0c078e37b88f.jpg)  
Figur8oat aperture and PSF magnitudes for the single-epoch images.

# 9.3.Comparisonswith the CFHTLSDeepu Band

The Canada-France-Hawaii Telescope Legacy Survey (CFHTLS；Astier et al. 2006) used the wide-field optical imaging camera on CFHT to obtain deep multicolor photometry over wide areas over 5 years.The photometric system is similar to that of the SDSS，except the $u$ filter. As one component of the CFHTLS,the wide synoptic survey covers 155 square degrees in four patches down to $i = 2 4 . 5$ The $u \cdot$ band magnitude limit in the wide survey reaches $2 5 . 2 \mathrm { m a g }$ which is much deeper than the SCUSS $u$ band.Thus,the catalogs of the wide survey can be regarded as a reference when comparing the SCUSS photometry with that of the SDSS. There are two CFHTLS wide regions,W1 and W4, overlapping with the SCUSS footprints. The W4 field $\alpha = 2 2 ^ { \mathrm { h } } 1 3 ^ { \mathrm { m } } 1 8 ^ { \mathrm { s } }$ ， $\delta \ : = \ : + 0 1 ^ { \mathrm { d } } 1 9 ^ { \mathrm { m } } 0 0 ^ { \mathrm { s } } )$ has an area of $2 5 \deg ^ { 2 }$ fully covered by the SCUSS and it is located at a higher declination,where the SCUSS data quality is more typical than it is in the W1 field.We make some photometric comparisons using the W4 catalogs.

Figure 2O shows the photometric comparisons of point sources between the SCUSS and SDSS with the CFHTLS wide data as a reference. The left panels in this figure present the magnitude difference between the SDSS (in blue points） or SCUSS $u$ -band magnitude (in red points）and the CFHTLS automatic magnitude as a function of the CFHTLS u magnitude.

The SDSS magnitude is the PSF magnitude and the SCUSS magnitudes are automatic,co-added PSF,and co-added aperture $( 2 ! 2 7 )$ magnitudes from top to bottom, respectively. These three types of SCUSS magnitudes are considered to be the best flux measurements for point sources.The number of objects for the automatic magnitude is less than those of the other two magnitude types (mainly at the faint end) due to different source detection by SExtractor itself.Both the SCUSS and SDSS $u$ -band magnitudes are converted to the CFHTLS photometric system by the color term as indicated in the CFHTLS webpage8: $u _ { \mathrm { C F H T } } = u _ { \mathrm { S D S S / S C U S S } } - 0 . 2 4 1 ( u _ { \mathrm { S D S S / S C U S S } } - g _ { \mathrm { S D S S } } )$ ： The SDSS scatter for brighter sources is similar to the SCUSS scatter,while it is much larger than the SCUSS scatter at the faint magnitude ends.The histograms in the right panels of Figure 2O show the magnitude difference distributions with $2 2 < u _ { \mathrm { C F H T } } < 2 3$ .The scatter for the SCUSS and SDSS is also presented in these panels.The photometric accuracy of the SCUSS is much better than that of the SDSS for fainter sources due to deeper imaging.

# 9.4.Photometry for Extended Sources

Extended sources are much more complicated, especially in ultraviolet bands,since their morphologies look much more fragmented than in redder bands.By comparing different magnitude measurements on stacked images with the SDSS model magnitude,we calculate a scatter at $u \sim 2 1$ of about 0.2, 0.31,0.4, O.23 for automatic,aperture $( 2 ! 2 7 )$ ,PSF,and model magnitudes，respectively. The co-added photometric magnitudes give similar results.The automatic magnitudes seem to be the best for extended sources,but they only describe the brightnesses of SCUSS-detected objects. The model and aperture magnitudes are also adequate.The PSF photometry fails to measure the magnitudes of galaxies.

![](images/0da4f8680490215776fa793800df44b4281b73d2bd14d6d3d3a08df742eff9c7.jpg)  
Figure19.MagitudedifrecesetweendfrentCUSSagniesdthSDsFoodelmagitudesofpntssouesafunctfCU magnideot rightpael shown here is the one with an aperture radius of $4 { : } 5$ The two lines above and below zero show $\pm 1 \sigma$ scatter around the average.

Table 5 Magnitude Offset and Scatter of Point Sources for the SCUSS Magnitudes Compared withthe SDSSPSF orModelMagnitudes   

<html><body><table><tr><td rowspan="2">Magnitude</td><td colspan="2">16<u<18</td><td colspan="2">20.5<u<21.5</td></tr><tr><td>Offset</td><td>Scatter</td><td>Offset</td><td>Scatter</td></tr><tr><td>Automatic (stacked)</td><td>0.001</td><td>0.033</td><td>0.008</td><td>0.178</td></tr><tr><td>Petrosian (stacked)</td><td>0.002</td><td>0.033</td><td>0.065</td><td>0.200</td></tr><tr><td>PSF (stacked)</td><td>-0.003</td><td>0.047</td><td>0.025</td><td>0.175</td></tr><tr><td>Aperture (stacked)</td><td>-0.002</td><td>0.044</td><td>0.017</td><td>0.176</td></tr><tr><td>Model (stacked)</td><td>-0.006</td><td>0.059</td><td>0.004</td><td>0.177</td></tr><tr><td>Co-added PSF</td><td>-0.004</td><td>0.033</td><td>0.021</td><td>0.174</td></tr><tr><td>Co-added aperture</td><td>0.003</td><td>0.034</td><td>0.010</td><td>0.177</td></tr><tr><td>Co-added model</td><td>-0.003</td><td>0.049</td><td>0.003</td><td>0.175</td></tr></table></body></html>

# 9.5.Guidelines to use Magnitudes

The choice of photometric technique is dependent on the science one wants to do. Here we present some general guidelines.More than $90 \%$ of the stacked images are assembled from single-epoch images with consistent image quality. The photometry on these images is as good as the corresponding co-added photometry.However，as the background noise in single-epoch images is larger than that in stacked images，there are about $23 \%$ more objects with available magnitude measurements in stacked images than withavailable co-added magnitudes.

The automatic magnitude performs as well as the PSF and model magnitudes because it can adaptively fit elliptical apertures to both point and extended sources with similar flux loss.It can be regarded as a universal magnitude for both pointlike and extended sources. But unlike other photometric methods,the automatic photometry is based on the objects detected on SCUSS images,which are about $3 5 \%$ of SDSS objects with available SCUSS $u$ -band fixed-parameter measurements.For point sources like quasars and stars,the PSF and aperture magnitudes with appropriate aperture sizes are recommended. The aperture size needs to be determined based on scientific objectives.For nearby galaxies with extended morphological structures,the automatic magnitude and aperture magnitude aregood choices. The SCUSS model magnitude is defined the same as the SDSS “modelMag." When combining magnitudes of other SDSS bands to measure the colors of extended sources,it is better to use the model magnitude.

# 10.SUMMARY

The SCUSS survey is a wide-feld $u$ -band sky survey in the Southern Galactic cap. The survey used the Bok telescope on Kitt Peak and the filter is close to the SDSS $u$ band. The survey observations were completed by the end of 2O13 and the total area is about $5 0 0 0 \mathrm { d e g } ^ { 2 }$ .This paper describes the detailed data reduction dedicated to the survey，including basic image processing which has some special features related to the detectors,astrometric and photometric calibrations,and photometry.The general astrometric error is about $0 { : } 1 3$ .The SCUSS photometric calibration is tied to the SDSS catalogs and is performed for each amplifier of a CCD due to gain and weather variations.

![](images/0d74456074e5c194a08b7764d645527cf5997fd77cd8885155087927112de433.jpg)  
Figure2otessaee isthePSFmagtdetoadeeelsefe CFHTLS as a function of the CFHTLS $u$ bandmagnitude,andtherightonesarethe normalizeddistributionsof thediferencesat thefaintmagnitudeend(the hatch area: $2 2 < u < 2 3 \mathrm { \ m a g }$ ).Fromtoptobom,theyarecomparisonsoftreetypesofSCUSagnitudes:theutomaticcoaddedPSF,andco-addedaperture magnitues magnitude scatter of the SCUSS and SDSS,which corresponds to the $6 8 . 3 \%$ confidence level.

We apply different photometric techniques to the stacked images, includingautomaticphotometrybySExtractor, aperture photometry by DAOPHOT，PSF photometry，and model photometry. Our PSF photometry with more controllable parameters is consistent with DAOPHOT.The model photometry is similar to the SDSS“ModelMag,”which uses the SDSS $r$ -band model-derived shape parameters and SCUSS PSF profiles to make consistent and unbiased model magnitude measurements.We perform photometry on stacked images and also on single-epoch images,from which co-added photometry is derived. More than $90 \%$ of stacked images are assembled from single-epoch images with consistent quality. There are about $23 \%$ more objects with available magnitudes on stacked imagesthan with available co-added magnitudes. The photometry on these stacked images is as good as the coadded photometry.However,for the rest of the stacked images, their photometry is worse than the co-added photometry due to uneven image quality.

We thank the referee for thoughtful comments and insightful suggestions that greatly improved our paper. This work is supported by the National Natural Science Foundation of China (NSFC，N0s．11203031，11433005，11073032，11373035, 11203034，11303038，11303043）and by the National Basic ResearchProgram of China (973 Program，Nos. 2014CB845704，2013CB834902, and2014CB845702). Z.Y.W. was supported by the Chinese National Natural Science Foundation grant No.11373033.This work was also supported by the joint fund of Astronomy of the National Nature Science Foundation of China and the Chinese Academy of Science,under grants U1231113.

The SCUSS is funded by the Main Direction Program of Knowledge Innovation of Chinese Academy of Sciences (No. KJCX2-EW-TO6). It is also an international cooperative project between National Astronomical Observatories,Chinese Academy of Sciences,and Steward Observatory，University of

Arizona, USA.Technical support and observational assistance from the Bok telescope are provided by Steward Observatory. The project is managed by the National Astronomical Observatory of China and Shanghai Astronomical Observatory. Data resources are supported by Chinese Astronomical Data Center (CAsDC).

SDSS-III is managed by the Astrophysical Research Consortium for the Participating Institutions of the SDSS-III Collaboration includingthe University ofArizona, the Brazilian Participation Group,Brookhaven National Laboratory,Carnegie Mellon University，University of Florida, the French Participation Group,the German Participation Group, Harvard University,the Instituto de Astrofisica de Canarias, the Michigan State/Notre Dame/JINA Participation Group,Johns Hopkins University,Lawrence Berkeley National Laboratory, Max Planck Institute for Astrophysics,Max Planck Institute for Extraterrestrial Physics，New Mexico State University，New York University，Ohio State University，Pennsylvania State University,University of Portsmouth,Princeton University, the Spanish Participation Group,University of Tokyo,University ofUtah，Vanderbilt University，University ofVirginia, University of Washington,and Yale University.

Based on observations obtained with MegaPrime/MegaCam,a joint project of CFHT and CEA/IRFU,at the Canada

France-Hawaii Telescope(CFHT）which is operated by the National Research Council (NRC）of Canada,the Institut National des Science de1'Univers of the Centre National de la Recherche Scientifique(CNRS) of France,and the University of Hawaii. This work is based in part on data products produced at Terapix available at the Canadian Astronomy Data Centre as part of the Canada-France-Hawaii Telescope Legacy Survey,a collaborative project of NRC and CNRS.

# REFERENCES

Ahn,C.P.,Alexandroff,R.,Allende Prieto,C., et al.2012,ApJS,203,21   
Astier,P.,Guy, J.,Regnault,N., et al. 2006,A&A,447,31   
Bertin,E.2011,adassXX,442,435   
Bertin,E.,&Arnouts,S.1996,A&AS,117,393   
Betoule,M.,Marriner,J.,Regnault,N.,etal. 2013,A&A,552,A124   
Cui,X.-Q., Zhao,Y.-H., Chu,Y.-Q., et al. 2012,RAA,12,1197   
Doi,M.,Tanaka,M.,Fukugita,M.,et al.2010,AJ,139,1628   
Freyhammer，L.M.，Andersen，M.I.，Arentoft,T.，Sterken，C.，&   
Norregaard,P. 2001,ExA,12,147   
Kaiser,N. 2004,Proc. SPIE,5489,11   
Kron,R. G. 1980,ApJS,43,305   
Regnault,N., Conley,A., Guy, J., et al.2009,A&A,506, 999   
Stetson, P.B.1987,PASP, 99,191   
York,D.G.,Adelman,J.,Anderson,J.E.,Jr.,et al.200O,AJ,120,1579   
Zacharias,N.,Finch, C.T.,Girard, T.M.,et al.2013,AJ,145,44