# Azimuth High-Resolution for a Conically Scanned Pencil-beam Scatterometer Using Rotating Azimuth Doppler Discrimination

Gang Wang, Xiaolong Dong, Senior Member, IEEE,Di Zhu, Member, IEEE,and Qingliu Bao

Abstract-Inordertosatisfyarelativelyhighresolutionfortheretrievalofsnowwaterequivalent,anX/Ku-banddual-frequency full-polarizedSCATterometer(DFPSCAT）on-boardWaterCycleObservationMisson（WCOM）satellteisdesignedfor high-resolutionobservations.However,given the situationthati)theconicallyrotationrateof antenna is relatively fast $( { \bf 1 9 ~ r / m i n } )$ ,ii) the swath width is larger than $\mathbf { 1 0 0 0 ~ k m }$ ，iii day or night observation capabilities are required,the method called“Rotating Azimuth DopplerDiscrimination”isproposed，whichcansatisfytheresolutionrequirementandreal-timeprocesing.Consideringthe complexityoftesystem'sdsignandtheimprovementofazimuthresolutioncapability,aburstpusingschemisddresedtoatisfy thenumbersofazimuthsampling.Thesimulationmodelisusedtoanalyzethefeasibilityofazimuthdiscriminatiomethodbasedon geometry and system parameters. It is shown that the achievable azimuth resolution is about $2 { \cdot } 5 \mathbf { k m }$ far end of the swath and only 5km near end of the swath. The results show that Kpc is $\mathbf { < 0 . 4 }$ when snow thickness exceeds ${ \pmb 5 } { \bf m }$ and about 0.75 when light snow.

Index Terms—Scatterometer,Rotating Antenna,Doppler Discrimination,burst pulse scheme

# I．INTRODUCTION

WCOM proposes a DFPSCAT using the dual frequency (X-band 9.6 GHz and Ku-band 17 GHz)and multi-polarization for mapping of snow waterequivalent and freze-thaw processes[1，2],aiming to provide higheraccuracyandconsistent measurements ofkeyelements ofwatercycle fromspace outsideoftheEarth'stmosphere,including soilmoisture,oceansalinity freeze-thaw，snow waterequivalent，etc.Space-borne scaterometer has become of greatbenefittothenumerical weather predictionsand climate monitoring in the past4O years,andthe designand developmentofascaterometer fordiferent applications has been applied.The measurement accuracyandperformanceofsnow water equivalentisrelatedtotheresolution.In orderto ake intoaccountthe local vegetable variability,theresolution should be degradedtoahigherresolutionof1km[3]. However,suchaighresolutionishard toaceveforcurrtscaterometerinstrument,whichasaniherentspatialresolutionon the order of $1 0 { - } 5 0 \mathrm { k m }$ [4,5]. So,considering the implementation capabilityof the DFPSCATon-board WCOM,a spatial resolution of $2 { - } 5 \mathrm { k m }$ is proposed [2].

Unlike synthetic aperture radar (SAR),real apertureradar (RAR) provides measurements in real-time procesing.However, especially wen theantennaisscaning fast,theaccumulating timeoftheRARis notlong enough,sotheresolution willbe relativelylow.Incontrasttoafan-beam system,the pencil-beam design employs asingle antenna whichisconicallyscaning aboutthe nadiraxis inordertoprovidemultipleazimuth measurements.Suchapencil-beamantennaisalsoeasiertobeinstalledon thespacecraft[6].Basedontheplatform motionand theantenna scanning styleoftheon-board scaterometer,thissystem wil achieve an improvedresolutionalong the azimuthdirectionbyusing theDoppler discrimination method.This method is applied when the azimuth angle is in the range between 10 to 170 degrees [7,8]. When the azimuth is between the intervals of $0 { + } / { - } 1 0$ and $1 8 0 { + } / { - } 1 0 \$ degrees (the absolute valueof Doppler shift is the largest and the Doppler bandwidth is near zero),the method caled super-resolutionreconstructionisapplied[9].However,thatisnotthefocus inthispaper.Therefore,atadeoffbetweenaimuth resolutionand complexityof the system deserves careful consideration.Meantime,a compromisebetween high accuracy measurement of backscattering coeficient and relative high resolution should be considered.

