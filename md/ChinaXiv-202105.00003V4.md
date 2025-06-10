# SEPRES: Sepsis prediction via a clinical data integration system and real-world studies in the intensive care unit

Qiyu Chen#, Ranran $\mathbf { L i } ^ { \# }$ , ChihChe Lin, Chiming Lai, Dechang Chen, Hongping Qu, Yaling Huang, Wenlian Lu\*, Yaoqing Tang\*,Lei Li\*

# Affiliations

Department of Applied Mathematics, Fudan University, Shanghai, China (Q Chen BSc,Prof W Lu PhD)   
Department of Critical Care Medicine,Ruijin Hospital, Shanghai Jiaotong University School of Medicine, Shanghai, China (R Li PhD,D Chen MD,PhD,H Qu MD, PhD, Y Tang MD, PhD,L Li MD, PhD)   
Shanghai Electric Group Co., Ltd. Central Academe, Shanghai, China (C Lin PhD, C Lai MA, Y Huang BEc)

# Correspondence to:

Dr Lei Li, Department of Critical Care Medicine,Ruijin Hospital, Shanghai Jiaotong University School of Medicine, Shanghai, 20o025, China, lileiys1023@yeah.net   
Dr Yaoqing Tang,Department of Critical Care Medicine,Ruijin Hospital, Shanghai Jiaotong University School of Medicine, Shanghai, 20o025, China, tangyaoqing $@$ 126.com   
Dr Wenlian Lu, Department of Applied Mathematics,Fudan University, Shanghai, 200433, China, wenlian@fudan.edu.cn

# Summary

Background: Sepsis is vital in critical care medicine,and early detection and intervention are key to survival.We aimed to establish an early warning system for sepsis based on a data integration system that can be implemented in the intensive care unit (ICU).

Methods: We trained the LightGBM and multilayer perceptron on the open-source database Medical Information Mart for Intensive Care for sepsis prediction. An ensemble sepsis prediction model was established based on the transfer learning and ensemble learning technique on the private dataset of Ruijin Hospital. The Shapley Additive Explanations analysis was applied to present feature importance on the prediction inference. With the development of data-integrating hub to collect and transmit data from different brands of ICU medical devices, the data integration system was established to receive, integrate, standardize,and store the realtime clinical data. In this way, the sepsis prediction model developed in the ICU of the Ruijin

Hospital for the real-world study of sepsis early warning on ICU management. The trial was registered with ClinicalTrials.gov (NCT05088850).

Findings: Our best early warning model achieved an area under the receiver operating characteristic curve (AUC) of O·9833 in the task of detecting sepsis in 4-h preceding on the open-source database,while our ensemble model achieved an AUC of $0 { \cdot } 9 0 6 5 { - } 0 { \cdot } 9 4 3 6$ in the retrospective research from 1-5-h preceding on the private database,and $0 { \cdot } 8 6 3 6 { - } 0 { \cdot } 8 9 9 2$ in real-time real-world studies using the data integration system in the ICU of the Ruijin Hospital. In the continuous early warning process of patients admitted to the ICU, 22 patients who met the diagnostic criteria for sepsis during hospitalization were predicted as positive cases; 29 patients without sepsis were predicted as negative cases. Additionally， 17 patients were predicted as false-positive cases; in six patients with sepsis during ICU stay, the predicted probabilities at different time nodes were all less than the warning threshold O·7 and predicted as false-negative cases.

Interpretation: Machine learning models could allow accurate and real-time inference to detect sepsis onset within 5-h preceding at most with the help of the data integration system. We identified the features such as age,antibiotics,ventilation,and net balance to be important for the sepsis prediction inference. We argue that this system has promising potential to improve ICU management by helping medical practitioners identify at-sepsis-risk patients and prepare for timely diagnosis and intervention.

Funding: Shanghai Municipal Science and Technology Major Project, the ZHANGJIANG LAB,and the Science and Technology Commission of Shanghai Municipality.

# Introduction

Sepsis，an infection-induced syndrome of physiological， pathological， and biochemical abnormalities,is a global healthcare issue that is associated with unacceptably high mortality and long-term morbidity among patients in an intensive care unit (ICU),1² and is responsible for a substantial cost burden on health care resources.³ Early detection and timely administration of appropriate antibiotics may be the most important factors to improve the prognosis of patients with sepsis.4 However, nonspecific symptoms of patients with sepsis lead to delayed diagnosis and delayed intervention.5

Machine learning has emerged as a promising tool for early detection of sepsis occurrence through intensive management based on electronic medical records, laboratory data,and biomedical signals.67 In 2016, Singer et al. proposed a new definition (Sepsis-3) of sepsis.2 According to this, many recent studies on sepsis prediction defined sepsis by Sequential Organ Failure Assessment (SOFA） and infection instead of Systemic Inflammatory Response Syndrome (SIRS).8-12 Prospective studies have shown that implementation of machine learningbased sepsis prediction algorithms in hospitals can reduce in-hospital mortality and length of stay.l3.14 In addition, many machine learning models provide superior model performance at the cost of transparency and interpretability, which has become a barrier to clinical application. Algorithms based on gradients,attention mechanism, and Shapley values are used to interpret the machine learning models.15-17

Most studies on sepsis detection used historical medical data, such as the Medical Information Mart for Intensive Care (MIMIC).18 However, the implementation of the detection model in the ICU for real-time prediction is complex. The raw data needed for model inference, such as bedside data, laboratory data, demographic data,and doctor's orders,usually come from different devices.Moreover, the information cannot interact directly due to differences in the data transfer protocols between devices.Efforts have been made to integrate bedside medical devices.19-21 However, these data integration systems integrate a more limited number of devices and data types to present the complete perspective of a doctor. Moreover, they were mainly focused on data collection and presentation and lacked further functionality, such as real-time alerts. Meanwhile，previous studies on the prediction of sepsis were mainly retrospective，and prospective studies used only relatively simple variables，deployment methods, and models.

In this study, we aim to develop a data integration system for IntelliVue Information Center, Ventilators，Philips ICCA system， Laboratory Information System (LIS)，and Hospital Information System (HIS),an ensemble machine learning model for the prediction of sepsis based on Sepsis-3 and establish a real-time early warning system for sepsis in the ICU, named SEpsis PREdiction System (SEPRES). In this way, we have developed the SEPRES in the ICU in the Ruijin Hospital and conducted real-world studies to analyze the performance of this system in the management of ICU patients.

# Methods

SEPRES includes a data integration system equipped with a sepsis early warning module. The data integration system can collect, store, process, and display medical data. These functions were completed through the data integration machine,physical server, and network server. The sepsis early warning module included a sepsis prediction model and an interpretative tool. The sepsis prediction model is an ensemble of multiple machine learning models and utilizes the transfer learning technique to predict sepsis. The interpretative tool provides information on how the model works by assigning importance to the input features. Our research was approved by the Ruijin Hospital Ethics Committee (No. 2020 [140]).

# Medical device integration hub

We developed a medical device integration hub that can acquire and transmit data from different brands of medical devices.The medical device integration hub consists of customized device connection lines,a hub,and an integrated data receiver. The identification module containing encoding is inserted into each medical device,enabling the hub to identify the type of online device and collect data automatically according to the communication protocol. The integrated data receiver receives and translates the raw data and uploads them to the integration server through the local area network.The medical device integration hub has the following functions:

Device online services: Detect device connections and start a data reading pro: corresponding to the device.   
Decoding: Parsing raw data into structured data for further processing.   
Storage: Storing parsed data in native memory.   
Remote Settings: support remote system setup and send system status.   
Uploading: Upload data received to the specified database.

Details of the data extraction can be found in Appendix I. The framework of a data-integrating system

![](images/876849b469efc034dcaf98daa7e1c42d7f8b30c3fcb502b93cbb9ce4a6266a84.jpg)  
Figure 1 System Deployment Framework.The web release system of the sepsis prediction system (SEPRES) applies browser/server architecture.

As shown in Figure 1, the system includes a physical server with the PostgreSQL database to store the sepsis warning data, and the webserver deploys the system's user access portal. The architecture can be divided into the following parts.

Device side: The medical device integration hub transmits the device and HIS data to the data integration system through the local area network.   
Data management side: Heterogeneous data are integrated into the data integration system. The interface data, service data, and model predictions are stored and managed by the Structured Query Language (SQL） server, while the parts needed for the sepsis early warning module are sent to the PostgreSQL database. The Message Queuing Telemetry Transport (MQTT） server sends real-time data from the data integration system to the browser.   
Data server side: The web server responds to the browser's request and calls the sepsis early warning module. Data preprocessing and model inference are then executed, and the predictions are stored in the PostgreSQL database. The data server side includes some related services (real-time calculation of the SOFA score, determination of suspected infection, data statistics,data charts, and historical data query).   
Application side: The user's request is passed to the webserver in this layer, and the processing results are displayed in the system. The Java Script program is used for dynamic HTML page development, and the AJAX interface is used for data interaction with the webserver. Spring MVC is used to build full-featured MVC modules for web applications, combined with NODEJS to provide an elegant and highly maintainable method for creating templates. Users can use the system anytime and anywhere with a browser in various ways, such as PCs and mobile terminals.

# System deployment

Figure 2 shows the medical device integration hub installed at Ruijin Hospital. The hub was placed at the bedside,receiving data from multiple devices via different interfaces shown at the bottom of the figure, storing the last $^ { 7 2 \mathrm { ~ h ~ } }$ of data in native memory, and transmittng data with a time delay of less than $1 0 \mathrm { ~ s ~ }$ 、Interfaces distributed on the two sides of the hub include two universal network interfaces, four USB interfaces for the mouse, keyboard,and U disk, two HDMI and one VGA for extended display, and eight or 16 USB and Ethernet multiplexing interfaces for medical devices.The hub can integrate data from the monitor, ventilator, infusion pump,and dialysis machine. The processed data are then transmitted to the data integration system.

![](images/78659f2586aaeb71d9e70152f637448cc36890de366e40f97535236641f4a4e2.jpg)  
Figure 2 Medical device integration hub

# Sepsis prediction model

Our goal was to develop a sepsis prediction model that can run in real-time in hospitals. To avoid insuficient data in the specific hospital for training,we first trained the models in the open-source database MIMIC and then retrained them in private hospital databases using transfer learning techniques to improve the performance. The final sepsis prediction model was obtained by integrating multiple transferred models using ensemble learning techniques.

# Data acquisition

Data sources and inclusion criteria. Our study used the MIMIC-II database (version 1·4)18 and the private Ruijin Hospital historical (RJ) database. MIMIC encompasses approximately 40,000 patients admitted to the ICU at Beth Israel Deaconess Medical Center in Boston from 2001 to 2012.Two tasks were established: inference on the MIMIC dataset by models trained on the MIMIC dataset and inference on the RJ dataset by models trained on the MIMIC and RJ datasets.The first task was to facilitate comparison with other articles,and the second was to apply the models clinically in Ruijin Hospital.

Patients who met allthe following criteria were included in the case group: 1) At least 14 years old.

2) Sepsis onset at least $5 \mathrm { h }$ after admission to the ICU.   
3) Sepsis onset is the first instance since admission to the hospital.   
Patients who met all the following criteria were included in the control group:   
1) At least 14 years old.   
2) Patients who stayed in the ICU for at least $5 \mathrm { h }$ and have not had sepsis at this time.   
3) Patients without ICD-9 codes for sepsis $( 7 8 5 { \cdot } 5 2 , 9 9 5 { \cdot } 9 1$ ,and $9 9 5 { \cdot } 9 2 \$ ）   
4) SOFA score changes of no more than 1 point in an arbitrary continuous $7 2 \mathrm { { h } }$ in the ICU stay. The third criterion was excluded from the RJ database because ICD-9 codes were not recorded. Sepsis-label definitions. Patients were followed throughout their stay in the ICU until discharge or development of sepsis according to the definition of the Third International Consensus for sepsis (Sepsis-3).² Specifically, if the timestamp of antibiotics $\left( t _ { a b x } \right)$ and blood cultures $( t _ { c u l t u r e } )$ meet the condition $t _ { a b x } - 2 4 h \leqslant t _ { c u l t u r e } \leqslant t _ { a b x } + 7 2 h$ ， the earlier timestamp of $t _ { a b x }$ and tculture is defined as the timestamp of suspected infection $( t _ { s u s } )$ . The SOFA score was evaluated per hour within the time window $[ t _ { s u s } - 4 8 \ h , t _ { s u s } + 2 4 \ h ]$ . The first hour with two or more points of increase in the SOFA score than the lowest prior score is defined as the onset of sepsis （204号 $( t _ { o n s e t } )$ ：

