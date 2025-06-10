# A NOVEL INTERPRETATION OF THE POLSAR COHERENCY MATRIX DATA

Feiya Zhut\*, Yunhua Zhang\*, and Dong $L i ^ { \dagger }$

+Key Laboratory of Microwave Remote Sensing, National Space Science Center, Chinese Academy of Sciences, Beijing 100190, China \*University of Chinese Academy of Sciences, Beijing 100049, China

# ABSTRACT

Cloude-Pottier incoherent target decomposition (ICTD and Touzi ICTD has been widely applied as a popular approach to interpret the scattering characteristics of a targetinpolarimetricsyntheticapertureradar (PolSAR） data processing. However， they have a common drawback，i.e. proliferation of parameters (PoP)isunavoidable.Paladini et al. solved this problem by developing an orientation-invariant ICTD based on the coherencymatrixunder circular polarization basis. Asan alternative to Paladini decomposition，we proposed a novel ICTD based on the frequently used coherency matrix under linear polarization basis. The proposed method can also avoid the problem of PoP,and avoid the ambiguity of alpha angle of Paladini decomposition as well. Real PolSAR data is processed to validate the proposed decomposition.

Index Terms—Coherency matrix, ICTD,PolSAR, targetdecomposition

# 1.INTRODUCTION

Target decomposition is a popular way for target understanding in polarimetric synthetic aperture radar (PolSAR） data processing. Target decomposition includes two categories:coherenttarget decomposition(CTD） based on the scattering matrix and incoherent target decomposition (ICTD） based on the second order statistical coherency matrix or covariance matrix. As the incoherent scattering is general in real situation,ICTD has attracted much attention.ICTD originates fromHuynen decomposition [1]. Due to its preference for symmetry and regularity，Huynen decomposition has not been widely applied[2].Nowadays,the hotspots of ICTD areeigen-decomposition[3-5] and model-based decomposition [6-13].

Eigen-decomposition was pioneered by Cloude and Pottier 3]，which was criticized by Huynen that seriousproliferationofparameters(PoP) was generated [14]. Touzi also designed a successful ICTD based on his target scattering vector model (TSVM) [4],but PoP was still a problem. Paladini et al. proposed a novel ICTD of the coherency matrix under circular polarization basis,and successfully solved the problem of PoP[5]. A potential limitation of Paladini decomposition is that its alpha angle is identical to Cloude-Pottier alpha angle,while the helix angle is mixed in the alpha angle.

For model-based decomposition, the three-component decomposition or four-component decomposition is clear in physical meaning,and easy to be implemented [6-9].However, their disadvantage is information loss. Chenetal.proposedanovelmodel-based decomposition with separate orientation angle for oddand double-bounce models [1O],but we think the helix component should be modeled as the asymmetry of odd-and even-bouncescatterers， notasan independent scattering component. Van Zyl et al., Cui et al.,and Wang et al. proposed nonnegative eigendecomposition [11-13]， but theinterpretationof scattering mechanisms is partially based on eigendecomposition, not on scattering models.

As an alternative to Paladini decomposition, our ICTD which bases on the coherency matrix under linear polarization basisalso avoidsPoP,and also avoids the alphaangle ambiguityofPaladini ICTD.

# 2.MATRIXDEFINITIONS

For coherent scattering, the full polarimetric scattering information is contained in the scattering matrix

$$
\begin{array} { r } { S = \left[ \begin{array} { l l } { S _ { H H } } & { S _ { H V } } \\ { S _ { V H } } & { S _ { V V } } \end{array} \right] } \end{array}
$$

where the subscript $H V$ denotes vertical polarization transmission and horizontal polarization reception. Two of frequently used scattering vectors are the scattering vector $k _ { \mathrm { P } }$ in Pauli basis and the scattering vector $k _ { \mathrm { { C } } }$ in circularpolarization basis

$$
k _ { \mathrm { P } } = \frac { 1 } { \sqrt { 2 } } \big [ S _ { H H } + S _ { V V } \quad S _ { H H } - S _ { V V } \quad 2 S _ { H V } \big ] ^ { t }
$$

$$
k _ { \mathrm { { C } } } = { \left[ { S _ { L L } \sqrt { 2 } S _ { L L _ { \perp } } S _ { L _ { \perp } L _ { \perp } } } \right] } ^ { t }
$$

where the superscript $t$ denotes matrix transposition, and the subscripts $L$ and $L _ { \textrm { \perp } }$ denote left circular polarization and left orthogonal polarization.

Forincoherentscattering， thefullpolarimetric information is contained in the second order statistical coherency matrix $T$ in linear polarization basisor coherencymatrix $G$ in circular polarization basis

$$
T = \left. k _ { \mathrm { P } } \cdot k _ { \mathrm { P } } ^ { \dagger } \right.
$$

$$
G = \left. k _ { \mathrm { C } } \cdot k _ { \mathrm { C } } ^ { \dagger } \right.
$$

where $\left. < \cdot > \right.$ denotes time average or spatial average, and the superscript $\dagger$ denotes complex conjugation and transposition．Both $T$ and $G$ have nine degrees of freedom (DoFs).

The Cloude-Pottier, Touzi,and the proposed ICTDs are based on the coherency matrix $T _ { \cdot }$ ，while the Paladini ICTD is based on the coherency matrix $G$ （204号

# 3.THEPROPOSEDICTD

The proposed ICTD is based on eigen-decomposition of the coherency matrix $T$

$$
{ \cal T } = U \Lambda U ^ { \dagger }
$$

where $\Lambda$ is the diagonal matrix whose diagonal elements are the eigenvalues $\lambda _ { 1 } , \ \lambda _ { 2 }$ ，and $\lambda _ { 3 }$ ，with $\lambda _ { 1 } { \ge } \lambda _ { 2 } { \ge } \lambda _ { 3 }$ assumed,and $\mathrm { ~ U ~ }$ iscomprised of three columns of eigenvectors $k _ { 1 } , k _ { 2 }$ ,and $k _ { 3 }$

The matrix U is modelled by the multiplication of six unitary transformation matrices,and the DoF of each unitary transformation matrix is one

$$
U = [ k _ { 1 } \quad k _ { 2 } \quad k _ { 3 } ] = \prod _ { i = 1 } ^ { 6 } S U ( w _ { i } )
$$

In the following subsections we will detail the models of the matrices $\Lambda$ and U.

# 3.1.Information extraction from the matrix $\mathbf { A }$

The matrix $\Lambda$ has the form $\Lambda { \mathrm { = } } { \mathrm { { d i a g } } } ( \lambda _ { 1 } , \lambda _ { 2 } , \lambda _ { 3 } )$ . It has three independent parameters.For convenient physical informationextraction，otherthreephysical meaningful parameters are here suggested to replace the three eigenvalues,i.e. the total power SPAN,the scattering entropy $\mathrm { ~ H ~ }$ ,and the anisotropy A

$$
S P A N = \lambda _ { 1 } + \lambda _ { 2 } + \lambda _ { 3 }
$$

$$
H = - \sum _ { i = 1 } ^ { 3 } p _ { i } \log _ { 3 } p _ { i } \mathrm { , w i t h } p _ { i } = \frac { \lambda _ { i } } { \lambda _ { 1 } + \lambda _ { 2 } + \lambda _ { 3 } }
$$

$$
A = \frac { \lambda _ { 2 } - \lambda _ { 3 } } { \lambda _ { 2 } + \lambda _ { 3 } }
$$

The SPAN is the total power backscattered from the target,which was introduced by Cao et al.into the classification applications [15]. The entropy $\mathrm { ~ H ~ }$ is an indicator of the scattering randomness. The anisotropy A is also physical meaningful.

# 3.2.Model of the matrix U

As the matrix $\Lambda$ has three DoFs, the matrix U has only six DoFs.

3.2.1. Model of the dominant eigenvector $k _ { I }$ For three dimensional complex vector $k _ { 1 }$ , there are six DoFs.Two DoFs are lost because of 1) absolute phase indetermination and 2） unitary restriction [5]. Thus four independent parameters are used to model $k _ { 1 }$

We model $k _ { 1 }$ using Touzi's TSVM as

$$
\begin{array} { r l } & { \begin{array} { r l } { [ 1  } & { 0 } \\ { [ 0 . ~ \mathrm { s u b } _ { 2 } \mathrm { e } ^ { \mathrm { i } \varphi } - \mathrm { s i n } _ { 2 } \mathrm { e } ^ { \mathrm { i } \varphi } ] \Biggl [ \cos \alpha _ { x } \cos \alpha _ { x } \cos 2 \mathrm { e } _ { \mathrm { i } } } \\ {  \sin \alpha _ { x } \cos 2 \mathrm { e } _ { \mathrm { i } } - \mathrm { s i n } _ { 2 } \mathrm { e } ^ { \mathrm { i } \varphi } ] \Biggl [ \sin \alpha _ { x } \cos \alpha _ { x } \sin 2 \mathrm { e } _ { \mathrm { i } } } \\ {  0 \sin 2 \mathrm { e } _ { \mathrm { p } } - \cos 2 \mathrm { e } _ { \mathrm { p } } ] [ - j \cos \alpha _ { x } \sin 2 \mathrm { e } _ { \mathrm { i } } } \\ {  0 ] [ 1  } & { 0 } \end{array} ] } \\ &  = [ \begin{array} { l } { 1 } \\ { 0 } & { \cos 2 \mathrm { e } _ { x } \sin 2 \mathrm { e } _ { \mathrm { p } } \Biggr ] [ 0 . \mathrm { e } ^ { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } \exp ( \frac { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } { \mathrm { B } _ { \mathrm { p } } } ) \exp ( \frac { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } { \mathrm { B } _ { \mathrm { p } } } ) } \\ {  0 \sin 2 \mathrm { e } _ { \mathrm { p } } \cos 2 \mathrm { e } _ { \mathrm { p } } ] [ 0 . \mathrm { e } ^ { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } ] \Biggr ] } \\ { [ \cos 2 \mathrm { e } _ { \mathrm { p } } - \mathrm { s i n } _ { 2 } \mathrm { e } ^ { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } ] [ \cos 2 \mathrm { e } _ { \mathrm { p } } - \sin \alpha _ { x } \cos \mathrm { e } _ { \mathrm { i } } \mathrm { \Theta } _ { 0 } ] [ ] } \\ { [ - j \sin 2 \mathrm { e } _ { \mathrm { i } } \mathrm { e } ^ { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } \cos 2 \mathrm { e } _ { \mathrm { i } } \mathrm { e } ^ { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } ] [ 0 . \mathrm { e } ^ { \mathrm { i } \mathrm { B } _ { \mathrm { p } } } ] [ \begin{array} { l } { 1 } \\ { 0 } \\ { 0 } \end{array} ] } \end{array} \end{array}
$$

The parameter $\psi$ is the orientation angle of $k _ { 1 }$ . The parameter $\tau _ { \mathrm { { m } } }$ is the helix angle of $k _ { 1 }$ ，which measures the asymmetry of the target represented by $k _ { 1 }$ . The parameter $a _ { \mathrm { s } }$ is the scattering type magnitude,which is an important parameter used to discriminate the oddand the even-bounce scatterings. The parameter $\Phi _ { \mathrm { a s } }$ is the scattering type phase，which can be used to discriminate dipoles and quarter waves and has been used for ship recognition and other applications [4].

Thealpha angle of Paladini ICTD is identical to the Cloude-Pottier alpha angle. But the Cloude-Pottier alpha angle is a mixer of alpha angle and helix angle, itis ambiguous in physical meaning [4]. The parameter $ { a _ { \mathrm { s } } }$ of TSVM or our ICTD can avoid such ambiguity.

The four parameters have clear physical meanings. They eliminate some ambiguities of the Cloude-Pottier alpha-betamodel [4].

3.2.1.Model of the subdominant eigenvectors As the matrix U has six DoFs,and the dominant eigenvector has four DoFs.Thus only two DoFs are left in the two subdominant eigenvectors $k _ { 2 }$ and $k _ { 3 }$ Afterconductingthe following unitary transformations, we can get [5]

$$
\begin{array} { r l } & { X = S U ( - \alpha _ { s } ) S U ( - \tau _ { m } ) S U ( - \Phi _ { \alpha s } ) S U ( - \psi ) U } \\ & { = \left[ \begin{array} { l l l } { 1 } & { 0 } & { 0 } \\ { 0 } & { x _ { 1 } } & { x _ { 2 } } \\ { 0 } & { x _ { 3 } } & { x _ { 4 } } \end{array} \right] . } \end{array}
$$

The subdominant eigenvectors are modelled by two unitarytransformationmatricesas follows

$$
\begin{array} { r l } & { \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { x _ { 1 } } & { x _ { 2 } } \\ { 0 } & { x _ { 3 } } & { x _ { 4 } } \end{array} \right] = S U ( \Gamma ) S U ( \Psi ) } \\ & { = \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { e ^ { - j 2 \Gamma } } & { 0 } \\ { 0 } & { 0 } & { e ^ { j 2 \Gamma } } \end{array} \right] \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { \cos 2 \Psi } & { - \sin 2 \Psi } \\ { 0 } & { \sin 2 \Psi } & { \cos 2 \Psi } \end{array} \right] . } \end{array}
$$

