# A method on selecting reliable samples based on fuzziness in positive and unlabeled learning

TingTing Li   
College of Computer and Information   
Science,Chongqing Normal University China litingting@cqnu.edu.cn WeiYa Fan   
College of Computer and Information   
Science,Chongqing Normal University China fanweiya@cqnu.edu.cn YunSong Luo   
College of Computer and Information   
Science,Chongqing Normal University China luoyunsong@cqnu.edu.cn

# ABSTRACT

Traditional semi-supervised learning uses only labeled instances to train a classifier and then this classifier is utilized to classify unlabeled instances,while sometimes there are only positive instances which are elements of the target concept are available in the labeled set. Our research in this paper the design of learning algorithms from positive and unlabeled instances only.Among all the semi-supervised positive and unlabeled learning methods,it is a fundamental step to extract useful information from unlabeled instances.In this paper,we design a novel framework to take advantage of valid information in unlabeled instances.In essence, this framework mainly includes that（1） selects reliable negative instances through the fuzziness of the instances;(2) chooses new positive instances based on the fuzziness of the instances to expand the initial positive set, and we named these new instances asreliable positive instances;(3）uses data editing technique to filter out noise points with high fuzziness.The effectiveness of the presented algorithm is verified by comparative experiments on UCI dataset.

# CCSCONCEPTS

·Theory of computation $$ Theory and algorithms for application domains $$ Machine learning theory $$ Semi-supervised learning

# KEYWORDS

positive and unlabeled learning; fuzziness;reliable instances; data editing

# 1 INTRODUCTION

Semi-supervised positive unlabeled (PU) learning refers to the task of learning a binary classifier from only positive and unlabeled data[1-3].PUlearninghas drawn considerable attention recently,it is appealing to not only the academia but also the industry[4]. Such as:

Deceptive opinion detection[5]，where the goal is to find negative deceptive opinions from the unlabeled ones.

Disease genes prediction[6],where the goal is to find disease candidate genes through gene expression profiles from the human genome.

Cross-domain sentiment classification[Z],where the goal is to develop an instance adaptation method for cross-domain sentiment classification.

Software fault detection[8],where the goal is to build a prediction model for software fault detection.

In the traditional PU-learning, two methods are proposed to establisha PUclassifier.One is to heuristically identifyreliable negative (RN) instances from unlabeled instances and then use themto train standard binary classifiers,and the other is to use the whole unlabeled instances as negative data to establish binary classifiers[9].

The basic algorithm for PU-learning was described in text classification[1O]. It proceeded as follows: first,the whole unlabeled set is considered as the negative class,the instances from the unlabeled set classified as negative are selected to form the initial set ofRN.The second part iteratively enlarges the set of RN instances by increasing some additional instances from unlabeled set. The evaluation of the proposed method was carried out through used a set of hotel reviews gathered by Ott et al.[11]. As a further study,Donato et al[l2].believed that RN contains noise points,they proposed a method considers its iterative pruning,the experimental results demonstrated the effectiveness of the method.

Therefore，how to effectively select the reliable negative instances of unlabeled set is the most important work in PU learning. Some works proposed an automatic KL-divergence learning method which utilized the knowledge of unlabeled data distribution[9]. However, few people use the spatial structure of unlabeled set to extract valid information.In other words,we believe that unlabeled data may contain potential information of data space structure,which can be effectively used to assist PUlearning better and improve the generalization of PU-learning.As a knowledge mining tool, semi-supervised fuzzy c-means[13] can mine the data space structure information implied by a large number of unlabeled set.Yin et al[14]. proposed semi-supervised metric-based fuzzy clustering,which using the method of entropy regularization to solve the problem of parameter value selection of semi-supervised fuzzy c-means,and replacing the Euclidean distance with Mahalanobis distance,this way can select unlabeled instances with more information.The fuzziness of this classifier attains its minimum when every element absolutely belongs to the fuzzy set or absolutely not.The fuzziness attains its maximum when the membership degree of each element is equal to 0.5, i.e., the classification boundary is at the place where the fuzziness is equal to 0.5[15-17].

In this paper,we propose a novel framework to extract valid information of unlabeled instances.Our contributions are as follows:

1.In order to select reliable negative instances of the unlabeled set effectively,a new method that mines unlabeled instances space structure based on fuzziness is adopted.This is a general method which used on category data. 2.An approach to expand the initial positive set is proposed first,and we named these new instances as reliable positive instances. 3.With the help of classification fuzziness,we use data editing technique to filter out noise points.

A series of experiments are conducted on UCI dataset,using Fscore as the measure.Experimental results show that our method can always reach high performance.

The rest of this paper is organized as follows: Section 2 presents related work; Section 3 introduces the new PU-learning framework basedonsemi-supervised metric-based fuzzy clustering algorithm；Finally,the experimental results are in Section 4; followed by the conclusion in Section 5.

# 2 Related work

# 2.1 PU Learning

PU-learning is a semi-supervised classifier with only positive instances(P) and unlabeled sets(U) that contain both positive and negative instances.Then our task is to construct a classifier (C), which can find all reliable negative instances (RN) hidden in the unlabeledset.Itisformulatedasfollows:input (P,U) $\Rightarrow$ output(RN). The basic algorithm for PU-learning is shown in algorithm 1.

<html><body><table><tr><td>Input:a training dataset with a few positive samples P and lots of unlabeled samples U. Output: the labeled datasetD Step 1: i←-1</td></tr><tr><td>Step 2: Ci←Generate_Classifier(P,U) Step 3: UiL←Ci(U) Step 4:Qi←Extract_Negatives(UiL) Step 5: RNi←Qi</td></tr><tr><td>Step 6: Ui←U-Qi Step 7: while| Qi>O do Step 8:i←i+1</td></tr><tr><td>Step 9: Ci←Generate_Classifier(P,RNi-1) Step10: UiL←Ci(Ui-1) Step 11: Qi←Extract_Negatives(UiL) Step 12: Ui←Ui-1-Qi</td></tr></table></body></html>

Algorithm1.ThebasicalgorithmforPU-learning

# 2.2Semi-supervised metric-based fuzzy clustering

Inorder to explore the effective information in unlabeled instances better,we hope to derive a group of clusters with side information and fuzzy nature of the data. Therefore,we need the classifiers whose outputs are vectors of membership grades. semisupervised metric-based fuzzy clustering algorithm called SMUC is an algorithm that introduces metric learning and entropy regularization simultaneously into traditional fuzzy clustering. More specifically，SMUC focuses on learning a mahalanobis distance metric from side information given by the unlabeled instances.Thus,it makes the distance between instances within a cluster smaller than that between instances belonging to different clusters.Moreover, SMUC introduces maximum entropy as a regularized term in its objective function so that its formulas have more clear physical meaning compared with the other semisupervised fuzzy c-means methods.The derivation formula of SMUC is as follows:

jiven a prior membership degree and expressed as:

（20 $\mathrm { U } ^ { \prime } = \bigl \{ \mathrm { u } _ { \mathrm { i k } } ^ { \prime } \bigl | \mathrm { u } _ { \mathrm { i k } } ^ { \prime } \in [ 0 , 1 ] ; \mathrm { i } = 1 , . . . , \mathrm { n } ; \mathrm { k } = 1 , . . . , \mathrm { c } \bigr \} ,$ （204号 (1) where c and $\mathfrak { n }$ are the numbers of clusters and instances, respectively. If ${ \bf u } _ { \mathrm { i k } } ^ { \prime }$ is not given. Then the value $\mathrm { u _ { \mathrm { i k } } ^ { \prime } } = 0$ , Clearly, conditions for ${ \bf u } _ { \mathrm { i k } } ^ { \prime }$ can be written as:

$$
\sum _ { \mathrm { k = 1 } } ^ { \mathrm { c } } \mathrm { u _ { \mathrm { i k } } ^ { \prime } } \le 1 . ( \forall \mathrm { i } = 1 , 2 , \ldots , \mathrm { n } ) .
$$

So,we formulate the SMUC algorithm as follows:Given a set of data instances $\mathrm { X } = \{ \mathrm { x } _ { 1 } , \mathrm { x } _ { 2 } , . . . , \mathrm { x } _ { \mathrm { n } } \}$ with some prior membership degrees $\mathrm { ~ U ~ } ^ { \prime }$ ,find the optimal membership $\mathrm { ~ U ~ }$ such that X can be properly partitionedc fuzzy subsets.First ofall,we can obtain the preliminary centroid:

$$
\mathrm { v _ { k } ^ { \prime } = \frac { \sum _ { i = 1 } ^ { n } \mathrm { u _ { i k } ^ { ' 2 } \mathrm { x _ { i } } } } { \sum _ { i = 1 } ^ { n } \mathrm { u _ { i k } ^ { ' 2 } } } . }
$$

Next, the covariance matrix is calculated as follows:

$$
\mathrm { C = \frac { 1 } { n } \mathrm { \sum _ { k = 1 } ^ { c } \sum _ { i = 1 } ^ { n } u _ { i k } ^ { \prime 2 } \big ( x _ { i } - v _ { k } ^ { ' } \big ) \big ( x _ { i } - v _ { k } ^ { ' } \big ) ^ { T } . } }
$$

According to (4),the mahalanobis distance of $_ \mathrm { x l }$ and $_ { \mathbf { x } 2 }$ can be given as follows:

$$
\begin{array} { r } { \mathsf { d } _ { \mathrm { A } } ^ { 2 } ( \mathbf { x } _ { 1 } , \mathbf { x } _ { 2 } ) = ( \mathbf { x } _ { 1 } - \mathbf { x } _ { 2 } ) ^ { \mathrm { T } } \mathbb { C } ^ { - 1 } ( \mathbf { x } _ { 1 } - \mathbf { x } _ { 2 } ) , } \end{array}
$$

where $\mathsf { A } = \mathsf { C } ^ { - 1 }$ .With this new metric,we minimize the dispersion between the instance and the set $\mathrm { \Delta V }$ of $\mathrm { C }$ prototypes:

$$
\begin{array} { r } { \mathrm { J _ { A } ( U , V ) = \displaystyle \sum _ { k = 1 } ^ { c } \sum _ { i = 1 } ^ { n } u _ { i k } \left| | x _ { i } - v _ { k } \right| | _ { A } ^ { 2 } } } \\ { + \eta ^ { - 1 } \displaystyle \sum _ { k = 1 } ^ { c } \sum _ { i = 1 } ^ { n } \left( u _ { i k } - u _ { i k } ^ { ' } \right) \ln { ( \mathrm { u _ { i k } ~ } } } \\ { - u _ { i k } ^ { ' } ) ~ } \end{array}
$$

where $\mathbf { u } _ { \mathrm { i k } }$ is the membership degree of $\mathbf { X _ { i } }$ belonging to the cluster $\mathrm { C k }$ whose centroid is $\mathbf { v _ { \mathrm { k } } ^ { \prime } }$ and satisfies the following condition:

$$
\mathrm { { s . t . } \sum _ { k = 1 } ^ { c } u _ { i k } = 1 , \ u _ { i k } \ge 0 . }
$$

Equation (6) is the convexity of the optimization problem,we further define a Lagrangian functionas follows:

$$
\begin{array} { r l } & { \qquad \mathrm { ~ L } ( \mathrm { U } , \mathrm { V } , \lambda ) = \mathrm { J } _ { \mathrm { A } } ( \mathrm { U } , \mathrm { V } ) + \displaystyle \sum _ { \mathrm { i } = 1 } ^ { n } \lambda _ { \mathrm { i } } ( \displaystyle \sum _ { \mathrm { k } = 1 } ^ { \mathrm { c } } { \bf u } _ { \mathrm { i k } } - 1 ) } \\ & { = \displaystyle \sum _ { \mathrm { k } = 1 } ^ { \mathrm { c } } \displaystyle \sum _ { \mathrm { i } = 1 } ^ { n } { \bf u } _ { \mathrm { i k } } | | { \bf x } _ { \mathrm { i } } - { \bf v } _ { \mathrm { k } } | | + \eta \displaystyle \sum _ { \mathrm { k } = 1 } ^ { \mathrm { c } } \sum _ { \mathrm { i } = 1 } ^ { \mathrm { n } } ( { \bf u } _ { \mathrm { i k } } - { \bf u } _ { \mathrm { i k } } ^ { \prime } ) \ln ( { \bf u } _ { \mathrm { i k } } - { \bf u } _ { \mathrm { i k } } ^ { \prime } )  } \\ & {  + \displaystyle \sum _ { \mathrm { i } = 1 } ^ { \mathrm { n } } \lambda _ { \mathrm { i } } ( \displaystyle \sum _ { \mathrm { k } = 1 } ^ { \mathrm { c } } { \bf u } _ { \mathrm { i k } } - 1 ) , } \end{array}
$$

where $\lambda _ { \mathrm { i } }$ is a lagrangian multiplier,and then:

$$
{ \frac { \partial \mathrm { L } } { \partial \mathrm { V _ { \mathrm { k } } } } } = \sum _ { \mathrm { i = 1 } } ^ { \mathrm { n } } 2 \mathrm { u _ { \mathrm { i k } } ( \mathrm { x _ { \mathrm { i } } - V _ { \mathrm { k } } ) = 0 . } }
$$

We get the optimal solution of $\mathtt { V _ { k } }$ as follows:

$$
\mathrm { { V _ { k } } = \frac { \sum _ { i = 1 } ^ { n } \mathrm { { u _ { i k } } \mathrm { { X _ { i } } } } } { \sum _ { i = 1 } ^ { n } \mathrm { { u _ { i k } } } } . }
$$

We take the derivative of $\mathrm { L } ( \mathrm { u _ { i k } } )$ with respect to $\mathbf { u } _ { \mathrm { i k } }$ and set it to zero:

$$
\begin{array} { c } { \displaystyle \frac { \partial \mathrm { L } } { \partial \mathbf { u } _ { \mathrm { i k } } } = \vert \vert \mathrm { x } _ { \mathrm { i } } - \mathrm { v } _ { \mathrm { k } } \vert \vert _ { \mathrm { A } } ^ { 2 } + \eta ^ { - 1 } \big ( \mathrm { l n } \left( \mathrm { u } _ { \mathrm { i k } } - \mathrm { u } _ { \mathrm { i k } } ^ { \cdot } \right) + 1 \big ) + \lambda _ { \mathrm { i } } } \\ { = 0 . } \end{array}
$$

Therefore

$$
\mathrm { u _ { i k } = u _ { i k } ^ { \prime } + \rho ^ { - \eta ( \left( d _ { A ( i , k ) } + \lambda _ { i } \right) + 1 ) } } .
$$

where $\mathrm { d _ { A ( i , k ) } = | | x _ { i } - v _ { k } | | _ { A } ^ { 2 } }$ . According to constraints （7),we get the following equation:

