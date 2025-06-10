# Thermal Analysis of Resin Composites with Ellipsoidal Filler Considering Thermal Boundary Resistance

Yusuke Asakumal\* and Tsuyoshi Yamamoto²

1. Department of Chemical Engineering, University of Hyogo,Himeji, Japan   
2.Department of Chemical Engineering,Kyushu University, Fukuoka, Japan

The effective thermalconductivity of composites with elipsoidal fillers is analyzed by using a homogenization method that is able to represent the microstructure precisely.Inthis study,various parameters suchas the volume fraction,shape,and distribution of the filer are quantitatively estimated to understand the mechanisms of heat transfer in the composite.First,thermal boundary resistance between resin and filler is important for obtaining composites with higher thermal conductivity.Second,theanisotropyof theefective thermalconductivity arises from contact between filler in the case of ellpsoidal filler and produces lower thermal resistance.Finaly,the filler network and thermal resistance are essential for the heat transfer incomposites because the path of thermal conduction is improved by contact between neighboring filler particles.

# Keywords: effective thermal conductivity, homogenization method,multiscale analysis,composite

# Introduction

The thermal conductivity of resin is typically around 0.15 to $0 . 3 \mathrm { ~ W } / ( \mathrm { m } \cdot \mathrm { K } )$ ，which is much lower than that of metals and ceramics.Resin has thus often been used as an adiabatic material and for reinforcement due to its advantages of lower heat conduction and higher strength. In the last two decades,demand has grown for resins withhigher conductivity and better heat dissipation characteristicsinthe fieldof electronicsbecause of thebetter formability of resins compared with metals and ceramics [1,2].However, there are limits on how much the conductivity can be increased. To obtain higher conductivity, modification of composites has been performed by the addition of filler,which is a metal and ceramic of higher thermal conductivity. However, the mechanism of heat transfer in composites is quite complex because of the following factors related to obtaining effective thermal conductivity (ETC) [3-5].

1.Thermal conductivity of resin and filler   
2. Volume fraction of dispersed filler material   
3.Shape and size of filler   
4.Dispersion condition of filler particles   
5.Thermal boundary resistance between resin and fil

There are many methods for analyzing the ETC of composites [6-11]. However, it is quite difficult for conventional analytical models to model the above-mentioned factors perfectly. Direct numerical simulation, which can represent the microstructure of a composite with fillers of various shapes and volume fraction is required for precise thermal analysis.In our previous studies,we developed a homogenization method for thermal analysis of porous media [12] and packed beds [13] with complex structures.The method employs a three-dimensional finite element method that enables calculation of the ETC,making this approach very useful because it is able to consider changes in microstructure precisely. For example,the geometric anisotropy of the microstructure depending on pore shape and configuration was examined precisely, and the importance of microstructure was shown quantitatively for heat transfer in porous media and packed beds.Accordingly, this homogenization method is attractive for obtaining more quantitative information about the above-mentioned factors in composites [14,15].However, little research has focused on perfect modeling of the volume fraction, shape,and distribution of the filler in composites.In particular,experimental estimation of thermal boundary resistance between resin and filler particles has been difficult although it is caused by incomplete interfacial contact such as void. In this study,we investigate thermal behavior in composites while simultaneously considering factors 1,2,3,4 and 5 described above by means of our homogenization method.The resistance between fillers might be important.Moreover,although this method can also simultaneously consider factors 6 and 7 and different size of fillers,this study focuses on factors 1 to 5 which are related to heat transfer in composites.Finally, the ETC of composite is compared to that of porous medium with ellipsoidal pores.

# Model

# Homogenization method

To analyze the composites shown in Fig. 1(a),the simple periodic structure shown in Fig. 1(b) is assumed. The unit cell of the periodic structure consists of two domains: solid 1 (resin), $\Omega _ { \mathrm { s l } }$ ,and solid 2 (filler), $\Omega _ { \mathrm { s } 2 }$ as shown in Fig. 1(c). $\boldsymbol { \varGamma }$ denotes the interface between the two domains.