Section I itroduces the system parameters and a burst pulse scheme.In section II,we analyze the azimuth signals,and introduce a rotating azimuth Doppler discrimination method. Section $\mathrm { I V }$ gives some simulations of point targets. Finally， the summary and conclusion remarks are given in Section V .

II．INSTRUMENTDESIGN OF THE SCANNING PENCIL-BEAM SCATTEROMETER

# A. System parameters

The DFPSCATon-board WCOM willobserve the Earth for 3 years froma sun-synchronous,near-circular orbit with an equator-crossing altitude near $6 0 0 ~ \mathrm { k m }$ at two frequencies with four polarization(VV,HH,VH, HV） [1O]. The space-borne scaningpencil-beamscaterometercanprovidehighsignal-to-noiseratio(SNR)andtheadvantageofcoveringalargerarea than SAR.The DFPSCAT instrument is a dual-frequency polarized radar scaterometer,which consists of a mechanically scanned radiometer with a $1 . 5 \mathrm { m }$ diameter reflector antenna, which can satisfy the requirement of high Signal Noise Ratio (SNR) and high gain. Some key specifications are shown in TABLE I.

The DFPSCAT instrument is based on a single reflector measuring up to $1 . 5 \times 1 . 5 \mathrm { m }$ ,illuminated by two adjacently placed feeds that generate themultiplebeams.Asinglerotatingantennaallowsalargerswathofmeasurementsataconstantincidenceangle.In order to get a ground swath of about $1 0 0 0 \mathrm { k m }$ ，the antenna incidence angle is at least $3 9 ^ { \circ }$ ，which is calculated by using the observationgeometrysee Fig.1.Considering the‘along-track continuityconstraint',therotationrate should be given by

$$
\Omega \geq \frac { \nu _ { g r o u n d } } { x _ { e l e \nu a t i o n } }
$$

where $\Omega$ is the antenna rotation rate, $\nu _ { g r o u n d }$ is theground velocityof the satellite and $x _ { _ { e l e \nu a t i o n } }$ is the elevation width of the footprint (about $2 3 \ \mathrm { k m }$ in Ku-band and $2 8 ~ \mathrm { k m }$ in $\mathrm { \Delta X }$ -band). The rotation rate should be at least 19 revolutions per minute (RPM) while considering achieving complete surface coverage over the swath. The antenna scanning loss is defined by

$$
L _ { s c a n } = \frac { \displaystyle \int g _ { t } \left( R \right) g _ { r } \left( R \right) d A _ { c } } { \displaystyle \int g _ { t } ^ { 2 } \left( R \right) d A _ { c } }
$$

where $g _ { t } ( R )$ and $g _ { r } ( R )$ are the beam patterns on the surface at the time transmit and receive. The integral range is the whole footprint.The scanninglossofareflectorantenna isrepresentedasafunctionof the beampaterns onthesurfaceatthe timeof transmitandreceive,seeFig.2.Thespeedoftefootprintduetotesatelitemotioninteazimuthdirectionisfarsallertanthe speed caused bythescaning motion,sothe scanning lossisanimportantconsideration. Given therapid scaning motionof the antenna,ananalysis basedontheradarambiguityfunctionisfoundtobeparticularusefulforthepencil-beamscaterometer.Here, the scanning lossis afunction of azimuth displacement normalized bythe two-way azimuth beam-width.Becauseof thesame transceiverantenna,the scanning lossshouldbecarefullycalculated.Whentheantenna rotates at19RPM,theantenna saning loss is about -1.3dB.

![](images/a8372ffe34e6aac65e735ef97477fdd1e6973afaceeb514733b73a098a2d30d0.jpg)  
Fig.1.Geometry of the DFPSCAT instrument conically scanning antenna beam mapping out a swath of $1 0 0 0 { \mathrm { k m } }$ at Earth's surface.The antenna footprint is represented by a small oval.

![](images/60e893b53ceb6d108ff8005b9ef1d856033f2afdb53d3c267a5e5449d438cc13.jpg)  
Fig.2. The scanning loss vs.antenna rotation rate.

TABLEI SYSTEMPARAMETERS   

<html><body><table><tr><td></td><td>X band</td><td>Ku band</td></tr><tr><td>Frequency</td><td>9.6 GHz</td><td>17 GHz</td></tr><tr><td>Wavelength</td><td>3.10 cm</td><td>1.76 cm</td></tr><tr><td>Bandwidth</td><td>2 MHz</td><td></td></tr><tr><td>Orbit height</td><td>600 km</td><td></td></tr><tr><td>Satellite velocity</td><td>7500 m/s</td><td></td></tr><tr><td>Antenna incidence</td><td>39°</td><td></td></tr><tr><td>Polarization</td><td>HH,VV,HV/VH</td><td></td></tr><tr><td>Antenna</td><td>scanning pencil-beam</td><td></td></tr><tr><td>Rotation rate</td><td>19 RPM</td><td></td></tr><tr><td>Antenna dimension</td><td>1.5 mx1.5 m</td><td></td></tr><tr><td>Swathwidth</td><td>>1000 km</td><td></td></tr><tr><td>Scanning loss</td><td>-1.3 dB</td><td></td></tr><tr><td>System loss</td><td>-5dB</td><td></td></tr><tr><td>System temperature</td><td>300 K</td><td></td></tr><tr><td>Peak power</td><td>200W</td><td>150 W</td></tr><tr><td>Antenna gain</td><td>42 dBi</td><td>47 dBi</td></tr><tr><td>Footprint</td><td>28.0 km(ele)x</td><td>23.0 km(ele)x</td></tr><tr><td></td><td>20.3 km(azi)</td><td>13.9 km(azi)</td></tr><tr><td>Resolution (after processing)</td><td colspan="2">2~5km</td></tr></table></body></html>

# B.Radar pulse repetition frequency

Theresolution of azimuth in traditional scaterometer is equal tothe azimuth footprint，which is verycoarse.Inorder to unambiguouslyresolve thescene inazimuth,thePRFshouldbeatleastlargerthanthe totalDopperbandwidthacross theazimuth footprint. For Ku-band,the azimuth footprint corresponds to a Doppler bandwidth of approximately $1 0 \mathrm { k H z }$ ,and thus a minimum $1 0 ~ \mathrm { k H z }$ PRF is required. Meanwhile,in order to avoid range ambiguities within the footprint, a maximum PRF of $9 . 4 6 ~ \mathrm { k H z }$ is required, corresponding to the beam fill time of about $0 . 1 0 6 ~ \mathrm { { m s } }$ .The resolution is only improved in one dimension for the traditional pulsedesign,soatradeoffbetweenrange ambiguitiesandazimuthambiguitiesshouldbeconsidered[1].One wayto resolve this problem is to use a burst pulsing scheme[6]. InFig.3,the echo returns are depicted as semicircles,and $\mathrm { T _ { i n t } }$ is the time interval of pulses in a transmit burst, $\mathrm { { T _ { b } } }$ is the length of the transmit burst, $\mathrm { { T _ { r e c } } }$ is the length of the receive burst. A multiple-pulse burst of length is repeated at the burst repetition interval (BRI).

The DFPSCATradar emits H-polarized and V-polarized pulse pairs at the burst repetition interval of approximately $2 5 0 ~ \mathrm { H z }$ which $\mathrm { { T _ { b } } }$ is $1 . 2 ~ \mathrm { m s }$ and $\mathrm { T _ { i n t } }$ is 75 microseconds,which is modulated to a linear modulation frequency (LFM) chirp of 2 MHz bandwidth. In a transmit burst, the radar emits $1 6 \mathrm { H }$ polarized and $1 6 \mathrm { V }$ polarized pulses.For the transmit burst, pulses will adopt diferentcarierfrequencyof theadjacentpulse.Intheprocessofechoreturnsreceived,pulses willbedistinguishedbyde-chirp method,s Fig.4.Ieceivewidow,therewillbseveralpseswithderetcarierfrquencies.Inteprocssofslation, the voltage of $\mathrm { H }$ polarization is double than V polarization. Although these pulses are overlapping in the time domain, the pulses can beseparatedbyusingareceive windowcorresponding todifferentcarrerfrequency2]. InFig.4(a),therearfivepulses in a receive window. The $V _ { e c h o 2 }$ is what we want inthis receive window. In the Fig. 4(b),the pulses are processd by using a simple lowpass filter, and such processng cannot compensate the phase variation or frequency shift [13]