$$
\sum _ { \mathrm { k = 1 } } ^ { \mathrm { { \bar { c } } } } { \mathrm { u _ { i k } } } = \sum _ { \mathrm { k = 1 } } ^ { \mathrm { c } } { \mathrm { u _ { i k } ^ { \cdot } } } + \sum _ { \mathrm { k = 1 } } ^ { \mathrm { c } } { \rho ^ { - \eta ( \left( { \mathrm { d _ { A ( i , k ) } } } + { \lambda _ { i } } \right) + 1 ) } } \ : .
$$

Reducing the above equation, we derive:

$$
\rho ^ { - \eta \lambda _ { \mathrm { i } } } = \frac { 1 - \sum _ { \mathrm { k = 1 } } ^ { \mathrm { c } } \dot { \mathrm { u } _ { \mathrm { i k } } ^ { \cdot } } } { \rho ^ { - 1 } \sum _ { \mathrm { k = 1 } } ^ { \mathrm { c } } \rho ^ { - \eta \mathrm { d } _ { \mathrm { A ( i , k ) } } } } .
$$

Then,the optimal solution of $\mathbf { u } _ { \mathrm { i k } }$ as follows:

$$
\mathrm { \mathbf { u } _ { i k } = \mathbf { u } _ { i k } ^ { ' } + \frac { \boldsymbol { \rho } ^ { - \eta | | \mathrm { x } _ { i } - \mathrm { v } _ { k } | | _ { A } ^ { 2 } } } { \sum _ { j = 1 } ^ { c } \boldsymbol { \rho } ^ { - \eta | \left| \mathrm { x } _ { i } - \mathrm { v } _ { j } \right| | _ { A } ^ { 2 } } } \left( 1 - \sum _ { j = 1 } ^ { c } \mathrm { \mathbf { u } _ { i k } ^ { ' } } \right) . }
$$

