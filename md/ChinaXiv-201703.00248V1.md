# An Extension of the Complete Model-Based Decomposition of Polarimetric SAR data

Abstract—The model-based decomposition originated from Freeman-Durden three-component decomposition (FDD） has been widely applied in polarimetric synthetic aperture radar (POLSAR) data processing for its clear physical interpretation and easy implementation.Numerous improvements have been proposed to settle the two main drawbacks ofFDD,i.e.incomplete utilization of the polarimetric information in the coherency matrix and the negative scattering power problem.Recently,Cui etal. proposed a complete model-based three-component decomposition of POLSAR coherency matrix data which has successfully settled the two aforementioned drawbacks.However, the three scattering components’powers are not totally derived using scattering models,and the remained coherency matrix (RCM) obtained by subtracting the volume scattering component from the coherency matrix is not consistent with the models of surface scattering and double-bounce scattering components.As anextension of Cui's method, this letter is dedicated to develop a novel method to discriminate the surface scattering and double-scattering components from the RCM both using scattering models.With the orientation angle(OA） variation and helix angle variation compensated for the RCM,the RCM is automatically consistent with the models of surface scattering and double-scattering components.The OA variation and helix angle variation compensation for the RCM is done by unitary transformations of the eigenvectors of the RCM.Then the compensated RCM is used to derive the powers of surface scattering and double-scattering components using scattering models.The powers of surface scattering and double-bounce scattering components are positive.The effectiveness of the proposed method is demonstrated by processing POLSAR data.

Index Terms—Freeman-Durden three-component decomposition，helix angle variation，nonnegative eigenvalue decomposition,orientation angle variation,polarimetric synthetic apertureradar.

# I．INTRODUCTION

Polarimetric target decomposition plays an important role in target identification，target classification，and geophysical parameters retrieval.Huynen pioneered the work of target decomposition.He decomposed the distributed target into a single target and the target “noise”[1]. The instability, non-uniqueness,as well as the preference for symmetry and regularity,made that the Huynen decomposition has not been widelyused[2]. Nowadaysthehotspotsoftarget decomposition research mainly concentrate on two categories, i.e. the Cloude-Pottier eigenvalue/eigenvector decomposition andthemodel-baseddecompositionoriginatedfrom Freeman-Durden three-component decomposition (FDD).For the Cloude-Pottier eigenvalue/eigenvector decomposition, the polarimetric coherency matrix is decomposed into three orthogonal eigenvectors which represent three orthogonal single targets，respectively[3]，while forthe FDD，the covariance matrix is decomposed into three scattering components,i.e.surface scattering component, double-bounce scattering component,and volume scattering component [4]. We only focus on model-based decompositions in this letter.

Because reflection symmetry (RS） is assumed, FDD only accounts for five of nine independent parameters of the coherency matrix, i.e. the $T ( 1 , 3 )$ and $T ( 2 , 3 )$ of the coherency matrix $T$ are not used,and thus polarimetric information loss isunavoidable.Duetoblindlyassigningallthe cross-polarization to the volume scattering component, the negativepower of surface scattering or double-bounce scattering component may occur in FDD.In fact,numerous improvements [5-16] have been achieved to solve these two problems.Yamaguchi et al.[5] added a helix component to account for the off-diagonal elements of the coherency matrix, and six independent parameters are accounted for.The negative power problem is also alleviated in some degree as the helix component also accounts for some cross-polarization power. An et al. [6] and Lee et al. [7] introduced deorientation operation to the coherency matrix to mitigate the negative power problem,and reduced the independent parameters from nine to eight.The Yamaguchi's four-component decomposition with deorientation operation can account for six out of eight parameters[8]. Based on RS assumption， nonnegative eigenvalue decomposition (NNED) was proposed by van Zyl et al.[10，11] to avoid the negative power problem，but the polarimetric information is still not fully utilized.

Recently,Cui et al.[12] proposed a complete model-based three-component decomposition. The volumescattering component is determined by the NNED withoutRS assumption and thus full utilization of polarimetric informationis guaranteed.In [12]， two algorithms are introduced for discriminating the second and third components,i.e.surface scattering and double-bounce scattering components.In the first algorithm, the powers of these two components are derived as the eigenvalues of the remained coherency matrix (RCM) afterinterpreting the scattering mechanisms of the de-oriented eigenvectors of the RCM.However, the powers are not derived using scattering models as mentioned by Lee et al.[14].In the second algorithm, the RCMis first de-oriented,and from which amaximum single scatterer, surface scatterer or double-bounce scatterer，is derived using scattering model as the second scattering component. But, the third component is not derived using scattering model，and the derivation procedure is complex and ambiguous in physical meaning as mentioned by An et al. [15]. An et al. [15,16] considered that the (3,3) element of the coherency matrix of the third scattering component should be zero,because for a pure surface scatterer ordouble-bounce scatterer the(3,3)elementis zerowhichcan beverified by the models of surface scatteringand double-bounce scattering components:

$$
T _ { \mathrm { S } } = \frac { 1 } { 1 + \big | \beta \big | ^ { 2 } } \left[ \beta ^ { * } \beta \big | ^ { 2 } \right. \left. 0 \right] , \big | \beta \big | < 1
$$

and

$$
T _ { \mathrm { D } } = \frac { 1 } { 1 + \left| \alpha \right| ^ { 2 } } \left[ \begin{array} { c c c } { \left| \alpha \right| ^ { 2 } } & { \alpha } & { 0 } \\ { \alpha ^ { * } } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 0 } \end{array} \right] , \left| \alpha \right| < 1 .
$$

Thus,An et al.[15] improved Cui's method by implementing deorientation to minimize the (3,3) element of the coherency matrix of the third scattering component,and the (3,3) element can be much closer to zero.However, the(3,3) element is still not zero which is still not consistent with the models of(1)and (2).

Asan extension of Cui's method,thisletter is intended to develop a novel method to discriminate surface scattering and double-bounce scattering components from the RCM,and the proposed method manifests two main advantages: 1） all the three components are derived all using scattering models;2) After compensating the orientation angle(OA） variation (two OAs)and helix angle variation (two helix angles) for the RCM, the RCM is consistent with the models of(1） and(2),which leads to that all the powers are concentrated on co-polarization elements. Only in this circumstance, the compensated RCM is suitable to be used to derive the powers of the surface scattering and the double-bounce scattering components using the scattering models of(1) and(2).The powers are all positive as demonstrated by the results obtained by the proposed method using POLSAR data.

We briefly review the Cui's method in SectionII,introduce the proposed method in Section III,present experimental results and some discussions in Section IV and Section V,and finally conclude this letter in Section VI.

# II．BRIEF REVIEW OF CUI'S METHOD

The complete model-based three-component decomposition proposed by Cui et al. can be represented as [12]

$$
T = P _ { \mathrm { V } } T _ { \mathrm { V } } + P _ { \mathrm { S } } T _ { \mathrm { S } } + P _ { \mathrm { D } } T _ { \mathrm { D } }
$$

which can be also rewritten as

$$
\begin{array} { r } { T - P _ { \mathrm { V } } T _ { \mathrm { V } } = P _ { \mathrm { S } } T _ { \mathrm { S } } + P _ { \mathrm { D } } T _ { \mathrm { D } } . } \end{array}
$$

All the matrices in (4) should be physically meaningful, i.e the matrices should be positive semi-definite and do not have negative eigenvalues. The matrix $T - P _ { \mathrm { V } } T _ { \mathrm { V } }$ should also be positive semi-definite.Both Cui et al.and Wang et al. showed that the maximum possible volume scattering power is the minimum root of the cubic equation [12,13]

$$
\operatorname* { d e t } ( T - P _ { \mathrm { V } } T _ { \mathrm { V } } ) { = } 0
$$

where det(·) denotes matrix determinant. The methodof volume scattering power derivation is based on NNED without RS assumption.The derived maximum possible volume scattering power has also been suggested as the reasonable

value to be used [1O,11].

The RCM, ${ T } ^ { ' } = T  { - } T _ { \mathrm { V } } P _ { \mathrm { V } }$ , contains two single scatterers, i.e. the surface scatterer and the double-bounce scatterer.Cui et al. proposed two methods to discriminate these two single scatterers,which will be briefly reviewed in the following.

# A.The Algorithm 1

The first algorithm is based on eigenvalue/eigenvector decomposition of the RCM. The RCM is decomposed as

$$
T ^ { \prime } = \lambda _ { 1 } k _ { 1 } k _ { 1 } ^ { \mathrm { H } } + \lambda _ { 2 } k _ { 2 } k _ { 2 } ^ { \mathrm { H } }
$$

where the superscript $\mathrm { ~ H ~ }$ denotes the complex conjugate transpose.The eigenvectors $k _ { 1 }$ and $k _ { 2 }$ are then de-oriented, and are finally discriminated as surface scattering mechanism ordouble-bounce scattering mechanism based onthe co-polarized phase. The corresponding eigenvalues $\lambda _ { 1 }$ and $\lambda _ { 2 }$ will be assigned as the powers of the corresponding scattering mechanisms.

# B.The Algorithm 2

The second algorithm tries to fit a maximum power single surface (or double-bounce） scatterer with azimuth slope modulation to the RCM $T ^ { \prime }$ .The RCM can be represented as

$$
\boldsymbol { T } ^ { \prime } = \boldsymbol { P _ { \mathrm { S } } } \boldsymbol { R } ^ { H } ( \boldsymbol { \theta } ) \boldsymbol { T _ { \mathrm { S } } } \boldsymbol { R } ( \boldsymbol { \theta } ) + \boldsymbol { T } ^ { \prime \prime }
$$

where $R ^ { H } ( \theta ) T _ { \mathrm { S } } R ( \theta )$ is the azimuth slope modulated single scatterer, $\theta$ is the OA,and the OA rotation matrix is

$$
\begin{array} { r } { R ( \theta ) = \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { \cos { 2 \theta } } & { \sin { 2 \theta } } \\ { 0 } & { - \sin { 2 \theta } } & { \cos { 2 \theta } } \end{array} \right] . } \end{array}
$$

The value of $\theta$ can be derived by maximizing $P _ { \mathrm { S } }$ . The RCM is OA rotated as

$$
R ( \theta ) T ^ { \prime } R ^ { H } ( \theta ) = P _ { \mathrm { { S } } } T _ { \mathrm { { S } } } + R ( \theta ) T ^ { \prime } R ^ { H } ( \theta )
$$

The scattering mechanism of the power maximized single scatterer is determined by the value of the parameter $\beta$ of $T _ { \mathrm { S } }$ If $\left| \beta \right| < 1$ ,a power maximized rotated surface scatterer is fitted to the RCM,and a power maximized rotated double-bounce scatterer is fitted when $\left| \beta \right| \leq 1$ . The last scattering component is determined using the coherency matrix $R ( \theta ) T ^ { \prime } R ^ { H } ( \theta )$ ，whose corresponding scatteringmatrixis calculated, then de-oriented, and at last the scattering mechanism is determined based on co-polarized phase.

It can be seen that the powers of surface and double-bounce scatterers are derived from eigenvalues and eigenvectors for Algorithm 1,not from scattering models. For Algorithm 2, although the second scattering component is derived using scattering model,it is not the case for the third scattering component derivation， and the derivation procedure is complicated and ambiguous in physical meaning[15].

# III.THE PROPOSED METHOD

As an extension of Cui's method,the proposed method is devoted to discriminatingthesurfacescatteringand double-bounce scattering components from the RCM.

First,the volume scattering power is derived using Cui's method,and then the RCM is decomposed as shown in (6).

Then， the OA variation and helix angle variation are compensated for the RCM，i.e. the two eigenvectors are individually compensated for its OA and helix angle.The eigenvectorsaremodeled by the Kennaugh-Huynen's co-diagonalization of the scattering matrix [17,18]. $S _ { i }$ is assumed to be the corresponding scattering matrix of eigenvector $k _ { i }$ ， $i = 1 , 2$

$$
S _ { i } = R _ { \mathrm { S } } ( \theta _ { i } ) R _ { \mathrm { S } } ( \tau _ { i } ) S _ { \mathrm { d } i } R _ { \mathrm { S } } ( \tau _ { i } ) R _ { \mathrm { S } } ( - \theta _ { i } ) , i = 1 , 2
$$

where $S _ { \mathrm { d } i }$ is the diagonal matrix whose diagonal elements are complex co-eigenvalues $x _ { i 1 }$ and $x _ { i 2 }$ ，respectively. $\theta _ { i }$ and $\tau _ { i }$ are the OA and helix angle,respectively. The corresponding unitary transformation matrices are $R _ { \mathrm { S } } ( \theta _ { i } ) = { \left[ \begin{array} { l l } { \cos \theta _ { i } } & { - \sin \theta _ { i } } \\ { \sin \theta _ { i } } & { \cos \theta _ { i } } \end{array} \right] }$ and $\begin{array} { r } { R _ { \mathrm { S } } ( \tau _ { i } ) = \left[ \begin{array} { c c } { \cos \tau _ { i } } & { - j \sin \tau _ { i } } \\ { - j \sin \tau _ { i } } & { \cos \tau _ { i } } \end{array} \right] } \end{array}$ respectively. Then we expand and rewrite（1O) in Pauli basis,and consequently, the corresponding eigenvector $k _ { i }$ can be represented as

$$
k _ { i } = \left[ \begin{array} { c } { \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \cos { 2 \tau _ { i } } } \\ { \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \cos { 2 \theta _ { i } } + j \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \sin { 2 \tau _ { i } } \sin { 2 \theta _ { i } } } \\ { \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \sin { 2 \theta _ { i } } - j \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \sin { 2 \tau _ { i } } \cos { 2 \theta _ { i } } } \end{array} \right] .
$$

Hence, the OA $\theta _ { i }$ can be easily derived from(11) as

$$
\theta _ { i } = \frac { 1 } { 2 } \mathrm { a t a n } \left[ \frac { \mathrm { R e } \left[ { k _ { i } \left( 3 \right) \atop k _ { i } \left( 1 \right) } \right] } { \mathrm { R e } \left[ { k _ { i } \left( 2 \right) \atop k _ { i } \left( 1 \right) } \right] } \right] .
$$

The OA compensation for $k _ { i }$ is carried out by

$$
k _ { i } ^ { \prime } = R ( \theta _ { i } ) k _ { i }
$$

where $R ( \theta _ { i } )$ is the OA rotation matrix of (8),and $k _ { i } ^ { \prime }$ is OA compensated eigenvector as

$$
k _ { i } ^ { \prime } = \left[ \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \cos 2 \tau _ { i } \quad \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \quad - j \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \sin 2 \tau _ { i } \right] ^ { T } .
$$

The helix angle $\tau _ { i }$ is easily derived from(14) as

$$
\tau _ { i } = \frac { 1 } { 2 } \mathrm { a t a n } \Bigg ( \frac { j k _ { i } ^ { \prime } ( 3 ) } { k _ { i } ^ { \prime } ( 1 ) } \Bigg ) .
$$

The helix angle compensation for eigenvector is carried out as

$$
k _ { i } ^ { \prime \prime } { = } U _ { \tau } k _ { i } ^ { \prime }
$$

where $k _ { i } ^ { \prime \prime }$ is the OA and helix angle compensated eigenvector. The helix angle unitary transformationmatrix is $U _ { \tau } = \left[ \begin{array} { c c c } { { \cos 2 \tau } } & { { 0 } } & { { j \sin 2 \tau } } \\ { { 0 } } & { { 1 } } & { { 0 } } \\ { { j \sin 2 \tau } } & { { 0 } } & { { \cos 2 \tau } } \end{array} \right] ~ .$ The OA and helix angle

compensated eigenvector has the form

$$
k _ { i } ^ { \prime \prime } = \left[ \frac { x _ { i 1 } + x _ { i 2 } } { 2 } \quad \frac { x _ { i 1 } - x _ { i 2 } } { 2 } \quad 0 \right] ^ { T } .
$$

We can see that the cross-polarization element of the eigenvectoriszeronow after OA and helix angle compensations.

The compensated RCM $T _ { c } ^ { \prime }$ can be synthesized by combining the two compensated eigenvectors together as

$$
{ \cal T } _ { \mathrm { c } } ^ { \prime } = \sum _ { i = 1 } ^ { 2 } \lambda _ { i } k _ { i } ^ { \prime \prime } k _ { i } ^ { \prime \prime } { } ^ { H } .
$$

Itisinteresting to seethat not only $T _ { c } ^ { \prime } ( 3 , 3 )$ but also $T _ { c } ^ { \prime } ( 1 , 3 ) , T _ { c } ^ { \prime } ( 3 , 1 ) , T _ { c } ^ { \prime } ( 2 , 3 ) , T _ { c } ^ { \prime } ( 3 , 2 )$ of the compensated RCM are all zero now. It is noteworthy that $T _ { \mathrm { c } } ^ { \prime }$ is consistent with(1) and (2)，and $T _ { \mathrm { c } } ^ { \prime }$ can be used to derive the surface and double-bounce scattering components’ powers using scattering models of (1) and (2)

$$
\begin{array} { r } { T _ { \mathrm { c } } ^ { \prime } = P _ { \mathrm { S } } T _ { \mathrm { S } } + P _ { \mathrm { D } } T _ { \mathrm { D } } . } \end{array}
$$

If $T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) > T _ { \mathrm { c } } ^ { \prime } ( 2 , 2 )$ ， we assume $\alpha = 0$ ，and have $P _ { \mathrm { S } } = T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) + \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) } , P _ { \mathrm { D } } = T _ { \mathrm { c } } ^ { \prime } ( 2 , 2 ) - \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) }$ ; If $T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) \leq T _ { \mathrm { c } } ^ { \prime } ( 2 , 2 ) \quad , \quad \mathrm { w e } \quad \mathrm { a s s u m e } \quad \beta = 0 \quad ,$ and have $P _ { \mathrm { S } } = T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) - \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) } , P _ { \mathrm { D } } = T _ { \mathrm { c } } ^ { \prime } ( 2 , 2 ) + \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) } \ . \ P _ { \mathrm { S } } \mathrm { a n d } P _ { \mathrm { D } }$ are thus determined.The proposed extension of Cui's method is presented as Algorithm1 below.

