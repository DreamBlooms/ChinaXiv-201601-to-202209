# Numerical Simulation of Asymmetric Corona with Multi-Streamer Structures

Li Jingqun',Wei Fengsi, and Feng Xueshang Laboratory for Space Weather, Center for Space Science and Applied Research, Chinese Academy of Sciences

Abstract. A new procedure is proposed to generate planar asymmetric coronas with multi-streamer structures,as shown in SOHO/LASCO observations. The initial coronal magnetic field is separated into potential part and non-potential part. We first fit the potential part by using the sum of magnetic multi-poles,whereas the non-potential part is approximated bythe magnetic field induced by some properly fitted current densities.Then the total field is numerically modified in terms ofMaxwell's equations.Based on the initial magnetic fields obtained in such a way,we can further compute various complex asymmetric corona structures by solving MHD equations.In order to verify this procedure,we compute the 2-D coronal structures prior to the December,1996 CME and August,1999 CME events.The numerical result is on the whole in agreement with observations,and hence set proper backgrounds for further studying the propagation of CME in various coronal structures using numerical computations.

# 1．Introduction

The study of the coronal structure is an important topic in space physics and solar physics.It has been shown by observations that in most cases the corona has a variety of asymmetric multi-streamer structures.Since CMEs must pass the low coronal environment before moving into the interplanetary space, the study of coronal structure is fundamentallyimportant, especiallyforquantitatively understanding the changes in space weather [Dryer,1998; Feng and Wet,1999].There have been a great number of numerical works devoted to the study of the steady structure of the corona and CMEs.Pneuman and Kopp [1971] studied the 2-D steady structure of the corona by iteration method. Steinolfson et al [1982] simulated the steady structure of the corona by numerically solving the 2-D MHD initial boundary problem through relaxation method.Based on a symmetric coronal streamer background,Wu and Guo et al. [1997] investigated the formation and evolution of CME observed by LASCO (Large Angle Spectroscopic Coronagraph)，and considered the interaction between flux ropes and a single streamer.So much attention is paid to the symmetric coronal structures,asymmetric multi-current sheet configurations, nevertheless,have frequently been observed in realistic coronal structures.Linker and Mikic et al.[1999] developed a 3-D MHD model of the solar corona applicable to the Whole Sun Month time period, using measurements of the photospheric magnetic field as boundary conditions for their computation,and obtained results in good overall agreement with coronal and interplanetary structures.On the other hand.

since direct and accurate measurements of the coronal magnetic field cannot be made at present, some assumptions have been customarily introduced regarding its properties to make up for the lack of direct information.The measured photospheric field has been used as input to a potential tield-source surface model to compute the coronalor interplanetary magnetic fields [see Linker et al.,1999,for example]. Zhao and Hoecksema have developed many methods[Zhao et al,1993,1994,1999],such as the horizontal current-resource surface (HCSS) model, the horizontal current-current sheet (HCCS) model and the current sheet-source surface (CCSS) model, by respectively including the horizontal current, current sheet and volume current into the generating function $\Phi$ of the magnetic field or by adopting a good synoptic frame of the photospheric field corrected using the unseen surface adjustment to improve the potential field-source surface (PFSS) model.

Due to the lack of measurement of coronal magnetic field, it is a very interesting problem how to construct the coronal structure (including the magnetic field and plasma properties) based on the coronagraph observation. This paper presents a new method to numerically simulate complex asymmetric corona with multi-streamer structures on the basis of the coronagraph observation from SOHO/LASCO.

To verify the method,we apply it to reproduce the asymmetric multi-current sheet coronal structures prior to the December,1996 CME event and August 1999 CME event. The structures obtained by the method are rather stable,and hence can be used as the background to further simulate the propagation and evolution of the CME mentioned above in the corona and the interplanetary space.

The paper is organized as follows.We describe the scenario to generate asymmetric coronal structures with multi-streamer structures in section 2.In section 3,two examples are given to illustrate the method; in section 4,a brief discussion is made about the method.

# 2.Description of the method

