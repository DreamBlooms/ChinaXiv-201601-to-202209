# Improving wood volume predictions in dry tropical forest in the semi-arid Brazil

Robson B de LIMA1\*, Patricia AB BARRETO-GARCIA²,Alessandro de PAULA², JhulyESPEREIRA³,FlaviaFdeCARVALHO², Silvio HMGOMES4

l Department of Forest Engineering, State University of Amapä,Macapä 689ooo7o,Brazil;   
²Departmentof Forest Science,State Universityof SouthwestBahia, Vitoria da Conquista 450839oo,Brazil; 3 Universidade Federal de Lavras,Lavras 37200900,Brazil;   
4 Universidade de Sao Paulo,Piracicaba 1341890o,Brazil

Abstract: The volumetric variability of dry tropical forests in Brazil and the scarcity of studies on the subject show the need for the development of techniques that make it possible to obtain adequate and accurate wood volume estimates.In this study,we analyzed a database of thinning trees from a forest management plan in the Contendas de Sincora National Forest, southwestern Bahia State,Brazil. The data set included a total of 3OO trees with a trunk diameter ranging from 5 to $5 2 \mathrm { c m }$ .Adjustments, validation and statistical selection of four volumetric models were performed. Due to the difference in height values for the same diameter and the low correlation between both variables, we do not suggest models which only use the diameter at breast height (DBH) variable as a predictor because they accommodate the largest estimation errors. In comparing the best single entry model (Hohenald-Krenn) with the Spurr model (best fit model),it is noted that the exclusion of height as a predictor causes the values of 136.44 and 0.93 for Akaike information criterion (AIC) and adjusted determination coefficient $( \mathrm { R } _ { \mathrm { a d j } } ^ { 2 } )$ ,which are poorer than the second best model (Schumacher-Hal). Regarding the minimum sample size, errors in estimation (root mean square error (RMSE) and bias) of the best model decrease as the sample size increases, especially when a larger number of trees with $\mathrm { D B H } { \geq } 1 5 . 0 \ \mathrm { c m }$ are randomly sampled. Stratified sampling by diameter class produces smaller volume prediction errors than random sampling, especially when considering all trees. In summary, the Spurr and Schumacher-Hall models perform beter. These models suggest that the total variance explained in the estimates is not less than $9 5 \%$ ，producing reliable forecasts of the total volume with shell. Our estimates indicate that the bias around the average is not greater than $7 \%$ .Our results support the decision to use regression methods to build models and estimate their parameters, seeking stratification strategies in diameter classs for the sample trees.Volume estimates with valid confidence intervals can be obtained using the Spurr model for the studied dry forest. Stratified sampling of the data set for model adjustment and selection is necessry,since we find significant results with mean eror square root values and bias of up to $70 \%$ of the total database.

Keywords: volume modeling; minimal sample size; Caatinga; Spurr model; forest management

# 1 Introduction

The Caatinga is an exclusively Brazilian biome occupying approximately $7 \%$ of the national territory and constitutes one of the largest semi-arid areas in the world (Miles et al.,2Oo6; Queiroz, 2009；Araujo and Silva, 201O； Moro et al.，2O16). The name Caatinga has indigenous origin (Tupi-Guarani) and its meaning (white forest, or mata branca in Portuguese) is associated with the open and gray aspect of the vegetation component (Moro et al.,2O16), which is part of the group of seasonally dry tropical forests (Murphy and Lugo,1986). These forests grow on soils ranging from clayey and shallow to sandy and underlying (Costa et al.,2O14),and are resistant to up to 10 months of drought (Murphy and Lugo,1995; Pennington et al., 20o6; Dalmagro et al., 2014).

Forest ecosystems with complex mosaic distributed vegetation and high species' endemism, such as Caatinga dry tropical forests,are among the most fragmented and endangered in the world (Silva and Bates 2002; Miles et al.,2006; Werneck,2011). Thus,studies related to monitoring,detecting and mapping environmental changes,as well as to obtaining estimates of forest parameters become of great importance in this scenario, since they support sustainable forest management, aiming at the conservation and maintenance of the services provided.

The wood volume present in a forest is a valuable information to elaborate sustainable forest management plans (SFMPs),as it is the basis for assessing the forest stock of a region and assists in planning forest exploitation (Leite and Resende,2O1O).In Brazil, the Brazilian Institute of Environment and Renewable Natural Resources (IBAMA) requires that the volume of standing trees presented in SFMPs should be estimated using volumetric equations (Brasil, 2006).

Volumetric equations are usually obtained by adjusting mathematical models using regression techniques，and constitute the most adopted and efficient procedure for quantifying forest production (Cabacinha et al.，2O13; Silva-Ribeiro et al., 2014). Many allometric equations have been developed for various vegetation types,but they are rarely validated in the field,especially for seasonally dry tropical forests such as Caatinga (Sampaio et al., 2010).

