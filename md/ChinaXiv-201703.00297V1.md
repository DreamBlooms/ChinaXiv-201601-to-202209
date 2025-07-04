# A Novel Polarimetric Interferometric SAR Coherence Parameter and Its Application in Buildings Detection

Feiya Zhu1 ², Yunhua Zhangl1 ²,and Dong Lil

1 Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, China ²University of Chinese Academy of Sciences, China

Abstract- Man-made buildings detection is important in land use supervision and land control applications. Generally, polarimetric synthetic aperture radar (PolSAR) data are processed to detect buildings well But for some buildings which are not aligned with the radar track,these buildings are usually incorrectly recognized as forest，because the oriented buildings produce additional cross-polarization. Polarimetric interferometric SAR (PolINSAR) acquires two measurements with a spatial baseline or a temporal baseline.For the PolINSAR with a temporal baseline i.e.the repeat pass PolInSAR,the two polarimetric measurements are sensitive to targets’ temporal variations during the time.The buildings,regardless of the orientations,have high coherence,while some natural targets have low coherence.A novel parameter is proposed here, which represents the mean PolINSAR coherence and can be utilized to distinguish between buildings and some natural targets. The parameter is based on the coherence optimization theory of Cloude and Papathanassiou, and is the mean of the three optimal coherences with three pseudo-probabilities.Based on this new parameter and the SPAN，a method to detect buildings is further proposed. The excellent performance of the proposed method on buildings extraction is demonstrated by processing German Aerospace Center (DLR) L-band E-SAR repeat pass PolINSAR data of Oberpfaffenhofen area.

# 1.INTRODUCTION

Buildings detection is very important in land use supervision and land control applications.Based on the polarimetric synthetic aperture radar (PolSAR)data,polarimetric target decomposition (PTD) is often carried out to interpret the scatering mechanism of targets [1]-[8]. The PTD concept was proposed by Huynen [1],but Huynen PTD has not been widely applied due to its preference for symmetryand regulation [2]. Nowadays, the PTD is developed into two categories,i.e. the eigenvalue/eigenvector based decomposition and the model-based decomposition.Eigenvalue/eigenvector based decompositions extract physical meaningful parameters from the eigenvalues and eigenvectors of the coherency/covariance matrix [3],[4]. Model-based decompositions fit canonical scatering models to thecoherency/covariance matrix [5]-[8].Double-bounce scattring is generally induced by buildings due to the specular scatering.Both the two categories of PTD successfully characterize the double-bounce scattering.But when the buildings are not aligned with the radar track，additional cross-polarization willbe introduced while the corresponding double-bounce scattring willbe reduced.Thus, the buildings may be misclasified as forest of which the cross-polarization dominates.Deorientation process is often implemented prior to model-based PTD to alleviate this situation [6],[9]-[11],and to some extent the deorientation works wel.But for the buildings which are largely aligned with radar track,buildings may stillbe misclassified as forest even with deorientation conducted [11].

PolSAR interferometry (PolINSAR) is a popular technique which has been mainly used to generate terrair digital elevation model (DEM) and estimate physical parameters [12],[13].PolINSAR collects data with & spatial baseline or a temporal baseline.For the PolINSAR with a temporal baseline,i.e.the repeat pass PolINSAR,the two measurements are sensitive to the temporal variations of the targets.The coherence of man-made buildings is high regardless of the orientations of the buildings while the coherence of some natural targets,such as the coherence of the forest,is relatively low.Thus,the repeat pass PolINSAR coherence can be utilized for buildings detection. A mean PolINSAR coherence parameter is proposed in this paper.The parameter measures the coherence of the targets,and is the mean of the three optimal coherences of the coherence optimization theory[12],[13]. Uniting the proposed mean PolINSAR coherence parameter and the SPAN (total power),a building detection method is proposed.

# 2.MEAN POLINSAR COHERENCE PARAMETER

The proposed mean PolINSAR coherence parameter measures the polarimetric scattering coherence from targets between two measurements by repeat pass PolINSAR.It is based on the coherence optimization theory of Cloude and Papathanassiou [12],[13].

The repeat pass PolINSAR acquires two polarimetric scattering matrices $S _ { 1 }$ and $S _ { 2 }$ . Via the two scattering matrices $S _ { 1 }$ and $S _ { 2 }$ ，the corresponding scattering vectors $k _ { 1 }$ and $k _ { 2 }$ in Pauli basis can be obtained.The $6 { \times } 6$ PolINSAR coherency matrix $T _ { 6 }$ is represented by