Where each element in the output vector indicatesthe membership with which the input sample belongs to the corresponding class.The algorithmis given in Algorithm 2.

Input: D-dataset, a prior membership matrix ${ \bf u } _ { \mathrm { i k } } ^ { \prime }$ ， number   
of clusters c.   
Output: Membership matrix $\mathbf { u } _ { \mathrm { i k } }$   
Step1: Compute the preliminary centroid according to (3).   
Step 2: Compute the metric matrix according to (4) using   
${ \bf u } _ { \mathrm { i k } } ^ { \mathrm { \cdot } }$   
Step 3: while $| | \mathbf { u } _ { \mathrm { k } } - \mathbf { u } _ { \mathrm { k - 1 } } | | \geq \varepsilon$ Compute $\mathbf { u } _ { \mathrm { i k } }$ according to (15). Compute ${ \tt V } _ { \mathrm { k } }$ according to (10). end   
Step 4: Return Uik·

Algorithm 2. The algorithm for SMUC. ${ \bf u } _ { \bf i k } ^ { \prime }$ ，is the prior membership matrix，c is the numberofclusters.

# 2.3Classification fuzziness and side effects of boundary instances

In [18],Zadeh first mentioned the term “fuzziness” and the concept of fuzzy set. This article points out the imprecision existing in ill-defined events,which cannot be described by sharply defined collection of points.Wang etal[15].believed that the fuzziness of a fuzzy set attains its minimum when every element absolutely belongs to the fuzzy set or absolutely not, i.e., $\mathrm { \Delta u _ { i k } } = 0$ or $\mathbf { u } _ { \mathrm { i k } } = 1$ ；they also find that instances with higher fuzziness are near to the classification boundary,while samples withlower fuzziness are relatively far from the classification boundary. The boundary is shown in Fig.1 (a).Furthermore,it can be confirmed that both the misclassified instances and the instances with the larger fuzziness are all near to the classification boundary, which is shown in Fig.1 (b).