![](images/a4da0ab5cdd073cb57fcda691b0630841895d6b0546edb36a4196b3ffcbc76b5.jpg)  
Fig.1 Schematic diagram of homogenization method

The microscopic scale (filler size, $l )$ ）in the periodic domain $\Omega$ is small compared with the characteristic length $L$ at the macroscopic scale.

The multiscale periodic heat conduction problem under steady-state conditions without heat generation can be mathematically expressed as

$$
- \frac { \partial } { \partial x _ { j } } \left( \lambda _ { s 1 } \frac { \partial T _ { s 1 } } { \partial x _ { j } } \right) = 0 \mathrm { i n } \Omega _ { s 1 } ,
$$

$$
- \frac { \hat { \sigma } } { \hat { \sigma } x _ { j } } \left( \lambda _ { s 2 } \frac { \hat { \sigma } T _ { s 2 } } { \hat { \sigma } x _ { j } } \right) = 0 \mathrm { i n } \Omega _ { s 2 } ,
$$

$$
- \lambda _ { s 1 } { \frac { { \hat { \sigma } } T _ { s 1 } } { { \hat { \sigma } } x _ { j } } } \mathbf { n } _ { j } = h \left( T _ { s 1 } - T _ { s 2 } \right) \ { \mathrm { ~ o r ~ } }
$$

$$
- \lambda _ { s 2 } \frac { \partial T _ { s 2 } } { \partial x _ { j } } { \bf n } _ { j } = h \left( T _ { s 2 } - T _ { s 1 } \right) \mathrm { o n } \mathrm { ~ \bf ~ \cal ~ \Gamma ~ } ,
$$

where $\lambda$ and $T$ are the thermal conductivity and temperature field,respectively,and $h$ is the coefficient of thermal boundary resistance between the two domains. It is caused by the incomplete contact. The Biot number is given by

$$
\mathrm { B i } \equiv \frac { h l } { \lambda _ { s 1 } } .
$$

Finally, the ETC is obtained as a homogenized parameter by multiscale asymptotic expansion.Details of the calculations are described in the packed bed analysis of our previous study[13],with gaseous and solid phases in the reference corresponding to solids 1 and 2 in the composite, respectively.

In the present study, finite element meshes of simple cubic(SC)，body-centered cubic(BCC)，andfacecentered cubic(FCC) configurations are created as filler positions in the composites by using a tetragonal mesh by the Delaunay triangulation algorithm [16]. Ellipsoidal fillerparticles with $b = c > a$ are distributed in the cell as shown in Fig.2.ETC is calculated for composites with ellipsoidal fillers of $a / c = 0 . 2 5$ ，0.50,0.75,and1.0 for various Biot numbers and volume fractions $\rho ,$ and the mechanisms behind the manifestation of anisotropy of $\lambda _ { \mathrm { x } }$ and $\lambda _ { \mathrm { y } } \left( = \lambda _ { \mathrm { z } } \right)$ are examined.

![](images/852c1d46cba56e6fbb9195777140a29fb4806324a027b5c6d81826a5f5c3b61d.jpg)  
Fig.2Unit cell of composite containing ellipsoidal filler

# Materials

The thermal conductivity of the epoxy resin, $\lambda _ { \mathrm { s l } }$ is kept constant $( \lambda _ { \mathrm { s l } } = 0 . 2 )$ in this study. The thermal conductivity of the filler, $\lambda _ { \mathrm { s } 2 }$ ，is set to 5，30,and 170 $\mathrm { W } / ( \mathrm { m } { \cdot } \mathrm { K } )$ , which corresponds to the conductivity of metal and ceramic ( ${ \mathrm { . A l } } _ { 2 } { \mathrm { O } } _ { 3 }$ and AIN).

