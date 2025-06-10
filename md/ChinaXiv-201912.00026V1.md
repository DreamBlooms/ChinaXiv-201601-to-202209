# Spotting Macro- and Micro-expression Intervals in Long Video Sequences

Ying $\mathrm { H e ^ { 1 } }$ , Su-Jing $\mathrm { W a n g ^ { 1 } }$ , Jingting $\mathrm { L i ^ { \mathrm { 1 } } }$ and Moi Hoon Yap² 1 Key Laboratory of Behavior Sciences, Institute of Psychology, Chinese Academy of Sciences, Beijing, 100101, China ² Department of Computing and Mathematics, Manchester Metropolitan University, Manchester, M1 5GD, UK

Abstract-This paper presents baseline results for the Third Facial Micro-Expression Grand Challenge (MEGC2020).Both macro-and micro-expression intervals in $\mathbf { C A S ( M E ) } ^ { 2 }$ and SAMMLong Videos are spotted by employing the method of Main DirectionalMaximalDifferenceAnalysis(MDMD).TheMDMD method uses the magnitude maximal difference in the main direction of optical flow features to spot facial movements. The single frame prediction results of the original MDMD method are post processed into reasonable video intervals. The metric F1-scores of baseline results are evaluated:for $\mathbf { C A S ( M E ) } ^ { 2 }$ ，the F1-scores are 0.1196 and 0.0082 for macroand micro-expressions respectively,and the overall F1-score is 0.0376;for SAMM Long Videos, the F1-scores are 0.0629 and 0.0364 for macro- and micro-expressions respectively,and the overall F1-score is O.0445.The baseline project codes is publicly available at https: //github.com/HeyingGithub/ Baseline-project-for-MEGC2020_spotting.

# I．INTRODUCTION