Feature extraction. We extracted 78 and 63 patient variables from the MIMIC and RJ databases, respectively. After data cleaning， we extracted these variables as features,i.e., maximum, average, median, and minimum, at hourly intervals,and the missing data were padded by the nearest value before or a preset default value. After filtering, we obtained the MIMIC dataset with 1057 positive and 5834 negative episodes and the RJ dataset with 115 positive and 239 negative episodes. We used a 5-h time window from the episodes to predict sepsis. These two datasets were divided into training, validation,and test sets. See Appendix II for further details.

# Predictionmodel

Machine learning model. Multiple models were tested on the MIMIC dataset, including support vector machine (SVM), multilayer perceptron (MLP), gradient boosting machine (GBM), and long short-term memory (LSTM). For GBM，we used XGBoost2² and LightGBM²³ as implementations.A detailed introduction to these models can be found in Appendix V.

Training method. Some redundant features were removed to accelerate SVM and MLP training in the tasks.Data were standardized (i.e., each feature's value range was linearly scaled between O and 1） before training to eliminate magnitude differences between features. The hyperparameters and structures of each model were tuned according to the effects on the validation set. See Appendix VI for further details.

Transfer learning and ensemble learning. To ensure sufcient patient cases, we first trained LightGBM and MLP models in MIMIC and later transferred them to the RJ dataset in Task 2. These models were selected based on the performance of Task 1 and were used as representatives of traditional machine learning models and neural network models. They needed to be retrained from Task 1 because some variables were not available in the RJ database. Due to the population differences between the MIMIC and RJ databases, the data were standardized separately as in Task 1. Additionally, similar features (the maximum, average, median,and minimum values of variables with low recording frequency at the same hour) are reduced to one feature to reduce the dimension and help the transfer. The parameters of each model were shared as initial parameters and tuned again during training on RJ database.

Finally, we integrated the MLP and LightGBM models by taking the average to make the results more robust and accurate.This result was used as the final output of the sepsis prediction model.

# Role of the funding source

The funders of the study had no role in the study design, data collection,data analysis,data interpretation, or writing of the report.

# Results

# Sepsis prediction model

We evaluated our models based on accuracy, the area under the receiver operating characteristic curve (AUC), sensitivity, and specificity of the test set.

# Performance on the MIMIC-III dataset

In Task 1,the AUCs of XGBoost and LightGBM were the highest among these sepsis prediction models, followed by MLP and LSTM,and SVM performed the worst. Appendix VI shows the full performance of the five models.Although the GBM structure is relatively simple, it outperforms artificial neural network models.We compared our models with other models trained on the same open-source database,MIMIC,using the Sepsis-3 criteria, and reported prediction results within $^ { 5 \mathrm { h } }$ before the onset of sepsis, including InSight, AISE,’MGP-TCN, DTW-KNN,1° MLA,1 DSPA,1² and MGP-AttTCN.16 Table 1 shows that our models basically outperform the others.However, it should be highlighted that although these models all use the MIMIC-II database, there were still differences in the training and test sets due to diferences in the details of case extraction and sepsis criteria; therefore,the comparison is not as standard as most machine learning comparison works based on benchmark data.

Table1The resultsof different modelson the MIMIC-IIdataset   

<html><body><table><tr><td></td><td>Preceding hours</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>InSight8</td><td>4</td><td>0.57</td><td>0-74</td><td>0·80</td><td>0.54</td></tr><tr><td>AISE9</td><td>4</td><td>0·64</td><td>0.84</td><td>0-85</td><td>0·64</td></tr><tr><td>MGP-TCN10</td><td>4</td><td></td><td>about 0-85</td><td></td><td>-</td></tr><tr><td>DTW-KNN10</td><td>4</td><td>-</td><td>about 0-88</td><td>-</td><td></td></tr><tr><td>MLA11</td><td>0</td><td></td><td>0-88</td><td>0.80</td><td>0·78</td></tr><tr><td>MLA1</td><td>24</td><td></td><td>0-84</td><td>0.80</td><td>0·72</td></tr><tr><td>DSPA12</td><td>4</td><td></td><td>0.982</td><td></td><td></td></tr><tr><td>MGP-AttTCNl6</td><td>4</td><td></td><td>0-746</td><td>-</td><td>-</td></tr><tr><td>LightGBM</td><td>4</td><td>0·9075</td><td>0·9833</td><td>0·8491</td><td>0·9660</td></tr><tr><td>MLP</td><td>4</td><td>0·8462</td><td>0·9564</td><td>0·7292</td><td>0·9632</td></tr></table></body></html>

# Performance on the RJ dataset

In Task 2,after transfer learning and ensemble learning, the final performance of the sepsis prediction model is shown in Table 2.The overall performance was similar to that ofLightGBM or MLP transferred models,and the average value of AUC was slightly higher than that of LightGBM or MLP. Detailed results of transfer learning can be found in Appendix VIII.

Table2 Theresults of ensemble model in Task 2   

<html><body><table><tr><td>Preceding hours</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>1</td><td>0.8250</td><td>0.9231</td><td>0.6667</td><td>0.9833</td></tr></table></body></html>

<html><body><table><tr><td>2</td><td>0·7944</td><td>0·9200</td><td>0·6000</td><td>0-9889</td></tr><tr><td>3</td><td>0-8417</td><td>0·9242</td><td>0-7083</td><td>0·9750</td></tr><tr><td>4</td><td>0·8467</td><td>0-9436</td><td>0·6933</td><td>1-0000</td></tr><tr><td>5</td><td>0-8639</td><td>0·9065</td><td>0.7389</td><td>0-9889</td></tr></table></body></html>

# Feature interpretability

We used Shapley additive explanation $( { \mathrm { S H A P } } ) ^ { 2 4 }$ analysis to explore the importance of the features.For LightGBM models in SEPRES,antibiotics, respiratory rate, total positive endexpiratory pressure level, fibrinogen level, temperature, net balance,and age were important in most models. For MLP models,age,respiratory rate, ventilation, heart rate, antibiotics, and temperature were important in most models. Some of these features (antibiotics,respiratory rate, temperature, ventilation,and heart rate) were related to the definition of Sepsis-3 or SIRS, while there is also literature arguing for an association between some of these features (respiratoryrate,25fibrinogen,6netbalance,2andage28)andtheseverityormortalityfesis Detailed results are provided in Appendix IX.

# SEPRES

# Model inference in SEPRES

The detailed steps of model inference are as follows:

1) Obtain real-time features of patients using SQL query statements.   
2) The features were standardized by calling the scaler obtained in the training set.   
3) Call the trained model to get the prediction results.   
4) Call the interpretive tool to get the importance of the features based on the prediction   
results.   
5) Output and store prediction results and interpretations in a standard format.

