# Spatial-temporal characteristics of drought detected from meteorological data with high resolution in Shaanxi Province, China

WANG Yudan1,2.3, KONG Yunfeng1,2\*, CHEN Hao³, DING Yongjian4

1 College of Environment and Planning, Henan University, Kaifeng 475oo4, China;   
2 Key Laboratoryof Geospatial Technologyfor the Middle and Lower Yellw River Regions,Ministryof Education,Henan   
University, Kaifeng 475004, China;   
3 School of Geography and Environment,Baoji University of Arts and Sciences, Baoji 721013,China;   
4 Northwest Institute of Eco-Environment and Resources,Chinese Academyof Sciences,Lanzhou 73oo,China

Abstract: The spatial pattern of meteorological factors cannot be accurately simulated by using observations from meteorological stations (OMS) that are distributed sparsely in complex terrain. It is expected that the spatial-temporal characteristics of drought in regions with complex terrain can be better represented by meteorological data with the high spatial-temporal resolution and accuracy. In this study, Standard Precipitation Evapotranspiration Index (SPEI) calculated with meteorological factors extracted from ITPCAS (China Meteorological Forcing Dataset produced by the Institute of Tibetan Plateau Research, Chinese Academy of Sciences) was applied to identify the spatial-temporal characteristics of drought in Shaanxi Province of China, during the period of 1979-2016. Drought areas detected by SPEI calculated with data from ITPCAS (SPEI-ITPCAS) on the seasonal scale were validated by historical drought records from the Chinese Meteorological Disaster Canon-Shaanxi, and compared with drought areas detected by SPEI calculated with data from OMS (SPEI-OMS). Drought intensity, trend and temporal ranges for mutations of SPEI-ITPCAS were analyzed by using the cumulative drought intensity (CDI) index and the Mann-Kendall test. The results indicated that drought areas detected from SPEI-ITPCAS were closer to the historical drought records than those detected from SPEI-OMS. Severe and exceptional drought events with SPEI-ITPCAS lower than $- 1 . 0$ occurred most frequently in summer, followed by spring.There was a general drying trend in spring and summer in Shaanxi Province and a significant weting trend in autumn and winter in northern Shaanxi Province. On seasonal and annual scales, the regional and temporal ranges for mutations of SPEI-ITPCAS were different and most mutations occurred before the year 1990 in most regions of Shaanxi Province. The results reflect the response of different regions of Shaanxi Province to climate change, which will help to manage regional water resources.

Keywords: SPEI; drought areas; meteorological data; cumulative drought intensity; drying trend; weting trend

# 1 Introduction

Drought is a damaging and frequent natural disaster (He et al., 2O11) that is significantly related to temperature abnormalities and shortage of precipitation (Salehnia et al., 2O17a). It is sensitive to climate change (Kogan et al., 2013; Jia et al., 2O16) and has a significant impact on economic, ecological and agricultural activities. Research on the spatial-temporal characteristics of drought will help to identify the correlation of drought with meteorological, hydrological and ecological processes (Yu et al.,2O15; Yuan et al., 2O15), and to further evaluate the impact of climate change on human society.

Currently, research on the spatial-temporal characteristics of regional drought faces the following challenges: (1) the applicability of drought indices varies greatly due to the specific climatic features of the study area (Qiao et al., 2012; Yang et al., 2017); (2) the accuracy of drought monitoring depends heavily on the accuracy and spatial-temporal resolution of the input data for the drought index (Liu et al.,2016; Wang et al.,2016; Salehnia et al.,2017b); and (3) the occurrence and spatial-temporal distribution of drought events identified by the drought index need validation (Liu et al.,2018; Wang et al.,2018). It is imperative to find an appropriate drought index, a reliable validation method and the meteorological data with high spatial-temporal resolution to improve the quality of drought monitoring over specific regions.

Meteorological drought is generally monitored and measured by multifactorial drought indices involving water and energy balance (Vasiliades and Loukas, 2OO9; Dai, 2O11; Paulo et al., 2012; Gobena and Gan, 2O13), such as the Palmer Drought Severity Index (PDSI), Self-calibrated PDSI (Sc-PDSI) (Wells et al., 2O04), and Standard Precipitation Evapotranspiration Index (SPEI) (Vicente-Serrano et al., 2O1Oa). PDSI requires parameters including soil water holding capacity, groundwater level and lake/reservoir level (Ma et al., 2O15), which are not available in many circumstances. Furthermore, the temporal scale of PDSI is fixed (Vicente-Serrano et al., 2011), although drought is a multi-scale phenomenon (Changnon and Easterling, 1989; Pandey and Rafmasastri, 2010). Sc-PDSI is an improved version of PDSI (Wels et al., 2O04; Liu et al., 2015), but the temporal scale is still not alterable. In contrast, SPEI combines the sensitivity of PDSI to evaporation changes and the multi-temporal nature of the Standardized Precipitation Index (SPI) (Vicente-Serrano et al.,2O1Oa). Besides, it needs fewer parameters compared with PDSI when the Thornthwaite (Th) method is used to calculate evaporation. Thus, SPEI has been widely used to elaborate the spatial-temporal characteristics of regional drought and to reconstruct the spatialtemporal distribution of drought (Allen etal., 2O11; Meza, 2013).

Much research on drought quantification, monitoring and analysis has been conducted by machine learning models or spatial interpolation methods with metrological factors extracted from observations from meteorological stations (OMS) (Jiang et al., 2015; Rhee and Im, 2017; Wang et al., 2019; Zhang et al., 2019). However, the spatial interpolation of metrological factors (e.g., precipitation) brings significant errors due to the sparse observations and the complex terrain. Accuracy of SPEI forecasting by machine learning models with multisource data needs further theoretical investigation, particularly because SPEI may vary under diferent climatic conditions (Rhee and Im, 2O17). It is more reliable to adopt meteorological datasets with high spatial-temporal resolution to directly quantify the drought based on drought indices (Vicente-Serrano et al., 2010b; Hannaford et al., 2O11; Wang et al., 2O16). Many studies have tested the applicability of various meteorological datasets in drought analysis at multiple scales under different climatic conditions. For example, Salehnia et al. (2O17b) calculated eight drought indices with AgMERRA (Agricultural Model Intercomparison and Improvement Project based on the NASA Modern-Era Retrospective Analysis for Research and Applications) precipitation data and OMS data for drought monitoring. Results showed that the correlation between drought events and the former was higher than that between drought events and the latter. Naumann et al. (2O14) investigated five different datasets and three drought indicators with regard to their capability to improve drought monitoring in Africa. They found that the extents of drought areas identified by drought indicators were different. Spinoni et al. (2019) constructed a dataset of meteorological drought events from 1951 to 2016 based on Global Precipitation Climatology Centre (GPCC) and Climatic Research Unit (CRU) time-series datasets with a spatial resolution of $0 . 5 ^ { \circ }$ . It can be concluded that the spatial resolution and accuracy of the gridded meteorological data and a suitable drought index were essential to identify the occurrence, intensity and spatial extent of drought.

Multiple metrics (e.g., duration, intensity and area) of drought events were extracted from historical drought records and served as "ground truth" to validate the estimates obtained from drought indices (Spinoni et al., 2019; Wang et al., 2019). Drought detected from data with the high spatial resolution and accuracy can be bettr validated by drought records. In addition, meteorological data with a long temporal range can help to depict the trend of drought. The temporal range (1979-2016) and spatial resolution (approximately $1 0 \ \mathrm { k m } { \times } 1 0 \ \mathrm { k m } )$ of ITPCAS (China Meteorological Forcing Dataset produced by the Institute of Tibetan Plateau Research, Chinese Academy of Sciences) (Chen et al., 2O11) can beter meet those requirements of drought analysis compared with other commonly used meteorological products such as TRMM (Tropical Rainfall Measuring Mission) $( 0 . 2 5 ^ { \circ } \times 0 . 2 5 ^ { \circ } )$ and CMORPH (Climate Prediction Center Morphing Technique) (starting from 1998). Numerous studies have demonstrated the efficiency of ITPCAS in hydrological and meteorological applications across China (Guo and Wang, 2013; Xue et al., 2013; Wang et al., 2018).

In this study, the spatial-temporal characteristics of drought in Shaanxi Province of China were reconstructed by SPEI and ITPCAS data, and validated by historical drought records. Firstly, the SPEI of all grids with the spatial resolution of $1 0 \mathrm { k m } { \times } 1 0 \mathrm { k m }$ in Shaanxi Province was calculated with the temperature and precipitation data of ITPCAS (termed as SPEI-ITPCAS) from 1979 to 2016. Then, drought areas detected from SPEI-ITPCAS were validated by drought records extracted from the Chinese Meteorological Disaster Canon-Shaanxi, and compared with those calculated by OMS and ordinary Kriging interpolation (OKI). Finally, drought intensity, trends and mutations of SPEI-ITPCAS in Shaanxi Province from 1979 to 2016 were analyzed using the cumulative drought intensity (CDI) index and the Mann-Kendall(MK) test. This study aims to give more details about the spatial-temporal characteristics of drought in Shaanxi Province, especially in those ungauged areas which were neglected or poorly represented in previous studies (Jiang et al., 2015; Wang et al., 2019; Zhang et al., 2019).

