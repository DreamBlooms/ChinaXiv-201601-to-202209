# Optimization designs of artificial facilities in deserts based on computational simulation

DUN Hongchao, HUANG Ning\*, ZHANG Jie\*

KeyLaboratoryofechanicsonDisasterandEnvironmentinWesternChinaLanzhouUniversity,Lanzhou73Cina

Abstract: Sediment transport of sand particles by wind is one of the main processs leading to desertification inarid regions, which severely impairs the ability of mankind to produce and liveby drifting sand into settlements. Optimization designs of artificial facilities have lately attracted extensive interest for human settlement systems in deserts because of their acceptable protection effect, convenience of implementation, and low material cost. However, the complexity of a settlement system poses challenges concerning finding suitable materials, artificial facilities, and optimization designs for sand deposition protection. In an effort to overcome these challenges, we propose a settlement system built with brick, solar panel,and building arrays to meet the basic needs of human setlements in arid regions while preventing wind-sand disasters. The wind flow and movement characteristics of sand particles in the brick, panel, and building arays were calculated using computational fluid dynamics and discrete phase model. The performance of three types of arrays in wind-sand flow in terms of decreasing the wind velocity and sandparticle invasion distance was evaluated. The results show that the wind velocity near the surface and the sand invasion distance were significantly decreased in the space between the brick arrays through properly selected vertical size and interspaces, indicating that the brick arrays have an impressive sand fixing and blocking performance; their effective protection distance was $3 { - } 4 \mathrm { m }$ . The building arrays increased the nearsurface wind velocity among buildings, resulting in less deposition of sand particles. The solar panel arrays were similar to the building arrays in most cases,but the deposition of sand particles on solar panels exerted a negative effect on energy utilization efficiency. Therefore, taking the optimal configuration of the settlement system into consideration,this study concludes that (1)brick arrays, which were proven efective in preventing sand particles, must be arranged in an upwind area; (2) solar panel arrays could accelerate the wind flow, so they are best to be arranged at the place where sand particles deposited easily; and (3) building arrays present a better arrangement in downwind areas.

Keywords: desert city; sand deposition; optimization; wind flow; sand movement

# 二 Introduction

Desertification is one of the most serious environmental problems around the world, intensifying sediment transportation by wind and leading to desert extension (Christopherson et al., 2009; Tsuchiya etal., 2O1O). The desert area accounts for $20 \%$ of the Earth's land area and is continuously expanding rapidly. Approximately $0 . 7 5 \times 1 0 ^ { 9 }$ people are currently living in arid regions worldwide, and the growing population density adds pressure to the ecological environment (Warner, 2004).

Specifically, in Xinjiang Uygur Autonomous Region of China, the construction of a new countryside was carried out in the past few years to improve the quality of human life. Therefore, it is desirable to investigate wind flow and sediment transportation in human settlements (Golany, 1978).

The number of theoretical and experimental studies on novel tiled barriers for sand encroachment protection has notably increased, e.g.,low-height sand fences (Hatanaka and Hot, 1997; Bitog et al., 2009; Pye and Tsoar, 2009; Wang et al., 2O17), straw checkerboard barriers (Wang and Zheng, 2002; Huang et al., 2013; Bo et al., 2015; Xu et al., 2018; Wang et al.,2020), clay barriers (Sun et al., 2012), plastic checkerboard barriers (Liu et al., 2O11; Tian et al., 2O15),and brick arrays (Zhao et al., 2O12). A tiled barrier is usually low in height because $90 \%$ of sand grains encountering aerodynamic entrainment are located within $1 0 { - } 5 0 ~ \mathrm { c m }$ above the ground (Raupach and Lu, 2004; Mohamed and Khalaf, 2005; Jiang et al., 2017; Dun et al., 2O18). The straw checkerboard barrier is a typical tiled barrier that is widely used to prevent sand disasters along the railway in China. The study of sand transport and deposit processes in straw checkerboard barriers has been promoted by simplified theoretical analysis (Wang and Zheng， 2OO2) and air-particle two-phase flow simulation (Huang et al., 2013; Xu et al., 2018). As the latest development, Xu et al. (2018) simulated the wind-sand flow around straw checkerboard barriers using a large eddy simulation and the particle-trajectory method to explore the turbulent flow characteristics, sand particle transport, and deposit processes. They found that there are huge single streamwise vortices that filled the internal space of straw checkerboard barrier cells and double spanwise vortices located in the back of the cells.

Considering the important role of the porous parameter in the sand fence effect (Lee and Lim, 2001), Zhang et al. (2O1O) studied the shelter effect of a porous fence on wind-sand flow using a high-speed digital camera and the particle-tracking velocimetry method. These studies found that the transport rate and kinetic energy of sand can be reduced by more than $80 \%$ and $90 \%$ ， respectively. Inspired by this, Chen et al. (2O12) experimentally and numerically studied the shelter effect of porous sand fences,and found that deflector-porous fence with $30 \%$ porosity, $1 5 0 ~ \mathrm { m m }$ height and $1 5 0 ~ \mathrm { m m }$ distance which between the fence and the prism model was most effective in controlling dust emission. Adopting the advantages of the two aforementioned main tiled barriers, a brick array made of clay has attracted considerable interest because of its acceptable effect, easy implementation, environmental friendliness, and low cost (Zhao et al.,2Ol2). However, despite these advantages,the development of brick arrays is mainly retarded by a lack of thorough analysis of the sand particle transport and deposit processes.

Artificial facilities, such as buildings and solar panels, have significant influences on the atmospheric boundary-layer flow, but most simulations of the flow field around obstacles only model the flow field around isolated structures rather than groups of obstacles (Lien et al., 2004). For example, many scholars, based on the Reynolds-averaged Navier-Stokes (RANS) method, calculated the flow field around an isolated building (Montazeri and Blocken,2O13; Blocken, 2014; Chiu et al., 2O17) and around two interactive buildings (Ramponi and Blocken, 2012; Behrouzi et al.,2014). Hunter et al. (1990) calculated the three-dimension (3-D) characteristics of the flow field within an urban canyon based on the turbulence model. In addition, the shortage of studies on sand-particle movement characteristics among groups of buildings limits the optimization design effect.