# System operation

SEPRES provides predictions and explanations for every patient in the ICU every hour, including the risk of sepsis onset in the next $^ { 5 \mathrm { ~ h ~ } }$ ，the influence of features on the predictions calculated by SHAP,and SOFA predictions. It has been operating at Ruijin Hospital for several months, providing hourly early warning services for over 1O0 patients in the ICU. The PC terminal of the user interface is a layout in the ICU common room.Figure 3 presents an example of the display board for all patients in the ICU,including predictions of sepsis onset and SOFA changes, where high and low risks are shown by red and blue bars, respectively. Figure 4 shows the data details for a specific patient to observe the current and past status of the patient.

![](images/1b036791ec042744cb8cc5e95ae309ba93dc46784ae190271362e7904460a898.jpg)  
Figure 3 The user interface example.Each subplot shows the change in SOFA score and sepsisonset prediction for a patient.It is subtitled with patient information,and the upper right corner shows the maximum and minimum Sequential Organ Failure Assessment scores and sepsisonset predictions within $2 4 \mathrm { h }$

![](images/0f55b18dfbd53b1b25e065f3c831618e0cb00419ba8c00a68d14bc3401c28579.jpg)  
Figure 4 Historical data review for individual patients.The title is patient information, below the title are filter criteria, on the left side are optional data types,and the rest is the table and chart for the selected data.

# Real-time performance of the sepsis prediction model in the ICU of the Ruijin Hospital

We extracted a total of 67 ICU stays from February 2021 to June 2021 from the system. Each stay was labeled by the change in SOFA score and the doctor's examination for infection (based on antibiotics or blood culture),and 40 of these stays were labeled as having at least one sepsis onset at a threshold of O·5. Data from the control group and near onset of sepsis in the case group were included in the analysis. The statistical results of the predictions are presented in Table 3.

Table3Theresultsofreal-timedata

<html><body><table><tr><td>Preceding hours</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>1</td><td>0·8243</td><td>0·8636</td><td>0-8281</td><td>0-8150</td></tr><tr><td>2</td><td>0-8448</td><td>0-8789</td><td>0·8682</td><td>0·7843</td></tr><tr><td>3</td><td>0·8483</td><td>0-8992</td><td>0·8626</td><td>0·8106</td></tr><tr><td>4</td><td>0-8533</td><td>0.8952</td><td>0-8802</td><td>0·7803</td></tr><tr><td>5</td><td>0.8583</td><td>0.8858</td><td>0-8951</td><td>0-7566</td></tr></table></body></html>

# Casestudies

We discussed several of these cases, including true-positive, true-negative, false-positive, and false-negative cases.Figure 5 ilustrates the model predictions for positive cases near the onset of sepsis or negative cases over a random period (see Appendix X for more details).

![](images/f35938d64ca024010afeacf56a118b9edad66d57fd6c99c185d1c249bb953125.jpg)