Studies related to volumetric modeling of dry forest phytophysiognomy trees are rare in the literature,despite its relevance as a shelter of remarkable biodiversity of fauna and flora (Albuquerque et al.,2O12). Some authors also reported the dificulty of obtaining good allometric adjustments of individual trees of the predominant species in these phytophysiognomies,as they usually present tortuous trunks which fork near the ground (Lima et al.,1996). However, Souza et al.(2016) recommended the Schumacher-Hall and Spurr linear models to obtain stem volume estimates in typical Caatinga shrubby tree vegetation; and Lima et al. (2O17) found that total volume estimates for Caatinga species in the state of Pernambuco are more accurate when dendrometric stem and branch variables are included in the model using the least squares method.

The different results found reveal the typical volumetric variability of Brazilian dry tropical forests conditioned by variations in stem shape,branch shape,density and genetic characteristics (Lima et al., 2O17). There is a clear need to develop techniques for obtaining adequate and accurate volume estimates from tree sample volume data.

Herein,we analyzed a database of thinning trees from a forest management plan in the Contendas de Sincora National Forest (FLONA), southwestern Bahia State, Brazil. Our data set included a total of 3OO trees with trunk diameters ranging from 5 to $5 2 ~ \mathrm { c m }$ . We addressed the following questions: (i) what is the best volumetric model in predicting volume with bark? (ii) what is the best tree sampling strategy to produce models? and (ii) how does the number of trees used in fiting affect forecast errors with respect to the performance of the best locally derived model?

# 2 Materials and methods

# 2.1 Study area

The study was conducted in an area of Caatinga forest $( 1 3 ^ { \circ } 5 5 ^ { \prime } 2 1 ^ { \prime \prime } \mathrm { S }$ ， $4 1 ^ { \circ } 0 6 ^ { \prime } 5 7 ^ { \prime \prime } \mathrm { W } )$ belonging to the FLONA, which has an area of about $1 . 1 0 { \times } 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ and is located in south of Chapada Diamantina, in the municipality of Contendas do Sincora, southwestern Bahia State,Brazil.The vegetation is classified as savanna-steppe forest of arid land late successional stage,since the last intervention record in the area dates from 1997 (Ministry of the Environment, 2O06;Brazilian Institute of Geography and Statistics,2012).

The local climate is semi-arid (BSwh) according to the Koppen classification, with well-defined dry season and annual mean temperature of $2 3 . 0 ^ { \circ } \mathrm { C }$ (Alvares et al. 2O13). The annual precipitation is between 596.0 and $6 7 8 . 5 \mathrm { m m }$ , with most distributed from November to April. The altitude range of the region is $2 9 5 { - } 3 8 0 ~ \mathrm { m }$ a.s.l., reaching $5 8 0 \mathrm { m }$ a.s.l.in mountainous areas.The study area in the FLONA is located in the Resource Management Zone,determined by the Conservation Unit

Management Plan (Ministry of the Environment， 2Oo6)，which provides for and encourages research and management programs.

# 2.2Tree sampling and volume determination

We randomly selected 48 plots of $2 0 \ \mathrm { m } { \times } 2 0 \ \mathrm { m }$ $( 4 0 0 ~ \mathrm { m } ^ { 2 } )$ in order to understand the population diameter variation. We then measured the diameter at breast height (DBH) in each plot, taken at 1.3 m from the ground for all tree individuals with $_ { \mathrm { D B H } \ge 5 . 0 ~ \mathrm { c m } }$ .We measured the diameter of all the stems originating below $1 . 3 \mathrm { m }$ ,and used the quadratic diameter to obtain a single diameter per tree when a single tree had several stems (tillring). The stem DBH measurements were grouped into six diameter classes with an amplitude of eight centimeters,as shown in Table 1.

Table 1 Diametric distribution of tree stems in the dry tropical forest   

<html><body><table><tr><td>DBH classes (cm)</td><td>Class center (cm)</td><td>Frequency</td></tr><tr><td>5.0-13.0</td><td>6.50</td><td>1.2</td></tr><tr><td>13.1-21.0</td><td>17.05</td><td>96.0</td></tr><tr><td>21.1-29.0</td><td>25.05</td><td>25.0</td></tr><tr><td>29.1-37.0</td><td>33.05</td><td>7.0</td></tr><tr><td>37.1-45.0</td><td>41.05</td><td>4.0</td></tr><tr><td>45.1-53.0</td><td>49.05</td><td>2.0</td></tr></table></body></html>

Note:DBH,diameter at breast height.