# Algorithm1:An Extension of the Cui's Method

1: Input Tand $T _ { \mathrm { V } }$   
2: Solve cubic equation: ( $\mathrm { l e t } ( T { - } P \mathrm { v } T _ { \mathrm { V } } ) { = } 0$   
3:Select the minimum root to be the value of $P _ { \mathrm { V } }$   
4: Obtain the RCM: ${ \cal T } ^ { \prime } { = } { \cal T } { - } P _ { \mathrm { V } } { \cal T } _ { \mathrm { V } }$   
5: Implement eigendecomposition: $T ^ { \prime } = \lambda _ { 1 } k _ { 1 } k _ { 1 } ^ { \mathrm { H } } + \lambda _ { 2 } k _ { 2 } k _ { 2 } ^ { \mathrm { H } }$   
6:for $\dot { \mathbf { i } } = 1$ to 2 do   
7: Obtain OA $\theta _ { i }$ with (12)   
8: Implement OA compensation for $k _ { i }$ with (13)   
9: Obtain helix angle $\tau _ { i }$ with (15)   
10: Implement helix angle compensation for $k _ { i } ^ { \prime }$ with (16)   
11: Obtain OA and helix angle compensated $k _ { i } ^ { \prime \prime }$   
12:end for   
13: Obtain compensated RCM: $T _ { \mathrm { c } } ^ { \prime } = \lambda _ { 1 } k _ { 1 } ^ { \prime \prime } k _ { 1 } ^ { \prime \prime } { } ^ { H } + \lambda _ { 2 } k _ { 2 } ^ { \prime \prime } k _ { 2 } ^ { \prime \prime } { } ^ { H }$ （   
14:if $\begin{array} { r l } & { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) > T _ { \mathrm { c } } ^ { \prime } ( 2 , 2 ) \quad , \quad \mathrm { t h e n } \quad P _ { \mathrm { S } } = T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) + \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) } , } \\ & { P _ { \mathrm { D } } = T _ { \mathrm { c } } ^ { \prime } ( 2 , 2 ) - \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) } } \end{array}$   
15:else,then $P _ { \mathrm { S } } = T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) - \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) } , P _ { \mathrm { D } } = T _ { c } ^ { \prime } ( 2 , 2 ) + \frac { \left| T _ { \mathrm { c } } ^ { \prime } ( 1 , 2 ) \right| ^ { 2 } } { T _ { \mathrm { c } } ^ { \prime } ( 1 , 1 ) } ,$   
16:end if   
17: Output: $P _ { \mathrm { S } } , P _ { \mathrm { D } } , P _ { \mathrm { V } }$

