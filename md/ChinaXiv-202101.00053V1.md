# Assessment of drought hazard, vulnerability and risk in Iran using GIS techniques

Esmail HEYDARI ALAMDARLOO1, Hassan KHOSRAVI1\*, Sahar NASABPOUR', Ahmad GHOLAMI²

1Departmentof AridandMountainous Regions Reclamation,Facultyof Natural Resources,Universityof Thran,Thran31587 77871, Iran; ² DepartmentofOrganic &Polymer Chemistry,FacultyofChemistry,Kharazmi University,Tehran 15719-14911,Iran

Abstract: The drought has enormous adverse effects on agriculture, water resources and environment,and causes damages around the world. Drought risk assessment and prioritization of drought management can help decision makers and planners to manage the adverse effects of drought. This paper aims to determine the risk of drought in Iran.At the first stage,standardized precipitation index (SPI) was calculated for the period 1981-2016. Then the probability map of different drought classes or drought hazard probability map were prepared.After that the indicator-based vulnerability assessment method was used to determine the drought vulnerability index. Five indices including climate,topography, waterway density, land use and groundwater resources were chosen as the most critical factors of drought in Iran and folowed by the analytical hierarchy process questionnaire,the weights of each index were obtained based on expert opinions.Fuzzy membership maps of each index and sub-index were prepared using ArcGIS software. The drought vulnerability map of Iran was ploted using these weights and maps of each indicator.Finaly, the drought risk map of Iran was provided by multiplying drought hazard and vulnerability maps. According to the 43-completed questionnaires by experts,climate index has the highest vulnerability to drought. Climate does not have an important role in drought hazard index,but it is the most crucial factor to classified drought vulnerability index.The results showed that central, northeast, southeast and west parts of Iran are at high risks of drought.There are regions with different risks in Iran due to unusual weather and climatic conditions.We realized that the climate and the groundwater situation is almost the same in the central, east and south parts of Iran,because the land use plays a crucial role in the drought vulnerability and risk in these areas.The drought risk decreases from the center of Iran to the southwest and northwest.

Keywords: climate map;standardized precipitation index; analytical hierarchy proces; fuzzy membership; weight

# 1 Introduction

Drought is one of the most destructive natural phenomena which have devastating impacts on agriculture, water resources and environment (Dow, 2010; Popova et al.,2O14; Yu et al., 2014). This phenomenon starts slowly but can take a long time and covers a large area compared to the other natural hazards (Rossi et al.,1992; Mishra and Singh,2010; Lena et al.,2014). In the future, with an increase in severe weather incidents,it is expected that drought willoccur more often and stronger (Trenberth et al.,2014).

The definitions of drought are classified as meteorological drought，hydrologic drought, agronomic and social economic drought (Dracup et al.,1980; Orvile,1990; Wu et al.,2016). Meteorological drought is the most important type (Nasrollahi et al., 2O18),which is the driving force behind other droughts,resulting in a reduction in the average long-term precipitation. With the meteorological drought, its adverse efects appear and the other types of drought will gradually take place and the combind adverse impacts can cause the destructive impacts in an area.

Economically speaking，drought is the most dangerous natural phenomenon during history (Karabulut, 2015) and has always endangered global food security (Dai, 2O1; Mu et al., 2013). Owing to the consumption of water resources in recent decades, new aspects of drought has emerged,and it has affected the enormous human population around the world for years (Kim et al.,2013;Lei et al.,2O16). Hence,how to manage drought is one of the essential challenges worldwide (He et al.,2013).

In recent years,a risk-oriented approach has been adopted for disaster risk management (Tonini et al.,2012; Skakun et al., 2O14). In this regard, governments have attempted to develop a drought management policy with emphasizing on risk management instead of the traditional approach (Wilhite,20oo； Sivakumar and Wilhite,2OO2). Evaluation of drought risk is a two-argument function including drought hazard and vulnerability (Jonkman et al.,2O03; IPCC, 2O07; Jayanthi et al., 2013).

Drought hazard assessment is the vital aspect of drought risk (Hao et al.,2O12),which means investigation of probability for drought intensity and its frequency (Zhang and Zhang,2016). Repetition of high-intensity drought can have hazardous effects (IPCC, 2OO7). Drought hazard describes physical aspects of drought and has an essential role in the connection between drought risk and vulnerability (He et al., 2O11).Therefore,drought hazard is the most important aspect of drought risk (Hao et al.,2O12).Drought hazard can be defined as a probability for drought intensity and its frequency (Zhang and Zhang,2O16). In other words,drought hazard is the probability of drought occurrence.The drought hazard index is calculated by statistical analysis of drought indices like standardized precipitation index (SPI)， standardized precipitation evapotranspiration index (SPEI) and Palmer drought severity index (Zargar et al., 2O11; Beven et al.,2018).

