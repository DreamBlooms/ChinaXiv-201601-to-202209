# MODEL-BASEDDECOMPOSITION WITH ADAPTIVE SELECTION OFUNITARY TRANSFORMATIONS

Feiya Zhul, Yunhua Zhang²,Dong $L i ^ { 3 }$ and Xiang Gu4

1,2.4The KeyLabofMicrowave Remote Sensing,Centerfor Space Science and Applied Research Chinese Academy of Sciences, Beijing 100190, China; 1University of Chinese Academy of Sciences,Beijing 10049, China;

zhufeiyal99o@ gmail.com, zhangyunhua@mirslab.cn, lidong @mirslab.cn and guxiang@mirslab.cn

Keywords:polarimetric synthetic aperture radar,modelbased decomposition,unitary transformation,helix angle, orientation angle.

# Abstract

In this paper a three component model-based decomposition with adaptive selection of unitary transformations for polarimetric synthetic aperture radar(POLSAR) data processing is proposed. Singh et al implemented two unitary transformations on the coherency matrix to minimize the power of cross-polarization,and as a result the $T _ { 2 3 }$ element of the coherency matrix becomes zero.Another two unitary transformations are proposed by us to carry out on the coherency matrix also to minimize the power of crosspolarization,and the $T _ { 1 3 }$ element of the coherency matrix becomes zero.Here,we first implement Singh's two unitary transformations and the proposed two unitary transformations on the coherency matrix separately. Then we select the one which leads to the smaller $T _ { 3 3 }$ . At last, we carry out the three component model-based decomposition proposed by Freeman and Durden based on the obtained coherency matrix. The smaller $T _ { 3 3 }$ is obtained, the better the over-estimation of volume scattering in model-based decomposition can be suppressed. The RADARSAT-2 POLSAR data of San Francisco area is used to validate the improvement of the proposed method over the three component decomposition only with Singh's two unitary transformations.

# 1 Introduction