# IV．EXPERIMENTALRESULTS

In this section, the decomposition results of Cui's Algorithm 1 and the proposed method on RADARSAT-2 dataset of San Francisco area arepresented and compared. Asthe performances of Cui's Algorithms 1 and 2 are similar [12],the decomposition results of Cui's Algorithm2 are omitted here for saving space.

The used RADARSAT-2 C-band data of San Francisco area were acquired on April 9， 2Oo8 in a fine-beam and quad-polarization mode. The original data are in single-look complex scattering matrix format,and the azimuth and ground range resolutions are about $4 . 8 2 \mathrm { ~ m ~ }$ and $4 . 7 3 \ \mathrm { m } .$ ，respectively. The data were then 6-look processed both in azimuth and ground range directions to get the coherency matrix data,after which they have a dimension of $2 4 0 2 \times 4 7 0$ pixels.There are ocean,park,and built-up areas in the scene.Color-coded decomposition results of Cui's Algorithm 1 and the proposed decomposition are shown in Fig.1. We only present a portion of the whole scene.The surface scattering，double-bounce scattering,and volume scattering contributions are color coded in blue,red,and green, respectively. It can be seen from Fig. 1 that,the color of ocean areas,which are surface scattering dominant areas,is blue as expected.The color of park area, which is volume scattering dominant area,is green.The color of built-up areas,which are double-bounce scattering dominant areas,is red in general.But in some largely oriented built-up areas,the color is yellow or even green,which means that the volume scattering contribution is still over-estimated even with the proposed method and Cui's method implemented. The averagespannormalized $T ^ { \prime } ( 3 , 3 )$ andaveragespan normalized $T _ { \mathrm { c } } ^ { \prime } ( 3 , 3 )$ by the proposed method for the whole image are computed, and are $6 . 5 9 \%$ and zero on the whole image,respectively.As pointed out in[15,16], the $T ^ { \prime } ( 3 , 3 )$ of the RCM,i.e. the cross-polarization power of surface scattering and double-bounce scattering components represented by （1) and(2),respectively,should be zero,which has been achieved by the proposed method.