In this study, we propose a human settement system referring to a previous study on a desert city (Golany,1978). The system includes brick, solar panel, and building arrays to meet the basic neds for wind-sand disaster prevention, electric power, and human settlements. All these elements can also work together to prevent sand encroachment. To obtain the best arrangement of these facilities, we calculated the 3-D turbulent wind flow and sand-particle movement characteristics around the brick, solar panel, and building arrays using the computational fluid dynamics (CFD)- discrete phase model (DPM) method.The effects of the three kinds of arrays in wind-sand flow to decrease the mean air velocity and sand particle invasion distance were evaluated.

# 2Model description

# 2.1 Fluid-phase governing equations

2.1.1 3-D Reynolds-averaged Navier-Stokes (RANS) equations   
The present study assumes that the fluid flow satisfies the continuity equation and 3-D RANS momentum equation and that a neutral atmospheric boundary layer exists in the flow field. Heat and mass transfer processes are not considered. In addition, the model is simplified by assuming a non-slip boundary condition at the ground and an incompressible fluid flow with a constant density of $\rho { = } 1 . 2 2 5 \mathrm { k g } / \mathrm { m } ^ { 3 }$ and viscosity of $\mu { = } 0 . 0 1 7 8 9 ~ \mathrm { g / ( m { \cdot } s ) }$

The continuity equation is expressed as:

$$
\frac { \partial u _ { i } } { \partial x _ { i } } = 0 ,
$$

where $u _ { i }$ and $x _ { i }$ denote the fluid velocity $\mathrm { { ( m / s ) } }$ and the microelement position from the origin $\mathrm { ( m ) }$ in the $i ^ { \mathrm { t h } }$ direction, respectively.

The momentum equation is listed as follows (Batchelor, 1967):

$$
A { = } - \rho \overline { { u _ { i } ^ { ' } u _ { j } ^ { ' } } } ,
$$

$$
\frac { \hat { \sigma } \big ( \rho u _ { i } u _ { j } \big ) } { \hat { \sigma } x _ { j } } = - \frac { \hat { \sigma } p } { \hat { \sigma } x _ { i } } + \mu \frac { \hat { \sigma } ^ { 2 } u _ { i } } { \hat { \sigma } ^ { 2 } x _ { j } } + \frac { \hat { \sigma } \big ( - A \big ) } { \hat { \sigma } x _ { j } } + F _ { s } ,
$$

$$
F _ { _ { S } } = - \sum _ { i = 1 } ^ { n } F _ { D i } / V _ { \mathrm { c e l l } } \ ,
$$

where $A$ is the Reynolds stress caused by turbulence $( \mathrm { P a } ) ; p$ is the static pressure $\mathrm { ( P a ) }$ . $F _ { s }$ is the reactive force from sand particles $( \Nu )$ · $V _ { \mathrm { c e l l } }$ is the volume of a fluid grid cell $( \mathbf { m } ^ { 3 } ) ; n$ is the number of sand particles in the grid cell; and $F _ { \mathrm { D } i }$ is the drag force acting on a single sand particle by air flow (N).

# 2.1.2Turbulence model

The turbulence flow was simulated using the renormalization group (RNG) $k { - } \varepsilon$ turbulence model, which is good at predicting the behavior of complex flows. The complete formulation of the RNG $k$ -ε turbulence model is given as follows (Yakhot and Orszag,1986):

$$
\frac { \partial \big ( \rho k \big ) } { \partial t } + u _ { i } \frac { \partial \big ( \rho k \big ) } { \partial x _ { i } } = \frac { \partial } { \partial x _ { i } } \Bigg ( \frac { \mu _ { t } } { \sigma _ { k } } \frac { \partial k } { \partial x _ { i } } \Bigg ) + G _ { k } - \rho \varepsilon \ : ,
$$

$$
\frac { \hat { \sigma } \big ( \rho \varepsilon \big ) } { \hat { \sigma } t } + u _ { i } \frac { \hat { \sigma } \big ( \rho \varepsilon \big ) } { \hat { \sigma } x _ { i } } = \frac { \hat { \sigma } } { \hat { \sigma } x _ { i } } \Bigg ( \frac { \mu _ { t } } { \sigma _ { \varepsilon } } \frac { \hat { \sigma } \varepsilon } { \hat { \sigma } x _ { i } } \Bigg ) + \frac { C _ { 1 \varepsilon } \varepsilon } { k } G _ { k } - C _ { 2 \varepsilon } ^ { * } \rho \frac { \varepsilon ^ { 2 } } { k } ,
$$

$$
G _ { _ k } = 2 \mu _ { { _ t } } S _ { _ { i j } } S _ { _ { i j } } ,
$$

$$
C _ { 2 \varepsilon } ^ { ^ * } = C _ { 2 \varepsilon } + C _ { 2 \varepsilon } ^ { ^ * } ,
$$

$$
C _ { 2 \varepsilon } ^ { ^ { \prime } } = C _ { \mu } \rho \eta ^ { 3 } ( 1 - \eta / \eta _ { 0 } ) / ( 1 + \beta \eta ^ { 3 } ) ,
$$

$$
\mu _ { t } = C _ { \mu } \rho k ^ { 2 } / \varepsilon ,
$$

$$
\eta = \sqrt { 2 E _ { _ { i j } } \times E _ { _ { i j } } } k / \varepsilon ,
$$

$$
E _ { i j } = \left( \hat { \sigma } u _ { i } / \hat { \sigma } x _ { j } + \hat { \sigma } u _ { j } / \hat { \sigma } x _ { i } \right) / 2 ,
$$

