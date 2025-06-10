# Survey of Multi-sensor Image Fusion

Dingbing ${ \mathbf { W } } { \mathbf { u } } ^ { 1 }$ , Aolei Yang',Lingling Zhu²,and Chi Zhang

1 Shanghai Key Laboratory of Power Station Automation Technology School of Mechatronic Engineering and Automation Shanghai University 149 Yanchang Road, Shanghai, China ² Ningbo Institute of Materials Technology & Enginering, Chinese Academy of Sciences hanbing0821@126.com，aolei.yang@gmail.com, zhull_7627@163.com ，zhangchi@nimte.ac.cn

Abstract. The paper presents multi-sensor image fusion and its relevant framework and technical characteristics.The image fusion is divided into three level fusions: pixel level,feature level and decision level.It mainly discusses the image fusion algorithm at all levels of fusion,and then makes the summary and comparison of these algorithms.Since the high-level algorithms are related to some relevant practical applications of the image fusion,it is in general difficult to be summarized.So this paper also presents some typical algorithms of the feature and decision levels from the perspective of the applications,to provide the necessary summary of the high level image fusion algorithm.Further,the three levels of implementation schemes are described,followed by the comparison and summary for the image evaluation criteria of the fusion method. Some problems and future directions about the multi-sensor image fusion are finally given.

Keywords:Multi-sensor image fusion,image fusion classification,neural network image fusion,decision level fusion,fusion evaluation criteria.

# 1 Introduction

Multi-sensor image fusion is to adopt specific algorithms for combining two or more source images into new image information, which is more suitable for human visual perception, or for computer subsequent processing to meet the requirement of applications, such as image segmentation， feature extraction， and target identification. Through the image fusion technology，we can effectively improve the reliability of the system and the utilization eficiency of image information.From the early 1980s,the research of the multi-sensor image fusion has triggered widespread interest in the world, since it has a wide range of applications in automatic target recognition, computer vision,remote sensing,robotics,medical image processing,military applications and other fields [1-5], for example,infrared image and visible light image fusion can better help the helicopter pilot for navigation,and computed tomography (CT) and magnetic resonance imaging (MRI) are implemented to investigate the anatomy and function of the body in both health and disease,which could provide reliable information for clinical diagnosis [3-6].

The multi-sensor image fusion is generally divided into three level fusions: the pixel level,the feature level and the decision level. Most of the image fusion algorithms are based on the pixel level fusion which is the main fusion algorithm,and the fusion algorithm on the feature and decision levels are much less mentioned in the literature.However,for the high-level image fusion including the feature and decision levels,the corresponding problems of the image fusion are more complex,and the fusion methods of the system are more ambiguous.For example,the feature level image fusion method is in general associated with specific applications,which has rich meanings,and can be used in various applications of the image processing [4-6].

In this paper, the multi-sensor image fusion is divided into three levels depending on our thoughts. The algorithm of the pixel level was presented in detail,and some typical image fusion algorithms in the feature and decision levels are reviewed from the view of application to provide the necessary summary of the high level image fusion algorithm. Specifically,for the pixel algorithms,the classification and comparison of the pixel level algorithm are in detail presented,followed by the summaries of the fusion algorithms on the feature level and decision level.

This remainder of the paper is organized as follows. Section 2 outlines the principles of image fusion technology and architecture,technical features and image fusion classification methods, Section 3 presents a number of specific embodiments of the various methods and features,reviews some of the key issues of image fusion technology,and depicts some typical algorithms of the feature and the decision levels from the perspective of practical applications. Section 4 presents the image fusion evaluation criterion. The paper finally points out some problems and future directions about the multi-sensor image fusion.

# 2 Theory and Characteristics of Image Fusion

# 2.1 Image Fusion Classification

The image fusion requires preliminary pretreatment, which includes several aspects: alignment,calibration,removing noise,etc. After completing the pretreatment, the image fusion can generally be divided into three levels: pixel level, feature level and decision level fusion,which is shown in Fig.1.