To specifically demonstrate the different characteristics between the proposed method and Cui's Algorithm1 further, three typical patches are selected for detailed processing. The selected three patches are ocean area,built-up area,and central park area as shown in Fig.1(b).The surface scattering, double-bounce scattering， and volume scattering power proportions are shown in Table I.As can be seen from Table I, the power proportions by the two methods are similar generally. because of which that the visual effects of the decomposition results by the two methods of Fig.1 are similar generally.As can be seen from Table I, the surface scattering,double-bounce scattering,and volume scattering contributions are dominant in ocean area for patch1,in built-up area for patch 2,and in park area for patch3，respectively.One difference between the proposed method and Cui's Algorithm 1 is that the proposed method gets a litte higher surface scattering power,which is because that further helix angle compensation is adopted by the proposed method.Comparing(14) and(17),we can find that the cross-polarization element becomes zero after further helix angle compensation implemented，and the corresponding power of the cross-polarization will be transferred from $T ^ { \prime } ( 3 , 3 )$ to $T ^ { \prime } ( 1 , 1 )$ of the coherency matrix. The $T ^ { \prime } ( 1 , 1 )$ represents the surface scattering contribution in a sense.Thus, the surface scattering power obtained from the proposed method isa little higher.

In reality,it is still a problem in verifying that the result of which method is consistent with the ground truth.Hence,we just compare the performances of the proposed method and Cui's Algorithm1 here to demonstrate the characteristics of the two methods and the effectiveness of the proposed method.

