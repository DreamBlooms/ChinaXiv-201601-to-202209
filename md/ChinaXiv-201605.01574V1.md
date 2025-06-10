# WHYDOES THE APPARENT MASS OFACORONAL MASS EJECTION INCREASE?

LI FENG1,2, YUMING WANG³,FANG SHEN4, CHENGLONG SHEN, BERND INHESTER², LEI LU1, AND WEIQUN GAN1   
KeyLaboratoryfarkaterdacstroourpleoutaiseatorynseadeyofieces,ang,gu 2 Max-Planck-Institut fur Sonnensystemforschung,Gotingen,lower Saxony, Germany 3CASKeyLaboratoryofGeospaceEnvironmentScholofEarthandSpace Sciences，UniversityofScienceandTchnologyof China Hefei 230026, China; ymwang@ustc.edu.cn 4 State Key Laboratoryof Space Weather,National SpaceScience Center,Chinese Academyof Sciences,Beijing,China Received 2015May 12;accepted 2015 September7;published 2015 October 8

# ABSTRACT

Mass is one of the most fundamental parameters characterizing the dynamics ofa coronal massejection (CME). It has ben found that CME apparent mass measured fromthe brightness enhancement in coronagraphs increases durng its evolution in the corona.However,the physics behind it is not clear.Does the apparent massgain come from the outflow from the dimming regions inthe low corona,or from the pileup of the solar wind plasma around the CME? Here we analyze the mass evolution of six CME events.Based on the coronagraph observations from the Solar Terrestrial Relations Observatory, we find that their masses increased by a factor of1.3-1.7 from 7 to $1 5 R _ { \mathrm { S } }$ ，where the occulting effect is negligible.We thenadopt the“snow-plow”model tocalculate the mass contributionof the piled-up solar wind.The result gives evidence that the solar wind pileup probably makes a non-negligible contribution to the mass increase.In the height range from about 7 to $1 5 R _ { \mathrm { S } }$ ,the ratio of the modeled to the measured massincrease is roughlylargerthan O.55 though theratiosarebelievedtobeoverestimated.It is notclearyet whether the solar wind pileup is a major contributor to the final mass derived fromcoronagraph observations,but it does play an increasingly important role in the mass increase as a CME moves further away from the Sun.

Key words:Sun: corona - Sun: coronal mass ejections(CMEs)- solar wind

# 1.INTRODUCTION

Mass is a major parameter characterizing the dynamics of a coronal mass ejection (CME).However, due to the limitation of observations,we do not know very much about the CME mass, and its evolution from the corona to interplanetary space. CME masses are mostly derived from images of white-light coronagraphs (e.g.，Vourlidas et al. 2OoO)，as a CME can cause an enhanced brightness in white-light images.However, the mass derived from white-light coronagraph images is just an“apparent’mass of a CME. It has two components: one is the mass of plasma really ejected from the corona,the other is the piled-up solar wind mass due to the compression of the solar wind plasma surrounding the CME.It is difficult to separate the two components from imaging data. Therefore, what we often calculate is the apparent mass.A few studies have shown that the apparent mass of a CME increases with time (e.g., Colaninno & Vourlidas 2Oo9; Bein et al. 2013).

The statistical work by Wang et al. (2O11) has shown that the CME brightness is positively correlated with the CME speed.A natural explanation is that a faster CME causes higher compression of ambient solar wind and therefore a brighter signature in coronagraph images.Numerical simulations also revealed that the mass of the high-density shell ahead of an erupted flux rope increases as it propagates away from the Sun but the mass of the dark cavity,where the flux rope is located, remains almost unchanged(Lugaz et al. 2OO5； Riley et al.2OO8).All these studies imply that the piled-up solar wind mass may not be negligible， and may contribute significantly to the aforementioned phenomenon—apparent mass gain of a CME during its propagation.

On the other hand, there is also evidence suggesting that the CME mass gain can be attributed to the continuous outflow from the low corona (e.g.，Howard & Vourlidas 2OO5;Tian et al. 2012; Bein et al. 2013). Bein et al. (2013) investigated the CME mass evolution for a set of 25 events,and found that the apparent mass increased by about $2 \% - 6 \%$ per solar radius based on the COR2 observations taken bySolar Terrestrial Relations Observatory(STEREO)(Howard et al. 20O8；Kaiser et al. 2008).They further found that the mass centroids of these CMEs moved toward the Sun relative to their self-similar expansion in most events.The authors suggested that the reason might be that the rear part of the CME with higher mass might propagate slower than the front part of the CME. They found that the higher mass at the rear was supplied by the outflow from the lower corona.However,in the analysis ofBein etal.(2O13), the fact that materials may fall back to the Sun,which can also cause a backward motion of the CME centroid, was not considered. Thus,the question how much pileup and outflow contribute to the mass increase still remains unsolved.

