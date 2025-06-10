# Spatiotemporal changes of eco-environmental quality based on remote sensing-based ecological index in the Hotan Oasis, Xinjiang

YAO Kaixuan1,2, Abudureheman HALIKE1.2.3\*, CHEN Limei1,2, WEI Qianqian1.2

1 College of Geographical Science, Xinjiang University, Urumqi 83o017, China;   
2 Xinjiang KeyLaboratory ofOasis Ecology, Xinjiang University, Urumqi 830ol7,China;   
3KeyLaboratoryofSmartCityandEnvironmentModelingofHigherEducation Institute,XinjiangUniversity,Urumqi830017, China

Abstract: The rapid economic development that the Hotan Oasis in Xinjiang Uygur Autonomous Region, China has undergone in recent years may face some challenges in its ecological environment.Therefore, an analysis of the spatiotemporal changes in ecological environment of the Hotan Oasis is important for its sustainable development.First,we constructed an improved remote sensing-based ecological index (RSEI) in 1990,1995,2000,2005,2010,2015 and 2020 on the Go0gle Earth Engine (GEE) platform and implemented change detection for their spatial distribution. Second，we performed a spatial autocorrelation analysis on RSEI distribution map and used land-use and land-cover change (LUCC) data to analyze the reasons of RSEI changes.Finaly, we investigated the applicability of improved RSEI to arid area. The results showed that mean of RSEI rose from O.41 to O.50,showing a slight upward trend. During the 30-a period, $2 . 6 6 \%$ of the regions improved significantly, $10 . 7 4 \%$ improved moderately and $3 2 . 2 1 \%$ improved slightly, respectively. The global Moran's $I$ were 0.891, 0.889, 0.847 and 0.777 for 1990, 2000,2010 and 2020,respectively,and the local indicators of spatial autocorrelation (LISA) distribution map showed that the high-high cluster was mainly distributed in the central part of the Hotan Oasis, and thelow-low cluster was mainly distributed in the outer edge of the oasis.RSEI at the periphery of the Oasis changes from low to high with time, with the fragmentation of RSEI distribution within the oasis increasing. Its distribution and changes are predominantly driven by anthropologic factors,including the expansion of artificial oasis into the desert,the replacement of desert ecosystems by farmland ecosystems, and the increase in the distribution of impervious surfaces.The improved RSEI can reflect the eco-environmental quality effectively of the oasis inarid area with relatively high applicability.The high efficiency exhibited with this approach makes it convenient for rapid, high frequency and macroscopic monitoring of eco-environmental quality in study area.

Keywords:remote sensing-based ecological index；Google Earth Engine;spatial autocorrelationanalysis; eco-environmental quality; arid area

Citation:YAO Kaixuan，Abudureheman HALIKE，CHEN Limei，WEI Qianqian．2022.Spatiotemporal changesof eco-environmentalqualitybasedonremotesensing-basedecologicalindexintheHotanOasis,Xinjiang.JournalofAridLand, 14(3):262-283.https://doi.0rg/10.1007/s40333-022-0011-2

# 1Introduction

An oasis is an important part of arid area,and its ecology is relatively independent and fragile (Liu et al.，2O18). As a relatively independent geographical unit,an oasis is the carrier of anthropological socioeconomic activities in arid areas and has a positive regulatory efect on local climate,water resources and ecosystem (Hao et al., 2O19). Hotan Oasis is a piedmont oasis with limited natural resources such as water, fragile ecology, prominent environmental constraints and resource consumption problems in a typical arid area, Xinjiang Uygur Autonomous Region, China (Wang et al.，2O2O).Additionally， the proportion of agricultural land has increased substantially since 2O1O (Dong et al.,2O19),causing the edge of the oasis to advance considerably toward the desert. The extent of expansion can be estimated visually from satellite images. Balancing socioeconomic development and ecological environment is key to the sustainability of oasis development. Therefore, monitoring the distribution and changes of ecological environment of the oasis in a timely and rapid manner is particularly important.

