# Using associative neural network to interpret syndromes of Traditional Chinese Medicine

Guacheng Xi, Jianxin Chen, Jianqiang Yi, Member, IEEE,Dongbin Zhao, and Yongyan Wang

Abstract—Millionsof people benefit form Traditional Chinese Medicine(TCM) every day. Unfortunately， till now, TCM has not been accepted as science by world,especially western people.Bian Zheng Lun Zhi is distillation of TCM. Syndrome is key in system ofBian ZhengLun Zhi. Study about the syndrome is core of study of basic theory of TCM.We creatively interpret TCM through aview of cognitive scinece and take syndromes of TCM as concepts of brain. This paper try to introduce syndrome to western people, in order to let western people understand our viewpoints more easily, the best method isto adopta manner thatis easilyunderstoodby them,already exists,and has been thought to be right.So we employ neural network presented by foreign people as brain model instead of network presented by usUsing two classic case of TCM,we successfully clarify the three main properties of syndrome in TCM.

# I.INTRODUCTION

always considered a splendid treasure of China. It has a history of about three thousand years.Worldwide interest in herbal remedy of TCM has boomed these days [1]. The primary infrastructure of TCM is Bian Zheng Lun Zhi. It means TCM experts first identify and determine which Zheng that is called syndrome a patient caught based on information gathered from watching, snuffing,inquiring,and feeling the pulse (the four procedures are denoted as Si Zhen ), then they prescribe.People from community of TCM universally consider the Bian ZhengLun Zhias distillation of TCM.The syndrome is key in system of Bian Zheng Lun Zhi.Study about the syndrome is core of study of basic theory of TCM. Generally the syndrome is dependent on relation between (or among） symptoms.In fact the syndrome is diagnostic concepts produced by mean of mapping symptoms onto brain Till now,most people，especially westerners,have not accepted TCM as sciences.This may be because there is no mathematical and physical interpretations of TCM that are thought to be convincible of TCM.The best antidote that makes Bian Zheng Lun Zhi of TCM accepted is to combine brain sciences and basic theory in TCM.This is because syndrome is a concept of diagnostics,namely，syndrome exists in the brain of TCM expert who collects the whole symptoms ofa patient by Si Zhen.

Manuscript received September 12,20o5.This work was supported by the National Basic Research Program of China (973Program) under Grant No 2003CB517106.and Most projects (2004DFB02100)

Guangcheng Xi,corresponding author,（ Phone:861082618441,fax: 861062658815； e-mail: guangcheng.xi@mail.ia.ac.cn )， Jianxin Chen Jiangqiang Yi and Dongbin Zhao are with the Laboratory of Complex Systems & Intelligence Science, Institute of Automation,Chinese Academy of Sciences,Beijing 100o8o,China.

Yongyan Wang is with the Chinese Academy of Traditional Chinese Medicine.

A syndrome can be divided into some subtypes,each of which is composed of some symptoms and often could not be divided any more. Different subtype contains different symptoms by which the subtype is distinguished.

Real-In and Imaginary-Out, Spatiotemporal dynamics and Multidimensional interface are the main characters of syndrome [6].

Real-In and Imaginary-Out: With regard to all symptoms that relate to a syndrome, some of them fiercely contribute to thesyndrome,whicharelistedinacatalogthatisdenotedas “Real-In".Whereas others are less important than former counterpart and cataloged as another part that is denoted as "Imaginary-Out". Treatment that corresponds to a syndrome is composed of herbs with different ingredients.If symptoms belong to “Real-In” part,the ingredient of the herbs that corresponds to these symptoms is higher than counterpart than corresponds to symptoms from “Imaginary-Out".It is extremely vital to note that there are a few symptoms in “Real-In”that embody the syndrome,thatis,itis these few symptoms that characterize the syndrome significantly.

Spatiotemporal dynamics indicates that syndrome varies not only with time but space.After determining the “Real-In" and “Imaginary-Out”，TCM experts prescribe the herbal remedies accordingly.However, usually, first diagnosis can not completely heal all symptoms. Some symptoms disappear. but a few new symptoms may appear before second diagnosis. which may cause syndrome changes. So syndrome is of spatiotemporal dynamics.