A.Pixel level fusion

The pixel level fusion belongs to the lower level of fusion which directly fuses the image pixels information. Currently,most researches focus on this level.It fuses on the layer of the original image data collected from the imaging sensors. It is the highest accuracy level data fusion in spite of its lowest level image fusion. It can provide the details are that the other levels do not have,but a large amount of information need be processed.The pixel level fusion called data level fusion is the basis of the high-level image fusion.

![](images/ba64bc8527ac13d55f9372ce72a5bdc4caae77f75a99ec78a97758576c08212c.jpg)  
Fig.1. Three levels image fusion

B.Feature level fusion

The feature level image fusion extracts feature information from each imaging sensor,and comprehensively analyzes and processes this information. During the fusion, the purpose of application and the scene of the multi-sensor image fusion are closely related to specific form and the feature information. Through the feature level image fusion, the related information is extracted from the original image,and it increases the credibility of the feature information,eliminates the false features,and creates a new composite feature,etc. The feature level image fusion is middle level for the preparation of the decision level fusion. Its advantage is of achieving considerable information compression,and being convenient for real-time processing. Since the extracted feature is directly related to decision analysis,the fusion result can furthest support to decision analysis in the high level fusion.

C.Decision level fusion

The decision level fusion can be simply described as:(1) classify and identify the feature information of each image,(2) form the corresponding results,(3)make the further fusion process.It is a higher level of information fusion,and the fusion results will provide the basis for controls or decisions.Therefore,the decision level fusion must combine with specific application and demand characteristics.Because the feature directly affects the final result,we should selectively use the feature information to achieve the fusion purpose.The input information is all kinds of features,and the output results are about decision descriptions,so the decision level fusion is with the characteristics of the minimum data size and strong anti-jamming.

Tab.1 shows the comparison of the different fusion levels performance characteristics.From the table and the previous description,we can see that the pixel level fusion is the most important and most fundamental multi-sensor image fusion methods，which can obtain a large amount of information and the best fusion performance [4-8].

Table1.Comparison of image fusion levels and performance   

<html><body><table><tr><td>Levels</td><td rowspan="2">Pixel level</td><td rowspan="2">Feature level</td><td rowspan="2">Decision level</td></tr><tr><td>Features</td></tr><tr><td>Information content</td><td>maximum</td><td>medium</td><td>minimum</td></tr><tr><td>Information loss</td><td>minimum</td><td>medium</td><td>maximum</td></tr><tr><td>Fault tolerance</td><td>the worst</td><td>medium</td><td>the best</td></tr><tr><td>Immunity</td><td>the worst</td><td>medium</td><td>the best</td></tr><tr><td>Dependence of the sensor</td><td>maximum</td><td>medium</td><td>minimum</td></tr><tr><td>Method difficulty</td><td>hardest</td><td>medium</td><td>the easiest</td></tr><tr><td>Pretreatment</td><td>minimum</td><td>medium</td><td>maximum</td></tr><tr><td>Classification performance</td><td>the best</td><td>medium</td><td>the worst</td></tr><tr><td>Open systems</td><td>The worst</td><td>medium</td><td>the best</td></tr></table></body></html>

# 2.2 Characteristics of Multi-sensor Image Fusion Technology