# V．DISCUSSION

# A.The Necessity of Helix Angle Variation Compensation

In [1],Huynen used one parameter $F$ to represent the helicity of a distributed target, and the helicity is kind of global shape twist of the target.In [5],Yamaguchi et al.introduced helix scattering component as the fourth component of the scattering contribution froma target.In[17,18],Huynen and Touzi both used helix angle to characterize the asymmetry of the target. Thus, the helicity is the inherent characteristic of the target.

When using scattering models to discriminate the surface scattering and double-bounce scattering components from the RCM,the models of（1）and(2）are not consistent with the RCM[15,16].However, if we use the proposed method with OA variation compensation and further helix angle variation compensation for the RCM, then the compensated RCMis just consistent with the models (1） and (2). Actually,except for OAs of the surface scatterer and the double-bounce scatterer, the helix angles of the surface scatterer and the double-bounce scatterer also contribute to the cross-polarization,which can be demonstrated by and the third element of(14)and the helix scattering component of the Yamaguchi four-component decomposition [5]

$$
T _ { \mathrm { h e l i x } } = { \left[ \begin{array} { l l l } { 0 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { \pm 1 } \\ { 0 } & { \mp 1 } & { 1 } \end{array} \right] }
$$

When (1) and (2) were being modeled in [4],any OA and helix angle were not considered.Thus, OA variation and helix angle variation of the RCM must be compensated for before it is used to discriminate the surface scattering and double-bounce scattering components.

In addition,the helix angle $\tau _ { 1 }$ and $\tau _ { 2 }$ of the whole image is generally small. Thus, the effect on the decomposition results of helix angle compensation of(l6) is not so obvious,but the proposed method has necessarily accommodated the RCM to the scattering models.

# B.Interpretation of the Two Eigenvectors

Questions may be raised that how to interpret the two eigenvectors and which one is of surface or double-bounce scattering mechanism.Itis noteworthy that we do not interpret the scattering mechanisms of the two eigenvectors.The two orthogonal eigenvector can be considered as the projections of all the surface scatterers and double-bounce scatterers in one resolution cell to the orthogonal axes expanded by the two orthogonal eigenvectors.We just compensate for the OA variationandhelixanglevariationviaCloude's eigenvalue/eigenvector decomposition of the RCM, and combine the two compensated eigenvectors together as（18） to get the compensated RCM which is used to derive the powers of surface and double-bounce scattering components. The compensated RCM is also a positive semi-definite Hermitian matrix and physical realizable.

# C．Future Work

As shown in the results,although with the proposed method and Cui's method implemented, the scattering mechanism is still misinterpreted in some largely oriented built-up areas.The reason may be that the used volume scattering models do not fit all the scattering cases.The adaptive volume scattering model fitting all the scattering situations needs further study.

# VI．CONCLUSION

AnextensionoftheCui'scompletemodel-based decomposition is proposed in this letter,which provides a new method to discriminate the surface and double-bounce scattering components via compensating the OA and helix angle variation for the RCM using scattering models. As an alternate to Cui's method, it accommodates the RCM to the models of surface scattering and double-bounce scattering components.Its effectiveness is verified on the real POLSAR data.

# REFERENCE

[1]J.R. Huynen，“Phenomenological Theory of Radar Targets," Ph.D. Dissertation, Delf University of Technology, Delft, The Netherland,1970.   
[2]D,Li. and Y.H. Zhang,“Huynen dichotomy-based radar target adaptive extraction,”in Proc.PIERS 2O13,Stockholm, Sweden,2013, pp.881-885.   
[3] S.R. Cloude and E. Pottier，“A review of target decomposition theorems in radar polarimetry,”IEEE Trans. Geosci. Remote Sens., vol. 34, no.2, pp. 498-518,Mar. 1996. [4] A.Freeman and S.L.Durden,“A three-component scattering model for polarimetric SAR data,”IEEE Trans. Geosci. Remote Sens., vol.36, no. 3, pp. 963-973,May 1998. [5]Y.Yamaguchi,T.Moriyama,MIshido,and H.Yamada, "Four-component scattering model for polarimetric SAR image decomposition,"IEEE Trans.Geosci.Remote Sens.,vol.43,no. 8,pp.1699-1706,Aug.2005.   
[6]W. T． An，Y.Cui，and J. Yang，“Three-component model-based decomposition for polarimetric SAR data,’IEEE Trans. Geosci. Remote Sens.,vol.48, no.6,pp.2732-2739,Jun. 2010.   
[7]J.-S.Lee and T.L.Ainsworth,“The effect of orientation angle compensation on coherency matrix and polarimetric target decompositions,"IEEETrans.Geosci.Remote Sens.,vol. 49, no.1, pp.53-64, Jan.2011.   
[8]Y.Yamaguchi,A.Sato,W.M.Boerner,R.Sato,and H. Yamada,“Four-component scattering power decomposition with rotation of coherency matrix,”IEEE Trans. Geosci. Remote Sens., vol. 49, no. 6, pp.2251-2258,Jun.2011.   
[9] S. W. Chen, X. S.Wang, S.P.Xiao,and M. Sato,“General polarimetricmodel-baseddecompositionforcoherency matrix,” IEEE Trans. Geosci. Remote Sens., vol. 52, no. 3, pp. 1843-1855,Mar. 2014.   
[10]J.J. van Zyl, Y.Kim,and M. Arii,“Requirements for model based polarimetric decompositions,"in Proc. Int. Geosci. Remote Sens. Symp.,2008, pp. V-417-V-420.   
[11]J.J. van Zyl，M. Arii,and Y.Kim,“Model-based decomposition of polarimetric SAR covariance matrices constrained for nonnegative eigenvalues,”IEEE Trans.Geosci. Remote Sens., vol.49,no.9, pp.1104-1113, Sep.2011.   
[12]Y.Cui,Y.Yamaguchi, J.Yang,H.Kobayashi,S.Park, and G. Singh,“On complete model-based decomposition of polarimetric SAR coherencymatrix data,”IEEE Trans.Geosci. Remote Sens., vol.52, no. 4, pp.1991-2001,Apr. 2014.   
[13] C. L. Wang, W. D. Yu, R. Wang, Y. K. Deng, and F. J. Zhao,“Comparison of nonnegative eigenvalue decompositions with and without reflection symmetry assumptions,” IEEE Trans. Geosci. Remote Sens., vol. 52, no. 4, pp. 2278-2287, Apr.2014.   
[14] J. S. Lee,T.L. Ainsworth,and Y. Wang,“Generalized polarimetric model-based decompositions using incoherent scattering models," IEEE Trans. Geosci. Remote Sens., vol.52, no.3,pp.1705-1718,May 2014.   
[15] W.T.An, C.H. Xie,“An improvement on the complete model-based decomposition of polarimetric SAR data,”IEEE Geosci, Remote Sens, Lett., vol.11, no. 411,pp.1926- 1930, Nov. 2014.   
[16] W. T. An, M. S.Lin, C.H. Xie,“An Interpretation of A Coherency Matrix With Three Scattering Mechanisms,” in Proc.IGARSS,Milan, Italy,Jul.2015.   
[17] J.R. Huynen,“Measurement of the target scatering matrix,” Proc. IEEE,vol. 53,no.8,pp. 936-946,Aug.1965. [18]R.Touzi,‘Target scattering decomposition in terms of roll-invariant target parameters,” IEEE Trans. Geosci. Remote Sens., vol. 45,no.1, pp. 73-84, Jan. 2007.

TABLEI AVERAGE SCATTERING PROPORTIONS OF SURFACE SCATTERING, DOUBLE-BOUNCE SCATTERING,AND VOLUME SCATTERING COMPONENTSINSELECTED THREEPATCHES   

<html><body><table><tr><td></td><td>Algorithm</td><td>Ps/SPAN</td><td>PD/SPAN</td><td>Pv/SPAN</td></tr><tr><td rowspan="2">Patch 1</td><td>Proposed method</td><td>94.38%</td><td>2.52%</td><td>3.1%</td></tr><tr><td>Cui's Algorithm1</td><td>94.35%</td><td>2.55%</td><td>3.1%</td></tr><tr><td rowspan="2">Patch 2</td><td>Proposed method</td><td>31.49%</td><td>57.49%</td><td>11.02%</td></tr><tr><td>Cui's Algorithm 1</td><td>29.19%</td><td>59.79%</td><td>11.02%</td></tr><tr><td rowspan="2">Patch 3</td><td>Proposed method</td><td>36.66%</td><td>15.23%</td><td>48.11%</td></tr><tr><td>Cui's Algorithm1</td><td>35.57%</td><td>16.32%</td><td>48.11%</td></tr></table></body></html>

![](images/094b54143864bf738902980f001004730214abe0bcfb9e87e8317bfcb00134c9.jpg)  
Fig.1.Decomposition results on RADARSAT-2 data of San Francisco by (a) Cui's Algorithm 1 and (b) the proposed method.