![](images/74a9ad31a9aacf155c26aa7025cd1931a013075c04ba6385d5d727666711323f.jpg)  
Fig.3.Time series of radar transmit, reception,polarization.

![](images/a9d287695dea8e30cc356573bdf17a50c9b445cbc709cf8988d121f88f67dcfc.jpg)  
Fig.4.(a)pulses in a receive window,without filtering (b)after filtering.

# III.THE AZIMUTHRESOLUTION

The antenna of scatterometer is not only flying at the speed of about $7 5 5 0 \mathrm { m / s }$ ,but also rotates about the nadir axis at a stable rate. The roundtrip flight time for the beam pulse is approximately $5 . 2 6 ~ \mathrm { m s }$ ， which can cause a relatively large rotation angle of the antenna (about $0 . 6 ^ { \circ }$ ).The effective area iluminated by the antenna is defined by 3 dB bandwidth.If the dimension of an antenna is designed largeenough,theazimuthresolutioncanachieveseveral km,butalargeantenna willbrings great dificultiesto implement on-board.Inordertoachieve global seamless coverage,inthis paperapencil-beam antennais employed attherateof 19 RPM based on the along-track continuity constraint,as mentioned earlier.

# A．The analysis of azimuth resolution

Basedon thedesignofaburst pulsingscheme,thePRFcanreach abouten kHz.As previouslydiscussed,PRFshouldbe higher thantheDopplerbandwidthof-3dBfootprint.Errorscausedbythesatelite motionandorientationwilleadtotheerrors forthe Doppler centroidreal-timeestimation.However,this system hasahigh precisionof theorbit information.Theperformance requirementofthe atitudecontrol errorreaches O.O5degrees,and inactualytheatitudecontrol errorcanreachO.Odegrees. When the antenna is perpendicular to the flight direction (azimuth $_ { 1 = 9 0 }$ or 270 degrees),the system gets the maximum Doppler bandwidth,andtheiso-delayand iso-Dopplercontours arelocallperpendicular totheelevationandazimuthaxesrespectively. When the antenna scans to the forward or aft looking directions (azimuth $_ { = 0 }$ or 180 degrees), the iso-Doppler lines are parallel to the azimuthaxis.Ithiscase,theDopplerbandwidthoftheazimuthfootprintislmosero.Tusitisdiicultoachievehighaimuth resolutionhentheantenascanstotheforwardoraftlookingdirections.FromFig.5(a),thcross-trackdistance(CT)isdefied as the vertical distance between a given measurement and the nadir track.

