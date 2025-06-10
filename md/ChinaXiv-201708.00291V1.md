# 1 Modification on theory of sink strength: an Object 2 Kinetic Monte Carlo study

3Jie Hou $\mathbf { \Delta } _ { a , b } ^ { a , b }$ , Xiang-Shan Kong $a$ , Xiang-Yan Li $\boldsymbol { a }$ , Xuebang Wu $^ { a , * }$ , C. S. Liu $^ { a , * }$ ，   
4 Jun-Ling Chen $c$ , G.-N. Luo $c$   
5 α Key Laboratory of Materials Physics, Institute of Solid State Physics， Chinese Academy   
6 ofSciences,Hefei 230031，P.R. China   
7 （2 $b$ University of Science and Technology of China, Hefei 230026, P. R. China   
8 CInstitute of Plasma Physics, Chinese Academy of Sciences, Hefei 230031, P.R. China

# 9Abstract

10 Sink strength is a fundamental quantity in modeling the microstructure   
11 evolution of irradiated materials by the mean-field approaches. The analyti  
12 cal expressions for different sinks have been extensively studied. The Object   
13 Kinetic Monte Carlo (OKMC) simulations were subsequently performed to   
14 corroborate the expressions and to guide the development of analytical the  
15 ories. Although a general agreement was found between the theory and   
16 simulation, there are still some discrepancies in the case of the small spher  
17 ical sinks and the dislocation lines. In this work, OKMC simulations were   
18 performed to study the sink strength of spherical sinks and dislocation lines.   
19 Our results revealed the origins of discrepancies between the theory and simu  
20 lation for small sinks, high volume fraction sinks and periodically distributed   
21 dislocation lines. The theoretical corrections were also proposed according  
22 ly. These corrections can extend the capabilities of mean-field approaches to   
23 properly reproduce the defect evolution of irradiated materials, and provide   
24 a better insight into the experimental phenomena, such as the defect cluster   
25 nucleation, the irradiation-induced swelling and the blistering.

# 26 1．Introduction

27 The degradation of material properties under irradiation is a main con  
28 cern in reactor design. Under the high-energy particle irradiation, numerous   
29 mobile defects such as interstitials and vacancies are created. The clustering   
30 and aggregation of these defect are generally relevant to the the formation   
31 of blisters and voids, which leads to the degradation of materials. These mo  
32 bile defects can interact with each other and with other sinks such as grain   
33 boundaries and dislocation lines. The ability of these sinks to capture the   
34migrating defects can be quantitatively described by the sink strength that   
35was applied in mean-field approaches for simulations of defect evolution.   
36 The sink strength is proportional to the inverse square of average free   
37migration distance of defects. It is connected to the size, shape and density of   
38 sinks,as wellas the dimensionality of defect migration,i.e., three-dimensional   
39 (3D),one-dimensional (1D), or mixed 3D/1D. Based on the diffusion theory,   
401 many theoretical work has been carried out to obtain the analytical sink   
41 strength for different sinks. Brailsford and Bullough et al. have investigated   
42the expressions for the spherical sinks [1] and grain boundaries [2] under the   
43 3D limit. Similar expression for dislocations was derived by Wiedersich [3],   
44 corrected by Nichols [4],and shows a good agreement with the phase-field   
45results [5]. Theoretical sink strengths for these sinks under the 1D limit   
46were systematically investigated by Barashev et al. [6]. Recently, the Object   
47 Kinetic Monte Carlo (OKMC) method [7-9] which is expected to provide the   
48sink strengths spontaneously, has been used to corroborate these expressions   
49 and to guide the development of the theories. The OKMC simulations by   
5o Malerba and Jansson et al. [10,11] showed good agreements with analytical   
51 theory in both the 3D and 1D limits,as well as in the transition regime of   
523D to 1D diffusion. The transition region is described by a single-variable   
53 function (master-curve)，which was proposed by Trinkaus and Heinisch et al.   
54 and also confirmed by the OKMC simulations [12-15].   
55 Despite of the general agreements found between theoretical works and   
56simulations, unexplained discrepancies under certain situations have also   
57 been found in previous studies. More specifically, the OKMC simulation   
58 results always show an underestimate of the analytical sink strength for s  
59mall sinks [10,13,16],and a huge overestimate for high volume fraction sinks   
60 [10,11, 13]. An irregular discrepancy for periodically distributed dislocation   
61 lines was also pointed out[11]. Heinisch et al. [13] attributed the underesti  
62 mation to different nature between the diffusion mechanisms in OKMC and   
63 theoretical model. They thereby provided a fitted correction term，which   
64works well for the sink radii above $2 . 5 a _ { 0 }$ ( $a _ { 0 }$ is the lattice constant). How  
65ever, they did not consider the effectiveness of the correction for the smaller   
66sink( $< ~ 2 . 5 a _ { 0 }$ ， such as vacancy clusters containing about 1Oo vacancies).   
67More importantly， the corrected expression cannot describe point defects   
68 like mono-vacancy because it predicts a zero sink strength. Since OKMC   
69is a priori expected to provide the same sink strength to that provided by   
70 the diffusion theory, additional corrections should be required for OKMC or   
71mean-field simulations of defect cluster nucleation.   
72 In this work, we calculated sink strengths of different sinks through both   
73 the theoretical and OKMC approaches, for the defects characterized by a   
74varying motion dimensionality from the fully 3D limit to the pure 1D lim  
75 it. Particular cares were taken for the small sinks, the high volume fraction   
76sinks and the dislocation lines in the 1D migration limit. The theoretical   
77corrections thereof were also provided to eliminate the discrepancies men  
78tioned above. It was found that much better agreements between theory and   
79simulation can be achieved after the corrections.

# 。2.Computation method

