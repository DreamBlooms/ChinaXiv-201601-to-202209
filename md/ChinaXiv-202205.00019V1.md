# Application of the InVEST model for assessing water yield and its response to precipitation and land use in the Weihe River Basin, China

WU Changxue1, QIU Dexun2.3, GAO Peng1,2.3\*, MU Xingmin1,2.3\*, ZHAO Guangju1,2.3

1 State KeyLaboratoryof Soil Erosionand DrylandFarmingon the Loess Plateau,Instituteof Soiland Water Conservation,   
Northwest A&F University,Yangling 712100,China;   
2State KeyLaboratoryof SoilErosionandDrylandFarmingonthe LoessPlateau,Instituteof Soiland WaterConservation, Chinese Academy of Sciences and Ministry of Water Resources,Yangling 71210o, China;   
3 University of Chinese Academy of Sciences,Beijing 1ooo,China

Abstract: With realizing the importance of ecosystem services to society，the efforts to evaluate the ecosystem services have increased.As the largest tributary of the Yellow River,the Weihe River has been endowed with many ecological service functions.Among which, water yield can be a measure of local availability of water and an index for evaluating the conservation function of the region.This study aimed to explore the temporal and spatial variation of water yield and its influencing factors in the Weihe River Basin (WRB),and provide basis for formulating reasonable water resources utilization schemes. Based on the InVEST (integrated valuation of ecosystem services and tradeoffs) model, this study simulated the water yield in the WRB from 1985 to 2019,and discussed the impacts of climatic factors and land use change on water yield by spatial autocorrelation analysis and scenario analysis methods. The results showed that there was a slight increasing trend in water yield in the WRB over the study period with the increasing rate of $4 . 8 4 ~ \mathrm { m m } / 1 0 \mathrm { a }$ and an average depth of $8 3 . 1 4 ~ \mathrm { m m }$ . The main water-producing areas were concentrated along the mainstream of the Weihe River and in the southern basin. Changes in water yield were comprehensively affected by climate and underlying surface factors.Precipitation was the main factor affecting water yield, which was consistent with water yield in time.And there existed significant spatial agglomeration between water yield and precipitation. Land use had litle impact on the amount of water yield,but had an impact on its spatial distribution.Water yield was higher in areas with wide distribution of construction land and grassland. Water yield of different land use types were different. Unused land showed the largest water yield capacity,whereas grassland and farmland contributed most to the total water yield. The increasing water yield in the basin indicates an enhanced water supply service function of the ecosystem. These results are of great significance to the water resources management of the WRB.

Keywords:water yield; InVEST model; Weihe River Basin; Geoda model; scenario analysis

Citation: WUChangxue,QIU Dexun,GAO Peng,MU Xingmin, ZHAO Guangju.2022.Application of the InVESTmodel forassessing water yieldand itsresponse to precipitationandlanduseinthe WeiheRiver Basin,China.Jourmalof Arid Land,14(4): 426-440.https://doi.org/10.1007/s40333-022-0013-0

# 1Introduction

Ecosystems directly or indirectly provide various services to human beings (Symmank et al., 2020),which were defined as "the benefits that humans derive from nature"(Hassan and Scholes,

2005).As the attribute of the ecosystem and the key component of an ecological process, water yield can produce water-related ecosystem services (Costanza et al.，1998).For example,it regulates surface runoff over the dry and flood seasons,reduces potential drought and flood risks, and ensures drinking water sources (Zhang et al., 2O1O). In summary, water yield is a resource supporting human life and development, such as agriculture,industry, human consumption, hydropower, fisheries,and recreational activities (Natalia et al.,2015).

The growth in the global human population, the improvement in living standards, changes in consumption patterns,and the expansion of irigated agriculture over the last few decades has resulted in a gradual increase in the demand for water resources (Ercin and Hoekstra, 2014; G6mez et al., 2O14; Vorosmarty et al., 2Oo0). Consequently, many countries are facing increasing water scarcity challenges (Qiu, 2010; Liu and Wu, 2012； Mekonnen and Hoekstra, 2016). In China,high demand for food and the imbalance of regional economic development have resulted in increased water resources utilization and uneven distribution (Mekonnen and Hoekstra,2016). Relevant studies have shown a sharp decrease in measured runoff in major river basins of China in recent decades (Xu et al., 2O1O). The changes to water resources of the Yellow River have attracted more attention for the importance of this river in China (Qiang et al.,2Oo9). In the late 1990s,the average runoff entering the Yellow River was only $3 5 . 9 9 \times 1 0 ^ { 8 } \mathrm { ~ m } ^ { 3 }$ ，a decrease of $6 2 . 0 6 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ，compared with the 195Os (Xia et al., 20O7).And this runoff further decreased in the $2 1 ^ { \mathrm { s t } }$ century (Zhao et al.,2018).

The Weihe River is the largest tributary of the Yellow River and provides irrigation water for nearly $1 { \times } 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ of farmland in Guanzhong Plain,supporting nearly $61 \%$ of the population, $56 \%$ of cultivated land,and $81 \%$ of gross domestic product(GDP) in Shaanxi Province,China (Liu and Hu,2Oo8). However, the imbalance between water supply and demand in the Weihe River Basin (WRB） have intensified due to impacts of rapid human development, the construction of water conservancy, soil conservation projects,and other engineering measures (Ma et al., 2008; Cheng et al.,2019; Xu et al., 2O21). Information in the Shannxi Water Resources Bulletin (2019) states that agriculture is the sector consuming the most water in the basin $( 5 5 . 1 3 { \times } 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 } )$ ，which includes forestry,animal husbandry, fishery,and livestock farming,accounting for $60 \%$ of total water consumption; The water consumption of industry and municipal use was $1 4 . 8 5 \times 1 0 ^ { 8 }$ and $1 4 . 2 8 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,accounting for $1 6 . 0 5 \%$ and $1 4 . 1 2 \%$ of total water consumption, respectively. Water consumption in the basin will increase further with the development of economy,imposing more pressure on available water resources (Zhang et al., 2016).

The WRB belongs to a typical transition climate zone in the arid and semi-arid area of northwestern China, and water resources in this area are sensitive to climate change (Chen et al., 2013).Global climate variability over the last few centuries has been characterized by temperature rise and precipitation changes. These changes have had a destructive impact on the natural ecosystem, human economic,and social development (Milliman et al., 2Oo8). Water yield has gradually become an important factor restricting the sustainable development of society. Therefore,an evaluation of water yield of the WRB is of great significance.