where $k$ is the kinetic energy $( \mathrm { m } ^ { 2 } / \mathrm { s } ^ { 2 } )$ · $\varepsilon$ is the kinetic-energy dissipation rate $( \mathrm { m } ^ { 2 } / \mathrm { s } ^ { 3 } )$ ： $\sigma _ { k }$ and $\sigma _ { \varepsilon }$ are the Prandtl number of the kinetic energy and dissipation rate, respectively; $S _ { i j }$ is the shearing-rate tensor $\left( \mathrm { P a } \right)$ ： $G _ { k }$ presents the generation of turbulence kinetic energy due to mean velocity gradients $( \mathrm { k g } / ( \mathrm { m } { \cdot } \mathrm { s } ^ { 3 } ) )$ ： $\boldsymbol { C } _ { 2 \varepsilon } ^ { * }$ and $C _ { 2 \varepsilon } ^ { ' }$ are coefficients related to air density; $E _ { i j }$ is the mean strain rate; $\eta$ is the coefficient of $E _ { i j }$ ；and $\mu _ { t }$ is the turbulence viscosity. The default values of the coefficients used in the transport equation for $k$ and $\varepsilon$ are as follows: $C _ { \mu } { = } 0 . 0 8 5$ ·： $C _ { 1 \varepsilon } { = } 1 . 4 2$ ： $C _ { 2 \varepsilon } { = } 1 . 6 8$ ： $\sigma _ { k } { = } 0 . 7 2$ · $\sigma _ { \varepsilon } { = } 1 . 0$ ：

$_ { \beta = 0 . 0 1 2 }$ · $\eta _ { 0 } { = } 4 . 3 8$

# 2.2 Sand-particlekineticequation

It is assumed that the forces applied to a single sand particle are gravity $( F _ { g } )$ and the drag force $( F _ { D } )$ of the fluid, and the two forces are expressed as follows (Huang et al., 2019):

$$
F _ { g } = \pi \rho _ { _ p } D ^ { 3 } { \bf g } / 6 ,
$$

$$
F _ { _ D } = C _ { _ D } \pi D ^ { 2 } \rho \big | V _ { r } \big | V _ { r } \ / 8 \ ,
$$

$$
C _ { D } = \left( 0 . 6 3 + 4 . 8 / R e ^ { 0 . 5 } \right) ^ { 2 } ,
$$

$$
R e = { V _ { \mathrm { } } } _ { f } \rho D { \left| V _ { r } \right| } V _ { r } ,
$$

$$
V _ { r } = \sqrt { \left( u - u _ { _ { D } } \right) ^ { 2 } + \left( \nu - \nu _ { _ { D } } \right) ^ { 2 } + \left( w - w _ { _ { D } } \right) ^ { 2 } } \ ,
$$

where $\rho _ { p }$ is the particle density $( \mathrm { k g } / \mathrm { m } ^ { 3 } )$ ： $D$ is the particle diameter (m); $\mathrm { \bf { g } }$ is the gravitational acceleration $( 9 . 8 ~ \mathrm { m } / \mathrm { s } ^ { 2 } )$ $C _ { D }$ is the fluid drag coefficient; $R e$ is the Reynolds number; and $V _ { r }$ is the relative velocity $\mathrm { { ( m / s ) } }$ . In addition, $u , \nu$ ,and $w$ are the three velocity components of air in the $x , y ,$ and $z$ directions,respectively. $u _ { D } , \nu _ { D }$ ,and $w _ { D }$ are the three velocity components $\mathrm { { ( m / s ) } }$ of the sand particle in the $x , y ,$ ,and $z$ directions, respectively.

The kinetic equation for sand particles is (Huang et al., 2013):

$$
m _ { _ p } \frac { \mathrm { d } U _ { _ D } } { \mathrm { d } t } { = } F _ { g } + F _ { _ D } ,
$$

where $m _ { p }$ and $U _ { D }$ are the mass $( \mathrm { k g } )$ and velocity $\mathrm { ( m / s ) }$ of sand particle, respectively.

# 2.3Numerical simulation method

The simulations were performed using the commercially available software package FLUENT (ANSYS company, USA). In the solution procedure, the nonlinear partial differential equations of the model were discretized using the finite volume method, and the segregated solution algorithm was selected. The pressure and velocity fields were decoupled using the semi-implicit method for pressure-linked equations (SIMPLE) method. The discrete phase model was used to solve the sandparticle movements. The fluid-phase governing equations and the kinetic equation of the sand particles were also decoupled in this study.

# 2.4 Computational domain and boundary conditions

A system includes brick, solar panel, and building arrays to meet the basic needs for wind-sand disaster prevention, electric power, and human settlements has been proposed in this work (Fig. 1). Brick arrays are located outside the desert city to prevent the wind-sand disaster; solar panel arrays, commercial district, industrial district and lake are set on the edge of the desert city to provide limited protection; building arrays are the core of the desert city to meet the basic needs of human settlements. All the arrays are single layer in vertical direction.

![](images/95a8d60bef9deb0c9b6684dbf00c9b1625c429b51bb76701dfaa8fcb9687c02e.jpg)  
Fig.1A schematic diagram of a settlement system including brick, solar panel, and building arrays

Figure 2 presents the schematic illustration of the computational domains of the 3-D model in the simulation based on the assumption that the velocity of the wind field at the inlet meets the following logarithmic velocity profile:

$$
U \left( z \right) = \frac { u _ { * } } { \mathbf { k } } \mathrm { l n } \frac { z } { z _ { 0 } } ,
$$

where $z$ is the height of fluid microelement $\mathrm { ( m ) }$ ： $z _ { 0 }$ is the flat surface roughness (m); k is the von Karman constant (O.41); and $u _ { * }$ is the friction velocity $\mathrm { { ( m / s ) } }$

The pressure at the outlet was specified as the reference. The symmetry boundary condition was used for the lateral computational domain, and a non-slip wall boundary condition was used for the ground and surfaces of the brick, solar panel, and building arrays (Fig. 2). The convergence criterion for the RNG $k$ -ε turbulence model was having residuals less than $1 \times 1 0 ^ { - 6 }$

In the simulations, the sand particles were placed $1 \mathrm { m }$ before these arrays as a line at a density of $5 { \times } 1 0 ^ { 4 }$ per meter. The sand-particle diameter was $0 . 2 \mathrm { m m }$ . All the sand particles had an upward velocity in the range of $0 . 0 6 7 { - } 1 . 5 0 0 ~ \mathrm { m / s }$ as the initial condition, and obeyed a probability density function depending on the velocity as follows (Huang et al., 2006):

$$
p \left( w _ { D } \right) = \frac { 1 } { - 0 . 6 2 4 + 1 . 8 1 u _ { * } } \mathrm { e x p } \left( \frac { w _ { D } } { - 0 . 6 2 4 + 1 . 8 1 u _ { * } } \right) .
$$

![](images/a58a264e49e1d00175816403a52d26b67792142ed0c7aca3f26d7bf9870bc9d2.jpg)  
Fig. 2Schematic sketch of brick arays (a), solar panel arrays (b),and building arrays (c)on the computational domain and boundary conditions.Sand particles are blown into the simulation models from the left as the wind direction.

# 2.5 Grid system

To achieve a satisfactory trade-off between the computational cost and the need for capturing significant variations in the flow field, we used a hybrid grid system to mesh the computational domain. The domain was split into two zones: the upper zone was meshed with hexahedron grids, and the lower zone was meshed with tetrahedron grids.

Further, we applied the inflation method to the boundary cells to reflect the physical phenomena at the boundaries correctly. The computational grids maintained a warping factor below O.25, and the maximum aspect radius of the grids was less than 4O. As a whole, the grids comprised approximately $2 . 0 { \times } 1 0 ^ { 6 }$ individual cells.

# 2.6Numerical validation

The numerical method was tested in four cases in which the wind flowed over a rough block surface. The height, breadth, and separation distance of the block are denoted as ${ \mathit { h } } , { \mathit { l } } .$ ，and $d _ { \cdot }$ respectively $\mathrm { ( m ) }$ . The roughness concentration $\lambda$ ， which is defined as the ratio of frontal area to floor area per block, was calculated as Equation 21.

$$
\lambda = h l / d ^ { 2 } .
$$

The roughness length $z _ { h }$ was computed from the wind profile. Figure 3 shows that the calculated curve of roughness length $z _ { h }$ normalized with height $h$ versus roughness concentration $\lambda$ is in good agreement with the experimental curve reported by Raupach et al. (1980).

![](images/dc6ebcee05406bbb8bda797d8e4a61caa275b000e3ddc6f72538e81c6c0c3bd9.jpg)  
Fig. 3 Roughness length $z _ { h }$ normalized with height $( h )$ versus roughness concentration ()

# 3Results and discussion

In the simulations, the longitudinal direction was the same as the streamwise direction, and the horizontal direction was the transverse direction. To evaluate the performance of each type of array on fixing and blocking sand particles, we defined the average of velocities in the plane $0 . 0 2 \mathrm { ~ m ~ }$ above the ground as mean velocity of sand particles (Dun et al., 2O18), and the longest movement distance of sand particles in the arrays as invasion distance. Al the simulated cases are listed in Table 1,and the parameters were sizes of elements, separation distance among the brick, solar panel, building arrays, and panel laying angle. In this section, the influence of frictional velocity on the wind flow and invasion distance of sand particles were also discussed.

# 3.1 Brick arrays

Figure 4 shows the flow velocity field and movement of sand particles in the brick arrays. As shown in Figure 4a, a series of eddies emerged within the brick arrays,and the velocity of air flow was significantly reduced comparing with the air above the bricks. In comparison, straw checkerboard barriers consisted of continuous lattice structures that forced the air flow over the slides and resulted in a series of progressively smaller eddies in the streamwise direction (Huang et al., 2013; Xu et al., 2018), while the air flow can bypass bricks owing to the space between individual bricks.Therefore, the sizes of eddies were smaller and the wind flow near the surface at different positions was more uniform than that over straw checkerboard barriers. Figure 4b presents the movement characteristics of the sand particles around the brick arrays. These sand particles moved forward in the interspaces between the bricks,and the number of sand particles in air clearly decreased, indicating that more sand particles were deposited on the surface. This movement form kept sand particles always near the surface and rapidly weakened the forward momentum, which was obviously more beneficial for sand encroachment protection. As a comparison, some sand particles may jump over $2 0 \mathrm { c m }$ when they collided with the slides of straw checkerboard barriers, and the sand transport distances by wind increased significantly.

Table 1 Changes in the spaces, sizes,angles,and friction velocity of the three types of arrays   

<html><body><table><tr><td>Type of arrays</td><td>Horizontal space (m)</td><td>Longitudinal space (m)</td><td>Horizontal size (m)</td><td>Longitudinal size (m)</td><td>Vertical size (m)</td><td>Angle</td><td>u* (m/s)</td></tr><tr><td rowspan="5">Brick arrays</td><td>0.20</td><td>0.30</td><td>0.10</td><td>0.05</td><td>0.10</td><td>90</td><td>0.3</td></tr><tr><td>0.30</td><td>0.40</td><td>0.15</td><td>0.10</td><td>0.15</td><td>90</td><td>0.4</td></tr><tr><td>0.40</td><td>0.50</td><td>0.20</td><td>0.15</td><td>0.20</td><td>90</td><td>0.5</td></tr><tr><td>0.50</td><td>0.60</td><td>0.25</td><td>0.20</td><td>0.25</td><td>90</td><td>0.6</td></tr><tr><td>0.60</td><td>0.70</td><td>0.30</td><td>0.25</td><td>0.30</td><td>90</td><td>0.7</td></tr><tr><td rowspan="5">Solar panel arrays</td><td>0.00</td><td>0.10</td><td>-</td><td>0.05</td><td>0.10</td><td>15</td><td>0.3</td></tr><tr><td>0.05</td><td>0.15</td><td>-</td><td>0.10</td><td>0.15</td><td>30</td><td>0.4</td></tr><tr><td>0.10</td><td>0.20</td><td>-</td><td>0.15</td><td>0.20</td><td>45</td><td>0.5</td></tr><tr><td>0.15</td><td>0.25</td><td>-</td><td>0.20</td><td>0.25</td><td>60</td><td>0.6</td></tr><tr><td></td><td>0.30</td><td>-</td><td>0.25</td><td>0.30</td><td>75</td><td>0.7</td></tr><tr><td rowspan="5">Building arrays</td><td>10.00</td><td>10.00</td><td>10.00</td><td>10.00</td><td>3.00</td><td>90</td><td>0.3</td></tr><tr><td>20.00</td><td>20.00</td><td>20.00</td><td>20.00</td><td>10.00</td><td>90</td><td>0.4</td></tr><tr><td>30.00</td><td>30.00</td><td>30.00</td><td>30.00</td><td>17.00</td><td>90</td><td>0.5</td></tr><tr><td>40.00</td><td>40.00</td><td>40.00</td><td>40.00</td><td>24.00</td><td>90</td><td>0.6</td></tr><tr><td>50.00</td><td>50.00</td><td>50.00</td><td>50.00</td><td>30.00</td><td>90</td><td>0.7</td></tr></table></body></html>

Note:Horizontalspace,separationdistancebetwenelementsonorzontaldirection;longitudinalspace,separationdistacebetween elementsonlongitudinal direction;angle,solarpanel layingangle; $u *$ ,frictionvelocity;-,no data

![](images/bf64c90bd7f71a8cc741013da2fd47e9d2d6b2fd83dcb5358e56324ee488a2ec.jpg)  
Fig. 4Simulation results of sand particles limit ability of brick arrays with inlet friction velocity $\mathrm { \Delta } u { * } 0 . 3 ~ \mathrm { \ m / s } ,$ 0 (a), velocity contour plot of brick arrays; (b), trajectories of sand particles in brick arrays.

The mean velocity increased significantly on widening the horizontal space between bricks (Fig. 5a). When the longitudinal space became $0 . 4 \mathrm { ~ m ~ }$ , the mean velocity decreased to a constant value and then increased slightly with increasing horizontal space (Fig. 5a). This is probably because when the air flowed through the bricks placed with a suitable longitudinal space, a series of eddies emerged within the brick arrays and a large amount of airflow energy was consumed near the surface. The mean velocity increased with the longitudinal size increased,and it decreased when the horizontal size or vertical size increased (Fig. 5b). It is clear that increasing the vertical size is a very effective method to reduce the mean velocity when the vertical size is less than $0 . 2 5 \mathrm { m }$ Thus, optimizing the brick space and size may most efficiently decrease the mean velocity of the air flow. Furthermore, the mean velocity increased linearly with the increase in friction velocity (Fig. 5c).

The variation in the invasion distance is shown in Figure 6a. Note that the invasion distance first decreased and then increased rapidly as the longitudinal space increased. Compared with Figure 5a, both lines turned to the lowest point when the longitudinal space was $0 . 4 \mathrm { ~ m ~ }$ .This can be explained by the fact that most of the airflow power was used to form eddies between the bricks, and minority power remained to push the sand particles forward in this case. Figure 6b shows a more complicated change in the invasion distance with changes in the brick size. The invasion distance significantly increased and then decreased with increasing vertical size. This may be explained by the fact that more airflow entered the interspaces between the bricks at the beginning and accelerated the wind flow. As the vertical size increased, the form drag of the bricks was significantly enhanced, which slowed down the velocity of airflow near the surface. Moreover, the brick arrays were better at blocking sand particles when the friction velocity was low (Fig. 6c). It is evident that an appropriate adjustment of the spaces and sizes of the bricks can significantly decrease the invasion distance normally by $3 { - } 4 \mathrm { ~ m ~ }$ ， which was slightly longer than the invasion distance of straw checkerboard barriers (Huang et al., 2013; Bo et al., 2015; Xu et al., 2018; Wang et al., 2020).

7.0](a) ·Horizontal space 6.01(b) ·Horizontal size 6.01(c) () rree s Longitudinal space Longitudinal size 6.0 5.0- ·Vertical size 5.0- 5.0- 4.0 4.0- 4.0- 3.0 3.0- 3.0- 2.0- 2.0+ 1.0- 2.0+ 0.0 0.2 0.40.6 0.8 1.0 0.0 0.1 0.2 0.3 0.4 0.20.30.40.50.60.70.8 Size (m) Size (m) u.(m/s)