As the antenna is rotating, the achievable azimuth resolution $\delta _ { a z }$ is defined as:

$$
\delta _ { a z } = \frac { R _ { 0 } \cdot \lambda } { 2 V _ { s a t } T _ { d w } } f \left( \theta _ { a z } \right)
$$

where $f \left( \theta _ { a z } \right)$ represents the degradation in the azimuth resolution due to squint elongation effects, $\theta _ { \mathrm { a z } }$ is the azimuth angular, $\lambda$ is the wave length, $R _ { 0 }$ is the slant range, $V _ { s a t }$ is the speed of the satellite,and $T _ { d w }$ is the effective dwell time,which is approximately one half of $T _ { b }$ . The dwell time is the reciprocal proportion to the Doppler resolution. The burst pulsing scheme comes at the priceofafactorof twoor three decrease inachievableazimuth resolution,compared with traditional pulsedesign. From Fig. 5(b), when the CTD is in the range 200 to $5 0 0 \mathrm { k m }$ ,the azimuth resolution can reach $2 \mathrm { k m }$ and when the CTD is about 80 km, the azimuth resolution can only reach $5 \mathrm { k m }$ .When the CTD is less than $8 0 \mathrm { k m }$ ,some other methods are used, which are not the focus in this paper [9].

![](images/43e067b0dc625ea2d06f3061bc97fc50c0ac1e0b84040c1e9b13cebb175a253c.jpg)  
Fig. 5. (a) Range-Doppler geometry of rotating radar beam. (b) the azimuth resolution with CTD

# B.Arotating azimuth Doppler discrimination

Theconicallyscanned pencil-eam antenna willrotate as it moves along theflight direction.Meantime,thesystem shouldmeet the requirements forreal-time processngandlong term data storage.Sothe processng algorithm must besimple and eicient, whichsuits the needsof real useon thesatelite.Theprocessing algorithm which iscalld“Rotating Azimuth Doppler Discrimination”, can meet the design requirements.

