# A Novel Deorientation Method for PolSAR Data Processing

Feiya Zhu,KeyLaboratory of Microwave Remote Sensing,National Space Science Center, Chinese Academy of Sciences; University of Chinese Academy of Sciences.zhufeiya1990 $@$ gmail.com, China   
Yunhua Zhang,Key Laboratory of Microwave Remote Sensing,National Space Science Center, Chinese Academy of Sciences.zhangyunhua@mirslab.cn, China   
Dong Li, Key Laboratory of Microwave Remote Sensing,National Space Science Center, Chinese Academy of Sciences. lidong@mirslab.cn, China

# Abstract

In PolSAR data processing,deorientation operation is often necessary. The existing deorientation method uniformly deorients allthe sub-scatterers ofa resolution cell with one orientation angle.For high entropy situation, the sub-scatterers have diverse OAs,and the eectof the existing method is unsatisfactory.A novel deorientation method is proposed to welltreat the high entropy situation. Cloude's eigen-decomposition to the coherency matrix is first carred out.The three eigenvectors are then separately deoriented with their own orientation angles.Experiments demonstrate that the proposed method is suitable for extraction of urban regions, especially for extraction of oriented urban regions.

# 1 Introduction

Deorientation operation plays an important role in fully polarimetric synthetic aperture radar (PolSAR) data processing. For currently widely used deorientation method (the existing method) proposed in[1,2], the coherency matrix is rotated some angle about the radar line of sight (LOS). Only one “mixed” orientation angle (OA) is used.However, there are numerous scatterers in one resolution cell,and there is a real chance that they have different OAs.In oriented urban regions which are not aligned in the track direction, there may be roofs with azimuth slopes,oriented walls,and oriented dihedrals in one cell[3],for instance.Theyall have different OAs.Only one OA cannot effectively account for this situation. A novel deorientation method is thus proposed with OA variations (three OAs） taken into consideration,and the objective of which is to fit the scatterers with different OAs in one resolution cell.

# 2 Existing Deorientation Method

# 2.1 Existing Method

The existing deorientation method [1，2] which has gained wide applications can be represented as

$$
T _ { \mathrm { c } } = R ( \theta ) T R ^ { - 1 } ( \theta ) , R ( \theta ) = \left[ \begin{array} { c c c } { { 1 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \cos { 2 \theta } } } & { { \sin { 2 \theta } } } \\ { { 0 } } & { { - \sin { 2 \theta } } } & { { \cos { 2 \theta } } } \end{array} \right]
$$

where $T$ and $T _ { \mathrm { c } }$ denote the coherency matrix and the deoriented coherency matrix with the existing method respectively, and $R ( \theta )$ is the OA rotation matrix.The OA $\theta$ can be derived by the two methods proposed in [1, 2]. The OA is derived as the phase difference between the co-polarization terms based on circular polarization covariance matrix in [1],and is equivalently derived by minimizing the cross-polarization power in [2]. The derived OA is

$$
\theta = \frac { 1 } { 4 } \mathrm { a t a n } \Bigg [ { 2 \mathrm { R e } ( T _ { 2 3 } ) } \Bigg / _ { \left( T _ { 2 2 } - T _ { 3 3 } \right) } \Bigg ] .
$$

where $\operatorname { R e } ( { \cdot } )$ denotes the real part of a complex number.

# 2.2 Another Interpretation of the Existing Method

Here, the existing method is reconsidered and interpretedina different way.Via Cloude's eigen-decomposition [4], the coherency matrix is decomposed as

$$
{ \cal T } = \sum _ { i = 1 } ^ { 3 } \lambda _ { i } k _ { i } k _ { i } ^ { H } = \sum _ { i = 1 } ^ { 3 } T _ { i }
$$

where $\lambda _ { i } , k _ { i } ,$ and $T _ { i }$ are the eigenvalue,eigenvector,and single target, respectively, and $\lambda _ { 1 } \geq \lambda _ { 2 } \geq \lambda _ { 3 }$ is assumed. This provides a statistical interpretation of the target, i.e a three-symbol Bernoulli process is adopted [4]. Thus, the existing method of(1) can be rewritten as

$$
{ \cal T } _ { \mathrm { c } } = R ( \theta ) \left( \sum _ { i = 1 } ^ { 3 } T _ { i } \right) R ^ { - 1 } ( \theta ) = \sum _ { i = 1 } ^ { 3 } R ( \theta ) T _ { i } R ^ { - 1 } ( \theta )
$$

The three single targets, $T _ { 1 } , \ T _ { 2 }$ and $T _ { 3 }$ ，are deoriented about the radar LOS with one same OA. Actually as mentioned previously,the sub-scatterers in one cell may likely have different OAs,and that is to say that $T _ { 1 } , T _ { 2 }$ and $T _ { 3 }$ have their own OAs.Motivated by this point,a novel deorientation method is raised in this paper, i.e. $T _ { 1 } , T _ { 2 }$ ,and $T _ { 3 }$ are separately deoriented with their own OAs, respectively.

# 3Proposed Deorientation Method

# 3.1 Proposed Method

The proposed method reconstruct the sub-scatterers of a resolution cell, and the sub-scatterers are projected to three orthogonal single targets via Cloude-Pottier eigendecomposition of the coherency matrix.Then the three single targets are separately deoriented, i.e.

$$
T _ { \mathrm { p } } = \sum _ { i = 1 } ^ { 3 } R ( \theta _ { i } ) T _ { i } R ^ { - 1 } ( \theta _ { i } )
$$

where $T _ { \mathfrak { p } }$ is the deoriented coherency matrix with the proposed deorientation method, $T _ { i }$ is the single target obtained with (2), and $\theta _ { \mathrm { i } }$ is the OA of each single target （204号 $T _ { i \cdot }$ （20

One noteworthy feature of the proposed method is that the real part of $T _ { \mathrm { p l } 3 }$ element is zero,which is consistent with Huynen's deorientation theory that Huynen parameter $H$ (real part of $T _ { \mathrm { p 1 3 } }$ element) becomes zero after deorientation [5].But for the existing method,it is not the case, the real part of $T _ { { \mathrm { c } } 2 3 }$ element is zero.

The eigenvector $k _ { i }$ is here modelled by KennaughHuynen's co-diagonalization of scattering matrix [6, 7], and its OA $\theta _ { i }$ can be afterwards derived. The corresponding scattering matrix $S _ { i }$ of eigenvector $k _ { i }$ can thus be modelled as

$$
S _ { i } = R _ { \mathrm { S } } \left( \theta _ { i } \right) R _ { \mathrm { S } } \left( \tau _ { i } \right) S _ { \mathrm { d } i } R _ { \mathrm { S } } \left( \tau _ { i } \right) R _ { \mathrm { S } } \left( - \theta _ { i } \right)
$$

where $S _ { \mathrm { d } i }$ is the diagonal matrix whose diagonal ele ments are the complex con-eigenvalues of $x _ { i 1 }$ and $x _ { i 2 }$ respectively, and $\theta _ { i }$ and $\tau _ { i }$ are the OA and helix angle, respectively. The unitary transformation matrices are respectively

$$
R _ { \mathrm { S } } ( \theta _ { i } ) = \left[ \begin{array} { c c } { \cos \theta _ { i } } & { - \sin \theta _ { i } } \\ { \sin \theta _ { i } } & { \cos \theta _ { i } } \end{array} \right]
$$

and

$$
R _ { \mathrm { S } } ( \tau _ { i } ) = \left[ \begin{array} { c c } { \cos \tau _ { i } } & { - j \sin \tau _ { i } } \\ { - j \sin \tau _ { i } } & { \cos \tau _ { i } } \end{array} \right] .
$$

The eigenvector $k _ { i }$ can be obtained by expanding and rewriting the scattering matrix of(6) in Pauli basis as

$$
\begin{array} { r l } & { k _ { i } = [ \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \cos { 2 \tau _ { i } }  } \\ & { k _ { i } = [ \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \cos { 2 \theta _ { i } } + j \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \sin { 2 \tau _ { i } } \sin { 2 \theta _ { i } } ] } \\ & {  [ \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \sin { 2 \theta _ { i } } - j \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \sin { 2 \tau _ { i } } \cos { 2 \theta _ { i } } ]  } \\ & {  = [ k _ { i } ( 1 ) { k _ { i } } ( 2 ) { k _ { i } } ( 3 ) ] ^ { T } . } \end{array}
$$

The $\mathrm { O A } \theta _ { i }$ can be derived from (9) as

$$
\theta _ { i } = \frac { 1 } { 2 } \mathrm { a t a n } \left[ \frac { \mathrm { R e } \left[ { k _ { i } \left( 3 \right) \atop k _ { i } \left( 1 \right) } \right] } { \mathrm { R e } \left[ { k _ { i } \left( 2 \right) \atop k _ { i } \left( 1 \right) } \right] } \right] .
$$

The range of $\theta _ { i }$ is $[ - 4 5 ^ { \circ } , 4 5 ^ { \circ } ]$ .The above derived OA $\theta _ { i }$ of (10) is equivalent to that derived in [8].

# 3.2Physical Interpretation

The main idea of the proposed method is to rotate the three single targets about the LOS separately with different OAs instead of rotating them together with only one OA. We have numerous ways of decomposing one distributed target into three single targets,and Cloude's eigen-decomposition is chosen here.As an analytical tool, the Cloude's eigen-decomposition provides a concise and unique decomposition of the coherency matrix, and enables us to interpret the target in a higher dimension.Via eigen-decomposition, the coherency matrix is decomposed into three statistical single targets (three eigenvectors),and then the mean OAs of three single targets are all compensated.This results in that the proposed method is suitable for urban regions extraction, especially for characterisation of oriented urban regions. In oriented urban regions,there may be roofs with azimuth slopes,oriented walls,and orienteddihedrals and so on in one cell.These sub-scatterers are contained in the three single targets $T _ { i } ,$ and the proposed method just separately rotates the three single targets with their own OAs.

# 4Comparisons Between the Two Methods

# 4.1 Mathematical Comparison

From the mathematical point of view, the only difference between (4) and (5) is that the existing method uniformly rotates the three eigenvectors (the three targets) with a same OA $\theta$ about the LOS while the proposed method separately and adaptively rotates the three eigenvectors with their own OAs $\theta _ { 1 } , \theta _ { 2 }$ ,and $\theta _ { 3 }$ about the LOS.Then the proposed method can be viewed as a natural extension of the existing method. The three deoriented eigenvectors by the existing method is still orthogonal, but not the case by the proposed method. The two deoriented coherencymatrix, i.e. $T _ { \mathrm { c } }$ and $T _ { \mathrm { p } } ,$ are both positive semi-definite and physical meaningful.

# 4.2Experimental Results

Here, several experiments are carried out to demonstrate the different performances of the two methods. The RADARSAT-2 PolSAR data of San Francisco area are used [9]. The data are in single-look complex (SLC) format.For speckle reduction and geting the coherency matrix format data,a $7 \times 7$ refined Lee filter is implemented on the data. Only a part of the scene is utilized.

# 4.2.1 Comparisons Between the OAs

The OA $\theta$ of (2) used in the existing method and the OA $\theta _ { 1 }$ of（1O） of the dominant eigenvector used in the propposed method are demonstrated and compared,and are shown in Figure 1.

![](images/d9a8c8db07a03821e9979e1066b14f7592638d5d0269b2cf90fe91d030c9fb7f.jpg)  
Figure 1: a) OA of the existing method; (2) OA $\theta _ { 1 }$ of the proposed method

Four $1 0 0 \times 1 0 0$ typical patches are selected for further comparison.As shown in Figure 2 of Google Earth optical image, the selected patch 1-4 are ocean region,urban region,oriented urban region,and park region, respectively.

The statistical distributions of the OA $\theta$ used in the existing method and the OA $\theta _ { 1 }$ used in the propposed method for the four patches are shown in Figure 3.

![](images/b8894b52b7ab33fa1ab312751b3f667440888b86697aaa87f6bf329b6a935143.jpg)  
Figure3:Histgrams of the OAs of the four patches

OA of current method,ocean OA of proposed method,ocean   
500 500 1 一 40 -20 0 20 40 -40 2020 40 OAofcurrent method,urban OA of proposed method,urban   
500 1 1000 0 40 -20 0 20 40 -40 -20 0 20 40 OAofcurrent method,oriented urban OA of proposed method,oriented urban   
200 200   
100 100 0 0 -40 -20 0 20 40 -40 -20 0 20 40 OAof current method,park OA of proposed method,park   
400 300 200   
200 100 0 0 -40 -20 0 20 40 -40 -20 0 20 40

FromFigure 1 and Figure 3,we can see that $\theta$ and $\theta _ { 1 }$ are consistent in general, but the OA $\theta _ { 1 }$ of the dominant eigenvector is noisier as also mentioned in[1O]. Figure 1 shows that the OAs reasonably have large minus values in oriented urban region, such as patch 3.

# 4.2.2 Impacts of the Two Methods on the Model-based Decompsition

The two deorientation methods have different imapcts onthePolSAR model-basedpolarimetric decomposition,as will be shown in the folowing.As the deorientation methods are the emphasis, original Freeman-Durdenthree-componentdecomposition (FDD） without any modifications [12] is just selected here.The FDD is carried out based on the deoriented $T _ { \mathrm { c } }$ and Tp.

First, the negative power problem is tested. It is well known that the negative power phenomenon of FDD voliates the physical reality. Based on original FDD, $14 . 8 6 \%$ pixels have negative power. That numbers for FDD with the existing deorientation method and FDD with the proposed deorientation method are $8 . 7 4 \%$ and $7 . 7 7 \%$ ,respectively. Thus the proposed method is more effectiveinalleviatingthisphysicalvoliating phenomenon.

Second, the impacts of the two methods on the decomposedscatteringmechanismsandpower proportions of the three components are studied. The color-coded decomopistion results of FDD,FDD with the existing method,and FDD with the proposed method are shown in Figure 4, respectively.Blue color stands for surface scattering，red color stands for double-bounce scattering,and green color stands for volume scattering.

![](images/3e8b7a53244952c78c5827097aef684cf767f87bfaacc015a8fe133ff6d6e83a.jpg)  
Figure 2: Google Earth image of selected patches.   
Figure 4:Decomposition results of a)FDD,b) FDD with the existing method,and c) FDD with the proposed method.

