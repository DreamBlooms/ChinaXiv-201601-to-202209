# Application of SALTMED and HYDRUS-1D models for simulations of soil water content and soil salinity in controlled groundwater depth

Masoud NOSHADI\*, Saghar FAHANDEJ-SAADI, Ali R SEPASKHAH

Department of Irrigation, Shiraz University, Shiraz 71441-65186,Iran

Abstract: Salinization is a gradual process that should be monitored. Modeling is a suitable alternative technique that saves time and cost for the field monitoring. But the performance of the models should be evaluated using the measured data. Therefore,the aim of this study was to evaluate and compare the SALTMED and HYDRUS-1D models using the measured soil water content, soil salinity and wheat yield data under different levels of saline irrigation water and groundwater depth.The field experiment was conducted in 2013 and in this research three controlled groundwater depths,i.e.,60 (CD60),80 (CD80) and 10O (CD10O) cm and two salinity levels of irrigation water,i.e.,4 (EC4) and 8 (EC8) $\mathrm { d } \mathrm { S } / \mathrm { m }$ were used in a complete randomized design with three replications. Soil water content and soil salinity were measured in soil profile and compared with the predicted values by the SALTMED and HYDRUS-1D models. Calibrations of the SALTMED and HYDRUS-1D models were caried out using the measured data under EC4-CD10O treatment and the data of the other treatments were used for validation. The statistical parameters including normalized root mean square error (NRMSE) and degree of agreement (d) showed that the values for predicting soil water content and soil salinity were more accurate in the HYDRUS-1D model than in the SALTMED model. The NRMSE and $d$ values of the HYDRUS-1D model were $9 . 6 \%$ and O.64 for the predicted soil water content and $6 . 2 \%$ and O.98 for the predicted soil salinity, respectively. These indices of the SALTMED model were $10 . 6 \%$ and O.81 for the predicted soil water content and $1 1 . 0 \%$ and O.97 for the predicted soil salinity, respectively. According to the NRMSE and $d$ values for the predicted wheat yield ( $9 . 8 \%$ and O.91,respectively) and dry matter $( 2 . 9 \%$ and 0.99, respectively)，we concluded that the SALTMED model predicted the wheat yield and dry matter accurately.

Keywords: wheat; yield; dry matter; simulation; normalized root mean square error

# 1Introduction

In many parts of the world, salt concentration in groundwater is increasing and soil salinization could be occurred due to the decreasing water table depth and increasing capillary rise, especially in area with unsuitable drainage systems.Therefore, in the irrigated areas, groundwater depth has the utmost importance in controlling soil salinity and waterlogging，and improving plant environment. On the other hand, in arid regions,where the water resources are limited, a gap exists between the water supply and the increased water demands.In this situation,controlled groundwater depth is one of the modern techniques that may remediate the problem of water scarcity. In this method,the level of groundwater rises in the soil and gets close to the root zone, therefore， plant can use the groundwater more effectively. The efficiencies of controled groundwater depth were studied by many researchers (Asseng et al., 2OOla, b; Ayars et al., 2006; Steppuhn et al.，2Ol6) and it was concluded that the transition from uncontroled groundwater depth to controlled system was in response to environmental concerns and the need for improving water management. This is due to the fact that the controlled system provides flexibility in controlling over a wide range of groundwater depth and may be used for managing soil salinity and water use from shallow groundwater.

Khalil et al. (2OO4) studied the effect of controlled drainage on crop yield,soil salinity and irrigation water. In this research, they compared the rice production and water requirement under two drainage management treatments including conventional drainage and controlled drainage systems. Their results showed that the controlled drainage system and controlled water table depth had no significant positive effect on the rice production or the soil salinity. However, water requirement under the controlled drainage system was $2 5 \%$ less than that in the conventional drainage system. They reported that applying controlled drainage in rice fields have saved about $1 { \times } 1 0 ^ { 9 } \mathrm { \ m } ^ { 3 }$ of water per year.