In the research area of polarimetric synthetic aperture radar(POLSAR） target decomposition，model-based decomposition is always a hot topic.The pioneering work in model-based decomposition is the three component decomposition proposed by Freeman and Durden [1]. They decompose the covariance matrix of POLSAR data into three components,i.e.the surface scattering component, the double-bounce scattering component,and the volume scattering component. The surface scattering occurs on some Bragg surface,and the double-bounce scattering happens when the electromagnetic wave is scattered by ground-wall dihedral or ground-trunk dihedral,and the volume scattering happens when the target is the canopy, respectively.However,when the target is azimuth modulated[2] or when the dihedral does not aligned in the direction of the flight track[3,4], the cross-polarization will occur.As the azimuth modulated surface and the oriented dihedral will introduce additional cross-polarization,the volume scattering estimated from cross-polarization is often over estimated. Yamaguchi et al proposed a decomposition approach,i.e. the four component decomposition, by adding a helix term to alleviate the over-estimation of volume scattering [5]. Orientation angle compensation (OAC)was also implemented on POLSAR data and after which the cross-polarization power was decreased [2,3,4]. Except for OAC,Singh et al further implemented another unitary transformation on the coherency matrix also to minimize the power of the cross-polarization ( $T _ { 3 3 }$ element) [6].After this,there are seven degrees of freedom out of nine left in the coherency matrix,and the four component decomposition was carried out by Singh et al. So five of seven degrees of freedom were accounted.The two unaccounted degrees of freedom are the real and imaginary parts of $T _ { 1 3 }$ element,respectively.As mentioned in [6], these two degrees of freedom still remain unaccounted in any known model-based decompositions.

In fact,except for orientation angle, the helix angle also contributes to the power of cross-polarization.We can verify this point by the helix term of the four component decomposition. The helix term of the four component decomposition is

$$
T _ { h e l i x } = \left[ \begin{array} { c c c } { { 0 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { 1 } } & { { \pm j } } \\ { { 0 } } & { { \pm j } } & { { 1 } } \end{array} \right]
$$

Yamaguchi et al included this term in their decomposition. but this term was not displayed in the decomposition resulted color-coded image.In this paper,we propose a helix compensation operation for the coherency matrix, inspired by applying OAC to the coherency matrix,which is accomplished by a unitary transformation to minimize the $T _ { 3 3 }$ element.Then another unitary transformation is also carried out to minimize the $T _ { 3 3 }$ element for the coherency matrix following the first unitary transformation (helix compensation).After these two unitary transformations the $T _ { 1 3 }$ element becomes zero.We implement Singh's two unitary transformations and the two proposed unitary transformation on the coherency matrix separately. Then the smaller $T _ { 3 3 }$ element of the obtained two coherency matrices are preferred,and the corresponding two unitary transformations are selected.At last the FDD is carried out on the obtained coherency matrix after the alternative unitary transformations.The proposed method has an improvement in alleviating the over-estimation of volume scattering than applying the FDD only with the Singh's twounitary transformations.

# 2 FDD

The coherency matrix of a target can be expressed as

$$
T = { \left[ \begin{array} { l l l } { T _ { 1 1 } } & { T _ { 1 2 } } & { T _ { 1 3 } } \\ { T _ { 1 2 } ^ { * } } & { T _ { 2 2 } } & { T _ { 2 3 } } \\ { T _ { 1 3 } ^ { * } } & { T _ { 2 3 } ^ { * } } & { T _ { 3 3 } } \end{array} \right] }
$$

where $*$ denotes complex conjugation.

The coherency matrix can also be expressed using Huynen's nine parameter[7] as

$$
T = \left[ \begin{array} { c c c } { { A } } & { { C - j D } } & { { H + j G } } \\ { { C + j D } } & { { B _ { 0 } + B } } & { { E + j F } } \\ { { H - j G } } & { { E - j F } } & { { B _ { 0 } - B } } \end{array} \right]
$$

The coherency matrix of a target under reflection symmetry assumption can be decomposed into three components as [1,3]

$$
T = P _ { S } T _ { S } + P _ { D } T _ { D } + P _ { V } T _ { V }
$$

The model of the three components can be expressed a:

$$
\begin{array} { r l } { T _ { S } = \cfrac { 1 } { 1 + \left| \beta \right| ^ { 2 } } \left[ \begin{array} { c c } { 1 } & { \beta ^ { * } } & { 0 } \\ { \beta } & { \left| \beta \right| ^ { 2 } } & { 0 } \\ { 0 } & { 0 } & { 0 } \end{array} \right] } & { } \\ { T _ { D } = \cfrac { 1 } { 1 + \left| \alpha \right| ^ { 2 } } \left[ \begin{array} { c c } { 1 / 2 } & { \alpha } & { 0 } \\ { \alpha ^ { * } } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 0 } \end{array} \right] } & { } \\ { T _ { V } = \cfrac { 1 } { 4 } \left[ \begin{array} { c c } { 2 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 1 } \end{array} \right] } & { } \end{array}
$$

$P _ { S } \ , \ P _ { D }$ ，and $P _ { V }$ are the powers of surface scattering, double-bounce scattering，and volume scattering,respectively.These three coefficients should not be negative because they are the corresponding powers.However as discussed above，over-estimation of volume scattering often happens which leads to the negative $P _ { S }$ and $P _ { D }$ ：

# 3 Singh's two unitary transformations

The first unitary transformation is the rotation about the radar line of sight which is also known as OAC in [2,3,4]

$$
T ( \theta ) = R ( \theta ) T R ( \theta ) ^ { \dagger }
$$

where $\dagger$ denotes complex conjugation transposition, $T ( \theta )$ is the coherency matrix after OAC,and the rotation

$$
\begin{array} { r } { R ( \theta ) = \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { \cos ( 2 \theta ) } & { \sin ( 2 \theta ) } \\ { 0 } & { - \sin ( 2 \theta ) } & { \cos ( 2 \theta ) } \end{array} \right] . } \end{array}
$$