The parameter $\Psi$ measures the relative magnitude of the second and third elements of the eigenvector, which is interpreted as the local orientation angle of the target. The parameter $\Gamma$ introduces some phase difference containing the information of the local helix of the target. The physical basis of these two parametersneedsfurther validation.

In [16], the last two parameters are interpreted as the "relative orientation”and “relative helicity”,and they are both depolarization parameters.

In low entropy scattering situation， the dominant eigenvector described by four parameters accounts for the dominant or global scattering characteristics. The subdominant eigenvectors described by the remained two parameters account for the local scattering characteristics of the target. In high entropy scattering situation， the scattering power of the subdominant eigenvectors are comparable to that of the dominant eigenvector, and more information is contained in the last two parameters compared to the low entropy situation.

By the proposed ICTD,nine independent parameters are decomposed from the coherency matrix, i.e. SPAN, H, A, $\psi , \tau _ { \mathrm { m } } , \alpha _ { \mathrm { s } } , \Phi _ { \mathrm { a s } } , \Psi$ ,and I. Thus the proposed ICTD can avoid the problem of PoP.All the decomposed parameters have explicit physical meanings.

# 4.EXPERIMENTALRESULTS

In this section, RADARSAT-2 C-band PolSAR data of San Francisco Bay area are processed to demonstrate theinherentphysicalmeaningsofthenine decomposed parameters.

