# Assessmentofdesertificationin Eritrea: land degradation based on Landsat images

Mihretab G GHEBREZGABHER1.2, YANG Taibaol\*, YANG Xuemei3, WANG Congqiangl

1Instituteof GlaciologyandEco-Geography,CollgeofEarthandEnvironmental Sciences,Lanzhou University,Lanzhou   
730000, China;   
² College of Business and Social Sciences,Adi Keihi 59,Eritrea;   
3 Gansu Desert Control Research Institute,Lanzhou 73oo70, China

Abstract: Remote sensing is an efective way in monitoring desertification dynamics in arid and semi-arid regions. In this study,we used a decision tree method based on NDVI (normalized difference vegetation index), SAVI (soil adjusted vegetation index),and vegetation cover proportion to quantify and analyze the desertification in Eritrea using Landsat data of the 197Os,198Os and 2014. The results demonstrate that the NDVI value and the annual mean precipitation declined while the temperature increased over the past $4 0 \textrm { a }$ .Strongly desertified land increased from $4 . 8 2 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ （20 $( 3 8 . 5 \% )$ in the 1970s to $8 . 3 8 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ （20 $( 6 6 . 9 \% )$ in 2014:approximately $8 5 \%$ of the land of the country was under serious desertification，which significantly occurred in arid and semi-arid lowlands of the country (eastern, northern,and western lowlands） with relatively scarce precipitation and high temperature. The non-desertified area,mostly located in the sub-humid eastern escarpment, also declined from approximately $2 . 1 \%$ to $0 . 5 \%$ . The study concludes that the desertification is a cause of serious land degradation in Eritrea and may link to climate changes, such as low and unpredictable precipitation, and prolonged drought.

Keywords:desertification;Landsat images;NDVI index;SPI analysis; Eritrea

Citation:Mihretab G GHEBREZGABHER,YANG Taibao,YANG Xuemei, WANG Congqiang.2019.Assssment of desertification inEritrea:landdegradation based on Landsat images.Journal of Arid Land,1l(3):319-331. https://doi.0rg/10.1007/s40333-019-0096-4

# 1Introduction

Land degradation in arid,semi-arid and sub-humid areas is described as desertification, which is the response to human factors as well as climate change (McGlynn and Okin, 20o6; Veron et al., 2006; Xue et al.,2009; Xu et al., 2010; Cui et al., 2011; Lam et al., 2011; Dawelbait and Morari, 2012; Wang et al., 2012; D'Odorico et al., 2013; Li et al., 2013; Xue et al.,2013; Zhou et al., 2013; Dardel etal.,2014; Ghebrezgabher et al., 2014; Becerril-Pina et al.,2015; Wu et al.,2015; Lamchin et al.,2O16). Desertification is the most serious form of environmental degradation that covers $40 \%$ of the global land surface (Veron et al., 2006; Wang et al., 2012; Sun,2015; Zandler et al.,2015),affecting Africa in particular. Desertified land covers approximately one third of the continent of Africa including the Sahara, southern Africa (Kalahari and Namibia) and east Africa (Eritrea,Ethiopia, Somalia and Sudan) (Senut et al., 2Oo9).Although scientists consider that desertification has a strong association with human activities related to agricultural expansion, overgrazing, deforestation and urbanization， climate change， such as infrequent, erratic precipitation, drought and high evapotranspiration, may also cause desertification. The impact of climate change on desertification is very complex (Xue et al., 2009; Zhou et al.,2013; Landmann and Dubovyk,2014; Xu et al.， 2014; Becerril-Pina et al.， 2015). Desertification is a more significant environmental issue in less developed countries than in rich ones (Seely et al., 2008) and has a serious impact on the poorest populations of the world (Verstraete et al., 2008).

Climate change caused frequent and prolonged drought in Africa, particularly in the Horn of Africa (Senut et al., 2009). As an indicator of climate change (Senut et al., 2009; Stringer et al., 2009; Vicente-Serrano et al.， 2012； Gao and Zhang，2016)， drought may accelerate desertification-related land degradation and adversely afect household wellbeing (Stringer et al., 2009).The reduction of precipitation in the 197Os and 1980s in Africa, mainly in the Sahelian countries,caused moderate to severe drought and increased desertification (Voortman, 1998; Nyssen et al.,2004; Xue et al., 2009; Batisani and Yarnal, 2010; Hein et al., 2011; Brandt et al., 2014). The droughts in 1973-1974,1984,the 1990s and 2000s affected a large number of people in Ethiopia (Nyssen et al.,2004; Conway and Schipper,2011; Dardel et al.,2014) and Eritrea.

Remote sensing is an effective way in monitoring and managing desertification dynamics globally. Desertification has a direct association with the loss of production capacity in an ecosystem. Degradation of vegetation, soil properties and ecosystem production are all indicators of desertification (McGlynn and Okin, 2006; Wang et al., 2012; D'Odorico et al.,2013; Brandt et al.,2014; Ghebrezgabher et al., 2014; Xu, 2014; Zandler et al., 2015). Remote sensing data is more eficient in terms of cost, time and mapping of land degradation than fieldwork and it is productive when combined with GIS (Bakr et al.,2012). Different vegetation index models have been developed to monitor desertification and classify land use from remote sensing images.The most common vegetation indexes are NDVI (normalized difference vegetation index), SAVI (soil adjusted vegetation index), MSAVI (modified soil adjusted vegetation index) (Xu et al., 2009; Cui et al.,2011; Dawelbait and Morari, 2012; Li et al.,2014; Yang et al.,2014) and albedo index (Ma et al., 2011; Lamchin et al., 2016). NDVI is the index most commonly used to analyze vegetation cover (Hill et al.,2008; Cui et al., 2011; Li et al.,2013; Landmann and Dubovyk, 2014; Yang et al.,2014; Lamchin et al.,2O16) and can be used to analyze the relationship between vegetation and precipitation, particularly in the Sahelian countries (Herrmann et al., 2Oo5). Without prior knowledge of the condition of a region, changes in vegetation can be observed using the NDVI analysis method from local to global scales (Petta et al.,2O13; Dardel et al., 2014).

This study aims to monitor and analyze the dynamics of desertification and to assess the climate change as a driving factor in Eritrea. We used vegetation indexes of NDVI, VCP (vegetation cover proportion) and SAVI to quantify the degree of desertified land in the 1970s, 1980s and 2014 based on Landsat data with the help of ENVI 4.7 and ArcGIS 9.3. We found the NDVI to be the most useful measure of vegetation change and hence desertification. Desertified land refers to a place that has already been subject to desertification in this study.

# 2Materials and methods

# 2.1 Study area

Eritrea is a small country（ $( 1 2 ^ { \circ } 2 2 ^ { \prime } - 1 8 ^ { \circ } 0 2 ^ { \prime } \mathrm { N }$ ， $3 6 ^ { \circ } 2 6 ^ { \prime }  – 4 3 ^ { \circ } 1 3 ^ { \prime } \mathrm { E }$ ； Fig.1） situated in the Horn of Africa,bordered with Ethiopia to the south, the Red Sea to the east, Djibouti to the southeast and Sudan to the west. The area of the country is $0 . 1 2 5 { \times } 1 0 ^ { 6 } \mathrm { k m } ^ { 2 }$ and the population is about $6 . 3 \times 1 0 ^ { 6 }$ ： Eritrea is one of the poorest countries in Africa (Ogbazghi and Bein, 2O06). The agriculture, herding and fishing are the primary economic activities, involving about $80 \%$ of the population.

Eritrea has a very complex topography, including mountains, plateaus, hills,valleys, highlands, lowlands and escarpments. The elevation of the country ranges from below sea levels in the north to about $3 0 1 3 \mathrm { \ m } \mathrm { a } . \mathrm { s } . 1 .$ . in the south.The climate varies with the topography as well. It is hot in the lowlands and cold in the highlands. The amount of precipitation also varies between the lowlands and highlands, where the eastern escarpment receives the highest annual precipitation (above 900 $\mathrm { { m m } / \mathrm { { a } } } )$ ). Land degradation is severe in the country where arid and semi-arid land predominates.

Thus,desertification,deforestation,and soil erosion are the major environmental problems, which are mainly caused by human activities and climate variations such as frequent and prolonged drought (Teklay, 1999; Nyssen et al.，2004; Ogbazghi and Bein,2006; Tekeste et al.,2007; MLWE,2012; Ghebrezgabher et al., 2014).

35E 37E 39E 41E 43E 45E 47°E 49°ESDLMDLSLDL200 PortSudan WDLNDL 200+ Saudi ArabiaNo81 Sudan RedSea No81FitrN91 aMassawa Yemen N91NoI Gedaref 9 NoMekele+ Asseb Aden LegendNoI Ethiopia DjiboutiGulf of Aden Ligh:1m NoZI0 320km + Neighbor countriesL Weatherstation35 37E 39E 41E 43°E 45°E 47°E 49E

# 2.2 Data and methods

# 2.2.1 Landsat data selection

Remote sensing data for this study were freely downloaded from the United States Geological Survey (htps://www.usgs.gov) and the free of cloud cover images were chosen. The MSS Landsat_1, MSS Landsat_5 and $\mathrm { E T M ^ { + } }$ Landsat_7 were downloaded for the 1970s,1980s and 2014.We selected 13 images from the 1970s,15 images from the 1980s and 2014, with 57,60 and $3 0 \mathrm { ~ m ~ }$ spatial resolutions,respectively. The projection of the satellite data used here ranges from Zone 36N to 38N at datum WGS-84 and was scanned at different sun elevations.The DEM (digital elevation model) for this study was obtained from the Shutle Radar Topography Mission (http://gdem.ersdac.jspacesystems.or.jp/search.jsp).

# 2.2.2 Climate and population data

The annual population data for the period 1960-2013 were freely downloaded from https://www.quandl.com/data/UN/DEV_POPULATIONTOTAL_ERI-Population-Total-Eritrea and validated at http://data.un.org/browse.aspx. The gridded mean annual precipitation and annual mean temperature (1970-2010; with 0.25-degree resolution) were obtained from the University of Delaware at http://climate.geog.udel.edu/\~climate/html_pages/download.html. For temporal and spatial analysis, we selected 1O weather stations within and outside Eritrea (Fig. 1). A linear trend and standardized precipitation index (SPI) (McKee et al.,1993; Li et al., 2014; Karabulut, 2015; Gao and Zhang,2O16) were used to analyze the trend of climate change and drought conditions (Table1).The SPIis defined as Equation 1.

$$
\mathrm { S P I } { = } P _ { \mathrm { A m } } { - } P _ { \mathrm { L m } } / S _ { \mathrm { n } } ,
$$

where $P _ { \mathrm { A m } }$ is the monthly average precipitation (mm); $P _ { \mathrm { L m } }$ is the mean annual precipitation (mm);   
and $S _ { \mathrm { n } }$ is the standard deviation.

# 2.2.3Landsat image pre-processing

Satellite image pre-processing was carried out in ENVI 4.7. The red and near infrared bands were imported and calibrated. The geometrical and atmospheric corrections were also applied.We used a layer-stacking tool to convert the red and near infrared bands into a layer file and mosaicked them into a single file for each period. The nearest-neighbor resampling method was used in datum WGS-84 and a building mask was applied to fill the gap in the $\mathrm { E T M ^ { + } }$ Landsat images.The mosaicked images were projected at WGS-84 datum, zone 37N and resampled to $3 0 \mathrm { - m }$ spatial resolution. The masking method was applied to extract the study area from the Landsat images (Ma et al., 2011; Petta et al., 2013).

Table 1Extremity of drought conditions based on the SPI (standardized precipitation index)   

<html><body><table><tr><td>SPI</td><td>Extremity of drought</td></tr><tr><td>0.00 to -0.99</td><td>Mild</td></tr><tr><td>-1.00 to -1.49</td><td>Moderate</td></tr><tr><td>-1.50 to -1.99</td><td>Severe</td></tr><tr><td><-2.00</td><td>Extreme</td></tr></table></body></html>

# 2.3 Selection of indices

# 2.3.1Normalized difference vegetation index (NDVI)

The NDVI is the most widely used index to classify desertified land (Xu et al., 2Oo9; Cao et al., 2011; Cui et al.,2011; Dai et al.,2011; Ma et al.,2011; Yang et al.,2014). Vegetation indices based on remote sensing data are most relevant for determining the proportion of vegetation cover. The NDVI index was used to estimate the spatial distribution of vegetation change in Eritrea from the 1970s to 2014. The NDVI is more sensitive to the present vegetation conditions, with photosynthetically active radiation,as it is measured from red and near infrared bands (Elhadi and Zomrawi, 2009; Petta et al.,2013). The value of the NDVI was low in this study and may have been affected by soil brightness. Thus,locally， the NDVI value in forested land (non-desertified land) was above 0.315 and less than 0.101 in strongly desertified land (Table 2). NDVI is given as:

$$
\mathrm { N D V I } { = } \frac { ( \mathrm { N I R - r e d } ) } { ( \mathrm { N I R + r e d } ) } ,
$$

where NIR and red refer to near infrared and red bands,respectively

# 2.3.2 Vegetation cover proportion (VCP)

The VCP describes the density of vegetation based on the branches,leaves and stems of trees or vegetation. The VCP relies on the maximum and minimum NDVI, which respectively, refers to vegetation and soil cover (Cui et al., 2O11). The VCP value is positive, varying between O and 1 (Wang et al.,2012). In this paper, values of $\mathrm { V C P } { < } 0 . 5 4$ , 0.54-0.58, 0.58-0.61 and 0.61-0.64 indicate strongly, moderately, slightly and weakly desertified lands, respectively; and $\mathrm { V C P { > } } 0 . 6 4$ is non-desertified land (Table 2). The VCP is calculated as:

$$
\mathrm { V C P } { = } \frac { \left( \mathrm { N D V I - N D V I } _ { \mathrm { M N } } \right) } { \left( \mathrm { N D V I } _ { \mathrm { M A X } } - \mathrm { N D V I } _ { \mathrm { M N } } \right) } ,
$$

where NDVIMAx and NDVIMIN are the maximum and minimum values of NDVI, respectively, that refer to the values of NDVI associated with vegetation and soil.

# 2.3.3Soil adjusted vegetation index (SAVI)

The NDVI value is the total reflection of a given pixel, in which the amount of soil brightness directly or indirectly influences the NDVI of vegetation. Therefore, the soil adjusted vegetation index (SAVI) method has been developed to minimize the effect of soil brightness in the NDVI value, particularly in arid and semi-arid regions,where sparse vegetation cover is typical. The SAVI depends on near-infrared and red bands, with a constant "L" factor to adjust the influence of soil brightness (Huete,1988; Gilabert et al., 2002; Aggarwal and Minz,2013). The L factor is zero in a highly vegetated canopy, which is the same as the NDVI value.However, the L factor is 0.5 for a very sparsely vegetated canopy and is 1.0 for a moderately vegetated canopy. Since more than $70 \%$ of the study area is either arid or semi-arid land (MLWE,2012), the SAVI is significant. The L was O.5 to be applied to all pixels except in some areas under a very highly vegetated canopy. Values of $\mathrm { S A V I { > } } 0 . 6 8$ and $\mathrm { S A V I } { < } 0 . 5 0$ are considered as non-desertified and strongly desertified land, respectively (Table 2).The SAVI is defined as:

$$
{ \mathrm { N D V I } } = { \frac { ( { \mathrm { N I R } } - { \mathrm { r e d } } + { \mathrm { L } } ) } { ( { \mathrm { N I R } } + { \mathrm { r e d } } + { \mathrm { L } } ) } } ,
$$

where NIR is a near-infrared band; red refers to the red band; and L is the constant factor   
Table 2Desertified land types from NDVI and vegetation cover from VCP and SAVI   

<html><body><table><tr><td>Degree of desertified land</td><td>NDVI</td><td>VCP</td><td>SAVI</td></tr><tr><td>Strongly</td><td><0.101</td><td><0.54</td><td><0.50</td></tr><tr><td>Moderately</td><td>0.101-0.145</td><td>0.54-0.58</td><td>0.50-0.56</td></tr><tr><td>Slightly</td><td>0.145-0.215</td><td>0.58-0.61</td><td>0.56-0.60</td></tr><tr><td>Weakly</td><td>0.215-0.315</td><td>0.61-0.64</td><td>0.60-0.68</td></tr><tr><td>Non</td><td>>0.315</td><td>>0.64</td><td>>0.68</td></tr></table></body></html>

Note:NDVI,oralizeddifrenceegetationidex;VCPegetationoerproportion;SVI,soiladjustedvegetatiodex

# 2.4 Classification assessment

The assessment of classification for the different desertification grades was completed using a decision tree (DT) method. The DT is a useful non-parametric method (Obade and Lal, 2013) in the evaluation of variations in the land surface due to desertification stress.It is one of the most common methods of land use classification from remote sensing data. Researchers have used the method to assess the degree of desertification and classify vegetation changes using different indexes, in particular the NDVI (Xu et al., 2009; Ma et al., 2011; Xu et al., 2014, Yang et al., 2014; Lamchin et al., 2016).

In this study, a DT model was completed using samples selected from fieldwork at a local area to identify indices for each desertification category,and then applied to the whole study area. In addition,a high resolution Google Earth DEM was used as a reference to enhance the accuracy of classification (Fig. 2). We selected 200,150,120,100 and 80 samples for strongly, moderately, slightly, weakly and non- desertified lands,respectively, to control and determine the threshold value for each grade of desertification in recent years. The average threshold values were investigated for each vegetation index (Table 2). For instance，the NDVI value for the non-desertified land under forest cover， which was determined from data available at http://www.fao.org/forestry/country/18314/en/eri/ (FAO， 2000)， waslower than expected (approximately ${ > } 0 . 3$ ） due to the low density of the forest.We proposed that the NDVI ${ > } 0 . 3 1 5$ is an average value for non-desertified land and the NDVI $< 0 . 1 0 1$ can be considered as strongly desertified land.We applied the same threshold value for each class in the 197Os and 1980s images to avoid biases.All types of land cover in the three periods were scaled to display comparable information. The DT rule was developed for the strongly, moderately， slightly, weakly and non-desertified lands to analyze and evaluate the progress of desertification in 1970s2014) (Fig. 3).

![](images/096da9dfb50624e5bb599921248328f4b5c19dc89d8f2169be8f82828876a867.jpg)  
Fig.2Representative Google Earth image selected for each grade of desertified land for Eritrea in 2014

![](images/dc5c9f604bf45b3dad2aa154d05e1f6593ffbd5b5076560a99711a0f0af33fa4.jpg)  
Fig.3Flowchart for desertification levels based on the DT(decision tree） method.NDVI,normalized difference vegetation index; VCP, vegetation cover proportion; SAVI, soil adjusted vegetation index.

The land cover classification is very limited in Eritrea although the desertification and land degradation are major environmental issues. The Ministry of Agriculture (MOA)，and the Ministry of Land, Water and Environment of Eritrea,and the international organizations such as UNCCD (United Nations Convention to Combat Desertification)， UNDP (United Nations Development Program) and IGAD (Intergovernmental for African Development） have reported that desertification land degradation is underway in Eritrea. Different programs have been designed and implemented for soil conservation and to tackle desertification. However, there haven't being a land use map available for mapping the desertification changes. The study reported in this paper might be useful as a literature in this area for further study.

The Food and Agricultural Organization (FAO) plays a great role in classification of land cover change in Africa,including Eritrea. FAO (2O1O) found that deforestation was serious in Eritrea. According to the Africover project (http://www.glcn.org/activities/africover_en.jsp), only $14 \%$ of the study area is suitable for cultivation, also indicating that desertification is underway in Eritrea.

# 3 Results

# 3.1Dynamics of desertified land

According to the NDVI,VCP and SAVI, desertification continued in Eritrea for the last four decades (Table 3). Land with an NDVI value ${ \tt < } 0 . 1 0 1$ and $\mathrm { V C P } { < } 0 . 5 4$ is considered to be strongly desertified, whereas land with an NDVI value ${ > } 0 . 3 1 5$ or $\mathrm { V C P } { > } 0 . 6 4$ isclassified as non-desertified. The area suffering from strong desertification increased from $4 . 8 2 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ $( 3 8 . 5 \% )$ in the 1970s to $8 . 3 8 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 } ( 6 6 . 9 \% )$ in 2014.The areas with moderate, slight and weak desertification decreased as a consequence of the increase of desertification. The non-desertified land declined from $2 5 5 7 \mathrm { k m } ^ { 2 } \left( 2 . 0 \% \right)$ in the 1970s to only $6 4 1 \ \mathrm { k m } ^ { 2 } \left( 0 . 5 \% \right)$ in 2014.

Desertification is an ongoing environmental problem in Eritrea and is severe in western, northwestern and southeastern study area. In the 197Os, the strongly desertified land dominantly appeared in eastern and northwestern study area (Fig. 4). A significant part of western and southwestern of the study area was under moderate to slight desertification, but the south and the majority of the central highlands, eastern and western escarpments were under good vegetation cover. The results are in consistency with the land cover information from the Africover project. During 1980s-2014, desertified land increased in eastern, northern and western of the study area, and the vegetation cover dramatically decreased in the highlands,and northeastern and western escarpments. Vegetation cover remained stable in a small portion of Eritrea around the eastern and southwestern country, along with the Setit River, which was in agreement with Africover as well. In 2Ol4,the southwestern and central highlands of the study area were dominated by the moderately and slightly desertified lands.

Table3Desertified land dynamics based on the NDVIof the 197Os,the 1980s and 201   

<html><body><table><tr><td rowspan="2">Degree of desertification</td><td colspan="2">1970s</td><td colspan="2">1980s</td><td colspan="2">2014</td></tr><tr><td>Area (km²)</td><td>Area percentage (%)</td><td>Area (km²)</td><td>Area percentage (%)</td><td>Area (km²)</td><td>Area percentage (%)</td></tr><tr><td>Strongly</td><td>48,165</td><td>38.5</td><td>60,724</td><td>48.5</td><td>83,791</td><td>66.9</td></tr><tr><td>Moderately</td><td>37,494</td><td>29.9</td><td>35,100</td><td>28.0</td><td>23,556</td><td>18.8</td></tr><tr><td>Slightly</td><td>21,055</td><td>16.8</td><td>20,689</td><td>16.5</td><td>15,229</td><td>12.2</td></tr><tr><td>Weakly</td><td>15,967</td><td>12.8</td><td>7289</td><td>5.8</td><td>3333</td><td>2.7</td></tr><tr><td>Non</td><td>2557</td><td>2.0</td><td>1435</td><td>1.2</td><td>641</td><td>0.5</td></tr></table></body></html>

![](images/123bfc84989e13b20fff339a4733e43386ac8f37e8b42c525f666cc70cc06969.jpg)  
Fig.4Distributionand location of desertified land in the 197Os,the 1980s and 2014 based on theNDVI values

# 3.2 Desertified land change detection

Table 4 presents the changes of desertified lands in 1970s-1980s,1980s-2014 and 1970s-2014. The results demonstrate that the strongly desertified land expanded from $1 . 2 6 \times 1 0 ^ { 4 }$ to $2 . 3 1 \times 1 0 ^ { 4 }$ $\mathrm { k m } ^ { 2 }$ in the 1970s-1980s and 1980s-2014, respectively (Table 4). As strongly desertified land expanded， the area for moderately， slightly and weakly desertified lands decreased. The percentage of desertification decreased in the "moderately" and the "slightly" categories from $1 . 9 \%$ to $9 . 2 \%$ and from $0 . 3 \%$ to $4 . 3 \%$ ,respectively, in the 1970s-1980s and the 1980s-2014. As the strongly desertified land increased, the other land cover types gradually reduced. We found that approximately $3 . 5 6 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ of land became infertile due to the expansion of strongly desertified land and the non-desertified land reduced by $1 . 6 \%$ in 1970s-2014.

Table 4 Desertified land changes from the 197Os to 2014   

<html><body><table><tr><td rowspan="2">Degree of desertification</td><td colspan="2">1970s-1980s</td><td colspan="2">1980s-2014</td><td colspan="2">1970s-2014</td></tr><tr><td>Area change (km2)</td><td>Area phange (%</td><td>Area change (km2)</td><td>Area phange (%)</td><td>Area change (km2)</td><td>Area phange (ge</td></tr><tr><td>Strongly</td><td>12,559</td><td>10.0</td><td>23,067</td><td>18.4</td><td>35,626</td><td>28.4</td></tr><tr><td>Moderately</td><td>-2394</td><td>-1.9</td><td>-11,544</td><td>-9.2</td><td>-13,938</td><td>-10.4</td></tr><tr><td>Slightly</td><td>-366</td><td>-0.3</td><td>-5460</td><td>-4.3</td><td>-5826</td><td>-4.6</td></tr><tr><td>Weakly</td><td>-8678</td><td>-7.0</td><td>-3956</td><td>-3.1</td><td>-12,634</td><td>-10.1</td></tr><tr><td>Non</td><td>-1122</td><td>-0.6</td><td>-794</td><td>-1.0</td><td>-1916</td><td>-1.6</td></tr></table></body></html>

# 3.3 Annual changes of desertified land

In the last four decades,the annual rate of desertification increased in the strongly desertified land while the rate of desertification was decrease in the other degrees of desertification and non-desertified land (Table 5).The highest annual rate $( 9 6 1 . 1 ~ \mathrm { k m } ^ { 2 } / \mathrm { a } )$ ）of desertification appeared in the strongly desertified land in 1980s-2014, while the highest rate of decline recorded in the moderately and slightly between 1980s and 2O14. The weakly and non-desertified lands were lost at the annual rates of $1 . 8 \%$ and $1 . 7 \%$ ,respectively, from the 1970s to 2014.

Table 5Annual rate of desertified land in the 197Os-2014   

<html><body><table><tr><td rowspan="2">Degree of desertified land</td><td colspan="2">1970s-1980s</td><td colspan="2">1980s-2014</td><td colspan="2">1970s-2014</td></tr><tr><td>Annual rate deserifieation</td><td>Percentage</td><td>Annual rate desertifiation</td><td>(%)</td><td>Annual rate deserifiation</td><td>Percentage</td></tr><tr><td>Strongly</td><td>(km2/a) 626.7</td><td>1.30</td><td>(km2/a) 961.1</td><td>1.58</td><td>(km²/a) 809.7</td><td>1.68</td></tr><tr><td>Moderately</td><td>-119.7</td><td>-0.32</td><td>-481.0</td><td>-1.37</td><td>-316.8</td><td>-0.85</td></tr><tr><td>Slightly</td><td>-18.3</td><td>-0.09</td><td>-227.5</td><td>-1.10</td><td>-132.4</td><td>-0.63</td></tr><tr><td>Weakly</td><td>-433.9</td><td>-2.72</td><td>-164.8</td><td>-2.26</td><td>-287.1</td><td>-1.80</td></tr><tr><td>Non</td><td>-56.1</td><td>-2.20</td><td>-33.8</td><td>-2.36</td><td>-43.5</td><td>-1.70</td></tr></table></body></html>

# 3.4 Climate and population

Figure 5 demonstrates that the annual precipitation and temperature increased from 1970 to 2010 at rates of $0 . 2 4 ~ \mathrm { m m / a }$ and $0 . 0 2 7 ^ { \circ } \mathrm { C } / \mathbf { a }$ ，respectively. However, the mean annual precipitation was not significant at the $9 5 \%$ level $scriptstyle \cdot R ^ { 2 } = 0 . 0 0 3 2$ ， $P { = } 0 . 7 2 4 )$ ，whereas temperature increased very significantly at $9 9 \%$ level $R ^ { 2 } { = } 0 . 7 5$ $P { = } 0 . 0 0 0 6$ ). In this study, drought condition relies on the level of precipitation, the lower precipitation and longer period of time is insufficient for the demand of human activities and environment.We determined the level of precipitation based on the SPI value.Figure 5 indicates that dryness was recorded throughout the study period, that moderate drought occurred in the mid- and late-1970s and from early the 1980s to 1990,and that severe to extremely severe drought was recorded in 1984,1990,1991,2008 and 2009.The annual increase in total population from 1960 to 2013 was significant at $9 9 \%$ $R ^ { 2 } { = } 0 . 9 4 \$ ）

# 4Discussion

Desertification is a serious cause of land degradation, which is mainly brought about by climatic changes， such as precipitation variability, temperature change,drought and human factors including land use change and population explosion (MOA, 2002; Xue et al., 2009; Ghebrezgabher et al.,2014; Xu et al.,2014). In this study, the results demonstrate that strongly and moderately desertified lands were respectively $8 . 3 8 \times 1 0 ^ { 4 }$ （20号 $( 6 6 . 9 \% )$ and $2 . 3 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ $( 1 8 . 2 \% )$ in 2014,indicating that about $8 5 \%$ of Eritrea was dominated by degraded land. Furthermore, aridity increased by approximately $9 \%$ from 2012 to 2014 for the agro-ecological zone of Eritrea (MLWE,2O12). The woodland, grassland and cultivated lands defined by Africover were about $3 3 . 2 \%$ ， $1 8 . 8 \%$ and $1 4 . 2 \%$ of the total area,respectively. The data from Africover indicate that about $3 3 . 8 \%$ of the country has no vegetation, and about $8 5 \%$ is not productive for agriculture, which are consistent to the results of this study. Generally, the humid part of the study area is slightly or weakly desertified，whereas the dry part is strongly or moderately desertified. Moreover, the northeastern, southeastern,and western parts of the study area are covered by sand, barren land,rocky and black volcanic soils, where the lands are strongly desertified and negative NDVI values are observed in some areas.

![](images/c826f890d397980209c85d7afa160ea71c4f0e7ba92f1e49d6e713c13e20c3e8.jpg)  
Fig.5Changes of annual precipitation (a),annual mean temperature (b),standardized precipitation index (SPI) (c) and population (d) in Eritrea

Vegetation cover assessment based on Landsat data is the most common method of studying desertification. The DT classification method based on the vegetation indices mentioned above is suitable for monitoring and analyzing desertification dynamics, because it is highly sensitive to climate change, particularly in arid and semi-arid areas (Huang and Siegert, 2Oo6). However, the driving factors on a pixel basis are difficult to investigate and identification of the appropriate parameters as well as the choice of a suitable spatial-temporal scale is essential for correctly detecting the ecosystem and assessing its sensitivity to desertification.

In this study, we found that the vegetation cover decreased, which is in line with the findings of Landmann and Dubovyk (2O14),although their study focused on human factors and the reduction of vegetation, particularly forest in Kenya and eastern Africa as a whole. The non-desertified land (possibly the forest land) in Eritrea dramatically decreased from $2 . 0 \%$ in the 1970s to $0 . 5 \%$ in 2014.This result is lower than the amount of highland forest cover $( 0 . 8 \% )$ reported by MOA (2002) in the country.

The mean annual precipitation decreased and annual mean temperature increased in Eritrea from the 1960s to 2013. Summer precipitation seriously declined in the 1960s,1970s,1980s, 1990 and 1991,caused severe drought in Eritrea and the Sahel regions (Nyssen et al., 2004; Conway and Schipper,2011; MLWE,2012; Ghebrezgabher et al., 2014). This drought possibly caused vegetation cover to decline and increased desertification. Since the high temperature and low precipitation are indicators of high rates of evapotranspiration and land dryness, climate warming may have a great role in desertification growth in Eritrea (MAO, 2002; MLWE, 2012). Commonly, the growth of vegetation increases with rising temperature and precipitation. The vegetation cover will decrease and the rate of desertification intensifies when imbalance in the rate of evapotranspiration and amount of precipitation occurs (Xue et al., 2O09). Thus, the main climate threats in Eritrea relate to precipitation variability, including little amount, short duration and less intense rainfall, may lead to drought,and rarely cause flooding in the case of heavy rainfall (MOA, 2Oo2). Climate change may be a significant factor that induces desertification in the study area, particularly areas under extremely high temperature and extremely low precipitation (Fig. 6). However, areas under slight or weak desertification are prevalent and human factors are probably be more significant. An indirect correlation derived between the degrees of desertification and elevation of the study area is that the lower the elevation, the higher the degree of desertification. The strongly and moderately desertified lands are found below 600 m and between 6oo and $1 0 0 0 \mathrm { ~ m ~ }$ ；whereas,the weakly and non-desertified lands are mostly appeared above $1 5 0 0 \ \mathrm { m }$ .In other words, $4 4 . 7 \%$ of the area found below $6 0 0 ~ \mathrm { m }$ ，more than $70 \%$ （204号 below $1 0 0 0 \mathrm { m }$ ,and only $4 . 2 \%$ of the area is above $2 0 0 0 \mathrm { m }$ (Fig. 6).

![](images/9a6ac5735d6e1ee0ac572cd97bf7cdeda44e29f14b4bb55a6c0fd48d7d1cef63.jpg)  
Fig.6Spatial distribution of precipitation,temperature (1970-2010) and elevation of the study area

# 5 Conclusions

In Eritrea,desertification was serious in the last four decades, especially in the margins of deserts, and western and eastern parts of the country. The strongly desertified land started to expand since 1970s while the moderately and weakly desertified lands shrank. The non-desertified land (perhaps the forest land) was also seriously declined in the last 4O a. The annual mean temperature significantly increased since 197Os while the annual precipitation was relatively stable.Drought is a serious problem in the study area, with moderate drought recorded throughout the study period and sometimes severe drought adversely affecting the country. Population increased as well since l96Os, which might be a cause of desertification due to increasing demand for farming, firewood and grazing. This study revealed that precipitation and temperature are important to the desertification in the study area although human factors have major impacts on desertification and land degradation as well. Therefore, immediate actions are required to preserve land to avoid further desertification, particularly in the highlands and southwestern part of the study area where the areas are dominated by slightly and weakly desertified lands.

# Acknowledgements

This work was supported by the National Natural Science Foundation of China (41271024).We express our thanks to all members of the Institute of Glaciologyand Eco-Geography,Colege of Earth and Environmental Sciences,Lanzhou University for their valuable advices. We would like to express our deepest appreciation to the Editage/CACTUS,language editing company for checking the general language of this manuscript. The authors also appreciate to Mr. Goush FISSEHATSION and Mr. Wesley CHERUIYOT for their language checking.

# References

Aggarwal HK,Minz S,2O13.Change detectionusingunsupervised learningalgorithms for Delhi,India.AsianJourmalof Geoinformatics,13(4),11-15.   
BakrN,WeindorfDC,BahanassyMHetal0l2.ulti-temporalassessmentoflandsensitivitytodesertificationinfragile agro-ecosystem: Environmental indicators.Ecological Indicators,15(1): 271-280.   
BatisaniN,YarnalB.20l0.Rainfallvariabilityandtrends insemi-arid Botswana:Implications forclimatechangeadaptation policy. Applied Geography,30(4): 483-489.   
Beceril-PiaR,Mastach-LozaCA,Gonzalez-SosaE,etal.20l5.Assessngdesertificationiskinthesem-aridhiglandsof central Mexico.Journal of Arid Environments,120: 4-13.   
BrandtM,Romankiewicz C,SpekrmannR,etal.2014.Environmentalchangein time series-Aninterdisciplinarysudyinthe Sahel of Mali and Senegal. Journal of Arid Environments,105: 52-63.   
Cao XH,ChenX,BaoAM,etal.2011.Responseofvegetationtotemperatureand precipitationin Xinjiangduringtheperiod of 1998-2009.Journal of Arid Land,3(2): 94-103.   
ConwayD,SchipperELF.2O11.Adaptationtoclimate change inAfrica: ChallengesandopportunitiesidentifiedfromEthiopia. Global Environmental Change,21(1): 227-237.   
Cui G,Lee WK,Kwak DA,etal.2011.Desertification monitoringbyLANDSATTMsatelite imagery.Forest Scienceand Technology, 7(3): 110-116.   
Dai S P,Zhang B,Wang HJ,etal.2011.Vegetationcoverchange and thedriving factorsover northwest China.Journalof Arid Land,3(1): 25-33.   
Dardel C,KergoatL,Hiernaux P,etal.2O14.Re-grening Sahel:30yearsofremotesensingdataandfieldoservations (Mali, Niger).Remote Sensing of Environment,140: 350-364.   
Dawelbait M,MorariF.2O12.Monitoring desertification ina Savannah region in Sudan usingLandsat imagesand spectral mixture analysis. Journal of Arid Environments,80: 45-55.   
DOdorico P,BhattahanA,DavisKF,etal.20l3.Globaldesertification:Driversand feedbacks.Advances in WaterResources, 51: 326-344.   
Elhadi E M, Zomrawi N,Hu GD.2O09.Landscape change and sandydesertificationmonitoring and assessment.American Journal of Environmental Sciences,5(5):633-638.   
FAO (FoodandAgriculturalOrganizationofthe United Nations).2oooNatural forestformation,Eritrea,forestcover map. [2011-12-14]. htp://www.fao.org/forestry/country/18314/en/eri/.   
FAO.2010.Countryreport Eritrea,Global Forest Resources Assssment (FRA),Foodand Agricultural Organizationof the United Nations,FRA2010/063,Rome. htp://www.fao.org/3/al499E/al499e.pdf.   
Gao L,Zhang Y.2016.Spatio-temporal variationofhydrological drought under climate change during the period1960-2013 in the Hexi Corridor, China. Journal of Arid Land, 8(2): 157-171.   
Ghebrezgabher MG,Yang T,Yang X.2014.Remote Sensing and GISanalysis ofdeforestationand desertificationincentral highland and easternregionofEritrea (1972-20l4).International Journal of Sciences:BasicandApliedResearch,18(2): 161-176.   
GilabertMA,Gonzalez-PiquerasJ,Garcia-HaroFJ,etal.2o2.Ageneralizedsoil-adjusted vegetationindex.Remote Sensing of Environment. 82(2-3):303-310.   
HeinL,deRidderN,HierauxP,etal0l1.Desertificationinthe Sahel:Towardsbeteraccounting forecosystmdamicsin the interpretation of remote sensing images.Journal of Arid Environments,75(11): 1164-1172.   
HerrmannSM,AnyambaA,TuckerCJ.2Oo5.Recent trendsinvegetationdyamics intheAfrican Sahelandtheirrelatioship to climate. Global Environmental Change,15(4): 394-404.   
HillJ,Stellmes M,UdelhovenTH,etal.o8.Mediterraneandesertificationandlanddegradation: Mappingelatedlanduse change syndromes based on satelite observations.Global and Planetary Change,64(3-4):146-157.   
Huang S,SiegertF.2O06.Landcoverclassificationoptimizedtodetectareas atriskofdesertification inNorthChinabasedon SPOT VEGETATION imagery. Journal of Arid Environments,67(2): 308-327.   
Huete AR.1988.A soil-adjusted vegetation index (ASVI).Remote Sensing of Environment,25(3): 295-309.   
Lam D K,Remmel T K,Drezner T D.2011Tracking desertification in California using remote sensing:A sand dune encroachment approach. Remote Sensing,3(1):1-13.   
Lamchin M,Lee JY,Lee WK.2016.Asessmentoflandcover change and desertification using remotesensingtechnology in a local region of Mongolia.Advances in Space Research,57(1): 64-77.   
Landmann T,Dubovyk O.2014.Spatialanalysis ofhuman-induced vegetationproductivitydecline over eastern Africa usinga decade (2001-20l1)of medium resolution MODIS time-series data.International Journalof Applied Earth Observation and Geoinformation,33:76-82.   
LiJ,YangX,JYetal..oitoigdalyssofssndesrtiicatiodaicssingLandatiagesigxia China.Remote Sensing of Environment,138:19-26.   
LiR,TsunekawaA,Tsubo M.2014.Index-based aessmentofagricultural droughtinasemi-aridregionofIner Mongolia, China. Journal of Arid Land,6(1): 3-15.   
Ma Z,XieY,JiaoJ,etal.20l1.TheconstructionandappicationofanAledo-NDVIbaseddesertificationmonitoringmodel. Procedia Environmental Sciences,10: 2029-2035.   
McGlyn IO,Okin G S.2006.Characterization of shrub distribution using high spatialresolution remote sensing: Ecosystem implications for a former Chihuahuan Desert grassand.Remote Sensing of Environment,101(4): 554-566.   
McKeeTB,DeskenNJ,KleistJ,1993.Therelationshipofdroughtfrequencyanddurationtotime scales.In:Proceedingsof the $8 ^ { \mathrm { t h } }$ Conference on Applied Climatology. California: Anaheim,17-22.   
MLWE (MinistryofLand, Waterand EnvironmentofEritrea).2012.Eritrea's five-year actionplan forGGWIdraft,Asmara, Eritrea.[2012-10-16].http://www.fao.org/3/a-av137e.pdf.   
MOA(Ministryof Agriculture of Eritrea).2002.Thenational action programme for Eritrea tocombat desertification and mitigate thectsofought(),ararirea..htp://ucd.intctirogams/ritred.   
Nyssen J,Poesen J,Moeyersons J,etal.2O04.Humanimpactontheenvironment intheEthiopianandEritrean highlandsa state of the art.Earth-Science Reviews,64(3-4): 273-320.   
Obade VDP,Lal R.2013.Assesing landcover and soilqualitybyremote sensing and geographical information systems (GIS). Catena,104: 77-92.   
Ogbazghi W,BeinE.20o6.Assessmentof non-wood forest products and theirrole inthe livelihoodsofrural communities in the Gash-Barka region,Eritrea.Drylands Coordination Group Report No.40.Oslo,Norway.   
Petta RA,de CarvalhoL VErasmi S,et al.2O13.Evaluationof desertification processes in Seridoregion (NEBrazil). International Journal of Geosciences,4:12-17.   
SeelyM,DirkxE,Hager C,et al.2O08.Advances in desertfication and climate change research:Are they accessible for application to enhance adaptive capacity? Global and Planetary Change,64(3-4): 236-243.   
Senut B,Pickford M,SégalenL.2009.Neogene desertificationof Africa.Comptes Rendus Geoscience,341(8-9):591-602.   
StringerLC,DyerJC,Reed M S,et al.2009.Adaptations toclimate change,drought and desertification: localinsights to enhance policy in southern Africa.Environmental Science & Policy,12(7): 748-765.   
Sun D.2015.Detection of dryland degradation using Landsat spectral unmixing remote sensing with syndrome concept in Minqin County, China.International Journal of Applied Earth Observation and Geoinformation,41: 34-45.   
Tekeste M,Habtzghi DH,Strosnijder L.2007.Soil strength assessmentusing threshold probabilityapproachon soils from three agro-ecological zones in Eritrea.Biosystems Engineering, 98(4): 470-478.   
Teklay M.1999.Earth science education in Eritrea. Journal of African Earth Sciences,28(4): 805-810.   
Verón SR,Paruelo JM,OesterheldM.206.Assessing desertification.Journal ofArid Environments,66(4):751-763.   
Verstraete MM,Brink AB,ScholesRJ,etal.2008.Climatechange anddesertification: Where do we stand, where should we go? Global and Planetary Change,64(3-4):105-110.   
Vicente-SeranoSM,Begueria S,Gimeno L,et al.2012.Chalenges for drought mitigation in Africa:The potentialuseof geospatial data and drought information systems.Applied Geography,34: 471-486.   
VortmanRL.1998.Recent historical climatechangeandits efectonlandusein theeastern partof West Africa.Physics and Chemistry of the Earth,23(4): 385-391.   
Wang T,YanCZSongX,etal.2O12.Monitoringrecent trendsintheareaofaeoliandesertified landusingLandsatimagesin China's Xinjiang region. ISPRS Journal of Photogrammetry and Remote Sensing,68:184-190.   
Wu J,Li Z,GaoZ,etal.2015.Degradedlanddetectionbysoil particlecomposition derivedfrom multispectralremotesensing data in the Otindag Sandy Lands of China.Geoderma,241-242: 97-106.   
XuDY,Kang X,QiuD,etal.2O9.Quantitativeassssmentof dsertificationusing Landsat dataonaregionalsale-case study in the Ordos Plateau, China. Sensors,9(3):1738-1753.   
Xu DY,Kang XW,ZhangDF,etal.20l0.Multi-scalequantitativeassessmentoftherelativerolesofcimatechangeand humanactivitiesindesertification-Acase studyoftheOrdosPlateau,China.JournalofAridEnvironments,74(4):498-507.   
XuDY,LiC,SongX,etal.2O14.Thedamicsofdesertificationinthefarming-pastoralregionofNrthChinaoverthepast 10 years and their relationship to climate change and human activity.Catena,l23:11-22.   
XueX,GuoJ,HanB,etal.2o9.Theefectofclimate warmingand permafrostthawondesertificationintheQinghai-ibetan Plateau. Geomorphology,108(3-4):182-190.   
Xue Z,QinZ,LiH,etal.2O13.Evaluationofaeolian desertificationfrom1975 to2O10anditscausesinnorthwest Shanxi Province,China.Global and Planetary Change,107:102-108.   
Yang X,Yang T,JiQ,etal.2O14.Regional-scalegrasslandclasificationusing moderate-resolution imagingspectrometer datasets based on multistep unsupervised classification and indices suitabilityanalysis.Journal of Aplied Remote Sensing, 8(1):083548.doi: 10.1117/1.JRS.8.083548.   
Zandler H,Brenning A,Samimi C.2O15.Quantifying dwarf shrub biomas inanaridenvironment:comparing empirical methods in a high dimensional setting.Remote Sensing of Environment,158:140-155.   
Zhou W,Sun ZG,LIJL.2Ol3.Desertification dynamicand therelativerolesof climatechange and humanactivities in desertification in the Heihe River Basin based on NPP.Journal of Arid Land,5(4):465-479.