The average power proportions of the four patches are demonstrated in Table 1-4.

<html><body><table><tr><td>Method</td><td>Ps</td><td>Pd</td><td>Pv</td></tr><tr><td>FDD</td><td>92.29%</td><td>2.58%</td><td>5.14%</td></tr></table></body></html>

Table 1:Average power proportions of patch 1 ocean region.   

<html><body><table><tr><td>FDDwiththecurretmethod FDD with the proposed method</td><td>92.46% 94.17%</td><td>2.72% 4.43%</td><td>4.82% 1.4%</td></tr></table></body></html>

Table 2:Average power proportions of patch 2 urban region.   

<html><body><table><tr><td>Method</td><td>Ps</td><td>Pd</td><td>Pv</td></tr><tr><td>FDD</td><td>29.32%</td><td>51.12%</td><td>19.56%</td></tr><tr><td>FDD with the curret method</td><td>31.16%</td><td>52.78%</td><td>16.06%</td></tr><tr><td>FDD with the proposed method</td><td>33.78%</td><td>54.95%</td><td>11.27%</td></tr></table></body></html>

Table 3:Average power proportions of patch 3 oriented urban region.   

<html><body><table><tr><td>Method</td><td>Ps</td><td>Pd</td><td>Pv</td></tr><tr><td>FDD</td><td>-7.78%</td><td>3.47%</td><td>104.3%</td></tr><tr><td>FDD with the curret method FDD with the proposed method</td><td>0 16.11%</td><td>27.79% 38.96%</td><td>72.21% 44.93%</td></tr></table></body></html>