The data are in single-look complex format.A refined Lee filter is then applied to suppress the speckle and get the coherency matrix format data. Only a part of the scene isutilized.

The total power SPAN is shown in Fig.1(a),as one can see，dihedrals with specular scattering usually have higher backscattered powers. The scattering entropy His shown in Fig.1(b),from which one can see that the park area and the oriented urban area with higher scattering randomness have higher entropy. The anisotropy A is shown in Fig.1(c). For ocean area and urban area, the minimum eigenvalue is very small,and thus A is large.The orientation $\psi$ of the dominant eigenvectoris showninFig.1(d),where the blue color areareasonablycorrespondsto the orientedurban area. The helix angle $\tau _ { \mathrm { m } }$ of the dominant eigenvector is shown in Fig.1(e),where small value of helix angle is exhibited for the whole scene. The scattering type magnitude $a _ { \mathrm { s } }$ is shown in Fig. 1(f),which is close to $\pi / 2$ for urban area, while close to zero for ocean area. The scattering type phase $\Phi _ { \mathrm { a s } }$ is shown in Fig. 1(g), which also contains physical information as addressed before.The local orientation $\Psi$ is shown in Fig. 1(h), which is large for oriented urban area and park area because the sub-scatterers in the cell have diverse orientations. The local helix angle $\Gamma$ is shown in Fig. 1(i),and it is noise generally.

