# Modeling and Numerical Investigation of the Inlet Circumferential Fluctuations of Swept and Bowed Blades

TANG Mingzhi, JIN Donghai\*, GUI Xingmin

Aeroengine Numerical Simulation Research Center, Beihang University,Beijing, China.

$\circledcirc$ Science Press and Institute of Engineering Thermophysics,CAS and Springer-Verlag Berlin Heidelberg 2017

The circumferential fluctuation (CF)source terms inducedby the inviscid blade force can afectthe inlet distribution of flow parameters and radial equilibrium of swept and bowed blades.However,these phenomena cannot be adequately described by throughflow methods based on the axisymmetric assumption.A transport model for the CF stresses is proposed and correlated to the distributionof circulation to reflect the effect of the inviscid blade force.To investigate the eect of the inlet CFs on swept and bowed blades,the model is integrated into a throughflow model and applied to a series of cascades with different sweep and bow angles.For swept cascades, the CF source terms change the distributions of incidence angles,as wellas the radial equilibrium at the inlet of the blade passage.And the influence is enhanced as the absolute value of the sweep angle increases.For bowed cascades,the distributions of incidence angles are also altered.For both cases,the model can ofer a good prediction of the inlet CF source terms,and prove to exert a beter prediction of blade design key parameters such as flow angles.

# Keywords:Throughflow model; Circumferential fluctuation(CF) stresses; Transport model; Swept and bowed blades

# Introduction