The cost of the multi-sensor image fusion is less than that of single sensor, and it gets more or precise target information. The system has the following characteristics: (1) information redundancy: the confidence of the same scene target information may be different for the multi-sensor, but the image fusion will improve the overall target confidence.When a part of sensors are abnormal or damaged, it is also able to improve the system robustness (trustworthiness)；(2） information complementary: the information complementary is achieved from the multi-sensor fusion to make the system getting scenery features，which is not able to be achieved using the single sensor (enlarge the spatial overlapping); (3) enlarge time overlapping: in a long time,the single sensor and the multi-sensors are capable of getting multiple information with a long time overlapping;(4） higher cost performance: as increasing of the number of sensors,the increasing cost of the system is less than its increasing information [1-8].

# 3 Image Fusion Methods

# 3.1 Pixel Level Image Fusion

Currently, the pixel level fusion methods have been more deeply studied. There are many kinds of image fusion algorithms,but the pixel level fusion can be broadly divided into two categories: (1) image fusion based on space domain and (2) image fusion based on transform domain.The significant differences between them are: the former directly fuses the pixels; the latter firstly transforms the image,and the object of fusion is then transformed coefficient instead of pixel values itself. The fusion coefficient may come from several or even all the original space pixel value which is obtained by the result of some transformation. The fusion process is shown in Fig.2.

![](images/5765d97e9f456cf57bfc433472efb3da207032db32893bcd69f637bb090e33b0.jpg)  
Fig.2.Pixellevel image fusion flow

3.1.1 Image fusion algorithm based on space domain

1) Linear Weighting

The linear weighting method is a simple image fusion method,which is to directly make the weighted stacking for corresponding pixels of the original images. If $A _ { k } ( i , j )$ represents the grey value of the $\boldsymbol { k } ^ { \mathrm { { t h } } }$ image at the corresponding position $( i , j )$ , the fusion image $B _ { k } \left( i , j \right)$ can be then obtained by the following formula:

$$
B _ { k } \left( i , j \right) = \sum _ { k = 1 } ^ { n } W _ { k } \left( i , j \right) A _ { k } \left( i , j \right)
$$

$$
\sum _ { k = 1 } ^ { n } W _ { k } \left( i , j \right) = 1
$$

The advantages of the linear weighting method are that its concept is simple and it is suitable for real-time processing. The drawback is that the fusion image contains strong noise,especially,when the gray difference of the fusion image is significant, it may appear obvious splicing trace and poor visual effect.

2) Component Substitution (CS)

The component substitution algorithm is also called false color fusion algorithm. The most representative algorithm is the intensity-hue-saturation (IHS） transform, where“T’ represents density or brightness information,“H”represents chrominance information,and “S”represents saturation information.Although the IHS transform is very important false color fusion algorithm,it is just suitable for three band color image transformation. However, the current imaging systems,i.e. satelite imaging system, could provide far more than three bands.The latest IHS research, the related improvement and discussion to the spectral distortion can refer to the recent literature [2-4].

3)Probability Statistical Model Method

There are many kinds of methods are based on probabilistic statistical model, such as Bayesian estimation theory,Markov random field theory [4-6], etc.The probability and statistics theory is needed to establish the corresponding optimization model, and the expectation maximization or simulated annealing algorithm can be used to solve the problem.

3.1.2 Image fusion algorithm based on transform domain

The transform domain image fusion algorithms include the Discrete Cosine Transform (DCT) and the Fast Fourier Transform (FFT),etc.However, the most important one is based on multi-scale and multi-resolution, such as Wavelet Transform(WT),

Lifting Wavelet Transform (LWT),Discrete Wavelet Transform (DWT)，Ridgelet Transform, Pyramid Decomposition,etc. Currently,this category obtains unprecedented success in all kinds of the image fusion practical applications.The most prominent characteristics are that these algorithms have fast computing capabilities to satisfy a large number of practical systems. 3.1.3 Other image fusion algorithm

In recent years,there are some other image fusion algorithms in this field, such as Gradient-based multi-resolution image fusion method,which is based on the system transfer function theory and is established on basis of fusion decomposition model.It is significantly different from the multi-scale decomposition fusion algorithm.While also image fusion algorithm is based on ICA [7]; PDE-based approach to threedimensional seismic image fusion algorithm [8]; total variation-based image fusion algorithm [9];image fusion algorithm based on geometry [1O];and in recent years based on joint sparse representation theory and the theory of Compressive Sensing(CS） image fusion algorithm [11],[12]. These algorithms are based on broader basis theories,and they expand the meaning of image fusion itself.

# 3.2 Feature Level Image Fusion

The feature level algorithm is divided into two steps: target extraction and target feature fusion. In complex conditions, it is difficult to effectively extract the image target feature,which is a hot research area in this field,so the feature level fusion is more dependent on the target feature whether to correctly obtain. When geting the correct target feature,all classification algorithms,such as support vector clustering, fuzzy clustering, and neural network algorithm, can be directly used to fuse the image feature.

1) Joint Statistical

