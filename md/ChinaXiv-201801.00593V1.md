# Effect of Inlet Guide Vanes on the Performance of Small Axial Flow Fan

LIU Yang1,LIN Zhe1, LIN Peifeng1, JIN Yingzil\*,Toshiaki Setoguchi², Heuy Dong Kim3

1. KeyLaboratoryofFluid Transmision Technologyof Zhejang Province,Zhejiang Sci-Tech University,Hangzhou 310018, China   
2. Department of Mechanical Engineering, Saga University, Honjo-machi, Saga, 840-8502, Japan   
3.School of Mechanical Enginering, Andong National University, Seongcheon-Dong1375, Gyeongdong-RD,Andong, Gyeongsangnuk-DO, 760-749, Korea

Effcts ofthe inlet guide vanes on the static characteristics,aerodynamic noise and internal flow characteristics of a small axial flow fan are studied in this work.The inlet guide vanes with diffrent outlet angle are designed, which are mounted on the casing and located at the upstream ofthe impeller of the prototype fan.Both steady and unsteady flow simulations are performed.The steady flow is simulated by thecalculations of Navier-Stokes equations coupled with RNG k-epsilon turbulence model, while the unsteady flow is computed with large eddy simulation.According to the theoretical analysis, the inlet guide vanes with outlet angle of $6 0 ^ { \circ }$ are regarded as the optimal inlet guide vanes.The static characteristic experiment is cariedout in a standard test rigand the aerodynamic noise is tested in asemi-anechoic room.Then,performances of the fan with optimal inlet guide vanes are compared with those of the prototype fan.The results show that there is reasonable agreement between the simulation results and the experimental data.It is found that the static characteristics of smallaxial flow fan is improved obviouslyafter installing the optimal inlet guide vanes.Meanwhile,the optimal inlet guide vanes have effect on reducing noise at the near field, but have little effect on the noise at the far field.

# Keywords:smallaxialflowfan,inlet guide vanes,staticcharacteristics,aerodynamic noise,internalflowcharacteristics

# Introduction

Small axial flow fan is a main cooling device of electronic products at present.Its performance determines the operation status and service life of the electronic products directly.With the development of the electronic products toward integration and high power, the requirement of cooling is increasing and the performance of small axial flow fan attracts more and more attentions [1-2]. Therefore,it is very necessary to optimize the small axial flow fan and analyze its static characteristics,aerodynamic noise and internal flow characteristics.

The axial flow fan with inlet guide vanes is widely used for its high flow rate and high efficiency. The air can generate a rotational velocity in advance before entering the impeller,whose direction is contrary to the rotational direction of the impeller and this rotational velocity can be offset by the rotational velocity induced by the impeller. So,the airflow in the outlet of the fan forms a single axial flow. According to the sketches of gas dynamics of the fan，Wu [3] pointed out that the number of inlet guide vanes and the number of impeller blades were prime to one another in most cases. The axial distance between the trailing edge of inlet guide vanes and the leading edge of impeller blades shall not be less than O.25 times of the chord length of inlet guide vanes at the hub.Besides, the axial distance should be taken as the minimal value from the view of the structure size.While from the view of the aerodynamic noise, increasing of the axial distance would bring more benefits.The perfor manceof the fan would not be affected once the axial distance exceeded O.5 times of the chord length. Wallis [4] thought that the choice of the guide vanes number not only need to consider the aerodynamic performance and noise characteristics,but also should take into account the strength of the vanes and the axial structure size of the fan. The product of the guide vanes number and operating speed of the impeller should not equal to the natural frequency of the impeller. Sakharov et al. [5] believed that the strong wake caused by the upstream guide vanes would hinder the secondary leakage flow at the tip of the downstream impeller blade at the high load condition.Thus,the secondary leakage loss and the congestion at the tip of impeller blade were reduced,and the performance of the fan was improved. The flow at the tip clearance became more complicated due to the interference between the guide vanes and impeller blades. Jesus [6] focused on the deterministic fluctuations that occur in the axial gap between the blade rows.This periodic fluctuation was superimposed on the steady vane-to-vane velocity distribution, resulting in a nonuniform unsteadiness with additional phase-dependent wake-blockage interaction.