5.5 (a) ·Horizontal space 8.01(b) ·Horizontal size 5.51(c) [) grrrisp ilisrrnn 5.0 Longitudinal space 7.0- Lertitudial size 5.0 4.5 4.5 6.0- 4.0 4.0 5.0- 3.5 3.5 4.0- 3.0 3.0- 3.0+ 2.5 0.10.2 0.30.40.5 0.60.70.8 0.0 0.1 0.2 0.3 0.20.30.40.50.60.70.8 Size (m) Size (m) u.(m/s)

# 3.2 Solar panel arrays

Another series of simulations were performed to evaluate the sand fixing and blocking performance of the solar panel arrays. As shown in Figure 7a, a series of eddies emerged within the solar panel arrays,and the velocity of airflow was significantly reduced in the same regions as the brick arrays. Figure 7b presents the movement characteristics of the sand particles around the solar panel arrays. Most of the sand particles rapidly passed through the interspaces between solar panel arrays, suggesting that the solar panel arrays are not so good for blocking sand as brick arrays. In contrast to the brick arrays, some sand particles can move above the solar panels owing to the solar panel laying an angle,and a few particles will deposit on them. This is a typical phenomenon in the application of solar panels, which exerted a negative effect on energy generation (Farid, 2012). Compared with the majority of previous studies focused on the pollutant effect of particles (Mani and Pillai, 2010; Kazem et al., 2014; Darwish et al., 2015), our simulation results reproduced the deposition process of sand particles on solar panels, which will be helpful for improving their energy utilization efficiency.

