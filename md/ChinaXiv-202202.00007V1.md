# Spatiotemporal variation of forest land and its driving factors in the agropastoral ecotone of northern China

WANG Shiqing12, TAO Zefu1,2, SUN Piling1,2.3\*, CHEN Sijia1,2, SUN Huiying1,2,LI Nan1,2

1 School of Geographyand Tourism, Qufu Normal University,Rizhao 276826, China;   
2Rizhao KeyLaboratoryof TeritorySpatial Planning and Ecological Construction,Rizhao 276962,China;   
3College ofLand Science and Technology,China Agriculture University,Beijing 10o193,China

Abstract: As an important natural resource, forest land plays a key role in the maintenance of ecological security. However, variations of forest land in the agropastoral ecotone of northern China (AENC) have attracted little atention. Taking the AENC as an example and based on remote-sensing images from 2000, 2010 to 2O20,we explored the spatiotemporal variation of forest land and its driving factors using the land-use transfer matrix,spatial autocorrelation analysis and spatial error model. The results showed that from 2000 to 202O, the total area of forest land in the AENC increased from 75,547.52 to $7 7 , 3 5 9 . 9 6 ~ \mathrm { k m } ^ { 2 }$ and the changes were dominated by the transformations among forest land,grassand and cropland, which occurred mainly in areas with the elevation of $5 0 0 { - } 2 0 0 0 ~ \mathrm { m }$ and slope of $1 5 ^ { \circ } - 2 5 ^ { \circ }$ .There was obvious spatial agglomeration of forest land in the AENC from 2000 to 2020, with hot spots of forest land gathered in the southern marginal areas of the Yanshan Mountains and the low mountainous and hily areas of the Loess Plateau. The sub-hot spots around hot spots moved southward，the sub-cold spots spread to the surrounding areas and the cold spots disappeared.The spatiotemporal variation of forest land resulted from the interactions of natural environment, socioeconomic and policy factors from 20o0 to 2020.The variables of average annual precipitation, slope,terrain relief, ecological conversion program and afforestation policy for barren mountains affected the spatial patern of forest land positively, while those of annual average temperature, slope and road network density influenced it negatively.

Keywords: forest land;spatiotemporal variation;driving factors;spatial error model;agropastoral ecotone; northern China

Citation:WANG Shiqing,TAO Zefu,SUN Piling,CHEN Sijia,SUN Huiying,LI Nan.2022.Spatiotemporal variationof forestlandaditsingfactorsinthegropstoracotofortheia.JoualofAridLand,():-.:o 10.1007/s40333-022-0001-4

# 1 Introduction

In recent years,with the rapid development of urbanization and industrialization in China, the pattern of land use has changed dramaticaly, manifested mainly by rapid expansion of construction land,continuous decrease of natural ecological land and reconstruction of agricultural production land (Liu et al.，2O14).Regional land-use changes and their driving factors have always been important research topics in land science and global climate change (Liu et al.,2O18). In particular, comprehensive studies of how human activities and natural environment affect land-use change constitute an important part of the research into the driving mechanisms of land-use changes (Chen and Yang,2Oo1). The spatiotemporal variation and its driving factors for land-use types in specific areas have become important ecological issues (Peng et al.， 2O17). As an important ecological defense line,ecological environment of the AENC located in an arid and semi-arid transition area is very sensitive and fragile because of frequent human activities, therefore,the AENC has become a research hot spot for ecological environmental response to land-use changes (Liu et al., 2021).

Forest land is an important natural resource and plays a key role in regional development and ecological security maintenance (Godlee et al.,2O21). Therefore,the dynamic monitoring of forest land resource and driving factors has attracted widespread attention (Njoghomi et al.,2O21; Shriver et al.,2021).With the implementation of ecological projects and other socioeconomic measures, land-use type has undergone huge changes in the AENC,but the effects of these projects on the spatial distribution of forest land and the interaction between socioeconomic development and natural environment are difficult to measure (Wang et al.,2Oo7). Ecological projects such as the Three-North Shelter Forest Program, the Grain for Green and the Taihang Mountain Greening Project have had significant impacts on the evolution of forest land (Du et al., 2O16),leading directly to the conversion of forest land on a large scale (Zhou et al.,2O12).Therefore,it is very important to pay attention to the factors driving the spatiotemporal variation of forest land in sensitive and fragile areas with extremely important ecological environments.

Currently, research on forest land is mainly focused on the dynamic monitoring (Xie and Gong, 2019),saptiotemporal pattern and driving factors (Zhang et al.， 2O2O), landscape patern and gradient effect (Clarke，2Oo3)， scenario simulation and prediction (Yang and Fu，2018), transformation and circulation (Gong et al.,2O19; Yu et al, 2O2O),relationship between change of forest land and ecological environment (Garner et al., 2015; Zhu, 2O15),changes of ecosystem service values (Cao et al.,20O8),and management and protection (Li and Zhang,2O2O; Wei, 2020). With progress in remote sensing, geographic information, big-data mining technology, the methods of landscape pattern metrics，spatial autocorrelation analysis,probit regression models,logistic regression models and Celular Automata-Markov Chain model have been widely used in forest land research (Zhou et al.,2018; Shao et al.,2019; Gou et al.,2021; Li et al.,2021; Xi et al., 2021), but studies of the spatiotemporal variation of forest land and its driving factors in the AENC with spatial regression models are currently lacking.