# Results and Discussion

# Effect of filler fraction and filler shape on ETC of composite

Figures3,4,and5 show the effectof fillershape with SC geometry on ETC for the thermal boundary resistance when the volume fraction is $\rho = 0 . 1 , \ 0 . 3$ and 0.5 and the conductivity of the filler is $\lambda _ { \mathrm { s } 2 } = 5$ ，30，and 170 $\mathrm { W } / ( \mathrm { m } { \cdot } \mathrm { K } )$ . Solid symbols and open symbols indicate values for $\lambda _ { \mathrm { x } }$ and $\lambda _ { \mathrm { y } } ,$ respectively. When the filler particles are isolated or dispersed well at lower faction,ETC strongly depend on the thermal resistance between the two domains.For example,if the thermal resistance is higher (lower Biot number, $\mathrm { B i } < 0 . 1$ ),thermal conduction

a/b=0.25,x 4 a/b=0.25,y a/b=0.50,x 公 a/b=0.50,y a/b=0.75,x 日a/b=0.75,Xy a/b=1.00,x O a/b=1.00,y 0.8 0.4 0.2 0 0.01 1 100 10000 1000000 Biot numb er[-1 (a)p=0.1 a/b=0.25,x a/b=0.25,y a/b=0.50,x A a/b=0.50,y a/b=0.75,x a/b=0.75,Xy a/b=1.00,x a/b=1.00,y 2   
[xu/M] 1.5   
EC 0.5 0 0.01 1 100 10000 1000000 Biot number[-] (b)p=0.3 a/b=0.25,x a/b=0.25，y a/b=0.50，x a/b=0.50,y a/b=0.75,x a/b=0.75,y a/b=1.00x o1 a/b=1.00,y 3   
E 888 日 2 □□ 中 0 0.01 1 100 10000 1000000 Biot numb er[-] (c) p= 0.5

through the interface between resin and isolated filler can be ignored.If the heat transfer behaves like a porous material, then the composite acts as an adiabatic material. As a result, ETC is similar to the conductivity of the resin because the resin is a continuous phase.However,if a medium Biot number is used,which means moderate thermal resistance,then the thermal conduction through theinterface betweenthetwo domainsisimproved.The ETC gradually increases with Biot number,and then levels off.Because thermal conduction through the interface becomes perfect in the case of higher Biot number $\mathrm { \Delta B i } > 1 0 0 0 0 \mathrm { \Omega }$ ，the saturated ETC is proportional to the volume fraction and the conductivity of filler.Therefore, the conductivity of filler becomes more important for improving the thermal conduction of the composite as the Biot number becomes higher.

a/b=0.25,x a/b=0.25,y a/b=0.50，x a/b=0.50，y a/b=0.75,x a/b=0.75,y a/b=1.00x a/b=1.00y 4   
Et 3 2 1 0 0.01 1 100 10000 1000000 Biot numb er[-1 (a)p=0.1 a/b=0.25,x a/b=0.25,y -a/b=0.50,x △a/b=0.50,y Pa/b=0.75,x a/b=0.75,y 1 a/b=1.00x 9 a/b=1.00λy 10 ↑ A A A 8 A 6 4 Z 2 0 0.01 1 100 10000 1000000 Biot number[-] （204 $( \boldsymbol { \mathsf { b } } ) \rho = 0 . 3$ （2 a/b=0.25,x a/b=0.25,y a/b=0.50，x a/b=0.50,y 0 a/b=0.75,x 中 a/b=0.75,y . a/b=1.00,x O a/b=1.00y 16 4 ↑ 888 A   
2/m 白 中 中 中 中 0 0.01 1 100 10000 1000000 Biot numb er[-] $( \mathrm { c } ) \rho = 0 . 5$

When the filler shape is flatter, the anisotropy of the ETC becomes more remarkable.The anisotropy is not particularly high because filler particles are not in contact with neighboring filler particles at ${ \rho } \mathrm { { = } } \ 0 . 1$ . However, as the fraction becomes larger, thermal conduction improves in only they-directionin the caseof flatter filler.When thefraction reaches O.5,filler particles are in contact in y-direction even with nearly spherical filler $( a / c = 0 . 7 5$ ） Accordingly, the anisotropy of the ETC depends on the volume fraction and oblateness of the filler particles. However, the thermal conduction from the pathway in the $\mathbf { x }$ -direction that passes through the solid 1 (resin) phase decreases.For the same fraction,it is easier for flatter filler to produce closed pathways.For example,in the case of SC geometry with $\rho = 0 . 3$ and $a / c = 0 . 2 5$ ,the pathway in the $\mathbf { x }$ -direction through the solid 1 phase is almost blocked by the solid 2(filler) phase.In the case of lower Biot numbers (higher thermal boundary resistance),

a/b=0.25,x a/b=0.25,y a/b=0.50,x △a/b=0.50,y a/b=0.75,x a/b=0.75,y a/b=1.00,x a/b=1.00,λy 20   
ml 16 12 8 4 0 0.01 1 100 10000 1000000 Biot number[-] (a)p=0.1 a/b=0.25,x a/b=0.25,y a/b=0.50,x a/b=0.50,y a/b=0.75,x a/b=0.75,y a/b=1.00x o a/b=1.00,y 60   
[/ 40 50 A 30 A 20 10 0 0.01 1 100 10000 1000000 Biot number[-] （204号 $( \boldsymbol { \mathsf { b } } ) \rho = 0 . 3$ a/b=0.25,x a/b=0.25,y a/b=0.50，x a/b=0.50,y a/b=0.75,x a/b=0.75,y a/b=1.00,x a/b=1.00,y 100   
tr 80 文 □ 60 中 中 中 40 20 0D 0.01 1 100 10000 1000000 Biot number[-] (c)p=0.5

interruption of the pathway by solid 2 acts adiabatically in the $\mathbf { x }$ -direction although the ETC in the y-direction increases slightly due to contact between filler particles Finally, the ETC of composites with flatter filler exhibits anisotropy between the $\mathbf { X - }$ and y-directions when the Biot number is lower than 1O.The anisotropy at lower Biot number strongly depends on the filler shape.However, in the case ofhigher Biot numbers,the thermal resistance through the interface is improved in the $\mathbf { x }$ -direction,and the anisotropy almost disappears due to the perfect thermal conduction.When filler particles are in contact with neighboring particles,the anisotropy increases. This means that the connection network of the filler is important for obtaining higher thermal conduction. In particular. flatter filler exhibits stronger anisotropy at the same volume fraction.ETC in the y-direction for flatter filler at a larger fraction becomes almost constant regardless of Biotnumber. Thermal resistance does not affectETCin y-direction because most of the interface of flatter filler is nearly parallel to the y-direction.Moreover, it becomes easierto establishafillernetworkas thevolume fraction increases.However,composites with nearly spherical filler do not exhibit anisotropy for every Biot number.

A similar tendency is obtained for filler with higher conductivity, although the absolute values are higher. The filler shape,thermal conductivity,volume fraction,and thermal resistance through the interface are therefore essential for correctly estimating ETC.Moreover,if ETC is measured experimentally, quantitative prediction of thermal resistance,which is caused by incomplete contact between resin and filler particles,might become possible.

# Effect of filler configuration on composite ETC

The effect of filler distribution on ETC is analyzed because thermal boundary resistance is important for actual composites with flatter fillers.ETC for different filler fraction and filler shapes is calculated for three configurations (SC,BCC,and FCC) at $\lambda _ { \mathrm { s } 2 } = 3 0$ ，and atBiot number $\mathrm { B i } = 1$ ，100,and 1oooo (low,medium,and perfect thermal conduction through the interface) as shown inFigs.6,7,and 8.In these figures,solid symbols and open symbols indicate results for $\lambda _ { \mathrm { x } }$ and $\lambda _ { \mathrm { y } }$ ,respectively. For smaller $a / c$ ,the anisotropy ofETC becomes larger at around $\rho = \ 0 . 2 \ – 0 . 7$ for each geometry when the Biot number is low(1) and medium(1oo).For example,in the case of low volume fraction and low Biot number, ETC is smaller. When the flatter fillers come into contact with each other, ETC in the y-direction suddenly increases at the volume fraction where a pathway of filler with higher conductivity penetrates through the continuous resin phase.However,ETC in the $\mathbf { x } .$ -direction remains low in the case of low Biot number and flat filler.An increase in the ETC in the $\mathbf { x }$ -direction appears suddenly upon penetration in the $\mathbf { x }$ -direction. Two sudden increases in ETC thus appear in the case of flatter filler. The difference between the two depends on the oblateness of the filler. Moreover, the slope until the penetration points depends on the Biot number. For example,the slopes are quite low and gentle for $\mathrm { B i } = 1$ and $\mathrm { B i } = 1 0 0$ . Finally, the two discontinuities caused by the penetration disappear in the case of perfect thermal conduction.

The effect of filler configuration on ETC is larger when the volume fraction is around O.2 to O.5.Because the higher conductivity solid 2 phase penetrates the lower conductivity solid 1 phase,pathways formed by a netWork of solid 2 phase are essential for increasing the thermal conduction in the composite.For example,ellipsoidal fillers can make contact with neighboring filler particles easily even for the same volume fraction. Contact between filler particles in the FCC and BCC geometries is slightly more difficult than in the SC geometry because the distances between the filler particles are different. The difference in connection level caused by flat

a/b=0.25,x a/b=0.25,y a/b=0.50, △—a/b=0.50,y a/b=0.75,x a/b=0.75,y + a/b=1.00，x 0 a/b=1.00,y 35 30   
2 安 口 5 四 □ 0 COOA A 0 0.2 0.4 0.6 0.8 1 Volume fraction[-l (a) $\mathrm { B i } = 1$ a/b=0.25,x a/b=0.25,y a/b=0.50,x △a/b=0.50,y a/b=0.75,x a/b=0.75,y + a/b=1.00x a/b=1.00,y 35 30 如 20 15 10 □ 5 0 0 0.2 0.4 0.6 0.8 1 Volume fraction[-l (b)Bi=100 a/b=0.25,x a/b=0.25,y a/b=0.50,x △a/b=0.50，y a/b=0.75,x a/b=0.75,y a/b=1.00,x O a/b=1.00y 35   
TTtr 3025 20 15 10 5 0 0 0.2 0.4 0.6 0.8 1 Volume fraction[-l (c)Bi=10000

$$
\lambda _ { \mathrm { s } 2 } = 3 0
$$

ter fillers affects the anisotropy as well because connection becomes more difficult for flatter and horizontal fillers in the vertical direction than in the horizontal direction.

However,in the caseofhigherBiotnumber,alinear relation between the volume fraction and ETC is obtained for each geometry and filler shape.Because thermal conduction through the interface becomes perfect ETC becomes proportional to the volume fraction and conductivity of the two components.Finally, the filler configuration and shape must be taken into account for thermal analysis of composites when the thermal resistance is not perfect.

# Comparison with ETC of porous medium with ellipsoidal pores

In previous study [12],ETC of porous medium with ellipsoidal poreswasanalyzed and the effectsof parameters such as porosity,pore shape,pore distribution,and temperature of the porous medium on the conductivity

a/b=0.25，x a/b=0.25,y a/b=0.50,x △a/b=0.50,y a/b=0.75,x a/b=0.75,y . a/b=1.00，x Oa/b=1.00,y 35 3025 20 15 日 又 10 众 中 X 0 400A 0 0.2 0.4 0.6 0.8 1 Volume fraction[-l (a)Bi=1 a/b=0.25,x 4 a/b=0.25,y a/b=0.50,x △a/b=0.50,y a/b=0.75,x a/b=0.75,y a/b=1.00x Oa/b=1.00,y 35 325 中 中 8 5 ←< 0 8 一 0 0.2 0.4 0.6 0.8 1 Volume fraction[-1 (b)Bi=100 a/b=0.25,x 4 a/b=0.25,y a/b=0.50,x △a/b=0.50，y T a/b=0.75,x 日a/b=0.75,y O a/b=1.00x 0 a/b=1.00y 35 30 25 20 15 10 5 0 0 0.2 0.4 0.6 0.8 1 Volume fraction[-1 (c)）Bi=10000

a/b=0.25，x a/b=0.25,y a/b=0.50,x a/b=0.50,y a/b=0.75,x a/b=0.75,y a/b=1.00x a/b=1.00y 35   
85 四日 5 A G 0+△ 0 0.2 0.4 0.6 0.8 1 Volume fractionf-l (a)Bi=1 a/b=0.25，x a/b=0.25,y a/b=0.50，x a/b=0.50,y + 一 a/b=0.75,x a/b=0.75,y . a/b=1.00,x a/b=1.00,y 35 30   
50 0 0 0.2 0.4 0.6 0.8 1 Volume fraction[-1 (b)Bi=100 a/b=0.25,x a/b=0.25,y + a/b=0.50,x a/b=0.50,y a/b=0.75,x a/b=0.75,y a/b=1.00,x Oa/b=1.00,y 35   
88 5 0 0 0.2 0.4 0.6 0.8 1 Volume fraction[-l (c）Bi=10000

$$
\lambda _ { \mathrm { s } 2 } = 3 0
$$

were studied to clarify the mechanisms in complex pore structures.In the case of composite with fillers, thermal conductivityof dispersed phase(filler) ishigher than that of continuous phase (resin). Accordingly, ETC of composite is improved by thermal conduction through the pathway of dispersed phase.As mentioned above,filler network,which is a connection between neighboring filler is influential to the ETCs of composite.

On the other hand,in the case of porous medium, thermal conductivity of dispersed phase(gas） is lower than that of continuous phase (solid).Even if ellipsoidal pore has contacts with neighboring pores,the pathway of continuous phase of higher conductivity is unchanged.In this case, the ETCs are relatively constant. However, when the pathway for thermal conduction is completely blocked by gaseous phase of lower conductivity， the ETCs drastically decrease.Accordingly, cross-sectional pathway of the solid phase plays more roles than the pore connections.The effect of thermal radiation on the ETCs could be estimated for porous medium,meanwhile thermal radiation effect on the composite is insignificant. It was observed that thermal radiation is dominant at high temperatures and for large pore sizes,and the anisotropy introduced by pore shape could be neglected. Based on the aforementioned, the ETCs of materials with ellipsoidal pores or ellipsoidal fillers showed different behaviors under homogenization method which indicate the microstructure and the conductivity of each phases.

# Conclusions

A homogenization method that is able to consider heat transfer with thermal resistance was applied to thermal analysis of composites with ellipsoidal filler. The effect of microstructural aspects such as filler configuration, shape,and volume fraction on ETC was calculated.First, ETC depends on Biot number,which is related to thermal boundary resistance,with the value drastically increasing at $\mathrm { B i } = 1 0$ to 100o.In the case of lower Biot number, the composite behaves like a porous material. Second, larger anisotropy of ETC arises from flatter fillers and higher thermal resistance because pathways through the different phase with lower conductivity are blocked.Thermal resistance and contact between filler particles are impor tant for heat transfer in the composites.Moreover, quantitative data considered for contact between the fller particles show that the anisotropy of ETC occurs easily when ellipsoidal filler is placed in the SC configuration compared to FCC and BCC configurations.Finally, the proposed three-dimensional method is a useful tool for precisely modeling heat transfer with thermal resistance in composites because it can estimate the microstructure of filler shape and configuration.

# References

[1]W. Zhou,Q.Chen,X. Sui,L.Dong, Z.Wang,Enhanced thermal conductivity and dielectric properties of Al/ $\beta$ -SiCw/PVDF composites, Composites Part A: Applied Science and Manufacturing,71 (2015) 184-191.   
[2]B.L.Zhu,J.Wang,H. Zheng,J.Ma,J.Wu,R.Wu,Investigation of thermal conductivity and dielectric properties of LDPE-matrix composites filled with hybrid filler of hollow glass microspheres and nitride particles, Composites Part B:Engineering,69(2015) 496-506.   
[3]Z.Gao,L, Zhao,.Effect of nano-fillers on the thermal conductivity of epoxy composites with micro-Al2O3 particles,Materials & Design,66(A) (2015) 176-182.   
[4] Y.Yao,X.Zeng,K.Guo,R.Sun,Jb.Xu,The effect of interfacial state on the thermal conductivity of functionalized Al2O3 filled glass fibers reinforced polymer composites,Composites Part A:Applied Science and Manufacturing,69 (2015) 49-55.   
[5]J.Schuster,D.Heider,K.Sharp,M.Glowania,Thermal conductivities of three-dimensionally woven fabric composites,Composites Science and Technology, 68 (2008) 2085-2091.   
[6]EB.Wei, YM. Poon. Effective thermal conductivity of graded nonlinear composites with heat contact resistance. PhysicsLetters A,359 (2006) 685-692.   
[7]R.Kothari, CT. Sun,R. Dinwiddie,H. Wang,Experimental and numerical study of the effective thermal conductivity of nano composites with thermal boundary resistance,International Journal ofHeat andMass Transfer, 66 (2013) 823-829.   
[8]BR. Wang, JT. Liu,ST. Gu, QC. He, Numerical evaluation of the effective conductivities of composites with interfacial weak and strong discontinuities,International Journal of Thermal Sciences,93 (2015) 1-20.   
[9]EB.Wei, JB.Song,JW. Tian,Thermal conductivity of graded spherical composites with contact resistance, PhysicsLettersA,319(2003) 401-405.   
[10]JJ.Gou,H. Zhang,YJ.Dai,S.Li,WQ. Tao,Numerical prediction of effective thermal conductivities of 3D four-directional braided composites,Composite Structures,125 (2015) 499-508.   
[11]W.Leclerc,N.Ferguen,C.Pélegris,E.Bellenger,M. Guessasma,HHaddad,An efficient numerical model for investigating the effects of anisotropy on the effective thermal conductivity of alumina/Al composites,Advances in Engineering Software,77 (2014) 1-12.   
[12]Y. Asakuma,T. Yamamoto,Thermal analysis of porous medium with ellipsoidal pores using a homogenization method,Heat and Mass Transfer,accepted HAMT-D-15- 00053.   
[13]Y. Asakuma, Y. Kanazawa, T. Yamamoto, Thermal radiation analysis of packed bed bya homogenization method, International Journal of Heat and Mass Transfer,73 (2014)93-102.   
[14]A. Matine,N. Boyard, G Legrain, Y. Jarny, P. Cartraud, Transient heat conduction within periodic heterogeneous media:A space-time homogenization approach.International Journal of Thermal Sciences,92 (2015) 217-229.   
[15]I. Sevostianov, G. Mishuris,Effective thermal conductivity of a composite with thermo-sensitive constituents and related problems, International Journal of Engineering Science 80 (2014) 124-135.   
[16]J.Gudmundsson,M.Hammar,M.Kreveld,Higher order Delaunaytriangulations.ComputationalGeometry, Theory and Applications,23 (2002) 85-98.