Figure 8 illustrates that changing the horizontal space, longitudinal space, or solar panel sizes had little effect on reducing the mean velocity unless the horizontal space was very small. In other words, the solar panel arrays exhibited the best effect to fix and block the sand particles when the solar panels were close to a row of walls. Figure 8c shows that the mean velocity decreased when increasing the angle between the solar panels and the ground, and Figure 8d demonstrates that the mean velocity increased linearly with the increase in friction velocity. In general, the mean velocity increased in most cases because the solar panel arrays can increase the airflow entering the interspaces between the solar panels unless the horizontal space was very small, and can remove sand particles by enhancing the airflow in a specific configuration. Thus, the solar panel arrays played a flexible role in either blocking the incoming sand particles or removing the accumulation of sand particles in accordance with specific conditions.

![](images/2fd149a7a693ea767a5422664e60967f683d99c2db3edbb42843f6745b45e28b.jpg)  
Fig. 7Simulation results of sand particles limit ability of solar panel arrays with inlet friction velocity $\scriptstyle u * = 0 . 3$ $\mathrm { m / s }$ . (a), velocity contour plot of solar panel arrays; (b), trajectories of sand particles in solar panel arrays.

![](images/201f02b21260f9be8ff80defd4b2b688059438ec532dfc4e1f0c79c538e87107.jpg)  
Fig.8Variations of the mean velocity versus (a) the space between panels with $u { * } { = } 0 . 3 ~ \mathrm { m / s }$ ,(b) the sizes of panels with $u { * } { = } 0 . 3 ~ \mathrm { m / s }$ , (c) the angle between the panels and the ground with $u { * } { = } 0 . 3 ~ \mathrm { m / s }$ ,and (d) the $u *$ ，

