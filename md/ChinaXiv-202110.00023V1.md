# Climate change impacts on the streamflow of Zarrineh River, Iran

Farhad YAZDANDOOST\*, Sogol MORADIAN

Department of Civil Engineering,K.N.Toosi Universityof Technology,Tehran 19697,Iran

Abstract: Zarrineh River is located in the northwest of Iran, providing more than $40 \%$ of the total inflow into theLake Urmia thatis one of the largest saltwater lakes on the earth.Lake Urmiais a highly endangered ecosystem on the brink of desiccation. This paper studied the impacts of climate change on the streamflow of Zarrineh River.The streamflow was simulated and projected for the period 1992-2050 through seven CMIP5 (coupled model intercomparison project phase 5) data series (namely, BCC-CSM1-1, BNU-ESM, CSIRO-Mk3-6-0，GFDL-ESM2G, IPSL-CM5A-LR,MIROC-ESM and MIROC-ESM-CHEM) under RCP2.6 (RCP, representative concentration pathways) and RCP8.5. The model data series were statistically downscaled and bias corrected using an artificial neural network (ANN) technique and a Gamma based quantile mapping bias correction method.The best model (CSIRO-Mk3-6-0) was chosen by the TOPSIS (technique for order of preference by similarity to ideal solution) method from seven CMIP5 models based on statistical indices.For simulation of streamflow,a rainfal-runoff model,the hydrologiska byrans vattenavdelning (HBV-Light) model, was utilized. Results on hydro-climatological changes in Zarrineh River basin showed that the mean daily precipitation is expected to decrease from O.94 and $0 . 9 6 ~ \mathrm { m m }$ in 2015 to 0.65 and $0 . 6 8 \mathrm { m m }$ in 2050 under RCP2.6 and RCP8.5,respectively. In the case of temperature, the numbers change from $1 2 . 3 3 ^ { \circ } \mathrm { C }$ and $1 2 . 3 7 ^ { \circ } \mathrm { C }$ in 2015 to $1 4 . 2 8 ^ { \circ } \mathrm { C }$ and $1 4 . 3 2 ^ { \circ } \mathrm { C }$ in 2050. Corresponding to these climate scenarios, this study projected a decrease of the annual streamflow of Zarrineh River by half from 2015 to 2050 as the results of climatic changes willead to a decrease in the annual streamflow of Zarrineh River from $5 9 . 4 9 ~ \mathrm { m } ^ { 3 } / \mathrm { s }$ in 2015 to 22.61 and $2 3 . 1 9 ~ \mathrm { m } ^ { 3 } / \mathrm { s }$ in 2050. The finding is of important meaning for water resources planning purposes, management programs and strategies of the Lake's endangered ecosystem.

Keywords: climate change; water resources management; climate model intercomparison project phase5 (CMIP5); artificial neural network (ANN);biascorrection; hydrologiska byrans vattenavdelning (HBV-Light); Zarrineh River

# 1 Introduction

Considerable changes in precipitation and temperature regimes in the past few decades, resulting in socio-economic and environmental issues, necessitates hydrological simulations for estimation of future changes in streamflow conditions. Global climate model (GCM),also known as general circulation model, using a mathematical model of the general circulation of a planetary atmosphere or ocean， can be taken into consideration to obtain climate change projections for climatic parameters such as temperature and precipitation (Liu et al.,2O10, 2011; Yazdandoost et al.,2O21).GCM simulations are based on the four global scenarios,RCP (representative concentration

pathways) 2.6, RCP4.5, RCP6.0 and RCP8.5, where RCP2.6 and RCP8.5 are the most optimistic and pessimistic scenarios,based on a possble range of radiative forcing values in 21Oo. Despite the increasing use of GCMs (global climate models),the main problem with them is their coarse resolution, which makes them unable to provide reliable information at the hydrological scales (Maraun et al.,2010). Therefore, using the downscaling approaches in relevant studies has become inevitable (Fowler et al., 2007; Teutschbein and Seibert, 2012; IPCC,2013; McSweeney et al., 2015; Bozkurt et al., 2018; Cai et al., 2018; Khan et al., 2018).

Two major downscaling approaches, dynamical downscaling and statistical downscaling, are often used. Dynamical downscaling methods result in the higher-resolution regional climate models (RCMs), used to preserve the physical coherence between atmospheric and land surface variables (Anderson et al.， 2011). However, the raw RCM (higher-resolution regional climate model) simulations may stillbe biased (Fowler et al.,20o7).The statistical downscaling methods are based on statistical relationships between large-scale atmospheric variables (predictors)and local climate variables (predictands) (Do et al.,2011; Wilby et al., 2014). Compared to dynamic downscaling, statistical downscaling involves simple computational skills to downscale GCM simulations (Khalili et al.,2013).

Artificial intelligence (AI),as a common method of statistical downscaling, is capable of analyzing long-series of hydrological data.In recent years,the use of AI methods such as artificial neural networks (ANNs) approaches is increasing. The success of this technique is primarily due to its ability to map highly nonlinear relations between inputs and outputs of the model (Coulibaly et al., 2005). Mendes and Marengo (2010) compared the performance of a temporal neural network model with an autocorrelation statistical downscaling model with emphasis on its ability to reproduce the observed climate variability and tendency for the period 1970-1999 in the Amazon region. The results showed that the neural network model remarkably outperforms the statistical models for the downscaling of daily precipitation variations. Skamarock et al. (2O13) highlighted that ANN (artificial neural network) estimates of rainfall were more accurate than Weather Research and Forecasting model estimates,which applies dynamic downscaling approaches. Campozano et al. (2015) used the statistical downscaling model, the least squares support vector machines (LS-SVM) and ANNs to downscale precipitation data over the Paute River Basin in souther Ecuador. The results indicated that LS-SVM and ANNs performed better in downscaling of precipitation data.

As development and implementation of adaptive management strategies in water systems requires the cognition of future changes in water resources,in this study, the aim was to simulate and project the effects of climate change on Zarrineh River's streamflow.In this regard, seven different climate model precipitation and temperature data series, were downscaled using an ANN technique and bias correction method. Then the bias corrected data were used in hydrological simulations of the streamflow. So,a toolbox was developed, which comprises the ANN toolbox of MATLAB (matrix laboratory)，a program based on the bias correction method, a TOPSIS (technique for order of preference by similarity to ideal solution) program, and a rainfall-runoff model,namely the hydrologiska byrans vattenavdelning (HBV-light) model as the central engine.

# 2 Materials and methods

# 2.1 Study area