A syndrome relates to several symptoms, a symptoms is a dimension.In addition,a interface exists between‘Real-In" and“Imaginary-Out", because symptoms that constitute each syndrome are usually not only one,so the interface is of multi-dimension.It can be clearly seen that syndrome has the property of multidimensional interface.

In this paper，we introduce TCM to western people by employing brain science and show that TCM can be interpreted scientifically.

As stated above, the syndrome is diagnostic concepts produced by mean of mapping symptoms onto brain. Therefore we annotate it by neural network. In order to let western people understand our viewpoints more easily, the best method is to adopt a manner that is easily understood by them,already exists,and has been thought to be right. So we employ neural network presented in [3] as brain model instead of network presented by us [4]

# II.NEURAL NETWORK MODEL

We have used the neural network model presented in [3],

which is Hopfield-like,parallel updated and devoted to the phase transition in neural networks for two reasons:

(a)Syndrome in TCM is a concept of diagnostics. (b)Phase transitions play a key role in thoughts of human brain.

The dynamics of the network is described by following equations:

$$
\begin{array} { l } { \displaystyle \mathrm { x } _ { \mathrm { i } } ( \mathrm { t } + 1 ) = \sum _ { \mathrm { j } = 1 } ^ { \mathrm { N } } \mathrm { w } _ { \mathrm { i j } } ( \mathrm { t } ) \mathrm { v } _ { \mathrm { j } } ( \mathrm { t } ) + \mathrm { Z } _ { \mathrm { i } } + \mathrm { \varepsilon } { \mathrm { I } } _ { \mathrm { i } } ( \mathrm { t } ) } \\ { \displaystyle \mathrm { v } _ { \mathrm { i } } ( \mathrm { t } ) = \frac { 1 } { 2 } ( 1 + \mathrm { t a n h } \frac { \mathrm { x } _ { \mathrm { i } } ( \mathrm { t } ) } { \mathrm { T } } ) } \end{array}
$$

where t is the discrete time, $\mathbf { X _ { i } }$ is the state variable of neuron i， $\mathrm { \Delta N }$ is the number of neurons contained in the neural network, $\mathbf { W } _ { \mathrm { i j } } ( \mathrm { t } )$ represents the synaptic connection from neuron j to neuron i at discrete time t, $Z _ { \mathrm { i } }$ is the neuron i's threshold which is supposed to be invariable during evolution, $\mathrm { I _ { i } }$ is an external input stimulus multiplied by an weak input gain 8 $\dag ( 0 { < } \mathfrak { E } \boxed { \begin{array} { c } { 1 } \end{array} } , \mathrm { T }$ is the temperature of the network. The output $\mathbf { V } _ { \mathrm { i } }$ of the i-th neuron takes a real value between O and 1. The synaptic weights $\mathbf { W } _ { \mathrm { i j } } ( 0 )$ for the initial state $( \mathrm { t } { = } 0 )$ are determined by following formation:

$$
\begin{array} { r l } & { \displaystyle \mathrm { w } _ { \mathrm { i j } } ( 0 ) { = } \frac { 1 } { \mathrm { N } } \sum _ { \mathrm { k } = 1 } ^ { \mathrm { K } } \mathfrak { a } _ { \mathrm { k } } ( 2 \mathrm { S } _ { \mathrm { i } } ^ { \mathrm { k } } - 1 ) ( 2 \mathrm { S } _ { \mathrm { j } } ^ { \mathrm { k } } - 1 ) { + } } \\ & { \displaystyle \frac { 1 } { \mathrm { N } } \sum _ { \mathrm { k } = 1 } ^ { \mathrm { K } } \beta _ { \mathrm { k } } ( 2 \mathrm { S } _ { \mathrm { i } } ^ { \mathrm { k } + 1 } { - } 1 ) ( 2 \mathrm { S } _ { \mathrm { j } } ^ { \mathrm { k } } - 1 ) } \end{array}
$$