# 3.3 Building arrays

Figure 9 presents the flow velocity field and the movement of sand particles in the building arrays. As shown in Figure 9a, a series of eddies emerged within the building arrays, and the velocity of airflow was significantly reduced in the same regions as the brick and solar penal arrays. The longitudinal space was replete with a large eddy when the longitudinal space was approximately equal to the brick height. This has also been observed by Kanda et al. (2OO4) in their laboratory Large-eddy simulation results, which confirmed the existence of isolated large eddy in canyon flow regimes.The building spacing was significantly larger than that of bricks in the described situation, and the eddies had no chance to reduce the power of airflow near the surface between the arrays. Figure 9b shows that most sand particles rapidly passed through the interspaces between building arrays and only a few particles deposited in front of the buildings. This coincides with the transport and deposit characteristics of particulate pollutants in urban street canyons summarized by Yazid et al. (2O14). Our results suggest that blown sand hazards had litte effect on building arrays on a flat surface.

![](images/d1ce387534441aa514d2b796bfd4b15f0044b6facfce827047ad682f36783b75.jpg)  
Fig.9Simulation results of sand particles limit ability of building arrays with inlet friction velocity $u _ { * } { = } 0 . 3 ~ \mathrm { m / s }$ (a), velocity contour plot of building arrays; (b), trajectories of sand particles in building arrays.   
Fig.10Variations of the mean velocity versus (a) the space between buildings with $\scriptstyle u = 0 . 3 { \mathrm { ~ m } } / { \mathrm { s } }$ ,(b) the sizes of building with $u { * } { = } 0 . 3 ~ \mathrm { m / s }$ ,and (c) the $u *$ .

Figure 10 illustrates that changing the horizontal space, longitudinal space, or building sizes had litle effect on reducing the mean velocity in most cases. Similar to the situation with solar panel arrays,Figure 1Oa shows that the mean velocity was significantly reduced when the horizontal space was small,but it was stilltoo high to prevent sand particles from moving. According to Figure 10b, the canyon effect was enhanced because of the increased vertical size and air flow entering the interspaces between the buildings. Therefore, the mean velocity evidently increased with the vertical size. Figure 1Oc shows that the mean velocity linearly increased with the friction velocity. Thus,there was no risk of buried damage from the sand flow when the building arrays were arranged in an appropriate configuration.

9.07(a) ·Horizontal space 9.5 1(b) ·Horizontal size 16.01(c) (sa) rnrletcalt 8.5 Longitudinal space 9.0 . Lortitudialsize 14.0 7.5 8.5 10.0- 7.0 8.0 6.5 8.0 6.0- 7.5 6.0 5.5 7.0 4.0 0.0 10.020.030.040.0 50.0 0.010.020.030.040.050.0 0.20.30.40.50.60.70.8 Size (m) Size (m) u.(m/s)

# 3.4Distribution of sand flux

Variations in the distribution of sand fluxes in the streamwise direction in brick arrays are shown in Figure 11 to investigate the influence of arrays on the development of wind-sand flow. Note that changes in the horizontal brick space and horizontal size between bricks had a significant influence on the sand-flux rate on the inlet owing to the complex boundary and flow field (Dun et al., 2018), and the influence decreased with the sand flow into the brick arrays. This is because the entering space for sand into brick arrays became smaller when we increased the horizontal size and decreased the horizontal space, and more sand particles resisted outside. However, the wind flow in the streamwise direction was hardly affected in these situations, and the sand fluxes and invasion distances were almost the same inside the brick arrays. Figure 11a shows that, although increasing the longitudinal space had a slight impact on the sand-flux rate on the inlet of the brick arrays, it increased the wind-flow structure in the streamwise direction inside the brick arrays, thereby enhancing the sand-flux rates and invasion distances by providing more energy to the sand particles. Figure 11b illustrates that the sand flux reached its peak when the vertical size was approximately $0 . 2 \mathrm { ~ m ~ }$ ， indicating that this vertical size may strengthen the wind-flow structure and $0 . 1 \mathrm { ~ m ~ }$ was a more proper vertical size for tiled barriers for sand encroachment protection (Bo et al., 2O15; Xu et al., 2018). Figure 1lc suggests that the brick arrays performed better when the sand-flux rate was reduced at a low friction velocity. Owing to the litle effect on blocking sand particles in most situations, the distributions of sand flux in solar panels and building arrays were not the primary focus of this study.