Inorder to construct asymmetric corona with multi-streamer structures on the basis of the coronal observations, we proposed a magnetic field fitting-modification method.It consists of the following steps: 1） fitting the initial magnetic field,2) determining the other initial flow parameters,and 3） solving the MHD initial and boundary value problem based on the above initial field and flow parameters(usingthenonreflectingprojective characteristic boundary conditions).Step 1 is the core of the method,which account for its name.

# 2.1Fittingand modification of the initial magnetic field.

When using the time-relaxation method to get realistic steady coronal structure,it is crucial to choose suitable initial magnetic fieldonthebasis of the SOHO/LASCO observations. For this reason we develop the following method to fit and modify magnetic field.

It is well known that the magnetic field can be thought as consisting of two components: the potential part ${ \vec { B } } _ { \imath }$ and the non-potential part $\vec { B } _ { 2 }$ ,they satisfies

$$
\left\{ \begin{array} { l l } { \nabla \bullet { \vec { B } } _ { 1 } = 0 } \\ { \nabla \times { \vec { B } } _ { 1 } = 0 } \end{array} \right.
$$

and

$$
\left\{ \begin{array} { l l } { \nabla \bullet { \vec { B } } _ { 2 } = 0 } \\ { \nabla \times { \vec { B } } _ { 2 } = \mu _ { 0 } { \vec { J } } } \end{array} \right.
$$

separately.

When the corona is in a simple and quiet state,its magnetic field can be taken as a potential field,otherwise,when the plasma interacting with the magnetic field,and the effect of the charge current cannot be ignored, the coronal magnetic field is not potential field at all.Both the potential and non-potential case are taken into account. In the following treatment of the magnetic field,we draw ideas from the theory of incompressible flowin hydrodynamics,and treat the magnetic field astreating velocityin the theoryof incompressible flow, takingadvantage of the analogy between magnetic field and the velocity in incompressible flow in hydrodynamics.

2.1.A．Fitting of $\vec { B } _ { \scriptscriptstyle 1 }$ .Since $\vec { B } _ { \iota }$ satisfies equation (1), it can be represented as

$$
\vec { B } _ { \vert } = \nabla \phi
$$

then it follows

$$
\Delta \phi = 0
$$

that is, $\phi$ satisfies the Laplace's equation.According to partial differential equation theory,in 3-dimension $\mathsf { c a s e } , \phi$ can be expanded as the following sum:

$$
\begin{array} { r } { \displaystyle \phi ^ { \mathrm { ~ } } \left( r \right) = \phi ( \infty ) + \frac { C ^ { ( 0 ) } } { r } + C _ { \imath } ^ { ( 1 ) } \frac { \partial } { \partial x _ { \imath } } ( \frac { 1 } { r } ) } \\ { \displaystyle + C _ { \imath \jmath } ^ { ( 2 ) } \frac { \partial } { \partial x _ { \imath } \partial x _ { \jmath } } ( \frac { 1 } { r } ) + . . . . . . } \end{array}
$$

wheretheright-handsideare successivelydipole, quadrupole...from the third term.

In 2-D case,a similar expansion holds,if replacing $1 / r$ by $\ln { r }$ ：

This suggests that we can fit the magnetic field $\vec { B } _ { \scriptscriptstyle { 1 } }$ by a delicate combination of multi-poles.That is,we place some dipoles,quadrupoles,etc,in appropriate positions,and compute the magnetic field strength of every such multi-poles then take the sum of them as $\vec { B } _ { \scriptscriptstyle 1 }$ ：

2.1.B.Fitting of $\vec { B } _ { 2 }$ .Since $\vec { B } _ { 2 }$ satisfies (2), it can be approxiamted by the following way.

1）Place some currents density $\vec { J } _ { 1 } ( x ) , \vec { J } _ { 2 } ( x ) ,$ 银 $\vec { \boldsymbol { J } } _ { \boldsymbol { k } } ( \boldsymbol { x } )$ in appropriate positions( in the current case,they should be perpendicular to the considered plane), and take their sum

$$
\vec { J } ( x ) = \sum _ { \prime = 1 } ^ { k } \vec { J } _ { \prime } ( x )
$$

2）Use the formula

$$
{ \vec { \mathbf { A } } } ( \mathbf { x } ) = { \frac { \mu _ { 0 } } { 4 \pi } } { \underset { \mathbf { f } } { \int } } { \frac { \mathbf { \vec { J } } ( \mathbf { y } ) \times { \vec { \mathbf { r } } } } { \mathbf { r } ^ { 3 } } } { \mathrm { d } } \mathbf { V }
$$

to get the induced field,and take it as the approximation of $\vec { B } _ { 2 }$ ：

Byproperly choosing the strength and position of every multi-pole and current density,we can construct an initial magnetic field for a given corona. Starting with the initial magnetic field, we wish to further get the observed asymmetric coronal magnetic structure by time-relaxation method.

# 2.2. Modification of $\vec { B } = \vec { B } _ { 1 } + \vec { B } _ { 2 }$

Generallyspeaking,theresultobtainedthrough time-evolution method starting from the above assembled initial magnetic field is not very satisfactory.It needs to be modified in the following way so as to get a better result.

The following relations can be derived from equations(1) and (2)

$$
\frac { \partial } { \partial r } ( r B _ { \theta } ) = \frac { \hat { \sigma } B _ { r } } { \hat { \sigma } \theta } + \mu _ { 0 } r J
$$

$$
\frac { 1 } { r } \frac { \hat { \sigma } ^ { 2 } ( r B _ { o } ) } { \hat { \sigma } \theta ^ { 2 } } + \frac { \hat { \sigma } } { \hat { \partial } r } \Biggl ( r \frac { \hat { \sigma } } { \hat { \partial } r } ( r B _ { o } ) \Biggr ) = 2 r \mu _ { 0 } J + \mu _ { 0 } r ^ { 2 } \frac { \hat { \sigma } J } { \hat { \sigma } r }
$$

$$
\frac { 1 } { r } \frac { \hat { \sigma } ^ { 2 } ( r B _ { r } ) } { \hat { \sigma } \theta ^ { 2 } } + \frac { \hat { \sigma } } { \hat { \sigma } r } \Bigg ( r \frac { \hat { \sigma } } { \hat { \sigma } r } ( r B _ { , } ) \Bigg ) = - \mu _ { 0 } r \frac { \hat { \sigma } J } { \hat { \sigma } \theta }
$$

$$
\oint B _ { r } d s = 0
$$

$$
\oint B _ { \theta } d l = \mu _ { 0 } I
$$

here $B , \boldsymbol { B } _ { \iota }$ ,have the usual meanings,and $I$ represent the cuirent enclosed inside $1 R s .$ 、Equations (1l) and(12) represent the surface integration and the line integration along the inner boundary respectively. The reader should keep in mind the fact that we only consider the 2-D planar flow.

We can use the above five equations to numerically modify the above fitted magnetic field as follows:

Step 1:According to observed pictures,make proper modification on the component $B _ { \theta }$ on the inner boundary so as to better approximate the observation.Usually,this can be successfully done by repeatedly comparing the computational result with the observation. Of course,educated experience is also important.Meanwhile，it should be noted that the modified $B _ { \theta }$ has to satisfy equation (12).

Step2:Discretize equation (9) into difference form,use the $B _ { \theta }$ values obtained in step l as the inner boundary condition, and take the normal derivatives of $B _ { \theta }$ to be zero on the outer boundary.Then solve the difference equations by using the Gauss-Seidel iterative method to get the values of $B _ { \theta }$ in the whole annual region from $1 R s$ to $1 0 R s$

Step 3:Determine the values of $B _ { \prime }$ on the inner boundary by using equations (8) and (11).

Step 4:Proceed as in step 2 to determine the values of $B _ { \prime }$ in the whole computational region from $1 R s$ to $1 0 R s$ by equation (10).

# 2.3.Determination of other initial parameters

Up to now we have described how to construct the initial magnetic field by using our fitting-modification method. Following the same way as in the simulation of axisymmetric coronal streamer,we can determine the initial distribution of other flow field parameters such as the density，velocity [Steinolfson. et al,1982; Zhang and Wei,1993].That is,by solving the 1-D steady flow when the magnetic field is zero, we can obtain the distribution of radial velocity, density,and pressurealong the radial direction,and take themas the initial values of the corresponding varieties.The latitudinal velocity is taken to be zero.

![](images/845afca0195f348148d4f22234eb7703a03ee6d046dcdcd43e2e5cac2d2485a7.jpg)  
Figure 1. a） Observational picture of December.1996 CME event.b) Computed density result at $\mathrm { \ t { = } 1 0 0 . 0 0 0 s }$ represented by brightness

# 2.4.Numerical solution of the MHD equations

Considering the interaction between the magnetic field and the coronal piasma, we apply MacCormack's difference scheme to solve the time-dependent MHD equations,using the above magnetic field as initial field and the other initial parameters. The numerical solution after a sufficiently long time computation is taken as our steady coronal structure. The non-reflection projective characteristic boundary conditions is used as the boundary conditions on the inner boundary and outerboundary[Lt and Wet,2001].

![](images/6184be934e10d00399e266337a262b6728087321f8cab64ec0d51b27538ee96f.jpg)  
Figure 2. a) Initial magnetic field and velocity for calculating the corona prior to the December event: b) Magnetic and velocity at $\scriptstyle \mathbf { t = 5 0 , 0 0 0 s }$ ；c）Magnetic and velocity at $\mathrm { \ t = } 1 0 0 { , } 0 0 0 \mathrm { s }$ ；d) Magnetic and velocityat $\mathrm { \ t = } 1 1 0 { , } 0 0 0 \mathrm { s }$