We rigorously measured the volume of 3OO randomly selected trees distributed in different diameter classes proportionally to their frequencies (Table 1). We measured the diameters on each trunk with the bark at the 0.1, 0.3, 0.5, 0.7,1.0, 1.3 and $2 . 0 \mathrm { m }$ level positions from the soil using the Smalian method for calculating the volume.Then the sections were measured from this point at intervals of $1 . 0 \mathrm { m }$ to the height where the diameter of three centimeters was,and then the length of the tip was measured. The total volume of each stem was obtained by summing the volume of all sections plus the tip volume,and then the total volume of each tree was obtained by the sum of the stem volumes.

We considered the height of the largest stem as the total height for individuals with more than one stem,and obtained the diameter equivalent to the height of $1 . 3 \mathrm { ~ m ~ }$ (DEq) from the DBH of the multiple stem of each tree.The DEq assumes that the cross-sectional area $( \mathbf { m } ^ { 2 } )$ at $1 . 3 \mathrm { ~ m ~ }$ ofa multi-stem tree is equivalent to the sum of the individual cross-sectional areas of each stem and is defined by the root sum of squares of the stem DBH (Fraga et al., 2014).

# 2.3 Fitting of volumetric models

We tested two volumetric models based only on DBH and two combinations of DBH and height (H) commonly used to estimate trunk volume in the region:

$$
\ln ( \mathrm { V O L } ) = \beta _ { 0 } + \beta _ { 1 } \times \ln ( \mathrm { D B H } ) + \beta _ { 2 } \times \ln ( \mathrm { H } ) + \varepsilon ,
$$

where VOL $( \mathbf { m } ^ { 3 } )$ is the volume with bark; $\beta _ { i }$ is the parameter to be estimated; DBH (cm) is the diameter at breast height measured at $1 . 3 \mathrm { m }$ from trunk length; $\mathrm { ~ H ~ } ( \mathrm { m } )$ is the total height; and $\varepsilon$ is the random error.