$$
T _ { 6 } = \left. { \left[ \begin{array} { l } { k _ { 1 } } \\ { k _ { 2 } } \end{array} \right] } { \left[ \begin{array} { l l } { k _ { 1 } ^ { * T } } & { k _ { 2 } ^ { * T } } \\ { k _ { 2 } } & { T _ { 2 } } \end{array} \right] } \right. = { \left[ \begin{array} { l l } { T _ { 1 1 } } & { \Omega _ { 1 2 } } \\ { \Omega _ { 1 2 } ^ { * T } } & { T _ { 2 2 } } \end{array} \right] }
$$

where the superscript \* denotes complex conjugate,and $\left. < \cdot > \right.$ denotes ensemble averaging. The three $3 { \times } 3$ matrices $T _ { 1 1 } , \Omega _ { 1 2 }$ ,and $T _ { 2 2 }$ are respectively

$$
{ \cal T } _ { 1 1 } = \Big \langle k _ { 1 } k _ { 1 } ^ { * T } \Big \rangle , \Omega _ { 1 2 } = \Big \langle k _ { 1 } k _ { 2 } ^ { * T } \Big \rangle , { \cal T } _ { 2 2 } = \Big \langle k _ { 2 } k _ { 2 } ^ { * T } \Big \rangle .
$$

