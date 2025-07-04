# Model based decision support system for land use changes and socio-economic assessments

YU Yang1\*, CHEN $\mathrm { \ X i ^ { \mathrm { 1 } } }$ ， Philipp HUTTNER², Marie HINNENTHAL³, Andreas BRIEDEN³,SUN Lingxiao1, Markus DISSE²

1 Xinjiang Institute of Ecology and Geography,Chinese Academy of Sciences, Urumqi 830o11,China;   
2 Chair of Hydrology and River Basin Management,Technical University of Munich,Munich 8O33,Germany;   
3Chairof Statistics andRisk Management, Universitaetder Bundeswehr Muenchen,Neubiberg D-85577,Germany

Abstract: Hydrological models are often linked with other models in cognate sciences to understand the interactions among climate， earth， water， ecosystem， and human society. This paper presents the development and implementation of a decision support system (DSS) thatlinks the outputs of hydrological models with real-time decision making on social-economic assessments and land use management. Discharge and glacier geometry changes were simulated with hydrological model, water availability in semiarid environments. Irigation and ecological water were simulated by a new commercial software MIKE HYDRO. Groundwater was simulated by MODFLOW. All the outputs of theses hydrological models were taken as inputs into the DSS in three types of links: regression equations, stationary data inputs, or dynamic data inputs as the models running paralel in the simulation periods. The DSS integrates the hydrological data, geographic data, social and economic statistical data,and establishes the relationships with equations, conditional statements and fuzzy logics. The programming is realized in $C { + } { + }$ . The DSS has four remarkable features: (1) editable land use maps to asist decision-making; (2) conjunctive use of surface and groundwater resources; (3) interactions among water, earth, ecosystem,and humans; and (4) links with hydrological models.The overallgoal of the DSS is to combine the outputs of scientific models, knowledge of experts, and perspectives of stakeholders, into a computer-based system, which alows sustainability impact assessment within regional planning; and to understand ecosystem services and integrate them into land and water management.

Keywords: decision support system; hydrological modeling; ecosystem services; land management; socio-economic ndicator;TarimRiverBasin

# Introduction

The debate over the effectiveness of integrated water resources management (IWRM) in practice has lasted for years (Jefrey and Gearey, 20O6; Biswas, 2008; Quevauviller, 2O10; Giordano and Shah, 2014). As the complexity and scope of IWRM increases, the difficulties of hydrological modeling are shifting from the model itself to the links with other cognate sciences and to understand the interactions among water, earth, ecosystem and humans. This paper presents the development and implementation of a decision support system (DSS) that links the outputs of hydrological models with real-time decision making on social-economic assessments and land use management. The DSS assists the decision-making in a qualitative manner based on the outputs of hydrological models and knowledge of experts in cross-disciplinary fields.

There are currently many DSS models with economic assessments (Wenkel et al., 2O13; West and Turner, 2014; Yue et al.,2014; Pedro-Monzonis et al., 2016), focusing on single topic (e.g., climate change,land use, agriculture, water account), and many socio-economic models (Florke et al., 2013; Arnell and Lloyd-Hughes, 2014; Herrero et al.， 2014; Visconti et al., 2015) without simulation of hydrological processes. Few model is capable of integrating meteorological, geographical, ecological, social and economic factors, which is based on the simulation of hydrological models. Little research has been done to show the interactions of so many crossdisciplinary researches on IWRM to understand ecosystem services (ESS) and integrate them into land and water management. Due to model complexity issues, many DSS models have to consider less issues within a specific research framework (McCown, 2OO2; Basso and Ritchie, 2015). However, the model complexity of DSS is worth the effort (Chenoweth et al., 2O04; Power et al., 2015) to increase model accuracy on the comprehensive analysis in IWRM.

Since the last decade the Chinese government has been promoting the development of western China.The demographic development and socio-economic change has led to a rapid change of land use systems in the Tarim River Basin, where it is the habitat for more than $80 \%$ of Populus euphratica trees in China, and has substantially affected the quantity and quality of arable soil, surface water, and groundwater (Zhao et al.,2009; Zhang et al.,2014; Rumbaur et al., 2015). These changes in soil and water have large impacts on the crop production and natural vegetation (Chen et al., 2015; Zhang et al., 2015), such as the $P$ .euphratica trees.

Since 2011, the German Ministry of Science and Education Bundesministeriums fuer Bildung und Forschung (BMBF) established the Sino-German SuMaRiO (www.sumario.de) project for sustainable management of river oases along the Tarim River. A cross-disciplinary consortium of 11 German and 9 Chinese universities and research institutes joint together for the research on SuMaRiO and the DSS. Project SuMaRiO focus on realizable management strategies, considering social, economic and ecological criteria. This will have positive effects for nearly $1 0 \times 1 0 ^ { 6 }$ inhabitants of different ethnic groups. The DSS is the main outcome of SuMaRiO. The overall goal of the DSS is to integrate all crucial research results of SuMaRiO, including stakeholder perspectives, into a model based decision support system, which allows a sustainability impact assessment within regional planning on land and water management in the Tarim River Basin to understand ESS and interactions with water, earth and humans. The DSS is an indicator based tool that enables stakeholders and decision-makers to evaluate the consequences of their intended actions, which helps to implement sustainable land and water management measures in the upcoming development plans (Disse, 2016).

# 2Materials and methods

# 2.1 Study area