Figure 5 some illustrative examples of the prediction.Each subplot describes the confidence index (CI) for multiple models (Y-axis) at the target time (X-axis). (i) The condition of the patient aggravated in the early morning ofFebruary 15,2021, with multiple organ dysfunction,and the patient was diagnosed with sepsis at 12:00 AM. Our model prediction exceeded the warning threshold of O·7 for the prediction at $9 { : } 0 0 \mathrm { A M }$ . (ii) Despite the high Sequential Organ Failure Assessment (SOFA） score $( 7 \cdot 0 )$ ，there was no evidence of $\Delta \mathrm { S O F A } \ \geqslant 2$ within $^ { 7 2 \mathrm { ~ h ~ } }$ Consistently, the predictions were allower than the threshold. (ii) Although the patient's SOFA score was stable at $6 { \cdot } 0$ , our model made incorrect predictions. (iv) The SOFA score showed an increase from $6 { \cdot } 0$ to $9 { \cdot } 0$ at 06:00 PM on May 9,2021.In combination with evidence of infection, the patient was diagnosed with sepsis. However, the prediction was below the warning threshold.

Our model can detect sepsis early in most cases, although there are a small number of falsenegative and false-positive cases.We propose that the possible reason for false-negatives is that our models tend to give lower predictions when the collected data are limited. The early prediction of sepsis occurrence by our model effectively guided medical practitioners to pay more attention appropriately to this patient, leading to early diagnosis of sepsis and more efficient management of ICU patients.

# Discussion

Machine learning methods have been considered a promising method for early warning of sepsis in the ICU.6-17 Early diagnosis and timely management of septic patients can efectively improve prognosis.29 However, sepsis may not be diagnosed in time in the clinic due to the doctor's shift and day-night shift of the medical staff. Therefore,an accurate and efcient early prediction system for sepsis at the bedside is important.

In this study, we established an ICU bedside sepsis early warning system, SEPRES,to conduct real-time sepsis prediction for patients in the ICU through a data integration system. In contrast to most studies on machine-learning sepsis prediction in the open-source database, SEPRES has been developed and conducted real-time inference and analysis in the ICU of the Ruijin Hospital by the integration of IntelliVue Information Center, Ventilators,Philips ICCA system, LIS,and HIS data.Additionally, the system can display the patient’s historical data in the user interface to help doctors intuitively obtain changes in the patient's condition. Although SEPRES could not provide a definitive basis for our therapeutic regime,the probability of sepsis occurrence allows us to pay more attention to specific patients. Furthermore, weight analysis of medical factors can provide insights into the use of therapeutic regimens.

To avoid the influence of the insuficiency of data size and inhomogeneity distribution of the data in different medical centers on training and inferring machine learning models,we deployed the transfer learning technique to improve the performance of the specific medical center. In particular, MIMIC-III mainly enrolled white patients (40996 of 58976 hospital admissions), in contrast to the private dataset of the Ruijin Hospital that is mainly composed of the Chinese population, which has a significant difference in certain features of the sepsis prediction model (See Appendix XI). In this way, the transfer learning process improved the prediction AUC ofLightGBM models from $0 { \cdot } 8 6 1 3 { - } 0 { \cdot } 8 9 1 3$ to 0:8964-0·9348 on the historical data of the Ruijin Hospital.

The interpretive tool may help medical practitioners identify risk factors.In the SHAP analysis of the models loaded in SEPRES,we paid special attention to the insights brought about by the importance of net balance. As shown in Supplementary Figure 2,a positive net balance indicates a higher risk of sepsis. Because the net balance is nursing data that are difficult to collect, in the MIMIC dataset, 4079 out of 6891 episodes have no balance data for colloid and crystalloid solutions, while in the RJ dataset, only 25 out of 329 episodes had no net balance data.Therefore, net balance has not been considered a feature for most machine learning models or has been analyzed as an important factor for sepsis prediction inference based on MIMIC datasets. Our SHAP analysis showed that a negative net balance tended to decrease the predicted probability of sepsis. Indeed, positive cumulative fluid balance has been reported to be an independent predictor of ICU mortality.27 Furthermore,Lin et al. have shown that patients with an early positive fluid balance have an increased risk of developing venous thromboembolism.30 The weight of net balance, as shown in our SHAP analysis, further emphasized the importance of careful fluid management in critically ill patients. Therefore, we argue that including the net balance in the prediction model may improve not only the performance but also the clinical management in the ICU.

Our model has certain limitations. First, we enrolled only patients who were non-septic during the entire period in the ICU as negative controls.The enrollment condition may be too pure to be used to establish a model to predict the onset period of sepsis, which may cause false-positive cases.Second, as we observed in consecutive case studies, patients diagnosed with sepsis shortly after being transferred to the ICU were difficult to predict by the model. That is,a short period of data recording may cause false-negative cases. Finally, our model incorporates variables,such as antibiotics and mechanical ventilation, resulting in the predictions of the model being influenced by the subjective behavior of the doctor. These limitations will be addressed in future work through diverse methods, including finegrained labeling, inclusion of data collection from the ICU,and data augmentation. Moreover, this workflow applies to disease warnings other than sepsis in the ICU, such as disseminated intravascular coagulation and acute kidney injury, with the help of the data integration system to collect the necessary features and data for model construction.

# Contributors

WL, YT,LL, QC,RL, and Lin C conceived and designed the study. YT,LL, QC,RL, DC, HQ, and YH acquired the data. WL,Lin C, and Lai C implemented quality control of data and algorithms. WL, QC,RL,and Lai C had fullaccess to and verified all data in the study. QC developed, trained, and applied machine-learning models. Lai C developed a data integration system. YT, LL, RL,DC,and HQ performed the consecutive case studies.QC and RL prepared the first draft of the manuscript. WL,LL，and YT revised the manuscript. All authors contributed to the preparation of the manuscript.

# Declaration of Interest

We report no competing interests.

# Data Sharing

The MIMIC-III database can be accessed at https://physionet.org/content/mimicii/1.4/ after becoming a member of Physionet (https:/physionet.org/). The RJ database used in this study is not publicly available.The code used to develop the model in this manuscript is available from the corresponding author upon reasonable request.

# Acknowledgments

The authors acknowledge Shanghai Electric Group Co.,Ltd. Central Academe for their support during the development of the data integration system.

# Ethics Committee Approval

Our study was approved by the Ruijin Hospital Ethics Commitee [ethics committee reference number: (2020) Linlunshen No. (140)].

# References

87.   
2 Singer M, Deutschman CS, Seymour CW,et al. The third international consensus definitions for sepsis and septic shock (Sepsis-3). Jama 2016; 315: 801-10.   
3 Angus DC，Linde-Zwirble WT,Lidicker J，Clermont G， Carcillo J， Pinsky MR. Epidemiology of severe sepsis in the United States: Analysis of incidence, outcome, and associated costs of care. Crit Care Med 2001; 29: 1303-10.   
4 Marik PE,Farkas JD. The changing paradigm of sepsis: early diagnosis, early antibiotics, early pressors, and early adjuvant treatment. Crit Care Med 2018; 46: 1690-2.   
5 Filbin MR, Lynch J, Gillingham TD, et al. Presenting symptoms independently predict mortality in septic shock: Importance of a previously unmeasured confounder. Crit Care Med 2018; 46: 1592-9.   
6 Henry KE, Hager DN, Pronovost PJ, Saria S.A targeted real-time early warning score (TREWScore) for septic shock. Sci Transl Med 2015; 7: 299ra122-299ra122.   
/ Lauritsen SM, Kalor ME, Kongsgaard EL, et al. Early detection of sepsis utilizing deep learning on electronic health record event sequences. Artif Intell Med 2020; 104: 101820.   
8 Desautels T, Calvert J,Hoffman J, et al. Prediction of sepsis in the intensive care unit with minimal electronic health record data: A machine learning approach. JMIR Med Inform 2016; 4: e5909.   
9 Nemati S,Holder A, Razmi F, Stanley MD, Clifford GD, Buchman TG.An interpretable machine learning model for accurate prediction of sepsis in the ICU. Crit Care Med 2018; 46: 547.   
10Moor M, Horn M, Rieck B, Roqueiro D, Borgwardt K. Early recognition of sepsis with Gaussian process temporal convolutional networks and dynamic time warping. Machine Learning for Healthcare Conference; 2019: PMLR.   
11Barton C, Chetipally U, Zhou Y, et al. Evaluation of a machine learning algorithm for up to 48-hour advance prediction of sepsis using six vital signs. Comput Biol Med 2019; 109: 79-84.   
12Asuroglu T, Ogul H. A deep learning approach for sepsis monitoring via severity score estimation. Comput Methods Programs Biomed 2021; 198: 105816.   
13McCoy A, Das R. Reducing patient mortality, length of stay and readmissions through machine learning-based sepsis prediction in the emergency department, intensive care unit and hospital floor units. BMJ Open Qual 2017; 6: e000158.   
14Shimabukuro DW, Barton CW,Feldman MD, Mataraso SJ, Das R. Effect of a machine learning-based severe sepsis prediction algorithm on patient survival and hospital length of stay: A randomised clinical trial. BMJ Open Respir Res 2017; 4: e000234.   
15Zhang D, Yin C,Hunold KM, Jiang X, Caterino JM, Zhang P.An interpretable deeplearning model for early prediction of sepsis in the emergency department. Patterns (N Y) 2021; 2: 100196.   
16Rosnati M, Fortuin V. MGP-AttTCN: An interpretable machine learning model for the prediction of sepsis. PLoS One 2021; 16: e0251248.   
17Oei SP, van Sloun RJ, van der Ven M, Korsten HH,Mischi M. Towards early sepsis detection from measurements at the general ward through deep learning. Intell Based Med 2021; 5: 100042.   
18Johnson AE,Pollard TJ, Shen L,et al. MIMIC-II,a freely accessible critical care database. Sci Data 2016; 3: 1-9.   
19 Sorani MD,Hemphill JC,Morabito D, Rosenthal G,Manley GT. New approaches to physiological informatics in neurocritical care. Neurocrit Care 2O07; 7: 45-52.   
20 Goldstein B,McNames J, McDonald BA, et al. Physiologic data acquisition system and database for the study of disease dynamics in the intensive care unit. Crit Care Med 2003; 31: 433-41.   
21Sun Y, Guo F, Kaffashi F, Jacono FJ, DeGeorgia M, Loparo KA. INSMA: An integrated system for multimodal data acquisition and analysis in the intensive care unit.J Biomed Inform 2020; 106:103434.   
22 Chen T, Guestrin C. Xgboost: A scalable tree boosting system. Proceedings of the 22nd acm sigkdd international conference on knowledge discovery and data mining; 2O16: 785- 94.   
23Ke G, Meng Q, Finley T, et al. Lightgbm: A highly efficient gradient boosting decision tree. Advances in neural information processing systems 2017; 30: 3146-54.   
24Lundberg S,Lee SI.A Unified approach to interpreting model predictions. Proceedings of the 31st international conference on neural information processing systems 2O17: 4768- 77.   
25Kenzaka T, Okayama M, Kuroki S,et al. Importance of vital signs to the early diagnosis and severity of sepsis: Association between vital signs and sequential organ failure assessment score in patients with sepsis. Intern Med 2012; 51: 871-6.   
26Matsubara T, Yamakawa K, Umemura Y, et al. Significance of plasma fibrinogen level and antithrombin activity in sepsis: A multicenter cohort study using a cubic spline model. Thromb Res 2019; 181: 17-23.   
27Brotfain E, Koyfman L, Toledano R, et al. Positive fluid balance as a major predictor of clinical outcome of patients with sepsis/septic shock after ICU discharge. Am J Emerg Med 2016; 34: 2122-6.   
28Martin GS, Mannino DM, Moss M. The effect of age on the development and outcome of adult sepsis. Crit Care Med 2006; 34: 15-21.   
29 Burdick H, Pino E, Gabel-Comeau D,et al. Effect of a sepsis prediction algorithm on patient mortality， length of stay and readmission: A prospective multicentre clinical outcomes evaluation of real-world patient data from US hospitals. BMJ Health Care Inform 2020; 27: e100109.   
30Lin T-L,Dhillon NK, Conde G,et al. Early positive fluid balance is predictive for venous thromboembolism in critically ill surgical patients. Am J Surg 2021; 222: 220-6.

# Research in context

# Evidence before this study

We searched PubMed from inception to September 30, 2021,using the keywords“machine learning” or“deep learning” or“artificial intelligence” and “sepsis,” and using the keywords "critical care”or“ICU” or“sepsis”and“data integration system”or “data acquisition system" or “integrated,” without language restrictions. Previous studies built various prediction models based on different sepsis definitions and datasets or built data acquisition systems to integrate some types of data. However, most of them did not combine the two together to get a real-time prediction and describe the whole process in detail.

# Added value of this study

We developed an entire sepsis prediction system in the ICU, including a set of procedures that can be applied in practice. The machine learning models achieved high AUC scores in the two databases,and we interpreted the predictions. In addition,we examined our system through consecutive case studies. Moreover, this workflow is also applicable to other disease warnings, not only for sepsis.

# Implications ofall the available evidence

Our system can be applied to display patients’conditions in real-time, identify patients more likely to suffer from sepsis,help medical practitioners focus on them,and help with future research.

# supplementarymaterial

# Contents

Appendix I Details of data extraction.   
Appendix II Details of feature extraction .   
Appendix III Complete list of variables used in Task 1.   
Appendix IV Complete list of variablesused in Task 2   
Appendix V Machine-learning models..   
Appendix VI Training method.   
Appendix VII Results of sepsis prediction models in Task 1. 5 Appendix VIII Results of transferred models in Task 2 6 Appendix IX Feature importance.   
Appendix X Case studies . 9 Appendix XI Differences in features between MIMIC dataset and RJ dataset. 15

Reference. 16

# Appendix I Details of data extraction

# Serial Port

Most medical devices communicate through the network or the serial port, including RS-232 and miniDIN.The serial port uses binary signals,so the data rate in bits per second is equal to the symbol rate in baud,and commonly supported bit rates include from 2400 to 115200 bits per second.

# The HL7interface

The device data are transmitted to the data integration system through the HL7 interface,an electronic data interchange standard for the provision of inpatient care based on the IP protocol. Using TCP/IP connections,client systems can obtain data from the interface using both active sends and queries.HL7 v2.3.1 is generally used.

Supplementary Table1 The types of data collected from the devices and systems   

<html><body><table><tr><td>Source device/system</td><td>Data type</td><td>Output medium</td><td>Format</td></tr><tr><td>IntelliVue Information Center</td><td>Vital signs</td><td>Network</td><td>HL7</td></tr><tr><td>PB 840 Ventilator</td><td></td><td></td><td></td></tr><tr><td>Maquet Servo-i Ventilator</td><td></td><td></td><td>According to the device</td></tr><tr><td>Maquet Servo-s Ventilator</td><td>Ventilator data Pharmacy data,GCS,and</td><td>RS-232</td><td>output format</td></tr><tr><td>Philips ICCA</td><td>urine output</td><td>Network</td><td>WebServices</td></tr><tr><td>Laboratory Information System</td><td>Laboratory data</td><td>Network</td><td>WebServices</td></tr><tr><td>Hospital Information System</td><td>Admission, discharge,and hospitalization data</td><td>Network</td><td>WebServices</td></tr></table></body></html>

# Appendix I Details of feature extraction

Seventy-eight patient variables from MIMIC were chosen as raw data for the dataset. Appendix III contains a complete list of these variables.We excluded significantly incorrect records by setting the range of variables according to the specialists.When integrating the same variables from different sources, we set priorities to extract values with the highest confidence.After data cleaning, these data were summarized per hour into the maximum, average, median, and minimum, except for some changeless or durative variables, which in total were 285 features. Padding was used if there was no value at the corresponding time. Padding values were taken as the nearest value before, or the average of all patients when no value was valid since the patient’s admission.Episodes with too few valid variables were removed to ensure data quality. We used a five-hour-long time window from the episodes to predict sepsis; thus, each sample point in these tasks had 1425 features.Finally, we obtained a dataset with 1057 positive and 5834 negative episodes. We divided the dataset into training, validation,and test sets. Negative episodes were divided at a ratio of 7:1:2.For positive episodes,we chose the same number as the negative episodes in the validation and test sets.The remaining positive episodes were included in the training set. Oversampling of positive sample points or down-sampling of negative sample points was used to ensure that the proportion was 1:1 in each set.

Similar preparation steps were used in the RJ database as well, although only sixty-three variables were available. Appendix IV contains a complete list of these variables. These variables were summarized hourly into 226 features.After padding and filtering, we obtained the RJ dataset with 115 positive and 239 negative episodes. We divided them into a training set with 76 positive and 2O0 negative episodes,a validation set with nine positive and nine negative episodes, and a test set with 30 positive and 30 negative episodes.

# AppendixIII Complete listofvariablesused in Task1

We consulted literature on predicting sepsis or SOFA scores and the variables mentioned in the literature and could be extracted from MIMIC-III were selected, for a total of 78 variables.1-4

The 78 variables are MAP, heart rate, $\mathrm { O } _ { 2 } \mathrm { s a t }$ ,SBP, DBP, respiratory rate, temperature, GCS, $\mathrm { P a O } _ { 2 }$ $\mathrm { F i O } _ { 2 }$ $\mathrm { S p O } _ { 2 }$ ,cardiac output, stroke volume, stroke volume variation, tidal volume, peak inspiratory pressure, total PEEP level, $\mathrm { O } _ { 2 }$ flow rate, WBC, hemoglobin, hematocrit, creatinine,bilirubin, bilirubin direct, platelets, INR,PTT,AST,lactate, glucose, potassium, calcium,BUN,phosphorus, magnesium,chloride, BNP, troponin I, fibrinogen, CRP, sedimentation rate,ammonia, PH, $\mathrm { P C O } _ { 2 }$ ,bicarbonate, base excess, $\mathrm { S a O } _ { 2 }$ , anion gap,albumin, bands,PT, sodium, ferritin, transferrin, creatine kinase, creatine kinase-MB, LDH, troponin T, RDW, ALP,MCHC, uric acid, monocytes,lymphocytes,MCH, $\mathbf { A a D O } _ { 2 }$ ,RBC,MCV, neutrophils,weight, urine output in the past 24 hours, net balance,ventilation, number of antibiotics in the past 12, 24,and 48 hours, SOFA,and age.

# AppendixIV Complete list of variables used in Task 2

Based on Appendix I, we removed some variables that were not recorded in the Ruijin Hospital historical database and removed some infrequently used variables based on doctors' opinions.We also added four variables that were involved in the SOFA score.   
Nineteen variables were removed: GCS, $\mathrm { O } _ { 2 } \mathrm { s a t }$ , Cardiac Output, Stroke Volume, Stroke Volume Variation, Calcium, BNP, CRP, Sedimentation Rate,Ammonia,Anion Gap, Bands,Ferritin, Transferrin, Troponin T, RDW,MCHC,MCH,MCV.   
Four variables were added: rate of norepinephrine, epinephrine, dopamine,and dobutamine.   
Finally, 63 variables were collected.

# Appendix V Machine-learning models

# 1. Support Vector Machine (SVM)

The rationale of Support Vector Machine (SVM) is to find such a hyperplane $y = \pmb { w } \cdot \pmb { x } + b$ to separate data that the distance between positive data on one side and the hyperplane and the distance between negative data on the other side and the hyperplane is maximized:

$$
\begin{array} { c } { { \displaystyle \operatorname* { m a x } _ { w , b } \gamma } } \\ { { s . t . \quad y ^ { n } \left( \displaystyle \frac { w } { \left\| w \right\| } \cdot \mathbf { x } ^ { n } + \displaystyle \frac { b } { \left\| w \right\| } \right) \geq \gamma , \forall n = 1 , 2 , \cdots , N } } \end{array}
$$

Where the dataset is $\left\{ \left( \mathbf { x } ^ { n } , { y } ^ { n } \right) \right\} _ { n = 1 } ^ { N }$ ,and $y ^ { n }$ is the label of $ { \mathbf { x } } ^ { n }$

Furthermore, kernel tricks can be introduced to improve the nonlinearity of the model.Data are mapped into a feature space using a nonlinear mapping with the help of kernel function, including polynomial kernel function, linear kernel, or mixed kernel function.

# 2. Multi-Layer Perceptron (MLP)

Multi-Layer Perceptron (MLP) is a classical and useful neural network model. It contains an input layer, several hidden layers,and an output layer.

Let $I n$ denote the input layer, and $F c _ { 1 } , F c _ { 2 } , . . . , F c _ { L }$ denote hidden layers and the output layer successively, where $\displaystyle F c _ { \scriptscriptstyle L }$ is the output layer. Each hidden layer and output layer learn a nonlinear map $\mathbf { h } _ { i } = \sigma \big ( \mathbf { W } _ { i } \mathbf { h } _ { i - 1 } + \mathbf { b } _ { i } \big )$ , where $\mathbf { h } _ { i }$ is the representation ofan example at layer $F { { c } _ { i } }$ ， $\mathbf { W } _ { i }$ and $\mathbf { b } _ { i }$ are the weight and bias parameters of layer $\mathrm { F c } _ { i }$ ,and $\sigma$ is the activation function, taken as Rectifier Linear Units (ReLu)σ(x)= max(0,x) for the hidden layers and Softmax Units $\sigma \big ( \mathbf { x } \big ) _ { i } = e x p ( \mathbf { x } _ { i } ) / \sum _ { j } e x p ( \mathbf { x } _ { j } )$ for the output layer. The loss function like

$$
\begin{array} { l } { { \displaystyle { \cal L } ( f \Big ( { \bf x } ^ { n } \Big ) , y ^ { n } ) } \ ~ } \\ { { \displaystyle = - \frac { 1 } { N } \sum _ { n = 1 } ^ { N } \biggl [ y ^ { n } \log \Bigl ( f \Big ( { \bf x } ^ { n } \Bigr ) \Bigr ) - \Big ( 1 - y ^ { n } \Big ) \log \Bigl ( 1 - f \Big ( { \bf x } ^ { n } \Bigr ) \Bigr ) \biggr ] + \lambda \sum _ { i = 1 } ^ { L } \bigl \| { \bf W } _ { i } \bigr \| _ { F } } } \end{array}
$$

and Stochastic Gradient Descent algorithms are always used to train the networks, where $f { \Big ( } \mathbf { x } ^ { n } { \Big ) }$ is the network output of $ { \mathbf { x } } ^ { n }$ ，and $\Vert \cdot \Vert _ { F }$ is the Frobenius norm. The first term in the formula is the crossentropy loss and the second is a weight decay term in order to prevent over-fittng where $\lambda$ is the weight decay coefficient.

# 3. Gradient Boosting Decision Tree

Gradient boosting decision tree (GBDT) is a widely-used machine learning algorithm and there are many effective implementations such as XGBoost and LightGBM which have been used in our experiments. XGBoost makes use of second-order information of loss function instead of first-order information in the case of GBDT,which makes convergence faster and beter. Moreover， XGBoost uses several algorithms and technologies to accelerate the training procedure. Compared with XGBoost, LightGBM can accelerate the training further, benefiting from the histogram-based algorithm, gradient-based oneside sampling, and exclusive feature bundling.

# 4.Long Short-Term Memory (LSTM)

Considering the time-sequential datasets, recurrent neural networks (RNN),specifically long short-term memory(LSTM) networks, which is the most successul RNN, had been used in our experiments.LSTM networks have memory blocks consisting of memory cels and gates in the recurrent hidden layer. The gates control which information to forget and which to remember. Through these,LSTM networks are able to store information selectively and capture the long-time-dependent behavior compared with MLP or GBDT.A single repeating structure of the LSTM can be represented as the following:

$$
\begin{array} { r l } & { f _ { t } = \sigma \Bigl ( W _ { f } \cdot \bigl [ h _ { t - 1 } , x _ { t } \bigr ] + b _ { f } \Bigr ) } \\ & { i _ { t } = \sigma \Bigl ( W _ { i } \cdot \bigl [ h _ { t - 1 } , x _ { t } \bigr ] + b _ { i } \Bigr ) } \\ & { \tilde { C } _ { t } = \operatorname { t a n h } \bigl ( W _ { C } \cdot \bigl [ h _ { t - 1 } , x _ { t } \bigr ] + b _ { C } \bigr ) } \\ & { C _ { t } = f _ { t } * C _ { t - 1 } + i _ { t } * \tilde { C } _ { t } } \\ & { o _ { t } = \sigma \bigl ( W _ { o } \cdot \bigl [ h _ { t - 1 } , x _ { t } \bigr ] + b _ { o } \bigr ) } \\ & { h _ { t } = o _ { t } * \operatorname { t a n h } \bigl ( C _ { t } \bigr ) } \end{array}
$$

Where $f _ { t } , i _ { t } , C _ { t } , o _ { t } , h _ { t }$ represent the forget gate, input gate, cellstate, output gate, hidden state, and the symbol $\ast$ refers to element-wise multiplication.

# Appendix VI Training method

In Task 1,some redundant features were removed to accelerate the training of the SVM and MLP.For SVM, all average features and features whose coefficient of variation was $> 2$ were used; for MLP, only one of the maximum, average, median, and minimum of each laboratory variable was kept, considering the low record frequency. Data were standardized (i.e., each feature's value range was linearly scaled between O and 1） before training to eliminate magnitude differences among features and reduce distribution differences between the two datasets in the next task.

We chose the linear kernel function and 1 as the penalty factor in the SVM.For MLP,46O features were selected as the input. We finally used a six-layer architecture, which is shown in Supplementary Table 2. We chose 256 as the batch size, $0 { \cdot } 0 0 1$ as the learning rate, O·6 as the dropout rate, and $0 { \cdot } 0 0 1$ as the weight decay coefficient in MLP. We also used dropout to prevent over-fiting as well. The proposed networks were trained with the AdaGrad algorithm. For XGBoost， we set max_depth as 6, colsample_bytree as O·2,and other configurations as default.For LightGBM, we set num_leaves as 5, lambda_l2 as O·1,learning rate as O·2,and other configurations as default. During LSTM training, we used LSTM architecture with four hidden LSTM layers with 16 one-cel memory blocks and a fully connected layer with one output unit added, followed by a sigmoid function. We set the learning rate as $0 { \cdot } 0 0 0 1$ and the batch size to 2000.

Supplementary Table 2The network structure of the MLP   

<html><body><table><tr><td></td><td>input</td><td>layer1</td><td>layer2</td><td>layer3</td><td>layer4</td><td>layer5</td><td>output</td></tr><tr><td>units</td><td>460</td><td>256</td><td>128</td><td>64</td><td>24</td><td>24</td><td>2</td></tr></table></body></html>

# Appendix VII Results of sepsis prediction models in Task 1

Supplementary Table 3 THE RESULTS OF MODELS IN TASK1   

<html><body><table><tr><td></td><td>Preceding hours</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td> Specificity</td></tr><tr><td>SVM</td><td>1</td><td>0-8762</td><td>0-8762</td><td>0·8726</td><td>0-8797</td></tr><tr><td></td><td>2</td><td>0.8687</td><td>0·8687</td><td>0-8711</td><td>0-8664</td></tr><tr><td></td><td>3</td><td>0-8791</td><td>0.8791</td><td>0.8762</td><td>0.8821</td></tr><tr><td></td><td>4</td><td>0-8665</td><td>0-8665</td><td>0-8736</td><td>0-8594</td></tr><tr><td></td><td>5</td><td>0-8719</td><td>0·8719</td><td>0-8711</td><td>0-8726</td></tr><tr><td>MLP</td><td>1</td><td>0-8443</td><td>0·9539</td><td>0·7123</td><td>0·9764</td></tr><tr><td></td><td>2</td><td>0-8412</td><td>0.9546</td><td>0-7107</td><td>0.9717</td></tr><tr><td></td><td>3</td><td>0-8414</td><td>0-9579</td><td>0-7123</td><td>0-9705</td></tr><tr><td></td><td>4</td><td>0.8462</td><td>0-9564</td><td>0-7292</td><td>0-9632</td></tr><tr><td></td><td>5</td><td>0-8534</td><td>0·9552</td><td>0·7437</td><td>0-9631</td></tr><tr><td>XGBoost</td><td>1</td><td>0-8903</td><td>0·9867</td><td>0·7972</td><td>0-9835</td></tr><tr><td></td><td>2</td><td>0.8962</td><td>0-9883</td><td>0-8113</td><td>0.9811</td></tr><tr><td></td><td>3</td><td>0.8950</td><td>0-9875</td><td>0-8149</td><td>0.9752</td></tr><tr><td></td><td>4</td><td>0.8976</td><td>0.9872</td><td>0.8189</td><td>0-9764</td></tr><tr><td></td><td>5</td><td>0-8990</td><td>0-9873</td><td>0·8200</td><td>0-9780</td></tr><tr><td>LightGBM</td><td>1</td><td>0·8892</td><td>0-9839</td><td>0-8090</td><td>0-9693</td></tr><tr><td></td><td>2</td><td>0-8954</td><td>0·9840</td><td>0-8192</td><td>0-9717</td></tr><tr><td></td><td>3</td><td>0.8950</td><td>0.9825</td><td>0-8255</td><td>0·9646</td></tr><tr><td></td><td>4</td><td>0.9075</td><td>0·9833</td><td>0-8491</td><td>0.9660</td></tr></table></body></html>

<html><body><table><tr><td></td><td>5</td><td>0-9076</td><td>0·9848</td><td>0·8420</td><td>0-9733</td></tr><tr><td>LSTM</td><td>1</td><td>0-8384</td><td>0·9463</td><td>0·7028</td><td>0-9741</td></tr><tr><td></td><td>2</td><td>0-8522</td><td>0·9541</td><td>0-7421</td><td>0-9623</td></tr><tr><td></td><td>3</td><td>0-8561</td><td>0·9486</td><td>0-7665</td><td>0-9458</td></tr><tr><td></td><td>4</td><td>0-8509</td><td>0·9492</td><td>0·7642</td><td>0·9377</td></tr><tr><td></td><td>5</td><td>0-8671</td><td>0·9485</td><td>0-8176</td><td>0-9167</td></tr></table></body></html>

Supplementary Table 3 shows that the AUCs of XGBoost and LightGBM were the highest among these sepsis prediction models, followed by MLP and LSTM,and SVM performed the worst. Although the GBM's structure was relatively simple, it outperformed the artificial neural network models, which may be due to the complexity of artificial neural network models,leading to poor generalization. At the same time,LSTM didn't outperform MLP. In each model, the five tasks of predicting sepsis from 1 to $^ { 5 \mathrm { ~ h ~ } }$ in advance did not show significant differences in the predicting AUC.

# Appendix VIII Resultsof transferred models in Task2

In Task 2,the performances of LightGBM and MLP models trained directly on the RJ dataset are shown in the top half of Supplementary Table 4 and Supplementary Table 5 as a comparison, while models trained with the transfer learning technique are shown in the bottom half.Models trained using the transfer learning technique performed better in most cases.This indicates that the models can learn generic knowledge from MIMIC and help with predictions on the RJ dataset.These models were further ensembled by taking the average.

Supplementary Table4THERESULTSOFLIGHTGBMINTASK2   

<html><body><table><tr><td>Preceding</td><td>Transfer learning</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>hours 1</td><td>N</td><td>0·8500</td><td>0·8644</td><td>0-7333</td><td>0.9667</td></tr><tr><td>2</td><td>N</td><td>0·7333</td><td>0-8769</td><td>0-5889</td><td>0.8778</td></tr><tr><td>3</td><td>N</td><td>0·7292</td><td>0.8613</td><td>0·5833</td><td>0-8750</td></tr><tr><td>4</td><td>N</td><td>0·7600</td><td>0.8857</td><td>0-5733</td><td>0.9467</td></tr><tr><td>5</td><td>N</td><td>0.7556</td><td>0.8913</td><td>0-5889</td><td>0.9222</td></tr><tr><td>1</td><td>Y</td><td>0-8167</td><td>0.9183</td><td>0-7333</td><td>0·9000</td></tr><tr><td>2</td><td>Y</td><td>0·7833</td><td>0.9348</td><td>0-5667</td><td>1:0000</td></tr><tr><td>3</td><td>Y</td><td>0·8583</td><td>0.9171</td><td>0·7333</td><td>0·9833</td></tr><tr><td>4</td><td>Y</td><td>0·7900</td><td>0.9311</td><td>0·5800</td><td>1:0000</td></tr><tr><td>5</td><td>Y</td><td>0.8472</td><td>0.8964</td><td>0-7056</td><td>0·9889</td></tr></table></body></html>

Supplementary Table 5THE RESULTS OF MLP IN TASK2   

<html><body><table><tr><td>Preceding</td><td>Transfer learning</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>hours 1</td><td>N</td><td>0·7750</td><td>0·9150</td><td>0-5667</td><td>0·9833</td></tr><tr><td>2</td><td>N</td><td>0.7778</td><td>0·9037</td><td>0-5889</td><td>0·9667</td></tr><tr><td>3</td><td>N</td><td>0·8083</td><td>0·9021</td><td>0-6333</td><td>0·9833</td></tr></table></body></html>

<html><body><table><tr><td>Preceding</td><td>Transfer learning</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>hours</td><td>N</td><td>0·7900</td><td>0.8953</td><td>0·6133</td><td>0·9667</td></tr><tr><td>4 5</td><td>N</td><td>0·8000</td><td>0·9010</td><td>0·6222</td><td>0.9778</td></tr><tr><td>1</td><td>Y</td><td>0·8083</td><td>0.9172</td><td>0·6500</td><td>0·9667</td></tr><tr><td>2</td><td>Y</td><td>0·7944</td><td>0·8936</td><td>0-6000</td><td>0.9889</td></tr><tr><td>3</td><td>Y</td><td>0-8333</td><td>0·9166</td><td>0-6917</td><td>0-9750</td></tr><tr><td>4</td><td>Y</td><td>0·8267</td><td>0·9221</td><td>0·6867</td><td>0·9667</td></tr><tr><td>5</td><td>Y</td><td>0-8250</td><td>0·9208</td><td>0-6778</td><td>0·9722</td></tr></table></body></html>

# Appendix IX Feature importance

We used the Shapley Additive Explanations (SHAP) analysis to explore the importance of features of different models.The SHAP value of each feature represents the impact of the feature on the output of the model.For LightGBM models trained on the MIMIC-II dataset,the beeswarm plots were shown in Supplementary Figure 1. The importance of features of the same hour and from the same variable were combined,and the twenty most important features were displayed in the figures. As shown in Supplementary Figure 1, several features were found to be important in most models,e.g., $\mathrm { F i O } _ { 2 }$ fibrinogen, calcium, ventilation, age, albumin, antibiotics, $\mathrm { O } _ { 2 } \mathrm { S a t }$ $\mathrm { P C O } _ { 2 }$ , peak inspiratory pressure, and SOFA.

![](images/abe77e44074605cc0342c258bce1e2c2be00eaa650e745dd65d2a19d36113dc4.jpg)  
Supplementary Figure 1 Feature importance of LightGBM models on the MIMIC-II dataset. (i) - (v) are the beeswarm plots of the models detecting sepsis in 1 - 5 hours preceding,respectively. In each subgraph, Y-axis represents different features and X-axis represents the SHAP value of the sample point represented by one dot. A vertical thickness of a dot cluster represents the number of

dots that fall on this SHAP value.The color of a dot represents the value of the feature for one sample, with blue indicating low and red indicating high. The names of features on the Y-axis follow the format‘feature (hours before onset)'.

For the models in SEPRES,the feature importance for LightGBM and MLP models was calculated separately in Supplementary Figure 2 and Supplementary Figure 3.The feature importance ofLightGBM and MLP models was not consistent overall,although they both yielded high AUCs.For LightGBM models,antibiotics,respiratory rate,total PEEP level, fibrinogen,temperature,net balance,and age were found to be important in most models. For MLP models,age,respiratory rate, ventilation, heart rate, antibiotics,and temperature were found to be important in most models.

Some of these features (antibiotics, respiratory rate, temperature, ventilation, heart rate) were related to the definition of Sepsis-3 or SIRS,while there was also literature arguing for an association between some of these features (respiratory rate,5 fibrinogen,6 net balance,7 and age8) and the severity or the mortality of sepsis.

![](images/38e0f4f880f0803f7c07aa3fa29809e79add7caf038d104951798380d5aa7f66.jpg)  
Supplementary Figure 2 Feature importance of LightGBM models in the sepsis early warning module. (i) - (v) are the beeswarm plots of the models detecting sepsis in 1 - 5 hours preceding, respectively.

![](images/27c34878352b991373c7c8bba50cb0eeec4b5945dc8c522c679c5f6061a159a7.jpg)  
Supplementary Figure3Feature importance of MLP models in the sepsis early warning module. (i) - (v) are the beeswarm plots ofthe models detecting sepsis in 1 - 5 hours preceding, respectively.

# Appendix X Case studies

In the actual operation at Ruijin Hospital, the threshold was increased from the default $0 { \cdot } 5 0$ to $0 { \cdot } 7 0$ in order to reduce the false alarm rate of sepsis warning.The adjusted specificity was increased to about $0 { \cdot } 8 8$ ,although the sensitivity was reduced to about O·72, which is shown in Supplementary Table 6.

Supplementary Table 6 THE RESULTS OFREAL-TIME DATA WITHTHRESHOLD AT0·70   

<html><body><table><tr><td>Preceding hours</td><td>Accuracy</td><td>AUC</td><td> Sensitivity</td><td>Specificity</td></tr><tr><td>1</td><td>0-7480</td><td>0·8636</td><td>0·6930</td><td>0-8861</td></tr><tr><td>2</td><td>0·7770</td><td>0-8789</td><td>0·7351</td><td>0-8855</td></tr><tr><td>3</td><td>0·7716</td><td>0-8992</td><td>0·7265</td><td>0-8912</td></tr><tr><td>4</td><td>0·7747</td><td>0-8952</td><td>0·7340</td><td>0-8852</td></tr><tr><td>5</td><td>0.7855</td><td>0.8858</td><td>0-7475</td><td>0·8909</td></tr></table></body></html>

# Positive case:

On February 14, 2021,a 49-year-old man was transferred to our ICU due to intestinal obstruction and abdominal infection after the pancreaticoduodenectomy (PD) one month ago. After the drainage surgery, the condition of the patient aggravated in the early morning of February 15,2O21, with multiple organ dysfunction. At 12:00 AM, the SOFA score was 13 ( $\Delta \mathrm { S O F A } \ \geqslant \ 2$ within 72 hours). In combination with the suspected infection, the patient was diagnosed as sepsis according to the definition of Sepsis-3. Our sepsis early prediction model has already predicted the incidence of sepsis three hours in advance. At 9:00 AM, the sepsis early prediction model showed that the confidence index (CI) of sepsis incidence in one hour was O·7161 which was over the prediction threshold 0·70 (Supplementary Figure 4),and the prediction software at the medical terminal UI interface raised the pre-warning prompt. The high CI at 10:00 AM and $1 1 { : } 0 0 \ \mathrm { A M }$ indicated the aggravation of the patient. The early prediction of sepsis occurrence by our model eectively guided medical practitioners to appropriately pay more attention to this patient, thereby leading to the early diagnosis of sepsis.

![](images/1184e53ab3bacf3078d4c15b85b875a91d6e8c8466d9b03af6508fb43cb76946.jpg)  
Supplementary Figure 4 The confidence index(CI) ofsepsis prediction of the patient at each time node.

# Negative case I:

On May 20,2O21,a 45-year-old man was admitted to our hospital due to chronic renal failure (uraemia period with acute exacerbation) in combination with metabolic acidosis and renal failure after renal transplantation as well as severe hypertension.The patient was given RRT hypertension control treatment. During the monitoring in the ICU, the SOFA score was high (7·O),and the condition of the patient was severe due to several comorbidities and complications in combination with uraemia. However, there was no evidence of $\Delta \mathrm { S O F A } \ \geqslant \ 2$ within 72 hours. Consistently, as shown in Supplementary Figure 5, the CI of sepsis incidence were all lower than the warning threshold $0 { \cdot } 7 0$ ，suggesting no sepsis occurrence after admission. Therefore, this is a negative case.

![](images/b0ed861a23b5f0d40a24bfdb808518fed4e7b74abd928a06bf86d5a35d453d39.jpg)  
Supplementary Figure 5 The confidence index (CI) ofsepsis prediction of the patient at each time node.

Negative case II:

On May 11,2021,a 58-year-old man was admitted into the ICU due to pancytopenia and bloodstream infection combined with respiratory failure, chronic kidney disease,and severe hypertension and diabetes. After the MDT discussion, the patient was considered to be infection-induced myelosuppression and was given anti-infectious treatment.The patient was diagnosed as sepsis on admission and after the treatment in the ICU,the septic condition was improved,and the vital signs of the patient turned to be stable without the new evidence of $\Delta \mathrm { S O F A } \ \geqslant \ 2$ within 72 hours. Therefore, the medical terminal interface showed that the CI of sepsis was lower than the warning threshold $0 { \cdot } 7 0$ (Supplementary Figure 6), suggesting no sepsis occurrence after admission. Therefore, this is a negative case.

![](images/4cd170f0b7f05a7f743c547e9c1fa209d91c388d760febd3013c6ce00cc78203.jpg)  
Supplementary Figure 6 The confidence index(CI) ofsepsis prediction of the patient at each time node.

# Negative case III:

On May 20, 2021,a 69-year-old man was admited into the ICU due to cardiac insufficiency and pneumonia.After the anti-infectious therapy and organ function maintenance,the condition of the patient was improved,and the vital signs were stable. The SOFA score was stable at $5 { \cdot } 0$ without the evidence of $\Delta \mathrm { S O F A } \ \geqslant \ 2$ within 72 hours, suggesting no sepsis occurrence. Consistently, the CI of sepsis predicted by the model was lower than the threshold O·7O,as shown on the medical terminal interface (Supplementary Figure 7), indicating no sign for the warning of sepsis occurrence after admission. Therefore, this is a negative case.

![](images/b84a5c2e574607ca036c2874a5b8d35079b62fe931b70acca47123e283ed90e9.jpg)

Supplementary Figure 7 The confidence index(CI) ofsepsis prediction of the patient at each time node.

# False positive case I:

On May 1,2021,an 84-year-old man was admitted into our hospital due to intracranial space occupying lesion (frontotemporal malignant tumor).The patient was transferred to the ICU due to hospital-acquired pneumonia (klebsiella pneumoniae) and respiratory failure after surgery.The condition of the patient was severe with fluctuations in body temperature during the monitoring period. The SOFA score was stable at $6 { \cdot } 0$ without the evidence of $\Delta \mathrm { S O F A } \ \geqslant \ 2$ within 72 hours, suggesting no sepsis occurrence. However, the CI ofsepsis incidence in 5 hours predicted by our sepsis early prediction model was over the warning threshold O·70 (Supplementary Figure 8). Therefore, this is a false positive case.

![](images/86c44b23a20b78dd29734c05ddb469362c41893f70a0aeb45df9d080797561b0.jpg)  
Supplementary Figure 8 The confidence index(CI) ofsepsis prediction of the patient at each time node.

# Falsepositive case II:

On January 6, 2021,a 26-year-old man was transferred into the ICU due to cardiogenic shock, hyperthyroid heart disease,and pneumonia.The patient was diagnosed as sepsis on admission and was given ventilation and anti-infectious therapy in the ICU.During the monitoring period,the condition of the patient was very severe,and the body temperature significantly fluctuated. The medical terminal interface showed that the CI of sepsis incidence was over the warning threshold O·7O (Supplementary Figure 9). However, the SOFA score was stable at 7·O without the evidence of $\Delta \mathrm { S O F A } \ \geqslant \ 2$ within 72 hours,and the condition of the patient improved after the control of infection.Therefore,this is a false positive case.

![](images/5139be65c465e72d0575d5b189066b6bea39f57d85d92f2a1fad40e020a5ec03.jpg)  
Supplementary Figure 9 The confidence index(CI) ofsepsis prediction of the patient at each time node.

The negative control group used during training the sepsis early prediction model was non-septic patients. Therefore, the prediction model may falsely determine the patient that is severely illto be sepsis.This is a limitation of our present model. To solve this problem，we will analyze the control group by delaminating patients with different severities and further optimize the prediction model.

# False negative case I:

On May 1,2021,a 63-year-old man was admited into our hospital due to sellar tumor. On May 8,2021, during the transnasal transsphenoidal resection of pituitary adenoma,the patient had hemorrhagic shock and hypoxic-ischemic encephalopathy. The patient was transferred into the ICU and was given ventilation and anti-infectious therapy.The SOFA score showed an increase from 6·0 to 9·O (△SOFA ≥ 2 within 72 hours) at $0 6 { : } 0 0 \ \mathrm { P M }$ on May 9,2021.In combination with the evidence of infection, the patient was diagnosed as sepsis. However, as shown on the medical terminal interface (Supplementary Figure 1O), the CI of sepsis incidence was below the warning threshold $0 { \cdot } 7 0$ .Therefore,this isa false negative case.

![](images/eb57decbeea0840f41e629cd96f332837ecdeceeb3c3730e13df0428837d248b.jpg)  
Supplementary Figure 10 The confidence index (CI) of sepsis prediction of the patient at each time node.

# False negative case II:

On March 11,2O021,a 46-year-old man was admitted into the ICU due to severe acute pancreatitis and abdominal infection. During the monitoring period,the patient had an obvious fluctuation in body temperature,and at 06:00 AM on March 13,2021,there was an obvious increase in SOFA score (△SOFA $\geqslant 2$ within 72 hours), indicating the occurrence of sepsis. However, the CI of sepsis incidence was below the warning threshold O·70 (Supplementary Figure 11). Therefore, this is a false negative case.

![](images/fe62da60c287f5b282ac47b4c6c5da7aba5984bee5f61fc608c38dae83699993.jpg)  
Supplementary Figure11 The confidence index (CI) of sepsis prediction of the patient at each time node.

# False negative case III:

On March 15,2021,a 55-year-old man was admitted into our hospital due to severe acute pancreatitis. After debridement and drainage of necrotizing pancreatitis on March 22,2O21,the patient was transferred into the ICU and was given anti-infectious therapy. During the monitoring period,the patient had an obvious fluctuation in body temperature and at $1 0 { : } 0 0 \ \mathrm { A M }$ on March 23,2021, there was an obvious increase in SOFA score $( \Delta \mathrm { S O F A } ~ \geqslant ~ 2$ within 72 hours), indicating the occurrence of sepsis. However, the CI of sepsis incidence was below the warning threshold O·70 (Supplementary Figure 12).Therefore, this is a false negative case.

![](images/40816103a8fcb3918f06040c8a749d184bc2d99fb41964453ec26f7178014c91.jpg)  
Supplementary Figure 12 The confidence index (CI) of sepsis prediction of the patient at each time

node.

We concluded that the ICU duration for all these three false negative cases was relatively short, therefore the data collected for prediction was limited,which may lead to inaccurate prediction for sepsis occurrence.As supporting evidence, there were only 17 positive cases with an onset within 2 days in the RJhistorical dataset, which may not be sufficient for the model to learn positive cases in the absence of enough data.

As a further experiment, we selected cases in the RJ database that were screened out due to too few valid variables,and the performance on these cases is shown in Supplementary Table 7.It can be seen that the sensitivity produced a substantial decrease in sensitivity in contrast to a slight decrease in specificity. This suggests that when there is insuficient valid data for a case, the model willtend to produce lower CI of sepsis incidence,resulting in false negative cases.This may need to be addressed by the inclusion of more positive cases with fewer valid variables,as well as data augmentation.

Supplementary Table7THE RESULTSONCASESWITHFEWVALID VARIABLES   

<html><body><table><tr><td>Preceding hours</td><td>Accuracy</td><td>AUC</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>1</td><td>0·6325</td><td>0·6492</td><td>0-3150</td><td>0.9500</td></tr><tr><td>2</td><td>0.6283</td><td>0-6740</td><td>0-3167</td><td>0.9400</td></tr><tr><td>3</td><td>0·6338</td><td>0·6680</td><td>0-3300</td><td>0·9375</td></tr><tr><td>4</td><td>0-6350</td><td>0·6706</td><td>0-3180</td><td>0-9520</td></tr><tr><td>5</td><td>0·6283</td><td>0·6865</td><td>0-3050</td><td>0·9517</td></tr></table></body></html>

# Appendix XI Differences in features between MIMIC dataset and RJ dataset

![](images/1d9505b35603acf535c7bbd6dce6a565dc6b2a1ae7e2ce247579506a4ec3a5f8.jpg)

Supplementary Figure 13 Feature distributions with relatively large diferences between the MIMIC dataset and the RJ dataset.Each subplot shows the density functions of a feature on two datasets obtained by kernel density estimation using the Gaussian kernel function.

# Reference

Nemati S, Holder A, Razmi F, Stanley MD, Clifford GD, Buchman TG.An interpretable machine

learning model for accurate prediction of sepsis in the ICU. Crit Care Med 2018; 46: 547.   
2 Moor M, Horn M, Rieck B, Roqueiro D, Borgwardt K. Early recognition of sepsis with Gaussian process temporal convolutional networks and dynamic time warping. Machine Learning for Healthcare Conference; 2019: PMLR.   
3 Hong LK, Wogan G, Vacca L, Tidor B, inventors. Peach IntelliHealth Pte Ltd., assignee. System and method for predicting sequential organ failure assessment (sofa） scores using artificial intelligence and machine learning. United States Patent 20190259499; 2019.   
4 Silva A,Cortez P, Santos MF, Gomes L,Neves J. Rating organ failure via adverse events using data mining in the intensive care unit. Artif Intell Med 20o8; 43:179-93.   
5 Kenzaka T, Okayama M, Kuroki S,et al. Importance of vital signs to the early diagnosis and severity of sepsis: association between vital signs and sequential organ failure assessment score in patients with sepsis. Intern Med 2012; 51: 871-6.   
6 Matsubara T, Yamakawa K, Umemura Y, et al. Significance of plasma fibrinogen level and antithrombin activity in sepsis: a multicenter cohort study using a cubic spline model. Thromb Res 2019; 181: 17-23.   
7 Brotfain E, Koyfman L,Toledano R,et al.Positive fluid balance as a major predictor of clinical outcome of patients with sepsis/septic shock after ICU discharge. Am JEmerg Med 2016; 34: 2122- 6.   
8 Martin GS, Mannino DM, Moss M. The effect of age on the development and outcome of adult sepsis. Crit Care Med 2006; 34:15-21.