Where ${ \bf S } _ { \mathrm { i } } ^ { \mathrm { k } }$ represents the i-th point of the $\mathbf { k }$ -th stored pattern. For the firing pattern of the network itinerate among K embede paterns,the ${ \bf S } _ { \mathrm { i } } ^ { \mathrm { K + 1 } }$ is set to qualing he ${ \bf S } _ { \mathrm { i } } ^ { 1 }$ for $\mathrm { I } { = } 1 { , } 2 { , } { \ldots } \mathrm { N }$ ： $\mathsf { a } _ { \mathrm { k } } , \mathsf { \beta } _ { \mathrm { k } }$ are responsible for the relative stability and the relative transition possibility of the k-th stored pattern $\{ \mathrm { S } _ { \mathrm { i } } ^ { \mathrm { k } } , \mathrm { I } { = } 1 , 2 , . . . . \mathrm { N } \}$ respectively.

The neural network operates in two basins,one is the pattern cyclically itinerant basin and the other is fixed point attractor. When the network runs in the former basin, the synaptic connection $\mathbf { W _ { \mathrm { i j } } }$ for $\mathrm { i , j } { = } 1 , 2 , . . . \mathrm { N }$ is updated parallelly as following Hebbian learning rules:

$$
\begin{array} { r l } & { \mathbf { w } _ { \mathrm { i j } } ( \mathrm { t } + 1 ) \mathbf { = } \mathbf { w } _ { \mathrm { i j } } ( \mathrm { t } ) \mathbf { + } \Delta \mathbf { w } _ { \mathrm { i j } } ( \mathrm { t } ) \qquad ( 4 ) } \\ & { \Delta \mathbf { w } _ { \mathrm { i j } } ( \mathrm { t } ) \mathbf { = } \left\{ \begin{array} { l l } { \gamma \mathbf { v } _ { \mathrm { i } } ( \mathrm { t } ) \mathbf { v } _ { \mathrm { j } } ( \mathrm { t } ) , \mathrm { i f } ( \mathbf { v } _ { \mathrm { i } } ( \mathrm { t } ) , \mathbf { v } _ { \mathrm { j } } ( \mathrm { t } ) \geq 0 . 9 ) } \\ { \delta ( 1 \mathrm { - } \mathbf { v } _ { \mathrm { i } } ( \mathrm { t } ) ) \mathbf { v } _ { \mathrm { j } } ( \mathrm { t } ) , \mathrm { i f } ( \mathbf { v } _ { \mathrm { i } } ( \mathrm { t } ) \leq 0 . 1 \& \mathbf { v } _ { \mathrm { j } } ( \mathrm { t } ) \geq 0 . 9 ) } \\ { 0 , \quad \mathrm { o t h e r w i s e } } \end{array} \right. } \end{array}
$$

Whereγ ,S satisfy: $0 < \gamma , | \delta | \bigtriangledown \ 1 , \delta < 0$ ，the state variable andoutput of neuronsof thenetworkarerenewed parallelly under the stimulation of an external input corresponding to one of the K stored patterns. After some periods of learning process, the network falls suddenly into the external input, that is,the neural network transits from the cyclically itinerant basin into the fixed pattern basin,which is a kind of phase transition by which thought is produced in neural network [4];When the neural network stays at the point attractor basin, the synaptic couplings are renewed according to the Hebbian unlearning rule composed of equation (4) and

$$
\Delta \mathrm { w } _ { \mathrm { i j } } ( \mathrm { t } ) { = } { \bf { - } } \kappa ( 2 \mathrm { v } _ { \mathrm { i } } ( \mathrm { t } ) { - } 1 ) ( 2 \mathrm { v } _ { \mathrm { j } } ( \mathrm { t } ) { - } 1 )
$$

The neural network is updated without any input and eventually runs in the pattern cyclically itinerant basin, which is also a kind of phase transition that drives the network into ready state (Figure 1).i.e., transitions between the two basins of the neural network are well-defined and reversible.

![](images/41e5ef6fcdd755b7286899ef68394bc7858f4acc869e8107b9ec34959b3fba17.jpg)  
Fig.1. The output of the neural network varies temporally. If the hamming distance from current network's output to pattern 1(pattern 2) is less than 1.7(O.1N),a colorful point is plot at the corresponding row. Otherwise, the point vanishes. Green (blue) point represents the network operates in the fixed pattern 1(2) basin.Brown point represents the network runs in the pattern cyclically itinerant basin.The network itinerates between two patterns so frequent that the brown points look like a line.However,the network operates in patterncyclicallyitinerant basin indeed

# III.ENCODING THE SYMPTOMS AS EMBEDDED PATTERNS

We get two classic TCM's cases from reference[5],in which the two patients were diagnosed as catching same disease-- typhoid fever but distinct cold syndromes subtypes due to some key different symptoms by which the cold syndromes subtypes are distinguished, although the two subtypes belong to same kind of cold syndrome and have five identical symptoms.We first have to encode the symptoms as two stored patterns of neural network.As presented in Table1, the two syndrome subtypes totally have 17 symptoms where the first subtype called sthenia cold syndrome,contains 12 symptoms and the second,called asthenia or deficient cold syndrome, is composed of 10.The encoded two patterns are shown in Table 2.It is noted here that the network with 17 neurons can store and retrieve two patterns without error, sincethecapacityofHopfield networkis0.15, while $1 7 ^ { * } 0 . 1 5 = 2 . 5 5 > 2$ ：

![](images/f3de44d13085f3b7a0024103eedf175bb9d4235243aaa0797b915be8bcebe5ef.jpg)  
Fig.2.Phase transition (2-A)and reverse phase transition (2-B)

# IV．PHASE TRANSITIONS

The parameters of the neural network are chosen as following, $\scriptstyle \mathrm { T = } 0 . 0 0 1 5$ $\mathfrak { a } _ { \mathrm { k } } = 0 . 7 , \beta _ { \mathrm { k } } = 0 . 3$ for $\mathrm { k } { = } 1 , 2 . \mathrm { } Z _ { \mathrm { i } } { = } { - } 0 . 0 1 4$ for each i, $\scriptstyle \varepsilon = 0 . 0 1$ 5 $\mu = - \delta = \kappa = 0 . 0 0 0 0 1$ . We set the neural network into the initial state and let the neural network undergoes unlearning process,after a period of time，the network will operate in the pattern cyclically itinerant basin, then a weak stimulus that corresponds to pattern 2, that is, the deficient cold syndrome,inputs into the network, the synaptic strength will be organized according to the Hebbian learning rule,after some courses of learning, the network suddenly falls into the second pattern, namely, the second syndrome subtype is recognized. When the phase transitions take place, according to our conclusion, the thought will be produced in the brain, then the concept is identified in the brain.Here, we consider a syndrome subtype as a concept,so if a syndrome subtype is identified by the brain，then “Bian Zheng”is successfully， the corresponding herbal remedy can be prescribed. The phase transitions between the two subtypes are implemented by an unlearning process.

As shown in [3],the transitions between two basins are measured by the largest eigenvalue of the Jacobian matrix calculated by a Tailor expansion of the equ (2) in the vicinity of the equilibrium point. The critical point corresponds to the Jacobian matrix's largest eigenvalue that equals unit (Figure 2).

The temporal change of eigenvalues of Jacobian matrix attributes to the variation of the states of network, so we analyze the outputs of neurons around transition point, finding out that only five,not all,neurons changes their outputs,other 12 neurons keep the same as the corresponding values of pattern 2 and constant around the critical point (Table3),that is to say,itis these neurons whose states and outputs keep variable that drive the network from the largest eigenvalue $^ { > 1 }$ to $^ { < 1 }$ Meanwhile,itis important to note that these neurons correspond to the symptoms that are specific for second subtype and not contained in the first subtype.

We further classify the five key symptoms and determine the most important symptoms(s) by anatomizing the eigenvectors of the Jacobian matrix in the neighbors of the critical point. The significance of the five elements is ranked by absolute values of the corresponding component of the eigenvectors (Table 4).We can easily dissect the five key symptoms into two components,one part is the symptom1,which has the most significance due to the absolute value of corresponding component of the eigenvector that corresponds to the secondly largest eigenvalue is the biggest.Another is the other four elements that can not be divided any more.

By mean of same method,we also find that symptom 2 has the most significance in first subtype.That is to say, headache withoutsweatingis the coreof stheniacold syndrome,while sweating like rain is the core of deficient cold syndrome.It can be concluded that the core symptom that distinguish two cold syndrome subtypes is whether the patient sweats or not. Although the two patients caught same disease,however, they are diagnosed as different subtype,so the corresponding herbs is somewhat different. The primary component of herbs that correspond to sthenia cold syndrome is Ephedra and Manchurian Wildginger, whereas the primary component of herbs that correspond to deficient cold syndrome is Ramulus Cinnamomi and White peony Alba.

# V.INTERPRETATION

# A.Theinterpretationof theReal-in and Imaginary-out

Since a syndrome subtype is a concept and is denoted by a pattern. The pattern is a vector with $\mathrm { \Delta N }$ dimensions,each dimension is used to represent a symptom and is assigned either $\cdot _ { 0 } ,$ or $\cdot _ { 1 } \cdot$ ,in which‘1’is denoted as the symptom belongs to the syndrome subtype while $\cdot _ { 0 } ,$ is denoted as the symptom belongs to other subtypes.However,we can not determine which symptoms are the real part of the syndrome and which are imaginary. We use differences between the components of eigenvector that corresponds to the largest eigenvalues and corresponding components of the pattern to indicate the contribution of a symptom to a syndrome.The less the difference is, the more significant a symptom is. We

# REFERENCES

![](images/c37d05c56e064b98178cfbd558669c2d772e08e2904a1830d68a3363d289f71b.jpg)  
Fig.3 Real-In and Imaginary-Out

[1] D.Normile,The new face of Traditional Chinese Medicine,Science. 299(2003)188-190.   
[2] T.H.Xue,R.Roy,Studying Traditional Chinese Medicine,Science. 300(2003). 740-741   
[3] O.Hoshino,Y.Kashimori,T.Kambara,Self-organized phase transitions in neural networks as a neural mechanism of information processing ,Proc.Natl.Acad. Sci.U.S.A.93(1996),3303-3307   
[4] G.C.Xi,Variability of structure of abstract neural automata and the ability of thought,Kyberneles.32(2003),1549-1554.   
[5] G.R.Ding,Ding Gan Ren Yi An (Shang Hai Techology and Science Press,ed,1,1960) pp.8-9   
[6] L.Guo, Y.Y.Wang, Z.B. Zhang,About the annotation to the concept of syndrome, Journal of Beijing University of TCM.26(2003), 5-8.

take pattern 2 as example.After the network transits to the pattern， the eigenvector that corresponds to the largest eigenvalue is calculated, then we can easily compute the differences.For the first,fifth,ninth,thirteenth,sixteenth symptoms,we find out that the differences are all the same (about O.553 unit) and less than corresponding differences for the fourth, seventh, tenth, fifteenth,seventeenth symptoms(1 unit).So the former five symptoms are the real part of the syndrome and latter five symptoms are imaginary part. Because the differences of the former five symptoms are 0.553 unit, we choose the difference as the radius and plot a circle.By mean of the same method,we plot a concentric circles(Figure3)， whichinterpretsthefeatureof syndrome—Real-in and Imaginary-out.

# B.The interpretation of the spatiotemporal dynamics

Due to the eigenvalues vary temporally, the syndrome is of the temporal property,in addition,obviously，syndrome has the spatial feature.

# C.TheinterpretationofMulti-dimensioninterface

Under our conditions,the network is stable if and only if space of configuration of the network is separable.Phase transition point corresponds to the bifurcation point of the new fixed point .Neural network passes through the transition point, enters the new stable state,realizes recall of the state, namely, the syndrome subtype.Thus separate theorem of hyper plane comes into existence under the situation.The hyper plane with N-1 dimensions separates the two syndrome subtypes.Syndrome is of multi-dimension interface.

# VI．CONCLUSION

We have creatively treated syndromes in TCM as concepts of brain，and by using two classical medical cases as two patterns of neural network that served as model of brain,we successfully clarify the main properties of syndrome--Real-in and Imaginary-out, spatiotemporal dynamics, Multi-dimension interface.

TABLEI TWO CLASSIC CASES OF TCM   

<html><body><table><tr><td>Posit- ion</td><td>Patient A</td><td>Patient B</td></tr><tr><td>1</td><td></td><td>Sweat like rain</td></tr><tr><td>2</td><td>headache without sweating</td><td></td></tr><tr><td>3</td><td>Interlocking</td><td></td></tr><tr><td>4</td><td>fever with chills</td><td>fever with chills</td></tr><tr><td>5</td><td></td><td>floatingwiry pulse</td></tr><tr><td>6</td><td>combined disease of Taiyangand Shaoying meridians</td><td></td></tr><tr><td>7</td><td>lumbago and aching of bones</td><td>lumbago and aching of bones</td></tr><tr><td>8</td><td>Double-meridian febrile disease</td><td></td></tr><tr><td>9</td><td></td><td>Taiyang is intruded bywind</td></tr><tr><td>10</td><td>abdominal pain and tenderness</td><td>Abdominal pain and tenderness</td></tr><tr><td>11</td><td>nausea and can not eat</td><td></td></tr><tr><td>12</td><td>tongue coating seems pale and sticky</td><td></td></tr><tr><td>13</td><td></td><td>tongue coating seems thin and sticky</td></tr><tr><td>14</td><td>deep,thready and slow pulse</td><td></td></tr><tr><td>15</td><td>post-menstrual excessive sexual activities</td><td>post-menstrual excessive sexual activities</td></tr><tr><td>16</td><td></td><td>skin and hair is open and JingYuPoint isclose</td></tr><tr><td>17</td><td>lower-energizer is blocked and accumulated</td><td>lower-energizer is blocked and accumulated</td></tr></table></body></html>

The medical case is a classical exemplification of the cold syndrome.The woman A suffered12 symptoms, diagnosing as a subtype of the cold syndrome- sthenia cold syndrome,whereas womanB had10 symptoms in which 5 symptoms resemble former,diagnosingas another subtype-deficient cold syndrome.The two subtype patterns totally composed of 17 symptoms. s0 $\scriptstyle \mathbf { M } = 2 , \mathbf { N } = 1 7$

TABLE2 TWO PATTERNS EMBEDED INTHEPRESENTNEURAL NETWORK   

<html><body><table><tr><td>Neuron</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td><td>16</td><td>17</td></tr><tr><td>Pattern 1</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td></tr><tr><td>Pattern 2</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>1</td><td>1</td></tr></table></body></html>

Two patternsare generatedby meansof binornd(2,17,0.5),where binorndrepresentsthebinomialdistribution.2and17 forms a matrix of $2 \times 1 7 . 0 . 5$ represents the probability that random variable is $\cdot _ { 0 } ,$ ：

TABLE3 THE OUTPUTS OF THE NEURAL NETWORK AROUND THE TRANSITIONPOINT   

<html><body><table><tr><td>t=19850+ Largest</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td></tr><tr><td>eigenvalue</td><td>1.4902 0.9308</td><td>1.3447 0.9733</td><td>1.2020 0.9495</td><td>1.0766 0.9706</td><td>0.9589 0.9620</td><td>0.8539 0.9710</td><td>0.7580 0.9699</td><td>0.6721 0.9739</td><td>0.5947</td></tr><tr><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.9752</td></tr><tr><td>2</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>4 5</td><td>1 0.9308</td><td>1</td><td>1 0.9495</td><td>1 0.9706</td><td>1 0.9620</td><td>1 0.9710</td><td>1 0.9699</td><td>1 0.9739</td><td>1</td></tr><tr><td></td><td></td><td>0.9733</td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.9752</td></tr><tr><td>6</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>7</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>8 9</td><td>0 0.9308</td><td>0 0.9733</td><td>0 0.9495</td><td>0 0.9706</td><td>0 0.9620</td><td>0 0.9710</td><td>0 0.9699</td><td>0 0.9739</td><td>0 0.9752</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>10</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>11</td><td>0 0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>12 13</td><td>0.9308</td><td>0 0.9733</td><td>0 0.9495</td><td>0 0.9706</td><td>0 0.9620</td><td>0 0.9710</td><td>0 0.9699</td><td>0 0.9739</td><td>0 0.9752</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>14 15</td><td>0 1</td><td>0 1</td><td>0 1</td><td>0 1</td><td>0 1</td><td>0 1</td><td>0 1</td><td>0 1</td><td>1</td></tr><tr><td>16</td><td>0.9308</td><td>0.9733</td><td>0.9495</td><td>0.9706</td><td>0.9620</td><td>0.9710</td><td>0.9699</td><td>0.9739</td><td>0.9752</td></tr><tr><td>17</td><td>1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr></table></body></html>

Itcanbeemploedasdeterminatingthe“Real-In”and“maginaryOutWeanalyze9timepointsaroundthecriticalpont.Wecanreadily findthatoliosts),,9gs(stdaltOthsi invariableandteralsalterorrspodingvalsofpatt2otefrerfvesmptosecatalogedas“Real-,icete variations of the five positions’value drive the largest eigenvalue changes from $^ { > 1 }$ to $^ { < 1 }$ .Meanwhile,positions(symptoms) 4,7,10,15,17are cataloged as“Imaginary-Out”.

TABLE4 . Eigenvectorss around the transition point.   

<html><body><table><tr><td colspan="3">The time before transition</td><td colspan="3">The time after transition</td></tr><tr><td>4.4721e-001</td><td>8.9442e-001</td><td>8.9442e-001</td><td>4.4721e-001</td><td>5.8467e-001</td><td>8.9442e-001</td></tr><tr><td>1.2727e-024</td><td>7.6259e-008</td><td>2.3558e-012</td><td>1.2839e-024</td><td>2.8370e-001</td><td>1.8979e-008</td></tr><tr><td>1.2727e-024</td><td>7.6250e-008</td><td>3.9262e-013</td><td>1.2840e-024</td><td>2.8372e-001</td><td>3.1632e-009</td></tr><tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>4.4721e-001</td><td>2.2360e-001</td><td>2.2360e-001</td><td>4.4721e-001</td><td>1.5383e-001</td><td>2.2360e-001</td></tr><tr><td>1.2727e-024</td><td>7.6250e-008</td><td>3.9262e-013</td><td>1.2840e-024</td><td>2.8372e-001</td><td>3.1632e-009</td></tr><tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>1.2727e-024</td><td>7.6250e-008</td><td>3.9262e-013</td><td>1.2840e-024</td><td>2.8372e-001</td><td>3.1632e-009</td></tr><tr><td>4.4721e-001</td><td>2.2360e-001</td><td>2.2360e-001</td><td>4.4721e-001</td><td>1.5383e-001</td><td>2.2360e-001</td></tr><tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>1.2727e-024</td><td>7.6250e-008</td><td>3.9262e-013</td><td>1.2840e-024</td><td>2.8372e-001</td><td>3.1632e-009</td></tr><tr><td>1.2727e-024</td><td>7.6250e-008</td><td>3.9262e-013</td><td>1.2840e-024</td><td>2.8372e-001</td><td>3.1632e-009</td></tr><tr><td>4.4721e-001</td><td>2.2360e-001</td><td>2.2360e-001</td><td>4.4721e-001</td><td>1.5385e-001</td><td>2.2360e-001</td></tr><tr><td>1.2727e-024</td><td>7.6250e-008</td><td>3.9262e-013</td><td>1.2840e-024</td><td>2.8372e-001</td><td>3.1632e-009</td></tr><tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>4.4721e-001</td><td>2.2360e-001</td><td>2.2360e-001</td><td>4.4721e-001</td><td>1.5383e-001</td><td>2.2360e-001</td></tr><tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

According to the basic theory of TCM there exista few(often one or two)symptoms in the“Real-In"which significantly characterize the syndrome.We analyze the eigenvectors corresponding to the eigenvalues( we usethelargest,secondly largest,thirdly largest),finding thatthe position(symptom)1 has the most significance