<html><body><table><tr><td>Method</td><td>Ps</td><td>Pd</td><td>Pv</td></tr><tr><td>FDD</td><td>19.49%</td><td>8.07%</td><td>72.44%</td></tr><tr><td>FDD with the curret method FDD with the proposed method</td><td>21.05% 34.72%</td><td>16.39% 26.70%</td><td>62.56% 38.58%</td></tr></table></body></html>

Table 4: Average power proportions of patch 4 park region.

For Figure 4，the red colors in urban regions are strenghened by the proposed deorientation method, especially in oriented urban regions,such as patch 3.By the existing method, the patch 3 oriented urban region is not discriminated as double-bounce scattering dominant region, but as volume scattering dominant region. By the proposed method, this phenomenon is improved, and the green colors in patch 3 partially turn to red or yellow. The power proportions in Table 2-3 support the color change. Thus from the target classification point of view, the proposed method is more suitable for urban regions extraction, especially for oriented urban regions extraction.The green colors in park region，such as patch 4，are weakened by the proposed method, but the park region can still be correctly discriminated as volumescatteringdominantregion. Thepower proportions in Table 4 support the statement that the proposed method gets lower average volume scattering power than the curret method.

# 5Discussion

The proposed deorientation method is designed to better treat the high entropy regions.The high entropy regions usually include the oriented urban regions and forest regions.For oriented urban regions, the proposed method has more reasonable and superior performance than the existing method as previously demonstrated.For forest regions, the proposed method gets lower average volume scattering power than the existing method does. Although the forest regions can be correctly discriminated as volume scattering dominant regions by the proposed method, such as patch 4,one question may still be raised that does the proposed method underestimate the volume scattering power in forest regions? First, the volume scattering is modelled by the backscattering from a cloud of dipoles,and the OAs of the dipolesobey some probability distribution.The commonlyapplied uniform distribution and half cosine distribution are the centered at zero value,and this is consistent with the OA distributions of patch 4 in Figure 3.Second, the eigenvector of dipole scattering mechanism corresponds to the volume scattering part. Mean OA or the center OA of the OA distribution of the eigenvector is compensated for each eigenvector by the proposed method.As mentioned before, the OAs of forest regions usually center at zero generally, therefore,the deorientation effect on the eigenvector that corresponds to the volume scattering is very small. Thus the proposed method does not underestimate the volume scattering power for this general case.For the few targets whose mean OAs are not centered at zero, the mean OAs of the eigenvectors of dipole scattering mechanism will be rotated, and the volume scattering power from the canopy for this case may be underestimated,which may be the foreseen limitation of proposed method.However, it is difficult to expect that one method can fit all kinds of targets.