In recent years,with the rapid development of economy in the AENC,ecological problems such as vegetation destruction,land degradation and soil erosion have been increasing，and conflicts between ecological protection and economic development are becoming serious. Therefore, for the sake of ecological protection and sustainable development, there is an urgent need to clarify the trend of forest land changes in the AENC. The aims of the present study are to (1） analyze the transition of forest land in the AENC from 2000 to 2O2O; (2) reveal the spatiotemporal variation of forest land; and (3) explore the factors driving this spatiotemporal variation.

# 2Materials and methods

# 2.1 Study area

The AENC includes 226 counties (banners, cities and districts) in the autonomous regions of Inner Mongolia and Ningxia Hui and the provinces of Jilin,Liaoning, Hebei, Shanxi, Shaanxi, Gansu and Qinghai $( 3 4 ^ { \circ } 4 3 ^ { \prime } 3 1 ^ { \prime } \mathrm { N } ^ { - } 4 6 ^ { \circ } 5 7 ^ { \prime } 4 6 ^ { \prime } \mathrm { N }$ $1 0 0 ^ { \circ } 5 7 ^ { \prime } 1 1 ^ { \prime } \mathrm { E } ^ { - } 1 2 5 ^ { \circ } 3 4 ^ { \prime } 1 1 ^ { \prime } \mathrm { E }$ ；Fig.1). The total area of the AENC is $6 9 9 , 0 7 8 . 7 8 \mathrm { k m } ^ { 2 }$ and its elevation ranges from $1 6 0 \mathrm { ~ m ~ }$ below sea level to $4 9 7 3 \mathrm { ~ m ~ }$ above sea level. This area is dominated by plateaus,mountains and hills. The AENC has a temperate arid and semi-arid climate, experiencing the low temperature and drought. The annual average temperature is $0 ^ { \circ } \mathrm { C } \mathrm { - } 8 ^ { \circ } \mathrm { C }$ ,the average annual precipitation is $3 0 0 { \ - } 4 5 0 \ \mathrm { m m }$ and variation of annual precipitation is high, being $1 5 \% - 3 0 \%$ (Liu and Gao, 2OO8). With decreasing precipitation from east to west, the vegetation transforms gradually from forest steppe to desert steppe.

# 2.2 Data sources and processing

The data used in this study came from remote-sensing images comprising Landsat images from 2000 to 2O1O and Operational Land Image in 2020. These images were obtained from China's Geospatial Data Cloud (http://www.gscloud.cn/). Preprocessing of these Landsat images included an atmospheric correction in the Environment for Visualizing Images (ENVI) 5.1 and geometric rectification. In total,281 sample points were collected and classified in August 2O2O with the Google Earth and spot surveying. Approximately $3 5 \%$ of the sample points were selected randomly for accuracy assessment.The methods of neural-net estimation and man-machine interactive interpretation were used to interpret and clasify these images.The results were then tested and verified, with overall accuracies of $8 7 . 6 8 \%$ ， $8 9 . 7 2 \%$ and $8 8 . 5 9 \%$ for the images in 2000,2010 and 2020,respectively,and Kappa coefficients of 0.85,0.87 and 0.86,respectively, indicating that the interpretation results could meet the needs of this study.Land-use types were divided into six categories: cropland,forest land, grassand, water body,construction land and unused land (Wang and Liu,2OO9). The topographical data were derived from a digital elevation model (DEM) with a resolution of $3 0 ~ \mathrm { m } { \times } 3 0 ~ \mathrm { m }$ and downloaded from the China Meteorological Science Data Sharing Service Network (http://cdc.cma.gov.cn/). The slope,aspect and terrain relief were extracted from the DEM.The meteorological data downloaded from the same datasets were interpolated spatially by the inverse distance weighting method.The road traffic data (including railways and highways) came from the electronic trafic map (2OoO and 2O2O),and the social and economic statistics such as population and regional gross domestic product came mainly from the statistical yearbooks of these provinces and regions of the AENC.

![](images/2ef94f04e148cb324b11e012a2e8eafe87fb370d9a7099d9619e2561a3cf528f.jpg)  
Fig.1Location of study area and sample points

We processed the aforementioned data using the ArcGIS 1O.4 software,and we used a $1 0 \mathrm { k m } \times 1 0 \mathrm { k m }$ grid as the data carrier and basic analysis unit. Format conversion, mask clipping and vector data rasterization were processed to unify all the spatial data into the Albers projection system. In the same grid，spatial statistics for forest land，meteorology，topography， socioeconomic data and other multisource data were processed,and spatial data for the driving factors of forest land were obtained.

# 2.3 Methods

# 2.3.1Land-use transfer matrix

Land-use transfer matrix was used to characterize the inter-conversion relationship between forest land and other land types in the AENC from 2000 to 2020.It is expressed as follows (Liu et al., 2021).

$$
S _ { i j } = { \left[ \begin{array} { l l l l } { S _ { 1 1 } } & { S _ { 1 2 } } & { \cdots } & { S _ { \mathrm { 1 n } } } \\ { S _ { 2 1 } } & { S _ { 2 2 } } & { \cdots } & { S _ { 2 n } } \\ { \cdots } & { \cdots } & { \cdots } & { \cdots } \\ { S _ { n 1 } } & { S _ { n 2 } } & { \cdots } & { S _ { n n } } \end{array} \right] } ,
$$

where $S _ { i j }$ is the area converted from land-use type $i$ to type $j ( \mathrm { k m } ^ { 2 } )$ ; and $n$ is the number of land-use types.

# 2.3.2Spatial autocorrelation analysis

The method of spatial autocorrelation analysis is effective for revealing whether the spatial distribution of a spatial element or a property value is related to the adjacent region and the degree of correlation (Qing et al.，2O2O). In the present study, global spatial autocorrelation was used to analyze the spatial distribution characteristics of forest land. Spatial hotspot analysis (Getis-Ord ${ G _ { i } } ^ { * } )$ was used to identify the spatial characteristics of forest land clusters in the AENC (Ren et al., 2016). The equations were as follows:

$$
I = \frac { \sum _ { i = 1 } ^ { n } \sum _ { j \neq i } ^ { n } W _ { i j } ( x _ { i } - \overline { { x } } ) ( x _ { j } - \overline { { x } } ) } { s ^ { 2 } \sum _ { i = 1 } ^ { n } \sum _ { j \neq i } ^ { n } W _ { i j } } ,
$$

$$
G _ { i } ^ { * } = \frac { \sum _ { j = 1 } ^ { n } W i j ( d ) X _ { j } } { \sum _ { j = 1 } ^ { n } X _ { j } } ,
$$

$$
Z ( G _ { i } ^ { * } ) = { \frac { G _ { i } ^ { * } - E ( G _ { i } ^ { * } ) } { \sqrt { \operatorname { v a r } ( G _ { i } ^ { * } ) } } } ,
$$

where $I$ is the global Moran's $I ; x _ { i }$ and $x _ { j }$ are the forest land areas of regions $i$ and $j$ ，respectively $( \mathrm { k m } ^ { 2 } )$ ; $\overline { { x } }$ is the mean forest land area $( \mathrm { k m } ^ { 2 } )$ ·， $W _ { i j }$ is the spatial weight matrix $( i \neq j ) ; { G _ { i } } ^ { * }$ is the statistic of region $i ;$ $Z ( { G _ { i } } ^ { * } )$ is the standardized value of $\boldsymbol { G _ { i } } ^ { * }$ , which is used to execute a $Z$ statistic test for forest land in the AENC; $E ( \boldsymbol { G _ { i } } ^ { * } )$ is the average of $\boldsymbol { G _ { i } } ^ { * }$ ; and $\mathbf { v a r } ( \boldsymbol { G } _ { i } ^ { * } )$ is the coefficient of variation of ${ G _ { i } } ^ { * }$ . The global Moran's $I$ ranges from $^ { - 1 }$ to 1. If $I { > } 0$ ，the forest land is positively correlated spatially,and the high or low values of forest land are distributed centrally；if $I { < } 0$ ，there isa negative correlation, which indicates that forest land from one region is different from those of the surrounding regions; if $\scriptstyle { I = 0 }$ ,forest land occurs randomly.If $Z ( G _ { i } ^ { \overline { { * } } } )$ passes the statistical test and is greater than O, then region $i$ is surrounded by the high values of forest land area and a cluster of high values (a hot spot) forms; if $Z ( { G _ { i } } ^ { * } )$ passes the statistical test and is less than O, then region $i$ is surrounded by the low values of forest land area and a cluster of low values (a cold spot) forms.

# 2.3.3 Explanatory variables

The spatiotemporal variation of forest land is driven by natural environmental, socioeconomic and regional policy factors (Dwomoh et al.，2021; Hou_et al.，2021; Luo et al., 2021). Following previous studies (Bochet et al.,2021; Li et al.,2021; Rohde et al.,2021), we selected explanatory variables from those three aspects,i.e., natural environment, socioeconomic and regional policy factors (Table 1).Natural environment factors play a key role in forest land changes,and six explanatory variables including average annual precipitation, annual average temperature, elevation, slope,aspect and terrain relief were selected to characterize the natural environment features in the AENC. Three explanatory variables of economic density，population density and road network density were selected to reflect the socioeconomic conditions in the AENC.The regional policy is the measure of afforestation for barren mountains.

# 2.3.4Spatial regression model

Generally,the relationship between observed variables and potential driving factors is explored using multiple linear regression (Yu et al., 2Ol7). However,as a geographic phenomenon, forest land changes are correlated spatially, therefore it was necessary to use a spatial regresson model that considers the spatial correlation among regions to identify the driving factors of forest land changes. The spatial regression model includes a spatial lag model (SLM) and a spatial error model (SEM) (Liu et al.,2O12; Sun et al.,2O17) that were used to analyze the relationship between the spatiotemporal variation of forest land and the explanatory variables. Using the ArcGIS and GeoDa software, we screened the appropriate spatial measurement model by using the Lagrange multiplier (LM) test and by checking the spatial autocorrelation of forest land distribution.

The SLMis expressed as follows (Sun etal.,2017):

$$
Y = \rho W Y + \beta X + \varepsilon ,
$$

Table1Explanatory variables relevant to spatiotemporal variation of forest land   

<html><body><table><tr><td colspan="2">Driving factor</td><td>Explanatory variable</td><td>Interpretation</td></tr><tr><td rowspan="4">Natural</td><td rowspan="2">Climate condition</td><td>Average annual precipitation Annual average</td><td>Average annual precipitation of each unit was obtained by spatial interpolation with ArcGIS software (mm) Annual average temperature of each unit was obtained by spatial</td></tr><tr><td>temperature</td><td>interpolationwith ArcGIS software(C) Digital elevation model (DEM) of each unit was obtained by</td></tr><tr><td rowspan="4">Topographic condition</td><td>Elevation</td><td>neighbor analysis with ArcGIS software (m) Annual average temperature of each unit was obtained by spatial</td></tr><tr><td>Slope</td><td>interpolation with ArcGIS software (C)</td></tr><tr><td>Aspect</td><td>AitArGsotedadtaiedbyeali Terrain relief was extracted from DEM and obtained by neighbor</td></tr><tr><td>Terrain relief</td><td>analysis with ArcGIS software (m)</td></tr><tr><td rowspan="2" colspan="2">Socioeconomic factor</td><td>Economic density</td><td>GrY dmesticpoduct was dided bythe talregionalarea (x10</td></tr><tr><td>Population density</td><td>Total population was divided bythetotal regionalarea (people/</td></tr><tr><td rowspan="3" colspan="2">Regional policy factor</td><td>Road network density Ecological conversion</td><td>Road mileage was divided by the total regional area (km/km²) If the ecological conversion area in one unit was O,then the value of</td></tr><tr><td>program</td><td>ecological conversion program was O;if it was greater than O,then the value was 1.</td></tr><tr><td>Afforestation policy for barren mountains</td><td>IfthesaffonpoticyfoiouniisOtenitevaef than O, then the value was 1.</td></tr></table></body></html>

where $Y$ is the forest land area of spatial regional unit $( \mathrm { k m } ^ { 2 } )$ ， $W$ and $\rho$ are the spatial adjacency weight and its estimated coefficient,respectively; $\beta$ is the coefficient of explanatory variable; $X$ is the explanatory variable matrix; and $\varepsilon$ is a random error. The SEM is expressed as follows ( $\mathrm { Y u }$ et al., 2017):

$$
Y = \beta X + \lambda W \varepsilon + \mu ,
$$

where $\lambda$ is the coefficient of regression; and $\mu$ is an independent random error.

# 3 Results

# 3.1Transition of forest land in the AENC

From 2000 to 2020, the total area of forest land increased from 75,547.52 to $7 7 , 3 5 9 . 9 6 \mathrm { k m } ^ { 2 }$ with a $2 . 4 0 \%$ increase rate for each year. The newly increased forest land was scattered mainly in the mountainous areas of northern Hebei Province,and low mountainous and hilly areas of the Loess Plateau (Fig. 2).

As shown in Figure 3, the total area of forest land decreased by $1 1 1 . 5 5 \mathrm { k m } ^ { 2 }$ in the AENC from 2000 to 2O10. On the one hand,the decreased forest land was converted mainly to grassland and cropland. The areas of this conversion for grassland and cropland were 9142.64 and $5 1 7 . 9 9 ~ \mathrm { k m } ^ { 2 }$ accounting for $9 4 . 1 9 \%$ and $5 . 3 4 \%$ of the total area changed, respectively. The conversion of forest land to grassand occurred mainly in the mountainous areas of northern Hebei Province and Inner Mongolia Autonomous Region. Furthermore, the conversion of forest land to cropland was distributed mainly in river valleys and intermountain basins in the counties of Hunyuan,Lingqiu and Guangling with a low elevation and flat terrain. On the other hand, increased forest land was derived mainly from grassland and cropland. And the areas of the conversion were 8613.O2 and $8 5 2 . 3 7 ~ \mathrm { k m } ^ { 2 }$ for grassland and cropland,accounting for $8 9 . 7 6 \%$ and $8 . 7 8 \%$ of the total area changed，respectively. The conversion of grassland to forest land occurred mainly in the mountainous areas of northern Hebei Province, while the conversion of cropland to forest land was scatered in areas of high elevation and complex terrin, including the counties of Gujiao,Jingle, Chongli and Zhangbei. In recent years，with the implementation of ecological projects，the expansion of forest land was derived mainly from grassland and cropland from 2O1O to 2020, which accounted for 1923.99 and $2 9 9 1 . 2 3 \mathrm { k m } ^ { 2 }$ , respectively. Cropland was converted to forest land because of the construction of farmland shelterbelt,and the increase of forest land improved the

# ecological environment further.

![](images/6b89a6da9ab90836f6d7d2101b7e19f202284b7d77cc1452250913cc724b5e9e.jpg)  
Fig.2Spatiotemporal variationof forest land in the agropastoral ecotone of northern China (AENC)in 2000 (a), 2010 (b) and 2020 (c)   
Fig.3Conversation between forest land and other land types in the AENC from 2000 to 2020. (a),2000-2010; (b),2010-2020.

100°E 108E 116E 124°E 100°E 108E 116E 124°E (a) 2000-2010 N84 (b)2010-2020 N.84   
454 Legend Conty line 455   
2 Frest land→Cropsland Forestland→Waterbody Forest land→Construction land 104 N N54   
N6 GraslandFrose stadd IForpstldUnsused land Construction land →Forest land 304 3660 N6 N N6   
N9 Unused land→Forest land 0 300 km N90 N90 0 300km N9 100E 108°E 116E 124E 100°E 108E 116E 124°E

The topographical gradient effect of forest land was obvious in the AENC (Fig. 4). Forest land changes were distributed mainly in areas with elevations of $5 0 0 { - } 2 0 0 0 \ \mathrm { m }$ and slopes of $1 5 ^ { \circ } - 2 5 ^ { \circ }$ With the implementation of ecological projects such as the Three-North Shelter Forest Program, the Grain for Green and the Taihang Mountain Greening Project, forest land expanded into regions with a higher topographic gradient in the AENC, which occupied a dominant position at elevations exceeding $2 0 0 0 \mathrm { m }$ and slopes exceeding $1 5 ^ { \circ }$ ：

# 3.2Spatiotemporal distribution of forest land in the AENC

# 3.2.1 Distribution trendofforestland

The geostatistical analysis module of ArcGIS 1O.4 software was used to analyze the distribution trend of forest land in the AENC from 2000,2010 to 202O (Fig.5).The change in forest land in the

AENC was very obvious.The overall spatial pattern of forest land showed an inverted U-shaped differentiation trend in the east-west direction,being high in the north and low in the south from 2000 to 2020.

100°E 108E 116E 124E 100E 108E 116E 124E （a)DEM N84 (b) Slope N84   
254 Legend 4544   
2 N6 Forest land→Crasland Forestland→Waterbody 国 aterbndrerestad Consrstand r □County line 200-500m 1100000 N4 2 2 N6 Legend 0°-5° 50-1 15°-25° >25° N4 N N60 N69   
N90 N9 0 300km N9 0 300km N9 L 100E 108E 116E 124E 100°E 108E 116E 124E

![](images/8d1288c171e11c07fc77aa40d56e40c816f81c440801ee52c1301b30a4a9a065.jpg)  
Fig.4Vertical distribution of forest land in the AENC in diffrent elevations (a)and slopes (b).DEM,digital elevation model.   
Fig.5Distribution trend of forest land in the AENC in 2000 (a),2010(b) and 202O(c).N,north; E,east.

# 3.2.2Spatiotemporal variation of forest land

The global Moran's $I$ of forest land in the AENC from 20OO to 202O was calculated using ArcGIS 10.4 (Table 2) and ranged from 0.323 to 0.328 from 2000 to 2020. The $Z ( { G _ { i } } ^ { * } )$ values were positive and all tested significantly at the O.O1 level, which indicated a positive spatial autocorrelation of forest land. This result showed that areas with similar levels of forest land tended to be spatial agglomerated.Furthermore, the global Moran's $I$ maintained a downward trend in its fluctuations, indicating that the degree of agglomeration continued to weaken after a minor intensification in the AENC from 2000 to 2020.

Table 2 Global Moran's $I$ of forestland in the AENC from 200O to 2020   

<html><body><table><tr><td>Year</td><td>Global Moran's I</td><td>E(Gi)</td><td>Z(Gi)</td><td>P</td></tr><tr><td>2000</td><td>0.328</td><td>-0.004</td><td>8.952</td><td>0.000</td></tr><tr><td>2010</td><td>0.333</td><td>-0.004</td><td>9.090</td><td>0.000</td></tr><tr><td>2020</td><td>0.323</td><td>-0.004</td><td>8.818</td><td>0.000</td></tr></table></body></html>

Note: ${ G _ { i } } ^ { * }$ is the statistic of region i; $Z ( { G _ { i } } ^ { * } )$ is the standardized value of ${ G _ { i } } ^ { * }$ ,which is used to execute a $Z$ statistic test for forest land in the AENC; $E ( \boldsymbol { G _ { i } } ^ { * } )$ is the average of ${ G _ { i } } ^ { * }$ ：

To effectively analyze the spatiotemporal variation of forest land in the AENC,we divided the values of Getis-Ord $\dot { \boldsymbol { G } } _ { i } ^ { * }$ from high to low into five types of hot spot, sub-hot spot,sub-cold spot, cold spot and non-significant area using the Jenks natural-breaks method (Cao et al., 2O14). The spatial pattern of forest land showed an obvious spatial difference in the AENC from 2Oo0 to 2020 (Fig. 6).

The spatial pattern of hot spots evolved significantly in the AENC, which was manifested mainly as a reduction trend from 2OOO to 2O20.Forest land was distributed mainly in the mountainous areas with higher elevations and slopes.From 2O0O to 2020,the number of counties (districts) in hot spots decreased constantly, becoming gathered in the southern marginal area. Two clusters of high forest land area formed in 23 counties (districts) located in the Yanshan Mountains and the low mountainous and hilly areas of the Loess Plateau.During this time，the spatial pattern evolution of sub-hot spots moved southward, which occurred mainly in regions around the hot spots.With the implementation of ecological projects,in 2O2O,the sub-hot spots covered 13 counties (districts) located in the Yanshan Mountains and the Loess Plateau, where the ecological environment is very sensitive and fragile. Meanwhile, the sub-cold spots spread to the surrounding areas,and the number of counties (districts) with sub-cold spots increased from 43 to 47 from 2000 to 2020.These counties (districts） were distributed mainly in areas with a low elevation and flat terrain,such as the valleys of Huangshui, the Yellow River and the Daqing River,located in the provinces of Qinghai, Gansu and Iner Mongolia Autonomous Region, where two clusters of low forest land area (sub-cold spots） formed.Moreover，the spatial pattern of cold spots changed significantly. In 2OOo,there was a cluster of low forest land area (cold spot) in the region between the provinces of Qinghai and Gansu, including the county of Minhe in Qinghai and the district of Qilihe in Gansu; however,this cold spot disappeared as Minhe and Qilihe fellinto sub-cold spots in 2020 (Fig. 6c).

![](images/a6d381112c31a6bd575b23885a8a828e9b88fc7b1cbbb0b8980f02e51ba36244.jpg)  
Fig.6Spatiotemporal variation of forest land in the AENC in 200O (a),2010 (b) and 2020 (c)

# 3.3Driving factors of spatiotemporal variation of forest land

In this study， the LM test was used to select the spatial measurement model. Conventional least-squares analysis showed that the results of SEM and robust LM for the years 2OoO and 2020 both passed the test at the O.O1 level. This result indicated that SEM was suitable for identifying the factors driving the spatiotemporal variation of forest land in the AENC.And the spatial variation was influenced by natural environment, socioeconomic and regional policy factors (Table 3).

# 3.3.1 Natural environment factors

As shown in Table 3, the significant variables are average annual precipitation, annual average temperature, slope,aspect and terrain relief.This result indicates that climate and topographic conditions basically determined the spatial patern of forest land in the AENC.Precipitation and temperature are important natural conditions for land use,determining the level of climate-induced potential productivity in a region. The spatiotemporal variation of forest land was affected significantly by precipitation and temperature in the AENC from 2OOO to 2O20. There was a positive correlation between the average annual precipitation and the distribution of forest land, which passed the significance test at the O.O1 level in 2OOO and 2O2O,while it was negatively correlated with annual average temperature.The AENC is located in arid and semi-arid areas, where the distribution of vegetation cover is consistent with the precipitation.Therefore,the higher the precipitation is,the better the forest land covers.In mountainous areas,the sunny slope and flat areas are often suitable for agricultural production, so cropland and garden land usually occupy the dominant position there,while forest land is scarce.The regional differentiation of land resources is restricted by topographical conditions, which can affect the redistribution of heat and water. The distribution of forest land was correlated positively with slope and terrain relief but negatively with aspect. In the southern and northwestern mountainous areas,there was a wide distribution of forest land.As shown in Figure 5,the hot spots of forest land covered the mountainous areas in northern Hebei Province and the low mountainous and hilly areas of the Loess Plateau, with a larger slope and complex terrain. Slope was found to be associated significantly and positively with forest land area $( P { < } 0 . 0 1 )$ ，and the coefficients were 2169.820 and 3901.600 in 2000 and 2020,respectively. Terrain relief was not significant in 2OOO but was highly significant $( P { < } 0 . 0 1 )$ and positively associated with forest land area in 2O2O,with a coefficient of138.368.

Table 3Factors driving spatiotemporal variation of forest land in the AENC   

<html><body><table><tr><td rowspan="2">Variable</td><td colspan="2">Impact factor in 2000</td><td colspan="2">Impact factor in 2020</td></tr><tr><td>Coefficient</td><td>P</td><td>Coefficient</td><td>P</td></tr><tr><td>Constant</td><td>-13,799.200</td><td>0.000</td><td>-26374.700</td><td>0.000</td></tr><tr><td>Average annual precipitation</td><td>7.235***</td><td>0.000</td><td>12.376***</td><td>0.000</td></tr><tr><td>Annual average temperature</td><td>-241.243***</td><td>0.000</td><td>-483.495***</td><td>0.000</td></tr><tr><td>Elevation</td><td>1.497</td><td>0.433</td><td>1.747</td><td>0.629</td></tr><tr><td>Slope</td><td>2169.820***</td><td>0.000</td><td>3901.600***</td><td>0.000</td></tr><tr><td>Aspect</td><td>-13.154**</td><td>0.020</td><td>-26.441***</td><td>0.000</td></tr><tr><td>Terrain relief</td><td>30.720</td><td>0.393</td><td>138.368***</td><td>0.000</td></tr><tr><td>Economic density</td><td>-3.299</td><td>0.995</td><td>0.184</td><td>0.786</td></tr><tr><td>Population density</td><td>-0.022*</td><td>0.071</td><td>-3.421</td><td>0.311</td></tr><tr><td>Road network density</td><td>-0.711***</td><td>0.000</td><td>-2.856***</td><td>0.001</td></tr><tr><td>Ecological conversion project</td><td>3953.950</td><td>0.513</td><td>9634.830***</td><td>0.000</td></tr><tr><td>Afforestation policy for barren mountains</td><td>311.692***</td><td>0.000</td><td>2298.230**</td><td>0.020</td></tr><tr><td>R²</td><td colspan="2">0.805</td><td colspan="2">0.793</td></tr><tr><td>Log likelihood</td><td colspan="2">-70,786.733</td><td colspan="2">-75,596.840</td></tr><tr><td>Akaike information criterion</td><td colspan="2">141,597</td><td colspan="2">151,218</td></tr><tr><td>Schwarz criterion</td><td colspan="2">141,679</td><td colspan="2">151,299</td></tr></table></body></html>

Nte:\*\*iaeaelaosattdsspeivelesatistabledtith value of explained variable when the value of explanatory variable is O.

# 3.3.2 Socioeconomic factors

With improved socioeconomic levels, the distribution pattern of forest land changed significantly. Table 3 shows that two variables passed the significance test of SEM in the socioeconomic dimension: (1） population density was associated significantly and negatively with the dependent variable $( P { < } 0 . 0 5 )$ in 2000 with a coefficient of $- 0 . 0 2 2$ , but it became insignificant in 202O; and (2) road network density was highly significant $( P { < } 0 . 0 1 )$ in 2OOO and 2O2O and was also correlated negatively with the distribution of forest land,with the coefficients of $- 0 . 7 1 1$ and $- 2 . 8 5 6$ respectively. These results showed that forest land had a lower possibility of appearing in regions with intensive population, more-developed economy and superior transportation location, where cropland and construction land were dominant. Forest land was distributed mainly in suburbs and remote areas with inconvenient transportation.

# 3.3.3 Regional policy factors

Table 3 shows that two variables impacted the distribution of forest land in the aspect of regional policies: forest land area was correlated significantly and positively with ecological projects and afforestation policy for barren mountains.The former was significantly relevant to forest land $( P { < } 0 . 0 1 )$ in 2020, with a regression coefficient of 9643.830. Implemented in 1999 and restarted in 2014,the project of Grain for Green resulted in dramatic changes in forest land distribution in the AENC.Moreover，afforestation policy for barren mountains was significantly and positively relevant to forest land ( $( P { < } 0 . 0 1$ in 2000 and $P { < } 0 . 0 5$ in 2020,respectively),with the coefficients of 311.692 and 2298.230, respectively. With the implementation of ecological projects,the evolution of forest land has had significant impacts. These results indicate that the probability of forest land increased in regions located in ecological construction areas from 2Ooo to 2020.

# 4Discussion

# 4.1 Effects of natural environment factors on forest land in the AENC

According to the results of spatial regression model (Table 3), natural environment factors such as average annual precipitation, annual average temperature, slope, aspect and terrain relief were the key driving factors for the spatial distribution of forest land,which were consistent with the existing researches. For example，Morales et al. (2O2O) and Kibler et al.(2O21） found that precipitation was an important natural factor affecting the spatial pattern of forest land.Fu et al (2021) and Deng et al (2O21) pointed out that climatic and topographical factors,such as annual average temperature,altitude and slope,played important impacts on the spatial distribution of forest land. Compared with previous studies,the influence of natural environment factors such as average annual precipitation, annual average temperature, slope,aspect and terrain relief on the spatial distribution of forest land was positive.The AENC located in the transitional zone from farming areas to pastoral areas and from semi-arid areas to arid areas, was an important ecological security barrier and water conservation area of Beijing-Tianjin-Hebei with sensitive ecological environment. Those natural environment factors represented the regional natural conditions, which reflected the macro-geographic background of the AENC to a certain extent. Therefore,the effects of those natural environment factors on the spatial distribution of forest land in the AENC was synthetic. Similar results were reported form the researchers of Chen et al. (2O17) and Wang et al. (2021),who found that spatial differentiation of forest land was resulted from altitude,aspect and slope position. Since the $2 1 ^ { \mathrm { s t } }$ century， government took ecological projects in the AENC, which resulted in the expansion of forest land in high altitude and slope areas.Moreover,because the AENC was located in the transitional areas from the monsoon areas to the non-monsoon areas, its sunny slopes and semi-sunny slopes were also windward slopes,where the heat and precipitation were relatively abundant. Development of forest land in these areas was more suitable. Similar result was confirmed by Nirmal et al. (2O21) and Wang et al. (2O21), who found that geographical location influenced the drought distribution and the growth of shrub.

# 4.2 EffectsofhumanactivitiesonforestlandintheAENC

Socioeconomic and policy factors played important roles in the spatial distribution of forest land. Our results found that road network density had a negative impact on the spatial distribution of forest land in the AENC,and the impact of population density gradually weakened. Yu et al. (2017)and Bochet et al. (2O21) also found that population growth and economic development had significant impacts on the transition and spatial distribution of forest land with the qualitative analysis. Rapid economic development, improvement of urbanization level, changes of industrial structure and urban population growth usually resulted in the decrease of forest land (Wan et al., 2019; Feng et al.,2O21; Hou et al., 2021). Due to the limited socioeconomic construction and slow development of industry and agriculture in the AENC,the impact of economic density on the spatial distribution of forest land weakened.Moreover, population outflow was serious and the residents was gradually decreasing in the AENC. The influence of population density on the spatial distribution of forest land isalso decreasing.With the implementation of new urbanization construction and rural revitalization strategy in the AENC，the traic facilities had been continuously improved,and the road accessibility had gradually increased，which caused the change of spatial distribution pattern of forest land.

Policy factors,especially Grain for Green project had significant effects on the spatiotemporal variation of forest land in the AENC.Deng et al. (2O21) and Liu et al.(201O) found that the Grain for Green project was an important driving factor for the increase of forest land in mountainous areas,which was consistent with this study. Compared with previous studies,the impact of ecological projects and aforestation policy for barren mountains on the spatial distribution of forest land in the AENC had gradually enhanced. Owing to a series of ecological projects had been carried out since 1999, the function of ecological security barrier of the AENC had been enhanced.

# 5 Conclusions

This study found that the changes in forest land in the AENC from 20OO to 2O2O were dominated by conversion among forest land, grassland and cropland, which occurred mainly in the areas with elevations of $5 0 0 { - } 2 0 0 0 \mathrm { m }$ and slopes of $5 ^ { \circ } - 2 5 ^ { \circ }$ . In this study,the spatial pattern of forest land from 2000 to 2O2O showed a trend of an inverted U-shaped diferentiation in the east-west direction, being high in the north and low in the south.The hot spots of forest land gathered in the southern marginal areas of the Yanshan Mountains and the low mountainous and hilly areas of the Loess Plateau,and the sub-hot spots around the hot spots moved southward. The sub-cold spots spread to the surrounding areas, and the cold spots disappeared. Spatiotemporal variation of forest land was influenced by natural environment, socioeconomic and policy factors. Impacts of terrain relief and ecological conversion policy increased, while those of population density decreased. Consequently, this study offers scientific references for protection of forest land and ecological construction in the AENC.However,a further study should be conducted to explore the impact of intensity of policy implementation and other policy factors that will influence the distribution of forest land.

# Acknowledgements

This research was funded by the National Natural Science Foundation of China (41971238),the Ministry of Education Humanities and Social Youth Foundation of China (19YJCZH144),the Natural Science Foundation of Shandong Province，China (ZR2019QDo06)，and the National College Student Innovation Training Project (S202010446004).

# References

BochetE,MolinaMJ,MonleonV,etal.2O21.Interactionsof pasthumandisturbanceandariditytriggerabruptshifts nthe functional state of Mediterranean holm oak woodlands.CATENA,206:doi:10.1016/J.CATENA.2021.105514.   
Cao RF,ZhangAL,CaiYY.2O14.Economiccompensationpartitionforcultivatedland protectioand fiscal ransferpayment: Take Hubei Province as example.China Population,Resourcesand Environment,24(12):14-22.(in Chinese)   
Cao YG,YaoLJ,HaoY,etal.2Oo8.Researchonregionalforestrypatern,drivingforceandecological value.ResearchfSil and Water Conservation,15 (2):73-79.(in Chinese)   
ChenY,LinYW,LinLL,etal.2O17.StudyonlandusechangeinPutianCityandspatial simulationofforestlandtrasition basedonMarkovmodelandLogisticregresionmodel.JournalofChina AgriculturalUniversity22(2):87-97.(inChinese)   
ChenYQ,Yang P.2Oo1.Recent progressesof international studyonlanduse and land cover change.Economic Geography, 21(1):95-100.(in Chinese)   
ClarkePJ.2Oo3.Compositionof grazedand cleared temperate grassy woodlands ineastern Australia:paterns inspaceand inferences in time.Journal of Vegetation Science,14(1):5-14.   
DahalNM,XiongDH,NeupaneN,etal.2O21.Spatiotemporalanalysisof droughtvariabilitybasedonthestandardized precipitation evapotranspiration index in the KoshiRiver Basin,Nepal.Journal of AridLand,13(5): 433-454.   
DengYJ,HouMY,Zhang X,etal.2O21.Analysisof driving forcesofforestlandchange inQinba Mountainareaof Shaanxi basedontheLogisticregressionmodel.JournalofNanjingForestry University(NaturalSciencesEdition),45(6):9098.(in Chinese)   
Du GM,SunXB,LiuYS.2O16.Analysis of ecologicalrestorationonecosystemservice and its human drivingfactorsinYan'an

City.Research of Soil and Water Conservation,23(3):233-239.(in Chinese)

DwomohFK,Brown JF,Toerud HJ,etal2021.Hoterdrought escalates tree cover declines inblueoak woodlandsof California.Frontiers in Climate,doi: 10.3389/FCLIM.2021.689945.   
Feng Y,Tang X,Bao QF.2O21. Driving factorsofforest ecological securityin Yangtze River Delta based on GWR Model. Ecological Economy.[2021-03-21]. htps://ns.cnki.net/kcms/detail/53.1193.F.20211003.1204.004.html. (inChinese)   
Fu JX,CaoGC,Guo WJ.2O21.Terrin gradient changeof landuseand its geographical detectorof terrain factors on the south-facingslopeof Qilianshan Mountains from1980 to2018.ResearchofSoiland WaterConservation,28(6):371-381.(in Chinese)   
GarnerG,MalcolmLA,SadlerJP,etal.2O15.Inter-anualvariabilityintheeectsofriparian woodlandonmicro-cmate,   
energy exchanges and water temperature of an upland Scotish stream. Hydrological Processes,29(6):1080-1095.   
GodleeJL,RyanCM,BaumanB,etal.2O21.Structuraldiversityandtreedensitydrivesvariationinthbiodiversitycosystem function relationship of woodlands and savannas.New Phytologist,232(2): 579-594.   
Gou MM,LiuCF,LiLetal.2O21.EcosystemservicevalueefectsoftheThreeGorges ReservoirArea landtransforation underthe perspectiveof "production-living-ecological"space.Chinese Journal of Applied Ecology，32(11):393-3941.(in Chinese)   
Hou W,Hou XY,Sun M,etal.2O21.Landuse/landcoverchange alonglow-midle latitudecoastalareasof Eurasiaandtheir driving forces from 2000 to 2010.World Regional Studies,30(4): 813-825.(in Chinese)   
Kibler CL,SchmidtEC,RobertsDA,etal.221.Abrown waveofriparian woodlandmortalityfollowinggroundwaterdeclines duringthe2012-2019Califoiadrought.EnvironmentalResearchLeters,16(8):084030,doi:10.1088/1748-9326/AC1377.   
Li J,Wang X,ChangSL,etal.2O21.Distributioncharacteristicsandinfluencing factorsofmercuryonthesoilprofileof Picea Schrenkiana forest.Environmental Chemistry,40(6):1723-1732.(in Chinese)   
Li Y,XiaoLM,HuWM,etal.2021.Spatio-temporalpaternoflandusechangeinChangsha-Zhuhou-Xiangtacore areasand its driving forces.Economic Geography,41(7):173-182.(in Chinese)   
LiY,ZhaoZB,WangLZ,etal.2O21.Vegetationchanges inresponse toclimaticfactorsand human activities inJilinProvince,   
China,2000-2019. Sustainability,13(16): 8956.   
Liu C,Huo YW,XuYQ,etal.2O18.Changes incultivated landand influencing factors beforeand after the implementationof Grain for Green Project in Zhangjiakou City.Journal of Natural Resources,33(10):1806-1820.(in Chinese)   
Liu JX,GaoJX.2o8.Changesoflnduseand landscape pattrn intheboundarychange areas infarming-pastoral ecotoneof Northern China.Transactions ofthe Chinese Society of Agricultural Engineering,24(11):76-82. (in Chinese)   
Liu JY,Zhang ZX,Kuang WH,et al.20lo.Spatialpaterns and driving forces of landuse changein China during the early $2 1 ^ { \mathrm { s t } }$ （20 century. Journal of Geographical Sciences,2O(4): 483-494.   
Liu JY,KuangWH,Zhang ZX,etal.2O14.Spatiotemporalcharacteristics,patterns,ndcausesof land-usechanges inChina since the late 198Os. Journal of Geographical Sciences,69(1): 3-14.   
Liu M,Zhao CW,Shi M H.2O12.Spatialautocorrelation analysis of multi-scale landusechange at mountainous areas in Guizhou Province.Transactions of the Chinese Societyof Agricultural Enginering,28(10):239-246.(in Chinese)   
Liu MZ,Wang YF,Pei HW.2021.Thechanges oflanduseandcarbon storage inthe northern farming-pastoral ecotoneunder the background of returning farmland to forest (grass).Journalof Desert Research,41(1):174-182.(in Chinese)   
Luo ZW,LiYH,Hu XJ,etal.2O21.Analysisofforest landscapepatern evolutionanditsinfluencing factorsinHunan Province.Research of Soil and Water Conservation,doi:10.13869/j.cnki.rswc.20210820.002.(in Chinese)   
Morales MC,StefenM,SamartinS,etal2O2.Long-termresponsesofMediterraneanmountainforests toclimatechange,fire and human activities in the Northern Apennines (Italy).Ecosystems,24: 1361-1377.   
Njoghomi EE,Valkonen S,KaelssonK,etal.2021.Regenerationdynamicsand structural changes inMiombo woodlandstands at Kitulangalo Forest Reserve in Tanzania. Journal of Sustainable Forestry, 4O(6): 539-557.   
Peng J,DuYY,LiuYX,etal.2O17.Fromnaturalregionalization,landchangeto landscapeservice:The developmentof integrated physical geography in China. Geographical Research,36(10):1819-1833.(in Chinese)   
Qing F,ChenPX,YangBG,etal.2O20.Kernel densityhotspot detectionandspatialautocorrelationanalysisofaccesble facility spatial layout:acase studyof outdoor public space in centralof Beijing.Buletinof Surveyingand Maping,(9): 140-142.(in Chinese)   
RenP,WuT,ZhouJM,etal.2O16.Analysisofspatialdistributionpaterand evolutionarycharacteristicsofcultivatedlands basedonspatialautocorrelation modelandGIS platform:AcasestudyofLongquanyi District,Chengdu,China.Chinese Journal of Eco-Agriculture,24(3):325-334.(in Chinese)   
Rohde MM,StelaJC,Roberts DA,etal.2O21.Groundwaterdependenceof riparian woodlandsandthedisruptingeffectof anthropogenicallyaltered streamflow.Procedingof the National Academyof Science of the United Statesof America. 118(25): e2026453118,doi: 10.1073/PNAS.2026453118.   
ShaoYK,ZhuCM,XuXL,etal.20l9.Analysisofspatialandtemporalchangesandtributiondiscriminationofforestlandin Anhui Province from 2000 to 2015.Ecological Science,38(6):15-21. (in Chinese)   
ShriverRK,YackulicCB,BellDM,etal.2O21.Quantifying thedemographiculnerabilitiesofdry oodlands toclimateand competition using range wide monitoring data. Ecology,102(8): e03425,doi: 10.1002/ECY.3425.   
SunSL,Zhang XP.2O21.Analysisonthespatiotemporal evolutionoflanduse transformationand itsecological environment effect in Shaanxi Province.Research of Soil and Water Conservation,28(6):1-9.(in Chinese)   
Wan AG,Wang JQ,WuK Q.2O19.Temporaland spatialcharacteristicsand driving factorsofforest land change inJiangxi. Anhui Agricultural Science Bulletin,47(7):128-131.(in Chinese)   
Wang C,Ouyang H,Maclaren V,etal.2Oo7.Evaluationof theeconomicand environmental impactofconvertingcroplandto forest: Acase study in Dunhua County,China.Journal of Environmental Management, 85(3): 746-756.   
Wang JY,LiuYS.2Oo9.Land use andcover changeand its driving forces in Sanya.Journal of Natural Resources,24(8): 1458-1466.(in Chinese)   
WangR,TangCW,LiZ,2O21.Ecological suitabilityevaluation basedonGIS-acase studyof Yiwagou forestarea,Diebu, eastern Qinghai-Tibet Plateau.Academic Research,4(3): 3-10.   
WangZT,YangL,LiG,etal.21.DistributionanddiversityofherbageunderCaraganaorshinskiiplantationathisoe scale in the semi-arid loess hilly region.Journal of Desert Research,41(2):120-128.(in Chinese)   
Wei CP.2O20.Problems and countermeasures in theprotectionand management offorest landresources in state-owned forest farm:Acase studyof Huangmian forest farm directlyunder Guangxi Zhuang Autonomous Region.Anhui Agricultural Science Bulletin,26(8): 53-54.(in Chinese)   
Xi MZ,ZhaoZQ,WuPS,et al.2O21.Changesand predictionsof landuseinmountain sectionof theHutuo RiverBasinbased on improved CA-Markov model.Journal of Northwest Forestry University,36(4):150-158.(in Chinese)   
XieM,Gong ZW.20l9.Forestresource monitoringanddrivingforce analysisbasedonhigh-resolutionsatelite images.Journal of Central South University of Forestry & Technology,29(5):30-36.(in Chinese)   
YangL,Fu C.2O18.Spatio-temporalsimulationofGannan ecologicalbarierunder diferentscenarios.Scientia Geographica Sinica,38(3): 457-463.(in Chinese)   
Yu H,ZhangB,Wang ZM,etal.2Ol7.Landcover changeand itsdriving forcesintherepublicof Korea since the 1990s. Scientia Geographica Sinica,37(11):1755-1763.(in Chinese)   
Yu Y,ChengQW,Yu WF,etal.2020.Studyonimpactof rural-householddiferentiationonforestlandcirculationbehavior. Forestry Economics,42(8):23-31. (in Chinese)   
Zhang Y,YangBG,WangM,etal.2O2O.StudyonthespatialchangesanddrivingforcesofforestlandinBeijing-Tanjin-Hebei Region.Science of Surveying and Mapping,45(9):104-110.(in Chinese)   
Zhou CQ,LiuSY,WangP.2O18.Analysisofthedriving factorsof land useandchange basedon GIS-Logisticcoupling model in Guanghe County. Journal of Gansu Agriculture University,53(3):118-125.(in Chinese)   
Zhou D C,ZhaoSQ,Zhu C.2012.The impact of theGrain for GreenProjectonthe land use/coverchange in the northern farming-pastoral ecotone,China-acase studyof Kezuohouqi County.Scientia Geographica Sinica,32(4):442-449.(in Chinese)   
ZhuL.2015.Analysisoftherelationship between forestlndchangeand ecologicalenvironmentcoupling in DoronCounty inthe past 20 years.Inner Mongolia Forestry,(8):1O-11.(in Chinese)