Zarrineh River basin $( 3 5 ^ { \circ } 4 0 ^ { \prime } - 3 7 ^ { \circ } 2 6 ^ { \prime } \mathrm { N } _ { \cdot }$ $4 5 ^ { \circ } 4 6 ^ { \prime }  – 4 7 ^ { \circ } 2 2 ^ { \prime } \mathrm { E } )$ ,with an area of $1 . 1 8 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ , is located in the northwest part of Iran (Fig. 1). It provides more than $40 \%$ of the total inflow into Lake Urmia, which is on the brink of desiccation with a recorded annual water level reduction of about $4 0 \ \mathrm { c m }$ over 1998-2018 (Ahmadaali et al., 2018). Lake Urmia, the largest lake in the country and the second largest saltwater lake on earth, has encountered a critical problem due to ineffective water resources management (comprising agricultural development and low irrigation water use efficiency, over allocation of the lake's inflows,irrigation projects and overuse of surface water and groundwater, etc.) and climate change (Fig. 2).

The mean annual precipitation and the annual mean temperature in the basin were reported to be about $2 9 2 . 0 0 \ \mathrm { \ m m }$ and $1 3 . 2 6 ^ { \circ } \mathrm { C }$ between 1992 and 2005，respectively. The potential daily evapotranspiration was about $4 . 1 7 \ \mathrm { m m }$ . However, these reported numbers did not follow the specific trend during the period (Ahmadi et al.,2016; Ahmadaali et al.,2018; Alborzi et al.,2018; Yazdandoost et al., 2020).

If a methodical comprehensive plan is built and implemented,reviving the shriveled lake is possible. As Zarrineh River feeds Urmia Lake, modellng the rainfall-runoff process in the river under the influence of future climate changes is crucial. The results are of important meaning for appropriate decision-making and water allocation in the basin.

![](images/86af8aa68589bc61285e4b23ea62b1c861932bd305c915700d5da45afbdc575d.jpg)  
Fig.1Location of the Zarrneh River basin in Iran (a)and the distributions of the meteorological and stream gauging stations in the study area (b)

![](images/b96baa30db41739e7fd8054c0b11b1c8e80e700f00ea316b78de3b616504b706.jpg)  
Fig.2Urmia Lake shrinkage over 1993-2018 acquired by Land Remote-Sensing Satelite using Normalized Difference Water Index

# 2.2 Data

Zarrineh River basin, used as the case study of this work, was divided into twelve O.5-degree cells.The cells were named from the top left.The study area lacks an adequate system to collect weather data. For this study, the observed daily mean temperature，provided by the Iranian Meteorological Organization (htp://reports.irimo.ir/), were used as predictands at three observation sites,which are evenly distributed across the entire area of the basin (Table 1） and a bilinear interpolation technique was employed for developing gridded temperature data. Also，daily precipitation sums were provided from the global precipitation climatology center (GPCC), providing gridded gauge-analysis products, derived from quality-controlled station data. Here in the GPCC website (htp://gpcc.dwd.de/),the gridded daily precipitation data is available in netCDF (network common data form) format with a spatial resolution of $0 . 5 ^ { \circ }$ . Also, seven different CMIP5 models for the most optimistic scenario,RCP2.6 and the most pessimistic scenario, RCP8.5, providing the predictor data, were gathered from the CERA (climate and environmental data retrieval and archive system) website (htps://cera-www.dkrz.de/)(Table 2). For calibration of the HBV-Light (hydrologiska byrans vattnavdelning) model, measured streamflow values of Zarrineh River were used. More information of the four stream gauging stations has been provided in Table 1. It should be noted that the calibration period of the study was 1992-20o5,the evaluation was performed for the verification period 2Oo6-2Ol5,and the projection period was considered for 2016-2050.

Table1 Location of the meteorological and stream gauging stations   

<html><body><table><tr><td colspan="2">Station</td><td colspan="2">Location</td><td rowspan="2">Altitude above sea level (m)</td><td rowspan="2">Period of record</td></tr><tr><td>Name</td><td>Type</td><td>Longitude</td><td>Latitude</td></tr><tr><td>Maragheh</td><td>Meteorological</td><td>46°16'E</td><td>37°24'N</td><td>1477.7</td><td>1987-2019</td></tr><tr><td>Saghez</td><td>Meteorological</td><td>46°16'E</td><td>36°15'N</td><td>1522.8</td><td>1987-2019</td></tr><tr><td>Takab</td><td>Meteorological</td><td>47°06'E</td><td>36°24'N</td><td>1817.2</td><td>1992-2019</td></tr><tr><td>Sarighmish</td><td>Stream gauging</td><td>46°29'E</td><td>36°29'N</td><td>1372.0</td><td>1955-2019</td></tr><tr><td>Gezkerpi</td><td>Stream gauging</td><td>46°33'E</td><td>36°37'N</td><td>1350.0</td><td>1956-2019</td></tr><tr><td>Miandoab</td><td>Stream gauging</td><td>46°07'E</td><td>36°57N</td><td>1290.0</td><td>1964-2019</td></tr><tr><td>Nezamabad</td><td>Stream gauging</td><td>46°03'E</td><td>37°03'N</td><td>1290.0</td><td>1993-2019</td></tr></table></body></html>

Table2GCMs(global climate models) used in this study   

<html><body><table><tr><td rowspan="2">Model</td><td rowspan="2">Complete name</td><td colspan="4">Resolution</td></tr><tr><td>Atmospheric grid</td><td></td><td>Ocean grid</td><td></td></tr><tr><td>BCC-CSM1-1</td><td>Beijing Climate Center Climate</td><td>Longitude 2.8125°</td><td>Latitude 2.7906°</td><td>Longitude 1.0000°</td><td>Latitude 0.3333°,</td></tr><tr><td>BNU-ESM</td><td>System Model Beijinm Momal University Earth</td><td>2.8125°</td><td>2.7906°</td><td>1.0000°</td><td>1.0000° 0.3344%,</td></tr><tr><td>CSIRO-Mk3-6-0</td><td>Commonwealth Scientific and</td><td>1.8750°</td><td>1.8653°</td><td>1.8750°</td><td>0.9327°,</td></tr><tr><td>GFDL-ESM2G</td><td>Industrial Research Organization Geophysical Fluid Dynamics</td><td>2.0000°</td><td>2.0225°</td><td>1.0000°</td><td>0.9457° 0.3750°,</td></tr><tr><td>IPSL-CM5A-LR</td><td>Laboratory IPSL Eerthrt-stewModutlfor the 5th</td><td>3.7500°</td><td>1.8947°</td><td>lon (i,j)</td><td>0.5000° lat (i,j)</td></tr><tr><td>MIROC-ESM</td><td>Model for Interdisciplinary Research</td><td>2.8125°</td><td>2.7906°</td><td>1.4063°</td><td>0.5582°,</td></tr><tr><td>MIROC-ESM-CHEM</td><td>on Climate- earth system model An atmospheric chemistry coupled version ofMIROC-ESM</td><td>2.8125°</td><td>2.7906°</td><td>1.4063°</td><td>1.7111° 0.5582°, 1.7111°</td></tr></table></body></html>

Note: more information at htps://portal.enes.org/data/enes-model-data/cmip5/resolution.lon $( i , j )$ and lat $( i , j )$ denote that the resolution cannot simply be read out.

# 2.3 Artificial neural network

ANNs are patern recognition tools, which are able to find confirmable relationships between a set of inputs and the corresponding outputs (Chadwick et al., 201l; Patil et al.，2015). In 1957, Rosenblattintroduced the simplest form of feed-forward neural network, called perceptron. But as the inputs were fed directly to the output unit via the weighted connections in the method, it was proved that they could not be trained to distinguish different classes of paterns (Hung et al., 2009). A multilayer perceptron (MLP) is a feedforward ANN, comprising of at least three layers of nodes: an input layer, a hidden layer and an output layer. As the MLP finds non-linear relationships among the nodes, it overcomes many limitations of the single layer perceptron (Lippmann, l987). Two important characteristics of the MLP are: its nonlinear processing elements which have a smooth nonlinearity; and their massive interconnectivity. The effectiveness of an ANN model is gauged by MSE(means quared error） and $R ^ { 2 }$ ，which are derived from comparing the output data with the corresponding target output for the pattern. The best performance can be yielded by specifying the network architecture and by finding the optimal values of connection weights (Hung et al., 2009).

The network size depends on the number of nodes and layers. However, in the process of finding the optimal values for the connection weights,selection of a training algorithm is important. There are several training processes which difer in how the weights are obtained. In this study, the standard back propagation algorithm was used in ANN training based on its popularity. Detailed information about the proposed ANN approach is provide in Chadwick et al. (2011), TueVu et al. (2016),and Tran Anh and Taniguchi (2018).

In the present work, to implement the ANN models, the ANN toolbox of MATLAB was used, and the transfer function of hidden layer was taken as tansigmoid while function of the output layer was a linear transfer function. The ANN models were trained on $70 \%$ dataset to predict precipitation and temperature for the twelve different O.5-degree cells of the study area. The remaining $30 \%$ dataset was used for testing and validation of the models.In this study,it was desired to produce an output of temperature and precipitation and to establish the relationship between GCM simulations and observed temperature and rainfall data. ANNs were trained separately for temperature and precipitation, so each network produced only one output variable, corresponding to the target layer of the ANN.

# 2.4 Bias correction

Simulated precipitation and temperature by GCMs are often characterized by considerable biases due to their coarse spatial resolution (Gondim et al., 2018), limiting their direct application for basin-scale hydrological modeling.To address the systematic errors of GCMs, most of the climate studies use bias correction methods to bias correct the climate model outputs.This study describes how to use an efficient statistical bias correction method over the study area and improve the performance of the downscaled data, derived from the ANN models. The quantile mapping (QM) method (also known as distribution mapping method) was applied to correct precipitation and temperature data and is utilized to match the distribution function of the data, derived from ANN, with the observed distribution function.As it is used to adjust mean, standard deviation and quantiles, it preserves the extremes (Themebl et al.,2O12), but it also has its limitation due to the assumption that both meteorological variables follow the same distribution, which may cause new biases (Fang et al., 2015). The Gamma distribution (Thom,1958) with shape parameter $\boldsymbol { a }$ and scale parameter $\beta$ is often used for precipitation distribution (Piani et al., 2010):

$$
f _ { y ( x | \alpha , \beta ) } = x ^ { \alpha - 1 } \frac { 1 } { \beta ^ { \alpha } \Gamma ( x ) } e ^ { \frac { - x } { \beta } } ( x \geq 0 ; \alpha > 0 , \beta > 0 ) ,
$$

where $\Gamma ( x )$ is the gamma function for the variable $x$ . The QM method of precipitation is expressec mathematically in terms of the Gamma cumulative distribution function $f _ { y }$ and its inverse $f _ { y } ^ { - 1 }$ as:

$$
P _ { \mathrm { c o r } , m , d } = f _ { y } ^ { - 1 } ( f _ { y } ( P _ { \mathrm { A N N } , m , d } \mid \alpha _ { \mathrm { A N N } , m } , \beta _ { \mathrm { A N N } , m } ) \mid \alpha _ { \mathrm { o b s } , m } , \beta _ { \mathrm { o b s } , m } ) ,
$$

where $P _ { \mathrm { c o r } , m , d }$ is corrected precipitation; $P _ { \mathrm { A N N } , m , d }$ is the precipitation derived from the ANN models on the day $d$ of month $m$ · $\alpha _ { \mathrm { A N N } , m }$ and $\beta _ { \mathrm { A N N } , m }$ are the shape parameter and scale parameter from the ANN data on the month $m$ ; and $a _ { \mathrm { o b s } }$ ，and $\beta _ { \mathrm { o b s } , m }$ are the shape parameter and scale parameter from the observational data on the month $m$ ：

For temperature, the Gaussian (or normal） distribution (Cramer, 1999） with mean $( \mu )$ and standard deviation $( \sigma )$ is usually presumed to fit temperature best (Teutschbein and Seibert, 2012):

$$
f _ { _ { N ( x | \mu , \sigma ^ { 2 } ) } } = x ^ { \alpha - 1 } \frac { 1 } { \sigma \sqrt { 2 \pi } } e ^ { \frac { - ( x - \mu ) ^ { 2 } } { 2 \sigma ^ { 2 } } } ; x \in \mathrm { R } \ ,
$$

where $f _ { N }$ is the calculated Gaussian distribution and $\mathrm { ~ R ~ }$ is a real number.

For temperature,the QM method is expressed mathematically in terms of the Gaussian cumulative distribution function $f _ { N }$ and its inverse $\ b { f } _ { N } ^ { - 1 }$ as:

$$
T _ { \mathrm { c o r } , m , d } = f _ { N } ^ { - 1 } ( f _ { N } ( T _ { \mathrm { A N N } , m , d } \mid \mu _ { \mathrm { A N N } , m } , \sigma _ { \mathrm { A N N } , m } ^ { 2 } ) \mid \mu _ { \mathrm { o b s } , m } , \sigma _ { \mathrm { o b s } , m } ^ { 2 } ) ,
$$

where $T _ { \mathrm { c o r } , m , d }$ is the corrected temperature; $T _ { \mathrm { A N N } , m , d }$ is the temperature derived from ANN models on the day d of month $m ; \mu _ { \mathrm { A N N } , m }$ and $\hat { \sigma } _ { \mathrm { A N N } , m } ^ { 2 }$ are the mean and variance from the ANN data on the month

$m$ ; and $\mu _ { \mathrm { o b s } , m }$ and $\sigma _ { \mathrm { { \ o b s } } , m } ^ { 2 }$ are the mean and variance from the observational data on the month m.

# 2.5 TOPSIS method

TOPSIS is a multi-criteria decision making method, which is based on the idea that the selected alternative should have the shortest geometric distance from the positive ideal solution and the longest distance from the negative ideal solution (Garcia-Cascales and Lamata,2O12).The method was first developed by Hwang and Yoon (1981). The procedure consists of the six following steps (Garcia-Cascales and Lamata, 2012; Jena et al., 2015):

# 2.5.1 Establishing a performance matrix

The decision-matrix $( M )$ consists of $m$ alternatives $\left( A _ { m } \right)$ and $n$ criteria $\left( C _ { n } \right)$ ,with the intersection of each alternative and criterion given as $z _ { i j }$

$$
\begin{array} { r } { \begin{array} { c c c c c } { C _ { 1 } } & { C _ { 2 } } & { \ldots } & { C _ { n } } \\ { A _ { 1 } } & { \left( z _ { 1 1 } } & { z _ { 1 2 } } & { \ldots } & { z _ { 1 n } \right) } \\ { M = A _ { 2 } } \\ { \ldots } & { \left( \begin{array} { c c c c c } { z _ { 2 1 } } & { z _ { 2 2 } } & { \ldots } & { z _ { 2 n } } \\ { \ldots } & { \ldots } & { \ldots } & { \ldots } \\ { z _ { m 1 } } & { z _ { m 2 } } & { \ldots } & { z _ { m n } } \end{array} \right) , } \end{array} } \end{array}
$$

where $i$ and $j$ represent the number of row and column, respectively

2.5.2Normalizing the decision-matrix

In the classcal TOPSIS approach, the normalized matrix can be obtained using the following transformation formula:

$$
N _ { i j } = \frac { z _ { i j } } { \displaystyle { \sqrt { \sum _ { i = 1 } ^ { m } z _ { i j } ^ { 2 } } } } ,
$$

where $N _ { i j }$ isa member of the normalized matrix.

2.5.3Calculating the weighted normalized decision matrix $( V )$ as Equation 7,

$$
\begin{array} { r } { V = N _ { i j } \times W _ { n \times n } , } \end{array}
$$

where these weights $W _ { n \times n }$ are calculated by entropy,AHP (Analytic Hierarchy Process) and direct assignation, etc.

2.5.4Determining the positive ideal solution $( A ^ { + } )$ and negative ideal solution $( A ^ { - } )$

$$
\begin{array} { r } { A ^ { + } = \{ \nu _ { 1 } ^ { + } , . . . . , \nu _ { n } ^ { + } \} = \{ ( \operatorname* { m a x } \nu _ { i j } , j \in J ) ( \operatorname* { m i n } \nu _ { i j } , j \in J ^ { \prime } ) \} , i = 1 , \ 2 , . . . , m \ , } \end{array}
$$

$$
\begin{array} { r } { A ^ { - } = \{ \nu _ { 1 } ^ { - } , . . . . , \nu _ { n } ^ { - } \} = \{ ( \operatorname* { m i n } \nu _ { i j } , j \in J ) ( \operatorname* { m a x } \nu _ { i j } , j \in J ^ { \prime } ) \} , \ i = 1 , \ 2 , \ . . . , m , } \end{array}
$$

where $J$ is associated with benefit criteria; $J ^ { \prime }$ is associated with cost criteria; and $\nu _ { i j }$ is the componen of matrix $V$ in the $i ^ { \mathrm { t h } }$ line and $j ^ { \mathrm { t h } }$ column calculated from Equation 7.

# 2.5.5 Calculating the separation measures

The separation of each alternative from the $\boldsymbol { A } ^ { + } ( \boldsymbol { d } _ { i } ^ { + } )$ and the separation of each alternative from the $\mathbf { A } ^ { - } ( d _ { i } ^ { - } )$ are given as follows:

$$
\begin{array} { r } { d _ { i } ^ { + } = \sqrt { \sum _ { j = 1 } ^ { n } ( \nu _ { i j } - \nu _ { j } ^ { + } ) ^ { 2 } } , i = 1 , 2 , . . . , m , } \end{array}
$$

$$
\begin{array} { r } { d _ { i } ^ { - } = \sqrt { \sum _ { j = 1 } ^ { n } ( \nu _ { i j } - \nu _ { j } ^ { - } ) ^ { 2 } } , i = 1 , 2 , . . . , m . } \end{array}
$$

2.5.6 Calculating the relative closeness $( \mathrm { C L } _ { i } ^ { * } )$ to the ideal solution

$$
\mathrm { C L } _ { i } ^ { * } = \frac { d _ { i } ^ { - } } { d _ { i } ^ { - } + d _ { i } ^ { + } } , \qquad i = 1 , 2 , . . . , m .
$$

Alternatives are ranked according to $\mathrm { C L } _ { i } ^ { * }$ . The higher $\mathrm { C L } _ { i } ^ { * }$ value, the higher the priority of the

$i ^ { \mathrm { t h } }$ alternative (Garcia-Cascales and Lamata, 2012).

# 2.6Hydrological modeling

HBV-Light, a conceptual, continuous and semi-distributed streamflow model developed by Sten Bergstrom in 1992 and 1995, was used to simulate daily streamflow values for the study area. HBVLight includes some different routines and it can simulate snow, soil water， evaporation, groundwater and channel routing (Teutschbein and Seibert, 2012). HBV-Light requires daily temperature， precipitation and long-term average of potential evaporation values as driving variables.In this study,for the best GCM in the study area,chosen by TOPSIS method,48 possible daily temperature and precipitation series in the twelve O.5-degree cells, derived from the QM method based on the two scenarios of RCP2.6 and RCP8.5, were available to run the HBV-Light models.First, the HBV-Light models were calibrated and validated to measured streamflow values. For this purpose, the monthly averages of HBV-Light-simulated streamflow were analyzed and were compared to the observed values from 1992 to 2015. Then, these HBV-Light parameter sets were used to simulate streamflow with the corrected GCM simulations as driving conditions between 1992 and 2050.Figure 3 shows the flowchart of the study.

![](images/3464065b2383c6c15814d1a54334cd546b40adead2bcee6bdaf1c739df8a8320.jpg)  
Fig.3Flowchart of the study. CMIP5,climate model intercomparison project phase 5; GCMs,global climate models; RCPs, representative concentration pathways; TOPSIS,technique for order of preference by similarity to ideal solution.

# 3 Results

# 3.1 Statistical evaluationof the bias-corrected ANN simulations

At this stage, we applied three statistical metrics to evaluate the performance of raw GCMs data over the study area and to assess the inter-model differences.The evaluation started by comparing the mean daily precipitation of GPCC data and individual model mean during the historical period of 1992-2005. In addition,we used the mean absolute error (MAE) to compare the observed climate data with the corrected forecasted data and used the coefficient of determination $( R ^ { 2 } )$ to show the statistical relationship between the observation data set with the corrected data (Table 3). Results from Table 3 highlight the need for correcting GCMs outputs before any further analysis.

We established the relationship between GCM simulations and observed temperature and rainfall data to implement the ANN models. In addition，we used the bias correction methods of precipitation and temperature to improve the performance of each ANN model. Precipitation and temperature correction methods were conducted on a daily basis from 1992 to 2050 (Table 4).

Table 3Statistical evaluation of the raw GCMs' simulations for daily temperature and precipitation data from 1992 to 20o5 in cell number1 as a sample   

<html><body><table><tr><td rowspan="2">Model</td><td colspan="4">Temperature</td><td colspan="4">Precipitation</td></tr><tr><td>MAE (C)</td><td>R²</td><td>Mean (C)</td><td>Observed mean (C)</td><td>MAE (mm)</td><td>R²</td><td>Mean (mm)</td><td>Observed mean (mm)</td></tr><tr><td>BCC-CSM1-1</td><td>6.95</td><td>0.68</td><td>15.12</td><td rowspan="7"></td><td>1.21</td><td>0.02</td><td>0.60</td><td rowspan="7"></td></tr><tr><td>BNU-ESM</td><td>6.68</td><td>0.89</td><td>18.92</td><td>1.05</td><td>0.03</td><td>0.43</td></tr><tr><td>CSIRO-Mk3-6-0</td><td>7.44</td><td>0.66</td><td>15.03</td><td>1.25</td><td>0.04</td><td>0.64</td></tr><tr><td>GFDL-ESM2G</td><td>7.80</td><td>0.71</td><td>18.53</td><td>1.36</td><td>0.01</td><td>0.74</td></tr><tr><td>IPSL-CM5A-LR</td><td>6.35</td><td>0.77</td><td>9.22</td><td>1.30</td><td>0.02</td><td>0.73</td></tr><tr><td>MIROC-ESM</td><td>6.57</td><td>0.90</td><td>19.38</td><td>1.25</td><td>0.01</td><td>0.64</td></tr><tr><td>MIROC-MSM-</td><td>6.40</td><td>0.90</td><td>19.20</td><td>1.25</td><td>0.05</td><td>0.68</td></tr></table></body></html>

Note: MAE,mean absolute error.

Table 4Statistical evaluation of the bias-corrected ANN(artificial neural network） simulations for daily temperature and precipitation data from 1992 to 2005 in cell number 1 as a sample   

<html><body><table><tr><td rowspan="2">Model</td><td colspan="4">Temperature</td><td colspan="4">Precipitation</td></tr><tr><td>MAE(C)</td><td>R²</td><td>Mean (C)</td><td>Obaerved</td><td>MAE (mm)</td><td>R²</td><td>Mean (mm)</td><td>Obsn (med)</td></tr><tr><td>BCC-CSM1-1</td><td>2.86</td><td>0.72</td><td>15.12</td><td rowspan="6"></td><td>1.02</td><td>0.30</td><td>0.74</td><td rowspan="6"></td></tr><tr><td>BNU-ESM</td><td>2.77</td><td>0.93</td><td>18.92</td><td>0.87</td><td>0.30</td><td>0.74</td></tr><tr><td>CSIRO-Mk3-6-0</td><td>2.36</td><td>0.69</td><td>15.03</td><td>1.09</td><td>0.32</td><td>0.77</td></tr><tr><td>GFDL-ESM2G</td><td>2.85</td><td>0.76</td><td>18.53</td><td>1.21</td><td>0.30</td><td>0.77</td></tr><tr><td>IPSL-CM5A-LR</td><td>2.41</td><td>0.81</td><td>9.22</td><td>1.11</td><td>0.30</td><td>0.74</td></tr><tr><td>MIROC-ESM</td><td>2.53</td><td>0.95</td><td>19.38</td><td>1.05</td><td>0.30</td><td>0.74</td></tr><tr><td>MIROC-ESM-CHEM</td><td>2.54</td><td>0.94</td><td>19.20</td><td></td><td>1.06</td><td>0.30</td><td>0.74</td></tr></table></body></html>

# 3.2 TOPSIS method

The best CMIP5 model was chosen by TOPSIS method.Development of the TOPSIS algorithm was done based on the statistical evaluation of the bias-corrected ANN simulations from 1992 to 2005 in the study area. As a non-limiting sample, Table 5 indicates that the highest priority of model selection is belonged to CSIRO-Mk3-6-0.Therefore,in the next step, this model was used to simulated Zarrineh River's streamflow under the RCP2.6 and RCP8.5 in the HBV-Light models. In this table,the bias-corrected ANN simulations for daily precipitation and temperature were evaluated statistically during 1992-2005.

Table 6 shows the annual mean observed and corrected precipitation and temperature from 1992 to 2005 by the bias-corrected ANN data,derived from CSIRO-Mk3-6-0 in Zarrineh River basin. Based on the table,a fairly good consistency between the observed and simulated data was revealed. Results indicate that the coefficient of determination between the annual mean observed and biascorrected ANN data in the target period is 0.81 and 0.93 in the case of precipitation and temperature, respectively.

Figure 4 indicates the observed and corrected mean precipitation and temperature from 1992 to 2005 by bias-corrected ANN data for daily precipitation and temperature, derived from CSIRO

Table 5The result of TOPSIS (technique for order of preference by similarity to ideal solution) method for choosing the best CMIP5 (coupled model intercomparison project phase 5) model during 1992-2005   

<html><body><table><tr><td rowspan="2">Model</td><td colspan="3">Precipitation</td><td colspan="3">Temperature</td><td colspan="2">TOPSIS</td></tr><tr><td>MAE (mm)</td><td>R²</td><td>Mean error (mm)</td><td>MAE(C)</td><td>R²</td><td>Mean error (C)</td><td>Cli*</td><td>Rank</td></tr><tr><td>BCC-CSM1-1</td><td>1.02</td><td>0.30</td><td>0.06</td><td>2.86</td><td>0.72</td><td>1.86</td><td>0.787</td><td>2</td></tr><tr><td>BNU-ESM</td><td>0.87</td><td>0.30</td><td>0.06</td><td>2.87</td><td>0.93</td><td>5.66</td><td>0.106</td><td>5</td></tr><tr><td>CSIRO-Mk3-6-0</td><td>1.09</td><td>0.32</td><td>0.03</td><td>2.36</td><td>0.69</td><td>1.77</td><td>0.971</td><td>1</td></tr><tr><td>GFDL-ESM2G</td><td>1.21</td><td>0.30</td><td>0.03</td><td>2.85</td><td>0.76</td><td>5.27</td><td>0.289</td><td>4</td></tr><tr><td>IPSL-CM5A-LR</td><td>1.11</td><td>0.30</td><td>0.06</td><td>2.41</td><td>0.81</td><td>4.04</td><td>0.450</td><td>3</td></tr><tr><td>MIROC-ESM</td><td>1.05</td><td>0.30</td><td>0.06</td><td>2.53</td><td>0.95</td><td>6.12</td><td>0.028</td><td>7</td></tr><tr><td>MIROC-ESM-CHEM</td><td>1.06</td><td>0.30</td><td>0.06</td><td>2.54</td><td>0.94</td><td>5.94</td><td>0.048</td><td>6</td></tr></table></body></html>

Table 6Observed and corrected mean annual precipitations and annual mean temperatures from 1992 to 2005 by bias-corrected ANN data,derived from CSIRO-Mk3-6-O in Zarrineh River basin   

<html><body><table><tr><td rowspan="2">Parameter</td><td colspan="10">Time</td><td rowspan="2"></td><td colspan="3"></td></tr><tr><td></td><td>1992 1993</td><td>1994</td><td>1995</td><td></td><td>1996</td><td>1997</td><td>1998</td><td>1999</td><td>2000</td><td>2001</td><td>2002 2003</td><td>2004</td><td>2005</td></tr><tr><td>Pobs (mm)</td><td>1.22</td><td>1.69</td><td>1.72</td><td>1.07</td><td>1.18</td><td>1.16</td><td>1.07</td><td>0.71</td><td></td><td>0.85</td><td>0.81</td><td>1.37</td><td>1.26</td><td>1.36</td><td>1.07</td></tr><tr><td>Pcor (mm)</td><td>1.30</td><td>1.34</td><td>1.29</td><td>1.19</td><td>1.13</td><td>1.08</td><td></td><td>1.01</td><td>0.96</td><td>0.96</td><td>1.01</td><td>1.09</td><td>1.13</td><td>1.12</td><td>1.00</td></tr><tr><td>Tobs(C)</td><td>8.52</td><td>10.02</td><td>11.16</td><td>11.18</td><td>11.55</td><td>10.27</td><td>11.54</td><td></td><td>12.20</td><td>11.49</td><td>12.31</td><td>11.45</td><td>11.50</td><td>11.54</td><td>11.61</td></tr><tr><td>Tcor(C)</td><td>9.76</td><td>11.10</td><td>12.12</td><td>12.56</td><td>12.42</td><td>12.20</td><td>12.46</td><td></td><td>12.86</td><td>12.95</td><td>12.96</td><td>12.87</td><td>12.74</td><td>12.58</td><td>12.45</td></tr></table></body></html>

Note: $P _ { \mathrm { o b s } }$ ,observed precipitation; $P _ { \mathrm { c o r } } ,$ corrected precipitation; $T _ { \mathrm { o b s } }$ ,observed temperature; $T _ { \mathrm { c o r } } ,$ corrected temperature.

![](images/7ffa3dab445dba217319d2e0f8941815c0535721defe185c09dac00039fe4f22.jpg)  
Fig.4The observed (points) and corrected (box plots) mean precipitation (a) and mean temperature (b) from 1992 to 2005 by bias-corrected ANN data for daily data,derived from CSIRO-Mk3-6-0

Mk3-6-O.In this figure, the cells were named from the top left.

In the validation period of 2006-2015，bias-corrected ANN data for precipitation and temperature data of CSIRO-Mk3-6-0 projects, based on RCP2.6 and RCP8.5,were assessed based on the observed data. The coefficient of determination in the validation period for bias-corrected

ANN data for precipitation was 0.50 and 0.51 in the case of RCP2.6 and RCP8.5, respectively. These numbers change to 0.70 and 0.74 when it comes to temperature.As Figures 5 indicate,results achieved an acceptable agreement between the annual mean observed and bias-corrected ANN data. Bias-corrected ANN data for precipitation data of CSIRO-Mk3-6-0 reveals that the daily mean precipitation is expected to decrease from O.94 and $0 . 9 6 \mathrm { m m }$ in 2015 to 0.65 and $0 . 6 8 \mathrm { m m }$ in 2050 based on RCP2.6 and RCP8.5, respectively. In the case of temperature, the numbers change from $1 2 . 3 3 ^ { \circ } \mathrm { C }$ and $1 2 . 3 7 ^ { \circ } \mathrm { C }$ in 2015 to $1 4 . 2 8 ^ { \circ } \mathrm { C }$ and $1 4 . 3 2 ^ { \circ } \mathrm { C }$ in 2050,respectively. This data was next used to simulate Zarrineh River's streamflow in the HBV-Light models.

![](images/86192cfe91f04cdd19836ff337adac234b33d8649e8245bb7bad9819b0cc9aed.jpg)  
Fig.5Assessment of bias corrected ANN simulations of monthly mean precipitation (a) and temperature (b) derived from CSIRO-Mk3-6-0 in the validation period (2006-2015)

# 3.3 Evaluation of the hydrological models

The chosen CMIP5 model (CSIRO-Mk3-6-0), operated under RCP2.6 and RCP8.5, was used to simulate Zarrineh River's streamflow in the HBV-Light models from 1992 to 2050.For the evaluation of the models,statistical indexes such as the coefficient of determination were used. Also, monthly mean streamflow in hydrological simulations for the catchment were compared with the observed data between 1992 and 2015.In general, it can be said that the agreement between the observed and simulated values both in the calibration period of 1992-20o5 and in the validation period of 2006-2015 is acceptable.The observed monthly streamflow in 2015 and corresponding simulated streamflow in HBV-Light models by the corrected data, derived from CSIRO-Mk3-6-0, operated under RCP2.6 and RCP8.5, were summarized in Tables 7 and 8. Generally, allsimulations were in good agreement with the observations and there was no significant difference between these results and the observed values.

Upon assuring that the models simulate the stream flow of Zarrineh River in the plausible limits, future projections of the river flow were achieved.Future projections for the period of 2016-2050 of streamflow for the study site, simulated by bias-corrected ANN data for daily precipitation and temperature, derived from CSIRO-Mk3-6-0, operated under RCP2.6 and RCP8.5, were generally in agreement in terms of the general trend (Fig. 6).A more detailed look at the figure reveals that the annual streamflow of Zarrineh River is expected to decrease from $5 9 . 4 9 \mathrm { m } ^ { 3 } / \mathrm { s }$ in 2015 to 22.61 and $2 3 . 1 9 \mathrm { m } ^ { 3 } / \mathrm { s }$ in 2050 based on RCP2.6 and RCP8.5, respectively.

Table7Performance of the HBV-Light (hydrologiska byrans vattenavdelning）models simulated by biascorrected ANNdata fordailybias-corrected precipitationand temperature,derived from CSIRO-Mk3-6-0,operated under RCP2.6 and RCP8.5 in 2015   

<html><body><table><tr><td colspan="2">R²</td><td colspan="3">Sumof monthly mean streamflow (m³/s)</td><td colspan="3">Monthly mean streamflow (m/s)</td></tr><tr><td>RCP2.6</td><td>RCP8.5</td><td>Observed</td><td>RCP2.6</td><td>RCP8.5</td><td>Observed</td><td>RCP2.6</td><td>RCP8.5</td></tr><tr><td>0.63</td><td>0.63</td><td>713.84</td><td>703.58</td><td>714.34</td><td>59.49</td><td>58.63</td><td>59.53</td></tr></table></body></html>

Table 8Monthly mean streamflow of the HBV-Light models simulated by bias-corrected ANN data for daily bias-corrected precipitation and temperature,derived from CSIRO-Mk3-6-0,operated under RCP2.6 and RCP8.5 in 2015   

<html><body><table><tr><td rowspan="2">Month</td><td colspan="3">Monthly mean streamflow (m/s)</td></tr><tr><td>Observation</td><td colspan="2">Simulation</td></tr><tr><td>Jan</td><td>42.74</td><td>RCP2.6</td><td>RCP8.5 34.70</td></tr><tr><td>Feb</td><td></td><td>32.40 38.10</td><td>37.75</td></tr><tr><td></td><td>211.78</td><td>219.21</td><td>219.81</td></tr><tr><td>Mar Apr</td><td>202.61</td><td>75.21</td><td>75.01</td></tr><tr><td>May</td><td>89.31</td><td>54.20</td><td></td></tr><tr><td>Jun</td><td>45.76 40.69</td><td>45.50</td><td>53.72</td></tr><tr><td>Jul</td><td>27.30</td><td>42.89</td><td>45.42</td></tr><tr><td>Aug</td><td>16.68</td><td>40.82</td><td>42.89</td></tr><tr><td>Sep</td><td></td><td></td><td>40.83</td></tr><tr><td>Oct</td><td>9.89</td><td>39.18</td><td>39.36</td></tr><tr><td>Nov</td><td>7.83</td><td>37.22</td><td>38.74</td></tr><tr><td></td><td>8.19</td><td>33.77</td><td>36.23</td></tr><tr><td>Dec</td><td>11.06</td><td>45.08</td><td>49.88</td></tr></table></body></html>

![](images/625a924bf450664dade7136d73dde43dab8882022f11da3dbe0778966bd1b9dd.jpg)  
Fig.6Annual mean streamflow of the Zarrineh River in the HBV-Light (hydrologiska byrans vattenavdelning) models simulated by bias-corrected ANN data,derived from CSIRO-Mk3-6-0,operated under RCP2.6 and $\mathrm { R C P 8 . 5 }$ from 2015 to 2050

# 4Discussion

Climate change is expected to alter the magnitude and timing of runoff and, consequently, have significant implications for existing water resources systems as well as for planning and management of future water resources (Teutschbein and Seibert, 2O12). Zarrineh River basin faces high pressure on water due to ineffective water resources management, as well as climate change (Abbaspour and Nazaridoust, 2007; Ahmadaali et al.,2018; Alborzi et al., 2018). So,a better understanding of the impact of climate change on water resources in the basin is necessary (Ahmadzadeh et al.,2011; Delju etal.,2013; Nikbakht et al.,2013; Gholampour et al.,2015; Torabi Haghighi and Klove,2017; Ghale et al.,2018). The present study aimed to simulate and project the streamflow of Zarrineh River from 1992 to 2050.For this purpose,a toolbox was developed, comprising the ANN method for downscaling the large-scale data,a bias correction method for generating unbiased climate datasets,a TOPSIS program for choosing the best CMIP5 model and a rainfall-runoff model, namely HBV-Light for investigating the effects of climate change on water resources. The results indicated that the daily mean precipitation is expected to decrease from 0.94 and $0 . 9 6 \mathrm { m m }$ in 2015 to 0.65 and $0 . 6 8 ~ \mathrm { m m }$ in 2050 based on RCP2.6 and RCP8.5,respectively. In the case of temperature, the numbers change from $1 2 . 3 3 ^ { \circ } \mathrm { C }$ and $1 2 . 3 7 ^ { \circ } \mathrm { C }$ in 2015 to $1 4 . 2 8 ^ { \circ } \mathrm { C }$ and $1 4 . 3 2 ^ { \circ } \mathrm { C }$ in 2050, respectively. In addition, the annual streamflow of Zarrineh River is expected to decrease by half from 2015 to 2050.

Results from this study, along with previous studies, showed that the combination of the ANN method and bias correction method can improve the performance of the forecasted data.As the results showed that the performances of bias correction methods are not robust in allof the months. To evaluate the robustness of the performances of the methods in different hydrological seasons, the stramflow can be divided into different periods according to the hydrographs.As statistical downscaling methods rely heavily on the assumption that currently observed relationships will carry into the future,using two statistical downscaling methods simultaneously may result in similar consequences for both RCP2.6 and RCP8.5.

The proposed approach can be further strengthened and extended from several aspects. Future research will, hopefully, combine and apply the ANN method and different bias correction methods to other study areas as the accuracy of the method depends on several spatial and temporal conditions. A major extension may be considering land cover-use change, where any change in land cover may also result in a decrease in streamflow while sensitivity analysis is an approach to handle this type of challenge.It is undeniable that other potential topics can be covered in future studies in Zarrineh River basin to quantify the impacts of different future scenarios and to reduce the negative effects of climate change and human activities on local water resources.

# 5 Conclusions

Considerable changes in precipitation and temperature regimes in the past few decades have resulted in socio-economic and environmental problems.Accordingly, it is required to estimate future changes, being used in hydrological simulations of streamflow. In spite of the increasing use of GCM simulations in hydro-climatic studies, their direct application is contestable due to the biases. This paper introduces a new approach for forecasting rainfall and temperature, using an ANN technique. To improve its performance,a bias correction method may be used. So,a toolbox was developed, comprising the ANN method,a bias correction and a TOPSIS program, and a rainfall-runoff model, namely the HBV-light model, where the eects of climate change on water resources were investigated. The toolbox was utilized for the case of Zarrineh River basin. Future projections of streamflow revealed that the annual streamflow is expected to decrease by half from 2015 to 2050.

# References

Abaspour M,NazaridoustA.2O7.Determinationofenvironmental waterrequirementsofLakeUrmia,Iran:anecological approach.International Journal of Environmental Studies,64(2):161-169.   
AhmadaliJ,BaraniG,QaderiK,etal.2O18.Analysisoftheefectsof watermanagementstrategiesandlimatechangeonthe environmental and agricultural sustainability of Urmia Lake basin,Iran.Water,lO(2):1-21.   
Ahmadi A,Abbaspour M,Arjmandi R,etal.2016.Resilientappoach toward urban development inlakecatchments,caseof Lake Urmia. Scientia Iranica,23(4): 1627-1632   
AhmadzadehKT,PejmaA,MahinAE,etal.2O11Evaluationofsalt efectsonsomethermodynamic propertisofUriaLake water.International Journal of Environmental Research,5(2):343-348.   
Alborzi A,Mirchi A,Moftakhari H,etal.2018.Climate-informed environmental inflows torevivea drying lake facing meteorologicalandanthropogenicdroughts.EnvronmentalResearchleers,3(8):08410,doi:10.08/1748-9326/aad246.   
AndersonJWP,StornioloRE,RiceJS.2Ol1.Bank thermalstorageasasinkoftemperaturesurges inurbanized streams.Journal of Hydrology, 409(1-2): 525-537.   
BozkurtD,RojasM,BoisierJP,etal.2O18.Projected hydroclimatechangesoverAndeanbasins in CentralChilefromdownsca   
led CMIP5 models under the low and high emission scenarios. Climatic Change,150:131-147.   
CampozanoL,TenelandaD,SanchezE,etal.2O15.Comparisonofstatisticaldownscaling methods formonthlytotalprecipitation: Casestudy for thepaute river basin in southern Ecuador.Advances in Meteorology，Special Issue:6526341，doi: 10.1155/2016/6526341.   
Chadwick R,Coppola E,GiorgiF.2011Anartifcial neural network technique fordownscaling GCMoutputs toRCM spatial scale.Nonlinear Processes in Geophysics,18:1013-1028.   
CoulibalyP,DibikeYB,AnctilF.2Oo5.Downscalingprecipitationandtemperature with temporal neural networks.Joualof Hydrometeorology, 6(4): 483-496.   
Cramer H. 1999. Mathematical Methods of Statistics $9 ^ { \mathrm { t h } }$ ed.). Princeton: Princeton University Press,208-232,310-316,557- 559.   
Delju A,CeylanA,PguetE,etal.2O13.Observedclimatevariabilityandchangein UrmiaLake Basin,Iran.Theoreticaland Applied Climatology,111: 285-296.   
Do Hoai N,Udo K,ManoA.2011.Downscalingglobal weather forecast outputs using ANN for flood prediction.Jourmal of Applied Mathematics,Special Issue: 246286,doi: 10.1155/2011/246286.   
Fang G,Yang JH,ChenYN,etal.2O15.Comparing biascorrection methodsindownscaling meteorologicalvariables fora hydrologic impact study in an arid area in China.Hydrology and Earth System Sciences,19: 2547-2559.   
Fowler HJ,EkstromM,Blenkinsop S,etal.27.Estimatingchange inextremeEuropeanprecipitationusingamultimodel ensemble.Journal of Geophysical Research,112(D18):104,doi: 10.1029/2007JD008619.   
Garcia-Cascales MS,Lamata TM.2012.Onrank reversal and TOPSIS method.Journal of Mathematicaland Computer Modelling, 56(5-6):123-132.   
Ghale Y,Altunkaynak A,Unal A.2018.Investigationanthropogenic impactsand climate factorson dryingupof Urmia Lake using water budget and drought analysis.Water Resources Management,32: 325-337.   
GholampourA,Nabizadeh R,Hassanvand MS,etal.2O15.Characterizationofsalinedust emisionresulted from Urmia Lake drying.Journal of Environmental Health Scienceand Engineering,13:82,doi:10.1186/s40201-015-0238-3.   
Gondim R,SilveiraC,SouzaF,et al.2O18.Climate change impacts on water demandand availabilityusing CMIP5 models in the Jaguaribe basin,semi-arid Brazil.Environmental Earth Sciences,77:550,doi:10.10o7/s12665-018-723-9.   
Hung NQ,BabelMS,Wesakul S,etal.2O09.Anartificial neuralnetwork model forrainfallforecasting inBangkok,Thailand. Hydrology and Earth System Sciences,13(8): 1413-1425.   
IPCC(Intergovermmental Panelon Climate Change).2013.Climate change 20l3:The physical sciencebasis,contributionof working group Ito the fifth assessmentreport of the intergovernmental panel on climate change.Cambridge: Cambridge University Press,75,109,113.   
Jena P,AzadS,Nair Rajeevan M.2O15.Statistical selectionoftheoptimum models in thecmip5dataset for climate change projections of indian monsoon rainfall. Climate, 3(4): 858-875.   
Khalili M,Nguyen VT,GachonP.2O13.Astatisticalapproach tomulti-sitemultivariate downscalingof dailyextreme temperature series. International Journal of Climatology, 33(1):15-32.   
Khan N,Shahid S,Ahmed K,etal.2018Performance assssmentof generalciculationmodel in simulatingdaily precipitation and temperature using multiple gridded datasets.Water,10(12): 1793,doi:10.3390/w10121793.   
Lippmann R P.1987.An introduction to computing with neural nets. IEEE ASSP Magazine,4(2): 4-22.   
LiuT,Willems P,PanXL,etal.20l1.Climate changeimpacton waterresource extremes inaheadwaterregionof theTarim basin in China,Hydrology and Earth System Sciences,15:3511-3527.   
Liu Z,Xu Z,HuangJ,etal.2010.Impactsofclimatechangeonhydrologicalproceses intheeadwatercatchmentof he Tarim River basin,China.Hydrological Processes,24(2):196-208.   
MaraunD,WeterhallF,resonAM,etal.2O10.Precipitationdownscalingunderclimatechange:recentdevelopmentstobrdge thegap between dynamical models and the end user.Reviews ofGeophysics,48(3): RG3003,doi:10.1029/2009RG000314.   
McSweeney CF,Jones R G,LeeR W,et al.2015.Selecting CMIP5 GCMs fordownscaling over multipleregions.Climate Dynamics,44(11-12): 3237-3260.   
Mendes D,Marengo JA.2O10.Temporal downscaling:acomparison between artificial neural network and autocorrelation techniquesovertheAmazonBasin inpresentandfutureclimatechangescenarios.TheoreticalandApliedClimatology,00(3): 413-421.   
Nikbakht J,Tabari H,TalaeePH.2013.Streamflow droughtseverityanalysis bypercentof normalindex (PNI) in Northwest Iran.Theoretical and Applied Climatology,112: 565-573.   
PatilNS,LaddimathR,PoojaS,etal.2O15.Downscalingofprecipitationdata fromGCMoutputsusingartificialneuralnetwork for Bhima basin. International Journal of Applied Environmental,10(4): 1493-1508.   
PianiC,HaerterJ,CoppolaE.olo.Statistical biascorrectionfordailyprecipitationinregionalclimate modelsoverEurope. Theoretical and Applied Climatology, 99:187-192.   
Skamarock WC,KlempJB,Dudhia J.2008.ADescriptionoftheAdvancedResearch WRF Version3.In: NCAR Technical Note （204号 $\mathrm { T N } { \ - } 4 7 5 { \scriptstyle + \mathrm { S T R } }$ . Colorado, USA.   
Teutschbein C,SeibertJ.20l2.Biascorrectionofregional climate model simulations forhydrologicalclimate-change impact studies: Review and evaluation of different methods.Journal of Hydrology, 456-457:12-29.   
ThemeblMJ,GobietA,Heinrich G.2O12.Empirical-statisticaldownscalingand errorcorrectionofregionalclimate modelsand its impact on the climate change signal. Climatic Change,112: 449-468.   
Thom H C.1958.A note on the gamma distribution.Monthly Weather Review,86(4):117-122.   
Torabi Haghighi A,KloveB.20l7.Designofenvironmental flowregimes tomaintain lakesand wetlands inregions with high seasonal irrigation demand. Ecological Engineering,loo:120-129.   
TranAnhQ,Taniguchi K.2018.Couplingdynamicaland statistical downscaling forhigh-resolutionrainfallforecasting:case studyoftheRedRiverDelta,Vietnam.ProgressinEarthandPlanetary Science,5:28,doi:10.1186/s40645-018-0185-6.   
Tue VuM,AribargT,SupratidS,etal.216.Statisticaldownscalingrainfallusingartificialeuralnetwork:significantlywetter Bangkok? Theoretical and Applied Climatology,126(3-4): 453-467.   
WilbyRL,Charles SP,ZoritaE,etal.2014.GuidelinesforUseofClimate Scenarios Developed from Statistical Downscaling Methods.SupportingMaterialoftheIntergovernmentalPanelonClimateChange.htp://www.ipccdata.org/guidelines/dgm_no2_v1_09_2004.pdf.   
YazdandoostF,MoradianS,Izadi A.2O2o.Evaluationof watersustainabilityunderachanging climate in ZarinehRiverBasin, Iran.Water Resources Management,34 (15): 4831-4846.   
YazdandostF,MoradianS,Izadi A,etal.2021.EvaluationofCMP6precipitationsimulationsacross diferentclimatic zones: Uncertaintyandmodelintercomparison.JouralofAtmosphericResearch,250:05369,doi:10.1016/j.atmosres.0.105369.