![](images/8340bde845cbcd9c79775896c0bc892c5032229eda25229615cebb71a4977d2c.jpg)  
Figure 3.a) Observational picture of August, l999 CME event. b） Computed density result at $\mathrm { t } { = } 5 0 . 0 0 0 \mathrm { s }$ represented by brightness

# 3. Simulation of December, 1996 and August, 1999 asymmetric coronal multi-streamer structures

In order to verify the above procedure,we simulate the asymmetric corona prior to the December, 1996and August,l999 CME events. The equations we use to describe the motion of the solar wind are the 2D planar ideal MHD equations taking the gravitation of the sun into account. The computational domain is the entire annualar region from 1Rs to $1 0 R s$ .The computational grid is 75 (radial direction) $\times$ 288(meridional direction). The steps along the radial direction increase as a geometric series,but the steps along the meridional direction are even.The initial temperature on the inner boundary is $1 . 8 \times 1 0 ^ { 6 } K ,$ the maximal magnetic field is about 1.5 Gauss,γis taken as 1.1.

![](images/20418a440534eb8bf3563a3553384e33605af69269b2bbe863ac32383acf27ae.jpg)  
Figure 4.a） Initial magnetic field and velocity for calculating the corona prior to the August event.. b) Velocity and magnetic field at $\mathrm { \hbar t = 5 0 . 0 0 0 s }$