From geometry of the observation, the echoes return from a footprint can be written as:

$$
\begin{array} { r } { s _ { r } \left( t , \tau \right) = \underset { f o o t p r i \mathrm { i n t } } { \iint } \sigma \big ( r , x \big ) \cdot r \mathrm { e c t } \Bigg ( \frac { \tau - 2 R ( t ; r , x ) / c } { T _ { p } } \Bigg ) \cdot r e c t \Bigg [ \frac { t } { T _ { b } } \Bigg ] } \\ { \cdot \exp \Bigg [ j \frac { 4 \pi } { \lambda } R ( t ; r , x ) \Bigg ] \cdot \exp \Bigg \{ - j \pi \gamma \Bigg [ \tau - \frac { 2 R ( t ; r , x ) } { c } \Bigg ] ^ { 2 } \Bigg \} } \end{array}
$$

where rect $( t / T _ { p } )$ is a rectangular window, $\sigma ( r , x )$ is the backscattring coefficient of target $\scriptstyle ( r , x )$ ， $f _ { 0 }$ is the transmit carrier frequency, $T _ { p }$ is the width of the transmit pulse, $\gamma$ is the frequency modulation rate, $c$ is the speed of light, $\tau$ and $t$ is the time of range and azimuth, which is called ‘fast’ time and‘slow’ time, $R \big ( t ; r , x \big )$ is distance between the target and the transmiter.

FromFig. 6(a),the relations between the slow-time and frequency domain Doppler are described [14]. $B _ { d }$ is the target Doppler bandwidth, $T _ { d }$ is the dwell time of the target, $k _ { a }$ is the Doppler rate, and $k _ { r o t }$ is the Doppler centroid varying rate, which is given as follows:

$$
k _ { r o t } = \frac { \partial \big ( f _ { d c } ( t ) \big ) } { \partial t } = \frac { 2 V _ { s a t } \sin \big ( \theta _ { r o t } t \big ) \cdot \theta _ { r o t } \cdot \sin ( \theta _ { i n c } ) } { \lambda }
$$

where the $\theta _ { r o t }$ is the angular velocity, $\theta _ { i n c }$ is the antenna incidence angle. From Fig. 6 (a) and Fig. 6 (b) $B _ { d }$ is the maximum at

target S1 and S7, and $B _ { d }$ is the minimum at target S4. As the antenna is scanned forward or backward, the Doppler bandwidth and Doppler centroid will change nonlinearly.

![](images/2054ca1f67ff362379d72cc353ec44a3c6be9bb6ee6d5247dceb7e7d6d43a852.jpg)  
Fig. 6.(a) The raw-data support in the slow time/frequency (b) range migration

![](images/0786251d1b9f22b773ce97b59886aa3b47166f26603559e34714af7cd89c4987.jpg)  
Fig.7. The block diagram of the model.

The block diagramofthe modelisshowninFig.7[15].Thefirsttepis toremovethecarier frequencyfromrawdata,thenthe next step is toadoptthe de-chirp method by introducing azimuth product between the signal and the following chirp signal:

$$
H _ { 1 } = \exp \left[ j 2 \pi f _ { 0 } \tau _ { d } \right] \cdot \exp \left[ - j \pi \gamma \left( \tau - \tau _ { d } \right) ^ { 2 } \right]
$$

where $f _ { 0 }$ is the carrier frequency, $R _ { d }$ is the reference slant range, and $\tau _ { d } = 2 R _ { d } / c$

Then next three steps are to remove the residual video phase by using the range FFT, $H _ { 2 }$ and range inverse FFT, where $H _ { 2 }$ is given as follows:

$$
H _ { 2 } = \exp \biggl [ - j \pi \frac { f _ { r } ^ { ~ 2 } } { \gamma } \biggr ]
$$

where $f _ { r }$ is the frequency sampling in range direction.

# A．Point targets response analysis