When multi-sensor information is used for classification and decision,we need some type of discrimination scale,and need compare the sensed environment with the known feature.The joint statistics can be used to quickly and eficiently classify the unknown sample probability density function.

2) Constrained Gauss-Markov Estimate

The covariance matrix is used to storage and to restrain relevant information, and can be used as the fundamental geometric reasoning database.

3)ExtendedKalmanFilter

The Extended Kalman filter can be effectively adopted to make the image registration and then implement the feature layer fusion.It also can reduce the uncertainty of the object location when appearing environment and sensor noise.

4) Neural Network Image Fusion

The characteristics of artificial neural network: inherent parallel structure and parallel processing，distribution storage knowledge,fault tolerance，self-adaptability, etc.Network knowledge representation and acquisition process will be completed at the same time, so the execution speed can be accelerated. Additionally, the image noise exists inevitably in the real world,and even some information may be missing. In this case, the neural network fusion method can also reason in a reasonable way. After the neural network is trained,each image pixel is divided into several classes during image fusion,so that each image pixel has a membership function vector group.At present, most of the neural network is implemented by simulations,and digital signal processing chips and the relevant software are employed to simulate the parallel compute [13-17].

# 3.3 Decision Level Image Fusion

The decision level fusion is a joint decision-making process and is more reliable than single sensor. Currently,the main problems of the decision level fusion: due to the time-varying characteristics of the environment and target, the prior knowledge is difficult to obtain. Simultaneously the enormous knowledge base and the design requirement of the object-oriented system hinder the theory and technology development of the decision level fusion. The main decision level image fusion methods are based on the cognitive model algorithm,which needs to use expert system and relational database to analyze fusion judgment. The fusion algorithms on this level are mainly based on Bayes inference, evidence reasoning, neural networks, support vector machines and fuzzy integral fusion algorithm[7-11],etc.

1)Bayesian estimation

The bayesian estimation provides method which assembles sensor information in probability theory rule.The bayesian estimation is based on Bayes’rule basal technology.

2) Fuzzy Logic

The fuzzy logic is a class of multi-valued logic. The reasoning process uncertainty of the multi-sensor fusion can be directly represented by assigning real values for each proposition and operator from O.O to 1.0. The uncertainty model of the fusion process is then generated, as well as the subsequent consistency reasoning.

3)Dempster-Shafer (D-S)

The dempster-shafer (D-S） reasoning method: it is the bayesian approach extension，which uses probability interval and uncertainty interval to firm the likelihood function under the assumption of more evidence.The evidence theory can deal with uncertainty which is caused by unknown factors.Here,the belief function rather than probability is considered as a measure,bounding some event probability to establish trust function without explanation precise probability which is difficult to obtain.When constraints limit is strict probability，which becomes probabilistic theory.When evidence is relevant，we may consider using D-S theory promotion methods [18-21].

# 4 Performance Evaluation of Multi-sensor Image Fusion Method

The performance evaluation of the image fusion effect is an important and meaningful research aspect, that is, how to evaluate the fusion effect or how to evaluate the image fusion quality.Although it is an important step in the image fusion, there still lack systematic evaluation methods. In the literature,the image fusion evaluation mainly consists of the two subjective and objective evaluation methods.

# 4.1 Subjective Evaluation ofImage QualityFusion

If a person is an image observer, the meaning of the image quality mainly includes two aspects: one is the image fidelity,and another is the image intelligibility. Over many years, people always want to seek quantitative measurement method about the image fidelity and intelligibility to be a criterion of image quality and image design system. Since a human visual system is not fully understood and a quantitative description method about people's psychological factors is not generated, these issues should be resolved in the future.

# 4.2 Objective Evaluation of Image Quality Fusion

In order to overcome the human visual system, mental status, knowledge background and other uncertainty factors,we mostly use the objective evaluation criterion in the actual evaluation of the fusion effect. Objective evaluation determines and compares the pros and cons of various fusion methods through the calculation of fusion image statistical parameters [19-22].

In order to quantitatively evaluate the effect and quality of the fusion image,assuming the two source images of participating into the fusion are $A , B$ ,its image size is $M { \times } N ,$ and the fusion image $F$ can be generated through the fusion treatment, several parameters are defined as follows:

# 1) Entropy

Image entropy is an important index of image information richness,and the entropy value shows how much the image average information is. The greater the entropy value of the fusion image is, the richer the information about the fusion image is,and the better the quality of the image fusion is.

2)Average Gradient

