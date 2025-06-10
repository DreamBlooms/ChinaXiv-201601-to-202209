# Forecasting solar still performance from conventional weather data variation by machine learning method

Wenjie Gao',Leshan Shen23, Senshan Sun', Guilong Peng', Zhen Shen2,3, Yunpeng Wang', AbdAllah Wagih Kandeal6, Zhouyang Luo2.3, A.E Kabeel7, Jianqun Zhang4\*, Hua Bao5\*, Nuo Yang1\*

1 State Key Laboratory of Coal Combustion, and School of Energy and Power Engineering,   
Huazhong University of Science and Technology, Wuhan 430074, China   
2 Key Laboratory of Solar Energy Utilization & Energy Saving Technology of Zhejiang Province,   
Hangzhou, 311121, China   
3 Zhejiang Energy Group R&D Institute Co., Ltd., Hangzhou, 311121, China   
4 Zhejiang Zheneng Yueqing Electric Power Generation Co., Ltd., Yueqing, 325609, China   
5 University of Michigan-Shanghai Jiao Tong University Joint Institute, Shanghai Jiao Tong   
University, Shanghai, 200240, China   
6 Mechanical Engineering Department, Faculty of Engineering, Kafrelsheikh University,   
Kafrelsheikh 33516, Egypt.   
7 Mechanical Power Engineering Department, Faculty of Engineering, Tanta University, Tanta,   
Egypt

Corresponding authors: N.Y. (nuo@hust.edu.cn); H.B. (hua.bao@sjtu.edu.cn); J.Z. (zhangjianq888@163.com)

# Highlights

This work proposed a method to forecast the freshwater production of solar still by using conventional weather data.   
The dataset was obtained from 8 months of evaporation experiments and measurements. The forecasting model is established by machine learning and has a much higher accuracy than traditional models.   
By applying the model, freshwater productions of four cities were predicted with high accuracy from their weather data.

# Abstract

Solar stills are considered an effective method to solve the scarcity of drinkable water. However, it is still missing a way to forecast its production. Herein, it is proposed that a convenient forecasting model which just needs to input the conventional weather forecasting data. The model is established by using machine learning methods of random forest and optimized by Bayesian algorithm. The required data to train the model is obtained from daily measurements lasting 9 months. To validate the accuracy model, the determination coeficients of two types of solar stills are calculated as 0.935 and 0.929,respectively， which are much higher than the value of both multiple linear regression (0.767) and the traditional models (0.829 and 0.847). Moreover, by appling the model, it is predicted that the freshwater production of four cities in China. The predicted production is approved to be reliable by a high value of correlation (0.868) between the predicted production and the solar insolation. With the help of the forecasting model, it would greatly promote the global application of solar stills.

Keywords: Solar still; Production forecasting; Forecasting model; Weather data; Random forest

# Nomenclatures:

RF Random forest   
BOA Bayesian optimization algorithm   
$\scriptstyle { \mathrm { \mathrm { R } } } ^ { 2 }$ （204 The determination coefficient of the model   
Ws Wind speed m/s   
$\mathrm { W _ { D } }$ （204号 Winddirection

Press.Atmospheric pressure Pa

T Air temperature $^ { \circ } \mathsf { C }$   
$\mathrm { T } _ { \mathrm { m a x } }$ （20 Maximum value of air temperature $\mathcal { \ L }$   
$\mathrm { T _ { m i n } }$ （20 Minimum value of air temperature $\mathcal { \ L }$   
RH Relative humidity $\%$   
AQI The air quality index

BIF-SS The solar still with an interfacial evaporation structure at the bottom and insulation foams at the sidewall

BSI-SS The solar stil with an interfacial evaporation structure at both the bottom and the sidewall

# 1. Introduction