# 2 Study area and methods

# 2.1 Studyarea

Shaanxi Province is located on the boundary between the western arid zone and the eastern monsoon zone of China $( 3 1 ^ { \circ } 4 2 ^ { \prime } - 3 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { N }$ $1 0 5 ^ { \circ } 2 9 ^ { \prime } - 1 1 1 ^ { \circ } 1 5 ^ { \prime } \mathrm { E }$ ； Fig. 1). Meteorological disaster, especially drought, frequently occurs with damaging effects on the ecological system and regional economy. Shaanxi Province can be divided into three regions with regard to geography and climate: the northern Loess Plateau with a cold, arid climate; the middle Guanzhong Plain with a mild climate; and the southern Qinba Mountainous region with a warm, wet climate (Liu et al., 2013). Qinling Mountains run across the middle of Shaanxi Province with significant climate discrepancy between the northern and southern sides of the mountains. The Loess Plateau in the northern part of Shaanxi Province (briefly, northern Shaanxi) has a sub-arid monsoon climate with average annual precipitation varying greatly from 300 to $6 0 0 \ \mathrm { m m }$ . It is prone to both droughts and waterlogging. The Guanzhong Plain in the middle of Shaanxi Province (briefly, Guanzhong) has a warm sub-humid monsoon climate with average annual precipitation between 55O and $7 0 0 ~ \mathrm { { m m } }$ The Qinba Mountainous region in the southern part of Shaanxi Province (briefly, southern Shaanxi) has a subtropical humid monsoon climate with average annual precipitation between 8OO and 1300 mm. Flash floods and geological disasters occur frequently in this southern region. The annual mean temperature of the entire Shaanxi Province is about $1 3 ^ { \circ } \mathrm { C }$ ,with regional means of $1 0 ^ { \circ } \mathrm { C }$ in the north, $1 3 ^ { \circ } \mathrm { C }$ in the middle and $1 5 ^ { \circ } \mathrm { C }$ in the south (Wan et al., 2O13). For administrative purposes, Shaanxi Province is divided into ten areas of prefecture-level city (APC). Yulin and Yan'an belong to northern Shaanxi; Baoji, Xianyang, Tongchuan, Weinan and Xi'an belong to Guanzhong; and Shangluo, Ankang and Hanzhong belong to southern Shaanxi (Fig. 1).

# 2.2 Data sources

Temperature and precipitation data (1979-2016) with the horizontal spatial resolution of $0 . 1 ^ { \circ }$ were extracted from ITPCAS. This dataset was merged with meteorological data from the following sources: China Meteorological Administration data, reanalysis dataset of Princeton, Global Land Data Assmilation System (GLDAS) data, and Global Energy and Water Exchanges-Surface Radiation Budget (GEWEX-SRB) radiation data.

![](images/b26c677460647346bee6408d5668ae7165f89779ae52691ba1dbb53b389eb8f5.jpg)  
Fig.1Topography, administrative areas and distribution of standard meteorological stations of Shaanxi Province. N, northern Shaanxi(the Loess Plateau in the northern partof Shaanxi Province); G, Guanzhong (Guanzhong Plain in the middle of Shaanxi Province); S,southern Shaanxi (the Qinba Mountainous region in the southern part of Shaanxi Province). The two blue lines are the northern and southern boundaries of Guanzhong.

The Chinese Meteorological Disaster Canon-Shaanxi briefly summarizes the start-end months or seasons, duration, severity, areas and financial loss of drought events. However, drought areas were recorded vaguely. For example, the spatial extent was recorded as parts of the APC, or even parts of northern Shaanxi, Guanzhong and southern Shaanxi. Furthermore, the severity of drought is hard to quantify from these descriptions. Drought events extracted from records of the Chinese Meteorological Disaster Canon-Shaanxi (Zhai, 2O05) during the period of 1979-2016 are shown in Table 1. It can be seen that Guanzhong and northern Shaanxi were more frequently afected by drought from 1979 to 2016.