Facial expressions are important non-verbal cues that convey emotions.Macro-expressions are the common facial expressions in our daily life,which are the types we usually know.There is a special type of expressions called“microexpressions”that were first found by Haggard and Isaacs [5]. Micro-expressions(MEs）are involuntary facial movements occurring spontaneously when a person attempts to conceal the experiencing emotion in a high-stakes environment. The duration of MEs is very short. The general duration is less than 50O milliseconds (ms）[21],[1O]. The close connection between MEs and deception makes the relevant research have great significance on many applications such as medical care [3] and law enforcement [4].

Spotting expressions is to find the moment when expressions occurs in the whole video sequences.In the Second Micro-Expression Spotting Challenge (MEGC 2019）[14], methods for spotting ME intervals in long videoswere explored [7].In the past decades,several explorations for spotting MEs have been done [12],[20],[18],[17],[16], [24],[9],[19],[8],[11].However,MEsare often accompanied by macro-expressions,and both of the two types of expressionsare valuable for affect analysis.Therefore,developing methods to spot both macro- and micro-expressions is the main theme of MEGC 2020.

In this paper, we provide the baseline method and results for the Third Facial Micro-Expression Grand Challenge (MEGC 202O)，spotting macro- and micro-expression intervals in long video sequences from the dataset CAS(ME)2 and SAMM Long Videos. The main method is the Main

Directional Maximal Difference Analysis(MDMD)[19]. The original MDMD only predicts whether a frame belongs to facial movements.To obtain target intervals,the adja cent frames consistently predicted to be macro- or microexpressions form an interval,and the intervals that are too long or too short are removed.Parameters are adjusted to specific expression types for specific datasets.The performance metric,F1-scores,is used for the evaluation on the two long video datasets.

The rest of paper is organized as follows: Section II presents the methodology and performance metrics. Section III introduces the detailed experiment results. Section IV concludes the paper.

# II.METHODOLOGY

This section describes the benchmark datasets,the baseline method,and the performancemetrics.

# A. Datasets

$\mathbf { C A S ( M E ) ^ { 2 } }$ [13]: In the part A of $\mathrm { C A S ( M E ) ^ { 2 } }$ database, there are 22 subjects and 98 long videos.The facial movements are classified as macro- and micro-expressions. The video samples may contain multiple macro or micro facial expressions.The onset,apex,offset index for these expressions are given in the excel file.In addition,the eye blinks are labeled with onset and offset time.

SAMM Long Videos [22] : The original SAMM dataset [2] contains 159 micro-expressions,which was used for the past two micro-expressions recognition challenge [23], [14]. Recently, the authors [22] released the SAMMLong Videos dataset,which consists of 147 long videos.There are 343 macro-movements and 159 micro-movements in the long videos.The index of onset,apex and offset frames of microand macro-movements are outlined in the ground truth excel file.

More detailed and comparative information of these two datasets is presented in Table I.

# B.Baseline method

1）Preprocess:Expression spotting focuses on facial regions. So we preprocess every video sample by cropping and resizing facial regions in all frames.For each video, we locate the rectangular box that exactly bounds facial regions in the first frame,and then all the frames of the video are cropped and resized according to the box located in the first frame.We locate the bounding box according to facial landmarks detected by the corresponding function in the "Dlib” toolkit [6],as we found that applying a face detecting algorithm directly cannot behavior very well. The preprocess details are as follows.

TABLEI A COMPARISON BETWEEN CAS $( \mathrm { M E } ) ^ { 2 }$ AND SAMMLONG VIDEOS.   

<html><body><table><tr><td>Dataset</td><td>CAS(ME)2</td><td>SAMMLong Videos</td></tr><tr><td>Participants</td><td>22</td><td>32</td></tr><tr><td>Videosamples</td><td>98</td><td>147</td></tr><tr><td>Macro-expressions</td><td>300</td><td>343</td></tr><tr><td>Micro-expressions</td><td>57</td><td>159</td></tr><tr><td>Resolution</td><td>640×480</td><td>2040×1088</td></tr><tr><td>FPS</td><td>30</td><td>200</td></tr></table></body></html>

Firstly,we use the landmark detecting function in the "Dlib” toolkit to obtain 68 facial landmarks on the face in the first frame of the video,as illustrated in the Fig. 1(a)- the first frame of s23_0102 in $\mathrm { C A S ( M E ) ^ { 2 } }$ ．The landmarks are marked as $L _ { 1 } , L _ { 2 } , \cdots , L _ { 6 8 }$ in the sequence of the list returned by the landmark detecting function in "Dlib"，and the corresponding coordinates are marked as $( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , \cdot \cdot \cdot , ( x _ { 6 8 } , y _ { 6 8 } )$ . The coordinate system is consistent with the one in the OpenCV toolkit [1],i.e.Xaxis means the horizontal direction from left to right,and y-axis means the vertical direction from top to bottom. The green dots in Fig.1(a) are the landmarks,and some of the serial numbers aremarkedbythered text.

Secondly,in order to form a rectangular box that bounds the facial region exactly, the leftmost,rightmost,topmost and bottommost landmarks are marked as $L _ { l } , L _ { r } , L _ { t } , L _ { b }$ with coordinates $( x _ { l } , y _ { l } ) , ( x _ { r } , y _ { r } ) , ( x _ { t } , y _ { t } ) , ( x _ { b } , y _ { b } )$ ，respectively.Rather than forming the box directly according to $L _ { l } , L _ { r } , L _ { t } , L _ { b }$ ，we form two points: $A ( x _ { l } , y _ { t } \textrm { -- } ( y _ { 3 7 } \textrm { -- }$ $y _ { 1 9 } )$ ） $, B ( x _ { r } , y _ { b } )$ to obtain the box $\mathbf { B }$ with $A$ as the upper left corner and $B$ as the lower right corner. The coordinate $y _ { t } - ( y _ { 3 7 } - y _ { 1 9 } )$ means that the upper edge of the box is moved up a relative distance to maintain more regions around eyebrows.In Fig.1(a),the box $\mathbf { B }$ is illustrated by the blue rectangular.

Thirdly,as shown by Fig.1(b),which is the region in B,we found there are too many regions in the bottom for several subjects in the two datasets because of the inaccuracy of landmark detecting,and so,we detect landmarks again on the region of the first frame in $\mathbf { B }$ for cropping faces more precisely.It is shown in the Fig. 1(c). Then,we get a new bottommost landmark $L _ { b } ^ { \prime } ( x _ { b } ^ { \prime } , y _ { b } ^ { \prime } )$ ： $B$ is updated to $B ^ { \prime } ( x _ { r } , y _ { m i n } )$ ，where $y _ { m i n }$ is the smaller one of $y _ { b }$ and $y _ { b } ^ { \prime }$ Then a new rectangular box $\mathbf { B } ^ { \prime }$ is formed with $A$ as the upper left corner and $B ^ { \prime }$ as the lower right corner. In Fig.1(c), the box $\mathbf { B } ^ { \prime }$ is illustrated by the blue rectangular. And the region of the first frame in $\mathbf { B } ^ { \prime }$ is illustrated in Fig.1(d),in which we can find that the facial region is located better.

Finally,after obtaining the box $\mathbf { B } ^ { \prime }$ ，we crop all the frames of the video in the rectangular box $\mathbf { B } ^ { \prime }$ ,and thus get the facial regions.The cropped regions are then resized to the size of $2 2 7 \times 2 2 7$ ：

2）MDMD:The method of Main Directional Maximal Difference Analysis (MDMD） is proposed in the literature [19]. The main idea is that: when an expression happens, the face will experience a process of producing an expression and returning to a neutral face.The main movement directions will be opposite in the process.By analyzing it, expressions can be spotted.Here we review the MDMD method.

Givenavideowith $n$ frames,the current frame is denoted as $F _ { i }$ ： $F _ { i - k }$ is the $k$ -th frame before the $F _ { i }$ ，and $F _ { i + k }$ is the $k$ -th frame after the $F _ { i }$ . The robust local optical flow (RLOF)[15] between the $F _ { i - k }$ frame(Head Frame) and the $F _ { i }$ frame(Current Frame) is computed.We denote the optical flow by $( u ^ { H C } , v ^ { H C } )$ . For convenience, $( u ^ { H C } , v ^ { H C } )$ means the displacement of any point. Similarly, the optical flow between the $F _ { i - k }$ frame(Head Frame) and the $F _ { i + k }$ frame (Tail Frame) is denoted by $( u ^ { H T } , v ^ { H T } )$ . Then, $( u ^ { H C } , v ^ { H C } )$ （204号 and $( u ^ { H T } , v ^ { H T } )$ are converted from Euclidean coordinates to polar coordinates $( \rho ^ { H C } , \theta ^ { H C } )$ and $( \rho ^ { H T } , \theta ^ { H T } )$ ，where $\rho$ and $\theta$ represent, respectively, the magnitude and direction.

Based on the directions $\{ \dot { \theta } ^ { H C } \}$ , all the optical flow vectors $\{ ( \rho ^ { H C } , \theta ^ { H C } ) \}$ are divided into $a$ directions. Fig.2 illustrates the condition when $a = 4$ .The Main Direction $\Theta$ is the direction that has the largest number of optical flow vectors among the $( \rho _ { M } ^ { H C } , \theta _ { M } ^ { H C } )$ $a$ is the optica flow vector directions.The main directional optical vector $( \rho ^ { H C } , \theta ^ { H C } )$ that falls in theMainDirection

![](images/66987f8af52985447a3749ea130a761ec5ed34b5727eaf203871a02fd66bc739.jpg)  
Fig.2.Four directions in the polar coordinates.

$$
\{ ( \rho _ { M } ^ { H C } , \theta _ { M } ^ { H C } ) \} = \{ ( \rho ^ { H C } , \theta ^ { H C } ) | \theta ^ { H C } \in \Theta \}
$$

The opticalflowvector_corresponding to $( \rho _ { M } ^ { H C } , \theta _ { M } ^ { H C } )$ between $F _ { i - k }$ frame and $F _ { i + k }$ is denoted as $( \rho _ { M } ^ { H T } , \theta _ { M } ^ { H T } )$

$$
\begin{array} { r l } & { \{ ( \rho _ { M } ^ { H T } , \theta _ { M } ^ { H T } ) \} = \{ ( \rho ^ { H T } , \theta ^ { H T } ) | ( \rho ^ { H T } , \theta ^ { H T } ) \ \mathrm { a n d } \ ( \rho _ { M } ^ { H C } , \theta _ { M } ^ { H C } ) } \\ & { \mathrm { a r e ~ t w o ~ d i f f e r e n t ~ v e c t o r s ~ o f ~ t h e ~ s a m e ~ p o i n t ~ i n ~ } F _ { i - k } \} } \\ & { \quad \curvearrowright } \end{array}
$$

After the differences $\rho _ { M } ^ { H C } - \rho _ { M } ^ { H T }$ is sorted into a descending order, the maximal difference $d ^ { i }$ is defined as the mean difference value of the first 1/3 of the differences pMC $\rho _ { M } ^ { H C } - \rho _ { M } ^ { H T }$ to characterize the frame $F _ { i }$ as in the formula:

$$
d = \frac { 3 } { g } \sum \operatorname* { m a x } _ { \frac { g } { 3 } } \{ \rho ^ { H C } - \rho ^ { H T } \}
$$

![](images/5e714c3853adc59065847fd28df38250277448ff04a6153858960dde8b6d0d6b.jpg)  
Fig.1Digafoiiepoigtp:dcialksdhctaa;(io$\mathbf { B }$ ； (c)detect facial landmarks in the region in $\mathbf { B }$ and form the rectangular box $\mathbf { B } ^ { \prime }$ ； (d) the region in $\mathbf { B } ^ { \prime }$ ：

where $g = | \{ ( \rho ^ { H C } , \theta ^ { H C } ) \} |$ is the number of elements in the subset $\{ ( \rho ^ { H C } , \theta ^ { H C } ) \}$ ,and $\operatorname* { m a x } _ { m } S$ denotes a set comprised of the first $m$ maximal elements in the subset $S$

Since our method is a block-based analysis,the cropped facial region of each frame is divided into $\mathbf { \boldsymbol { b } } \times \mathbf { \boldsymbol { b } }$ blocks，as shown in Fig.3.And we calculate the maximal difference $d _ { j } ^ { i } ( j = 1 , 2 , \cdot \cdot \cdot , b ^ { 2 } ) _ { - }$ for each block in the $F _ { i }$ frame.For frame $F _ { i }$ , there are $b ^ { 2 }$ maximal differences $d _ { j } ^ { i }$ due to the $\mathbf { \boldsymbol { b } } \times \mathbf { \boldsymbol { b } }$ block structure. Then, we arrange the $b ^ { 2 }$ maximal differences $d _ { j } ^ { i }$ in a descending order where $\bar { d } ^ { i }$ is the first $s$ maximal difference and characterizes the frame $F _ { i }$ feature:

$$
\bar { d } ^ { i } = \frac { 1 } { s } \sum \operatorname* { m a x } _ { s } \{ d _ { j } ^ { i } \} , j = 1 , 2 , \cdot \cdot \ , b ^ { 2 }
$$

![](images/deaf42788ed6803115fb3e617614e05b904d981799021fc3dc9f1a97124820a4.jpg)  
Fig.3.Examplesof facial $6 \times 6$ block structure.

offset frame after $F _ { i + k }$ ，which is presented in Fig.4(b).In this case,the $\bar { d } ^ { i }$ value will also be small if $k$ is set to be a small value.However, $k$ cannot be set as a large value because this would influence the accuracy of the computing optical flow.

If a person maintained a neutral expression at $F _ { i - k }$ ,her/his emotional expression，such as disgust,starts at the onset frame between $F _ { i - k }$ and $F _ { i }$ ,is repressed at the offset frame between $F _ { i }$ and $F _ { i + k }$ ,and then the facial expression recovers a neutral expression at $F _ { i + k }$ ,which is presented in Fig.4(a). In this circumstance, the movement between $F _ { i }$ and $F _ { i - k }$ is more intense than the movement between $F _ { i + k }$ and $F _ { i - k }$ because the expression is neutral at both $F _ { i + k }$ and $F _ { i - k }$ Therefore,the ${ \bar { d } } ^ { i }$ value will be large.Another situation is that a person maintains a neutral expression from $F _ { i - k }$ to $F _ { i + k }$ . The movement between $F _ { i }$ and $F _ { i - k }$ is similar to the movement between $F _ { i + k }$ and $F _ { i - k }$ ; thus,the $\bar { d } ^ { i }$ value will be small.In a long video,sometimes an emotional expression starts at the onset frame before $F _ { i - k }$ and is repressed at the

We employed a relative difference vector for eliminating the background noise,which was computed by:

$$
r ^ { i } = \overline { { d } } ^ { i } - \frac { 1 } { 2 } \left( \overline { { d } } ^ { i - k + 1 } + \overline { { d } } ^ { i + k - 1 } \right) , i = k + 1 , k + 2 , \cdots , n - k
$$

Therefore,the frame $F _ { i }$ is characterized by $r ^ { i }$ .A threshold is used to obtain the frames that have peaks representing the facial movements in a video:

$$
t h r e s h o l d = r _ { m e a n } + p \times \left( r _ { m a x } - r _ { m e a n } \right)
$$

where

$$
r _ { m e a n } = \frac { 1 } { n - 2 k } \sum _ { n - k } ^ { i = k + 1 } r ^ { i } \mathrm { a n d } r _ { m a x } = \operatorname* { m a x } _ { n - k } ^ { i = k + 1 } r ^ { i } .
$$

$p$ isa variable parameter in the range $[ 0 , 1 ]$ .The frames with $r ^ { i }$ larger than the threshold are the frames where expressions appear.

3)Parameter settings and post process: In the literature [19],several parameter combinations are explored to spot micro-expressions on the $\mathrm { C A S ( M E ) ^ { 2 } }$ dataset. For spotting both macro- and micro-expressions on the two datasets for MEGC 2020, i.e. $\mathrm { C A S ( M E ) ^ { 2 } }$ and SAMM Long Videos,we select the best combination of blocks and directions explored in [19].and we set other parameters according the FPSs of the two datasets.Moreover, since the original MDMD only predicts whether a frame belongs to facial movements,a post process is added in order to output target intervals required by MEGC 2020. The details are as follows.

The number of blocks is set to $6 \times 6$ and the number of directions $a$ is set to 4. In $\mathrm { C A S ( M E ) ^ { 2 } }$ dataset,the $k$ is set to 12 for micro-expressions，and 39 for macroexpressions；in SAMM Long Videos dataset, the $k$ is set to 80 for micro-expressions,and 26o for macro-expressions. Concerning the threshold, $p$ varies from 0.01 to 0.99 with a step-size of O.O1.And the final results are reported under the setting of $p = 0 . 0 1$ . The original MDMD only predicts whether a frame belongs to facial movements.To output target intervals,the adjacent frames consistently predicted to be macro- or micro-expressions form an interval,and the intervals that are too long or too short are removed. The number of micro-expression frames is limited between 7 and 16 for the $\mathrm { C A S ( M E ) ^ { 2 } }$ dataset,and between 47 and 105 for the SAMM Long Videos dataset. The number of macro-expression frames is defined as larger than 16 for the $\mathrm { C A S ( M E ) ^ { 2 } }$ dataset, and larger than 1O5 for the SAMM Long Videos dataset.

![](images/c3ab05fee6a705211804b73a16def82c6b118c79c13a6636de2a3df7ceb75a74.jpg)  
Fig.4.Two situations: (a) An emotional expression starting at the onset frame between $F _ { i - k }$ and $F _ { i }$ is repressed at the offset frame between $F _ { i }$ and $F _ { i + k }$ and recovers a neutral expression at $F _ { i + k }$ ；(b)An emotional expression starting at the onset frame before $F _ { i - k }$ is repressed at the offset frame after Fi+k·

# C. Performance metrics

In order to avoid the inaccuracy caused by annotation, we propose to evaluate the spotting result per interval in MEGC 2020.

# 1.True positive in one video definition

The true positive(TP) per interval in one video is frst defined based on the intersection between the spotted interval and the ground-truth interval. The spotted interval $W _ { s p o t t e d }$ is considered as TP if it fits the following condition:

$$
\frac { W _ { s p o t t e d } \cap W _ { g r o u n d T r u t h } } { W _ { s p o t t e d } \cup W _ { g r o u n d T r u t h } } \ge k
$$

where $k$ is set to 0.5, $W _ { g r o u n d T r u t h }$ represents the ground truth of the macro- or micro-expression interval (onsetoffset).If the condition is not fulfilled, the spotted interval is regarded as false positive (FP).

# 2.Result evaluation in one video

Supposing there are $m$ ground truth interval in the video, and $n$ intervals are spotted.According to the overlap evaluation, the TP amount in one video is counted as $a$ （ $\overset { \cdot } { \underset { \cdot } { a } } \leq m$ and $a \leq n ,$ ，therefore $\mathrm { F P } = n - a$ ， $\mathrm { F N } = m - a$ .The spotting performance in one video can be evaluated by following metrics:

$$
R e c a l l = \frac { a } { m } , \ P r e c i s i o n = \frac { a } { n }
$$

$$
F - s c o r e = { \frac { 2 T P } { 2 T P + F P + F N } } = { \frac { 2 a } { m + n } }
$$

Yet, the videos in real life have some complicated situations which influences the evaluation per single video:

·There might be no macro- nor micro-expression in the test video.In this case, $\textit { m } = \mathrm { ~ 0 ~ }$ ，the denominator of recall would be zeros.   
· If there is no spotted intervals in the video, the denominator of precision would be zeros since $n = 0$ ：   
· It is impossible to compare two spotting methods when both TP amounts are zero.The metric (recall, precision or F1-score） values both equal to zeros.However, the Methodi outperforms $\mathrm { { M e t h o d } _ { 2 } }$ ，if Methodi spots less intervals than $\mathrm { \bf M e t h o d _ { 2 } }$ ：

Thus, to avoid these situations,we propose for single video spotting result evaluation,we just note the amount of TP,FP andFN. Other metrics are not considered for one video.

# 3.Evaluation for entire database

Supposing in the entire dataset,

·There are $V$ videos including $M _ { 1 }$ macro-expressions   
He $M _ { 2 }$ $\begin{array} { r } { M _ { 1 } = \sum _ { i = 1 } ^ { V } m _ { 1 i } } \end{array}$ $\begin{array} { r } { M _ { 2 } = \sum _ { i = 1 } ^ { V } m _ { 2 i } } \end{array}$ $N _ { 1 }$ $N _ { 2 }$ in total, where $\textstyle N _ { 1 } = \sum _ { i = 1 } ^ { V } n _ { 1 i }$ and $\textstyle N _ { 2 } { \bar { = } } \sum _ { i = 1 } ^ { V } n _ { 2 i }$ .   
·There are $A _ { 1 }$ TPs for MaE and $A _ { 2 }$ TPs for ME in total, where $\textstyle A _ { 1 } = \sum _ { i = 1 } ^ { V } a _ { 1 i }$ and $\textstyle A _ { 2 } = \sum _ { i = 1 } ^ { V } a _ { 2 i }$ ：

The dataset could be considered as one long video.The results are firstly evaluated for the MaE spotting and ME spotting separately. Then the overall result for macro- and micro spotting is evaluated. The recall and precision for entire dataset can be calculated by following formulas:

·for macro-expression: $R e c a l l _ { M a E . D } = \frac { A _ { 1 } } { M _ { 1 } } \ P r e c { i s i o n } _ { M a E . D } = \frac { A _ { 1 } } { N _ { 1 } }$   
·for micro-expression: $R e c a l l _ { M E . D } = \frac { A _ { 2 } } { M _ { 2 } } \ P r e c { i s i o n _ { M E . D } } = \frac { A _ { 2 } } { N _ { 2 } }$ (   
，foroverall evaluation: $R e c a l l _ { D } = \frac { A _ { 1 } + A _ { 2 } } { M _ { 1 } + M _ { 2 } } \ P r e c { i s i o n _ { D } } = \frac { A _ { 1 } + A _ { 2 } } { N _ { 1 } + N _ { 2 } }$

Then, the values of $F l$ -score for all these three evaluations are obtained based on:

$$
F 1 - s c o r e = \frac { 2 \times ( R e c a l l \times P r e c i s i o n ) } { R e c a l l + P r e c i s i o n }
$$

The champion of the challenge will be the best score for overall results in spotting micro- and macro-expressions.

# III.RESULTS AND DISCUSSION

For the parameter $p$ ,we have studied the evaluation results by varying $p$ from O.01 to O.99 with step-size of O.01,and the 20 resultsfrom O.O1 to O.2O are shownin TableII.In Table II, we list the information of TPs and F1-scores for macro- and micro-expression spotting respectively. We observe that, for both types of expressions in the two datasets,the number of TP is decreasing with the increase of $p$ .Regarding the F1-score, it also shows a decreasing trend in SAMM Long Videos.Yet, in $\mathrm { C A S ( M E ) ^ { 2 } }$ , the F1-score increases at first and then begins to decrease.The initial increase of the F1-score in $\mathrm { C A S ( M E ) ^ { 2 } }$ is mainly because the number of the totally predicted intervals $( n )$ become smaller with the increase of $p$ ，making the precision $( a / n )$ increase.

Since the amount of TP is an important metric for the spotting result evaluation,we select the results under the condition of $p ~ = ~ 0 . 0 1$ as the final baseline results.The details of the final baseline results for spotting macro- and micro-expressions are shown in Table III.For $\mathrm { C A S ( M E ) ^ { 2 } }$ the F1-scores are O.1196 and O.0o82 for macro- and microexpressions respectively,and O.O376 for overall result.For SAMM Long Videos,the F1-scores are O.0629 and 0.0364 for macro- and micro-expressions respectively,and 0.0445 for overall result.More details about the number of true labels,TP,FP,FN,precision, recall andF1-score forvarious situations are shown in the Table III.

# IV.CONCLUSIONS

This paper addresses the challenge in spotting macro- and micro-expressions in long video sequence,and provides the baseline method and results for the ThirdFacial Micro Expression Spotting Challenge (MEGC 202O). The Main Directional Maximal Difference Analysis (MDMD)[19]is employed as the baseline method,and the parameter settings are adjusted to $\mathrm { C A S ( M E ) ^ { 2 } }$ and SAMM Long Videos for the spotting challenge in MEGC 2O2O. Slight modification are done to predict more reasonable intervals on the postprocessing of results.Experiments were done and the predicted results were evaluated using the metrics in MEGC 2020.The results have shown that the MDMD method can produce reasonable performance,but there are still a huge challenge to reduce the amount of FPs.

# REFERENCES

[1]G.Bradski．The OpenCV Library．Dr.Dobb's Journal of Software Tools,2000. [2]A.K.Davison,C.Lansley,N.Costen,K.Tan,and M.H.Yap.SAMM: Aspontaneous micro-facial movement dataset.IEEE Transactions on Affective Computing,9(1):116-129,2018. [3]J.Endres and A.Laidlaw. Micro-expression recognition training in medical students:a pilot study.BMC Medical Education,9(1):47, 2009.   
[4] M.Frank, D. Kim, S. Kang,A. Kurylo,and D. Matsumoto. Improving the ability to detect micro expressions in law enforcement officers. 2014.   
[5] E.A. Haggard and K. S. Isaacs. Micromomentary facial expressions as indicators_of ego mechanisms in psychotherapy.In Methods of Research in Psychotherapy,pages 154-i65.1966. [6]D.E.King.Dlib-ml:A machine learning toolkit.Journal of Machine Learning Research,10(3):1755-1758,2009. [7]J.Li,C.Soladie,R.Sguier,S.Wang,and M.H. Yap．Spotting micro-expressions on long videos sequences.In IEEE International Conference on Automatic Face and Gesture Recognition, pages 1-5, 2019.   
[8] X.Li,X.Hong,A.Moilanen,X.Huang,T.Pfister,G.Zhao,and M.Pietikäinen.Towards reading hidden emotions:A comparative study of spontaneous micro-expression spoting and recognition methods.IEEE Transactions on Affective Computing,9(4):563-577,2018. [9]S.-T.Liong, J. See,K.Wong,A. C.Le Ngo,Y.-H. Oh,andR.Phan. Automatic apex frame spotting in micro-expression database.In IAPR Asian Conference on Pattern Recognition,pages 665-669,2015.   
[10]D.Matsumoto and H.S.Hwang.Evidence for training the ability to read microexpressions of emotion.Motivation and Emotion, 35(2):181-191, 2011.   
[11] A.Moilanen,G. Zhao,and M.Pietikainen．Spotting rapid facial movements from videos using appearance-based feature difference analysis. In International Conference on Pattern Recognition,pages 1722-1727,2014.   
[12]S.Polikovsky,Y. Kameda,and Y. Ohta．Facial micro-expression detection in hi-speed video based on facial action coding system (FACS).IEICE Transactions on Information and Systems,96(i):81- 92,2013.   
[13]F.Qu,S.J.Wang,W.J.Yan,H.Li, S.Wu,and X.Fu.CAS(ME)²: A database for spontaneous macro-expression and micro-expression spotting and recognition. IEEE Transactions on Affective Computing, 9(4):424-436,2017.   
[14]J.See,M.H. Yap,J.Li,X.Hong,and S.-J.Wang.MEGC 2019 the second facial micro-expressions_grand challenge.In IEEE International Conference on Automatic Face and Gesture Recognition, pages 1-5,2019.   
[15] T.Senst,V.Eiselein,and T. Sikora．Robust local optical flow for feature tracking.22(9):1377-1387,2012.   
[16] M.Shreve,J.Brizzi，S.Fefilatyev,T.Luguev,D.Goldgof,and S. Sarkar.Automatic expression spotting in videos.Image Vision Computing,32(8):476-486,2014.   
[17]M.Shreve,S.Godavarthy,D.Goldgof,and S.Sarkar.Macro- and micro-expression spoting in long videos using spatio-temporal strain. In IEEE International Conference on Automatic Face and Gesture Recognition,pages 51-56,2011.   
[18]M.Shreve,S.Godavarthy,V.Manohar,D.Goldgof,and S.Sarkar. Towards macro-and micro-expression spotting in video using strain patterns.In Workshop on ApplicationsofComputer Vision,pages $^ { 1 - }$ 6,2009.   
[19]S.-J.Wang,S.Wu,X.Qian, J.Li,and X.Fu.A main directional maximal difference analysis for spotting facial movements from longterm videos. Neurocomputing,230:382-389,2017.   
[20]Q.Wu,X. Shen,and X.Fu. The machine knows what you are hiding: an automatic micro-expression recognition system.In International Conference on Affective Computing and Intelligent Interaction,pages 152-162, 2011.   
[21]W.-J.Yan,Q.Wu,J.Liang,Y.-H.Chen,and X.Fu.How fast are the leaked facial expressions:The duration of micro-expressions.Journal ofNonverbal Behavior,37(4):217-230,2013.   
[22]C.H.Yap，C.Kendrick,and M.H. Yap. Samm long videos: A spontaneous facial micro-and macro-expressions dataset.arXiv preprint arXiv:1911.01519,2019.   
[23]M.H.Yap,J. See,X.Hong,and S.-J.Wang.Facial micro-expressions grand challenge 2018 summary.In 2018 13th IEEE International Conference on Automatic Face& Gesture Recognition (FG 2018), pages 675-678.IEEE,2018.   
[24] Z. Zhang,T.Chen,H.Meng,G.Liu,and X.Fu.SMEConvNet:A convolutional neural network for spotting spontaneous facial microexpression from long videos.IEEE Access,6:71143-71151,2018.

TABLE II BASELINE RESULTS IN CAS $( \mathrm { M E } ) ^ { 2 }$ AND SAMM LONG VIDEOS WITH $p$ VARYING FROM 0.01 TO 0.20 WITH AN STEP-SIZE OF 0.01.   

<html><body><table><tr><td>Dataset</td><td colspan="4">CAS(ME)2</td><td colspan="4">SAMMLong Videos</td></tr><tr><td>Expression</td><td colspan="2">macro-expression</td><td colspan="2">micro-expression</td><td colspan="2">macro-expression</td><td colspan="2">micro-expression</td></tr><tr><td>p(%)</td><td>TP</td><td>F1-score</td><td>TP</td><td>F1-score</td><td>TP</td><td>F1-score</td><td>TP</td><td>F1-score</td></tr><tr><td>1</td><td>109</td><td>0.1196</td><td>21</td><td>0.0082</td><td>22</td><td>0.0629</td><td>29</td><td>0.0364</td></tr><tr><td>2</td><td>107</td><td>0.1408</td><td>18</td><td>0.0093</td><td>20</td><td>0.0627</td><td>25</td><td>0.0356</td></tr><tr><td>3</td><td>96</td><td>0.1455</td><td>15</td><td>0.0100</td><td>18</td><td>0.0627</td><td>19</td><td>0.0309</td></tr><tr><td>4</td><td>92</td><td>0.1573</td><td>14</td><td>0.0115</td><td>16</td><td>0.0588</td><td>17</td><td>0.0306</td></tr><tr><td>5</td><td>91</td><td>0.1738</td><td>12</td><td>0.0121</td><td>16</td><td>0.0626</td><td>14</td><td>0.0282</td></tr><tr><td>6</td><td>88</td><td>0.1857</td><td>10</td><td>0.0120</td><td>14</td><td>0.0574</td><td>11</td><td>0.0245</td></tr><tr><td>7</td><td>81</td><td>0.1879</td><td>10</td><td>0.0142</td><td>12</td><td>0.0510</td><td>11</td><td>0.0266</td></tr><tr><td>8</td><td>74</td><td>0.1876</td><td>8</td><td>0.0131</td><td>10</td><td>0.0443</td><td>9</td><td>0.0239</td></tr><tr><td>9</td><td>73</td><td>0.1984</td><td>8</td><td>0.0155</td><td>9</td><td>0.0407</td><td>7</td><td>0.0201</td></tr><tr><td>10</td><td>68</td><td>0.1954</td><td>8</td><td>0.0176</td><td>8</td><td>0.0371</td><td>7</td><td>0.0214</td></tr><tr><td>11</td><td>61</td><td>0.1863</td><td>6</td><td>0.0150</td><td>8</td><td>0.0378</td><td>7</td><td>0.0228</td></tr><tr><td>12</td><td>61</td><td>0.2013</td><td>6</td><td>0.0173</td><td>8</td><td>0.0382</td><td>7</td><td>0.0245</td></tr><tr><td>13</td><td>57</td><td>0.1949</td><td>6</td><td>0.0190</td><td>7</td><td>0.0337</td><td>6</td><td>0.0219</td></tr><tr><td>14</td><td>56</td><td>0.2007</td><td>6</td><td>0.0214</td><td>7</td><td>0.0340</td><td>6</td><td>0.0227</td></tr><tr><td>15</td><td>50</td><td>0.1859</td><td>5</td><td>0.0197</td><td>6</td><td>0.0299</td><td>5</td><td>0.0200</td></tr><tr><td>16</td><td>50</td><td>0.1927</td><td>5</td><td>0.0214</td><td>6</td><td>0.0301</td><td>5</td><td>0.0210</td></tr><tr><td>17</td><td>48</td><td>0.1886</td><td>5</td><td>0.0236</td><td>6</td><td>0.0304</td><td>5</td><td>0.0222</td></tr><tr><td>18</td><td>46</td><td>0.1855</td><td>5</td><td>0.0253</td><td>6</td><td>0.0305</td><td>4</td><td>0.0183</td></tr><tr><td>19</td><td>43</td><td>0.1795</td><td>5</td><td>0.0275</td><td>6</td><td>0.0310</td><td>3</td><td>0.0146</td></tr><tr><td>20</td><td>42</td><td>0.1783</td><td>3</td><td>0.0179</td><td>6</td><td>0.0313</td><td>3</td><td>0.0152</td></tr></table></body></html>

TABLE III BASELINE RESULTS FOR MACRO-AND MICRO-SPOTTING ( ${ \bf \dot { \boldsymbol { p } } } = 0 . 0 1 \dot { \bf \Omega } ,$ IN CAS(ME)² AND SAMMLONG VIDEOS.   

<html><body><table><tr><td>Dataset</td><td colspan="3">CAS(ME)2</td><td colspan="3">SAMMLongVideos</td></tr><tr><td>Expression</td><td>macro-expression</td><td>micro-expression</td><td>overall</td><td>macro-expression</td><td>micro-expression</td><td>overall</td></tr><tr><td>Total number</td><td>300</td><td>57</td><td>357</td><td>343</td><td>159</td><td>502</td></tr><tr><td>TP</td><td>109</td><td>21</td><td>130</td><td>22</td><td>29</td><td>51</td></tr><tr><td>FP</td><td>1414</td><td>5014</td><td>6428</td><td>334</td><td>1407</td><td>1741</td></tr><tr><td>FN</td><td>191</td><td>36</td><td>335</td><td>314</td><td>130</td><td>451</td></tr><tr><td>Precision</td><td>0.0716</td><td>0.0042</td><td>0.0198</td><td>0.0618</td><td>0.0202</td><td>0.0285</td></tr><tr><td>Recall</td><td>0.3633</td><td>0.3684</td><td>0.3641</td><td>0.0641</td><td>0.1824</td><td>0.1016</td></tr><tr><td>F1-score</td><td>0.1196</td><td>0.0082</td><td>0.0376</td><td>0.0629</td><td>0.0364</td><td>0.0445</td></tr></table></body></html>