This research is conducted in the Tarim River Basin. With the mainstream of $1 3 2 1 \ \mathrm { k m }$ and located at the northern edge of the Taklimakan Desert, the Tarim River is the longest inland river in China. The Tarim Basin is known worldwide for its natural resources, extreme arid climate and vulnerable ecosystem. In this region, agricultural water consumption and allocation management are crucial to address the conflicts among irrigation water users from upstream to downstream(Yu et al., 2015), which cause severe water scarcity problems on ecosystem (Liu and Chen, 2O06) and sustainable land management (Feng et al., 2OO1; Liu and Meng, 2011).

This research focused on the mainstream of Tarim River, starting from Aral till Taitema Lake. With a mean annual precipitation of around $4 0 ~ \mathrm { \ m m }$ and more than $3 0 0 0 ~ \mathrm { \ m m }$ potential evapotranspiration per year, the region is extremely arid with vulnerable ecosystem. Water in the mainstream of Tarim River is mainly provided by high mountain glacier melting, which feed the Tarim River through its tributaries. Water resources and ecosystem stability are the most obvious and sensitive issues in this hyper-arid region.

The oases along the Tarim River is covered by riparian forest, grassland, reed, shrubs, and farmlands. The main crop of the irrigated fields is cotton, which is also a major income source for the local people. The Tarim River Basin has a global reputation of producing high quality cotton, which provides more than half of the cotton production in China.

# 2.2Research fields

The interdisciplinary research challenges are clustered in five interrelated work blocks, WB 1-WB 5 (Fig. 1), with WB 1 on organization with stakeholders and management issues, WB 2 on regional climate change and discharge of the Tarim River tributaries, WB 3 on sustainable water and land use management, WB 4 on ecosystem services (ESS) and ecosystem functions (ESF),and WB 5 on multi-level socio-economic assessment of ecosystem services and implementation tools. The DSS will identify realizable management strategies, considering social, economic and ecological criteria.

Global asscssmcnt of 1and usc dynamics on grccnhousc gas emissions and ESS WB 2: Regional climate change and ↑ WB5:Multi-level socio-economic discharge ofTarimtributaries assessmentof ecosystem servicesand implementation tools   
WP2.1:Monitoringand modeling SuMaRiO WP5.1:Multi-level economic system assessment   
WP2.2:Regional climate scenarios and ofcryosphere WP5.2:Transdisciplinary asscssmcnt of ESS for urbanareasregardingdust and heat stress medium-term forecast of precipitation   
WP2.3:Climatechange impact WP5.3:Actor-bascd decisionsupport on water discharge forlandandwatermanagement WB 1: Organization WP1.1:Project coordination and equipment management WP1.2: Scenario management WP1.3:Stakeholderdialogueand coordination ofknowlcdgc transfer WP1.4: GIS andDATA management   
WB3:staiasi WB4:Eaesg   
WP 3.1: Wathr pueae $( 0 . 1 \mathrm { k m } ^ { 2 } )$ ter quality WP4   
WP3.2:Hydrologysalinityandbiomass WP4.2:ESS and ccosystcm functions of production on the local scale $( 1 0 \mathrm { k m } ^ { 2 } )$ 0 non-irrigated iand use systems   
WP3.3:Upscalingto theregional scale $( 2 0 0 ~ \mathrm { k m } ^ { 2 } )$ Wp 4.3: ESS and ecosystem functions of urban   
WP3.4:Modelingof thewaterbalance and peri-urban oasis vegetation alongtheTarimRiver(1000km)

Research content of the DSS covers the following aspects in the Tarim River Basin: water resources, climate, biodiversity, demographics, energy consumption and production, poverty and health, economic development, land management, and scenario management. A number of these research fields involve more than one WB,and thus need expert knowledge from interdisciplinary cooperation.

# 2.3Indicators of DSS

Under scenario assumptions, possble actions and their impacts are estimated in a quantitative way with the help of sustainable indicators (Table 1). Climate indicators, socio-economic indicators and management indicators are input indicators,and ESS indicators are output indicators. Input indicators give users opportunities to change the scenario on the baseline or perspective in the planning years,and output indicators demonstrate the simulation results caused by the management alternatives.

User can define the inputs of DSS according to the reference values, possble ranges and certain rules. Simulation years can be chosen from 2012 to 2050. The climate projections were based on three emission scenarios, nine global climate models,and additional two regional climate models. Four types of climate scenarios, CCLM RCP 2.6, CCLM RCP 4.5, CCLM RCP 8.5, and REMO

A1B,are included in the DSS. For socio-economic indicators and management indicators, users can change the reference values on the management alternatives in the planning years.The results of their actions will be demonstrated by the output indicators.

Table 1 Input and output indicators of the decision support system (DSS)   