The parameters of the Hohenald-Krenn，Spurr and Schumacher-Hall models were estimated using the Ordinary Least Squares(OLS） method. Husch's non-linear model was adjusted by modifying the Levenberg-Marquardt algorithm using the "minipack.lm" package. The parameters were generally calculated using the total tree population sampled in each plot and were assumed to be true parameters representing trunk volume.

The obtained equations were analyzed by comparing some statistical indices (Vanclay,1994):

Akaike information criterion (AIC)，adjusted determination coefficient $( R _ { \mathrm { a d j } } ^ { 2 } )$ ，root mean square error (RMSE) and bias,with the formulas described below:

$$
\mathrm { A I C } = - 2 \mathrm { L L } + 2 k ,
$$

$$
R _ { \mathrm { a d j } } ^ { 2 } = R ^ { 2 } - \biggl [ \frac { k - 1 } { n - k } \biggr ] { \times } \bigl ( 1 - R ^ { 2 } \bigr ) ,
$$

$$
\mathrm { R M S E } = \sqrt { \frac { \sum _ { i = 1 } ^ { n } ( V _ { i } - \hat { V _ { i } } ) ^ { 2 } } { n } } ,
$$

$$
\mathrm { B i a s } = { \frac { \sum _ { i = 1 } ^ { n } ( V _ { i } - { \overline { { V } } } _ { i } ) ^ { 2 } } { n } } / { \overline { { V } } } ,
$$

where LL is the likelihood-log; $k$ is the number of model parameters; $R ^ { 2 }$ is the coefficient of determination; $n$ is the number of trees measured; $V _ { i } ( \mathbf { m } ^ { 3 } )$ is the volume with individual bark $i ; \ \hat { V _ { i } }$ $( \mathbf { m } ^ { 3 } )$ is the estimated volume with bark of the tree $i$ $\overline { { { V } } } _ { i } ( { \bf m } ^ { 3 } )$ is the arithmetic mean of volume with bark; and $\overline { { V } }$ is the mean volume.

# 2.4Minimum sample size for volumetric model development

# 2.4.1 Random sampling

We iteratively generated sub-samples from the total dataset and from trees with DBH greater than $1 5 . 0 ~ \mathrm { c m }$ ，randomly selecting a sub-samples number and increasing the total number of trees by $20 \%$ ， $50 \%$ and $70 \%$ .We followed the best selected model assembly procedure (as described in Section 2.3) for volume estimates for each set of randomly sampled trees. As the random sampling produces highly variable adjusted parameters,we iterated random sampling 1Ooo times for each sample size and calculated the mean parameter in lOoo iterations to produce a single average estimate of $\beta _ { 0 }$ (the constant angular parameter) and $\beta _ { 1 }$ and $\beta _ { 2 }$ (parameters) for each sample size,and to also generate the smallest error and bias measurements in the model calibration.

# 2.4.2Stratified random sampling

We alternatively simulated a stratified random sampling of trees in six size classes (5.O-7.0,7.0- 9.0, 9.0-11.0, 11.0-13.0, 13.0-15.0 and ${ > } 1 5 . 0 \ \mathrm { c m } { \dot { } } ,$ ）forall trees with $\mathrm { D B H } { \geq } 5 . 0$ cm, and 15.0-20.0, 20.0-25.0,25.0-30.0 and $> 3 0 . 0 \mathrm { c m }$ for trees with $\mathrm { D B H } { \geq } 1 5 . 0 \ \mathrm { c m }$ Similarly, $20 \%$ + $50 \%$ and $70 \%$ of the trees within a given class were randomly chosen (Duncanson et al.,2O15). The sample size was increased by selecting trees at random from both the total data and trees with $\mathrm { D B H } \ge 1 5 . 0$ cm. We also performed bootstrap in this procedure until we found the smallest measurements of error and bias in the model calibration. The best local model was developed for each subset and applied to the remaining data for cross validation.

We used R statistical software (R Development Core Team,2O19） in all computations and analyses.

# 3 Results

# 3.1 Volumetric models

Among the four adjusted volumetric models,the Spurr and Schumacher-Hall models present a better performance (smaller AIC; Table 2). These models suggest that the total variance explained in the estimates is not less than $9 5 \%$ （2 $( R _ { \mathrm { a d j } } ^ { 2 } )$ ， producing reliable predictions of the total volume with bark. Our estimates indicate that bias around the mean is not greater than $7 \%$ (bias $_ { \mathrm { \Omega } = 0 . 0 7 }$ ; Table 2).

Table 2Estimates of parameters and adequacy indices of four volumetric models of individual trees adjusted for the dry tropical forest   

<html><body><table><tr><td>Model</td><td>β(±SE)</td><td>β (±SE)</td><td>β(±SE)</td><td>AIC</td><td>RSE</td><td>Rdj</td><td>RMSE</td><td>Bias</td></tr><tr><td>Husch</td><td>-8.613 (±0.082)</td><td>2.303 (±0.036)</td><td>-</td><td>141.45</td><td>0.30</td><td>0.93</td><td>0.06</td><td>0.10</td></tr></table></body></html>

JOURNALOFARIDLAND   

<html><body><table><tr><td>Hohenald-Krenn</td><td>-9.504 (±0.346)</td><td>3.058 (±0.286)</td><td>-0.151 (±0.057)</td><td>136.44</td><td>0.30</td><td>0.93</td><td>0.04</td><td>0.09</td></tr><tr><td>Spurr</td><td>-9.914 (±0.089)</td><td>1.013 (±0.013)</td><td>-</td><td>58.88</td><td>0.27</td><td>0.95</td><td>0.06</td><td>0.07</td></tr><tr><td>Schumacher-Hall</td><td>-9.792 (±0.140)</td><td>2.060 (±0.040)</td><td>0.909 (±0.092)</td><td>59.60</td><td>0.27</td><td>0.95</td><td>0.06</td><td>0.07</td></tr></table></body></html>

Note: $\beta _ { i }$ ,the parameterof the models adjusted with their respective confidence intervals obtained bystandard errorofthe mean $( P { > } 0 . 0 5 )$ （204号 SE,standardror;AIC,Akaike iformationcritera;SE,residualstandarderor;MSE,ootmeanquareeror,noatavailable

None of the adjusted models shows lack of fit according to the $F$ -test.All selected models present parameters with valid confidence intervals $( P { > } 0 . 0 5 )$ . Although the volume estimate is similar for the range of trees up to $2 5 . 0 ~ \mathrm { c m }$ in diameter for all four models (Fig.1),there is a noticeable divergence for the other diameter ranges.This can be caused mainly by the height data in which double entry models result in significantly lower percentage biases than models that do not include height.

![](images/128fad14d1fb92e9951c35a8162d1e4f37beb0d4606d6ff5ee81c03be28c56c4.jpg)  
Fig.1Fitting (a) and validation (b) regression curves (color lines） and $9 5 \%$ CIs (CIs,confidence intervals; grey envelopes)offour models (detailed in Table1)relating volumeand diameterat breast height (DBH)of trees in the dry tropical forest

Due to the diference in height values for the same diameter and the low correlation between both variables, we do not suggest models which only use the DBH variable as a predictor because they accommodate the largest estimation errors. In comparing the best single entry model (Hohenald-Krenn) with the Spurr model (best fit model),it is noted that the exclusion of height as a predictor causes the AIC of 136.44 and the $R _ { \mathrm { a d j } } ^ { 2 }$ of 0.93,which are poorer than the second best model (Schumacher-Hal). Therefore,our results suggest that it is more parsimonious to maintain a volumetric Spurr model obtained for the entire FLONA.

The Spurr equation predicts that logarithmic transformation of the combination of tree diameter and height variables for a given volume decreases the bias in the estimate.The functional form of the equations tested is biologically consistent, especially with the inclusion of the height variable, and these results can be illustrated in the residual distribution (Fig. 2).

# 3.2 Minimum sample size

Regarding the minimum sample size, there are three important and visible trends shown in Table 3 and Figure 3.First, errors in estimation (RMSE and bias) of the best model decrease as the sample size increases, especially when a larger number of trees with $\mathrm { D B H } { \geq } 1 5 . 0$ cm are randomly sampled. Second,stratified sampling by diameter class produces smaller volume prediction errors than random sampling,especially when considering alltrees. This is most evident when we evaluate the minimized values of the differences between predicted and observed data.We further note that a significant error reduction occurs up to a $50 \%$ sample size considering random sampling of both all trees and those with $\mathrm { D B H } > 1 5 . 0 \ \mathrm { c m }$ ，while the size of up to $70 \%$ maintains a large mean difference for all trees considering stratified sampling (see bias in Table 3). Third,there is a considerable variability in volume estimates for the area,and this variability also decreases with increased sample size percentage.

![](images/2be3e687d8828eaaea1b3f8aec41d5e832affb13e8dc5d419e8493f28956093d.jpg)  
Fig.2Residualdistribution of wood volume forthe best equation (Spur)obtained for the trees in the dry tropical forest.(a),fitting;(b),validation.

Table 3Statistical criteria for different tree sampling strategies   

<html><body><table><tr><td>Sampling strategy</td><td>RMSE</td><td>RSE</td><td>CV (%)</td><td>Bias</td><td>Percentile (%)</td></tr><tr><td>All trees (stratified)</td><td>0.0559</td><td>0.2644</td><td>65</td><td>-0.0710</td><td>20</td></tr><tr><td>All trees (stratified)</td><td>0.0549</td><td>0.2632</td><td>63</td><td>-0.2452</td><td>50</td></tr><tr><td>All trees (stratified)</td><td>0.0541</td><td>0.2642</td><td>63</td><td>-0.0851</td><td>70</td></tr><tr><td>DBH>15.0 cm (stratified)</td><td>0.1120</td><td>0.2681</td><td>38</td><td>0.4497</td><td>20</td></tr><tr><td>DBH>15.0 cm (stratified)</td><td>0.1066</td><td>0.2672</td><td>36</td><td>-0.4606</td><td>50</td></tr><tr><td>DBH>15.0 cm (stratified)</td><td>0.1083</td><td>0.2715</td><td>37</td><td>-0.3180</td><td>70</td></tr><tr><td>DBH>15.0 cm (random)</td><td>0.2400</td><td>0.2668</td><td>81</td><td>9.4526</td><td>20</td></tr><tr><td>DBH>15.0 cm (random)</td><td>0.1373</td><td>0.2806</td><td>46</td><td>3.8118</td><td>50</td></tr><tr><td>DBH>15.0 cm (random)</td><td>0.1345</td><td>0.2804</td><td>45</td><td>3.5025</td><td>70</td></tr></table></body></html>

lote:RMSE,root mean square error;RSE,residual standard error; CV,coefficient of variation

![](images/5fba256db90f459698bed6f845aec6fdb7ced12a6434d2543e6ba382fd4ac121.jpg)  
Fig.3Root mean square error(RMSE;a)and bias (b)of estimated total volume using diferent percentiles of data size to adjust and validate the best local model

# 4Discussion

Theoretically,regression analysis has been used with emphasis on solving most forest problems, especially when estimating forest parameters through biometric relationships (Robinson and Hamannn,2011; Burkhart and Tomé, 2012; Lima et al.,2014). The use of regression models that can accurately determine forest production based on wood volume estimation is critical to implementing sustainable management (Berger et al., 2014; McRoberts and Westfall, 2014); this allows estimates of the monetary value of forests (Burkhart and Tomé,2012).

Logarithmic models have been constantly used in studying biometric relationships,mainly for developing biomass and volume equations in natural forests (Chave et al.， 2Oo5； Segura and Kanninen,2005; Litton and Boone Kauffman, 2008; Basuki et al.,2009). These models are often generally used in Brazil and particularly in the different tropical dry forests (Lima et al.,2017), although few studies have applied the volume transformation from the logarithmic scale to the original scale using the correction factor(Vibrans et al., 2O15).In addition,robust methods for leveraging model fit quality such as AIC or Bayesian information criteria are rarely used and should be incorporated into statistical model fit routines (Zeng and Tang，2O11). Our results support the decision to use regresson methods to build models and estimate their parameters.

While much of the variation in volume is explained by diameter alone,and the improvement is relatively significant when the height variable is included.Overall,all of the statistical evaluation criteria reveal that double-entry equations show a greater accuracy in predictions,especially the equation obtained from the Spurr model. Therefore,our results indicate the inclusion of the height variable in the volume estimate,since single entry models assume that trees of different diameter sizes have the same heights,which is not true for tropical forests (Brando,2O18; Sullivan et al., 2018).

However, it is important to ensure that the predominant tree growth forms and architecture are represented among the sampled trees used to develop the volumetric model (Duncanson et al., 2015).The accuracy of volume predictions tends to be improved by including height as an explanatory variable in using appropriate tree sample and small measurement errors, despite the added uncertainty using a height and diameter model (Kachamba and Eid, 2016).

Regarding the minimum sample size,we generally notice that stratified sampling presents a higher precision than random sampling,especially when considering trees with $\mathrm { D B H } { > } 1 5 . 0 \ \mathrm { c m }$ in the adjustment of the models.This is because random sampling distorts the sampling for trees with $\mathrm { D B H } { \geq } 1 5 . 0 \ \mathrm { c m }$ ，causing larger errors in the simulations and allowing a less representative sample for smaller trees (Duncanson et al.,2015).

Focusing on the results of stratified sampling,as these are probably more representative of forest measurement, it can be observed that the sample size of $70 \%$ of the total trees is in agreement with the average sampling obtained by Jenkins et al. (2OO3) and Duncanson et al. (2015). In stratified sampling,all trees and for trees with $\mathrm { D B H } { \geq } 1 5 . 0$ cm are likely to have higher mean prediction errors because they simulate a low number of trees per diameter class,and volume estimation biases willincrease with small sample size (Sullivan et al.,2O18). The higher proportion of trees in the stratified sampling yields a more reliable volume estimate at the $70 \%$ level of data. Therefore, our results suggest that stratifying data across different DBH size classes is the most eficient way to develop a generic volumetric model.

This work seeks to fill the gap about the validity of volumetric equations developed for dry tropical forests,although some research has already suggested the development of individual equations for species (Abreu et al.,2O16). The issue currently being discussed and reported in this paper is whether it would be better to use generic volume equations or form factors from other locations,or to develop site-specific equations in locations where no generic volumetric equation is available.

However, there is a lack of guidelines for selecting existing volumetric models and validating alternatives.The limiting factor has always been the destructive sampling of trees for model adjustment and selection (Chave et al.,2O14).Highly accurate estimates of individual tree volumes and biomasses are increasingly available through Lidar technology (Wat et al.,2O13; Levick et al.,

2016; Oliveira et al.,2O18). These estimates do not require destructive tree sampling and can be performed systematicaly in the field (Duncanson et al., 2O15,2O17;Duncanson and Dubayah, 2018). A system could be developed to adequately sample tree volume data in situ at environmental gradients with appropriate sampling, providing a potential solution to outstanding problems related to forest biomass and carbon stock.

# 5 Conclusions

Volume estimates with valid confidence intervals can be obtained by the Spurr model for the FLONA. Stratified sampling by diameter class for model adjustment and selection was proved to be necessary, since we found significant results with lower RMSE and bias values for up to $70 \%$ of the total database and also when only considering trees with DBH>15.O cm. These results can be used by forest managers as a technical tool in predicting the volume of dry tropical forests in southwestern Bahia State,Brazil. Further studies should clarify the mechanisms for developing specific equations at the ecological group,family and commercial species levels.

# Acknowledgements

Special thanks to the National Council for Scientific and Technological Development-CNPq for granting financial support to the project (484260/2013-8).

# References

AbreuJC,SilvaJAA,FerreiraRLC,etal.2O16.Seting linearandnonlinear mathematicalmodels forbiomassestimateand nutrients inAnadenantheracolubrinavar.cebilin thesemiaridregionofPernambuco.ScientiaForestalis,44(1):739-750. (in Brazilian)   
AlbuquerqueUP,AraujoELEl-DeirACA,etal.Ol.Catingarevisited:cologyandconservationofanimportatsasonal dry forest. Scientific World Journal,2012:e205182,doi:10.1100/2012/205182.   
Alvares CA,StapeJL,SentelasPC,etal2Ol3.KoppenclimateclasificationmapforBrazil.MeteorologischeZeitschrit, 22(6):711-728.(in Brazilian)   
AraujoLVC,SilvaJA.2010.Belo Horizonte farm experimentalunit-Mossoró/RN.In: GariglioMA,SampaioEVSB,Cestaro LA,etal.SustainableUseandConservationofCatingaForest Resources.BrazilianForestService,2O5-214.(inBrazilian)   
BasukiTM,vanLaakePE,SkidmoreAK,etal.2Oo9.Allmetricequationsforestimatingtheabove-groundbiomass in tropical lowland Dipterocarp forests.Forest Ecology and Management,257(8): 1684-1694.   
Berger A,GschwantnerT,McrobertsRE,etal.2O14.Effectsof measurement erorsonindiviualtreestemvolume estimatesfor the Austrian national forest inventory.Forest Science,6O(l): 14-24.   
Brando P.2018.Tree height matters.Nature Geoscience,11(1):390-391.   
Brasil.2006.NormativeInstruction,No.5of December1.Provides for technical procedures forthepreparation,executionnd technical evaluation of sustainable forest management plans. [2020-04-24]. https://www.mma.gov.br/estruturas/pnf/_arquivos/in%20mma%2004-06.pdf.(in Brazilian)   
Brazilian Institute of Geography and Statistics.2O12.Technical Manual of the Brazilian vegetation $( 2 ^ { \mathrm { n d } } )$ .Rio de Janeiro,Brazil, 271.(in Brazilian)   
Burkhart HE,Tomé M.2O12.Modeling Forest Trees and Stands.Dordrecht: Springer Netherlands,1-460.   
CabacinhaCD,ScolforoJRS,Thiersch,CR,etal.2O13.Anewapproach forthegeometric methodusing theparabolaindex method.Ciencia Florestal,23(1): 261-271. (in Brazilian)   
Chave J,AndaloC,BrowS,etal.2Oo5.Treealometryandimprovedestimationofcarbonstocksandbaance introicalforests. Oecologia,145(6): 87-99.   
ChaveJ,Rejou-MechaiM,urquezA,etal.14.Improvedallometricodels tostimatetheabovegroundiomassoftocal trees.Global Change Biology,20(10): 3177-3190.   
CostaTL,SampaioEVSB,SalesMF,etal.2Ol4.Rootandshootbiomassesinthetropicaldryforestofsemi-aridNortheast Brazil.Plant and Soil,378:113-123.   
DalmagroHJ,LoboFDA,VourlitisGL,etal.2O14.Tephysiologicalightresponseoftwotre speciesacrossahdrologic   
DuncansonL,RourkeO,DubayahR.2Ol5.Smallsample sizes yieldbiasedallometricequations intemperate forests.Scientific Reports,5: 17153,doi:10.1038/srep17153.   
Duncanson L,Huang W,Johson K,etal.2017.Implicationsof allmetric model selectionforcounty-levelbiomassmapping. Carbon Balance and Management, 12(18): 1-11.   
DuncansonL,Dubayah R.2O18.Monitoringindividual tree-based change withairborne lidar.EcologyandEvolution,8(10): 5079-5089.   
Fraga MP,BaretoPAB,dePaulaA.2O14.Volume estimationof Pterogyne nitens inpureplantationinthe southwestofBahia. Embrapa Forestry,34(79): 207-215.(in Brazilian)   
JenkinsJC,ChojnackyDC,HeathL S,etal.2003.National-scale biomassestimators for United States tree species.Forest Science,49(1): 12-35.   
Kachamba D J,Eid T.2016.Total tree,merchantable stem and branch volume models for miombo woodlands of Malawi. Southern Forests,78(1): 41-51.   
Leite $\mathrm { ~ F ~ S ~ L ~ }$ ,Resende A V.2010.Estimate of wood volume departing from the diameter at stump height in an exploited area in "terra firme"amazon forest. Ciencia Florestal,2O(1): 69-79.(in Brazilian)   
LevickSR,HessenmolerD,SchulzeE.2016.Scaling wood volume estimates from inventoryplots tolandscapes withairbore LiDAR in temperate deciduous forest. Carbon Balance and Management,11(7): 1-14.   
LimaPCF,OliveiraEB,Machado SA.1996EquationsforbiomassestimationofProsopis species in the braziliansemi-arid region. Boletim de Pesquisa Florestal,32(33): 67-79.(in Brazilian)   
Lima RB,AparicioPS,FerreiraRLC,etal.2O14.Volumetryandclasificationof productioncapacityfor Mora paraensis (Ducke) in Amapa estuary. Scientia Forestalis,42(101): 141-154.(in Brazilian)   
Lima RB,Alves JuniorFT,Oliveira CPD,etal.2O17.Predictingof biomassinBraziliantropicaldryforest:astatistical evaluation of generic equations. Anais da Academia Brasileira de Ciencias,89(3): 1815-1828.   
Liton CM,BooneKJ.o08.Alometric models for predictingabovegroundbiomas in twowidespread woodyplants inHawai. Biotropica,40(3): 313-320.   
Mcroberts RE,WestfallJA.2014.Effectsof uncertainty in modelpredictions of individual teevolumeonlargearea volume estimates.Forest Science,60(1): 34-42.   
MilesL,NewtonAC,DefriesRS,etal.2Oo6.A globaloverviewoftheconservationstatusof tropicaldryforests.Journalof Biogeography,33(3): 491-505.   
Ministryof theEnvironment.2Oo6.NationalForest ManagementPlan Contendas do Sincora.Volume I:General Information about the NationalForest.Brasilia:Brazilian InstituteofEnvironmentandRenewable Natural Resources,32.(in Brazilian)   
Moro MF,LughadhaEN,ArajoFS,etal.2O16.APytogeograpicalmetaanalysisofthesemiaridCatingadomainiBrazil. The Botanical Review, 82(2):91-148.   
MurphyPG,Lugo AE.1986.Ecologyof tropical dry forest.Annual Reviewof Ecology and Systematics,17(1):67-8.   
MurphyPG,LugoAE.1995.DryforestsofCentral Americaand theCaribbean.In: Bullock S,Mooney H,MedinaE.Seasonally Dry Tropical Forests.California: University Press,9-34.   
OliveiraLZ,KlitzkeAR,Fantini A,etal.2O18.Robustvoumetric models frsupporting themanagementofsecondaryforest standsintheSouthern BrazilianAtlanticForest.AnaisdaAcademia Brasileirade Ciencias,90(4):3729-3744.(inBrazilian)   
PenningtonRT,LewisGP,RaterJA.26.Anoverviewof theplantdiversity,biogeographyandconservationofNotropical Savannas and seasonallydryforests.In:PeningtonRT,Lewis GP,RatterJA.Neotropical Savannas and SeasonallyDry Forests: Plant Diversity, Biogeography,and Conservation. Boca Raton: CRC Press,1-29.   
Queiroz L P.2Oo9.Leguminous of Caatinga.Feira de Santana: UEFS,443.(in Brazilian)   
R Development Core Team.2O19.R:A Languageand Environment for Statistical Computing.Vienna:RFoundation for Statistical Computing.[2020-04-24].htp://www.R-project.or/.   
Robinson AP,Hamann JD.2011.Forest Analytics with R.New York: Springer,1-311.   
SampaioE,GassonPBaracatA,etal.2Ol.Treebiomassestimationinegeneratingareasoftroicaldryvegetationioast Brazil.Forest Ecology and Management,259(6): 1135-1140.   
Segura M,Kanen M.2Oo5.Allometricmodels for treevolumeand totalabovegroundbiomassiatropicalhumidforestin Costa Rica. Biotropica,37(1): 2-8.   
SilvaJM C,BatesJM.2O02.Biogeographic patternsand conservation in the South American Cerado:Atropical Savanna hotspot. BioScience,52(3): 225-234.   
Silva-RibeiroRB,GamaJRV,MeloLO.2Ol4.Sectionalanalysis forvolumedeterminationandselectionofvolumeequations for the Tapajos Nacional Forest. Cerne,2O(4): 6O5-612.(in Brazilian)   
SouzaPF,SilaJA,LucenaDS,etal.216.Dendrometricandptosociologicalstudiesinafragmentofcatinga,aoJosede Espinharas-PB.Ciencia Florestal,26(4):1317-1330.(in Brazilian)   
Sulivan MJP,LewisSL,Hubau W,etal.2Ol8.Fieldmethodsforsampling treeheightfortropicalforestbiomassestimation. Methods in Ecology and Evolution,9(5):1179-1189.   
Vanclay JK.1994.ModelingForest GrowthandYield:Applications to Mixed TropicalForests.Oxford: CAB International,1- 330.   
Vibrans AC,MoserP,OliveiraLZ,etal.20l5.Genericand specific stem volume models for three subtropical forest types in southern Brazil.Annals of Forest Science,72: 865-874.   
Watt MS,AdamsT,Gonzalez-AracilS,etal.2O13.The influenceofLiDARpulse densityand plotsizeon theaccracyof New Zealand plantation stand volume equations.New Zealand Journal of Forestry Science,43(15):1-10.   
Werneck FP.2011.Thediversificationof eastern South Americanopenvegetation biomes:historical biogeographyand perspectives.Quaternary Science Reviews,30(13-14):1630-1648.   
Zeng WS,Tang SZ.20l1Bias correction inlogarithmicregression and comparison with weighted regression for nonliear models.Nature Precedings,24(2):137-143.