The average gradient can sensitively reflect the expression ability of image tiny details contrasts.It can be not only used to evaluate image clarity,but also reflects the image tiny detail contrasts and texture transform features.

3) Standard Deviation (SD)

The SD reflects the discrete case of the image gray level relative to the average gray level, and it can be used to compare the size of image.If the SD is large, the image grayscale distribution is dispersed,and the image contrasts is big,so more information can be achieved.If the standard deviation and the image contrasts are small and the hue is homogeneous,we do not see too much information.

4) Cross Entropy

The cross entropy called the relative entropy is generally adopted to represent the difference between the two images.The smaller the cross-entropy is,the smaller the image difference is.

5) Correlation Coefficient

The correlation coefficient called similarity measure reflects the relevance of two images.After image fusion,it can reflect the spectrum information of the multispectral image to judge the retention capacity of the fused image spectrum.

# 4.3 Combination of Subjective and Objective Methods

The combination of subjective and objective quality evaluation method is an important index of the fusion image quality evaluation. It is the combination of artificial intelligence and expert systems fusion method to evaluate the effect [3O]. This method does not require the ideal image,and does not take full account of the human visual characteristics. It can quantitatively evaluate the fusion image retaining much significant information (such as variance,contrast and edge information,etc.). It is a practical, effective and versatile method of the image fusion quality evaluation.

# 5 Conclusions

In this paper, the multi-sensor image fusion is divided into three levels,which are made relatively systematic analyze and compare. This paper makes a systematic summary about the algorithms of the pixel, the feature and the decision levels from a large number of literatures.For lots of the pixel algorithms,the classification and comparison of the pixel level algorithm is presented in detail. Facing numerous the feature level and decision level algorithms,we list some typical algorithms for everyone's reference.

The involved image fusion technology is very extensive,and it is restricted by time and conditions,so there is a lot of intensive detail work need to be continued in the future:

1)Although there are many kinds of the image fusion methods,researchers do not think there is recognized standard and mature theory to support particular type image fusion. For the specific type image fusion, we need to develop corresponding unified mathematical model and integration framework.

2) In this paper, we study the objective evaluation methods are just some commonly evaluation methods,to avoid subjective evaluation of one-sidedness on some level. There are so many image fusion evaluation methods and standards, however, for the specific image fusion,the uniform evaluation criteria becomes an urgent problem to be studied.

3) The rapid image fusion can be achieved by the optimization algorithm and reducing the algorithm complexity. The improvement of the fusion effect often sacrifices the calculation speed and the algorithm complexity. The rapid and simple algorithm is the foundation of practical applications,so it is necessary to optimize the algorithm and study the fast algorithm.

# References