Fig.1.a) shows the December,1996 asymmetric coronal structure observed by SOHO/LASCO.It can be seen that there is a current sheet near the equatorial plane in the east side of the sun,and there are two current sheets in the west side,with one above the equatorial plane and another below. The whole structure is asymmetric.

Fig.l.b） shows the result of density represented by brightness.The different values of brightness describe the changes of $\rho - \rho _ { \circ }$ ,where $\rho$ is the simulation result of density $\rho _ { \circ }$ is the initial density.The brighter part is where the larger difference of the density lies.

Fig.2.a) shows the initial magnetic field obtained by our fitting-modification method and the superposed initial velocity distribution;Fig.2.b) to d) show the evolution of the magnetic field and the velocity.It can be seen that the flow basicallyreachesstableat $\mathbf { t } { = } 1 0 0 { , } 0 0 0 \mathbf { s }$ and the velocity in open field regions is larger than that in closed field regions.The magnetic field result is on the whole in agreement with the inferredobservation obtained by SOHO/LASCO.

Fig.3.a) shows the August, 1999 asymmetric coronal multi-streamer structure observed by SOHO;b) shows the result of density represented by brightness(at $\scriptstyle \mathbf { t = 5 0 } , 0 0 0$ seconds). The location of the streamers approximately agrees with the observed one.