Model can be a useful tool for the evaluation of water-related ecosystem service functions and the quantitative estimation of water yield under various conditions. The models include soil and water assessment tool (SWAT) (Baker and Miller, 2O13; Gassman et al.,2O17), social values for ecosystem services (SolVES) (Greg et al., 2012; Sherrouse et al., 2O11),multi-scale integrated models of ecosystem services (MIMES) (Boumans and Costanza, 2Oo8),and integrated valuation of ecosystem services and tradeoffs (InVEST) (Sharp et al.，202O). Among these models, the InVEST model has been the most widely applied due to its less data requirement and ability to visualize simulation results (Huang et al.,2013;Scordo et al.,2018; Cara et al., 2020).The InVEST model integrates a series of ecosystem processes,and can simulate the quality and value of ecosystem services regulated by land use, physical environmental factors,and socio-economic factors (Jiang et al., 2O21). Numerous studies have applied it to various regions of the world and have achieved good results, such as North Korea (Kim and Jung,2O2O),the Wildcat Creek Watershed in Indiana， the Upper Upatoi Creek Watershed in Georgia，the United States (Dennedy-Frank et al.,2016),and some regions of China (Yang et al.,2019; Yin et al.,2020; Li et al., 2021). However, there have been few attempts to apply the InVEST model to the WRB. Those few studies that have applied the InVEST model to the WRB were not able to identify the temporal and spatial variation characteristics in water yield due to their short study periods. Most of these studies also only analyzed the quantitative relationships between water yield and driving factors (Yang et al.,2O19),while not analyzing their spatial correlations.