<html><body><table><tr><td colspan="2">Climate indicators</td><td>Socio-economic indicators</td><td>Management indicators</td></tr><tr><td rowspan="6">Input indicators</td><td>Temperature rising (C)</td><td>Cotton production costs (CNY/hm²)</td><td>Drip irrigation share in total agricultural irrigation area (%)</td></tr><tr><td>Precipitation increase (%)</td><td>Average costs for the production of fruits (CNY/hm²)</td><td>Subsidy for drip irrigation (CNY/hm²)</td></tr><tr><td></td><td>Average costs for the production of other crops (CNY/hm²)</td><td>Household and industry water allocation (%)</td></tr><tr><td></td><td>Cotton price (CNY/t)</td><td>Flooding of natural vegetation (%)</td></tr><tr><td></td><td>Average price of fruits (CNY/t)</td><td></td></tr><tr><td colspan="3">Average price of other crops (CNY/t)</td></tr><tr><td colspan="2">Agriculture</td><td>ESS ESS indicators</td><td colspan="2"></td></tr><tr><td rowspan="15">Output indicators</td><td colspan="2"></td><td colspan="2">Cotton production (x106 t)</td></tr><tr><td rowspan="10">Riparian Forest</td><td>Provisioning services Provisioning services</td><td colspan="2">Fruit production (×10 t)</td></tr><tr><td>Provisioning services</td><td colspan="2">Production of other crops (x10 t)</td></tr><tr><td>Provisioning services</td><td colspan="2">Farmer's income (x10 CNY)</td></tr><tr><td>Provisioning services</td><td colspan="2">Biomass production (x10 t)</td></tr><tr><td>Regulating services</td><td colspan="2">Drifting dust control by riparian forest (kg)</td></tr><tr><td>Regulating services</td><td colspan="2">Sand mobilization control by riparian forest (×10 t)</td></tr><tr><td>Regulating services</td><td colspan="2">Wind control (Attenuation in % at 2 m height) Carbon storage (×106 t)</td></tr><tr><td>Regulating services</td><td colspan="2">Mean species (×106 t)</td></tr><tr><td> Supporting services</td><td colspan="2"> Apocynum production (x106 t)</td></tr><tr><td>Provisioning services</td><td colspan="2"></td></tr><tr><td rowspan="3">Grassland</td><td>Provisioning services</td><td colspan="2">Reed production (t)</td></tr><tr><td>Regulating services</td><td colspan="2">Drifting dust control by grassland (kg)</td></tr><tr><td>Regulating services</td><td colspan="2">Sand mobilization control by grassland (×10 t)</td></tr></table></body></html>

Note: Apocynumis used as amedicinal plantand a fibercrop inthe arid regionof Central Asia.ESS,ecosystemservices.

# 2.4 Logics of DSS

Equations, conditional statements, and fuzzy logic consist the three logical relationships, which connect the parameters inthe DSS

# 2.4.1 Equations

Equations are formed by expert knowledge, theorem, empirical equations and literature findings to build the relationships among the parameters in the DSS. In sum, there were 115 equations established in the DSS. Two examples are given in the following text.

Due to the absence of industry in the region, water consumption in the catchment is comprised of domestic, flooding of natural vegetation, irrigation water use and water losses (Eq. 1). Inflow of the first sub-catchment is given by a model of water availability in semi-arid environments (WASA) depending on the climate scenarios. Because no bifurcation exists in the mainstream of Tarim River, inflows into the sub-catchments are calculated in a simple way each month.

$$
Q ( n + 1 ) = Q ( n ) - Q ( n ) \times P ( \mathrm { d o m e s t i c } ) - Q ( n ) \times P ( \mathrm { f l o o d } ) \times k - \mathrm { I W } \times 0 . 9 6 4 ,
$$

where $Q ( n { + } 1 )$ is the inflow into the next sub-catchment $( \mathbf { m } ^ { 3 } )$ ， $Q ( n )$ is the inflow of the current subcatchment $( \mathbf { m } ^ { 3 } )$ ， $P$ (domestic) is the interpolated value of domestic water use $( \% )$ , P(flood) is the interpolated value of flooding of natural vegetation $( \% ) , k$ is the flood distribution over the month $( \% )$ , and IW is the irrigation water demand of current sub-catchment $( \mathbf { m } ^ { 3 } )$ , which multiplied with a loss factor of 0.964.

Cotton production is calculated cell-by-cell,then aggregated in sum for the DSS output (Eq. 2).

YU Yang et al.: Model based decision support system for land use changes and socio-economic..

$$
\gamma _ { \mathrm { c } } = \left[ 1 - K _ { \mathrm { y } } \left( 1 - \frac { \mathrm { E T _ { a } } } { \mathrm { E T _ { c } } } \right) \right] \times Y _ { \mathrm { m } } \times m / 1 0 0 , \
$$

where $Y _ { \mathrm { c } }$ is the cotton production (t) in each cell, $\mathrm { E T _ { c } }$ is derived from Penman-Monteith method and influenced by crop factors, $\mathrm { E T _ { a } }$ is calculated by MIKE HYDRO, which identified the actual rate of crop evapotranspiration under the effects of soil water stress, $Y _ { \mathrm { m } }$ is the maximum harvest yield $( \mathrm { k g } )$ ， $m$ is the cotton production distribution over months $( \% )$ ，and $K _ { \mathrm { y } }$ is the yield response factor representing the effect of reduction in evapotranspiration on lost yield. $K _ { \mathrm { y } }$ values were obtained from FAO Irrigation and Drainage Paper No. 33 (Doorenbos and Kassam, 1979).

# 2.4.2 Conditional statements

The knowledge of experts are also used to formulate the 'if-then' rules to solve modeling problems. Such conditional construct perform different computations whether a condition is evaluated to be true or false. Conditional statement is a convenient method if the rules are clear and homogeneous. Three examples are given as follows.

For a grassland cell, if groundwater level $< - 5 \mathrm { m }$ in 9 months each year and continues for 7 years, then land use type of the cell will become unused land in the $8 ^ { \mathrm { { t h } } }$ year.

For a high density riparian forest cell, if groundwater level $< - 1 0 \mathrm { ~ m ~ }$ in 9 months each year and continues for 7 years, then the grid cell will become riparian forest with low density in the $8 ^ { \mathrm { { t h } } }$ year.

For a low density riparian forest cell, if groundwater level $< - 1 0 \mathrm { ~ m ~ }$ in 9 months each year and continues for 7 years, then the grid cell will become unused land in the $8 ^ { \mathrm { { t h } } }$ year.

# 2.4.3 Fuzzy logic