Via minimizing the $T _ { 3 3 } ( \boldsymbol { \theta } )$ element (the third row and third column element of $T ( \theta )$ ）the angle $\theta$ can be derived

$$
\operatorname* { m i n } ( T _ { 3 3 } ( \theta ) )
$$

$$
\theta = \frac { 1 } { 4 } \tan ^ { - 1 } \left( \frac { 2 \mathrm { R e } ( T _ { 2 3 } ) } { T _ { 2 2 } - T _ { 3 3 } } \right)
$$

After the rotation of (8), $E$ of $T ( \theta )$ becomes zero,and $F$ of $T ( \theta )$ remains unchanged.

The second unitary transformation carried out following thefirstunitarytransformationis

$$
T ( \varphi ) = U ( \varphi ) T ( \theta ) U ( \varphi ) ^ { \dagger }
$$

where $T ( \varphi )$ is the matrix obtained after this unitary trans

$$
U ( \varphi ) = \left[ \begin{array} { c c c } { { 1 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \cos ( 2 \varphi ) } } & { { j \sin ( 2 \varphi ) } } \\ { { 0 } } & { { j \sin ( 2 \varphi ) } } & { { \cos ( 2 \varphi ) } } \end{array} \right] .
$$

Similar to OAC above,the angle $\varphi$ can be derived via minimizing the $T _ { 3 3 } ( \varphi )$ element

$$
\operatorname* { m i n } ( T _ { 3 3 } ( \varphi ) )
$$

$$
\varphi = \frac { 1 } { 4 } \left( \frac { 2 \operatorname { I m } ( T _ { 2 3 } ( \theta ) ) } { T _ { 2 2 } ( \theta ) - T _ { 3 3 } ( \theta ) } \right)
$$

After the unitary transformation of (11), $F$ of $T ( \varphi )$ becomes zero,and $E$ of $T ( \varphi )$ remains unchanged. Because $E$ of $T ( \theta )$ equals to zero, the $E$ and $F$ of $T ( \varphi )$ are all zeros.So the degrees of freedom of coherency matrix reduce from nine to seven after these two unitary transformations. Although the physical meaning of the second unitary transformation is somewhat obscure，it indeed makes the $T _ { 3 3 }$ element smaller which is helpful for alleviating the over-estimation of volume scattering.

# 4 The Proposed Model-based Decomposition

# 4.1 The Proposed Two Unitary Transformations

As mentioned above,not only the orientation angle but also the helix angle of a target contribute to the crosspolarization.Similar to OAC，helix angle compensation for the target is proposed as

$$
{ \cal T } ( \tau ) = U ( \tau ) { \cal T } U ( \tau ) ^ { \dagger }
$$

where $\tau$ is the helix angle,and the unitary transformation matrix is $U ( \tau ) = \left[ \begin{array} { c c c } { \cos ( 2 \tau ) } & { 0 } & { j \sin ( 2 \tau ) } \\ { 0 } & { 1 } & { 0 } \\ { j \sin ( 2 \tau ) } & { 0 } & { \cos ( 2 \tau ) } \end{array} \right] .$

The $\tau$ can be derived by minimizing the $T _ { 3 3 } ( \tau )$ element

$$
\begin{array} { c } { { \displaystyle \operatorname* { m i n } ( T _ { 3 3 } ( \tau ) ) } } \\ { { \displaystyle \tau = \frac { 1 } { 4 } \tan ^ { - 1 } \left( \frac { 2 \mathrm { I m } ( T _ { 1 3 } ) } { T _ { 1 1 } - T _ { 3 3 } } \right) } } \end{array}
$$

After unitary transformation of (14), $G$ of $T ( \tau )$ becomes zero,and $H$ of $T ( \tau )$ remains unchanged.

The second unitary transformation is proposed as

$$
T ( \omega ) = U ( \omega ) T ( \tau ) U ( \omega ) ^ { \dag }
$$

where $\omega$ isthe unitary transformation angle, and

$$
U ( \omega ) = \left[ \begin{array} { c c c } { { \cos ( 2 \omega ) } } & { { 0 } } & { { \sin ( 2 \omega ) } } \\ { { 0 } } & { { 1 } } & { { 0 } } \\ { { - \sin ( 2 \omega ) } } & { { 0 } } & { { \cos ( 2 \omega ) } } \end{array} \right] .
$$

The angle $\omega$ is derived by minimizing the $T _ { 3 3 } ( \omega )$ element

$$
\operatorname* { m i n } ( T _ { 3 3 } ( \omega ) )
$$

$$
\omega = \frac { 1 } { 4 } \tan ^ { - 1 } \left( \frac { 2 \operatorname { R e } ( \mathrm { T } _ { 1 3 } ( \tau ) ) } { T _ { 1 1 } - T _ { 3 3 } } \right)
$$

After unitary transformation of (17), $H$ of $T ( \omega )$ becomes zero,and $G$ of $T ( \omega )$ remains unchanged,i.e. $H$ and $G$ of $T ( \omega )$ are all zeros,and it is to say that the real and imaginary parts of $T _ { 1 3 } ( \omega )$ are zeros.As far as we know,it is the first time that the helix unitary transformation is directly implemented on coherency matrix,as well as that two unitary transformations are utilized to make $G$ and $H$ (real and imaginary parts of $T _ { 1 3 }$ element zeros.The difference between Singh's unitary transformations and our unitary transformations is that Singh's first unitary transformation is OAC,but our first unitary transformation is helix compensation. In addition, $T _ { 2 3 } = 0$ （204号 is one of the results of Singh's transformations,however $T _ { 1 3 } = 0$ is the counterpart of our transformations.

# 4.2 The Proposed Decomposition

In the following we first conduct Singh's two unitary transformations((8) and(11)） and the proposed two unitary transformations ((14) and(17)) on the same coherency matrix separately,and then adaptively select the two unitary transformations which lead to the smaller $T _ { 3 3 }$ element,and then carry out the FDD on the coherency matrix obtained after the unitary transformations.The goal of adaptive selection of unitary transformations is to best fit the ground truth,because for some targets the orientation angle may be the main factor of the cross-polarization generation, however for some other targets the helix angle may be the main factor of the cross-polarization generation. The flowchart of the proposed decomposition is presented in figure 1.

![](images/8c1353ea39ecabb7de63d83078a6c9b2f6bd5959e681b2b126e97ac2f54ae600.jpg)  
Figure 1.Flowchart of the proposed decomposition.

# 5Experimental Results and Analysis

The RADARSAT-2 C-band data in San Francisco area [8] which was acquired on April 9,2Oo8 on a fine-beam, quad-polarization mode,is used to validate the improvement of the proposed method. The data has been 6-look processed in range and azimuth directions,and has a dimension of $4 7 0 \times 2 4 0 2$ pixels. The $\tau$ calculated by(16) is presented in figure 2.It should be pointed out that the scene of Figure 2 is only part of the San Francisco area data, and the corresponding Google Earth optical image is presented in figure 5.It can be seen in figure 2 that the value of $\tau$ is around zero in ocean areas.For comparison, the $\tau _ { 1 }$ (the helix angle of the dominant eigenvector) in [9] is shown in figure 3.We can see that $\tau$ and $\tau _ { 1 }$ are consistent in general, so the physical meaningful $\tau$ from (16) contains useful information.Then the proposed method is carried out. The resulted color-coded image of the proposed decomposition is shown in figure 4.In the image, the blue color areas mean that the surface scattering is dominant. Similarly,red color means the double-bounce scattering is dominant,and the green color means the volume scattering is dominant. The experimental results show that 67.6O percent of the pixels of the data select Singh's two unitary transformations,and the left pixels select our two unitary transformations. The average ratio of the volume scattering power to the total scattering poweronly with Singh's two unitary transformationsis $2 7 . 1 6 \%$ ，which is improved to $2 6 . 4 8 \%$ by using the proposed decomposition. So the average power of the vol

![](images/386d0515b74f8a3d586b42270c3265a4c94c63245a9176015988853ef0f53e15.jpg)

![](images/1eb4c392a4263ea342b7ec921a497490bce5626bf8f4ec35e769ea5b0d83c990.jpg)  
Figure 4. Color-coded image obtained by the proposed decomposition on RADARSAT-2 data.

![](images/7d7d7c700ad80d2956d8f846d27d3b9afbe0b1b8ad068f7a7ee497a276589827.jpg)  
Figure 5. Google Earth optical images of the selected area.

![](images/085d97d58bef9010247a94bbea8e49f1e76aeec1471e9acb6e9548bec3647664.jpg)  
Figure 2.Helix $\tau$ calculated by(16) for RADARSAT-2 data   
Figure 3.Helix $\tau _ { 1 }$ in [9] for RADARSAT-2 data

Table 1.Average volume scattering power contributions of(a) the proposed decomposition (b) the FDD only with Singh's transformations   

<html><body><table><tr><td></td><td>Patch 1</td><td>Patch 2</td><td>Patch 3</td><td>Patch 4</td></tr><tr><td>a</td><td>3.08%</td><td>18.54%</td><td>49.13%</td><td>49.06%</td></tr><tr><td>b</td><td>3.17%</td><td>19.11%</td><td>50.93%</td><td>50.89%</td></tr></table></body></html>

mations and the proposed decomposition are similar with each other,because the orientation angle and the helix angle of the ocean surface are both small,which introduceslittle cross-polarization as a result. For patch 2,,there is a small improvement by the proposed method with $1 8 . 5 4 \%$ volume scattering compared to $1 9 . 1 1 \%$ volume scatteringby only with Singh's two trans1formations.The volume scattering power contribution by the proposed decomposition is $4 9 . 1 3 \%$ compared to $5 0 . 9 3 \%$ for patch 3, and the volume scattering power contribution by the proposed decomposition is $4 9 . 0 6 \%$ compared to $5 0 . 8 9 \%$ for patch 4,respectively.For patch 3 and 4, the proposed two unitary transformations are more suitable for compensating the coherency matrix,because the orientation angle is very small for that there are no oriented buildings and azimuth modulated surfaces in these areas,and the helix angle of all the scatters in a resolution mainly contributes to the cross-polarization of the coherency matrix. The proposed decomposition is more reasonable,because it takes into account of different types of targets that for some targets the orientation angle is the main factor of cross-polarization generation，but for some other targets the helix angle may be the main factor of crosspolarization generation.

ume scattering of the proposed decomposition is lower. It is to say the proposed model-based decomposition method with adaptive selection of unitary transformations is more effective in alleviating the over-estimation of volume scattering than that only uses Singh's two unitary transformations.

To more specifically demonstrate the improvement of the proposed decomposition,we select four patches from the data for further validation. The Google Earth optical image of the four patches is shown in figure 5.Patch1 is the ocean area,patch 2 is the oriented built-up area,and patch 3 and 4 are the park areas,respectively.The decomposition results are presented in table 1. For patch 1, the results of the FDD only with Singh's unitary transfor

# 6 Conclusion

A three component model-based decomposition with adaptive selection of unitary transformations is proposed in this paper. Two new unitary transformations on the coherency matrix are also proposed which include helix compensation. The $T _ { 1 3 }$ element becomes zero after applying these two unitary transformations.Experimental results demonstrate the improvement of the proposed decomposition method.

# Acknowledgments

This work is supported by the National Natural Science Foundation of China under Grant 414O1406.

# References

[1] Freeman,A.andDurden,S.L.“A three-component scattering model forpolarimetric SAR data,”IEEE Trans. Geosci. Remote Sens., 1998,5,vol. 36, no.3, pp. 964-973.   
[2] Lee, J.S. Schuler, D.L. Ainsworth, T.L. Krogager, E. Kasilingam,D.and Boerner,W.-M. “On the estimation of polarization orientation shifts induced by terrain slopes,’ IEEE Trans. Geosci. Remote Sens., 2002,1, vol. 40, no.1, pp.30-41.   
[3] An，W.Cui，Y.and Yang,J.“Three-component model-based decomposition for polarimetric SAR data,”IEEE Trans. Geosci. Remote Sens., 2010,1, vol. 48, no. 6, pp.2732-2739.   
[4] Yamaguchi，Y.Sato，A. Boerner，W.-M.Sato，R. and Yamada, H.“Four component scattering power decomposition with rotation of coherency matrix,” IEEE Trans. Geosci. Remote Sens.,2011,1, vol.49, no. 6, pp.2251-2258.   
[5] Yamaguchi,Y.Moriyama,T.Ishido,M.and Yamada,H.“Four component scattering model for polarimetric SAR image decomposition,” IEEE Trans. Geosci. Remote Sens.， 2005,8, vol. 43, no. 8, pp. 1699-1706.   
[6] Singh,G.Yamaguchi,Y.and Park,S.-E.“General four-component scattering power decomposition with unitary transformation of coherency matrix,” IEEE Trans.Geosci. Remote Sens.,2013,5,vol.51, no.5,pp.3014-3022.   
[7] Huynen，J.R.“Phenomenological theory of radar targets," Ph.D.Dissertation，Delf Universityof Technology,1970.   
[8] http://gs.mdacorporation.com/SatelliteData/Radarsat 2/SampleDataset.aspx, accessed December 2014   
[9] Touzi, R.“Target scattering decomposition in terms of roll-invariant target parameters,” IEEE Trans. Geosci. Remote Sens.，2007,1,vol. 45,no.1,pp. 73-84.