Seawater covers $70 \%$ of the earth, freshwater is mainly distributed in glaciers,ice caps,and underground[1,2]. With the increase in population, industrial activities, the shortage of drinkable Water is a catastrophic issue the world facing[3,41. As seawater accounts for $9 7 \%$ of the water on the earth, desalination is an effective solution for the shortage of freshwater[5].

Among the many desalination technologies, solar desalination[] is one of the most environmentally friendly technologies. Fortunately， areas where freshwater is scarce happen to possess abundant solar energy[7]. Solar stillis one of the solar desalination technologies,which is easy to installand maintain[8]. Solar still has broad application prospects in remote coastal areas and islands.Given this,solar desalination has received widespread atention in recent years[9-18]. However, the value of daily production fluctuates greatlyand much affected by climatic conditions, which is not easily forcasted.

Tranditional models[19-21l show the function between production and a couple of important factors.Due to the complexity of heat and mass transfer in reality， these models with simple functions are difficult to describe the heat and mass transfer process inside the solar still accurately, and limited to guide the design of solar stils[22. Recently, it is an emerging and effective way to predict the performance of solar still by using machining learning method[23l. Such as the multiple linear regresson (MLR) method[24], artificial neural network (ANN) method[25,26], random forest (RF） method[27, 28]. Among current algorithms,RF is an ensemble learning algorithm based on decision tres, with unexcelledaccuracyl29,3o,and shows excellnt performance in predicting[28].

However, the previous studies just gave the functional relationship between the performance and a couple of professional parameters, such as basin plate temperature, glass cover temperature, and feedwater temperature， etc.， which is not convinent to measure for customers. More importantly， the previous models cannot forecast the production in advance，which is a big chanllenge.

The production is greatly affected by weather. And, it is easy to obtain weather forecast data, such as air temperature,humidity, wind, atmospheric pressure, and air quality index. It will be a convenient and efective way to forcast the production if a model could be establish between the production and the weather forecasting data.

The production forecasting is significant to promote the globle application of solar still Even for remote areas, it is not dificult to get the conventional weather forcating. Besides, the forecasting can help to make a stable supply of water or a controllable desalination capacity. That is, with the help of forecasting, a proper substitute desalination strategy can be planned and chosen, such as using the electrically powered desalination as compensation.

This work aims to make a model to forecast the daily production of solar still based on convenient weather data. The required data to train the model was obtained by carrying out experimental measurements from July 2020 to March 2021. Based on the production and weather data,the forecasting model was conducted by using the random forest method. To verify the practicability and accuracy of the model, the determination coeficients were calculated and compared. By applying the model, the freshwater production of four cities in China was forcasted from conventional weather data.

# 2.Experimental systems

The solar stills are consist of a glass cover, basin, foam heat-insulation layer, water feeding tank, freshwater outlet, and required measuring instrument, as shown in Fig.1 (a). The bottom dimension is $5 0 { \times } 5 0$ cm. Singh and Tiwari[31] reported that the annual solar still yield reached a maximum value when the condensing glass cover inclination was equal to the latitude of the place. Thus the glass cover of the solar stills has an inclination angle of $3 0 ^ { \circ }$ ， which is the preferred solar incidence angle at Hangzhou ( $\cdot 1 2 0 . 2 ^ { \circ } \mathrm { ~ E } , 3 0 . 3 ^ { \circ } \mathrm { ~ N } )$ . The equipment is installed on the roof of a building in Hangzhou, China. The solar still is placed horizontally and the front is south facing.

The schematic of solar still is shown in Fig.1 (b). The solar still has an interfacial evaporation structure at the bottom and insulation foams at the sidewall (BIF-SS). The BIF-SS adopts a threelayer composite structure: floating light absorption layer， water-conducting layer,and heatinsulating layer. The light-absorbing layer structure is made of black deerskin velvet fiber cloth, with $9 5 \%$ solar absorption. The water-conducting layer is made of cotton fiber cloth with a thickness of about $8 ~ \mathrm { m m }$ ， and in contact with seawater through the water-conducting channel. The sides and bottom are all wrapped with heat-insulating extruded foam XPS board, 2 cm thick. The thermal conductivity of the XPS board is O.O3 W/m-K. The freshwater is obtained from the freshwater collction tank， recording by cylinder manually. The solar still with interfacial evaporation structure is designed based on our previous work[32]， which has both high energy efficiency and salt rejection capacity. Meanwhile, a control group was set up on the solar still with an interfacial evaporation structure at both the botom and the sidewall(BSI-SS).The schematic of BSI-SS is shown in Fig. 1 (c).

![](images/88683a938ef8ae85d87558f97f310c91e14dea7286905b6f5a3cbf226a085b00.jpg)  
Figure l(a) The photo of the solar stillsystem for measurement in Hangzhou.The diagrams of two types of solar stills with an interfacial evaporation structure: (b)at the bottom and the insulation foams at the sidewall (BFI),and (c) on both the bottom and sidewall (BSI).

The measurements need a series of sensors which are shown in Table 1. The weather parameters were recorded every minute， including wind speed $( \mathrm { W _ { S } } )$ ，wind direction $( \mathrm { W _ { D } } )$ ， atmospheric pressure (Press.), air temperature (T), relative humidity (RH). The air quality index (AQI) data is obtained from the website of www.tianqi.com. The recorded weather data of Hangzhou is shown in Fig. 2 which is expressed as daily average values. Afected by the El Nino, the average temperature in August is highest, which is significantly higher than that in July. Meanwhile, August is the driest month with the lowest average air humidity. It also can be seen from Fig. 2 that the AQI and atmospheric pressure are higher in the winter.

Table 1 The test platform of meteorological data

Name Device model Range Accuracy Resolutir Wind speed sensor 011E-MetOne 0-60 m/s ±0.1 m/s 0.04 m/ Wind direction sensor 020C-MetOne 0-360° ±3° <0.1°   
Environmental humidity sensor HC2S3-Campbell 0-100% RH ±0.8% RH 0.1% Rl   
Atmospheric pressure sensor CS106-Campbell 500-1100 kPa ±0.3 kPa ±0.1 kP   
Ambient temperature sensor 110PV-Campbell -40-135C ±0.2℃ Data collector CR100-Campbell 0-4200 g 0.01g 30 ℃ 20 3>>> T 10 wmwm 0 a 100 WWMW 80 WW % 60 B 40 20 140 104 120 wWm 0 1030 P 1020 Wwwwnyvnow ssss 1010 1000 wMw 990 （d） Ju Aug Sep Oct Nov Dec Jan Feb Month

Fig. 3 (a) shows the hourly production of the BIF-SS on March 9th, the freshwater productivity gradually increases from 8:OO and reaches the highest at 12:0O about $0 . 8 ~ \mathrm { k g / m } ^ { 2 } { \cdot } \mathrm { h }$ .By 20:00, the productivity is close to 0.Fig. 3 (b) shows the recorded water production of the solar still from July 2020 to March 2021. Affected by the weather, the daily production varies. The freshwater production in August was the highest and significantly higher than in the other months. The highest daily production is $6 . 0 \mathrm { k g / m } ^ { 2 . }$ day. The data of weather and production listed in supporting materials (SM) I.

![](images/4fac9cef27f061ad41090393d899c27d2a717bd358c0075941bb7be9b8c7109b.jpg)  
Figure 3(a) Both the accumulated production (red dots)and the hourly production (black squares)of the BIF solar still on March $9 ^ { \mathrm { t h } }$ ,2021.(b) The daily production of BIF-SS measured from July 202O to March 2021, which is a part of the dataset for building the forecasting model.

# 3.Machine learning methods

The forecasting model is established based on the dataset. The solar still dataset is given as $\scriptstyle \mathrm { F } = \{ X , y \} _ { 1 : i } ,$ where $X$ is the input parameter, including Week, $\mathrm { W _ { S } , W _ { D } , }$ T, Press, RH, and AQI, and $y$ is daily production, the target value corresponding to $X$

The basic steps include data preprocessing, model construction, and algorithm optimization. The process of data preprocessing refers to scaling the data atributes to a specific range. Because the data attributes with larger magnitudes will dominate,the accuracy of the model willbe affected. The standardized method (Z-Scale) is used to scale the input data parameter. The Z-Scale method is based on the mean and standard deviation of the original data, the sample spacing can be maintained. After data standardization, the RF method is used to establish the forcasting model. First, selecting samples randomly, divided into training and test set. Then, building a decision tree for each piece of data, and get the predicting result. Last, vote on all the results and get the final result. The Bayesian optimization algorithm (BOA)[28] is used for searching the most appropriate hyper-parameters of the RF model. The Diagram of the forecasting model establishment is shown in

![](images/8eb8c4ce848a14ea75a597fff8e733d9c2385b415c9bbe93f42f5377eeeace67.jpg)  
Fig. 4 (Details in SM II)   
Figure 4 The flowchart of making the forecasting model, which includes data preprocessing, model construction, algorithm optimization.

4.Results and discussions

# Forcasting results of RF model

Fig. 5 shows the performance of forcasting model for three different cases of testing dataset. The determination coefficient $( \mathbb { R } ^ { 2 } )$ and mean square error (MSE） are used to evaluate the performance of the forcasting model (details in SM II). With the increasing/decreasing of the size of training/testing dataset, $\mathrm { R } ^ { 2 }$ of the random forest models remains at a high level and improves gradually which indicates the model processes a good convergence. The value of $\mathrm { R } ^ { 2 }$ and MSE are 0.935 and 0.209, respectively, when the test size is $10 \%$

![](images/f8490155dc5afefbe04deaad9c961a2529e09d0f1c3ed32782008334ee621d19.jpg)  
Figure 5 For BIF-SS,the predicted values versus the measured values corresponding to different sizes of testing dataset, which are (a) $10 \%$ (b) $20 \%$ and (c) $30 \%$ of the dataset, respectively. The value of $\mathrm { R } ^ { 2 }$ is much higher than that of multiple linear regression (0.767).

The value of $\mathrm { R } ^ { 2 }$ is much higher than that of multiple linear regression (O.767) and traditional models. For example, Kumar[20] developed a thermal model to predict the exact performance of solar stills for a different range of Grashof Number, the value of $\mathrm { R } ^ { 2 }$ of Kumar's model was only 0.829. In Panchal's work[21, the main parameters of the theoretical model were water temperature and inner glass cover temperature, and the $\mathrm { R } ^ { 2 }$ of the model was O.847. The results in Fig. 5 indicate that the RF method possesses a much higher predicting accuracy than traditional models. (Details of calculation in SM III.)

# Correlation between productions and weather parameters

It was evaluated that the degree of correlation between the production of solar stills and the conventional weather forecasting parameters. The random forest method was preferred due to its superior forecasting performance. And the results are shown in Fig. 6. The three highest parameters are the daily highest temperature $\left( \mathrm { T } _ { \mathrm { m a x } } \right)$ , relative humidity (RH),and the daily lowest temperature （204号 $\left( \mathrm { T } _ { \mathrm { m i n } } \right)$ whose values are $41 \%$ ， $20 \%$ ，and $1 8 \%$ ， respectively. Moreover, Press., $\mathrm { w _ { s } }$ and $\mathrm { W _ { D } }$ have similar importance values in the range of $2 . 3 \%$ to $3 . 6 \%$ ，which is close to that of random orders $( 2 . 1 \% )$ . The random orders were generated randomly, so it was a factor having no correlation with the production and used as a normal value for comparision.

It indicates that $\mathrm { T } _ { \mathrm { m a x } }$ ,RH,and $\mathrm { T _ { m i n } }$ are the three highest correlated factors correalating with the production. $\mathrm { T } _ { \mathrm { m a x } }$ has the higherst correlation values. When the temperature rises due to increasing solar radiation, the evaporation rate willbe increased.The relative humidity has a higher degree of correlation because the relative humidity directly reflects weather conditions and solar radiation. When the air humidity is high, it is usually cloudy or rainy and has low radiation intensity. Besides the three highest correlated factors, the air quality index has an importance value of $6 \%$ . AQI can also affect solar radiation energy. When the AQI is high,it means the air quality is poor and the particulate matters scatter the sunlight, which reduces the solar energy entering solar stills.

![](images/da2b190e4325e608d2840da8d185c25172cbf2b5ca19db19cd01c0065bfc79e6.jpg)

Figure 6 The degree of correlation between the production of solar stills and the conventional weather forecasting parameters.. The three parameters with highest values are the daily highest temperature $\left( \mathrm { T _ { \ m a x } } \right)$ ， relative humidity (RH),and the daily lowest temperature $\left( \mathrm { T } _ { \mathrm { m i n } } \right)$ ， whose values are $41 \%$ ， $20 \%$ ，and $18 \%$ ， respectively.

# Forcasting results between different types of solar still

A control group was set up to verify the accuracy and applicability of the predicting RF method. The solar evaporation experiments were done on the solar still with an interfacial evaporation structure at both the bottom and the sidewall (BSI-SS).

Fig.7 shows the results of the predicting performance based on the production data of BSI-SS.

The predicting results are comparable to the BIF-SS.As shown in Fig. 8, $20 \%$ of production data is used as the test set. The forcasting models based on the two types of solar stills show high predicting accuracy, the $\mathrm { R } ^ { 2 }$ of the BIF and BSI are O.927 and O.939. The results verify the high accuracy and applicability of the forcasting model.

![](images/56e28a20f0ee944aba6a153e23e4a8a1328e6593553ff4c35fdb265b65b8eb2a.jpg)  
Figure 7 The results of the predicting performance between different test sizes (BSI-SS).

![](images/314a3be377f5d2a30442c1a68b86d2d63909c795627bf8d12d8702aa2cdbdfc0.jpg)  
Figure 8 Comparison of the production values between the measured and the predicted, using $20 \%$ of production data as the test set. (a) BIF-SS;(b) BSI-SS.

# 5 Appliying forcasting model

By applying the forcasting model, freshwater production of four Chinese cities (Wuhan, Hefei, Chongqing,and Linzhi) was calculated and predicted from the weather data. It is are obtained from the China meteorological data center (http://data.cma.cn) that the weather data from July 2020 to February 2021 including air temperature,atmospheric pressure, wind speed and direction, relative humidity, air quality index. The four cities are picked up because they have similar latitudes to Hangzhou $( \sim 3 0 \ : \mathrm { N } )$ . Then, the daily productions from July 202O to February 2021 were calculated and predicted based on the daily weather data.

The average daily productions of the four cities are shown in Fig. 9. The average daily productions in Hefei and Wuhan are similar to that of Hangzhou, $2 . 1 8 ~ \mathrm { k g } / \mathrm { m } ^ { 2 }$ per day. Because the three cities have similar latitudes and are located close to the Yangtze River,that is,the climates of these three cities are similar. The production of Chongqing is the lowest among these cities, 2.1 $\mathrm { k g / m } ^ { 2 }$ per day， because Chongqing is foggy all year round and its intensity of solar radiation is lower than other cities.The production of Linzhi is the highest, $2 . 4 8 ~ \mathrm { k g } / \mathrm { m } ^ { 2 }$ per day. This is because Linzhi is located at the Qinghai-Tibet Plateau and has a high altitude $( 3 . 1 ~ \mathrm { k m } )$ and insolation. The predicted daily production of the three cities were shown in SM IV.

![](images/dbb5ed1dc2e2f9534f7c392d810abd906973b43f7812144c709816a0dbe84094.jpg)  
Figure 9 The predicted average daily production of five cities in China by using the RF model. The production of Linzhi is the highest due to its high elevation and insolation.Chongqing is the lowest due to its dense mist and lower radiation

Furthermore, The daily solar insolation data is obtained from the China meteorological data center to analyze the prediction accuracy. It needs a gauge to check the predicted values because there are no measured values of production. As shown above, solar insolation is not used in building the model. That is,the values of solar insolation are independent of the predicted production. Generally, the solar insolation is in direct proportion to the production,which can be used as a gauge to check the predicted values.Fig.10 shows the comparison of the predicted daily production and the solar insolation from July 2020 to February 2021 in Wuhan. Because of the higher/lower radiation intensity and temperature,the production should be higher in the summer/winter. The changing trend of the predicted production is similar to the daily solar insolation.And the correlation coefficient of the two data sets is O.868，which indicates that the forcasting model possesses high accuracy.

![](images/6f499c930fa3f458f6d7a0923735a3863a10515299039a640a9f6ceae4849bff.jpg)  
Figure 10 A comparison of the predicted daily production and the solar insolation from July 2O20 to February

2021 in Wuhan.The correlation coefficient of the predicted daily production and the solar insolation is   
0.868, which indicates that the forcasting model possesses high accuracy.

# 6. Conclusions

In a conclusion, a forecasting model is built, that can forecast freshwater production by convenient weather data.To collect the dataset, a series of solar evaporation experiments were done from July 2020 to March 2021 based on two types of solar stills, where the values of production and weather data were recorded. Then, the model to forecast solar still production was established by using the random forest method and conducted by the Bayesian optimization algorithm

The forecasting model has a high accuracy. The determination coefficient $( \mathbb { R } ^ { 2 } )$ on the training dataset and test dataset can reach 0.946 and O.935,respectively, the test size is $10 \%$ of production data. A control group was set up to verify the accuracy and applicability of the predicting RF method, the determination coefficients of two types of solar stills are calculated as 0.935 and 0.929.

To look for closely related parameters, it was also calculated that the degree of correlation between the production and weather parameters. The three highest correlated parameters are maximum air temperature， Relative humidity， minimum air temperature， whose degree of correlation are $41 \%$ 0 $20 \%$ ， $18 \%$ , respectively.

By applying the model, productions of four cities were predicted with high accuracy from their weather data. To verify the reliability of the predicted results, the predicting results were compared with the daily solar insolation data. The correlation coefficient between predicted production and the solar insolation is O.864, indicating that the predictions have high accuracy.

With the help of the forecasting model, it would greatly promote the global application of solar stills.

# Data Availability Statement.

Replicationdataand code can be found on the website forthisproject: http://nanoheat.energy.hust.edu.cn/Code_ 22_ 1.rar .

# Acknowledgment

The work was sponsored by the National Key Research and Development Program of China (2018YFE0127800), Science, Technology &Innovation Funding Authority (STIFA), Egypt grant (40517)，China Postdoctoral Science Foundation (2O20M682411)，and Fundamental Research

Funds for the Central Universities (2019kfyRCPY045).

# References

[1] El-Samadony Y, Kabeel A E. Theoretical estimation of the optimum glass cover water film cooling parameters combinations of a stepped solar still Energy, 2014, 68:744-750.   
[2] Abujazar M S S,Fatihah S,Lotfy E R, et al. Performance evaluation of inclined copper-stepped solar still in a wet tropical climate[J]. Desalination, 2018, 425: 94-103.   
[3] Kabeel A E,Arunkumar T, Denkenberger D C, et al. Performance enhancement of solar still through efficient heat exchange mechanism- A review. Applied Thermal Engineering, 2017, 114:815-836.   
[4] Kumar P V, Kumar A, Prakash O, et al. Solar stils system design: A review[J]. Renewable and sustainable energy reviews, 2015, 51: 153-181.   
[5] Elimelech M, Phillip W A. The Future of Seawater Desalination: Energy, Technology, and the Environmen. Science, 2011, 333(6043):712-717.   
[6] Guilong Peng, Swellam W. Sharshir, Yunpeng Wang,et al. Potential and challenges of improving solar still by micro/nano-particles and porous materials- A review. Journal of Cleaner Production,2021, 311(9):127432.   
[7] Mekonnen M M, Hoekstra A Y. Four billion people facing severe water scarcity. Science Advances,2016, 2(2):e1500323-e1500323.   
[8] Swellam W. Sharshir, Guilong Peng, Ammar H. Elsheikh, et al. Influence of basin metals and novel wick-metal chips pad on the thermal performance of solar desalination process.Journal of Cleaner Production, 2020, 248,119-224.   
[9] Shalaby S M, Sharshir S W, Kabeel A E, et al. Reverse osmosis desalination systems powered by solar energy: Preheating techniques and brine disposal challenges-A detailed review. Energy Conversion and Management, 2022, 251: 114971.   
[10] Kandeal A W, El-Shafai N M, Abdo M R, et al. Improved thermo-economic performance of

solar desalination via copper chips, nanofluid, and nano-based phase change material. Solar Energy, 2021,224: 1313-1325.

[11] Qian Chen, Alrowais R, Burhan M, et al. A self-sustainable solar desalination system using direct spray technology. Energy, 2020,205:118037.   
[12] Gao M, Zhu L, Peh C K, et al. Solar absorber material and system designs for photothermal water vaporization towards clean water and energy production. Energy & Environmental Science, 2019, 12(3): 841-864.   
[13] Guilong Peng, Shichen Deng, Swellam W. Sharshir, et al. High efficient solar evaporation by airing multifunctional textile. International Journal of Heat and Mass Transfer, 2019,147:118866. [14] Chen S, Zhao P, Xie G, et al. A floating solar still inspired by continuous root water intake. Desalination, 2021, 512: 115133.   
[15] Rahmani A, Kemmar F, Saadi Z. Experimental investigation on the negative effect of the external condenser on the conventional solar still performance. Desalination, 2021, 501:114914. [16] Guo Y, Dundas C M, Zhou X, et al. Molecular engineering of hydrogels for rapid water disinfection and sustainable solar vapor generation. Advanced Materials,2O21, 33(35): 2102994. [17] Swellam W. Sharshir, Guilong Peng, Wu L, et al. Enhancing the solar still performance using nanofluids and glass cover cooling: Experimental study. Applied Thermal Engineering, 2017, 113: 684-693.   
[18] Cheng D, Gong W, Li N. Response surface modeling and optimization of direct contact membrane distillation for water desalination. Desalination, 2016, 394: 108-122.   
[19] R.Dunkle. Solar water distillation the roof type still and a multiple effect diffusion stil. International Development in Heat Transfer, 5 (1961) 895-902.   
[20] S. Kumar, G.N. Tiwari, Estimation of convective mass transfer in solar distillation systems. Sol. Energy, 57 (1996) 459-464.   
[21] Panchal H. Performance investigation on variations of glass cover thickness on solar stil: experimental and theoretical analysis[J]. Technology and Economics of Smart Gridsand

Sustainable Energy, 2016, 1(1): 1-11.

[22] C.Elango，N. Gunasekaran，K. Sampathkumar， Thermal models of solar still—A comprehensive review. Renewable Sustainable Energy Rev., 47 (2015) 856-911.   
[23] Ham A, Mbb C, D A, et al. Performance estimation of a mini-passive solar still via machine learning. Renewable Energy, 2020, 162:489-503.   
[24] Mashaly AF, Alazba AA. MLP and MLR models for instantaneous thermal effciency prediction of solar still under hyper-arid environment. Computers and Electronics in Agriculture. 2016;122:146-55.   
[25] Ren Y-S,Lei L, Deng X, Zheng Y, Li Y, Li J,et al. Novel application of neural network modelling for multicomponent herbal medicine optimization. Scientific Reports. 2019;9:15442 [26] Pei J, Deng L, Song S, Zhao M, Zhang Y, Wu S, et al. Towards artificial general intelligence with hybrid Tianjic chip architecture. Nature. 2019;572:106.   
[27] Belmokre A, Mihoubi M K, D Santillan. Analysis of Dam Behavior by Statistical Models: Application of the Random Forest Approach. KSCE Journal of Civil Engineering,2019(2). [28] Yunpeng Wang,A.W.Kandeal, Swellam W. Sharshir, et al. Prediction of tubular solar still performance by machine learning integrated with Bayesian optimization algorithm. Applied Thermal Engineering.2020;186: 116233.   
[29] Svetnik V. Random forest: a classification and regression tool for compound classification and QSAR modeling. Journal of Chemical Information & Computer Sciences, 2003;43(6):1947-58 [30] Chan C W, Paelinckx D. Evaluation of Random Forest and Adaboost tree-based ensemble classification and spectral band selection for ecotope mapping using airborne hyperspectral imagery. Remote Sensing of Environment, 2008,112(6):2999-3011.   
[31] Singh H N, Tiwari G N. Monthly performance of passive and active solar stills for different Indian climatic conditions. Desalination, 2004,168:145-150.   
[32] Shi J, Luo X, Liu Z, et al. Efficient and antifouling interfacial solar desalination guided by a transient salt capacitance model. Cell Reports Physical Science, 2021, 2(2):100330.