Fully three-dimensional (3D) Navier-Stokes (N-S） simulations have been widely used in the design process of turbomachines nowadays.However, throughflow method remains an important tool for designers [1] in the early design process,as it can rapidly provide the predictions of performance and flow fields [2,3].

Asa dimension reduction method, the circumferential average method was first proposed by Smith [2].Later, throughflow models based on circumferentially averaged Euler[4] orN-S[5-8] equations were widely investigated and applied to predict the performance of compressors, and these models were proved to be well suited for obtaining transonic compressor flow fields [9].In these throughflow models，the axisymmetric assumption is adopted.With this assumption，the throughflow solvers may fail to reproduce some influences induced by 3D blade design, such as the change in the radial distribution of blade loading.

CFstresses,related to the blade-to-blade spatial fluctuations,arise in the circumferential averaging of the 3D N-S equations,due to the non-linearity of the equations. These terms are usually neglected in most throughflow models,leading to the simple axisymmetric form of the equations. The reason to neglect thenon-axisymmetric character is that the magnitude of the CF stresses was found to be small,compared with other terms in the

# Nomenclature

<html><body><table><tr><td>x,r</td><td>axial and radial coordinate (m)</td><td>i</td><td>total enthalpy (J)</td></tr><tr><td></td><td>circumferential coordinate (rad)</td><td>8</td><td>rotating speed (rad/s)</td></tr><tr><td>U</td><td>vector of conservative variables</td><td>T</td><td>viscous stress tensor</td></tr><tr><td>F,G</td><td>vectors of convective fluxes</td><td>q</td><td>heat flux</td></tr><tr><td>Fv,Gv</td><td>vectors of viscous fluxes</td><td>k</td><td>ratio of specific heat</td></tr><tr><td>S</td><td>vectors of source terms</td><td>Superscripts</td><td></td></tr><tr><td>FB</td><td>inviscid blade force</td><td>，</td><td>circumferential fluctuation</td></tr><tr><td>FF</td><td>viscous blade force</td><td>"</td><td>circumferential fluctuation (density-weighted)</td></tr><tr><td>P</td><td>circumferential fluctuation source terms</td><td>1</td><td>circumferentially averaged parameter</td></tr><tr><td>p</td><td>density (kg/m³)</td><td>=</td><td>circumferentially averaged parameter (density-weighted)</td></tr><tr><td>W</td><td>relative velocity (m/s)</td><td>Subscripts</td><td></td></tr><tr><td>V</td><td>absolute velocity (m/s)</td><td>x,r, u</td><td>axial,radial and circumferential components</td></tr><tr><td>p</td><td>pressure (Pa)</td><td>S</td><td>suction surface</td></tr><tr><td>E</td><td>total internal energy (J)</td><td>p</td><td>pressure surface</td></tr></table></body></html>

governing equations [2]. Another reason is that the designers do not have a priori knowledge of their magnitudes However, the CF stresses might be more important than the viscous terms,and their importance grew with the loading[1O,11].With the CF terms included,a major enhancement in the prediction capability of the through flowanalysis is obtained.Besides,the CF stresses might affect the spanwise and axial distribution of flow parameters,such as velocity, flow angle,pressure and loss [8, 12,13].These stresses can reveal the effect of corner stall and radial mixing. Moreover, the CF stresses will also alter the distributions of flow parameters at the inlet of the blade rows.For swept or bowed blades,the radial equilibrium would change,resulting in a stronger redistribution of flow parameters and reflecting the effect induced by swept or bowed blades [14].

The CF stresses are mainly induced by the tip leakage vortex,passage shock,shock-boundary layer interaction and hub corner stall[1O],as well as the inviscid blade force [14]. However, the difficulty still exists in modeling these physical phenomena to obtain the CF stresses.The CF stresses exhibited a harmonic behavior[15] and were modeled by a nonlinear harmonic method [16]. However, this approach was difficult to apply to the blade-to-blade stream surface.

In this paper,a stress transport model is formulated to calculate the CF stresses.This model aims at providing a quantitative approach to account for the nonaxisymmetry of the flow. The effect of CF stresses on swept and bowed blades are also investigated in the paper.

# Governing equations

# Circumferentially averaged N-S equations

The throughflow model is based on the circumferen

tiallyaveraged $\mathbf { N } { - } \mathbf { S }$ equations.The circumferentially averaging operation of aflow variable $q$ is defined as

$$
\overline { { q } } \left( x , r , t \right) = \frac { 1 } { \Delta \varphi } \int _ { \varphi _ { p } } ^ { \varphi _ { s } } q \left( x , r , \varphi , t \right) d \varphi
$$

where $\Delta \varphi$ is the azimuthal width of the blade passage. For compressible flow, the density-weighted circumferentially averaging operator is defined as

$$
\overline { { \overline { { q } } } } = \frac { \overline { { \rho } } \overline { { q } } } { \overline { { \rho } } }
$$

Further, the 3D flow parameter is decomposed into the sum of a circumferential average and a spatial fluctuation which arises from the flow non-uniformity in the circumferential direction,which can be expressed as

$$
q { \big ( } x , r , \varphi , t { \big ) } = { \overline { { q } } } { \big ( } x , r , t { \big ) } + q ^ { \prime \prime } { \big ( } x , r , \varphi , t { \big ) }
$$

Due to the non-linearity of the equations,the fluctuations appear in the formof the circumferentially averaged stresses,i.e.the so-called CF stresses.These stresses can be considered as correction terms in the momentum and energy equations which reintroduce the mean effects of the flow nonaxisymmetry into the axisymmetric equations.The non-linear terms can be expressed as

$$
\overline { { \rho q _ { 1 } q _ { 2 } } } = \overline { { \rho } } \overline { { q _ { 1 } q _ { 2 } } } + \overline { { \rho } } \overline { { q _ { 1 } ^ { \prime \prime } q _ { 2 } ^ { \prime \prime } } }
$$

Applying the circumferentially averaging operator to the N-S equations, the circumferentially averaged N-S equations in the relative frame of reference are formulated with the CF stresses being grouped as source terms, i.e. the so-called CF source terms $P$

$$
\begin{array} { l } { \displaystyle \frac { \partial \overline { { U } } } { \partial t } { + } \frac { 1 } { b r } \frac { \partial } { \partial x } \Big [ b r \Big ( \overline { { F } } - \overline { { F _ { \nu } } } \Big ) \Big ] { + } \frac { 1 } { b r } \frac { \partial } { \partial r } \Big [ b r \Big ( \overline { { G } } - \overline { { G _ { \nu } } } \Big ) \Big ] } \\ { = \overline { { S } } + F _ { B } + F _ { F } { + } P } \end{array}
$$

where

$$
\overline { { U } } = \left[ \begin{array} { c } { \overline { { \rho } } } \\ { \overline { { \rho } } \overline { { w _ { x } } } } \\ { \overline { { \rho } } \overline { { w _ { r } } } } \\ { \overline { { \rho } } \overline { { w } } _ { u } } \\ { \overline { { \rho } } \overline { { w } } _ { u } } \\ { \overline { { \rho } } \overline { { E } } } \end{array} \right] , \overline { { F } } = \left[ \begin{array} { c } { \overline { { \rho } } \overline { { w _ { x } } } } \\ { \overline { { \rho } } \overline { { w _ { x } } } \overline { { w _ { x } } } } \\ { \overline { { \rho } } \overline { { w _ { r } } } \overline { { w _ { x } } } } \\ { \overline { { \rho } } \overline { { w _ { x } } } \overline { { w _ { u } } } } \\ { \overline { { \rho } } \overline { { w } } _ { u } \overline { { w _ { x } } } } \\ { \overline { { \rho } } \overline { { i } } \overline { { w } } _ { x } } \end{array} \right] , \overline { { G } } = \left[ \begin{array} { c } { \overline { { \rho } } \overline { { w _ { r } } } } \\ { - \overline { { \rho } } \overline { { w _ { x } } } \overline { { w _ { r } } } } \\ { \overline { { \rho } } \overline { { w _ { x } } } \overline { { w _ { r } } } } \\ { \overline { { \rho } } \overline { { w _ { r } } } \overline { { w _ { r } } } + \overline { { p } } } \\ { \overline { { \rho } } \overline { { w _ { u } } } \overline { { w _ { r } } } } \\ { - \overline { { \frac { w } { \tau _ { x x } } } } \overline { { w _ { x } } } + \overline { { \tau _ { x r } } } \overline { { w _ { r } } } + \overline { { \tau _ { x u } } } \overline { { w _ { u } } } - \overline { { q _ { x } } } } \end{array} \right] ,
$$

$$
\begin{array} { r l } { \mathbb { E } _ { \tau } [ [ \begin{array} { c c } { \tau } & { 0 } \\ { \frac { \tau } { \Delta \tau } } \\ & { 0 } \\ { \frac { \tau } { \Delta \tau } } \\ & { 0 } \\ { \frac { \tau } { \Delta \tau } } \\ & { 0 } \\ { \frac { \tau } { \Delta \tau } } \end{array} ] _ { \epsilon } , } & { \mathbb { E } _ { \tau } [ \frac { \tau } { \Delta \tau } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } \mathbb { E } _ { \tau } [ [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } } \\ & { - \frac { \tau } { \Delta \tau } \Bigg [ \frac { \Delta \tau } { \epsilon } \Bigg ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \Delta \tau } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } } \\ & { \times } \\  \mathbb { E } _ { \tau } [ [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac { \Delta \tau } { \epsilon } ] _ { \epsilon } [ \frac  \Delta  \end{array}
$$

In this set of equations, $F _ { B }$ is the inviscid blade force to model the effect of pressure gradient on flow turning, while $F _ { F }$ is the viscous blade force to model the blade surface friction effect on the passage flow, and $b$ is the blockage factor reflecting the blade geometric blockage effect.

To investigate the effect of inlet CFs on swept blades, the radial momentum equation for inviscid flow can be induced to

$$
\begin{array} { c } { \underbrace { \frac { 1 } { b \overline { { \rho } } } \frac { \partial } { \partial r } \overline { { \hat { \rho } } } } _ { R G P } = \underbrace { \frac { \overline { { { \nu } } } _ { u } } { r } } _ { C E N T _ { - } H } + \underbrace { \overline { { \frac { { w _ { m } } } { r _ { m } } } } \cos \sigma } _ { C E N T _ { - } M } } \\ { \displaystyle \ - \underbrace { \overline { { w _ { m } } } \sin \sigma \frac { D \overline { { w _ { m } } } } { d m } } _ { D H M D M } + \frac { P _ { r } } { \overline { { \rho } } } + \frac { F _ { B r } } { \overline { { \rho } } } } \end{array}
$$

In equation (6),RGP is the radial gradient of pressure. CENT_W is the centrifugal force induced by the absolute circumferential velocity. CENT_M is the centrifugal force due to the curvature of the meridional streamline. DWMDM results from the acceleration of the meridional velocity along the meridional streamline.Before the leading edge of the blade passage,the radial component of the inviscid blade force $F _ { B r }$ is O, while $P r$ (actually the $P r$ in equation (5) divided by the averaged density） still exists to affect the radial equilibrium, acting as an extension of the inviscid blade force.

# Transport equations for CF stresses

To model the CF stresses $\overline { { \overline { { w _ { i } ^ { \prime \prime } w _ { j } ^ { \prime } } } } }$ in equation (5), the transport equations for the CF stresses are derived by analogy with the Reynolds stress-transport model,and presented hereas:

$$
\begin{array} { r l } & { \underbrace { \frac { \hat { \sigma } \left( b \nu ^ { - } \overline { { \rho } } \overline { { w _ { k } ^ { \prime } w _ { j } ^ { \prime } } } \right) } { b r \overline { { c } } \overline { { x } } _ { k } } } _ { \mathrm { c o i n v } \mathrm { ~ \rho ~ } } = \underbrace { - \frac { \hat { \sigma } \left( b r ^ { - } \rho w _ { k } ^ { \prime } w _ { i } ^ { \prime } w _ { j } ^ { \prime } \right) } { b r \overline { { c } } \overline { { x } } _ { k } } } _ { T R M \mathrm { ~ \rho ~ } } } \\ & { \qquad - \underbrace { \left( \overline { { \rho } } \overline { { w _ { i } ^ { \prime } w _ { k } ^ { \prime } } } \frac { \hat { \sigma } w _ { j } ^ { \prime } } { \overline { { c } } \overline { { x } } _ { k } } + \overline { { \rho } } \overline { { w _ { j } ^ { \prime } w _ { k } ^ { \prime } } } \frac { \hat { \sigma } w _ { i } ^ { \prime } } { \overline { { c } } \overline { { x } } _ { k } } \right) } _ { \mathrm { d } \mathrm { d } \mathrm { ~ \rho ~ } } } \\ & { \qquad - \underbrace { \left( \overline { { w _ { i } ^ { \prime } \frac { \hat { \sigma } p } { \hat { w } _ { j } } } } + \overline { { \rho } } \overline { { \nu } } \overline { { \frac { \hat { \sigma } p } { \hat { w } _ { i } } } } \right) + \left( \overline { { { w _ { i } ^ { \prime } \hat { \sigma } p } } } + \overline { { w _ { j } ^ { \prime } \hat { \sigma } _ { i } } } \right) } _ { \mathrm { c o i n ~ \rho ~ } } } \end{array}
$$

The transport equations consist of six equations,but the transport equations for the velocity-enthalpy correlation terms in the energy equation are not modeled,since they are less important [17].

In equation(7),term CONV is the convection term, representing the convection of CF stresses.Term TRAN is the transport term.Term GEN is the generation term, representing the coupling of the transport equation and the axisymmetric flow. Term PRE is the pressure-velocity correlation term，representing the work done by the pressure fluctuation. Term CENT is the velocity-source correlation term，representing the work done by the source terms of the mean flow.

Different from the Reynolds stress-transport models, the viscous terms are neglected in equation (7).The reason is that the focus of the present paper is to model the CF at the inlet of the blade passage,where the loss is small.Furthermore,CFs of the first half of the blade chord mainly comes from inviscid effects [11].

The PRE term is found to be the dominant term at the right-hand side of equation (7).So only the PRE term is modeled to close the transport model，while the other terms are neglected.

# Modeling the pressure-velocity correlation

The method to model the pressure-velocity correlation is mainly based on the inviscid analysis. Since the pressure potential field dominates the circumferential nonuniformity, considering the Helmholtz decomposition,

$$
\stackrel {  } { \nu } = \nabla \phi + \nabla \times \stackrel { \longrightarrow } { \psi }
$$

For modeling the circumferential non-uniformity at the inlet of the blade passage, the flow can be assumed to be irrotational in the absolute frame of reference.That is,

$$
\nabla \times \vec { \nu } = \vec { 0 }
$$

This reduction of the problem omits the influence of the secondary flow which is another source of the CF stresses.Nevertheless,it does not introduce a lack of generality, since the core-flow are far from being negligible[8,11, 15].

Besides,a further assumption is that the flow variables $p , \rho$ and $w _ { i }$ are able to be expressed through a Taylor series expansion in the circumferential direction. In the present investigation, the flow parameters are expressed through Taylor series expansion with partial derivatives up to $1 ^ { \mathrm { s t } }$ order, i.e.

$$
\left\{ \begin{array} { l } { \displaystyle p = \overline { { p } } + \frac { \hat { c } p } { \hat { c } \varphi } ( \varphi - \varphi _ { 0 } ) } \\ { \displaystyle } \\ { \displaystyle \rho = \overline { { \rho } } + \frac { \hat { c } \rho } { \hat { c } \varphi } ( \varphi - \varphi _ { 0 } ) } \\ { \displaystyle _ { w _ { i } = \overline { { w _ { i } } } + \frac { \hat { c } w _ { i } } { \hat { c } \varphi } ( \varphi - \varphi _ { 1 } ) } } \end{array} \right.
$$

which means that these variables are assumed to be linearlydistributed inthecircumferentialdirection.This assumption may fail if a strong shock wave exists in the flow field.However, this situation is not considered in the present investigation.Besides,higher order Taylor series expansion may bring higher precision,but the improvement in precision is not investigated either.

From equation (1O), the PRE term can be derived as

$$
\overline { { w _ { i } ^ { \prime } \frac { \partial p } { \partial x _ { j } } } } = \overline { { \frac { \partial w _ { i } } { \partial \varphi } ( \varphi - \varphi _ { 1 } ) \cdot \frac { \partial } { \partial x _ { j } } [ \overline { { p } } + \frac { \partial p } { \partial \varphi } ( \varphi - \varphi _ { 0 } ) ] } }
$$

If we further assume that $\varphi _ { 0 }$ locates at the middle of the blade passage,and ${ \frac { \partial w _ { i } } { \partial \varphi } } , \ { \frac { \partial ^ { 2 } p } { \partial x _ { j } \partial \varphi } }$ are independent of $\varphi ,$ then the PRE term can be derived as

$$
\begin{array} { c } { { \displaystyle { \overline { { w _ { i } ^ { \prime \prime } \frac { \partial p } { \partial x _ { j } } } } = \frac { \partial w _ { i } } { \partial \varphi } \frac { \partial ^ { 2 } p } { \partial x _ { j } \partial \varphi } \frac { \Delta \varphi ^ { 2 } } { 1 2 } - \frac { \hat { \sigma } w _ { i } } { \hat { \sigma } \varphi } \frac { \hat { \sigma } \overline { { p } } } { \hat { \sigma } x _ { j } } \big ( \varphi _ { 1 } - \varphi _ { 0 } \big ) } } } \\ { { + \frac { \hat { \sigma } w _ { i } } { \hat { \sigma } \varphi } \frac { \hat { \sigma } p } { \hat { \sigma } \varphi } \frac { \hat { \sigma } \varphi _ { 0 } } { \hat { \sigma } x _ { j } } \big ( \varphi _ { 1 } - \varphi _ { 0 } \big ) } } \end{array}
$$

According to equation (2), the relationship between $\varphi _ { 0 }$ and $\varphi _ { 1 }$ is

$$
\varphi _ { 1 } = \frac { \Delta \varphi ^ { 2 } } { 1 2 \overline { { \rho } } } \frac { \partial \rho } { \partial \varphi } + \varphi _ { 0 }
$$

As long as we obtain the circumferential derivatives of pressure and velocity, the pressure-velocity correlation is closed. Moreover,to formulate the correlation with the distribution of blade loading,which reflects the inviscid blade force,the formula in Wu's [18,19] hub-to-tip stream surface theory is adopted,i.e.

$$
\frac { \partial p } { \partial \varphi } = - \rho w _ { x } \frac { D ( \nu _ { u } r ) } { D x }
$$

So the circumferential derivative of pressure is corre lated to the distribution of the circulation,which is a key parameter in the design process.

To get the circumferential derivatives of the three velocity components,the continuity equation and the inviscid form of energy equation are adopted. Combined with equation (9),the circumferential derivatives of the three velocitycomponents are as follows,

$$
\left\{ \begin{array} { l } { { \displaystyle { \frac { \hat { \alpha } \boldsymbol { w } _ { x } } { \partial \varphi } } = { \frac { \hat { \alpha } \boldsymbol { w } _ { u } \boldsymbol { r } } { \hat { \alpha } \boldsymbol { x } } } } } \\ { { \displaystyle { \frac { \hat { \alpha } \boldsymbol { w } _ { r } } { \hat { \alpha } \varphi } } = { \frac { \hat { \alpha } \boldsymbol { w } _ { u } \boldsymbol { r } } { \hat { \alpha } \boldsymbol { r } } } + 2 \omega r = { \frac { \hat { \alpha } \boldsymbol { v } _ { u } \boldsymbol { r } } { \hat { \alpha } \boldsymbol { r } } } } } \\ { { \displaystyle { \frac { \hat { \alpha } \boldsymbol { w } _ { u } } { \hat { \alpha } \varphi } } = [ k R T ( { \frac { \hat { \alpha } \left( r \rho \boldsymbol { w } _ { r } \right) } { \hat { \alpha } r } } + { \frac { \hat { \alpha } \left( r \rho \boldsymbol { w } _ { x } \right) } { \hat { \alpha } \boldsymbol { x } } } ) } } \\ { { - \rho \boldsymbol { w } _ { u } ( \boldsymbol { w } _ { x } { \frac { \hat { \alpha } \boldsymbol { w } _ { x } } { \hat { \alpha } \varphi } } + \boldsymbol { w } _ { r } { \frac { \hat { \alpha } \boldsymbol { w } _ { r } } { \hat { \alpha } \varphi } } ) ] / [ \rho ( { w } _ { u } ^ { 2 } - k R T ) ] } } \end{array} \right.
$$

Considering equations (14） and (15)， the major sources of circumferential non-uniformity are the partial derivatives of the circulation.

# Results and discussion

A series of swept and bowed cascades are selected to validate the model and investigate the effect of the inlet CFs.The swept and bowed cascades have the same element profile.The thickness distribution of the CDA profile is the same as SKG3.6 [2O]. The basic parameters are listed in table1.

For all cases,the nominal incidence angles are zero, which means the inlet flow angle is equal to the blade geometric inlet angle.

Table1 Basic parameters of cascade   

<html><body><table><tr><td>Parameters</td><td>Values</td></tr><tr><td>Chord</td><td>100 mm</td></tr><tr><td>Blade geometric inlet angle βik</td><td>40°</td></tr><tr><td>Aspect ratio of cascades</td><td>6.0</td></tr><tr><td>Solidity</td><td>2.15</td></tr><tr><td>Camber angle</td><td>40°</td></tr></table></body></html>

Both 3D and throughflow numerical simulations are carried out. The 3D numerical solver is FINE Turbo by NUMECA International. The number of grid nodes of each cascade is 1623296.Fig.1 shows the grids for 3D simulations.Two sets of Euler throughflow simulations denoted as CAM,representing the original throughflow model，and CAM+MODEL，representing the throughflow model including the transport model, respectively in the following sections,are also carried out.For $\mathbf { C A M + }$ MODEL，the CF source terms are taken into account before the leading edge of the blade row,while they are set to zero at other portion. Total pressure, total temperature and the direction of the flow are imposed at the inlet ofthe computation domain.Themassflowisimposed as the outlet boundary condition to ensure the same inlet Mach number.For 3D simulations，the adiabatic nonslipping conditions are applied to the solid boundaries.

![](images/4052dbd675c8684a96671fc1e2b44c946dc0db6ed8678df59a593dc941ce6aa7.jpg)  
Fig.1 3D computational grids of the cascades

In the following sections,the data in the figures is extracted at about $4 \%$ of the chord before the leading edge.

# Cascades of different sweep angles

To investigate the effect of the inlet CFs on swept blades,a series of simplified cascades with different sweep angles are employed to be compared and analyzed. In this paper,we use the definition of sweep defined by Ramakrishna and Govardhan [21],as shown in Fig.2. The sweep angles are $\pm 5 ^ { \circ }$ ， $\pm 1 0 ^ { \circ }$ $\pm 1 5 ^ { \circ }$ ， $\pm 2 0 ^ { \circ }$ ， $\pm 2 5 ^ { \circ }$ ，where the negative and positive values represent backward (BS) and forward sweep (FS) respectively.Fig.3 illustrates the meridional viewof the forwardand backwardcases.

![](images/b63579e3e8cf193bcab7a0d0a5a49cb66056a44cfa024b3c0772534a5340693e.jpg)  
Fig.2Definition of sweep [22]

![](images/ed52fbe52fdd01e31bbf306d98639157db5309235b2c56f94ad48ff1dc93818b.jpg)  
Fig.3Sketch of swept cases in meridional view

For 3D numerical simulations,viscous calculations are carried out. Therefore flows near the endwalls are affected by the boundary layer.In this paper,only the inviscid phenomena are discussed,so the parameters near theendwallsarenotincluded.

Fig.4 shows the relationship between the incidence angle and the sweep angle.At $20 \%$ height of the cascades. the incidence angle increases with the increase of the sweep angle.While it reveals an opposite trend at $80 \%$ height.Besides,compared with the 3D results, $\mathbf { C A M + }$ MODEL gives a better prediction of incidence angles than CAM.And the difference ranges from $0 . 2 ^ { \circ }$ to $0 . 5 ^ { \circ }$ Thisremark shows that the throughflow model without the CFs is not sufficient to have an accurate description of the flow turning.

The improvement in the prediction of incidence angles mainly results from the inclusion of $P u$ $P r$ and $P x$ ，which affectsthedistributionofmeridional andcircumferential velocity. Fig. 5 presents the relation between the sweep angle and $P u$ before the leading edge of the cascade. Fromthedefinition,the inviscidbladeforceisObefore the leading edge.However, $P u$ still exists and will work as a source term to change $w _ { u }$ along the streamline direction. $P r$ and $P x$ will affect the distribution of pressure and velocity in the radial and axial direction respectively.As stated in [14],the CF source terms are induced by the inviscid blade force,and work as the extension of the inviscid blade force to the upstream of the blade passage.

![](images/a416ac73b2f34aefbf84485aa99b7c15ced1a6e7d17ea653558e1767d4d30f29.jpg)  
Fig.4 Relation between the sweep angle and the incidence angle at different spanwise position

For stators, $F _ { B u }$ equals $\frac { \left( p _ { s } - p _ { \mathrm { p } } \right) } { r \Delta \varphi }$ which is negative at the present working conditions of these cascades. Therefore, $P u$ is also negative,representing the extension of pressure difference on the blade surfaces at the leading edge of the cascades.As observed in Fig.5,the transport model can give a good prediction of $P u$ .The magnitude of $\mathbf { C A M + M O D E L }$ is the same as 3D.Moreover, $\mathrm { C A M + }$ MODEL gives a similar trend in the changes of $P u$ with sweep angles to the 3D results.The absolute value of $P u$ of both numerical simulations increases as the absolute value of the sweep angle increases,revealing stronger CFs induced by blades of higher sweep angles.As a result, the modification of $\nu _ { u } r$ at the inlet of the blade passage by the CFs is enhanced.And the model can provide an accurate description of this modification.Moreover, the change differs at different spanwise positions for a swept blade,or for blades of different sweep angles,and the transport model can give a good prediction of the change in $\nu _ { u } r$

![](images/1bd616f75016be4925d18be8de9c41be4f18ce5fc88dc4ff1b52de58586b9f0c.jpg)  
Fig.5Relation between the sweep angle and the inlet $P u$ at different spanwise position

To further exploit the improvement brought by the transport model, the prediction of the radial equilibrium at the inlet of the blade passage is analyzed.The spanwise distributions of the terms in equation (6) are extracted，as shown in Figs.6-1O.From these figures, CENT_M and $P r$ are the major terms to balance RGP, while CENT_W and DWMDM are about $1 0 ^ { - 3 }$ to $1 0 ^ { - 1 }$ order of RGP.Hence, it is necessary to model $P r$ to get a more accurate prediction of the radial gradient of pressure.Furthermore,for 3D,fromBS1O to BS2O,the value of RGP increases from about $5 0 0 0 ~ \mathrm { m / s } ^ { 2 }$ to about 12000 $\mathrm { m } / \mathrm { s } ^ { 2 }$ (Fig.6),and the value of $P r$ increases from about $1 0 0 0 \ \mathrm { m / s } ^ { 2 }$ to about $7 0 0 0 \ \mathrm { m / s } ^ { 2 }$ (Fig.10),which makes most of the contribution to the change in RGP,while CENT_M increases fromabout $3 0 0 0 ~ \mathrm { m / s } ^ { 2 }$ to $5 0 0 0 ~ \mathrm { m / s } ^ { 2 }$ Forforward sweep cases,similar trends can be observed. That is,as the absolute value of the sweep angle gets larger,theabsolutevaluesofRGP and $P r$ increase faster than CENT_M.Moreover, $P r$ gets more prominent as the sweep angle increases.

From BS1O to BS2O, the discrepancy of RGP between 3D and CAM increases from about $3 0 0 0 ~ \mathrm { m / s } ^ { 2 }$ to about $6 0 0 0 ~ \mathrm { m / s } ^ { 2 }$ ，while $\mathbf { C A M + M O D E L }$ represents a better description of RGP than CAM,although discrepancies still exist between CAM+MODEL and 3D, as shown in Fig. 6. Besides,as the absolute value of the sweep angle increases,a more accurate prediction of RGP by $\mathrm { C A M + }$ MODEL is obtained.Combined with Figs.7-1O,the improvement mainly comes from $P r$ .Thus the inclusion of $P r$ by the throughflow model may provide a more accurate prediction with the increase of the absolute value of the sweep angle.

0.9 □ Δ ? N 1 h 0.8 3 1 21111 1 \*HR △-FS10_3D BS20_3D 0.7 BS2CAM E 4 FS10_CAM BS20_CAM+MODEL ← -△-FS10_CAM+MODEL 1 -D-FS20_CAM+MODEL + 0.3 会 H \*. A 0.2 □ ? P Z 5 T 0.1 ? A ■ T ！ -15000 -10000 -5000 F0 5000 10000 15000 RGP

From Fig.8, CAM $+$ MODEL can also give a good description of CENT_M.Since the difference in the meridional velocity between CAM, CAM+MODEL and 3D is small, CAM $\cdot +$ MODEL can better depict the streamline curvature at the inlet of the blade passage,which is modified by the new radial equilibrium.

0.9- A 1 金 90080 L 0.8 □ 0.7- BS20_3D BS10_3D 0.6- △-FS10_3D 4 asimueds --- FS20_3D BS20_CAM 0.5- 1 BS10_CAM △FS10_CAM FS20_CAM 0.4- -BS20_CAM+MODEL BS10_CAM+MODEL △FS10_CAM+MODEL 000000000000 二 0.3- -□--FS20_CAM+MODEL 会 0.2- 公 L 新 0.1+ □ 中 T 1 250 260 270 280 290 300 CENT_W

![](images/f7f0b920d98e2de268e22bc80f5bbfb040cd6bfe793a73adfbe495e3aa004da5.jpg)  
Fig.6Spanwise distribution of the inlet RGP with different sweep angles   
Fig.8Spanwise distribution of the inlet CENT_M with different sweep angles   
Fig.7Spanwise distribution of the inlet CENT_W with different sweep angles   
Fig.9Spanwise distribution of the inlet DWMDM with different sweep angles   
Fig.10Spanwise distribution of the inlet $P r$ with different sweep angles

0.9- □ 1 A 7 A 4 店 1 A 4 0.8 1 T 五 1 1 ■ 4 □ 1 BS20_3D 0.7- 4 R 1 FS10_3D --FS20_3D + BS20_CAM 0.6- 工 中 BS10_CAM △FS10_CAM ssimueds □ FS20_CAM 0.5 △ 台 040 PS10CAMMODEL X L 3 ? 会公民 □-FS20_CAM+MODEL 0.4- A - A 乾 0.3- 中 会 A ? 足 □ △ ? 1 石 A 0.2- 会 A 1 ? L □. L □ △ □ □ △ X T .. □ 0.1+ A □ 公 □ □ 一 -350-300-250-200-150-100-50050 100150200 250300 350 DWMDM

8 □00000000□0□0□□□□00000□□000□0□□00 X△△△△△△△ HHH A4   
0.7   
6 JNNNNNOONOONNNNKKKKKKKK SD ES20_CAM+MODEL -BS10_CAM+MODEL FS10_CAM+MODEL   
0.3-   
0.2-   
0.1000 -4000 -2000 0 2000 4000 6000 8000 Pr

For FS1O and BS1O, the value of $P r$ predicted by the transport model is about O.O8 of the 3D results (Fig. 10), and this ratio increases to about O.2 for FS2O and BS20.

Therefore, the transport model still needs to be modified. However, the model can already give a good prediction of the radial equilibrium at the inlet of the blade passage. Besides,better prediction of $P r$ can be obtained by the transport model with the increase of the absolute value of the sweep angle.

# Cascades of different bow angles

To further investigate the effect of inlet CFs,a series of simplified bowed cascades with different bow angles are employed to be analyzed and compared. In this paper, we use the definition of bow defined by Wang Zhongqi [23]. The bow angles are $\pm 5 ^ { \circ }$ $\pm 1 0 ^ { \circ }$ $\pm 1 5 ^ { \circ }$ . An axial view of the bowed cases is presented in Fig. 11.

Therelation between the incidence angle and the bow angleis analyzed,as shown in Fig.12.Similar to the swept cascade cases, $\mathbf { C A M + M O D E L }$ also providesa better prediction of the incidence angles than CAM.Besides,the incidence angles vary as the bow angles change and $\mathbf { C A M + M O D E L }$ can better depict the trend at $50 \%$ and $80 \%$ height of the cascades.

Fig.13 is the relation between the inlet $P u$ and the bowangle.Asaforementioned, forbowed cascades, $P u$ is also inducedby the inviscidblade force.Thus itsvalue is negative.For bowed cascades,the transport model can givea good prediction of $P u$ as well.

From Figs.12 and 13,for negative bowed cascades, the incidence angle decreases as the bow angle increases, reflecting an unloading process, thus inducing the decrease of the absolute value of $P u$ .Forpositive bowed cascades，the process is on the contrary.And $\mathbf { C A M + }$ MODEL can depict this trend as well.

The radial equilibrium of the bowed cascades case is also altered. However, the change of terms in equation (6) is small. Therefore,they are not presented in the present paper.

![](images/1643ca5a672b08e0cdb5b0736c8ce9283a792e90dd9d88e76c9f389dc1d657bb.jpg)  
Fig.11Sketch of bowed cases in axial view

![](images/9b761b5a1eb6bd752fbff20b1c70973003ebb78b63422484792fccc87083ee3c.jpg)  
Fig.12Relation between the bow angle and the incidence angle at different spanwise position

![](images/507964ab13922559080eb5bf5fe90c1a19c1edaed989c493c095b026d3e49063.jpg)  
Fig.13Relation between the bow angle and the inlet $P u$ at different spanwise position

# Conclusions

The CF stresses are always neglected in throughflow models,which may fail to describe some flow phenome na induced by 3D blade design. To conquer the shortcomings,a transport model for the CF stresses is formulated and integrated into a throughflow model. The transport model is based on potential flow analysis and is correlated with the distribution of circulation,which reflects the inviscidblade force.

To investigate the effect of the inlet CFs on swept and bowed blades,such as the change in flow angles and the radial equilibrium,a series of swept and bowed cascades are employed. Some conclusions are summarized as follows:

1. The CF source terms can offer a better description of the radial equilibrium at the inlet of the blade passage induced byswept and bowed cascades.

2.The CF source terms have a greater influence on the inlet radial equilibrium of swept cascades than bowed cascades.Besides,as the absolute value of the sweep angle increases,the influence of CF source terms gets stronger. And the accuracy of the transport model improves meanwhile.

3．Compared with 3D results，throughflow models with the transport model included can provide a better prediction of the flow fields of swept and bowed cascades.Moreover, the transport model can provide a good prediction of the inlet CF source terms,i.e. a good quantitative approach to account for the nonaxisymmetry of the flow.

# Acknowledgement

This work was supported by National Natural Science Foundation of China (51006005，51236001)，National Basic Research Program of China （2012CB720201） and Beijing Natural Science Foundation (No.3151002).

# References

[1]Horlock,J.H.,Denton,J.D.:A review of Some Early Design Practice Using Computational Fluid Dynamics and a Current Perspective,Transactions of the ASME Journal of Turbomachinery,vol.127,pp.5-13,(2005).   
[2]Smith Jr,L.H.: The radial-equilibrium equation of turbomachinery,Journal of Engineering for Power,Transactions of the ASME,Vol.88,No.1,(1966).   
[3]Jin Hailiang，Jin Donghai,Li Xiaojuan,et al.:A Time-Marching Throughflow Model and its Application in Transonic Axial Compressor,Journal of Thermal Science,Vol.19,pp.519-525,(2010).   
[4]Spurr,A.: The prediction of 3D transonic flow in turbomachinery using a combined throughflow and blade-toblade time marching method, International Journal of Heat Fluid Flow, Vol.2,No.4, pp.189-199,(1980).   
[5]Fay,G.,Lawerenz,M.， Przewozny,H.: Calculation of Pitch Averaged Viscous Flow in Annular Compressor Cascade, Computational Methods in Experimental Measurements IX,22: 185-194,(1999).   
[6]Simon,J. F.,Leonard, O.: A Throughflow Analysis Tool Based on the Navier-Stokes Equations,Proceedings of the 6th European Turbomachinery Conference，Lille, (2005).   
[7]Simon, J. F.,Leonard, O.: Modeling of 3-D Losses and Deviations in a Throughflow Analysis Tool, Journal of Thermal Science,16(3): 1-7,(2007).   
[8]Simon, J. F., Thomas,J. P., Leonard, O.: On the Role of the Deterministic and Circumferential Stresses in Throughflow Calculations,ASME,Journal of Turbomachinery, Vol. 131(3): 1-12,(2009).   
[9]Baralon,S.，et al.: Validation of a Throughflow TimeMarching Finite-Volume Solver for Transonic compressors,ASME 98-GT-74, Stockholm, Sweden,(1998).   
[10]Baralon S,Erikson LE,Hall U.: Evaluation of high-order terms in the throughflow approximation using 3D Navier-Stokes computations of a transonic compressor rotor, ASME Paper, 99-GT-74, Indianapolis,USA,(1999).   
[11]Simon,J. F.: Contribution to throughflow modelling for axial flow turbomachines,University of Liege,Belgium, (2007).   
[12]Jennious, I.K.,and Stow, P.: A Quasi-Three-Dimensional Turbomachinery Blade Design System:Part I - Throughflow Analysis,Journal of Engineering for Gas Turbines & Power 107(2): 301-307, (1985).   
[13]Jennious, I.K.,and Stow, P.: A Quasi-Three-Dimensional Turbomachinery Blade Design System: Part II - Computerised System,Journal of Engineering for Gas Turbines & Power 107(2): 308-314,(1985).   
[14]Xingmin Gui, Fang Zhu, Ke Wan, Donghai Jin.: Effects of Inlet Circumferential Fluctuation on the Sweep Aerodynamic Performance of Axial Fans/Compressors,Journal of Thermal Science,22(5): 383-394,(2013).   
[15]Thomas, J.P., Simon, J. F,and Leonard, O.: Investigating Circumferential Non-Uniformities in Throughflow Calculations Using a Harmonic Reconstruction,ASME Paper No.GT2008-50328,Berlin,Germany, (2008).   
[16]Thomas,J. P,Leonard,O.: Toward a high order throughflow-investigation of the nonlinear harmonic method coupled with an immersed boundary method for the modeling of the circumferential stresses.Journal of Turbomachinery， Transactions of the ASME,vol.134，pp. 1-9, (2012).   
[17]Ke Wan.: Modeling and Application of Circumferentially Averaged Method in Turbomachinery,Ph.D thesis, Beihang University,Beijing,(2014).   
[18] Wu Chunghua.:AGeneral Through-Flow TheoryofFluid Flow with Subsonic or Supersonic Velocity in Turbomachines of Arbitrary Hub and Casing Shapes,NACA TN 2302,(1951).   
[19] Wu Chunghua.:A General Theory of Three-Dimensional Flow in Subsonic or Supersonic Turbomachines in Radial, Axial and Mixed-Flow Types,NACA TN2604,(1952).   
[20]Rechter, H.,Steinert,W.,Lehmann,K.: Comparison of ControlledDiffusionAirfoilsWith Conventional NACA65 Airfoils Developed for Stator Blade Application in a Multistage Axial Compressor,Transactions of the ASME Journal of Engineering for Gas Turbines and Power,107:494-498,(1985).   
[21]Ramakrishna PV,Govardhan M.: Numerical Study of the Stagger Angle EffectsinForward Swept Axial CompressorRotor Passages,ASME Paper GT2010-23160,Glasgow,UK,(2010).   
[22] Chang,H.,Zhu,F., Jin,D.,and Gui,X..:Effect of blade sweep on inlet flow in axial compressor cascades,Chinese Journal of Aeronautics,28(1),103-111,(2015).   
[23] Wang Zhongqi, Zheng Yan.,Research Status and Development of the Bowed-Twisted Blade for Turbomachines, Engineering Science,2(6),(2000).