# 5.DISCUSSION

Similaritiesand differencesof the Paladini ICTD and the proposed ICTD are addressed.

First,the similarities are 1） they both avoid the problem of PoP;2) they are both serial (multiplicative) decompositions,while other common decompositions which are parallel（additive）decompositions.3） the helix angles of both ICTDs have ambiguities.The helix angle cannot describe the asymmetry when $ { a _ { \mathrm { s } } }$ equals $\pi / 2$ for proposed ICTD,while the helix angle cannot describe the asymmetry when alpha angle equals zero for PaladiniICTD.

Second，the differences are 1）our proposed ICTD bases on the frequently used coherency matrix $T _ { \cdot }$ while Paladini ICTD bases on the coherency matrix $G$ 2） the dominant eigenvector model for our ICTD is based on TSVM,and it eliminates the alpha angle ambiguity ofPaladini ICTD;

# 6. CONCLUSION

A novel serial (multiplicative) ICTD of the coherency matrix is proposed with nine decomposed independent parameters obtained and all of them have explicit physical meanings. Theproposeddecomposition successfullyavoidstheproblemofPoP.RealPolSAR data are processed to demonstrate the effectiveness of the proposed approach. The classification method based on these nine parameters is under study.

# 7.REFERENCE

[1]J.R.Huynen,“Phenomenological theory of radar targets," Ph.D.Dissertation，Delf University of Technology，Delft,The Netherland,1970.   
[2] D,Li.and Y.H. Zhang,“Unified Huynen Phenomenological DecompositionofRadarTargetsandItsClassification Applications,” IEEETrans. Geosci. RemoteSens.，DOI: 10.1109/TGRS.2015.2464113 (In Press).   
[3] S.R.Cloude and E.Pottier,“A review of target decomposition theoremsinradarpolarimetry,”IEEETrans.Geosci.Remote Sens., vol.34,no.2,pp.498-518,Mar.1996.   
[4] R.Touzi,“Target scattering decomposition in terms of rollinvariant target parameters,”IEEETrans.Geosci.Remote Sens., vol.45,no.1, pp.73-84,Jan.2007.   
[5]Paladini，L.R.Ferro-Famil，E.Pottier，M.Martorella,F. Berizzi,and E.Dalle Mese,‘Lossless and sufficient psi-invariant decomposition of random reciprocal target,’IEEE Trans. Geosci. Remote Sens.,vol.50,no.9,pp.3487-3501,Sep.2012. [6] A.Freeman and S.L. Durden,“A three-component scattering model forpolarimetric SAR data,”IEEE Trans.Geosci.Remote Sens.,vol.36,no.3,pp.963-973,May 1998.   
[7] W.T. An,Y.Cui,and J. Yang,“Three-component modelbased decomposition for polarimetric SAR data,”IEEE Trans. Geosci.Remote Sens.,vol.48,no.6,pp.2732-2739,Jun.2010. [8] Y.Yamaguchi,A.Sato，W.M.Boerner,R.Sato,and H. Yamada,“Four-component scattering power decomposition with rotation of coherency matrix,” IEEE Trans. Geosci. Remote Sens., vol. 49, no.6, pp.2251-2258,Jun.2011.   
[9]J.S.Lee，T.L.Ainsworth,and Y.Wang,“Generalized polarimetricmodel-baseddecompositionsusingincoherent scattering models,”IEEE Trans.Geosci.Remote Sens.,vol.52, no. 3, pp.1705-1718,May 2014.   
[10] S.W.Chen,X.S.Wang,S.P.Xiao,and M.Sato,“General polarimetric model-based decomposition for coherency matrix," IEEE Trans. Geosci. Remote Sens., vol. 52, no.3,pp.1843-1855, Mar.2014.   
[11]J.J. van Zyl,M.Arii,and Y.Kim,“Model-based decompositionofpolarimetricSARcovariancematrices constrained for nonnegative eigenvalues,” IEEE Trans. Geosci. Remote Sens.,vol.49,no.9,pp.1104-1113,Sep.2011.   
[12] Y. Cui,Y.Yamaguchi, J.Yang,H. Kobayashi, S.Park,and G. Singh,“On complete model-based decomposition of polarimetric SAR coherency matrix data,” IEEE Trans.Geosci. Remote Sens., vol. 52,no.4, pp.1991- 2001,Apr. 2014.   
[13] C.L.Wang,W.D. Yu,R,Wang,Y.K.Deng,andF.J. Zhao, “Comparison of nonnegative eigenvalue decompositions with and without reflection symmetry assumptions,”IEEE Trans. Geosci. Remote Sens.,vol. 52,no.4,pp.2278-2287,Apr.2014.   
[14] J.R.Huynen,“Comments on target decomposition theorems,” in Direct and Inverse Methods in Radar Polarimetry，W.-M. Boerner et al.,Eds. Dordrecht, The Netherlands: Kluwer,1992,pt. 1,pp.387-399.   
[15] F.Cao,W.Hong,Y.Wu,and E.Pottier,“An unsupervised segmentation with an adaptive number of clusters using the SPAN/H/alpha/A space and the complex wishart clustering for fullypolarimetric SAR data analysis,”IEEE Trans.Geosci. Remote Sens.,vol. 45,no.11, pp.3454-3467,Nov.2007.   
[16] T.L. Ainsworth,S.R. Cloude and J. S.Lee,“Eigenvector Analysis of Polarimetric SAR Data,”Proceedings IGARSS'02, Toronto,2002.

![](images/48a8092019d44809b4e778750f9c79933aa518165f632b9eb1a8c38332f6bbe6.jpg)

![](images/22ec600c8068d9f567db3f7aa5b4431d0df8dda154d7b4f13c9348586bf79ac6.jpg)  
Figure. 1. Results of the parameters (a) SPAN, (b) H, (c) A, (d) $\psi$ (e) $\tau _ { \mathrm { m } } ,$ (f) $a _ { \mathrm { s } }$ (g） $\Phi _ { \mathrm { a s } } ,$ (h) $\Psi$ ,and (i) $\Gamma$