In the DSS, some relationships cannot be precisely expressed as equations or conditional statements and a useful method under such circumstance is called fuzzy logic. Fuzzy logic is a logical approach to deal with uncertainty management (Zadeh, 1983). Elements have degrees of membership in the fuzzy set. Membership functions represent the degrees of truth in vaguely defined sets. Unlike possibilities or conditions, the truth values of variables may be any real number between O and 1. Examples of tree height, crown area and drifting dust control by riparian forest are demonstrated in Tables 2-4.

# 2.5 Models linked withDSS

Discharge and glacier geometry changes were simulated with hydrological model WASA (Guntner and Bronstert, 2OO4).The calibration and evaluation of the model were conducted in the headwater catchments of Tarim River. WASA provides daily discharge input into the DSS. Based on different temperature rise and precipitation change projections, four climate scenarios, A1B, PCP2.6, RCP4.5, and RCP8.5, could be selected by users (Duethmann et al., 2016).

Table 2Fuzzy logic of tree height   
Table 3Fuzzy logic of crown area   

<html><body><table><tr><td colspan="4">Membership function for tree height (m)</td></tr><tr><td>Status</td><td>Left bound</td><td>Middle</td><td>Right bound</td></tr><tr><td>Low</td><td>3</td><td></td><td>5</td></tr><tr><td> Medium</td><td>5</td><td>7</td><td>12</td></tr><tr><td>High</td><td>12</td><td>一</td><td>20</td></tr><tr><td colspan="4">Fuzzy rules for tree height</td></tr><tr><td>Rules</td><td>Groundwater level (m)</td><td>Flooding (m)</td><td>Tree height (m)</td></tr><tr><td>If</td><td>High And</td><td>High</td><td>Then High</td></tr><tr><td>If</td><td>Low And</td><td>Low</td><td>Then Low</td></tr><tr><td>If</td><td>Medium And</td><td>Medium</td><td>Then Medium</td></tr><tr><td>If</td><td>High And</td><td>Medium</td><td>Then High</td></tr><tr><td>If</td><td>Medium And</td><td>High</td><td>Then Medium</td></tr><tr><td>If</td><td>Low And</td><td>High</td><td>Then Medium</td></tr><tr><td>If</td><td>High And</td><td>Low</td><td>Then Medium</td></tr></table></body></html>

Note: "-" means not necessary.

JOURNALOFARIDLAND   

<html><body><table><tr><td colspan="4">Membership function for crown area (m²)</td></tr><tr><td colspan="4"></td></tr><tr><td>Status Low</td><td>Left bound 2</td><td>Middle -</td><td>Right bound 6</td></tr><tr><td colspan="2"> Medium</td><td>7</td><td></td></tr><tr><td colspan="2">High</td><td>一</td><td>12 20</td></tr><tr><td colspan="4">10</td></tr><tr><td colspan="4">Fuzzy rules for crown area (m²)</td></tr><tr><td>Rules</td><td>Groundwater level (m)</td><td>Flooding (m³)</td><td></td></tr><tr><td>If If</td><td>High And Low</td><td>High</td><td>Then High</td></tr><tr><td>If</td><td>And</td><td>Low Then</td><td>Low</td></tr><tr><td>Medium If High</td><td>And</td><td>Medium Then</td><td>Medium</td></tr><tr><td>If Medium</td><td>And</td><td>Medium Then</td><td>High</td></tr><tr><td></td><td>And</td><td>High Then</td><td>Medium</td></tr><tr><td>If</td><td>Low And</td><td>High Then</td><td>Medium</td></tr><tr><td>If High</td><td>And</td><td>Low Then</td><td>Medium</td></tr></table></body></html>

Table 4 Fuzzy logic of drifting dust control by high density and low density riparian forest   

<html><body><table><tr><td colspan="4">Membership function for drifting dust control by riparian forest (kg/hm²)</td></tr><tr><td>Status</td><td></td><td>Left bound</td><td>Middle Right bound</td></tr><tr><td colspan="2">Low</td><td colspan="2">0 一 3.3x10-6</td></tr><tr><td colspan="2">Medium</td><td>3.3x10-6 4.2×10-6</td><td>5.8x10-6</td></tr><tr><td colspan="2">High</td><td>6.7×10-6</td><td>8.3x10-6</td></tr><tr><td colspan="4">Fuzzy rules for drifting dust control by riparian forest high density</td></tr><tr><td>Rules</td><td>Crown area (m2)</td><td> Tree height (m)</td><td>Drifting dust control by riparian forest high density (kg/hm²)</td></tr><tr><td>If</td><td>High And</td><td>High Then</td><td>High</td></tr><tr><td>If</td><td>Low And</td><td>Low Then</td><td>Medium</td></tr><tr><td>If</td><td>Medium And</td><td>Medium Then</td><td>High</td></tr><tr><td>If</td><td>Low And</td><td>Medium Then</td><td>High</td></tr><tr><td>If</td><td>Medium And</td><td>Low Then</td><td>High</td></tr><tr><td colspan="4">Fuzzy rules for drifting dust control by riparian forest low density</td></tr><tr><td>Rules</td><td>Crown area (m2)</td><td>Tree height (m)</td><td>Drifting dust control by riparian forest low density (kg/hm²)</td></tr><tr><td>If</td><td>High And</td><td>High Then</td><td>Low</td></tr><tr><td>If</td><td>Low And</td><td>Low Then</td><td>Low</td></tr><tr><td>If</td><td>Medium And</td><td>Medium Then</td><td>Low</td></tr><tr><td>If</td><td>High And</td><td>Medium Then</td><td>Low</td></tr><tr><td>If</td><td>Medium And</td><td>High Then</td><td>Low</td></tr></table></body></html>