1.Mahmood,A., Tudor,P.M., Oxford,W.: Applied Multi-dimensional Fusion. Computer Journal 50(6),646-659 (2007)   
2.Gholipour,A.,Kehtarnavaz,N.,Briggs,R.: Brain Functional Localization:A Survey of Image Registration Techniques.IEEE Transactions on Medical Imaging 26(4),427-451 (2007)   
3． Chikr,M.,Mezouar,E., Taleb,N., Kpalma,K.: An IHS-based Fusion for Color Distortion Reduction and Vegetation Enhancement in IKONOS Imagery. IEEE Transactions on Geoscience and Remote Sensing 49(5),1590-1602 (2011)   
4.John Nisha Anita, S., John Moses,C.: Survey on Pixel Level Image Fusion Techniques. In: International Conference on Emerging Trends in Computing, Communication and Nanotechnology,pp.141-145 (2013)   
5.Xu,M., Chen,P.H., Varshney,K.: An Image Fusion Approach Based on Markov Random Fields. IEEE Geosci. Remote 49(12),5116-5127 (2011)   
6.Mignote,M.A.: Multiresolution Markovian Fusion Model for the Color Visualization of Hyper Spectral Images. IEEE Transactions on Geoscience and Remote Sensing 48(12), 4236-4247 (2010)   
7.Nedeljko, C., David, B., Nishan, C.: Region-based Multimodal Image Fusion Using ICA Bases.IEEE Sensors Journal 7(5),743-751 (2007)   
8.Sorin,P., Lavialle, O.,Donias,M.: A PDE-based Approach to Three-dimensional Seismic Data Fusion. IEEE Transactions on Geoscience and Remote Sensing 46(5),1385-1393 (2008)   
9.Kumar,M.,Dass,S.: A Total Variation-based Algorithm for Pixel-level Image Fusion. IEEE Transactions on Image Processing 18(9),2137-2143 (2009)   
10.Mark,A., Davenport, B., Hegde, C.: Joint Manifolds for Data Fusion. IEEE Transactions on Image Processing 19(10),2580-2594 (2010)   
11.Yu,N., Qiu, T.S.，Wang，A.Q.: Image Features Extraction and Fusion Based on Joint Sparse Representation. IEEE Journal of Selected Topics in Signal Processing 5(5), 1074-1082 (2011)   
12. Wan, T., Qin, Z.C.: An Application of Compresive Sensing for Image Fusion. International Journal of Computer Mathematics 4,1-16 (2011)   
13.Rong,W., Fanliang, B., Hua, J., et al.: A Feature-level Image Fusion Algorithm Based on Neural Networks. In: 2Oo7 1st International Conference on Bioinformatics and Biomedical Engineering,Wuhan, pp. 821-824 (2007)   
14. Kong,A., Zhang, D., Kamel, M.: Palmprint Identification Using Feature-level Fusion. Pattern Recognition 39(3),478-487 (2006)   
15.Ross,A., Govindarajan,R.: Feature Level Fusion Using Hand and Face Biometrics. Biometric Technology for Human Identification II 57(79),196-204 (2005)   
16.Kong,A., Zhang, D., Kamel, M.: Palmprint Identification Using Feature-level Fusion.Pattern Recognition 39(3),478-487 (2006)   
17.Wu, K.X., Wang, C.H.,Li,L.H.: Image Fusion at Pixel Level Algorithm is Introduced and the Evaluation Criteria.In: International Conference on Educational and Network Technology,pp.585-588 (2010)   
18. Qian, T., Veldhuis,R.: Threshold-optimized Decision-level Fusion and Its Application to Biometrics.Pattern Recognition, 823-836 (2009)   
19.Dawoud,A., Alam, M.S., Bal, A.: Target Tracking in Infrared Imagery Using Weighted Composite Reference Function-based Decision Fusion. IEEE Transactions on Image Processing 15(2),404-410 (2006)   
20.Huan,R.,Pan, Y.: Decision Fusion Strategies for SAR Image Target Recognition. IET Radar Sonar&Navigation 5(7),747-755 (2011)   
21.Yi,W.,Wei, C.,Yi,M.S.: Multi-sensor Decision Level Image Fusion Based on Fuzzy Theory and Unsupervised FCM. In: Proceedings of the SPIE-The International Society for Optical Engineering, pp. 62000-62007 (2006)   
22. Kong, W.W.: Multi-sensor Image Fusion Based on NSST Domain I2CM. Electronics Letters 49(13),802-803 (2013)