The vulnerability is a broad concept with various definitions (Easter,1999;Birkmann, 2006; Fussel,2OO7). Vulnerability means human and natural potential sensitivity of an area when drought occurs. In other words, the differences between natural properties and economical-social features caused different sensitivity when drought occurs (Santos et al., 2OO1). There are different ways to measure drought vulnerability. One of the most common methods is index-based vulnerability assessment (IBVA） methods.To quantify the vulnerability, IBVA depends on several potential indices and combining them with the related levels of vulnerability. Many researchers have used this method in local and global scales (Moss et al.,2001; Leichenko and O-Brien, 2002; Vincent, 2004;Ashok and Sasikala, 2O12). There are two options for calculating the vulnerability using IB VA.The first is to consider the equal importance and therefore equal weight for all factors (MeBar and Valdez,2Oo5)；and the second is to find the different emphasis and to assign different weights to the factors causing vulnerability. In the second option, there are different approaches to consider different weights. To determine the weights of the factors influencing vulnerability, techniques such as the analytical hierarchy process (AHP) can be used.

Many studies on drought hazard, vulnerability to drought and drought risk have been carried out. For example, Sahahid and Behravan (2OO8) used several physical factors such as soil available water capacity, production amount and percentage of the irigated area; and socio-economic factors such as population density, gender ration and the rate of people employed in the agriculture sector to provide the map of vulnerability to drought in the west of Bangladesh.

Han et al. (2O16) calculated the comprehensive drought risk index of southwestern China using climatic, geographic, soil and remote sensing data, with the help of AHP. The results of the research indicated that prevention capacity factor and reducing drought, drought hazard,sensitivity and environmental vulnerability are involved in calculate the drought risk index.

Nasrollahi et al.(2O18) studied the drought risk of Semnan province of Iran.In this research drought hazard was calculated using SPI. Vulnerability of the area to drought was evaluated by indices such as agricultural land and water used in domestic,agronomy and industry sections.The results show that the most significant part of the study area has the medium $( 6 2 . 4 6 \% )$ and very intense $( 5 3 . 1 2 \% )$ drought risk. Chen et al.(2O19) evaluated drought risk in agriculture in China using SPI to determine the drought hazard. Results show that agricultural drought risk decrease from northeast to southwest. They suggested that the research results can be used to mitigate the effects of future droughts in China. To study the future drought risk in Africa,Ahmadalipour et al. (2019)calculated drought hazard index using SPEI. The drought vulnerability index was calculated by available layer such as land use and water resources,etc.The drought risk was predicted based on two climate scenarios for 21Oo. The results indicate that Africa would face an unprecedented drought hazard if there is no risk management plan against to climate change.

Drought is one of the most costly natural disasters (Lee et al.,1999; Khoshnodifar et al., 2012), having adverse environmental, social and economic impacts in Iran. The researches on climate change indicate that the frequency and duration of drought in the Middle East will also increase (Dai, 2011). Government activities in Iran have focused on drought crisis management (response to drought and recovery),but supervision and increase readiness to copy with drought as risk management has not been considered (Nasrollahi et al., 2O18). So, assessment of drought risk and prioritizing management strategies to cope with this phenomenon is necessary. Therefore this paper tries to demonstrate the probability of drought map of Iran to determine drought-vulnerability areas in Iran for management when severe drought occurs.

# 2 Materials and methods

# 2.1 Study area

Iran ( $( 1 . 6 5 { \times } 1 0 ^ { 6 } ~ \mathrm { k m } ^ { 2 }$ ： $2 5 ^ { \circ } 0 3 ^ { \prime } - 3 9 ^ { \circ } 4 7 ^ { \prime } \mathrm { N } _ { \cdot }$ $4 4 ^ { \circ } 1 4 ^ { \prime } { - } 6 3 ^ { \circ } 2 0 ^ { \prime } \mathrm { E } )$ has very different weather conditions due to its broad ecological diversity and terrain variety (Heydari et al.,2O18; Behrang,2O19).Figure 1 shows the climatic diversity of Iran, which was prepared by mixing different classes of climate map developedbyIran Forests，Range and WatershedManagementOrganization (http://www.frw.org.ir/Oo/En/default.aspx).

![](images/385f8ca3448bea37c0f27ecc651b2420e5cb541b3300ed6097aca5232063bbf1.jpg)  
Fig.1Location of the study region,distribution of synoptic stations and climatic diversity in Iran

# 2.2 Data

The data of 46 meteorological stations including the mean annual precipitation, temperature and evaporation were obtained from the Iran Meteorological Organization (http:// http://www.irimo.ir). The meteorological data were interpolated using the IDW (inverse distance weighting) method in ArcGIS 10.3 (Esri, USA).Locations of the meteorological and interpolated stations in Iran are shown in Figure 1. For groundwater resources condition,the data of piezometer wells prepared by Iran Water Resources Management Company (https://www.wrm.ir/） were used. The waterways layer of Iran was prepared by Forests Range and Watershed Management Organization of Iran (htp://www.frw.org.ir/O2/En/). The land use layer of Iran was provided by Forests Range and

Watershed Management Organization of Iran (http://www.frw.org.ir/O2/En/).For topography index the DEM (digitial elevation model) $9 0 \mathrm { ~ m ~ }$ of Iran (https://cgiarcsi.community/data/srtm-90mdigital-elevation-database-v4-1/) was used to provide slope, aspect and height layers.

# 3Methodologies

# 3.1 Drought hazard

The monthly precipitation data of 46 synoptic stations with long-term (1981-2016) and reliable statistics were selected to calculate the drought hazard (Fig.1).The data of station were completed and their missing data were estimated from the nearest neighbor stations using linear regression. Then,the SPI was used to determine the drought hazard (Potop et al., 2012).

In order to calculate the SPI, the precipitation data of the statistical period of each station were fitted to the gamma probability distribution function, $g ( x )$ ,as Equation 1.

$$
g ( x ) = \frac { x ^ { \alpha - 1 } e ^ { - x / \beta } } { \beta ^ { \alpha } \Gamma ( \alpha ) } \quad ( x > 0 ) ,
$$

where $\alpha$ is the shape parameter, which is estimated using the method of maximum likelihood; $\beta$ is the scale parameter; $x$ is the precipitation $\left( \mathrm { m m } \right)$ ; and $\Gamma ( \boldsymbol { a } )$ is characteristics of the gamma function. The parameters of $g ( x )$ were calculated by the following equations:

$$
\alpha = \frac { 1 } { 4 A } \left( 1 + \sqrt { 1 + \frac { 4 A } { a } } \right) ,
$$

$$
\beta = \frac { \overline { { x } } } { 4 A } ,
$$

$$
A = \left[ \ln ( { \overline { { x } } } ) - { \frac { \displaystyle \sum \ln ( x ) } { n } } \right] ,
$$

where $A$ is a dimensionless component used for calculation of $\alpha$ and $\beta ; n$ is the number of rain observations；and $\bar { x }$ is the average precipitation $\left( \mathrm { m m } \right)$ for a given month during the statistical period.The calculated parameters allow the distribution of precipitation at the station be efectively represented by a cumulative mathematical probability function, $G ( x )$ ,as Equation 5.

$$
G ( x ) = \int _ { 0 } ^ { x } \frac { 1 } { \beta ^ { \alpha } \Gamma ( \alpha ) } \int _ { 0 } ^ { x } x ^ { \alpha - 1 } e ^ { - x / \beta } d x .
$$

Since the gamma function is not defined for $\scriptstyle x = 0$ ，the distribution of the precipitation become zero.

$$
H ( x ) = q + ( 1 - q ) G ( x ) ,
$$

where $H ( x )$ is the cumulative probability function if $\scriptstyle x = 0$ and $q$ is zero probability. $H ( x )$ then converted to the standard normal distribution for calculating SPI values ((Mckee et al.,1993).

To simplify operations and increase the accuracy of calculations,the DIP (Drought Index Package) software version 2 was used to calculate SPIin a 12-month time step (Morid et al.,2005). After calculating the SPI, the classification of the drought severity was performed (Table 1).

In this study, drought hazard was evaluated by the probability of drought occurrence.To calculate the drought probability,at first, the occurrence frequency of different drought classes including moderate, severe and too severe was determined in each synoptic station. Then,by a division of probability of drought occurrence in each category to allpossible states,the percentage of drought probability in each category was calculated.In the next step,the point data interpolation was performed using geostatistical analysis tools through IDW method in ArcGIS 10.3.

Table 1SPI (standardized precipitation index) classification (Mckee et al.,1993)

JOURNALOFARIDLAND   

<html><body><table><tr><td>Drought category</td><td>SPI value</td></tr><tr><td>Too severe drought</td><td>≤-2.00</td></tr><tr><td>Severe drought</td><td>-1.99<SPI< -1.50</td></tr><tr><td>Medium drought</td><td>-1.49<SPI<-1.00</td></tr><tr><td>Normal</td><td>-0.99<SPI<0.99</td></tr><tr><td>Medium wet</td><td>1.00<SPI<1.49</td></tr><tr><td>Severe wet</td><td>1.50<SPI<2.00</td></tr><tr><td>Too severe wet</td><td>≥2.00</td></tr></table></body></html>

Because various drought intensities do not have the same value,for quantifying and mapping the drought hazard,the weight was given to each class of drought according to Table 1. The rating of 1 to 4 was assigned to the moderate, severe and very severe drought groups (Table 2). The map of each intensity class was classified into four subclasses based on percentage probability value using natural break method. This method based on a computational algorithm tries to minimize the differences between the data in each class and to maximize the distinctions among categories. This algorithm uses the average of each range for creating classes to achieve greater uniformity for distributing data. In this study,ArcGIS 10.3 was used to determine natural break points. Then, number 1 and 4 were assigned to the subclass with the lowest and highest probabilities of drought, respectively.

Finally, the drought hazard index (DHI) was calculated using Equation 7 and ArcGIS 10.3 in a time step of 12 months:

$$
\mathrm { D H I } = ( \mathbf { M } \mathbf { D } \mathbf { r } \times \mathbf { M } \mathbf { D } \mathbf { w } ) + ( \mathbf { S } \mathbf { D } \mathbf { r } \times \mathbf { S } \mathbf { D } \mathbf { w } ) + ( \mathbf { V } \mathbf { S } \mathbf { D } \mathbf { r } \times \mathbf { V } \mathbf { S } \mathbf { D } \mathbf { w } ) ,
$$

where $\mathbf { M D } _ { \mathrm { r } }$ ， $\mathrm { S D } _ { \mathrm { r } }$ ,and $\mathrm { \Delta V S D _ { r } }$ are given rating to the moderate drought (MD),severe drought (SD) and very severe drought (VSD), respectively, and $\mathbf { M D } _ { \mathrm { w } }$ $\mathrm { S D } _ { \mathrm { w } }$ ,and $\mathrm { \Delta V S D _ { w } }$ are weights for moderate, severe and very severe drought. According to Equation 1,DHI can have a value of 6-24.Then, DHI maps can be classified into four classes of low, moderate, severe and very severe.

Table 2Weight and rating assigned to the drought in a time step of 12 months   

<html><body><table><tr><td>Drought class</td><td>Weight</td><td>Rating</td><td>Occurrence probability"(%)</td><td>Area (%)</td></tr><tr><td rowspan="4">Moderate drought</td><td rowspan="4">1</td><td>1</td><td>≤6.96</td><td>20.02</td></tr><tr><td>2</td><td>6.96-8.69</td><td>42.23</td></tr><tr><td>3</td><td>8.69-10.56</td><td>28.89</td></tr><tr><td>4</td><td>≥10.56</td><td>8.86</td></tr><tr><td rowspan="4">Severe drought</td><td rowspan="4">2</td><td>1</td><td>≤3.76</td><td>32.21</td></tr><tr><td>2</td><td>3.76-5.05</td><td>39.92</td></tr><tr><td>3</td><td>5.05-6.84</td><td>14.89</td></tr><tr><td>4</td><td>≥6.84</td><td>12.98</td></tr><tr><td rowspan="3">Very severe drought</td><td rowspan="3">3</td><td>1</td><td>≤1.59</td><td>12.47</td></tr><tr><td>2</td><td>1.59-2.34</td><td>35.43</td></tr><tr><td>3</td><td>2.34-3.03</td><td>43.18</td></tr><tr><td></td><td></td><td>4</td><td>≥3.03</td><td>8.92</td></tr></table></body></html>

Note:",the occurrence probability of each rating was calculated using natural break method in ArcGIS 10.3.

# 3.2 Drought vulnerability

In this study,IBVA method was used to calculate the drought vulnerability.At first,effective indices of drought vulnerability was determined. They are selected according to the purpose of the study and properties of the study areas (Hinkel, 2O11;Araya-Munoz et al., 2O17) and their variation (Dabanli,2O18).Based on the previous studies and consultation with Iranian experts in the field of drought, five indices including climate, topography, waterway density,land use and groundwater resources were selected and for each index some sub-indices were considered (Fig. 2).

The AHP method, e.g., pairwise comparison matrix, was used for weighing each effective index and sub-indices (Sadeghravesh et al.,2O15). After the formation of the pairwise matrix,if the matrix contrariety rate was acceptable, the weight of each criterion was calculated (Malczewski,1999; Hill et al.,2Oo5).The 43-completed questionnaires by drought experts were used for analyzing and estimating the weight of each index and sub-index. Also,Expert Choice (Expert Choice Inc., USA) was used for formation of the pairwise matrix,calculating the contrariety rate,relative and final weights of criteria.

![](images/30ae212eb57b7f7faf6ca9352d0f7f1bafe47b0fdbdfbe280ccec24c672ae38f.jpg)

Fig.2Analytic hierarchy process (AHP) for drought vulnerability determination In the next step,the map of each index and sub-index were prepared in ArcGIS 1O.3.The selected indices,sub-indices and the method for calculating them are described as follows: · Groundwater resources index: groundwater is one of the essential factors which affects drought vulnerability (Jordaan et al.,2O19). In this study, groundwater resources index was divided into two sub-indices: water depth average and annual groundwater drop level. The fundamental data of these two indices were calculated by the reported 17-a data (2000- 2016).A special water depth average and an average amount of annual groundwater drop level were atributed to each sub-watershed.Maximum weight was for the watershed which had the highest amount of drop and depth; and this watershed was much sensitive to drought and vice versa. . Waterway density index: high density of waterway shows much runoff water. Consequently, much runoff in an area increases sensitivity against drought (Jain et al.,2015). 1 Climate index: climate is one of the most important factors in determining drought vulnerability. The index of climate included three sub-indices of precipitation, evaporation and temperature. For the preparation layer of these three sub-indices,data of mean precipitation, evaporation and annual temperature of 46 synoptic stations of the country in the period 1981-2O16 were used.Then, zoning was conducted for the three sub-indices using conventional Kriging method in ArcGIS 10.3. Increasing precipitation decreases drought severity，so regions with more precipitation will have a lower weight value. Raising temperature increases the susceptibility to drought, accordingly, the maximum weight value assigned to the areas with the maximum temperature,and the minimum weight value was allocated to areas with the minimum temperature.The difference between evaporation and precipitation can be considered as a factor in assessing drought. Increasing this difference will increase the sensitivity to drought. Thus,areas with more difference allocated more weight. Land use index: one of the most important indices which afect vulnerability is land use (Nelson et al., 2Oo5; Dayal et al., 2O18). The layer of the index was prepared using ArcGIS 10.3 and utilizing land use layer. At the next step, the maximum and minimum weight were given to the areaes with irrigated cultivation and rangeland or bare lands respectively. Topography index: since the topography has an enormous effect on available water, it could be one of important factors for drought vulnerability. This index are composed of three subindices of slope, aspect and height.As we know, increasing height reduces sensitivity to drought, so the areas with the maximum height assigned less value and the areas with the lowest one assigned more value. The increased slope leads to water being unreachable to the plants rapidly; thus,areas with greater slopes were assgned higher weight value.In the standardized map of direction parameter,the highest weight attached to south, west, east and north slopes, respectively.

Finally,the fuzzy logic was used to combine and overlay the layers of indices and sub-indices. In fuzzy logic,membership of an element in a set is defined with a value in the range of O to 1 (Sui, 1992;Bonham-Carter,1994). Each pixel of indices and sub-indices maps was gotten the value between O and 1,and O indicates a litle impact while 1 suggests the high impact on drought vulnerability.

Fuzzy operation gamma was resulted by multiplying operators of fuzzy algebraic product (Eq. 8).

$$
\mu ( x ) = ( \mathrm { F u z z y ~ a l g e b r i c ~ s u m } ) ^ { \gamma } \times ( \mathrm { F u z z y ~ a l g e b r i c ~ p r o d u c t i o n } ) ^ { 1 - \gamma } \ : ,
$$

where $\mu ( x )$ represents the fuzzy operation gamma equation and y is a number between O and 1.The correct and conscious selection of y creates some values in outputs that shows flexible adaptation between downward tendencies of fuzzy multiplication and upward trends of fuzzy summation (Bonham-Carter,1994). In this study,y was considered as O.9.Dayal et al. (2018) used $\scriptstyle \gamma = 0 . 9$ to assess drought risk in southeastern Australia and achieved acceptable results.The map of drought vulnerability index was obtained by overlaying indices and sub-indices maps.

# 3.3Drought risk

By calculating drought hazard index (DHI) and drought vulnerability index (DVI), the drought risk index (DRI; Eq.9) was calculated (Knutson et al., 1998; Downing et al.,1999; Downing and Bakker, 2000;Wilhite,2000).

$$
{ \mathrm { D R I } } = { \mathrm { D H I } } \times { \mathrm { D V I } } .
$$

Drought risk will increase with DRI. In the end, each map (drought hazard, vulnerability and risk maps） was classified into five classes as very low,low,moderate, high and very high by utilizing natural break in ArcGIS 10.3.

# 4 Results

# 4.1 Drought hazard

The l2-month severe drought percentage probability map (Fig. 3） shows that the northeastern, central,southwestern,and part of northwestern Iran have high drought probability.The coasts near the Strait of Hormuz,southern and the north coast of Iran and around the lake of Urmia have a very low probability of such a severe drought for 12 months.In general, the eastern and southeastern Iran have the highest possbility of severe drought and the northwest, northeast coast of the Persian Gulf to the center of Iran have the minimum probability. It can be concluded that the dispersed parts of northwest to southeast have the highest probability, while the west, east and northeast parts of Iran have the lowest drought probability.

# 4.2 Drought vulnerability

The 12-month DHI spatial distribution in Iran for the period 1981-2016 (Fig.4) shows that the middle belt of Iran from east to west and the southwest have high probability of drought in a time step of 12 months.The coast of the Strait of Hormuz to the center of Fars province and the northwest region has the lowest hazard of drought for the period. Almost half of Iran located in the very high class $( 4 8 . 2 \% )$ and the smallest area are also related to the low class $( 9 . 9 \% )$ . More than $65 \%$ of the country is in high and very high classes.

The weights of each index and sub-index were calculated by AHP to determine the drought vulnerability.Table 3 shows that the climate index has the highest susceptibility to drought.In other words,climate index plays a major role in deciding the vulnerable areas (more than $50 \%$ ). The subindices of precipitation，slope and depletion have the most significant impacts on climate, topography and groundwater resources, respectively.

![](images/916b64691ae7cdbc28548b7337da566ce53b860f7ceef48e5d654452b0e02ab5.jpg)  
Fig.3Drought probability map for 12 months: moderate (a); severe (b);and very severe (c)

![](images/c5a95166c0962b64dd21483a40208e6658068b4d4efc472162dcd026f9a68d52.jpg)  
Fig.4Drought hazard index for time step of 12 months

Table 3Index and sub-index weights determined by the analytic hierarchy process

JOURNALOFARIDLAND   

<html><body><table><tr><td>Index</td><td>Weight</td><td>Sub-index</td><td>Weight</td></tr><tr><td rowspan="3">Climate</td><td rowspan="3">0.516</td><td>Precipitation</td><td>0.693</td></tr><tr><td>Evaporation</td><td>0.088</td></tr><tr><td>Temperature</td><td>0.219</td></tr><tr><td rowspan="2">Waterway density</td><td rowspan="2">0.040</td><td></td><td>-</td></tr><tr><td>Slope</td><td>0.490</td></tr><tr><td rowspan="2">Topography</td><td rowspan="2">0.061</td><td>Aspect</td><td>0.197</td></tr><tr><td>Height</td><td>0.313</td></tr><tr><td>Land use</td><td>0.164</td><td></td><td></td></tr><tr><td rowspan="2">Groundwater resources</td><td rowspan="2">0.219</td><td>Depletion</td><td>0.875</td></tr><tr><td>Depth</td><td>0.125</td></tr></table></body></html>

The fuzzy membership map of waterway density index (Fig.5) shows that some regions in northcentral and eastern Iran are less vulnerable to drought, and southwest and western Iran are more susceptible to drought due to the high density of waterway.

![](images/8ce2c2dc139b99de868789d3737ad80ea7d376da8a59fcc96343a99e4f663aa9.jpg)  
Fig.5Fuzzy membership map of waterway density index

Fuzzy membership maps of land use index (Fig. 6) shows that areas with more vegetation cover have a more significant role in determining vulnerability to drought. The central Iran, especially the Dasht-e Kavir and Kavir-e-Lut, have no critical role concerning land use and vulnerability to drought. The fuzzy membership map of groundwater resources index (Fig.7） shows that each watershed has its requirements depending on the management of groundwater resources in that watershed. Fuzzy membership topographic map index does not show a specific trend,and each pixel has been weighed according to its slope, direction and height (Fig. 8). Checking the fuzzy membership map of climate index shows that areas in the central Iran are more sensitive to drought and are more vulnerable compared to the western, northwestern and northern regions (Fig. 9). After determining fuzzy membership of indices,the map of vulnerability to the drought of Iran was drawn using fuzzy overlap in ArcGIS 1O.3,and was classified into five classes (Fig. 10).

Based on the drought vulnerability map of Iran, the central, northeastern and southeastern Iran are located in very high class,but southeastern,eastern and north-central part are located in very low class.Highlands of Zagros and Alborz mountains are also found in high class and most parts of the northwestern and western Iran as wellas the north coast were in the moderate and low classes.

![](images/0759b1c416159d1f69b91a0ffc177e56453d110556ef5d9b26c7645e8198561a.jpg)  
Fig.6Fuzzy membership map of land use index

![](images/cdd5ab2222c8eafabb8d3ad9d3d65aa1557180b2f7819ba97a3bbb1574525730.jpg)  
Fig.7Fuzzy membership map of groundwater index (a)and its sub-indices: groundwater depletion (b） and groundwater depth (c)

![](images/216fc35bee7fde4706d23d389dfd4c13a29ff87bdfc63ec0ae2673c012ca93f5.jpg)  
Fig.8Fuzzy membership mapof topography index (a) and its sub-indices: aspect (b), height (c),and slope (d)

![](images/8e16984a206d7bf766e5a5a4687a51171424735e3b713390439b5a638fa8afd8.jpg)  
Fig.9Fuzzy membership map of climate index (a) and its sub-indices: precipitation (b),temperature (c） and evaporation (d)

![](images/a7106b96877efec003b18271fe363a465c4e3c837a3dc53679f9209f7f87baad.jpg)  
Fig.10 Drought vulnerability map of Iran

# 4.3 Droughtrisk

Drought risk map of Iran was prepared by multiplying the two sheets of hazard and vulnerability to drought, which was classified into five classes (Fig.11).The results showed that parts of central, northeast, southeast and west parts of Iran are at high risk drought class. North and northwest parts of Iran are at low and very low risk classes.

![](images/558482a25d750ab8b301db5523803f2e2bf9e454495dd1dd9e10715145a8f7ff.jpg)  
Fig.11Drought risk map of Iran

# 5 Discussion

Drought is a complicated phenomenon and comprehensive drought risk management is necessary to reduce its negative effects. In this study,the DRI of Iran was evaluated using DHI and DVI. DHI was estimated from a study of occurrence probability with different drought intensity,which is calculated by SPI. In other words,drought occurrence probability has a major effect on DHI (Wang et al.,2012; Liu et al., 2014; Han et al.,2016). In general, the results show that,by increasing drought intensity,the probability of drought occurrence will decrease.The research results of Li et al. (2018) also proved this. Drought probability maps (Fig.3) indicate that drought occurrence with different intensities is nota function of climate in different regions.Therefore,DHI is not dependent on climate. It is just because drought will occur in different types of climate (Vicente-Serrano et al.,2012; Wang et al.,2O17; Lai et al.,2O19) and the intensity of the drought will not relate to climate. Also,Iran's DHI indicates that an area located in very high risk class might have lower probability of very severe drought risks than an area located in a low risk class. For example, the probability of 12-month very severe drought is low in eastern Iran,but this area is located in the very high drought risk class.This indicates that DHI isa combination of diferent drought intensities and can be used for drought-related planning.

The assessment of drought risk is not possible without determining drought vulnerability (Jain et al.,2015; Ekrami et al.,2016; Thomas et al.,2016).In this study, IBVA method was used to determine drought vulnerability.Five indices and their sub-indices were considered as effective factors on drought vulnerability. There are a lot of methods to determine the weight of indices, but it is notable that determining the precise weight of indices is not easy (Kiem et al.,2O16; Tänago et al.,2016; Muyambo et al.,2017).We used AHP method to determine the weights.Table 3 shows that the climate index has the most significant weight and has the most efficacy on drought vulnerability.Figure 9 also indicates that,if the climate of an area is dry,it would be more vulnerable to drought.

The groundwater resources and land use are also important indices effecting DVI and have direct relations with human activities,which can reflect the economic and social conditions in Iran.The main source of water supply in Iran is groundwater (Jafary and Bradley, 2O18). Groundwater resources has a vital role in drought vulnerability because of the high dependency in the agriculture sector in Iran. Non-systematic and uncontrolled consumption caused to face a crisis of groundwater (Hojjati and Boustani,2O1O; Izady et al.,2O12). Hence, crisis and risk management of groundwater in Iran has a vital role in vulnerability and drought risk. The significant influence of land use on determining DVI demonstrated that time,period and drought intensity have different effects on different land uses (Khosravi et al., 2017).

The map of drought vulnerability (Fig.1O) shows that the regions nearby Urmia Lake located in moderate and high vulnerable classes have to be considered for drought risk management. The effects of drought and human activities,especially agriculture and utilizing groundwater, have caused a decrease in the lake water level (Ghale et al.,2O18).West coasts of the Caspian Sea have less vulnerability against drought in comparison with the east shores because of the humid climate of the west. Based on selected indices,Alborz and Zagros Mountains are located in high drought vulnerable class.

The evaluation results of drought risk in Iran show that risks vary in different areas owing to the different climatic conditions.Most of the areas in semi-arid to humid climate (Fig.1O) are classified as high to very high drought risk.Most of the Iranian population are situated in these areas. Hence, the drought risk management in these areas has special importance.

Having hyper-arid and arid climate (Fig.1) as well as the same groundwater condition,land use index has the decisive role on drought vulnerability and risk in the central,eastern and southern Iran.For instance,most arid areas,like Lut and central desert with high and very high drought probability are located in low drought risk class.From the central part of Iran to the southwest, drought risk gradually decreases,whereas the very high class of drought risk increases from northwest to Iran's central region.Land use is a sign of interaction between human and nature (Moghadasi et al.,2O18).Therefore,human activities excessive exploitation of natural resources have a decisive role in management drought risk in dry and very dry parts of Iran.

# 6 Conclusions

In this research,we tried to provide the Iran's drought hazard, vulnerability and risk maps to determine drought vulnerability areas when severe and very severe drought occurs.The monthly precipitation of 46 synoptic stations with 35-a data were used to calculate the SPI in a 12-month time step. Drought hazard map was provided by the probability map of drought occurrence. Based on the IBVA method,five indices including groundwater resources, waterway density,climate,land use and topography were selected as the most drought-sensitive indices in Iran to prepare the drought vulnerability map. Multiplying drought hazard and vulnerability maps,the drought risk map of Iran was created.The drought hazard map inl2-month time step showed that more than $60 \%$ of Iran have high and very high probability of drought hazard. The eastern and southeastern Iran have the highest possibility of severe drought and the northwest, northeast coast of the Persian Gulf to the central part of Iran have the minimum probability. Based on the drought vulnerability map,the central, northeast and southeast parts of Iran located in very high class are the most sensitive area to drought. This is due to the topography and waterway density. Among the subindices of topography, the weight of slope was greater than the height and aspect. In arid and hyperarid regions of Iran,slope changes are much less than those in the semi-arid and humid areas, so the weight of the topography was low in the arid and hyper-arid regions.The waterway density is low in the arid and arid regions,so this index also has a lower weight than that in the semi-arid and humid areas.

The results of this study illustrate that climate,groundwater resources and land use have important impacts on drought vulnerability in Iran. The groundwater resources and land use as human activities show the human role on drought vulnerability and risk.Due to population density and its pressure on resources, the weights of land use and groundwater resources in semi-arid and humid areas were greater than those in the arid and hyper-arid areas.

Based on the drought hazard and vulnerability maps,the climate index does not have an essential role on drought hazard index,but it is the most crucial factor for determining the drought vulnerability index. The drought risk map showed that the central part, northeast, southeast and west areas of Iran are at high risk drought class. Some reducing-drought risk activities,including providing a drought monitoring and foresight system, developing the jobs not depending on the water, and training society to create a new method, are proposed to improve water consumption efficiency in industrial, agriculture,and domestic sectors.

Drought risk map of Iran ilustrated that in the dry and very dry area,land use has a unique role on drought risk.In other words,in these area, there is a close relationship between land use and drought risk. Increasing drought risk can change land use; and the land use management can effect drought risk and vulnerability.The hyper-arid and arid regions having a high probability of drought are located in very low and low drought risk classes. These areas have less management priority. In general, natural risk management is more important in places where human interests are at stake. In arid and hyper-arid regions,the population density is lower than that in the semi-arid and humid regions,so human resources are less pressured and land use is more stable.The combination of these reasons led to a lower risk of drought in arid and arid regions than in humid and semi-arid regions.

It is recommended that the risk of drought in each land use be separately assessed under different topographic climatic conditions. This provides better risk management in arid and arid regions, and reduces the importance of population centers in determining vulnerable areas. Furthermore, it is suggested that vegetation changes as a new index in assessing drought vulnerability be achieved using satellite imagery.

# Acknowledgements

We are grateful to the Faculty of Natural Resources,University of Tehran.

# References

change,and population growth. Science of the Total Environment, 662: 672-686.   
Araya-MunozD,MetzgerMJ,StuartN,etal.2Ol7.Aspatialfuzzylogicapproachtourban multi-hazard impactassessentin Concepcion, Chile. Science of the Total Environment,576: 508-519.   
Ashok KR,Sasikala C.2O12.Farmers'vulnerability torainfallvariabilityand technologyadoption inrain-fedtankirrigated agriculture.Agricultural Economics Research Review,25(2): 267-278.   
Behrang MM,KhosraviH,Heydari AE,etal.2O19.Linkageofagricultural droughtwithmeteorological droughtindierent climates of Iran. Theoretical and Applied Climatology,138(1-2):1025-1033.   
Beven K,Almeida S,AspinallWP,etal.2O18.Epistemicuncertaintiesandnatural hzardriskassssment-Part1:Areviewof different natural hazard areas.Natural Hazards and Earth System Sciences,18(1O): 2741-2768.   
Birkmann J.2Oo6.Measuring VulnerabilitytoNatural Hazards:Towards DisasterResilientSocieties.Tokyo: UNUPres,1-720.   
Bonham-Carter GF.1994.Geographic Information System for Geoscientists: Modeling with GIS.New York:Elsevier Science Ltd.,291-300.   
ChenF,Jia H,Pan D.2O19.Riskassssmentofmaize drought in China basedonphysical vulerability.JournalofFood Quality, 1-9.   
Dabanli I 2018.Droughthazard,vulnerabilityandrisk assessmentinTurkey.ArabianJournalofGeosciences,11(18):538.   
Dai A.2011.Drought under global warming: areview.Wiley Interdisciplinary Reviews: Climate Change,2(1): 45-65.   
Dayal KS,DeoRC,ApanAA.2018.Spatio-temporal droughtrisk mapping approachanditsapplication inthe drought-prone region of south-east Queensland,Australia.Natural Hazards,93(2): 823-847.   
Dow K.2010.News coverage of drought impacts andvulnerability in theUSCarolinas,1998-207.Natural Hazards,54(2): 497-518.   
Downing TE,Olsthoorn A J,Tol R S J. 1999. Climate,Change and Risk.London: Routledge,1-18.   
Downing TE,Bakker K.20oo.Drought discourse and vulnerability.Drought: A Global Assessment,2: 213-230.   
Dracup JA,LeeKS,PaulsonEG.1980.Onthe statisticalcharacteristicsofdrought events.WaterResourcesResearch6(2): 289-296.   
EakinHA,Bojorquez-TapiaL.2Oo1.Insights intothecompositionofhouseholdvulnerabilityfrommulticriteriadecision analysis. Global Environmental Change,18(1):112-127.   
Easter C.1999.Smallstates development: a commonwealth vulnerability index.The Round Table,8(351): 403-422.   
Ekrami M,MarjAF,Barkhordari J,etal.2O16.Droughtvulnerability mapping using AHPmethod inaridandsemiaridareas:a case study for Taft Township,Yazd Province,Iran.Environmental Earth Sciences,75(l2):1039.   
FusselHM.2Oo7.Vulnerability:A generallyapplicable conceptual framework forclimate changeresearch．Global Environmental Change,17(2): 155-167.   
GhaleYAG,Altunkaynak A,UnalA.2O18.Investigation anthropogenic impacts and climatefactors ondrying upofUrmiaLake using water budget and drought analysis.Water Resources Management,32(1):325-337.   
HanL,Zhang Q,MaP,etal.2O1.The spatialdistributioncharacteristicsofacomprehensivedoughtriskindexinsouthwester China and underlying causes.Theoretical and Applied Climatology,124(3-4): 517-528.   
HaoL,ZhangX,LiuS.2Ol2.RiskaessmenttoChina'sagiculturaldroughtdisaster incountyunit.NaturalHazards,6(2): 785-801.   
He B,LuA,WuJetal.2Ol1.Drought hazardasessmentandspatialcharacteristics analysisin China.JournalofGeogapical Sciences,21(2): 235-249.   
HeB,WuJ,LuA,etall3.QuantitatieasessmentandspatialcharacteristicaalysisoficulturaldroughtiskinCa. Natural Hazards,66(2): 155-166.   
HeydariAE,Behrang MM,KhosraviH.2O18.Probabilityassssmentof vegetationvulnerabilitytodroughtbasedonremote sensing data. Environmental Monitoring and Assessment,19o(12):702.   
HillM J,BraatenR,Veitch S.etal.2Oo.Multi-criteria decisionanalysis inspatial decisionsupport:theASSESSanalytic hierarchy processand theroleofquantitative methodsand spatiallyexplicit analysis.Environmental Modelling& Software, 20(7): 955-976.   
HinkelJ.2011."Indicatorsofvulnerabilityandadaptivecapacity":towardsaclarificationof thesience-policy interface.Global Environmental Change,21(1):198-208.   
Hojati MH,BoustaniF0l0.Anassessmentof groundwatercrisis in Irancase study:Farsprovince.WorldAcademyof Science, Engineering and Technology,70: 476-480. of working group I to the fourth assessment reportofthe intergovernmental panelonclimate change.Cambridge: Cambridge University Press,1-987.   
Izady A,DavaryK,AlzadehA,etal.2O12.Applicationof"panel-data"modeling topredictgroundwaterlevelsintheNeishboor Plain,Iran. Hydrogeology Journal,20(3):435-447.   
JafaryF,Bradley C.2018.Groundwater irigation management andtheexisting challenges fromthe farmers'perspective in central Iran. Land,7(1): 15.   
Jain VK,PandeyRP,JainMK.Ol5.Spati-temporalassssmentofvulnerabilitytodrought.NaturalHazards,76(1):443-469.   
JayanthiH,HusakGJ,FunkC,etal.2O13.Modelingrain-fedmaizevulnerabilitytodroughtsusing thestandardizedprecipiation index fromsatelite estimatedrainfall—Souther Malawicase study.International Journalof DisasterRiskReduction,4:71-81.   
Jonkman SN,van GelderPHAJM,VrijlingJK.2O03.Anoverviewofquantitativerisk measuresforlossoflifeand economic damage. Journal of Hazardous Materials,99(1): 1-30.   
Jordaan A,BahtaYT,Phatudi-Mphahlele B.2019.Ecological vulnerabilityindicators todrought:Caseofcommunal farmers in Eastern Cape,South Africa. Jambá: Journal of Disaster Risk Studies,11(1): 591.   
Karabulut M.2O15.Drought analysis in Antakya-Kahramanmaras Graben,Turkey.Journalof AridLand,7(6):741-754.   
Khoshnodifar Z,Sookhtanlo M,Gholami H.2012.Identificationand measurementof indicators of drought vulnerabilityamong wheat farmers in Mashhad County,Iran.Annals of Biological Research,3(9): 4593-4600.   
Khosravi H,HaydariE,Shekoohizadegan S,etal.2Ol7.Assssmenttheeffectof droughtonvegetationin desertarea using landsat data. The Egyptian Journal of Remote Sensing and Space Science,2O(S1): S3-S12.   
KiemAS,TwomeyC,LockartN,etal.2Ol6.LinksbetweenEastCoastLowsandthespatialandtemporalvariabilityofrainfll along the eastern seaboard of Australia.Journal of Southern Hemisphere Earth Systems Science,66(2):162-176.   
KimH,ParkJooJ,etal.5.Assssmefoughthadlerabilitndsk:Aasesdyfodmistraiect in South Korea. Journal of Hydro-environment Research,9(1): 28-35.   
Knutson C,HayesM,PhilipsT.1998.HowtoReduce DroughtRisk.[2018-09-12].htp://drought.unl.edu/handbook/risk.pdf.   
LaiC,ZhongR,WangZ,etal.20l9.Monitoring hydrologicaldroughtusinglong-termsatelite-basedprecipitationdata.Science of the Total Environment, 649: 1198-1208.   
Lee M,Pham H,Zhang X.1999.Amethodology forprioritysetting withapplication to software development proces.European Journal of Operational Research,118(2): 375-389.   
LeiT,WuJ,LiX,etal.2O16.Anew framework for evaluating theimpactsof droughtonnet primaryproductivityof grasland. Science of the Total Environment,536;161-172   
Leichenko RM,O'brien KL.2O2.The dynamics ofrural vulnerabilityto global change: thecaseof southern Africa.Mitigation and Adaptation Strategies for Global Change,7(1): 1-18.   
LenaDB,VergniL,AntenucciF,etal.2O14.Analysisofdroughtintheregionof Abruzzo(Central Italy)bythe Standardized Precipitation Index. Theoretical and Applied Climatology,115(1-2): 41-52.   
Li C,Wang J,Yin S,etal.2O19.Drought hazardasessment and posibleadaptationoptions for typical steppegrassland in Xilingol League,Inner Mongolia, China. Theoretical and Applied Climatology,136(3-4): 1339-1346.   
Liu Z,ZhangJ,LuoH,etal.014.TemporalandspatialdistributionofmaizedroughtinouthwestofChinabasedongricultural reference index for drought. Transactions of the Chinese Society of Agricultural Enginering,3O(2):105-115.   
Malczewski J.1999.GIS and Multicriteria Decision Analysis.New York: John Wiley & Sons,91-92.   
McKeeTB,Doesken NJ,KleistJ.1993.Therelationshipof drought frequencynd duration to time scales.In: Proceedingsof the $8 ^ { \mathrm { t h } }$ Conference on Applied Climatology. Califonia: American Meteorological Society,179-183.   
Me-BarY,ValdezJrF.2Oo5.Onthevulnerabilityof theancientMaya societytonatural threats.Journalof Archaeological Science,32(6): 813-825.   
Mishra A K, Singh VP.2010.A review of drought concepts.Journal of Hydrology,391(1-2): 202-216.   
MoghadasiN,KarimiradI,Sheikh V.2Ol8.Assessngthe impactoflandusechangesandrangelandsandforestdegradatioon flooding using watershed modeling system.In: Do Carmo JSA.Natural Hazards-Risk Assessment and Vulnerability Reduction. [2019-03-21]. https://www.intechopen.com/books/natural-hazards-risk-assessment-and-vulnerabilityreduction/assessing-the-impact-of-land-use-changes-and-rangelands-and-forest-egradation-on-flooding-using-wat/. doi: 10.5772/intechopen.77041.   
Morid S,MoghaddasiM,ArshadS,etal.2Oo5.DroughtIndexPackage(Version2).Tehran:TarbiatModares University,23.   
Mu Q,ZhaoM,KimballJS,etal.2O13.Aremotelysensed globalterrestrial droughtseverityindex.BulltinofteAmerican Meteorological Society, 94(1): 83-98.   
MuyamboF,JordanAJ,BahtaYT.2O17.Asssing socialvulnerabilitytodroughtin SouthAfrica: Policy implication for drought risk reduction. Jamba: Journal of Disaster Risk Studies,9(1): 1-76.   
Nasrollhi M,Khosravi H,MoghaddamniaA,etal.2O18.Assessmentof drought risk indexusing drought hazardand vulnerability indices.Arabian Journal of Geosciences,11(2O):606.   
NelsonR,KokicP,ElistonL,etal.25.Structuraladjustment:avulnerabilityidexforAustralian broadacreagriculture. Australian Commodities:Forecasts and Issues,12(1):171.   
OrvilleHD.1990.AMSstatementonmeteorologicaldrought.BuletinoftheAmericanMeteorologicalSociety7(7):02-1025   
PopovaZ,IvanovaM,MartinsD,etal.2O14.VulnerabilityofBulgarianagriculturetodroughtandcimatevariabilitywithfocus on rainfed maize systems. Natural Hazards,74(2): 865-886.   
Potop V,Mozny M,SoukupJ.20l2.Droughtevolutionatvarious tme scales inthelowlandregionsandtheirimpactonvegetable crops in the Czech Republic.Agricultural and Forest Meteorology,156:121-133.   
Rossi G,Benedini M,Tsakiris G,etal.1992.Onregional drought estimationandanalysis.Water Resources Management,6(4), 249-277.   
Sadeghravesh MH,Khosravi H,Ghasemian S.2O15.Application offuzzy analytical hierarchy process forassessmentof combating-desertification alternatives in central Iran. Natural Hazards,75(1): 653-667.   
Santos MJJ,VerssimoR,Rodrigues R.2O0l.Overviewof meteorologicaldroughtaalysison WesternEurope.In:Asessment of the Regional Impact of Droughts in Europe.Technical Report 10.Lisbon: Water Institute,78-79.   
Shahid S,Behrawan H.2Oo8.Droughtrisk assessment in the westernpart of Bangladesh.Natural Hazards,46(3):391-413.   
SivakumarMVK，WilhiteDA.2002.Drought preparednessand drought management.[2018-09-12]. https://www.researchgate.net/publication/267362571_Drought_preparedness_and_drought_management.   
Skakun S,KussulN,ShelestovAetal.2O14.loodazardandfloodrisassessmenusingatimeseriesofsateliteges:A case study in Namibia.Risk Analysis,34(8):1521-1537.   
SuiD Z.1992.Afuzzy GIS modeling approach for urban land evaluation.Computers,Environment and Urban Systems,16(2): 101-115.   
TanagoIG,UrquijoJlauut Vetal.2016.Leaingfromexperience:asystematiceviewofessmentsofvuerabilityto drought. Natural Hazards,80(2): 951-973.   
Thomas T,JaisalRK,GalkateR,etal.2O16.Droughtindicators-based integratedasessmentofroughtvulnerabilitycase study of Bundelkhand droughts in central India.Natural Hazards,81(3): 1627-1652.   
ToniniF,Lasinio GJ,Hochmair HH.2012.Mapping return levelsofabsolute NDVIvariations for theassssmentof drought risk in Ethiopia.International Journal of Applied Earth Observation and Geoinformation,18: 564-572.   
Trenberth KE,DaiA,vander SchrierG,etal.(2O14).Global warming andchanges indrought.Nature Climate Change,4(1): 17-22.   
Vicente-Serrano SM,López-MorenoJI,Begueria S,etal.2012.Accurate computationof astreamflowdroughtindex.Journal of Hydrologic Engineering,17(2): 318-332.   
VincentK.2O04.Creatingan indexofsocialvulnerabilitytoclimatechangeinAfrica.TyndallCenterforClimate Change Research WorkingPaper56.[2018-09-12].htps://ww.researchgate.net/publication/228809913_Creating_an_index_of_social vulnerability_to_climate_change_for_Africa.   
Wang M,Wang X,Huang W,etal.2012.Temporaland spatialdistributionofseasonal droughtin Southwestof Chinabasedon relative moisture index.Transactionsof the Chinese SocietyofAgricultural Engineering,28(19):85-92.(in Chinesewith English abstract)   
Wang Z,LiJ,LaiC,etal.017.DoesdroughtinChinashowasignificantdecreasingtrendfrom1961to2Oo9?Scienceof The Total Environment, 579: 314-324.   
Wilhite DA.2Ooo.Droughtasanatural hazard:conceptsand definitions.In: WilhiteDA.Drought:A Global Assessment. London: Routledge,3-18.   
Wu Z,MaoY,iX,etal.6.Exploringsatiotemporalelatiosipsmongeteorological,gcultural,dhological droughts in Southwest China. Stochastic Environmental Research and Risk Assessment,30(3):1033-1044.   
Yu X,He X,Zheng H,etal.2014.Spatialand temporal analysisof droughtriskduringthecrop-growingseasonovernortheast China.Natural Hazards,71(1):275-289.   
Zargar A,Sadiq R,Naser B,et al.2011.Areview of drought indices.Environmental Reviews,19(NA):33-349.   
Zhang Q,ZhangJ.2O16.Drought hazard assessment in typicalcorn cultivated areasof Chinaat presentand potential climate change.Natural Hazards,81(2): 1323-1331.