10 Boundary Boundary +ε × X x X× X xX xx xX X xXx   
6 xxx X X X 美 X ×X X XxX X X X 艾 X X X Xx   
42 × X XX +++ X XX xx +++ x XX XX XX X Xx 8 Xx X 8 0 X ? ® 8 X 0 8   
-2 囍 3 共 x XXx X X Xxx 新 X X X\* 0 ++ XX ++   
-6 X X X Xx xX X X × ++ xx   
8 2 3 4 5 6 7 8 9 10 2 3 4 5 6 7 .8 9 10 (a) (b)

# 3The main algorithm

Based on the analysis above，we propose a new PU-learning frameworkbasedonsemi-supervisedmetric-basedfuzzy clustering algorithm called PUFC.This algorithm calculates the cluster membership ofU set bases on $\mathrm { \bf ~ P }$ set andU set,we select the membership degree that belongs to the positive class only. When the membership degree get closer to 1,the fuzziness of the data belongs to the positive class is smaller,that is,the probability of the data belonging to the positive class is larger.On the contrary,when the membership degree is closer to 1,the fuzziness of the data belonging to negative class is smaller,that is to say the possibility of being a negative class is larger. Therefore,we set a parameter ε ( $( 0 < \mathfrak { s } < 0 . 5 )$ ，when the membership degree ${ \bf u } _ { \mathrm { i } } ^ { + }$ （ $\overset { \cdot } { 1 } \leq$ $\mathrm { u } _ { \mathrm { i } } ^ { + } \leq 0 . 5 - \varepsilon )$ ,we consider this instance to be a reliable negative instance；when the membership degree ${ \bf u } _ { \mathrm { i } } ^ { + }$ （20 $( 0 . 5 + \varepsilon \leq \mathrm { u _ { i } ^ { + } } \leq 1 )$ ， we consider this instance to be a reliable positive instance.In addition, the fuzziness and misclassification will reach its maximum when the membership degree of each instance is equivalent to O.5.So,we consider instances with membership $\mathrm { u _ { i } ^ { + } } \left( 0 . 5 - \varepsilon < \mathrm { u _ { i } ^ { + } } < 0 . 5 + \varepsilon \right)$ as noisy points and edit these data. By means of this way it is possible to divide reliable negative instances,reliable positive instances and noisy points from the unlabeled set,and to constructa better final binaryclassifier than using the extra comparison algorithms.The specific algorithm is as follows:

