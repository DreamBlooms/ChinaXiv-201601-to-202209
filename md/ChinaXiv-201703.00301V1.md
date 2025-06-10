# A novel deorientation method in PolSAR data processing

FEIYA ZHU\*†, YUNHUA ZHANG\*, DONG LI

Key Lab of Microwave and Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing,China

+University of Chinese Academy of Sciences, Beijing, China

Feiya Zhu is with the Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing 1Oo190, China, and also with the University of Chinese Academy of Sciences,Beijing 1Ooo49, China   
Address: No.1 Nanertiao, Zhongguancun, Haidian District, Beijing 1Oo19o, China. Tel / Fax: 086-010-62582874.   
E-mail: zhufeiyal $9 9 0 @$ gmail.com   
Yunhua Zhang and Dong Li are with the Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing 1O0190, China Address: No.1 Nanertiao, Zhongguancun, Haidian District, Beijing 1Oo19o, China. Tel /Fax: 086-010-62582874.   
E-mail: zhangyunhua $@$ mirslab.cn; lidong $@$ mirslab.cn Correspondence about this manuscript is directed to Feiya Zhu at the following address, email,as well as phone and fax number:   
Address: No.1 Nanertiao, Zhongguancun, Haidian District, Beijing 1Oo19o, China. Email: zhufeiya $1 9 9 0 @$ gmail.com.   
Tel / Fax: 086-010-62582874.

This work was supported by the National Natural Science Foundation of China under Grant 41401406

# A novel deorientation method in PolSAR data processing