The present study used the InVEST model to(1） simulate water yield of the WRB from 1980 to 2019,and analyze its spatiotemporal variation; (2) identify the main factors regulating water yield under different climate factors and land use types；and (3） discuss the mechanism of regulating water yield.

# 2 Materials and methods

# 2.1 Study area

The Weihe River originates from Niaoshu Mountain, Weiyuan County, Gansu Province, following which it flows through the Ningxia Hui Autonomous Region and Shaanxi Province from east to west, including 1O regions and 84 counties.The Weihe River merges into the Yellow River eventually at Tongguan County, Shaanxi Province, China. As the largest tributary of the Yellow River, the Weihe River has a total length of $8 1 8 ~ \mathrm { k m }$ ，and drains an area of $1 3 . 5 { \times } 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ .WRB located in the southeastern Loess Plateau，China $( 3 3 ^ { \circ } 4 2 ^ { \prime } - 3 7 ^ { \circ } 2 0 ^ { \prime } \mathrm { N } _ { \mathrm { \scriptscriptstyle } }$ ， $1 0 6 ^ { \circ } 1 8 ^ { \prime }  – 1 1 0 ^ { \circ } 3 7 ^ { \prime } \mathrm { E } )$ .The terrain of the WRB gradually decreases from west to east. And there is an elevation difference of over $3 0 0 0 \mathrm { m }$ a.s.l. (Fig.1).The climate of the WRB is cold and dry in winter,and hot and rainy in summer. The annual average temperature and average annual precipitation are $7 . 8 ^ { \circ } \mathrm { C } - 1 3 . 5 ^ { \circ } \mathrm { C }$ and $5 7 2 \mathrm { m m }$ ,respectively.

![](images/d274cdcc3371e7fe183c36bd9ccc728312e26700a3ac9f02f38707cb1f52c534.jpg)  
Fig.1Elevation,and hydrological and meteorological stations in the Weihe River Basin,China

# 2.2 Data sources

The data required by the model include meteorological, soil and land use/land cover (LULC) data. The raster input data for the model were derived directly or indirectly from these data.Table 1 summarizes the relevant basic data used in the present study.

Table1 Relevant basic data sources and description   

<html><body><table><tr><td>Data</td><td>Data description</td><td>Data source</td></tr><tr><td>Climate data</td><td>Daily precipitation Daily maximum temperature Daily minimum temperature Daily mean temperature</td><td>China Meteorological Science Data Sharing Service Network (http://www.cma.gov.cn/)</td></tr><tr><td>Soil data</td><td>Soil texture (clay,sand,and silt) Soil organic carbon Soil depth</td><td>Harmonized World Soil Database (HWSD)</td></tr><tr><td>Land use/land cover</td><td>Land use/land cover during 1980-2020 at 1 km spatial resolution</td><td>Resource and Environmental Science Data Center, Chinese Academy of Sciences (http://www.resdc.cn)</td></tr><tr><td>Digital elevation model (DEM)</td><td>Elevation of the Weihe River Basin at 30 m spatial resolution</td><td>Geospatial Data Cloud Platform of Chinese Academy of Sciences (https://www.gscloud.cn/)</td></tr><tr><td>Streamflow data</td><td>Measured runoff of Huaxian and Zhuangtou hydrological stations from 1980 to 2019</td><td>YellowRiverHydrological Yearbook</td></tr><tr><td>Runoff data</td><td>Restored runoff of Huaxian and Zhuangtou hydrological stations from 198O to 1984</td><td>Runoff data of the Yellow River Basin</td></tr></table></body></html>

# 2.3 InVESTmodel

# 2.3.1 Introductionof theInVESTmodel

Budyko curve (Budyko,1974),and annual average precipitation $( P )$ were used in the InVEST model to calculate water yield. Water yield simulated by the model represents the water outflow from the landscape,including surface flow, underground flow,and base flow (Sharp et al., 2020). The model assumes that water yield of a pixel reaches the specified outlet through one of several paths mentioned above (Zhang et al.,2OO4; Donohue et al., 2O12). The formula is expressed as:

$$
Y ( x ) = \left( 1 { - } { \frac { \mathrm { A E T } ( x ) } { P ( x ) } } \right) \times P ( x ) ,
$$

where $\mathbf { A E T } ( x )$ is the annual actual evapotranspiration $( \mathrm { m m } )$ ; and $P ( x )$ is the precipitation for a pixel (mm).

For vegetation-covered land, $\frac { \operatorname { A E T } ( x ) } { P ( x ) }$ was calculated (Fu, 1981; Zhang et al., 2004):

$$
{ \frac { \mathrm { A E T } ( x ) } { P ( x ) } } = 1 + { \frac { \mathrm { P E T } ( x ) } { P ( x ) } } - \left[ 1 + \left( { \frac { \mathrm { P E T } ( x ) } { P ( x ) } } \right) ^ { \omega } \right] ^ { 1 / \omega } ,
$$

where $\mathrm { P E T } ( x )$ is the potential evapotranspiration $\mathrm { { ( m m ) } }$ ；and $\omega ( x )$ is a nonphysical parameter characterizing regional climate and soil conditions,ranging from 1.25 to 5.0o (Yang et al., 2008; Donohue et al., 2O12). The minimum value can be selected when the root depth is $0 \mathrm { c m }$ (bare soil), and is calculated as:

$$
\omega \big ( x \big ) = Z \frac { \mathrm { A W C } \big ( x \big ) } { P \big ( x \big ) } + 1 . 2 5 ,
$$

where $Z$ is the local $P$ and other hydrogeological features,with possible values of 1 to 3O; and $\operatorname { A W C } ( x )$ is the plant available water capacity (mm),and is calculated as:

$$
\mathrm { A W C } ( x ) = \operatorname* { m i n } ( { \mathrm { r e s t ~ l a y e r ~ d e p t h , r o o t ~ d e p t h } } ) \times \mathrm { P A W C } ,
$$

where PAWC is the plant available water capacity (Fig. 2a); and rest layer depth is the depth of

root restricted layer, often expressed as the depth at which $9 5 \%$ of root biomass of the plant (Fig.   
2b).

![](images/bfadbda8a5c25e79d2e6cd79d11fe87ec78a45d5b556165d100657305c9ce980.jpg)  
Fig.2Spatial distributions of biophysical characteristics of the Weihe River Basin,China.(a),PAWC, plant available water capacity;(b), soil depth; (c),land use/land cover (LULC) in 2020.

# 2.3.2 Data preparation

The data input to the model included rasterized annual $P$ , average annual $\mathrm { E T _ { 0 } }$ ,LULC, depth of the root restricting layer, PAWC,the layers of watersheds and sub-watersheds,the biophysical table, and an appropriate $Z$ parameter (Sharp et al., 2O2O).All raster data used in the present study were unified into the Krasovsky_194O_Albers coordinate system before input. The sections below describe the processing methods used.

(1) $P$ and $\mathrm { E T _ { 0 } }$

The annual $P$ and $\mathrm { E T _ { 0 } }$ data were obtained by adding the daily precipitation and monthly $\mathrm { E T _ { 0 } }$ data within a year, and Kriging was then used to interpolate the data of 22 meteorological stations around the WRB,which provided a value for each cell in the raster. $\mathrm { E T _ { 0 } }$ was calculated by the modified Hargreaves equation (Droogers and Allen,2002):

$$
\mathrm { E T _ { 0 } } = 0 . 0 0 1 3 \times 0 . 4 0 8 \times \mathrm { R A } \times ( T _ { \mathrm { a v } } + 1 7 ) \times ( \mathrm { T D } - 0 . 0 1 2 3 P ) ^ { 0 . 7 6 } ,
$$

where $T _ { \mathrm { a v } }$ is the average of mean $T _ { \mathrm { m a x } }$ and $T _ { \mathrm { m i n } }$ for every month $( ^ { \circ } \mathrm { C } )$ ，respectively；TD is the difference between mean $T _ { \mathrm { m a x } }$ and $T _ { \mathrm { m i n } }$ for every month $( ^ { \circ } \mathrm { C } )$ ； and RA is the extraterrestrial radiation $( \mathbf { M J } / ( \mathbf { m } ^ { 2 } { \cdot } \mathbf { d } ) )$ .Radiation data were obtained from the United Nations Food and Agriculture Organization (FAO) Irrigation Drainage Paper (Fao et al.,1982).

(2) PAWC

PAWC(Fig. 2a) is the field capacity minus wilting point, ranging from O to 1，which was calculated as (Zhou et al.; 2005):

$$
\mathrm { P A W C } = 5 4 . 5 0 9 - 0 . 1 3 2 \times \mathrm { s a n d } - 0 . 0 0 3 \times ( \mathrm { s a n d } ) ^ { 2 } - 0 . 0 5 5 \times \mathrm { s i l t } - 0 . 0 0 6 \times ( \mathrm { s i l t } ) ^ { 2 } - 0 . 0 0 9 6
$$

$$
0 . 7 3 8 \times \mathrm { c l a y } + 0 . 0 0 7 \times \left( \mathrm { c l a y } \right) ^ { 2 } - 2 . 6 8 8 \times \mathrm { O M } + 0 . 5 0 1 \times \left( \mathrm { O M } \right) ^ { 2 } ,
$$

where sand, silt, clay, and organic matter (OM) were expressed as percentages $( \% )$

(3) LULC

ArcGIS 10.2 was used to reclassify 25 secondary land use types into 6 primary land types (Fig. 2c): farmland, forestland, grassland, water body,construction land,and unused land.

(4)Watershed and sub-watershed

In Arcgis10.2， through the hydrology tool， the WRB was finally divided into 377 sub-watersheds by setting the threshold flow accumulation (TFA) to $4 { \times } 1 0 ^ { 5 } \mathrm { m } ^ { 3 }$

(5)Biophysical table

The biophysical table (Table 2) contains the information for each LULC grid required by the model (Sharp et al.,2O2O).The LULC_veg determines which AET calculation formula to be used. LULC with vegetation cover is assigned as 1，and others are assigned as 0. $K _ { \mathrm { c } }$ is the evapotranspiration coefficient of vegetation, which is based on alfalfa,and used to adjust the $\mathrm { E T _ { 0 } }$ to obtain PET, with a range from 0.O to 1.5. Root depth (Fig. 2b) is the maximum depth that plant root system can extend,which is often expressed as the depth at which $9 5 \%$ of root biomass occurs (Alln et al.,2Oo6). The data in Table 2 were obtained from the relevant literature (Yang et al., 202O),and from the values recommended by the FAO and the InVEST model.

Table 2Biophysical table for the InVEST model   

<html><body><table><tr><td>Code</td><td>Land use type</td><td>LULC_veg</td><td>K</td><td>Root depth (m)</td></tr><tr><td>1</td><td>Farmland</td><td>1</td><td>0.65</td><td>400</td></tr><tr><td>2</td><td>Forestland</td><td>1</td><td>1.00</td><td>1500</td></tr><tr><td>3</td><td>Grassland</td><td>1</td><td>0.65</td><td>500</td></tr><tr><td>4</td><td>Water body</td><td>0</td><td>1.00</td><td>1</td></tr><tr><td>5</td><td>Construction land</td><td>0</td><td>0.30</td><td>1</td></tr><tr><td>6</td><td>Unused land</td><td>0</td><td>0.50</td><td>1</td></tr></table></body></html>

Note:LULC_veg,land use/land cover with vegetation cover; $K _ { \mathrm { c } }$ ,evapotranspiration coefficient.

# 2.3.3 Model calibration

The InVEST model simulates natural runoff of a basin. The simulation accuracy largely depends on parameter $Z$ (Eq.3).The present study validated the parameter $Z$ by comparing the simulated water yield data with natural runoff data at the Huaxian and Zhuangtou hydrological stations in the WRB from 1980 to 1984. The accuracy of simulation was assessed using the correlation coefficient $( R ^ { 2 } )$ ,Nash coefficient (NSE),and relative error $( R _ { \mathrm { e } } )$ (Rientjes et al., 2011). The study set the range of $Z$ value for the study area to $3 . 6 { - } 9 . 0$ ,consistent with those of relevant studies（Wu et al.,2O18;Yue et al.,2021). The model was initiated with a $Z$ value of 3.6,following which $Z$ was gradually increased by O.2. The process was continued until the maximized values of $R ^ { 2 }$ ,NSE, and $R _ { \mathrm { e } }$ were obtained.After nearly a thousand tests,the optimal values of $R _ { \mathrm { e } } , R ^ { 2 }$ ,and NSE of $2 \%$ ， 0.98,and O.63, respectively were obtained at an input $Z$ value of 8.8.

# 2.4Trend analysis

Mann-Kendall (M-K) test is a non-parametric method, which does not need samples to follow a certain distribution,and is not disturbed by a few outliers (Mann,1945; Kendall,1975).The M-K test is often used to identify trends in precipitation and drought under the influence of climate change (Sheng and Paul,2OO4). This study applied M-K test to detect the trends in the water yield, and climate factors over time.It should be noted that the statistic $Z$ value from the M-K test is different to the seasonal parameter $Z$ required as input into the InVEST model.

# 2.5 Correlation analysis

# 2.5.1 Global spatial autocorrelation

The present study used Moran's $I$ to express global spatial autocorrelation. This index was used to analyze the overall correlations between spatial units，and to assess whether a spatial agglomeration existed. The valueof Moran's $I$ ranges from $^ { - 1 }$ to $1 . \ I { > } 0$ indicates that spatial attribute value has a spatial agglomeration effect with the surrounding atribute value,and the closer to 1 the $I$ value, the more significant the spatial agglomeration effect. $I { < } 0$ indicates that the spatial atribute value has a spatial difference effect with the surrounding atribute value. The spatial difference expressed by Moran's $I$ becomes more significant,and the closer the value is to $^ { - 1 }$ ,whereas $\scriptstyle { I = 0 }$ indicates no spatial autocorrelation (Tu and Xia, 2Oo8). The spatial weight matrix was set as a simple binary adjacency matrix.The calculation of Moran's $I$ is as follows(Moran, 1950):

$$
I = \frac { n } { \sum i \sum j W _ { i j } } \frac { \sum i \sum j W _ { i j } \left( x _ { i } - \overline { { x } } \right) \left( x _ { j } - \overline { { x } } \right) } { \sum i \left( x _ { i } - \overline { { x } } \right) ^ { 2 } } ,
$$

where $W _ { i j }$ is the spatial weight matrix of cell $i$ and $j ; x _ { i }$ and $x _ { j }$ are the measured values of cell $x$ and $y$ ，respectively； $\overline { { x } }$ is the average measured value of all cells；and $n$ is the number of all

evaluation units.

# 2.5.2 Bivariate local Moran's I

We used local indicators of spatial association (LISA） method to assess the strength of the correlation between atributes of each spatial unit and the attributes of adjacent units according to local Moran's $I$ (Harries，2006). Here, $I _ { i } { > } 0$ indicates that spatial units are highly correlated, including high-high and low-low types; $I _ { i } { < } 0$ indicates large differences in spatial units, including high-low and low-high types. The formula is as follows (Tepanosyan et al., 2019):

$$
I _ { i } = \frac { n ^ { 2 } } { \sum i \sum j W _ { i j } } \frac { ( x _ { i } - \overline { { x } } ) \sum j W _ { i j } ( x _ { j } - \overline { { x } } ) } { \sum j ( x _ { j } - \overline { { x } } ) ^ { 2 } } .
$$

This method can be used to study the spatial agglomeration effect of meteorological factors and water yield. The high-high and low-low types refer to proportional relationships between meteorological factors and water yield,whereas high-low and low-high types indicate inverse correlations.

# 3 Results

# 3.1Spatiotemporal characteristics of water yield

# 3.1.1 Temporal variation

$P$ ,AET,PET,and simulated water yield in the WRB from 1985 to 2019 were shown in Figure 3. Annual average $P$ over the study period was $5 4 2 . 0 9 \ \mathrm { m m }$ with no significant temporal trend $\scriptstyle ( Z = 1 . 2 8$ 5 $P { > } 0 . 0 5 \$ ).The minimumand maximum $P$ of 364.26 and $7 6 6 . 1 2 \mathrm { m m }$ occurred in 1997 and 2003，respectively. The average PET was $6 9 5 . 5 5 \ \mathrm { m m }$ ，showing no significant trend $\scriptstyle ( Z = 0 . 4 3$ $P { > } 0 . 0 5 )$ . The average AET was $4 5 8 . 8 1 \ \mathrm { m m }$ ，and showed a significant increasing trend ( $\scriptstyle \ Z = 1 . 9 3$ $P { < } 0 . 0 5 )$ ， suggesting that more than $8 0 . 0 0 \%$ of precipitation in the WRB was returned to the atmosphere in the form of evaporation every year. The water yield of the WRB fluctuated, and was correlated with precipitation. The maximum and minimum water yields of 261.62 and 6.08 mm were found in 2OO3 and 1997,respectively. The annual average water yield was $8 3 . 1 4 ~ \mathrm { m m }$ accounting for about $1 5 . 3 3 \%$ of annual precipitation. There was an insignificantly increasing trend in water yield over the entire study period ( $\scriptstyle { Z = 0 . 9 4 }$ $P { > } 0 . 0 5 \rangle$ at arate of $4 . 8 4 ~ \mathrm { m m } / 1 0 ~ \mathrm { a }$ ，with a turning point occurring in 2003.

![](images/881a8309ab657e01a0cb1e14b15e741e93172148e9f1c465a2aee92fe9c52a41.jpg)  
Fig.3Annual precipitation,actual evapotranspiration (AET)，potential evapotranspiration (PET） and water yieldof the Weihe RiverBasin,China during1985-2019

# 3.1.2Spatial variation

As shown in Figure 4,the present study examined the spatial distributions of simulated annual water yield.For example, in 1985,the overall water yield of the basin was high.The main water producing areas were located in the Beiluo River Basin,the north Jinghe River Basin,and the upper reaches of the Weihe River. The annual water yield from 2OO5 to 2O15 decreased from east to west and south to north. The main water-producing areas included the main stream of the Weihe River,and southern part of the Qinling Mountains.The low water yield areas located in the Jinghe River and Beiluo River. The global Moran's $I$ obtained by the Geoda model ranged from 0.38 to O.68, indicating that water yield had a significant spatial agglomeration effect.

![](images/9bd88a04a520f52488f57b2e87e2f62314c71b048863099879a7dade06a8be92.jpg)  
Fig.4Spatial distribution of water yield in the Weihe River Basin,China.(a),1985;(b),20o5;(c),2015;(d), average.

# 3.2 Response of water yield to $P$ and LULC

According to the principle of water yield model, $P$ and AET were the main factors affecting the simulation results. However, AET was largely influenced by LULC.In this study, two scenarios were designed to explore the changes in water yield under different LULC and $P$ conditions (Table 3).Scenario 1 was established to study the change in water yield under different $P$ intensities, in which 1997,2O03,and 2010 represented dry, wet, and average years,respectively. Scenario 2 was established to study the change in water yield under different LULC conditions.

Table3 $P$ andLULC under different scenarios   

<html><body><table><tr><td>Index</td><td colspan="3">Scenario 1</td><td colspan="3">Scenario 2</td></tr><tr><td>P</td><td>1997</td><td>2003</td><td>2007</td><td>1990</td><td>1990</td><td>1990</td></tr><tr><td>LULC</td><td>2020</td><td>2020</td><td>2020</td><td>1990</td><td>2010</td><td>2020</td></tr></table></body></html>

Note: $P$ ,precipitation;LULC, land use/land cover.

# 3.2.1Change in water yield under scenario 1

The results of scenario 1 showed that water yield of the basin has changed significantly under different $P$ conditions (Fig. 5). As $P$ changed from less to more,the water yield of the basin changed accordingly. The maximum water yield during a wet year ( $( 6 7 5 . 4 0 ~ \mathrm { m m } )$ ）exceededthat during a dry year ( $1 3 3 . 5 3 ~ \mathrm { m m } )$ by a factor of 5,whereas it exceeded that during a normal year （20 $( 3 6 5 . 2 0 \mathrm { m m }$ )by a factor of 2. The average water yield of the basin varied greatly with changing $P$ in 1997, 2003,and 2010 with 6.36,264.63,and $7 2 . 9 6 ~ \mathrm { m m }$ ,respectively. The spatial distribution of water yield was consistent with that of $P . \ P$ in the study area was mostly concentrated in the southern and eastern areas, corresponding with the main water-producing areas of the WRB.

![](images/4702d459771bdd786a6f33225c82f30353045f129c9da1b5a7e1118e3331f07b.jpg)  
Fig.5Spatial distributions of annual precipitation $( P , { \mathsf { a } } { - } \mathbf { c } )$ and water yield (d-f) in the Weihe River Basin, China under scenario 1

# 3.2.2Spatial correlation between water yield and $P$

The bivariate Moran's $I$ of $P$ and water yield obtained by the Geoda model ranged from O.30 to 0.80,and showed a positive correlation $( P { > } 0 . 0 5 )$ . The LISA agglomeration maps of $P$ and water yield showed aggregations of mainly high-high and low-low correlation relationships (Fig. 6). Areas with high-high relationships were mainly concentrated in the southern and eastern WRB. Areas with low-low relationships were mainly concentrated in northern Jinghe River and Beiluo River.

![](images/6367fbc24687f3cee529bf056dda50a942080c24e1969808492e2c9504c9e514.jpg)  
Fig.6Spatial distributionof the relationship betweenannual precipitation and water yield in the Weihe River Basin,China in 1997 (a),2003 (b) and 2007 (c)

# 3.2.3Change in water yield under scenario 2

The results of scenario 2 showed that LULC had no significant effect on water yield,but had an impact on the spatial distribution of water yield (Fig.7). There were litle diferences between the maximum and average water yield of the basin in 1990,2010,and 2019 with 468.10,466.88,and $4 7 4 . 5 4 ~ \mathrm { m m }$ ,respectively, and with 140.07, 140.9,and $1 4 2 . 8 5 ~ \mathrm { m m }$ ,respectively. The distribution of land use types has a certain impact on the spatial characteristics of water yield.As shown in Figure 7,areas of higher water yield were correlated with grassland and farmland， such as northern Jinghe River and the upper reaches of the Weihe River.

# 3.2.4Water yield under different LULC

The spatial analysis of ArcGIS1O.2 was used to identify zones of water yield for each land use type under scenario 2. As shown in Figure 8, the fluctuations of water yield were different among different LULC.The water yields of farmland,forestland, grassland, water body,and construction land continued to increase over the study period,whereas those of unused land first increased and then decreased. The maximum and minimum average water yield obtained for unused land and water body were 162.40 and $1 3 1 . 5 8 ~ \mathrm { m m }$ ,respectively.

![](images/0d7ae1d9c28e63fe65a0f3ba0c745de5fa1c754a059d69c6d6a892d145ee5877.jpg)  
Fig.7Spatial distributions ofLULC(landuse/land cover)types (a-c)and wateryield(d-f) in the Weihe River Basin,Chinaunder scenario 2

LULC of the WRB has changed significantly during the study period. As shown in Table 4, the areas of farmland, grassland,and construction land have changed significantly. Farmland area decreased by $4 1 4 6 . 8 3 \ \mathrm { k m } ^ { 2 }$ ，whereas water yield increased by $2 0 . 0 0 \ \mathrm { m m }$ The areas of forestland, grassland and construction land increased by 498.42，1624.8,and $1 7 9 1 . 9 6 \ \mathrm { k m } ^ { 2 }$ ，respectively, whereas water yield increased by11.34,24.31,and $1 2 . 5 3 ~ \mathrm { m m }$ ,respectively. The area of unused land decreased by $9 . 7 1 ~ \mathrm { k m } ^ { 2 }$ ，whereas water yield decreased by $1 7 . 4 4 \ \mathrm { m m }$ . The results indicated that the areas of forestland, grassland, unused land,and water body had positive correlations with water yield,whereas that of farmland had a negative correlation with water yield. However, grassland and farmland were the dominant land use types in the WRB,accounting for more than $80 \%$ of the basin's area in 2O2O. Therefore, water yield was larger in grassland and agricultural land.

Table 4Changes ofLULC(land use/land cover) types of the Weihe River Basin China from 1990 to 2020   

<html><body><table><tr><td>Index</td><td>Farmland (km2)</td><td>Forestland (km2)</td><td>Grassland (km2)</td><td>Construction (km2)</td><td>Unaused (km2)</td><td>Wotyr (km²)</td><td>Total (km2)</td></tr><tr><td>Farmland</td><td>32,855.50</td><td>3589.30</td><td>18,335.17</td><td>3383.78</td><td>68.70</td><td>491.49</td><td>58,723.94</td></tr><tr><td>Forestland</td><td>2933.04</td><td>11,916.83</td><td>6314.91</td><td>177.19</td><td>30.31</td><td>60.66</td><td>21,432.95</td></tr><tr><td>Grassland</td><td>16,536.86</td><td>6219.80</td><td>25,866.74</td><td>703.06</td><td>58.78</td><td>207.40</td><td>49,592.64</td></tr><tr><td>Construction land</td><td>1770.24</td><td>117.94</td><td>448.83</td><td>741.28</td><td>4.94</td><td>43.82</td><td>3127.04</td></tr><tr><td>Unused land</td><td>61.76</td><td>39.77</td><td>60.20</td><td>7.99</td><td>36.59</td><td>3.86</td><td>210.16</td></tr><tr><td>Water body</td><td>419.71</td><td>47.73</td><td>191.59</td><td>85.70</td><td>1.14</td><td>128.26</td><td>874.14</td></tr><tr><td>Total</td><td>54,577.11</td><td>21,931.37</td><td>51,217.44</td><td>5099.00</td><td>200.45</td><td>935.50</td><td>133,960.87</td></tr></table></body></html>

![](images/228915f4adf6ce149c0db386d52b03ffb22e1a9021dc6428f7c25ab1bd7be73f.jpg)  
Fig.8Water yield of different LULC (land use/land cover) types in the Weihe River Basin, China

# 4Discussion

# 4.1 Effects of various factors on water yield

A combined examination of the results of trend and spatial analysis as well as scenario analysis showed that precipitation was the most direct factor affecting regional water yield,which is consistent with the relevant research results (Jiang et al., 2O16; Li et al., 2021). As for AET, it directly participates in the hydrological cycle process (Lewis and Allen,2O17). With emergence of challenges resulting from global climate change，AET has gradually increased in recent decades (Fig. 3).The increase in AET may accelerate the hydrological cycle process,and affect the temporal and spatial distributions of hydrological elements (Gusev et al., 2O19; Cheng and Li, 2020).AET is not only affected by meteorological factors (temperature,wind speed,relative humidity and sunshine hours), but also by the land use conditions (Lang et al., 2017).

There is variation in water yield among different land use types due to differences in soil water content, evapotranspiration capacity， litter water holding capacity, and canopy interception. Unused land had the largest water yield because a greater proportion of precipitation directly penetrated into the ground or formed surface runoff (Lang et al.，2O17). The increase in construction land in the basin has not only increased the demand for water resources,but also changed the underlying surface conditions. Construction practices transform the ground surface into an impermeable layer by removing the vegetation. These conditions lead to a decrease in the evapotranspiration and a higher water yield capacity (Sterling et al., 2O13; Anache et al., 2017). The water yield capacity of water body is weak due to strong evaporation on the water surface. The water yield generated by forestland was relatively lower because of high transpiration and interception of water by the deep root system, litter layer, and dense canopy (Vose et al., 2011; Li et al.,2O21). The effect of grassland and farmland on the redistribution of precipitation was similar to that of forestland. However,the regulation effect of grassland and farmland was relatively weak due to a lower canopy coverage and shallower root depth. In addition, the wide distributions of these two types of lands in the basin has resulted in their dominant contributions to water yield. Previous studies have shown that grassland was the optimal land use pattrns for maintaining hydrology (Li et al., 2O21). Although there have been considerable changes to the land use in the basin during the study period,these changes had no significant efect on water yield.This result can be attributed to the mutual transformation of various land types offsetting any dominant trend in water yield change due to land use changes (Nie et al., 2011).

Land use is the product of human activities,emphasizing human use of natural lands (Lambin et al.,2003; Goldewijk and Ramankutty, 2004; Liu et al., 2013), which can afect processes and components of ecosystems. A series of soil and water conservation projects have been conducted in the basin since the 195Os (Mu et al.,2OO7). These include the construction of terraces and sediment dams,afforestation， plant restoration， pasture improvement，and the returning of farmland to forestland or grassland. These projects have significantly improved the ecological environment and water supply functions of the basin (Wang et al.,2O17; He et al.,2O21). The principle of water balance indicates that the difference between water yield and measured runoff is the water consumed by agricultural, urban and industrial activities,and the changes in reservoir storage (Li et al., 2O2O). The current study calculated the runoff of the WRB as sum of measured runoff of the Huaxian and Zhuangtou hydrological stations (Fig.1） over years.The results showed an upward trend in annual water consumed $\scriptstyle \sum = 1 . 5 6$ ， $P { < } 0 . 0 1$ )，which has increased pressure on water resources.

# 4.2 Limitations of theInVEST model

The InVEST model has been broadly used to evaluate ecosystem service functions,and has achieved good results (Lang et al., 2017; Kim and Jung,202O; Daneshi et al., 2021). However, there are some uncertainties in the model related to model setup and its simplified algorithm (Sharp et al.,2O2O).For example, the model does not consider complex terrain factors,and is not able to rigorously describe the water balance process under complex underlying surface conditions (Jiang et al.,2O16). Topography affects the climate by changing regional hydrothermal conditions. These changes influence the growth and structure of vegetation, the accumulation of litter and the physicochemical properties of soil, which consequently affect water yield (Jia et al., 2014; Maurya et al., 2016).

In addition,the present study obtained root depth and soil data for input into the model from the global soil database. The low spatial resolution of these data affected the simulation accuracy of the model to a certain extent.Moreover, the value of seasonal parameter $Z$ used in the present study was slightly different from that applied in similar watersheds.This indicates that differences in natural conditions will lead to large changes in $Z ,$ ，even between similar basins.Therefore,the value of $Z$ is important to verify before the InVEST model is applied.

# 5 Conclusions

The Weihe River is the largest tributary of the Yellow River,and has strategic significance for the protection of ecological environment and water resources management in Northwest China. The present study applied the InVEST model to quantitatively evaluate the water yield of the WRB from 1985 to 2O19.In addition,the response of water yield to climate factors and land use types was explored.

The average annual water yield of the study area was $8 3 . 1 4 ~ \mathrm { m m }$ ，and yearly water yield over the study period showed a slight increasing trend.The main stem of the Weihe River and southern region were the main water-producing areas. Water yield was comprehensively affected by climate and land use factors. Precipitation was the most direct influencing factor, with the spatial distribution of precipitation corresponding with that of water yield. In contrast,land use did not have a significant effect on water yield. However, there was variation in water yield among different land use types. Unused land had the largest water yield capacity,but farmland and grasland contributed the most to the total water yield of the basin due to their wide distribution. The results of the present study can act as a reference for formulating reasonable and efficient water resources allcation schemes. In addition,the successul application of the InVEST model in the current study can guide its application in related researches under similar natural conditions.

# Acknowledgements

This work was funded by the National Natural Science Foundation of China (U2243211).

# Rererences

Alen R G,PrtritsLD,Raes D,etal.2O6.Cropevapotranspirationguidelinesforomputingcropwaterrequirements.Fao Irrigation & Drainage Paper No.56.FAO,Rome, Italy.   
Anache JAA,Flanagan DC,Srivastava A,etal.2O17.Landuse and climatechange impactsonrunoffandsoil erosioatthe hillslope scale in the Brazilian Cerrado.Science of the Total Environment,622-623:140-151.   
BakerTJ,MillrSN.20l3.Using the soiland waterassessment tool (SWAT)toassesslanduse impacton waterresources in an East African watershed.Journal of Hydrology,486:100-111.   
Boumans R,Costanza R.2O08.The multiscale integrated Earth systems model (MIMES):The dynamics,modeling and valuation of ecosystem services.Issues in Global Water System Research,2(2): 30-41.   
Budyko M I. 1974. Climate and Life. Academic Pres: San Diego, 508   
Cara A,SIhb A,Capm B.2020.Modeling interactions among multiple ecosystem services.Acritical review.Ecological Modelling,429:109103,doi: 10.1016/j.ecolmodel.2020.109103.   
Chen ZS,ChenYN,LiBF2O13.Quantifying theefectsof climate variabilityand humanactivitiesonrunoffforKaidu River Basin in arid region of northwest China.Theoretical and Applied Climatology,111(3-4): 537-545.   
Cheng B,LiHE,Yue SY,etal.2O19.Aconceptual decision-making fortheecological baseflowofrivers consideringthe economic value of ecosystem services of rivers in water shortage area of Northwest China.Journal of Hydrology，578: 124126,doi: 10.1016/j.jhydrol.2019.124126.   
Cheng B,Li H.2O20.Impact of climate change and human activities on economic values produced by ecosystem service functionsof rivers in water shortage area of Northwest China.Environmental ScienceandPolution Research,27(21): 26570-26578.   
CostanzaR,ArgeR,GrootR,etal.1998.The valueof theworld's ecosystem servicesand natural capital.Ecological Economics,25(1): 3-15.   
Daneshi A,BrouwerR,NajafinejdA,etal.2O21.Modellingthe impactsof climateand landusechangeon watersecurityina semi-arid forested watershed using InVEST.Journal of Hydrology,593:125621,doi:10.1016/j.jhydrol.2020.125621.   
Denedy-Frank PJ,Muenich RL, ChaubeyI,et al.2O16.Comparing two tools for ecosystem serviceassssmentsregarding water resources decisions. Journal of Environmental Management,177:331-340.   
Donohue RJ,Roderick ML,McVicarTR.2O12.Roots,storms and soil pores: Incorporating keyecohydrologicalprocesses into Budyko's hydrological model.Journal of Hydrology, 436-437: 35-50.   
DroogersP,AllenR G2Oo2.Estimatingreference evapotranspirationunderinaccuratedataconditions.IrigationandDrainage Systems,16(1): 33-45.   
ErcinAE,HoekstraAY2O14.Waterfooprintsenariosfor05O:Aglobalaalysis.EnvironmentIterational5():782.   
FuBP.1981.Onthecalculationof theevaporation from land surface.Scientia Atmospherica Sinica,5(1):23-31.(in Chinese)   
GassmanPW,Reyes MR,Gree C H,et al.2007.The soiland water assssmenttool: Historical development,applications, and future research directions.Transactions of the Asabe,5O(4):1211-1250.   
Goldewijk KK,RamankuttyN.2Oo4.Landcoverchange overthe lastthreecenturies due to humanactivities:Theavailability of new global data sets. Geojournal, 61(4): 335-344.   
G6mez CM,Pérez-Blanco CD,BatallRJ.2014.Tradeofsinriverrestoration: Flushing flows vs.hydropowergeneration in the Lower Ebro River, Spain. Journal of Hydrology, 518:130-139.   
GusevEM,NasonovaON,KovalevEE,etal.20l9.Impactof possibleclimatechange on extreme annualrunoff fromriver basins located in different regions of the globe.Water Resources,46: S126-S136.   
Harries K.2O06.Extreme spatial variations in crimedensity in Baltimore County,MD.Geoforum,37(3): 404-416.   
Hassan R,Scholes R,Ash N.2Oo5.Ecosystems and humanwell-being:Curent state andtrends.JournalofBacteriology,1(5): 1387-1404.   
HeJ,ShiXY,FuYJ.21.Identifyingvegetatiorestoratioefectivenesanddriingfactorsondierentmicrotopogapic types of hilly Loess Plateau: From the perspectiveof ecological resilience.Journal of Environmental Management,289: 112562,doi: 10.1016/j.jenvman.2021.112562.   
Huang C H, Yang J, Zhang WJ.2013.Development of ecosystem services evaluation models: Research progress.Chinese Journal of Ecology,32(12): 3360-3367.(in Chinese)   
JiaX,FuB,FengX,etal.2O14.ThetradeoffandsyergybetweencosystemservicesintheGrain-for-Greeareasinorthe Shaanxi,China. Ecological Indicators,43(1):103-113.   
Jiang C,LiDQ,WangDW,etal.2016.Quantificationandasessmentof changes inecosystem service intheThree-River Headwaters Region, China as aresult ofclimate variabilityand landcover change.Ecological Indicators,66:199-211.   
Kendall M G.1975.Rank correlation methods.Charles Griffin: London.British Journal of Psychology,25(1):86-91.   
KimS W,JungYY.202.Appicationofthe InVESTmodeltoquantifythe wateryieldof North Koreanforests.Forests,(8): 804.   
Lambin EF,Geist HJ,Lepers E.2Oo3.Dynamicsof land-use and land-coverchange intropical regions.Anual Reviewof Environment and Resources,28(1): 205-241.   
Lang Y,SongW,Zhang Y.2O17.Responsesofthewater-yield ecosystemservicetoclimateand landusechange in Sancha River Basin,China.Physics and Chemistry of the Earth,Parts A/B/C:102-111.   
Lewis C S,Alen LN.20l7.Potentialcropevapotranspiration andsurface evaporation estimates via a gridded weather forcing dataset. Journal of Hydrology, 546: 450-463.   
Li MY,Liang D,XiaJ,etal.2021.Evaluationof waterconservationfunctionofDanjiangRiverBasin inQinling Mountains, China basedonInVESTmodel.JournalofEnvironmental Management,286:112212,doi:10.1016/jjenvman.2021.12212.   
Li X Y,Guo JM, Qi S Z.2021.Forestland landscape change induced spatiotemporal dynamicsof subtropical urban forest ecosystem services value in forestedregionof China: Acaseof Hangzhou City.Environmental Research,193:10618,doi: 10.1016/j.envres.2021.110926.   
Li YY,Yao SB,DengYJ,etal.2O20.Spatio-temporalstudyonsuplyand demand matchingof ecosystem wateryield service-a case study of Wei River Basin.Polish Journal of Environmental Studies,30(2):1677-1693.   
Liu J,Wu Y.2012.Water sustainability for China and beyond. Science,337(6095): 649-650.   
Liu JX,Li ZG Zhang XP,etal.2013.Responsesof vegetationcovertothe Grain forGren program andtheirdrivingforces in the He-Long region of the middle reaches of the Yelow River. Journal of Arid Land,5(4): 511-520.   
Liu Y,Hu AM.2oo8.Studyonspatialdiferentiationcharacteristicsof waterresourcessupply-demandand balancein Weihe Basin. Journal of Arid Land Resources and Environment,22(3):81-85.   
Ma Z M,Kang SZ, ZhangL,et al.2O08.Analysis of impactsof climate variabilityand human activityonstreamflow for a river basin in arid region of northwest China. Journal of Hydrology,352(3-4): 239-249.   
Mann HB.1945.Nonparametric test against trend. Econometrica,13(3): 245-259.   
Maurya S,Srivastava P K,Gupta M,et al.2O16.Integrating soil hydraulic parameter and micro wave precipitation with morphometric analysis for watershed prioritization. Water Resources Management,30(14): 5385-5405.   
Mekonnen MM,Hoekstra AY.20l6.Four bilion people facing severe water scarcity.Science Advances,2(2): e1500323,doi: 10.1126/sciadv.1500323.   
MilimanJD,FarsworthKL,JonesPDetal.8.Cmaticandanthropogenicfactorsectingrverdishargetoelobal ocean,1951-2000.Global and Planetary Change,62(3-4): 187-194.   
Moran PAP.1950. Notes on continuous stochastic phenomena. Biometrika,37(1-2):17-23.   
Mu X M, Zhang L,McVicar TR,et al.2O07.Analysisof the impact of conservation measureson stream flow regime in catchments of the Loess Plateau, China.Hydrological Processes,21(16):2124-2134.   
NataliaP,SilviaF,LauraB,etal.2O15.Geting waterright:Acasestudyinwateryield modellingbasedonprecipitationdata. Science of the Total Environment,537: 225-234.   
Nie W,Yuan Y,Kepner W,etal.2011.Assessng impactsof landuseand landcoverchangeson hydrologyfortheupperSan Pedro watershed. Journal of Hydrology, 407(1-4): 105-114.   
Qiang Z,XuCY,TaoY.2Oo9.Scaling propertiesoftherunoff variations inthearidandsemi-aridregionsofChina:Acase study of the Yellow River basin. Stochastic Environmental Research & Risk Assessment,23(8):1103-1111.   
Qiu J.2010.China faces up to groundwater crisis. Nature,466(7304): 308-308.   
Rientjes T,PereraB,HaileAT,etal.2l1.Regionalisation forlakelevelsimulation-thecaseofLake Tana intheupper Blue Nile,Ethiopia.Hydrology and Earth System Sciences Discussions,15(14): 1167-1183.   
ScordoF,LavenderTM,SeitzC,etal.2O18.Modeling wateryield: Asssng theroleof siteandregio-speciicaribtes in determining model performanceof the InVESTseasonal water yield model. Water,10(11):1496,doi:10.3390/w10111496.   
Sharp R,DouglassJ,Wolny S,etal.2020.InVEST3.9.0 Users Guide.The Natural Capital Project,Stanford University, University of Minnesota,the Nature Conservancy and World Wildlife Fund.   
ShengY,PaulPO04.Acomparisonoftepowerofthtest,Mann-Kendallndbootstraptestsfotrenddetection:Detecting change in hydrological data. International Association of Scientific Hydrology Bulletin, 49(1): 21-37.   
Sherrouse B C, Clement JM,Semmns DJ.2011AGISapplication for assessing,mapping,and quantifying thesocial values of ecosystem services.Applied Geography, 31(2): 748-760.   
Sterling SM,Ducharne A,Polcher J.2013.The impactof global land-coverchangeon theterrestrial watercycle.Nature Climate Change,3(4): 385-390.   
Symmank L,Natho S,Scholz M,et al.2O20.The impactof bioengineeringtechniques forriverbank protectiononecosystem services of riparian zones.Ecological Engineering,158:106040,doi:10.1016/j.ecoleng.2020.106040.   
Tepanosyan G, Sahakyan L, Zhang C S,et al. 2O19. The application of local Moran's $I$ to identify spatial clusters and hot spots of Pb,Mo and Ti in urban soils of Yerevan.Applied Geochemistry,1O4:116-123.   
Tu J,Xia ZG 2Oo8.Examiningspatiallyvarying relationships between land useand waterqualityusing geographically weighted regresson I: Model design and evaluation.Science of the Total Environment,407(1):358-378.   
VorosmartyCJ,GreenP,SalisburyJ,etal.2Ooo.Global waterresources:Vulnerability fromclimatechange and population growth. Science,289(5477): 284-288.   
Vose JM, Sun G,Ford CR,et al. 2O11.Forest ecohydrological research in the $2 1 ^ { \mathrm { s t } }$ century:What are the critical needs? Ecohydrology, 4(2): 146-158.   
Wang B,GaoP,Niu X,etal.2O17.Policy-driven China's Grain to Green program:Implications for ecosystemservices. Ecosystem Services,27: 38-47.   
Wu N,SongXY,Kang WH,etal.20l8.Standardofpaymentforecosystemservicesina watershedbasedon InVETmodel underdifferent standpoints:Acase studyofthe WeiheRiverin Gansu Province.Acta Ecologica Sinica,38(7):2512-2522. (in Chinese)   
Xia J,QiaoYF,Song XF,et al.2Oo7.Analysisabout efectrulesof underlying surfacechange totherelationship between rainfall and runoff in the Chabagou Catchment.Resources Science,29(1):7O-76.(in Chinese)   
Xu K,MillmanJD,Hui X.2010.Temporaltrendof precipitationandrunof inmajor Chineseriverssince1951.Globaland Planetary Change,73(3-4): 219-232.   
XuYX,ZhuGFWanQZ,etal.2O21.Efectofterrceconstructionosoilmoistureinain-fedfarmingareaofLoesslateau. Journal of Hydrology: Regional Studies,37:100889,doi:10.1016/j.ejrh.2021.100889.   
Yang D,Liu W,Tang L,et al.2O19.Estimationof water provision service for monsooncatchmentsof South China: Applicability of the InVEST model.Landscape and Urban Planning,182:133-143.   
Yang HB,YangDW,Lei ZD,etal.2Oo8.Newanalyticalderivationof themeanannual water-energybalanceequation.Water Resources Research,44(3): 893-897.   
YangJ,XieBP,ZhangDG2O2o.Spatio-temporalvariationof wateryieldanditsresponse toprecipitationand landuse change in the Yellow River Basin basedon InVEST model.Chinese Journal of Applied Ecology,31(8):2731-2739.(in Chinese)   
Yang X,Chen R S,Meadows M E,et al.2020. Modellng water yield with the InVEST model in a data scarce region of northwest China.Water Supply,20(3):1035-1045.   
Yin GD,Wang X,ZhangX,etal.2O20.InVESTmodel-basedestimationof wateryieldinNorth Chinaanditssensitivities to climate variables.Water,12(6):1692,doi:10.3390/w12061692.   
YueSY,LiHE,ZhaoL.2O21.Impactof climate and landusechangeson waterscarcityin the Wei RiverBasin.Researchof Soil and Water Conservation,28(5):95-101.(in Chinese)   
Zhang H,HuangQ,Zhang Q,etal.2O16.Changes in thelong-termhydrologicalregimesand theimpactsofhumanactivitie in the main Wei River, China.Hydrological Sciences Journal, 61(6):1054-1068.   
ZhangL,HickelK,Dawes WR,etal.2Oo4.Arational function approach forestimating meanannual evapotranspirationWater Resources Research, 40(2):W02502,doi:10.1029/2003WR002710.   
Zhao Y,HuCHZhang XM,etal2O18.Analysisonrunoffandsedimentregimes anditscauses of the Yellow Riverinrecent 70 years.Transactions of the Chinese Society of Agricultural Engineering,34(21):112-119.(in Chinese)   
Zhou W,Liu GPanJ,etal.2Oo5.DistributionofavailablesoilwatercapacityinChina.Jourmalof GeographicalSciences, 15(1): 3-12.