The simulationparametersaredescribedinTABLEI.A groupof ransmitburstisused,andthis producesaPRFofabout13.3 kHz.The model is usedtoanalyzepointtargetsfirstlyforthe side-lookingcase,and then extendtheseresults tothecaseof an arbitraryazimuthangle.Thespacecraftnadironthesurfaceisdefinedasthecoordinate origin.Theflightdirectioncanbedefined as $\mathrm { \Delta } \mathrm { X }$ axis and the cross track direction is $\mathrm { \Delta Y }$ axis.When the azimuth angle is $9 0 ^ { \circ }$ ，two targets are $5 ~ \mathrm { k m }$ apart,which their coordinates can be given as: (-2.5e3,500e3, O), (2.5e3, 500e3) and two targets are $2 \mathrm { k m }$ apart, which their coordinates can be given as: (-1e3, 500e3), (le3,500e3), given in units of meter.

![](images/bf384fb6d458c36cdfb497eb594239498bcb7d97ccd73054455b09dcbe322b93.jpg)

![](images/c42423d78df008496f5dbd06534e9228acfd4b19cf66058adf47ca025f48bdba.jpg)  
Fig 8. (a) azimuth is $9 0 ^ { \circ }$ ， $5 \mathrm { k m }$ (b) azimuth is $9 0 ^ { \circ }$ ,2km

(c) azimuth is $6 0 ^ { \circ }$ ， $5 \mathrm { k m }$ (d) azimuth is $6 0 ^ { \circ }$ ， $2 \mathrm { k m } ( \mathbf { e } )$ azimuth is $3 0 ^ { \circ }$ ， $5 \mathrm { k m }$ (f) azimuth is $3 0 ^ { \circ }$ ，2km

From Fig 8, the targets which are $2 \mathrm { k m }$ apart can be distinguished by using the model when the azimuth is in the range 6O to 90 degrees,which is consistent with previous analysis. However, when the azimuth is $3 0 ^ { \circ }$ ,the targets which are $2 \mathrm { k m }$ apart can not beseparated becausethe Dopperresolutionis slightly largerthanthe Dopperbandwidth betweenthem.At the same scope ofthe azimuth,the larger the distance between the targets, the beter the separation capability.The transmit burst time is $1 . 2 ~ \mathrm { m s }$ corresponding to a scanning distance of $1 . 2 \mathrm { k m }$ .Thus the total coverage distance along the rotating direction in one burst time is about $1 5 ~ \mathrm { k m }$ .When the azimuth is $3 0 ^ { \circ }$ ,if the azimuth resolution is $5 ~ \mathrm { k m }$ ,then the scanning distance should be at least $1 0 ~ \mathrm { k m }$ Because theazimuth resolutionquicklydegrades nearthenadir rackbecauseoftheelongation efects,so whenthe azimuth is in the range 10 to $3 0 ^ { \circ }$ ,the azimuth resolution should be set to about $5 \mathrm { k m }$ ,Therefore,the azimuth resolution can reach $2 ~ \mathrm { k m }$ at far end of swath and $5 \mathrm { k m }$ at near end of swath.

# B. Communication error Kpc

ThecalculationofKpcfora pencil-beamrotating scatterometer maybequitecomplex,especiallfor thecombinedslices[16]. Thedetectedenergyfromseveralslicesissummed,andacompositecaibrationfactorisapped[17].Thenrmalizedstadard deviation of the $\sigma _ { 0 }$ estimate can be expressed as:

$$
K _ { _ { p c } } = \frac { 1 } { \sqrt { N _ { e l } N _ { a z } } } { \left( 1 + \frac { 2 } { S N R } + \frac { 1 } { S N R ^ { 2 } } \right) } ^ { 1 / 2 }
$$

where SNR is the signal-to noise ratio, $N _ { e l }$ is the number independent looks of the elevation,and $N _ { a z }$ is the equivalent number of azimuth looks.

![](images/2fd2094403b0d7dd4f9c7accaa5c5f3efdf7c0a50f00df98f9181e4d0295bb82.jpg)  
图9(a)5km combined slice，Kpc with footprint along the cross track (b)Kpc with snow thicknessusing diferentcombined slices

The simulationdatais basedonthe modelof the dense media radiative transfer (DMRT)[18].Wechoose the spatialresolution of a snow vector cell as $5 \mathrm { k m } \times 5 \mathrm { k m }$ and assume that the energy estimates are uncorrelated from slice to adjacent slice.From Fig. 9 (a) and (b),the Kpc willreduce with the snow accumulation,because of the higher SNR.When snow thickness exceeds $5 \mathrm { m }$ ,the Kpc of different combinedslices canreachO.4.Howeverthe Kpcisrelativelylargeat theshallowsnow for theSNR is low.The Kpc depends on the combination of the slice number,the slice size and the SNR.From Fig.9 (b),the Kpc of $3 ~ \mathrm { k m }$ and $5 ~ \mathrm { k m }$ combined slices is relatively small compared with $4 \mathrm { k m }$ combined slices.