301(a) Horizontal space (m) 301(b) Horizontal space (m) 301(c) u, (m/s) ((s.u)/s) xnu pues 25 0.2010-0.0101040 25 -0.010-0.15 25 110.0410.5 20 Lonitudinal sar (.) 20 Lonitudinal l sa -.20 20 15 0.60-- 0.70 15- - 0.25-0-0.30 15 Vertical space (m) 10 10- -0.10 0.15-4-0.20 10 0.25--0.30 5 5- 5 0- T 0- T 0 T 3 0 1 2 3 4 5 0 1 2 3 4 5 6 0 1 2 4 5 Distance (m) Distance (m) Distance (m)

# 3.5Configuration considerations

In general, most of the setlements are composed of block, solar panel, and building arrays to meet the basic needs of humans. There are few other human facilities afecting wind flow and sand movement. In this case, the three types of arrays considered in this study should be the main focus of configuration consideration for human settlement.

The above results suggest that the brick arrays have the most significant effect on reducing the mean velocity of airflow and the invasion distance of sand particles, demonstrating good sand fixing and blocking performance. Both the solar panel and building arrays, however, can increase the mean velocity in most cases and block the deposition of most sand particles. Exceptionally, the solar panel arrays have a significant effect on fixing and blocking sand particles when the horizontal space is small Consequently, brick arrays must be arranged in an upwind area to stop sand-particle movement and fix them on the ground. Solar panel arrays are supposed to accelerate the wind flow where sand particles deposit easily, and building arrays should better to be arranged in downwind areas.

# 4Conclusions

The invasion distance and mean velocity significantly decreased in the space between the brick arrays with properly selected vertical size and interspace, indicating that the brick arrays have a remarkable sand fixing and blocking performance, and their effective protection distance is $3 { \mathrm { - } } 4 \ \mathrm { m }$

Concerning the simulation results of the solar panel arrays, the mean velocity increased in most cases unless the horizontal space was very small, and the sand particles could be removed by enhancing the airflow in a specific configuration. The deposition of sand particles on solar panels was simulated. This is beneficial to improve the energy utilization eficiency in future studies.

The large spaces of buildings hindered reducing the power of airflow near the surface between the arrays, resulting in most sand particles rapidly going through the interspaces between the building arrays and only a few particles deposited in front of the buildings. These results suggest that blown sand hazards have little effect on building arrays on a flat surface.

Hence, in consideration of the optimal configuration of settlement systems, this study concludes that: (1) brick arrays must be arranged in an upwind area; (2) solar panel arrays could accelerate the wind flow, so it is best to arrange them at the place where sand particles deposit easily; and (3) building arrays must be arranged in downwind areas.

# Acknowledgements

This research was supported by the National Natural Science Foundation of China (11772143, 11702163, 41730644) and the National Key Research and Development Program of China (2016YFC0500901).

# References