In this study, metrological observations including precipitation and temperature during the period of 1979-2016 were downloaded from the China Meteorological Information Center (http://data.cma.cn/). Because these data were collcted under rigorous quality control, no modifications were made for this study.

# 2.3 Methods

Drought characteristics of Shaanxi Province were analyzed by the following steps in this study. Firstly,SPEI was calculated with OMS at each standard meteorological station of Shaanxi Province and then interpolated into $1 0 \ \mathrm { k m } { \times } 1 0 \ \mathrm { k m }$ grids by OKI (termed as SPEI-OMS). Then, SPEI was calculated by temperature and precipitation data extracted from ITPCAS at $1 0 \mathrm { k m } { \times } 1 0 \mathrm { k m }$ grids of Shaanxi Province (termed as SPEI-ITPCAS). Both SPEI-OMS and SPEI-ITPCAS were calculated on seasonal and annual scales, and reclassfied into drought and non-drought areas. The drought areas and period of drought occurrence were identified and then validated by comparison with historical records of drought events listed in Table 1. Secondly, spatial distributions of drought intensity, trend and temporal ranges for mutations of SPEI-ITPCAS in Shaanxi Province during the period of 1979-2016 were analyzed on seasonal (SPEI 3) and annual (SPEI 12) scales using the CDI index and the MK test.

Table 1Historical records of typical drought events occurred in Shaanxi Province from the Chinese Meteorological Disaster Canon-Shaanxi   

<html><body><table><tr><td>Year</td><td>Season</td><td>Drought areas</td></tr><tr><td>1991</td><td>Summer</td><td>South of northern Shaanxi, Guanzhong and southern Shaanxi (especially in Shangluo)</td></tr><tr><td>1994</td><td>Winter</td><td>North of northern Shaanxi and Shangluo</td></tr><tr><td>1995</td><td> Summer</td><td> South of northern Shaanxi and Guanzhong</td></tr><tr><td>1995</td><td> Autumn</td><td>All regions*</td></tr><tr><td>1997</td><td>Spring</td><td>All regions*</td></tr><tr><td>1997</td><td> Summer</td><td> All regions*</td></tr><tr><td>1998</td><td> Autumn</td><td> All regions*</td></tr><tr><td>1998</td><td>Winter</td><td> All regions*</td></tr><tr><td>1999</td><td> Summer</td><td> All regions*</td></tr><tr><td>2000</td><td> Summer</td><td>Northern Shaanxi, northern Guanzhong and east of southern Shaanxi</td></tr><tr><td>2001</td><td> Spring</td><td>All regions*</td></tr><tr><td>2001</td><td> Summer</td><td>Northern Shaanxi, Guanzhong and east of southern Shaanxi</td></tr><tr><td>2002</td><td> Summer</td><td>All regions of Shaanxi Province except for Tongchuan and south of Yan'an</td></tr><tr><td>2008</td><td>Winter</td><td>All regions*</td></tr><tr><td>2010</td><td> Autumn</td><td>All regions*</td></tr><tr><td>2011</td><td> Summer</td><td>Part of northern Shaanxi and Guanzhong</td></tr></table></body></html>

Note:\*meansthedroughteventsoccredinalltenprefecture-lvelcities.NorthSaanireferstteLoessPlateauintheorth partofShaanxi Province;Guanzhongrefers toGuanzhongPlaininthe midleofShanxiProvince;southernShaanxireferstotheQinba Mountainous region in the southern part of Shaanxi Province.

# 2.3.1 SPEI model

SPEI (Vicente-Serrano et al., 2O1Oa) reflects the characteristics of drought or waterlogging by calculating the difference between precipitation and potential evapotranspiration (PET). Currently, PET is generally calculated by Penman-Monteith (PM) equation (Allen et al., 1994) or Th (Thornthwaite, 1937) parameterization schemes. The PM scheme needs unavailable parameters such as reflectivity of ground objects in each grid of Shaanxi Province, whereas the Th scheme needs only latitude and monthly temperature data (Tsakiris et al., 2OO7) which are available for this study. Thus, the Th scheme was selected in this study. The calculation of SPEI was described as follows:

Firstly, monthly potential evapotranspiration $( \mathrm { P E T } _ { i } )$ was estimated by the Th scheme using Equation 1:

$$
\mathrm { P E T } _ { i } = 1 6 \mathrm { K } \Bigg ( \frac { 1 0 T _ { i } } { I } \Bigg ) ^ { m } ,
$$

where $\mathrm { P E T } _ { i }$ (mm) is the potential evapotranspiration of month $i ; \mathrm { ~ K ~ }$ is a correction coefficient computed as a function of the latitude and month; $T _ { i } \left( ^ { \circ } \mathbf { C } \right)$ is the mean temperature of month $i ; I$ is an annual heat index; and $m$ is a polynomial with parameter $I$

Secondly, monthly water deficit or surplus $D _ { i }$ was calculated by monthly precipitation $P _ { i }$ and $\mathrm { P E T } _ { i }$

$$
D _ { i } = P _ { i } - \mathrm { P E T } _ { i } .
$$

The calculated $D _ { i }$ values can be aggregated at different time scales. The water deficit or surplus $D _ { i , j } ^ { k }$ in a given month $i$ and year $j$ at the time scale of $k$ $( k { \le } 1 2 )$ months was defined as Equations 3 and 4:

$$
D _ { i , j } ^ { k } = \sum _ { l = 1 3 - k + i } ^ { 1 2 } D _ { l , j - 1 } + \sum _ { l = 1 } ^ { i } D _ { l , j } \left( i < k \right) ,
$$

$$
D _ { i , j } ^ { k } = \sum _ { l = j - k + 1 } ^ { i } D _ { i , j } \left( i \geq k \right) ,
$$

where $D _ { l , j } \left( \mathrm { m m } \right)$ is the water deficit or surplus in the month $l$ of year $j$ and $D _ { l , j - 1 }$ (mm) is the water deficit or surplus in the month $l$ of year $j { - } 1$

According to the Kolmogorov-Smirnov test, the log-logistic distribution was the best to fit SPEI at time scales from 1 to 24 months compared with Pearson II and Gamma distribution (VicenteSerrano et al., 2010a; Yu et al.,2O14). Thus, the log-logistic distribution was used to calculate SPEI after $D _ { i , j } ^ { k }$ series were normally standardized. The probability distribution function $f ( x )$ and cumulative distribution function $F ( x )$ of the log-logistic distribution for $D _ { i , j } ^ { k }$ series were defined in Equations 5 and 6, respectively:

$$
f ( x ) = \frac { \beta } { \alpha } \Bigg ( \frac { x - \gamma } { \alpha } \Bigg ) ^ { \beta - 1 } \Bigg [ 1 + \Bigg ( \frac { x - \gamma } { \alpha } \Bigg ) ^ { \beta } \Bigg ] ^ { - 2 } ,
$$

$$
F ( x ) = \left[ 1 + \left( { \frac { \alpha } { x - \gamma } } \right) \right] ^ { - 1 } ,
$$

where $a , \beta$ and $\gamma$ are the scale, shape and origin $( \gamma { < } D _ { i } { < } \infty )$ parameters, respectively. Finally, SPEI can be calculated by Equations 7 and 8:

$$
\mathrm { S P E I } = W - \frac { \mathbf { C } _ { 0 } + \mathbf { C } _ { 1 } W + \mathbf { C } _ { 2 } W ^ { 2 } } { 1 + \mathbf { d } _ { 1 } + \mathbf { d } _ { 2 } W ^ { 2 } + \mathbf { d } _ { 3 } W ^ { 3 } } ,
$$

$$
{ \cal W } = \sqrt { - 2 \ln \left( P \right) } \ .
$$

W used in Equations 7 and 8 is the standardized value of $F ( x )$ . Constants used in Equation 7 are listed as follows: $\mathrm { C _ { 0 } } { = } 2 . 5 1 5 5 1 7$ ， $\mathbf { C } _ { 1 } { = } 0 . 8 0 2 8 5 3$ ， $\mathbf { C } _ { 2 } { = } 0 . 0 1 0 3 2 8$ ， $\mathrm { d } _ { 1 } { = } 1 . 4 3 2 7 8 8$ ， $\scriptstyle \mathbf { d } _ { 2 } = 0 . 1 8 9 2 6 9$ and $\mathrm { d } _ { 3 } { = } 0 . 0 0 1 3 0 8$ . In Equation 8, if $P { \leq } 0 . 5$ ，then $P$ can be calculated as $P { = } 1 { - } F ( x )$ ，where $P$ is the probability of exceeding the determination of $D _ { i }$ ；whereasif $P { > } 0 . 5$ ，thus $P$ can be calculated as $\scriptstyle P = F ( x )$

In this study, SPEI was calculated on seasonal (SPEI 3) and annual (SPEI 12) scales. Categories of drought and waterlogging classified by SPEI are shown in Table 2.

Table 2 Categories of drought and waterlogging classified by SPEI (Standard Precipitation Evapotranspiration Index)   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">Drought</td><td>Normal</td><td colspan="3">Waterlogging</td></tr><tr><td>Exceptional</td><td>Severe</td><td>Moderate</td><td>Normal</td><td>Moderate</td><td>Severe</td><td>Exceptional</td></tr><tr><td>SPEI</td><td>≤-2.0</td><td>-2.0- -1.0</td><td>-1.0- -0.5</td><td>-0.5-0.5</td><td>0.5-1.0</td><td>1.0-2.0</td><td>≥0.0</td></tr></table></body></html>

# 2.3.2 Ordinary Kriging interpolation (OKI)

OKI makes an unbiased estimation of variables at target locations by a weighted linear combination of neighboring observations. It has been widely used as a popular Kriging technique to interpolate meteorological factors. Previous studies showed that OKI outperformed in precipitation interpolation compared with methods including Inverse Distance Weighted, Thiessen Polygons and Simple Kriging (Zhang and Srinivasan, 2OO9; Szczesniak and Piniewski, 2015). Details of using OKI for precipitation interpolation can be found in the original study of Goovaerts (2000).

# 2.3.3Cumulative drought intensity (CDI)

CDI on seasonal and annual scales can integrate the drought severity and frequency of various forms of drought, providing the ways to evaluate drought over the long-term period (Kim et al., 2002; Loukas et al., 2Oo8). It can wellindicate the cumulative impact of drought on human society in a specific region.

We calculated CDI according to the following steps: firstly, we calculated the SPEI-ITPCAS of each grid on seasonal and annual scales; secondly, we accumulated the drought (SPEI-ITPCAS lower than $- 0 . 5 )$ according to the temporal range (Kim et al., 2OO2; Loukas et al., 2O08). The larger the absolute cumulative SPEI-ITPCAS is, the greater the CDI is. Drought areas with cumulative SPEI-ITPCAS less than $- 1 4 . 0$ were calculated by summing the areas of the grids with high CDI values.

# 2.3.4 Mann-Kendall (MK) test

MK test (Mann,1945; Kendall,1975) was used in this study for trend and trend mutation tests. MK test is widely applied in trend analysis of meteorological and environmental factors, such as precipitation, temperature and runoff (Ahmad et al., 2O15). The principle of MK trend test was described below.

MK trend test assumed that the original time series $\scriptstyle x _ { t } = ( x _ { 1 } , x _ { 2 } , \ldots , x _ { n } )$ was random and independent with no significant trend. The statistical variable $S$ was defined in Equation 9:

$$
S = \sum _ { i = 1 } ^ { n - 1 } \sum _ { j = i + 1 } ^ { n } \operatorname { s g n } { \Big ( } x _ { j } - x _ { i } { \Big ) } ,
$$

where sgn is a symbolic function; and $x _ { j }$ and $x _ { i }$ are the values of variables of the time series. If $n { \geq } 1 0$ + S can be approximately normally distributed. In addition, variable $Z$ was used to show the results ofsignificance test, which was defined as Equation 10:

$$
Z = { \left\{ \begin{array} { l l } { \left( S - 1 \right) / { \sqrt { \operatorname { v a r } \left( S \right) } } \ \left( S > 0 \right) } \\ { \qquad 0 \ } & { \qquad \left( S = 0 \right) . } \\ { \left( S + 1 \right) / { \sqrt { \operatorname { v a r } \left( S \right) } } \ \left( S < 0 \right) } \end{array} \right. }
$$

In a two-sided hypothesis test, positive and negative values of $Z$ corresponded to the upward and downward trends, respectively. If $\scriptstyle | Z | \leq Z _ { 1 - \alpha / 2 }$ （ $\overset { \cdot } { \alpha }$ is the significance level), the original hypothesis was accepted, namely, the time series data had no significant trend; otherwise, the hypothesis was rejected, and the time series data had a significant trend. Moreover, If $\vert Z \vert { \ge } 1 . 2 8$ , 1.64 and 2.32, the significance test was accepted at significance levels of $90 \%$ ， $9 5 \%$ and $9 9 \%$ , respectively.

In this study, we conducted the mutation test of MK according to the following descriptions.

The MK trend variation test assumed that the original time series $\scriptstyle x _ { t } = ( x _ { 1 } , x _ { 2 } , \dotsc , x _ { n } )$ was random and independent with no significant trend. The statistical variable $U F _ { k }$ was the forward sequence and was defined as Equation 11:

$$
U F _ { k } = \frac { S _ { k } - E \big ( S _ { k } \big ) } { \sqrt { \operatorname { v a r } \big ( S _ { k } \big ) } } , k = 1 , 2 , . . . , n ,
$$

$$
S _ { k } = \sum _ { i = 1 } ^ { k } r _ { i } , k = 2 , 3 , . . . , n ,
$$

$$
r _ { i } = \left\{ { \begin{array} { l } { + 1 \left( x _ { i } > x _ { j } \right) } \\ { 0 \left( x _ { i } \leq x _ { j } \right) } \end{array} } , \right.
$$

$$
E { \Big ( } S _ { k } { \Big ) } = { \frac { k { \big ( } k - 1 { \big ) } } { 4 } } , k = 2 , 3 , . . . , n ,
$$

$$
\operatorname { v a r } \left( S _ { k } \right) = { \frac { k \left( k - 1 \right) \left( 2 k + 5 \right) } { 7 2 } } , k = 2 , 3 , . . . , n ,
$$

where $S _ { k }$ represents the total numbers of $x _ { j }$ preceding all $x _ { i }$ and is defined in Equations 12 and 13; $E ( S _ { k } )$ represents the expectation of $S _ { k }$ ;var $( S _ { k } )$ represents the variance of $S _ { k }$ ; and $k$ represents the sequence number. For each $x _ { i } , \ r _ { i }$ represents the total numbers of $x _ { j }$ which is smaller than $x _ { i } \left( j < i \right)$ Statistical parameter $U F _ { k }$ obeys the normal distribution. If $| U F _ { k } | { > } U _ { \alpha / 2 }$ ， the time series data had a significant decreasing or increasing trend. $U F _ { k } ^ { \prime }$ was calculated by the same Equations 11-14 with the reversed times series of $x _ { t } .$ .When the two curves $U F _ { k }$ and $U F _ { k } ^ { \prime }$ intersected between the critical boundary $\scriptstyle ( y = \pm U _ { a } )$ , the moment of intersection was the trend variation begins.

# 3 Results

# 3.1 ValidationofSPEI-ITPCASandSPEI-OMS

Figures 2 and 3 show the drought areas of Shaanxi Province detected from SPEI-ITPCAS and SPEI-OMS, respectively, for years and seasons corresponding to typical drought events. It can be seen that the distribution of drought areas detected from SPEI-ITPCAS and SPEI-OMS were similar in summer of 1991, spring of 1997, autumn of 1998, winter of 1998 and spring of 2001 (Figs. 2 and 3), which accounted for $3 1 . 3 \%$ of the total seasons. In contrast, there were significant discrepancies of drought areas between the remaining seasons, indicating that meteorological data extracted from OMS and ITPCAS were not spatially consistent with drought monitoring for most of the seasons. As shown in Table 1, drought occurred in all10 APCs of Shaanxi Province in nine seasons: springs of 1997 and 2001; summers of 1997 and 1999; autumns of 1995, 1998 and 2010; and winters of 1998 and 2Oo8. In the above nine seasons, the distribution of drought areas identified from SPEI-ITPCAS (Fig. 2) was consistent with the historical records from the Chinese Meteorological Disaster Canon-Shaanxi (Table 1). In contrast, in summer of 1999 and winter of 2008, drought areas identified from SPEI-OMS (Fig. 3) were different with the historical drought records from the Chinese Meteorological Disaster Canon-Shaanxi (Table 1), with the absence of north of Guanzhong.

Table 3 lists the discrepancies of drought areas detected from different sources, i.e., historical drought records (Table 1) and SPEI-ITPCAS (Fig.2), while Table 4 shows the discrepancies of drought areas between historical drought records (Table 1) and SPEI-OMS (Fig. 3). Compared with the seasons and regions in which drought events occurred, the discrepancies of drought areas between the two SPEI results and historical records happened in summer and in north of Guanzhong and northern Shaanxi frequently. Discrepancies of drought areas listed in Table 3 were similar to those in the same season listed in Table 4. However, Table 4 presents more discrepancies than Table 3. Discrepancies of drought areas shown in Table 4 were more likely to occur in Yulin, Tongchuan and Weinan, which were frequently affected by drought. In conclusion, the detection of drought areas from SPEI-ITPCAS presented a higher accuracy than that from SPEI-OMS. Therefore, SPEI-ITPCAS was adopted to analyze the spatial-temporal characteristics of drought in Shaanxi Province.

# 3.2Distribution of CDI

Figure 4 shows that the cumulative SPEI-ITPCAS (SPEI-ITPCAS lower than $- 0 . 5 )$ in Shaanxi Province from 1979 to 2016 waswithin $- 1 0 . 0$ to $- 2 0 . 0$ on seasonal and annual scales. On seasonal and annual scales, the cumulative SPEI-ITPCAS was within $- 1 0 . 0$ to $- 1 4 . 0$ in most regions of Shaanxi Province. When the cumulative SPEI-ITPCAS was less than $- 1 4 . 0$ , the region was defined as a typical area with high CDI values. On the winter scale, the cumulative SPEI-ITPCAS was within $- 1 6 . 0$ to $- 2 0 . 0$ in most regions of Shaanxi Province and the CDI values were higher than those on other seasonal and annual scales. Figure 4a indicates that areas with higher CDI values in spring were mainly distributed on the eastern and western boundaries of Guanzhong and in southern Shaanxi (A1 and A2), especially in southeast of Guanzhong and northwest of southern Shaanxi (A2) with an area of more than $2 0 0 0 \mathrm { k m } ^ { 2 }$ and high CDI values on seasonal and annual scales. In summer, areas with high CDI values were mainly distributed in Yulin (B1) and Shangluo (B2; Fig. 4b). In autumn,areas with high CDI values were located in Yan'an (C1) and Hanzhong (C2; Fig. 4c). On an annual scale, the CDI values in western Yulin (E1) and eastern Shangluo and Weinan (E2; Fig. 4e) were high. However, Figure 4d indicates that the CDI values in winter in the whole region were abnormally high, which is not consistent with the historical drought records (Zhai, 2OO5). Thus, the CDI in winter was not analyzed in this section.

Z106E108E 110°E Z106°E 108°E 110°E Z106°E108°E110°E 1 108E110°E 400   
a) Summer of 1991 400 (b)Winter of 1994 4(c) Summer of 1995 (d) Autumn of 1995   
N88 No88 No88 Yulin N88 Yulin 380   
N.99 N9 Yan'an N9 N9 199   
2000 N0 Baojianyag eit N04 Baoji No00 N00 ng {s2Shanglu Hanzhong Sh 中 Shang   
220 Ankang 320 3Ank 220 Ankang 20 Ankang 3200 108E110E No00 106°E 108E110E No04 106°E 108E110°E No04 106E108E110°E N004 (e) Spring of 1997 (f) Summer of 1997 (g)Autumn of 1998, (h) Winter of 1998   
1088N99 N088 Yuli N80 No8 N088 AN N9 N9 Yan'ar N9 Yan No90   
N000 1 N00 N0 Baoji? lanyang N0 N40 s5   
220 200 200 N70 220   
106E108E110E No00 1069E108E110E No0t 10Sp108E1109E N04 106E108E1109E N000   
3089390 No88 N088 Yulin No8 Yulin N88 Sish N99 N9 N09 N099   
204 Not Shanglug N00 No anglu N050 Hanz ong   
220 220 22 20 200   
1E108E10 No04 106E108E1109E 10E108E110E N004 106E108rEf110E No0v   
N88 N99 Yulin N.88 N8 Yulin N08 Yulin N89 Yan'an N9 N9 N9 n'an N90 Tongchg   
2040 Not N00 Baoji anyar No4 Baoji hanyarg 3050 nangluo   
220 220 220 320 Anka 20 106E108E110E 106E108E 110°E 106E 108°E 110E 106°E 108°E 110E Legend Drought area Non-drought area ！ 200 400 km Approved No.陕S (2020) 018 (a) Summer of 1991 16E108E110E 10E108E110E E108E110E 4000   
N80 N080 N88 Yulin No8 N88 点 3.99   
N99 N9 an'ar N.9 Yan'an N9 Yan'a van 200   
2040 240 Baoj1 N0 N040 aoj！ Xi'an   
220 hong 's C'Shangluo Ankang 300 Hanzhong Ankan 220 Ankan 22 Ankang 35N   
10E 10 108E110E N 106E108E110E N004 106°E 108E110E N000 (f) Summer of1997 44 (g)Autumn of 1998 (h) Winter of 1998   
No88 No8 08 N88 uli 388 390 900   
N99 N9€ Yan' N99 Yan'a N9 Yan'at   
200 No00 N00 N00 Baoji   
320 220 320 N000 320   
N004 106E108E1102E N004 106°E108E110E N.00 10Spri108E110E 10E108E110 No00   
N088 N88 Yulin N088 Yulin N88 Yulin N88 N   
N90 Yan'a N9 N9 'an'ar N9 299 chgan Tongc) hn   
3040 Shang Veinar N0 hangluo N00 N00 Shang 3050 nzhong   
22 200 BAnkang 220 200 Ankang 320   
N004 1mE108rE1109E N004 106WE1089E110E N.04 106E1mE1109E No04 106E10erE1109E 100   
N89 Yulin N8€ Yul N088 Yu N8 Yulin N88 r   
N90 Yan'an N9 Tongc N9 Yan'ar N9 399 KanyangWeinan   
N04 N0 N00 N00 Baoji 2000   
220 200 22 200 Ankang 350 106°E108E110E 106E108E110°E 106E108°E110E 106E108E110E   
Legend Drought area Non-drought area 0 200 400 km Approved No.陕S (2020) 018 108°E 110°E N004 (b) 108°E 110°E 108E 110°E N.04   
N88 Yulin 3 Yulin Yulin 38g   
N.90 Yan'an Yan'an Yan'an. 3.90 Tongcha Tongchuan tongch   
3050 Baoji Tanyang Veima Baoji van cinan Baojianyang Veinan 304M Xi'an PG Xian/5 G.Xi'an shangluo Shangluo Shangluo nong Hanzhong Hanzhong   
32 Ankang 3Ankang 3Ankang 320 106°E 108E 110E 106°E 108E 110E 106E 108°E 110E   
N004 106 108°E 110E 108°E 110°E No04 Legend   
N088 Yulin Yulin N8 Cumulative_SPEI-TPCAS -18.0--16.0   
N090 Yan'an Yan'an' N90 -16.0- -14.0 -14.0--12.0 Tongchgian 1 -12.0- -10.0 Xanyangy Wcina anyaT 北   
304 Baoji Baoji 205 Xian Shangluo Shangluo 0 200 400 km Hanzhong Hanzhong   
320 Ankang Ankang 320 ApprovedNo.陕S(2020) 018 106°E 108E 110E 106E 108E 110E

Table 3Discrepancies of drought areas detected from historical drought records of Chinese Meteorological Disaster Canon-Shaanxi and SPEI-ITPCAS   

<html><body><table><tr><td>Year</td><td>Season</td><td>Discrepancy of drought areas</td></tr><tr><td>1991</td><td>Summer</td><td>North of northern Shaanxi</td></tr><tr><td>1994</td><td>Winter</td><td>East of Ankang</td></tr><tr><td>2000</td><td> Summer</td><td>North of Guanzhong</td></tr><tr><td>2002</td><td>Summer</td><td>Tongchuan and south of Yan'an</td></tr></table></body></html>

Note:SPEI-ITCAS,tandardPrecipitationEvapotraspirationIndexcalculatedwithdatafromChinaMeteorolgicalForcingataset roduced bythe Instituteof TibetanPlateau Research,Chinese Academyof Sciences.

Table 4Discrepancies of drought areas detected from historical drought records of Chinese Meteorological Disaster Canon-Shaanxi and SPEI-OMS   
Note:SPEI-OM,andardPreipitationEvapotranspirationIdexcalculatedwithdatafromoseratiosofmeteorologcalsatio   

<html><body><table><tr><td>Year</td><td> Season</td><td>Discrepancy of drought areas</td></tr><tr><td>1991</td><td>Summer</td><td>North of northern Shaanxi</td></tr><tr><td>1994</td><td>Winter</td><td>Part of Weinan</td></tr><tr><td>1995</td><td>Summer</td><td>South of northern Shaanxi and north of Guanzhong</td></tr><tr><td>1999</td><td>Summer</td><td>North of Guanzhong</td></tr><tr><td>2000</td><td> Summer</td><td>North of Guanzhong</td></tr><tr><td>2001</td><td>Summer</td><td>Yulin</td></tr><tr><td>2002</td><td> Summer</td><td>Tongchuan, south of Yan'an and Yulin</td></tr><tr><td>2008</td><td>Winter</td><td>Tongchuan, Xianyang and Weinan</td></tr><tr><td>2011</td><td>Summer</td><td>Guanzhong and parts of northern Shaanxi</td></tr></table></body></html>

Frequencies of severe and exceptional drought in Shaanxi Province from 1979 to 2016 are shown in Table 5. The rank of drought frequency on different scales was as follows: summer>spring>annual>autumn; however, the discrepancies between different scales were not significant. From Figure 4 and Table 5 we can conclude that, drought occurred most frequently and seriously in summer, followed by spring. Southeast of Guanzhong and northwest of southern Shaanxi were the most sensitive areas to the impact of drought with the highest CDI value and the largest drought area in spring and summer and on an annual scale. In addition, eastern Yulin, southern Yan'an and Hanzhong were also likely to be affected in summer and autumn.

Table 5Frequencies of severe and exceptional drought (SPEI-ITPCAS lower than $- 1 . 0 \dot { }$ ）andregionswith high cumulative drought intensity (CDI) values on seasonal and annual scales in Shaanxi Province   

<html><body><table><tr><td>Season/annual scale</td><td>Severe and exceptional drought (times)</td><td>Regionswith high CDI values</td></tr><tr><td> Spring</td><td>12,331</td><td>Part of Hanhong (A1), ih an (A),ofiabout 50 km2; put2of Shkamluo,</td></tr><tr><td> Summer</td><td>12.937</td><td>Part of Yulin (B1) xitha a2) aof aout 820 km2; partof Shangluo,</td></tr><tr><td> Autumn</td><td>11,860</td><td>Part of Yan'an (C1), with an area of about 1Oo0 km²; part of Hanzhong (C2),with anarea of about 700 km²</td></tr><tr><td>Annual</td><td>12,250</td><td>Part of Yulin (E1),with an area of about 44O km²; part of Shangluo (E2), withanarea of about 490km²</td></tr></table></body></html>

Note: A1,A2, B1, B2, C1, C2, E1 and E2 are depicted in Figure 4.

# 3.3MK test of precipitation, temperature and SPEI-ITPCAS

As shown in Figures 5 and 6, temperature presented a significant increasing trend $( Z 2 1 . 2 8 )$ in most regions of Shaanxi Province on seasonal and annual scales. Only part of Ankang showed an insignificant decreasing trend $( - 1 . 2 8 { \le } Z { \le } 0 . 0 0 )$ in summer, autumn and winter. However, the significance and variation trend of precipitation and SPEI-ITPCAS in MK test varied in most regions of Shaanxi Province on the seasonal scale. Tables 6 and 7 showed the significance and variation trends of precipitation and SPEI-ITPCAS on seasonal and annual scales in Shaanxi Province, respectively. In spring, the upward trend of precipitation occurred in most regions of Shaanxi Province, except for parts of Guanzhong. Moreover, the temperature showed a significant upward trend at $9 9 \%$ confidence level. The SPEI-ITPCAS showed a drying trend in most regions of Shaanxi Province, except for part of southern Shaanxi. The variation trends of SPEI-ITPCAS and precipitation were opposite in most regions, which indicated that the abnormal increase of temperature dominated meteorological processes, leading to a drying trend in most regions.

In summer, the downward trend of precipitation together with the significant upward trend of temperature led to a general drying trend in most regions of Shaanxi Province. This drying trend was especially significant in parts of Yan'an and Guanzhong,and west of southern Shaanxi. Almost all of the five APCs in Guanzhong showed a significant drying trend. The situation was consistent with historical drought records, which indicated that drought in spring and summer was quite serious in Guanzhong and northern Shaanxi (Zhai, 2005).

In autumn and winter, the significant upward trend of precipitation mainly occurred in northern Shaanxi, while the downward trend mainly occurred in Guanzhong and southern Shaanxi. The temperature showed a significant upward trend in all regions. The variation trends of SPEI-ITPCAS reflected a composite interaction of precipitation and temperature with remarkable spatial heterogeneity in Shaanxi Province. In conclusion, we found a significant wetting trend in northern Shaanxi and a significant drying trend in parts of Xi'an, Weinan, Hanzhong and Ankang.

The variation trends of precipitation and temperature in northern Shaanxi, Guanzhong and southern Shaanxi on an annual scale were similar with those on autumn and winter scales. The weting trend in northern Shaanxi was less significant than the upward trend of precipitation, and the drying trends in Guanzhong and southern Shaanxi were more significant than the downward trend of precipitation on an annual scale. The phenomena showed that the significant upward trend of temperature in Shaanxi Province counteracted the upward trend of precipitation (leading to a less significant weting trend in northern Shaanxi) and interacted with the downward trend of precipitation (leading to a more significant drying trend in Guanzhong and southern Shaanxi).

Precipitation Temperature SPEI-ITPCAS   
Z106E108E110E Z106E108E110E Z106E108E110E   
400 (a1) 0 (a2) 40(a3） N00   
389 Yulin No8 N8 No88 Ls2s MN   
N98 Yan'an N9 Yan' N9 Yan'an N99 Fongo   
3040 N0t Nte Baoji 2000 Shangluo Hanzhong   
320 220 200 220   
N004 106 108E110E 1062E108°E110E 2106E108°E 110E No04   
N088 N88 N88 Yulin N080 八 点 ar   
N99 N9 Yan' N98 290   
3000 GXian.s N0 25 N000 hanglu   
200 20 200 Anka 220   
N000 10 108°E110E 1062E 108%E 110E 108°E 110°E No0t   
N88 N88 N8 N8   
N99 N9 N9 an'an N.9 fung   
200 aoji No0 200 N0 Shanglu S5   
320 200 220 220   
N004 106°E 108°E110E 106E108%E110E 16E 108E 110E No0t   
N89 No88 No88 N88   
290 N9 N9 N9   
2000 N000 N00 Baoji N0 了   
320 3 200 220 106E108E110°E 106E108E110E 106E108E110E Legend Z value of MK test 0 200 400 km 一 $< - 2 . 3 2$ ■ -2.32--1.64-1.64--1.28-1.28-0.00 0.00-1.28 1.28-1.64 1.64-2.32 >2.32 Approved No.陕S(2020)018   
z106E 4 (a)Precipitation 108E 110E (b) Temperature 108E 110E (c) SPEI-ITPCAS 108E 110°E N00   
N88 N080 Yulin N.88 Yulin 3.8g A   
N9 Y N090 Yan'an N98 Yan'an 3.90   
350 Baojiy G N05 204 G 340 Shangluo shangluc Shangluo Hanzhong S Hanzhong Hanzhon   
320 3Ankang 320 32M 3Ankang 3220 106°E 108E 110E 106°E 108°E 110E 106°E 108E 110E   
Legend   
Z value of MK test 0 200 400 km <-2.32 -2.32- -1.64 -1.64- -1.28 -1.28-0.00 0.00-1.28 1.28-1.64 1.64-2.32 >2.32 Approved No.陕S (2020) 018

Table 6Significance and trend of precipitation in Mann-Kendall(MK) test on seasonal and annual scales in Shaanxi Province   

<html><body><table><tr><td>Season/annual scale</td><td> Z value</td><td>Trend</td><td>Regions</td></tr><tr><td>Spring</td><td>Z≥0.00</td><td>Upward</td><td>All of Shaanxi Province except for Xi'an and Weinan</td></tr><tr><td rowspan="5"></td><td>Z≥1.28</td><td>Upward*</td><td>Parts of Yulin and Ankang</td></tr><tr><td>Z≤0.00</td><td>Downward</td><td>Xi'an and Weinan</td></tr><tr><td>Z≤ -1.28</td><td>Downward*</td><td>Partsof Xi'an and Weinan</td></tr><tr><td>Z≥0.00</td><td> Upward</td><td>Tongchuan and parts of Yulin and Yan'an</td></tr><tr><td>Z≥1.28</td><td>Upward*</td><td></td></tr><tr><td rowspan="5"> Autumn</td><td>Z≤0.00</td><td>Downward</td><td>Parts of northern Shaanxi, Guanzhong (except for Tongchuan) and southern Shaanxi</td></tr><tr><td>Z≤ -1.28</td><td>Downward*</td><td>Parts of Baoji, Hanzhong and Weinan</td></tr><tr><td>Z≥0.00</td><td> Upward</td><td>Al f ani Pre f ats f ia xia</td></tr><tr><td>Z≥1.28</td><td>Upward*</td><td>Yulin and Yan'an</td></tr><tr><td>Z≤0.00</td><td>Downward</td><td>Parts of Weinan, Xi'an, Shangluo and Ankang</td></tr><tr><td rowspan="4">Winter</td><td>Z≤ -1.28</td><td>Downward*</td><td>Parts of Xi'an and Ankang</td></tr><tr><td>Z≥0.00</td><td> Upward</td><td>AllfSa Preetsofeai</td></tr><tr><td>Z≥1.28</td><td>Upward*</td><td>Yulin, Yan'an, and parts of Tongchuan, Xianyang and Baoji</td></tr><tr><td>Z≤0.00</td><td>Downward</td><td>Parts of Weinan, Xi'an, Ankang and Hanzhong</td></tr><tr><td rowspan="5">Annual</td><td>Z≤ -1.28</td><td>Downward*</td><td> Parts of Xi'an and Ankang</td></tr><tr><td>Z≥0.00</td><td>Upward</td><td>Northern Shaanxi, parts of Guanzhong and southern Shaanxi</td></tr><tr><td>Z≥1.28</td><td>Upward*</td><td>Parts of Yulin, Yan'an and Tongchuan</td></tr><tr><td>Z≤0.00</td><td>Downward</td><td>Parts of Guanzhong and southern Shaanxi</td></tr><tr><td>Z≤ -1.28</td><td>Downward*</td><td>Partsof Baoji,Xi'an and Weinan</td></tr></table></body></html>

Note: \*means that the confidence level of trend isabove $90 \%$

# 3.4Temporal ranges for mutations of SPEI-ITPCAS on seasonal and annual scales

As shown in Figure 7, the temporal ranges for mutations of SPEI-ITPCAS can be notably discerned on seasonal and annual scales in Shaanxi Province. For example, mutations of SPEI-ITPCAS occurred during the period of 199O-2O00 in west of Shaanxi Province and east of Guanzhong in spring (Fig. 7a). In summer, they occurred during the period of 1990-200O in west and middle of Guanzhong (Fig. 7b). In autumn, they appeared after the year 2OOO in north of northern Shaanxi (Fig. 6c). In winter, they occurred after the year 2OOO in east and middle of Guanzhong and in parts of southern Shaanxi (Fig. 7d). On an annual scale, mutations of SPEI-ITPCAS occurred during the period of 1990-2000 in west and middle of Guanzhong,and after the year 2000 in parts of northern Shaanxi (Fig. 7e). In conclusion, the regional and temporal ranges for mutations of SPEI-ITPCAS differed on seasonal and annual scales, and most mutations happened before the year 1990. As Shaanxi Province has three types of terrain with comparably diverse climates (i.e., cold and arid plateau in the north, mild plain in the middle, and wet and warm mountainous regions in the south), the regional responses to climate change varied. The discrepancies of temporal ranges for mutations of SPEI-ITPCAS indicated that the responses of the three sub-regions (northern Shaanxi, Guanzhong and southern Shaanxi) to climate change may be quite different.

Table 7Significance and trend of SPEI-ITPCAS in MK test on seasonal and annual scales in Shaanxi Province   

<html><body><table><tr><td>Season/annual</td><td>Z value</td><td>Trend</td><td>Regions</td></tr><tr><td rowspan="3"> Spring</td><td>Z≥0.00</td><td>Wetting</td><td>Parts of southern Shaanxi and Baoji</td></tr><tr><td>Z≥1.28</td><td>Wetting*</td><td>Parts of Ankang</td></tr><tr><td>Z≤0.00</td><td>Drying</td><td>All of Shaanxi Province except for parts of southern Shaanxi and Baoji</td></tr><tr><td rowspan="4">Summer</td><td>Z≤-1.28</td><td>Drying*</td><td>Part of Yulin, Yan'an, and middle and east of Guanzhong</td></tr><tr><td>Z≥0.00</td><td>Wetting</td><td>Partsof Tongchuanand south of Yan'an</td></tr><tr><td>Z≥1.28</td><td>Wetting*</td><td></td></tr><tr><td>Z≤0.00</td><td>Drying</td><td>All of Shaanxi Province except for parts of Tongchuan and south of Yan'an</td></tr><tr><td rowspan="4"> Autumn</td><td>Z≤-1.28</td><td>Drying*</td><td>West of southern Shaanxi, and parts of Yan'an and Guanzhong</td></tr><tr><td>Z≥0.00</td><td>Wetting</td><td>Northern Shaanxi, west and north of Guanzhong,and east of Hanzhong</td></tr><tr><td>Z≥1.28</td><td>Wetting*</td><td>Yulin and north of Yan'an</td></tr><tr><td>Z≤0.00</td><td>Drying</td><td>Middle and eastern parts of Guanzhong and southern Shaanxi</td></tr><tr><td rowspan="4">Winter</td><td>Z≤ -1.28</td><td>Drying*</td><td>Parts of Xi'an and Ankang</td></tr><tr><td>Z≥0.00</td><td>Wetting</td><td>Northern Shaanxi,and parts of Gaunzhong and southern Shaanxi</td></tr><tr><td>Z≥1.28</td><td>Wetting*</td><td>Northern Shaanxi, and parts of Gaunzhong and southern Shaanxi</td></tr><tr><td>Z≤0.00</td><td>Drying</td><td>Parts of Xi'an, Weinan, Hanzhong and Ankang</td></tr><tr><td rowspan="5"> Annual</td><td>Z≤ -1.28</td><td>Drying*</td><td>Parts of Xi'an, Weinan, Hanzhong and Ankang</td></tr><tr><td>Z≥0.00</td><td>Wetting</td><td>Yulin, and parts of Yan'an, Tongchuan and Xianyang</td></tr><tr><td>Z≥1.28</td><td>Wetting*</td><td></td></tr><tr><td>Z≤0.00</td><td>Drying</td><td>Allfi </td></tr><tr><td>Z≤-1.28</td><td>Drying*</td><td>Parts of Guanzhong, Hanzhong and Ankang</td></tr></table></body></html>

Note:\*means that the confidence level of trend is above $90 \%$

![](images/ca6ef890b3d92dcb7ab131aba9bb8e21ec743e819c90f5f9ad95d56fa364411b.jpg)  
Fig.7Temporal ranges for mutations of SPEI-ITPCAS in spring (a), summer (b),autumn (c)and winter (d),and on an annual scale (e) in Shaanxi Province.The two blue lines are the northern and southern boundaries of Guanzhong.

# 4Discussion

# 4.1Meteorological data with high spatial-temporal resolution

Validation of SPEI-OMS and SPEI-ITPCAS has proved that meteorological datasets with high spatial-temporal resolution can better reflect the characteristics of drought in regions with complex climate than OMS. Thus, comprehensive evaluations of the existing meteorological datasets in drought monitoring are necessary. Vicente-Serrano et al. (2O1Ob) has proposed a worldwide drought index dataset based on SPEI calculated with $0 . 5 ^ { \circ }$ net CDF reanalysis data. However, it is too coarse for drought monitoring at the provincial scale. ITPCAS, TRMM and CMORPH-PDF (CMORPH calibrated by probability density function matching and optimal interpolation method) are commonly used for provincial drought analysis in China (Tian and Li, 2O15; Lu et al., 2018). ITPCAS has a higher spatial resolution than TRMM and a longer time range than CMORPH. Moreover, numerous studies have shown the superior performance of ITPCAS in predicting precipitation in hydrological simulations in China (Guo and Wang, 2013; He et al., 2O15). Kan et al. (2013) pointed out that the accuracy of spatial distribution of precipitation data derived from ITPCAS for western China was better than those of TRMM Multi-satellite Precipitation Analysis (TMPA3B42V6) and CMORPH. In the future， we will downscale ITPCAS with auxiliary environmental factors to finer resolution so that the spatial-temporal characteristics of drought can be better identified even more precisely.

# 4.2Assessment of SPEI

According to the algorithms of SPEI, the accuracy of SPEI depends on the following thre factors: (1) accuracy of precipitation data; (2) accuracy of calculated PET; and (3) option of probability density function to fit water deficit or surplus. Precipitation from ITPCAS has been proved to be effective in modelling applications (Wang et al., 2O18). Many scholars have verified that the loglogistic function, which is a probability density function and is used for calculating the SPEI, fits well the distribution of water surplus (Begueria et al., 2O14; Yang et al., 2O16). Therefore, the algorithms used for calculating the PET, including PM equation and Th method, need further evaluation. The error of PET calculated by Th method has been shown to be high in winter (Duan et al., 2013; Parsons et al., 2O19). Figure 4d showed that in Shaanxi Province, the CDI value on the winter scale was abnormally higher than those on other seasonal and annual scales. This anomaly happened because low temperature in winter caused errors in the calculation of PET by Th method. Thus, estimates of PET in winter calculated by Th method need to be adjusted.

# 4.3Adjustments of Th method in winter

Figures 2 and 4d and Table 3 showed that drought areas in winter detected by SPEI-ITPCAS were relatively consistent with the historical drought records, while the CDI in winter was abnormal, indicating that Th method tended to overestimate the intensity of drought in winter. Tsakiris et al. (2007) proposed that the ratio of precipitation to potential evapotranspiration (briefly, P/PET) can be used as an appropriate drought index and as a way to distinguish arid and humid regions (Paulo et al., 2012). Because arid and humid regions are relatively stable, PET calculated by Th method in winter can be adjusted by P/PET values.

# 5 Conclusions

In this study, temperature and precipitation data were extracted from ITPCAS to calculate SPEI, and the calculation results were then validated by historical drought records. Spatial-temporal characteristics of drought on seasonal and annual scales in Shaanxi Province during the period of 1979-2016 were analyzed by SPEI-ITPCAS. Results showed that SPEI-ITPCAS was superior to SPEI-OMS in detecting drought areas of Shaanxi Province on seasonal and annual scales. The rank of drought frequency on different scales was as follows: summer>spring>annual>autumn. The CDI values in Shaanxi Province during the period of 1979-2O16 were different on seasonal and annual scales. In spring and summer, there was a general drying trend in most regions of Shaanxi Province while a significant drying trend in Weinan and Xi'an. In autumn and winter, there was a significant wetting trend in northern Shaanxi while a drying trend in other regions.Mutations of SPEI-ITPCAS occurred before the year 1990 in most regions of Shaanxi Province on different time scales.

# Acknowledgements

This study was supported by the National Natural Science Foundation of China (41871307) and the Shaanxi Coordinate Innovation Plan Project of Science and Technology (2016KTCL03-17).

# References

Ahmad I,TangDS,WangTF,etal.2O15.Precipitationtrendsover time using Mann-Kendallandspearman'sotests iSwat River Basin, Pakistan.Advances in Meteorology,2015: 431860,doi: https:/doi.org/10.1155/2015/431860.   
AllenKJ,OgdenJuckleyB,etal.l1.epotetialtoeostructbadscalecimateidiceassiateditoast Australian droughts from Athrotaxis species,Tasmania. Climate Dynamics,37(9-10): 1799-1821.   
AllenR,SmithM,erreA,etal.1994.Audatefor theefiiionofrefrenceevapotranspirationICIbulletin,4(2):1- 34.   
BegueriaS,Vicente-SerranoSM,ReigFetal.2O14.Standardizedprecipitationevapotranspirationindex (SPEvisied: parameter fiting,evapotranspiration models,tools,datasetsand drought monitoring.InternationalJournalofClimatology, 34(10): 3001-3023.   
ChangnonSA,EasterlingWE.1989.Measuringdroughtimpacts:theilinoiscase.Jawra JournaloftheAmerican Water Resources Association, 25(1): 27-42.   
Chen YY, Yang K,HeJ,etal.2O11.Improvinglandsurface temperaturemodelingfordrylandofChina.JournalofGeophysical Research-Atmospheres,116(D20): 12-20.   
Dai AG.2011.Characteristicsand trends invarious formsofthePalmerDrought Severity Index during1900-2008.Journalof Geophysical Research-Atmospheres,116(D12): 1248-1256.   
DuanY,Wang W,Cai XJ.2O13.Applied analysesonPalmer,SPEIand CIindicesof DroughtProcessinYangtze-HuaiheRiver Basins during Winter of 2010/Spring of 2011.Plateau Meterology,32(4): 1126-1139. (in Chinese)   
Gobena AK, Gan TY.2O13. Asessment of trendsand possible climatechange impacts onsummer moisture availability in western Canadabased on metrics of the Palmer Drought Severity Index.Journal of Climate,26(13): 4583-4595.   
Goovaerts P.2Oo.Geostatisticalapproaches for incorporating elevation intothespatial interpolationofrainfallJournalof Hydrology, 228(1-2): 113-129.   
GuoDL,WangHJ.2Ol3.SmulationofpermafrostandseasonallyfrozengroundconditionsontheTbetanPlateau,1981-2010. Journal of Geophysical Research-Atmospheres, 118(11): 5216-5230.   
Hannaford J,Lloyd-Hughes B,Kef C,et al.201.Examining the large-scale spatial coherenceofEuropeandroughtusing regional indicators of precipitation and streamflow deficit. Hydrological Processes,25(7): 1146-1162.   
He B,LuAF,WuJJ,etal2l1.Doughthaardsesmntandspatialchracteristicsanalyis inCina.Joualofoaical Sciences,21(2):235-249.   
HeS W,NanZT,ZhangL,etal.2015.Spatial-temporaldistributionof waterandenergyfluxesintheupperreachesofthe Heihe River simulated with VIC model. Journal of Glaciology and Geocryology,37(1): 211-225. (in Chinese)   
Jia J,Wang Q,LiLH016.Long-termoscilationofdroughtconditionsinthe westernChna:ananalysisofPDSIonadecadal scale. Journal of Arid Land, 8(6): 819-831.   
JiangRG,XieJC,HeHL,etal.2O15.Useoffourdrought indicesforevaluatingdroughtcharacteristicsunderclimatechange in Shaanxi, China: 1951-2012. Natural Hazards,75(3): 2885-2903.   
Kan BY,SuFG,Tong K,et al.2013.Analysisof the applicabilityoffourprecipitationdatasets intheupperreaches of the Yarkant River, the Karakorum. Journal of Glaciology and Geocryology,35(3): 710-722. (in Chinese)   
Kendall M G. 1975. Rank Correlation Methods. London: Charles Griffin, 200-202.   
KimT W,Valdes JB,Aparicio J.2O02.Frequencyand spatial characteristicsof droughts in theConchos River Basin,Mexico. Water International, 27(3): 420-430   
KoganF,AdamenkoT,GuoW.20l3.Globalandregionaldroughtdynamics inthecimatewarming era.RemoteSensingLters, 4(4): 364-372.   
Liu CR,Chen H,Ning C,et al.2018.Analysis ofdrought characteristics in Shaanxi Provice during1961-2016 based on SPI Acta Agriculturae Jiangxi, 30(4): 117-122. (in Chinese)   
Liu WL,ZhangMJ,WangSJ,etal.2O13.Changes inprecipitationextremesoverShaanxiProvince,northwesternChina,during 1960-2011. Quaternary International, 313-314: 118-129.   
Liu Y, Yang XL,RenLL,etal.2O15.Anew physicallbased self-calibratingpalmerdroughtseverity index andits prforance evaluation. Water Resources Management, 29(13): 4833-4847.   
Liu YF, YuanZH,Feng JM,et al.2O16.Dry-wet conditionof Shaanxi Provinceinrecent56 years basedonsurfacehumidity index. Arid Land Geography, 39(6): 1186-1196. (in Chinese)   
Loukas A,VasiliadesL,TzabirasJ.2oo8.Climatechange effectsondroughtseverity.Advances inGeosciences,17:23-29.   
LuJ,JiaL,MenentiM,etal.2O18.Performanceofthestandardized precipitation index basedontheTMPAandCMORPH precipitation products for drought monitoring in China.IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, 11(5): 1387-1396.   
Ma M W,RenLY,Singh VP,etal.2015.Evaluationand applicationof the SPDI-JDIfordroughts inTexas,USA.Jouralof Hydrology, 521: 34-45.   
Mann H B. 1945. Nonparametric tests against trend. Econometrico,13(3): 245-259.   
Meza FJ.2013.Recent trendsand ENSO influenceon droughts in Northern Chile:Anapplicationof the Standardized Precipitation Evapotranspiration Index. Weather & Climate Extremes,1(1): 51-58.   
Naumann G,DutraE,Barbosa P,et al. 2014. Comparisonof drought indicators derived from multiple data sets over Africa. Hydrology and Earth System Sciences,18(18): 1625-1640.   
PandeyR P, Ramasastri K S. 2010.Relationship between the common climatic parameters and average drought frequency. Hydrological Processes,15(6): 1019-1032.   
Parsons DJ,ReyD,Tanguy M,et al.2O19.Regional variations inthe link btween drought indicesandreported agricultural impacts of drought. Agricultural Systems,173: 119-129.   
Paulo AA,Rosa R D,Pereira L S.2012. Climate trendsand behaviour of drought indices basedon precipitation and evapotranspiration in Portugal. Natural Hazards and Earth System Sciences,12(5): 1481-1491.   
QiaoL,ChengK,WuLR,tal.O2.SpatialandemporaldistributionofmeteoroloicaldroughtdisastersinniProince over past 30 year. Bulletin of Soil and Water Conservation, 46(1): 253-256. (in Chinese)   
RheeJ,ImJ.2017.Meteorologicaldrought forecasting forungaugedareas basedonmachine leaning: Usinglong-rangecmate forecast and remote sensing data. Agricultural and Forest Meteorology, 237-238: 105-122.   
Salehnia N,Zare H, Kolsoumi S,etal.2017a.Predictive valueof Ketch-Byram Drought Indexforcereal yields inasm-arid environment. Theoretical & Applied Climatology, 134(3-4): 1005-1014.   
SalehniaN,Alizadeh A,Sanaeinejad H,et al.2017b.Estimationof meteorologicaldrought indices basedon AgMERRA precipitation data and station-observed precipitation data.Journal of Arid Land, 9(6): 797-809.   
SpinoniJ,BarbosaP,deJagerA,etal.2019.Anewglobaldatabaseofmeteorologicaldroughteventsfrom1951to016.Joual of Hydrology: Regional Studies,22(4): 100593-100616.   
Szczesniak M,Piniewski M.2015.Improvementof hydrological simulations byapplying dailyprecipitation interpolation schemes in meso-scale catchments. Water, 7(2): 747-779.   
Thornthwaite C W.1937. Microclimatic studies in Oklahoma and Ohio. Science,86(2222): 100-101.   
Tian M,Li WG.2015.Analysis of spatialand temporal characteristicsof drought and flood basedonTRMMremote sensing data. Transactions of the Chinese Society for Agricultural Machinery, 46(5): 252-257. (in Chinese)   
Tsakiris G,PangalouD,Vangelis H.2Oo7.Regional droughtassssment basedontheReconnaissanceDrought Index (DI). Water Resources Management,21(5): 821-833.   
Vasiliades L,Loukas A.2009.Hydrologicalresponse to meteorological drought using the Palmer drought indices inThessaly Greece. Desalination,237(1-3): 3-21.   
Vicente-Serrano S M, Begueria S,López-Moreno JI. 201Oa. A multiscalar drought index sensitive to global warming:the Standardized Precipitation Evapotranspiration Index. Journal of Climate, 23(7): 1696-1718.   
Vicente-SerranoSM,BegueriaS,Lpez-MornoJI,etal.2ob.Anewglobal0.5degreesgriddeddataset(90206)ofa multiscalar drought index:comparison with current drought index datasets based on the Palmer Drought Severity Index. Journal of Hydrometeorology, 11(4): 1033-1043.   
Vicente-SerranoSM,Begueria S,Lpez-MorenoJI.20.Commenton "characteristicsand trendsinvarious forsof the Palmer Drought Severity Index (PDSI) during 1900-2008"by Aiguo Dai. Journal of Geophysical Research-Atmospheres, 116(D19): 4-13.   
Wan XJ,RenZY,ZhangC.013.Resarchonspatial-temporaldistributionof temperatureandprecipitationchangesinSani. Journal of Arid Land Resourcesand Environment, 27(6): 140-147. (in Chinese)   
WangF,WangZM,YangHB,etal.2O18.Studyof thetemporalandspatialpaternsofdroughtintheYellowRiverbasinbased on SPEI. Science China Earth Sciences,61(8): 1098-1111.   
WangXY,ZhuoL,LiC,etal.019.TmporalandspatialevolutiontrendsofdroughtinorthernSaaniofChina:1960-100. Theoretical and Applied Climatology,139(3-4): 965-979.   
WangYD,ChenH,LiuCR,etal.2018.ApplicabilityofITPCASandCMORPH precipitationdatasetsover Shaanxi Province. Arid Zone Research,35(3): 579-588. (in Chinese)   
Wang Z,Guan K Y,SheffeldJ,etal. 2O16.Depictionof drought over sub-Saharan Africa using reanalyses precipitation data sets. Journal of Geophysical Research Atmospheres,121(18): 10555-10574.   
Wells N,GoddardS,HayesMJ.204.Aself-calibratingPalmerDroughtSeverityIndex.JoualofClimate,17(12):235-2351.   
XueBL,WangL,YangK,etal.O13.Mdelingthelandsurface waterandenergycyclesofamesoscale watershedintheentral Tibetan Plateau during summer withadistributedhydrologicalmodel.Journalof GeophysicalResearch-Atmospheres,18(16): 8857-8868.   
Yang MJ,YanDH,YuYD,etal.2016.SPEI-based spatiotemporalanalysisofdroughtinHaiheRiver Basinfrom1961to2010. Advances in Meteorology, 2016: 7658015, doi: 10.1155/2016/7658015.   
YangQ,LiMX,ZhngZY,etal.217Regioalaplicabilityofsevenmeteorologcaldroughtindicesinia.SienceChina Earth Sciences. 60(4): 745-760.   
YuFK,Huang XH,Liang QB,etal.2015.Ecologicalwaterdemandofregionalvegetation:the exampleof the2O1severe drought insouthwest China.PlantBiosystems-An InternationalJouralDealingwithallAspectsofPlant Biology,149(1): 100-110.   
Yu M X,Li QF,Hayes MJ,et al. 2014. Are droughts becoming more frequent or severe in China based on the Standardized Precipitation Evapotranspiration Index: 1951-2010? International Journal of Climatology,34(3): 545-558.   
YuanF,Ma MW,RenLL,etal.2O15.Posiblefutureclimatechangeimpactsonthehydrologicaldrought events inthe Weihe River Basin, China. Advances in Meteorology,2016: 2905198,doi: htps://doi.org/10.1155/2016/2905198.   
ZhaiYA.20o5.China MeteorologicalDisasterCanon-Shaanxi Volume.Beijing: Meteorological Press,30-41.(inChinese)   
Zhang R,Chen ZY,XuLJ,etal.2019.Meteorological droughtforecasting basedona statistical model withmachine learning techniques in Shaanxi Province, China. Science of the Total Environment, 665: 338-346.   
Zhang X S,Srinivasan R.20o9. GIS-Based spatial precipitation estimation:Acomparisonof geostatisticalapproaches.Joual of the American Water Resources Association, 45(4): 894-906.