For the surface flow, hydrological model MIKE HYDRO (Yu et al., 2O15) provides inputs for the DSS on a catchment level. MIKE HYDRO is a comprehensive deterministic and physically based modeling tool for the simulation of water flow, water supply/demand, soil moisture and crop growing. It has an integrated modular structure with basic computational modules for hydrology and hydrodynamics. The DSS and MIKE HYDRO have the same delineation of sub-catchments (SC): SC1 from Aral to Xinqiman, SC2 from Xinqiman to Yingbazar, SC3 from Yingbazar to Qiala, and SC4 from Qiala to Taitema Lake. The irrigation water demand, ecological water for the natural vegetation, seepage losses, fruit production, and crop yields were calculated and summarized as inputs into the DSS.

For the groundwater simulation, a MODFLOW model was computed with internal links to the DSS on a $5 0 0 ~ \mathrm { m } { \times } 5 0 0 ~ \mathrm { m }$ cell level (Fig. 2). MODFLOW is running parallel with the DSS in the simulation. The daily water head of each cellis simulated in MODFLOW, then updates the cells in the DSS. Groundwater recharge is considered via four different sources: river leakage, irrigation water seepage, infiltration during flood season, and ecological water percolation in the lower reaches.

![](images/6d9bdf4d00d03abd9495f6b28ed80cb5f3c61b28501091aad03442f6bedfb7d3.jpg)  
Fig. 2Hydrological models linked with decision support system (DSS). Model of water availability in semi-arid environments (WASA) provides discharge. MIKE HYDRO provides water consumption and water balance. MODFLOW runs parallel with the DSS on groundwater simulations.SC, sub-catchment; SC1,sub-catchment from Aral to Xinqiman; SC2,sub-catchment from Xinqimanto Yingbazar; SC3, sub-catchment from Yingbazar to Qiala; SC4, sub-catchment from Qiala to Taitema Lake.

It is a challenge to find links between the DSS and other models. The key issue is that the outputs of different models are not uniform as for the input into the DSS. The parameter sets and their relationships vary largely from model to model. The outputs of different models can either serve as stationary data inputs, regression equations, or dynamic data inputs into the DSS as the models running parallel in the simulation periods.

As MIKE HYDRO linked with the DSS on the sub-catchment level, data and equations are bridging the two models. MIKE HYDRO provides simulation results of ecological water for the natural vegetation in the upper and middle reaches in the DSS. Crop productions are linked by yield equations calculated from evapotranspiration. Seepage losses were calculated in MIKE HYDRO and aggregated in monthly values into the DSS. Irrgation water consumptions were distributed in MIKE HYDRO and integrated on sub-catchment level in the DSS.

Particularly, MODFLOW has internal links with the DSS. As the same delineation on the cell level, both models are running parallel in the simulation periods. At the beginning of each year, water heads from MODFLOW results are updating the groundwater levels in the DSS. Groundwater plays a crucial role in the ecosystem, and has large influence on a number of output indicators in the DSS.

# 2.6Graphical user interface of DSS

A user-friendly graphical user interface (GUI) was developed to assist the decision-makers and common users with Chinese and English versions available at the moment. Labels and instructions allow users interact with the DSS more conveniently. The input indicators have default values, acquired from database,literature and expert knowledge. Calculation years start from 2O12 to 2050. The land use map is editable as well in the baseline year, to assist decision-making on land use changes. The GUI is designed to be user-friendly so that more stakeholders and scientists could get involved in using and improving the model. Implementation of the DSS bridges the gap between research and practice through interviews, workshops,and feedbacks.

# 3Results and discussion

# 3.1 Land use changes

Users can freely define the input land use types by clicking the cells in the GUI. In this trial, land use types are remained as they were in the default map which acquired from MODIS data. The baseline year is 2O12,and all the values of input indicators are kept business as usual. the planning years are 2O3O and 2O50, which indicate land use changes in the near and far future (Fig. 3).

![](images/9ca099a23a68bd26b9b37aa333e43a11819e45b4a36fbc25a6793295357832f1.jpg)  
Fig.3Land use changes from 2012 to 2030 and then to 2050

Grassland, natural vegetation and forest willsuffer varying degrees of deterioration in the near and far future if the scenario is kept business as usual. In the upper, middle,and lower reaches, the decay of green areas is obvious. Similar results were shown by the latest findings (Liu et al.,2016; Lv et al., 2016). Because of the low precipitation and flow rate in the dry seasons, vegetation is dependent on summer flood and groundwater. Additionally, riparian forests would be gradually vanished in some regions by 2O5O, especially in the middle reaches. Since coton and other agricultural fields are determined by anthropogenic activities, farmland areas remain unchanged throughout the simulation period. However,the consequences of farmland changes can be revealed by output indicators if a user changes the land use types in the first place. In the middle reaches, where riparian forest (mostly $P$ . euphratica) is mainly growing, forest degradation will be severe by 2050 (Fig. 4).

Simulation results indicate that both forest area and density have been reduced in various degrees In several hotspots, riparian forest areas have substantially dwindled or even faded away. Theses hotspots are all located on the north of the river. Population is one reason to identify a hotspot, where deforestation could be a big threat to the living conditions of local residents. Another reason is the vanishing points of forest in several regions, which would be a destruction to ecological balance in arid land. Groundwater recesson is the reason for forest decay in the model, as deforestation has been prohibited in the oases along the Tarim River. Continuous low groundwater level for more than 7 years is considered fatal to the forest. The correlations between groundwater and $P$ . euphratica were also discussed by Thomas (Thomas et al., 2O17)， who made further discussions on the threats for these precious trees.