In this work, the inlet guide vanes are applied on a small axial flow fan.The inlet guide vanes with different outlet angle are designed, which are connected with the casing and set up on the upstream of the impeller of the prototype fan. The optimal inlet guidevanesare selected according to the theoretical analysis through the calculation of the flow field. The performances of the fan with optimal inlet guide vanes are compared with those of the prototype fan with the help of the simulation and the experiment. The research results are benefit for parameter optimization and noise prediction of small axial flow fan with inlet guide vanes.

# Research method

# Design of inlet guide vanes

A small axial flow fan as shown in Fig.1 is regarded as the prototype fan, whose main parameters are listed in Table 1.In order to reduce the axial length of the casing and simplify the model, four arc plate inlet guide vanes with different outlet angle are designed and set up on the upstream of the impeller of the prototype fan. The geometric model of the fan with inlet guide vanes is shown in Fig.2 and its main parameters are listed in Table 2. The outlet angles of inlet guide vanes are set to $3 0 ^ { \circ }$ $4 5 ^ { \circ }$ $6 0 ^ { \circ }$ and $7 5 ^ { \circ }$ ,respectively. The width of the casing of four fans with inlet guide vanes is equal, so, they can be compared with each other.

![](images/c83704e4d2605ee6350b4e5fb6cd95a37546feeba654d6bc81942b7633fca569.jpg)  
Fig.1Prototype fan.

Table1Main parameters of the prototype fan   

<html><body><table><tr><td>Main parameters</td><td>Value</td></tr><tr><td>External diameter (mm)</td><td>85</td></tr><tr><td>Hub ratio</td><td>0.72</td></tr><tr><td>Stagger angle (°)</td><td>27.7</td></tr><tr><td>Blade number</td><td>5</td></tr><tr><td>Blade chord length (mm)</td><td>28</td></tr><tr><td>Tip clearance (mm)</td><td>2</td></tr><tr><td>Rated condition (kg/s)</td><td>0.01</td></tr><tr><td>Rated rotational speed (r/min)</td><td>3000</td></tr></table></body></html>

![](images/279d71d6b6619dd39a7fde7ec2e9af78f659be528940bb99855d0f01c74fb1a3.jpg)  
Fig.2 Geometric model of the fan with inlet guide vanes.

Table 2Main parameters of the fan with inlet guide vanes   

<html><body><table><tr><td>Main parameters</td><td>Value</td></tr><tr><td>Blade height (mm)</td><td>14</td></tr><tr><td>Vane number</td><td>6</td></tr><tr><td>Inlet angle (°)</td><td>0</td></tr><tr><td>Outlet angle α (°)</td><td>30,45,60,75</td></tr><tr><td>toiaditae</td><td>12</td></tr></table></body></html>

# Simulationforstaticcharacteristics

The steady flow was simulated by the calculations of Reynolds averaged Navier-Stokes equations coupled with RNG k-epsilon turbulence model. The standard wall function was used to deal with the regions near the wall. The SIMPLE algorithm was adopted to couple pressure and velocity. The second order upwind difference scheme was selected to discrete the governing equations. The computational domain of the prototype fan and the fan with inlet guide vanes are shown in Figs.3(a) and 3(b), respectively. In order to make these two kinds of fans compare with each other, the computational domains are both divided into the inlet region,the outlet region, the rotating fluid region and the casing region. The inlet region is a hemisphere with radius $\mathrm { R _ { h } } = 8 5 \ \mathrm { m m }$ .The outlet regionisa cylinderwith radius $\mathrm { R _ { c } } = 1 7 0 \ \mathrm { m m }$ and extends to $5 0 0 ~ \mathrm { m m }$ to ensure that the fluid through the fan has beenfully developed. The mass flow rate at the inlet was controlled and the pressure at the outlet was set to atmospheric pressure.

![](images/c4006b16a9f8b7a68e75bd119e5afdeb17229409e33d367931847744e8058c47.jpg)  
Fig.3Computational domain of fans.