Fig.4.a) shows the initial magnetic field for calculating the corona prior to the August event.

Fig.4.b) shows thevelocityand magnetic field at $\mathfrak { t } { = } 5 0 , 0 0 0 \mathfrak { s }$ Again we can see the basic consistence of magnetic configuration with the SOHO/LASCO observation.

# 4.Discussion and Conclusions

In the previous section,assuming that the December, 1996 CME and August,1999 CME events started from the asymmetric coronal structures as shown in Figure l.a and Figure 3.a respectively,we study both coronal backgrounds byusing the procedure described in section 2. The computational resultsdemonstrate the power ofthe fitting-modification method to simulate complicated coronal structures.More importantly,the method provides a way to numerically get rather complex 2-D coronal magnetic structures. Based on such coronal structures, we can quantitatively investigate the propagation of CME in a more realistic corona-interplanetary space.It should also be noted that the method should be generalized to 3-D cases in order to get better results consistent with observations. Since the procedures described in section 2.1.A and 2.1.B obviously can be applied to 3-D case without any change, we know that there is no essential difficulty in such a generalization.

Acknowledgments. This work was supported by the National NaturalScienceFoundation of China,Grants 49990452, 40074044and 49925412 and National 973 project 2000078405 We thank professor S T.Wu and J.K Chao for their help when writing the paper

# References

Dryer,M，Multi-dimensional MHD simulation of solar-generated disturbances: Space weather forecasting of geomagnetic storms, AIAAJ 36,365-390,1998.   
Feng, X.S，Wei,F．S.，An operable solution approach to hydrodynamic interplanetary shock waves,Solar Physics,184, 385-402,1999.   
Linker,J A,Z Mikic,Z.,and Biesecker,D.A.,Forsyth,R.J., Gibson.S.E,Lazarus,A.J.,Lecinski,A.,Riley,P. Szabo,A., and Thompson,BJ.,Magnetohydrodynamic modeling of the solar corona duringWhole Sun Month,JGR， 104,9809-9830,1999.   
LiJQ.，Wei，F.S，On nonreflecting projective characteristic boundary condition and its application in the numerical simulation ofasymmetric coronal structure,Chinese Science Bulletin, 2001,in press.   
Pneuman,G.W,and Kopp,R.A,Gas-magnetic field interactions in the solar corona,Solar Phys.,18,258-270,1971   
Steinolfson,R S,Suess,S.T.,Wu., S.T., The steady global corona. Astrophys J 255,730-742,1982.   
Suess. ST,Wang,A.H.,Wu, S.T.,Poletto,G,and McComas,D.J, ATwo-fluid, MHD coronal model,J.G.R104, A3,4697-4708,1999   
Wu.ST,Guo,W P.,Andrews,M D,Brueckner,G.E.,Howard, RA,Koomen，MJ.Korendyke.C.M.,Michels,D.J,Moses, JD,Socker,D G,Dere,K P,Lamy,PL,Llebaria,A.,Bout, M V. Schwenn,R,Simnett,G M.,Bedford,D K.,and Eyles, C.J.MHD interpretation of LASCO observations of a coronal mass ejection as a disconnected magnetic structure，Solar Phys.175,719-735,1997.   
Zhang，J H.，Wei，F S.， A time-dependent solutionof transonic.trans-Alfvenic MHD flow in the solarmeridian, Sciences in China,36,83-89,1993.   
Zhao,X P.,and Hoeksema,J.T.,Unique determination of model coronal magnetic fields using photospheric observations,Solar Phys，143,41-48,1993   
Zhao,X.P.,and Hoeksema, J T,Modeling the coronal magnetic field in a polar hole,Space ScienceRev,70,369-372,1994   
Zhao,X.P.Hoeksema,J.T,and Schrrer,P.H.,Changes of the boot-shaped coronal hole boundary during Whole Sun Month near sunspot minimum,JGR，104,No.A5,9735-9751,1999.