![](images/4879460ee247530a47305fe9012d991b0b38c6e47905d8d565e511950509d1e0.jpg)  
Fig.4 Forest degradation in the middle reaches of Xinqiman to Qiala sub-catchments from 2012 to 2050

# 3.2 Downstream outflow

The natural terminal of Tarim River is Taitema Lake. However, due to long-term water interception downstream, the outflow of Tarim River is studied at Daxihaizi Reservoir. The reservoir is located $3 5 8 ~ \mathrm { k m }$ upstream of the river till Taitema Lake. The outflow of Tarim River in future years is dependent on the upstream discharge and water consumption along the oases, which were calculated from the other hydrological models. Simulation results indicate an increasing trend of outflow in 2020, and decreasing trends in 2030 and 2040 (Fig. 5).

![](images/eda9886175df3473ec4fcc89727aea3efcafbdf8b03406faf94eda39d246e882.jpg)  
Fig.5Downstream outflow in the Daxihaizi Reservoir

Peak volumes of outflow appeared in July, with $7 . 3 { \times } 1 0 ^ { 8 }$ . $9 . 5 { \times } 1 0 ^ { 8 }$ . $6 . 9 \times 1 0 ^ { 8 }$ ，and $5 . 9 { \times } 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ in 2012, 2020, 2030,and 2040,respectvely. From Figure 5, it was noticeable that summer flood last two months in July and August, and drop dramatically in September. These results agreed with the outputs of hydrological model (Yu et al., 2O15). Dry season occupied most of the year. In June, water deficits occurred in all the simulation years. Particularly, near $4 . 0 { \times } 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ of water shortage was predicted in June 2040. A noticeable water deficit also showed up in September 2040, which is the first time that the outflow water is on shortage in September. Upstream reservoirs need to prepare enough storage for the water crisis in future.

# 3.3 Socio-economic outputs

Cotton production, fruit production, biomass production, mean species of plants, farmer's income, wind control, drifting dust control by riparian forest, drifting dust control by grassland, and sand mobilization control by grassland are shown as examples for the socio-economic assessments (Fig. 6). These indicators were calculated separately in the four sub-catchments of Aral to Xinqiman, Xinqiman to Yingbazar, Yingbazar to Qiala, and Qiala to Taitema Lake. Simulation period is from 2012 to 2050, and all the inputs were kept as default values.

SC1 SC2 SC3 SC4 0.35 (a) Cotton production 0.09 (b) Fruit production 3.0 (c) Biomass production   
88898 0.06 2.0- 0.05 1.5 0.04 0.03 1.0 0.05- 0.02 0.5 0.00 0+ 0- 3029 2444 2282 2 3002 24220 2130 2442 228 2555 140 (d) Mean species of plants (e) Farmer's income E 120 5000   
Nmee 100 4000- 6042 30000 自 2230 14280 (g) Drifting dust control (h) Drifting dust control (i) Sand mobilization by riparian forest by grassland control by grassland ！ 5040300 1.5 · 1.0 2010 0.5 0 0 3 200 23 212 22038 0 11380 2420 2240

Cotton production has an increasing trend in all the sub-catchments. The largest cotton production region is within SC1, but the fastest production growth comes from SC4. This result complies with the study of Xu et al. (2OO8), who warned that the agricultural development in the lower reaches may cause water scarcity problems for the ecosystem. Fruit production also has a rising trend, and develops rapidly in the lower reaches. Biomass production experiences an increasing period till 2O18, then drops in 2O19 and remains steady afterwards. The reason for this sudden change may be because the rules in DSS are not complex and smooth enough， and quantitative accumulations lead to a qualitative transformation in 2019.

The number of mean species of plants has a steady growth, similar to farmer's income. Because of the development of economic crops,farmer's income in the lower reaches has the largest growth among all the sub-catchments. Due to lacking of clear policy and data in future years, change of population and migration are not considered in current version of the DSS. Wind control and drifting dust control by riparian forest remain stable, even the forest area in shrinking. This is caused by the contribution of growing tree height and crown area. In comparison, drifting dust and sand mobilization control by grassland have declined in varying degrees until 2050.

One scenario was tested as an example for land use management and assessment (Fig. 7). In the baseline year of 2012, $4 \times 1 0 0$ cells $( 1 \times 1 0 ^ { 4 } \mathrm { h m } ^ { 2 } )$ of cotton fields are changed into grassland in the first sub-catchment to investigate the consequences of this action in future years until 2030.

The simulation results indicate the reduction of cotton production and farmer's income, and increase of sand mobilization control by grassland after land use change. Cotton production provides the main income for local farmers. From a local decision-maker's point of view, if the losses of farmer's income are too large to bear, then this land use change scenario may not be accepted. However, if sand mobilization control is considered more important than the economic losses, the decision-maker may adopt this scenario,and mitigate the farmer's losses in other ways. Additionally, the increased portion of sand control is shrinking in the future years. This phenomenon indicates either groundwater level is too low in the fields, or groundwater salinity is too high for grass to grow.

![](images/57bae6e6861c976dd40717fd3c95ff96d45836bb28084057f3855ee0cbf7fcdd.jpg)  
Fig. 7Editable land use map in the DSS. In SC1, $4 \times 1 0 0$ cells of cotton fields are changed into grassland in 2012. Cotton production,farmer's income and sand mobilization controlby grassland are investigated as output indicators of this action.

# 3.4Uncertainties and further developments