Input:a training dataset with a few positive instances $\mathrm { \bf ~ P }$ and   
lots of unlabeled instances U,where $P = \{ P _ { 1 } , P _ { 2 } , . . . P _ { n } \}$ $n$ is the   
number of positive instances, $U = \{ U _ { 1 } , U _ { 2 } , . . . U _ { m } \}$ ，mis the   
number of unlabeled instances; Parameter ε.   
Output: the labeled dataset D   
Step 1: Set $\scriptstyle \mathrm { R N } = O$ ；Set $\scriptstyle \mathrm { R P = } O$ ；SetNoise $_ { = 0 }$   
Step 2: SetP with label 1,U with label -1.   
Step 3: Clustering U set based on $\mathrm { \bf ~ P }$ and U with Algorithm 2, and obtaining cluster membership degree $u _ { i k }$ ：   
Step 4: Select the membership degree that belongs to the positive class $u _ { i } ^ { + }$   
Step 5: for $\mathrm { i } { = } 1 { : } \mathrm { m }$ （204号   
Step 6:if $0 \leq u _ { i } ^ { + } \leq - \varepsilon + 0 . 5$ （20 $R N { = } R N { + } U _ { i } .$   
Step 7: else if $- \varepsilon + 0 . 5 < u _ { i } ^ { + } < \varepsilon + 0 . 5$ Noise= Noise +Ui.   
Step 8: else if $\varepsilon + 0 . 5 \leq u _ { i } ^ { + } \leq 1$ $R P { = } R P { + } U _ { i } .$ end end end end   
Step9:The reliable negative instances RN is obtained,and set RN with label -1.   
Step1o:The reliable positive instancesRP is obtained,and set RP with label 1.   
Step 11:Expand the initial positive set,where $\scriptstyle \mathbf { P } = \mathbf { P } + \mathbf { R } \mathbf { P }$   
Step12:Uses data editing technique to filter out noise point with high fuzziness,I.e. throw away the Noise set.   
Step13:TrainaclassifierCwithPand RN.   
Step 14: Classify instances in Uusing C.   
Step 15: Output the labeled dataset D.

# 4Experiment and analysis

# 4.1Experimental algorithm and description

In order to illustrate the effectiveness of the experiment,the following algorithm was used for the comparison experiment:

