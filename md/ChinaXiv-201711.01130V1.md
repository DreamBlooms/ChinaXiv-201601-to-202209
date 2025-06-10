# Inertia Tensor for MORVEL Tectonic Plates

Li Chunxiao1,2

(1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 650011,China,Email:lcx@ ynao.ac.cn; 2.University of Chinese Academy of Scinces，Beijing 1OoO49，China)

Abstract：The NNR（No-Net-Rotation）-MORVEL（Mid-Ocean Ridge VELocity） 56 isa set of angular velocities describing the motions of 56 plates relative to a No-Net-Rotation reference frame.These plates can be adjusted in terms of non-overlapping polygonal regions，separated by plate boundaries on a unit sphere.During the calculation on the kinematic parameters for these 56 plates in a NNR reference frame using the International Terrestrial Reference Frame （ITRF） velocity field，the geometric parameters of tectonic plates play a significant role in establishing an absolute plate motion model based on space geodesy results. The computational method for these geometric parameters implemented as a FORTRAN9O program is described in this paper，allowing an evaluation of the area and the inertia tensor of a polygonal region on a unit sphere.This program is mainly built on a triangulation algorithm and the adaptive Simpson's double integral method for spherical polygons，which produces highly reliable results for all 56 modern plates.

Key Words: Tectonic plate；Spherical polygon； Inertia tensor；NNR-MORVEL56

# 1 Introduction

Most of Earth's major features can be understood from the interactions between tectonic plates，which move independently，separating from，colliding with，and sliding against one another.Until the middle 1960s an unifying theory was developed to explain Earth's dynamics[1].Several decades after the inception of the theory on plate tectonics，the plate dynamic models constructed using the geological and geophysical data have been dominant，until long time-span geodetic observations were gathered to estimate contemporary plate kinematic parameters[2-5]. As one of the most representative geological plate motion models，NUVEL-1A is one of the mainstream models regarding the plate dynamics and kinematics.With the setting up of the enhanced amount and quality of the geologicor geodetic data during the last few years，the MORVEL refined the precision and accuracy of the geometric and kinematic parameters for 56 plates that are partly taken from an updated digital model of pate boundaries by Bird[6].Relative to the NUVEL-1A，the MORVEL incorporates more than twice as many plates and covers more of Earth’s surface，and nearly allthe NUVEL-1A angular velocities differ significantly from its MORVEL counterparts[7].

To derive an absolute motion model in a NNR reference frame，however，the inertia tensors are always considered as indispensable atribute of all these plates.Despite various established methods for calculating plate inertia tensors corresponding to the NUVEL-1A model presented in many papers[8-9]，however it is necesary to recalculatea newsetfor the NNR-MORVEL56 model[10]，given theconsiderable discrepancy between the NUVEL-1A and the MORVEL.

When a polygon on the unit sphere is employed for the representation of a tectonic plate，a simplified analysis of the plate inertia tensorcanbe performed through a numerical method，which is carred out over all 56 plates.The method forcalculating all9 componentsof the inertia tensor is illustrated in this paper and this method requires the precise knowledge of the plate boundaries.The boundary file contains a 2-column sequence of the latitude-longitude plate boundary coordinates that fully enclosethe plate in the counterclockwise direction.

In the first section，we introduce some concepts regarding the no-net-rotation conditions and indicate the calculation of the Euler vector in anabsolute motion model.The following section describes the detailed mathematical models toestimate the area and the inertia tensor of the spherical polygons.The last section of this paper is dedicated to manifest the results for 56 modern platesand the appendix gives the original FORTRAN90 program for obtaining the aforementioned results.

# 2 Net Lithosphere Rotation

A no-net-rotation model for the lithosphere assumes that the integral of $v \times r$ over the Earth’s surface equals zero[11]， i. e.

$$
\int _ { \mathrm { E a r t h } } \boldsymbol { v } \times \boldsymbol { r } d S = 0 ,
$$

where， $r$ is the radial vector of the surface element on a unit sphere，and $v$ corresponds to the horizontal velocity at that position. The angular velocity of net rotation $\omega _ { \mathrm { n e t } }$ was computed as the total angular momentum of all plates divided by the moment of inertia of the entire lithosphere，using the equation[12-13]

$$
\omega _ { \mathrm { n e t } } = \frac { 3 } { 8 \pi } { \int } _ { \mathrm { E a r t h } } v \times r d S .
$$

Then it is convenient to convert the Eq.（2） into the following $\mathrm { f o r m } ^ { [ 8 ] }$

$$
\omega _ { \mathrm { n e t } } = \frac { 3 } { 8 \pi } \sum _ { i = 1 } ^ { n } Q _ { i } \omega _ { i } \ ,
$$

where $\pmb { \omega } _ { i }$ is the Euler vector describing the motion of plate $i$ relative to an inertial reference frame，such as ITRF2008，and $Q _ { i }$ is the inertia tensor of plate $i$ ，where $i$ goes from 1 to $n$ . The angular velocities of the plates relative to the NNR reference frame were then found by vector subtraction，namely,

$$
\begin{array} { r } { { \pmb { \omega } } _ { i } ^ { \mathrm { N N R } } = { \pmb { \omega } } _ { i } - { \pmb { \omega } } _ { \mathrm { n e t } } . } \end{array}
$$

For those tectonic plates where angular velocitiesare not available in the geodetic model such as the ITRF2000- PMM，due to alack of sufcient data，Altamimi[14] tested four cases to perfect the incomplete geodetic model. The fourth case described a method for estimating the missing angular velocity.Here we employ it in this paper by using a simple equation written as:

$$
\omega _ { i } ^ { \mathrm { I T R F } } = \omega _ { i j } ^ { \mathrm { M O R V E L } } + \omega _ { j } ^ { \mathrm { I T R F } } ,
$$

where $\pmb { \omega } _ { i } ^ { \mathrm { { I I R F } } }$ is the undeterminedrotationvector of plate $i$ in the ITRF model,and 0MORVEL is the MORVEL rotation vector for plate $i$ relative to plate $j$ ，which is adjacent to the missing plate $i$ ：

# 3 Area and inertia tensor of plates

# 3.1 Evaluation of the plate area

The spherical polygons are defined by great circle arcs connecting points on the sphere，the positions of which are given by latitudes and longitudes.Infact，analgorithm for determining thearea of a spherical polygon of arbitrary shapehas been presented by Bevis and Cambareri15]，where the kernel idea is to compute the interior angle at each vertex of the spherical polygon.In this paper，however，we employ a somewhat similar method to thatof Miler[16]，trying to determine the areaof spherical polygon bysumming the signed

areas of component triangles.

For a spherical polygon of $n$ sides，the spherical excess $E$ is generalized as

$$
E = \sum _ { i = 1 } ^ { n } \alpha _ { i } - \left( \left( n - 2 \right) \times 1 8 0 ^ { \circ } \right) ,
$$