81 An OKMC program is designed to calculate sink strengths of spherical   
82sinks and dislocation lines. The entire procedure is similar to that used in   
83refs. [10,11]. Briefly, defects and sinks are treated as objects with specific   
84positions in a simulation box and with associated reaction volumes. Proba  
85bility of a thermally activated event, such as defect migration, is given in the   
86form of Arrhenius frequency, $\Gamma _ { i } = v _ { i } e x p ( - E _ { a , i } / k _ { B } T )$ .Here $\upsilon _ { i }$ is the attempt   
87frequency for event $i$ ， $E _ { a , i }$ is the corresponding activation energy, $k _ { B }$ is the   
88 Boltzmann constant, and $T$ is the absolute temperature. An event is random  
89ly chosen according to its probability. The binary search algorithm is applied   
90here to accelerate the choosing procedure. After the event is executed, the   
91 object configuration will be updated,and the simulated time will be increased   
92acodingtoti], $\Delta \tau = 1 / ( \Sigma _ { i = 1 } ^ { N _ { i n t } } \Gamma _ { i } ^ { i n t } { + \Sigma _ { j = 1 } ^ { N _ { e x t } } \Gamma _ { j } ^ { e x t } } )$ ，   
93where $N _ { i n t }$ and $N _ { e x t }$ are the number of internal and external events, respec  
94 tively. Here, two internal events are considered, including defect migration   
95and rotation of migration direction. No external events are considered in this   
96work, i.e., $N _ { e x t } = 0$ . Note that, when two objects overlap geometrically, reac  
97tions between these two defects will take place. For instance, absorptions of   
98 a point defect take place when its distance to a sink is smaller than the sum   
9 of their capture radii. This kind of event will bring no time increment to the   
100system. During the simulation，events are chosen and executed repeatedly   
101until certain time or steps are achieved. In this work, in order to achieve   
102 a statistical convergence, simulations will not be stopped until 1Oooo point   
103 defects are absorbed.

Similar to previous works[10, 13,14], a model handles only idealised situations is implemented. In this model,a point defect with zero radius is introduced at a random position and allowed to migrate. After its absorp

107 tion,a new point defect will be introduced instantaneously so that only one   
108 point defect at a time is presented in the system. It should be pointed out   
109 that defects created inside spherical sinks or dislocation lines are not taken   
110 into account. In this way, the sink strength, $k ^ { 2 }$ , can be given by:

$$
k ^ { 2 } = { \frac { 2 n } { d ^ { 2 } < m > } } ,
$$

111 where $n$ is the dimensionality of point defect migration, which is taken as 3   
112 even for 1D migrating in order to consistently trace the transition between   
113 1D and 3D migration. $d$ is the migration distance of a point defect,which   
114 equals $\sqrt { 3 } a _ { 0 } / 2$ in bcc tungsten with lattice constant $a _ { 0 } = 0 . 3 1 6 5$ nm. $< m >$   
115 is the average number of jumps before it is absorbed by sinks. Similar to   
116 ref. [10], the dimensionality of defect motion is changed by assigning a ro  
117 tation energy $E _ { r }$ to defects,whereby the probability of changing migration   
118 direction is expressed as $\exp ( - E _ { r } / k _ { B } T )$ . One can set $E _ { r } = 0$ to acquire pure   
119 3D migration or set $E _ { r }$ to a relatively high value to get pure 1D migration   
120 ( $<$ 111> directions in tungsten). In this work, at the chosen simulation tem  
121 perature of 723 K, $E _ { r } = 1 . 5 \ \mathrm { e V }$ is enough to provide a fully 1D path,while   
122 the intermediate values are considered to give a mixed 1D/3D migration.   
123 A non-cubic periodic box with a fixed size ratio $l _ { x } : l _ { y } : l _ { z } = \frac { 1 } { \sqrt [ 4 ] { 2 } } : \sqrt [ 4 ] { 2 }$ ：   
124 1 is employed in order to correctively describe the 1D migrating of point   
125 defects [1o]. The irrational ratio of box sides was used to ensure that any   
126 super-box of this box would be non-cubic. Spherical sinks are randomly   
127 introduced in this non-cubic box with $l _ { z } = 3 5 0 \ \mathrm { n m }$ . The radius of spherical   
128 sinks, $R _ { s }$ ，varied from O.27 to 10.25 nm. And their number density, $N _ { s }$ ，   
129 varied from $1 0 ^ { - 5 }$ to $1 . 5 \times 1 0 ^ { - 4 } ~ \mathrm { { n m ^ { - 3 } } }$ for the 3D and 1D migration. For the   
130 mixed 1D/3D migration, a fixed $R _ { s } = 4 . 2 5$ nm was used and $N _ { s }$ varied from   
131 （20 $3 \times 1 0 ^ { - 5 }$ to $1 . 5 \times 1 0 ^ { - 4 } \ \mathrm { n m ^ { - 3 } }$ ． As shown in Fig. 1, the dislocation line is   
132 introduced as a cylindrical sink whose two opposite faces touch the faces of   
33 the simulation box. Only one dislocation line is introduced along $l _ { z }$ direction   
34 of the simulation box. However, under the periodic boundary condition, this   
35model is practically equivalent to a regular array of infinitely long dislocation   
36 lines. Different surface densities can be obtained by changing the box size.   
37Here, $l _ { z }$ varied from 15 to 45 nm while keep the size ratio fixed, corresponding   
38 to surface densities from $5 \times 1 0 ^ { - 4 }$ to $4 . 5 \times 1 0 ^ { - 3 } ~ \mathrm { { n m ^ { - 2 } } }$ . The dislocation radius   
39used here, $R _ { d }$ ，varied from 0.25 to $1 0 ~ \mathrm { { n m } }$ . Some large $R _ { d }$ are not used for   
40 small boxes due to the box size limit,and some small ones are not used for   
41 large boxes owing to the computational time limit.

# 3.Results and discussion

# 3.1. Spherical sinks

# 3.1.1. Results without any correction

The analytical sink strength of spherical sinks under 3D migration limit is given by [1]:

$$
k _ { 3 , s } ^ { 2 } = 4 \pi R _ { s } N _ { s } ( 1 + k _ { 3 , s } R _ { s } ) .
$$

This equation is usually solved by the iterative method. The $n ^ { t h }$ order of   
148 iterative result is calculated by $k _ { 3 , s , n } ^ { 2 } = 4 \pi R _ { s } N _ { s } ( 1 + k _ { 3 , s , n - 1 } R _ { s } )$ , with the first   
149 order given as $k _ { 3 , s , 1 } ^ { 2 } = 4 \pi R _ { s } N _ { s }$ As proposed byprevious worki   
necessary to use high orders of iterative approximation for a good agreement   
151 between the theoretical expression and the OKMC simulation. For Eq. (2),   
152 the larger the $R _ { s }$ is,the poorer the convergence will be. Even so,as shown in   
153 Fig. 2, for the largest $R _ { s } = 1 0 . 2 5$ nm used in this work, a good convergence   
154 is already achieved at the third order approximation. In this work, the fifth   
155 order approximation is adopted for all calculations using Eq. (2)，and for   
156 similar equation Eq. (4). In the case of 1D migrating defects, expression of