Deorientation plays an important role in PolSAR target decomposition, terrain classification， and geophysical parameters retrieval. The existing deorientation method roughly rotates the target by one average/dominant orientation angle (OA) about the line of radar sight.But as for the complex high-entropy mixed scatterer which is usually comprised of several comparable sub-scatterers with different OAs，the average/dominant OA is obviously insufficient to account for the diverse OAs reality.To treat this,a novel PolSAR data deorientation method is proposed in this letter. The proposed method de-orients a mixed scatterer by reconstructingtheunderlyingsub-scatterersusingtheeigenvalue-based Cloude-Pottier decomposition first，and then compensates the OA of each reconstructed sub-scatterer using Huynen's desying operation, respectively. One important feature of the proposed method is that it is consistent with Huynen's desying operation that the real part of the(1,3） element of the de-oriented coherency matrix should be zero.The proposed method provides a fine deorientation for mixed targets,and is especially suitable for the extraction of oriented urban regions. Comparative experiments with the existing method on RADARSAT-2PolSAR data demonstrate theexcellentdeorientation performance of the proposed method.

Keywords: deorientation； orientation angle compensation; orientation angle variation; PolSAR; target decomposition;

# 1:Introduction

Deorientation plays an important role in polarimetric synthetic aperture radar (PolSAR) target decomposition， terrain classification，and geophysical parameters estimation. Without deorientation， the scattering mechanism may be misjudged for target decomposition and terrain classification， and inaccurate geophysical parameters estimation may be thus produced. The currently most used deorientation method (the existing method) rotates the coherency matrix with one orientation angle(OA) about the line of radar sight (LOS) (Lee et al. 2000; An et al. 2010). Lee et al. (2000) estimated the OA based on circular polarization covariance matrix,and An et al. (2O1O) derived the OA by minimizing the cross-polarization power. Recently, it was pointed out that even with the existing method applied,the largely oriented urban regions are still misclassified as volume scattering dominant regions (Chen et al. 2O13). The OA employed in the existing method is a mixed OA of all the sub-scatterers in this resolution cell. For some high entropy regions, such as for oriented urban regions which are not aligned along the track direction, the scattering mechanism is very complex, and there may be roofs with different azimuth slopes, oriented walls,and oriented dihedrals in one cell (Kimura, 2O08). These sub-scatterers have diverse OAs. One OA cannot account for this situation.We also take Cloude-Pottier decomposition (Cloude and

Potter, 1997） for example: for low entropy situation, the dominant eigenvector can effectively describe the target; For medium entropy situation， the dominant two eigenvectors must be employed to describe the target; For high entropy situation, all the three eigenvectors must be utilized to describe the target, and thus one dominant or average eigenvector cannot well account for this situation because the three eigenvectors are comparative. Analogously， one OA may effectively account for the low entropy situation, but cannot effectively account for the high entropy situation. In this letter,we propose a new deorientation method in consideration of OA variation in order to treat the high entropy case better.

# 2:Review of the existing deorientation method

# 2.1: The existing deorientation method

The scattering matrix contains the polarimetric scattering information about the target in coherent scattering case, which can be expressed as

$$
\begin{array} { r } { S = \left[ \begin{array} { l l } { S _ { H H } } & { S _ { H V } } \\ { S _ { V H } } & { S _ { V V } } \end{array} \right] } \end{array}
$$

where the subscript HV denotes vertical polarization transmission and horizontal polarization reception. When the scattering matrix is expressed in Pauli basis, the scattering vector is

$$
k = \frac { 1 } { \sqrt { 2 } } \Big [ S _ { H H } + S _ { V V } \quad S _ { H H } - S _ { V V } \quad 2 S _ { H V } \Big ] ^ { T }
$$

where the superscript $\mathrm { \Delta T }$ denotes matrix transposition. In incoherent scattering case, the coherency matrix can be obtained as

$$
T = \left. \boldsymbol { k } \cdot \boldsymbol { k } ^ { * T } \right. = \left[ \begin{array} { l l l } { T _ { 1 1 } } & { T _ { 1 2 } } & { T _ { 1 3 } } \\ { T _ { 1 2 } ^ { * } } & { T _ { 2 2 } } & { T _ { 2 3 } } \\ { T _ { 1 3 } ^ { * } } & { T _ { 2 3 } ^ { * } } & { T _ { 3 3 } } \end{array} \right]
$$

where $\langle . >$ denotes time averaging or spatial averaging，and \* denotes the complex conjugation. The coherency matrix is positive semi-definite，and thus is physical realizable.

The existing deorientation method performs by rotating the coherency matrix with OA about the LOS (Lee et al. 200O; An et al. 2010)

$$
{ \cal T } _ { \mathrm { c } } = R ( \theta ) { \cal T } R ^ { H } ( \theta ) , \mathrm { w i t h } R ( \theta ) = \left[ \begin{array} { c c c } { { 1 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \cos 2 \theta } } & { { \sin 2 \theta } } \\ { { 0 } } & { { - \sin 2 \theta } } & { { \cos 2 \theta } } \end{array} \right]
$$

where $T _ { \mathrm { c } }$ is the de-oriented coherency matrix by the existing method, and the superscript $\mathrm { ~ H ~ }$ denotes the complex conjugation transposition. Lee et al. (2OoO) estimated the OA based on the circular polarization covariance matrix,and An et al.(2O1O) derived the OA by minimizing the cross-polarization power. The OAs estimated by the above two methods are the same

$$
\theta = \frac { 1 } { 4 } \mathrm { a t a n } \Bigg [ \frac { 2 \mathrm { R e } \left( T _ { 2 3 } \right) } { T _ { 2 2 } - T _ { 3 3 } } \Bigg ] .
$$

One noteworthy feature of the existing method is that the real part of the $T _ { \mathrm { c } } ( 2 , 3 )$ element is zero.

# 2.2: Another interpretation of the existing method

In this subsection, the existing method is reconsidered and interpreted in a different way. With Cloude-Pottier's eigen-decomposition, the coherency matrix is decomposed into three orthogonal single targets (Cloude and Pottier, 1996)

$$
{ \cal T } = \sum _ { i = 1 } ^ { 3 } \lambda _ { i } k _ { i } k _ { i } ^ { H } = \sum _ { i = 1 } ^ { 3 } { \cal T } _ { i }
$$

where $\lambda _ { i } , \ k _ { i }$ ，and $T _ { i }$ $( i { = } 1 , 2 , 3 )$ are the eigenvalues，eigenvectors,and single targets, respectively. We have ${ \cal T } _ { i } { = } { \lambda } _ { i } k _ { i } k _ { i } ^ { H }$ with $\lambda _ { 1 } \ge \lambda _ { 2 } \ge \lambda _ { 3 }$ assumed. The eigen-decomposition enables a statistical interpretation of the mixed/distributed target $T$ in terms of three orthogonal single targets $T _ { 1 } , T _ { 2 } .$ ，and $T _ { 3 }$ . All the sub-scatterers in one resolution cell are projected to these three single targets，and the three single targets represent all the sub-scatterers in the cell. Thus the existing method of (4) can be rewritten as

$$
T _ { \mathrm { c } } = R ( \theta ) \left( \sum _ { i = 1 } ^ { 3 } T _ { i } \right) R ^ { H } ( \theta ) = \sum _ { i = 1 } ^ { 3 } R ( \theta ) T _ { i } R ^ { H } ( \theta )
$$

The three single targets which represent all the sub-scatterers are de-oriented with the same OA of $\theta$ ,and then are combined to constitute the de-oriented mixed target which is represented by $T _ { \mathrm { c } }$ ,i.e.all the sub-scatterers in this cell are rotated by the same OA.As mentioned previously, for low entropy situation, one dominant scatterer is effective to describe the mixed target,and one OA may effectively account for this situation. But for high entropy situation, the scattering powers of the $T _ { 1 } , T _ { 2 } ,$ and $T _ { 3 }$ are comparative, and they have different OAs. Thus one OA cannot effectively account for the high entropy situation.Motivated by this point, a novel deorientation method is developed，which separately de-orients $T _ { 1 } , T _ { 2 } .$ and $T _ { 3 }$ by their own OAs instead of uniformly de-orienting $T _ { 1 }$ $T _ { 2 }$ ,and $T _ { 3 }$ by a common OA.

# 3:The proposed deorientation method

# 3.1: The proposed method

The coherency matrix is first decomposed into three single targets via Cloude-Pottier's eigen-decomposition as (6), and then the proposed method can be expressed by slightly modifying（7) as

$$
T _ { \mathfrak { p } } = \sum _ { i = 1 } ^ { 3 } R ( \theta _ { i } ) T _ { i } R ^ { H } ( \theta _ { i } )
$$

where $T _ { \mathfrak { p } }$ is the de-oriented coherency matrix by the proposed deorientation method, and $\theta _ { \mathrm { i } }$ is the OA of each single target ${ \cal T } _ { \mathrm { i } } \mathrm { o r } k _ { \mathrm { i } }$ . The main idea behind the proposed method is that we reconstruct the underlying sub-scatterers using eigen-decomposition to get the three eigenvectors,and then de-orient each eigenvector separately with their own OAs instead of a common OA.

Now we detail the procedure of the derivation of the OA $\theta _ { \mathrm { i } }$ , which is based on Huynen's desying operation. First， the eigenvector $k _ { i }$ ismodelled by Kennaugh-Huynen's co-diagonalization of scattering matrix (Huynen, 1965; Touzi, 2OO7). The corresponding scattering matrix $S _ { i }$ of eigenvector $k _ { i }$ can be parameterizedas

$$
S _ { i } = R _ { \mathrm { S } } \left( \theta _ { i } \right) R _ { \mathrm { S } } \left( \tau _ { i } \right) S _ { \mathrm { d } i } R _ { \mathrm { S } } \left( \tau _ { i } \right) R _ { \mathrm { S } } \left( - \theta _ { i } \right)
$$

where $S _ { \mathrm { d } i }$ is the diagonal matrix whose diagonal elements are the complex con-eigenvalues of $x _ { i 1 }$ and $x _ { i 2 }$ ,respectively, and $\theta _ { i }$ and $\tau _ { i }$ are the OA and helix angle of $S _ { i } ,$ respectively. The two unitary transformation matrices are

$$
R _ { \mathrm { S } } ( \theta _ { i } ) = \left[ \begin{array} { c c } { \cos \theta _ { i } } & { - \sin \theta _ { i } } \\ { \sin \theta _ { i } } & { \cos \theta _ { i } } \end{array} \right] \mathrm { , ~ a n d ~ } ~ R _ { \mathrm { S } } ( \tau _ { i } ) = \left[ \begin{array} { c c } { \cos \tau _ { i } } & { - j \sin \tau _ { i } } \\ { - j \sin \tau _ { i } } & { \cos \tau _ { i } } \end{array} \right] \mathrm { . }
$$

The model of eigenvector $k _ { i }$ can be obtained by expanding and rewriting (9) in Pauli basis

$$
k _ { i } = \left[ \begin{array} { c } { \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \cos { 2 \tau _ { i } } } \\ { \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \cos { 2 \theta _ { i } } + j \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \sin { 2 \tau _ { i } } \sin { 2 \theta _ { i } } } \\ { \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \sin { 2 \theta _ { i } } - j \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \sin { 2 \tau _ { i } } \cos { 2 \theta _ { i } } } \end{array} \right] .
$$

The OA $\theta _ { i }$ of $k _ { i }$ or $T _ { i }$ can be calculated by (12)

$$
\theta _ { i } = \frac { 1 } { 2 } \mathrm { a t a n } \left[ \frac { \mathrm { R e } \left[ k _ { i } \left( 3 \right) _ { k _ { i } \left( 1 \right) } \right] } { \mathrm { R e } \left[ k _ { i } \left( 2 \right) _ { k _ { i } \left( 1 \right) } \right] } \right] .
$$

Theobtained $\theta _ { i }$ is the same as the result of Bombrun et al. (2010).

Once OA $\theta _ { i }$ is derived, the de-oriented coherency matrix $T _ { \mathfrak { p } }$ can be obtained by (8). The $( 1 , 3 )$ element of $T _ { \mathfrak { p } }$ is calculated by

$$
T _ { \mathrm { p } } ( 1 , 3 ) = \sum _ { i = 1 } ^ { 3 } - j \frac { \left| x _ { i 1 } + x _ { i 2 } \right| ^ { 2 } } { 8 } \sin { 4 \tau _ { i } } .
$$

It can be seen from（13） that $T _ { \mathrm { p } } ( 1 , 3 )$ is purely imaginary,which is consistent with Huynen's desying operation that the real part of(1,3） element of the de-oriented coherency matrix should be zero (Huynen, 197O). But as for the existing Lee's or An's method,it is not the case,in which the real part of the (2,3) element of the de-oriented coherency matrix $T _ { \mathrm { c } }$ is zero instead.

# 3.2: Physical interpretation

Our aim is to better treat the deorientation of the mixed target in high entropy case.

Different from the existing deorientation method,after we reconstruct the sub-scatterers using eigen-decomposition, the obtained three single targets are rotated about the LOS separately by their own OAs instead of being rotated uniformly by only one OA. This results in that the proposed method is suitable for characterization of high entropy regions, especially for the oriented urban regions. Because the scattering mechanism of these regions is complex,and the main sub-scatterers in one cell likely have diverse OAs. Let us take oriented urban regions for example, there may be roofs with azimuth slopes, oriented walls,and oriented dihedrals and so on in one cell. These underlying sub-scatterers contained in one cell form a mixed distributed target, which are projected to three single targets $T _ { i }$ $( i { = } 1 , 2 , 3 )$ . Then the proposed method just rotates the three single targets by their own OAs,respectively, and thus fine deorientation is achieved. By separate and fine deorientation instead of uniform deorientation, one can expect to obtain better results than that by the existing method.

# 4:Comparisons between the existing method and the proposed method

# 4.1: Mathematical comparison

From the mathematical point of view, the only difference between (7) and (8) is that the existing method uniformly rotates the three eigenvectors (the three targets) by a common OA $\theta$ about the LOS while the proposed method separately rotates the three eigenvectors by their own OAs $\theta _ { 1 } , \theta _ { 2 }$ ,and $\theta _ { 3 }$ about the LOS. The proposed method can be viewed as a natural extension of the existing method. The three de-oriented eigenvectors by the existing method are still orthogonal， but it is not the case by the proposed method. However, the two de-oriented coherency matrices,i.e. $T _ { \mathrm { c } }$ and $T _ { \mathfrak { p } }$ ，are both positive semi-definite and physical meaningful.

# 4.2: Comparison of experimental results

Several experiments are conducted to demonstrate the different performances of the two methods,the effectiveness of the proposed method,and superiority of the proposed method in characterization of oriented urban regions.

# 4.2.1: The PolSAR data

The C-band RADARSAT-2 PolSAR data of San Francisco Bay area are used for validation. The data are in single-look complex (SLC） format,and a $7 { \times } 7$ refined Lee filter is implemented on each pixel position to suppress the speckle and to estimate the coherency matrix. We only use a part of the scene. Figure 1 shows the Google Earth optical image of this area. The azimuth direction of the PolSAR data is in the up-down direction. Four 100 $\times 1 0 0$ typical patches are selected for subsequent processing,i.e. patch 1 of ocean region, patch 2 of urban region, patch 3 of oriented urban region,and patch 4 of park region.

# 4.2.1: OA comparison

Two OAs, i.e. the OA $\theta$ of (5) of the existing method and the OA $\theta _ { 1 }$ of(12) of the dominant eigenvector of the proposed method,are compared. Figure 2 demonstrates the results. For further comparison, the statistical distributions of the two OAs in the four selected patches are shown in Figure 3.From Figures 2 and 3,we can observe that the OA of the existing method and the dominant OA of the proposed method are consistent generally. The dominant OA of the proposed method looks more noisy than that of the existing method does,and this is because the OA of the existing method is an average or mixed version. For patch 1, 2,and 4,the OAs distribute symmetrically around the zero value generally. For patch 3 of the oriented urban region，the OAs reasonably demonstrate large minus values generally.

# 4.2.2: Impacts of the two deorientation methods on the model-based decomposition

The different impacts of the two methods on the PolSAR model-based polarimetric decomposition will be evaluated. As we only focus on the deorientation methods, thus the original Freeman-Durden three-component decomposition (FDD） without any modifications is just selected here (Freeman and Durden, 1998). The FDD is carried out based on the de-oriented $T _ { \mathrm { c } }$ and $T _ { \mathfrak { p } }$ . The total backscattering of a target is decomposed into three scattering components by FDD，i.e. surface scattering，double-bounce scattering, and volume scatering.

First, the negative power problem is investigated. It is well known that the power of surface scattering component or double-bounce scattering component may be negative for FDD which violates the physical reality. Based on the original FDD, $1 4 . 8 6 \%$ pixels have negative surface or double-bounce scattering power. The numbers for FDD with the existing deorientation method and FDD with the proposed deorientation method are $8 . 7 4 \%$ and $7 . 7 7 \%$ ,respectively. Compared with the existing method, a further reduction is achieved by the proposed method. Thus the proposed method is more effective than the existing method in alleviating this physical violation phenomenon.

Second, the impacts of the two methods on the decomposed scattering mechanisms and power proportions of the three components are compared. The color-coded decomposition results of FDD,FDD with the existing method,and FDD with the proposed method are shown in Figure 4,respectively. The blue,red,and green colors denote the surface scattering， double-bounce scattering，and volume scattering, respectively. The average power proportions of the three scattering mechanisms for the four patches are shown in Table 1. As shown in Figure 4, the two deorientation methods have similar performance in low-entropy ocean region, such as patch 1,and the power proportions of patch 1 in Table 1 also support this finding. Thus the utility of one OA by the existing method is effective to account for the low entropy situation.The red colors in urban regions are strengthened by the proposed deorientation method, especially in oriented urban regions, such as patch 3.By the existing method, the patch 3 oriented urban region is not discriminated as double-bounce scattering dominant, but as volume scattering dominant. However, by using the proposed method, the green colors in patch 3 partially turn to red or yellow as we expect. Some improvements are achieved. The power proportions of patch 3 in Table 1 are in accordance with the color change. Thus from the target classification point of view, the proposed method is more suitable for extraction of urban regions,especially for oriented urban regions. The green colors in park region, such as patch 4, are lightened by the proposed method, but the park region can still be generally discriminated as volume scattering dominant region. The power proportions in Table 1 support the statement that the proposed method gets lower average volume scattering power than the existing method, but the volume scattering power still dominants.

The effectiveness and improvement of the proposed method with other speckle reduction window sizes and on the L-band E-SAR PolSAR data of Oberpfaffenhofen area are also verified with similar results obtained, which are not presented here due to the space.

# 4:Discussions

In this section, we would like to discuss some issues as follows.

First, the oriented surface sub-scatterers and the oriented double-bounce sub-scatterers in one resolution cell will produce additional cross-polarization backscattering,and they usually have diverse OAs for high-entropy case. Ideally，we want to individually de-orient each oriented surface sub-scatterer and each oriented double-bounce sub-scatterer in one cell. According to the state-of-the-art PolSAR target decomposition, we cannot conduct such decomposition and deorientation. Thus we reconstruct the sub-scatterers using Cloude-Potier's eigen-decomposition, and the three single targets are obtained which represent all the sub-scatterers,and we de-orient them separately by their own OAs so as to realize a fine deorientation of the sub-scatterers.In fact, we have numerous ways to decompose one distributed target into three single targets, and the Cloude'seigen-decomposition ischosen here because it providesa concise decomposition of the coherency matrix by reconstructing the underlying single targets well based on the scattering orthogonality.

Second, the proposed deorientation method is designed to better treat the high entropy regions like the oriented urban regions and forest regions. For oriented urban regions, the proposed method has more reasonable and superior performance than the existing method as previously demonstrated. For forest regions, the proposed method gets lower average volume scattering power than the existing method does.Although the forest regions can be correctly discriminated as volume scattering dominant regions by the proposed method， such as patch 3,one question may still be raised that does the proposed method underestimate the volume scattering power in forest regions? First, the volume scattering is modelled by the backscattering from a cloud of dipoles,and the OAs of the dipoles obey some probability distribution.The commonly applied probability distributions are the uniform distribution centered at zero value and half cosine distribution centered at zero value (Freeman and Durden, 1998; Yamaguchi et al. 2005).The same point is that both the probability distributions are centered at zero value,and this is consistent with the OA distributions of patch 4 in Figure 3. Second, the eigenvector of dipole scattering mechanism corresponds to the volume scattering part. Mean OA or the center OA of the OA distribution of the eigenvector is compensated for each eigenvector by the proposed method. As mentioned before, the OAs of forest regions usually center at zero generally, therefore, the deorientation effect on the eigenvector that corresponds to the volume scattering is very small. Thus the proposed method does not underestimate the volume scattering power for this general case. For the few targets whose mean OAs are not centered at zero, the mean OAs of the eigenvectors of dipole scattering mechanism will be rotated, and the volume scattering power from the canopy for this case may be underestimated, which may be the foreseen limitation of proposed method. However, it is difficult to expect that one method can fit all kinds of targets.

Third,although three eigenvectors are utilized, the scattering mechanisms of the three eigenvectors need not to be interpreted. The three eigenvectors are just obtained and de-oriented.

Last, all the deorientation methods aim to get results agreed with the ground truth, but now it is still dificult to theoretically evaluate which result is more close to the ground truth. Both $T _ { \mathrm { c } }$ and $T _ { \mathfrak { p } }$ are approximations to the ideal de-oriented coherency matrix. The experimental results just demonstrate the different performances of the two methods and the effectiveness and improvement of the propose method.

# 4: Conclusion

As an alternate to the existing deorientation method which utilizes one mixed OA to uniformly rotate the coherency matrix,a novel deorientation method is proposed, whose objective is to fit the sub-scatterers with different OAs in one resolution cell. The proposed deorientation method separately rotates the three single targets which represent all the sub-scatterers. One important feature of the proposed method is that it is consistent with Huynen's desying operation, i.e. the real part of the (1, 3) element of the coherency matrix becomeszero afterdeorientation. Experimental results demonstrate the advantage of the proposed method,i.e.it is suitable for extraction of urban regions, especially for oriented urban regions.

# References

LEE, J.-S., ScHULER, D.L., and AINsWORTH, T.L., 2OOO, Polarimetric SAR data compensation for terrain azimuth slope variation. IEEE Transactions on Geoscience and Remote Sensing, 38, pp. 2153-2163.   
AN,W.-T, Cu1. Y，and YANG, J.， 2010,Three-component model-based decomposition for polarimetric SAR data. IEEE Transactions on Geoscience and Remote Sensing， 48, pp. 2732-2739.   
CHEN, S.-W., OHKI, M., SHIMADA,M.,and SATo, M.,2O13, Deorientation effect investigation for model-based decomposition over oriented built-up areas. IEEE Geoscience and Remote Sensing Letters,10, pp. 273-277.   
KIMURA, H., 2OO8,Radar polarization orientation shifts in built-up areas. IEEE Geoscience and Remote Sensing Letters,5, pp.217-221.   
CLOUDE，S.R.and PoTTIER，E.，1997，An entropy based classification scheme for land applications of polarimetric SAR. IEEE Transactions on Geoscience and Remote Sensing, 35, pp. 68-78.   
CLOUDE，S.R.and PoTTIER，E.，1996,review of target decomposition theorems in radar polarimetry. IEEE Transactions on Geoscience and Remote Sensing, 34, pp. 498-518.   
HUYNEN, J.R., 1965, Measurement of the target scatering matrix. Proceedings of IEEE, 53, pp. 936-946.   
ToUZI,R.， 2Oo7, Target scattering decomposition in terms of roll-invariant target parameters. IEEE Transactions on Geoscience and Remote Sensing, 45, pp. 73-84.   
BOMBRUN，L.，2O10，Roll invariant target detection based on POLSAR cluter models. Proceedings of the IEEE International Geoscience and Remote Sensing Symposium， pp 2511-2514.   
HUYNEN, J.R.,1970,Phenomenological theory of radar targets. PhD diss., University of Delft. FREEMAN, A. and DURDEN, S.L.,1998, A three-component scattering model for polarimetric SAR data. IEEE Transactions on Geoscience and Remote Sensing,36, pp. 963-973.   
YAMAGUCHI, Y.,MORIYAMA,T., IsHIDO,M. and YAMADA,H.,2OO5,Four-Component scattering model for polarimetric SAR image decomposition. IEEE Transactions on Geoscience and Remote Sensing, 43, pp. 1699-1706. Figure 1. Google Earth optical image of the data.   
Figure 2(a). OA of the existing method.   
Figure 2(b). OA of the dominant eigenvector of the proposed method.   
Figure 3.Two OAs’ distributions in the four selected patches.   
Figure 4(a).Decomposition results of FDD.   
Figure 4(b). Decomposition results of FDD with the existing method.   
Figure 4(c). Decomposition results of FDD with the proposed method.

Table 1. Average power proportions of the three scatering mechanisms for patch 1-4 with FDD, FDD with the existing method,and FDD with the proposed method. $P _ { \mathrm { S } } , P _ { \mathrm { D } }$ ,and $P _ { \mathrm { V } }$ stands for power proportions of surface, double-bounce, and volume scatering components, respectively.   

<html><body><table><tr><td colspan="4">Patch 1</td><td colspan="3">Patch 2</td></tr><tr><td>Method</td><td>Ps</td><td>PD</td><td>Pv</td><td>Ps</td><td>PD</td><td>Pv</td></tr><tr><td>FDD</td><td>92.29%</td><td>2.58%</td><td>5.14%</td><td>29.32%</td><td>51.12%</td><td>19.56%</td></tr><tr><td>FDD with existing method</td><td>92.46%</td><td>2.72%</td><td>4.82%</td><td>31.16%</td><td>52.78%</td><td>16.06%</td></tr><tr><td>FDD with proposed method</td><td>94.17%</td><td>4.43%</td><td>1.4%</td><td>33.78%</td><td>54.95%</td><td>11.27%</td></tr><tr><td></td><td></td><td>Patch 3</td><td></td><td></td><td>Patch 4</td><td></td></tr><tr><td>Method</td><td>Ps</td><td>PD</td><td>Pv</td><td>Ps</td><td>PD</td><td>Pv</td></tr><tr><td>FDD</td><td>-7.78%</td><td>3.47%</td><td>104.3%</td><td>19.49%</td><td>8.07%</td><td>72.44%</td></tr><tr><td>FDD with existing method</td><td>0</td><td>27.79%</td><td>72.21%</td><td>21.05%</td><td>16.39%</td><td>62.56%</td></tr><tr><td>FDD with proposed method</td><td>16.11%</td><td>38.96%</td><td>44.93%</td><td>34.72%</td><td>26.70%</td><td>38.58%</td></tr></table></body></html>