where $\alpha _ { i } ( i \mathrm { = } 1 \cdots n )$ are the interior angles of the polygon.Considering a spherical polygon ABCD as shown in Fig.1（a），the north-pole combined with any twoadjacent vertices of the polygoncan constitute a spherical triangle，such as NAB.The two sides of the triangle are known from the latitudes of their vertices，i.e. $a n = \pi / 2 -$ latitude(A）and $b n { = } { \pi } / { 2 } { - } l a t i t u d e ( B )$ . Taking the previously obtained two sides and the included angle specified by the difference between longitudes of $A$ and $B$ ，the opposite side $a b$ can be calculated via the formula:

$$
a b = 2 \sin ^ { - 1 } \sqrt { h a v ( ~ b n - a n ) ~ + ~ \sinh b \sin a n h a v \angle N } ~ ,
$$

where the haversine function is defined as $h a v x = ( 1 - \mathrm { c o s } x ) / 2$ with $x$ in radians.Having obtained all three sides of the spherical polygon，we can use the formula to obtain its excess:

$$
E = 4 \tan ^ { - 1 } { \sqrt { \tan { \frac { s } { 2 } } + \tan { \frac { s - a n } { 2 } } + \tan { \frac { s - b n } { 2 } } + \tan { \frac { s - a b } { 2 } } } } ,
$$

where $s = { \frac { a n + b n + a b } { 2 } }$

To find the area of a spherical polygon，first，one may use the successive vertices in pair to form a spherical triangle.Each spherical triangle employs the north poleas acommon vertex to make the calculations convenient.When calculating the areas of the individual triangles，we adopt a convention that the sign of the triangle area （which has a same value as the spherical exces for a polygon on a unit sphere）is identical to thesignof the diference between the longitudes ofa pairof adjacent vertices.Ifthe longitude ofthe first vertex is less than the second one,then the sign of this triangle area is defined as a positive value for aset of points arranged in the anticlockwise Wayand vice versa.Therefore the area of the spherical polygon isregarded as the absolute value of the sum of the signed spherical excesses for each of the spherical triangles.Taking the facility of the calculation for the upcoming inertia tensor，a provision is crucial that the vertex point traversing the polygon prefersto be enumerated in the counterclockwise direction.

![](images/6047194bc160b0020196f964a46eb6c0ea3aab59bd8b9707a748567fcd4cdaab.jpg)  
Fig.1Spherical polygon andtriangles ilustrating calculation method for areaand inertia tensor discussed in text. （a）N triangles constructed from counterclockwise spherical polygon of n sides; (b）Spherical triangle encompassing Sorth Pole and the sides of polygon traversing the $1 8 0 \mathrm { { t h } }$ meridian

One should note the folowing two special cases when estimating the geometric parameters of the spherical polygons.The first case isas follows:if the sides of the polygon cross over the International Date Line from point $E _ { 1 }$ to $W _ { 1 }$ ，as illustrated in the Fig.1（b），a $2 \pi$ has to be added to the longitude of $\textstyle \mathbb { W } _ { 1 }$ . The same applies to a similar situation when a vertex leave $\textstyle \ W _ { _ 2 }$ for $E _ { 2 }$ ，a $2 \pi$ has to be subtracted from $E _ { 2 }$ in order to promise the continuity of the calculation.Thesecondcase occurs when a spherical polygon has an area larger than that of the hemisphere.According to a implicit assumption that the area of any polygon is less than $2 \pi$ ，for those extensive polygons，such as the triangle $A B C$ surrounding the north pole $\mathrm { \Delta N }$ ，the exact area of $A B C$ is the complement of $A B C$ including thenorth pole，i.e．Exa $\mathit { c t a r e a } \ = \ A r e a _ { \mathrm { { A B C } } } ^ { \mathrm { { s } } } \ = \ 4 \pi \ - \ A r e a _ { \mathrm { { A B C } } } ^ { \mathrm { { N } } }$ .Theoriginal FORTRAN9O program in the appendix has taken into account these two singular cases.

# 3.2Estimation of plate inertia tensor

The components of the symmetric inertia tensor $Q$ can be calculated for a region $P$ using the following formula :

$$
Q _ { \mu \nu } = \int _ { \mathrm { \scriptsize { P } } } \bigl ( \delta _ { \mu \nu } - x _ { \mu } x _ { \nu } \bigr ) \mathrm { d } A ,
$$

where $x _ { \mu } ( { \mu } = 1 , 2 , 3 )$ are the Cartesian coordinates， $\delta _ { \mu \nu } ( \mu , \nu = 1 , 2 , 3 )$ are the elements of the identity matrix，and the integration is carried out over the surface of a plate $P$ .These inertia tensors are based on the hypothesis that the surface density of the plate is unit one，and entirely describe the plategeometry.For instance，the plate area $A$ is easily calculated by taking the trace of $Q$ ：

$$
T r ( Q ) = \sum _ { \mu } \int _ { \mathrm { P } } ( 1 - x _ { \mu } ^ { 2 } ) \mathrm { d } A = 2 A .
$$

This implies invariance of the trace under coordinate rotations and the sum of the diagonal components is always double the area of the polygon. Generally speaking，non-diagonal components indicate the asymmetry of the polygon with respect to the Cartesian axes，and allof the diagonalcomponents have a positive value，which is useful,together with the Eq.（1O），as the verification test for the calculation results.

In this paper we propose a somewhat diffrent method from Schetino[17] for constructing the spherical triangle.In fact，we willsee that the integral at the right-hand sideof（Eq.（9））iseasilycalculated for spherical triangles. The components of the total tensor are therefore given by :

$$
\begin{array} { c } { { Q _ { \mu \nu } = \displaystyle \sum _ { i = 1 } ^ { n } \int _ { T _ { i } } ( \delta _ { \mu \nu } - x _ { \mu } x _ { \nu } ) \mathrm { d } A } } \\ { { { } } } \\ { { = \delta _ { \mu \nu } A - \displaystyle \sum _ { i = 1 } ^ { n } \int _ { T _ { i } } x _ { \mu } x _ { \nu } \mathrm { d } A } } \end{array} ,
$$

where $A$ is the total polygon area，which has been illustrated in the last section.Let a point on the sphere be given in spherical coordinates $( \theta , \lambda )$ ，where $\theta$ is the latitude and $\lambda$ is the longitude，so that its Cartesian coordinates are given by

$$
x _ { 1 } = \cos \theta \mathrm { c o s } \lambda \qquad x _ { 2 } = \mathrm { c o s } \theta \mathrm { s i n } \lambda \qquad x _ { 3 } = \mathrm { s i n } \theta ,
$$

then the area element $\mathrm { d } A$ at this position is equal to $\cos \theta \mathrm { d } \lambda \mathrm { d } \theta$ .The components of the inertia tensor for a triangle $N A B$ are therefore written， in spherical coordinates，as :

$$
Q _ { \mu \nu } = \delta _ { \mu \nu } A - \int _ { \lambda _ { 1 } } ^ { \lambda _ { 2 } } \mathrm { d } \lambda \int _ { \theta ( \lambda ) } ^ { \pi / 2 } f _ { \mu \nu } ( \theta , \lambda ) \mathrm { d } \theta ,
$$

where $\lambda _ { \scriptscriptstyle 1 }$ ， $\lambda _ { 2 }$ are the longitudes of vertices $A , B$ and the function $f$ is given by

$$
\begin{array} { r } { \pmb { f } ( \theta , \ \lambda ) = \left[ \begin{array} { l l l } { f _ { 1 1 } ( \theta , \ \lambda ) } & { f _ { 1 2 } ( \theta , \ \lambda ) } & { f _ { 1 3 } ( \theta , \ \lambda ) } \\ { f _ { 2 1 } ( \theta , \ \lambda ) } & { f _ { 2 2 } ( \theta , \ \lambda ) } & { f _ { 2 3 } ( \theta , \ \lambda ) } \\ { f _ { 3 1 } ( \theta , \ \lambda ) } & { f _ { 3 2 } ( \theta , \ \lambda ) } & { f _ { 3 3 } ( \theta , \ \lambda ) } \end{array} \right] . } \end{array}
$$

Next，as a result of the symmetry of the inertia tensor，the 6 independent components of $f$ are expressed in the following way :

$$
\begin{array} { c } { { f _ { 1 1 } ( \theta , \ \lambda ) = \cos ^ { 3 } \theta \cos ^ { 2 } \lambda } } \\ { { { } } } \\ { { f _ { 1 2 } ( \theta , \ \lambda ) = \cos ^ { 3 } \theta \mathrm { c o s } \lambda \mathrm { s i n } \lambda } } \\ { { { } } } \\ { { f _ { 1 3 } ( \theta , \ \lambda ) = \cos ^ { 2 } \theta \mathrm { s i n } \theta \mathrm { c o s } \lambda } } \end{array}
$$

$$
f _ { 2 2 } ( \theta , \ \lambda ) = \cos ^ { 3 } \theta \mathrm { s i n } ^ { 2 } \lambda
$$

$$
f _ { 2 3 } ( \theta , \ \lambda ) = \cos ^ { 2 } \theta \mathrm { s i n } \theta \mathrm { s i n } \lambda
$$

$$
f _ { 3 3 } ( \theta , \ \lambda ) = \sin ^ { 2 } \theta \mathrm { c o s } \theta .
$$

The upper limit of the inner integral about the latitude is always set to $\pi / 2$ ，because the North Pole is considered as the common vertex of each of the spherical triangles.In contrast，with the simple upper limit, the lower limit function $\theta ( \lambda )$ can be obtained from a serious of derivations，whose concrete form is formulated as

$$
\theta ( \lambda ) = - \arctan ( \frac { C _ { 1 } { \cos } \lambda + C _ { 2 } { \sin } \lambda } { C _ { 3 } } ) ,
$$

where $C _ { 1 }$ ， $C _ { 2 }$ ， $C _ { 3 }$ represent three constants. Once the integrated triangles are determined by one side of the polygon， such as $A B$ ，we can write their expression in the following form:

$$
\begin{array} { r l } & { C _ { 1 } = \mathrm { c o s } \theta _ { 1 } \mathrm { s i n } \lambda _ { 1 } \mathrm { s i n } \theta _ { 2 } - \mathrm { c o s } \theta _ { 2 } \mathrm { s i n } \lambda _ { 2 } \mathrm { s i n } \theta _ { 1 } } \\ & { C _ { 2 } = \mathrm { c o s } \theta _ { 2 } \mathrm { c o s } \lambda _ { 2 } \mathrm { s i n } \theta _ { 1 } - \mathrm { c o s } \theta _ { 1 } \mathrm { c o s } \lambda _ { 1 } \mathrm { s i n } \theta _ { 2 } , } \\ & { C _ { 3 } = \mathrm { c o s } \theta _ { 1 } \mathrm { c o s } \theta _ { 2 } \mathrm { s i n } \big ( \lambda _ { 2 } - \lambda _ { 1 } \big ) } \end{array}
$$

where $( \theta _ { 1 } , \lambda _ { 1 } ) , ( \theta _ { 2 } , \lambda _ { 2 } )$ are the latitude and the longitude of vertices $A$ and $B$ ， respectively.

Unlike the process of the area estimation，the evaluation of the inertia tensor is associated with the integral order.Hence，a counterclockwise direction must be adopted in the procedure.All of the special situations have been considered in the Fortran program,including the 18Oth meridian case and the encompassing the South Pole case.In addition to theaforementioned two special cases in the area estimation，the principal moments in the tensor calculation need to be deducted from the whole inertia tensorof the spherical surface in order to acquire the exact moments，i.e. Momen $t _ { \mathrm { E x a c t } } ^ { \mathrm { S } } = 8 \pi / 3 - M o m e n t _ { \mathrm { P r i n c i p a l } } ^ { \mathrm { N } }$ ，when involving thepolygon containing the south pole.

# 4Results and analysis

The NNR-NUVEL56 model contains 56 tectonic plates around the earth，and the software OSXStereonet developed by CardozoandAllmendinger[18]was aplied to plottheglobal platedistribution map，as ilustrated in Fig.2. Utilizing the Fortran program，we estimated geometry parameters of all56 modern plates with the accuracy the inertia tensor better than ${ { 1 0 } ^ { - 6 } }$ . Table 1 lists the area and the inertia tensor of all MORVEL plates , which provide essntial material for calculating plate kinematic parameters in the NNR reference frame.The sum ofthe area of all plates equals 12.56634O steradian，which is slightly less than the surface area of the whole unit sphere，namely $4 \pi ( 1 2 . 5 6 6 3 7 1 )$ with the relative error $\eta = 0 . 0 0 0 2 3 \%$ . Our results indicate that the relative errors for the six components of the total tensor are $0 . 0 0 0 1 7 \%$ ， $0 . 0 0 0 2 9 \%$ ， $0 . 0 0 0 2 6 \%$ ， $0 . 0 0 1 0 \%$ ， $0 . 0 0 0 1 6 \%$ ，and $0 . 0 0 0 1 0 \%$ respectively，It is shown that the inertia tensor of the entire spherical surface is $8 \pi / 3 E$ ，where $E$ takes the identity matrix.The discrepancy probably arises from either the imperfection of plates over the entire sphere or the unavoidable rounding errors in floating point arithmetic.

# 5 Conclusion

The method for computing the areas and inertial tensors of tectonic plates has been presented.This method is based upon the triangulation algorithm and the adaptive Simpson’sdouble integral procedure，which can be applied to the spherical polygons representing such tectonic plates.Results for the NNR-MORVEL56 tectonic plates show that highly reliable data can be produced,as long as starting from the precise definition of the plate boundaries.In addition,a FORTRAN9O program has been atached to the end of thispaper,which is expected to be valuable to the future studies of the kinematics and dynamics associated to the motions of tectonic plates.

![](images/28fc1bc359ac9651f3ad8ce8ea2678f574585170f3a1e5f700b0293d51f37b05.jpg)  
Fig.2Plate boundaries and geometries employed for MORVEL

(a）View direction at $3 5 ^ { \circ }$ sorth, $\boldsymbol { 0 } ^ { \circ } \mathrm { e a s t }$ ；（b）View direction at $2 0 ^ { \circ }$ north, ${ 1 8 0 } ^ { \circ }$ east a Plate name abbreviations areas folows：am，Amur；an，Antarctic；AP，Altiplano；ar，Arabia；AS，Aegean Sea；au, Australia;BH,Birds Head;BR，Balmoral Ref；BS,Banda Sea；BU,Burma；ca,Caribbean；CL,Caroline；cp,Cocos；cp, Capricorm；CR,Caroline；EA，Easter；eu，Eurasia；FT,Futuna；GP,Galapagos；in，India；jf,Juan deFuca；JZ，Juan Fernandez； KE,Kermadec；lw,Lwandle；MA,Mariana；MN,Manus；MO,Maoke；mq，Macquarie；MS,Molucca Sea；na, North America；NB,North Bismarck；ND，North Andes；NH，New Hebrides；NI，Niuafou；nb，Nubia；nz，Nazca；OK, Okhotsk；ON,Okinawa;pa,Pacific；PM,Panama；ps,Philipine Sea；ri，Rivera；sa,South America；SB,South Bismarck； sc，Scotia;SL，Shetland；sm,Somalia;sr,Sur;SS,SolomonSea；su,Sundaland；sw,Sandwich；TI,Timor;TO,Tonga；WL, Woodark；yz,Yangte.PlateabbreviationsgiveninlowercaseareforplatesincludedintheMORVEL.Plateabbreviationsgivenin the uppercase are forplatesfrom Bird(2OO3）；b.Plate areasare insteradians foraunit sphere,and thesumof which totals $4 \pi$ ：

Table 1Geometric parameters of 56 modern plates included in the NNR-MORVEL56   

<html><body><table><tr><td>Platea</td><td>Areab</td><td>Q1</td><td>Q22</td><td>Q33</td><td>Q12</td><td>Q13</td><td>Q23</td></tr><tr><td>ram</td><td>0. 130659</td><td>0. 108248</td><td>0. 089481</td><td>0. 063589</td><td>0. 028732</td><td>0.036320</td><td>-0. 051295</td></tr><tr><td>an</td><td>1. 432624</td><td>1. 326692</td><td>1. 174711</td><td>0.363845</td><td>-0. 050954</td><td>0. 052461</td><td>0.081269</td></tr><tr><td>AP</td><td>0. 020501</td><td>0. 018168</td><td>0. 004178</td><td>0. 018656</td><td>0. 006097</td><td>0. 002056</td><td>-0.005420</td></tr><tr><td>ar</td><td>0. 120824</td><td>0. 074249</td><td>0. 066810</td><td>0. 100589</td><td>-0.048782</td><td>-0. 029553</td><td>-0. 031041</td></tr><tr><td>AS</td><td>0.007930</td><td>0. 003780</td><td>0.007017</td><td>0. 005063</td><td>-0.001938</td><td>-0.003445</td><td>-0. 001610</td></tr><tr><td>AT</td><td>0.014182</td><td>0.008022</td><td>0. 011586</td><td>0.008756</td><td>-0.003970</td><td>-0.005767</td><td>-0. 003733</td></tr><tr><td>au</td><td>0. 921383</td><td>0. 597620</td><td>0. 558686</td><td>0. 686460</td><td>0. 223995</td><td>-0. 217199</td><td>0. 241071</td></tr><tr><td>BH</td><td>0. 012950</td><td>0. 007157</td><td>0. 005807</td><td>0. 012936</td><td>0. 006391</td><td>-0. 000194</td><td>0.000201</td></tr><tr><td>BR</td><td>0. 004814</td><td>0. 000353</td><td>0.004786</td><td>0. 004488</td><td>0.000322</td><td>-0.001203</td><td>0.000086</td></tr><tr><td>BS</td><td>0. 017146</td><td>0.011322</td><td>0. 005961</td><td>0. 017009</td><td>0. 007977</td><td>-0.000850</td><td>0. 001173</td></tr><tr><td>BU</td><td>0. 012697</td><td>0. 012632</td><td>0.000436</td><td>0.012327</td><td>0. 000852</td><td>0.000130</td><td>-0. 001936</td></tr><tr><td>ca</td><td>0. 073043</td><td>0. 066003</td><td>0. 011971</td><td>0. 068111</td><td>0. 018006</td><td>-0. 005213</td><td>0. 017059</td></tr><tr><td>CL</td><td>0. 037650</td><td>0. 015349</td><td>0. 022487</td><td>0. 037464</td><td>0. 018192</td><td>0. 001581</td><td>-0.001323</td></tr><tr><td>C0</td><td>0. 072230</td><td>0. 071072</td><td>0. 003017</td><td>0. 070372</td><td>-0. 005543</td><td>0. 001064</td><td>0. 010142</td></tr><tr><td>cp</td><td>0. 203647</td><td>0. 196537</td><td>0. 022175</td><td>0.188580</td><td>-0. 021636</td><td>0.007182</td><td>0. 045603</td></tr><tr><td>CR</td><td>0. 003559</td><td>0. 000414</td><td>0. 003532</td><td>0. 003172</td><td>0. 000289</td><td>-0.001100</td><td>0.000101</td></tr><tr><td>EA</td><td>0. 004114</td><td>0. 003554</td><td>0. 001272</td><td>0.003402</td><td>-0.001260</td><td>-0.000631</td><td>-0.001420</td></tr><tr><td>eu</td><td>1. 196311</td><td>1. 005910</td><td>0. 894791</td><td>0. 491921</td><td>-0. 035559</td><td>-0. 213221</td><td>-0. 310262</td></tr><tr><td>FT</td><td>0.000789</td><td>0.000054</td><td>0. 000787</td><td>0. 000736</td><td>-0.000027</td><td>-0.000197</td><td>-0.000007</td></tr><tr><td>GP</td><td>0.000360</td><td>0. 000346</td><td>0. 000015</td><td>0. 000360</td><td>-0.000071</td><td>0.000002</td><td>0. 000012</td></tr><tr><td>in</td><td>0.306360</td><td>0. 286350</td><td>0. 042318</td><td>0.284052</td><td>-0. 057049</td><td>-0. 013096</td><td>-0.060490</td></tr><tr><td>jf</td><td>0. 006315</td><td>0. 005162</td><td>0. 004356</td><td>0. 003111</td><td>-0. 001501</td><td>0.001916</td><td>0. 002491</td></tr><tr><td>JZ</td><td>0. 002406</td><td>0. 002192</td><td>0. 000941</td><td>0. 001679</td><td>-0.000560</td><td>-0.000394</td><td>-0.001032</td></tr><tr><td>KE</td><td>0. 012450</td><td>0. 003751</td><td>0. 012432</td><td>0. 008717</td><td>-0.000123</td><td>-0. 005589</td><td>-0.000034</td></tr><tr><td>lw</td><td>0. 117084</td><td>0. 063137</td><td>0. 081094</td><td>0. 089937</td><td>-0.043330</td><td>0. 036053</td><td>0. 029664</td></tr><tr><td>MA</td><td>0. 010367</td><td>0. 004018</td><td>0. 007354</td><td>0.009362</td><td>0. 004369</td><td>0. 002475</td><td>-0.001708</td></tr><tr><td>MN</td><td>0.000203</td><td>0.000050</td><td>0.000154</td><td>0.000202</td><td>0.000086</td><td>-0.000011</td><td>0.000006</td></tr></table></body></html>

Table 1 continued from previous page.   

<html><body><table><tr><td>Platea</td><td>Areab</td><td>Q11</td><td>Q22</td><td>Q33</td><td>Q12</td><td>Q13</td><td>Q23</td></tr><tr><td>MO</td><td>0.002841</td><td>0. 001271</td><td>0.001581</td><td>0.002830</td><td>0. 001405</td><td>-0. 000126</td><td>0.000113</td></tr><tr><td>mq</td><td>0.007890</td><td>0.006131</td><td>0.007510</td><td>0.002139</td><td>0.000812</td><td>-0. 003172</td><td>0.001465</td></tr><tr><td>MS</td><td>0.010301</td><td>0.007165</td><td>0.003150</td><td>0.010287</td><td>0. 004720</td><td>-0.000118</td><td>0. 000164</td></tr><tr><td>na</td><td>1. 365654</td><td>1. 228582</td><td>0. 941574</td><td>0.561152</td><td>0.066184</td><td>-0.003632</td><td>0. 396247</td></tr><tr><td>NB</td><td>0. 009563</td><td>0. 002624</td><td>0. 006962</td><td>0. 009540</td><td>0. 004209</td><td>-0.000360</td><td>0. 000211</td></tr><tr><td>ND</td><td>0. 023942</td><td>0. 022362</td><td>0.002000</td><td>0. 023523</td><td>0. 005755</td><td>-0.000735</td><td>0. 002485</td></tr><tr><td>NH</td><td>0. 015853</td><td>0. 001931</td><td>0. 015441</td><td>0. 014334</td><td>0.002345</td><td>-0. 004547</td><td>0. 000758</td></tr><tr><td>NI</td><td>0. 003062</td><td>0. 000271</td><td>0. 003046</td><td>0. 002808</td><td>-0.000212</td><td>-0.000839</td><td>-0.000063</td></tr><tr><td>nb</td><td>1. 440653</td><td>0. 372572</td><td>1. 301219</td><td>1. 207515</td><td>-0. 051346</td><td>-0. 005428</td><td>0. 044223</td></tr><tr><td>nz</td><td>0. 396683</td><td>0. 385354</td><td>0. 068410</td><td>0.339603</td><td>-0. 012644</td><td>-0. 002969</td><td>-0. 113428</td></tr><tr><td>OK</td><td>0. 074825</td><td>0. 053441</td><td>0. 066413</td><td>0. 029796</td><td>0. 012953</td><td>0. 030320</td><td>-0. 017870</td></tr><tr><td>ON</td><td>0.008000</td><td>0.005617</td><td>0.004075</td><td>0.006307</td><td>0.003044</td><td>0.002004</td><td>-0. 002552</td></tr><tr><td>pa</td><td>2. 576858</td><td>1. 175689</td><td>1. 961254</td><td>2. 016772</td><td>-0. 429469</td><td>0. 077428</td><td>-0.057431</td></tr><tr><td>PM</td><td>0. 006744</td><td>0. 006575</td><td>0. 000333</td><td>0. 006580</td><td>0.001000</td><td>-0. 000159</td><td>0. 001021</td></tr><tr><td>ps</td><td>0. 134118</td><td>0. 077744</td><td>0. 071266</td><td>0.119226</td><td>0.058301</td><td>0. 026648</td><td>-0. 027639</td></tr><tr><td>ri</td><td>0. 002486</td><td>0. 002289</td><td>0. 000489</td><td>0. 002193</td><td>-0. 000625</td><td>0. 000239</td><td>0. 000763</td></tr><tr><td>sa</td><td>1. 003382</td><td>0. 606780</td><td>0.582701</td><td>0.817282</td><td>0.338318</td><td>0. 179187</td><td>-0.168608</td></tr><tr><td>SB</td><td>0. 007615</td><td>0. 002101</td><td>0. 005575</td><td>0. 007554</td><td>0. 003341</td><td>-0. 000571</td><td>0. 000346</td></tr><tr><td>SC</td><td>0. 041900</td><td>0. 036723</td><td>0. 034464</td><td>0. 012613</td><td>0. 005695</td><td>0. 011988</td><td>-0. 014451</td></tr><tr><td>SL</td><td>0.001780</td><td>0. 001675</td><td>0.001490</td><td>0.000396</td><td>0.000174</td><td>0.000381</td><td>-0. 000634</td></tr><tr><td>sm</td><td>0. 354795</td><td>0. 221034</td><td>0. 153743</td><td>0. 334814</td><td>-0. 154899</td><td>0.024755</td><td>0.035861</td></tr><tr><td>ST</td><td>0. 027055</td><td>0. 018681</td><td>0. 026496</td><td>0. 008933</td><td>0. 001954</td><td>0. 012245</td><td>-0. 002957</td></tr><tr><td>SS</td><td>0.003170</td><td>0. 000715</td><td>0.002505</td><td>0.003119</td><td>0. 001275</td><td>-0.000352</td><td>0.000183</td></tr><tr><td>su</td><td>0. 219667</td><td>0. 188850</td><td>0. 036326</td><td>0.214159</td><td>0. 069104</td><td>0. 006544</td><td>-0. 016832</td></tr><tr><td>SW</td><td>0. 004543</td><td>0. 003525</td><td>0. 004269</td><td>0.001292</td><td>0. 000527</td><td>0. 001817</td><td>-0.000940</td></tr><tr><td>TI</td><td>0.008704</td><td>0. 005784</td><td>0.003120</td><td>0.008503</td><td>0.004009</td><td>-0. 000751</td><td>0.001052</td></tr><tr><td>TO</td><td>0. 006248</td><td>0. 000759</td><td>0. 006194</td><td>0. 005544</td><td>-0. 000536</td><td>-0.001947</td><td>-0. 000186</td></tr><tr><td>WL</td><td>0. 011163</td><td>0. 003492</td><td>0. 007835</td><td>0. 010998</td><td>0. 004966</td><td>-0. 001074</td><td>0. 000660</td></tr><tr><td>yz</td><td>0. 054249</td><td>0. 045687</td><td>0. 019960</td><td>0. 042851</td><td>0. 016644</td><td>0.009648</td><td>-0. 019528</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# References :

[1] Hamblin W K,Christiansen E H. Earth's dynamic systems [M].1Oth ed. State of New Jersey: Prentice Hall,2003.   
[2] Larson K M，Freymueler JT，Philipsen S. Global plate velocities from the global positioning system ［J]. Journal of Geophysical Research Solid Earth，1997，102（B5）:9961-9981.   
[3] Sella G F，Dixon T H，Mao A. Revel: a model for recent plate velocities from space geodesy [J]. Journal of Geophysical Research Solid Earth，2002，107(B4)：ETG 11-1- ETG 11-30.   
[4] Corné K，Holt W E, John HA.An integrated global model of present-day plate motions and plate boundary deformation [J].Geophysical Journal International，2OO3，154(1）：8-34.   
[5] Altamimi Z,Métivier L,Colilieux X. ITRF 2008 plate motion model[J]. Journal of Geophysical Research Solid Earth，2012，117(B7）:47-56.   
[6] Peter B. An updated digital model of plate boundaries [J]. Geochemistry Geophysics Geosystems , 2003，4(3):101-112.   
[7] Demets C，Gordon R G，Argus D F. Geologically current plate motions [J]. Geophysical Journal International，2010，181（1）：1-80.   
[8] Argus D F，Gordon R G.No-net-rotation model of current plate velocities incorporating plate motion model nuvel-1［J]. Geophysical Research Letters，1991，18(11）：2039-2042.   
[9] Corné K，Holt W E.A no-net-rotation model of present-day surface motions [J]. Geophysical Research Letters，2001，28(23）:4407-4410.   
[10] Argus D F，Gordon R G，Demets C.Geologically current motion of 56 plates relative to the nonet-rotation reference frame [J]. Geochemistry Geophysics Geosystems，2011,12(11）: 75-87.   
[11]Klemann V，Martinec Z,Ivins ER. Glacial isostasy and plate motion [J]. Journal of Geodynamics, 2008,46(3-5) : 95-103.   
[12] Solomon S C， Sleep N H. Some simple physical models for absolute plate motions [J]. Journal of Geophysical Research，1974，79(17）:2557-2567.   
[13] Torsvik T H,Steinbergerd B,Gurnise M,et al.Plate tectonics and net lithosphere rotation over the past 150 my［J].Earth & Planetary Science Letters，2010,291（1）：106-112.   
[14] Zuheir A，Patrick S,Claude B.The impact of a no-net-rotation condition on ITRF2Ooo ［J]. Geophysical Research Letters，2003，30(2）：36-1-36-4.   
[15] Bevis M，Cambareri G. Computing the area of a spherical polygon of arbitrary shape [J]. Mathematical Geology，1987，19(4）:335-346.   
[16] Heckbert P S.Graphics Gems IV[M]. Boston: Academic Press Professonal，1994:132-137.   
[17] Schetino A. Computational methods for calculating geometric parameters of tectonic plates [J]. Computers& Geosciences，1999，25（8）:897-907.   
[18] Cardozo N，Allmendinger R W. Spherical projections with OSXStereonet [J]. Computers & Geosciences，2013，51：193-205.

# The FORTRAN90 Program

MODULECALCULATE_SPHPOLAERA_INERTEN

！  
!THIS IS A FORTRAN9O MODULE，WHICH INCLUDES A SET OF FUNCTIONS AND SUBROUTIBES! USED FOR CALCULATING THE AREAS AND INERTIA TENSORS OF AMOUNTS SPHERICAL POLYGONS.！\*\*\*\* \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*  
！DISCUSSION:  
! VERTEXES OF THE SPHERICAL POLYGON MUSTBE SEQUENCEDINA COUNTERCLOCKWISE DRIECTION.!THEFIRSTPOINT IN BOUNDARYFILES SHOULD ALWAYS BE IDENTICAL TO THE LAST ONE  
!INORDERTOCONSTRUCTACLOSEDPOLYGONOFNSIDESWITH $_ { \mathrm { { N + 1 } } }$ DATA POINTS.  
！  
！MODIFIED：26DECEMBER2014  
！  
！AUTHOR：CHUNXIAO LI  
，PARAMETER:: HALFPI $\mathbf { \Sigma } = \mathbf { \Sigma }$ PI/2D0  
,PARAMETER::DEGREE $\mathbf { \tau } = \mathbf { \tau }$ 180D0/PI!DEGREES PER RADIAN  
ETURNS THE AREA AND SIX COMPONENTS OF THE INERTIA TENSOR OF A N-SIDED  
CAL POLYGON.  
T AND LON SHOULED TAKE DEGREE AS THEIR UNIT,RANGING FROM -9O TO 90 AND  
.80 TO 180,RESPECTIVELY.DATAPOINTSPORTRAYAPOLYGONWIYHNVERTEXES.  
PUT PARAMETER, SPHERICALPOLYGONAREA，REPRESENTS THE AREA OF THE SPHERICAL POLYGON  
ADIANSFOR AUNIT SPHERE.  
MAMENT SIXPARANETERS INDICATE SIX COMPONENTS OF THE INERTIA TENSOR  
TINE SPITC(LAT,LON,N,SPHERICALPOLYGONAREA,SUM11,SUM22,SUM33,SUM12,SUM13,SUM23)  
IMPLICIT NONE  
INTEGER: : N  
REAL $\ast \mathbf { 8 }$ : : LAT(N),LON(N)  
REAL $\ast \mathbf { 8 }$ : : SPHERICALPOLYGONAREA  
REAL $\ast \mathbf { 8 }$ : : SUM11,SUM22,SUM33,SUM12,SUM13,SUM23  
INTEGER: : J  
REAL $\ast \mathbf { 8 }$ : : LON1,LON2,LAT1,LAT2  
REAL ${ \ast \mathbf { \delta \mathbf { 8 } } }$ ::HAVB,DLON,PDLON  
REAL $\ast \mathbf { 8 }$ : : T,A,B,C,S,SUM,EXCESS  
REAL $\ast \mathbf { 8 }$ : : C1,C2,C3  
COMMON/GROUP1/ C1,C2,C3  
REAL $\ast \mathbf { 8 }$ : : S11,S22,S33,S12,S13,S23  
REAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ : : EPS  
COMMON/GROUP2/EPS!THE TOLERANCE INVOLVED ON COMPUTATION IS SPECIFIED BY EPS.  
（204号 $\mathrm { S U M } \ = \ 0 \mathrm { D } 0$   
（20 $\mathrm { S U M } 1 1 = 0 \mathrm { D } 0$ （204号  
（20 $\mathrm { S U M } 2 2 \ = \ 0 \mathrm { D } 0$ （  
（20 $\mathrm { S U M } 3 3 \ = \ 0 \mathrm { D } 0$ （  
（204号 $\mathrm { S U M } 1 2 \ = \ 0 \mathrm { D } 0$   
（20 $\mathrm { S U M } 1 3 \ = \ 0 \mathrm { D } 0$ （  
（20 $\mathrm { S U M } 2 3 \ = \ 0 \mathrm { D } 0$ （  
（20 $\bf { D O J } = 1 , \bf { N } \mathrm { - 1 }$ （20LON1 = LON(J)/DEGREE$\mathrm { L A T 1 } = \mathrm { L A T ( J ) } / \mathrm { D E G R E E }$ $\mathrm { L O N } 2 = \mathrm { L O N } ( \mathrm { J } + 1 ) / \mathrm { D E G R E E }$ （20 $\mathrm { L A T 2 } = \mathrm { L A T ( J + 1 ) } / \mathrm { D E G R E E }$ CALL COEFFICIENT(LAT1,LON1,LAT2,LON2)PI $) \mathrm { L O N } = \mathrm { L }$ ON2-LON1DLON $\ c =$ ABS(PDLON)IF（DLON.GT.1E-6）THENIF(DLON.GT.PI) $\mathrm { D L O N } = 2 \mathrm { D } 0 *$ PI-DLONIF（LON2.LT.LON1.AND.PDLON.LT.-PI) $\mathrm { L O N } 2 = \mathrm { L O N } 2 + 2 \mathrm { D } 0 * \mathrm { P I }$ （IF（LON2.GT.LON1.AND.PDLON.GT.PI) $\mathrm { L O N } 2 \ : = \ : \mathrm { L O N } 2 \ : - 2 \mathrm { D } 0 \ast \mathrm { P I }$ $\mathrm { H A V B } = \mathrm { H A V } ( \mathrm { L A T 2 - L A T 1 } ) + \mathrm { \mathbf { C O S } ( L A }$ T1）\* COS（LAT2）\* HAV（DLON)（20 $\mathrm { \bf ~ B } = 2 \mathrm { D 0 } * \mathrm { \bf A S I N } ( \mathrm { \bf S Q R T } ( \mathrm { \bf ~ H A V B } ) )$ A = HALFPI-LAT1（204 $\mathrm { C } = \mathrm { H A L F P I - L A T 2 }$ （204号（204号 $\mathrm { S = 0 . 5 D 0 * ( A { + } B { + } C ) }$ （20（204 $\mathrm { \Delta T = T A N ( S / 2 D 0 ) * T A N ( ( S - A ) / 2 D 0 ) * T A N ( ( S - B ) / 2 D 0 ) }$ \* TAN((S-C)/2D0)$\mathrm { E X C E S S } = \mathbf { A B S } ( 4 \mathrm { D 0 } * \mathbf { A T A N } ( \mathbf { S Q R T } ( \mathbf { A B S } ( \mathrm { T } ) ) ) )$ IF（LON2.LT.LON1） EXCESS $\mathbf { \tau } = \mathbf { \tau }$ -EXCESS$\mathrm { S U M } = \mathrm { S U M } + \mathrm { E X C E S S }$ （20CALL FSIM2(LON1,LON2,FS_LOWERLIMIT,FS_UPPERLIMIT,F11,EPS,S11)CALL FSIM2(LON1,LON2,FS_LOWERLIMIT,FS_UPPERLIMIT,F22,EPS,S22)CALLFSIM2（LON1,LON2,FS_LOWERLIMIT,FS_UPPERLIMIT,F33,EPS,S33)CALL FSIM2(LON1,LON2,FS_LOWERLIMIT,FS_UPPERLIMIT,F12,EPS,S12)CALL FSIM2(LON1,LON2,FS_LOWERLIMIT,FS_UPPERLIMIT,F13,EPS,S13)CALLFSIM2(LON1,LON2,FS_LOWERLIMIT,FS_UPPERLIMIT,F23,EPS,S23)（204号 $\mathrm { S U M 1 1 } = \mathrm { S U M 1 1 } + \mathrm { S 1 1 }$ （204号（204号 $\mathrm { S U M } 2 2 \ = \ \mathrm { S U M } 2 2 \ + \ \mathrm { S } 2 2$ （204号（204号 $\mathrm { S U M } 3 3 = \mathrm { S U M } 3 3 + \mathrm { S } 3 3$ $\mathrm { S U M } 2 3 \ = \ \mathrm { S U M } 2 3 \ + \ \mathrm { S } 2 3$ END IF  
END DO  
IF（SUM.LT.O.DO）THENSPHERICALPOLYGONAREA $\mathbf { \Sigma } = \mathbf { \Sigma }$ SUM+ 4D0 \*PISUM11 = 8.D0/3.D0 \*PI-SUM11-ABS(SUM)$\mathrm { S U M } 2 2 \ = \ 8 . \mathrm { D } 0 / 3 . \mathrm { D } 0 * \mathrm { P I } \mathrm { - S U M } 2 2 \mathrm { - } \mathrm { \bf A B S } ( \mathrm { S U M }$ ）$\mathrm { S U M } 3 3 \ = \ 8 . \mathrm { D } 0 / 3 . \mathrm { D } 0 * \mathrm { P I } \mathrm { - S U M } 3 3 \mathrm { - } \mathbf { A } \mathbf { B } \mathbf { S } ( \mathrm { S U M } )$   
ELSESPHERICALPOLYGONAREA $\mathbf { \tau } = \mathbf { \tau }$ SUMSUM11 $\mathbf { \Sigma } = \mathbf { \Sigma }$ SPHERICALPOLYGONAREA - SUM11SUM22 $\mathbf { \tau } = \mathbf { \tau }$ SPHERICALPOLYGONAREA -SUM22SUM33 $\mathbf { \tau } = \mathbf { \tau }$ SPHERICALPOLYGONAREA -SUM33END IFSUM12 $\mathbf { \Sigma } = \mathbf { \Sigma }$ -SUM12SUM13 $\mathbf { \tau } = \mathbf { \tau }$ -SUM13$\mathrm { S U M } 2 3 \ = \ - \mathrm { S U M } 2 3$ （204号RETURN  
END SUBROUTINE  
!GIVEN THE DOMAIN OF INTEGERAL，FSIM2 RETUENS THE INTEGRAL OF F.  
SUBROUTINE FSIM2（A,B,FS_LOWERLIMIT,FS_UPPERLIMIT,F,EPS,S)IMPLICITNONEREAL $\ast \mathbf { 8 }$ ,EXTERNAL::FS_LOWERLIMIT,FS_UPPERLIMIT,FREAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ ::A,B,EPS,S!LOCALVARIABLESREAL $\ast \mathbf { 8 }$ : : H,S1,S2,TS1,TS2,X,G,S0,CINTEGER:: N,J（204号 ${ \mathrm { N } } = 1$ $\mathrm { H } = 0 . 5 \mathrm { D } 0 *$ (B-A)$\mathrm { C } = \left( \mathrm { \Delta B } { - } \mathrm { A } \right) * 1 . 0 \mathrm { E } { - } 0 6$ （204号CALL SIMP1(A,FS_LOWERLIMIT,FS_UPPERLIMIT,F,EPS,S1)CALLSIMP1（B,FS_LOWERLIMIT,FS_UPPERLIMIT,F,EPS,S2)${ \mathrm { T S 1 } } = { \mathrm { H } } *$ （ $\mathrm { S } 1 { + } \mathrm { S } 2 \$ ）DO WHILE（ABS(H).GE.ABS（C））$\mathrm { { X = A \mathrm { { - H } } } }$ （204号$\mathrm { T S } 2 = 0 . 5 \mathrm { D 0 } * \mathrm { T S } 1$ DO $\mathrm { J } = 1 , \mathrm { N }$ （20$\mathrm { X = X + 2 D 0 * H }$ （20CALL SIMP1(X,FS_LOWERLIMIT,FS_UPPERLIMIT,F,EPS,G)$\mathrm { T S } 2 = \mathrm { T S } 2 + \mathrm { H } * \mathrm { G }$ （204号END DO（20 $\mathrm { S } { } = ( \mathrm { 4 D 0 } * \mathrm { T S 2 } { } \mathrm { - T S 1 } ) / 3 . 0 \mathrm { D 0 }$ （20${ \bf N } = { \bf N } + { \bf N }$ （204号IF（N.GE.16）THENIF（ABS(S-SO).LE.EPS $*$ （ABS（S）+1.0DO））RETURNEND IF（20 ${ \mathrm { S 0 } } = { \mathrm { S } }$ （204号 $\mathrm { T S } 1 = \mathrm { T S } 2$ （204号（20 $\mathrm { H } = 0 . 5 \mathrm { D 0 } * \mathrm { H }$ （20END DORETURN  
END SUBROUTINE  
SUBROUTINE SIMP1(X,FS_LOWERLIMIT,FS_UPPERLIMIT,F,EPS,G)IMPLICIT NONEREAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ : : X,EPS,GREAL $\ast \mathbf { 8 }$ ,EXTERNAL::FS_LOWERLIMIT,FS_UPPERLIMIT,F!LOCAL VARIABLESREAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ : : Y1,Y2,H,C,TS1,TS2,Y,G0INTEGER : : N,I（20 ${ \mathrm { N } } = 1$ Y1 = FS_LOWERLIMIT（X)

$\mathrm { Y } 2 \ = \ \mathrm { F S \_ U P P E R L I M I T ( \mathrm { X } ) }$ $\mathrm { H } = 0 . 5 \mathrm { D } 0 *$ (Y2-Y1) C=（Y2-Y1）\*1.0E-06

$\mathrm { T S 1 } = \mathrm { H } * \left( \mathrm { F } ( \mathrm { X } , \mathrm { Y 1 } ) + \mathrm { F } ( \mathrm { X } , \mathrm { Y 2 } ) \right)$ ）  
DOWHILE（ABS(H).GE.ABS(C））${ \boldsymbol { \Upsilon } } = { \boldsymbol { \Upsilon } } 1 - { \boldsymbol { \mathrm { H } } }$ TS2=0.5D0 \* TS1DOI=1,NY = Y +ZDU \* HTS2=TS2+H \* F(X,Y)END DO（204号 $\mathrm { G } = ( 4 \mathrm { D } 0 * \mathrm { T S } 2 \mathrm { - } \mathrm { T S } 1 ) / 3 . 0 \mathrm { D } 0$ （20（204号 ${ \bf N } = { \bf N } + { \bf N }$ （20IF（N.GE.16）THENIF（ABS(G-GO).LE.EPS $*$ （ABS（G）+1.0DO））RETURNEND IF（20 $G 0 = { \mathrm { G } }$ （204号$\mathrm { T S } 1 = \mathrm { T S } 2$ （204号（204号 $\mathrm { H } = 0 . 5 \mathrm { D 0 } * \mathrm { H }$ （2END DORETURN  
END SUBROUTINE  
!FS_LOWERLIMIT RETURN THE LOWERLIMIT CONDUCTING AS A FUNCTION OF  
! LONGITUDE；AND THE FS_UPPERLIMIT RETURNS A CONSTANT UPPERLIMIT，PI/2.  
FUNCTION FS_LOWERLIMIT(LON)IMPLICIT NONEREAL ${ \bf \nabla } { \bf * 8 }$ ::FS_LOWERLIMITREAL ${ \ast \mathbf { \delta \mathbf { 8 } } }$ : : LONREAL \*8 ::C1,C2,C3COMMON/GROUP1/C1,C2,C3FS_LOWERLIMIT $\ c =$ -ATAN(（C1 \* COS(LON) +C2 \* SIN(LON))/C3)RETURN  
END FUNCTION  
FUNCTION FS_UPPERLIMIT（LON）IMPLICIT NONEREAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ : :FS_UPPERLIMITREAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ : : LONFS_UPPERLIMIT $\ c =$ HALFPIRETURN  
END FUNCTION  
! COEFFICIENT RETURNS THREE COEFFICIENTS RELATING THE SPHERICAL COORDINATES OF ANY  
! TWO ADJACENT VERTEXES OF THE POLYGON.  
SUBROUTINE COEFFICIENT（LAT1,LON1,LAT2,LON2)IMPLICIT NONEREAL $\ast \mathbf { 8 }$ : : LAT1,LON1,LAT2,LON2REAL \*8 :: C1,C2,C3COMMON/GROUP1/C1,C2,C3（204号 $\mathbf { C } 1 \mathbf { \Psi } = \mathbf { C } \mathbf { O } \mathbf { S }$ （LAT1） \* SIN(LON1) $*$ SIN(LAT2) -COS（LAT2） \* SIN(LON2) $*$ SIN(LAT1)C2 = COS(LAT2）\*COS(LON2) $*$ SIN(LAT1) -COS（LAT1） \* COS(LON1） \* SIN（LAT2)C3 = COS（LAT1） \* COS（LAT2） \* SIN(LON2-LON1)RETURN  
END SUBROUTINE  
! THE FOLLOWING INTEGRANDS CORRESPOND SIX COMPONENTS OF THE INERTIA TENSOR.  
FUNCTION F11(LON,LAT)IMPLICIT NONER ${ \mathfrak { Q } } \mathbf { A } \mathbf { L } * \mathbf { 8 } \ : : \ \mathbf { \Omega }$ F11REAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ : : LAT,LON$\mathrm { F 1 1 } = \mathbf { C O S } ( \mathrm { L A T } ) * * 3 * \mathbf { C O S } ( \mathrm { L O N } ) * * 2$ RETURN  
ENDFUNCTION  
FUNCTION F22(LON,LAT)IMPLICIT NONERE $\mathbf { A L } * \mathbf { 8 } : : \mid$ F22REAL $^ { * 8 }$ : : LAT,LON

F22 = COS(LAT)\* \*3\*SIN(LON）\* \*2

# RETURN ENDFUNCTION

FUNCTIONF33(LON,LAT) IMPLICITNONE REAL ${ \bf \nabla } { \bf * 8 }$ ：:F33 REAL $\ast \mathbf { 8 }$ : : LAT,LON $\mathrm { F } 3 3 = \mathrm { \bf S I N } ( \mathrm { L A T } ) * * 2 * \mathrm { \bf C O S } ( \mathrm { L A T } )$ RETURN   
ENDFUNCTION   
FUNCTION F12(LON,LAT) IMPLICITNONE REAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ ：:F12 REAL $\ast \mathbf { 8 }$ : : LAT,LON $\mathrm { F 1 2 } = \mathrm { \bf C O S } ( \mathrm { L A T } ) * * 3 * \mathrm { \bf C O S } ( \mathrm { L O N } ) * \mathrm { \bf S I N } ( \mathrm { L O N } )$ RETURN   
ENDFUNCTION   
FUNCTION F13(LON,LAT) IMPLICITNONE REAL $\ast \mathbf { 8 }$ ::F13 REAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ : : LAT,LON $\mathrm { F 1 3 } = \mathrm { \bf C O S } ( \mathrm { L A T } ) * * 2 * \mathrm { \bf S I N } ( \mathrm { L A T } ) * \mathrm { \bf C O S } ( \mathrm { L O N } )$ RETURN   
ENDFUNCTION   
FUNCTION F23(LON,LAT) IMPLICITNONE REAL $^ { * 8 }$ ：:F23 STHZREAL $^ { * 8 }$ : : LAT,LON F23= COS(LAT）\* \*2\*SIN(LAT）\* SIN(LON) RETURN   
ENDFUNCTION   
！HAVERSINEFUNCTION   
FUNCTION HAV(X) IMPLICITNONE REAL $^ { * 8 }$ ：：X REAL ${ \ast \mathbf { \delta \delta \delta \delta } }$ ::HAV $\mathrm { H A V } ~ = ~ ( 1 \mathrm { D } 0 { - } \mathbf { C } \mathbf { O } \mathbf { S } ( \mathrm { X } ) ) / 2 \mathrm { D } 0$ RETURN   
ENDFUNCTION

# MORVEL构造板块的转动张量

李春晓1,2(1.中国科学院云南天文台，云南 昆明 650011；2.中国科学院大学，北京100049)

摘要：NNR-MORVEL56板块运动模型描述了全球56个构造板块在无整体旋转参考架下的角速度运动参数。这些板块可以近似描述为单位球上的无重叠球面多边形区域。用ITRF速度场计算这56个板块相对于无整体旋转参考架下的绝对运动时，板块的几何参数起着至关重要的作用。详细给出了计算板块几何参数的方法并且编写了FORTRAN90程序以供参考，使得计算单位球上板块的面积和转动惯性张量得以实现。文中的计算方法和程序主要采用球面三角算法和自适应辛普森双积分算法，并对全球56个板块的几何参数进行了计算，得到了较为可靠的计算结果。

关键词：构造板块；球面多边形；转动惯量张量；NNR-MORVEL56  
中图分类号：P183.2 文献标识码：A 文章编号：1672-7673(2016)01-0058-12