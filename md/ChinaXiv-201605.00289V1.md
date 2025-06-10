# ANUNFOCUSEDSARDESIGNTO IMPROVE AZIMUTHRESOLUTIONOFDUALFREQUENCYFULL-POLARIZEDSCATTEROMETER

Gang Wang $^ { 1 , 2 }$ ,Xiaolong Dong' ,Qingliu Baol, ²,Di Zhu', Xingou Xul

1． CAS Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences,Beijing,100190, China 2.University of Chinese Academy of Sciences, Beijing,10o049, China. Email: wangganggreat@163.com

# ABSTRACT

In order to satisfya high resolution for the measurement of snow water equivalent,we use the system of using the dual frequency(X-band 9.6GHz and Ku-band 17GHz）and full polarization. This paper discusses the various system options(scanning pencil-beam,high PRF,high SNR）and tradeoffs considered for improving the azimuth resolution of scatterometer are required.

Index Terms— Unfocused SAR,Doppler,azimuth, Scatterometer

can be used to ensure coherent accumulation without correction.Because the secondary phase item is no more than $\pi / 2$ ,the coherent accumulation time should satisfy:

$$
T _ { s } \le { \frac { 1 } { V _ { s a t } } } \sqrt { \lambda R _ { 0 } / ( 1 - { \bf c o s } _ { \gamma } ^ { 2 } \sin _ { \varphi } ^ { 2 } ) }
$$

where $\varphi$ is the angle between satellite nadir point and antenna direction, $\gamma$ is antenna azimuth angle.The error of phase center is small enough that the targets do not have migration through resolution cell, thus

# 1.INTRODUCTION

$$
T _ { s } < \frac { c } { 2 B V _ { s a t } \cos \gamma _ { \scriptscriptstyle 0 } \sin \varphi }
$$

WCOM(Water Cycle Observation Mission） proposes an X/Ku band dual-frequency full-polarized SCATterometer (DFPSCAT)with a resolution of $2 { \sim } 5 \mathrm { k m }$ and an $1 0 0 0 \mathrm { k m }$ swath for mapping of snow water equivalent and freezethaw processes [1]. The retrieval error of snow water equivalent is very high when the resolution is more than $1 0 \mathrm { k m }$ ，so the resolution of the system is required to be $2 { \sim } 5 \mathrm { k m }$ [2].For the spaceborne scanning pencil-beam scatterometer, the azimuth resolution is $2 0 { - } 5 0 ~ \mathrm { k m }$ that could not meet the demands.Based on the motion of platform and thescanning rulesof the spacebornescatterometer, therefore an unfocused synthetic aperture radar (SAR） is designed to improve the Azimuth Resolution. Toachieve an improved resolution along the azimuth direction,the system will use an unfocused synthetic aperture design where the Doppler effect is exploited to synthesize a longer aperture,as well as super-resolution reconstruction by oversampling in the direction of the azimuth. Considering high accuracy measurement of backscattering coefficient and relative high resolution of the snow water equivalent measurement,the system parameters should be a compromise between these two variables during the system design ofDFPSCAT.

# 2.SYSTEMDESIGN

According to the echo signal property of the target, the secondaryphase itemof Taylor series for the echo equation

A general goal in this design is to make sure the numbers of the beam sharpening ratio are stable,which can be achieved by two methods:1） changing PRF following the antenna rotates but the numbers of accumulation pulse are stable; 2) changing the numbers of accumulation pulse following the antennarotates,but the PRFisstable.

The spaceborne scanning pencil-beam scatterometer can provide high signal-to-noise ratio (SNR),but shorter dwell time and it does have the advantage of covering a larger cover area than SAR.DFPSCAT will use pulse compression by linear frequency modulation along the elevation direction,which provides range resolution of about $5 0 \mathrm { m }$ 1 $\mathrm { \Delta B = 5 M H z } ,$ and $2 5 \mathrm { m }$ 0 $\scriptstyle \mathbf { B } = 1 0 \mathbf { M } \mathbf { H } z ^ { \prime }$ .Giventhatthe requirement of resolutionis $2 { \sim } 5 \mathrm { k m }$ ，the area could theoretically be resolved into asmanyas 40 or1oO separate elements,each constituting one independent samples,and correspondingto a normalized-measurement standard deviation of $1 / \sqrt { 4 0 }$ and 1/10 [3].

Considering the engineering realization,we usually use the second method employing constant PRF and rotation rate to change the numbers of the accumulation pulse following the antenna rotates.Each target radial velocity relative to the radar is different,so the beam may have the frequency difference of arrival.The unfocused SAR design should not be used when the azimuth is near along-track.At the far swath,the footprint of azimuth corresponds to a Dopplerbandwidthofapproximately $1 0 ~ \mathrm { k H z }$ ，while atnear swath this corresponds to a Doppler bandwidth of about 5.5 kHz.Thus a minimum $1 0 ~ \mathrm { \ k H z }$ PRFis required to unambiguously resolve the scene in azimuth.To avoid range ambiguities within the footprint,this requiresa maximum PRF of $8 ~ \mathrm { { k H z } }$ ，corresponding to the beam fill time of about O.13ms.[4] The resolution is only improved in one dimension,thus we should design the PRF with a tradeoffbetween rangediscriminationand azimuth resolution.

To acquire high resolution in azimuth direction,the rotation rate should be designed small,and meanwhile satisfies the no gap coverage of the footprint, which implies a minimum rotation rate of $2 7 \mathrm { r p m }$ .The antenna dimension is $1 . 5 \mathrm { m } { \times } 1 . 5 \mathrm { m }$ ，achieving a suficiently narrow beamwidth. Some key specifications are shown in Table 1.

Table1.System Parameters   

<html><body><table><tr><td>Frequency</td><td colspan="2">9.6GHz</td></tr><tr><td>Wavelength</td><td colspan="2">3.1cm</td></tr><tr><td>Bandwidth</td><td colspan="2">5MHz</td></tr><tr><td>Orbit height</td><td colspan="2">600km</td></tr><tr><td>Peak power</td><td colspan="2">200W</td></tr><tr><td>Polarization</td><td colspan="2">150W HH, VV, HV/VH</td></tr><tr><td>Antenna dimension</td><td colspan="2">1.5m×1.5m</td></tr><tr><td>Antenna incidence</td><td colspan="2">39°</td></tr><tr><td>Antenna</td><td colspan="2">scanning pencil-beam</td></tr><tr><td>Swath</td><td colspan="2">>1000km</td></tr><tr><td>Resolution</td><td colspan="2">2~5km</td></tr><tr><td>after processing Raw resolution (B=5MHz)</td><td colspan="2">47.6m(ele)x 47.6m(ele)x 16.4km(azi) 12.04km(azi)</td></tr></table></body></html>

As the antenna rotates,the DFPSCAT radar emits Hpolarized and V-polarized pulse pairs at a pulse-repetition frequency of approximately $6 6 6 7 \mathrm { H z }$ Each pulse is 45us in length,and is modulated to a linear-FM chirp of $5 ~ \mathrm { { M H z } }$ bandwidth.During the transmit time(approximately $4 . 8 \mathrm { m s } \dot { }$ ）, the radar emits $3 2 \mathrm { ~ H ~ }$ -polarized and V-polarized pulses without echoes.The frequency of H-polarized and $\mathrm { v } .$ polarized isdifferent, $f _ { H }$ and $f _ { \scriptscriptstyle V }$ ，and separated by $3 \mathrm { { M H z } }$ (Figure1） to be distinguished duringtheir simultaneous reception.

The resolution cell is observed by several pulses during the transmit time and matched by multi-look technique using the information of antenna direction and orbit geometry (Figure 2).

![](images/797f0c89c63a36101333798427745c3ee8a567b371aa40ffb806023ca0199e40.jpg)  
Figure 1 Time series of radar transmit,reception, polarization

![](images/624e5425504d601867bbd3022a0038fba126f02c905856580f26dfcc3bd76cad.jpg)  
Figure 2.Multi-look processing

# 3.SIMULATION

Owing to the limitation of range ambiguities, the maximum PRF is 8kHz.When the antenna rotation rate is $2 7 ~ \mathrm { r p m }$ ，the numbers of coherent accumulation pulse shouldbe calculatedby the PRF and satellitevelocity.The numbers of coherent accumulation pulse can be 16 or 32,which is suited to do FFT processing(Table 2). The maximum length of the unfocused synthetic aperture is given by $\sqrt { R \lambda / 2 }$ ,where $R$ is the distance between the satellite and the target, implying the maximum integration time of about 8ms.The transmit pulses consist 32 pulses every 15Ous and this produces a PRFof about $6 . 6 7 \mathrm { k H z }$ oneach beam individually.Transmit pulses last about $4 . 8 \mathrm { m s }$ and the roundtrip flight time is approximately $5 . 3 2 \mathrm { m s }$ .Due to the motion of the radar relative to the earth and the rotation of the antenna,the Doppler shift brings great difficulties for the processing of unfocused SAR,especially when the azimuth is near $0 ^ { \circ } ~ \pm 1 5 ^ { \circ }$ or $1 8 0 ^ { \circ } + 1 5 ^ { \circ }$ (the Doppler shift is largest and the Doppler bandwidth is near O,so a method called super-resolution can be used).

Case 1, $9 0 ^ { \circ }$ Azimuth: see Figure 3.(a). The Doppler shift is approximately $5 \mathrm { k H z }$ ， Case 2, $6 0 ^ { \circ }$ Azimuth:see Figure 3.(b). The Doppler shift is approximately $2 1 0 \mathrm { k H z }$ ： Case 3, $4 5 ^ { \circ }$ Azimuth: see Figure 3.(c). The Doppler shift is approximately $3 0 0 \mathrm { k H z }$ ， Case 4, $3 0 ^ { \circ }$ Azimuth: see Figure 3.(d). The Doppler shift is approximately $3 7 0 \mathrm { k H z }$ ：

Table2.NumbersofCoherent Accumulation Pulse inDifferentPRF   

<html><body><table><tr><td>PRF(kHz)</td><td>Numbersof coherent accumulation pulse</td></tr><tr><td>4</td><td>35</td></tr><tr><td>5</td><td>44</td></tr><tr><td>6</td><td>52</td></tr><tr><td>7</td><td>61</td></tr></table></body></html>

![](images/fa10a0c2b1c17afa12acdaf35e130a763bbf43e2eb45c0919b4e9d1d5ffcfb60.jpg)

![](images/32548580eceab40b08d2fa41964a8e2c27ce03a3fba0361eaee622ae357dc0e3.jpg)  
Figure 3.Different targets using Doppler and range discrimination

# 4.CONCLUSION

An unfocused SAR processing design is introduced in this paper,which can acquire azimuth resolution of $2 { \sim } 5 ~ \mathrm { k m }$ In the next work, the important thing is to keep the numbers of the beam sharpening ratio stable,although the azimuth changes all the time.In this paper,the various options considered for improving the azimuth resolution are simulated.In the future,the simulation using different parameters will be carried out.

# 5.REFERENCES

[1] Dong X,Liu H,Wang Z,et al.WCOM: The mission concept and payloads of a global water cycle observation mission[C]. Geoscience and Remote Sensing Symposium (IGARSS),2014 IEEEInternational.IEEE,2014:3338-3341.

[2] Shi J. Snow Water Equivalence Retrieval Using X and $\mathrm { K u }$ band Dual-Polarization Radar[C]. Geoscience and Remote Sensing Symposium,IGARSS,IEEE International Conference on.IEEE, 2006:2183 - 2185.

[3]M W Spencer,C Wu,D G Long,et al.Improved Resolution Backscatter Measurements with the SeaWinds Pencil-Beam Scatterometer [J].IEEE Transactions on Geoscience and Remote Sensing,2000,38(1):89-104.

[4]DG Long,C-Y Chi and F K Li.The Design of an Onboard Digital Doppler Processor for a Spaceborne Scatterometer [J]. IEEE Transactions on Geoscience and Remote Sensing,1988, 26(6): 869-878.