In the DSS, the delineation of regions is relatively homogeneous in multiple criteria, including hydrological, meteorological, geographical, ecological, socio-economical, and political aspects. Therefore， the complexity of the management practices cannot be completely reproduced. Equations, conditional statements and fuzzy logic all have limitations in the delineation of parameter relationships, and thus cause uncertainties by temporal and special changes on specific maters. Socio-economic and management indicators (e.g. cotton price, farmland area and drip irrigation coverage) are often sensitive to the change of government policies and water authority regulations, which could cause large uncertainties in future planning years.

Although the hydrological models were calibrated and validated to increase the possibility of more reliable results, the DSS has not been calibrated so far. However, a comprehensive model calibration requires the feedback from local stakeholders, more statistical data, and a better understanding of the DSS itself. Since the DSS involves knowledge on varying aspects, no individual developer is able to master allthe criteria. Interdisciplinary cooperation is as important in the implementation and optimization phase as it was in the system developing phase.

It is difficult to say which scenario has the most robustness, or one scenario is more preferable than the other. Based on a number of trials and comparisons with real data, most outputs of the DSS were reasonable and comply with the knowledge and perceptions of local stakeholders. However, the sensitivity of soil salinization change are lower than expected. Because winter irrigation uses extra water to washes down the salt, salinization on the surface soil should be changed obviously in winter. The process of winter irigation is not included in the simulation of DSS at the moment, and can be considered as a special stress to increase system reliability in future improvements.

# 4 Conclusions

A model based DSS was developed to assist the stakeholders with decision-making on sustainable land management and socio-economic assessments in the oases along the Tarim River. The development and implementation of DSS involves knowledge of experts in interdisciplinary research aspects, as well as the experiences and feedbacks from a large number of local stakeholders. The DSS has notable features in a number of research aspects.

(1) Editable land use maps in the GUI were developed to assist stakeholders of decision-making on land use management. The clicking and drawing on the land use map provide stakeholders a catchy approach for examining land management alternatives. If the scenario is kept business as usual in the simulation, then natural vegetation, riparian forest and grassland would suffer varying degrees of deterioration in the near and far future. In the upper, middle and lower reaches, the decay of nature vegetation are obvious.

(2) The conjunctive use of surface and subsurface water resources provide more accuracy on the system. The DSS integrates the hydrological data, geographic data, social and economic statistical data,and establishes the relationships with equations, conditional statements and fuzzy logics. Under scenario assumptions, possible actions and their impacts are estimated in a semi-quantitative way with the help of climate indicators, socio-economic indicators, management indicators, and ESS indicators. Socio-economic outputs illustrate more crop productions and farmer's income, but weaker sand mobilization and drifting dust control in future.

(3) The integration of expert knowledge on interdisciplinary studies gave specific insights on the interactions among water, earth, ecosystem and human activities. The system does not only consider direct impacts, but also side effects among different matters. For instance, increased irrigation water may raise crop production, but it can also cause less water for winter flooding, therefore aggravate salinization on the field, and lead to less yield in the end.

(4) Links with hydrological models help reduce system complexity and increase model accuracy of the DSS. MODFLOW is running parallel in the simulation periods with the DSS. WASA provides discharge inputs, and MIKE HYDRO simulates irrigation and ecological water consumptions. Al the outputs of theses hydrological models were taken as inputs into the DSS. After the calculations of water balance in the DSS, simulation results indicate an increasing trend of outflow in 2020,and a decreasing trend in 2030 and 2040.

Though many expert knowledge and stakeholder feedbacks were considered in the developing phase, the DSS should not be recognized as an end product. Lots of estimations and uncertainties still remain in the system, which requires further research and development. The GUI was designed to be user-friendly so that more common stakeholders can use and improve the system, and make the steps in bridging the gap between research and IWRM practice.

# Acknowledgements

This study was supported by German-Sino bilateral collaboration research project SuMaRiO funded bythe German Federal MinistryofEducation and Research. We are grateful to the supportof NSFC-UNEPProject (41361140361): Ecological Responses to Climatic Change and Land-cover Change in Arid and Semiarid Central Asia during the Past 500 Years.This work is the outcome of the interdisciplinary cooperation research among 11 German and 9 Chinese universities and research institutes. Many further researches and projects can learn experience from the algorithm and methodologies ofthe DSS,whichisapplicable toother regions.TheDSS is free available onrequest. Comments and further discussions are welcome.

# References