In general, irrgation with saline water reduces crop yield and grain quality; however, there are some strategies to lower the yield reduction under saline conditions.Jiang et al. (2Ol2) studied the effects of irrigation water depth, including 375,300 and $2 2 5 ~ \mathrm { { m m } }$ (W1, W2 and W3, respectively) and water salinity up to $6 . 1 ~ \mathrm { d S / m }$ on water consumption and water productivity of spring wheat from 20O8 to 2O1O. The highest yield at the same salinity level under saline irrigation water was obtained in W2( $( 6 . 9 \ \mathrm { M g / h m } ^ { 2 } )$ ）treatment,also the water use efficiency (WUE) $( 1 . 2 5 { - } 1 . 6 3 \ \mathrm { k g } / \mathrm { m } ^ { 3 } )$ （204 and irrigation water use efficiency (IWUE) $( 2 . 1 1 { - } 2 . 3 6 ~ \mathrm { k g } / \mathrm { m } ^ { 3 } )$ in W2 treatment were higher than those in W1 treatment.

Due to the scarcity of surface water resources,especially during dry season, crops are largely irrigated using the saline groundwater and drainage water. There are several studies indicating that brackish water can be successfully used for irrigation during crop production， however, negative efects on crop production may occur due to the accumulation of salts in the soil (Wang et al.,2O15).Liu et al. (2O16) found that it was useful by using saline water resources for irrigation during jointing stage of winter wheat in northern China and the yield of winter wheat and summer maize doubled. They mentioned that sufficient fresh water irrigation (i.e., $6 0 { - } 9 0 ~ \mathrm { m m } )$ during sowing stage of summer maize is necessary to avoid the negative effects of saline irrigation water and guarantee good growth conditions during the early sensitive growing period.

Ma et al. (2oo8) described crop responses to saline irrigation water based on field experiments. The results showed that the $\mathrm { E C _ { \mathrm { e } } }$ (saturated paste electrical conductivity) of the top soil $( 0 { - } 1 0 0 \ \mathrm { c m } )$ （20 was $40 \%$ higher than that in the subsoil $( 1 0 0 - 1 8 0 ~ \mathrm { c m } )$ under saline irrigation water. Also the salt load rapidly increased, especially in the upper $8 0 \ \mathrm { c m }$ . It was concluded that the maximum soil depth that was leached during the wet season was about $1 5 0 \mathrm { c m }$

Previous researches confirmed that saline irrigation water appears to be economically attractive to farmers in a short term and ecological hazards can be controlled with the proper salt leaching in soil. It seems that the usage of field experiments in a short time would not be appropriate criteria for decision making.Therefore, the usage of modelling is a suitable alternative for field experiments that save time and cost.

In the past decade，the SALTMED model has been used for the integrated field water management (Ragab,2OO2a, b). The SALTMED model is a physically based model that includes key processes of evapotranspiration, plant water uptake, water and solute transport under different irrigation systems, nitrogen application rates,water qualities and relationship between crop yield and water use (Ragab, 2O02a, b; Ranjbar et al., 2015).

Many researchers have used the SALTMED model to simulate the plant growth and yield for many crops, such as sugar beet,carrots, kale,quinoa and tomatoes (Malash et al.,2O11; El-Shafie et al.,2017; Silva et al.， 2O17). They concluded that the SALTMED model could accurately predict the soil salinity and crop yield under salinity conditions.The SALTMED model was used for simulation of the yield and dry matter of wheat under different depths of irrigation and systems,i.e., sprinkler and basin systems (Razzaghi and Ghannadi, 2O16). The wet, medium and dry treatments were considered as irrgation treatments.The results showed that the SALTMED model predicted the wheat yield and dry matter accurately,for both irrigation systems.However, the soil water content was predicted better in sprinkler irrigation system than in basin irrigation method.The SALTMED model was used for simulation of the yield and dry matter of quinoa, as a drought-tolerant crop,under four irrigation levels, i.e., $100 \%$ (control treatment), $7 5 \%$ ， $50 \%$ and $2 5 \%$ of the crop water requirement by Koutar et al. (2O17). The SALTMED model was calibrated using the control treatment data and then it was evaluated by the data of the other treatments. The results showed that the SALTMED model simulated the total dry matter and grain yield for the quinoa under different deficit irrigation regimes with a reasonable precision.

The HYDRUS-1D model is another advanced one-dimensional model associated with water, salt and heat movement in the soil (Simunek et al., 2008; Luo at al., 2010; Zeng at al., 2014; Noshadi et al., 2O17). The HYDRUS-1D software package contains a wide range of approaches that can be selected for simulating variable saturated water flow and solute transport，and considers one-dimensional problems associated with,for example, soil columns,lysimeter, soil profile and plots. In addition to the basic water flow and solute transport processes, HYDRUS-1D can also simulate the transport and production of carbon dioxide and transport of major ions. Furthermore,a wide range of non-equilibrium flow and transport modelling approaches are available in this model (Simunek et al., 2O08). Jha et al. (20l7) and Shahrokhnia and Sepaskhah (2018) simulated the water and nitrogen (N) transport using the HYDRUS-1D model on paddy in a sandy loam soil in India and rapeseed and saflower in a clay loam soil in Iran. The result revealed that this model could simulate the variations of water pressure head and N concentration in soil with the good precision.

As mentioned above,models are effective tools in simulating the efects of different environmental conditions,such as salinity of irrigation water on crop yield. There are many models,such as LEACHC,UNSATCHEM, SWAP (Soil-Water-Plant-Atmosphere)， SALTMED and HYDRUS-1D that were developed to simulate these conditions.Although the SALTMED and HYDRUS-1D models are known as powerful tools, comparison of the accuracy of these models in simulating the sol salinity and soil water content in shallow groundwater condition have not been investigated. Therefore, the aim of this study was to evaluate and compare the SALTMED and HYDRUS-1D models in simulating the soil water content and soil salinity, also to evaluate the SALTMED model in simulating the wheat yield under different levels of saline irrigation water and groundwater depth.

# 2 Materials and methods

# 2.1Field experiment

This research was conducted in the College of Agriculture, Shiraz University $( 3 6 ^ { \circ } 2 9 \mathrm { { N } }$ ， $3 2 ^ { \circ } 5 2 ^ { \prime } \mathrm { E }$ $1 8 1 0 \mathrm { m }$ a.s.l.), located in a distance of $1 6 \mathrm { k m }$ from the Shiraz City, Iran in 2O13.Wheat seeds with a density of $2 0 0 \mathrm { k g } / \mathrm { h m } ^ { 2 }$ were planted in 18 soil columns (lysimeters） with the $1 2 0 \ \mathrm { c m }$ height and $4 0 \mathrm { c m }$ diameter. Soil physical characteristics are shown in Table 1.

Table1Soil physical characteristics in different soil depths   

<html><body><table><tr><td rowspan="2">Depth (cm)</td><td rowspan="2">Soil texture</td><td>Clay</td><td>Silt</td><td rowspan="2">Sand</td><td rowspan="2">pH</td><td rowspan="2">BD (g/cm³)</td><td rowspan="2">FC (cm³/cm³)</td><td rowspan="2">PWP (cm³/cm³)</td></tr><tr><td></td><td>(%)</td></tr><tr><td>0-15</td><td>Clay loam</td><td>30</td><td>35</td><td>35</td><td>8</td><td>1.25</td><td>0.32</td><td>0.11</td></tr><tr><td>15-30</td><td>Clay loam</td><td>30</td><td>35</td><td>35</td><td>8</td><td>1.32</td><td>0.36</td><td>0.12</td></tr><tr><td>30-50</td><td>Clay loam</td><td>39</td><td>38</td><td>23</td><td>8</td><td>1.36</td><td>0.36</td><td>0.14</td></tr><tr><td>50-70</td><td>Clay</td><td>40</td><td>39</td><td>21</td><td>8</td><td>1.42</td><td>0.39</td><td>0.16</td></tr><tr><td>70-100</td><td>Clay</td><td>40</td><td>39</td><td>21</td><td>8</td><td>1.42</td><td>0.39</td><td>0.16</td></tr></table></body></html>

Note:BD,bulkdensity;FColumetricsoilwatercontentatfieldcapacity;WP,vometricsolwatercontentatpermanntilting point.

Three controlled groundwater depths including 60 (CD60),80 (CD80) and 100 (CD100） cm and two saline irrigation water treatments,i.e.,4 (EC4) and 8 (EC8) $\mathrm { d } \mathrm { S } / \mathrm { m }$ with three replications were considered as a complete randomized design. Therefore,18 soil columns were considered for treatments.Four exit pipes were installed at the depths of 30, 6O, 90 and $1 3 0 \ \mathrm { c m }$ from top of the soil columns for sampling groundwater and establishing the groundwater depths at desired levels. To establish the groundwater depths at 60,80 and $1 0 0 ~ \mathrm { c m }$ ， we entered water with a very low discharge from bottom of soil columns through pipe that was installed at $1 3 0 \ \mathrm { c m }$ depth. The water table depths were controlled by manometer tubes that were installed in the bottm side of the soil column. Groundwater level was measured in the manometer tube. When this level was below the desired groundwater table depth (6O, 80 or $1 0 0 \mathrm { c m }$ in different treatments),saline water was added using Marriott's bottle to keep the desired water table depth.These volumes of water were measured and considered as groundwater contribution (GC).

The groundwater salinity at the beginning of growing season was equal to fresh water salinity, i.e., $0 . 7 6 ~ \mathrm { d S / m }$ .During the growing season, all the soil columns were irrigated at the same time. Before all irrigation events,soil water content at different depths was measured by a portable time-domain reflectometer (TDR) in all soil columns.TDR probes were installed in different depths of soil columns to measure soil water content before each irigation event. Soil water content was measured at the depth of $3 0 \ \mathrm { c m }$ in CD6O treatment,at the depths of 2O and $6 0 ~ \mathrm { c m }$ in CD8O treatment and at the depths of 15,45 and $7 5 \ \mathrm { c m }$ in CD1OO treatment. We determined net irrigation water depth according to the following equation (Brouwer et al., 1989):

$$
D = ( \mathrm { F C } - \theta _ { \mathrm { v } } ) \times Z _ { \mathrm { r } } ,
$$

where $D$ is the net irrigation water depth (cm); $\theta _ { \mathrm { v } }$ is the volumetric soil water content within the root depth before irrigation $( \mathrm { c m } ^ { 3 } / \mathrm { c m } ^ { 3 } )$ ; FC is the volumetric soil water content at field capacity $( \mathrm { c m } ^ { 3 } / \mathrm { c m } ^ { 3 } )$ ；and $Z _ { \mathrm { r } }$ is the root depth (cm).In Equation 1, $Z _ { \mathrm { r } }$ is a time variable parameter that obtained from the following equation (Borg and Grimes,1986):

$$
Z _ { r } \ = \ ( 0 . 5 + \ 0 . 5 \mathrm { s i n } ( 3 . 0 3 ^ { D A _ { \mathrm { s } } } / D T _ { \mathrm { m } } \ ^ { } - \ 1 . 4 7 ) ) R D _ { \mathrm { m } } \ ,
$$

where $Z _ { \mathrm { r } }$ is the root depth at a given day (cm); $D A _ { \mathrm { s } }$ is the number of days after planting; $D T _ { \mathrm { m } }$ is the number of days to reach the maximum root depth, which was considered as $1 7 0 \mathrm { d }$ ，according to the wheat growth period; and $R D _ { \mathrm { m } }$ is the maximum depth of roots that was considered as 100, 80 and $6 0 \mathrm { c m }$ in CD100, CD80 and CD60 treatments.

The irrigation application efficiency $( E _ { \mathrm { a } } )$ was $80 \%$ . Therefore,the gross depth of irrigation water $( I _ { \mathrm { g } } )$ was calculated as follows (Brouwer et al., 1989):

$$
I _ { \mathrm { g } } = ( D / E _ { \mathrm { a } } ) \times 1 0 0 .
$$

We determined the applied irrigation water depth based on the differences between the calculated irigation water depth and sum of the groundwater contribution and precipitation.The applied irrigation water was measured by a flow meter for each irrigation event. The precipitation was measured in the climatological station near the study area, being about $5 0 0 \mathrm { m }$ away.

The saline water was made by adding NaCl and $\mathrm { C a C l } _ { 2 }$ in a ratio of 1:1 into the fresh water and the level of water salinity was measured by electrical conductivity meter. $\mathbf { N }$ was applied with a rate of $2 0 0 \mathrm { k g } / \mathrm { h m } ^ { 2 }$ urea through irrigation water in two steps,one at the planting time and another at 110 days after planting. At the end of growing season, the harvested wheats (seeds and dry matter） were oven dried and weighed. Also,soil was sampled in 15,45 and $7 5 \ \mathrm { c m }$ of soil depths and the $\mathrm { E C _ { \mathrm { e } } }$ was determined.

# 2.2 Models

# 2.2.1 HYDRUS 1-D model

Input parameters in the HYDRUS 1-D model included soil profile data， soil hydraulic characteristics，boundary conditions of water flow，solute transport parameters and related boundary conditions, root water and solute uptake model, and evapotranspiration data.

Water movement for the experimental situation is described by a modified form of the Richards equation using the assumptions that the air phase plays an insignificant role in the liquid flow

process and that water flow due to thermal gradients can be neglected:

$$
\frac { \partial \theta } { \partial t } = \frac { \partial } { \partial z } ( k ( \frac { \partial h } { \partial z } + 1 ) ) - S ,
$$

where $\hat { o }$ is a symbol of partial derivative; $h$ is the water pressure head (cm); $\theta$ is the volumetric water content $( \mathrm { c m } ^ { 3 } / \mathrm { c m } ^ { 3 } )$ · $t$ is the time (d); $S$ is the root water uptake rate $\mathrm { ( c m ^ { 3 } / ( c m ^ { 3 } { \cdot } d ) ) }$ ; and $k$ is the unsaturated hydraulic conductivity $( \mathrm { c m / d } )$ ：

The solution of Equation 4 requires information of the initial distribution of the pressure head within the flow domain:

$$
h ( x , t ) = h _ { i } ( x ) , t = t _ { 0 } ,
$$

where $h _ { i }$ (cm)is the water pressure head as a function of $x$ and $t _ { 0 }$ is the time (d) when the simulation begins.

For the upper boundary condition given by Equation 5, $h$ is considered at the soil surface and air interface (exposed to atmospheric conditions).The atmospheric boundary condition with surface layer permits water to build up on the surface. The height of the surface water increases due to precipitation and reduces because of infiltration and evaporation.The numerical solution of Equation 4 is obtained by limiting the absolute value of the surface flux by the folowing two conditions (Neuman et al., 1974):

$$
\left| - k \frac { \hat { \alpha } h } { \hat { \alpha } x } - k \right| \le E , ~ x = L ,
$$

$$
h _ { \mathrm { { A } } } \ \leq \ h \ \leq \ h _ { \mathrm { { S } } } , \ x = \ L ,
$$

where $E$ is the maximum potential rate of infiltration or evaporation under the current atmospheric conditions $( \mathrm { c m / d } )$ ；and $h _ { \mathrm { { A } } }$ and $h _ { \mathrm { { S } } }$ are,respectively, the minimum and maximum pressure heads at the soil surface allowed under the prevailing soil conditions (cm).

The lower boundary condition considered in this study is a seepage face at the bottom of the soil profile through which water can leave the saturated part of the flow domain. This type of boundary condition is often applied to laboratory soil columns when the local pressure head at the bottom of the soil profile $( x { = } 0 )$ is negative.

In simulation of solute transport, the upper and lower boundary conditions were concentration flux boundary condition (determining liquid phase concentration of infiltration water） and concentration boundary condition (determining liquid phase concentration at the boundary), respectively.

Equation 8 prescribes the concentration at a boundary and Equation 9 used to prescribe the concentration flux at the lower boundary:

$$
c = ( x , t ) = c _ { 0 } ( x , t ) , \ : \ : \ : x = L ,
$$

$$
- \theta D \frac { \partial c } { \partial x } + q c = q _ { 0 } c _ { 0 } , ~ x = 0 ,
$$

Where $q _ { 0 }$ is the upward fluid flux $\mathrm { ( m g / c m ^ { 3 } ) }$ ; and $c _ { 0 }$ is the concentration of the incoming fluid $( \mathrm { m g } / \mathrm { c m } ^ { 3 } )$ ：

# 2.2.2 SALTMED model

The SALTMED model can be used for simulation of soil, water content, soil salinity and crop yield in a variety of irrigation systems, soil types, crops and trees, water application strategies and different water qualities.

In this model,the water flow in soils can be mathematically described by the Richard's equation (Eq.4). In this equation, the initial and boundary conditions are similar to that described in Section 2.2.1. The movement of solute in the soil system, its rate and direction depends greatly on the path of water movement, but it is also determined by diffusion and hydrodynamic dispersion.By the combination of the diffusion,we can obtain the dispersion and the convection of the overall flux of solute according to Hillel (1977):

$$
J = - ( D _ { \mathrm { { h } } } ^ { } + D _ { \mathrm { { s } } } ^ { } ) ( \frac { \widehat { \cal { O } } c } { \widehat { \cal { O } } x } ) + \overline { { { \nu } } } \theta c ,
$$

where $c$ is the concentration of solute (mmol/L) in the flowing water; $\mathbf { \Pi } _ { \nu } ^ { - }$ is the average velocity of the flow $\left( \mathrm { L } / \mathrm { t } \right)$ · $D _ { \mathrm { h } }$ is the hydrodynamic dispersion in soil $( \mathrm { L } ^ { 2 } / \mathrm { t } )$ ; and $D _ { \mathrm { s } }$ is the solute diffusion in soil $( \mathrm { L } ^ { 2 } / \mathrm { t } )$ , which decreases due to the fact that the liquid phase occupies only a fraction of soil volume and also due to the tortuous nature of the path.

# 2.3 Modelevaluation

Some statistical parameters including normalized root mean square error (NRMSE), index of agreement $( d )$ and error percentage $( E )$ were used for evaluation of simulation accuracy (Loague and Green,1991).NRMSE provides the total difference between the measured and simulated data proportioned against means of measured data. The lower limit for NRMSE is O,which occurs when there is no difference between such paired data. Obviously,a smaller value of NRMSE indicates a higher accurate simulation. The value of $d$ was calculated for assessing the accuracy of simulated data. The maximum value for $d$ is 1，which occurs when simulated values are completely identical to the measured values (Willmott et al., 1985). $E$ is defined as a percentage of the difference between the simulated and measured values.A lower value for $E$ means that the simulated result is closer to the measured value.

$$
\begin{array} { r l } & { \quad \mathrm { N R M S E } = \left[ \sum _ { i = 1 } ^ { n } \left( P _ { i } - { O } _ { i } \right) ^ { 2 } \displaystyle { \int _ { n } ^ { V _ { i } } } \times 1 0 \% \right] ^ { \gamma _ { i } } \times 1 0 0 \displaystyle { \int _ { \bar { \sigma } } } , } \\ & { d = 1 - \sum _ { i = 1 } ^ { n } \left( P _ { i } - { O } _ { i } \right) ^ { 2 } \displaystyle { \int _ { \sum _ { i = 1 } ^ { n } \left( \left. P _ { i } - \bar { O } \right. - \left. O _ { i } - \bar { O } \right. \right) ^ { 2 } } } , } \\ & { \quad \quad E = \left( P _ { i } - { O } _ { i } \right) \displaystyle { \int _ { Q _ { i } } } \times 1 0 0 \% , } \end{array}
$$

where $P _ { i }$ is the predicted value; $O _ { i }$ is the observed value; $\bar { O }$ is the mean of observed value; and $n$ is the number of observation.

# 3Results and discussion

# 3.1Irrigation water depth and soil salinity

The irrigation water depths and the results of statistical analysis are shown in Table 2.Differences between the irrgation water depths in controlled groundwater treatments under the salinities of 4 and $8 ~ \mathrm { d S / m }$ were significant $( P { < } 0 . 0 1 )$ . The irrigation water depths under CD1O0, CD8O and CD60 treatments with the $8 ~ \mathrm { d S / m }$ salinity level were respectively, $1 3 . 0 \%$ ， $1 0 . 9 \%$ and $9 . 6 \%$ ,less than those obtained with the $4 \ \mathrm { d } \mathrm { S } / \mathrm { m }$ salinity level. Decreasing in the water consumption value by increasing the level of water salinity was reported in the study of Jiang et al. (2O12). In their research，by increasing the irrigation water salinity from O.67 to 6.1O dS/m，actual evapotranspiration $\mathrm { ( E T _ { a } ) }$ was reduced from 580 to $5 6 0 \mathrm { m m } ( 3 . 4 \% )$ ：

The reductions of irrigation water depth under CD8O and CD6O treatments with the $4 ~ \mathrm { d S / m }$ salinity level were $1 8 . 3 \%$ (from 710 to $5 8 0 ~ \mathrm { m m } )$ and $3 6 . 6 \%$ (from 710 to $4 5 0 ~ \mathrm { m m } ,$ ,respectively, compared with those obtained under CD1OO treatment. And it was $2 2 . 4 \%$ under CD6O treatment compared with that obtained under CD8O treatment. Also with the $8 \ \mathrm { d S / m }$ salinity level,the reductions of irrigation water depth under CD8O and CD6O treatments were $1 6 . 4 \%$ 0 $\mathrm { f r o m } 6 1 8 \$ to $5 1 7 \ \mathrm { m m } )$ and $3 4 . 1 \%$ (from 618 to $4 0 7 ~ \mathrm { { m m } }$ ，respectively,compared with that obtained under CD100 treatment. And it was $2 1 . 3 \%$ under CD6O treatment compared with that obtained under CD8O treatment. All of these differences were significant $( P { < } 0 . 0 1 )$ . Therefore,with the salinity levels of 4 and $8 ~ \mathrm { d S / m }$ , the lowest and the highest values of irrigation water were obtained under CD60 and CD100 treatments, respectively (Table 2). The fraction of water requirement could be provided by capillary rise and it was depended on the groundwater depth. Therefore, the capillary rise values were higher under CD6O than under CD1OO treatment.

The mean irrigation water depth (over salinity levels） under different water table depths is shown in Table 2.According to the result, the mean reductions in irigation water depth under CD80 and CD6O treatments were $1 7 . 4 \%$ (from 664.0 to $5 4 8 . 5 \ \mathrm { m m }$ ）and $3 5 . 5 \%$ (from 664.0 to $4 2 8 . 5 \ \mathrm { m m }$ ), respectively, compared with that obtained under CD1OO treatment, and the reduction in irrigation water depth was $2 1 . 9 \%$ under CD6O treatment compared with that obtained under CD80 treatment, therefore,the water table depth had a significant effect on the reduction in mean irrigation water depth $( P { < } 0 . 0 1 )$ ：

Table 2Statistical analysis of irrigation water depth, $I _ { \mathrm { { g } } }$ and saturated paste electrical conductivity (ECe)   

<html><body><table><tr><td rowspan="3">Irrigation water salinity (dS/m)</td><td colspan="8">Controlled groundwater depth</td></tr><tr><td colspan="2">CD100</td><td colspan="2">CD80</td><td colspan="2">CD60</td><td colspan="2">Mean</td></tr><tr><td>Ig(mm)</td><td>ECe (dS/m)</td><td>Ig (mm)</td><td>ECe (dS/m)</td><td>Ig(mm)</td><td>ECe (dS/m)</td><td>Ig (mm)</td><td>ECe (dS/m)</td></tr><tr><td>4 (EC4)</td><td>710a</td><td>4.831</td><td>580c</td><td>9.87i</td><td>450e</td><td>8.18j</td><td>580A</td><td>7.63B</td></tr><tr><td>8 (EC8)</td><td>618b</td><td>7.50k</td><td>517d</td><td>16.638</td><td>407f</td><td>14.65h</td><td>514B</td><td>12.93A</td></tr><tr><td>Mean</td><td>664A</td><td>6.17C</td><td>549B</td><td>13.25A</td><td>429C</td><td>11.42B</td><td></td><td></td></tr></table></body></html>

Note: CD100-CD60 means the 100-60 cm groundwater depths,respectively. $I _ { \mathrm { g } } ,$ ，gross depth of irrigation water.Means followed by the same lowercase and uppercase letters in each column or row are not significantly different at $P { < } 0 . 0 1$ level (Duncan multiple range test).

The mean $\mathrm { E C _ { \mathrm { e } } }$ at the end of growing season and the statistical analysis of the mean ECe for all water table depths and irrigation water salinities are shown in Table 2. Under CD8O and CD60 treatments, the $\mathrm { E C _ { \mathrm { e } } }$ at the soil surface increased due to increasing the root water uptake at surface layer.Under CD1OO treatment, by increasing the unsaturated soil depth, the $\mathrm { E C _ { \mathrm { e } } }$ increased at the soil surface due to decreasing capillary rise values and then decreased near the water table due to saturation conditions. The mean $\mathrm { E C _ { \mathrm { e } } }$ under CD100, CD80 and CD60 treatments with the salinity levels of 4 and $8 \ \mathrm { \ d } \mathrm { S } / \mathrm { m }$ showed significant differences $( P { < } 0 . 0 1$ ；Table 2). In controlled groundwater depth, i.e., CD100, CD8O and CD60, the increases in $\mathrm { E C _ { \mathrm { e } } }$ with the salinity level of 8 $\mathrm { d } \mathrm { S } / \mathrm { m }$ were respectively, $3 5 . 6 \%$ ， $6 8 . 5 \%$ and $7 9 . 1 \%$ compared with those obtained with the salinity level of $4 \ : \mathrm { d S / m }$ (Table 2).

The effect of water table depth on $\mathrm { E C _ { \mathrm { e } } }$ was significant $( P { < } 0 . 0 1 )$ . In other words,in all levels of irrigation water salinity, the values of $\mathrm { E C _ { \mathrm { e } } }$ under CD8O and CD6O treatments were higher than that obtained under CD1OO treatment. The irrigation water depth under CD1OO treatment was higher than those obtained under CD8O and CD6O treatments (Table 2). Therefore,the higher leaching fraction was occurred under CD1OO treatment compared with those under CD8O and CD6O treatments. The effect of salinity on the mean irrigation water depth was significant $( P { < } 0 . 0 1 )$ . The mean irrigation water depth with the salinity level of $8 ~ \mathrm { d S / m }$ was $1 1 . 3 7 \%$ less than that with the salinity level of $4 ~ \mathrm { d } \mathrm { S } / \mathrm { m }$ . In general,at each level of salinity, the irrigation water depth decreased by decreasing groundwater depth,and at each level of groundwater depth, the irrigation water depth decreased by increasing water salinity level. Decreasing irigation water depth by increasing in water salinity level occurred as a result of the less crop transpiration due to less water uptake in salinity conditions,the less soil evaporation and therefore,the higher soil water content during the growing season. Also, decreases in irrigation water depth by decreasing the groundwater depth could be due to the higher capillary rise and GC to crop water use (Table 3).

Table 3Groundwater contribution (GC) to sub-irrigation in different treatments   

<html><body><table><tr><td rowspan="2">Irrigation water salinity (dS/m)</td><td colspan="2">CD100</td><td colspan="2">CD80</td><td colspan="2">CD60</td></tr><tr><td>GC (mm)</td><td>GC (%)</td><td>GC (mm)</td><td>GC (%)</td><td>GC (mm)</td><td>GC (%)</td></tr><tr><td>4 (EC4)</td><td>0a</td><td>0.0</td><td>130c</td><td>18.3</td><td>260e</td><td>36.3</td></tr><tr><td>8 (EC8)</td><td>92b</td><td>13.0</td><td>193d</td><td>27.2</td><td>303f</td><td>42.7</td></tr></table></body></html>

Note:CD10-CD6O means the10O-6Ocmgroundwaterdepths,respectively.Means followedbythesame lowercase leters ineach column are not significantly different at $P { < } 0 . 0 1$ level (Duncan multiple range test).

# 3.2 Calibrations of the SALTMED and HYDRUS-1D models

The SALTMED and HYDRUS-1D models were calibrated using EC4-CD10O treatment. According to the soil physical properties (Table 1),we divided soil profile into three layers and entered the properties of each soil layer including soil texture, initial soil water content, saturated hydraulic conductivity and required parameters of van Genuchten equation (Table 4） in the models. The initial value of these parameters was determined by the RETC software (van Genuchten et al.，1992)，and then they were optimized during the calibration process. The calibrated parameters of the SALTMED and HYDRUS-1D models are shown in Table 5.

Table 4Parameters of the van Genuchten (198O) equation   

<html><body><table><tr><td>Soil layer thickness (cm)</td><td>n</td><td>α (1/cm)</td><td>Lambie distribution</td><td>Bubbling pressure*(cm)</td><td>Ksat (cm/d)</td><td>0sat (cm³/cm³)</td><td>0res (cm³/cm³)</td></tr><tr><td>0-30</td><td>1.478</td><td>0.011</td><td>index* 0.478</td><td>90.9</td><td>188.6</td><td>0.462</td><td>0.082</td></tr><tr><td>30-50</td><td>1.413</td><td>0.012</td><td>0.413</td><td>83.3</td><td>121.6</td><td>0.465</td><td>0.090</td></tr><tr><td>50-100</td><td>1.399</td><td>0.012</td><td>0.399</td><td>83.3</td><td>85.8</td><td>0.450</td><td>0.090</td></tr></table></body></html>

Note:nandaareshapeparameters,respectively;Ksatisthesaturatedhydraulicconductivity;Osatandresarethesaturatedand residual soil water contents,respectively.\*means that these parameters are required for the SALTMED model.

Table 5 Calibrated values of parameters in the HYDRUS-1D and SALTMED models   

<html><body><table><tr><td colspan="5">HYDRUS-1D</td></tr><tr><td>Soil layer thickness (cm)</td><td>Disp (cm)</td><td>Diff-W (cm²/d)</td><td>Diff-G (cm²/d)</td><td>Sink watera (1/d)</td></tr><tr><td>0-30</td><td>20</td><td>2</td><td>0</td><td>0.096</td></tr><tr><td>30-50</td><td>20</td><td>2</td><td>0</td><td>0.076</td></tr><tr><td>50-100</td><td>20</td><td>2</td><td>0</td><td>0.067</td></tr><tr><td colspan="3">SALTMED</td><td colspan="2"></td></tr><tr><td>Crop factor</td><td>Calibrated value</td><td colspan="2">Crop growth factor</td><td>Calibrated value</td></tr><tr><td>Kc Initial</td><td>0.38</td><td colspan="2">Photosynthesis efficiency (g/MJ)</td><td>1.60</td></tr><tr><td>Kc Mid</td><td>1.25</td><td colspan="2">Extinction coefficient</td><td>0.45</td></tr><tr><td>Kc End</td><td>0.25</td><td colspan="2">PAR ratio</td><td>0.50</td></tr><tr><td>Kcb Initial</td><td>0.20</td><td colspan="2">Tmax (C)</td><td>40.00</td></tr><tr><td>Kcb Mid</td><td>1.00</td><td colspan="2">TopT2b (C)</td><td>28.00</td></tr><tr><td>Kcb End</td><td>0.15</td><td colspan="2">TopT1 (C)</td><td>25.00</td></tr><tr><td>π50 (dS/m)</td><td>10.50</td><td colspan="2">Tmin (C)</td><td>4.00</td></tr></table></body></html>

Note:Disp,logialdispsityi-Woluladisiooentinfreeater;DiGolelardiuionetl air;a,first-order rate constant for dissolved phase; $K \mathrm { c }$ ,crop coeficient;Kcb,crop transpiration coefficient; $\pi 5 0$ ,osmotic pressure at which the root water uptake is reduced by $50 \%$ ；PAR,photosynthetically active radiation;Tmax,maximum air temperature;b,upper optimumtemperaturefordevelopment;,oweroptimumtemperaturefordevelopment;Topis theotimumtemperatureforcropgrowth; Tmin, minimum air temperature.

The water uptake reduction model proposed by Feddes et al.(1974) was used in both models for simulation of the root water uptake under salinity conditions.In this method, the maximum root depth, salinity threshold and slope of yield function decreased by increasing salinity and were considered as $1 0 0 \mathrm { c m }$ ， $6 . 5 \ : \mathrm { d S / m }$ and $7 . 8 \% / ( \mathrm { d S / m } )$ , respectively (Allen et al.,1998).

# 3.2.1 Soil water content

Predicted values of the soil water content under EC4-CD1OO treatment using the two models at different days after planting are shown in Figure 1. There was a good agreement between the predicted and measured soil water content in surface layer $\left( 0 { - } 3 0 \ \mathrm { c m } \right)$ at different days after planting.In the second layer $( 3 0 { - } 6 0 ~ \mathrm { c m } )$ ，the predicted values of both models were higher than the measured values,whereas,in the third layer $( 6 0 { - } 9 0 ~ \mathrm { c m } )$ ,the SALTMED and HYDRUS-1D models predicted the soil water content, respectively, higher and lower than the measured values. $E$ ，NRMSE and $d$ of simulated soil water content in the whole soil profile were $4 . 4 \%$ ， $9 . 4 \%$ and 0.88 for the SALTMED model and $0 . 5 \%$ ， $7 . 6 \%$ and O.89 for the HYDRUS-1D models, respectively. Although, the two models have predicted soil water content very well; however, the prediction of the HYDRUS-1D model for soil water content was more accurate than that of the SALTMED model.

Soil water content (%) Soil water content (%) Soil water content (%) Soil water content (%) 25 35 45 20 25 35 45 20 25 35 45 20 253545   
40 40- 40 40   
60 60 60 60   
80 80 80 80 15 253545 15 2535 45 15 253545 152535 45 (e) 20f 2f8 20 0 (h)   
40 40 40 40   
60 60 60 60-   
80 80 80 80 ·Observed SALTMED HYDRUS-1D

# 3.2.2 $\mathrm { E C _ { \mathrm { e } } }$

Themodels simulated $\mathrm { E C _ { \mathrm { e } } }$ and the associated soil water content at different depths and times.At the same time,the actual $\mathrm { E C _ { \mathrm { e } } }$ in the experiment is measured. Therefore,by using a correction factor based on the ratio of field soil water content to the saturated soil water content, we adjusted the predicted $\mathrm { E C _ { \mathrm { e } } }$ to the measured $\mathrm { E C _ { \mathrm { e } } }$ . Mean values of $E$ were $1 . 0 \%$ and $0 . 8 \%$ ; NRMSE values were $9 . 0 \%$ and $8 . 0 \%$ and $d$ indices were O.88 and O.89 for the SALTMED and HYDRUS-1D models,respectively. Despite the fact that these values show the high accuracy of both models in simulation of $\mathrm { E C _ { \mathrm { e } } }$ ，the prediction of the HYDRUS-1D model was more accurate than that of the SALTMED model.

# 3.3 Validationsof theSALTMEDandHYDRUS-1Dmodels

The SALTMED and HYDRUS-1D models were validated using all treatments except that used for calibration,i.e.，EC4-CD1OO.Values of NRMSE and $d$ indices of the predicted soil water content and soil salinity in the validation step are shown in Table 6.

Table6NRMSE and $d$ indices during validation process of the SALTMED and HYDRUS-1D models   

<html><body><table><tr><td rowspan="2">Parameter</td><td rowspan="2">Statistical parameter</td><td colspan="2">EC4-CD80</td><td colspan="2">EC4-CD60</td><td colspan="2">EC8-CD100</td><td colspan="2">EC8-CD80</td><td colspan="2">EC8-CD60</td></tr><tr><td>H</td><td>S</td><td>H</td><td>S</td><td>H</td><td>S</td><td>H</td><td>S</td><td>H</td><td>S</td></tr><tr><td rowspan="2">Soil water content</td><td>NRMSE (%)</td><td></td><td></td><td>0.07</td><td>0.12</td><td>0.12</td><td>0.10</td><td>0.10</td><td>0.10</td><td></td><td></td></tr><tr><td>d</td><td></td><td></td><td>0.56</td><td>0.82</td><td>0.73</td><td>0.82</td><td>0.65</td><td>0.81</td><td></td><td></td></tr><tr><td rowspan="2">Soil salinity</td><td>NRMSE (%)</td><td>0.06</td><td>0.13</td><td>0.08</td><td>0.10</td><td>0.03</td><td>0.05</td><td>0.06</td><td>0.12</td><td>0.08</td><td>0.15</td></tr><tr><td>d</td><td>0.99</td><td>0.98</td><td>0.99</td><td>0.99</td><td>0.98</td><td>0.91</td><td>0.99</td><td>0.98</td><td>0.99</td><td>0.98</td></tr></table></body></html>

Note:NRMSE,normalizedrootmeansquare eror;d,degreeofagreement;H,HYDRUS-D;S,SALTMED.-meansnoalue

# 3.3.1 Soil water content

The observed and simulated values of soil water content in soil profile at different days after planting under EC8-CD100 and EC8-CD80 treatments are shown in Figures 2 and 3.Because the soil water content was measured only at the depth of $3 0 \ \mathrm { c m }$ in EC4-CD60 treatment, plotting the soil water content profile is not possble for this treatment. Comparison of the predicted soil water content under the EC8-CD100 and EC4-CD100 treatments showed that by increasing the level of water salinity to higher than the wheat threshold salinity level $( 6 . 5 ~ \mathrm { d S / m } )$ ，root water uptake decreased and, therefore,soil profile was wetter. Therefore,the mean predicted soil water content using the both models was higher under EC8-CD1OO treatment than under EC4-CD1OO treatment.

By raising the obtained water table depth and reaching the saturated zone to the depth of $6 0 \mathrm { c m }$ below the soil surface, soil water content increased in two consecutive irigation intervals. Soil water content was increased in top layers of soil profile under EC4-CD6O treatment due to the lower water table depth and higher capillary rises.The simulated soil water content by the both models of this treatment was less than the observed values;whereas,the errors of simulation by the SALTMED and HYDRUS-1D models were $- 1 0 . 7 \%$ and $- 0 . 4 \%$ ,respectively. The precision of the HYDRUS-1D model was higher than the SALTMED model, because in this model the effects of waterlogging stress is well considered and when the soil water content is high and root water uptake decreases or stops.The simulated soil water content under EC8-CD8O treatment in surface layer $( 0 { - } 3 0 \mathrm { c m } )$ was more accurate than that obtained in the deeper layers. It is notable that in this treatment,due to the higher capillary rise,soil salinity in the deeper layers was the highest. This result is in agreement with Kaya et al. (2O15),who predicted the soil water contents in 0-30, 30-60 and $6 0 { - } 9 0 ~ \mathrm { c m }$ soil depths using the SALTMED model. According to their results, simulated water content was more accurate in surface layer than in the third soil layer ( $R ^ { 2 }$ values were O.86 and O.8O,respectively). They described that the lower $R ^ { 2 }$ in the deeper layer might be attributed to the neglecting soil drainage properties because of missing data. In another similar research of the HYDRUS-1D model, it was obtained that simulation of soil water content in the $\scriptstyle 0 - 4 0 \ \mathrm { c m }$ soil depth was more accurate than that obtained in the $4 0 { \mathrm { - } } 1 0 0 \ { \mathrm { c m } }$ soil depth (Zeng et al., 2014).

Soil water content $( \% )$ （204号 Soil water content $( \% )$ （204号 Soil water content $( \% )$ （204号 Soil water content $( \% )$ 15 25 35 45 15 25 3545 15 253545 15 253545 u (a) 0 (b) 0 (c) 0 (d) + 20- 1 20 20 40- 40 40 60- 60 60 80 80 80 15 2535 45 15 253545 15 25 35 45 15 2535 45 0 0+ 0 20(e） 20 (g) 20 (h) 中 20 40 40 40- 40 60 60 60 60 80 80 80 80 ·Observed SALTMED HYDRUS-1D

Soil water content $( \% )$ （20 Soil water content $( \% )$ （204 Soil water content $( \% )$ （204号 Soil water content $( \% )$ （204号 15 25 35 45 15 25 35 45 15 25 35 45 15 25 35 45   
0 ⊥ 0+ 1 0+ 0 20 (b) 20(0) 20(d)   
40- 40 40- 40   
60- 60 60 60   
80- 80 80 80 15 2535 45 15 2535 45 15 2535 45 15 25 35 45   
0 0+ 0 0 20 (f) 20(g) 20(h)   
40- 40 40 40   
60- 60 60 60   
80- 80 80- 80 : Observed SALTMED HYDRUS-1D

The predicted soil water content in the depth of $3 0 \ \mathrm { c m }$ by the HYDRUS-1D model in all treatments was closer to the observed values.In the first layer $\left( 0 { - } 3 0 \ \mathrm { c m } \right)$ ,the NRMSE values of EC4-CD100,EC4-CD60,EC8-CD100 and EC8-CD80 treatments in the HYDRUS-1D model were $5 . 6 \%$ ， $3 . 1 \%$ ， $9 . 7 \%$ and $7 . 3 \%$ , respectively with the average value of $7 . 3 \%$ ,and the errors of simulation were $- 0 . 7 \%$ ， $- 0 . 4 \%$ ， $- 5 . 0 \%$ and $0 . 2 \%$ , respectively, and $- 1 . 5 \%$ as an average. In the SALTMED model, the NRMSE values of EC4-CD100, EC4-CD60,EC8-CD100 and EC8-CD80 treatments were $0 . 0 \%$ ， $1 2 . 7 \%$ ， $1 1 . 7 \%$ and $8 . 9 \%$ , respectively with the average value of $9 . 9 \%$ ，and the errors of simulation were $- 0 . 2 \%$ ， $- 1 0 . 7 \%$ ， $- 1 . 7 \%$ and $4 . 0 \%$ ，respectively and $- 2 . 1 \%$ as an average. Therefore, the result of the HYDRUS-1D model was closer to the measured values. In the second layer $\left( 3 0 { - } 6 0 ~ \mathrm { c m } \right)$ ，the simulation accuracy of both models under EC4-CD10O and EC8-CD80 treatments was decreased and under EC8-CDiOO treatment it was increased. In the second layer, the NRMSE values of EC4-CD100,EC8-CD100 and EC8-CD80 treatments in the HYDRUS-1D model were $8 . 4 \%$ ， $8 . 7 \%$ and $1 2 . 1 \%$ , respectively with the average value of $9 . 7 \%$ and the errors of simulation were $4 . 3 \%$ ， $- 0 . 6 \%$ and $- 5 . 9 \%$ , respectively with the average value of $- 0 . 5 \%$ ：In the SALTMED model， the NRMSE values of EC4-CD100，EC8-CD100，and EC8-CD80 treatments were $1 2 . 7 \%$ ， $8 . 8 \%$ and $1 0 . 7 \%$ ，respectively with the average value of $1 0 . 7 \%$ and the errors of simulation in these treatments were $1 0 . 2 \%$ ， $6 . 4 \%$ and $8 . 1 \%$ with the average value of $8 . 2 \%$ . Therefore, the result of the HYDRUS-1D model with the average NRMSE of $9 . 7 \%$ and the average error of $- 0 . 5 \%$ is closer to the measured values.

In the third layer $( 6 0 { - } 9 0 \ \mathrm { c m } )$ ,unlike the two otherlayers, the NRMSE in the SALTMED model was less than that obtained in the HYDRUS-1D model. The NRMSE in the third layer of EC4-CD100 and EC8-CD100 treatments were $7 . 9 \%$ and $1 4 . 4 \%$ , respectively with the average of $1 1 . 1 5 \%$ ,and the errors of simulation were $- 5 . 1 \%$ and $- 1 1 . 4 \%$ ,respectively with the average value of $- 8 . 3 \%$ . In the SALTMED model, the NRMSE of EC4-CD100 and EC8-CD100 treatments were $7 . 3 \%$ and $1 1 . 5 \%$ , respectively, and the errors of simulation were $3 . 3 \%$ and $- 5 . 0 \%$ ， respectively. Therefore,in the third layer, the result of SALTMED model with the average NRMSE of $9 . 4 \%$ and the average error of $- 0 . 9 \%$ was closer to the measured values.

The results of calibrated and validated soil water contents are shown in Figure 4. In general, the NRMSE values of EC4-CD100, EC4-CD60,EC8-CD100 and EC8-CD80 treatments in all soil profile were $4 . 5 \%$ ， $7 . 9 \%$ ， $1 1 . 9 \%$ and $8 . 1 \%$ ，respectively, in the HYDRUS-1D model, they were $9 . 5 \%$ ， $7 . 9 \%$ ， $9 . 7 \%$ and $1 1 . 4 \%$ , respectively,in the SALTMED model. Therefore,forall predicted soil water content in dierent treatments and layers,the HYDRUS-1D model provided a better estimation of soil water content (Fig. 4).

# 3.3.2 $\mathrm { E C _ { \mathrm { e } } }$

Values of $\mathrm { E C _ { \mathrm { e } } }$ in soil profile using both models at the end of growing season are shown in Figure 5.The HYDRUS-1D model provided more accurate simulation of $\mathrm { E C _ { \mathrm { e } } }$ at the end of growing season. Of course,the prediction of the SALTMED model in the third layer was very good; however, the order of goodness was decreased to the second and the first layers,due to unsuitable prediction of the capillary rise by this model. In the first layer, the means of $E$ of the predicted soil salinity using the SALTMED and HYDRUS-1D models in all treatments were $- 9 . 9 \%$ and $- 1 . 4 \%$ ， respectively. The values of this index in the second layer were $7 . 6 \%$ and $- 3 . 7 \%$ ，and in the third layer they were $1 . 0 \%$ and $7 . 5 \%$ , respectively. When all the predicted values under all treatments were plotted and compared against the 1:1 line,it revealed that the NRMSE and $d$ for the HYDRUS-1D model were $6 . 7 \%$ and 0.997,respectively,and for the SALTMED model, they were $1 2 . 9 \%$ and O.988，respectively. Therefore， the HYDRUS-1D model provided more accurate simulation for $\mathrm { E C _ { \mathrm { e } } }$ in soil profile (Fig. 5).

According to the result of Zeng et al. (2O14), the simulation of $\mathrm { E C _ { \mathrm { e } } }$ in surface layer was more accurate than that of the deeper layer and in general, the HYDRUS-1D model showed a good agreement between the simulated and measured $\mathrm { E C _ { \mathrm { e } } }$ . Najib et al. (2017) simulated the soil salinity profile from different irrigation methods including furrow,basin,sprinkler and drip irrigations and found that the SALTMED model was able to successfully simulate salinity in all irrigation methods. Golabi et al. (2O12) found that the predicted soil salinity by the SALTMED model was lower than the measured value because of some uncontrolled factors that existed in the field, but are not considered in the model.

45 45 (a) (b) (c)   
40 40 40 NRMSE,=11.7%   
35 NRMSE,=7.6% 35 NRMSE=12.3% 35 d=0.727 .： d=0.892 d=0.819   
30 30 30   
25 25 25   
20 NRMSE=9.4% 20 NRMSE,=7.1% 20 NRMSE=10.8% d=0.885 d=0.564 d=0.817   
15 15 15 15 20 25 30354045 15202530354045 15202530354045 Predicted soil water content (%) Predicted soil water content $( \% )$ Predicted soil water content $( \% )$ 45 (d) (e)   
40 40 NRMSE=10.4% NRMSE,=9.8%   
35 d=0.653 35 d=0.777 ECE 16 dH=0.997 NRMSE,=6.7%   
3025 20 NRMSE=10.4% 3025 20 NRMSE=10.5% anse NRMSE=12.9% d=0.809 d=0.836 ds=0.988   
15 15 0 1520 2530354045 15202530354045 0 4812162024 Predicted soil water content $( \% )$ （204号 Predicted soil water content $( \% )$ （204号 Predicted EC (dS/m) 1:1 line·SALTMED ·HYDRUS-1D SALTMED trend line HYDRUS-1D trend line

EC(dS/m) EC(dS/m) EC(dS/m) 048121620 24 04812 16 2024 4812162024 0 0+ 0 (a) (b) (c) 8 20- 20 40- 40 60- 60 80- 80 100 100 100 8 12 162024 2004812 16 2024 2094121620 24 40 40- 40 60 60- 60 80 80- 80 100 100 100 ·Observed -HYDRUS SALTMED

# 3.4Simulations of wheat yield and dry matter using the SALTMED model

The predicted values of wheat yield and dry mater are shown in Table 7 and Figure 6,and the NRMSE and $d$ indices were determined.In the water table depth of $8 0 ~ \mathrm { c m }$ ，the groundwater contributed to the plant water uptake through the capillary rise,but when the water table depth reached up to $6 0 ~ \mathrm { c m }$ ，the root zone is saturated and the plant is exposed to waterlogging stress. Therefore,the wheat yield and dry matter in the water table depth of $8 0 \ \mathrm { c m }$ were higher than those obtained in the $6 0 \ \mathrm { c m }$ depth. This trend was also observed in the model predictions regarding to the NRMSE and $d$ （ $2 . 9 \%$ and O.985 for dry matter, and $9 . 8 \%$ and 0.908 for wheat yield,respectively). It is concluded that the SALTMED model provides an accurate simulation for wheat yield and dry matter. The model accuracy in simulation of dry mater was higher than that obtained of crop yield,because the model predicts the dry mater firstly and then determines the crop yield by multiplying dry matter by the harvest index (O.4) that may not be very accurate. This result are similar to the study that was carried out by Aziz Hirich et al. (2O12),Akbari Fazli (2013）and other researches that obtained a very good agreement between the measured and predicted crop yield using the SATMED model.

Table 7Measured and predicted wheat yield and dry matter by the SALTMED model   

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">Treatment</td><td colspan="2">Dry matter (Mg/hm²)</td><td rowspan="2">Error percentage (%)</td><td colspan="2">Wheat yield (Mg/hm²)</td><td rowspan="2">Error percentage (%)</td></tr><tr><td>Predicted</td><td>Measured</td><td>Predicted</td><td>Measured</td></tr><tr><td rowspan="3">EC4</td><td>CD100</td><td>11.52</td><td>11.35</td><td>1.5</td><td>4.60</td><td>4.88</td><td>-5.7</td></tr><tr><td>CD80</td><td>12.19</td><td>11.72</td><td>4.0</td><td>4.87</td><td>5.80</td><td>-16.0</td></tr><tr><td>CD60</td><td>10.56</td><td>10.46</td><td>1.0</td><td>4.22</td><td>4.06</td><td>3.9</td></tr><tr><td rowspan="3">EC8</td><td>CD100</td><td>9.40</td><td>9.43</td><td>-0.3</td><td>3.78</td><td>3.62</td><td>4.4</td></tr><tr><td>CD80</td><td>9.68</td><td>9.76</td><td>-0.8</td><td>4.12</td><td>4.12</td><td>-6.1</td></tr><tr><td>CD60</td><td>8.11</td><td>8.63</td><td>-6.0</td><td>3.17</td><td>3.17</td><td>2.2</td></tr></table></body></html>

![](images/05b7cbe04af94152595d78ca8bf897f2fd3d48676d1434599148da2fcc764b58.jpg)  
Fig.6Relationships between the measured and predicted (a) wheat yield and (b)dry matter

# 4 Conclusions

The mean soil water content during the growing season showed that in the most cases, soil water content predicted by the HYDRUS-1D model was higher than the measured values and the values predicted by the SALTMED model were higher in the soil surface layer and lower in the deep soil layers than the measured values.The predicted soil water content in different salinity levels and controlled groundwater treatments by the HYDRUS-1D model was generally more accurate than that of the SALTMED model. The accuracy of the predicted soil water content by both two models with the salinity level of $8 ~ \mathrm { d S / m }$ decreased,but the SALTMED model provided more accurate simulation with higher levels of salinity(Table 7).Therefore,it is concluded that the HYDRUS-1D and SALTMED models are appropriate in lower and higher levels of salinity, respectively. In general, simulation of soil salinity by the HYDRUS-1D is more accurate than that of the SALTMED model.

The wheat yield was only predicted by the SALTMED model because the HYDRUS-1D model is not designed to simulate crop yield.Wheat yield and dry matter decreased by increasing the salinity level.By decreasing the water table depth to $8 0 \ \mathrm { c m }$ ，the wheat yield and dry matter increased;however,by reaching the water table depth to $6 0 ~ \mathrm { c m }$ ，theydecreased.When the water table was in the depth of $8 0 \mathrm { c m }$ ,the groundwater contributed to the plant water uptake through the capillary rise; whereas, in the water table depth of $6 0 \mathrm { c m }$ ,a great part of the root was placed in the saturated zone and; therefore, the plant root exposed to waterlogging stress that resulted in wheat yield losses.This trend was also observed in the model predictions. However, the model accuracy in simulation of wheat dry matter was higher than that of wheat yield. In general, the SALTMED model provides an accurate simulation for dry matter and yield of wheat.

# Acknowledgements

Thisresearch was supported in part by the Project of the Shiraz University Research Council,Iran (94GCU5M1923).The third author acknowledged the financial support of Iran National Science Foundation (INSF).

# References

AllenR G,PereiraLS,Raes D,etal.1998.Crop evapotranspiration-guidelines forcomputingcrop waterrequirements.FAO Irrigation and Drainage paper 56.FAO,Rome,300(9): D05109.   
Aseng S,FilleryIRP,DuninFX,etal.2Oola.Potentialdeepdrainage under wheatcrops ina Mediteranean climate.I. Temporal and spatial variability. Crop and Pasture Science,52(1): 45-56.   
Aseng S,DuninFX,FillryIRP,etal.2Oolb.Potential deepdrainageunder wheatcrops inaMediterraneancliate.. Management opportunities to control drainage.Crop and Pasture Science,52(1): 57-66.   
Ayars JE,ChristenEW,HornbuckleJW.2Oo6.Controlleddrainageforimproved water management inaridregions irrigate agriculture.Agricultural Water Management, 86(1-2):128-139.   
Borg H,Grimes DW.1986.Depth development of rots with time:An empirical description.Transactionsof the American Society of Agricultural Engineers,29(1):194-197.   
Brouwer C,PrinsK,HeibloemM.1989.Irgation WaterManagement: IrigationScheduling.Training Manual,4.Rome:Food and Agriculture Organization of the United Nations.[2019-02-05]. htp://www.fao.org/3/T7202E/T7202E00.htm.   
El-Shafie AFOsama MA,Hussein MM,etal.2O17.Predictingsoilmoisturedistribution,drymatter,waterprouctiityand potato yield under a modified gated pipe irigationsystem:SALTMED modelapplication using field experimental data. Agricultural Water Management,184: 221-233.   
Fazli RA,Gholami A,Andarzian B,etal.2O13.Investigating the efectof applying drainaged-wateron wheat yield using SALTMED model. Journal of Novel Applied Science,2(Suppl.3):1003-1011.   
FeddesRA,BreslerE,Neuman SP.1974.Field testof a modified numerical modelfor water uptake byroot system.Water Resource Research,10(5): 1199-1206.   
GolabiM,Naseri AA,Kashkuli HA.2O09.Evaluationof SALTMED modelperformance in irigationand drainageof sugarcane farms in Khuzestan province of Iran.Journal ofFood,Agriculture and Environment,7(2):874-880.   
NajibBH,ManiaIJ,Zaoui A,et al2Oo7.Irigation water management using fresh and saline water:modellingand experimental study SALTMED model calibration and validation using fresh water.In: Proceeding of ICID (International Commission on Irrigation and Drainage) $2 2 ^ { \mathrm { n d } }$ European Regional Conference,2-7 September 2Oo7,Pavia, Italy.   
Hirich A,Choukr-Alla R,RagabR,etal.2012.The SALTMED model calibrationand validation using field data from Morocco.Journal of Materials and Environmental Science,3(2):342-359.   
Jha R K,Sahoo B,PandaR K.2O17.Modeling the water and nitrogen transports in asoil-paddy-atmosphere systemusing HYDRUS-1D and lysimeter experiment.Paddy and Water Environment,15(4): 831-846.   
Jiang J,HuoZ,Feng S,etal.2012.Effectofirigationamountand watersalinityon waterconsumptionand waterproductivity of spring wheat in Northwest China.Field Crops Research,137: 78-88.   
Kaya CI,YazarA,Sezen SM.2O15.SALTMED model performanceonsimulationof soil moisture andcrop yield forquinoa irigated using different iigationsystems,irrigationstrategiesand waterqualities inTurkey.AgricultureandAgricultural Science Procedia,4:108-118.   
KhalilB M,Abdel-Gawad ST,MilleteJA.2004.Impactof controlleddrainageonrice production,irrigation water requirement and soil salinity in Egypt. In: Cooke R.Drainage VII Proceedings of the $8 ^ { \mathrm { t h } }$ International Symposium,21-24 March 2004,Sacramento,CA,USA.Michigan: American Society of Agricultural and Biological Engineers,443-452.   
Liu XW,FeikeT,CHENSY,etal.2016.Efctsofsalie irigationonsoilsaltaccumulationandgrainyieldinthe winter wheat-summer maize double cropping system in the low plain of North China.Journal of Integrative Agriculture,15(12): 2886-2898.   
Loague K,Green RE.1991.Statistical and graphical methods for evaluating solute transport model: Overview andappication. Journal of Contaminant Hydrology,7(1-2): 15-73.   
Luo Y,Sophocleous M.20lo.Seasonal groundwater contribution to crop-wateruse assessed with lysimeterobservations and model simulations. Journal of Hydrology,389(3-4): 325-335.   
Ma WJ,MaoZQ,YuZR,etal.208.Effectsofsaline waterirrigationonsoilsalinityand yieldof winter wheat-maize in North China Plain. Irrigation and Drainage Systems,22(1): 3-18.   
Malash NM,FlowersTJ,RagabR.2O11Plant-waterrelations,growthand productivityof tomatoirigatedbydifferent methods with saline and non-saline water.Irrigation and Drainage,6O(4): 446-453.   
NoshadiM,ForoutaniA,SepaskhahA.2O17.Analysisofclodinafop-propargylherbicidetransportinsoilprofileunderetiver cultivationusingHYDRUS-1DandmodifiedPRZM-3models.Toxicology:OpenAccess，3:doi: 10.4172/2476-2067.1000120.   
Ragab R.2O02a.A holistic generic integrated approach for irrigation,cropand field management: the SALTMED model. Environmental Modelling and Software,17(4): 345-361.   
Ragab R.2Oo2b.Integrated modelling approach for irrigation water management using saline and non-saline water:the SALTMED model. Acta Horticulturae,573:129-138.   
Ranjbar GH,Ghadiri H,RazzaghiF,etal.2O15.Evaluationof the SALTMEDmodelforsorghum undersalineconditions inan arid region.International Journal of Plant Production,9(3):373-392.   
RazzaghiF,GhannadiT.2O16."Assessing SALTMED modelforwheat experiments irigated withbasinand sprinklersystems". International Journal of Plant Production,10(2): 233-250.   
ShahrokhniaMH,SepaskhahAR.2O18.Waterand nitratedynamics insafflowerfieldlysimetersunderdiferentirigation strategies,planting methods and nitrogen fertizationandapplicationof HYDRUS-1D model.Environmental Science and Pollution Research,25: 8563-8580.   
SilvaLL,BaptistaFJ,Meneses JF,etal.2O17.Evaluationof theSALTMEDmodel for tomatocropproduction inuneated greenhouses.Acta Horticulturae,117O:441-446.   
Simünek J,KohneJM,Kodesova R,etal.2o8.Simulatingnon equilibrium movementof water,solutes,andparticlesusing HYDRUS: A review of recent applications. Soil and Water Research, 3(Special Issue 1): 42-51.   
Steppuhn H. 2O16.Enhancing subsurface drainage to control salinity in dry land agriculture. In: $1 0 ^ { \mathrm { { u } } }$ International Drainage Symposium Conference,6-9 September 2O16,Minneapolis,Minnesota.Michigan:American Societyof Agricultural and Biological Engineers.   
van GenuchtenMT.1980.Aclosed-form equationforpredicting thehydraulicconductivityofunsaturatedsoils.SoilScience Society of America Journal, 44(5): 892-898.   
van GenuchtenMT,LeijFJ,undLJ.1992.Indirectmethods forestimatingthehydraulicpropertiesofunsaturatedsoils.In: Proceedingsof the International Workshopon Indirect MethodsforEstimatingtheHydraulic Propertiesof Unsaturated Soils, 11-13 October,1992,Riverside,California,USA.   
Wang XP,YangJS,LiuGM,etal.2Ol5.Impactof irigationvolumeand watersalinityon winterwheat productivityand soil salinity distribution.Agricultural Water Management,149:44-54.   
Willmott C J,Ackleson $s _ { \mathrm { ~ G ~ } }$ Davis R E,et al.1985.Statistics for the evaluation and comparison of models.Journal of Geophysical Research: Oceans,90(5): 8995-9005.   
ZengWZ,XuC,WuJW,et al.2014.Soilsalt leaching underdifferent irigationregimes: HYDRUS-1Dmodellig and analysis. Journal of Arid Land,6(1): 44-58.