A combination of remote sensing spatial information technology and geoinformation technology for spatial observation and analysis,which has the unique advantages of update quickly and wide range, is widely used in ecological environment monitoring (Yu et al., 2014). Furthermore, many researchers have developed spectral algorithms or indices that are closely related to ecological environment. For example,the normalized diference vegetation index (NDVI) is widely used in various ecological studies (Cao et al., 2018; Chu et al.,2019; Hassan et al.,2019; Fung and Siu,2OOO). Leaf area index (LAI) is used to reflect the number of plant leaves, canopy structure changes,vitality of plant communities and environmental effects (Fang et al., 2019; Kganyago et al.,2O2O). Land surface temperature (LST) is used to study the effects of the ecological environment and temperature,such as the impact of urban heat islands on an urban ecological environment (Alexander， 202O； Zhao et al.， 202O). Other indicators used to characterize ecological environment include enhanced vegetation index (EVI） to correct soil background and atmospheric noise aspects (Wang et al., 2Oo3), hyperspectral flower index (HFI) to assess flower cover in the flowering state (Chen et al.，2Oo9),normalized difference water index (NDWI; Magruder et al.,2O19) and modified normalized diference water index (MNDWI; Xu, 2005) that reflect the moisture status of ecological environment. The abovementioned indices are all refined single indicators for a certain field with a complex ecological environment. The use of single indicators to represent the overall change in the quality of ecological environment would be insufficient.

Many multifactor indicators based on remote sensing have been proposed to represent complex ecological environment. As ecological environment is monitored using multiple indicators from different aspects,the use of multiple factors is more advantageous than the application of single factor (Xu et al., 2019). For example, ecological environmental status index (EI),which uses biological abundance,vegetation coverage，water network density and other indicators to comprehensively evaluate and systematically analyze ecological environment, is widely used to evaluate ecological environment-carrying capacity (Zhu et al., 2O17). The synthesized drought index (SDI; Li et al.，2O2O)， scaled drought condition index (SDCI； Rhee et al.，2010） and improved optimal scaled drought condition index (OSDCI； Guo et al.，2O19） are used for large-scale drought monitoring using precipitation, temperature and vegetation health conditions as input variables. The moderate resolution imaging spectrometer (MODIS） global disturbance index (MGDI)，which uses LST and EVI as input variables,is also used to monitor the disturbance of forest ecosystems (Mildrexler et al.,2Oo9).However, although these multifactor indices can reflect the quality of ecological environment in the study area,obtaining each of these variables may be challenging,and the weight of each factor needs to be determined repeatedly by experiments.In addition，when applied to different study areas,the weights differ (Xu et al., 2019). In the remote sensing-based ecological index (RSEI) proposed by Xu (2O13), he calculated four single indicators (greenness, wetness, dryness and temperature, which are closely related to ecological environment） based on land satelite imagery and coupled into a comprehensive index by principal component analysis (PCA). This model has been proven, many times,to be credible and reliable at reflecting the quality of regional ecological environment. For example,results showed that the overall wetland eco-environmental quality is closely related to the proportion of humidity in RSEI (Jing et al., 2O20). RSEI was used to predict the impact of potential increase in population and impervious surfaces on ecological environment (Xu et al. 2O18),and discuss the spatiotemporal evolution of ecological quality of island under different urban densities (Liu et al., 2021).

The aforementioned research on RSEI usually focuses on wet monsoon areas or densely populated cities；however, the Hotan Oasis is a typical oasis in an arid area. Ecological environment is characterized by high potential evaporation and relatively few water resources. Therefore, we attempted to make the following improvements to explore the applicability of RSEI to arid area. As farmland is the mainly land type in the Hotan Oasis,we kept the following two indicators: greenness and humidity. The proportion of urban impervious surface distribution in the Hotan Oasis is relatively small however, it includes a large expanse of bare land and desert.For the dryness index，we removed the original index-based building index (IBI) from RSEI and retained the bare soil index (BSI), which is sensitive to bare land and desert.The salinity index is more sensitive to reflect the degree of salinization of dry land surface,therefore we replaced original heat index with it. Thus,the aforementioned remote sensing indices of greenness, humidity, dryness and salinity, which reflect the macro eco-environmental quality of arid area,are re-combined via PCA to forma new RSEI for arid area.

![](images/932dcaad9f9541d9a36a77571dbec577996ec888d956f84daa10326f565432c0.jpg)  
Fig.1Workflow of the study. GEE,Google Earth Engine; NDVI, normalized diference vegetation index; WET, wetness; BSI,baresoil index; SI,salinity idex; PCA,principal componentanalysis; RSEI,remotesensing-based ecological index; LUCC,land-use and land-cover change.

However, the use of local computer resources to process the aforementioned data would become increasingly time consuming as the study area increased. This generates many intermediate data processing products that occupy local storage resources. The efficiency of data analysis is greatly limited and does not allow for timely folow-up monitoring and analysis of ecological environment.

Google Earth Engine (GEE) is a cloud computing platform that can batch process remote sensing images and other big data from the earth observations. Owing to its powerful computing capability, GEE can rapidly process multitemporal and large-scale remote sensing data compared with traditional desktop remote sensing image processing software (Mutanga and Kumar, 2019).

We combined the improved RSEI and the GEE platform for the analysis of the temporal and spatial changes in the eco-environmental quality of the Hotan Oasis. The workflow is shown in Figure 1: (1） we used the dataset of Landsat TM,ETM and OLI/TIRS on the GEE platform to construct RSEI; (2) we analyzed the temporal and spatial changes in the eco-environmental quality of the Hotan Oasis in 1990,2000,2010 and 2020; (3)analysis of the spatial correlation of RSEI in different years and revealed the changing trend of its eco-environmental quality； and (4） the distribution of RSEI and the reasons for variation were analyzed using LUCC data.The JavaScript code used to build RSEI in this study is available in the GEE platform，asfollows: https://code.earthengine.google.com/?accept_repo $\ c =$ users/changhorn4616/RSEI.

# 2 Materials and methods

# 2.1 Study area

Hotan Oasis is located at $3 6 ^ { \circ } 3 0 ^ { \prime } \mathrm { N } { - } 3 8 ^ { \circ } 1 5 ^ { \prime } \mathrm { N }$ and $7 9 ^ { \circ } 0 5 ^ { \prime } \mathrm { E } { - } 8 0 ^ { \circ } 4 0 ^ { \prime } \mathrm { E }$ ,and the terrain is dominated by sloping plains with an altitude ranging from 1300 to $1 4 5 0 \mathrm { ~ m ~ a . s . l ~ }$ ，The Yurungkax River and Karakax River pass through the oasis and meet at the lower reaches of the two rivers (Guo et al., 2016). It includes Hotan City, Hotan County, Moyu County, Lop County and Kunyu City. The study area has an arid desert climate,and is windy and sandy with litle precipitation and high potential evaporation (Ding et al., 2020).

Vast deserts and Gobi surround the Hotan Oasis. These land surfaces have almost no vegetation cover,and have not changed significantly over the years. The monitoring and analysis of these deserts are not significant for this study,but can have a huge impact on the overall PCA results. Therefore,a general boundary was drawn between the Hotan Oasis and the surrounding desert through visual interpretation and removed the desert area,leaving a study area of approximately $5 0 0 0 \mathrm { k m } ^ { 2 }$ ,as shown in Figure 2.

# 2.2 Data source and data processing

In 2021, U.S. Geological Survey (USGS) launched a new Landsat Collction 2 Level 2 dataset on theGEEplatform (https://developers.google.com/earth-engine/datasets/catalog/landsat). This dataset contains Landsat surface reflectance and surface temperature bands after orthorectification (Cook et al.， 2014). To beter reflect ecological environment conditions of vegetation growing season in the study area,we selected images with less than $20 \%$ cloud cover from July to August in the above dataset for seven years: 1990,1995,2000,2005,2010,2015 and 2020.Using the cloud removal algorithm provided on the GEE platform, we used the pixel quality band QA_PIXEL to remove clouds and their shadows,and used the median value to synthesize the multilayer image into a good-quality multiband image.To ensure enough quantity and quality of the images,we combined three years of images into one year; for example,the image of 199O is a combination of all images from July to August in 1989,1990 and 1991 with less than $20 \%$ of cloud cover. Owing to the large time scale,the satellites/sensors used in different years and datasets varied. As shown in Table 1,Landsat 5 TM images were selected for 1990,1995 and 2010,Landsat $^ { 7 } \mathrm { E T M + }$ images were selected for 200O and 20O5,and Landsat 8 OLI/TIRS images were selected for 2015 and 2020.

![](images/4e8e2ff2d7e19b0167cb0956a6df1b5bc192b29af5f64473b8f67d0d80e94422.jpg)  
Fig.2Location of the Hotan Oasis

Table 1 Basic information ofLandsat data sources   

<html><body><table><tr><td>Year</td><td>Dataset</td><td>Satellite</td><td>Used band</td><td> Number</td><td>combiation</td><td>Path</td><td>Mont/esloudion</td></tr><tr><td>1990</td><td>LANDSAT/LT05/C02/</td><td>Landsat 5</td><td>SR_B(1,2,3,4,5,</td><td>4</td><td>1989/1990/1991</td><td>146/033</td><td>Jul-Aug</td></tr><tr><td>1995</td><td>T1_L2</td><td>/TM</td><td>7) ST_B6</td><td>14</td><td>1994/1995/1996</td><td>146/034</td><td><20%</td></tr><tr><td>2000</td><td>LANDSAT/LE07/C02/</td><td>Landsat 7</td><td>SR_B(1,2,3,4,5,</td><td>12</td><td>1999/2000/2001</td><td>146/035</td><td>30m</td></tr><tr><td>2005</td><td>T1_L2</td><td>/ETM+</td><td>7) ST_B6</td><td>19</td><td>2004/2005/2006</td><td>147/034</td><td></td></tr><tr><td>2010</td><td>LANDSAT/LT05/C02/ T1_L2</td><td>Landsat 5 /TM</td><td>SR_B(1,2,3,4,5, 7) ST_B6</td><td>13</td><td>2009/2010/2011</td><td>147/035</td><td></td></tr><tr><td>2015</td><td>LANDSAT/LC08/C02/</td><td>Landsat 8</td><td>SR_B (2,3,4,5,6,</td><td>12</td><td>2014/2015/2016</td><td></td><td></td></tr><tr><td>2020</td><td>T1_L2</td><td>/OLI/TIRS</td><td>7) ST_B10</td><td>13</td><td>2019/2020/2021</td><td></td><td></td></tr></table></body></html>

We generated LUCC data using unsupervised classification based on the characteristics of the Hotan Oasis. Socio-economic data were obtained from the Xinjiang Statistical Yearbook during 1993-2020 and the China County Statistical Yearbook during 1993-2020.

# 2.3 Methodology

# 2.3.1 Construction ofRSEI on the GEE platform

This study explored the applicability of the improved RSEI in the Hotan Oasis based on the GEE platform to evaluate the eco-environmental quality of the study area.This index is a composite of four indicators related to the ecological environment of arid area: greenness, wetness,dryness and salinity, which obtained by remote sensing data,and then coupled via PCA; the index is expressed as follows:

(1) Greenness

$$
\mathrm { N D V I } { = } \frac { N - R } { N + R } ,
$$

where $N$ is the near-infrared band of the Landsat data; and $R$ is the red band of the Landsat data.

# (2) Wetness

The wetness index reflects the water content of soil， vegetation and artificial ground. The tasseled cap transformation algorithm can extract corresponding components from an image (Joshi et al.,2O19). In this study, the moisture component of tassel cap transformation as a wetness indicator to reflect the humidity of land surface in the study area.Images from diferent sensors had different coefficients for each band when calculating tassel cap transformation humidity component, which is expressed as follows (Huang et al.,2002; Baig et al., 2014):

$$
+ 0 . 1 5 9 4 \rho _ { \mathrm { N I R } } - 0 . 6 8 0 6 \rho _ { \mathrm { { S W I R 1 } } } - 0 . 6 1 0 9 \rho _ { \mathrm { { S W I R 2 } } } ,
$$

$$
\mathrm { W E T ( E T M + ) } = 0 . 2 6 2 6 \rho _ { \mathrm { b l u e } } + 0 . 2 1 4 1 \rho _ { \mathrm { g r e e n } } + 0 . 0 9 2 6 \rho _ { \mathrm { r e d } }
$$

$$
+ 0 . 0 6 5 6 \rho _ { \mathrm { N I R } } ^ { } - 0 . 7 6 2 9 \rho _ { \mathrm { { S W I R 1 } } } ^ { } - 0 . 5 3 8 8 \rho _ { \mathrm { { S W I R 2 } } } ^ { } ,
$$

$$
\mathrm { W E T ( O L I ) } { = } 0 . 1 5 1 1 \rho _ { \mathrm { b l u e } } { + } 0 . 1 9 7 3 \rho _ { \mathrm { g r e e n } } { + } 0 . 3 2 8 3 \rho _ { \mathrm { r e d } }
$$

$$
+ 0 . 3 4 0 7 \rho _ { \mathrm { N I R } } - 0 . 7 1 1 7 \rho _ { \mathrm { S W I R 1 } } - 0 . 4 5 5 9 \rho _ { \mathrm { S W I R 2 } } ,
$$

where WET(TM), $\mathsf { W E T } ( \mathbf { E T M } + )$ and WET(OLI） are the moisture component of tassel cap transformation of the Landsat TM, $\mathrm { E T M + }$ and OLI images, respectively, and $\rho _ { \mathrm { b l u e } }$ Pgreen, $\rho _ { \mathrm { r e d } }$ $\rho _ { \mathrm { N I R } }$ ， $\rho _ { \mathrm { S W I R 1 } }$ and $\rho$ sWIR2 represent the surface reflectance of blue, green,red, near infrared, shortwave infrared 1 and shortwave infrared 2 bands of the Landsat TM, $\mathrm { E T M + }$ and OLI images, respectively.

The presence of surface water affected the load size of ground moisture in the PCA.We selected seasonal water and permanent water data from the JRC Yearly Water Classification History dataset (https://developers.google.com/earth-engine/datasets/catalog/JRC_GSW1_3_YearlyHistory $\mathrm { \ ? h l { = } e n \mathrm { \backslash } }$ 0 (Pekel et al.,2Ol6)on the GEE platform as mask files and used these to mask the water bodies of original images.

(3) Dryness

BSI reflects the dryness of ground surface,and is an important indicator that reflects the ecological condition of arid area. Therefore, dryness is expressed using BSI, which is expressed as follows:

$$
\mathrm { B S I } { = } \frac { \lbrack \left( \rho _ { \mathrm { S W I R 1 } } + \rho _ { \mathrm { r e d } } \right) - ( \rho _ { \mathrm { N I R } } + \rho _ { \mathrm { b l u e } } ) ] } { [ \left( \rho _ { \mathrm { S W I R 1 } } + \rho _ { \mathrm { r e d } } \right) + ( \rho _ { \mathrm { N I R } } + \rho _ { \mathrm { b l u e } } ) ] } . \
$$

(4) Salinity

Salinity is an important factor that limits ecological environment of the oasis inarid area.The retrieval of soil salinity indicators from images can reflect soil salinity status efectively (Whitney et al.,2O18; Yu et al.,2O1O). Salinity index (SI) inversion equation used in this paper is expressed as follows (Khan et al., 2005):

$$
\mathrm { S I } { = } \sqrt { \rho _ { \mathrm { b l u e } } \times \rho _ { \mathrm { r e d } } } .
$$

(5) PCA

Four indicators including NDVI, WET,BSI and SI were combined into a comprehensive indicator through principal component transformation，and most of the information was concentrated on the first two principal components: PC1 and PC2 (Zheng et al., 2O2O). This way, eco-environmental quality monitoring can be realized by means of remote sensing without manually configuring the weights of various indicators. Because the range of values for the four indicators is not unified,the weight of each indicator becomes unbalanced if PCA is conducted directly on the indicators. Therefore,before PCA,the range of each indicator value must be unified to O-1.The normalization formula is expressed as follows:

$$
N I _ { i } = \frac { I _ { i } - I _ { \operatorname* { m i n } } } { I _ { \operatorname* { m a x } } - I _ { \operatorname* { m i n } } } ,
$$

where $N I _ { i }$ is the index normalization result; $I _ { \mathrm { i } }$ is the pixel value of each pixel; $I _ { \mathrm { m a x } }$ is the maximum pixel value of the entire image; and $I _ { \mathrm { m i n } }$ is the minimum pixel value of the entire image.

The four single-band images obtained after the above normalization were synthesized into a multiband image,and the same operation was performed for every year. Seven multiband images in 1990,1995,2000,2005,2010,2015 and 2020 were obtained.If the contribution rates of the eigenvalues of PC1 obtained after performing PCA exceed $80 \%$ and the eigenvectors are stable, PC1 can be considered to integrate most of features of these images. Generally,the larger the value of PC1, the more inferior the eco-environmental quality that may be reflected; this is contrary to typical logical judgments. Therefore,the positive and negative values of PC1 may be transposed to obtain the initial RSEI, expressed by $\mathrm { R S E I _ { 0 } }$ as follows:

$$
\mathrm { R S E I } _ { 0 } { = } 1 - \mathrm { P C } 1 .
$$

To facilitate quantitative analysis,we normalized $\mathrm { R S E I _ { 0 } }$ to obtain the improved RSEI, which can reflect the eco-environmental quality of arid area at a macroscopic level. The folowing formula was used:

$$
\mathrm { R S E I { = } ( R S E I _ { 0 } - R S E I _ { 0 m i n } ) / ( R S E I _ { 0 m a x } - R S E I _ { 0 m i n } ) , }
$$

where ${ \mathrm { R S E I } } _ { \mathrm { 0 m i n } }$ and $\mathrm { R S E I _ { \mathrm { 0 m a x } } }$ represent the minimum and maximum values of $\mathrm { R S E I } _ { 0 }$ , respectively.

# 2.3.2 Spatial autocorrelation analysis

Spatial autocorrelation can reflect the spatial distribution pattern (Soka and Oden,1978;Legendre, 1993) and interdependence among elements in the research field (Getis,2Oo7). The application of spatial autocorrelation analysis in ecological environment, especially in large-scale remote sensing ecological environment analysis, is relatively successful (Jing et al., 2O2O; Xiong et al., 2021). In this study, we adopted two commonly used spatial statistical methods, global spatial autocorrelation analysis and LISA. Global spatial autocorrelation was used to analyze the overall spatial distribution characteristics of RSEI in the research area,which was represented by global Moran's $I$ (Moran, 1948; Yang et al., 2O21) via the following formulas:

$$
{ \mathrm { g l o b a l ~ M o r a n } } ^ { \mathrm { * } } s I = { \frac { n } { S _ { 0 } } } { \frac { \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \mathrm { W } _ { i , j } ( x _ { i } - { \overline { { x } } } ) ( x _ { j } - { \overline { { x } } } ) } { \sum _ { i = 1 } ^ { n } ( x _ { i } - { \overline { { x } } } ) ^ { 2 } } } ,
$$

$$
S _ { 0 } = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } W _ { i , j , }
$$

where $x _ { i }$ and $x _ { j }$ are the spatial attribute values for positions $i$ and $j$ ,respectively; $\overline { { x } }$ is the average value of the spatial attributes of all elements in the study area; $n$ is the total number of space elements; $W _ { i , j }$ is the spatial weight; and $S _ { 0 }$ is the collection of all spatial weights. The range of global Moran's $I$ values is $( - 1 , 1 )$ ； A global Moran's $I { > } 0$ means that RSEI has a clustered distribution in space.The closer it is to 1, the higher the degree of clustering.A global Moran's $I { < } 0$ means that RSEI has a discrete distribution in space.The closer it is to $^ { - 1 }$ , the higher the degree of this discrete distribution.A global Moran's $\scriptstyle { I = 0 }$ means that the attribute is randomly distributed in the overall space (Li et al., 2020).

LISA can reflect the local correlation of the spatial distribution of the attributes of a research object.Even if the global Moran's $I$ is O,there may be local cluster phenomenon；therefore,a combination of LISA and global Moran's $I$ analysis is necessary. The formula is expressed as follows (Anselin, 1995):

$$
\mathrm { L I S A } { = } \frac { x _ { i } - \overline { { x } } } { { S _ { i } } ^ { 2 } } \sum _ { j = 1 , \ j \neq i } ^ { n } \mathrm { W } _ { i , j } ( x _ { j } - \overline { { x } } ) ,
$$

$$
S _ { i } ^ { 2 } = { \frac { \sum _ { j = 1 , \ j \neq i } ^ { n } ( x _ { j } - { \overline { { x } } } ) ^ { 2 } } { n - 1 } } ,
$$

where $x _ { i }$ and $x _ { j }$ are the attribute values of spatial elements $i$ and $j$ ，respectively; $W _ { i , j }$ is the spatial weight between spatial elements $i$ and $j ; \overline { { x } }$ is the mean value of the corresponding attributes；and $n$ is the total number of spatial elements.

The results of local spatial autocorrelation analysis generated a LISA clustering map where five spatial distribution types were presented: high-high (H-H) cluster， low-low (L-L） cluster, high-low (H-L) outlier, low-high (L-H) outlier and not significant.H-H indicates the presence of high values is surrounded by high values and L-L indicates the presence of low values is surrounded by low values.H-L indicates a high value abnormality and L-H indicates a low value abnormality. A not significant value indicates that the attribute value is close to a random distribution.

# 2.3.3 Impact ofLUCC on RSEI

Over the past $3 0 \mathrm { a }$ ,the land cover type of the Hotan Oasis has changed significantly,which directly leads to changes in RSEI. To investigate how the distribution and changes in RSEI are reflected in LUCC，this study uses Landsat imagery from two time points,199O and 2O2O (the same data sources used to calculate RSEI in 199O and 2O2O), to classify their land cover types.

# 3 Results

# 3.1 PCAofRSEI

The results of the four indices,i.e.,NDVI, WET,BSI and SI, obtained using PCA for each year are shown in Table 2.The eigenvalue contribution rates of the PC1 in 1990,1995,2000,2005,2010, 2015 and 2020 were $8 9 . 6 3 \%$ ， $8 8 . 6 7 \%$ ， $8 9 . 5 9 \%$ $8 6 . 9 4 \%$ $9 1 . 5 2 \%$ $9 0 . 6 0 \%$ and $91 . 5 9 \%$ ,respectively. In other words, they all exceeded $8 5 . 0 0 \%$ , indicating that PC1 integrates most of the features of the four indices and can be used as the initial RSEI, that is, $\mathrm { R S E I _ { 0 } }$ . Take the PCA reports for 1990 and 2020 as an example,as shown in Table 3,The rates of contribution from the eigenvalues of PC2, PC3 and PC4 were all found to be below $10 \%$ and the positive and negative directions are unstable, reflecting more noisy features. Therefore, they were disregarded in the analysis. In PC1, NDVI and WET eigenvectors for each year are negative,and BSI and SI eigenvectors are positive,which appears to contradict the actual ecological environment condition.However, PC1 is not the final result,and a positive and negative conversion operation for PC1 using Equation 9 is required. In this way, the sign of the eigenvector is consistent with the actual ecological environment condition.

Table 2First principal component(PC1)of principal component analysis forRSEI in1990,1995,2000,2005, 2010,2015and2020   

<html><body><table><tr><td>PC1</td><td>1990</td><td>1995</td><td>2000</td><td>2005</td><td>2010</td><td>2015</td><td>2020</td></tr><tr><td>NDVI</td><td>-0.48641</td><td>-0.48552</td><td>-0.49201</td><td>-0.48959</td><td>-0.49658</td><td>-0.49817</td><td>-0.50478</td></tr><tr><td>WET</td><td>-0.47930</td><td>-0.47372</td><td>-0.47392</td><td>-0.46008</td><td>-0.48033</td><td>-0.47307</td><td>-0.47814</td></tr><tr><td>BSI</td><td>0.51779</td><td>0.52127</td><td>0.51721</td><td>0.52479</td><td>0.51152</td><td>0.51710</td><td>0.51375</td></tr><tr><td>SI</td><td>0.51534</td><td>0.51782</td><td>0.51557</td><td>0.52271</td><td>0.51092</td><td>0.51052</td><td>0.50263</td></tr><tr><td>Eigenvalue</td><td>0.09923</td><td>0.09809</td><td>0.09906</td><td>0.09599</td><td>0.10061</td><td>0.09903</td><td>0.10018</td></tr><tr><td> Percentage of eigenvalue</td><td>89.63</td><td>88.67</td><td>89.59</td><td>86.94</td><td>91.52</td><td>90.60</td><td>91.59</td></tr></table></body></html>

Note:RSEIotesiedolicaleledeegeaidex;Essel; SI, salinity index.

Table 3Principal component (PC) analysis for199O and 2020   

<html><body><table><tr><td>Year</td><td>Indicator</td><td>PC1</td><td>PC2</td><td>PC3</td><td>PC4</td></tr><tr><td rowspan="6">1990</td><td>NDVI</td><td>-0.48641</td><td>0.66914</td><td>0.10060</td><td>0.55275</td></tr><tr><td>WET</td><td>-0.47930</td><td>-0.70834</td><td>-0.20970</td><td>0.47387</td></tr><tr><td>BSI</td><td>0.51779</td><td>-0.17157</td><td>0.63423</td><td>0.54792</td></tr><tr><td>SI</td><td>0.51534</td><td>0.14517</td><td>-0.73733</td><td>0.41194</td></tr><tr><td>Eigenvalue</td><td>0.09923</td><td>0.00942</td><td>0.00186</td><td>0.00020</td></tr><tr><td>Percentage of eigenvalue (%)</td><td>89.63</td><td>8.51</td><td>1.68</td><td>0.18</td></tr><tr><td rowspan="6">2020</td><td>NDVI</td><td>-0.50478</td><td>0.55881</td><td>-0.10010</td><td>0.65032</td></tr><tr><td>WET</td><td>-0.47814</td><td>-0.80865</td><td>-0.17005</td><td>0.29755</td></tr><tr><td>BSI</td><td>0.51375</td><td>-0.18263</td><td>0.54236</td><td>0.63918</td></tr><tr><td>SI</td><td>0.50263</td><td>-0.02139</td><td>-0.81665</td><td>0.28283</td></tr><tr><td>Eigenvalue</td><td>0.10018</td><td>0.00625</td><td>0.00283</td><td>0.00012</td></tr><tr><td>Percentage of eigenvalues (%)</td><td>91.59</td><td>5.71</td><td>2.59</td><td>0.11</td></tr></table></body></html>

Note:RSEIesdicaliex;ldreegeade;WEss;ele; SI, salinity index.

# 3.2Spatial distribution of RSEI

We processed RSEI maps in 1990，1995，2000，2005，2010,2015 and 2020 to calculate the multi-year mean of RSEI of the Hotan Oasis,as shown in Figure 3.The high values of multi-year mean RSEI correspond to the middle of the oasis and both sides of the river, except for the urban built-up areas.The highest values occurring in the south and southeast of built-up areas in Moyu County, in a strip-like distribution.The outer side of the oasis and bare land of the river channel are generally distributed with low values and surround the entire oasis. The medium and low values were mainly distributed in Kunyu City,the northwestern and northeastern parts of the oasis,and the built-up areas of Moyu County, Hotan City and Lop County.

The value of RSEI was divided into five levels: poor, fair, moderate,good and excellent corresponding to 0.0-0.2, 0.2-0.4, 0.4-0.6,0.6-0.8 and 0.8-1.0,respectively,as shown in Figure 4.In Kunyu City，the distribution was almost always poor in 1990,1995 and 2000,and fair, moderate and good in 2Oo5 and increasingly every subsequent year; their areas increased to the maximum in 2020. Combined with Figure 5,the average values of RSEI in 1990,1995, 2000, 2005,2010,2015 and 2020 were 0.41,0.42,0.42,0.46,0.46, 0.50 and 0.50, respectively, showing an increasing trend. The poor distribution proportion decreased year by year from $2 6 \%$ in 1990 to $4 \%$ in 2020,and the percentages of fair and moderate distributions of RSEI increased from $23 \%$ to $27 \%$ and from $23 \%$ to $36 \%$ ，respectively. The percentage of good distribution of RSEI fluctuates, but is relatively stable. The percentage of excellent distribution increased slightly but not significantly.

# 3.3Change detection of RSEI

To explore the spatial and temporal changes in RSEI, we performed a change detection of RSEI in the Hotan Oasis during 1990-2000,2000-2010,2010-2020 and 1990-2020,as shown in Table 4.If RSEI level does not change over the year, it is indicated by O,for example,from moderate to moderate; if the region grows by one level, it is indicated by1,for example,from moderate to good; and if the level drops,for example, from excellent to good,it is indicated by $^ { - 1 }$ . Similarly, if the level rises by 2 or 3 and drops by 2 or 3,it is indicated by 2 or 3 and $^ { - 2 }$ or $^ { - 3 }$ ，respectively.We omitted 4 and $^ { - 4 }$ from the analysis because the area of the region ascending by four levels and descending by four levels was too small. We named the levels that changed by $3 , 2 , 1 , 0 , - 1 , - 2$ and $^ { - 3 }$ as follows: obviously improved (OI), generally improved (GI), slightly improved (SI), invariable (IN)，slightly deteriorated (SD)，generally deteriorated (GD）and obviously deteriorated (OD), respectively. Results showed that IN accounted for $7 4 . 3 5 \%$ ， $6 1 . 5 5 \%$ ， $5 5 . 3 8 \%$ and $4 1 . 1 1 \%$ during 1990-2000,2000-2010,2010-2020 and 1990-2020,respectively，indicating that approximately half of the regional eco-environmental quality has changed. The percentages of OI and OD during 1990-2000,2000-2010 and 2010-2020 did not exceed $1 . 0 0 \%$ , and even throughout the 3O-a period from 1990 to 2020, the percentage of IO was only $2 . 6 6 \%$ ，while the percentage of OD was only $0 . 1 0 \%$ , indicating that the area with changes obviously in eco-environmental quality was very small (Table 4). During 1990-2000,2000-2010,2010-2020 and 1990-2020,the percentages of GD area were $0 . 2 8 \%$ ， $0 . 2 2 \%$ ， $0 . 9 3 \%$ and $1 . 3 6 \%$ ,whereas those of GI were $0 . 8 5 \%$ $3 . 4 5 \%$ ， $4 . 5 2 \%$ and $1 0 . 7 \%$ respectively. The increase of GI was significantly higher. Similarly, the percentages of SD were $1 1 . 7 4 \%$ ， $8 . 2 8 \%$ ， $1 3 . 4 4 \%$ and $1 1 . 8 0 \%$ ,and those of IS were $1 2 . 7 5 \%$ ， $2 6 . 3 4 \%$ ， $2 5 . 3 3 \%$ and $3 2 . 2 1 \%$ respectively. The differences between SI and SD for the aforementioned periods were $1 . 0 1 \%$ $1 8 . 0 6 \%$ ， $1 1 . 8 9 \%$ and $2 0 . 4 1 \%$ , respectively. That is, the amount of spatial and temporal changes in RSEI of the Hotan Oasis remained stable from 1990 to 2Oo0,but increased significantly between 2000-2010 and 2010-2020.

![](images/d0bea36c753b9a8b1ef674fcad751382894ac2857b28b63b0dd7a4ccb1565079.jpg)  
Fig.3Spatial distribution of multi-year mean RSEI(remote sensing-based ecological index)in the Hotan Oasis

![](images/871d8acc9f0393d37a78864da5907b6abf854c51e2e34c5609f6a4a1988538d2.jpg)  
Fig.4Spatial distribution of RSEI (remote sensing-based ecological index)level in the Hotan Oasis in 1990, 1995,2000,2005,2010,2015and2020

![](images/119844fbd2730597c31451b2f5aef8e8006f4661ae8f75c2d25f7e9a2e89fc40.jpg)  
Fig.5Percentage of different levelsofRSEI(remote sensing-based ecological index)in the Hotan Oasis in1990, 1995，2000,2005,2010,2015 and2020

Table 4Area and percentage of RSEIlevel change during 1990-2000,2000-2010,2010-2020 and 1990-2020   

<html><body><table><tr><td>Year</td><td>Index</td><td>3 (01)</td><td>2 (GI)</td><td>1 (SI)</td><td>0 (IN)</td><td>-1 (SD)</td><td>-2 (GD)</td><td>-3 (OD)</td></tr><tr><td>1990-2000</td><td>Area (km²)</td><td>0.88</td><td>36.59</td><td>547.22</td><td>3191.04</td><td>504.04</td><td>12.05</td><td>0.34</td></tr><tr><td rowspan="2">2000-2010</td><td>Percentage (%)</td><td>0.02</td><td>0.85</td><td>12.75</td><td>74.35</td><td>11.74</td><td>0.28</td><td>0.01</td></tr><tr><td>Area (km²)</td><td>6.79</td><td>147.91</td><td>1130.46</td><td>2641.94</td><td>355.40</td><td>9.47</td><td>0.18</td></tr><tr><td></td><td>Percentage (%)</td><td>0.16</td><td>3.45</td><td>26.34</td><td>61.55</td><td>8.28</td><td>0.22</td><td>0.00</td></tr><tr><td rowspan="2">2010-2020</td><td>Area (km²)</td><td>13.80</td><td>194.02</td><td>1087.26</td><td>2376.80</td><td>576.91</td><td>39.75</td><td>3.53</td></tr><tr><td>Percentage (%)</td><td>0.32</td><td>4.52</td><td>25.33</td><td>55.38</td><td>13.44</td><td>0.93</td><td>0.08</td></tr><tr><td rowspan="2">1990-2020</td><td>Area (km²)</td><td>114.35</td><td>460.84</td><td>1382.44</td><td>1764.33</td><td>506.54</td><td>58.32</td><td>4.23</td></tr><tr><td>Percentage (%)</td><td>2.66</td><td>10.74</td><td>32.21</td><td>41.11</td><td>11.80</td><td>1.36</td><td>0.10</td></tr></table></body></html>

Note:RSEI,remotesensing-basedecologicalindex.OI,GI,SI,IN,SD,GDandODrepresentthattheRSEIlevelftheareais obviouslyimprovedgerallyproed,igtlmpovdable,igtlyeterioatedenralleteateddisly deteriorated,respectively. The number of 3-1,O and $^ { - 1 - - 3 }$ represent the improved,unchanged and deteriorated levels of RSEI, respectively.

RSEI level changes in the four periods are shown in Figure 6.During 199O-2O00, most regions did not change significantly,and even the changed regions did not exhibit significant distribution characteristics.During 2Ooo-2O10, SI and GI distributions of larger areas occurred in the central part of Kunyu City, the northern part of Moyu County, the eastern and northeastern parts of Lop County,and on both sides of the downstream channels of the two rivers.A ring of GD hotspots formed at the periphery of the built-up area of Hotan City,and a considerable area of SD distribution occurred in the eastern and central parts of Lop County. SI and GI were distributed in the reclamation area in the northern part of Kunyu City,in the outermost part of the two rivers,and in the southeastern part of Lop County during 2O10-2O20.The distribution of GD and OD in the eastern and southern parts of the urban built-up area of Moyu County indicates a significant degradation of eco-environmental quality. The distribution of degraded areas in the periphery of the urban built-up area of Hotan City has expanded sharply to the west.From RSEI level change in the 30-a period of 1990-2O2O shown in Figure 6,eco-environmental quality near the edge of the oasis increases,while eco-environmental quality in the middle of the oasis decreases,and the "three cores and one line" macroscopic ecological distribution pattern among Hotan City, Moyu County, Lop County and their connecting roads has been formed.

![](images/4cf5c4a643f207e267940b56b38f5688679b958c71ee4cb8dc93bb6e15d71d65.jpg)  
Fig.6RSEI (remote sensing-based ecological index）level change during 1990-2000 (a),2000-2010 (b), 2010-2020 (c） and 1990-202O (d). OI,GI, SI,IN,SD,GD and OD represent that RSEI level of the area is obviously improved，generally improved，slightly improved，invariable，slightly deteriorated，generally deteriorated and obviously deteriorated,respectively. The number of 3-1,O and $^ { - 1 - - 3 }$ mean the improved, unchanged and deteriorated levels of RSEI, respectively.

# 3.4Spatial autocorrelation of RSEI

To analyze the spatial correlation of RSEI, we sampled RSEI distribution in 1990, 20O0,2010 and 2020 with a $1 \mathrm { k m } { \times } 1 \mathrm { k m }$ grid to generate 5956 sampling points in the Hotan Oasis. The scatter plots of global Moran's $I$ of RSEI in 1990, 2000,2010 and 2020 are shown in Figure 7.Most of scattered points were distributed in the first and third quadrants, indicating that eco-environmental quality of the study area was positively correlated with its spatial distribution. Global Moran's Iin 1990,2000, 2010 and 2020 were 0.891, 0.889, 0.847 and 0.777,respectively， showing a high degree of aggregated distribution characteristic.

![](images/767f8e814a640a5be0aabf9a3d7fb6fb37656329dfcbfb2b6935f14c4bf75223.jpg)  
Fig.7Global Moran's $I$ scatterplot of RSEI (remote sensing-based ecological index) level change in the Hotan Oasis in 1990(a),2000 (b),2010(c)and 2020(d).H-H,L-L,H-LandL-Hare high-high cluster,low-lowcluster, high-low outlier and low-high outlier,respectively.

# 3.5Local indicators of spatial autocorrelation of RSEI

To explore the spatial characteristics of RSEI, we generated LISA clustering maps of RSEI in 1990, 2000,2010 and 2020,as shown in Figure 8.Compared with 1990,the extent of NS (not significant) expanded in 20O0,and it continued to expand in 2010,and reached the most in 2020,especially in the built-up area of Moyu County,Hotan City and Lop County. The H-H cluster area is divided into four parts: the central reclamation area of Kunyu City, the northwestern reclamation area of Moyu County,and the western and eastern reclamation areas of the Yurungkax River. The fragmentation of the H-H cluster area is significantly higher in 2O2O than in previous years; therefore,the global Moran's $I$ is the lowest in 2O2O.The distribution of the H-L outlier and L-H outlier is very small and sporadic,indicating that there are few extreme points of eco-environmental quality in the entire oasis. Overall, the areas of H-H cluster are mainly distributed in the middle of the Hotan Oasis,and the areas of L-L cluster are mainly distributed in the outer edges of the oasis,reflecting the trend that the overall eco-environmental quality decreases from the inner part of the oasis to the edges.

![](images/96095600855d72ebcc2209c943201ab164c6e71b8b190a854fdf22a8add22d0b.jpg)  
Fig.8LISA (local indicators of spatial autocorrelation) clustering map of RSEI in the Hotan Oasis in 1990 (a), 2000 (b),2010 (c) and 2020 (d)

# 3.6 Impact ofLUCCon RSEI

We used the Landsat images of the Hotan Oasis in 1990 and 202O (the same images as those used to calculate RSEI) to generate land use maps,as shown in Figure 9.According to its characteristics, we classified the Hotan Oasis into six types of land use:high coverage cultivated land，general coverage cultivated land, forest, grass and shrubland,impervious surfaces,water bodies and bare land. High coverage cultivated land is the land on which high covered crops are grown such as rice and wheat (Fig.9a). General coverage cultivated land is the land on which general covered crops are grown, consisting mainly of fruit trees (such as jujube and walnuts)or fruit trees combined with food crops (Fig.9b). Impervious surfaces are mainly urban built-up areas (Fig.9d).We divided the forest,grassand and shrubland into one category (Fig. 9c).The water bodies include river, ditch, reservoir and pond (Fig. 9e). The bare land include desert (Fig. 9f).

![](images/f524d18cbd79280fa1b6779536d6d99a158cf2b1999068c65f7e94f489b2f8e9.jpg)  
Fig.9Spatial distribution mapof LUCC (land-use and land-cover change)in the Hotan Oasis in 2Oo0 and 2020 (a,b,c,d,eandfare the Google Earth images of six types of typical land surfaces.Boxes are the location of these land surfaces)

Compared with the map of RSEI spatial distribution (Fig.4), we found that the distribution of the bare land and the worst eco-environmental quality areas (Denoted by Poor） almost overlap. Compared with 1990,the distribution of this land type in 202O is already very small,and was replaced by cultivated land,which correspondingly showed by a decrease in poor distribution of RSEI and an increase in moderate distribution of RSEI.

In 1990,there was almost no cultivated land at Kunyu City，while in 2O2O,cultivated land occupied large area, indicating that agricultural activities were frequent over the 3O-a development and that the eco-environmental quality has changed significantly. These results confirmed by the increase in reclamation areas on both sides of the Yurungkax and Karakax rivers and in the eastern part of Lop County. On the other hand, the area of impervious surface undergone a considerable increase in 2O2O compared with 1990,indicating that the continuous urbanization of the Hotan Oasis. Correspondingly, the fragmentation of the distribution of RSEI increased inside the oasis.

# 4Discussion

# 4.1 ValidationofindicatorsforRSEI

Based on the 5956 sampling points, we projected NDVI, WET and RSEI onto a three-dimensional space as one group,and BSI, SI and RSEI onto a three-dimensional space as another group,as shown in Figure 1O. RSEI increases when NDVI and WET increase, but decreases when BSI and SI increase， showing different and strong linear relationships. Therefore， the greenness represented by NDVI and the wetness represented by WET were positively correlated with the eco-environmental quality represented by RSEI, which is consistent with the actual situation (Fig. 10a). The similar relationships of NDVI and WET with RSEI used for the study of ecological quality in Er Hai Lake Basin by Xiong et al. (2O21). The dryness represented by BSI and salinity represented by SI are negatively correlated with the eco-environmental quality represented by RSEI, in line with the actual situation (Fig.1Ob).This is similar to the relationship between the surface albedo (albedo), SI and soil salinity ecological index (SSEI) from remote sensing of ecological environment in salinized irigation areas in the Manas River Basin in Xinjiang Uygur Autonomous Region (Zhang et al., 2017).

![](images/4f54317ab99e3840f3b59b1d5fbd39a7c5a1a5a30e93e9b1103c457bcfeb0c49.jpg)  
Fig.10Three-dimensional scatter plots of NDVI, WETand RSEI (a);and of BSI, SI and RSEI (b).NDVI, normalizeddifference vegetation index;WET,wetness;RSEI,remote sensing-basedecological index; BSI,bare soil index; SI,salinity index;   
Fig.11Correlation matrix of each indicatorand RSEI in 1990 (a)and 2O20 (b).NDVI, normalized difference vegetation index;WET, wetness;BSI,bare soil index; SI,salinity index; RSEI,remote sensing-based ecological index.

The question of whether RSEI we constructed for arid area is more representative than single indicators can be analyzed using the Pearson correlation coefficient (Feidas et al.，2O14).We selected four single indicators and RSEI composite indicator for the correlation coefficient matrix calculation from 199O and 2O2O,respectively,as shown in Figure 11.The red color represent a positive correlation. The darker the red,the stronger the positive correlation. The darker the blue, the stronger the negative correlation. Mean is the average correlation, using the year 199O as an example,MeanNDVI_1990 $= ( | 0 . 7 4 | + | - 0 . 9 5 | + | - 0 . 9 0 | ) / 3 { = } 0 . 8 6$ . The mean of NDVI, WET,BSI, SI and RSEI in 1990 was 0.86, 0.85, 0.93, 0.93 and 0.96,and that in 2020 was 0.90, 0.85,0.93, 0.91 and 0.96, respectively. Thus,the mean of NDVI, WET,BSI, SI and RSEI in these two years was 0.88,

Correlation Correlation (a)1990 coefficient (b)2020 coefficient 1.00 1.00   
NDVI NDVI 0.74 -0.95 -0.90 0.94 0.80 NDVI NDVI 0.80 -0.98 -0.93 0.96 0.80 0.60 0.60   
WET WET -0.88 -0.93 0.93 0.40 WET WET -0.88 -0.88 0.92 0.40 0.20 0.20 BSI BSI 0.95 -0.99 0.00 BSI BSI 0.92 -0.98 0.00 -0.20 -0.20 SI SI -0.99 -0.40 SI SI -0.97 -0.40 -0.60 -0.60   
RSEI RSEI -0.80 RSEI RSEI -0.80 -1.00 -1.00 NDVI WET BSI SI RSEI NDVI WET BSI SI RSEI

0.85，0.93, O.92 and O.96,respectively. For a single indicator,BSI has the highest average correlation between indicators,which reaches 0.93 in 1990 and 2020.For the composite indicator, the average correlation coefficient between RSEI and these four indicators for each year exceeds 0.93.In addition to integrating the main information for each indicator, the improved RSEI is more representative than any single indicators, beter ilustrating the eco-environmental quality of the Hotan Oasis.

Yu et al. (2O21) studied the salinized land degradation index (SDI) of eco-environmental quality in the Aral Sea Basin.Although SDI was positively correlated with SI and albedo and negatively correlated with NDVI and land surface soil moisture index (LSM), positive and negative values of PC1 after PCA was not converted in the study. According to the final results,the correlation coefficients between combined indicators and single indicators were both greater than those between single indicators themselves,which is consistent with the result of current study.

The climate of the Hotan Oasis is dry with strong potential evaporation (Ding et al., 2O2O). The PC1 loadings of BSI and SI, representing surface dryness and salinity,ranged from O.5O to 0.52 in the PCA (Table 2). Those of NDVI and WET that represented surface greenness and humidity, ranged from O.46 to 0.50, with a slightly lower weighting compared with those of BSI and SI. The result is similar to that of the Aral Sea Basin (Wang et al.,2O21). The PC1 loadings for the greenness and moisture index in the constructed arid remote sensing ecological index (ARSEI) are also relatively low due to the low vegetation coverage in the area (Jiang et al.,2O19). Wang et al. (2019) conducted a study of ecological quality assessment of the Manas Lake in Xinjiang Uygur Autonomous Region. They found that the PC1 loadings of NDVI and WET were only O.12 and 0.33, respectively. The lower values of these loadings can be atributed to the low coverage of vegetation in the area, scare precipitation and high potential evaporation (Wang,2O21). Our result found that salinization in the oasis-desert transition zone of the Hotan Oasis led to a slightly higher share of SI in the PC1 loadings. Similar results were found on the eco-environmental quality of the Gurbantunggut Desert in Xinjiang Uygur Autonomous Region (Jiang et al.， 2O19） and Dulan County in Qinghai Province (Jia et al., 2021).

Different indicators have diferent degrees of spectral response to ground objects (Xue et al., 2017).To highlight their sensitivity,we considered the year 2O2O as an example and extracted the image pixel corresponding to the value range of 0.5-1.0,and then selected Sentinel 2 images with a higher spatial resolution as the effect comparison,as shown in Figure 12.In Figure 12,al and a2 are mainly distributed in the periphery of urban built-up areas with a high vegetation coverage, which is consistent with that reflected in the standard false color image of Sentinel 2 (Fig.12a6).The areas reflected by bl and b2 (Fig.12) are cultivated land on both sides of the Karakax River, which has the highest crop coverage owing to the stable water supply, while bare ground on both sides of river, desert and artificial surfaces are all clearly shown on Fig.12b3. In Figure 12,c1 reflects the striped reclamation area in the northwestern part of the Hotan oasis,bare land in the middle is relatively low and flat,and the degree of salinization is higher than elsewhere,as reflected in the c4 of Figure 12.

# 4.2 Validation of spatiotemporal distribution for RSEI

We selected representative indicators from the Xinjiang Statistical Yearbook and the China County Statistical Yearbook from 1992,1995,2000,2005,2010,2015 and 2019 to generate the statistical table of socio-economic data from the Hotan Oasis,as shown in Table 5.Results showed that population, total power of agricultural machinery,cultivated land area and grain production have increasing trends. Population growth leads to an increase in the demand for cultivated land (Deng et al.,2O15). The reclamation of new cultivated land occurs at the edge of the Hotan Oasis, transforming desert into cultivated land. This result explains the increasing RSEI values at the edge of the Hotan Oasis (Chen et al.,2019).

The statistical table shows that gross regional product (GRP) for both the secondary industry GRP and the tertiary industry GRP are growing rapidly. The growth in secondary and tertiary industries,combined with the emergence of large numbers of field roads and setlements in rural areas have increased the size of impervious surfaces across the oasis.They have also contributed to the fragmentation of RSEI distribution. Results by Xue et al. (2O21） indicated that anthropogenic factors as the main driving force led to the increased fragmentation in the landscape ecological pattern of the Hotan Oasis. Anthropogenic influences have also led to the expansion of the oasis,which is similar to the results of this study.

![](images/564cf8ad1b89b15cd375f73255ca952136d28f2a726431f10b178d0740c58698.jpg)  
Fig.12Comparison among indicators.a,b and c represent different sampling locations; 6and 7represents the standard falsecolor image and true color image of Sentinel 2，respectively.NDVI,normalized diference vegetation index; WET, wetnes; BSI,bare soil index; SI,salinity index; RSEI,remote sensing-based ecological index.

Table 5Socio-economic data of the Hotan Oasis   

<html><body><table><tr><td>Year</td><td>Total population (10.00)</td><td>Total power of agricultural (10.0i kry)</td><td>Cultivated land area (1000 hm²)</td><td>Grain production (t)</td><td>Gross regional (10.000 CNY)</td><td>Primary industry GRP</td><td>Secondary industry GRP (10,000 CNY)(10,000 CNY)</td><td>Tertiary industry GRP (10,000 CNY)</td></tr><tr><td>1992</td><td>90.10</td><td>17.50</td><td>81.84</td><td>387,358</td><td>81,029</td><td>50,761</td><td>11,648</td><td>18,620</td></tr><tr><td>1995</td><td>96.60</td><td>18.40</td><td>82.64</td><td>404,569</td><td>160,780</td><td>105,131</td><td>21,612</td><td>34,035</td></tr><tr><td>2000</td><td>110.00</td><td>23.00</td><td>91.17</td><td>509,114</td><td>178,411</td><td>101,566</td><td>22.614</td><td>54,231</td></tr><tr><td>2005</td><td>120.00</td><td>26.00</td><td>91.41</td><td>579,342</td><td>321,140</td><td>134,080</td><td>75,448</td><td>111,612</td></tr><tr><td>2010</td><td>135.00</td><td>33.00</td><td>97.11</td><td>674,272</td><td>696,522</td><td>210,118</td><td>141,565</td><td>344,839</td></tr><tr><td>2015</td><td>155.00</td><td>54.00</td><td></td><td></td><td>1,612,653</td><td>403,842</td><td>266,778</td><td>942.033</td></tr><tr><td>2019</td><td>171.28</td><td></td><td>123.25</td><td></td><td>2,630,573</td><td>451,317</td><td>422,743</td><td>1,756,513</td></tr></table></body></html>

Note:Kunyu Citywas establishedi2O16andthedataisincomplete.GRP,GrossRegionalProduct.TheGRPisbasedonthepricesof that year;-means that no statistics are available.

From the macroscopic perspective of satellite remote sensing monitoring, we can assume that in the oasis ecosystem,the greater the greenness index,i.e., the greater the vegetation cover, the greater the surface humidity and the smaller the scale of bare ground and salinity,the higher the biodiversity and ecosystem complexity and the more excellent the eco-environmental quality. Moreover, the application of medium resolution remote sensing images is inevitably be affected by mixed pixels.Therefore,more field validation data in some key areas in further work should be supplemented.

# 5 Conclusions

In this study，we used PCA to couple greenness,humidity, dryness and salinity on the GEE platform to construct a macroscopic and efficient monitoring method for eco-environmental quality based on improved RSEI. The spatial and temporal distribution of eco-environmental quality in the Hotan Oasis were quantitatively observed and its cause was analyzed in conjunction with LUCC.Results showed that the improved RSEI can reflect eco-environmental quality effectively of the oasis in arid area with relatively high applicability. NDVI and WET had a positive effect on eco-environmental quality of the Hotan Oasis. Meanwhile,BSI and SI had negative effects.The spatial distribution of eco-environmental quality for the Hotan Oasis is high in the middle,and low in the surrounding areas,decreasing from the middle to the surrounding areas of the oasis.Moreover, RSEI at the periphery of the oasis changes from low to high with increasing years,while the fragmentation of RSEI distribution within the oasis increases.This is mainly due to the impact of anthropogenic,including the expansion of artificial oasis into the desert,the replacement of desert ecosystems by farmland ecosystems,and the increase in the distribution of impervious surfaces. In arid areas with limited water and fertilizer resources, changing land use methods from quantitative expansion to high-quality development can reduce the risks that the oasis ecological environment may face.

# Acknowledgements

This research was funded by the National Natural Science Foundation of China (42161049,41761019,41061052). Weacknowledge the editors and anonymous reviewers for their helpful comments on improvement of the manuscript.

# References

AlexanderC.2O2o.Normalised diference spectral indicesandurbanlandcoverasindicatorsoflndsurfacetemperature (LST). InternationalJournalof AppliedEarthObservationand Geoinformation,86:102013,doi:10.1016/j.jag.2019.102013.   
Anselin L.1995.Local indicators of spatial association-LISA. Geographical Analysis,27(2): 93-115.   
BaigMHA,ZhangLF,ShuaiT,etal.2O14.DerivationofataselledcaptransformationbasedonLandsat8at-satelite reflectance.Remote Sensing Letters,5(5): 423-431.   
Cao R,Chen Y,Shen MG,et al.2018.Asimple methodto improve thequalityof NDVItime-series data byintegrating spatiotemporal information with the Savitzky-Golay filter.Remote Sensing of Environment,217: 244-257.   
Chen J,Shen MG,ZhuXL,etal.O9.dicatorofflowerstatusderivedfrominsituhyperspectralmeasurementinapine meadow on the Tibetan Plateau.Ecological Indicators,9(4):818-823.   
ChenMX,YeC,LuDD,etal.20l9.Cognitionandconstructionofthetheoreticalconnotationsofnewurbanizationwith Chinese characteristics.Journal of Geographical Sciences,29(1O):1681-1698.   
Chu HS,Venevsky S，WuC,et al.2019.NDVI-based vegetation dynamicsand itsresponse to climatechangesat Amur-Heilongjiang River Basin from 1982 to 2015.Science of the Total Environment,650:2051-2062.   
CookM,SchottJR,MandelJ,etal.2O14.Developmentofanoperationalcalibration methodologyfortheLandsat hermaldata archiveandinitialtestingof theatmosphericcompensationcomponentofaland surface temperature (LST)productfrom the archive.Remote Sensing,6(11): 11244-11266.   
Deng XZ,Huang JK,Rozele S,et al.2O15.Impactofurbanizationoncultivatedland changesin China.LandUsePolicy45: 1-7.   
Ding Y,AbdiramanH,ChenXY,etal.2O2o.Spatial-temporalchanges inegetationcharacteristicsandclimatenHotan Prefecture.Acta Ecologica Sinica,40(4): 1258-1268.(in Chinese)   
DongD W,Abdirahman H,Wang DD,et al.2019.Spatio-temporal variationsin vegetationcoverin Hotan Oasis from1994 to 2016.Acta Ecologica Sinica,39(10): 3710-3719.(in Chinese)   
Fang HL,ZhangYG,Wei SS,et al.2O19.Validationof global moderateresolution leaf area index (LAI)productsover croplands in northeastern China.Remote Sensing of Environment,233:111377,doi: 10.1016/j.rse.2019.111377.   
Feidas H,Karagianidis A,Keppas S,tal.2O14.Modelingandmapping temperatureand precipitationclimate data inreece using topographical and geographical parameters.Theoretical and Applied Climatology,118(1): 133-146.   
FungT,Siu W.2Ooo.Environmentalqualityanditschanges,ananalysisusingNDVI. InterationalJouralofRemote Sensing, 21(5): 1011-1024.   
Getis A.20o7.Reflections on spatial autocorrelation.Regional Science and Urban Economics,37(4): 491-496.   
Guo H,Bao A,Liu T,etal.2019.Determining variable weights foran Optimal Scaled Drought Condition Index (SDCI): Evaluation in Central Asia.Remote Sensing of Environment,231: 11220,doi:10.1016/j.rse.2019.111220.   
Guo H W,Ling HB,Xu HL,etal.2O16.Studyof suitableoasis scales based on waterresource availability in anaridregionof China: a case study of Hotan River Basin. Environmental Earth Sciences,75(11):1-14.   
Guo YH,Abdirahman H, Wei TB,etal.2O21.Theecosystem servicevalue evaluationof Hotan area based onland usechanges. Acta Ecologica Sinica,41(16): 6363-6372.(in Chinese)   
HaoLN,Su XL,Singh VP,et al.2O19.Suitableoasisandcultivatedlandscales inaridregions basedonecologicalhealth. Ecological Indicators,102: 33-42.   
Hassan M A,Yang MJ,Rasheed A,et al. 2019.Arapid monitoring of NDVI acrossthe wheat growth cycle for grain yield prediction using a multi-spectral UAV platform. Plant Science,282: 95-103.   
Huang C,WylieB,YangLetaloo2.DerivationofatasseledcaptransformationbasedonLandsat7at-satelitereflectance. Remote Sensing Letters, 23(8): 1741-1748.   
Jia H W,YanCZ,Xing X G,et al.2O21.Evaluationof ecological environment inthe Dulan County basedonthemodified remote sensing ecological index model.Journal of Desert Research,41(2): 181-190.(in Chinese)   
JiangCL,WuL,LiuD,etal.2O19.Dynamic monitoringof eco-environmental qualityinariddesertareabyremote sensing: Taking the Gurbantunggut DesertChina as an example. Chinese Jourmal of Appied Ecology,30(3):877-883.(in Chinese)   
JiangLL,JiapaerGBaoAM,etal.2O19.Assessnglanddegradationandquantifyngitsrivers intheAmudaryaRiverdelta. Ecological Indicators,107:105595,doi: 10.1016/j.ecolind.2019.105595.   
Jing YQ,ZhangF,HeYF,et al.2020.Assessmentof spatial andtemporal variationof ecological environmentqualityin EbinurLake Wetland NationalNatureReserve,Xinjiang,China.Ecological Indicators,11O:105874,doi:10.1016/j.colind. 2019.105874.   
JoshiPP,WynneR H,Thomas VA.2019.Cloud detection algorithmusing SVM with SWIR2 and tasseled cap aplied to Landsat8.InternationalJourmalof Applied Earth Observation and Geoinformation,82:101898,doi:10.1016/j.jag.2019. 101898.   
Kganyago M,MhangaraP,AexandridisT,etal.2O20.Validationofsentinel-2leaf areaindex(LAI) productderived from SNAP toolbox andits comparison with global LAI products in an African semi-arid agricultural landscape. Remote Sensing Letters,11(10): 883-892.   
Khan NM,Rastoskuev V V,Sato Y,et al.2005.Assessment of hydrosaline land degradationbyusing a simple aproachof remote sensing indicators.Agricultural Water Management,77(1-3): 96-109.   
Legendre P.1993. Spatial autocorrelation: trouble or new paradigm?. Ecology, 74(6): 1659-1673.   
Li RH,Chen NC,Zhang X,etal.2O20. Quantitative analysisof agricultural drought propagation processintheYangtze River Basin byusing crosswavelet analysisand spatialautocorelation.Agricultural and Forest Meteorology,28o:107809,doi: 10.1016/j.agrformet.2019.107809.   
LiZY,Han Y,HaoTY.2O2o.Assessngtheconsistencyofremotelysensed multipledroughtindices formonitoring drought phenomena in continental China. IEEE Transactions on Geoscience and Remote Sensing,58(8): 5490-5502.   
Liu C,Yang MH,HouYT,etal.2O21.Spatiotemporal evolutionof sandecologicalqualityunderdiferenturbandensities:A comparative analysisof Xiamen and Kinmen Islands,southeast China.Ecological Indicators,124:107438,doi:10.1016/j. ecolind.2021.107438.   
Liu Y, XueJ, GuiD W,etal. 2O18.Agricultural oasis expansionand itsimpact on oasis landscapepaterns in the southern margin of Tarim Basin, Northwest China.Sustainability,1O(6):1957.   
Mildrexler DJ,Zhao M S,Running SW.2009.Testing a MODIS global disturbance index acrossNorth America.Remote Sensing of Environment,113(10): 2103-2117.   
MoranPAP.1948.The interpretationof statistical maps.Journal oftheRoyal Statistical Society: Series B(Methodological), 10(2): 243-251.   
Mutanga O, Kumar L. 2019. Google earth engine applications. Remote Sensing,11(5): 591.   
PekelJF,Cottam A,Gorelick N,etal.2O16.High-resolution mappngof globalsurface waterand itslong-termchanges. Nature,540(7633): 418-422.   
RheJ,ImJ,Carbone GJ.20l0.Monitoring agricultural droughtforarid andhumid regions usingmulti-sensorremote snsing data.Remote Sensing of Environment,114(12): 2875-2887.   
SokalRR,Oden NL.1978.Spatialautocorelationinbiology: Methodology.Biological Journalof theLinneanSociety0(2): 199-228.   
Wang J,MaJL,XieFF,etal.020.Improvement ofremotesensingecologicalindex inaridregions:Taking Ulan Buh Desert as an example.Chinese Journal of Applied Ecology,31(11): 3795-3804.(in Chinese)   
Wang J,LiuDW,MaJL,etal.221.Developmentofalarge-scaleremotesensing ecological index inaridareasandits application in the Aral Sea Basin. Journal of Arid Land,13(1): 40-55.   
WangLC,JiaoL,LaiFB,etal.2l9.Evaluationofecolgicalchangesbasedonaremotesensing ecologicalindexinaManas Lake wetland.Acta Ecologica Sinica,39(8): 2963-2972. (in Chinese)   
Wang LP, Wang SF,ZhangLD,et al.2020.Assessing the spatial paternof irrigation demandunderclimatechange inarid area. ISPRS International Journal of Geo-Information, 9(9): 506.   
WangYG2O21.Evaluationoflake wetland ecotourismresourcesbasedonremotesensing ecological index.Arabian Journalof Geosciences,14(7):1-8.   
Wang ZX,Liu C,Alfredo H.2O03.From AVHRR-NDVI to MODIS-EVI: Advances in vegetation index research.Acta Ecologica Sinica,23(5): 979-987. (in Chinese)   
Whitney K,ScudieroE,El-Askary HM,etal.2O18.Validating theuseof MODIS time series forsalinityassssmentover agricultural soils in California, USA. Ecological Indicators,93: 889-898.   
Xiong Y,Xu WH,LuN,etal.221.Assssmentofspatialtemporalchangesofeological eviromentqalitybasedoREI and GEE:Acase studyin Erhai Lake Basin,Yunnan Province,China.Ecological Indicators,125:107518,doi:10.1016/j. ecolind.2021.107518.   
Xu HQ.2005.Astudyon information extractionof waterbody withthe modified normalized diference water index (MNDWI). Journal of Remote Sensing,9(5): 589-595.(in Chinese)   
Xu HQ.2013.Aremote sensingurban ecological index and itsaplication.Acta Ecologica Sinica,33(24):7853-7862.(in Chinese)   
Xu H Q,Wang MY,Shi TT,etal.2018.Predictionof ecological effectsof potentialpopulationand impervioussurface increases using a remote sensing based ecological index (RSEI). Ecological Indicators,93: 730-740.   
Xu H Q,Wang YF, Guan H,et al.2019.Detecting ecological changes with aremote sensing based ecological index (RSEI) produced time series and change vector analysis.Remote Sensing,11(20): 2345.   
XueDP,XueJ,Dai H,et al.2O21. Analysisofspatialandtemporalpaternchangesanddriving factorsof Hotan Oasis.Joural of Desert Research,41(4): 59-69.(in Chinese)   
Xue J,Su BF.2O17. Significant remote sensing vegetation indices: Areview of developments and applications.Journal of Sensors,2017:1-17,doi: 10.1155/2017/1353691.   
Yang QQ,XuGL,LiAJ,etal2O21.Evaluationandtrade-off of ecosystem services inthe QingyijiangRiverBasin.Acta Ecologica Sinica,41(23): 9315-9327.(in Chinese)   
Yu GM,Zhang S,Yu QW,et al.2014.Assesing ecological securityatthe watershed scale basedonRS/GIS: Acase study from the Hanjiang River Basin. Stochastic Environmental Research and Risk Assessment,28(2): 307-318.   
Yu RH,LiuTX,XuYP,etal.2O10.Analysisofsalinizationdynamicsbyremote sensing inHetao IrrgationDistrictof North China.Agricultural Water Management,97(12): 1952-1960.   
Yu T,JiapaerGBaoAM,etal.O1.Usingsytheticremotesensingindicators toonitorthelanddegradationinasalinized area.Remote Sensing,13(15): 2581,doi:10.3390/rs13152851.   
ZhangTY,WangL,Wang H,etal.2O17.Assssmentofsoil salinizationecological environmentchange inthe Manas river basin using remote sensing technology. Acta Ecologica Sinica,37(9): 30o9-3018.(in Chinese)   
Zhao G, Gao HL,CaiXM.2O20.Estimating lake temperature profileandevaporatiolosses byleveraging MODISLSTdata. Remote Sensing of Environment,251:112104,doi:10.1016/j.rse.2020.112104.   
Zheng ZH,WuZF,ChenYB,et al.2O2O.Explorationof eco-environmentand urbanizationchanges incoastal zones:Acase study in China over the past 20 years.Ecological Indicators,119:106847,doi:10.1016/j.ecolind.2020.106847.   
Zhu JW,Xie XT,LiXH.2O17.Asolution totheproblem ofecological environmental carrying capacityevaluation:Acase study of Henan Province.Acta Ecologica Sinica,37(21): 7039-7047. (in Chinese)