[wo unitary complex projection vectors $\omega _ { 1 }$ and $\omega _ { 2 }$ are defined，and then the coherence can be generally xpressed as [13], [14]

$$
\gamma = \frac { \left| \left. \omega _ { 1 } ^ { * T } \left[ \Omega _ { 1 2 } \right] \omega _ { 2 } \right. \right| } { \sqrt { \left| \left. \omega _ { 1 } ^ { * T } \left[ T _ { 1 1 } \right] \omega _ { 1 } \right. \right| \left| \left. \omega _ { 2 } ^ { * T } \left[ T _ { 2 2 } \right] \omega _ { 2 } \right. \right| } } .
$$

In order to determine which combination of $\omega _ { 1 }$ and $\omega _ { 2 }$ leads to the maximum coherence,Cloude and Papathanassou proposed a method to optimize the coherence.Detailed information about the coherence definition and optimization can be found in[12] and[13].The coherence optimization problem is transformed to two eigenvalue/eigenvector problems as follows

$$
\begin{array} { r l } & { T _ { 2 2 } ^ { - 1 } \Omega _ { 1 2 } ^ { * T } T _ { 1 1 } ^ { - 1 } \Omega _ { 1 2 } \omega _ { 2 } = \upsilon \omega _ { 2 } } \\ & { T _ { 1 1 } ^ { - 1 } \Omega _ { 1 2 } T _ { 2 2 } ^ { - 1 } \Omega _ { 1 2 } ^ { * T } \omega _ { 1 } = \upsilon \omega _ { 1 } } \end{array}
$$

By solving the above the first eigenvalue/eigenvector problem, three eigenvectors,i.e. $\omega _ { 2 1 } , \omega _ { 2 2 }$ ，and $\omega _ { 2 3 }$ ，and three eigenvalues $\upsilon _ { 2 1 } , \upsilon _ { 2 2 }$ ,and $\upsilon _ { 2 3 }$ are obtained. By solving the second eigenvalue/eigenvector problem, another three eigenvectors, i.e. $\omega _ { 1 1 } , \ \omega _ { 1 2 }$ and $\omega _ { 1 3 }$ ， and three eigenvalues, i.e. $\upsilon _ { 1 1 } , \upsilon _ { 1 2 }$ ，and $\upsilon _ { 1 3 }$ ，are obtained. The three optimal coherence can be obtained as

$$
\gamma _ { i } = \frac { \left| \left. \omega _ { 1 i } ^ { * T } \left[ \Omega _ { 1 2 } \right] \omega _ { 2 i } \right. \right| } { \sqrt { \left| \left. \omega _ { 1 i } ^ { * T } \left[ T _ { 1 1 } \right] \omega _ { 1 i } \right. \right| \left| \left. \omega _ { 2 i } ^ { * T } \left[ T _ { 2 2 } \right] \omega _ { 2 i } \right. \right| } } , i = 1 , 2 , 3
$$

Similar to the average alpha angle of Cloude-Potier decomposition [3],the mean PolINSAR coherence parameter is defined as

$$
\overline { { \gamma } } = p _ { 1 } \gamma _ { 1 } + p _ { 2 } \gamma _ { 2 } + p _ { 3 } \gamma _ { 3 }
$$

where $p _ { 1 } , p _ { 2 }$ ，and $p _ { 3 }$ are the corresponding pseudo-probabilities with $\scriptstyle p _ { i } = { \upsilon _ { 1 } } _ { i } / ( \upsilon _ { 1 1 } + \upsilon _ { 1 2 } + \upsilon _ { 1 3 } )$ . The physical basis is that $\forall _ { 1 } , ~ \forall _ { 2 }$ ，and $\gamma _ { 3 }$ occurs with pseudo-probabilities $p _ { 1 } , p _ { 2 }$ ，and $p _ { 3 }$ ，respectively. Thus,the mean PolINSAR coherence parameter is a best estimate of $\gamma _ { 1 } , \gamma _ { 2 }$ ,and $\gamma _ { 3 } \left[ 3 \right]$

The proposed mean PolINSAR coherence parameter of (6) can be generally used to measure the coherence o.   
the targets for repeat pass PolINSAR.

# 3.BUILDINGSDETECTION METHOD

Proposed mean PolINSAR coherence parameter and SPAN (total power) are jointly utilized to detect buildings from the repeat passPolINSAR data.The SPAN is the total power of the two measurements, which is defined as

$$
S P A N = t r a c e ( T _ { 1 1 } ) + t r a c e ( T _ { 2 2 } )
$$

1: Compute the SPAN of the repeat pass PolINSAR data;   
2: Compute the mean PolINSAR coherence parameter of the repeat pass PolINSAR data;   
3: If SPAN $>$ Threshold 1 If $\bar { \gamma } >$ Threshold 2 Recognized as building; End if; End if;

As shown in Figure 1,the SPAN and the mean PolINSAR coherence parameter are first calculated.For each pixel,compare the SPAN with the threshold1.If the SPANof the pixel is greater than the threshold1,this pixel should be further investigated using the mean PolINSAR parameter. Then, if the mean PolINSAR parameter is greater than the threshold 2 as well, this pixel is recognized as building.

# 4EXPERIMENTSVALIDATION

In this section,the buildings detection algorithm is validated with real repeat pass PolINSAR data.The data used were collected by German Aerospace Center L-band repeat pass PolINSAR E-SAR from Oberpfafenhofen area. The temporal baseline is within one day.Figure 2(a) shows the Google Earth optical image as the reference. Figure 2(b) shows the SPAN image where the white color represents the high SPAN.As can be seen the forest and buildings generally induce high SPAN.Forest induces high SPAN part due to the random scattering from the canopy and part due to the ground-trunk double-bounce scatering. Buildings induce high SPAN due to the ground-wall double-bounce scatterings.Figure 2(c) is the SPAN based detection result， where the pixels are coded white or black if the SPAN is greater or smaller than the threshold 1.Forest and buildings are simultaneously detected. By only utilizing SPAN information we cannot successfully extract buildings.

Figure 2(d) shows the mean PolINSAR coherence image,where white color indicates high mean PolINSAR coherence.Wecan clearly see that the buildings have high mean coherence while the forest reasonably has low mean coherence because of the temporal decorrelation.Figure 2(e) shows the histograms of the mean PolINSAR coherence of two selected patches,i.e.forest and one oriented building of the airport,which are marked as patch 1 and 2 in Figure 2(a).Figure 2(e) shows that the mean PolINSAR coherence can be used to wellseparate the forest and the building.Figure 2(f) is the mean PolINSAR coherence based detection result, where one pixel is coded white or black if their mean PolINSAR coherence is larger or smaller than threshold 2.The buildings are successfully detected,such as the oriented isolated buildings of the airport.Except for the buildings,large areas of Bragg surface scatering also have high coherence.These areas are farmlands with sparse short grass or without crops. Only utilizing mean PolINSAR coherence cannot successfully extract buildings.

Figure 2(g) shows the detection result by the proposed method. It can be seen that the buildings are generally detected,such as the oriented isolated buildings of the airport. Compared to Figure 2(c),the proposed method removes the forest area which are with high SPAN,because the mean coherence value is low for forest. Compared to Figure 2(f),the proposed method removes the Bragg scattering areas although they are of high mean coherence, because the SPAN value is low.

It is worth noting that two lines in the two red circles of Figure $2 ( \mathrm { g ) }$ are wrongly detected as buildings,which may be the potential deficiency of the proposed method. Actually, the two lines are the fences on the roads,and they also induce high SPAN and high mean coherence.In addition,although there is no building reference data in hand,we can refer to the Google Earth optical image,by doing so the detection result still can be used to demonstrate the effectiveness of the proposed method.

# 5 CONSLUSION

The mean PolINSAR coherence is proposed as a general parameter to measure the coherence of the targets for repeat pass PolINSAR.The buildings have high coherence between two measurements.A buildings detection method based on the mean PolINSAR coherence and SPAN is proposed. By processing repeat pass PolINSAR data,we validates the buildings detection method.The potential deficiency of the method is also addressed.

# REFERENCES

1．Huynen，J.R.“Phenomenological theory of radar targets,”Ph.D.Dissrtation，Delf University of Technology,Delft, The Netherland,1970.   
2.Li,D. and Y.H. Zhang,“Unified Huynen phenomenological decomposition of radar targets and its classification applications,” IEEE Trans. Geosci. Remote Sens,Vol.54, No.2,723-743,2016.   
3.Cloude,S.R.and E.Potier,“A review of target decomposition theorems in radar polarimetry,” IEEE Trans. Geosci. Remote Sens, Vol.34, No.2, 498-518, 1996.   
4.Van Zyl,J.J.,M. Ari,and Y. Kim,“Model-based decomposition of polarimetric SAR covariance matrices constrained for nonnegative eigenvalues,” IEEE Trans. Geosci. Remote Sens,Vol. 49,No.9,1104-1113,   
2011.   
5.Freeman, A. and S.L. Durden,“A three-component scatering model for polarimetric SAR data” IEEE Trans. Geosci. Remote Sens, Vol. 36, No. 3, 963-973,1998.   
6.An, W.T.,Y. Cui,and J. Yang,“Three-component model-based decomposition for polarimetric SAR data,” IEEE Trans. Geosci. Remote Sens,Vol. 48,No.6,2732-2739,2010.   
7.Yamaguchi，Y.，T.Moriyama,，M.Ishido，and H. Yamada，‘Four-component scatering model for polarimetric SAR image decomposition,” IEEE Trans. Geosci. Remote Sens,Vol. 43, No.8,1699-1706, 2005.   
8.Cui,Y.，Y. Yamaguchi,J. Yang，H.Kobayashi, S.Park,and G. Singh，“On complete model-based decomposition of polarimetric SAR coherency matrix data,” IEEE Trans. Geosci. Remote Sens, Vol.52, No. 4,1991- 2001,2014.   
9.Lee,J. S., D.L. Schuler,and T.L. Ainsworth,“Polarimetric SAR data compensation for terrain azimuth slope variation,” IEEE Trans. Geosci. Remote Sens, Vol.38,No.5, 2153-2163, 2000.   
10.Xu,F.and Y. Q. Jin,“Deorientation theory of polarimetric scatering targets and application to terrain surface classification,” IEEE Trans. Geosci. Remote Sens, Vol.43, No.10,2351-2364,2005.   
11.Chen，S.W.，M. Ohki，M. Shimada,and M. Sato,“Deorientation efect investigation for model-based decomposition over oriented built-up areas,” IEEE Geosci. Remote Sens.Lett， Vol.10,No.2, 273-277, 2013.   
12. Cloude,S.R.and K.P.Papathanasiou,“Polarimetric SAR interferometry,” IEEE Trans. Geosci. Remote Sens,Vol. 36, No.5, 1551-1565,1998.   
13.Papathanassiou,K.P.and S.R.Cloude,“Single-baseline polarimetric SAR interferometry,” IEEE Trans. Geosci. Remote Sens,Vol.39,No. 11,2352-2363,2001.

![](images/012666e9efe1ef9a3782f88c89c895ae37dc67a66a5a858640e059d72817ca1c.jpg)  
Figure 2.(a) Google Earth optical image; (b) SPAN image; (c) SPAN based detection result image. (d) The mean PolINSAR coherence parameter; (e) Histograms of the mean PolINSAR coherence of the selected forest and building patches. (f) The mean PolINSAR coherence parameter based detection result image. (g) The buildings detection result of the proposed method