# Simulation foraerodynamic noise

The large eddy simulation (LES） and Ffowcs Williams-Hawkings (FW-H) noise model were adopted for unsteady simulation and aerodynamic noise prediction The solution obtained by the steady simulation at the rated condition $\mathrm { ( Q { = } 0 . 0 1 ~ k g / s ) }$ was regarded as the initial condition of large eddy simulation.The finite volume method was used to disperse the filtered Navier-Stokes equations. The PISO algorithm was applied for coupling pressure and velocity. The second order central difference scheme was selected to couple the momentum equation In order to solve the interaction of interfaces, the dynamic grid method was used in the interfaces between the rotating fluid region and the casing region.

In order to analyze the aerodynamic noise characteristics at different locations after introducing the noise model, the coordinate system was established with the center of the impeller as the origin.A near field monitoring point M1 $( 0 , 0 , 1 0 . 5 )$ and a far field monitoring point M2(0,0, 1009.5) were set at the positions of $1 \mathrm { m m }$ and 1 m away from the impeller on the positive rotational axis, respectively.

# Selection of optimal inlet guide vanes

According to the simulation results,the optimal inlet guide vanes are selected among four inlet guide vanes with different outlet angle in this section,which have the best static characteristics and the best noise reduction effect.

Fig.4 shows the variation of static pressure with $\mathfrak { a }$ .It can be seen that the static pressure of the fan with inlet guide vanes first increases and then decreases with the increasing of $\mathfrak { a }$ at the rated condition.Besides,all of the static pressure of the fans with inlet guide vanes is higher than that of the prototype fan as shown in the dotted line in the figure.The static pressure of the fans with inlet guide vanes with $\scriptstyle \mathbf { q } = 4 5 ^ { \circ }$ and $\scriptstyle { \mathfrak { a } } = 6 0 ^ { \circ }$ is the largest,whose maximal values are both close to $1 3 . 5 \ \mathrm { P a }$ ，itis $2 . 8 \ \mathrm { P a }$ higher than that of the prototype fan.

![](images/f3cfb90966cc293497d6c152763c23c9a79dd6df977067a258dd62ec40470659.jpg)  
Fig.4Variation of static pressure with $\mathfrak { a }$

Fig.5 shows the variation of efficiency with $\mathfrak { a }$ .It can be observed from the figure that the efficiency of the fan with inlet guide vanes first increases and then decreases with the increasing of $\mathfrak { a }$ at the rated condition.When $\scriptstyle { \mathfrak { a } } = 3 0 ^ { \circ }$ , the efficiency of the fan with inlet guide vanes is lower than that of the prototype fan. When $\scriptstyle { \mathfrak { a } } = 7 5 ^ { \circ }$ ，the efficiency of the fan with inlet guide vanes is equal to that of the prototype fan. For the fans with inlet guide vanes with $\scriptstyle \mathbf { q } = 4 5 ^ { \circ }$ and $\scriptstyle { \mathfrak { a } } = 6 0 ^ { \circ }$ ,the efficiency increases that of the prototype fan by $2 . 9 \%$ and $1 . 5 \%$ ,respectively.

![](images/0ffd8ac41fe7aeb040c91a74cf6d705fa0dd811fe93142f88075a485c88b2629.jpg)  
Fig.5Variation of efficiency with $\mathfrak { a }$

Fig.6 shows the variation of the overall sound pressure level (SPL) at both monitoring points with α. For the monitoring point M1,the overall SPL of four fans with inlet guide vanes is all lower than that of the prototype fanat the rated condition,which illustrates that the inlet guide vanes are help for reducing effect on the noise at the near field.When $\scriptstyle { \mathfrak { a } } = 6 0 ^ { \circ }$ ,the overall SPL of the fan is the lowest, which is lower than that of the prototype fan by 3.4 dB.When $\scriptstyle { \mathfrak { a } } = 4 5 ^ { \circ }$ ,the overall SPL of the fan is the second lowest, which is lower than that of the prototype fan by $2 . 3 ~ \mathrm { d B }$ . For the monitoring point M2,at the rated condition, the overall SPL of four fans with inlet guide vanes do not change significantly,which means that the inlet guide vanes have little effect on the noise at the far field.

![](images/a9b655c5d3ed27f95002713a7a52ea1f7fca6c9636f5f268306dbdeb77e5c0e3.jpg)  
Fig.6Variation of overall SPL with $\mathfrak { a }$ at both monitoring points.

Taking into account the static pressure, the eficiency, the overall SPL at the monitoring points M1 and M2 of these fans reasonably, the inlet guide vanes with $\scriptstyle { \mathrm { \mathfrak { a } } } = 6 0 ^ { \circ }$ are regarded as the optimal inlet guide vanes.

# Comparison of simulation results

# Staticcharacteristics

Fig.7 shows the comparison of static characteristic curves between the fan with optimal inlet guide vanes and the prototype fan, including static pressure (P-Q) curve in Fig.7(a) and efficiency $( \eta - \mathrm { Q } )$ curve in Fig. 7(b).

![](images/9bad7ad00892c18da078e64362782bdad4c17b85fabf9c79ce049565cc349b67.jpg)  
Fig.7Static characteristic curves.

From Fig. 7(a), we can see that the static pressure of of the prototype fan at all conditions. For the prototype the fan with optimal inlet guide vanes is larger than that fan,the static pressure decreases rapidly with the in

creasing of the flow rate when $\mathrm { Q { < } 0 . 0 0 5 ~ k g / s }$ and reaches minimal value $7 \mathrm { \ P a }$ when $\mathrm { Q { = } 0 . 0 0 5 ~ k g / s }$ . The static pressure increases slowly with the increasing of the flow rate when $0 . 0 0 5 ~ \mathrm { { \ k g / s / Q / c 0 . 0 1 1 } ~ \mathrm { { \ k g / s } } }$ and reaches maximal value $1 0 . 6 \ \mathrm { P a }$ when $\mathrm { Q { = } 0 . 0 1 1 ~ k g / s }$ When $Q { > } 0 . 0 1 1 ~ \mathrm { k g / s }$ the static pressure decreases with the increasing of the flow rate.The decrease rate becomes faster when $\mathrm { Q { > } 0 . 0 1 2 \ k g / s }$ ：

From Fig.7(b) we can observe that the efficiency of the fan with optimal inlet guide vanes is larger than that of prototype fan at all conditions.The efficiency of both fans shows a growth trend with the increasing of the flow rate when $Q { < } 0 . 0 1 2 ~ \mathrm { { \ k g / s } }$ and reaches maximal value when $\mathrm { Q { = } 0 . 0 1 2 ~ k g / s }$ . The maximal efficiency of the prototype fan exceeds $22 \%$ ，while the maximal efficiency of the fan with optimal inlet guide vanes is close to $2 7 \%$ When $Q { > } 0 . 0 1 2 ~ \mathrm { k g / s }$ ,the efficiency of both fans decreases rapidly with the increasing of the flow rate.

Fig.8 shows the variation of the torque with the flow rate.It can be seen from the figure that the torque of the fan with optimal inlet guide vanes is larger than that of the prototype fan at all conditions.According to the formula of the efficiency, the larger the torque is,the smaller the efficiency of the fan is in the case that the static pressure is constant. Compared with the prototype fan, the torque of the fan with optimal inlet guide vanes is larger while the efficiency of the fan with optimal inlet guide vanes is larger.Itis indicated that the static pressure has a greater impact on the efficiency than the torque.

![](images/e8c6b80ea6297b4843df715745130f9ecd38957b6e5287a52e8e85b6d399ede0.jpg)  
Fig.8Variation of torque with flow rate.

In summary, the static characteristics of the fan are improved significantly after installing the optimal inlet guide vanes.Thus the work capacity is improved and the power consumption is reduced.

# Aerodynamicnoise

Fig.9 shows the variation of the overall SPL with the rotational time at both monitoring points(T is the rotational period of the fan).It can be seen that the overall SPL of both fans at the monitoring point M1 decreases with the increasing of time when $\scriptstyle \mathrm { T } < 5 \mathrm { T }$ and remains constant when $\mathrm { T } { > } 5 \mathrm { T }$ ，which means the internal flowreaches a relatively stable state when $\mathrm { T } { > } 5 \mathrm { T }$ 、At the monitoring point M1, the overall SPL of the fan with optimal inlet guide vanes is lower than that of the prototype fan and the gap is about $4 . 2 \ : \mathrm { d B }$ . Compared with the prototype fan at the monitoring point M2,the overall SPL of the fan with optimal inlet guide vanes is lower when $\mathrm { t } { < } 5 \mathrm { T }$ while higher when $\mathrm { T } { > } 5 \mathrm { T }$ .However, the gap of the overall SPL between both fans at the monitoring point M2 is very small.

![](images/f9008f5ddc724866b590cb4386a5ffcf48b0688a0b5cd3ab3f53f7a616b61db4.jpg)  
Fig.9Variation of overall SPL with rotational time at both monitoring points.

Fig.1O shows the overall SPL in different axial positions.The same variation trends of the overall SPL of both fans along the axial direction are shown in the Figure. When $1 0 . 5 \ \mathrm { m m < z < 2 0 0 \ \mathrm { m m } }$ ,the overall SPL of the fan with optimal inlet guide vanes along the axial direction is lower than that of the prototype fan, and the overall SPL of both fans decreases rapidly with the increasing of z.The reducing noise at these positions is mainly discrete noise.When $\mathrm { \Delta } z { > } 2 0 0 ~ \mathrm { m m }$ ，the overall SPL of the fan with optimal inlet guide vanes is higher than that of the prototype fan, but the gap is not more than $0 . 4 ~ \mathrm { d B }$ .Although the overall SPL of both fans along the axial direction still decreases with the increasing of $z$ ，the downtrend rate decreases significantly. The reducing noise at these positions is mainly broadband noise.

![](images/ecbf297bd2295da4fedc96b602fecb17c85b682e4ef9b8e8cd603629a7b616b1.jpg)  
Fig.10 Overall SPL along the axial direction in the downstream of fans.

Fig.11 shows the overall SPL along the radial direction on the section $\mathrm { z } { = } 1 0 . 5 ~ \mathrm { m m }$ .It can be seen from the figure that the overall SPL of the fan with optimal inlet guide vanes is lower than that of the prototype fan in each of the radial positions.The samevariation trends of the overall SPL of both fans along the radial direction are shown in the figure.With the decreasing of r, the overall SPLof both fans increases to the maximum value, then decreases to the relatively stable value.The maximal overall SPL of the fan with optimal inlet guide vanes is lower than that of the prototype fan but the radial positions are both located in the 1/3 of the blade height.

![](images/2846156e8aaaf4c8b6bf640fe8b29afe3768a85c39e88b54444823656ab69e3d.jpg)  
Fig.11 Overall SPL along the radial direction on the section $\mathtt { z } { = } 1 0 . 5 \ \mathrm { m m }$ ：

Fig.12 shows the power spectral density(PSD) at the monitoring point M1.It can be observed that the maxim al PSD of the prototype fan appeared at $2 0 0 \mathrm { H z }$ whose value is $0 . 1 1 ~ \mathrm { W / H z }$ .While the peak of PSD of the fan with optimal inlet guide vanes decreases to $0 . 0 5 ~ \mathrm { W / H z }$ When the frequency exceeds $1 0 0 0 ~ \mathrm { H z }$ ，the PSD of both fans is close to zero.

![](images/2ebf1bf53a9c84c407518b7371f775e7a71377d1a6bd1053a7a4dc0b64de89d8.jpg)  
Fig.12PSD at the monitoring point M1.

Fig.13 shows the A-weighted SPL of1/3 octave band at the monitoring point M2.From the figure we can see that the A-weighted SPL of the fan with optimal inlet guide vanes is lower than that of the prototype fan in $0 { \sim } 3 0 0 0 ~ \mathrm { H z }$ frequency band and the maximal noise reduction is more than 5 dBA.However, the A-weighted SPL of the fan with optimal inlet guide vanes is higher than that of the prototype fan in $3 0 0 0 { \sim } 2 0 0 0 0 ~ \mathrm { H z }$ frequency band except $5 5 0 0 { \sim } 7 0 0 0 ~ \mathrm { H z }$ frequency band and the big gest gap is appeared in $1 1 0 0 0 { \sim } 1 4 0 0 0 \mathrm { H z }$ frequency band.

![](images/667fe071bdd8b3b4e994d806ccf01bb68c45012790a694b2f643fac53c1e17a9.jpg)  
Fig.13 A-weighted SPL of $1 / 3$ octave band at the monitoring point M2.

# Internal flow characteristics

Fig.14 shows the static pressure contour on the meridian plane $( \mathrm { X } { = } 0 )$ . It can be seen that the static pressure in the inlet region of the fan with optimal inlet guide vanes is lower than that of the prototype fan.However, the static pressure in the outlet region of both fans mainly ranges from ${ \bf - 5 } \mathrm { \bf ~ P a }$ to O.Thus compared with the prototype fan, the fan with optimal inlet guide vanes shows the better performance in static pressure.The area of low pressure on the suction side of the fan with optimal inlet guide vanes is larger than that of the prototype fan and the minimal pressure zone appears near the tip and the hub at the same time.On the pressure side,the area of high pressure of the fan with optimal inlet guide vanes occupies 1/3 of the whole blade length,while only 1/5 of the whole blade length for the prototype fan. Therefore, the fan with optimal inlet guide vanes has the better acting ability than the prototype fan.

Fig.15 shows the distribution of the axial velocity on the rotational axis. Compared with the prototype fan, the axial velocity of the fan with optimal inlet guide vanes is larger when $z { < } 0$ and the maximal axial velocity of the fan with optimal inlet guide vanes is approximately two times larger.The flow is accelerated before it enters the impeller due to the effectofthe inlet guide vanes,thus the ventilation of the fan increases.The negative axial velocity appears in the downstream of the impeller near the hub,which indicates that the direction of the flow in this region is contrary to that of the main flow and forms theinverse flow.Theabsolutevalueof themaximal axial velocity of the fan with optimal inlet guide vanes is lower than that of the prototype fan in this region. It is concluded that the inverse flow at the downstream of the prototype fan is more intense.

![](images/05cb1b115b2065db54e32055e4147fe1be5b52d952a97d07b59f907fc5b2953b.jpg)  
Fig.14 Contours of static pressure on the meridian plane $( \mathrm { X } \mathrm { = } 0 )$ 1

![](images/1e78bb80fa53b4f8ffc56bf5d0b1911b8ac3e6d690bcfe1fb36194ef7862adfd.jpg)  
Fig.15Distribution of axial velocity on the rotational axis.

Fig.16 shows the total pressure fluctuation at the monitoring point M1.According to the above section, both fansreacha relatively stable state when $\mathrm { t } { > } 5 \mathrm { T }$ So the total pressure fluctuation during the time ranges from 5T to 8T is selected here.The total pressure fluctuation of both fans does not show the obvious periodic variation even appears about four peaks in each rotational period. This is the reason why the frequency of the peak of PSD is $2 0 0 ~ \mathrm { H z }$ at the monitoring point M1.Although the extreme differences of the total pressure fluctuation of both fans are the same,the fluctuation of the fan with optimal inlet guide vanes is more like an equal amplitude oscillation than that of the prototype fan.

![](images/20d3a7a48879e5fb991fdbc2ce759a4ecdb1142e85399b42002aff683aa11243.jpg)  
Fig.16Total pressure fluctuation at the monitoring point M1.

![](images/01e2f1c61f02055aed3c01d8ca71f7d88ce28186003212786d59dad5bfd916ab.jpg)  
Fig.17Radial cross section $\scriptstyle \mathrm { R = } 4 2 . 4 \ \mathrm { m m }$ (near the blade tip).

![](images/09194877b62a15f81ac13266d5fce4a7c8912c2e1ece31daf197a73bcb95ff06.jpg)  
Fig.18Contours of vorticity on the radial cross section $\scriptstyle \mathrm { R = } 4 2 . 4 \mathrm { m m }$ at different time.

The radial cross section $\mathrm { R } { = } 4 2 . 4 \ \mathrm { \ m m }$ is selected to study the variation of the vorticity as shown in Fig.17 Fig.18 shows the vorticity contours on the radial cross section $\scriptstyle \mathrm { R = } 4 2 . 4 \ \mathrm { m m }$ at different time,where the vorticity contours at the moment of 7T, $7 \mathrm { T } { + } 3 \mathrm { T } / 5$ and 8T are regarded as the representatives.The blade in the red frame is regarded as the object of observation.It can be seen by comparing Fig.18(a) and (b),(c) and (d),(e) and (f) that a large number of vortices gather on the suction side of both fans at different time,showing the escape tendency from the surface.The distribution and the magnitude of vorticity of both fans are basically similar to each other.

The maximal vorticity is close to the surface of blade whose value is more than $3 0 0 0 0 ~ \mathrm { { s } ^ { - 1 } }$ . By comparing Fig 18(a),(c), (e) and (b), (d),(f),the similar variations of vorticity of both fans are shown in their rotational processes.The vortex first gathers in the leading edge of the blade, then moves along the suction side of the blade and finally escapes from the surface.

# Experimental results

# Static characteristic experiment

In order to verify the reliability of simulation for static characteristics,static pressure of the fan with optimal inlet guide vanes and the prototype fan was tested in the wind tunnel as shown in Fig.19.The optimal inlet guide vanes and their installation are shown in Fig.20.

![](images/7fce95828d4acfa885700d55114933713a4f3fc2465404196499d0271d45cf5b.jpg)  
Fig.19Wind tunnel used for the experiments.

![](images/557d4b2075ad39e45e0bd59a05fc9ac8a4c6c315dabe565e4f28cc50b5554924.jpg)  
Fig.20Optimal inlet guide vanes and their installation.

Fig. 21 shows the comparison of P-Q curve of the prototype fan between simulation and experiment. The results of simulation and experiment are in good agreement with each other,especially at the stable operation condition ranging from $0 . 0 0 5 ~ \mathrm { k g / s }$ to $0 . 0 1 1 ~ \mathrm { k g / s }$ ，which confirms the reliability of the simulation.

![](images/5b67db3cccaa5f474d671f562fcee93ccba5c9391919f423a3154da79ce8d5af.jpg)  
Fig.21 Comparison of P-Q curve of prototype fan between simulation and experiment.

Fig. 22 shows the experimental results of the P-Q curve.The same variation trends of both fans are observed from the figure.The static pressure decreases sharply at first,then increases slowly and finally decreases with the increasing of the flow rate. The static pressure of the fan with optimal inlet guide vanes is larger than that of the prototype fan at the stable conditions ranging from $0 . 0 0 5 ~ \mathrm { k g / s }$ to $0 . 0 1 1 ~ \mathrm { k g / s }$ .Combined with simulation and wind tunnel experiment, it can be concluded that the optimal inlet guide vanes can improve the static characteristics of the prototype fan.

![](images/40fe810af3181fc4894cebc035e29a581d4f6e92c153662c24b7285896ba438e.jpg)  
Fig.22Experimental results of the P-Q curve.

# Noise experiment

In order to verify the reliability of the simulation results for aerodynamic noise,noise experiment of the fan with optimal inlet guide vanes and the prototype fan was carried out in a semi-anechoic room whose structure size is $5 \mathrm { m } { \times } 4 \mathrm { m } { \times } 3 . 5 \mathrm { m }$ .The background noise is 21.5 dB.The experimental device for noise measurement is shown in Fig. 23.

![](images/9a2bf2c903386d62951f5e88bfbda9ec94be9e61a52d921eabffc99d4a27d224.jpg)  
Fig.23The experimental device for noise measurement.

Fig. 24 shows the measured overall SPL along the axial direction in the downstream of fans.It can be seen that the largest difference of the overall SPL between the fan with optimal inlet guide vanes and the prototype fan is located at the near field measuring point,where is 1 mmaway from the outlet of the fan in the axial direction. The value of largest difference is approximately 2 dB. With the increasing of the axial distance between the measuringpoint and the fan, the overall SPL ofboth fans decreases quickly at first, then the variation tends to be stable.The values of the overall SPL of both fans are almost the same at the far field measuring point where is $1 \mathrm { ~ m ~ }$ away from the outlet of fan in the axial direction. The difference between experimental data and simulation results exists,while the experimental data of the fan with optimal inlet guide vanes and the prototype fan have comparability. Through the noise experiment,itis further proved that the optimal inlet guide vanes can reduce the noise at the near field of small axial flow fan,but the effect on the noise at the far field is very little.

![](images/864fda6bc56f6c6bb24aeb651840164e46bca485f9cddcc3b54faacb2492d672.jpg)  
Fig.24Measured overall SPL along the axial direction in the downstream of fans.

# Conclusions

In this paper, effects of the inlet guide vanes on the performance of a small axial flow fan are studiedon three aspects including static characteristics,aerodynamic noise and internal flow characteristics.The inlet guide vanes with different outlet angle are designed, which are mounted on the casing and located in the upstream of the impeller of the prototype fan.The conclusions are summarized as follows:

(1)The static pressure and the efficiency of the fan with inlet guide vanes both first increase then decrease with the increasing of the outlet angle of inlet guide vanes at the rated condition. Compared with the prototype fan, the overall SPL of four fans with inlet guide vanes is lower at the near field, but the inlet guide vanes have little effect on the overall SPL at the far field.The inlet guide vanes with outlet angle of $6 0 ^ { \circ }$ have the optimal noise performance under the condition that the static characteristics are improved.

(2) The static pressure and the efficiency of the fan are improved significantly after installing the optimal inlet guide vanes at all conditions.

(3) The fluctuation of total pressure of the fan with optimal inlet guide vanes is more like an equal amplitude oscillation than that of the prototype fan at the near field. Therefore,compared with the prototype fan, the overall SPL of the fan with optimal inlet guide vanes at the near field is lower.

(4) The distribution and the magnitude of the vorticity near the blade tip of the fan with optimal inlet guide vanes and the prototype fan are basically similar to each other at different time.Besides,similar variations of the vorticity near the blade tip of both fans are observed in their rotational processes.Thus,the gap of the overall SPL between the fan with optimal inlet guide vanes and the prototype fan at the far field is very small.

# Acknowledgement

This work was supported by National Natural Science Foundation of China (No．51276172)，Public Welfare Technology Application Projects of Zhejiang Province (No.2015C31002)，Open Foundation of Zhejiang Pro vincial TopKey AcademicDiscipline ofMechanical En gineering and Zhejiang Sci-Tech University Key Laboratory(ZSTUME O1A04),and Zhejiang Province Science and Technology Innovation Team Project (2013TD18).

# References

[1]Chu,W.,Lin,P., Jin,Y., Simulation and Experiment ResearchofAerodynamic Performance of Small Axial Fans WithStruts,Journal of Thermal Science, vol.25, pp.216-222,(2016).   
[2]Zhang L., Jin Y.,An Investigation on the Effects of Irregular Airfoils on the Aerodynamic Performance of Small Axial Flow Fans,Journal of Mechanical Science and Technology, vol.27,pp.1677-1685,(2013).   
[3]Wu,B.,The Match of Rotor and Stator Blades and the Disposition of Axial Distance for Axial Fan, Compressor Blower& Fan Technology,vol.6,pp.13-14,(2002).   
[4] Wallis,R.A.,Axial Flow Fans and Ducts,John Wiley, vol.3,pp.302-322,(1983).   
[5] Sirakov,B.T.,Tan,C.S.Effects ofUpstream Unsteady Fow Conditions on Rotor Tip Leakage Flow,ASME GT2002-30358,vol.5,pp.311-321,(2002).   
[6]Jesus,M.F.，Analysis of the Deterministic Unsteady Flow in a Low-Speed Axial Fan With Inlet Guide Vanes, Journal ofFluids Engineering,vol.130,pp.1-12,(2008).