(1) The basic algorithm of PU-learning（Basic） (2)PU- learning based on spy technology (Spy)[19]. (3）A conservative variant of the original PU learning   
algorithm. Instead of following an iterative growing strategy for   
building the RN set,this method considers its iterative pruning   
(Pruning)[12].   
In our experiment,a collection of 9 real world dataset from the   
UCI and kaggle repository was used, where contain few   
hundreds/thousands of samples.Part of the datasetIonosphere and   
dataset abalone are processed,and for dataset Ionosphere,two of

the discrete attributes are deleted; For dataset abalone,we merge it into two categories of data.Table 1 shows some of their statistics.

Table1 DescriptionofUCI dataset   

<html><body><table><tr><td>Data</td><td>Size</td><td>Features</td></tr><tr><td>Banknote authentication</td><td>1372</td><td>4</td></tr><tr><td>lonosphere</td><td>351</td><td>32</td></tr><tr><td>pima</td><td>768</td><td>8</td></tr><tr><td>Haberman Survival</td><td>306</td><td>3</td></tr><tr><td>Wholesale customers</td><td>440</td><td>8</td></tr><tr><td>Breast Cancer Coimbra</td><td>115</td><td>7</td></tr><tr><td>Breast Cancer Wisconsin</td><td>516</td><td>30</td></tr><tr><td>Indian Liver Patient</td><td>583</td><td>5</td></tr><tr><td>abalone</td><td>4177</td><td>8</td></tr></table></body></html>

During the experiment, each dataset will be divided into two parts using ten cross-validation methods: the training set and the test set, in which the training set accounted for $90 \%$ and the test set accounted for $10 \%$ .Then $20 \%$ ， $30 \%$ + $40 \%$ + $50 \%$ and $60 \%$ of the training instances were selected as the initial positive instances in the training set.

# 4.2 Evaluation measure

In our experiments,we use the popular F-measure on the positive class as the evaluation measure[2O]. The F-measure is computed as follows:

$$
\mathrm { F - m e a s u r e } = { \frac { 2 * { \mathrm { p r e c i s i o n } } * { \mathrm { r e c a l l } } } { \mathrm { p r e c i s i o n } + \mathrm { r e c a l l } } }
$$

The parameter ε is mentioned in the third part,we know that different parameter have different effects on the experimental results.Therefore,we assign different values to ε by taking $30 \%$ of the positive instances and calculate the F-measure of the algorithm proposed in this paper.Table 2 shows the effect on Fmeasure when selecting different parameter values.

It can be shown from Table 2 that different parameter values will produce different classification effects,and this phenomenon is related to the distribution characteristics of the dataset itself. Observe this table,we find that for different dataset,the parameters ε corresponding to the highest F-measure must be set in order to achieve the best experimental results.So in the next experiments,which $20 \%$ and $30 \%$ of the positive instances are selected as the initial positive instances in the training set.The experimental resultsare shown in Table 3 and Table 4,where the mean and standard deviation of the F-measure are provided in percent.The bold digit in each line indicates that the best mean Fmeasure obtains from the corresponding PUFC algorithm. correlation between attributes of dataset Wholesale customers or Indian Liver Patient are not strong.While SMUC takes into account the correlation between attributes in practical applications and uses entropy regularization to optimize physical expressions, therefore,our algorithm cannot achieve satisfactory results in these two dataset.It can be viewed on the above analysis that PUFC has better classification performance when the number of labeled sample sets is extremely missing.

Table 2 The effect on F-measure when selecting differentε   
%(percent)   

<html><body><table><tr><td>Data</td><td>0</td><td>0.05</td><td>0.1</td><td>0.15</td><td>0.2</td><td>0.25</td><td>0.3</td><td>0.35</td><td>0.4</td><td>0.45</td></tr><tr><td>Banknote authentication</td><td>72.2553</td><td>73.1030</td><td>72.422</td><td>69.8368</td><td>67.6378</td><td>61.3922</td><td>61.4074</td><td>61.434</td><td>61.4903</td><td>61.4241</td></tr><tr><td>lonosphere</td><td>77.4471</td><td>77.8932</td><td>78.110 5</td><td>78.1806</td><td>77.7634</td><td>78.0532</td><td>79.7793</td><td>78.2814</td><td>77.673</td><td>77.8331</td></tr><tr><td>pima</td><td>80.7641</td><td>80.4503</td><td>79.882</td><td>80.3955</td><td>80.6635</td><td>80.9097</td><td>80.615</td><td>79.9737</td><td>79.9684</td><td>78.8061</td></tr><tr><td>Haberman Survival</td><td>67.0818</td><td>65.9427</td><td>62.830 8</td><td>65.1118</td><td>67.8659</td><td>70.0259</td><td>79.2072</td><td>84.6326</td><td>84.5817</td><td>84.5255</td></tr><tr><td>Wholesale customers</td><td>77.5154</td><td>79.6393</td><td>80.627 4</td><td>80.7162</td><td>80.4627</td><td>80.5324</td><td>80.5975</td><td>80.6997</td><td>80.5711</td><td>80.6230</td></tr><tr><td>Breast Cancer Coimbra</td><td>61.4583</td><td>58.4975</td><td>55.396</td><td>59.2451</td><td>63.5106</td><td>61.0724</td><td>61.2375</td><td>59.9638</td><td>59.2017</td><td>60.1415</td></tr><tr><td>Breast Cancer Wisconsin</td><td>89.5790</td><td>89.3284</td><td>88.650 3</td><td>89.5432</td><td>82.8911</td><td>58.3785</td><td>55.5739</td><td>55.7431</td><td>55.4139</td><td>55.3528</td></tr><tr><td>Indian Liver Patient</td><td>44.7730</td><td>48.7804</td><td>57.075</td><td>51.7715</td><td>57.2552</td><td>61.9700</td><td>60.0237</td><td>69.4509</td><td>70.6576</td><td>83.0750</td></tr><tr><td>abalone</td><td>49.8732</td><td>49.9642</td><td>50.164</td><td>51.0339</td><td>50.7563</td><td>51.8679</td><td>52.3452</td><td>53.1425</td><td>53.6105</td><td>53.5071</td></tr></table></body></html>

Table 3 F-measure corresponding to each dataset when the labeled instances set is $2 0 \%$   

<html><body><table><tr><td>Data</td><td>PUFC</td><td>Spy</td><td>Basic</td><td>Pruning</td></tr><tr><td>Banknote authentication</td><td>73.3377±4.3797</td><td>42.8554±4.5199</td><td>44.5258±7.3272</td><td>45.1275±7.9486</td></tr><tr><td>lonosphere</td><td>77.5766±7.4217</td><td>77.0215±6.9856</td><td>77.0226±8.8019</td><td>77.5504±5.0861</td></tr><tr><td>pima</td><td>80.5316±3.8007</td><td>67.8393±9.6371</td><td>74.8178±5.6586</td><td>75.5283±6.2065</td></tr><tr><td>Haberman Survival</td><td>84.5773±4.7251</td><td>40.4222±8.9044</td><td>42.7199±4.8383</td><td>42.1104±10.5274</td></tr><tr><td>Wholesale customers</td><td>80.5162±5.7551</td><td>80.4106±6.6747</td><td>80.2920±8.1469</td><td>80.3960±6.9866</td></tr><tr><td>Breast Cancer Coimbra</td><td>60.8730±18.7243</td><td>56.1534±19.1862</td><td>56.8126±17.2072</td><td>60.1249±15.1223</td></tr><tr><td>Breast Cancer Wisconsin</td><td>87.4444±4.7496</td><td>87.1651±5.4424</td><td>86.8066±8.5495</td><td>87.0548±6.0685</td></tr><tr><td>Indian Liver Patient</td><td>83.1898±3.7159</td><td>83.1542±4.0601</td><td>83.1342±4.2791</td><td>83.1061±4.5003</td></tr><tr><td>abalone</td><td>53.5474±1.7763</td><td>10.1553±2.7646</td><td>12.2736±4.5039</td><td>17.4083±5.0379</td></tr></table></body></html>

Table 4 F-measure corresponding to each dataset when the labeled instances set is $3 0 \%$   

<html><body><table><tr><td>Data</td><td>PUFC</td><td>Spy</td><td>Basic</td><td>Pruning</td></tr><tr><td>Banknote authentication</td><td>73.2512±5.9918</td><td>43.9693±5.8424</td><td>46.2228±7.5175</td><td>47.2304±6.7198</td></tr><tr><td>lonosphere</td><td>79.8883±5.7919</td><td>77.4390±8.2798</td><td>77.8232±8.4845</td><td>78.4424±6.3602</td></tr><tr><td>pima</td><td>80.6545±3.5522</td><td>76.5370±4.8736</td><td>78.5755±3.1937</td><td>79.3060±4.0949</td></tr><tr><td>Haberman Survival</td><td>84.5646±4.8638</td><td>47.4618±12.0583</td><td>50.4281±8.7767</td><td>50.4026±10.1718</td></tr><tr><td>Wholesale customers</td><td>80.7162±2.3700</td><td>80.5005±5.6913</td><td>80.4568±6.3885</td><td>80.5479±5.2578</td></tr><tr><td>Breast Cancer Coimbra</td><td>62.4385±9.5240</td><td>60.0509±13.3866</td><td>61.2411±11.3887</td><td>61.3631±15.3276</td></tr><tr><td>Breast Cancer Wisconsin</td><td>89.6980±5.3182</td><td>88.2327±5.5703</td><td>88.9063±5.7307</td><td>88.8687±5.2832</td></tr><tr><td>IndianLiverPatient</td><td>83.2162±2.9526</td><td>83.1440±4.1555</td><td>83.1612±3.9406</td><td>83.1260±4.3989</td></tr><tr><td>abalone</td><td>51.8046±6.5298</td><td>22.7847±5.2576</td><td>32.1086±4.5430</td><td>49.3723±5.0002</td></tr></table></body></html>

In addition,to gain a better understanding of our work,we add the number of labeled instances in the experimental process gradually. For instance,in Banknote authentication dataset,we tried a series of initial positive instances from $20 \%$ to $60 \%$ .Fig.2 illustrates the experimental results with different number oflabeled instances.It can be observed in the figure that the classification effect of the algorithm higher than comparison algorithms as a whole.However. the F-measure of PUFC algorithm has not been effectively improved due to the weak attribute correlation of dataset Wholesale customers or Indian Liver Patient.Another interesting observation from Fig.2 is that SPY、 Basic and Pruning are incapable to learn a suitable classifier,when the dataset Banknote authentication 、 Haberman Survival and abalone having few labeled instances for training.Its poor performance could be attributed to two main reasons: the great imbalance in the training sets( $20 \%$ or $30 \%$ labeled instances against $70 \%$ unlabeled instances),and the difficulty of capturing the diversity in content and style of dataset from a small number of instances.Look at dataset abalone again,when there are more labeled instances, the comparison algorithms show more effectual improvement rate. While PUFC can obtain more comprehensive data distribution information even when the amount of labeled instances is very small,and then the classification effect isrelatively stable when labeled instances are slightly increased.when the set of labeled instances are sufficient, the comparison algorithms also have strong expressiveness.

![](images/7e7af938bebcc2d5118cf7a36ca044cb114ccdd2f5d74fb5cf7010bb90a2e188.jpg)  
Figure.2.The relationship between the average clasification accuracy offour algorithms on nine datasets

# 5 Conclusions

Inreality, thenumberoflabeled dataisoftensmall,and there are a huge number of unlabeled data.In this paper,the problem of drawing lessons from positive and unlabeled instances is tackled by using a novel approach called PUFC.PUFC could achieve good performance when the labeled instances proportion in training set was low.As future work we aim at applying the novel PU-learning to cope with the problem of data multi-classification.

# ACKNOWLEDGMENTS

This work is supported by Chongqing Normal University 2018 research and innovation programme,under award number YKC.18025.

# REFERENCES

[1] Sansone E,De Natale FGB,Zhou ZH.Efficient Training for Positive Unlabeled Learning[J]. IEEE Transactions on Pattern Analysis & Machine Intelligence, 2016,38(7):99-113.DOI:10.1109/TPAMI.2018.2860995   
[2] Plessis MCD,Niu G,Sugiyama M.Class-prior estimation for learning from positive and unlabeled data[J].Machine Learning,2016,105(22):1-30.DOI: 10.1007/s10994-016-5604-6   
[3] Lan W,Wang J,Li M,et al.Predicting drug-target interaction using positiveunlabeled learning[J]. Neurocomputing, 2016,206(C):50-57.DOI: 10.1016/j.neucom.2016.03.080   
[4] Niu G,Plessis M C D,Sakai T,et al. Theoretical comparisons of positiveunlabeled learning against positive-negative learning[J].3Oth Conference on Neural Information Processing Systems,2016.   
[5] Yafeng R,Donghong J, Hongbin Z,et al. Deceptive Reviews Detection Based on Positive and Unlabeled Learning[J]．Journal of Computer Research& Development,2015,52(3):639-648.DOI:10.7544/issn1000-1239.2015.20131473   
[6] Nikdelfaz O,Jalili S.Disease genes prediction by HMM based PU-learning using gene expression profiles[J].Journal of Biomedical Informatics,2018,59(81):102- 111.DOI: 10.1016/j.jbi.2018.03.006   
[7] Xia R,Hu X,Lu J,et al. Instance selection and instance weighting for crossdomain sentiment classification via PU learning[J]. State Key Laboratory of Pattern Recognition, 2014:2176-2182. DOI: doi:http://espace.library.uq.edu.au/view/UQ:319543   
[8] He Z,Mei L,Yang Z,et al. Research of software fault prediction based on PU learning[D]. Northwest Agriculture and Forestry University,2015.   
[9] Hu H, Sha C,Wang X,et al.A unified framework for semi-supervised PU learning[J].World Wide Web-internet & Web Information Systems,2014, 17(4):493-510.DOI: 10.1007/s11280-013-0215-7   
[10] Liu B,Dai Y,LiX,et al.Building Text Classifiers Using Positive and Unlabeled Examples[C].IEEE Computer Society,2003.DOI:10.1109/ICDM.2003.1250918   
[11] Ott,M.,Cardie,C.,& Hancock,J.T.Negative Deceptive Opinion Spam[C]. Proceedings of the 20l3 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies,2013, 497-501.   
[12] Donato HF,Manuel M G,Paolo R,et al. Detecting positive and negative deceptiveopinionsusingPU-learning[J].InformationProcessing& Management,2015,51(4):433-443.DOI:10.1016/j.ipm.2014.11.001   
[13] Gan H, Sang N,Huang R,et al.Using clustering analysis to improve semisupervised classification[J]. Neurocomputing，2013,101(3):290-298.DOI: 10.1016/j.neucom.2012.08.020   
[14] Yin X,Shu T, Huang Q.Semi-supervised fuzzy clustering with metric learning and entropy regularization[J]. Knowledge-Based Systems,2012,35(15):304- 311.DOI: 10.1016/j.knosys.2012.05.016   
[15] Wang X Z,Xing HJ,LiY,etal.A study on relationship between generalization abilities and fuzziness of Base Classifiers in Ensemble Learning[J].IEEE Transactions on Fuzzy Systems，2014，5(23):1638-1654.DOI: 10.1109/TFUZZ.2014.2371479   
[16] Ashfaq R A R,Wang X Z, Huang J Z,et al. Fuzziness based semi-supervised learning approach for intrusion detection system[J].Information Sciences An International Journal,2017,378(C):484-497.DOI:10.1016/j.ins.2016.04.019   
[17] Wang X Z,Ashfaq R A R,Fu A M.Fuzziness based sample categorization for classifier performance improvement[J].Journal of Intelligent & Fuzzy Systems,2015,29(3):1185-1196.   
[18] Zadeh L A.Probability measures of Fuzzy events[J]. Journal of Mathematical Analysis&Applications, 1968，23(2):421-427.DOI: 10.1016/0022- 247X(68)90078-4   
[19] Ya L Z,Long FL,Jun Z,et al.POSTER:A PU Learning based System for Potential Malicious URL Detection[C].CCS '17 Proceedings of the 2017 ACM SIGSAC Conference on Computer and Communications Security,2017,2599- 2601.   
[20] Calvo B,Pedro Larrafiaga, José A.Lozano.Learning Bayesian classifiers from positiveand unlabeled examples[J].Pattern Recognition Letters,2007, 28(16):2375-2384.DOI: 10.1016/j.patrec.2007.08.003