In this paper, we are going to answer the question why the CME apparent mass increases in a way different from that by Bein et al. (2O13). We try to quantitatively figure out at which height and how significantly the piled-up solar wind mass contributes to the CME apparent mass.In Section 2,we briefly describe the selection of events,their observations,and their three-dimensional (3D） geometric and kinematic properties. How we derive the CME mass and the mass evolution of selected events is presented in Section 3.In Section 4,we analyze the possible source of the CME mass with the help of a solar wind pileup model and MHD numerical simulations.The final section consists of the discussions and conclusions.

# 2.EVENTS

# 2.1.Event Selection

Six CME events (see Table 1）were selected from the halo CME list (http://space.ustc.edu.cn/dreams/fhcmes/） compiled by Shen et al. (2O13a). The criteria to choose these events are:(1） they appeared halo in the Large Angle

Table 1 The Geometric and Kinematic Parameters of Six CME Events   

<html><body><table><tr><td>No.</td><td>Date</td><td></td><td>0（</td><td>Wf()</td><td>We()</td><td>Ω (sr)</td><td>Vavg (km s−1)</td></tr><tr><td>E1</td><td>2010 Feb 12</td><td>-2.5</td><td>7.2</td><td>68</td><td>47</td><td>1.0</td><td>752 ± 31</td></tr><tr><td>E2</td><td>2010 Apr 03</td><td>4.6</td><td>-25.1</td><td>77</td><td>50</td><td>1.2</td><td>824 ± 29</td></tr><tr><td>E3</td><td>2011 Apr 17</td><td>-177.1</td><td>8.9</td><td>72</td><td>52</td><td>1.1</td><td>1312 ± 51</td></tr><tr><td>E4</td><td>2011 Jun 21</td><td>-20.8</td><td>9.5</td><td>70</td><td>70</td><td>1.5</td><td>1006 ± 38</td></tr><tr><td>E5</td><td>2011 Aug 03</td><td>15.4</td><td>16.4</td><td>68</td><td>41</td><td>0.8</td><td>1294 ± 56</td></tr><tr><td>E6</td><td>2012 Feb 23</td><td>67.2</td><td>24.4</td><td>139</td><td>82</td><td>3.5</td><td>445 ± 12</td></tr></table></body></html>

Note. $\phi$ and $\theta$ are the longitude and latitude of the 3D CME propagation direction,respectively. Positive/negative values of $\phi$ mean westward/eastward propagation with respect to the Earth. $W _ { \mathrm { f } } = 2 ( \alpha + \delta )$ and $W _ { e } = 2 \delta$ are the face-on and edge-on angular width,respectively. $\Omega = W _ { \mathrm { f } } W _ { e } = 4 \delta ( \alpha + \delta )$ approximates the solid angle of a CME. $\nu _ { \mathrm { a v g } }$ is the average speedof the CMEfromthe linearfitto theobserved height-time profile.

Spectrometric Coronagraph (LASCO) on board the Solar and Heliospheric Observatory(SOHO) spacecraft.Theywere also observed by COR1 and COR2 coronagraphs on board STEREO andin most cases as almost limb events.Limb CMEs are less occulted by the coronagraph occulter,thus are favorable for mass estimate.(2）There was no contamination from other CMEs in the region where the investigated CME was located. (3） There was no contamination of very bright $\mathrm { H } \alpha$ line emission from prominence material inside the investigated CME in the coronagraph images.Mass estimate of such contaminated CMEs is often misleading if Thomson scattering theory is applied (Mierla et al. 2O11; Carley et al. 2O12). The six CMEs cover a broad range of leading-edge speed from 450 to $1 3 0 0 \mathrm { k m s } ^ { - 1 }$ as indicated in Table 1.

The twin spacecraft STEREO $\mathbf { A } { + } \mathbf { B }$ and SOHO monitor the solar corona from three different angles of view at about1 AU. COR1 and COR2 on board STEREO observe the corona from 1.4 to $4 R _ { \mathrm { { S } } }$ and 2.5 to $1 5 R _ { \mathrm { S } }$ ,respectively (Howard et al. 2008). LASCO C2 and C3 cameras on board $s o H O$ have a field of view (FOV) of $2 { - } 6 R _ { \mathrm { S } }$ ,and $3 . 7 { - } 3 2 ~ R _ { \mathrm { S } }$ ,respectively (Brueckner et al. 1995).

# 2.2.Deprojected CME Geometry and Kinematics

The projection of a CME onto an image may significantly distort its geometric and kinematic parameters.For a better estimate of the mass of a CME and its evolution,we have tried to derive the deprojected 3D geometry and kinematics.Various models/methods have been developed to retrieve realistic parameters based on multi-point imaging data, e.g., the forward modeling (e.g.，Thernisien et al. 2009；Wood et al. 2009), triangulation method (e.g.，Liewer et al. 2Oo9； Temmer etal. 2Oo9)， polarization ratiomethod(e.g.， Moran et al.2010), inverse method (Antunes et al. 2009)，geometric localization (e.g., de Koning et al. 2009; Byrne et al. 2010; Feng et al.2O12). The comparison of various models could be found in, e.g.,Mierla et al. (201O), Thernisien et al. (2011) and Feng et al. (2013a).

Here we use the forward modeling developed by Thernisien et al. (2O09） to derive the 3D geometric and kinematic parameters of the six CME events.In this method,the graduated cylindrical shell (GCS）model is applied,which consists of a tubular section forming the main body of the structure attached to two cones that correspond to the “legs" of the CME.This model has six free parameters: the propagation longitude and latitude ( $\cdot \phi$ and $\theta$ )，aspect ratio $( \kappa )$ ， tiltangle $( \gamma )$ half angle between two legs $( \alpha )$ ,and heliocentric height of the CME leading edge $( h )$ . From the parameters $\alpha$ and $\kappa$ ，we further derived the edge-on angular width (2δ) and face-on angular width $( 2 ( \alpha + \delta ) )$ ，where $\delta = \arcsin ( \kappa )$ is the half angle of the cone,i.e., the CME leg.Note that all the heights mentioned in this work are the radial distance measured from the solar center. These six parameters were tuned to obtain a best match between the modeled flux rope and the observed CME from different viewpoints.More details of this model and its application to CMEs could be found in,e.g.，Thernisien et al. (2009,2011) and Gui et al. (2011). For the time sequence of images of each CME,we obtained a set of parameters at each time.For simplicity，the free parameters are set to be constants by trial and error,except the height $h$ which is a function of time.

As a demonstration,Figure 1 shows the results for the event on 201O April 3.The upper panels are the images taken by COR B,C2 and COR A,respectively,in which a pre-event image has been subtracted to remove the background and make the CME structure more pronounced. To get a picture of the CME as complete as possible，we incorporated COR1 and COR2 observations.The aforementioned procedure has been applied to all the other five CME events as well. The lower panels are the same as the upper panels except that the green meshes are superimposed to show the best-fit flux rope.It has to be pointed out that for the GCS reconstruction,we did not include in the fiting process the shock-sheath region when visible.By repeatedly applying the GCS model to the time sequence of the images of the CME,the evolution of the height of the leading edge of this CME can be obtained andis shown in Figure 2. The uncertainty in the height is indicated by the error bars.It has two sources; one is the ${ \sim } 0 . 3 \ : R _ { \mathrm { S } }$ uncertainty in the definition of the CME leading front in the white-light images (e.g.,Bein et al. 2013),and the other comes from the forward fittng process.We assumed that the uncertainty is about $5 \%$ of the height at each time instance.At the height of $2 0 ~ R _ { \mathrm { S } }$ ，it produces an uncertainty of $1 ~ R _ { \mathrm { S } }$ which is close to the maximal uncertainty in the sensitivity analysis in Thernisien et al.(2OO9).The height-time data points were further fitted by a linear function to estimate the average speed of the CME.

Table 1 lists the geometric and kinematic parameters of our six events,i.e.，longitude and latitude of the propagation direction ( $\cdot \phi$ and $\theta _ { . }$ ),face-on and edge-on angularwidth ( $W _ { \mathrm { f } }$ and $W _ { e } )$ ，CME solid angle $( \Omega )$ ，and average speed $( \nu _ { \mathrm { a v g } } )$ .The longitude and the latitude are in a heliographic coordinate system with Earth sitting at zero longitude.Positive/negative longitude represents a CME propagating westwards/eastwards. The solid angle spanned by a CME is approximated by the multiplication of the face-on and edge-on angular width. The leading-edge speeds of the CME events vary from about 450 to $1 3 0 0 \mathrm { \bar { k m s } ^ { - 1 } }$ ， showing good representativeness.

![](images/4241a296cf3422be9cb87d844a3113532723fa82b0b26268cceb38da9b63664a.jpg)  
Figure1.Uerpaels:theCMEobseedbySTEREOCORlandCORandbySOH/ASCOCo201April3.NotehatCORandCORiagsare incoporatedtoefossatodeedady green meshes are superposed.

![](images/b62e9e74037c99de70700682640bdef7776bf18f774a343a39c6f72c3ea1b95e.jpg)  
Figure 2.Deprojected height as a function of time for the CME event on 2010 April 3.The asterisks are the measurements and the black solid line is a linear fit.The average speed derived from the linear fit is marked in the upper part. The error bars indicate the $5 \%$ uncertainty of the deprojected heights.

# 3.EVOLUTIONOFCMEAPPARENTMASS

# 3.1.MassEstimateMethod

Mass calculations based on white-light coronagraph images are usually based on the Thomson scattering theory (Minnaert 1930; van de Hulst 1950; Billings 1966; Howard & Tappin 2Oo9).The major non-Thomson scattered contributions like stray light and dust scatter are removed by subtracting a pre-event background image. The remaining image brightness then should show the CME density distribution produced by Thomson scattering alone.For the total brightness in a given image pixel,the details of this scattering process can be described by

$$
\begin{array} { c } { { b = b _ { \odot } \displaystyle \frac { \pi \sigma _ { e } } { 2 } \int _ { \mathrm { L o s } } F \left( r , \chi , u \right) N _ { e } ( r ) d \ell , } } \\ { { F ( r , \chi , u ) = 2 \displaystyle \frac { ( 1 - u ) C ( r ) + u D ( r ) } { 1 - u / 3 } } } \\ { { - \displaystyle \frac { ( 1 - u ) A ( r ) + u B ( r ) } { 1 - u / 3 } \sin ^ { 2 } \chi } } \end{array}
$$

where $b _ { \odot }$ is the physical mean solar brightness(MSB) that is used asa unit of the pixel value in calibrated COR1 and COR2 observations, $F ( r , \chi , u )$ is a function of three variables $r , \chi .$ and $u . \ r$ is the distance of the scattering location to the solar center, $\chi$ is the scattering angle between the radial vector from the solar center to the scattering electron and a position vector from the electron toward the observer.u accounts for the solar disk limb darkening，and we used the value of O.56 for $u$ in the visible white-light spectral range. A, $B$ ， $C$ and $D$ are known functions of $r$ ： $\sigma _ { e }$ is the differential Thomson scattering cross section, and has a value of $7 . 9 5 \times 1 0 ^ { - 2 6 } \mathrm { c m } ^ { 2 } \mathrm { s r } ^ { - 1 }$

In Equation (1)，particular attention should be paid to the scattering angle $\chi$ . In this work,the scattering angles were computed under the assumption that a CME is concentrated in the plane defined by the CME propagation direction and the rotationalaxisof the Sunasin Colaninno&Vourlidas(2009) and Carley et al. (2O12). And the CME propagation direction was derived in Section 2.2 using GCS forward modeling method.Under such all-in-propagation-plane assumption of a CME,we can calculate the column density $\int _ { \mathrm { L O S } } { N _ { e } \ : \dot { d l } }$ for any LOS with Equation (1). Assuming a composition of $90 \%$ H and $10 \%$ He(Vourlidas et al.2OOO),the mass in each pixel of a coronagraph image can be derived by multiplying the column density with the pixel area measured at a distance of about 1 AU from the observer.

![](images/46e6b7ed016010ef428cdcec33b34e969816c57ff59626098baa5422f6f2784e.jpg)  
Figure3assesateaspil shown on the right side.

In our practical procedure,we first defined a sector that contains the whole CME.In Figure 3,the mass in each pixel within the sectors in COR A and CORB is presented for the CME occurred on 2O1O April 3.And we integrated the mass over the entire sector and obtained two mass values from COR A and COR B data, respectively.It should be noted that as we subtracted a pre-event background from the image of interest, the brightness in the non-CME region is supposed to be roughlyat noise level.Thus,although the sector is larger than the region that the CME actually occupies,the calculated values of the apparent mass should be acceptable.Due to the different perspectives of COR A and B,the two values are slightly different.In Figure 4 we show the mass evolution with time.The mass evolution derived from COR A observations is delineatedby thered solidline,and from CORBobservations bythe red dashed line.The average of the mass derived from COR A and B observations is delineated by the green solid line.We found that thedifference between the mass derived from COR A and B was about $1 0 \pm 4 \%$ .Some other curves and associated error bars in Figure 4 will be explained in Section 3.2. The evolution of the averaged mass derived from CORA and B data forall six eventsis shown in Figure 5.The mass uncertainties will also be described in Section 3.2.

# 3.2.Mass Uncertainty Analyses

Vourlidas et al.(2O1O) has shown that the instrumentally photometric uncertainty is quite small,and the subtraction of a pre-event image introduces insignificant errors,if the pre-event image is selected carefully. Similar to Feng et al.(2O15),we mainly considered two sources of error in the mass estimate. One is the LOS distribution of the CME mass in Equation (1), especially the longitudinal propagation angle $\phi$ .The other source is our somewhat arbitrary selection of the CME sector. To estimate the uncertainties from these two sources,we varied $\phi$ within $\phi \pm 5 ^ { \circ }$ at seven values and repeated the CME sector selection process independently for eight times.A total of 15 measurements were made from COR A and B observations, respectively.Theyareshownbyblacksolidandblackdashed lines in Figure 4.Correspondingly，the red solid and dashed lines are the averaged values over 15 measurements.For our analyses of the mass evolution of a CME event,we adopted the green curve.Fifteen measurements from COR A and 15 measurements from COR B yield 15 averaged mass over A and

![](images/d608ee04f750982ef6256edb01e440d2b4d7b28315c392309595158e018fd3e4.jpg)  
Figure4.Mass evolution with time for the CME on $2 0 1 0 { \mathrm { ~ A p r i l ~ } } 3$ .The thin black solid lines are the mass derived from COR A total brightness images with different selections of CME sectors and varing propagational longitudes within $\phi \pm 5 ^ { \circ }$ .A total of 15 independent mass measurements were made for the error estimate.The mass along the thin black dashed lines are derived in a similar way but from COR B observations.The mean mass evolution derived from CORA and CORB are marked by solid and dashed lines in red,respectively. Fifteen measurements from COR A and 15 measurements from COR B yield 15 averaged mass over A and B.The green line and associated error bars are the mean and $3 \sigma$ values of the 15 averaged mass measurements.

![](images/99167f251cd75ef8853b67d7c7356305cc1e487dd429e11893893188efd82169.jpg)  
Figure 5. Mass evolution of alsix events. The black error bars are the $3 \sigma$ of all te 15 mass measurements with diferent sector regions and different propagatiol angles.Therederrorbarsarethe $3 \sigma$ of eightmassmeasurementsonlywithdiferent sectorregions.For mostcases,majorerrorcomes fromthe selectionof the CMl sector.While forthe CMEon2O12February 23,the majoreror comes fromthe uncertaintyof thepropagation angle.

![](images/28f4a52214984813d23a4827afd494897f71a2a8f7b5aeccba8860f15cb1214c.jpg)  
Figure 6.Dependence of the function $F ( r , \chi , u )$ on the scattering angle $\chi$ at three impact distances $R = 2$ ，4, $1 0 ~ R _ { \mathrm { S } } { \mathrm { , } }$ .For CORobservations,the impact distance is the projected distance of $r$ from the scattering location to the solar center onto the POS.The brightness is normalized by its maximal value at the POS $\mathit { \Delta } ^ { \prime } F ( r , \chi = 9 0 ^ { \circ } , u )$ ).The vertical dotted line marks the position of $\chi = 9 0 ^ { \circ }$

B. The green line and associated error bars are the mean and $3 \sigma$ values of the 15 averaged mass measurements.

Figure 4 presents an example of the mass evolution and error analyses.In Figure5,the mass evolution and associated error bars of all six events are shown.The black error bars are the $3 \sigma$ of all 15 mass measurements with different sectors and propagation longitudes,while the red error bars are the $3 \sigma$ of the mass measurements only with different sector regions.In most cases the major uncertainty comes from the selection of the CME sector.However,for the CME observed on 2012 February 23, the major uncertainty originates from the error of the propagation longitude.

To explain the results of uncertainty above,we include in Figure 6 the dependence of the function $F ( r , \ \chi , \ u )$ on the scattering angle $\chi$ at three impact distances of 2,4,and $1 0 ~ R _ { \mathrm { S } }$ The ordinate is $F ( r , \ \chi , u )$ normalized by its maximum at the POS $\chi = 9 0 ^ { \circ }$ .For COR observations,the impact distance is the projected distance of $r$ from the scattering location to the solar center onto the POS.As revealed by Figure 6,when $\chi$ deviates from $9 0 ^ { \circ }$ within about $3 0 ^ { \circ }$ $F ( r , \chi , u )$ only changes slightly and forms a plateau around $\chi = 9 0 ^ { \circ }$ . This phenomenon has also beenfoundbyHoward&DeForest(2012)where theytermed it “Thomson plateau” for the heliospheric HI observations and Colaninno & Vourlidas (2Oo9).Therefore,a small change in propagation longitude $\phi \pm 5 ^ { \circ }$ ，which causes a small change of $\chi \pm 5 ^ { \circ }$ ，does not effect $F ( r , \ \chi , \ u )$ much within the $3 0 ^ { \circ } .$ deviation range.Subsequently,the column density and mass for a given pixel derived from Equation（1） does not change much when $\chi$ deviates from $9 0 ^ { \circ }$ within about $3 0 ^ { \circ }$ .This is the case for the first five CME events.Therefore,the uncertainty of the mass for these events mainly comes from the selection of the CME sector rather than the propagation longitude.

In the case of the CME occurred on 2012 February 23, the propagation direction deviated from the POS as seen by STEREO A by about $5 0 ^ { \circ }$ ，and from the POS as seen by STEREOBbyabout $9 0 ^ { \circ }$ . As the CME appeared in the FOV of COR B as a full halo,the corresponding mass calculation subjects to a large error.Therefore,we onlyused COR Adata for mass analyses.When we derived the mass from COR A data,a small change in $\chi$ yielded a large change in mass.It is because the slope of $F ( r , \ \chi , u )$ at $\chi \approx 1 4 0 ^ { \circ }$ is quite steep in Figure 6,a small change of $\chi \pm 5 ^ { \circ }$ makes a large change in $F ( r ,$ $\chi , u )$ ,hence in column density and mass.That is why the major uncertainty of this event comes from the uncertainty of the propagation longitude.

Note that our all-in-propagation-plane assumption yields an infinitesimal angular width for a CME.Mass can be underestimated under such an assumption according to Vourlidas et al.(2OoO).The authors derived the ratio of the mass estimate under the infinitesimal-angular-width assumption to the mass under a finite-angular-width assumption as a function of the angular width of a CME. As the angular width usually keeps nearly constant in time in the COR FOV,the under-estimate ratio should also keep constant.Therefore, the mass change rate $d m / d t$ isnot effected by the infinitesimal-angular-width assumption.

# 3.3.Treatment of the Occulting Effect

Figure 5 clearly shows that the mass evolution has an increasing trend.Bein et al.(2O13) have demonstrated that one of the major causes of such an increase is the entering of the CME ejecta into the COR FOV from behind the occulter, which we call occulting effect.They then showed that the apparent mass evolution could be fitted by the following function

$$
m ( h ) = m _ { 0 } \bigg [ 1 - \bigg ( \frac { h _ { \mathrm { o c c } } } { h } \bigg ) ^ { 3 } \bigg ] + \Delta m \big ( h - h _ { \mathrm { o c c } } \big ) ,
$$

where the parameter $h _ { \mathrm { o c c } }$ is the height of the outer edge of an effective occulter, $m _ { 0 }$ is a modeled initial apparent mass of a CME,and $\Delta m$ is an additional mass increment per unit height. The first term on the right-hand side of Equation (2) represents the increase of visible mass from a homogeneous cone-shaped and self-similarly expanding CME.It describes how the visible mass of a CME with a constant mass $m _ { 0 }$ evolves，when entering the FOV of COR due to its expansion. The increase of the visible mass above the occulter is merely a geometric effect. The second term is an empirical correction to this simplified model evolution,as the CME mass could increase due to physical reasons,e.g., mass outflow from a dimming region, or solar wind pileup.In the model ofBein etal.(2O13), the actual physical mass increase of a CME can be approximated by $m ( h ) = m _ { 0 } + \Delta m ( h - h _ { \mathrm { o c c } } )$

In Figure 7, the black discrete data points are the calculated massas a function of deprojected height with the error bars in horizontal and vertical directions.Taking these error bars into account,we fitted Equation(2）to the mass-height measurements of each CME event. The best-fit parameters for each CME event are written in the bottom right,and for $m _ { 0 }$ and $\Delta m$ the mean $\pm \sigma$ are in logarithmic scale. In each panel the fitting results are shownby the black solid line,and the black dashed line is the mass variation $m _ { 0 } + \Delta m ( h - h _ { \mathrm { o c c } } )$ with the occulting effect removed.The vertical line marks the height from which the occulting effect starts to be negligible.It is defined as the height from which the measured mass can reach above $9 7 \%$ of the dashed line. It is found that the occulting effect could be ignored once the CME reached about $7 - 8 ~ R _ { \mathrm { S } }$ We denote this height as $h _ { 1 }$ ,the corresponding mass at $h _ { 1 }$ is $m _ { 1 }$ $m _ { 1 }$ and $h _ { 1 }$ forall six CME events are listed in Table 2.The other two mass quantities that are also included in Table 2 are $m _ { 0 }$ below $h _ { \mathrm { o c c } }$ ，and the final apparent mass $m _ { 2 }$ before a CME leaves COR FOV at $h _ { 2 }$

![](images/fe75e0f8a66242bc319b31da754fc2dc5d14a30e42ecc74a0ce54af6457db649.jpg)  
Figr7ast afteremovingteocultigefectissowythebackdshdlin.ebestftparametesemarkeditebottmightineachpael.For $m _ { 0 }$ and $\Delta m$ ，the mean $\pm \sigma$ is written in logarithmic scale.The vertical dotted line marks the height $h _ { 1 }$ where the occulting effect starts to be negligible.The mass evolution due to the solar wind pileup above $h _ { 1 }$ isshownyareddashedineinachpanel.Theuncertatiesindicatedbythsadowegioinorangearedriedudertheassumptiothat $n _ { \mathrm { s w } }$ and $\nu _ { \mathrm { s w } }$ vary in the range from $80 \%$ to $120 \%$ of the simulated values.

Note that our purpose of adopting this model is only to obtain the height where the occulting effect starts to be negligible.We did not use this simplified model for further analyses of mass evolution. The measured mass evolution may deviate from the linear increase assumption in Equation (2). Actually,in Figure 7, for most events,when the CME starts to

Table 2 Derived Parameters of CME Mass at Different Heights,Solar Wind Parameters,and its Mass Contribution   

<html><body><table><tr><td>No.</td><td>mo log10(g)</td><td>hocc (Rs)</td><td>m1 log1o(g)</td><td>h1 (Rs)</td><td>m2 log10(g)</td><td>h (Rs)</td><td>nsw (cm-3)</td><td>Vsw (km s-1)</td><td>ms log1o(g)</td><td>f</td></tr><tr><td>E1</td><td>15.17</td><td>2.83</td><td>15.27</td><td>7.74</td><td>15.37</td><td>14.2</td><td>869</td><td>263</td><td>15.09</td><td><2.55</td></tr><tr><td>E2</td><td>15.38</td><td>2.34</td><td>15.48</td><td>7.76</td><td>15.60</td><td>14.3</td><td>657</td><td>376</td><td>15.01</td><td><1.06</td></tr><tr><td>E3</td><td>15.35</td><td>1.82</td><td>15.63</td><td>7.01</td><td>15.86</td><td>15.7</td><td>824</td><td>243</td><td>15.32</td><td><0.70</td></tr><tr><td>E4</td><td>15.45</td><td>2.69</td><td>15.62</td><td>7.97</td><td>15.78</td><td>15.8</td><td>696</td><td>355</td><td>15.20</td><td><0.85</td></tr><tr><td>E5</td><td>15.42</td><td>2.62</td><td>15.68</td><td>8.46</td><td>15.85</td><td>15.6</td><td>878</td><td>226</td><td>15.15</td><td><0.62</td></tr><tr><td>E6</td><td>15.65</td><td>2.79</td><td>15.83</td><td>7.51</td><td>16.01</td><td>15.3</td><td>610</td><td>338</td><td>15.28</td><td><0.55</td></tr></table></body></html>

Note. $m _ { 0 }$ is the modeled initial apparent mass of a CME below the effective occulter height $h _ { \mathrm { o c c } }$ $m _ { 1 }$ is the apparent mass at the height $h _ { 1 }$ where the occulting effect   
begins to be negligible. $m _ { 2 }$ is the final apparent mass before a CME leaves CORFOV,and $h _ { 2 }$ is the corresponding height. $n _ { \mathrm { s w } }$ and $\nu _ { \mathrm { s w } }$ are the ambient solar wind   
density and speed at $h = 2 0 R _ { \mathrm { S } }$ $m _ { s }$ is the solar wind mass piled up around the CME from $h _ { 1 }$ 0 $\begin{array} { r } { h _ { 2 } . \ f _ { s } = \frac { m _ { s } } { m _ { 2 } - m _ { 1 } } } \end{array}$ measures the contribution of the solar wind pileup to 1   
the apparent mass increase in the height range from $h _ { 1 }$ to $h _ { 2 }$

leave the COR FOV,the measured mass is lower than this linear-model prediction.

# 4.SOURCESOFCMEAPPARENTMASSGAIN

As mentioned before, the CME apparent mass might consist a significant contribution from ambient compressed solar wind plasma.In some appropriate circumstances,shock might form around a CME moving faster than the fast magnetoacoustic wave.For events E3，E5,in COR images we saw deflected streamers which were not adjacent to the CME,and left a very diffusive space between the deflected streamer and the CME.It might be the signature of a shock(Vourlidas et al. 2003; Ontiveros & Vourlidas 20o9).It is almost impossible to separate the brightness contribution of the shock from that of the CME.Although solar wind pileup and compression due to a MHD shock are different physical processes,as the observed shocks were far fainter than the CME,we did not remove these possible shocks from our mass analyses and treated them as an extreme case of compression.

To quantify the piled-up mass of the solar wind plasma surrounding the CME,a highly ideal model,called the“snow plow”model, is applied.In this model, a CME accretes mass as it propagates and its momentum is changed through the interaction with the ambient solar wind. The mass change per unit time is described by (see also in Tappin 2006)

$$
\frac { d m } { d t } = \rho _ { \mathrm { s w } } A \ \big | \nu _ { \mathrm { s w } } - \nu \big | ,
$$

where $m , \nu$ and $A$ are the mass,speed and the cross-sectional area of a CME,respectively,and $\nu _ { \mathrm { s w } }$ and $\rho _ { \mathrm { s w } }$ are the ambient solar wind speed and density,respectively. The value of $A$ is approximated by the solid angle $\Omega$ in Table 1 times $h ^ { 2 }$ i.e., $A = 4 \delta ( \alpha + \delta ) h ^ { 2 } $ .The derivation of the above equation could be found in the Appendix.It should be noted that the equation assumes that the entire piled-up plasma moves together with the CME.Although this assumption may not be true,it is still worth investigating if this model can represent the mass gain during the CME propagation. Actually the “snow plow” equation gives the maximal amount of mass that the solar wind can contribute to CME mass.

# 4.1.Parameters of Background Solar Wind

The“snow plow” model requires the solar wind parameters. Thus we use 3D MHD simulations to obtain the undisturbed solar wind parameters along the CME path from 2.5 to $2 0 ~ R _ { \mathrm { S } }$ The solar wind density and speed at different heights are calculated as the average over a spherical sector of ${ { 6 0 } ^ { \circ } }$ which is centered at the 3D propagation direction of a CME.The numerical scheme in the 3D MHD simulations is a total variation diminishing(TVD） scheme in a Sun-centered sphericalsystem(Fenget al.2003， 2005；Shen et al.2007,2009). For all six events,the synoptic maps of longitudinal magnetic field over a Carrington rotation from Wilcox Solar Observatory are used as input to the code for reality. The details of how to get a steady background solar wind could be found in our previous works (e.g.，Shen et al. 2013b; Wang et al. 2014).

The averaged solar wind density and speed against height over the spherical sectors are presented in Figures 8 and 9, respectively.Forall six events,the variation of density follows about $h ^ { - 6 }$ to ${ h ^ { - 4 } }$ below $7 { - } 8 R _ { \mathrm { S } }$ ,and follows $\boldsymbol { h } ^ { - 2 }$ above $7 { - } 8 R _ { \mathrm { S } }$ Itis also the height where the occulter effect starts to be negligible.The solar wind speeds have a rapid increase at lower heights and thena slower increase at largerheights.The speeds have a similar trend of evolution for different Carrington rotations,but reach different values at $2 0 ~ R _ { \mathrm { S } }$ which range from about 220 to $4 6 0 \mathrm { k m s } ^ { - 1 }$ . The solar wind parameters at $2 0 ~ R _ { \mathrm { S } }$ have been listed in Table 2 for reference.We also plot in each panel the speed of the CME derived from a quadratic fit to the height-time diagram. The scale of the solar wind speed is marked on the left $Y$ axis,and the scale of the CME speed is marked on the right $Y$ axis.For all events,we find that $\nu _ { \mathrm { c m e } } \mathrm { ~ - ~ } \nu _ { \mathrm { s w } }$ decreases with height.

# 4.2.How Much Mass Can Solar Wind Pileup Contribute?

The calculation of the mass that the solar wind pileup can contribute is straightforward, as all the parameters $m , \nu , A$ $\rho _ { \mathrm { s w } }$ and $\nu _ { \mathrm { s w } }$ can be obtained from either CME observations or MHD numerical simulations.The CME speed $\nu$ was estimated froma quadratic fit to the height-time plot,as it provides a better result than the linear fit.We started the mass pileup from $m _ { 1 }$ at $h _ { 1 }$ ,below which we assumed that the mass increase is due to the geometric occulting effect and the mass supply from lower corona.If the mass increase above $h _ { 1 }$ wassolelybecause of the solar wind pileup,we would obtain the mass evolution indicated by the red line in each panel of Figure 7.The shadow region in orange is obtained by assuming that the solar wind density and velocity have an uncertainty of $20 \%$ ：

It is found that, for most events (E3 through E6),the solar wind pileup mass is not sufficient to interpret the measured mass increase from COR observations represented by black symbols， suggesting that apparent mass increase isalso contributed by the outflow from the low corona. For the event E1,the solar wind pileup mass has a higher value than the measured ones above $h _ { 1 }$ in the late-phase evolution in the COR FOV,while for the event E2, it is more or less consistent with the measured mass.Note that the“snow plow” model gives an upper limit of the mass estimate.This model assumes that the solar wind plasma colliding with the CME will all be attached to the CME.However,this is an ideal case. Some solar wind plasma may not be attached,and just flow around the CME and eventually become the ambient background.Therefore，the actual mass increase due to the solar wind pileup may drop below the red lines.

![](images/3dd00d0962c93e9be9f4bf121a6960e3d197a1d2086b7567018ff32ca432d2e4.jpg)  
Figure8.SolarwindumberdsityagainstheightdrivedroMDsmulatio.eumberdesityisteaverageoftdesityovcoeof ${ 6 0 } ^ { \circ }$ centered at the CME propagation direction.Three dashed lines indicate the variation of density following ${ h ^ { - 2 } , h ^ { - \tilde { 4 } } }$ ,and ${ h ^ { - 6 } }$ ,respectively,from upper to bottom. The vertical dotted lines mark the height at $7 . 5 ~ R _ { \mathrm { S } }$

![](images/fb64c014c609aa1687ff1b12dc2abd3b373570fcc52eab8b274f4e3a21dd261f.jpg)  
igure9.Soldlines:thesolawinddialspedgaisthightderivedfroMDimulatiosichis teaverageofthespdoeroef $6 0 ^ { \circ }$ centered at the ME propagation direction. Plus signs: the CME speed.

Although the solar wind pileup mass may be overestimated, the results still imply that the solar wind pileup probably makes a significant contribution to the apparent mass increase observed by the coronagraphs.By comparing the piled-up mass $m _ { s }$ from $h _ { 1 }$ to $h _ { 2 }$ with the total mass gain $m _ { 2 } \mathrm { ~ - ~ } m _ { 1 }$ during the same period,we find that the piled-up mass occupies more than half of the total mass gain as listed in the column for $f _ { s }$ in Table 2,or $m _ { s }$ is at least $1 9 \%$ of the final mass $m _ { 2 }$ before the CMEs leave the COR FOV.Since the piled-up mass are overestimated and our infinitesimal-angular-width assumptionmaymake the measured massunderestimated, the ratios of the piled-up mass to the total mass gain given above are obviously overestimated.However，even if we consider a $100 \%$ overestimate,the ratio of the piled-up mass to the total mass gain is larger than $2 5 \%$ in the height range from $h _ { 1 }$ to $h _ { 2 }$ That is to say,although the pileup is not sufficient to explain the observed mass increase,its contribution is non-negligible Due to the overestimation,it is not clear whether the pileup could make a major contribution to the measured mass increase.

Besides,from Figure 7,we can find that the slopes of massevolutiondm/dh ofthemeasured massand modeled pileup mass gradually decrease with height. When the CME was about to leave the COR FOV, the two slopes are nearly the same for most of the events except the first one. It indicates that solar wind pileup makes a more important contribution to the mass increase at larger distances from the Sun.

# 5.CONCLUSIONS ANDDISCUSSIONS

Based on the brightness enhancement in coronagraph images,we have followed the mass evolution of six CMEs. The deprojected speed of the investigated CMEs covers from 450 to $\mathrm { i } 3 0 0 \mathrm { k m } \mathrm { \dot { s } } ^ { - 1 }$ ．All of these CMEs with different kinematics have an increasing trend in their mass evolution even when the occulting effect is removed. The long-lasting accumulation of CME mass in coronagraph FOV implies that the initial kinetic energy in the CME source region is smaller than the energy estimate using the final asymptotic mass (Carley et al. 2012; Feng et al. 2013b).

Physically, there may be two sources of CME mass gain in the corona: the solar wind mass piled up around the CMEs and the mass supply by the outflow from the dimming regions in the low corona(Aschwanden et al. 2O09; Jin et al. 2OO9; Tian et al.2O12).We calculated the mass contribution of the solar wind pileup from the height beyond which the occulting effect is negligible.Itis found that solar wind pileup may make a non-negligible contribution to the apparent mass increase observedby coronagraphs.Forall of the events,the solarwind piled-up mass might occupy more than half of the total mass gain during the same period from 7 or $8 ~ R _ { \mathrm { S } }$ to the edge of the FOV of COR2.It has to be pointed out that those ratios represent upper limits of the pileup contribution.However, even if we consider a $100 \%$ overestimation,the ratio of the pileup mass to the total mass gain could be larger than one-fourth in the height range from 7 to $1 5 ~ R _ { \mathrm { S } }$ .Wealso find that the contribution from the solar wind pileup becomes increasingly significant asa CME propagates to larger distances from the Sun.In short,Our work reveals that the solarwind pileup is not sufficient to explain the measured mass increase in the COR FOV.However, its contribution is nonnegligible.Due to the overestimation,it is not clear yet whether the pileup could make a major contribution to the measured mass increase.

Whether the solar wind pileup is a major contributor to the final apparent mass in the COR FOV is not clear either.If we assume that the mass below 7 or $8 ~ R _ { \mathrm { S } }$ came from the mass outflow from the dimming region, the ratio of $m _ { s } / m _ { 2 }$ reveals that the solar wind pileup comprises less than half of the final mass for all events.In this case,it may not be a dominant contributor to the CME apparent mass in the COR FOV. Whether this assumption is valid or not requires further investigation.Future work involving the mass estimate from the dimming regions using SDO/AIA multi-wavelength data will be pursued. If the solar wind pileup could also contribute to the mass below about $7 R _ { \mathrm { { S } } }$ ,for some of the CMEs,the pileup may be a dominant contributor.

Both the piled-up mass derived from the“snow-plow”model and the“virtual mass” introduced in Cargill (2OO4) are related to the solar wind mass density.However, they are theoretically and observationally different.From a hydrodynamic point of view, the“virtual mass” is the“added mass” of an accelerating body moving in a fluid,and is required to obtain the correct accelerating force in the momentum equation.The “virtual mass”in Cargill (2OO4) was derived under the assumption of an incompressible fluid,which means that the density in the surrounding solar wind does not change over time.The total brightness observed with a coronagraph is proportional to the density,as there is no density change caused by the added mass，we will not be able to detect it from base-difference images. On the other hand, the piled-up mass in the “snowplow”model is a compressional effect,and the resulting density enhancement could in principle be detected in the basedifference images.Furthermore,pileup occurs even when a CME is moving steadily without any acceleration.

DeForest et al.(2013) tracked the CME mass from STEREO/COR2FOVto HI2FOV,andfound that themass of the CME under investigation continuously increased until it reached a distance of about $0 . 7 \mathrm { A U }$ ，but the mass increase dropped with distance.It is consistent with the trend of evolution predicted from our mass evolution in the COR FOV. When the CME started to leave the CORFOV,the measured mass increase per height $( d m / d h )$ seems to agree with the prediction of the“snow plow” model.As an outlook of the Work in this paper,we will test whether this model can explain the mass evolution in the HI FOV.Furthermore, if we assume a proper shape of CME at 1 AU,the mass residing in the CME and in the shock sheath can be approximately calculated from in situ measurements,which can add another data point in the mass evolution profile.

SOHO and STEREO are projects of international cooperation between ESA and NASA.The SECCHI data are produced by an international consortium of NRL，LMSAL,and NASA GSFC(USA)，RAL，and U. Birmingham (UK)，MPS (Germany),CSL (Belgium),IOTA,and IAS (France).SDO is a mission of NASA's Living With a Star Program.L.F.and W.Q.G. aresupported bythegrantsfromMOSTC (2011CB811402)，NSFC（11522328，11473070，11427803, 11233008and11273065)， NSFofJiangsuProvince (BK2012889)，CAS(XDA04076101). Y.W. and C.S.are supported by the grants from MOSTC (2011CB811403), CAS(KZZD-EW-01-4) and NSFC (41131065，41574165, 41121003 and 41274173). F.S. is supported by the grants from MOSTC（2012CB825601） andNSFC（41174150and 41474152).L.F.also acknowledges the Youth Innovation Promotion Association, CAS,for financial support. The work of B.I. is supported by DLR contract 5O OC 1301.

# APPENDIX “SNOWPLOW’MODELFORCMEPROPAGATION

“Snow plow”model assumes that all the solar wind plasma colliding with the CME will be attached to the CME.Based on this assumption and considering the 1D problem,the mass exchange between the CME and the solar wind is given by

$$
\Delta m = - \Delta m _ { \mathrm { s w } } = \rho _ { \mathrm { s w } } A \ \big | \nu _ { \mathrm { s w } } - \nu \big | \Delta t
$$

or

$$
{ \frac { d m } { d t } } = - { \frac { d m _ { \mathrm { { s w } } } } { d t } } = \rho _ { \mathrm { { s w } } } A \ \vert \nu _ { \mathrm { { s w } } } - \nu \vert
$$

where $m , \nu$ and $A$ are the mass,speed and the area of the crosssection of the CME, respectively, and $m _ { \mathrm { s w } } , \rho _ { \mathrm { s w } }$ and $\nu _ { \mathrm { s w } }$ are the mass,density and speed of the solar wind,respectively.The cross-section area $A = 4 \delta ( \alpha + \delta ) h ^ { 2 }$ ,where $2 \delta$ is the flux rope edge-on angularwidth, $2 ( \alpha + \delta )$ is the face-on angular width, and $h$ is the height of the leading edge.Using absolute value of $( \nu _ { \mathrm { s w } } - \nu )$ means the solar wind pileup could occur at either the frontside or backside of the CME.When the CME speed is higher than the solar wind speed, the solar wind piles up mainly at the frontside of the CME;When the CME speed is lower than the solar wind speed,the pileup mainly occurs at the backside. For the CME events in this paper,we have CME speed always higher than the solar wind speed.Therefore the pileup mainly occurred at the frontside.

The mass exchange causes the loss of the momentum of the background solar wind,which is

$$
\Delta p _ { \mathrm { s w } } = \Delta m _ { \mathrm { s w } } \nu _ { \mathrm { s w } } = - \rho _ { \mathrm { s w } } A \left| \nu _ { \mathrm { s w } } - \nu \right| \nu _ { \mathrm { s w } } \Delta t
$$

or

$$
\frac { d p _ { \mathrm { s w } } } { d t } = \frac { d m _ { \mathrm { s w } } } { d t } \nu _ { \mathrm { s w } } = - \rho _ { \mathrm { s w } } A \left| \nu _ { \mathrm { s w } } - \nu \right| \nu _ { \mathrm { s w } } .
$$

Meanwhile, the conservation ofmomentum requires $\begin{array} { r } { \frac { d p } { d t } = - \frac { d p _ { \mathrm { s w } } } { d t } } \end{array}$ i.e.,

$$
\begin{array} { c } { \displaystyle { \frac { d m \nu } { d t } = - \frac { d m _ { \mathrm { s w } } } { d t } \nu _ { \mathrm { s w } } } } \\ { \displaystyle { \Rightarrow \frac { d m } { d t } \nu + m a = - \frac { d m _ { \mathrm { s w } } } { d t } \nu _ { \mathrm { s w } } } } \end{array}
$$

where $a$ is the acceleration of the CME. Using Equation (5), the above equation leads to

$$
m a = { \frac { d m } { d t } } ( \nu _ { \mathrm { { s w } } } - \nu ) .
$$

On the other hand, combine Equations(7) and (9),we have

$$
\frac { d m } { d t } \nu + m a = \rho _ { \mathrm { s w } } A \nu _ { \mathrm { s w } } \left| \nu _ { \mathrm { s w } } - \nu \right|
$$

After Substituting Equation (1O) for ma in the above equation, it is obtained that

$$
\frac { d m } { d t } = \rho _ { \mathrm { s w } } A \left| \nu _ { \mathrm { s w } } - \nu \right|
$$

which is the equation we used to calculate the mass contribution from solar wind pileup.

# REFERENCES

Antunes,A., Thernisien,A.,& Yahil, A. 2009,SoPh,259,199   
Aschwanden, M. J., Nitta, N.V.,Wuelser, J.-P.,et al. 2009,ApJ, 706,376   
Bein,B.M.,Temmer,M., Vourlidas,A., Veronig,A.M.,& Utz,D.2013,ApJ, 768,31   
Billings,D.E.1966,A Guide to the Solar Corona (New York:Academic Press)   
Brueckner,G.E.,Howard,R.A.,Koomen,M.J.,et al.1995,SoPh,162, 357   
Byrne，J.P.，Maloney，S．A.，McAteer，R.T.J.，Refojo，J.M，& Gallagher, P.T.2010,NatCo,1,74   
Cargill, P. J. 2004, SoPh,221,135   
Carley,E.P.,McAteer,R.T.J.,&Gallagher,P.T.2012,ApJ,752,36   
Colaninno,R. C.,& Vourlidas,A.2009,ApJ, 698,852   
de Koning,C.A.,Pizzo,V.J.,& Biesecker, D.A.2009,SoPh,256,167   
DeForest, C.E.,Howard,T.A.,& McComas,D.J.2013,ApJ,769,43   
Feng,L.,Inhester,B.,& Gan,W.2015,ApJ,805,113   
Feng,L.,Inhester,B.,& Mierla,M.2013a, SoPh,282,221   
Feng,L.,Inhester, B., Wei, Y., et al. 2012, ApJ, 751,18   
Feng,L., Wiegelmann, T., Su, Y., et al. 2013b,ApJ, 765, 37   
Feng, X., Wu, S.T.,Wei,F.,& Fan, Q. 2003,SSRv,107, 43   
Feng,X.,Xiang,C.,Zhong,D.,& Fan,Q.2005,ChSBu,50,672   
Gui,B., Shen, C.,Wang,Y.,et al.2011, SoPh,271,111   
Howard,R.A.,Moses,J.D.,Vourlidas,A.,et al.2008,SSRv,136,67   
Howard，R.A.，& Vourlidas,A.2005，AGU Spring Meeting Abstracts SH53A-05   
Howard,T.A.,& DeForest, C.E.2012,ApJ, 752,130   
Howard,T. A.,& Tappin, S.J. 2009, SSRv,147,31   
Jin,M.,Ding,M.D., Chen,P.F.,Fang,C.,& Imada, S.2009,ApJ,702,27   
Kaiser, M.L., Kucera,T.A.,Davila, J. M., et al. 2008, SSRv,136,5   
Liewer, P.C.,de Jong,E.M.,Hall, J.R.,et al. 2009,SoPh,256,57   
Lugaz，N.，Manchester，W.B.，IV，& Gombosi，T.I.2005，ApJ，627, 1019   
Mierla,M., Chifu,I.,Inhester,B.,Rodriguez,L.,& Zhukov,A. 2011,A&A, 530, L1   
Mierla,M.,Inhester,B., Antunes,A.,et al. 2010, AnGeo,28,203   
Minnaert,M.1930, ZA,1,209   
Moran, T.G.,Davila, J. M.,& Thompson, W. T.2010,ApJ, 712,453   
Ontiveros,V.,&Vourlidas,A.2009,ApJ,693,267   
Riley,P.,Lionello,R.,Mikic,Z.,&Linker,J.2008,ApJ,672,1221   
Shen,C.,Wang,Y.,Pan, Z., et al.2013a, JGRA,118,6858   
Shen,F.,Feng,X. S.，& Song,W.B.2009, Sci China Ser E-Tech Sci, 522,2895   
Shen,F.,Feng, X. S.,Wu, S.T.,& Xiang, C.2007, JGRA,112, 6109   
Shen,F.，Shen, C.,Wang,Y.,Feng,X.,& Xiang,C.2013b,GeoRL,40, 1457   
Tappin, S.J. 2006, SoPh,233,233   
Temmer, M., Preiss, S.,& Veronig,A.M.2009, SoPh,256,183   
Thernisien,A.,Vourlidas,A.,& Howard,R.A.2009,SoPh,256,111   
Thernisien,A.,Vourlidas,A.,& Howard,R.A.2011,JASTP,73,1156   
Tian,H.,McIntosh, S.W., Xia,L.,He,J.，& Wang,X.2012,ApJ，748, 106   
van de Hulst,H. C.1950,BAN,11,135   
Vourlidas,A.,Howard,R.A.,Esfandiari,E.,et al.2010,ApJ,722,1522   
Vourlidas,A.，Subramanian,P.,Dere,K.P.,& Howard,R.A.2000,ApJ, 534, 456   
Vourlidas,A.,Wu,S.T.,Wang,A.H., Subramanian,P.,& Howard,R.A. 2003,ApJ,598,1392   
Wang,Y., Chen, C., Gui, B., et al. 2011, JGRA, 116, 4104   
Wang,Y.,Wang,B.，Shen, C.， Shen,F.,& Lugaz,N. 2014, JGRA,119, 5117   
Wood,B.E.,Howard,R.A., Thernisien,A.,Plunkett, S.P.,& Socker,D.G. 2009,SoPh,259,163