157 the sink strength is given by [6]:

$$
k _ { 1 , s } ^ { 2 } = 6 ( \pi R _ { s } ^ { 2 } N _ { s } ) ^ { 2 } .
$$

158 In our OKMC simulations, spherical sinks were introduced randomly but   
159 without overlap with each other. Under the 3D migration limit, the radius   
160 of spherical sink, $R _ { s }$ ，varied from 0.27 to 10.25 nm (0.27, 0.75, 1.25, 2.25,   
161 4.25,6.25,8.25,and 10.25 nm)，and their number density, $N _ { s }$ ， varied from   
162 （20 $3 \times 1 0 ^ { - 5 }$ to $1 5 \times 1 0 ^ { - 5 } \mathrm { n m ^ { - 3 } }$ (1.0, 3.0, 6.0, 9.0, 1.2, and $1 5 . 0 \times 1 0 ^ { - 5 } \mathrm { n m ^ { - 3 } }$ ). The   
163 two highest densities were not considered when $R _ { s } = 1 0 . 2 5 ~ \mathrm { n m }$ 1， because of   
164 the limitation of non-overlap. For the 1D migration limit, it is impossible to   
165 produce all the data points explored in the 3D case owing to computational   
166 time reasons. The same densities to the 3D case are all taken into account   
167 for $R _ { s } > 4 . 2 5 ~ \mathrm { n m }$ .While only one number density ( $N _ { s } = 1 0 ^ { - 3 } ~ \mathrm { { n m ^ { - 3 } } }$ is   
168 considered when $R _ { s } < 4 . 2 5$ nm (0.75, 1.25, 1.75, 2.25, 2.75, 3.25 and 3.75   
169 nm).   
70 Fig. 3 presents results of sink strength under the 3D and 1D migration   
71 limits. Similar to previous studies [10,13],a general agreement is found   
72 between analytical theory and simulation. Whereas two significant discrep  
73ancies can also be identified for small sinks under the 3D limit and for the   
74 high volume fraction sinks. These discrepancies can be clearly displayed by   
75relative errors, defined as the percentage ratio of simulated-analytical sink   
76strength difference to analytical sink strength, i.e., $( k _ { s i m } ^ { 2 } - k _ { a n a } ^ { 2 } ) / k _ { a n a } ^ { 2 } \times 1 0 0 \%$ ：   
77 As shown in Fig. 4(a), the simulated sink strength is about $3 3 \%$ lower than   
78 the analytical one for the smallest sink under the 3D migration limit. Mean  
79 while,errors for the same sink radius are close. This indicates that the sink   
80 radius is the key variable of such errors. However, for the 1D limit that   
81 shown in Fig. 4(b)，similar errors for small sinks are not observed. With   
82 the growing of sink radius,in the volume fraction range of $1 0 ^ { - 4 } \sim 1 0 ^ { - 1 }$ ， the

relative error reduces to nearly zero in both cases, suggesting a good agreement between theoretical works and simulations. When the volume fraction is above $1 0 ^ { - 1 }$ , the relative error grows very rapidly with the increase of sink volume fraction. This implies a large discrepancy between theory and simulation data. In order to eliminate the discrepancies, further investigations and additional corrections are required.

# 3.1.2. Correction for small sinks

The discrepancy for small sinks under the 3D migration limit is often attributed to different nature of diffusion mechanisms between the theory and the OKMC simulation [13, 16]. As shown in Fig. 5(a). For the theoretical model, the diffusion is a continuous process, where point defects are absorbed exactly at the sink surface. For the OKMC simulation, the diffusion is a discrete process composed of a series of individual hops, where the absorption takes place when a defect jumps into the sink. Since the jump distance $d$ is not zero, point defects in OKMC simulation can penetrate into the sink. The penetration area is not an ideal spherical surface but a spherical shell (gray area in Fig. $5 ( \mathrm { a } )$ ). Therefore, $R _ { s }$ in the Eq. (2） should be revised by adding a correction term $\Delta R$ ：

$$
k _ { 3 , s } ^ { 2 } = 4 \pi ( R _ { s } + \Delta R ) N _ { s } [ 1 + k _ { 3 , s } ( R _ { s } + \Delta R ) ] .
$$

201 Here, $R _ { s } + \Delta R$ , is denoted by $R _ { e f f }$ , namely the effective radius of the sink.   
202 For the 3D limit, the thickness of the penetration area in the OKMC   
203 model is the jump distance $d$ . Since the sink strength of spherical sinks varies   
204 linearly with the radius for small sinks,the correction term $\Delta R$ should be   
205 weighted average of the penetration depth $p$

$$
\Delta R = - \overline { { p } } = \overline { { r - R _ { s } } } ,
$$

206 where $r = R _ { s } - p$ is the distance to sink center. For a certain $r$ , its possible   
207 start point (red dot) of the last jump falls on a spherical cap surface with   
208radius $d$ centered at destination point (black dot). Form $r$ to $r + \mathrm { d } r$ , the pos  
209 sible start point is given by shifting the spherical cap surface by ${ \mathrm { d } } r$ (shadow   
210area in Fig. 5(a)). The volume of this area is given by the differential of   
211spherical cap volume[18]:

$$
\mathrm { d } V = \pi { \frac { d ^ { 4 } + ( r ^ { 2 } - R _ { s } ^ { 2 } ) ^ { 2 } - 2 d ^ { 2 } ( r ^ { 2 } + R _ { s } ^ { 2 } ) } { 4 r ^ { 2 } } } \mathrm { d } r .
$$

212 The correction term is given by:

$$
\Delta R = \overline { { r - R _ { s } } } = \frac { \int _ { R _ { s } - d } ^ { R _ { s } } ( r - R _ { s } ) 4 \pi r ^ { 2 } \frac { \mathrm { d } V } { \mathrm { d } r } \mathrm { d } r } { \int _ { R _ { s } - d } ^ { R _ { s } } 4 \pi r ^ { 2 } \frac { \mathrm { d } V } { \mathrm { d } r } \mathrm { d } r } ,
$$

213 where $4 \pi r ^ { 2 } { \frac { \mathrm { d } V } { \mathrm { d } r } } \mathrm { d } r$ represents the set of start points that can jump to a spherical   
214shell between $r$ and $r + \mathrm { d } r$ ， namely, the weight of $r$ . Substituting Eq. (6)   
215 into Eq. (7),we have:

$$
\Delta R = - \frac { 5 d ^ { 2 } + 1 6 d R _ { s } - 3 0 R _ { s } ^ { 2 } } { 1 6 d ^ { 2 } + 3 0 d R _ { s } - 8 0 R _ { s } ^ { 2 } } d .
$$

By substituting this correction term into Eq. (4),we calculated percentage errors after the effective radius correction. The modified sink strength and its corresponding relative error are calculated and summarized in Fig. 6. It clearly shows that that discrepancies for small sinks are perfectly removed after the effective radius correction.

We also noticed that there is no discrepancy for small sinks under 1D limit. This can be understood as follows. As shown in Fig. 5(b),under 1D migration limit, the sink strength is connected to the biggest cross-section of the sink perpendicular to the migration direction. Under the continuous diffusion mechanism, point defects are absorbed exactly at the sink surface. Therefore, the radius of the biggest cross-section is equal to the sink radius

$R _ { s }$ . While in the OKMC simulation，as stated before, point defects can penetrate into the sink. The penetration area here is the gray area between the two spherical surfaces separated by $d$ in the migration direction. $R _ { e f f }$ （20 is thereby given by the radius of the biggest cross-section of the penetration area. Since defects penetrate along the migration direction， $R _ { e f f }$ is also equal to $R _ { s }$ . In this way, the discrete diffusion mechanism will not change the effective radius $R _ { e f f }$ ，and the correction term $\Delta R = 0$ ：

# 3.1.3. Correction for high volume fraction sinks

The discrepancy at the high sink volume fraction region is likely a result of different sink configurations. In the OKMC simulation， sinks are randomly distributed in the simulation box and do not overlap with each other(non-overlap configuration). While in the theoretical model with the mean-feld approximation, sinks are considered to be randomly and uniformly distributed in the system without taking care to avoid the overlapping between sinks (overlap configuration). In order to verify this speculation, we also constructed an overlap configuration in the OKMC simulation. The sink strengths under this configuration are calculated and their corresponding relative error is presented in Fig. 7. Compared with Fig. 4, the relative error becomes nearly zero throughout the considered range, which supports our hypothesis about the sink configurations.

The distinct behaviors between two configurations are likely to originate from the sink volume fractions. For the non-overlapping configuration,its volume fraction $f _ { v }$ is given by:

$$
f _ { v } = 4 \pi R _ { s } ^ { 3 } N _ { s } / 3 .
$$

250 Due to the overlap between sinks, this formula does not apply to the overlap   
251 configuration. In the overlap configuration, a larger sink density $N _ { s , l a p } > N _ { s }$ （204号   
252 is required to occupy the same $f _ { v }$ to the non-overlap configuration. In this   
253 case,we define a dummy volume fraction that given by simply summing all   
254sinks without caring about the overlap:

$$
F _ { v } = 4 \pi R _ { s } ^ { 3 } N _ { s , l a p } / 3 .
$$

255 The relationship between $f _ { v }$ and $F _ { v }$ is given by differential equations:

256

$$
f _ { v } ( F _ { v } + \mathrm { d } F _ { v } ) = f _ { v } ( F _ { v } ) + [ 1 - f _ { v } ( F _ { v } ) ] \mathrm { d } F _ { v } ,
$$

$$
F _ { v } \left( f _ { v } = 0 \right) = 0 ,
$$

257 where $1 - f _ { v } ( F _ { v } )$ represents the volume fraction of unoccupied regions. So  
258 lution of these two equations is:

$$
F _ { v } = \ln { \frac { 1 } { 1 - f _ { v } } } .
$$

259 With this relationship,we find that the error function fits best with the   
260 relative error at the high volume fraction of Fig. 4(b) and Fig. 6(b) is given   
261 by:

$$
e = { \frac { F _ { v } ^ { 4 } - f _ { v } ^ { 4 } } { f _ { v } ^ { 4 } } } = { \frac { ( \ln { \frac { 1 } { 1 - f _ { v } } } ) ^ { 4 } - f _ { v } ^ { 4 } } { f _ { v } ^ { 4 } } } .
$$

262 In the low volume fraction region, the probability of overlap is very low,   
263 and $F _ { v } ^ { \prime }$ is practically equal to $f _ { v }$ . Therefore, the relative error arising from the   
264sink distribution is invisible. However,as the volume fraction increases, the   
265 overlap probability grows very rapidly. Therefore, the relative error becomes   
266 significantly large at the high volume fraction region. It should be pointed   
267 out that the overlap configuration is unrealistic in real materials, because $F _ { v }$   
268 can exceed $1 0 0 \%$ . In order to handle the defect interaction under the high   
269 sink volume fractions,according to Eq. (14), the theoretical sink strengths   
270 need to be corrected by multiplying a coeffcient $\Big ( \frac { \ln { \frac { 1 } { 1 - f _ { v } } } } { f _ { v } } \Big ) ^ { 4 }$

In addition, in the previous work of sink strength theory[1], Brailsford et al. pointed out an intrinsic part of their method is that the sample volume must be large compared with the inter-sink spacing in random arrays. This implies that the theoretical work is premised on the assumption of low sink volume fraction. Therefore, the additional correction for the high volume fraction sink should be reasonable.

# 3.1.4. Transition from 3D to 1D regime

The sink strength of spherical sinks for the mixed 1D/3D migration, $k _ { 1 - 3 , s } ^ { 2 }$ ，canb tween the 1D and 3D limiting cases, i.e.,

$$
y = \frac { 1 } { 2 } ( 1 + \sqrt { 1 + 4 / x ^ { 2 } } ) ,
$$

281 where $y$ and $x$ are two dimensionless variables. In the OKMC simulation, $y$ （20   
282and $x$ are defined as:

283

$$
y = k _ { 1 - 3 , s } ^ { 2 } / k _ { 1 , s } ^ { 2 } ,
$$

$$
x = \frac { l _ { c h } ^ { 2 } k _ { 1 , s } ^ { 2 } } { 1 2 } + \frac { k _ { 1 , s } ^ { 4 } } { k _ { 3 , s } ^ { 4 } } ,
$$

where $l _ { c h } = d \sqrt { \exp ( E _ { r } / k _ { B } T ) }$ is the average migration length between two direction changes.

In Fig. 8(a), the simulated sink strengths of different densities of sinks under the mixed 1D/3D limit are plotted as a function of rotation the energy $E _ { r }$ All simulations are conducted under the non-overlap configuration.Because we do not know the effective radius correction $\Delta R$ under this situation, the radius of sinks is chosen to be 4.25 nm,which is large enough to avoid the error introduced by effective radius change and also small enough to avoid the error from the overlap configuration. Sink density $N _ { s }$ varies from $3 \times 1 0 ^ { - 5 }$ （204号 to $1 . 5 \times 1 0 ^ { - 4 } ~ \mathrm { { n m ^ { - 3 } } }$ . As we can see, the sink strength smoothly transits from

94 3D to 1D migrating with the increasing $E _ { r }$ . And a rotation energy of 1.5   
95eV is high enough to ensure a pure 1D migration. The master-curve defined   
6 by Eq. (15) is illustrated in Fig. 8(b). Here we find that the analytical   
7master-curve is in a perfect agreement with our simulated data.

# 3.2. Dislocation lines

According to the previous study [11], the theoretical sink strength of the 3D and 1D migration defects being absorbed by dislocation lines are [3, 4, 6]:

$$
k _ { 3 . d } ^ { 2 } = \frac { 2 \pi \rho _ { d } ( 1 - \pi \rho _ { d } R _ { d } ^ { 2 } ) } { 0 . 2 5 \pi \rho _ { d } R _ { d } ^ { 2 } ( 4 - \pi \rho _ { d } R _ { d } ^ { 2 } ) - 0 . 7 5 - \ln { ( R _ { d } \sqrt { \pi \rho _ { d } } ) } } ,
$$

301 and

$$
k _ { 1 . d } ^ { 2 } = 6 \times \left( \pi R _ { d } \rho _ { d } \right) ^ { 2 } ,
$$

respectively. Here, $R _ { d }$ represents capture radius of the dislocation line, $\rho _ { d } =$ （204号 $l _ { z } ^ { - 2 }$ is its surface density. Its volume fraction is given by $f _ { v } = \pi R _ { d } ^ { 2 } \rho _ { d }$

# 3.2.1. 3D limit

5 Fig. 9(a) shows the sink strengths of dislocation lines under 3D migration 06 limit. Similar to the situation of spherical sinks,a good agreement between D7 simulation and theory is found but two discrepancies appear for dislocations 08 with small $R _ { d }$ and with high volume fraction. The former discrepancy arises 09 from the difference between diffusion mechanisms,which are continuous in L0 the theory while discrete in the OKMC. This discrepancy can be well reconl ciled by introducing the effective radius correction to Eq. (18). The corrected l2equation is given by:

$$
k _ { 3 , d } ^ { 2 } = \frac { 2 \pi \rho _ { d } [ 1 - \pi \rho _ { d } ( R _ { d } + \Delta R ) ^ { 2 } ] } { \frac { 1 } { 4 } \pi \rho _ { d } ( R _ { d } + \Delta R ) ^ { 2 } [ 4 - \pi \rho _ { d } ( R _ { d } + \Delta R ) ^ { 2 } ] - \frac { 3 } { 4 } - \ln { [ ( R _ { d } + \Delta R ) \sqrt { \pi \rho _ { d } } ] } } .
$$

313 Similar to Eq. (2), Eq. (18) is approximately a linear function of $R _ { d }$ when   
314 $R _ { d }$ is small. Therefore,the correction term $\Delta R$ should be similar to that

for spherical sinks. A detailed derivation of $\Delta R$ is a little bit tedious. For simplicity, we shall use the $\Delta R$ from Eq. (8)(simply replace $R _ { s }$ with $R _ { d }$ ） As shown in Fig. 9(b)，after the effective radius modification, the relative error in the low volume fraction region becomes nearly zero. On the other hand, the discrepancy at the high volume fraction cannot be explained as we discussed for the spherical sinks. This might be because that the analytical expression is based on an assumption that $\rho _ { d }$ is a small value, i.e., the low sink volume fraction. And the periodic boundary condition，which might cause an interplay between vicinal dislocations, is obviously not included in the theoretical model. Since such discrepancy is not obvious until the volume fraction is higher than O.1, this is acceptable because the typical value in real materials is usually much smaller than 0.1.

# 3.2.2. 1D limit and the influence of the periodic configuration

Fig. 1O (a) and (b） show the sink strength and the relative error for dislocation lines under the 1D limit, grouped by dislocation surface densities. No effective radius correction is required here owing to the similar reason shown in the Fig. 5(b). The agreement between simulation and theory is less satisfactory than the 3D limit. Similar to the case of spherical sinks, a rapid growth of the relative error is also observed in the high volume fraction region, which can be described by Eq. (14). This indicates that the theoretical expression is also based on the overlap configuration. This significant error at the high volume fraction region can be eliminated by multiplying a coefficient $\Big ( \frac { \ln { \frac { 1 } { 1 - f v } } } { f _ { v } } \Big ) ^ { 4 }$ to the right side of Eq. (19).

Figure. 1O(c) shows the relative error after the correction. All data are positive and show a zigzag behavior as a function of the sink volume fraction. These positive errors may origin from a truncation of the tail of very long distance migration before absorption. Namely, in a completely

342 random distribution of dislocations, free migration distance of point defects   
343before its absorption should follow an exponential distribution [6]:

$$
P ( L ) = \pi R _ { d } \rho _ { d } \exp ( - \pi R _ { d } \rho _ { d } L ) ,
$$

where $L$ is the free migration distance and $P ( L )$ is its probability density. Any positive $L$ can be achieved with a positive probability density in such configuration. However, in a periodic dislocation configuration， such very long distance migrations are cut out. Fig. 11 shows a sketch of this cuttail effect. In a periodically extended simulation box, 1D migration defects cannot travel to a distance longer than $L _ { c u t 1 }$ . Meanwhile, we also find that the cutoff distance $L _ { c u t }$ does not vary continuously with $R _ { d }$ . A slight reduction of the dislocation radius from $R _ { d 1 }$ to $R _ { d 2 }$ might cause a mutation of the cutoff distance ( $L _ { c u t 1 }$ to $L _ { c u t 2 }$ ). Such cut-tail effect will reduce the average migration distance,which consequently causes an overestimate of the theoretical sink strength. Therefore, the mutation of the cutoff distance is responsible for the zigzag behavior of relative errors.

356 Figure $1 2 ( \mathrm { a } )$ shows the cutoff distance in OKMC, $\ L _ { c u t }$ ，as a function of   
357 the sink volume fraction. The average migration distance, $\overline { { L } } = ( \pi R _ { d } \rho _ { d } ) ^ { - 1 }$ [6],   
358 calculated from Eq. (21) is also plotted for comparisons. With an increase of   
359 the volume fraction, the cutoff distance decreases step by step like a staircase.   
360 The ratio of $\ b { L _ { c u t } }$ to $\overline { { L } }$ is shown in Fig. 12(b). Four high peaks and four low   
361 peaks can be clearly distinguished here. Each of them represents a mutation   
362 of the cutoff distance. The high peaks in Fig. 12(b) correspond to four   
363 main peaks of relative error in Fig. 1O(c) (labeled with green vertical lines),   
364 while the low peaks correspond to four shoulder peaks of relative error in   
365 Fig. 1O(c) (blue vertical lines). Although we are aware of the origin of these   
366 error peaks,it is still very diffcult to build a complete random configuration   
367 to eliminate them. More studies are required in the future to achieve a

consistency between theory and OKMC simulation.

Note that, our results are different from the previous work by Jansson et al. [11], where the relative error tends to be negative in the low volume fractions,but positive in the high volume fraction region. This difference is likely contributed to the different simulation box we used. In our work, the ratio of box sides perpendicular to the dislocation is an irrational number, $l _ { x } : l _ { y } = \sqrt { 2 }$ . While in the previous simulation, the ratios are rational numbers. It has been pointed out [1O] that in order to prevent endless migrations of 1D point defects,a non-cubic (non-square in this situation） box is instrumental to simulate correctly the 1D migrating defects. However,a box with a rational ratio, for instance $l _ { x } : l _ { y } = 4 0 0 a _ { 0 } : 3 5 0 a _ { 0 }$ ， is equally a square super-box with $L _ { x } : L _ { y } = 7 l _ { x } : 8 l _ { y } = 2 8 0 0 a _ { 0 } : 2 8 0 0 a _ { 0 }$ . The square super-box cannot completely prevent the endless migrations from happening in low sink volume fraction region. Once an endless migration is started, the point defect cannot be absorbed until the simulation is halted manually. This should be restrictively forbidden because it would increase the free migration distance unpredictively, and lead to a negative relative error in the low volume fraction region.

# 3.2.3. Transition from 3D to 1D regime

The transition between 3D migrating and 1D migrating is illustrated in Fig. 13(a). The capture radii were carefully chosen to ensure the volume fraction $f _ { v } = 0 . 0 0 5$ and $f _ { v } = 0 . 0 3$ . Because the simulation results fit very well with the theory for both 3D and 1D migrating at these volume fractions. The transition is more abrupt compared to the simulation of spherical sinks. The 1D regime is already reached at $E _ { r } = 1 . 0$ eV.Meanwhile, in the mastercurve representation (Fig. 13(b)), the simulation always gives a lower value than the analytical one in the 3D migrating region. This was also found in the previous study [11]. However, unlike their results, we find that the simulation data of the same volume fraction collapse onto the same curve, which indicates that the volume fraction should be the key variable of this discrepancy.

# 4.Conclusion

We performed a series of OKMC simulations to study the sink strengths of spherical sinks and dislocation lines with different radii and volume fractions. The simulation results were compared with the theoretical expressions derived from diffusion theory to evaluate the validity of these expressions, and further, to modify these expressions.

For the small sinks, the discrepancy between the diffusion theory and simulation is caused by the different migration distances used in these two methods. This can be resolved by adding a correction term to the effective radius of sinks. For the high volume fraction sinks, the discrepancy is attributed to different sink configurations in two methods. It can be eliminated by introducing a compensation term of sink volume fraction to the theoretical expressions. For dislocation lines under the 1D migration limit,a zigzag like discrepancy is found. It is caused by the periodic distribution of dislocation lines adopted in OKMC.

Based on these results, the origins of the above discrepancies have been revealed and successfully resolved. This can extend the capability of mean-field approaches to properly reproduce the defect evolution of irradiated materials,and provide a better insight into experimental phenomena, such as the defect cluster, the irradiation-induced swelling and the blistering.

# 19 Acknowledgement

This work was supported by the National Magnetic Confinement Fusion Program (Grant No.: 2015GB112001), the National Natural Science Foundation of China (Nos.: 11505229,11575229,11375231)， the Youth Innovation Promotion Association of CAS (2015384)，and by the Center for Computation Science, Hefei Institutes of Physical Sciences.

425 [1] A.D. Brailsford, R. Bullough, Philos. Trans. R. Soc.London. 302 (1981)   
426 87 - 137.   
427 [2] R. Bullough, M. R. Hayns, M. H. Wood, J. Nucl. Mater. 90 (1980) 44 -   
428 59.   
429 [3] H. Wiedersich,Radiat. Eff.12(1972) 111 - 125.   
430 [4] F. A. Nichols, J. Nucl. Mater. 75 (1978) 32 - 41.   
431 [5] H.Rouchette, L. Thuinet,A. Legris,A.Ambard, C. Domain,Comput.   
432 Mater. Sci. 88 (2014) 50 - 60.   
433 [6] A.V. Brarshev, S. I. Golubov, H. Trinkaus,Philos. Mag. A 81 (2001)   
434 2515 - 2532.   
435 [7] M. J. Caturla,N. Soneda, E. Alonso, B. D. Wirth,T. Diaz de la Rubia,   
436 J. M. Perlado, J. Nucl. Mater. 276 (2000) 13 - 21.   
437 [8] N. Soneda, S. Ishino,A. Takahasi, K. Dohi, J. Nucl. Mater. 323 (2003)   
438 169 - 180.   
439 [9] C. Domain, C.S. Becquart,L. Malerba, J. Nucl. Mater. 335 (2004) 121   
440 - 145.   
441[10] L. Malerba, C. S. Becquart, C. Domain, J. Nucl. Mater.360 (2007) 159   
442 - 169.   
443[11] V. Jansson, L. Malerba, A. De Backer, C. S. Becquart, C. Domain, J.   
444 Nucl. Mater. 442(2013) 218 - 226.   
445[12] H. Trinkaus,H.L. Heinisch,A. V. Barashev, S. I.Golubov, B.N. Singh,   
446 Phys. Rev. B 66 (2002) 060105.   
447[13] H. L. Heinisch, B. N. Singh,S. I. Golubov, J. Nucl. Mater. 283 - 287   
448 (2000) 737 - 740.   
449[14] H. L. Heinisch,B.N. Singh，Philos.Mag.83(31-34) （2003） 3661 -   
450 3676.   
451[15] H. L. Heinisch, H. Trinkaus,B. N. Singh, J. Nucl. Mater. 367 - 370   
452 (2007) 332 - 337.   
453[16] R. E. Stoller, S. I. Golubov, C. Domain, C. S. Becquart, J. Nucl. Mater.   
454 382 (2008) 77 - 90.   
455[17] W. Young, E. Elcock,Proc. Phys. Soc.89(1966) 735.   
456[18] R. Panvani, G.Ranchino, Comput. Chem. 6 (1982） 133 - 135.   
457 Figure caption:   
458 Figure 1 Schematic of the non-cubic box and the dislocation line model in   
459 OKMC. The periodic boundary condition is applied in all three dimensions.   
460 Figure 2(color online) The first to the fifth iterative order approximation   
461 of Eq. (2). Here, the largest sink radius of our simulations, $R _ { s } = 1 0 . 2 5 ~ \mathrm { n m }$ 1’   
462is used for convergence test. The sink volume fraction is given by $f _ { v } \ =$   
463 $4 \pi R _ { s } ^ { 3 } N _ { s } / 3$ ，where $N _ { s }$ is the number density of spherical sinks.

Figure 3(color online) Sink strength of spherical sinks with different radii versus sink volume fraction, lines are results of Eq. (2） and Eq. (3)，dots are the corresponding simulated results. (a) and (b) represents 3D migration and 1D migration limit, respectively.

Figure 4(color online) The relative error between theoretical and simulated sink strength that presented in Fig. 3. (a） and (b) represents 3D migration and 1D migration limit, respectively. The solid line represents the error estimated by Eq. (14).

Figure 5(color online) Schematics of a point defect being absorbed by a spherical sink under two different diffusion mechanisms. The gray area represents the penetration area in OKMC simulation. (a) 3D migration limit. The effective radius, $R _ { e f f }$ , is the weighted average of the penetration depth $p$ Shadow area represents possible start points those can jump into the segment from $r$ to $r + \mathrm { d } r$ ; (b）1D migration limit. $R _ { e f f }$ is the radius of the biggest cross-section perpendicular to the migration direction of the penetration area, which equals sink radius $R _ { s }$ in this case.

Figure 6(color online) Results of 3D migration defects absorbed by spherical sinks with different radii, theoretical values are calculated by Eq. (4) with （204号 $\Delta R$ from Eq. (8). (a) sink strength from simulation (dots) and the theoretical expression (lines). (b) the relative error between simulation and the theoretical expression, solid line represents the error estimated by Eq. (14). Figure 7(color online) The relative error between theoretical (by Eq. (4) with $\Delta R$ from Eq. (8)，and by Eq. (3)） and simulated sink strength of spherical sinks,under a configuration that sinks are allowed to overlap without any reaction takes place. (a) and (b） represents 3D migration and 1D migration limits, respectively.

Figure 8(color online) The transition from 3D to 1D migration limit for 4.25 nm spherical sinks，grouped by sink densities.(a) simulated sink strength as a function of rotation energy, with temperature $T \ = \ 7 2 3$ K. (b) the master-curve representation, the solid line represents the theoretical relationship of x and y in Eq. (15), dots are the simulation results elaborated according to Eqs. (16) and (17).

Figure 9(color online) Results of 3D migration defects absorbed by dis location lines, grouped by box sizes with a fixed ratio. (a) sink strength from simulation (empty dots） and theoretical expression (dotted and solid lines are the results from Eqs. (18) and (2O),respectively). (b) the relative error between simulation and theoretical expression (empty and solid dots are the results using Eqs. (18) and (20), respectively).

Figure 1O(color online) Results of 1D migration defects absorbed by dislocation lines,grouped by box sizes with a fixed ratio. (a) sink strength from simulation (empty dots) and theoretical expression (solid lines). (b) the relative error between simulation and theoretical expression， the solid line represents the error estimated by Eq. (14). (c) data obtained by removing the error described by Eq. (14) from (b). Vertical lines are the corresponding position of mutation peaks in Fig. 12(b).

Figure 11(color online) Schematics of 1D migration in a periodically extended simulation box in OKMC, picture is taken perpendicular to the direction of dislocation lines. Two kinds of round circles represent dislocation lines with different radii. The furthest migration distance, namely the cutoff distance, is labeled by $L _ { c u t 1 }$ and $L _ { c u t 2 }$ . Dislocations with radius $R _ { d 1 }$ (left) corresponding to a cutoff distance of $L _ { c u t 1 }$ ， while a slightly reduction of the dislocation radius from $R _ { d 1 }$ to $R _ { d 2 }$ (right） will cause a mutation of the cutoff distance from Lcut1 to Lcut2 .

Figure 12(color online) (a) the mutation of the cutoff distance (in the unit of box size $l _ { z }$ ）， $\ L _ { c u t }$ , of 1D migration as the function of volume fraction, compared with the average migration distance, $\overline { { L } }$ , obtained from Eq. (21). (b) the ratio of $L _ { c u t }$ to $\overline { { L } }$ ， each peak represents a mutation of the cutoff distance. Four high peaks corresponding to the four main peaks of relative error in Fig. 1O(c), while the four lower peaks corresponding to four shoulder peaks of relative error in Fig. 10(c).

Figure 13(color online) The transition from 3D to 1D migrating sink strength of point defects absorbed by dislocation lines, grouped by box sizes, where the volume fraction of sinks is fixed at $f _ { v } ~ = ~ 0 . 0 0 5$ and $f _ { v } ~ = ~ 0 . 0 3$ (denoted by empty and solid dots, respectively). (a) simulated sink strength as a function of rotation energy, with temperature $T = 7 2 3$ K. (b) the mastercurve representation, solid line represents the theoretical relationship of x and y in Eq. (15)，dots are the simulation results elaborated according to Eqs. (16) and (17).

![](images/095c89e33e7da3bb1bde6a98fe949bd17419f58414a63d48f0c3b7102895c56f.jpg)  
Figure 1: Schematic of the non-cubic box and the dislocation line model in OKMC.The periodic boundary condition is applied in all three dimensions.

![](images/071fdcfd9f863472c09d1fbe00cc8e231eba87c4a878588b8900276ac367a2bc.jpg)  
Figure 2: (color online) The first to the fifth iterative order approximation for sink strength from Eq. (2). Here, the largest sink radius of our simulations, $R _ { s } = 1 0 . 2 5 ~ \mathrm { n m }$ , is used for convergence test. The sink volume fraction is given by $f _ { v } = 4 \pi R _ { s } ^ { 3 } N _ { s } / 3$ ，where $N _ { s }$ is the number density of spherical sinks.

![](images/a4e084969026a3a0e5829f112369baab5f2d493d96974c273ebae2adb36407d9.jpg)  
Figure 3: (color online) Sink strength of spherical sinks with different radii versus sink volume fraction,lines are results of Eq. (2) and Eq. (3), dots are the corresponding simulated results.(a) and (b) represents 3D migration and 1D migration limit,respectively.

![](images/d19d71bcb6e731f7dac04af8dd812da4f3d5208e1b4d874917e7ccd00fcbb372.jpg)  
Figure 4: (color online) The relative error between theoretical and simulated sink strength that presented in Fig. 3. (a) and (b) represents 3D migration and 1D migration limit, respectively. The solid line represents the error estimated by Eq. (14).

![](images/6dc2c6680097f630596cab12c135be70a1fef5f089029a8c4405ef853ec48376.jpg)  
Figure 5: (color online) Schematics of a point defect being absorbed by a spherical sink under two different diffusion mechanisms. The gray area represents the penetration area in OKMC simulation. (a) 3D migration limit. The effective radius, $R _ { e f f }$ , is the weighted average of the penetration depth $p$ .Shadow area represents possible start points those can jump into the segment from $r$ to $r + \mathrm { d } r$ ;(b)1D migration limit. $R _ { e f f }$ is the radius of the biggest cross-section perpendicular to the migration direction of the penetration area, which equals sink radius $R _ { s }$ in this case.

![](images/ba2e809cceb3f8995f500c242345e8620f927a695a73f538bcf6e505afcdee82.jpg)  
Figure 6: (color online) Results of 3D migration defects absorbed by spherical sinks with different radii, theoretical values are calculated by Eq. (4) with $\Delta R$ from Eq. (8). (a) sink strength from simulation (dots) and the theoretical expression (lines). (b） the relative error between simulation and the theoretical expression，solid line represents the error estimated by Eq. (14).

![](images/f74ab85e9628461cc4c8e286b90f8c863ec5f66a3965f2fa86ac6bf0e565d8f9.jpg)  
Figure 7: (color online） The relative error between theoretical (by Eq.(4） with $\Delta R$ （204 from Eq. (8),and by Eq. (3)) and simulated sink strength of spherical sinks,under a configuration that sinks are allowed to overlap without any reaction takes place. (a) and (b) represents 3D migration and 1D migration limits,respectively.

![](images/c57b5f75ec27f469adaabc3849497a411431ee1ee4ea5ba39a1654e0aaeeb8a8.jpg)  
Figure 8: (color online) The transition from 3D to 1D migration limit for 4.25 nm spherical sinks,grouped by sink densities. (a) simulated sink strength as a function of rotation energy,with temperature $T = 7 2 3 \mathrm { ~ K ~ }$ .(b）the master-curve representation, the solid line represents the theoretical relationship of x and y in Eq. (15),dots are the simulation results elaborated according to Eqs. (16) and (17).

![](images/0f8a5fadc153869ec581f6207b9b6593fce7d481de9773b4a2f09eb1ca40480a.jpg)  
Figure 9: (color online） Results of 3D migration defects absorbed by dislocation lines, grouped by box sizes with a fixed ratio. (a) sink strength from simulation (empty dots) and theoretical expression (dotted and solid lines are the results from Eqs. (18) and (20), respectively). (b) the relative error between simulation and theoretical expression (empty and solid dots are the results using Eqs. (18) and (20),respectively).

![](images/db59bef686227364c66225544e1420f0f51e76dd38bf01e7c57977992a7a44d1.jpg)  
Figure 10: (color online) Results of 1D migration defects absorbed by dislocation lines, grouped by box sizes with a fixed ratio. (a) sink strength from simulation (empty dots) and theoretical expression (solid lines). (b) the relative error between simulation and theoretical expression, the solid line represents the error estimated by Eq. (14). (c) data obtained by removing the error described by Eq. (14) from (b). Vertical lines are the corresponding position of mutation peaks in Fig. 12(b).

![](images/5765100553506c362a9bbf51cc89e8b44364349ccb1787ce02756137519115f6.jpg)

Figure 11: (color online) Schematics of 1D migration in a periodically extended simulation box in OKMC,picture is taken perpendicular to the direction of dislocation lines. Two kinds of round circles represent dislocation lines with different radii. The furthest migration distance, namely the cutoff distance, is labeled by $L _ { c u t 1 }$ and $L _ { c u t 2 }$ . Dislocations with radius $R _ { d 1 }$ (left）corresponding to a cutoff distance of $L _ { c u t 1 }$ ,while a slightly reduction of the dislocation radius from $R _ { d 1 }$ to $R _ { d 2 }$ (right） will cause a mutation of the cutoff distance from $\boldsymbol { L } _ { c u t 1 }$ to $L _ { c u t 2 }$

![](images/e4a79e607eca046daf39615f591ce230b0aad1d849f431fd3c74d55d0537f016.jpg)  
Figure l2: (color online)(a) the mutation of the cutoff distance (in the unit of box size （20 $l _ { z }$ ) $L _ { c u t }$ , of 1D migration as the function of volume fraction, compared with the average migration distance, $L$ ,obtained from Eq. (21)． (b) the ratio of $L _ { c u t }$ to $L$ ，each peak represents a mutation of the cutoff distance. Four high peaks corresponding to the four main peaks of relative error in Fig. $1 0 ( \mathrm { c } )$ ，while the four lower peaks corresponding to four shoulder peaks of relative error in Fig. 10(c).

![](images/e6a65ddef0a839cd807af731baedacb366a35004dfaff91d52f123b48a4247c0.jpg)  
Figure 13: (color online) The transition from 3D to 1D migrating sink strength of point defects absorbed by dislocation lines,grouped by box sizes,where the volume fraction of sinks is fixed at $f _ { v } = 0 . 0 0 5$ and $f _ { v } = 0 . 0 3$ (denoted by empty and solid dots, respectively). (a) simulated sink strength as a function of rotation energy,with temperature $T = 7 2 3 \textrm { K }$ ： (b) the master-curve representation, solid line represents the theoretical relationship of $\mathbf { X }$ （204号 and y in Eq. (15), dots are the simulation results elaborated according to Eqs. (16) and (17).