climate and socio-economic scenarios. Climatic Change, 122(1-2): 127-140.   
Basso B,RitchieJT.2015.Simulatingcrop growthandbiogeochemicalfluxes inresponse toland management using theSALUS model. In: Hamilton S K,DollJE,Robertson GP.The Ecologyof Agricultural Landscapes: Long-termResearch onthePath to Sustainability. New York: Oxford University Press,252-274.   
Biswas AK.2008.Integrated waterresources management:isit working?InternationalJournalof WaterResources Development, 24(1): 5-22.   
Chen YN,Li WH, Xu CC,etal.2O15.Desertriparian vegetation and groundwater in the lower reaches of the Tarim River basin. Environmental Earth Sciences, 73(2): 547-558.   
Chenoweth T,Dowling KL,St.Louis RD.2004.Convincing DSSusers thatcomplex modelsare worth theeffort.Decision Support Systems,37(1): 71-82.   
Disse M.2O16.Sustainable landand water management ofRiver Oases along the Tarim River. Procedings of the International Association of Hydrological Sciences, 373: 25-29.   
Doorenbos J, Kassam A H. 1979. Yield Response to Water. Rome: FAO, 257.   
Duethmann D,Menz C,JiangT,etal.2016.Projections forheadwatercatchmentsofthe TarimRiverreveal glacierretreatand decreasing surface water availability but uncertainties are large.Environmental Research Leters,11(5): 054024.   
Feng Q,EndoKN,Cheng GD.2001.Towardssustainable developmentofthe environmentalldegradedarid rivers of China a case study from Tarim River. Environmental Geology, 41(1-2): 229-238.   
FlorkeM,KynastE,BarlundIetal.213.Domesticandindustrial waterusesof thepast6yarsasamirrorofsocicoomc development: a global simulation study. Global Environmental Change,23(1): 144-156.   
Giordano M, Shah T.2014.From IWRMback to integrated water resources management. International Journal of Water Resources Development, 30(3): 364-376.   
GuntnerA,BronstertA.2O04.Representationof landscapevariabilityand lateral redistribution processs for large-scale hydrological modelling in semi-arid areas. Journal of Hydrology, 297(1-4): 136-161.   
Herero M,Thornton PK,Bernués A,et al. 2O14. Exploring future changes insmallholder farming systems bylinking socio economic scenarios with regional and household models. Global Environmental Change,24: 165-182.   
Jefrey P,GeareyM.2O06.Integrated waterresources management:lostontheroadfromambition torealisation?WaterScience & Technology,53(1): 1-8.   
Liu GL,Yin G, Kurban A,etal.2016.Spatiotemporaldyamicsoflandcoverand theirimpacts onpotentialdustsourceregions in the Tarim Basin, NW China. Environmental Earth Sciences,75(23): 1477.   
Liu XP,Meng M.2011.Sustainable land use andthecouplingrelationof ecological economic harmonious development: acase study of Tarim River Basin. Arid Land Geography, 34(1): 173-178. (in Chinese)   
Liu YB,ChenYN.2Oo6.Impactof populationgrowthandland-usechange on waterresources and ecosystems of thearidTarim RiverBasin in WesternChina.The International Journal ofSustainableDevelopment & World Ecology,13(4): 295-305.   
Lv X,Liu X P,Li ZB.2016.Coupling of ecological economic system in TarimRiver Watershed.In: QuFT,SunRM, Guo Z X,et al. Ecological Economics and Harmonious Society. Singapore: Springer, 197-208.   
McCow R L. 2002. Locating agricultural decision support systems in the troubled past and socio-technical complexity of ‘models for management'. Agricultural Systems, 74(1): 11-25.   
Pedro-Monzonis M,Jiménez-Fernandez P, Solera A,et al. 2016.The use of AQUATOOL DSS applied to the Systemof Environmental-Economic Accounting for Water (SEEAW). Journal of Hydrology, 533: 1-14.   
Power DJ,Sharda R,Burstein F.2O15. Decision support systems.Volume7.Management information systems. In: Cooper CL. Wiley Encyclopedia of Management. New York: John Wiley & Sons,Ltd, 1-11.   
QuevauvillrP.2010.I IWRMachievablei practice?Atempts tobreak disciplinaryandsectoral wals through ascience-olicy interfacing framework inthecontextof theEU WaterFramework Directive.Irigationand drainagesystems,24(3-4):177- 189.   
RumbaurC,Thevs N, Dise M,et al.2O15.Sustainable management of river oases along the Tarim River (SuMaRiO)in Northwest China under conditions of climate change. Earth System Dynamics,6(1): 83-107.   
ThomasFM,Jeschke M, Zhang X M,etal.2O17.Stand structure and productivityof Populus euphratica along a gradientof groundwater distances at the Tarim River (NW China). Journal of Plant Ecology, 10(5): 753-764.   
Visconti P,BakkenesM,SmithRJ,etal.2015.Socieconomicandecologicalimpactsoflobalprotectedareexpasioplas. Philosophical Transactions of the Royal Society B: Biological Sciences,370(1681): 20140284.   
WenkelK O,BergM,Mirschel W,etal.2013.LandCaReDSS-Aninteractive decisionsupportsystemforclimate change impact assessment and theanalysis of potentialagricultural landuse adaptation strategies.Journal of Environmental Management, 127(Suppl.): S168-S183.   
West GG,TurnerJA.2014.MyLand: a web-basedand meta-modeldecisionsupportsystem framework for spatialand temporal evaluation of integrated land use. Scandinavian Journal of Forest Research,29(Suppl.): 108-120.   
Xu HL,Ye M,LiJM.2Oo8.The watertransferefectsonagriculturaldevelopmentinthelowerTarimRiver,Xinjiangof China. Agricultural Water Management, 95(1): 59-68.   
Yu Y,Disse M,YuRD,etal.2O15.Large-scale hydrological modelinganddecision-makingforagriculturalwaterconsuption and allocation in the main stem Tarim River, China. Water, 7(6): 2821-2839.   
YueHL,ZhuYP,XueY,etal.2014.Studyocountiesagculturaleconomicintellgentdeisio-makingsupportsytem(s) based on GIS and knowledge. Advanced Materials Research, 889-890: 1319-1322.   
ZadehLA.1983.The roleoffuzzylogic inthe managementofuncertainty in expert systems.FuzzySets andSystems,11(1-3): 199-227.   
Zhang Q,SunP,LiJF,etal.2O15.AsessmentofdroughtvulnerabilityoftheTarimRiverbasin,Xijiang,China.Trtical and Applied Climatology, 121(1-2): 337-347.   
Zhang Z,Hu H,TianF,etal.2O14.Groundwaterdynamicsunder water-saving irigationandimplications forsustainable water management in an oasis: Tarim River basinof western China. Hydrology and Earth System Sciences,18(10):3951-3967.   
Zhao RF,ChenYN,Li WH,etal.2O9.Landcoverchangeandlandscape patterinthe mainstreamoftheTarimRiverActa Geographica Sinica,64(1): 95-106.(in Chinese)