# V．CONCLUSION

In this paper,a‘Rotating Azimuth Doppler Discrimination’ method is introducedandanalyzed,which canacquire azimuth resolution of $2 { - } 5 \mathrm { k m }$ at the far end of the swath and only $5 \mathrm { k m }$ at the near end of the swath. Some various options considered for improving the azimuth resolution are compared.A key design of the burst pulse scheme is proposed which can reach $1 3 . 3 \mathrm { \ k H z }$ （204号 (PRF). Because the scatterometer obtains a large swath of $1 0 0 0 ~ \mathrm { k m }$ in real-time and day or night, a rotating azimuth Doppler discriminationa techniqueinazimuth discriminationisemployed toimprove theresolution simplyand eficiently.Althoughthe azimuth resolution can reach a high level of $2 { \cdot } 5 \ \mathrm { k m }$ at the near end of the swath, the normalized standard deviation of the $\sigma _ { 0 }$ （20 estimate is relativelyhigh,which may exceed O.5.Aseries ofsimulations forthe point targets havebeenpresented to verifythe feasibilityand validityofthis method.Itshows thatthe scatterometercanobtainahighazimuth resolutionbyusing a‘Rotating AzimuthDopplerDiscrimination’method.Inthe future,thesimulationandexperimentusingdiferent parameters willbecarried out.

# REFERENCES

[3]Gall backscateringeeb"ocEf,ou,HJl-.   
[4] M.WSpenceudo"csisae Geosci. Remote Sens.,vol.38,no.1,pp.89-104,Jan.2000.   
[5] M.WSpenceueibateeE Trans. Geosci. Remote Sens.,vol.35,no.1, pp.115-126,Jan.1997.   
[6] M.W. Spencer, Amethodologforiofsaceboecateromeestes,"setatiepatlectricaldter Engineering,Brigham YoungUniversity,2001.   
[7] M.WSpencesdGg"gtsibcee discrimination techniques,"inIEEETrans.Geos.Remote Sens.,vol.41,no.3,pp.567-581,Mar.2003.   
[8] M.W. Spen r,TsaiWu-YangdGong,"soluaterometrlausaeolesriatio"inocEo. Honolulu,HI,2000,pp.3166-3168.   
[9] B.A.Williar Reconstruction fromaperture-filteredsamples withaplication tosaterometerimagereconstruction,"inIEEETrans.Geosci. Remote p.1663-1676,May.2011.   
10]J. Shi, retrieval using Xand Ku band dual-polarizationradar,"in Proc.IGARSS,Denver,CO,2Oo6,pp.2183-2185. .Fung,MicrowaveRemote SensingActive and Passive,vol.2,982,Addison-WesleyHouse.   
[12]Q.Ba nd X.Xu,"The feasibilityof ocean surface current measurement using pencil-beam rotating scattrometer,"in IEEE n Applied Earth Observations and Remote Sensing,vol.8,no.7,pp.3441-3451,Jul.2015.   
[13]W.Xu ,and X.Shang,"An eficient approach withscaling factors for TOPS-ModeSARdata focusing,"in IEEE Geosci.Remote .929-933,Oct. 2011.   
[14]A.Mor Mitermayer,"Azimuth andrange scalingforSARand ScanSAR processng,"inProc.IEEEInt.Geosci.Remote Sens.,Symp, coli 1214-1216.   
[15]D.G.I "Radar backscater measurement accuracy fora spaceborne pencil-beam wind scaterometer with transmit modulation,"in IEEETr .,vol.35,no.1,pp.102-114,Jan.1997.   
[16]X.Dong H.Liu,"Accuracyand resolutionanalysis ofthe pencil beamradar scaterometeronboard China'sHY-2satellte,"in IEEE Geosct 2007,pp.4467-4470.   
[17]Lsangde theory with multiple-scatering effects,"inIEEETrans.Geosci.Remote Sens.,vol.45,no.4,pp.990-1004,Apr.2007.