# 6 Conclusion

Updated from theexisting deorientation method proposed by Lee et al. and An et al.which utilizes one average OA to uniformly rotate the coherency matrix,a novel deorientation method whose objective is to fit the scatterers with different OAs in one resolution cell is proposed.Theproposeddeorientationmethod separately rotates the three single targets with their own OAsobtained by the eigen-decomposion of the coherency matrix. One feature of the proposed method isthat it is consistent with Huynen's deorientation theory,i.e. the real part of the $T _ { 1 3 }$ becomes zero after deorientation, but not the case for the existing method. Experimental results demonstrate that the proposed method issuitableforurban regionsextraction, expecially for oriented urban regions extraction.

# References

[1] J.S.Lee,D.L. Schuler, and T.L.Ainsworth,“Polarimetric SAR data compensation for terrain azimuth slope variation,”IEEE Trans.Geosci. Remote Sens., vol.38, no.5,pp.2153-2163, Sep.2000. [2] W. T. An,Y. Cui, and J. Yang,“Three-component model-based decomposition for polarimetric SAR data," IEEE Trans. Geosci. Remote Sens., vol. 48, no. 6, pp. 2732-2739,Jun. 2010.

[3]H.Kimura,‘Radar polarization orientation shifts in built-up areas,” IEEE Geosci. Remote Sens. Lett., vol. 5, no.2,pp.217-221,Apr.2008.   
[4] S.R. Cloude and E.Pottier, “A review of target decomposition theoremsin radar polarimetry,"IEEE Trans. Geosci.Remote Sens.,vol. 34,no.2, pp. 498- 518, Mar. 1996.   
[5]J.R.Huynen, ‘Phenomenological theory of radar targets,”Ph.D.Dissertation，Tech.Univ.Delft,Delft, The Netherland, 1970.   
[6] J.R. Huynen,“Measurement of the target scattering matrix,”Proc.IEEE,vol. 53,no.8,pp.936-946, Aug. 1965.   
[7]R.Touzi,“Target scattering decomposition in terms of roll-invariant target parameters,” IEEE Trans. Geosci. Remote Sens.,vol. 45,no.1, pp.73-84,Jan. 2007.   
[8] Lionel Bombrun et al, “Roll invariant target detection based on POLSAR clutter models,”Proceedings of the IEEE International Geoscience and Remote Sensing Symposium, Honolulu, Hawaii, USA, pages 2511-2514,2010.   
[9]http://gs.mdacorporation.com/SatelliteData/Radar sat2/SampleDataset.aspx   
[10] S.R. Cloude,“Decomposition theorems” in Polarisation Applications in Remote Sensing. Oxford, U.K: Oxford Univ. Press,2010, pp. 183-184.