Batchelor G K.2Oo0.An Introduction to Fluid Dynamics.Cambridge: Cambridge University Press,241.   
Behrouzi F, Sidik NA C, Malik A MA,et al. 2014. Prediction of windflow around high-rise buildings using RANS models. Applied Mechanics and Materials, 554: 724-729.   
BitogJP,LeeIB,ShinMH,etal.2O9.Numericalsimulationofanarrayofences inSaemangeumrclaimedland.Atosprc Environment, 43(30): 4612-4621.   
Blocken B.2014.5O yearsofcomputational wind engineering: past,present and future.Journal of Wind Engineering and Industrial Aerodynamics, 129: 69-102.   
BoTL,MaP,Zheng XJ.2O15.Numericalstudyontheeffectofsemi-buried strawcheckerboardsandbarriers beltonthe wind speed. Aeolian Research,16: 101-107.   
Chen G H,Wang W W,Sun CF,et al.2012.3D numerical simulation of wind flow behind anew porous fence. Powder Technology, 230: 118-126.   
Chiu PH, Raghavan VSG,Poh HJ,etal.2017.CFDmethodologydevelopmentfor Singapore greenmarkbuildingapplication. Procedia Engineering, 180: 1596-1602.   
ChristoFC.2012.Numericalmodelingof windanddust pattrns aroundafullscale parabolodal solardish.Renewable Energy, 39(1): 356-366.   
Christopherson R W, Byrne ML,Aitken AE.202. Geosystems: An Introduction to Physical Geography.Upper Saddle River: Prentice Hall, 52.   
Darwish Z A,Kazem HA,Sopian K,etal. 2O15.Effect of dust polutant typeonphotovoltaic performance. Renewable and Sustainable Energy Reviews, 41: 735-744.   
Dun HC,HuangN, Zhang J,et al.2018.Efects ofshapeand rotation ofsand particles insaltation.Journal of Geophysical Research: Atmospheres, 123(23): 13,462-13,471.   
Golany G.1978. Urban Planing for Arid Zones: American Experiences and Directions. New York: John Wiley & Sons,Inc. 142-146.   
HatanakaK,HotaS.1997.Finiteelement analysisofirflowaround permeablesand fences.InternationalJournalforNumerical Methods in Fluids,24: 1291-1306.   
HuangN,ZhengXJ,ZhouYH,etal.2Oo6.Simulationofwind-blownsandmovementandprobabilitydensityfunctionofliftof velocities ofsand particles.JournalofGeophysicalResearch: Atmospheres,11: 20201,doi:10.1029/205D006559.   
Huang N,Xia XP,Tong D.2O13.Numerical simulationof windsand movement in straw checkerboardbarrers.The European Physical Journal E,36: 99, doi: 10.1140/epje/i2013-13099-6.   
Huang N,Gong K, XuB,etal.2019. Investigations intothe lawofsand particle accumulation overrailwaysubgrade with windbreak wall. The European Physical Journal E, 42: 145, doi: 10.1140/epje/i2019-11910-0.   
Hunter LJ, Watson ID,Johson G T.1990. Modeling air flow regimes in urban canyons.Energy Build,15: 315-324.   
Jiang H,Dun HC,TongD,etal.2O17.Sandtransportationandreversepaterns overleewardfaceofsanddune.Geomorphology, 283: 41-47.   
Kanda M,Moriwaki R, Kasamatsu F2O04.Large-eddy simulation ofturbulent organized structures within andabove explicitly resolved cube arrays. Boundary-Layer Meteorology, 112: 343-368.   
Kazem AA,ChaichanMT,Kazem HA.2O14.Efectof dustonphotovoltaic utilization in Iraq: reviewarticle.Renewable and Sustainable Energy Reviews,37: 734-749.   
Lee S J,Lim HC.2Oo1.Anumerical studyon flow around atriangular prism located behind a porous fence.Fluid Dynamics Research,28: 209-221.   
LienFS,Yee E,Cheng Y. 2004.Simulationof mean flow and turbulence overa 2Dbuilding arrayusing high-resolution CFD anda distributed drag force approach.Journal of Wind Engineering and Industrial Aerodynamics,92(2): 117-158.   
LiuHJ,WangJH,LiYetal.11.Efctsoflasticheckerboardsdbaronid-anfuxofleewardofcreeicne. Journal of Soil and Water Conservation, 25(5): 26-29,34. (in Chinese)   
Mani M,PilliR.2010.Impactofdustonsolarphotovoltaic (PV)performance: rsearch status,challnges andrecommendations. Renewable and Sustainable Energy Reviews,14: 3124-3131.   
Mohamed AMI, Khalaf FI 2005.Development of computer software forthe calculation of the rateof aeolian sand transport. Port-Said Engineering Research Journal, 9: 251-266.   
Montazeri H,BlockenB.213.CFDsimulationofwind-induced pressurecoeficientsonbuildings withand withoutbalconies: validation and sensitivity analysis. Building and Environment, 6O: 137-149.   
PyeK,TsoarH. 2009. Aeolian Sand and Sand Dunes.Berlin:SpringerBerlin Heidelberg，329-367, https://link.springer.com/book/10.1007%2F978-3-540-85910-9.   
RamponiR,BlockenB.2012.CFDsimulationof cross-ventilation forageneric isolatedbuilding:impactofcomputational parameters. Building and Environment, 53: 34-48.   
Raupach MR,Thom A S,Edwards I. 1980.A wind-tunnel studyof turbulent flowclose to regularly arryed rough surfaces. Boundary-Layer Meteorology, 18: 373-397.   
RaupachMR,LuH.2o04.Representationofland-surfaceprocessesinaeoliantransportmodels.EnvironmentalModeling& Software, 19(2): 93-112.   
SunT,LiuHJ,Zhu GQetal.2O12.Timeliness ofreducingwindandstabilzingsandfunctionsof hreemechanicalsandaries in arid region. Journal of Soil and Water Conservation,26(4): 12-16,22. (in Chinese)   
TianLH,WuWY,ZhangDS,etal.2015.Characteristicsof erosionanddepositionofstrawcheckerboardbarriersinalpine sandy land. Environmental Earth Sciences,74: 573-584.   
Tsuchiya K,Igarshi T,Qong M.2O10.Landcoverchange detection basedonsatelitedataforanaridarea tothesouthof Aksu in Taklimakan desert. Journal of Arid Land, 2(1): 14-19.   
WangT,QuJJ,LingYQ,etal.2017.Wind tunnelest ontheefectof metalnetfences onsandflux inaGobiDesert,China. Journal of Arid Land, 9(6): 888-899.   
WangT,QuJJ,NiuQH.2O20.Comparativestudyofthesheltereficacyofstrawcheckerboardbarrersandrockycheckerboard barriers in a wind tunnel. Aeolian Research, 43:100575,doi: 10.1016/j.aeolia.2020.100575.   
Wang ZT, Zheng XJ.2O02.A simple model for calculating measurementsof straw checkerboard barriers.Journalof Desert Research,22(3),229-232.(in Chinese)   
Warner TT.2OO4.Desert Meteorology. Cambridge: Cambridge University Press, 1-4.   
Xu B,Zhang J,Huang N,etal.2O18.Characteristicsofturbulentaeoliansand movementoverstrawcheckerboardbarersand formation mechanismsof their internal erosionform.Journal of Geophysical Research: Atmospheres,123: 6907-6919.   
Yakhot V,Orszag SA.1986.Renormalization groupanalysis of turbulence..basic theory.JournalofScientificComputing,1(1): 3-49.   
Yazid AWM,SidikNAC,SalimSM,etal.2014.Areviewontheflowstructureandpollutantdispersioinurbanstreecaons for urban planning strategies. Simulation, 90(8): 892-916.   
Zhang N, Kang JH,Lee SJ.210. Wind tunnel observation ontheefect of aporous wind fence on shelterof saltating sand particles. Geomorphology, 120(3-4): 224-232.   
Zhao WJ, Wang LR,Ji H,etal.201.Effectof blended wheat strawonevaporationof seeding bricks with diferentoils. Bulletin of Soil and Water Conservation, 32(5): 253-256. (in Chinese)